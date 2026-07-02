Pontificia Universidad Cat´olica de Chile
Escuela de Ingenier´ıa
Departamento de Ingenier´ıa Industrial y de Sistemas
ICS2123 – Modelos Estoc´asticos
Profesores Ver´onica Godoy y Andr´es Navarro
Ayudante Jefe Joaqu´ın Vergara
Primer Semestre 2026
Ayudant´ıa 4:
Proceso Poisson III
Ayudantes: Emilio Pe˜na (emilio.penasepulveda@uc.cl) & Mart´ın Pe˜na (martinpena@uc.cl)
Resumen
Relaci´on distribuci´on Binomial y Proceso de Poisson
⋄Considere que N(u) | N(t) = n ∼Binomial(n, p = u
t ) cuando 0 < u < t.
⋄Esta idea se puede generalizar para intervalos que no necesariamente comienzan desde el origen (por
la propiedad de incrementos estacionarios).
Por tanto consideremos que N(a) −N(b) | N(c) −N(d) = n ∼Binomial(n, p = a −b
c −d) cuando
d < b < a < c.
Suma y Descomposici´on Proceso de Poisson
⋄Sea N(t), t ≥0 un Proceso de Poisson con tasa λ > 0. Supongamos que cada evento de este proceso
es, de forma independiente, de tipo 1, con probabilidad p ∈(0, 1) y de tipo 2, con probabilidad 1 −p.
Sea Ni(t), t ≥0 el proceso que cuenta los eventos de tipo i = 1, 2. Entonces se puede demostrar
que N1(t), t ≥0 es un Proceso de Poisson con tasa λp y N2(t), t ≥0 es un Proceso de Poisson con
tasa λ(1 −p). Adem´as N1(t), t ≥0 y N2(t), t ≥0 son procesos independientes. Esta idea se puede
generalizar para la descomposici´on en k ∈N≥2 tipo de eventos.
⋄Sea N1(t), N2(t), . . . , Nk(t), t ≥0, procesos Possion independientes con tasas λ1, λ2, . . . , λk > 0 res-
pectivamente, entonces el proceso N(t) = N1(t) + N2(t) + . . . + Nk(t) es un proceso Poisson con tasa
λ = λ1 + λ2 + . . . + λk.
Proceso de Poisson Compuesto
El proceso de conteo {X(t), t ≥0} es un Proceso de Poisson Compuesto si puede representarse como:
X(t) =
N(t)
X
i=1
Yi
Donde N(t) es un Proceso de Poisson con tasa λ > 0 y {Yi, i = 1, 2, 3, . . .} son v.a. iid que adem´as son
independientes de N(t). Se tiene que el proceso:
⋄Posee la propiedad de incrementos independientes.
⋄Posee la propiedad de incrementos estacionarios.
⋄No posee la propiedad de orden.
⋄No existe una f´ormula expl´ıcita para la funci´on de probabilidades de X(t).
⋄Se cumple que E[X(t)] = E[Yi] · E[N(t)]
1

Proceso de Poisson No homog´eneo
El proceso de conteo {N(t), t ≥0} es un Proceso de Poisson no homog´eneo con tasa λ : [0, ∞) →(0, ∞),
t ≥0 si:
⋄N(0) = 0
⋄El proceso tiene incrementos independientes.
⋄P(N(t + h) −N(t) ≥2) = o(h)
⋄P(N(t + h) −N(t) = 1) = λ(t)h + o(h)
Como la tasa de ocurrencia de eventos λ(t) depende del tiempo, no se cumple la propiedad de incrementos
estacionarios. Sea:
m(t) =
Z t
0
λ(s)ds
Si {N(t), t ≥0} es un Proceso de Poisson no homog´eneo con tasa λ : [0, ∞) →(0, ∞), t ≥0, se tiene que:
P(N(t + s) −N(t) = n) = e−(m(t+s)−m(t)) (m(t + s) −m(t))n
n!
,
n ≥0
Notar que:
m(t + s) −m(t) = m(t, t + s) =
Z t+s
t
λ(u)du
2

