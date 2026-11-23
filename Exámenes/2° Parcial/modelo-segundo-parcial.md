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

**La situación:** hay **dos variables por persona**, X = antigüedad e Y = llegadas tarde, con n = 6. Se quiere ver si Y depende de X en forma de **recta**.

**a)** 💡 **Regresión lineal.** Se busca la recta $\hat y = b_0 + b_1x$ (📄 H2) que pasa "lo más cerca posible" de los puntos: la que hace mínima la suma de las distancias verticales al cuadrado (**mínimos cuadrados**).
- **$b_1$ (pendiente):** cuánto sube y, en promedio, por cada unidad que sube x.
- **$b_0$ (ordenada):** el valor de la recta en x = 0.

**Sumas:** $\sum x = 34$, $\sum y = 22$, $\sum x^2 = 200{,}1$, $\sum y^2 = 88$, $\sum xy = 131{,}8$.

**Cantidades básicas** (📄 H2):
- $S_{xx} = \sum x^2 - \frac{(\sum x)^2}{n} = 200{,}1 - \frac{34^2}{6} = 7{,}433$
- $S_{yy} = 88 - \frac{22^2}{6} = 7{,}333$
- $S_{xy} = \sum xy - \frac{\sum x\sum y}{n} = 131{,}8 - \frac{34\cdot22}{6} = 7{,}133$

**Recta** (📄 H2):

```math
b_1 = \frac{S_{xy}}{S_{xx}} = \frac{7{,}133}{7{,}433} = 0{,}9596 \qquad b_0 = \bar y - b_1\bar x = 3{,}667 - 0{,}9596\cdot5{,}667 = -1{,}7713
```

```math
\hat y = -1{,}7713 + 0{,}9596x \quad (\text{válido para } 4 \le x \le 7)
```

Cada año más de antigüedad suma, en promedio, casi una llegada tarde por mes.

**Con las apps:** Calculadora de estadística → **Regresión lineal** con los 6 pares da $b_0$ y $b_1$. Para $S_{xx}$ sirve la descriptiva: $S_{xx} = (n-1)s_x^2$ (❌).

**b) No.** La recta solo se probó para x entre 4 y 7 años. Usarla en 20 es **extrapolar** (❌): nada asegura que la relación siga siendo una recta tan lejos de los datos. Daría 17 llegadas tarde por mes, un número absurdo.

**c)** 💡 **Coeficiente de correlación r** (📄 H2, $`r = \frac{S_{xy}}{\sqrt{S_{xx}S_{yy}}}`$): mide qué tan alineados están los puntos (de −1 a 1). Con pocos puntos, una muestra puede salir alineada por casualidad. El **test** decide si la correlación de la población, ρ, es distinta de 0.

**Supuestos** (❌): errores normales, independientes y con la misma varianza para todo x.

1. H₀: ρ = 0 (no hay relación lineal) vs. H₁: ρ ≠ 0. Lo que se quiere demostrar va en H₁.
2. α = 0,05.
3. Estadístico (📄 H2, $`\sqrt{n-2}\frac{r}{\sqrt{1-r^2}} = t_{n-2}`$): $T \sim t_4$ si H₀ es cierta.
4. $r = \frac{7{,}133}{\sqrt{7{,}433\cdot7{,}333}} = 0{,}9662$ ($`R^2 = 0{,}9335`$), así que $t_{obs} = \sqrt4\cdot\frac{0{,}9662}{\sqrt{1 - 0{,}9335}} = 7{,}49$.
5. H₁ es "≠", así que es bilateral, con α/2 = 0,025 en cada cola:
   ```
   X~t(ν)   ν=4   P(X<x)=0.975   → x=2.77645
   X~t(ν)   ν=4   P(X>x)   x=7.49   → 0.00085   → p = 2·0.00085 = 0.0017
   ```
   7,5 > 2,776: **se rechaza H₀**.

**Conclusión:** hay correlación lineal significativa, así que el modelo es **válido** al 5 %. El 93 % de la variabilidad de las llegadas tarde se explica por la antigüedad ($`R^2`$, 📄 H2).

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

💡 **Test de hipótesis: funciona como un juicio.**
- **H₀** es "el inocente": se da por cierta salvo evidencia fuerte en contra. Siempre lleva la igualdad (=, ≤ o ≥).
- **H₁** es lo que se quiere demostrar: una desigualdad estricta.
- Si la muestra es contundente, se rechaza H₀. Si no, no se rechaza, lo que **no** prueba que H₀ sea cierta.

μ = duración media real de **todos** los neumáticos (en miles de km).

