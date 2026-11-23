# Unidad 2 — Ejercicios resueltos

Ejercicios de la **Práctica 2 de la Guía de TP** (Variables aleatorias).

Cada ejercicio tiene un botón **Solución**. Al abrirlo aparece la respuesta y, arriba de ella, un segundo botón **Solución paso a paso** con el desarrollo completo.

> **Referencias:** ⭐ = ejercicio sugerido como prioritario en los apuntes de la cátedra. ⏭️ = no es necesario resolverlo.

---

### 1) Recorrido y clasificación

Para cada variable aleatoria definida a continuación, indicar el recorrido y clasificarla:

- a) Q: "Número de estudiantes en la lista de un curso en particular que están ausentes el primer día de clase, de los 20 inscriptos".
- b) R: "Tiempo de espera en una caja de un banco antes de ser atendido".
- c) S: "Temperatura máxima y mínima medida en la estación meteorológica de La Plata un día cualquiera del año".
- d) T: "Cantidad de bicicletas en stock en una bicicletería al finalizar un día de la semana, si comenzó la semana con 120 unidades y no realizó reposición".
- e) U: "Número de hijos que debe tener una pareja hasta tener 3 mujeres, siendo su tope 8 hijos".
- f) V: "Cantidad de meses del año en que una fábrica excede los límites permitidos de contaminación ambiental".
- g) W: "Cantidad de dinero que se puede extraer sacando tres monedas de una caja que tiene 2 de 50 ctv, 3 de 25 ctv y 4 de 1 peso".
- h) X: "Presión de un neumático de un coche que ha sido cargado con 32 libras y medido un día cualquiera".
- i) Y: "Número de veces que se debe lanzar al aire una moneda para obtener dos caras o dos cecas consecutivas".
- j) Z: "Número de ruedas que, al recolocarlas al azar en un auto, ocupan su posición original".

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

💡 **Qué es una variable aleatoria (v.a.).** Es un **número** que sale de un experimento aleatorio: cantidad de ausentes, tiempo de espera, presión. Antes de hacer el experimento no se sabe qué número va a salir.

💡 **Recorrido** ($`R_X`$): la lista o el rango de **todos los valores posibles** de la variable.

💡 **Discreta o continua:**
- **Discreta:** sus valores se pueden **contar uno por uno** (0, 1, 2, …), aunque la lista sea infinita. Suele pasar cuando se **cuenta** algo.
- **Continua:** puede tomar **cualquier valor de un intervalo**, con decimales sin fin. Suele pasar cuando se **mide** algo (tiempo, presión, temperatura).

- a) Se **cuentan** ausentes: de 0 a 20 → discreta.
- b) Un tiempo se **mide** y puede valer cualquier número de un intervalo → continua (la guía usa [0; 300] min).
- c) Son **dos** números (máxima y mínima), así que es un par, una v.a. **bidimensional**. Los dos son temperaturas (continuas), con −10° ≤ mín ≤ máx ≤ 40°.
- d) Bicicletas que quedan: de 0 a 120 → discreta.
- e) Como mínimo hacen falta 3 hijos (si nacen tres mujeres seguidas) y como máximo 8 (el tope): {3, …, 8} → discreta.
- f) Meses: de 0 a 12 → discreta.
- g) Se listan las sumas posibles de 3 monedas, eligiendo de 0,25, 0,50 y 1 (hay 3 de 25 ctv, 2 de 50 ctv y 4 de 1 peso):
  - 0,25·3 = 0,75
  - 0,25 + 0,25 + 0,5 = 1
  - 0,25 + 0,5 + 0,5 = 1,25
  - 0,25 + 0,25 + 1 = 1,5
  - 0,5 + 0,25 + 1 = 1,75
  - 0,5 + 0,5 + 1 = 2
  - 0,25 + 1 + 1 = 2,25
  - 0,5 + 1 + 1 = 2,5
  - 1 + 1 + 1 = 3

  Son valores sueltos que se pueden contar → discreta. No hay 0,5 + 0,5 + 0,5, porque hay solo 2 monedas de 50.
- h) Una presión se **mide**: entre 0 y 32 libras → continua.
- i) Como mínimo 2 tiradas (CC o XX), y no hay tope: {2, 3, 4, …}. Es infinita, pero se puede numerar → discreta.
- j) Pueden quedar 0, 1, 2 o 4 ruedas en su lugar. **No** 3: si 3 están en su lugar, la que sobra solo puede ir al lugar libre, que es el suyo → discreta.

</details>

**Respuesta:**
- a) {0, …, 20} D
- b) [0; 300] min C
- c) {(x₁; x₂) / −10° ≤ x₂ ≤ x₁ ≤ 40°} C
- d) {0, …, 120} D
- e) {3, …, 8} D
- f) {0, …, 12} D
- g) {0,75; 1; 1,25; 1,5; 1,75; 2; 2,25; 2,5; 3} D
- h) [0; 32] C
- i) {2, 3, …} D
- j) {0, 1, 2, 4} D

</details>

---

### 2) Estaciones de servicio ⏭️

Se seleccionaron tres estaciones de servicio A, B y C de la ciudad de Buenos Aires, que cuentan respectivamente con 5, 3 y 2 surtidores. En estas estaciones no siempre están todos los surtidores en uso. Dar el recorrido de las siguientes variables aleatorias:

- a) U: "Número total de surtidores en uso entre las estaciones seleccionadas".
- b) V: "(Número de surtidores en uso de la estación B ; Número de surtidores en uso de la estación C)".
- c) W: "Número de estaciones que tienen exactamente 2 surtidores en uso".
- d) X: "Diferencia en el número de surtidores en servicio entre la estación A y la B".

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

💡 El **recorrido** de una variable es la lista de todos los valores que puede tomar. Para encontrarlo, se piensa en el caso más chico y en el más grande, y en si se puede llegar a todos los intermedios.

- **a) Total en uso:** como mínimo ninguno (0) y como máximo todos, 5 + 3 + 2 = 10. Se puede llegar a cualquier número intermedio: {0, …, 10}.
- **b) Par (en uso en B; en uso en C):** cada coordenada va por separado. B va de 0 a 3 y C de 0 a 2, así que el recorrido son todos los pares $(x_1; x_2)$ con $0 \le x_1 \le 3$ y $0 \le x_2 \le 2$.
- **c) Estaciones con exactamente 2 en uso:** cada estación tiene al menos 2 surtidores (A tiene 5, B 3, C 2), así que cualquiera puede tener 2 en uso. Pueden ser ninguna, 1, 2 o las 3: {0, 1, 2, 3}.
- **d) Diferencia A − B:** la más chica es con A en 0 y B en 3, 0 − 3 = −3. La más grande es con A en 5 y B en 0, 5 − 0 = 5. Pasa por todos los enteros intermedios: {−3, …, 5}.

</details>

**Respuesta:**

- a) {0, …, 10}
- b) {(x₁; x₂) / 0 ≤ x₁ ≤ 3, 0 ≤ x₂ ≤ 2}
- c) {0, 1, 2, 3}
- d) {−3, …, 5}

</details>

---

### 3) Bolillas azules ⭐

De una caja con 6 bolillas azules y 2 rojas se extraen 3 sin reposición. Sea X: "cantidad de bolillas azules entre las tres extraídas".

- a) Hallar la función de probabilidad puntual de X.
- b) Hallar E(X) y V(X).
- c) Hallar E(X²), E(1/X), E(1/X²) y V(X²).

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

**a)** 💡 **Función de probabilidad puntual** $p(x) = P(X = x)$: una tabla que dice, para cada valor posible de X, cuál es su probabilidad. Todas tienen que sumar 1.

**Recorrido:** se sacan 3 bolillas y hay solo 2 rojas, así que al menos 1 es azul. X puede valer 1, 2 o 3.

**Probabilidades:** se eligen 3 de 8 sin importar el orden, con todos los grupos igual de probables (Laplace). Hay $\binom83 = 56$ grupos ($`\binom nk`$ es nCr en la calculadora). Para "x azules" se eligen x de las 6 azules **y** el resto de las 2 rojas:
- $P(X=1) = \frac{\binom61\binom22}{56} = \frac{6}{56} = \frac3{28}$
- $P(X=2) = \frac{\binom62\binom21}{56} = \frac{30}{56} = \frac{15}{28}$
- $P(X=3) = \frac{\binom63\binom20}{56} = \frac{20}{56} = \frac5{14}$

Control: 6 + 30 + 20 = 56 ✓. (Es la hipergeométrica de la U3, 📄 H1.)

**b)** 💡 **Esperanza (valor esperado) E(X):** el promedio que daría X si el experimento se repitiera muchísimas veces. Cada valor se multiplica por su probabilidad y se suma (📄 H1, $`E(X) = \sum x_i P(x_i)`$):

$$E(X) = 1\cdot\frac{6}{56} + 2\cdot\frac{30}{56} + 3\cdot\frac{20}{56} = \frac{126}{56} = \frac94 = 2{,}25$$

💡 **Varianza V(X):** mide cuánto se dispersa X alrededor de su esperanza. La forma práctica es $V(X) = E(X^2) - E(X)^2$ (📄 H1), donde $E(X^2)$ se calcula igual que E(X), pero con los valores al cuadrado:

$$E(X^2) = 1^2\cdot\frac{6}{56} + 2^2\cdot\frac{30}{56} + 3^2\cdot\frac{20}{56} = \frac{6 + 120 + 180}{56} = \frac{153}{28}$$

$$V(X) = \frac{153}{28} - \left(\frac94\right)^2 = \frac{153}{28} - \frac{81}{16} = \frac{45}{112} \approx 0{,}402$$

**c)** 💡 **Esperanza de una función de X** (📄 H1, $`E(g(X)) = \sum g(x)P(x)`$): se transforma cada **valor** y se multiplica por la **misma** probabilidad de antes.
- $E(X^2) = \frac{153}{28}$, ya calculada.
- $E(1/X) = \frac11\cdot\frac{6}{56} + \frac12\cdot\frac{30}{56} + \frac13\cdot\frac{20}{56} = \frac{83}{168} \approx 0{,}494$.
- $E(1/X^2) = \frac{6 + 30/4 + 20/9}{56} \approx 0{,}2808$.
- **V(X²):** es la varianza de la variable $X^2$. Con la misma fórmula, $V(X^2) = E[(X^2)^2] - [E(X^2)]^2 = E(X^4) - E(X^2)^2$:

  $$E(X^4) = \frac{1\cdot6 + 16\cdot30 + 81\cdot20}{56} = \frac{2106}{56} \approx 37{,}607 \qquad V(X^2) \approx 37{,}607 - 5{,}464^2 = 37{,}607 - 29{,}858 = 7{,}749$$

