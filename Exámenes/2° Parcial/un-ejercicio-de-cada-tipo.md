# Un ejercicio de cada tipo del 2.º Parcial

Probabilidad y Estadística — UTN FRBA. Reúne **un ejercicio por cada tipo** que se tomó en los segundos parciales (Tema 1 y Tema 2 del 08/07/2026, Parte B) y en el modelo de la Guía de TP, sin repetir tipos, ordenados por unidad. Sirve para repasar todo el 2.º parcial en un solo lugar.

Cada ejercicio tiene un botón **Solución**. Al abrirlo aparece la respuesta y, arriba de ella, el botón **Solución paso a paso**.

| # | Unidad | Tipo | Origen |
|---|---|---|---|
| 1 | 4 | Distribución de la media muestral | [Modelo de la guía, ej. 4](modelo-segundo-parcial.md) |
| 2 | 4 | Comparación de estimadores (sesgo, varianza, ECM) | [Tema 1, III](segundo-parcial-tema-1.md) |
| 3 | 4 | Teórico: sesgo de un estimador | [Parte B, teórico 1](parcial-parte-b-tema-1.md) |
| 4 | 4 | Teórico: métodos de estimación | [Modelo de la guía, teórico 2](modelo-segundo-parcial.md) |
| 5 | 4 | Intervalo de confianza para μ con muestra grande | [Modelo de la guía, ej. 3](modelo-segundo-parcial.md) |
| 6 | 4 | Intervalo de confianza para σ² y tamaño de muestra para μ | [Tema 1, II](segundo-parcial-tema-1.md) |
| 7 | 5 | Test t para μ y valor p | [Tema 1, IV](segundo-parcial-tema-1.md) |
| 8 | 5 | Test Z para μ y potencia | [Tema 1, V](segundo-parcial-tema-1.md) |
| 9 | 5 | Test para una proporción y β | [Parte B, ej. 1](parcial-parte-b-tema-1.md) |
| 10 | 5 | Teórico: tipos de error, potencia y valor p | [Modelo de la guía, teórico 1](modelo-segundo-parcial.md) |
| 11 | 5 | Teórico: región crítica y tamaño de muestra con α y β | [Parte B, teórico 2](parcial-parte-b-tema-1.md) |
| 12 | 6 | Regresión: significación del modelo e intervalo en x₀ | [Parte B, ej. 2](parcial-parte-b-tema-1.md) |

---

## Unidad 4: distribuciones muestrales y estimación

### 1) Distribución de la media muestral

*Origen: [Modelo de la guía, ej. 4](modelo-segundo-parcial.md).*

Se sabe por experiencias anteriores que el peso de los recién nacidos en cierta localidad se distribuye normalmente con media 3 kg y desviación 400 g. ¿Cuál es la probabilidad de que el promedio de los pesos de los 16 bebés que nacieron ayer supere los 3,2 kg?

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

**Lo primero es notar qué se pregunta:** no es "un bebé pesa más de 3,2", sino "**el promedio** de 16 bebés supera 3,2". Son preguntas distintas.

💡 **Población, muestra y promedio.**
- La **población** son todos los bebés, con media μ = 3 y desvío σ = 0,4 kg.
- Los 16 de ayer son una **muestra**, y su promedio $\bar X$ es una variable aleatoria: otros 16 darían otro promedio.

💡 **Cómo se comporta el promedio.** Al promediar, los bebés pesados y los livianos se compensan, así que el promedio varía **menos** que un bebé solo (📄 H2):

$$\bar X \sim N\left(\mu;\ \frac{\sigma}{\sqrt n}\right)$$

Misma media, desvío dividido por $\sqrt n$. Es Normal porque la población es Normal; si no lo fuera, con n ≥ 30 lo sería aproximadamente (TCL).

$$\bar X \sim N\left(3;\ \frac{0{,}4}{\sqrt{16}}\right) = N(3;\ 0{,}1)$$

