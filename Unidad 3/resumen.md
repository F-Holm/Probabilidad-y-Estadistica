# Unidad 3 — Variables aleatorias especiales

Resumen de la teoría y la práctica del material del aula virtual (Prof. Andrea Alvarez, PyE UTN-FRBA). Distribuciones discretas: Bernoulli, Binomial, Hipergeométrica y Poisson. Distribuciones continuas: Uniforme, Exponencial negativa y Normal. También la relación Exponencial–Poisson y el uso de la app *Probability Distributions*.

---

## 1. Bernoulli

Sea A un suceso de un experimento con $P(A) = p$ (probabilidad de **éxito**) y $P(\bar A) = 1 - p = q$ (probabilidad de **fracaso**).

La v.a. de Bernoulli asociada a A vale 1 si ocurre A y 0 si no ocurre: $R_X = \{0; 1\}$.

| $x$ | 0 | 1 |
|---|---|---|
| $P(x)$ | $1 - p$ | $p$ |

- Parámetro: $p$
- $E(X) = p$; $E(X^2) = p$
- $V(X) = p - p^2 = p(1 - p)$; $\sigma = \sqrt{p(1-p)}$

---

## 2. Binomial — $X \sim Bin(n; p)$

**X = cantidad de veces que ocurre A (éxito) en $n$ repeticiones independientes del experimento, con $P(A) = p$ constante en cada repetición.**

$R_X = \{0, 1, 2, \dots, n\}$.

### Deducción de la fórmula

- $P(X = 0) = P(\bar A_1 \cap \dots \cap \bar A_n) = (1-p)^n$ (por independencia).
- $P(X = 1) = n\,p\,(1-p)^{n-1}$ (el éxito puede estar en cualquiera de las n posiciones).
- En general, una secuencia concreta con $k$ éxitos y $n-k$ fracasos tiene probabilidad $p^k(1-p)^{n-k}$, y hay $\binom{n}{k}$ ordenamientos posibles.

$$\boxed{P(X = k) = \binom{n}{k} p^k (1-p)^{n-k}, \quad k = 0, 1, \dots, n}$$

**Número combinatorio** (en la calculadora, tecla nCr): $\binom{n}{k} = \dfrac{n!}{(n-k)!\,k!}$. Por ejemplo, $\binom52 = 10$ (hay 10 formas de ubicar 2 éxitos en 5 repeticiones), $\binom51 = 5$, $\binom50 = \binom55 = 1$.

### Esperanza y varianza

La binomial es la **suma de n Bernoulli independientes**: $X = \sum_{i=1}^n X_i$ con $X_i \sim$ Bernoulli($p$).
- $E(X) = \sum E(X_i) = np$
- $V(X) = \sum V(X_i) = np(1-p)$ (la varianza de la suma es la suma de las varianzas porque las $X_i$ son independientes)

### Ejemplo: bulones (5 % con falla en la rosca)

X = cantidad de bulones fallados entre n ⇒ $X \sim Bin(n; 0{,}05)$.
- a) Con n = 5, exactamente 2 fallados: $\binom52 0{,}05^2\,0{,}95^3 = 0{,}02143$ (con la tabla: F(2) − F(1)).
- b) Con n = 10, al menos uno: $P(X \ge 1) = 1 - P(X = 0) = 1 - 0{,}95^{10} = 0{,}40126$ (con la tabla: 1 − F(0)).
- c) Con n = 8, a lo sumo 1: $0{,}95^8 + 8\cdot0{,}05\cdot0{,}95^7 = 0{,}66342 + 0{,}27933 = 0{,}94275$ (con la tabla: F(1)).
- d) ¿Cuántos hay que revisar para que P(al menos uno fallado) > 0,90?
  $1 - 0{,}95^n > 0{,}90 \Rightarrow 0{,}95^n < 0{,}10 \Rightarrow n > \dfrac{\ln 0{,}10}{\ln 0{,}95} = 44{,}89 \Rightarrow$ **n ≥ 45** (verificación: con n = 44 da 0,89533 y con n = 45 da 0,90056). Ojo: al dividir por $\ln 0{,}95 < 0$ se invierte la desigualdad.
