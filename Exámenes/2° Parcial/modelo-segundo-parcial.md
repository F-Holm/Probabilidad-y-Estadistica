# Modelo de 2.º Parcial (Guía de TP, cap. 7.2)

Probabilidad y Estadística — UTN FRBA. Modelo de examen que aparece al final de la [Guía de Trabajos Prácticos](../../GU%C3%8DA%20DE%20TPs.pdf).

> **Aprobación:** dos prácticos y un teórico correctos. Todas las respuestas deben estar debidamente justificadas.

Cada ejercicio tiene un botón **Solución**. Al abrirlo aparece la respuesta y, arriba de ella, el botón **Solución paso a paso**.

---

### Ejercicio 1) Antigüedad y llegadas tarde

La siguiente tabla exhibe las antigüedades de los empleados de una cierta fábrica, medidas en años, y el número de llegadas tarde de un mes elegido al azar del 2017:

| Antigüedad (años) | 4 | 4,6 | 5,3 | 6,4 | 6,7 | 7 |
|---|---|---|---|---|---|---|
| **Llegadas tarde (en el mes)** | 2 | 3 | 3 | 4 | 5 | 5 |

- a) Hallar un modelo lineal que permita estimar la cantidad de llegadas tarde en función de la antigüedad del empleado.
- b) ¿Se pueden estimar con este modelo las llegadas tarde de un individuo que tiene 20 años en la empresa?
- c) Estudiar mediante un test de nivel 0,05 la validez de este modelo lineal.

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

X = antigüedad, Y = llegadas tarde, n = 6.

**Sumas:** $\sum x = 34$, $\sum y = 22$, $\sum x^2 = 200{,}1$, $\sum y^2 = 88$, $\sum xy = 131{,}8$.

**Cantidades básicas:**
- $S_{xx} = 200{,}1 - \frac{34^2}6 = 7{,}433$
- $S_{yy} = 88 - \frac{22^2}6 = 7{,}333$
- $S_{xy} = 131{,}8 - \frac{34\cdot22}6 = 7{,}133$

a) $b_1 = \frac{7{,}133}{7{,}433} = 0{,}9596$ y $b_0 = \bar y - b_1\bar x = 3{,}667 - 0{,}9596\cdot5{,}667 = -1{,}7713$.

$\hat y = -1{,}7713 + 0{,}9596x$, válido para 4 ≤ x ≤ 7.

b) **No:** x = 20 está muy fuera del rango observado (4 a 7 años). Sería extrapolar, y nada garantiza que la relación siga siendo lineal.

c) **Test de correlación** (supuestos: errores normales, independientes y con varianza constante):
1. H₀: ρ = 0 vs. H₁: ρ ≠ 0.
2. α = 0,05.
3. $T = \frac{r\sqrt{n-2}}{\sqrt{1 - r^2}} \sim t_4$.
4. $r = \frac{7{,}133}{\sqrt{7{,}433\cdot7{,}333}} = 0{,}9662$ ($R^2 = 0{,}9335$) ⇒ $t_{obs} = \frac{0{,}9662\cdot2}{\sqrt{1 - 0{,}9335}} = 7{,}5$.
5. RC = {|T| > $t_{4;\,0{,}975}$ = 2,776}. Como 7,5 ∈ RC ⇒ se rechaza H₀ (p ≈ 0,0017).

</details>

**Respuesta:**

- a) $\hat y = -1{,}7713 + 0{,}9596x$ (R² = 0,9335)
- b) No, porque 20 años está fuera del rango de los datos (4 a 7)
- c) $t_{obs}$ = 7,5 > 2,776 ⇒ se rechaza ρ = 0: el modelo lineal es válido al 5 %

</details>

---

### Ejercicio 2) Duración de neumáticos

El fabricante de neumáticos sostiene que en promedio sus productos tienen una duración no menor a 50 mil km antes de necesitar reemplazo. Un grupo de consumidores quiere poner a prueba dicha afirmación, suponiendo que la distribución de la duración es normal.

- a) Plantee las hipótesis a contrastar, el estadístico del test junto con su función de distribución, la región de rechazo y la decisión tomada a nivel aproximado 0,05.
- b) Si una muestra de 30 neumáticos arrojó un promedio de 49 mil km y un desvío de 3 mil km, ¿cuál es el p valor de la prueba?

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

μ = duración media real (miles de km). Los consumidores sospechan que es menor que 50.

a) Test:
1. H₀: μ ≥ 50 vs. H₁: μ < 50 (la afirmación del fabricante queda en H₀).
2. α = 0,05.
3. Población normal y σ desconocido ⇒ $T = \frac{\bar X - 50}{S/\sqrt n} \sim t_{n-1}$ bajo H₀.
4. Con los datos de b) (n = 30, $\bar x$ = 49, s = 3): $t_{obs} = \frac{49 - 50}{3/\sqrt{30}} = -1{,}826$.
5. RC = {T < $t_{29;\,0{,}05}$ = −1,699}. Como −1,826 ∈ RC ⇒ se rechaza H₀.

Como n = 30, también se puede usar Z: RC = {Z < −1,645}, con la misma decisión.

b) p valor = $P(t_{29} < -1{,}826) = 0{,}039$ (con la normal, 0,034). Como es menor que 0,05, se rechaza H₀.

</details>

**Respuesta:**

- a) H₀: μ ≥ 50 vs. H₁: μ < 50; $T = \dfrac{\bar X - 50}{S/\sqrt n} \sim t_{29}$; RC = {T < −1,699}; $t_{obs}$ = −1,83 ⇒ se rechaza la afirmación del fabricante
- b) p valor ≈ 0,039 (≈ 0,034 con la aproximación normal)

</details>

---

### Ejercicio 3) Espera en el supermercado

