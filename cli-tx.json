```
chain-maind query bank balances tcro1j7pej8kplem4wt50p4hfvndhuw5jprxxn5625q --node=https://testnet-croeseid.crypto.com:26657

tcrocnclconspub1zcjduepqnkh82r7yvc5he94wya7j8tpdwuvql60afkthzv356ye6k9t2h2psr3u067
tcrocnclconspub1zcjduepq7pwhpamngugc7g4sgh5e2dfnpr8hg6d34xc8k7f3mv5eqtr3l2vqlm7l

chain-maind query tx 8073901A78389B15DBED8AFD759A5EDE79F7BBD940323DAC5BF7B4989BE40CFD --node=https://testnet-croeseid.crypto.com:26657 --output=json

chain-maind tx bank send \
    tcro1j7pej8kplem4wt50p4hfvndhuw5jprxxn5625q \
    tcro1j7pej8kplem4wt50p4hfvndhuw5jprxxn5625q  \
    10010000tcro \
    --gas-prices=0.1basetcro \
    --chain-id=testnet-croeseid-2 --keyring-backend=test --node=https://testnet-croeseid.crypto.com:26657 \
    --generate-only \
    --broadcast-mode=async

chain-maind tx staking delegate \
    tcrocncl1j7pej8kplem4wt50p4hfvndhuw5jprxxxtenvr \
    1tcro \
    --from=ledger-cosmos-0 \
    --offline --ledger  --sign-mode=amino-json \
    --chain-id=testnet-croeseid-2  --keyring-backend=test --node=https://testnet-croeseid.crypto.com:26657

chain-maind tx staking delegate \
    tcrocncl1j7pej8kplem4wt50p4hfvndhuw5jprxxxtenvr \
    1tcro \
    --from=tcro1w34k53py5v5xyluazqpq65agyajavep2487axh \
    --offline --ledger  --sign-mode=amino-json  --generate-only \
    --chain-id=testnet-croeseid-1 --keyring-backend=test > unsigned.json

chain-maind tx sign unsigned-tx.json \
    --from=ledger-cosmos-0 \
    --sign-mode=legacy-amino --offline \
    --chain-id=testnet-croeseid-1 --keyring-backend=test > signed.json
```
