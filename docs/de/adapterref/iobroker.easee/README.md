---
translatedFrom: en
translatedWarning: Wenn Sie dieses Dokument bearbeiten möchten, löschen Sie bitte das Feld "translationsFrom". Andernfalls wird dieses Dokument automatisch erneut übersetzt
editLink: https://github.com/ioBroker/ioBroker.docs/edit/master/docs/de/adapterref/iobroker.easee/README.md
title: ioBroker.easee
hash: Nhtw//Pj0JtYaC4vkoXniAzHmPhI26dZny0RA6ZuJJ4=
---
![Logo](../../../en/adapterref/iobroker.easee/admin/easee.png)

![NPM-Version](http://img.shields.io/npm/v/iobroker.easee.svg)
![Downloads](https://img.shields.io/npm/dm/iobroker.easee.svg)
![Anzahl der Installationen (aktuell)](http://iobroker.live/badges/easee-installed.svg)
![Anzahl Installationen (stabil)](http://iobroker.live/badges/easee-stable.svg)
![Abhängigkeitsstatus](https://img.shields.io/david/Newan/iobroker.easee.svg)
![Bekannte Schwachstellen](https://snyk.io/test/github/Newan/ioBroker.easee/badge.svg)
![NPM](https://nodei.co/npm/iobroker.easee.png?downloads=true)

# IoBroker.easee
**Tests:** ![Test und Freigabe](https://github.com/Newan/ioBroker.easee/workflows/Test%20and%20Release/badge.svg)

## Easee-Adapter für ioBroker
Adapter zum Anschluss der Easee Wallbox

## Hilfe
ChargerOpMode = Offline: 0, Getrennt: 1, AwaitingStart: 2, Laden: 3, Abgeschlossen: 4, Fehler: 5, ReadyToCharge: 6

DynamicCircuitCurrentPX -> Alle Phasen müssen innerhalb von 500ms gesetzt werden (Skript), sonst wird die Phase auf 0 gesetzt.

## Spende
[![](https://www.paypalobjects.com/de_DE/DE/i/btn/btn_donateCC_LG.gif)](https://www.paypal.com/cgi-bin/webscr?cmd=_s-xclick&hosted_button_id=L55UBQJKJEUJL)

## Changelog
<!--
  Placeholder for the next version (at the beginning of the line):
  ### **WORK IN PROGRESS**
-->
### 1.0.8 (2023-07-02)
* (Newan)  small fixes

### 1.0.7
* (Newan) Changed login URL

### 1.0.6
* (Newan) Changed that smart charging is editable

### 1.0.5
* (marwin79) More Features supported and convert values to expected datatypes

### 1.0.4
* (Newan) dynamicCircuitCurrentPX writeable (set all Phases in 500ms) to limit ampere

### 1.0.3
* (Newan) Adapter crash fixed an other bugfixes

### 1.0.1
* (Newan) Add circuitMaxCurrentPX to limit current ampere

### 1.0.0
* (Newan) Stable Version with SignalR

## License
MIT License

Copyright (c) 2021 Newan <iobroker@newan.de>

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