Pontificia Universidad Cat´olica de Chile
Escuela de Ingenier´ıa
Departamento de Ingenier´ıa Industrial y Sistemas
Proceso Poisson
ICS2123 Modelos Estoc´asticos
Ver´onica Godoy
Andr´es Navarro
ICS2123
Proceso Poisson
2026-1
1 / 61

Outline
1 Proceso de Conteo
2 Proceso de Poisson
3 Descomposici´on y Suma
4 Extensiones
ICS2123
Proceso Poisson
2026-1
2 / 61

Proceso de Conteo
Outline
1 Proceso de Conteo
2 Proceso de Poisson
3 Descomposici´on y Suma
4 Extensiones
ICS2123
Proceso Poisson
2026-1
3 / 61

Proceso de Conteo
Proceso Estoc´astico
Proceso Estoc´astico
Un proceso estoc´astico es una familia de variables aleatorias Xt (o X(t)),
donde t es un par´ametro que var´ıa de acuerdo a un ´ındice en el conjunto T.
●En muchas ocasiones, el ´ındice t corresponde a unidades discretas de
tiempo, siendo el conjunto T = {0,1,2,3,...}
●En otras, el ´ındice t puede representar el tiempo u otra variable
continua como la distancia desde el origen. En este caso, T = [0,∞[
Entonces, en general:
●{Xt,t = 0,1,2,...} es un Proceso Estoc´astico en tiempo discreto.
●{X(t),t ≥0} es un Proceso Estoc´astico en tiempo continuo.
ICS2123
Proceso Poisson
2026-1
4 / 61

Proceso de Conteo
Proceso Estoc´astico
Realizaci´on o instancia
La realizaci´on o instancia de un proceso estoc´astico corresponde a la
sucesi´on de instancias de las variables aleatorias que resultan de la
“ejecuci´on” del proceso.
Estado transiente y estacionario
●En estado transiente la distribuci´on de probabilidades de las variables
aleatorias var´ıa a trav´es del tiempo.
●En estado estacionario (o de r´egimen) la distribuci´on de
probabilidades de las variables aleatorias es constante a trav´es del
tiempo.
ICS2123
Proceso Poisson
2026-1
5 / 61

Proceso de Conteo
Proceso de Conteo
Proceso de Conteo
{N(t),t ≥0} es un proceso de conteo si N(t) representa la cantidad de
veces que ha ocurrido un evento aleatorio en [0,t].
.
De los siguientes ejemplos ¿cu´ales son procesos de conteo?
●Cantidad de llamadas telef´onicas recibidas
●Cantidad de personas que ha ingresado a un recinto
●Cantidad de personas que hay un recinto
●Cantidad de accidentes de tr´ansito ocurridos en una autopista
●Cantidad de veh´ıculos esperando frente a un sem´aforo en rojo
●Cantidad de l´ıneas telef´onicas ocupadas
ICS2123
Proceso Poisson
2026-1
6 / 61

Proceso de Conteo
Propiedades de los procesos de conteo
Por definici´on N(t) debe satisfacer:
.
●N(t) es siempre entero no negativo
●Si s < t, entonces N(s) ≤N(t) (es no decreciente)
.
Si N(s,t) es el n´umero de eventos en el intervalo ]s,t], entonces: .
●N(s,t) est´a dado por N(t) −N(s)
ICS2123
Proceso Poisson
2026-1
7 / 61

Proceso de Conteo
Propiedades de los procesos de conteo
Incrementos Independientes (i.i)
El proceso de conteo {N(t),t ≥0} tiene incrementos independientes si la
v.a. N(s,s + t) es independiente del proceso {N(u),0 ≤u ≤s} para
cualquier s,t.
.
0
u
s
s + t
Por lo tanto, el n´umero de eventos en intervalos disjuntos son
independientes:
P[N(s,s + t) = k∣N(u) = r] = P[N(s,s + t) = k]
0 ≤u ≤s
ICS2123
Proceso Poisson
2026-1
8 / 61

Proceso de Conteo
Propiedades de los procesos de conteo
Incrementos Estacionarios (i.e)
El proceso de conteo {N(t),t ≥0} tiene incrementos estacionarios si la
distribuci´on de probabilidades de N(s,s + t) no depende de s.
0
r
r + t
s
s + t
t
t
Por lo tanto, la distribuci´on de probabilidades del n´umero de eventos
depende del largo del intervalo y no de su posici´on.
Advertencia
N(r,r + t) ≠N(s,s + t)
∀r ≠s
P[N(r,r + t) = k)] = P[N(s,s + t) = k]
∀r ≠s
∀k
ICS2123
Proceso Poisson
2026-1
9 / 61

