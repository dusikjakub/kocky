ą# 🐱 Kočky vs. Vysavače (Vintage 8-Bit TD)

> **2D Tower Defense hra v retro pixel-art stylu vytvořená v čistém HTML5 Canvas a JavaScriptu bez externích knihoven.**

---

## 📖 Popis hry

V poklidném domově babičky Boženy došlo ke vzpouře robotických vysavačů! Zblázněné stroje všech tvarů a velikostí se snaží dostat k jejímu oblíbenému gauči a babičku vysát. Naštěstí má babička věrnou armádu koček, které neváhají použít své drápky, speciální schopnosti a dokonce i létající lasagne, aby babičku ubránily.

Hráč staví a vylepšuje kočičí věže podél cest, kudy se vysavače valí. Cílem je přežít všechny vlny nepřátel, ochránit babiččino zdraví a vyčistit celý dům od přemnožených robotů.

### Hlavní prvky hry:
* **8 unikátních kočičích věží** s odlišnými mechanikami (přímý útok, rychlopalba, plošný dopad AoE, zpomalení, sniper z dálky, poškození v čase DoT, omráčení/chycení, podpůrná aura odhalující neviditelné).
* **8 rozmanitých typů robotických nepřátel** včetně rychlých jednotek, těžkých tanků, swarm rojů, maskovaných stealth vysavačů, EMP vysavačů vyřazujících věže, létajících Dysonů a obřích bossů.
* **3 propracované mapy s rostoucí obtížností**:
  * 🛋️ *Obývací pokoj* (1 cesta, 10 vln – pro seznámení se základními mechanikami)
  * 🍳 *Kuchyně* (2 spojující se cesty, 15 vln – rozdělení obrany)
  * 🏠 *Celý byt* (3 sbíhající se cesty, 20 vln – maximální strategická výzva)
* **Ekonomický systém**: Odměny v podobě klubíček (🧶) za každého zničeného nepřítele a bonusy po vlnách, možnost upgradů věží na 3 úrovně nebo prodej se 60% návratností.
* **Čistá procedurální grafika a zvuk**: Kompletní vizuál kreslený v HTML5 Canvas v retro 8-bit stylu a zvuky generované v reálném čase přes Web Audio API bez nutnosti stahovat assety.

---

## 🎮 Ovládání hry

Hru lze plnohodnotně ovládat myší i pomocí klávesových zkratek:

### Ovládání myší:
* **Výběr kočky z nabídky:** Kliknutí levým tlačítkem myši na ikonu kočky ve spodní liště.
* **Umístění kočky:** Kliknutí na volné zeleně zvýrazněné stavební pole na mapě.
* **Zrušení výběru / zavření nabídky:** Pravé tlačítko myši nebo kliknutí mimo pole.
* **Správa postavené kočky:** Kliknutí na postavenou kočku otevře kontextové menu pro vylepšení (Upgrade) nebo prodej (Prodat).
* **Spuštění vlny:** Kliknutí na tlačítko `DALŠÍ VLNA!` v pravém dolním rohu.
* **Zrychlení hry:** Přepínač rychlosti `1× / 2×` pro svižnější průběh.
* **Nápověda (Tooltip):** Najetí myší nad kočku v obchodě zobrazí detailní statistiky a schopnosti.

### Klávesové zkratky:
| Klávesa | Akce |
|---------|------|
| `1` – `8` | Rychlý výběr kočičí věže z obchodu |
| `Mezerník (Space)` | Spuštění další vlny / Pauza |
| `U` | Vylepšení (Upgrade) označené věže |
| `S` | Prodej (Sell) označené věže |
| `Escape` | Zrušení aktuálního výběru / zavření menu |

---

## 🚀 Postup spuštění

Hra nevyžaduje žádnou instalaci, build nástroje ani externí závislosti. Lze ji okamžitě spustit na libovolném moderním operačním systému (Windows, macOS, Linux).

### Rychlé spuštění:
1. Stáhněte nebo naklonujte tento repozitář:
   ```bash
   git clone <URL_REPOZITÁŘE>
   ```
2. Otevřete soubor `index.html` v libovolném moderním webovém prohlížeči (Google Chrome, Firefox, Safari, Microsoft Edge):
   * Dvojklikem na soubor `index.html` ve správci souborů.
   * Nebo přetažením souboru `index.html` do otevřeného okna prohlížeče.

### Spuštění přes lokální HTTP server (volitelné):
Pokud preferujete běh na lokálním serveru:
* **Python 3:**
  ```bash
  python3 -m http.server 8000
  ```
  Následně otevřete v prohlížeči adresu `http://localhost:8000`.
