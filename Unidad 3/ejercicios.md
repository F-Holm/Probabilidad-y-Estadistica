# Unidad 3 — Ejercicios resueltos

Ejercicios de la **Práctica 3 de la Guía de TP** (Variables aleatorias especiales).

Cada ejercicio tiene un botón **Solución**. Al abrirlo aparece la respuesta y, arriba de ella, un segundo botón **Solución paso a paso** con el desarrollo completo.

Notación: Φ(z) = P(Z < z) para Z ~ N(0; 1). Los valores numéricos se obtienen con tabla o con la app *Probability Distributions*.

> **Referencias:** ⭐ = ejercicio sugerido como prioritario en los apuntes de la cátedra.

---

### 1) Refrigeradores devueltos

Diez refrigeradores de cierto tipo han sido devueltos a un distribuidor debido a la presencia de un ruido oscilante agudo cuando el refrigerador está funcionando. Supongamos que 4 de estos 10 refrigeradores tienen compresores defectuosos y los otros 6 tienen problemas más leves. Se examinan al azar 5 de estos 10 refrigeradores y se define la variable aleatoria X: "el número, entre los 5 examinados, que tienen un compresor defectuoso". Indicar:

- a) la distribución de la variable aleatoria X.
- b) la probabilidad de que no todos tengan fallas leves.
- c) la probabilidad de que a lo sumo cuatro tengan fallas de compresor.

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

a) Se extrae sin reposición de un lote finito ⇒ **hipergeométrica** con N = 10, K = 4, n = 5.

b) "No todos leves" = al menos uno con compresor defectuoso: $1 - P(X = 0) = 1 - \frac{\binom65}{\binom{10}5} = 1 - \frac6{252} = 0{,}9762$.

c) Sólo hay 4 compresores defectuosos, así que X ≤ 4 siempre ⇒ P = 1.

</details>

**Respuesta:**

- a) X ~ H(N = 10, K = 4, n = 5)
- b) 0,9762
- c) 1

</details>

---

### 2) El asado de Laura

Un grupo de amigos del secundario se reúne en la casa de Laura para comer un asado. En este grupo hay 6 varones y 8 mujeres, contando a Laura. De las mujeres, 5 estudian Letras y el resto Exactas, mientras que de los varones sólo uno estudia Letras y el resto Exactas.

- a) Si las primeras en llegar a la casa son tres chicas, ¿cuál es la probabilidad de que las tres estudien lo mismo que Laura?
- b) Si tres cualesquiera de ellos hacen el asado, ¿cuál es la probabilidad de que estudien lo mismo?
- c) Si se seleccionan 2 al azar de este conjunto de amigos y se define la variable aleatoria X: "cantidad de amigos que estudian Letras entre los dos elegidos", hallar el valor esperado y la varianza de X.

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

a) Laura está en su casa, así que las que llegan son 3 de las otras 7 mujeres. La respuesta de la guía (4/35) supone que **Laura estudia Letras**: entonces quedan 4 de Letras y 3 de Exactas ⇒ $\frac{\binom43}{\binom73} = \frac4{35}$.

(Si estudiara Exactas, sólo quedarían 2 de Exactas y la probabilidad sería 0.)

b) De los 14: 6 de Letras y 8 de Exactas. $\frac{\binom63 + \binom83}{\binom{14}3} = \frac{20 + 56}{364} \approx 0{,}2088$.

c) Hipergeométrica con N = 14, K = 6, n = 2:
- $E = n\frac KN = \frac{12}{14} = \frac67$
- $V = n\frac KN\left(1 - \frac KN\right)\frac{N-n}{N-1} = 2\cdot\frac6{14}\cdot\frac8{14}\cdot\frac{12}{13} = \frac{288}{637}$

</details>

**Respuesta:**

- a) 4/35
- b) 0,2088
- c) E = 6/7, V = 288/637

</details>

---

### 3) Truco

En una partida de truco (mazo de 40 cartas: 4 palos de 10 cartas cada uno), asumiendo que el mazo se encuentra bien mezclado, se reparte una mano de cartas (3 cartas a cada jugador).

- a) Hallar la probabilidad de que el jugador que recibe las primeras tres cartas tenga envido (dos cartas del mismo palo y una diferente).
- b) Hallar la probabilidad de que el primer jugador tenga flor (tres cartas del mismo palo).
- c) Hallar la probabilidad de que ambos jugadores tengan flor.
- d) Hallar la probabilidad de que el primer jugador no tenga ni flor ni envido.

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

Manos posibles: $\binom{40}3 = 9880$.

