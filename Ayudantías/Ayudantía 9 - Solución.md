Pontificia Universidad Cat´olica de Chile
Escuela de Ingenier´ıa
Departamento de Ingenier´ıa Industrial y de Sistemas
ICS2123 – Modelos Estoc´asticos
Profesores Ver´onica Godoy y Andr´es Navarro
Ayudante Jefe Joaqu´ın Vergara
Primer Semestre 2026
Ayudant´ıa 9:
CMTD III
Ayudantes: Emilio Pe˜na (emilio.penasepulveda@uc.cl) & Mart´ın Pe˜na (martinpena@uc.cl)
Resumen
CMTD
Una CMTD es un proceso estoc´astico que toma valores denominados estados, donde Xn = i significa que
el sistema se encuentra en el estado i en la etapa n. Adem´as, la probabilidad de pasar del estado i al estado
j es constante dada por Pij.
Largo plazo
Se estudia l´ımn→∞P (n)
ij
si el l´ımite existe, se puede interpretar como al probabilidad de que, si parto en el
estado i, y observo un proceso por un largo tiempo, el nuevo estado observado sea j.
⋄Si j es recurrente nulo o transiente l´ımn→∞P (n)
ij
= 0
⋄Si j es recurrente positivo:
• Si j es aperi´odico:
Si i = j : l´ım
n→∞P (n)
ij
= l´ım
n→∞P (n)
jj
=
1
E[T(j, j)]
Si i ̸= j : l´ım
n→∞P (n)
ij
=
F(i, j)
E[T(j, j)]
• Si j es peri´odico con per´ıodo d:
Si i = j :
l´ım
n→∞P (nd)
jj
=
d
E[T(j, j)]
l´ım
n→∞P (nd+k)
jj
= l´ım
n→∞P (nd+k)
jj
= 0
∀k = 1, 2, ..., d −1.
Si i ̸= j : e i pertenece a la misma clase que j, y sea n0 el n´umero m´ınimo de etapas para ir de
i a j.
l´ım
n→∞P (n0+nd)
ij
=
d
E[T(j, j)]
l´ım
n→∞P (n0+nd+k)
ij
= 0
k = 1, 2, . . . , d −1
Si i ̸= j : e i pertenece a una clase recurrente distinta:
l´ım
n→∞P (n)
ij
= 0
Si i ̸= j : e i pertenece a una clase transiente:
l´ım
n→∞P (n)
ij
= ... depende de la estructura de la cadena
1

Proposici´on
⋄Si en una CMTD existe al menos una clase recurrente positiva peri´odica, entonces no existen todos
los l´ımn→∞P (n)
ij
⋄Si en una CMTD no existe una clase recurrente positiva peri´odica entonces existen todos los l´ımn→∞P (n)
ij
Distribuci´on l´ımite
Si existen todos los l´ımites para las probabilidades de transici´on en n ∈N etapas y, en todos los casos, estos
l´ımites no dependen del estado inicial, diremos que el proceso tiene distribuci´on de probabilidades l´ımite.
Es decir, en este caso se tiene que para todo j ∈S se cumple que para cualquier i ∈S:
l´ım
n→∞P (Xn = j) = l´ım
n→∞P (n)
ij
Distribuci´on estacionaria
Se le llama distribuci´on de proabilidades estacionaria a la soluci´on del siguiente sistema
πT = πT P
X
i∈S
πi = 1
Proposici´on
Si una CMTD tiene distribuci´on l´ımite y distribuci´on estacionaria, entonces ambas coinciden y se usa el
vector π para denotar esta distribuci´on.
πj = l´ım
n→∞P (Xn = j) = l´ım
n→∞P (n)
ij
Interpretaci´on: La probabilidad l´ımite de que el proceso se encuentre en el estado j ∈S en un tiempo n ∈N
(con n →∞) es igual a la proporci´on de tiempo, en el largo plazo, que el proceso estar´a en el estado j ∈S
(probabilidad estacionaria).
Algunas definiciones importantes
⋄CMTD irreducible: cuando tiene finitos estados y todos los estados se comunican.
⋄Si una CMTD es irreducible y aperi´odica, entonces el proceso tiene distribuci´on l´ımite y distribuci´on
estacionaria (y coinciden).
2

