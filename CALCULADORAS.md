# Calculadoras permitidas

En los ejercicios y parciales se pueden usar tres apps de Android. Este archivo lista qué tiene cada una (relevado de capturas del 20/11/2026) y para qué sirve en la materia.

**Prioridad:** usar **Probability Distributions** y **Calculadora de estadística** (o calculadora común). **IntroStat** se evita: solo se sugiere cuando algo no se puede hacer con las otras dos o es mucho más complicado, y **siempre** se muestra también el camino alternativo más fácil con las otras apps o a mano (ver sección 3).

---

## 1. Probability Distributions

App para calcular probabilidades de distribuciones conocidas: P(X<x), P(X>x) y, al revés, el x que deja cierta probabilidad.

### Distribuciones disponibles

| Distribución | Uso en la materia |
|---|---|
| **Normal** | U2–U5: probabilidades normales, TCL, x̄, p̂, valores z |
| **t** | U4–U6: IC y tests para μ con σ desconocida, tests de regresión |
| **Chi-Square** | U4–U5: varianza muestral, IC y test para σ² |
| **F** | Cociente de varianzas (si aparece) |
| **Exponential** | U2: tiempos de espera |
| **Gamma** | U2 |
| **Beta** | Truco para la uniforme (ver abajo) |
| **Log-Normal**, **Pareto (Type I)**, **Weibull** | Poco uso en la materia |
| **Binomial** | U2: cantidad de éxitos en n ensayos |
| **Geometric (I)** y **Geometric (II)** | U2: las dos convenciones (contar ensayos o contar fracasos hasta el 1.er éxito). Chequear en la app cuál es cuál según el rango de x |
| **Hypergeometric** | U2: muestreo sin reposición |
| **Negative Binomial (I)** y **(II)** | U2: las dos convenciones, igual que la geométrica |
| **Poisson** | U2: cantidad de eventos en un intervalo |

La lista del menú termina en Poisson.

### Qué NO tiene

- **Uniforme continua.** Se calcula a mano: P(X > x) = (b − x)/(b − a). Si se quiere usar la app, U(0;1) = Beta(1;1): `X~Beta(α;β) α=1 β=1 P(X>x) x=(x−a)/(b−a)`.

### Notación para escribir los cálculos

Siempre se indican los inputs tal como se cargan en la app:

```
X~N(μ;σ)     μ=165   σ=0.7   P(X>x)   x=168
X~t(ν)       ν=24            P(X>x)   x=2.064
X~χ²(ν)      ν=35            P(X>x)   x=25.714
X~Bin(n,p)   n=80    p=0.4   P(X≥x)   x=28
```

- Para la **t** y la **χ²**, ν son los grados de libertad (normalmente n − 1).
- En la χ² el x **no es el desvío**: es (n−1)·s²/σ².
- Para una probabilidad "entre" se hacen dos cuentas y se resta: P(X<x₂) − P(X<x₁).

---

## 2. Calculadora de estadística (Statistics Calculator, João Gondim)

App para procesar datos y hacer algunos tests. Para ver la fórmula que usa cada función hay que **mantener presionado** el botón correspondiente (el botón "Fórmulas" del menú solo avisa esto).

### Funciones disponibles

| Función | Qué hace | Uso en la materia |
|---|---|---|
| **Estadística descriptiva** | Media, mediana, cuartiles, varianza, desvío, CV, error estándar a partir de datos sueltos | U4–U5: sacar x̄, s y s/√n de una muestra para armar IC o tests |
| **Descriptiva con frecuencia** | Lo mismo pero con datos agrupados (valor + frecuencia) | Igual que la anterior, cuando los datos vienen en tabla |
| **Regresión lineal** | Coeficientes y ecuación de la recta a partir de los pares (x, y) | U6: b₀, b₁, ŷ = b₀ + b₁x |
| **Regresión con suma** | Regresión cargando las sumas (Σx, Σy, Σxy, Σx², n) en vez de los datos | U6: cuando el ejercicio da las sumatorias directamente |
| **Distribución de frecuencias** | Tabla de frecuencias | U1 |
| **Binomial** | Probabilidades, esperanza, varianza y desvío | U2 |
| **Poisson** | Probabilidades de Poisson | U2 |
| **Distribución normal** | Probabilidades normales | U2–U5 (también lo hace la otra app) |
| **Prueba T una media** | Test t para μ: H0, H1, región crítica, estadístico, conclusión, valor p | U5: test para la media con σ desconocida |
| **Prueba T dos medias** | Test t para μ₁ − μ₂ | U5: diferencia de medias |
| **Prueba Chi-Cuadrado** | Casi seguro es el de bondad de ajuste o independencia (tablas de frecuencias) | **No** es el test de varianza σ² de la U5 |

### Qué NO tiene (según la descripción oficial)

