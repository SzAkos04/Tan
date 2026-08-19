---
tags:
  - Dashboard
  - MOC
---
# 🗺️ Master Dashboard — Tan Vault

> Íme a teljes vault áttekintése: kurzusok, érettségi tantárgyak és tennivalók egy helyen.

---

## 📚 Tantárgyak & Kurzusok MOC-jai

- [[Irodalom MOC]]
- [[Történelem MOC]]
- [[Angol MOC]]

---

## 📝 Nyitott Feladatok

```dataview
TASK
WHERE !completed
```

---

## 📖 Összes Érettségi Tétel

```dataview
TABLE Kategória, Niveau, Érettségi_Szint
FROM #Erettsegi
SORT Tantárgy ASC, Kategória ASC
```

---

## 🛠️ Sablonok

- [[Erettsegi_Tetel_Vorlage]]