Problema 1
La Escuela de Ingenier´ıa tiene un servidor de computadores con varias CPUs. Considera que se mide el
nivel de uso de las CPUs en intervalos de tiempo de 1 hora. Los niveles de uso de las CPUs pueden ser:
alto (A), medio (M) o bajo (B).
Por otro lado, el servidor de la escuela tiene 3 modos de operaci´on: normal (N), ahorro de energ´ıa (E) y en
reparaci´on (R). Se ha encontrado que el cambio entre estado de las CPUs de una medici´on a la siguiente
se comporta como una CMTD con la siguiente matriz de transici´on:
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

(N, B)
(N, M)
(N, A)
(E, B)
(E, M)
(E, A)
(R)
(N, B)
0.5
0
0.5
0
0
0
0
(N, M)
0.3
0
0.7
0
0
0
0
(N, A)
0
0.1
0.9
0
0
0
0
(E, B)
0
0
0
0
0
0
1
(E, M)
0
0
0
0.4
0
0.6
0
(E, A)
0
0.2
0
0
0.5
0.3
0
(R)
0
0
0
1 −p
p
0
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

Donde p ∈[0, 1] representa la probabilidad de poder reparar por completo las CPUs, y 1−p la probabilidad
de repararla solo parcialmente. En base a esto responda las siguientes preguntas:
(a) Esboce el grafo que permita modelar esta CTMD para el caso de p ̸= 0, luego especifique las clases
que la componen y clasif´ıquelas.
Soluci´on: El grafo es
R
E, B
E, M
N, A
N, M
N, B
E, A
0.3
0.5
0.1
0.7
0.5
0.2
0.4
0.6
0.5
0.9
1
1 −p
p
0.3
Las clases corresponden a:
⋄{(E, A), (E, M), (E, B), (R)}: Clase transiente
⋄{(N, A), (N, M).(N, B)}: Clase recurrente positiva aperi´odica
(b) Justifique la existencia (o la no existencia) de distribuci´on l´ımite en la CTMD. En caso de existir,
explique como calcularla (No es necesario desarrollar las expresiones).
Soluci´on: La CMTD cuenta con una clase transciente y una ´unica clase recurrente positiva, adem´as
esta clase recurrente es aperi´odica, por lo que cumple las condiciones para poseer distribuci´on l´ımite
(o sea, que existan las probabilidades l´ımite, y que est´as no dependan del estado inicial).
3

Las formulas para calcular la distribuci´on l´ımite l´ımn→∞P (n)
ij
se detallan a continuaci´on:
Si j es transiente:
l´ım
n→∞P (n)
ij
= 0 ∀i
Si j es recurrente positivo aperi´odico:
l´ım
n→∞P (n)
ij
=
F(i, j)
E[T(j, j)] ∀i
.
As´ı:
l´ım
n→∞P (n)
ij
= 0 ∀j ∈{(E, A), (E, M), (E, B), (R)} ∀i
l´ım
n→∞P (n)
ij
=
F(i, j)
E[T(j, j)] ∀j ∈{(N, A), (N, M).(N, B)} ∀i
(c) Justifique la existencia (o la no existencia) de distribuci´on estacionaria en la CTMD. En caso de
existir, calcule las probabilidad de largo plazo.
Soluci´on: La CMTD cuenta con solo una clase recurrente positiva, por lo que cumple las condiciones
para poseer distribuci´on estacionaria (no es necesario que esta sea aperi´odica). Es m´as, dado que
existe distribuci´on l´ımite, debe existir distribuci´on estacionaria y deben coincidir.
Sea πj la probabilidad de encontrarse en el nodo j en el largo plazo (donde por lo mencionado ante-
riormente se cumple que: πj = l´ımn→∞P (n)
ij
∀i). Para obtener el valor de la distribuci´on estacionaria
se debe resolver el siguiente sistema de ecuaciones:
πT = πT · P
X
j∈Ω
πj = 1
Por lo tanto el sistema a resolver corresponde a:
π(N,B) = 0.5π(N,B) + 0.3π(N,M)
π(N,M) = 0.1π(N,A) + 0.2π(E,A)
π(N,A) = 0.5π(N,B) + 0.7π(N,M) + 0.9π(N,A)
π(E,B) = 0.4π(E,M) + (1 −p)π(R)
π(E,M) = 0.5π(E,A) + pπ(R)
π(E,A) = 0.6π(E,M) + 0.3π(E,A)
π(R) = π(E,B)
π(N,B) + π(N,M) + π(N,A) + π(E,B) + π(E,M) + π(E,A) + π(R) = 1
Obteniendo de resultado:
π(E,B) = π(E,M) = π(E,A) = π(R) = 0
π(N,B) = 0.0517
π(N,M) = 0.0862
π(N,A) = 0.8621
(d) Se le informa que existe un costo asociado a cada hora que se usen las CPUs en sus distintas moda-
lidades. Si una hora pasa en nivel alto el costo es de 10$, si pasa en nivel medio el costo es de 5$, si
pasa en bajo el costo es de 3$ y si pasa en reparaci´on el costo es de 40$. Calcule el costo energ´etico
esperado en el largo plazo para un periodo de tiempo de 1 hora.
Soluci´on: Sea V el valor de la energ´ıa en el largo plazo en un periodo de 1 hora. Nos piden calcular
el valor esperado, E[V ]. Luego:
E[V ] =
X
i∈Ω
E[V | πi] · πi = 10 · π(N,A) + 5 · π(N,M) + 3 · π(N,B) + 0
= 9.21
4

