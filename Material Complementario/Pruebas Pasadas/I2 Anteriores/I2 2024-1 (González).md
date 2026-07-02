Pontificia Universidad Cat´olica de Chile
Escuela de Ingenier´ıa
Departamento de Ingenier´ıa Industrial y de Sistemas
ICS2123 Modelos Estoc´asticos
Profesor Maximiliano Gonz´alez R.
Primer Semestre 2024
Interrogaci´on 2
Tiempo total: 2 horas
Problema 1 (24 puntos)
Nuevamente, este a˜no el sistema de salud en Chile se ve desafiado por una fuerte ola de infecciones respiratorias. Esto afecta
particularmente a centros m´edicos de peque˜nas localidades, los cuales cuentan con recursos bastante limitados. Suponga
un peque˜no centro de salud, en el cual dos m´edicos se dedican a atender consultas regulares y emergencias respiratorias.
El primer m´edico atiende consultas a una tasa de µ1 consultas por d´ıa, mientras que el segundo atiende a una tasa de µ2
consultas por d´ıa. Suponga que los pacientes llegan al centro de salud seg´un un proceso de Poisson de media λp pacientes
por d´ıa. Cada m´edico puede atender a un solo paciente a la vez, por lo que si ambos est´an ocupados en una atenci´on
regular y un nuevo cliente aparece, la recepcionista los har´a esperar en una fila cuya capacidad m´axima es de 2 pacientes.
En cualquier otro caso, dicho paciente ser´a enviado a otro centro de salud.
Por otra parte, si llega un paciente con una emergencia respiratoria, lo cual ocurre a una tasa de λe emergencias por
d´ıa, ambos m´edicos le dar´an prioridad en simult´aneo. Esto significa que dejar´an en espera cualquier atenci´on regular que
estuvieran realizando hasta finalizar con la emergencia. En promedio, el tiempo que les toma resolver una emergencia es de
1/µe d´ıas. Si durante la resoluci´on de una emergencia llega otra similar, los m´edicos se sentir´an abrumados por no poder
atenderla y pedir´an al recepcionista que cancele todos los registros de atenciones actuales, de modo que cualquier consulta
regular que estuviera en espera ser´a enviada a otro centro de salud.
a) (8 pts.) Construya una Cadena de Markov en Tiempo Continuo que modele el estado de ocupaci´on del centro m´edico.
Indique claramente qu´e representa cada estado y las tasas de transici´on instant´anea entre ellos.
b) (4 pts.) Construya el sistema de ecuaciones que permite calcular las probabilidades de largo plazo.
Asumiendo conocidas las probabilidades l´ımite:
c) (4pts.) Indique la tasa de entrada efectiva al centro de salud.
d) (4pts.) Indique la cantidad promedio de casos que se encuentran resolviendo en un instante cualquiera de tiempo.
e) (4pts.) Entregue una expresi´on para el tiempo medio de espera de pacientes en la cola.
Problema 2 (10 puntos)
En un jard´ın infantil un ni˜no quiere construir una torre de bloques. El ni˜no cuenta con un total de 10 bloques id´enticos
y para hacer la torre coloca cada bloque encima del otro. Como el ni˜no es peque˜no tiene una cierta probabilidad de que
al poner un bloque la torre se caiga. La probabilidad de que se caiga la torre depende del n´umero de bloques que lleva
puestos, es decir, si el ni˜no va a poner el i-´esimo bloque la probabilidad de que la torre se caiga es p(i) = (i −1) · 0.05 .
Considere que si la torre se cae esto equivale a tener 1 bloque en la torre. El ni˜no continuara con su juego hasta que la torre
contenga todos los bloques. Considere que Xn es el n´umero de bloques colocados exitosamente despu´es de n movimientos.
Adem´as considere que en caso que la torre se caiga, el resultado es equivalente a que quede un solo bloque en su torre.
a) (5 pts.) Utilizando Xn como variable de estados, modele el problema como una CMTD definiendo el espacio de
estados posibles y las probabilidades de transici´on entre estados.

