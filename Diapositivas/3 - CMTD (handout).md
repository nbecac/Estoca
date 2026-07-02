Pontificia Universidad Cat´olica de Chile
Escuela de Ingenier´ıa
Departamento de Ingenier´ıa Industrial y Sistemas
Cadenas de Markov en Tiempo Discreto
ICS2123 Modelos Estoc´asticos
Ver´onica Godoy
Andr´es Navarro
ICS2123
CMTD
2026-1
1 / 64

Outline
1 Motivaci´on
2 CMTD y sus propiedades
3 Visitas entre estados
4 Clasificaci´on de estados
5 Largo plazo
6 Distribuci´on L´ımite y Distribuci´on Estacionaria
ICS2123
CMTD
2026-1
2 / 64

Motivaci´on
Outline
1 Motivaci´on
2 CMTD y sus propiedades
3 Visitas entre estados
4 Clasificaci´on de estados
5 Largo plazo
6 Distribuci´on L´ımite y Distribuci´on Estacionaria
ICS2123
CMTD
2026-1
3 / 64

Motivaci´on
Motivaci´on
Ejemplo: Sistema de inventario
Una tienda que vende computadores de lunes a viernes ocupa la siguiente
pol´ıtica de inventario:
●Revisa su inventario al final del d´ıa viernes
●Si el inventario es menor que s, entonces pone una orden para que la
cantidad de computadores llegue a S, la cual llega el lunes justo antes
de abrir la tienda.
●Si el inventario es mayor o igual a s, no se hace nada.
La demanda semanal de computadores se comporta como una variable
aleatoria con distribuci´on Poisson de media λ computadores.
ICS2123
CMTD
2026-1
4 / 64

