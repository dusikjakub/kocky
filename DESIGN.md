# 🐱 KOČKA vs. VYSAVAČ — Design Document

---

## 1. Název hry a základní myšlenka

**Název:** Kočka vs. Vysavač

**Žánr:** 2D Tower Defense

**Základní myšlenka:**
Stará babička Božena sedí na svém oblíbeném gauči, plete svetr a dívá se na televizi. Jednoho dne se všechny robotické vysavače v domě zbláznily a snaží se ji vysát! Naštěstí má babička celou armádu koček, které jí pomohou se bránit.

Hráč strategicky umísťuje různé typy koček (obranné věže) na vyhrazená pole podél cest, kudy přicházejí nepřátelské vysavače. Každá kočka má unikátní schopnosti — od rychlého drápání přes plošné útoky až po zpomalování a odhalování neviditelných nepřátel. Vysavače přicházejí ve vlnách o stoupající síle. Pokud vysavač projde celou cestou, poškodí babičku.

---

## 2. Cíl hry a pravidla

### Cíl
Ubránit babičku Boženu před všemi vlnami robotických vysavačů na dané mapě.

### Základní pravidla
1. Nepřátelé (vysavače) se pohybují po předem dané cestě směrem k babičce.
2. Hráč umísťuje kočičí věže na stavební pole podél cesty.
3. Věže automaticky útočí na nepřátele v dosahu.
4. Za každého zabitého vysavače hráč obdrží odměnu v měně (Klubíčka 🧶).
5. Za Klubíčka lze kupovat nové věže nebo vylepšovat stávající.
6. Pokud vysavač dojde na konec cesty, odebere babičce životy.
7. Pokud babička ztratí všechny životy, hra končí prohrou.
8. Pokud hráč přežije všechny vlny, hra končí výhrou.

### Tok jedné hry
1. Hráč zvolí mapu.
2. Na začátku má počáteční kapitál a čas na rozmístění prvních věží.
3. Hráč ručně spouští každou vlnu tlačítkem „Další vlna!".
4. Během vlny přicházejí nepřátelé a věže na ně útočí.
5. Po skončení vlny má hráč čas na stavbu a vylepšování.
6. Kroky 3–5 se opakují, dokud neskončí všechny vlny (výhra) nebo babička neztratí životy (prohra).

---

## 3. Hlavní menu

### Obrazovka hlavního menu

```
╔══════════════════════════════════════════╗
║                                          ║
║           🐱 KOČKA vs. VYSAVAČ 🤖        ║
║                                          ║
║     (animace: kočka honí vysavač)        ║
║                                          ║
║          ┌──────────────────┐            ║
║          │    ▶  HRÁT       │            ║
║          └──────────────────┘            ║
║          ┌──────────────────┐            ║
║          │    📖 NÁVOD      │            ║
║          └──────────────────┘            ║
║          ┌──────────────────┐            ║
║          │   ⚙️ NASTAVENÍ   │            ║
║          └──────────────────┘            ║
║                                          ║
║  Pozadí: útulný obývací pokoj babičky    ║
╚══════════════════════════════════════════╝
```

### Popis prvků

| Prvek | Funkce |
|-------|--------|
| **Název hry** | Velký nápis s tematickým fontem, jemná animace (kočičí tlapka mávne) |
| **Animace** | Pod názvem: malá kočka honí vysavač zleva doprava ve smyčce |
| **Tlačítko HRÁT** | Přejde na obrazovku výběru mapy |
| **Tlačítko NÁVOD** | Otevře overlay s pravidly hry a popisem ovládání |
| **Tlačítko NASTAVENÍ** | Zapnutí/vypnutí zvuku, reset postupu |
| **Pozadí** | Teplé barvy, obývák s kobercem, gauč v pozadí, polštáře |

### Návod (overlay)
Stručné vysvětlení:
- „Umísťuj kočky na modrá pole kliknutím."
- „Každá kočka má jiné schopnosti — experimentuj!"
- „Spusť vlnu tlačítkem. Přežij všechny vlny!"
- „Klikni na postavenou kočku pro vylepšení nebo prodej."
- Diagram s popisky: ukázka cesty, věže, nepřítele a HUD.

---

## 4. Herní mapy

### Mapa 1: Obývací pokoj ⭐ (Lehká)

**Příběh:** Vysavače vtrhly hlavními dveřmi a míří přímo ke gauči!

| Vlastnost | Hodnota |
|-----------|---------|
| Obtížnost | ⭐ Lehká |
| Počet vln | 10 |
| Cest | 1 |
| Stavebních polí | 14 |
| Životy babičky | 20 ❤️ |
| Počáteční kapitál | 200 🧶 |

**Layout:**
```
  ┌────────────────────────────────────┐
  │ VSTUP                              │
  │  ↓                                 │
  │  ↓   [◻][◻]                        │
  │  ↓                                 │
  │  →  →  →  →  ↓    [◻][◻]          │
  │              ↓                     │
  │  [◻][◻]     ↓                     │
  │              ↓                     │
  │  ←  ←  ←  ←  ←    [◻][◻]          │
  │  ↓                                 │
  │  ↓   [◻][◻]                        │
  │  ↓                                 │
  │  →  →  →  →  →  →  → 🛋️ BABIČKA   │
  │              [◻][◻][◻][◻]          │
  └────────────────────────────────────┘
```

Jednoduchá S-cesta. Ideální na naučení se základních mechanik. Dostatek místa na věže, dlouhá cesta dává čas na zabíjení nepřátel.

---

### Mapa 2: Kuchyně ⭐⭐ (Střední)

**Příběh:** Vysavače se připlížily z chodby I z prádelny. Babička se přesunula ke kuchyňskému stolu!

