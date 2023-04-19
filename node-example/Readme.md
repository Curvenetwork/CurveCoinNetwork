# Run a CURVE Validator
## Setting up a node
1. Git clone https://github.com/Curvenetwork/CurveCoinNetwork.git

2. Copy source form node-example to root folder
```
cp -r CurveCoinNetwork/node-example/CURVE  /root/
```
3. Create an Account

```
cd /root/CURVE
chmod +x openethereum
./openethereum account new --config nodes/validator/node.toml
```
Returned address like that 0x00aa39d30f0d20ff03a22ccfc30b7efbfca597c2

Copy result address to mode.toml
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

    To stake CURVE coin, all you should do is sending your CURVE coin to the CURVE Consensus contract address over the CURVE network from the validator address.
    The CURVE Consensus contract address: 0xC50Ca7Ead738F5501F5EF88F6015d7F09D238F95
    The easiest way to do so, is to import your private key or key-store file to your favourite wallet (for example Metamask), switch network to CURVE and send the CURVE coin to the Consensus contract address.

    You can find your key-store (containing your private key) and the password for the created account in:
    /CURVE/nodes/validator/keys/CURVE/UTC--xxxx
    /CURVE/nodes/validator/node.pwd

6. Wait for 1 cycle (approximately 48 hours).

    Wait until the next cycle gets started.
