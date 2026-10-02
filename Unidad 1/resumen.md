# Unidad 1 — Probabilidades

Resumen de la teoría y la práctica del material del aula virtual (Prof. Andrea Alvarez, PyE UTN-FRBA): presentación de la unidad, introducciones al concepto de probabilidad (partes 1 y 2), clase de repaso, ejercicios teóricos y ejercicios resueltos de la Guía de TP.

---

## 1. Experimentos, espacio muestral y sucesos

- **Experimento determinístico**: el resultado se puede predecir a priori (soltar un objeto: cae).
- **Experimento aleatorio (E)**: no se puede predecir el resultado a priori (tirar un dado).
- **Espacio muestral (S)**: conjunto de todos los resultados posibles de E.
- **Suceso o evento**: cualquier subconjunto de S (A, B, C, …). Se representan con diagramas de Venn.

Ejemplo: E = "tirar un dado", S = {1, 2, 3, 4, 5, 6}.
A = {1}, B = "sale par" = {2, 4, 6}, C = "sale menor que 4" = {1, 2, 3}, D = "múltiplo de 10" = ∅.
- Si sale 2 ocurren S, B y C.
- A y B no pueden ocurrir juntos: son **incompatibles**.
- Si ocurre A ocurre C (A ⊆ C), pero no al revés.
- D no ocurre nunca: es el **suceso imposible** (∅).

### Operaciones entre sucesos

| Operación | Definición | Ocurre cuando… |
|---|---|---|
| Complemento $\bar A$ | $\{x \in S / x \notin A\}$ | no ocurre A |
| Intersección $A \cap B$ | $\{x \in S / x \in A \wedge x \in B\}$ | ocurren A **y** B |
| Unión $A \cup B$ | $\{x \in S / x \in A \vee x \in B\}$ | ocurre A **o** B (alguno) |
| Diferencia $A - B = A \cap \bar B$ | | sólo ocurre A |
| $(A \cap \bar B) \cup (\bar A \cap B)$ | | ocurre **sólo uno** |
| $\bar A \cap \bar B$ | | no ocurre **ninguno** |
| $\overline{A \cap B}$ | | no ocurren **juntos** |

**Leyes de De Morgan**: $\bar A \cap \bar B = \overline{A \cup B}$  y  $\bar A \cup \bar B = \overline{A \cap B}$

**Observaciones útiles**: $\bar S = \emptyset$, $\bar\emptyset = S$, $A \cap S = A$, $A \cup S = S$, $A \cap \bar A = \emptyset$, $A \cup \bar A = S$. Si $A \subseteq B$: $A \cap B = A$ y $A \cup B = B$.

### Sucesos mutuamente excluyentes (M.E.)

A y B son M.E. ⇔ $A \cap B = \emptyset$. En general, $A_1, \dots, A_n$ son M.E. ⇔ $A_i \cap A_j = \emptyset$ para todo $i \neq j$. Son incompatibles: si ocurre uno, no puede ocurrir ninguno de los otros.

---

## 2. Definiciones de probabilidad

### Definición clásica (Fórmula de Laplace)

$$P(A) = \frac{n_A}{n} = \frac{\text{n° de casos favorables a } A}{\text{n° de casos posibles equiprobables}}$$

- Sólo vale si S es **finito** y todos los resultados son **equiprobables** (hay que poder contar casos posibles y favorables).
- Propiedad fundamental: $0 \le P(A) \le 1$.
- La probabilidad **no es un porcentaje**: se dice "P = 0,65", aunque se relaciona con "el 65 %".

Propiedades que se deducen de la definición clásica: $P(A) + P(\bar A) = 1$, $P(S) = 1$, $P(\emptyset) = 0$; si A y B son M.E., $P(A \cup B) = P(A) + P(B)$; en general $P(A \cup B) = P(A) + P(B) - P(A \cap B)$.

### Definición frecuencial

Si E se repite n veces y A ocurre $n_A$ veces, la **frecuencia relativa** es $fr_A = n_A / n$.
**Principio de estabilidad de las frecuencias relativas**: cuando $n \to \infty$, $fr_A$ se estabiliza alrededor de un número, que se define como $P(A)$: $fr_A \xrightarrow[n\to\infty]{} P(A)$.