| Vlastnost | Hodnota |
|-----------|---------|
| Obtížnost | ⭐⭐ Střední |
| Počet vln | 15 |
| Cest | 2 (spojí se před cílem) |
| Stavebních polí | 18 |
| Životy babičky | 15 ❤️ |
| Počáteční kapitál | 250 🧶 |

**Layout:**
```
  ┌────────────────────────────────────┐
  │ VSTUP A           VSTUP B         │
  │  ↓                  ↓             │
  │  ↓  [◻][◻]         ↓  [◻][◻]    │
  │  ↓                  ↓             │
  │  →  →  →  ↓    ←  ←              │
  │   [◻]    ↓     ↓    [◻]          │
  │   [◻]    ↓     ↓    [◻]          │
  │           ↓     ↓                  │
  │   [◻]    →  →  →    [◻]          │
  │                ↓                   │
  │  [◻][◻]      ↓      [◻][◻]      │
  │                ↓                   │
  │          🛋️ BABIČKA                │
  └────────────────────────────────────┘
```

Dvě cesty se spojují uprostřed mapy. Hráč musí rozdělit obranu. Méně životů babičky zvyšuje tlak. Klíčové je pokrýt křižovatku, kde se cesty spojují.

---

### Mapa 3: Celý byt ⭐⭐⭐ (Těžká)

**Příběh:** Totální invaze! Vysavače útočí z koupelny, ložnice i balkónu najednou!

| Vlastnost | Hodnota |
|-----------|---------|
| Obtížnost | ⭐⭐⭐ Těžká |
| Počet vln | 20 |
| Cest | 3 (částečně se spojují) |
| Stavebních polí | 22 |
| Životy babičky | 10 ❤️ |
| Počáteční kapitál | 300 🧶 |

**Layout:**
```
  ┌────────────────────────────────────────┐
  │ VSTUP A       VSTUP B       VSTUP C   │
  │  ↓              ↓              ↓       │
  │  ↓ [◻][◻]      ↓ [◻]        ↓ [◻]  │
  │  ↓              ↓              ↓       │
  │  →  →  ↓       ↓        ←  ←         │
  │  [◻]  ↓   [◻] ↓  [◻]  ↓   [◻]      │
  │        ↓       ↓        ↓             │
  │        →  →  → ● ←  ←  ←             │
  │           [◻] [◻] [◻]                 │
  │                ↓                       │
  │   [◻][◻]     ↓      [◻][◻]          │
  │                ↓                       │
  │          🛋️ BABIČKA                    │
  └────────────────────────────────────────┘
```

Tři vstupy, cesty se sbíhají v jednom uzlu (●) a pak vedou společně k babičce. Nejméně životů, nejvíce vln. Křižovatka je strategicky klíčová — plošné věže (Garfield) a podpůrné věže (Sfinx, Perská) zde září.

---

## 5. Kočičí věže (8 typů)

### Obecné mechaniky věží
- Věž se umísťuje na stavební pole (◻) kliknutím.
- Po umístění automaticky útočí na nejbližšího nepřítele v dosahu, který je nejblíže ke konci cesty (priorita = největší hrozba).
- Věž lze **vylepšit** (3 úrovně) nebo **prodat** (vrací 60 % investice).
- Každá věž má vizuální animaci útoku.

---

### 🐱 Věž 1: Mourek (Základní)

| Vlastnost | Hodnota |
|-----------|---------|
| **Popis** | Obyčejný pruhovaný kocour. Spolehlivý univerzální obránce. |
| **Vzhled** | Oranžovo-hnědý pruhovaný kruh s ušima a zelenýma očima |
| **Pořizovací cena** | 50 🧶 |
| **Dosah útoku** | 120 px (střední) |
| **Síla útoku** | 10 dmg |
| **Rychlost útoku** | 1,0 útok/s |
| **DPS** | 10,0 |
| **Typ útoku** | Jednoduchost — drápne jednoho nepřítele |
| **Speciální schopnost** | Žádná — čistý, spolehlivý damage |
| **Střela** | Oranžová tlapka letící k cíli |

**Upgrade Lvl 2** (cena 30 🧶): Dmg → 14, Dosah → 132 px
**Upgrade Lvl 3** (cena 50 🧶): Dmg → 20, Dosah → 144 px, Rychlost → 1,2/s

**Kdy použít:** Vždy. Základní páteř obrany. Dobrý poměr cena/výkon.

---

### 🐈 Věž 2: Micinka (Rychlá)

| Vlastnost | Hodnota |
|-----------|---------|
| **Popis** | Malé hravé kotě. Co jí chybí na síle, dohání rychlostí. |
| **Vzhled** | Malý bílý kruh s růžovým nosíkem, velké modré oči |
| **Pořizovací cena** | 30 🧶 |
| **Dosah útoku** | 90 px (krátký) |
| **Síla útoku** | 5 dmg |
| **Rychlost útoku** | 2,5 útok/s |
| **DPS** | 12,5 |
| **Typ útoku** | Rychlé drápání jednoho cíle |
| **Speciální schopnost** | **Zuřivost** — po každém 5. zásahu do stejného cíle zdvojnásobí rychlost útoku na 2 s |
| **Střela** | Drobné bílé drápky |

**Upgrade Lvl 2** (cena 18 🧶): Dmg → 7, Rychlost → 3,0/s
**Upgrade Lvl 3** (cena 30 🧶): Dmg → 10, Rychlost → 3,5/s, Zuřivost se aktivuje po 3. zásahu

**Kdy použít:** Levný early-game spam. Skvělá proti rychlým jednotkám (Roomba Turbo). Slabá proti tankům.

---

### 🐈‍⬛ Věž 3: Garfield (Plošný)

