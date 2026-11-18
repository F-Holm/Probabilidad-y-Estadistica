# Unidad 6 — Ejercicios resueltos

Ejercicios de la **Práctica 6 de la Guía de TP** (Regresión y Correlación).

Cada ejercicio tiene un botón **Solución**. Al abrirlo aparece la respuesta y, arriba de ella, un segundo botón **Solución paso a paso** con el desarrollo completo.

Notación: $S_{xx} = \sum(x_i - \bar x)^2$, $S_{yy} = \sum(y_i - \bar y)^2$, $S_{xy} = \sum(x_i - \bar x)(y_i - \bar y)$. Recta estimada: $\hat y = b_0 + b_1x$, con $b_1 = S_{xy}/S_{xx}$ y $b_0 = \bar y - b_1\bar x$. $s^2 = SC_{res}/(n-2)$.

> **Referencias:** (T) = ejercicio teórico · (\*) = requiere aplicación informática o de celular. Los gráficos y salidas de computadora están en la guía; acá se reconstruyen los valores con los datos.

---

### 1) Cobre y níquel

Se realiza un estudio para establecer una ecuación mediante la cual se pueda utilizar la concentración de cobre de una pieza (X) para predecir el porcentaje de níquel de la misma (Y). Se extrajeron al azar los siguientes datos de 14 piezas fabricadas en una misma planta durante el mes pasado:

| X | 1,4 | 7,5 | 8,5 | 9 | 9 | 11 | 13 | 14 | 14,5 | 16 | 17 | 18 | 20 | 23 |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| **Y** | 30 | 25 | 31,5 | 27,5 | 39,5 | 38 | 43 | 49 | 55 | 48,5 | 51 | 64,5 | 63 | 68 |

Sabiendo que X e Y tienen distribución Normal:

- a) Graficar sobre el diagrama de dispersión la recta de regresión y señalar un par ordenado observado y un residuo.
- b) Verificar gráfica y analíticamente que la recta de regresión pasa por el punto $(\bar x, \bar y)$.
- c) Indicar, a partir de la salida de computadora, los parámetros estimados para el modelo y el porcentaje de variabilidad de Y que logra explicar X a través de la recta de regresión.

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

Cantidades básicas: n = 14, $\bar x = 12{,}99$, $\bar y = 45{,}25$, $S_{xx} = 423{,}31$, $S_{yy} = 2593{,}38$, $S_{xy} = 957{,}78$.

$b_1 = \frac{957{,}78}{423{,}31} = 2{,}263$ y $b_0 = 45{,}25 - 2{,}263\cdot12{,}99 = 15{,}85$ ⇒ $\hat y = 15{,}85 + 2{,}263x$.

a) Por ejemplo, el par observado (14; 49) tiene $\hat y = 15{,}85 + 2{,}263\cdot14 = 47{,}53$. Su residuo es $e = y - \hat y = 49 - 47{,}53 = 1{,}47$: el segmento vertical entre el punto y la recta.

b) $\hat y(\bar x) = 15{,}85 + 2{,}263\cdot12{,}99 = 45{,}25 = \bar y$. Siempre se cumple, porque $b_0 = \bar y - b_1\bar x$.

c)
- $SC_{res} = 426{,}32$ ⇒ $\hat\sigma^2 = s^2 = \frac{426{,}32}{12} = 35{,}53$.
- $R^2 = \frac{S_{xy}^2}{S_{xx}S_{yy}} = 0{,}8356$: el 84 % de la variabilidad del níquel queda explicada por el cobre a través de la recta.

</details>

**Respuesta:**

- a) Gráfico (por ejemplo, el punto (14; 49) y su residuo 1,47)
- b) $\bar x = 13$, $\bar y = 45{,}25$, $\hat y_i = 15{,}85 + 2{,}263x_i$; se verifica que $\bar y = 15{,}85 + 2{,}263\bar x$
- c) $\hat\alpha = 15{,}85$, $\hat\beta = 2{,}26$, $\hat\sigma^2 = 35{,}53$, $R^2 = 0{,}84$

</details>

---

### 2) Vapor y temperatura

En una planta química se sospecha que la cantidad de vapor utilizada por mes (Y, en miles de libras) está relacionada con la temperatura ambiente promedio del mismo mes (X, en °F). La siguiente tabla presenta, para todo un año, el uso de vapor y la temperatura del mes correspondiente:

| X | 21 | 24 | 32 | 47 | 50 | 59 | 68 | 74 | 62 | 50 | 41 | 30 |
|---|---|---|---|---|---|---|---|---|---|---|---|---|
| **Y** | 240 | 220 | 320 | 325 | 280 | 230 | 200 | 275 | 270 | 250 | 200 | 270 |

Shapiro-Wilks (modificado):

| Variable | n | Media | D.E. | W\* | p (Unilateral D) |
|---|---|---|---|---|---|
| X | 12 | 46,50 | 17,34 | 0,93 | 0,5413 |
| Y | 12 | 256,67 | 41,25 | 0,92 | 0,4005 |

Se pide:

- a) Indicar las hipótesis a testear para responder a la sospecha de la planta química, indicando el estadístico de contraste y su distribución.
- b) Indicar si se satisfacen los supuestos para realizar esta prueba (para el test de Shapiro-Wilks utilizar un nivel del 0,10) y, en caso afirmativo, realizarla y concluir en el contexto del problema con un nivel del 0,05.

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

a) Test de correlación lineal:
- H₀: ρ = 0 vs. H₁: ρ ≠ 0.
- Estadístico: $T = \frac{r\sqrt{n-2}}{\sqrt{1 - r^2}} \sim t_{n-2}$ bajo H₀.

b) Supuestos: Shapiro-Wilks da p = 0,54 y p = 0,40, ambos > 0,10 ⇒ no se rechaza la normalidad. Se puede suponer normal conjunta.

$S_{xx} = 3309$, $S_{yy} = 18716{,}67$, $S_{xy} = -325$ ⇒ $r = \frac{-325}{\sqrt{3309\cdot18716{,}67}} = -0{,}041$.

$t_{obs} = \frac{-0{,}041\sqrt{10}}{\sqrt{1 - 0{,}0017}} = -0{,}13$.

RC = {|T| > $t_{10;\,0{,}975}$ = 2,228}. Como |−0,13| < 2,228 ⇒ no se rechaza H₀ (p = 0,90).

</details>

**Respuesta:**

- a) H₀: ρ = 0 vs. H₁: ρ ≠ 0; $T = \dfrac{r\sqrt{n-2}}{\sqrt{1 - r^2}} \sim t_{n-2}$
- b) Sí se cumplen los supuestos (normalidad). $t_{obs}$ = −0,13: no se rechaza H₀ al 5 %; no hay evidencia de asociación lineal entre la temperatura y el vapor

</details>

---

### 3) Sal y tensión arterial

Se quiere estudiar la asociación lineal entre el consumo diario de sal y la tensión arterial. A una serie de voluntarios se les interroga sobre la dosis de sal en su dieta y se mide simultáneamente su tensión arterial. Los datos están en la tabla:

| Consumo de sal (mg) | 1,8 | 2,2 | 3,5 | 4,0 | 4,3 | 5 |
|---|---|---|---|---|---|---|
| **Tensión arterial (mm de Hg)** | 100 | 98 | 110 | 110 | 112 | 120 |

Si se sabe que ambas variables tienen distribución Normal conjunta:

- a) De la observación del diagrama de dispersión, ¿le parece razonable testear la hipótesis de asociación lineal? Justificar.
- b) ¿Qué test correspondería aplicar en caso afirmativo?
- c) Establecer las hipótesis, indicar el estadístico de contraste, la región crítica y la decisión al 5 %.

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

a) Sí: los puntos siguen aproximadamente una recta creciente.

b) El test de correlación lineal (test para ρ).

c) H₀: ρ = 0 vs. H₁: ρ ≠ 0.

$S_{xx} = 7{,}713$, $S_{yy} = 331{,}33$, $S_{xy} = 48{,}87$ ⇒ $r = 0{,}9666$ ($R^2 = 0{,}934$).

$t_{obs} = \frac{0{,}9666\sqrt4}{\sqrt{1 - 0{,}934}} = 7{,}54$.

RC = {|T| > $t_{4;\,0{,}975}$ = 2,776}. Como 7,54 ∈ RC ⇒ se rechaza H₀ (p = 0,0017).

</details>

