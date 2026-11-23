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

**Cómo reconocerlo:** dos "fuentes" (los ingenieros) y una pregunta **al revés**: sabiendo cómo salió la cotización, ¿quién la hizo? Eso es **Bayes**.

**Sucesos:** A = "la estimó A" (70 %), B = "la estimó B" (30 %, el que menos trabaja), $\bar D$ = "está **bien** estimada".

**Datos.** Las tasas de error son condicionales: P(D/A) = 0,02 y P(D/B) = 0,04. ⚠️ Pero se pregunta por las **bien** estimadas, así que se usan los complementos:

$$P(\bar D/A) = 1 - 0{,}02 = 0{,}98 \qquad P(\bar D/B) = 1 - 0{,}04 = 0{,}96$$

```
        ┌─ D̄   0,98  → 0,7·0,98 = 0,686
 A 0,7 ─┤
        └─ D   0,02
        ┌─ D̄   0,96  → 0,3·0,96 = 0,288
 B 0,3 ─┤
        └─ D   0,04
```

💡 **Probabilidad total:** se suman los caminos que terminan en $\bar D$:

$$P(\bar D) = 0{,}686 + 0{,}288 = 0{,}974$$

💡 **Bayes** (📄 H1): el camino de B dividido el total de bien estimadas.

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

💡 **Exponencial:** modela tiempos de espera. Su media es $E(X) = \frac1\lambda$ (📄 H1). Media 5 min significa λ = 0,2 por minuto. De $F(x) = 1 - e^{-\lambda x}$ (📄 H1) sale $P(X > t) = e^{-0{,}2t}$.

**Traducción.** "Hace 4 minutos que no llega nadie" es la condición X > 4. "Llega **luego** de los próximos 2 minutos" es X > 6. Se pide $P(X > 6 / X > 4)$.

**Con la definición de condicional** (📄 H1). Si X > 6, seguro X > 4, así que la intersección es X > 6:

$$P(X > 6 / X > 4) = \frac{P(X > 6)}{P(X > 4)} = \frac{e^{-1{,}2}}{e^{-0{,}8}} = e^{-0{,}4} \approx 0{,}67032$$

💡 **Falta de memoria** (📄 H1, $`P(X > t_0 + \Delta t / X > t_0) = P(X > \Delta t)`$). El resultado es justo P(X > 2): lo ya esperado no cuenta, y es como empezar de cero.
```
X~Exp(λ)   λ=0.2   P(X>x)   x=2   → 0.67032
```

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

Es una cadena: **Normal** (una barra) → **p** → **binomial** (5 barras).

**1. Hallar σ.** 💡 **Estandarizar** (📄 H1, $`Z = \frac{X - \mu}{\sigma}`$). El dato dice que 1,6 deja 2,28 % a la derecha. El z que deja eso es:
```
X~N(μ;σ)   μ=0   σ=1   P(X>x)=0.0228   → x=2.000
```

$$\frac{1{,}6 - 1{,}2}{\sigma} = 2 \;\Rightarrow\; \sigma = 0{,}2 \text{ mm}$$

**2. Una barra:**
```
X~N(μ;σ)   μ=1.2   σ=0.2   P(X>x)   x=1   → 0.84134
```

**3. Cinco barras.** 💡 **Binomial** (📄 H1): cada barra supera 1 mm (éxito) con la misma p, independientemente, y se cuentan cuántas. W ~ Bin(5; 0,84134). "A lo sumo 2" es 0, 1 o 2:

$$P(W \le 2) = \sum_{k=0}^{2}\binom5k0{,}84134^k\,0{,}15866^{5-k} \approx 0{,}03104$$

```
X~Bin(n,p)   n=5   p=0.84134   P(X≤x)   x=2   → 0.03104
```

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

💡 **Hipergeométrica** (📄 H1, $`\frac{\binom Kk\binom{N-K}{n-k}}{\binom Nn}`$): se eligen n de un grupo finito de N **sin reposición**, y se cuenta cuántos tienen una característica que tienen K del grupo.

- X = técnicos del grupo de electrónica ~ H(N = 30; K = 20; n = 5).
- Y = técnicos del grupo de civil ~ H(N = 25; K = 10; n = 5).

"Al menos 3" es lo contrario de "a lo sumo 2":
```
X~HG(N,K,n)   N=30   K=20   n=5   P(X≥x)   x=3   → 0.80877
X~HG(N,K,n)   N=25   K=10   n=5   P(X≥x)   x=3   → 0.30119
```

"En ambos grupos" es una intersección. Los grupos se eligen por separado (independientes), así que se multiplica (📄 H1):

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

**Herramientas** (📄 H1): $F(t) = 1 - e^{-\lambda t}$, así que $P(X > t) = e^{-\lambda t}$; y la condicional $P(A/B) = \frac{P(A\cap B)}{P(B)}$.

1. **Definición de condicional:**

   $$P(X > a+b / X > b) = \frac{P(\{X > a+b\}\cap\{X > b\})}{P(X > b)}$$

2. **La intersección.** Como a > 0, si X > a + b, seguro X > b: $\{X > a+b\} \subseteq \{X > b\}$. La intersección es $\{X > a + b\}$.
3. **Reemplazar y simplificar**, con $e^{-\lambda(a+b)} = e^{-\lambda a}e^{-\lambda b}$:

   $$\frac{e^{-\lambda(a+b)}}{e^{-\lambda b}} = e^{-\lambda a} = P(X > a) \qquad ∎$$

</details>

**Respuesta:** queda demostrada la propiedad de **falta de memoria** de la exponencial.

</details>

---

### VI) Función de distribución con k

Sea $`F(x) = \begin{cases}0 & x \le 0\\ kx^2 & 0 < x < 2\\ 1 & x \ge 2\end{cases}`$ la función de distribución de X. Hallar $V(3 - X)$ y $P(X > 1{,}2)$.

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

💡 $F(x) = P(X \le x)$ es la probabilidad acumulada. En una continua no salta, y su derivada es la densidad f (❌, $`f = F'`$).

**1. Hallar k.** F no puede saltar en x = 2: $k\cdot2^2 = 1$, así que $k = \frac14$. (Otra forma: $f(x) = 2kx$ y el área total $\int_0^2 2kx\,dx = 4k = 1$.) Entonces $f(x) = \frac12x$ en (0; 2).

**2. Momentos** (📄 H1, $`E(g(X)) = \int g(x)f(x)\,dx`$):

$`\displaystyle E(X) = \int_0^2 \frac12x^2\,dx = \frac43 \qquad E(X^2) = \int_0^2 \frac12x^3\,dx = 2`$

**3. Varianza.** 💡 $V(aX + b) = a^2V(X)$: la constante 3 no dispersa, y el −1 sale al cuadrado (📄 H1, $V(aX + bY)$ con la otra variable constante). Con 📄 H1, $V(X) = E(X^2) - E(X)^2$:

$$V(3 - X) = (-1)^2V(X) = 2 - \frac{16}{9} = \frac29$$

**4. Probabilidad** (📄 H1, $`P(X > a) = 1 - F(a)`$):

$$P(X > 1{,}2) = 1 - \frac14(1{,}2)^2 = 1 - 0{,}36 = 0{,}64$$

</details>

**Respuesta:** k = 1/4, $V(3 - X) = 2/9$, $P(X > 1{,}2) = 0{,}64$

</details>

---

[← Volver al menú principal](../../README.md)