a) Se elige el palo repetido (4), 2 cartas de ese palo ($\binom{10}2$ = 45) y una de los otros 30: $\frac{4\cdot45\cdot30}{9880} = \frac{135}{247} \approx 0{,}5466$.

b) $\frac{4\binom{10}3}{9880} = \frac{480}{9880} \approx 0{,}04858$.

c) Después de una flor quedan 37 cartas: 7 del palo usado y 10 de cada uno de los otros 3.

$P = 0{,}04858\cdot\frac{3\binom{10}3 + \binom73}{\binom{37}3} = 0{,}04858\cdot\frac{395}{7770} \approx 0{,}00247$.

d) Es el complemento de a) y b) (tres palos distintos): $1 - 0{,}5466 - 0{,}0486 = 0{,}40486$.

</details>

**Respuesta:**

- a) 135/247
- b) 0,04858
- c) 0,00247
- d) 0,40486

</details>

---

### 4) Sobreventa de pasajes ⭐

La compañía de aviación *GranJet* ha determinado, mediante un estudio estadístico, que el 4 % de los pasajeros que reservan un viaje Buenos Aires–Misiones no se presentan a tomar el vuelo. Un día de mucha demanda de pasajes, la empresa decide vender 72 pasajes de un vuelo con capacidad para 70 pasajeros. ¿Cuál es la probabilidad de que puedan viajar todos los pasajeros que se presentan a tomar el vuelo?

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

X = pasajeros que se presentan ~ Bin(72; 0,96). Todos viajan si X ≤ 70:

$P(X \le 70) = 1 - P(71) - P(72) = 1 - 72\cdot0{,}96^{71}\cdot0{,}04 - 0{,}96^{72} \approx 0{,}78836$.

</details>

**Respuesta:** 0,78836

</details>

---

### 5) Pinchaduras ⭐

Se ha probado que el 25 % de los neumáticos de motocicleta sufren pinchaduras en caminos de ripio durante los primeros 1000 km de uso. ¿Cuál es la probabilidad de que, entre los próximos 6 neumáticos que se prueben:

- a) al menos 2 sufran pinchaduras?
- b) a lo sumo 3 no sufran pinchaduras?
- c) no se supere el número esperado de pinchaduras?

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

X = pinchados ~ Bin(6; 0,25).

a) $1 - P(0) - P(1) = 1 - 0{,}75^6 - 6\cdot0{,}25\cdot0{,}75^5 \approx 0{,}466$.

b) "No pinchados ≤ 3" ⇔ X ≥ 3 ⇒ $P(X \ge 3) \approx 0{,}169$. La guía da 0,9624, que es $P(X \le 3)$, o sea "a lo sumo 3 **sufran** pinchaduras".

c) E(X) = 6·0,25 = 1,5 ⇒ $P(X \le 1) \approx 0{,}534$.

</details>

**Respuesta:**

- a) 0,466
- b) 0,169 (con la lectura de la guía, 0,9624)
- c) 0,534

</details>

---

### 6) Motores de cuatriciclos ⭐

Al probar motores para cuatriciclos se encontró que el 5 % no superaba la prueba.

- a) Hallar la probabilidad de que, en los próximos 5 motores, al menos uno no pase la prueba.
- b) Hallar el número de motores que se espera que pasen la prueba entre los próximos 20.
- c) Hallar la probabilidad de que no todos, pero sí la mayoría de los próximos 7 motores, no pasen la prueba.

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

a) $1 - 0{,}95^5 = 0{,}22622$

b) Pasan ~ Bin(20; 0,95) ⇒ E = 19

c) Fallan ~ Bin(7; 0,05). "La mayoría pero no todos" = 4, 5 o 6 ⇒ $\sum_{k=4}^6\binom7k0{,}05^k0{,}95^{7-k} \approx 0{,}00019$

</details>

**Respuesta:**

- a) 0,22622
- b) 19
- c) 0,00019

</details>

---

### 7) Proyectos de calidad y expansión ⭐

En una empresa (con más de 2000 empleados), el 30 % de los empleados está en un proyecto de calidad, el 50 % está en un proyecto de expansión y el 70 % está trabajando en al menos uno de estos proyectos. Se seleccionan al azar cinco empleados de esta empresa para una encuesta de satisfacción.

- a) Hallar la probabilidad de que al menos dos de los seleccionados estén exactamente en un proyecto.
- b) Hallar la probabilidad de que a lo sumo tres estén en ambos proyectos.
- c) Hallar la probabilidad de que todos los seleccionados estén en algún proyecto.

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

P(ambos) = 0,3 + 0,5 − 0,7 = 0,1; P(exactamente uno) = 0,7 − 0,1 = 0,6. La empresa es grande, así que se toman los 5 como ensayos independientes (binomial).

