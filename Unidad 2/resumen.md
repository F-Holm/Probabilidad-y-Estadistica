# Unidad 2 — Variables aleatorias

Resumen de la teoría y la práctica del material del aula virtual (Prof. Andrea Alvarez, PyE UTN-FRBA): definición y clasificación de v.a., variables aleatorias discretas (VAD), valor esperado y varianza de VAD, variables aleatorias continuas (VAC), función de distribución de VAC, esperanza y varianza de VAC, distribución conjunta, covarianza, varianza de la suma y coeficiente de correlación.

---

## 1. Variable aleatoria: definición y clasificación

Muchas situaciones de probabilidad se repiten con la misma estructura y se pueden **modelizar** con una variable aleatoria. La idea es asociar un número real a cada resultado del experimento ("cuantificar" el espacio muestral) para poder analizarlo con herramientas de cálculo.

**Definición**: una variable aleatoria (v.a.) es una función $X: S \to \mathbb{R}$ que asigna un número real a cada resultado $s$ del experimento aleatorio.
- Dominio: S. Codominio: $\mathbb{R}$.
- **Recorrido** $R_X = \text{Im}(X)$: conjunto de valores que efectivamente toma X.

Ejemplos:
1. Tirar una moneda 2 veces, X = cantidad de caras: X(C,C) = 2, X(C,S) = X(S,C) = 1, X(S,S) = 0 ⇒ $R_X = \{0, 1, 2\}$.
2. X = cantidad de tiradas de un dado hasta que sale un 5 ⇒ $R_X = \{1, 2, 3, \dots\} = \mathbb{N}$.
3. X = cantidad de bolitas rojas entre 2 extraídas de una caja con 3 rojas y 7 blancas ⇒ $R_X = \{0, 1, 2\}$.
4. X = distancia entre dos monedas tiradas en una habitación de diagonal D ⇒ $R_X = [0; D]$ (un intervalo real).

### Clasificación

| Tipo | Recorrido $R_X$ | Ejemplos |
|---|---|---|
| **Discreta (VAD)** | finito o infinito **numerable** | 1, 2 y 3 |
| **Continua (VAC)** | infinito **no numerable** (intervalos) | 4 |

---

## 2. Variables aleatorias discretas (VAD)

Cada valor del recorrido proviene de resultados de un experimento, así que se le puede asignar una probabilidad.

### Función de probabilidad (distribución de probabilidades)

$P(x_i) = P(X = x_i)$ es función de probabilidad de X si:
- $P(x_i) \ge 0$ para todo $x_i \in R_X$
- $\sum_{x_i \in R_X} P(x_i) = 1$

Se representa con una tabla (x, P(x)) o con un gráfico de bastones.

**Dos VAD con el mismo recorrido pueden ser distintas**: lo que las diferencia es **cómo está distribuida la probabilidad**.
- Moneda tirada 2 veces: P(0) = 1/4, P(1) = 1/2, P(2) = 1/4 → distribución **simétrica**.
- 2 bolitas sin reposición (3 R y 7 B): P(0) = 7/10·6/9 = 7/15; P(1) = 2·3/10·7/9 = 7/15; P(2) = 3/10·2/9 = 1/15 → distribución **asimétrica**.

### Función de distribución (acumulada)

Para cualquier v.a.: $F(x) = P(X \le x)$ para todo $x \in \mathbb{R}$.

Para una VAD: $F(x) = \sum_{x_i \le x} P(x_i)$.

**Ejemplo** (X = cantidad de hijos de los empleados de una PYME):

| x | 0 | 1 | 2 | 3 | 4 |
|---|---|---|---|---|---|
| P(x) | 0,25 | 0,20 | 0,40 | 0,10 | 0,05 |
| F(x) | 0,25 | 0,45 | 0,85 | 0,95 | 1 |

$$F(x) = \begin{cases} 0 & x < 0 \\ 0{,}25 & 0 \le x < 1 \\ 0{,}45 & 1 \le x < 2 \\ 0{,}85 & 2 \le x < 3 \\ 0{,}95 & 3 \le x < 4 \\ 1 & x \ge 4 \end{cases}$$

F está definida para **todos los reales**: F(1,75) = 0,45, F(−2,4) = 0, F(6,15) = 1. Su gráfico es una **escalera**, y el salto en cada $x_i$ es $P(x_i)$.

**Características de F para una VAD**:
- $\lim_{x\to-\infty} F(x) = 0$ y $\lim_{x\to+\infty} F(x) = 1$ (acotada entre 0 y 1).
- Es **no decreciente**.
- Es discontinua en los puntos de $R_X$, pero **continua por derecha**.

