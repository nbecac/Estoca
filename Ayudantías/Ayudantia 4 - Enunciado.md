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
(b) Calcule la probabilidad de que entre las 13 : 30 y 15 : 00 hrs hayan llegado 800 personas, dado que
entre las 12 : 00 y las 14 : 30 llegaron 1200.
(c) Para poder calcular las porciones de comida, la organizaci´on del festival le pide calcular el valor
esperado de personas que habr´a en la cena (21 : 00 hrs), considerando que a las 18 : 00 hrs hab´ıan
5.000 personas.
3

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
b) Si durante el d´ıa jueves se vendieron 250 entradas para una nueva pel´ıcula, ¿cu´al es la probabilidad
de vender 125 entradas entre las 17:00 horas de ese d´ıa y las 4:00 del viernes?
c) Si las entradas tienen un valor de $5000 ¿Cu´al es el ingreso esperado del cine durante una semana?
4

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
(b) Calcule la probabilidad de que en un rango de tiempo de dos horas lleguen 20 o m´as cajas y 5 o m´as
alternadores (es decir, de que conjuntamente ocurran ambos eventos a la vez).
(c) Calcule la probabilidad de que en un rango de tiempo de dos horas lleguen 5 o m´as alternadores dado
que se sabe que en dicho rango de tiempo llegan 7 o m´as puertas.
(d) Calcule la probabilidad de que en un rango de tiempo de dos horas lleguen 20 o m´as cajas dado que
se sabe que en dicho rango de tiempo llegan 5 o m´as alternadores.
(e) Calcule la probabilidad de que en un rango de tiempo de dos horas lleguen 5 o m´as alternadores dado
que se sabe que en dicho rango de tiempo llegan 20 o m´as cajas.
En otro sector de la f´abrica se sabe que llegan ruedas seg´un un Proceso de Poisson con una tasa de α
ruedas por hora y que llegan espejos seg´un un Proceso de Poisson con una tasa de β espejos por hora. Por
otra parte, se sabe que con probabilidad 0.1 una rueda cualquiera es defectuosa, y que con probabilidad
0.3 un espejo cualquiera es defectuoso. En adelante, llamaremos piezas defectuosas a ruedas defectuosas y
a espejos defectuosos.
(g) Calcule la probabilidad de que en un rango de tiempo de 10 horas lleguen 100 o m´as piezas defectuosas.
(h) Calcule la probabilidad de que entre t = 0 y t = 10 horas lleguen lleguen 100 o m´as piezas defectuosas
dado que se sabe que entre t = 0 y t = 3 horas llegan 20 o m´as ruedas (de cualquier tipo, es decir,
defectuosas o no defectuosas).
5

