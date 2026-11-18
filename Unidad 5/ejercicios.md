# Unidad 5 — Ejercicios resueltos

Ejercicios de la **Práctica 5 de la Guía de TP** (Test de Hipótesis).

Cada ejercicio tiene un botón **Solución**. Al abrirlo aparece la respuesta y, arriba de ella, un segundo botón **Solución paso a paso** con el desarrollo completo.

Notación: Φ(z) = P(Z < z) para Z ~ N(0; 1). $z_{q}$, $t_{n-1;\,q}$ y $\chi^2_{n-1;\,q}$ son los valores con probabilidad **acumulada q a la izquierda**. RC = región crítica (de rechazo). Los tests se resuelven con los pasos del apunte: 1) hipótesis, 2) α, 3) estadístico de prueba, 4) valor observado, 5) decisión.

> **Referencias:** *(opcional)* = la cátedra indica que no es necesario resolverlo · (T) = ejercicio teórico · (\*) = requiere aplicación informática o de celular.

---

### 1) Planteo de hipótesis

Dados los siguientes pares de aseveraciones, indicar cuál/es no cumple/n con las reglas para establecer hipótesis acerca del valor de la media poblacional μ en una prueba basada en una muestra aleatoria $\{X_1, X_2, \dots, X_n\}$. Justificar la respuesta.

- a) H₀: μ = 100 vs. H₁: μ = 200
- b) H₀: μ = 100 vs. H₁: μ < 100
- c) H₀: μ = 100 vs. H₁: μ ≠ 100
- d) H₀: μ < 100 vs. H₁: μ ≥ 100
- e) H₀: μ ≤ 100 vs. H₁: μ > 100
- f) H₀: μ ≠ 100 vs. H₁: μ = 100
- g) H₀: x̄ = 100 vs. H₁: x̄ > 100

Asociar los siguientes enunciados con las hipótesis que les correspondan.

- a) Para determinar si las soldaduras efectuadas en tubos de una planta de energía nuclear cumplen con las especificaciones, se selecciona una muestra al azar de soldaduras y se realizan pruebas en cada soldadura de la muestra. La resistencia de la soldadura se mide como la fuerza requerida para romper la soldadura. Supongamos que en las especificaciones se establece que la resistencia media de soldaduras debe rebasar 100 lb/pulg².
- b) Interesa controlar si una balanza está correctamente calibrada; para ello se pesará una pesa patrón de 100 kg, veinte veces.
- c) Se conduce una investigación para estudiar si el nivel de ventas promedio de una sucursal por día es inferior a 100 unidades.
- d) ¿Qué significaría el error de tipo I en (a)?
- e) ¿Qué implicaría el error de tipo II en (b)?

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

Reglas: las hipótesis son sobre un **parámetro** (no sobre un estadístico como $\bar x$), H₀ lleva la **igualdad** (=, ≤ o ≥) y H₁ es la desigualdad estricta que se quiere probar.

- d) No cumple: la igualdad está en H₁.
- f) No cumple: H₀ no puede ser "≠" (no fija un valor para calcular α).
- g) No cumple: las hipótesis se plantean sobre μ, no sobre $\bar x$.
- a) es válida como test de hipótesis simple vs. simple, aunque es poco usual.

Asociaciones:
- (a) Soldaduras: se quiere probar que la media **supera** 100 ⇒ H₀: μ ≤ 100 vs. H₁: μ > 100 → par (e).
- (b) Balanza: interesa cualquier desvío ⇒ H₀: μ = 100 vs. H₁: μ ≠ 100 → par (c).
- (c) Ventas: interesa si es **inferior** ⇒ H₀: μ = 100 vs. H₁: μ < 100 → par (b).
- (d) Error tipo I en (a): rechazar H₀ siendo verdadera ⇒ decir que las soldaduras cumplen la especificación cuando no la cumplen.
- (e) Error tipo II en (b): no rechazar H₀ siendo falsa ⇒ no detectar que la balanza está descalibrada.

</details>

**Respuesta:**

- (d), (f) y (g) no cumplen
- a) ↔ (e) · b) ↔ (c) · c) ↔ (b)
- d) Decir que cumple la especificación cuando no es así
- e) No detectar que la balanza está descalibrada

</details>

---

### 2) Regiones de rechazo

El estadístico de contraste de un ensayo de hipótesis, Z, tiene distribución Normal estándar. Indicar para cada una de las regiones de rechazo las hipótesis correspondientes y el nivel de significación considerado:

- a) {Z > 2,33}
- b) {Z < −2,58}
- c) {Z < −1,96 ∨ Z > 1,96}

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

a) RC a la derecha ⇒ unilateral derecho. α = P(Z > 2,33) = 0,01.

b) RC a la izquierda ⇒ unilateral izquierdo. α = P(Z < −2,58) = 0,005.

c) RC en las dos colas ⇒ bilateral. α = 2·P(Z > 1,96) = 0,05.

(En la guía figura "{Z < 1,96 ∨ Z > −1,96}", que es una errata: así escrita sería toda la recta.)

</details>

**Respuesta:**

- a) α = 0,01; H₀: μ = μ₀ vs. H₁: μ > μ₀
- b) α = 0,005; H₀: μ = μ₀ vs. H₁: μ < μ₀
- c) α = 0,05; H₀: μ = μ₀ vs. H₁: μ ≠ μ₀

</details>

---

### 3) Valor p con Z

Para cada uno de los siguientes pares de hipótesis, considerando una prueba cuyo estadístico de contraste tenga distribución normal estándar, indicar el valor p de la prueba para los valores observados en cada caso.

