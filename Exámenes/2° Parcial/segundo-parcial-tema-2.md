# 2.º Parcial — Tema 2 (08/07/2026)

Probabilidad y Estadística — UTN FRBA. Enunciado original: [MODELO 2°PARCIAL.pdf](Fotos/MODELO%202%C2%B0PARCIAL.pdf) (página 2).

> **Aprobación:** al menos 2 de los primeros 4 puntos correctamente resueltos.
> **Promoción:** aprobación + al menos 2 de los últimos 4 puntos bien resueltos. Los puntos IV y V sólo se corrigen si se alcanza la aprobación.

Cada ejercicio tiene un botón **Solución**. Al abrirlo aparece la respuesta y, arriba de ella, el botón **Solución paso a paso**.

---

### I) Azúcar convertida según la temperatura

Se realizó un estudio sobre la cantidad de azúcar convertida en cierto proceso a distintas temperaturas. Los datos se codificaron y se obtuvo lo siguiente:

| Temp (x) | 1,1 | 1,2 | 1,3 | 1,4 | 1,5 | 1,6 | 1,7 | 1,8 | 1,9 |
|---|---|---|---|---|---|---|---|---|---|
| **Azúcar (y)** | 7,8 | 8,5 | 9,8 | 9,5 | 8,9 | 8,6 | 10,2 | 9,3 | 9,2 |

Analizar con un nivel de significación del 10 % la pertinencia del modelo de regresión lineal simple para explicar la cantidad de azúcar a partir de la temperatura. Si el modelo ajusta correctamente, determinar la cantidad media de azúcar si la temperatura es 1,35. Justificar.

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

💡 **Regresión lineal:** se busca una recta $\hat y = b_0 + b_1x$ (📄 H2) para predecir el azúcar (Y) a partir de la temperatura (X): la que pasa más cerca de los puntos (mínimos cuadrados). **El orden importa:** primero se ve si el modelo sirve (test), y recién después se usa.

**Sumas** (n = 9): $\sum x = 13{,}5$, $\sum y = 81{,}8$, $\sum x^2 = 20{,}85$, $\sum y^2 = 747{,}72$, $\sum xy = 123{,}49$. (Calculadora de estadística → Regresión lineal o Regresión con suma.)

**Cantidades básicas** (📄 H2, $S_{xx} = \sum x^2 - \frac{(\sum x)^2}{n}$, etc.): $\bar x = 1{,}5$, $\bar y = 9{,}0889$, $S_{xx} = 0{,}6$, $S_{yy} = 4{,}2489$, $S_{xy} = 0{,}79$.

**Recta estimada** (📄 H2, $b_1 = S_{xy}/S_{xx}$ y $`b_0 = \bar y - b_1\bar x`$): $b_1 = 1{,}3167$ y $b_0 = 7{,}1139$, así que $\hat y = 7{,}114 + 1{,}317x$.

💡 **¿El modelo es pertinente? Test de correlación.** El **coeficiente de correlación r** (📄 H2, $`r = \frac{S_{xy}}{\sqrt{S_{xx}S_{yy}}}`$) mide qué tan alineados están los puntos (de −1 a 1). El test decide si la correlación de la población, ρ, es distinta de 0, o si el alineamiento pudo ser casualidad.

**Supuestos** (❌): errores normales, independientes y con la misma varianza (homocedásticos).

1. H₀: ρ = 0 vs. H₁: ρ ≠ 0.
2. α = 0,10.
3. Estadístico (📄 H2, $`\sqrt{n-2}\frac{r}{\sqrt{1-r^2}} = t_{n-2}`$): $T \sim t_7$ si H₀ es cierta.
4. $r = \frac{0{,}79}{\sqrt{0{,}6\cdot4{,}2489}} = 0{,}4948$ ($`R^2 = 0{,}245`$), así que $t_{obs} = \sqrt7\cdot\frac{0{,}4948}{\sqrt{1 - 0{,}2448}} = 1{,}506$.
5. Bilateral con α = 0,10: 0,05 en cada cola.
   ```
   X~t(ν)   ν=7   P(X<x)=0.95   → x=1.89458
   X~t(ν)   ν=7   P(X>x)   x=1.506   → 0.0878   → p = 0.176
   ```
   1,506 < 1,895 (p = 0,176 > 0,10): **no se rechaza H₀**.