**Cálculo de probabilidades con F** (para $x_i, x_j \in R_X$, donde $x_{i-1}$ es el valor anterior a $x_i$ en el recorrido):
- $P(X \le x_i) = F(x_i)$
- $P(X \ge x_i) = 1 - F(x_{i-1})$
- $P(x_i \le X \le x_j) = F(x_j) - F(x_{i-1})$
- $P(X = x_i) = F(x_i) - F(x_{i-1})$

En el ejemplo: P(X = 2) = 0,85 − 0,45 = 0,40; P(X ≤ 3) = 0,95; P(X ≥ 2) = 1 − 0,45 = 0,55; P(2 ≤ X ≤ 3) = 0,95 − 0,45 = 0,50.

En las VAD importa si la desigualdad es estricta o no: P(X < 2) ≠ P(X ≤ 2).

---

## 3. Valor esperado de una VAD

### Idea: promedio ponderado

X = salario semanal en la empresa B, con P(6000) = 0,6, P(8000) = 0,3 y P(10000) = 0,1.
- Promedio simple: (6000 + 8000 + 10000)/3 = 8000. Es incorrecto, porque ignora cuántos empleados hay en cada categoría.
- Promedio **ponderado**: 6000·0,6 + 8000·0,3 + 10000·0,1 = **7000**. El peso de cada valor lo da su probabilidad ($P(x_i) = N_i/N$).
- Los dos coinciden sólo si la distribución es simétrica (empresa A: 0,3 / 0,4 / 0,3 ⇒ ambos dan 8000).

### Definición

$$E(X) = \sum_{x_i \in R_X} x_i\,P(x_i)$$

Se lo llama valor esperado, valor medio, esperanza matemática o media de X. **No** es necesariamente un valor que X pueda tomar: es el valor al que se acerca el promedio de muchas repeticiones del experimento.

### Propiedades

1. $E(c) = c$
2. $E(cX) = c\,E(X)$
3. $E(X + Y) = E(X) + E(Y)$
4. $E(XY) = E(X)\,E(Y)$ **si X e Y son independientes**
5. $E(g(X)) = \sum g(x_i)\,P(x_i)$

En consecuencia: $E(aX + b) = a\,E(X) + b$.

### Ejemplo: tiro al blanco

Se paga \$100 por tiro y el premio es 30 × el puntaje. P(0) = 0,20, P(1) = 0,40, P(2) = 0,30, P(5) = 0,10.
- $E(X) = 0\cdot0{,}2 + 1\cdot0{,}4 + 2\cdot0{,}3 + 5\cdot0{,}1 = 1{,}5$ puntos.
- Ganancia: $Y = 30X - 100$. Y "hereda" la distribución de X (−100, −70, −40 y 50, con las mismas probabilidades).
- $E(Y) = 30\,E(X) - 100 = 30\cdot1{,}5 - 100 = -55$: el jugador pierde en promedio \$55 por tiro. Da lo mismo que calcular $\sum y_i P(y_i)$, pero las propiedades ahorran cuentas.

---

## 4. Varianza, desvío estándar y coeficiente de variación

### ¿Por qué hace falta?

Distintas distribuciones de "edad de los chicos de un jardín" tienen la misma media E(X) = 4 años, pero sus valores se reparten de manera muy distinta alrededor de ella. Si todos tienen 4 años, la media representa perfectamente al grupo; en los demás casos no.

- **Desvío**: $D(X) = X - E(X)$. Su promedio ponderado ("desvío medio") **siempre da 0**, así que no aporta información.
- Por eso se promedian los **cuadrados** de los desvíos.

### Definiciones

$$V(X) = E\left[(X - E(X))^2\right] = \sum_{x_i} (x_i - E(X))^2\,P(x_i)$$

**Fórmula de cálculo** (más práctica):
$$V(X) = E(X^2) - [E(X)]^2, \qquad E(X^2) = \sum x_i^2\,P(x_i)$$

Se deduce desarrollando el cuadrado: $E(X^2 - 2X\,E(X) + E(X)^2) = E(X^2) - 2E(X)^2 + E(X)^2$.

- La varianza tiene las unidades **al cuadrado** (años²), lo que no tiene una interpretación directa.
- **Desvío estándar**: $\sigma(X) = \sqrt{V(X)}$, en las mismas unidades que X.

**Ejemplos de los jardines** (todos con E(X) = 4 años):