Motivaci´on
Motivaci´on
Sean:
●Xn: Cantidad de computadores en inventario al inicio de la semana
n ∈N.
●Dn: Demanda de computadores en la semana n ∈N.
Como Xn depende de la demanda semanal, Xn y Dn son variables
aleatorias.
¿C´omo se relaciona Xn+1 con Xn?
Xn+1 = { Xn −Dn
si Xn −Dn ≥s
S
si Xn −Dn < s
Xn+1 depende de Xn, Xn depende de Xn−1,...
ICS2123
CMTD
2026-1
5 / 64

CMTD y sus propiedades
Outline
1 Motivaci´on
2 CMTD y sus propiedades
3 Visitas entre estados
4 Clasificaci´on de estados
5 Largo plazo
6 Distribuci´on L´ımite y Distribuci´on Estacionaria
ICS2123
CMTD
2026-1
6 / 64

CMTD y sus propiedades
Propiedad Markoviana
Propiedad Markoviana
Sea {Xn,n = 0,1,2,...} un proceso estoc´astico. Se dice que el proceso
cumple la propiedad markoviana si:
P(Xn+1 = j∣Xn = i,Xn−1 = in−1,...,X0 = i0) = P(Xn+1 = j∣Xn = i)
Para todo j,i,in−1,...,i0 en el conjunto de estados posibles de Xn.
Una interpretaci´on que se puede dar a la propiedad markoviana es que el
futuro depende del pasado solo a trav´es del presente.
O equivalentemente, el estado futuro solo depende del estado actual y no
de c´omo se lleg´o a ´el.
ICS2123
CMTD
2026-1
7 / 64

CMTD y sus propiedades
Propiedad Estacionaria
Propiedad Estacionaria
Sea {Xn,n = 0,1,2,...} un proceso estoc´astico. Se dice que el proceso
cumple la propiedad estacionaria si la probabilidad P(Xn+1 = j∣Xn = i)
depende solo de i y j, y no de n (para todo i,j en el conjunto de estados
posibles de Xn, y para todo n = 0,1,2,...).
●Es decir, la probabilidad depende del estado actual y el estado al que
se quiere llegar, pero no depende de la etapa en que ocurra.
●Debido a esto, se puede usar la siguiente notaci´on:
Pij = P(Xn+1 = j∣Xn = i)
Importante
En adelante y sin p´erdida de generalidad, asumiendo que el conjunto de
estados es contable, usaremos a los enteros no negativos como el conjunto
de estados. Es decir: Xn ∈{0,1,2,...}.
ICS2123
CMTD
2026-1
8 / 64

CMTD y sus propiedades
Cadenas de Markov en tiempo discreto (CMTD)
Definici´on CMTD
El proceso estoc´astico {Xn,n = 0,1,2,...} es una Cadena de Markov en
tiempo discreto si cumple la propiedad markoviana y la propiedad
estacionaria.
Definici´on alternativa CMTD
Una CMTD es un proceso estoc´astico {Xn,n = 0,1,2,...} que toma
valores denominados estados, donde Xn = i significa que el sistema se
encuentra en el estado i en la etapa n.
Adem´as, la probabilidad de pasar del estado i al estado j es constante y
est´a dada por:
Pij = P(Xn+1 = j∣Xn = i,Xn−1 = in−1,...,X0 = i0)
∀n ≥0
ICS2123
CMTD
2026-1
9 / 64

CMTD y sus propiedades
Probabilidad de transici´on en una etapa
Probabilidad de transici´on
En una CMTD la probabilidad de transici´on se define como:
Pij = P(Xn+1 = j∣Xn = i)
∀n ≥0
Y corresponde a la probabilidad de que, si el proceso est´a en el estado i,
en la pr´oxima etapa est´e en el estado j.
Se cumple que:
●Pij ≥0
∀i,j
●∑∞
j=0 Pij = 1
∀i
ICS2123
CMTD
2026-1
10 / 64

CMTD y sus propiedades
Matriz de transici´on en un etapa
Matriz de transici´on
Denominaremos P la matriz de transici´on en una etapa.
P =
⎛
⎜⎜⎜⎜⎜⎜
⎝
P00
P01
...
P0j
...
P10
P11
...
P1j
...
⋮
⋮
⋱
⋮
Pi0
Pi1
...
Pij
...
⋮
⋮
⋱
⋮
⎞
⎟⎟⎟⎟⎟⎟
⎠
●Para cada fila i de P, su suma debe ser igual a 1.
●La suma de las columnas no necesariamente es igual a 1.
ICS2123
CMTD
2026-1
11 / 64

CMTD y sus propiedades
Probabilidad de transici´on en n etapas
Probabilidad de transici´on en n etapas
En una CMTD la probabilidad de transici´on en n etapas est´a dada por:
P (n)
ij
= P(Xm+n = j∣Xm = i)
Para todo m,n ≥0
●Corresponde a la probabilidad de que el proceso est´e en el estado j en
n etapas m´as, dado que ahora est´a en el estado i.
●Note que P (1)
ij
= Pij.
ICS2123
CMTD
2026-1
12 / 64

CMTD y sus propiedades
Ecuaci´on de Chapman-Kolmogorov
Ecuaci´on de Chapman-Kolmogorov
Se cumple que:
P (n)
ij
=
∞
∑
k=0
P (m)
ik
⋅P (n−m)
kj
∀n,m ≥0; m < n; ∀i,j
Lo que nos permite calcular probabilidades de transici´on en n etapas.
Demostraci´on:
P (n)
ij
=
P(Xn = j∣X0 = i)
=
∞
∑
k=0
P(Xn = j∣Xm = k,X0 = i) ⋅P(Xm = k∣X0 = i)
=
∞
∑
k=0
P (n−m)
kj
⋅P (m)
ik
ICS2123
CMTD
2026-1
13 / 64

CMTD y sus propiedades
Matriz de transici´on en n etapas
Definici´on
Denominaremos P (n) a la matriz de transici´on en n etapas. Esta matriz
est´a formada con los P (n)
ij
de la CMTD.
Proposici´on
Se tiene que: P (n) = P n
Demostraci´on: Gracias a las ecuaciones de Chapman-Kolmogorov,
podemos escribir:
P (n) = P (m) ⋅P (n−m)
En particular, se tiene que:
P (2) = P (1+1) = P (1) ⋅P (1) = P ⋅P = P 2
Luego, usando inducci´on:
P (n) = P (n−1+1) = P (n−1) ⋅P (1) = P n−1 ⋅P = P n
ICS2123
CMTD
2026-1
14 / 64

CMTD y sus propiedades
Distribuci´on de probabilidades del proceso
Sea {Xn,n = 0,1,2...} una CMTD con un espacio de estados dados por
{0,1,2,...,r}, en donde se conoce la distribuci´on inicial del proceso,
denotado por f(0) y que corresponde a:
f(0) =
⎛
⎜⎜⎜
⎝
P(X0 = 0)
P(X0 = 1)
⋮
P(X0 = r)
⎞
⎟⎟⎟
⎠
De la misma forma, la distribuci´on del proceso en la etapa n
corresponde a:
f(n) =
⎛
⎜⎜⎜
⎝
P(Xn = 0)
P(Xn = 1)
⋮
P(Xn = r)
⎞
⎟⎟⎟
⎠
ICS2123
CMTD
2026-1
15 / 64

CMTD y sus propiedades
Distribuci´on de probabilidades del proceso
Se puede calcular la distribuci´on del proceso en la etapa n sabiendo cu´al es
su distribuci´on inicial:
P(Xn = j)
=
∞
∑
i=0
P(Xn = j∣X0 = i) ⋅P(X0 = i)
=
∞
∑
i=0
P (n)
ij
⋅f(0)
i
⇒f(n) = [P (n)]⊺⋅f(0) = [P n]⊺⋅f(0)
Proposici´on
Sea {Xn,n = 0,1,2...} una CMTD donde se conoce f(0). Se puede
calcular f(n) como:
f(n)⊺= f(0)⊺P n
ICS2123
CMTD
2026-1
16 / 64

CMTD y sus propiedades
CMTD
Ejemplo
Sea P una matriz de probabilidades de transici´on con estados i = 1,2,3.
P =
⎛
⎜
⎝
0.2
0.3
0.5
0.1
0
0.9
0.55
0
0.45
⎞
⎟
⎠
1 Si en alguna etapa me encuentro en el estado 1, ¿Cu´al es la
probabilidad de estar en el estado 3 en la pr´oxima etapa?
2 ¿Cu´al es la probabilidad de ir del estado 2 al 3 en tres etapas?
3 Calcule la matriz de transici´on en dos etapas.
4 Si en la etapa n = 0 la probabilidad de estar en estado 1 es 0.5, en el
estado 2 es 0.4 y en el estado 3 es 0.1. ¿Cu´al es la probabilidad de
estar en el estado 2 en la etapa n = 2?
ICS2123
CMTD
2026-1
17 / 64

CMTD y sus propiedades
Representaci´on gr´afica
Nodos:
●Cada estado se representa por un nodo.
Arcos:
●Un arco representa las probabilidades de transici´on entre distintos
estados.
●Si P(Xn+1 = j∣Xn = i) > 0, entonces existe un arco entre el nodo i
(estado i) y el nodo j (estado j).
●Si P(Xn+1 = j∣Xn = i) = 0, entonces no hay un arco entre el nodo i y
el nodo j.
ICS2123
CMTD
2026-1
18 / 64

CMTD y sus propiedades
Representaci´on gr´afica
Consideremos la matriz de transici´on en una etapa:
P =
⎛
⎜
⎝
0.2
0.3
0.5
0.1
0
0.9
0.55
0
0.45
⎞
⎟
⎠
Podemos representar esto como un grafo:
1
2
3
0.3
0.5
0.2
0.9
0.1
0.55
0.45
ICS2123
CMTD
2026-1
19 / 64

CMTD y sus propiedades
Ejercicio
Falla de m´aquinas
Considere una empresa que ocupa dos m´aquinas id´enticas y que funcionan
de forma independiente.
Si una m´aquina est´a funcionando al inicio del d´ıa n, tiene una probabilidad
p de seguir funcionando al final del d´ıa. Si una m´aquina no est´a
funcionando al inicio del d´ıa, un mec´anico la va a revisar y con probabilidad
q la repara durante al d´ıa. Si no logra repararla, vuelve al d´ıa siguiente.
La probabilidad de reparar una m´aquina en un d´ıa es independiente de la
cantidad de d´ıas que la m´aquina lleva sin funcionar.
Sea Xn la cantidad de m´aquinas funcionando al inicio del d´ıa n:
1 ¿Se puede modelar como una CMTD? Justifique su respuesta.
2 Determine la matriz de probabilidades de transici´on P.
3 ¿C´omo cambia el modelo si el mec´anico solo puede reparar una
m´aquina a la vez?.
ICS2123
CMTD
2026-1
20 / 64

CMTD y sus propiedades
Ejercicio
Pron´ostico del tiempo
Suponga que usted est´a encargado de pronosticar el tiempo y que solo
existen dos posibles estados: Soleado (S) o Nublado (N). Usted sabe que
el estado del tiempo del d´ıa siguiente (ma˜nana) depende del tiempo actual
(hoy) y del d´ıa anterior (ayer), de acuerdo a las siguientes probabilidades:
Ayer
Hoy
Ma˜nana
Probabilidad
S
S
S
0.8
N
S
S
0.6
S
N
S
0.4
N
N
S
0.1
Construya una CMTD que modele el sistema y determine su matriz de
probabilidades de transici´on.
ICS2123
CMTD
2026-1
21 / 64

CMTD y sus propiedades
Ejercicio
Urnas (Propuesto)
3 bolitas blancas y 3 bolitas negras se distribuyen en 2 urnas de modo tal
que cada una tiene 3 bolitas. Decimos que el sistema est´a en estado i si la
primera urna posee i bolitas blancas. En cada etapa, sacamos una bolita
de cada urna y las intercambiamos.
Considere Xn la cantidad de bolitas blancas en la primer urna, en la etapa
n:
1 Se puede modelar como una CMTD? Justifique su respuesta.
2 Encuentre la matriz P.
3 Si inicialmente hay 2 bolitas blancas en la primera urna, calcule el
vector de estados en la segunda etapa.
4 Si no se sabe cu´antas bolitas blancas hay en la primera urna, calcule
el vector de estados en la cuarta etapa.
ICS2123
CMTD
2026-1
22 / 64

Visitas entre estados
Outline
1 Motivaci´on
2 CMTD y sus propiedades
3 Visitas entre estados
4 Clasificaci´on de estados
5 Largo plazo
6 Distribuci´on L´ımite y Distribuci´on Estacionaria
ICS2123
CMTD
2026-1
23 / 64

Visitas entre estados
Visitas a un determinado estado
Definici´on T(i,j)
El tiempo (n´umero de etapas) empleado para ir desde el estado i al estado
j por primera vez est´a dado por:
T(i,j) = inf{n ∶Xn = j,n ≥0}∣X0 = i
Definici´on Fm(i,j)
La probabilidad de ir del estado i al estado j en m etapas, sin haber
pasado por j antes de la etapa m est´a dada por:
Fm(i,j) = P(T(i,j) = m)
ICS2123
CMTD
2026-1
24 / 64

Visitas entre estados
Visitas a un determinado estado
Proposici´on
Se tiene que:
Fm(i,j) = ∑
k≠j
Pik ⋅Fm−1(k,j)
∀k ≥2
Interpretaci´on:
La probabilidad de ir desde i a j (por primera vez) en m etapas es igual a
la probabilidad de ir de i a k en una etapa y luego ir de k a j en las
restantes m −1 etapas (sin visitar j en etapas intermedias).
ICS2123
CMTD
2026-1
25 / 64

Visitas entre estados
Probabilidad de visitar un estado en alg´un momento
Definici´on F(i,j)
La probabilidad de visitar eventualmente el estado j dado que al inicio el
proceso est´a en el estado i se denotar´a F(i,j) y corresponde a:
F(i,j) = ∑
m
Fm(i,j)
Tambi´en se tiene que:
F(i,j) = P(T(i,j) < ∞)
Es decir, es igual a la probabilidad de visitar el estado j en un n´umero
finito de etapas dado que part´ı en el estado i.
Adem´as, la probabilidad de retornar alguna vez al estado i est´a dada por:
F(i,i)
ICS2123
CMTD
2026-1
26 / 64

Visitas entre estados
Probabilidad de visitar un estado en alg´un momento
Proposici´on
Se tiene que:
F(i,j) = Pij + ∑
k≠j
PikF(k,j)
Interpretaci´on:
La probabilidad de visitar el estado j, dado que partimos del estado i, es
igual a la probabilidad de ir de i a j en una etapa m´as la suma de las
probabilidades de ir de i a k (k ≠j) en una etapa y visitar j alguna vez
dado que se parti´o desde k.
ICS2123
CMTD
2026-1
27 / 64

Visitas entre estados
Otros resultados importantes
Si F(i,j) = 1, entonces el valor esperado del n´umero de etapas para ir de i
a j es:
E(T(i,j)) =
∞
∑
m=1
m ⋅Fm(i,j)
ICS2123
CMTD
2026-1
28 / 64

Visitas entre estados
Otros resultados importantes
Otra forma de calcular E(T(i,j)) es:
E(T(i,j))
=
∑
k
E(T(i,j)∣X1 = k)P(X1 = k∣X0 = i)
=
E(T(i,j)∣X1 = j)P(X1 = j∣X0 = i) +
∑
k≠j
E(T(i,j)∣X1 = k)P(X1 = k∣X0 = i)
=
1 ⋅Pij + ∑
k≠j
(1 + E(T(k,j))) ⋅Pik
=
Pij + ∑
k≠j
Pik + ∑
k≠j
E(T(k,j)) ⋅Pik
=
1 + ∑
k≠j
E(T(k,j)) ⋅Pik
Es decir, para obtener el valor esperado de T(i,j), podemos ocupar:
E(T(i,j)) = 1 + ∑
k≠j
Pik ⋅E(T(k,j))
ICS2123
CMTD
2026-1
29 / 64

Visitas entre estados
Ejercicio
Ejemplo
Consideremos la matriz de transici´on P con estados i = 1,2,3 y responda
las siguientes preguntas.
P =
⎛
⎜
⎝
0.4
0.6
0
0.7
0
0.3
0.5
0.5
0
⎞
⎟
⎠
1 Si se parte del estado 2, ¿Cu´al es la probabilidad de llegar por primera
vez al estado 3 en tres etapas?
2 Si se parte del estado 1, ¿Cu´al es la probabilidad de retornar a ´el
alguna vez?
3 Si se parte del estado 3, ¿Cu´al es el tiempo esperado (en etapas) para
visitar el estado 1 por primera vez?
ICS2123
CMTD
2026-1
30 / 64

Clasificaci´on de estados
Outline
1 Motivaci´on
2 CMTD y sus propiedades
3 Visitas entre estados
4 Clasificaci´on de estados
5 Largo plazo
6 Distribuci´on L´ımite y Distribuci´on Estacionaria
ICS2123
CMTD
2026-1
31 / 64

Clasificaci´on de estados
Clasificaci´on de estados
Recurrente
El estado i se denomina recurrente si
F(i,i) = P(T(i,i) < ∞) = 1
Adem´as se tiene que:
●Si E(T(i,i)) = ∞, i se denomina recurrente nulo.
●Si E(T(i,i)) < ∞, i se denomina recurrente positivo.
Transiente
El estado i se denomina transiente si
F(i,i) = P(T(i,i) < ∞) < 1
ICS2123
CMTD
2026-1
32 / 64

Clasificaci´on de estados
Comunicaci´on entre estados
Definici´on
Decimos que los estados i y j se comunican si hay un camino (en el grafo)
para ir de de i a j y un camino para ir de j a i. Lo denotaremos por i ↔j.
Propiedades de Comunicaci´on
La relaci´on de comunicaci´on satisface estas tres propiedades:
●Reflexi´on: i ↔i para todo estado i
●Simetr´ıa: i ↔j si y s´olo si j ↔i
●Transitividad: Si i ↔k y k ↔j, entonces i ↔j
Es decir, la relaci´on de comunicaci´on es una relaci´on de equivalencia.
ICS2123
CMTD
2026-1
33 / 64

Clasificaci´on de estados
Comunicaci´on entre estados
La relaci´on de comunicaci´on define clases. Decimos que dos estados
pertenecen a la misma clase si estos se comunican.
Proposici´on
Las clases constituyen una partici´on del conjunto de todos los estados.
Proposici´on
Todos los estados de una clase son del mismo tipo: transientes,
recurrentes nulos o recurrentes positivos.
ICS2123
CMTD
2026-1
34 / 64

Clasificaci´on de estados
Comunicaci´on entre estados
Proposici´on
Las clases de estados recurrentes son cerradas, es decir, si el sistema parte
de un estado dentro de esa clase nunca sale.
Proposici´on
Si una CMTD posee una cantidad de estados finita, luego:
●No pueden existir estados recurrentes nulos
●No pueden ser todos los estados transientes
ICS2123
CMTD
2026-1
35 / 64

Clasificaci´on de estados
Periodicidad
Definici´on
Un estado es peri´odico si partiendo desde ese estado s´olo es posible volver
a ´el en un n´umero de etapas que sea m´ultiplo de un n´umero entero mayor
a uno.
El per´ıodo, d, de un estado j corresponde al m´aximo com´un divisor de los
n para los que P (n)
jj
> 0.
●Si d > 1, diremos que el estado es peri´odico con per´ıodo d.
●Si d = 1, diremos que el estado es aperi´odico.
ICS2123
CMTD
2026-1
36 / 64

Clasificaci´on de estados
Ejercicio
Ejemplo
Considere la siguiente matriz de transici´on para una CMTD.
P =
⎛
⎜⎜⎜⎜⎜⎜⎜⎜⎜⎜
⎝
0.9
0
0
0
0.1
0
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
0.7
0.2
0
0
0
0
0
0
0
1
0
0
0.5
0
0
0
0.5
0
0
0
0
0
1
0
0
1
0
0
0
0
0
⎞
⎟⎟⎟⎟⎟⎟⎟⎟⎟⎟
⎠
Clasifique todos los estados e indique si tienen periodo o no.
ICS2123
CMTD
2026-1
37 / 64

Largo plazo
Outline
1 Motivaci´on
2 CMTD y sus propiedades
3 Visitas entre estados
4 Clasificaci´on de estados
5 Largo plazo
6 Distribuci´on L´ımite y Distribuci´on Estacionaria
ICS2123
CMTD
2026-1
38 / 64

Largo plazo
Evoluci´on del proceso en el largo plazo
¿Qu´e ocurre con la distribuci´on del proceso de una CMTD cuando
n tiende a infinito?
Si los l´ımites existen se tiene que:
lim
n→∞f(n) = lim
n→∞(P n)⊺f(0)
Pero, ¿convergen los elementos de la matriz?. Estudiaremos:
lim
n→∞P (n)
ij
Si el l´ımite existe, entonces se puede interpretar como la probabilidad de
que, si parto en el estado i y observo el proceso por un largo tiempo, el
nuevo estado observado sea j.
ICS2123
CMTD
2026-1
39 / 64

Largo plazo
L´ımite de probabilidades de transici´on en n etapas
Separaremos el estudio en varios casos:
●Si j es recurrente nulo o transiente.
lim
n→∞P (n)
ij
= 0
●Si j es recurrente positivo.
●Si j es aperi´odico
●Si i = j.
lim
n→∞P (n)
ij
= lim
n→∞P (n)
jj
=
1
E(T(j, j))
●Si i ≠j
lim
n→∞P (n)
ij
=
F(i, j)
E(T(j, j))
ICS2123
CMTD
2026-1
40 / 64

Largo plazo
L´ımite de probabilidades de transici´on en n etapas
●Si j es recurrente positivo. (continuaci´on)
●Si j es peri´odico con periodo d
●Si i = j.
lim
n→∞P (nd)
ij
= lim
n→∞P (nd)
jj
=
d
E(T(j, j))
lim
n→∞P (nd+m)
ij
= lim
n→∞P (nd+m)
jj
= 0
m = 1, 2, ⋯, d −1
●Si i ≠j e i pertenece a la misma clase que j.
lim
n→∞P (n0+nd)
ij
=
d
E(T(j, j))
lim
n→∞P (n0+nd+m)
ij
= 0
m = 1, 2, ⋯, d −1
Donde n0 es el m´ınimo n´umero de etapas para ir de i a j.
ICS2123
CMTD
2026-1
41 / 64

Largo plazo
L´ımite de probabilidades de transici´on en n etapas
●Si j es recurrente positivo. (continuaci´on)
●Si j es peri´odico con periodo d (continuaci´on)
●Si i ≠j e i pertenece una clase recurrente distinta.
lim
n→∞P (n)
ij
= 0
●Si i ≠j e i pertenece una clase transiente.
lim
n→∞P (n)
ij
= ... depende de la estructura de la cadena
Demostraci´on: Modeling and Analysis of Stochastic Systems - V. G. Kulkarni
(Cap´ıtulo 4.5, Segunda edici´on)
ICS2123
CMTD
2026-1
42 / 64

Largo plazo
L´ımite de probabilidades de transici´on en n etapas
Proposici´on
Si en una CMTD existe al menos una clase recurrente positiva peri´odica,
entonces no existen todos los limn→∞P (n)
ij .
Si en una CMTD no existe una clase recurrente positiva peri´odica,
entonces existen todos los limn→∞P (n)
ij .
ICS2123
CMTD
2026-1
43 / 64

Largo plazo
Ejemplos
Ejemplo
Considere una CMTD con matriz de transici´on P. Encuentre todos los
limn→∞P (n)
ij .
P =
(
1
2
1
0
1
2
1
0)
Soluci´on:
Como la CMTD tiene una sola clase recurrente con periodo 2, no existen
los l´ımites.
ICS2123
CMTD
2026-1
44 / 64

Largo plazo
Ejemplos
Ejemplo
Considere una CMTD con matriz de transici´on P.
P =
(
1
2
1
0.1
0.9
2
0.8
0.2)
Calcule limn→∞P (n)
11
y limn→∞P (n)
22
Soluci´on:
P 2 = (0.73
0.27
0.24
0.76)
P 10 = (0.49
0.51
0.46
0.54)
P 100 = (0.47
0.53
0.47
0.53)
ICS2123
CMTD
2026-1
45 / 64

Distribuci´on L´ımite y Distribuci´on Estacionaria
Outline
1 Motivaci´on
2 CMTD y sus propiedades
3 Visitas entre estados
4 Clasificaci´on de estados
5 Largo plazo
6 Distribuci´on L´ımite y Distribuci´on Estacionaria
ICS2123
CMTD
2026-1
46 / 64

Distribuci´on L´ımite y Distribuci´on Estacionaria
Distribuci´on l´ımite
Si existen todos los l´ımites para las probabilidades de transici´on en n
etapas y estos l´ımites no dependen del estado inicial, entonces el proceso
tiene distribuci´on de probabilidades l´ımite. Es decir, se cumple que:
lim
n→∞P (n)
ij
= lim
n→∞P(Xn = j)
Distribuci´on estacionaria
La soluci´on del siguiente sistema se denomina distribuci´on de
probabilidades estacionaria:
π⊺
=
π⊺P
∑
i
πi
=
1
πi
≥
0
∀i
ICS2123
CMTD
2026-1
47 / 64

Distribuci´on L´ımite y Distribuci´on Estacionaria
Algunos resultados importantes
Proposici´on
Si una CMTD tiene distribuci´on l´ımite y distribuci´on estacionaria, entonces
ambas coinciden. En este caso, la distirbuci´on del proceso en el largo plazo
π viene dada por:
πj = lim
n→∞P(Xn = j) = lim
n→∞P (n)
ij
∀j
Interpretaci´on: La probabilidad l´ımite de que el proceso se encuentre en
el estado j en un tiempo n (n →∞) es igual a la proporci´on de tiempo, en
el largo plazo, que el proceso estar´a en el estado j (probabilidad
estacionaria).
ICS2123
CMTD
2026-1
48 / 64

Distribuci´on L´ımite y Distribuci´on Estacionaria
Algunos resultados importantes
Definici´on
Una CMTD es irreducible cuando tiene finitos estados y todos sus estados
se comunican. Por lo tanto, una CMTD irreducible consiste de una ´unica
clase recurrente positiva.
Proposici´on
Si una CMTD irreducible y aperi´odica, entonces el proceso tiene
distribuci´on l´ımite y distribuci´on estacionaria (las cuales coinciden).
ICS2123
CMTD
2026-1
49 / 64

Distribuci´on L´ımite y Distribuci´on Estacionaria
Algunos resultados importantes
Proposici´on
Considere una CMTD con espacio de estados S = C ∪T, en que C es una
clase de estados recurrentes positivos aperi´odicos y T es un conjunto de
una o m´as clases transientes. Si para cada estado i en T se cumple que:
lim
n→∞P(Xn ∈C∣X0 = i) = 1
entonces la cadena tiene una ´unica distribuci´on estacionaria. Adem´as, se
cumplir´a que πj > 0 para todo j ∈C y πj = 0 para todo j ∈T.
ICS2123
CMTD
2026-1
50 / 64

Distribuci´on L´ımite y Distribuci´on Estacionaria
Ejemplos
Ejemplo
Considere una CMTD con matriz de transici´on dada por:
P = (a
b
c
d)
Considerando que a,b,c,d > 0 y que a + b = 1 y c + d = 1, demuestre que
esta cadena tiene distribuci´on estacionaria.
Hint: Puede usar una de las proposiciones.
ICS2123
CMTD
2026-1
51 / 64

Distribuci´on L´ımite y Distribuci´on Estacionaria
Ejemplos
Ejemplo
Consideremos una CMTD con matriz de transici´on dada por:
P =
⎛
⎜
⎝
1
0
0
0.4
0
0.6
0
1
0
⎞
⎟
⎠
Calcule la distribuci´on estacionaria.
Hint: Puede usar el sistema de ecuaciones visto.
ICS2123
CMTD
2026-1
52 / 64

Distribuci´on L´ımite y Distribuci´on Estacionaria
Problema del inventario
Continuaci´on
Consideremos el problema de inventario que hab´ıamos visto al inicio del
cap´ıtulo. En resumen:
●Tienda vende computadores y atiende de lunes a viernes.
●Para reponer el stock, la tienda utiliza una pol´ıtica (s,S) = (2,5), es
decir:
●Revisa su inventario al final del d´ıa viernes.
●Si el n´umero de computadores es menor a 2, pone una orden para subir
el stock a 5.
●Si el n´umero de computadores es mayor o igual a 2, no se hace nada.
●La demanda semanal es una v.a. Poisson con tasa λ = 3
●La demanda que no puede ser satisfecha se pierde.
ICS2123
CMTD
2026-1
53 / 64

Distribuci´on L´ımite y Distribuci´on Estacionaria
Problema del inventario
Continuaci´on
El problema se hab´ıa modelado de la siguiente forma:
●Xn: Cantidad de computadores en inventario al inicio de la semana n
(n = 0,1,2,...).
●Dn: Demanda de computadores en la semana n (n = 0,1,2,...).
Xn+1 = { Xn −Dn
si Xn −Dn ≥s
S
si Xn −Dn < s
Ahora considere:
●La tienda compra computadores a US$ 1.500 la unidad y los vende a
US$ 1.750.
●Hay un costo de inventario que es proporcional al inventario al inicio
de la semana (constante de proporcionalidad es igual a US$ 50).
Se le pide ahora que modele la matriz P de probabilidades de transici´on.
Adem´as, el due˜no de la tienda le pide a usted que encuentre la utilidad
neta esperada si ocupa la pol´ıtica de inventario propuesta.
ICS2123
CMTD
2026-1
54 / 64

Distribuci´on L´ımite y Distribuci´on Estacionaria
Problema del inventario
Continuaci´on
Soluci´on:
Ocupemos la siguiente notaci´on para definir P:
a(k)
=
P(Dn = k)
A(k)
=
P(Dn > k)
Por lo que la matriz quedar´ıa:
P =
⎛
⎜⎜⎜
⎝
2
3
4
5
2
a(0)
0
0
A(0)
3
a(1)
a(0)
0
A(1)
4
a(2)
a(1)
a(0)
A(2)
5
a(3)
a(2)
a(1)
A(3) + a(0)
⎞
⎟⎟⎟
⎠
ICS2123
CMTD
2026-1
55 / 64

Distribuci´on L´ımite y Distribuci´on Estacionaria
Problema del inventario
Continuaci´on
La utilidad esperada se puede calcular de la siguiente forma:
E(Utilidad) = E(Ingresos) −E(Costos)
En donde los ingresos son las ventas, y los costos est´an representados por
las compras de equipos sumado al costo de inventario.
Consideremos una semana cualquiera n y que Xn = i con i ∈{2,3,4,5}.
Costos esperados de inventario (si Xn = i):
E[Cinventario∣Xn = i] = 50 ⋅i
ICS2123
CMTD
2026-1
56 / 64

Distribuci´on L´ımite y Distribuci´on Estacionaria
Problema del inventario
Continuaci´on
Cantidad esperada de compra (si Xn = i):
●Si el inventario final es 0 (Xn ≤Dn) →compro 5 computadores.
●Si el inventario final es igual a 0 < Xn −Dn < 2 →compro
5 −(i −Dn) computadores.
●Si el inventario final es igual a Xn −Dn ≥2 →compro 0
computadores.
Por lo tanto:
E[Compra∣Xn = i]
=
∞
∑
j=i
5 ⋅P(Dn = j) +
i−1
∑
j=i−1
(5 −(i −j)) ⋅P(Dn = j) +
i−2
∑
j=0
0 ⋅P(Dn = j)
ICS2123
CMTD
2026-1
57 / 64

Distribuci´on L´ımite y Distribuci´on Estacionaria
Problema del inventario
Continuaci´on
Cantidad esperada de venta (si Xn = i):
●Si Dn ≤Xn entonces venta = Dn
●Si Dn > Xn entonces venta = Xn = i
E[V enta∣Xn = i]
=
i
∑
j=0
j ⋅P(Dn = j) +
∞
∑
j=i+1
i ⋅P(Dn = j)
=
i
∑
j=0
j ⋅P(Dn = j) + i ⋅P(Dn ≥i + 1)
ICS2123
CMTD
2026-1
58 / 64

Distribuci´on L´ımite y Distribuci´on Estacionaria
Problema del inventario
Continuaci´on
La utilidad esperada para una semana en que Xn = i es:
U(i)
=
1750 ⋅E[V enta] −1500 ⋅E[Compra] −E[Cinventario]
Entonces, la utilidad esperada para una semana n es:
Un =
5
∑
i=2
U(i) ⋅P(Xn = i) =
5
∑
i=2
U(i) ⋅f(n)
i
Y en el largo plazo, la utilidad esperada por semana es U = ∑5
i=2 U(i) ⋅πi
ICS2123
CMTD
2026-1
59 / 64

Distribuci´on L´ımite y Distribuci´on Estacionaria
Ejercicios propuestos
Problema 1:
Considere una CMTD de 10 estados con matriz de transici´on:
P =
⎛
⎜⎜⎜⎜⎜⎜⎜⎜⎜⎜⎜⎜⎜⎜⎜⎜⎜⎜
⎝
1
2
3
4
5
6
7
8
9
10
1
1/2
0
1/2
0
0
0
0
0
0
0
2
0
1/3
0
0
0
0
2/3
0
0
0
3
1
0
0
0
0
0
0
0
0
0
4
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
5
0
0
0
1/3
1/3
0
0
0
1/3
0
6
0
0
0
0
0
1
0
0
0
0
7
0
0
0
0
0
0
1/4
0
3/4
0
8
0
0
1/4
1/4
0
0
0
1/4
0
1/4
9
0
1
0
0
0
0
0
0
0
0
10
0
1/3
0
0
1/3
0
0
0
0
1/3
⎞
⎟⎟⎟⎟⎟⎟⎟⎟⎟⎟⎟⎟⎟⎟⎟⎟⎟⎟
⎠
ICS2123
CMTD
2026-1
60 / 64

Distribuci´on L´ımite y Distribuci´on Estacionaria
Ejercicios propuestos
Problema 1: (continuaci´on)
●Determine la clase de estados y clasif´ıquelos.
●Demuestre que existen dos estados i y k tal que
limn→∞P (n)
i3
≠limn→∞P (n)
k3
●Suponga que los estados 1,3,6 y 8 se quitan de su cadena. Demuestre
que esta nueva cadena tiene distribuci´on l´ımite y encuentre todos sus
valores.
ICS2123
CMTD
2026-1
61 / 64

Distribuci´on L´ımite y Distribuci´on Estacionaria
Ejercicios propuestos
Problema 2:
En un jard´ın infantil un ni˜no quiere construir una torre de bloques. El ni˜no
cuenta con un total de 10 bloques id´enticos y para hacer la torre coloca
cada bloque encima del otro. Como el ni˜no es peque˜no tiene una cierta
probabilidad de que al poner un bloque la torre se caiga. La probabilidad
de que se caiga la torre depende del n´umero de bloques que lleva puestos,
es decir, si el ni˜no va a poner el i-´esimo bloque la probabilidad de que la
torre se caiga es p(i) = (i −1) ⋅0,05 . Considere que si la torre se cae esto
equivale a tener 1 bloque en la torre. El ni˜no continuara con su juego
hasta que la torre contenga todos los bloques.
Considere que Xn es el n´umero de bloques colocados exitosamente
despu´es de n movimientos. Adem´as considere que en el turno 0 el ni˜no
tiene un bloque en su torre.
ICS2123
CMTD
2026-1
62 / 64

Distribuci´on L´ımite y Distribuci´on Estacionaria
Ejercicios propuestos
Problema 2: (continuaci´on)
1 Utilizando Xn como variable de estados, modele el problema como
una CMTD definiendo el espacio de estados posibles y las
probabilidades de transici´on entre estados.
2 Una parvularia ha visto jugar al ni˜no varias veces y este siempre se
toma un descanso despu´es de haber botado la torre. ¿Cu´al es la
probabilidad de que despu´es de 5o turnos el ni˜no se haya tomado solo
un descanso?
3 La mam´a del ni˜no llega al jard´ın infantil despu´es de un largo tiempo.
En ese tiempo el ni˜no ha hecho un n´umero muy grande de
movimientos (n →∞). ¿Cu´al es la probabilidad de que el ni˜no no
haya terminado la torre? Justifique su respuesta.
ICS2123
CMTD
2026-1
63 / 64

Distribuci´on L´ımite y Distribuci´on Estacionaria
Ejercicios propuestos
Problema 3: En un pasillo de una bodega hay una ampolleta que puede
ser normal o led. Cada noche se revisa si la ampolleta est´a funcionando o
si est´a mala. Si la ampolleta es normal tiene una probabilidad de 0.2 de
fallar, y si es led tiene una probabilidad de 0.1. Cuando la ampolleta falla
el encargado la cambia inmediatamente. Si la ampolleta original es
normal, entonces hay una probabilidad de 0.3 a que la cambia a una led.
Si la ampolleta es led hay una probabilidad de 0.2 que se cambie por una
ampolleta normal.
1 Modele este problema como una CMTD. Identifique claramente el
espacio de estados y las probabilidades de transici´on entre estados.
2 Si hoy la ampolleta est´a buena y es led, ¿cu´al es la probabilidad de
que en 3 d´ıas m´as la ampolleta siga buena y sea led?
3 Calcule la probabilidad de ir de una ampolleta normal y buena a una
led y mala en k (k = 1,2,3,4,5) pasos por primera vez.
4 Calcule el n´umero esperado de noches para que una ampolleta led
mala sea una ampolleta normal mala.
ICS2123
CMTD
2026-1
64 / 64

