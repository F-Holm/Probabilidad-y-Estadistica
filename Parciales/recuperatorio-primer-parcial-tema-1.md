# Recuperatorio del 1.er Parcial — Tema 1 (16/07/2026)

Probabilidad y Estadística — UTN FRBA.

> **Aprobación:** al menos 2 de los primeros 4 puntos correctamente resueltos.
> **Promoción:** aprobación + el punto V o el VI correctamente resuelto. Los puntos V y VI sólo se corrigen si se alcanza la aprobación.

Cada ejercicio tiene un botón **Solución**. Al abrirlo aparece la respuesta y, arriba de ella, el botón **Solución paso a paso**.

---

### I) Aeronaves desaparecidas

El 70 % de las aeronaves ligeras que desaparecen en vuelo en cierto país son posteriormente localizadas. De las aeronaves localizadas, el 60 % cuenta con un localizador de emergencia, mientras que el 90 % de las no localizadas no cuenta con dicho localizador. Suponga que una aeronave ligera ha desaparecido. Si tiene un localizador de emergencia, ¿cuál es la probabilidad de que no sea localizada?

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

**Sucesos:** L = "es localizada", E = "tiene localizador de emergencia".

**Datos:** P(L) = 0,7 y $P(\bar L) = 0,3$; P(E/L) = 0,6; $P(\bar E/\bar L) = 0{,}9 \Rightarrow P(E/\bar L) = 0{,}1$.

**Probabilidad total:** $P(E) = 0{,}7\cdot0{,}6 + 0{,}3\cdot0{,}1 = 0{,}42 + 0{,}03 = 0{,}45$.

**Bayes:**
$$P(\bar L/E) = \frac{P(E/\bar L)P(\bar L)}{P(E)} = \frac{0{,}03}{0{,}45} = \frac1{15} \approx 0{,}067$$

</details>

**Respuesta:** $P(\bar L/E) \approx 0{,}067$

</details>

---

### II) Tablas de álamo

El espesor de ciertas tablas de madera de álamo se distribuye uniformemente entre 19,5 y 20,5 mm. Si se observan al azar 4 de estas tablas, ¿cuál es la probabilidad de que alguna de ellas supere los 20,1 mm de espesor?

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

**1. Una tabla.** X ~ U(19,5; 20,5):
$p = P(X > 20{,}1) = \frac{20{,}5 - 20{,}1}{20{,}5 - 19{,}5} = 0{,}4$

**2. Cuatro tablas.** W = tablas que superan 20,1 mm ~ Bin(4; 0,4):
$P(W \ge 1) = 1 - P(W = 0) = 1 - 0{,}6^4 = 1 - 0{,}1296 = 0{,}8704$

</details>

**Respuesta:** 0,8704

</details>

---

### III) Grupo de TP

En un curso de PyE hay 10 mujeres y 40 varones. Se elige al azar un grupo de 12 estudiantes para realizar un TP. ¿Cuál es la probabilidad de que en el grupo haya más mujeres que varones?

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

X = cantidad de mujeres en el grupo ~ **H(N = 50, K = 10, n = 12)** (sin reposición).

"Más mujeres que varones" con 12 personas ⇔ X > 6 ⇔ X ≥ 7. Como sólo hay 10 mujeres, X va de 7 a 10:
$$P(X \ge 7) = \sum_{k=7}^{10}\frac{\binom{10}{k}\binom{40}{12-k}}{\binom{50}{12}} \approx 0{,}00068$$

</details>

**Respuesta:** ≈ 0,00068

</details>

---

### IV) Vida útil de lámparas

La vida útil de ciertas lámparas es una v.a. con distribución exponencial. Se estima que el 35 % no supera las 4307,83 horas de vida. Se seleccionan 8 lámparas: calcular la probabilidad de que sólo 3 de ellas superen la vida media en más de 500 horas.

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

