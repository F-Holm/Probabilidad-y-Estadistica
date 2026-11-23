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

💡 **Qué es un experimento aleatorio.** Es algo que se puede repetir y cuyo resultado no se sabe de antemano: tirar una moneda, elegir un artículo, medir un tiempo.

💡 **Qué es el espacio muestral (S o Ω).** Es la **lista de todos los resultados posibles** del experimento. Para armarla sin olvidarse ninguno, conviene pensar el experimento como una **secuencia de etapas** y anotar qué puede pasar en cada una. Si el orden de las etapas importa, (N, D) y (D, N) son resultados distintos.

- a) Hay una sola etapa con dos resultados posibles: la molécula **está** o **no está**.
- b) Hay dos etapas (primer artículo, segundo artículo), y cada una puede dar N (normal) o D (defectuoso). Como se eligen **uno después del otro**, el orden importa: ND (el primero normal y el segundo defectuoso) no es lo mismo que DN. En total hay 2 · 2 = 4 pares.
- c) Se tira **hasta que sale cara**. Puede salir en la 1.ª tirada (C), en la 2.ª (antes una cruz: XC), en la 3.ª (XXC), y así sin fin. Es un conjunto **infinito**, pero se pueden numerar sus elementos (se dice "infinito numerable").
- d) Hay dos etapas: primer billete y segundo billete.
  - **Sin reposición:** el billete sacado no vuelve, así que no se puede repetir. Hay 3 opciones para el primero y 2 para el segundo: 3 · 2 = 6 pares.
  - **Con reposición:** el billete vuelve a la billetera, así que se puede repetir: 3 · 3 = 9 pares.
- e) El experimento **se corta** en cuanto aparece la 2.ª blanca (B), o al llegar a 4 extracciones. Se ordena por cantidad de extracciones:
  - Con 2 extracciones: BB (ya salieron las dos blancas).
  - Con 3: la 3.ª tiene que ser la 2.ª blanca, así que entre las dos primeras hay exactamente una B: NBB, BNB.
  - Con 4: o la 4.ª es la 2.ª blanca (NNBB, NBNB, BNNB), o se llega a la 4.ª sin haber juntado 2 blancas (BNNN, NBNN, NNBN, NNNB, NNNN).
- f) Un tiempo puede tomar **cualquier valor** entre 0 y 60 minutos, incluidos los decimales. Es un intervalo de números reales (espacio muestral **continuo**).

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

💡 **Qué es un evento (o suceso).** Es un **subconjunto** del espacio muestral: el grupo de resultados que cumplen una condición. "Describir por extensión" significa escribir la lista de esos resultados.

Del ejercicio 1 b), $S = \{NN, ND, DN, DD\}$, donde la primera letra es el primer artículo. Se revisa cada resultado y se ve si cumple la condición:
- A (el primero es D) = {DN, DD}
- B (al menos un D, es decir uno o dos) = {ND, DN, DD}
- C (los dos D) = {DD}

💡 **Vocabulario que se usa en las proposiciones:**
- $A \subseteq B$ ("A está incluido en B"): todo resultado de A también está en B. Dicho de otro modo, si ocurre A, seguro ocurre B.
- $A \cap B$ (intersección, "A y B"): los resultados que están en los dos.
- $A^c$ o $\bar A$ (complemento, "no A"): los resultados de S que **no** están en A.
- **Evento imposible** (∅): el que no tiene ningún resultado. **Evento cierto**: S entero, que siempre ocurre.
- **Incompatibles** (o mutuamente excluyentes, M.E.): no pueden ocurrir a la vez, es decir $A \cap B = \emptyset$.

a) Los dos resultados de A (DN y DD) están en B, así que A ⊆ B: **V**. Tiene sentido: si el primero es defectuoso, seguro hay al menos un defectuoso.

b) El único resultado de C es DD, y DD está en A: **V**.

c) $A \cap C = \{DD\}$, que **no** está vacío. Entonces no es imposible: **F**.

d) Al imposible le falta todo S, así que su complemento es S entero, el evento cierto: **V**.

e) $B^c$ = "ningún defectuoso" = {NN}. No tiene nada en común con A = {DN, DD}: $A \cap B^c = \emptyset$, así que son incompatibles: **V**.

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

a) Se arma un **árbol**: en cada tirada salen dos ramas (C o X). Con 3 tiradas quedan $2\cdot2\cdot2 = 2^3 = 8$ caminos, y cada camino es una terna:

```
        ┌ C ─ CCC          ┌ C ─ XCC
    ┌ C ┤             ┌ C ┤
    │   └ X ─ CCX     │   └ X ─ XCX
 C ─┤                X ─┤
    │   ┌ C ─ CXC     │   ┌ C ─ XXC
    └ X ┤             └ X ┤
        └ X ─ CXX         └ X ─ XXX
```

b) "Equilibrada" significa que cada cara sale con probabilidad ½. Las tiradas no se influyen entre sí (son **independientes**), y en ese caso la probabilidad de un camino del árbol es el **producto** de sus ramas: $\frac12\cdot\frac12\cdot\frac12 = \frac18$.

💡 **Espacio equiprobable:** todos los resultados tienen la misma probabilidad. Acá sí: los 8 valen ⅛.

c) A = "exactamente una cara": CXX, XCX, XXC. B = "al menos una cara" (una, dos o tres): son todas las ternas menos XXX.

d) 💡 **Regla de Laplace:** si el espacio es equiprobable, $P(\text{evento}) = \frac{\text{casos favorables}}{\text{casos posibles}}$. Entonces $P(A) = \frac38$ y $P(B) = \frac78$.

💡 **Unión** $A \cup B$ ("A o B"): los resultados que están en al menos uno de los dos.

Todos los resultados de A están en B ($A \subseteq B$). Por eso:
- la intersección es A misma: $P(A \cap B) = P(A) = \frac38$;
- la unión es B misma: $P(A \cup B) = P(B) = \frac78$.

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

La moneda está cargada, así que **no** se puede usar Laplace (cara y cruz no son igual de probables). Se plantea una ecuación.

**Incógnita:** se llama $q = P(X)$, la probabilidad de cruz. "Cara es el triple de cruz" se escribe $P(C) = 3q$.

💡 **Las probabilidades de todos los resultados posibles suman 1** (siempre sale algo). C y X son los únicos dos resultados, así que:

$$P(C) + P(X) = 1 \;\Rightarrow\; 3q + q = 1 \;\Rightarrow\; 4q = 1 \;\Rightarrow\; q = \frac14$$

Entonces $P(X) = \frac14$ y $P(C) = 3\cdot\frac14 = \frac34$. Control: suman 1 ✓.

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

**Paso 1, ponerle nombre a cada cosa.** A = "peso insuficiente", B = "tapa no hermética". Los datos son $P(A) = 0{,}12$, $P(B) = 0{,}08$ y $P(A \cap B) = 0{,}03$ (las dos fallas a la vez).

**Paso 2, un diagrama de Venn.** Ojo: el 12 % de A **incluye** al 3 % que tiene las dos fallas. Se separa en regiones que no se pisan:

```
   ┌──────────── S ─────────────┐
   │   ┌─── A ───┐              │
   │   │  sólo A ┌┼──── B ───┐  │
   │   │  0,09   │ 0,03 sólo B│  │
   │   └─────────┼┘     0,05  │  │
   │             └────────────┘  │
   │     ninguna falla: 0,83     │
   └─────────────────────────────┘
```
- Sólo A: $P(A \cap \bar B) = 0{,}12 - 0{,}03 = 0{,}09$.
- Sólo B: $P(\bar A \cap B) = 0{,}08 - 0{,}03 = 0{,}05$.

**a) Exactamente una falla** es "sólo A" o "sólo B". Son regiones separadas, así que se suman: $0{,}09 + 0{,}05 = 0{,}14$.

**b) "No descartado"** significa que no tiene ninguna falla. Conviene calcular lo contrario, "tiene alguna falla", que es la **unión** $A \cup B$.

💡 **Regla de la unión:** $P(A \cup B) = P(A) + P(B) - P(A \cap B)$. Se resta la intersección porque, al sumar P(A) y P(B), la zona común se contó dos veces. 📄 **H1** trae la versión de tres eventos; con dos se tacha todo lo que tiene C.

$$P(A \cup B) = 0{,}12 + 0{,}08 - 0{,}03 = 0{,}17$$

💡 **Complemento:** $P(\bar E) = 1 - P(E)$. "Ninguna falla" es el complemento de "alguna falla":

$$P(\bar A \cap \bar B) = 1 - 0{,}17 = 0{,}83$$

Control: las cuatro regiones del Venn suman $0{,}09 + 0{,}03 + 0{,}05 + 0{,}83 = 1$ ✓.