a) X ~ Bin(5; 0,6): $1 - 0{,}4^5 - 5\cdot0{,}6\cdot0{,}4^4 = 0{,}91296$

b) Y ~ Bin(5; 0,1): $1 - P(4) - P(5) = 0{,}99954$

c) $0{,}7^5 = 0{,}16807$

</details>

**Respuesta:**

- a) 0,91296
- b) 0,99954
- c) 0,16807

</details>

---

### 8) Esperanza y varianza de la binomial (T)

(T) Sea X una variable aleatoria con distribución Binomial de parámetros n y p.

- a) Demostrar que E(X) = np.
- b) Demostrar que V(X) = np(1 − p).
- c) ¿Existen valores de probabilidad p para los cuales se cumpla que V(X) = 0?

Considerando un valor de n fijo:

- d) ¿Para qué valores de p es máxima E(X)?
- e) ¿Para qué valores de p es máxima V(X)?

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

$X = \sum X_i$ con $X_i$ Bernoulli(p) independientes, con E = p y V = p(1 − p).

a) $E(X) = \sum E(X_i) = np$.

b) Por independencia, $V(X) = \sum V(X_i) = np(1-p)$.

c) $np(1-p) = 0 \Leftrightarrow p = 0$ o $p = 1$ (no hay aleatoriedad).

d) np crece con p ⇒ es máxima en p = 1.

e) p(1 − p) es una parábola con vértice en p = ½.

</details>

**Respuesta:**

- c) p = 0 o p = 1
- d) p = 1
- e) p = 0,5

</details>

---

### 9) Fórmula recursiva de la binomial (T)

(T) Sea X una variable aleatoria binomial con parámetros n y p. Demostrar que:

$$P(X = k+1) = \frac{(n-k)\,p}{(k+1)(1-p)}\,P(X = k)$$

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

Se hace el cociente:

$$\frac{P(k+1)}{P(k)} = \frac{\binom n{k+1}p^{k+1}(1-p)^{n-k-1}}{\binom nkp^k(1-p)^{n-k}} = \frac{n!/((k+1)!(n-k-1)!)}{n!/(k!(n-k)!)}\cdot\frac p{1-p} = \frac{n-k}{k+1}\cdot\frac p{1-p}$$

</details>

**Respuesta:** queda demostrada la fórmula, que sirve para calcular las probabilidades una a partir de la anterior.

</details>

---

### 10) Cabina de peaje ⭐

Los autos que pasan por cierta cabina de peaje siguen un proceso de Poisson con intensidad λ = 20 autos por hora. El peaje cuesta 45 pesos, pero todos los automovilistas pagan con billetes de 50 pesos. Al empezar el día, Fabián (que trabaja en la cabina) cuenta solamente con un billete de 5 pesos.

- a) ¿Cuál es la probabilidad de que algún automovilista se quede sin vuelto en los primeros 5 minutos?
- b) Fabián quiere salir de la cabina para tomar un café. ¿Cuánto debería tardar como mucho, si quiere que la probabilidad de que en su ausencia no aparezca ningún auto sea de 1/10?

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

a) Cada auto recibe 5 pesos de vuelto. Con un solo billete, al primer auto le puede dar vuelto y al segundo ya no (los billetes de 50 pesos no sirven para dar 5 pesos). Hay problema si llegan 2 o más.

En 5 min: λ = 20·(5/60) = 5/3. $P(X \ge 2) = 1 - e^{-5/3}(1 + \frac53) \approx 0{,}4963$.

b) $P(X = 0) = e^{-20t} = 0{,}1 \Rightarrow t = \frac{\ln10}{20}$ h ≈ 0,115 h ≈ 6,9 min.

</details>

**Respuesta:**

- a) 0,4963
- b) ≈ 6,9 minutos

</details>

---

### 11) Sala de emergencias de Moquehue ⭐

La cantidad de pacientes que asisten a la sala de emergencias de la localidad de Moquehue semanalmente sigue una distribución de Poisson con media 3. Se pueden asistir 4 pacientes por semana; los que no pueden ser asistidos se derivan a la localidad de Villa Pehuenia.

- a) ¿Cuál es la probabilidad de derivar algún paciente esta semana?
- b) ¿Cuál es el número esperado de pacientes que se derivan semanalmente?
- c) ¿Cuántos pacientes se deberían poder asistir para garantizar que no se realicen derivaciones el 90 % de las semanas?

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

X ~ Po(3).

a) $P(X \ge 5) = 1 - \sum_{k=0}^4\frac{3^k}{k!}e^{-3} \approx 0{,}185$.

