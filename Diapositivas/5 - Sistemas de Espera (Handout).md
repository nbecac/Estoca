Pontificia Universidad Cat´olica de Chile
Escuela de Ingenier´ıa
Departamento de Ingenier´ıa Industrial y Sistemas
Sistemas de Espera
ICS2123 Modelos Estoc´asticos
Ver´onica Godoy
Andr´es Navarro
ICS2123
Sistemas de Espera
2026-1
1 / 52

Outline
1 Definici´on
2 Modelos Markovianos
3 Modelos no Markovianos
4 Extensiones
ICS2123
Sistemas de Espera
2026-1
2 / 52

Definici´on
Outline
1 Definici´on
2 Modelos Markovianos
3 Modelos no Markovianos
4 Extensiones
ICS2123
Sistemas de Espera
2026-1
3 / 52

Definici´on
Motivaci´on
¿Que tienen en com´un los siguientes sistemas?
●Cajeros autom´aticos
●Check-in aeropuerto
●Locales de votaci´on
●Peajes
●Centrales telef´onicas
●Restaurantes
●Sem´afotos
ICS2123
Sistemas de Espera
2026-1
4 / 52

Definici´on
Motivaci´on
Todos de alguna manera siguen el siguiente formato:
Vemos que esto esta vinculado procesos de distinta ´ındole. Comprender su
funcionamiento es escencial a la hora de crear un sistema eficiente o
querer mejorar uno existente.
ICS2123
Sistemas de Espera
2026-1
5 / 52

Definici´on
Motivaci´on
En la mayor´ıa de los servicios existen personas esperando a ser atendidas.
En estos escenarios las empresas buscan entregar un buen servicio a sus
clientes, donde un servicio lento no es bienvenido.
En este tipo de sistemas existe un trade-off entre la calidad del servicio y
los costos totales, pues muchas veces hay que contratar a una persona que
haga el rol de servidor.
¿C´omo podemos definir cu´antos servidores se necesitan para balancear la
minimizaci´on de costos y la maximizaci´on de la calidad del servicio?
ICS2123
Sistemas de Espera
2026-1
6 / 52

Definici´on
Definici´on
Consideremos un sistema al cual llegan estoc´asticamente clientes a
requerir un servicio. Una vez que llegan, si no hay capacidad de atenci´on
disponible, deben esperar en una cola hasta que sea su turno de ser
atendidos. Una vez que termina la atenci´on, los clientes dejan el sistema.
Modelos de este tipo son los que corresponden a sistemas de espera, y
para ellos nos interesar´a determinar, entre otras cosas, medidas tales como
el n´umero promedio de clientes en el sistema o el tiempo promedio que un
cliente debe esperar en la cola.
Para representar estos modelos, se usa la notaci´on X1/X2/X3/X4, donde:
●X1 corresponde a la distribuci´on de los tiempos entre llegadas.
●X2 corresponde a la distribuci´on de los tiempos de atenci´on.
●X3 corresponde a la cantidad de servidores.
●X4 corresponde a la capacidad del sistema.
ICS2123
Sistemas de Espera
2026-1
7 / 52

Definici´on
Definici´on
Algunas consideraciones:
●Si se omite X4, se asume capacidad infinita para el sistema.
●Usaremos la letra M para representar que la distribuci´on de tiempo
correspondiente es exponencial.
●Usaremos la letra G para representar que la distribuci´on de tiempo
correspondiente es una distribuci´on general (no exponencial).
As´ı, por ejemplo un sistema M/G/c corresponde a un sistema en que:
●Los tiempos entre llegadas tienen distribuci´on exponencial.
●Los tiempos de atenci´on siguen una distribuci´on general.
●Existen c servidores, es decir, se pueden atender hasta c entidades al
mismo tiempo.
●El sistema, y por lo tanto tambi´en la cola, tiene capacidad infinita.
ICS2123
Sistemas de Espera
2026-1
8 / 52

Definici´on
Medidas de desempe˜no
Las principales medidas de desempe˜no que nos interesar´a estudiar son:
●L: n´umero medio de clientes en el sistema.
●Lq: n´umero medio de clientes en la cola.
●W: tiempo medio de permanencia de un cliente en el sistema.
●Wq: tiempo medio de permanencia de un cliente en la cola.
ICS2123
Sistemas de Espera
2026-1
9 / 52

