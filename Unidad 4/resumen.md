# Unidad 4 — Estimación

Resumen de la teoría y la práctica del material del aula virtual (Prof. Andrea Alvarez, PyE UTN-FRBA). Suma de variables aleatorias independientes y Teorema Central del Límite, población y muestra, variables aleatorias muestrales, estimación puntual y sus propiedades, distribuciones t de Student y χ², e intervalos de confianza para la media, la varianza, la proporción, la diferencia de medias y la diferencia de proporciones.

---

## 1. Suma de variables aleatorias independientes

### Combinación lineal de normales independientes

Sean $X_1, \dots, X_n$ v.a. **independientes** con $X_i \sim N(\mu_i; \sigma_i)$ y $\alpha_1, \dots, \alpha_n$ números reales. Entonces $W = \alpha_1X_1 + \dots + \alpha_nX_n$ **también es Normal**, con:

$$\boxed{E(W) = \sum_{i=1}^n \alpha_i\mu_i \qquad V(W) = \sum_{i=1}^n \alpha_i^2\sigma_i^2 \qquad \sigma_W = \sqrt{\sum \alpha_i^2\sigma_i^2}}$$

La esperanza es lineal siempre. La fórmula de la varianza usa la independencia (las covarianzas son 0).

Casos particulares:

| | W | E(W) | V(W) |
|---|---|---|---|
| Suma | $\sum X_i$ | $\sum\mu_i$ | $\sum\sigma_i^2$ |
| Diferencia | $X_1 - X_2$ | $\mu_1 - \mu_2$ | $\sigma_1^2 + \sigma_2^2$ (¡se **suman**!) |
| Promedio | $\frac1n\sum X_i$ | $\frac1n\sum\mu_i$ | $\frac1{n^2}\sum\sigma_i^2$ |

**Ojo:** el peso de 3 hombres es $H_1 + H_2 + H_3$ (varianza $`3\sigma^2`$), no $3H$ (varianza $`9\sigma^2`$).

### Ejemplo: ascensor

H ~ N(72; 10) kg, M ~ N(60; 15) kg, independientes. Máximo 300 kg.
- a) Suben 3 hombres y 2 mujeres: $W \sim N\left(3\cdot72 + 2\cdot60;\ \sqrt{3\cdot10^2 + 2\cdot15^2}\right) = N(336;\ 27{,}4)$ ⇒ $P(W > 300) = 0{,}90555$.
- b) Dos hombres difieren en menos de 10 kg: $D = H_1 - H_2 \sim N(0;\ \sqrt{2}\cdot10 = 14{,}14)$ ⇒ $P(|D| < 10) = 0{,}52056$.
- c) El peso de la mujer supera al del hombre: $M - H \sim N(-12;\ 18{,}03)$ ⇒ $P(M - H > 0) = 0{,}25285$.

### Teorema Central del Límite (TCL)

Si $X_1, \dots, X_n$ son **independientes e idénticamente distribuidas** (con cualquier distribución), la suma y el promedio tienden a una Normal cuando $n \to \infty$.

**En la práctica: si n ≥ 30**, se toman como aproximadamente normales:

$$\sum_{i=1}^n X_i \approx N\left(n\mu;\ \sigma\sqrt n\right) \qquad \bar X \approx N\left(\mu;\ \frac{\sigma}{\sqrt n}\right)$$

**Ejemplo (tubos de luz):** cada tubo dura $X_i \sim Exp$ con media 200 h (σ = 200 h). Con 30 tubos en cadena, $W = \sum X_i \approx N(6000;\ 200\sqrt{30} = 1095{,}45)$ ⇒ $P(W > 7500) = 0{,}08545$.

---

## 2. Población, muestra y variables aleatorias muestrales

- **Población:** la v.a. X, con parámetros (μ, σ², σ, p, …) **desconocidos**, que se quieren **estimar**.
- **Muestra aleatoria (m.a.):** $X_1, \dots, X_n$, **n v.a. independientes** con la **misma distribución** que X. Entonces $E(X_i) = \mu$ y $V(X_i) = \sigma^2$.
- **Muestra particular (m.p.):** $x_1, \dots, x_n$, los números que se observan.
- **Variable aleatoria muestral (estadístico):** cualquier función de la m.a., $W = g(X_1, \dots, X_n)$.

### Media muestral

