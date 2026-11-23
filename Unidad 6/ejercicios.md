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

💡 **Qué es la regresión lineal.** Hay **dos variables por pieza**: cobre (X) y níquel (Y). Se quiere una **recta** que, dado el cobre, prediga el níquel:

```math
\hat y = b_0 + b_1x
```

📄 H2.
- **$b_1$ (pendiente):** cuánto sube Y, en promedio, por cada unidad que sube X.
- **$b_0$ (ordenada al origen):** el valor de la recta en x = 0.

Los puntos nunca caen todos sobre una recta. Se elige la recta que pasa **lo más cerca posible** de todos: la que hace mínima la suma de las distancias verticales al cuadrado (**mínimos cuadrados**).

💡 **Las cuentas base** (📄 H2): tres sumas que miden cuánto varía X, cuánto varía Y y cuánto varían juntas.

```math
S_{xx} = \sum x_i^2 - \frac{(\sum x_i)^2}{n} \qquad S_{yy} = \sum y_i^2 - \frac{(\sum y_i)^2}{n} \qquad S_{xy} = \sum x_iy_i - \frac{\sum x_i\sum y_i}{n}
```

Con ellas (📄 H2): $b_1 = \frac{S_{xy}}{S_{xx}}$ y $b_0 = \bar y - b_1\bar x$.

**Con las apps:** Calculadora de estadística → **Regresión lineal**, cargando los 14 pares, da $b_0$ y $b_1$. Para los S: la **descriptiva** da la varianza de X, y $S_{xx} = (n-1)\cdot s_x^2$ (❌). Lo mismo para Y.

**Cuentas** (n = 14): $\bar x = 12{,}99$, $\bar y = 45{,}25$, $S_{xx} = 423{,}31$, $S_{yy} = 2593{,}38$, $S_{xy} = 957{,}78$.

```math
b_1 = \frac{957{,}78}{423{,}31} = 2{,}263 \qquad b_0 = 45{,}25 - 2{,}263\cdot12{,}99 = 15{,}85 \;\Rightarrow\; \hat y = 15{,}85 + 2{,}263x
```

Cada unidad más de cobre suma, en promedio, 2,26 % de níquel.

**a)** 💡 **Residuo:** la diferencia entre lo observado y lo que predice la recta, $e = y - \hat y$. En el gráfico es el segmento **vertical** entre el punto y la recta.

Por ejemplo, el punto (14; 49): la recta predice $\hat y = 15{,}85 + 2{,}263\cdot14 = 47{,}53$, así que el residuo es $49 - 47{,}53 = 1{,}47$. El punto está 1,47 por encima de la recta.

**b)** Se reemplaza $x = \bar x$ en la recta:

```math
\hat y(\bar x) = 15{,}85 + 2{,}263\cdot12{,}99 = 45{,}25 = \bar y
```

Siempre pasa: $b_0 = \bar y - b_1\bar x$ se construye justamente para que $\bar y = b_0 + b_1\bar x$. La recta siempre pasa por el "centro de gravedad" de los datos.

**c)** Los parámetros estimados son $\hat\alpha = b_0 = 15{,}85$ y $\hat\beta = b_1 = 2{,}26$.
- 💡 **Varianza del error** (📄 H2, $`\hat\sigma^2 = \frac{SC_{res}}{n-2}`$): cuánto se apartan los puntos de la recta. $SC_{res} = S_{yy} - \frac{S_{xy}^2}{S_{xx}} = 426{,}32$, así que $\hat\sigma^2 = \frac{426{,}32}{12} = 35{,}53$.
- 💡 **Coeficiente de determinación** (📄 H2, $`R^2 = \frac{SC_{exp}}{SC_{total}} = r^2`$): la fracción de la variabilidad de Y que **explica** la recta.

  ```math
  R^2 = \frac{S_{xy}^2}{S_{xx}S_{yy}} = 0{,}8356
  ```

  El 84 % de la variabilidad del níquel queda explicada por el cobre a través de la recta.

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

💡 **Coeficiente de correlación r** (📄 H2, $`r = \frac{S_{xy}}{\sqrt{S_{xx}S_{yy}}}`$): mide qué tan bien se alinean los puntos en una recta. Va de −1 a 1:
- cerca de 1: recta creciente;
- cerca de −1: recta decreciente;
- cerca de 0: no hay relación lineal.

