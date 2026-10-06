# Unidad 1 — Ejercicios resueltos

Ejercicios de la **Práctica 1 de la Guía de TP** (Probabilidades) y, al final, las **actividades del aula virtual** (introducciones y clase de repaso).

Cada ejercicio tiene un botón **Solución**. Al abrirlo aparece la respuesta y, arriba de ella, un segundo botón **Solución paso a paso** con el desarrollo completo.

> **Referencias:** ⭐ = ejercicio sugerido como prioritario en los apuntes de la cátedra. ⏭️ = no es necesario resolverlo.

---

## Práctica 1 — Guía de TP

### 1) Espacios muestrales ⭐

Para cada uno de los siguientes experimentos, se pide definir el espacio muestral:

- a) Se analiza un tubo de ensayo con una muestra para detectar la presencia o ausencia de una molécula contaminante.
- b) Se seleccionan sucesivamente dos artículos de cierta producción y se clasifica cada uno en normal o defectuoso.
- c) Se arroja una moneda hasta obtener una cara.
- d) Se seleccionan dos billetes de una billetera que contiene uno de 50 pesos, uno de 10 pesos y uno de 5 pesos. Considerar el experimento con y sin reposición.
- e) De una caja que contiene bolillas blancas y negras se extraen sucesivamente bolillas hasta obtener dos blancas o cuatro bolillas cualesquiera.
- f) Se mide el tiempo en minutos de espera en la parada del colectivo 7 entre las 23 hs. y las 24 hs. en Campus.

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

Describir por extensión los siguientes eventos correspondientes a los experimentos aleatorios descriptos en el ítem (b) del ejercicio anterior.

- A: el primer artículo seleccionado es defectuoso.
- B: al menos uno de los artículos es defectuoso.
- C: ambos artículos son defectuosos.

Indicar el valor de verdad de las siguientes proposiciones:

- a) A ⊆ B
- b) C ⊆ A
- c) A ∩ C es un evento imposible.
- d) El complemento de un evento imposible es cierto.
- e) Bᶜ y A son eventos incompatibles.

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

**Respuesta:** A = {DN, DD}, B = {DN, DD, ND}, C = {DD}.

- a) V
- b) V
- c) F
- d) V
- e) V.

</details>

---

### 3) Tres monedas

Supongamos que se lanza una moneda equilibrada tres veces y se observan las caras superiores registrando cara o cruz según corresponda.

- a) Establecer el espacio muestral de este experimento.
- b) Asignar una probabilidad a cada punto. ¿Se trata de un espacio de equiprobabilidad?
- c) Sea A el evento de observar exactamente una vez cara y B el evento de observar al menos una cara. Obtener los puntos muestrales de A y B.
- d) A partir de las respuestas anteriores, calcular P(A), P(B), P(A ∪ B) y P(A ∩ B).

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

### 4) Moneda cargada ⭐

Una moneda está cargada de modo tal que la probabilidad de que salga cara es el triple de la probabilidad de cruz. Calcular ambas probabilidades.

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

Los frascos de mermelada tienen por lo general dos tipos de fallas: peso insuficiente o tapa no hermética. El 12 % contiene menos cantidad de la informada en la etiqueta, el 8 % tiene problemas con la tapa y el 3 % presenta ambas deficiencias. Los frascos en los que se detecta alguna de estas fallas son descartados. Hallar la probabilidad de que un frasco elegido al azar:

- a) tenga exactamente una falla.
- b) no sea descartado.

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

**Respuesta:**

- a) 0,14
- b) 0,83

</details>

---

### 6) Blanco cuadrado ⭐

Se dispone de un blanco cuadrado de 2,5 m de lado. Un dispositivo electrónico realiza disparos independientes que impactan en forma aleatoria en cualquier punto del cuadrado. Hallar la probabilidad de que:

- a) Un disparo impacte a menos de 1 m del centro del blanco.
- b) Un disparo impacte a menos de 1 m del centro pero a más de ½ m del centro del blanco.
- c) Si se hacen dos disparos, ambos caigan en el semiplano superior.
- d) Si se hacen dos disparos, los dos caigan en distinto cuadrante.

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

**Respuesta:**

- a) $\frac{4}{25}\pi$
- b) $\frac{3}{25}\pi$
- c) 1/4
- d) 3/4

</details>

---

### 7) Dado cargado

Se tiene un dado cargado tal que la probabilidad de cada número par es proporcional a ese número (con la misma constante de proporcionalidad en todos los casos) y las probabilidades de los números impares son las mismas que en un dado normal. Consideremos los eventos A = "número par", B = "divisor de 6" y C = "múltiplo de 5".

- a) Hallar la probabilidad de cada elemento del espacio muestral.
- b) Hallar P(A), P(A ∪ C), P(Aᶜ ∩ Bᶜ) y P(B − C).

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

**Respuesta:**

