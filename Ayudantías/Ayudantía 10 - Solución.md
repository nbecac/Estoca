Pontificia Universidad Cat´olica de Chile
Escuela de Ingenier´ıa
Departamento de Ingenier´ıa Industrial y de Sistemas
ICS2123 – Modelos Estoc´asticos
Profesores Ver´onica Godoy y Andr´es Navarro
Ayudante Jefe Joaqu´ın Vergara
Primer Semestre 2026
Ayudant´ıa 10:
CMTC
Ayudantes: Emilio Pe˜na (emilio.penasepulveda@uc.cl) & Mart´ın Pe˜na (martinpena@uc.cl)
Resumen
CMTC
Una CMTC es un proceso estoc´astico {X(t) ∈S, t ≥0}, con espacio de estados S, que cumple las siguientes
propiedades:
⋄Cada vez que el sistema entra al estado i ∈S, permanece en ese estado un tiempo que distribuye
exponencial de par´ametro νi > 0.
⋄Cada vez que el sistema est´a en el estado i ∈S, la probabilidad de que haga una transici´on al estado
j ∈S es Pij ∈[0, 1].
⋄Las probabilidades Pij deben satisfacer:
Pii = 0 ,
X
j∈S
Pij = 1 ∀i ∈S
Sea Ti el tiempo de permanencia del proceso en el estado i ∈S. La propiedad Markoviana hace que el
proceso tenga p´erdida de memoria, por lo que
Ti ∼Exponencial (νi) , ∀i ∈S
N´otese que esta definici´on es equivalente a pedir que cumpla con la Propiedad Markoviana y Estacionaria.
Tasas de transici´on y permanencia
Se denomina tasa de transici´on instant´anea, qij > 0, a la tasa a la cual el proceso realiza una transici´on del
estado i ∈S al estado j ∈S, estando en i. Esta tasa est´a dada por:
qij = νi · Pij
Donde νi > 0 corresponde a la tasa a la cual el proceso realiza una transici´on cuando se encuentra en el
estado i ∈S (tasa de permanencia):
νi =
X
j∈S\{i}
qij
Y Pij ∈[0, 1] corresponde a la probabilidad que, estando en el estado i ∈S, la pr´oxima transici´on sea al
estado j ∈S \ {i}:
Pij = qij
νi
=
qij
P
j∈S\{i}
qij
1

Ecuaci´on de Equilibrio en el Largo Plazo
Se define
Pj = l´ım
t→∞Pij(t)
Si Pj existe y es independiente de i para todo j, se dice que es {Pj, j ∈S} es una distribuci´on de probabilidad
l´ımite, y se interpreta como la probabilidad de que el sistema se encuentre en el estado j, o como la
proporci´on del tiempo que el sistema pasa en ese estado en el largo plazo.
Para una CMTC se cumple que la tasa de salida en el largo plazo es igual a la suma de las tasas de llegada
en el largo plazo a ese mismo estado. Es decir:
νj · Pj =
X
k∈S\j
qkj · Pk
con:
X
i∈S
Pi = 1
La distribuci´on de probabilidades l´ımite corresponde a la soluci´on del sistema de Ecuaciones de Equilibrio
de Largo Plazo.
2

