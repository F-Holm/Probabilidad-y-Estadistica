# Unidad 1 — Ejercicios resueltos

Ejercicios de la **Práctica 1 de la Guía de TP** (Probabilidades) y, al final, las **actividades del aula virtual** (introducciones y clase de repaso).

Cada ejercicio tiene un botón **Solución**. Al abrirlo aparece la respuesta y, arriba de ella, un segundo botón **Solución paso a paso** con el desarrollo completo.

---

## Práctica 1 — Guía de TP

### 1) Espacios muestrales

Para cada uno de los siguientes experimentos, definir el espacio muestral:
- a) Se analiza un tubo de ensayo con una muestra para detectar la presencia o ausencia de una molécula contaminante.
- b) Se seleccionan sucesivamente dos artículos de cierta producción y se clasifica cada uno en normal o defectuoso.
- c) Se arroja una moneda hasta obtener una cara.
- d) Se seleccionan dos billetes de una billetera que contiene uno de \$50, uno de \$10 y uno de \$5. Considerar el experimento con y sin reposición.
- e) De una caja con bolillas blancas y negras se extraen sucesivamente bolillas hasta obtener dos blancas o cuatro bolillas cualesquiera.
- f) Se mide el tiempo en minutos de espera en la parada del colectivo 7 entre las 23 h y las 24 h en Campus.

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

El espacio muestral es el conjunto de **todos** los resultados posibles. Conviene pensar cada experimento como una secuencia de etapas.

- a) Sólo hay dos resultados: la molécula está o no está.
- b) Cada artículo es N (normal) o D (defectuoso), y el orden importa porque se seleccionan sucesivamente: hay 2 · 2 = 4 pares.
- c) Se tira hasta que sale cara: puede salir en la 1.ª tirada, en la 2.ª (antes una cruz X), etc. Es un conjunto infinito numerable.
- d) **Sin reposición** no se puede repetir el billete y el orden importa: 3 · 2 = 6 pares. **Con reposición** sí se puede repetir: 3 · 3 = 9 pares.
- e) Se corta al obtener la 2.ª blanca (B) o al llegar a 4 extracciones:
  - Con 2 extracciones: BB.
  - Con 3: la 3.ª es la 2.ª blanca → NBB, BNB.
  - Con 4: o la 4.ª es la 2.ª blanca (NNBB, NBNB, BNNB) o se llega a 4 sin 2 blancas (BNNN, NBNN, NNBN, NNNB, NNNN).
- f) El tiempo es continuo, entre 0 y 60 minutos.

</details>

**Respuesta:**
- a) $S_1 = \{\text{sí}, \text{no}\}$
- b) $S_2 = \{NN, ND, DN, DD\}$
- c) $S_3 = \{C, XC, XXC, XXXC, \dots\}$
- d) Sin reposición: $\{(50;10),(50;5),(10;50),(10;5),(5;50),(5;10)\}$. Con reposición, se agregan además $(50;50),(10;10),(5;5)$ (9 pares).
- e) $S_6 = \{BB, NBB, BNB, NNBB, NBNB, BNNB, BNNN, NBNN, NNBN, NNNB, NNNN\}$
- f) $S_7 = [0; 60]$ minutos

</details>

---

### 2) Eventos y proposiciones

Con el experimento 1 b), describir por extensión: A = "el primer artículo es defectuoso", B = "al menos uno es defectuoso", C = "ambos son defectuosos". Indicar el valor de verdad de:
a) $A \subseteq B$ b) $C \subseteq A$ c) $A \cap C$ es un evento imposible d) El complemento de un evento imposible es cierto e) $B^c$ y $A$ son incompatibles.

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

$S = \{NN, ND, DN, DD\}$ (la primera letra es el primer artículo).
- A (primero D) = {DN, DD}
- B (al menos un D) = {ND, DN, DD}
- C (ambos D) = {DD}

a) Todos los elementos de A están en B → **V**.
b) DD ∈ A → **V**.
c) $A \cap C = \{DD\} \neq \emptyset$, así que no es imposible → **F**.
d) $\bar\emptyset = S$, el evento cierto → **V**.
e) $B^c = \{NN\}$ y $A \cap B^c = \emptyset$ → son incompatibles → **V**.

</details>

**Respuesta:** A = {DN, DD}, B = {DN, DD, ND}, C = {DD}. a) V b) V c) F d) V e) V.

</details>

---

### 3) Tres monedas

Se lanza una moneda equilibrada tres veces.
a) Establecer el espacio muestral. b) Asignar una probabilidad a cada punto. ¿Es un espacio de equiprobabilidad? c) Sea A "exactamente una cara" y B "al menos una cara". Obtener los puntos de A y de B. d) Calcular P(A), P(B), P(A∪B) y P(A∩B).

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

a) Con un árbol de 3 niveles (C/X en cada tirada) se obtienen $2^3 = 8$ ternas.
b) La moneda es equilibrada y las tiradas son independientes, así que cada terna tiene probabilidad $\frac12\cdot\frac12\cdot\frac12 = \frac18$. Es equiprobable.
c) A: una sola C → CXX, XCX, XXC. B: todas menos XXX.
d) Por Laplace: $P(A) = 3/8$ y $P(B) = 7/8$. Como $A \subseteq B$: $A \cap B = A$ y $A \cup B = B$.

</details>

**Respuesta:**
a) S = {CCC, CCX, CXC, XCC, XXC, XCX, CXX, XXX}
b) 1/8 cada punto; sí, es equiprobable.
c) A = {CXX, XCX, XXC}; B = S − {XXX}
d) P(A) = 3/8, P(B) = 7/8, P(A∪B) = 7/8, P(A∩B) = 3/8

</details>

---

### 4) Moneda cargada

Una moneda está cargada de modo que la probabilidad de cara es el triple que la de cruz. Calcular ambas probabilidades.

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

Sea $P(X) = q$. Entonces $P(C) = 3q$.
Como C y X son complementarios: $q + 3q = 1 \Rightarrow q = 1/4$.

</details>

**Respuesta:** $P(X) = 1/4$, $P(C) = 3/4$.

