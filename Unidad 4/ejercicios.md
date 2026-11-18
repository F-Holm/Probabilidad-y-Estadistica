# Unidad 4 — Ejercicios resueltos

Ejercicios de la **Práctica 4 de la Guía de TP** (Estimación).

Cada ejercicio tiene un botón **Solución**. Al abrirlo aparece la respuesta y, arriba de ella, un segundo botón **Solución paso a paso** con el desarrollo completo.

Notación: Φ(z) = P(Z < z) para Z ~ N(0; 1). $z_{q}$, $t_{n-1;\,q}$ y $\chi^2_{n-1;\,q}$ son los valores que dejan una probabilidad **acumulada q a la izquierda** (como en la app *Probability Distributions*).

> **Referencias:** ⭐ = ejercicio sugerido como prioritario por la cátedra · *(opcional)* = la cátedra indica que no es necesario resolverlo · (T) = ejercicio teórico · (\*) = requiere aplicación informática o de celular.

---

### 1) Temperaturas de los O-rings *(opcional)*

Los siguientes datos corresponden a las temperaturas de unión de los O-rings (°F), en una muestra de prueba de lanzamientos reales del motor de un cohete de un transbordador espacial:

84 49 60 83 66 47 45 70 68 91 65 58 33 53 78 82 55 61 49 70

- a) Hallar la media aritmética y la mediana de la muestra.
- b) ¿Qué indicaría un valor de la media muy superior al de la mediana?
- c) Calcular la varianza y el desvío estándar muestrales.
- d) Eliminar la observación mayor, repetir los cálculos y comparar los resultados.

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

a) n = 20, $\sum x_i = 1267$ ⇒ $\bar x = 1267/20 = 63{,}35$.

Ordenados, los lugares 10.° y 11.° son 61 y 65 ⇒ $\tilde x = (61 + 65)/2 = 63$.

b) La media es sensible a valores extremos y la mediana no. Si la media es mucho mayor que la mediana, hay valores muy grandes (outliers) o una distribución asimétrica a derecha.

c) $s^2 = \dfrac{\sum (x_i - \bar x)^2}{n-1} = 232{,}55$ y $s = \sqrt{232{,}55} = 15{,}25$.

d) Sin el 91 quedan n = 19: $\bar x = 61{,}89$, $\tilde x = 61$ (el 10.° valor), $s^2 = 200{,}77$, $s = 14{,}17$.

Al sacar el valor más alto bajan la media y la mediana, y también la dispersión.

</details>

**Respuesta:**

- a) $\bar x = 63{,}35$; $\tilde x = 63$
- b) Presencia de outliers (asimetría a derecha)
- c) $s^2 = 232{,}55$; $s = 15{,}25$
- d) $\bar x = 61{,}89$; $\tilde x = 61$; $s^2 = 200{,}77$; $s = 14{,}17$

</details>

---

### 2) Laboratorios de análisis de agua *(opcional)*

Se desea elegir un laboratorio para enviar a procesar muestras de agua. Se postulan para esto cinco candidatos. Los boxplots correspondientes a 10 mediciones de cada laboratorio de una muestra de agua que contiene un 4 % de impurezas se exhiben en la guía.

- a) ¿Cuál/es de los laboratorios tienen sesgo en sus mediciones?
- b) Entre los menos sesgados: ¿cuál es el más preciso? Justificar.

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

a) Un laboratorio es **insesgado** si sus mediciones están centradas en el valor real (4 %). En los boxplots, sólo L3 y L5 tienen la mediana alrededor de 4 %; los demás están corridos.

b) Entre L3 y L5, el más **preciso** es el de menor dispersión (caja y bigotes más cortos), que es L5.

</details>

**Respuesta:**

- a) Todos menos L3 y L5
- b) L5, por tener menor dispersión

</details>

---

### 3) Resistencias en serie ⭐

Un circuito funciona con varias resistencias independientes en serie, cada una de las cuales tiene distribución Normal con media 20 ohms y varianza 0,36 ohm².

- a) Si se instalan 6 de estas resistencias, ¿cuál es la probabilidad de que la resistencia del circuito sobrepase los 118 ohm?
- b) ¿Cuántas resistencias deberán instalarse de manera que la probabilidad de que la resistencia total exceda los 200 ohm sea aproximadamente 0,05?

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

a) $R = R_1 + \dots + R_6$ es suma de normales independientes:

$R \sim N(6\cdot20;\ \sqrt{6\cdot0{,}36}) = N(120;\ 1{,}47)$.

$P(R > 118) = 1 - \Phi\left(\frac{118 - 120}{1{,}47}\right) = 1 - \Phi(-1{,}36) = 0{,}91317$.

b) Con n resistencias: $R \sim N(20n;\ 0{,}6\sqrt n)$. Se pide $P(R > 200) = 0{,}05$:

$\frac{200 - 20n}{0{,}6\sqrt n} = z_{0{,}95} = 1{,}645 \Rightarrow 20n + 0{,}987\sqrt n - 200 = 0$.

Con $u = \sqrt n$: $20u^2 + 0{,}987u - 200 = 0 \Rightarrow u = 3{,}138 \Rightarrow n \approx 9{,}85$.

Se redondea hacia arriba ⇒ n = 10.

</details>

**Respuesta:**

- a) 0,91317
- b) n ≥ 10

</details>

---

### 4) Sueldos de las sucursales *(opcional)*

Una empresa agroalimentaria tiene tres sucursales en cierta región, cada una de ellas manejada por dos empleados. Los sueldos mensuales de estos empleados en miles de unidades monetarias se exhiben en la siguiente tabla:

| Sucursal | 1 | 1 | 2 | 2 | 3 | 3 |
|---|---|---|---|---|---|---|
| Empleado | 1 | 2 | 3 | 4 | 5 | 6 |
| Sueldo | 19,5 | 23,8 | 20,1 | 23,8 | 15,6 | 19,5 |

- a) Se seleccionan al azar dos empleados entre estos seis con reemplazo y se calcula el promedio de sus sueldos. Hallar la distribución muestral del sueldo medio.
- b) Se selecciona una de las tres sucursales al azar y se considera la variable aleatoria Z: "promedio de los sueldos de los dos empleados de la misma". Hallar la distribución de Z.
- c) Compare los resultados de (a) y (b) con la media y la varianza del sueldo de un empleado elegido al azar de la empresa.

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

