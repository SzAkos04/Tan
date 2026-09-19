<%*
const tantargy = tp.file.title.replace(/ MOC$/, "");
const tanar = await tp.system.prompt("Tanár neve:", "", true);
const szint = await tp.system.suggester(["Közép", "Emelt"], ["Közép", "Emelt"], true, "Érettségi szint");
-%>
---
tipus: moc
tantargy: <% tantargy %>
tanar: <% tanar %>
szint: <% szint %>
---
# <% tp.file.title %>

Tanár: `=this.tanar` | Szint: `=this.szint`

## Tételek

```dataview
TABLE temakor AS "Témakör", allapot AS "Állapot"
FROM -"00 Rendszer"
WHERE tipus = "tetel" AND tantargy = this.tantargy
SORT temakor ASC, file.name ASC
```

## Kapcsolódó

- [[Dashboard]]