</details>

---

### 5) Frascos de mermelada

El 12 % de los frascos tiene peso insuficiente, el 8 % tiene problemas con la tapa y el 3 % presenta ambas fallas. Los frascos con alguna falla se descartan. Hallar la probabilidad de que un frasco al azar:
a) tenga exactamente una falla. b) no sea descartado.

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

A = peso insuficiente, B = tapa: $P(A) = 0{,}12$, $P(B) = 0{,}08$, $P(A \cap B) = 0{,}03$.

a) "Sólo A": $P(A \cap \bar B) = 0{,}12 - 0{,}03 = 0{,}09$. "Sólo B": $P(\bar A \cap B) = 0{,}08 - 0{,}03 = 0{,}05$.
Exactamente una falla $= 0{,}09 + 0{,}05 = 0{,}14$ (o bien $P(A) + P(B) - 2P(A\cap B)$).

b) Se descarta si tiene alguna falla: $P(A \cup B) = 0{,}12 + 0{,}08 - 0{,}03 = 0{,}17$.
No descartado: $P(\bar A \cap \bar B) = 1 - 0{,}17 = 0{,}83$.

Extra (de la resolución del aula virtual):
- $P(B/A) = 0{,}03/0{,}12 = 0{,}25$
- $P(A/\bar B) = 0{,}09/0{,}92 \approx 0{,}098$
- $0{,}12\cdot0{,}08 = 0{,}0096 \neq 0{,}03$ ⇒ A y B no son independientes.

</details>

**Respuesta:** a) 0,14 b) 0,83

</details>

---

### 6) Blanco cuadrado

Un blanco cuadrado de 2,5 m de lado recibe disparos independientes que impactan al azar en cualquier punto. Hallar la probabilidad de que:
a) un disparo impacte a menos de 1 m del centro.
b) impacte a menos de 1 m pero a más de ½ m del centro.
c) dos disparos caigan en el semiplano superior.
d) dos disparos caigan en distinto cuadrante.

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

Es probabilidad **geométrica**: P = área favorable / área total, con área total $= 2{,}5^2 = 6{,}25$ m².

a) Círculo de radio 1: $\pi \cdot 1^2 / 6{,}25 = \frac{4}{25}\pi \approx 0{,}503$.
b) Corona entre r = ½ y r = 1: $\pi(1 - \frac14)/6{,}25 = \frac{3}{25}\pi \approx 0{,}377$.
c) Cada disparo cae en el semiplano superior con P = ½. Por independencia: $\frac12\cdot\frac12 = \frac14$.
d) Cada cuadrante tiene P = ¼. Mismo cuadrante: $4\cdot\frac14\cdot\frac14 = \frac14$. Distinto cuadrante: $1 - \frac14 = \frac34$.

</details>

**Respuesta:** a) $\frac{4}{25}\pi$ b) $\frac{3}{25}\pi$ c) 1/4 d) 3/4

</details>

---

### 7) Dado cargado

La probabilidad de cada número par es proporcional a ese número (con la misma constante), y los impares tienen la misma probabilidad que en un dado normal. A = "par", B = "divisor de 6", C = "múltiplo de 5".
a) Hallar la probabilidad de cada elemento de S. b) Hallar P(A), P(A∪C), P(Aᶜ∩Bᶜ) y P(B − C).

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

a) P(1) = P(3) = P(5) = 1/6; P(2) = 2k, P(4) = 4k, P(6) = 6k.
La suma tiene que dar 1: $3\cdot\frac16 + 12k = 1 \Rightarrow k = \frac1{24}$.
Entonces P(2) = 1/12, P(4) = 1/6, P(6) = 1/4.

b) A = {2, 4, 6}, B = {1, 2, 3, 6}, C = {5}. **No** se puede usar Laplace, porque los resultados no son equiprobables.
- $P(A) = \frac1{12} + \frac16 + \frac14 = \frac12$ (o $1 - P(\text{impar}) = 1 - \frac36$).
- A y C son M.E. ⇒ $P(A \cup C) = \frac12 + \frac16 = \frac23$.
- $A^c \cap B^c = \overline{A \cup B} = \{5\}$ ⇒ $\frac16$.
- $B - C = B \cap C^c = B$ (B no tiene al 5) ⇒ $P(B) = \frac16 + \frac1{12} + \frac16 + \frac14 = \frac23$.

</details>

**Respuesta:** a) P(1) = P(3) = P(5) = P(4) = 1/6, P(2) = 1/12, P(6) = 1/4. b) P(A) = 1/2, P(A∪C) = 2/3, P(Aᶜ∩Bᶜ) = 1/6, P(B − C) = 2/3.

</details>

---

### 8) Anteojos

Una clase tiene 6 varones y 10 mujeres. La tercera parte de los varones y la quinta parte de las mujeres usan anteojos. Probabilidad de que un alumno al azar:
a) use anteojos o sea mujer. b) sea varón y no use anteojos.

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

Tabla de contingencia: varones con anteojos = 6/3 = 2; mujeres con anteojos = 10/5 = 2.

| | A (anteojos) | $\bar A$ | Total |
|---|---|---|---|
| M | 2 | 8 | 10 |
| V | 2 | 4 | 6 |
| Total | 4 | 12 | 16 |

a) $P(A \cup M) = \frac{4}{16} + \frac{10}{16} - \frac{2}{16} = \frac{12}{16} = \frac34$.
b) $P(V \cap \bar A) = \frac4{16} = \frac14$ (es justo el complemento de a).

</details>

**Respuesta:** a) 3/4 b) 1/4

</details>

---

### 9) Motores a inyección

Se eligen al azar 3 motores de 10, entre los cuales 4 son a inyección. Probabilidad de que:
a) ninguno sea a inyección. b) a lo sumo uno lo sea. c) al menos dos lo sean.

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

