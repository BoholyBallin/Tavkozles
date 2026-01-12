# Kapcsolás összefoglalása

A kapcsolás egy **egyszerű egyenáramú soros ellenállásos áramkör**, amely egy feszültségforrásból és két sorosan kapcsolt ellenállásból áll.

## Fő elemek
- Egyenfeszültség-forrás
- Két soros ellenállás
- Az áramerősség az áramkör minden pontján azonos

A kapcsolás célja a feszültség megosztása az ellenállások között, valamint az áram meghatározása Ohm törvénye alapján.

---

## Kapcsolási rajz (logikai leírás)

+5 V ── R1 (2 kΩ) ── R2 (1.5 kΩ) ── 0 V

---

## Alkatrészlista (BOM)

| Jelölés | Alkatrész        | Érték |
|-------|------------------|-------|
| R1    | Ellenállás       | 2 kΩ  |
| R2    | Ellenállás       | 1.5 kΩ |
| U1    | Feszültségforrás | 5 V DC |

---

## Számított / mért értékek

### Összellenállás

\[
R_{össz} = R_1 + R_2 = 2000\ \Omega + 1500\ \Omega = 3500\ \Omega
\]

---

### Áramerősség

Ohm törvénye alapján:

\[
I = \frac{U}{R_{össz}} = \frac{5\ \text{V}}{3500\ \Omega} \approx 1.43\ \text{mA}
\]

---

### Feszültségesés az ellenállásokon

**R1 (2 kΩ):**

\[
U_{R1} = I \cdot R_1 = 1.43\ \text{mA} \cdot 2000\ \Omega \approx 2.86\ \text{V}
\]

**R2 (1.5 kΩ):**

\[
U_{R2} = I \cdot R_2 = 1.43\ \text{mA} \cdot 1500\ \Omega \approx 2.14\ \text{V}
\]

**Ellenőrzés:**

\[
U_{R1} + U_{R2} \approx 5\ \text{V}
\]

---

### Teljesítménydiszipáció

**R1:**

\[
P_{R1} = I^2 \cdot R_1 \approx 4.1\ \text{mW}
\]

**R2:**

\[
P_{R2} = I^2 \cdot R_2 \approx 3.1\ \text{mW}
\]

**Feszültségforrás:**

\[
P = U \cdot I \approx 5\ \text{V} \cdot 1.43\ \text{mA} \approx 7.15\ \text{mW}
\]

---

## Következtetés

- A kapcsolás helyesen működik
- Az áram kb. **1.4 mA**
- A veszteségek kicsik
- Szabványos **¼ W-os ellenállások** bőven elegendőek
- Klasszikus példa soros ellenállásos feszültségosztóra