**Conclusión:** aun con un α tan permisivo (10 %), el modelo lineal **no es pertinente**.

**La trampa de la consigna:** dice "**si** el modelo ajusta". Como no ajusta, no corresponde estimar con la recta en x = 1,35 (daría 8,89). La media de azúcar se estima con el promedio de los y, $\bar y = 9{,}09$, y hay que justificarlo con el test.

</details>

**Respuesta:** $t_{obs}$ = 1,506 < 1,895 ⇒ no se rechaza ρ = 0 al 10 %. El modelo lineal no es pertinente, así que no se estima con la recta en x = 1,35 (la media de azúcar se estima con $\bar y$ ≈ 9,09).

</details>

---

### II) Consumo de combustible

Se toma una muestra de consumo de combustible en un cierto modelo de coche, obteniéndose los siguientes datos (expresados en litros cada 100 km):

6,7 − 7,2 − 7,3 − 7,0 − 7,1 − 6,9 − 7,3 − 7,1 − 6,9 − 6,8

- a) Suponiendo que el consumo sigue una distribución normal, estimar mediante un intervalo de confianza al 90 % el **desvío** del consumo.
- b) Suponiendo que el desvío poblacional del consumo de combustible en el modelo de coche considerado es de 0,15 litros/100 km, ¿de qué tamaño debería ser la muestra para que el error máximo de estimación (d) en un intervalo de confianza para la media al 95 % sea de a lo sumo 0,08 litros/100 km?

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

**a)** 💡 **Intervalo de confianza:** un rango que contiene al valor verdadero de la población (acá, el **desvío** σ del consumo) con una confianza dada (90 %).

**Datos.** Calculadora de estadística → **Estadística descriptiva** con los 10 valores: n = 10, $\bar x = 7{,}03$, $s^2 = 0{,}04233$ (s = 0,2058).

💡 **Por qué se usa la χ².** La varianza muestral no es Normal. Si la población es Normal, $\frac{(n-1)S^2}{\sigma^2} \sim \chi^2_{n-1}$ (📄 H2). De ahí sale el intervalo para la **varianza** (📄 H2):

```math
I.C._{\sigma^2} = \left(\frac{(n-1)S^2}{\chi^2_{n-1;1-\frac\alpha2}};\ \frac{(n-1)S^2}{\chi^2_{n-1;\frac\alpha2}}\right)
```

⚠️ Piden el **desvío**: al final se saca **raíz** a las dos puntas (❌, la hoja solo trae σ²).

Con 1 − α = 0,90, α/2 = 0,05 y 9 grados de libertad:
```
X~χ²(ν)   ν=9   P(X<x)=0.95   → x=16.919
X~χ²(ν)   ν=9   P(X<x)=0.05   → x=3.3251
```

```math
I.C._{\sigma^2} = \left(\frac{9\cdot0{,}04233}{16{,}919};\ \frac{9\cdot0{,}04233}{3{,}325}\right) = (0{,}02252;\ 0{,}11458)
```

```math
I.C._\sigma = (\sqrt{0{,}02252};\ \sqrt{0{,}11458}) = (0{,}150;\ 0{,}339) \text{ l/100 km}
```

**b)** IC **para la media** con σ = 0,15 **conocido**. 💡 La fórmula (📄 H2) es "promedio ± margen", $\bar X \mp z_{1-\frac\alpha2}\frac{\sigma}{\sqrt n}$, y el margen es el **error máximo**, $d = z\cdot\frac{\sigma}{\sqrt n}$.

✍️ Se pide d ≤ 0,08 y se despeja n (❌):
```
X~N(μ;σ)   μ=0   σ=1   P(X<x)=0.975   → x=1.95996
```

```math
1{,}96\cdot\frac{0{,}15}{\sqrt n} \le 0{,}08 \;\Rightarrow\; n \ge \left(\frac{1{,}96\cdot0{,}15}{0{,}08}\right)^2 = 13{,}5 \;\Rightarrow\; n = 14
```

Siempre se redondea hacia arriba.

</details>

**Respuesta:**

- a) $IC_{90}(\sigma) = [0{,}150;\ 0{,}339]$ litros/100 km
- b) n ≥ 14

</details>

---

### III) Comparación de estimadores