r se calcula con la **muestra**. ρ es la correlación de **toda la población**.

**a)** La sospecha es que vapor y temperatura **están relacionados**. 💡 En un test, lo que se quiere demostrar va en H₁, y H₀ es "no hay relación":

```math
H_0: \rho = 0 \qquad H_1: \rho \neq 0
```

**Estadístico** (📄 H2, $`\sqrt{n-2}\frac{r}{\sqrt{1-r^2}} = t_{n-2}`$): si H₀ es cierta, es una t de Student con n − 2 grados de libertad. Se pierden 2 porque se estimaron b₀ y b₁.

**b) Supuestos.** El test pide normalidad. 💡 **Shapiro-Wilks** es un test cuya H₀ es "los datos son normales". Sus valores p (0,54 y 0,40) son mayores que 0,10, así que **no se rechaza** la normalidad: se puede hacer el test.

**Cuentas** (📄 H2, con las fórmulas de S): $S_{xx} = 3309$, $S_{yy} = 18\,716{,}67$ y $S_{xy} = -325$.

```math
r = \frac{-325}{\sqrt{3309\cdot18\,716{,}67}} = -0{,}041 \qquad t_{obs} = \sqrt{10}\cdot\frac{-0{,}041}{\sqrt{1 - 0{,}0017}} = -0{,}13
```

**Región crítica bilateral** (H₁ es ≠), con α = 0,05:
```
X~t(ν)   ν=10   P(X<x)=0.975   → x=2.22814
```
|−0,13| < 2,228 (p ≈ 0,90): **no se rechaza H₀**. No hay evidencia de relación lineal entre la temperatura y el uso de vapor: la sospecha no se confirma.

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

**a)** 💡 Un **diagrama de dispersión** es el gráfico de los pares (x, y) como puntos. Si los puntos forman aproximadamente una **línea recta**, tiene sentido estudiar una asociación **lineal**. Acá sí: más sal, más tensión, en forma aproximadamente recta y creciente.

**b)** 💡 El **test de correlación lineal**: decide si la correlación de la población, ρ, es distinta de 0. Se usa el **coeficiente de correlación r**, que mide qué tan alineados están los puntos (de −1 a 1; 📄 H2, $`r = \frac{S_{xy}}{\sqrt{S_{xx}S_{yy}}}`$).

**c)** 💡 **Hipótesis.** Lo que se quiere demostrar (que hay asociación) va en H₁:

```math
H_0: \rho = 0 \qquad H_1: \rho \neq 0
```

**Cuentas** (📄 H2, fórmulas de los S): $S_{xx} = 7{,}713$, $S_{yy} = 331{,}33$ y $S_{xy} = 48{,}87$.

```math
r = \frac{48{,}87}{\sqrt{7{,}713\cdot331{,}33}} = 0{,}9666 \qquad R^2 = r^2 = 0{,}934
```

**Estadístico** (📄 H2): $T = \sqrt{n-2}\frac{r}{\sqrt{1-r^2}} \sim t_{n-2}$ si H₀ es cierta.

```math
t_{obs} = \sqrt4\cdot\frac{0{,}9666}{\sqrt{1 - 0{,}934}} = 7{,}54
```

**Región crítica** (bilateral, 5 %):
```
X~t(ν)   ν=4   P(X<x)=0.975   → x=2.77645
X~t(ν)   ν=4   P(X>x)   x=7.54   → 0.00083   → p = 2·0.00083 ≈ 0.0017
```
7,54 > 2,776: **se rechaza H₀**. Hay evidencia de asociación lineal entre el consumo de sal y la tensión arterial.

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

**a)** 💡 **Recta de regresión** $\hat y = b_0 + b_1x$: la recta que pasa más cerca de los puntos (mínimos cuadrados). Se calcula con (📄 H2):

```math
b_1 = \frac{S_{xy}}{S_{xx}} \qquad b_0 = \bar y - b_1\bar x
```

con $S_{xx} = \sum x^2 - \frac{(\sum x)^2}{n}$ y $S_{xy} = \sum xy - \frac{\sum x\sum y}{n}$ (📄 H2). La Calculadora de estadística → **Regresión lineal** da $b_0$ y $b_1$ directo.

Con n = 8: $\bar x = 29{,}725$, $\bar y = 15{,}5875$, $S_{xx} = 222{,}135$ y $S_{xy} = 166{,}41$.