Proceso de Conteo
Propiedades de los procesos de conteo
Ejemplo
Sea {N(t),t ≥0} un proceso que cuenta los buses que pasan por un
paradero. Suponga que el tiempo hasta que pasa el primer bus y los
tiempos entre buses sucesivos son variables independientes que distribuyen
Uniforme(10,20) min.
1 ¿Cumple con la propiedad de incrementos independientes?
2 ¿Cumple con la propiedad de incrementos estacionarios?
ICS2123
Proceso Poisson
2026-1
10 / 61

Proceso de Conteo
Propiedades de los procesos de conteo
Funci´on de orden o(h)
Se dice que la funci´on f(⋅) es o(h) si: lim
h→0
f(h)
h
= 0. Es decir, la funci´on
tiende a cero m´as r´apido que su argumento
Propiedad de orden
El proceso {N(t),t > 0} tiene la propiedad de orden si, para alg´un λ > 0,
se cumple que:
P(N(h) = 1)
= λh + o(h)
P(N(h) ≥2)
= o(h)
N(h) ≈{ 0
con probabilidad 1 −λh
1
con probabilidad λh
ICS2123
Proceso Poisson
2026-1
11 / 61

Proceso de Poisson
Outline
1 Proceso de Conteo
2 Proceso de Poisson
3 Descomposici´on y Suma
4 Extensiones
ICS2123
Proceso Poisson
2026-1
12 / 61

Proceso de Poisson
Proceso de Poisson
Proceso de Poisson
El proceso de conteo {N(t),t ≥0} es un Proceso de Poisson con tasa
λ > 0, si:
1 N(0) = 0
2 El proceso tiene incrementos independientes.
3 El proceso tiene incrementos estacionarios.
4 El proceso cumple la propiedad de orden.
Probabilidad de un Proceso de Poisson
Si {N(t),t ≥0} es un Proceso Poisson, entonces se puede demostrar que:
P[N(t) = k)] = (λt)k ⋅e−λt
k!
k = 0,1,2,...
ICS2123
Proceso Poisson
2026-1
13 / 61

Proceso de Poisson
Proceso de Poisson
Ejemplo
Considere {N(t),t ≥0} un Proceso Poisson que cuenta la cantidad de
personas que llegan a una tienda. La tasa de llegada es λ personas por
hora. Calcule:
1 La probabilidad que entre las 2:00 y las 4:00 lleguen 7 personas.
2 La probabilidad que entre las 2:00 y las 4:00 lleguen 7 personas si
entre las 1:00 y las 1:30 llegaron 2 personas.
3 La probabilidad que entre las 2:00 y las 4:00 lleguen 7 personas si
entre las 2:00 y las 2:30 llegaron 3 personas.
4 La probabilidad que entre las 2:00 y las 2:30 lleguen 3 personas si
entre las 2:00 y las 4:00 llegaron 7 personas.
ICS2123
Proceso Poisson
2026-1
14 / 61

Proceso de Poisson
Proceso de Poisson
Distribuci´on del tiempo entre eventos
T1
T2
T3
Denotemos:
T1 : Tiempo hasta el primer evento
T2 : Tiempo entre el 1er y 2do evento
Tn : Tiempo entre el (n −1)-´esimo y n-´esimo evento
¿C´omo distribuyen T1,T2,T3,...?
ICS2123
Proceso Poisson
2026-1
15 / 61

Proceso de Poisson
Proceso de Poisson
Distribuci´on del tiempo entre eventos
Estudiemos T1:
P(T1 ≤x) = 1 −P(T1 > x) = 1 −P[N(x) = 0] = 1 −e−λx
x ≥0
Ahora veamos T2:
P(T2 ≤x)
=
1 −P(T2 > x)
=
1 −∫
∞
0
P[N(y,y + x) = 0∣T1 = y]fT1(y)dy
=
1 −∫
∞
0
P[N(y,y + x) = 0]fT1(y)dy
=
1 −∫
∞
0
P[N(x) = 0]fT1(y)dy
=
1 −P[N(x) = 0]
=
1 −e−λx
ICS2123
Proceso Poisson
2026-1
16 / 61

Proceso de Poisson
Proceso de Poisson
Distribuci´on del tiempo entre eventos
Teorema
En un Proceso de Poisson con tasa λ (λ > 0) los tiempos entre las
ocurrencias de cada evento T1,T2,T3,... son v.a. i.i.d. con distribuci´on
exponencial de par´ametro λ
Resultado Inverso
Sean T1,...,Tn los tiempos entre eventos de un proceso de conteo
{N(t),t > 0}. Si {T1,...,Tn} son v.a. i.i.d. con distribuci´on exponencial
a tasa λ constante, entonces {N(t),t ≥0} es un Proceso de Poisson.
Basta con demostrar que {N(t),t ≥0} satisface la propiedades:
incrementos independientes, incrementos estacionarios y de orden.
Ver Kulkarni, 1999 para detalles.
ICS2123
Proceso Poisson
2026-1
17 / 61

