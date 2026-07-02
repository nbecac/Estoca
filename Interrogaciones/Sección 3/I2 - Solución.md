Pontificia Universidad Cat´olica de Chile
Escuela de Ingenier´ıa
Departamento de Ingenier´ıa Industrial y de Sistemas
ICS2123 – Modelos Estoc´asticos 1-2026
Profesora: Ver´onica Godoy
Interrogaci´on 2
Duraci´on: 2 horas 30 minutos
Problema 1 (18 puntos)
a) (6 puntos) Felipe, Jos´e y Mateo est´an jugando con una pelota. Felipe siempre le pasa la pelota a Jos´e y Jos´e siempre
se la pasa a Mateo. Mateo por su parte, le pasa la pelota indistintamente a Felipe o a Jos´e.
i. Modele la situaci´on descrita como una CMTD. Argumente si el proceso tiene distribuci´on l´ımite.
Soluci´on:
Xn: ni˜no que tiene la pelota al inicio de la jugada n, Xn ∈{F (Felipe), J (Jos´e), M (Mateo) }
F
J
M
1
1
0.5
0.5
La cadena es irreductible (todos los estados se comunican), finita (solo tres estados posibles), aperi´odica (si el
proceso inicia en el estado F se puede estar en F en las etapas 3,5,6,7,8,...), por lo que SI tiene distribuci´on l´ımite.
ii. Proponga una modificaci´on a la din´amica del juego de manera tal que cambie su respuesta anterior (por ejemplo,
si en i. dijo que el proceso SI ten´ıa distribuci´on l´ımite en ii. NO la tiene). Arme la nueva cadena y justifique.
Soluci´on:
Si Mateo siempre le pasa la pelota a Felipe la cadena quedar´ıa as´ı:
F
J
M
1
1
1
Y ser´ıa peri´odica de periodo 3, raz´on por la cual la distribuci´on l´ımite NO existe.
Puntaje:
2p Modelo (definici´on, estados, grafo o matriz).
2p Argumentos para justificar la existencia de distribuci´on l´ımite.
2p Nuevo din´amica, grafo y argumentos para justificar la no existencia de distribuci´on l´ımite.
1

b) (6 puntos) Francisca y Javiera est´an estudiando el comportamiento de largo plazo de una CMTD. Para ello han
parametrizado algunos valores de las probabilidades de transici´on (0 < p, q, r < 1 ), obteniendo la siguiente matriz:
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


1
0
0
0
0
0
1 −p
0
p
0
0
0
0
0
0
1 −q
q
0
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
1 −r
r
0
0
0
0
1
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


Determine la matriz P (100). Para aquellas celdas (i, j) que sean distintas de 0 y 1 utilice las variables x, y, z. Justifique.
Soluci´on:
1
2
3
4
5
6
1 −p
p
1 −q
q
1
1 −r
1
r
1
La cadena tiene tres clases: C1 = {1} recurrente C2 = {2, 3, 4} transiente C3 = {5, 6} recurrente
Si j es recurrente, entonces
lim
n→∞P (n)
ij
=
F(i, j)
E(T(j, j))
La matriz P (100) tiende a:
P (100) =











1
0
0
0
0
0
y
0
0
0
x(1 −y)
(1 −x)(1 −y)
z
0
0
0
x(1 −z)
(1 −x)(1 −z)
y
0
0
0
x(1 −y)
(1 −x)(1 −y)
0
0
0
0
x
1 −x
0
0
0
0
x
1 −x











donde:
x =
1
E(T(5, 5))
1 −x =
1
E(T(6, 6))
y = F(2, 1); F(2, 1) + F(2, 5) = 1; F(2, 5) = F(2, 6) = 1 −y
z = F(3, 1); F(3, 1) + F(3, 5) = 1; F(3, 5) = F(3, 6) = 1 −z
F(4, 1) = P42 · F(2, 1) = y
Puntaje:
2 pts Determinaci´on de clases y su tipo.
4 pts Matriz.
2

c) (6 puntos) Considere una CMTC con la siguiente matriz de transici´on:
P =






0
0.9
0.1
0
0
0
0.6
0.4
0
0
0
1
1
0
0
0