```math
b_1 = \frac{166{,}41}{222{,}135} = 0{,}749 \qquad b_0 = 15{,}5875 - 0{,}749\cdot29{,}725 = -6{,}68
```

```math
\hat y = -6{,}68 + 0{,}749x
```

**Interpretación:**
- **$b_1 = 0{,}749$:** cada cm más de agua nieve aumenta la afluencia, en promedio, 0,749 pulgadas.
- **$b_0 = -6{,}68$:** sería la afluencia media con x = 0, pero x = 0 está muy fuera del rango observado (23 a 40), así que no tiene sentido práctico.

💡 **Supuestos del modelo** (❌). Para hacer tests, los **errores** (lo que la recta no explica) tienen que:
1. ser Normales;
2. tener la **misma varianza** para todo x (**homocedasticidad**);
3. ser independientes.

Se revisan con los **residuos** $e_i = y_i - \hat y_i$.

**b)** 💡 **Shapiro-Wilks** sobre los residuos: su H₀ es "son normales". Su valor p es 0,694 > 0,10, así que **no se rechaza** la normalidad ✓.

**c)** En el gráfico de residuos contra x se busca algún patrón: un **embudo** (la dispersión crece o decrece con x) o residuos muy grandes. No se ve ninguno, así que se acepta la homocedasticidad ✓.

**d)** 💡 **Test de significación del modelo.** Si la pendiente verdadera β₁ fuera 0, X no serviría para predecir Y. Lo que se quiere demostrar (que sirve) va en H₁:

```math
H_0: \beta_1 = 0 \qquad H_1: \beta_1 \neq 0
```

**Estadístico** (❌, la versión con b₁ no está en la hoja; la equivalente con r sí está): $T = \frac{b_1}{s/\sqrt{S_{xx}}} \sim t_{n-2}$, donde $s = \sqrt{\frac{SC_{res}}{n-2}}$ (📄 H2, $`\hat\sigma^2 = \frac{SC_{res}}{n-2}`$).

```math
SC_{res} = 4{,}26 \;\Rightarrow\; s = \sqrt{\frac{4{,}26}{6}} = 0{,}843 \qquad \frac{s}{\sqrt{S_{xx}}} = \frac{0{,}843}{14{,}90} = 0{,}0565
```

```math
t_{obs} = \frac{0{,}749}{0{,}0565} = 13{,}25
```

```
X~t(ν)   ν=6   P(X<x)=0.975   → x=2.44691
```
13,25 > 2,447: **se rechaza H₀**. La regresión es significativa.

(Con la fórmula de la hoja da lo mismo: $r = 0{,}983$ y $\sqrt6\,\frac{r}{\sqrt{1-r^2}} \approx 13{,}2$.)

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

**a)** 💡 **Recta de regresión** (📄 H2): $\hat d = b_0 + b_1u$, con $b_1 = \frac{S_{ud}}{S_{uu}}$ y $b_0 = \bar d - b_1\bar u$. Los S salen de las fórmulas de sumas de la hoja, o la Calculadora de estadística → **Regresión lineal** da $b_0$ y $b_1$.

Con n = 11: $\bar u = 1149{,}27$, $\bar d = 3{,}838$, $S_{uu} = 4\,558\,764$ y $S_{ud} = 18\,717{,}98$.

```math
b_1 = \frac{18\,717{,}98}{4\,558\,764} = 0{,}00411 \qquad b_0 = 3{,}838 - 0{,}00411\cdot1149{,}27 = -0{,}881
```

```math
\hat d = -0{,}881 + 0{,}0041u
```

💡 **¿El ajuste es adecuado? Test de significación.** Si la pendiente verdadera fuera 0, U no serviría para predecir D:

```math
H_0: \beta_1 = 0 \qquad H_1: \beta_1 \neq 0
```

Estadístico (❌): $T = \frac{b_1}{s/\sqrt{S_{uu}}} \sim t_{n-2}$, con $s = \sqrt{SC_{res}/(n-2)}$ (📄 H2, $`\hat\sigma^2`$).

```math
SC_{res} = 18{,}79 \;\Rightarrow\; s = \sqrt{18{,}79/9} = 1{,}445 \qquad \frac{s}{\sqrt{S_{uu}}} = 0{,}000677 \qquad t_{obs} = \frac{0{,}00411}{0{,}000677} = 6{,}07
```