- e) Con 200 bulones se esperan $E(X) = 200\cdot0{,}05 = 10$ fallados.

---

## 3. Hipergeométrica — $X \sim Hip(N; K; n)$

Hay un lote de **N** elementos, de los cuales **K** son éxitos y N − K son fracasos. Se extraen **n sin reposición**. X = cantidad de éxitos entre los n extraídos.

Por Laplace (casos favorables / casos posibles):

$$\boxed{P(X = k) = \frac{\binom{K}{k}\binom{N-K}{n-k}}{\binom{N}{n}}}$$

Parámetros: N, K y n.

**Diferencia con la binomial**: en la binomial las repeticiones son independientes y $p$ es constante (con reposición o población infinita). En la hipergeométrica se extrae **sin reposición** de un lote finito, así que la probabilidad cambia en cada extracción.

### Ejemplo: 25 estudiantes, 18 técnicos

- a) Se eligen n = 5; exactamente 2 técnicos: $\dfrac{\binom{18}{2}\binom{7}{3}}{\binom{25}{5}} = \dfrac{153\cdot35}{53130} = 0{,}10079$.
- b) Se eligen n = 6; alguno técnico: $1 - P(X = 0) = 1 - \dfrac{\binom{7}{6}}{\binom{25}{6}} = 1 - \dfrac{7}{177100} = 0{,}99996$.
- c) Se eligen n = 4; más técnicos que no técnicos: $P(X \ge 3) = P(3) + P(4) = 0{,}69344$.

---

## 4. Poisson — $X \sim Po(\lambda)$

Cuenta la **cantidad de veces que ocurre un suceso A en un continuo t** (longitud, área, volumen o tiempo).

Ejemplos: fallas en la aislación de un cable (t = longitud), burbujas en el vidrio de una damajuana (t = volumen), fallas en un mantel (t = área), llamadas erróneas que llegan a una central (t = tiempo).

$R_X = \{0, 1, 2, \dots\} = \mathbb{N}_0$ (infinito numerable).

### Condiciones (proceso de Poisson)

Se divide el continuo t en n intervalos de amplitud $\Delta t = t/n$ y se hace $n \to \infty$:
1. En cada intervalo pequeño, la probabilidad de que A ocurra más de una vez es despreciable.
2. La probabilidad de que A ocurra en un intervalo depende sólo de su **amplitud**, no de su ubicación: $p = \alpha\,\Delta t = \alpha t/n$. **α es la intensidad del proceso** y es constante. Como $p \to 0$, A es un "suceso raro".
3. Las ocurrencias de A en intervalos distintos son **independientes**.

Entonces X es el **límite de una binomial** cuando $n \to \infty$ con $np = \alpha t$ fijo:

$$\boxed{P(X = k) = \frac{\lambda^k}{k!}e^{-\lambda}, \quad k = 0, 1, 2, \dots \qquad \lambda = \alpha\,t}$$

- Parámetro: λ (cantidad media de ocurrencias en el continuo t).
- $E(X) = \lambda$ y $V(X) = \lambda$.
- **Si cambia el tamaño del continuo, cambia λ**: se calcula α = λ/t y luego λ' = α·t'.

### Ejemplo: sala de emergencias

La cantidad de pacientes por semana es Poisson con media 3 (α = 3 por semana). Se pueden atender 4 por semana; el resto se deriva.
- a) P(derivar algún paciente) = $P(X \ge 5) = 1 - P(X \le 4) = 0{,}18474$.
- b) Cantidad esperada de derivados: Y = máx(X − 4, 0), con P(Y = 0) = P(X ≤ 4) = 0,81526, P(Y = 1) = P(X = 5) = 0,10082, … ⇒ $E(Y) = \sum y\,P(y) \approx 0{,}32$ pacientes por semana.
- c) ¿Cuántos hay que poder atender para no derivar en el 90 % de las semanas? P(X ≤ 4) = 0,81526 no alcanza; P(X ≤ 5) = 0,91608 > 0,90 ⇒ hay que poder atender **5 pacientes**.