El tiempo de permanencia en el estado i (i = 0, 1, 2, 3) distribuye exponencial de tasa vi > 0
∀i
i. Elabore el diagrama de transici´on de estados. Especifique claramente las tasas de transici´on instant´aneas.
ii. Plantee las ecuaciones necesarias para obtener las probabilidades de largo plazo de esta cadena.
Soluci´on:
0
1
2
3
0.9 · v0
0.1 · v0
0.6 · v1
0.4 · v1
v2
v3
Ecuaciones de equilibrio:
P0 · v0 = P3 · v3
P1 · v1 = P0 · 0.9 · v0
P2 · v2 = P0 · 0.1 · v0 + P1 · 0.6 · v1
P3 · v3 = P1 · 0.4 · v1 + P2 · v2
P0 + P1 + P2 + P3 = 1
Puntaje:
3p Grafo, transiciones y tasas de transici´on.
3p Ecuaciones de cada estado y ecuaci´on de normalizaci´on.
3

Problema 2 (24 puntos)
Una empresa de delivery utiliza cajas pl´asticas reutilizables para transportar los pedidos de sus clientes. Al inicio de cada
semana la empresa revisa cada caja y la clasifica como: buena, aceptable o estropeada. Cada caja estropeada es eliminada
y reemplazada por una caja nueva la cual demora una semana en llegar a la empresa.
El registro de la empresa indica que, a la semana siguiente: el 90% de las cajas nuevas se clasifican como buenas y las
restantes como aceptables, el 20% de las cajas buenas se clasifican como aceptables y el 10% como estropeadas, mientras
que el 40% de las cajas aceptables se clasifican como estropeadas.
a) (6 puntos) Modele la situaci´on descrita como una CMTD.
Soluci´on:
Xn : Estado de la caja al inicio de la semana n; Xn ∈{N (Nueva), B (Buena), A (Aceptable), E (Estropeada) }
P =






0
0.9
0.1
0
0
0.7
0.2
0.1
0
0
0.6
0.4
1
0
0
0






Puntaje:
2p Definici´on, estados;
4p Matriz de transici´on o grafo.
.
b) (6 puntos) ¿Cu´antas semanas, en promedio, tarda una caja nueva en estropearse?
Soluci´on: Se pide calcular E[T(N, E)]
1) E[T(N, E)] = 1 + 0, 9 · E[T(B, E)] + 0, 1 · E[T(A, E)]
2) E[T(B, E)] = 1 + 0, 7 · E[T(B, E)] + 0, 2 · E[T(A, E)]
3) E[T(A, E)] = 1 + 0, 6 · E[T(A, E)]
De 3) se obtiene que E[T(A, E)] = 2, 5 semanas. Se reemplaza en 2) y se obtiene que E[T(A, E)] = 5 semanas. Se
reemplazan en 1) y se obtiene que E[T(B, E)] = 5, 75 semanas.
R: Una caja nueva tarda 5,75 semanas, en promedio, en estropearse.
Puntaje:
2p Sistema de ecuaciones.
3p Resoluci´on.
1p Respuesta.
4

c) (6 puntos) Si al inicio de la semana una caja est´a buena, ¿cu´al es la probabilidad que dure cuatro semanas m´as?
Soluci´on: Las transiciones posibles son: BBBBE, BBBAE, BBAAE, BAAAE.
P(BBBBE) = 0.73 · 0.1
P(BBBAE) = 0.72 · 0.2 · 0.4
P(BBAAE) = 0.7 · 0.2 · 0.6 · 0.4
P(BAAAE) = 0.2 · 0.62 · 0.4
R: La probabilidad que una caja buena dure cuatro semanas m´as es 0.1359
Puntaje (resoluci´on 1):
2p Casos favorables.
3p C´alculo probabilidades.
1p Respuesta.
Obs: Tambi´en se puede realizar calculando F4(B, E)
F4(B, E) = 0.7 · F3(B, E) + 0.2 · F3(A, E) = 0.1071 + 0.0288 = 0.1359
F3(B, E) = 0.7 · F2(B, E) + 0.2 · F2(A, E) = 0.105 + 0.048 = 0.153
F3(A, E) = 0.6 · F2(A, E) = 0.144
F2(B, E) = 0.7 · 0.1 + 0.2 ·0.4 = 0.15
F2(A, E) = 0.6 · 0.4 = 0.24
Puntaje (resoluci´on 2):
2p Sistema de ecuaciones.
3p Resoluci´on.
1p Respuesta.
.
d) (6 puntos) Si la empresa inicia su operaci´on con 10.000 cajas nuevas ¿cu´antas cajas de cada tipo espera tener durante
una semana cualquiera, despu´es de muchas semanas de operaci´on?
Soluci´on: Se calculan las probabilidades de largo plazo.
πN = πE
πB = 0.9πN + 0.7πB
πA = 0.1πN + 0.2πB + 0.6πA
πE = 0.1πB + 0.4πA
πN + πB + πA + πE = 1
Resolviendo se obtiene Π = ( 4
27, 12
27, 7
27, 4
27)
Si parte con 10.000 cajas nuevas, en una semana cualquiera espera tener:
10.000 · 4
27 ≈1481 cajas nuevas 10.000 · 12
27 ≈4444 cajas buenas 10.000 · 7
27 ≈2593 cajas aceptables
Puntaje:
2p Sistema de ecuaciones.
2p C´alculo probabilidades.
2p Respuesta.
.
Obs: Plantee expl´ıcitamente todas las ecuaciones que necesite para obtener sus resultados.
5