```
X~t(ν)   ν=9   P(X<x)=0.995   → x=3.24984
```
6,07 > 3,25: **se rechaza H₀** al 1 %. La regresión es significativa ($`R^2 = 0{,}80`$).

**b)** Hay dos intervalos posibles en un punto, y es importante distinguirlos (❌, ninguno está en la hoja):
- 💡 **IC para la media**, E(D | u₀): el rango para la demanda **promedio** de todos los clientes con u = 900.
- 💡 **Intervalo de predicción (IP)**: el rango para la demanda de **un** cliente individual con u = 900.

Un cliente suelto varía mucho más que el promedio, así que el IP lleva un "1 +" extra adentro de la raíz y es **siempre más ancho**:

```math
IP = \hat d_0 \pm t\cdot s\sqrt{1 + \frac1n + \frac{(u_0 - \bar u)^2}{S_{uu}}} \qquad IC = \hat d_0 \pm t\cdot s\sqrt{\frac1n + \frac{(u_0 - \bar u)^2}{S_{uu}}}
```

Con $\hat d(900) = -0{,}881 + 0{,}00411\cdot900 = 2{,}815$ y $t_{9;0{,}995} = 3{,}25$:
- $IP = 2{,}815 \pm 4{,}93 = (-2{,}12;\ 7{,}75)$. Con 99 % de confianza, **un** cliente con 900 kWh tendrá una demanda en ese rango (en la práctica, entre 0 y 7,75).
- $IC = (1{,}30;\ 4{,}33)$: mucho más angosto.

**c) No.** u = 156 está **fuera** del rango observado (de 292 a 2189). Usar la recta ahí es **extrapolar** (❌): no hay datos que muestren que la relación siga siendo lineal tan lejos.

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

💡 **Regresión lineal:** se busca la recta $\hat y = b_0 + b_1x$ (📄 H2) que mejor aproxima los puntos (x = ruido, y = aumento de presión). El enunciado ya da las sumas, así que se usan las fórmulas de la hoja directamente. También sirve la Calculadora de estadística → **Regresión con suma**, cargando Σx, Σy, Σxy, Σx² y n.

**Cuentas base** (📄 H2), con n = 8:
- $S_{xx} = \sum x^2 - \frac{(\sum x)^2}{n} = 53\,030 - \frac{642^2}{8} = 1509{,}5$
- $S_{yy} = \sum y^2 - \frac{(\sum y)^2}{n} = 200 - \frac{34^2}{8} = 55{,}5$
- $S_{xy} = \sum xy - \frac{\sum x\sum y}{n} = 2983 - \frac{642\cdot34}{8} = 254{,}5$

Medias: $\bar x = 642/8 = 80{,}25$ y $\bar y = 34/8 = 4{,}25$.

**a)** (📄 H2)

```math
b_1 = \frac{S_{xy}}{S_{xx}} = \frac{254{,}5}{1509{,}5} = 0{,}1686 \qquad b_0 = \bar y - b_1\bar x = 4{,}25 - 0{,}1686\cdot80{,}25 = -9{,}28
```

```math
\hat y = -9{,}28 + 0{,}1686x
```

Cada dB más de ruido sube la presión, en promedio, 0,17 unidades.

**b)** 💡 **Coeficiente de determinación R²** (📄 H2, $`R^2 = \frac{SC_{exp}}{SC_{total}} = r^2`$): la proporción de la variabilidad de Y que **explica** la recta. Va de 0 (no explica nada) a 1 (todos los puntos sobre la recta).

```math
R^2 = \frac{S_{xy}^2}{S_{xx}S_{yy}} = \frac{254{,}5^2}{1509{,}5\cdot55{,}5} = 0{,}7731
```

**Interpretación:** el 77,3 % de la variabilidad del aumento de presión se explica por el nivel de ruido, a través de la recta. El 22,7 % restante se debe a otros factores.

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

💡 **Regresión lineal** ($`\hat y = b_0 + b_1x`$, 📄 H2) solo tiene sentido si los puntos forman aproximadamente una **recta**. Si no, a veces se puede **transformar** una variable para que sí la formen.