b) Derivados Y = máx(X − 4, 0): $E(Y) = \sum_{k\ge5}(k-4)P(X = k) = 1\cdot0{,}1008 + 2\cdot0{,}0504 + 3\cdot0{,}0216 + \dots \approx 0{,}32$.

c) P(X ≤ 4) = 0,815 no alcanza; P(X ≤ 5) = 0,916 ≥ 0,90 ⇒ 5 pacientes.

</details>

**Respuesta:**

- a) 0,185
- b) ≈ 0,32
- c) 5 pacientes

</details>

---

### 12) Fila del ANSES ⭐

Las llegadas a la fila de espera de una oficina del ANSES ocurren según un proceso de Poisson, de modo tal que la probabilidad de que no haya arribos en 5 minutos es e⁻¹.

- a) Determinar qué cantidad de personas se espera que lleguen a la fila en una hora.
- b) Calcular la probabilidad de que pasen más de 6 minutos entre el arribo de dos personas consecutivas a la fila.

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

$e^{-\lambda} = e^{-1}$ ⇒ λ = 1 en 5 min ⇒ α = 0,2 por min.

a) En 60 min: λ = 0,2·60 = 12.

b) El tiempo entre arribos es Exp(0,2) ⇒ $P(Y > 6) = e^{-1{,}2} \approx 0{,}3012$.

</details>

**Respuesta:**

- a) 12 personas
- b) 0,3012

</details>

---

### 13) Fórmula recursiva de Poisson (T)

(T) Demostrar que si X ~ Po(λ), se cumple que:

$$P(X = k+1) = \frac{\lambda}{k+1}\,P(X = k)$$

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

$P(k+1) = \frac{e^{-\lambda}\lambda^{k+1}}{(k+1)!} = \frac\lambda{k+1}\cdot\frac{e^{-\lambda}\lambda^k}{k!} = \frac\lambda{k+1}P(k)$.

</details>

**Respuesta:** queda demostrada la fórmula.

</details>

---

### 14) Uniforme con datos ⭐

De una variable aleatoria uniforme se sabe que su valor esperado es 15 y que P(13 ≤ X ≤ 18,5) = 0,55. Hallar su varianza y P(X ≤ 13).

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

$\frac{a+b}2 = 15$ y $\frac{18{,}5 - 13}{b - a} = 0{,}55 \Rightarrow b - a = 10$ ⇒ X ~ U(10; 20).

$V = \frac{10^2}{12} = \frac{25}3$. $P(X \le 13) = \frac{13 - 10}{10} = 0{,}3$.

</details>

**Respuesta:** V = 25/3, P(X ≤ 13) = 0,3

</details>

---

### 15) Peso de bultos ⭐

El peso de ciertos bultos se distribuye uniformemente en el intervalo (a, b). Supongamos que el 20 % de los bultos pesa menos de 4 kg y el 40 % más de 8 kg.

- a) Hallar la probabilidad de que un bulto elegido al azar pese entre 5 y 9 kg.
- b) Si se eligen ocho de estos bultos aleatoriamente, hallar la probabilidad de que ninguno pese entre 5 y 9 kg.
- c) Hallar la cantidad de bultos, de estos ocho, que se espera que pesen entre 5 y 9 kg.

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

Con L = b − a: 4 − a = 0,2L y b − 8 = 0,4L. Sumando: L − 4 = 0,6L ⇒ L = 10, a = 2, b = 12.

a) (9 − 5)/10 = 0,4

b) Bin(8; 0,4): $0{,}6^8 \approx 0{,}0168$

c) 8·0,4 = 3,2

</details>

**Respuesta:**

- a) 0,4
- b) 0,0168
- c) 3,2

</details>

---

### 16) Amplificadores (mezcla de exponenciales) ⭐

La duración de un amplificador electrónico está modelada como una variable Exponencial. Si el 10 % de los amplificadores tiene una duración media de 20000 horas, mientras que la del resto es de 50000 horas, hallar:

- a) la proporción de amplificadores que fallan antes de las 60000 horas.
- b) la probabilidad de que, si la duración de un amplificador supera las 20000 horas, supere las 40000 horas.

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

Probabilidad total con las dos exponenciales (λ = 1/20000 y λ = 1/50000):

a) $0{,}1(1 - e^{-3}) + 0{,}9(1 - e^{-1{,}2}) = 0{,}0950 + 0{,}6289 = 0{,}7239$.

b) $\frac{P(X > 40000)}{P(X > 20000)} = \frac{0{,}1e^{-2} + 0{,}9e^{-0{,}8}}{0{,}1e^{-1} + 0{,}9e^{-0{,}4}} \approx 0{,}6529$. Ojo: acá **no** se aplica la falta de memoria, porque la mezcla de dos exponenciales no es exponencial.