Proceso de Poisson
Propiedad de la distribuci´on exponencial
.
Consideremos una ampolleta que cada vez que falla es reemplazada
instant´aneamente por una ampolleta nueva e id´entica a la anterior. Sea
{N(t),t ≥0} el proceso que cuenta el n´umero de veces que se ha
reemplazado la ampolleta hasta el instante t.
Supongamos que la primera ampolleta que se instal´o lleva funcionando s
unidades de tiempo, ¿cu´anto tiempo m´as funcionar´a la ampolleta?
Sea Y el tiempo adicional de funcionamiento:
¿P(Y ≤x)?
s
Y
T1
ICS2123
Proceso Poisson
2026-1
18 / 61

Proceso de Poisson
Proceso de Poisson
Propiedad de distribuci´on del tiempo entre eventos
P(Y ≤x)
=
1 −P(Y > x)
=
1 −P(T1 > s + x∣T1 > s)
=
1 −P(T1 > s + x,T1 > s)
P(T1 > s)
=
1 −P(T1 > s + x)
P(T1 > s)
=
1 −e−λ(s+x)
e−λs
=
1 −e−λx
Y tambi´en distribuye exponencial y no depende de s. Es decir, no importa
cu´anto tiempo haya pasado antes, la distribuci´on de “lo que falta” seguir´a
siendo la misma. Esta propiedad se llama falta de memoria.
ICS2123
Proceso Poisson
2026-1
19 / 61

Proceso de Poisson
Proceso de Poisson
Ejemplo
Considere {N(t),t ≥0} un Proceso Poisson con tasa λ que cuenta la
cantidad de autos que se suben a un transbordador (ferry). Considere que
el transbordador parte cuando hay M autos dentro de ´el.
1 ¿Cu´al es el tiempo promedio que debe esperar el primer auto, desde
que llega al transbordador hasta que este parte?
2 ¿Cu´al es el tiempo promedio que debe esperar el k−´esimo auto
(k ≤M), desde que llega al transbordador hasta que este parte?
3 Si en el instante u hay n autos sobre el transbordador (n < M), ¿Cu´al
es la probabilidad de que en el instante u + s ya haya partido el
transbordador? (u,s > 0)
ICS2123
Proceso Poisson
2026-1
20 / 61

Proceso de Poisson
Distribuci´on del tiempo de ocurrencia del k-´esimo evento
Definici´on
Llamaremos Sk al instante en que ocurre el k-´esimo (k = 1,2,...) evento
de un Proceso Poisson. Por lo tanto:
Sk = T1 + T2 + ⋅⋅⋅+ Tk
En donde Ti (i = 1,...,k) corresponde al i-´esimo tiempo entre eventos.
Adem´as, Sk es una v.a. con distribuci´on Gamma, con par´ametros k y λ.
FSk(x) = 1 −
k−1
∑
j=0
e−λx (λx)j
j!
ICS2123
Proceso Poisson
2026-1
21 / 61

Proceso de Poisson
Distribuci´on del tiempo de ocurrencia del k-´esimo evento
Gr´aficamente:
T1
T2
T3
S3
ICS2123
Proceso Poisson
2026-1
22 / 61

Proceso de Poisson
Distribuci´on condicional de los tiempos entre eventos
Proposici´on
Si se sabe que en el intervalo [0,t] ocurri´o un solo evento de un Proceso
Poisson, el tiempo de ocurrencia de dicho evento (dentro del intervalo)
tiene una distribuci´on uniforme en [0,t]. Es decir:
P[S1 < x∣N(t) = 1] = x
t
para x ∈[0,t]
ICS2123
Proceso Poisson
2026-1
23 / 61

Proceso de Poisson
Distribuci´on condicional de los tiempos entre eventos
Consideremos un Proceso de Poisson en el que han ocurrido n eventos en
un tiempo t:
●Un observador del proceso anota los tiempos exactos de ocurrencia de
los n eventos (S1,S2,...,Sn) en distintos papeles.
●Introduce los n papeles en una caja y los revuelve.
●Saca un papel al azar de la caja.
.
¿Cu´al es la distribuci´on de probabilidad del tiempo
que aparece anotado en el papel?
ICS2123
Proceso Poisson
2026-1
24 / 61

Proceso de Poisson
Distribuci´on condicional de los tiempos entre eventos
●No sabemos a qu´e elemento corresponde, puede ser el 1°, 2° o el
´ultimo.
●Como el proceso N(t) tiene incrementos estacionarios no se privilegia
ning´un intervalo en particular dentro de [0,t]
●Intuitivamente ese tiempo deber´ıa ser uniforme en [0,t].
ICS2123
Proceso Poisson
2026-1
25 / 61

