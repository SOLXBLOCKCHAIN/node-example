# Run a SOLX Validator
## Setting up a node
1. Git clone https://github.com/friendri311/CoinNetwork.git

2. Copy source form node-example to root folder
```
cp -r CoinNetwork/node-example/SOLX  /root/
```
3. Create an Account

```
cd /root/SOLX
chmod +x openethereum
./openethereum account new --config nodes/validator/node.toml
```
Returned address like that 0x00aa39d30f0d20ff03a22ccfc30b7efbfca597c2

Copy result address to node.toml
Ex:
```
...
[account]
unlock = ["0x00aa39d30f0d20ff03a22ccfc30b7efbfca597c2"]
password = ["password"]

[mining]
force_sealing = true
engine_signer = "0x00aa39d30f0d20ff03a22ccfc30b7efbfca597c2"
reseal_on_txs = "none"
...
```
4. Run the authority nodes
```
./openethereum --config ./nodes/validator/node.toml

```
5. Stake

    Stake

    To stake SOLX coin, all you should do is sending your SOLX coin to the SOLX Consensus contract address over the SOLX network from the validator address.
    The SOLX Consensus contract address: 0x865932C5Ce5371588a8B9E9E49680A278522727f
    The easiest way to do so, is to import your private key or key-store file to your favourite wallet (for example Metamask), switch network to SOLX and send the SOLX coin to the Consensus contract address.

    You can find your key-store (containing your private key) and the password for the created account in:
    /SOLX/nodes/validator/keys/SOLX/UTC--xxxx
    /SOLX/nodes/validator/node.pwd

6. Wait for 1 cycle (approximately 48 hours).

    Wait until the next cycle gets started.