- a) H₀: μ = 10 vs. H₁: μ > 10; $Z_{obs}$ = 2,5
- b) H₀: μ = 12 vs. H₁: μ < 12; $Z_{obs}$ = −1,2
- c) H₀: μ = 7 vs. H₁: μ ≠ 7; $Z_{obs}$ = 2,8

¿En qué casos rechazaría la hipótesis nula con un nivel de significación del 5 %?

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

El valor p es la probabilidad, bajo H₀, de obtener un valor **tan extremo o más** que el observado, en la dirección de H₁. Se rechaza H₀ si p < α.

a) p = P(Z > 2,5) = 0,00621 < 0,05 ⇒ se rechaza.

b) p = P(Z < −1,2) = 0,1151 > 0,05 ⇒ no se rechaza.

c) Bilateral: p = 2·P(Z > 2,8) = 0,00511 < 0,05 ⇒ se rechaza.

</details>

**Respuesta:**

- a) p = 0,00621 ⇒ se rechaza H₀
- b) p = 0,1151 ⇒ no se rechaza H₀
- c) p = 0,00512 ⇒ se rechaza H₀

</details>

---

### 4) Valor p con t (\*)

Dado el valor observado para una prueba basada en un estadístico t y sus grados de libertad (gl), aproximar el p valor y la decisión de una prueba con nivel de significación α = 0,05:

- a) unilateral derecha, con gl = 8, $t_{obs}$ = 2,84
- b) unilateral izquierda, con gl = 10, $t_{obs}$ = −2,5
- c) bilateral, con gl = 15, $t_{obs}$ = 1,95

¿En alguno de los casos le parece que cambiaría la decisión si se considerara un nivel de significación α = 0,01?

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

a) p = P(t₈ > 2,84) = 0,0109 < 0,05 ⇒ se rechaza.

b) p = P(t₁₀ < −2,5) = 0,0157 < 0,05 ⇒ se rechaza.

c) p = 2·P(t₁₅ > 1,95) = 0,0701 > 0,05 ⇒ no se rechaza.

Con α = 0,01: en a) y b) p > 0,01, así que **dejarían de rechazarse**. En c) sigue sin rechazarse.

(La respuesta "No" de la guía no coincide con este análisis: con α = 0,01 sí cambia la decisión en a) y b).)

</details>

**Respuesta:**

- a) p = 0,0109 ⇒ se rechaza
- b) p = 0,0157 ⇒ se rechaza
- c) p = 0,0701 ⇒ no se rechaza
- Con α = 0,01, a) y b) pasarían a no rechazarse

</details>

---

### 5) Test con una sola observación exponencial

Se dispone de una muestra de tamaño 1 para decidir entre dos hipótesis sobre la media μ de una distribución Exponencial. La hipótesis H afirma que μ ≤ 2 y la hipótesis K afirma que μ > 2.

- a) Diseñar una regla de decisión que cumpla la condición de que la máxima probabilidad de equivocarse al rechazar la hipótesis H cuando H es verdadera sea 0,1.
- b) Calcular la probabilidad de decidir en forma errónea cuando el verdadero valor de la media es μ = 2,1.

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

a) Valores grandes de X apoyan K ⇒ RC = {X > c}. P(X > c) = $e^{-c/\mu}$ crece con μ, así que el máximo bajo H se da en μ = 2:

$e^{-c/2} = 0{,}1 \Rightarrow c = -2\ln0{,}1 = 4{,}6$.

b) Con μ = 2,1 la verdadera es K. El error es no rechazar H (tipo II):

$\beta = P(X \le 4{,}6) = 1 - e^{-4{,}6/2{,}1} = 0{,}8884$.

</details>

**Respuesta:**

- a) Se rechaza H si $x_{obs}$ > 4,6
- b) 0,8884

</details>

---

### 6) Nuevo sistema de producción

Una empresa estudia introducir un nuevo sistema de producción para mejorar su productividad media, establecida actualmente en 42 unidades por persona y por día. Se estima que el cambio no será rentable si no consigue elevar dicho número por encima de 45 u. Realizada una prueba con la nueva tecnología, aplicada a 35 personas, se obtuvo una producción media de 46,5 y no se observó ningún cambio apreciable en la dispersión, que estaba establecida en σ = 3 u por día. Considerando esta información y utilizando un nivel de significación del 1 %, ¿se debería efectuar el cambio tecnológico?

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

1) Se quiere probar que la media supera 45: H₀: μ ≤ 45 vs. H₁: μ > 45.

2) α = 0,01.

3) σ conocido y n = 35 ≥ 30: $Z = \frac{\bar X - 45}{3/\sqrt{35}} \sim N(0; 1)$.

4) $z_{obs} = \frac{46{,}5 - 45}{0{,}507} = 2{,}96$.

5) RC = {Z > $z_{0{,}99}$ = 2,33}. Como 2,96 > 2,33 ⇒ se rechaza H₀ (p = 0,0015).

Equivalente con $\bar X$: RC = {$\bar X$ > 46,18}, y 46,5 está en la RC.

</details>

**Respuesta:** Se rechaza H₀ ($z_{obs}$ = 2,96 > 2,33): hay evidencia al 1 % de que la productividad supera 45 ⇒ conviene implementar el cambio.

</details>

---

### 7) Calibración de un fotómetro

Se desea calibrar un fotómetro para medir la proporción de monóxido de carbono (CO) de un gas. Se toman 25 mediciones de una muestra patrón con 60 ppm de proporción de CO, sabiendo que los errores de medición tienen distribución Normal con dispersión σ = 0,5 ppm. Designando con μ al verdadero valor medio de la calibración del fotómetro:

- a) ¿Qué hipótesis probaría?
- b) Si se rechaza la hipótesis de nulidad para valores de x̄ superiores a 60,196 ppm o inferiores a 59,804 ppm, ¿cuál es la probabilidad de que la recalibración se realice sin ser necesaria?
- c) ¿Cuál es la probabilidad de no recalibrar si el fotómetro mide 60,3 ppm?

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

a) Interesa cualquier desvío ⇒ H₀: μ = 60 vs. H₁: μ ≠ 60.

$\sigma_{\bar X} = 0{,}5/\sqrt{25} = 0{,}1$.

b) Recalibrar sin necesidad = error tipo I:

$\alpha = P(\bar X > 60{,}196) + P(\bar X < 59{,}804)$ con μ = 60, es decir $2\,P(Z > 1{,}96) = 0{,}05$.

c) No recalibrar si μ = 60,3 = error tipo II:

$\beta = P(59{,}804 < \bar X < 60{,}196)$ con $\bar X \sim N(60{,}3; 0{,}1)$, o sea $\Phi(-1{,}04) - \Phi(-4{,}96) = 0{,}1492$.

</details>

**Respuesta:**

- a) H₀: μ = 60 vs. H₁: μ ≠ 60
- b) α = 0,05
- c) 0,1492

</details>

---

### 8) Rendimiento del auto A

Un fabricante sostiene que el modelo de auto A tiene un rendimiento promedio menor a 13 kilómetros por litro de nafta. Se selecciona una muestra de 9 de estos vehículos, y cada uno es conducido con un litro de nafta en las mismas condiciones. La muestra proporciona una media de 12,34 km/l. Se sabe que la distribución de la cantidad de kilómetros recorridos por litro de nafta es Normal con un desvío estándar de 1,26 km/l.

- a) Plantear las hipótesis a contrastar, el estadístico del test junto con su distribución y la decisión tomada a nivel 0,05.
- b) ¿El test elegido es de nivel exacto o aproximado? Justificar.
- c) ¿Cuál es la probabilidad de no decidir que se cumple la hipótesis del fabricante, cuando el verdadero rendimiento medio del modelo de auto A es de 12 km/l?

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

a) La afirmación del fabricante va en H₁: H₀: μ ≥ 13 vs. H₁: μ < 13.

Bajo H₀: $\bar X \sim N(13;\ 1{,}26/3 = 0{,}42)$.

RC = {$\bar X$ < 13 − 1,645·0,42 = 12,31}. Como $\bar x$ = 12,34 > 12,31 (o $z_{obs}$ = −1,57 > −1,645) ⇒ no se rechaza H₀.

b) **Exacto:** la población es Normal con σ conocido, así que $\bar X$ es exactamente normal (no se usa el TCL).

c) No decidir a favor del fabricante = no rechazar H₀:

$\beta = P(\bar X > 12{,}31)$ con μ = 12, es decir $1 - \Phi\left(\frac{12{,}31 - 12}{0{,}42}\right) = 0{,}231$.

</details>

**Respuesta:**

- a) H₀: μ ≥ 13 vs. H₁: μ < 13; $\bar X \sim N(13; 0{,}42)$; no se rechaza H₀ al 5 %
- b) Exacto, pues se conoce la distribución exacta del estadístico
- c) 0,231

</details>

---

### 9) Curva de potencia (\*)

(\*) La gráfica de la guía corresponde a la curva de potencia de una prueba para la media de una población normal, conocida la varianza σ² = 4, basada en una muestra de tamaño n = 25 (la potencia vale α en μ = 10 y crece hacia 1 para μ > 10).

- a) Indicar qué hipótesis se están testeando.
- b) Sabiendo que $\beta_{\mu=11}$ = 0,2946, ¿cuál es el nivel de significación de la prueba?
- c) Hallar la probabilidad del error de tipo II para μ = 11,2, μ = 11,5 y μ = 12.

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

a) La potencia crece sólo hacia la derecha de 10 ⇒ H₀: μ = 10 vs. H₁: μ > 10.

$\sigma_{\bar X} = 2/5 = 0{,}4$. RC = {$\bar X$ > c}.

b) $\beta_{11} = P(\bar X < c \mid \mu = 11) = 0{,}2946$ ⇒ $\frac{c - 11}{0{,}4} = z_{0{,}2946} = -0{,}54 \Rightarrow c = 10{,}784$.

$\alpha = P(\bar X > 10{,}784 \mid \mu = 10) = 1 - \Phi(1{,}96) = 0{,}025$.

c) $\beta_\mu = \Phi\left(\frac{10{,}784 - \mu}{0{,}4}\right)$:
- μ = 11,2: Φ(−1,04) = 0,1492
- μ = 11,5: Φ(−1,79) = 0,0367
- μ = 12: Φ(−3,04) = 0,0012

</details>

**Respuesta:**

- a) H₀: μ = 10 vs. H₁: μ > 10
- b) α = 0,025
- c) $\beta_{11{,}2}$ = 0,1492; $\beta_{11{,}5}$ ≈ 0,03; $\beta_{12}$ = 0,0012

</details>

---

### 10) Compresión del cemento: tamaño de muestra

El coeficiente de compresión del cemento curado sigue una distribución Normal con una media de 50 kg/cm² (en cientos). Utilizar un cemento de menor coeficiente promedio podría ocasionar problemas en la construcción, por lo que se requiere tener una probabilidad de 0,95 de descartar las partidas si el coeficiente de compresión promedio proviniera de una población con coeficiente de compresión promedio de 47 kg/cm², y una probabilidad de 0,01 de rechazar las partidas que cumplan con la especificación. Supongamos que el desvío de la población es de 5 kg/cm².

