# Unidad 3 — Ejercicios resueltos

Ejercicios de la **Práctica 3 de la Guía de TP** (Variables aleatorias especiales).

Cada ejercicio tiene un botón **Solución**. Al abrirlo aparece la respuesta y, arriba de ella, un segundo botón **Solución paso a paso** con el desarrollo completo.

Notación: Φ(z) = P(Z < z) para Z ~ N(0; 1). Los valores numéricos se obtienen con tabla o con la app *Probability Distributions*.

> **Referencias:** ⭐ = ejercicio sugerido como prioritario en los apuntes de la cátedra.

---

### 1) Refrigeradores devueltos

De 10 refrigeradores, 4 tienen el compresor defectuoso. Se examinan 5 al azar. X = cantidad con compresor defectuoso.
a) Distribución de X. b) P(no todos tienen fallas leves). c) P(a lo sumo 4 tienen falla de compresor).

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

a) Se extrae sin reposición de un lote finito ⇒ **hipergeométrica** con N = 10, K = 4, n = 5.
b) "No todos leves" = al menos uno con compresor defectuoso: $1 - P(X = 0) = 1 - \frac{\binom65}{\binom{10}5} = 1 - \frac6{252} = 0{,}9762$.
c) Sólo hay 4 compresores defectuosos, así que X ≤ 4 siempre ⇒ P = 1.

</details>

**Respuesta:** a) X ~ H(N = 10, K = 4, n = 5) b) 0,9762 c) 1

</details>

---

### 2) El asado de Laura

Hay 6 varones (1 de Letras y 5 de Exactas) y 8 mujeres (5 de Letras y 3 de Exactas), contando a Laura.
a) Si las primeras en llegar son 3 chicas, P(las tres estudian lo mismo que Laura). b) Tres cualesquiera hacen el asado: P(estudian lo mismo). c) Se eligen 2; X = cantidad de Letras: E(X) y V(X).

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

**Respuesta:** a) 4/35 b) 0,2088 c) E = 6/7, V = 288/637

</details>

---

### 3) Truco

Mazo de 40 cartas (4 palos de 10). Se reparten 3 cartas a cada jugador.
a) P(el primero tiene envido: dos del mismo palo y una distinta). b) P(flor: tres del mismo palo). c) P(ambos tienen flor). d) P(ni flor ni envido).

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

**Respuesta:** a) 135/247 b) 0,04858 c) 0,00247 d) 0,40486

</details>

---

### 4) Sobreventa de pasajes ⭐

El 4 % de los pasajeros no se presenta. Se venden 72 pasajes para 70 asientos. ¿P(pueden viajar todos los que se presentan)?

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

El 25 % de los neumáticos se pinchan. Entre 6: a) P(al menos 2 se pinchan) b) P(a lo sumo 3 no se pinchan) c) P(no se supera el número esperado de pinchaduras).

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

X = pinchados ~ Bin(6; 0,25).
a) $1 - P(0) - P(1) = 1 - 0{,}75^6 - 6\cdot0{,}25\cdot0{,}75^5 \approx 0{,}466$.
b) "No pinchados ≤ 3" ⇔ X ≥ 3 ⇒ $P(X \ge 3) \approx 0{,}169$. La guía da 0,9624, que es $P(X \le 3)$, o sea "a lo sumo 3 **sufran** pinchaduras".
c) E(X) = 6·0,25 = 1,5 ⇒ $P(X \le 1) \approx 0{,}534$.

</details>

**Respuesta:** a) 0,466 b) 0,169 (con la lectura de la guía, 0,9624) c) 0,534

</details>

---

### 6) Motores de cuatriciclos ⭐

El 5 % no supera la prueba. a) Entre 5, P(al menos uno no pasa). b) Entre 20, cantidad esperada que pasa. c) Entre 7, P(no todos pero sí la mayoría no pasan).

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