Extra (de la resolución del aula virtual; usa conceptos que se explican más adelante, en los ejercicios 12 y 16):
- Probabilidad condicional, 📄 H1 $P(B/A) = \frac{P(A\cap B)}{P(A)}$: entre los frascos con poco peso, ¿qué fracción tiene además mala la tapa? $0{,}03/0{,}12 = 0{,}25$.
- $P(A/\bar B) = \frac{P(A \cap \bar B)}{P(\bar B)} = \frac{0{,}09}{0{,}92} \approx 0{,}098$.
- Independencia, 📄 H1 $P(A\cap B) = P(A)P(B)$: $0{,}12\cdot0{,}08 = 0{,}0096 \neq 0{,}03$, así que A y B **no** son independientes.

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

💡 **Probabilidad geométrica.** Si el disparo puede caer en **cualquier punto** del cuadrado con la misma chance, no se pueden contar "casos" (hay infinitos puntos). En su lugar se comparan **áreas**: es la misma idea que Laplace, pero midiendo.

$$P = \frac{\text{área favorable}}{\text{área total}}, \qquad \text{área total} = 2{,}5^2 = 6{,}25 \text{ m}^2$$

**a)** "A menos de 1 m del centro" es un círculo de radio 1 alrededor del centro. Entra entero en el cuadrado, porque del centro al borde hay 1,25 m. Área $= \pi r^2 = \pi$:
$$P = \frac{\pi}{6{,}25} = \frac{4}{25}\pi \approx 0{,}503$$

**b)** "Entre ½ m y 1 m del centro" es una **corona** (un anillo): el círculo grande menos el chico.
$$P = \frac{\pi\cdot1^2 - \pi\cdot(\frac12)^2}{6{,}25} = \frac{\frac34\pi}{6{,}25} = \frac{3}{25}\pi \approx 0{,}377$$

**c)** Un disparo cae en la mitad de arriba con probabilidad ½: es la mitad del área.

💡 **Independencia:** los disparos no se influyen entre sí. Cuando dos eventos son independientes, la probabilidad de que ocurran **los dos** es el **producto** (📄 H1, $P(A\cap B) = P(A)P(B)$):
$$P(\text{ambos arriba}) = \frac12\cdot\frac12 = \frac14$$

**d)** Cada cuadrante es ¼ del área, así que cada disparo cae en un cuadrante dado con probabilidad ¼.

Es más fácil calcular lo contrario, "los dos en el **mismo** cuadrante". Puede ser el cuadrante 1, el 2, el 3 o el 4 (4 casos que no se pisan), y cada uno vale $\frac14\cdot\frac14$:
$$P(\text{mismo}) = 4\cdot\frac14\cdot\frac14 = \frac14 \;\Rightarrow\; P(\text{distinto}) = 1 - \frac14 = \frac34$$

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

**a) Traducir el enunciado a ecuaciones.**
- Impares "como en un dado normal": P(1) = P(3) = P(5) = 1/6.
- "La probabilidad de cada par es **proporcional** a ese número" significa que es el número multiplicado por una misma constante k: P(2) = 2k, P(4) = 4k, P(6) = 6k.

💡 Las probabilidades de todos los resultados suman 1:
$$\underbrace{3\cdot\frac16}_{\text{impares}} + \underbrace{2k + 4k + 6k}_{\text{pares}} = 1 \;\Rightarrow\; \frac12 + 12k = 1 \;\Rightarrow\; k = \frac1{24}$$

Entonces P(2) = 2/24 = 1/12, P(4) = 4/24 = 1/6 y P(6) = 6/24 = 1/4.

**b)** Primero se escribe cada evento como lista: A = {2, 4, 6}, B (divisores de 6) = {1, 2, 3, 6}, C (múltiplos de 5) = {5}.

⚠️ **No** se puede usar Laplace (favorables/posibles), porque los resultados no son igual de probables. La probabilidad de un evento es la **suma de las probabilidades de sus resultados**.

- $P(A) = \frac1{12} + \frac16 + \frac14 = \frac12$. También sale como $1 - P(\text{impar}) = 1 - \frac36$.
- **A ∪ C:** A y C no tienen resultados en común (son mutuamente excluyentes), así que la unión es la suma: $\frac12 + \frac16 = \frac23$.
- **$A^c \cap B^c$** = "ni par ni divisor de 6". Por **De Morgan** ("ni A ni B" es lo contrario de "A o B"), es $\overline{A \cup B}$. $A \cup B = \{1, 2, 3, 4, 6\}$, y lo que falta es {5}: probabilidad $\frac16$.
- **B − C** ("B pero no C") $= B \cap C^c$. B no tiene al 5, así que B − C es B entera: $\frac16 + \frac1{12} + \frac16 + \frac14 = \frac23$.

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

💡 **Tabla de contingencia.** Cuando cada persona se clasifica según **dos** características (sexo y anteojos), conviene armar una tabla con todas las combinaciones. Después todo se calcula leyendo celdas.

- "La tercera parte del primer grupo usa anteojos": varones con anteojos = 6/3 = 2.
- "La quinta parte del segundo": mujeres con anteojos = 10/5 = 2.
- El resto de cada fila sale por resta.

| | A (anteojos) | $\bar A$ (sin anteojos) | Total |
|---|---|---|---|
| M (mujer) | 2 | 8 | 10 |
| V (varón) | 2 | 4 | 6 |
| Total | 4 | 12 | 16 |

Se elige uno de 16 alumnos, todos con la misma chance, así que vale Laplace: casos favorables / 16.

**a) "Use anteojos o sea mujer"** es una unión. 💡 $P(A \cup M) = P(A) + P(M) - P(A \cap M)$: se resta la intersección porque las 2 mujeres con anteojos se contaron en los dos grupos (📄 H1, versión de 3 eventos).
$$P(A \cup M) = \frac{4}{16} + \frac{10}{16} - \frac{2}{16} = \frac{12}{16} = \frac34$$
Contando directo: todas las mujeres (10) más los varones con anteojos (2) son 12.

**b) "Varón y sin anteojos"** es una celda de la tabla: $\frac{4}{16} = \frac14$. Es justo lo que queda afuera de a): $1 - \frac34$.

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

Se eligen 3 motores **a la vez** de 10, sin importar el orden. Todos los grupos de 3 tienen la misma chance, así que vale Laplace. Hay que **contar** grupos.

💡 **Número combinatorio** $\binom{n}{k}$ ("n tomados de a k"): cuántos grupos distintos de k elementos se pueden armar con n, sin importar el orden. $\binom nk = \frac{n!}{k!(n-k)!}$. En la calculadora es la tecla nCr.

**Casos posibles:** $\binom{10}{3} = 120$ grupos. Hay 4 motores a inyección y 6 que no. Sea I = cantidad a inyección en el grupo.

**a) Ninguno a inyección:** los 3 salen de los 6 comunes, $\binom63 = 20$ grupos.
$$P(I = 0) = \frac{20}{120} = \frac16$$
Otra forma, uno por uno (regla de la multiplicación): el 1.º es común con prob. 6/10, el 2.º con 5/9 (queda uno menos), el 3.º con 4/8: $\frac6{10}\cdot\frac59\cdot\frac48 = \frac16$.

**b) A lo sumo uno** significa 0 o 1. Para exactamente 1 se elige **1 de los 4** de inyección **y 2 de los 6** comunes. Las dos elecciones se combinan entre sí, así que se multiplican:
$$P(I = 1) = \frac{\binom41\binom62}{120} = \frac{4\cdot15}{120} = \frac{60}{120} \;\Rightarrow\; P(I \le 1) = \frac{20 + 60}{120} = \frac23$$

**c) Al menos dos** (2 o 3) es lo contrario de "a lo sumo uno": $1 - \frac23 = \frac13$.

(Este tipo de conteo es la distribución **hipergeométrica** de la Unidad 3; la fórmula está en 📄 H1.)

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

💡 **Truco del complemento.** "Al menos dos coinciden" abarca muchísimos casos (dos coinciden, tres coinciden, dos pares distintos…). Lo contrario es uno solo: "**todos** cumplen en días distintos". Se calcula ese y se resta de 1.

Se ordena a las personas (persona 1, persona 2, …) y se usa Laplace:
- **Casos posibles:** cada persona puede cumplir cualquiera de los 365 días: $365\cdot365\cdots = 365^8$.
- **Casos con días todos distintos:** la 1.ª tiene 365 días disponibles, la 2.ª 364 (no puede repetir), la 3.ª 363, … la 8.ª 358: $365\cdot364\cdots358$.

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

**La idea:** solo se sabe hacer la unión de **dos** eventos. El truco es mirar la unión de tres como la unión de dos: el bloque $(A\cup B)$ y C. Después se aplica la regla de dos todas las veces que haga falta.

La regla que se puede usar es $P(E\cup F) = P(E) + P(F) - P(E\cap F)$: se suman los dos y se resta lo que se contó dos veces.

