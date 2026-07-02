Pontificia Universidad Cat´olica de Chile
Escuela de Ingenier´ıa
Departamento de Ingenier´ıa Industrial y Sistemas
Cadenas de Markov en Tiempo Continuo
ICS2123 Modelos Estoc´asticos
Ver´onica Godoy
Andr´es Navarro
ICS2123
CMTC
2026-1
1 / 34

Outline
1 Definici´on
2 Probabilidades de Transici´on
3 Probabilidades L´ımite
4 Procesos de Nacimiento y Muerte
ICS2123
CMTC
2026-1
2 / 34

Definici´on
Outline
1 Definici´on
2 Probabilidades de Transici´on
3 Probabilidades L´ımite
4 Procesos de Nacimiento y Muerte
ICS2123
CMTC
2026-1
3 / 34

Definici´on
Motivaci´on
¿Por qu´e ocupar Cadenas de Markov en Tiempo Continuo si
siempre se puede discretizar el tiempo?
En algunas ocasiones se necesita una mirada m´as fina del tiempo para
representar correctamente un problema.
Ejemplo: Sea X(t) el n´umero de ampolletas buenas en una f´abrica que
opera 24/7. Si la idea es que siempre haya un n´umero m´ınimo de
ampolletas buenas para poder trabajar.
●¿Qu´e pasa si discretizamos el tiempo?
●Periodos de revisi´on en d´ıas vs horas vs minutos.
●¿C´omo afecta esto a la productividad de la empresa?
ICS2123
CMTC
2026-1
4 / 34

Definici´on
Motivaci´on
Ejemplo: Sea X(t) el n´umero de ambulancias disponibles en un hospital
en el instante t.
●Si t es discreto, ¿qu´e pasa si el avance es por d´ıa?
●¿Qu´e pasa si el avance es por hora?
●¿Qu´e tipo de avance se necesita para que el modelo sirva ante una
emergencia?
ICS2123
CMTC
2026-1
5 / 34

Definici´on
Motivaci´on
Ejemplo de procesos:
●Clientes en la cola de un banco, donde X(t) es el n´umero de clientes
en la cola en el instante t.
●La temperatura interna en un invernadero oscila entre -10oC y 20oC.
Sea X(t) la temperatura del lugar en el tiempo t.
●Un partido de basquetball, donde X(t) indica si el equipo local va
ganando, empatando o perdiendo en el instante t.
●Un computador procesa trabajos de forma simult´anea, con X(t) el
n´umero de trabajos que est´an siendo procesados en el instante t.
ICS2123
CMTC
2026-1
6 / 34

Definici´on
Motivaci´on
¿Qu´e nos interesa de un proceso estoc´astico continuo?
Ejemplo: M´aquina con dos estados X(t) : 1 y 0.
●Probabilidad de que la m´aquina se encuentre funcionando en el
tiempo t.
●Sea W(t) el tiempo de funcionamiento de la m´aquina entre [0,t],
¿cu´al es su valor esperado?
●La proporci´on del tiempo que la m´aquina se encuentra en reparaci´on
en el largo plazo.
●Si se incurre en un costo $c por cada unidad de tiempo que la
m´aquina no funciona, ¿cu´al es el costo de operaci´on en el largo plazo?
ICS2123
CMTC
2026-1
7 / 34

Definici´on
Propiedades B´asicas
Supongamos que tenemos un proceso estoc´astico en tiempo continuo,
{X(t),t ≥0}, cuyo espacio de estados generalmente ser´a el conjunto de
estados enteros no negativos.
Propiedad Markoviana
{X(t),t ≥0} posee la propiedad markoviana si para todo s,t ≥0, todo
entero no negativo i,j, y para todo x(u), 0 ≤u < s,
P (X(t + s) = j∣X(s) = i, X(u) = x(u) ∀u ∈[0,s)) =
P(X(t + s) = j∣X(s) = i)
Interpretaci´on: El futuro depende del pasado solo a trav´es del presente.
ICS2123
CMTC
2026-1
8 / 34

Definici´on
Propiedades B´asicas
Propiedad Estacionaria
El proceso {X(t),t ≥0} posee la propiedad de estacionariedad si
P(X(t + s) = j∣X(s) = i) no depende de s.
Notaci´on:
Pij(t) = P(X(t + s) = j∣X(s) = i)
ICS2123
CMTC
2026-1
9 / 34

Definici´on
Definiciones
Cadena de Markov en tiempo continuo (CMTC)
El proceso {X(t),t ≥0} es una CMTC si cumple la propiedad markoviana
y con la propiedad estacionaria.
Consecuencias propiedad markoviana y estacionaria:
●No importa el tiempo que haya permanecido en un determinado
estado.
P(Ti > s + t∣Ti > s) = P(Ti > t)
∀s,t ≥0,i = 0,1,2...
●El tiempo de permanencia en un estado i (Ti) no tiene memoria, por
lo que tiene que ser exponencial.
ICS2123
CMTC
2026-1
10 / 34