</details>

**Respuesta:**

- a) 0,7239
- b) 0,6529

</details>

---

### 17) Lámparas

La duración de ciertas lámparas eléctricas se distribuye exponencialmente. Se sabe, además, que el 80 % dura más de 800 horas. ¿Cuántas lámparas se deben extraer como mínimo para que la probabilidad de que alguna funcione más de 600 horas sea al menos del 90 %?

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

$e^{-800\lambda} = 0{,}8 \Rightarrow P(X > 600) = e^{-600\lambda} = 0{,}8^{600/800} = 0{,}8^{0{,}75} \approx 0{,}8459$.

$1 - (1 - 0{,}8459)^n \ge 0{,}9 \Rightarrow 0{,}1541^n \le 0{,}1 \Rightarrow n \ge \frac{\ln0{,}1}{\ln0{,}1541} \approx 1{,}23$ ⇒ n = 2.

</details>

**Respuesta:** n ≥ 2

</details>

---

### 18) Clases sociales por ingreso ⭐

El ingreso anual de los jefes de familia de una cierta ciudad se puede modelar con una distribución Exponencial con λ = 0,00005. Para clasificar a los hogares de esa ciudad se ha decidido dividir a la población en 5 grupos igualmente numerosos: clase baja, clase media-baja, clase media, clase media-alta y clase alta, de modo que el 20 % de la población pertenezca a cada uno de ellos. Es decir, el 20 % de los hogares con menores ingresos entra dentro de la clase baja, el segundo 20 % será clasificado dentro de la clase media-baja, etc. Hallar los salarios que indican el salto de categoría.

**Observación:** los valores hallados representan los cuantiles correspondientes a 0,20, 0,40, 0,60 y 0,80, respectivamente.

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

$F(x_q) = 1 - e^{-\lambda x_q} = q \Rightarrow x_q = \frac{-\ln(1-q)}{\lambda} = -20000\ln(1-q)$.

</details>

**Respuesta:** 4462,87; 10216,51; 18325,81; 32188,75

</details>

---

### 19) Escalar una exponencial

Sabiendo que X ~ Exp(λ), hallar la distribución de Y = cX.

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

$P(Y > y) = P(X > y/c) = e^{-(\lambda/c)y}$ ⇒ es la función de supervivencia de una exponencial.

</details>

**Respuesta:** Y ~ Exp(λ/c)

</details>

---

### 20) Pilas ⭐

La duración de ciertas pilas se distribuye en forma Exponencial. Se sabe, además, que el 20 % tiene una duración inferior a 400 horas. ¿Cuál es la probabilidad de que, entre cinco pilas elegidas al azar, todas duren menos de 500 horas?

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

$e^{-400\lambda} = 0{,}8 \Rightarrow P(X < 500) = 1 - 0{,}8^{1{,}25} \approx 0{,}2434$. Las 5 independientes: $0{,}2434^5 \approx 0{,}00085$.

</details>

**Respuesta:** 0,00085

</details>

---

### 21) Baterías de dos fábricas ⭐

Las baterías de una marca de celulares pueden provenir de dos fábricas diferentes, H y M. El 60 % de las pilas vendidas son producidas por la fábrica H y tienen una duración (en miles de horas) Exponencial cuyo valor esperado es μ = 100. El resto son producidas por la otra fábrica, con una duración (en miles de horas) con distribución Uniforme [80, 130].

- a) Si una batería del primer fabricante dura más de 70 000 horas, ¿qué probabilidad hay de que dure más de 90 000 horas?
- b) Calcular la probabilidad de que una batería vendida del stock dure a lo sumo 90 000 horas.
- c) Si efectivamente la batería seleccionada dura a lo sumo 90 000 horas, ¿cuál sería la probabilidad de que proviniera de la fábrica H?

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

a) Falta de memoria: $P(X > 90 / X > 70) = P(X > 20) = e^{-0{,}2} = 0{,}8187$.

b) $P_H = 1 - e^{-0{,}9} = 0{,}5934$ y $P_M = \frac{90 - 80}{50} = 0{,}2$ ⇒ $0{,}6\cdot0{,}5934 + 0{,}4\cdot0{,}2 = 0{,}436$.

c) Bayes: $0{,}3560/0{,}436 = 0{,}8165$.

</details>

**Respuesta:**

- a) 0,8187
- b) 0,436
- c) 0,8165

</details>

---

### 22) Cajero de banco ⭐

El número de clientes que atiende un cajero de banco sigue una distribución de Poisson con intensidad de 2 clientes cada 15 minutos.