- a) Plantear un test adecuado. Justificar las hipótesis elegidas.
- b) Calcular el tamaño de la muestra necesario para que se cumplan las condiciones requeridas y establecer la zona de rechazo y la regla de decisión.

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

a) Preocupa un coeficiente **menor** ⇒ H₀: μ = 50 vs. H₁: μ < 50, con α = 0,01.

Se rechaza H₀ (se descarta la partida) si $\bar X < x_{crít} = 50 - 2{,}33\frac5{\sqrt n}$.

b) Condiciones:
- α = 0,01 ⇒ $x_{crít} = 50 - 2{,}33\frac5{\sqrt n}$ (ecuación I).
- Potencia 0,95 en μ₁ = 47 ⇒ β = 0,05 ⇒ $x_{crít} = 47 + 1{,}645\frac5{\sqrt n}$ (ecuación II).

Igualando: $\sqrt n = \frac{(2{,}33 + 1{,}645)\cdot5}{3} = 6{,}625 \Rightarrow n = 43{,}9$ ⇒ **n = 44**.

$x_{crít} = 50 - 2{,}33\cdot\frac5{\sqrt{44}} = 48{,}24$.

</details>

**Respuesta:**

- a) H₀: μ = 50 vs. H₁: μ < 50; se rechaza H₀ si $\bar x < 50 - 2{,}33\frac{5}{\sqrt n}$
- b) n = 44; se rechazan las partidas con $\bar x$ < 48,24

</details>

---

### 11) Altura de la espuma del shampoo

Una compañía de productos para el consumidor está desarrollando un nuevo shampoo y está interesada en la altura de la espuma (en mm). La altura de la espuma tiene una distribución aproximadamente Normal. La compañía quiere verificar si la altura de la espuma supera los 180 mm, y se considera una muestra de tamaño 24. Los valores observados son:

122,72 182,53 156,03 200,31 219,86 187,20 213,00 133,47 203,39 207,56 212,64 132,57 204,95 181,51 184,27 194,70 184,46 169,48 207,28 186,65 195,85 181,26 181,78 211,32

- a) Establecer las hipótesis correspondientes al test.
- b) Interpretar la salida del programa R. Concluir.

```
data: muestra
t = 0.81221, df = 23, p-value = 0.2123
alternative hypothesis: true mean is greater than 180
sample estimates:
mean of x 185.62
```

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

a) H₀: μ ≤ 180 vs. H₁: μ > 180.

b) Población normal, σ desconocido, n = 24 < 30 ⇒ test t con 23 g.l.

R informa $t_{obs}$ = 0,81 y valor p = 0,2123 > α = 0,05 ⇒ no se rechaza H₀.

(Con los datos listados se obtiene $\bar x$ = 185,62 y s = 26,42, de donde $t_{obs}$ = 1,04 y p = 0,154: la conclusión es la misma.)

</details>

**Respuesta:**

- a) H₀: μ ≤ 180 vs. H₁: μ > 180
- b) p = 0,2123 > 0,05 ⇒ no se rechaza H₀. No hay evidencia de que la altura media supere los 180 mm

</details>

---

### 12) Índice de esfericidad *(opcional)*

La calidad de ciertas piezas de un aparato depende de su esfericidad. Para mejorar el control de calidad se determinó un nuevo método para medir el índice de esfericidad (IE) y se aplicó en 91 piezas.

| Variable | n | Media | D.E. | W\* | p (una cola) |
|---|---|---|---|---|---|
| IE | 91 | 1,45 | 0,22 | 0,93 | 0,2569 |

(Test de Shapiro-Wilks). El método de medición anterior tiene un desvío estándar de 0,32 plg. Interesa determinar si el nuevo método es más preciso, es decir, si tiene menor desvío estándar.

- a) Analizar el cumplimiento de los supuestos para realizar un test y usar un nivel de significación del 5 %.
- b) Realizar la prueba y concluir en el contexto del problema.

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

a) El test para σ² requiere normalidad. Shapiro-Wilks da p = 0,2569 > 0,05 ⇒ no se rechaza la normalidad, así que se puede usar $\frac{(n-1)S^2}{\sigma_0^2} \sim \chi^2_{n-1}$.

b) H₀: σ² = 0,32² vs. H₁: σ² < 0,32².

$\chi^2_{obs} = \frac{90\cdot0{,}22^2}{0{,}32^2} = 42{,}54$; RC = {χ² < $\chi^2_{90;\,0{,}05}$ = 69,13}.

42,54 < 69,13 ⇒ se rechaza H₀ (p ≈ 0,000005).

</details>

**Respuesta:**

- a) H₀: σ² = 0,32² vs. H₁: σ² < 0,32²; Shapiro-Wilks no rechaza la normalidad, así que vale el test χ²
- b) $\chi^2_{obs}$ = 42,539 < 69,126 ⇒ se rechaza H₀: hay evidencia de que el nuevo método es más preciso

</details>

---

### 13) Tiempo de armado según el capataz

Un capataz afirma que bajo su supervisión el armado de una pieza tiene una duración promedio inferior a 25 minutos y una dispersión de 2 minutos. El tiempo medio arrojado por una muestra de 25 obreros con este nuevo proceso resultó de 23 minutos y el desvío estándar muestral es de 3,9 minutos. Los tiempos se distribuyen en forma aproximadamente Normal.

- a) Plantear un test para decidir si la media y la variabilidad del tiempo del armado de una pieza coinciden con la afirmación del capataz.
- b) Concluir en función de los datos muestrales, considerando un nivel de significación del 5 %.

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

