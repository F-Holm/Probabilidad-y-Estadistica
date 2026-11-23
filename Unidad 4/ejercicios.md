# Unidad 4 — Ejercicios resueltos

Ejercicios de la **Práctica 4 de la Guía de TP** (Estimación).

Cada ejercicio tiene un botón **Solución**. Al abrirlo aparece la respuesta y, arriba de ella, un segundo botón **Solución paso a paso** con el desarrollo completo.

Notación: Φ(z) = P(Z < z) para Z ~ N(0; 1). $z_{q}$, $t_{n-1;\,q}$ y $\chi^2_{n-1;\,q}$ son los valores que dejan una probabilidad **acumulada q a la izquierda** (como en la app *Probability Distributions*).

> **Referencias:** ⭐ = ejercicio sugerido como prioritario por la cátedra · *(opcional)* = la cátedra indica que no es necesario resolverlo · (T) = ejercicio teórico · (\*) = requiere aplicación informática o de celular.

---

### 1) Temperaturas de los O-rings *(opcional)*

Los siguientes datos corresponden a las temperaturas de unión de los O-rings (°F), en una muestra de prueba de lanzamientos reales del motor de un cohete de un transbordador espacial:

84 49 60 83 66 47 45 70 68 91 65 58 33 53 78 82 55 61 49 70

- a) Hallar la media aritmética y la mediana de la muestra.
- b) ¿Qué indicaría un valor de la media muy superior al de la mediana?
- c) Calcular la varianza y el desvío estándar muestrales.
- d) Eliminar la observación mayor, repetir los cálculos y comparar los resultados.

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

💡 **Muestra.** Estos 20 números son una **muestra**: unos pocos datos observados de algo más grande (todas las temperaturas posibles, la **población**). Con ellos se calculan resúmenes, llamados **estadísticos muestrales**.

**Con la app.** Calculadora de estadística → **Estadística descriptiva**, cargando los 20 datos. Da media, mediana, varianza y desvío de una vez:
```
→ n = 20   media = 63.35   mediana = 63   varianza = 232.55   desvío = 15.25
```

**a)** 💡 **Media muestral** $\bar x$: la suma de los datos dividida por cuántos son (📄 H2, $`\bar X = \frac{\sum X_i}{n}`$):

```math
\bar x = \frac{1267}{20} = 63{,}35
```

💡 **Mediana** $\tilde x$ (❌): el valor del medio cuando los datos se ordenan de menor a mayor. Con n = 20 (par) hay dos valores del medio, los lugares 10.º y 11.º, que son 61 y 65. Se promedian:

```math
\tilde x = \frac{61 + 65}{2} = 63
```

**b)** La media usa **el valor** de todos los datos: un dato enorme la "arrastra" hacia arriba. La mediana solo mira **el orden**, y un dato enorme no la mueve. Si la media es mucho mayor que la mediana, hay valores muy grandes (outliers) o la distribución es **asimétrica a derecha** (cola larga hacia los valores altos).

**c)** 💡 **Varianza muestral** $s^2$ (❌, la fórmula no está en la hoja): el promedio de los cuadrados de las distancias a la media, pero dividiendo por **n − 1** en lugar de n. Con n − 1, el estimador da en promedio el valor justo (es insesgado).

```math
s^2 = \frac{\sum (x_i - \bar x)^2}{n-1} = 232{,}55 \qquad s = \sqrt{232{,}55} = 15{,}25
```

El **desvío** s vuelve a las unidades originales (°F).

⚠️ Si la app da 226,6 como varianza, está dividiendo por n. Mantené apretado el botón para ver qué fórmula usa.

**d)** Sin el 91 quedan n = 19 datos:
- $\bar x = \frac{1267 - 91}{19} = 61{,}89$;
- la mediana es el valor del medio, el 10.º ordenado: $\tilde x = 61$;
- $s^2 = 200{,}77$ y $s = 14{,}17$.

Al sacar el valor más alto bajan la media (bastante), la mediana (un poco) y la dispersión, porque se fue un dato que estaba lejos del centro.

</details>

**Respuesta:**

- a) $\bar x = 63{,}35$; $\tilde x = 63$
- b) Presencia de outliers (asimetría a derecha)
- c) $s^2 = 232{,}55$; $s = 15{,}25$
- d) $\bar x = 61{,}89$; $\tilde x = 61$; $s^2 = 200{,}77$; $s = 14{,}17$

</details>

---

### 2) Laboratorios de análisis de agua *(opcional)*

Se desea elegir un laboratorio para enviar a procesar muestras de agua. Se postulan para esto cinco candidatos. Los boxplots correspondientes a 10 mediciones de cada laboratorio de una muestra de agua que contiene un 4 % de impurezas se exhiben en la guía.

- a) ¿Cuál/es de los laboratorios tienen sesgo en sus mediciones?
- b) Entre los menos sesgados: ¿cuál es el más preciso? Justificar.

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

💡 **Boxplot** (diagrama de caja). Resume una muestra:
- la **línea del medio** es la mediana;
- la **caja** contiene el 50 % central de los datos;
- los **bigotes** llegan a los valores extremos (sin contar outliers).

💡 **Sesgo y precisión**, con la analogía del tiro al blanco. El valor real (4 %) es el centro del blanco.
- **Sesgo:** apuntar corrido. Un instrumento es **insesgado** si sus mediciones, en promedio, dan el valor real.
- **Precisión:** qué tan juntos caen los tiros. Es **preciso** si las mediciones varían poco entre sí.

Las dos cosas son independientes: se puede ser muy preciso y estar corrido (todos los tiros juntos, pero lejos del centro).

**a)** Se mira dónde está centrada cada caja respecto del 4 %. Solo L3 y L5 tienen la mediana alrededor de 4 %. Los demás están corridos para arriba o para abajo: **tienen sesgo**.

**b)** Entre los insesgados (L3 y L5), el más **preciso** es el de menor dispersión, con caja y bigotes más cortos: **L5**.

</details>

**Respuesta:**

- a) Todos menos L3 y L5
- b) L5, por tener menor dispersión

</details>

---

### 3) Resistencias en serie ⭐

Un circuito funciona con varias resistencias independientes en serie, cada una de las cuales tiene distribución Normal con media 20 ohms y varianza 0,36 ohm².

- a) Si se instalan 6 de estas resistencias, ¿cuál es la probabilidad de que la resistencia del circuito sobrepase los 118 ohm?
- b) ¿Cuántas resistencias deberán instalarse de manera que la probabilidad de que la resistencia total exceda los 200 ohm sea aproximadamente 0,05?

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

**Traducción.** En serie, las resistencias se **suman**: R = R₁ + R₂ + … Cada una es N(20; σ), con σ = √0,36 = 0,6. ⚠️ El dato es la **varianza**: el desvío es su raíz.

💡 **Suma de normales independientes** (📄 H2, $`W = \sum X_i \sim N\left(\sum\mu_i;\ \sqrt{\sum\sigma_i^2}\right)`$). La suma de normales independientes **sigue siendo normal**:
- las **medias se suman**;
- las **varianzas se suman** (no los desvíos). El desvío de la suma es la raíz de la suma de varianzas.

**a)** Con 6 resistencias:

```math
R \sim N\left(6\cdot20;\ \sqrt{6\cdot0{,}36}\right) = N(120;\ 1{,}4697)
```

```
X~N(μ;σ)   μ=120   σ=1.4697   P(X>x)   x=118   → 0.91322
```
(Con tabla, estandarizando con 📄 H1: $1 - \Phi\left(\frac{118 - 120}{1{,}47}\right) = 1 - \Phi(-1{,}36) \approx 0{,}913$.)

**b)** Con n resistencias, $R \sim N(20n;\ 0{,}6\sqrt n)$. La incógnita es n.

**Paso 1, el z que deja 5 % a la derecha:**
```
X~N(μ;σ)   μ=0   σ=1   P(X>x)=0.05   → x=1.64485
```

**Paso 2, plantear la ecuación.** Estandarizando 200 (📄 H1), tiene que dar ese z:

```math
\frac{200 - 20n}{0{,}6\sqrt n} = 1{,}645 \;\Rightarrow\; 20n + 0{,}987\sqrt n - 200 = 0
```

**Paso 3, resolver.** Con $u = \sqrt n$ queda una cuadrática: $20u^2 + 0{,}987u - 200 = 0$. Con la resolvente, $u = 3{,}138$, así que $n = u^2 \approx 9{,}85$.

**Paso 4, interpretar** (la parte delicada). n tiene que ser entero, y **ningún** entero da 0,05 exacto:
- con 9 resistencias, la media es 180 y P(R > 200) ≈ 0;
- con 10, la media es exactamente 200 y P(R > 200) = 0,5.

Más resistencias suman **más** ohms, así que P(R > 200) **crece** con n. Si se quiere que esa probabilidad no pase de 0,05, se pueden instalar **a lo sumo 9**.

⚠️ La guía da "n ≥ 10": redondea 9,85 hacia arriba como si fuera un tamaño de muestra. Pero con 10 la probabilidad es 0,5, no 0,05. El valor que resuelve la ecuación es n ≈ 9,85, igual que en la resolución del aula virtual (Prof. Calvo: "9 resistencias y el 84,5 % de otra"); en enteros, n = 9.

</details>

**Respuesta:**

- a) 0,91317
- b) n ≈ 9,85 (con 9 resistencias P ≈ 0; con 10, P = 0,5). La guía da n ≥ 10.

</details>

---

### 4) Sueldos de las sucursales *(opcional)*

Una empresa agroalimentaria tiene tres sucursales en cierta región, cada una de ellas manejada por dos empleados. Los sueldos mensuales de estos empleados en miles de unidades monetarias se exhiben en la siguiente tabla:

| Sucursal | 1 | 1 | 2 | 2 | 3 | 3 |
|---|---|---|---|---|---|---|
| Empleado | 1 | 2 | 3 | 4 | 5 | 6 |
| Sueldo | 19,5 | 23,8 | 20,1 | 23,8 | 15,6 | 19,5 |

- a) Se seleccionan al azar dos empleados entre estos seis con reemplazo y se calcula el promedio de sus sueldos. Hallar la distribución muestral del sueldo medio.
- b) Se selecciona una de las tres sucursales al azar y se considera la variable aleatoria Z: "promedio de los sueldos de los dos empleados de la misma". Hallar la distribución de Z.
- c) Compare los resultados de (a) y (b) con la media y la varianza del sueldo de un empleado elegido al azar de la empresa.

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

💡 **Población y distribución muestral.** Acá la **población** son los 6 empleados y se conoce entera. X = sueldo de un empleado elegido al azar, con cada uno de los 6 sueldos con probabilidad 1/6 (📄 H1, $`E = \sum x\,p`$):

```math
E(X) = \frac{122{,}3}{6} = 20{,}38 \qquad V(X) = \frac16\sum(x_i - 20{,}38)^2 = 7{,}978
```

(Esta varianza divide por 6 porque es la **verdadera** varianza de la población, no una estimación.)

La **distribución muestral** de $\bar X$ responde: si se toman muestras al azar y se calcula su promedio, ¿qué valores puede dar ese promedio y con qué probabilidad?

**a)** Con reemplazo, el 1.º y el 2.º se eligen independientes: 6·6 = 36 pares, todos igual de probables. Se calcula el promedio de cada par, y los pares que dan el mismo promedio se agrupan sumando probabilidades. Esa es la distribución de $\bar X$.

No hace falta la tabla completa para sus momentos. 💡 Para una **muestra aleatoria** (observaciones independientes de la misma población):
- $E(\bar X) = E(X) = 20{,}38$: el promedio de muestras está centrado en la media verdadera;
- $V(\bar X) = \frac{V(X)}{n} = \frac{7{,}978}{2} = 3{,}989$: promediar reduce la dispersión.

(Es lo que dice 📄 H2, $\bar X \sim N(\mu;\ \sigma/\sqrt n)$, en cuanto a media y desvío.)

