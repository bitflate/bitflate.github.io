---
layout: post
title:  "Bitflate Lightning Network with c-lightning"
date:   2019-09-07 12:59:00 -0700
categories: post
author: doph
---

Bitflate is a Bitcoin fork with constant inflation. Since it is updated frequently with Bitcoin Core code base, it has Lightning Network support. Bitflate mainnet activated SegWit at 28k block. In this article, we describe how to use c-lightning on Bitflate testnet. You can use it on mainnet.

*Note: Lightning Network is an experimental protocol. c-lightning is experimental software. Please use it with caution. Always run on testnet first. Contact us if you have problem.*

To run Lightning Network transactions, you will need at least 2 machines (send and receive). You first need to build or download Bitflate Core and c-lightning software on both machines.

[Bitflate Binaries](https://github.com/bitflate/bitflate/releases)

[c-lightning Build Instruction](https://github.com/ElementsProject/lightning/blob/master/doc/INSTALL.md)

[c-lightning Binaries](https://github.com/ElementsProject/lightning/releases)

### Send Machine

On send machine, start bitflated and lightningd.

```
# You may also need -maxtipage=864000000 option to avoid stale tip on testnet
./bin/bitflated -testnet -rpcuser=sender -rpcpassword=sender

# Start c-lightning daemon
./lightningd/lightningd --bitcoin-rpcuser=sender --bitcoin-rpcpassword=sender --bitcoin-rpcport=17332 --bitcoin-cli=[path to bitflate-cli]
```

Create new address in c-lightning and send coin to c-lightning address:

```
# Create lightning address
lightning-cli newaddr

# Send Bitflate coin to lightning address
bitflate-cli sendtoaddress <address> <amount_in_bitflates>
```

After this, you need to mine a block to process the transaction. If you need help with mining a block on testnet, please send us an email: [contact@bitflate.org](mailto:contact@bitflate.org).

After your transaction is mined into a block, you should see the amount in c-lightning:

```
./cli/lightning-cli listfunds
```

### Receive Machine

On receive machine, start bitflated and lightningd.

```
# You may also need -maxtipage=864000000 option to avoid stale tip on testnet
./bin/bitflated -testnet -rpcuser=receiver -rpcpassword=receiver

# Start c-lightning daemon
./lightningd/lightningd --bitcoin-rpcuser=receiver --bitcoin-rpcpassword=receiver --bitcoin-rpcport=17332 --bitcoin-cli=[path to bitflate-cli]
```

After lightningd start, copy the server public key. It's a string that look like this: 0284a33b6286d9647b9e2fa4c7e2f71f0bd78b97c78b49726c8d04c204648fed36.

### Send Coins

We are now ready to send some coins from sender machine to receiver machine.

On sender machine:

```
# connect to receiver machine
./cli/lightning-cli connect [receiver public key] [receiver ip address]

# fund channel with coin (unit is in satoshi)
# amount cannot be too small but should not exceed 16777215 satoshi
./cli/lightning-cli fundchannel [receiver public key] [amount]

# create invoice
./cli/lightning-cli invoice [amount] "test_invoice" "test invoice description"

# invoice command generates a bolt11 string, copy it to use for pay command
./cli/lightning-cli pay [bolt11]
```

*Lightning Network requires several nodes to route transactions. You may get and error like: "invoice: insufficient incoming capacity". In that case, you don't have sufficient nodes. See the below article for possible solutions.*

[Solutions to inbound capacity problem in Lightning Network](https://medium.com/lightningto-me/practical-solutions-to-inbound-capacity-problem-in-lightning-network-60224aa13393)