⚠️ $E(1/X) \neq 1/E(X)$: en general **no** se puede "meter la función adentro" de la esperanza.

</details>

**Respuesta:**

- a) P(1) = 3/28, P(2) = 15/28, P(3) = 5/14
- b) E = 9/4, V = 45/112
- c) 153/28; 83/168; 0,2808; 7,7487

</details>

---

### 4) Dos urnas ⏭️

Se tienen dos urnas. La urna A tiene 6 bolitas rojas y 4 blancas. La urna B tiene 2 bolitas rojas y 7 blancas. Se extrae una bolita al azar de A y se coloca en B. A continuación se extraen de B, **con reposición**, 2 bolitas. Sea X: "cantidad de bolitas rojas extraídas de la urna B".

- a) Hallar la función de probabilidad de X.
- b) Graficar la función de probabilidad de X.
- c) Repetir (a) pero considerando que las extracciones de B son **sin** reposición.

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

**La idea:** lo que pasa en B depende del color que se pasó desde A. Se calcula la distribución de X **en cada escenario** y después se combinan con la **probabilidad total** (suma de caminos, U1).

**Escenarios:**
- Pasa roja (6/10 = 0,6): B queda con 3R y 7B.
- Pasa blanca (0,4): B queda con 2R y 8B.

**a) Con reposición:** la bolita vuelve, así que las dos extracciones son independientes y en cada una la probabilidad de roja es la misma.
- Si pasó roja, P(R) = 3/10 = 0,3:
  - P(0 rojas) = 0,7·0,7 = 0,49;
  - P(1) = 2·0,3·0,7 = 0,42 (dos órdenes: RB o BR);
  - P(2) = 0,3² = 0,09.
- Si pasó blanca, P(R) = 0,2: 0,8² = 0,64; 2·0,2·0,8 = 0,32; 0,2² = 0,04.

(Es una binomial con n = 2, de la U3.)

**Probabilidad total**, cada valor sumando los dos escenarios con su peso:
- $P(0) = 0{,}6\cdot0{,}49 + 0{,}4\cdot0{,}64 = 0{,}55$
- $P(1) = 0{,}6\cdot0{,}42 + 0{,}4\cdot0{,}32 = 0{,}38$
- $P(2) = 0{,}6\cdot0{,}09 + 0{,}4\cdot0{,}04 = 0{,}07$

Control: 0,55 + 0,38 + 0,07 = 1 ✓.

**b)** Una variable discreta se grafica con **bastones**: una línea vertical en cada valor (0, 1 y 2), de altura igual a su probabilidad (0,55, 0,38 y 0,07).

**c) Sin reposición:** la 1.ª bolita no vuelve, así que la 2.ª se saca de 9. Contando pares **ordenados** (1.ª, 2.ª): con 10 bolitas hay 10·9 = 90 pares.
- **Si pasó roja** (3R, 7B):
  - 0 rojas = blanca y blanca: 7·6 = 42;
  - 1 roja = RB o BR: 3·7 + 7·3 = 42;
  - 2 rojas: 3·2 = 6.
- **Si pasó blanca** (2R, 8B): 0 rojas: 8·7 = 56; 1 roja: 2·2·8 = 32; 2 rojas: 2·1 = 2.

(Todo sobre 90.)

Probabilidad total:
- $P(0) = \frac{0{,}6\cdot42 + 0{,}4\cdot56}{90} = \frac{47{,}6}{90} = \frac{119}{225}$
- $P(1) = \frac{38}{90} = \frac{19}{45}$
- $P(2) = \frac{4{,}4}{90} = \frac{11}{225}$

</details>

**Respuesta:**

- a) 0,55 / 0,38 / 0,07
- c) 119/225 / 19/45 / 11/225

</details>

---

### 5) Neumáticos con baja presión ⭐

Sea X = número de neumáticos de un automóvil, seleccionado al azar, que tienen baja la presión.

| x | 0 | 1 | 2 | 3 | 4 |
|---|---|---|---|---|---|
| p₁(x) | 0,20 | 0,30 | 0,10 | 0,07 | 0,03 |
| p₂(x) | 0,40 | 0,10 | 0,10 | 0,10 | 0,30 |
| p₃(x) | 0,40 | 0,15 | 0,10 | 0,15 | 0,30 |

- a) ¿Cuál de las tres funciones pᵢ(x) de la tabla es una función de probabilidad puntual para X?
- b) Obtener la función de distribución acumulada de X.
- c) Con la función de probabilidad seleccionada en (a), calcular P(2 < X < 4), P(X < 2) y P(X ≠ 0).
- d) Si p(x) = k·(5 − x) para x = 0, 1, 2, 3, 4, ¿cuál debe ser el valor de la constante k para que p sea una función de probabilidad?

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

**a)** 💡 Para que una tabla sea una **función de probabilidad** tiene que cumplir dos cosas:
1. ninguna probabilidad es negativa;
2. todas suman 1, porque X siempre toma algún valor.

Se suman las filas:
- p₁: 0,2 + 0,3 + 0,1 + 0,07 + 0,03 = **0,70**. No suma 1.
- p₂: 0,4 + 0,1 + 0,1 + 0,1 + 0,3 = **1**. ✓
- p₃: 0,4 + 0,15 + 0,1 + 0,15 + 0,3 = **1,10**. No suma 1.

Solo **p₂** sirve.

**b)** 💡 **Función de distribución acumulada** $F(x) = P(X \le x)$: la probabilidad de que X valga x **o menos**. Se va sumando la tabla de izquierda a derecha (📄 H1, $`F(x_k) = \sum_{i \le k} p(x_i)`$):
- F(0) = 0,4;
- F(1) = 0,4 + 0,1 = 0,5;
- F(2) = 0,6;
- F(3) = 0,7;
- F(4) = 1.

Entre dos valores, F se queda quieta: por ejemplo, F(1,5) = P(X ≤ 1,5) = P(X ≤ 1) = 0,5. Por eso se escribe "por escalones": 0 si x < 0, 0,4 en [0; 1), 0,5 en [1; 2), y así.

**c)** Se traduce cada pregunta a qué valores entran:
- P(2 < X < 4): estrictamente entre 2 y 4 solo está el 3, así que P(X = 3) = 0,1.
- P(X < 2): el 0 y el 1, 0,4 + 0,1 = 0,5. Es F(1).
- P(X ≠ 0): todo menos el 0, 1 − 0,4 = 0,6.

**d)** Se pide que la suma dé 1. Con $p(x) = k(5 - x)$, los valores son 5k, 4k, 3k, 2k y k:

$$k(5 + 4 + 3 + 2 + 1) = 15k = 1 \;\Rightarrow\; k = \frac1{15}$$

Además todos son positivos ✓.

</details>

**Respuesta:**

- a) p₂
- b) F = 0 (x < 0); 0,4 [0,1); 0,5 [1,2); 0,6 [2,3); 0,7 [3,4); 1 (x ≥ 4)
- c) 0,1; 0,5; 0,6
- d) k = 1/15

</details>

---

### 6) Llegadas tarde ⭐

La siguiente distribución de probabilidad corresponde a la variable aleatoria X: "cantidad de llegadas tarde a la clase de Probabilidad y Estadística en marzo de un alumno elegido al azar".

| x | 0 | 1 | 2 | 3 | 4 |
|---|---|---|---|---|---|
| p(x) | 0,3 + k | 2k | 0,2 | 0,1 + 5k² | 0,05 |

- a) Hallar el valor de k.
- b) Calcular la probabilidad de que las tardanzas de un alumno elegido al azar sean 3.
- c) Hallar el número más probable de tardanzas. ¿Coincide con el valor esperado de tardanzas?

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

**a)** 💡 Las probabilidades de todos los valores tienen que sumar 1. Se suman las 5 celdas:

$$(0{,}3 + k) + 2k + 0{,}2 + (0{,}1 + 5k^2) + 0{,}05 = 1 \;\Rightarrow\; 5k^2 + 3k + 0{,}65 = 1 \;\Rightarrow\; 5k^2 + 3k - 0{,}35 = 0$$

Es una cuadrática. Con la resolvente:

$$k = \frac{-3 \pm \sqrt{9 + 4\cdot5\cdot0{,}35}}{10} = \frac{-3 \pm 4}{10} \;\Rightarrow\; k = 0{,}1 \text{ o } k = -0{,}7$$

Con k = −0,7, P(X = 1) = 2k sería negativa, y eso es imposible. Entonces **k = 0,1**.

**b)** Se reemplaza: $P(X = 3) = 0{,}1 + 5\cdot0{,}1^2 = 0{,}15$.

**c)** Con k = 0,1, la tabla queda:

| x | 0 | 1 | 2 | 3 | 4 |
|---|---|---|---|---|---|
| p(x) | 0,4 | 0,2 | 0,2 | 0,15 | 0,05 |

💡 **Moda** (el valor "más probable"): el de mayor probabilidad, que es **0**.

💡 **Valor esperado** (📄 H1, $`E(X) = \sum x\,p(x)`$), el promedio a la larga:

$$E(X) = 0\cdot0{,}4 + 1\cdot0{,}2 + 2\cdot0{,}2 + 3\cdot0{,}15 + 4\cdot0{,}05 = 1{,}25$$

**No coinciden.** La moda es el valor que más se repite, y la esperanza es un promedio. La esperanza ni siquiera tiene que ser un valor posible: nadie llega tarde 1,25 veces.

</details>

**Respuesta:**

- a) k = 0,1
- b) 0,15
- c) Moda = 0, E(X) = 1,25; no coinciden.

</details>

---

### 7) Cadenas de eslabones ⏭️

En una fábrica se producen cadenas con 15, 25, 30 o 40 eslabones, en proporciones 2 : 3 : 4 : 6. Se vuelca toda la producción en una sola cinta transportadora. Se eligen de la cinta, al azar, dos cadenas con reposición.

Se definen las variables aleatorias X: "promedio de eslabones de las cadenas elegidas" e Y: "longitud máxima de las cadenas elegidas". Determinar su recorrido.

- a) Hallar la función de probabilidad puntual de cada una de las variables.
- b) Calcular el valor esperado y la varianza de ambas variables.

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

