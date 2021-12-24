# 如何在 Pygame 中添加音乐播放列表？

> 原文:[https://www . geesforgeks . org/how-to-add-music-playlist-in-pygame/](https://www.geeksforgeeks.org/how-to-add-music-playlist-in-pygame/)

在本文中，我们将看到如何在 Pygame 中添加音乐播放列表。

Pygame 有一个方法， ***pygame.mixer()*** 它具有所有关于音频操作的功能，如播放歌曲、对歌曲进行排队、设置音量、倒带、停止、暂停、继续等等。该类提供的功能有–

*   **pygame . mixer . music . load():**这将加载音乐文件/文件名对象。
*   ***pygame . mixer . music . play(loops，start，fade_ms )*** :开始播放已加载的音乐。这需要 3 个参数
    *   **循环:**这是一个可选的整数参数，表示歌曲应该重复多少次。如果设置为-1，那么它将无限循环。
    *   **start:** 这是一个可选的 float 参数，表示音乐开始播放的时间和位置。
    *   **fade_ms:** 是可选的整数参数。它使音乐从 0 音量开始，并在给定时间逐渐变满音量。
*   **pygame . mixer . music . queue():**这将在当前音乐文件的末尾排队一首歌曲。当前文件一结束，下一个排队的音乐文件就会播放。您还可以将多首歌曲排队，这将是我们构建播放列表的主要逻辑。
*   **pygame . mixer . music . rewind():**这将当前音乐文件的回放倒回到开头。
*   **pygame . mixer . music . pause():**这将暂停当前音乐文件的播放。
*   **pygame . mixer . music . set _ endevent():**这发出一个信号，即一个事件。如果音乐文件已经播放完毕，将会有一个事件排队。
*   **pygame . mixer . music . get _ busy():**返回一个布尔值，表示当前是否播放过音乐文件。

## 在 Pygame 中添加播放列表

为了在 Pygame 中创建播放列表，我们将使用上面提到的所有方法来形成一个流程，在这个流程中，我们选择的所有音乐文件都将被推到列表中，并且这些文件中的每一个都将按顺序一个接一个地排队和播放。该逻辑可以如下实现:

*   使用**pygame . mixer . music . load()**将包含音乐文件的列表的第一个条目加载到 pygame 中，同时从列表中删除第一个条目。
*   在加载第一首歌曲时，我们将使用**pygame . mixer . music . play()**播放。
*   随后，我们还将使用**pygame . mixer . music . queue()**对第二个条目进行排队，并将其从我们的列表中删除。
*   每当音乐结束时，我们都会举办一个活动 **pygame。MUSIC_END** 通过使用**pygame . mixer . MUSIC . set _ endevent()**通知玩家从列表中排队下一首歌曲。
*   一旦我们的播放列表中的所有音乐文件都已播放/排队，那么**pygame . mixer . music . get _ busy()**返回 false，我们中断 for 循环和 while 循环，从而结束我们的程序。

**下面是实现:**

## 计算机编程语言

```
import pygame

# setting up pygame
pygame.init()

def insert_into_playlist(playlist, music_file):

    # Adding songs file in our playlist
    playlist.append(music_file)

def start_playlist(playList):

    # Loading first audio file into our player
    pygame.mixer.music.load(playList[0])

    # Removing the loaded song from our playlist list
    playList.pop(0)

    # Playing our music
    pygame.mixer.music.play()

    # Queueing next song into our player
    pygame.mixer.music.queue(playList[0])
    playList.pop(0)

    # setting up an end event which host an event
    # after the end of every song
    pygame.mixer.music.set_endevent(pygame.MUSIC_END)

    # Playing the songs in the background
    running = True
    while running:

        # checking if any event has been
        # hosted at time of playing
        for event in pygame.event.get():

            # A event will be hosted
            # after the end of every song
            if event.type == pygame.MUSIC_END:
                print('Song Finished')

                # Checking our playList
                # that if any song exist or
                # it is empty
                if len(playList) > 0:

                    # if song available then load it in player
                    # and remove from the player
                    pygame.mixer.music.queue(playList[0])
                    playList.pop(0)

            # Checking whether the 
            # player is still playing any song
            # if yes it will return true and false otherwise
            if not pygame.mixer.music.get_busy():
                print("Playlist completed")

                # When the playlist has
                # completed playing successfully
                # we'll go out of the
                # while-loop by using break
                running = False
                break

if __name__ == '__main__':

    # This list is going to be
    # our playlist as we can
    # only queue one song at a
    # time by using `.queue()` method
    # therefore we are using list
    # and will queue song one by one.
    playList = []

    insert_into_playlist(playList, 'eg1.wav')
    insert_into_playlist(playList, 'eg2.wav')
    insert_into_playlist(playList, 'eg3.wav')

    start_playlist(playList)
```

**输出:**

<video class="wp-video-shortcode" id="video-641672-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210708214827/pygame_playlist.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20210708214827/pygame_playlist.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210708214827/pygame_playlist.mp4)</video>