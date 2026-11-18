# Unidad 5 — Test de Hipótesis

Resumen de la teoría y la práctica del material del aula virtual (Prof. Andrea Alvarez, PyE UTN-FRBA). Hipótesis estadísticas, errores de tipo I y II, nivel de significación, región crítica y valor p. Tests para la media, la varianza, la proporción y la diferencia de medias (y de proporciones). Potencia de un test y cálculo del tamaño de muestra para α y β dados.

---

## 1. Hipótesis estadísticas

Una **hipótesis estadística** es una afirmación, con sentido, sobre una o varias poblaciones.
- **Paramétrica:** afirma algo sobre un parámetro (μ = 500, σ² > 25, μ₁ − μ₂ < 0).
- **No paramétrica:** afirma otra cosa (X es Normal, X e Y son independientes).

Su valor de verdad **no se puede conocer**: se decide a partir de una muestra. Una muestra puede avalar una H falsa o refutar una H verdadera.

### Hipótesis nula y alternativa

- **H₀ (nula o inicial):** la hipótesis establecida, que se pone a prueba. Siempre lleva la **igualdad** (=, ≤, ≥).
- **H₁ (alternativa):** la que contradice a H₀ y se quiere probar. Es una desigualdad **estricta** (<, >, ≠).

Lo que se quiere demostrar (la "sospecha", la afirmación del fabricante, …) va en **H₁**, porque sólo rechazar H₀ es una conclusión fuerte.

Las hipótesis se plantean sobre **parámetros** (μ, σ², p), nunca sobre estadísticos ($\bar x$, s², $\hat p$).

| Tipo de test | H₀ | H₁ | Región crítica |
|---|---|---|---|
| Unilateral izquierdo | θ = θ₀ | θ < θ₀ | cola izquierda |
| Unilateral derecho | θ = θ₀ | θ > θ₀ | cola derecha |
| Bilateral | θ = θ₀ | θ ≠ θ₀ | las dos colas (α/2 en cada una) |

---

## 2. Decisión y tipos de error

Se rechaza H₀ cuando el valor observado del estimador es **"significativamente"** distinto de θ₀ en la dirección de H₁.

| | H₀ verdadera | H₀ falsa |
|---|---|---|
| **Rechazar H₀** | Error tipo I (α) | Decisión correcta (1 − β) |
| **No rechazar H₀** | Decisión correcta (1 − α) | Error tipo II (β) |

- **α = P(rechazar H₀ | H₀ verdadera)** = **nivel de significación**. Se fija a priori (habitualmente 0,05, 0,01 o 0,10).
- **β = P(no rechazar H₀ | H₀ falsa)**. Depende del verdadero valor del parámetro.
- **1 − β = potencia** del test = P(rechazar H₀ | H₀ falsa).

α y β **no** suman 1: se calculan bajo hipótesis distintas. Para un n fijo, si se achica uno, crece el otro. La única forma de achicar ambos es aumentar n.

---

## 3. Procedimiento (5 pasos del apunte)

1. **Hipótesis:** plantear H₀ y H₁.
2. **Nivel de significación:** fijar α.
3. **Estadístico de prueba (E.P.)** y su distribución **suponiendo H₀ verdadera**.
4. **Muestra:** calcular el valor observado del estadístico.
5. **Decisión:** comparar con la **región crítica (RC)** o con el **valor p**, y responder en el contexto del problema.

### Región crítica

Es el conjunto de valores del estadístico que llevan a rechazar H₀. Su borde es el **valor crítico**, y se elige para que P(estadístico ∈ RC | H₀) = α.

### Valor p

Es la probabilidad, **suponiendo H₀ verdadera**, de obtener un valor del estadístico **tan extremo o más** que el observado (en la dirección de H₁). En el bilateral se duplica la cola.

$$\boxed{\text{Se rechaza } H_0 \iff \text{valor } p < \alpha}$$

Es el menor nivel de significación con el que se rechazaría H₀.

### Relación con los intervalos de confianza

El test bilateral de nivel α **no rechaza** H₀: θ = θ₀ exactamente cuando θ₀ ∈ IC de nivel 1 − α (con los mismos datos).

---

## 4. Test para la media μ

| Caso | Estadístico de prueba (bajo H₀) | Distribución |
|---|---|---|
| σ conocido (X normal, o n ≥ 30) | $Z = \dfrac{\bar X - \mu_0}{\sigma/\sqrt n}$ | N(0; 1) |
| σ desconocido, X normal, n < 30 | $T = \dfrac{\bar X - \mu_0}{S/\sqrt n}$ | $t_{n-1}$ |
| σ desconocido, n ≥ 30 | $Z = \dfrac{\bar X - \mu_0}{S/\sqrt n}$ | ≈ N(0; 1) |

