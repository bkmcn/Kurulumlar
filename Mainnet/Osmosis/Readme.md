<p align="center">
  <img height="100" height="auto" src="https://raw.githubusercontent.com/Nodeist/Kurulumlar/main/logos/osmosis.png">
</p>



# Osmosis Node Installation Guide
Feel free to skip this step if you already have Go and Cosmovisor.


## Install Go
We will use Go `v1.19.3` as example here. The code below also cleanly removes any previous Go installation.

```
sudo rm -rvf /usr/local/go/
wget https://golang.org/dl/go1.19.3.linux-amd64.tar.gz
sudo tar -C /usr/local -xzf go1.19.3.linux-amd64.tar.gz
rm go1.19.3.linux-amd64.tar.gz
```

### Configure Go
Unless you want to configure in a non-standard way, then set these in the `~/.profile` file.

```
export GOROOT=/usr/local/go
export GOPATH=$HOME/go
export GO111MODULE=on
export PATH=$PATH:/usr/local/go/bin:$HOME/go/bin
```


### Install Cosmovisor
We will use Cosmovisor `v1.0.0` as example here.

```
go install github.com/cosmos/cosmos-sdk/cosmovisor/cmd/cosmovisor@v1.0.0
```

## Install Node
Install the current version of node binary.

```
cd $HOME
git clone https://github.com/osmosis-labs/osmosis.git
cd osmosis
git checkout v13.1.2
make install
```

## Configure Node
### Initialize Node
Please replace `MONIKERNAME` with your own moniker.

```
osmosisd init MONIKERNAME --chain-id osmosis-1
```

### Download Genesis
The genesis file link below is Nodeist's mirror download. The best practice is to find the official genesis download link.

```
wget -O genesis.json https://snapshots.nodeist.net/osmosis/genesis.json --inet4-only
mv genesis.json ~/.osmosisd/config
```