### Definición axiomática

$P$ es una probabilidad sobre S si para todo $A, B \subseteq S$:

- **Ax. 1**: $P(A) \ge 0$
- **Ax. 2**: $P(S) = 1$
- **Ax. 3**: si $A \cap B = \emptyset$ ⇒ $P(A \cup B) = P(A) + P(B)$

Las definiciones frecuencial y axiomática cumplen las mismas propiedades que la clásica.

### Propiedades (con su demostración a partir de los axiomas)

1. $P(\emptyset) = 0$ — S y ∅ son M.E. y $S \cup \emptyset = S$ ⇒ $P(S) + P(\emptyset) = P(S)$.
2. $P(A) + P(\bar A) = 1$ — $A \cup \bar A = S$ (Ax. 2) y A, $\bar A$ son M.E. (Ax. 3).
3. Si $A \subseteq B$ ⇒ $P(A) \le P(B)$ — $B = A \cup (B \cap \bar A)$ con M.E. ⇒ $P(B) = P(A) + P(B \cap \bar A) \ge P(A)$ (Ax. 1).
4. $P(A) \le 1$ — $A \subseteq S$ ⇒ $P(A) \le P(S) = 1$.
5. $P(A \cup B) = P(A) + P(B) - P(A \cap B)$ — $A \cup B = B \cup (A \cap \bar B)$ y $P(A \cap \bar B) = P(A) - P(A \cap B)$.
6. $P(A \cup B \cup C) = P(A) + P(B) + P(C) - P(A \cap B) - P(A \cap C) - P(B \cap C) + P(A \cap B \cap C)$ — se aplica la 5 a $(A \cup B) \cup C$ y la distributiva $(A \cup B) \cap C = (A \cap C) \cup (B \cap C)$.

Consecuencias muy usadas:
- $P(A \cap \bar B) = P(A) - P(A \cap B)$ ("sólo A").
- $P(\text{sólo uno}) = P(A \cup B) - P(A \cap B) = P(A) + P(B) - 2P(A \cap B)$.
- $P(\bar A \cap \bar B) = 1 - P(A \cup B)$ (ninguno, por De Morgan).

### Herramientas para organizar datos

- **Diagrama de Venn**: se completan las regiones (sólo A, A∩B, sólo B, ninguno) que suman 1.
- **Diagrama de Carroll / tabla de contingencia**: filas B, $\bar B$; columnas A, $\bar A$; totales marginales y total 1 (o el total de casos).
- **Diagrama de árbol**: para experimentos en etapas; se multiplican las probabilidades a lo largo de una rama y se suman las ramas favorables.

---

## 3. Probabilidad condicional

$$P(A/B) = \frac{P(A \cap B)}{P(B)}, \quad P(B) > 0$$

Es la probabilidad de A sabiendo que ocurrió B (el espacio muestral se "reduce" a B). En una tabla: se divide la celda por el total de la fila o columna que condiciona.

### Teorema de la multiplicación

$$P(A \cap B) = P(B)\,P(A/B) = P(A)\,P(B/A)$$

Para tres sucesos: $P(B_1 \cap B_2 \cap B_3) = P(B_1)\,P(B_2/B_1)\,P(B_3/B_1 \cap B_2)$, que es lo que se calcula recorriendo una rama de un diagrama de árbol.

### Propiedades de la condicional (ejercicios teóricos)

- $P(B/A) + P(\bar B/A) = 1$ si $P(A) > 0$ (también $P(A/B) + P(\bar A/B) = 1$).
- $P(A \cup B / C) = P(A/C) + P(B/C) - P(A \cap B / C)$ si $P(C) > 0$.
- Si $P(B/A) > P(B)$ entonces $P(\bar B/A) < P(\bar B)$.
- Si $A \subseteq B$: $P(B/A) = 1$ (siempre que ocurre A ocurre B) y $P(A/B) = P(A)/P(B)$.
- Si A y B son incompatibles: $P(B/A) = 0$.

---

## 4. Probabilidad total y Teorema de Bayes

