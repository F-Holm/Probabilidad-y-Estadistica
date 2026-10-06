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

Una v.a. es **discreta** si su recorrido es finito o infinito numerable (se puede "contar"), y **continua** si es un intervalo (infinito no numerable).

- a) De 0 a 20 ausentes → finito → discreta.
- b) Un tiempo puede tomar cualquier valor de un intervalo → continua (la guía usa [0; 300] min).
- c) Es un par (máx, mín) con −10° ≤ mín ≤ máx ≤ 40° → v.a. bidimensional continua.
- d) De 0 a 120 → discreta.
- e) Hacen falta como mínimo 3 hijos (MMM) y como máximo 8 → {3, …, 8} → discreta.
- f) De 0 a 12 → discreta.
- g) Sumas posibles con 3 monedas: 0,25·3 = 0,75; 0,25+0,25+0,5 = 1; 0,25+0,5+0,5 = 1,25; 0,25+0,25+1 = 1,5; 0,5+0,25+1 = 1,75; 0,5+0,5+1 = 2; 0,25+1+1 = 2,25; 0,5+1+1 = 2,5; 1+1+1 = 3 → discreta.
- h) Entre 0 y 32 libras → continua.
- i) Como mínimo 2 tiradas, sin tope → {2, 3, 4, …} → discreta infinita numerable.
- j) Permutaciones de 4 ruedas: pueden quedar 0, 1, 2 o 4 en su lugar (si 3 están bien, la cuarta también lo está) → discreta.

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

- a) Entre 0 y 5 + 3 + 2 = 10.
- b) B va de 0 a 3 y C de 0 a 2: pares.
- c) Cualquiera de las 3 estaciones puede tener exactamente 2 en uso (A tiene 5, B tiene 3 y C tiene 2) → 0 a 3.
- d) $x_A - x_B$, con $x_A \in [0,5]$ y $x_B \in [0,3]$ → de 0 − 3 = −3 a 5 − 0 = 5.

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

Casos posibles: $\binom83 = 56$. Como hay sólo 2 rojas, X ≥ 1.
- $P(1) = \binom61\binom22/56 = 6/56 = 3/28$
- $P(2) = \binom62\binom21/56 = 30/56 = 15/28$
- $P(3) = \binom63/56 = 20/56 = 5/14$

b) $E(X) = \frac{1\cdot6 + 2\cdot30 + 3\cdot20}{56} = \frac{126}{56} = \frac94$.

$E(X^2) = \frac{6 + 120 + 180}{56} = \frac{153}{28}$ ⇒ $V(X) = \frac{153}{28} - \frac{81}{16} = \frac{45}{112}$.

c) Con $E(g(X)) = \sum g(x)P(x)$:
- $E(1/X) = \frac{6 + 30/2 + 20/3}{56} = \frac{83}{168} \approx 0{,}494$
- $E(1/X^2) = \frac{6 + 30/4 + 20/9}{56} \approx 0{,}2808$
- $E(X^4) = \frac{6 + 30\cdot16 + 20\cdot81}{56} = \frac{2106}{56}$ ⇒ $V(X^2) = E(X^4) - E(X^2)^2 \approx 37{,}607 - 29{,}858 = 7{,}749$

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

Se condiciona según el color que se pasó:
- Pasa roja (0,6) → B queda con 3R y 7B.
- Pasa blanca (0,4) → B queda con 2R y 8B.

**a) Con reposición** (binomial con n = 2):
- Si pasó roja (p = 0,3): 0,49 / 0,42 / 0,09.
- Si pasó blanca (p = 0,2): 0,64 / 0,32 / 0,04.

Probabilidad total:
- $P(0) = 0{,}6\cdot0{,}49 + 0{,}4\cdot0{,}64 = 0{,}55$
- $P(1) = 0{,}6\cdot0{,}42 + 0{,}4\cdot0{,}32 = 0{,}38$
- $P(2) = 0{,}6\cdot0{,}09 + 0{,}4\cdot0{,}04 = 0{,}07$