```
X~N(μ;σ)   μ=3   σ=0.1   P(X>x)   x=3.2   → 0.02275
```
(Con tabla: estandarizando, 📄 H1, $P(Z > 2) = 0{,}02275$.)

Para comparar: que **un** bebé pese más de 3,2 tiene probabilidad 0,31. Que el promedio de 16 lo haga es mucho más raro.

</details>

**Respuesta:** ≈ 0,0228

</details>

---

### 2) Comparación de estimadores (sesgo, varianza, ECM)

*Origen: [Tema 1, III](segundo-parcial-tema-1.md).*

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

### 3) Teórico: sesgo de un estimador

*Origen: [Parte B, teórico 1](parcial-parte-b-tema-1.md).*

Defina sesgo y encuentre el sesgo del estimador propuesto para la varianza poblacional de una población normal, a partir de una muestra de tamaño 4, si:

$`\displaystyle \hat\theta = \frac{\sum_{i=1}^4 (X_i - \bar X)^2}3 + \frac{\sum_{i=1}^4 X_i^2}4`$

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

💡 **Estimador:** una fórmula con los datos de la muestra para "adivinar" un parámetro desconocido (acá, la varianza σ²). Cambia de muestra en muestra, así que es una variable aleatoria, con su propia esperanza.

**Definición** (❌): el sesgo de un estimador $\hat\theta$ de un parámetro θ es $B(\hat\theta) = E(\hat\theta) - \theta$, cuánto se corre **en promedio** del valor verdadero. El estimador es insesgado si B = 0. Aparece en el error cuadrático medio, $ECM = V(\hat\theta) + B^2$ (📄 H2).

Aquí θ = σ² y n = 4. Se calcula $E(\hat\theta)$ separando los dos términos:
- **Primer término:** divide por n − 1 = 3, así que es exactamente $S^2$, la varianza muestral. Se sabe que $E(S^2) = \sigma^2$ (❌; por eso se divide por n − 1).
- **Segundo término:** $\frac14\sum X_i^2$. Por linealidad (❌), $E = \frac14\cdot4\,E(X^2) = E(X^2)$. De 📄 H1, $V(X) = E(X^2) - E(X)^2$, así que $E(X^2) = \sigma^2 + \mu^2$.

$E(\hat\theta) = \sigma^2 + \sigma^2 + \mu^2 = 2\sigma^2 + \mu^2$.

$B(\hat\theta) = 2\sigma^2 + \mu^2 - \sigma^2 = \sigma^2 + \mu^2$.

</details>

**Respuesta:** $B(\hat\theta) = E(\hat\theta) - \sigma^2 = \sigma^2 + \mu^2$ (> 0): el estimador es sesgado y sobreestima σ².

</details>

---

### 4) Teórico: métodos de estimación

*Origen: [Modelo de la guía, teórico 2](modelo-segundo-parcial.md).*

Explicar dos métodos de estimación y ejemplificar. ¿Cómo se puede seleccionar entre dos estimadores de un parámetro?

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

💡 **Qué es estimar.** Un **estimador** es una fórmula con los datos de la muestra para "adivinar" un parámetro desconocido de la población. Los métodos de estimación son **recetas para fabricar** esa fórmula. Nada de esto está en la hoja (❌), salvo el ECM.

**1. Método de los momentos** ("lo teórico igual a lo observado"): se igualan los momentos poblacionales (E(X), E(X²), …), que dependen del parámetro, a los momentos muestrales ($`\bar X`$, $\frac1n\sum X_i^2$, …), y se despeja el parámetro.

Ejemplo: en una Exp(λ), $E(X) = 1/\lambda = \bar X \Rightarrow \hat\lambda = 1/\bar X$.