**Media:**
- H₀: μ ≥ 25 vs. H₁: μ < 25 (la afirmación del capataz va en H₁).
- σ desconocido y n = 25 < 30 ⇒ $T = \frac{\bar X - 25}{S/\sqrt{25}} \sim t_{24}$.
- $t_{obs} = \frac{23 - 25}{3{,}9/5} = -2{,}56 < t_{24;\,0{,}05} = -1{,}71$ ⇒ se rechaza H₀: la afirmación sobre la media es correcta.

**Varianza** (ejemplo del apunte):
- H₀: σ² = 4 vs. H₁: σ² ≠ 4.
- $\chi^2 = \frac{(n-1)S^2}{\sigma_0^2} \sim \chi^2_{24}$.
- $\chi^2_{obs} = \frac{24\cdot15{,}21}{4} = 91{,}26$.
- RC = {χ² < 12,40} ∪ {χ² > 39,36}. Como 91,26 > 39,36 ⇒ se rechaza H₀: el desvío **no** es 2 min.

</details>

**Respuesta:**

- Media: $t_{obs}$ = −2,56 < $t_{crít}$ = −1,71 ⇒ se rechaza H₀; la afirmación sobre la media es correcta
- Varianza: $\chi^2_{obs}$ = 91,26 > 39,36 ⇒ se rechaza H₀; la afirmación sobre la dispersión no es correcta

</details>

---

### 14) Neumáticos Mirelli

El fabricante de neumáticos Mirelli sostiene que en promedio sus productos tienen una duración superior a 50.000 km antes de necesitar reemplazo. Un grupo de consumidores quiere poner a prueba dicha afirmación. Para ello seleccionan una muestra de 50 neumáticos y resulta que en promedio duraron 50.300 km, con una dispersión de 1000 km.

- a) Definir con claridad cuál sería el parámetro de interés en este problema.
- b) Establecer la hipótesis nula y la alternativa en términos de dicho parámetro.
- c) Explicar el significado de los errores de tipo I y II en el contexto de este problema.
- d) Responder si la afirmación del fabricante es aceptable con un nivel de significación del 0,01.

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

a) μ = verdadera duración media de los neumáticos Mirelli antes de requerir reemplazo.

b) H₀: μ ≤ 50.000 vs. H₁: μ > 50.000.

c)
- Tipo I: creer que la duración media supera 50.000 km cuando no es así.
- Tipo II: no detectar que la duración media supera 50.000 km cuando sí la supera.

d) $t_{obs} = \frac{50300 - 50000}{1000/\sqrt{50}} = 2{,}12$.

Valor crítico: $t_{49;\,0{,}99} = 2{,}405$ (o $z_{0{,}99} = 2{,}33$ con n ≥ 30). Como 2,12 < 2,405 ⇒ no se rechaza H₀.

</details>

**Respuesta:**

- a) μ: duración media real de los neumáticos Mirelli
- b) H₀: μ ≤ 50000 vs. H₁: μ > 50000
- c) Tipo I: confiar en que la duración supera 50000 km cuando no es así. Tipo II: no detectar que la supera
- d) $t_{obs}$ = 2,12 < 2,405 ⇒ no se rechaza H₀ al 1 %: no hay evidencia suficiente para la afirmación del fabricante

</details>

---

### 15) Proveedores de internet

Dos empresas distintas compiten para brindar servicio de internet en cierta región. Denotamos con p a la proporción de pobladores que prefieren a la primera de las empresas por encima de la segunda. Se toma una muestra aleatoria de 50 personas para probar la hipótesis de que la primera empresa tiene conquistada más de la mitad del mercado.

- a) Considerando que X es la cantidad de individuos encuestados que optaron por la primera empresa, ¿cuál de las siguientes regiones de rechazo le parece más adecuada? {x ≥ 32}; {x ≤ 18}; {x ≤ 15 ∨ x ≥ 45}
- b) ¿Cuál es la distribución de probabilidad de X siendo cierta H₀?
- c) ¿Qué se puede concluir, al 1 %, si 12 personas estuvieron a favor de la segunda empresa? ¿Cuál es el p valor de la prueba?
- d) ¿Cuál es la probabilidad de cometer error de tipo II si p = 0,6?

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

a) H₀: p = 0,5 vs. H₁: p > 0,5 ⇒ se rechaza con valores **grandes** de X ⇒ {X ≥ 32}.

b) Bajo H₀: X ~ Bin(50; 0,5).

c) 12 a favor de la segunda ⇒ x = 38, $\hat p$ = 0,76.

$z_{obs} = \frac{0{,}76 - 0{,}5}{\sqrt{0{,}25/50}} = 3{,}68$, que es mayor que $z_{0{,}99}$ = 2,33 ⇒ se rechaza H₀.

p valor = P(Z > 3,68) ≈ 0,0001.

d) $\beta = P(X < 32 \mid p = 0{,}6)$. Con la aproximación normal, $X \approx N(30; \sqrt{12})$ ⇒ $\Phi\left(\frac{32 - 30}{3{,}46}\right) = 0{,}718$.

</details>

**Respuesta:**

- a) {X ≥ 32}
- b) X ~ Bi(50; 0,5) bajo H₀: p = 0,5
- c) $z_{obs}$ ≈ 3,7; p valor < 0,001 ⇒ se rechaza H₀
- d) 0,718

</details>

---

### 16) Crema para manchas

Una empresa de cosmética afirma que una nueva crema reduce las manchas del cutis tras un uso prolongado (3 meses o más) en más de un 60 %. A fin de verificar la veracidad de esta afirmación, un centro de belleza que pretende adquirir este producto utilizará el mismo en 120 manchas de cutis de clientas elegidas al azar. Si se eliminan más de 82 manchas, tomará la decisión de adquirir el nuevo producto.