---

## 5. Uniforme — $X \sim Uni(a; b)$

X se distribuye uniformemente en [a; b] si su densidad es constante en ese intervalo. Como el área total (un rectángulo) tiene que ser 1, la altura es $1/(b - a)$:

$$\boxed{f(x) = \frac{1}{b-a}, \quad a \le x \le b}$$

- Parámetros: a y b.
- $E(X) = \dfrac{a + b}{2}$ (el punto medio) y $V(X) = \dfrac{(b-a)^2}{12}$.
- Las probabilidades son áreas de rectángulos: $P(c < X < d) = \dfrac{d - c}{b - a}$ para $a \le c < d \le b$.

### Ejemplo: espera del tren (pasa cada 30 min) ⇒ $X \sim Uni(0; 30)$

- a) $P(X < 12) = 12\cdot\frac{1}{30} = 0{,}4$.
- b) Si ya esperó 10 min, P(esperar a lo sumo 5 min más) = $P(X < 15 / X > 10) = \dfrac{P(10 < X < 15)}{P(X > 10)} = \dfrac{5/30}{20/30} = 0{,}25$.
- c) Espera promedio: $E(X) = (0 + 30)/2 = 15$ min.

Video: https://youtu.be/Lq8Fx5P1J98

---

## 6. Exponencial negativa — $X \sim Exp(\lambda)$

$$\boxed{f(x) = \lambda e^{-\lambda x}, \quad x \ge 0 \;(\lambda > 0)}$$

Es densidad porque $\int_0^\infty \lambda e^{-\lambda x}dx = -e^{-\lambda x}\big|_0^\infty = 1$.

**Función de distribución** (se obtiene integrando y ajustando las constantes por los límites y la continuidad):
$$F(x) = \begin{cases} 0 & x < 0 \\ 1 - e^{-\lambda x} & x \ge 0 \end{cases}$$

- $P(X < a) = F(a) = 1 - e^{-\lambda a}$
- $P(X > a) = 1 - F(a) = e^{-\lambda a}$
- $E(X) = \dfrac1\lambda$, $E(X^2) = \dfrac{2}{\lambda^2}$, $V(X) = \dfrac{1}{\lambda^2}$, $\sigma(X) = \dfrac1\lambda$ (la media y el desvío coinciden).

Se usa para modelar duraciones o tiempos de espera.

### Propiedad de falta de memoria

$$P(X > t_0 + \Delta t \,/\, X > t_0) = P(X > \Delta t)$$

Que la componente ya haya durado $t_0$ no cambia la probabilidad de que dure $\Delta t$ más.

### Ejemplo: componentes electrónicas con duración media de 500 h

$\lambda = 1/500 = 0{,}002\ \text{h}^{-1}$.
- a) $P(X > 800) = e^{-1{,}6} = 0{,}2019$.
- b) $P(X > 600 / X > 500) = \dfrac{e^{-0{,}002\cdot600}}{e^{-0{,}002\cdot500}} = e^{-0{,}2} = 0{,}81873$ (falta de memoria).
- c) Duración del 40 % que más dura: $P(X > a) = 0{,}40 \Rightarrow e^{-\lambda a} = 0{,}4 \Rightarrow a = \dfrac{\ln 0{,}4}{-0{,}002} = 458{,}15$ h.
- d) Se eligen 5 componentes; P(a lo sumo 2 duren menos de 400 h). Primero $p = P(X < 400) = 1 - e^{-0{,}8} = 0{,}55067$. Luego Y = cantidad que dura menos de 400 h ~ Bin(5; 0,55067) ⇒ $P(Y \le 2) = 0{,}40564$.

Este último punto es un patrón muy común: **una distribución continua da la p de éxito para una binomial**.

Video: https://youtu.be/txbIJlSLtvU

---

## 7. Relación entre la Exponencial y Poisson

Si X ~ Po(λ = αt) cuenta las ocurrencias en un intervalo t, entonces P(ninguna ocurrencia en t) = $P(X = 0) = e^{-\alpha t}$.