a) $1 - 0{,}95^5 = 0{,}22622$
b) Pasan ~ Bin(20; 0,95) ⇒ E = 19
c) Fallan ~ Bin(7; 0,05). "La mayoría pero no todos" = 4, 5 o 6 ⇒ $\sum_{k=4}^6\binom7k0{,}05^k0{,}95^{7-k} \approx 0{,}00019$

</details>

**Respuesta:** a) 0,22622 b) 19 c) 0,00019

</details>

---

### 7) Proyectos de calidad y expansión ⭐

El 30 % está en calidad, el 50 % en expansión y el 70 % en al menos uno. Se eligen 5 empleados. P de: a) al menos 2 en exactamente un proyecto b) a lo sumo 3 en ambos c) todos en algún proyecto.

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

P(ambos) = 0,3 + 0,5 − 0,7 = 0,1; P(exactamente uno) = 0,7 − 0,1 = 0,6. La empresa es grande, así que se toman los 5 como ensayos independientes (binomial).
a) X ~ Bin(5; 0,6): $1 - 0{,}4^5 - 5\cdot0{,}6\cdot0{,}4^4 = 0{,}91296$
b) Y ~ Bin(5; 0,1): $1 - P(4) - P(5) = 0{,}99954$
c) $0{,}7^5 = 0{,}16807$

</details>

**Respuesta:** a) 0,91296 b) 0,99954 c) 0,16807

</details>

---

### 8) Esperanza y varianza de la binomial (T)

X ~ Bin(n; p). a) Demostrar E = np. b) Demostrar V = np(1 − p). c) ¿Para qué p es V = 0? d) ¿Para qué p es máxima E? e) ¿Y V?

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

**Respuesta:** c) p = 0 o p = 1 d) p = 1 e) p = 0,5

</details>

---

### 9) Fórmula recursiva de la binomial (T)

Demostrar que $P(X = k+1) = \frac{(n-k)p}{(k+1)(1-p)}P(X = k)$.

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

Pasan autos según un proceso de Poisson con α = 20 autos/h. El peaje cuesta \$45 y todos pagan con \$50; Fabián empieza con un solo billete de \$5.
a) P(algún automovilista se queda sin vuelto en los primeros 5 min). b) ¿Cuánto puede tardar en el café para que P(no llega ningún auto) = 1/10?

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

a) Cada auto recibe \$5 de vuelto. Con un solo billete, al primer auto le puede dar vuelto y al segundo ya no (los billetes de \$50 no sirven para dar \$5). Hay problema si llegan 2 o más.
En 5 min: λ = 20·(5/60) = 5/3. $P(X \ge 2) = 1 - e^{-5/3}(1 + \frac53) \approx 0{,}4963$.
b) $P(X = 0) = e^{-20t} = 0{,}1 \Rightarrow t = \frac{\ln10}{20}$ h ≈ 0,115 h ≈ 6,9 min.

</details>

**Respuesta:** a) 0,4963 b) ≈ 6,9 minutos

</details>

---

### 11) Sala de emergencias de Moquehue ⭐

Los pacientes por semana son Poisson con media 3. Se pueden atender 4 por semana; el resto se deriva. a) P(derivar alguno). b) Derivados esperados por semana. c) ¿Cuántos se deberían poder atender para no derivar en el 90 % de las semanas?

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

X ~ Po(3).
a) $P(X \ge 5) = 1 - \sum_{k=0}^4\frac{3^k}{k!}e^{-3} \approx 0{,}185$.
b) Derivados Y = máx(X − 4, 0): $E(Y) = \sum_{k\ge5}(k-4)P(X = k) = 1\cdot0{,}1008 + 2\cdot0{,}0504 + 3\cdot0{,}0216 + \dots \approx 0{,}32$.
c) P(X ≤ 4) = 0,815 no alcanza; P(X ≤ 5) = 0,916 ≥ 0,90 ⇒ 5 pacientes.

</details>

**Respuesta:** a) 0,185 b) ≈ 0,32 c) 5 pacientes

