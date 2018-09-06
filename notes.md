

180903~180906

parity-bridge code analysis

cli/, deploy/   cmd tools to use parity bridge
bridge/, the core implementation part of this project
contracts/, the core main and side smart contracts implementation using solidity
compiled_contracts, compiled contracts to load
integration-tests/, test files and configs
res/, tools/, truffle, helper directories

The most cares:  
contracts/bridge.sol
bridge/src/


Main problem:

How to make ethereum node A execute smart contract to interact with this bridge relay?



180831
1. 
We can take ethereum mainnet as the HOME chain, another ethereum based chain as the FOREIGN chain. Parity-bridge can bridge these two chains.  Parity-bridge works as a seperate process, home account can deposit ether in the bridge channel, and the foreign account will receive  corresponding ERC20 token .

parity-bridge sign deposit transaction with authority secret, and it must be a separate process ( not a third chain? It seems using relay tech to reach it), and why the FOREIGN chain can admit it, I want to ask.

no enough docs on it, so I need to read code of parity-bridge to learn it.

2. And next, I need to read substrate documents and try to deploy it.

180829~30
1. Compile parity-bridge, fix some compiling bugs (later to submit issue on parity-bridge project);
2. Read parity config document, do research how to make two private chains with PoA, and use parity-bridge to connect to them;



