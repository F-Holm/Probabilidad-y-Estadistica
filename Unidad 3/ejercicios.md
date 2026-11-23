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

**a)** 💡 **Distribución hipergeométrica.** Se usa cuando:
- hay un grupo **finito** de N objetos, de los cuales K tienen una característica ("éxitos");
- se eligen n **sin reposición** (no se puede elegir dos veces el mismo);
- X cuenta cuántos éxitos salieron.

Su fórmula está en 📄 **H1**:

```math
P(X = k) = \frac{\binom Kk\binom{N-K}{n-k}}{\binom Nn}
```

Se lee: elegir k de los K éxitos **y** el resto de los no-éxitos, sobre todas las formas de elegir n.

Acá N = 10 refrigeradores, K = 4 con compresor defectuoso, n = 5 examinados: **X ~ H(N = 10; K = 4; n = 5)**.

**b)** "No todos tienen fallas leves" significa que al menos uno tiene el compresor defectuoso, X ≥ 1. Es lo contrario de X = 0, donde los 5 salen de los 6 leves:

```math
P(X \ge 1) = 1 - \frac{\binom40\binom65}{\binom{10}5} = 1 - \frac{6}{252} = 0{,}9762
```

```
X~HG(N,K,n)   N=10   K=4   n=5   P(X≥x)   x=1   → 0.97619
```

**c)** Solo **existen** 4 compresores defectuosos, así que entre los examinados no puede haber más de 4. "X ≤ 4" se cumple siempre: P = 1.

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

**Ordenar los datos** en una tabla:

| | Letras | Exactas | Total |
|---|---|---|---|
| Mujeres | 5 | 3 | 8 |
| Varones | 1 | 5 | 6 |
| Total | 6 | 8 | 14 |

**a)** Laura está en su casa, así que las que llegan son 3 de las **otras 7** mujeres, elegidas al azar sin reposición. Todos los grupos son igual de probables: $\binom73 = 35$ grupos.

El enunciado no dice qué estudia Laura. La respuesta de la guía (4/35) supone que **Laura estudia Letras**. Entonces entre las otras 7 quedan 4 de Letras y 3 de Exactas, y las 3 que llegan tienen que salir de esas 4:

```math
\frac{\binom43}{\binom73} = \frac4{35}
```

(Si Laura estudiara Exactas, quedarían solo 2 de Exactas, y no podrían llegar 3: la probabilidad sería 0.)

**b)** Ahora son 3 cualesquiera de los 14: $\binom{14}{3} = 364$ grupos. "Estudian lo mismo" significa los 3 de Letras **o** los 3 de Exactas. Son casos separados, así que se suman:

```math
\frac{\binom63 + \binom83}{364} = \frac{20 + 56}{364} \approx 0{,}2088
```

**c)** Se eligen 2 de 14 sin reposición y X cuenta los de Letras. Es una 💡 **hipergeométrica** (📄 H1) con N = 14, K = 6 (de Letras) y n = 2.

Su esperanza y su varianza tienen fórmula propia (❌, no están en la hoja):
- $E(X) = n\frac KN = 2\cdot\frac{6}{14} = \frac67$. Es "cuántos elijo × la proporción de éxitos".
- $V(X) = n\frac KN\left(1 - \frac KN\right)\frac{N-n}{N-1} = 2\cdot\frac6{14}\cdot\frac8{14}\cdot\frac{12}{13} = \frac{288}{637}$. El último factor corrige por no reponer.

Comprobación directa con la tabla (📄 H1, $`E = \sum x\,p(x)`$):
- P(0) = $\binom82/91 = 28/91$, P(1) = 6·8/91 = 48/91, P(2) = 15/91.
- E = (48 + 30)/91 = 78/91 = 6/7 ✓.

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

Una mano son 3 cartas de 40, sin importar el orden, y todas las manos son igual de probables (Laplace). Hay que **contar** manos con $\binom nk$ (nCr):

```math
\text{manos posibles} = \binom{40}{3} = 9880
```

**a) Envido** (exactamente 2 del mismo palo y 1 de otro). Se arma la mano en pasos y se multiplican las opciones de cada paso:
1. elegir **cuál** es el palo repetido: 4 opciones;
2. elegir 2 cartas de ese palo: $\binom{10}2 = 45$;
3. elegir la tercera entre las 30 cartas de los otros palos: 30.

$$\frac{4\cdot45\cdot30}{9880} = \frac{5400}{9880} = \frac{135}{247} \approx 0{,}5466$$

**b) Flor** (las 3 del mismo palo): se elige el palo (4) y 3 cartas de él ($`\binom{10}{3} = 120`$):

```math
\frac{4\cdot120}{9880} = \frac{480}{9880} \approx 0{,}04858
```

**c) Los dos jugadores con flor.** Regla de la multiplicación: P(el 1.º tiene flor) · P(el 2.º tiene flor / el 1.º tiene flor).

Si el 1.º tuvo flor, quedan 37 cartas: 7 del palo que usó y 10 de cada uno de los otros 3. El 2.º puede tener flor de otro palo ($`3\cdot\binom{10}3 = 360`$) o del mismo palo con las 7 que quedan ($`\binom73 = 35`$):

```math
P = 0{,}04858\cdot\frac{360 + 35}{\binom{37}{3}} = 0{,}04858\cdot\frac{395}{7770} \approx 0{,}00247
```

**d) Ni flor ni envido** significa las tres de palos distintos. Una mano solo puede ser de tres tipos (flor, envido o tres palos distintos), que no se pisan y suman 1. Entonces:

```math
1 - 0{,}5466 - 0{,}0486 = 0{,}40486
```

Comprobación directa: se eligen 3 palos de 4 ($`\binom43 = 4`$) y una carta de cada uno ($`10^3`$): $\frac{4000}{9880} = 0{,}40486$ ✓.

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

💡 **Distribución binomial.** Se usa cuando:
- se repite **n veces** un ensayo con dos resultados posibles (éxito o fracaso);
- los ensayos son **independientes**, y la probabilidad de éxito **p** es la misma en todos;
- X cuenta cuántos éxitos hubo.

Su fórmula está en 📄 **H1**:

```math
P(X = k) = \binom nk p^k(1-p)^{n-k}
```

Se lee: elegir **cuáles** k ensayos son éxitos, por la probabilidad de esa combinación.

**Planteo.** Cada uno de los 72 pasajes es un ensayo. Éxito = "el pasajero se presenta", con p = 1 − 0,04 = 0,96. Se supone que cada pasajero decide independientemente. Entonces X = pasajeros que se presentan ~ **Bin(72; 0,96)**.

