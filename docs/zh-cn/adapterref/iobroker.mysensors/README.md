---
translatedFrom: en
translatedWarning: 如果您想编辑此文档，请删除“translatedFrom”字段，否则此文档将再次自动翻译
editLink: https://github.com/ioBroker/ioBroker.docs/edit/master/docs/zh-cn/adapterref/iobroker.mysensors/README.md
title: ioBroker.mysensors
hash: KnLKRjIiq8ieUK5hWxhZac4nJqAAScbQVkOtPO/H3Fg=
---
![商标](../../../en/adapterref/iobroker.mysensors/admin/mysensors.png)

![安装数量](http://iobroker.live/badges/mysensors-stable.svg)
![NPM 版本](http://img.shields.io/npm/v/iobroker.mysensors.svg)
![下载](https://img.shields.io/npm/dm/iobroker.mysensors.svg)
![测试](https://travis-ci.org/ioBroker/ioBroker.mysensors.svg?branch=master)
![新PM](https://nodei.co/npm/iobroker.mysensors.png?downloads=true)

# IoBroker.mysensors
此适配器与[我的传感器](http://www.mysensors.org) 串行或以太网网关（TCP 或 UDP）通信。
如果在这种情况下选择的以太网网关 ioBroker 是服务器，则需要连接。

## TCP 客户端
此选项仅与 TCP&lt;=&gt;Serial bridge 一起使用，如 [ESP-链接](https://github.com/jeelabs/esp-link)。

##前置要求
要在 Windows 上使用串行端口，需要 VS 构建二进制文件。
要在 linux 上使用串口，它是 build-essential 和 python2.7 必需的。要安装它们，只需编写：

```
sudo apt-get update
sudo apt-get install build-essential
sudo apt-get install python2.7
```

<!-- 下一个版本的占位符（在行首）：

### **正在进行中** -->

## Changelog
### 3.0.0 (2022-03-21)
* (bluefox) Updated serialport package

### 2.0.3 (2021-11-10)
* (sergeyksv) Added the support of deep sleep

### 2.0.1 (2020-06-01)
* (jangatzke) compare integer values

### 2.0.0 (2019-05-15)
* (Apollon77) Support for nodejs 12 added, nodejs 4 is no longer supported!

### 1.2.2 (2018-09-17)
* (Haba1234) Added new objects (library 2.3.x)
* (Haba1234) Added support for sleeping nodes

### 1.2.1 (2018-01-23)
* (Haba1234) Update for Admin v3

### 1.2.0 (2018-01-23)
* (Apollon77) Upgrade Serialport Library

### 1.1.0 (2017-12-17)
* (bluefox) TCP client added

### 1.0.10 (2017-10-24)
* (jangatzke) Fixed wrong data type for scene controller, enabled ack flag on set command

### 1.0.8 (2017-04-18)
* (Qube2org) adjust log level for I_LOG_MESSAGE

### 1.0.7 (2017-04-10)
* (bluefox) fix I_TIME request

### 1.0.6 (2016-12-17)
* (bluefox) show extended list of serial ports

### 1.0.5 (2016-12-15)
* (Apollon77) update serialport library for node 6.x compatibility

### 1.0.4 (2016-07-01)
* (bluefox) add comment in configuration
* (bluefox) fix inclusion mode control

### 1.0.2 (2016-07-06)
* (soef) fix id usage

### 1.0.1 (2016-07-01)
* (soef) necessary version of sensor module increased

### 1.0.0 (2016-06-28)
* (soef) some value corrections and enlargement

### 0.2.6 (2016-06-16)
* (bluefox) do not switch off inclusion mode by stop

### 0.2.5 (2016-06-14)
* (bluefox) remove debug outputs

### 0.2.4 (2016-06-10)
* (bluefox) try/catch parse of messages

### 0.2.3 (2016-04-13)
* fix boolean values

### 0.2.2 (2016-04-10)
* (bluefox) implement inclusion mode

### 0.2.1 (2016-03-21)
* (bluefox) translates
* (bluefox) connection timeout for serial connection

### 0.2.0 (2016-03-21)
* (bluefox) wait till serial port is opened
* (bluefox) configurable baud rate

### 0.1.10 (2016-03-21)
* (bluefox) set role of dimmer as level.dimmer

### 0.1.9 (2016-03-15)
* (bluefox) fix typo

### 0.1.8 (2016-03-02)
* (bluefox) fix connection indicator for serial

### 0.1.7 (2016-03-02)
* (bluefox) do not send any data on disconnect

### 0.1.6 (2016-03-02)
* (bluefox) set UDP as default settings

### 0.1.5 (2016-03-02)
* (bluefox) change tree

The MIT License (MIT)

Copyright (c) 2016-2022, Bluefox <dogafox@gmail.com>

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.