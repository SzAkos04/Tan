---
Tantárgy: <% tp.file.title.replace(" MOC", "") %>
Tanár: <% await tp.system.prompt("Tanár neve:", "") %>
Érettségi_Szint: <% await tp.system.suggester(["Közép", "Emelt"], ["Közép", "Emelt"]) %>
tags:
  - MOC
  - Erettsegi
---
# 📚 `=this.Tantárgy` MOC

**Tanár:** `=this.Tanár` | **Tervezett érettségi szint:** `=this.Érettségi_Szint`

---

## 📖 Összes tétel kategória szerint

```dataview
TABLE Kategória, Létrehozva
FROM #Erettsegi
WHERE Tantárgy = this.Tantárgy
SORT Kategória ASC, Téma ASC
```

---

## 🔗 Kapcsolódó anyagok

- [[00_Dashboard]]