Eso es lo mismo que decir que el tiempo Y entre dos eventos consecutivos supera t: $P(Y > t) = e^{-\alpha t}$.

$$\boxed{\text{El tiempo entre dos eventos consecutivos de Poisson es } Exp(\lambda_{Exp} = \alpha_{Po})}$$

(el parámetro de la exponencial es la **intensidad** del proceso de Poisson).

### Ejemplo (Ej. 12 de la guía): llegadas a una fila

P(ningún arribo en 5 min) = $e^{-1}$ ⇒ λ = 1 en 5 min ⇒ α = 1/5 min⁻¹ = 0,2 min⁻¹.
- a) Llegadas esperadas en una hora: λ = 0,2·60 = **12 personas**.
- b) P(pasan más de 6 min entre dos arribos) con Y ~ Exp(0,2): $P(Y \ge 6) = e^{-1{,}2} = 0{,}30119$.

---

## 8. Normal — $X \sim N(\mu; \sigma)$

$$\boxed{f(x) = \frac{1}{\sigma\sqrt{2\pi}}\,e^{-\frac12\left(\frac{x-\mu}{\sigma}\right)^2}}$$

- Parámetros: $\mu \in \mathbb{R}$ y $\sigma > 0$.
- $E(X) = \mu$, $V(X) = \sigma^2$, $\sigma(X) = \sigma$.
- Es la "campana de Gauss": simétrica respecto de μ y con puntos de inflexión en μ ± σ.

### Cálculo de probabilidades: estandarización

La densidad normal **no tiene primitiva conocida**, así que F(x) no se puede escribir con una fórmula. Con la sustitución $z = (x - \mu)/\sigma$ todo se lleva a la **normal estándar**:

$$\frac{X - \mu}{\sigma} = Z \sim N(0; 1) \qquad P(X < a) = P\left(Z < \frac{a - \mu}{\sigma}\right) = \Phi\left(\frac{a-\mu}{\sigma}\right)$$

- $\Phi(z) = P(Z < z)$ es la función de distribución de Z y está **tabulada** (hay tablas para z < 0 y z > 0), o se calcula con la app.
- $P(X > a) = 1 - \Phi\left(\frac{a-\mu}{\sigma}\right)$; $P(a < X < b) = \Phi\left(\frac{b-\mu}{\sigma}\right) - \Phi\left(\frac{a-\mu}{\sigma}\right)$.
- Por simetría: $\Phi(-z) = 1 - \Phi(z)$.
- **Percentiles** (problema inverso): si $P(X < a) = q$, entonces $a = \mu + z_q\,\sigma$, donde $z_q$ cumple $\Phi(z_q) = q$.

### Regla de los "seis sigmas" (68–95–99,7)

| Intervalo | Probabilidad |
|---|---|
| $\mu \pm \sigma$ | $\Phi(1) - \Phi(-1) = 0{,}84134 - 0{,}15866 = 0{,}68268$ (≈ 68 %) |
| $\mu \pm 2\sigma$ | $0{,}97725 - 0{,}02275 = 0{,}9545$ (≈ 95 %) |
| $\mu \pm 3\sigma$ | $0{,}99865 - 0{,}00135 = 0{,}9973$ (≈ 99,7 %) |

En una población normal, casi todos los valores (99,7 %) están en un rango de 6σ, a menos de 3σ de la media.

### Ejemplo (Ej. 30 de la guía): peso de los alumnos ~ N(75; 7) kg

- a) $P(X > 95) = 0{,}00214$.
- b) Alumnos con peso entre 80 y 95 kg, sobre 15000: $P(80 < X < 95) = 0{,}99786 - 0{,}76247 = 0{,}23539$. Con Y ~ Bin(15000; 0,23539), $E(Y) = np \approx 3531$ alumnos.
- c) Peso no superado por el 10 %: $P(X < a) = 0{,}10 \Rightarrow a = 66{,}03$ kg (**percentil 10**).
- d) Se eligen 10 alumnos; P(al menos la mitad pesa más de 80 kg). Primero $p = P(X > 80) = 0{,}23753$. Luego Y ~ Bin(10; 0,23753) ⇒ $P(Y \ge 5) = 0{,}0644$.

