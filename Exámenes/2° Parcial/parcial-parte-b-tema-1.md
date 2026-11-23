# Parcial Parte B — Tema 1

Probabilidad y Estadística — UTN FRBA. Enunciado original: [foto del examen](Fotos/WhatsApp%20Image%202026-11-18%20at%2010.39.53.jpeg).

> Examen con 4 ejercicios prácticos y 2 teóricos (casillas de Promoción y Final).

Cada ejercicio tiene un botón **Solución**. Al abrirlo aparece la respuesta y, arriba de ella, el botón **Solución paso a paso**.

---

### Ejercicio 1) Piezas defectuosas

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

### Ejercicio 2) Demanda pico de energía

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

### Ejercicio 3) Alanina en adultos mayores de 40

Sea X una muestra aleatoria de tamaño 12 de una distribución normal. Se determinó a partir de la misma la cantidad del aminoácido alanina (mg/100 ml) para 12 adultos mayores de 40 años normales, sometidos a una dieta libre de isoleucina, resultando la siguiente información:

2,84 3,54 2,8 2,44 2,94 2,7 2,93 2,54 2,79 2,14 2,74 2,67

- a) Encuentre un intervalo de confianza del 98 % para el verdadero valor de la varianza de la cantidad de alanina para adultos mayores de 40 años con esa dieta. Interprete el intervalo hallado.
- b) ¿Cuál es la probabilidad de que la varianza muestral supere el valor hallado en a) en una muestra de tamaño 12 si σ = 0,89?

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

**a)** 💡 **Intervalo de confianza:** un rango que contiene al valor verdadero (acá, la varianza σ² de **toda** la población) con una confianza dada. La varianza muestral S² **no** es Normal (nunca es negativa y es asimétrica). Lo que se sabe es que, si la población es Normal, $\frac{(n-1)S^2}{\sigma^2}$ sigue una **χ² (chi cuadrado)** con n − 1 grados de libertad (📄 H2).

De ahí sale el intervalo (📄 H2):

$`\displaystyle I.C._{\sigma^2} = \left(\frac{(n-1)S^2}{\chi^2_{n-1;1-\frac\alpha2}};\ \frac{(n-1)S^2}{\chi^2_{n-1;\frac\alpha2}}\right)`$

En la punta izquierda va el χ² **grande**. Dividir por un número grande da un resultado chico.

**Datos.** Calculadora de estadística → Estadística descriptiva con los 12 valores: n = 12, $\bar x = 2{,}756$, $s^2 = 0{,}11143$ (s = 0,334).

Con 98 %, α/2 = 0,01:
```
X~χ²(ν)   ν=11   P(X<x)=0.99   → x=24.725
X~χ²(ν)   ν=11   P(X<x)=0.01   → x=3.0535
```

$$I.C._{\sigma^2} = \left(\frac{11\cdot0{,}11143}{24{,}725};\ \frac{11\cdot0{,}11143}{3{,}053}\right) = (0{,}0496;\ 0{,}4014) \text{ (mg/100 ml)}^2$$

**Interpretación:** si se repitiera el muestreo muchas veces, el 98 % de los intervalos construidos así contendría a la verdadera varianza σ². σ² es fijo; lo que varía es el intervalo. Con esta muestra, se confía al 98 % en que σ² está entre 0,0496 y 0,4014.

**b)** **Cambia la pregunta.** Ya no se estima nada: se **conoce** σ = 0,89 y se pregunta por algo que hace la **muestra** (su S²). La herramienta es la misma frase de la hoja, $\frac{(n-1)S^2}{\sigma^2} \sim \chi^2_{n-1}$: se pasa la pregunta a la escala χ², como cuando se estandariza a Z.

Se toma como "valor hallado" el extremo superior, 0,4014. Con σ² = 0,89² = 0,7921:

$$P(S^2 > 0{,}4014) = P\left(\frac{11S^2}{0{,}7921} > \frac{11\cdot0{,}4014}{0{,}7921}\right) = P(\chi^2_{11} > 5{,}574)$$

```
X~χ²(ν)   ν=11   P(X>x)   x=5.574   → 0.9002
```
⚠️ En la app, el x de la χ² no es la varianza: es $(n-1)S^2/\sigma^2$.

Si se tomara $s^2 = 0{,}1114$: $P(\chi^2_{11} > 1{,}547) = 0{,}9996$.

Que la probabilidad sea tan alta indica que σ = 0,89 es poco compatible con la muestra (σ² = 0,79 queda fuera del IC).

</details>

**Respuesta:**

- a) $IC_{98}(\sigma^2) = [0{,}0496;\ 0{,}4014]$ (mg/100 ml)²
- b) $P(S^2 > 0{,}4014) = P(\chi^2_{11} > 5{,}574) \approx 0{,}90$

</details>

---

### Teórico 1) Sesgo de un estimador de la varianza

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

### Teórico 2) Región crítica y tamaño de muestra

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

[← Volver al menú principal](../../README.md)
