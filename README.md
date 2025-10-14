# Liste Sozialleistungen

Dieses Repository enthält eine Liste der Sozialleistungen im **YAML**-Format.

Stand: September 2025

Struktur:
- `sozialleistungen.yml`: canonical YAML (Gesetzbuch, Kategorie, Liste)

Konventionen:
- `zielgruppen` und `themenfelder` sind Listen; Reihenfolge impliziert Priorität (erstes Element = primär).

Aufbau und Hierarchie:
```yaml
<Gesetzbuch>:
  <Kategorie>:
  - leistung: <Bezeichnung und ggf. Beschreibung der Leistung>
    rechtsnorm: <Angabe/Fundstelle im Gesetz>
    zielgruppen:
    - <Primäre Zielgruppe>
    - <ggf. sekundäre Zielgruppe>
    themenfelder:
    - <primäres Themenfeld>
    - <ggf. sekundäres Themenfeld>
```

Beispiel:
```yaml
SGB II:
  Leistungen der Grundsicherung für Arbeitssuchende:
  - leistung: Leistungen zur Eingliederung in Arbeit, Beratung für sicherungsempfangende
      Arbeitssuchende.
    rechtsnorm: § 14 Abs. 2 Grundsatz des Förderns SGB II
    zielgruppen:
    - Erwerbsalter
    - Jugendliche
    themenfelder:
    - Arbeit & Grundsicherung
```
