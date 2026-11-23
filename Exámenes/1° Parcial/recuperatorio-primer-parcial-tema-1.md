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

**Cómo reconocerlo:** dos grupos (localizadas o no), cada uno con su probabilidad de tener localizador, y la pregunta va **al revés**: sabiendo que tiene localizador, ¿qué probabilidad hay de que no sea localizada? Es **Bayes**.

**Sucesos:** L = "es localizada", E = "tiene localizador de emergencia".

**Datos.** "De las localizadas, el 60 %…" es una **condicional**.
- P(L) = 0,7, así que $P(\bar L) = 0{,}3$.
- P(E/L) = 0,6.
- ⚠️ **Trampa:** "el 90 % de las no localizadas **no** tiene localizador" es $P(\bar E/\bar L) = 0{,}9$. La que se usa es su complemento, $P(E/\bar L) = 0{,}1$.

```
        ┌─ E   0,6  → 0,7·0,6 = 0,42
 L 0,7 ─┤
        └─ Ē   0,4
        ┌─ E   0,1  → 0,3·0,1 = 0,03
 L̄ 0,3 ─┤
        └─ Ē   0,9
```

💡 **Probabilidad total:** se suman los caminos que terminan en E:

$$P(E) = 0{,}42 + 0{,}03 = 0{,}45$$

💡 **Bayes** (📄 H1): el camino de $\bar L$ dividido el total con localizador.

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

Es una cadena: **uniforme** (una tabla) → **p** → **binomial** (4 tablas).

**1. Una tabla.** 💡 **Uniforme U(a; b):** cualquier valor del intervalo es igual de probable, así que la probabilidad de un tramo es **su largo sobre el largo total** (❌). La app no tiene uniforme, así que va a mano:

$$p = P(X > 20{,}1) = \frac{20{,}5 - 20{,}1}{20{,}5 - 19{,}5} = \frac{0{,}4}{1} = 0{,}4$$

(Alternativa con la app: `X~Beta(α;β) α=1 β=1 P(X>x) x=0.6 → 0.4`, donde 0,6 = (20,1 − 19,5)/1.)

**2. Cuatro tablas.** 💡 **Binomial** (📄 H1, $`\binom nk p^k(1-p)^{n-k}`$): cada tabla supera 20,1 (éxito) con p = 0,4, independientemente. W ~ Bin(4; 0,4).

"Alguna" significa al menos una, P(W ≥ 1):

```
X~Bin(n,p)   n=4   p=0.4   P(X≥x)   x=1   → 0.8704
```

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

💡 **Hipergeométrica** (📄 H1, $`P(X = k) = \frac{\binom Kk\binom{N-K}{n-k}}{\binom Nn}`$): se eligen n personas de un grupo **finito** de N **sin reposición**, y se cuenta cuántas tienen una característica que tienen K del grupo.

X = cantidad de mujeres en el grupo ~ **H(N = 50; K = 10; n = 12)**.

**Traducir "más mujeres que varones".** Con 12 personas, varones = 12 − X. La condición es X > 12 − X, es decir X > 6, o sea **X ≥ 7**. Solo hay 10 mujeres, así que X va de 7 a 10. A mano serían cuatro términos de la fórmula; con la app es P(X ≥ 7) directo:

```
X~HG(N,K,n)   N=50   K=10   n=12   P(X≥x)   x=7   → 0.000685
```
Es casi imposible: solo el 20 % del curso son mujeres.

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

Es una cadena: **exponencial** (una lámpara) → **p** → **binomial** (8 lámparas).

💡 **Exponencial:** modela tiempos de vida. De 📄 H1, $F(x) = 1 - e^{-\lambda x}$, así que $P(X > x) = e^{-\lambda x}$, y la vida media es $E(X) = \frac1\lambda$.

**1. Hallar λ.** "El 35 % no supera 4307,83 h" significa que el 65 % la supera:

$$e^{-4307{,}83\lambda} = 0{,}65 \;\Rightarrow\; \lambda = \frac{\ln0{,}65}{-4307{,}83} \approx 0{,}0001 \text{ h}^{-1} \;\Rightarrow\; E(X) = \frac1\lambda = 10\,000 \text{ h}$$

**2. Una lámpara.** "Supera la vida media en más de 500 h" significa X > 10 000 + 500 = 10 500:

```
X~Exp(λ)   λ=0.0001   P(X>x)   x=10500   → 0.34994
```

**3. Ocho lámparas.** 💡 **Binomial** (📄 H1): cada lámpara cumple (éxito) con p ≈ 0,35, independientemente. W ~ Bin(8; 0,35). "Sólo 3" significa **exactamente** 3, P(W = 3):