Población X = sueldo de un empleado al azar: $E(X) = 122{,}3/6 = 20{,}38$ y $V(X) = \frac16\sum(x_i - 20{,}38)^2 = 7{,}978$.

a) Con reemplazo hay 36 pares equiprobables (n = 2, muestra aleatoria). La distribución de $\bar X$ se arma con todos los promedios posibles. Como es una m.a.:
- $E(\bar X) = E(X) = 20{,}38$
- $V(\bar X) = V(X)/2 = 3{,}989$

b) Promedios por sucursal: (19,5 + 23,8)/2 = 21,65; (20,1 + 23,8)/2 = 21,95; (15,6 + 19,5)/2 = 17,55. Cada uno con probabilidad 1/3.

c) $E(Z) = (21{,}65 + 21{,}95 + 17{,}55)/3 = 20{,}38 = E(X)$.

$V(Z) = \frac13\sum(z_i - 20{,}38)^2 = 4{,}028 \ne V(X)/2$.

En (b) los dos empleados no son independientes (salen de la misma sucursal), así que no vale $V(X)/n$.

</details>

**Respuesta:**

- a) $E(\bar X) = 20{,}38 = E(X)$; $V(\bar X) = 3{,}989 = \frac12V(X)$
- b) P(Z = 17,55) = P(Z = 21,65) = P(Z = 21,95) = 1/3
- c) $E(Z) = 20{,}38 = E(X)$; $V(Z) = 4{,}028 \ne \frac12V(X)$

</details>

---

### 5) Espesor de la pintura ⭐

Se supone que el espesor de cierta pintura al aceite (X) en mm tiene distribución Normal. Se realizaron las siguientes observaciones de espesores de esta pintura:

0,89 0,88 0,88 1,03 1,09 1,12 1,29 1,31 1,48 1,49 1,59 1,62 1,64 1,71 1,76 1,83

- a) Calcular a partir de la muestra la media, la varianza, el desvío estándar y la mediana.
- b) ¿Cuál/es de estos valores utilizaría para estimar el valor central de los espesores de esta pintura?
- c) Si la muestra tuviera tamaño 1000, ¿qué estimador puntual elegiría para la media? ¿En qué basa su elección?

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

a) n = 16, $\sum x_i = 21{,}61$ ⇒ $\bar x = 1{,}35$.

$s^2 = 0{,}1107$ y $s = 0{,}3327$.

Mediana: promedio de los lugares 8.° y 9.°: $(1{,}31 + 1{,}48)/2 = 1{,}395$.

b) Como la población es Normal, $\bar X$ es el mejor estimador de μ (insesgado, consistente y eficiente) ⇒ $\hat\mu = \bar x = 1{,}35$.

c) $\bar X$: es insesgado y $V(\bar X) = \sigma^2/n \to 0$ (consistente). Por la Ley de los Grandes Números, con n grande $\bar x$ queda muy cerca de μ.

</details>

**Respuesta:**

- a) $\bar x = 1{,}35$; $s^2 = 0{,}1107$; $s = 0{,}3327$; $\tilde x = 1{,}395$
- b) $\hat\mu = \bar x = 1{,}35$
- c) $\bar x$, por la Ley de los Grandes Números (consistencia)

</details>

---

### 6) Esperanza y varianza de una suma (T) ⭐

(T) Probar que si $X_1, X_2, \dots, X_n$ son variables aleatorias independientes idénticamente distribuidas con $E(X_i) = \mu$ y $V(X_i) = \sigma^2$, entonces:

- a) $E(X_1 + X_2 + \dots + X_n) = n\mu$
- b) $V(X_1 + X_2 + \dots + X_n) = n\sigma^2$

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

a) La esperanza es lineal (no hace falta independencia):

$E\left(\sum X_i\right) = \sum E(X_i) = \mu + \dots + \mu = n\mu$.

b) $V(X + Y) = V(X) + V(Y) + 2\,Cov(X; Y)$. Si son independientes, la covarianza es 0. Aplicándolo n − 1 veces:

$V\left(\sum X_i\right) = \sum V(X_i) = n\sigma^2$.

</details>

**Respuesta:**

- a) $E(\sum X_i) = \sum E(X_i) = n\mu$
- b) $V(\sum X_i) = \sum V(X_i) = n\sigma^2$, usando la independencia (covarianzas nulas)

</details>

---

### 7) Cajas de café ⭐

Una fábrica envasa paquetes de café cuyo peso es una variable aleatoria Normal de media 495 g y desvío estándar 18 g. Los paquetes se venden en cajas de 9 unidades. El peso de la caja de cartón es una variable aleatoria Normal de media 50 g y desvío estándar 4 g. Si se selecciona una caja al azar, ¿cuál es la probabilidad de que el peso no supere los 4.500 g? (Considerar los pesos de los paquetes como variables aleatorias independientes).

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

W = peso total = $X_1 + \dots + X_9 + C$ (suma de normales independientes).

- $E(W) = 9\cdot495 + 50 = 4505$ g
- $V(W) = 9\cdot18^2 + 4^2 = 2932$ ⇒ $\sigma_W = 54{,}15$ g

$P(W \le 4500) = \Phi\left(\frac{4500 - 4505}{54{,}15}\right) = \Phi(-0{,}092) = 0{,}46322$.

Ojo: el peso de 9 paquetes es $X_1 + \dots + X_9$ (varianza $9\sigma^2$), **no** $9X$ (que tendría varianza $81\sigma^2$).

</details>

**Respuesta:** 0,46322

</details>

---

### 8) Estatura de la población ⭐

En una población determinada, la estatura de una persona adulta tiene un promedio de 165 cm con una desviación estándar de 7 cm.

- a) Si se toma una muestra aleatoria de 100 personas en esta población, calcular la probabilidad de que la estatura media de la muestra exceda 168 cm.
- b) Si se supone distribución normal de las estaturas, hallar la probabilidad de que en una muestra de 36 personas el desvío de la estatura resulte superior a 6 cm.
- c) Si llamamos p a la proporción de personas de la población que superan el 1,70 m, hallar la probabilidad de que dicha proporción en una muestra de tamaño 36 supere el 20 %.

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