Video: https://youtu.be/191SI7D2Ahg

---

## 9. Herramientas de cálculo

- **Tablas**: la binomial está tabulada con su F acumulada (por eso P(X = 2) = F(2) − F(1), P(X ≥ 1) = 1 − F(0), etc.), y la normal estándar con Φ(z).
- **App *Probability Distributions*** (Matthew Bognar, Univ. de Iowa, para celular): se elige la distribución (Binomial, Hypergeometric, Poisson, Normal, Exponential, etc.), se cargan los parámetros y se pide $P(X = x)$, $P(X \le x)$ o $P(X \ge x)$ (o $P(X < x)$ y $P(X > x)$ en las continuas). Si se carga la probabilidad, devuelve el valor de x, lo que sirve para percentiles. La pestaña *Formulas* muestra la función de probabilidad, la media y la varianza.

---

## 10. Tabla resumen

| Distribución | Qué modela | $P(X = k)$ o $f(x)$ | $E(X)$ | $V(X)$ |
|---|---|---|---|---|
| Bernoulli($p$) | éxito/fracaso en una prueba | $P(1) = p$, $P(0) = 1 - p$ | $p$ | $p(1-p)$ |
| Binomial($n; p$) | n.º de éxitos en n pruebas independientes | $\binom{n}{k}p^k(1-p)^{n-k}$ | $np$ | $np(1-p)$ |
| Hipergeométrica($N; K; n$) | n.º de éxitos al extraer n sin reposición | $\dfrac{\binom{K}{k}\binom{N-K}{n-k}}{\binom{N}{n}}$ | $n\dfrac{K}{N}$ * | $n\dfrac{K}{N}\left(1-\dfrac{K}{N}\right)\dfrac{N-n}{N-1}$ * |
| Poisson($\lambda = \alpha t$) | n.º de ocurrencias en un continuo | $\dfrac{\lambda^k}{k!}e^{-\lambda}$ | $\lambda$ | $\lambda$ |
| Uniforme($a; b$) | valor "al azar" en un intervalo | $\dfrac{1}{b-a}$ en $[a; b]$ | $\dfrac{a+b}{2}$ | $\dfrac{(b-a)^2}{12}$ |
| Exponencial($\lambda$) | tiempo de espera o duración (sin memoria) | $\lambda e^{-\lambda x}$, $x \ge 0$ | $\dfrac1\lambda$ | $\dfrac1{\lambda^2}$ |
| Normal($\mu; \sigma$) | mediciones simétricas alrededor de μ | $\dfrac{1}{\sigma\sqrt{2\pi}}e^{-\frac12\left(\frac{x-\mu}{\sigma}\right)^2}$ | $\mu$ | $\sigma^2$ |

\* La esperanza y la varianza de la hipergeométrica no aparecen en las diapositivas del aula virtual; se agregan como referencia.

### Cómo elegir el modelo

1. ¿Se cuenta una cantidad de éxitos?
   - Con un n fijo de pruebas independientes y p constante → **Binomial**.
   - Extrayendo sin reposición de un lote finito y chico → **Hipergeométrica**.
   - En un continuo (tiempo, longitud, área), sin un n de pruebas → **Poisson**.
2. ¿Se mide una magnitud continua?
   - Igualmente probable en un intervalo → **Uniforme**.
   - Tiempo hasta un evento o entre eventos de Poisson → **Exponencial**.
   - Valores simétricos alrededor de una media → **Normal**.
3. Si se pregunta "de n elementos, cuántos cumplen una condición" y la condición viene de otra distribución, primero se calcula p con esa distribución y después se usa una **Binomial(n; p)**.

### Ejercicios de la guía sugeridos en el material

Binomial: 4, 5, 6 y 7 · Poisson: 10 a 13 · Uniforme: 14 y 15 · Exponencial: 16 a 21 · Normal y el resto: los ejercicios restantes de la guía.