**Respuesta:**

- a) Sí
- b) Test de correlación lineal
- c) H₀: ρ = 0 vs. H₁: ρ ≠ 0; $T_{obs}$ = 7,54 > $t_{crít}$ = 2,77 ⇒ se rechaza H₀: hay asociación lineal entre sal y tensión

</details>

---

### 4) Agua nieve y afluencia del río Salado

Los siguientes datos proporcionan información acerca del contenido de agua nieve (X) en cm y la afluencia de abril a junio en pulgadas (Y) en la cuenca del río Salado. Se sabe que ambas variables tienen distribución Normal.

| X | 23,1 | 32,8 | 31,8 | 32 | 30,4 | 24 | 39,5 | 24,2 |
|---|---|---|---|---|---|---|---|---|
| **Y** | 10,5 | 16,7 | 18,2 | 17 | 16,3 | 10,5 | 23,1 | 12,4 |

Shapiro-Wilks (modificado):

| Variable | n | Media | D.E. | W\* | p-valor |
|---|---|---|---|---|---|
| RESIDUO | 8 | 0,00 | 0,78 | 0,94 | 0,6941 |

Se pide:

- a) Ajustar el modelo de regresión lineal simple para estimar Y en función de X, basándose en los datos disponibles, e interpretar los coeficientes obtenidos.
- b) ¿Se satisface el supuesto de normalidad de los errores para este modelo? Utilizar un 10 % de significación. Justificar.
- c) ¿Le parece que se satisface el supuesto de homocedasticidad de los errores para este modelo? (Observe en el gráfico si se presenta alguna estructura, es decir, si al aumentar el valor de la variable predictora aumenta o disminuye la variabilidad de los residuos, o bien si se detectan residuos muy altos en valor absoluto.)
- d) En caso de haber respondido afirmativamente a las últimas dos preguntas, testear la significación del modelo con nivel 0,05.

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

a) $\bar x = 29{,}725$, $\bar y = 15{,}5875$, $S_{xx} = 222{,}135$, $S_{xy} = 166{,}41$.

$b_1 = 0{,}749$ y $b_0 = 15{,}5875 - 0{,}749\cdot29{,}725 = -6{,}68$ ⇒ $\hat y = -6{,}68 + 0{,}749x$.

b) Shapiro-Wilks sobre los residuos: p = 0,694 > 0,10 ⇒ no se rechaza la normalidad.

c) En el gráfico de residuos vs. x no hay forma de embudo ni residuos muy grandes ⇒ se acepta la homocedasticidad.

d) H₀: β₁ = 0 vs. H₁: β₁ ≠ 0.

$SC_{res} = 4{,}26$ ⇒ $s = \sqrt{4{,}26/6} = 0{,}843$; $s_{b_1} = \frac{s}{\sqrt{S_{xx}}} = 0{,}0565$.

$t_{obs} = \frac{0{,}749}{0{,}0565} = 13{,}25 > t_{6;\,0{,}975} = 2{,}447$ ⇒ se rechaza H₀.

</details>

**Respuesta:**

- a) $\hat y_i = -6{,}68 + 0{,}749x_i$. $\hat\alpha = -6{,}68$ es el valor medio estimado de Y cuando x = 0 (fuera del rango observado). $\hat\beta = 0{,}749$ es el aumento medio estimado de Y cuando X aumenta en una unidad
- b) Sí, por el p valor del test de Shapiro-Wilks (0,694 > 0,10)
- c) Sí, no se aprecia en el gráfico estructura creciente ni decreciente de la variabilidad
- d) $T_{obs}$ = 13,24 > $T_{crít}$ = 2,4469 ⇒ se rechaza H₀: la regresión es estadísticamente significativa

</details>

---

### 5) Demanda máxima y uso de energía

Una compañía productora de energía eléctrica está interesada en desarrollar un modelo que relacione la demanda máxima por hora (D, en kW) con el uso de la energía total al mes (U, en kWh). Las variables se distribuyen en forma Normal bivariada. La siguiente tabla muestra los datos obtenidos de una muestra de 11 clientes elegidos al azar entre los de esta compañía:

| U | 679 | 292 | 1012 | 493 | 582 | 1156 | 997 | 2189 | 1087 | 2077 | 2078 |
|---|---|---|---|---|---|---|---|---|---|---|---|
| **D** | 0,79 | 0,44 | 0,56 | 0,79 | 2,7 | 3,64 | 4,73 | 9,5 | 5,34 | 6,88 | 6,85 |

Se pide:

- a) Ajustar el modelo de regresión lineal simple a los datos e indicar si el ajuste es adecuado con un nivel de significación del 1 %.
- b) Encontrar un intervalo de predicción para $u_0$ = 900 kWh con un nivel del 99 %. Interpretarlo e indicar la diferencia con un intervalo de confianza para la media con el mismo valor de $u_0$.
- c) ¿Puede estimarse a partir de estos datos el valor esperado de D para U = 156?

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

a) $\bar u = 1149{,}27$, $\bar d = 3{,}838$, $S_{uu} = 4.558.764$, $S_{ud} = 18.717{,}98$.

$b_1 = 0{,}00411$ y $b_0 = -0{,}881$ ⇒ $\hat d = -0{,}881 + 0{,}0041u$.

$SC_{res} = 18{,}79$ ⇒ $s = 1{,}445$; $s_{b_1} = \frac{1{,}445}{\sqrt{4558764}} = 0{,}000677$.

Test H₀: β₁ = 0 vs. H₁: β₁ ≠ 0: $t_{obs} = 6{,}07 > t_{9;\,0{,}995} = 3{,}25$ ⇒ la regresión es significativa al 1 % ($R^2 = 0{,}80$).

b) $\hat d(900) = 2{,}815$. Con $t_{9;\,0{,}995} = 3{,}25$:

$IP = \hat d \pm t\,s\sqrt{1 + \frac1n + \frac{(u_0 - \bar u)^2}{S_{uu}}} = 2{,}815 \pm 4{,}93 = [-2{,}12;\ 7{,}75]$.

Es el rango donde se espera, con 99 % de confianza, la demanda de **un** cliente con u = 900.

El IC para la **media** usa $\sqrt{\frac1n + \frac{(u_0 - \bar u)^2}{S_{uu}}}$ (sin el "1 +"): da [1,30; 4,33], siempre más angosto.

c) No: u = 156 está fuera del rango observado (292 a 2189). Sería **extrapolar**.

</details>

**Respuesta:**

- a) $\hat d_i = -0{,}881 + 0{,}0041u_i$; H₀: β = 0 vs. H₁: β ≠ 0; $T_{obs}$ = 6,06 > $T_{crít}$ = 3,24 ⇒ la regresión es significativa al 1 %
- b) $I_{pred} = [-2{,}1;\ 7{,}7]$; siempre tiene mayor longitud que el intervalo de confianza para la media ([1,30; 4,33])
- c) No, pues 156 está alejado del recorrido de U

</details>

---

### 6) Ruido y presión sanguínea

Se realizó un estudio para estimar los efectos producidos en las personas debidos a la exposición al ruido. Ocho personas participaron en este estudio. Se registraron los aumentos en la presión sanguínea del individuo y el nivel de presión sonora, distribuido normalmente, al que se sometieron. Los datos se expresan en la tabla:

| X: Nivel de presión sonora (dB) | 60 | 63 | 70 | 80 | 85 | 90 | 94 | 100 |
|---|---|---|---|---|---|---|---|---|
| **Y: Aumento de presión sanguínea (Hg)** | 1 | 0 | 4 | 3 | 5 | 8 | 7 | 6 |

$\sum x_i = 642$, $\sum y_i = 34$, $\sum x_i^2 = 53030$, $\sum y_i^2 = 200$, $\sum x_iy_i = 2983$.

- a) Hallar la recta de regresión estimada.
- b) Hallar el coeficiente de determinación e interpretarlo.

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

Con las fórmulas de cálculo:
- $S_{xx} = 53030 - \frac{642^2}8 = 1509{,}5$
- $S_{yy} = 200 - \frac{34^2}8 = 55{,}5$
- $S_{xy} = 2983 - \frac{642\cdot34}8 = 254{,}5$

a) $b_1 = \frac{254{,}5}{1509{,}5} = 0{,}1686$ y $b_0 = 4{,}25 - 0{,}1686\cdot80{,}25 = -9{,}28$.

