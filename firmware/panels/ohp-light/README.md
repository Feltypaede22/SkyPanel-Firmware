# OHP LIGHT

- Quellcode: `firmware/firmware-ohp-light/OHP_LIGHT/`
- Mapping: `config/mappings/ohp_light.json`
- Hardware: `config/hardware/ohp_light.json`
- Pin-Quelle: `Overhead Lights.mfmc` / `Overhead Lights Fenix.mcc`
- Profil: `ohp_light`
- Controller: Raspberry Pi Pico
- Build: `pio run -e pico` im Ordner `firmware/firmware-ohp-light`
- Inhalt: EXT LT · INT LT · SIGNS · Anti-Ice/APU/Press-Kontakte · Annunciators · AN/BL

## Pins (kurz)

| Funktion | Pins |
|---|---|
| Buttons GPIO | 0,1,2,6,7,9,21,22,26,27,28 + Strobe 3/4, Land 10/13, Nav 11, Nose 14/15 |
| Input 74HC165 | Latch 19, Clock 18, Data 20 (2 Module) |
| LED 74HC595 | Latch 12, Clock 17, Data 16 (2 Module) |
| PWM | AN=8, BL=5 |
