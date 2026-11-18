# Parcial Parte B — Tema 1

Probabilidad y Estadística — UTN FRBA. Enunciado original: [foto del examen](Fotos/WhatsApp%20Image%202026-11-18%20at%2010.39.53.jpeg).

> Examen con 4 ejercicios prácticos y 2 teóricos (casillas de Promoción y Final).

Cada ejercicio tiene un botón **Solución**. Al abrirlo aparece la respuesta y, arriba de ella, el botón **Solución paso a paso**.

---

### Ejercicio 1) Piezas defectuosas

Un fabricante produce piezas de metal que se emplean en construcciones. El cliente requiere que la fracción de piezas defectuosas en uno de los pasos de manufactura críticos sea menor que 0,04, y que el fabricante demuestre esta característica del proceso de fabricación con este nivel de calidad, utilizando un nivel de significación de 0,01. El fabricante toma una muestra aleatoria de 1000 dispositivos y encuentra que 9 de ellos son defectuosos.

- a) ¿Puede el fabricante demostrar al cliente la calidad del proceso con el nivel de significación indicado?
- b) Suponga que la fracción de defectuosos del proceso es p = 0,02. ¿Cuál es en este caso la probabilidad de cometer error de tipo II?

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

p = fracción de defectuosos. Lo que hay que demostrar va en H₁.

a) Test:
1. H₀: p ≥ 0,04 vs. H₁: p < 0,04.
2. α = 0,01.
3. n = 1000 grande ⇒ $Z = \frac{\hat p - 0{,}04}{\sqrt{0{,}04\cdot0{,}96/1000}} \approx N(0; 1)$, con $\sigma_0 = 0{,}0062$.
4. $\hat p = 9/1000 = 0{,}009$ ⇒ $z_{obs} = \frac{0{,}009 - 0{,}04}{0{,}0062} = -5{,}0$.
5. RC = {Z < −2,326}, o sea $\hat p < 0{,}04 - 2{,}326\cdot0{,}0062 = 0{,}0256$. Como −5 ∈ RC ⇒ se rechaza H₀ (p valor ≈ 3·10⁻⁷).

b) β = P(no rechazar H₀ | p = 0,02) = P($\hat p$ ≥ 0,0256 | p = 0,02).

Con p = 0,02: $\sigma_1 = \sqrt{0{,}02\cdot0{,}98/1000} = 0{,}00443$.

$\beta = P\left(Z \ge \frac{0{,}0256 - 0{,}02}{0{,}00443}\right) = P(Z \ge 1{,}26) = 0{,}1035$.

</details>

**Respuesta:**

- a) Sí: $z_{obs}$ = −5 < −2,326 ⇒ se rechaza H₀: p ≥ 0,04; el fabricante demuestra que p < 0,04 al 1 %
- b) β ≈ 0,1035

</details>

---

### Ejercicio 2) Demanda pico de energía

Una compañía productora de energía eléctrica está interesada en desarrollar un modelo que relacione la demanda pico por hora (Y, en kW) con el uso de la energía total al mes (X, en kWh). Las variables se distribuyen en forma normal bivariada. La siguiente tabla muestra los datos obtenidos de una muestra de 5 clientes:

| X (kWh) | 997 | 2190 | 1087 | 2087 | 2081 |
|---|---|---|---|---|---|
| **Y (kW)** | 1,65 | 4,05 | 1,84 | 3,88 | 4,87 |

- a) Pruebe la significatividad de la regresión a un nivel de significación del 1 %.
- b) Encuentre un intervalo de confianza para un x₀ = 1050 kWh con un nivel del 99 %. Interprételo.

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

**Sumas** (n = 5): $\sum x = 8442$, $\sum y = 16{,}29$, $\sum x^2 = 15.657.808$, $\sum y^2 = 61{,}2819$, $\sum xy = 30.746{,}66$.

**Cantidades básicas:** $\bar x = 1688{,}4$ y $\bar y = 3{,}258$.
- $S_{xx} = 1.404.335{,}2$
- $S_{yy} = 8{,}2091$
- $S_{xy} = 3242{,}62$

**Recta estimada:** $b_1 = \frac{3242{,}62}{1404335{,}2} = 0{,}002309$ y $b_0 = 3{,}258 - 0{,}002309\cdot1688{,}4 = -0{,}6405$ ⇒ $\hat y = -0{,}6405 + 0{,}00231x$.

