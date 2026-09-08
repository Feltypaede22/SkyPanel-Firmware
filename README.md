# SkyPanel-Firmware

Nur **Arduino / Pico Panel-Firmware** (HEX / UF2) für den SkyPanel Firmware Updater.

## Struktur (nicht ändern)

```
firmware/manifest.json
firmware/panels/<slug>/<datei>.hex|.uf2
firmware/panels/<slug>/manifest.json
```

SkyPanel Firmware Updater liest:

- Manifest: `https://raw.githubusercontent.com/Feltypaede22/SkyPanel-Firmware/main/firmware/manifest.json`
- Dateien: `firmware/panels/<slug>/<filename>`

## Neue Firmware veröffentlichen

1. HEX/UF2 unter `firmware/panels/<slug>/` ablegen
2. Version in `firmware/manifest.json` und Panel-Eintrag erhöhen (`version` + Katalog-`version`)
3. Push auf `main`

Oder aus dem Shop-Repo:

```bash
python "ped software/scripts/publish_skypanel_update.py" --firmware --manifest-version 2026.09.09
```

## Repo

https://github.com/Feltypaede22/SkyPanel-Firmware