b) $R^2 = \frac{S_{xy}^2}{S_{xx}S_{yy}} = \frac{254{,}5^2}{1509{,}5\cdot55{,}5} = 0{,}7731$.

</details>

**Respuesta:**

- a) $\hat y_i = -9{,}28 + 0{,}1686x_i$
- b) $R^2 = 0{,}7731$: el 77,31 % de la variabilidad de Y queda explicado por la variabilidad de X a través de la recta de regresión

</details>

---

### 7) Propagación de un virus

Una empresa de servicios informáticos está preocupada por la proliferación de cierto tipo de virus. La siguiente tabla registra el número de días que han transcurrido desde que se ha detectado un nuevo virus (X) y el número de ordenadores (Y) que han requerido los servicios de esta empresa a causa del virus.

| $x_i$ | 1 | 2 | 4 | 5 | 8 | 10 | 11 | 14 | 16 | 20 |
|---|---|---|---|---|---|---|---|---|---|---|
| $y_i$ | 254 | 1,5 | 2,105 | 5,05 | 16,2 | 45,32 | 58,57 | 375,8 | 1525640 | 2577000 |
| $\ln(y_i)$ | 5,54 | 0,41 | 0,74 | 1,62 | 2,79 | 3,81 | 4,07 | 5,93 | 14,24 | 14,76 |

Se pide:

- a) A partir de los dos diagramas de dispersión presentados (Y vs. X y ln(Y) vs. X), decidir cuál es la regresión lineal más adecuada y estimar los coeficientes correspondientes.
- b) Estimar puntualmente el número de consultas que tendrá la empresa a los 15 días de la detección del virus.

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

a) Y crece en forma **exponencial** (pasa de cientos a millones), así que la relación con X no es lineal. En cambio ln(Y) vs. X se parece mucho más a una recta.

Se ajusta $\ln y = b_0 + b_1x$:
- $\bar x = 9{,}1$, $\overline{\ln y} = 5{,}391$, $S_{xx} = 354{,}9$, $S_{x,\ln y} = 238{,}09$.
- $b_1 = 0{,}6709$ y $b_0 = -0{,}714$ ⇒ $\widehat{\ln y} = -0{,}714 + 0{,}671x$ ($R^2 = 0{,}67$).

Equivale al modelo $\hat y = e^{-0{,}714}e^{0{,}671x}$.

b) $\widehat{\ln y}(15) = -0{,}714 + 0{,}6709\cdot15 = 9{,}35$ ⇒ $\hat y = e^{9{,}35} \approx 11488$.

</details>

**Respuesta:**

- a) La de ln(Y) vs. X: $\widehat{\ln y} = -0{,}714 + 0{,}671x$
- b) $\hat y(15) = 11488{,}33$

</details>

---

### 8) Estimadores de mínimos cuadrados (T)

- a) (T) Deducir los estimadores de mínimos cuadrados de los coeficientes del modelo de regresión lineal para el caso general.
- b) (T) Existen aplicaciones importantes en las que, debido a restricciones científicas conocidas, la recta de regresión debe pasar por el origen de coordenadas, es decir, el (0, 0) debe pertenecer a la recta. Por ello, en el modelo sólo se requiere estimar un parámetro (modelo de regresión al origen). Demostrar que el estimador de mínimos cuadrados para la pendiente es $b_1 = \dfrac{\sum x_iy_i}{\sum x_i^2}$.

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

a) Se minimiza $g(b_0, b_1) = \sum(y_i - b_0 - b_1x_i)^2$. Derivando e igualando a 0 se obtienen las **ecuaciones normales**:
- $\frac{\partial g}{\partial b_0} = -2\sum(y_i - b_0 - b_1x_i) = 0 \Rightarrow \sum y_i = nb_0 + b_1\sum x_i$
- $\frac{\partial g}{\partial b_1} = -2\sum x_i(y_i - b_0 - b_1x_i) = 0 \Rightarrow \sum x_iy_i = b_0\sum x_i + b_1\sum x_i^2$

De la primera, $b_0 = \bar y - b_1\bar x$. Reemplazando en la segunda:

$b_1 = \frac{n\sum x_iy_i - \sum x_i\sum y_i}{n\sum x_i^2 - (\sum x_i)^2} = \frac{S_{xy}}{S_{xx}}$.

