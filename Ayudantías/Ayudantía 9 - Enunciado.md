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
n→∞P (nd+m)
jj
= l´ım
n→∞P (nd+m)
jj
= 0
∀m = 1, 2, ..., d −1.
Si i ̸= j : e i pertenece a la misma clase que j, y sea n0 el n´umero m´ınimo de etapas para ir de
i a j.
l´ım
n→∞P (n0+nd)
ij
=
d
E[T(j, j)]
l´ım
n→∞P (n0+nd+m)
ij
= 0
m = 1, 2, . . . , d −1
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
(b) Justifique la existencia (o la no existencia) de distribuci´on l´ımite en la CTMD. En caso de existir,
explique como calcularla (No es necesario desarrollar las expresiones).
(c) Justifique la existencia (o la no existencia) de distribuci´on estacionaria en la CTMD. En caso de
existir, calcule las probabilidad de largo plazo.
(d) Se le informa que existe un costo asociado a cada hora que se usen las CPUs en sus distintas moda-
lidades. Si una hora pasa en nivel alto el costo es de 10$, si pasa en nivel medio el costo es de 5$, si
pasa en bajo el costo es de 3$ y si pasa en reparaci´on el costo es de 40$. Calcule el costo energ´etico
esperado en el largo plazo para un periodo de tiempo de 1 hora.
(e) Ahora considere que p = 0. Vuelva a clasificar los nodos en sus respectivas clases y per´ıodos. Adicio-
nalmente explique si es que existe o no distribuci´on l´ımite y estacionaria en esta nueva CMTD.
(f) A pesar de no poseer distribuci´on estacionaria en la nueva CMTD, si se pueden determinar las
probabilidades de encontrarse en cada nodo en el largo plazo, con el supuesto de que llega a alguna
de las 2 clases recurrentes positivas en particular. Encuentre estas probabilidades para ambos casos,
es decir, para el caso de que la cadena lo lleve a cada una de las clases recurrentes.
3

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
(b) Calcule la probabilidad de ganar un JUEGO, deje expresado en t´erminos de p. Asuma que todos los
JUEGOS empiezan con el marcador 0-0.
(c) Justifique la existencia (o la no existencia) de la distribuci´on l´ımite y estacionaria en la CMTD. En
caso de existir calcule ambas. En caso de no existir, argumente que espec´ıficamente es lo que impide
su existencia y proponga un cambio a la CMTD para que si existiesen (No necesariamente tiene que
tener sentido para las reglas del tenis).
4

Problema 3 (Propuesto EX 2024-1)
Fernanda es responsable de distribuir los suministros m´edicos entre el almac´en central y una cl´ınica de
un connotado hospital de la regi´on. Tiene r ∈R kits m´edicos que son esenciales para el tratamiento de
pacientes. Si Fernanda est´a en el almac´en al comienzo del d´ıa y la cl´ınica necesita un kit m´edico, llevar´a uno
si es que hay al menos uno disponible en el almac´en. De manera an´aloga, si est´a en la cl´ınica y el almac´en
central necesita un kit m´edico, llevar´a uno de los disponibles en la cl´ınica de vuelta al almac´en (si es que
hay alguno disponible). Supongamos que, independientemente de lo que haya sucedido en el pasado, cada
d´ıa se necesita un kit m´edico con probabilidad p ∈(0, 1).
(a) Defina una Cadena de Markov en Tiempo Discreto de r+1 estados (necesariamente unidimensionales)
que ayude a determinar la proporci´on del tiempo que Fernanda no tiene un kit donde lo necesita.
Para esto debe definir claramente la variable de estado, el espacio de estados y las probabilidades de
transici´on. Incluya un grafo para modelar la situaci´on.
(b) Identifique la(s) clase(s) de estados y a partir de eso discuta sobre la existencia de distribuci´on l´ımite
y estacionaria.
(c) Encuentre expl´ıcitamente las probabilidades de la distribuci´on estacionaria. Despu´es, determine qu´e
fracci´on del tiempo Fernanda no tiene un kit cuando lo necesita.
5