Sea X ~ N(μ; σ) y sea {X₁; X₂; X₃; X₄} una muestra aleatoria de X. Probar que $\hat\mu_a = \dfrac{X_1 + X_3}2$ es mejor estimador de la media que $\hat\mu_b = \dfrac{3X_1 + 5X_4}8$. Justificar.

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

💡 **Qué es un estimador:** una fórmula con los datos de la muestra para "adivinar" un parámetro desconocido (acá, la media μ). Es una variable aleatoria, porque cambia con la muestra.

💡 **Qué significa "mejor":**
1. que no apunte corrido, $E(\hat\mu) = \mu$ (**insesgado**). El **sesgo** es $E(\hat\mu) - \mu$ (❌);
2. que no se disperse mucho (varianza chica).

Las dos cosas se juntan en el **error cuadrático medio**, $ECM = V(\hat\theta) + (\text{sesgo})^2$ (📄 H2). Gana el de menor ECM.

**Datos:** como es una muestra aleatoria, las $X_i$ son independientes, con $E(X_i) = \mu$ y $V(X_i) = \sigma^2$.

**Sesgo** (linealidad, ❌):
- $E(\hat\mu_a) = \frac{\mu + \mu}{2} = \mu$: insesgado.
- $E(\hat\mu_b) = \frac{3\mu + 5\mu}{8} = \mu$: insesgado (los coeficientes suman 1).

**Varianza.** Los coeficientes salen **al cuadrado**, sin covarianza por independencia (📄 H1, $V(aX + bY) = a^2V(X) + b^2V(Y) + 2ab\,Cov$ con Cov = 0):
- $V(\hat\mu_a) = \frac14\cdot2\sigma^2 = \frac{\sigma^2}2 = 0{,}5\,\sigma^2$
- $V(\hat\mu_b) = \frac{9\sigma^2 + 25\sigma^2}{64} = \frac{34}{64}\sigma^2 = 0{,}531\,\sigma^2$

Los dos son insesgados (ECM = V), y $V(\hat\mu_a) < V(\hat\mu_b)$ ⇒ $\hat\mu_a$ es más eficiente.

</details>

**Respuesta:** Ambos son insesgados, pero $V(\hat\mu_a) = 0{,}5\sigma^2 < V(\hat\mu_b) = \frac{17}{32}\sigma^2 \approx 0{,}531\sigma^2$ ⇒ $\hat\mu_a$ es mejor (más eficiente, menor ECM).

</details>

---

### IV) Óxidos de azufre

Se tomó una muestra aleatoria de 10 observaciones de óxidos de azufre (SO₂), en ppm, provenientes de una fundición, la que arrojó una media de 56,84 ppm con un desvío de 0,94 ppm.

- a) Con los datos proporcionados y un α = 0,05, ¿podría avalarse la hipótesis de que el valor medio de óxido de azufre (en ppm) está por debajo de 58? Establecer los supuestos necesarios.
- b) ¿Con qué niveles de significación podría rechazar la hipótesis que dice que μ = 58?

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

💡 **Test de hipótesis, como un juicio:** H₀ (con la igualdad) se da por cierta salvo evidencia fuerte; H₁ es lo que se quiere demostrar. Si la muestra es contundente, se rechaza H₀.

**Supuestos** (los piden): población **normal** y muestra aleatoria (observaciones independientes). σ es desconocido (0,94 es de la muestra) y n = 10 es chico, así que se usa la **t de Student** con 9 grados de libertad, que exige normalidad.

**a)**
1. **Hipótesis.** "Avalar que está por debajo de 58" va en H₁:

   ```math
   H_0: \mu \ge 58 \qquad H_1: \mu < 58
   ```

2. α = 0,05.
3. 💡 **Estadístico:** a cuántos errores estándar cayó el promedio de 58. Con S en lugar de σ, es una t (📄 H2, tal cual):

   ```math
   T = \frac{\bar X - 58}{S/\sqrt n} \sim t_9
   ```

4. $t_{obs} = \frac{56{,}84 - 58}{0{,}94/\sqrt{10}} = \frac{-1{,}16}{0{,}2973} = -3{,}902$.
5. 💡 **Región crítica**, del lado de H₁ (izquierda), con área α:
   ```
   X~t(ν)   ν=9   P(X<x)=0.05   → x=−1.83311
   ```
   −3,902 < −1,833: **se rechaza H₀**. Hay evidencia al 5 % de que la media de SO₂ está por debajo de 58.