(e) Ahora considere que p = 0. Vuelva a clasificar los nodos en sus respectivas clases y per´ıodos. Adicio-
nalmente explique si es que existe o no distribuci´on l´ımite y estacionaria en esta nueva CMTD.
Soluci´on: Las clase ahora corresponden a:
⋄{(E, M), (E, A)}: Clase transiente
⋄{(E, B), (R)}: Clase recurrente positiva con d = 2
⋄{(N, A), (N, M), (N, B)}: Clase recurrente positiva aperi´odica
La distribuci´on l´ımite no existe porque, por un lado, existen periodos en las clases recurrentes posi-
tivas, y por otro, porque existe m´as de una clase recurrente positiva. Por este ´ultimo motivo es que
tampoco existe distribuci´on estacionaria.
(f) A pesar de no poseer distribuci´on estacionaria en la nueva CMTD, si se pueden determinar las
probabilidades de encontrarse en cada nodo en el largo plazo, con el supuesto de que llega a alguna
de las 2 clases recurrentes positivas en particular. Encuentre estas probabilidades para ambos casos,
es decir, para el caso de que la cadena lo lleve a cada una de las clases recurrentes.
Soluci´on: Primero, supongamos, que la CMTD inicia o nos lleva a la clase recurrente {(E, B), (R)}.
Para este subcaso, se puede construir un sistema de ecuaciones particular para este par de nodos, el
que corresponde a:
π(E,B) = π(R)
π(R) = π(E,B)
π(E,B) + π(R) = 1
Obteniendo como resultado:
π(E,B) = π(R) = 0.5
Para el segundo caso posible, supongamos que la CMTD inicia o nos lleva a la clase recurrente
{(N, B), (N, M), (N, A)}. Para este caso, se puede construir un sistema de ecuaciones particular para
este grupo de nodos, que coincide con el calculado en (c), por lo que el resultado de las probabilidades
de este subcaso es equivalente al obtenido en (c).
5

