# ESO P1 data model vs DSMR 5.0.2

Lithuanian grid operator **ESO** smart meter **P1 port** data model, cleaned up and compared with the Dutch **DSMR 5.0.2 P1 Companion Standard** that ESO declares it follows.

## Files

| File | Content |
|---|---|
| `P1_duomenu_modelis_v32.xlsx` | ESO P1 data model. **Data profiles** – every OBIS code with ESO sets (Standard / Extended / Maximum), English and Lithuanian description, unit, example value with the precision used, value format (linked) and DSMR 5.0.2 status. **DSMR 5.0.2** – value format codes, COSEM data types, and one table of all electricity objects (DSMR + ESO extensions) with Class ID, attribute, tag, format and unit. **Telegram standard / extended / maximum** – ESO example telegrams. |
| `P1_ESO_vs_DSMR_coverage_v1.xlsx` | Which DSMR 5.0.2 objects ESO sends in which telegram set, with findings. |

## Key findings

- ESO **Standard** set omits export (generation) data that DSMR always includes: `2.8.1`, `2.8.2`, `2.7.0`, `22/42/62.7.0`.
- ESO **Maximum** set omits total power `1.7.0` / `2.7.0` (uses per-phase values and own aggregates instead).
- `1-0:52.36.0` is marked Standard in the ESO profile table but is missing from the ESO Standard example telegram.
- Not sent by ESO at all: `1-3:0.2.8`, `0-0:96.14.0`, `0-0:96.7.9`, `1-0:99.97.0`.
- 72 ESO objects are extensions outside DSMR 5.0.2; their Class ID / tag are inferred (ESO does not publish them).

## Sources

- ESO FAQ – P1 sąsaja: https://www.eso.lt/duk/p1-sasaja-196#ffaq694
- ESO original file: https://www.eso.lt/download/585550/p1%20duomenu%20modelis_v2.xlsx
- DSMR 5.0.2 P1 Companion Standard (Netbeheer Nederland, 2016-02-26): https://www.netbeheernederland.nl/publicatie/dsmr-502-p1-companion-standard