Problema 3 (18 puntos)
En un paradero de la ciudad los buses pasan de acuerdo a un proceso de Poisson a tasa β (buses/hora), mientras que las
personas llegan de acuerdo a un proceso de Poisson a tasa α (personas/hora). Una fracci´on p de las personas prefiere viajar
sentada en el bus.
La din´amica en el paradero es la siguiente: en la fila 1 se forman las personas que prefieren viajar sentadas (est´an dispuestas
a esperar lo que sea necesario para subir a un bus que tenga asientos disponibles), mientras que en la fila 2 se forman las
restantes (se suben al primer bus que pase, aunque tengan que viajar de pie). Cuando pasa un bus por el paradero, primero
se suben las personas de la fila 1; cuando se acaban los asientos disponibles del bus o la fila 1 se queda vac´ıa (lo que ocurra
primero), se suben las personas de la fila 2. Suponga que la subida de personas al bus no toma tiempo.
Considere que cada bus que llega al paradero tiene K asientos disponibles y capacidad suficiente para llevar a todos los
pasajeros que quieran viajar de pie, a su vez, la capacidad del paradero es infinita, por lo que todas las personas que llegan
al paradero pueden quedarse esperando hasta subirse a un bus.
a) (10 puntos) Modele la cantidad de personas en el paradero como una CMTC. Especifique claramente los estados y
las tasas de transici´on (instant´anea) entre estados.
Soluci´on: Sea
N1(t): n´umero de personas en la fila 1 en el instante t
N2(t): n´umero de personas en la fila 2 en el instante t
X(t) = [N1(t), N2(t)]: estado del paradero en el instante t
Si X(t) = (i, j), las transiciones posibles son a:
• (i + 1, j) a tasa α · p
∀i, j (llega una persona que prefiere viajar sentada)
• (i, j + 1) a tasa α · (1 −p)
∀i, j (llega una persona que no le importa viajar de pie)
• (i −K, 0) a tasa β
si i ≥K, j ≥0 (pasa un bus, se ocupan todos los asientos con personas de la fila 1 y se
suben todas las personas de la fila 2 (si las hay))
• (0, 0) a tasa β
si 0 ≤i < K, j > 0 (pasa un bus, se suben todas las personas que est´an en la fila 1 (sobran
asientos) y se suben todas las personas de la fila 2 (algunas podr´ıan irse sentadas))
Puntaje:
2p Definici´on, estados.
2p Por cada transici´on posible.
b) (4 puntos) ¿Qu´e relaci´on deben cumplir los par´ametros α, β, p y K para que existan probabilidades de largo plazo?
Justifique.
Soluci´on: α · p < β · K
De esta forma, los buses que, en promedio, pasan por hora tienen suficientes asientos disponibles (β ·K asientos/hora)
como para llevarse a las personas que, en promedio, llegan al paradero por hora (α · p personas/hora) y que prefieren
irse sentadas. As´ı, la fila 1 no crece indefinidamente.
Puntaje:
2p Relaci´on entre los par´ametros.
2p Justificaci´on.
6

Considere ahora que las personas que est´an en la fila 1 se pueden cambiar a la fila 2 de la siguiente manera: si una persona
que prefiere viajar sentada tiene la certeza que no alcanzar´a a subirse en el pr´oximo bus que pase, esperar´a un tiempo
exponencial de valor esperado 1/γ horas para cambiarse a la fila 2.
c) (4 puntos) Modifique la cadena anterior para modelar esta nueva situaci´on. Especifique claramente los cambios
realizados.
Soluci´on:
Si X(t) = (i, j), se agrega la transici´on a:
(i −1, j + 1) a tasa γ · (i −K)
si i > K
Las primeras K personas de la fila 1 tienen certeza de que se ir´an en el siguiente bus que pase pues tiene K asientos
disponibles, por tanto, s´olo se cambiaran a la fila 2 las personas que est´an a partir de la posici´on K+1 en la fila 1.
Puntaje:
1p Transici´on.
2p Tasa de transici´on.
1p Condici´on.
7

