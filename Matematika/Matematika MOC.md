---
tipus: moc
tantargy: Matematika
tanar: Schuch Angéla
szint: Emelt
---
# Matematika MOC

Tanár: `=this.tanar` | Szint: `=this.szint`

## Tételek

```dataview
TABLE temakor AS "Témakör", allapot AS "Állapot"
FROM -"00 Rendszer"
WHERE tipus = "tetel" AND tantargy = this.tantargy
SORT temakor ASC, file.name ASC
```

## PDF-ek

A `Tételek` mappában (almappákban is) lévő PDF-ek. A Jegyzet oszlop akkor mutat linket, ha van azonos nevű tétel jegyzet, egyébként "nincs".

```dataviewjs
const mappa = dv.current().file.folder + "/Tételek";
const jegyzetek = dv.pages('"' + mappa + '"').array();
const pdfek = app.vault.getFiles()
  .filter(f => f.extension === "pdf" && f.path.startsWith(mappa + "/"))
  .sort((a, b) => a.basename.localeCompare(b.basename, "hu"));
if (pdfek.length === 0) {
  dv.paragraph("Nincs PDF a tételek mappában.");
} else {
  dv.table(
    ["PDF", "Jegyzet"],
    pdfek.map(f => {
      const j = jegyzetek.find(p => p.file.name === f.basename);
      return [dv.fileLink(f.path, false, f.basename), j ? j.file.link : "nincs"];
    })
  );
}
```

## Kapcsolódó

- [[Tudnivalók a vizsgázók számára.pdf]]
- [[README]]