**a)** Y pasa de unos pocos a **millones**: crece en forma **exponencial** (multiplica, no suma), así que contra X no forma una recta. Un truco: el **logaritmo** convierte un crecimiento exponencial en uno lineal. Si $y \approx Ce^{kx}$, entonces $\ln y \approx \ln C + kx$, que es una recta. El gráfico de ln(Y) contra X se parece mucho más a una recta, así que se usa ese.

Se ajusta la recta con **ln y** en lugar de y (📄 H2, $b_1 = \frac{S_{xy}}{S_{xx}}$ y $b_0 = \bar y - b_1\bar x$, con y → ln y). En la Calculadora de estadística → Regresión lineal se cargan los pares (x; ln y):
- $\bar x = 9{,}1$, $\overline{\ln y} = 5{,}391$, $S_{xx} = 354{,}9$, $S_{x,\ln y} = 238{,}09$;
- $b_1 = \frac{238{,}09}{354{,}9} = 0{,}6709$ y $b_0 = 5{,}391 - 0{,}6709\cdot9{,}1 = -0{,}714$.

```math
\widehat{\ln y} = -0{,}714 + 0{,}671x \qquad (R^2 = 0{,}67)
```

Volviendo a y (exponencial de los dos lados): $\hat y = e^{-0{,}714}\cdot e^{0{,}671x}$.

**b)** Se predice el logaritmo y después se "deshace" con la exponencial:

```math
\widehat{\ln y}(15) = -0{,}714 + 0{,}6709\cdot15 = 9{,}35 \;\Rightarrow\; \hat y = e^{9{,}35} \approx 11\,488
```

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

💡 **Mínimos cuadrados** (❌, la deducción no está en la hoja). Para cada punto, el **residuo** $y_i - (b_0 + b_1x_i)$ es cuánto se equivoca la recta en ese punto. Se elige la recta que hace **mínima la suma de los residuos al cuadrado**. Se elevan al cuadrado para que los positivos y los negativos no se cancelen, y para castigar más los errores grandes.

Para minimizar una función de dos variables se deriva respecto de cada una y se iguala a 0, como en Análisis.

**a)** Se minimiza $g(b_0, b_1) = \sum(y_i - b_0 - b_1x_i)^2$. Derivando e igualando a 0 se obtienen las **ecuaciones normales**:
- $\frac{\partial g}{\partial b_0} = -2\sum(y_i - b_0 - b_1x_i) = 0 \Rightarrow \sum y_i = nb_0 + b_1\sum x_i$
- $\frac{\partial g}{\partial b_1} = -2\sum x_i(y_i - b_0 - b_1x_i) = 0 \Rightarrow \sum x_iy_i = b_0\sum x_i + b_1\sum x_i^2$

**Resolver el sistema.** Se divide la primera ecuación por n: $\bar y = b_0 + b_1\bar x$, así que $b_0 = \bar y - b_1\bar x$. La recta pasa por el punto de las medias.

Se reemplaza en la segunda y se despeja $b_1$:

```math
b_1 = \frac{n\sum x_iy_i - \sum x_i\sum y_i}{n\sum x_i^2 - (\sum x_i)^2} = \frac{S_{xy}}{S_{xx}}
```

Dividiendo arriba y abajo por n se reconocen $S_{xy}$ y $S_{xx}$ de la hoja. Son exactamente las fórmulas de 📄 H2.

**Relación con máxima verosimilitud.** 💡 Máxima verosimilitud (❌) elige los parámetros que hacen más probable la muestra observada. Si los errores son normales, el logaritmo de la verosimilitud es

```math
-\frac n2\ln(2\pi) - n\ln\sigma - \frac1{2\sigma^2}\sum(Y_i - a - bx_i)^2
```

El único término que depende de a y b tiene signo **menos** delante de la suma de cuadrados. Maximizarlo es lo mismo que **minimizar** esa suma. Por eso los estimadores de MV y de MC **coinciden**.

**b) Recta por el origen.** Ahora la recta es $\hat y = b_1x$ (sin $`b_0`$), y hay una sola incógnita. Se minimiza $g(b_1) = \sum(y_i - b_1x_i)^2$:

```math
g'(b_1) = -2\sum x_i(y_i - b_1x_i) = 0 \;\Rightarrow\; \sum x_iy_i = b_1\sum x_i^2 \;\Rightarrow\; b_1 = \frac{\sum x_iy_i}{\sum x_i^2}
```