Problema 2
El fin de semana pr´oximo, usted ir´a a jugar un partido de tenis en contra de su amigo. Usted esta convencido
de que posee una probabilidad p ∈(0, 1) de ganarle en cada punto. Considerando que todos los puntos son
independientes uno de otro, responda las siguientes preguntas:
Nota: Un partido de tenis de subdivide en JUEGOS, las puntuaciones para cada JUEGO son 0, 15, 30,
40 y FIN, el primer jugador en llegar a FIN, es decir, anotar 4 puntos gana el JUEGO y se le anota 1
JUEGO ganado, con la excepci´on de cuando el marcador va 40-40, en cuyo caso deber´an obtener 2 puntos de
diferencia con su contrincante para llevarse el JUEGO, lo cual se conoce t´ecnicamente como “Av”(Ventaja).
(a) Modele el comportamiento de un JUEGO como una CMTD, especifique sus estados y luego clasifi-
quelos seg´un sus clases y per´ıodos.
Soluci´on: Los estados corresponden a la puntuaci´on del JUEGO, en donde cada jugador tiene como
posible puntaje 0,15,30,40,Av. Adicionalmente, se incluyen los estados GANAR (G) y PERDER (P)
(visto desde la perspectiva del jugador principal), por lo que los estados posibles son:
Xn ∈{(0, 0), (15, 0), ..., (40, 40), (Av, 40), (40, Av), G, P}
El grafo corresponde a:
0 −0
15 −0
30 −0
40 −0
G
P
0 −15
15 −15
30 −15
40 −15
0 −30
15 −30
30 −30
0 −40
15 −40
30 −40
40 −40
Av −40
40 −Av
40 −30
p
p
p
p
p
p
p
p
p
p
p
p
p
p
p
p
1 −p
1 −p
1 −p
1 −p
1 −p
1 −p
1 −p
1 −p
1 −p
1 −p
1 −p
1 −p
p
1 −p
1 −p
1 −p
1 −p
1 −p
p
1 −p
1
1
En este caso, todos los nodos pertenecen a clases individuales ya que no estan conectados con otros
nodos, excepto los nodos (40, 40), (Av, 40) y (40, Av) los cuales pertenecen a una clase aparte.
Todas las clases son transientes, a excepci´on de las clases que componen a los nodos G y P que son
recurrentes positivos aperi´odicos.
(b) Calcule la probabilidad de ganar un JUEGO, deje expresado en t´erminos de p. Asuma que todos los
JUEGOS empiezan con el marcador 0-0.
Soluci´on: Lo que se nos pide es obtener la probabilidad de ir del nodo (0, 0) al nodo (G) en cualquier
cantidad de etapas, lo cual corresponde a F((0, 0), (G)), al desarrollar esta probabilidad se obtiene:
6

F((0, 0), G) = P(0,0),G +
X
r̸=G
P(0,0),r · F(r, G) = 0 + pF((15, 0), G) + (1 −p)F((0, 15), G)
F((15, 0), G) = P(15,0),G +
X
r̸=G
P(15,0),r · F(r, G) = 0 + pF((30, 0), G) + (1 −p)F((15, 15), G)
F((0, 15), G) = P(0,15),G +
X
r̸=G
P(0,15),r · F(r, G) = 0 + pF((15, 15), G) + (1 −p)F((0, 30), G)
...
F((40, 0), G) = P(40,0),G +
X
r̸=G
P(40,0),r · F(r, G) = p + (1 −p)F((40, 15), G)
...
F((0, 40), G) = P(0,40),G +
X
r̸=G
P(0,40),r · F(r, G) = 0 + pF((15, 40)G) + (1 −p)F(P, G)
...
F((Av, 40), G) = P(Av,40),G +
X
r̸=G
P(Av,40),r · F(r, G) = p + (1 −p)F((40, 40), G)
F((40, Av), G) = P(40,Av),G +
X
r̸=G
P(40,Av),r · F(r, G) = 0 + (1 −p)F((40, 40), G)
F(P, G) = 0
Al resolver el sistema se obtiene: F((0, 0), G) = p4(15−34p+28p2−8p3)
1−2p+2p2
(c) Justifique la existencia (o la no existencia) de la distribuci´on l´ımite y estacionaria en la CMTD. En
caso de existir calcule ambas. En caso de no existir, argumente que espec´ıficamente es lo que impide
su existencia y proponga un cambio a la CMTD para que si existiesen (No necesariamente tiene que
tener sentido para las reglas del tenis).
Soluci´on: En este caso la CMTD cuenta con 2 clases recurrentes, por lo cual, las distribuciones
limites depender´an del punto de partida en la CMTD y, por ende, no existir´a distribuci´on l´ımite.
Para la distribuci´on estacionaria, se tiene una distribuci´on por cada clase recurrente, por lo que no
habr´ıa una ´unica distribuci´on estacionaria para toda la CMTD.
Un posible cambio a la CMTD para que si existan ambas distribuciones ser´ıa convertir alguna de las
2 clases recurrentes a transciente, lo cual se lograr´ıa por medio de la creaci´on de una probabilidad
de ir del nodo P o G, a cualquier otro nodo de la cadena. Con ello habr´ıa una ´unica clase recurrente
aperi´odica permitiendo la existencia de ambas distribuciones.
Otra opci´on ser´ıa unificar las clases recurrentes en una sola, asegur´andose de que siga siendo una clase
aperi´odica. Para ello habr´ıa que agregar una probabilidad de ir del nodo P al nodo G y viceversa.
7

