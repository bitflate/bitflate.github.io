---
layout: post
title:  "Bitflate Solo Mining with GekkoSicence NewPac USB"
date:   2019-07-21 15:44:00 -0700
categories: post
author: doph
---

I assume you have downloaded Bitflate binaries. If not, see this article:

[Bitflate Binaries](https://bitflate.github.io/post/2019/07/19/bitflate-binaries-v0.18.0.html)

In this post, I'll show you how to mine Bitflate coins. This is my current setup. We currently don't have any pool support. I do solo mining. If you already have ASIC mining hardware, you can use your own mining setup with Bitflate Core client. I show simple and low cost mining setup.

First, we need to buy some hardware. I've got mine from 419mining.com and Amazon.

[GekkoScience NewPac USB Stickminer](https://www.419mining.com/shop/miners/gekkoscience-newpac-dual-bm1387-usb-stickminer/)

[Pluggable USB 2.0 7-Port Hub](https://www.419mining.com/shop/cables/plugable-usb-2-0-7-port-hub-with-60w-power-adapter/)

[ARCTIC Breeze USB Fan](https://www.amazon.com/ARCTIC-Breeze-Mobile-Flexible-Portable/dp/B003XN24GY/ref=sr_1_5?keywords=artic+fans&qid=1563749478&s=gateway&sr=8-5)

Next, we need cgminer software in addition to run mining. We'll use a modified cgminer version from GekkoScience NewPac vendor vthoang/cgminer. I modified the code to enable proper solo mining. Please use this cgminer version. Otherwise, you will not get any coin reward.

### Ubuntu

```
# clone the code tree
git clone https://github.com/bitflate/cgminer
# go to r606 branch, this branch has the latest code for GekkoScience NewPac
git checkout r606
# follow the build instruction on your OS on the README page
# I show the instruction for Ubuntu here
sudo apt-get install build-essential autoconf automake libtool pkg-config \
                             libcurl4-openssl-dev libudev-dev libusb-1.0-0-dev \
                             libncurses5-dev
./autogen.sh
CFLAGS="-O2 -Wall -march=native" ./configure <options>
make
```

After building cgminer, we need to generate an address to solo mining to. We do this through bitflate-cli.

```
./bin/bitflate-cli getnewaddress "myaddress"
```

Plug all the hardware together into your machine. Start Bitflate Core client. We are ready to mine with this command.

```
./cgminer -o http://localhost:7332 -u [username] -p [password] --btc-address [address generated above]
```

### Windows

On Windows, you need to perform cgminer build. The build instruction is here:

[Windows Build Instruction](https://github.com/bitflate/cgminer/blob/master/windows-build.txt)

For simplicity, we've created a Windows build for you to use on x86-64 machines. You can download it here:

[Windows Build](https://github.com/bitflate/cgminer/releases/tag/v4.11.1)

Prior to running cgminer.exe, you need to install zadig WinUSB driver. You can download it here:

[http://zadig.akeo.ie](http://zadig.akeo.ie)

```
cgminer.exe -o http://localhost:7332 -u [username] -p [password] --btc-address [address generated above]
```

If you have more questions, you can find information about GekkoScience NewPac miner on bitcointalk.org forum:

[https://bitcointalk.org/index.php?topic=5053833.0](https://bitcointalk.org/index.php?topic=5053833.0)