# Unidad 6 — Regresión y Correlación

Resumen de la teoría y la práctica del material del aula virtual (Prof. Andrea Alvarez, PyE UTN-FRBA). Diagrama de dispersión, coeficiente de correlación lineal, modelo de regresión lineal simple, estimadores de mínimos cuadrados, descomposición de la variación y coeficiente de determinación, y validación del modelo (test para ρ y para la pendiente, supuestos e intervalos).

---

## 1. Diagrama de dispersión

Es la representación gráfica de todos los pares observados $(x_i; y_i)$. Sirve para ver si hay relación entre las variables, de qué forma es (lineal, exponencial, …) y si hay puntos atípicos.

**Ejemplo (Ausentismo según Edad):** el gerente de la empresa P&C toma una muestra de 10 trabajadores.

| Edad X (años) | 25 | 46 | 58 | 37 | 55 | 32 | 41 | 50 | 23 | 60 |
|---|---|---|---|---|---|---|---|---|---|---|
| Ausentismo Y (días/año) | 18 | 12 | 8 | 15 | 10 | 13 | 7 | 9 | 16 | 6 |

Los puntos muestran una tendencia **lineal decreciente**: a mayor edad, menos ausentismo.

---

## 2. Coeficiente de correlación lineal

### Poblacional

$$\rho = \frac{Cov(X, Y)}{\sigma_X\,\sigma_Y} \qquad -1 \le \rho \le 1$$

Mide el grado de asociación **lineal**:
- ρ cerca de 1: relación lineal directa.
- ρ cerca de −1: relación lineal inversa.
- ρ cerca de 0: no hay relación lineal (puede haber otra).

Es un parámetro desconocido y se estima con r.

### Muestral y cantidades básicas

$$\boxed{r = \frac{S_{xy}}{\sqrt{S_{xx}\,S_{yy}}}}$$

Las tres cantidades básicas se pueden calcular de dos maneras:
- $S_{xx} = \sum(x_i - \bar x)^2 = \sum x_i^2 - \frac1n\left(\sum x_i\right)^2$
- $S_{yy} = \sum(y_i - \bar y)^2 = \sum y_i^2 - \frac1n\left(\sum y_i\right)^2$
- $S_{xy} = \sum(x_i - \bar x)(y_i - \bar y) = \sum x_iy_i - \frac1n\sum x_i\sum y_i$

**Ejemplo:** $\sum x = 427$, $\sum y = 114$, $\sum xy = 4452$, $\sum x^2 = 19833$, $\sum y^2 = 1448$.
- $S_{xx} = 1600{,}1$, $S_{yy} = 148{,}4$, $S_{xy} = -415{,}8$.
- $r = \frac{-415{,}8}{\sqrt{1600{,}1\cdot148{,}4}} = -0{,}8533$: está cerca de −1 (¿lo suficiente? → test de la sección 6).

---

## 3. Modelo de regresión lineal simple

$$Y = \beta_0 + \beta_1X + \varepsilon \qquad E(Y \mid X) = \beta_0 + \beta_1X$$

- X: variable **independiente** o explicativa. Y: variable **dependiente**, explicada o de respuesta.
- β₀: ordenada al origen de la recta de regresión. β₁: pendiente (cambio medio de Y cuando X aumenta 1 unidad).
- ε: v.a. error.

### Supuestos teóricos

1. $\varepsilon \sim N(0;\ \sigma)$ (**normalidad** de los errores).
2. σ **constante** para todo X (**homocedasticidad**).
3. Los errores son **independientes**.

Entonces $Y \mid X \sim N(\beta_0 + \beta_1X;\ \sigma)$. Los parámetros del modelo son β₀, β₁ y σ, todos desconocidos.

---

## 4. Estimación por mínimos cuadrados

A partir de la m.a. $(X_1; Y_1), \dots, (X_n; Y_n)$ se estima la **recta de regresión muestral** $\hat y = b_0 + b_1x$.

- Valor estimado: $\hat y_i = b_0 + b_1x_i$.
- **Residuo:** $e_i = y_i - \hat y_i$ (distancia vertical entre el punto y la recta).

**Método de mínimos cuadrados:** $b_0$ y $b_1$ son los valores que minimizan

$$g(b_0, b_1) = \sum_{i=1}^n e_i^2 = \sum_{i=1}^n \left(y_i - (b_0 + b_1x_i)\right)^2$$

$$\boxed{b_1 = \frac{S_{xy}}{S_{xx}} \qquad b_0 = \bar y - b_1\bar x \qquad \hat\sigma^2 = S^2 = \frac{\sum e_i^2}{n-2} = \frac{SC_{res}}{n-2}}$$

- $b_0$ y $b_1$ son **insesgados y consistentes**; $S^2$ es insesgado.
- Se divide por n − 2 porque se estimaron 2 parámetros.
- La recta siempre pasa por $(\bar x, \bar y)$, y además $\sum e_i = 0$ y $\sum x_ie_i = 0$ (ecuaciones normales).
- Si los errores son normales, coinciden con los estimadores de máxima verosimilitud.
- El **signo de b₁ es el mismo que el de r**.

**Ejemplo:** $\bar x = 42{,}7$, $\bar y = 11{,}4$.
- $b_1 = \frac{-415{,}8}{1600{,}1} = -0{,}26$ y $b_0 = 11{,}4 + 0{,}26\cdot42{,}7 = 22{,}5$ ⇒ $\hat y = 22{,}5 - 0{,}26x$, válida para $23 \le x \le 60$.
- Un trabajador de 35 años: $\hat y = 22{,}5 - 0{,}26\cdot35 = 13{,}4$ días por año.