- a) P(1) = P(3) = P(5) = P(4) = 1/6, P(2) = 1/12, P(6) = 1/4.
- b) P(A) = 1/2, P(A∪C) = 2/3, P(Aᶜ∩Bᶜ) = 1/6, P(B − C) = 2/3.

</details>

---

### 8) Anteojos ⭐

Una clase consta de seis varones y diez mujeres. La tercera parte del primer grupo y la quinta parte del segundo usa anteojos. Hallar la probabilidad de que un alumno seleccionado al azar:

- a) use anteojos o sea mujer.
- b) sea varón y no use anteojos.

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

**Respuesta:**

- a) 3/4
- b) 1/4

</details>

---

### 9) Motores a inyección ⭐

Se eligen al azar tres motores de un conjunto de diez, entre los cuales cuatro son a inyección. Hallar la probabilidad de que:

- a) ninguno sea a inyección.
- b) a lo sumo uno sea a inyección.
- c) al menos dos sean a inyección.

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

Casos posibles: $\binom{10}{3} = 120$. Sea I = cantidad a inyección.

a) $P(I = 0) = \binom{6}{3}/120 = 20/120 = 1/6$. (Con el teorema de la multiplicación: $\frac6{10}\cdot\frac59\cdot\frac48 = \frac16$.)

b) $P(I = 1) = \binom41\binom62/120 = 60/120$ ⇒ $P(I \le 1) = (20 + 60)/120 = 2/3$.

c) $P(I \ge 2) = 1 - P(I \le 1) = 1/3$.

</details>

**Respuesta:**

- a) 1/6
- b) 2/3
- c) 1/3

</details>

---

### 10) Cumpleaños

Calcular la probabilidad de que en una reunión de ocho personas se encuentren al menos dos que cumplan años el mismo día. (Sugerencia: considerar un año de 365 días y ordenar a los individuos). ¿Y si son 23 personas?

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

Usando la propiedad P(A ∪ B) = P(A) + P(B) − P(A ∩ B), probar la fórmula:

$$P(A\cup B\cup C) = P(A)+P(B)+P(C)-P(A\cap B)-P(A\cap C)-P(B\cap C)+P(A\cap B\cap C)$$

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

Un estudio de la conducta después de una re-educación en leyes de tránsito de un gran número de infractores sugiere que la probabilidad de reincidencia dentro de los seis meses siguientes a la re-educación podría depender de los años de educación formal recibida por el individuo.

Las proporciones del número total de casos que caen dentro de las cuatro categorías de educación-reincidencia se presentan a continuación:

| Educación | Reincidente | No reincidente | Totales |
|---|---|---|---|
| 7 años o más | 0,10 | 0,30 | 0,40 |
| Menos de 7 años | 0,23 | 0,37 | 0,60 |
| Totales | 0,33 | 0,67 | 1,00 |

Supóngase que se selecciona al azar una única persona del programa de tratamiento. Sean los eventos:

- A: la persona seleccionada tiene siete años o más de educación.
- B: la persona seleccionada reincide dentro del período de los seis meses posteriores a la re-educación.

Se pide:

- a) Encontrar las probabilidades de los eventos A, B, A ∩ B y A/B.
- b) Encontrar las probabilidades de los eventos A ∪ B y (A ∪ B)ᶜ.
- c) ¿Resultaron independientes los eventos A y B?

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

a) Se leen los márgenes y la celda: P(A) = 0,40, P(B) = 0,33, P(A∩B) = 0,10. Luego $P(A/B) = \frac{0{,}10}{0{,}33} = \frac{10}{33} \approx 0{,}303$.

b) $P(A\cup B) = 0{,}40 + 0{,}33 - 0{,}10 = 0{,}63$ ⇒ $P((A\cup B)^c) = 0{,}37$ (es la celda "menos de 7 y no reincidente").

c) $P(A)P(B) = 0{,}132 \neq 0{,}10$ ⇒ no son independientes.

</details>

**Respuesta:**

- a) 0,4; 0,33; 0,1; 10/33
- b) 0,63 y 0,37
- c) No.

</details>

---

### 13) Traspaso entre oficinas

En una oficina Of₁ trabajan 3 mujeres y un varón, y en otra oficina Of₂ trabajan dos mujeres y dos varones. Se decidió transferir un empleado al azar de la primera oficina a la segunda. Si se selecciona, después de este traspaso, un empleado de la segunda oficina, ¿qué probabilidad hay de que sea mujer?

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

(T) Sean tres eventos A, B y C asociados a un espacio muestral Ω. Demostrar que:

- a) Si A no es imposible, entonces P(B / A) + P(Bᶜ / A) = 1.
- b) Si P(B / A) > P(B), entonces P(Bᶜ / A) < P(Bᶜ).
- c) Si C no es imposible, entonces P(A ∪ B / C) = P(A / C) + P(B / C) − P(A ∩ B / C).

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