| Distribución | E(X²) | V(X) | σ(X) |
|---|---|---|---|
| 4 con P = 1 (constante) | 16 | 0 | 0 |
| 3, 4, 5 con 0,3 / 0,4 / 0,3 | 16,6 | 0,6 | 0,77 |
| 3, 4, 5 con 0,1 / 0,8 / 0,1 | 16,2 | 0,2 | 0,45 (la menos dispersa) |
| 3, 4, 5 con 0,4 / 0,2 / 0,4 | 16,8 | 0,8 | 0,89 |
| 2, 4, 6 con 0,2 / 0,6 / 0,2 | 17,6 | 1,6 | 1,26 (la más dispersa) |

Un truco útil es armar la tabla con las columnas x, P(x), x·P(x), x²·P(x) y sumar cada columna.

### Coeficiente de variación

Si dos variables tienen **distinta media**, no alcanza con comparar los σ: se usa una medida **relativa**.

$$CV(X) = \frac{\sigma(X)}{E(X)}\cdot 100\%$$

Ejemplo de salarios: empresa A con E = \$40000 y σ = \$8000 ⇒ CV = 20 %; empresa B con E = \$80000 y σ = \$8500 ⇒ CV = 10,6 %. La distribución de A es más **heterogénea**, aunque su σ sea menor.

### Clasificación de medidas

- **Posición**: valor esperado.
- **Dispersión absoluta**: varianza y desvío estándar.
- **Dispersión relativa**: coeficiente de variación.

### Propiedades de la varianza

1. $V(X) \ge 0$
2. $V(c) = 0$
3. $V(cX) = c^2\,V(X)$ (y por lo tanto $V(aX + b) = a^2 V(X)$: sumar una constante no cambia la dispersión)
4. $V(X + Y) = V(X) + V(Y)$ **si X e Y son independientes** (caso general en la sección 8)

---

## 5. Variables aleatorias continuas (VAC)

Una VAC tiene recorrido infinito no numerable. La probabilidad **no** se asigna punto a punto, sino mediante una **función de densidad de probabilidad** $f(x)$.

### Función de densidad (f.d.)

$f(x)$ es función de densidad de X si y sólo si:
1. $f(x) \ge 0$ para todo $x \in \mathbb{R}$
2. $\int_{-\infty}^{+\infty} f(x)\,dx = 1$ (el área total bajo la curva es 1)

Las **probabilidades son áreas**:
- $P(X \le a) = \int_{-\infty}^{a} f(x)\,dx$
- $P(X \ge b) = \int_{b}^{+\infty} f(x)\,dx$
- $P(a \le X \le b) = \int_{a}^{b} f(x)\,dx$
- $P(X = a) = \int_a^a f(x)\,dx = 0$: **en una VAC la probabilidad puntual es 0**, así que da lo mismo usar < o ≤.

$f(x)$ no es una probabilidad (puede ser mayor que 1); lo que es probabilidad es el área.

### Ejemplo: facturación de un kiosco

X = facturación por hora, en miles de \$, con $f(x) = 2x$ si $0 \le x \le 1$ (0 en otro caso), así que $R_X = [0; 1]$.
- Es f.d.: $2x \ge 0$ y $\int_0^1 2x\,dx = x^2\big|_0^1 = 1$.
- $P(X < 0{,}7) = 0{,}7^2 = 0{,}49$ (en el 49 % de las horas factura menos de \$700).
- $P(X > 0{,}2) = 1 - 0{,}2^2 = 0{,}96$.
- $P(0{,}5 < X < 0{,}8) = 0{,}64 - 0{,}25 = 0{,}39$.
- **Mediana**: el valor $a$ tal que $P(X > a) = 0{,}5$ ⇒ $1 - a^2 = 0{,}5$ ⇒ $a = \sqrt{0{,}5} \approx 0{,}7071$. En la mitad de las horas factura más de \$707,1.

---

## 6. Función de distribución de una VAC

$$F(x) = P(X \le x) = \int_{-\infty}^{x} f(t)\,dt \quad \text{para todo } x \in \mathbb{R}$$

(t es la variable de integración; x es el límite superior).

**Características**: $\lim_{-\infty} F = 0$ y $\lim_{+\infty} F = 1$; es **continua** en todo $\mathbb{R}$; es no decreciente. Además $F'(x) = f(x)$ donde f es continua.

**Cálculo de probabilidades con F**:
- $P(X \le a) = P(X < a) = F(a)$
- $P(X \ge a) = P(X > a) = 1 - F(a)$
- $P(a \le X \le b) = P(a < X < b) = F(b) - F(a)$ (y también con los extremos mezclados)

En el gráfico, $F(a)$ es la **ordenada** de F en $a$ y es igual al **área** bajo f hasta $a$.