**¿Cuándo viajan todos?** Cuando se presentan **a lo sumo 70**, la capacidad del avión. Es más corto restar los dos casos malos (71 o 72):

```math
P(X \le 70) = 1 - P(71) - P(72) = 1 - \binom{72}{71}0{,}96^{71}\,0{,}04 - 0{,}96^{72} \approx 0{,}78836
```

```
X~Bin(n,p)   n=72   p=0.96   P(X≤x)   x=70   → 0.78836
```

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

💡 **¿Por qué binomial?** Son 6 neumáticos (n = 6) que se prueban por separado (independientes). Cada uno "se pincha" (éxito) con la misma probabilidad p = 0,25, y se cuenta cuántos se pinchan. Entonces X = pinchados ~ **Bin(6; 0,25)**, con $P(X = k) = \binom6k0{,}25^k0{,}75^{6-k}$ (📄 H1).

**a) Al menos 2** (2, 3, …, 6). Es más corto restar lo contrario (0 o 1):

```math
P(X \ge 2) = 1 - P(0) - P(1) = 1 - 0{,}75^6 - 6\cdot0{,}25\cdot0{,}75^5 \approx 0{,}466
```

```
X~Bin(n,p)   n=6   p=0.25   P(X≥x)   x=2   → 0.46606
```

**b) "A lo sumo 3 NO sufran pinchaduras".** Hay que traducirlo a X. Si "no pinchados" = 6 − X ≤ 3, entonces X ≥ 3:
```
X~Bin(n,p)   n=6   p=0.25   P(X≥x)   x=3   → 0.16943
```
La guía da 0,9624, que es P(X ≤ 3): leyó "a lo sumo 3 **sufran** pinchaduras". Conviene aclarar qué lectura se usó.

**c)** 💡 **Número esperado** en una binomial: E(X) = n·p (❌, la hoja trae solo la varianza np(1 − p)). Es "cuántos ensayos × la proporción de éxitos": 6·0,25 = 1,5.

"No superar 1,5" significa X ≤ 1, porque X es entero:
```
X~Bin(n,p)   n=6   p=0.25   P(X≤x)   x=1   → 0.53394
```

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

💡 Cada motor pasa o no pasa, independientemente de los otros, siempre con la misma probabilidad. Contar cuántos fallan (o pasan) es una **binomial** (📄 H1, $`\binom nk p^k(1-p)^{n-k}`$). En cada inciso hay que decidir **qué cuenta como éxito**.

**a)** Éxito = "no pasa" (p = 0,05), n = 5. "Al menos uno" se hace por complemento: 1 − "ninguno falla" = 1 − "los 5 pasan":

```math
1 - 0{,}95^5 = 0{,}22622
```

**b)** Éxito = "pasa" (p = 0,95), n = 20. El número esperado de una binomial es E = n·p (❌):

```math
E = 20\cdot0{,}95 = 19
```

**c)** Éxito = "no pasa" (p = 0,05), n = 7. "La mayoría no pasa" significa más de la mitad de 7, o sea 4 o más. "Pero no todos" saca el 7. Quedan 4, 5 o 6:

```math
P(4 \le X \le 6) = \sum_{k=4}^6\binom7k0{,}05^k\,0{,}95^{7-k} \approx 0{,}00019
```

```
X~Bin(n,p)   n=7   p=0.05   P(X≥x)   x=4   → 0.000194   (P(X=7) ≈ 8·10⁻¹⁰, despreciable)
```

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

**Paso 1, probabilidades para un empleado** (lo de la U1). C = calidad, E = expansión.
- "Al menos uno" es la unión: $P(C\cup E) = 0{,}7$.
- De la regla de la unión (📄 H1, la de 3 sin el tercero), $P(C\cap E) = P(C) + P(E) - P(C\cup E) = 0{,}3 + 0{,}5 - 0{,}7 = 0{,}1$: **ambos**.
- **Exactamente uno** es "al menos uno" menos "ambos": $0{,}7 - 0{,}1 = 0{,}6$.

**Paso 2, ¿por qué binomial?** Se eligen 5 sin reposición, que en rigor sería hipergeométrica. Pero la empresa es **muy grande** (más de 2000), así que sacar 5 casi no cambia las proporciones. Se pueden tratar como 5 ensayos independientes con p constante: binomial (📄 H1).

**a)** Éxito = "exactamente un proyecto" (p = 0,6), X ~ Bin(5; 0,6). "Al menos 2" es 1 − P(0) − P(1):

```math
1 - 0{,}4^5 - 5\cdot0{,}6\cdot0{,}4^4 = 0{,}91296
```

```
X~Bin(n,p)   n=5   p=0.6   P(X≥x)   x=2   → 0.91296
```

**b)** Éxito = "ambos proyectos" (p = 0,1), Y ~ Bin(5; 0,1). "A lo sumo 3" es 1 − P(4) − P(5):
```
X~Bin(n,p)   n=5   p=0.1   P(X≤x)   x=3   → 0.99954
```

**c)** "Todos en algún proyecto": los 5 cumplen "al menos uno" (0,7 cada uno). Por independencia, $0{,}7^5 = 0{,}16807$.

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

**La idea clave:** una binomial es una **suma de n ensayos sueltos**. Se define $X_i$ = 1 si el ensayo i es éxito y 0 si no. Entonces la cantidad de éxitos es $X = X_1 + X_2 + \dots + X_n$.

💡 Cada $X_i$ es una **Bernoulli(p)**: vale 1 con probabilidad p y 0 con 1 − p. Sus momentos salen con 📄 H1:
- $E(X_i) = 1\cdot p + 0\cdot(1-p) = p$
- $E(X_i^2) = 1^2\cdot p + 0 = p$
- $V(X_i) = E(X_i^2) - E(X_i)^2 = p - p^2 = p(1-p)$

**a)** La esperanza de una suma es la suma de las esperanzas (❌, linealidad):

```math
E(X) = E(X_1) + \dots + E(X_n) = p + \dots + p = np
```

**b)** Para la varianza de una suma, 📄 H1 dice $V(X+Y) = V(X) + V(Y) + 2Cov$. Los ensayos son **independientes**, así que las covarianzas valen 0 y las varianzas simplemente se suman:

```math
V(X) = \sum V(X_i) = np(1-p)
```

(📄 H1 trae este resultado, pero acá piden demostrarlo.)

