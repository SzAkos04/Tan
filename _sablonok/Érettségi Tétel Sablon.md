---
Téma: <% tp.file.title %>
Tantárgy: <% await tp.system.suggester(["Irodalom", "Nyelvtan", "Történelem", "Matematika", "Fizika", "Biológia", "Kémia", "Informatika", "Német", "Angol"], ["Irodalom", "Nyelvtan", "Történelem", "Matematika", "Fizika", "Biológia", "Kémia", "Informatika", "Német", "Angol"]) %>
Kategória: <% await tp.system.prompt("Kategória / Témakör:", "") %>
tags:
  - Erettsegi
---
# `=this.Téma`

**Tantárgy:** `=this.Tantárgy` | **Kategória:** `=this.Kategória` | **Tanár:** `=this.Tanár`

---

## 📌 Lényeg / Összefoglalás
> [!NOTE] Áttekintés
> 

---

## 📖 Kidolgozás

<!-- Ide jön a tanári jegyzet alapján elkészített kidolgozás -->


---

## 🔗 Kapcsolódó tételek & MOC
- [[<% tp.frontmatter.Tantárgy %> MOC]]
