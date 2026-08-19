---
tags:
  - MOC
  - Erettsegi
Tantárgy: Történelem
Érettségi_Szint: Emelt
---
# 📚 `=this.Tantárgy` MOC — Érettségi Felkészülés

**Tantárgy:** `=this.Tantárgy` | **Cél / Szint:** `=this.Érettségi_Szint`

---

## 📖 Összes történelem tétel kategóriák szerint

```dataview
TABLE Kategória, Niveau, Szerző_Alak_Esemény AS "Fő szereplő / Esemény", Évszám_Időszak AS "Időszak"
FROM #Erettsegi
WHERE Tantárgy = this.Tantárgy
SORT Kategória ASC, Téma ASC
```

---

## 🔗 Gyors hivatkozások & Meglévő jegyzetek
- [[Kiegyezés]]
- [[Magyar történelem]]
- [[Egyetemes történelem]]