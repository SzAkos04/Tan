---
tipus: moc
tantargy: Irodalom
tanar: Kövi Andrea
szint: Közép
---
# Irodalom MOC

Tanár: `=this.tanar` | Szint: `=this.szint`

## Tételek

```dataview
TABLE temakor AS "Témakör", allapot AS "Állapot"
FROM -"00 Rendszer"
WHERE tipus = "tetel" AND tantargy = this.tantargy
SORT temakor ASC, file.name ASC
```

## Kapcsolódó

- [[Irodalmi fogalomtár]]
- [[Dashboard]]