| Vlastnost | Hodnota |
|-----------|---------|
| **Popis** | Obrovský tlustý kocour. Líně hází lasagne na skupiny nepřátel. |
| **Vzhled** | Velký oranžový kruh, přivřené oči, široký úsměv |
| **Pořizovací cena** | 120 🧶 |
| **Dosah útoku** | 110 px (střední) |
| **Síla útoku** | 30 dmg |
| **Rychlost útoku** | 0,5 útok/s |
| **DPS** | 15,0 (na cíl; efektivně více díky AoE) |
| **Typ útoku** | **Plošný (AoE)** — zasáhne všechny nepřátele v okruhu 50 px od dopadu |
| **Speciální schopnost** | **Lasagne bomba** — plošný útok, zanechá na zemi lepivou skvrnu zpomalující o 20 % na 1 s |
| **Střela** | Létající talíř lasagne, exploze při dopadu |

**Upgrade Lvl 2** (cena 72 🧶): Dmg → 42, AoE radius → 60 px
**Upgrade Lvl 3** (cena 120 🧶): Dmg → 55, AoE radius → 70 px, zpomalení → 35 % na 1,5 s

**Kdy použít:** Nejlepší proti swarmům (Mini vysavače). Klíčový na křižovatkách map. Drahý, vyplatí se na místech s hustým provozem.

---

### 👑 Věž 4: Perská kočka (Zpomalovací)

| Vlastnost | Hodnota |
|-----------|---------|
| **Popis** | Elegantní perská kočka. Svým pohrdavým pohledem zpomaluje vysavače. |
| **Vzhled** | Bílý nadýchaný kruh, zploštělý nos, korunka |
| **Pořizovací cena** | 80 🧶 |
| **Dosah útoku** | 110 px (střední) |
| **Síla útoku** | 5 dmg |
| **Rychlost útoku** | 1,0 útok/s |
| **DPS** | 5,0 |
| **Typ útoku** | Chladný pohled — zasáhne jednoho nepřítele |
| **Speciální schopnost** | **Mrazivý pohled** — zasažený nepřítel je zpomalen o 40 % po dobu 2 s |
| **Střela** | Modrý ledový paprsek |

**Upgrade Lvl 2** (cena 48 🧶): Dmg → 7, Zpomalení → 50 %
**Upgrade Lvl 3** (cena 80 🧶): Dmg → 10, Zpomalení → 60 %, délka efektu → 3 s, dosah → 130 px

**Kdy použít:** Podpůrná věž. Umístit před silné útočné věže, aby nepřátelé strávili více času v palbě. Kritická proti rychlým jednotkám (Turbo, Dyson).

---

### 🎯 Věž 5: Siamská kočka (Sniper)

| Vlastnost | Hodnota |
|-----------|---------|
| **Popis** | Tichá a soustředěná siamka. Čeká, cílí, zasáhne z obrovské vzdálenosti. |
| **Vzhled** | Štíhlý krémový kruh s tmavýma ušima a modrýma očima, zaměřovací kříž |
| **Pořizovací cena** | 100 🧶 |
| **Dosah útoku** | 200 px (dlouhý) |
| **Síla útoku** | 25 dmg |
| **Rychlost útoku** | 0,6 útok/s |
| **DPS** | 15,0 |
| **Typ útoku** | Přesný zásah na jednoho nepřítele na velkou vzdálenost |
| **Speciální schopnost** | **Kritický zásah** — 20 % šance na 2× dmg |
| **Střela** | Rychlý modrý laserový paprsek |

**Upgrade Lvl 2** (cena 60 🧶): Dmg → 35, Krit šance → 25 %
**Upgrade Lvl 3** (cena 100 🧶): Dmg → 50, Krit šance → 30 %, Dosah → 240 px

**Kdy použít:** Zadní linie obrany. Snipes vysokohodnotné cíle. Skvělá proti Létajícím Dysonům a bossům. Slabá proti swarmům.

---

### 🖤 Věž 6: Černá kočka (Jedová)

| Vlastnost | Hodnota |
|-----------|---------|
| **Popis** | Tajemná černá kočka. Přináší smůlu — vysavačům se začnou kazit součástky. |
| **Vzhled** | Černý kruh se svítícíma žlutýma očima, fialová aura |
| **Pořizovací cena** | 90 🧶 |
| **Dosah útoku** | 110 px (střední) |
| **Síla útoku** | 8 dmg (počáteční) + 5 dmg/s po dobu 3 s (DoT) |
| **Rychlost útoku** | 1,0 útok/s |
| **DPS** | 8 + 15 = efektivně ~18–23 (dle překrývání) |
| **Typ útoku** | Jedovatý zásah — počáteční dmg + poškození v čase |
| **Speciální schopnost** | **Smůla (DoT)** — otráví nepřítele, 5 dmg/s po 3 s. Jed se nesčítá, ale obnovuje trvání. |
| **Střela** | Fialový oblak letící k cíli |

**Upgrade Lvl 2** (cena 54 🧶): Dmg → 12, DoT → 7/s po 3 s
**Upgrade Lvl 3** (cena 90 🧶): Dmg → 16, DoT → 10/s po 4 s, DoT se šíří na blízké nepřátele (5 px radius)

**Kdy použít:** Excelentní proti pomalým tankům (Průmyslový vysavač) — jed tiká dlouho. Lvl 3 spread jed devastuje swarmy. Slabší proti rychlým jednotkám, které projedou dosah příliš rychle.

---

### 🦁 Věž 7: Mainská mývalí (Blokátor)

| Vlastnost | Hodnota |
|-----------|---------|
| **Popis** | Obrovská a majestátní mainská mývalí kočka. Občas chytne vysavač a drží ho na místě. |
| **Vzhled** | Velký hnědý chlupatý kruh, mohutná hříva, klidné oči |
| **Pořizovací cena** | 150 🧶 |
| **Dosah útoku** | 80 px (krátký) |
| **Síla útoku** | 15 dmg |
| **Rychlost útoku** | 1,0 útok/s |
| **DPS** | 15,0 |
| **Typ útoku** | Silné drápnutí na blízko |
| **Speciální schopnost** | **Chycení** — 25 % šance při zásahu nepřítele zastavit na 1,5 s. Nefunguje na bossy a Létající Dysony. |
| **Střela** | Velká hnědá tlapka (blízký dosah, okamžitý zásah) |

