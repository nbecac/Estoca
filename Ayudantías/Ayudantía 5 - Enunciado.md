Pontificia Universidad Cat´olica de Chile
Escuela de Ingenier´ıa
Departamento de Ingenier´ıa Industrial y de Sistemas
ICS2123 – Modelos Estoc´asticos
Profesores Ver´onica Godoy y Andr´es Navarro
Ayudante Jefe Joaqu´ın Vergara
Primer Semestre 2026
Ayudant´ıa 5:
Proceso Poisson IV
Ayudantes: Emilio Pe˜na (emilio.penasepulveda@uc.cl) & Mart´ın Pe˜na (martinpena@uc.cl)
Resumen
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
1

Problema 1
Usted es el administrador de un centro de eventos, lugar donde se llevar´a a cabo un evento desde las 13:00
hasta las 23:00. Debido a la seguridad y al control de ingresos, puede determinar que las personas que
llegan al lugar del evento lo hacen en grupos y siguiendo un Proceso Poisson. Debido a que hay momen-
tos del d´ıa con mayor llegada de p´ublico, se puede estimar que la tasa de llegada de los grupos corresponde a:
λ(t) =
(
( t
5)2
si 0 ≤t < 5
sen( πt
10)
si t ≥5
con t en horas.
(a) Calcule la probabilidad de que entre la hora 5 y 9 lleguen 9 grupos, si es que usted ya conoce que
entre la hora 3 y la hora 8 llegaron exactamente 6 grupos.
(b) Ahora, usted tiene informaci´on de que cada grupo esta conformado por una cantidad de personas
aleatoria que se puede modelar como una distribuci´on Binomial(n, p) con n natural y p ∈[0, 1]. Se
le pide determinar la probabilidad que entre las 17:00 y las 20:00 lleguen m´as de 50 personas. Luego
calcule la cantidad esperada de gente que llegar´a entre las 17:00 y las 20:00.
(c) (Propuesto) Ahora, se le informa que hay 2 tipos de grupos que pueden llegar al lugar del evento,
con probabilidad p ∈(0, 1) llegan grupos de metaleros, y con probabilidad 1 −p llegan grupos de
reguetoneros.Se conoce que la cantidad de personas en cada grupo de metaleros distribuye seg´un una
variable aleatoria Binomial(4, 0.7) y la cantidad de personas en cada grupo de reguetoneros distri-
buye seg´un Poisson(6). Considerando que la cantidad de personas en cada grupo es independiente, e
independiente al proceso de llegada de grupos, se le pide determinar la distribuci´on del n´umero de
personas totales que llega entre la hora 3 y la hora 7.
2

Problema 2
Parte 1
Considere un proceso Poisson {N(t) : t ≥0} de tasa λ. Considere tambi´en un tiempo t > 0. Sea Z =
t −SN(t), donde S0 = 0. ¿Cu´al es el valor esperado de Z?
Parte 2
Suponga que la distribuci´on de inter-eventos para un proceso de renovaci´on es una distribuci´on Poisson
con media µ. Es decir, suponga:
P[Tn = k] = e−µ µk
k!
(a) Encuentre la distribuci´on de Sn.
(b) Calcule P[N(t) = n].
Parte 3 (Propuesto)
(a) Considere un proceso de renovaci´on {N(t), t ≥0} cuyos tiempos inter-eventos (Ti)i∈N siguen una
distribuci´on Geom´etrica de par´ametro p, es decir, para todo i ∈N
P(Ti = k) =
(
(1 −p)k−1p
si k ∈N
0
e.o.c.
Muestre que para todo n ∈N, Sn, el instante de ocurrencia del n-´esimo evento, distribuye Binomial
Negativa de par´ametros n, p.
(b) Muestre que para n ∈N y t ≥0 se tiene
P(N(t) = n) =
⌊t⌋
X
k=n
P(Tn+1 > t −k)P(Sn = k)
y ´uselo para encontrar la distribuci´on de N(t).
3

