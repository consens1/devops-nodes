# Devops-nodes
Guide how to set up your full node for BTC/ETH/ETC/LTC/Waves

## ETH(Parity)

Fast start:
```
# docker run --restart=always -ti -d -p 8545:8545 \ 
-p 8546:8546 -p 30303:30303  -p 30303:30303/udp \ 
parity/parity:v2.1.3 --ui-interface all --jsonrpc-interface all 
```
Full start(with docker volume) - [eth_etc.sh](https://github.com/button-tech/devops-nodes/blob/master/eth_etc.sh)

- Disk space used ~ 100GB

- Load average ~ 3.38, 3.36, 3.31


Virtual machine specifications:

- CPU: Intel(R) Xeon(R) CPU E5-2676 v3 @ 2.40GHz

- RAM: 4GB

- Disk space: 600GB

## ETC(Parity)

Fast start:
```
# docker run --restart=always -ti -d -p 8545:8545 \ 
-p 8546:8546 -p 30303:30303 -p 30303:30303/udp \ 
parity/parity:v2.1.3 --ui-interface all --jsonrpc-interface all \
 --chain classic 
```
Full start(with docker volume) - [eth_etc.sh](https://github.com/button-tech/devops-nodes/blob/master/eth_etc.sh)

(Add the "--chain classic" flag to the end of the script)

- Disk space used ~ 146GB

- Load average ~ 0.12, 0.09, 0.06


Virtual machine specifications:

- CPU: Intel(R) Xeon(R) CPU E5-2676 v3 @ 2.40GHz

- RAM: 4GB

- Disk space: 600GB


## BTC(Insight-api)

```
# git clone https://github.com/WooGenius/bitcore-docker
# cd bitcore-docker
# docker-compose up --build -d
```

Or use this -  [btc.sh](https://github.com/button-tech/devops-nodes/blob/master/btc.sh)


- Disk space used ~ 443GB

- Lload average ~ 0.13, 0.03, 0.01


Virtual machine specifications:

- CPU: Intel(R) Xeon(R) CPU E5-2676 v3 @ 2.40GHz

- RAM: 4GB

- Disk space: 600GB


## LTC(Insight-api)

```
# docker run -e LITECOIN_LIVENET=1 -d -p 3001:3001 -p 9333:9333 \ 
-v your_volume:/root/litecoin-node/livenet \
--name litecoin-livenet berrywallet/litecore-node
```

- Disk space used ~ 50GB

- Lload average ~ 0.01, 0.02, 0.00


Virtual machine specifications:

- CPU: Intel(R) Xeon(R) CPU E5-2686 v4 @ 2.30GHz

- RAM: 4GB

- Disk space: 500GB

## Waves 

```
# docker run -d -p 6869:6869 -p 6868:6868 -e WAVES_NETWORK=MAINNET \ 
 -e WAVES_LOG_LEVEL=DEBUG -e WAVES_HEAP_SIZE=2g -v your_volume:/waves wavesplatform/node
```



