# Unidad 2 — Ejercicios resueltos

Ejercicios de la **Práctica 2 de la Guía de TP** (Variables aleatorias).

Cada ejercicio tiene un botón **Solución**. Al abrirlo aparece la respuesta y, arriba de ella, un segundo botón **Solución paso a paso** con el desarrollo completo.

---

### 1) Recorrido y clasificación

Indicar el recorrido de cada v.a. y clasificarla:
- a) Q: estudiantes ausentes el primer día, de 20 inscriptos.
- b) R: tiempo de espera en la caja de un banco.
- c) S: temperatura máxima y mínima de un día en La Plata.
- d) T: bicicletas en stock al final de un día, si la semana empezó con 120 y no hubo reposición.
- e) U: hijos que tiene una pareja hasta tener 3 mujeres, con un tope de 8 hijos.
- f) V: meses del año en que una fábrica excede los límites de contaminación.
- g) W: dinero que se obtiene al sacar 3 monedas de una caja con 2 de 50 ctv, 3 de 25 ctv y 4 de \$1.
- h) X: presión de un neumático cargado con 32 libras, medida un día cualquiera.
- i) Y: tiradas de una moneda hasta obtener dos caras o dos cecas consecutivas.
- j) Z: ruedas que, recolocadas al azar, quedan en su posición original.

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

### 2) Estaciones de servicio

Las estaciones A, B y C tienen 5, 3 y 2 surtidores. Recorrido de: a) U: total de surtidores en uso b) V: (en uso en B; en uso en C) c) W: estaciones con exactamente 2 surtidores en uso d) X: diferencia de surtidores en uso entre A y B.

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

- a) Entre 0 y 5 + 3 + 2 = 10.
- b) B va de 0 a 3 y C de 0 a 2: pares.
- c) Cualquiera de las 3 estaciones puede tener exactamente 2 en uso (A tiene 5, B tiene 3 y C tiene 2) → 0 a 3.
- d) $x_A - x_B$, con $x_A \in [0,5]$ y $x_B \in [0,3]$ → de 0 − 3 = −3 a 5 − 0 = 5.

</details>

**Respuesta:** a) {0, …, 10} b) {(x₁; x₂) / 0 ≤ x₁ ≤ 3, 0 ≤ x₂ ≤ 2} c) {0, 1, 2, 3} d) {−3, …, 5}

</details>

---

### 3) Bolillas azules

De una caja con 6 azules y 2 rojas se extraen 3 sin reposición. X = cantidad de azules.
a) Función de probabilidad. b) E(X) y V(X). c) E(X²), E(1/X), E(1/X²) y V(X²).

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

**Respuesta:** a) P(1) = 3/28, P(2) = 15/28, P(3) = 5/14 b) E = 9/4, V = 45/112 c) 153/28; 83/168; 0,2808; 7,7487

</details>

---

### 4) Dos urnas

A: 6 rojas y 4 blancas. B: 2 rojas y 7 blancas. Se pasa una bolita al azar de A a B y luego se extraen 2 de B. X = rojas extraídas.
a) Función de probabilidad con reposición. b) Gráfico. c) Ídem sin reposición.

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

**Respuesta:** a) 0,55 / 0,38 / 0,07 c) 119/225 / 19/45 / 11/225

</details>

---

### 5) Neumáticos con baja presión

| x | 0 | 1 | 2 | 3 | 4 |
|---|---|---|---|---|---|
| p₁ | 0,20 | 0,30 | 0,10 | 0,07 | 0,03 |
| p₂ | 0,40 | 0,10 | 0,10 | 0,10 | 0,30 |
| p₃ | 0,40 | 0,15 | 0,10 | 0,15 | 0,30 |

a) ¿Cuál es función de probabilidad? b) Su F(x). c) P(2 < X < 4), P(X < 2) y P(X ≠ 0). d) Si p(x) = k(5 − x), ¿cuánto vale k?

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

a) Las probabilidades tienen que ser ≥ 0 y sumar 1. p₁ suma 0,70 y p₃ suma 1,10; sólo **p₂** suma 1.

b) Se acumula: 0,4; 0,5; 0,6; 0,7; 1.