**Paso 1, una cadena sola.** "Proporciones 2 : 3 : 4 : 6" significa que, de cada 2 + 3 + 4 + 6 = 15 cadenas, 2 tienen 15 eslabones, 3 tienen 25, y así. Sea L = eslabones de una cadena:
- P(15) = 2/15
- P(25) = 3/15
- P(30) = 4/15
- P(40) = 6/15

**Paso 2, dos cadenas.** Con reposición, las dos elecciones son **independientes**, así que la probabilidad de un par (L₁, L₂) es el producto $p_i\cdot p_j$. Hay 4 · 4 = 16 pares, todos con denominador 15 · 15 = 225.

**X = promedio = (L₁ + L₂)/2.** Se calcula el promedio de cada par y se **suman las probabilidades de los pares que dan el mismo promedio**:

| X | 15 | 20 | 22,5 | 25 | 27,5 | 30 | 32,5 | 35 | 40 |
|---|---|---|---|---|---|---|---|---|---|
| ·/225 | 4 | 12 | 16 | 9 | 48 | 16 | 36 | 48 | 36 |

Por ejemplo, el promedio 27,5 sale de dos maneras:
- (25, 30) y (30, 25): 2·3·4 = 24;
- (15, 40) y (40, 15): 2·2·6 = 24.

En total 48/225. El 15 solo sale con (15, 15): 2·2 = 4.

**Y = longitud máxima de las dos.** Hay un truco: "el máximo es ≤ y" equivale a "**las dos** son ≤ y". Como son independientes, $P(Y \le y) = P(L \le y)^2$. Después, la probabilidad de cada valor es la diferencia entre escalones consecutivos:
- P(L ≤ 15) = 2/15, así que P(Y ≤ 15) = 4/225 y P(Y = 15) = 4/225.
- P(L ≤ 25) = 5/15, así que P(Y ≤ 25) = 25/225 y P(Y = 25) = 25/225 − 4/225 = 21/225.
- P(L ≤ 30) = 9/15, así que P(Y ≤ 30) = 81/225 y P(Y = 30) = 81/225 − 25/225 = 56/225.
- P(Y = 40) = 1 − 81/225 = 144/225.

**b)** Primero, una sola cadena (📄 H1, $E = \sum x\,p(x)$ y $`V = E(X^2) - E(X)^2`$):

$$E(L) = \frac{15\cdot2 + 25\cdot3 + 30\cdot4 + 40\cdot6}{15} = 31 \qquad V(L) = \frac{225\cdot2 + 625\cdot3 + 900\cdot4 + 1600\cdot6}{15} - 31^2 = 1035 - 961 = 74$$

**X es el promedio de dos cadenas independientes.** Se podría usar la tabla, pero hay un atajo con propiedades (U2/U4):
- La esperanza del promedio es la misma: $E(X) = \frac{31 + 31}{2} = 31$.
- La varianza: $V\left(\frac{L_1 + L_2}{2}\right) = \frac14(V(L_1) + V(L_2)) = \frac{74 + 74}{4} = 37$. El ½ sale al cuadrado, y como son independientes no hay covarianza (📄 H1, $`V(aX + bY) = a^2V(X) + b^2V(Y) + 2ab\,Cov`$).

**Y**, con su tabla:

$$E(Y) = \frac{15\cdot4 + 25\cdot21 + 30\cdot56 + 40\cdot144}{225} = \frac{8025}{225} \approx 35{,}67$$

$$E(Y^2) = \frac{225\cdot4 + 625\cdot21 + 900\cdot56 + 1600\cdot144}{225} \approx 1310{,}33 \;\Rightarrow\; V(Y) \approx 1310{,}33 - 35{,}67^2 \approx 38{,}22$$

</details>

**Respuesta:**

- a) tablas de arriba
- b) E(X) = 31, V(X) = 37; E(Y) ≈ 35,67, V(Y) ≈ 38,2. (La guía da E(Y) = 35,2, pero la cuenta da 8025/225 ≈ 35,67.)

</details>

---

### 8) Lavarropas ⭐

Sea X la capacidad (en kg) de un lavarropas comprado por el próximo cliente que elige la marca *Cándida*. La función de probabilidad puntual de X está dada por:

| xᵢ | 5 | 7,5 | 10 |
|---|---|---|---|
| p(xᵢ) | 0,25 | 0,45 | 0,30 |

- a) Calcular el valor esperado y la varianza de la variable X.
- b) Si el precio del lavarropas es Y = 20X − 7,5, hallar el valor esperado y el desvío estándar del precio del lavarropas *Cándida*.

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

**a)** 💡 **Valor esperado** (📄 H1, $`E(X) = \sum x_i\,p(x_i)`$): cada valor por su probabilidad, sumados. Es la capacidad promedio si se miraran muchísimos clientes.

$$E(X) = 5\cdot0{,}25 + 7{,}5\cdot0{,}45 + 10\cdot0{,}30 = 1{,}25 + 3{,}375 + 3 = 7{,}625 \text{ kg}$$

💡 **Varianza** (📄 H1, $`V(X) = E(X^2) - E(X)^2`$): mide cuánto se apartan los valores del promedio. Primero $E(X^2)$, con los valores al cuadrado:

$$E(X^2) = 25\cdot0{,}25 + 56{,}25\cdot0{,}45 + 100\cdot0{,}30 = 61{,}5625$$

$$V(X) = 61{,}5625 - 7{,}625^2 = 61{,}5625 - 58{,}1406 = 3{,}4219 \text{ kg}^2$$

(Tiene unidades al cuadrado. Para volver a kg está el **desvío estándar**, $\sigma = \sqrt V = 1{,}85$ kg.)

**b)** Y = 20X − 7,5 es una **transformación lineal** de X. No hace falta una tabla nueva, porque hay propiedades:
- **Esperanza** (❌, linealidad): $E(aX + b) = aE(X) + b$. Si a cada precio se le hace lo mismo, al promedio también.

  $$E(Y) = 20\cdot7{,}625 - 7{,}5 = 145$$

- **Varianza:** $V(aX + b) = a^2V(X)$. El −7,5 corre todos los valores por igual y **no cambia la dispersión**, y el 20 la estira, al cuadrado. Sale de 📄 H1, $V(aX + bY) = a^2V(X) + \dots$, tomando la segunda variable como constante.
  
  Entonces el desvío es $\sigma(Y) = |a|\,\sigma(X) = 20\cdot\sqrt{3{,}4219} = 20\cdot1{,}85 = 37$.

</details>

**Respuesta:**

- a) 7,625 y 3,4219
- b) E(Y) = 145, σ(Y) = 37

</details>

---

### 9) Gimnasio Sporties ⭐

La cadena de gimnasios *Sporties* ofrece a sus socios un plan anual con opciones de pago. Para un socio seleccionado al azar, sea X = número de meses para pagar el plan. La función de distribución acumulada de X es:

$$F(x) = \begin{cases} 0 & x < 1 \\ 0{,}1 & 1 \le x < 2 \\ 0{,}4 & 2 \le x < 3 \\ 0{,}6 & 3 \le x < 6 \\ 0{,}9 & 6 \le x < 12 \\ 1 & x \ge 12 \end{cases}$$

Utilizando la función de distribución, calcular las siguientes probabilidades:

- a) P(X < 5), P(X > 2), P(3 ≤ X ≤ 6) y P(3 < X ≤ 6).
- b) P(X < 6 / X ≥ 3).

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

💡 **Función de distribución** $F(x) = P(X \le x)$: la probabilidad acumulada hasta x. En una variable discreta tiene forma de **escalera**:
- cada **salto** está en un valor posible de X;
- la **altura del salto** es la probabilidad de ese valor.

**Leyendo los saltos:**
- en 1 sube de 0 a 0,1, así que P(X = 1) = 0,1;
- en 2 sube a 0,4: P(2) = 0,3;
- en 3 a 0,6: P(3) = 0,2;
- en 6 a 0,9: P(6) = 0,3;
- en 12 a 1: P(12) = 0,1.

$R_X = \{1, 2, 3, 6, 12\}$.

**a)** Se traduce cada pregunta a "hasta dónde acumular". Las reglas de 📄 H1 para discretas son $P(X \le x_i) = F(x_i)$, $P(X \ge x_i) = 1 - F(x_{i-1})$ y $P(x_i \le X \le x_j) = F(x_j) - F(x_{i-1})$.
- **P(X < 5):** los valores menores que 5 son 1, 2 y 3, así que F(3) = 0,6. (F(4,99) también es 0,6, porque la escalera no salta entre 3 y 6.)
- **P(X > 2):** lo contrario de X ≤ 2, así que 1 − F(2) = 1 − 0,4 = 0,6.
- **P(3 ≤ X ≤ 6):** incluye el 3 y el 6. Se acumula hasta 6 y se resta lo que está **antes** del 3 (hasta 2): F(6) − F(2) = 0,9 − 0,4 = 0,5.
- **P(3 < X ≤ 6):** ahora el 3 **no** entra, así que se resta hasta 3: F(6) − F(3) = 0,9 − 0,6 = 0,3. Es solo el 6.

En discretas importa si la desigualdad es ≤ o <: cambia qué valores entran.

**b)** 💡 **Condicional** (📄 H1, $`P(A/B) = \frac{P(A\cap B)}{P(B)}`$). "X < 6 y X ≥ 3" deja solo el 3:

$$P(X < 6 / X \ge 3) = \frac{P(3 \le X < 6)}{P(X \ge 3)} = \frac{P(X = 3)}{1 - F(2)} = \frac{0{,}2}{0{,}6} = \frac13$$

</details>

**Respuesta:**

- a) 0,6; 0,6; 0,5; 0,3
- b) 1/3

</details>

---

### 10) Máquinas tejedoras

Las máquinas tejedoras de una fábrica de elásticos utilizan rayo láser para detectar los hilos rotos. Cuando se detecta un hilo roto, se detiene la máquina tejedora. Consideremos la variable aleatoria X: "cantidad de veces que se detiene la máquina por día". La función de probabilidad de X está dada por:

$$p(x) = \frac{16}{31}\left(\frac12\right)^x \quad \text{para } x = 0, 1, 2, 3, 4 \quad (\text{y } 0 \text{ en otro caso})$$

