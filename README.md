# Liste Sozialleistungen

Dieses Repository enthält eine Liste der Sozialleistungen in den Formaten **YAML, CSV und Excel**. 
`index.html` erzeugt zusätzlich einen statischen Explorer mit Suche und Filtern
nach Gesetzbuch, Zielgruppe und Themenfeld. Filter werden in der URL gehalten,
damit konkrete Ausschnitte als Link geteilt werden koennen.

Eine PDF-Version der Liste ist [hier](https://www.ifo.de/publikationen/2025/monographie-autorenschaft/eine-inventur-im-haus-der-sozialen-hilfe-und)  veröffentlicht.

Eine Erklärung zur Methodologie sowie Auswertungen aufbauend auf dieser Inventur befinden sich in [diesem Artikel](https://www.ifo.de/publikationen/2025/aufsatz-zeitschrift/auf-der-suche-nach-passierschein-a38).


Stand: September 2025

## Explorer und Exporte regenerieren

```sh
python yml_transformer.py
```

Der Generator nutzt `sozialleistungen.yml` als Quelle und schreibt
`sozialleistungen.csv`, `sozialleistungen.xlsx`, `sozialleistungen.json` und
`index.html`.

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
