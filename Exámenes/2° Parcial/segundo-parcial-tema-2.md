# 2.º Parcial — Tema 2 (08/07/2026)

Probabilidad y Estadística — UTN FRBA. Enunciado original: [MODELO 2°PARCIAL.pdf](Fotos/MODELO%202%C2%B0PARCIAL.pdf) (página 2).

> **Aprobación:** al menos 2 de los primeros 4 puntos correctamente resueltos.
> **Promoción:** aprobación + al menos 2 de los últimos 4 puntos bien resueltos. Los puntos IV y V sólo se corrigen si se alcanza la aprobación.

Cada ejercicio tiene un botón **Solución**. Al abrirlo aparece la respuesta y, arriba de ella, el botón **Solución paso a paso**.

---

### I) Azúcar convertida según la temperatura

Se realizó un estudio sobre la cantidad de azúcar convertida en cierto proceso a distintas temperaturas. Los datos se codificaron y se obtuvo lo siguiente:

| Temp (x) | 1,1 | 1,2 | 1,3 | 1,4 | 1,5 | 1,6 | 1,7 | 1,8 | 1,9 |
|---|---|---|---|---|---|---|---|---|---|
| **Azúcar (y)** | 7,8 | 8,5 | 9,8 | 9,5 | 8,9 | 8,6 | 10,2 | 9,3 | 9,2 |

Analizar con un nivel de significación del 10 % la pertinencia del modelo de regresión lineal simple para explicar la cantidad de azúcar a partir de la temperatura. Si el modelo ajusta correctamente, determinar la cantidad media de azúcar si la temperatura es 1,35. Justificar.

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

**Sumas** (n = 9): $\sum x = 13{,}5$, $\sum y = 81{,}8$, $\sum x^2 = 20{,}85$, $\sum y^2 = 747{,}72$, $\sum xy = 123{,}49$.

**Cantidades básicas:** $\bar x = 1{,}5$, $\bar y = 9{,}0889$, $S_{xx} = 0{,}6$, $S_{yy} = 4{,}2489$, $S_{xy} = 0{,}79$.

**Recta estimada:** $b_1 = 1{,}3167$ y $b_0 = 7{,}1139$ ⇒ $\hat y = 7{,}114 + 1{,}317x$.

**Test de correlación** (supuestos: errores normales, independientes y homocedásticos):
1. H₀: ρ = 0 vs. H₁: ρ ≠ 0.
2. α = 0,10.
3. $T = \frac{r\sqrt{n-2}}{\sqrt{1 - r^2}} \sim t_7$.
4. $r = \frac{0{,}79}{\sqrt{0{,}6\cdot4{,}2489}} = 0{,}4948$ ($R^2 = 0{,}245$) ⇒ $t_{obs} = 1{,}506$.
5. RC = {|T| > $t_{7;\,0{,}95}$ = 1,895}. Como 1,506 ∉ RC ⇒ no se rechaza H₀ (p = 0,176 > 0,10).

**Conclusión:** aun con α = 10 %, el modelo lineal **no es pertinente**. No corresponde estimar con la recta en x = 1,35 (daría $\hat y = 8{,}89$); la media de azúcar se estima con $\bar y = 9{,}09$.

</details>

**Respuesta:** $t_{obs}$ = 1,506 < 1,895 ⇒ no se rechaza ρ = 0 al 10 %. El modelo lineal no es pertinente, así que no se estima con la recta en x = 1,35 (la media de azúcar se estima con $\bar y$ ≈ 9,09).

</details>

---

### II) Consumo de combustible

Se toma una muestra de consumo de combustible en un cierto modelo de coche, obteniéndose los siguientes datos (expresados en litros cada 100 km):

6,7 − 7,2 − 7,3 − 7,0 − 7,1 − 6,9 − 7,3 − 7,1 − 6,9 − 6,8

- a) Suponiendo que el consumo sigue una distribución normal, estimar mediante un intervalo de confianza al 90 % el **desvío** del consumo.
- b) Suponiendo que el desvío poblacional del consumo de combustible en el modelo de coche considerado es de 0,15 litros/100 km, ¿de qué tamaño debería ser la muestra para que el error máximo de estimación (d) en un intervalo de confianza para la media al 95 % sea de a lo sumo 0,08 litros/100 km?

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

a) n = 10, $\bar x = 7{,}03$, $s^2 = 0{,}04233$ ($s = 0{,}2058$).

Con 1 − α = 0,90, α/2 = 0,05 y 9 g.l.:
- $\chi^2_{9;\,0{,}05} = 3{,}325$
- $\chi^2_{9;\,0{,}95} = 16{,}919$

$IC_\sigma = \left[\sqrt{\frac{9\cdot0{,}04233}{16{,}919}};\ \sqrt{\frac{9\cdot0{,}04233}{3{,}325}}\right] = [\sqrt{0{,}02252};\ \sqrt{0{,}11458}] = [0{,}150;\ 0{,}339]$ litros/100 km.

b) $1{,}96\cdot\frac{0{,}15}{\sqrt n} \le 0{,}08 \Rightarrow n \ge \left(\frac{1{,}96\cdot0{,}15}{0{,}08}\right)^2 = 13{,}5$ ⇒ **n = 14**.

</details>

**Respuesta:**

