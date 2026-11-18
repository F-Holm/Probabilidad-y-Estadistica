# 2.º Parcial — Tema 1 (08/07/2026)

Probabilidad y Estadística — UTN FRBA. Enunciado original: [MODELO 2°PARCIAL.pdf](Fotos/MODELO%202%C2%B0PARCIAL.pdf) (página 1).

> **Aprobación:** al menos 2 de los primeros 4 puntos correctamente resueltos.
> **Promoción:** aprobación + al menos 2 de los últimos 4 puntos bien resueltos. Los puntos IV y V sólo se corrigen si se alcanza la aprobación.

Cada ejercicio tiene un botón **Solución**. Al abrirlo aparece la respuesta y, arriba de ella, el botón **Solución paso a paso**.

---

### I) Azúcar convertida según la temperatura

Se realizó un estudio sobre la cantidad de azúcar convertida en cierto proceso a distintas temperaturas. Los datos se codificaron y se obtuvo lo siguiente:

| Temp (x) | 1,1 | 1,2 | 1,3 | 1,4 | 1,5 | 1,6 | 1,7 | 1,8 | 1,9 |
|---|---|---|---|---|---|---|---|---|---|
| **Azúcar (y)** | 7,8 | 8,5 | 9,8 | 9,5 | 8,9 | 8,6 | 10,2 | 9,3 | 9,2 |

Analizar con un nivel de significación del 1 % la pertinencia del modelo de regresión lineal simple para explicar la cantidad de azúcar a partir de la temperatura. Si el modelo ajusta correctamente, determinar la cantidad media de azúcar si la temperatura es 1,65. Justificar.

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

**Sumas** (n = 9): $\sum x = 13{,}5$, $\sum y = 81{,}8$, $\sum x^2 = 20{,}85$, $\sum y^2 = 747{,}72$, $\sum xy = 123{,}49$.

**Cantidades básicas:** $\bar x = 1{,}5$ y $\bar y = 9{,}0889$.
- $S_{xx} = 20{,}85 - \frac{13{,}5^2}9 = 0{,}6$
- $S_{yy} = 747{,}72 - \frac{81{,}8^2}9 = 4{,}2489$
- $S_{xy} = 123{,}49 - \frac{13{,}5\cdot81{,}8}9 = 0{,}79$

**Recta estimada:** $b_1 = \frac{0{,}79}{0{,}6} = 1{,}3167$ y $b_0 = 9{,}0889 - 1{,}3167\cdot1{,}5 = 7{,}1139$ ⇒ $\hat y = 7{,}114 + 1{,}317x$.

**Test de correlación** (supuestos: errores normales, independientes y homocedásticos):
1. H₀: ρ = 0 vs. H₁: ρ ≠ 0.
2. α = 0,01.
3. $T = \frac{r\sqrt{n-2}}{\sqrt{1 - r^2}} \sim t_7$.
4. $r = \frac{0{,}79}{\sqrt{0{,}6\cdot4{,}2489}} = 0{,}4948$ ($R^2 = 0{,}245$) ⇒ $t_{obs} = \frac{0{,}4948\sqrt7}{\sqrt{1 - 0{,}2448}} = 1{,}506$.
5. RC = {|T| > $t_{7;\,0{,}995}$ = 3,4995}. Como 1,506 ∉ RC ⇒ no se rechaza H₀ (p = 0,176).

**Conclusión:** no hay evidencia de correlación lineal: el modelo **no es pertinente**. Como no ajusta, no corresponde usar la recta para estimar en x = 1,65 (daría $\hat y = 9{,}29$). Lo razonable es estimar la cantidad media de azúcar con $\bar y = 9{,}09$, sin depender de la temperatura.

</details>

**Respuesta:** $t_{obs}$ = 1,506 < 3,4995 ⇒ no se rechaza ρ = 0 al 1 %. El modelo lineal no es pertinente, así que no se estima con la recta en x = 1,65 (la media de azúcar se estima con $\bar y$ ≈ 9,09).

</details>

---

### II) Consumo de combustible

Se toma una muestra de consumo de combustible en un cierto modelo de coche, obteniéndose los siguientes datos (expresados en litros cada 100 km):

6,7 − 7,2 − 7,3 − 7,0 − 7,1 − 6,9 − 7,3 − 7,1 − 6,9 − 6,8

- a) Suponiendo que el consumo sigue una distribución normal, estimar mediante un intervalo de confianza al 98 % la **varianza** del consumo.
- b) Suponiendo que el desvío poblacional del consumo de combustible en el modelo de coche considerado es de 0,17 litros/100 km, ¿de qué tamaño debería ser la muestra para que el error máximo de estimación (d) en un intervalo de confianza para la media al 99 % sea de a lo sumo 0,05 litros/100 km?

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

a) n = 10, $\bar x = 7{,}03$, $s^2 = 0{,}04233$ ($s = 0{,}2058$).

Población normal ⇒ $\frac{(n-1)S^2}{\sigma^2} \sim \chi^2_9$. Con 1 − α = 0,98, α/2 = 0,01:
- $\chi^2_{9;\,0{,}01} = 2{,}088$
- $\chi^2_{9;\,0{,}99} = 21{,}666$

$IC_{\sigma^2} = \left[\frac{9\cdot0{,}04233}{21{,}666};\ \frac{9\cdot0{,}04233}{2{,}088}\right] = [0{,}0176;\ 0{,}1825]$ (litros/100 km)².

b) σ conocido ⇒ $d = z_{0{,}995}\frac{\sigma}{\sqrt n} \le 0{,}05$, con $z_{0{,}995} = 2{,}576$:

$n \ge \left(\frac{2{,}576\cdot0{,}17}{0{,}05}\right)^2 = 76{,}7$ ⇒ **n = 77**.