1. **Agrupar**, con $E = A\cup B$ y $F = C$:
   $$P(A\cup B\cup C) = P(A\cup B) + P(C) - P[(A\cup B)\cap C]$$
2. **Distributiva** (como en álgebra, "∩ distribuye sobre ∪"). "Estar en A o en B, y además en C" es lo mismo que "estar en A y C, o en B y C":
   $$(A\cup B)\cap C = (A\cap C)\cup(B\cap C)$$
3. **Regla de dos otra vez**, ahora con $E = A\cap C$ y $F = B\cap C$. Su intersección es estar en los tres, $A\cap B\cap C$:
   $$P[(A\cap C)\cup(B\cap C)] = P(A\cap C) + P(B\cap C) - P(A\cap B\cap C)$$
4. **Reemplazar** en el paso 1, también $P(A\cup B) = P(A) + P(B) - P(A\cap B)$, y ordenar. Ojo con el signo menos del paso 1, que se distribuye sobre los tres términos del paso 3:
   $$P(A)+P(B)-P(A\cap B)+P(C)-P(A\cap C)-P(B\cap C)+P(A\cap B\cap C)$$

Esta fórmula está en 📄 **H1**, pero acá piden demostrarla.

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

**Cómo leer la tabla.** Las celdas de adentro son probabilidades de **dos cosas a la vez** (intersecciones). Los totales de los márgenes son probabilidades de **una sola** cosa.

**a)**
- P(A) = "7 años o más" = total de esa fila = **0,40**.
- P(B) = "reincide" = total de esa columna = **0,33**.
- P(A ∩ B) = "7 años o más **y** reincide" = la celda donde se cruzan = **0,10**.

💡 **Probabilidad condicional** $P(A/B)$, que se lee "A dado B": la probabilidad de A **sabiendo que ya ocurrió B**. Saber que ocurrió B achica el universo: ahora solo se mira a los reincidentes, y de ellos qué fracción tiene 7 años o más:
$$P(A/B) = \frac{P(A\cap B)}{P(B)} = \frac{0{,}10}{0{,}33} = \frac{10}{33} \approx 0{,}303$$
📄 **H1**.

**b)** Unión, 📄 H1 (versión de 3 sin C): $P(A\cup B) = 0{,}40 + 0{,}33 - 0{,}10 = 0{,}63$.

El complemento es $1 - 0{,}63 = 0{,}37$. Se puede leer en la tabla: es la celda "menos de 7 y no reincidente", la única que no tiene ni A ni B.

**c)** 💡 **Independencia:** A y B son independientes si saber uno **no cambia** la probabilidad del otro, es decir $P(A/B) = P(A)$. Eso equivale a $P(A\cap B) = P(A)\cdot P(B)$ (📄 H1).
$$P(A)\,P(B) = 0{,}40\cdot0{,}33 = 0{,}132 \neq 0{,}10$$
**No son independientes.** Lo mismo se ve con la condicional: entre los reincidentes, el 30 % tiene 7 años o más, contra el 40 % en general. El nivel de educación sí está relacionado con reincidir.

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

**El problema:** el resultado final (elegir una mujer en Of₂) depende de **qué pasó antes** (a quién se transfirió). Hay que considerar los dos escenarios posibles.

**Etapa 1, el traspaso.** Of₁ tiene 3 mujeres y 1 varón:
- M₁ = "se transfiere una mujer", P = 3/4;
- V₁ = "se transfiere un varón", P = 1/4.

Uno de los dos pasa seguro, y nunca los dos: se dice que forman una **partición**.

**Etapa 2, la elección en Of₂** (que tenía 2M y 2V), según el escenario:
- Si pasó una mujer, Of₂ queda con 3M y 2V, y $P(M_2/M_1) = 3/5$.
- Si pasó un varón, Of₂ queda con 2M y 3V, y $P(M_2/V_1) = 2/5$.

```
          ┌── M₂  3/5  → 3/4 · 3/5 = 9/20
 M₁ 3/4 ──┤
          └── V₂  2/5
          ┌── M₂  2/5  → 1/4 · 2/5 = 2/20
 V₁ 1/4 ──┤
          └── V₂  3/5
```

💡 **Teorema de la probabilidad total.** Para saber la probabilidad de algo que puede llegar por varios caminos, se suman **todos los caminos que terminan ahí**. Cada camino vale el producto de sus ramas: P(escenario) · P(resultado / escenario).

$$P(M_2) = P(M_1)P(M_2/M_1) + P(V_1)P(M_2/V_1) = \frac34\cdot\frac35 + \frac14\cdot\frac25 = \frac{9}{20} + \frac{2}{20} = \frac{11}{20}$$

En 📄 **H1** esta suma aparece como el denominador de la fórmula de Bayes.

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

La única herramienta es la **definición de probabilidad condicional** (📄 H1): $P(E/F) = \frac{P(E\cap F)}{P(F)}$, válida si P(F) > 0. Por eso cada inciso pide que el evento de abajo "no sea imposible": no se puede dividir por 0.

**a)** Se escribe cada condicional con la definición y se suman (tienen el mismo denominador):
$$P(B/A) + P(B^c/A) = \frac{P(A\cap B) + P(A\cap B^c)}{P(A)}$$
Ahora se mira el numerador: los resultados de A se parten en los que están en B y los que no. Esas dos partes no se pisan, así que sus probabilidades suman la de A entera: $P(A\cap B) + P(A\cap B^c) = P(A)$. Entonces:
$$\frac{P(A)}{P(A)} = 1$$
En palabras: sabiendo que pasó A, B pasa o no pasa.

**b)** Se parte de lo que dice el enunciado y se multiplica por −1, lo que **da vuelta** la desigualdad; después se suma 1:
$$P(B/A) > P(B) \;\Rightarrow\; 1 - P(B/A) < 1 - P(B)$$
Por a), $1 - P(B/A) = P(B^c/A)$. Por complemento, $1 - P(B) = P(B^c)$. Reemplazando: $P(B^c/A) < P(B^c)$.

En palabras: si A hace **más** probable a B, hace **menos** probable a "no B".

**c)** Definición, y después distributiva ("A o B, y C" es "A y C, o B y C"):
$$P(A\cup B/C) = \frac{P[(A\cup B)\cap C]}{P(C)} = \frac{P[(A\cap C)\cup(B\cap C)]}{P(C)}$$
Regla de la unión en el numerador, sabiendo que la intersección de $A\cap C$ con $B\cap C$ es $A\cap B\cap C$:
$$= \frac{P(A\cap C) + P(B\cap C) - P(A\cap B\cap C)}{P(C)}$$
Se separa en tres fracciones, y cada una es una condicional: $P(A/C) + P(B/C) - P(A\cap B/C)$.

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

Es un experimento **en dos etapas**, donde la segunda depende de la primera, porque el cubo que se pasa cambia la caja II. Se piensa como un árbol.

💡 **Regla de la multiplicación:** $P(E\cap F) = P(E)\cdot P(F/E)$. Es la probabilidad de la 1.ª etapa por la de la 2.ª **sabiendo** lo que pasó en la 1.ª (se despeja de la condicional de 📄 H1).

**a) "Azul de la I y verde de la II".**
- 1.ª etapa: la caja I tiene 7 azules de 10, así que $P(a_I) = \frac7{10}$.
- 2.ª etapa: se agregó un azul a la II, que queda con 7 azules y 4 verdes (11 cubos). Entonces $P(v_{II}/a_I) = \frac4{11}$.

$$P = \frac7{10}\cdot\frac4{11} = \frac{28}{110} = \frac{14}{55} \approx 0{,}2545$$

**b) ¿Cuándo quedan las cajas como al principio?** Cuando el cubo que vuelve a la I es **del mismo color** que el que salió. Hay dos caminos, que no se pisan, así que se suman:
- **azul y después azul:** la II quedó con 7 azules de 11: $\frac7{10}\cdot\frac7{11} = \frac{49}{110}$;
- **verde y después verde:** la II quedó con 6 azules y 5 verdes: $\frac3{10}\cdot\frac5{11} = \frac{15}{110}$.

$$P = \frac{49 + 15}{110} = \frac{64}{110} = \frac{32}{55} \approx 0{,}582$$

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

💡 **Dos tipos de independencia para tres eventos.**
- **De a pares:** cada par por separado cumple $P(\text{par}\cap\text{par}) = P\cdot P$. Es decir, A con B, A con C y B con C.
- **Mutua (o total):** además, los tres juntos cumplen $P(A\cap B\cap C) = P(A)P(B)P(C)$.

Este ejercicio muestra que la primera **no** garantiza la segunda.

**Probabilidades sueltas.** Dos dados dan 6 · 6 = 36 pares igual de probables (Laplace).
- P(A) = P(B) = ½: la mitad de los números son pares.
- C = "suma par". Pasa si los dos son pares (3 · 3 = 9 pares) o los dos son impares (9 pares): $\frac{18}{36} = \frac12$.