**b)** Ahora se elige una **sucursal** y se promedian sus dos empleados. Hay solo 3 resultados posibles, cada uno con probabilidad 1/3:
- (19,5 + 23,8)/2 = 21,65;
- (20,1 + 23,8)/2 = 21,95;
- (15,6 + 19,5)/2 = 17,55.

**c)**

```math
E(Z) = \frac{21{,}65 + 21{,}95 + 17{,}55}{3} = 20{,}38 = E(X) \qquad V(Z) = \frac13\sum(z_i - 20{,}38)^2 = 4{,}028
```

La esperanza coincide, pero la varianza **no** es V(X)/2. ¿Por qué? Los dos empleados de una sucursal **no** son una muestra aleatoria independiente: siempre salen juntos. La regla V/n solo vale con observaciones independientes.

</details>

**Respuesta:**

- a) $E(\bar X) = 20{,}38 = E(X)$; $V(\bar X) = 3{,}989 = \frac12V(X)$
- b) P(Z = 17,55) = P(Z = 21,65) = P(Z = 21,95) = 1/3
- c) $E(Z) = 20{,}38 = E(X)$; $V(Z) = 4{,}028 \ne \frac12V(X)$

</details>

---

### 5) Espesor de la pintura ⭐

Se supone que el espesor de cierta pintura al aceite (X) en mm tiene distribución Normal. Se realizaron las siguientes observaciones de espesores de esta pintura:

0,89 0,88 0,88 1,03 1,09 1,12 1,29 1,31 1,48 1,49 1,59 1,62 1,64 1,71 1,76 1,83

- a) Calcular a partir de la muestra la media, la varianza, el desvío estándar y la mediana.
- b) ¿Cuál/es de estos valores utilizaría para estimar el valor central de los espesores de esta pintura?
- c) Si la muestra tuviera tamaño 1000, ¿qué estimador puntual elegiría para la media? ¿En qué basa su elección?

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

**a)** Calculadora de estadística → **Estadística descriptiva**, cargando los 16 espesores:
```
→ n = 16   media = 1.3506   varianza = 0.1107   desvío = 0.3327   mediana = 1.395
```
- 💡 **Media** (📄 H2, $`\bar X = \frac{\sum X_i}{n}`$): $\bar x = \frac{21{,}61}{16} = 1{,}35$.
- 💡 **Varianza muestral** (❌): $s^2 = \frac{\sum(x_i - \bar x)^2}{n-1} = 0{,}1107$. Divide por n − 1. El desvío es $s = \sqrt{s^2} = 0{,}3327$.
- 💡 **Mediana** (❌): el valor del medio de los datos ordenados. Con 16 datos se promedian el 8.º y el 9.º: $\frac{1{,}31 + 1{,}48}{2} = 1{,}395$.

**b)** 💡 **Estimador:** una fórmula con los datos para "adivinar" un valor desconocido de la población, en este caso la media μ. Entre los candidatos (media, mediana) se elige el que tenga mejores propiedades:
- **insesgado:** en promedio da justo μ;
- **eficiente:** de los insesgados, el que menos varía;
- **consistente:** con más datos, se acerca cada vez más a μ.

Si la población es Normal, la media y la mediana son las dos insesgadas, pero $\bar X$ varía menos. El mejor estimador es $\hat\mu = \bar x = 1{,}35$. La varianza y el desvío no estiman el centro, sino la dispersión.

**c)** Se elige $\bar X$ por **consistencia**. Su varianza es $V(\bar X) = \frac{\sigma^2}{n}$ (📄 H2, el desvío de $\bar X$ es $`\frac{\sigma}{\sqrt n}`$), y con n = 1000 es muy chica. Entonces $\bar x$ queda casi seguro muy cerca de μ: es la **Ley de los Grandes Números** (❌).

</details>

**Respuesta:**

- a) $\bar x = 1{,}35$; $s^2 = 0{,}1107$; $s = 0{,}3327$; $\tilde x = 1{,}395$
- b) $\hat\mu = \bar x = 1{,}35$
- c) $\bar x$, por la Ley de los Grandes Números (consistencia)

</details>

---

### 6) Esperanza y varianza de una suma (T) ⭐

(T) Probar que si $X_1, X_2, \dots, X_n$ son variables aleatorias independientes idénticamente distribuidas con $E(X_i) = \mu$ y $V(X_i) = \sigma^2$, entonces:

- a) $E(X_1 + X_2 + \dots + X_n) = n\mu$
- b) $V(X_1 + X_2 + \dots + X_n) = n\sigma^2$

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

"Independientes idénticamente distribuidas" significa dos cosas: no se influyen entre sí, y todas tienen la misma distribución (misma μ, misma σ²). Es lo que pasa con una **muestra aleatoria**.

**a)** 💡 **Linealidad de la esperanza** (❌, no está en la hoja): la esperanza de una suma es la suma de las esperanzas, **siempre**, aunque no sean independientes.

```math
E(X_1 + \dots + X_n) = E(X_1) + \dots + E(X_n) = \underbrace{\mu + \dots + \mu}_{n} = n\mu
```

**b)** Para dos variables, 📄 H1 dice $V(X + Y) = V(X) + V(Y) + 2\,Cov(X;Y)$.

Si son **independientes**, la covarianza es 0 (no hay relación), así que $V(X + Y) = V(X) + V(Y)$. Se aplica de a una: primero $X_1 + X_2$, después se le suma $X_3$, y así. Cada vez se agrega una varianza:

```math
V(X_1 + \dots + X_n) = V(X_1) + \dots + V(X_n) = n\sigma^2
```

Aquí la independencia **sí** hace falta. Sin ella aparecerían todas las covarianzas.

**Consecuencia importante.** Para el promedio $\bar X = \frac{1}{n}\sum X_i$, las constantes salen de la esperanza tal cual y de la varianza al cuadrado:

```math
E(\bar X) = \mu \qquad V(\bar X) = \frac{n\sigma^2}{n^2} = \frac{\sigma^2}{n}
```

Es el $\frac{\sigma}{\sqrt n}$ de 📄 H2, $\bar X \sim N(\mu;\ \sigma/\sqrt n)$.

</details>

**Respuesta:**

- a) $E(\sum X_i) = \sum E(X_i) = n\mu$
- b) $V(\sum X_i) = \sum V(X_i) = n\sigma^2$, usando la independencia (covarianzas nulas)

</details>

---

### 7) Cajas de café ⭐

Una fábrica envasa paquetes de café cuyo peso es una variable aleatoria Normal de media 495 g y desvío estándar 18 g. Los paquetes se venden en cajas de 9 unidades. El peso de la caja de cartón es una variable aleatoria Normal de media 50 g y desvío estándar 4 g. Si se selecciona una caja al azar, ¿cuál es la probabilidad de que el peso no supere los 4.500 g? (Considerar los pesos de los paquetes como variables aleatorias independientes).

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

**Planteo.** El peso de una caja llena es W = (peso de los 9 paquetes) + (peso del cartón):

```math
W = X_1 + X_2 + \dots + X_9 + C
```

Cada $X_i \sim N(495; 18)$ y $C \sim N(50; 4)$, todos independientes.

💡 **Suma de normales independientes** (📄 H2, $`W = \sum X_i \sim N\left(\sum\mu_i;\ \sqrt{\sum\sigma_i^2}\right)`$). La suma es normal, con:
- media = suma de medias: $E(W) = 9\cdot495 + 50 = 4505$ g;
- varianza = suma de **varianzas** (los desvíos al cuadrado): $V(W) = 9\cdot18^2 + 4^2 = 2916 + 16 = 2932$.

Entonces $\sigma_W = \sqrt{2932} = 54{,}148$ g.

```math
W \sim N(4505;\ 54{,}148)
```

```
X~N(μ;σ)   μ=4505   σ=54.148   P(X<x)   x=4500   → 0.46321
```
(Con tabla, estandarizando con 📄 H1: $\Phi\left(\frac{4500 - 4505}{54{,}15}\right) = \Phi(-0{,}092) \approx 0{,}463$.)

⚠️ **Error típico:** escribir el peso de los 9 paquetes como 9X. Eso sería **un** paquete multiplicado por 9 (9 paquetes idénticos), con varianza $9^2\sigma^2 = 81\sigma^2$. Nueve paquetes **distintos** e independientes se compensan entre sí, y la varianza es solo $9\sigma^2$.

</details>

**Respuesta:** 0,46322

</details>

---

### 8) Estatura de la población ⭐

En una población determinada, la estatura de una persona adulta tiene un promedio de 165 cm con una desviación estándar de 7 cm.

- a) Si se toma una muestra aleatoria de 100 personas en esta población, calcular la probabilidad de que la estatura media de la muestra exceda 168 cm.
- b) Si se supone distribución normal de las estaturas, hallar la probabilidad de que en una muestra de 36 personas el desvío de la estatura resulte superior a 6 cm.
- c) Si llamamos p a la proporción de personas de la población que superan el 1,70 m, hallar la probabilidad de que dicha proporción en una muestra de tamaño 36 supere el 20 %.

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

Las tres preguntas son sobre algo que se calcula **con la muestra**: el promedio, el desvío y la proporción. Cada uno tiene su propia distribución, distinta de la de una persona.

**a)** 💡 **Distribución del promedio** (📄 H2, $`\bar X \sim N\left(\mu;\ \frac{\sigma}{\sqrt n}\right)`$). Al promediar muchas personas, las altas y las bajas se compensan. El promedio:
- está centrado en la misma μ;
- varía **mucho menos**: su desvío es $\sigma/\sqrt n$ (se llama **error estándar**).

💡 **Teorema Central del Límite (TCL)** (❌). Acá **no** se dice que la estatura sea normal. Pero con n ≥ 30, el promedio es aproximadamente normal **igual**, sea cual sea la distribución de la población.

```math
\bar h \sim N\left(165;\ \frac{7}{\sqrt{100}}\right) = N(165;\ 0{,}7)
```

```
X~N(μ;σ)   μ=165   σ=0.7   P(X>x)   x=168   → 0.0000091
```
$z = \frac{168 - 165}{0{,}7} = 4{,}29$: es casi imposible. Para **una** persona, P(h > 168) = 0,33. Para el promedio de 100, casi 0.

**b)** Ahora se pregunta por el **desvío** de la muestra, S. 💡 Si la población es **normal** (por eso el enunciado lo supone), la cantidad $\frac{(n-1)S^2}{\sigma^2}$ tiene una distribución conocida, la **χ² (chi cuadrado)** con n − 1 grados de libertad (📄 H2, si $X \sim N$, $`\frac{(n-1)S^2}{\sigma^2} \sim \chi^2_{n-1}`$).

**Receta:** se pasa la pregunta sobre S a una pregunta sobre esa cantidad. Con n = 36 y σ² = 49:

```math
P(S > 6) = P(S^2 > 36) = P\left(\frac{35\,S^2}{49} > \frac{35\cdot36}{49}\right) = P(\chi^2_{35} > 25{,}714)
```

```
X~χ²(ν)   ν=35   P(X>x)   x=25.714   → 0.87390
```
⚠️ En la app de la χ² el x **no** es el desvío ni la varianza: es $(n-1)s^2/\sigma^2$.

**c)** Dos pasos.

**Paso 1, la proporción en la población.** Suponiendo h ~ N(165; 7):
```
X~N(μ;σ)   μ=165   σ=7   P(X>x)   x=170   → 0.23753
```
p ≈ 0,2375. La guía redondea a 0,24.

**Paso 2, la proporción en la muestra** ($`\hat p`$). 💡 Cada persona supera o no 1,70 m. $\hat p$ es el promedio de esos unos y ceros, así que por TCL (n ≥ 30) es aproximadamente normal (📄 H2, si n ≥ 30, $`\hat p \sim N\left(p;\ \sqrt{\frac{p(1-p)}{n}}\right)`$). Con p = 0,24:

```math
\hat p \sim N\left(0{,}24;\ \sqrt{\frac{0{,}24\cdot0{,}76}{36}}\right) = N(0{,}24;\ 0{,}0712)
```

```
X~N(μ;σ)   μ=0.24   σ=0.0712   P(X>x)   x=0.20   → 0.71293
```
Con p = 0,2375 sin redondear da 0,7016. La guía da 0,71341 y el apunte 0,71615; las diferencias son por redondeo.

</details>

**Respuesta:**

- a) 0,00001
- b) 0,87403
- c) 0,71341

</details>

---

### 9) Tiempo de secado de la pintura (\*) ⭐

(\*) La pintura para autopista de color amarillo tiene una especificación que recomienda que la varianza del tiempo de secado no supere los 20 min². Sabiendo que la distribución del tiempo de secado es aproximadamente Normal con varianza 16 min²:

- a) hallar la probabilidad de que la varianza del tiempo de secado en una muestra de tamaño 10 exceda los 42,77 min².
- b) hallar la variabilidad superada por el 20 % de las muestras de tamaño 10 de tiempos de secado.

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

**¿Qué se pregunta?** Por la **varianza de una muestra** de 10 tiempos, $S^2$. Varía de muestra en muestra, así que es una variable aleatoria.

💡 **La herramienta** (📄 H2): si la población es normal (el enunciado lo dice), $\frac{(n-1)S^2}{\sigma^2} \sim \chi^2_{n-1}$. La **χ²** es una distribución que solo toma valores positivos y es asimétrica. Su parámetro son los grados de libertad, n − 1 = 9. Acá σ² = 16, así que:

```math
\frac{9\,S^2}{16} \sim \chi^2_9
```

**Receta:** toda pregunta sobre $S^2$ se traduce a una pregunta sobre $\chi^2_9$ multiplicando por 9/16.

**a)**

```math
P(S^2 > 42{,}77) = P\left(\chi^2_9 > \frac{9\cdot42{,}77}{16}\right) = P(\chi^2_9 > 24{,}058)
```

```
X~χ²(ν)   ν=9   P(X>x)   x=24.058   → 0.00421
```
Muy improbable: una muestra con varianza 42,77 sería rarísima si la verdadera es 16.

**b)** "La variabilidad superada por el 20 % de las muestras" es el valor c con $P(S^2 > c) = 0{,}20$. Primero se busca el χ² que deja 20 % a la derecha:
```
X~χ²(ν)   ν=9   P(X>x)=0.20   → x=12.242
```
Después se vuelve a la escala de $S^2$, despejando:

```math
\frac{9c}{16} = 12{,}242 \;\Rightarrow\; c = \frac{16\cdot12{,}242}{9} = 21{,}76 \text{ min}^2
```

</details>

**Respuesta:**

- a) 0,00421
- b) $s^2 = 21{,}76$ min²

</details>

---

### 10) Redondeo en el supermercado ⭐

En un supermercado se decide redondear el cobro de las ventas al entero más cercano. Si en un día se realizan 800 ventas y se supone que el redondeo tiene distribución Uniforme, hallar la probabilidad de que en ese día el supermercado pierda en el redondeo más de $9.

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

**Una venta.** Al redondear al entero más cercano, el supermercado gana o pierde entre −0,50 y +0,50 pesos, y cualquier valor es igual de probable. Es una **uniforme** $X_i \sim U(-0{,}5;\ 0{,}5)$:
- $E(X_i) = \frac{-0{,}5 + 0{,}5}{2} = 0$ (❌, punto medio);
- $V(X_i) = \frac{(b-a)^2}{12} = \frac{1}{12}$ (📄 H1).

**800 ventas.** El redondeo total del día es la suma W = X₁ + … + X₈₀₀. Las ventas son independientes, así que:
- las medias se suman: E(W) = 0;
- las varianzas se suman: V(W) = 800/12 = 66,67, y $\sigma_W = 8{,}165$.

💡 **Teorema Central del Límite (TCL)** (❌). Cada $X_i$ es uniforme, no normal. Pero la **suma de muchas** variables independientes (n ≥ 30) es aproximadamente **normal**, sea cual sea la distribución de cada una. Por eso se puede usar la forma de 📄 H2 para sumas:

```math
W \approx N(0;\ 8{,}165)
```

**"Perder más de 9 pesos"** es W < −9, si W mide ganancia. La campana es simétrica alrededor de 0, así que da lo mismo que W > 9:
```
X~N(μ;σ)   μ=0   σ=8.165   P(X<x)   x=−9   → 0.13517
```
(Con tabla: $1 - \Phi(9/8{,}165) = 1 - \Phi(1{,}10) \approx 0{,}135$.)

</details>

**Respuesta:** 0,1351

</details>

---

### 11) Errores tipográficos ⭐

La primera tarea en un curso introductorio de programación por computadora implica correr un breve programa. Si la experiencia indica que el 40 % de todos los estudiantes principiantes no cometerán errores tipográficos, calcular la probabilidad aproximada de que en un grupo de 80 estudiantes:

- a) por lo menos 35 % no cometan errores.
- b) entre el 45 % y el 55 % cometan errores.

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

💡 **Proporción muestral** $\hat p$: la fracción de la muestra que cumple algo (acá, no cometer errores). Varía de grupo en grupo. Cada estudiante es un 1 (cumple) o un 0 (no cumple), y $\hat p$ es el **promedio** de esos unos y ceros. Por el TCL, con n ≥ 30 es aproximadamente normal (📄 H2):

```math
\hat p \sim N\left(p;\ \sqrt{\frac{p(1-p)}{n}}\right)
```

Con p = 0,4 y n = 80, el desvío es $\sqrt{\frac{0{,}4\cdot0{,}6}{80}} = 0{,}0548$.

**a)** $\hat p$ = proporción **sin** errores, aproximadamente N(0,40; 0,0548). "Por lo menos 35 %" es $\hat p \ge 0{,}35$:
```
X~N(μ;σ)   μ=0.40   σ=0.0548   P(X>x)   x=0.35   → 0.8193
```

**b)** ⚠️ Ojo con de qué grupo habla: ahora pregunta por los que **cometen** errores. Su proporción en la población es 1 − 0,4 = 0,6. El desvío es el mismo, porque $0{,}6\cdot0{,}4 = 0{,}4\cdot0{,}6$. Así que $\hat q \sim N(0{,}60;\ 0{,}0548)$.

"Entre 45 % y 55 %" es la acumulada hasta 0,55 menos la acumulada hasta 0,45:
```
X~N(μ;σ)   μ=0.60   σ=0.0548   P(X<x)   x=0.55   → 0.1807
X~N(μ;σ)   μ=0.60   σ=0.0548   P(X<x)   x=0.45   → 0.0031    → resta = 0.1776
```
La guía da 0,81835 y 0,17846; las diferencias son por redondear z a dos decimales.

</details>

**Respuesta:**

- a) 0,81835
- b) 0,17846

</details>

---

### 12) Imperfecciones por pieza *(opcional)*

Se examinan 180 piezas recién fabricadas y se registra el número de imperfecciones por pieza. Sería ideal que las piezas fabricadas no tuvieran imperfecciones. Sea X: "número de imperfecciones en una pieza seleccionada al azar" y supongamos que X tiene distribución Poisson de parámetro λ. Se obtuvieron las siguientes observaciones:

| Imperfecciones por pieza | 0 | 1 | 2 | 3 | 4 | 5 | 6 | 7 |
|---|---|---|---|---|---|---|---|---|
| Frecuencia observada | 18 | 47 | 52 | 40 | 13 | 7 | 2 | 1 |

- a) Hallar las expresiones de los estimadores de momentos y de máxima verosimilitud correspondientes al valor del parámetro λ desconocido.
- b) Analizar si estos estimadores son insesgados.
- c) Con la estimación lograda, aproximar el valor de P(X < 4).

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

**El problema:** se sabe que X es Poisson, pero no se conoce λ. Hay que **estimarlo** con los datos. 💡 Hay dos recetas para fabricar un estimador (❌, ninguna está en la hoja).

**a) Método de los momentos.** "Lo teórico igual a lo observado": se iguala la esperanza teórica (que depende del parámetro) al promedio de la muestra. En una Poisson, E(X) = λ, así que:

```math
\lambda = \bar X \;\Rightarrow\; \hat\lambda_{mom} = \bar X
```

**Máxima verosimilitud.** "Elegir el λ con el cual **lo que salió** es lo más probable".
1. Se escribe la probabilidad de toda la muestra como función de λ. Las observaciones son independientes, así que es el producto (📄 H1, $`P(X = k) = \frac{\lambda^k}{k!}e^{-\lambda}`$):

   ```math
   L(\lambda) = \prod_{i=1}^n \frac{\lambda^{x_i}e^{-\lambda}}{x_i!}
   ```

2. Para maximizar es más fácil trabajar con el logaritmo, que convierte productos en sumas:

   ```math
   \ln L = \sum x_i\ln\lambda - n\lambda - \sum\ln(x_i!)
   ```

3. Se deriva respecto de λ y se iguala a 0:

   ```math
   \frac{\sum x_i}{\lambda} - n = 0 \;\Rightarrow\; \hat\lambda_{MV} = \frac{\sum x_i}{n} = \bar X
   ```

Los dos métodos dan el mismo estimador: el promedio.

**Con los datos.** Son datos agrupados: cada valor se multiplica por su frecuencia. En la Calculadora de estadística → **Descriptiva con frecuencia**, se cargan valor y frecuencia:

```math
\bar x = \frac{0\cdot18 + 1\cdot47 + 2\cdot52 + 3\cdot40 + 4\cdot13 + 5\cdot7 + 6\cdot2 + 7\cdot1}{180} = \frac{377}{180} = 2{,}09
```

**b)** 💡 **Insesgado:** que en promedio dé justo el parámetro, $E(\hat\lambda) = \lambda$ (❌). El promedio de una muestra tiene la misma esperanza que una observación (📄 H2, $\bar X$ está centrado en μ), y en la Poisson esa esperanza es λ:

```math
E(\bar X) = E(X) = \lambda
```

Es insesgado.

**c)** Se reemplaza λ por su estimación 2,09 y se calcula con la Poisson. "Menor que 4" es 0, 1, 2 o 3:
```
X~Po(λ)   λ=2.09   P(X≤x)   x=3   → 0.84053
```

</details>

**Respuesta:**

- a) $\hat\lambda_{mom} = \hat\lambda_{MV} = \bar X$; estimación 2,09
- b) Sí, son insesgados
- c) 0,84053

</details>

---

### 13) Estimadores para una exponencial ⭐

Sea $X_1, X_2, X_3, X_4$ una muestra aleatoria de tamaño 4 de una población exponencial de parámetro α desconocido. Considere $f(x) = \alpha e^{-\alpha x}$. Se proponen los siguientes estadísticos para estimar (tener en cuenta el valor esperado de esta variable):

- $T_1 = \frac16(X_1 + X_2) + \frac13(X_3 + X_4)$
- $T_2 = \frac15(X_1 + 2X_2 + 3X_3 + 4X_4)$
- $T_3 = \frac14(X_1 + X_2 + X_3 + X_4)$

Se pide:

- a) Seleccionar el o los estimadores insesgados entre los propuestos.
- b) Elegir el de menor varianza entre los seleccionados en (a).
- c) Ver si el error cuadrático medio del estimador elegido en (b) es el mínimo.

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

💡 **Estimador:** una fórmula con los datos de la muestra para "adivinar" un parámetro desconocido. Acá hay tres candidatos, y hay que elegir el mejor con criterios objetivos.

**¿Qué estiman?** Los tres son "promedios" de las X, así que estiman la **media** de la exponencial: $\mu = E(X) = \frac1\alpha$. Su varianza es $V(X) = \frac{1}{\alpha^2}$ (📄 H1, $`\sigma = 1/\lambda`$).