Regiones críticas (con Z; con T se cambian los z por $t_{n-1}$):

| H₁ | RC |
|---|---|
| μ < μ₀ | $Z < z_\alpha$ (o $\bar X < \mu_0 + z_\alpha\frac\sigma{\sqrt n}$) |
| μ > μ₀ | $Z > z_{1-\alpha}$ (o $\bar X > \mu_0 + z_{1-\alpha}\frac\sigma{\sqrt n}$) |
| μ ≠ μ₀ | $\lvert Z\rvert > z_{1-\alpha/2}$ |

El test es de **nivel exacto** si la distribución del estadístico es exacta (población normal) y **aproximado (asintótico)** si se usa el TCL.

---

## 5. Test para la varianza σ²

Requiere **población Normal**. Estimador: $S^2$.

$$\chi^2 = \frac{(n-1)S^2}{\sigma_0^2} \sim \chi^2_{n-1} \quad \text{(bajo } H_0: \sigma^2 = \sigma_0^2\text{)}$$

| H₁ | RC |
|---|---|
| σ² < σ₀² | $\chi^2 < \chi^2_{n-1;\,\alpha}$ |
| σ² > σ₀² | $\chi^2 > \chi^2_{n-1;\,1-\alpha}$ |
| σ² ≠ σ₀² | $\chi^2 < \chi^2_{n-1;\,\alpha/2}$ o $\chi^2 > \chi^2_{n-1;\,1-\alpha/2}$ |

**Ejemplo (Ej. 13):** el capataz afirma σ = 2 min; n = 25, s = 3,9 min, α = 0,05.
1. H₀: σ² = 4 vs. H₁: σ² ≠ 4.
2. α = 0,05.
3. E.P.: $\frac{24S^2}{4} \sim \chi^2_{24}$.
4. $\chi^2_{obs} = \frac{24\cdot15{,}21}{4} = 91{,}26$.
5. RC = {χ² < 12,40} ∪ {χ² > 39,36}. Como 91,26 ∈ RC, se rechaza H₀: el desvío no es 2 min.

---

## 6. Test para la proporción p

Población Bernoulli(p); con n grande, por TCL:

$$Z = \frac{\hat p - p_0}{\sqrt{\dfrac{p_0(1-p_0)}{n}}} \approx N(0; 1) \quad \text{(bajo } H_0: p = p_0\text{)}$$

En el desvío se usa **p₀** (el valor de H₀), no $\hat p$. Las RC son como las de la media con Z.

También se puede trabajar con la cantidad de éxitos X ~ Bin(n; p₀): por ejemplo, RC = {X ≥ 32} para H₁: p > 0,5 con n = 50.

---

## 7. Test para la diferencia de medias μ₁ − μ₂

Poblaciones **normales e independientes**. H₀: μ₁ − μ₂ = D (casi siempre D = 0, "las medias son iguales").

| Caso | Estadístico de prueba |
|---|---|
| σ₁ y σ₂ conocidos | $Z = \dfrac{(\bar X_1 - \bar X_2) - D}{\sqrt{\dfrac{\sigma_1^2}{n_1} + \dfrac{\sigma_2^2}{n_2}}} \sim N(0; 1)$ |
| σ₁ = σ₂ desconocidos | $T = \dfrac{(\bar X_1 - \bar X_2) - D}{S_p\sqrt{\dfrac1{n_1} + \dfrac1{n_2}}} \sim t_{n_1+n_2-2}$, con $S_p^2 = \dfrac{(n_1-1)S_1^2 + (n_2-1)S_2^2}{n_1 + n_2 - 2}$ |

**Ejemplo (pérdida de líquido):** σ = 300 litros en ambas poblaciones, n₁ = n₂ = 10.
- Antes de la modificación $\bar x_1$ = 14900 litros y después $\bar x_2$ = 14000 litros.
- Se quiere probar que la modificación reduce la pérdida: H₀: μ₁ − μ₂ = 0 vs. H₁: μ₁ − μ₂ > 0, con α = 0,05.
- $z_{obs} = \frac{900}{300\sqrt{0{,}2}} = 6{,}7 > 1{,}645$ ⇒ se rechaza H₀.

### Diferencia de proporciones (práctica)

Para H₀: p₁ = p₂ se usa la **proporción combinada** $\hat p = \frac{x_1 + x_2}{n_1 + n_2}$:

$$Z = \frac{\hat p_1 - \hat p_2}{\sqrt{\hat p(1-\hat p)\left(\frac1{n_1} + \frac1{n_2}\right)}} \approx N(0; 1)$$

---

## 8. Potencia de un test

$$1 - \beta(\mu_1) = P(\text{rechazar } H_0 \mid \mu = \mu_1) = P(\bar X \in RC \text{ con } \bar X \sim N(\mu_1;\ \sigma/\sqrt n))$$

La potencia es una **función del valor alternativo μ₁** (curva de potencia). Vale α en μ₀ y tiende a 1 cuanto más lejos de μ₀ está μ₁ (en la dirección de H₁).

**Ejemplo:** X ~ N(μ; 10) cc, n = 12, H₀: μ = 995 vs. H₁: μ < 995, α = 0,05.
- $\bar X \sim N(995;\ 2{,}9)$ ⇒ RC = {$\bar X$ < 990,2}.
- Con $\bar x$ = 993 no se rechaza H₀.
- Potencia si μ₁ = 980: P($\bar X$ < 990,2) con $\bar X$ ~ N(980; 2,9) = 0,99978.
- Potencia si μ₁ = 994: 0,09504. Es baja: un valor alternativo cercano a μ₀ es difícil de detectar.

---

## 9. Tamaño de muestra para α y β dados

Test para la media con σ conocido, unilateral izquierdo (H₁: μ < μ₀), con β fijado en el valor alternativo μ₁:
- **Ecuación I** (α): $x_{crít} = \mu_0 + z_\alpha\frac{\sigma}{\sqrt n}$
- **Ecuación II** (β): $x_{crít} = \mu_1 + z_{1-\beta}\frac{\sigma}{\sqrt n}$

Igualando y despejando:

$$\boxed{n = \left(\frac{\sigma\,(z_\alpha - z_{1-\beta})}{\mu_1 - \mu_0}\right)^2 = \left(\frac{\sigma\,(z_{1-\alpha} + z_{1-\beta})}{\mu_0 - \mu_1}\right)^2} \quad \text{(se redondea hacia arriba)}$$

En un test bilateral se usa $z_{1-\alpha/2}$ en lugar de $z_{1-\alpha}$.

**Ejemplo (dulce de leche):** envases de 500 g, σ = 8 g. H₀: μ = 500 vs. H₁: μ < 500, con α = 0,05 y β = 0,10 si μ = 495:

$n = \left(\frac{8(1{,}645 + 1{,}28)}{5}\right)^2 = 21{,}9$ ⇒ **n = 22**.

Para dos muestras del mismo tamaño (σ conocido) y diferencia δ: $n = \frac{2\sigma^2(z_{1-\alpha} + z_{1-\beta})^2}{\delta^2}$ en cada grupo.

---

## 10. Tabla resumen de tests

| Parámetro | Supuestos | Estadístico (bajo H₀) | Distribución |
|---|---|---|---|
| μ | Normal, σ conocido | $\dfrac{\bar X - \mu_0}{\sigma/\sqrt n}$ | N(0; 1) |
| μ | Normal, σ desconocido | $\dfrac{\bar X - \mu_0}{S/\sqrt n}$ | $t_{n-1}$ |
| μ | n ≥ 30 | $\dfrac{\bar X - \mu_0}{S/\sqrt n}$ | ≈ N(0; 1) |
| σ² | Normal | $\dfrac{(n-1)S^2}{\sigma_0^2}$ | $\chi^2_{n-1}$ |
| p | n grande | $\dfrac{\hat p - p_0}{\sqrt{p_0(1-p_0)/n}}$ | ≈ N(0; 1) |
| μ₁ − μ₂ | Normales, σ conocidos | $\dfrac{\bar X_1 - \bar X_2 - D}{\sqrt{\sigma_1^2/n_1 + \sigma_2^2/n_2}}$ | N(0; 1) |
| μ₁ − μ₂ | Normales, σ₁ = σ₂ desconocidos | $\dfrac{\bar X_1 - \bar X_2 - D}{S_p\sqrt{1/n_1 + 1/n_2}}$ | $t_{n_1+n_2-2}$ |
| p₁ − p₂ | n₁, n₂ grandes | $\dfrac{\hat p_1 - \hat p_2}{\sqrt{\hat p(1-\hat p)(1/n_1 + 1/n_2)}}$ | ≈ N(0; 1) |

### Ejercicios de la guía sugeridos en el material

No es necesario resolver los ejercicios 12, 18 y 20.

---

[← Volver al menú principal](../README.md)