- a) ¿Cuál es la probabilidad de que un día dado se detenga la máquina?
- b) Si las detenciones en dos días consecutivos son independientes, hallar la probabilidad de que el máximo de detenciones entre las del lunes y las del martes sea exactamente 2.
- c) Hallar la función de probabilidad puntual del número máximo de detenciones por día, considerando lunes y martes.

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

**Paso 0, armar la tabla.** Se reemplaza x = 0, …, 4 en $\frac{16}{31}\left(\frac12\right)^x$:

| x | 0 | 1 | 2 | 3 | 4 |
|---|---|---|---|---|---|
| p(x) (·/31) | 16 | 8 | 4 | 2 | 1 |
| F(x) = P(X ≤ x) (·/31) | 16 | 24 | 28 | 30 | 31 |

F es la acumulada: se va sumando la fila de arriba.

**a)** "Se detiene" significa al menos una vez, X ≥ 1. Es lo contrario de X = 0:

$$1 - p(0) = 1 - \frac{16}{31} = \frac{15}{31}$$

**b)** Sea M = máx(lunes, martes). Contar directamente qué pares dan máximo 2 es engorroso. Hay un truco:

💡 "El máximo es ≤ k" equivale a "**los dos** son ≤ k". Como los días son independientes, se multiplica:

$`\displaystyle P(M \le k) = P(X_L \le k)\cdot P(X_M \le k) = F(k)^2`$

Y "el máximo es exactamente 2" es "M ≤ 2 pero no M ≤ 1":

$$P(M = 2) = F(2)^2 - F(1)^2 = \left(\frac{28}{31}\right)^2 - \left(\frac{24}{31}\right)^2 = \frac{784 - 576}{961} = \frac{208}{961}$$

**c)** Lo mismo para cada k: $P(M = k) = F(k)^2 - F(k-1)^2$, con F(−1) = 0.
- $P(M=0) = 16^2 = 256$
- $P(M=1) = 24^2 - 16^2 = 320$
- $P(M=2) = 208$
- $P(M=3) = 30^2 - 28^2 = 116$
- $P(M=4) = 31^2 - 30^2 = 61$

(Todo sobre 961.) Control: 256 + 320 + 208 + 116 + 61 = 961 ✓.

</details>

**Respuesta:**

- a) 15/31
- b) 208/961
- c) 256, 320, 208, 116, 61 (sobre 961)

</details>

---

### 11) Cajas de cambio ⭐

Un fabricante de automóviles tiene un programa de control de calidad que incluye la inspección de materiales recibidos para verificar que no tengan defectos. Supongamos que recibe las cajas de cambio para los automóviles en lotes de 5 unidades. Se seleccionan al azar dos cajas de un lote y se las inspecciona para decidir si son defectuosas o no.

- a) Describir el espacio muestral asociado a este experimento.
- b) Supongamos que el lote tiene dos cajas defectuosas y definamos la variable aleatoria W: "número de cajas defectuosas seleccionadas". Hallar las funciones de probabilidad y de distribución de la variable W.
- c) Hallar el valor esperado, el valor mediano y el valor más probable de la variable W.

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

**a)** Cada una de las 2 cajas elegidas se clasifica como B (buena) o D (defectuosa), en orden: {BB, BD, DB, DD}.

**b)** El lote tiene 5 cajas: 2 defectuosas y 3 buenas. Se eligen 2 a la vez, sin reposición. Todos los grupos de 2 son igual de probables, así que se cuentan grupos: $\binom52 = 10$ ($`\binom nk`$ es nCr).
- **W = 0** (las 2 buenas): $\binom32 = 3$ grupos, así que P = 3/10 = 0,3.
- **W = 1** (una de las 2 D y una de las 3 B): $\binom21\binom31 = 6$, así que P = 0,6.
- **W = 2** (las 2 D): $\binom22 = 1$, así que P = 0,1.

(Es la hipergeométrica de la U3, 📄 H1.)

💡 **Función de distribución** $F(w) = P(W \le w)$, acumulando: F(0) = 0,3; F(1) = 0,9; F(2) = 1. Es 0 para w < 0, se mantiene en cada escalón, y vale 1 desde w = 2.

**c)** Tres "centros" distintos:
- 💡 **Valor esperado** (📄 H1, $`\sum w\,p(w)`$): $0\cdot0{,}3 + 1\cdot0{,}6 + 2\cdot0{,}1 = 0{,}8$.
- 💡 **Mediana:** el valor que deja la mitad de la probabilidad a cada lado. En discretas es el **primer valor donde F llega a 0,5 o más** (❌). F(0) = 0,3 no llega y F(1) = 0,9 sí, así que la mediana es **1**.
- 💡 **Moda** (el más probable): el de mayor p, también **1**.

</details>

**Respuesta:**

- b) 0,3 / 0,6 / 0,1
- c) E = 0,8, mediana = moda = 1

</details>

---

### 12) Herramienta alquilada ⭐

La cantidad de veces por día que se usa en la fábrica una herramienta para reparar ciertos equipos puede modelarse mediante una variable que tiene la siguiente función de probabilidad:

$$P(x) = \frac{c}{x+1}, \quad \text{siendo el recorrido de la variable } R_X = \{0, 1, 2, 3\}$$

- a) Hallar el valor de la constante c.
- b) Si esta herramienta se alquila a 100 pesos cada vez que se usa, hallar el valor esperado del costo de alquiler mensual (20 días hábiles).

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

**a) Hallar c**

💡 En toda función de probabilidad, las probabilidades de todos los valores posibles suman 1 (X siempre vale algo). Esa condición da una ecuación para c:

$$P(0) + P(1) + P(2) + P(3) = \frac{c}{1} + \frac{c}{2} + \frac{c}{3} + \frac{c}{4} = 1$$

$$c\left(1 + \frac12 + \frac13 + \frac14\right) = c\cdot\frac{25}{12} = 1 \quad\Rightarrow\quad c = \frac{12}{25}$$

**b) Costo mensual esperado**

💡 **Valor esperado** E(X): el promedio de usos por día a la larga. Cada valor por su probabilidad, sumados (📄 H1, $`E(X) = \sum x_i P(x_i)`$):

$$E(X) = 0\cdot\frac{c}{1} + 1\cdot\frac{c}{2} + 2\cdot\frac{c}{3} + 3\cdot\frac{c}{4} = c\left(\frac12 + \frac23 + \frac34\right) = \frac{12}{25}\cdot\frac{23}{12} = 0{,}92$$

El costo de un mes es C = 100 · (usos del día 1 + … + usos del día 20).

💡 **Linealidad de la esperanza** (❌, no está en la hoja): la esperanza de una suma es la suma de las esperanzas, y las constantes salen afuera. Cada día aporta 0,92 usos esperados:

$$E(C) = 100\cdot20\cdot E(X) = 2000\cdot0{,}92 = 1840$$

</details>

**Respuesta:**

- a) c = 12/25
- b) 1840 pesos por mes

</details>

---

### 13) Stock de taladros ⏭️

La demanda semanal de taladros en cierto local comercial de la localidad de Arroyo Seco sigue la siguiente función de distribución de probabilidades:

| x | 0 | 1 | 2 | 3 | 4 |
|---|---|---|---|---|---|
| F(x) | 0,2 | 0,55 | 0,8 | 0,95 | 1 |

Cada taladro vendido origina una ganancia de 350 pesos, pero los que no se venden originan una pérdida de 80 pesos por unidad. ¿Cuántos taladros convendría disponer en stock para maximizar el beneficio semanal esperado?

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

**Paso 1, de F a las probabilidades de cada demanda.** La tabla da la acumulada $F(x) = P(D \le x)$. La probabilidad de cada valor es el **salto** entre escalones:
- P(0) = 0,2
- P(1) = 0,55 − 0,2 = 0,35
- P(2) = 0,25
- P(3) = 0,15
- P(4) = 0,05

**Paso 2, el beneficio para un stock s dado.** Si la demanda es D:
- se venden $\min(D, s)$ taladros, que ganan 350 cada uno;
- sobran $\max(s - D, 0)$, que pierden 80 cada uno.

Por ejemplo, con s = 2:
- si D = 0, sobran 2: −160;
- si D = 1, vende 1 y sobra 1: 350 − 80 = 270;
- si D ≥ 2, vende los 2: 700.

**Paso 3, beneficio esperado** para cada s. 💡 Es la esperanza de una función de D (📄 H1, $`E(g(D)) = \sum g(d)P(d)`$): cada beneficio posible por su probabilidad, sumados.
- s = 1: $0{,}2\cdot(-80) + 0{,}8\cdot350 = 264$.
- s = 2: $0{,}2\cdot(-160) + 0{,}35\cdot270 + 0{,}45\cdot700 = 377{,}5$.
- s = 3: $0{,}2\cdot(-240) + 0{,}35\cdot190 + 0{,}25\cdot620 + 0{,}2\cdot1050 = 383{,}5$.

| s | 0 | 1 | 2 | 3 | 4 |
|---|---|---|---|---|---|
| E(G) | 0 | 264 | 377,5 | **383,5** | 325 |

El máximo está en **s = 3**.

</details>

**Respuesta:** conviene tener **3** taladros (beneficio esperado ≈ 383,5 pesos).

</details>

---

### 14) ¿Funciones de densidad? ⭐

Indicar cuál o cuáles de las siguientes son funciones de densidad de probabilidad:

- a) f(x) = 3x² si 0 ≤ x ≤ 1, y f(x) = 0 en otro caso.
- b) f(x) = 3e^(−x/3) si x > 0, y f(x) = 0 en otro caso.
- c) f(x) = (2/3)(x − 1) si 0 ≤ x ≤ 3, y f(x) = 0 en otro caso.

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

💡 **Qué es una función de densidad.** Para una variable **continua** (que puede valer cualquier número de un intervalo), la probabilidad de un valor exacto es 0. Lo que tiene sentido es la probabilidad de un **intervalo**, y esa probabilidad es el **área bajo la curva f** en ese intervalo:

$$P(a < X < b) = \int_a^b f(x)\,dx$$

Para que f sea una densidad tiene que cumplir dos cosas:
1. **f(x) ≥ 0** en todos lados: un área negativa no tendría sentido;
2. **el área total es 1**: $\int_{-\infty}^{\infty} f(x)\,dx = 1$, porque X siempre cae en algún lado.

**a)** $3x^2 \ge 0$ ✓. El área: $\int_0^1 3x^2\,dx = x^3\Big|_0^1 = 1$ ✓. **Sí** es densidad.