**Datos que se usan:** cada $X_i$ tiene E = μ y V = 1/α², y son independientes (muestra aleatoria).

**a)** 💡 **Insesgado** (❌): $E(T) = \mu$, que "en promedio acierta". Se calcula E de cada uno con linealidad (❌), reemplazando cada $E(X_i)$ por μ:
- $E(T_1) = \frac16(\mu + \mu) + \frac13(\mu + \mu) = \frac13\mu + \frac23\mu = \mu$: **insesgado**.
- $E(T_2) = \frac15(1 + 2 + 3 + 4)\mu = 2\mu$: **sesgado**, sobreestima al doble.
- $E(T_3) = \frac14\cdot4\mu = \mu$: **insesgado**.

Truco: si los coeficientes suman 1, es insesgado.

**b)** 💡 Entre insesgados se prefiere el que **menos varía**. La varianza de una combinación de independientes lleva los coeficientes **al cuadrado** (📄 H1, $V(aX + bY) = a^2V(X) + b^2V(Y)$, con Cov = 0):

```math
V(T_1) = \left(\frac1{36} + \frac1{36} + \frac19 + \frac19\right)\frac1{\alpha^2} = \frac{10}{36}\cdot\frac{1}{\alpha^2} = \frac{5}{18\alpha^2} \approx \frac{0{,}278}{\alpha^2}
```

```math
V(T_3) = 4\cdot\frac1{16}\cdot\frac1{\alpha^2} = \frac{1}{4\alpha^2} = \frac{0{,}25}{\alpha^2}
```

Como 0,25 < 0,278, se elige **T₃**, el promedio muestral.

**c)** 💡 **Error cuadrático medio** (📄 H2, $`ECM = V(\hat\theta) + (\text{sesgo})^2`$): mide el error total, juntando cuánto varía y cuán corrido está. Para un insesgado, el sesgo es 0 y ECM = V:

```math
ECM(T_3) = \frac{1}{4\alpha^2} < ECM(T_1)
```

Además se sabe (❌) que $\bar X$ es el insesgado de menor varianza posible para la media, así que entre los insesgados su ECM es el mínimo.

(Para comparar, el sesgado: $V(T_2) = \frac{30}{25\alpha^2}$ y sesgo = 2μ − μ = 1/α, así que $ECM(T_2) = \frac{1{,}2}{\alpha^2} + \frac{1}{\alpha^2} = \frac{2{,}2}{\alpha^2}$, muchísimo peor.)

</details>

**Respuesta:**

- a) $T_1$ y $T_3$ son insesgados ($`E = \mu`$); $T_2$ es sesgado ($`E(T_2) = 2\mu`$)
- b) $V(T_1) = \frac5{18\alpha^2}$, $V(T_3) = \frac1{4\alpha^2}$ ⇒ $T_3$
- c) $ECM(T_3) = V(T_3)$: sí, es el mínimo

</details>

---

### 14) Error cuadrático medio (T) *(opcional)*

(T) Verificar que el error cuadrático medio de un estimador es la suma de la varianza del mismo y el cuadrado de su sesgo.

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

💡 **Qué es el ECM.** Un estimador $\hat\theta$ intenta adivinar un parámetro θ. El **error cuadrático medio** es el promedio (esperanza) del error al cuadrado:

```math
ECM(\hat\theta) = E[(\hat\theta - \theta)^2]
```

Mide qué tan lejos cae, en promedio, el estimador del valor verdadero.

💡 **Sesgo** (❌): $B(\hat\theta) = E(\hat\theta) - \theta$, cuánto se corre el centro del estimador respecto del valor real.

**Demostración.** θ es un número fijo y $\hat\theta$ es la variable aleatoria.

1. Se desarrolla el cuadrado y se usa la linealidad de la esperanza (las constantes salen):

   ```math
   E[(\hat\theta - \theta)^2] = E(\hat\theta^2) - 2\theta E(\hat\theta) + \theta^2
   ```

2. El truco: se **suma y resta** $[E(\hat\theta)]^2$, que no cambia nada, y se agrupa:

   ```math
   = \underbrace{E(\hat\theta^2) - [E(\hat\theta)]^2}_{V(\hat\theta)} + \underbrace{[E(\hat\theta)]^2 - 2\theta E(\hat\theta) + \theta^2}_{(E(\hat\theta) - \theta)^2}
   ```

   - El primer grupo es la varianza (📄 H1, $`V(X) = E(X^2) - (E(X))^2`$).
   - El segundo es un cuadrado de un binomio, $(a - b)^2$ con $a = E(\hat\theta)$ y $b = \theta$: es el **sesgo al cuadrado**.

$$ECM(\hat\theta) = V(\hat\theta) + B(\hat\theta)^2 \qquad ∎$$

Está en 📄 H2. En palabras: el error total tiene dos fuentes, cuánto varía el estimador y cuán corrido está.

</details>

**Respuesta:** $ECM(\hat\theta) = V(\hat\theta) + B(\hat\theta)^2$, con $B(\hat\theta) = E(\hat\theta) - \theta$ (sesgo).

</details>

---

### 15) $\bar X^2$ no estima bien a μ² (T) *(opcional)*

(T) Sea $X_1, \dots, X_n$ una muestra aleatoria de una población de la que se sabe que $E(X_i) = \mu$ y $V(X_i) = \sigma^2$. Demostrar que $\bar X^2$ no es un estimador insesgado de μ².

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

💡 **Insesgado** (❌): un estimador $\hat\theta$ es insesgado si $E(\hat\theta) = \theta$, es decir, si en promedio da justo lo que quiere estimar. Hay que calcular $E(\bar X^2)$ y ver si da μ².

**Herramientas:**
- 📄 H1: $V(Y) = E(Y^2) - E(Y)^2$, válida para cualquier variable, también para $Y = \bar X$. Despejando: $E(\bar X^2) = V(\bar X) + [E(\bar X)]^2$.
- El promedio de una muestra aleatoria cumple $E(\bar X) = \mu$ y $V(\bar X) = \frac{\sigma^2}{n}$ (ver el ejercicio 6, o 📄 H2, $`\bar X \sim N(\mu;\ \sigma/\sqrt n)`$).

Reemplazando:

```math
E(\bar X^2) = \frac{\sigma^2}{n} + \mu^2 \neq \mu^2
```

Es **sesgado**, con sesgo $\frac{\sigma^2}{n}$ siempre positivo: sobreestima μ². Como el sesgo tiende a 0 cuando n crece, se dice que es **asintóticamente insesgado**.

Moraleja: aunque $\bar X$ estime bien μ, **elevar al cuadrado no conserva la insesgadez**, porque $E(Y^2) \neq E(Y)^2$.

</details>

**Respuesta:** $E(\bar X^2) = \mu^2 + \frac{\sigma^2}n \ne \mu^2$ ⇒ es sesgado (sesgo σ²/n, que tiende a 0 cuando n crece).

</details>

---

### 16) Estimador de momentos de θ *(opcional)*

Se denota con X la proporción de tiempo que un estudiante, seleccionado al azar, emplea trabajando en cierta prueba de aptitud. Suponiendo que X tiene una distribución cuya función de densidad está dada por:

$$f(x) = \begin{cases}(\theta + 1)x^\theta & \text{si } 0 \le x \le 1\\ 0 & \text{en otro caso}\end{cases}$$

- a) Obtener el estimador de momentos de θ.
- b) Se toma una muestra aleatoria de 12 estudiantes, obteniendo las siguientes observaciones: 0,92 − 0,79 − 0,90 − 0,69 − 0,86 − 0,49 − 0,73 − 0,97 − 0,94 − 0,77 − 0,93 − 0,75. Calcular la estimación de θ para esta muestra.

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

💡 **Método de los momentos** (❌): para estimar un parámetro desconocido, se iguala **lo teórico a lo observado**. La esperanza teórica E(X), que depende de θ, se iguala al promedio de la muestra $\bar X$, y se despeja θ.

**a) Paso 1, la esperanza teórica** (📄 H1, $`E(X) = \int x\,f(x)\,dx`$):

```math
E(X) = \int_0^1 x\,(\theta + 1)x^\theta\,dx = (\theta + 1)\int_0^1 x^{\theta + 1}\,dx = (\theta + 1)\frac{1}{\theta + 2} = \frac{\theta + 1}{\theta + 2}
```

**Paso 2, igualar a $\bar X$ y despejar θ:**

```math
\frac{\theta + 1}{\theta + 2} = \bar X \;\Rightarrow\; \theta + 1 = \bar X\theta + 2\bar X \;\Rightarrow\; \theta(1 - \bar X) = 2\bar X - 1 \;\Rightarrow\; \hat\theta = \frac{2\bar X - 1}{1 - \bar X}
```

Es lo mismo que $\frac{1 - 2\bar X}{\bar X - 1}$ (multiplicando arriba y abajo por −1).

**b)** Con la Calculadora de estadística → Estadística descriptiva, la media de los 12 datos es $\bar x = \frac{9{,}74}{12} = 0{,}8117$. Se reemplaza:

```math
\hat\theta = \frac{2\cdot0{,}8117 - 1}{1 - 0{,}8117} = \frac{0{,}6233}{0{,}1883} = 3{,}309
```

</details>

**Respuesta:**

- a) $\hat\theta = \dfrac{1 - 2\bar X}{\bar X - 1}$
- b) $\hat\theta = 3{,}309$

</details>

---

### 17) Horas de estudio de los ingresantes ⭐

Se quiere estimar el valor medio de las horas de estudio semanales de los alumnos recién ingresados a la UTN. Se toma una muestra de 100 alumnos y se obtiene un promedio de 4 hs 20 min. Sabiendo que la distribución de estos tiempos es aproximadamente Normal con desvío de 55 min:

- a) construir un intervalo de confianza de nivel 90 %, 95 % y 99 % para el valor medio de las horas semanales de estudio.
- b) comparar las longitudes de los intervalos construidos en (a) y dar una conclusión.

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

**El problema.** Se quiere conocer μ, el promedio de horas de **todos** los ingresantes. Solo se tiene el promedio de una muestra de 100: $\bar x$ = 4 h 20 min = **260 min** (todo en minutos). Ese 260 casi seguro no es exactamente μ: otra muestra daría 255 o 263. En lugar de dar un número, se da un **rango**.

💡 **Intervalo de confianza (IC):** un rango "estimación ± margen" que contiene al valor verdadero con una confianza dada (90 %, 95 %…).

💡 **De dónde sale.**
1. El promedio de una muestra varía alrededor de μ con desvío $\frac{\sigma}{\sqrt n}$, llamado **error estándar** (📄 H2, $`\bar X \sim N\left(\mu;\ \frac{\sigma}{\sqrt n}\right)`$).
2. En una normal, el 95 % de los valores cae a menos de 1,96 desvíos del centro. Entonces el 95 % de las veces, $\bar x$ cae a menos de $1{,}96\cdot\frac{\sigma}{\sqrt n}$ de μ.
3. Si $\bar x$ está cerca de μ, **μ está igual de cerca de $\bar x$**. Por eso el IC es $\bar x$ ± ese margen.

La fórmula de la hoja, cuando **σ es conocido** (📄 H2):

```math
I.C._\mu = \left(\bar X - z_{1-\frac\alpha2}\cdot\frac{\sigma}{\sqrt n};\ \bar X + z_{1-\frac\alpha2}\cdot\frac{\sigma}{\sqrt n}\right)
```

- **1 − α** es la confianza. α es lo que se acepta errar, repartido mitad en cada cola (α/2).
- **$z_{1-\frac\alpha2}$** es el z que deja $1 - \frac\alpha2$ a la izquierda. Es lo que se carga en la app como P(X<x).

**¿σ conocido?** Sí: "la distribución de estos tiempos tiene desvío 55" habla de la **población**. Error estándar: $\frac{55}{\sqrt{100}} = 5{,}5$ min, igual para los tres niveles.