Es un mínimo, porque la derivada segunda es $g'' = 2\sum x_i^2 > 0$.

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

💡 **Qué dice la fórmula.** La variabilidad total de Y (cuánto se aparta cada $Y_i$ de su promedio) se parte en dos pedazos:
- **$SC_{res}$**: lo que la recta **no** explica, la distancia de cada punto a la recta;
- **$SC_{regr}$** (o $`SC_{exp}`$): lo que la recta **sí** explica, la distancia de la recta al promedio.

La descomposición está en 📄 H2 ($`SC_{total} = SC_{exp} + SC_{res}`$), pero acá piden demostrarla. Es la base de $R^2 = SC_{exp}/SC_{total}$.

**Demostración.** El truco es sumar y restar $\hat Y_i$ (lo que predice la recta) adentro del paréntesis:

```math
\sum(Y_i - \bar Y)^2 = \sum\left[(Y_i - \hat Y_i) + (\hat Y_i - \bar Y)\right]^2
```

Se desarrolla el cuadrado de un binomio, $(a+b)^2 = a^2 + b^2 + 2ab$, con $e_i = Y_i - \hat Y_i$:

```math
= \sum(Y_i - \hat Y_i)^2 + \sum(\hat Y_i - \bar Y)^2 + 2\sum e_i(\hat Y_i - \bar Y)
```

**Falta ver que el último término (el "doble producto") vale 0.** Como $\hat Y_i = b_0 + b_1x_i$:

```math
\sum e_i(\hat Y_i - \bar Y) = \sum e_i(b_0 + b_1x_i - \bar Y) = (b_0 - \bar Y)\sum e_i + b_1\sum e_ix_i
```

Las **ecuaciones normales** (ejercicio 8, las que salen de derivar e igualar a 0 en mínimos cuadrados) dicen justamente que $\sum e_i = 0$ y $\sum e_ix_i = 0$. Entonces el doble producto es 0, y queda la igualdad. ∎

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

Se revisa cada cantidad y qué valores puede tomar.

- **$SC_{Total} < SC_{error} + SC_{regres}$:** falsa. La variabilidad total **siempre es igual** a la suma de la no explicada más la explicada (📄 H2, $SC_{total} = SC_{exp} + SC_{res}$; demostrado en el ejercicio 9). No puede ser menor.
- **$R^2 = -0{,}65$:** falsa. 💡 R² es la **fracción** de la variabilidad explicada por la recta, y además es un cuadrado (📄 H2, $`R^2 = r^2`$). Siempre está entre 0 y 1.
- **$s_b = -1{,}25$:** falsa. $s_b$ es el **desvío estándar** (error estándar) de la pendiente estimada, una raíz cuadrada. Nunca es negativo.
- **$t_{obs} = -2{,}45$:** **puede ser cierta**. El estadístico del test de la pendiente es $t = b_1/s_b$. El denominador es positivo, así que t tiene el **signo de $b_1$**: si la recta es decreciente, t es negativo. Lo mismo con la versión de la hoja, $\sqrt{n-2}\frac{r}{\sqrt{1-r^2}}$, que tiene el signo de r.

</details>

**Respuesta:** La última ($`t_{obs}`$ = −2,45).

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

**a)** 💡 **Recta de mínimos cuadrados** (📄 H2): $\hat y = b_0 + b_1x$, con $b_1 = \frac{S_{xy}}{S_{xx}}$ y $b_0 = \bar y - b_1\bar x$. La Calculadora de estadística → **Regresión lineal** da los coeficientes cargando los 13 pares.

$\bar x = 0{,}4554$, $\bar y = 0{,}8054$, $S_{xx} = 1{,}1155$ y $S_{xy} = 1{,}0785$.

```math
b_1 = \frac{1{,}0785}{1{,}1155} = 0{,}967 \qquad b_0 = 0{,}8054 - 0{,}967\cdot0{,}4554 = 0{,}365
```

```math
\hat y = 0{,}37 + 0{,}97x
```

**b)** Una salida de computadora de regresión tiene, para cada coeficiente, su estimación, su error estándar, el **t** y el **valor p** del test "ese coeficiente vale 0".

💡 **Valor p:** la probabilidad, si el coeficiente verdadero fuera 0, de obtener un t tan extremo o más. Si es chico (< 0,05), el coeficiente es significativo.