**b)** $3e^{-x/3} > 0$ ✓. Pero el área:

$`\displaystyle \int_0^\infty 3e^{-x/3}\,dx = 3\cdot\left[-3e^{-x/3}\right]_0^\infty = 3\cdot(0 + 3) = 9 \neq 1`$

**No** es densidad. Le sobra un 3: con $\frac13 e^{-x/3}$ sí sería.

**c)** Para x entre 0 y 1, $x - 1 < 0$, así que $f(x) < 0$: **no** es densidad, aunque el área total dé 1. Comprobación: $\frac23\cdot\frac{(x-1)^2}{2}\Big|_0^3 = \frac23\cdot\frac{4 - 1}{2} = 1$.

</details>

**Respuesta:**

- a) sí
- b) no
- c) no

</details>

---

### 15) Porcentaje de fallas ⭐

El porcentaje de fallas de una producción industrial está dado por la variable aleatoria X, cuya función de densidad es:

$$f_X(x) = \begin{cases} a(x - x^3) & 0 < x \le 1 \\ 0 & \text{en otro caso} \end{cases}$$

- a) Hallar el valor de a.
- b) Hallar la función de distribución de probabilidades.
- c) Hallar el valor esperado y la varianza.

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

💡 **Densidad** (variable continua): la probabilidad de un intervalo es el **área bajo f** en ese intervalo. Por eso el área total tiene que dar 1.

**a)** Área total = 1:

$`\displaystyle \int_0^1 a(x - x^3)\,dx = a\left[\frac{x^2}{2} - \frac{x^4}{4}\right]_0^1 = a\left(\frac12 - \frac14\right) = \frac a4 = 1 \;\Rightarrow\; a = 4`$

Además $x - x^3 \ge 0$ en (0; 1], así que f ≥ 0 ✓.

**b)** 💡 **Función de distribución** $F(x) = P(X \le x)$: el área acumulada desde el comienzo hasta x (📄 H1, $`F(x) = \int_{-\infty}^x f(t)\,dt`$). Se arma por tramos:
- x ≤ 0: todavía no hay área, F = 0.
- 0 < x ≤ 1: $F(x) = \int_0^x (4t - 4t^3)\,dt = 2x^2 - x^4$.
- x > 1: ya se acumuló toda el área, F = 1.

Control: F(1) = 2 − 1 = 1 ✓.

**c)** En continuas, las fórmulas de las discretas cambian la suma por una integral (📄 H1, $E(X) = \int x\,f(x)\,dx$ y $`E(g(X)) = \int g(x)f(x)\,dx`$):

$`\displaystyle E(X) = \int_0^1 x\cdot4(x - x^3)\,dx = \int_0^1 (4x^2 - 4x^4)\,dx = \frac43 - \frac45 = \frac8{15}`$

$`\displaystyle E(X^2) = \int_0^1 x^2\cdot4(x - x^3)\,dx = \int_0^1 (4x^3 - 4x^5)\,dx = 1 - \frac23 = \frac13`$

$$V(X) = E(X^2) - E(X)^2 = \frac13 - \frac{64}{225} = \frac{11}{225}$$

(📄 H1, $V(X) = E(X^2) - (E(X))^2$.)

</details>

**Respuesta:**

- a) 4
- b) F = 2x² − x⁴
- c) E = 8/15, V = 11/225

</details>

---

### 16) Densidad con parámetro m ⭐

Sea

$$f(x) = \begin{cases} \dfrac{1}{72}(x+1)^2 & -1 \le x \le m \\ 0 & \text{en otro caso} \end{cases}$$

- a) Hallar el número real m > 0 para que f(x) sea la función de densidad de una variable aleatoria X.
- b) Hallar la función de distribución acumulada de X.
- c) Utilizando la función calculada, hallar P(−1 ≤ X < 3) y P(−1 < X < 3).
- d) Calcular el percentil 75 (tercer cuartil) de la variable.
- e) Calcular la función de densidad de la variable aleatoria Y = 2X + 1 y su valor mediano.
- f) Hallar el valor esperado de X y la varianza de Y.

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

**a)** 💡 En una densidad, el área total bajo f vale 1 (la probabilidad de que X caiga en algún lado). La incógnita es dónde termina el intervalo:

$`\displaystyle \int_{-1}^m \frac{(x+1)^2}{72}\,dx = \frac{(x+1)^3}{216}\Big|_{-1}^m = \frac{(m+1)^3}{216} = 1 \;\Rightarrow\; (m+1)^3 = 216 \;\Rightarrow\; m + 1 = 6 \;\Rightarrow\; m = 5`$

(Se integró con la sustitución u = x + 1: $\int u^2 = u^3/3$, y $3\cdot72 = 216$.)

**b)** 💡 $F(x) = P(X \le x)$ es el área acumulada hasta x (📄 H1, $`F(x) = \int_{-\infty}^x f`$):
- 0 si x < −1;
- $\frac{(x+1)^3}{216}$ en [−1; 5];
- 1 si x > 5.

**c)** 📄 H1: $P(a \le X \le b) = F(b) - F(a)$. Las dos dan $F(3) - F(-1) = \frac{64}{216} - 0 = \frac8{27}$.

💡 En una variable **continua** da igual poner < o ≤, porque la probabilidad de un punto exacto es 0 (no tiene área). Por eso los dos resultados coinciden.

**d)** 💡 **Percentil 75** (tercer cuartil): el valor que deja el 75 % del área a su izquierda, $F(x_{75}) = 0{,}75$ (❌, definición):

$$\frac{(x+1)^3}{216} = 0{,}75 \;\Rightarrow\; (x+1)^3 = 162 \;\Rightarrow\; x = \sqrt[3]{162} - 1 \approx 4{,}45$$

**e)** 💡 **Densidad de una transformación** (❌, método de la función de distribución): para conseguir $f_Y$ se pasa por $F_Y$, que sí se puede calcular con probabilidades de X.

$`\displaystyle F_Y(y) = P(Y \le y) = P(2X + 1 \le y) = P\left(X \le \frac{y-1}{2}\right) = F_X\left(\frac{y-1}{2}\right)`$

Se deriva con la regla de la cadena (❌, $`f = F'`$):

$`\displaystyle f_Y(y) = f_X\left(\frac{y-1}{2}\right)\cdot\frac12 = \frac12\cdot\frac{1}{72}\left(\frac{y-1}{2} + 1\right)^2 = \frac{(y+1)^2}{576}`$

El recorrido también se transforma: x ∈ [−1; 5] da y = 2x + 1 ∈ [−1; 11].

**Mediana de Y:** $F_Y(y) = 0{,}5$. Integrando, $F_Y(y) = \frac{(y+1)^3}{1728}$:

$$\frac{(y+1)^3}{1728} = \frac12 \;\Rightarrow\; y = \sqrt[3]{864} - 1 \approx 8{,}52$$

Atajo: la mediana de X cumple $(x+1)^3 = 108$, o sea $x = \sqrt[3]{108} - 1 \approx 3{,}76$. Como $y = 2x + 1$ es creciente, la mediana de Y es $2\cdot3{,}76 + 1 = 8{,}52$.

**f)** 📄 H1, $E(X) = \int x\,f(x)\,dx$. Con u = x + 1, u va de 0 a 6 y x = u − 1:

$$E(X) = \frac1{72}\int_0^6 (u - 1)u^2\,du = \frac1{72}\left(\frac{6^4}{4} - \frac{6^3}{3}\right) = \frac{324 - 72}{72} = 3{,}5$$

$$E(X^2) = \frac1{72}\int_0^6 (u-1)^2u^2\,du = 13{,}6 \;\Rightarrow\; V(X) = 13{,}6 - 3{,}5^2 = 1{,}35$$

Para Y = 2X + 1: $V(aX + b) = a^2V(X)$, porque el +1 no dispersa y el 2 sale al cuadrado (📄 H1 con la otra variable constante):

$$V(Y) = 4\cdot1{,}35 = 5{,}4$$

</details>

**Respuesta:**

- a) 5
- b) (x+1)³/216
- c) 8/27
- d) ∛162 − 1 ≈ 4,45
- e) (y+1)²/576 en [−1, 11], mediana ≈ 8,52
- f) E(X) = 3,5, V(Y) = 5,4

</details>

---

### 17) Densidad |x|

Sea X una variable aleatoria con densidad:

$$f_X(x) = \begin{cases} |x| & -5c \le x \le 5c \\ 0 & \text{en otro caso} \end{cases}$$

- a) Hallar el valor de la constante c de modo tal que resulte una función de densidad de probabilidad.
- b) Considerar los eventos A = {x / x > −1/2} y B = {x / x < 1/2} e indicar si se trata de eventos independientes.

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

**a)** 💡 El área total bajo una densidad tiene que ser 1. Además, |x| ≥ 0 siempre, así que f ≥ 0 ✓.

La función |x| es **simétrica** (tiene forma de V): el área de la izquierda es igual a la de la derecha. Se calcula la mitad derecha y se multiplica por 2:

$$2\int_0^{5c} x\,dx = 2\cdot\frac{(5c)^2}{2} = 25c^2 = 1 \;\Rightarrow\; c = \frac15$$

(Se toma c > 0 para que el intervalo tenga sentido.) X vive en [−1; 1].

**b)** 💡 Dos **eventos** son independientes si $P(A\cap B) = P(A)\,P(B)$ (📄 H1). Hay que calcular las tres probabilidades como áreas.
- **P(A) = P(X > −½).** Es más fácil por complemento. A la izquierda de 0, |x| = −x:

  $`\displaystyle P(X \le -\tfrac12) = \int_{-1}^{-1/2} (-x)\,dx = \left[-\frac{x^2}{2}\right]_{-1}^{-1/2} = -\frac18 + \frac12 = \frac38 \;\Rightarrow\; P(A) = \frac58`$

- **P(B) = P(X < ½)**: por simetría también vale $\frac58$.
- **A ∩ B** = "−½ < X < ½": $2\int_0^{1/2} x\,dx = 2\cdot\frac18 = \frac14$.

Comparando: $P(A)P(B) = \frac{25}{64} \approx 0{,}39 \neq \frac14$. **No son independientes.**

</details>

**Respuesta:**

- a) c = 1/5
- b) No.

</details>

---

### 18) Componentes eléctricos ⭐

Una empresa fabrica componentes eléctricos cuya duración (en años) está dada por una variable aleatoria T, cuya función de densidad es:

$$f_T(t) = \begin{cases} 1 & 0 \le t < \tfrac12 \\ \tfrac12 e^{-(t - \frac12)} & t > \tfrac12 \\ 0 & \text{en otro caso} \end{cases}$$

- a) Hallar la función de distribución acumulada F_T.
- b) El producto se considera *regular* si dura menos de tres meses, *bueno* si dura entre tres meses y tres años y *muy bueno* si dura más de tres años. Calcular los porcentajes de componentes regulares, buenos y muy buenos de la producción.
- c) Se empaquetan los componentes en cajas de 20 unidades. Si un comprador encuentra en una caja 1 o más artículos regulares, la fábrica le proporciona una caja nueva en forma gratuita. Cierto usuario adquirió una caja: ¿cuál es la probabilidad de obtener otra de regalo?

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

**a)** 💡 $F(t) = P(T \le t)$ es el área acumulada bajo f hasta t (📄 H1, $`F(t) = \int_{-\infty}^t f`$). Como f tiene dos tramos, F también:
- **t < 0:** no hay área, F = 0.
- **0 ≤ t < ½:** f vale 1, así que el área es un rectángulo de base t y altura 1: F(t) = t. En t = ½ se acumuló ½.
- **t ≥ ½:** lo acumulado hasta ½ más lo que se agrega después:

  $`\displaystyle F(t) = \frac12 + \int_{1/2}^t \frac12 e^{-(s - 1/2)}\,ds = \frac12 + \frac12\left[-e^{-(s-1/2)}\right]_{1/2}^t = \frac12 + \frac12\left(1 - e^{-(t-1/2)}\right) = 1 - \frac12 e^{-(t - 1/2)}`$

  Cuando t → ∞, F → 1 ✓.

**b)** Las unidades están en **años**: 3 meses = 0,25 año.
- **Regular** (menos de 0,25): F(0,25) = 0,25, así que **25 %**.
- **Muy bueno** (más de 3 años), 📄 H1 $P(T > a) = 1 - F(a)$:

  $$1 - F(3) = \frac12 e^{-2{,}5} \approx 0{,}041 \;\Rightarrow\; \text{≈ 4,1 \%}$$

- **Bueno** (entre los dos): lo que queda, $1 - 0{,}25 - 0{,}041 \approx 0{,}709$, es decir **70,9 %**.

**c)** Cada componente de la caja es "regular" (éxito) con p = 0,25, y los 20 son independientes. Entonces la cantidad de regulares es una **binomial** Bin(20; 0,25) (U3, 📄 H1).

"Al menos uno regular" se hace por complemento:

$$1 - P(\text{ninguno}) = 1 - 0{,}75^{20} \approx 0{,}9968$$

```
X~Bin(n,p)   n=20   p=0.25   P(X≥x)   x=1   → 0.99683
```

</details>

**Respuesta:**

- a) F = t en [0, ½); 1 − ½e^{−(t−½)} para t ≥ ½
- b) 25 %; ≈ 70,9 %; ≈ 4,1 %
- c) ≈ 0,9968

</details>

---

### 19) Densidad triangular

Sea X una variable aleatoria con función de densidad f(x) = ½·(3 − x) para 1 ≤ x ≤ 3, y 0 en caso contrario.

- a) Hallar la función de distribución acumulada y graficarla.
- b) Determinar r sabiendo que P(X < r) = 2·P(X > r).
- c) Calcular P(X ≤ 5/2 / 2 ≤ X ≤ 7/2).

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

**a)** 💡 $F(x) = P(X \le x)$, el área bajo f hasta x (📄 H1). En [1; 3]:

$`\displaystyle F(x) = \int_1^x \frac{3 - t}{2}\,dt = \left[\frac32t - \frac{t^2}{4}\right]_1^x = \frac32x - \frac14x^2 - \frac54`$

Vale 0 si x < 1 y 1 si x > 3. Control: $F(3) = 4{,}5 - 2{,}25 - 1{,}25 = 1$ ✓.

El gráfico es una curva creciente, cóncava hacia abajo (sube rápido al principio porque f es más alta cerca de 1), que va de (1; 0) a (3; 1).

**b)** Se traducen las dos probabilidades con F: P(X < r) = F(r) y P(X > r) = 1 − F(r) (📄 H1):

$$F(r) = 2(1 - F(r)) \;\Rightarrow\; 3F(r) = 2 \;\Rightarrow\; F(r) = \frac23$$

Se iguala la fórmula de F a 2/3 y se pasa todo a un lado, multiplicando por 12:

$$\frac32r - \frac14r^2 - \frac54 = \frac23 \;\Rightarrow\; 3r^2 - 18r + 23 = 0 \;\Rightarrow\; r = \frac{18 \pm \sqrt{324 - 276}}{6} = 3 \pm \frac{\sqrt{48}}{6}$$

La raíz con + da 4,15, fuera de [1; 3]. Queda $r = 3 - \frac{\sqrt{48}}{6} \approx 1{,}845$.

**c)** 💡 Condicional (📄 H1, $`P(A/B) = \frac{P(A\cap B)}{P(B)}`$). X nunca pasa de 3, así que la condición "2 ≤ X ≤ 7/2" es en la práctica "2 ≤ X ≤ 3". La intersección con "X ≤ 5/2" es "2 ≤ X ≤ 2,5":

$$\frac{F(2{,}5) - F(2)}{F(3) - F(2)} = \frac{0{,}9375 - 0{,}75}{1 - 0{,}75} = \frac{0{,}1875}{0{,}25} = \frac34$$

</details>

**Respuesta:**

- a) ver arriba
- b) r ≈ 1,845
- c) 3/4

</details>

---

### 20) Densidad trapezoidal

Sea X una variable aleatoria con función de densidad definida por:

$$f(x) = \begin{cases} ax & 0 \le x < 1 \\ a & 1 \le x < 2 \\ -ax + 3a & 2 \le x < 3 \\ 0 & \text{en otro caso} \end{cases}$$

- a) Determinar la constante a.
- b) Hallar la función de distribución acumulada de X y graficarla.

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

**a)** 💡 El área total bajo una densidad es 1. Si se dibuja f, es un **trapecio**:
- sube en línea recta de 0 a a (entre 0 y 1);
- se mantiene en a (entre 1 y 2);
- baja de a a 0 (entre 2 y 3).

No hace falta integrar: se suman áreas de figuras.

$`\displaystyle \underbrace{\frac{1\cdot a}{2}}_{\text{triángulo}} + \underbrace{1\cdot a}_{\text{rectángulo}} + \underbrace{\frac{1\cdot a}{2}}_{\text{triángulo}} = 2a = 1 \;\Rightarrow\; a = \frac12`$

**b)** 💡 $F(x)$ = área acumulada hasta x (📄 H1). Por tramos, **arrastrando** lo acumulado en los tramos anteriores:
- **[0; 1):** $\int_0^x \frac t2\,dt = \frac{x^2}{4}$. En x = 1 vale ¼.
- **[1; 2):** ¼ más el rectángulo de altura ½ y base (x − 1): $\frac14 + \frac12(x - 1)$. En x = 2 vale ¾.
- **[2; 3):** ¾ más $\int_2^x \frac{3 - t}{2}\,dt$, que simplifica a $\frac32x - \frac14x^2 - \frac54$. En x = 3 vale 1 ✓.
- **x ≥ 3:** 1. Y antes de 0, F = 0.

El gráfico es una S suave: una parábola, después una recta y después otra parábola, sin saltos.

</details>

**Respuesta:**

- a) ½
- b) la F de arriba

</details>

---

### 21) Transformaciones de una uniforme

Sea X una variable aleatoria con función de densidad definida por f(x) = 1 para 0 < x < 1, y 0 en caso contrario. Calcular las funciones de densidad de las variables aleatorias Y = ln(X) y Z = 3X + 4.

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

💡 **Método de la función de distribución** (❌, no está en la hoja). Para encontrar la densidad de una variable nueva Y = g(X):
1. Se escribe $F_Y(y) = P(Y \le y)$.
2. Se despeja X adentro de la probabilidad, para que quede una probabilidad sobre X, que se sabe calcular.
3. Se deriva: $f_Y = F_Y'$.

Acá X es uniforme en (0; 1): f = 1, así que $P(X \le t) = t$ para t entre 0 y 1.

**Y = ln X.**
- Recorrido: si X está entre 0 y 1, su logaritmo es negativo. Y va de −∞ a 0.
- $F_Y(y) = P(\ln X \le y) = P(X \le e^y) = e^y$. Se despejó con la exponencial, que es creciente y no da vuelta la desigualdad.
- Derivando: $f_Y(y) = e^y$ para y < 0.

Control: $\int_{-\infty}^0 e^y\,dy = 1$ ✓.

**Z = 3X + 4.**
- Recorrido: X ∈ (0; 1) da Z ∈ (4; 7).
- $F_Z(z) = P(3X + 4 \le z) = P\left(X \le \frac{z-4}{3}\right) = \frac{z-4}{3}$.
- Derivando: $f_Z(z) = \frac13$ en (4; 7).

Es otra uniforme: estirar y correr una uniforme da una uniforme.

</details>

**Respuesta:** $f_Y(y) = e^y$ para y < 0; $f_Z(z) = 1/3$ en [4, 7].

</details>

---

### 22) Probabilidad condicional con parámetro

Sea X una variable aleatoria con función de densidad dada por f(x) = 3x² para −1 ≤ x ≤ 0, y 0 en caso contrario. Sea b un número real tal que −1 < b < 0. Calcular P(X > b / X < b/2).

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

**Paso 1, la función de distribución.** 💡 $F(x) = P(X \le x)$, el área acumulada (📄 H1). En [−1; 0]:

$`\displaystyle F(x) = \int_{-1}^x 3t^2\,dt = t^3\Big|_{-1}^x = x^3 + 1`$

**Paso 2, ubicar los números.** b es negativo, y la mitad de un negativo está **más cerca de 0**, así que es más grande. Por ejemplo, con b = −0,6, b/2 = −0,3. Entonces b < b/2.

**Paso 3, la condicional** (📄 H1, $`P(A/B) = \frac{P(A\cap B)}{P(B)}`$). "X > b y X < b/2" es el intervalo (b; b/2):

$$P(X > b / X < b/2) = \frac{P(b < X < b/2)}{P(X < b/2)} = \frac{F(b/2) - F(b)}{F(b/2)}$$