**a) De a pares.**
- A∩B = los dos pares: $\frac{9}{36} = \frac14 = \frac12\cdot\frac12$ ✓.
- A∩C = "el 1.º par y la suma par". Si el primero es par, para que la suma sea par el segundo **también** tiene que ser par. Entonces A∩C es lo mismo que "los dos pares": $\frac14 = \frac12\cdot\frac12$ ✓.
- B∩C: igual razonamiento, $\frac14$ ✓.

Son **independientes de a pares**.

**b) Los tres juntos.** Si los dos son pares, la suma es par seguro, así que $A\cap B\cap C = A\cap B$:
$$P(A\cap B\cap C) = \frac14 \neq \frac12\cdot\frac12\cdot\frac12 = \frac18$$
**No son mutuamente independientes.** La explicación: conocer A y B juntos determina C por completo.

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

**La idea en palabras:** "ocurre al menos uno" es lo contrario de "no ocurre ninguno". Y "ninguno", con eventos independientes, se calcula multiplicando.

1. **Complemento:** $P(A\cup B\cup C) = 1 - P[(A\cup B\cup C)^c]$.
2. **De Morgan:** "no (A o B o C)" es lo mismo que "no A y no B y no C": $(A\cup B\cup C)^c = A^c\cap B^c\cap C^c$.
3. **Independencia de los complementos:** si A, B y C son mutuamente independientes, sus complementos también lo son (se demuestra en el ejercicio 24 para dos eventos, y con tres es igual). Entonces la probabilidad de la intersección es el producto:
   $$P(A^c\cap B^c\cap C^c) = P(A^c)P(B^c)P(C^c)$$
4. Reemplazando en 1: $P(A\cup B\cup C) = 1 - P(A^c)P(B^c)P(C^c)$. ∎

Se usa muchísimo: "probabilidad de que **alguno** funcione = 1 − probabilidad de que fallen **todos**". Ver el ejercicio 21.

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

💡 **B − A** ("B menos A") son los resultados que están en B pero **no** en A: $B - A = B\cap A^c$. En un Venn, es la parte de B que queda afuera de A.

**P(A ∩ B).** B se parte en dos pedazos que no se pisan: la parte que está en A ($B\cap A$) y la que no ($B - A$). Entonces sus probabilidades suman P(B):
$$P(B) = P(A\cap B) + P(B - A) \;\Rightarrow\; P(A\cap B) = \frac13 - \frac1{12} = \frac{4 - 1}{12} = \frac14$$

**P(Aᶜ / B).** Es la condicional (📄 H1, $P(E/F) = \frac{P(E\cap F)}{P(F)}$): entre los resultados de B, la fracción que **no** está en A. El numerador $A^c\cap B$ es justamente $B - A$:
$$P(A^c/B) = \frac{P(A^c\cap B)}{P(B)} = \frac{1/12}{1/3} = \frac14$$

(El dato P(A) = ½ no hacía falta.)

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

Se usa la definición (📄 H1): $P(B/A) = \frac{P(A\cap B)}{P(A)}$, que es la probabilidad de B sabiendo que ocurrió A. Lo que cambia en cada caso es la intersección.

**a) A ⊆ B:** todo resultado de A está también en B. Entonces lo que tienen en común es A entera: $A\cap B = A$.
$$P(B/A) = \frac{P(A)}{P(A)} = 1$$
En palabras: si ocurrió A, seguro ocurrió B.

**b) A y B incompatibles:** no tienen resultados en común, $A\cap B = \emptyset$, cuya probabilidad es 0.
$$P(B/A) = \frac{0}{P(A)} = 0$$
En palabras: si ocurrió A, es imposible que haya ocurrido B.

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

"Si aparece un 4…" significa que **ya se sabe** eso. Es una **probabilidad condicional**: se achica el universo a los casos que cumplen la condición, y ahí adentro se cuentan los favorables.

**a)** Universo nuevo: el primer dado es 4. El segundo puede ser cualquiera de 6 números, todos igual de probables. Para que la suma sea ≥ 8 hace falta que el segundo sea ≥ 4, es decir {4, 5, 6}:
$$P = \frac36 = \frac12$$

**b)** Universo nuevo: D = "al menos un 4" entre los 36 pares posibles.
- Pares con 4 en el primer dado: 6. Con 4 en el segundo: 6.
- El (4,4) se contó dos veces, así que hay 6 + 6 − 1 = **11** pares: $P(D) = \frac{11}{36}$.

Favorables (algún 4 **y** suma ≥ 8): (4,4), (4,5), (4,6), (5,4), (6,4). Son **5** pares; el (4,4) va una sola vez.

Con la definición de condicional (📄 H1):
$$P(\text{suma} \ge 8 / D) = \frac{P(\text{suma} \ge 8 \cap D)}{P(D)} = \frac{5/36}{11/36} = \frac5{11}$$
Es lo mismo que contar "5 favorables entre los 11 posibles del universo nuevo".

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

**Cómo pensarlo.** Para ir de A a C hay que pasar por B. Entonces hacen falta **las dos cosas**: poder ir de A a B (por **alguno** de los 3 caminos) **y** poder ir de B a C (por alguno de los 2).

Cada camino está bloqueado con P = 0,1 y abierto con P = 0,9, sin depender de los demás (independientes).

💡 **"Alguno abierto" = 1 − "todos bloqueados".** Que estén todos bloqueados es una intersección de eventos independientes, así que se multiplica (📄 H1, $P(A\cap B) = P(A)P(B)$). Es el resultado del ejercicio 17.
- Tramo A–B (3 caminos): $P(\text{alguno abierto}) = 1 - 0{,}1^3 = 0{,}999$.
- Tramo B–C (2 caminos): $1 - 0{,}1^2 = 0{,}99$.

**a)** Los dos tramos son independientes entre sí, así que "los dos transitables" es el producto:
$$0{,}999\cdot0{,}99 = 0{,}98901$$

**b)** Ya se sabe que A₂ (el corto) está cerrado, así que de A a B solo quedan A₁ y A₃. Ir de C a A o de A a C es lo mismo (los caminos son los mismos):
$$\underbrace{(1 - 0{,}1^2)}_{A_1 \text{ o } A_3}\cdot\underbrace{(1 - 0{,}1^2)}_{B_1 \text{ o } B_2} = 0{,}99^2 = 0{,}9801$$

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

"Sin reposición" significa que la bola sacada **no vuelve**: cada extracción cambia lo que queda en la urna.

💡 **Regla de la multiplicación para varias etapas:** la probabilidad de una secuencia es el producto de la probabilidad de cada paso, calculada **con lo que queda en la urna** en ese momento. Se deduce de la condicional de 📄 H1: $P(E\cap F) = P(E)P(F/E)$.

**a) Roja, roja, blanca, en ese orden:**
- 1.ª roja: 7 rojas de 10, $\frac7{10}$.
- 2.ª roja: quedan 6 rojas de 9, $\frac69$.
- 3.ª blanca: quedan 3 blancas de 8, $\frac38$.

$$P = \frac7{10}\cdot\frac69\cdot\frac38 = \frac{126}{720} = \frac7{40}$$

**b) Exactamente una blanca,** sin importar dónde. La blanca puede salir 1.ª, 2.ª o 3.ª, así que hay tres órdenes: RRB, RBR, BRR. Son casos que no se pisan y se suman.

Cada orden tiene la misma probabilidad. Por ejemplo, RBR = $\frac7{10}\cdot\frac39\cdot\frac68$: son los mismos números en otro orden, y dan $\frac{7\cdot6\cdot3}{720}$ igual. Entonces:
$$P = 3\cdot\frac7{40} = \frac{21}{40}$$

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

Hay **tres etapas**: (1) qué urna se elige, (2) qué bola se pasa a la otra urna, (3) qué bola se saca de esa otra urna. Se arma un árbol y se suman los caminos que terminan en "mismo color" (**probabilidad total**). Cada camino vale el producto de sus ramas.

**Rama "se elige A" (probabilidad ½).** A tiene 3R y 2B; B tiene 2R y 5B.
- Sale R de A (3/5). Pasa a B, que queda con 3R y 5B (8 bolas). Para igual color, de B tiene que salir R: 3/8.
- Sale B de A (2/5). B queda con 2R y 6B. Tiene que salir B: 6/8.
- Igual color, dado que se eligió A: $\frac35\cdot\frac38 + \frac25\cdot\frac68 = \frac{9}{40} + \frac{12}{40} = \frac{21}{40}$.