b) (3 pts.) Una parvularia ha visto jugar al ni˜no varias veces y este siempre se toma un descanso despu´es de haber
botado la torre. ¿Cu´al es la probabilidad de que despu´es de 5 turnos el ni˜no se haya tomado solo un descanso?
c) (2 pts.) La mam´a del ni˜no llega al jard´ın infantil despu´es de un largo tiempo. En ese tiempo el ni˜no ha hecho un
n´umero muy grande de movimientos (n →∞). ¿Cu´al es la probabilidad de que el ni˜no no haya terminado la torre?
Justifique su respuesta.
Problema 3 (26 puntos)
Considere una Cadena de Markov en Tiempo Discreto con estados 1, 2, 3, 4, 5, 6, 7 dada por la siguiente matriz de
transici´on:
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
0.9
0
0
0
0
r
0
0
0
0
0
s
0
0
0.6
0
t
0
0
0
0
0
0
0
0.3
u
0
0.7
0
v
0
0
0.9
0
0
0
0
1
0
0
0
0
0
0.1
0
0
0
w
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
(1)
a) (2 pts.) Suponga que f (0) = (0 0 0 1 0 0 0). ¿Cu´antas etapas tardar´a el sistema en promedio para visitar el estado 1
por primera vez?
b) (2 pts.) Suponga que f (0) = (0 0 0 0.7 0 0 0.3). ¿Qu´e es m´as probable, visitar el estado 5 o visitar el estado 1?
c) (2 pts.) Suponga que f (0) = (0 0 0 0.7 0 0 0.3). Calcule P(X3 = 2, X4 = 5)
d) (5 pts.) Suponga que f (0) = (0 0 0 1 0 0 0). Calcule lim
n→∞f (n)
Las siguientes preguntas son independientes de los apartados anteriores.
e) (3 pts.) A una CMTD con N estados donde se cumple que
X
i
X
j
Pij = N, se le conoce como cadena doblemente
estoc´astica. Utilizando un ejemplo de al menos tres estados que contenga al menos un loop, verifique que la distribuci´on
estacionaria corresponde a una distribuci´on uniforme (i.e. πi = 1/N
∀i)
f) (3 pts.) ¿Qu´e ocurre si no se cumple la condici´on λ < µ en un sistema M/M/∞?
g) (3 pts.) Considerando el desarrollo visto en clases, ¿por qu´e no existen las probabilidades l´ımite en un sistema con
capacidad infinita donde la tasa de atenci´on es exactamente igual a la de llegada de clientes?
h) (3 pts.) Considere un sistema M/G/∞en que la llegada de clientes es a tasa λ > 0 y que los tiempos de atenci´on
tienen distribuci´on uniforme en el intervalo [a, b], con 0 < a < b. Determine el valor de las medidas de desempe˜no Lq
y W para este sistema.
i) (3 pts.) Considere un sistema M/M/1 con tasa de llegada λ y tasa de atenci´on µ. Obtenga la proporci´on de clientes
que al terminar de ser atendidos dejan menos de m personas en el sistema, sin contar dicho cliente. Su respuesta
puede quedar en funci´on de probabilidades l´ımite.
Sistema
Probabilidades l´ımite
C´alculo de L
Ec de Little
M/M/1
Pn = λn−1 · . . . · λ0
µn · . . . · µ1
P0
L = P∞
i=0 n · Pn =
λ
µ −λ
L = λe · W