a) La distribución de la población es desconocida, pero n = 100 ≥ 30 ⇒ por TCL:

$\bar h \sim N\left(165;\ \frac7{\sqrt{100}}\right) = N(165;\ 0{,}7)$.

$P(\bar h > 168) = 1 - \Phi\left(\frac{3}{0{,}7}\right) = 1 - \Phi(4{,}29) \approx 0{,}00001$.

b) Población normal ⇒ $\frac{(n-1)S^2}{\sigma^2} = \frac{35S^2}{49} \sim \chi^2_{35}$.

$P(S > 6) = P(S^2 > 36) = P\left(\chi^2_{35} > \frac{35\cdot36}{49}\right) = P(\chi^2_{35} > 25{,}71) = 0{,}87403$.

c) Con h ~ N(165; 7): $p = P(h > 170) = 1 - \Phi(0{,}714) = 0{,}2375 \approx 0{,}24$.

n = 36 ≥ 30 ⇒ $\hat p \sim N\left(0{,}24;\ \sqrt{\frac{0{,}24\cdot0{,}76}{36}}\right) = N(0{,}24;\ 0{,}0712)$.

$P(\hat p > 0{,}20) = 1 - \Phi\left(\frac{0{,}20 - 0{,}24}{0{,}0712}\right) \approx 0{,}71$ (la guía da 0,71341 y el apunte 0,71615, según el redondeo de p).

</details>

**Respuesta:**

- a) 0,00001
- b) 0,87403
- c) 0,71341

</details>

---

### 9) Tiempo de secado de la pintura (\*) ⭐

(\*) La pintura para autopista de color amarillo tiene una especificación que recomienda que la varianza del tiempo de secado no supere los 20 min². Sabiendo que la distribución del tiempo de secado es aproximadamente Normal con varianza 16 min²:

- a) hallar la probabilidad de que la varianza del tiempo de secado en una muestra de tamaño 10 exceda los 42,77 min².
- b) hallar la variabilidad superada por el 20 % de las muestras de tamaño 10 de tiempos de secado.

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

Población normal ⇒ $\frac{9S^2}{16} \sim \chi^2_9$.

a) $P(S^2 > 42{,}77) = P\left(\chi^2_9 > \frac{9\cdot42{,}77}{16}\right) = P(\chi^2_9 > 24{,}06) = 0{,}00421$.

b) Se busca c con $P(S^2 > c) = 0{,}20$, es decir $\frac{9c}{16} = \chi^2_{9;\,0{,}80} = 12{,}24$.

$c = \frac{16\cdot12{,}24}9 = 21{,}76$ min².

</details>

**Respuesta:**

- a) 0,00421
- b) $s^2 = 21{,}76$ min²

</details>

---

### 10) Redondeo en el supermercado ⭐

En un supermercado se decide redondear el cobro de las ventas al entero más cercano. Si en un día se realizan 800 ventas y se supone que el redondeo tiene distribución Uniforme, hallar la probabilidad de que en ese día el supermercado pierda en el redondeo más de $9.

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

El redondeo de cada venta es $X_i \sim U(-0{,}5;\ 0{,}5)$ (ganancia o pérdida en pesos):
- $E(X_i) = 0$
- $V(X_i) = \frac{1^2}{12} = \frac1{12}$

W = redondeo total = $\sum_{i=1}^{800} X_i$. Por TCL (n = 800 ≥ 30):

$W \sim N\left(0;\ \sqrt{800/12}\right) = N(0;\ 8{,}165)$.

Perder más de $9 equivale a W < −9 (o W > 9 si se mide la pérdida), por simetría:

$P = 1 - \Phi\left(\frac9{8{,}165}\right) = 1 - \Phi(1{,}10) = 0{,}1351$.

</details>

**Respuesta:** 0,1351

</details>

---

### 11) Errores tipográficos ⭐

La primera tarea en un curso introductorio de programación por computadora implica correr un breve programa. Si la experiencia indica que el 40 % de todos los estudiantes principiantes no cometerán errores tipográficos, calcular la probabilidad aproximada de que en un grupo de 80 estudiantes:

- a) por lo menos 35 % no cometan errores.
- b) entre el 45 % y el 55 % cometan errores.

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

n = 80 ≥ 30 ⇒ por TCL la proporción muestral es aproximadamente normal, con desvío $\sqrt{\frac{0{,}4\cdot0{,}6}{80}} = 0{,}0548$.

a) $\hat p$ = proporción **sin** errores ~ N(0,40; 0,0548):

$P(\hat p \ge 0{,}35) = 1 - \Phi\left(\frac{0{,}35 - 0{,}40}{0{,}0548}\right) = 1 - \Phi(-0{,}91) = 0{,}8183$.

b) $\hat q$ = proporción **con** errores ~ N(0,60; 0,0548):

$P(0{,}45 < \hat q < 0{,}55) = \Phi(-0{,}91) - \Phi(-2{,}74) = 0{,}1776$.

(La guía da 0,81835 y 0,17846; las pequeñas diferencias son por redondeo de z.)

</details>

**Respuesta:**

- a) 0,81835
- b) 0,17846

</details>

---

### 12) Imperfecciones por pieza *(opcional)*

Se examinan 180 piezas recién fabricadas y se registra el número de imperfecciones por pieza. Sería ideal que las piezas fabricadas no tuvieran imperfecciones. Sea X: "número de imperfecciones en una pieza seleccionada al azar" y supongamos que X tiene distribución Poisson de parámetro λ. Se obtuvieron las siguientes observaciones:

| Imperfecciones por pieza | 0 | 1 | 2 | 3 | 4 | 5 | 6 | 7 |
|---|---|---|---|---|---|---|---|---|
| Frecuencia observada | 18 | 47 | 52 | 40 | 13 | 7 | 2 | 1 |

- a) Hallar las expresiones de los estimadores de momentos y de máxima verosimilitud correspondientes al valor del parámetro λ desconocido.
- b) Analizar si estos estimadores son insesgados.
- c) Con la estimación lograda, aproximar el valor de P(X < 4).

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

a) **Momentos:** se iguala $E(X) = \lambda$ al promedio muestral ⇒ $\hat\lambda = \bar X$.