Proceso de Poisson
Propiedades de un Proceso Poisson
Distribuci´on condicional de los tiempos de evento
Estad´ısticos de Orden
Sean X1,X2,...,Xn v.a. con distribuci´on cualquiera. Supongamos que
observamos estos valores. Sea X(1) = min{X1,X2,...,Xn}
X(2)
=
min({X1,X2,...,Xn} ∖{X(1)})
X(3)
=
min({X1,X2,...,Xn} ∖{X(1),X(2)})
⋮
X(n)
=
max{X1,X2,...,Xn}
Las v.a. X(1),X(2),...,X(n) se denominan estad´ısticos de orden de
X1,X2,...,Xn.
ICS2123
Proceso Poisson
2026-1
26 / 61

Proceso de Poisson
Propiedades de un Proceso Poisson
Distribuci´on condicional de los tiempos de evento
Teorema
Los tiempos S1,...,Sn dado N(t) = n se distribuyen como los estad´ısticos
de orden de n variables aleatorias con distribuci´on Uniforme[0,t].
Corolario
Dado N(t) = n, las variables S1,...,Sn tomadas en forma desordenada
corresponden a variables aleatorias con distribuci´on Uniforme[0,t].
Por lo tanto, si se sabe que en el intervalo [0,t] ocurrieron n eventos, el
tiempo de ocurrencia de un evento cualquiera (sin conocer su orden de
ocurrencia) tiene distribuci´on uniforme en [0,t].
ICS2123
Proceso Poisson
2026-1
27 / 61

Proceso de Poisson
Propiedades de un Proceso Poisson
Distribuci´on condicional de los tiempos de evento
Proposici´on
Sea {N(t),t ≤0} un Proceso Poisson con tasa λ > 0. Entonces, para
0 < u < t y 0 ≤k ≤n se tiene que:
P(N(u) = k∣N(t) = n) =
n!
k!(n −k)! ⋅(u
t )
k
⋅(1 −u
t )
(n−k)
Es decir, la distribuci´on de N(u) dado N(t) = n es Binomial(n,p = u
t )
Nota: Este resultado es tambi´en v´alido para cualquier intervalo de largo t
y subintervalo de largo u contenido en el primero.
ICS2123
Proceso Poisson
2026-1
28 / 61

Proceso de Poisson
Propiedades de un Proceso Poisson
Ejemplo
Un guardia anota los tiempos entre salidas de personas de un recinto y se
da cuenta que son i.i.d. con distribuci´on Exponencial(λ) personas por
hora. El guardia pierde el papel donde anota los tiempos entre salidas,
pero se acuerda que en las primeras cinco horas anot´o 10 salidas.
1 El jefe del guardia le pregunta si alguna persona sali´o del recinto en
las primeras dos horas. ¿Cu´al es la probabilidad de que haya ocurrido
esto?
2 El guardia cree que entre la primera y la tercera hora de toma de
datos salieron 6 personas del recinto. ¿Cu´al es la probabilidad de que
el guardia est´e en lo correcto?
ICS2123
Proceso Poisson
2026-1
29 / 61

Descomposici´on y Suma
Outline
1 Proceso de Conteo
2 Proceso de Poisson
3 Descomposici´on y Suma
4 Extensiones
ICS2123
Proceso Poisson
2026-1
30 / 61

Descomposici´on y Suma
Descomposici´on de Procesos Poisson
M´aquina 1
M´aquina 2
p
1 −p
N(t) ∼Poisson(λ)
N1(t)
N2(t)
A un proceso productivo llegan piezas seg´un un Proceso Poisson con tasa
λ. Cuando llegan las piezas, con probabilidad p pasan a la m´aquina 1 y
con 1 −p a la m´aquina 2. Sean:
N1(t) = N´umero de productos que llegan a la m´aquina 1
N2(t) = N´umero de productos que llegan a la m´aquina 2
ICS2123
Proceso Poisson
2026-1
31 / 61

Descomposici´on y Suma
Descomposici´on de Procesos Poisson
M´aquina 1
M´aquina 2
p
1 −p
N(t) ∼Poisson(λ)
N1(t)
N2(t)
¿Qu´e podemos decir sobre N1(t) y N2(t)?
¿C´omo distribuyen? ¿C´omo se relacionan con N(t)?
ICS2123
Proceso Poisson
2026-1
32 / 61

Descomposici´on y Suma
Descomposici´on de Procesos Poisson
N1(t) es un Proceso de Poisson a tasa pλ..
De forma an´aloga, N2(t) es un Proceso de Poisson a tasa (1 −p)λ.
¿Ser´an N1(t) y N2(t) independientes?
Si nos dicen que N1(t) = k, ¿cambia la distribuci´on de N2(t)?
ICS2123
Proceso Poisson
2026-1
33 / 61