Soluci´on problema 1
(a) Una forma de resolverlo es la que describe a continuaci´on.
Definimos los siguientes estados:
⋄(0): Ambos m´edicos se encuentran desocupados.
⋄(1): M´edico 2 ocupado atendiendo un paciente normal y m´edico 1 desocupado.
⋄(2): Ambos m´edicos atendiendo paciente normal.
⋄(3): M´edico 1 atendiendo paciente normal y m´edico 2 desocupado.
⋄(4): Ambos m´edicos atienden una emergencia, el m´edico 2 deja su paciente normal en pausa y el m´edico 1 no
tiene otros pacientes en pausa.
⋄(5): Ambos m´edicos atienden una emergencia y dejan sus pacientes normales en pausa.
⋄(6): Ambos m´edicos atienden una emergencia, el m´edico 1 deja su paciente normal en pausa y el m´edico 2 no
tiene otros pacientes en pausa.
⋄(7): Ambos m´edicos atienden una emergencia y no tienen otros pacientes en pausa.
⋄(8): Ambos m´edicos atendiendo paciente normal y un paciente en la cola.
⋄(9): Ambos m´edicos atendiendo paciente normal y dos pacientes en la cola.
[4 puntos] por definir estados que logren modelar el problema
0
1
2
3
4
5
6
7
9
8
λp
2
λp
2
µ1
µ2
λp
µ1 + µ2
λp
µ1 + µ2
λe
µe
λe
µe
λp
µ1
λp
λe
µe
λe
λe
λe
λe
µ2
µe
λe
λe
[4 puntos] por definir correctamente las tasas de transici´on

(b) La condici´on es que la tasa de salida de un estado es igual a la suma de las tasas de entrada de los estados distintos.
(λp + λe)P0 = µ1P1 + µ2P2 + µeP7
(µ1 + λp + λe)P1 = µ2P2 + λp
2 P0 + µ2P2 + µeP4
(µ2 + µ1 + λp + λe)P2 = λpP1 + (µ1 + µ2)P8 + µeP5 + λpP3
(µ2 + λp + λe)P3 = λp
2 P0 + µ1P2 + µeP6
(µe + λe)P4 = λeP1
(µe + λe)P5 = λeP2 + λeP8 + λeP9
(µe + λe)P6 = λeP3
λeP7 = λe(P5 + P6 + P4 + P0)
(λp + µ1 + µ2 + µe)P8 = λpP2 + (µ1 + µ2)P9
(µ1 + µ2 + µe)P9 = λpP8
9
X
i=0
Pi = 1
[4 puntos] se resta 0.25 puntos por cada ecuaci´on faltante
(c) Para obtener la tasa de entrada efectiva necesitamos considerar cuando cada tipo de paciente podr´a o no ingresar al
sistema. En particular, un paciente no podr´a ingresar en los siguientes estados:
⋄λp: Estados donde hay emergencia o hay fila de espera llena.
⋄λe: Estados donde hay una emergencia siendo atendida.
λeff = λp(1 −P4 −P5 −P6 −P7 −P9) + λe(1 −P4 −P5 −P6 −P7)
[2 puntos por parte clientes regulares]
[2 puntos por parte clientes emergencia]
(d) Para obtener dicha cantidad, que llamaremos C, calculamos la suma ponderada por cada estado
C = (P1 + P3 + P4 + P5 + P6 + P7) + 2 · (P2 + P8 + P9)
[4 puntos]
(e)
Wq =
Lq
λefectiva
[1 punto]
Donde Lq = P8 + 2 · P9 [1 punto] y λefectiva corresponde a la tasa de entrada a la cola de espera solamente.
Wq = P8 + 2 · P9
λp(P2 + P8)[2 puntos]
Soluci´on problema 2
Se consideran correctos los modelos que parten de 0 bloques y tambi´en los que parten de 1 bloque.
(a) Xn: Cantidad de bloques colocados exitosamente despu´es de n movimientos.
Ω= {1, 2, . . . 10} [1 punto]