Definici´on
Ecuaci´on de Little
La ecuaci´on de Little es uno de los resultados m´as importante de teor´ıa de
colas. Permite relacionar el n´umero promedio de clientes en el sistema con
el tiempo promedio que permanece un cliente en el sistema.
Sean:
●X(t): n´umero de clientes en el sistema en el instante t (t ≥0).
●Wi: tiempo de permanencia en el sistema del cliente i (i = 1,2,3,...).
●N(t): cantidad de clientes que han llegado en el intervalo [0,t].
ICS2123
Sistemas de Espera
2026-1
10 / 52

Definici´on
Ecuaci´on de Little
ICS2123
Sistemas de Espera
2026-1
11 / 52

Definici´on
Ecuaci´on de Little
El ´area bajo la curva es:
t
∫
0
X(u)du
Entonces, el valor promedio de X(u) en el intervalo [0,t] es:
¯X(t) =
t
∫
0
X(u)
t
du
Pero tambi´en se podr´ıa medir el ´area de forma horizontal.
ICS2123
Sistemas de Espera
2026-1
12 / 52

Definici´on
Ecuaci´on de Little
ICS2123
Sistemas de Espera
2026-1
13 / 52

Definici´on
Ecuaci´on de Little
De este modo, podemos aproximar el ´area bajo la curva como:
t
∫
0
X(u)du ≈
N(t)
∑
i=1
Wi
Esta aproximaci´on mejora en la medida que t crece. Luego, se puede
reescribir el valor promedio de X(t) como:
¯X(t)
=
t
∫
0
X(u)
t
du
≈
N(t)
∑
i=1
Wi
t
=
N(t)
∑
i=1
Wi
N(t) ⋅N(t)
t
ICS2123
Sistemas de Espera
2026-1
14 / 52

Definici´on
Ecuaci´on de Little
⇒¯X(t) =
N(t)
∑
i=1
Wi
N(t) ⋅N(t)
t
●
N(t)
∑
i=1
Wi
N(t) representa el tiempo de permanencia promedio de los
clientes que llegaron en el intervalo [0,t].
●N(t)
t
representa la tasa media de llegada de los clientes que arribaron
en el intervalo [0,t].
Si hacemos t →∞, la aproximaci´on se convierte en igualdad:
lim
t→∞
t
∫
0
X(u)
t
du
´¹¹¹¹¹¹¹¹¹¹¹¹¹¹¹¹¹¹¹¹¹¸¹¹¹¹¹¹¹¹¹¹¹¹¹¹¹¹¹¹¹¹¹¹¶
L
= lim
t→∞
N(t)
∑
i=1
Wi
N(t)
´¹¹¹¹¹¹¹¹¹¹¹¹¹¹¹¹¹¹¸¹¹¹¹¹¹¹¹¹¹¹¹¹¹¹¹¹¹¶
W
⋅lim
t→∞
N(t)
t
´¹¹¹¹¹¹¹¹¹¸¹¹¹¹¹¹¹¹¹¹¶
λe
ICS2123
Sistemas de Espera
2026-1
15 / 52

Definici´on
Ecuaci´on de Little
Ecuaci´on de Little
Para un sistema de espera se cumple la siguiente relaci´on entre el n´umero
medio de entidades en un sistema y el tiempo medio de permanencia de
una entidad en el sistema.
L = λe ⋅W
Donde λe es la tasa media de entrada al sistema.
Esta ecuaci´on se cumple:
●En estado estacionario (largo plazo cuando existe distribuci´on l´ımite).
●Independiente del tipo de proceso de llegada y de atenci´on.
●Independiente de la disciplina de la cola (FIFO, LIFO, etc).
●Independiente de la cantidad de servidores.
ICS2123
Sistemas de Espera
2026-1
16 / 52

Definici´on
Ejercicio
Ejemplo
Si la esperanza de vida en Chile es de 81.5 a˜nos, y la poblaci´on es de
17.760.000, estime la tasa de natalidad en el pa´ıs.
ICS2123
Sistemas de Espera
2026-1
17 / 52

Modelos Markovianos
Outline
1 Definici´on
2 Modelos Markovianos
3 Modelos no Markovianos
4 Extensiones
ICS2123
Sistemas de Espera
2026-1
18 / 52