c) P(2 < X < 4) = P(3) = 0,1. P(X < 2) = P(0) + P(1) = 0,5. P(X ≠ 0) = 1 − 0,4 = 0,6.

d) $k(5 + 4 + 3 + 2 + 1) = 15k = 1 \Rightarrow k = 1/15$.

</details>

**Respuesta:** a) p₂ b) F = 0 (x < 0); 0,4 [0,1); 0,5 [1,2); 0,6 [2,3); 0,7 [3,4); 1 (x ≥ 4) c) 0,1; 0,5; 0,6 d) k = 1/15

</details>

---

### 6) Llegadas tarde

| x | 0 | 1 | 2 | 3 | 4 |
|---|---|---|---|---|---|
| p(x) | 0,3 + k | 2k | 0,2 | 0,1 + 5k² | 0,05 |

a) Hallar k. b) P(X = 3). c) Valor más probable; ¿coincide con el valor esperado?

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

a) La suma da 1: $0{,}65 + 3k + 5k^2 = 1 \Rightarrow 5k^2 + 3k - 0{,}35 = 0 \Rightarrow k = \frac{-3 + \sqrt{9 + 7}}{10} = 0{,}1$. (La otra raíz, −0,7, da probabilidades negativas.)

b) $0{,}1 + 5(0{,}01) = 0{,}15$.

c) La distribución queda 0,4 / 0,2 / 0,2 / 0,15 / 0,05 ⇒ la moda es 0. $E(X) = 0{,}2 + 0{,}4 + 0{,}45 + 0{,}2 = 1{,}25$ ≠ 0.

</details>

**Respuesta:** a) k = 0,1 b) 0,15 c) Moda = 0, E(X) = 1,25; no coinciden.

</details>

---

### 7) Cadenas de eslabones

Se producen cadenas de 15, 25, 30 y 40 eslabones en proporciones 2:3:4:6. Se eligen dos al azar con reposición. X = promedio de eslabones e Y = longitud máxima.
a) Funciones de probabilidad. b) Esperanza y varianza de ambas.

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

**Respuesta:** a) tablas de arriba b) E(X) = 31, V(X) = 37; E(Y) ≈ 35,67, V(Y) ≈ 38,2. (La guía da E(Y) = 35,2, pero la cuenta da 8025/225 ≈ 35,67.)

</details>

---

### 8) Lavarropas

| x (kg) | 5 | 7,5 | 10 |
|---|---|---|---|
| p | 0,25 | 0,45 | 0,30 |

a) E(X) y V(X). b) Si el precio es Y = 20X − 7,5, hallar E(Y) y σ(Y).

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

a) $E(X) = 1{,}25 + 3{,}375 + 3 = 7{,}625$. $E(X^2) = 6{,}25 + 25{,}3125 + 30 = 61{,}5625$ ⇒ $V(X) = 61{,}5625 - 58{,}1406 = 3{,}4219$.

b) $E(Y) = 20\cdot7{,}625 - 7{,}5 = 145$. $\sigma(Y) = |20|\,\sigma(X) = 20\cdot1{,}85 = 37$.

</details>

**Respuesta:** a) 7,625 y 3,4219 b) E(Y) = 145, σ(Y) = 37

</details>

---

### 9) Gimnasio Sporties

$F(x)$: 0 (x < 1); 0,1 [1,2); 0,4 [2,3); 0,6 [3,6); 0,9 [6,12); 1 (x ≥ 12).
a) P(X < 5), P(X > 2), P(3 ≤ X ≤ 6), P(3 < X ≤ 6). b) P(X < 6 / X ≥ 3).

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

**Respuesta:** a) 0,6; 0,6; 0,5; 0,3 b) 1/3

</details>

---

### 10) Máquinas tejedoras

$p(x) = \frac{16}{31}(\frac12)^x$, para x = 0, …, 4. a) P(se detiene algún día). b) Con independencia entre días: P(el máximo de lunes y martes es 2). c) Distribución del máximo.

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

p = 16, 8, 4, 2, 1 (/31); F = 16, 24, 28, 30, 31 (/31).
a) $1 - p(0) = 15/31$.
b) Para el máximo M de dos independientes: $P(M \le k) = F(k)^2$ ⇒ $P(M = 2) = F(2)^2 - F(1)^2 = \frac{784 - 576}{961} = \frac{208}{961}$.
c) $P(M = k) = F(k)^2 - F(k-1)^2$: 256, 320, 208, 116, 61 (/961).