**c)** $np(1-p) = 0$ cuando p = 0 o p = 1 (n ≥ 1). Tiene sentido: si siempre sale fracaso (o siempre éxito), X vale siempre lo mismo y no varía.

**d)** E = np es una recta creciente en p, así que en [0; 1] es máxima en **p = 1**.

**e)** V = n(p − p²) es una parábola "boca abajo" en p, con raíces en 0 y 1. Su vértice está en el medio, **p = ½**. La incertidumbre es máxima cuando éxito y fracaso son igual de probables.

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

Se parte de la fórmula de la binomial (📄 H1, $`P(X = k) = \binom nk p^k(1-p)^{n-k}`$). La estrategia es dividir $P(k+1)$ por $P(k)$ y simplificar: lo que quede es el factor que los relaciona.

$$\frac{P(k+1)}{P(k)} = \frac{\binom n{k+1}p^{k+1}(1-p)^{n-k-1}}{\binom nk p^k(1-p)^{n-k}}$$

Por partes:
- **Potencias de p:** $\frac{p^{k+1}}{p^k} = p$.
- **Potencias de (1 − p):** $\frac{(1-p)^{n-k-1}}{(1-p)^{n-k}} = \frac{1}{1-p}$.
- **Combinatorios:** con $\binom nk = \frac{n!}{k!(n-k)!}$, el n! se cancela y queda

  ```math
  \frac{k!\,(n-k)!}{(k+1)!\,(n-k-1)!} = \frac{n-k}{k+1}
  ```

  porque $(k+1)! = (k+1)\cdot k!$ y $(n-k)! = (n-k)\cdot(n-k-1)!$.

Juntando: $\frac{P(k+1)}{P(k)} = \frac{(n-k)\,p}{(k+1)(1-p)}$, y pasando P(k) multiplicando queda la fórmula. ∎

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

💡 **Distribución de Poisson.** Cuenta **cuántos eventos ocurren en un intervalo** (de tiempo, de espacio…) cuando ocurren al azar, de a uno, con un ritmo promedio constante. Su único parámetro λ es el **promedio de eventos en ese intervalo**. 📄 **H1**:

```math
P(X = k) = \frac{\lambda^k}{k!}e^{-\lambda}
```

⚠️ λ depende del largo del intervalo: si en 1 hora llegan en promedio 20 autos, en 5 minutos llegan en promedio 20·(5/60).

**a) ¿Cuándo hay problema?** Cada auto paga 45 con un billete de 50 y necesita 5 de vuelto. Fabián tiene un solo billete de 5: le puede dar vuelto al **primer** auto y a ninguno más (los billetes de 50 que recibe no sirven para dar 5). Alguien se queda sin vuelto si llegan **2 o más** autos.

En 5 minutos, λ = 20·(5/60) = 5/3 ≈ 1,667:

```math
P(X \ge 2) = 1 - P(0) - P(1) = 1 - e^{-5/3}\left(1 + \frac53\right) \approx 0{,}4963
```

```
X~Po(λ)   λ=1.6667   P(X≥x)   x=2   → 0.49633
```

**b)** Si Fabián se va t horas, el promedio de autos es λ = 20t. "Ningún auto" es $P(X = 0) = e^{-20t}$, y se pide que eso valga 1/10:

```math
e^{-20t} = 0{,}1 \;\Rightarrow\; -20t = \ln0{,}1 \;\Rightarrow\; t = \frac{\ln10}{20} \approx 0{,}115 \text{ h} \approx 6{,}9 \text{ min}
```

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

💡 **Poisson:** cuenta eventos (pacientes) en un intervalo (una semana) con un promedio fijo λ = 3. X ~ Po(3), con $P(X = k) = \frac{3^k}{k!}e^{-3}$ (📄 H1).

**a)** Se deriva algún paciente si llegan más de 4, es decir X ≥ 5:

```math
P(X \ge 5) = 1 - \sum_{k=0}^{4}\frac{3^k}{k!}e^{-3} \approx 0{,}185
```

```
X~Po(λ)   λ=3   P(X≥x)   x=5   → 0.18474
```

**b)** Los derivados son Y = X − 4 si X > 4, y 0 si no. Es una **función** de X. 💡 Su esperanza es $E(g(X)) = \sum g(k)P(X = k)$ (📄 H1): cada cantidad de derivados por su probabilidad.

```math
E(Y) = \sum_{k \ge 5}(k - 4)P(X = k) = 1\cdot0{,}1008 + 2\cdot0{,}0504 + 3\cdot0{,}0216 + 4\cdot0{,}0081 + \dots \approx 0{,}32
```

Cada P(X = k) sale con `X~Po(λ) λ=3 P(X=x) x=k`.

**c)** Se busca la capacidad c **más chica** que cumpla $P(X \le c) \ge 0{,}90$. Se prueba acumulando:
```
X~Po(λ)   λ=3   P(X≤x)   x=4   → 0.81526   (no alcanza)
X~Po(λ)   λ=3   P(X≤x)   x=5   → 0.91608   (alcanza)
```
Hay que poder atender **5 pacientes**.

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

💡 **Proceso de Poisson.** Las llegadas ocurren al azar a un **ritmo** constante α (llegadas por minuto). La cantidad de llegadas en t minutos es Poisson con λ = α·t (📄 H1, $`P(X = k) = \frac{\lambda^k}{k!}e^{-\lambda}`$).

**Hallar el ritmo.** "Ningún arribo en 5 minutos" es $P(X = 0) = e^{-\lambda}$, con λ el promedio en 5 min. El dato dice que vale $e^{-1}$, así que λ = 1 llegada cada 5 minutos: α = 1/5 = 0,2 por minuto.

**a)** El promedio en 60 minutos es λ = 0,2·60 = **12 personas**. En una Poisson la esperanza es λ (❌).

**b)** 💡 **Relación Poisson–exponencial:** si las llegadas son Poisson con ritmo α, el **tiempo entre dos llegadas** es **exponencial** con parámetro α (❌). La exponencial (📄 H1) tiene $F(t) = 1 - e^{-\alpha t}$, así que $P(T > t) = e^{-\alpha t}$.

"Más de 6 minutos entre dos arribos":

```math
P(T > 6) = e^{-0{,}2\cdot6} = e^{-1{,}2} \approx 0{,}3012
```