Sea $\{A_1, \dots, A_n\}$ una **partición** de S: los $A_i$ son no vacíos, mutuamente excluyentes y su unión es S. Para cualquier $B \subseteq S$:

**Teorema de la probabilidad total**
$$P(B) = \sum_{i=1}^{n} P(A_i)\,P(B/A_i)$$

**Teorema de Bayes**
$$P(A_j/B) = \frac{P(A_j)\,P(B/A_j)}{\sum_{i=1}^{n} P(A_i)\,P(B/A_i)}$$

Para aplicar probabilidad total con A, B, C, los sucesos tienen que ser M.E. y su unión tiene que ser S. En un árbol: $P(B)$ es la suma de todas las ramas que terminan en B; Bayes es "rama favorable / suma de ramas que terminan en B". Las $P(A_i)$ son probabilidades **a priori** y las $P(A_j/B)$ son **a posteriori**.

---

## 5. Sucesos independientes

$$A \text{ y } B \text{ independientes} \iff P(A \cap B) = P(A)\,P(B)$$

Equivale a $P(A/B) = P(A)$ y $P(B/A) = P(B)$: la ocurrencia de uno no modifica la probabilidad del otro.

- **Extracciones con reposición** ⇒ independientes. **Sin reposición** ⇒ hay condicionamiento.
- Si A y B son independientes, también lo son A y $\bar B$, $\bar A$ y B, y $\bar A$ y $\bar B$. (Prueba: $P(A \cap \bar B) = P(A) - P(A)P(B) = P(A)P(\bar B)$.)
- **Independencia ≠ exclusión mutua**: si $P(A), P(B) > 0$ y A, B son M.E., entonces $P(A \cap B) = 0 \neq P(A)P(B)$, así que **no** son independientes. Recíprocamente, si son independientes no son M.E.
- **Tres sucesos mutuamente independientes**: además de la independencia de a pares, tiene que cumplirse $P(A \cap B \cap C) = P(A)P(B)P(C)$. La independencia de a pares **no alcanza** (Ej. 16: dos dados, A = "1° par", B = "2° par", C = "suma par": son independientes de a pares, pero $P(A \cap B \cap C) = 1/4 \neq 1/8$).
- Si A, B, C son mutuamente independientes: $P(A \cup B \cup C) = 1 - P(\bar A)P(\bar B)P(\bar C)$ ("al menos uno" = 1 − "ninguno").

Que $P(A \cap B) = 0$ no implica que A y B sean complementarios: además deberían cumplir $P(A) + P(B) = 1$ (por ejemplo, con 0,5 y 0,3 no lo son).

---

## 6. Ejemplos resueltos de la teoría

**Botellas con fallas**: P(A) = 0,15 (menos cantidad), P(B) = 0,10 (tapa), P(A∩B) = 0,02.
- No pasa la prueba (alguna falla): $P(A \cup B) = 0{,}15 + 0{,}10 - 0{,}02 = 0{,}23$.
- Sólo una falla: $P(A \cap \bar B) + P(\bar A \cap B) = 0{,}13 + 0{,}08 = 0{,}21$.
- Ninguna falla: $1 - 0{,}23 = 0{,}77$.

**Encuesta de envases** (tabla con H/M y A/B; total 150): $P(H) = 65/150 = 0{,}43$; $P(B) = 90/150 = 0{,}6$; $P(H \cap B) = 40/150 = 0{,}27$; $P(B/H) = 40/65 = 0{,}62$ (probabilidad condicional).

**Teorema de la multiplicación**: 70 % de mecánica y el 10 % de ellos desaprueba ⇒ $P(D \cap M) = 0{,}7 \cdot 0{,}1 = 0{,}07$.

**Probabilidad total**: planta M (60 %, 10 % fallado) y N (40 %, 5 % fallado) ⇒ $P(F) = 0{,}6\cdot0{,}1 + 0{,}4\cdot0{,}05 = 0{,}08$.

**Bayes (autos)**: Nacionales 40 % (15 % con aire), Europeos 30 % (25 %), Japoneses 30 % (35 %).
$P(A) = 0{,}06 + 0{,}075 + 0{,}105 = 0{,}24$; $P(J/A) = 0{,}105/0{,}24 = 0{,}4375$.

