# StorageLab 0.9.1 für deinen Mac

Diese Ausgabe ist für Intel-Macs mit macOS 13.3 oder neuer. Gebaut und geprüft auf deinem Mac mit macOS 13.7.8 und 8 GB RAM. Eine separate Python-Installation und ein geöffnetes ChatGPT sind nicht nötig.

## Installieren und starten

1. StorageLab-0.9.1-macOS-Intel.dmg öffnen.
2. StorageLab.app auf „Programme“ ziehen.
3. StorageLab aus „Programme“ öffnen.

Alternativ kannst du die mitgelieferte StorageLab.app direkt starten. Im Finder bei Bedarf mit Rechtsklick → Öffnen starten, falls macOS die normale Öffnung zunächst verhindert. Diese Ausgabe hat eine lokale Ad-hoc-Signatur, aber keine Apple-Developer-ID-Signatur oder Notarisierung. Für öffentliche Verteilung wäre das noch einzurichten.

## Enthalten

Die Windows-0.9.1-Codebasis wurde für macOS angepasst: Scan und Abbruch, Suche, Speicheranalyse, Dubletten, Dateiprüfung, Organizer mit Vorschau/Freigabe und Rückgängig, NAS-/Backupvergleich und Überwachung, Mac-Check, Autostart, Foldy mit Animationen und Ton, Teeküche, Regelassistent, lokales Sprachmodell, deutsche Spracheingabe, Einstellungen und optionaler Online-Modus.

Der lokale Qwen-Assistent und das deutsche Vosk-Modell liegen vollständig in der App. Es gibt beim normalen Start keinen Modelldownload. Offline startet wie bisher der Regelassistent; „Lokales Sprachmodell“ schaltet auf Qwen um. Auf diesem Intel-Mac benötigte ein Suchauftrag etwa 43–52 Sekunden. Das kleine Modell kann irren.

Für NAS im Finder zuerst eine Freigabe verbinden, dann deren Ordner unter /Volumes wählen. StorageLab richtet keine Routerverbindungen ein und erstellt keine Backups; es vergleicht vorhandene Ordner.

Dateien werden erst nach Vorschau, Auswahl und dem Freigabeklick verschoben. Bestehende Ziele werden nicht überschrieben. Wie in der Windows-Version sind nur Verschiebungen innerhalb desselben Volumes freigegeben. Rückgängig gilt für die laufende Sitzung.

## Mac-Funktionen

- Finder statt Explorer; Mac-Speicherverwaltung und Aktivitätsanzeige statt Windows-Systemwerkzeugen.
- Übersicht des Systemvolumes und eingebundener Volumes. Netzwerkvolumes werden beim Start nicht auf freien Platz abgefragt.
- Autostart: eigene Benutzer-LaunchAgents einzeln für künftige Anmeldungen ausschalten und wieder einschalten. Laufende Programme werden dabei nicht beendet. System-LaunchAgents sind nur lesbar. Weitere Anmeldeobjekte und Hintergrunddienste in den macOS-Einstellungen verwalten.
- Einstellungen unter ~/Library/Application Support/StorageLab. Chats, Aufnahmen und Scan-Ergebnisse speichert StorageLab nicht dauerhaft.
- ⌘O für Scanauswahl, F5 für erneuten Scan und F8 für Diktieren. Auf manchen Mac-Tastaturen ist zusätzlich Fn nötig.
- Foldy: fünf schnelle Klicks öffnen die Teeküche; danach auch über Rechtsklick beziehungsweise Control-Klick erreichbar. Produktionszeiten: 60 Sekunden Ziehen und fünf Minuten Anime-Foldy.

## Noch von dir zu prüfen

Beim ersten Diktieren die Mikrofonfreigabe erteilen. Unter macOS können auch bestimmte Ordner eine Freigabe benötigen. Das echte Mikrofon wurde hier nicht aufgenommen; die Offline-Erkennung wurde mit einer künstlich erzeugten deutschen Testaufnahme geprüft.

Die optionalen Online-Anbieter benötigen deinen eigenen API-Schlüssel und eine verfügbare Modell-ID. Sie bleiben anfangs aus und fragen vor dem Senden. Es wurden keine kostenpflichtigen Anfragen mit deinen Schlüsseln ausgeführt.

Noch kein Mac-Update veröffentlicht: Die App prüft einen eigenen Intel-Mac-Updatekanal und lädt keine Windows-EXE herunter. Eine fehlende Mac-Veröffentlichung wird angezeigt. Zukünftige Mac-Updates müssen erst im Download-Repository veröffentlicht werden.

Der Prüfbericht beschreibt getestete Funktionen und Grenzen. Das ist eine lokale, funktional geprüfte Mac-Ausgabe; Kompatibilität mit anderen Macs und echte NAS-Verbindungen sind noch nicht bestätigt.

© 2026 Franz Niklaus. Die bisherigen Lizenzhinweise und ergänzte Hinweise zu Mac-Abhängigkeiten liegen in der App.
