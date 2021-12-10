---
layout: post
title:  "Securing Your Bitflate Coins"
date:   2020-11-09 10:00:00 -0700
categories: post
author: doph
---

Bitflate is a fork of Bitcoin. We can reuse software components from Bitcoin. The infrastructure for Bitflate is still limited. As of today, we can do the following:

* Use the Bitflate Core Client.

* Mine Bitflate (BFL) coins on mining-dutch or cminor pools. Pools come with online wallets. Check pools' documentation for wallet use.

* Buy and sell BFL coins on Unnamed Exchange. This exchanges comes with online wallets. Check its documentation for wallet use.

In this article, I describe a method for securing your own Bitflate coins (BFL). I use the Bitflate Core Client. With the client, you can store your coins locally on your computer. You can backup your coins into USB devices. This method is still based on software. As of today, Bitflate is experimental. There are security risks. A good security practice: Use a dedicated computer. You can avoid bugs and potential malware in the client to interfere with your computer. You can also avoid other software to interfere with the Bitflate Core Client.

### Take Ownership of Your Coins

* Download a Bitflate Core Client from github. You can download the latest release from GitHub. Pick the release for your OS.
[https://github.com/bitflate/bitflate/releases](https://github.com/bitflate/bitflate/releases)

* Unzip or install the client on your machine.

* Start your Bitflate Core Client daemon. For example, on Linux, use the following command:

```
./bin/bitflated
```

After v0.19, the client default fallbackfee is 0. If you need to send Bitflate coins, you may need to add -fallbackfee=0.0002 to the command. With this parameter, the command is:

```
./bin/bitflated -fallbackfee=0.0002
```

* Wait for your client to sync the blockchain. This process can take a while. You can compare your block number with the number on the Bitflate Block Explorer.

https://explorer.bitflate.org/

At this stage, the daemon downloads the Bitflate blockchain and stores it on your computer. You can also start the Bitflate Core UI. It also syncs the blockchain. You can use the -fallbackfee parameter with the UI command.

```
./bin/bitflate-qt
```

* Once your client is fully synced, you can start receiving your coins. Click on the Receive tab and create a receive order. This will generate a receiving address.

* On another wallet, e.g. pool or exchange, send or withdraw your coins to the receiving wallet.

For better privacy, you can generate multiple receiving addresses. A wallet can hold many addresses.

### Encrypt, Backup, and Recover Your Wallet

I highly recommend encrypting and creating backups of your wallet.

* To encrypt your wallet, click on Settings menu and Encrypt Wallet. Select a passphrase for encryption. Make sure you know the passphrase to open your encrypted wallet.

* To backup your wallet, click on File -> Backup Wallet. This will create a wallet.dat file. You can save it to USB drives.

You can open the wallet file on other computers using the encrypted passphrase.

* Copy the file on a new machine.

* Repeat the client sync process.

* Once synced, click on File -> Open Wallet.

* Enter your passphrase, your wallet should be opened.