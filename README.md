# SI2 – Telemedicínský systém pro srdeční selhání

Sdílený repozitář týmu pro zdrojové soubory diagramů, text dokumentu a prezentaci.

| Role | Bloky systému |
|---|---|
| R1 – Pacient & UX | Pacientská aplikace, senzory, webový portál, GUI |
| R2 – Architekt & data | WEB API, databáze, celková architektura |
| R3 – Integrace & provoz | Integrátor pro NIS, HL7 FHIR, DevOps |

## Struktura

```
diagramy/
  uc/          UC diagramy (zdrojové soubory .drawio / .puml)
  stavove/     stavové diagramy
  komponenty/  component diagram
  db/          ER diagram
  gui/         mockupy
dokument/      kapitoly dokumentu v Markdownu (podklady pro sdílený dokument)
podklady/      rešerše, FHIR/LOINC tabulky, poznámky
prezentace/    zdroje prezentace
```

## Klíčové termíny

| Fáze | Hotovo do | Kontrolní bod |
|---|---|---|
| 0 Rozjezd | 8. 10. | nahlášení choroby |
| 1 Požadavky a doména | 22. 10. | – |
| 2 UC a stavové diagramy | 5. 11. | – |
| 3 Architektura, komponenty, DB | 12. 11. | kontrola designu a rozdělení bloků |
| 4 GUI, implementace, testy, nasazení | 26. 11. | kontrola postupu |
| 5 Kompletace a prezentace | 17. 12. (finál dokumentu 10. 12.) | prezentace, odevzdání |
| 6 Připomínky | 7. 1. 2027 | zápočet |

Pravidla práce viz [CONTRIBUTING.md](CONTRIBUTING.md).
