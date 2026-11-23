# 1.er Parcial — Tema 1 (12/05/2026)

Probabilidad y Estadística — UTN FRBA.

> **Aprobación:** al menos 2 de los primeros 4 puntos correctamente resueltos.
> **Promoción:** aprobación + el punto V o el VI correctamente resuelto. Los puntos V y VI sólo se corrigen si se alcanza la aprobación.

Cada ejercicio tiene un botón **Solución**. Al abrirlo aparece la respuesta y, arriba de ella, el botón **Solución paso a paso**.

---

### I) Ingenieros que estiman costos

Una compañía emplea a 2 ingenieros para estimar costos. Uno de ellos estima el 70 % de las cotizaciones. Cada uno tiene una tasa de error del 2 % y del 4 %, respectivamente. Si se observa una cotización mal estimada, ¿cuál es la probabilidad de que la haya estimado el ingeniero que más trabaja?

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

**Cómo reconocerlo:** hay dos "fuentes" (los ingenieros), cada una con su probabilidad de error, y la pregunta va **al revés**: sabiendo que hay un error, ¿de quién es? Eso es **Bayes**.

**Sucesos:** A = "la estimó el ingeniero A" (el que más trabaja), B = "la estimó B", D = "está mal estimada".

**Datos.** "Tasa de error del 2 %" es una **condicional**: dado que la estimó A, se equivoca con 0,02.
- P(A) = 0,7 y P(B) = 0,3.
- P(D/A) = 0,02 y P(D/B) = 0,04.

```
        ┌─ D   0,02  → 0,7·0,02 = 0,014
 A 0,7 ─┤
        └─ D̄   0,98
        ┌─ D   0,04  → 0,3·0,04 = 0,012
 B 0,3 ─┤
        └─ D̄   0,96
```

💡 **Probabilidad total:** se suman los caminos del árbol que terminan en D:

$$P(D) = 0{,}7\cdot0{,}02 + 0{,}3\cdot0{,}04 = 0{,}014 + 0{,}012 = 0{,}026$$

💡 **Bayes** (📄 H1, $`P(A_j/B) = \frac{P(A_j)P(B/A_j)}{\sum_i P(A_i)P(B/A_i)}`$): el camino que interesa dividido todos los que llegan a D.

$$P(A/D) = \frac{P(D/A)P(A)}{P(D)} = \frac{0{,}014}{0{,}026} \approx 0{,}5385$$

</details>

**Respuesta:** $P(A/D) \approx 0{,}5385$

</details>

---

### II) Llegadas a la cola del supermercado

El tiempo que transcurre entre la llegada de dos personas consecutivas a la cola del supermercado se distribuye exponencialmente, con un tiempo medio de 5 minutos. Si hace 4 minutos que no llega nadie, ¿cuál es la probabilidad de que la siguiente persona llegue dentro de los próximos 2 minutos?

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

💡 **Distribución exponencial:** modela tiempos de espera. Tiene un parámetro λ y media $E(X) = \frac1\lambda$ (📄 H1). Media 5 minutos significa λ = 1/5 = 0,2 por minuto, con $F(x) = 1 - e^{-0{,}2x}$ (📄 H1).

**Traducción.** "Hace 4 minutos que no llega nadie" es la condición X > 4. "Llega en los próximos 2 minutos" es X < 6. Se pide $P(X < 6 / X > 4)$.

**Camino 1, con la definición de condicional** (📄 H1, $`P(A/B) = \frac{P(A\cap B)}{P(B)}`$). La intersección de X < 6 con X > 4 es 4 < X < 6:

$$P(X < 6 / X > 4) = \frac{P(4 < X < 6)}{P(X > 4)} = \frac{F(6) - F(4)}{1 - F(4)}$$

```
X~Exp(λ)   λ=0.2   P(X<x)   x=6   → 0.69881
X~Exp(λ)   λ=0.2   P(X<x)   x=4   → 0.55067
```

$$\frac{0{,}69881 - 0{,}55067}{1 - 0{,}55067} = \frac{0{,}14814}{0{,}44933} \approx 0{,}3297$$