- a) $IC_{90}(\sigma) = [0{,}150;\ 0{,}339]$ litros/100 km
- b) n ≥ 14

</details>

---

### III) Comparación de estimadores

Sea X ~ N(μ; σ) y sea {X₁; X₂; X₃; X₄} una muestra aleatoria de X. Probar que $\hat\mu_a = \dfrac{X_1 + X_3}2$ es mejor estimador de la media que $\hat\mu_b = \dfrac{3X_1 + 5X_4}8$. Justificar.

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

Las $X_i$ son independientes, con $E(X_i) = \mu$ y $V(X_i) = \sigma^2$.

**Sesgo:**
- $E(\hat\mu_a) = \frac{\mu + \mu}2 = \mu$ ⇒ insesgado.
- $E(\hat\mu_b) = \frac{3\mu + 5\mu}8 = \mu$ ⇒ insesgado.

**Varianza:**
- $V(\hat\mu_a) = \frac14\cdot2\sigma^2 = \frac{\sigma^2}2 = 0{,}5\,\sigma^2$
- $V(\hat\mu_b) = \frac{9\sigma^2 + 25\sigma^2}{64} = \frac{34}{64}\sigma^2 = 0{,}531\,\sigma^2$

Los dos son insesgados (ECM = V), y $V(\hat\mu_a) < V(\hat\mu_b)$ ⇒ $\hat\mu_a$ es más eficiente.

</details>

**Respuesta:** Ambos son insesgados, pero $V(\hat\mu_a) = 0{,}5\sigma^2 < V(\hat\mu_b) = \frac{17}{32}\sigma^2 \approx 0{,}531\sigma^2$ ⇒ $\hat\mu_a$ es mejor (más eficiente, menor ECM).

</details>

---

### IV) Óxidos de azufre

Se tomó una muestra aleatoria de 10 observaciones de óxidos de azufre (SO₂), en ppm, provenientes de una fundición, la que arrojó una media de 56,84 ppm con un desvío de 0,94 ppm.

- a) Con los datos proporcionados y un α = 0,05, ¿podría avalarse la hipótesis de que el valor medio de óxido de azufre (en ppm) está por debajo de 58? Establecer los supuestos necesarios.
- b) ¿Con qué niveles de significación podría rechazar la hipótesis que dice que μ = 58?

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

**Supuestos:** población normal y m.a. (observaciones independientes); σ desconocido y n = 10 ⇒ t de Student con 9 g.l.

a) Test:
1. H₀: μ ≥ 58 vs. H₁: μ < 58.
2. α = 0,05.
3. $T = \frac{\bar X - 58}{S/\sqrt n} \sim t_9$.
4. $t_{obs} = \frac{56{,}84 - 58}{0{,}94/\sqrt{10}} = -3{,}902$.
5. RC = {T < $t_{9;\,0{,}05}$ = −1,833}. Como −3,902 ∈ RC ⇒ se rechaza H₀.

b) Valor p = $P(t_9 < -3{,}902) = 0{,}0018$. Se rechaza H₀ con cualquier α ≥ 0,0018 (incluso con α = 0,01).

Si la alternativa fuera bilateral, p = 0,0036.

</details>

**Respuesta:**

- a) $t_{obs}$ = −3,90 < −1,833 ⇒ se rechaza H₀: hay evidencia al 5 % de que μ < 58 (suponiendo normalidad y m.a.)
- b) Con α ≥ 0,0018 (valor p unilateral)

</details>

---

### V) Meditación trascendental

En el boletín de la Asociación Americana del Corazón, *Hypertension*, investigadores reportan que los individuos que practican la meditación trascendental (MT) bajan su presión sanguínea de manera significativa. Una muestra aleatoria de 36 personas practicantes de MT meditan, en promedio, 9,2 horas a la semana. Suponer que el desvío poblacional es de 2,4 horas.

- a) ¿Esto sugiere que, en promedio, las personas que hacen MT utilizan más de 8 horas por semana? Usar un nivel de significación del 1 %.
- b) Calcular la probabilidad de aceptar que las personas que practican MT lo hacen en promedio más de 8 h semanales cuando el tiempo medio verdadero es de 9 h.

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

$\sigma_{\bar X} = 2{,}4/\sqrt{36} = 0{,}4$.

a) Test:
1. H₀: μ ≤ 8 vs. H₁: μ > 8.
2. α = 0,01.
3. $Z = \frac{\bar X - 8}{0{,}4} \sim N(0; 1)$.
4. $z_{obs} = \frac{9{,}2 - 8}{0{,}4} = 3$.
5. RC = {Z > 2,326}, o sea $\bar X > 8 + 2{,}326\cdot0{,}4 = 8{,}93$. Como 3 > 2,326 ⇒ se rechaza H₀ (p = 0,00135).

b) Potencia en μ = 9:

$1 - \beta = P(\bar X > 8{,}93 \mid \mu = 9) = P\left(Z > \frac{8{,}93 - 9}{0{,}4}\right) = P(Z > -0{,}17) = 0{,}569$.

</details>

**Respuesta:**

- a) $z_{obs}$ = 3 > 2,326 ⇒ se rechaza H₀: hay evidencia al 1 % de que meditan más de 8 h semanales
- b) 1 − β ≈ 0,569

</details>

---

[← Volver al menú principal](../../README.md)