**Máxima verosimilitud:** $L(\lambda) = \prod \frac{\lambda^{x_i}e^{-\lambda}}{x_i!}$, entonces $\ln L = \sum x_i\ln\lambda - n\lambda - \sum\ln x_i!$.

Derivando e igualando a 0: $\frac{\sum x_i}\lambda - n = 0 \Rightarrow \hat\lambda = \bar X$.

Con los datos: $\bar x = \frac{0\cdot18 + 1\cdot47 + 2\cdot52 + 3\cdot40 + 4\cdot13 + 5\cdot7 + 6\cdot2 + 7\cdot1}{180} = \frac{377}{180} = 2{,}09$.

b) $E(\bar X) = E(X) = \lambda$ ⇒ insesgado.

c) $P(X < 4) = P(X \le 3) = e^{-2{,}09}\left(1 + 2{,}09 + \frac{2{,}09^2}2 + \frac{2{,}09^3}6\right) = 0{,}84053$.

</details>

**Respuesta:**

- a) $\hat\lambda_{mom} = \hat\lambda_{MV} = \bar X$; estimación 2,09
- b) Sí, son insesgados
- c) 0,84053

</details>

---

### 13) Estimadores para una exponencial ⭐

Sea $X_1, X_2, X_3, X_4$ una muestra aleatoria de tamaño 4 de una población exponencial de parámetro α desconocido. Considere $f(x) = \alpha e^{-\alpha x}$. Se proponen los siguientes estadísticos para estimar (tener en cuenta el valor esperado de esta variable):

- $T_1 = \frac16(X_1 + X_2) + \frac13(X_3 + X_4)$
- $T_2 = \frac15(X_1 + 2X_2 + 3X_3 + 4X_4)$
- $T_3 = \frac14(X_1 + X_2 + X_3 + X_4)$

Se pide:

- a) Seleccionar el o los estimadores insesgados entre los propuestos.
- b) Elegir el de menor varianza entre los seleccionados en (a).
- c) Ver si el error cuadrático medio del estimador elegido en (b) es el mínimo.

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

Los estadísticos estiman la media $\mu = E(X) = 1/\alpha$, con $V(X_i) = 1/\alpha^2$.

a)
- $E(T_1) = \frac26\mu + \frac23\mu = \mu$ ⇒ insesgado.
- $E(T_2) = \frac{1+2+3+4}5\mu = 2\mu$ ⇒ sesgado.
- $E(T_3) = \frac44\mu = \mu$ ⇒ insesgado.

b)
- $V(T_1) = \left(\frac1{36}\cdot2 + \frac19\cdot2\right)\frac1{\alpha^2} = \frac5{18\alpha^2}$
- $V(T_3) = \frac4{16}\cdot\frac1{\alpha^2} = \frac1{4\alpha^2}$

Como 1/4 < 5/18, se elige $T_3$ (el promedio muestral).

c) Para un estimador insesgado, ECM = V. Entonces $ECM(T_3) = \frac1{4\alpha^2} < ECM(T_1)$.

$\bar X$ es el estimador insesgado de mínima varianza de μ ⇒ su ECM es el mínimo.

</details>

**Respuesta:**

- a) $T_1$ y $T_3$ son insesgados ($E = \mu$); $T_2$ es sesgado ($E(T_2) = 2\mu$)
- b) $V(T_1) = \frac5{18\alpha^2}$, $V(T_3) = \frac1{4\alpha^2}$ ⇒ $T_3$
- c) $ECM(T_3) = V(T_3)$: sí, es el mínimo

</details>

---

### 14) Error cuadrático medio (T) *(opcional)*

(T) Verificar que el error cuadrático medio de un estimador es la suma de la varianza del mismo y el cuadrado de su sesgo.

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

$ECM(\hat\theta) = E[(\hat\theta - \theta)^2] = E(\hat\theta^2) - 2\theta E(\hat\theta) + \theta^2$.

Se suma y resta $[E(\hat\theta)]^2$:

$ECM(\hat\theta) = \underbrace{E(\hat\theta^2) - [E(\hat\theta)]^2}_{V(\hat\theta)} + \underbrace{[E(\hat\theta)]^2 - 2\theta E(\hat\theta) + \theta^2}_{(E(\hat\theta) - \theta)^2}$.

</details>

**Respuesta:** $ECM(\hat\theta) = V(\hat\theta) + B(\hat\theta)^2$, con $B(\hat\theta) = E(\hat\theta) - \theta$ (sesgo).

</details>

---

### 15) $\bar X^2$ no estima bien a μ² (T) *(opcional)*

(T) Sea $X_1, \dots, X_n$ una muestra aleatoria de una población de la que se sabe que $E(X_i) = \mu$ y $V(X_i) = \sigma^2$. Demostrar que $\bar X^2$ no es un estimador insesgado de μ².

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

$V(\bar X) = E(\bar X^2) - [E(\bar X)]^2$. Como $E(\bar X) = \mu$ y $V(\bar X) = \sigma^2/n$:

$E(\bar X^2) = \mu^2 + \frac{\sigma^2}n$.

</details>

**Respuesta:** $E(\bar X^2) = \mu^2 + \frac{\sigma^2}n \ne \mu^2$ ⇒ es sesgado (sesgo σ²/n, que tiende a 0 cuando n crece).

</details>

---

### 16) Estimador de momentos de θ *(opcional)*

Se denota con X la proporción de tiempo que un estudiante, seleccionado al azar, emplea trabajando en cierta prueba de aptitud. Suponiendo que X tiene una distribución cuya función de densidad está dada por:

$$f(x) = \begin{cases}(\theta + 1)x^\theta & \text{si } 0 \le x \le 1\\ 0 & \text{en otro caso}\end{cases}$$

- a) Obtener el estimador de momentos de θ.
- b) Se toma una muestra aleatoria de 12 estudiantes, obteniendo las siguientes observaciones: 0,92 − 0,79 − 0,90 − 0,69 − 0,86 − 0,49 − 0,73 − 0,97 − 0,94 − 0,77 − 0,93 − 0,75. Calcular la estimación de θ para esta muestra.

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

a) $E(X) = \int_0^1 x(\theta + 1)x^\theta\,dx = \frac{\theta + 1}{\theta + 2}$.

Se iguala a $\bar X$: $\bar X(\theta + 2) = \theta + 1 \Rightarrow \hat\theta = \frac{1 - 2\bar X}{\bar X - 1}$.

