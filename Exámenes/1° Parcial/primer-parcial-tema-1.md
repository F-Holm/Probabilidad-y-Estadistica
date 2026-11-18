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

**Sucesos:** A = "la estimó el ingeniero A" (el que más trabaja), B = "la estimó el ingeniero B", D = "está mal estimada".

**Datos:** P(A) = 0,7, P(B) = 0,3, P(D/A) = 0,02, P(D/B) = 0,04.

**Probabilidad total:** $P(D) = 0{,}7\cdot0{,}02 + 0{,}3\cdot0{,}04 = 0{,}014 + 0{,}012 = 0{,}026$.

**Bayes:**

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

$E(X) = 5$ min ⇒ $\lambda = 1/5 = 0{,}2$ min⁻¹, con $F(x) = 1 - e^{-0{,}2x}$.

Se pide que llegue antes de los 6 minutos, sabiendo que ya pasaron 4:

$$P(X < 6 / X > 4) = \frac{P(4 < X < 6)}{P(X > 4)} = \frac{F(6) - F(4)}{e^{-0{,}8}} = \frac{e^{-0{,}8} - e^{-1{,}2}}{e^{-0{,}8}} = \frac{0{,}44933 - 0{,}30119}{0{,}44933} \approx 0{,}3297$$

Por la **falta de memoria** da lo mismo que $P(X < 2) = 1 - e^{-0{,}4} = 0{,}3297$.

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

**1. Hallar σ.** X ~ N(1,2; σ).

$P(X > 1{,}6) = P\left(Z > \frac{0{,}4}{\sigma}\right) = 0{,}0228 \Rightarrow \frac{0{,}4}{\sigma} = 2 \Rightarrow \sigma = 0{,}2$ mm.

**2. Probabilidad de éxito para una barra:**

$p = P(X > 1) = P(Z > -1) = \Phi(1) = 0{,}84134$.

**3. Binomial.** W = cantidad de barras con elongación mayor a 1 mm, entre 4 ⇒ W ~ Bin(4; 0,84134).

$P(W \ge 2) = 1 - P(W = 0) - P(W = 1) = 1 - 0{,}15866^4 - 4\cdot0{,}84134\cdot0{,}15866^3 \approx 0{,}98593$

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

Se extrae sin reposición de cursos finitos ⇒ **hipergeométricas**:
- X = técnicos del grupo de electrónica ~ H(N = 30, K = 20, n = 5)
- Y = técnicos del grupo de civil ~ H(N = 25, K = 10, n = 5)

$P(X \le 2) = \sum_{k=0}^{2}\frac{\binom{20}{k}\binom{10}{5-k}}{\binom{30}{5}} \approx 0{,}19123$

$P(Y \le 2) = \sum_{k=0}^{2}\frac{\binom{10}{k}\binom{15}{5-k}}{\binom{25}{5}} \approx 0{,}69881$

Los grupos se eligen de manera independiente:

$P(X \le 2 \wedge Y \le 2) = 0{,}19123\cdot0{,}69881 \approx 0{,}13363$

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

Si X ~ Exp(λ), entonces $P(X > t) = 1 - F(t) = e^{-\lambda t}$ para t ≥ 0.

Como a > 0, el evento $\{X > a + b\}$ está incluido en $\{X > b\}$, así que su intersección es $\{X > a + b\}$:

$$P(X > a + b / X > b) = \frac{P(X > a + b)}{P(X > b)} = \frac{e^{-\lambda(a+b)}}{e^{-\lambda b}} = e^{-\lambda a} = P(X > a)$$

</details>

**Respuesta:** queda demostrada la **propiedad de falta de memoria**: haber "sobrevivido" b no cambia la probabilidad de durar a más.

</details>

---

### VI) Función de distribución con k

Sea $F(x) = \begin{cases}0 & x \le 0\\ kx^2 & 0 < x < 2\\ 1 & x \ge 2\end{cases}$ la función de distribución de la v.a. X para algún valor de k. Hallar $V(4 - X)$ y $P(X > 1{,}3)$.

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

**1. Hallar k.** Derivando: $f(x) = 2kx$ en (0, 2).

$\int_0^2 2kx\,dx = kx^2\big|_0^2 = 4k = 1 \Rightarrow k = \frac14$ ⇒ $f(x) = \frac12x$.

(También sale de la continuidad de F en x = 2: $k\cdot4 = 1$.)

**2. Momentos.**

$E(X) = \int_0^2\frac12x^2dx = \frac{x^3}{6}\Big|_0^2 = \frac43$

$E(X^2) = \int_0^2\frac12x^3dx = \frac{x^4}{8}\Big|_0^2 = 2$

**3. Varianza.** Sumar una constante no cambia la varianza y $(-1)^2 = 1$:

$V(4 - X) = V(X) = 2 - \left(\frac43\right)^2 = 2 - \frac{16}{9} = \frac29$

**4. Probabilidad.**

$P(X > 1{,}3) = 1 - F(1{,}3) = 1 - \frac14(1{,}3)^2 = 1 - 0{,}4225 = 0{,}5775$

</details>

**Respuesta:** k = 1/4, $V(4 - X) = 2/9$, $P(X > 1{,}3) = 0{,}5775$

</details>

---

[← Volver al menú principal](../../README.md)