**2. Máxima verosimilitud** ("el valor que hace más probable lo que salió"): se elige el valor del parámetro con el que la muestra observada es la más probable. Se maximiza $L(\theta) = \prod f(x_i; \theta)$, el producto porque las observaciones son independientes. En general se deriva $\ln L$ (más fácil, porque convierte productos en sumas) y se iguala a 0.

Ejemplo: en una Poisson(λ), $\ln L = \sum x_i\ln\lambda - n\lambda - \sum\ln x_i!$ ⇒ $\hat\lambda = \bar X$.

(En la regresión se usa además **mínimos cuadrados**: se minimiza $\sum e_i^2$.)

**Selección entre dos estimadores:** un estimador es una variable aleatoria (cambia con la muestra). Se le pide que no apunte corrido y que no se disperse mucho:
- **Insesgadez:** $E(\hat\theta) = \theta$, que en promedio acierte. La diferencia $B = E(\hat\theta) - \theta$ es el sesgo.
- **Menor varianza** entre los insesgados (más eficiente).
- En general, el de **menor error cuadrático medio**, que junta las dos cosas: $ECM(\hat\theta) = V(\hat\theta) + B(\hat\theta)^2$ (📄 H2).
- **Consistencia:** con más datos se acerca al valor verdadero (V → 0 cuando n → ∞).

Ejemplo: $\bar X$ y $T = \frac16(X_1 + X_2) + \frac13(X_3 + X_4)$ son insesgados para μ, pero $V(\bar X) = \sigma^2/4 < V(T) = 5\sigma^2/18$ ⇒ se elige $\bar X$.

</details>

**Respuesta:** Momentos (igualar momentos poblacionales y muestrales) y máxima verosimilitud (maximizar L(θ)). Se elige el estimador insesgado de menor varianza o, en general, el de menor ECM.

</details>

---

### 5) Intervalo de confianza para μ con muestra grande

*Origen: [Modelo de la guía, ej. 3](modelo-segundo-parcial.md).*

Se desea estimar el tiempo medio de espera en una cola de supermercado los días domingos al mediodía. Para ello se tomó el tiempo de espera de 100 clientes en diferentes días domingo en el mismo supermercado, y la muestra arrojó un promedio de 20 minutos con una dispersión de 3 minutos.

- a) Hallar un intervalo del 98 % de confianza para el tiempo promedio.
- b) Hallar el tamaño de muestra necesario para reducir a la mitad la longitud de dicho intervalo.

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

**La situación:** se conoce el promedio de la muestra ($`\bar x`$ = 20) y se quiere averiguar μ, el tiempo medio de **todos** los domingos.

**a)** 💡 **Por qué un intervalo.** μ casi seguro no es exactamente 20: con otros 100 clientes habría dado 19,6 o 20,3. En lugar de un número, se da un rango con una confianza: un **intervalo de confianza (IC)**.

💡 **De dónde sale.**
1. El promedio de una muestra varía alrededor de μ con desvío $\frac{\sigma}{\sqrt n}$ (📄 H2, $`\bar X \sim N(\mu;\ \sigma/\sqrt n)`$).
2. En una normal, el 98 % de los valores está a menos de z desvíos del centro, con z el que deja 1 % en cada cola (0,99 a la izquierda). Entonces el 98 % de las veces, $\bar x$ está a menos de $z\frac{\sigma}{\sqrt n}$ de μ.
3. Si $\bar x$ está cerca de μ, μ está igual de cerca de $\bar x$. Por eso el IC es "promedio ± margen".

💡 **¿Qué pasa si no se conoce σ?** La "dispersión de 3 minutos" es de **la muestra** (S). La fórmula exacta usa S y la **t de Student** con n − 1 grados de libertad, que es un poco más grande para compensar no conocer σ (📄 H2):

$`\displaystyle I.C._\mu = \left(\bar X \mp t_{n-1;1-\frac\alpha2}\cdot\frac{S}{\sqrt n}\right)`$