```
X~Exp(λ)   λ=0.2   P(X>x)   x=6   → 0.30119
```
Otra forma de verlo: "más de 6 minutos sin llegadas" es "0 llegadas en 6 minutos", y una Poisson con λ = 1,2 da $P(0) = e^{-1{,}2}$. Lo mismo.

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

Se parte de la fórmula de Poisson (📄 H1, $`P(X = k) = \frac{\lambda^k}{k!}e^{-\lambda}`$) aplicada a k + 1, y se busca "sacar" P(k) de adentro:

```math
P(X = k+1) = \frac{\lambda^{k+1}}{(k+1)!}e^{-\lambda}
```

Se usa que $\lambda^{k+1} = \lambda\cdot\lambda^k$ y que $(k+1)! = (k+1)\cdot k!$:

```math
= \frac{\lambda\cdot\lambda^k}{(k+1)\cdot k!}e^{-\lambda} = \frac{\lambda}{k+1}\cdot\underbrace{\frac{\lambda^k}{k!}e^{-\lambda}}_{P(X = k)}
```

∎ Sirve para calcular P(1), P(2), … a partir de P(0) = $e^{-\lambda}$, multiplicando cada vez por λ/(k+1).

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

💡 **Distribución uniforme U(a; b).** La variable cae en cualquier lugar del intervalo [a; b] con la **misma** chance: la densidad es una "meseta" plana de altura $\frac1{b-a}$. Entonces la probabilidad de un tramo es **su largo dividido el largo total** (❌):

```math
P(c \le X \le d) = \frac{d - c}{b - a} \qquad E(X) = \frac{a+b}{2}\;(❌) \qquad V(X) = \frac{(b-a)^2}{12}\;(📄\text{ H1})
```

**Hallar a y b con los dos datos:**
- El valor esperado es el **punto medio**: $\frac{a+b}{2} = 15$.
- La probabilidad del tramo [13; 18,5] es su largo sobre el largo total: $\frac{18{,}5 - 13}{b - a} = 0{,}55 \Rightarrow b - a = \frac{5{,}5}{0{,}55} = 10$.

Un intervalo de largo 10 centrado en 15 va de 10 a 20: **X ~ U(10; 20)**.

**Varianza** (📄 H1): $V = \frac{(20 - 10)^2}{12} = \frac{100}{12} = \frac{25}{3}$.

**P(X ≤ 13):** el tramo [10; 13] tiene largo 3: $\frac{13 - 10}{10} = 0{,}3$.

(La app Probability Distributions no tiene uniforme. Si se quiere usar: `X~Beta(α;β) α=1 β=1 P(X<x) x=(13−10)/10=0.3 → 0.3`.)

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

💡 **Uniforme U(a; b):** todos los valores del intervalo son igual de probables, así que la probabilidad de un tramo es **largo del tramo / largo total** (❌).

**Hallar a y b.** Se llama L = b − a al largo total.
- "20 % pesa menos de 4": el tramo [a; 4] mide el 20 % de L, es decir $4 - a = 0{,}2L$.
- "40 % pesa más de 8": el tramo [8; b] mide el 40 % de L, es decir $b - 8 = 0{,}4L$.

Sumando las dos ecuaciones: $(b - a) - 4 = 0{,}6L$, o sea $L - 4 = 0{,}6L$. Entonces $L = 10$, $a = 4 - 2 = 2$ y $b = 12$. **X ~ U(2; 12).**

**a)** El tramo [5; 9] mide 4: $\frac{9 - 5}{10} = 0{,}4$.

**b)** Cada bulto pesa entre 5 y 9 (éxito) con p = 0,4, y los 8 son independientes. 💡 Contar éxitos en ensayos independientes es **binomial**: Bin(8; 0,4) (📄 H1). "Ninguno" es P(0):

```math
0{,}6^8 \approx 0{,}0168
```

**c)** En una binomial el número esperado es n·p (❌): $8\cdot0{,}4 = 3{,}2$ bultos.

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

💡 **Distribución exponencial.** Modela **tiempos de vida o de espera**. Tiene un parámetro λ, y su media es $E(X) = \frac1\lambda$ (📄 H1). La probabilidad de durar más de t es $P(X > t) = e^{-\lambda t}$, que sale de $F(t) = 1 - e^{-\lambda t}$ (📄 H1).

**Hay dos tipos de amplificadores** (dos escenarios), como en la U1:
- tipo 1 (10 %): media 20000 h, así que λ₁ = 1/20000;
- tipo 2 (90 %): media 50000 h, así que λ₂ = 1/50000.

**a)** Un amplificador al azar puede ser de cualquier tipo. 💡 **Probabilidad total**: se suma P(tipo)·P(falla antes de 60000 / tipo):

```math
0{,}1\left(1 - e^{-60000/20000}\right) + 0{,}9\left(1 - e^{-60000/50000}\right) = 0{,}1(1 - e^{-3}) + 0{,}9(1 - e^{-1{,}2}) = 0{,}0950 + 0{,}6289 = 0{,}7239
```

```
X~Exp(λ)   λ=0.00005   P(X<x)   x=60000   → 0.95021
X~Exp(λ)   λ=0.00002   P(X<x)   x=60000   → 0.69881
```

**b)** Condicional (📄 H1). "Supera 40000" está dentro de "supera 20000", así que la intersección es "supera 40000":

```math
P(X > 40000 / X > 20000) = \frac{P(X > 40000)}{P(X > 20000)}
```

Cada una se calcula con probabilidad total:

```math
\frac{0{,}1e^{-2} + 0{,}9e^{-0{,}8}}{0{,}1e^{-1} + 0{,}9e^{-0{,}4}} \approx \frac{0{,}4179}{0{,}6401} \approx 0{,}6529
```

⚠️ **No** vale la falta de memoria (que diría "P(X > 20000)"). Esa propiedad es de **una** exponencial, y la mezcla de dos exponenciales no es exponencial. Saber que ya duró 20000 h hace más probable que sea del tipo "duradero".

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

💡 **Exponencial:** sirve para tiempos de vida. La probabilidad de durar más de t es $P(X > t) = e^{-\lambda t}$, que sale de 📄 H1, $F(t) = 1 - e^{-\lambda t}$.

**Paso 1, usar el dato.** "El 80 % dura más de 800 h" se escribe $e^{-800\lambda} = 0{,}8$. No hace falta despejar λ: hay un atajo con potencias.

```math
P(X > 600) = e^{-600\lambda} = \left(e^{-800\lambda}\right)^{600/800} = 0{,}8^{0{,}75} \approx 0{,}8459
```