b) $\bar x = 9{,}74/12 = 0{,}8117$ ⇒ $\hat\theta = \frac{1 - 1{,}6233}{0{,}8117 - 1} = 3{,}309$.

</details>

**Respuesta:**

- a) $\hat\theta = \dfrac{1 - 2\bar X}{\bar X - 1}$
- b) $\hat\theta = 3{,}309$

</details>

---

### 17) Horas de estudio de los ingresantes ⭐

Se quiere estimar el valor medio de las horas de estudio semanales de los alumnos recién ingresados a la UTN. Se toma una muestra de 100 alumnos y se obtiene un promedio de 4 hs 20 min. Sabiendo que la distribución de estos tiempos es aproximadamente Normal con desvío de 55 min:

- a) construir un intervalo de confianza de nivel 90 %, 95 % y 99 % para el valor medio de las horas semanales de estudio.
- b) comparar las longitudes de los intervalos construidos en (a) y dar una conclusión.

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

σ conocido ⇒ $IC_\mu = \bar x \pm z_{1-\alpha/2}\frac\sigma{\sqrt n}$, con $\bar x = 260$ min y $\frac\sigma{\sqrt n} = \frac{55}{10} = 5{,}5$ min.

a)
- 90 %: $z_{0{,}95} = 1{,}645$ ⇒ d = 9,05 ⇒ [250,95; 269,05]
- 95 %: $z_{0{,}975} = 1{,}96$ ⇒ d = 10,78 ⇒ [249,22; 270,78]
- 99 %: $z_{0{,}995} = 2{,}576$ ⇒ d = 14,17 ⇒ [245,83; 274,17]

b) La amplitud es $2d$ y crece con $z_{1-\alpha/2}$: a mayor confianza, intervalo más ancho (menos preciso).

</details>

**Respuesta:**

- a) $I_{90} = [250{,}925;\ 269{,}075]$, $I_{95} = [249{,}22;\ 270{,}78]$, $I_{99} = [245{,}81;\ 274{,}19]$ (en minutos)
- b) $L_{90} < L_{95} < L_{99}$: cuando aumenta la confianza se pierde precisión

</details>

---

### 18) Estatura promedio ⭐

Se quiere estimar la estatura promedio en la población, que se supone tiene una distribución Normal con σ = 4 cm. Se toma una muestra de 144 personas y se obtiene que el promedio muestral es de 168 cm.

- a) Calcular el intervalo de confianza para la altura promedio de la población con un nivel de confianza del 98 %.
- b) ¿De qué tamaño debería ser la muestra para mantener el mismo error muestral (que el obtenido en (a)) pero con un nivel de confianza del 95 %?

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

a) 1 − α = 0,98 ⇒ $z_{0{,}99} = 2{,}33$.

$d = 2{,}33\cdot\frac4{\sqrt{144}} = 0{,}78$ cm ⇒ $IC = [168 - 0{,}78;\ 168 + 0{,}78] = [167{,}22;\ 168{,}78]$ cm.

b) Con 1 − α = 0,95, $z_{0{,}975} = 1{,}96$ y se pide d ≤ 0,78:

$1{,}96\cdot\frac4{\sqrt n} \le 0{,}78 \Rightarrow \sqrt n \ge 10{,}05 \Rightarrow n \ge 101{,}0$ ⇒ **n = 102** (siempre se redondea hacia arriba).

</details>

**Respuesta:**

- a) $I_{98} = [167{,}22;\ 168{,}78]$ cm
- b) n ≃ 102

</details>

---

### 19) Interpretación de un IC para σ² (T) ⭐

(T) Supongamos que a partir de una muestra aleatoria $X_1, X_2, \dots, X_{100}$, donde $X_i$ es el tiempo de duración de cierto procedimiento que tiene distribución Normal con media de 20 minutos, se construyó un intervalo de confianza para la varianza poblacional de nivel 0,98 y este intervalo resultó [5,28; 10,2] min². Indicar si las siguientes afirmaciones son verdaderas o falsas, justificando adecuadamente en cada caso.

- a) La probabilidad de que σ² se encuentre entre 5,28 y 10,2 es de aproximadamente 98 %.
- b) Si en lugar de hacer 100 observaciones se hubieran tomado 1000 y se hubiera construido un intervalo de confianza de nivel 0,98, este último con certeza habría resultado incluido en [5,28; 10,2] min².
- c) Si se tomaran muchas muestras independientes de tamaño 100 y para cada una de ellas se calculara un intervalo de confianza con el mismo procedimiento, alrededor del 98 % de estos intervalos contendrían a σ².
- d) Si se duplica el tamaño de la muestra, la longitud del intervalo se reduciría a la mitad.
- e) Si se tomaran muchas muestras independientes de tamaño 100, los promedios muestrales de las mismas estarían contenidos en el intervalo $\left[20 - 1{,}96\frac{\sqrt{5{,}28}}{10};\ 20 + 1{,}96\frac{\sqrt{10{,}2}}{10}\right]$.

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

a) **F.** Una vez calculado, el intervalo es fijo y σ² también: lo contiene o no. El 98 % se refiere al **procedimiento**, no a un intervalo particular.

b) **F.** Con n = 1000 el intervalo suele ser más angosto, pero depende de la nueva $s^2$: no hay certeza de que quede dentro.

c) **V.** Es exactamente la interpretación frecuencial del nivel de confianza.

d) **F.** La longitud depende de $s^2$ y de los cuantiles χ², no es proporcional a 1/n (ni siquiera a $1/\sqrt n$ en forma exacta).

e) **F.** Se mezclan extremos de un IC para σ² con un intervalo para $\bar X$. Además, un intervalo no contiene a "todos" los promedios.

</details>

**Respuesta:** a) F · b) F · c) V · d) F · e) F

</details>

---

### 20) Resistencia de barras de cerámica ⭐

Un artículo de la revista *American Ceramic Society Bulletin* contiene información acerca de la distribución de las resistencias a la fractura, en MPa, de ciertas barras de cerámica quemadas en determinado horno: se sabe que tienen distribución Normal y que el desvío poblacional es σ = 3,73 MPa. Una muestra de tamaño n = 121 arrojó un promedio de $\bar X$ = 89,10 MPa.

