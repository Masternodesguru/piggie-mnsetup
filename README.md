# MasternodeSetup

### Required:

1. PIGGIE for Collateral <br>
(You can buy PIGGIE from exchange for collateral) <br>

GRAVIEX: https://graviex.net/markets/piggiebtc

2. Download your Local Wallet: https://github.com/Masternodesguru/piggie/releases/download/1001/piggie-1001-linux.zip

3. You will need also VPS with Ubuntu  18.04


**VPS WALLET:**

1. After you longin on your VPS , with this command you will download masternode-installer.   
 
- dl the install script 
`wget https://raw.githubusercontent.com/masternodesguru/piggie-mnsetup/master/masternode-install.sh` 

2. With this command you will need to change permission 

- change permission: <br>
`sudo chmod +x masternode-install.sh` <br>

3. Now install your masternode.  

- Use this to install masternode: <br>
`./masternode-install.sh`



**LOCAL WALLET:**

Send the collateral
Open your wallet and wait until your wallet has downloaded the blockchain.

Go to “Tools”.
Click “Debug console”.
This is the console where you will execute all commands.

Create a new masternode private key.

```
createmasternodekey
```

Example output

7fohQVEc9sb5FVt2wQcyacVahrMkB36cP3p4rXYwva1nogFpFwJ

Show your collateral address.
```
getaccountaddress "MN1"
```

Example output

PSSRoLjKTQjJwPLNtDFWgzeGyfN3n5W3vM
```
Transfer the required amount of coins to the “collateral address” that you created using the command “getaccountaddress "MN1"”.
```
Wait until the transaction has the required masternode confirmations.

Go to “Tools”.
Click “Debug console”.
Enter the following command.
```
getmasternodeoutputs
```
```
Example output


[
  {
    "txhash": "506a242ccbfd2555bcd9cff5f4041752c911f39cb2905acc83ccfe0cf8808df9",
    "outputidx": 1
  }
]
```

Modify the following line in your masternode.conf file and paste it into:
```
MN1 VPSIP:22190 7VatfYVk5fFMTymPDhgSURAESDACJhWpd89WHGoh35d9fbLQPj5 506a242ccbfd2555bcd9cff5f4041752c911f39cb2905acc83ccfe0cf8808df9 1
```
MN1 - Alias for your masternode.

VPSIP- External IP address of your VPS.

22190 - The port for PIGGIE

7VatfYVk5fFMTymPDhgSURAESDACJhWpd89WHGoh35d9fbLQPj5 - Masternode private key from the command “createmasternodekey”.

506a242ccbfd2555bcd9cff5f4041752c911f39cb2905acc83ccfe0cf8808df9 - Value “txhash” from the command “getmasternodeoutputs”.

1 - Value “outputidx” from the command “getmasternodeoutputs”.


Save the file and close.

Close your wallet.

Restart your wallet! 
On Masternode tab in your wallet - Start the masternode! 