**Kiosco**: $F(x) = 0$ si $x < 0$; $x^2$ si $0 \le x \le 1$; $1$ si $x > 1$. Con F las probabilidades salen sin integrar: $F(0{,}7) = 0{,}49$, etc.

### Ejemplo (Ej. 15 de la guía): proporción de fallas

$f(x) = a(x - x^3)$ si $0 < x \le 1$.
- a) Para que $f \ge 0$ hace falta $a \ge 0$, y $\int_0^1 a(x - x^3)\,dx = a\left(\tfrac12 - \tfrac14\right) = \tfrac{a}{4} = 1$ ⇒ **a = 4**.
- b) Integrando por tramos: $F(x) = c_1$ si $x \le 0$; $2x^2 - x^4 + c_2$ si $0 < x \le 1$; $c_3$ si $x > 1$. Las constantes salen de las propiedades de F: $c_1 = 0$ y $c_3 = 1$ por los límites, y $c_2 = 0$ por continuidad en 0 y en 1. Entonces:
$$F(x) = \begin{cases} 0 & x \le 0 \\ 2x^2 - x^4 & 0 < x \le 1 \\ 1 & x > 1\end{cases}$$
- $P(X < 0{,}3) = F(0{,}3) = 0{,}1719$
- $P(X > 0{,}5) = 1 - F(0{,}5) = 1 - 0{,}4375 = 0{,}5625$
- Condicional: $P(X > 0{,}5 \,/\, X < 0{,}8) = \dfrac{F(0{,}8) - F(0{,}5)}{F(0{,}8)} = 1 - \dfrac{0{,}4375}{0{,}8704} = 0{,}4974$

---

## 7. Valor esperado y varianza de una VAC

$$E(X) = \int_{-\infty}^{+\infty} x\,f(x)\,dx \qquad E(X^2) = \int_{-\infty}^{+\infty} x^2 f(x)\,dx$$
$$V(X) = \int_{-\infty}^{+\infty} (x - E(X))^2 f(x)\,dx = E(X^2) - [E(X)]^2$$
$$E(g(X)) = \int_{-\infty}^{+\infty} g(x)\,f(x)\,dx$$

Valen **las mismas propiedades** que para las VAD (sumas reemplazadas por integrales).

**Kiosco**:
- $E(X) = \int_0^1 2x^2\,dx = 2/3 \approx 0{,}667$ ⇒ factura en promedio \$667 por hora.
- $E(X^2) = \int_0^1 2x^3\,dx = 1/2$.
- $V(X) = 1/2 - 4/9 = 1/18$; $\sigma = \sqrt{1/18} \approx 0{,}24$.
- $CV = 0{,}24/0{,}667 \approx 36\,\%$ ⇒ facturación "poco homogénea".

---

## 8. Distribución conjunta de dos VAD

### Función de probabilidad conjunta

$P(x, y) = P(X = x, Y = y)$ es función de probabilidad conjunta si:
- $P(x, y) \ge 0$ para todo $(x, y)$
- $\sum_x \sum_y P(x, y) = 1$

Se arma una **tabla de doble entrada**.

**Distribuciones marginales**: se suman las filas o las columnas.
$$P_X(x) = \sum_y P(x, y) \qquad P_Y(y) = \sum_x P(x, y)$$

### Ejemplo: bolígrafos

Hay 3 azules, 2 rojos y 3 verdes, y se sacan 2 sin reposición. X = cantidad de azules, Y = cantidad de rojos.

| P(x, y) | X = 0 | X = 1 | X = 2 | $P_Y(y)$ |
|---|---|---|---|---|
| **Y = 0** | 3/28 | 9/28 | 3/28 | 15/28 |
| **Y = 1** | 6/28 | 6/28 | 0 | 12/28 |
| **Y = 2** | 1/28 | 0 | 0 | 1/28 |
| $P_X(x)$ | 10/28 | 15/28 | 3/28 | 1 |

(por ejemplo, P(0, 0) = P(2 verdes) = 3/8·2/7 = 3/28 y P(1, 0) = 2·3/8·3/7 = 9/28).

- P(1 rojo) = P(0, 1) + P(1, 1) = $P_Y(1)$ = 12/28.

### Independencia de v.a.

$$X \text{ e } Y \text{ independientes} \iff P(x, y) = P_X(x)\,P_Y(y) \quad \text{para **todo** } (x, y)$$

Alcanza **un solo par** que no cumpla para que no sean independientes. En el ejemplo: $P(0, 0) = 3/28 \neq (10/28)(15/28)$ ⇒ no son independientes.

### Probabilidad condicional

$$P(x / y) = \frac{P(x, y)}{P_Y(y)}$$