**Urna 3 rojas y 7 negras, extraer 2**:
- Sin reposición: $P(R_1 \cap N_2) = \frac{3}{10}\cdot\frac{7}{9} = \frac{7}{30}$.
- Con reposición: $P(R_1 \cap N_2) = \frac{3}{10}\cdot\frac{7}{10} = \frac{21}{100}$ (independientes: $P(N_2/R_1) = P(N_2)$).

**Urna 4 negras y 3 blancas, 3 extracciones sin reposición**: $P(B_1 \cap B_2 \cap B_3) = \frac{3}{7}\cdot\frac{2}{6}\cdot\frac{1}{5} = \frac{1}{35}$.

**Dado y moneda**: P("3" y "Cara") = 1/12, ya sea por Laplace (1 caso entre 12) o por independencia (1/6 · 1/2).

**¿Independientes?** P(AM I) = 0,6, P(Física) = 0,8 y el 15 % no aprobó ninguna ⇒ $P(A \cup F) = 0{,}85$ ⇒ $P(A \cap F) = 0{,}55 \neq 0{,}6\cdot0{,}8 = 0{,}48$ ⇒ **no** son independientes.

---

## 7. Práctica: ejercicios resueltos de la Guía de TP

| Ej. | Tema | Planteo / resultado |
|---|---|---|
| 3 | Tres monedas | S tiene 8 ternas equiprobables (1/8 cada una). A = "exactamente una cara", B = "al menos una cara": P(A) = 3/8, P(B) = 7/8; como A ⊆ B, P(A∩B) = 3/8, P(A∪B) = 7/8 y P(A/B) = 3/7. |
| 5 | Frascos de mermelada (12 % peso, 8 % tapa, 3 % ambas) | a) Exactamente una falla: 0,12 + 0,08 − 2·0,03 = **0,14**. b) No descartado: 1 − 0,17 = **0,83**. c) P(tapa / peso) = 0,03/0,12 = 0,25. d) P(peso / sin problema de tapa) = 0,09/0,92 ≈ 0,098. e) 0,12·0,08 ≠ 0,03 ⇒ no son independientes. |
| 6 | Blanco cuadrado de 2,5 m (probabilidad geométrica) | P = área favorable / área total. a) $\pi\cdot1^2/2{,}5^2 = 0{,}16\pi$. b) Corona entre 0,5 y 1 m: $\pi(1 - 0{,}25)/6{,}25 = 0{,}12\pi$. c) Dos disparos en el semiplano superior: 0,5·0,5 = 0,25. d) En distinto cuadrante: 1 − 4·(1/4)² = **0,75**. |
| 7 | Dado cargado (pares proporcionales a su valor) | 3·(1/6) + 2k + 4k + 6k = 1 ⇒ k = 1/24: P(2) = 1/12, P(4) = 1/6, P(6) = 1/4. Laplace **no** se aplica a los pares porque no son equiprobables. P(A) = 1/2; P(A∪C) = 1/2 + 1/6 = 2/3 (M.E.); $P(A^c \cap B^c) = P(C) = 1/6$; P(B − C) = P(B) = 2/3. |
| 8 | 6 varones (1/3 con anteojos) y 10 mujeres (1/5) | Tabla: A = 4, M = 10, A∩M = 2, total 16. a) P(A∪M) = (4 + 10 − 2)/16 = **3/4**. b) P(V∩$\bar A$) = 4/16 = **1/4** (es el complemento de a). |
| 9 | 3 motores de 10, 4 a inyección | Casos totales $\binom{10}{3} = 120$. a) Ninguno: $\binom{6}{3}/120 = 1/6$. b) A lo sumo uno: (20 + 60)/120 = **2/3**. c) Al menos dos: 1 − 2/3 = 1/3. También sale con el teorema de la multiplicación: 6/10·5/9·4/8 = 1/6. |
| 10 | Cumpleaños (8 personas) | Complemento: "todos en días distintos" = $\frac{365\cdot364\cdots358}{365^8} \approx 0{,}926$ ⇒ P(al menos 2 coinciden) ≈ **0,074**. Con 23 personas da ≈ 0,507. |
| 11 | Unión de tres sucesos | Demostración de la propiedad 6 (ver sección 2). |
| 12 | Reincidencia vs. educación (tabla de proporciones) | P(A) = 0,40, P(B) = 0,33, P(A∩B) = 0,10, P(A/B) = 0,10/0,33 = 0,303. P(A∪B) = 0,63 y P((A∪B)ᶜ) = 0,37. 0,10 ≠ 0,40·0,33 ⇒ no son independientes. |
| 13 | Traspaso entre oficinas (3M + 1V → 2M + 2V) | Probabilidad total: P(M₂) = 3/4·3/5 + 1/4·2/5 = **11/20**. |
| 14 | Demostraciones con condicional | Ver sección 3. |
| 15 | Cubos entre dos cajas (7a + 3v; 6a + 4v) | a) P(a de I y v de II) = 7/10·4/11 = 28/110 ≈ 0,2545. c) Que las cajas queden como al principio: 7/10·7/11 + 3/10·5/11 = 64/110 ≈ 0,58. |
| 16 | Independencia de a pares vs. mutua | Ver sección 5. |
| 17 | P(A∪B∪C) con independencia | $1 - P(\bar A)P(\bar B)P(\bar C)$ (De Morgan + independencia). |
| 19 | P(B/A) | Si A ⊆ B vale 1; si son incompatibles vale 0. |
| 20 | Dos dados, suma ≥ 8 | a) Con un 4 en el primero: P(X₂ ≥ 4) = **1/2**. b) Con un 4 en al menos uno: P = (5/36)/(11/36) = **5/11**. |
| 21 | Caminos A→B (3) y B→C (2), cada uno bloqueado con P = 0,1 | a) [1 − 0,1³]·[1 − 0,1²] = 0,999·0,99 = **0,98901**. b) Con el camino A₂ cerrado: [1 − 0,1²]·[1 − 0,1²] = **0,9801**. |
| 22 | Urna 7R y 3B, 3 extracciones sin reposición | a) R, R, B: 7/10·6/9·3/8 = **7/40**. b) Exactamente una blanca: 3 órdenes, cada uno de 7/40 ⇒ **21/40**. |
| 24 | Independencia y complementos | Ver sección 5. |
| 25 | Supervivencia (1/3 y 1/4, independientes) | Ambos: 1/12; al menos uno: 1/2; ninguno: 1/2; sólo la mujer: 1/4·2/3 = 1/6. |
| 26 | Tres cajoneras (plata-plata, plata-oro, oro-oro) | P(oro) = 1/2; Bayes: P(cajonera oro-oro / oro) = **2/3**. |
| 27 | Test diagnóstico (prevalencia 1/25; sensibilidad 98 %; falso positivo 3 %) | P(+) = 0,98·0,04 + 0,03·0,96 = 0,068; P(enfermo/+) = 0,0392/0,068 ≈ **0,58** (a priori 4 %, a posteriori 58 %). P(sano/−) = 0,96·0,97/0,932 ≈ 0,999. |
| 28 | Una pieza de cada caja (A: 3/8, B: 2/5, C: 4/10 defectuosas) | a) Todas defectuosas: 3/8·2/5·4/10 = **0,06**. b) Sólo una: **87/200**. c) P(es la de A / sólo una) = (3/8·3/5·6/10)/(87/200) = **9/29**. |
| 29 | Deporte (40 % de los hombres, 55 % de las mujeres; 70 % mujeres) | P(D) = 0,505; P(M/D) = 0,385/0,505 = **0,7623**. |
| 30 | Aerolínea (familia 30 %, amigos 25 %, solos 45 %) | P(N) = 0,15 + 0,175 + 0,1125 = 0,4375 ⇒ P(no nocturno) = **0,5625**; P(amigos / N) = 0,175/0,4375 = **0,4**. |
| 31 | Comisión de 3 entre 6 docentes | P(la inicial repetida es L / hay una inicial repetida) = **0,5**; P(la suma de antigüedades de 2 da 27) = 4/30. |