### 15) Cubos entre dos cajas ⏭️

Una caja contiene 7 cubos azules y 3 verdes, y una segunda caja contiene 6 cubos azules y 4 verdes. Se elige al azar un cubo de la primera caja y se lo pone en la segunda caja. Luego se selecciona al azar un cubo de la segunda caja y se lo pone en la primera caja.

- a) Hallar la probabilidad de que durante el proceso se seleccione un cubo azul de la primera caja y un cubo verde de la segunda caja.
- b) Hallar la probabilidad de que al finalizar el proceso las cajas queden como estaban inicialmente.

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

**Respuesta:**

- a) 14/55
- b) 32/55

</details>

---

### 16) Independencia de a pares

Un dado equilibrado se arroja dos veces. Se definen los eventos:

- A: "el primer resultado es par"
- B: "el segundo resultado es par"
- C: "la suma de los resultados es par"

Se pide:

- a) Mostrar que los eventos A, B y C son independientes de a pares.
- b) Mostrar que los eventos A, B y C no son mutuamente independientes.

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

36 pares equiprobables. P(A) = P(B) = 18/36 = 1/2. C: la suma es par si los dos son pares o los dos son impares ⇒ 9 + 9 = 18 ⇒ P(C) = 1/2.

a) A∩B = ambos pares: 9/36 = 1/4 = ½·½. A∩C = 1.° par y suma par ⇒ 2.° par ⇒ es el mismo evento: 1/4. Lo mismo con B∩C. Son independientes de a pares.

b) A∩B∩C = A∩B (si los dos son pares, la suma es par) ⇒ 1/4 ≠ ⅛ = P(A)P(B)P(C).

</details>

**Respuesta:**

- a) Todas las intersecciones de a dos valen 1/4 = ½·½.
- b) P(A∩B∩C) = 1/4 ≠ 1/8 ⇒ no son mutuamente independientes.

</details>

---

### 17) Unión de independientes (T)

(T) Demostrar que si los eventos A, B y C son mutuamente independientes y no son imposibles, entonces:

$$P(A \cup B \cup C) = 1 - P(A^c)\cdot P(B^c)\cdot P(C^c)$$

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

Sean A y B dos eventos con probabilidad P(A) = 1/2, P(B) = 1/3 y P(B − A) = 1/12. Hallar P(A ∩ B) y P(Aᶜ / B).

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

### 19) P(B/A) en casos especiales ⭐

Calcular P(B / A) si:

- a) A es un subconjunto de B.
- b) A y B son incompatibles.

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

a) $A\subseteq B \Rightarrow A\cap B = A \Rightarrow P(B/A) = \frac{P(A)}{P(A)} = 1$ (siempre que ocurre A, ocurre B).

b) $A\cap B = \emptyset \Rightarrow P(B/A) = \frac{0}{P(A)} = 0$.

</details>

**Respuesta:**

- a) 1
- b) 0

</details>

---

### 20) Dos dados, suma ≥ 8 ⭐

Se lanza un dado dos veces. Hallar la probabilidad de que la suma de sus números sea mayor o igual que ocho si:

- a) aparece un cuatro en el primer dado.
- b) aparece un cuatro en, por lo menos, uno de los dados.

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

a) Si el primero es 4, hace falta que el segundo sea ≥ 4: {4, 5, 6} ⇒ 3/6 = 1/2.

b) Condición D = "al menos un 4": 6 + 6 − 1 = 11 pares ⇒ P(D) = 11/36.

Favorables (suma ≥ 8 y algún 4): (4,4), (4,5), (4,6), (5,4), (6,4) ⇒ 5/36 (el (4,4) se cuenta una sola vez).

$P = \frac{5/36}{11/36} = \frac5{11}$.

</details>

**Respuesta:**

- a) 1/2
- b) 5/11

</details>

---

### 21) Caminos bloqueados ⭐

Existen tres caminos de A hasta B y dos caminos de B hasta C, como se muestra en la figura. Cada uno de estos caminos está bloqueado con probabilidad 0,1 independientemente de los otros.

*(Figura: de A a B hay tres caminos, A₁ arriba, A₂ recto en el medio, que es el más corto, y A₃ abajo. De B a C hay dos caminos, B₁ arriba y B₂ abajo.)*

Hallar la probabilidad de que:

- a) exista algún camino abierto que permita llegar de A hasta C.
- b) cuando el camino más corto que une A con B está cerrado, se pueda llegar de C hasta A.

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

Cada camino está abierto con P = 0,9.

a) Hace falta (algún tramo A–B abierto) **y** (algún tramo B–C abierto). Por independencia, se multiplican, y cada "alguno" es 1 − "ninguno":

$[1 - 0{,}1^3]\cdot[1 - 0{,}1^2] = 0{,}999\cdot0{,}99 = 0{,}98901$.