- a) Calcular un intervalo de confianza del 95 % para la resistencia real promedio.
- b) ¿Cómo se modificaría este intervalo si se desconociera la varianza poblacional y la muestra arrojara una desviación estándar de 4,2 MPa?

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

a) σ conocido: $d = 1{,}96\cdot\frac{3{,}73}{11} = 0{,}665$ ⇒ [88,435; 89,765] ≈ [88,45; 89,75].

b) σ desconocido: se reemplaza por s = 4,2. Como n ≥ 30 se puede usar z (o $t_{120;\,0{,}975} = 1{,}98$, casi igual):

$d = 1{,}96\cdot\frac{4{,}2}{11} = 0{,}75$ ⇒ [88,35; 89,85].

El intervalo es más ancho porque s > σ.

</details>

**Respuesta:**

- a) $IC_{95} = [88{,}45;\ 89{,}75]$ MPa
- b) $IC_{95} = [88{,}34;\ 89{,}86]$ MPa (más ancho)

</details>

---

### 21) Hemoglobina de jugadores de hockey ⭐

Un artículo del *Journal of Sports Science* expone un intervalo de confianza para el promedio del nivel de hemoglobina de los jugadores de hockey sobre hielo (en g/dl) en la Olimpíada de Canadá. Con 20 jugadores, fue estimado con un 95 % de confianza, obteniéndose el intervalo (15,01; 15,59) g/dl.

- a) Indicar los valores de $\bar x$ y s para esta muestra. Suponga que el nivel de hemoglobina de los jugadores sigue una distribución Normal.
- b) Si se conociera la varianza poblacional y fuera de 0,36 (g/dl)², ¿cuál sería el nivel de confianza del intervalo construido?

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

a) El centro es la media: $\bar x = \frac{15{,}01 + 15{,}59}2 = 15{,}3$; semiamplitud d = 0,29.

σ desconocido y n = 20 < 30 ⇒ $d = t_{19;\,0{,}975}\frac s{\sqrt{20}}$, con $t_{19;\,0{,}975} = 2{,}093$:

$s = \frac{0{,}29\sqrt{20}}{2{,}093} = 0{,}62$.

b) Con σ = 0,6: $0{,}29 = z_{1-\alpha/2}\frac{0{,}6}{\sqrt{20}} \Rightarrow z_{1-\alpha/2} = 2{,}16$.

Entonces $1 - \alpha/2 = 0{,}9846$ ⇒ 1 − α ≈ 0,97.

</details>

**Respuesta:**

- a) $\bar x = 15{,}3$; s = 0,62
- b) 0,97

</details>

---

### 22) Resistencia de cuerdas ⭐

La resistencia a la rotura, expresada en kg, de 12 ejemplares de cuerda es de 280, 242, 270, 285, 273, 275, 266, 257, 285, 274, 258, 264. Estimar la resistencia media mediante un intervalo de confianza con nivel 0,95 suponiendo distribución Normal.

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

$\bar x = 269{,}08$; s = 12,57; n = 12 < 30 y σ desconocido ⇒ t de Student con 11 g.l.: $t_{11;\,0{,}975} = 2{,}201$.

$d = 2{,}201\cdot\frac{12{,}57}{\sqrt{12}} = 7{,}99$ ⇒ [261,09; 277,07].

</details>

**Respuesta:** $IC_{95} = [261{,}09;\ 277{,}06]$ kg

</details>

---

### 23) Desvío de resistencias eléctricas ⭐

Se tomó una muestra de n = 36 resistencias eléctricas, resultando la desviación estándar muestral de las lecturas s = 2,81 ohm. Suponiendo normalidad en la distribución de las resistencias, hallar un intervalo de confianza de 95 % para σ.

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

$IC_\sigma = \left[\sqrt{\frac{(n-1)s^2}{\chi^2_{n-1;\,1-\alpha/2}}};\ \sqrt{\frac{(n-1)s^2}{\chi^2_{n-1;\,\alpha/2}}}\right]$, con 35 g.l.:
- $\chi^2_{35;\,0{,}025} = 20{,}6$
- $\chi^2_{35;\,0{,}975} = 53{,}2$

$(n-1)s^2 = 35\cdot2{,}81^2 = 276{,}36$ ⇒ $IC_\sigma = \left[\sqrt{\frac{276{,}36}{53{,}2}};\ \sqrt{\frac{276{,}36}{20{,}6}}\right] = [2{,}28;\ 3{,}66]$ ohm.

</details>

**Respuesta:** $IC_{95} = [2{,}28;\ 3{,}67]$ ohm

</details>

---

### 24) Altura de un río ⭐

Se midió la altura de un río en un punto geográfico dado durante 20 días al azar del verano, obteniéndose los siguientes valores en cm:

69,5 71,9 72,6 73,1 73,3 73,5 75,5 75,7 75,8 76,1 79,7 79,5 80,1 82,6 83,7 92,7 78,0 77,9 78,1 79,6

- a) ¿Qué condiciones se necesitan para que resulte válida la construcción de un intervalo de confianza para la varianza poblacional?
- b) Construir un intervalo de confianza de 99 % para la desviación estándar de la distribución de la altura de este río en verano.

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

a) La fórmula sale de $\frac{(n-1)S^2}{\sigma^2} \sim \chi^2_{n-1}$, que vale sólo si la población es **Normal** y las observaciones son **independientes** (m.a.).

b) $s^2 = 26{,}35$; con 19 g.l.:
- $\chi^2_{19;\,0{,}005} = 6{,}844$
- $\chi^2_{19;\,0{,}995} = 38{,}58$

$IC_\sigma = \left[\sqrt{\frac{19\cdot26{,}35}{38{,}58}};\ \sqrt{\frac{19\cdot26{,}35}{6{,}844}}\right] = [3{,}602;\ 8{,}553]$ cm.

</details>

**Respuesta:**

- a) Distribución Normal e independencia de las observaciones
- b) $IC_{99} = [3{,}602;\ 8{,}553]$ cm

</details>

---

### 25) Obra de teatro: tamaño de muestra ⭐

