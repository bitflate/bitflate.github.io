---
layout: post
title:  "Bitflate Binaries v0.19.0.1"
date:   2020-03-27 10:00:00 -0700
categories: post
author: doph
---

**Important: Please backup your datadir and wallet before upgrading**

We have a new release for Bitflate Core client. This release notable change in Bitflate is burying of SegWit at block 28224.

For other notable changes in v0.19.0.1, see Bitcoin Core release notes:

[Bitcoin Core 0.19.0.1 Release Notes](https://bitcoin.org/en/release/v0.19.0.1)

You can download Bitflate binaries here:

[Bitflate 0.19.0.1](https://github.com/bitflate/bitflate/releases/tag/v0.19.0.1)

Bitflate network currently has two seed nodes:

- 159.203.68.109 (s1.bitflate.org)
- 157.230.117.175 (s2.bitflate.org)

After extracting the binaries, you can run the software with the below following commands.

For mainnet:

```
./bin/bitflated
./bin/bitflate-qt
```

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