$$\bar X = \frac{\sum_{i=1}^n X_i}{n} \qquad E(\bar X) = \mu \qquad V(\bar X) = \frac{\sigma^2}{n} \qquad \sigma_{\bar X} = \frac{\sigma}{\sqrt n}$$

Distribución:
- Si X es Normal ⇒ $\bar X \sim N(\mu;\ \sigma/\sqrt n)$ exactamente (promedio de normales independientes).
- Si X no es Normal y n ≥ 30 ⇒ $\bar X \approx N(\mu;\ \sigma/\sqrt n)$ (TCL).

### Varianza y desvío muestrales

$$S^2 = \frac{\sum_{i=1}^n (X_i - \bar X)^2}{n - 1} \qquad S = \sqrt{S^2}$$

Ejemplo: m.p. = {20; 24; 26; 20} ⇒ $\bar x = 22{,}5$, $s^2 = 9$, $s = 3$.

### Proporción muestral

Si interesa una característica (éxito), la población es $X \sim$ Bernoulli(p), con $E(X) = p$ y $V(X) = p(1 - p)$. La proporción muestral es el promedio de 0 y 1:

$$\hat p = \frac{\sum X_i}{n} = \bar X \qquad \text{si } n \ge 30:\ \hat p \approx N\left(p;\ \sqrt{\frac{p(1-p)}{n}}\right)$$

**Ejemplo (estaturas h ~ N(165; 7)):**
- a) n = 100: $\bar h \sim N(165;\ 0{,}7)$ ⇒ $P(\bar h > 168) = 0{,}00001$.
- b) n = 36: $P(S > 6) = P\left(\chi^2_{35} > \frac{35\cdot36}{49} = 25{,}71\right) = 0{,}87403$ (ver la sección 4).
- c) p = P(h > 170) ≈ 0,24; con n = 36: $\hat p \approx N(0{,}24;\ 0{,}07)$ ⇒ $P(\hat p > 0{,}20) = 0{,}71615$.

---

## 3. Estimación puntual

Un **estimador puntual** $\hat\theta = g(X_1, \dots, X_n)$ de un parámetro θ es cualquier función de la m.a.

θ es un número (desconocido); $\hat\theta$ es una **v.a.** (toma distintos valores según la muestra). Al valor que toma en una m.p. se lo llama **estimación**.

### Error cuadrático medio y sesgo

$$ECM(\hat\theta) = E\left[(\hat\theta - \theta)^2\right] = V(\hat\theta) + B(\hat\theta)^2 \qquad B(\hat\theta) = E(\hat\theta) - \theta \text{ (sesgo)}$$

### Propiedades de un "buen" estimador

1. **Óptimo:** minimiza el ECM.
2. **Insesgado:** $E(\hat\theta) = \theta$ (sesgo 0: los valores del estimador se reparten alrededor del parámetro).
3. **Consistente:** es insesgado (o asintóticamente insesgado) y $V(\hat\theta) \to 0$ cuando $n \to \infty$, así que las estimaciones se acercan al parámetro.
4. **Eficiente:** es el insesgado de menor varianza.
5. **Suficiente:** usa toda la información de la muestra.

### Estimadores usuales

| Parámetro θ | Estimador $\hat\theta$ | Propiedades |
|---|---|---|
| μ | $\bar X = \frac{\sum X_i}n$ | óptimo, insesgado, consistente, eficiente y suficiente |
| σ² | $S^2 = \frac{\sum(X_i - \bar X)^2}{n-1}$ | insesgado: $E(S^2) = \sigma^2$ (por eso se divide por n − 1) |
| σ | $S = \sqrt{S^2}$ | el mejor estimador de σ |
| p | $\hat p = \frac{\text{éxitos}}{n}$ | insesgado y consistente |

### Métodos para construir estimadores (práctica)

- **Momentos:** se igualan los momentos poblacionales a los muestrales ($`E(X) = \bar X`$, …) y se despeja el parámetro.
- **Máxima verosimilitud:** se elige el θ que maximiza $L(\theta) = \prod f(x_i; \theta)$ (en general, se deriva $\ln L$ y se iguala a 0).

Ejemplo: para Poisson ambos métodos dan $\hat\lambda = \bar X$.

---

## 4. Distribuciones t de Student y χ²

### t de Student con n − 1 grados de libertad