Con $s = \sqrt{\frac{SC_{res}}{n-2}} = \sqrt{\frac{0{,}4106}{11}} = 0{,}193$ (📄 H2) y 11 grados de libertad:
- **Ordenada:** $s_{b_0} = 0{,}099$, t = 0,365/0,099 = 3,69.
  ```
  X~t(ν)   ν=11   P(X>x)   x=3.69   → 0.0018   → p = 2·0.0018 = 0.0036
  ```
- **Pendiente:** $s_{b_1} = s/\sqrt{S_{xx}} = 0{,}183$, t = 0,967/0,183 = 5,29.
  ```
  X~t(ν)   ν=11   P(X>x)   x=5.29   → 0.00013  → p ≈ 0.0003
  ```

El p de la **pendiente** es < 0,05: se rechaza β₁ = 0 y el modelo es **significativo** ($`R^2 = 0{,}72`$).

**c)** 💡 **IC para el valor esperado** de Y en x₀ (❌, no está en la hoja): el rango para el nitrógeno **promedio** de todos los líquenes con 0,4 g/cm² de nitrato. Tiene la forma "estimación ± t · error estándar":

```math
\hat y_0 \pm t_{n-2;1-\frac\alpha2}\cdot s\sqrt{\frac1n + \frac{(x_0 - \bar x)^2}{S_{xx}}}
```

Es más angosto cerca de $\bar x$ y se ensancha al alejarse.

$\hat y(0{,}4) = 0{,}365 + 0{,}967\cdot0{,}4 = 0{,}752$, y:
```
X~t(ν)   ν=11   P(X<x)=0.975   → x=2.20099
```

```math
0{,}752 \pm 2{,}201\cdot0{,}193\sqrt{\frac1{13} + \frac{(0{,}4 - 0{,}4554)^2}{1{,}1155}} = 0{,}752 \pm 0{,}120 = (0{,}632;\ 0{,}872)
```

La guía informa [0,536; 0,98], que no coincide con los datos de la tabla. Con esta fórmula sale el intervalo de arriba.

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

**a)** 💡 En el **diagrama de dispersión** (cada pieza es un punto: x = superficie, y = peso), los puntos bajan en general: a más superficie, menos peso. Pero la 6.ª observación (61,4; 68,7) tiene la **mayor** superficie y el **mayor** peso, contra la tendencia del resto.

Es un punto **atípico**. Además está en un extremo de x, lo que lo hace **influyente**: puede "tirar" de la recta hacia él.

**b)** 💡 **Recta de mínimos cuadrados** (📄 H2): $b_1 = \frac{S_{xy}}{S_{xx}}$ y $b_0 = \bar y - b_1\bar x$. Calculadora de estadística → **Regresión lineal** con los 9 pares:

```math
b_1 = \frac{-18{,}06}{594{,}52} = -0{,}030 \qquad b_0 = 49{,}35 \;\Rightarrow\; \hat y = 49{,}35 - 0{,}03x \quad (R^2 \approx 0)
```

La recta sale casi **horizontal**: el punto atípico "cancela" la tendencia decreciente.

**c)** 💡 **Residuo** = observado − predicho = $y_i - \hat y_i$:

−0,41; −3,23; −4,74; 8,55; 14,95; **21,22**; −6,27; −13,43; −16,63.

El 6.º es el más grande: la recta no logra acercarse a ese punto.

**d)** Sin la 6.ª observación (8 pares):

```math
b_1 = -1{,}146 \qquad b_0 = 95{,}90 \;\Rightarrow\; \hat y = 95{,}90 - 1{,}146x \quad (R^2 = 0{,}55)
```

Residuos: 2,22; −8,88; 6,40; 2,20; 11,86; −5,91; −0,49; −7,40. Son mucho más parejos.

**Comparación:** un **solo punto** cambiaba por completo la pendiente, de −1,15 a casi 0, y hacía desaparecer la relación ($`R^2`$ de 0,55 a 0). Antes de ajustar conviene mirar el gráfico y revisar los puntos raros.

</details>

**Respuesta:**

- a) La sexta observación
- b) $\hat\alpha = 49{,}35$, $\hat\beta = -0{,}03$
- c) El sexto residuo (21,22)
- d) $\hat y_i = 95{,}9 - 1{,}146x_i$: cambian fundamentalmente los coeficientes

</details>

---

[← Volver al menú principal](../README.md)