**Upgrade Lvl 2** (cena 90 🧶): Dmg → 22, Šance chycení → 30 %, Délka → 2,0 s
**Upgrade Lvl 3** (cena 150 🧶): Dmg → 30, Šance chycení → 40 %, Délka → 2,5 s, Funguje na bossy (s poloviční délkou)

**Kdy použít:** Umístit na úzká místa cesty. Zastavuje nepřátele, takže ostatní věže je stíhají zabít. Extrémně silná v kombinaci se Siamkou a Garfieldem. Nejdražší věž.

---

### 👁️ Věž 8: Sfinx (Podpůrná aura)

| Vlastnost | Hodnota |
|-----------|---------|
| **Popis** | Holá mystická kočka. Ničím neútočí, ale její přítomnost zesiluje ostatní kočky a odhaluje skryté nepřátele. |
| **Vzhled** | Růžovo-šedý holý kruh, velké uši, svítící třetí oko na čele |
| **Pořizovací cena** | 110 🧶 |
| **Dosah aury** | 130 px (střední–dlouhý) |
| **Síla útoku** | 0 dmg (neútočí) |
| **Rychlost útoku** | — |
| **DPS** | 0 (ale zesiluje ostatní) |
| **Typ útoku** | Žádný přímý útok |
| **Speciální schopnost** | **Mystická aura** — všechny věže v dosahu aury získají +25 % dmg. Zároveň odhaluje neviditelné nepřátele (Stealth Roomba) v celém dosahu aury. |
| **Střela** | Žádná — viditelný pulzující okruh aury |

**Upgrade Lvl 2** (cena 66 🧶): Buff → +35 % dmg, Dosah aury → 150 px
**Upgrade Lvl 3** (cena 110 🧶): Buff → +50 % dmg, Dosah aury → 170 px, Nový efekt: +15 % rychlost útoku věží v dosahu

**Kdy použít:** Force multiplier. Umístit doprostřed shluku věží. Jediný spolehlivý counter na Stealth Roomby. Lvl 3 Sfinx obklopená 4+ věžemi dramaticky zvyšuje celkový DPS.

---

### Přehledová tabulka věží

| # | Věž | Cena | Dmg | Rychlost | DPS | Dosah | Speciální |
|---|-----|------|-----|----------|-----|-------|-----------|
| 1 | Mourek | 50 | 10 | 1,0/s | 10,0 | 120 | — |
| 2 | Micinka | 30 | 5 | 2,5/s | 12,5 | 90 | Zuřivost |
| 3 | Garfield | 120 | 30 | 0,5/s | 15,0+ | 110 | AoE + slow |
| 4 | Perská | 80 | 5 | 1,0/s | 5,0 | 110 | 40 % slow |
| 5 | Siamka | 100 | 25 | 0,6/s | 15,0 | 200 | 20 % krit |
| 6 | Černá | 90 | 8+DoT | 1,0/s | ~20 | 110 | DoT 5/s, 3 s |
| 7 | Mainská | 150 | 15 | 1,0/s | 15,0 | 80 | 25 % stun 1,5 s |
| 8 | Sfinx | 110 | 0 | — | 0 | 130 | +25 % dmg aura, reveal |

---

## 6. Robotické vysavače (nepřátelé)

### Obecné mechaniky nepřátel
- Nepřátelé se pohybují po předem dané cestě (waypointy).
- Mají HP bar zobrazený nad sebou.
- Po zabití zmizí a hráč obdrží odměnu.
- Pokud dorazí na konec cesty, poškodí babičku a zmizí.
- Některé typy mají speciální schopnosti.

---

### 🤖 Nepřítel 1: Roomba Basic

| Vlastnost | Hodnota |
|-----------|---------|
| **Popis** | Obyčejný kulatý robotický vysavač. Nic zvláštního, ale je jich hodně. |
| **Vzhled** | Šedý kruh s malým červeným světýlkem, otáčející se kartáč |
| **Počet životů** | 50 HP |
| **Rychlost pohybu** | 1,0 (základní) |
| **Poškození babičky** | 2 ❤️ |
| **Odměna za poražení** | 10 🧶 |
| **Speciální** | Žádná |

---

### ⚡ Nepřítel 2: Roomba Turbo

| Vlastnost | Hodnota |
|-----------|---------|
| **Popis** | Upravená roomba s turbo motorem. Profrčí obranou dřív, než si jí všimnete. |
| **Vzhled** | Červený kruh s pruhy, jiskry za sebou, menší než Basic |
| **Počet životů** | 35 HP |
| **Rychlost pohybu** | 2,0 (dvojnásobná) |
| **Poškození babičky** | 2 ❤️ |
| **Odměna za poražení** | 15 🧶 |
| **Speciální** | **Turbo start** — první 2 sekundy na mapě se pohybuje 3× rychlostí |

---

### 🏋️ Nepřítel 3: Průmyslový vysavač

| Vlastnost | Hodnota |
|-----------|---------|
| **Popis** | Masivní průmyslový vysavač na kolečkách. Pomalý, ale extrémně odolný. |
| **Vzhled** | Velký tmavě modrý obdélník s hadicí, robustní kola, blikající výstražná světla |
| **Počet životů** | 250 HP |
| **Rychlost pohybu** | 0,5 (pomalá) |
| **Poškození babičky** | 4 ❤️ |
| **Odměna za poražení** | 30 🧶 |
| **Speciální** | **Obrněný** — přijímá o 20 % méně dmg ze všech zdrojů |