</details>

**Respuesta:** a) 15/31 b) 208/961 c) 256, 320, 208, 116, 61 (sobre 961)

</details>

---

### 11) Cajas de cambio

Lotes de 5 cajas, de las cuales 2 son defectuosas; se inspeccionan 2. a) Espacio muestral. b) Funciones de probabilidad y de distribución de W = defectuosas seleccionadas. c) Esperanza, mediana y moda.

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

a) Clasificando cada caja seleccionada: {BB, BD, DB, DD}.
b) Es hipergeométrica: $\binom52 = 10$ casos. P(0) = $\binom32/10$ = 0,3; P(1) = 2·3/10 = 0,6; P(2) = 1/10 = 0,1. F: 0,3; 0,9; 1.
c) E(W) = 0,6 + 0,2 = 0,8. La mediana es el primer valor con F ≥ 0,5 ⇒ 1. La moda también es 1.

</details>

**Respuesta:** b) 0,3 / 0,6 / 0,1 c) E = 0,8, mediana = moda = 1

</details>

---

### 12) Herramienta alquilada

$P(x) = \frac{c}{x+1}$, con $R_X = \{0, 1, 2, 3\}$. a) Hallar c. b) Si se cobra \$100 por cada uso, costo mensual esperado (20 días hábiles).

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

a) $c(1 + \frac12 + \frac13 + \frac14) = c\cdot\frac{25}{12} = 1 \Rightarrow c = \frac{12}{25}$.
b) $E(X) = c(0 + \frac12 + \frac23 + \frac34) = \frac{12}{25}\cdot\frac{23}{12} = 0{,}92$ usos por día.
Costo mensual = $20\cdot100\cdot E(X) = \$1840$ (linealidad de la esperanza).

</details>

**Respuesta:** a) c = 12/25 b) \$1840

</details>

---

### 13) Stock de taladros

F de la demanda semanal: 0,2; 0,55; 0,8; 0,95; 1 (x = 0, …, 4). Cada taladro vendido deja \$350 y cada uno no vendido pierde \$80. ¿Cuántos conviene tener en stock?

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

**Respuesta:** conviene tener **3** taladros (beneficio esperado ≈ \$383,5).

</details>

---

### 14) ¿Funciones de densidad?

a) $3x^2$ en [0,1] b) $3e^{-x/3}$ para x > 0 c) $\frac23(x - 1)$ en [0,3].

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

Se verifica que f ≥ 0 y que el área total sea 1.
a) $\int_0^1 3x^2\,dx = 1$ y f ≥ 0 → sí.
b) $\int_0^\infty 3e^{-x/3}\,dx = 9 \neq 1$ → no.
c) f < 0 para x < 1 → no (aunque el área dé 1).

</details>

**Respuesta:** a) sí b) no c) no

</details>

---

### 15) Porcentaje de fallas

$f(x) = a(x - x^3)$ para 0 < x ≤ 1. a) Hallar a. b) F(x). c) E(X) y V(X).

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

a) $a\int_0^1(x - x^3)dx = a(\frac12 - \frac14) = \frac a4 = 1 \Rightarrow a = 4$.
b) $F(x) = \int_0^x (4t - 4t^3)dt = 2x^2 - x^4$ en [0,1]; 0 antes y 1 después.
c) $E(X) = \int_0^1(4x^2 - 4x^4)dx = \frac43 - \frac45 = \frac8{15}$. $E(X^2) = \int_0^1(4x^3 - 4x^5)dx = 1 - \frac23 = \frac13$ ⇒ $V = \frac13 - \frac{64}{225} = \frac{11}{225}$.

</details>

**Respuesta:** a) 4 b) F = 2x² − x⁴ c) E = 8/15, V = 11/225

</details>

---

### 16) Densidad con parámetro m

$f(x) = \frac1{72}(x + 1)^2$ en [−1, m]. a) Hallar m. b) F(x). c) P(−1 ≤ X < 3) y P(−1 < X < 3). d) Percentil 75. e) Densidad de Y = 2X + 1 y su mediana. f) E(X) y V(Y).

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

