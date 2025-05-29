MConfig v1.2 / 05.2010

----------------------------------------------------------------------------------------------------------------------------
----------------------------------------------------------------------------------------------------------------------------
----------------------------------------------------------------------------------------------------------------------------
----------------------------------------------------------------------------------------------------------------------------
----------------------------------------------------------------------------------------------------------------------------
----------------------------------------------------------------------------------------------------------------------------
----------------------------------------------------------------------------------------------------------------------------
----------------------------------------------------------------------------------------------------------------------------
----------------------------------------------------------------------------------------------------------------------------
----------------------------------------------------------------------------------------------------------------------------
----------------------------------------------------------------------------------------------------------------------------
----------------------------------------------------------------------------------------------------------------------------

Allgemein:
----------------------------------------------------------------------------------------------------------------------------

Das Programm kann auf jedem Windows Rechner ausgeführt werden.
Zur Ausführung ist allerdings das .Net Framework nötig, dies ist, ebenso wie der USB VCP Treiber meist schon installiert. 
Sollte das Programm 'Application\MConfig.exe' nicht ausführbar sein, bitte zunächst das .Net Framework installieren.
Nach Verbindung der PC USB Schnittstelle mit der USB Schnittstelle der Motorsteuerung fordert Windows evt. den Treiber an. 
In diesem Fall bitte nachinstallieren.


Virtueller COM Port:
----------------------------------------------------------------------------------------------------------------------------
Der USB Treiber richtet einen virtuellen COM Port ein. Die COM Port Nummer kann bei bestehender Motorsteuerung-PC Verbindung 
im Gerätemanager ausgelesen werden.

-> Start -> Einstellungen -> System -> Register Hardware -> Button Gerätemanager -> Anschlüsse COM und LPT



Anwendung starten / Verbindung aufbauen:
----------------------------------------------------------------------------------------------------------------------------

Nach Start der Anwendung MConfig.exe den Button 'Einstellungen' (oben rechter Bereich) klicken und im geöffneten Dialog den 
COM Port der Motorsteuerung wählen.

Jetzt wird die Verbindung durch einen Klick auf den Button 'Verbindung aufbauen' (oben links) aufgebaut. 
Ein erfolgreicher Verbindungsaufbau wird in der Statusleiste angezeigt.


Parameter aus der Steuerung in die Anwendung laden:
----------------------------------------------------------------------------------------------------------------------------
Nach erfolgreichem Verbindungsaufbau werden die Daten durch ein Klicken auf den Button 'Daten laden' (Pfeil nach oben) 
in die Anwendung geladen.




Parameter aus der Anwendung in die Motorsteuerung laden:
----------------------------------------------------------------------------------------------------------------------------
Nach erfolgreichem Verbindungsaufbau werden die Daten durch ein Klicken auf den Button 'Daten senden' (Pfeil nach unten) 
in die Motorsteuerung übertragen.

Hierzu müssen die Daten allerdings konsistent sein, d.h. :

- Die Phasenverschiebung muss zwischen 0-180° liegen
- Die Eingabefelder müssen komplett mit Zahlenwerten ausgefüllt sein.

Bei fehlerhafter Eingabe erscheint ein Meldefenster.

!!!Nach erfolgreicher Übertragung ändert sich evt. der Wert der Phasenverschiebung!!!
Diese Änderung ist Systembedingt durch Auf- oder Abrundung. Theoretisch ist eine Abstufung der Phasenverschiebung von 
0,17578125° möglich. Der Anwender kann aber nur x,x° eingeben. Der eingegebene Wert wird dann vor der Übertragung geprüft, 
auf einen möglichen Wert gerundet, übertragen und im Anwenderprogramm aktualisiert.


Wenn die Daten erfolgreich in die Motorsteuerung übernommen wurden, quittiert die Motorsteuerung dies mit einem Neustart.

Alle Einstellungen sind remanent, d.h. dauerhaft, in der Motorsteuerung gespeichert.



Betriebsstundenzähler:
----------------------------------------------------------------------------------------------------------------------------
Wenn eine Frequenz größer 0 Hz ausgegeben wird, wird der interne Betriebsstundenzähler sekundengenau erhöht und alle 5 Minuten 
in das interne EEPROM gespeichert. Beim Auslesen der Parameter aus der Motorsteuerung in die PC Anwendung wird der Betriebsstundenzähler 
automatisch ausgelesen und angezeigt. Durch Klicken auf den Reset Button und spätere Bestätigung dieser Eingabe wird der Betriebsstundenzähler 
zurückgesetzt. Vorrraussetzung zum Rücksetzen des Zählers ist eine aufgebaute Verbindung.


Parameter:
----------------------------------------------------------------------------------------------------------------------------

- Stufe 1 (in Hz): Hier wird die Ausgabefrequenz für die Stufe 1 (linker LED Taster) eingegeben (theoretisch 33 1/3 RPM = 50Hz).

- Stufe 2 (in Hz): Hier wird die Ausgabefrequenz für die Stufe 2 (rechter LED Taster) eingegeben (theoretisch 45 RPM = 67,5Hz).

- Phasenverschiebung (in °): Die Phasenverschiebung von Phase 1 zu Phase 2. Üblich ist eine Phasenverschiebung von 90°. 
Da die Motorwicklungen allerdings nie mechanisch optimal angeordnet sind, besteht hier die Möglichkeit durch Anpassung dieses 
Parameters einen ruhigeren Motorlauf (weniger Ruckeln) zu erzielen.

- Startrampe (in Hz/s): Hierbei handelt es sich um die Beschleunigungsrampe. Wird ein Wert von 10Hz/s eingegeben, wird das Signal bei Änderung 
in positiver Richtung um 10Hz/s verstellt. 

Z.B. : Die Steuerung ist ausgeschaltet, Stufe 1 (hier 50Hz) wird durch betätigen des Tasters für Stufe 1 eingeschaltet. Jetzt fährt die 
ausgegebene Frequenz beider Phasen innerhalb 5 Sekunden von 0Hz auf 50Hz hoch.

Der Wert für die Startrampe kann im Bereich von 0-99Hz/s eingestellt werden. Wird eine 0 eingestellt, so ist die Startrampe deaktiviert und 
die angeforderte Frequenz (Soll Frequenz) wird direkt übernommen. 

- Stopprampe (in Hz/s): Analog zur Startrampe allerdings bei Frequenzänderung in negativer Richtung.



Weitere Einstellungen:
----------------------------------------------------------------------------------------------------------------------------

- LED blinken: Lässt die jeweilige LED (Stufe 1 oder 2) während der Rampe blinken und geht danach in Dauerlicht über. Anders ausgedrückt, 
blinkt die LED wenn die Sollfrequenz ungleich Istfrequenz ist. Wenn der Haken nicht gesetzt ist leuchtet die entsprechende LED nach Anwahl.
einer Stufe direkt in Dauerlicht.

- Signal Steuerung EIN: Wenn diese Funktion aktiviert wurde und die Motorsteuerung eingeschaltet ist, aber 33/45RPM nicht aktiviert wurde (Frequenz = 0Hz)
 blinken die LED´s alle 5 Minuten nach einem bestimmten Muster. Diese Anzeige dient dazu eine eingeschaltete Motorsteuerung früher oder später zu erkennen.

- Drehrichtungsumkehr: Bei gesetzer Checkbox wird die Drehrichtung 






Viel Spaß mit der Steuerung und angenehmens Musik hören!