Modelos Markovianos
Modelos markovianos
Los modelos markovianos (o exponenciales) son aquellos sistemas de
espera en que tanto los tiempos entre llegadas como los tiempos de
atenci´on son v.a. exponenciales (y por lo tanto, sin memoria o
markovianos).
Los modelos que estudiaremos son:
●M/M/1
●M/M/1/K
●M/M/c
●M/M/c/K
ICS2123
Sistemas de Espera
2026-1
19 / 52

Modelos Markovianos
Sistema M/M/1
●Llegadas seg´un un proceso de Poisson a tasa λ
●Tiempos de atenci´on exponenciales con par´ametro µ
●Un servidor
●Capacidad infinita del sistema
Sea X(t) el n´umero de personas en el sistema (servidor + cola) en el
instante t.
Si X(t) = n, com n > 0, entonces se tiene que:
Pn,n+1
=
λ
λ + µ
Pn,n−1
=
µ
λ + µ
Pn,m
=
0
∀m ≠n + 1,n −1
Luego, {X(t),t ≥0} es un proceso de nacimiento y muerte.
ICS2123
Sistemas de Espera
2026-1
20 / 52

Modelos Markovianos
Sistema M/M/1
Recordando conceptos de CMTC, se tiene que la probabilidad de que
X(t) = n es:
Pn =
n
∏
i=1
λi−1
µi
P0 = (λ
µ)
n
P0
Adem´as, se tiene que:
1 =
∞
∑
n=0
Pn =
∞
∑
n=0
(λ
µ)
n
P0
Luego,
P0 =
1
∞
∑
n=0
( λ
µ)
n
ICS2123
Sistemas de Espera
2026-1
21 / 52

Modelos Markovianos
Sistema M/M/1
Como necesitamos que la sumatoria converja, se debe cumplir que λ
µ < 1.
Si esto se cumple, entonces se tiene que:
∞
∑
n=0
(λ
µ)
n
=
1
1 −λ
µ
Por lo que para este tipo de sistemas se cumple que:
P0 =
1
∞
∑
n=0
( λ
µ)
n = 1 −λ
µ
Pn = (λ
µ)
n
(1 −λ
µ)
∀i ∈{1,2,...}
ICS2123
Sistemas de Espera
2026-1
22 / 52

Modelos Markovianos
Ejercicio
Medidas de desempe˜no
Los clientes de un supermercado llegan a la caja de acuerdo a un proceso
de Poisson a tasa λ. Existe una ´unica caja, cuyo tiempo de atenci´on posee
distribuci´on exponencial con tasa µ. Calcule:
1 Cantidad de personas promedio que hay en el sistema.
2 Cantidad de personas promedio que hay en la cola.
3 Cantidad de tiempo promedio que una persona pasa en el
supermercado.
ICS2123
Sistemas de Espera
2026-1
23 / 52

Modelos Markovianos
Ejercicio
Soluci´on:
●Se nos pide L:
L
=
∞
∑
n=0
n ⋅Pn
=
∞
∑
n=0
n(λ
µ)
n
(1 −λ
µ)
=
λ
µ −λ
ICS2123
Sistemas de Espera
2026-1
24 / 52

Modelos Markovianos
Ejercicio
●Se nos pide Lq:
Lq
=
∞
∑
n=1
(n −1) ⋅Pn
=
∞
∑
n=1
n ⋅Pn −
∞
∑
n=1
Pn
=
∞
∑
n=0
n ⋅Pn −(1 −P0)
=
λ
µ −λ −λ
µ
=
λ2
µ(µ −λ)
ICS2123
Sistemas de Espera
2026-1
25 / 52

Modelos Markovianos
Ejercicio
●Se nos pide W. Si se atiende por orden de llegada, y un cliente llega
cuando hay n −1 clientes en la cola y 1 en la caja, entonces debe
esperar a que termine de atenderse al que est´a en la caja, se atiendan
los otros n −1 clientes esperando y que lo atiendan a ´el. Por lo tanto,
el valor esperado de tiempo de espera del cliente que llegar´ıa es
n + 1
µ
. Entonces:
W
=
∞
∑
n=0
n + 1
µ
Pn
=
1
µ ⋅(
∞
∑
n=0
nPn +
∞
∑
n=0
Pn)
=
1
µ ⋅(
λ
µ −λ + 1) =
1
µ −λ
ICS2123
Sistemas de Espera
2026-1
26 / 52