Casos posibles: $\binom{10}{3} = 120$. Sea I = cantidad a inyección.
a) $P(I = 0) = \binom{6}{3}/120 = 20/120 = 1/6$. (Con el teorema de la multiplicación: $\frac6{10}\cdot\frac59\cdot\frac48 = \frac16$.)
b) $P(I = 1) = \binom41\binom62/120 = 60/120$ ⇒ $P(I \le 1) = (20 + 60)/120 = 2/3$.
c) $P(I \ge 2) = 1 - P(I \le 1) = 1/3$.

</details>

**Respuesta:** a) 1/6 b) 2/3 c) 1/3

</details>

---

### 10) Cumpleaños

Probabilidad de que en una reunión de 8 personas al menos dos cumplan años el mismo día (año de 365 días). ¿Y con 23 personas?

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

Conviene el complemento: "todos cumplen en días distintos".
- Casos posibles (ordenando a las personas): $365^8$.
- Casos con días distintos: $365\cdot364\cdots358$ (cada persona tiene un día menos disponible).

$P(\text{distintos}) = \prod_{k=0}^{7}\frac{365-k}{365} \approx 0{,}9257$ ⇒ $P(\text{al menos 2 coinciden}) \approx 0{,}0743$.

Con 23 personas: $1 - \prod_{k=0}^{22}\frac{365-k}{365} \approx 0{,}5073$ (¡ya supera el 50 %!).

</details>

**Respuesta:** 8 personas: ≈ 0,0743. 23 personas: ≈ 0,507.

</details>

---

### 11) Unión de tres sucesos (T)

Usando $P(A\cup B) = P(A) + P(B) - P(A\cap B)$, probar
$P(A\cup B\cup C) = P(A)+P(B)+P(C)-P(A\cap B)-P(A\cap C)-P(B\cap C)+P(A\cap B\cap C)$.

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

1. Se agrupa: $P(A\cup B\cup C) = P[(A\cup B)\cup C] = P(A\cup B) + P(C) - P[(A\cup B)\cap C]$.
2. Distributiva: $(A\cup B)\cap C = (A\cap C)\cup(B\cap C)$.
3. Se aplica la propiedad otra vez: $P[(A\cap C)\cup(B\cap C)] = P(A\cap C) + P(B\cap C) - P(A\cap B\cap C)$, porque $(A\cap C)\cap(B\cap C) = A\cap B\cap C$.
4. Se reemplaza $P(A\cup B) = P(A) + P(B) - P(A\cap B)$ y se ordena.

</details>

**Respuesta:** queda demostrada la fórmula, con signo + para los sucesos sueltos, − para las intersecciones de a dos y + para la intersección triple.

</details>

---

### 12) Reincidencia y educación

| Educación | Reincidente | No reincidente | Total |
|---|---|---|---|
| 7 años o más | 0,10 | 0,30 | 0,40 |
| Menos de 7 años | 0,23 | 0,37 | 0,60 |
| Total | 0,33 | 0,67 | 1 |

A = "7 años o más de educación", B = "reincide".
a) P(A), P(B), P(A∩B), P(A/B). b) P(A∪B) y P((A∪B)ᶜ). c) ¿A y B son independientes?

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

a) Se leen los márgenes y la celda: P(A) = 0,40, P(B) = 0,33, P(A∩B) = 0,10. Luego $P(A/B) = \frac{0{,}10}{0{,}33} = \frac{10}{33} \approx 0{,}303$.
b) $P(A\cup B) = 0{,}40 + 0{,}33 - 0{,}10 = 0{,}63$ ⇒ $P((A\cup B)^c) = 0{,}37$ (es la celda "menos de 7 y no reincidente").
c) $P(A)P(B) = 0{,}132 \neq 0{,}10$ ⇒ no son independientes.

</details>

**Respuesta:** a) 0,4; 0,33; 0,1; 10/33 b) 0,63 y 0,37 c) No.

</details>

---

### 13) Traspaso entre oficinas

En Of1 hay 3 mujeres y 1 varón; en Of2, 2 mujeres y 2 varones. Se transfiere un empleado al azar de Of1 a Of2 y luego se elige uno de Of2. ¿Probabilidad de que sea mujer?

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

M₁ = "se transfiere una mujer" (P = 3/4), V₁ = "se transfiere un varón" (P = 1/4). Forman una partición.
- Si pasó una mujer, Of2 queda con 3M y 2V ⇒ $P(M_2/M_1) = 3/5$.
- Si pasó un varón, Of2 queda con 2M y 3V ⇒ $P(M_2/V_1) = 2/5$.

Probabilidad total: $P(M_2) = \frac34\cdot\frac35 + \frac14\cdot\frac25 = \frac{9}{20} + \frac{2}{20} = \frac{11}{20}$.

</details>

**Respuesta:** 11/20 = 0,55

</details>

---

### 14) Propiedades de la condicional (T)

Demostrar: a) Si A no es imposible, $P(B/A) + P(B^c/A) = 1$. b) Si $P(B/A) > P(B)$, entonces $P(B^c/A) < P(B^c)$. c) Si C no es imposible, $P(A\cup B/C) = P(A/C) + P(B/C) - P(A\cap B/C)$.

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

a) $P(A) > 0$. $P(B/A) + P(B^c/A) = \frac{P(A\cap B) + P(A\cap B^c)}{P(A)} = \frac{P(A)}{P(A)} = 1$, porque $A = (A\cap B)\cup(A\cap B^c)$ con M.E.

b) $P(B/A) > P(B) \Rightarrow 1 - P(B/A) < 1 - P(B)$. Por a), $1 - P(B/A) = P(B^c/A)$, y $1 - P(B) = P(B^c)$ ⇒ $P(B^c/A) < P(B^c)$.

c) $P(A\cup B/C) = \frac{P[(A\cap C)\cup(B\cap C)]}{P(C)} = \frac{P(A\cap C) + P(B\cap C) - P(A\cap B\cap C)}{P(C)}$, y se separa en las tres condicionales.

</details>

**Respuesta:** las tres igualdades quedan demostradas: la probabilidad condicional (con C fijo) cumple las mismas propiedades que una probabilidad.

</details>

---

### 15) Cubos entre dos cajas

