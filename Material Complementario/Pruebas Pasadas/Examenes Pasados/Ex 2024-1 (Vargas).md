Pontificia Universidad Cat´olica de Chile
Escuela de Ingenier´ıa
Departamento de Ingenier´ıa Industrial y de Sistemas
ICS2123-2 – Modelos Estoc´asticos
Profesor Nicol´as Vargas C.
Primer Semestre 2024
Examen
Duraci´on: 2.5 horas
Resuelva 5 de las siguientes 6 preguntas. Marque claramente con una X toda la hoja de la pregunta que no contestar´a. En
caso de no descartar una pregunta, no se contar´a el problema con mayor puntaje para el c´alculo de la nota.
Problema 1 (12 puntos)
A un banco llegan personas de acuerdo a un proceso de Poisson a tasa λ personas por hora. El banco abri´o a las 9 AM y
usted sabe sabe que entre las 9 AM y 11 AM llegaron 8 personas.
1. (5 puntos) ¿Cu´al es la probabilidad de que, partiendo a las 10 AM, no llegue nadie en las pr´oximas 2 horas?
2. (4 puntos) ¿Cu´al es la probabilidad de que al mediod´ıa hayan llegado 25 personas en total?
3. (3 puntos) Suponga que ahora le dicen que el banco en realidad abri´o a las 8 AM. Determine nuevamente la proba-
bilidad de que al mediod´ıa hayan llegado 25 personas en total.
Soluci´on Problema 1
1. Por simplicidad, se usar´a la siguiente notaci´on para el desarrollo del problema: N(t1, t2) = N(t2) −N(t2).
P(N(10, 12)) = 0|N(9, 11) = 8) = P(N(10, 12) = 0, N(9, 11) = 8)
P(N(9, 11) = 8)
= P(N(9, 10) = 8, N(10, 12) = 0)
P(N(9, 11) = 8)
= P(N(9, 10) = 8)P(N(10, 12) = 0)
P(N(9, 11) = 8)
= P(N(1) = 8)P(N(2) = 0)
P(N(2) = 8)
=
(2λ)0e−2λ
0!
· λ8e−λ
8!
(2λ)8e−2λ
8!
= e−λ
28
2.
P(N(9, 12) = 25|N(9, 11) = 8) = P(N(11, 12) = 17)
1

= P(N(1) = 17)
= λ17e−λ
17!
3.
P(N(8, 12) = 25|N(9, 11) = 8) = P(N(8, 12) = 0, N(9, 11) = 8)
P(N(9, 11) = 8)
=
P17
i=0 P(N(8, 9) = i, N(9, 11) = 8, N(11, 12) = 17 −i)
P(N(9, 11) = 8)
=
P17
i=0 P(N(8, 9) = i)P(N(9, 11) = 8)P(N(11, 12) = 17 −i)
P(N(9, 11) = 8)
=
17
X
i=0
P(N(8, 9) = i)P(N(11, 12) = 17 −i)
=
17
X
i=0
P(N(1) = i)P(N(1) = 17 −i)
=
17
X
i=0
λie−λ
i!
· λ17−ie−λ
(17 −i)!
=
17
X
i=0
λ17e−2λ
i!(17 −i)!
Problema 2 (12 puntos)
Sean X e Y variables aleatorias independientes con distribuci´on exponencial, de par´ametros α y β, respectivamente.
1. (6 puntos) Demuestre que la distribuci´on del m´ınimo entre X e Y es exponencial y especifique el par´ametro de dicha
distribuci´on.
2. (6 puntos) Calcule P(X < Y ).
Soluci´on Problema 2
1. Sea Z = m´ın(X, Y ). Queremos encontrar la funci´on de distribuci´on acumulativa (CDF) de Z, denotada por FZ(z).
FZ(z) = P(Z ≤z) = P(m´ın(X, Y ) ≤z)
= 1 −P(m´ın(X, Y ) > z)
= 1 −P(X > z, Y > z)
= 1 −P(X > z)P(Y > z)
(independencia de X y Y )
= 1 −e−αze−βz
= 1 −e−(α+β)z
La CDF FZ(z) corresponde a una distribuci´on exponencial con par´ametro α + β. Es decir, Z es exponencial con
par´ametro α + β.
2. Condicionando sobre Y tenemos que:
2