Definici´on
Definiciones
CMTC definici´on alternativa
Una CMTC es un proceso {X(t),t ≥0)} con las siguientes propiedades:
●Cada vez que entra al estado i, el tiempo que permanece en ese
estado antes de efectuar una transici´on a un estado diferente tiene
distribuci´on exponencial con una media 1/vi.
●Cuando el proceso deja el estado i, a continuaci´on entra al estado j
con una probabilidad Pij. La probabilidades Pij deben satisfacer:
Pii = 0 ∀i
∑
j
Pij = 1 ∀i
ICS2123
CMTC
2026-1
11 / 34

Definici´on
Definiciones
Conclusiones importantes:
●Una CMTC es un proceso estoc´astico que se mueve de un estado a
otro de acuerdo a una CMTD.
●Los Pij corresponden a las componentes de la matriz P de transici´on
de la CMTD asociada.
●Los tiempos de permanencia en un estado dado son independientes
con distribuci´on exponencial (la media de los tiempos puede ser
diferentes para distintos estados).
●El pr´oximo estado a visitar (j) es independiente del tiempo que el
proceso permanece en el estado i.
ICS2123
CMTC
2026-1
12 / 34

Probabilidades de Transici´on
Outline
1 Definici´on
2 Probabilidades de Transici´on
3 Probabilidades L´ımite
4 Procesos de Nacimiento y Muerte
ICS2123
CMTC
2026-1
13 / 34

Probabilidades de Transici´on
Matriz de transici´on
Al igual que en las CMTD, podemos construir una matriz con las
probabilidades de transici´on Pij. Sin embargo, para este caso Pii = 0 para
todo i.
P =
⎛
⎜⎜⎜
⎝
1
2
3
⋯
1
0
P12
P13
...
2
P21
0
P23
...
3
P31
P32
0
...
⋮
⋮
⋮
⋮
⎞
⎟⎟⎟
⎠
ICS2123
CMTC
2026-1
14 / 34

Probabilidades de Transici´on
Probabilidades de transici´on
Definici´on
Considere una CMTC. Se llama probabilidad de transici´on, Pij(t), a la
probabilidad de que el proceso, dado que ahora est´a en el estado i, en t
unidades de tiempo m´as est´e en el estado j.
Pij(t) = P(X(t + s) = j∣X(s) = i)
∀i,j
∀s,t ≥0
Ecuaci´on Chapman-Kolmogorov
Para todo 0 ≤s < t se tiene que:
Pij(t) =
∞
∑
k=0
Pik(s) ⋅Pkj(t −s)
ICS2123
CMTC
2026-1
15 / 34

Probabilidades de Transici´on
Probabilidades de transici´on
Definici´on
Se denomina tasa de transici´on instant´anea, qij, a la tasa a la cual el
proceso realiza una transici´on del estado i al estado j. Esta tasa est´a dada
por:
qij = vi ⋅Pij
Como vi corresponde a la tasa a la cual el proceso realiza una transici´on
cuando se encuentra en el estado i, y Pij corresponde a la probabilidad de
que esta transici´on sea al estado j, entonces qij corresponde a la tasa a la
cual el proceso realiza una transici´on del estado i al estado j, estando en i.
Las tasas de transici´on instant´aneas determinan los par´ametros de una
CMTC.
Pij = qij
vi
=
qij
∑j qij
ICS2123
CMTC
2026-1
16 / 34

Probabilidades de Transici´on
Ejemplos
Ejemplo
Considere una peluquer´ıa que posee dos peluqueros y un espacio de espera
de a lo m´as 5 personas. La llegada de las personas sigue un Proceso de
Poisson con tasa λ personas por hora. Los tiempos de atenciones de los
peluqueros son iid con distribuci´on exponencial µ personas por hora. Los
tiempos de atenci´on y de llegada son independientes entre s´ı. Finalmente,
si llega alguien y no puede entrar a la peluquer´ıa este simplemente se va.
Considere que X(t) es el n´umero de personas en la peluquer´ıa en el
tiempo t. Modele esto como una CMTC identificando el conjunto de
estados y encontrando todos los qij, vi y Pij.
ICS2123
CMTC
2026-1
17 / 34

Probabilidades de Transici´on
Ejemplos
Soluci´on:
Espacio de estados = {0,1,2,3,4,5,6,7}.
0
1
2
⋯
7
v0 = λ
v1 = λ + µ
vi = λ + 2µ
i = 2,3,4,5,6
v7 = 2µ
Las tasas de transici´on est´an dadas por:
ICS2123
CMTC
2026-1
18 / 34

