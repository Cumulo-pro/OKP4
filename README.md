<h2>Basic tools for a validator node in OKP4</h2>
<h3>OKP4, the Open Protocol for Knowledge</h3>
<img src='https://user-images.githubusercontent.com/2853158/208320040-6e086387-d3e5-47d6-b52f-1446b7af0641.png'>

<h3>📌 Overview</h3>
OKP4 is a domain-specific, layer 1 blockchain dedicated to the exchange of data with minimal trust. Digital Territory for the Data Economy and the Next Generation of Data Applications

OKP4 is PoS and is based on Tendermint. Its validators participate in the consensus protocol by casting votes containing cryptographic signatures signed by each validator’s private key.

The KNOW is the native token of OKP4.

Chain ID: okp4-nemeton-1 | Latest version Tag: v3.0.0

<h3>🌐 Useful links</h3>
Website: https://okp4.network

GitHub: https://github.com/okp4/okp4d

OKP4 whitepaper and documentation: https://docs.okp4.network

Frequently Asked Questions: https://nemeton.okp4.network/faq#faq

Cumulo Spanish Resources: http://cumulo.pro/okp4.html

<h4>Social media:</h4>
● Twitter: https://twitter.com/OKP4_Protocol

● Telegram: https://t.me/okp4network

● Discord: https://discord.com/invite/okp4

● Medium: https://blog.okp4.network/

● LinkedIn: https://www.linkedin.com/company/okp4-open-knowledge-protocol-for/

● Youtube: https://www.youtube.com/@okp4351

<h4>Explorers:</h4>
● https://explore.okp4.network/

● https://okp4.explorers.guru/

<h3>⚙️Hardware requirements</h3>
● Memory: 8 GB RAM

● CPU: 2 core

● Disk: 200 GB of storage

<h3>🛠 Manual installation</h3>

<h4>Updating packages and installing dependencies</h4>
<pre>sudo apt update && sudo apt upgrade -y
sudo apt install curl git wget htop tmux build-essential jq make gcc -y</pre>

<h4>Environment variables</h4>
To set environment variables replace your wallet and moniker < YOUR_WALLET_NAME> < YOUR_MONIKER> without <> , and save and import the variables into the system.

<pre>echo "export OKP4_WALLET="<YOUR_WALLET_NAME>"" >> $HOME/.bash_profile
echo "export OKP4_MONIKER="<YOUR_MONIKER>"" >> $HOME/.bash_profile
echo "export OKP4_CHAIN_ID="okp4-nemeton-1"" >> $HOME/.bash_profile
source $HOME/.bash_profile</pre>

<h4>Install go</h4>
<pre>cd $HOME
VER="1.19.1"
wget "https://golang.org/dl/go$VER.linux-amd64.tar.gz"
sudo tar -C /usr/local -xzf "go$VER.linux-amd64.tar.gz"
rm -rf  "go$VER.linux-amd64.tar.gz"
echo "export PATH=$PATH:/usr/local/go/bin:$HOME/go/bin" >> $HOME/.bash_profile
source $HOME/.bash_profile
go version</pre>

<h4>Download and compile binaries</h4>
<pre>cd || return
rm -rf okp4d
git clone https://github.com/okp4/okp4d.git
cd okp4d || return
git checkout v3.0.0
make install
okp4d version # 3.0.0</pre>

<h4>Configure and start the application</h4>
<pre>okp4d config chain-id okp4-nemeton-1
okp4d init $OKP4_MONIKER --chain-id $OKP4_CHAIN_ID</pre>

<h4>Download genesis</h4>
<pre>curl https://raw.githubusercontent.com/okp4/networks/main/chains/nemeton-1/genesis.json > $HOME/.okp4d/config/genesis.json
sha256sum $HOME/.okp4d/config/genesis.json #2ec25f81cc2abecbc0da3de45b052ea3314d0d658b1b7f4c7b6a48d09254c742</pre>

<h4>Set seeds and peers</h4>
Seeds