Problema 1 (I2-2025-2)
Suponga que usted desea monitorear en tiempo real la divulgaci´on de una fake news en una poblaci´on de
n ∈N individuos. Cada individuo puede ser ignorante (no conoce la fake news), mal informado (conoce la
fake news) o bien informado (conoce la fake news pero sabe que es falsa). Los individuos reciben noticias
de forma independiente seg´un un Proceso de Poisson con par´ametro λ > 0 (noticias por d´ıa). Cuando
un individuo recibe una noticia, con probabilidad p ∈(0, 1) es la fake news que usted desea monitorear,
con probabilidad r ∈(0, 1) es una noticia que desmiente la fake news que usted desea monitorear y con
probabilidad 1 −p −r la noticia no est´a relacionada con la fake news. Si un individuo recibe una noticia
que desmiente la fake news pasa a ser un individuo bien informado, independientemente de si conoc´ıa o no
la fake news antes.
(a) Modele la situaci´on descrita como una Cadena de Markov en Tiempo Continuo (CMTC) que permita
determinar la cantidad de individuos ignorantes, mal informados y bien informados en un instante
t ≥0. Especifique el conjunto de estados y las tasas de transici´on instant´anea entre cada estado.
Soluci´on: Para modelar la cantidad de individuos ignorantes, mal informados y bien informados en
un instante t definimos las variable aleatorias:
⋄X(t) ∈N0: Cantidad de individuos ignorantes en el instante t.
⋄Y (t) ∈N0: Cantidad de individuos mal informados en el instante t.
⋄Z(t) ∈N0: Cantidad de individuos bien informados el instante t.
Luego, los estados de la CMTC corresponden a todas las posibles combinaciones del proceso (X(t), Y (t), Z(t))
tales que
S := {(x, y, z) ∈N3
0 : x + y + z = n}.
Las tasas de transici´on entre estados est´an dadas por
q(i,j,k),(i′,j′,k′) =









ipλ,
si (i′, j′, k′) = (i −1, j + 1, k),
irλ,
si (i′, j′, k′) = (i −1, j, k + 1),
jrλ,
si (i′, j′, k′) = (i, j −1, k + 1),
0,
en otro caso.
∀(i, j, k), (i′, j′, k′) ∈S.
(b) Dibuje el grafo asociado a la CMTC para n = 3.
Soluci´on: Se tiene:
Suponga ahora que los individuos bien informados pueden olvidar la noticia que desment´ıa la fake
news y pasar a ser ignorantes nuevamente. El tiempo que pasa desde que un individuo conoce la
3

noticia que desment´ıa la fake news y la olvida distribuye exponencial de par´ametro µ > 0 (en d´ıas) y
es independiente para cada individuo
(c) Explique claramente qu´e modificaciones deben realizarse a la CMTC anterior para modelar esta nueva
situaci´on. En particular, describa las nuevas transiciones, tasas asociadas y c´omo cambian los estados
involucrados, sin necesidad de reconstruir toda la cadena desde cero.
Soluci´on: El conjunto de estados se mantiene igual a S. Se a˜nade la transici´on:
q(i,j,k),(i+1,j,k−1) = kµ,
∀(i, j, k) ∈S con k ≥1
El resto de tasas se mantienen.
Problema 2
El local Tofi, famoso entre los alumnos de la universidad, tiene capacidad para 10 personas. Las personas
pueden llegar solas o con un acompa˜nante. Los que llegan solos lo hacen a una tasa de α personas por hora
y los que llegan en pareja lo hacen a una tasa de β parejas por hora. Si es que hay 9 personas en el sistema,
las parejas no pueden entrar y simplemente se van. Una vez que ingresan al sistema cada individuo (ya sea
que vino solo o en pareja), tiene un tiempo de permanencia que distribuye exponencial con media 1
µ horas.
Modele el problema como una CMTC identificando estados, tasas de transici´on, permanencia y probabili-
dades de transici´on entre estados.
Soluci´on: El grafo correspondiente es el siguiente:
0
2
1
6
5
7
8
9
10
4
3
β
β
β
10µ
9µ
8µ
7µ
6µ
α
α
α
β
β
α
α
β
5µ
α
α
α
α
α
β
β
β
4µ
3µ
2µ
µ
Las tasas de transici´on instant´anea para cada estado son:
⋄Para i = 0, 1,..., 9 se tiene:
qi,i+1 = α
⋄Para i = 0, 1,..., 8 se tiene:
qi,i+2 = β
⋄Para i = 1, 2,..., 10 se tiene:
qi,i−1 = iµ
Las tasas de permanencia para cada estado son:
⋄Para el estado 0 se tiene:
ν0 = α + β
4