```
X~Bin(n,p)   n=8   p=0.34994   P(X=x)   x=3   → 0.27857
```

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

**Paso 1, los datos de cada variable** (esperanza y varianza):

| Variable | E | V | De dónde |
|---|---|---|---|
| X ~ Po(5) | 5 | 5 | ❌ En la Poisson, E = V = λ |
| Y ~ N(4; 2) | 4 | 4 | Son los parámetros; ⚠️ V = σ² = 2² |
| U ~ U(2; b) | ? | $\left(\frac{6}{\sqrt{12}}\right)^2 = 3$ | El desvío al cuadrado |

**Paso 2, hallar b.** 📄 H1: $V(U) = \frac{(b-a)^2}{12}$.

$$\frac{(b-2)^2}{12} = 3 \;\Rightarrow\; (b - 2)^2 = 36 \;\Rightarrow\; b = 8$$

La esperanza de la uniforme es el punto medio (❌): $E(U) = \frac{2 + 8}{2} = 5$.

**Paso 3, E(X²).** Aparece $X^2$, así que hace falta su esperanza. Se despeja de 📄 H1, $V(X) = E(X^2) - E(X)^2$:

$$E(X^2) = V(X) + E(X)^2 = 5 + 25 = 30$$

**Paso 4, la esperanza.** 💡 Propiedad, **linealidad** (❌): $E(aX + bY + cZ) = aE(X) + bE(Y) + cE(Z)$. Las constantes salen afuera y la esperanza de una suma es la suma de esperanzas.

$$E(X^2 - 3Y + 4U) = E(X^2) - 3E(Y) + 4E(U) = 30 - 12 + 20 = 38$$

**Paso 5, la varianza.** Propiedades:
- 📄 H1: $V(aX + bY) = a^2V(X) + b^2V(Y) + 2ab\,Cov(X;Y)$. Como son **independientes**, Cov = 0, y se extiende a tres variables.
- Los coeficientes salen **al cuadrado**, así que un signo menos no resta: las varianzas siempre suman.
- La varianza de una constante es 0 (no varía), así que el −5 no aporta.

$$V(4X - 2Y - U - 5) = 4^2V(X) + (-2)^2V(Y) + (-1)^2V(U) = 16\cdot5 + 4\cdot4 + 3 = 99$$

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

💡 **Qué es una densidad.** Para una variable continua, la probabilidad de un intervalo es el **área bajo f**. Para que f sea densidad tiene que cumplir dos cosas:
1. **área total = 1**;
2. **f ≥ 0** en todo el intervalo.

**1. Área total igual a 1:**

$`\displaystyle \int_1^3(4kx + 1)\,dx = (2kx^2 + x)\Big|_1^3 = (18k + 3) - (2k + 1) = 16k + 2 = 1 \;\Rightarrow\; k = -\frac1{16}`$

Entonces $f(x) = 1 - \frac x4$. **f ≥ 0:** es decreciente, así que su mínimo está en x = 3, donde vale ¼ > 0 ✓. Es una densidad (que k sea negativo no es problema).

**2. Función de distribución.** 💡 $F(x) = P(X \le x)$, el área acumulada hasta x (📄 H1, $`F(x) = \int_{-\infty}^x f(t)\,dt`$). En 1 < x < 3:

$`\displaystyle F(x) = \int_1^x\left(1 - \frac t4\right)dt = \left[t - \frac{t^2}{8}\right]_1^x = -\frac{x^2}{8} + x - \frac78`$

Vale 0 para x ≤ 1 y 1 para x ≥ 3. Control: F(3) = −9/8 + 3 − 7/8 = 1 ✓.

**3. Condicional.** 💡 📄 H1: $P(A/B) = \frac{P(A\cap B)}{P(B)}$. "X < 2 y X > 1,5" es 1,5 < X < 2. Con las reglas $P(a < X < b) = F(b) - F(a)$ y $P(X > a) = 1 - F(a)$ (📄 H1):

$$P(X < 2 / X > 1{,}5) = \frac{P(1{,}5 < X < 2)}{P(X > 1{,}5)} = \frac{F(2) - F(1{,}5)}{1 - F(1{,}5)}$$

F(2) = −½ + 2 − ⅞ = 5/8 y F(1,5) = −9/32 + 3/2 − 7/8 = 11/32:

$$\frac{\frac{20}{32} - \frac{11}{32}}{\frac{21}{32}} = \frac9{21} = \frac37 \approx 0{,}4286$$

</details>

**Respuesta:** k = −1/16 y $P(X < 2 / X > 1{,}5) = 3/7$

</details>

---

[← Volver al menú principal](../../README.md)
