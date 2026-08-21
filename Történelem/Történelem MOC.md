---
Tantárgy: Történelem
Tanár: Turi Zoltán
Érettségi_Szint: Közép
tags:
  - MOC
  - Erettsegi
---
# 📚 `=this.Tantárgy` MOC — Érettségi Felkészülés

**Tantárgy:** `=this.Tantárgy` | **Cél / Szint:** `=this.Érettségi_Szint`

---

## 📖 Összes történelem tétel kategóriák szerint

```dataview
TABLE Kategória
FROM #Erettsegi
WHERE Tantárgy = this.Tantárgy AND !(contains(file.name, "MOC"))
SORT Kategória ASC, Téma ASC
```

---

## 🔗 Gyors hivatkozások

- [[Magyar történelem]]
- [[Egyetemes történelem]]