</details>

**Respuesta:**

- a) $IC_{98}(\sigma^2) = [0{,}0176;\ 0{,}1825]$
- b) n ≥ 77

</details>

---

### III) Comparación de estimadores

Sea X ~ N(μ; σ) y sea {X₁; X₂; X₃; X₄} una muestra aleatoria de X. Probar que $\hat\mu_a = \dfrac{X_1 + X_2}2$ es mejor estimador de la media que $\hat\mu_b = \dfrac{2X_1 + 3X_4}5$. Justificar.

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

Las $X_i$ son independientes, con $E(X_i) = \mu$ y $V(X_i) = \sigma^2$.

**Sesgo:**
- $E(\hat\mu_a) = \frac{\mu + \mu}2 = \mu$ ⇒ insesgado.
- $E(\hat\mu_b) = \frac{2\mu + 3\mu}5 = \mu$ ⇒ insesgado.

**Varianza** (por independencia, $V(aX + bY) = a^2V(X) + b^2V(Y)$):
- $V(\hat\mu_a) = \frac14(\sigma^2 + \sigma^2) = \frac{\sigma^2}2 = 0{,}5\,\sigma^2$
- $V(\hat\mu_b) = \frac{4\sigma^2 + 9\sigma^2}{25} = \frac{13}{25}\sigma^2 = 0{,}52\,\sigma^2$

Los dos son insesgados, así que su ECM es su varianza. Como $V(\hat\mu_a) < V(\hat\mu_b)$, $\hat\mu_a$ es **más eficiente** (menor ECM).

</details>

**Respuesta:** Ambos son insesgados, pero $V(\hat\mu_a) = 0{,}5\sigma^2 < V(\hat\mu_b) = 0{,}52\sigma^2$ ⇒ $\hat\mu_a$ es mejor (más eficiente, menor ECM).

</details>

---

### IV) Óxidos de azufre

Se tomó una muestra aleatoria de 10 observaciones de óxidos de azufre (SO₂), en ppm, provenientes de una fundición, la que arrojó una media de 57,41 ppm con un desvío de 0,94 ppm.

- a) Con los datos proporcionados y un α = 0,01, ¿podría avalarse la hipótesis de que el valor medio de óxido de azufre (en ppm) está por debajo de 58? Establecer los supuestos necesarios.
- b) ¿Con qué niveles de significación podría rechazar la hipótesis que dice que μ = 58?

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

**Supuestos:** la concentración de SO₂ tiene distribución **normal** y las observaciones son independientes (m.a.). Como σ es desconocido y n = 10 < 30, se usa t de Student.

a) Test:
1. H₀: μ ≥ 58 vs. H₁: μ < 58.
2. α = 0,01.
3. $T = \frac{\bar X - 58}{S/\sqrt n} \sim t_9$.
4. $t_{obs} = \frac{57{,}41 - 58}{0{,}94/\sqrt{10}} = -1{,}985$.
5. RC = {T < $t_{9;\,0{,}01}$ = −2,821}. Como −1,985 ∉ RC ⇒ no se rechaza H₀.

b) Valor p = $P(t_9 < -1{,}985) = 0{,}039$. Se rechaza H₀: μ = 58 (frente a μ < 58) con cualquier α ≥ 0,039 (por ejemplo, α = 0,05 o 0,10).

Si la alternativa fuera bilateral (μ ≠ 58), p = 0,078 y se rechazaría con α ≥ 0,078.

</details>

**Respuesta:**

- a) $t_{obs}$ = −1,985 > −2,821 ⇒ no se rechaza H₀: al 1 % no se puede avalar que μ < 58 (suponiendo normalidad y m.a.)
- b) Con α ≥ 0,039 (valor p unilateral)

</details>

---

### V) Meditación trascendental

En el boletín de la Asociación Americana del Corazón, *Hypertension*, investigadores reportan que los individuos que practican la meditación trascendental (MT) bajan su presión sanguínea de manera significativa. Una muestra aleatoria de 36 personas practicantes de MT meditan, en promedio, 8,8 horas a la semana. Suponer que el desvío poblacional es de 2,4 horas.

- a) ¿Esto sugiere que, en promedio, las personas que hacen MT utilizan más de 8 horas por semana? Usar un nivel de significación del 5 %.
- b) Calcular la probabilidad de aceptar que las personas que practican MT lo hacen en promedio más de 8 h semanales cuando el tiempo medio verdadero es de 10 h.

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

σ = 2,4 conocido y n = 36 ⇒ $\sigma_{\bar X} = 2{,}4/6 = 0{,}4$.

a) Test:
1. H₀: μ ≤ 8 vs. H₁: μ > 8.
2. α = 0,05.
3. $Z = \frac{\bar X - 8}{0{,}4} \sim N(0; 1)$.
4. $z_{obs} = \frac{8{,}8 - 8}{0{,}4} = 2$.
5. RC = {Z > 1,645}, o sea $\bar X > 8 + 1{,}645\cdot0{,}4 = 8{,}658$. Como 2 > 1,645 ⇒ se rechaza H₀ (p = 0,0228).

b) "Aceptar que meditan más de 8 h" es rechazar H₀. Cuando μ = 10 eso es la **potencia**:

$1 - \beta = P(\bar X > 8{,}658 \mid \mu = 10) = P\left(Z > \frac{8{,}658 - 10}{0{,}4}\right) = P(Z > -3{,}36) = 0{,}9996$.

</details>

**Respuesta:**

- a) $z_{obs}$ = 2 > 1,645 ⇒ se rechaza H₀: hay evidencia al 5 % de que meditan más de 8 h semanales
- b) 1 − β ≈ 0,9996

</details>

---

[← Volver al menú principal](../../README.md)