**a)**
1. **Hipótesis.** La trampa: "no menor a 50" es **μ ≥ 50**, que **incluye la igualdad**, así que tiene que ir en H₀. Los consumidores sospechan lo contrario, y eso va en H₁:

   ```math
   H_0: \mu \ge 50 \qquad H_1: \mu < 50
   ```

   (Si el fabricante dijera "**más de** 50", su afirmación iría en H₁.)
2. **α = 0,05**, el riesgo aceptado de rechazar H₀ siendo cierta.
3. 💡 **Estadístico.** Se mide a cuántos desvíos de 50 cayó el promedio de la muestra. Como el desvío de la población no se conoce, se usa el de la muestra (S), y el estadístico es una **t de Student** con n − 1 grados de libertad: una campana con colas más gordas que la normal (📄 H2, tal cual):

   ```math
   T = \frac{\bar X - 50}{S/\sqrt n} \sim t_{n-1}
   ```

4. Con los datos de b) (n = 30, $\bar x$ = 49, s = 3):

   ```math
   t_{obs} = \frac{49 - 50}{3/\sqrt{30}} = -1{,}826
   ```

5. 💡 **Región crítica:** los valores de T que llevan a rechazar, del lado de H₁ (izquierda), con área α:
   ```
   X~t(ν)   ν=29   P(X<x)=0.05   → x=−1.69913
   ```
   RC = {T < −1,699}. Como −1,826 < −1,699, **se rechaza H₀**.

**Conclusión:** hay evidencia al 5 % de que la duración media es **menor** a 50 mil km. Se rechaza la afirmación del fabricante.

"Nivel aproximado" porque, con n = 30, también se puede usar Z: RC = {Z < −1,645}, con la misma decisión.

**b)** 💡 **Valor p:** la probabilidad, si H₀ fuera cierta, de un resultado tan extremo o más que el observado, del lado de H₁. Se rechaza si p < α.
```
X~t(ν)   ν=29   P(X<x)   x=−1.826   → 0.0391
```
p ≈ 0,039 < 0,05, coherente con a). Con la normal da 0,034.

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

**La situación:** se conoce el promedio de la muestra ($`\bar x`$ = 20) y se quiere averiguar μ, el tiempo medio de **todos** los domingos.

**a)** 💡 **Por qué un intervalo.** μ casi seguro no es exactamente 20: con otros 100 clientes habría dado 19,6 o 20,3. En lugar de un número, se da un rango con una confianza: un **intervalo de confianza (IC)**.

💡 **De dónde sale.**
1. El promedio de una muestra varía alrededor de μ con desvío $\frac{\sigma}{\sqrt n}$ (📄 H2, $`\bar X \sim N(\mu;\ \sigma/\sqrt n)`$).
2. En una normal, el 98 % de los valores está a menos de z desvíos del centro, con z el que deja 1 % en cada cola (0,99 a la izquierda). Entonces el 98 % de las veces, $\bar x$ está a menos de $z\frac{\sigma}{\sqrt n}$ de μ.
3. Si $\bar x$ está cerca de μ, μ está igual de cerca de $\bar x$. Por eso el IC es "promedio ± margen".

💡 **¿Qué pasa si no se conoce σ?** La "dispersión de 3 minutos" es de **la muestra** (S). La fórmula exacta usa S y la **t de Student** con n − 1 grados de libertad, que es un poco más grande para compensar no conocer σ (📄 H2):

```math
I.C._\mu = \left(\bar X \mp t_{n-1;1-\frac\alpha2}\cdot\frac{S}{\sqrt n}\right)
```

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

### Ejercicio 4) Peso de recién nacidos

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

```math
\bar X \sim N\left(\mu;\ \frac{\sigma}{\sqrt n}\right)
```

Misma media, desvío dividido por $\sqrt n$. Es Normal porque la población es Normal; si no lo fuera, con n ≥ 30 lo sería aproximadamente (TCL).

```math
\bar X \sim N\left(3;\ \frac{0{,}4}{\sqrt{16}}\right) = N(3;\ 0{,}1)
```

```
X~N(μ;σ)   μ=3   σ=0.1   P(X>x)   x=3.2   → 0.02275
```
(Con tabla: estandarizando, 📄 H1, $P(Z > 2) = 0{,}02275$.)

Para comparar: que **un** bebé pese más de 3,2 tiene probabilidad 0,31. Que el promedio de 16 lo haga es mucho más raro.

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

### Teórico 2) Métodos de estimación

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

[← Volver al menú principal](../../README.md)
