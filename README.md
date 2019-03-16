# WorxInstaller

This script allows for easy setup of linux masternode or CLI wallet. 

Just run with (pick the version for your Ubuntu, 16.04 or 18.04):
```bash
bash <(curl https://raw.githubusercontent.com/WG91/WorxInstaller/master/worx_installer_U16)
bash <(curl https://raw.githubusercontent.com/WG91/WorxInstaller/master/worx_installer_U18)
```
as root on your linux VPS, or computer if you just want CLI wallet. 

# Worx
Shell script to install a [Worx Masternode](https://worx.world/) on a Linux server running Ubuntu 16.04. 
***

## Installation
```
bash <(curl https://raw.githubusercontent.com/WG91/WorxInstaller/master/worx_installer_U16)
bash <(curl https://raw.githubusercontent.com/WG91/WorxInstaller/master/worx_installer_U18)
```
***

## Desktop wallet setup  

After the MN is up and running, you need to configure the desktop wallet accordingly. Here are the steps:  
1. Open the Worx Desktop Wallet.  
2. Go to RECEIVE and create a New Address: **MN1**  
3. Send **5000** WORX to **MN1**. You need to send all 5000 coins in one single transaction.
4. Wait for 15 confirmations.  
5. Go to **Help -> "Debug Window - Console"**  
6. Type the following command: **masternode outputs**  
7. Open Windows Explorer and go to **%APPDATA%\Worx** folder
8. Open/create masternode.conf
9. Add the following entry:
```
Alias Address Privkey TxHash TxIndex
```
* Alias: **MN1**
* Address: **VPS_IP:PORT**
* Privkey: **Masternode Private Key**
* TxHash: **First value from Step 6**
* TxIndex:  **Second value from Step 6**
10. Save and close the file.
11. Open **Debug Console** and type:
```
masternode start-alias MN1
```
12. Login to your VPS and check your masternode status by running the following command. If you get **Status 9**, it means your masternode is active.
```
worx-cli masternode status
```
***

## Usage:
```
worx-cli mnsync status
worx-cli masternode status  
worx-cli getinfo
```
Also, if you want to check/start/stop **Worx**, run one of the following commands as **root**:

```
systemctl status Worx #To check if Worx2 service is running
systemctl start Worx #To start Worx2 service
systemctl stop Worx #To stop Worx2 service
systemctl is-enabled Worx #To check if Worx2 service is enabled on boot
```  
***

