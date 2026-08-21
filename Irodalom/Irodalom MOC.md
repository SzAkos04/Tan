---
Tantárgy: Irodalom
Tanár: Kövi Andrea
Érettségi_Szint: Közép
tags:
  - MOC
  - Erettsegi
---
# 📚 `=this.Tantárgy` MOC — Érettségi Felkészülés

**Tantárgy:** `=this.Tantárgy` | **Cél / Szint:** `=this.Érettségi_Szint`

---

## 📖 Összes irodalom tétel kategóriák szerint

```dataview
TABLE Kategória
FROM #Erettsegi
WHERE Tantárgy = this.Tantárgy AND !(contains(file.name, "MOC"))
SORT Kategória ASC, Téma ASC
```

---

## 🔗 Gyors hivatkozások & Meglévő jegyzetek

- [[Irodalmi fogalomtár]]