⋄Para i = 1, 2,..., 8 se tiene:
νi = α + β + iµ
⋄Para el estado 9 se tiene:
ν9 = α + 9µ
⋄Para el estado 10 se tiene:
ν10 = 10µ
Las probabilidades de transici´on entre estados son:
⋄Para Pi,i+1 tenemos:
α
α + β
,
i = 0
α
α + β + iµ
,
i ∈{1, 8}
α
α + 9µ
,
i = 9
⋄Para Pi,i+2 tenemos:
β
α + β
,
i = 0
β
α + β + iµ
,
i ∈{1, 8}
⋄Para Pi,i−1
iµ
α + β + iµ
,
i ∈{1, 8}
9µ
α + 9µ
,
i = 9
1
,
i = 10
Problema 3 (Propuesto)
A las afueras del campus San Joaqu´ın se encuentra el puesto de fajitas de don Pedro. Este recibe una
gran cantidad de estudiantes que desean almorzar las fajitas que ofrece. Para modernizarse, el due˜no est´a
implementando un sistema de atenci´on autom´atica, en el cual se debe realizar el pedido en una m´aquina
que coloc´o al frente del puesto.
Considere que el sistema implementado tiene tres modos de atenci´on: r´apido, medio y lento. En el modo
lento, se puede atender a un cliente a la vez y el tiempo para que llegue el pedido distribuye Exponencial
con tasa α (llegadas por minutos). En el modo medio, se puede atender a dos personas a la vez y el tiempo
de atenci´on distribuye Exponencial con tasa α/2 (llegadas por minuto). Finalmente, en el modo r´apido,
se puede atender a dos personas a la vez pero con un tiempo de atenci´on por persona que distribuye
Exponencial con tasa β (llegadas por minuto con, α/2 < β < α).
La llegada de estudiantes que desean comer fajitas es un Proceso de Poisson con tasa de llegada de λ
estudiantes por minuto. Si al terminar un pedido hay 5 o m´as estudiantes en el sistema (atenci´on + cola),
entonces la m´aquina pasa al siguiente modo de atenci´on m´as r´apido de ser posible. Si al terminar un pedido
hay 2 o menos estudiantes en el sistema, la m´aquina pasa al siguiente modo m´as lento de ser posible
(es decir, nunca va a saltar de lento a r´apido o viceversa, y no hay modo m´as r´apido/lento que el modo
r´apido/lento). Asuma que si hay m´as de 7 estudiantes en el sistema, nadie entrar´a a la cola del puesto ya
que en dicho caso los estudiantes prefieren comer en otro lado.
Se desea modelar este nuevo sistema de atenci´on como una CMTC {X(t), t ≥0} donde X(t) representa la
cantidad de estudiantes en el sistema y el modo de funcionamiento. Asuma que el sistema est´a en modo
lento en t = 0. A partir de lo anterior, responda:
5

a) Defina X(t) y el conjunto de estados Ω.
Soluci´on: Se define,
X(t) := (Modo m´aquina, N´umero de personas en el sistema)
con,
Ω= {(L, 0), . . . , (L, 7), (M, 2), . . . , (M, 7), (R, 3), . . . , (R, 7)}
Donde, L, M y R representan el modo lento, medio y r´apido de la m´aquina, respectivamente.
b) Calcule todas las tasas de permanencia y tasas de transici´on instant´anea. Puedes dejar la soluci´on
expresada de forma gr´afica y/o como f´ormulas matem´aticas que distingan todos los casos posibles.
Soluci´on: Las tasas de transici´on instant´anea, qij, est´an dadas por,
Mientras que las tasas de permanencia, vij,
vL,0
=
λ
vL,i
=
λ + α
∀i ∈{1, . . . , 6}
vL,7
=
α
vM,i
=
λ + α
∀i ∈{2, . . . , 6}
vM,7
=
α
vR,i
=
λ + 2β
∀i ∈{3, . . . , 6}
vR,7
=
2β
6