**1. Hallar λ.** $P(X \le 4307{,}83) = 0{,}35 \Rightarrow P(X > 4307{,}83) = e^{-4307{,}83\lambda} = 0{,}65$
$\lambda = \frac{\ln0{,}65}{-4307{,}83} \approx 10^{-4}$ h⁻¹ ⇒ $E(X) = 1/\lambda = 10000$ h.

**2. Una lámpara.** "Supera la vida media en más de 500 h" ⇔ X > 10500:
$p = P(X > 10500) = e^{-1{,}05} \approx 0{,}34994$

**3. Ocho lámparas.** W ~ Bin(8; 0,35):
$P(W = 3) = \binom83 0{,}35^3\,0{,}65^5 \approx 0{,}27859$

</details>

**Respuesta:** E(X) = 10000 h y $P(W = 3) \approx 0{,}2786$

</details>

---

### V) Esperanza y varianza de combinaciones

Sea X ~ Poisson(λ = 5), Y ~ N(μ = 4; σ = 2) y U ~ Uni(2; b) con desvío $\frac{6}{\sqrt{12}}$. Considerando que X, Y y U son independientes, hallar, indicando en cada paso la propiedad aplicada:
$$E(X^2 - 3Y + 4U) \quad\text{y}\quad V(4X - 2Y - U - 5)$$

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

**Parámetros de cada variable:**
- X ~ Po(5): E(X) = V(X) = 5 ⇒ $E(X^2) = V(X) + E(X)^2 = 5 + 25 = 30$
- Y ~ N(4; 2): E(Y) = 4, V(Y) = 4
- U ~ U(2; b): $V(U) = \frac{(b-2)^2}{12} = \frac{36}{12} = 3 \Rightarrow b - 2 = 6 \Rightarrow b = 8$; E(U) = (2 + 8)/2 = 5

**Esperanza** (linealidad: $E(aX + bY) = aE(X) + bE(Y)$ y $E(cX) = cE(X)$):
$E(X^2 - 3Y + 4U) = E(X^2) - 3E(Y) + 4E(U) = 30 - 12 + 20 = 38$

**Varianza** (por independencia, $V(aX + bY) = a^2V(X) + b^2V(Y)$; y $V(c) = 0$, así que la constante −5 no aporta):
$V(4X - 2Y - U - 5) = 16V(X) + 4V(Y) + V(U) = 16\cdot5 + 4\cdot4 + 3 = 99$

</details>

**Respuesta:** $E = 38$ y $V = 99$

</details>

---

### VI) Densidad con k y probabilidad condicional

Demostrar que $f(x) = 4kx + 1$ si 1 < x < 3 es una función de densidad de la v.a. X para algún valor de k, y calcular $P(X < 2 / X > 1{,}5)$ usando la función de distribución F(x).

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

**1. Área total igual a 1:**
$\int_1^3(4kx + 1)dx = (2kx^2 + x)\Big|_1^3 = (18k + 3) - (2k + 1) = 16k + 2 = 1 \Rightarrow k = -\frac1{16}$

Entonces $f(x) = 1 - \frac x4$. Además f ≥ 0 en (1, 3), ya que en x = 3 vale ¼ > 0. Es una densidad.

**2. Función de distribución** (en 1 < x < 3):
$F(x) = \int_1^x\left(1 - \frac t4\right)dt = -\frac{x^2}{8} + x - \frac78$, con F = 0 para x ≤ 1 y F = 1 para x ≥ 3.

**3. Condicional:**
$$P(X < 2 / X > 1{,}5) = \frac{P(1{,}5 < X < 2)}{P(X > 1{,}5)} = \frac{F(2) - F(1{,}5)}{1 - F(1{,}5)}$$
F(2) = −½ + 2 − ⅞ = 5/8 y F(1,5) = −9/32 + 3/2 − 7/8 = 11/32:
$$\frac{\frac{20}{32} - \frac{11}{32}}{\frac{21}{32}} = \frac9{21} = \frac37 \approx 0{,}4286$$

</details>

**Respuesta:** k = −1/16 y $P(X < 2 / X > 1{,}5) = 3/7$

</details>

---

[← Volver al menú principal](../../README.md)