Problema 1
Luego de una larga espera se llevar´a a cabo el internacionalmente prestigioso festival Poisson-Pallooza el
cual reunir´a durante tres dias a grandes artistas como 31 procesos de conteo y Markovina Carpenter. Todos
los dias el festival opera desde medio d´ıa hasta media noche (12 hrs por d´ıa). Por su parte, los asistentes
del evento llegan en metro y bus seg´un distribuciones exponenciales con tiempos medios de espera
1
λm y
1
λb respectivamente. Considere que los grupos de asistentes son de 30 personas con probabilidad p y 50
personas con probabilidad 1 −p, independiente del medio de transporte.
Considere que debido al alto prestigio del evento, las personas que ingresan al recinto no se retiran hasta
terminado el d´ıa, de forma tal que la cantidad de personas presentes cada d´ıa puede ser modelado seg´un
un proceso de conteo.
(a) Determine la distribuci´on de probabilidad para la cantidad de asistentes en t ∈(12 : 00 −24 : 00).
Soluci´on: (Hacer a detalle)
Definamos los siguientes procesos de conteo:
⋄Nm(t) ∼Poisson(λmt): llegada de metros al festival.
⋄Nb(t) ∼Poisson(λbt): llegada de buses al festival.
⋄N(t) = Nm(t) + Nb(t) ∼Poisson((λm + λb)t): llegada total de veh´ıculos.
⋄S(t) = PN(t)
i=1 Yi: cantidad total de personas.
Sea Yi la variable aleatoria i.i.d. del tama˜no del grupo i:
Yi =
(
30
p
50
1 −p
N(t):
P(S(t) = n) = P(
N(t)
X
i=0
Yi = n)
Utilizando el teorema de probabilidad total sobre el n´umero de veh´ıculos
P(S(t) = n) =
∞
X
k=0
P(
k
X
i=0
Yi = n | N(t) = k)P(N(t) = k)
P(S(t) = n) =
∞
X
k=0
P
 k
X
i=1
Yi = n
!
· ((λm + λb)t)ke−(λm+λb)t
k!
Considerando que ´unicamente pueden entrar 30 o 50 personas en cada momento, podemos definir la
variable aleatoria auxiliar Wi ∼Bernoulli (p) la cual toma valor 1 con probabilidad p y valor 0 con
probabilidad 1 −p. De esta forma es posible reescribir:
Yi = 50 −20Wi
P(
k
X
i=1
Yi = n) = P(
k
X
i=1
50 −20Wi = n) = P(50k −20
k
X
i=1
Wi = n)
= P(
k
X
i=1
Wi = 50k −n
20
)
N´otese que la suma de variables Wi distribuye binomial de par´ametros k, p. Es importante notar que
n debe cumplir que 50k−n
20
sea un entero entre 0 y k, de lo contrario la sumatoria ser´a 0 .
P(S(t) = n) =
∞
X
k=0
P
 k
X
i=1
Wi = 50k −n
20
!
· ((λm + λb)t)ke−(λm+λb)t
k!
P(S(t) = n) =
∞
X
k=0

k
50k−n
20

(p)
50k−n
20
(1 −p)k−50k−n
20
· ((λm + λb)t)ke−(λm+λb)t
k!
3

(b) Calcule la probabilidad de que entre las 13 : 30 y 15 : 00 hrs hayan llegado 800 personas, dado que
entre las 12 : 00 y las 14 : 30 llegaron 1200.
Soluci´on:
t
12:00
13:30
14:30
15:00
1200
800
Se nos pide calcular P(S(13 : 30, 15 : 00) = 800|S(12 : 00, 14 : 30) = 1200). Utilizando el teorema de
Bayes.
P(S(13 : 30, 15 : 00) = 800, S(12 : 00, 14 : 30) = 1200)
P(S(12 : 00, 14 : 30) = 1200)
Dado que hay un intervalo superpuesto en el numerador entre las 13 : 30 y 14 : 30, utilizamos la ley
de probabilidades totales para condicionar los posibles escenarios. Para el numerador:
800
X
k=0
P(S(13 : 30, 15 : 00) = 800, S(14 : 30) = 1200|S(13 : 30, 14 : 30) = k)P(S(13 : 30, 14 : 30) = k)
Considerando las 12 : 00 como el punto inicial, podemos desplazar los intervalos y expresarlos como:
800
X
k=0
P(S(1.5, 3) = 800, S(2.5) = 1200|S(1.5, 2.5) = k)P(S(1.5, 2.5) = k)
800
X
k=0
P(S(2.5, 3) = 800 −k, S(1.5, 2.5) = 1200 −k)P(S(1.5, 2.5) = k)
Ahora que los intervalos no se solapan podemos aplicar la propiedad de incrementos independientes.
800
X
k=0
P(S(2.5, 3) = 800 −k)P(S(1.5, 2.5) = 1200 −k)P(S(1.5, 2.5) = k)
Considerando el denominador la expresi´on queda:
P800
k=0 P(S(2.5, 3) = 800 −k)P(S(1.5, 2.5) = 1200 −k)P(S(1.5, 2.5) = k)
P(S(2.5) = 1200)
Utilizando incremento estacionario:
P800
k=0 P(S(0.5) = 800 −k)P(S(1) = 1200 −k)P(S(1) = k)
P(S(2, 5) = 1200)
Luego para concer el valor final, basta con remplazar lo obtenido en a).
(c) Para poder calcular las porciones de comida, la organizaci´on del festival le pide calcular el valor
esperado de personas que habr´a en la cena (21 : 00 hrs), considerando que a las 18 : 00 hrs hab´ıan
5.000 personas.
Soluci´on: Por la propiedad de incrementos independientes y estacionarios:
E[S(9) | S(6) = 5000] = 5000 + E[S(9) −S(6)] = 5000 + E[S(3)]
En un proceso de Poisson compuesto, E[S(t)] = E[N(t)] · E[Yi].
⋄E[N(3)] = 3(λm + λb)
⋄E[Yi] = 30p + 50(1 −p) = 50 −20p
E[S(9) | S(6) = 5000] = 5000 + 3(λm + λb)(50 −20p)
4