---

### 🐜 Nepřítel 4: Mini vysavač

| Vlastnost | Hodnota |
|-----------|---------|
| **Popis** | Titěrný ručný vysaváček. Sám o sobě neškodný, ale přichází v hordách. |
| **Vzhled** | Velmi malý zelený kroužek, rychle kmitající |
| **Počet životů** | 15 HP |
| **Rychlost pohybu** | 1,5 (mírně rychlá) |
| **Poškození babičky** | 1 ❤️ |
| **Odměna za poražení** | 3 🧶 |
| **Speciální** | **Swarm** — vždy přichází ve skupině 6–12 kusů s krátkým rozestupem |

---

### 👻 Nepřítel 5: Stealth Roomba

| Vlastnost | Hodnota |
|-----------|---------|
| **Popis** | Tichá roomba s maskovacím zařízením. Projíždí kolem věží nepozorovaně. |
| **Vzhled** | Poloprůhledný světle šedý kruh, občas problikne (při viditelnosti plně viditelný) |
| **Počet životů** | 45 HP |
| **Rychlost pohybu** | 1,2 (mírně rychlá) |
| **Poškození babičky** | 2 ❤️ |
| **Odměna za poražení** | 20 🧶 |
| **Speciální** | **Neviditelnost** — věže na něj nemůžou cílit, pokud: (a) nemá v dosahu Sfinx věž, nebo (b) se nachází v krátkém dosahu (≤ 60 px) libovolné věže |

---

### 💥 Nepřítel 6: EMP vysavač

| Vlastnost | Hodnota |
|-----------|---------|
| **Popis** | Vysavač vybavený EMP generátorem. Dočasně vyřadí okolní kočky z provozu. |
| **Vzhled** | Žlutý kruh s blikajícími elektrickými oblouky, varovný symbol ⚡ |
| **Počet životů** | 100 HP |
| **Rychlost pohybu** | 0,8 (pomalejší) |
| **Poškození babičky** | 3 ❤️ |
| **Odměna za poražení** | 30 🧶 |
| **Speciální** | **EMP pulz** — každých 5 s vypustí pulz (radius 70 px), který deaktivuje všechny věže v dosahu na 2 s (věže přestanou útočit a zešednou). Nefunguje na Sfinx. |

---

### 🚁 Nepřítel 7: Létající Dyson

| Vlastnost | Hodnota |
|-----------|---------|
| **Popis** | Futuristický vysavač s rotory. Létá nad cestou — ignoruje pozemní blokaci. |
| **Vzhled** | Stříbrný kruh s vrtulkou nahoře, stín pod ním, mírně nad cestou |
| **Počet životů** | 70 HP |
| **Rychlost pohybu** | 1,8 (rychlá) |
| **Poškození babičky** | 3 ❤️ |
| **Odměna za poražení** | 25 🧶 |
| **Speciální** | **Let** — imunní vůči Chycení (Mainská kočka) a zpomalení od Lasagne (Garfield). Zpomalení od Perské kočky funguje na 50 % efektivity. |

---

### 💀 Nepřítel 8: Mega Vysavač 3000 (BOSS)

| Vlastnost | Hodnota |
|-----------|---------|
| **Popis** | Obrovský šílený prototypový vysavač. Boss jednotka, přichází na konci klíčových vln. |
| **Vzhled** | 3× velikost normálního nepřítele, tmavě červený s černými pruhy, svítící červené oči, kouř z výfuku |
| **Počet životů** | 600 HP |
| **Rychlost pohybu** | 0,4 (velmi pomalá) |
| **Poškození babičky** | 6 ❤️ |
| **Odměna za poražení** | 100 🧶 |
| **Speciální** | **Regenerace** — obnovuje 3 HP/s. **Obrněný** — přijímá o 30 % méně dmg. **Pomalá imunita** — nemůže být zpomalen pod 50 % své rychlosti. |

---

### Přehledová tabulka nepřátel

| # | Nepřítel | HP | Rychlost | Dmg babičce | Odměna | Speciální |
|---|----------|----|----------|-------------|--------|-----------|
| 1 | Roomba Basic | 50 | 1,0 | 2 ❤️ | 10 🧶 | — |
| 2 | Roomba Turbo | 35 | 2,0 | 2 ❤️ | 15 🧶 | Turbo start |
| 3 | Průmyslový | 250 | 0,5 | 4 ❤️ | 30 🧶 | -20 % dmg |
| 4 | Mini vysavač | 15 | 1,5 | 1 ❤️ | 3 🧶 | Swarm (6–12) |
| 5 | Stealth Roomba | 45 | 1,2 | 2 ❤️ | 20 🧶 | Neviditelnost |
| 6 | EMP vysavač | 100 | 0,8 | 3 ❤️ | 30 🧶 | Deaktivace věží |
| 7 | Létající Dyson | 70 | 1,8 | 3 ❤️ | 25 🧶 | Let, anti-CC |
| 8 | BOSS: Mega 3000 | 600 | 0,4 | 6 ❤️ | 100 🧶 | Regen, obrněný |

---

## 7. Systém vln nepřátel

### Principy systému vln

1. **Hráčem řízené tempo** — vlna začíná až po stisknutí tlačítka „Další vlna!".
2. **Eskalace** — každá vlna je těžší (více nepřátel, silnější typy).
3. **Nové typy postupně** — nový typ nepřítele se představí vždy s varovným textem.
4. **Boss vlny** — každá 5. vlna obsahuje Mega Vysavač 3000.
5. **Spawning** — nepřátelé se objevují v intervalech (0,8–2,0 s mezi jednotlivými).
6. **Multi-path** — na mapách s více cestami se nepřátelé rozdělují náhodně (s váhou).