**a)** Cambia solo el z:
```
90 %: X~N(μ;σ)  μ=0  σ=1  P(X<x)=0.95    → x=1.64485
95 %: X~N(μ;σ)  μ=0  σ=1  P(X<x)=0.975   → x=1.95996
99 %: X~N(μ;σ)  μ=0  σ=1  P(X<x)=0.995   → x=2.57583
```

| Nivel | z | Margen = z × 5,5 | IC = 260 ± margen |
|---|---|---|---|
| 90 % | 1,645 | 9,05 | (250,95; 269,05) |
| 95 % | 1,960 | 10,78 | (249,22; 270,78) |
| 99 % | 2,576 | 14,17 | (245,83; 274,17) |

(Las pequeñas diferencias con la respuesta son por redondear z.)

**b)** La longitud es punta derecha menos punta izquierda: $2\cdot z\cdot\frac{\sigma}{\sqrt n}$. Da 18,1, 21,6 y 28,3. Lo único que cambia es z, que crece con la confianza.

**Más confianza = intervalo más ancho = menos precisión.** Para "embocar" más seguido hay que abrir el rango. La única forma de tener mucha confianza **y** un intervalo angosto es aumentar n, porque el $\sqrt n$ está abajo.

💡 **Cómo se interpreta "95 % de confianza"** (❌): μ es fijo. Lo que varía es el intervalo, porque depende de la muestra. Si se repitiera con muchísimas muestras, el 95 % de los intervalos contendría a μ. Se dice "**confío** al 95 %", no "hay 95 % de probabilidad".

</details>

**Respuesta:**

- a) $I_{90} = [250{,}925;\ 269{,}075]$, $I_{95} = [249{,}22;\ 270{,}78]$, $I_{99} = [245{,}81;\ 274{,}19]$ (en minutos)
- b) $L_{90} < L_{95} < L_{99}$: cuando aumenta la confianza se pierde precisión

</details>

---

### 18) Estatura promedio ⭐

Se quiere estimar la estatura promedio en la población, que se supone tiene una distribución Normal con σ = 4 cm. Se toma una muestra de 144 personas y se obtiene que el promedio muestral es de 168 cm.

- a) Calcular el intervalo de confianza para la altura promedio de la población con un nivel de confianza del 98 %.
- b) ¿De qué tamaño debería ser la muestra para mantener el mismo error muestral (que el obtenido en (a)) pero con un nivel de confianza del 95 %?

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

💡 **Intervalo de confianza para μ con σ conocido** (📄 H2):

```math
I.C._\mu = \left(\bar X - z_{1-\frac\alpha2}\cdot\frac{\sigma}{\sqrt n};\ \bar X + z_{1-\frac\alpha2}\cdot\frac{\sigma}{\sqrt n}\right)
```

Es "promedio de la muestra ± margen". El margen, $d = z\cdot\frac{\sigma}{\sqrt n}$, se llama **error muestral** o error máximo de estimación. Sale de que el promedio varía alrededor de μ con desvío $\frac{\sigma}{\sqrt n}$ (📄 H2, $`\bar X \sim N(\mu;\ \sigma/\sqrt n)`$).

**a)** σ = 4 es de la población (conocido), n = 144 y $\bar x = 168$. Con 98 % de confianza, α = 0,02, cada cola tiene 0,01, y el z deja 0,99 a la izquierda:
```
X~N(μ;σ)   μ=0   σ=1   P(X<x)=0.99   → x=2.32635
```

```math
d = 2{,}32635\cdot\frac{4}{\sqrt{144}} = 2{,}32635\cdot0{,}3333 = 0{,}7754 \text{ cm}
```

```math
I.C._\mu = (168 - 0{,}7754;\ 168 + 0{,}7754) = (167{,}22;\ 168{,}78) \text{ cm}
```

**b)** Ahora se quiere el **mismo error** d = 0,7754, pero con 95 % de confianza. La incógnita es n.

💡 **Tamaño de muestra** (❌, despeje de la fórmula del IC). Se plantea "margen ≤ d" y se despeja n:
```
X~N(μ;σ)   μ=0   σ=1   P(X<x)=0.975   → x=1.95996
```

```math
1{,}96\cdot\frac{4}{\sqrt n} \le 0{,}7754 \;\Rightarrow\; \sqrt n \ge \frac{1{,}96\cdot4}{0{,}7754} = 10{,}11 \;\Rightarrow\; n \ge 102{,}2
```

**Siempre se redondea hacia arriba:** con 102 el error quedaría apenas mayor que 0,7754. Entonces **n = 103**.

⚠️ La respuesta dice 102 porque redondea d a 0,78 antes de despejar: $(1{,}96\cdot4/0{,}78)^2 = 101{,}0$. Con d sin redondear, da 103.

Da menos de 144 porque se pide **menos** confianza (95 % < 98 %): con menos exigencia alcanza con menos gente para el mismo error.

</details>

**Respuesta:**

- a) $I_{98} = [167{,}22;\ 168{,}78]$ cm
- b) n ≃ 102 (103 sin redondear d)

</details>

---

### 19) Interpretación de un IC para σ² (T) ⭐

(T) Supongamos que a partir de una muestra aleatoria $X_1, X_2, \dots, X_{100}$, donde $X_i$ es el tiempo de duración de cierto procedimiento que tiene distribución Normal con media de 20 minutos, se construyó un intervalo de confianza para la varianza poblacional de nivel 0,98 y este intervalo resultó [5,28; 10,2] min². Indicar si las siguientes afirmaciones son verdaderas o falsas, justificando adecuadamente en cada caso.

- a) La probabilidad de que σ² se encuentre entre 5,28 y 10,2 es de aproximadamente 98 %.
- b) Si en lugar de hacer 100 observaciones se hubieran tomado 1000 y se hubiera construido un intervalo de confianza de nivel 0,98, este último con certeza habría resultado incluido en [5,28; 10,2] min².
- c) Si se tomaran muchas muestras independientes de tamaño 100 y para cada una de ellas se calculara un intervalo de confianza con el mismo procedimiento, alrededor del 98 % de estos intervalos contendrían a σ².
- d) Si se duplica el tamaño de la muestra, la longitud del intervalo se reduciría a la mitad.
- e) Si se tomaran muchas muestras independientes de tamaño 100, los promedios muestrales de las mismas estarían contenidos en el intervalo $\left[20 - 1{,}96\frac{\sqrt{5{,}28}}{10};\ 20 + 1{,}96\frac{\sqrt{10{,}2}}{10}\right]$.

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

💡 **La idea que evalúa este ejercicio: qué significa "98 % de confianza"** (❌, hay que saberlo). Una analogía:
- el parámetro (σ²) es un **poste clavado**: un número fijo, que no se mueve;
- cada muestra es **tirar un aro**: el intervalo, que depende de la muestra;
- un método de nivel 98 % es un tirador que emboca 98 de cada 100 tiros.

Una vez tirado, **ese** aro embocó o no embocó: ya no hay probabilidad. El 98 % describe al **método**, no a un intervalo particular.

El intervalo dado salió de la fórmula para varianzas (📄 H2):

```math
I.C._{\sigma^2} = \left(\frac{(n-1)S^2}{\chi^2_{n-1;1-\frac\alpha2}};\ \frac{(n-1)S^2}{\chi^2_{n-1;\frac\alpha2}}\right)
```

Lo único aleatorio ahí es $S^2$, la varianza de la muestra.

**a) F.** σ² es fijo y [5,28; 10,2] también, una vez calculado. No queda nada aleatorio. Lo correcto es decir "98 % de **confianza**".

**b) F.** Con 1000 datos se tira **otro aro**: otra $S^2$, otros χ². Tiende a ser más angosto, pero puede quedar corrido. "Con certeza" es falso: con datos al azar nunca hay certeza.

**c) V.** Es exactamente la definición del 98 %: con muchas muestras, alrededor del 98 % de los intervalos contienen a σ².

**d) F.** La longitud es (punta derecha − punta izquierda) $= (n-1)S^2\left(\frac{1}{\chi^2_{n-1;\alpha/2}} - \frac{1}{\chi^2_{n-1;1-\alpha/2}}\right)$. Con la misma $S^2$, el factor $(n-1)\left(\dots\right)$ vale 0,695 con n = 100 y 0,478 con n = 200:
```
n=100:  X~χ²(ν)  ν=99    P(X<x)=0.01 → 69.230    P(X<x)=0.99 → 134.642
n=200:  X~χ²(ν)  ν=199   P(X<x)=0.01 → 155.548   P(X<x)=0.99 → 248.329
```
Se reduce a ≈ 69 %, no a la mitad. La precisión mejora más o menos como $1/\sqrt n$: para la mitad haría falta cuatro veces n.

**e) F.** Tiene tres errores:
1. Usa las puntas de un IC **para σ²** como si fueran desvíos para armar algo sobre **promedios**.
2. 1,96 corresponde a 95 %, no a 98 %.
3. Ningún intervalo contiene a "todos" los promedios: por 📄 H2 ($`\bar X \sim N(\mu;\ \sigma/\sqrt n)`$), solo una proporción.

</details>

**Respuesta:** a) F · b) F · c) V · d) F · e) F

</details>

---

### 20) Resistencia de barras de cerámica ⭐

Un artículo de la revista *American Ceramic Society Bulletin* contiene información acerca de la distribución de las resistencias a la fractura, en MPa, de ciertas barras de cerámica quemadas en determinado horno: se sabe que tienen distribución Normal y que el desvío poblacional es σ = 3,73 MPa. Una muestra de tamaño n = 121 arrojó un promedio de $\bar X$ = 89,10 MPa.

- a) Calcular un intervalo de confianza del 95 % para la resistencia real promedio.
- b) ¿Cómo se modificaría este intervalo si se desconociera la varianza poblacional y la muestra arrojara una desviación estándar de 4,2 MPa?

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

💡 **Intervalo de confianza para μ:** "promedio de la muestra ± margen". El margen sale de que el promedio varía alrededor de μ con desvío $\frac{\sigma}{\sqrt n}$ (📄 H2, $`\bar X \sim N(\mu;\ \sigma/\sqrt n)`$).

**a) σ conocido** ("se sabe que el desvío poblacional es 3,73"). Fórmula con z (📄 H2):

```math
I.C._\mu = \left(\bar X \mp z_{1-\frac\alpha2}\cdot\frac{\sigma}{\sqrt n}\right)
```

```
X~N(μ;σ)   μ=0   σ=1   P(X<x)=0.975   → x=1.95996
```

```math
d = 1{,}96\cdot\frac{3{,}73}{\sqrt{121}} = 1{,}96\cdot0{,}3391 = 0{,}665 \;\Rightarrow\; (89{,}10 - 0{,}665;\ 89{,}10 + 0{,}665) = (88{,}44;\ 89{,}76)
```

**b) σ desconocido.** Ahora solo se tiene **S = 4,2**, el desvío de la muestra.

💡 **La t de Student.** Si se reemplaza σ por S, hay que pagar un precio: S también es una estimación y puede haber salido corrida. Para compensar, en lugar de z se usa la **t de Student**: una campana parecida a la normal, con colas más gordas, que da un número un poco mayor. Su parámetro son los **grados de libertad**, n − 1. Con muchos datos se parece cada vez más a la normal.

La fórmula (📄 H2):

```math
I.C._\mu = \left(\bar X \mp t_{n-1;1-\frac\alpha2}\cdot\frac{S}{\sqrt n}\right)
```

```
X~t(ν)   ν=120   P(X<x)=0.975   → x=1.97993
```

```math
d = 1{,}97993\cdot\frac{4{,}2}{11} = 1{,}97993\cdot0{,}3818 = 0{,}756 \;\Rightarrow\; (88{,}34;\ 89{,}86)
```

Con n = 121, z daría casi lo mismo (0,748). El repo usa z en el paso intermedio.