1
2
3
4
5
6
7
9
10
8
p2
1 −p2
p3
1 −p3
p4
1 −p4
p5
1 −p5
p6
1 −p6
p7
1 −p7
p8
1 −p8
p9
1 −p9
p10
1 −p10
1
[4 puntos]
(b) Queremos que despu´es de 5 turnos s´olo se haya ca´ıdo la torre una vez. Consideramos:
⋄Ca´ıda en turno 1 = 0.05 · 0.95 · 0.9 · 0.85 · 0.8 = 0.02907
⋄Ca´ıda en turno 2 = 0.95 · 0.1 · 0.95 · 0.9 · 0.85 = 0.069
⋄Ca´ıda en turno 3 = 0.95 · 0.9 · 0.15 · 0.95 · 0.9· = 0.11
⋄Ca´ıda en turno 4 = 0.95 · 0.9 · 0.85 · 0.2 · 0.95 = 0.138
⋄Ca´ıda en turno 5 = 0.95 · 0.9 · 0.85 · 0.8 · 0.25 = 0.145
[2 puntos]
Finalmente sumamos todos los casos y obtenemos 0.49107 [1 punto]
(c) Como el estado 10 es el ´unico estado recurrente positivo y adem´as es aperi´odico, en el largo plazo nos encontraremos
en este estado con probabilidad igual a 1. Por lo tanto, la probabilidad de que el ni˜no no haya terminado la torre es
igual a 0. [2 puntos]
Soluci´on problema 3
Se presenta un grafo para visualizar las preguntas con mayor facilidad:

1
2
3
4
5
6
7
0.9
0.1
1
0.6
0.4
0.3
0.7
0.1
0.9
1
0.1
0.9
(a) E(T(4, 1)) = 1 + 0, 3E(T(4, 1)) + 0, 7E(T(7, 1))[1 punto]
E(T(7, 1)) = 1 + 0, 3E(T(2, 1)) + E(T(6, 1))[0.5 puntos]
Sin embargo, E(T(2, 1)) = ∞por lo tanto E(T(4, 1)) = ∞[0.5 puntos]
(b) Lo que se quiere calcular es:F(4, 5), F(4, 1), F(7, 5) y F(7, 1).
F(4, 5) = P45 + P47F(7, 5) + P44F(4, 5) lo que es equivalente a 0.7F(4, 5) = 0.7F(7, 5)[0.5 puntos]
Por otro lado, F(7, 5) = P75 + P72F(2, 5) + P76F(6, 5) = 0 + 0, 1 + 0.9F(6, 5) = 0 + 0.1 + 0 = 0.1 [0.5 puntos]
Como F(4, 5) = F(7, 5) se tiene lo siguiente:
F(4, 5) = 0.1
F(7, 5) = 0.1
Ahora se calcula:
F(7, 1) = P71 + P72F(2, 1) + P76F(6, 1) = 0 + 0.1F(2, 1) + 0.9F(6, 1) = 0 + 0 + 0.9P76 = 0.9[0.5 puntos]
F(4, 1) = 0.3F(4, 1) + 0.7F(7, 1) = 0.9 [0.5 puntos]
La probabilidad de visitar el estado 1 es: 0.7F(4, 1) + 0.3F(7, 1) = 0.9
La probabilidad de visitar el estado 5 es: 0.7F(4, 5) + 0.3F(7, 5) = 0.1
Por lo tanto, es m´as probable visitar el estado 1 que el estado 5.
(c) Si X3 = 2, entonces X4 ser´a 5 con probabilidad 1, debido a que P2,5 = 1. Por lo tanto, la probabilidad que se busca
es P(X3 = 2)
P(X3 = 2) = 0.7 · P 3
4,2 + 0.3 · P 3
7,2[0.5puntos]
Notamos que P 3
4,2 tiene una ´unica forma de suceder, equivalente a P44 ·P47 ·P72. La probabilidad asociada es entonces
0.021
Luego, de manera similar P 3
7,2 tambi´en tiene una ´unica manera de ocurrir, equivalente a P72 · P25 · P52, cuyo valor es
0.01.
Finalmente, P(X3 = 2) = 0.0147 + 0.003 = 0.0177
(d) Sabemos que los estados 4 y 7 son transientes, por lo que el sistema con certeza no se encontrar´a en dichos estados
en el largo plazo. As´ı, calculamos entonces la probabilidad de estar en cada estado recurrente, por la probabilidad de
que el sistema efectivamente visite esa sub-cadena alguna vez.
De b) ya sabemos que F(4, i) = 0.1 para i ∈{2, 5} y que F(4, j) = 0.9 para j ∈{1, 3, 6} [0.5 puntos]
Ahora se obtiene la distribuci´on estacionaria para cada clase recurrente.
 0