</details>

---

### 12) Fila del ANSES ⭐

P(ningún arribo en 5 min) = $e^{-1}$. a) Llegadas esperadas en una hora. b) P(pasan más de 6 min entre dos arribos consecutivos).

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

$e^{-\lambda} = e^{-1}$ ⇒ λ = 1 en 5 min ⇒ α = 0,2 por min.
a) En 60 min: λ = 0,2·60 = 12.
b) El tiempo entre arribos es Exp(0,2) ⇒ $P(Y > 6) = e^{-1{,}2} \approx 0{,}3012$.

</details>

**Respuesta:** a) 12 personas b) 0,3012

</details>

---

### 13) Fórmula recursiva de Poisson (T)

Si X ~ Po(λ), demostrar que $P(X = k+1) = \frac{\lambda}{k+1}P(X = k)$.

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

X uniforme con E = 15 y P(13 ≤ X ≤ 18,5) = 0,55. Hallar V(X) y P(X ≤ 13).

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

El peso es uniforme en (a, b): el 20 % pesa menos de 4 kg y el 40 % más de 8 kg. a) P(5 < X < 9). b) De 8 bultos, P(ninguno pesa entre 5 y 9). c) Cantidad esperada entre 5 y 9.

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

Con L = b − a: 4 − a = 0,2L y b − 8 = 0,4L. Sumando: L − 4 = 0,6L ⇒ L = 10, a = 2, b = 12.
a) (9 − 5)/10 = 0,4
b) Bin(8; 0,4): $0{,}6^8 \approx 0{,}0168$
c) 8·0,4 = 3,2

</details>

**Respuesta:** a) 0,4 b) 0,0168 c) 3,2

</details>

---

### 16) Amplificadores (mezcla de exponenciales) ⭐

El 10 % de los amplificadores tiene duración media de 20000 h y el resto, de 50000 h (exponenciales). a) Proporción que falla antes de 60000 h. b) P(supera 40000 h / supera 20000 h).

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

Probabilidad total con las dos exponenciales (λ = 1/20000 y λ = 1/50000):
a) $0{,}1(1 - e^{-3}) + 0{,}9(1 - e^{-1{,}2}) = 0{,}0950 + 0{,}6289 = 0{,}7239$.
b) $\frac{P(X > 40000)}{P(X > 20000)} = \frac{0{,}1e^{-2} + 0{,}9e^{-0{,}8}}{0{,}1e^{-1} + 0{,}9e^{-0{,}4}} \approx 0{,}6529$. Ojo: acá **no** se aplica la falta de memoria, porque la mezcla de dos exponenciales no es exponencial.

</details>

**Respuesta:** a) 0,7239 b) 0,6529

</details>

---

### 17) Lámparas

El 80 % dura más de 800 h (exponencial). ¿Cuántas lámparas hacen falta como mínimo para que P(alguna dure más de 600 h) ≥ 0,9?

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

El ingreso es Exp(λ = 0,00005). Hallar los cuantiles 0,2, 0,4, 0,6 y 0,8.

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

X ~ Exp(λ). Hallar la distribución de Y = cX (c > 0).

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

El 20 % dura menos de 400 h (exponencial). De 5 pilas, P(todas duran menos de 500 h).

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

H (60 %): duración Exp con media 100 (miles de h). M (40 %): duración U[80, 130]. a) P(H dura > 90 / dura > 70). b) P(una batería cualquiera dura ≤ 90). c) P(es de H / dura ≤ 90).

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

a) Falta de memoria: $P(X > 90 / X > 70) = P(X > 20) = e^{-0{,}2} = 0{,}8187$.
b) $P_H = 1 - e^{-0{,}9} = 0{,}5934$ y $P_M = \frac{90 - 80}{50} = 0{,}2$ ⇒ $0{,}6\cdot0{,}5934 + 0{,}4\cdot0{,}2 = 0{,}436$.
c) Bayes: $0{,}3560/0{,}436 = 0{,}8165$.