Descomposici´on y Suma
Descomposici´on de Procesos Poisson
Sea {N(t),t ≥0} un Proceso Poisson con tasa λ. Supongamos que los
eventos de este proceso se pueden clasificar en m categor´ıas mutuamente
excluyentes, con probabilidad p1, p2,... pm respectivamente.
Sea {Ni(t),t ≥0} el proceso que cuenta los eventos de tipo i hasta el
tiempo t (i = 1,...,m).
Descomposici´on de un Proceso Poisson
{Ni(t),t ≥0} es un Proceso de Poisson con tasa λi=λpi para i = 1,...,m
Adem´as, {N1(t),t ≥0}, {N2(t),t ≥0},..., {Nm(t),t ≥0} son procesos
independientes entre s´ı.
ICS2123
Proceso Poisson
2026-1
34 / 61

Descomposici´on y Suma
Suma de Procesos Poisson
Sean N1(t) y N2(t) dos procesos Poisson independientes entre s´ı, con
tasas λ1 y λ2 respectivamente. Queremos saber qu´e ocurre con la suma de
estos procesos.
N(t) = N1(t) + N2(t)
¿Es N(t) un Proceso de Poisson?
Sean:
X1,..Xi,..: Tiempos entre eventos de N1(t).
Y1,..Yi,..: Tiempos entre eventos de N2(t).
T1,..Ti,..: Tiempos entre eventos de N(t).
¿C´omo distribuye T1? →T1 = min{X1,Y1}
ICS2123
Proceso Poisson
2026-1
35 / 61

Descomposici´on y Suma
Suma de Procesos Poisson
P(T1 > x)
=
P(X1 > x,Y1 > x)
=
P(X1 > x) ⋅P(Y1 > x)
=
e−λ1x ⋅e−λ2x
=
e−(λ1+λ2)x
Por lo tanto, T1 distribuye exponencial a tasa λ1 + λ2.
Se puede demostrar tambi´en que T2 distribuye exponencial a tasa λ1 + λ2
y que es independiente de T1.
Por lo tanto, N(t) es un Proceso de Poisson.
Suma Procesos de Poisson
Sean N1(t),N2(t),...,Nm(t), t ≥0, procesos Poisson independientes con
tasas λ1,λ2,...,λm, respectivamente.
El proceso N(t) = N1(t) + N2(t) + ⋅⋅⋅+ Nm(t) es un Proceso Poisson con
tasa λ = λ1 + λ2 + ⋅⋅⋅+ λm.
ICS2123
Proceso Poisson
2026-1
36 / 61

Descomposici´on y Suma
Descomposici´on y Suma de Procesos Poisson
Ejemplo
Dos supermercados, A y B, se ubican en veredas opuestas de una misma
calle. La llegada de clientes al supermercado i ocurre de acuerdo a un
Proceso de Poisson con tasas λi, i = A,B. Ambos procesos son
independientes entre s´ı y se inician a la hora en que simult´aneamente
abren estos supermercados, que es a las 9:00 a.m.
1 Considere el proceso que cuenta la llegada de clientes sin importar el
supermercado al que se dirijan. Determine la distribuci´on de
probabilidad del tiempo que trascurre desde las 9:00 a.m. hasta el
instante de ocurrencia del segundo evento de dicho proceso.
2 Determine la probabilidad de que el primer cliente que llega tras la
apertura de los supermercados sea un cliente del supermercado A y
que esta llegada ocurra despu´es del instante t.
ICS2123
Proceso Poisson
2026-1
37 / 61

Extensiones
Outline
1 Proceso de Conteo
2 Proceso de Poisson
3 Descomposici´on y Suma
4 Extensiones
ICS2123
Proceso Poisson
2026-1
38 / 61

Extensiones
Proceso Poisson compuesto
Ejemplo:
Llegan grupos de personas a un parque de diversiones y queremos contar
la cantidad de gente que llega al parque. Definamos:
●N(t): Cantidad de grupos que llega al parque en [0,t].
●Yi: Cantidad de personas que contiene el grupo i.
●X(t): Cantidad de personas que llega al parque entre [0,t].
Entonces
X(t) =
N(t)
∑
i=1
Yi
¿Qu´e podemos decir sobre X(t)? ¿Qu´e propiedades posee?
ICS2123
Proceso Poisson
2026-1
39 / 61

Extensiones
Proceso Poisson compuesto
Definici´on
El proceso de conteo {X(t),t ≥0} es un Proceso de Poisson compuesto si
puede representarse como:
X(t) =
N(t)
∑
i=1
Yi
Donde {N(t),t ≥0} es un Proceso de Poisson con tasa λ y
{Yi,i = 1,2,3...} son v.a. i.i.d. que adem´as son independientes de N(t).
ICS2123
Proceso Poisson
2026-1
40 / 61