Además, si los errores son normales, el logaritmo de la verosimilitud es $-\frac n2\ln(2\pi) - n\ln\sigma - \frac1{2\sigma^2}\sum(Y_i - a - bx_i)^2$. Maximizarlo equivale a minimizar la suma de cuadrados ⇒ los estimadores de MV y de MC coinciden.

b) Con $g(b_1) = \sum(y_i - b_1x_i)^2$:

$g'(b_1) = -2\sum x_i(y_i - b_1x_i) = 0 \Rightarrow b_1 = \frac{\sum x_iy_i}{\sum x_i^2}$.

Es un mínimo porque $g'' = 2\sum x_i^2 > 0$.

</details>

**Respuesta:**

- a) $b_1 = \dfrac{n\sum x_iy_i - \sum x_i\sum y_i}{n\sum x_i^2 - (\sum x_i)^2} = \dfrac{S_{xy}}{S_{xx}}$, $b_0 = \bar y - b_1\bar x$ (coinciden con los de máxima verosimilitud)
- b) $b_1 = \dfrac{\sum x_iy_i}{\sum x_i^2}$

</details>

---

### 9) Descomposición de la suma de cuadrados (T)

(T) Demostrar que la suma de cuadrados totales es igual a la suma de cuadrados residuales más la suma de cuadrados de la regresión; es decir:

$$\sum_{i=1}^n (Y_i - \bar Y)^2 = \sum_{i=1}^n (Y_i - \hat Y_i)^2 + \sum_{i=1}^n (\hat Y_i - \bar Y)^2$$

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

Se suma y resta $\hat Y_i$:

$\sum(Y_i - \bar Y)^2 = \sum\left[(Y_i - \hat Y_i) + (\hat Y_i - \bar Y)\right]^2 = \sum(Y_i - \hat Y_i)^2 + \sum(\hat Y_i - \bar Y)^2 + 2\sum e_i(\hat Y_i - \bar Y)$.

Falta ver que el doble producto es 0. Como $\hat Y_i = b_0 + b_1x_i$:

$\sum e_i(\hat Y_i - \bar Y) = (b_0 - \bar Y)\sum e_i + b_1\sum e_ix_i$.

Por las ecuaciones normales, $\sum e_i = 0$ y $\sum e_ix_i = 0$ ⇒ el doble producto es 0.

</details>

**Respuesta:** $SC_{Total} = SC_{res} + SC_{regr}$, porque $\sum e_i(\hat Y_i - \bar Y) = 0$ por las ecuaciones normales.

</details>

---

### 10) ¿Qué resultado puede ser cierto?

Con respecto a los resultados de un análisis de regresión lineal simple, ¿cuál de las afirmaciones siguientes puede ser cierta? (Justificar adecuadamente.)

- $SC_{Total} < SC_{error} + SC_{regres}$
- $R^2 = -0{,}65$
- $s_b = -1{,}25$
- $t_{obs} = -2{,}45$

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

- $SC_{Total} = SC_{error} + SC_{regres}$ siempre (ejercicio 9) ⇒ falsa.
- $R^2 = r^2 \in [0; 1]$ ⇒ no puede ser negativo.
- $s_b$ es un desvío estándar ⇒ siempre ≥ 0.
- $t_{obs} = b_1/s_b$ tiene el signo de $b_1$: es negativo si la pendiente es negativa ⇒ **puede ser cierta**.

</details>

**Respuesta:** La última ($t_{obs}$ = −2,45).

</details>

---

### 11) Líquenes y nitratos (\*)

En varios estudios se ha demostrado que los líquenes, organismos compuestos por un alga y un hongo, son buenos indicadores biológicos de la contaminación del aire. Los siguientes datos corresponden a las variables X (depósito de nitratos, en g/cm²) e Y (nitrógeno en el liquen, en % de peso seco):

| X | 0,05 | 0,1 | 0,11 | 0,12 | 0,31 | 0,37 | 0,42 | 0,58 | 0,68 | 0,68 | 0,73 | 0,85 | 0,92 |
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
| **Y** | 0,48 | 0,55 | 0,48 | 0,5 | 0,58 | 0,52 | 1,02 | 0,86 | 0,86 | 1 | 0,88 | 1,04 | 1,7 |