**Respuesta:** a) 5 b) (x+1)³/216 c) 8/27 d) ∛162 − 1 ≈ 4,45 e) (y+1)²/576 en [−1, 11], mediana ≈ 8,52 f) E(X) = 3,5, V(Y) = 5,4

</details>

---

### 17) Densidad |x|

$f(x) = |x|$ en [−5c, 5c]. a) Hallar c. b) ¿Son independientes A = {X > −½} y B = {X < ½}?

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

a) Por simetría, $2\int_0^{5c}x\,dx = 25c^2 = 1 \Rightarrow c = \frac15$ (X ∈ [−1, 1]).
b) $P(X \le -\frac12) = \int_{-1}^{-1/2}(-x)dx = \frac38$ ⇒ $P(A) = \frac58$; por simetría $P(B) = \frac58$.
$P(A\cap B) = P(-\frac12 < X < \frac12) = 2\int_0^{1/2}x\,dx = \frac14$. Como $\frac{25}{64} \neq \frac14$, no son independientes.

</details>

**Respuesta:** a) c = 1/5 b) No.

</details>

---

### 18) Componentes eléctricos

$f(t) = 1$ en [0, ½) y $\frac12e^{-(t - 1/2)}$ para t > ½ (en años). a) F(t). b) % regulares (< 3 meses), buenos (3 meses a 3 años) y muy buenos (> 3 años). c) Cajas de 20: si hay 1 o más regulares, se regala otra caja. P(recibir una caja de regalo).

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

**Respuesta:** a) F = t en [0, ½); 1 − ½e^{−(t−½)} para t ≥ ½ b) 25 %; ≈ 70,9 %; ≈ 4,1 % c) ≈ 0,9968

</details>

---

### 19) Densidad triangular

$f(x) = \frac12(3 - x)$ en [1, 3]. a) F(x). b) r tal que P(X < r) = 2P(X > r). c) P(X ≤ 5/2 / 2 ≤ X ≤ 7/2).

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

a) $F(x) = \int_1^x\frac{3-t}{2}dt = \frac32x - \frac14x^2 - \frac54$ en [1, 3].
b) $F(r) = 2(1 - F(r)) \Rightarrow F(r) = \frac23$ ⇒ $3r^2 - 18r + 23 = 0$ ⇒ $r = 3 - \frac{\sqrt{48}}6 \approx 1{,}845$ (la otra raíz cae fuera de [1, 3]).
c) Como X ≤ 3, la condición equivale a 2 ≤ X ≤ 3: $\frac{F(2{,}5) - F(2)}{1 - F(2)} = \frac{0{,}9375 - 0{,}75}{0{,}25} = \frac34$.

</details>

**Respuesta:** a) ver arriba b) r ≈ 1,845 c) 3/4

</details>

---

### 20) Densidad trapezoidal

f = ax en [0,1), a en [1,2), −ax + 3a en [2,3). a) Hallar a. b) F(x).

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

**Respuesta:** a) ½ b) la F de arriba

</details>

---

### 21) Transformaciones de una uniforme

X con f = 1 en (0, 1). Densidades de Y = ln X y Z = 3X + 4.

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

$f(x) = 3x^2$ en [−1, 0], con −1 < b < 0. Calcular P(X > b / X < b/2).

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

### 23) Costo de un proceso

El tiempo tiene E = 2 h y V = 0,5 h². El costo es \$3 por hora más \$8 fijos. E(C) y V(C).

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

C = 3T + 8 ⇒ E(C) = 3·2 + 8 = 14; V(C) = 3²·0,5 = 4,5.

</details>

**Respuesta:** E(C) = \$14, V(C) = 9/2

</details>

---

### 24) Demanda de combustible

F(x) = bx² en [0,1); b[2(x − 1) + 1] en [1,3); 1 − b(x − 4)² en [3,4); 1 desde 4. a) Densidad. b) Demanda superada sólo el 20 % de los días.

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