- Curva simétrica respecto de 0, parecida a la normal estándar pero con "colas más pesadas". Parámetro: grados de libertad (g.l.).
- Si n → ∞ tiende a N(0; 1). **Si n ≥ 30 se aproxima por la normal estándar.**

### χ² (chi cuadrado) con n − 1 grados de libertad

- Sólo toma valores **positivos** y **no es simétrica**.

### Estadísticos pivote

| Situación | Estadístico | Distribución |
|---|---|---|
| σ conocido (X normal, o n ≥ 30) | $\dfrac{\bar X - \mu}{\sigma/\sqrt n}$ | N(0; 1) |
| σ desconocido, X normal, n < 30 | $\dfrac{\bar X - \mu}{S/\sqrt n}$ | $t_{n-1}$ |
| σ desconocido, n ≥ 30 | $\dfrac{\bar X - \mu}{S/\sqrt n}$ | ≈ N(0; 1) |
| X normal | $\dfrac{(n-1)S^2}{\sigma^2}$ | $\chi^2_{n-1}$ |

Notación: el subíndice indica la **probabilidad acumulada a la izquierda**. Por ejemplo, $z_{0{,}975} = 1{,}96$ y $\chi^2_{35;\,0{,}025} = 20{,}6$.

Valores usuales de z: $z_{0{,}95} = 1{,}645$, $z_{0{,}975} = 1{,}96$, $z_{0{,}99} = 2{,}33$, $z_{0{,}995} = 2{,}58$.

---

## 5. Intervalos de confianza: generalidades

Con distintas muestras se obtienen distintos intervalos: algunos contienen al parámetro y otros no. Se construyen para que un **gran porcentaje** de ellos lo contengan.

$$IC_\theta = [a; b] \iff P(a < \theta < b) = 1 - \alpha$$

- **1 − α:** nivel de confianza (se fija a priori; valores habituales 0,90, 0,95 y 0,99). **α:** probabilidad de error.
- Los extremos a y b son **v.a. muestrales**: el intervalo es aleatorio, θ no.
- **Interpretación correcta:** si se repitiera el procedimiento con muchas muestras, el (1 − α)·100 % de los intervalos contendría a θ. Para un intervalo ya calculado, θ está o no está: no se habla de "probabilidad".
- **Amplitud:** b − a. **Semiamplitud** $d = \frac{b-a}2$ = precisión del IC = **máximo error de estimación**.
- A mayor confianza, mayor amplitud (menos precisión). A mayor n, menor amplitud.

---

## 6. IC para la media μ

$$IC_\mu = [\bar X - d;\ \bar X + d]$$

| Caso | Semiamplitud d |
|---|---|
| σ **conocido** (X normal, o n ≥ 30) | $d = z_{1-\alpha/2}\,\dfrac{\sigma}{\sqrt n}$ |
| σ desconocido, X **normal**, **n < 30** | $d = t_{n-1;\,1-\alpha/2}\,\dfrac{S}{\sqrt n}$ |
| σ desconocido, **n ≥ 30** | $d = z_{1-\alpha/2}\,\dfrac{S}{\sqrt n}$ |

**Deducción (σ conocido):** $P(-d < \bar X - \mu < d) = 1 - \alpha$; se divide por $\sigma/\sqrt n$ y queda $P\left(-\frac{d}{\sigma/\sqrt n} < Z < \frac{d}{\sigma/\sqrt n}\right) = 1 - \alpha$. Entonces $\frac{d}{\sigma/\sqrt n} = z_{1-\alpha/2}$.

Con σ conocido, la amplitud **no depende de la muestra** (es constante para n y 1 − α dados).

### Tamaño de muestra para un error d dado

$$z_{1-\alpha/2}\frac{\sigma}{\sqrt n} \le d \iff \boxed{n \ge \left(\frac{z_{1-\alpha/2}\,\sigma}{d}\right)^2} \quad\text{(se redondea hacia arriba)}$$

**Ejemplo (Ej. 18):** X ~ N(μ; 4), n = 144, $\bar x = 168$, 98 %: $d = 2{,}33\cdot\frac4{12} = 0{,}78$ ⇒ $IC_\mu = [167{,}22;\ 168{,}78]$ cm.

Con 95 % y el mismo d: $n \ge (1{,}96\cdot4/0{,}78)^2 = 101{,}0$ ⇒ **n ≥ 102**.

---

## 7. IC para la varianza σ² y el desvío σ

