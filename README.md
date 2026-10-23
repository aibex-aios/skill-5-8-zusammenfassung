# skill-5-8-zusammenfassung

Paket von AIbex AIOS mit dem Skill `5-8-zusammenfassung`, Version 1.2.0: gliedert ein Dokument zweistufig in je 5 bis 8 disjunkte, erschöpfende Themen und legt das Ergebnis als Memo im `@Memo/`-Ordner des Projekts ab.

## Holen

**Voraussetzung:** AIbex AIOS v0.4 ist installiert, und der Vault oder das Projekt ist mit `aios --activate v0.4.<n>` aktiviert.

```bash
aios --fetch skill-5-8-zusammenfassung
```

Das Paket braucht `skill-memo` (`~=6.0`); `aios --fetch` holt es mit. Der Skill wirkt **ab dem nächsten Chat** im Projekt.

## Aufruf

Im Chat etwa „Mach eine 5-8-Zusammenfassung von `<dokument>`" oder `/5-8-zusammenfassung <dokument>`. Das Ergebnis ist ein Memo `NN <Titel> — 5-8-Zusammenfassung.md` in `@Memo/`.

Ab 1.2.0 kann ein Aufrufer, ein anderer Skill oder du im Chat, **Vorgaben** machen, jede einzeln: **Zielordner** (statt `@Memo/`, wird bei Bedarf angelegt), **Nummer** (statt eigener Vergabe), **Titel** und **nicht committen**. Beispiel: „Mach eine 5-8-Zusammenfassung von `<dokument>`, Zielordner `@Summary/`, Nummer `07`, Titel `Probe`, nicht committen". Eine bestehende Datei wird nie überschrieben.

## Lizenz

Apache License 2.0 (`LICENSE`), Rechteinhaber AIbex KG (`NOTICE`). Die Marken „AIbex" und „AIbex AIOS" sind nicht mitlizenziert.