F es continua en x = 3: b(4 + 1) = 1 − b ⇒ b = 1/6.
a) Derivando: x/3 en [0,1); 1/3 en [1,3); (4 − x)/3 en [3,4).
b) F(x) = 0,8. F(3) = 5/6 ≈ 0,833 > 0,8, así que x está en [1,3): $\frac16(2x - 1) = 0{,}8 \Rightarrow x = 2{,}9$ miles de litros.

</details>

**Respuesta:** a) f = x/3, 1/3, (4 − x)/3 b) 2,9 miles de litros

</details>

---

### 25) Región circular de muestreo

$f(r) = \frac34[1 - (10 - r)^2]$ en [9, 11]. a) P(el radio difiere de 10 en a lo sumo 30 cm). b) Área esperada.

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

Con u = r − 10, f = ¾(1 − u²) en [−1, 1].
a) $\int_{-0{,}3}^{0{,}3}\frac34(1 - u^2)du = \frac34(0{,}6 - 0{,}018) = 0{,}4365$.
b) $E(\pi R^2) = \pi E[(10 + u)^2] = \pi(100 + 20E(u) + E(u^2))$, con E(u) = 0 y $E(u^2) = \frac34(\frac23 - \frac25) = \frac15$ ⇒ $100{,}2\pi \approx 314{,}8$ m².

</details>

**Respuesta:** a) 0,4365 b) 100,2π ≈ 314,8 m² (la guía da 100π, porque desprecia el término E(u²) = 0,2).

</details>

---

### 26) Pacientes regulares y de urgencia

| X₁ \ X₂ | 0 | 1 | 2 |
|---|---|---|---|
| 0 | 0,08 | 0,07 | 0,04 |
| 1 | 0,06 | 0,15 | 0,09 |
| 2 | 0,05 | 0,04 | 0,16 |
| 3 | 0 | 0,14 | 0,12 |

a) P(X₁ = X₂). b) P(X₂ = 2). c) P(X₂ = 2 y X₁ ≥ 1). d) Marginales; ¿son independientes?

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

a) Diagonal: 0,08 + 0,15 + 0,16 = 0,39.
b) Columna 2: 0,04 + 0,09 + 0,16 + 0,12 = 0,41.
c) 0,09 + 0,16 + 0,12 = 0,37.
d) X₁: 0,19 / 0,30 / 0,25 / 0,26. X₂: 0,19 / 0,40 / 0,41. P(1,1) = 0,15 ≠ 0,30·0,40 = 0,12 ⇒ no son independientes.

</details>

**Respuesta:** a) 0,39 b) 0,41 c) 0,37 d) no son independientes

</details>

---

### 27) Conjunta c(x + y)

f(x; y) = c(x + y) con x, y ∈ {1, 2, 3}. a) Hallar c. b) P(X = 1 ∧ Y < 4), P(Y = 1), P(X < 2 / Y < 2). c) Cov(X; Y) y ρ.

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

**Respuesta:** a) 1/36 b) 0,25; 0,25; 2/9 c) Cov = −1/36, ρ = −1/23

</details>

---

### 28) Cartuchos de bolígrafo

3 azules, 2 rojos y 3 verdes; se eligen 2. X = azules, Y = rojos. a) p(x, y). b) P(X + Y ≤ 1). c) P(X = 0 / Y = 1) y P(Y = 1 / X = 0).

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

**Respuesta:** b) 9/14 c) 0,5 y 0,6

</details>

---

### 29) Covarianza nula sin independencia

| X \ Y | −1 | 0 | 1 |
|---|---|---|---|
| −1 | b | c | b |
| 0 | c | 0 | c |
| 1 | b | c | b |

con b + c = 0,25. Demostrar que E(XY) = E(X)E(Y). ¿Son independientes? ¿Cuánto vale ρ?

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

### 30) Propiedades con dos variables

E(X₁) = 1, E(X₂) = −2, V(X₁) = 4, V(X₂) = 9, ρ = √6/3. Hallar: a) E(3X₁ − 2X₂) b) V(3X₁) c) Cov(X₁; X₂) d) V(X₁ + X₂) e) V(2X₁ − 3X₂).

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

**Respuesta:** a) 7 b) 36 c) 2√6 d) 13 + 4√6 e) 97 − 24√6

</details>

---

[← Volver al menú principal](../README.md)