- a) Evaluar el nivel de significación utilizado.
- b) Hallar el error de tipo II que se cometería si el producto lograra limpiar el 75 % de las manchas.

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

H₀: p = 0,6 vs. H₁: p > 0,6. X = manchas eliminadas de 120; RC = {X > 82}.

a) Bajo H₀: E(X) = 72, σ = √(120·0,6·0,4) = 5,37.

α = P(X > 82) ≈ 1 − Φ((82 − 72)/5,37) = 1 − Φ(1,86) ≈ 0,031.

b) Con p = 0,75: E(X) = 90, σ = √22,5 = 4,74.

β = P(X ≤ 82) ≈ Φ((82 − 90)/4,74) = Φ(−1,69) ≈ 0,0455.

</details>

**Respuesta:**

- a) α = 0,03144
- b) $\beta_{0{,}75}$ = 0,04551

</details>

---

### 17) Campaña publicitaria del café A

Se supone que el 10 % de los consumidores de cierta localidad prefiere la marca A de café. Se realizó una campaña publicitaria y, después de la misma, se entrevistó a 100 habitantes de esta localidad para determinar la efectividad de la campaña. El resultado de esta encuesta mostró que 13 encuestados prefieren la marca A.

- a) ¿Existe evidencia, a nivel aproximado 0,05, de un aumento en la preferencia por la marca A?
- b) Calcular el valor p.
- c) ¿Cuál es la probabilidad aproximada de decidir que la campaña publicitaria no fue efectiva, cuando en realidad la proporción de preferencia por la marca A después de la campaña es 0,2?
- d) ¿Qué tamaño muestral le parece apropiado para que la probabilidad de (c) fuese a lo sumo 0,05?

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

a) H₀: p = 0,1 vs. H₁: p > 0,1. Bajo H₀: $\sigma_{\hat p} = \sqrt{0{,}09/100} = 0{,}03$.

$z_{obs} = \frac{0{,}13 - 0{,}10}{0{,}03} = 1 < 1{,}645$ ⇒ no se rechaza H₀.

b) p = P(Z > 1) = 0,1587.

c) RC: $\hat p > 0{,}1 + 1{,}645\cdot0{,}03 = 0{,}149$. Con p = 0,2, $\sigma = \sqrt{0{,}16/100} = 0{,}04$:

$\beta = \Phi\left(\frac{0{,}149 - 0{,}2}{0{,}04}\right) = \Phi(-1{,}27) = 0{,}10$.

d) Para β ≤ 0,05 se igualan los dos valores críticos:

$n \ge \left(\frac{z_{0{,}95}\sqrt{p_0q_0} + z_{0{,}95}\sqrt{p_1q_1}}{p_1 - p_0}\right)^2 = \left(\frac{1{,}645\cdot0{,}3 + 1{,}645\cdot0{,}4}{0{,}1}\right)^2 = 132{,}6$.

Con esta fórmula alcanza con n ≥ 133. La guía da n ≥ 167, un criterio más conservador; cualquier n ≥ 167 cumple seguro.

</details>

**Respuesta:**

- a) No se rechaza H₀ ($z_{obs}$ = 1)
- b) p-valor = 0,1587
- c) $\beta_{0{,}2}$ = 0,1038
- d) n ≥ 167 según la guía (con la fórmula de arriba alcanza n ≥ 133)

</details>

---

### 18) ¿Qué máquina hizo las piezas? *(opcional)*

Las piezas producidas por dos máquinas se encuentran en el depósito de un taller mecánico. Se sabe que el diámetro de estas piezas es una variable aleatoria Normal con parámetros conocidos μ₁ = 10,2 mm y σ₁ = 0,45 mm para la máquina 1, y μ₂ = 10,4 mm y σ₂ = 0,5 mm para la máquina 2. Se ha recibido un trabajo que requiere de 2500 de estas piezas y se preparó el material de trabajo con todas las piezas producidas por una sola de estas dos máquinas, pero no se sabe cuál. Para decidir si es de una u otra, se realiza una prueba. Diseñar la prueba de tal manera que la probabilidad de decidir que las piezas corresponden a una máquina cuando en realidad no es así, a partir de los valores medios de las muestras, sea la misma para ambas máquinas.

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

H₀: μ = 10,2 (máquina 1) vs. H₁: μ = 10,4 (máquina 2). Se rechaza H₀ si $\bar X > c$.

Se pide α = β:

$P\left(Z > \frac{c - 10{,}2}{0{,}45/\sqrt n}\right) = P\left(Z < \frac{c - 10{,}4}{0{,}5/\sqrt n}\right)$

$\Rightarrow \frac{c - 10{,}2}{0{,}45} = \frac{10{,}4 - c}{0{,}5} \Rightarrow c = \frac{10{,}2\cdot0{,}5 + 10{,}4\cdot0{,}45}{0{,}95} = 10{,}29$ mm (no depende de n).

</details>

**Respuesta:** VC = 10,29: con H₀: μ = 10,2, se rechaza H₀ (se decide máquina 2) si $\bar x$ > 10,29.

</details>

---

### 19) Tiempo de secado de dos fórmulas

Un productor está interesado en reducir el tiempo de secado de una pintura impermeabilizante. Se prueban dos fórmulas de pintura: la fórmula A tiene el contenido químico tradicional, mientras que la fórmula B tiene un nuevo ingrediente que reduce el tiempo de secado. De la experiencia se sabe que la desviación estándar del tiempo de secado es de 8 minutos para ambas pinturas y que la distribución es normal. Se pintan diez especímenes con cada una de estas fórmulas, resultando las medias muestrales de 121 minutos y 112 minutos respectivamente.

