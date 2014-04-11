RaspBerry CEC Server
======

* Aktuelle Version: 0.1
* Based on original "https://github.com/Pulse-Eight/libcec" Version 2.4.1-2 

## Dokumentation / Funktionsweise
In die Lib wurde ein Socket-Server implementiert, der �ber den Port 8888 reine 
Hex-Befehle entgegen nimmt. Die notwendigen Befehle zur Steuerung von CEC-f�hignen 
Geräten können unter: http://www.cec-o-matic.com generiert werden. Diese Befehle 
m�ssen dann über den Socket als reine Hex-Werte �bergeben werden.

Beispiel:
Fernseher auf Stand-by w�re: 10:36 --> 0x100x36 in Hex

�ndern des Ports vor dem Compilieren:
Der Port, auf den der Server horcht, kann wie folgt ge�ndert werden:
Editieren von /src/lib/CECProcessor.cpp
Zeile 1095 --> den Wert in Klammer anpassen (default 8888)

## Compilieren der Lib:
### System updaten
```sudo apt-get update```

### System Voraussetzungen schaffen
```sudo apt-get install build-essential autoconf liblockdev1-dev libudev-dev git libtool pkg-config```

### Holen
```git clone https://github.com/Eisbaeeer/RaspCEC-Server```

```cd RaspCEC-Server```

```cd libcec```

### Compilieren
```sudo ./bootstrap```

```sudo ./configure --with-rpi-include-path=/opt/vc/include --with-rpi-lib-path=/opt/vc/lib --enable-rpi```

```sudo make```

```sudo make install```

### Libraries linken
```sudo ldconfig```

### Starten des CEC-Servers
```cec-client &```

 