Ejemplo: si no salió ningún azul, la probabilidad de que los dos sean rojos es $P(Y = 2 / X = 0) = \dfrac{1/28}{10/28} = \dfrac{1}{10}$.

---

## 9. Covarianza, varianza de la suma y correlación

### Covarianza

$$\text{Cov}(X, Y) = E\big[(X - E(X))(Y - E(Y))\big] = E(XY) - E(X)\,E(Y)$$

Mide la naturaleza de la **asociación** entre X e Y:
- **Cov > 0**: a valores grandes de X le corresponden valores grandes de Y (y a chicos, chicos).
- **Cov < 0**: a valores grandes de X le corresponden valores chicos de Y.

Para calcular $E(XY)$ se arma la distribución de $W = XY$ a partir de la tabla conjunta, o se calcula $\sum\sum x\,y\,P(x, y)$.

**Ejemplo de los bolígrafos**: E(X) = 3/4, E(Y) = 1/2. W = XY vale 1 sólo en (1, 1) ⇒ P(W = 1) = 6/28, así que E(XY) = 6/28 = 3/14.
$$\text{Cov}(X, Y) = \frac{3}{14} - \frac34\cdot\frac12 = -\frac{9}{56}$$
(Es negativa: cuantos más azules salen, menos rojos.)

**Propiedades**:
- Si X e Y son **independientes** ⇒ Cov(X, Y) = 0. **El recíproco es falso**: puede ser Cov = 0 sin que sean independientes.
- $\text{Cov}(aX, bY) = ab\,\text{Cov}(X, Y)$

### Varianza de la suma

$$V(X + Y) = V(X) + V(Y) + 2\,\text{Cov}(X, Y)$$
$$V(aX + bY) = a^2 V(X) + b^2 V(Y) + 2ab\,\text{Cov}(X, Y)$$

Si X e Y son independientes: $V(X + Y) = V(X) + V(Y)$. Además $V(X - Y) = V(X) + V(Y) - 2\text{Cov}(X, Y)$ (con a = 1 y b = −1).

### Coeficiente de correlación lineal

$$\rho(X, Y) = \frac{\text{Cov}(X, Y)}{\sigma_X\,\sigma_Y}$$

**Propiedades**:
1. $-1 \le \rho \le 1$ (no tiene unidades).
2. $\rho(aX, bY) = \dfrac{ab}{|ab|}\,\rho(X, Y)$: no cambia si $ab > 0$ y cambia de signo si $ab < 0$.

**Ejemplo de los bolígrafos**: E(X²) = 27/28 ⇒ V(X) = 45/112 ≈ 0,4018 y σ_X ≈ 0,63; E(Y²) = 16/28 ⇒ V(Y) = 9/28 ≈ 0,3214 y σ_Y ≈ 0,57.
$$\rho = \frac{-9/56}{\sqrt{45/112}\,\sqrt{9/28}} \approx -0{,}45$$

---

## 10. Resumen de fórmulas

| | VAD | VAC |
|---|---|---|
| Distribución | $P(x_i) \ge 0$, $\sum P(x_i) = 1$ | $f(x) \ge 0$, $\int f = 1$ |
| $F(x) = P(X \le x)$ | $\sum_{x_i \le x} P(x_i)$ (escalera) | $\int_{-\infty}^{x} f(t)\,dt$ (continua) |
| $P(X = a)$ | $P(a)$ | 0 |
| $E(X)$ | $\sum x_i P(x_i)$ | $\int x f(x)\,dx$ |
| $E(g(X))$ | $\sum g(x_i) P(x_i)$ | $\int g(x) f(x)\,dx$ |
| $V(X)$ | $E(X^2) - E(X)^2$ | $E(X^2) - E(X)^2$ |

Comunes a las dos: $E(aX + b) = aE(X) + b$; $V(aX + b) = a^2V(X)$; $\sigma = \sqrt V$; $CV = \sigma/E \cdot 100\%$; $\text{Cov} = E(XY) - E(X)E(Y)$; $V(X \pm Y) = V(X) + V(Y) \pm 2\text{Cov}$; $\rho = \text{Cov}/(\sigma_X\sigma_Y)$.

### Ejercicios de la guía sugeridos en el material

- Definición de v.a.: ejercicios 1 y 2.
- VAD y función de distribución: 1, 2, 4, 5, 6a y 6b.
- Valor esperado: 3a, 3b (sólo E(X)), 3c, 6c, 8a y 8b (sólo valor esperado) y 13.
- Varianza: hasta el ejercicio 13 inclusive.
- VAC: ejercicio 14; el 15 está resuelto en la sección 6.
