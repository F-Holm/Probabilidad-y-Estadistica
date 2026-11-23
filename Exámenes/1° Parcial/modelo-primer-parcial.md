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

**Cómo reconocerlo:** hay dos "fuentes" (las fábricas), cada una con su propia distribución de pesos. La pregunta a) junta las dos (**probabilidad total**) y la b) va al revés: sabiendo el resultado, ¿de qué fuente vino? (**Bayes**).

**Sucesos:** A = "la lata es de la fábrica A", B = "es de la fábrica B", M = "pesa más de 248 g".

**Datos y dos trampas:**
- P(A) = 0,4 y el peso de A es $N(250;\ 4)$. ⚠️ Dan la **varianza** (16): el desvío es σ = √16 = 4, y la app pide σ.
- P(B) = 0,6 y el peso de B es $N(247;\ 6)$. ⚠️ Dan la **mediana**. En la Normal, que es simétrica, mediana = media (❌), así que μ_B = 247.

💡 **Normal y estandarización** (📄 H1, $`\frac{X - \mu}{\sigma} = Z`$). La probabilidad de pesar más de 248 **dentro de cada fábrica** (son condicionales):
```
P(M/A):  X~N(μ;σ)   μ=250   σ=4   P(X>x)   x=248   → 0.69146
P(M/B):  X~N(μ;σ)   μ=247   σ=6   P(X>x)   x=248   → 0.43382
```
Con tabla: $P(Z > -0{,}5) = 0{,}69146$ y $P(Z > 0{,}167) = 0{,}43382$.

**a)** 💡 **Probabilidad total:** una lata pesada puede venir de A o de B. Se suman los dos caminos, cada uno como P(fábrica) · P(M / fábrica). Es el denominador de Bayes en 📄 H1:

$$P(M) = 0{,}4\cdot0{,}69146 + 0{,}6\cdot0{,}43382 = 0{,}27659 + 0{,}26029 = 0{,}53687$$

**b)** 💡 **Bayes** (📄 H1, $`P(A_j/B) = \frac{P(A_j)P(B/A_j)}{\sum P(A_i)P(B/A_i)}`$): el camino de B dividido el total.

$$P(B/M) = \frac{0{,}26029}{0{,}53687} = 0{,}4848$$

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

💡 **Densidad** (variable continua): la probabilidad de un intervalo es el **área bajo f** en ese intervalo. Por eso el área total tiene que dar 1.

**Constante a.** Área total igual a 1:

$`\displaystyle \int_0^2 ax\,dx = a\frac{x^2}{2}\Big|_0^2 = 2a = 1 \;\Rightarrow\; a = \frac12`$

**a)** 💡 **Función de distribución** $F(x) = P(X \le x)$: el área acumulada hasta x (📄 H1, $`F(x) = \int_{-\infty}^x f(t)\,dt`$). Se arma por tramos:
- antes de 0 no hay área: F = 0;
- entre 0 y 2: $F(x) = \int_0^x \frac t2\,dt = \frac{x^2}{4}$;
- después de 2 ya se acumuló todo: F = 1.

$`\displaystyle F(x) = \begin{cases} 0 & x \le 0\\ \dfrac{x^2}4 & 0 < x \le 2\\ 1 & x > 2\end{cases}`$

Control: F(2) = 4/4 = 1 ✓, no hay saltos.

**b)** 💡 **Mediana** (❌): el valor que deja la mitad del área a cada lado, $F(x_{me}) = 0{,}5$.

$`\displaystyle \frac{x_{me}^2}{4} = 0{,}5 \;\Rightarrow\; x_{me} = \sqrt2 \approx 1{,}414`$

💡 **Varianza** (📄 H1): $V(X) = E(X^2) - E(X)^2$, con $E(g(X)) = \int g(x)f(x)\,dx$. Se multiplica cada valor (o su cuadrado) por la densidad y se integra.
- $E(X) = \int_0^2 x\cdot\frac x2\,dx = \frac{x^3}{6}\Big|_0^2 = \frac86 = \frac43$
- $E(X^2) = \int_0^2 x^2\cdot\frac x2\,dx = \frac{x^4}{8}\Big|_0^2 = 2$
- $V(X) = 2 - \left(\frac43\right)^2 = 2 - \frac{16}{9} = \frac29 \approx 0{,}2222$

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

💡 **Distribución exponencial.** Sirve para distancias o tiempos de espera hasta un evento. Tiene un parámetro λ. De 📄 H1, $F(x) = 1 - e^{-\lambda x}$, así que la probabilidad de superar x es $P(X > x) = e^{-\lambda x}$. Su media es 1/λ.

X = distancia entre fallas (en metros).

**1. Hallar λ con el dato.** "Más de 1800 m con probabilidad 0,082":

$$e^{-1800\lambda} = 0{,}082 \;\Rightarrow\; -1800\lambda = \ln0{,}082 \;\Rightarrow\; \lambda = \frac{-\ln0{,}082}{1800} = 0{,}0013895 \text{ m}^{-1}$$

La distancia media es 1/λ ≈ 720 m.

**2. "Entre 1000 y 1500"** es la acumulada hasta 1500 menos la acumulada hasta 1000 (📄 H1, $`P(a < X < b) = F(b) - F(a)`$):

```
X~Exp(λ)   λ=0.0013895   P(X<x)   x=1500   → 0.87557
X~Exp(λ)   λ=0.0013895   P(X<x)   x=1000   → 0.75077     → resta = 0.1248
```

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

💡 **Distribución binomial** (📄 H1, $`P(X = k) = \binom nk p^k(1-p)^{n-k}`$). Se usa cuando:
- se repite n veces un ensayo con dos resultados (éxito o no);
- los ensayos son independientes, con la misma probabilidad p;
- se cuenta cuántos éxitos hay.

