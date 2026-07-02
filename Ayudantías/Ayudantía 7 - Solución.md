Pontificia Universidad Cat´olica de Chile
Escuela de Ingenier´ıa
Departamento de Ingenier´ıa Industrial y de Sistemas
ICS2123 – Modelos Estoc´asticos
Profesores Ver´onica Godoy y Andr´es Navarro
Ayudante Jefe Joaqu´ın Vergara
Primer Semestre 2026
Ayudant´ıa 7:
CMTD I
Ayudantes: Emilio Pe˜na (emilio.penasepulveda@uc.cl) & Mart´ın Pe˜na (martinpena@uc.cl)
Resumen
Cadenas de Markov en Tiempo Discreto (CMTD)
Una CMTD es un proceso estoc´astico (una variable aleatoria que evoluciona en etapas) que toma valores
denominados estados, donde Xn = i significa que el sistema se encuentra en el estado i en la etapa n.
Es importante mencionar que un proceso estoc´astico {Xn, n ∈N} es una CMTD si cumple con 2 propie-
dades.
Estas son:
⋄Propiedad Markoviana: “La distribuci´on de probabilidad de la siguiente etapa depende de las etapas
anteriores a trav´es de la etapa actual”. Es decir, la informaci´on que se tiene del pasado es redundante
sabiendo el estado del presente. Formalmente diremos que se debe cumplir:
P(Xn+1 = j|Xn = i, Xn−1 = i0, ..., X0 = i0) = P(Xn+1 = j|Xn = i)
Para cualquier j, i, in−1, ..., i0 en el conjunto de estados posibles de Xn.
⋄Propiedad Estacionaria: “La probabilidad de que el proceso cambie de un estado a otro en un determi-
nado n´umero de etapas s´olo depende de los estados y la cantidad de etapas en cuesti´on”. Es decir, esta
probabilidad es independiente del n´umero de etapas que lleva el proceso. Formalmente esto equivale
a decir que P(Xn+1 = j|Xn = i) s´olo depende de i, j y no de n. Por ejemplo, P(Xn+k = j|Xn = i)
depende del hecho de que transcurren k etapas y de (i, j), pero no del hecho de que en la n-´esima
etapa es cuando se estuvo en el estado i.
Finalmente esto implica que la probabilidad de pasar del estado i al estado j en una etapa es constante
dada por:
Pij = P(Xn+1 = j|Xn = i) ∀n ∈Z≥0.
Esta definici´on es la base sobre la que se construye cualquier probabilidad de inter´es respecto a las CMTD,
y se trabajar´a a continuaci´on en el curso.
Ecuaci´on de Chapman-Kolmogorov
La siguiente ecuaci´on nos permite calcular la probabilidad de transici´on en n etapas;
P (n)
ij
=
∞
X
k=0
P (m)
ik
· P (n−m)
kj
∀n ≥m ≥0 y ∀i, j
Matriz de transici´on en n etapas
Denominaremos P (n) a la matriz de transici´on en n etapas. Esta matriz est´a formada con los P (n)
ij
de la
CMTD.
1