- a) ¿Cuál es la probabilidad de que el tiempo de atención de un cliente resulte superior a 20 minutos?
- b) ¿Cuál es la probabilidad de que se demore más de 10 minutos en atender un cliente?
- c) Si se demoró más de media hora en atender a un cliente, hallar la probabilidad de que esa atención se demore más de 40 minutos.
- d) Comparar los resultados de los dos ítems anteriores y explicar.
- e) ¿Cuál es la probabilidad de que en menos de 4 horas se atiendan 30 clientes?

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

El tiempo de atención es T ~ Exp(2/15).

a) $e^{-20\cdot2/15} = e^{-8/3} \approx 0{,}0695$

b) $e^{-4/3} \approx 0{,}2636$

c) Falta de memoria: P(T > 40 / T > 30) = P(T > 10) = 0,2636

d) Dan igual por la propiedad de falta de memoria.

e) En 240 min, N ~ Po(32). Atender 30 clientes en menos de 4 h ⇔ N(240) ≥ 30 ⇒ ≈ 0,662. La guía da 0,5939, que es P(N ≥ 31).

</details>

**Respuesta:**

- a) 0,06948
- b) 0,2636
- c) 0,2636
- d) falta de memoria
- e) ≈ 0,662 (la guía da 0,5939)

</details>

---

### 23) Paquetes de mensajes

Los mensajes que llegan al nodo A de un sistema de comunicación de datos son puestos en paquetes antes de ser transmitidos por la red. La llegada de mensajes a este nodo sigue una distribución de Poisson con una intensidad de 30 mensajes por minuto, y se utilizan 6 mensajes para formar un paquete.

- a) ¿Cuál es el tiempo promedio necesario para formar un paquete, esto es, el tiempo que transcurre hasta que llegan los seis mensajes al nodo?
- b) ¿Cuál es la varianza del tiempo necesario para formar el paquete?
- c) ¿Cuál es la probabilidad de formar un paquete en menos de 12 segundos?

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

El tiempo hasta el 6.° evento es la suma de 6 exponenciales independientes ⇒ T ~ Gamma(α = 6, λ = 0,5/s).

a) E = α/λ = 12 s

b) V = α/λ² = 24 s²

c) T < 12 ⇔ hay al menos 6 llegadas en 12 s: N ~ Po(6) ⇒ $1 - P(N \le 5) \approx 0{,}5543$

</details>

**Respuesta:**

- a) 12 s
- b) 24 s²
- c) 0,5543

</details>

---

### 24) Máquina parada (Gamma)

El tiempo semanal Y (en horas) durante el cual cierta máquina industrial no funciona tiene una distribución Gamma con α = 3 y λ = 0,5. La pérdida semanal L (en cientos de pesos) para la industria debido a esta baja está dada por:

L = 30Y + 8

(3000 pesos por hora en que la máquina no funciona, más 800 pesos de costo fijo). Calcular la probabilidad de que se pierdan más de 18 800 pesos en una semana.

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

L > 188 ⇔ 30Y > 180 ⇔ Y > 6. Para una Gamma con α entero: P(Y > 6) = P(Po(λ·6 = 3) ≤ 2) = $e^{-3}(1 + 3 + 4{,}5) \approx 0{,}4232$.

</details>

**Respuesta:** 0,42319

</details>

---

### 25) Pérdida esperada con Gamma

El tiempo semanal Y (en horas) durante el cual cierta máquina industrial no funciona tiene distribución Gamma con parámetros α = 100 y λ = 20. La pérdida en pesos para la operación industrial está dada por L = 20Y − 3Y². Calcular el valor esperado de L.

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

E(Y) = 100/20 = 5 y V(Y) = 100/400 = 0,25 ⇒ E(Y²) = 0,25 + 25 = 25,25.

E(L) = 20·5 − 3·25,25 = 100 − 75,75 = 24,25.

</details>

**Respuesta:** E(L) = 24,25

</details>

---

### 26) Componentes en serie y en paralelo

Dos componentes idénticas, A y B, funcionan en forma independiente en un sistema S. El tiempo hasta la ocurrencia de una falla para cada una de estas componentes puede considerarse una variable aleatoria con distribución Exponencial de parámetro α = (100 hs)⁻¹. Obtener las funciones de distribución y de densidad de probabilidad para el tiempo T hasta la ocurrencia de una falla del sistema S:

- a) considerando que las componentes están conectadas en serie.
- b) considerando que las componentes están conectadas en paralelo.

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

a) En serie, falla cuando falla la primera: T = mín. $P(T > t) = e^{-t/100}e^{-t/100} = e^{-t/50}$ ⇒ Exp(1/50).

