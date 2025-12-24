# NEO-Einschaltverhalten

Das Einschaltverhalten legt fest, wie sich der NeoPixel-Adapter nach dem Einschalten der Stromversorgung oder einem Neustart verhält. 

## Mögliche Einstellungen
- **Letzter Zustand**: Der zuletzt aktive Effekt, die Farben und die Helligkeit werden wiederhergestellt.
- **Vordefinierter Zustand**: Es wird ein festgelegter Effekt, eine bestimmte Farbe oder Helligkeit aktiviert, unabhängig vom vorherigen Zustand.
- **Aus**: Die Segmente bleiben nach dem Einschalten ausgeschaltet, bis ein Befehl empfangen wird.

## Hinweise
- Das Einschaltverhalten kann für jedes Segment individuell konfiguriert werden.
- Die Einstellung ist besonders nützlich, um nach Stromausfällen ein gewünschtes Lichtbild sicherzustellen.
- Änderungen am Einschaltverhalten werden nach dem nächsten Neustart wirksam.

## Typische Anwendungsfälle
- Automatisches Wiederherstellen der letzten Lichtszene nach Stromausfall
- Immer mit einer bestimmten Farbe oder Helligkeit starten (z.B. Nachtlicht)
- Nach dem Einschalten immer ausgeschaltet bleiben (z.B. für sicherheitskritische Anwendungen)
