# 1.er Parcial — Tema 2 (05/2026)

Probabilidad y Estadística — UTN FRBA.

> **Aprobación:** al menos 2 de los primeros 4 puntos correctamente resueltos.
> **Promoción:** aprobación + el punto V o el VI correctamente resuelto. Los puntos V y VI sólo se corrigen si se alcanza la aprobación.

Cada ejercicio tiene un botón **Solución**. Al abrirlo aparece la respuesta y, arriba de ella, el botón **Solución paso a paso**.

---

### I) Ingenieros que estiman costos

Una compañía emplea a 2 ingenieros para estimar costos. Uno de ellos estima el 70 % de las cotizaciones. Cada uno tiene una tasa de error del 2 % y del 4 %, respectivamente. Si se observa una cotización **bien** estimada, ¿cuál es la probabilidad de que la haya estimado el ingeniero que **menos** trabaja?

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

**Sucesos:** A = "la estimó A" (70 %), B = "la estimó B" (30 %, el que menos trabaja), $\bar D$ = "está bien estimada".

**Datos:** $P(\bar D/A) = 1 - 0{,}02 = 0{,}98$ y $P(\bar D/B) = 1 - 0{,}04 = 0{,}96$.

**Probabilidad total:** $P(\bar D) = 0{,}7\cdot0{,}98 + 0{,}3\cdot0{,}96 = 0{,}686 + 0{,}288 = 0{,}974$.

**Bayes:**

$$P(B/\bar D) = \frac{P(\bar D/B)P(B)}{P(\bar D)} = \frac{0{,}288}{0{,}974} \approx 0{,}2957$$

</details>

**Respuesta:** $P(B/\bar D) \approx 0{,}2957$

</details>

---

### II) Llegadas a la cola del supermercado

El tiempo que transcurre entre la llegada de dos personas consecutivas a la cola del supermercado se distribuye exponencialmente, con un tiempo medio de 5 minutos. Si hace 4 minutos que no llega nadie, ¿cuál es la probabilidad de que la siguiente persona llegue **luego** de los próximos 2 minutos?

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

$E(X) = 5$ min ⇒ $\lambda = 0{,}2$ min⁻¹ y $P(X > t) = e^{-0{,}2t}$.

Se pide que llegue después del minuto 6, sabiendo que ya pasaron 4:

$$P(X > 6 / X > 4) = \frac{P(X > 6)}{P(X > 4)} = \frac{e^{-1{,}2}}{e^{-0{,}8}} = e^{-0{,}4} = P(X > 2) \approx 0{,}67032$$

(Falta de memoria: lo que ya se esperó no cuenta.)

</details>

**Respuesta:** ≈ 0,67032

</details>

---

### III) Elongación de barras de acero

La elongación de una barra de acero se distribuye normalmente con media 1,2 mm. En el 2,28 % de las veces que se somete a una carga, la elongación es superior a 1,6 mm. Si se someten **5** barras a una carga, calcular la probabilidad de que **a lo sumo 2** tengan una elongación mayor a 1 mm.

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

**1. Hallar σ.** $P(X > 1{,}6) = P(Z > 0{,}4/\sigma) = 0{,}0228 \Rightarrow 0{,}4/\sigma = 2 \Rightarrow \sigma = 0{,}2$ mm.

**2. Probabilidad de éxito:** $p = P(X > 1) = P(Z > -1) = 0{,}84134$.

**3. Binomial.** W ~ Bin(5; 0,84134):

$P(W \le 2) = \sum_{k=0}^{2}\binom5k0{,}84134^k\,0{,}15866^{5-k} \approx 0{,}03104$

</details>

**Respuesta:** σ = 0,2 mm y $P(W \le 2) \approx 0{,}03104$

</details>

---

### IV) Técnicos en dos cursos

En un curso de ingeniería electrónica de 30 estudiantes hay 20 técnicos, y en un curso de ingeniería civil de 25 estudiantes hay 10 técnicos. Si se elige al azar un grupo de 5 estudiantes de cada curso, ¿cuál es la probabilidad de que en ambos grupos haya **al menos 3** técnicos?

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

**Hipergeométricas** (sin reposición):
- X ~ H(N = 30, K = 20, n = 5): $P(X \ge 3) = 1 - P(X \le 2) \approx 1 - 0{,}19123 = 0{,}80877$
- Y ~ H(N = 25, K = 10, n = 5): $P(Y \ge 3) = 1 - P(Y \le 2) \approx 1 - 0{,}69881 = 0{,}30119$

Por independencia entre los grupos:

$P(X \ge 3 \wedge Y \ge 3) = 0{,}80877\cdot0{,}30119 \approx 0{,}24359$

</details>

**Respuesta:** ≈ 0,24359

</details>

---

### V) Falta de memoria (teórico)

Sea X una v.a. exponencial y $a, b \in \mathbb{R}^+$. Probar que $P(X > a + b / X > b) = P(X > a)$.

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

Si X ~ Exp(λ), entonces $P(X > t) = e^{-\lambda t}$. Como $\{X > a + b\} \subseteq \{X > b\}$:

$$P(X > a + b / X > b) = \frac{P(X > a + b)}{P(X > b)} = \frac{e^{-\lambda(a+b)}}{e^{-\lambda b}} = e^{-\lambda a} = P(X > a)$$

</details>

**Respuesta:** queda demostrada la propiedad de **falta de memoria** de la exponencial.

</details>

---

### VI) Función de distribución con k

Sea $F(x) = \begin{cases}0 & x \le 0\\ kx^2 & 0 < x < 2\\ 1 & x \ge 2\end{cases}$ la función de distribución de X. Hallar $V(3 - X)$ y $P(X > 1{,}2)$.

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

**1. Hallar k.** $f(x) = 2kx$ en (0, 2); $\int_0^2 2kx\,dx = 4k = 1 \Rightarrow k = \frac14$ ⇒ $f(x) = \frac12x$.

**2. Momentos.** $E(X) = \int_0^2\frac12x^2dx = \frac43$ y $E(X^2) = \int_0^2\frac12x^3dx = 2$.

**3. Varianza.** $V(3 - X) = (-1)^2V(X) = 2 - \frac{16}{9} = \frac29$.

**4. Probabilidad.** $P(X > 1{,}2) = 1 - F(1{,}2) = 1 - \frac14(1{,}2)^2 = 1 - 0{,}36 = 0{,}64$.

</details>

**Respuesta:** k = 1/4, $V(3 - X) = 2/9$, $P(X > 1{,}2) = 0{,}64$

</details>

---

[← Volver al menú principal](../../README.md)
