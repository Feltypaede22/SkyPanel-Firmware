# SkyPanel Firmware (GitHub)

Firmware-Dateien für den Shop-Download und den **SkyPanel Firmware Updater**.

## Struktur (GitHub-Ordner: `firmware/`)

Der **Hauptordner heisst `firmware/`** — darin liegen Manifest, Panel-Dateien und Dokumentation.
Der Unterordner **`panels/`** enthält die einzelnen Paneele (je Slug ein Ordner mit `.hex`/`.uf2`).

```
firmware/
  manifest.json
  docs/                  ← PDF-Anleitungen + Screenshots
  panels/                ← Panel-Firmware (RMP, ACP, …)
```

**SkyPanel funktioniert nur mit Fenix A320 (MSFS).**

## Struktur (Detail)

```
firmware/
  manifest.json              ← Index (Slug, Titel, Version, Dateiname)
  README.md
  panels/
    rmp/RMP.hex
    acp/ACP.hex
    atc-tcas/ATC-TCAS.hex
    ped-wxr/PED-WXR.hex
    ped-ecam-sw/PED-ECAM-SW.hex
    mip-hyd-prs/MIP-HYD-PRS.hex
    chrono/Chrono.hex
    hyd-fuel/Hyd Fuel.uf2
    ohp-light/OHP_LIGHT.uf2
```

Jeder Panel-Ordner enthält:

- `{filename}` — die Firmware-Datei
- `manifest.json` — Metadaten (Profil, Controller)
- `README.md` — Kurzinfo

## Workflow

1. Neue `.hex` / `.uf2` unter `firmware/panels/<slug>/` ablegen (**gleicher Dateiname ersetzt die alte Version**).
2. `manifest.json` → `version` und ggf. Panel-`version` anpassen.
3. Nach `git push` auf [Feltypaede22/a320-shop.ch](https://github.com/Feltypaede22/a320-shop.ch):
   - **Shop:** Admin → Downloads → «Firmware von GitHub sync»
   - **Desktop:** SkyPanel Firmware Updater → «Updates prüfen»

## Shop-Sync

Der Server lädt `manifest.json` und die Firmware-Dateien von GitHub (`main`-Branch).
Pro Panel (`slug`) gibt es **genau einen** Download-Eintrag — alte Datei wird beim Sync gelöscht.

Umgebungsvariable auf dem VPS (optional):

`FIRMWARE_GITHUB_REPO=Feltypaede22/a320-shop.ch`
