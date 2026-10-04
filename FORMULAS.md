# Resumen de fórmulas — Probabilidad y Estadística

Fórmulas de las Unidades 1 a 3. Notación: $\bar A$ = $A^c$ = A' = complemento de A ("no ocurre A"); $\Phi(z) = P(Z < z)$ para $Z \sim N(0;1)$.

---

## Unidad 1 — Probabilidades

### Operaciones entre sucesos

| Expresión | Significado |
|---|---|
| $A \cup B$ | ocurre A o B (alguno) |
| $A \cap B$ | ocurren A y B |
| $\bar A$ | no ocurre A |
| $A - B = A \cap \bar B$ | sólo ocurre A |
| $(A\cap\bar B)\cup(\bar A\cap B)$ | ocurre sólo uno |
| $\bar A \cap \bar B = \overline{A \cup B}$ | no ocurre ninguno (De Morgan) |
| $\bar A \cup \bar B = \overline{A \cap B}$ | no ocurren juntos (De Morgan) |

**Mutuamente excluyentes (M.E.):** $A \cap B = \emptyset$.

### Definiciones de probabilidad

- **Laplace** (resultados equiprobables): $P(A) = \dfrac{n_A}{n} = \dfrac{\text{casos favorables}}{\text{casos posibles}}$
- **Frecuencial:** $fr_A = \dfrac{n_A}{n} \xrightarrow[n\to\infty]{} P(A)$
- **Axiomas:** $P(A) \ge 0$; $P(S) = 1$; si $A \cap B = \emptyset$, entonces $P(A \cup B) = P(A) + P(B)$.

### Propiedades

$$P(\emptyset) = 0 \qquad P(\bar A) = 1 - P(A) \qquad 0 \le P(A) \le 1 \qquad A \subseteq B \Rightarrow P(A) \le P(B)$$

$$P(A \cup B) = P(A) + P(B) - P(A \cap B)$$

$$P(A\cup B\cup C) = P(A)+P(B)+P(C)-P(A\cap B)-P(A\cap C)-P(B\cap C)+P(A\cap B\cap C)$$

$$P(A \cap \bar B) = P(A) - P(A \cap B) \qquad P(\text{sólo uno}) = P(A) + P(B) - 2P(A\cap B)$$

### Probabilidad condicional y multiplicación

$$P(A/B) = \frac{P(A \cap B)}{P(B)} \quad (P(B) > 0)$$

$$P(A \cap B) = P(A)\,P(B/A) = P(B)\,P(A/B)$$

$$P(A_1\cap A_2\cap A_3) = P(A_1)\,P(A_2/A_1)\,P(A_3/A_1\cap A_2)$$

$$P(A/B) + P(\bar A/B) = 1$$

### Probabilidad total y Bayes

Si $A_1, \dots, A_n$ forman una **partición** de S (M.E. y su unión es S):

$$P(B) = \sum_{i=1}^n P(A_i)\,P(B/A_i) \qquad\qquad P(A_j/B) = \frac{P(A_j)\,P(B/A_j)}{\sum_i P(A_i)\,P(B/A_i)}$$

### Independencia

$$A \text{ y } B \text{ independientes} \iff P(A\cap B) = P(A)\,P(B) \iff P(A/B) = P(A)$$

- Si A y B son independientes, también lo son A y $\bar B$, $\bar A$ y B, y $\bar A$ y $\bar B$.
- M.E. con probabilidades positivas ⇒ **no** son independientes.
- Mutuamente independientes (tres sucesos): independencia de a pares **y** además $P(A\cap B\cap C) = P(A)P(B)P(C)$.
- "Al menos uno" con independencia: $P(A\cup B\cup C) = 1 - P(\bar A)P(\bar B)P(\bar C)$.

### Combinatoria

$$\binom nk = \frac{n!}{(n-k)!\,k!} \quad\text{(nCr en la calculadora)}$$

---

## Unidad 2 — Variables aleatorias

### Distribución

