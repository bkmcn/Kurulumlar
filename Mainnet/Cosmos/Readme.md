<p align="center">
  <img height="100" height="auto" src="https://raw.githubusercontent.com/Nodeist/Kurulumlar/main/logos/cosmos.png">
</p>



# Cosmos Node Installation Guide
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
git clone https://github.com/cosmos/gaia cosmos
cd cosmos
git checkout v7.1.0
make install
```

## Configure Node
### Initialize Node
Please replace `MONIKERNAME` with your own moniker.

```
gaiad init MONIKERNAME --chain-id cosmoshub-4
```

### Download Genesis
The genesis file link below is Nodeist's mirror download. The best practice is to find the official genesis download link.

```
wget -O genesis.json https://snapshots.nodeist.net/cosmos/genesis.json --inet4-only
mv genesis.json ~/.gaia/config
```

### Configure Peers
Here is a script for you to update `persistent_peers` setting with these peers in `config.toml`.
```
PEERS=048a3d581dcdd343d57c35b27027686ecd5c7ad4@185.180.220.127:26656,a09ed43e09f773e39855dc5d8b6a220eff4cb947@204.16.241.207:26656,31681c089f19cbc8008e133c64e2b524aff0dd3f@46.4.107.112:14956,d17dffabf7ad521719e4175245d54ac2994a458d@138.201.127.91:26678,1d0eb9185523d5e8d09451557cb837d50112d8e2@51.195.63.75:11256,213857e741833d17275ea559bb2d0342398cec99@35.245.206.45:26656,d09c50da7b46624b8f1866bcf66fa11639bfb696@198.244.203.179:26656,dc3a1d1fbe0e477ebdb56fcee13ac6288fce2d87@65.108.141.62:26656,322efd4fdc72a189a2fc8b2b597927831df2bbed@128.0.51.9:26656,d2247f7b919f0781c90ee61958d7044665a22d38@164.152.161.86:26656,55debc20a243bbb6acc5db054559953bb87acb30@162.251.238.5:26656,d0238198ffa7f4db9a5d8c7b131c73f8382f8c47@65.108.141.109:30656,2e470eb2dfd65ffa34a9ae2d73646f82c6e594b7@65.108.10.36:26656,44594a57ce538a21f8558bcb1c9ce560ad879e3e@15.235.114.84:26656,a2bd6a63813bba08e2b8504f6eace00d088cff82@23.88.18.142:26656,137f98c8e22965e672744a3f8909c0f4c8cffc53@135.148.54.43:26656,57b3ec821a394c243a856b2c82cfb59b7830b0ac@65.108.98.218:19095,64148c47e1424173e3dcf90ab90bf196c2971b15@88.218.224.118:26656,1d7e4efb0acaac12f9d75fc7d5417398653c6863@31.7.207.16:33656,ab7370e0af17b3fb10c912e722ff05e6e6505fc4@52.76.189.151:26656,d35f08a60aeb2729d07e92e778b4c6f83379092e@18.138.160.68:26656,ea1779f3c46730e98727fbc0499ba45b31a40ce0@95.216.16.205:14956,b9b99fbf40189c604ea618c4b99c61abc1489b70@18.140.125.215:26656,b533749dfe0dc09eff1dfb2adf83108f9125ee1c@162.55.97.111:26656,0b27d23a50a6969a22b268ec90a198c31b741b2d@65.108.103.184:27656,c6f03336e99b15b104048a1af056063107389441@18.142.7.52:26656,2633bc088bcf96209b695734005952906b5c45e3@3.123.191.80:26656,4fb444050d0084c4aa81f9f55e10060063179dd9@151.80.26.241:26656,be6a3c78962d1dff8e79bfa6548ea40d837d8640@86.111.48.34:26656,2441e90fcb341fcd5bebec15b54e346cdca64a9b@135.148.123.8:14956,48b090282c851435f3a4d4a9af831ca716d25e97@136.243.174.45:16656,7dd34d8d3880bc48eff3e47b941d06bd1941a962@93.115.25.106:26656,dee3771d222681139d9df18d4e127d4f52820614@65.108.142.81:26656,2eb0e5e53401c51535c13250aba5fe98374ba7f0@51.210.32.145:26656,20f6da46a65ba8996604adeb12644c96ec78e85c@148.251.132.176:26656,989f4e22208c3a77bd8b550ce68d8ad23e5bdda7@3.129.15.134:26656,762175c3ae976cc93d28a151a8551c1a0018f32d@20.48.28.69:26656,47f8eb3d20e8a7388a7a8bfb38826d7e95f65552@185.252.220.88:25028,26ac129d380e7010473dfeda9c84bf25450c711f@163.114.159.145:26656,61afb0f37c02031f285f6b27ead2a3e7a97cc28a@35.212.34.104:26656,8707282f51ebfba828c08a7316ca84ed5667a0f5@74.118.142.175:26656,d82513849c2722a32e2e03617a516f65b3ca0216@176.191.97.120:33656,7b15dce221b13ca353187b4f7219a94db6b71ad3@185.119.118.109:2000,ca46c023eab241377285ae0222f5971d01b1a9fd@176.9.139.74:16656,3c99aba53d77d9b86efb9a7a74037761360086e6@18.139.147.9:26656,6b4a6e35c5329b07f23662c683e24b262dd10b5e@195.189.96.115:26656,538348fa1eac998dad392a3f00f7b957042c3e84@15.235.53.86:11156,0eae0c3b87453c625a1de230fca4993b8ebe5c00@65.21.94.45:26656,dc63e8b5120e49de9b39fee606edc3cedc8fbeae@35.208.116.244:26656,456848491f76ddefeb00ac462db0740d5639df24@135.181.113.227:26656,ae31f306e33a100e20b12f17cd91428120ed883c@54.81.193.10:26656,5aa66312a7ad2550c66165715c16f2b76e19c3a7@46.4.113.202:26656,f40a6e7d7168a3f2a5362cd37cbe6eac7a686056@185.229.119.178:26656,dd53fa5cfb6a604feb80860d47506d0dd84baa12@142.132.210.234:26656,b79e1d3a621bdafd3a8d9a49dff8f4737d0bedc9@52.73.168.104:26656,f9b0745b2e969422f2a208327d84266ff5d82e50@65.109.82.115:26656,c540af0c82963228aa865d27d9b6142fc54b571d@176.9.102.164:26656,6ea2ef7d3dd5d6967708a0b31eed85ba090a90a1@65.108.121.190:12010,dff07399aeadf3f1b6edfac07f92a238112d3036@93.189.30.120:26656,298b87256adc41a8cf7ac3c755c23020ac96ac7f@34.145.9.235:26656,3da88430414ec9084c8983fe4d462cce655ff1f3@51.222.245.114:26656,344d87e04fdf04be760da5069a59d9a489b886a6@52.14.44.1:26656,4ddba29a7dfa740a4edeb5c620c963f67f951e1d@5.9.72.212:2000,76c65af180735315774497698ccf2091fb81284e@34.141.50.37:26656,72829b78b38408b03793ed389b9f16596b82c306@146.59.81.92:26656,581bd4859a0a6bf2fa7ea4850d45fec4e92c6173@91.194.30.202:31656,97e8ca8e1c91168eb70beb56b29fb135d5e19d65@131.153.242.199:26656,3a94f1021e84bb54a640e5b1c1fe16827824e4f7@51.79.20.217:26656,df1b21a6a92c6045946b2263ada344628ee9a8b6@74.118.143.189:26656,0e71a3cbdddfe77ebff79378bf6ac07915e747dc@167.235.152.95:27002,2286eeee09fcf37e768dfffc0db8c821b9231b7b@204.16.244.78:26656,a7d96dc929824613315dcc1c90fee119f28cc51f@134.65.193.5:26656,8698cb819c9a4503fe2c71055f1380d08edc5adf@204.16.244.116:26656,573692f610c093ac1fc42df916103f54f9ba56ea@65.21.132.27:21986,4ebf074e8b4a24438bd0bd503b62b4728dfb8eae@35.212.101.35:26656,eebc7a0257c91306b38fb42924b9292d6dd2951c@51.79.176.202:26656,61bb33c7869e1d5014c996299a818d816ae961a6@52.77.137.184:26656,60afd908298c1ff249bb8e60e469594c5422473d@136.243.91.221:26656,b7ea5e11d7a6b30fbb2dbe8c9d415170bfb4611c@209.182.239.210:26656,e4ddf5c29adca9505a51d19c653e4e472f06d119@18.232.149.102:26656,f8ae898b130457bbbf05fd3d2e9ca4559bd528fd@37.120.245.157:26656,17a36a938b247e887a5b0d5f07a6c7df78d1c89c@54.37.81.39:26656,1cce99042f884d669e7287e3e362bff8e385c63e@46.4.79.183:26726,0f0fe80e8fffbdad69b6f01b43669dd2e5a7c84b@51.77.134.111:26656,89757803f40da51678451735445ad40d5b15e059@169.155.168.135:26656,32bdba6ced12cdf2e534566e6c3d66ee2f7ef494@84.244.95.229:26656,3c08dde641866bf332e1a9f94261a39d57247328@65.108.230.27:26656,e829d4764a5cecc44b3414777853b34407b36601@185.16.39.179:26656,c7a1d95db766b57bbea36ad1db1fc3cb41857fc8@86.111.48.38:26656,c1e437f73b8889b78ea34981e7c349157ad80284@107.135.15.66:26656,6f473f7156b9e0a460f5ab9d5b8bba2412058974@93.159.134.156:36656,51c49b57b371e3645de715e0034236a8bd61965e@35.234.21.2:26656,daa6d8314246ad65037a48ec2e2266eeea9d46f8@154.53.63.50:26656,7dbd25c2e2bf602d6ed14b9a2648bdcd58f3e79d@65.108.77.106:26649,c14d39422b5d70d9084d19d286c7427c0762cdfc@162.55.92.114:2010,43be5650f15129bc5971e6c68f111255702fbdc6@18.236.101.119:26656,b858ca4f3fed2c36b949cf67188b126e2542a39a@135.181.215.115:26726,cf10a45ead9e76d45b06dee97ef779e65103c78e@3.128.185.235:26656,5d45bc48f6c0199c047e685fafb4309f53593f37@5.161.119.242:49656
sed -i.bak -e "s/^persistent_peers *=.*/persistent_peers = \"$PEERS\"/" $HOME/.gaia/config/config.toml
```

## Launch Node
### Configure Cosmovisor Folder
Create Cosmovisor folders and load the node binary.

```
# Create Cosmovisor Folders
mkdir -p ~/.gaia/cosmovisor/genesis/bin
mkdir -p ~/.gaia/cosmovisor/upgrades