Con n ≥ 30 la t es casi igual a la z, y el repo usa z con S (IC "asintótico"). Las dos opciones:
```
X~t(ν)     ν=99         P(X<x)=0.99   → x=2.36461
X~N(μ;σ)   μ=0   σ=1    P(X<x)=0.99   → x=2.32635
```
- Con z: $d = 2{,}326\cdot\frac{3}{\sqrt{100}} = 0{,}698$, así que $I.C._\mu = (19{,}30;\ 20{,}70)$ min.
- Con t: $d = 0{,}709$, así que (19,29; 20,71).

💡 **Interpretación** (❌): μ es fijo. Lo que varía es el intervalo, según la muestra. El método acierta en el 98 % de las muestras: se dice "**confío** al 98 %", no "hay 98 % de probabilidad".

**b)** La longitud es punta derecha menos izquierda: $L = 2\cdot z\cdot\frac{S}{\sqrt n}$. n está **dentro de una raíz, en el denominador**: para que L sea la mitad, $\sqrt n$ tiene que ser el doble, y entonces **n se cuadruplica**: n = 4·100 = **400**.

</details>

**Respuesta:**

- a) $IC_{98} = [19{,}30;\ 20{,}70]$ minutos
- b) n = 400

</details>

---

### 6) Intervalo de confianza para σ² y tamaño de muestra para μ

*Origen: [Tema 1, II](segundo-parcial-tema-1.md).*

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

## Unidad 5: tests de hipótesis

### 7) Test t para μ y valor p

*Origen: [Tema 1, IV](segundo-parcial-tema-1.md).*

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

### 8) Test Z para μ y potencia

*Origen: [Tema 1, V](segundo-parcial-tema-1.md).*

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

### 9) Test para una proporción y β

*Origen: [Parte B, ej. 1](parcial-parte-b-tema-1.md).*

Un fabricante produce piezas de metal que se emplean en construcciones. El cliente requiere que la fracción de piezas defectuosas en uno de los pasos de manufactura críticos sea menor que 0,04, y que el fabricante demuestre esta característica del proceso de fabricación con este nivel de calidad, utilizando un nivel de significación de 0,01. El fabricante toma una muestra aleatoria de 1000 dispositivos y encuentra que 9 de ellos son defectuosos.

- a) ¿Puede el fabricante demostrar al cliente la calidad del proceso con el nivel de significación indicado?
- b) Suponga que la fracción de defectuosos del proceso es p = 0,02. ¿Cuál es en este caso la probabilidad de cometer error de tipo II?

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

💡 **Test de hipótesis, como un juicio.** H₀ es lo que se da por cierto salvo evidencia fuerte en contra, y lleva la igualdad. H₁ es lo que se quiere **demostrar**.

p = fracción de defectuosas de **toda** la producción, desconocida. $\hat p$ = fracción en la muestra = 9/1000 = 0,009.

**a)**
1. **Hipótesis.** "El fabricante debe **demostrar** p < 0,04", así que eso va en H₁:

   $`\displaystyle H_0: p \ge 0{,}04 \qquad H_1: p < 0{,}04`$

2. **α = 0,01**, el riesgo aceptado de rechazar H₀ siendo cierta.
3. 💡 **Estadístico.** Cada pieza es un 1 (defectuosa) o un 0, y $\hat p$ es el promedio, así que por el TCL es aproximadamente Normal (📄 H2, $`\hat p \sim N\left(p;\ \sqrt{\frac{p(1-p)}{n}}\right)`$). Se estandariza **suponiendo H₀ cierta**, así que en la raíz va **p₀ = 0,04**, no $\hat p$:

   $$Z = \frac{\hat p - 0{,}04}{\sqrt{0{,}04\cdot0{,}96/1000}} \approx N(0;1), \qquad \sigma_0 = 0{,}0062$$

