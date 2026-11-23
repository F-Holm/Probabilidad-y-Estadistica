# 2.º Parcial — Tema 1 (08/07/2026)

Probabilidad y Estadística — UTN FRBA. Enunciado original: [MODELO 2°PARCIAL.pdf](Fotos/MODELO%202%C2%B0PARCIAL.pdf) (página 1).

> **Aprobación:** al menos 2 de los primeros 4 puntos correctamente resueltos.
> **Promoción:** aprobación + al menos 2 de los últimos 4 puntos bien resueltos. Los puntos IV y V sólo se corrigen si se alcanza la aprobación.

Cada ejercicio tiene un botón **Solución**. Al abrirlo aparece la respuesta y, arriba de ella, el botón **Solución paso a paso**.

---

### I) Azúcar convertida según la temperatura

Se realizó un estudio sobre la cantidad de azúcar convertida en cierto proceso a distintas temperaturas. Los datos se codificaron y se obtuvo lo siguiente:

| Temp (x) | 1,1 | 1,2 | 1,3 | 1,4 | 1,5 | 1,6 | 1,7 | 1,8 | 1,9 |
|---|---|---|---|---|---|---|---|---|---|
| **Azúcar (y)** | 7,8 | 8,5 | 9,8 | 9,5 | 8,9 | 8,6 | 10,2 | 9,3 | 9,2 |

Analizar con un nivel de significación del 1 % la pertinencia del modelo de regresión lineal simple para explicar la cantidad de azúcar a partir de la temperatura. Si el modelo ajusta correctamente, determinar la cantidad media de azúcar si la temperatura es 1,65. Justificar.

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

💡 **Regresión lineal:** se busca una recta $\hat y = b_0 + b_1x$ (📄 H2) para predecir el azúcar (Y) a partir de la temperatura (X): la que pasa más cerca de los puntos (mínimos cuadrados). **El orden importa:** primero se ve si el modelo sirve (test), y recién después se usa.

**Sumas** (n = 9): $\sum x = 13{,}5$, $\sum y = 81{,}8$, $\sum x^2 = 20{,}85$, $\sum y^2 = 747{,}72$, $\sum xy = 123{,}49$. (Calculadora de estadística → Regresión lineal o Regresión con suma.)

**Cantidades básicas** (📄 H2, $S_{xx} = \sum x^2 - \frac{(\sum x)^2}{n}$, etc.): $\bar x = 1{,}5$ y $\bar y = 9{,}0889$.
- $S_{xx} = 20{,}85 - \frac{13{,}5^2}9 = 0{,}6$
- $S_{yy} = 747{,}72 - \frac{81{,}8^2}9 = 4{,}2489$
- $S_{xy} = 123{,}49 - \frac{13{,}5\cdot81{,}8}9 = 0{,}79$

**Recta estimada** (📄 H2, $b_1 = \frac{S_{xy}}{S_{xx}}$ y $`b_0 = \bar y - b_1\bar x`$): $b_1 = \frac{0{,}79}{0{,}6} = 1{,}3167$ y $b_0 = 9{,}0889 - 1{,}3167\cdot1{,}5 = 7{,}1139$, así que $\hat y = 7{,}114 + 1{,}317x$.

💡 **¿El modelo es pertinente? Test de correlación.** El **coeficiente de correlación r** (📄 H2, $`r = \frac{S_{xy}}{\sqrt{S_{xx}S_{yy}}}`$) mide qué tan alineados están los puntos (de −1 a 1). El test decide si la correlación de **toda la población**, ρ, es distinta de 0, o si el alineamiento de la muestra pudo ser casualidad.

**Supuestos** (❌): errores normales, independientes y con la misma varianza (homocedásticos).

1. H₀: ρ = 0 (no hay relación lineal) vs. H₁: ρ ≠ 0. Lo que se quiere mostrar va en H₁.
2. α = 0,01.
3. Estadístico (📄 H2, $`\sqrt{n-2}\frac{r}{\sqrt{1-r^2}} = t_{n-2}`$): $T \sim t_7$ si H₀ es cierta.
4. $r = \frac{0{,}79}{\sqrt{0{,}6\cdot4{,}2489}} = 0{,}4948$ ($`R^2 = 0{,}245`$), así que $t_{obs} = \sqrt7\cdot\frac{0{,}4948}{\sqrt{1 - 0{,}2448}} = 1{,}506$.
5. Bilateral, α/2 = 0,005 en cada cola:
   ```
   X~t(ν)   ν=7   P(X<x)=0.995   → x=3.49948
   X~t(ν)   ν=7   P(X>x)   x=1.506   → 0.0878   → p = 0.176
   ```
   1,506 < 3,4995: **no se rechaza H₀**.