Extensiones
Proceso Poisson compuesto
Caracter´ısticas del proceso:
●No existe una f´ormula expl´ıcita para la funci´on de probabilidades de
X(t).
●E[X(t)] = E[Yi] ⋅E[N(t)]
Demostraci´on:
E[X(t)]
=
∞
∑
n=0
E[X(t)∣N(t) = n] ⋅P(N(t) = n)
=
∞
∑
n=0
n ⋅E[Yi] ⋅P(N(t) = n)
=
E[Yi]
∞
∑
n=0
n ⋅P(N(t) = n)
=
E[Yi] ⋅E[N(t)]
ICS2123
Proceso Poisson
2026-1
41 / 61

Extensiones
Proceso Poisson compuesto
Ejemplo
Considere un proceso {X(t),≥0} que cuenta la cantidad de productos
vendidos en un almac´en. Sean {N(t),≥0} el Proceso Poisson que cuenta
la cantidad de ventas realizadas e Yi la cantidad de productos en cada
venta. Usted sabe que con probabilidad p la venta es de un producto y con
probabilidad 1 −p es de 2 productos.
Los Yi son independientes entre s´ı e independientes del n´umero de ventas.
Calcule la probabilidad de que en 10 minutos el almac´en haya vendido 5
productos.
ICS2123
Proceso Poisson
2026-1
42 / 61

Extensiones
Proceso Poisson no homog´eneo
Ejemplo:
La frecuencia con la que pasan los buses por un paradero del transantiago
depende de la hora del d´ıa y queremos calcular la cantidad de buses que
pasa por el paradero. Definamos:
●N(t): Cantidad de buses que pasa por el paradero en [0,t].
●λ(t): tasa a la que pasan los buses en el instante t.
●m(t): tasa media a la que pasan los buses en [0,t].
m(t) = ∫
t
0 λ(r)dr
m(s,t) = ∫
t
s λ(r)dr
¿Qu´e podemos decir sobre N(t)? ¿Qu´e propiedades cumple?
ICS2123
Proceso Poisson
2026-1
43 / 61