| | Discreta (VAD) | Continua (VAC) |
|---|---|---|
| Condiciones | $P(x_i) \ge 0$, $\sum P(x_i) = 1$ | $f(x) \ge 0$, $\int_{-\infty}^{\infty} f(x)\,dx = 1$ |
| $F(x) = P(X \le x)$ | $\sum_{x_i \le x} P(x_i)$ (escalera) | $\int_{-\infty}^{x} f(t)\,dt$ (continua) |
| $P(X = a)$ | $P(a)$ | 0 |
| $P(a \le X \le b)$ | $F(b) - F(a^-)$ | $F(b) - F(a)$ |
| $E(X)$ | $\sum x_i P(x_i)$ | $\int x f(x)\,dx$ |
| $E(g(X))$ | $\sum g(x_i) P(x_i)$ | $\int g(x) f(x)\,dx$ |

- En una VAC, $F'(x) = f(x)$ y no importa si las desigualdades son estrictas.
- Discreta: $P(X = x_i) = F(x_i) - F(x_{i-1})$ y $P(X \ge x_i) = 1 - F(x_{i-1})$.
- **Percentil / mediana:** el valor $x_q$ tal que $F(x_q) = q$ (la mediana es $q = 0{,}5$).

### Varianza y medidas

$$V(X) = E\big[(X - E(X))^2\big] = E(X^2) - E(X)^2 \qquad \sigma(X) = \sqrt{V(X)} \qquad CV = \frac{\sigma(X)}{E(X)}\cdot100\%$$

### Propiedades de E y V

| Esperanza | Varianza |
|---|---|
| $E(c) = c$ | $V(c) = 0$ |
| $E(aX + b) = aE(X) + b$ | $V(aX + b) = a^2V(X)$ |
| $E(X + Y) = E(X) + E(Y)$ | $V(X \pm Y) = V(X) + V(Y) \pm 2\,\text{Cov}(X,Y)$ |
| $E(XY) = E(X)E(Y)$ si son independientes | $V(X + Y) = V(X) + V(Y)$ si son independientes |

$$V(aX + bY) = a^2V(X) + b^2V(Y) + 2ab\,\text{Cov}(X,Y)$$

### Distribución conjunta (discreta)

$$P_X(x) = \sum_y P(x,y) \qquad P_Y(y) = \sum_x P(x,y) \qquad P(x/y) = \frac{P(x,y)}{P_Y(y)}$$

Son independientes si y sólo si $P(x,y) = P_X(x)P_Y(y)$ **para todo** (x, y).

### Covarianza y correlación

$$\text{Cov}(X,Y) = E(XY) - E(X)E(Y) \qquad \rho = \frac{\text{Cov}(X,Y)}{\sigma_X\sigma_Y}, \quad -1 \le \rho \le 1$$

- $\text{Cov}(aX, bY) = ab\,\text{Cov}(X,Y)$
- Si son independientes, entonces Cov = 0 (el recíproco es falso).

### Transformaciones (VAC)

Si $Y = g(X)$ es creciente: $F_Y(y) = F_X(g^{-1}(y))$. Para $Y = aX + b$: $f_Y(y) = \dfrac{1}{|a|}f_X\!\left(\dfrac{y-b}{a}\right)$.

Máximo y mínimo de n independientes iguales: $F_{\max}(x) = F(x)^n$ y $P(\min > x) = [1 - F(x)]^n$.

---

## Unidad 3 — Distribuciones especiales

### Discretas

| Distribución | Uso | $P(X = k)$ | $E(X)$ | $V(X)$ |
|---|---|---|---|---|
| **Bernoulli**(p) | éxito o fracaso | $P(1) = p$, $P(0) = 1-p$ | $p$ | $p(1-p)$ |
| **Binomial**(n; p) | éxitos en n pruebas independientes con p constante | $\binom nk p^k(1-p)^{n-k}$ | $np$ | $np(1-p)$ |
| **Hipergeométrica**(N; K; n) | éxitos al extraer n **sin reposición** de N (con K éxitos) | $\dfrac{\binom Kk\binom{N-K}{n-k}}{\binom Nn}$ | $n\dfrac KN$ | $n\dfrac KN\left(1-\dfrac KN\right)\dfrac{N-n}{N-1}$ |
| **Poisson**(λ = αt) | ocurrencias en un continuo t (α = intensidad) | $\dfrac{\lambda^k}{k!}e^{-\lambda}$ | $\lambda$ | $\lambda$ |