P(X < Y ) =
Z ∞
0
P(X < Y | Y = y)fY (y) dy
=
Z ∞
0
P(X < y)fY (y) dy
=
Z ∞
0
(1 −e−αy)βe−βy dy
= β
Z ∞
0
e−βy dy −
Z ∞
0
e−(α+β)y dy

= β

−1
β e−βy
∞
0
−

−
1
α + β e−(α+β)y
∞
0

= β
 1
β −
1
α + β

= 1 −
1
α + β
=
α
α + β
Problema 3 (12 puntos)
Considere una Cadena de Markov en Tiempo Discreto con espacio de estados {1, 2, 3, 4, 5, 6} y la siguiente matriz de
probabilidades de transici´on:
P =











0,4
0,2
0,2
0,2
0
0
0
0
0
0
0
1
0,8
0
0
0,2
0
0
0
0
0
1
0
0
0
1
0
0
0
0
0
0
0
0
1
0











1. (2 puntos) Determine las clases de estados y clasifique todos los estados en transientes, recurrentes positivos o nulos,
y determine si son aperi´odicos o peri´odicos, y el valor del per´ıodo si es que corresponde.
2. (2 puntos) ¿Existe l´ımn→∞P (n)
ij
para todo (i, j)? Justifique.
3. (4 puntos) ¿Existe alguna distribuci´on estacionaria? Si su respuesta es afirmativa, especifique al menos una distribuci´on
estacionaria y verifique que cumple con su correspondiente sistema de ecuaciones.
4. (4 puntos) Asumiendo que el estado inicial es el estado 1, calcule la probabilidad de eventualmente visitar el estado 4.
Soluci´on Problema 3
1. Las clases de estado son:
{1, 3}: Transiente aperi´odica.
{2, 5, 6}: Recurrente positiva peri´odica, con per´ıodo 3.
{4}: Recurrente positiva aperi´odica.
3

2. Como existe una clase recurrente positiva peri´odica, no existe l´ımn→∞P (n)
ij
para todo (i, j).
3. Para determinar si existe alguna distribuci´on estacionaria, debemos encontrar un vector π tal que π⊺= π⊺P con
π ≥0 y π1 + . . . + π6 = 1. Analizando la cadena, se aprecia que si partimos en el estado 4, una soluci´on estacionaria
es π = (0, 0, 0, 1, 0, 0). Por otro lado, si partimos desde un estado de la clase {2, 5, 6}, otra soluci´on estacionaria es
π = (0, 1
3, 0, 0, 1
3, 1
3).
4. Nos piden calcular F(1, 4), luego:
F(1, 4) = P1,4 + P1,3F(3, 4) + P1,1F(1, 4)
F(1, 4) = 0,2 + 0,2F(3, 4) + 0,4F(1, 4)
F(3, 4) = P3,4 + P3,1F(1, 4)
F(3, 4) = 0,2 + 0,8F(1, 4)
⇒F(1, 4) = 0,2 + 0,2(0,2 + 0,8F(1, 4)) + 0,4F(1, 4)
F(1, 4) = 0,2 + 0,04 + 0,16F(1, 4) + 0,4F(1, 4)
F(1, 4) = 0,24 + 0,56F(1, 4)
F(1, 4) =
0,24
1 −0,56 = 0,5454
Problema 4 (12 puntos)
Usted junto a un amigo han decidido instalarse con un puesto para lustrar zapatos que consta de dos sillas. En la primera silla,
que es atendida por usted, los zapatos del cliente son limpiados y embetunados. Luego, si la segunda silla est´a desocupada,
los clientes se sientan y su amigo le saca brillo a sus zapatos. Los tiempos de servicio de ambas sillas son variables aleatorias
independientes, que distribuyen exponencial con tasas µ1 y µ2 respectivamente. Considere que los clientes potenciales tienen
tiempos de llegada exponenciales de tasa λ y que solo entran al establecimiento si la primera silla est´a desocupada.
1. (4 puntos) Construya una Cadena de Markov en Tiempo Continuo que modele el estado de ocupaci´on de las sillas de
su puesto. Explicite claramente los estados y sus respectivas tasas de transici´on.
4