La producción es grande, así que elegir unos pocos pernos no cambia las proporciones: son independientes. En cada inciso hay que definir **qué es éxito**.

**a)** Éxito = "utilizable" (p = 0,9), n = 3. Se piden los 3, P(X = 3):

```
X~Bin(n,p)   n=3   p=0.9   P(X=x)   x=3   → 0.729
```

**b)** Éxito = "hay que recortarlo" (p = 0,06), n = 5. "Al menos uno" es P(Y ≥ 1):

```
X~Bin(n,p)   n=5   p=0.06   P(X≥x)   x=1   → 0.2661
```

**c)** 💡 **Cantidad esperada** en una binomial: E = n·p (❌, la hoja trae solo la varianza np(1 − p)).
- "No desechar" tiene p = 1 − 0,04 = 0,96: $E = 30\cdot0{,}96 = 28{,}8$.
- "Usar inmediatamente" tiene p = 0,9: $E = 30\cdot0{,}9 = 27$.

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

💡 **Esperanza** E(X): el promedio que daría X si el experimento se repitiera muchísimas veces. En el caso discreto es $E(X) = \sum x_iP(x_i)$ (📄 H1): cada valor por su probabilidad.

**a)** Dos propiedades (❌, no están en la hoja):
1. **Esperanza de una constante:** E(c) = c. Si siempre vale c, el promedio es c.
2. **Linealidad:** E(aX + b) = aE(X) + b. Si a cada valor se le hace "por a, más b", al promedio le pasa lo mismo.

**Demostración de (2), caso discreto.** Se aplica la definición a la variable aX + b. Toma el valor $ax_i + b$ con la misma probabilidad $P(x_i)$:

$`\displaystyle E(aX + b) = \sum_i (ax_i + b)P(x_i) = a\underbrace{\sum_i x_iP(x_i)}_{E(X)} + b\underbrace{\sum_i P(x_i)}_{=1} = aE(X) + b`$

Se separó la suma en dos y se sacaron las constantes. Las probabilidades suman 1. En el caso continuo es igual, con integrales y $\int f(x)\,dx = 1$.

**b)** ⚠️ **No** se puede "meter" la esperanza dentro del cuadrado: $E[(2+4X)^2] \neq (2 + 4E(X))^2$. Primero se **desarrolla** y después se aplica la linealidad término a término:
- $E[(2 + 4X)^2] = E(4 + 16X + 16X^2) = 4 + 16E(X) + 16E(X^2) = 4 + 32 + 128 = 164$
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

💡 **Distribución conjunta.** Cuando hay **dos** variables en el mismo experimento, la conjunta da la probabilidad de cada **par**: $P(X = x \text{ y } Y = y)$. Se arma como una tabla con X en las filas e Y en las columnas.

**Planteo.** Hay 11 bolillas y se repone, así que las extracciones son **independientes** y siempre valen P(N) = 5/11, P(B) = 2/11 y P(R) = 4/11. La probabilidad de una secuencia de 3 es el producto (📄 H1, independencia), con denominador 11³ = 1331.

⚠️ **Cuidado con Y:** cuenta las rojas **antes de la primera blanca**. Si no sale ninguna blanca, cuenta todas las rojas.

**a) Método:** se recorren las 27 secuencias posibles (3 colores en 3 extracciones) y se agrupan por el par (x, y) que producen. Por ejemplo:
- **(X = 0, Y = 0):** ninguna negra y ninguna roja antes de la blanca, así que la 1.ª tiene que ser blanca, y las otras dos no son negras: BBB, BBR, BRB, BRR. Suman (8 + 16 + 16 + 32)/1331 = 72/1331.
- **(X = 1, Y = 2):** una negra y dos rojas, sin blanca: NRR, RNR, RRN. Cada una vale 5·4·4, así que 3·80/1331 = 240/1331.

Tabla completa (valores × 1/1331):

| X \ Y | 0 | 1 | 2 | 3 | P(X = x) |
|---|---|---|---|---|---|
| 0 | 72 | 48 | 32 | 64 | 216 |
| 1 | 180 | 120 | 240 | 0 | 540 |
| 2 | 150 | 300 | 0 | 0 | 450 |
| 3 | 125 | 0 | 0 | 0 | 125 |
| **P(Y = y)** | 527 | 468 | 272 | 64 | 1331 |

💡 **Marginales:** la distribución de una sola variable se obtiene sumando la conjunta por filas (para X) o por columnas (para Y) (📄 H1, $`P_X(x) = \sum_y P(x;y)`$). Son la última columna y la última fila de la tabla.

**Control:** X sola cuenta negras en 3 extracciones independientes, así que es Bin(3; 5/11). Por ejemplo, $P(X = 0) = (6/11)^3 = 216/1331$ ✓.

**b)** 💡 **Independencia de variables** (📄 H1): X e Y son independientes si y solo si $P(x, y) = P_X(x)\,P_Y(y)$ para **todos** los pares. Para mostrar que **no** lo son, alcanza con **un** par que falle:

$`\displaystyle P(X = 3, Y = 1) = 0 \qquad\text{pero}\qquad P_X(3)\,P_Y(1) = \frac{125}{1331}\cdot\frac{468}{1331} \neq 0`$

**Son dependientes.** Tiene sentido: si salen 3 negras, no puede haber rojas.

</details>

**Respuesta:**

- a) La tabla de arriba (en 1331-avos)
- b) Son **dependientes**, por ejemplo P(X = 3, Y = 1) = 0 ≠ P(X = 3)·P(Y = 1)

</details>

---

[← Volver al menú principal](../../README.md)