4. $z_{obs} = \frac{0{,}009 - 0{,}04}{0{,}0062} = -5{,}0$.
5. 💡 **Región crítica:** del lado de H₁ (izquierda), con área α:
   ```
   X~N(μ;σ)   μ=0   σ=1   P(X<x)=0.01   → x=−2.32635
   ```
   RC = {Z < −2,326}. En la escala de $\hat p$: $\hat p < 0{,}04 - 2{,}326\cdot0{,}0062 = 0{,}0256$. Como −5 está en la RC, **se rechaza H₀** (valor p ≈ 3·10⁻⁷).

**Conclusión:** **sí**, el fabricante demuestra al 1 % que la fracción de defectuosas es menor a 0,04.

**b)** 💡 **Error tipo II (β):** no rechazar H₀ cuando es falsa. Si en verdad p = 0,02, H₀ es falsa, y el error sería no detectarlo.

**Receta** (❌): la frontera se arma con p₀ (ya está: 0,0256), y la probabilidad se calcula con el p **verdadero**. ⚠️ El desvío **cambia**, porque depende de p:

$$\sigma_1 = \sqrt{\frac{0{,}02\cdot0{,}98}{1000}} = 0{,}00443$$

$$\beta = P(\hat p \ge 0{,}0256) \text{ con } \hat p \sim N(0{,}02;\ 0{,}00443)$$

```
X~N(μ;σ)   μ=0.02   σ=0.00443   P(X>x)   x=0.0256   → 0.1035
```
**β ≈ 0,104.** Si el proceso tiene 2 % de defectuosas, un 10 % de las veces no se lograría demostrarlo.

</details>

**Respuesta:**

- a) Sí: $z_{obs}$ = −5 < −2,326 ⇒ se rechaza H₀: p ≥ 0,04; el fabricante demuestra que p < 0,04 al 1 %
- b) β ≈ 0,1035

</details>

---

### 10) Teórico: tipos de error, potencia y valor p

*Origen: [Modelo de la guía, teórico 1](modelo-segundo-parcial.md).*

Definir los tipos de errores de una prueba estadística y vincular estos conceptos con la potencia de la prueba y el p valor.

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

💡 **Contexto.** En un test de hipótesis, H₀ es lo que se da por cierto salvo evidencia en contra, y H₁ es lo que se quiere demostrar (como en un juicio: "inocente" contra "culpable"). Se decide con una muestra, así que uno se puede equivocar de dos maneras. Nada de esto está en la hoja (❌).

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

### 11) Teórico: región crítica y tamaño de muestra con α y β

*Origen: [Parte B, teórico 2](parcial-parte-b-tema-1.md).*

En un test de hipótesis:

- a) ¿Qué representa la región crítica?
- b) Deduzca la selección del tamaño de la muestra en un test para la media de población normal con desvío conocido, conocidas las probabilidades de cometer ambos errores.

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

💡 **Contexto.** En un test, H₀ se da por cierta salvo evidencia en contra, y H₁ es lo que se quiere demostrar. Hay dos errores posibles:
- **tipo I:** rechazar H₀ siendo cierta, con probabilidad α;
- **tipo II:** no rechazar H₀ siendo falsa, con probabilidad β.

Nada de esto está en la hoja (❌).

**a)** La **región crítica** (de rechazo) es el conjunto de valores del estadístico de prueba que llevan a rechazar H₀. Se construye en la dirección de H₁ y de modo que, si H₀ es verdadera, la probabilidad de caer en ella sea α: P(E.P. ∈ RC | H₀) = α. Su borde es el valor crítico.

**b) La idea:** se quieren fijar α **y** β a la vez. Hay dos incógnitas, la frontera $x_c$ y el tamaño n. Cada error da una ecuación para $x_c$, y se igualan.

**Planteo:** test unilateral izquierdo, H₀: μ = μ₀ vs. H₁: μ < μ₀, con X ~ N(μ; σ) y σ conocido. Se rechaza si $\bar X < x_c$, con $\bar X \sim N(\mu;\ \sigma/\sqrt n)$ (📄 H2). Se fijan α y β (este último en un valor alternativo μ₁ < μ₀). Se estandariza con 📄 H1.

