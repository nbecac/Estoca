Pontificia Universidad Cat´olica de Chile
Escuela de Ingenier´ıa
Departamento de Ingenier´ıa Industrial y de Sistemas
ICS2123 – Modelos Estoc´asticos
Profesores Ver´onica Godoy y Andr´es Navarro
Ayudante Jefe Joaqu´ın Vergara
Primer Semestre 2026
Ayudant´ıa 14:
Sistemas de Espera II
Ayudantes: Emilio Pe˜na (emilio.penasepulveda@uc.cl) & Mart´ın Pe˜na (martinpena@uc.cl)
Problema 1
Considere que al Achoclonados de la Universidad llegan alumnos hambrientos seg´un un Proceso Poisson a
tasa λ > 0 alumnos/minuto. El local cuenta con una ´unica fila y se atiende seg´un l´ogica FIFO. Se cuenta
con cinco trabajadores cuyos tiempos de atenci´on distribuyen exponencial, de par´ametro µ > 0, en minutos.
Cuando hay m > 14 personas en cola, la tasa de llegada disminuye a 0 < αm < λ alumnos/minuto (notar
que depende de la cantidad m personas en cola). Asimismo, una vez que hay n ≥15 personas en el sistema,
los trabajadores aumentan su velocidad de atenci´on, pasando a una tasa γ > 0 alumnos/minuto. Tambi´en,
cuando hay m ≥20 personas en cola, cada una de estas personas en la cola, con probabilidad pn ∈(0, 1)
(estrictamente creciente en n) puede irse, esto seg´un un tiempo que distribuye exponencial con par´ametro
βn > 0, en minutos, donde n representa la cantidad de personas en el sistema. Dos de los trabajadores se
amurran cuando hay n > 30 personas en el sistema, momento en el cual se toman un descanso forzado
hasta que la cantidad de gente vuelva a restaurarse. Por ´ultimo, considere que para no sobreexplotar a los
trabajadores, se establece un m´aximo de 40 personas en el sistema. A partir de lo anterior, responda:
(a) Modele la ocupaci´on de Achoclonados seg´un una Cadena de Markov en Tiempo Continuo, identifi-
cando claramente la variable de estado, el espacio de estados y las tasas de transici´on instant´anea. Se
le recomienda apoyarse de un grafo.
Soluci´on: Consideremos X(t) como la cantidad de personas en el sistema en el instante t ≥0, donde
el conjunto de estados viene dado por X(t) ∈{0, 1, 2, ..., 40}. El diagrama, junto con las tasas de
transici´on instant´aneas vienen dadas por:
1

0
1
2
3
4
5
6
...
14
15
16
...
19
20
21
...
24
25
26
...
30
31
32
...
39
40
λ
λ
λ
λ
µ
2µ
3µ
4µ
λ
5µ
λ
5µ
λ
5µ
λ
5µ
5γ
5γ
λ
λ
5γ
λ
5γ
λ
λ
5γ
α15
5γ
α16
5γ
α18
5γ
α19
5γ + 20β25p25
α20
5γ + 21β26p26
α21
5γ + 22β27p27
α24
5γ + 25β30p30
α25
α28
3γ + 28β31p31
3γ + 29β32p32
α29
3γ + 30β33p33
α35
α36
3γ + 36β39p39
3γ + 37β40p40
(b) Obtenga una expresi´on expl´ıcita (en funci´on de las tasas enunciadas) para la probabilidad de que en
el largo plazo el local est´e vac´ıo.
Soluci´on: Dado que se trata de un modelo de Sistema de Espera, se cumple con que es un Proceso
de Nacimiento y Muerte. Sabemos que:
P0 =
1
1 + P40
n=1
λn−1λn−2 ... λ0
unun−1 ... u1
Se debe explicitar el elemento λn−1λn−2 ... λ0
unun−1 ... u1
seg´un los diferentes casos posibles. Para ello:
λn−1λn−2 ... λ0
unun−1 ... u1
=












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












λn
n!µn
si n ≤5
λn
5!5n−5µn
si 5 < n ≤14
λn
5!5n−5µ14γn−14
si 14 < n ≤20
λ20 Qn
i=21 αi−6
5!5n−5µ14γn−14
si 20 < n ≤24
λ20 Qn
i=21 αi−6
5!519µ14γ10 Qn
i=25(5γ+(i−5)βipi)
si 24 < n ≤30
λ20 Qn
i=21 αi−6
5!519µ14γ10 Q30
i=25(5γ+(i−5)βipi) Qn
i=31(3γ+(i−3)βipi)
si n = 31
λ20 Q31
i=21 αi−6
Qn
i=32 αi−4
5!519µ14γ10 Q30
i=25(5γ+(i−5)βipi) Qn
i=31(3γ+(i−3)βipi)
si 31 < n ≤40
Reemplazando se obtiene P0
(c) Suponga por solo este inciso que el sistema cuenta con capacidad infinita, indique la(s) condicion(es)
para que el sistema no colapse.
Soluci´on: Para que el sistema no colapse, se debe exigir que:
∞
X
n=1
λn−1λn−2 ... λ0
unun−1 ... u1
< ∞
Aunque de forma m´as directa basta con exigir que:
2