Reemplazando con $F(x) = x^3 + 1$:

$$= \frac{\left(\frac{b^3}{8} + 1\right) - (b^3 + 1)}{\frac{b^3}{8} + 1} = \frac{\frac{b^3}{8} - b^3}{\frac{b^3 + 8}{8}} = \frac{-7b^3}{b^3 + 8}$$

Como b < 0, $-7b^3 > 0$, así que el resultado es positivo ✓.

</details>

**Respuesta:** $\dfrac{-7b^3}{b^3 + 8}$

</details>

---

### 23) Costo de un proceso ⭐

El tiempo que tarda un proceso electrónico es una variable aleatoria con media 2 hs y varianza 0,5 hs². El costo del proceso es de 3 pesos por hora más un costo fijo de 8 pesos. Hallar el costo esperado y su varianza.

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

**Traducción:** si T es el tiempo en horas, el costo es C = 3T + 8 (3 pesos por hora más 8 fijos). Es una **transformación lineal** de T.

No hace falta conocer la distribución de T: alcanza con su media y su varianza, gracias a dos propiedades.
- **Esperanza** (❌, linealidad): $E(aT + b) = aE(T) + b$.

  $$E(C) = 3\cdot2 + 8 = 14 \text{ pesos}$$

- **Varianza:** $V(aT + b) = a^2V(T)$. El costo fijo 8 se suma igual a todos y no dispersa; el 3 multiplica la dispersión, y en la varianza aparece al cuadrado. Sale de 📄 H1, $V(aX + bY) = a^2V(X) + b^2V(Y) + \dots$, con la segunda variable constante.

  $$V(C) = 3^2\cdot0{,}5 = 4{,}5 \text{ pesos}^2$$

</details>

**Respuesta:** E(C) = 14 pesos, V(C) = 9/2

</details>

---

### 24) Demanda de combustible

La función de distribución de la demanda de combustible X, en miles de litros por día, en cierta boca de expendio es:

$$F(x) = \begin{cases} 0 & x < 0 \\ bx^2 & 0 \le x < 1 \\ b\,[2(x-1)+1] & 1 \le x < 3 \\ 1 - b(x-4)^2 & 3 \le x < 4 \\ 1 & x \ge 4 \end{cases}$$

- a) Hallar la función de densidad de la demanda de combustible.
- b) Hallar la demanda superada sólo el 20 % de los días.

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

**Paso 0, hallar b.** 💡 La función de distribución de una variable continua **no tiene saltos**: cada tramo tiene que empalmar con el siguiente. En x = 3, el tramo del medio y el de la derecha tienen que dar lo mismo:

$`\displaystyle \underbrace{b[2(3-1) + 1]}_{\text{tramo medio en }3} = \underbrace{1 - b(3-4)^2}_{\text{tramo derecho en }3} \;\Rightarrow\; 5b = 1 - b \;\Rightarrow\; b = \frac16`$

(En x = 1 empalman solos: $b\cdot1 = b[0 + 1]$.)

**a)** 💡 La densidad es la **derivada** de la distribución (❌, $f = F'$; la hoja trae solo el camino inverso, $`F = \int f`$). Se deriva cada tramo con b = 1/6:
- $\left(\frac{x^2}{6}\right)' = \frac x3$ en [0; 1);
- $\left(\frac{2(x-1) + 1}{6}\right)' = \frac13$ en [1; 3);
- $\left(1 - \frac{(x-4)^2}{6}\right)' = -\frac{2(x-4)}{6} = \frac{4 - x}{3}$ en [3; 4);
- 0 en el resto.

**b)** "Superada solo el 20 % de los días" significa que el 80 % de los días la demanda es menor: se busca x con **F(x) = 0,8** (es el percentil 80).

¿En qué tramo está? F(1) = 1/6 ≈ 0,17 y F(3) = 5/6 ≈ 0,83. Como 0,8 está entre los dos, x está en el tramo [1; 3):

$$\frac16(2x - 1) = 0{,}8 \;\Rightarrow\; 2x - 1 = 4{,}8 \;\Rightarrow\; x = 2{,}9 \text{ miles de litros}$$

</details>

**Respuesta:**

- a) f = x/3, 1/3, (4 − x)/3
- b) 2,9 miles de litros

</details>

---

### 25) Región circular de muestreo

Un ecologista desea marcar una región circular de muestreo de 10 m de radio; sin embargo, el radio de la región resultante es una variable aleatoria cuya función de densidad está dada por:

$$f(r) = \begin{cases} \tfrac34\left[1 - (10 - r)^2\right] & 9 \le r < 11 \\ 0 & \text{en otro caso} \end{cases}$$

- a) Hallar la probabilidad de que el radio difiera del deseado por el ecologista en a lo sumo 30 cm.
- b) ¿Cuál es el área esperada de la región resultante?

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

**Simplificar primero.** Se llama u = r − 10, cuánto se aparta el radio de los 10 m deseados. Entonces r = 10 + u, u va de −1 a 1, y la densidad queda $\frac34(1 - u^2)$. Es simétrica alrededor de u = 0.

**a)** "Difiere en a lo sumo 30 cm" significa $|r - 10| \le 0{,}3$, es decir u entre −0,3 y 0,3. 💡 La probabilidad es el área bajo la densidad:

$`\displaystyle \int_{-0{,}3}^{0{,}3} \frac34(1 - u^2)\,du = \frac34\left[u - \frac{u^3}{3}\right]_{-0{,}3}^{0{,}3} = \frac34(0{,}6 - 0{,}018) = 0{,}4365`$

**b)** El área del círculo es $A = \pi R^2$, una **función** de R. 💡 Su esperanza se calcula con 📄 H1, $E(g(X)) = \int g(x)f(x)\,dx$. Hay un atajo: se desarrolla el cuadrado y se usa la linealidad (❌):

$$E(\pi R^2) = \pi E[(10 + u)^2] = \pi\left(100 + 20E(u) + E(u^2)\right)$$

- $E(u) = 0$, porque la densidad es simétrica alrededor de 0.
- $E(u^2) = \int_{-1}^1 u^2\cdot\frac34(1 - u^2)\,du = \frac34\left(\frac23 - \frac25\right) = \frac15$.

$$E(A) = \pi(100 + 0 + 0{,}2) = 100{,}2\pi \approx 314{,}8 \text{ m}^2$$

⚠️ **No** es π·10² = 100π: en general $E(R^2) \ne E(R)^2$. La diferencia es justamente la varianza de R, 0,2.

</details>

**Respuesta:**

- a) 0,4365
- b) 100,2π ≈ 314,8 m² (la guía da 100π, porque desprecia el término E(u²) = 0,2).

</details>

---

### 26) Pacientes regulares y de urgencia ⭐

Cierto laboratorio atiende análisis clínicos regulares y de urgencia. Sea X₁ el número de pacientes que se atienden por un análisis regular en un momento particular del día, y X₂ el número de pacientes que demandan atención de urgencia en ese mismo momento. La función de probabilidad conjunta de X₁ y X₂ está dada por:

| X₁ ↓ \ X₂ → | 0 | 1 | 2 |
|---|---|---|---|
| 0 | 0,08 | 0,07 | 0,04 |
| 1 | 0,06 | 0,15 | 0,09 |
| 2 | 0,05 | 0,04 | 0,16 |
| 3 | 0 | 0,14 | 0,12 |

- a) Hallar la probabilidad de que el número de pacientes regulares sea igual al número de pacientes de urgencia.
- b) Hallar la probabilidad de que haya exactamente dos pacientes de urgencia.
- c) Hallar la probabilidad de que haya dos pacientes de urgencia y al menos uno regular.
- d) Hallar las funciones de probabilidad marginales de X₁ y X₂. ¿Son estas variables independientes? Justificar la respuesta.

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

💡 **Función de probabilidad conjunta.** Cuando hay **dos** variables a la vez, la tabla da la probabilidad de cada **par**: la celda (fila x₁, columna x₂) es $P(X_1 = x_1 \text{ y } X_2 = x_2)$. Todas las celdas suman 1. Cualquier probabilidad se calcula **sumando las celdas que cumplen la condición**.

**a) X₁ = X₂:** las celdas donde coinciden son (0,0), (1,1) y (2,2), la diagonal: $0{,}08 + 0{,}15 + 0{,}16 = 0{,}39$. (No hay X₂ = 3.)

**b) X₂ = 2:** toda la columna 2, sin importar X₁: $0{,}04 + 0{,}09 + 0{,}16 + 0{,}12 = 0{,}41$.

**c) X₂ = 2 y X₁ ≥ 1:** la columna 2 sin la fila 0: $0{,}09 + 0{,}16 + 0{,}12 = 0{,}37$.

**d)** 💡 **Marginales:** la distribución de **una sola** variable se obtiene sumando la conjunta por filas o por columnas (📄 H1, $`P_X(x) = \sum_y P(x;y)`$).
- X₁ (sumando cada fila): 0,19 / 0,30 / 0,25 / 0,26 para 0, 1, 2, 3.
- X₂ (sumando cada columna): 0,19 / 0,40 / 0,41 para 0, 1, 2.

💡 **Independencia de variables** (📄 H1): X₁ y X₂ son independientes si y solo si $P(x_1, x_2) = P_{X_1}(x_1)\cdot P_{X_2}(x_2)$ para **todas** las celdas. Para probar que **no** lo son, alcanza con una celda que falle:

$`\displaystyle P(1, 1) = 0{,}15 \neq P_{X_1}(1)\,P_{X_2}(1) = 0{,}30\cdot0{,}40 = 0{,}12`$

**No son independientes.** Otra forma de verlo: P(3, 0) = 0, pero el producto de marginales no es 0.

</details>

**Respuesta:**

- a) 0,39
- b) 0,41
- c) 0,37
- d) no son independientes

</details>

---

### 27) Conjunta c(x + y) ⭐

Siendo la función de probabilidad conjunta

$$f(x; y) = \begin{cases} c\,(x + y) & x, y \in \{1, 2, 3\} \\ 0 & \text{en otro caso} \end{cases}$$

hallar:

- a) El valor de c para que f(x; y) resulte una función de probabilidad conjunta.
- b) P(X = 1 ∧ Y < 4), P(Y = 1) y P(X < 2 / Y < 2).
- c) Cov(X; Y) y ρ(X; Y).

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

**Armar la tabla** ayuda mucho. Cada celda es c·(x + y):