**Ecuación I** (α):

$\alpha = P(\bar X < x_c \mid \mu_0) \Rightarrow \frac{x_c - \mu_0}{\sigma/\sqrt n} = z_\alpha \Rightarrow x_c = \mu_0 + z_\alpha\frac\sigma{\sqrt n}$.

**Ecuación II** (β):

$\beta = P(\bar X > x_c \mid \mu_1) \Rightarrow \frac{x_c - \mu_1}{\sigma/\sqrt n} = z_{1-\beta} \Rightarrow x_c = \mu_1 + z_{1-\beta}\frac\sigma{\sqrt n}$.

**Igualando:**

$\mu_0 + z_\alpha\frac\sigma{\sqrt n} = \mu_1 + z_{1-\beta}\frac\sigma{\sqrt n} \Rightarrow \sqrt n = \frac{\sigma(z_\alpha - z_{1-\beta})}{\mu_1 - \mu_0}$.

$`\displaystyle n = \left(\frac{\sigma(z_{1-\alpha} + z_{1-\beta})}{\mu_0 - \mu_1}\right)^2`$

Se redondea hacia arriba. En el bilateral se usa $z_{1-\alpha/2}$.

</details>

**Respuesta:**

- a) El conjunto de valores del estadístico para los que se rechaza H₀, con P(RC | H₀) = α
- b) $n = \left(\dfrac{\sigma(z_{1-\alpha} + z_{1-\beta})}{\mu_0 - \mu_1}\right)^2$, redondeado hacia arriba

</details>

---

## Unidad 6: regresión

### 12) Regresión: significación del modelo e intervalo en x₀

*Origen: [Parte B, ej. 2](parcial-parte-b-tema-1.md).*

Una compañía productora de energía eléctrica está interesada en desarrollar un modelo que relacione la demanda pico por hora (Y, en kW) con el uso de la energía total al mes (X, en kWh). Las variables se distribuyen en forma normal bivariada. La siguiente tabla muestra los datos obtenidos de una muestra de 5 clientes:

| X (kWh) | 997 | 2190 | 1087 | 2087 | 2081 |
|---|---|---|---|---|---|
| **Y (kW)** | 1,65 | 4,05 | 1,84 | 3,88 | 4,87 |

- a) Pruebe la significatividad de la regresión a un nivel de significación del 1 %.
- b) Encuentre un intervalo de confianza para un x₀ = 1050 kWh con un nivel del 99 %. Interprételo.

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

💡 **Regresión lineal:** se busca la recta $\hat y = b_0 + b_1x$ (📄 H2) que pasa más cerca de los puntos (mínimos cuadrados), con $b_1 = \frac{S_{xy}}{S_{xx}}$ y $b_0 = \bar y - b_1\bar x$ (📄 H2). La Calculadora de estadística → **Regresión lineal** da $b_0$ y $b_1$ cargando los pares.

**Sumas** (n = 5): $\sum x = 8442$, $\sum y = 16{,}29$, $\sum x^2 = 15.657.808$, $\sum y^2 = 61{,}2819$, $\sum xy = 30.746{,}66$.

**Cantidades básicas** (📄 H2, $S_{xx} = \sum x^2 - \frac{(\sum x)^2}{n}$, etc.): $\bar x = 1688{,}4$ y $\bar y = 3{,}258$.
- $S_{xx} = 1.404.335{,}2$
- $S_{yy} = 8{,}2091$
- $S_{xy} = 3242{,}62$

**Recta estimada:** $b_1 = \frac{3242{,}62}{1404335{,}2} = 0{,}002309$ y $b_0 = 3{,}258 - 0{,}002309\cdot1688{,}4 = -0{,}6405$ ⇒ $\hat y = -0{,}6405 + 0{,}00231x$.

