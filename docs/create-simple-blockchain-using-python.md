# 使用 Python 创建简单的区块链

> 原文:[https://www . geeksforgeeks . org/create-simple-区块链-using-python/](https://www.geeksforgeeks.org/create-simple-blockchain-using-python/)

**一个区块链**是一个带有时间戳的分散的固定记录系列，包含任何大小的数据，由分散在全球各地的大型计算机网络控制，不归单一组织所有。每个块都是安全的，并使用哈希技术相互连接，防止未经授权的人对其进行篡改。

**使用 Python 创建区块链，挖掘新的区块，显示整个区块链:**

*   Data will be stored in JSON format, which is very easy to implement and read. Data is stored in a block, which contains multiple data. Many blocks are added every minute. To distinguish them, we will use fingerprint identification.
*   Fingerprint identification is done by using hash. Specifically, we will use SHA256 hash algorithm. Each block will contain its own hash and the hash of the previous function, so that it will not be tampered with.
*   The fingerprint will be used to chain the blocks together. Each block will be appended to the previous block with its hash and appended to the next block by giving its hash.
*   The exploitation of new blocks is completed by giving the work certificate of successfully finding the answer. To make mining difficult, the evidence of work must be hard enough to be mined.
*   After successfully mining the block, the block will be added to the chain.
*   After excavating several blocks, the validity of the chain must be checked to prevent any tampering with the blockchain.
*   Then use **mask** to make network applications, and deploy them locally or publicly according to users' needs.

## 蟒 3

```
# Python program to create Blockchain

# For timestamp
import datetime

# Calculating the hash
# in order to add digital
# fingerprints to the blocks
import hashlib

# To store data
# in our blockchain
import json

# Flask is for creating the web
# app and jsonify is for
# displaying the blockchain
from flask import Flask, jsonify

class Blockchain:

    # This function is created
    # to create the very first
    # block and set it's hash to "0"
    def __init__(self):
        self.chain = []
        self.create_block(proof=1, previous_hash='0')

    # This function is created
    # to add further blocks
    # into the chain
    def create_block(self, proof, previous_hash):
        block = {'index': len(self.chain) + 1,
                 'timestamp': str(datetime.datetime.now()),
                 'proof': proof,
                 'previous_hash': previous_hash}
        self.chain.append(block)
        return block

    # This function is created
    # to display the previous block
    def print_previous_block(self):
        return self.chain[-1]

    # This is the function for proof of work
    # and used to successfully mine the block
    def proof_of_work(self, previous_proof):
        new_proof = 1
        check_proof = False

        while check_proof is False:
            hash_operation = hashlib.sha256(
                str(new_proof**2 - previous_proof**2).encode()).hexdigest()
            if hash_operation[:4] == '00000':
                check_proof = True
            else:
                new_proof += 1

        return new_proof

    def hash(self, block):
        encoded_block = json.dumps(block, sort_keys=True).encode()
        return hashlib.sha256(encoded_block).hexdigest()

    def chain_valid(self, chain):
        previous_block = chain[0]
        block_index = 1

        while block_index < len(chain):
            block = chain[block_index]
            if block['previous_hash'] != self.hash(previous_block):
                return False

            previous_proof = previous_block['proof']
            proof = block['proof']
            hash_operation = hashlib.sha256(
                str(proof**2 - previous_proof**2).encode()).hexdigest()

            if hash_operation[:4] != '00000':
                return False
            previous_block = block
            block_index += 1

        return True

# Creating the Web
# App using flask
app = Flask(__name__)

# Create the object
# of the class blockchain
blockchain = Blockchain()

# Mining a new block
@app.route('/mine_block', methods=['GET'])
def mine_block():
    previous_block = blockchain.print_previous_block()
    previous_proof = previous_block['proof']
    proof = blockchain.proof_of_work(previous_proof)
    previous_hash = blockchain.hash(previous_block)
    block = blockchain.create_block(proof, previous_hash)

    response = {'message': 'A block is MINED',
                'index': block['index'],
                'timestamp': block['timestamp'],
                'proof': block['proof'],
                'previous_hash': block['previous_hash']}

    return jsonify(response), 200

# Display blockchain in json format
@app.route('/get_chain', methods=['GET'])
def display_chain():
    response = {'chain': blockchain.chain,
                'length': len(blockchain.chain)}
    return jsonify(response), 200

# Check validity of blockchain
@app.route('/valid', methods=['GET'])
def valid():
    valid = blockchain.chain_valid(blockchain.chain)

    if valid:
        response = {'message': 'The Blockchain is valid.'}
    else:
        response = {'message': 'The Blockchain is not valid.'}
    return jsonify(response), 200

# Run the flask server locally
app.run(host='127.0.0.1', port=5000)
```