**Conclusión:** no hay evidencia de correlación lineal, así que el modelo **no es pertinente**. Mirando los datos, el azúcar sube y baja sin un patrón claro (R² de apenas 0,245).

**La trampa de la consigna:** dice "**si** el modelo ajusta". Como **no** ajusta, no corresponde usar la recta en x = 1,65 (daría 9,29). La mejor estimación de la cantidad media de azúcar es el promedio de los y, $\bar y = 9{,}09$, sin depender de la temperatura. Hay que justificarlo con el test.

</details>

**Respuesta:** $t_{obs}$ = 1,506 < 3,4995 ⇒ no se rechaza ρ = 0 al 1 %. El modelo lineal no es pertinente, así que no se estima con la recta en x = 1,65 (la media de azúcar se estima con $\bar y$ ≈ 9,09).

</details>

---

### II) Consumo de combustible

Se toma una muestra de consumo de combustible en un cierto modelo de coche, obteniéndose los siguientes datos (expresados en litros cada 100 km):

6,7 − 7,2 − 7,3 − 7,0 − 7,1 − 6,9 − 7,3 − 7,1 − 6,9 − 6,8

- a) Suponiendo que el consumo sigue una distribución normal, estimar mediante un intervalo de confianza al 98 % la **varianza** del consumo.
- b) Suponiendo que el desvío poblacional del consumo de combustible en el modelo de coche considerado es de 0,17 litros/100 km, ¿de qué tamaño debería ser la muestra para que el error máximo de estimación (d) en un intervalo de confianza para la media al 99 % sea de a lo sumo 0,05 litros/100 km?

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

**a)** 💡 **Intervalo de confianza:** un rango que contiene al valor verdadero de la población (acá, la varianza σ² del consumo) con una confianza dada (98 %).

**Datos.** Calculadora de estadística → **Estadística descriptiva** con los 10 valores: n = 10, $\bar x = 7{,}03$, $s^2 = 0{,}04233$ (s = 0,2058). La varianza muestral divide por n − 1.

💡 **Por qué se usa la χ².** La varianza muestral S² no es Normal (nunca es negativa y es asimétrica). Si la población es Normal (por eso la consigna lo supone), $\frac{(n-1)S^2}{\sigma^2} \sim \chi^2_{n-1}$ (📄 H2). De ahí sale el intervalo (📄 H2):

$`\displaystyle I.C._{\sigma^2} = \left(\frac{(n-1)S^2}{\chi^2_{n-1;1-\frac\alpha2}};\ \frac{(n-1)S^2}{\chi^2_{n-1;\frac\alpha2}}\right)`$

Hacen falta dos valores de χ² (uno por cola), y el **grande** va en la punta izquierda.

Con 1 − α = 0,98, α/2 = 0,01 y 9 grados de libertad:
```
X~χ²(ν)   ν=9   P(X<x)=0.99   → x=21.666
X~χ²(ν)   ν=9   P(X<x)=0.01   → x=2.0879
```

$$I.C._{\sigma^2} = \left(\frac{9\cdot0{,}04233}{21{,}666};\ \frac{9\cdot0{,}04233}{2{,}088}\right) = (0{,}0176;\ 0{,}1825) \text{ (l/100 km)}^2$$

**b)** Ahora el IC es **para la media**, con σ = 0,17 **conocido**. 💡 La fórmula de la hoja (📄 H2) es "promedio ± margen", $\bar X \mp z_{1-\frac\alpha2}\frac{\sigma}{\sqrt n}$. El margen es el **error máximo de estimación**:

$$d = z_{1-\frac\alpha2}\cdot\frac{\sigma}{\sqrt n}$$

(Sale de que el promedio varía alrededor de μ con desvío $\frac{\sigma}{\sqrt n}$.)

✍️ Se pide d ≤ 0,05 y se despeja n (❌, despeje):
```
X~N(μ;σ)   μ=0   σ=1   P(X<x)=0.995   → x=2.57583
```

$$2{,}576\cdot\frac{0{,}17}{\sqrt n} \le 0{,}05 \;\Rightarrow\; n \ge \left(\frac{2{,}576\cdot0{,}17}{0{,}05}\right)^2 = 76{,}7 \;\Rightarrow\; n = 77$$

Siempre se redondea hacia arriba: con 76 el error quedaría apenas mayor que 0,05.

</details>

**Respuesta:**

- a) $IC_{98}(\sigma^2) = [0{,}0176;\ 0{,}1825]$
- b) n ≥ 77

</details>

---

### III) Comparación de estimadores

Sea X ~ N(μ; σ) y sea {X₁; X₂; X₃; X₄} una muestra aleatoria de X. Probar que $\hat\mu_a = \dfrac{X_1 + X_2}2$ es mejor estimador de la media que $\hat\mu_b = \dfrac{2X_1 + 3X_4}5$. Justificar.

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

