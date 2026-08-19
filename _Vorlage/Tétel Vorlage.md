---
Téma: <% tp.file.title %>
Tantárgy: <% await tp.system.prompt("Tantárgy (pl. Történelem, Fizika, Irodalom):", "") %>
Kategória: <% await tp.system.prompt("Kategória / Témakör:", "") %>
Érettségi_Szint: <% await tp.system.suggester(["Közép", "Emelt"], ["Közép", "Emelt"]) %>
Létrehozva: <% tp.date.now("YYYY-MM-DD HH:mm") %>
tags:
  - Erettsegi
---
# `=this.Téma`

**Tantárgy:** `=this.Tantárgy` | **Kategória:** `=this.Kategória` | **Szint:** `=this.Érettségi_Szint`

---

## 📌 Lényeg / Összefoglalás

> [!NOTE] Tétel áttekintése
> 

---

## 📖 Kidolgozás

---

## 🔗 Kapcsolódó tételek & MOC

- [[00_Dashboard]]