Problema 1
Un restaurante exclusivo de Santiago, que dispone de n ∈N≥2 mesas, inicia su jornada recibiendo clientes
bajo una pol´ıtica estricta de admisi´on. En particular, los clientes ´unicamente pueden ingresar al restaurante
al inicio de cada hora. As´ı, los clientes que se encuentren esperando (en caso de haberlos) s´olo son admitidos
en ese instante; si al comenzar la hora todas las mesas se encuentran ocupadas, dichos clientes no ser´an
aceptados y deber´an retirarse.
En cada hora existe una probabilidad p ∈(0, 1) de que lleguen clientes deseosos de entrar, mientras que
con probabilidad 1 −p no llega ninguno. Una vez dentro del restaurante, s´olo si hay al menos dos mesas
ocupadas existe una probabilidad q ∈(0, 1) de que al finalizar esa hora alguna mesa se desocupe.
Cabe resaltar que, en el caso de que el restaurante est´e lleno al inicio de la hora, no se permitir´a el ingreso
de clientes incluso si, posteriormente en esa misma hora, una mesa se libera. En otras palabras, el orden de
los sucesos es: primero se eval´ua la posible entrada de clientes, y s´olo despu´es se analiza la eventual salida
de alguno de los ya presentes.
(a) Modele la cantidad de mesas ocupadas en el restaurante como una CMTD. Sea claro en la definici´on
de etapas, variables de estado y espacio de estados.
Soluci´on: Las etapas del problema corresponden a los momentos en que el sistema cambia de estado,
en este caso, cada hora representar´a una etapa.
Los estados, son los distintos valores en los que se puede encontrar el sistema, en este caso los valores
posibles son la cantidad de mesas ocupadas, que corresponde a: Ω= {0, 1, 2, ..., n}.
Sea {Xn, n ∈N} el proceso estoc´astico que representa el n´umero de mesas ocupadas (dado por
Xn ∈Ω) en la etapa n ∈N). As´ı, la CMTD queda descrita como:
0
1
2
3
n −1
n
...
1 −p
p
1 −p
p
α
p(1 −q)
(1 −p)q
α
(1 −p)q
p(1 −q)
(1 −p)q
α
p(1 −q)
(1 −p)q
α
p(1 −q)
q
1 −q
Con α = (1 −p)(1 −q) + pq
Ahora, un segundo restaurante se coloca aleda˜no al primero. Un cliente cualquiera, tiene una probabilidad
de 0.7 de elegir ir al primer restaurante de 0.3 de ir al segundo, excepto cuando alguno de los 2 restaurantes
este lleno, en este caso se ir´a directamente al otro. Este nuevo restaurante cuenta con m ∈N≥2 mesas
y a partir de ahora en ambos restaurantes solo cuando est´en llenos habr´a una probabilidad q ∈(0, 1) y
r ∈(0, 1) respectivamente de que alguna de las mesas se desocupe al final de la hora.
(b) (Propuesto) Modele el comportamiento de ambos restaurantes como una CMTD. Modele la cantidad
de mesas ocupadas en el restaurante como una CMTD. Sea claro en la definici´on de etapas, variables
de estado y espacio de estados.
Soluci´on: Las etapas vuelven a ser cada una de las horas. Para los estados se debe conocer el
n´umero de mesas ocupadas en cada uno de los restaurantes, por ende, son todas las combinaciones
posibles entre las n mesas del primer restaurante y las m mesas del segundo, lo cual se escribe como:
Ω= {(0, 0), (1, 0), ..., (n, 0), (0, 1), (1, 1), ..., (n, 1), ..., (n, m)}.
Sea {(Xn, Yn), n ∈N} el proceso estoc´astico que representa el n´umero de mesas ocupadas tanto en
los restaurantes 1 y 2 (representado por (Xn, Yn) ∈Ω). As´ı, la CMTD queda descrita como:
2

0, 0
1, 0
n, 0
...
0, 1
1, 1
...
0, m
...
n, 1
...
...
...
1, m
...
n, m
1 −p
0.7p
0.3p
0.7p
0.3p
0.7p
0.3p
0.7p
0.7p
0.3p
0.3p
0.3p
0.7p
0.7p
0.3p
0.7p
0.3p
0.7p
0.3p
1 −p
1 −p
1 −p
1 −p
1 −p
1 −p
1 −p
1 −p
(1 −p)q
(1 −p)(1 −q)
p(1 −q)
pq
p(1 −q)
pq
(1 −p)(1 −q)
(1 −p)q
(1 −p)q
(1 −p)(1 −q)
p(1 −q)
pq
p(1 −r)
(1 −p)r
(1 −p)(1 −r)
pr
pr
(1 −p)r
p(1 −r)
(1 −p)(1 −r)
(1 −p)(1 −r)
p(1 −r)
(1 −p)r
pr
(1 −q)(1 −r)
(1 −q)r
q(1 −r)
qr
3

