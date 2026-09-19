---
tipus: dashboard
---
# Dashboard

A listák a jegyzetek frontmatteréből épülnek, kézzel nem kell karbantartani őket. A szabályok: [[Vault útmutató]].

## Tantárgyak

```dataview
TABLE tanar AS "Tanár", szint AS "Szint"
FROM -"00 Rendszer"
WHERE tipus = "moc"
SORT tantargy ASC
```

## Állás tantárgyanként

```dataview
TABLE length(rows) AS "Tételek", length(filter(rows.allapot, (a) => a = "kesz")) AS "Kész"
FROM -"00 Rendszer"
WHERE tipus = "tetel"
GROUP BY tantargy
```

## Nem kész tételek

```dataview
TABLE tantargy AS "Tantárgy", temakor AS "Témakör", allapot AS "Állapot"
FROM -"00 Rendszer"
WHERE tipus = "tetel" AND allapot != "kesz"
SORT tantargy ASC, temakor ASC
```

## Nyitott pontok

```dataview
TASK
FROM -"00 Rendszer"
WHERE !completed
GROUP BY file.link
```