<pre>sed -i -e "s|^seeds *=.*|seeds = \"3f472746f46493309650e5a033076689996c8881@okp4-testnet.rpc.kjnodes.com:36659\"|" $HOME/.okp4d/config/config.toml
</pre>
Peers
<pre>PEERS=9c462b1c0ba63115bd70c3bd4f2935fcb93721d0@65.21.170.3:42656,a4a96019d2fbc1b5df07940cd971585311166acd@65.108.206.118:61356,ee4c5d9a8ac7401f996ef9c4d79b8abda9505400@144.76.97.251:12656,2e85c1d08cfca6982c74ef2b67251aa459dd9b2f@65.109.85.170:43656,264256d32511c512a0a9d4098310a057c9999fd1@okp4.sergo.dev:12233,4ea26ce893d8f4f89a7b49b9bd77e0fbd914e029@65.109.88.162:36656,8d8fdad759361a57121903632adbd66ad072b1ab@okp4-testnet.nodejumper.io:29656,e3c602b146121c88d350bd7e0f6ce8977e1aacff@161.97.122.216:26656,3c805c2dead7b7a3a1d3ba2399d4d62153322413@65.108.2.41:36656,9d1482bc31fb4578a5c7f7f65c4e0aaf2dfc2336@213.239.215.77:34656,a7f1dcf7441761b0e0e1f8c6fdc79d3904c22c01@[2a02:c206:2093:4875::1]:36656,a7f1dcf7441761b0e0e1f8c6fdc79d3904c22c01@38.242.150.63:36656,99f6675049e22a0216af0e2447e7a4c5021874cd@142.132.132.200:28656,9392c27a9a561c31e7a920dc6f577d663c473ef8@154.12.225.88:26656,9928d19b7663a6fa639eb7c1ee239e671edcbdb2@5.9.147.22:26616,b5484e85a8802e0489234904d2b3a2d3c0c16e71@135.181.116.246:26106,f575a4c927d28990c84004d9af555f9956b1f22f@195.201.194.249:26656,b0b56d944cf1cc569a1e77e0923e075bad94d755@141.95.145.41:28656,667b419765454ad6970cc739e75d1ddf2b8a3f47@62.171.184.126:26656,eef77b5ae1c37f3e5809ff928c329dde906be388@65.108.133.73:21656,0f0c071ffc1948767fa866501a4d7d3144b8bf0b@142.132.208.26:26157,3ecbc8aa00b5dd8af88af7496489b0054e3b4d7f@138.68.182.247:26656,c030413e39be95c397c6681639f5d48675554c0c@51.79.78.121:26646,15fdc722cd49ef7676205b6ad3120a84728d948c@65.108.225.158:17656,61544968b65e34a59513b67613519cd37ace7ecb@161.97.151.109:26656,977373e6ff096d43c928e14724b8c6d9d7f48cb7@5.9.147.185:51656,9e5fe90a7b35285b14d27d409184026c92f43bc8@95.111.225.137:37656,1655cdc8fdfe1dc2209d47ff68c02a417ef9ed52@135.181.222.179:31656,8cdeb85dada114c959c36bb59ce258c65ae3a09c@88.198.242.163:36656,02b982c1907e461bf74d84d87c1657f12d9438b0@167.235.15.19:31656,a49302f8999e5a953ebae431c4dde93479e17155@141.95.153.244:26656,751d8d4bc73443aef9f95ddfac3572ddfc34e035@5.75.226.80:26656,f045c5324e03d54f96285a33130d3886457e18be@46.4.81.204:49656,01e492870d6c3027e9677713049e2a4de9e78e76@38.242.231.150:26656,c6e8fcf0e7545a0773cebb6445ff8e5cd3125f10@213.136.84.176:26657,da8e2423cb90fba519e685aa47669eb861ea18c4@65.108.249.79:36656,05454303ced866f3c849e4e35be4f48d96a3ece2@91.211.251.232:28656,61a8b9fdd5c21ebe6c02359cb192a4eda13d44cb@135.181.139.153:26656,bc648d1d8aef7f622d38f47ab8a0ecaee9791c46@54.36.109.62:26656,94345c725cd6e61dca339c743d800f6f497b08be@95.216.145.19:36658,0448864ede56d3c96d7d3bb8ea9f546b70cc722e@51.159.149.68:26656,08c925f04cb7a324b1aa91b472faa99c7cccc6ab@65.108.56.126:36656,339460a562c9a52b6be22da3211f19edb11faa2b@194.163.162.56:28656,84da5ad673d086c5c0b4a8da8b8b1c1c29e1d81e@142.132.130.196:36656,d1a424812c4447ca05611ff271ea5b486e27955d@173.249.8.187:36656,30092d2717053f1c0813e8354c07c761c9c3ac5c@194.163.161.234:26656,2f9e54645aca860f703e3f756fa7c472b829a9a9@tenderseed.ccvalidators.com:26009,869bad4136d773f9ae83909257fd6c422b5cbe7a@142.132.151.169:26656</pre>
<pre>sed -i.bak -e "s/^persistent_peers *=.*/persistent_peers = \"$PEERS\"/" $HOME/.okp4d/config/config.toml</pre>

<h4>Configure pruning</h4>
<pre>sed -i 's|pruning = "default"|pruning = "custom"|g' $HOME/.okp4d/config/app.toml
sed -i 's|pruning-keep-recent = "0"|pruning-keep-recent = "100"|g' $HOME/.okp4d/config/app.toml
sed -i 's|pruning-interval = "0"|pruning-interval = "17"|g' $HOME/.okp4d/config/app.toml
#Set the minimum gas price
sed -i 's|^minimum-gas-prices *=.*|minimum-gas-prices = "0.0001uknow"|g' $HOME/.okp4d/config/app.toml</pre>