Requiere **población normal**. Como $\frac{(n-1)S^2}{\sigma^2} \sim \chi^2_{n-1}$ (no simétrica), se reparte α/2 en cada cola:

$$\boxed{IC_{\sigma^2} = \left[\frac{(n-1)S^2}{\chi^2_{n-1;\,1-\alpha/2}};\ \frac{(n-1)S^2}{\chi^2_{n-1;\,\alpha/2}}\right] \qquad IC_\sigma = \left[\sqrt{\frac{(n-1)S^2}{\chi^2_{n-1;\,1-\alpha/2}}};\ \sqrt{\frac{(n-1)S^2}{\chi^2_{n-1;\,\alpha/2}}}\right]}$$

El cuantil **grande** va en el extremo **inferior**. El intervalo no está centrado en $S^2$.

(Si se usa una tabla que da la probabilidad acumulada a **derecha**, los subíndices de los denominadores aparecen invertidos.)

**Ejemplo (Ej. 23):** n = 36, s = 2,81 ohm, 95 %: $\chi^2_{35;\,0{,}025} = 20{,}6$ y $\chi^2_{35;\,0{,}975} = 53{,}2$ ⇒ $IC_\sigma = \left[\sqrt{\frac{35\cdot2{,}81^2}{53{,}2}};\ \sqrt{\frac{35\cdot2{,}81^2}{20{,}6}}\right] = [2{,}28;\ 3{,}66]$ ohm.

---

## 8. IC para la proporción p

Por TCL, $\hat p \approx N\left(p;\ \sqrt{p(1-p)/n}\right)$. Como p es desconocido, en el desvío se reemplaza por $\hat p$. Esto sólo vale si la muestra es **"muy grande"** (el apunte pide **n ≥ 100**; el resumen de la cátedra, n ≥ 30):

$$\boxed{IC_p = \left[\hat p - z_{1-\alpha/2}\sqrt{\frac{\hat p(1-\hat p)}{n}};\ \hat p + z_{1-\alpha/2}\sqrt{\frac{\hat p(1-\hat p)}{n}}\right]}$$

**Tamaño de muestra:** $n \ge \dfrac{z_{1-\alpha/2}^2\,\hat p(1 - \hat p)}{d^2}$. Si no se conoce $\hat p$, se usa el caso más desfavorable $\hat p(1 - \hat p) = 0{,}25$.

**Ejemplo (Ej. 27 a):** 350 neumáticos, 86 con algún defecto ⇒ $\hat p = 0{,}25$. Con 99 %: $d = 2{,}58\sqrt{\frac{0{,}25\cdot0{,}75}{350}} = 0{,}06$ ⇒ $IC_p = [0{,}19;\ 0{,}31]$.

---

## 9. IC para la diferencia de medias μ₁ − μ₂

Dos poblaciones **independientes** y **normales**. Estimador puntual: $\bar X_1 - \bar X_2 \sim N\left(\mu_1 - \mu_2;\ \sqrt{\frac{\sigma_1^2}{n_1} + \frac{\sigma_2^2}{n_2}}\right)$.

$$IC_{\mu_1 - \mu_2} = [(\bar X_1 - \bar X_2) - d;\ (\bar X_1 - \bar X_2) + d]$$

| Caso | Semiamplitud d |
|---|---|
| $\sigma_1$ y $\sigma_2$ **conocidos** | $d = z_{1-\alpha/2}\sqrt{\dfrac{\sigma_1^2}{n_1} + \dfrac{\sigma_2^2}{n_2}}$ |
| Desconocidos pero **iguales** ($`\sigma_1 = \sigma_2`$) | $d = t_{n_1+n_2-2;\,1-\alpha/2}\;S_p\sqrt{\dfrac1{n_1} + \dfrac1{n_2}}$ |

**Varianza ponderada (amalgamada):** promedio ponderado de las varianzas muestrales:

$$S_p^2 = \frac{(n_1 - 1)S_1^2 + (n_2 - 1)S_2^2}{n_1 + n_2 - 2}$$

$S_p$ siempre queda **entre** $S_1$ y $S_2$ (sirve para controlar la cuenta).

Si n₁, n₂ ≥ 30 con varianzas desconocidas, se usa z con $S_1^2$ y $S_2^2$ en lugar de σ₁² y σ₂².