La caja I tiene 7 azules y 3 verdes; la caja II, 6 azules y 4 verdes. Se pasa un cubo al azar de I a II y luego uno al azar de II a I.
a) Probabilidad de sacar un azul de I y un verde de II. b) Probabilidad de que las cajas queden como al principio.

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

a) $P(a_I) = 7/10$. Después de pasarlo, II tiene 7a y 4v (11 cubos) ⇒ $P(v_{II}/a_I) = 4/11$.
$P = \frac7{10}\cdot\frac4{11} = \frac{28}{110} = \frac{14}{55} \approx 0{,}2545$.

b) Las cajas quedan igual si vuelve un cubo del mismo color que el que se pasó:
- azul–azul: $\frac7{10}\cdot\frac7{11} = \frac{49}{110}$ (II tenía 7a de 11)
- verde–verde: $\frac3{10}\cdot\frac5{11} = \frac{15}{110}$ (II tenía 5v de 11)

Total: $\frac{64}{110} = \frac{32}{55} \approx 0{,}582$.

</details>

**Respuesta:** a) 14/55 b) 32/55

</details>

---

### 16) Independencia de a pares

Se tira un dado dos veces. A = "1.° par", B = "2.° par", C = "suma par". a) Mostrar que son independientes de a pares. b) Mostrar que no son mutuamente independientes.

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

36 pares equiprobables. P(A) = P(B) = 18/36 = 1/2. C: la suma es par si los dos son pares o los dos son impares ⇒ 9 + 9 = 18 ⇒ P(C) = 1/2.

a) A∩B = ambos pares: 9/36 = 1/4 = ½·½. A∩C = 1.° par y suma par ⇒ 2.° par ⇒ es el mismo evento: 1/4. Lo mismo con B∩C. Son independientes de a pares.

b) A∩B∩C = A∩B (si los dos son pares, la suma es par) ⇒ 1/4 ≠ ⅛ = P(A)P(B)P(C).

</details>

**Respuesta:** a) Todas las intersecciones de a dos valen 1/4 = ½·½. b) P(A∩B∩C) = 1/4 ≠ 1/8 ⇒ no son mutuamente independientes.

</details>

---

### 17) Unión de independientes (T)

Si A, B y C son mutuamente independientes y no imposibles, demostrar que $P(A\cup B\cup C) = 1 - P(A^c)P(B^c)P(C^c)$.

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

1. Complemento: $P(A\cup B\cup C) = 1 - P[(A\cup B\cup C)^c]$.
2. De Morgan: $(A\cup B\cup C)^c = A^c\cap B^c\cap C^c$.
3. Los complementos de sucesos independientes son independientes ⇒ $P(A^c\cap B^c\cap C^c) = P(A^c)P(B^c)P(C^c)$.

</details>

**Respuesta:** $P(A\cup B\cup C) = 1 - P(A^c)P(B^c)P(C^c)$ ("al menos uno" = 1 − "ninguno").

</details>

---

### 18) Datos parciales

$P(A) = \frac12$, $P(B) = \frac13$, $P(B - A) = \frac1{12}$. Hallar $P(A\cap B)$ y $P(A^c/B)$.

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

$B - A = B\cap A^c$ y $B = (B\cap A)\cup(B\cap A^c)$ ⇒ $P(A\cap B) = P(B) - P(B - A) = \frac13 - \frac1{12} = \frac14$.

$P(A^c/B) = \frac{P(A^c\cap B)}{P(B)} = \frac{1/12}{1/3} = \frac14$.

</details>

**Respuesta:** $P(A\cap B) = 1/4$ y $P(A^c/B) = 1/4$.

</details>

---

### 19) P(B/A) en casos especiales

Calcular P(B/A) si: a) $A \subseteq B$ b) A y B son incompatibles.

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

a) $A\subseteq B \Rightarrow A\cap B = A \Rightarrow P(B/A) = \frac{P(A)}{P(A)} = 1$ (siempre que ocurre A, ocurre B).
b) $A\cap B = \emptyset \Rightarrow P(B/A) = \frac{0}{P(A)} = 0$.

</details>

**Respuesta:** a) 1 b) 0

</details>

---

### 20) Dos dados, suma ≥ 8

Se tira un dado dos veces. Probabilidad de que la suma sea ≥ 8 si: a) sale un 4 en el primer dado. b) sale un 4 en al menos uno de los dados.

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

a) Si el primero es 4, hace falta que el segundo sea ≥ 4: {4, 5, 6} ⇒ 3/6 = 1/2.

b) Condición D = "al menos un 4": 6 + 6 − 1 = 11 pares ⇒ P(D) = 11/36.
Favorables (suma ≥ 8 y algún 4): (4,4), (4,5), (4,6), (5,4), (6,4) ⇒ 5/36 (el (4,4) se cuenta una sola vez).
$P = \frac{5/36}{11/36} = \frac5{11}$.

</details>

**Respuesta:** a) 1/2 b) 5/11

</details>

---

### 21) Caminos bloqueados

Hay tres caminos de A a B (A₁, A₂ el más corto, A₃) y dos de B a C (B₁, B₂). Cada uno está bloqueado con probabilidad 0,1, de manera independiente.
a) Probabilidad de que haya algún camino abierto de A a C. b) Si el camino más corto de A a B está cerrado, probabilidad de poder llegar de C a A.

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

Cada camino está abierto con P = 0,9.

a) Hace falta (algún tramo A–B abierto) **y** (algún tramo B–C abierto). Por independencia, se multiplican, y cada "alguno" es 1 − "ninguno":
$[1 - 0{,}1^3]\cdot[1 - 0{,}1^2] = 0{,}999\cdot0{,}99 = 0{,}98901$.

b) A₂ está cerrado, así que quedan A₁ y A₃: $[1 - 0{,}1^2]\cdot[1 - 0{,}1^2] = 0{,}99^2 = 0{,}9801$.

</details>

**Respuesta:** a) 0,98901 b) 0,9801

</details>

---

### 22) Urna sin reposición

Una urna tiene 7 rojas y 3 blancas. Se sacan 3 sin reposición. Probabilidad de que: a) las dos primeras sean rojas y la tercera blanca. b) exactamente una sea blanca.

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