# Load Node Binary into Cosmovisor Folder
cp ~/go/bin/gaiad ~/.gaia/cosmovisor/genesis/bin
```

### Create Service File
Create a `gaiad.service` file in the `/etc/systemd/system` folder with the following code snippet. Make sure to replace `USER` with your Linux user name. You need `sudo` previlege to do this step.

```
[Unit]
Description="gaiad node"
After=network-online.target

[Service]
User=USER
ExecStart=/home/USER/go/bin/cosmovisor start
Restart=always
RestartSec=3
LimitNOFILE=4096
Environment="DAEMON_NAME=gaiad"
Environment="DAEMON_HOME=/home/USER/.gaia"
Environment="DAEMON_ALLOW_DOWNLOAD_BINARIES=false"
Environment="DAEMON_RESTART_AFTER_UPGRADE=true"
Environment="UNSAFE_SKIP_BACKUP=true"

[Install]
WantedBy=multi-user.target
```

### Start Node Service
```
# Enable service
sudo systemctl enable gaiad.service

# Start service
sudo service gaiad start

# Check logs
sudo journalctl -fu gaiad
```

# Other Considerations
This installation guide is the bare minimum to get a node started. You should consider the following as you become a more experienced node operator.



> Configure firewall to close most ports while only leaving the p2p port (typically 26656) open

> Use custom ports for each node so you can run multiple nodes on the same server

> If you find a bug in this installation guide, please reach out to our [Discord Server](https://discord.gg/yV2nEunsTY) and let us know.