# Geth POA docker network

This repository contains a docker-compose file to start a private ethereum network with a geth bootnode and 2 miners/validators.

## Start the network

To start the network run:

```bash
docker-compose up
```
The validators will expose their rpc port on localhost:8541 (miner 1) and localhost:8543 (miner 2).

Give it a try with curl:

```bash
```bash
curl -i -X POST \
-H "Content-Type: application/json" \
--data '{"jsonrpc":"2.0","method":"eth_getBalance","params":["0x767cfb66c9f2a8a66ebc817d4981f6897d2c07fd","latest"],"id":1}' \
"localhost:8541"
```

The address `0x767cfb66c9f2a8a66ebc817d4981f6897d2c07fd` is prefilled with 1 Eth.

If you want to increase the amount of Eth, feel free to change the genesis file and restart the network.