Problema 2
Considera un cine que est´a abierto las 24 horas del d´ıa, todos los d´ıas de la semana. En este cine modelan
la llegada de personas que compran entradas seg´un un proceso Poisson, sin embargo, la tasa varia a lo
largo de la semana. Los jueves se estrena una nueva pel´ıcula y se acerca el fin de semana, por lo que la
tasa aumenta linealmente desde 10 personas por hora a las 00:00 del jueves, hasta 50 personas por hora a
las 00:00 horas del viernes. La tasa se mantiene constante en 50 personas por hora hasta el final del d´ıa
domingo. Como el lunes empieza la semana laboral, la tasa comienza a disminuir linealmente desde las
00:00 horas del lunes hasta el final del d´ıa llegando a 10 personas por hora. Esta tasa de 10 personas por
hora se mantienen constante hasta el jueves cuando empieza nuevamente a subir.
Considere que la llegada de un cliente implica la compra de una sola entrada, no hay restricciones de
capacidad, y el cine tiene en cartelera una sola pel´ıcula (la cual cambia todos los jueves).
a) Escriba matem´aticamente la tasa de llegada del proceso Poisson no-homog´eneo y graf´ıquela para una
semana. Considere el jueves a las 0:00 como el tiempo t = 0.
Soluci´on: El gr´afico de variaci´on de la tasa queda de la siguiente manera:
Espec´ıficamente:
λ(t) =









10 + 5
3t
0 ≤t ≤24
50
24 ≤t ≤96
210 −5
3t
96 ≤t ≤120
10
120 ≤t ≤168
b) Si durante el d´ıa jueves se vendieron 250 entradas para una nueva pel´ıcula, ¿cu´al es la probabilidad
de vender 125 entradas entre las 17:00 horas de ese d´ıa y las 4:00 del viernes?
Soluci´on: Sea N(t), t ≥0 un Proceso Poisson No-Homog´eneo con tasa λ(t).
17
24
28
250
125
250 −i
i
125 −i
Nos preguntan:
P(N(28) −N(17) = 125|N(24) = 250) = P(N(28) −N(17) = 125, N(24) = 250)
P(N(24) = 250)
5

