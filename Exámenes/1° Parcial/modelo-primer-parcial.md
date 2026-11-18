# Modelo de 1.er Parcial (Guía de TP, cap. 7.1)

Probabilidad y Estadística — UTN FRBA. Modelo de examen que aparece al final de la [Guía de Trabajos Prácticos](../../GU%C3%8DA%20DE%20TPs.pdf).

> **Aprobación:** dos prácticos y un teórico correctos. Todas las respuestas deben estar debidamente justificadas.

Cada ejercicio tiene un botón **Solución**. Al abrirlo aparece la respuesta y, arriba de ella, el botón **Solución paso a paso**.

---

### Ejercicio 1) Tomates enlatados

Dos fábricas de tomates enlatados (A y B) abastecen con su producción el consumo de la CABA, en una proporción de 40 % y 60 % respectivamente. El peso en gramos tiene una distribución normal. Las latas de la fábrica A tienen una media de 250 gramos y una varianza de 16 g². De las de la fábrica B se sabe que la mediana es de 247 gramos y la varianza de 36 g².

- a) Se compra al azar una lata, ¿cuál es la probabilidad de que su peso sea mayor que 248 g?
- b) Si el peso de la lata elegida al azar es mayor que 248 gramos, ¿cuál es la probabilidad de que sea de la fábrica B?

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

**Sucesos:** A = "la lata es de la fábrica A", B = "la lata es de la fábrica B", M = "pesa más de 248 g".

**Datos:**
- P(A) = 0,4 y $X_A \sim N(250;\ 4)$ (σ = √16).
- P(B) = 0,6 y $X_B \sim N(247;\ 6)$: en la normal, mediana = media, así que μ_B = 247.

**Probabilidades condicionales:**
- $P(M/A) = P\left(Z > \frac{248 - 250}4\right) = P(Z > -0{,}5) = 0{,}69146$
- $P(M/B) = P\left(Z > \frac{248 - 247}6\right) = P(Z > 0{,}167) = 0{,}43382$

a) **Probabilidad total:**

$P(M) = 0{,}4\cdot0{,}69146 + 0{,}6\cdot0{,}43382 = 0{,}27659 + 0{,}26029 = 0{,}53687$.

b) **Bayes:**

$P(B/M) = \frac{P(M/B)P(B)}{P(M)} = \frac{0{,}26029}{0{,}53687} = 0{,}4848$.

</details>

**Respuesta:**

- a) P(M) ≈ 0,5369
- b) P(B/M) ≈ 0,4848

</details>

---

### Ejercicio 2) Impurezas en resinas

La proporción de impurezas que aparecen en un compuesto de resinas es una variable aleatoria con la siguiente función de densidad:

$$f_X(x) = \begin{cases} ax & 0 < x \le 2\\ 0 & \text{otro caso}\end{cases}$$

- a) Hallar la función de distribución de probabilidades.
- b) Hallar el valor mediano y la varianza de la distribución.

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

**Constante a:** el área total vale 1.

$\int_0^2 ax\,dx = a\frac{x^2}2\Big|_0^2 = 2a = 1 \Rightarrow a = \frac12$.

a) Para 0 < x ≤ 2: $F(x) = \int_0^x \frac t2\,dt = \frac{x^2}4$.

$$F(x) = \begin{cases} 0 & x \le 0\\ \dfrac{x^2}4 & 0 < x \le 2\\ 1 & x > 2\end{cases}$$

b) **Mediana:** $F(x_{me}) = \frac{x_{me}^2}4 = 0{,}5 \Rightarrow x_{me} = \sqrt2 \approx 1{,}414$.

**Varianza:**
- $E(X) = \int_0^2 x\cdot\frac x2\,dx = \frac{x^3}6\Big|_0^2 = \frac86 = \frac43$
- $E(X^2) = \int_0^2 x^2\cdot\frac x2\,dx = \frac{x^4}8\Big|_0^2 = 2$
- $V(X) = E(X^2) - E(X)^2 = 2 - \frac{16}9 = \frac29 \approx 0{,}2222$

</details>

**Respuesta:**

- a) a = 1/2; F(x) = 0 si x ≤ 0, x²/4 si 0 < x ≤ 2, y 1 si x > 2
- b) Mediana = √2 ≈ 1,414; V(X) = 2/9 ≈ 0,2222

</details>

---

### Ejercicio 3) Fallas de hilado

La distancia entre dos fallas de hilado se distribuye exponencialmente, de modo tal que la probabilidad de que haya más de 1800 metros entre dos fallas es 0,082. Calcular la probabilidad de que entre dos fallas consecutivas tomadas al azar haya entre 1000 y 1500 metros.

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

X = distancia entre fallas (m), X ~ Exp(λ), con $P(X > x) = e^{-\lambda x}$.

**1. Hallar λ:**

$e^{-1800\lambda} = 0{,}082 \Rightarrow \lambda = \frac{-\ln0{,}082}{1800} = 0{,}0013895$ m⁻¹ (distancia media 1/λ ≈ 720 m).

**2. Probabilidad pedida:**

$P(1000 < X < 1500) = e^{-1000\lambda} - e^{-1500\lambda} = e^{-1{,}3895} - e^{-2{,}0842} = 0{,}24923 - 0{,}12443 = 0{,}1248$.

</details>

**Respuesta:** λ ≈ 0,00139 m⁻¹ y P(1000 < X < 1500) ≈ 0,1248

