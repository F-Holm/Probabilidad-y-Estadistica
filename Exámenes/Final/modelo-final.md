# Modelo de Examen Final 2018 (Guía de TP, cap. 7.3)

Probabilidad y Estadística — UTN FRBA. Modelo de examen que aparece al final de la [Guía de Trabajos Prácticos](../../GU%C3%8DA%20DE%20TPs.pdf).

> **Aprobación:** al menos el 50 % de la práctica y al menos el 50 % de la teórica.

Cada ejercicio tiene un botón **Solución**. Al abrirlo aparece la respuesta y, arriba de ella, el botón **Solución paso a paso**.

---

### Ejercicio 1) Consumo telefónico

En una empresa se sabe que el consumo telefónico tiene distribución normal y que su promedio histórico es de 2520 pulsos mensuales. El gerente considera que, debido al uso de los celulares, el promedio de pulsos de línea ha bajado. Propone, para contestar a esta cuestión, un test de hipótesis basado en una muestra de los últimos 12 meses que le facilita su asistente:

2477 2443 2748 2662 2531 2578 2744 2301 2049 2237 2198 2602

- a) ¿Cuál es la conclusión del gerente a nivel 0,05?
- b) Cinco años después, el gerente quiere rehacer la misma prueba de hipótesis con los datos de los 5 años previos. Le pide a su asistente que le facilite los datos y este (como ya era la hora de retirarse) decide darle los mismos datos que le dio cinco años atrás, pero repetidos cinco veces. Si el gerente rehace el test con esos datos, ¿qué conclusión obtendrá al mismo nivel que antes?

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

a) Test:
1. H₀: μ ≥ 2520 vs. H₁: μ < 2520.
2. α = 0,05.
3. Población normal, σ desconocido, n = 12 ⇒ $T = \frac{\bar X - 2520}{S/\sqrt n} \sim t_{11}$.
4. $\bar x = 2464{,}17$ y s = 224,92 ⇒ $t_{obs} = \frac{2464{,}17 - 2520}{224{,}92/\sqrt{12}} = -0{,}86$.
5. RC = {T < $t_{11;\,0{,}05}$ = −1,796}. Como −0,86 ∉ RC ⇒ no se rechaza H₀ (p = 0,204).

El gerente **no** puede afirmar que el consumo bajó.

b) Con los 60 datos (los 12 repetidos 5 veces):
- La media no cambia: $\bar x = 2464{,}17$.
- s casi no cambia: $s = 224{,}92\sqrt{\frac{5\cdot11}{59}} = 217{,}16$.
- Pero n = 60 ⇒ $t_{obs} = \frac{-55{,}83}{217{,}16/\sqrt{60}} = -1{,}99 < t_{59;\,0{,}05} = -1{,}671$ ⇒ **se rechaza H₀** (p = 0,026).

Concluiría que el consumo bajó, pero es una conclusión **inválida**: los datos repetidos no son una muestra aleatoria (no son independientes). Inflar n achica artificialmente el error estándar $s/\sqrt n$ sin aportar información nueva.

</details>

**Respuesta:**

- a) $t_{obs}$ = −0,86 > −1,796 ⇒ no se rechaza H₀: no hay evidencia de que el promedio haya bajado
- b) $t_{obs}$ = −1,99 < −1,671 ⇒ rechazaría H₀, pero la conclusión no es válida porque los datos repetidos no son una muestra aleatoria independiente

</details>

---

### Ejercicio 2) Ascensor de carga

Se diseña un ascensor de carga cuyo límite es 1000 kg. El peso de cada caja sigue una distribución normal con un peso medio de 32 kg y un desvío estándar de 10 kg.

- a) ¿Cuál es la probabilidad de que un grupo de 30 cajas exceda el límite de carga?
- b) Se toma una muestra aleatoria simple de 2 cajas. ¿Cuál es la probabilidad de que el mínimo de la muestra sea inferior a 30 kg?

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

X ~ N(32; 10) kg, con pesos de cajas independientes.

a) $W = X_1 + \dots + X_{30} \sim N\left(30\cdot32;\ 10\sqrt{30}\right) = N(960;\ 54{,}77)$.

$P(W > 1000) = P\left(Z > \frac{40}{54{,}77}\right) = P(Z > 0{,}73) = 0{,}2326$.

b) El mínimo es mayor o igual que 30 ⇔ **las dos** cajas pesan al menos 30:

$P(\min < 30) = 1 - P(X_1 \ge 30)\,P(X_2 \ge 30)$.

$P(X \ge 30) = P(Z \ge -0{,}2) = 0{,}5793$ ⇒ $P(\min < 30) = 1 - 0{,}5793^2 = 0{,}6645$.

</details>

**Respuesta:**

- a) ≈ 0,2326
- b) ≈ 0,6645

</details>

---

### Ejercicio 3) Profundidad de un disparo

Sea X (mm) una variable aleatoria que describe la profundidad de un disparo. Su función de densidad de probabilidad es:

$$f_X(x) = \begin{cases} 2x^{-1} & c \le x \le c + 2\\ 0 & \text{otro caso}\end{cases}$$

- a) Indicar si los eventos {x / x > c + 1} y {x / x < c + 1,5} son independientes.
- b) Si el diámetro de la perforación del disparo Y, en mm, se puede definir como Y = 10X + 1, hallar el valor del diámetro esperado.

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

**Constante c:** el área total vale 1.

$\int_c^{c+2}\frac2x\,dx = 2\ln\frac{c+2}c = 1 \Rightarrow \frac{c+2}c = e^{1/2} \Rightarrow c = \frac2{\sqrt e - 1} = 3{,}083$.

Para c ≤ x ≤ c + 2, $F(x) = 2\ln\frac xc$.

a) A = {X > c + 1} y B = {X < c + 1,5}:
- $P(A) = 1 - 2\ln\frac{4{,}083}{3{,}083} = 0{,}4381$
- $P(B) = 2\ln\frac{4{,}583}{3{,}083} = 0{,}7929$
- $P(A \cap B) = P(c + 1 < X < c + 1{,}5) = 2\ln\frac{4{,}583}{4{,}083} = 0{,}2310$
- $P(A)\,P(B) = 0{,}3474 \ne 0{,}2310$ ⇒ **no son independientes**.

b) $E(X) = \int_c^{c+2} x\cdot\frac2x\,dx = \int_c^{c+2} 2\,dx = 4$ mm.

Por linealidad: $E(Y) = 10E(X) + 1 = 41$ mm.

</details>

**Respuesta:**

- a) c = 2/(√e − 1) ≈ 3,083; P(A ∩ B) = 0,231 ≠ P(A)P(B) = 0,347 ⇒ no son independientes
- b) E(Y) = 41 mm

</details>

---

### Ejercicio 4) Corrosión del acero

La siguiente información resultó de un estudio realizado para examinar la relación entre una medida de la corrosión del acero y la concentración de NaPO₄.

| Corrosión | 7,68 | 6,95 | 6,30 | 5,75 | 5,01 | 1,43 | 0,93 | 0,72 | 0,68 | 0,65 | 0,56 |
|---|---|---|---|---|---|---|---|---|---|---|---|
| **NaPO₄** | 2,5 | 5,03 | 7,6 | 11,6 | 13,0 | 19,6 | 26,2 | 33,0 | 40,0 | 50,0 | 55,0 |

- a) Estime el modelo lineal para explicar la corrosión conociendo el nivel de NaPO₄. Indique los supuestos del modelo.
- b) Estime el coeficiente de determinación e interprételo en el contexto del problema.

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

X = NaPO₄ (explicativa), Y = corrosión, n = 11.

**Sumas:** $\sum x = 263{,}53$, $\sum y = 36{,}66$, $\sum x^2 = 9677{,}47$, $\sum y^2 = 209{,}76$, $\sum xy = 400{,}52$.

**Cantidades básicas:** $\bar x = 23{,}957$ y $\bar y = 3{,}333$.
- $S_{xx} = 9677{,}47 - \frac{263{,}53^2}{11} = 3364{,}01$
- $S_{yy} = 209{,}76 - \frac{36{,}66^2}{11} = 87{,}586$
- $S_{xy} = 400{,}52 - \frac{263{,}53\cdot36{,}66}{11} = -477{,}75$

a) $b_1 = \frac{-477{,}75}{3364{,}01} = -0{,}1420$ y $b_0 = 3{,}333 + 0{,}1420\cdot23{,}957 = 6{,}735$.

$\hat y = 6{,}735 - 0{,}142x$ (2,5 ≤ x ≤ 55): a más NaPO₄, menos corrosión.

**Supuestos** del modelo $Y = \beta_0 + \beta_1X + \varepsilon$: errores $\varepsilon \sim N(0; \sigma)$, con varianza constante para todo x (homocedasticidad) e independientes.