b) A₂ está cerrado, así que quedan A₁ y A₃: $[1 - 0{,}1^2]\cdot[1 - 0{,}1^2] = 0{,}99^2 = 0{,}9801$.

</details>

**Respuesta:**

- a) 0,98901
- b) 0,9801

</details>

---

### 22) Urna sin reposición ⭐

Una urna tiene siete bolas rojas y tres blancas. Si se sacan tres bolas, una tras otra sin reposición, ¿cuál es la probabilidad de que:

- a) las dos primeras sean rojas y la tercera blanca?
- b) exactamente una sea blanca?

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

a) Regla de la multiplicación: $\frac7{10}\cdot\frac69\cdot\frac38 = \frac{126}{720} = \frac7{40}$.

b) La blanca puede salir en la 1.ª, la 2.ª o la 3.ª extracción (RRB, RBR, BRR). Cada orden tiene la misma probabilidad (7·6·3/720), así que $P = 3\cdot\frac7{40} = \frac{21}{40}$.

</details>

**Respuesta:**

- a) 7/40
- b) 21/40

</details>

---

### 23) Dos urnas, igual color ⏭️

Tenemos dos urnas A y B. En A hay tres bolas rojas y dos blancas, y en B dos rojas y cinco blancas. Se elige una urna al azar y de ella una bola que se coloca en la otra urna. Luego se saca una bola de la segunda urna. Hallar la probabilidad de que las bolas sacadas sean de igual color.

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

(T) Sean A y B sucesos de un espacio muestral Ω. Probar que:

- a) Si A y B son independientes, entonces son independientes A y Bᶜ (análogamente Aᶜ y B). Deducir que Aᶜ y Bᶜ también son independientes.
- b) Si los sucesos A y B son excluyentes (A ∩ B = ∅) y P(A)·P(B) > 0, entonces A y B **no** son independientes.

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

a) $P(A\cap B^c) = P(A) - P(A\cap B) = P(A) - P(A)P(B) = P(A)[1 - P(B)] = P(A)P(B^c)$.

Para los dos complementos: $P(A^c\cap B^c) = 1 - P(A\cup B) = 1 - P(A) - P(B) + P(A)P(B) = (1 - P(A))(1 - P(B)) = P(A^c)P(B^c)$.

b) $P(A\cap B) = P(\emptyset) = 0$, pero $P(A)P(B) > 0$ ⇒ no se cumple la definición de independencia.

</details>

**Respuesta:**

- a) Los pares de complementos heredan la independencia.
- b) Dos sucesos excluyentes con probabilidad positiva nunca son independientes.

</details>

---

### 25) Supervivencia

La probabilidad de que un hombre y una mujer vivan 10 años más, a partir de ahora, es 1/3 y 1/4 respectivamente. Suponiendo independencia entre ambas supervivencias, calcular la probabilidad de que:

- a) ambos estén vivos dentro de diez años.
- b) al menos uno de ellos esté vivo dentro de diez años.
- c) ninguno esté vivo dentro de diez años.
- d) sólo la mujer esté viva dentro de diez años.

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

a) $\frac13\cdot\frac14 = \frac1{12}$

b) $\frac13 + \frac14 - \frac1{12} = \frac12$

c) $\frac23\cdot\frac34 = \frac12$ (= 1 − b)

d) $\frac14\cdot\frac23 = \frac16$

</details>

**Respuesta:**

- a) 1/12
- b) 1/2
- c) 1/2
- d) 1/6

</details>

---

### 26) Cajoneras ⭐

Se tienen tres cajoneras idénticas; cada cajonera, a su vez, tiene dos cajones. En una de las cajoneras hay una moneda de plata en cada cajón, en otra hay una de plata en un cajón y una de oro en el otro, mientras que en la última hay una de oro en cada cajón. Se elige una cajonera al azar y de ésta se saca una moneda de uno de los cajones. Si la moneda es de oro, ¿cuál es la probabilidad de que en el otro cajón haya una moneda de oro?

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

### 27) Test diagnóstico ⭐

Uno de cada 25 adultos de cierta población está afectado de una enfermedad para la cual se ha desarrollado una prueba diagnóstica. La prueba es tal que, cuando un individuo padece la enfermedad, el resultado de la prueba es positivo en un 98 % de las veces, mientras que un individuo sano tendrá un resultado positivo solamente el 3 % de las veces. Eligiendo un individuo al azar de esta población:

- a) Hallar la probabilidad de que el test dé positivo.
- b) Hallar la probabilidad de que realmente padezca la enfermedad, sabiendo que el resultado de la prueba fue positivo.
- c) Hallar la probabilidad de que realmente esté sano, sabiendo que el resultado de la prueba fue negativo.

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

E = enfermo: P(E) = 0,04, P(Eᶜ) = 0,96. P(+/E) = 0,98, P(+/Eᶜ) = 0,03.