**Rama "se elige B" (probabilidad ½).**
- Sale R de B (2/7). Pasa a A, que queda con 4R y 2B (6 bolas). Tiene que salir R: 4/6.
- Sale B de B (5/7). A queda con 3R y 3B. Tiene que salir B: 3/6.
- Igual color, dado que se eligió B: $\frac27\cdot\frac46 + \frac57\cdot\frac36 = \frac{8}{42} + \frac{15}{42} = \frac{23}{42}$.

**Probabilidad total** (cada urna con peso ½):
$$P = \frac12\cdot\frac{21}{40} + \frac12\cdot\frac{23}{42} = \frac12\cdot\frac{441 + 460}{840} = \frac{901}{1680} \approx 0{,}536$$

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

💡 **Definición de independencia** (📄 H1): A y B son independientes ⇔ $P(A\cap B) = P(A)P(B)$. Para demostrar que dos eventos son independientes, hay que llegar a esa igualdad.

**a) A y Bᶜ.** A se parte en "A y B" y "A sin B", así que $P(A\cap B^c) = P(A) - P(A\cap B)$. Como A y B son independientes, se reemplaza $P(A\cap B) = P(A)P(B)$ y se saca factor común:
$$P(A\cap B^c) = P(A) - P(A)P(B) = P(A)[1 - P(B)] = P(A)\,P(B^c)$$
Se cumple la definición, así que A y Bᶜ son independientes. Con Aᶜ y B es igual, cambiando los roles.

**Aᶜ y Bᶜ.** "Ni A ni B" es el complemento de "A o B" (De Morgan). Se usa la unión y la independencia:
$$P(A^c\cap B^c) = 1 - P(A\cup B) = 1 - P(A) - P(B) + P(A)P(B)$$
Ese polinomio se factoriza como un producto (se puede verificar distribuyendo):
$$= (1 - P(A))(1 - P(B)) = P(A^c)\,P(B^c)$$

**b) Excluyentes no es lo mismo que independientes.** Si $A\cap B = \emptyset$, entonces $P(A\cap B) = 0$. Pero el enunciado dice que $P(A)P(B) > 0$. Como $0 \neq P(A)P(B)$, no se cumple la definición: **no son independientes**.

En palabras: si son excluyentes, saber que pasó A dice que B **seguro no pasó**. Eso es información, así que no son independientes.

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

H = "el hombre vive 10 años más", con P(H) = 1/3. M = "la mujer vive 10 años más", con P(M) = 1/4.

💡 **Independientes** significa que lo que le pase a uno no cambia la probabilidad del otro. Entonces "los dos" es el **producto** (📄 H1, $P(H\cap M) = P(H)P(M)$), y eso vale también con los complementos (ejercicio 24).

**a) Ambos vivos:** $P(H\cap M) = \frac13\cdot\frac14 = \frac1{12}$.

**b) Al menos uno vivo** es la unión. Regla de la unión: $P(H\cup M) = P(H) + P(M) - P(H\cap M)$:
$$\frac13 + \frac14 - \frac1{12} = \frac{4 + 3 - 1}{12} = \frac12$$

**c) Ninguno vivo:** hombre muerto (prob. 2/3) **y** mujer muerta (prob. 3/4). Son independientes, así que se multiplica:
$$\frac23\cdot\frac34 = \frac12$$
Es justo lo contrario de b): $1 - \frac12$ ✓.

**d) Sólo la mujer:** ella vive **y** él no: $\frac14\cdot\frac23 = \frac16$.

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

**La trampa:** la intuición dice ½ ("si salió oro, es la cajonera OO o la PO"). Pero esas dos **no** son igual de probables una vez que se sabe que salió oro. Hay que "dar vuelta" la condicional, y para eso está **Bayes**.

**Escenarios** (cuál cajonera se eligió), cada uno con P = 1/3: E₁ = PP, E₂ = PO, E₃ = OO.

**Probabilidad de sacar oro en cada escenario:**
- P(oro / E₁) = 0;
- P(oro / E₂) = ½ (uno de sus dos cajones);
- P(oro / E₃) = 1.

**Probabilidad total de sacar oro** (sumar los caminos que terminan en oro):
$$P(O) = \frac13\cdot0 + \frac13\cdot\frac12 + \frac13\cdot1 = \frac12$$

**¿Qué se pregunta?** "El otro cajón tiene oro" solo pasa si la cajonera es E₃. Se pide entonces $P(E_3/O)$: la probabilidad del **escenario**, sabiendo el **resultado**.

💡 **Teorema de Bayes** (📄 H1): $P(E_j/O) = \frac{P(E_j)\,P(O/E_j)}{P(O)}$. Es "el camino que interesa" dividido "todos los caminos que llegan al resultado".
$$P(E_3/O) = \frac{\frac13\cdot1}{\frac12} = \frac23$$

**Intuición:** hay 3 monedas de oro igual de probables de ser la que se sacó. Dos de ellas están en la cajonera OO, así que 2 de cada 3 veces el otro cajón tiene oro.

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

**Paso 1, traducir los datos.** "Uno de cada 25" significa $P(E) = \frac1{25} = 0{,}04$, así que $P(E^c) = 0{,}96$.

Los porcentajes de la prueba son **condicionales**: dicen qué pasa **dado** que la persona está enferma o sana.
- Enfermo da positivo el 98 %: $P(+/E) = 0{,}98$, y entonces $P(-/E) = 0{,}02$.
- Sano da positivo el 3 %: $P(+/E^c) = 0{,}03$, y entonces $P(-/E^c) = 0{,}97$.

```
              ┌── +  0,98 → 0,04·0,98 = 0,0392
 E   0,04 ────┤
              └── −  0,02 → 0,0008
              ┌── +  0,03 → 0,96·0,03 = 0,0288
 Eᶜ  0,96 ────┤
              └── −  0,97 → 0,96·0,97 = 0,9312
```

**a)** 💡 **Probabilidad total:** se suman todos los caminos que terminan en "+".
$$P(+) = 0{,}0392 + 0{,}0288 = 0{,}068$$

**b)** Se pide al revés: **dado** el positivo, ¿está enfermo? 💡 **Bayes** (📄 H1) es "el camino que interesa / todos los caminos que llegan a +":
$$P(E/+) = \frac{0{,}0392}{0{,}068} = 0{,}5765$$

**Lectura:** aunque la prueba acierta el 98 % con los enfermos, un positivo solo significa 58 % de chances de estar enfermo. Pasa porque hay muchísimos más sanos, y su 3 % de falsos positivos pesa mucho.

**c)** Ahora la condición es "−". Total de negativos: $P(-) = 1 - 0{,}068 = 0{,}932$. El camino "sano y negativo" es $0{,}96\cdot0{,}97 = 0{,}9312$. Bayes:
$$P(E^c/-) = \frac{0{,}9312}{0{,}932} = 0{,}9991$$

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

**Datos:** la probabilidad de sacar un defectuoso de cada caja es $P(D_A) = \frac38$, $P(D_B) = \frac25$ y $P(D_C) = \frac4{10}$. Las de sacar uno bueno son $\frac58$, $\frac35$ y $\frac6{10}$.

Lo que sale de una caja no influye en las otras, así que las tres extracciones son **independientes**: la probabilidad de una combinación es el **producto** (📄 H1).

**a) Los tres defectuosos:**
$$\frac38\cdot\frac25\cdot\frac4{10} = \frac{24}{400} = \frac3{50}$$

**b) Exactamente uno defectuoso.** Puede ser el de A, el de B o el de C. Son tres casos que no se pisan (mutuamente excluyentes), así que se calcula cada uno y se suman. En cada caso, la caja "elegida" da defectuoso y las otras dos dan bueno:
- sólo el de A: $\frac38\cdot\frac35\cdot\frac6{10} = \frac{54}{400}$;
- sólo el de B: $\frac58\cdot\frac25\cdot\frac6{10} = \frac{60}{400}$;
- sólo el de C: $\frac58\cdot\frac35\cdot\frac4{10} = \frac{60}{400}$.

$$P = \frac{54 + 60 + 60}{400} = \frac{174}{400} = \frac{87}{200}$$

**c)** **Sabiendo** que hubo un solo defectuoso, ¿vino de A? Es una condicional (📄 H1, $P(E/F) = \frac{P(E\cap F)}{P(F)}$), y la misma lógica de Bayes: el caso que interesa dividido todos los casos posibles.
$$P(\text{de A} / \text{uno solo}) = \frac{54/400}{174/400} = \frac{54}{174} = \frac9{29}$$

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

**Cómo reconocer un Bayes:** hay grupos (mujeres y hombres) con distinta probabilidad de algo (hacer deporte), y la pregunta va **al revés**: **sabiendo** que hace deporte, ¿de qué grupo es?

**Datos:**
- P(M) = 0,7 y P(H) = 0,3.
- Los porcentajes de deporte son **dentro de cada grupo**, así que son condicionales: P(D/M) = 0,55 y P(D/H) = 0,4.