Problema 2
Usted y un amigo est´an jugando al Polic´ıa y Ladr´on, pero una versi´on un poco diferente. Por ahora usted
ser´a el polic´ıa y su amigo ser´a el ladr´on. Tanto usted como su amigo solo pueden elegir dos habitaciones
posibles, que llamaremos sala 1 y sala 2, donde cada hora cada uno debe elegir si cambiar de sala o
mantenerse en la que est´a. Las probabilidades de pasar de una sala a otra o de mantenerse se presentan en
las siguientes matrices de transici´on para ambos jugadores.
P (policia) =
 1
2
1
1
4
3
4
2
1
2
1
2

P (ladron) =
 1
2
1
1
2
1
2
2
3
5
2
5

Si es que ambos jugadores est´an en la misma sala, durante la hora que estar´an ah´ı hay una probabilidad
del 40 % de que el polic´ıa atrape al ladr´on y termine el juego, y hay un 60 % de que el ladr´on escape y
contin´ue el juego.
(a) Modele este problema como una ´unica CMTD, sea claro en la definici´on de etapas, variables de estado
y espacio de estados.
Soluci´on: Las etapas del problema corresponde a cada hora de juego.
Para los estados se debe conocer la posici´on de cada jugador, por ende, corresponden a todas las
combinaciones posibles en las que pueden estar ambos jugadores, con la salvedad de que se a˜nade un
estado adicional que corresponder´a a cuando el polic´ıa atrape al ladr´on.
Matem´aticamente esto corresponde a: Ω= {(1, 1), (1, 2), (2, 1), (2, 2), C}
Para obtener las transiciones entre estados se analizan las posibles combinaciones de sucesos que
pueden ocurrir de una hora a otra. A modo de ejemplo se analiza que es lo que ocurre si se est´a en
el estado (1,1):
P(1,1)−→C = 40 % = 2
5
P(1,1)−→(1,1) = 60 % · P (policia)
11
· P (ladron)
11
= 3
5 · 1
4 · 1
2 = 3
40
P(1,1)−→(1,2) = 60 % · P (policia)
11
· P (ladron)
12
= 3
5 · 1
4 · 1
2 = 3
40
P(1,1)−→(2,1) = 60 % · P (policia)
12
· P (ladron)
11
= 3
5 · 3
4 · 1
2 = 9
40
P(1,1)−→(2,2) = 60 % · P (policia)
12
· P (ladron)
12
= 3
5 · 3
4 · 1
2 = 9
40
El resto de probabilidades se obtiene de manera an´aloga. As´ı:
P =






(1, 1)
(1, 2)
(2, 1)
(2, 2)
C
(1, 1)
3
40
3
40
9
40
9
40
2
5
(1, 2)
3
20
2
20
9
20
3
10
0
(2, 1)
1
4
1
4
1
4
1
4
0
(2, 2)
9
50
3
25
9
50
3
25
2
5
C
0
0
0
0
1






(b) Suponga que ambos jugadores parten en la sala 1. Calcule la probabilidad de que en 2 horas (2 turnos
del juego) vuelvan a encontrarse en la sala 2.
Soluci´on: Se nos pide obtener la probabilidad de pasar del estado (1,1) al (2,2) en exactamente 2
etapas. Lo cual se representa como P (2)
(1,1)−→(2,2).
Para ello hay 2 opciones de calculo posibles. La primera corresponde a, por medio de inspecci´on
visual, identificar todos los posibles caminos para llegar desde (1,1) a (2,2) en 2 turnos del juego, lo
cual se calcula de la siguiente manera:
4

P 2
(1,1)−→(2,2) = P(1,1)−→(1,1)P(1,1)−→(2,2) + P(1,1)−→(1,2)P(1,2)−→(2,2) + P(1,1)−→(2,1)P(2,1)−→(2,2) + P(1,1)−→(2,2)P(2,2)−→(2,2)
= 3
40 · 9
40 + 3
40 · 3
10 + 9
40 · 1
4 + 9
40 · 3
25
= 0.122625
La segunda alternativa consiste en calcular la matriz P (2), la cual se obtiene realizando el producto
matricial P · P y luego extrayendo la componente (1, 1), (2, 2). Al realizar los calculos de obtiene:
P 2 =