a) Probabilidad total: $0{,}04\cdot0{,}98 + 0{,}96\cdot0{,}03 = 0{,}0392 + 0{,}0288 = 0{,}068$.

b) Bayes: $\frac{0{,}0392}{0{,}068} = 0{,}5765$ (sube de 4 % a priori a 58 % a posteriori).

c) $P(-) = 0{,}932$ y $P(E^c\cap -) = 0{,}96\cdot0{,}97 = 0{,}9312$ ⇒ $\frac{0{,}9312}{0{,}932} = 0{,}9991$.

</details>

**Respuesta:**

- a) 0,068
- b) 0,5765
- c) 0,9991

</details>

---

### 28) Un artículo de cada caja ⭐

La caja A contiene 8 artículos de los cuales 3 son defectuosos, la caja B contiene 5 artículos de los cuales 2 son defectuosos y la caja C contiene 10 artículos de los cuales 4 son defectuosos. Se extrae al azar un artículo de cada caja.

- a) ¿Cuál es la probabilidad de que todos los artículos seleccionados sean defectuosos?
- b) ¿Cuál es la probabilidad de que sólo un artículo de los seleccionados sea defectuoso?
- c) Si un solo artículo es defectuoso, ¿cuál es la probabilidad de que el artículo defectuoso proceda de la caja A?

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

**Respuesta:**

- a) 3/50
- b) 87/200
- c) 9/29

</details>

---

### 29) Deporte ⭐

En cierta facultad, el 40 % de los hombres y el 55 % de las mujeres practican deporte. Además, el 70 % de los estudiantes son mujeres. Si se elige un estudiante al azar y hace deporte, ¿cuál es la probabilidad de que sea mujer?

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

### 30) Aerolíneas Cordobesas ⭐

De los pasajeros que viajan en Aerolíneas Cordobesas, el 30 % viaja con familia, el 25 % con amigos y el resto solos. De los que viajan con familia, la mitad lo hace en vuelos nocturnos; de los que viajan con amigos, el 70 % lo hace en vuelos nocturnos, y de los que viajan solos, apenas el 25 % lo hace en vuelos nocturnos.

- a) Si se selecciona un pasajero al azar de Aerolíneas Cordobesas, hallar la probabilidad de que no viaje en vuelo nocturno.
- b) Si viaja en vuelo nocturno, hallar la probabilidad de que viaje con amigos.

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

P(S) = 1 − 0,30 − 0,25 = 0,45.

a) $P(N) = 0{,}3\cdot0{,}5 + 0{,}25\cdot0{,}7 + 0{,}45\cdot0{,}25 = 0{,}15 + 0{,}175 + 0{,}1125 = 0{,}4375$ ⇒ $P(\bar N) = 0{,}5625$.

b) $P(A/N) = \frac{0{,}175}{0{,}4375} = 0{,}4$.

</details>

**Respuesta:**

- a) 0,5625
- b) 0,4

</details>

---

### 31) Comisión de docentes

El Departamento de Ciencias Básicas de la Universidad tiene seis docentes titulares de Matemática: Euler, Cauchy, Leibnitz, Laplace, Gauss y Euclides, y debe seleccionar a tres docentes titulares de esta área para integrar una comisión de revisión de contenidos. Debido a que el trabajo será tedioso, nadie desea hacerlo; luego se eligen los nombres de una urna al azar.

- a) Hallar la probabilidad de que alguno de los seleccionados tenga un apellido que comience con L.
- b) Si dos de los seleccionados tienen la misma inicial del apellido, ¿cuál es la probabilidad de que sea la L?
- c) Si las antigüedades docentes de los miembros titulares son respectivamente 12, 15, 9, 16, 20 y 7 años, hallar la probabilidad de que la suma de antigüedades de dos de estos miembros elegidos al azar resulte:
  1. 27 años.
  2. mayor a 30 años.

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

**Respuesta:**

- a) 0,8
- b) 1/2
- c) 1) 2/15 2) 4/15

</details>

---

## Actividades del aula virtual

### Introducción (parte 1) — 1) Bolitas de colores

Se tienen 10 bolitas verdes, 4 rojas, 8 azules y 3 blancas. Si se toma una bolita al azar, calculá la probabilidad de que la obtenida:

- a) sea roja.
- b) sea verde o azul.
- c) no sea blanca.
- d) no sea roja ni sea azul.

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

**Respuesta:**

- a) 0,16
- b) 0,72
- c) 0,88
- d) 0,52

</details>

---

### Introducción (parte 1) — 2) Cartones

Hay diez cartones rojos numerados del 1 al 10 y quince verdes numerados del 11 al 25.