**Camino 2, con la falta de memoria (el más corto)** (📄 H1, $`P(X > t_0 + \Delta t / X > t_0) = P(X > \Delta t)`$). La exponencial "no recuerda" cuánto se esperó: los 4 minutos ya esperados no cuentan. La probabilidad de que llegue en los próximos 2 es la misma que la de que llegue en 2 minutos desde cero:

```
X~Exp(λ)   λ=0.2   P(X<x)   x=2   → 0.32968
```

</details>

**Respuesta:** ≈ 0,3297

</details>

---

### III) Elongación de barras de acero

La elongación de una barra de acero se distribuye normalmente con media 1,2 mm. En el 2,28 % de las veces que se somete a una carga, la elongación es superior a 1,6 mm. Si se someten 4 barras a una carga, calcular la probabilidad de que al menos 2 tengan una elongación mayor a 1 mm.

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

Es un ejercicio "en cadena": **Normal** (una barra) → **p** → **binomial** (varias barras).

**1. Hallar σ.** X ~ N(1,2; σ), con σ desconocido. 💡 **Estandarizar** (📄 H1, $`Z = \frac{X - \mu}{\sigma}`$) lleva cualquier normal a la estándar. El dato dice que 1,6 deja 2,28 % a la derecha. Se busca el z que deja eso:
```
X~N(μ;σ)   μ=0   σ=1   P(X>x)=0.0228   → x=2.000
```
Ese z tiene que ser $\frac{1{,}6 - 1{,}2}{\sigma}$:

$$\frac{0{,}4}{\sigma} = 2 \;\Rightarrow\; \sigma = 0{,}2 \text{ mm}$$

**2. Una barra:** probabilidad de que la elongación supere 1 mm.
```
X~N(μ;σ)   μ=1.2   σ=0.2   P(X>x)   x=1   → 0.84134
```
p = 0,84134. Con tabla: $P(Z > -1) = \Phi(1)$.

**3. Cuatro barras.** 💡 **Binomial** (📄 H1, $`\binom nk p^k(1-p)^{n-k}`$): cada barra "supera 1 mm" (éxito) con la misma p, independientemente, y se cuenta cuántas lo hacen. W ~ Bin(4; 0,84134).

"Al menos 2" es P(W ≥ 2):

```
X~Bin(n,p)   n=4   p=0.84134   P(X≥x)   x=2   → 0.98593
```

</details>

**Respuesta:** σ = 0,2 mm y $P(W \ge 2) \approx 0{,}98593$

</details>

---

### IV) Técnicos en dos cursos

En un curso de ingeniería electrónica de 30 estudiantes hay 20 técnicos, y en un curso de ingeniería civil de 25 estudiantes hay 10 técnicos. Si se elige al azar un grupo de 5 estudiantes de cada curso, ¿cuál es la probabilidad de que en ambos grupos haya a lo sumo 2 técnicos?

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

💡 **Distribución hipergeométrica** (📄 H1, $`P(X = k) = \frac{\binom Kk\binom{N-K}{n-k}}{\binom Nn}`$). Se usa cuando se eligen n personas de un grupo **finito** de N, **sin reposición** (no se puede elegir dos veces a la misma), y se cuenta cuántas tienen una característica que tienen K del grupo. Se lee: elegir k de los K "éxitos" y el resto de los demás, sobre todas las formas de elegir n.

- X = técnicos en el grupo de electrónica ~ H(N = 30; K = 20; n = 5).
- Y = técnicos en el grupo de civil ~ H(N = 25; K = 10; n = 5).

"A lo sumo 2" es P(X ≤ 2) y P(Y ≤ 2). A mano serían tres términos de la fórmula para cada grupo; con la app es una línea:

```
X~HG(N,K,n)   N=30   K=20   n=5   P(X≤x)   x=2   → 0.19123
X~HG(N,K,n)   N=25   K=10   n=5   P(X≤x)   x=2   → 0.69881
```
(En la app: tamaño de la población, cantidad de éxitos en la población y tamaño de la muestra.)

**"En ambos grupos"** es una intersección. Los grupos se eligen por separado, así que son independientes y se multiplica (📄 H1, $`P(A\cap B) = P(A)P(B)`$):

$$P(X \le 2 \wedge Y \le 2) = 0{,}19123\cdot0{,}69881 \approx 0{,}13363$$

</details>

