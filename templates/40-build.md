---
stage: build
owner: build
status: in_arbeit            # offen | in_arbeit | fertig | uebersprungen
revision: 1
created: <JJJJ-MM-TTThh:mm>
updated: <JJJJ-MM-TTThh:mm>
input: 20-plan.md@<rev>, 30-design.md@<rev>
git: <ja | nein>             # aus 00-maquette.md übernommen
---

# Build <Kürzel>: <Arbeitstitel>

_Ergebnis der Stufe build. Der Code liegt in `vcode/`. Diese Datei ist das Bautagebuch: ein Eintrag je Slice, in Reihenfolge, nie rückwirkend geändert._

## Starten

<!-- Drei Zeilen, die ein Nicht-IT-Nutzer ausführen kann. Wird von harden und brief benutzt. -->

```
<Befehl 1, z. B. cd vcode>
<Befehl 2, z. B. python -m http.server 8000>
<Adresse, z. B. http://localhost:8000>
```

## Slices

<!-- Je Slice ein Block. Status: fertig | teilweise | ausgelassen. Smoke-Check = das Akzeptanzkriterium aus 20-plan.md §10, ausprobiert, nicht angenommen. Commit nur mit Git. -->

### S1 — <Titel aus 20-plan.md>
- **Status:** <fertig | teilweise | ausgelassen>
- **Smoke-Check:** <Akzeptanzkriterium> → <bestanden | nicht bestanden: <…>>
- **Commit:** <Hash | — (kein Git)>
- **Abweichung vom Plan:** <keine | <was und warum>>
- **Dauer:** <Minuten>

### S2 — <…>
- …

## Beim Bauen entdeckte Anforderungen

<!-- Alles, was der Plan nicht hatte und der Code gebraucht hat. IDs laufen aus 20-plan.md weiter (cF-neu-1 …, bis brief sie einordnet). Nie zurück in 10 oder 20 schreiben (Schreibregel 3). -->

| ID | Anforderung | Entdeckt in Slice | Umgesetzt? |
| --- | --- | --- | --- |
| cF-neu-1 | <…> | S<n> | <ja | nein> |

## Bekannte Lücken

<!-- Was bewusst weggelassen oder gestubbt wurde. Ehrlich — harden prüft genau hier, brief macht daraus die Kann-nicht-Liste. -->

- <…>

## Offene Fragen

- **Q<n>** — <…>

## Notizen (Mensch)

<!-- Tabu für alle Skills. Wird bei jeder Neuschreibung unverändert übernommen. -->