<h4>Activate prometheus<h4>
<pre>sed -i -e "s/prometheus = false/prometheus = true/" $HOME/.okp4d/config/config.toml</pre>

<h4>Clean up old data<h4>
<pre>okp4d tendermint unsafe-reset-all --home $HOME/.okp4d --keep-addr-book</pre>
 
 
<h3>♻️ Fast synchronisation with snapshot (Optional)</h3>
<p>You can sync your OKP4 node quickly by downloading a recent snapshot from kjnodes (https://services.kjnodes.com/home/testnet/okp4/snapshot), Kolot (https://github.com/Kolot86/Snapshots-StateSync/blob/main/OKP4/Snapshot.md), …</p>

<pre>sudo systemctl stop okp4d
cp $HOME/.okp4d/data/priv_validator_state.json $HOME/.okp4d/priv_validator_state.json.backup
rm -rf $HOME/.okp4d/data
cd $HOME
rm -rf $HOME/.okp4d/data
curl -L https://snapshots.kjnodes.com/okp4-testnet/snapshot_latest.tar.lz4 | lz4 -dc - | tar -xf - -C $HOME/.okp4d
mv $HOME/.okp4d/priv_validator_state.json.backup $HOME/.okp4d/data/priv_validator_state.json</pre>

<h3>🛎 Service with SystemD</h3>
Create the service file
<pre>sudo tee /etc/systemd/system/okp4d.service > /dev/null << EOF
[Unit]
Description=OKP4 Node
After=network-online.target
[Service]
User=$USER
ExecStart=$(which okp4d) start
Restart=on-failure
RestartSec=10
LimitNOFILE=10000
[Install]
WantedBy=multi-user.target
EOF</pre>

<h4>Enable, start service and check logs</h4>
<pre>sudo systemctl daemon-reload
sudo systemctl enable okp4d
sudo systemctl restart okp4d
sudo journalctl -u okp4d -f --no-hostname -o cat</pre>

<h3>🗝Wallet</h3>

<h4>Create wallet</h4>
<p>Don’t forget to save the mnemonic.</p>

<pre>okp4d keys add $OKP4_WALLET</pre>

<h4>Restore wallet</h4>
<pre>okp4d keys add $OKP4_WALLET --recover</pre>

<h4>Deposit funds into your wallet</h4>
<p>Before creating a validator, you have to deposit funds in your wallet, go to the OKP4 discord server and request them in the faucet channel.</p>

<pre>/reques  <<-YOUR_WALLET_ADDRESS->></pre>

<h3>📝Validator</h3>

<h4>Save the wallet and validator address</h4>
<pre>OKP4_WALLET_ADDRESS=$(okp4d keys show $OKP4_WALLET -a)
OKP4_VALOPER_ADDRESS=$(okp4d keys show $OKP4_WALLET --bech val -a)
echo "export OKP4_WALLET_ADDRESS="${OKP4_WALLET_ADDRESS} >> $HOME/.bash_profile
echo "export OKP4_VALOPER_ADDRESS="${OKP4_VALOPER_ADDRESS} >> $HOME/.bash_profile
source $HOME/.bash_profile</pre>

<h4>Create validator</h4>
<p>Before creating a validator, you should make sure that the node is synchronised and check the balance of your wallet.</p>

<h5>Check synchronisation status</h5>
<p>Once your node is fully synchronised, the output will read false.</p>

<pre>okp4d status 2>&1 | jq .SyncInfo</pre>

<h5>Check your balance</h5>
<pre>okp4d q bank balances $(okp4d keys show wallet -a)</pre>

<h5>Create validator</h5>
<pre>okp4d tx staking create-validator \
--amount=1000000uknow \
--pubkey=$(okp4d tendermint show-validator) \
--moniker=$OKP4_MONIKER \
--chain-id=$OKP4_CHAIN_ID \
--commission-rate=0.05 \
--commission-max-rate=0.20 \
--commission-max-change-rate=0.01 \
--min-self-delegation=1 \
--from=wallet \
--gas-adjustment=1.4 \
--gas=auto \
-y</pre>

<p>You can add the flags — website — security-contact — identity — details (optional)</p>

<pre>--website <WEB_SITE_URL> \
--security-contact <YOUR_CONTACT> \
--identity <KEYBASE_IDENTITY> \
--details <YOUR_VALIDATOR_DETAILS></pre>

<h3>🎛 Monitoring</h3>
<p>If you want to set up a monitoring and alerting system use our guide to monitoring Cosmos nodes with tenderduty.</p>

<h3>🛎 SystemD commands</h3>
<h4>Stop the service</h4>
<pre>sudo systemctl stop okp4d</pre>
<h4>Start service</h4>
<pre>sudo systemctl start okp4d</pre>
<h4>Restart service</h4>
<pre>sudo systemctl restart okp4d</pre>
<h4>Check logs</h4>
<pre>sudo journalctl -u okp4d -f --no-hostname -o cat</pre>
<h4>Check status</h4>
<pre>sudo systemctl status okp4d</pre>

<h3>📈 Node information</h3>
<h4>Synchronization information</h4>
<pre>okp4d status 2>&1 | jq .SyncInfo</pre>
<h4>Node information</h4>
<pre>okp4d status 2>&1 | jq .NodeInfo</pre>
<h4>Validator information</h4>
<pre>okp4d status 2>&1 | jq .ValidatorInfo</pre>
<h4>Get peers</h4>
<pre>echo $(okp4d tendermint show-node-id)'@'$(curl -s ifconfig.me)':'$(cat $HOME/.okp4d /config/config.toml | sed -n '/Address to listen for incoming connection/{n;p;}' | sed 's/.*://; s/".*//')</pre>

<h3>🔏 Wallet operation</h3>
<h4>Check balance</h4>
<pre>okp4d query bank balances $OKP4_WALLET_ADDRESS</pre>
<h4>Wallet Key List</h4>
<pre>okp4d keys list</pre>
<h4>Create a new wallet</h4>
<pre>okp4d keys add $OKP4_WALLET</pre>
<h4>Wallet recovering</h4>
<pre>okp4d keys add $OKP4_WALLET --recover</pre>
<h4>Delete wallet</h4>
<pre>okp4d keys delete $OKP4_WALLET</pre>
<h4>Transfer funds</h4>
<pre>okp4d tx bank send $OKP4_WALLET_ADDRESS <TO_OKP4_WALLET_ADDRESS> 800000000uknow --gas auto --gas-adjustment 1.3</pre>

<h3>💬 Governance</h3>
<h4>List all proposals</h4>
<pre>okp4d query gov proposal 1</pre>
<h4>Vote YES</h4>
<pre>okp4d tx gov vote 1 yes --from $OKP4_WALLET --chain-id $OKP4_CHAIN_ID --gas-adjustment 1.4 --gas auto -y</pre>
<h4>Vote NO</h4>
<pre>okp4d tx gov vote 1 no --from $OKP4_WALLET --chain-id $OKP4_CHAIN_ID --gas-adjustment 1.4 --gas auto -y</pre>
<h4>Refrain</h4>
<pre>okp4d tx gov vote 1 abstain --from $OKP4_WALLET --chain-id $OKP4_CHAIN_ID --gas-adjustment 1.4 --gas auto -y</pre>

<h3>🚰 Staking, delegation and rewards</h3>
<h4>Withdraw all rewards</h4>
<pre>okp4d tx distribution withdraw-all-rewards --from $OKP4_WALLET --chain-id $OKP4_CHAIN_ID --gas auto --gas-adjustment 1.3</pre>
<h4>Withdraw commission</h4>
<pre>okp4d tx distribution withdraw-rewards $OKP4_VALOPER_ADDRESS --from $OKP4_WALLET --commission --fees 20uknow</pre>
<h4>Delegate Stake</h4>
<pre>okp4d tx staking delegate $OKP4_VALOPER_ADDRESS 10000000uknow --from $OKP4_WALLET --chain-id $OKP4_CHAIN_ID --gas=auto --gas-adjustment 1.3</pre>

<h3>✔️ Validator operation</h3>
<h4>Edit validator</h4>
<pre>okp4d tx staking edit-validator \
  --moniker=$NODENAME \
  --identity=<keybase_id> \
  --website="<website>" \
  --details="<validator_description>" \
  --chain-id=$OKP4_CHAIN_ID \
  --from=$OKP4_WALLET</pre>
  
<h3>Validator information</h3>
<pre>okp4d status 2>&1 | jq .ValidatorInfo</pre>
<h4>Jailing information</h4>
<pre>okp4d q slashing signing-info $(okp4d tendermint show-validator)</pre>
<h4>Validator unjailing</h4>
<pre>okp4d tx slashing unjail --broadcast-mode=block --from $OKP4_WALLET --chain-id $OKP4_CHAIN_ID --gas auto --gas-adjustment 1.5</pre>

<h3>🗑 Delete node</h3>
<pre>sudo systemctl stop okp4d
sudo systemctl disable okp4d
sudo rm -rf /etc/systemd/system/okp4d*
sudo systemctl daemon-reload
sudo rm $(which okp4d)
sudo rm -rf $HOME/.okp4d
sudo rm -fr $HOME/ okp4d
sed -i "/OKP4_/d" $HOME/.bash_profile</pre>

<h3>Authors: Sami & Mon</h3>
http://cumulo.pro/










