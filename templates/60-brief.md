---
stage: brief
owner: brief
status: in_arbeit            # offen | in_arbeit | fertig | uebersprungen
revision: 1
created: <JJJJ-MM-TTThh:mm>
updated: <JJJJ-MM-TTThh:mm>
input: 10-seed.md@<rev>, 20-plan.md@<rev>, 40-build.md@<rev>, 50-harden.md@<rev>
---

# Brief <Kürzel>: <Arbeitstitel>

_Ergebnis der Stufe brief und Ausgang der Maquette. Teil 1 ist für die Vorführung, Teil 2 für die Entscheidung danach, Teil 3 der Retrofit-Seed für das Concept Authoring Manifest (Path B → Phase 1)._

## Teil 1 — Demo-Skript (3 Minuten)

<!-- Für den Menschen, der vorführt. Keine Technik, keine Skill-Namen. -->

- **Das Problem in einem Satz:** <aus 10-seed.md §1, in den Worten des Sponsors>
- **Für wen:** <der konkrete Mensch aus Q3>
- **Klickpfad:**
  1. <Starten: Befehl/Adresse aus 40-build.md>
  2. <Schritt — was man sieht — was man sagt>
  3. <…>
- **Der Moment, auf den es ankommt:** <die eine Interaktion, die den Nutzen zeigt>
- **Was man nicht anklicken sollte:** <Einschränkungen aus 50-harden.md §4>

## Teil 2 — Kann / Kann bewusst nicht

| Kann | Kann bewusst nicht | Warum nicht |
| --- | --- | --- |
| <…> | <aus 20-plan.md §7, 40-build.md „Lücken", 50-harden.md §5> | <Umfang | Zeit | Daten | Entscheidung offen> |

**Was diese Maquette beweist:** <ein Satz>
**Was sie nicht beweist:** <ein Satz — ehrlich, damit niemand einen Prototyp für ein Produkt hält>

## Teil 3 — Retrofit-Seed

<!-- Der Übergabepunkt ins Manifest. Alles, was 10, 20, 40, 50 gelehrt haben, konsolidiert. Kandidaten bleiben unratifiziert; Phase 1 (Grilling) ratifiziert und nummeriert um. -->

### Aktualisierte Kandidaten-Anforderungen

<!-- Aus 20-plan.md §3–5 plus 40-build.md „entdeckte Anforderungen", umnummeriert in eine Reihe. Spalte „Status in Maquette": gezeigt | teilweise | nicht gezeigt. -->

| ID | Anforderung | Herkunft | Status in Maquette |
| --- | --- | --- | --- |
| cF-1 | <…> | seed | gezeigt |
| cF-<n> | <…> | build | teilweise |

### Gemeinsame Sprache

<aus 20-plan.md §2, ergänzt um Begriffe aus build/harden — Startpunkt für CONTEXT.md>

### Entschiedene Fragen

<aus 20-plan.md §8 — bleiben als ADR-Seeds erhalten>

### Offene Fragen

<!-- Alle Q aus 10, 20, 40, 50, die noch offen sind, in einer Liste. Das ist die Startmunition für das Grilling. -->

- **Q<n>** — <…>

### Riskanteste Annahme — Stand nach der Maquette

- **Annahme (aus 10-seed.md §9):** <…>
- **Was die Maquette dazu gezeigt hat:** <bestätigt | geschwächt | nicht berührt — mit Beobachtung>
- **Q5 Beobachtung:** <Hat jemand die Maquette ohne Hilfe benutzt? Was hat überrascht? — oder „noch nicht beobachtet: nächster Test">

## Teil 4 — Nächster Schritt

- **Empfehlung:** <Discovery Sprint (Manifest Phase 1 mit diesem Seed) | riskanteste Annahme testen (siehe oben) | zweite Maquette-Runde mit Scope <…> | Ende — Idee geparkt, weil <…>>
- **Wer entscheidet:** <Sponsor aus 00-maquette.md>
- **Wann:** <…>

## Notizen (Mensch)

<!-- Tabu für alle Skills. Wird bei jeder Neuschreibung unverändert übernommen. -->