### Configure Peers
Here is a script for you to update `persistent_peers` setting with these peers in `config.toml`.
```
PEERS=20913e92e8b9ea2d80ad34edd9b52e97886cf616@54.37.30.181:26656,33cf290cc0cfec8c59e6af86f1a5579303d21087@138.68.14.64:26656,7c5459ea4bbc41aa4d86ffe8126f0651155227c8@85.195.102.127:26656,7de231d5c75feb810a9196fa2a3e83e0576c88a9@212.95.53.152:26656,43785e5ffd8783393ea8094f77efcee5bdbcdce3@78.141.244.18:26656,1876eb08c7e93c965a895177f82c8725f89c0f65@54.214.183.228:26656,42745690b41f6a7515c4a87d88efda2e82b55b76@78.46.94.183:26656,f4b811759e55f665180545ad5e1b42573f660861@135.181.181.251:26656,8ec254ac8f261f00120f44eec4a46c21a6fd80c0@78.46.68.249:26656,30e9432879d5b0976b88e52120dc12338e40fc33@65.108.108.176:26656,ba90bda66b2436e42f07da1659c715aa1e7e98b3@15.235.14.240:26656,4c927f93d430baf31e6d6418e62c56f442f092bc@46.4.28.42:26656,a850f6d18912606e3dcab0c93e3d169d069d6915@51.79.99.19:26656,be930386104083882c7e491d60584e15c101c1da@178.128.156.131:26656,797094953d830f8727f3b5175f2b205df16d5867@45.77.212.231:26656,7226ca2c9761d61cecf3f6b0f619e6fee8da6586@35.215.6.104:26656,ec929701754be057fb38c824fc127e26add9c900@138.201.121.185:26666,724cef11bbe866269b3d67f7dd5ea539cc4096bf@198.244.164.186:26656,a6283307952423c1751431c220d11ed36b61ed84@143.110.237.113:26656,95f7624ab26311f8774eb2452577fed9ce4a1efa@5.9.87.218:26656,10f328a43a1ac7aeeae7ee34c1127ce6839e4265@15.235.13.139:26656,e0fbdbdce6ec8797412751edd00fbaf114c42fad@34.220.226.204:26656,4cccbb26639559c39f44758d246c5ed928f7717f@176.9.19.66:26656,fd0930fea06876e362e0a92046854ed651f27ac2@45.76.13.41:26656,e81c3c20833cfb5d652a9c842c9f1c8b1835479d@108.61.190.21:26656,c47e03ce1b82b136768581a028033c4e201962f6@65.108.79.45:26656,9352138fa4f5fd4d0607e13794adc7a2199cdb8b@74.118.142.76:26656,efbe79e244693ae343dd8b6308bf4b708da82200@74.118.139.212:26656,1f650c50f6c556d375ce47740ba1b58c608daab3@95.217.115.220:26656,bfb67b2ae345955d6bc0991450120669c683386e@149.56.25.66:26656,407267ac44b20a0a4258d0bbca1c9f657bf88d08@74.118.143.19:26656,d2247f7b919f0781c90ee61958d7044665a22d38@164.152.161.249:26656,1a26dfdddd57a499841e45936f45c1d59c643b98@137.184.37.245:26656,3197daa0ee5245b17a546be032ff0f6814e1d1db@148.251.191.239:26656,2000928f1b09973431b53292ef80c1cd836fd967@168.119.213.117:26656,47e4075978458bfc382630b2a46aabbbbf7977b2@143.198.234.114:26656,0431022ccc3d354d92518df2d0ab30149a3d5fd7@202.182.116.179:26656,8e5051244ada217dc580feb774789ad7eb8b357c@34.27.219.200:26656,d2a4b47f8d2f4130943ef7a38c1c1c80ea4d06fd@199.247.29.239:26656,0813f61788331d5fdf66246b50cd417652194c27@23.106.120.19:26656,b69e57cd6f796ac5d6efb1a834163365c37cbfa8@78.46.69.29:26656,913e9db0332df1152e5afe032ab81bdb65e3f91c@110.11.23.44:26656,94e69330d6f4cfe221cdd2ce49ee141e53e5f200@23.106.120.6:26656,3e2687691d1e7c82b5880b55d2ea13e5d517b9fe@18.220.77.152:26656,71eab9bbf4edabb7b0f2d58e409edc7eb2a98a78@54.241.23.96:26656,d0c050f33b7aa1032a3763da0e7eb8df0ac72a2c@162.55.92.114:12000,971c324f0889de5fd528402487168d88857a3df6@66.172.36.141:36656,60a2c89e7253502e93517a026f44a2431cc81230@220.85.113.39:26656,2736d870197d443e463b4ff4b7b52f1cec920030@45.63.39.14:26656,34340a9151d4a97a850d2cd64d8778279faf3f96@194.163.181.100:26656
sed -i.bak -e "s/^persistent_peers *=.*/persistent_peers = \"$PEERS\"/" $HOME/.osmosisd/config/config.toml
```

## Launch Node
### Configure Cosmovisor Folder
Create Cosmovisor folders and load the node binary.

```
# Create Cosmovisor Folders
mkdir -p ~/.osmosisd/cosmovisor/genesis/bin
mkdir -p ~/.osmosisd/cosmovisor/upgrades

# Load Node Binary into Cosmovisor Folder
cp ~/go/bin/osmosisd ~/.osmosisd/cosmovisor/genesis/bin
```

### Create Service File
Create a `osmosisd.service` file in the `/etc/systemd/system` folder with the following code snippet. Make sure to replace `USER` with your Linux user name. You need `sudo` previlege to do this step.

```
[Unit]
Description="osmosisd node"
After=network-online.target

[Service]
User=USER
ExecStart=/home/USER/go/bin/cosmovisor start
Restart=always
RestartSec=3
LimitNOFILE=4096
Environment="DAEMON_NAME=osmosisd"
Environment="DAEMON_HOME=/home/USER/.osmosisd"
Environment="DAEMON_ALLOW_DOWNLOAD_BINARIES=false"
Environment="DAEMON_RESTART_AFTER_UPGRADE=true"
Environment="UNSAFE_SKIP_BACKUP=true"

[Install]
WantedBy=multi-user.target
```

### Start Node Service
```
# Enable service
sudo systemctl enable osmosisd.service

# Start service
sudo service osmosisd start

# Check logs
sudo journalctl -fu osmosisd
```

# Other Considerations
This installation guide is the bare minimum to get a node started. You should consider the following as you become a more experienced node operator.



> Configure firewall to close most ports while only leaving the p2p port (typically 26656) open

> Use custom ports for each node so you can run multiple nodes on the same server

> If you find a bug in this installation guide, please reach out to our [Discord Server](https://discord.gg/yV2nEunsTY) and let us know.