---
layout: post
title:  "Bitflate Binaries v0.18.0"
date:   2019-07-19 14:04:00 -0700
categories: post
author: Phuoc Do
---

After months of tinkering and adapting Bitcoin Core system, I am able to create build for Bitflate binaries.
I've mined 6k blocks to create checkpoints. Mining is paused now. I will resume mining after I post
mining setup instruction.

In this post, I show how to run Bitflate Core client.

You can download Bitflate binaries here:

(Latest version 0.18.1)

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

If your client has trouble finding nodes, use --addnode= argument.

```
# addnode s1 seed
./bin/bitflated --adnode=159.203.68.109
```

Bitflate comes with bitflate-cli, it has the same capability as bitcoin-cli. For brevity,
please refer to [bitcoin-cli](https://en.bitcoin.it/wiki/Original_Bitcoin_client/API_calls_list) documentation on how to use it.