**Probabilidad total** de hacer deporte (los dos caminos que llevan a D):
$$P(D) = \underbrace{0{,}7\cdot0{,}55}_{0{,}385} + \underbrace{0{,}3\cdot0{,}4}_{0{,}12} = 0{,}505$$

**Bayes** (📄 H1): el camino "mujer y deporte" dividido el total de deportistas:
$$P(M/D) = \frac{0{,}385}{0{,}505} = \frac{77}{101} \approx 0{,}7624$$

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

**Escenarios** (con quién viaja), que forman una partición porque cada pasajero está en uno solo:
- F (familia) = 0,30;
- A (amigos) = 0,25;
- S (solo) = 1 − 0,30 − 0,25 = 0,45, porque tienen que sumar 1.

**Datos condicionales** ("de los que viajan con…"): P(N/F) = 0,5, P(N/A) = 0,7 y P(N/S) = 0,25, donde N = vuelo nocturno.

**a)** 💡 **Probabilidad total:** se suman los tres caminos que llevan a "nocturno", cada uno como P(grupo) · P(N / grupo):
$$P(N) = 0{,}3\cdot0{,}5 + 0{,}25\cdot0{,}7 + 0{,}45\cdot0{,}25 = 0{,}15 + 0{,}175 + 0{,}1125 = 0{,}4375$$
Lo que se pide es lo contrario: $P(\bar N) = 1 - 0{,}4375 = 0{,}5625$.

**b)** Pregunta al revés: **sabiendo** que es nocturno, ¿viaja con amigos? 💡 **Bayes** (📄 H1), el camino "amigos y nocturno" sobre el total nocturno:
$$P(A/N) = \frac{0{,}175}{0{,}4375} = 0{,}4$$

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

Se eligen 3 personas de 6 al azar, sin importar el orden. Todas las comisiones son igual de probables, así que vale Laplace: favorables / posibles.

💡 $\binom nk$ (nCr en la calculadora) cuenta cuántos grupos de k se pueden formar con n elementos, sin importar el orden.

**Total de comisiones:** $\binom63 = 20$. Iniciales: L tiene 2 (Leibnitz, Laplace), E tiene 2 (Euler, Euclides), C tiene 1 (Cauchy) y G tiene 1 (Gauss).

**a) "Alguno con L"**: es más fácil por complemento. "Ninguno con L" significa elegir los 3 entre los 4 que no empiezan con L: $\binom43 = 4$ comisiones.
$$P = 1 - \frac4{20} = 0{,}8$$

**b)** Es una **condicional**: se achica el universo a las comisiones que tienen dos con la misma inicial. Eso solo puede pasar con LL o con EE, porque ninguna inicial se repite tres veces.
- Comisiones con los dos L: se eligen los 2 L ($\binom22 = 1$ forma) y el tercero entre los otros 4: $1\cdot4 = 4$.
- Comisiones con los dos E: también 4.
- No hay ninguna con LL y EE a la vez, porque solo hay 3 lugares.

Universo nuevo: 8 comisiones. Favorables (la inicial repetida es L): 4.
$$P = \frac48 = \frac12$$

**c)** Ahora se eligen **2** personas: $\binom62 = 15$ pares posibles. Antigüedades: 12, 15, 9, 16, 20 y 7. Se listan los pares que cumplen:
1. **Suma 27:** 12 + 15 y 20 + 7, así que $\frac{2}{15}$.
2. **Suma mayor a 30:** 12 + 20 = 32, 15 + 16 = 31, 15 + 20 = 35 y 16 + 20 = 36, así que $\frac4{15}$. Control: 9 + 20 = 29 y 16 + 12 = 28 no llegan.

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

💡 **Regla de Laplace.** Si todos los resultados son igual de probables (cualquier bolita tiene la misma chance de salir):
$$P(\text{evento}) = \frac{\text{casos favorables}}{\text{casos posibles}}$$

Casos posibles: 10 + 4 + 8 + 3 = **25** bolitas.

**a)** Favorables: las 4 rojas, así que $\frac4{25} = 0{,}16$.

**b)** "Verde o azul": se cuentan las de los dos colores. Ninguna bolita es de los dos colores a la vez, así que no hay que restar nada: $\frac{10 + 8}{25} = \frac{18}{25}$.

**c)** 💡 **Complemento:** "no blanca" es lo contrario de "blanca", así que $P = 1 - P(\text{blanca}) = 1 - \frac3{25} = \frac{22}{25}$.

**d)** "Ni roja ni azul" deja las verdes y las blancas: $\frac{10 + 3}{25} = \frac{13}{25}$.

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

Hay 25 cartones, todos igual de probables, así que vale Laplace (favorables / posibles). Rojos: del 1 al 10. Verdes: del 11 al 25.

**a)** 15 verdes de 25: $\frac{15}{25} = \frac35$.

**b)** "Menor a 20" son los números del 1 al 19: $\frac{19}{25}$.

**c)** "Rojo **y** par" (las dos cosas a la vez): 2, 4, 6, 8, 10, así que $\frac5{25} = \frac15$.

**d)** "Rojo **o** par" (al menos una de las dos): todos los rojos (10) más los verdes que son pares (12, 14, …, 24, que son 7). Los rojos pares no se cuentan dos veces: $\frac{17}{25}$.

Con la regla de la unión da lo mismo: $P(R) + P(\text{par}) - P(R \cap \text{par}) = \frac{10 + 12 - 5}{25}$, porque hay 12 pares en total.

**e)** "Ni verde ni impar" es "rojo y par" (De Morgan), lo mismo que c): $\frac15$.

**f)** 💡 **Condicional:** "se saca entre los verdes" achica el universo a los 15 verdes. De ellos, los impares son 11, 13, …, 25, que son 8: $\frac8{15}$.

**g)** Universo: los impares, 5 rojos (1, 3, 5, 7, 9) más 8 verdes, en total 13. De ellos, los verdes son 8: $\frac8{13}$.

f) y g) **no** dan lo mismo: $P(\text{impar}/V) \neq P(V/\text{impar})$. El orden de la condicional importa.

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

**Paso 1, completar los totales** de la tabla de contingencia:

| | A | B | Total |
|---|---|---|---|
| Hombre | 25 | 40 | **65** |
| Mujer | 35 | 50 | **85** |
| Total | **60** | **90** | **150** |

Se elige un encuestado al azar entre 150, así que vale Laplace.

**a)** Hombres: $\frac{65}{150} \approx 0{,}433$.

**b)** Prefieren B: $\frac{90}{150} = 0{,}6$.

**c)** "Hombre **y** B" es la celda del cruce: $\frac{40}{150} \approx 0{,}267$.

**d)** 💡 **Condicional:** "resulta ser hombre" significa que **ya se sabe** que es hombre. El universo se achica a los 65 hombres, y de ellos 40 eligieron B:
$$P(B/H) = \frac{40}{65} \approx 0{,}615$$
Con la fórmula de 📄 H1 da lo mismo: $\frac{P(B\cap H)}{P(H)} = \frac{40/150}{65/150}$.

**e)** **Tabla por fila:** cada celda se divide por el total de **su fila**.
- Hombres: A 25/65 = 38,5 %, B 40/65 = **61,5 %**.
- Mujeres: A 35/85 = 41,2 %, B 50/85 = 58,8 %.

La celda (H, B) = 61,5 % es "de los **hombres**, qué porcentaje prefiere B": $P(B/H)$.

**Tabla por columna:** cada celda se divide por el total de **su columna**.
- Envase A: H 25/60 = 41,7 %, M 58,3 %.
- Envase B: H 40/90 = **44,4 %**, M 55,6 %.

La celda (H, B) = 44,4 % es "de los que prefieren **B**, qué porcentaje son hombres": $P(H/B)$.

**Moraleja:** lo que va **después** de la barra "/" es el grupo por el que se divide (el universo).

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

**4)** En un diagrama de Venn con dos fallas, cada pieza cae en **una sola** de cuatro regiones: sólo A, sólo B, las dos, ninguna. Como siempre cae en alguna, las cuatro probabilidades suman 1:
$$P(\text{las dos}) = 1 - 0{,}10 - 0{,}20 - 0{,}55 = 0{,}15$$

**5)** "El 10 % **de los de mecánica** desaprueba" es una probabilidad **condicional**: $P(D/M) = 0{,}1$. Se pide "mecánica **y** desaprueba", una intersección.

💡 **Regla de la multiplicación**, que sale de despejar la condicional de 📄 H1: $P(M\cap D) = P(M)\cdot P(D/M) = 0{,}7\cdot0{,}1 = 0{,}07$.

**6)** Un artículo fallado puede venir de M o de N, y hay que sumar los dos caminos (💡 **probabilidad total**). Cada camino es P(planta) · P(fallado / planta):
$$P(F) = \underbrace{0{,}6\cdot0{,}1}_{\text{de M}} + \underbrace{0{,}4\cdot0{,}05}_{\text{de N}} = 0{,}06 + 0{,}02 = 0{,}08$$
(N fabrica el resto: 1 − 0,6 = 0,4.)

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

