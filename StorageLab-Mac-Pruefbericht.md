# StorageLab 0.9.1 macOS – Prüfbericht

13. Oktober 2026 · Intel x86_64 · macOS 13.7.8 · 8 GB RAM.

Grundlage: StorageLab-Quellcode-0.9.1-Mac-Uebergabe.zip. Die 89 Dateien im Originalmanifest stimmen mit ihren SHA256-Prüfsummen überein. Die unveränderte Windows-Quelle bleibt im ursprünglichen ZIP erhalten.

## Prüfergebnisse

| Funktion | Prüfung und Ergebnis | Grenze |
|---|---|---|
| Eigenständige App | PyInstaller-Build, Start ohne separates Python, native Intel-Laufzeit, lokale Signaturprüfung | Nicht Apple-notarisiert; andere Macs nicht geprüft |
| Scan, Abbruch, Grenzen, Links, Unicode | Bestehende Tests bestanden; realer Scan von drei eigenen Dateien über Oberfläche | Keine persönlichen Ordner gescannt; macOS-Ordnerberechtigungen nicht umfassend geprüft |
| Suche, Dateifilter, Dubletten, Analyse | Tests bestanden; Suche und Dubletten über Oberfläche ausgeführt | Sehr große reale Datenbestände nicht geprüft |
| ZIP-/Office-Containerprüfung | Tests für CRC, Defekt, Abbruch und Sicherheitsgrenzen bestanden | Keine inhaltliche Office- oder Virenprüfung |
| Organizer | Vorschau, Auswahl, Freigabe, Verschieben und Rückgängig über Oberfläche ausgeführt | Nur eigene Testdateien; nur innerhalb desselben Volumes |
| Schutz vor Überschreiben | macOS renamex_np mit RENAME_EXCL; vorhandene Ziele bleiben erhalten, veränderte Quelle und Links abgelehnt | Keine vollständige Absicherung gegen absichtliche gleichzeitige Manipulation aller übergeordneten Ordner behauptet |
| NAS und Backup | Backupvergleich mit SHA256 und Start/Stop der Überwachung über Oberfläche; vorhandene Vergleichstests bestanden | Eigene lokale Ordner; kein reales NAS verbunden; der 15-Minuten-Intervall wurde nicht 15 Minuten abgewartet |
| Laufwerke und RAM | Native psutil-Metadaten, Systemvolume und Arbeitsspeicher ermittelt; Laufwerksdialog geöffnet | Keine zusätzliche externe Festplatte geprüft |
| Autostart | LaunchAgent-Liste über Oberfläche; Ausschalten/Wiederherstellen mit simuliertem launchctl an eigenen Testkonfigurationen | Keine echten Benutzerjobs verändert; Betriebssystem-Anmeldeobjekte über System Settings |
| Regelassistent | Bestehende Tests und unveränderte Aufgaben-/Erklärungsfunktionen | Keine generative KI im Regelmodus |
| Lokales LLM | Qwen3.5-2B Q4_K_M, b11558 Intel-Mac-Laufzeit; echte Wissensantwort und Suchklassifikation; Suchauftrag auch mit App-verpackter Laufzeit ausgeführt | Kleines Modell kann trotz Vorgaben unzutreffende Aussagen erzeugen. Suchauftrag ca. 43–52 Sekunden auf diesem Mac |
| Diktieren | Vosk geladen, Core-Audio-Mikrofone gelistet; künstliche Aufnahme „Suche nach Rechnung“ als „die suche nach rechnung“ erkannt | Echte Mikrofonaufnahme, TCC-Freigabe, menschliche Sprache und Ende-zu-Ende-Senden noch vom Nutzer prüfen |
| Online-KI | OpenAI/Anthropic/Gemini-Code erhalten; Nutzlasten für alle drei Anbieter erstellt | Keine API-Schlüssel verwendet, aktuelle Kontofreigaben/Modellverfügbarkeit nicht live bestätigt |
| Foldy und Ton | Oberfläche/Animationstimer laufen ohne Tk-Callbackfehler; lokaler Ton abgespielt; Stummschaltung geprüft | Subjektive Tonqualität und alle Gesten nicht vollständig manuell bewertet |
| Teeküche | Entdeckung, sechs Ritualschritte, Mehrfachklicks, Schließen/Wiederöffnen und Rückverwandlung über Oberfläche geprüft | Timer für diesen Test verkürzt beziehungsweise vorgespult; ausgelieferter Code bleibt bei 60/300 Sekunden |
| Einstellungen und Dialoge | Eigene Testeinstellungen statt persönlicher Konfiguration; Laufwerke, Autostart, Updates und Über-Dialog geöffnet | Wiederanmeldung und alle Berechtigungskombinationen nicht geprüft |
| Updates | Mac-spezifischer Manifestname, Architekturprüfung und Ablehnung von Windows-Installer/arm64 getestet | Kein Mac-Release vorhanden; realer Mac-Update-Download/Installation deshalb noch nicht möglich |
| Oberfläche | Eigenes Tk-/Cocoa-Fenster gerendert und auf Anordnung/Lesbarkeit geprüft | Keine vollständige Prüfung aller Bildschirmgrößen; Foldy liegt in eigenen transparenten Fenstern |

34 automatisierte Tests bestanden. Der Oberflächentest meldete keine Tk-Callbackfehler. Tests verwendeten ausschließlich eigene Dateien. Es wurden keine persönlichen Dateien verschoben, kein echter Autostart verändert und keine Chatdaten zu einem Online-Anbieter gesendet.

## Laufzeiten und Herkunft

- Python 3.12.14 und Tcl/Tk 9.0.4 aus der verfügbaren lokalen Build-Laufzeit.
- PyInstaller 6.22.3, Vosk 0.3.44, sounddevice 0.5.6, psutil 7.2.2, NumPy 2.5.4; vollständige Liste im Quellcodepaket.
- llama.cpp b11558: https://github.com/ggml-org/llama.cpp/releases/tag/b11558
- Modell: https://huggingface.co/bartowski/Qwen_Qwen3.5-2B-GGUF/tree/7d26695454df6de5fbcce2e58681e62dae06ce43
- Modell-SHA256: 57a1085840f497d764a7fc5d346922dbde961efb54cc792ea81d694fd846a1d8
- Windows-Basis: https://github.com/wampenwalther-glitch/StorageLab-Downloads/releases/tag/v0.9.1

## Verteilung

Die App enthält beide Offline-Modelle und alle erforderlichen Mac-Laufzeiten. Das DMG ist zur lokalen Installation und Weitergabe vorbereitet. Öffentliche Veröffentlichung, Developer-ID-Signierung und Apple-Notarisierung wurden nicht vorgenommen.