| X \ Y | 1 | 2 | 3 | Marginal X |
|---|---|---|---|---|
| 1 | 2c | 3c | 4c | 9c |
| 2 | 3c | 4c | 5c | 12c |
| 3 | 4c | 5c | 6c | 15c |
| Marginal Y | 9c | 12c | 15c | 36c |

**a)** 💡 En una conjunta, todas las celdas suman 1: $36c = 1$, así que $c = \frac1{36}$.

**b)**
- **P(X = 1 y Y < 4):** Y vale siempre 1, 2 o 3, así que "Y < 4" siempre se cumple. Es P(X = 1), la fila 1: $\frac{2 + 3 + 4}{36} = \frac9{36} = 0{,}25$.
- **P(Y = 1):** la columna 1, también $\frac{9}{36} = 0{,}25$ (la tabla es simétrica).
- **P(X < 2 / Y < 2):** X < 2 es X = 1, y Y < 2 es Y = 1. 💡 Condicional (📄 H1, $`P(x/y) = \frac{P(x,y)}{P_Y(y)}`$):

  $$P(X = 1/Y = 1) = \frac{P(1,1)}{P_Y(1)} = \frac{2/36}{9/36} = \frac29$$

**c)** 💡 **Covarianza** (📄 H1, $`Cov(X,Y) = E(XY) - E(X)E(Y)`$): mide si X e Y tienden a moverse juntas. Es positiva si cuando una es grande la otra también, y negativa si van al revés.
- Con la marginal de X: $E(X) = \frac{1\cdot9 + 2\cdot12 + 3\cdot15}{36} = \frac{78}{36} = \frac{13}{6}$. Igual E(Y).
- $E(XY) = \sum x\,y\,P(x,y)$, sumando sobre las 9 celdas: $\frac{1\cdot2 + 2\cdot3 + 3\cdot4 + 2\cdot3 + 4\cdot4 + 6\cdot5 + 3\cdot4 + 6\cdot5 + 9\cdot6}{36} = \frac{168}{36} = \frac{14}{3}$.
- $Cov = \frac{14}{3} - \left(\frac{13}{6}\right)^2 = \frac{168}{36} - \frac{169}{36} = -\frac1{36}$.

💡 **Coeficiente de correlación** (📄 H1, $`\rho = \frac{Cov}{\sigma_X\sigma_Y}`$): es la covarianza "estandarizada", y va de −1 a 1.
- $E(X^2) = \frac{1\cdot9 + 4\cdot12 + 9\cdot15}{36} = \frac{192}{36} = \frac{16}{3}$.
- $V(X) = \frac{16}{3} - \frac{169}{36} = \frac{23}{36}$, igual que V(Y).

$$\rho = \frac{-1/36}{\sqrt{23/36}\cdot\sqrt{23/36}} = \frac{-1/36}{23/36} = -\frac1{23} \approx -0{,}043$$

Es prácticamente 0: casi no hay relación lineal.

</details>

**Respuesta:**

- a) 1/36
- b) 0,25; 0,25; 2/9
- c) Cov = −1/36, ρ = −1/23

</details>

---

### 28) Cartuchos de bolígrafo ⭐

Se seleccionan al azar dos cartuchos de bolígrafo de una caja que contiene tres azules, dos rojos y tres verdes. Si X: "número de cartuchos azules elegidos" e Y: "número de cartuchos rojos seleccionados", calcular:

- a) La función de probabilidad conjunta p(x, y).
- b) P(A), siendo A = {(x; y) / x + y ≤ 1}.
- c) P(X = 0 / Y = 1) y P(Y = 1 / X = 0).

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

**a)** 💡 La **conjunta** p(x, y) da la probabilidad de cada par "x azules y y rojos". Se eligen 2 cartuchos de 8 sin importar el orden, con todos los pares igual de probables: $\binom82 = 28$ casos posibles.

Para cada celda se cuenta: x de los 3 azules, y de los 2 rojos, y el resto (2 − x − y) de los 3 verdes. Por ejemplo:
- (1, 0): 1 azul y 1 verde, $\binom31\binom31 = 9$;
- (0, 1): 1 rojo y 1 verde, $2\cdot3 = 6$;
- (1, 1): 1 azul y 1 rojo, $3\cdot2 = 6$;
- (0, 0): 2 verdes, $\binom32 = 3$.

Los pares con x + y > 2 son imposibles, porque solo se sacan 2.

| p | Y=0 | Y=1 | Y=2 |
|---|---|---|---|
| X=0 | 3/28 | 6/28 | 1/28 |
| X=1 | 9/28 | 6/28 | 0 |
| X=2 | 3/28 | 0 | 0 |

Control: todas suman 28/28 ✓.

**b)** Se suman las celdas que cumplen x + y ≤ 1, que son (0,0), (1,0) y (0,1):

$$\frac{3 + 9 + 6}{28} = \frac{18}{28} = \frac9{14}$$

**c)** 💡 Condicionales con la conjunta (📄 H1, $`P(x/y) = \frac{P(x,y)}{P_Y(y)}`$). Hacen falta las **marginales**, que se obtienen sumando una fila o una columna:
- $P_Y(1)$ = columna Y = 1: $\frac{6 + 6}{28} = \frac{12}{28}$.
- $P_X(0)$ = fila X = 0: $\frac{3 + 6 + 1}{28} = \frac{10}{28}$.

$$P(X = 0/Y = 1) = \frac{6/28}{12/28} = 0{,}5 \qquad P(Y = 1/X = 0) = \frac{6/28}{10/28} = 0{,}6$$

Tienen el mismo numerador, pero distinto universo (el denominador).

</details>

**Respuesta:**

- b) 9/14
- c) 0,5 y 0,6

</details>

---

### 29) Covarianza nula sin independencia

Considerando la función de probabilidad conjunta de (X, Y) dada por la siguiente tabla:

| X ↓ \ Y → | −1 | 0 | 1 |
|---|---|---|---|
| −1 | b | c | b |
| 0 | c | 0 | c |
| 1 | b | c | b |

Sabiendo que b + c = 0,25, demostrar que E(XY) = E(X)·E(Y). ¿Son independientes las variables X e Y? ¿Cuánto vale el coeficiente de correlación lineal?

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

**Marginales** (📄 H1, sumando filas y columnas): $P_X(-1) = 2b + c$, $P_X(0) = 2c$ y $P_X(1) = 2b + c$. Lo mismo para Y.

**E(X) y E(Y).** Los valores −1 y 1 tienen la misma probabilidad, así que se compensan: $E(X) = -1\cdot(2b + c) + 0 + 1\cdot(2b + c) = 0$. Lo mismo para Y.

**E(XY).** Se multiplica x·y en cada celda por su probabilidad:
- las celdas con x = 0 o y = 0 dan producto 0;
- quedan las cuatro esquinas: (−1)(−1)b + (−1)(1)b + (1)(−1)b + (1)(1)b = b − b − b + b = 0.

Entonces $E(XY) = 0 = E(X)E(Y)$ ✓.

💡 **Covarianza** (📄 H1): $Cov = E(XY) - E(X)E(Y) = 0$. Y el coeficiente de correlación $\rho = \frac{Cov}{\sigma_X\sigma_Y} = 0$.

**¿Independientes?** 💡 Tendrían que cumplir $P(x,y) = P_X(x)P_Y(y)$ en **todas** las celdas (📄 H1). Pero en el centro:

$`\displaystyle P(0, 0) = 0 \neq P_X(0)P_Y(0) = (2c)^2 > 0 \quad(\text{si } c > 0)`$

**No son independientes.**

**La moraleja:** si son independientes, la covarianza es 0. Pero la **vuelta no vale**: covarianza 0 solo dice que no hay relación **lineal**. Acá hay relación: si X = 0, seguro Y ≠ 0.

</details>

**Respuesta:** Cov = 0 y ρ = 0, pero no son independientes (covarianza nula no implica independencia).

</details>

---

### 30) Propiedades con dos variables ⭐

Supongamos que X₁ y X₂ son variables aleatorias de las que se sabe que:

E(X₁) = 1, E(X₂) = −2, V(X₁) = 4, V(X₂) = 9 y ρ(X₁; X₂) = √6 / 3.

Hallar:

- a) E(3X₁ − 2X₂)
- b) V(3X₁)
- c) Cov(X₁; X₂)
- d) V(X₁ + X₂)
- e) V(2X₁ − 3X₂)

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

Se resuelve **solo con propiedades**, sin conocer las distribuciones. Los desvíos son $\sigma_1 = \sqrt4 = 2$ y $\sigma_2 = \sqrt9 = 3$.

**a)** Linealidad de la esperanza (❌): $E(aX_1 + bX_2) = aE(X_1) + bE(X_2)$.

$`\displaystyle E(3X_1 - 2X_2) = 3\cdot1 - 2\cdot(-2) = 7`$

**b)** Al multiplicar por una constante, la varianza se multiplica por la constante **al cuadrado** (📄 H1, $V(aX + bY)$ con b = 0):

$$V(3X_1) = 3^2\cdot4 = 36$$

**c)** 💡 Del coeficiente de correlación (📄 H1, $`\rho = \frac{Cov}{\sigma_1\sigma_2}`$) se despeja la covarianza:

$`\displaystyle Cov = \rho\,\sigma_1\sigma_2 = \frac{\sqrt6}{3}\cdot2\cdot3 = 2\sqrt6 \approx 4{,}9`$

**d)** 💡 Las variables **no** son independientes (ρ ≠ 0), así que la varianza de la suma lleva el término de covarianza (📄 H1, $`V(X+Y) = V(X) + V(Y) + 2Cov`$):

$`\displaystyle V(X_1 + X_2) = 4 + 9 + 2\cdot2\sqrt6 = 13 + 4\sqrt6 \approx 22{,}8`$

**e)** 📄 H1: $V(aX + bY) = a^2V(X) + b^2V(Y) + 2ab\,Cov$, con a = 2 y b = −3. Ojo con el signo: 2ab = 2·2·(−3) = −12.

$`\displaystyle V(2X_1 - 3X_2) = 4\cdot4 + 9\cdot9 - 12\cdot2\sqrt6 = 97 - 24\sqrt6 \approx 38{,}2`$

</details>

**Respuesta:**

- a) 7
- b) 36
- c) 2√6
- d) 13 + 4√6
- e) 97 − 24√6

</details>

---

[← Volver al menú principal](../README.md)
