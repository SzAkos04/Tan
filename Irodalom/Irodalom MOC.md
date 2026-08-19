---
tags:
  - MOC
  - Erettsegi
Tantárgy: Magyar nyelv és irodalom
Érettségi_Szint: Közép
---
# 📚 `=this.Tantárgy` MOC — Érettségi Felkészülés

**Tantárgy:** `=this.Tantárgy` | **Cél / Szint:** `=this.Érettségi_Szint`

---

## 📖 Összes irodalom tétel kategóriák szerint

```dataview
TABLE Kategória, Niveau, Szerző_Alak_Esemény AS "Szerző / Mű"
FROM #Erettsegi
WHERE Tantárgy = this.Tantárgy
SORT Kategória ASC, Téma ASC
```

---

## 🔗 Gyors hivatkozások & Meglévő jegyzetek
- [[Ady Endre szerelmi lírája]]
- [[Arany János]]
- [[Irodalmi fogalomtár]]