Las cuatro regiones del diagrama no se pisan, así que cada evento se calcula **sumando las regiones que lo forman**.

**a)** A está formado por "sólo A" y "A ∩ B": $0{,}20 + 0{,}30 = 0{,}5$.

**b)** $B\cap A^c$ es "B pero no A", la región "sólo B": $0{,}1$.

**c)** $A\cup B$ (al menos uno) son las tres regiones que tocan A o B: $0{,}2 + 0{,}3 + 0{,}1 = 0{,}6$. También es $1 - 0{,}40$, lo que queda afuera.

**d)** 💡 **Condicional** (📄 H1), $P(B/A) = \frac{P(A\cap B)}{P(A)}$: dentro de A, qué parte también es B.
$$\frac{0{,}3}{0{,}5} = 0{,}6$$

**e)** Primero $P(B) = 0{,}3 + 0{,}1 = 0{,}4$. Después, dentro de B, qué parte **no** es A (la región "sólo B"):
$$P(A^c/B) = \frac{0{,}1}{0{,}4} = 0{,}25$$

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

**Ojo con los datos:** "el 30 % tiene la falla A" **incluye** a los que tienen las dos. No es "sólo A".

**Paso 1.** "Fallado" significa tener al menos una falla, $A\cup B$. Es lo contrario de "no tiene fallas":
$$P(A\cup B) = 1 - 0{,}65 = 0{,}35$$

**a)** De la regla de la unión, $P(A\cup B) = P(A) + P(B) - P(A\cap B)$ (📄 H1, la de 3 sin C), se despeja la intersección:
$$P(A\cap B) = 0{,}3 + 0{,}2 - 0{,}35 = 0{,}15$$

**b)** "Una sola falla" es estar fallado pero sin tener las dos: $0{,}35 - 0{,}15 = 0{,}20$. Por regiones: sólo A = 0,30 − 0,15 = 0,15 y sólo B = 0,20 − 0,15 = 0,05, que suman 0,20 ✓.

**c)** Fallado = $P(A\cup B) = 0{,}35$.

**d)** "Entre los que tienen A" es una **condicional**:
$$P(B/A) = \frac{P(A\cap B)}{P(A)} = \frac{0{,}15}{0{,}3} = 0{,}5$$

**e)** Universo: los que **no** tienen B, $P(\bar B) = 1 - 0{,}2 = 0{,}8$. De ellos, los que tienen A son "sólo A", $P(A\cap\bar B) = 0{,}3 - 0{,}15 = 0{,}15$:
$$P(A/\bar B) = \frac{0{,}15}{0{,}8} = 0{,}1875$$

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

**Escenarios:** la división del estudiante, con P(A) = 0,25, P(B) = 0,35 y P(C) = 0,40. Los porcentajes de desaprobados son **dentro de cada división** (condicionales): P(D/A) = 0,2, P(D/B) = 0,3 y P(D/C) = 0,25.

**a)** 💡 **Probabilidad total:** un desaprobado puede venir de A, de B o de C. Se suman los tres caminos, cada uno como P(división) · P(D / división):
$$P(D) = 0{,}25\cdot0{,}2 + 0{,}35\cdot0{,}3 + 0{,}4\cdot0{,}25 = 0{,}05 + 0{,}105 + 0{,}1 = 0{,}255$$

**b)** Pregunta al revés: **sabiendo** que desaprobó, ¿es de C? 💡 **Bayes** (📄 H1), el camino "C y desaprobado" sobre el total de desaprobados:
$$P(C/D) = \frac{0{,}1}{0{,}255} \approx 0{,}392$$

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

💡 **Diagrama de árbol.** Cada nivel es una extracción y cada rama es un color posible, con su probabilidad **en ese momento**. La probabilidad de un camino completo es el **producto** de sus ramas (regla de la multiplicación).

**Sin reposición.** La bolita no vuelve, así que en cada paso hay una menos: los denominadores son 7, 6, 5, y los numeradores bajan según el color que ya salió.
- **a) B, N, B:** 1.ª blanca, 3 de 7. 2.ª negra, 4 de 6 (quedan todas las negras). 3.ª blanca, 2 de 5 (ya salió una blanca).
  $$\frac37\cdot\frac46\cdot\frac25 = \frac{24}{210} = \frac4{35}$$
- **b) N, N, N:** $\frac47\cdot\frac36\cdot\frac25 = \frac{24}{210} = \frac4{35}$.
- **c) Dos negras**, sin importar el orden. La blanca puede estar 1.ª, 2.ª o 3.ª: NNB, NBN y BNN. Cada camino da $\frac{4\cdot3\cdot3}{210} = \frac{36}{210}$ (los mismos números en otro orden). Son caminos que no se pisan, así que se suman:
  $$3\cdot\frac{36}{210} = \frac{108}{210} = \frac{18}{35}$$

**Con reposición.** La bolita vuelve, así que la caja siempre tiene 4 negras y 3 blancas: las extracciones son **independientes** y siempre valen $\frac47$ (negra) y $\frac37$ (blanca).
- **a)** $\frac37\cdot\frac47\cdot\frac37 = \frac{36}{343}$.
- **b)** $\left(\frac47\right)^3 = \frac{64}{343}$.
- **c)** Tres órdenes, cada uno de $\left(\frac47\right)^2\cdot\frac37$: $3\cdot\frac{48}{343} = \frac{144}{343}$.

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

💡 **Independencia:** el tipo de sangre de una persona no influye en el de la otra. La probabilidad de que pasen dos cosas (una con cada persona) es el **producto** (📄 H1, $P(A\cap B) = P(A)P(B)$).

**a) Las dos del tipo A:** $0{,}4\cdot0{,}4 = 0{,}16$.

**b) Ninguna del tipo A:** cada una "no A" con prob. 1 − 0,4 = 0,6, así que $0{,}6^2 = 0{,}36$.

**c) Una A y la otra O.** Hay **dos órdenes** posibles: la 1.ª A y la 2.ª O, o la 1.ª O y la 2.ª A. Cada uno vale $0{,}4\cdot0{,}3$, y no se pisan, así que se suman:
$$2\cdot0{,}4\cdot0{,}3 = 0{,}24$$

**d) "Alguna AB"** (al menos una) se hace por complemento: 1 − "ninguna es AB". Cada una no es AB con prob. 0,9:
$$1 - 0{,}9^2 = 0{,}19$$

**e) Mismo tipo:** las dos A, o las dos B, o las dos O, o las dos AB. Son casos que no se pisan:
$$0{,}4^2 + 0{,}2^2 + 0{,}3^2 + 0{,}1^2 = 0{,}16 + 0{,}04 + 0{,}09 + 0{,}01 = 0{,}30$$

**f) Distinto tipo** es lo contrario de e): $1 - 0{,}30 = 0{,}70$.

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

Se supone que los partidos son **independientes** (el resultado de uno no cambia las chances del otro). Entonces la probabilidad de una secuencia de resultados es el producto.

**a) G, P, E en ese orden:** $0{,}6\cdot0{,}3\cdot0{,}1 = 0{,}018$.

**b) Uno de cada resultado, en cualquier orden.** Hay que contar los órdenes posibles: G, P y E se pueden ordenar de $3! = 3\cdot2\cdot1 = 6$ maneras (GPE, GEP, PGE, PEG, EGP, EPG). Cada orden vale 0,018 (los mismos factores en otro orden), así que:
$$6\cdot0{,}018 = 0{,}108$$

**c) Exactamente 2 victorias.** El partido que no gana puede ser el 1.º, el 2.º o el 3.º: hay $\binom32 = 3$ formas de elegir cuáles 2 gana. En cada caso hay 2 victorias ($0{,}6^2$) y un "no gana", que es perder o empatar ($0{,}3 + 0{,}1 = 0{,}4$):
$$3\cdot0{,}6^2\cdot0{,}4 = 0{,}432$$
(Esto es la distribución **binomial** de la Unidad 3; 📄 H1 tiene la fórmula $\binom nk p^k(1-p)^{n-k}$.)

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

**Traducción:** "tener que hacer n pozos" significa que el **primer** potable aparece justo en el pozo número n. Los n − 1 anteriores salieron **no** potables (prob. 0,9 cada uno) y el n-ésimo sí (prob. 0,1).

Se supone que los pozos son independientes, así que esa secuencia es el producto de sus probabilidades.

**a)** El 1.º falla y el 2.º es potable: $0{,}9\cdot0{,}1 = 0{,}09$.

**b)** Los 9 primeros fallan y el 10.º es potable: $0{,}9^9\cdot0{,}1 \approx 0{,}0387$.

