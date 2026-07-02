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
Soluci´on: Sea {N(t), λ(t)}: Proceso Poisson No Homog´eneo que cuenta llegada de grupos al evento,
hasta la hora t.
La probabilidad pedida corresponde a: P(N(9) −N(5) = 9|N(8) −N(3) = 6), la cual se desarrolla de
la siguiente manera:
= P(N(9) −N(5) = 9|N(8) −N(3) = 6) = P(N(9) −N(5) = 9, N(8) −N(3) = 6)
P(N(8) −N(3) = 6)
=
6
X
k=0
P(N(9) −N(5) = 9, N(8) −N(3) = 6 | N(8) −N(5) = k) · P(N(8) −N(5) = k)
P(N(8) −N(3) = 6)
=
6
X
k=0
P(N(9) −N(8) = 9 −k, N(5) −N(3) = 6 −k) · P(N(8) −N(5) = k)
P(N(8) −N(3) = 6)
=
6
X
k=0
P(N(9) −N(8) = 9 −k) · P(N(5) −N(3) = 6 −k) · P(N(8) −N(5) = k)
P(N(8) −N(3) = 6)
Para calcular cada probabilidad se necesita de m(t) =
R t
0 λ(s)ds la cual se calcula:
∀t ∈[0, 5[: m(t) =
Z t
0
(s
5)2ds = 5
3( t
5)3 = t3
75
∀t ∈[5, 12] : m(t) =
Z 5
0
(s
5)2ds +
Z t
5
sen(πs
10 )ds = 125
75 −10
π cos(πt
10) + 10
π cos(5π
10 ) = 5
3 −10
π cos(πt
10)
En conclusi´on, el resultado final es:
=
6
X
k=0
(m(9)−m(8))9−k·e−(m(9)−m(8)
(9−k)!
· (m(5)−m(3))6−k·e−(m(5)−m(3)
(6−k)!
· (m(8)−m(5))k·e−(m(8)−m(5)
(k)!
(m(8)−m(3))6·e−(m(8)−m(3)
(6)!
(b) Ahora, usted tiene informaci´on de que cada grupo esta conformado por una cantidad de personas
aleatoria que se puede modelar como una distribuci´on Binomial(n, p) con n natural y p ∈[0, 1]. Se
le pide determinar la probabilidad que entre las 17:00 y las 20:00 lleguen m´as de 50 personas. Luego
calcule la cantidad esperada de gente que llegar´a entre las 17:00 y las 20:00.
Soluci´on: Se define
(i)
Yi ∼Binomial(n, p): Cantidad de personas en el grupo i
(ii)
Z(t) = PN(t)
i=1 Yi: Cantidad de personas totales que llegan hasta la hora t
Se pide P(Z(7) −Z(4) ≥50). El desarrollo consiste en:
2

=
∞
X
k=50
P(Z(7) −Z(4) = k) =
∞
X
k=50
P(
N(7)
X
i=1
Yi −
N(4)
X
i=1
Yi = k) =
∞
X
k=50
P(
N(7)
X
i=N(4)+1
Yi = k)
=
∞
X
k=50
P(
N(7)−N(4)
X
i=1
Yi = k) =
∞
X
j=0
∞
X
k=50
P(
N(7)−N(4)
X
i=1
Yi = k | N(7) −N(4) = j) · P(N(7) −N(4) = j)
=
∞
X
j=0
∞
X
k=50
P(
j
X
i=1
Yi = k) · P(N(7) −N(4) = j)
Es conocido que la suma de j distribuciones iid Binomial(n, p) corresponde a una distribuci´on
Binomial(nj, p), por ende, el resultado de la expresi´on anterior es:
P(Z(7) −Z(4) ≥50) =
∞
X
j=0
∞
X
k=50
nj
k

pk(1 −p)nj−k · (m(7) −m(4))j · e−(m(7)−m(4))
j!
Ahora para el calculo de la cantidad esperada, se nos pide E[Z(7) −Z(4)]. El desarrollo consiste en:
E[Z(7) −Z(4)] = E[Y ] · E[N(7) −N(4)] = (np) · (m(7) −m(4))
(c) (Propuesto) Ahora, se le informa que hay 2 tipos de grupos que pueden llegar al lugar del evento,
con probabilidad p ∈(0, 1) llegan grupos de metaleros, y con probabilidad 1 −p llegan grupos de
reguetoneros.Se conoce que la cantidad de personas en cada grupo de metaleros distribuye seg´un una
variable aleatoria Binomial(4, 0.7) y la cantidad de personas en cada grupo de reguetoneros distri-
buye seg´un Poisson(6). Considerando que la cantidad de personas en cada grupo es independiente, e
independiente al proceso de llegada de grupos, se le pide determinar la distribuci´on del n´umero de
personas totales que llega entre la hora 3 y la hora 7.
Soluci´on: Se definen:
⋄NM(t): Proceso poisson no homog´eneo que cuenta grupos de metaleros con λM(t) = p · λ(t).
⋄NR(t): Proceso Poisson no homog´eneo que cuenta grupos de reguetoneros con λR(t) = (1 −p) ·
λ(t).
⋄Mi ∼Binomial(4, 0.7): Cantidad de personas en grupo i de metaleros.
⋄Ri ∼Poisson(6): Cantidad de personas en grupo i de reguetoneros.
⋄Z(t) = PNM(t)
i=1
Mi + PNR(t)
i=1
Ri: Cantidad de personas totales que llegan hasta la hora t.
Se nos pide calcular la distribuci´on de Z(7) −Z(3), el procedimiento para calcularla es:
P(Z(7) −Z(3) = n) = P(
NM(7)
X
i=1
Mi +
NR(7)
X
i=1
Ri −
NM(3)
X
i=1
Mi −
NR(3)
X
i=1
Ri = n) = P(
NM(7)
X
i=NM(3)+1
Mi +
NR(7)
X
i=NR(3)+1
Ri = n)
= P(
NM(7)−NM(3)
X
i=1
Mi +
NR(7)−NR(3)
X
i=1
Ri = n)
=
∞
X
k=0
P(
NM(7)−NM(3)
X
i=1
Mi +
NR(7)−NR(3)
X
i=1
Ri = n | NM(7) −NM(3) = k) · P(NM(7) −NM(3) = k)
=
∞
X
k=0
P(
k
X
i=1
Mi +
NR(7)−NR(3)
X
i=1
Ri = n) · P(NM(7) −NM(3) = k)
=
∞
X
k=0
∞
X
j=0
P(
k
X
i=1
Mi +
NR(7)−NR(3)
X
i=1
Ri = n | NR(7) −NR(3) = j) · P(NM(7) −NM(3) = k) · P(NR(7) −NR(3) = j)
=
∞
X
k=0
∞
X
j=0
P(
k
X
i=1
Mi +
j
X
i=1
Ri = n) · P(NM(7) −NM(3) = k) · P(NR(7) −NR(3) = j)
=
∞
X
k=0
∞
X
j=0
n
X
l=0
P(
k
X
i=1
Mi +
j
X
i=1
Ri = n |
k
X
i=0
Mi = l) · P(NM(7) −NM(3) = k) · P(NR(7) −NR(3) = j) · P(
k
X
i=0
Mi = l)
=
∞
X
k=0
∞
X
j=0
n
X
l=0
P(
j
X
i=1
Ri = n −l) · P(NM(7) −NM(3) = k) · P(NR(7) −NR(3) = j) · P(
k
X
i=0
Mi = l)
Es conocido que la suma de j distribuciones independientes Poisson(6) iid corresponde a una dis-
tribuci´on Poisson(6j), por otro lado, la suma de k distribuciones independientes Binomial(4, 0.7)
corresponde a una distribuci´on Binomial(4k, 0.7), por ende, el resultado de la expresi´on anterior es:
3

P(Z(7) −Z(3) = n) =
∞
X
k=0
∞
X
j=0
n
X
l=0
(6j)n−le−6j
(n −l)!
·
4k
l

(0.7)l(0.3)4k−l · (p(m(7) −m(3)))ke−p(m(7)−m(3))
k!
· ((1 −p)(m(7) −m(3)))je−(1−p)(m(7)−m(3))
j!
4

Problema 2
Parte 1
Considere un proceso Poisson {N(t) : t ≥0} de tasa λ. Considere tambi´en un tiempo t > 0. Sea Z =
t −SN(t), donde S0 = 0. ¿Cu´al es el valor esperado de Z?
Soluci´on: Sabemos por la paradoja de la inspecci´on que:
P(Z(t) ≤x) =
(
1 −e−λx
, x < t
e−λt
, x ≥t
El valor esperado de Z es:
E[Z] =
Z t
0
xfZ(x)dx +
Z ∞
t
tfZ(x)dx
=
Z t
0
xλe−λxdx + t
Z ∞
t
λe−λxdx
= 1
λ −e−λt
λ
= 1 −e−λt
λ
Parte 2
Suponga que la distribuci´on de inter-eventos para un proceso de renovaci´on es una distribuci´on Poisson
con media µ. Es decir, suponga:
P[Tn = k] = e−µ µk
k!
(a) Encuentre la distribuci´on de Sn.
Soluci´on: En primer lugar recordemos que Sn representa el tiempo de llegada del evento n. Es decir,
Sn =
n
X
i=1
Ti
Ahora, a simple vista al ser suma de variables aleatorias i.id Poisson, se puede aplicar el teorema demos-
trado en clases para suma de va Poisson, as´ı Sn distribuye Poisson(µn). A continuaci´on se demuestra de
una manera intuitiva.
Sea T1, T2, ..., Tn variables aleatorias independientes e id´enticamente distribuidas (iid) con distribuci´on
Poisson(µ). Consideremos la variable aleatoria Sn = T1 + T2 + ... + Tn, que denota la suma de las n
variables aleatorias. Entonces:
P(Sn = k) = P(T1 = k1, T2 = k2, ..., Tn = kn)
= P(T1 = k1) · P(T2 = k2) · ... · P(Tn = kn)
= e−µ(µ)k1
k1!
· e−µ(µ)k2
k2!
· ... · e−µ(µ)kn
kn!
= e−nµ(nµ)k
k!
Lo cual distribuye Poisson(nµ)
(b) Calcule P[N(t) = n].
Soluci´on:
5

Notemos que Sn ∼Poisson(nµ). Ahora, al tratarse de un proceso de renovaci´on tendremos que:
P[N(t) = n] = P(Sn ≤t) −P(Sn+1 ≤t)
= F n(t) −F n+1(t)
=
⌊t⌋
X
k=0
e−nµ(nµ)k
k!
−
⌊t⌋
X
k=0
e−(n+1)µ((n + 1)µ)k
k!
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
Soluci´on:
Sn ∼BinNeg(n, p). Esto lo vemos de la siguiente manera:
Opci´on 1: Vemos que para n ∈N y k ∈N0 se tiene
P(Sn = k) =
X
j1,...,jn∈N
P(Sn = k|T1 = j1, . . . , Tn = jn)
n
Y
i=1
P(Ti = ji)
(1)
=
X
j1,...,jn∈N
P(T1 + . . . + Tn = k|T1 = j1, . . . , Tn = jn)
n
Y
i=1
P(Ti = ji)
(2)
=
X
j1,...,jn∈N
P(j1 + . . . + jn = k)
n
Y
i=1
P(Ti = ji)
(3)
=
X
j∈J k
n
1 ·
n
Y
i=1
P(Ti = ji)
(4)
=
X
j∈J k
n
1 ·
n
Y
i=1
p · (1 −p)ji−1
(5)
=
X
j∈J k
n
pn · (1 −p)
n
P
i=1
(ji−1)
(6)
=
X
j∈J k
n
pn · (1 −p)j1+...+jn−n
(7)
=

X
j∈J k
n
1

pn · (1 −p)k−n
(8)
= |J k
n | · pn · (1 −p)k−n
(9)
=
k −1
n −1

· pn · (1 −p)k−n
(10)
Donde
• (1) Es probabilidades totales condicionando en {T1, . . . , Tn}.
• (2) Es la definici´on de Sn como suma de los tiempos inter-eventos.
• (3) Es el reemplazo de la condici´on.
6

• (4) La probabilidad anterior se eval´ua en un evento determin´ıstico y por lo tanto vale 1 si se
cumple el evento (j ∈J k
n ) y 0 en otro caso.
• (5) Ti ∼Geom(p).
• (6) y (7) Se calcula el producto de las n probabilidades.
• (8) j1 + . . . + jn = k y se separa lo que no depende de j y lo que s´ı.
• (9) La sumatoria es simplemente contar los elementos que hay en el conjunto J k
n .
Opci´on 2: Sabemos que S1 = T1 ∼Geom(p), es decir
P(S1 = x) = p(1 −p)x−1 =
x −1
1 −1

p(1 −p)x−1
. Adem´as para x ∈N
P(S2 = x) = P(T1 + T2 = x)
=
x−1
X
k=1
P(T2 = x −k) · P(T1 = k)
=
x−1
X
k=1
(1 −p)x−k−1 · p · (1 −p)k−1 · p
= (x −1) · p2 · (1 −p)x−2
=
x −1
2 −1

· p2 · (1 −p)x−2
Supongamos que para todo k ≤n se tiene que Sk ∼BinNeg(k, p), i.e. para x ∈N se tiene
P(Sk = x) =
x −1
x −k

pk · (1 −p)x−k
Mostremos que Sn+1 ∼BinNeg(n + 1, p).
P(Sn+1 = x) = P(Sn + Tn+1 = x)
=
∞
X
j=1
P(Tn+1 = x −Sn | Sn = j) · P(Sn = j)
=
x−1
X
j=n
P(Tn+1 = x −j) · P(Sn = j)
=
x−1
X
j=n
p(1 −p)x−j−1 ·
j −1
j −n

pn(1 −p)j−n
=


x−1
X
j=n
j −1
j −n

pn+1 · (1 −p)x−(n+1)
=

x −1
x −(n + 1)

pn+1 · (1 −p)x−(n+1)
Es decir Sn+1 ∼BinNeg(n + 1, p) con lo que se demuestra lo pedido.
(b) Muestre que para n ∈N y t ≥0 se tiene
P(N(t) = n) =
⌊t⌋
X
k=n
P(Tn+1 > t −k)P(Sn = k)
y ´uselo para encontrar la distribuci´on de N(t).
7

Soluci´on:
Para n ∈N y t ≥0 se tiene
P(N(t) = n) = P(Sn ≤t < Sn+1)
= P(Sn ≤t < Sn + Tn+1)
=
∞
X
k=0
P(Sn ≤t < Sn + Tn+1 | Sn = k) · P(Sn = k)
=
∞
X
k=0
P(k ≤t < k + Tn+1) · P(Sn = k)
=
∞
X
k=0
P(k ≤t , t −k < Tn+1) · P(Sn = k)
=
⌊t⌋
X
k=n
P(t −k < Tn+1) · P(Sn = k)
=
⌊t⌋
X
k=n
P(t −k < Tn+1) · P(Sn = k)
Para encontrar la distribuci´on de N(t) debemos reemplazar los valores sabiendo que
• P(Tn+1 > t −k) = 1 −P(Tn+1 ≤t −k) = 1 −(1 −(1 −p)⌊t⌋−k) = (1 −p)⌊t⌋−k
• P(Sn = k) =
 k−1
k−n

pn(1 −p)k−n
Entonces
P(N(t) = n) =
⌊t⌋
X
k=n
P(t −k < Tn+1) · P(Sn = k)
=
⌊t⌋
X
k=n
(1 −p)⌊t⌋−k ·
k −1
k −n

pn(1 −p)k−n
=


⌊t⌋
X
k=n
k −1
k −n

pn(1 −p)⌊t⌋−n
=
⌊t⌋
n

pn(1 −p)⌊t⌋−n
Por lo que N(t) ∼Bin(⌊t⌋, p).
8