(1, 1)
(1, 2)
(2, 1)
(2, 2)
C
(1, 1)
909
8000
771
8000
1179
8000
981
8000
13
25
(1, 2)
771
4000
679
4000
981
4000
849
4000
9
50
(2, 1)
131
800
109
800
221
800
179
800
1
5
(2, 2)
981
10000
849
10000
1611
10000
1359
10000
13
25
C
0
0
0
0
1






Por ende, P 2
(1,1)−→(2,2) =
981
8000 = 0.122625
5

Problema 3 (Propuesto)
Un restaurante posee 2 mesas, con 2 asientos cada una, para atender a sus clientes. La pol´ıtica del restau-
rante es tal que abre las puertas cada hora para recibir clientes, los que llegan exactamente al terminar
cada hora de atenci´on del restaurante. As´ı, la llegada de clientes durante cada hora al restaurante se puede
describir probabil´ısticamente de la siguiente manera: llega un ´unico cliente junto a su pareja (cliente con
pareja) tiene probabilidad P ∈(0, 1), que llegue un ´unico cliente de forma solitaria (cliente solitario) tiene
probabilidad Q ∈(0, 1), y que no llegue ning´un cliente tiene probabilidad H ∈(0, 1) (con P + Q + H = 1).
Se sabe que un cliente solitario o con pareja que llega al restaurante y no se le asigna una mesa para la
siguiente hora se retirar´a del mismo. Es importante destacar que los clientes que llegan no comparten mesa
entre ellos (o sea, dos solitarios no comparten mesa).
Por otra parte, se sabe que un cliente, solitario o con pareja, la mitad de las veces decidir´a pasar una
nueva hora comiendo en el restaurante si al finalizar una hora cualquiera observa que la otra mesa est´a
desocupada. Pero en el caso de que ambas mesas se encuentren ocupadas, si ambas est´an ocupadas por
clientes con pareja o ambas est´an ocupadas por clientes solitarios, se desocupar´a exactamente una de ellas
para la siguiente hora (y entonces, la otra mesa seguir´a comiendo en el restaurante la siguiente hora). Ahora
bien, en el caso de que una de las mesas est´e ocupada por un cliente solitario y la otra por un cliente con
pareja, ambas mesas se desocupar´an al finalizar la hora.
Bas´andose en la informaci´on anteriormente entregada, construya una CMTD que permita modelar el estado
de ocupaci´on de este restaurante. Explique los estados y etapas.
Soluci´on: Las etapas corresponde a las horas que transcurren en el restaurante.
Sea {(Xn, Yn), n ∈N} el proceso estoc´astico que representa la ocupaci´on del restaurante, donde:
⋄Xn ∈{0, 1, 2}: Representa la ocupaci´on de la mesa 1 del restaurante, donde toma el valor de 0 si no
hay clientes en ella, valor de 1 si hay un cliente solitario, y valor de 2 si hay una pareja.
⋄Yn ∈{0, 1, 2}: Representa la ocupaci´on de la mesa 2 del restaurante, donde toma el valor de 0 si no
hay clientes en ella, valor de 1 si hay un cliente solitario, y valor de 2 si hay una pareja.
El espacio de estados viene dado por Ω= {(0, 0), (1, 0), (2, 0), (1, 1), (2, 1), (2, 2)}. El diagrama que repre-
senta esta CMTD viene dado por:
0, 0
1, 0
2, 0
1, 1
2, 1
2, 2
Q
(H + Q)/2
(H + P)/2
H
Q
P
Q/2
H
H/2
P/2
Q/2
H/2
Q/2
P
Q
P/2
P
H
P/2
Q
P
H
6