💡 **Qué es un estimador:** una fórmula con los datos de la muestra para "adivinar" un parámetro desconocido (acá, la media μ). Hay que decidir cuál de los dos adivina mejor.

💡 **Qué significa "mejor".** El estimador cambia con la muestra, así que es una variable aleatoria. Se le pide:
1. que no apunte corrido: $E(\hat\mu) = \mu$ (**insesgado**). La diferencia $E(\hat\mu) - \mu$ es el **sesgo** (❌);
2. que no se disperse mucho: varianza chica.

Las dos cosas se juntan en el **error cuadrático medio**, $ECM = V(\hat\theta) + (\text{sesgo})^2$ (📄 H2). Gana el de menor ECM.

**Datos:** como es una muestra aleatoria, las $X_i$ son independientes, con $E(X_i) = \mu$ y $V(X_i) = \sigma^2$.

**Sesgo** (linealidad de la esperanza, ❌):
- $E(\hat\mu_a) = \frac{\mu + \mu}{2} = \mu$: insesgado.
- $E(\hat\mu_b) = \frac{2\mu + 3\mu}{5} = \mu$: insesgado. (Truco: si los coeficientes suman 1, es insesgado.)

**Varianza.** Los coeficientes salen **al cuadrado**, y por independencia no hay covarianza (📄 H1, $V(aX + bY) = a^2V(X) + b^2V(Y) + 2ab\,Cov$ con Cov = 0):
- $V(\hat\mu_a) = \frac14(\sigma^2 + \sigma^2) = \frac{\sigma^2}2 = 0{,}5\,\sigma^2$
- $V(\hat\mu_b) = \frac{4\sigma^2 + 9\sigma^2}{25} = \frac{13}{25}\sigma^2 = 0{,}52\,\sigma^2$

Los dos son insesgados, así que su ECM es su varianza. Como $V(\hat\mu_a) < V(\hat\mu_b)$, $\hat\mu_a$ es **más eficiente** (menor ECM).

</details>

**Respuesta:** Ambos son insesgados, pero $V(\hat\mu_a) = 0{,}5\sigma^2 < V(\hat\mu_b) = 0{,}52\sigma^2$ ⇒ $\hat\mu_a$ es mejor (más eficiente, menor ECM).

</details>

---

### IV) Óxidos de azufre

Se tomó una muestra aleatoria de 10 observaciones de óxidos de azufre (SO₂), en ppm, provenientes de una fundición, la que arrojó una media de 57,41 ppm con un desvío de 0,94 ppm.

- a) Con los datos proporcionados y un α = 0,01, ¿podría avalarse la hipótesis de que el valor medio de óxido de azufre (en ppm) está por debajo de 58? Establecer los supuestos necesarios.
- b) ¿Con qué niveles de significación podría rechazar la hipótesis que dice que μ = 58?

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

💡 **Test de hipótesis, como un juicio.**
- **H₀** es "el inocente": se da por cierta salvo evidencia fuerte, y lleva la igualdad.
- **H₁** es lo que se quiere demostrar: una desigualdad estricta.
- Si la muestra es contundente, se rechaza H₀.

**Supuestos** (los piden): la concentración de SO₂ tiene distribución **normal** y las observaciones son independientes (muestra aleatoria). σ es desconocido (0,94 es de la muestra) y n = 10 es chico, así que se usa la **t de Student**, que **exige** normalidad.

**a)**
1. **Hipótesis.** "Avalar que está por debajo de 58" es lo que se quiere demostrar, así que va en H₁:

   $`\displaystyle H_0: \mu \ge 58 \qquad H_1: \mu < 58`$

2. α = 0,01, el riesgo aceptado de rechazar H₀ siendo cierta.
3. 💡 **Estadístico:** a cuántos "errores estándar" cayó el promedio de 58. Con S en lugar de σ, es una **t** con n − 1 grados de libertad (📄 H2, tal cual):

   $$T = \frac{\bar X - 58}{S/\sqrt n} \sim t_9$$

4. $t_{obs} = \frac{57{,}41 - 58}{0{,}94/\sqrt{10}} = \frac{-0{,}59}{0{,}2973} = -1{,}985$.
5. 💡 **Región crítica:** los valores que llevan a rechazar, del lado de H₁ (izquierda), con área α:
   ```
   X~t(ν)   ν=9   P(X<x)=0.01   → x=−2.82144
   ```
   RC = {T < −2,821}. −1,985 **no** es menor que −2,821, así que **no se rechaza H₀**. Al 1 % no hay evidencia suficiente para afirmar que μ < 58.