1
0.1
0.9

(2)

π2 = 0.1π5
π5 = π2 + 0.9π5
Por lo tanto se tiene que π5 = 10
11 y π2 =
1
11[1.5 puntos]
Ahora para los estados 1, 3 y 6 se tiene lo siguiente:


0.9
0
0.1
0.6
0.4
0
0
1
0


(3)
π1 = 0.9π1 + 0.6π3
π3 = 0.4π3 + π6
π6 = 0.1π1
Por lo tanto se obtiene que π1 = 60
76, π3 = 10
76 y π6 =
6
76[1.5 puntos]
Finalmente se obtiene la distribuci´on de probabilidades en el largo plazo:
lim
n→∞f (n) =
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
0.9 · 60
76
0.1 · 1
11
0.9 · 10
76
0
0.1 · 10
11
0.9 · 6
76
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
=
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
54
76
1
110
9
76
0
1
11
54
760
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
[1 punto]
(e) En una Cadena de Markov en Tiempo Discreto (CMTD) con N estados, si la suma de todas las probabilidades de
transici´on es igual a N, o equivalentemente la suma de las columnas es 1, la cadena se conoce como doblemente
estoc´astica.
Ejemplo 1:
En un ejemplo simple con tres estados (A, B, C) y la matriz de transici´on:
P =


1/3
1/3
1/3
1/3
1/3
1/3
1/3
1/3
1/3

[2puntos]
(4)
cada fila y columna suma 1. Para encontrar la distribuci´on estacionaria, verificamos que el vector π = [1/3, 1/3, 1/3]
se multiplica por la matriz de transici´on para dar el mismo vector π, lo que demuestra que la distribuci´on estacionaria
es uniforme[1 punto].
Ejemplo 2:
Supongamos una cadena de Markov con tres estados y la siguiente matriz de transici´on:
P =


0.5
0.25
0.25
0.25
0.5
0.25
0.25
0.25
0.5


Cada fila y cada columna suman 1, cumpliendo la condici´on de ser doblemente estoc´astica. Para encontrar la dis-
tribuci´on estacionaria π, necesitamos que πP = π. Supongamos que π = (π1, π2, π3). Entonces,
(π1, π2, π3)


0.5
0.25
0.25
0.25
0.5
0.25
0.25
0.25
0.5

= (π1, π2, π3)
Esto se convierte en el siguiente sistema de ecuaciones:
0.5π1 + 0.25π2 + 0.25π3 = π1
0.25π1 + 0.5π2 + 0.25π3 = π2

0.25π1 + 0.25π2 + 0.5π3 = π3
Dado que la suma de las probabilidades debe ser 1 (π1 + π2 + π3 = 1), podemos ver que π1 = π2 = π3 = 1
3.
(f) En un sistema M/M/∞, si la tasa de llegada λ es igual o mayor que la tasa de servicio µ, significa que los clientes
llegan m´as r´apido de lo que demoran en ser atendidos. Sin embargo, como el sistema tiene un n´umero infinito de
servidores este no se va a saturar, puesto que siempre que llegue un cliente, se podr´a atender inmediatamente.[3
puntos]
(g) Si λ = µ se tiene que P∞
n=0( λ
µ)n diverge (suma de infinitos 1’s) y no se puede determinar P0 =
 P∞
n=0( λ
µ)n−1
.
Luego, al no existir P0, no se puede calcular ning´un Pn.
(h) Si consideramos un sistema M/G/∞, tenemos un sistema con infinitos servidores, lo que significa que ning´un cliente
tiene que esperar ya que es inmediatamente atendido. Luego, la cantidad de clientes promedio en la cola es Lq = 0 [1
punto]. Por otro lado, el tiempo medio que tardar´a cada cliente en el sistema, corresponder´a ´unicamente al tiempo
que tarda en ser atendido [1 punto], luego, sea U la variable aleatoria que distribuye Uniforme[a,b], tenemos que
W = E[U] = b−a
2
+ a[1 punto].
(i) Podemos determinar la proporci´on a trav´es de la cantidad de clientes promedio que hay en el sistema, L, y la cantidad
de clientes promedio que al terminar de ser atendidos dejan a k o menos personas en el sistema, Lk:
L =
∞
X
n=0
n · Pn
Lk =
k+1
X
n=1
n · Pn[2puntos]
Lk debe considerarse desde el ´ındice 1, para asegurar que al menos haya un cliente atendi´endose, hasta k + 1, porque
el cliente k + 1, al terminar de atenderse, deja k clientes en el sistema.
La proporci´on pedida corresponde a:
p = Lk
L [1punto]