(Si se prefiere, $\lambda = -\ln0{,}8/800 = 0{,}000279$, y da lo mismo.)

**Paso 2, n lámparas.** Se quiere que **alguna** dure más de 600 h. Por complemento, es 1 − "todas duran menos". Las lámparas son independientes, y cada una dura menos con probabilidad 1 − 0,8459 = 0,1541:

```math
1 - 0{,}1541^n \ge 0{,}9 \;\Rightarrow\; 0{,}1541^n \le 0{,}1
```

**Paso 3, despejar n con logaritmos.** ln(0,1541) es negativo, y al dividir por un negativo se da vuelta la desigualdad:

```math
n\ln0{,}1541 \le \ln0{,}1 \;\Rightarrow\; n \ge \frac{\ln0{,}1}{\ln0{,}1541} \approx 1{,}23
```

n tiene que ser entero, así que **n = 2**. Control: con 1 lámpara, 0,846 < 0,9; con 2, 1 − 0,1541² = 0,976 ✓.

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

💡 **Cuantil q:** el valor $x_q$ que deja una proporción q de la población **por debajo**, es decir $F(x_q) = q$. Por ejemplo, el salario que separa la clase baja de la media-baja deja al 20 % por debajo: es el cuantil 0,20.

Con la exponencial, $F(x) = 1 - e^{-\lambda x}$ (📄 H1). Se iguala a q y se despeja:

```math
1 - e^{-\lambda x_q} = q \;\Rightarrow\; e^{-\lambda x_q} = 1 - q \;\Rightarrow\; x_q = \frac{-\ln(1-q)}{\lambda} = -20000\ln(1-q)
```

(1/λ = 1/0,00005 = 20000.)

| q | 0,20 | 0,40 | 0,60 | 0,80 |
|---|---|---|---|---|
| $x_q$ | 4462,87 | 10216,51 | 18325,81 | 32188,75 |

Con la app se busca el x que deja esa área a la izquierda:
```
X~Exp(λ)   λ=0.00005   P(X<x)=0.2   → x=4462.87
X~Exp(λ)   λ=0.00005   P(X<x)=0.4   → x=10216.51   (y así con 0.6 y 0.8)
```

Las clases **no** son tramos de igual ancho. La exponencial tiene mucha gente con ingresos bajos y una cola larga de ingresos altos, así que los cortes se van separando cada vez más.

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

**Idea:** para saber qué distribución tiene Y, se calcula una probabilidad de Y y se compara con la forma de la exponencial. Se supone c > 0.

💡 Una exponencial de parámetro μ se reconoce porque $P(Y > y) = e^{-\mu y}$ para y ≥ 0 (sale de 📄 H1, $`F(y) = 1 - e^{-\mu y}`$).

Se calcula, despejando X adentro:

```math
P(Y > y) = P(cX > y) = P\left(X > \frac yc\right) = e^{-\lambda\frac yc} = e^{-\left(\frac\lambda c\right)y}
```

Tiene exactamente la forma de una exponencial, con parámetro λ/c. Entonces **Y ~ Exp(λ/c)**.

Tiene sentido: si se multiplican los tiempos por c, la media 1/λ pasa a ser c/λ, que es 1/(λ/c).

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

💡 **Exponencial:** $P(X > t) = e^{-\lambda t}$ (📄 H1, $`F(t) = 1 - e^{-\lambda t}`$).

**Paso 1, el dato.** "El 20 % dura menos de 400" significa que el 80 % dura más: $e^{-400\lambda} = 0{,}8$.

**Paso 2, una pila.** Con el atajo de potencias, $e^{-500\lambda} = (e^{-400\lambda})^{500/400} = 0{,}8^{1{,}25}$:

```math
P(X < 500) = 1 - 0{,}8^{1{,}25} \approx 0{,}2434
```

```
X~Exp(λ)   λ=0.000557859   P(X<x)   x=500   → 0.24341
```
(λ = −ln 0,8 / 400.)

**Paso 3, las cinco.** Las pilas son independientes, así que "las 5 duran menos de 500" es el producto (📄 H1):

```math
0{,}2434^5 \approx 0{,}00085
```

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

**Unidades:** todo en miles de horas. 90 000 h es 90 y 70 000 h es 70.

**Fábrica H:** exponencial con media 100, así que λ = 1/100 = 0,01 (📄 H1, $`E(X) = 1/\lambda`$).
**Fábrica M:** uniforme en [80; 130].

**a)** 💡 **Falta de memoria** (📄 H1, $`P(X > t_0 + \Delta t / X > t_0) = P(X > \Delta t)`$). Una exponencial "no envejece": si ya duró 70, la probabilidad de durar 20 más es la misma que la de una batería nueva de durar 20.

```math
P(X > 90 / X > 70) = P(X > 20) = e^{-0{,}01\cdot20} = e^{-0{,}2} = 0{,}8187
```

**b)** Una batería del stock puede venir de cualquiera de las dos fábricas. 💡 **Probabilidad total** (U1): se suma P(fábrica)·P(dura ≤ 90 / fábrica).
- H: $1 - e^{-0{,}01\cdot90} = 1 - e^{-0{,}9} = 0{,}5934$.
- M: uniforme, largo del tramo sobre largo total: $\frac{90 - 80}{130 - 80} = 0{,}2$.

$$P(\le 90) = 0{,}6\cdot0{,}5934 + 0{,}4\cdot0{,}2 = 0{,}3560 + 0{,}08 = 0{,}436$$

**c)** Pregunta al revés: sabiendo que duró ≤ 90, ¿es de H? 💡 **Bayes** (📄 H1), el camino de H sobre el total:

```math
P(H / \le 90) = \frac{0{,}3560}{0{,}436} = 0{,}8165
```

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

💡 **Relación Poisson–exponencial** (❌). Si la **cantidad** de eventos es Poisson con ritmo α (eventos por minuto), el **tiempo** entre uno y el siguiente es **exponencial** con el mismo α.

Acá el ritmo es 2 clientes cada 15 min, α = 2/15 por minuto. El tiempo de atención es T ~ Exp(2/15), con $P(T > t) = e^{-\alpha t}$ (📄 H1).

**a)** $P(T > 20) = e^{-20\cdot2/15} = e^{-8/3} \approx 0{,}0695$
```
X~Exp(λ)   λ=0.13333   P(X>x)   x=20   → 0.06948
```

**b)** $P(T > 10) = e^{-10\cdot2/15} = e^{-4/3} \approx 0{,}2636$