</details>

---

### Ejercicio 4) Pernos

De los pernos manufacturados por cierta aplicación, el 90 % satisface la longitud especificada y se puede utilizar inmediatamente, el 6 % es demasiado largo y debe recortarse, y el restante 4 % es demasiado corto y debe desecharse.

- a) Hallar la probabilidad de que al seleccionar tres pernos al azar todos puedan utilizarse inmediatamente.
- b) Hallar la probabilidad de que al seleccionar cinco pernos al azar al menos uno deba recortarse.
- c) ¿Cuántos se espera, de una muestra de 30 pernos, que no deban desecharse? ¿Cuántos utilizarse inmediatamente?

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

Los pernos se toman independientes (población grande) ⇒ binomiales.

a) X = pernos utilizables entre 3, X ~ Bin(3; 0,9) ⇒ $P(X = 3) = 0{,}9^3 = 0{,}729$.

b) Y = pernos a recortar entre 5, Y ~ Bin(5; 0,06):

$P(Y \ge 1) = 1 - P(Y = 0) = 1 - 0{,}94^5 = 1 - 0{,}7339 = 0{,}2661$.

c) No se desechan: p = 1 − 0,04 = 0,96 ⇒ E = np = 30·0,96 = 28,8.

Se usan inmediatamente: p = 0,9 ⇒ E = 30·0,9 = 27.

</details>

**Respuesta:**

- a) 0,729
- b) 0,2661
- c) Se espera que 28,8 no deban desecharse y que 27 se usen inmediatamente

</details>

---

### Teórico 1) Propiedades de la esperanza

- a) Enuncie dos propiedades de la esperanza matemática y demuestre una de ellas.
- b) Sabiendo que E(X) = 2 y que E(X²) = 8, hallar E[(2 + 4X)²] y E[X² + 2(1 + X)].

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

a) Propiedades:
1. **Esperanza de una constante:** E(c) = c.
2. **Linealidad:** E(aX + b) = aE(X) + b.

**Demostración de (2), caso discreto:**

$E(aX + b) = \sum_i (ax_i + b)P(x_i) = a\sum_i x_iP(x_i) + b\sum_i P(x_i) = aE(X) + b\cdot1$.

En el caso continuo es igual, con integrales y $\int f(x)\,dx = 1$.

b) Se desarrolla y se aplica la linealidad:
- $E[(2 + 4X)^2] = E(4 + 16X + 16X^2) = 4 + 16\cdot2 + 16\cdot8 = 4 + 32 + 128 = 164$
- $E[X^2 + 2(1 + X)] = E(X^2) + 2 + 2E(X) = 8 + 2 + 4 = 14$

</details>

**Respuesta:**

- a) E(c) = c y E(aX + b) = aE(X) + b (demostrada arriba)
- b) E[(2 + 4X)²] = 164 y E[X² + 2(1 + X)] = 14

</details>

---

### Teórico 2) Urna con bolillas

Una urna contiene cinco bolillas negras, dos blancas y cuatro rojas. Se extrae aleatoriamente una muestra de 3 bolillas, de a una por vez y reponiendo cada bolilla en la urna antes de extraer la siguiente. Sea X el número de bolillas negras en la muestra, e Y el número de rojas antes de la primera blanca.

- a) Hallar la distribución conjunta de probabilidades de X e Y.
- b) Decidir si las variables X e Y son dependientes.

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

Total: 11 bolillas, con reposición ⇒ extracciones independientes con P(N) = 5/11, P(B) = 2/11 y P(R) = 4/11.

Cada secuencia de 3 tiene probabilidad (producto)/11³ = …/1331. Si no sale ninguna blanca, Y cuenta todas las rojas de la muestra.

a) Se recorren las 27 secuencias posibles y se agrupan por (x, y). Por ejemplo:
- (X = 0, Y = 0): la primera es blanca y las otras no son negras: BBB, BBR, BRB, BRR ⇒ (8 + 16 + 16 + 32)/1331 = 72/1331.
- (X = 1, Y = 2): una negra y dos rojas, sin blanca: NRR, RNR, RRN ⇒ 3·5·4·4/1331 = 240/1331.

Tabla completa (valores × 1/1331):

| X \ Y | 0 | 1 | 2 | 3 | P(X = x) |
|---|---|---|---|---|---|
| 0 | 72 | 48 | 32 | 64 | 216 |
| 1 | 180 | 120 | 240 | 0 | 540 |
| 2 | 150 | 300 | 0 | 0 | 450 |
| 3 | 125 | 0 | 0 | 0 | 125 |
| **P(Y = y)** | 527 | 468 | 272 | 64 | 1331 |

Control: las marginales de X coinciden con una Bin(3; 5/11): $(6/11)^3 = 216/1331$, etc.

b) Basta un par que no cumpla $P(x, y) = P(x)\,P(y)$. Por ejemplo, P(X = 3, Y = 1) = 0, pero $P(X = 3)\,P(Y = 1) = \frac{125}{1331}\cdot\frac{468}{1331} \ne 0$.

Tiene sentido: si salen 3 negras no puede haber rojas.

</details>

**Respuesta:**

- a) La tabla de arriba (en 1331-avos)
- b) Son **dependientes**, por ejemplo P(X = 3, Y = 1) = 0 ≠ P(X = 3)·P(Y = 1)

</details>

---

[← Volver al menú principal](../../README.md)