</details>

**Respuesta:** a) 0,8187 b) 0,436 c) 0,8165

</details>

---

### 22) Cajero de banco ⭐

Atiende según un proceso de Poisson con 2 clientes cada 15 min (α = 2/15 por min). a) P(atender un cliente lleva más de 20 min). b) Más de 10 min. c) Más de 40 min dado que lleva más de 30. d) Comparar b) y c). e) P(se atienden 30 clientes en menos de 4 h).

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

**Respuesta:** a) 0,06948 b) 0,2636 c) 0,2636 d) falta de memoria e) ≈ 0,662 (la guía da 0,5939)

</details>

---

### 23) Paquetes de mensajes

Llegan mensajes según Poisson con 30 por minuto (0,5 por segundo), y se necesitan 6 para formar un paquete. a) Tiempo medio para formar un paquete. b) Su varianza. c) P(se forma en menos de 12 s).

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

El tiempo hasta el 6.° evento es la suma de 6 exponenciales independientes ⇒ T ~ Gamma(α = 6, λ = 0,5/s).
a) E = α/λ = 12 s
b) V = α/λ² = 24 s²
c) T < 12 ⇔ hay al menos 6 llegadas en 12 s: N ~ Po(6) ⇒ $1 - P(N \le 5) \approx 0{,}5543$

</details>

**Respuesta:** a) 12 s b) 24 s² c) 0,5543

</details>

---

### 24) Máquina parada (Gamma)

Y (horas paradas por semana) ~ Gamma(α = 3, λ = 0,5). La pérdida es L = 30Y + 8 (en cientos de \$). P(se pierden más de \$18800).

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

Y ~ Gamma(α = 100, λ = 20) y L = 20Y − 3Y². Hallar E(L).

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

A y B son independientes, con tiempo hasta la falla Exp(1/100 h). Hallar F y f del tiempo T hasta la falla del sistema: a) en serie b) en paralelo.

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

a) En serie, falla cuando falla la primera: T = mín. $P(T > t) = e^{-t/100}e^{-t/100} = e^{-t/50}$ ⇒ Exp(1/50).
b) En paralelo, falla cuando fallan ambas: T = máx. $F(t) = (1 - e^{-t/100})^2$; derivando, $f(t) = \frac1{50}e^{-t/100} - \frac1{50}e^{-t/50}$.

</details>

**Respuesta:** a) T ~ Exp(1/50 h) b) F = (1 − e^{−t/100})², f = (1/50)e^{−t/100} − (1/50)e^{−t/50}

</details>

---

### 27) Normal N(5; 10) ⭐

a) P(X < 0), P(X > 10), P(X ≥ 15). b) P(−20 < X < 15) y P(−5 ≤ X ≤ 30). c) x tal que P(X > x) = 0,05. d) x tal que P(X < x) = 0,23.

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

**Respuesta:** a) 0,3085; 0,3085; 0,1587 b) 0,8351 ambas c) 21,45 d) −2,39

</details>

---

### 28) Propiedades de la normal

a) Mostrar que P(|X − μ| ≤ 1,24σ) = 0,785. b) Hallar c tal que P(μ − c ≤ X ≤ μ + c) = 0,95.

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

a) $P(-1{,}24 \le Z \le 1{,}24) = 2\Phi(1{,}24) - 1 = 2\cdot0{,}8925 - 1 = 0{,}785$.
b) $2\Phi(c/\sigma) - 1 = 0{,}95 \Rightarrow \Phi(c/\sigma) = 0{,}975 \Rightarrow c = 1{,}96\sigma$.

</details>

**Respuesta:** a) 0,785 b) c = 1,96σ

</details>

---

### 29) Calidad seis sigma

Mediciones normales. a) La media está centrada a 3σ de cada especificación: P(no cumplir). b) La media se corre 1,5σ hacia arriba: P(no cumplir). Expresar en partes por millón.

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