Problema 3 (Propuesto EX 2024-1)
Fernanda es responsable de distribuir los suministros m´edicos entre el almac´en central y una cl´ınica de
un connotado hospital de la regi´on. Tiene r ∈R kits m´edicos que son esenciales para el tratamiento de
pacientes. Si Fernanda est´a en el almac´en al comienzo del d´ıa y la cl´ınica necesita un kit m´edico, llevar´a uno
si es que hay al menos uno disponible en el almac´en. De manera an´aloga, si est´a en la cl´ınica y el almac´en
central necesita un kit m´edico, llevar´a uno de los disponibles en la cl´ınica de vuelta al almac´en (si es que
hay alguno disponible). Supongamos que, independientemente de lo que haya sucedido en el pasado, cada
d´ıa se necesita un kit m´edico con probabilidad pin(0, 1).
(a) Defina una Cadena de Markov en Tiempo Discreto de r+1 estados (necesariamente unidimensionales)
que ayude a determinar la proporci´on del tiempo que Fernanda no tiene un kit donde lo necesita.
Para esto debe definir claramente la variable de estado, el espacio de estados y las probabilidades de
transici´on. Incluya un grafo para modelar la situaci´on.
Soluci´on: Tenemos el siguiente grafo:
0
1
2
...
r −1
r
r −2
1
1 −p
p
p
1 −p
p
1 −p
p
1 −p
p
Del grafo se desprende que las probabilidades de transici´on son:
P(i kits | j kits) =









p
si j = r −i + 1
1 −p
si j = r −i, ∀i > 0
1
si j = r y i = 0
0
en otro caso
(b) Identifique la(s) clase(s) de estados y a partir de eso discuta sobre la existencia de distribuci´on l´ımite
y estacionaria.
Soluci´on: Se tiene una ´unica clase (que contiene a todos los estados) recurrente positiva peri´odica con
periodo 2. Por ello, las probabilidades l´ımite no existir´an, y por tanto la distribuci´on l´ımite tampoco.
Dado que la cadena es irreducible y existe una ´unica clase recurrente positiva (independiente del
periodo), la distribuci´on estacionaria existir´a y estar´a dada por la resoluci´on del sistema de ecuaciones
asociado.
8

(c) Encuentre expl´ıcitamente las probabilidades de la distribuci´on estacionaria. Despu´es, determine qu´e
fracci´on del tiempo Fernanda no tiene un kit cuando lo necesita.
Soluci´on:
Las ecuaciones que nos permiten encontrar las probabilidades estacionarias son las si-
guientes:
π0 = πr · (1 −p)
π1 = πr · p + πr−1 · (1 −p)
π2 = πr−1 · p + πr−2 · (1 −p)
π3 = πr−2 · p + πr−1 · (1 −p)
...
πr−1 = π2 · p + (1 −p)π1
πr = π1 · p + π0
r
X
i=0
πi = 1
Utilizando las r primeras ecuaciones descubrimos que:
π1 = π2 = ... = πr =
π0
1 −p
Si utilizamos esto en la ´ultima ecuaci´on llegamos a que:
π0
1 −p · (r + 1 −p) = 1
π0 =
1 −p
r + 1 −p
Las ocasiones cuando Fernanda no tenga el kit y lo necesite ser´a, que est´e en un lugar sin kit (fracci´on
π0 de los casos) y le toque la mala suerte que este sea necesario (con probabilidad p). Entonces el
resultado es:
Fracci´on del tiempo que necesita kit y no lo tiene = p · π0 = p(1 −p)
r + 1 −p
9

