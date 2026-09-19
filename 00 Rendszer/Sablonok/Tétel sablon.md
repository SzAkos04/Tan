<%*
const tantargyak = ["Irodalom", "Nyelvtan", "Történelem", "Matematika", "Fizika", "Biológia", "Kémia", "Digitális kultúra", "Német", "Angol"];
const tantargy = await tp.system.suggester(tantargyak, tantargyak, true, "Tantárgy");
const temakor = await tp.system.prompt("Témakör (pl. Nyugat, Romantika):", "", true);
-%>
---
tipus: tetel
tantargy: <% tantargy %>
temakor: <% temakor %>
allapot: vaz
---
# <% tp.file.title %>

<!-- A kidolgozás ide kerül, ## szintű címsorokkal. -->

## Kapcsolódó

- [[<% tantargy %> MOC]]

## Nyers jegyzet

<!-- Ide másold be a tanári jegyzetet változtatás nélkül. -->