a) Fuera de μ ± 3σ: 2(1 − Φ(3)) = 0,0027 ⇒ 2700 ppm.
b) Ahora los límites quedan a 1,5σ (arriba) y 4,5σ (abajo): (1 − Φ(1,5)) + Φ(−4,5) ≈ 0,0668 + 0,0000034 ≈ 0,0668 ⇒ ≈ 66 810 ppm.

</details>

**Respuesta:** a) 0,0027 (2700 ppm) b) 0,0668 (≈ 66 810 ppm)

</details>

---

### 30) Peso de los alumnos ~ N(75; 7) ⭐

a) P(pesa más de 95 kg). b) De 15000 alumnos, cuántos pesan entre 80 y 95 kg. c) Peso no superado por el 10 %. d) De 10 alumnos, P(al menos la mitad pesa más de 80 kg).

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

a) $1 - \Phi(20/7) = 1 - \Phi(2{,}857) \approx 0{,}0021$.
b) $\Phi(2{,}857) - \Phi(0{,}714) = 0{,}99786 - 0{,}76247 = 0{,}2354$ ⇒ 15000·0,2354 ≈ 3531 alumnos.
c) $75 + z_{0{,}1}\cdot7 = 75 - 1{,}2816\cdot7 \approx 66{,}03$ kg.
d) p = P(X > 80) = 0,2375; Y ~ Bin(10; 0,2375) ⇒ P(Y ≥ 5) ≈ 0,0644. La guía da 0,0699 porque redondea distinto el valor de z.

</details>

**Respuesta:** a) 0,0021 b) ≈ 3531 c) ≈ 66 kg d) ≈ 0,064 (la guía da 0,0699)

</details>

---

### 31) Longitud de piezas ⭐

Normal: el 15 % mide menos de 13 mm y el 10 % más de 14 mm. No es apta si mide menos de 12,8 o más de 13,8 mm. a) P(no apta). b) Se acepta una bolsa de 10 piezas si tiene a lo sumo una no apta: P(aceptar).

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

$\frac{13 - \mu}\sigma = -1{,}0364$ y $\frac{14 - \mu}\sigma = 1{,}2816$. Restando: $\frac1\sigma = 2{,}318$ ⇒ σ ≈ 0,4314 y μ ≈ 13,447.
a) $\Phi\left(\frac{12{,}8 - 13{,}447}{0{,}4314}\right) + 1 - \Phi\left(\frac{13{,}8 - 13{,}447}{0{,}4314}\right) = \Phi(-1{,}50) + 1 - \Phi(0{,}818) \approx 0{,}0668 + 0{,}2067 \approx 0{,}273$.
b) Bin(10; 0,273): $P(\le1) = 0{,}727^{10} + 10\cdot0{,}273\cdot0{,}727^9 \approx 0{,}20$.

</details>

**Respuesta:** a) ≈ 0,273 b) ≈ 0,20 (la guía: 0,27315 y 0,2019)

</details>

---

### 32) Dureza Rockwell ~ N(50; 3)

a) P(aceptable: entre 46 y 55). b) c tal que (50 − c, 50 + c) contenga al 95 %. c) De 8 piezas, cantidad esperada de aceptables. d) De 3 piezas, P(la dureza máxima no supera 52).

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

a) Φ(5/3) − Φ(−4/3) = 0,9522 − 0,0912 = 0,861.
b) c = 1,96·3 = 5,88.
c) 8·0,861 ≈ 6,9.
d) El máximo no supera 52 ⇔ las tres no superan 52: Φ(2/3)³ = 0,7475³ ≈ 0,4177.

</details>

**Respuesta:** a) 0,861 b) 5,88 c) 6,9 d) 0,4177

</details>

---

### 33) Transformación lineal de una normal (T)

Si X ~ N(μ; σ²), demostrar que Y = aX + b es normal. ¿Con qué parámetros?

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