- a) Se saca un cartón al azar: calculá la probabilidad de que sea verde.
- b) Se saca un cartón al azar: calculá la probabilidad de que sea menor a 20.
- c) Se saca un cartón al azar: calculá la probabilidad de que sea rojo y par.
- d) Se saca un cartón al azar: calculá la probabilidad de que sea rojo o par.
- e) Se saca un cartón al azar: calculá la probabilidad de que no sea verde ni impar.
- f) Se saca un cartón al azar entre los verdes. Calculá la probabilidad de que sea impar.
- g) Se saca un cartón al azar entre los impares. Calculá la probabilidad de que sea verde.

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

**Respuesta:**

- a) 3/5
- b) 19/25
- c) 1/5
- d) 17/25
- e) 1/5
- f) 8/15
- g) 8/13

</details>

---

### Introducción (parte 1) — 3) Envases de bebida

Una consultora de marketing relevó la preferencia de hombres y mujeres respecto de los envases de cierta bebida mediante una encuesta en los supermercados. Los datos se volcaron en la siguiente tabla:

| | A | B |
|---|---|---|
| Hombre | 25 | 40 |
| Mujer | 35 | 50 |

- a) Calculá la probabilidad de que un encuestado sea hombre.
- b) Calculá la probabilidad de que un encuestado haya preferido el envase B.
- c) Calculá la probabilidad de que un encuestado sea hombre y haya preferido el envase B.
- d) Se elige un encuestado al azar y resulta ser hombre: calculá la probabilidad de que haya elegido el envase B.
- e) Para presentar un informe hicieron dos tablas de valores porcentuales: una donde cada **fila** suma 100 % y otra donde cada **columna** suma 100 %. Completalas y explicá el significado del valor en la celda sombreada (Hombre, B) de cada tabla.

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

**Respuesta:**

- a) 0,433
- b) 0,6
- c) 0,267
- d) 0,615
- e) 61,5 % = P(B/H) y 44,4 % = P(H/B)

</details>

---

### Introducción (parte 1) — 4), 5) y 6)

4) En una fábrica se hacen artículos que pueden tener dos tipos de fallas. El 10 % tiene sólo la falla A, el 20 % sólo la falla B y el 55 % no tiene fallas. ¿Cuál es la probabilidad de que una pieza tenga las dos fallas?

5) En un curso, el 70 % de los estudiantes es de ingeniería mecánica. Entre los estudiantes de ingeniería mecánica, el 10 % desaprueba la materia. ¿Cuál es la probabilidad de que un estudiante elegido al azar sea de mecánica y desapruebe la materia?

6) En una empresa se fabrica en dos plantas, M y N. Luego la producción se guarda en un depósito sin registrar la planta de origen. En la planta M hacen el 60 % de la producción. El 10 % de lo que hacen en M está fallado; lo mismo ocurre con el 5 % de lo que fabrican en N. Se toma un artículo al azar: calculá la probabilidad de que esté fallado.

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

Observen el diagrama en el que se representa el espacio muestral asociado a un experimento aleatorio y los sucesos A y B. Las probabilidades de cada región son:

- sólo A (A sin B): 0,20
- A ∩ B: 0,30
- sólo B (B sin A): 0,10
- fuera de A y de B: 0,40

Calculen:

- a) P(A)
- b) P(B ∩ Aᶜ)
- c) P(A ∪ B)
- d) P(B / A)
- e) P(Aᶜ / B)

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

**Respuesta:**

- a) 0,5
- b) 0,1
- c) 0,6
- d) 0,6
- e) 0,25

</details>

---

### Introducción (parte 2) — 2) Dos fallas

Un artículo puede tener dos tipos de fallas. El 30 % tiene la falla A, el 20 % la falla B y el 65 % no tiene fallas.

- a) Calcular la probabilidad de que un artículo elegido al azar tenga ambas fallas.
- b) Calcular la probabilidad de que un artículo elegido al azar tenga una sola falla.
- c) Calcular la probabilidad de que un artículo elegido al azar esté fallado.
- d) Calcular la probabilidad de que un artículo elegido al azar entre los que tienen la falla A tenga también la falla B.
- e) Calcular la probabilidad de que un artículo elegido al azar entre los que no tienen la falla B tenga la falla A.

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

**Respuesta:**

- a) 0,15
- b) 0,20
- c) 0,35
- d) 0,5
- e) 0,1875

</details>

---

### Introducción (parte 2) — 3) Divisiones de PyE

En Probabilidad y Estadística hay 3 divisiones, A, B y C, que tienen el 25 %, 35 % y 40 % de los estudiantes respectivamente. En la división A hay un 20 % de desaprobados, y lo mismo ocurre con el 30 % de los estudiantes de B y el 25 % de los de C.

- a) Hallar la probabilidad de que un estudiante elegido al azar esté desaprobado.
- b) Hallar la probabilidad de que, si se elige un estudiante y resulta ser desaprobado, sea del curso C.

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

a) $0{,}25\cdot0{,}2 + 0{,}35\cdot0{,}3 + 0{,}4\cdot0{,}25 = 0{,}05 + 0{,}105 + 0{,}1 = 0{,}255$