a) Test de significación:
1. H₀: β₁ = 0 (equivalente a ρ = 0) vs. H₁: β₁ ≠ 0.
2. α = 0,01.
3. $T = \frac{r\sqrt{n-2}}{\sqrt{1 - r^2}} \sim t_3$.
4. $r = 0{,}955$ ($R^2 = 0{,}912$) ⇒ $t_{obs} = \frac{0{,}955\sqrt3}{\sqrt{1 - 0{,}912}} = 5{,}58$.
5. RC = {|T| > $t_{3;\,0{,}995}$ = 5,841}. Como 5,58 < 5,841 ⇒ **no se rechaza** H₀ (p = 0,011).

Con sólo 5 datos (3 g.l.), aunque R² es alto, no alcanza para la significación al 1 %. Sí sería significativa al 5 % ($t_{3;\,0{,}975}$ = 3,18).

b) $\hat y(1050) = -0{,}6405 + 0{,}002309\cdot1050 = 1{,}784$ kW.

$SC_{res} = 0{,}7218$ ⇒ $s = \sqrt{0{,}7218/3} = 0{,}4905$.

$IC = \hat y_0 \pm t_{3;\,0{,}995}\,s\sqrt{\frac1n + \frac{(x_0 - \bar x)^2}{S_{xx}}} = 1{,}784 \pm 5{,}841\cdot0{,}4905\sqrt{0{,}2 + \frac{(1050 - 1688{,}4)^2}{1404335{,}2}} = 1{,}784 \pm 2{,}006$.

Resultado: [−0,22; 3,79] kW.

**Interpretación:** con 99 % de confianza, la demanda pico **media** de los clientes que consumen 1050 kWh al mes está entre −0,22 y 3,79 kW (en la práctica, entre 0 y 3,79). Es muy ancho por el n chico; además, al no ser significativa la regresión al 1 %, la estimación es poco confiable.

</details>

**Respuesta:**

- a) $t_{obs}$ = 5,58 < 5,841 ⇒ no se rechaza H₀: la regresión no es significativa al 1 % (p ≈ 0,011)
- b) $\hat y(1050)$ = 1,78 kW; $IC_{99}$ = [−0,22; 3,79] kW para la demanda pico media con x = 1050

</details>

---

### Ejercicio 3) Alanina en adultos mayores de 40

Sea X una muestra aleatoria de tamaño 12 de una distribución normal. Se determinó a partir de la misma la cantidad del aminoácido alanina (mg/100 ml) para 12 adultos mayores de 40 años normales, sometidos a una dieta libre de isoleucina, resultando la siguiente información:

2,84 3,54 2,8 2,44 2,94 2,7 2,93 2,54 2,79 2,14 2,74 2,67

- a) Encuentre un intervalo de confianza del 98 % para el verdadero valor de la varianza de la cantidad de alanina para adultos mayores de 40 años con esa dieta. Interprete el intervalo hallado.
- b) ¿Cuál es la probabilidad de que la varianza muestral supere el valor hallado en a) en una muestra de tamaño 12 si σ = 0,89?

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

a) n = 12, $\bar x = 2{,}756$, $s^2 = 0{,}11143$ (s = 0,334).

Población normal ⇒ $\frac{11S^2}{\sigma^2} \sim \chi^2_{11}$. Con α/2 = 0,01:
- $\chi^2_{11;\,0{,}01} = 3{,}053$
- $\chi^2_{11;\,0{,}99} = 24{,}725$

$IC_{\sigma^2} = \left[\frac{11\cdot0{,}11143}{24{,}725};\ \frac{11\cdot0{,}11143}{3{,}053}\right] = [0{,}0496;\ 0{,}4014]$ (mg/100 ml)².

**Interpretación:** si se repitiera el muestreo muchas veces, el 98 % de los intervalos construidos así contendría a la verdadera varianza σ². Con esta muestra, se estima que σ² está entre 0,0496 y 0,4014.

b) Se toma como "valor hallado" el extremo superior, 0,4014. Con σ² = 0,89² = 0,7921:

$P(S^2 > 0{,}4014) = P\left(\chi^2_{11} > \frac{11\cdot0{,}4014}{0{,}7921}\right) = P(\chi^2_{11} > 5{,}574) = 0{,}900$.

Si se tomara $s^2 = 0{,}1114$: $P(\chi^2_{11} > 1{,}547) = 0{,}9996$.