Pontificia Universidad Cat´olica de Chile
Escuela de Ingenier´ıa
Departamento de Ingenier´ıa Industrial y de Sistemas
ICS2123 Modelos Estoc´asticos
Profesor Maximiliano Gonz´alez R.
Primer Semestre 2024
Interrogaci´on 2
Tiempo total: 2 horas
Problema 1 (24 puntos)
Nuevamente, este a˜no el sistema de salud en Chile se ve desafiado por una fuerte ola de infecciones respiratorias. Esto afecta
particularmente a centros m´edicos de peque˜nas localidades, los cuales cuentan con recursos bastante limitados. Suponga
un peque˜no centro de salud, en el cual dos m´edicos se dedican a atender consultas regulares y emergencias respiratorias.
El primer m´edico atiende consultas a una tasa de µ1 consultas por d´ıa, mientras que el segundo atiende a una tasa de µ2
consultas por d´ıa. Suponga que los pacientes llegan al centro de salud seg´un un proceso de Poisson de media λp pacientes
por d´ıa. Cada m´edico puede atender a un solo paciente a la vez, por lo que si ambos est´an ocupados en una atenci´on
regular y un nuevo cliente aparece, la recepcionista los har´a esperar en una fila cuya capacidad m´axima es de 2 pacientes.
En cualquier otro caso, dicho paciente ser´a enviado a otro centro de salud.
Por otra parte, si llega un paciente con una emergencia respiratoria, lo cual ocurre a una tasa de λe emergencias por
d´ıa, ambos m´edicos le dar´an prioridad en simult´aneo. Esto significa que dejar´an en espera cualquier atenci´on regular que
estuvieran realizando hasta finalizar con la emergencia. En promedio, el tiempo que les toma resolver una emergencia es de
1/µe d´ıas. Si durante la resoluci´on de una emergencia llega otra similar, los m´edicos se sentir´an abrumados por no poder
atenderla y pedir´an al recepcionista que cancele todos los registros de atenciones actuales, de modo que cualquier consulta
regular que estuviera en espera ser´a enviada a otro centro de salud.
a) (8 pts.) Construya una Cadena de Markov en Tiempo Continuo que modele el estado de ocupaci´on del centro m´edico.
Indique claramente qu´e representa cada estado y las tasas de transici´on instant´anea entre ellos.
b) (4 pts.) Construya el sistema de ecuaciones que permite calcular las probabilidades de largo plazo.
Asumiendo conocidas las probabilidades l´ımite:
c) (3pts.) Indique la tasa de entrada efectiva al centro de salud.
d) (3pts.) Indique la cantidad promedio de casos que se encuentran resolviendo en un instante cualquiera de tiempo.
e) (3pts.) Entregue una expresi´on para el tiempo medio de espera de pacientes en la cola.
f) (3pts.) Si en el instante t los m´edicos est´an resolviendo una emergencia, indique el tiempo esperado que transcurrir´a
antes de comenzar a resolver otra emergencia.
Problema 2 (10 puntos)
En un jard´ın infantil un ni˜no quiere construir una torre de bloques. El ni˜no cuenta con un total de 10 bloques id´enticos
y para hacer la torre coloca cada bloque encima del otro. Como el ni˜no es peque˜no tiene una cierta probabilidad de que
al poner un bloque la torre se caiga. La probabilidad de que se caiga la torre depende del n´umero de bloques que lleva
puestos, es decir, si el ni˜no va a poner el i-´esimo bloque la probabilidad de que la torre se caiga es p(i) = (i −1) · 0.05 .
Considere que si la torre se cae esto equivale a tener 1 bloque en la torre. El ni˜no continuara con su juego hasta que la torre
contenga todos los bloques. Considere que Xn es el n´umero de bloques colocados exitosamente despu´es de n movimientos.
Adem´as considere que en caso que la torre se caiga, el resultado es equivalente a que quede un solo bloque en su torre.