Modelos Markovianos
Ejercicio
●Se nos pide W.
W
=
∞
∑
n=0
n + 1
µ
Pn
=
1
µ ⋅(
∞
∑
n=0
nPn +
∞
∑
n=0
Pn)
=
1
µ ⋅(
λ
µ −λ + 1) =
1
µ −λ
Notar que, si consideramos la ecuaci´on de Little, tendr´ıamos:
W = L
λe
=
λ
µ −λ ⋅1
λ =
1
µ −λ
Se llega al mismo resultado!
ICS2123
Sistemas de Espera
2026-1
27 / 52

Modelos Markovianos
Sistema M/M/1/K
●Llegadas seg´un un proceso de Poisson a tasa λ
●Tiempos de atenci´on exponenciales con par´ametro µ
●Un servidor
●Capacidad finita. Pueden haber m´aximo K entidades en el sistema.
Es decir, es muy parecido al sistema M/M/1, con la diferencia que si una
entidad llega al sistema y est´a lleno, entonces se va. Por lo tanto, la tasa
de entrada efectiva es distinta a la tasa de llegada λ.
λe = λ(1 −PK)
ICS2123
Sistemas de Espera
2026-1
28 / 52

Modelos Markovianos
Sistema M/M/1/K
Adem´as, podemos calcular:
Pn =
n
∏
i=1
λi−1
µi
P0 = (λ
µ)
n
P0
De esta forma, sabiendo que
K
∑
n=0
Pn = 1:
P0 =
1
K
∑
n=0
( λ
µ)
n
Esta sumatoria siempre converge, por lo que podemos reescribir esta
expresi´on como:
K
∑
n=0
(λ
µ)
n
=
1 −( λ
µ)
K+1
1 −λ
µ
⇒P0 =
1 −λ
µ
1 −( λ
µ)
K+1
ICS2123
Sistemas de Espera
2026-1
29 / 52

Modelos Markovianos
Sistema M/M/1/K
¿C´omo ser´ıan las medidas de desempe˜no del sistema completo?
L
=
K
∑
n=0
nPn
=
K
∑
n=0
n(λ
µ)
n ⎛
⎜⎜
⎝
1 −λ
µ
1 −( λ
µ)
K+1
⎞
⎟⎟
⎠
=
⎛
⎝
λ
µ
1 −λ
µ
⎞
⎠
⎛
⎜⎜
⎝
1 −( λ
µ)
K
−K ( λ
µ)
K
+ K ( λ
µ)
K+1
1 −( λ
µ)
K+1
⎞
⎟⎟
⎠
ICS2123
Sistemas de Espera
2026-1
30 / 52

Modelos Markovianos
Sistema M/M/1/K
Ocupamos la ecuaci´on de Little:
W = 1
λe
L
Por lo tanto,
W = ⎛
⎝
λ
µ
1 −λ
µ
⎞
⎠
⎛
⎜⎜⎜
⎝
1 −( λ
µ)
K
−K ( λ
µ)
K
+ K ( λ
µ)
K+1
λ(1 −PK)(1 −( λ
µ)
K+1
)
⎞
⎟⎟⎟
⎠
ICS2123
Sistemas de Espera
2026-1
31 / 52