Que la probabilidad sea tan alta indica que σ = 0,89 es poco compatible con la muestra (σ² = 0,79 queda fuera del IC).

</details>

**Respuesta:**

- a) $IC_{98}(\sigma^2) = [0{,}0496;\ 0{,}4014]$ (mg/100 ml)²
- b) $P(S^2 > 0{,}4014) = P(\chi^2_{11} > 5{,}574) \approx 0{,}90$

</details>

---

### Teórico 1) Sesgo de un estimador de la varianza

Defina sesgo y encuentre el sesgo del estimador propuesto para la varianza poblacional de una población normal, a partir de una muestra de tamaño 4, si:

$$\hat\theta = \frac{\sum_{i=1}^4 (X_i - \bar X)^2}3 + \frac{\sum_{i=1}^4 X_i^2}4$$

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

**Definición:** el sesgo de un estimador $\hat\theta$ de un parámetro θ es $B(\hat\theta) = E(\hat\theta) - \theta$. El estimador es insesgado si B = 0. Además, $ECM = V(\hat\theta) + B^2$.

Aquí θ = σ² y n = 4:
- El primer término es $S^2$ (divide por n − 1 = 3) ⇒ $E(S^2) = \sigma^2$.
- El segundo es $\frac14\sum X_i^2$ ⇒ $E = \frac14\cdot4\,E(X^2) = V(X) + E(X)^2 = \sigma^2 + \mu^2$.

$E(\hat\theta) = \sigma^2 + \sigma^2 + \mu^2 = 2\sigma^2 + \mu^2$.

$B(\hat\theta) = 2\sigma^2 + \mu^2 - \sigma^2 = \sigma^2 + \mu^2$.

</details>

**Respuesta:** $B(\hat\theta) = E(\hat\theta) - \sigma^2 = \sigma^2 + \mu^2$ (> 0): el estimador es sesgado y sobreestima σ².

</details>

---

### Teórico 2) Región crítica y tamaño de muestra

En un test de hipótesis:

- a) ¿Qué representa la región crítica?
- b) Deduzca la selección del tamaño de la muestra en un test para la media de población normal con desvío conocido, conocidas las probabilidades de cometer ambos errores.

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

a) La **región crítica** (de rechazo) es el conjunto de valores del estadístico de prueba que llevan a rechazar H₀. Se construye en la dirección de H₁ y de modo que, si H₀ es verdadera, la probabilidad de caer en ella sea α: P(E.P. ∈ RC | H₀) = α. Su borde es el valor crítico.

b) Test unilateral izquierdo: H₀: μ = μ₀ vs. H₁: μ < μ₀, con X ~ N(μ; σ) y σ conocido. RC = {$\bar X < x_c$}, con $\bar X \sim N(\mu;\ \sigma/\sqrt n)$. Se fijan α y β (este último en un valor alternativo μ₁ < μ₀).

**Ecuación I** (α):

$\alpha = P(\bar X < x_c \mid \mu_0) \Rightarrow \frac{x_c - \mu_0}{\sigma/\sqrt n} = z_\alpha \Rightarrow x_c = \mu_0 + z_\alpha\frac\sigma{\sqrt n}$.

**Ecuación II** (β):

$\beta = P(\bar X > x_c \mid \mu_1) \Rightarrow \frac{x_c - \mu_1}{\sigma/\sqrt n} = z_{1-\beta} \Rightarrow x_c = \mu_1 + z_{1-\beta}\frac\sigma{\sqrt n}$.

**Igualando:**

$\mu_0 + z_\alpha\frac\sigma{\sqrt n} = \mu_1 + z_{1-\beta}\frac\sigma{\sqrt n} \Rightarrow \sqrt n = \frac{\sigma(z_\alpha - z_{1-\beta})}{\mu_1 - \mu_0}$.

$$n = \left(\frac{\sigma(z_{1-\alpha} + z_{1-\beta})}{\mu_0 - \mu_1}\right)^2$$

Se redondea hacia arriba. En el bilateral se usa $z_{1-\alpha/2}$.

</details>

**Respuesta:**

- a) El conjunto de valores del estadístico para los que se rechaza H₀, con P(RC | H₀) = α
- b) $n = \left(\dfrac{\sigma(z_{1-\alpha} + z_{1-\beta})}{\mu_0 - \mu_1}\right)^2$, redondeado hacia arriba

</details>

---

[← Volver al menú principal](../../README.md)
