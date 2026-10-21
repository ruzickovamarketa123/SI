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

## zmeny market ve vojtove praci 21.10.
* opravené měření a NIS: do `databaze.tex` jsem doplnila databázový trigger, který po vložení nebo změně měření či dotazníku nastaví `sync_status = pending`. Oprava tak znovu dojde do NIS a účet WEB API pořád do sloupců integrátoru nezapisuje. Navazuje na to text ve `web-api.tex` a `design-integrator.tex`.
* Administrace integrátoru: do CMP-01 jsem přidala rozhraní „Administrace integrátoru (HTTPS, jen interní síť)“. Doplnila jsem i `component.tex`, tabulku rolí a UC integrátoru.
* Stav spojení s NIS: `integrator_settings` má nově čtyři sloupce (`nis_status`, `outage_since`, `consecutive_failures`, `last_check_at`). Jsou v ER diagramu, v tabulce tabulek i ve výčtech. Databáze má dál 12 tabulek.
* Endpoint /devices jsem přejmenovala na /push-registrations a ?status=open nahradila ?evaluated=false.
* V ukázce JSON jsou teď identifikátory ve tvaru UUID.
* Notifikace se během jednoho výpadku neopakují. Teď to tak říká FR-INT-09 i text k SD-06.
* Smoke testy jsou pojmenované všude stejně a kontrola NIS ověřuje i zdroj Practitioner.