a) Regla de la multiplicación: $\frac7{10}\cdot\frac69\cdot\frac38 = \frac{126}{720} = \frac7{40}$.
b) La blanca puede salir en la 1.ª, la 2.ª o la 3.ª extracción (RRB, RBR, BRR). Cada orden tiene la misma probabilidad (7·6·3/720), así que $P = 3\cdot\frac7{40} = \frac{21}{40}$.

</details>

**Respuesta:** a) 7/40 b) 21/40

</details>

---

### 23) Dos urnas, igual color

La urna A tiene 3 rojas y 2 blancas; la urna B, 2 rojas y 5 blancas. Se elige una urna al azar, se saca una bola y se coloca en la otra urna; luego se saca una bola de esa segunda urna. Probabilidad de que las dos bolas sean del mismo color.

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

**Se elige A (½):**
- Sale R (3/5) → B queda con 3R y 5B ⇒ P(R) = 3/8.
- Sale B (2/5) → B queda con 2R y 6B ⇒ P(B) = 6/8.
- Igual color: $\frac35\cdot\frac38 + \frac25\cdot\frac68 = \frac{21}{40}$.

**Se elige B (½):**
- Sale R (2/7) → A queda con 4R y 2B ⇒ P(R) = 4/6.
- Sale B (5/7) → A queda con 3R y 3B ⇒ P(B) = 3/6.
- Igual color: $\frac27\cdot\frac46 + \frac57\cdot\frac36 = \frac{23}{42}$.

Probabilidad total: $\frac12\left(\frac{21}{40} + \frac{23}{42}\right) = \frac12\cdot\frac{441 + 460}{840} = \frac{901}{1680}$.

</details>

**Respuesta:** 901/1680 ≈ 0,536

</details>

---

### 24) Independencia y exclusión (T)

a) Si A y B son independientes, también lo son A y Bᶜ (y Aᶜ y B); deducir que Aᶜ y Bᶜ también lo son. b) Si A y B son excluyentes y P(A)P(B) > 0, entonces **no** son independientes.

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

a) $P(A\cap B^c) = P(A) - P(A\cap B) = P(A) - P(A)P(B) = P(A)[1 - P(B)] = P(A)P(B^c)$.
Para los dos complementos: $P(A^c\cap B^c) = 1 - P(A\cup B) = 1 - P(A) - P(B) + P(A)P(B) = (1 - P(A))(1 - P(B)) = P(A^c)P(B^c)$.

b) $P(A\cap B) = P(\emptyset) = 0$, pero $P(A)P(B) > 0$ ⇒ no se cumple la definición de independencia.

</details>

**Respuesta:** a) Los pares de complementos heredan la independencia. b) Dos sucesos excluyentes con probabilidad positiva nunca son independientes.

</details>

---

### 25) Supervivencia

P(el hombre vive 10 años más) = 1/3 y P(la mujer vive 10 años más) = 1/4, de manera independiente. Probabilidad de que dentro de 10 años: a) ambos vivan b) al menos uno viva c) ninguno viva d) sólo la mujer viva.

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

a) $\frac13\cdot\frac14 = \frac1{12}$
b) $\frac13 + \frac14 - \frac1{12} = \frac12$
c) $\frac23\cdot\frac34 = \frac12$ (= 1 − b)
d) $\frac14\cdot\frac23 = \frac16$

</details>

**Respuesta:** a) 1/12 b) 1/2 c) 1/2 d) 1/6

</details>

---

### 26) Cajoneras

Hay tres cajoneras con dos cajones cada una: plata–plata, plata–oro y oro–oro. Se elige una cajonera al azar y se abre un cajón: sale oro. ¿Probabilidad de que el otro cajón también tenga oro?

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

E₁ (PP), E₂ (PO) y E₃ (OO), cada una con P = 1/3. P(oro/E₁) = 0, P(oro/E₂) = ½, P(oro/E₃) = 1.
Probabilidad total: $P(O) = \frac13(0 + \frac12 + 1) = \frac12$.
El otro cajón tiene oro sólo si es la cajonera E₃. Por Bayes: $P(E_3/O) = \frac{\frac13\cdot1}{\frac12} = \frac23$.

</details>

**Respuesta:** 2/3

</details>

---

### 27) Test diagnóstico

1 de cada 25 adultos tiene la enfermedad. El test da positivo en el 98 % de los enfermos y en el 3 % de los sanos.
a) P(test positivo). b) P(enfermo / positivo). c) P(sano / negativo).

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

E = enfermo: P(E) = 0,04, P(Eᶜ) = 0,96. P(+/E) = 0,98, P(+/Eᶜ) = 0,03.

a) Probabilidad total: $0{,}04\cdot0{,}98 + 0{,}96\cdot0{,}03 = 0{,}0392 + 0{,}0288 = 0{,}068$.
b) Bayes: $\frac{0{,}0392}{0{,}068} = 0{,}5765$ (sube de 4 % a priori a 58 % a posteriori).
c) $P(-) = 0{,}932$ y $P(E^c\cap -) = 0{,}96\cdot0{,}97 = 0{,}9312$ ⇒ $\frac{0{,}9312}{0{,}932} = 0{,}9991$.

</details>

**Respuesta:** a) 0,068 b) 0,5765 c) 0,9991

</details>

---

### 28) Un artículo de cada caja

La caja A tiene 3 defectuosos de 8; la B, 2 de 5; la C, 4 de 10. Se extrae un artículo de cada caja.
a) P(todos defectuosos). b) P(sólo uno defectuoso). c) P(el defectuoso es de A / sólo uno es defectuoso).

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

$P(D_A) = 3/8$, $P(D_B) = 2/5$, $P(D_C) = 4/10$. Las cajas son independientes.

a) $\frac38\cdot\frac25\cdot\frac4{10} = \frac{24}{400} = \frac3{50}$.