b) Bastones en 0, 1 y 2 con alturas 0,55, 0,38 y 0,07.

**c) Sin reposición** (10 bolitas en B, 90 pares ordenados):
- Si pasó roja: P(0) = 7·6/90 = 42/90, P(1) = 2·3·7/90 = 42/90, P(2) = 3·2/90 = 6/90.
- Si pasó blanca: P(0) = 8·7/90 = 56/90, P(1) = 2·2·8/90 = 32/90, P(2) = 2/90.

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

a) Las probabilidades tienen que ser ≥ 0 y sumar 1. p₁ suma 0,70 y p₃ suma 1,10; sólo **p₂** suma 1.

b) Se acumula: 0,4; 0,5; 0,6; 0,7; 1.

c) P(2 < X < 4) = P(3) = 0,1. P(X < 2) = P(0) + P(1) = 0,5. P(X ≠ 0) = 1 − 0,4 = 0,6.

d) $k(5 + 4 + 3 + 2 + 1) = 15k = 1 \Rightarrow k = 1/15$.

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

a) La suma da 1: $0{,}65 + 3k + 5k^2 = 1 \Rightarrow 5k^2 + 3k - 0{,}35 = 0 \Rightarrow k = \frac{-3 + \sqrt{9 + 7}}{10} = 0{,}1$. (La otra raíz, −0,7, da probabilidades negativas.)

b) $0{,}1 + 5(0{,}01) = 0{,}15$.

c) La distribución queda 0,4 / 0,2 / 0,2 / 0,15 / 0,05 ⇒ la moda es 0. $E(X) = 0{,}2 + 0{,}4 + 0{,}45 + 0{,}2 = 1{,}25$ ≠ 0.

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

Una cadena (L): P(15) = 2/15, P(25) = 3/15, P(30) = 4/15, P(40) = 6/15. Dos cadenas independientes ⇒ 16 pares, cada uno con probabilidad $p_ip_j$ (denominador 225).

**X = (L₁ + L₂)/2**, sumando los pares que dan el mismo promedio:

| X | 15 | 20 | 22,5 | 25 | 27,5 | 30 | 32,5 | 35 | 40 |
|---|---|---|---|---|---|---|---|---|---|
| ·/225 | 4 | 12 | 16 | 9 | 48 | 16 | 36 | 48 | 36 |

(por ejemplo, 27,5 sale de (25,30) y (30,25): 2·3·4 = 24, más (15,40) y (40,15): 2·2·6 = 24, en total 48).

**Y = máx**: $P(Y \le y) = P(L \le y)^2$ ⇒ P(15) = 4/225, P(25) = 25/225 − 4/225 = 21/225, P(30) = 81/225 − 25/225 = 56/225, P(40) = 1 − 81/225 = 144/225.

b) E(L) = 31 y V(L) = 1035 − 961 = 74. Como X es el promedio de dos independientes: E(X) = 31 y V(X) = 74/2 = 37.

$E(Y) = \frac{15\cdot4 + 25\cdot21 + 30\cdot56 + 40\cdot144}{225} = \frac{8025}{225} \approx 35{,}67$; $V(Y) \approx 38{,}22$.

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

a) $E(X) = 1{,}25 + 3{,}375 + 3 = 7{,}625$. $E(X^2) = 6{,}25 + 25{,}3125 + 30 = 61{,}5625$ ⇒ $V(X) = 61{,}5625 - 58{,}1406 = 3{,}4219$.

b) $E(Y) = 20\cdot7{,}625 - 7{,}5 = 145$. $\sigma(Y) = |20|\,\sigma(X) = 20\cdot1{,}85 = 37$.

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

Los saltos de F dan $R_X = \{1, 2, 3, 6, 12\}$ con P = 0,1 / 0,3 / 0,2 / 0,3 / 0,1.