2. (2 puntos) Justifique la existencia de una distribuci´on de probabilidades estacionarias y construya el sistema de
ecuaciones que permita calcularlas.
3. (2 puntos) En el largo plazo, ¿cu´al es la tasa efectiva de llegada de clientes al puesto?
4. (2 puntos) En el largo plazo, ¿cu´al es el n´umero promedio de clientes dentro del puesto?
5. (2 puntos) En el largo plazo, ¿cu´al es el tiempo promedio que pasa un cliente que entra al puesto, dentro de ´este?
Soluci´on Problema 4
1. La cadena con los estados y tasas de transici´on se muestra en la siguiente figura:
2. Dado que todos los estados est´an conectados y que la probabilidad de estar en un estado cualquiera existe y es
independiente del estado inicial, se tiene que existe la distribuci´on l´ımite y por ende, una distribuci´on de probabilidades
estacionarias. Adem´as, a partir del diagrama se puede plantear el siguiente sistema de ecuaciones de equilibrio en el
largo plazo:
P0,0λ = P0,1µ2
P1,0µ1 = P0,0λ + P1,1µ2
P0,1(λ + µ2) = P1,0µ1 + PEµ2
P1,1(µ1 + µ2) = P0,1λ
PEµ2 = P1,1µ1
P0,0 + P1,0 + P0,1 + P1,1 + PE = 1
3. Utilizando las probabilidades estacionarias definidas en el inciso anterior, se tiene que la tasa efectiva de llegada es:
λ(P0,0 + P0,1)
4. Interpretando las probabilidades estacionarias como la probabilidad de encontrar al sistema (en el largo plazo) en un
estado en particular tendremos que:
L = P0,1 + P1,0 + 2P1,1 + 2PE
5

5. Si un cliente llega y las dos sillas est´an vac´ıas, el tiempo promedio del cliente en el puesto est´a dado por la suma del
tiempo promedio de servicio de ambas sillas. Esto es:
1
µ1
+ 1
µ2
Por otro lado, si un cliente llega y la segunda silla est´a ocupada, el tiempo promedio del cliente en el puesto estar´a
dado por la suma del tiempo promedio de servicio de ambas sillas m´as el tiempo de espera promedio. Como los
tiempos distribuyen exponencial, no tiene memoria y por lo tanto el tiempo de espera promedio tambi´en es
1
µ2 . Como
solo esperamos con probabilidad
µ1
µ1+µ2 , el tiempo promedio del cliente en el puesto es:
1
µ1
+ 1
µ2
+
µ1
µ1 + µ2
· 1
µ2
Finalmente utilizando probabilidades totales tenemos que:
W = P0,0
 1
µ1
+ 1
µ2

+ P0,1
 1
µ1
+ 1
µ2
+
µ1
µ1 + µ2
· 1
µ2