**b)** 💡 **Valor p:** la probabilidad, si H₀ fuera cierta, de un resultado tan extremo o más que el observado. Se rechaza si p < α, así que "¿con qué α se rechaza?" se contesta con **cualquier α mayor que p**.
```
X~t(ν)   ν=9   P(X<x)   x=−1.985   → 0.0392
```
Se rechaza con cualquier α ≥ 0,039 (por ejemplo, 0,05 o 0,10), pero no con 0,01.

Si la alternativa fuera bilateral (μ ≠ 58), el p se duplica: 0,078.

**Control:** Calculadora de estadística → **Prueba T una media**.

</details>

**Respuesta:**

- a) $t_{obs}$ = −1,985 > −2,821 ⇒ no se rechaza H₀: al 1 % no se puede avalar que μ < 58 (suponiendo normalidad y m.a.)
- b) Con α ≥ 0,039 (valor p unilateral)

</details>

---

### V) Meditación trascendental

En el boletín de la Asociación Americana del Corazón, *Hypertension*, investigadores reportan que los individuos que practican la meditación trascendental (MT) bajan su presión sanguínea de manera significativa. Una muestra aleatoria de 36 personas practicantes de MT meditan, en promedio, 8,8 horas a la semana. Suponer que el desvío poblacional es de 2,4 horas.

- a) ¿Esto sugiere que, en promedio, las personas que hacen MT utilizan más de 8 horas por semana? Usar un nivel de significación del 5 %.
- b) Calcular la probabilidad de aceptar que las personas que practican MT lo hacen en promedio más de 8 h semanales cuando el tiempo medio verdadero es de 10 h.

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

**La pregunta es de sí o no:** ¿la media de **todos** los practicantes supera 8 h? La muestra dio 8,8, pero ¿es lo bastante mayor, o pudo salir así por casualidad?

💡 **Test de hipótesis, como un juicio:** H₀ (lleva la igualdad) se da por cierta salvo evidencia fuerte en contra. H₁ es lo que se quiere demostrar.

💡 **Cuánto varía el promedio.** El promedio de 36 personas varía con desvío $\frac{\sigma}{\sqrt n} = \frac{2{,}4}{6} = 0{,}4$ (📄 H2, $`\bar X \sim N(\mu;\ \sigma/\sqrt n)`$). σ = 2,4 es conocido ("desvío poblacional").

**a)**
1. Se quiere demostrar "más de 8":

   $`\displaystyle H_0: \mu \le 8 \qquad H_1: \mu > 8`$

2. α = 0,05, el riesgo aceptado de rechazar H₀ siendo cierta.
3. 💡 **Estadístico:** a cuántos desvíos de 8 cayó el promedio. Se estandariza (📄 H1):

   $$Z = \frac{\bar X - 8}{0{,}4} \sim N(0;1) \text{ si } \mu = 8$$

4. $z_{obs} = \frac{8{,}8 - 8}{0{,}4} = 2$.
5. 💡 **Región crítica:** del lado de H₁ (derecha), con área α:
   ```
   X~N(μ;σ)   μ=0   σ=1   P(X<x)=0.95   → x=1.64485
   ```
   RC = {Z > 1,645}; en horas, $\bar X > 8 + 1{,}645\cdot0{,}4 = 8{,}658$. Como 2 > 1,645, **se rechaza H₀**.

💡 **Valor p** (la probabilidad de algo tan extremo si H₀ fuera cierta): `X~N(μ;σ) μ=0 σ=1 P(X>x) x=2 → 0.02275`. p = 0,0228 < 0,05 ✓.

**Conclusión:** hay evidencia al 5 % de que meditan en promedio más de 8 h semanales.

**b)** **Leer bien:** "aceptar que meditan más de 8 h" es **rechazar H₀**. Si μ es en realidad 10, H₀ es falsa y rechazarla es **acertar**.

💡 **Errores y potencia:**
- **Error tipo II (β):** no rechazar H₀ siendo falsa.
- **Potencia = 1 − β:** la probabilidad de rechazar cuando H₀ es falsa. Es lo que se pide.

**Receta** (❌): la frontera se arma con el μ de H₀ (ya está: 8,658), y la probabilidad se calcula con el μ verdadero (10):
```
X~N(μ;σ)   μ=10   σ=0.4   P(X>x)   x=8.658   → 0.9996
```
**1 − β ≈ 0,9996.** Si meditan 10 h, el test casi siempre lo detecta, porque 10 está muy lejos de 8.

</details>

**Respuesta:**

- a) $z_{obs}$ = 2 > 1,645 ⇒ se rechaza H₀: hay evidencia al 5 % de que meditan más de 8 h semanales
- b) 1 − β ≈ 0,9996

</details>

---

[← Volver al menú principal](../../README.md)