### Ejercicios de la clase de repaso

1. **Cursos del turno noche** (35, 25 y 18 alumnos; 3, 5 y 4 sin trabajo; total 78, de los cuales 12 sin trabajo):
   - P(no trabaja) = 12/78; P(no trabaja / 1° curso) = 3/35; P(3° curso / trabaja) = 14/66.
   - Cuatro estudiantes, dos sin trabajo y dos con trabajo: hay $\binom{4}{2} = 6$ órdenes ⇒ $6\cdot(11/13)^2(2/13)^2 \approx 0{,}102$ (se asume independencia porque la población es grande).
2. **Moneda y luego dado** (si sale cara, P(par) = 1/4): P(cara ∩ impar) = 1/2 · 3/4 = 3/8.
3. **Proveedores** (10 %, 30 %, 60 %; rechazos de 2 %, 0,4 % y 0,2 %): P(R) = 0,002 + 0,0012 + 0,0012 = 0,0044; P(3° / R) = 0,0012/0,0044 ≈ 0,273.
4. **Cerradura de 3 discos con dígitos de 0 a 5**: número que empiece con 3 y sea par: 1/6 · 1 · 1/2 = 1/12. Con una segunda cerradura independiente que abre con "153" (1/216): P(abrir) = 1/12 + 1/216 − 1/12·1/216 ≈ 0,0876.
5. A ⊆ B ⇒ P(A/B) = P(A)/P(B). Si son independientes ⇒ P(A/B) = P(A).
6. $P(A \cup C / B) = P(A/B) + P(C/B) - P(A \cap C / B)$.
7. Incompatibles: $A \cap B = \emptyset$. Independientes: $P(A \cap B) = P(A)P(B)$. Con P(A∩B) = 0, P(A) = 0,5 y P(B) = 0,3 no son complementarios, porque P(A) + P(B) ≠ 1.
8. Para usar probabilidad total con A, B, C, tienen que formar una partición: $P(D) = P(A)P(D/A) + P(B)P(D/B) + P(C)P(D/C)$.

