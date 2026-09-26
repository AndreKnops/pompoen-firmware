# Pompoen — firmware releases

Publieke releases-repo voor de gecompileerde firmware van het pompoen-project
(DFRobot ESP32-S3 AI Camera / DFR1154), gebaseerd op de vogelhuisje-camera-firmware.
Bevat alleen het gecompileerde `.bin`-bestand en een versienummer, geen broncode — de
firmware-bronrepo blijft privé.

Bedoeld om door het board zelf te worden uitgelezen (via `GITHUB_PATH` in `appGlobals.h`),
zowel voor automatische OTA-updates als voor het verse-SD-kaart-downloadmechanisme:
- `version.txt` — huidige versienummer (vergelijkt het board met zijn eigen `APP_VER`)
- `firmware.bin` — bijbehorend, klaar-om-te-flashen app-binary
- `data/MJPEG2SD.htm`, `data/common.js` — de webinterface-bestanden; worden door het board
  gedownload als ze nog niet op de SD-kaart staan (verse kaart), en na een OTA-update
  automatisch opnieuw gedownload zodat de webinterface in sync blijft met de firmware
- `rollback/` — de vorige release (firmware.bin + version.txt), voor de "Roll Back"-knop

Bij elke nieuwe release worden al deze bestanden hier overschreven, met hetzelfde versienummer.
