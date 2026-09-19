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

```dataviewjs
const mocok = dv.pages('-"00 Rendszer"').where(p => p.tipus === "moc").sort(p => p.tantargy, "asc").array();
const tetelek = dv.pages('-"00 Rendszer"').where(p => p.tipus === "tetel").array();
const pdfek = app.vault.getFiles().filter(f => f.extension === "pdf");
const sorok = mocok.map(m => {
  const jegyzetek = tetelek.filter(t => t.tantargy === m.tantargy);
  const nevek = new Set(jegyzetek.map(t => t.file.name));
  const mappa = m.file.folder + "/Tételek/";
  const csakPdf = pdfek.filter(f => f.path.startsWith(mappa) && !nevek.has(f.basename));
  return [
    dv.fileLink(m.file.path, false, m.tantargy),
    jegyzetek.length + csakPdf.length,
    jegyzetek.filter(t => t.allapot === "kesz").length,
    csakPdf.length
  ];
});
dv.table(["Tantárgy", "Tételek", "Kész", "Csak PDF"], sorok);
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