### Actividades de las introducciones (partes 1 y 2)

- Diagrama de Venn con sólo A = 0,20, A∩B = 0,30, sólo B = 0,10 y ninguno = 0,40: P(A) = 0,5; P(B∩$\bar A$) = 0,1; P(A∪B) = 0,6; P(B/A) = 0,6; P($\bar A$/B) = 0,25.
- Fallas: el 30 % tiene A, el 20 % tiene B y el 65 % no tiene fallas ⇒ ambas = 0,15; una sola = 0,20; fallado = 0,35; P(B/A) = 0,5; P(A/$\bar B$) = 0,1875.
- Divisiones A, B, C (25 %, 35 %, 40 %; 20 %, 30 % y 25 % desaprobados): P(D) = 0,255; P(C/D) ≈ 0,392.
- Fallas sólo A = 10 %, sólo B = 20 % y sin fallas = 55 % ⇒ ambas = 0,15.
- Pozo potable con P = 0,1: que el primero potable sea el n-ésimo pozo = $0{,}9^{\,n-1}\cdot0{,}1$ (n = 2: 0,09).
- Tipos de sangre (A 40 %, B 20 %, O 30 %, AB 10 %; dos personas independientes): mismo tipo = 0,4² + 0,2² + 0,3² + 0,1² = 0,30; tipos distintos = 0,70.

---

## 8. Estrategia para resolver problemas

1. Definir el experimento y nombrar los sucesos con letras.
2. Traducir el enunciado: "y" → ∩, "o / alguno / al menos uno" → ∪, "ninguno" → $\bar A \cap \bar B$, "sólo A" → $A \cap \bar B$, "si / sabiendo que / entre los que" → condicional.
3. Elegir la herramienta: Laplace si hay equiprobabilidad; tabla o Venn si hay dos características; árbol si hay etapas; probabilidad total + Bayes si hay una partición y se pide "la causa" dado el efecto.
4. Para "al menos uno", conviene casi siempre el complemento: 1 − P(ninguno).
5. Revisar si hay reposición o independencia antes de multiplicar probabilidades.

---

[← Volver al menú principal](../README.md)