**c)** En general: $0{,}9^{n-1}\cdot0{,}1$.

(Es la distribución **geométrica** de la Unidad 3.)

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

**Problema:** el enunciado da la probabilidad de cada rubro por separado, pero no dice qué pasa con los que compran varios. Sin eso no se pueden calcular las combinaciones. Hay que **suponer independencia**: comprar un rubro no cambia la probabilidad de comprar otro. Con esa suposición, "esto y aquello" es el producto.

C = comestibles (0,9), T = tocador y limpieza (0,7), E = electrodomésticos (0,2).

**a) Los tres:** $0{,}9\cdot0{,}7\cdot0{,}2 = 0{,}126$.

**b) Ninguno:** no C (0,1), no T (0,3) y no E (0,8). Los complementos de eventos independientes también son independientes:
$$0{,}1\cdot0{,}3\cdot0{,}8 = 0{,}024$$

**c) Alguno** (al menos uno) es lo contrario de "ninguno": $1 - 0{,}024 = 0{,}976$.

**d) Al menos dos** significa exactamente dos o los tres. Se suman las intersecciones de a dos: $P(C\cap T) = 0{,}63$, $P(C\cap E) = 0{,}18$ y $P(T\cap E) = 0{,}14$.

Pero los que compran **los tres** están incluidos en las tres intersecciones, así que se contaron 3 veces. Deben contarse una sola vez, y por eso se restan 2 veces:
$$0{,}63 + 0{,}18 + 0{,}14 - 2\cdot0{,}126 = 0{,}698$$

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

**Paso 1, una tabla con todo contado.** Se elige un alumno al azar entre todos, así que vale Laplace con estos números:

| | Curso 1 | Curso 2 | Curso 3 | Total |
|---|---|---|---|---|
| Sin trabajo | 3 | 5 | 4 | 12 |
| Con trabajo | 32 | 20 | 14 | 66 |
| Total | 35 | 25 | 18 | 78 |

**a)**
1. **No tiene trabajo:** $\frac{12}{78} \approx 0{,}154$.
2. **Sabiendo que es del 1.er curso** (condicional): el universo pasa a ser los 35 del curso 1, y de ellos 3 no trabajan: $\frac3{35}$.
3. **Sabiendo que tiene trabajo**: el universo son los 66 que trabajan, y de ellos 14 son del curso 3: $\frac{14}{66} \approx 0{,}212$.

**b)** Se eligen 4. Hay que pensar cuántas formas hay de que 2 no trabajen y 2 sí.

**Como lo resuelve el aula (aproximación):** se trata cada elección como independiente, con P(trabaja) = 66/78 = 11/13 y P(no trabaja) = 2/13. Las posiciones de los 2 que no trabajan se pueden elegir de $\binom42 = 6$ formas:
$$6\left(\frac{11}{13}\right)^2\left(\frac2{13}\right)^2 \approx 0{,}102$$

**Exacto, sin reposición:** no se puede elegir dos veces al mismo alumno. Se cuentan grupos: elegir 2 de los 12 sin trabajo **y** 2 de los 66 con trabajo, sobre todos los grupos de 4 de 78:
$$\frac{\binom{12}{2}\binom{66}{2}}{\binom{78}{4}} \approx 0{,}0992$$
Esa cuenta es la hipergeométrica de la Unidad 3. Las dos dan parecido porque el grupo es grande.

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

**2)** "Si salió cara, la probabilidad de par es 1/4" es una condicional: $P(\text{par}/C) = \frac14$, así que $P(\text{impar}/C) = 1 - \frac14 = \frac34$.

Se pide "cara **y** impar". 💡 Regla de la multiplicación, que sale de despejar la condicional de 📄 H1: $P(C\cap\text{impar}) = P(C)\,P(\text{impar}/C) = \frac12\cdot\frac34 = \frac38$.

**3)** Escenarios: el proveedor (0,1; 0,3; 0,6). Los porcentajes de rechazo son **dentro de cada proveedor** (condicionales): 0,02, 0,004 y 0,002.
- **a)** 💡 Probabilidad total, sumando los tres caminos que llevan a "rechazado":
  $$P(R) = 0{,}1\cdot0{,}02 + 0{,}3\cdot0{,}004 + 0{,}6\cdot0{,}002 = 0{,}002 + 0{,}0012 + 0{,}0012 = 0{,}0044$$
- **b)** 💡 Bayes (📄 H1): sabiendo que fue rechazado, ¿vino del 3.º? Es el camino del 3.º sobre el total:
  $$\frac{0{,}0012}{0{,}0044} \approx 0{,}273$$

**4)** Cada disco muestra un dígito del 0 al 5 al azar (6 opciones, prob. 1/6 cada uno), sin depender de los otros.
- **a)** "Empieza con 3 y es par":
  - el 1.er disco tiene que ser 3, prob. $\frac16$;
  - el último tiene que ser par, {0, 2, 4}, prob. $\frac36 = \frac12$;
  - el del medio puede ser cualquiera, prob. 1.

  Por independencia se multiplica: $\frac16\cdot1\cdot\frac12 = \frac1{12}$.
- **b)** La 2.ª cerradura se abre solo con 153: un número exacto de los $6^3 = 216$ posibles, prob. $\frac1{216}$. La puerta se abre si se abre **al menos una**: es una unión. Como son independientes, la intersección es el producto:
  $$\frac1{12} + \frac1{216} - \frac1{12}\cdot\frac1{216} \approx 0{,}0876$$

**5)** Con la definición, $P(A/B) = \frac{P(A\cap B)}{P(B)}$:
- **a)** Si A ⊆ B, lo común es A misma, $A\cap B = A$, así que $P(A/B) = \frac{P(A)}{P(B)}$.
- **b)** Si son independientes, $P(A\cap B) = P(A)P(B)$, así que $P(A/B) = \frac{P(A)P(B)}{P(B)} = P(A)$. Saber B **no cambia** la probabilidad de A, que es justamente lo que significa ser independientes.

**6)** Es la misma demostración del Ej. 14 c) de la guía, con B haciendo de condición. Por la definición y la distributiva:
$$P(A\cup C/B) = \frac{P[(A\cap B)\cup(C\cap B)]}{P(B)} = \frac{P(A\cap B) + P(C\cap B) - P(A\cap C\cap B)}{P(B)}$$
Separando en tres fracciones: $P(A/B) + P(C/B) - P(A\cap C/B)$.

**7)**
- **a)** **Incompatibles:** no pueden ocurrir juntos, $A\cap B = \emptyset$. **Independientes:** uno no cambia la probabilidad del otro, $P(A\cap B) = P(A)P(B)$ (📄 H1). Son cosas distintas.
- **b)** Para ser **complementarios**, además de no tener nada en común, entre los dos tienen que cubrir todo S, es decir sumar 1. Pero 0,5 + 0,3 = 0,8 ≠ 1. Son incompatibles, pero **no** complementarios: queda un 20 % donde no ocurre ninguno de los dos.

**8)** Para usar la **probabilidad total**, A, B y C tienen que ser los "escenarios" posibles: que no se pisen (mutuamente excluyentes) y que siempre ocurra uno de ellos (su unión es S). Eso se llama **partición**. Entonces:
$$P(D) = P(A)P(D/A) + P(B)P(D/B) + P(C)P(D/C)$$
Esta suma aparece en 📄 H1 como el denominador de Bayes.

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

**Herramientas:** la definición de independencia, $P(A\cap B) = P(A)P(B)$, y la de condicional, $P(A/B) = \frac{P(A\cap B)}{P(B)}$ (las dos en 📄 H1).

Se supone que A y B tienen probabilidad positiva (que "no son vacíos" se interpreta así).

**2) a)** Mutuamente excluyentes significa $A\cap B = \emptyset$, así que $P(A\cap B) = 0$. Pero $P(A)P(B) > 0$, porque los dos son positivos. Entonces $P(A\cap B) \neq P(A)P(B)$: **no** son independientes.

**2) b)** Es la misma idea dada vuelta. Si son independientes, $P(A\cap B) = P(A)P(B) > 0$. Una probabilidad positiva no puede ser la del vacío, así que $A\cap B \neq \emptyset$: **no** son excluyentes.

**5)** Se suman las dos condicionales, que tienen el mismo denominador:
$$P(A/B) + P(\bar A/B) = \frac{P(A\cap B) + P(\bar A\cap B)}{P(B)}$$
Los resultados de B se parten en los que están en A y los que no, sin pisarse, así que el numerador es P(B):
$$\frac{P(B)}{P(B)} = 1$$

(Los demás ejercicios teóricos del aula son los Ej. 11, 14, 17, 19 y 24 de la guía, resueltos más arriba.)

</details>

**Respuesta:** ambas propiedades quedan demostradas.

</details>

---

[← Volver al menú principal](../README.md)
