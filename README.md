# 777 Masternode Install Script

# Part 1 - Sending Collateral Coins

1. Open your Windows wallet - MAKE SURE IT IS SYNCED WITH THE NETWORK
2. Go to Tools -> Debug Console
3. Type: getaccountaddress MN# (# is your masternode number you want to use)
4. Send 10,000 777 to this address
5. Go to Tools -> Debug Console
6. Type: masternode outputs (This can take a minute before an output is shown)
7. Type: masternode genkey
7. Save your TX ID (The first number) and your Index Number (Second number, either a 1 or 0)
8. Save your generated key as well as this will be needed in your VPS as your private key
9. Save these with a notepad
10. Close the wallet
11. Move to Part 2 for now

# Part 2 - Getting your Linux VPS Started Up (Read all instructions and follow prompts closely)

1. Connect to your linux vps copy and paste the following to get started:
```
cd && sudo apt-get -y install git && sudo git clone https://github.com/Jackpot-777/777-Masternode-Setup.git && cd 777-Masternode-Setup/ && sudo bash 777-mn.sh
```

# Part 3 - Editing your Windows Config File

1. Open your wallet
2. Go to Tools -> Open Masternode Configuration File
3. Enter the following on one single line after the example configuration
```<alias> <ip>:17771 <private_key> <tx_id> <index>```
4. It should look something like this:
``` mn1 127.0.0.1:17771 93HaYBVUCYjEMeeH1Y4sBGLALQZE1Yc1K64xiqgX37tGBDQL8Xg 2bcd3c84c84f87eaa86e4e56834c92927a07f9e18718810b92e0d0324456a67c 0```
5. Save and close the file and restart your wallet.

# Part 4 - Starting the Masternode

1. In your wallet, go to Tools -> Debug Console
2. Wait for your transaction to your masternode address to have 16 confirmations.
3. Enter ```startmasternode alias 0 <alias>``` with ```<alias>``` being the name of your masternode from Part 3
4. Enjoy!  You can start this process over again for another MN on a fresh Linux VPS!
