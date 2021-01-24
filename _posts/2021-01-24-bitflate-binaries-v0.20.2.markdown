---
layout: post
title:  "Bitflate Binaries v0.20.2"
date:   2021-01-24 10:00:00 -0700
categories: post
author: Phuoc Do
---

**Important: Please backup your datadir and wallet before upgrading.**

We have a new release for Bitflate Core client, v0.20.2. This release is a step ahead of Bitcoin Core client. It includes the pchMessageStart fix. This fix prevents Bitflate Core clients from connecting to Bitcoin Core clients. You can see Bitcoin Core v0.20.1 release notes for changes:

[Bitcoin Core 0.20.1 Release Notes](https://bitcoin.org/en/release/v0.20.1)

You can download Bitflate binaries here:

[Bitflate 0.20.2](https://github.com/bitflate/bitflate/releases/tag/v0.20.2)

**Important: This release requires a reindex of your local blockchain. Please backup before running reindex.**

```
# addnode s1 seed and reindex
./bin/bitflated -addnode=159.203.68.109 -reindex
```

Bitflate network currently has two seed nodes:

- 159.203.68.109 (s1.bitflate.org)
- 157.230.117.175 (s2.bitflate.org)

After extracting the binaries, you can run the software with the below following commands.

For mainnet:

```
./bin/bitflated
./bin/bitflate-qt
```

In this version, fallbackfee is set to 0 by default. In order to enable it, you'd need to run the client with -fallbackfee=0.0002.

For testnet:

```
./bin/bitflated -testnet
./bin/bitflate-qt -testnet
```

If your client has trouble finding nodes, use -addnode= argument.

```
# addnode s1 seed
./bin/bitflated -addnode=159.203.68.109
```

Bitflate comes with bitflate-cli, it has the same capability as bitcoin-cli. For brevity,
please refer to [bitcoin-cli](https://en.bitcoin.it/wiki/Original_Bitcoin_client/API_calls_list) documentation on how to use it.