Problema 5 (12 puntos)
Clientes llegan a una peluquer´ıa con una tasa media de 5 clientes por hora y los tiempos entre llegadas est´an distribuidos
exponencialmente. En esta peluquer´ıa hay un solo peluquero y 4 sillas para los clientes que llegan cuando el peluquero est´a
ocupado. La ley de prevenci´on de incendios limita el n´umero total de clientes en la peluquer´ıa, en cualquier momento, a
un m´aximo de 5. Los clientes que llegan cuando la peluquer´ıa est´a llena no pueden entrar. El tiempo de servicio distribuye
exponencialmente con una media que depende del n´umero de clientes en la peluquer´ıa (Cuadro 1).
1. (4 puntos) Determine el n´umero promedio de clientes en espera.
2. (4 puntos) Determine el tiempo de espera promedio.
3. (4 puntos) Determine el porcentaje del tiempo que el peluquero est´a inactivo en el largo plazo.
Exprese todos sus resultados como n´umeros.
N´umero de clientes en la peluquer´ıa
1
2
3
4
5
Tiempo medio de servicio por cliente (min.)
9
10
10
13
20
Cuadro 1: Tiempo de servicio en minutos en funci´on de la cantidad de clientes
Soluci´on Problema 5
1. Es un sistema M/M/1/5 donde la tasa de llegada es constante λ = 5 clientes/hora y la tasa de servicio depende del
n´umero de clientes en la peluquer´ıa, donde:
µ1 = 1
9
clientes
minuto = 6,6 clientes
hora
µ2 = 1
10
clientes
minuto = 6 clientes
hora
µ3 = 1
10
clientes
minuto = 6 clientes
hora
6

µ4 = 1
13
clientes
minuto = 4,62 clientes
hora
µ5 = 1
20
clientes
minuto = 3 clientes
hora
As´ı, podemos calcular P0 como:
P0 =
1
1 +
5
X
n=1
λn
Πn
i=1µi
=

1 + λ
µ1
+
λ2
µ1µ2
+
λ3
µ1µ2µ3
+
λ4
µ1µ2µ3µ4
+
λ5
µ1µ2µ3µ4µ5
−1
donde
λ
µ1
= 5
6,6 ≈0,75
λ2
µ1µ2
=
52
6,6 · 6,0 ≈0,625
λ3
µ1µ2µ3
=
53
6,6 · 6,0 · 6,0 = 125
237,6 ≈0,527
λ4
µ1µ2µ3µ4
=
54
6,6 · 6,0 · 6,0 · 4,62 ≈0,565
λ5
µ1µ2µ3µ4µ5
=
55
6,6 · 6,0 · 6,0 · 4,62 · 3 ≈0,941
De este modo,
P0 = (1 + 0,75 + 0,625 + 0,527 + 0,565 + 0,941)−1
= (4,408)−1
= 0,2272
Finalmente, el n´umero promedio de clientes en espera es:
Lq =
5
X
n=1
(n −1)Pn
=
5
X
n=1
(n −1)
λn
Πn
i=1µi
P0
= P0

0 λ
µ1
+ 1 λ2
µ1µ2
+ 2
λ3
µ1µ2µ3
+ 3
λ4
µ1µ2µ3µ4
+ 4
λ5
µ1µ2µ3µ4µ5

= 0,2272(0,625 + 2 · 0,527 + 3 · 0,565 + 4 · 0,941)
= 0,2272 · 7, 138
= 1,621 clientes
2. El tiempo promedio de espera viene dado por:
Wq = Lq
λe
,
donde
λe = λ(1 −P5)
= λ

1 −
λ5
µ1µ2µ3µ4µ5
P0

7

= 5(1 −0,941 · 0,2272)
= 5(1 −2137)
= 3,9315 clientes
hora
Luego,
Wq = 1,621
3,9315 ≈0,412 horas
3. El peluquero est´a inactivo cuando el sistema se encuentra en P0. Luego, el peluquero est´a inactivo aproximadamente
el 22.72 % del tiempo.
Problema 6 (12 puntos)
Considere una variable aleatoria X con una funci´on de densidad de probabilidad triangular (α, β, γ):
f(x) =