**¿Cómo se modificó?** Se ensanchó:
- **sobre todo** porque S = 4,2 es mayor que σ = 3,73 (esta muestra salió más dispersa);
- **un poquito** porque t = 1,98 es mayor que z = 1,96.

</details>

**Respuesta:**

- a) $IC_{95} = [88{,}45;\ 89{,}75]$ MPa
- b) $IC_{95} = [88{,}34;\ 89{,}86]$ MPa (más ancho)

</details>

---

### 21) Hemoglobina de jugadores de hockey ⭐

Un artículo del *Journal of Sports Science* expone un intervalo de confianza para el promedio del nivel de hemoglobina de los jugadores de hockey sobre hielo (en g/dl) en la Olimpíada de Canadá. Con 20 jugadores, fue estimado con un 95 % de confianza, obteniéndose el intervalo (15,01; 15,59) g/dl.

- a) Indicar los valores de $\bar x$ y s para esta muestra. Suponga que el nivel de hemoglobina de los jugadores sigue una distribución Normal.
- b) Si se conociera la varianza poblacional y fuera de 0,36 (g/dl)², ¿cuál sería el nivel de confianza del intervalo construido?

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

**La situación es al revés de lo habitual:** el intervalo ya está armado y hay que **desarmarlo**.

💡 **Estructura de un IC para μ:** "promedio ± margen". Con σ desconocido (piden s, así que no se conocía σ), la fórmula es (📄 H2):

```math
I.C._\mu = \left(\bar X - t_{n-1;1-\frac\alpha2}\cdot\frac{S}{\sqrt n};\ \bar X + t_{n-1;1-\frac\alpha2}\cdot\frac{S}{\sqrt n}\right)
```

La **t de Student** reemplaza a z cuando se usa S en lugar de σ. Es un poco más grande, para compensar la incertidumbre extra. Tiene n − 1 grados de libertad.

**a)** Igualando cada punta se arma un sistema. Llamo d al margen:

```math
\bar x - d = 15{,}01 \qquad \bar x + d = 15{,}59
```

- **Sumando** las dos: $2\bar x = 30{,}60$, así que $\bar x = 15{,}30$. Es el punto medio, porque el intervalo es simétrico.
- **Restando:** $2d = 0{,}58$, así que d = 0,29.

Ahora se despeja S del margen, $d = t\cdot\frac{S}{\sqrt n}$, con el t de 19 grados de libertad y 95 %:
```
X~t(ν)   ν=19   P(X<x)=0.975   → x=2.09302
```

```math
0{,}29 = 2{,}09302\cdot\frac{S}{\sqrt{20}} \;\Rightarrow\; S = \frac{0{,}29\cdot\sqrt{20}}{2{,}09302} = 0{,}62
```

**b)** Si se conociera σ = √0,36 = 0,6, el intervalo se armaría con z (📄 H2, $`\bar X \mp z_{1-\frac\alpha2}\frac{\sigma}{\sqrt n}`$). Con el **mismo** margen 0,29, la incógnita es z:

```math
0{,}29 = z\cdot\frac{0{,}6}{\sqrt{20}} \;\Rightarrow\; z = \frac{0{,}29\cdot\sqrt{20}}{0{,}6} = 2{,}1615
```

Se busca qué área deja ese z a la izquierda (📄 H1, $`P(Z < z) = \Phi(z)`$):
```
X~N(μ;σ)   μ=0   σ=1   P(X<x)   x=2.1615   → 0.98467
```
Eso es $1 - \frac\alpha2$, así que $\frac\alpha2 = 0{,}01533$, α = 0,0307 y **1 − α ≈ 0,97**.

Conocer σ quita incertidumbre, así que el mismo intervalo vale más confianza (97 % > 95 %).

</details>

**Respuesta:**

- a) $\bar x = 15{,}3$; s = 0,62
- b) 0,97

</details>

---

### 22) Resistencia de cuerdas ⭐

La resistencia a la rotura, expresada en kg, de 12 ejemplares de cuerda es de 280, 242, 270, 285, 273, 275, 266, 257, 285, 274, 258, 264. Estimar la resistencia media mediante un intervalo de confianza con nivel 0,95 suponiendo distribución Normal.

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

**¿Qué se estima?** μ, la resistencia media de **todas** las cuerdas de ese tipo. Solo hay 12 datos.

💡 **Intervalo de confianza:** "promedio de la muestra ± margen". El margen depende de cuánto varía el promedio, que es $\frac{\sigma}{\sqrt n}$ (📄 H2, $`\bar X \sim N(\mu;\ \sigma/\sqrt n)`$).

**Paso 1, sacar $\bar x$ y s de los datos.** Calculadora de estadística → **Estadística descriptiva**:
```
→ n = 12   media = 269.0833   desvío = 12.5731   error estándar = 3.6295
```
El "error estándar" de la app ya es $\frac{s}{\sqrt n} = \frac{12{,}5731}{\sqrt{12}}$. El desvío debe ser el que divide por n − 1: si da 12,04, está dividiendo por n.

**Paso 2, ¿z o t?** No se conoce σ, solo s (de la muestra). 💡 Cuando se reemplaza σ por s, se usa la **t de Student** en lugar de z: una campana con colas más gordas, que da un número un poco mayor para compensar la incertidumbre de estimar σ. Tiene n − 1 = 11 grados de libertad.

Con solo 12 datos, esto **exige que la población sea Normal**: por eso el enunciado lo supone.

📄 H2:

```math
I.C._\mu = \left(\bar X \mp t_{n-1;1-\frac\alpha2}\cdot\frac{S}{\sqrt n}\right)
```

```
X~t(ν)   ν=11   P(X<x)=0.975   → x=2.20099
```

**Paso 3:**

```math
d = 2{,}20099\cdot3{,}6295 = 7{,}99 \;\Rightarrow\; I.C._\mu = (269{,}08 - 7{,}99;\ 269{,}08 + 7{,}99) = (261{,}09;\ 277{,}07) \text{ kg}
```

Con 95 % de confianza, la resistencia media está entre 261 y 277 kg.

</details>

**Respuesta:** $IC_{95} = [261{,}09;\ 277{,}06]$ kg

</details>

---

### 23) Desvío de resistencias eléctricas ⭐

Se tomó una muestra de n = 36 resistencias eléctricas, resultando la desviación estándar muestral de las lecturas s = 2,81 ohm. Suponiendo normalidad en la distribución de las resistencias, hallar un intervalo de confianza de 95 % para σ.

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

**¿Qué cambia?** Ahora no interesa el promedio, sino **cuánto varían** las resistencias: σ. La muestra dio s = 2,81, pero el σ verdadero puede ser otro.

💡 **Por qué no sirve "estimación ± margen".** Esa receta funciona con el promedio porque es Normal. La varianza muestral **no** es Normal: nunca es negativa y es asimétrica. Si la población es Normal, la cantidad $\frac{(n-1)S^2}{\sigma^2}$ tiene una distribución conocida, la **χ² (chi cuadrado)** con n − 1 grados de libertad (📄 H2, si $X \sim N$, $`\frac{(n-1)S^2}{\sigma^2} \sim \chi^2_{n-1}`$).

De ahí sale el intervalo para la **varianza**. Se encierra esa cantidad entre los dos valores de χ² que dejan α/2 en cada cola, y se despeja σ² (📄 H2):

```math
I.C._{\sigma^2} = \left(\frac{(n-1)S^2}{\chi^2_{n-1;1-\frac\alpha2}};\ \frac{(n-1)S^2}{\chi^2_{n-1;\frac\alpha2}}\right)
```

- Como la χ² es asimétrica, hacen falta **dos** valores distintos, uno para cada cola.
- En la punta **izquierda** va el χ² **grande** (el de 1 − α/2): dividir por un número grande da un resultado chico.
- Para **σ** se saca raíz a las dos puntas (❌): la raíz conserva el orden.

**Cuentas** (n − 1 = 35, α/2 = 0,025):
```
X~χ²(ν)   ν=35   P(X<x)=0.975   → x=53.2033
X~χ²(ν)   ν=35   P(X<x)=0.025   → x=20.5694
```

```math
(n-1)s^2 = 35\cdot2{,}81^2 = 276{,}36
```

```math
I.C._{\sigma^2} = \left(\frac{276{,}36}{53{,}2033};\ \frac{276{,}36}{20{,}5694}\right) = (5{,}195;\ 13{,}436)
```

```math
I.C._\sigma = (\sqrt{5{,}195};\ \sqrt{13{,}436}) = (2{,}28;\ 3{,}67) \text{ ohm}
```

Control: s = 2,81 queda adentro, pero **no** en el centro. Es normal, porque la χ² es asimétrica.

</details>

**Respuesta:** $IC_{95} = [2{,}28;\ 3{,}67]$ ohm

</details>

---

### 24) Altura de un río ⭐

Se midió la altura de un río en un punto geográfico dado durante 20 días al azar del verano, obteniéndose los siguientes valores en cm:

69,5 71,9 72,6 73,1 73,3 73,5 75,5 75,7 75,8 76,1 79,7 79,5 80,1 82,6 83,7 92,7 78,0 77,9 78,1 79,6

- a) ¿Qué condiciones se necesitan para que resulte válida la construcción de un intervalo de confianza para la varianza poblacional?
- b) Construir un intervalo de confianza de 99 % para la desviación estándar de la distribución de la altura de este río en verano.

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

💡 **Intervalo para la varianza.** La varianza muestral S² no tiene distribución Normal. Lo que se conoce es que, **si la población es Normal**, $\frac{(n-1)S^2}{\sigma^2}$ sigue una **χ²** con n − 1 grados de libertad (📄 H2, "si X ~ N(μ;σ)"). La χ² es una distribución asimétrica que solo toma valores positivos.

**a) Condiciones.** Todo el método se apoya en esa frase de la hoja, que exige:
1. **población Normal**. Es obligatorio: a diferencia del promedio, no hay TCL que lo salve.
2. **observaciones independientes** (muestra aleatoria). Por eso los días son "al azar": si fueran seguidos, una creciente afectaría varios días.

**b)** Fórmula de la hoja (📄 H2):

```math
I.C._{\sigma^2} = \left(\frac{(n-1)S^2}{\chi^2_{n-1;1-\frac\alpha2}};\ \frac{(n-1)S^2}{\chi^2_{n-1;\frac\alpha2}}\right)
```

Se piden σ (el desvío): al final se saca **raíz** a las dos puntas (❌).

**Datos.** Calculadora de estadística → **Estadística descriptiva** con los 20 valores:
```
→ n = 20   media = 77.445   varianza = 26.351   desvío = 5.1333
```

**χ²** con 19 grados de libertad y 99 % (α/2 = 0,005 en cada cola):
```
X~χ²(ν)   ν=19   P(X<x)=0.995   → x=38.5823
X~χ²(ν)   ν=19   P(X<x)=0.005   → x=6.84397
```

**Reemplazo:**

```math
(n-1)S^2 = 19\cdot26{,}351 = 500{,}67
```

```math
I.C._{\sigma^2} = \left(\frac{500{,}67}{38{,}5823};\ \frac{500{,}67}{6{,}84397}\right) = (12{,}98;\ 73{,}15)
```

```math
I.C._\sigma = (\sqrt{12{,}98};\ \sqrt{73{,}15}) = (3{,}602;\ 8{,}553) \text{ cm}
```

Es muy ancho: hay pocos datos, se pide mucha confianza, y estimar una dispersión es más difícil que estimar un promedio.

</details>

**Respuesta:**

- a) Distribución Normal e independencia de las observaciones
- b) $IC_{99} = [3{,}602;\ 8{,}553]$ cm

</details>

---

### 25) Obra de teatro: tamaño de muestra ⭐

Se quiere estimar la proporción de personas que han visto una cierta obra de teatro en cartel. ¿Qué tamaño de muestra se deberá tomar para asegurar un nivel de confianza del 99 % y un margen de error de 0,02? Para el tamaño de muestra obtenido, hallar el intervalo de confianza para la proporción en cuestión, asumiendo que la proporción muestral es de 0,35. ¿Se logró el error objetivo?

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