**c)** 💡 **Falta de memoria** (📄 H1): si ya pasaron 30 minutos, la probabilidad de que tarde 10 más no depende de lo ya esperado.

```math
P(T > 40 / T > 30) = P(T > 10) = 0{,}2636
```

**d)** Dan **igual**, justamente por la falta de memoria: la exponencial "no recuerda" cuánto ya se esperó.

**e)** Ahora la pregunta es sobre **cantidades**. "Atender 30 clientes en menos de 4 horas" significa que en 240 minutos se atienden **al menos 30**. La cantidad en 240 min es Poisson con λ = (2/15)·240 = 32 (📄 H1, $`P(N = k) = \frac{\lambda^k}{k!}e^{-\lambda}`$):
```
X~Po(λ)   λ=32   P(X≥x)   x=30   → 0.66199
```
La guía da 0,5939, que es P(N ≥ 31). Parece una errata o una lectura distinta ("más de 30").

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

**Unidades:** 30 mensajes por minuto es 0,5 mensajes por segundo.

💡 **Distribución Gamma** (❌, no está en la hoja). El tiempo **entre** dos mensajes es exponencial con λ = 0,5/s. El tiempo hasta el **6.º** mensaje es la **suma de 6 exponenciales** independientes, y esa suma tiene distribución **Gamma(α = 6; λ = 0,5)**: α es cuántos eventos se esperan.

**a)** Cada espera es exponencial con media 1/λ = 2 s (📄 H1). Por linealidad, la suma de 6 tiene media 6·2:

```math
E(T) = \frac\alpha\lambda = 12 \text{ s}
```

**b)** Cada exponencial tiene varianza $1/\lambda^2 = 4$ (📄 H1, $`\sigma = 1/\lambda`$). Son independientes, así que las varianzas se suman:

```math
V(T) = \frac{\alpha}{\lambda^2} = 6\cdot4 = 24 \text{ s}^2
```

**c)** 💡 **Truco Gamma–Poisson:** "el paquete se forma antes de 12 s" es lo mismo que "en 12 s llegaron **al menos 6** mensajes". La cantidad en 12 s es Poisson con λ = 0,5·12 = 6:

```math
P(T < 12) = P(N \ge 6) = 1 - P(N \le 5) \approx 0{,}5543
```

```
X~Po(λ)   λ=6   P(X≥x)   x=6   → 0.55432
```
También se puede directo con la Gamma de la app (`X~Gamma(α;β)`). Fijate si pide la tasa λ o la escala 1/λ.

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

**Paso 1, pasar la condición a Y.** L está en cientos de pesos, así que 18 800 pesos son 188:

```math
L > 188 \;\Leftrightarrow\; 30Y + 8 > 188 \;\Leftrightarrow\; Y > 6 \text{ horas}
```

**Paso 2, P(Y > 6) con una Gamma.** 💡 Una Gamma(α; λ) con α **entero** es el tiempo hasta el α-ésimo evento de un proceso de Poisson con ritmo λ (❌). Entonces "Y > 6" equivale a "en 6 horas ocurrieron **menos de 3** eventos", es decir a lo sumo 2. Esa cantidad es Poisson con λ·6 = 0,5·6 = 3:

```math
P(Y > 6) = P(N \le 2) = e^{-3}\left(1 + 3 + \frac{3^2}{2}\right) = e^{-3}\cdot8{,}5 \approx 0{,}4232
```

```
X~Po(λ)   λ=3   P(X≤x)   x=2   → 0.42319
```

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

**Idea:** L es una función de Y. Por linealidad (❌), $E(L) = 20E(Y) - 3E(Y^2)$. Solo hacen falta E(Y) y E(Y²).

💡 **Gamma(α; λ)** (❌): $E(Y) = \frac\alpha\lambda$ y $V(Y) = \frac{\alpha}{\lambda^2}$ (es la suma de α exponenciales).

```math
E(Y) = \frac{100}{20} = 5 \qquad V(Y) = \frac{100}{400} = 0{,}25
```

💡 $E(Y^2)$ se despeja de 📄 H1, $V(Y) = E(Y^2) - E(Y)^2$:

```math
E(Y^2) = V(Y) + E(Y)^2 = 0{,}25 + 25 = 25{,}25
```

$$E(L) = 20\cdot5 - 3\cdot25{,}25 = 100 - 75{,}75 = 24{,}25$$

⚠️ Es un error común poner $E(Y^2) = E(Y)^2 = 25$. Daría 25, no 24,25.

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

Cada componente dura un tiempo exponencial con α = 1/100: $P(\text{dura más de } t) = e^{-t/100}$ (📄 H1).

**a) En serie** (como luces de árbol viejas): el sistema se corta en cuanto falla **una**. T es el **mínimo** de los dos tiempos.

Truco: "el sistema dura más de t" significa que **las dos** duran más de t. Como son independientes, se multiplica:

```math
P(T > t) = e^{-t/100}\cdot e^{-t/100} = e^{-t/50}
```

Esa es la forma de una exponencial con parámetro 1/50. Entonces T ~ Exp(1/50):
- $F(t) = 1 - e^{-t/50}$;
- $f(t) = \frac1{50}e^{-t/50}$ para t ≥ 0.

Dura la mitad en promedio: 50 h.

**b) En paralelo:** el sistema sigue andando mientras funcione **alguna**, y falla cuando fallan **las dos**. T es el **máximo**.

Truco: "el sistema ya falló en t" significa que **las dos** fallaron antes de t:

```math
F(t) = P(T \le t) = \left(1 - e^{-t/100}\right)^2
```

💡 La densidad es la derivada de F (❌), con la regla de la cadena:

```math
f(t) = 2\left(1 - e^{-t/100}\right)\cdot\frac{1}{100}e^{-t/100} = \frac1{50}e^{-t/100} - \frac1{50}e^{-t/50}
```

Ya **no** es exponencial.

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

💡 **Distribución Normal N(μ; σ).** Es la famosa "campana": simétrica alrededor de la media μ, con un ancho que controla el desvío σ. La mayoría de los valores cae cerca de μ, y es raro alejarse más de 2 o 3 σ.

💡 **Estandarizar** (📄 H1, $`\frac{X - \mu}{\sigma} = Z \sim N(0;1)`$). Cualquier normal se lleva a la normal estándar Z (media 0 y desvío 1) restando μ y dividiendo por σ. El valor de z dice **a cuántos desvíos de la media** está x. Después, $P(Z < z) = \Phi(z)$ (📄 H1) sale de la tabla o de la app.