**a)** 💡 **Significatividad de la regresión:** ¿la relación es real o pudo salir por casualidad con tan pocos puntos? Se testea si la pendiente verdadera β₁ (o la correlación ρ) es 0. Si lo fuera, X no serviría para predecir Y.

💡 **Coeficiente de correlación r** (📄 H2, $`r = \frac{S_{xy}}{\sqrt{S_{xx}S_{yy}}}`$): mide qué tan alineados están los puntos (de −1 a 1).

1. H₀: β₁ = 0 (equivale a ρ = 0) vs. H₁: β₁ ≠ 0. Lo que se quiere demostrar va en H₁.
2. α = 0,01.
3. Estadístico (📄 H2, $`\sqrt{n-2}\frac{r}{\sqrt{1-r^2}} = t_{n-2}`$): $T \sim t_3$ si H₀ es cierta.
4. $r = 0{,}955$ ($`R^2 = 0{,}912`$), así que $t_{obs} = \sqrt3\cdot\frac{0{,}955}{\sqrt{1 - 0{,}912}} = 5{,}58$.
5. Bilateral, α/2 = 0,005 en cada cola:
   ```
   X~t(ν)   ν=3   P(X<x)=0.995   → x=5.84091
   X~t(ν)   ν=3   P(X>x)   x=5.578   → 0.0057   → p = 0.0114
   ```
   5,58 < 5,841: **no se rechaza H₀** (p = 0,011).

**La lección:** R² = 0,91 parece altísimo, pero con solo 5 datos (3 grados de libertad) la t es muy exigente: con tan pocos puntos, un buen alineamiento puede ser casualidad. Al 5 % sí sería significativa ($`t_{3;\,0{,}975}`$ = 3,18).

**b)** 💡 **Qué se estima:** la demanda pico **media** de **todos** los clientes que consumen 1050 kWh, no la de uno solo. La estimación puntual es la recta:

$$\hat y(1050) = -0{,}6405 + 0{,}002309\cdot1050 = 1{,}784 \text{ kW}$$

💡 **IC para la media de Y en x₀** (❌, no está en la hoja). Tiene la forma de siempre, estimación ± t · error estándar:

$`\displaystyle \hat y_0 \pm t_{n-2;1-\frac\alpha2}\cdot s\sqrt{\frac1n + \frac{(x_0 - \bar x)^2}{S_{xx}}}`$

- s mide cuánto se apartan los puntos de la recta: $s^2 = \hat\sigma^2 = \frac{SC_{res}}{n-2}$ (📄 H2), con $SC_{res} = S_{yy} - \frac{S_{xy}^2}{S_{xx}}$.
- El término con $(x_0 - \bar x)^2$ hace el intervalo más ancho cuanto más lejos está x₀ del centro de los datos.

$$SC_{res} = 0{,}7218 \;\Rightarrow\; s = \sqrt{0{,}7218/3} = 0{,}4905$$

$$IC = 1{,}784 \pm 5{,}841\cdot0{,}4905\sqrt{0{,}2 + \frac{(1050 - 1688{,}4)^2}{1404335{,}2}} = 1{,}784 \pm 2{,}006$$

Resultado: (−0,22; 3,79) kW.

**Interpretación:** con 99 % de confianza, la demanda pico **media** de los clientes que consumen 1050 kWh al mes está entre −0,22 y 3,79 kW (en la práctica, entre 0 y 3,79). Es muy ancho por el n chico; además, al no ser significativa la regresión al 1 %, la estimación es poco confiable.

</details>

**Respuesta:**

- a) $t_{obs}$ = 5,58 < 5,841 ⇒ no se rechaza H₀: la regresión no es significativa al 1 % (p ≈ 0,011)
- b) $\hat y(1050)$ = 1,78 kW; $IC_{99}$ = [−0,22; 3,79] kW para la demanda pico media con x = 1050

</details>

---

[← Volver al menú principal](../../README.md)