a)
- P(X < 5) = F(3) = 0,6
- P(X > 2) = 1 − F(2) = 0,6
- P(3 ≤ X ≤ 6) = F(6) − F(2) = 0,5
- P(3 < X ≤ 6) = F(6) − F(3) = 0,3

b) $\frac{P(3 \le X < 6)}{P(X \ge 3)} = \frac{P(X = 3)}{0{,}6} = \frac{0{,}2}{0{,}6} = \frac13$.

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

p = 16, 8, 4, 2, 1 (/31); F = 16, 24, 28, 30, 31 (/31).

a) $1 - p(0) = 15/31$.

b) Para el máximo M de dos independientes: $P(M \le k) = F(k)^2$ ⇒ $P(M = 2) = F(2)^2 - F(1)^2 = \frac{784 - 576}{961} = \frac{208}{961}$.

c) $P(M = k) = F(k)^2 - F(k-1)^2$: 256, 320, 208, 116, 61 (/961).

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

a) Clasificando cada caja seleccionada: {BB, BD, DB, DD}.

b) Es hipergeométrica: $\binom52 = 10$ casos. P(0) = $\binom32/10$ = 0,3; P(1) = 2·3/10 = 0,6; P(2) = 1/10 = 0,1. F: 0,3; 0,9; 1.

c) E(W) = 0,6 + 0,2 = 0,8. La mediana es el primer valor con F ≥ 0,5 ⇒ 1. La moda también es 1.

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

Las probabilidades de los 4 valores tienen que sumar 1:

$$P(0) + P(1) + P(2) + P(3) = \frac{c}{1} + \frac{c}{2} + \frac{c}{3} + \frac{c}{4} = 1$$

$$c\left(1 + \frac12 + \frac13 + \frac14\right) = c\cdot\frac{25}{12} = 1 \quad\Rightarrow\quad c = \frac{12}{25}$$

**b) Costo mensual esperado**

Usos esperados por día:

$$E(X) = 0\cdot\frac{c}{1} + 1\cdot\frac{c}{2} + 2\cdot\frac{c}{3} + 3\cdot\frac{c}{4} = c\left(\frac12 + \frac23 + \frac34\right) = \frac{12}{25}\cdot\frac{23}{12} = 0{,}92$$

El costo de un mes es C = 100 · (usos en los 20 días hábiles). Por linealidad de la esperanza:

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

Demanda: P = 0,2 / 0,35 / 0,25 / 0,15 / 0,05.

Con stock s, el beneficio es $G = 350\min(D, s) - 80\max(s - D, 0)$. Se calcula E(G) para cada s:

| s | 0 | 1 | 2 | 3 | 4 |
|---|---|---|---|---|---|
| E(G) | 0 | 264 | 377,5 | **383,5** | 325 |

(por ejemplo, con s = 1: 0,2·(−80) + 0,8·350 = 264).

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

Se verifica que f ≥ 0 y que el área total sea 1.

a) $\int_0^1 3x^2\,dx = 1$ y f ≥ 0 → sí.

b) $\int_0^\infty 3e^{-x/3}\,dx = 9 \neq 1$ → no.

c) f < 0 para x < 1 → no (aunque el área dé 1).

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

a) $a\int_0^1(x - x^3)dx = a(\frac12 - \frac14) = \frac a4 = 1 \Rightarrow a = 4$.

b) $F(x) = \int_0^x (4t - 4t^3)dt = 2x^2 - x^4$ en [0,1]; 0 antes y 1 después.

c) $E(X) = \int_0^1(4x^2 - 4x^4)dx = \frac43 - \frac45 = \frac8{15}$. $E(X^2) = \int_0^1(4x^3 - 4x^5)dx = 1 - \frac23 = \frac13$ ⇒ $V = \frac13 - \frac{64}{225} = \frac{11}{225}$.

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

a) $\int_{-1}^m \frac{(x+1)^2}{72}dx = \frac{(m+1)^3}{216} = 1 \Rightarrow m + 1 = 6 \Rightarrow m = 5$.