* **VS Code:**
  Klikněte pravým tlačítkem na `index.html` a zvolte *Open with Live Server*.

---

## 🛠️ Použité technologie

Projekt je postaven na moderních webových standardech s důrazem na nulovou závislost na externích knihovnách a frameworks:
* **HTML5:** Sémantická struktura a prvek `<canvas>` sloužící jako hlavní vykreslovací plocha.
* **CSS3:** Retro herní rámeček (arcade cabinet styl), responzivní centrování a integrace pixelových fontů (*Press Start 2P*, *VT323*).
* **Vanilla JavaScript (ES6+):**
  * Herní smyčka (`requestAnimationFrame`) s delta-time kalkulací pro plynulý běh na různých obnovovacích frekvencích (60Hz, 120Hz, 144Hz).
  * Vlastní matematický a kolizní engine (detekce dosahu, interpolace cest po waypointech, kruhové a AABB kolize).
  * Stavový automat hry (Hlavní menu, Výběr mapy, Herní smyčka, Victory / Game Over obrazovky).
* **HTML5 Canvas 2D API:** Procedurální pixelové a vektorové vykreslování herních postav, projektilů, částicových efektů (particles), map a uživatelského rozhraní.
* **Web Audio API:** Procedurální syntezátor generující zvukové efekty (bílé šumy, pilové vlny, modulované frekvence) a ambientní podkres bez nutnosti externích audio souborů.

---

## 🧪 Testy a ruční testovací scénář

Pro ověření stability a hratelnosti byl navržen a proveden následující testovací scénář:

### Ruční testovací scénář (Akceptační testy):

| ID | Testovaný krok | Očekávaný výsledek | Stav |
|----|----------------|--------------------|------|
| **TC01** | Spuštění hry v prohlížeči | Zobrazí se hlavní menu s animovaným titulkem a tlačítky Hrát, Návod, Nastavení. | ✅ Prošlo |
| **TC02** | Výběr první mapy (Obývací pokoj) | Načte se mapa, zobrazí se počáteční stav (200 🧶, 20 ❤️ babičky) a stavební pole. | ✅ Prošlo |
| **TC03** | Umístění věže (Mourek) | Po kliknutí na ikonu a zelené pole se věž správně postaví a odečte se 50 🧶. | ✅ Prošlo |
| **TC04** | Validace zakázaného umístění | Věž nelze postavit mimo stavební pole, na obsazené pole ani při nedostatku klubíček. | ✅ Prošlo |
| **TC05** | Spuštění 1. vlny a útok | Po stisku tlačítka nebo mezerníku vyjedou vysavače; kočka automaticky útočí a projektily udělují poškození. | ✅ Prošlo |
| **TC06** | Smrt nepřítele a ekonomika | Zničený vysavač spustí částicový efekt a přičte hráči klubíčka do rozpočtu. | ✅ Prošlo |
| **TC07** | Průchod nepřítele do cíle | Pokud vysavač dosáhne konce cesty, zmizí a odečte babičce odpovídající počet životů. | ✅ Prošlo |
| **TC08** | Upgrade a prodej věže | Kliknutí na postavenou kočku umožní upgrade (zvýší dosah/poškození) i prodej (vrátí 60 % investice). | ✅ Prošlo |
| **TC09** | Speciální schopnosti věží | Perská kočka zpomaluje, Garfield uděluje plošný zásah, Sfinx odhaluje neviditelné Stealth vysavače. | ✅ Prošlo |
| **TC10** | Podmínky konce hry | Při poklesu životů na 0 nastává Game Over s možností restartu; po poražení všech vln nastává Victory obrazovka s hvězdami. | ✅ Prošlo |
| **TC11** | Responzivita a cross-platform běh | Hra funguje plynule na macOS i Windows v běžných rozlišeních i velikostech oken. | ✅ Prošlo |

---

## 👥 Tým a organizace projektu

Projekt vznikl v rámci týmové vývojové práce s využitím verzovacího systému Git a asistovaného vývoje pomocí AI.

* **Design dokument:** Kompletní specifikace mechanik, jednotek, balancingu a map je v souboru [`DESIGN.md`](./DESIGN.md).
* **Deník selhání AI a retrospektiva:** Zaznamenány v samostatných individuálních dokumentech (např. řešení problémů s pokládáním věží, menu, centrovaním map a multiplatformní kompatibilitou).
* **Git workflow:** Čistá commit historie, kde každý člen týmu vystupuje pod svým jménem a vlastními commity.