Con la app no hace falta estandarizar: se carga μ = 5 y σ = 10 directamente. Ojo: la app pide **σ**, no la varianza.

**a)**
```
P(X<0):   X~N(μ;σ)   μ=5   σ=10   P(X<x)   x=0    → 0.30854
P(X>10):  X~N(μ;σ)   μ=5   σ=10   P(X>x)   x=10   → 0.30854
P(X≥15):  X~N(μ;σ)   μ=5   σ=10   P(X>x)   x=15   → 0.15866
```
Con tabla: P(X < 0) = Φ((0 − 5)/10) = Φ(−0,5); P(X > 10) = 1 − Φ(0,5), que da lo mismo por simetría; P(X ≥ 15) = 1 − Φ(1). En una continua, > y ≥ dan igual.

**b)** "Entre" es la acumulada hasta el borde derecho menos la acumulada hasta el izquierdo (📄 H1, $`P(a < X < b) = F(b) - F(a)`$):
- P(−20 < X < 15) = Φ(1) − Φ(−2,5) = 0,8413 − 0,0062 = 0,8351.
- P(−5 ≤ X ≤ 30) = Φ(2,5) − Φ(−1) = 0,8351. Da igual por simetría.

**c)** Ahora se busca el **valor** x que deja 5 % a la derecha (búsqueda "al revés"):
```
X~N(μ;σ)   μ=5   σ=10   P(X>x)=0.05   → x=21.449
```
Con tabla: z = 1,645, así que x = μ + z·σ = 5 + 1,645·10 = 21,45.

**d)** El x que deja 23 % a la izquierda:
```
X~N(μ;σ)   μ=5   σ=10   P(X<x)=0.23   → x=−2.388
```
Con tabla: z = −0,739, así que x = 5 − 7,39 ≈ −2,39.

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

💡 **Estandarizar** (📄 H1): $Z = \frac{X - \mu}{\sigma} \sim N(0;1)$. Cuando el enunciado está en "cantidad de σ" alrededor de μ, al estandarizar desaparecen μ y σ.

**a)** $|X - \mu| \le 1{,}24\sigma$ significa que X está a menos de 1,24 desvíos de la media para cualquier lado. Dividiendo por σ: $|Z| \le 1{,}24$, es decir $-1{,}24 \le Z \le 1{,}24$.

Por la simetría de la campana, el área entre −z y z es $\Phi(z) - \Phi(-z) = 2\Phi(z) - 1$:

```math
P(-1{,}24 \le Z \le 1{,}24) = 2\cdot0{,}8925 - 1 = 0{,}785
```

```
X~N(μ;σ)   μ=0   σ=1   P(X<x)   x=1.24   → 0.89251
```

**b)** Mismo razonamiento al revés: se busca qué z deja 95 % en el medio. Si el medio tiene 0,95, cada cola tiene 0,025, así que a la izquierda de z queda 0,975:
```
X~N(μ;σ)   μ=0   σ=1   P(X<x)=0.975   → x=1.95996
```

```math
\frac{c}{\sigma} = 1{,}96 \;\Rightarrow\; c = 1{,}96\,\sigma
```

Es la regla famosa: el 95 % de una normal está a menos de 1,96 σ de la media.

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

💡 **Todo se mide en desvíos.** Estandarizando (📄 H1, $`Z = \frac{X - \mu}{\sigma}`$), "a 3 desviaciones de la media" significa z = ±3. No hace falta conocer μ ni σ.

"Partes por millón" (ppm) es la probabilidad multiplicada por 1 000 000.

**a)** Las especificaciones están en μ − 3σ y μ + 3σ. No cumple el que cae **afuera**: Z < −3 o Z > 3. Las dos colas son iguales:

```math
2(1 - \Phi(3)) = 2\cdot0{,}00135 = 0{,}0027 \;\Rightarrow\; 2700 \text{ ppm}
```

```
X~N(μ;σ)   μ=0   σ=1   P(X>x)   x=3   → 0.00135
```

**b)** La media sube 1,5σ, pero los límites no se mueven. Medidos desde la nueva media:
- el límite superior queda a 3 − 1,5 = **1,5σ** por encima;
- el inferior queda a 3 + 1,5 = **4,5σ** por debajo.

```math
P(Z > 1{,}5) + P(Z < -4{,}5) = 0{,}0668 + 0{,}0000034 \approx 0{,}0668 \;\Rightarrow\; \approx 66\,810 \text{ ppm}
```

```
X~N(μ;σ)   μ=0   σ=1   P(X>x)   x=1.5    → 0.06681
X~N(μ;σ)   μ=0   σ=1   P(X<x)   x=−4.5   → 0.0000034
```
Un corrimiento de 1,5σ multiplica los defectos por 25.

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

💡 **Normal N(μ; σ)**: la campana centrada en μ = 75 con desvío σ = 7. Para calcular, o se carga en la app con μ y σ, o se **estandariza** (📄 H1, $`Z = \frac{X - \mu}{\sigma}`$) y se usa Φ.

**a)**

```math
P(X > 95) = P\left(Z > \frac{95 - 75}{7}\right) = 1 - \Phi(2{,}857) \approx 0{,}0021
```

```
X~N(μ;σ)   μ=75   σ=7   P(X>x)   x=95   → 0.00214
```

**b)** Primero la proporción entre 80 y 95 (📄 H1, $`P(a < X < b) = F(b) - F(a)`$):

```math
\Phi(2{,}857) - \Phi(0{,}714) = 0{,}99786 - 0{,}76247 = 0{,}2354
```

"Estimar el número" de alumnos es multiplicar esa proporción por el total: 15 000·0,2354 ≈ **3531 alumnos**.

**c)** "El peso no superado por el 10 %" es el valor que deja 10 % a la izquierda (percentil 10):
```
X~N(μ;σ)   μ=75   σ=7   P(X<x)=0.1   → x=66.03
```
Con tabla: $z_{0{,}1} = -1{,}2816$, así que x = 75 − 1,2816·7 ≈ 66,03 kg.

**d)** Una cadena "normal → binomial":
1. **Un alumno:** p = P(X > 80) = 0,2375.
   ```
   X~N(μ;σ)   μ=75   σ=7   P(X>x)   x=80   → 0.23753
   ```
