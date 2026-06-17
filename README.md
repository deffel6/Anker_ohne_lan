# Anker Solix Display – ESP32-C3 Firmware

Web-Flasher für die Anker Solix Display Firmware (Version 1.0.2), basierend auf [ESP Web Tools](https://esphome.github.io/esp-web-tools/).

## Hardware

- ESP32-C3 (z.B. ESP32-2424S012)
- 1.28" GC9A01A Round Display, 240×240
- Anker Solix Cloud API Integration

## Flashen

1. Repo per GitHub Pages veröffentlichen (Settings → Pages → Branch `main`, Ordner `/`)
2. Seite mit Chrome oder Edge öffnen (Web Serial API erforderlich)
3. Board per USB anschließen
4. "Firmware installieren" klicken, Port auswählen

## Firmware-Dateien

| Datei | Offset | Beschreibung |
|---|---|---|
| `anker_display_1.0.2.ino.bootloader.bin` | 0x0 | Bootloader |
| `anker_display_1.0.2.ino.partitions.bin` | 0x8000 | Partitionstabelle |
| `boot_app0.bin` | 0xe000 | OTA-Auswahl |
| `anker_display_1.0.2.ino.bin` | 0x10000 | Hauptprogramm |

Alternativ liegt unter `firmware/anker_display_1.0.2.ino.merged.bin` eine bereits zusammengeführte Komplettdatei (ab Offset 0x0).

## Build-Einstellungen (Arduino IDE)

- Board: ESP32C3 Dev Module
- Upload Speed: 921600
- CDC On Boot: Enabled
- CPU Frequency: 160MHz
- Flash Frequency: 80MHz
- Flash Mode: QIO
- Flash Size: 4MB
- Partition Scheme: Default