2(x −α)
(β −α)(γ −α)
α ≤x ≤γ
2(β −x)
(β −α)(β −γ)
γ ≤x ≤β
0
en otro caso
1. (9 puntos) Desarrolle un algoritmo de Aceptaci´on y Rechazo para generar instancias de X.
2. (3 puntos) Si se usa su algoritmo, ¿cu´al es el valor esperado de la cantidad de iteraciones necesarias para generar una
instancia de X?
Soluci´on Problema 6
1. En primer lugar, se debe determinar una funci´on t(x) que acote superiormente a la funci´on f(x) en todo su dominio.
Una forma de hacer esto es a trav´es una funci´on constante cuyo valor es el m´aximo de f(x) en el dominio respectivo.
Como f(x) est´a compuesta por dos rectas, una creciente y otra decreciente, su valor m´aximo se encuentra en el l´ımite
superior/inferior de cada intervalo respectivamente, es decir, en x = γ. Se define entonces:
t(x) = f(γ) =
2
β −α,
x ∈[α, β]
Como t(x) no es una funci´on de densidad, se debe definir un c que normalice esta funci´on. El valor adecuado de c se
encuentra integrando t(x) en el dominio de f(x), esto es:
c =
Z β
α
t(x) dx
=
2
β −α
Z β
α
1 dx
=
2
β −α · (β −α)
= 2
Luego,
h(x) = t(x)
c
=
1
β −α
8

Como la funci´on de densidad h(x) es
1
β−α para todo x ∈[α, β], h(x) ∼Uniforme(α, β). Finalmente, definimos:
g(x) = f(x)
t(x) =



x−α
γ−α,
α ≤x ≤γ
β−x
β−γ ,
γ ≤x ≤β
Con todos los elementos necesarios ya calculados, el algoritmo de Aceptaci´on y Rechazo es el siguiente:
a) Generar una instancia U1 ∼Uniforme(0, 1).
b) Generar una instancia de Y ∼h(y), utilizando otra instancia U2 ∼Uniforme(0, 1) mediante el m´etodo de la
transformada inversa. Esto es y = (β −α)u2 + α.
c) Si u1 ≤g(y), entonces hacer x = y.
d) Volver al primer paso.
2. Como la probabilidad de aceptar una instancia en cada iteraci´on es 1
c, el n´umero esperado de iteraciones requeridas
para obtener una instancia de X es c = 2.
9

Distribuci´on
PDF (f(x))
CDF (F (x))
Esperanza
Varianza
Poisson(λ)
λxe−λ
x!
P⌊x⌋
k=0
λke−λ
k!
λ
λ
Exponencial(λ)
λe−λx
1 −e−λx
1
λ
1
λ2
Binomial(n, p)
 n
x

px(1 −p)n−x
P⌊x⌋
k=0
 n
k

pk(1 −p)n−k
np
np(1 −p)
Uniforme(a, b)
1
b−a
x−a
b−a
a+b
2
(b−a)2
12
Geom´etrica(p)
(1 −p)x−1p
1 −(1 −p)x
1
p
1−p
p2
Sistema
P0
Pn
L
Lq
M/M/1
1 −λ
µ

λ
µ
n
P0
∀i ∈{1, 2, ...}
λ
µ−λ
λ2
µ(µ−λ)
M/M/1/K
1 −λ
µ
1 −

λ
µ
K+1

λ
µ
n
P0
∀i ∈{1, 2, ..., K}
λ
µ




1 −

λ
µ
K
−K

λ
µ
K
+ K

λ
µ
K+1

1 −λ
µ
 
1 −

λ
µ
K+1




L −λ(1−PK)
µ
M/M/c
"
cP
n=0
 λn
n!µn

+ λc
c!µc ·
λ
cµ
1 −
λ
cµ
#−1
λn
n!µn P0
∀i ∈{1, 2, ..., c}
λn
c!cn−cµn P0
∀i ∈{c + 1, ...}
λ
µ +
( λ
µ)
c
c!(1−λ
cµ)2
λ
µ
L −λ
µ
M/M/c/K


cP
n=0
 λn
n!µn

+ λc
c!µc · λ
cµ ·
1 −

λ
cµ
K−c
1 −
λ
cµ


−1
λn
n!µn P0
∀i ∈{1, 2, ..., c}
λn
c!cn−cµn P0
∀i ∈{c + 1, ..., K}
K
X
n=0
nPn
L −λ(1−PK)
µ