b) Tres casos M.E.:
- sólo A: $\frac38\cdot\frac35\cdot\frac6{10} = \frac{54}{400}$
- sólo B: $\frac58\cdot\frac25\cdot\frac6{10} = \frac{60}{400}$
- sólo C: $\frac58\cdot\frac35\cdot\frac4{10} = \frac{60}{400}$

Suma: $\frac{174}{400} = \frac{87}{200}$.

c) $\frac{54/400}{174/400} = \frac{54}{174} = \frac9{29}$.

</details>

**Respuesta:** a) 3/50 b) 87/200 c) 9/29

</details>

---

### 29) Deporte

Practican deporte el 40 % de los hombres y el 55 % de las mujeres; el 70 % de los estudiantes son mujeres. Si un estudiante hace deporte, ¿probabilidad de que sea mujer?

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

$P(D) = 0{,}7\cdot0{,}55 + 0{,}3\cdot0{,}4 = 0{,}385 + 0{,}12 = 0{,}505$.
Bayes: $P(M/D) = \frac{0{,}385}{0{,}505} = \frac{77}{101} \approx 0{,}7624$.

</details>

**Respuesta:** 77/101 ≈ 0,762

</details>

---

### 30) Aerolíneas Cordobesas

El 30 % viaja con familia, el 25 % con amigos y el resto solo. Viajan de noche: la mitad de los que van con familia, el 70 % de los que van con amigos y el 25 % de los que viajan solos.
a) P(no viaja de noche). b) P(viaja con amigos / viaja de noche).

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

P(S) = 1 − 0,30 − 0,25 = 0,45.
a) $P(N) = 0{,}3\cdot0{,}5 + 0{,}25\cdot0{,}7 + 0{,}45\cdot0{,}25 = 0{,}15 + 0{,}175 + 0{,}1125 = 0{,}4375$ ⇒ $P(\bar N) = 0{,}5625$.
b) $P(A/N) = \frac{0{,}175}{0{,}4375} = 0{,}4$.

</details>

**Respuesta:** a) 0,5625 b) 0,4

</details>

---

### 31) Comisión de docentes

Hay seis titulares: Euler, Cauchy, Leibnitz, Laplace, Gauss y Euclides. Se eligen 3 al azar.
a) P(alguno tiene apellido que empieza con L). b) Si dos tienen la misma inicial, ¿probabilidad de que sea la L? c) Con antigüedades 12, 15, 9, 16, 20 y 7 años, se eligen dos al azar: probabilidad de que la suma sea 1) 27 años 2) mayor a 30 años.

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

Total de comisiones: $\binom63 = 20$. Hay 2 con L (Leibnitz, Laplace) y 2 con E (Euler, Euclides).

a) Ninguna L: $\binom43 = 4$ ⇒ $P = 1 - \frac4{20} = 0{,}8$.

b) "Dos con la misma inicial" sólo puede ser LL o EE (no hay tres con la misma inicial). Comisiones con LL: $\binom22\cdot4 = 4$; con EE: también 4. ⇒ $P = \frac4{8} = \frac12$.

c) Pares posibles: $\binom62 = 15$.
1) Suma 27: (12, 15) y (20, 7) ⇒ 2/15.
2) Suma > 30: 12+20, 15+16, 15+20, 16+20 ⇒ 4/15.

</details>

**Respuesta:** a) 0,8 b) 1/2 c) 1) 2/15 2) 4/15

</details>

---

## Actividades del aula virtual

### Introducción (parte 1) — 1) Bolitas de colores

Hay 10 bolitas verdes, 4 rojas, 8 azules y 3 blancas. Se toma una al azar. Probabilidad de que: a) sea roja b) sea verde o azul c) no sea blanca d) no sea roja ni azul.

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

Total 25 (equiprobables, Laplace).
a) 4/25
b) (10 + 8)/25 = 18/25
c) 1 − 3/25 = 22/25
d) verdes o blancas: 13/25

</details>

**Respuesta:** a) 0,16 b) 0,72 c) 0,88 d) 0,52

</details>

---

### Introducción (parte 1) — 2) Cartones

Hay 10 cartones rojos numerados del 1 al 10 y 15 verdes del 11 al 25. Se saca uno al azar. Probabilidad de que: a) sea verde b) sea menor a 20 c) sea rojo y par d) sea rojo o par e) no sea verde ni impar f) entre los verdes, sea impar g) entre los impares, sea verde.

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

Total 25.
a) 15/25 = 3/5
b) del 1 al 19: 19/25
c) rojos pares (2, 4, 6, 8, 10): 5/25 = 1/5
d) 10 rojos + verdes pares (12, 14, …, 24 = 7) = 17/25
e) "no verde y no impar" = rojo y par = 1/5
f) verdes impares 11, 13, …, 25 = 8 de 15 ⇒ 8/15
g) impares: 5 rojos + 8 verdes = 13 ⇒ 8/13

</details>

**Respuesta:** a) 3/5 b) 19/25 c) 1/5 d) 17/25 e) 1/5 f) 8/15 g) 8/13

</details>

---

### Introducción (parte 1) — 3) Envases de bebida

| | A | B |
|---|---|---|
| Hombre | 25 | 40 |
| Mujer | 35 | 50 |

a) P(hombre) b) P(prefiere B) c) P(hombre y prefiere B) d) P(prefiere B / hombre) e) Completar las tablas de porcentajes por fila y por columna e interpretar la celda (Hombre, B).

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

Totales: H = 65, M = 85, A = 60, B = 90, N = 150.
a) 65/150 ≈ 0,433
b) 90/150 = 0,6
c) 40/150 ≈ 0,267
d) 40/65 ≈ 0,615 (condicional: se reduce el espacio a los 65 hombres)
e) **Por fila** (cada fila suma 100 %): H: A 38,5 %, B 61,5 %; M: A 41,2 %, B 58,8 %. La celda (H, B) = 61,5 % es el porcentaje de hombres que prefiere B, o sea P(B/H).
**Por columna** (cada columna suma 100 %): A: H 41,7 %, M 58,3 %; B: H 44,4 %, M 55,6 %. La celda (H, B) = 44,4 % es el porcentaje de hombres entre quienes prefieren B, o sea P(H/B).