Probabilidades de Transici´on
Ejemplos
Ejemplo
En una f´abrica existen dos m´aquinas distintas, A y B. Ambas m´aquinas son
utilizadas durante todo el d´ıa, pero presentan fallas de vez en cuando. La
m´aquina A presenta fallas a tasa α, mientras que la m´aquina B lo hace a tasa β.
Cuando las m´aquinas fallan deben ser reparadas por sus respectivos mec´anicos. El
mec´anico A tarda un tiempo que distribuye exponencial de media 1/a en reparar
la m´aquina, en tanto el mec´anico B tarda un tiempo que distribuye exponencial
de media 1/b. Dibuje un grafo con todos los Pij.
ICS2123
CMTC
2026-1
19 / 34

Probabilidades L´ımite
Outline
1 Definici´on
2 Probabilidades de Transici´on
3 Probabilidades L´ımite
4 Procesos de Nacimiento y Muerte
ICS2123
CMTC
2026-1
20 / 34

Probabilidades L´ımite
Distribuci´on del proceso en el largo plazo
Probabilidad l´ımite
Considere la probabilidad de que una CMTC est´e en el estado j despu´es
de un tiempo t, con t →∞. Si esta probabilidad existe y es independiente
del estado inicial se llama probabilidad l´ımite:
Pj = lim
t→∞Pij(t)
En este caso, para t →∞se tiene que cumplir que:
d
dtPij(t) = 0
Obs: En una CMTD se dice que f(n+1) = f(n) cuando hay l´ımite.
ICS2123
CMTC
2026-1
21 / 34

Probabilidades L´ımite
Ecuaci´on de equilibrio
Es posible demostrar que se cumple lo siguiente, conocido como la
ecuaci´on de Kolmogorov:
d
dtPij(t) = ∑
k≠j
vkPik(t)Pkj −vjPij(t)
Tomando l´ımite a ambos lados, obtenemos
0 = ∑
k≠j
vkPkPkj −vjPj →vjPj = ∑
k≠j
vkPkPkj
Ecuaci´on de equilibrio en el largo plazo
Para una CMTC en el largo plazo se cumple que la tasa de salida de un
estado es igual a la suma de las tasas de entrada a ese mismo estado. Es
decir:
vj ⋅Pj = ∑
k≠j
qkj ⋅Pk
j = 1,2,3,...
ICS2123
CMTC
2026-1
22 / 34

Probabilidades L´ımite
Observaciones
Interpretaci´on:
●Si los Pj existen se pueden interpretar como la proporci´on del tiempo
que el proceso se encuentra en el estado j.
●vj ⋅Pj corresponde a la tasa a la cual el proceso deja el estado j en el
largo plazo.
●∑k≠j qkj ⋅Pk corresponde a la tasa a la cual el proceso entra al estado
j en el largo plazo.
Si a estas ecuaciones le agregamos la ecuaci´on
∞
∑
k
Pk = 1, se obtiene un
sistema de ecuaciones que permite calcular las probabilidades l´ımite del
proceso.
ICS2123
CMTC
2026-1
23 / 34

Probabilidades L´ımite
Ejercicios
Ejemplo
Un local limpia zapatos en dos etapas. Cuando un cliente entra al local
pasa primero por la etapa 1, luego por la etapa 2, y luego se va. Los
tiempos de servicio de ambas etapas son independientes con distribuci´on
exponencial de tasas µ1 y µ2 respectivamente. Potenciales clientes llegan
seg´un un Proceso Poisson de tasa λ que es independiente de los tiempos
de servicio de ambas etapas, pero estos solo entran al local si no hay otro
cliente.
1 Modele esta situaci´on como una CMTC identificando los qij, vi y Pij
2 Si es posible, encuentre la proporci´on de tiempo que se permanece en
el largo plazo en cada uno de los estados.
3 En particular, ¿cu´al es la proporci´on de tiempo que el local est´a vac´ıo
en el largo plazo si la etapa 1 toma en promedio 2 minutos, la etapa 2
toma en promedio 1 minutos y en promedio arriba un cliente cada 5
minutos?
ICS2123
CMTC
2026-1
24 / 34

Probabilidades L´ımite
Ejercicios
Soluci´on:
Espacio de estados = {0,1,2}, en donde:
●0: el local est´a vac´ıo.
●1: hay una persona en la etapa 1.
●2: hay una persona en la etapa 2.
0
1
2
λ
µ1
µ2
Los qij est´an en el grafo.
P01 = P12 = P20 = 1
ICS2123
CMTC
2026-1
25 / 34