a) (5 pts.) Utilizando Xn como variable de estados, modele el problema como una CMTD definiendo el espacio de
estados posibles y las probabilidades de transici´on entre estados.
b) (3 pts.) Una parvularia ha visto jugar al ni˜no varias veces y este siempre se toma un descanso despu´es de haber
botado la torre. ¿Cu´al es la probabilidad de que despu´es de 5 turnos el ni˜no se haya tomado solo un descanso?
c) (2 pts.) La mam´a del ni˜no llega al jard´ın infantil despu´es de un largo tiempo. En ese tiempo el ni˜no ha hecho un
n´umero muy grande de movimientos (n →∞). ¿Cu´al es la probabilidad de que el ni˜no no haya terminado la torre?
Justifique su respuesta.
Problema 3 (26 puntos)
Considere una Cadena de Markov en Tiempo Discreto con estados 1, 2, 3, 4, 5, 6, 7 dada por la siguiente matriz de
transici´on:
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
0.9
0
0
0
0
r
0
0
0
0
0
s
0
0
0.6
0
t
0
0
0
0
0
0
0
0.3
u
0
0.7
0
v
0
0
0.9
0
0
0
0
1
0
0
0
0
0
0.1
0
0
0
w
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
(1)
a) (2 pts.) Suponga que f (0) = (0 0 0 1 0 0 0). ¿Cu´antas etapas tardar´a el sistema en promedio para visitar el estado 1
por primera vez?
b) (2 pts.) Suponga que f (0) = (0 0 0 0.7 0 0 0.3). ¿Qu´e es m´as probable, visitar el estado 5 o visitar el estado 1?
c) (2 pts.) Suponga que f (0) = (0 0 0 0.7 0 0 0.3). Calcule P(X3 = 2, X4 = 5)
d) (5 pts.) Suponga que f (0) = (0 0 0 1 0 0 0). Calcule lim
n→∞f (n)
Las siguientes preguntas son independientes de los apartados anteriores.
e) (3 pts.) A una CMTD con N estados donde se cumple que
X
i
X
j
Pij = N, se le conoce como cadena doblemente
estoc´astica. Utilizando un ejemplo de al menos tres estados que contenga al menos un loop, verifique que la distribuci´on
estacionaria corresponde a una distribuci´on uniforme (i.e. πi = 1/N
∀i)
f) (3 pts.) ¿Qu´e ocurre si no se cumple la condici´on λ < µ en un sistema M/M/∞?
g) (3 pts.) Considerando el desarrollo visto en clases, ¿por qu´e no existen las probabilidades l´ımite en un sistema con
capacidad infinita donde la tasa de atenci´on es exactamente igual a la de llegada de clientes?
h) (3 pts.) Considere un sistema M/G/∞en que la llegada de clientes es a tasa λ > 0 y que los tiempos de atenci´on
tienen distribuci´on uniforme en el intervalo [a, b], con 0 < a < b. Determine el valor de las medidas de desempe˜no Lq
y W para este sistema.
i) (3 pts.) Considere un sistema M/M/1 con tasa de llegada λ y tasa de atenci´on µ. Obtenga la proporci´on de clientes
que al terminar de ser atendidos dejan menos de m personas en el sistema, sin contar dicho cliente. Su respuesta
puede quedar en funci´on de probabilidades l´ımite.
Sistema
Probabilidades l´ımite
C´alculo de L
Ec de Little
M/M/1
Pn = λn−1 · . . . · λ0
µn · . . . · µ1
P0
L = P∞
i=0 n · Pn =
λ
µ −λ
L = λe · W