**No extrapolar:** el modelo sólo vale dentro del rango de x observado.

---

## 5. Fuentes de variación y coeficiente de determinación

$$\underbrace{\sum(y_i - \bar y)^2}_{SC_{total} = S_{yy}} = \underbrace{\sum(\hat y_i - \bar y)^2}_{SC_{exp} = S_{xy}^2/S_{xx}} + \underbrace{\sum(y_i - \hat y_i)^2}_{SC_{res}}$$

- **SC total:** variación total de Y.
- **SC explicada (de la regresión):** la parte que explica la recta.
- **SC residual:** la parte no explicada.

$$\boxed{R^2 = \frac{SC_{exp}}{SC_{total}} = r^2 \qquad 0 \le R^2 \le 1}$$

R² es la **proporción de la variación total de Y explicada por la recta de regresión** (a través de X).

**Ejemplo:** $SC_{total} = 148{,}4$, $SC_{exp} = \frac{(-415{,}8)^2}{1600{,}1} = 108{,}05$, $SC_{res} = 40{,}35$ ⇒ $R^2 = 0{,}7281$.

Se estima que el 72,81 % de la variación de los días de ausentismo está explicada por la variación de la edad.

---

## 6. Validación del modelo

### Test para el coeficiente de correlación ρ

Con el modelo y sus supuestos (normalidad):

1. H₀: ρ = 0 (no hay correlación lineal) vs. H₁: ρ ≠ 0.
2. α.
3. Estadístico: $T = \dfrac{r\sqrt{n-2}}{\sqrt{1 - r^2}} \sim t_{n-2}$ bajo H₀.
4. Valor observado $t_{obs}$.
5. RC = {|T| > $t_{n-2;\,1-\alpha/2}$}. Si se rechaza H₀, el modelo lineal es válido (significativo).

**Ejemplo (antigüedad vs. llegadas tarde, n = 6):** $\hat y = 0{,}9596x - 1{,}7713$ ($4 \le x \le 7$), $R^2 = 0{,}9335$.
- Como $b_1 > 0$, $r = +\sqrt{0{,}9335} = 0{,}9662$.
- $t_{obs} = \frac{0{,}9662\sqrt4}{\sqrt{1 - 0{,}9335}} = 7{,}5 > t_{4;\,0{,}975} = 2{,}776$ ⇒ se rechaza H₀: el modelo es válido para explicar las llegadas tarde según la antigüedad.
- ¿Se puede usar para 20 años de antigüedad? **No**, porque 20 está fuera del rango observado.

### Test para la pendiente β₁ (significación de la regresión)

$$H_0: \beta_1 = 0 \quad\text{vs.}\quad H_1: \beta_1 \ne 0 \qquad T = \frac{b_1}{s_{b_1}} \sim t_{n-2}, \quad s_{b_1} = \frac{S}{\sqrt{S_{xx}}}$$

Es equivalente al test para ρ: da el mismo $t_{obs}$. Para la ordenada se usa $s_{b_0} = S\sqrt{\frac1n + \frac{\bar x^2}{S_{xx}}}$.

### Intervalos para una nueva observación x₀ (práctica)

Con $\hat y_0 = b_0 + b_1x_0$ y $t = t_{n-2;\,1-\alpha/2}$:

| Intervalo | Fórmula |
|---|---|
| IC para la **media** E(Y \| x₀) | $\hat y_0 \pm t\,S\sqrt{\dfrac1n + \dfrac{(x_0 - \bar x)^2}{S_{xx}}}$ |
| Intervalo de **predicción** de un valor individual | $\hat y_0 \pm t\,S\sqrt{1 + \dfrac1n + \dfrac{(x_0 - \bar x)^2}{S_{xx}}}$ |

El de predicción siempre es **más ancho** (suma la variabilidad de un individuo). Ambos son más angostos cuando $x_0 = \bar x$.

### Verificación de los supuestos (análisis de residuos)

- **Normalidad:** test de Shapiro-Wilks sobre los residuos (no rechazar ⇒ se acepta la normalidad).
- **Homocedasticidad:** en el gráfico de residuos vs. x (o vs. ŷ) no debe aparecer estructura (forma de embudo) ni residuos muy grandes en valor absoluto.
- **Puntos atípicos/influyentes:** un punto alejado puede cambiar mucho la pendiente; conviene ajustar con y sin él.
- **Linealidad:** si la nube tiene forma curva (por ejemplo, exponencial), se puede **transformar** la variable: ajustar ln(Y) vs. X y después volver con $\hat y = e^{b_0 + b_1x}$.

---

## 7. Resumen de fórmulas

| Concepto | Fórmula |
|---|---|
| Pendiente | $b_1 = S_{xy}/S_{xx}$ |
| Ordenada | $b_0 = \bar y - b_1\bar x$ |
| Correlación | $r = S_{xy}/\sqrt{S_{xx}S_{yy}}$ |
| Determinación | $R^2 = r^2 = SC_{exp}/SC_{total}$ |
| SC explicada | $S_{xy}^2/S_{xx}$ |
| Varianza residual | $S^2 = SC_{res}/(n-2)$ |
| Test ρ = 0 | $T = r\sqrt{n-2}/\sqrt{1 - r^2} \sim t_{n-2}$ |
| Test β₁ = 0 | $T = b_1/(S/\sqrt{S_{xx}}) \sim t_{n-2}$ |

---

[← Volver al menú principal](../README.md)