💡 **Intervalo de confianza para una proporción.** Se quiere estimar p, la fracción de **toda** la población que vio la obra. Se encuesta a n personas y $\hat p$ es la fracción de la muestra que dijo que sí.

Cada persona es un 1 (la vio) o un 0, y $\hat p$ es el promedio de esos unos y ceros. Por el TCL es aproximadamente Normal (📄 H2, $`\hat p \sim N\left(p;\ \sqrt{\frac{p(1-p)}{n}}\right)`$). De ahí la fórmula, con la misma estructura de siempre, "estimación ± margen" (📄 H2):

```math
I.C._p = \left(\hat p \mp z_{1-\frac\alpha2}\sqrt{\frac{\hat p(1-\hat p)}{n}}\right), \quad n \ge 100
```

**Parte 1, tamaño de muestra.** Se quiere que el margen sea a lo sumo 0,02:

```math
z\sqrt{\frac{p(1-p)}{n}} \le 0{,}02
```

**Problema:** todavía no se encuestó a nadie, así que no hay $\hat p$. 💡 **Peor caso** (❌): $p(1-p)$ vale como máximo 0,25, cuando p = 0,5. Si se calcula n con 0,25, el margen se cumple **sea cual sea** el p real.
```
X~N(μ;σ)   μ=0   σ=1   P(X<x)=0.995   → x=2.57583
```
✍️ Despejando n:

```math
n \ge \frac{z^2\cdot0{,}25}{0{,}02^2} = \frac{2{,}57583^2\cdot0{,}25}{0{,}0004} = 4146{,}8 \;\Rightarrow\; n = 4147
```

Se redondea siempre hacia arriba.

⚠️ La respuesta usa z = 2,58 redondeado: $\frac{2{,}58^2\cdot0{,}25}{0{,}0004} = 4160{,}25$, así que 4161. Con el z exacto de la app es 4147. Cualquiera de los dos cumple.

**Parte 2, el intervalo** con $\hat p = 0{,}35$ (y n = 4147 ≥ 100 ✓):

```math
d = 2{,}57583\sqrt{\frac{0{,}35\cdot0{,}65}{4147}} = 2{,}57583\cdot0{,}007407 = 0{,}0191
```

```math
I.C._p = (0{,}35 - 0{,}0191;\ 0{,}35 + 0{,}0191) = (0{,}331;\ 0{,}369)
```

**Parte 3, ¿se logró el error?** Sí: 0,0191 ≤ 0,02. Era esperable, porque se planificó con el peor caso y $0{,}35\cdot0{,}65 = 0{,}2275 < 0{,}25$.

</details>

**Respuesta:** n ≥ 4161; $IC_{99} = [0{,}331;\ 0{,}369]$; sí se logró el error (d ≈ 0,019).

</details>

---

### 26) Elongación de telas *modal* ⭐

En una muestra de 81 piezas de tela *modal* se obtuvo una elongación media muestral de 8,17 % y un desvío estándar muestral del 1,42 %. Además, la tercera parte de las telas observadas tuvo elongaciones superiores a 8,4. Suponiendo que la elongación sigue una distribución Normal, estimar mediante un intervalo del 95 % de confianza:

- a) el verdadero valor medio de elongación μ.
- b) el desvío estándar poblacional de la elongación σ.
- c) la proporción poblacional de telas con elongación superior a 8,4.

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

Con **una sola muestra** se arman tres intervalos distintos. Lo importante es reconocer **qué herramienta va en cada caso**.

**Datos:** n = 81, $\bar x = 8{,}17$, s = 1,42 (de la **muestra**: σ es desconocido) y $\hat p = \frac13$ ("la tercera parte").

| Inciso | Qué se estima | Herramienta | Por qué |
|---|---|---|---|
| a) | μ | t con 80 g.l. | σ desconocido, se usa s |
| b) | σ | χ² con 80 g.l. | Es una dispersión |
| c) | p | z | Es una proporción |

```
X~t(ν)     ν=80          P(X<x)=0.975   → x=1.99006
X~χ²(ν)    ν=80          P(X<x)=0.975   → x=106.629
X~χ²(ν)    ν=80          P(X<x)=0.025   → x=57.1532
X~N(μ;σ)   μ=0   σ=1     P(X<x)=0.975   → x=1.95996
```

**a)** 💡 IC para μ con σ desconocido: "promedio ± t·s/√n" (📄 H2). La t reemplaza a z cuando se usa s en lugar de σ.

```math
d = 1{,}99006\cdot\frac{1{,}42}{\sqrt{81}} = 1{,}99006\cdot0{,}1578 = 0{,}314 \;\Rightarrow\; (7{,}856;\ 8{,}484)
```

**b)** 💡 IC para la varianza, si la población es Normal (📄 H2): $\left(\frac{(n-1)S^2}{\chi^2_{n-1;1-\alpha/2}};\ \frac{(n-1)S^2}{\chi^2_{n-1;\alpha/2}}\right)$. El χ² grande va a la izquierda. Para σ se saca raíz (❌).

```math
(n-1)s^2 = 80\cdot1{,}42^2 = 161{,}31 \;\Rightarrow\; I.C._\sigma = \left(\sqrt{\frac{161{,}31}{106{,}629}};\ \sqrt{\frac{161{,}31}{57{,}1532}}\right) = (1{,}23;\ 1{,}68)
```

**c)** 💡 IC para una proporción (📄 H2): $\hat p \mp z\sqrt{\frac{\hat p(1-\hat p)}{n}}$.

```math
d = 1{,}96\sqrt{\frac{\frac13\cdot\frac23}{81}} = 1{,}96\cdot0{,}0524 = 0{,}103 \;\Rightarrow\; (0{,}231;\ 0{,}436)
```

⚠️ La hoja pide n ≥ 100 para este IC, y acá n = 81. Conviene aclararlo como observación.

</details>

**Respuesta:**

- a) $IC_\mu = [7{,}856;\ 8{,}484]$
- b) $IC_\sigma = [1{,}23;\ 1{,}68]$
- c) $IC_p = [0{,}231;\ 0{,}436]$

</details>

---

### 27) Defectos en neumáticos ⭐

Un artículo sobre "Evaluaciones de neumáticos bajo condición de esfuerzo" reporta que de una muestra aleatoria de 350 neumáticos, 54 mostraron daños severos, 48 manchas y 16 ambos tipos de defecto.

- a) Calcular un intervalo de confianza del 99 % para la proporción de neumáticos con algún defecto.
- b) Calcular un intervalo de confianza del 95 % para la proporción de neumáticos con más de un defecto.
- c) Calcular un intervalo de confianza del 95 % para la proporción de neumáticos con un único defecto.

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

**Paso 1, contar bien** (la trampa es de la U1). Los 54 con daño severo **incluyen** a los 16 que tienen los dos defectos, y lo mismo los 48 con manchas. Si se suma 54 + 48, esos 16 se cuentan dos veces. Una tabla de doble entrada lo ordena (D = daño severo, M = manchas):

|  | M | sin M | Total |
|---|---|---|---|
| D | 16 | 54 − 16 = 38 | 54 |
| sin D | 48 − 16 = 32 | 264 | 296 |
| Total | 48 | 302 | 350 |

- **Algún defecto** (al menos uno): 16 + 38 + 32 = **86**. Es lo mismo que 54 + 48 − 16, la regla de la unión (📄 H1).
- **Más de un defecto:** con dos tipos, es tener los dos: **16**.
- **Un único defecto:** solo D o solo M: 38 + 32 = **70**.

**Paso 2, los intervalos.** 💡 IC para una **proporción**: se estima p (la fracción en **todos** los neumáticos) con $\hat p$ (la de la muestra). $\hat p$ es un promedio de unos y ceros, así que por TCL es aproximadamente Normal, y el IC tiene la forma "estimación ± margen" (📄 H2):

```math
I.C._p = \left(\hat p \mp z_{1-\frac\alpha2}\sqrt{\frac{\hat p(1-\hat p)}{n}}\right), \quad n \ge 100
```

Acá n = 350 ≥ 100 ✓.

```
99 %: X~N(μ;σ)   μ=0   σ=1   P(X<x)=0.995   → x=2.57583
95 %: X~N(μ;σ)   μ=0   σ=1   P(X<x)=0.975   → x=1.95996
```

| | Cantidad | $\hat p$ | $\sqrt{\hat p(1-\hat p)/350}$ | z | Margen | IC |
|---|---|---|---|---|---|---|
| a) | 86 | 0,2457 | 0,02301 | 2,576 | 0,0593 | (0,1864; 0,3050) |
| b) | 16 | 0,0457 | 0,01116 | 1,960 | 0,0219 | (0,0238; 0,0676) |
| c) | 70 | 0,2000 | 0,02138 | 1,960 | 0,0419 | (0,1581; 0,2419) |

Lectura de a): con 99 % de confianza, entre el 18,6 % y el 30,5 % de todos los neumáticos de ese tipo tienen algún defecto.

</details>

**Respuesta:**

- a) $IC_{99} = [0{,}1863;\ 0{,}3051]$
- b) $IC_{95} = [0{,}0238;\ 0{,}0676]$
- c) $IC_{95} = [0{,}1581;\ 0{,}2419]$

</details>

---

### 28) Grasa en salchichas ⭐

Considere las siguientes muestras de contenido de grasa (en porcentaje) de salchichas seleccionadas al azar de dos marcas A y B:

| A | 25,2 | 21,3 | 22,8 | 17 | 29,8 | 21 | 25,5 | 16 | 20,9 | 19,5 |
|---|---|---|---|---|---|---|---|---|---|---|
| **B** | 24,2 | 20,7 | 21 | 18,9 | 29,1 | 20,5 | 25,2 | 16,3 | | |

Si se supone que los porcentajes de grasa de ambas marcas tienen distribución Normal:

- a) Hallar un intervalo de confianza del 95 % para la diferencia entre los contenidos medios de grasa de las dos marcas.
- b) ¿Es necesario pedir el cumplimiento de alguna otra condición?
- c) Si se conoce que el desvío estándar poblacional del contenido de grasa de la primera marca es de 2,8 g, mientras que el de la segunda es de 2,3 g, construir nuevamente el intervalo pedido en (a).

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

**La idea nueva: comparar dos grupos.** Se quiere saber si una marca tiene más grasa que la otra. Se estima la **diferencia** de medias $\mu_A - \mu_B$ con un intervalo de la forma de siempre:

```math
(\bar x_A - \bar x_B) \pm d
```

📄 H2: $I.C._{\mu_1-\mu_2} = (\bar X_1 - \bar X_2 - d;\ \bar X_1 - \bar X_2 + d)$.

💡 **Cómo se lee al final:**
- si **el 0 está adentro**, la diferencia podría ser cero: **no hay evidencia** de que las marcas difieran;
- si **el 0 queda afuera** (todo el intervalo positivo o todo negativo), sí hay evidencia.

**Paso 1, procesar cada muestra.** Calculadora de estadística → **Estadística descriptiva**, una vez por marca:
```
A (10 valores) → media = 21.9      varianza = 17.0911   desvío = 4.1341
B (8 valores)  → media = 21.9875   varianza = 16.0755   desvío = 4.0094
```
$\bar x_A - \bar x_B = -0{,}0875$: casi iguales.

**a) σ's desconocidos.** 💡 **Varianza combinada $S_p$.** Si las dos marcas tienen **la misma dispersión**, $s_A$ y $s_B$ son dos estimaciones de lo mismo. Se combinan en una sola, más confiable: un promedio ponderado, donde la muestra más grande pesa más (📄 H2):

