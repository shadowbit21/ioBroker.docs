---
translatedFrom: en
translatedWarning: Если вы хотите отредактировать этот документ, удалите поле «translatedFrom», в противном случае этот документ будет снова автоматически переведен
editLink: https://github.com/ioBroker/ioBroker.docs/edit/master/docs/ru/adapterref/iobroker.amazon-dash/README.md
title: ioBroker.amazon-dash (только для Linux!)
hash: sGzxItEtI3Jqdb9z3uu0NdbFH9wL1sCN4sBS+ACF/2c=
---
![Логотип](../../../en/adapterref/iobroker.amazon-dash/admin/amazon-dash.png)

![Количество установок](http://iobroker.live/badges/amazon-dash-stable.svg)
![версия NPM](http://img.shields.io/npm/v/iobroker.amazon-dash.svg)
![Загрузки](https://img.shields.io/npm/dm/iobroker.amazon-dash.svg)
![НПМ](https://nodei.co/npm/iobroker.amazon-dash.png?downloads=true)

# IoBroker.amazon-dash (только для Linux!)
Адаптер для обнаружения нажатий на кнопки Amazon Dash в ioBroker.

Этот адаптер не работает под Windows!

## Шаги
1. Установите `libpcap-dev`:

`sudo apt-get install libpcap-dev`

2. Соедините свой Dash-адаптер в приложении Amazon, но не выбирайте продукт!

Просто выйдите из процедуры установки на вкладке выбора продукта.
Иначе будете каждый раз заказывать товар ;) [Немецкие инструкции](https://www.amazon.de/gp/help/customer/display.html?nodeId=201746340).

3. Нажмите кнопку тире (сначала она должна быть белой, а затем мигать красной)

4. В объектах адаптера должна появиться новая кнопка, которую вы можете использовать для запуска сцен или в адаптере JS.

5. Иногда требуется дать права доступа к сети узлу:

`sudo setcap 'cap_net_raw,cap_net_admin+eip' $(readlink -f $(which node))`

## ТРЕБУЕТСЯ ПОМОЩЬ!
Так как этот проект разрабатывается в свободное время.
Я активно ищу помощь в обслуживании и расширении этого адаптера! Если вы готовы помочь, напишите мне!

<!--

### **В РАБОТЕ** -->

## Changelog
### 1.2.0 (2023-02-10)
* (bluefox) added option to execute `setcap` rights by every start

### 1.1.0 (2020-02-25)
+ (foxriver76) support of compact mode
+ (foxriver76) usage of adapter-core and eslint

### 1.0.1
+ (Apollon77) BREAKING: Upgrade pcap library supports nodejs 10+ and also supports nodejs 12

### 0.3.1
+ (PArns) Added new Amazon MAC family

### 0.3.0
+ (foxriver76) materialize ui
+ (foxriver76) dash buttons are now of type device

### 0.2.9
+ (cernst1980) Ignore duplicate ARPs for 5 seconds
+ (PArns) Added new Amazon MAC family

### 0.2.8
+ (offline4ever) Added new Amazon MAC family

### 0.2.7
+ (arteck) fixed MAC parsing

### 0.2.6
+ (arteck) edit admin
+ (arteck) add manual MAC Addresses 
+ (PArns) Added new Amazon MAC family

### 0.2.5
+ (PArns) Added new Amazon MAC family

### 0.2.4
+ (PArns) Added new Amazon MAC family

### 0.2.3
+ (PArns) Added new Amazon MAC family

### 0.2.2
+ (PArns) Added new Amazon MAC family
+ (PArns) Fixed function name in description

### 0.2.1
+ (PArns) Added new Amazon MAC family

### 0.2.0
+ (PArns) Simplified MAC lookup (thx to GermanBluefox)

### 0.1.2
+ (PArns) Added new Amazon MAC family

### 0.1.1
+ (GermanBluefox) Try to install `libpcap-dev` automatically

### 0.1.0
+ (Niksac) Added the ability to select an interface

### 0.0.5
+ (PArns) Fixed lastPushed
+ (PArns) Fixed GIT dependency which might cause problems on some systems

### 0.0.4
+ (PArns) Removed debug infos

### 0.0.3
+ (PArns) Fixed switch state

### 0.0.2
* (PArns) Added switch state, which toggles between true and false
* (PArns) Changed License

### 0.0.1
* (PArns) Initial release

## License
The MIT License (MIT)

Copyright (c) 2016-2023 Patrick Arns <npm@patrick-arns.de>

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