3γ + (n −3)βnpn > αn−4
∀n > 31
(d) Indique como obtener las probabilidades en el largo plazo para cada estado. Luego, determine expre-
siones para obtener las m´etricas de desempe˜no L, Lq, W y Wq.
Soluci´on: Explicitado P0, se pueden determinar Pn
∀n = 1, 2, ..., 40 mediante:
Pn = λn−1λn−2 ... λ0
unun−1 ... u1
P0
∀n = 1, 2, ..., 40
Para las m´etricas de desempe˜no, obtengamos primero la cantidad promedio en sistema y en cola:
L =
40
X
n=0
nPn
Lq =
30
X
n=5
(n −5)Pn +
40
X
n=31
(n −3)Pn
Y para los tiempos promedio, primero se calcula λe mediante:
λe =
39
X
n=0
λnPn =
19
X
n=0
λPn +
30
X
n=20
αn−5Pn +
39
X
n=31
αn−3Pn
Y con ello, W y Wq se obtienen utilizando la ecuaci´on de Little:
W = L
λe
=
P40
n=0 nPn
P19
n=0 λPn + P30
n=20 αn−5Pn + P39
n=31 αn−3Pn
Wq = Lq
λe
=
P30
n=5(n −5)Pn + P40
n=31(n −3)Pn
P19
n=0 λPn + P30
n=20 αn−5Pn + P39
n=31 αn−3Pn
3

Problema 2
Consideremos una plaza de peaje donde llegan veh´ıculos de acuerdo a un proceso de Poisson con tasa
λ veh´ıculos/minuto. Cada veh´ıculo tiene, independientemente, una probabilidad p, 0 < p < 1, de ser
autom´ovil y una probabilidad 1 −p de ser un cami´on. La plaza de peajes cuenta con tres cajas, que
llamaremos caja 1, 2 y 3. Las cajas 1 y 2 atienden solamente autom´oviles y la caja 3 atiende solamente
camiones. Si hay al menos una caja disponible del tipo que le corresponde, un veh´ıculo que llega es atendido
de inmediato, si esto no es el caso los autom´oviles que llegan esperan en una cola hasta ser atendidos y
los camiones esperan su turno en otra cola. La atenci´on de autom´oviles y de camiones es por orden de
llegada. El tiempo de atenci´on de cada caja de autom´oviles es exponencial con valor esperado 1
µ minutos y
el tiempo para la caja de camiones es exponencial con valor esperado 1
β . Los tiempos de atenci´on son todos
independientes y suponga que µ > λ y β > λ
a) Defina variables de estado. Indique cual es el conjunto de estados posibles.
Soluci´on: Notamos que por los datos que tenemos de enunciado, podemos tratar el ejercicio como
dos sistemas diferentes, la llegada de autos y la llegada de camiones. La llegada de autos funciona
como un Proceso Poisson con tasa λp y la llegada de camiones funciona como un Proceso Poisson
con tasa λ(1 −p). Por lo tanto:
⋄Llegada de autos →Sistema M/M/2. Con tasa de llegada de λp y tasa de atenci´on de µ.
⋄Llegada de camiones →Sistema M/M/1, con tasa de llegada de λ(1 −p) y tasa de atenci´on de
β.
Se definen estos dos sistemas como:
⋄XA(t) N´umero de autos en el sistema. Donde ΩA = {0, 1, 2, . . .}.
⋄XC(t) N´umero de camiones en el sistema. Donde ΩC = {0, 1, 2, . . .}.
b) Especifique las transiciones posibles y las tasas de transici´on instant´aneas.
Soluci´on: Podemos ver las transiciones en los siguientes grafos:
Autos:
0
1
2
3
...
λ p
λ p
µ
2µ
λ p
2µ
2µ
λ p
Camiones:
0
1
2
3
...
λ(1 −p)
λ(1 −p)
β
β
λ(1 −p)
β
β
λ(1 −p)
c) Obtenga las expresiones explicitas para las probabilidades en el largo plazo.
Soluci´on: Para los autos al ser un sistema M/M/1 se tiene:
P A
n =
( λp
µ P A
0
n = 1
λnpn
2!2n−2µn P A
0
n ≥2
P A
0 = (1 + λp
µ +
∞
X
n=2
λnpn
2!2n−2µn )−1
Para los camiones al ser un sistema M/M/1 se tiene:
P C
n = λn(1 −p)n
µn
P C
0
4

P C
0 = (1 +
∞
X
n=1
λn(1 −p)n
µn
)−1 = 1 −λ(1 −p)
µ
d) Escriba una expresi´on para la fracci´on de tiempo, en el largo plazo, en que hay m´as autom´oviles que
camiones en la plaza de peaje. Asuma conocidas las probabilidades de largo plazo.
Soluci´on: Sea,
⋄NA: n´umero de autos en el largo plazo, donde (NA = n) = P A
n .
⋄NC: n´umero de autos en el largo plazo, donde (NC = n) = P C
n .
Con esto, utilizando probabilidades totales tenemos:
(NA > NC) =
∞
X
i=0
(NA > NC | NC = i) · (NC = i)
=
∞
X
i=0
(NA > i)P C
i
=
∞
X
i=0
∞
X
k=i+1
P A
k P C
i
e) Se propone calcular el tiempo medio de permanencia (en el largo plazo) de un veh´ıculo cualquiera en
la plaza de peajes empleando la expresi´on LA+LC
λ
, donde LA es el n´umero medio de autos en la plaza
y LC es el n´umero medio de camiones en la plaza. Justifique si esta expresi´on es correcta o no.
Soluci´on: Calculando los tiempos medios de espera para ambos sistemas se obtiene:
WA = LA
λA
e
= LA
λp
WC = LC
λC
e
=
LC
λ(1 −p)
Definiendo W como el tiempo medio de cualquier veh´ıculo en el sistema. Se tiene:
W = p · WA + (1 −p) · WC = p · LA
λp + (1 −p) ·
LC
λ(1 −p) = LA
λ + LC
λ
Por lo tanto, la proposici´on es verdadera.
5