- **Poisson:** si cambia el intervalo, $\lambda' = \alpha\,t'$.
- **Recursivas:** $P(k+1) = \dfrac{(n-k)p}{(k+1)(1-p)}P(k)$ (binomial) y $P(k+1) = \dfrac{\lambda}{k+1}P(k)$ (Poisson).
- **"Al menos uno":** $P(X \ge 1) = 1 - P(X = 0)$. En la binomial es $1 - (1-p)^n$, y para hallar n: $n > \dfrac{\ln(1 - \text{objetivo})}{\ln(1-p)}$.

### Continuas

| Distribución | $f(x)$ | $F(x)$ | $E(X)$ | $V(X)$ |
|---|---|---|---|---|
| **Uniforme**(a; b) | $\dfrac{1}{b-a}$ en [a, b] | $\dfrac{x-a}{b-a}$ | $\dfrac{a+b}{2}$ | $\dfrac{(b-a)^2}{12}$ |
| **Exponencial**(λ) | $\lambda e^{-\lambda x}$, $x \ge 0$ | $1 - e^{-\lambda x}$ | $\dfrac1\lambda$ | $\dfrac1{\lambda^2}$ |
| **Normal**(μ; σ) | $\dfrac{1}{\sigma\sqrt{2\pi}}e^{-\frac12\left(\frac{x-\mu}{\sigma}\right)^2}$ | tabla Φ | $\mu$ | $\sigma^2$ |
| **Gamma**(α; λ) (guía) | $\dfrac{\lambda^\alpha x^{\alpha-1}e^{-\lambda x}}{\Gamma(\alpha)}$, $x > 0$ | — | $\dfrac\alpha\lambda$ | $\dfrac{\alpha}{\lambda^2}$ |

### Exponencial

$$P(X > a) = e^{-\lambda a} \qquad P(X < a) = 1 - e^{-\lambda a} \qquad x_q = \frac{-\ln(1-q)}{\lambda}$$

- **Falta de memoria:** $P(X > t_0 + \Delta t \,/\, X > t_0) = P(X > \Delta t)$.
- **Relación con Poisson:** el tiempo entre dos eventos de un proceso de Poisson con intensidad α es $Exp(\lambda = \alpha)$, porque $P(\text{0 eventos en } t) = e^{-\alpha t} = P(Y > t)$.
- **Gamma con α entero:** es el tiempo hasta el α-ésimo evento. $P(T > t) = P(Po(\lambda t) \le \alpha - 1)$.
- **Serie y paralelo:** con exponenciales independientes, $\min \sim Exp(\lambda_1 + \lambda_2)$ y $F_{\max} = F_1F_2$.

### Normal

$$Z = \frac{X - \mu}{\sigma} \sim N(0;1) \qquad P(X < a) = \Phi\!\left(\frac{a-\mu}{\sigma}\right) \qquad \Phi(-z) = 1 - \Phi(z)$$

$$P(a < X < b) = \Phi\!\left(\tfrac{b-\mu}{\sigma}\right) - \Phi\!\left(\tfrac{a-\mu}{\sigma}\right) \qquad x_q = \mu + z_q\,\sigma \qquad aX + b \sim N(a\mu + b;\ |a|\sigma)$$

| Intervalo | Probabilidad |
|---|---|
| $\mu \pm \sigma$ | 0,6827 |
| $\mu \pm 2\sigma$ | 0,9545 |
| $\mu \pm 3\sigma$ | 0,9973 |
| $\mu \pm 1{,}96\sigma$ | 0,95 |

Valores de z frecuentes: $z_{0{,}90} = 1{,}2816$, $z_{0{,}95} = 1{,}645$, $z_{0{,}975} = 1{,}96$, $z_{0{,}99} = 2{,}326$, $z_{0{,}995} = 2{,}576$.

### Cómo elegir el modelo

1. Hay que **contar** éxitos:
   - Con n fijo de pruebas independientes y p constante → **Binomial**.
   - Extrayendo sin reposición de un lote finito → **Hipergeométrica**.
   - En un continuo (tiempo, longitud, área) → **Poisson**.
2. Hay que **medir** una magnitud continua:
   - Igualmente probable en un intervalo → **Uniforme**.
   - Tiempo de espera o duración → **Exponencial**.
   - Valores simétricos alrededor de una media → **Normal**.
3. Si se pregunta "de n elementos, cuántos cumplen una condición" y la condición sale de otra distribución, primero se calcula p con esa distribución y después se usa una **Binomial(n; p)**.

---

[← Volver al menú principal](README.md)