b) $F(x) = \frac{(x+1)^3}{216}$ en [−1, 5].

c) Ambas valen F(3) = 64/216 = 8/27 (en una VAC no importan los bordes).

d) $\frac{(x+1)^3}{216} = 0{,}75 \Rightarrow x = \sqrt[3]{162} - 1 \approx 4{,}45$.

e) $X = \frac{Y-1}{2}$ ⇒ $f_Y(y) = \frac12 f_X\left(\frac{y-1}{2}\right) = \frac{(y+1)^2}{576}$ en [−1, 11]. Mediana: $F_Y(y) = \frac{(y+1)^3}{1728} = \frac12 \Rightarrow y = \sqrt[3]{864} - 1 \approx 8{,}52$.

f) Con u = x + 1: $E(X) = \frac1{72}\int_0^6(u - 1)u^2du = \frac{324 - 72}{72} = 3{,}5$. $E(X^2) = 13{,}6$ ⇒ $V(X) = 1{,}35$ ⇒ $V(Y) = 4\cdot1{,}35 = 5{,}4$.

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

a) Por simetría, $2\int_0^{5c}x\,dx = 25c^2 = 1 \Rightarrow c = \frac15$ (X ∈ [−1, 1]).

b) $P(X \le -\frac12) = \int_{-1}^{-1/2}(-x)dx = \frac38$ ⇒ $P(A) = \frac58$; por simetría $P(B) = \frac58$.

$P(A\cap B) = P(-\frac12 < X < \frac12) = 2\int_0^{1/2}x\,dx = \frac14$. Como $\frac{25}{64} \neq \frac14$, no son independientes.

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

a) En [0, ½): F = t (y F(½) = ½). Para t ≥ ½: $F = \frac12 + \int_{1/2}^t \frac12e^{-(s-1/2)}ds = 1 - \frac12e^{-(t-1/2)}$.

b) 3 meses = 0,25 año.
- Regular: F(0,25) = 0,25.
- Bueno: F(3) − 0,25 = 0,75 − ½e^{−2,5} ≈ 0,709.
- Muy bueno: ½e^{−2,5} ≈ 0,041.

c) Cantidad de regulares ~ Bin(20; 0,25) ⇒ $P(\ge1) = 1 - 0{,}75^{20} \approx 0{,}9968$.

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

a) $F(x) = \int_1^x\frac{3-t}{2}dt = \frac32x - \frac14x^2 - \frac54$ en [1, 3].

b) $F(r) = 2(1 - F(r)) \Rightarrow F(r) = \frac23$ ⇒ $3r^2 - 18r + 23 = 0$ ⇒ $r = 3 - \frac{\sqrt{48}}6 \approx 1{,}845$ (la otra raíz cae fuera de [1, 3]).

c) Como X ≤ 3, la condición equivale a 2 ≤ X ≤ 3: $\frac{F(2{,}5) - F(2)}{1 - F(2)} = \frac{0{,}9375 - 0{,}75}{0{,}25} = \frac34$.

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

a) Área: triángulo (a/2) + rectángulo (a) + triángulo (a/2) = 2a = 1 ⇒ a = ½.

b) Integrando por tramos:
- $\frac{x^2}{4}$ en [0, 1)
- $\frac14 + \frac12(x - 1)$ en [1, 2)
- $\frac32x - \frac14x^2 - \frac54$ en [2, 3)
- 1 para x ≥ 3

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

Y: si X ∈ (0, 1), entonces ln X < 0. $F_Y(y) = P(\ln X \le y) = P(X \le e^y) = e^y$ ⇒ $f_Y(y) = e^y$ para y < 0.

Z: $F_Z(z) = P(X \le \frac{z-4}3) = \frac{z-4}3$ ⇒ $f_Z = \frac13$ en [4, 7] (uniforme).

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

$F(x) = x^3 + 1$. Como b < 0, b < b/2, así que el evento es b < X < b/2:

$\frac{F(b/2) - F(b)}{F(b/2)} = \frac{b^3/8 - b^3}{b^3/8 + 1} = \frac{-7b^3}{b^3 + 8}$.

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

C = 3T + 8 ⇒ E(C) = 3·2 + 8 = 14; V(C) = 3²·0,5 = 4,5.

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

F es continua en x = 3: b(4 + 1) = 1 − b ⇒ b = 1/6.

a) Derivando: x/3 en [0,1); 1/3 en [1,3); (4 − x)/3 en [3,4).

b) F(x) = 0,8. F(3) = 5/6 ≈ 0,833 > 0,8, así que x está en [1,3): $\frac16(2x - 1) = 0{,}8 \Rightarrow x = 2{,}9$ miles de litros.

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

Con u = r − 10, f = ¾(1 − u²) en [−1, 1].

a) $\int_{-0{,}3}^{0{,}3}\frac34(1 - u^2)du = \frac34(0{,}6 - 0{,}018) = 0{,}4365$.

b) $E(\pi R^2) = \pi E[(10 + u)^2] = \pi(100 + 20E(u) + E(u^2))$, con E(u) = 0 y $E(u^2) = \frac34(\frac23 - \frac25) = \frac15$ ⇒ $100{,}2\pi \approx 314{,}8$ m².

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

a) Diagonal: 0,08 + 0,15 + 0,16 = 0,39.

b) Columna 2: 0,04 + 0,09 + 0,16 + 0,12 = 0,41.

c) 0,09 + 0,16 + 0,12 = 0,37.

d) X₁: 0,19 / 0,30 / 0,25 / 0,26. X₂: 0,19 / 0,40 / 0,41. P(1,1) = 0,15 ≠ 0,30·0,40 = 0,12 ⇒ no son independientes.

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

a) $\sum(x + y) = 3\cdot6 + 3\cdot6 = 36 \Rightarrow c = 1/36$.

b)
- P(X = 1) = (2 + 3 + 4)/36 = 0,25 (Y < 4 siempre se cumple).
- P(Y = 1) = 0,25 por simetría.
- $P(X = 1 / Y = 1) = \frac{2/36}{9/36} = \frac29$.

c) E(X) = E(Y) = 13/6, E(X²) = 16/3 ⇒ V = 23/36. E(XY) = 14/3 ⇒ Cov = 14/3 − 169/36 = −1/36 ⇒ ρ = (−1/36)/(23/36) = −1/23.

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

a) Casos posibles $\binom82 = 28$:

| p | Y=0 | Y=1 | Y=2 |
|---|---|---|---|
| X=0 | 3/28 | 6/28 | 1/28 |
| X=1 | 9/28 | 6/28 | 0 |
| X=2 | 3/28 | 0 | 0 |

(por ejemplo, P(1, 0) = 1 azul y 1 verde = 3·3/28).

b) (0,0) + (1,0) + (0,1) = 18/28 = 9/14.

c) $P_Y(1) = 12/28$ y $P_X(0) = 10/28$ ⇒ (6/28)/(12/28) = 0,5 y (6/28)/(10/28) = 0,6.

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

Por simetría, E(X) = E(Y) = 0. E(XY) = b(1) + b(−1) + b(−1) + b(1) = 0 = E(X)E(Y) ⇒ Cov = 0 ⇒ ρ = 0.

No son independientes: P(0, 0) = 0, pero $P_X(0)P_Y(0) = (2c)^2 > 0$ (si c > 0).

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

a) 3·1 − 2·(−2) = 7

b) 9·4 = 36

c) $\rho\sigma_1\sigma_2 = \frac{\sqrt6}{3}\cdot2\cdot3 = 2\sqrt6$

d) $4 + 9 + 2\cdot2\sqrt6 = 13 + 4\sqrt6 \approx 22{,}8$

e) $4\cdot4 + 9\cdot9 - 2\cdot2\cdot3\cdot2\sqrt6 = 97 - 24\sqrt6 \approx 38{,}2$

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