b) En paralelo, falla cuando fallan ambas: T = máx. $F(t) = (1 - e^{-t/100})^2$; derivando, $f(t) = \frac1{50}e^{-t/100} - \frac1{50}e^{-t/50}$.

</details>

**Respuesta:**

- a) T ~ Exp(1/50 h)
- b) F = (1 − e^{−t/100})², f = (1/50)e^{−t/100} − (1/50)e^{−t/50}

</details>

---

### 27) Normal N(5; 10) ⭐

Sea X una variable aleatoria Normal con μ = 5 y σ = 10. Hallar:

- a) P(X < 0), P(X > 10) y P(X ≥ 15).
- b) P(−20 < X < 15) y P(−5 ≤ X ≤ 30).
- c) el valor de x tal que P(X > x) = 0,05.
- d) el valor de x tal que P(X < x) = 0,23.

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

Se estandariza: z = (x − 5)/10.

a) Φ(−0,5) = 0,3085; 1 − Φ(0,5) = 0,3085; 1 − Φ(1) = 0,1587.

b) Φ(1) − Φ(−2,5) = 0,8351; Φ(2,5) − Φ(−1) = 0,8351.

c) z₀,₉₅ = 1,645 ⇒ x = 5 + 16,45 = 21,45.

d) z₀,₂₃ ≈ −0,739 ⇒ x ≈ −2,39.

</details>

**Respuesta:**

- a) 0,3085; 0,3085; 0,1587
- b) 0,8351 ambas
- c) 21,45
- d) −2,39

</details>

---

### 28) Propiedades de la normal

Sea X ~ N(μ, σ²).

- a) Mostrar que P(|X − μ| ≤ 1,24σ) = 0,785.
- b) Hallar el valor de c (en términos de σ) que cumple P(μ − c ≤ X ≤ μ + c) = 0,95.

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

a) $P(-1{,}24 \le Z \le 1{,}24) = 2\Phi(1{,}24) - 1 = 2\cdot0{,}8925 - 1 = 0{,}785$.

b) $2\Phi(c/\sigma) - 1 = 0{,}95 \Rightarrow \Phi(c/\sigma) = 0{,}975 \Rightarrow c = 1{,}96\sigma$.

</details>

**Respuesta:**

- a) 0,785
- b) c = 1,96σ

</details>

---

### 29) Calidad seis sigma

Se dice que un proceso es de calidad seis sigma (una metodología de mejora de procesos centrada en la reducción de su variabilidad, que consigue reducir o eliminar los defectos o fallas en la entrega de un producto o servicio al cliente) si la media del proceso está a menos de seis desviaciones estándar de la especificación más cercana. Supongamos que la distribución de las mediciones es Normal.

- a) Si la esperanza del proceso está centrada entre las especificaciones superior e inferior, a una distancia de tres desviaciones estándar de cada una de ellas, ¿cuál es la probabilidad de que el producto no cumpla con las especificaciones?
- b) Si la media del proceso se desplaza hacia arriba, respecto de la del ítem (a), en 1,5 desviaciones estándar, ¿cuál es la probabilidad de que un producto no cumpla con las especificaciones?

Expresar las respuestas en partes por millón.

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

a) Fuera de μ ± 3σ: 2(1 − Φ(3)) = 0,0027 ⇒ 2700 ppm.

b) Ahora los límites quedan a 1,5σ (arriba) y 4,5σ (abajo): (1 − Φ(1,5)) + Φ(−4,5) ≈ 0,0668 + 0,0000034 ≈ 0,0668 ⇒ ≈ 66 810 ppm.

</details>

**Respuesta:**

- a) 0,0027 (2700 ppm)
- b) 0,0668 (≈ 66 810 ppm)

</details>

---

### 30) Peso de los alumnos ~ N(75; 7) ⭐

La distribución de los pesos de los alumnos varones de una facultad es aproximadamente Normal, con media μ = 75 kg y desviación típica 7 kg.

- a) Hallar la probabilidad de que un alumno, elegido al azar, pese más de 95 kilos.
- b) Estimar el número de alumnos, entre los 15 000 de esta facultad, con peso entre 80 y 95 kilos.
- c) Calcular el peso no superado por el 10 % de los alumnos.
- d) Si se seleccionan diez alumnos de esta población, hallar la probabilidad de que al menos la mitad tengan pesos superiores a 80 kg.

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

a) $1 - \Phi(20/7) = 1 - \Phi(2{,}857) \approx 0{,}0021$.

b) $\Phi(2{,}857) - \Phi(0{,}714) = 0{,}99786 - 0{,}76247 = 0{,}2354$ ⇒ 15000·0,2354 ≈ 3531 alumnos.