Probabilidades L´ımite
Ejercicios
Para calcular la proporci´on en el largo plazo:
λP0
=
µ2P2
µ1P1
=
λP0
µ2P2
=
µ1P1
∑
i
Pi
=
1
P0 =
µ1µ2
µ1µ2 + λµ1 + λµ2
P1 =
λµ2
µ1µ2 + λµ1 + λµ2
P2 =
λµ1
µ1µ2 + λµ1 + λµ2
Por lo tanto, en particular, se est´a con el local vac´ıo en un 62,5% del
tiempo total.
ICS2123
CMTC
2026-1
26 / 34

Procesos de Nacimiento y Muerte
Outline
1 Definici´on
2 Probabilidades de Transici´on
3 Probabilidades L´ımite
4 Procesos de Nacimiento y Muerte
ICS2123
CMTC
2026-1
27 / 34

Procesos de Nacimiento y Muerte
Definici´on y caracterizaci´on
Proceso de nacimiento y muerte
Un proceso de nacimiento y muerte es una CMTC con estados
{0,1,2,...} para el cual las transiciones desde el estado i s´olo pueden ser
al estado i −1 o al estado i + 1.
0
1
2
⋯
λ0
µ1
λ1
µ2
λ2
µ3
ICS2123
CMTC
2026-1
28 / 34

Procesos de Nacimiento y Muerte
Probabilidades l´ımites para Nacimiento y Muerte
Dado X(t) = j tendremos:
●Tiempo hasta el siguiente nacimiento: ∼exp(λj)
●Tiempo hasta la siguiente muerte : ∼exp(µj)
Luego,
v0 = λ0
vj = λj + µj
j = 1,2,3,...
P01 = 1
Pj,j+1 =
λj
λj + µj
j = 1,2,3,...
Pj,j−1 =
µj
λj + µj
j = 1,2,3,...
ICS2123
CMTC
2026-1
29 / 34

Procesos de Nacimiento y Muerte
Probabilidades l´ımites para Nacimiento y Muerte
Reemplazando en las ecuaciones de equilibrio:
(λj + µj)Pj = λj−1Pj−1 + µj+1Pj+1
Es decir, para cada j, esta ecuaci´on ser´ıa:
λ0P0 = µ1P1
(λ1 + µ1)P1 = λ0P0 + µ2P2
(λ2 + µ2)P2 = λ1P1 + µ3P3
⋮
(λn + µn)Pn = λn−1Pn−1 + µn+1Pn+1
ICS2123
CMTC
2026-1
30 / 34

Procesos de Nacimiento y Muerte
Probabilidades l´ımites para Nacimiento y Muerte
Sumando estas n + 1 ecuaciones:
λnPn = µn+1Pn+1
⇒
Pn+1 = λn
µn+1
Pn
Realizando el mismo c´alculo recursivo, se obtiene la siguiente expresi´on:
Pn = P0
λn−1λn−2...λ0
µnµn−1...µ1
= P0
n
∏
i=1
λi−1
µi
j = 1,2,3,...
ICS2123
CMTC
2026-1
31 / 34

Procesos de Nacimiento y Muerte
Probabilidades l´ımites para Nacimiento y Muerte
Adem´as se debe cumplir que:
∞
∑
n=0
Pn = 1
P0 + P0
∞
∑
n=1
k
∏
i=1
λi−1
µi
= 1
⇒P0 =
1
1 +
∞
∑
n=1
n
∏
i=1
λi−1
µi
Para que estas probabilidades l´ımites existan, es necesario y suficiente que:
∞
∑
n=1
n
∏
i=1
λi−1
µi
< ∞
ICS2123
CMTC
2026-1
32 / 34

Procesos de Nacimiento y Muerte
Ejercicio
Ejemplo
Suponga que a un banco llegan personas seg´un un proceso Poisson con
tasa λ. El banco cuenta con 4 cajas que atienden de forma simult´anea,
cada una con una tasa de atenci´on µ. Considere que el banco tiene
capacidad infinita y existe una ´unica fila. Determine la proporci´on de
tiempo en el largo plazo que el banco est´a vac´ıo.
ICS2123
CMTC
2026-1
33 / 34

Procesos de Nacimiento y Muerte
Ejercicio
Soluci´on:
Espacio de estados: cantidad de gente en el banco = {0,1,2,...}
0
1
2
3
4
5
⋯
λ
λ
µ
λ
2µ
λ
3µ
λ
4µ
λ
4µ
4µ
P0 =
1
1 +
4
∑
n=1
1
n! ( λ
µ)
n
+ 1
24
∞
∑
n=5
1
4n−4 ( λ
µ)
n
ICS2123
CMTC
2026-1
34 / 34

