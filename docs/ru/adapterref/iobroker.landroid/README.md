---
translatedFrom: en
translatedWarning: Если вы хотите отредактировать этот документ, удалите поле «translationFrom», в противном случае этот документ будет снова автоматически переведен
editLink: https://github.com/ioBroker/ioBroker.docs/edit/master/docs/ru/adapterref/iobroker.landroid/README.md
title: Этот адаптер УСТАРЕЛ и не будет развиваться дальше.
hash: 0EHhr5qlOIy7tWNtiOKpY5u9grZDQwwP6h6mvcA9Q3Q=
---
![Логотип](../../../en/adapterref/iobroker.landroid/admin/landroid.png)

![Количество установок](http://iobroker.live/badges/landroid-stable.svg)
![версия NPM](http://img.shields.io/npm/v/iobroker.landroid.svg)
![Загрузки](https://img.shields.io/npm/dm/iobroker.landroid.svg)
![Статус зависимости](https://img.shields.io/david/iobroker-community-adapters/iobroker.landroid.svg)
![Известные уязвимости](https://snyk.io/test/github/iobroker-community-adapters/ioBroker.landroid/badge.svg)
![НПМ](https://nodei.co/npm/iobroker.landroid.png?downloads=true)
![Трэвис-CI](http://img.shields.io/travis/iobroker-community-adapters/ioBroker.landroid/master.svg)
![AppVeyor](https://ci.appveyor.com/api/projects/status/github/iobroker-community-adapters/ioBroker.landroid?branch=master&svg=true)
![Значок Гринкипера](https://badges.greenkeeper.io/iobroker-community-adapters/ioBroker.landroid.svg)

# Этот адаптер УСТАРЕЛ и больше не будет развиваться
-----

В настоящее время дальнейшее развитие этого адаптера не планируется. __Пожалуйста, перейдите на адаптер ioBroker.worx__, который поддерживается.
Если вы пропустите какие-либо функции на ioBroker.worx, откройте задачу в этом репозитории (https://github.com/tp1de/ioBroker.worx/issues).

ioBroker.landroid будет оставаться доступным в течение некоторого времени, но имейте в виду, что он не будет адаптирован к Node 20 и грядущему js-controller v5.

-----

# IoBroker.landroid
## Адаптер Worx Landroid для ioBroker
Это адаптер ioBroker для вашей косилки Worx Landroid. Он был протестирован с Landroid WG796E.

## Changelog

<!--
    Placeholder for the next version (at the beginning of the line):
    ### **WORK IN PROGRESS**
-->
### **WORK IN PROGRESS**
-   (mcm1957) changed: Testing has been changed to support node 16, 18 and 20
-   (mcm1957) changed: Dependencies have been updated

### 1.0.3
* (ldittmar) compact mode compatibility added
* (ldittmar) add chinese support

### 1.0.2
* (ldittmar) Support of admin3

### 1.0.0
* (ldittmar) Fixed little changes

### 0.1.1
* (ldittmar) Change PIN field to type password

### 0.1.0
* (ChrBender) Bug with start/stop button fixed

### 0.0.4
* (ldittmar) Bugfixes

### 0.0.3
* (ldittmar) Minor bug fixes / compatibility with the WG797E.1 mower

### 0.0.2
* (ldittmar) read all important informations (can't start or stop ist at this time)

### 0.0.1
* (ldittmar) initial commit

## License
The MIT License (MIT)

Copyright (c) 2018-2019 ldittmar <iobroker@lmdsoft.de>

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in
all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN
THE SOFTWARE.