### Nový nepřítel — oznámení

Při prvním výskytu nového typu se zobrazí varovný banner:
> ⚠️ **Nový nepřítel: Stealth Roomba!** — Pozor, je neviditelná! Použij Sfinx nebo ji nech přiblížit.

### Podrobné rozložení vln

#### Mapa 1: Obývací pokoj (10 vln)

| Vlna | Nepřátelé | Celkem HP | Odměna | Nový typ |
|------|-----------|-----------|--------|----------|
| 1 | 5× Roomba Basic | 250 | 50 🧶 | Roomba Basic |
| 2 | 8× Roomba Basic | 400 | 80 🧶 | — |
| 3 | 6× Roomba Basic + 6× Mini | 390 | 78 🧶 | Mini vysavač |
| 4 | 5× Roomba Turbo + 4× Basic | 375 | 115 🧶 | Roomba Turbo |
| 5 | 10× Basic + 1× **BOSS** | 1100 | 200 🧶 | **BOSS** |
| 6 | 4× Stealth + 6× Basic | 480 | 140 🧶 | Stealth Roomba |
| 7 | 3× Průmyslový + 10× Mini | 900 | 120 🧶 | Průmyslový |
| 8 | 4× EMP + 5× Turbo | 575 | 195 🧶 | EMP vysavač |
| 9 | 4× Dyson + 4× Stealth + 3× Průmyslový | 1210 | 240 🧶 | Létající Dyson |
| 10 | 8× směs + 1× **BOSS** (2× HP) | ~1800 | 300+ 🧶 | BOSS enhanced |

**Bonusová odměna za dokončení vlny:** +30 🧶

#### Mapa 2: Kuchyně (15 vln)

| Vlna | Klíčový obsah | Poznámka |
|------|--------------|----------|
| 1–3 | Basic + Mini, postupně více | Rozehřátí, hráč se učí 2 cesty |
| 4–5 | Turbo + Basic, vlna 5 = BOSS | První boss, cesty se plní |
| 6–8 | Stealth, Průmyslový, EMP mix | Speciální nepřátelé |
| 9–10 | Dyson + plný mix, vlna 10 = BOSS | Druhý boss, vyšší HP |
| 11–13 | Velké swarmy + EMP + Stealth | Chaos, nutí prodávat a přestavovat |
| 14–15 | Vše najednou, vlna 15 = BOSS (3× HP) | Finální zátěž |

#### Mapa 3: Celý byt (20 vln)

| Vlna | Klíčový obsah | Poznámka |
|------|--------------|----------|
| 1–4 | Základní typy, 3 cesty | Hráč se učí třídit obranu |
| 5 | BOSS (cesta A) + swarmy (B + C) | Tlak na všechny cesty |
| 6–9 | Všechny speciální typy | Hráč potřebuje diverzifikovat |
| 10 | BOSS + EMP doprovod | Deaktivace + tank |
| 11–14 | Masivní vlny, 15–25 nepřátel | Ekonomický test |
| 15 | Dvojitý BOSS (2 cesty) | Extrémní tlak |
| 16–19 | Plný mix, Stealth+Dyson komba | Chaos vln |
| 20 | Trojitý BOSS + plná směs | Ultimátní výzva |

---

## 8. Herní měna a ekonomika

### Měna: Klubíčka 🧶

| Zdroj příjmu | Hodnota |
|-------------|---------|
| Počáteční kapitál (mapa 1) | 200 🧶 |
| Počáteční kapitál (mapa 2) | 250 🧶 |
| Počáteční kapitál (mapa 3) | 300 🧶 |
| Za zabití nepřítele | Dle tabulky (3–100 🧶) |
| Bonus za dokončení vlny | 30 🧶 (mapa 1), 40 🧶 (mapa 2), 50 🧶 (mapa 3) |

| Výdaj | Cena |
|-------|------|
| Nákup věže | 30–150 🧶 (dle typu) |
| Upgrade na Lvl 2 | 60 % základní ceny |
| Upgrade na Lvl 3 | 100 % základní ceny |
| Prodej věže | Vrací 60 % celkové investice (nákup + upgrady) |

### Ekonomická křivka (mapa 1)

| Po vlně | Přibližný příjem (kumulativní) | Co si hráč může dovolit |
|---------|-------------------------------|-------------------------|
| Start | 200 🧶 | 3–4 levné věže nebo 2 střední |
| Vlna 3 | ~450 🧶 | Upgrady + 1–2 nové věže |
| Vlna 5 | ~800 🧶 | Drahé věže (Mainská, Garfield) |
| Vlna 7 | ~1200 🧶 | Plné Lvl 2 upgrady |
| Vlna 10 | ~1800 🧶 | Několik Lvl 3 věží |

### Designový záměr
- Hráč nikdy nemá dost peněz na všechno → musí činit rozhodnutí.
- Upgrade vs. nová věž je vždy dilema.
- Prodej špatně umístěné věže penalizuje (ztráta 40 %), ale umožňuje adaptaci.

---

## 9. Systém životů babičky

### Mechanika životů

| Mapa | Počáteční životy |
|------|-----------------|
| Obývací pokoj | 20 ❤️ |
| Kuchyně | 15 ❤️ |
| Celý byt | 10 ❤️ |

### Poškození dle typu nepřítele

| Nepřítel | Poškození |
|----------|-----------|
| Mini vysavač | 1 ❤️ |
| Roomba Basic | 2 ❤️ |
| Roomba Turbo | 2 ❤️ |
| Stealth Roomba | 2 ❤️ |
| Průmyslový | 4 ❤️ |
| EMP vysavač | 3 ❤️ |
| Létající Dyson | 3 ❤️ |
| BOSS: Mega 3000 | 6 ❤️ |