c) $75 + z_{0{,}1}\cdot7 = 75 - 1{,}2816\cdot7 \approx 66{,}03$ kg.

d) p = P(X > 80) = 0,2375; Y ~ Bin(10; 0,2375) ⇒ P(Y ≥ 5) ≈ 0,0644. La guía da 0,0699 porque redondea distinto el valor de z.

</details>

**Respuesta:**

- a) 0,0021
- b) ≈ 3531
- c) ≈ 66 kg
- d) ≈ 0,064 (la guía da 0,0699)

</details>

---

### 31) Longitud de piezas ⭐

La longitud de ciertas piezas fabricadas por una máquina se distribuye normalmente. Se sabe que el 15 % de las piezas mide menos de 13 mm y el 10 % mide más de 14 mm. Una pieza se considera no apta para un proceso de ensamble si mide menos de 12,8 mm o más de 13,8 mm. Además, el embalaje del producto se realiza en cajas que contienen 12 bolsas de 10 piezas cada una.

- a) ¿Cuál es la probabilidad de que una pieza seleccionada al azar no sea apta?
- b) Un cliente que recibe una bolsa de 10 piezas decide la aceptación del pedido si encuentra a lo sumo una pieza no apta. ¿Cuál es la probabilidad de que el pedido no sea rechazado?

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

$\frac{13 - \mu}\sigma = -1{,}0364$ y $\frac{14 - \mu}\sigma = 1{,}2816$. Restando: $\frac1\sigma = 2{,}318$ ⇒ σ ≈ 0,4314 y μ ≈ 13,447.

a) $\Phi\left(\frac{12{,}8 - 13{,}447}{0{,}4314}\right) + 1 - \Phi\left(\frac{13{,}8 - 13{,}447}{0{,}4314}\right) = \Phi(-1{,}50) + 1 - \Phi(0{,}818) \approx 0{,}0668 + 0{,}2067 \approx 0{,}273$.

b) Bin(10; 0,273): $P(\le1) = 0{,}727^{10} + 10\cdot0{,}273\cdot0{,}727^9 \approx 0{,}20$.

</details>

**Respuesta:**

- a) ≈ 0,273
- b) ≈ 0,20 (la guía: 0,27315 y 0,2019)

</details>

---

### 32) Dureza Rockwell ~ N(50; 3)

La dureza Rockwell de un metal se determina al presionar con una punta acerada la superficie del metal y después medir la profundidad de la penetración de la punta. Supongamos que la dureza Rockwell de cierto metal está normalmente distribuida, con media de 50 HR y desvío estándar de 3 HR.

- a) Una pieza de metal será considerada aceptable si su dureza está entre 46 y 55. ¿Cuál es la probabilidad de que una pieza seleccionada al azar tenga una dureza aceptable?
- b) Si se desea que el 95 % de las piezas resulten aceptables respecto de su dureza y se quiere que el intervalo de aceptabilidad sea de la forma (50 − c, 50 + c), ¿cuál deberá ser el valor de c?
- c) Considerando independencia entre la dureza de las piezas y seleccionando 8 piezas al azar de este metal, ¿qué cantidad se espera que resulte aceptable, con el criterio establecido en (a)?
- d) Si se seleccionan al azar tres piezas, hallar la probabilidad de que la máxima de las durezas no supere 52.

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

a) Φ(5/3) − Φ(−4/3) = 0,9522 − 0,0912 = 0,861.

b) c = 1,96·3 = 5,88.

c) 8·0,861 ≈ 6,9.

d) El máximo no supera 52 ⇔ las tres no superan 52: Φ(2/3)³ = 0,7475³ ≈ 0,4177.

</details>

**Respuesta:**

- a) 0,861
- b) 5,88
- c) 6,9
- d) 0,4177

</details>

---

### 33) Transformación lineal de una normal (T)

(T) Demostrar que si X tiene una distribución Normal con parámetros μ y σ², entonces Y = aX + b también tiene una distribución Normal. ¿Cuáles son los parámetros de la distribución de Y?

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

Para a > 0: $F_Y(y) = P(aX + b \le y) = F_X\left(\frac{y-b}a\right)$. Derivando:

$$f_Y(y) = \frac1af_X\left(\frac{y-b}a\right) = \frac1{a\sigma\sqrt{2\pi}}e^{-\frac12\left(\frac{y - (a\mu + b)}{a\sigma}\right)^2}$$

que es una densidad normal. Para a < 0 se procede igual, con |a|.

</details>

**Respuesta:** Y ~ N(aμ + b; a²σ²), es decir, media aμ + b y desvío |a|σ.

</details>

---

[← Volver al menú principal](../README.md)