- a) Indicar el modelo estimado para estos datos por mínimos cuadrados.
- b) Completar los p valores de las salidas e indicar la significación del modelo.
- c) Construir un intervalo de confianza de nivel 95 % para el valor esperado de nitrógeno en el liquen para un depósito de nitrato de 0,4 g/cm².

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

a) $\bar x = 0{,}4554$, $\bar y = 0{,}8054$, $S_{xx} = 1{,}1155$, $S_{xy} = 1{,}0785$.

$b_1 = 0{,}967$ y $b_0 = 0{,}365$ ⇒ $\hat y = 0{,}37 + 0{,}97x$.

b) $SC_{res} = 0{,}4106$ ⇒ $s = \sqrt{0{,}4106/11} = 0{,}193$. Con 11 g.l.:
- Ordenada: $s_{b_0} = 0{,}099$, $t = 3{,}69$ ⇒ p = 0,0036.
- Pendiente: $s_{b_1} = 0{,}183$, $t = 5{,}29$ ⇒ p = 0,0003.

El p valor de la pendiente es < 0,05 ⇒ el modelo es significativo ($R^2 = 0{,}72$).

c) $\hat y(0{,}4) = 0{,}752$; $t_{11;\,0{,}975} = 2{,}201$.

$IC = 0{,}752 \pm 2{,}201\cdot0{,}193\sqrt{\frac1{13} + \frac{(0{,}4 - 0{,}4554)^2}{1{,}1155}} = 0{,}752 \pm 0{,}120 = [0{,}632;\ 0{,}872]$.

(La guía informa [0,536; 0,98]. Con los datos de la tabla, la fórmula del IC para la media da el intervalo de arriba.)

</details>

**Respuesta:**

- a) $\hat y_i = 0{,}37 + 0{,}97x_i$
- b) p-valor₁ (ordenada) = 0,0036; p-valor₂ (pendiente) = 0,0003 ⇒ el modelo es significativo
- c) IC ≈ [0,632; 0,872] (la guía da [0,536; 0,98])

</details>

---

### 12) Superficie y peso de piezas metálicas

En la siguiente tabla se han registrado las superficies y los pesos de ciertas piezas metálicas producidas por una máquina.

| Superficie de la pieza | 44,09 | 36,67 | 51,72 | 36,04 | 38,97 | 61,4 | 42,06 | 53,33 | 50,01 |
|---|---|---|---|---|---|---|---|---|---|
| **Peso de la pieza** | 47,6 | 45 | 43,04 | 56,8 | 63,11 | 68,7 | 41,8 | 34,3 | 31,2 |

- a) Graficar el diagrama de dispersión aproximado de Peso vs. Superficie. ¿Hay alguna observación que le llame la atención?
- b) Estimar los coeficientes del modelo de regresión lineal utilizando toda la información disponible.
- c) Calcular los residuos. ¿Hay alguno que le parezca especial?
- d) Eliminar la sexta observación y repetir los dos ítems anteriores. Comparar los resultados.

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

a) La 6.ª observación (61,4; 68,7) se aleja de la tendencia decreciente del resto: tiene la mayor superficie y el mayor peso. Es un punto atípico e influyente.

b) Con los 9 datos: $b_1 = \frac{-18{,}06}{594{,}52} = -0{,}030$ y $b_0 = 49{,}35$ ⇒ $\hat y = 49{,}35 - 0{,}03x$ ($R^2 \approx 0$).

c) Residuos: −0,41; −3,23; −4,74; 8,55; 14,95; **21,22**; −6,27; −13,43; −16,63. El 6.º es el más grande.

d) Sin la 6.ª observación: $b_1 = -1{,}146$ y $b_0 = 95{,}90$ ($R^2 = 0{,}55$).

Residuos: 2,22; −8,88; 6,40; 2,20; 11,86; −5,91; −0,49; −7,40.

Un solo punto cambiaba por completo la pendiente.

</details>

**Respuesta:**

- a) La sexta observación
- b) $\hat\alpha = 49{,}35$, $\hat\beta = -0{,}03$
- c) El sexto residuo (21,22)
- d) $\hat y_i = 95{,}9 - 1{,}146x_i$: cambian fundamentalmente los coeficientes

</details>

---

[← Volver al menú principal](../README.md)