Se quiere estimar la proporción de personas que han visto una cierta obra de teatro en cartel. ¿Qué tamaño de muestra se deberá tomar para asegurar un nivel de confianza del 99 % y un margen de error de 0,02? Para el tamaño de muestra obtenido, hallar el intervalo de confianza para la proporción en cuestión, asumiendo que la proporción muestral es de 0,35. ¿Se logró el error objetivo?

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

Sin información previa sobre p se toma el peor caso p(1 − p) = 0,25:

$z_{0{,}995}\sqrt{\frac{0{,}25}n} \le 0{,}02 \Rightarrow n \ge \frac{2{,}58^2\cdot0{,}25}{0{,}02^2} = 4160{,}25$ ⇒ **n = 4161**.

Con $\hat p = 0{,}35$: $d = 2{,}58\sqrt{\frac{0{,}35\cdot0{,}65}{4161}} = 0{,}019$ ⇒ [0,331; 0,369].

Como d = 0,019 ≤ 0,02, sí se logró.

</details>

**Respuesta:** n ≥ 4161; $IC_{99} = [0{,}331;\ 0{,}369]$; sí se logró el error (d ≈ 0,019).

</details>

---

### 26) Elongación de telas *modal* ⭐

En una muestra de 81 piezas de tela *modal* se obtuvo una elongación media muestral de 8,17 % y un desvío estándar muestral del 1,42 %. Además, la tercera parte de las telas observadas tuvo elongaciones superiores a 8,4. Suponiendo que la elongación sigue una distribución Normal, estimar mediante un intervalo del 95 % de confianza:

- a) el verdadero valor medio de elongación μ.
- b) el desvío estándar poblacional de la elongación σ.
- c) la proporción poblacional de telas con elongación superior a 8,4.

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

a) σ desconocido, n = 81: $t_{80;\,0{,}975} = 1{,}99$.

$d = 1{,}99\cdot\frac{1{,}42}9 = 0{,}314$ ⇒ [7,856; 8,484].

b) $(n-1)s^2 = 80\cdot1{,}42^2 = 161{,}31$; con 80 g.l.:
- $\chi^2_{80;\,0{,}025} = 57{,}15$
- $\chi^2_{80;\,0{,}975} = 106{,}63$

$IC_\sigma = \left[\sqrt{161{,}31/106{,}63};\ \sqrt{161{,}31/57{,}15}\right] = [1{,}23;\ 1{,}68]$.

c) $\hat p = 1/3$: $d = 1{,}96\sqrt{\frac{(1/3)(2/3)}{81}} = 0{,}103$ ⇒ [0,231; 0,436].

</details>

**Respuesta:**

- a) $IC_\mu = [7{,}856;\ 8{,}484]$
- b) $IC_\sigma = [1{,}23;\ 1{,}68]$
- c) $IC_p = [0{,}231;\ 0{,}436]$

</details>

---

### 27) Defectos en neumáticos ⭐

Un artículo sobre "Evaluaciones de neumáticos bajo condición de esfuerzo" reporta que de una muestra aleatoria de 350 neumáticos, 54 mostraron daños severos, 48 manchas y 16 ambos tipos de defecto.

- a) Calcular un intervalo de confianza del 99 % para la proporción de neumáticos con algún defecto.
- b) Calcular un intervalo de confianza del 95 % para la proporción de neumáticos con más de un defecto.
- c) Calcular un intervalo de confianza del 95 % para la proporción de neumáticos con un único defecto.

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

Tabla de doble entrada (D = daño severo, M = manchas):

|  | M | sin M | Total |
|---|---|---|---|
| D | 16 | 38 | 54 |
| sin D | 32 | 264 | 296 |
| Total | 48 | 302 | 350 |

a) Algún defecto: 54 + 48 − 16 = 86 ⇒ $\hat p = 0{,}2457$.

$d = 2{,}576\sqrt{\frac{0{,}2457\cdot0{,}7543}{350}} = 0{,}0593$ ⇒ [0,1864; 0,3050].

b) Ambos defectos: 16 ⇒ $\hat p = 0{,}0457$.

$d = 1{,}96\sqrt{\frac{0{,}0457\cdot0{,}9543}{350}} = 0{,}0219$ ⇒ [0,0238; 0,0676].

c) Un único defecto: 38 + 32 = 70 ⇒ $\hat p = 0{,}2$.

$d = 1{,}96\sqrt{\frac{0{,}2\cdot0{,}8}{350}} = 0{,}0419$ ⇒ [0,1581; 0,2419].

(Todas cumplen n = 350 ≥ 100, así que vale la aproximación normal.)

</details>

**Respuesta:**

- a) $IC_{99} = [0{,}1863;\ 0{,}3051]$
- b) $IC_{95} = [0{,}0238;\ 0{,}0676]$
- c) $IC_{95} = [0{,}1581;\ 0{,}2419]$

</details>

---

### 28) Grasa en salchichas ⭐

Considere las siguientes muestras de contenido de grasa (en porcentaje) de salchichas seleccionadas al azar de dos marcas A y B:

| A | 25,2 | 21,3 | 22,8 | 17 | 29,8 | 21 | 25,5 | 16 | 20,9 | 19,5 |
|---|---|---|---|---|---|---|---|---|---|---|
| **B** | 24,2 | 20,7 | 21 | 18,9 | 29,1 | 20,5 | 25,2 | 16,3 | | |

Si se supone que los porcentajes de grasa de ambas marcas tienen distribución Normal:

- a) Hallar un intervalo de confianza del 95 % para la diferencia entre los contenidos medios de grasa de las dos marcas.
- b) ¿Es necesario pedir el cumplimiento de alguna otra condición?
- c) Si se conoce que el desvío estándar poblacional del contenido de grasa de la primera marca es de 2,8 g, mientras que el de la segunda es de 2,3 g, construir nuevamente el intervalo pedido en (a).

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

Muestras:
- A: $n_A = 10$, $\bar x_A = 21{,}9$, $s_A = 4{,}13$
- B: $n_B = 8$, $\bar x_B = 21{,}99$, $s_B = 4{,}01$

a) Varianzas desconocidas, supuestas iguales ⇒ varianza amalgamada:

$s_p = \sqrt{\frac{9\cdot4{,}13^2 + 7\cdot4{,}01^2}{16}} = 4{,}08$ (está entre $s_A$ y $s_B$, como debe ser).