**Respuesta:** ≈ 0,13363

</details>

---

### V) Falta de memoria (teórico)

Sea X una v.a. exponencial y $a, b \in \mathbb{R}^+$. Probar que $P(X > a + b / X > b) = P(X > a)$.

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

**Herramientas** (las dos en 📄 H1):
- de $F(t) = 1 - e^{-\lambda t}$ sale $P(X > t) = 1 - F(t) = e^{-\lambda t}$ para t ≥ 0;
- la condicional, $P(A/B) = \frac{P(A\cap B)}{P(B)}$.

**Demostración paso a paso:**
1. Por la definición de condicional:

   $$P(X > a + b / X > b) = \frac{P(\{X > a+b\}\cap\{X > b\})}{P(X > b)}$$

2. **La intersección.** Como a > 0, si X supera a + b, seguro supera b. El evento $\{X > a+b\}$ está **incluido** en $\{X > b\}$, así que la intersección es solo $\{X > a + b\}$. Este es el paso que más se olvida justificar.
3. Se reemplaza con la fórmula de la exponencial y se simplifica, usando $e^{-\lambda(a+b)} = e^{-\lambda a}e^{-\lambda b}$:

   $$\frac{P(X > a+b)}{P(X > b)} = \frac{e^{-\lambda(a+b)}}{e^{-\lambda b}} = e^{-\lambda a} = P(X > a) \qquad ∎$$

</details>

**Respuesta:** queda demostrada la **propiedad de falta de memoria**: haber "sobrevivido" b no cambia la probabilidad de durar a más.

</details>

---

### VI) Función de distribución con k

Sea $`F(x) = \begin{cases}0 & x \le 0\\ kx^2 & 0 < x < 2\\ 1 & x \ge 2\end{cases}`$ la función de distribución de la v.a. X para algún valor de k. Hallar $V(4 - X)$ y $P(X > 1{,}3)$.

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

💡 **Función de distribución** $F(x) = P(X \le x)$: la probabilidad acumulada hasta x. En una variable continua no tiene saltos, y su derivada es la **densidad** f (❌, $`f = F'`$). La hoja trae el camino inverso, $F(x) = \int f$ (📄 H1).

**1. Hallar k.**
- **Camino rápido:** F no puede saltar. En x = 2 el tramo del medio tiene que llegar a 1: $k\cdot2^2 = 1$, así que $k = \frac14$.
- **Camino largo:** derivando, $f(x) = 2kx$ en (0; 2). El área total tiene que ser 1: $\int_0^2 2kx\,dx = kx^2\big|_0^2 = 4k = 1$, el mismo k.

Con k = ¼, la densidad es $f(x) = \frac12x$ en (0; 2).

**2. Momentos.** 📄 H1: $E(g(X)) = \int g(x)f(x)\,dx$.

$`\displaystyle E(X) = \int_0^2 x\cdot\frac12x\,dx = \frac{x^3}{6}\Big|_0^2 = \frac43 \qquad E(X^2) = \int_0^2 x^2\cdot\frac12x\,dx = \frac{x^4}{8}\Big|_0^2 = 2`$

**3. Varianza de 4 − X.** 💡 Propiedad: $V(aX + b) = a^2V(X)$. Sumar una constante (el 4) corre todos los valores igual y **no** cambia la dispersión. El −1 que multiplica a X sale **al cuadrado**: $(-1)^2 = 1$. Sale de 📄 H1, $V(aX + bY) = a^2V(X) + b^2V(Y) + 2ab\,Cov$, con la segunda variable constante (varianza 0).

$$V(4 - X) = V(X) = E(X^2) - E(X)^2 = 2 - \frac{16}{9} = \frac29$$

(📄 H1, $V(X) = E(X^2) - (E(X))^2$.)

**4. Probabilidad.** 📄 H1: $P(X > a) = 1 - F(a)$. Se usa F directamente, sin integrar:

$$P(X > 1{,}3) = 1 - \frac14(1{,}3)^2 = 1 - 0{,}4225 = 0{,}5775$$

</details>

**Respuesta:** k = 1/4, $V(4 - X) = 2/9$, $P(X > 1{,}3) = 0{,}5775$

</details>

---

[← Volver al menú principal](../../README.md)
