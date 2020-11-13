---
layout: post
title:  "Bitflate Binaries v0.20.0"
date:   2020-07-25 10:00:00 -0700
categories: post
author: Phuoc Do
---

We have a new release for Bitflate Core client.

For other notable changes in v0.20.0, see Bitcoin Core release notes:

[Bitcoin Core 0.20.0 Release Notes](https://bitcoin.org/en/release/v0.20.0)

You can download Bitflate binaries here:

[Bitflate 0.20.0](https://github.com/bitflate/bitflate/releases/tag/v0.20.0)

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