```math
S_p = \sqrt{\frac{(n_A-1)S_A^2 + (n_B-1)S_B^2}{n_A + n_B - 2}} = \sqrt{\frac{9\cdot17{,}0911 + 7\cdot16{,}0755}{16}} = \sqrt{16{,}647} = 4{,}080
```

Control: queda entre $s_B$ y $s_A$ ✓.

El margen usa t con $n_A + n_B - 2 = 16$ grados de libertad (📄 H2):

```math
d = t_{n_A+n_B-2;1-\frac\alpha2}\,S_p\sqrt{\frac1{n_A} + \frac1{n_B}}
```

```
X~t(ν)   ν=16   P(X<x)=0.975   → x=2.11991
```

```math
d = 2{,}11991\cdot4{,}080\cdot\sqrt{0{,}1 + 0{,}125} = 4{,}103 \;\Rightarrow\; (-0{,}0875 - 4{,}103;\ -0{,}0875 + 4{,}103) = (-4{,}19;\ 4{,}02)
```

**El 0 está adentro:** no hay evidencia de que las marcas difieran en grasa.

**b)** Además de normalidad, hace falta:
- **varianzas poblacionales iguales**, $\sigma_A = \sigma_B$. Sin eso no se pueden combinar en un solo $S_p$. Acá es creíble: 4,13 y 4,01 son muy parecidos.
- **muestras independientes**: las salchichas de A no tienen relación con las de B.

**c) σ's conocidos.** No hace falta combinar ni suponer que son iguales. Se usa z, y cada σ aporta lo suyo (📄 H2):

```math
d = z_{1-\frac\alpha2}\sqrt{\frac{\sigma_A^2}{n_A} + \frac{\sigma_B^2}{n_B}} = 1{,}96\sqrt{\frac{2{,}8^2}{10} + \frac{2{,}3^2}{8}} = 1{,}96\cdot1{,}2022 = 2{,}356
```

```math
I.C. = (-0{,}0875 - 2{,}356;\ -0{,}0875 + 2{,}356) = (-2{,}44;\ 2{,}27)
```

Es más angosto (σ's más chicos y z < t), pero el 0 sigue adentro: la misma conclusión.

</details>

**Respuesta:**

- a) $IC_{95} = [-4{,}183;\ 4{,}023]$
- b) Independencia y varianzas iguales
- c) $IC_{95} = [-2{,}436;\ 2{,}276]$

</details>

---

### 29) Bicisendas *(opcional)*

Se tomaron dos muestras aleatorias de 1000 individuos de Capital Federal y 1500 de la provincia de Buenos Aires y se las encuestó respecto a si acuerdan con la construcción de bicisendas en su barrio o localidad. Como resultado de la encuesta, 400 de los individuos de Capital Federal manifestaron estar de acuerdo, mientras que 900 de la provincia de Buenos Aires acuerdan con la medida.

- a) Hallar un intervalo de confianza de nivel asintótico 95 % para la diferencia de proporciones de acuerdo con la bicisenda en las dos poblaciones.
- b) ¿En cuánto se reduce la longitud del intervalo si se considera una confianza del 90 %?

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

**La idea:** comparar la proporción de acuerdo en dos poblaciones. Se estima la **diferencia** $p_2 - p_1$ con un intervalo "estimación ± margen".

**Proporciones muestrales:** $\hat p_1 = \frac{400}{1000} = 0{,}4$ (Capital) y $\hat p_2 = \frac{900}{1500} = 0{,}6$ (Provincia). La diferencia estimada es 0,2.

💡 **IC para una diferencia de proporciones** (❌, no está en la hoja). Cada $\hat p$ es aproximadamente Normal con varianza $\frac{p(1-p)}{n}$ (📄 H2, la de $`\hat p`$). Las dos muestras son independientes, así que las **varianzas se suman**:

```math
(\hat p_2 - \hat p_1) \pm z_{1-\frac\alpha2}\sqrt{\frac{\hat p_1(1-\hat p_1)}{n_1} + \frac{\hat p_2(1-\hat p_2)}{n_2}}
```

"Nivel asintótico" significa que vale por la aproximación Normal, con n grande.

**a)**
```
X~N(μ;σ)   μ=0   σ=1   P(X<x)=0.975   → x=1.95996
```

```math
d = 1{,}96\sqrt{\frac{0{,}4\cdot0{,}6}{1000} + \frac{0{,}6\cdot0{,}4}{1500}} = 1{,}96\cdot0{,}02 = 0{,}0392
```

```math
I.C.(p_2 - p_1) = (0{,}2 - 0{,}0392;\ 0{,}2 + 0{,}0392) = (0{,}1608;\ 0{,}2392)
```

Longitud: 0,0784. (Si se hace $p_1 - p_2$, da lo mismo con el signo cambiado.)

El 0 queda afuera: hay evidencia de que en la Provincia el acuerdo es mayor.

**b)** Con 90 % cambia solo el z:
```
X~N(μ;σ)   μ=0   σ=1   P(X<x)=0.95   → x=1.64485
```
$d = 1{,}645\cdot0{,}02 = 0{,}0329$, así que el IC es (0,167; 0,233), con longitud 0,0658.

**Reducción:** $\frac{0{,}0658}{0{,}0784} = 0{,}84$, es decir, se acorta un **16 %**. El cociente es simplemente $\frac{1{,}645}{1{,}96}$: no depende de los datos, solo de los z.

</details>

**Respuesta:**

- a) $IC_{95} = [0{,}1608;\ 0{,}2392]$
- b) $IC_{90} = [0{,}167;\ 0{,}233]$: se reduce un 16 %

</details>

---

### 30) Concentración del antibiótico según el equipo ⭐

Se piensa que la concentración del ingrediente activo de un antibiótico es afectada por el tipo de instrumental utilizado en el proceso de fabricación. Se sabe que la desviación estándar de la concentración del ingrediente activo es de 3 g/l, independientemente del tipo de instrumental empleado en su producción. Se realizan 10 observaciones de una muestra de un antibiótico con cada uno de los equipos disponibles, y se obtienen los siguientes datos:

- Equipo 1: 57,9 − 66,2 − 65,4 − 65,4 − 65,2 − 62,6 − 67,6 − 63,7 − 67,2 − 71,0
- Equipo 2: 65,4 − 70,7 − 70,1 − 69,3 − 63,8 − 68,6 − 68,6 − 69,4 − 65,3 − 68,8

Se pide:

- a) Suponiendo normalidad de las distribuciones, encontrar un intervalo de confianza del 95 % para la diferencia entre los valores medios de las concentraciones logradas por cada uno de los equipos.
- b) Considerar ahora la dispersión poblacional desconocida pero igual para ambos equipos.

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

**La pregunta de fondo:** ¿el equipo cambia la concentración media? Se estima la **diferencia** de medias con un intervalo, y se mira si contiene al 0:
- **0 adentro:** no hay evidencia de diferencia;
- **0 afuera:** sí hay.

**Datos.** Calculadora de estadística → **Estadística descriptiva**, una vez por equipo:
```
Equipo 1 → n = 10   media = 65.22   varianza = 11.864   desvío = 3.4444
Equipo 2 → n = 10   media = 68.00   varianza = 5.3778   desvío = 2.3190
```
Se toma 2 − 1 para que dé positivo: $\bar x_2 - \bar x_1 = 2{,}78$.

💡 **Forma del IC** (📄 H2): $I.C._{\mu_1-\mu_2} = (\bar X_1 - \bar X_2 - d;\ \bar X_1 - \bar X_2 + d)$. Lo que cambia según el caso es cómo se calcula d.

**a) σ = 3 conocido** ("se sabe", "independientemente del instrumental"). Se usa z, y cada σ aporta su parte (📄 H2):

```math
d = z_{1-\frac\alpha2}\sqrt{\frac{\sigma_1^2}{n_1} + \frac{\sigma_2^2}{n_2}} = 1{,}96\sqrt{\frac{9}{10} + \frac{9}{10}} = 1{,}96\cdot1{,}3416 = 2{,}63
```

```
X~N(μ;σ)   μ=0   σ=1   P(X<x)=0.975   → x=1.95996
```

```math
I.C.(\mu_2 - \mu_1) = (2{,}78 - 2{,}63;\ 2{,}78 + 2{,}63) = (0{,}15;\ 5{,}41)
```

**b) σ desconocido pero igual en los dos.** 💡 Como la dispersión es la misma, se **combinan** las dos varianzas muestrales en una sola, $S_p$, y se usa **t** con $n_1 + n_2 - 2$ grados de libertad (📄 H2):

```math
S_p = \sqrt{\frac{(n_1-1)S_1^2 + (n_2-1)S_2^2}{n_1 + n_2 - 2}} = \sqrt{\frac{9\cdot11{,}864 + 9\cdot5{,}3778}{18}} = \sqrt{8{,}621} = 2{,}936
```

```math
d = t_{n_1+n_2-2;1-\frac\alpha2}\,S_p\sqrt{\frac1{n_1} + \frac1{n_2}}
```

```
X~t(ν)   ν=18   P(X<x)=0.975   → x=2.10092
```

```math
d = 2{,}10092\cdot2{,}936\cdot\sqrt{0{,}2} = 2{,}76 \;\Rightarrow\; (2{,}78 - 2{,}76;\ 2{,}78 + 2{,}76) = (0{,}02;\ 5{,}54)
```

**Conclusión:** en los dos casos el intervalo es **todo positivo** (no contiene al 0). Hay evidencia de que **el equipo 2 da concentraciones medias mayores**. En b) queda muy justo: arranca en 0,02.

</details>

**Respuesta:**

- a) $IC_{95}(\mu_2 - \mu_1) = [0{,}15;\ 5{,}41]$
- b) $IC_{95}(\mu_2 - \mu_1) = [0{,}02;\ 5{,}53]$

</details>

---

### 31) Vuelos demorados *(opcional)*

Se desea estimar el porcentaje de vuelos demorados en Aeroparque. Las líneas de interés para el estudio son Golazo y LAP. En un determinado mes se seleccionan al azar 100 vuelos de la primera y 121 de la segunda. Resultaron 20 demoras en Golazo y 28 demoras en LAP. Se construyó un intervalo de confianza (LAP − Golazo) para la diferencia de proporciones, siendo su límite superior 0,1605. Hallar el nivel de confianza utilizado.

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

**La situación:** dan un intervalo ya armado (su punta superior) y hay que **desarmarlo** para saber qué confianza se usó.

💡 **IC para una diferencia de proporciones** (❌, no está en la hoja): "estimación ± z · error estándar", con

```math
\text{EE} = \sqrt{\frac{\hat p_1(1-\hat p_1)}{n_1} + \frac{\hat p_2(1-\hat p_2)}{n_2}}
```

Cada proporción tiene varianza $\frac{p(1-p)}{n}$ (📄 H2), y como las muestras son independientes, las varianzas se suman.

**Paso 1, la estimación.** $\hat p_L = \frac{28}{121} = 0{,}2314$ y $\hat p_G = \frac{20}{100} = 0{,}2$, así que la diferencia LAP − Golazo es 0,0314.

**Paso 2, el error estándar:**

```math
\text{EE} = \sqrt{\frac{0{,}2314\cdot0{,}7686}{121} + \frac{0{,}2\cdot0{,}8}{100}} = 0{,}0554
```

**Paso 3, despejar z de la punta superior:**

```math
0{,}0314 + z\cdot0{,}0554 = 0{,}1605 \;\Rightarrow\; z = \frac{0{,}1291}{0{,}0554} = 2{,}33
```

**Paso 4, de z a la confianza.** Se busca qué área deja ese z a la izquierda (📄 H1, $`P(Z < z) = \Phi(z)`$):
```
X~N(μ;σ)   μ=0   σ=1   P(X<x)   x=2.33   → 0.9901
```
Eso es $1 - \frac\alpha2 = 0{,}99$, así que α = 0,02 y la confianza es **1 − α = 0,98**.

</details>

**Respuesta:** 0,98

</details>

---

[← Volver al menú principal](../README.md)
