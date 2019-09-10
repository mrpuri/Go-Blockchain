# Go-Blockchain
Locally deployed blockchain developed in Golang.
It takes BPM of a person as the data stored securely in a block.

Using post requests, we can add blocks to the blockchain by passing the json value as raw body value ( {"BPM":72} )
Genesis block is the first block in the Blockchain array of struct block.

Genesis block has following properties
 1. index:0
 2. previous hash: " "
 3. BPM:62
 4. hash: genesisBlock.hash //generate by createHash function by adding current time, index, bpm and prev hash using a SHA256.

every new block added to the Blockchain array undergoes the following process:
1. generating the block through generateBlock() with oldBlock and BPM as arguments.
2. calculating hash through calculateHash().
3. Validating the Block.
and finally addition the the Chain.

ReplaceChain function is also present which solves the basic blockchain problem of selecting the 
longest blockchain in case a duplicate blockchain is present.

The local server is made using gorrila/Mux. For further reference about gorrila/mux click visist this link https://github.com/gorilla/mux.
