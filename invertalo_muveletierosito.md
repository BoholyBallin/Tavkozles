# Projekt Dokumentáció: Fázisfordító Erősítő Vizsgálata

**Dátum:** 2024
**Típus:** Áramkör szimuláció és elemzés

## 1. A projekt célja
A feladat egy műveleti erősítős alapkapcsolás, konkrétan egy fázisfordító erősítő (inverting amplifier) működésének bemutatása, a feszültségerősítés számítása és a szimulációs eredmények igazolása. Az áramkör egy **TL071** típusú műveleti erősítőre épül.

## 2. Felhasznált alkatrészek és paraméterek

Az áramkör az alábbi komponensekből épül fel (balról jobbra, fentről lefelé haladva):

| Jelölés | Alkatrész | Érték / Típus | Funkció |
| :--- | :--- | :--- | :--- |
| **R1** | Ellenállás | $9.1\text{ k}\Omega$ | Bemeneti ellenállás ($R_{in}$) |
| **R2** | Ellenállás | $99.9\text{ k}\Omega$ | Visszacsatoló ellenállás ($R_f$) |
| **R3** | Ellenállás | $10\text{ k}\Omega$ | Kompenzáló ellenállás a nem-invertáló lábon |
| **U_be** | Feszültségforrás | $1\text{ V}$ | Bemeneti jel (DC) |
| **IC1** | Műveleti erősítő | TL071 | Aktív erősítő elem (JFET bemenetű) |

## 3. Elméleti háttér és Számítások

A fázisfordító erősítő kimeneti feszültségét az alábbi képlet határozza meg:

$$U_{ki} = -U_{be} \cdot \frac{R_f}{R_{in}}$$

Ahol:
* $R_f = R_2 = 99.9\text{ k}\Omega$
* $R_{in} = R_1 = 9.1\text{ k}\Omega$

### 3.1 Az erősítés ($A_u$) kiszámítása:

$$A_u = -\frac{99.9\text{ k}\Omega}{9.1\text{ k}\Omega} \approx -10.978$$

Tehát az áramkör elméleti feszültségerősítése kb. **-11-szeres**.

### 3.2 A kimeneti feszültség számítása:
Ha a bemenetre $1\text{ V}$ nagyságú feszültséget kapcsolunk:

$$U_{ki} = 1\text{ V} \cdot (-10.978) = -10.978\text{ V}$$

*(Megjegyzés: A szimulációs képen a kimenet pozitív $10.977\text{ V}$, ami arra utal, hogy a szimulációban a bemeneti feszültség polaritása negatív volt ($-1\text{ V}$), mivel a fázisfordító kapcsolás megfordítja az előjelet.)*

## 4. Mérési / Szimulációs eredmények

A szimulátor által mért érték a kimeneten:

> **Mért $U_{ki}$:** $10.977\text{ V}$

### Összegzés
A számított elméleti érték ($10.978\text{ V}$) és a szimulált érték ($10.977\text{ V}$) közötti eltérés elhanyagolható (hibahatáron belüli), így az áramkör a várakozásoknak megfelelően, helyesen működik. A kapcsolás stabilan biztosítja a beállított, közel 11-szeres erősítést.