- a) ¿A qué conclusión puede llegar el productor sobre la eficacia del nuevo ingrediente, considerando un nivel de significación del 5 %?
- b) Si la verdadera diferencia de tiempos promedio de secado fuera de 10 minutos, ¿cuál sería el tamaño muestral requerido (suponiendo ambas muestras del mismo tamaño) para detectar dicha diferencia con una probabilidad igual o mayor a 0,90?

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

a) H₀: μ_B − μ_A = 0 vs. H₁: μ_B − μ_A < 0 (B seca más rápido).

Varianzas conocidas: $Z = \frac{\bar X_B - \bar X_A}{8\sqrt{1/10 + 1/10}}$.

$z_{obs} = \frac{112 - 121}{3{,}578} = -2{,}52 < -1{,}645$ ⇒ se rechaza H₀.

b) Con α = 0,05 y potencia 0,90 (β = 0,10) para una diferencia δ = 10:

$n \ge \frac{2\sigma^2(z_{0{,}95} + z_{0{,}90})^2}{\delta^2} = \frac{2\cdot64\cdot(1{,}645 + 1{,}282)^2}{100} = 10{,}96$ ⇒ **n = 11** por grupo.

</details>

**Respuesta:**

- a) $z_{obs}$ = −2,52 < −1,65 ⇒ se rechaza H₀: hay evidencia al 5 % de la eficacia del nuevo ingrediente
- b) n ≥ 11 (en cada muestra)

</details>

---

### 20) Desarrollo psicomotriz *(opcional)*

En un estudio sobre el desarrollo psicomotriz de niños que cursan el preescolar se seleccionaron dos muestras aleatorias de 24 niños y 25 niñas de 5 años de edad. Entre otras pruebas se realizó un test que evalúa habilidades psicomotoras. Los investigadores estaban interesados en comparar las medias de los puntajes en las poblaciones de varones y mujeres de 5 años. En la guía se muestran los histogramas y boxplots de ambas muestras. Se sabe que la dispersión de los puntajes de este test en cualquier población es de 1,5 puntos y se pueden considerar normales.

- a) La media de los varones resultó 25,04 y la de las mujeres 26,40. Indicar si las diferencias de rendimiento pueden considerarse significativas al 5 %.
- b) ¿Se podría haber inferido lo mismo de la observación de los gráficos?

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

a) H₀: μ_V = μ_M vs. H₁: μ_V ≠ μ_M; σ = 1,5 conocido.

$z_{obs} = \frac{25{,}04 - 26{,}40}{1{,}5\sqrt{1/24 + 1/25}} = -3{,}17$; |−3,17| > 1,96 ⇒ se rechaza H₀ (p = 0,0015).

b) Los gráficos sugieren, pero no constituyen evidencia estadística: no cuantifican el error.

</details>

**Respuesta:**

- a) Sí, las diferencias son significativas al 5 % ($z_{obs}$ = −3,17)
- b) No, la observación de gráficos no constituye evidencia estadística

</details>

---

### 21) Medicamentos para la mastitis

En un laboratorio de especialidades medicinales están comparando la efectividad de dos medicamentos A y B para el tratamiento de la mastitis. Para ello se trataron dos grupos de vacas afectadas con síntomas similares. Se registró el tiempo en días que tardaron en desaparecer los síntomas en cada caso. Las distribuciones de estos tiempos son normales con varianza común:

| A | 5 | 7 | 6 | 7 | 7 | 8 | 6 | 8 | 7 | 6 |
|---|---|---|---|---|---|---|---|---|---|---|
| **B** | 7 | 9 | 10 | 8 | 6 | 5 | 7 | 9 | 9 | 5 |

- a) Plantear las hipótesis a contrastar, el estadístico del test junto con su función de distribución, la región de rechazo y la decisión tomada a nivel aproximado 0,05.
- b) ¿Cuál es el p-valor de la prueba?

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

Muestras: $\bar x_A = 6{,}7$, $s_A^2 = 0{,}9$; $\bar x_B = 7{,}5$, $s_B^2 = 3{,}17$.

a) H₀: μ_A = μ_B vs. H₁: μ_A ≠ μ_B.

$s_p^2 = \frac{9\cdot0{,}9 + 9\cdot3{,}17}{18} = 2{,}03$ ⇒ $s_p = 1{,}43$.

$T = \frac{\bar X_A - \bar X_B}{S_p\sqrt{1/n_A + 1/n_B}} \sim t_{18}$ ⇒ $t_{obs} = \frac{-0{,}8}{1{,}43\sqrt{0{,}2}} = -1{,}25$.

RC = {|T| > $t_{18;\,0{,}975}$ = 2,10}. Como |−1,25| < 2,10 ⇒ no se rechaza H₀.

b) p = 2·P(t₁₈ > 1,25) ≈ 0,227.

</details>

**Respuesta:**

- a) H₀: μ_A = μ_B vs. H₁: μ_A ≠ μ_B; $T \sim t_{18}$; $|T_{obs}|$ = 1,25 < 2,1 ⇒ no se rechaza H₀
- b) p-valor = 0,2273

</details>

---

### 22) Acabado superficial según dos técnicos

Dos técnicos de control de calidad miden el acabado de la superficie de una pieza metálica y obtienen los siguientes resultados:

- Técnico 1: 1,45 1,37 1,21 1,54 1,48 1,29 1,34
- Técnico 2: 1,55 1,43 1,58 1,37 1,29 1,34 1,28 1,65

