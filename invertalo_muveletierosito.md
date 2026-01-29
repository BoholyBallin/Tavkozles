# Projekt Dokumentáció: Fázisfordító Erősítő Vizsgálata

**Dátum:** 2024
**Típus:** Áramkör szimuláció és elemzés

## 1. A projekt célja
A feladat egy műveleti erősítős alapkapcsolás, konkrétan egy fázisfordító erősítő (inverting amplifier) működésének bemutatása, a feszültségerősítés számítása és a szimulációs eredmények igazolása. Az áramkör egy **TL071** típusú műveleti erősítőre épül.

## 2. Felhasznált alkatrészek és paraméterek

Az áramkör az alábbi komponensekből épül fel (a frissített kapcsolási rajz alapján):

| Jelölés | Alkatrész | Érték / Típus | Funkció |
| :--- | :--- | :--- | :--- |
| **R1** | Ellenállás | $14.1\text{ k}\Omega$ | Bemeneti ellenállás ($R_{in}$) |
| **R2** | Ellenállás | $99.9\text{ k}\Omega$ | Visszacsatoló ellenállás ($R_f$) |
| **R3** | Ellenállás | $12\text{ k}\Omega$ | Kompenzáló ellenállás a nem-invertáló lábon |
| **U_be** | Feszültségforrás | $1\text{ V}$ | Bemeneti jel (DC) |
| **IC1** | Műveleti erősítő | TL071 | Aktív erősítő elem (JFET bemenetű) |

## 3. Elméleti háttér és Számítások

A fázisfordító erősítő kimeneti feszültségét az alábbi képlet határozza meg:

$$U_{ki} = -U_{be} \cdot \frac{R_f}{R_{in}}$$

Ahol:
* $R_f = R_2 = 99.9\text{ k}\Omega$
* $R_{in} = R_1 = 14.1\text{ k}\Omega$
* $U_{be} = 1\text{ V}$

### 3.1 Az erősítés ($A_u$) kiszámítása:

$$A_u = -\frac{99.9\text{ k}\Omega}{14.1\text{ k}\Omega} \approx -7.085$$

Tehát az áramkör elméleti feszültségerősítése kb. **-7.085-szeres**.

### 3.2 A kimeneti feszültség számítása:
Mivel a kapcsolás fázisfordító, a pozitív bemenő jelre ($1\text{ V}$) negatív kimenő jelet kapunk:

$$U_{ki} = 1\text{ V} \cdot (-7.085) = -7.085\text{ V}$$

## 4. Mérési / Szimulációs eredmények

A szimulátorban a voltmérő kijelzőjén $7.085\text{ V}$ olvasható.

**Eredmények értelmezése:**
* **Számított érték:** $-7.085\text{ V}$
* **Mért érték (abszolút):** $7.085\text{ V}$

**Megjegyzés:** A szimulációs képen a voltmérő pozitív értéket mutat. Ennek oka a műszer bekötési iránya (a referenciapont a földhöz képest). Fizikailag a kimeneten negatív feszültség jelenik meg (fázisfordítás), de az abszolút érték ($7.085$) tizedes pontossággal megegyezik az elméleti számítással.

### Összegzés
A számított elméleti erősítés és a szimulált feszültségérték tökéletesen egyezik. Az $R_1$ ellenállás $14.1\text{ k}\Omega$-ra történő növelése (az előző méréshez képest) csökkentette az erősítés mértékét kb. 11-szeresről 7-szeresre, ami igazolja az erősítés képletét: a bemeneti ellenállás növelése csökkenti a kimeneti jelszintet.