=
125
X
i=0
P(N(17) = 250 −i, N(24) −N(17) = i, N(28) −N(24) = 125 −i)
P(N(24) = 250)
=
125
X
i=0
P(N(17) = 250 −i) · P(N(24) −N(17) = i) · P(N(28) −N(24) = 125 −i)
P(N(24) = 250)
Para t0 < t1 ∈[0, 24] tenemos
m(t1) −m(t0) =
Z t1
t0
(10 + 5
3u)du = 10(t1 −t0) + 5
6(t2
1 −t2
0)
⇒P(N(17) = 250 −i) = m(17)250−i · e−m(17)
(250 −i)!
= (10 · 17 + 5
6 · 172)250−i · e−(10·17+ 5
6 ·172)
(250 −i)!
≈(411)250−i · e−411
(250 −i)!
Continuamos este proceso con las otras 3 probabilidades que hay que sacar. Es importante tomar en
cuenta que la funci´on cambia de forma a medida que aumenta t
m(24) −m(17) =
Z 24
17
λ(t) =
Z 24
17
(10 + 5
3t)dt = 10 · 7 + 5
6(242 −172)
⇒P(N(24) −N(17) = i) = (m(24) −m(17))i · e−(m(24)−m(17))
i!
= (10 · 7 + 5
6 · (242 −172))i · e−(10·7+ 5
6 ·(242−172))
(i)!
≈(309)i · e−309
(i)!
m(28) −m(24) =
Z 28
24
λ(t) =
Z 28
24
50dt = 200
⇒P(N(28) −N(24) = 125 −i) = (m(28) −m(24))125−i · e−(m(28)−m(24))
(125 −i)!
= (200)125−i · e−200
(125 −i)!
m(24) =
Z 24
0
(10 + 5
3t)dt = 720
⇒P(N(24) = 250) = m(24)250 · e−m(24)
(250)!
= (720)250 · e−720
(250)!
Combinando las 4 probabilidades obtenemos la respuesta final:
P(N(28) −N(17) = 125|N(24) = 250) =
125
X
i=0
(411)250−i · e−411
(250 −i)!
· (309)i · e−309
(i)!
·
(200)125−i · e−200
(125 −i)!
·
(250)!
(720)250 · e−720
c) Si las entradas tienen un valor de $5000 ¿Cu´al es el ingreso esperado del cine durante una semana?
Soluci´on: Se pregunta
E[I] = 5000 · E[N(168)]
⇒E[N(168)] =
∞
X
i=0
i · P(N(168) = i) =
∞
X
i=0
i · m(168)i · e−m(168)
i!
Calculamos m(168) y reemplazamos:
m(168) =
Z 24
0
(10 + 5
3t)dt +
Z 96
24
50dt +
Z 120
96
(210 −5
3t)dt +
Z 168
120
10dt
6

= 5520
⇒E[I] = 5000 ·
∞
X
i=0
i · 5520i · e−5520
i!
7

