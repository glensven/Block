# Blockchain Setup
1) Created public directory named Block
2) Navigate to folder named "Block"
3) Open a terminal window (GitBash in Windows) navigate to your Blockchain-Tools folder and type the following command:
#### Terminal: ./puppeth
4) Name network" "block"
5) Choose the Clique (Proof of Authority) consensus algorithm.
6) Paste both account addresses from the first step one at a time into the list of accounts to seal.
7) Paste them again in the list of accounts to pre-fund. There are no block rewards in PoA, so you'll need to pre-fund.
8) You can choose no for pre-funding the pre-compiled accounts (0x1 .. 0xff) with wei. This keeps the genesis cleaner.
9) Complete the rest of the prompts, and when you are back at the main menu, choose the "Manage existing genesis" option.

10) Create the first node's data directory using the geth command and a couple of command-line flags. Be sure you are under your Block directory and run the following command from the terminal window:
#### Teriminal: ./geth account new --datadir node1
11) Next, create another account using a different datadir by running the following command in the terminal window:
#### Teriminal: ./geth account new --datadir node2
12) Initialize and tell the nodes to use our genesis block! Open the terminal window and run the following command to initialize node1.
#### Teriminal: ./geth init block/block.json --datadir node1
13) Repeat the same process for the second node by running the following command in the terminal window.
#### Teriminal: ./geth init block/block.json --datadir node2
14) Launch the first node into mining mode with the following command:
#### Teriminal: ./geth --datadir node1 --unlock "node1_address" --mine --minerthreads 1
14) Launch the second node into mining mode with the following command:
#### Teriminal: ./geth --datadir node2 --unlock "node2_address" --port 30304 --rpc --bootnodes "enode_address" --ipcdisable --allow-insecure-unlock
15) Open MyCrypto