Problema 3 (Propuesto)
Clientes llegan a una peluquer´ıa con una tasa media de 5 clientes por hora y los tiempos entre llegadas
est´an distribuidos exponencialmente. En esta peluquer´ıa hay un solo peluquero y 4 sillas para los clientes
que llegan cuando el peluquero est´a ocupado. La ley de prevenci´on de incendios limita el n´umero total
de clientes en la peluquer´ıa, en cualquier momento, a un m´aximo de 5. Los clientes que llegan cuando la
peluquer´ıa est´a llena no pueden entrar. El tiempo de servicio distribuye exponencialmente con una media
que depende del n´umero de clientes en la peluquer´ıa (Cuadro 1).
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
(a) Determine el n´umero promedio de clientes en espera.
Soluci´on: Es un sistema M/M/1/5 donde la tasa de llegada es constante λ = 5 clientes/hora y la
tasa de servicio depende del n´umero de clientes en la peluquer´ıa, donde:
µ1 = 1
9
clientes
minuto = 6.6 clientes
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
µ4 = 1
13
clientes
minuto = 4.62 clientes
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
6.6 ≈0.75
λ2
µ1µ2
=
52
6.6 · 6.0 ≈0.625
λ3
µ1µ2µ3
=
53
6.6 · 6.0 · 6.0 = 125
237.6 ≈0.527
λ4
µ1µ2µ3µ4
=
54
6.6 · 6.0 · 6.0 · 4.62 ≈0.565
λ5
µ1µ2µ3µ4µ5
=
55
6.6 · 6.0 · 6.0 · 4.62 · 3 ≈0.941
De este modo,
P0 = (1 + 0.75 + 0.625 + 0.527 + 0.565 + 0.941)−1
= (4.408)−1
= 0.2272
Finalmente, el n´umero promedio de clientes en espera es:
Lq =
5
X
n=1
(n −1)Pn
6

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
= 0.2272(0.625 + 2 · 0.527 + 3 · 0.565 + 4 · 0.941)
= 0.2272 · 7, 138
= 1.621 clientes
(b) Determine el tiempo de espera promedio.
Soluci´on: El tiempo promedio de espera viene dado por:
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
= 5(1 −0.941 · 0.2272)
= 5(1 −2137)
= 3.9315 clientes
hora
Luego,
Wq = 1.621
3.9315 ≈0.412 horas
(c) Determine el porcentaje del tiempo que el peluquero est´a inactivo en el largo plazo.
Soluci´on: El peluquero est´a inactivo cuando el sistema se encuentra en P0. Luego, el peluquero est´a
inactivo aproximadamente el 22.72 % del tiempo.
(d) Determine el valor esperado de clientes que no ingresan a la peluquer´ıa. Soluci´on: Los clientes que
no ingresan son aquellos que llegan al local cuando se encuentra en su capacidad m´axima. Por ende,
su valor esperado se calcula de la siguiente manera:
E[Personas que no ingresan] = λ · P5 = λ ·
λ5
µ1µ2µ3µ4µ5
P0 = 5 · 0.941 · 0, 2272 = 1.069 personas
7