</details>

**Respuesta:** a) 0,433 b) 0,6 c) 0,267 d) 0,615 e) 61,5 % = P(B/H) y 44,4 % = P(H/B)

</details>

---

### Introducción (parte 1) — 4), 5) y 6)

4) El 10 % de los artículos tiene sólo la falla A, el 20 % sólo la falla B y el 55 % no tiene fallas. ¿P(ambas fallas)?
5) El 70 % de los estudiantes es de mecánica y el 10 % de ellos desaprueba. ¿P(mecánica y desaprueba)?
6) La planta M fabrica el 60 % (10 % fallado) y la N el resto (5 % fallado). ¿P(fallado)?

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

4) Las cuatro regiones del Venn suman 1: $1 - 0{,}10 - 0{,}20 - 0{,}55 = 0{,}15$.
5) Teorema de la multiplicación: $0{,}7\cdot0{,}1 = 0{,}07$.
6) Probabilidad total: $0{,}6\cdot0{,}1 + 0{,}4\cdot0{,}05 = 0{,}08$.

</details>

**Respuesta:** 4) 0,15 5) 0,07 6) 0,08

</details>

---

### Introducción (parte 2) — 1) Diagrama de Venn

Las regiones son: sólo A = 0,20, A∩B = 0,30, sólo B = 0,10, fuera de ambos = 0,40. Calcular a) P(A) b) P(B∩Aᶜ) c) P(A∪B) d) P(B/A) e) P(Aᶜ/B).

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

a) 0,20 + 0,30 = 0,5
b) sólo B = 0,1
c) 0,2 + 0,3 + 0,1 = 0,6
d) 0,3/0,5 = 0,6
e) P(B) = 0,4 ⇒ 0,1/0,4 = 0,25

</details>

**Respuesta:** a) 0,5 b) 0,1 c) 0,6 d) 0,6 e) 0,25

</details>

---

### Introducción (parte 2) — 2) Dos fallas

El 30 % tiene la falla A, el 20 % la falla B y el 65 % no tiene fallas. P de: a) ambas fallas b) una sola falla c) estar fallado d) B entre los que tienen A e) A entre los que no tienen B.

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

$P(A\cup B) = 1 - 0{,}65 = 0{,}35$.
a) $0{,}3 + 0{,}2 - 0{,}35 = 0{,}15$
b) $0{,}35 - 0{,}15 = 0{,}20$
c) 0,35
d) $0{,}15/0{,}3 = 0{,}5$
e) $P(A\cap\bar B) = 0{,}15$ y $P(\bar B) = 0{,}8$ ⇒ 0,1875

</details>

**Respuesta:** a) 0,15 b) 0,20 c) 0,35 d) 0,5 e) 0,1875

</details>

---

### Introducción (parte 2) — 3) Divisiones de PyE

Las divisiones A, B y C tienen el 25 %, 35 % y 40 % de los alumnos, con 20 %, 30 % y 25 % de desaprobados. a) P(desaprobado). b) P(es de C / desaprobado).

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

a) $0{,}25\cdot0{,}2 + 0{,}35\cdot0{,}3 + 0{,}4\cdot0{,}25 = 0{,}05 + 0{,}105 + 0{,}1 = 0{,}255$
b) Bayes: $0{,}1/0{,}255 \approx 0{,}392$

</details>

**Respuesta:** a) 0,255 b) ≈ 0,392

</details>

---

### Introducción (parte 2) — 5) y 6) Árbol de 3 extracciones

Hay 4 negras y 3 blancas y se extraen 3. Con el árbol, calcular: a) $P(B_1\cap N_2\cap B_3)$ b) que las tres sean negras c) que salgan exactamente dos negras. 5) sin reposición. 6) con reposición.

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

**Sin reposición** (los denominadores bajan: 7, 6, 5):
- a) $\frac37\cdot\frac46\cdot\frac25 = \frac{24}{210} = \frac4{35}$
- b) $\frac47\cdot\frac36\cdot\frac25 = \frac4{35}$
- c) NNB, NBN y BNN valen cada una $\frac{36}{210}$ ⇒ $\frac{108}{210} = \frac{18}{35}$

**Con reposición** (siempre 4/7 y 3/7):
- a) $\frac37\cdot\frac47\cdot\frac37 = \frac{36}{343}$
- b) $(\frac47)^3 = \frac{64}{343}$
- c) $3\cdot(\frac47)^2\cdot\frac37 = \frac{144}{343}$

</details>

**Respuesta:** sin reposición: 4/35, 4/35, 18/35. Con reposición: 36/343, 64/343, 144/343.

</details>

---

### Introducción (parte 2) — 7) Tipos de sangre

A 40 %, B 20 %, O 30 %, AB 10 %. Se eligen dos personas independientes. P de que: a) ambas sean A b) ninguna sea A c) una sea A y la otra O d) alguna sea AB e) tengan el mismo tipo f) tengan distinto tipo.

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

a) $0{,}4^2 = 0{,}16$
b) $0{,}6^2 = 0{,}36$
c) dos órdenes: $2\cdot0{,}4\cdot0{,}3 = 0{,}24$
d) $1 - 0{,}9^2 = 0{,}19$
e) $0{,}16 + 0{,}04 + 0{,}09 + 0{,}01 = 0{,}30$
f) 0,70

</details>

**Respuesta:** a) 0,16 b) 0,36 c) 0,24 d) 0,19 e) 0,30 f) 0,70

</details>

---

### Introducción (parte 2) — 8) Equipo de fútbol

Gana con P = 0,6, pierde con P = 0,3 y empata con P = 0,1; juega 3 partidos. P de que: a) gane el 1.°, pierda el 2.° y empate el 3.° b) gane uno, pierda otro y empate otro c) gane 2.

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

a) $0{,}6\cdot0{,}3\cdot0{,}1 = 0{,}018$
b) hay $3! = 6$ órdenes ⇒ $0{,}108$
c) exactamente 2 victorias: $\binom32 0{,}6^2\cdot0{,}4 = 0{,}432$

</details>