- Intervalos de confianza. Se arman con x̄ y s de la descriptiva más el valor t, z o χ² de Probability Distributions.
- Test para la proporción p y test para la varianza σ². Se hacen a mano con la Normal o la χ² de la otra app.
- Coeficiente de correlación r, R² y test de la pendiente. Verificar si la pantalla de regresión muestra r.

---

## 3. IntroStat (usar solo como último recurso)

> **Regla:** evitarla. Sugerirla solo si el cálculo no se puede hacer con las otras dos apps o es mucho más complicado. **Cada vez** que se use, mostrar también el camino alternativo más fácil (Probability Distributions, Calculadora de estadística o a mano).

Menú principal: **Tasks**, con pestañas. Los datos se cargan con *New Dataset* / *Edit Dataset* y cada función indica qué formato acepta (*Accepts*: Data List, Data Summary, 1-Way Freq. Table, Binomial Sample Summary, etc.).

### Descriptive Statistics
- Basic Statistics (media, mediana, moda, rango, desvío…; acepta lista de datos o tabla de frecuencias)
- z-Scores, Boxplot, Histogram, The Empirical Rule, Chebyshev's Theorem

### Probability
- **Sample Space & Events:** Symbolic Events (uniones, intersecciones, complementos), Tables
- **Discrete Random Variables:** General (distribución definida a mano), Bernoulli, Binomial, Poisson
- **Continuous Random Variables:** **Uniform**, Standard Normal, Normal, t, Chi-Square, F
- **Percentiles of Continuous Random Variables:** las mismas seis (ingresar un % y devuelve el x)

### Sampling Distributions
1. TCL para medias muestrales
2. Medias muestrales de población Normal
3. TCL para proporciones muestrales
4. Aproximación Normal a la Binomial

### Confidence Intervals
- **One Population Mean:** (1) muestra grande σ² conocida, (2) muestra grande σ² desconocida, (3) muestra chica Normal σ² conocida, (4) muestra chica Normal σ² desconocida, + tamaño mínimo de muestra
- **One Population Proportion:** muestra binomial grande, + tamaño mínimo de muestra
- **Difference of Two Population Means:** (1) dos muestras grandes, (2) chicas Normales con varianzas conocidas, (3) chicas Normales con varianzas desconocidas distintas, (4) desconocidas pero iguales, (5) muestras apareadas
- **Difference of Two Population Proportions:** dos muestras binomiales grandes
- No se vio IC para la varianza σ².

### Hypothesis Testing
- Mismas categorías que los IC (media, proporción, diferencia de medias, diferencia de proporciones). Solo se vio en detalle la de diferencia de proporciones; se asume que las variantes son las mismas que en IC.

### Simple Regression
- Basic Summary Statistics: recta de mínimos cuadrados, diagrama de dispersión, estimación del desvío del error, **r**, **R²**, rango
- IC de β₁, test sobre β₁, test sobre ρ
- ŷ en x = x₀, IC para E(Y) en x₀, intervalo de predicción para Y en x₀

### Chi-Square & F Tests
- Independencia de 2 factores (tabla de contingencia), bondad de ajuste, igualdad de 2 varianzas (F), ANOVA de 1 factor

### Cuándo puede valer la pena y cuál es la alternativa

| Caso | En IntroStat | Alternativa más fácil sin IntroStat |
|---|---|---|
| Uniforme | Continuous RV → Uniform | A mano: P(X>x) = (b−x)/(b−a) |
| IC para μ | Confidence Intervals → One Population Mean | x̄ y s de la descriptiva (Calc. estadística) + t o z de Prob. Distributions → x̄ ± t·s/√n |
| IC / test para p | One Population Proportion | p̂ ± z·√(p̂(1−p̂)/n); en el test, z = (p̂−p₀)/√(p₀(1−p₀)/n) y p-valor con la Normal de Prob. Distributions |
| Tamaño de muestra | Minimum Sample Size | A mano: n = (z·σ/d)² (redondear hacia arriba) |
| Diferencia de medias / proporciones | Difference of Two… | Test: Prueba T dos medias (Calc. estadística). IC y proporciones: fórmula + valor crítico de Prob. Distributions |
| Igualdad de 2 varianzas | Chi-Square & F Tests | F = s₁²/s₂² y p-valor con F(ν₁;ν₂) de Prob. Distributions |
| r, R², tests de β₁ y ρ, intervalos en x₀ (U6) | Simple Regression | b₀ y b₁ con Regresión lineal (Calc. estadística); r, R² y estadísticos a mano con las fórmulas de la hoja + t(n−2) de Prob. Distributions. **Es donde IntroStat ahorra más trabajo.** |

---

## Cómo combinar las apps

- **Calculadora de estadística:** procesar datos (descriptiva, regresión) y controlar tests t completos.
- **Probability Distributions:** cualquier probabilidad o valor crítico (Normal, t, χ², F) y todas las distribuciones de la U2.
- **IntroStat:** solo como último recurso, siempre con la alternativa al lado.