Se desea estimar el tiempo medio de espera en una cola de supermercado los días domingos al mediodía. Para ello se tomó el tiempo de espera de 100 clientes en diferentes días domingo en el mismo supermercado, y la muestra arrojó un promedio de 20 minutos con una dispersión de 3 minutos.

- a) Hallar un intervalo del 98 % de confianza para el tiempo promedio.
- b) Hallar el tamaño de muestra necesario para reducir a la mitad la longitud de dicho intervalo.

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

σ desconocido, pero n = 100 ≥ 30 ⇒ IC asintótico con z.

a) 1 − α = 0,98 ⇒ $z_{0{,}99} = 2{,}33$.

$d = 2{,}33\cdot\frac3{\sqrt{100}} = 0{,}699$ ⇒ $IC_\mu = [20 - 0{,}699;\ 20 + 0{,}699] = [19{,}30;\ 20{,}70]$ min.

b) La semiamplitud es $d = z\frac s{\sqrt n}$, proporcional a $1/\sqrt n$. Para que d se reduzca a la mitad, $\sqrt n$ se tiene que duplicar ⇒ n se cuadruplica: n = 4·100 = **400**.

</details>

**Respuesta:**

- a) $IC_{98} = [19{,}30;\ 20{,}70]$ minutos
- b) n = 400

</details>

---

### Ejercicio 4) Peso de recién nacidos

Se sabe por experiencias anteriores que el peso de los recién nacidos en cierta localidad se distribuye normalmente con media 3 kg y desviación 400 g. ¿Cuál es la probabilidad de que el promedio de los pesos de los 16 bebés que nacieron ayer supere los 3,2 kg?

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

X ~ N(3; 0,4) kg. El promedio de 16 normales independientes es normal:

$\bar X \sim N\left(3;\ \frac{0{,}4}{\sqrt{16}}\right) = N(3;\ 0{,}1)$.

$P(\bar X > 3{,}2) = P\left(Z > \frac{3{,}2 - 3}{0{,}1}\right) = P(Z > 2) = 0{,}02275$.

</details>

**Respuesta:** ≈ 0,0228

</details>

---

### Teórico 1) Errores, potencia y valor p

Definir los tipos de errores de una prueba estadística y vincular estos conceptos con la potencia de la prueba y el p valor.

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

| | H₀ verdadera | H₀ falsa |
|---|---|---|
| Rechazar H₀ | Error tipo I (prob. α) | Correcto (prob. 1 − β) |
| No rechazar H₀ | Correcto (prob. 1 − α) | Error tipo II (prob. β) |

- **Error de tipo I:** rechazar H₀ cuando es verdadera. Su probabilidad máxima es α, el **nivel de significación**, que se fija a priori.
- **Error de tipo II:** no rechazar H₀ cuando es falsa. Su probabilidad β depende del verdadero valor del parámetro (valor alternativo).
- **Potencia:** 1 − β = P(rechazar H₀ | H₀ falsa), la capacidad del test de detectar que H₀ es falsa. Es función del valor alternativo: vale α en θ₀ y tiende a 1 al alejarse.
- Para n fijo, si se achica α, crece β (baja la potencia). Para achicar ambos hay que aumentar n.
- **Valor p:** probabilidad, suponiendo H₀ verdadera, de obtener un valor del estadístico tan extremo o más que el observado (en la dirección de H₁). Es el menor α con el que se rechaza H₀ con esos datos: se rechaza si p < α. Un p chico indica evidencia contra H₀. α es fijo; p depende de la muestra.

</details>

**Respuesta:** Tipo I = rechazar H₀ verdadera (prob. α, nivel de significación). Tipo II = no rechazar H₀ falsa (prob. β). Potencia = 1 − β. Se rechaza H₀ cuando el valor p < α.

</details>

---

### Teórico 2) Métodos de estimación

Explicar dos métodos de estimación y ejemplificar. ¿Cómo se puede seleccionar entre dos estimadores de un parámetro?

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

**1. Método de los momentos:** se igualan los momentos poblacionales (E(X), E(X²), …), que dependen del parámetro, a los momentos muestrales ($\bar X$, $\frac1n\sum X_i^2$, …), y se despeja el parámetro.

Ejemplo: en una Exp(λ), $E(X) = 1/\lambda = \bar X \Rightarrow \hat\lambda = 1/\bar X$.

**2. Máxima verosimilitud:** se elige el valor del parámetro que hace más probable la muestra observada. Se maximiza $L(\theta) = \prod f(x_i; \theta)$; en general se deriva $\ln L$ y se iguala a 0.

Ejemplo: en una Poisson(λ), $\ln L = \sum x_i\ln\lambda - n\lambda - \sum\ln x_i!$ ⇒ $\hat\lambda = \bar X$.

(En la regresión se usa además **mínimos cuadrados**: se minimiza $\sum e_i^2$.)

**Selección entre dos estimadores:** se comparan sus propiedades:
- **Insesgadez:** $E(\hat\theta) = \theta$.
- **Menor varianza** entre los insesgados (más eficiente).
- En general, el de **menor error cuadrático medio**: $ECM(\hat\theta) = V(\hat\theta) + B(\hat\theta)^2$.
- **Consistencia** (V → 0 cuando n → ∞).

Ejemplo: $\bar X$ y $T = \frac16(X_1 + X_2) + \frac13(X_3 + X_4)$ son insesgados para μ, pero $V(\bar X) = \sigma^2/4 < V(T) = 5\sigma^2/18$ ⇒ se elige $\bar X$.

</details>

**Respuesta:** Momentos (igualar momentos poblacionales y muestrales) y máxima verosimilitud (maximizar L(θ)). Se elige el estimador insesgado de menor varianza o, en general, el de menor ECM.

</details>

---

[← Volver al menú principal](../../README.md)
