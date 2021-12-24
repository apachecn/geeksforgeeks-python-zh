# A3C 算法涉及的基础函数说明

> 原文:[https://www . geeksforgeeks . org/基本函数解释-参与-a3c-算法/](https://www.geeksforgeeks.org/explanation-of-fundamental-functions-involved-in-a3c-algorithm/)

虽然**异步优势演员评论家**算法的任何实现都必然是复杂的，但是所有的实现都有一个共同点——全球网络和工人类的存在。

1.  **全局网络类:**这包含自主创建神经网络所需的所有[张量流](https://www.tensorflow.org/)操作。
2.  **Worker 类:**这个类用来模拟一个拥有自己的环境副本和“个人”神经网络的工人的学习过程。

对于以下实施，需要以下模块:-

1.  数字
2.  张量流
3.  多重处理

下面几行代码表示构建相应类所需的基本功能。

**全球网络类:**

```
# Defining the Network class
class AC_Network():
```

下面几行包含描述上面定义的类的成员函数的各种函数。

**初始化类:**

```
# Initializing the class
def __init__(self, s_size, a_size, scope, trainer):
        with tf.variable_scope(scope):

            # Input and visually encoding the layers
            self.inputs = tf.placeholder(shape =[None, s_size], 
                                         dtype = tf.float32)
            self.imageIn = tf.reshape(self.inputs, shape =[-1, 84, 84, 1])
            self.conv1 = slim.conv2d(activation_fn = tf.nn.elu,
                                    inputs = self.imageIn, num_outputs = 16,
                                    kernel_size =[8, 8],
                                    stride =[4, 4], padding ='VALID')
            self.conv2 = slim.conv2d(activation_fn = tf.nn.elu,
                                    inputs = self.conv1, num_outputs = 32,
                                    kernel_size =[4, 4],
                                    stride =[2, 2], padding ='VALID')
            hidden = slim.fully_connected(slim.flatten(self.conv2),
                                          256, activation_fn = tf.nn.elu)
```

```
-> tf.placeholder()       - Inserts a placeholder for a tensor that will always be fed.
-> tf.reshape()           - Reshapes the input tensor
-> slim.conv2d()          - Adds an n-dimensional convolutional network
-> slim.fully_connected() - Adds a fully connected layer

```

**注意以下定义:**

*   **滤镜:**它是一个小矩阵，用于对给定的图像应用不同的效果。
*   **填充:**是在图像的边界上增加额外的一行或一列，以完整计算滤波器的滤波器卷积值的过程。
*   **步幅:**是在给定方向上对像素设置滤镜后的步数。

**建设循环网络:**

```
def __init__(self, s_size, a_size, scope, trainer):
        with tf.variable_scope(scope):
           . . . . . . . . . . 
           . . . . . . . . . .
           . . . . . . . . . .

            # Building the Recurrent network for temporal dependencies
            lstm_cell = tf.nn.rnn_cell.BasicLSTMCell(256, state_is_tuple = True)
            c_init = np.zeros((1, lstm_cell.state_size.c), np.float32)
            h_init = np.zeros((1, lstm_cell.state_size.h), np.float32)
            self.state_init = [c_init, h_init]
            c_Init = tf.placeholder(tf.float32, [1, lstm_cell.state_size.c])
            h_Init = tf.placeholder(tf.float32, [1, lstm_cell.state_size.h])
            self.state_Init = (c_Init, h_Init)
            rnn_init = tf.expand_dims(hidden, [0])
            step_size = tf.shape(self.imageIn)[:1]
            state_Init = tf.nn.rnn_cell.LSTMStateTuple(c_Init, h_Init)
            lstm_outputs, lstm_state = tf.nn.dynamic_rnn(lstm_cell, rnn_init,
                                                    initial_state = state_Init,
                                                    sequence_length = step_size,
                                                    time_major = False)
            lstm_c, lstm_h = lstm_state
            self.state_out = (lstm_c[:1, :], lstm_h[:1, :])
            rnn_out = tf.reshape(lstm_outputs, [-1, 256])
```

```
-> tf.nn.rnn_cell.BasicLSTMCell()  - Builds a basic LSTM Recurrent network cell
-> tf.expand_dims()                - Inserts a dimension of 1 at the dimension index
                                     axis of input's shape
-> tf.shape()                      - returns the shape of the tensor
-> tf.nn.rnn_cell.LSTMStateTuple() - Creates a tuple to be used by
                                     the LSTM cells for state_size,
                                     zero_state and output state.
-> tf.nn.dynamic_rnn()             - Builds a Recurrent network according to
                                     the Recurrent network cell

```

**构建价值和政策估算的输出层:**

```
def __init__(self, s_size, a_size, scope, trainer):
        with tf.variable_scope(scope):
           . . . . . . . . . . 
           . . . . . . . . . .
           . . . . . . . . . .

           # Building the output layers for value and policy estimations
            self.policy = slim.fully_connected(rnn_out, a_size,
                                               activation_fn = tf.nn.softmax,
                   weights_initializer = normalized_columns_initializer(0.01),
                                               biases_initializer = None)
            self.value = slim.fully_connected(rnn_out, 1,
                activation_fn = None,
                weights_initializer = normalized_columns_initializer(1.0),
                biases_initializer = None)
```

**建立主网络并部署工作人员:**

```
def __init__(self, s_size, a_size, scope, trainer):
        with tf.variable_scope(scope):
           . . . . . . . . . . 
           . . . . . . . . . .
           . . . . . . . . . .
           with tf.device("/cpu:0"): 

              # Generating the global network
               master_network = AC_Network(s_size, a_size, 'global', None)

               # Keeping the number of workers
               # as the number of available CPU threads
               num_workers = multiprocessing.cpu_count()

               # Creating and deploying the workers
               workers = []
               for i in range(num_workers):
                   workers.append(Worker(DoomGame(), i, s_size, a_size,
                                 trainer, saver, model_path))
```

**运行并行张量流操作:**

```
def __init__(self, s_size, a_size, scope, trainer):
        with tf.variable_scope(scope):
           . . . . . . . . . . 
           . . . . . . . . . .
           . . . . . . . . . .

           with tf.Session() as sess:
               coord = tf.train.Coordinator()
               if load_model == True:
                   ckpt = tf.train.get_checkpoint_state(model_path)
                   saver.restore(sess, ckpt.model_checkpoint_path)
               else:
                   sess.run(tf.global_variables_initializer())

               worker_threads = []
               for worker in workers:
                   worker_work = lambda: worker.work(max_episode_length,
                                         gamma, master_network, sess, coord)
                   t = threading.Thread(target =(worker_work))
                   t.start()
                   worker_threads.append(t)
               coord.join(worker_threads)
```

```
-> tf.Session()                    - A class to run the Tensorflow operations
-> tf.train.Coordinator()          - Returns a coordinator for the multiple threads
-> tf.train.get_checkpoint_state() - Returns a valid checkpoint state
                                     from the "checkpoint" file
-> saver.restore()                 - Is used to store and restore the models
-> sess.run()                      - Outputs the tensors and metadata obtained
                                     from running a session

```

**更新全局网络参数:**

```
def __init__(self, s_size, a_size, scope, trainer):
        with tf.variable_scope(scope):
           . . . . . . . . . . 
           . . . . . . . . . .
           . . . . . . . . . .

           if scope != 'global':
               self.actions = tf.placeholder(shape =[None], dtype = tf.int32)
               self.actions_onehot = tf.one_hot(self.actions,
                                                a_size, dtype = tf.float32)
               self.target_v = tf.placeholder(shape =[None], dtype = tf.float32)
               self.advantages = tf.placeholder(shape =[None], dtype = tf.float32)

               self.responsible_outputs = tf.reduce_sum(self.policy * 
                                                        self.actions_onehot, [1])

                # Computing the error
                self.value_loss = 0.5 * tf.reduce_sum(tf.square(self.target_v -
                                                    tf.reshape(self.value, [-1])))
                self.entropy = - tf.reduce_sum(self.policy * tf.log(self.policy))
                self.policy_loss = -tf.reduce_sum(tf.log(self.responsible_outputs)
                                                         *self.advantages)
                self.loss = 0.5 * self.value_loss + 
                self.policy_loss-self.entropy * 0.01

                # Get gradients from the local network
                local_vars = tf.get_collection(tf.GraphKeys.TRAINABLE_VARIABLES,
                                               scope)
                self.gradients = tf.gradients(self.loss, local_vars)
                self.var_norms = tf.global_norm(local_vars)
                grads, self.grad_norms = tf.clip_by_global_norm(self.gradients,
                                                               40.0)

                # Apply the local gradients to the global network
                global_vars = tf.get_collection(tf.GraphKeys.TRAINABLE_VARIABLES,
                                               'global')
                self.apply_grads = trainer.apply_gradients(
                        zip(grads, global_vars))
```

```
-> tf.one_hot()              - Returns a one-hot encoded tensor
-> tf.reduce_sum()           - Reduces the input tensor along the input dimensions
-> tf.gradients()            - Constructs the symbolic derivatives of the sum
-> tf.clip_by_global_norm()  - Performs the clipping of values of the multiple tensors
                               by the ratio of the sum of the norms
-> trainer.apply_gradients() - Performs the update step according to the optimizer.

```

**定义将一个网络的参数复制到另一个网络的效用函数:**

```
def update_target_graph(from_scope, to_scope):
    from_vars = tf.get_collection(tf.GraphKeys.TRAINABLE_VARIABLES, from_scope)
    to_vars = tf.get_collection(tf.GraphKeys.TRAINABLE_VARIABLES, to_scope)

    op_holder = []
    for from_var, to_var in zip(from_vars, to_vars):
        op_holder.append(to_var.assign(from_var))
    return op_holder
```

```
-> tf.get_collection() - Returns the list of values in the collection with the given name.

```

**工人阶级:**

**定义类别:**

```
# Defining the Worker Class
class Worker():
```

下面几行代码描述了上述类的成员函数

**初始化类:**

```
# Initializing the class
def __init__(self, game, name, s_size, a_size, trainer, saver, model_path):

    # Creating a copy of the environment and the network
    self.local_AC = AC_Network(s_size, a_size, self.name, trainer)
    self.update_local_ops = update_target_graph('global', self.name)
```

**定义工作人员与其环境交互的功能:**

```
def work(self, max_episode_length, gamma, global_AC, sess, coord):
    episode_count = 0
    total_step_count = 0
    with sess.as_default(), sess.graph.as_default():                 
        while not coord.should_stop():
            sess.run(self.update_local_ops)
            episode_buffer = []
            episode_values = []
            episode_frames = []
            episode_reward = 0
            episode_step_count = 0
            d = False

            # Building the environment into the frame
            # buffer of the machine
            self.env.new_episode()
            s = self.env.get_state().screen_buffer
            episode_frames.append(s)
            s = process_frame(s)
            rnn_state = self.local_AC.state_init

            while self.env.is_episode_finished() == False:

                # Sampling the different actions
                a_dist, v, rnn_state = sess.run([self.local_AC.policy,
                                     self.local_AC.value,
                                     self.local_AC.state_out], 
                                     feed_dict ={self.local_AC.inputs:[s],
                                     self.local_AC.state_in[0]:rnn_state[0],
                                     self.local_AC.state_in[1]:rnn_state[1]})
                    a = np.random.choice(a_dist[0], p = a_dist[0])
                    a = np.argmax(a_dist == a)

                    # Computing the reward
                    r = self.env.make_action(self.actions[a]) / 100.0
                    d = self.env.is_episode_finished()
                    if d == False:
                        s1 = self.env.get_state().screen_buffer
                        episode_frames.append(s1)
                        s1 = process_frame(s1)
                    else:
                        s1 = s

                    episode_buffer.append([s, a, r, s1, d, v[0, 0]])
                    episode_values.append(v[0, 0])

                    episode_reward += r
                    s = s1                    
                    total_steps += 1
                    episode_step_count += 1
```

```
-> sess.as_default() - Sets the current session as the default session
-> self.env.new_episode() - Initializes a new training episode for the worker

```

**定义工人的培训功能:**

```
def train(self, global_AC, rollout, sess, gamma, bootstrap_value):

    rollout = np.array(rollout)
    observations = rollout[:, 0]
    actions = rollout[:, 1]
    rewards = rollout[:, 2]
    next_observations = rollout[:, 3]
    values = rollout[:, 5]

    # Calculating the rewards and compute the advantage function
    self.rewards_plus = np.asarray(rewards.tolist() + 
                                   [bootstrap_value])
    discounted_rewards = discount(self.rewards_plus, 
                                  gamma)[:-1]
    self.value_plus = np.asarray(values.tolist() + 
                                 [bootstrap_value])
    advantages = rewards + 
    gamma * self.value_plus[1:] - self.value_plus[:-1]
    advantages = discount(advantages, gamma)

    # Update the global network parameters
    rnn_state = self.local_AC.state_init
    feed_dict = {self.local_AC.target_v:discounted_rewards,
                self.local_AC.inputs:np.vstack(observations),
                self.local_AC.actions:actions,
                self.local_AC.advantages:advantages,
                self.local_AC.state_in[0]:rnn_state[0],
                self.local_AC.state_in[1]:rnn_state[1]}
    v_l, p_l, e_l, g_n, v_n, _ = sess.run([self.local_AC.value_loss,
                                     self.local_AC.policy_loss,
                                     self.local_AC.entropy,
                                     self.local_AC.grad_norms,
                                     self.local_AC.var_norms,
                                     self.local_AC.apply_grads],
                                     feed_dict = feed_dict)
        return v_l / len(rollout), p_l / len(rollout), 
        e_l / len(rollout), g_n, v_n
```