Problema 3 (Propuesto)
Considere una moderna f´abrica de producci´on de veh´ıculos el´ectricos. En dicha f´abrica, los gerentes y
operadores est´an muy preocupados de que no se generen cuellos de botella u otros problemas relacionados
en los movimientos de piezas que dificulten el funcionamiento de la f´abrica y que retrasen las entregas
comprometidas de veh´ıculos, sobre todo en un contexto de importantes cambios en la disponibilidad de
recursos y en los perfiles de demanda, debido a la actual pandemia. Dado esto, lo han contratado a usted
como consultor para analizar algunos flujos dentro de la f´abrica a trav´es del uso de modelos estoc´asticos.
En un cierto sector de la f´abrica llegan cajas con distintas piezas necesarias para armar los veh´ıculos. Cada
caja trae una pieza, pero no se sabe con exactitud qu´e tipo de pieza trae cada una. Usted ha observado
la llegada de muchas cajas a trav´es del tiempo, observando tambi´en cuando ´estas son abiertas, y ha
determinado que una caja cualquiera trae un alternador con probabilidad p, una puerta con probabilidad
q, o un manubrio con probabilidad r, donde p + q + r = 1. Tambi´en ha observado que la llegada de cajas a
este sector de la f´abrica sigue un proceso de poisson con una tasa de λ cajas por hora.
(a) Calcule la probabilidad de que en un rango de tiempo de dos horas lleguen 5 o m´as alternadores y 7
o m´as puertas (es decir, de que conjuntamente ocurran ambos eventos a la vez).
Soluci´on: Sean los siguientes Procesos de conteo
• N(t) ∼Poisson(λ) : llegada de cajas a la f´abrica.
• NA(t) ∼Poisson(λpt) : llegada de cajas que contienen alternadores.
• NP (t) ∼Poisson(λqt) : llegada de cajas que contienen puertas.
• NM(t) ∼Poisson(λrt) : llegada de cajas que contienen manubrios.
• NP +M(t) ∼Poisson(λ(1 −p)t) : llegada de cajas que contienen puertas o manubrios.
Notar que NA(t), NP (t) y NM(t) independientes entre si. As´ı
P (NA(2) ≥5, NP (2) ≥7) =
∞
X
i=5
P (NA(2) = i) ·
∞
X
j=7
P (NP (2) = j) =
∞
X
i=5
(2pλ)ie−2pλ
i!
·
∞
X
j=7
(2qλ)je−2qλ
j!
(b) Calcule la probabilidad de que en un rango de tiempo de dos horas lleguen 20 o m´as cajas y 5 o m´as
alternadores (es decir, de que conjuntamente ocurran ambos eventos a la vez).
Soluci´on: Se solicita:
P(N(2) ≥20, NA(2) ≥5) = P(NP (2) + NM(2) + NA(2) ≥20, NA(2) ≥5)
=
∞
X
i=5
P(NP (2) + NM(2) ≥20 −i) · P(NA(2) = i)
=
20
X
i=5
P(NP (2) + NM(2) ≥20 −i) · P(NA(2) = i) +
∞
X
i=21
P(NA(2) = i)
=
20
X
i=5
∞
X
j=20−i
P(NP (2) + NM(2) = j) · P(NA(2) = i) +
∞
X
i=21
P(NA(2) = i)
=
20
X
i=5
∞
X
j=20−i
(2(1 −p)λ)je−2(1−p)λ
j!
· (2pλ)ie−2pλ
i!
+
∞
X
i=21
(2pλ)ie−2pλ
i!
.
(c) Calcule la probabilidad de que en un rango de tiempo de dos horas lleguen 5 o m´as alternadores dado
que se sabe que en dicho rango de tiempo llegan 7 o m´as puertas.
Soluci´on: Se pide
P (NA(2) ≥5 | NP (2) ≥7) = P (NA(2) ≥5) · P (NP (2) ≥7)
P (NP (2) ≥7)
=
∞
X
i=5
(2pλ)ie−2pλ
i!
8

(d) Calcule la probabilidad de que en un rango de tiempo de dos horas lleguen 20 o m´as cajas dado que
se sabe que en dicho rango de tiempo llegan 5 o m´as alternadores.
Soluci´on: Se pide
P(N(2) ≥20 | NA(2) ≥5) = P(NP (2) + NM(2) + NA(2) ≥20 | NA(2) ≥5)
= P(NP (2) + NM(2) + NA(2) ≥20, NA(2) ≥5)
P(NA(2) ≥5)
=
∞
P
i=5
P(NP (2) + NM(2) ≥20 −i) · P(NA(2) = i)
∞
P
i=5
P(NA(2) = i)
=
20
P
i=5
∞
P
j=20−i
(2(1−p)λ)je−2(1−p)λ
j!
(2pλ)ie−2pλ
i!
+
∞
P
i=21
(2pλ)ie−2pλ
i!
∞
P
i=5
(2pλ)ie−2pλ
i!
.
(e) Calcule la probabilidad de que en un rango de tiempo de dos horas lleguen 5 o m´as alternadores dado
que se sabe que en dicho rango de tiempo llegan 20 o m´as cajas.
Soluci´on:
P(NA(2) ≥5 | N(2) ≥20) = P(NA(2) ≥5 | NP (2) + NM(2) + NA(2) ≥20)
= P(NA(2) ≥5, NA(2) + NP (2) + NM(2) ≥20)
P(N(2) ≥20)
=
∞
P
i=5
P(NP (2) + NM(2) ≥20 −i) · P(NA(2) = i)
∞
P
k=20
P(N(2) = k)
=
20
P
i=5
∞
P
j=20−i
 2(1−p)λ
