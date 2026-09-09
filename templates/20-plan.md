---
stage: plan
owner: plan-board
status: in_arbeit            # offen | in_arbeit | fertig | uebersprungen
revision: 1
created: <JJJJ-MM-TTThh:mm>
updated: <JJJJ-MM-TTThh:mm>
input: 10-seed.md@<rev>
---

# Plan <Kürzel>: <Arbeitstitel>

_Ergebnis der Stufe plan-board. Struktur folgt dem Concept Authoring Manifest §0–8 in Modell-Tiefe: Abschnitte, die für die Maquette nicht relevant sind, bleiben stehen und tragen den Vermerk „für die Maquette nicht relevant" — so ist der spätere Retrofit ein Diff, kein Neuanfang._

## 0. Synthese-Kontext

- **Pfad:** B (Retrofit) — die Maquette wird gebaut, das Konzept danach extrahiert
- **Abhängigkeiten:** <andere Dokumente/Systeme, die der Prototyp voraussetzt, oder „keine">
- **Reichweite:** <was aus diesem Plan allein gebaut werden kann>

## 1. Zweck

<aus 10-seed.md §1, nach Grilling-light geschärft>

## 2. Gemeinsame Sprache

<aus 10-seed.md §4, ergänzt um Begriffe aus dem Grilling>

## 3. Funktionale Anforderungen (cF)

<!-- Übernommen aus 10-seed.md §7, im Grilling-light geprüft: gestrichen, geschärft, ergänzt. IDs bleiben stabil; neue IDs laufen weiter (cF-9 …). Jede Zeile nennt den Slice, der sie zeigt. -->

| ID | Anforderung | Slice |
| --- | --- | --- |
| cF-1 | <…> | S1 |

## 4. Nutzerinteraktion (cU)

| ID | Anforderung | Slice |
| --- | --- | --- |
| cU-1 | <…> | S1 |

## 5. Nicht-funktionale Anforderungen (cNF)

| ID | Anforderung | Slice |
| --- | --- | --- |
| cNF-1 | <…> | — |

## 6. Integrationspunkte

<Datenquellen, Dateien, APIs, die der Prototyp wirklich anspricht — oder „für die Maquette nicht relevant: alles synthetisch">

## 7. Nicht im Umfang

<!-- Explizit, damit build nicht abschweift und brief die Kann-nicht-Liste hat. -->

- <…>

## 8. Entschiedene Fragen

<!-- Aus 10-seed.md §8 und dem Grilling-light. Jede Q bekommt eine Einzeiler-Entscheidung. Offen gebliebene Fragen wandern unverändert nach §11. -->

| Frage | Entscheidung | Begründung |
| --- | --- | --- |
| Q1 | <…> | <…> |

## 9. Review-Board

<!-- Drei Rollen lesen nacheinander. Jede Rolle: Kleinentscheidungen selbst getroffen (Liste), echte Weichen dem Nutzer vorgelegt (Frage → Antwort). Idee aus gstack autoplan (© 2026 Garry Tan, MIT License, siehe `LICENSES/gstack-MIT.txt`), ohne DX-Rolle und ohne unbegrenzte Tiefe. -->

### Produkt
- **Selbst entschieden:** <…>
- **Weiche vorgelegt:** <Frage> → <Antwort des Nutzers>

### Design
- **Selbst entschieden:** <…>
- **Weiche vorgelegt:** <…>

### Engineering
- **Selbst entschieden:** <Stack, Datenhaltung, Startbefehl — so einfach wie möglich>
- **Weiche vorgelegt:** <…>

## 10. Slices

<!-- 3–5 vertikale Slices, jeder für sich vorzeigbar. S1 ist der Scope-Satz aus 10-seed.md §2 Q4. Jeder Slice hat genau ein Akzeptanzkriterium, das build per Smoke-Check prüft. -->

| Slice | Zeigt | Akzeptanzkriterium | Anforderungen |
| --- | --- | --- | --- |
| S1 | <…> | <ein Satz, prüfbar> | cF-1, cU-1 |
| S2 | <…> | <…> | <…> |

**Technische Eckdaten:** <Stack, Startbefehl, Datenquelle — drei Zeilen, kein Architekturkapitel>

## 11. Offene Fragen

<!-- Fortlaufende Nummerierung aus 10-seed.md. -->

- **Q<n>** — <…>

## 12. Gate

- **Freigabe durch Nutzer:** <ja, am <hh:mm> | mit Änderungen: <…> | nein — nochmal>
- **Überarbeitungsrunden:** <0 | 1>

## Notizen (Mensch)

<!-- Tabu für alle Skills. Wird bei jeder Neuschreibung unverändert übernommen. -->
