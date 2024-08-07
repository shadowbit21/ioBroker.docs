---
title:       "Systemeinstellungen"
lastChanged: "04.11.2022"
---


Die Systemeinstellungen erreicht man aus jedem Menüpunkt des Admins über das 
Schraubenschlüssel-Icon in der Titelzeile des Bildschirms.

![Die Systemeinstellungen](media/ADMIN_Settings_main.png)

## Systemeinstellungen

In den Haupteinstellungen werden grundlegende Parameter für ioBroker eingestellt, die in 
ioBroker auch von den Adaptern verwendet werden.

Einige Parameter werden bereits aus den Einstellungen des Hosts übernommen.

**Systemsprache**

damit kann zwischen verschiedenen Systemsprachen gewählt werden. Es ist möglich, dass 
noch nicht alle Sprachen vollständig unterstützt werden.

**Temperatureinheit**

dieses Wert wird von manchen Adaptern verwendet. Möglich ist °C oder °F.

**Währung**

Hier kann das gewünschte Währungsformat z.B. € eingetragen werden. Momentan benutzt das noch kein Adapter.

**Datumsformat**

Die festgelegte Auswahl wird im admin und vis angezeigt.

**Float Teiler Zeichen**

Komma oder Punkt für Float-Werte

**Standard-Historie**

Bei installierten Adapter zum loggen von Datenpunkten wird hier entsprechende Adapter ausgewählt

Ist nur ein History Adapter (SQL/History/InfluxDB) installiert wird dieser verwendet, 
sind mehrere vorhanden, kann man einen auswählen.

**Expertenmodus**

tbd

**Standardprotokollstufe**

tbd

**Erster Tag der Woche**

tbd

**Lokale Einstellungen**

tbd

## Repositories
![](media/ADMIN_Settings_repos.png)

ioBroker kann die Adapterliste von unterschiedlichen Quellen beziehen. Bei der Installation sind folgende Quellen eingetragen:

* stable: http://download.iobroker.net/sources-dist.json
* beta: http://download.iobroker.net/sources-dist-latest.json

Sollten aus einer älteren Installation hier noch andere Repositories eingetragen sein, 
sollten diese gelöscht werden, da sie nicht mehr gepflegt werden.

## Lizenzen
![](media/ADMIN_Settings_licences.png)

## Zertifikate
![Zertifikate](media/ADMIN_Settings_certificates.png)

Hier ist die zentrale Stelle für die Zertifikate, die für die SSL/HTTPS Kommunikation benutzt 
werden. Die Zertifikate werden von admin, web, simple-api, socketio benutzt. Defaultmäßig 
sind Standardzertifikate installiert. Damit kann man nichts verifizieren. Sie dienen nur der 
SSL-Kommunikation. Weil die Zertifikate offen liegen sollte man eigene (self-signed) 
Zertifikate benutzen, richtige Zertifikate kaufen oder auf Let’s Encrypt umsteigen. Die 
Kommunikation mit default Zertifikaten ist nicht sicher und falls jemand das Ziel hat den 
Traffic mitzulesen, könnte dies gemacht werden. Unbedingt eigene Zertifikate installieren. 
Z.b. unter linux.


Zertifikate können wahlweise als Pfad angegeben werden oder komplett per drag and 
drop hochgeladen werden


<span style="color:red">Es ist grundsätzlich eine gute Idee neue Zertifikate mit dem Web-Adapter zu testen und nicht direkt mit dem Admin-Adapter,
damit man sich nicht aus dem System aussperrt.</span>

Bei der Angabe eines Pfades müssen die korrekten Berechtigungen für den iobroker Benutzer vorhanden sein.

Für die Datei selbst 644, für die übergeordneten Verzeichnisse 755.

Sind die Rechte falsch kommt eine Fehlermeldung wie:

``web.0 (24704) Cannot create webserver: Error: error:0909006C:PEM routines:get_name:no start line``

Man kann den Zugriff prüfen, wenn man sich als Benutzer root am Server einloggt, dann zum iobroker Benutzer wechselt und die Zertifikatsdatei auflistet:

``su iobroker``

``ls -l /Pfad/zum/Zertifikat``

Es sollte **-rw-r--r--** am Beginn der Zeile angezeigt werden.

Wenn das eigentliche Zertifikat verlinkt ist, müssen die Rechte des Linkziels geprüft werden.

Kommt hier eine Meldung wie 

``ls: Zugriff auf '/Pfad/zum/Zertifikat' nicht möglich: Keine Berechtigung``

Müssen die Rechte angepasst werden.

Als root Benutzer für die Datei:

``chmod 644 /Pfad/zum/Zertifikat``