### Vizuální zpětná vazba
- **20–15 ❤️:** Babička plete klidně, zelený HP bar
- **14–8 ❤️:** Babička se mračí, žlutý HP bar, gauč se třese
- **7–4 ❤️:** Babička je vyděšená, oranžový HP bar, blikající okraje
- **3–1 ❤️:** Babička křičí, červený HP bar, pulzující červené okraje obrazovky
- **0 ❤️:** Prohra — animace babičky padající z gauče

### Životy se NEREGENERUJÍ mezi vlnami.

Toto zvyšuje napětí — každý proklouznutý vysavač se počítá permanentně.

---

## 10. Podmínky vítězství a prohry

### Výhra 🏆
- Hráč přežije **všechny vlny** dané mapy s alespoň 1 ❤️.
- Zobrazí se **Victory Screen**:
  - Animace: Babička mává, kočky předou, vysavače leží rozbitě na zemi.
  - **Statistiky:**
    - Zabitých vysavačů: X / Y
    - Zbylé životy babičky: X ❤️
    - Nejvíce zabití: [jméno věže]
    - Celkem utraceno: X 🧶
  - **Hvězdičkové hodnocení:**
    - ⭐ — Přežil (1+ ❤️)
    - ⭐⭐ — Přežil s 50 %+ ❤️
    - ⭐⭐⭐ — Přežil se 100 % ❤️ (žádný vysavač neprošel)
  - Tlačítko: **Další mapa** / **Zpět na menu**

### Prohra 💀
- Babička ztratí **všechny životy** (0 ❤️).
- Hra se okamžitě zastaví.
- Zobrazí se **Game Over Screen**:
  - Animace: Vysavače krouží kolem prázdného gauče.
  - Text: „Vysavače vyhrály! Babička Božena musela utéct k sousedce."
  - **Statistiky:** Jaká vlna, kolik nepřátel zabito.
  - Tlačítka: **Zkusit znovu** (stejná mapa od začátku) / **Zpět na menu**

### Odemykání map
- Mapa 1 je odemčená od začátku.
- Mapa 2 se odemkne po dokončení mapy 1 (jakékoliv hvězdy).
- Mapa 3 se odemkne po dokončení mapy 2 (jakékoliv hvězdy).

---

## 11. Ovládání hry

### Myš (primární ovládání)

| Akce | Vstup |
|------|-------|
| **Vybrat věž k nákupu** | Klik na ikonu věže ve spodním panelu |
| **Umístit věž** | Klik na volné stavební pole (zvýrazněné zeleně) |
| **Zrušit výběr** | Pravý klik myší nebo klik mimo pole |
| **Vybrat postavenou věž** | Klik na věž na mapě |
| **Vylepšit věž** | Klik na věž → klik na tlačítko „Vylepšit" v kontextovém menu |
| **Prodat věž** | Klik na věž → klik na tlačítko „Prodat" v kontextovém menu |
| **Spustit vlnu** | Klik na tlačítko „Další vlna!" v pravém dolním rohu |
| **Zrychlit hru** | Klik na ⏩ (přepíná 1× / 2× rychlost) |
| **Hover info** | Najet myší na věž v obchodě → tooltip s popisem a statistikami |

### Klávesové zkratky

| Klávesa | Akce |
|---------|------|
| `1`–`8` | Vybrat věž 1–8 z obchodu |
| `Escape` | Zrušit výběr / zavřít kontextové menu |
| `Space` | Spustit další vlnu / pauza |
| `S` | Prodat vybranou věž |
| `U` | Vylepšit vybranou věž |

### Vizuální nápovědy při umísťování
- **Zelené pole:** Sem lze věž umístit.
- **Červené pole:** Pole je obsazené.
- **Modrý kruh:** Zobrazí dosah vybrané věže při hoveru nad polem.
- **Žlutý okraj:** Pole je v dosahu Sfinx aury (bonus dmg).

---

## 12. Grafický styl a zvukové efekty

### Grafický styl

**Celkový přístup:** Procedurálně generovaná 2D grafika přímo na HTML5 Canvas. Žádné externí obrázky — vše kresleno kódem. Styl je **roztomilý a karikaturní** (cute cartoon).

#### Barevná paleta

| Oblast | Barvy |
|--------|-------|
| **Pozadí mapy** | Teplé béžové, hnědé, dřevěné tóny (podlaha) |
| **Cesta** | Světle šedá s tmavším okrajem (koberec / dlaždice) |
| **Stavební pole** | Zelená průhledná pole (dostupná), červená (obsazená) |
| **Kočky** | Každá svou barvou (oranžová, bílá, černá, šedá…) |
| **Vysavače** | Studené barvy (šedá, modrá, červená, žlutá pro varianty) |
| **HUD** | Poloprůhledný tmavý panel nahoře a dole |
| **Efekty** | Zářivé barvy — oranžové tlapky, modré paprsky, fialový jed |

#### Vizuální design kočičích věží

Každá kočka je kreslena jako kruh s detaily:
- **Tělo:** Vyplněný kruh hlavní barvou.
- **Uši:** Dva trojúhelníky nahoře.
- **Oči:** Dvě elipsy s pupilami (mrkají při útoku).
- **Nos:** Malý trojúhelník.
- **Vousky:** 3 čárky na každé straně.
- **Speciální prvek:** Korunka (Perská), třetí oko (Sfinx), jiskry (Siamka) atd.

#### Vizuální design vysavačů

- **Roomba typy:** Kruhy s indikátorem (LED pásek).
- **Průmyslový:** Obdélník s hadicí.
- **Létající Dyson:** Kruh s vrtulkou + stín pod ním.
- **BOSS:** 3× velikost, pulsující aura, kouř.

#### Animace