b) $r = \frac{-477{,}75}{\sqrt{3364{,}01\cdot87{,}586}} = -0{,}880$ ⇒ $R^2 = r^2 = 0{,}775$.

**Observación:** el diagrama de dispersión muestra una caída brusca entre x = 13 y x = 19,6 y luego un "piso". La relación no parece realmente lineal, así que convendría revisar los residuos (o probar una transformación) antes de confiar en la recta.

</details>

**Respuesta:**

- a) $\hat y = 6{,}735 - 0{,}142x$. Supuestos: errores normales, de media 0, con varianza constante e independientes
- b) R² ≈ 0,775: el 77,5 % de la variabilidad de la corrosión queda explicada por la concentración de NaPO₄ a través de la recta

</details>

---

### Teórico 1) Eventos independientes y excluyentes

- a) Defina eventos independientes y eventos mutuamente excluyentes. Ejemplifique.
- b) Demuestre que si dos eventos son independientes, también lo son sus complementos.

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

a) Definiciones y ejemplos:
- **Independientes:** $P(A \cap B) = P(A)\,P(B)$ (equivalentemente, P(A/B) = P(A): que ocurra B no cambia la probabilidad de A). Ejemplo: tirar dos monedas, A = "cara en la 1.ª" y B = "cara en la 2.ª": P(A ∩ B) = 1/4 = (1/2)(1/2).
- **Mutuamente excluyentes:** $A \cap B = \emptyset$, es decir, no pueden ocurrir juntos (P(A ∩ B) = 0). Ejemplo: tirar un dado, A = "sale par" y B = "sale 3".

No es lo mismo: si P(A) > 0 y P(B) > 0 y son excluyentes, entonces **no** son independientes, porque P(A ∩ B) = 0 ≠ P(A)P(B).

b) Por De Morgan, $\bar A \cap \bar B = \overline{A \cup B}$. Entonces:

$P(\bar A \cap \bar B) = 1 - P(A \cup B) = 1 - P(A) - P(B) + P(A)P(B)$ (por la independencia).

Factorizando: $= (1 - P(A))(1 - P(B)) = P(\bar A)\,P(\bar B)$.

</details>

**Respuesta:** Independientes: P(A ∩ B) = P(A)P(B). Excluyentes: A ∩ B = ∅. Demostración: $P(\bar A \cap \bar B) = 1 - P(A \cup B) = (1 - P(A))(1 - P(B)) = P(\bar A)P(\bar B)$.

</details>

---

### Teórico 2) Distribución exponencial

- a) Defina la distribución exponencial, señalando el soporte de la variable.
- b) Halle su valor esperado y explique la relación con la distribución de Poisson.

<details>
<summary><b>Solución</b></summary>

<details>
<summary>Solución paso a paso</summary>

a) X ~ Exp(λ), con λ > 0, si su densidad es

$$f(x) = \lambda e^{-\lambda x}, \quad x \ge 0 \quad (0 \text{ en otro caso})$$

El soporte es $[0; +\infty)$. Su distribución es $F(x) = 1 - e^{-\lambda x}$. Modela tiempos de espera o duraciones y tiene **falta de memoria**: P(X > s + t / X > s) = P(X > t).

b) Integrando por partes:

$E(X) = \int_0^\infty x\lambda e^{-\lambda x}\,dx = \left[-xe^{-\lambda x}\right]_0^\infty + \int_0^\infty e^{-\lambda x}\,dx = 0 + \frac1\lambda = \frac1\lambda$.

**Relación con Poisson:** si los eventos ocurren según un proceso de Poisson con intensidad α (N = cantidad de ocurrencias en [0; t], con N ~ Po(αt)), el tiempo T hasta la primera ocurrencia (o entre dos consecutivas) cumple:

$P(T > t) = P(N = 0 \text{ en } [0; t]) = e^{-\alpha t}$ ⇒ T ~ Exp(λ = α).

La Poisson **cuenta** ocurrencias en un continuo y la exponencial **mide** el tiempo (o la distancia) entre ellas. El tiempo medio entre ocurrencias, 1/α, es la inversa de la tasa.

</details>

**Respuesta:** $f(x) = \lambda e^{-\lambda x}$ para x ≥ 0 (soporte [0; ∞)); E(X) = 1/λ. El tiempo entre ocurrencias de un proceso de Poisson de intensidad α es Exp(α).

</details>

---

[← Volver al menú principal](../../README.md)
