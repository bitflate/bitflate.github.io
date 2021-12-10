---
layout: post
title:  "Bitflate Binaries v0.18.1"
date:   2019-08-11 14:23:00 -0700
categories: post
author: doph
---

You can download Bitflate binaries here:

[Bitflate 0.18.1](https://github.com/bitflate/bitflate/releases/tag/v0.18.1)

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