Modelos Markovianos
Sistema M/M/c
●Llegadas seg´un un proceso de Poisson a tasa λ
●Tiempos de atenci´on exponenciales con par´ametro µ
●c servidores
●Capacidad infinita.
Es decir, es parecido al sistema M/M/1, pero ahora se pueden atender
hasta c entidades al mismo tiempo. Por lo tanto, si en el sistema hay c
entidades o menos, la cola va a ser nula.
La tasa de salida del sistema depender´a de la cantidad de clientes en ese
momento:
µn = { n ⋅µ
si n ≤c
c ⋅µ
si n > c
Entonces:
Pn =
⎧⎪⎪⎪⎪⎪⎨⎪⎪⎪⎪⎪⎩
λn
n!µn P0
si n ≤c
λn
c!cn−cµn P0
si n > c
ICS2123
Sistemas de Espera
2026-1
32 / 52

Modelos Markovianos
Sistema M/M/c
Luego, como
∞
∑
n=0
Pn = 1, se tiene que:
P0 =
1
c
∑
n=0
λn
n!µn +
∞
∑
n=c+1
λn
c!cn−cµn
La primera sumatoria siempre converge, mientras que la segunda sumatoria
converge si λ
cµ < 1. Si esto ´ultimo se cumple, es posible demostrar que:
∞
∑
n=c+1
λn
c!cn−cµn = λc
c!µc ⋅
λ
cµ
1 −λ
cµ
Y por lo tanto:
P0 =
1
c
∑
n=0
λn
n!µn + λc
c!µc ⋅
λ
cµ
1 −λ
cµ
ICS2123
Sistemas de Espera
2026-1
33 / 52

Modelos Markovianos
Sistema M/M/c
Las medidas de desempe˜no de la cola de este sistema son:
Lq =
∞
∑
n=c
(n −c)Pn
Wq = 1
λLq
ICS2123
Sistemas de Espera
2026-1
34 / 52

Modelos Markovianos
Sistema M/M/c
Proposici´on
Para un sistema M/M/c en el que existen las probabilidades l´ımites
(λ < cµ), el proceso de salida del sistema en el largo plazo corresponde a
un proceso de Poisson a tasa λ.
Por el contrario, para un sistema M/M/c en el que no existen las
probabilidades l´ımites (λ ≥cµ), el proceso de salida del sistema en el largo
plazo corresponde a un proceso de Poisson a tasa cµ.
ICS2123
Sistemas de Espera
2026-1
35 / 52

Modelos Markovianos
Sistema M/M/c/K
●Llegadas seg´un un proceso de Poisson a tasa λ
●Tiempos de atenci´on exponenciales con par´ametro µ
●c servidores
●Capacidad finita. Pueden haber m´aximo K entidades en el sistema.
Se debe cumplir que K ≥c para que sea interesante estudiar este sistema
Pn =
⎧⎪⎪⎪⎪⎪⎨⎪⎪⎪⎪⎪⎩
λn
n!µn P0
si n ≤c
λn
c!cn−cµn P0
si c < n ≤K
ICS2123
Sistemas de Espera
2026-1
36 / 52

Modelos Markovianos
Sistema M/M/c/K
Luego, como
K
∑
n=0
Pn = 1, se tiene que:
P0 =
1
c
∑
n=0
λn
n!µn +
K
∑
n=c+1
λn
c!cn−cµn
Ambas sumatorias convergen. Luego, es posible demostrar que:
K
∑
n=c+1
λn
c!cn−cµn = λc
c!µc ⋅λ
cµ ⋅
1 −( λ
cµ)
K−c
1 −λ
cµ
Y por lo tanto:
P0 =
1
c
∑
n=0
λn
n!µn + λc
c!µc ⋅λ
cµ ⋅
1 −( λ
cµ)
K−c
1 −λ
cµ
ICS2123
Sistemas de Espera
2026-1
37 / 52

Modelos Markovianos
Convergencia
Algunas conclusiones sobre la convergencia de los sistemas:
●Sistemas con capacidad infinita →Se requiere que
λ
cµ < 1.
●Sistemas con capacidad finita →No pueden diverger
ICS2123
Sistemas de Espera
2026-1
38 / 52

Modelos Markovianos
Ejercicio propuesto
Sistema Markoviano
Considere un negocio al que llegan clientes de acuerdo a un proceso de
Poisson a tasa λ. Sin embargo, como los clientes no son muy pacientes,
cuando hay n clientes dentro del negocio solo ingresan con probababilidad
1
n+1 cuando hay n. En el negocio hay una ´unica cajera que atiende clientes
seg´un una v.a. exponencial de tasa µ. Finalmente, considere que la
capacidad del negocio es de N personas.
1 Calcule la proporci´on de clientes que no ingresan al local porque est´a
lleno.
2 Calcule la cantidad y tiempo de permanencia promedio de clientes en
el sistema.
ICS2123
Sistemas de Espera
2026-1
39 / 52

Modelos no Markovianos
Outline
1 Definici´on
2 Modelos Markovianos
3 Modelos no Markovianos
4 Extensiones
ICS2123
Sistemas de Espera
2026-1
40 / 52

Modelos no Markovianos
Sistema M/G/1
En la pr´actica, podr´ıa no ser realista modelar los tiempos de atenci´on
utilizando una distribuci´on exponencial.
●El tiempo que lleva un cajero atendiendo a un cliente, ¿influye sobre
el tiempo que le queda atendi´endolo?
●¿Y si es imposible que el tiempo de atenci´on tome menos de 3
minutos?
ICS2123
Sistemas de Espera
2026-1
41 / 52

Modelos no Markovianos
Sistema M/G/1
Sea X(t) la cantidad de personas en el sistema en el instante t. X(t) no
es una CMTC, pero es posible modelarlo como un proceso de renovaci´on:
●Sea Xn la cantidad de clientes que hay en el sistema justo en el
instante de salida de la n-´esima persona.
●Sea Yn+1 la cantidad de personas que llegan durante el servicio del
(n + 1)-´esimo cliente.
Entonces,
Xn+1 = { Xn + Yn+1 −1
si Xn > 0
Yn+1
si Xn = 0
¡Xn es una CMTD! Sus c´alculos son complejos, por lo que solamente
usaremos su valor esperado.
ICS2123
Sistemas de Espera
2026-1
42 / 52

Modelos no Markovianos
Sistema M/G/1
F´ormula de Pollacsek-Khinchin
Sea S el tiempo de servicio. Entonces, la cantidad media de clientes en el
sistema en el largo plazo est´a dada por:
lim
n→∞E(Xn)
´¹¹¹¹¹¹¹¹¹¹¹¹¹¸¹¹¹¹¹¹¹¹¹¹¹¹¹¶
L
= λE(S)
´¹¹¹¸¹¹¹¶
Ls
+
λ2E(S2)
2(1 −λE(S))
´¹¹¹¹¹¹¹¹¹¹¹¹¹¹¹¹¹¸¹¹¹¹¹¹¹¹¹¹¹¹¹¹¹¹¹¶
Lq
ICS2123
Sistemas de Espera
2026-1
43 / 52

Modelos no Markovianos
Sistema G/M/1
Sea X(t) la cantidad de personas en el sistema en el instante t. X(t) no
es una CMTC, pero es posible modelarlo como un proceso de renovaci´on.
Se puede observar el sistema en los instantes de llegada de nuevos clientes.
●Sea Xn la cantidad de clientes que hay en el sistema al ocurrir la
n-´esima llegada.
●Sea Yn+1 la cantidad de personas que se atienden entre la llegada del
n-´esimo y el (n + 1)-´esimo cliente, que distribuye Poisson a tasa µ.
Entonces,
Xn+1 = { Xn −Yn+1 + 1
si Xn −Yn+1 ≥0
1
si Xn −Yn+1 < 0
¡Xn tambi´en es una CMTD! Sin embargo, es este caso no existe una
f´ormula expl´ıcita para la cantidad media de clientes en el sistema.
ICS2123
Sistemas de Espera
2026-1
44 / 52

Modelos no Markovianos
Ejercicio propuesto
Sistema no Markoviano
Afuera de un supermercado hay un juego de ni˜nos con forma de auto
donde los ni˜nos se suben y este se mueve. Los ni˜nos llegan a este juego
seg´un un proceso poisson con tasa α. Al juego se puede subir solo un ni˜no
a la vez y tiene una duraci´on de s minutos (no cambia).
1 Identifique el tipo de sistema de espera que representa esta situaci´on.
2 Encuentre la proporci´on de tiempo en el largo plazo que el juego est´a
ocupado.
3 Encuentre el largo medio de la cola y el tiempo medio de espera en
cola.
ICS2123
Sistemas de Espera
2026-1
45 / 52

Extensiones
Outline
1 Definici´on
2 Modelos Markovianos
3 Modelos no Markovianos
4 Extensiones
ICS2123
Sistemas de Espera
2026-1
46 / 52

Extensiones
LIFO
Considere un sistema M/M/1 con pol´ıtica de atenci´on LIFO.
●Obtenga la probabilidad de que el sistema se encuentre vac´ıo.
●Obtenga el largo promedio de la cola en el largo plazo.
●Obtenga el tiempo de espera medio en la cola en el largo plazo.
Este sistema se puede modelar como una CMTC al igual que si la atenci´on
fuera FIFO.
La cadena quedar´ıa exactamente igual, por lo que la distribuci´on
estacionaria debe ser la misma. Luego, P0 no cambia.
De la misma forma, el largo promedio de la cola o el tiempo de espera
medio en la cola no cambiar´a.
Entonces, ¿importa la pol´ıtica de atenci´on? ¿Cu´al es la diferencia?
¡La variabilidad!
ICS2123
Sistemas de Espera
2026-1
47 / 52

Extensiones
Redes de sistemas de espera
¿Qu´e ocurre si una entidad debe pasar por m´as de un servidor en el
sistema?
Llegada
1
2
Salida
λ
El proceso de salida de un sistema condiciona el proceso de entrada a otro
sistema.
Recordemos que en un sistema M/M/c el proceso de salida de un sistema
en el largo plazo es un proceso de Poisson a una tasa que depende de la
tasa de llegada, de la tasa de atenci´on y de la cantidad de servidores.
ICS2123
Sistemas de Espera
2026-1
48 / 52

Extensiones
Redes de sistemas de espera
Ejemplo
Un sistema productivo consiste en dos etapas. En la primera hay c
m´aquinas en paralelo que demoran un tiempo exponencial a tasa µ1 en
procesar los productos, y en la segunda existe una ´unica m´aquina que
demora un tiempo exponencial a tasa µ2 en procesar productos. Si los
productos arriban seg´un un proceso de Poisson a tasa λ:
1 Determine la condici´on de equilibrio del sistema.
2 Calcule el tiempo promedio de proceso de los productos asumiendo
que se cumple la condici´on de equilibrio del sistema.
ICS2123
Sistemas de Espera
2026-1
49 / 52

Extensiones
Redes de sistemas de espera
Soluci´on:
●Condiciones de equilibrio: λ < cµ1 y λ < µ2.
●El tiempo promedio del proceso de un producto estar´a dado por el
tiempo promedio en cada uno de los dos procesos. En cada proceso,
hay que considerar el tiempo de espera y el tiempo de atenci´on.
Sean:
●TEi = Tiempo de espera en el sistema i.
●TSi = Tiempo de servicio en el sistema i.
●P i
n = Distribuci´on estacionaria para el sistema i.
Para calcular TE1, recordamos lo que aparece en las slides anteriores
sobre el sistema M/M/c:
Wq = 1
λLq, con Lq =
∞
∑
n=c
(n −c)P 1
n
ICS2123
Sistemas de Espera
2026-1
50 / 52

Extensiones
Redes de sistemas de espera
Para el segundo sistema, es un M/M/1 con tasa de llegada λ. Por lo
tanto, recordando los resultados del curso:
W =
1
µ2 −λ
Que corresponde al tiempo de espera m´as el tiempo de servicio promedio.
Por lo tanto:
Tiempo de proceso promedio
=
TE1 + TS1 + TE2 + TS2
=
∞
∑
n=c(n −c)P 1
n
λ
+ 1
µ1
+
1
µ2 −λ
ICS2123
Sistemas de Espera
2026-1
51 / 52

Extensiones
Ejercicio propuesto
Servidores en serie
Considere la llegada de personas a un establecimiento para renovar su
carnet de conducir. Las personas llegan seg´un un proceso Poisson con tasa
λ. Cuando llega la persona esta se dirige a la zona donde le toman los
datos y los ingresan al sistema. En esta zona hay 2 personas atendiendo
independientemente con tiempos de atenci´on exponencial con tasa β
(λ < 2β). Una vez que las personas salen de esta zona van a sacarse la
foto del carnet. Hay un solo fot´ografo y demora un tiempo exponencial
con tasa µ en sacar una foto (λ < µ). Despu´es de esto la persona se retira
del establecimiento.
Considere que en ambas zonas de atenci´on son independientes, se atienden
seg´un una pol´ıtica FIFO, tienen filas ´unicas y tienen capacidad infinita.
Calcule el tiempo medio de permanencia y el n´umero medio de clientes en
el sistema.
ICS2123
Sistemas de Espera
2026-1
52 / 52