**Interpretación:** si el IC **contiene al 0**, no hay evidencia de que las medias sean distintas. Si queda todo del lado positivo (o negativo), hay evidencia de que μ₁ > μ₂ (o μ₁ < μ₂).

**Ejemplo (Ej. 28):**
- Datos: $n_A = 10$, $\bar x_A = 21{,}9$, $s_A = 4{,}1$; $n_B = 8$, $\bar x_B = 22$, $s_B = 4$.
- $S_p = \sqrt{\frac{9\cdot4{,}1^2 + 7\cdot4^2}{16}} = 4{,}06$; $t_{16;\,0{,}975} = 2{,}12$ ⇒ $d = 2{,}12\cdot4{,}06\sqrt{\frac1{10} + \frac18} = 4{,}08$.
- $IC = [-0{,}1 - 4{,}08;\ -0{,}1 + 4{,}08] = [-4{,}18;\ 3{,}98]$.
- Supuestos necesarios: normalidad, independencia y $\sigma_A = \sigma_B$.

---

## 10. IC para la diferencia de proporciones p₁ − p₂

Muestras independientes y grandes (el apunte pide n₁, n₂ ≥ 100; el resumen de la cátedra, ≥ 30):

$$\boxed{IC_{p_1 - p_2} = (\hat p_1 - \hat p_2) \pm z_{1-\alpha/2}\sqrt{\frac{\hat p_1(1-\hat p_1)}{n_1} + \frac{\hat p_2(1-\hat p_2)}{n_2}}}$$

**Ejemplo (Ej. 29, bicisendas):** $\hat p_1 = 400/1000 = 0{,}4$ y $\hat p_2 = 900/1500 = 0{,}6$.
- 95 %: $d = 1{,}96\sqrt{\frac{0{,}24}{1000} + \frac{0{,}24}{1500}} = 0{,}0392$ ⇒ $IC = [-0{,}2392;\ -0{,}1608]$ (amplitud 0,0784).
- 90 %: $d = 1{,}64\cdot0{,}02 = 0{,}0328$ ⇒ amplitud 0,0656, un 83,7 % de la anterior ⇒ se reduce un **16,3 %**.

---

## 11. Tabla resumen de intervalos de confianza

| Parámetro | Condiciones | Intervalo |
|---|---|---|
| μ | Normal, σ conocido | $\bar X \pm z_{1-\alpha/2}\,\dfrac{\sigma}{\sqrt n}$ |
| μ | Normal, σ desconocido | $\bar X \pm t_{n-1;\,1-\alpha/2}\,\dfrac{S}{\sqrt n}$ |
| μ | Cualquier distribución, n ≥ 30 * | $\bar X \pm z_{1-\alpha/2}\,\dfrac{\sigma \text{ o } S}{\sqrt n}$ |
| p | n grande * | $\hat p \pm z_{1-\alpha/2}\sqrt{\dfrac{\hat p(1-\hat p)}{n}}$ |
| σ² | Normal | $\left[\dfrac{(n-1)S^2}{\chi^2_{n-1;\,1-\alpha/2}};\ \dfrac{(n-1)S^2}{\chi^2_{n-1;\,\alpha/2}}\right]$ |
| μ₁ − μ₂ | Normales, varianzas conocidas | $(\bar X_1 - \bar X_2) \pm z_{1-\alpha/2}\sqrt{\dfrac{\sigma_1^2}{n_1} + \dfrac{\sigma_2^2}{n_2}}$ |
| μ₁ − μ₂ | Normales, varianzas desconocidas e iguales | $(\bar X_1 - \bar X_2) \pm t_{n_1+n_2-2;\,1-\alpha/2}\,S_p\sqrt{\dfrac1{n_1} + \dfrac1{n_2}}$ |
| p₁ − p₂ | Muestras independientes grandes * | $(\hat p_1 - \hat p_2) \pm z_{1-\alpha/2}\sqrt{\dfrac{\hat p_1(1-\hat p_1)}{n_1} + \dfrac{\hat p_2(1-\hat p_2)}{n_2}}$ |

\* Intervalos **asintóticos** (valen por el TCL).

### Ejercicios de la guía sugeridos en el material

Priorizar los ejercicios 3, 5, 6, 7, 8, 9, 10, 11, 13, del 17 al 28 y el 30. No es necesario resolver los ejercicios 1, 2, 4, 12, 14, 15, 16, 29 y 31.

---

[← Volver al menú principal](../README.md)
