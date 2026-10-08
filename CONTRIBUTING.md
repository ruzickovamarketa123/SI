# Pravidla práce v repozitáři

## Pojmenování souborů

`<TYP>-<číslo>-<blok-nebo-téma>.<přípona>` – malá písmena, bez diakritiky, slova oddělená pomlčkou.

| Typ | Příklad |
|---|---|
| UC diagram | `UC-01-pacientska-aplikace.drawio` |
| Stavový diagram | `ST-03-zivotni-cyklus-mereni.drawio` |
| Component diagram | `CMP-01-system.drawio` |
| ER diagram | `DB-01-er-diagram.drawio` |
| Mockup | `GUI-04-portal-detail-pacienta.png` |

Číslování UC: 01 pacientská aplikace (R1), 02 webový portál (R1), 03 WEB API (R2), 04 integrátor pro NIS (R3).
Číslování stavových diagramů: 01 klinický stav, 02 dotazník (R1), 03 životní cyklus měření, 04 alert (R2), 05 synchronizace pacienta, 06 spojení s NIS (R3).

Export do `export/` se stejným názvem a příponou `.png` (300 dpi) nebo `.svg`. Popisek obrázku v dokumentu: „Obrázek N – název“, číslování průběžné přes celý dokument.

## Větve a commity

- `main` je vždy odevzdatelná verze; přímo do ní se necommituje.
- Každý pracuje ve větvi `r1/...`, `r2/...`, `r3/...` (např. `r3/pozadavky-integrator`).
- Merge request do `main` schvaluje další člen v pořadí revizí **R1 → R2 → R3 → R1** (R1 reviduje práci R3, R2 práci R1, R3 práci R2).
- Zprávy commitů česky v rozkazovacím způsobu: `Přidej UC diagram integrátoru`.

## Před koncem každé fáze

1. Vlastní výstupy jsou v `main` přes schválený merge request.
2. Exporty diagramů jsou aktuální.
3. Projitý „Kontrolní checklist povinných minim“ z plánu projektu.