**Respuesta:** a) 0,018 b) 0,108 c) 0,432

</details>

---

### Introducción (parte 2) — 9) Pozos de agua

Cada pozo es potable con P = 0,1. Probabilidad de que el primero potable sea: a) el 2.° pozo b) el 10.° c) el n-ésimo.

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

Hace falta que los n − 1 anteriores fallen (0,9 cada uno) y que el n-ésimo sea potable:
a) $0{,}9\cdot0{,}1 = 0{,}09$
b) $0{,}9^9\cdot0{,}1 \approx 0{,}0387$
c) $0{,}9^{n-1}\cdot0{,}1$

</details>

**Respuesta:** a) 0,09 b) ≈ 0,0387 c) $0{,}9^{n-1}\cdot0{,}1$

</details>

---

### Introducción (parte 2) — 10) Supermercado

El 90 % compra comestibles, el 70 % artículos de limpieza y el 20 % electrodomésticos. P de que el próximo cliente compre: a) los tres b) ninguno c) alguno d) al menos dos.

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

El enunciado no da intersecciones, así que hay que **suponer independencia** entre los rubros.
a) $0{,}9\cdot0{,}7\cdot0{,}2 = 0{,}126$
b) $0{,}1\cdot0{,}3\cdot0{,}8 = 0{,}024$
c) $1 - 0{,}024 = 0{,}976$
d) $P(CT) + P(CE) + P(TE) - 2P(CTE) = 0{,}63 + 0{,}18 + 0{,}14 - 2\cdot0{,}126 = 0{,}698$

</details>

**Respuesta (suponiendo independencia):** a) 0,126 b) 0,024 c) 0,976 d) 0,698

</details>

---

### Clase de repaso — Ej. 1) Cursos del turno noche

Los cursos tienen 35, 25 y 18 alumnos, de los cuales 3, 5 y 4 no trabajan. a) Se elige un alumno: 1) P(no trabaja) 2) P(no trabaja / 1.er curso) 3) P(3.er curso / trabaja). b) Se eligen 4: P(dos no trabajan y dos sí).

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

Total 78; no trabajan 12; trabajan 66 (32, 20 y 14).
a) 1) 12/78 2) 3/35 3) 14/66
b) Con la aproximación de independencia que usa la resolución del aula: P(T) = 11/13 y P(T̄) = 2/13. Hay $\binom42 = 6$ órdenes ⇒ $6\left(\frac{11}{13}\right)^2\left(\frac2{13}\right)^2 \approx 0{,}102$.
(Sin reposición exacta: $\binom{12}{2}\binom{66}{2}/\binom{78}{4} \approx 0{,}0992$.)

</details>

**Respuesta:** a) 12/78 ≈ 0,154; 3/35; 14/66 ≈ 0,212 b) ≈ 0,102

</details>

---

### Clase de repaso — Ej. 2) a 8)

2) Se tira una moneda y luego un dado; si salió cara, P(par) = 1/4. ¿P(cara e impar)?
3) Proveedores con el 10 %, 30 % y 60 % de los lotes, con rechazos de 2 %, 0,4 % y 0,2 %. a) P(rechazo) b) P(3.er proveedor / rechazo).
4) Cerradura de 3 discos con dígitos de 0 a 5. a) Abre con un número que empieza con 3 y es par. b) Se agrega otra cerradura independiente que abre con 153; se abre la puerta si abre alguna.
5) P(A/B) si A ⊆ B y si son independientes.
6) Demostrar $P(A\cup C/B) = P(A/B) + P(C/B) - P(A\cap C/B)$.
7) ¿Cuándo A y B son incompatibles y cuándo independientes? Si P(A∩B) = 0, P(A) = 0,5 y P(B) = 0,3, ¿son complementarios?
8) ¿Qué condiciones deben cumplir A, B y C para aplicar probabilidad total a D?

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

2) $\frac12\cdot\frac34 = \frac38$.
3) a) $0{,}1\cdot0{,}02 + 0{,}3\cdot0{,}004 + 0{,}6\cdot0{,}002 = 0{,}0044$ b) $0{,}0012/0{,}0044 \approx 0{,}273$.
4) a) 1.er disco = 3 (1/6), último par {0, 2, 4} (1/2) y el del medio cualquiera ⇒ 1/12. b) P(153) = 1/216 ⇒ $\frac1{12} + \frac1{216} - \frac1{12}\cdot\frac1{216} \approx 0{,}0876$.
5) Si A ⊆ B: P(A)/P(B). Si son independientes: P(A).
6) Igual que el Ej. 14 c) de la guía, con B en lugar de C.
7) Incompatibles: A∩B = ∅. Independientes: P(A∩B) = P(A)P(B). No son complementarios: además deberían sumar 1, y 0,5 + 0,3 = 0,8.
8) A, B y C deben ser M.E. y su unión debe ser S (una partición). Entonces $P(D) = P(A)P(D/A) + P(B)P(D/B) + P(C)P(D/C)$.

</details>

**Respuesta:** 2) 3/8 3) 0,0044 y 0,273 4) 1/12 y ≈ 0,0876 5) P(A)/P(B) y P(A) 7) no son complementarios 8) tienen que formar una partición de S.

</details>

---

### Ejercicios teóricos del aula — 2) y 5)

2) Si A ≠ ∅ y B ≠ ∅ (con probabilidad positiva), probar: a) si son M.E., no son independientes b) si son independientes, no son M.E.
5) Si B ≠ ∅, probar que $P(A/B) + P(\bar A/B) = 1$.

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

2) a) M.E. ⇒ P(A∩B) = 0 ≠ P(A)P(B) > 0. b) Independientes ⇒ P(A∩B) = P(A)P(B) > 0 ⇒ A∩B ≠ ∅.
5) $\frac{P(A\cap B) + P(\bar A\cap B)}{P(B)} = \frac{P(B)}{P(B)} = 1$.

(Los demás ejercicios teóricos del aula son los Ej. 11, 14, 17, 19 y 24 de la guía, resueltos más arriba.)

</details>

**Respuesta:** ambas propiedades quedan demostradas.

</details>