| Técnico | media | sd | n |
|---|---|---|---|
| Técnico 1 | 1,383 | 0,115 | 7 |
| Técnico 2 | 1,436 | 0,141 | 8 |

Se pide:

- a) ¿Qué observa en el boxplot paralelo respecto de las posiciones centrales de los grupos?
- b) Se aplicó el test de normalidad de Shapiro-Wilks a ambas muestras, obteniéndose respectivamente los siguientes p valores: 0,966 y 0,368. Determinar si existe diferencia significativa entre los valores medios de las mediciones obtenidas con α = 0,05, sabiendo que las mediciones de ambos técnicos tienen igual dispersión.

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

a) La caja del técnico 2 está algo más arriba: su media parece mayor.

b) Shapiro-Wilks no rechaza la normalidad (p > 0,05) y las varianzas son iguales ⇒ test t con varianza amalgamada.

H₀: μ₁ = μ₂ vs. H₁: μ₁ ≠ μ₂.

$s_p = \sqrt{\frac{6\cdot0{,}115^2 + 7\cdot0{,}141^2}{13}} = 0{,}130$.

$t_{obs} = \frac{1{,}383 - 1{,}436}{0{,}130\sqrt{1/7 + 1/8}} = -0{,}80$.

|−0,80| < $t_{13;\,0{,}975}$ = 2,16 ⇒ no se rechaza H₀ (p = 0,44).

</details>

**Respuesta:**

- a) La media del técnico 2 parece superior a la del técnico 1
- b) No se rechaza H₀ ($t_{obs}$ = −0,80): no hay evidencia de diferencia entre las medias, a pesar de lo que sugiere el gráfico

</details>

---

### 23) Verdadero o falso sobre tests (T)

(T) Decidir si son verdaderas o falsas las siguientes afirmaciones y justificar adecuadamente cada respuesta.

- a) Si el p-valor para ciertas hipótesis estadísticas es igual a 0,08, indica que se rechaza la hipótesis nula a nivel 5 %.
- b) Al aplicar cualquier prueba de hipótesis se verifica que P(error tipo I) = 1 − P(error tipo II).
- c) Se denomina potencia de una prueba al riesgo que voluntariamente asume el investigador de equivocarse al rechazar la hipótesis de nulidad cuando en realidad esta es cierta.
- d) Si se realiza dos veces un ensayo de hipótesis, la conclusión será la misma en ambos casos, independientemente de la muestra seleccionada.
- e) El nivel de significación de un test es la probabilidad de que la hipótesis nula sea cierta.
- f) Si el p-valor es 0,3, el test correspondiente no rechaza al nivel 0,01.
- g) Si un intervalo de confianza de nivel 0,99 para la media poblacional de una distribución Normal, calculado a partir de una muestra, da como resultado [−2, 3], entonces el test para las hipótesis H₀: μ = −3 vs. H₁: μ ≠ −3 basado en los mismos datos no rechazaría la hipótesis de nulidad con nivel 0,01.

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

a) **F.** 0,08 > 0,05 ⇒ no se rechaza.

b) **F.** α y β no son complementarios: se calculan bajo hipótesis distintas. 1 − β es la potencia.

c) **F.** Eso es α (nivel de significación). La potencia es 1 − β = P(rechazar H₀ | H₀ falsa).

d) **F.** La decisión depende de la muestra (el estadístico es una v.a.).

e) **F.** α = P(rechazar H₀ | H₀ verdadera); no es una probabilidad sobre H₀.

f) **V.** 0,3 > 0,01 ⇒ no se rechaza.

g) **F.** El test bilateral de nivel α no rechaza exactamente los μ₀ que están dentro del IC de nivel 1 − α. −3 ∉ [−2; 3] ⇒ **se rechaza**.

</details>

**Respuesta:** a) F · b) F · c) F · d) F · e) F · f) V · g) F

</details>

---

### 24) Frenos de autos viejos y nuevos

Una muestra aleatoria de 250 automóviles que circulan por la ciudad y que tienen 10 años o más de uso indica que 98 de ellos no pasan un chequeo básico de su sistema de frenos, mientras que en una muestra de 300 autos con menos de 10 años de antigüedad, 79 no pasan un chequeo básico de su sistema de frenos.

- a) ¿Existe evidencia significativa, al nivel 1 %, de que la proporción de autos con desgaste en su sistema de frenos de 10 o más años de uso es mayor que esta proporción en autos con menos de 10 años de uso?
- b) Hallar el valor p de la prueba e interpretarlo.
- c) ¿El nivel de esta prueba es exacto o asintótico?

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

$\hat p_1 = 98/250 = 0{,}392$ (10 años o más) y $\hat p_2 = 79/300 = 0{,}263$.

a) H₀: p₁ − p₂ = 0 vs. H₁: p₁ − p₂ > 0.

Bajo H₀ se usa la proporción combinada $\hat p = \frac{98 + 79}{550} = 0{,}322$:

$z_{obs} = \frac{0{,}392 - 0{,}263}{\sqrt{0{,}322\cdot0{,}678\left(\frac1{250} + \frac1{300}\right)}} = 3{,}22 > z_{0{,}99} = 2{,}33$ ⇒ se rechaza H₀.

b) p = P(Z > 3,22) ≈ 0,0006 (la guía informa 0,0012). Si las proporciones fueran iguales, sería muy improbable observar una diferencia tan grande.

c) Asintótico: se usa la aproximación normal (TCL).

</details>

**Respuesta:**

- a) Sí, hay evidencia al 1 % ($z_{obs}$ ≈ 3,22)
- b) Valor p ≈ 0,001 (la guía da 0,0012)
- c) Aproximado o asintótico

</details>

---

[← Volver al menú principal](../README.md)
