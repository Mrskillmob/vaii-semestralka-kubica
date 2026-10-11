# E-shop s elektronikou – ElectroShop

**Meno a priezvisko študenta:** Martin Kubica

**Študijná skupina:** 5ZYI35

## Stručný opis projektu

Cieľom projektu je vytvoriť dynamickú webovú aplikáciu predstavujúcu internetový obchod zameraný na predaj elektroniky a počítačového príslušenstva.
Aplikácia umožní návštevníkom prehliadať ponuku produktov, vyhľadávať ich podľa názvu, filtrovať podľa kategórií a zobrazovať podrobné informácie o jednotlivých produktoch.

Registrovaní používatelia budú môcť pridávať produkty do nákupného košíka, vytvárať objednávky a sledovať ich stav. Administrátor bude zodpovedný za správu produktov, kategórií a objednávok. 
Hlavným cieľom je vytvoriť funkčný internetový obchod s prehľadným používateľským rozhraním a administrátorskou časťou.

## Role v projekte

### Návštevník
- Prehliadanie katalógu produktov.
- Vyhľadávanie a filtrovanie produktov.
- Zobrazenie detailov jednotlivých produktov.
- Registrácia a prihlásenie do systému.

### Registrovaný zákazník
- Všetky oprávnenia návštevníka.
- Správa vlastného nákupného košíka.
- Vytváranie objednávok.
- Prehliadanie histórie vlastných objednávok.
- Zobrazenie a úprava svojich profilových údajov.

### Administrátor
- Správa produktov (vytvorenie, zobrazenie, úprava, odstránenie).
- Správa kategórií produktov.
- Správa objednávok a ich stavov.
- Nahrávanie a zmena obrázkov produktov.
- Prehliadanie registrovaných zákazníkov.

## Prípady použitia podľa rolí

### Návštevník
- Návštevník zobrazí zoznam dostupných produktov.
- Návštevník vyhľadá produkt podľa názvu.
- Návštevník filtruje produkty podľa kategórie alebo ceny.
- Návštevník zobrazí detail produktu.
- Návštevník si vytvorí používateľský účet.
- Návštevník sa prihlási do aplikácie.

### Registrovaný zákazník
- Zákazník pridá produkt do nákupného košíka.
- Zákazník upraví množstvo produktov v košíku.
- Zákazník odstráni produkt z košíka.
- Zákazník vytvorí objednávku.
- Zákazník zobrazí históriu svojich objednávok.
- Zákazník zobrazí detail a stav objednávky.
- Zákazník upraví údaje svojho profilu.

### Administrátor
- Administrátor pridá nový produkt do ponuky.
- Administrátor upraví informácie o existujúcom produkte.
- Administrátor odstráni produkt z ponuky.
- Administrátor vytvorí, upraví alebo odstráni kategóriu.
- Administrátor nahrá obrázok k produktu.
- Administrátor zobrazí všetky objednávky.
- Administrátor zmení stav objednávky.
- Administrátor zobrazí zoznam registrovaných zákazníkov.

## Plánované entity

### 1. Používateľ (User)
Reprezentuje registrovaného zákazníka alebo administrátora.

**Atribúty:**
- id
- meno
- email
- heslo (hash)
- rola
- dátum registrácie

### 2. Produkt (Product)
Reprezentuje produkt dostupný v internetovom obchode.

**Atribúty:**
- id
- názov
- popis
- cena
- skladové množstvo
- obrázok
- category_id

### 3. Kategória (Category)
Slúži na rozdelenie produktov do skupín, napríklad notebooky, monitory, klávesnice alebo myši.

**Atribúty:**
- id
- názov
- popis

### 4. Objednávka (Order)
Uchováva informácie o objednávke vytvorenej zákazníkom.

**Atribúty:**
- id
- user_id
- dátum vytvorenia
- celková cena
- stav objednávky
- doručovacia adresa

### 5. Položka objednávky (OrderItem)
Predstavuje konkrétny produkt zahrnutý v objednávke.

**Atribúty:**
- id
- order_id
- product_id
- množstvo
- jednotková cena v čase objednávky

### 6. Košíková položka (CartItem)
Uchováva produkty, ktoré má registrovaný zákazník momentálne vo svojom nákupnom košíku.

**Atribúty:**
- id
- user_id
- product_id
- množstvo

## Vzťahy medzi entitami

- **Používateľ – Objednávka (1:N):** Jeden používateľ môže vytvoriť viacero objednávok, ale každá objednávka patrí jednému používateľovi.
- **Kategória – Produkt (1:N):** Jedna kategória môže obsahovať viacero produktov. Produkt patrí do jednej kategórie.
- **Objednávka – Položka objednávky (1:N):** Jedna objednávka obsahuje jednu alebo viac položiek.
- **Produkt – Položka objednávky (1:N):** Jeden produkt môže byť súčasťou viacerých objednávkových položiek.
- **Objednávka – Produkt (M:N):** Jedna objednávka môže obsahovať viacero produktov a jeden produkt môže byť súčasťou viacerých objednávok. Vzťah je realizovaný prostredníctvom entity OrderItem.
- **Používateľ – Košíková položka (1:N):** Používateľ môže mať v košíku viacero položiek.
- **Produkt – Košíková položka (1:N):** Jeden produkt sa môže nachádzať v košíkoch viacerých používateľov.

## Hlavné stránky aplikácie

1. **Úvodná stránka** – predstavenie internetového obchodu, zobrazenie vybraných produktov a kategórií.
2. **Katalóg produktov** – zoznam produktov s možnosťou vyhľadávania, filtrovania a zoradenia.
3. **Detail produktu** – podrobné informácie o produkte, obrázok, cena, skladová dostupnosť a možnosť pridania do košíka.
4. **Nákupný košík** – zobrazenie vybraných produktov, úprava množstva a celkovej ceny.
5. **Dokončenie objednávky** – zadanie doručovacích údajov a potvrdenie objednávky.
6. **Prihlásenie a registrácia** – autentifikácia používateľov a vytváranie nových účtov.
7. **Používateľský profil** – správa osobných údajov a história objednávok.
8. **Administrácia produktov** – vytváranie, úprava a odstraňovanie produktov.
9. **Administrácia kategórií** – správa produktových kategórií.
10. **Administrácia objednávok** – prehliadanie objednávok a zmena ich stavov.

## Rozdelenie funkcionality

### Základné funkcie
- Registrácia a prihlásenie používateľov.
- Rozlíšenie používateľských rolí a kontrola oprávnení.
- Zobrazenie katalógu produktov a detailov produktov.
- Vyhľadávanie a filtrovanie produktov.
- Správa produktov a kategórií pomocou CRUD operácií.
- Nákupný košík s možnosťou pridávania, úpravy množstva a odstraňovania produktov.
- Vytváranie objednávok a zobrazenie ich histórie.
- Správa objednávok administrátorom.
- Nahrávanie obrázkov produktov.
- Asynchrónne vyhľadávanie produktov pomocou AJAX.
- Asynchrónna aktualizácia nákupného košíka pomocou AJAX.
- Spustenie aplikácie prostredníctvom Docker Compose vrátane databázy a počiatočných údajov.

### Rozširujúce funkcie
- Hodnotenie a recenzie produktov.
- Zoznam obľúbených produktov.
- Stránkovanie a pokročilé triedenie produktov.
- Viacero obrázkov pre jeden produkt.
- Grafy vývoja objednávok.