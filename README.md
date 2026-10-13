# StorageLab für macOS

StorageLab 0.9.1 für **Intel-Macs (x86_64) ab macOS 13.3**. Grundlage ist die Windows-Version 0.9.1 von Franz Niklaus. Die Mac-Ausgabe enthält die angepassten Dateifunktionen, Foldy, Teeküche, den lokalen Qwen-Assistenten und deutsche Offline-Spracheingabe.

## Download

Die installierbare Datei heißt **StorageLab-0.9.1-macOS-Intel.dmg** und liegt auf der [öffentlichen Download-Seite](https://github.com/wampenwalther-glitch/StorageLab-macOS/releases/latest). Downloadgröße: etwa 1,51 GB. Beide Offline-Modelle sind enthalten; beim normalen Start wird kein Modell heruntergeladen. Python muss nicht installiert werden.

DMG öffnen, StorageLab.app auf Programme ziehen und von dort starten.

**Diese Ausgabe ist lokal funktional geprüft und hat eine Ad-hoc-Signatur. Sie besitzt keine Apple-Developer-ID-Signatur und ist nicht notarisiert. macOS kann die Öffnung eines heruntergeladenen Exemplars blockieren. Apple Silicon ist nicht geprüft; dies ist kein nativer Apple-Silicon-Build.**

## Funktionen

- Scan, Suche, Speicheranalyse, Dubletten und Datei-/Containerprüfung
- Organizer mit Vorschau, Auswahl, Freigabe und Rückgängig; kein Überschreiben
- NAS-/Backupvergleich und Überwachung vorhandener Ordner
- Mac-Check, Laufwerksübersicht und Verwaltung eigener Benutzer-LaunchAgents
- Regelassistent, lokales Qwen-Sprachmodell und deutsche Vosk-Spracheingabe
- Optionale Online-Anbieter mit eigenem Schlüssel und Bestätigung vor dem Senden
- Foldy, Animationen, Sounds, Stummschaltung und geheime Teeküche

## Prüfungen und Grenzen

34 automatisierte Tests und Oberflächenprüfungen auf einem Intel-Mac mit macOS 13.7.8 und 8 GB RAM bestanden. Echte Mikrofonaufnahme, NAS-Verbindung, fremde Macs und Online-API-Konten sind noch nicht vollständig geprüft. Das kleine lokale Sprachmodell kann irren und benötigt auf dem geprüften Mac bei einem Suchauftrag etwa 43–52 Sekunden.

[Installationsanleitung](StorageLab-Mac-Anleitung.md) · [Prüfbericht](StorageLab-Mac-Pruefbericht.md)

## Quellcode und Weiterentwicklung

Die vollständige angepasste Quelle samt Ressourcen, Projektanweisungen, Lizenzen, Buildanleitung und ursprünglicher Übergabe ist als **StorageLab-0.9.1-macOS-Quellcode.zip** auf der [Release-Seite](https://github.com/wampenwalther-glitch/StorageLab-macOS/releases/latest) veröffentlicht. Verwende dieses ZIP für die Weiterentwicklung. GitHubs automatisch erzeugte „Source code“-Archive enthalten nur die Dateien des Repositorys und ersetzen das vollständige Quellcodepaket nicht.

Das große Qwen-Modellgewicht liegt in der App und kann beim Bauen daraus übernommen oder mit dem ausdrücklich aufgerufenen Buildskript heruntergeladen werden. Das deutsche Vosk-Modell und die native Intel-llama-Laufzeit sind bereits im Quellcodepaket enthalten.

Die ursprünglichen Übergabedokumente und der Prüfbericht beschreiben den jeweiligen Entwicklungsstand. Hinweise auf eine damals noch ausstehende Veröffentlichung sind historische Angaben. Für die tatsächliche Verfügbarkeit gelten die Releases dieses Repositorys.

Die App prüft spätere Updates über den gesonderten Mac-Kanal im bestehenden **StorageLab-Downloads**-Repository. Ein Release hier richtet diesen Updatekanal noch nicht automatisch ein. Windows-Installer werden auf dem Mac abgelehnt.

## Rechte und Herkunft

© 2026 Franz Niklaus. Kostenloses Nutzen, Kopieren und kostenloses Weitergeben ist nach der beigefügten [StorageLab-Erlaubnis](StorageLab-Lizenz.txt) gestattet. Copyright und Lizenzhinweise erhalten. Für Fremdkomponenten gelten ihre eigenen Lizenzen; Hinweise sind im Quellcode und in der App enthalten.

[Windows-Ausgabe](https://github.com/wampenwalther-glitch/StorageLab-Downloads/releases/latest) · [Web-Demo](https://wampenwalther-glitch.github.io/StorageLab-Demo/)