2. **Diez alumnos:** cada uno pesa más de 80 (éxito) con p = 0,2375, independientes. 💡 Contar éxitos es **binomial** (📄 H1): Y ~ Bin(10; 0,2375). "Al menos la mitad" es Y ≥ 5:
   ```
   X~Bin(n,p)   n=10   p=0.23753   P(X≥x)   x=5   → 0.06440
   ```
La guía da 0,0699 porque redondea distinto el z.

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

**El problema:** no se conocen ni μ ni σ. Hay dos datos y dos incógnitas, así que se arma un sistema.

💡 **Estandarizar** (📄 H1, $`Z = \frac{X - \mu}{\sigma}`$). Cada dato dice "este valor de X deja tal área". Con la app se busca el z que deja esa área, y se iguala a $\frac{x - \mu}{\sigma}$.

- "El 15 % mide menos de 13": el z que deja 0,15 a la izquierda.
  ```
  X~N(μ;σ)   μ=0   σ=1   P(X<x)=0.15   → x=−1.0364
  ```

  ```math
  \frac{13 - \mu}{\sigma} = -1{,}0364
  ```

- "El 10 % mide más de 14": el z que deja 0,10 a la derecha.
  ```
  X~N(μ;σ)   μ=0   σ=1   P(X>x)=0.10   → x=1.2816
  ```

  ```math
  \frac{14 - \mu}{\sigma} = 1{,}2816
  ```

**Resolver.** Se resta la primera ecuación de la segunda, y μ desaparece:

```math
\frac{14 - 13}{\sigma} = 1{,}2816 + 1{,}0364 = 2{,}318 \;\Rightarrow\; \sigma \approx 0{,}4314
```

Reemplazando: $\mu = 13 + 1{,}0364\cdot0{,}4314 \approx 13{,}447$.

**a)** No apta si mide menos de 12,8 **o** más de 13,8. Son dos colas, que se suman:
```
X~N(μ;σ)   μ=13.447   σ=0.4314   P(X<x)   x=12.8   → 0.0668
X~N(μ;σ)   μ=13.447   σ=0.4314   P(X>x)   x=13.8   → 0.2067
```

```math
P(\text{no apta}) \approx 0{,}0668 + 0{,}2067 = 0{,}2735
```

**b)** Cada pieza de la bolsa es no apta (éxito) con p = 0,2735, independientes. 💡 Contar éxitos es **binomial** (📄 H1), Bin(10; 0,2735). Se acepta si hay a lo sumo una no apta:
```
X~Bin(n,p)   n=10   p=0.2735   P(X≤x)   x=1   → 0.1952
```
La guía da 0,27315 y 0,2019, por redondear z a dos decimales.

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

💡 **Normal** N(50; 3). Se calcula con la app (μ = 50, σ = 3) o estandarizando (📄 H1, $`Z = \frac{X - 50}{3}`$).

**a)** "Entre 46 y 55" es la acumulada hasta 55 menos la acumulada hasta 46:

```math
\Phi\left(\frac{55 - 50}{3}\right) - \Phi\left(\frac{46 - 50}{3}\right) = \Phi(1{,}667) - \Phi(-1{,}333) = 0{,}9522 - 0{,}0912 = 0{,}861
```

```
X~N(μ;σ)   μ=50   σ=3   P(X<x)   x=55   → 0.95221
X~N(μ;σ)   μ=50   σ=3   P(X<x)   x=46   → 0.09121
```

**b)** Un intervalo **simétrico** alrededor de la media que contenga el 95 %: deja 2,5 % en cada cola. El z correspondiente deja 0,975 a la izquierda, z = 1,96:

```math
c = 1{,}96\cdot\sigma = 1{,}96\cdot3 = 5{,}88
```

El intervalo es (44,12; 55,88).

**c)** Cada pieza es aceptable con p = 0,861, independientes. 💡 La cantidad de aceptables es **binomial** Bin(8; 0,861), y su esperanza es n·p (❌):

```math
8\cdot0{,}861 \approx 6{,}9
```

**d)** Truco del máximo: "el máximo de las tres no supera 52" equivale a "**ninguna** supera 52", o sea las tres ≤ 52. Por independencia se multiplica:

```math
P(X \le 52)^3 = \Phi(2/3)^3 = 0{,}7475^3 \approx 0{,}4177
```

```
X~N(μ;σ)   μ=50   σ=3   P(X<x)   x=52   → 0.74751
```

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

💡 **La densidad normal** (❌, la fórmula no está en la hoja) es

```math
f_X(x) = \frac{1}{\sigma\sqrt{2\pi}}e^{-\frac12\left(\frac{x - \mu}{\sigma}\right)^2}
```

Para demostrar que Y es normal, hay que llegar a una densidad **con esta misma forma**, y leer cuáles son su "μ" y su "σ".

💡 **Método de la función de distribución** (❌): para obtener la densidad de Y = g(X), primero se calcula $F_Y(y) = P(Y \le y)$ despejando X, y después se deriva.

**Caso a > 0.** Se despeja X adentro de la probabilidad. Al dividir por a positivo, la desigualdad no se da vuelta:

```math
F_Y(y) = P(aX + b \le y) = P\left(X \le \frac{y - b}{a}\right) = F_X\left(\frac{y-b}{a}\right)
```

Se deriva con la regla de la cadena, porque la derivada de $F_X$ es $f_X$ y la de $\frac{y - b}{a}$ es $\frac1a$:

```math
f_Y(y) = \frac1a f_X\left(\frac{y-b}{a}\right) = \frac{1}{a\sigma\sqrt{2\pi}}\exp\left[-\frac12\left(\frac{\frac{y-b}{a} - \mu}{\sigma}\right)^2\right]
```

Se acomoda lo de adentro del exponente multiplicando arriba y abajo por a:

```math
\frac{\frac{y-b}{a} - \mu}{\sigma} = \frac{y - b - a\mu}{a\sigma} = \frac{y - (a\mu + b)}{a\sigma}
```

Queda exactamente la forma normal, con "μ" igual a $a\mu + b$ y "σ" igual a $a\sigma$.

**Caso a < 0.** Al despejar se da vuelta la desigualdad, y aparece un signo menos que termina en |a|. Resultado: **Y ~ N(aμ + b; |a|σ)**, o sea varianza a²σ².

Es lo que da la intuición: $E(Y) = aE(X) + b$ y $V(Y) = a^2V(X)$. La novedad es que la forma de campana se conserva.

</details>

**Respuesta:** Y ~ N(aμ + b; a²σ²), es decir, media aμ + b y desvío |a|σ.

</details>

---

[← Volver al menú principal](../README.md)