$t_{16;\,0{,}975} = 2{,}12$ ⇒ $d = 2{,}12\cdot4{,}08\sqrt{\frac1{10} + \frac18} = 4{,}10$.

$\bar x_A - \bar x_B = -0{,}09$ ⇒ [−4,19; 4,02].

b) Además de normalidad: muestras **independientes** y **varianzas poblacionales iguales** ($\sigma_A = \sigma_B$), que es lo que permite usar $s_p$ y la t con $n_A + n_B - 2$ g.l.

c) Varianzas conocidas: $d = 1{,}96\sqrt{\frac{2{,}8^2}{10} + \frac{2{,}3^2}8} = 2{,}356$ ⇒ [−2,44; 2,27].

En ambos casos el 0 está dentro del intervalo: no hay evidencia de diferencia entre las marcas.

</details>

**Respuesta:**

- a) $IC_{95} = [-4{,}183;\ 4{,}023]$
- b) Independencia y varianzas iguales
- c) $IC_{95} = [-2{,}436;\ 2{,}276]$

</details>

---

### 29) Bicisendas *(opcional)*

Se tomaron dos muestras aleatorias de 1000 individuos de Capital Federal y 1500 de la provincia de Buenos Aires y se las encuestó respecto a si acuerdan con la construcción de bicisendas en su barrio o localidad. Como resultado de la encuesta, 400 de los individuos de Capital Federal manifestaron estar de acuerdo, mientras que 900 de la provincia de Buenos Aires acuerdan con la medida.

- a) Hallar un intervalo de confianza de nivel asintótico 95 % para la diferencia de proporciones de acuerdo con la bicisenda en las dos poblaciones.
- b) ¿En cuánto se reduce la longitud del intervalo si se considera una confianza del 90 %?

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

$\hat p_1 = 400/1000 = 0{,}4$ (Capital) y $\hat p_2 = 900/1500 = 0{,}6$ (Provincia).

a) $d = 1{,}96\sqrt{\frac{0{,}4\cdot0{,}6}{1000} + \frac{0{,}6\cdot0{,}4}{1500}} = 0{,}0392$.

Para $p_2 - p_1$: 0,2 ± 0,0392 = [0,1608; 0,2392]. Amplitud 0,0784. (Para $p_1 - p_2$ es [−0,2392; −0,1608].)

b) $z_{0{,}95} = 1{,}645$ ⇒ d = 0,0329 ⇒ [0,167; 0,233]. Amplitud 0,0658.

0,0658/0,0784 = 0,84 ⇒ se reduce un **16 %** (el cociente es $1{,}645/1{,}96$, no depende de los datos).

</details>

**Respuesta:**

- a) $IC_{95} = [0{,}1608;\ 0{,}2392]$
- b) $IC_{90} = [0{,}167;\ 0{,}233]$: se reduce un 16 %

</details>

---

### 30) Concentración del antibiótico según el equipo ⭐

Se piensa que la concentración del ingrediente activo de un antibiótico es afectada por el tipo de instrumental utilizado en el proceso de fabricación. Se sabe que la desviación estándar de la concentración del ingrediente activo es de 3 g/l, independientemente del tipo de instrumental empleado en su producción. Se realizan 10 observaciones de una muestra de un antibiótico con cada uno de los equipos disponibles, y se obtienen los siguientes datos:

- Equipo 1: 57,9 − 66,2 − 65,4 − 65,4 − 65,2 − 62,6 − 67,6 − 63,7 − 67,2 − 71,0
- Equipo 2: 65,4 − 70,7 − 70,1 − 69,3 − 63,8 − 68,6 − 68,6 − 69,4 − 65,3 − 68,8

Se pide:

- a) Suponiendo normalidad de las distribuciones, encontrar un intervalo de confianza del 95 % para la diferencia entre los valores medios de las concentraciones logradas por cada uno de los equipos.
- b) Considerar ahora la dispersión poblacional desconocida pero igual para ambos equipos.

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

Muestras:
- Equipo 1: $\bar x_1 = 65{,}22$, $s_1 = 3{,}44$
- Equipo 2: $\bar x_2 = 68{,}00$, $s_2 = 2{,}32$

$\bar x_2 - \bar x_1 = 2{,}78$.

a) σ = 3 conocido: $d = 1{,}96\cdot3\sqrt{\frac1{10} + \frac1{10}} = 2{,}63$ ⇒ [0,15; 5,41].

b) $s_p = \sqrt{\frac{9s_1^2 + 9s_2^2}{18}} = 2{,}936$; $t_{18;\,0{,}975} = 2{,}101$.

$d = 2{,}101\cdot2{,}936\sqrt{0{,}2} = 2{,}76$ ⇒ [0,02; 5,54].

En ambos casos el intervalo no contiene al 0 ⇒ el equipo 2 da concentraciones medias mayores.

</details>

**Respuesta:**

- a) $IC_{95}(\mu_2 - \mu_1) = [0{,}15;\ 5{,}41]$
- b) $IC_{95}(\mu_2 - \mu_1) = [0{,}02;\ 5{,}53]$

</details>

---

### 31) Vuelos demorados *(opcional)*

Se desea estimar el porcentaje de vuelos demorados en Aeroparque. Las líneas de interés para el estudio son Golazo y LAP. En un determinado mes se seleccionan al azar 100 vuelos de la primera y 121 de la segunda. Resultaron 20 demoras en Golazo y 28 demoras en LAP. Se construyó un intervalo de confianza (LAP − Golazo) para la diferencia de proporciones, siendo su límite superior 0,1605. Hallar el nivel de confianza utilizado.

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

$\hat p_L = 28/121 = 0{,}2314$ y $\hat p_G = 20/100 = 0{,}2$ ⇒ $\hat p_L - \hat p_G = 0{,}0314$.

Error estándar: $\sqrt{\frac{0{,}2314\cdot0{,}7686}{121} + \frac{0{,}2\cdot0{,}8}{100}} = 0{,}0554$.

Límite superior: $0{,}0314 + z\cdot0{,}0554 = 0{,}1605 \Rightarrow z = 2{,}33 = z_{0{,}99}$.

Entonces 1 − α/2 = 0,99 ⇒ 1 − α = 0,98.

</details>

**Respuesta:** 0,98

</details>

---

[← Volver al menú principal](../README.md)