Extensiones
Poisson no-homog´eneo
Definici´on
El proceso de conteo {N(t),t ≥0} es Proceso de Poisson no homog´eneo
con tasa λ(t), t ≥0, si:
●N(0) = 0
●El proceso tiene incrementos independientes
●P[N(t,t + h)) ≥2] = o(h)
P[(N(t,t + h) = 1] = λ(t)h + o(h)
Proposici´on
Si {N(t),t ≥0} es un Proceso Poisson no Homog´eneo con tasa λ(t),
entonces N(s,t) distribuye Poisson con tasa m(s,t):
P[N(s,t) = n] = e−[m(s,t)] [m(s,t)]n
n!
n ≥0
ICS2123
Proceso Poisson
2026-1
44 / 61

Extensiones
Poisson no-homog´eneo
Tiempos entre eventos
Para el primer tiempo entre evento tenemos que:
P(T1 > t) = P(N(t) = 0) = e−m(t)
¿Es una distribuci´on exponencial? NO
¿Tiene falta de memoria?
P(T1 > x + y∣T1 > x)
=
P(T1 > x + y,T1 > x)
P(T1 > x)
= P(T1 > x + y)
P(T1 > x)
=
e−m(x+y)
e−m(x)
= e−[m(x+y)−m(x)] = e−[m(x,x+y)]
No existe falta de memoria (la probabilidad depende de x e y).
ICS2123
Proceso Poisson
2026-1
45 / 61

Extensiones
Poisson no-homog´eneo
Ejemplo
Se desea contar la cantidad de vueltas que un atleta da una pista ol´ımpica.
Se pensaba modelar esto como un Proceso Poisson, pero como el atleta se
cansa, cada vez corre m´as lento y el tiempo entre vueltas aumenta. Por lo
tanto se model´o como un Proceso Poisson no homog´eneo con λ(t) =
1
t+1
(t en minutos). Se desea calcular:
1 La probabilidad de que en 20 minutos de 4 vueltas a la pista.
2 Si el atleta da 3 vueltas a la pista en los primeros 10 minutos, ¿cu´al
es la probabilidad que los pr´oximos 10 minutos complete 2 vueltas?
3 Se sabe que el atleta dio 5 vueltas en los primeros 15 minutos, ¿cu´al
es la probabilidad de que haya dado al menos 3 vueltas en los
primeros 10 minutos?
ICS2123
Proceso Poisson
2026-1
46 / 61

Extensiones
Paradoja de la Inspecci´on
Consideremos el siguiente caso:
●Pasan buses por un paradero con tiempos entre eventos i.i.d.
Exponencial(λ).
●Un observador quiere estimar el tiempo esperado entre llegadas de
buses.
●Para esto se para en un instante t cualquiera.
X1
X2 ... XN(t)
t
Y (t)
Z(t)
XN(t)+1
¿C´omo distribuye Y (t)? ¿C´omo distribuye Z(t)?
¿Cuanto es la esperanza de XN(t)+1?
ICS2123
Proceso Poisson
2026-1
47 / 61

Extensiones
Paradoja de la Inspecci´on
XN(t)+1 = Z(t) + Y (t)
Por p´erdida de memoria sabemos que Y (t) ∼Exp(λ).
¿C´omo distribuye Z(t)?
Sin p´erdida de generalidad, asumamos que N(t) = 0, y por lo tanto,
Z(t) = t.
P(Z(t) ≤x)
=
1 −P(Z(t) > x)
(x < t)
=
1 −P(N(x) = 0)
=
1 −e−λx
Adem´as, sabemos que:
P(Z(t) = t) = P(N(t) = 0) = e−λt
Es decir, Z(t) no se comporta exactamente como una v.a. con
distribuci´on exponencial. ¿C´omo se grafica esto?
ICS2123
Proceso Poisson
2026-1
48 / 61

Extensiones
Paradoja de la Inspecci´on
t
1
e−λt
1 −e−λt
Z(t) presenta un ”salto” en t.
XN(t)+1 es m´as grande que un Xi cualquiera.
ICS2123
Proceso Poisson
2026-1
49 / 61

Extensiones
Paradoja de la Inspecci´on
Intuici´on:
Si uno se para en un punto cualquiera, es m´as probable que justo se haya
parado en un intervalo largo entre eventos, es decir, que el tiempo entre el
evento que reci´en pas´o y el que est´a por ocurrir sea m´as largo de lo
esperado. Por lo tanto, el promedio de tiempo que uno calcula es siempre
mayor a que si uno lo midiera desde que empieza un evento hasta que
empieza otro.
Llegada al azar
1
1
1
1
1
4
4
4
4
La paradoja tambi´en es v´alida si los tiempos entre eventos son v.a. i.i.d.
pero no exponenciales.
ICS2123
Proceso Poisson
2026-1
50 / 61

Extensiones
Paradoja de la Inspecci´on
Ejemplo
Consideremos un proceso con tiempos entre eventos Xi tal que:
Xi = { 1
con probabilidad 1/2
4
con probabilidad 1/2
t
P(XN(t)+1 = 4) = 4
5
E(Xi) = 1 ⋅1
2 + 4 ⋅1
2 = 2.5
E(XN(t)+1) = 4 ⋅4
5 + 1 ⋅1
5 = 3.4
ICS2123
Proceso Poisson
2026-1
51 / 61

Extensiones
Proceso de Renovaci´on
Definici´on
Sea {N(t),t ≥0} un proceso de conteo y Ti los tiempos entre eventos. Si
las variables aleatorias que componen la secuencia {Ti,i = 1,2,3...} son no
negativas, independientes e id´enticamente distribuidas, entonces se dice
que el proceso {N(t),t ≥0} es un Proceso de Renovaci´on.
●Este proceso es tal que el tiempo hasta que ocurre el primer evento
tiene una distribuci´on F(⋅), el tiempo entre el primer y segundo
evento es independiente del primer tiempo y tiene la misma
distribuci´on F(⋅), y as´ı sucesivamente. Cada vez que ocurre un
evento, el proceso se renueva.
●Un caso particular de este proceso es el Proceso de Poisson (recuerde
que Poisson no solo se renueva cuando ocurre un evento, sino que en
todo momento)
ICS2123
Proceso Poisson
2026-1
52 / 61

Extensiones
Proceso de Renovaci´on
Poisson se renueva
en todo instante
Renovaci´on se renueva
cada vez que ocurre
un evento
ICS2123
Proceso Poisson
2026-1
53 / 61

Extensiones
Proceso de Renovaci´on
¿C´omo distribuye N(t)?
N(t) ≥n ⇔Sn ≤t
Por lo tanto:
P(N(t) = n)
=
P(N(t) ≥n) −P(N(t) ≥n + 1)
=
P(Sn ≤t) −P(Sn+1 ≤t)
=
P(T1 + T2 + ⋅⋅⋅+ Tn ≤t) −P(T1 + T2 + ⋅⋅⋅+ Tn + Tn+1 ≤t)
Como las variables T1,T2 ... son id´enticamente distribuidas e
independientes con distribuci´on F(⋅), entonces Sn = ∑n
i=1 Ti tiene
distribuci´on F (n)(⋅), que es la n-´esima convoluci´on de F(⋅) consigo
misma. Entonces:
P(N(t) = n) = F (n)(t) −F (n+1)(t)
ICS2123
Proceso Poisson
2026-1
54 / 61

Extensiones
Proceso de Renovaci´on
Funci´on de valor medio o funci´on de renovaci´on
La funci´on de renovaci´on corresponde al n´umero medio (esperado) de
eventos en [0,t]. Es decir,
m(t) = E(N(t))
Ahora, nos interesa conocer la ecuaci´on de renovaci´on, que es una
ecuaci´on integral satisfecha por la funci´on de renovaci´on. Para obtenerla,
podemos condicionar sobre el tiempo de ocurrencia del primer evento.
m(t) = E(N(t)) = ∫
∞
0
E(N(t)∣T1 = x) ⋅f(x)dx
ICS2123
Proceso Poisson
2026-1
55 / 61

Extensiones
Proceso de Renovaci´on
Adem´as, usando el argumento de renovaci´on, sabemos que:
E(N(t)∣T1 = x) = { 1 + E(N(t −x))
si x ≤t
0
si x > t
Por lo tanto:
m(t)
=
∫
t
0 (1 + m(t −x)) ⋅f(x)dx
=
F(t) + ∫
t
0 m(t −x) ⋅f(x)dx
Entonces, la ecuaci´on de renovaci´on es:
m(t) = F(t) + ∫
t
0 m(t −x) ⋅f(x)dx
ICS2123
Proceso Poisson
2026-1
56 / 61

Extensiones
Proceso Poisson compuesto
Ejercicio
Ejemplo
Considere el proceso {X(t),t > 0} que cuenta la cantidad de productos
vendidos en un almac´en. Sea {N(t),t > 0} el Proceso Poisson que cuenta
la cantidad de ventas realizadas y sea Yi la cantidad de productos en cada
venta. Consideremos que con probabilidad p la venta es de un producto y
con probabilidad 1 −p la venta contiene dos productos. Los Yi son
independientes entre s´ı y son independiente del n´umero de ventas que han
ocurrido. Calcule la probabilidad de que en 10 minutos el almac´en haya
vendido 5 productos.
ICS2123
Proceso Poisson
2026-1
57 / 61

Extensiones
Proceso de Renovaci´on
Ejercicio
Ejemplo
Un minero se encuentra atrapado en una mina de carb´on. Existen 3
puertas que ´el puede escoger para salvarse. La primera lo conduce por un
t´unel que le permite salir a salvo de la mina en 2 horas. La segunda lo
conduce a un t´unel que lo lleva de vuelta a la mina despu´es de 3 horas. La
tercera, lo conduce a un t´unel que lo lleva de vuelta a la mina despu´es de
5 horas. Asuma que en cada ocasi´on el minero escoge una de las 3 puertas
al azar. Calcule el tiempo esperado que le toma salir a salvo de la mina.
Soluci´on:
T: Tiempo que se demora en salir.
A: Camino a seguir.
Queremos obtener E(T).
ICS2123
Proceso Poisson
2026-1
58 / 61

Extensiones
Proceso de Renovaci´on
Ejercicio
E(T∣A = 1) = 2
E(T∣A = 2) = 3 + E(T)
E(T∣A = 3) = 5 + E(T)
Por lo tanto,
E(T)
=
3
∑
i=1
E(T∣A = i)P(A = i)
=
2 ⋅1
3 + (3 + E(T)) ⋅1
3 + (5 + E(T)) ⋅1
3
⇒E(T)
=
10
ICS2123
Proceso Poisson
2026-1
59 / 61

Ejercicios Propuestos
Ejercicios Propuestos
Ejercicio 1
Considere una oficina de pagos con dos encargados que atienden clientes.
La llegada de clientes sigue un proceso de Poisson con tasa α
clientes/minuto. Cada cliente es atendido inmediatamente si al menos un
encargado est´a libre, y el tiempo de atenci´on es una variable exponencial
con media 1/β minutos, independiente entre clientes y encargados.
Inicialmente, la oficina est´a vac´ıa.
1 Determine la probabilidad de que el segundo cliente llegue antes de
que finalice la atenci´on del primero.
2 Calcule la probabilidad de que el tercer cliente llegue m´as de x
minutos despu´es del segundo.
3 Calcule la probabilidad de que al llegar el tercer cliente, los dos
primeros a´un est´en siendo atendidos.
ICS2123
Proceso Poisson
2026-1
60 / 61

Ejercicios Propuestos
Ejercicios Propuestos
Ejercicio 2
Considere un local que vende empanadas entre 9 AM y 7 PM. La llegada
de clientes sigue un proceso de Poisson con tasa β clientes/hora, y cada
cliente compra exactamente una empanada si hay disponibles. Diariamente
se prepara una cantidad fija de empanadas, K > 150, antes de abrir, sin
posibilidad de modificar esta cantidad posteriormente. Las empanadas
sobrantes al cierre se trasladan a otro local.
●Calcule la probabilidad de que todas las empanadas se hayan vendido
una hora antes del cierre.
●Calcule la probabilidad de que llegue al menos un cliente cuando ya
no queden empanadas disponibles.
●Si en un d´ıa llegaron exactamente K + 15 clientes, calcule la
probabilidad de que la ´ultima empanada se vendiera antes de las 6:30
PM.
ICS2123
Proceso Poisson
2026-1
61 / 61