b) Bayes: $0{,}1/0{,}255 \approx 0{,}392$

</details>

**Respuesta:**

- a) 0,255
- b) ≈ 0,392

</details>

---

### Introducción (parte 2) — 5) y 6) Árbol de 3 extracciones

(Contexto, actividad 4.) En una caja hay 4 bolitas negras y 3 blancas y se extraen 3 bolitas, una tras otra y sin reponer. Los resultados posibles y sus probabilidades se pueden representar en un diagrama de árbol. Por ejemplo, la probabilidad de que salgan todas blancas es:

$$P(B_1 \cap B_2 \cap B_3) = \frac37\cdot\frac26\cdot\frac15 = \frac1{35}$$

5) Utilicen el diagrama de árbol para calcular:

- a) P(B₁ ∩ N₂ ∩ B₃)
- b) la probabilidad de que las tres sean negras.
- c) la probabilidad de que salgan dos negras.

6) Construyan un diagrama de árbol con las características del anterior, pero considerando que las extracciones se hacen **con reposición** (se saca una bolita, se mira el color y se vuelve a poner en la caja), y luego calculen las probabilidades de la actividad 5.

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

Según los registros de Salud Pública de una ciudad, los porcentajes de los tipos de sangre A, B, O y AB son, respectivamente, 40 %, 20 %, 30 % y 10 %. Si se eligen dos personas al azar de esa ciudad y asumiendo independencia, calculen la probabilidad de que:

- a) ambas personas sean del tipo A.
- b) ninguna de ellas sea del tipo A.
- c) una sea del tipo A y la otra del tipo O.
- d) alguna sea del tipo AB.
- e) tengan el mismo tipo de sangre.
- f) tengan distinto tipo de sangre.

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

**Respuesta:**

- a) 0,16
- b) 0,36
- c) 0,24
- d) 0,19
- e) 0,30
- f) 0,70

</details>

---

### Introducción (parte 2) — 8) Equipo de fútbol

Un equipo de fútbol gana con probabilidad 0,6, pierde con probabilidad 0,3 y empata con probabilidad 0,1.

- a) Si juega tres partidos durante un mes, hallar la probabilidad de que gane el primero, pierda el segundo y empate el tercero.
- b) Si juega tres partidos durante un mes, hallar la probabilidad de que gane uno de ellos, pierda otro y empate el restante.
- c) Si juega tres partidos durante un mes, hallar la probabilidad de que gane 2 de ellos.

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

a) $0{,}6\cdot0{,}3\cdot0{,}1 = 0{,}018$

b) hay $3! = 6$ órdenes ⇒ $0{,}108$

c) exactamente 2 victorias: $\binom32 0{,}6^2\cdot0{,}4 = 0{,}432$

</details>

**Respuesta:**

- a) 0,018
- b) 0,108
- c) 0,432

</details>

---

### Introducción (parte 2) — 9) Pozos de agua

En la búsqueda de agua, se encuentra un pozo potable con probabilidad 0,1.

- a) Calcular la probabilidad de tener que hacer dos pozos para hallar uno potable.
- b) Calcular la probabilidad de tener que hacer 10 pozos para encontrar uno potable.
- c) Calcular la probabilidad de tener que hacer n pozos para encontrar uno potable.

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

Hace falta que los n − 1 anteriores fallen (0,9 cada uno) y que el n-ésimo sea potable:

a) $0{,}9\cdot0{,}1 = 0{,}09$

b) $0{,}9^9\cdot0{,}1 \approx 0{,}0387$

c) $0{,}9^{n-1}\cdot0{,}1$

</details>

**Respuesta:**

- a) 0,09
- b) ≈ 0,0387
- c) $0{,}9^{n-1}\cdot0{,}1$

</details>

---

### Introducción (parte 2) — 10) Supermercado

En un supermercado, el 90 % de los clientes compra comestibles, el 70 % compra artículos de tocador y limpieza y el 20 % compra electrodomésticos. Calculen la probabilidad de que el próximo cliente que pase por una caja compre:

- a) los tres tipos de artículos.
- b) ninguno de los tres tipos de artículos.
- c) alguno de los tres tipos de artículos.
- d) al menos dos de los tres tipos de artículos.

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

**Respuesta (suponiendo independencia):**

- a) 0,126
- b) 0,024
- c) 0,976
- d) 0,698

</details>

---

### Clase de repaso — Ej. 1) Cursos del turno noche

La UTN posee tres cursos de Probabilidad y Estadística en el turno noche. El primero tiene 35 estudiantes, de los cuales 3 no poseen trabajo; el segundo curso consta de 25 estudiantes, de los cuales 5 no tienen trabajo, mientras que el tercero está compuesto por 18 estudiantes, de los cuales 4 no tienen trabajo.