| Animace | Popis |
|---------|-------|
| Věž útočí | Kočka zamrká + střela vyletí |
| Nepřítel umírá | Zmenšení + „pop" efekt s particles |
| Nepřítel dostane zásah | Červený flash na 0,1 s |
| Jed (DoT) | Zelené bubliny nad nepřítelem |
| EMP pulz | Žlutý expandující kruh |
| Stealth | Poloprůhlednost se sinusovým kolísáním |
| Boss příchod | Obrazovka se zatřese + varovný text |
| Chycení (Mainská) | Vysavač se zastaví, animované tlapky kolem něj |
| Zpomalení | Modré šipky dolů nad nepřítelem |
| Lasagne dopad | Oranžový splash + skvrna na zemi |

#### Particles

- **Smrt nepřítele:** 5–8 malých šedých/oranžových teček rozletí se do stran.
- **Kritický zásah (Siamka):** Žlutá hvězdička + text „KRIT!".
- **Upgrade věže:** Zlaté jiskry spirálovitě stoupající.
- **Boss aura:** Červené partially kolem bosse.

### Zvukové efekty

Zvuky budou generované procedurálně pomocí Web Audio API (žádné externí soubory):

| Zvuk | Popis zvuku | Kdy hraje |
|------|-------------|-----------|
| **Útok tlapkou** | Krátký „fšš" (white noise burst, 50 ms) | Mourek, Micinka, Mainská útočí |
| **Lasagne hod** | Nízký „svišt" + „splat" (sweep down + noise) | Garfield útočí |
| **Laser** | Vysoký krátký „píp" (sine wave sweep) | Siamka útočí |
| **Mrazení** | Krystalický „tink" (high freq + reverb) | Perská útočí |
| **Jed** | Bublání (modulovaný low freq) | Černá kočka útočí |
| **Chycení** | „Chňap" (noise burst + low thud) | Mainská chytí nepřítele |
| **EMP** | Elektrické „bzzzt" (sawtooth + distortion) | EMP vysavač aktivuje pulz |
| **Smrt nepřítele** | Mechanický „klik-crack" (noise + pitch down) | Vysavač umírá |
| **Boss příchod** | Hluboký rumble (3 s, low freq) | BOSS vstupuje na mapu |
| **Poškození babičky** | Babičcino „Ježišmarjá!" (melodický pattern) | Vysavač projde obranou |
| **Nákup věže** | Veselo „ding" (ascending tones) | Hráč koupí věž |
| **Upgrade** | Vzestupná melodie (3 tóny nahoru) | Hráč upgraduje věž |
| **Prodej** | Mince cinknutí (short metallic) | Hráč prodá věž |
| **Výhra** | Vítězná fanfára (8-tónová melodie) | Hráč vyhraje mapu |
| **Prohra** | Smutný sestup (3 tóny dolů) | Game over |
| **Nová vlna** | Varovná siréna (2× ascending beep) | Vlna začíná |
| **Tlačítko hover** | Jemný „tick" | Myš najede na tlačítko |

### Hudba na pozadí
Jednoduchá procedurálně generovaná ambientní smyčka:
- Pomalé akordy (C-Am-F-G) hrané sinusovými vlnami.
- Tichá, neruší při hraní.
- Zvyšuje tempo během boss vln.
- Lze vypnout v nastavení.

---

## Příloha A: Counter systém (kdo je silný proti komu)

| Nepřítel | Silný counter | Proč |
|----------|---------------|------|
| Roomba Basic | Mourek, Micinka | Levné, stačí základní DPS |
| Roomba Turbo | Perská + Micinka | Zpomalit, pak rychle sejmout |
| Průmyslový | Černá kočka + Siamka | DoT tiká dlouho, Siamka dává velký dmg |
| Mini vysavač (swarm) | Garfield | AoE zasáhne celou skupinu |
| Stealth Roomba | Sfinx (odhalení) | Bez Sfinx je téměř nezasáhnutelná |
| EMP vysavač | Siamka (dlouhý dosah) | Střílí z bezpečné vzdálenosti mimo EMP pulz |
| Létající Dyson | Siamka + Perská | Dosah + zpomalení (ač snížené) |
| BOSS: Mega 3000 | Mainská Lvl 3 + Sfinx + vše | Chycení + buff + soustředěná palba |

---

## Příloha B: Vzorové synergické sestavy věží

### „Killzone" (nejefektivnější shluk)
```
        [Perská]
  [Siamka]  [Sfinx]  [Garfield]
        [Mainská]
```
Perská zpomalí → Mainská chytí → Sfinx buffne všechny → Garfield + Siamka sejmou.

### „Budget early game"
```
  [Micinka] [Mourek] [Micinka]
```
Nízká cena, solidní DPS. Přežije prvních 3–4 vln.

### „Anti-Stealth"
```
  [Sfinx] [Černá] [Mourek]
```
Sfinx odhalí → Černá otráví → Mourek dobije.

---

## Příloha C: Balancing úvahy

### DPS-per-coin efektivita (Lvl 1)

| Věž | DPS | Cena | DPS/🧶 | Efektivní role |
|-----|-----|------|--------|----------------|
| Micinka | 12,5 | 30 | 0,42 | Nejefektivnější raw DPS za cenu |
| Mourek | 10,0 | 50 | 0,20 | Univerzální |
| Garfield | 15,0+ | 120 | 0,13 | AoE to kompenzuje |
| Černá | ~20 | 90 | 0,22 | Silná proti pomalým |
| Siamka | 15,0 | 100 | 0,15 | Dosah to kompenzuje |
| Perská | 5,0 | 80 | 0,06 | Utility, ne DPS |
| Mainská | 15,0 | 150 | 0,10 | CC hodnota |
| Sfinx | 0 | 110 | — | Force multiplier |

**Záměr:** Micinka je nejlepší „na papíře", ale krátký dosah ji omezuje. Drahé věže mají utility, která čísla neodráží.
