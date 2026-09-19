---
tipus: rendszer
---
# Vault útmutató

Ez a jegyzet a vault szabályait rögzíti. Ember és LLM is ebből dolgozik. Ha a szerkezeten változtatsz, itt is írd át.

## Cél

Érettségi tételek egy helyen, egységes szerkezetben. Egy LLM bármikor ki tudja bővíteni vagy javítani őket, és a Dashboardról mindig látszik, mi kész és mi nem.

## Mappák

```
Tan/
  Dashboard.md
  00 Rendszer/
    Vault útmutató.md
    Sablonok/            Templater sablonok
  <Tantárgy>/
    <Tantárgy> MOC.md
    Tételek/             ide kerülnek a tételek
```

Beállítás: Templater, Template folder location = `00 Rendszer/Sablonok`. Dataview, Enable Inline Queries = be.

## Jegyzettípusok

Minden jegyzet frontmatterében van `tipus`. A Dataview listák erre szűrnek, címkére nincs szükség.

| tipus | Mi ez | Hol van |
|---|---|---|
| tetel | Egy érettségi tétel | `<Tantárgy>/Tételek/` |
| moc | Egy tantárgy tartalomjegyzéke | `<Tantárgy>/<Tantárgy> MOC.md` |
| dashboard | A teljes vault áttekintője | gyökér |
| rendszer | Szabályok | `00 Rendszer/` |

## Frontmatter mezők

Tétel:

| Kulcs | Érték |
|---|---|
| tipus | `tetel` |
| tantargy | pontosan egyezik a MOC tantargy értékével (pl. `Irodalom`) |
| temakor | szabad szöveg, csoportosításhoz (pl. `Nyugat`) |
| allapot | `vaz`, `kidolgozva` vagy `kesz` |

MOC: `tipus: moc`, `tantargy`, `tanar`, `szint` (`Közép` vagy `Emelt`).

A kulcsok szándékosan ékezet nélküliek és kisbetűsek, hogy a lekérdezésekben és az LLM-promptokban ne legyen belőlük gond. A létrehozás dátuma nem kell külön mezőbe, a Dataview ismeri a `file.ctime`-ot.

## Állapotok

- `vaz`: csak a nyers jegyzet van meg, a kidolgozás hiányzik vagy vázlatos.
- `kidolgozva`: megvan a teljes kidolgozás, de még nincs átnézve.
- `kesz`: átnézve, tartalmilag rendben, nincs nyitott pont a jegyzetben.

## Tétel szerkezete

1. Frontmatter.
2. `# Cím`, a fájlnévvel megegyezően. Ez az egyetlen H1.
3. A kidolgozás `##` szintű címsorokkal, legfeljebb `######` mélységig. A tartalom szerkezete szabad, tantárgyanként más lehet.
4. `## Kapcsolódó`: legalább a tantárgy MOC-ja.
5. `## Nyitott pontok`: csak ha van benne teendő.
6. `## Nyers jegyzet`: az eredeti tanári jegyzet változtatás nélkül, mindig az utolsó szakasz. Régebbi, már kidolgozott tételeknél nem kötelező.

## Formázás

- Nincs emoji és nincs díszítő elem sem a címsorokban, sem a szövegben.
- Kulcsfogalmak, nevek, évszámok: **félkövér**. Művek címei: *dőlt*.
- Fájlnév egyezik a jegyzet címével. MOC neve: `<Tantárgy> MOC`.

## Nyitott pontok jelölése

Ami hiányzik vagy ellenőrizendő, azt a jegyzet `## Nyitott pontok` szakaszában feladatként kell felvenni:

```
- [ ] HIÁNYZIK: mi hiányzik
- [ ] ELLENŐRIZNI: mit kell megnézni
```

A Dashboard ezeket egy helyen listázza. A pipát (`- [x]`) a felhasználó teszi ki átnézés után, az LLM nem.

## Munkafolyamatok

Új tétel: új jegyzet a `<Tantárgy>/Tételek/` mappában, Tétel sablon, a tanári jegyzet a `## Nyers jegyzet` alá, majd A prompt az LLM-nek. Az eredmény átnézése után `allapot: kesz`.

Meglévő tétel javítása: a Dashboard Nyitott pontok listájából kiválasztod a jegyzetet, majd B prompt.

Új tantárgy: `<Tantárgy> MOC` jegyzet a Tantárgy MOC sablonnal, mellé a `Tételek` mappa.

## Prompt az LLM-nek

A prompt: kidolgozás nyers jegyzetből. A jegyzet teljes szövegét mellé kell másolni.

```
Dolgozd ki az alábbi érettségi tételt a vault szabályai szerint.

- Add vissza a teljes jegyzetet Markdownban, frontmatterrel együtt.
- A frontmatter kulcsait ne változtasd. Az allapot értéke legyen: kidolgozva.
- Egy H1 van (a cím). A kidolgozást a cím és a "## Kapcsolódó" közé írd, ## szintű címsorokkal.
- Nincs emoji és díszítés. Kulcsfogalmak, nevek, évszámok félkövérrel, művek címei dőlten.
- Csak a Nyers jegyzetben szereplő vagy biztosan ismert tényeket írj le. Ne találj ki semmit.
- Ami bizonytalan: "## Nyitott pontok" alatt "- [ ] ELLENŐRIZNI: ..." feladat.
- Ami hiányzik a tételből: "- [ ] HIÁNYZIK: ..." feladat.
- A "## Nyers jegyzet" szakaszt hagyd változatlanul, utolsó szakaszként.
- Az érettségi szint (közép vagy emelt) szerint válaszd meg a részletességet.
- A chatben, a jegyzeten kívül, írj rövid listát arról, mit hoztál létre.
```

B prompt: meglévő jegyzet javítása. A jegyzet teljes szövegét mellé kell másolni.

```
Az alábbi jegyzet "## Nyitott pontok" szakaszában feladatok vannak.

- Csak ezeket a pontokat oldd meg, a többi szöveget ne írd át.
- A megoldott feladatot hagyd bejelölés nélkül, a pipát én teszem ki átnézés után.
- Ne találj ki tényeket. Amiben nem vagy biztos, azt hagyd nyitva, és írd oda, miért.
- Nincs emoji és díszítés. A jegyzet meglévő formázását kövesd.
- Add vissza a teljes jegyzetet, és a chatben sorold fel, pontosan mit változtattál.
```