- a) Si se elige al azar un alumno del turno noche, calcular la probabilidad de que:
  1. no tenga trabajo.
  2. no tenga trabajo, si se sabe que es del primer curso.
  3. si tiene trabajo, sea del tercer curso.
- b) Si se seleccionan cuatro estudiantes al azar del turno noche, ¿cuál es la probabilidad de que dos no tengan trabajo y dos sí?

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

Total 78; no trabajan 12; trabajan 66 (32, 20 y 14).

a) 1) 12/78 2) 3/35 3) 14/66

b) Con la aproximación de independencia que usa la resolución del aula: P(T) = 11/13 y P(T̄) = 2/13. Hay $\binom42 = 6$ órdenes ⇒ $6\left(\frac{11}{13}\right)^2\left(\frac2{13}\right)^2 \approx 0{,}102$.

(Sin reposición exacta: $\binom{12}{2}\binom{66}{2}/\binom{78}{4} \approx 0{,}0992$.)

</details>

**Respuesta:**

- a) 12/78 ≈ 0,154; 3/35; 14/66 ≈ 0,212
- b) ≈ 0,102

</details>

---

### Clase de repaso — Ej. 2) a 8)

**Ej. 2)** Se arroja una moneda equilibrada y luego un dado. Las probabilidades de los números obtenidos en el dado dependen de lo que salió en la moneda, de manera tal que, si salió cara, la probabilidad de obtener un número par con el dado es 1/4. Calcular la probabilidad de que en una tirada se obtenga cara y un número impar.

**Ej. 3)** La perfumería Lanis SA recibe lotes de mercadería de tres proveedores en proporciones 10 %, 30 % y 60 %. Se sabe que el 2 % de los lotes del primer proveedor, el 0,4 % de los del segundo y el 0,2 % de los del tercero son rechazados en el control de calidad que realiza Lanis SA.

- a) ¿Cuál es la probabilidad de que un lote de mercadería sea rechazado?
- b) Hallar la probabilidad de que un lote provenga del tercer proveedor, sabiendo que fue rechazado.

**Ej. 4)** Una cerradura de combinación consta de 3 discos sobre un eje. Cada disco está dividido en 6 sectores independientes, con un dígito del 0 al 5 en cada sector.

- a) Una puerta posee una única cerradura que se abre cuando en los discos se dispone un número que comience con 3 y sea par. Calcular la probabilidad de que la cerradura pueda abrirse.
- b) Ahora a la puerta se le agrega una segunda cerradura, la cual se abre, de manera independiente de la primera, si en los discos figura el número 153. ¿Cuál es la probabilidad de abrir la puerta, si esto se logra cuando al menos una de las cerraduras se abre?

**Ej. 5)** Dados A y B, deducir cómo queda expresada la P(A / B) si:

- a) A es un subconjunto de B.
- b) A y B son independientes.

**Ej. 6)** Dados tres eventos A, B y C, no imposibles, demostrar que P(A ∪ C / B) = P(A / B) + P(C / B) − P(A ∩ C / B).

**Ej. 7)** Dados dos sucesos A y B:

- a) ¿Cuándo A y B son incompatibles? ¿Y cuándo serán independientes?
- b) Si P(A ∩ B) = 0, P(A) = 0,5 y P(B) = 0,3, ¿son A y B sucesos complementarios? ¿Por qué?

**Ej. 8)** Sean A, B, C y D cuatro sucesos de un espacio muestral S, de los cuales se conocen las probabilidades P(A), P(B) y P(C) y las probabilidades condicionales P(D / A), P(D / B) y P(D / C). ¿Qué condiciones tienen que cumplir los sucesos A, B y C para aplicar la fórmula del Teorema de Probabilidad Total para calcular la P(D)? ¿Cómo quedaría expresada en este caso?

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

**Respuesta:**

- Ej. 2) 3/8
- Ej. 3) a) 0,0044 b) ≈ 0,273
- Ej. 4) a) 1/12 b) ≈ 0,0876
- Ej. 5) a) P(A)/P(B) b) P(A)
- Ej. 6) queda demostrado (igual que el Ej. 14 c de la guía).
- Ej. 7) incompatibles: A ∩ B = ∅; independientes: P(A ∩ B) = P(A)·P(B). No son complementarios.
- Ej. 8) A, B y C tienen que formar una partición de S.

</details>

---

### Ejercicios teóricos del aula — 2) y 5)

**2)** Sean los sucesos A, B ⊆ S tales que A ≠ ∅ y B ≠ ∅. Probar que:

- a) Si A y B son mutuamente excluyentes, entonces no son independientes.
- b) Si A y B son independientes, entonces no son mutuamente excluyentes.

**5)** Sean los sucesos A, B ⊆ S tales que B ≠ ∅. Probar que P(A / B) + P(Aᶜ / B) = 1.

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

---

[← Volver al menú principal](../README.md)