j
e−2(1−p)λ
j!
(2pλ)ie−2pλ
i!
+
∞
P
i=21
(2pλ)ie−2pλ
i!
∞
P
k=20
(2λ)ke−2λ
k!
.
En otro sector de la f´abrica se sabe que llegan ruedas seg´un un Proceso de Poisson con una tasa de α
ruedas por hora y que llegan espejos seg´un un Proceso de Poisson con una tasa de β espejos por hora. Por
otra parte, se sabe que con probabilidad 0.1 una rueda cualquiera es defectuosa, y que con probabilidad
0.3 un espejo cualquiera es defectuoso. En adelante, llamaremos piezas defectuosas a ruedas defectuosas y
a espejos defectuosos.
(g) Calcule la probabilidad de que en un rango de tiempo de 10 horas lleguen 100 o m´as piezas defectuosas.
Soluci´on: Sean los siguientes Procesos de Conteo:
• NR(t) ∼Poisson(αt) : llegada de una rueda a la f´abrica.
• NRB(t) ∼Poisson(0.9αt) : llegada de una rueda buena a la f´abrica.
• NRD(t) ∼Poisson(0.1αt) : llegada de una rueda defectuosa a la f´abrica.
• NE(t) ∼Poisson(βt) : llegada de un espejo a la f´abrica.
• NEB(t) ∼Poisson(0.7βt) : llegada de un espejo bueno a la f´abrica.
• NED(t) ∼Poisson(0.3βt) : llegada de un espejo defectuoso a la f´abrica.
• ND(t) ∼Poisson((0.1α + 0.3β)t) : llegada de un artefacto defectuoso a la f´abrica.
As´ı se solicita
P (NRD(10) + NED(10) ≥100) = P (ND(10) ≥100) =
∞
X
i=100
(α + 3β)ie−α−3β
i!
9

(h) Calcule la probabilidad de que entre t = 0 y t = 10 horas lleguen lleguen 100 o m´as piezas defectuosas
dado que se sabe que entre t = 0 y t = 3 horas llegan 20 o m´as ruedas (de cualquier tipo, es decir,
defectuosas o no defectuosas).
Soluci´on: Se pide
P(ND(10) ≥100 | NR(3) ≥20) = P(ND(10) ≥100, NR(3) ≥20)
P(NR(3) ≥20)
El numerador corresponde a
P(ND(10) ≥100 , NR(3) ≥20) =
∞
X
j=0
∞
X
i=0
P(ND(10) ≥100, NRD(3) + NRB(3) ≥20 | NRD(3) = i, NED(3) = j) · P(NRD(3) = i, NED(3) = j)
=
∞
X
j=0
∞
X
i=0
P

NRD(10) + NED(10) −NRD(3) −NED(3) ≥100 −i −j, NRB(3) ≥20 −i

P(NRD(3) = i, NED(3) = j)
=
∞
X
j=0
∞
X
i=0
P(NRD(7) + NED(7) ≥100 −i −j) · P(NRB(3) ≥20 −i) · P(NRD(3) = i) · P(NED(3) = j)
=
∞
X
j=0
∞
X
i=0


∞
X
k=100−i−j
P(ND(7) = k)


 
∞
X
n=20−i
P(NRB(3) = n)
!
P(NRD(3) = i) P(NED(3) = j) .
Luego, la probabilidad condicional buscada es equivalente a
P(ND(10) ≥100 | NR(3) ≥20) =
∞
X
j=0
∞
X
i=0
"

∞
X
k=100−i−j
P(ND(7) = k)


 
∞
X
n=20−i
P(NRB(3) = n)
!
P(NRD(3) = i) P(NED(3) = j)
#
∞
X
m=20
P(NR(3) = m)
.
=
∞
X
j=0
∞
X
i=0
"

∞
X
k=100−i−j
e−(0.1α+0.3β)7  (0.1α + 0.3β)7
k
k!


 
∞
X
n=20−i
e−0.9α·3 (0.9α · 3)n
n!
!
e−0.1α·3 (0.1α · 3)i
i!
e−0.3β·3 (0.3β · 3)j
j!
#
∞
X
m=20
e−α·3 (α · 3)m
m!
Notar que, cuando i ≥20, la sumatoria en n resultar´a 1, igual que la sumatoria en k cuando i+j ≥100.
10

