# Deník AI selhání
## Projekt: Kočka vs. Vysavač

Během vývoje hry Kočka vs. Vysavač jsme využívali umělou inteligenci jako pomocníka při programování, tvorbě herních mechanik a úpravách grafiky. AI nám výrazně urychlila práci, ale ne vždy vytvořila správné řešení. Některé její výstupy způsobily chyby, které jsme museli odhalit a následně opravit.

### 1. Nefunkční pokládání věží

**Co jsme chtěli:**  
Upravit systém pokládání koček na herní mapu tak, aby hráč mohl jednoduše vybrat kočku a umístit ji na volné místo.

**Co AI udělala špatně:**  
Po úpravách přestalo pokládání věží správně fungovat. Kočky se někdy nedaly umístit na mapu nebo systém nereagoval podle očekávání.

**Jak jsme chybu odhalili:**  
Při testování hry jsme zjistili, že hráč nemůže spolehlivě umisťovat obranné jednotky.

**Jak jsme chybu opravili:**  
Nechali jsme AI znovu zkontrolovat systém pokládání věží a opravit jeho logiku. Poté jsme testovali umisťování koček na různá místa mapy.

### 2. Poškození hlavního menu

**Co jsme chtěli:**  
Vylepšit vzhled hlavního menu a vytvořit zajímavější úvodní obrazovku s tlačítkem pro spuštění hry.

**Co AI udělala špatně:**  
Při úpravách narušila funkčnost hlavního menu. Některé prvky nereagovaly a chybělo tlačítko Hrát.

**Jak jsme chybu odhalili:**  
Po spuštění hry jsme zjistili, že se nemůžeme běžným způsobem dostat do výběru mapy.

**Jak jsme chybu opravili:**  
Zadali jsme AI, aby zkontrolovala celé hlavní menu, obnovila funkčnost tlačítek a ověřila přechody mezi jednotlivými obrazovkami.

### 3. Chybné grafické rozložení map

**Co jsme chtěli:**  
Upravit grafické rozložení herních map tak, aby byly správně vycentrované a nábytek byl umístěný na vhodných volných místech.

**Co AI udělala špatně:**  
Mapy nebyly správně vycentrované a některé grafické prvky byly rozmístěné nevhodně. Nábytek někdy překážel nebo působil náhodně umístěně.

**Jak jsme chybu odhalili:**  
Při prohlížení jednotlivých map jsme si všimli, že prostředí nepůsobí vyváženě a některé části byly přeplněné.

**Jak jsme chybu opravili:**  
Upřesnili jsme zadání a požadovali správné vycentrování map, jednotné odsazení a umístění dekorací pouze na vhodná volná místa.

### 4. Zamrznutí hry po spuštění

**Co jsme chtěli:**  
Zajistit, aby hra po spuštění správně načetla všechny potřebné prvky a umožnila hráči okamžitě začít hrát.

**Co AI udělala špatně:**  
Po některých úpravách hra po spuštění zamrzla. Obrazovka se zobrazila, ale herní prvky nereagovaly a nebylo možné pokračovat.

**Jak jsme chybu odhalili:**  
Při spuštění hry jsme zjistili, že nefungují tlačítka ani další interaktivní prvky.

**Jak jsme chybu opravili:**  
Nechali jsme AI zkontrolovat inicializaci hry a její JavaScriptové funkce. Po opravě jsme znovu otestovali spuštění a přechod do hry.

### 5. Nesprávné rozmístění a řazení koček

**Co jsme chtěli:**  
Upravit nabídku koček tak, aby byly přehledně seřazené podle ceny a hráč se v nich snadno orientoval.

**Co AI udělala špatně:**  
Kočky nebyly správně seřazené a jejich rozmístění v nabídce nebylo dostatečně přehledné. Některé prvky se nevešly do vyhrazeného prostoru.

**Jak jsme chybu odhalili:**  
Při testování nabídky jsme zjistili, že pořadí koček neodpovídá jejich cenám a rozložení působí neuspořádaně.

**Jak jsme chybu opravili:**  
Upřesnili jsme požadavky na řazení podle ceny a požadovali úpravu rozložení tak, aby byly všechny kočky dobře viditelné.

### 6. Narušení kompatibility mezi systémy

**Co jsme chtěli:**  
Zajistit, aby hra fungovala na počítačích s Windows i macOS.

**Co AI udělala špatně:**  
Při některých úpravách nebylo správně zohledněno rozdílné zobrazování a ovládání na různých zařízeních. Některé prvky se mohly zobrazovat jinak nebo nebyly správně přizpůsobené velikosti okna.

**Jak jsme chybu odhalili:**  
Hru jsme vyzkoušeli na různých zařízeních a všimli jsme si rozdílů v rozložení a zobrazování prvků.

**Jak jsme chybu opravili:**  
Požádali jsme AI o úpravu responzivního rozložení a kontrolu kompatibility. Následně jsme hru znovu vyzkoušeli na Windows i macOS.

---

## Závěr

Při vývoji jsme zjistili, že umělá inteligence může při úpravách jedné části projektu nechtěně poškodit jinou, již funkční část hry. Někdy také špatně pochopí zadání nebo vytvoří řešení, které nefunguje podle našich představ. Proto je důležité každou větší změnu důkladně otestovat. Naučili jsme se přesněji formulovat zadání, kontrolovat výsledný kód a nepřebírat automaticky vše, co AI vytvoří.
