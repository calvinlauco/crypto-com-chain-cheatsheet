```
chain-maind keys add multisig1 --keyring-backend=test

chain-maind keys add --multisig-threshold=2 --multisig=multisig1,multisig2,multisig3 multisig --keyring-backend=test

chain-maind keys list  --keyring-backend=test

chain-maind tx bank send \
    tcro1xc5uw8j6h3cjd7m2l9pn7xzg97q5pv9mdvp8ly \
    tcro1xc5uw8j6h3cjd7m2l9pn7xzg97q5pv9mdvp8ly  \
    1basetcro \
    --keyring-backend=test \
    --gas-prices=0.1basetcro \
    --chain-id=testnet-croeseid-2 --keyring-backend=test --node=https://testnet-croeseid.crypto.com:26657 \
    --broadcast-mode=async \
    --generate-only > unsigned.json

chain-maind tx sign \
    --multisig=tcro1xc5uw8j6h3cjd7m2l9pn7xzg97q5pv9mdvp8ly \
    --from=multisig1 \
    --node=https://testnet-croeseid.crypto.com:26657 \
    --chain-id=testnet-croeseid-2 \
    --keyring-backend=test unsigned.json > multisig1-signed.json

chain-maind tx multisign unsigned.json \
    multisig multisig1-signed.json multisig2-signed.json \
    --node=https://testnet-croeseid.crypto.com:26657 \
    --chain-id=testnet-croeseid-2 \
    --keyring-backend=test > signed.json

chain-maind tx broadcas signed.json --broadcast-mode=async --node=https://testnet-croeseid.crypto.com:26657
```
