---
layout: post
title:  "A Solution for Bitcoin Fee"
date:   2020-07-09 10:00:00 -0700
categories: post
author: Phuoc Do
---

Bitcoin has a potential problem in its security model. The block reward is an incentive for miners to provide hash power. But this reward halves every 4 years. It'll become zero around 2140. At that point, miners will need to rely on transaction fees to pay for their hash power. Some people think a fee market will develop to support mining.

Others think there's not enough incentive to support mining. Bitcoin is digital gold. People rarely want to use it for transactions. Bitcoin will need to have a perpetual block reward or a small reward inflation. You can read more about these discussions from [Hasu](https://medium.com/@hasufly/research-paper-a-model-for-bitcoins-security-and-the-declining-block-subsidy-11a21f600e33) and [Peter Todd](https://twitter.com/peterktodd/status/1231631295282843648).

Ethereum developers often criticize Bitcoin for this problem. They use a Minimum Necessary Issuance policy. It's a vague policy. Its goal is to provide miner enough incentives. Ethereum's vague policy highlights a problem. Bitcoin also has this problem. How do we set the issuance policy? What does "enough" mean? To preserve the Store of Value function, we need to pick a low inflation rate, like 0.5% or 1%. These rates are arbitrary. It's difficult to find consensus on a rate.

I want to propose a new approach, Bitflate. It's a fork of Bitcoin with inflation. Let's pick 7%, a moderately high inflation rate. Bitflate works the same way as Bitcoin. Its supply inflates at 7%. It's a high rate but not too high. If the rate is too high, the coins devalue too fast. A 7% rate has a nice feature: supply doubles every 10 years. Developers and engineers can get out of the business of picking an inflation rate. The market can decide inflation rate. They will do this by issuing a sidechain coin with the backing of Bitcoin and Bitflate coins.

Here's an example. In 2030, a financial provider wants to issue a coin that inflates at 3% per year. Let's call this coin Bit3. For simplicity, let's assume Bitcoin supply is 21 million. It no longer inflates. Bitflate supply is 30 million. It inflates at 7% per year. In 2031, Bitflate supply will reach 33 million.

At the time of this Bit3 issuance, 1 Bitcoin is equivalent to 1.4 Bitflate (30 million/21 million). If we mix ratio 1/1.4, we'd get a coin that has a supply inflation of 3.5%. To lower the inflation rate, we need to mix less Bitflate coins. In this case, the mix ratio is 1 Bitcoin and 1.2 Bitflate.

In 2040, Bitflate supply will reach 60 million. To issue a Bit3 coin, we'll need a different mix. 1 Bitcoin is equivalent to 2.8 Bitflate. We'd need a mix ratio of 1 Bitcoin and 2.4 Bitflate.

By using a mix of Bitcoin and Bitflate, the market can issue coins with any inflation rate between 0% and 7%. As builders, we no longer have the problem of deciding the inflation rate. The market can decide what it wants. The mixed coins with inflation are better suited for lending and staking. They will generate new businesses. They will create demand for Bitcoin transactions.