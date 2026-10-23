---
name: 5-8-zusammenfassung
version: 1.1.0
description: >
  Gliedert ein Dokument als 5-8-Zusammenfassung: zwei Ebenen mit je 5 bis 8 disjunkten,
  erschöpfenden Themen, abgelegt als Memo nach dem Skill "memo". Verwenden, wenn der User
  eine "5-8-Zusammenfassung" oder eine strukturierte, hierarchische Zusammenfassung verlangt
  oder ein Dokument in 5-8 Themen gliedern, zusammenfassen oder strukturieren lassen will.
---

# Skill: 5-8-Zusammenfassung

## Zweck

Erzeugt eine zweistufig hierarchische Zusammenfassung eines Dokuments, bei der die Gliederung selbst eine inhaltliche Aussage über das Dokument darstellt. Die Zwangsstruktur "5 bis 8 Themen pro Ebene" erzwingt echte Abwägung und tieferes Verständnis statt linearer Reproduktion.

---

## Kernprinzip

Vor jeder Gliederungsentscheidung wird das Dokument vollständig erfasst und reflektiert, **wie viele** Themenbereiche die richtige Granularität liefern. Die Wahl muss zwischen 5 und 8 liegen — der Korridor zwingt zur Begründung. Das Rationale bleibt intern und erscheint **nicht** im Endprodukt.

---

## Pflicht-Workflow

1. **Dokument vollständig erfassen** — Inhalt, Struktur, Schwerpunkte
2. **Hauptebene gliedern** — 5 bis 8 Themenbereiche identifizieren, intern begründen warum genau diese Anzahl
3. **Hauptebene numerieren** — `1)`, `2)`, …, `n)`
4. **Rekursiv jeden Hauptpunkt zerlegen** — wieder 5-8 Unterpunkte, intern begründet
5. **Unterebene numerieren** — `1.1)`, `1.2)`, …
6. **Ausformulieren**:
    - Pro Hauptpunkt: kurze Einleitung/Übersicht
    - Pro Unterpunkt: prägnante Wiedergabe des Wesentlichen
7. **Als Memo ausgeben** nach dem Skill `memo` (Abschnitt *Anwendung — ein Memo anlegen*):
    - kein YAML-Frontmatter, Header-Block mit `**Datum:**` und `**Status:** Zusammenfassung`
    - Datei `NN <Titel> — 5-8-Zusammenfassung.md` in den `@Memo/`-Ordner des aktuellen Projekts
    - Pfad dem User als Link nennen

---

## Gliederungsregeln

### Hauptebene (1 bis n)

- Mindestens 5, höchstens 8 Themenbereiche
- Themen müssen **disjunkt** sein (keine inhaltliche Überlappung)
- Themen müssen **erschöpfend** sein (decken das Dokument ab)
- Reihenfolge folgt der inneren Logik des Dokuments, nicht zwingend der Originalreihenfolge

### Unterebene (1.1 bis n.m)

- Pro Hauptpunkt wieder 5 bis 8 Unterpunkte
- Gleiche Disjunktheits- und Vollständigkeitsregel
- Falls ein Hauptthema sachlich weniger als 5 Unterpunkte hergibt: Hauptgliederung überdenken

### Rationale

- Wird **intern** durchdacht (warum 6 und nicht 5 oder 7?)
- Erscheint **nie** im Endprodukt
- Dient nur der Qualitätssicherung der Gliederung

---

## Format-Konvention im Memo

```markdown
## 1) Erstes Hauptthema

Kurze Einleitung/Übersicht zu Hauptthema 1 …

### 1.1) Erster Unterpunkt

Wesentliches in eigenen Worten …

### 1.2) Zweiter Unterpunkt

…
```

- Hauptpunkte: `## n)` mit schließender Klammer
- Unterpunkte: `### n.m)` mit schließender Klammer
- Einleitung pro Hauptthema: 1-3 Sätze Fliesstext
- Unterpunkte: 2-5 Sätze, das Wesentliche

---

## Abgrenzung zu anderen Zusammenfassungsformen

|Form|Wann|
|---|---|
|5-8-Zusammenfassung|Wenn User explizit danach fragt oder strukturierte, navigierbare Übersicht braucht|
|Lineare Zusammenfassung|Bei kurzen Texten, wo Hierarchie übertrieben wäre|
|Bullet-Liste|Bei reinen Faktensammlungen ohne thematische Struktur|

---

## Checkliste vor Ausgabe

- [ ] Dokument vollständig erfasst
- [ ] Hauptebene: 5 bis 8 Themen, intern begründet
- [ ] Jede Unterebene: 5 bis 8 Punkte, intern begründet
- [ ] Numerierung `n)` und `n.m)` konsistent
- [ ] Rationale **nicht** im Output
- [ ] Pro Hauptthema kurze Einleitung
- [ ] Pro Unterpunkt prägnante Inhaltswiedergabe
- [ ] Skill `memo` für Format und Dateiname angewendet
- [ ] Datei im `@Memo/`-Ordner des Projekts gespeichert (und committet, falls Git-Repo)
- [ ] Pfad dem User als Link genannt