Für die übergeordneten Verzeichnisse:

``chmod 755 /Pfad/zum``

## Let’s Encrypt SSL
![Let’s Encrypt](media/ADMIN_Settings_letsencrypt.png)


Let’s Encrypt ist eine kostenlose, automatisierte und Open Source certificate authority der
unabhängigen Internet Security Research Group (ISRG).

Nähere Informationen zu Let’s Encrypt gibt es [hier](https://letsencrypt.org/).

Einige Installationen benutzen Dynamic DNS o.ä. um über eine von dort vergebene Adresse, 
die eigene domain zu erreichen. IoBroker unterstützt die automatische Anforderung und 
Erneuerung von Zertifikaten bei der Let’s Encrypt Organisation.

Die Option die kostenlosen Zertifikate von Let’s Encrypt zu benutzen existiert in nahezu 
jedem Adapter, der einen Webserver starten kann und HTTPS unterstützt.

Wenn man die Option Zertifikate zu nutzen aktiviert, jedoch nicht das automatische Update, 
versucht die entsprechende Instanz mit gespeicherten Zertifikaten zu arbeiten.

Wenn die automatischen Updates aktiviert sind, versucht die Instanz Zertifikate bei Let’s 
Encrypt anzufordern und aktualisiert diese automatisch.

Die Zertifikate werden beim ersten Aufruf der entsprechenden Adresse zum ersten mal 
angefordert. D.h. wenn man z.B. “sub.domain.com” als Adresse konfiguriert und ruft 
anschließend https://sub.domain.com auf werden die Zertifikate erstmalig angefordert 
was ein wenig dauern kann bevor die Antwort kommt.

Die Ausgabe der Zertifikate ist eine komplexe Prozedur, aber wenn man die folgende 
Erklärung befolgt sollte es leicht sein, die kostenlosen Zertifikate zu erhalten.

**Vorgehensweise:**

Ein neues Konto mit der eingegebenen eMail-Adresse muss erstellt werden (Setup dazu in 
den Systemeinstellungen)

Ein zufälliger Schlüssel als Passwort für das Konto wird erzeugt.

Wenn das Konto angelegt wurde öffnet das System eine kleine Website auf Port 80 um 
die Adresse zu bestätigen.

Let’s encrypt benutzt immer den Port 80 um die Adresse zu prüfen.

Falls der Port 80 bereits von einem anderen Dienst benutzt wird, kommt Punkt 4 zum 
tragen – also dem anderen Dienst einen anderen Port zuweisen!

Wenn der kleine Webserver gestartet ist wird die Anfrage nach den Zertifikaten für 
die angegebenen Adressen in den Systemeinstellungen an den Let’s encrypt Server 
gesendet.

Der Let’s Encrypt Server sendet eine challenge phrase als Antwort auf die Anfrage zurück 
und versucht nach einer Weile diese challenge phrase unter der Adresse “http://yourdomain:80/.well-known/acme-challenge/” zu lesen.

Wenn der Server diese challenge phrase von unsrere Seite zurückbekommt sendet der 
Let’s Encrypt Server die Zertifikate. Diese werden in dem Verzeichnis, das in den Systemeinstellungen eingetragen ist gespeichert.

Dieses klingt komplex, aber alles was man machen muss ist ein paar Checkboxen zu 
aktivieren und die eMail-Adresse und die Web-Adresse in den Systemeinstellungen einzutragen.

Die erhaltenen Zertifikate sind für etwa 90 Tage gültig. Nachdem diese Zertifikate das erste mal 
ausgestellt wurden wird eine weiterer Task gestartet, der die Gültigkeit automatisch verlängert.

Dieses Thema ist ziemlich komplex und tausende Dinge können schiefgehen. Wenn es 
damit nicht klappen sollte wird empfohlen den IoT-Adapter für den Zugang von unterwegs 
zu benutzen.

Let’s Encrypt funktioniert nur mit einer node.js version>=4.5



## Standard ACL
![Zugriffsrechte](media/ADMIN_Settings_zugriffsrechte.png)

In dieser Unterseite können für alle User/Gruppen die Zugriffsrechte für verschieden 
Bereiche festgelegt werden


## Statistik
![Statistik](media/ADMIN_Settings_statistics.png)

Damit wir ein wenig den Überblick über die Installationen (verwendete Adapter) und die geografische Verteilung haben würden wir uns sehr freuen, wenn wir diese Informationen bekommen.

Man kann unterschiedlich umfangreiche Informationen verschicken. Dieser Umfang kann links ausgewählt werden.

Auf der rechten Seite wird dann angezeigt welche Daten versandt werden.
Diese Daten werden absolut anonym ausgewertet.
