# REECCOIN
Shell script to install a [Reeccoin Masternode](http://reec.io) on a Linux server running Ubuntu 18.04 / 20.04. Use it on your own risk.
***

## Installation
```
In case of ubuntu18.0.4 :

wget https://raw.githubusercontent.com/reeccoin/MasternodeSetupGuide/main/install-MN-18.0.4.sh
bash install-MN-18.0.4.sh

***********************************

In case of ubuntu20.0.4 :

wget https://raw.githubusercontent.com/reeccoin/MasternodeSetupGuide/main/install-MN-20.0.4.sh
bash install-MN-20.0.4.sh
```
***

## Desktop wallet setup  

After the MN is up and running, you need to configure the desktop wallet accordingly. Here are the steps:  
1. Open the Reeccoin Desktop Wallet.  
2. Go to RECEIVE and create a New Address: **MN1**  
3. Send **1000000** REEC to **MN1**. You need to send all 1000000 coins in one single transaction.
4. Wait for 15 confirmations.  
5. Go to **Help -> "Debug Window - Console"**  
6. Type the following command: **getmasternodeoutputs**
7. Open Masternode Configuration File **C:/Users/[username]/AppData/Roaming/REECCOIN/masternode.conf**
8. Add the following entry:
```
Alias Address Privkey TxHash Output_index
```
* Alias: **MN1**
* Address: **VPS_IP:PORT**
* Privkey: **Masternode Private Key**
* TxHash: **First value from Step 6**
* Output index:  **Second value from Step 6**
9. Save and close the file.
10. Go to **Masternode Tab**.
11. Select your MN and click **Start** to start it.
12. Alternatively, open **Debug Console** and type:
```
startmasternode alias false "MN1"
```
13. Login to your VPS and check your masternode status by running the following command:.
```
reeccoin-cli getmasternodestatus
```
***

## Usage:
```
reeccoin-cli mnsync status
reeccoin-cli getmasternodestatus  
reeccoin-cli getinfo
```

***