**b)** 💡 **Valor p:** la probabilidad, si H₀ fuera cierta, de algo tan extremo o más. Se rechaza con cualquier α mayor que p.
```
X~t(ν)   ν=9   P(X<x)   x=−3.902   → 0.0018
```
Se rechaza con cualquier α ≥ 0,0018, incluso con α = 0,01.

Si la alternativa fuera bilateral, el p se duplica: 0,0036.

</details>

**Respuesta:**

- a) $t_{obs}$ = −3,90 < −1,833 ⇒ se rechaza H₀: hay evidencia al 5 % de que μ < 58 (suponiendo normalidad y m.a.)
- b) Con α ≥ 0,0018 (valor p unilateral)

</details>

---

### V) Meditación trascendental

En el boletín de la Asociación Americana del Corazón, *Hypertension*, investigadores reportan que los individuos que practican la meditación trascendental (MT) bajan su presión sanguínea de manera significativa. Una muestra aleatoria de 36 personas practicantes de MT meditan, en promedio, 9,2 horas a la semana. Suponer que el desvío poblacional es de 2,4 horas.

- a) ¿Esto sugiere que, en promedio, las personas que hacen MT utilizan más de 8 horas por semana? Usar un nivel de significación del 1 %.
- b) Calcular la probabilidad de aceptar que las personas que practican MT lo hacen en promedio más de 8 h semanales cuando el tiempo medio verdadero es de 9 h.

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

**La pregunta es de sí o no:** ¿la media de **todos** los practicantes supera 8 h? La muestra dio 9,2, pero ¿es lo bastante mayor, o pudo ser casualidad?

💡 **Test de hipótesis, como un juicio:** H₀ (con la igualdad) se da por cierta salvo evidencia fuerte; H₁ es lo que se quiere demostrar.

💡 **Cuánto varía el promedio.** Desvío $\frac{\sigma}{\sqrt n} = \frac{2{,}4}{\sqrt{36}} = 0{,}4$ (📄 H2, $\bar X \sim N(\mu;\ \sigma/\sqrt n)$; σ es conocido, "desvío poblacional").

**a)**
1. $$H_0: \mu \le 8 \qquad H_1: \mu > 8$$
2. α = 0,01.
3. 💡 **Estadístico:** a cuántos desvíos de 8 cayó el promedio, estandarizando (📄 H1):

   ```math
   Z = \frac{\bar X - 8}{0{,}4} \sim N(0;1)
   ```

4. $z_{obs} = \frac{9{,}2 - 8}{0{,}4} = 3$.
5. 💡 **Región crítica**, del lado de H₁ (derecha), con área α = 0,01:
   ```
   X~N(μ;σ)   μ=0   σ=1   P(X<x)=0.99   → x=2.32635
   ```
   RC = {Z > 2,326}; en horas, $\bar X > 8 + 2{,}326\cdot0{,}4 = 8{,}93$. Como 3 > 2,326, **se rechaza H₀** (p = 0,00135).

**Conclusión:** hay evidencia al 1 % de que meditan en promedio más de 8 h semanales.

**b)** "Aceptar que meditan más de 8 h" es **rechazar H₀**. Si en realidad μ = 9, H₀ es falsa y rechazar es **acertar**. 💡 Esa probabilidad es la **potencia**, 1 − β, donde β es la probabilidad del error tipo II (no detectar).

**Receta** (❌): la frontera se arma con el μ de H₀ (ya está: 8,93), y la probabilidad se calcula con el μ verdadero (9):
```
X~N(μ;σ)   μ=9   σ=0.4   P(X>x)   x=8.93   → 0.569
```
**1 − β ≈ 0,569.** Es mucho más baja que si μ fuera 10: 9 está cerca de 8, y además α = 1 % pone la frontera más lejos.

</details>

**Respuesta:**

- a) $z_{obs}$ = 3 > 2,326 ⇒ se rechaza H₀: hay evidencia al 1 % de que meditan más de 8 h semanales
- b) 1 − β ≈ 0,569

</details>

---

[← Volver al menú principal](../../README.md)
