Pontificia Universidad Cat´olica de Chile
Escuela de Ingenier´ıa
Departamento de Ingenier´ıa Industrial y de Sistemas
ICS2123 – Modelos Estoc´asticos
Profesores Ver´onica Godoy y Andr´es Navarro
Ayudante Jefe Joaqu´ın Vergara
Primer Semestre 2026
Ayudant´ıa 12:
Repaso I2
Ayudantes: Emilio Pe˜na (emilio.penasepulveda@uc.cl) & Mart´ın Pe˜na (martinpena@uc.cl)
Problema 1
El fin de semana pr´oximo usted ir´a a jugar un partido de tenis en contra de su amigo/a. Usted est´a
convencido/a de que posee una probabilidad 0 < p < 1 de ganar cada punto.
En un partido de tenis, cuando los jugadores est´an empatados con 40 puntos (”iguales”), uno de los
jugadores debe ganar dos puntos m´as que su contrincante para ganar el juego. Si est´an empatados y un
jugador gana un punto, se dice que tiene ventaja, si el mismo jugador gana el siguiente punto, gana el
juego, pero si el otro jugador gana el siguiente punto, se pierde la ventaja y vuelven a quedar ”iguales”.
Considere que en un cierto momento, usted est´a ”iguales” con su contrincante.
(a) Construya la CMTD que modele el juego desde la posici´on de ”iguales” hasta el final del juego. Luego
responda, ¿Cu´al es la probabilidad que usted gane ese juego? (Considerando que se parte desde la
igualdad)
Soluci´on: Sea Xn: Estado del juego despu´es del punto n.
Los estados posibles son: GA: Gana usted; V A: Ventaja para usted; IG: Iguales; V B: Ventaja para
contrincante; GB: Gana contrincante.
Con ello la CMTD se visualiza de la siguiente manera.
IG
V B
GB
V A
GA
1
p
p
p
1
1 −p
1 −p
1 −p
Ahora se pide calcular la probabilidad de que usted gan´e, lo cual se representa como F(IG, GA)
F(IG, GA) = p · F(V A, GA) + (1 −p) · F(V B, GA)
F(V A, GA) = p + (1 −p) · F(IG, GA)
F(V B, GA) = p · F(IG, GA)
Al resolver se obtiene: F(IG, GA) =
p2
1−2p+2p2
(b) ¿Cu´antos puntos, en promedio, se jugar´an hasta que termine ese juego?
Soluci´on: En este caso, se busca la cantidad de turnos esperada para llegar de IG hasta GA o hasta
GB, lo que se traduce en E[T(IG, GA ∪GB)]
E[T(IG, GA ∪GB)] = 1 + p · E[T(V A, GA ∪GB)] + (1 −p) · E[T(V B, GA ∪GB)]
E[T(V A, GA ∪GB)] = 1 + (1 −p) · E[T(IG, GA ∪GB)]
E[T(V B, GA ∪GB)] = 1 + p · E[T(IG, GA ∪GB)]
Al resolver el sistema se obtiene: E[T(IG, GA ∪GB)] =
2
1−2p+2p2
1

(c) ¿Cu´al es la probabilidad que se disputen exactamente 4 puntos para terminar el juego?
Soluci´on: En este caso se pide: F4(IG, GA ∪GB)
F4(IG, GA ∪GB) = p · F3(V A, GA ∪GB) + (1 −p) · F3(V B, GA ∪GB)
F3(V A, GA ∪GB) = (1 −p) · F2(IG, GA ∪GB)
F3(V B, GA ∪GB) = p · F2(IG, GA ∪GB)
F2(IG, GA ∪GB) = p · F1(V A, GA ∪GB) + (1 −p) · F1(V B, GA ∪GB)
F1(V A, GA ∪GB) = p
F1(V B, GA ∪GB) = 1 −p
Al resolver se obtiene: F4(IG, GA ∪GB) = 2p(1 −p)((1 −p)2 + p2)
2

Problema 2
Suponga un dado cargado que se comporta del siguiente modo: si en el lanzamiento anterior sali´o el n´umero
i (con i = 1, 2, 3, 4, 5) es imposible que obtengamos el n´umero i + 1 en el lanzamiento actual. Adem´as, cada
vez que se lanza el dado existe un 50 % de probabilidades de que salga el mismo n´umero que sali´o en el
lanzamiento anterior y un 50 % de probabilidades de que salga cualquiera de los otros posibles n´umeros (en
forma equiprobable).
Por ´ultimo, cuando obtuvimos el n´umero 6 en el lanzamiento anterior, es posible obtener solo tres resultados
equiprobables en el lanzamiento actual, pudiendo sacar los n´umeros 1, 3 y 6. A partir de lo anterior,
responda:
(a) Argumente por qu´e la situaci´on anterior se puede modelar como una CMTD.
Soluci´on: Si definimos {Xn, n ∈N0} como el proceso estoc´astico que representa el n´umero del
dado (Xn) que sali´o en el lanzamiento n, es posible notar que el sistema cumple con la propiedad
markoviana (s´olo depende el ´ultimo lanzamiento) y con la propiedad estacionaria (no importa cuantos
lanzamientos se han realizado). Considerando esto, la situaci´on se puede modelar como una CMTD.
Notar que el conjunto de estados viene dado por S := {1, 2, 3, 4, 5, 6}.
(b) Construya el diagrama (o la matriz de probabilidades de transici´on en una etapa) de la CMTD
asociada a la situaci´on anterior. Luego, identifique las clases de estados y clasif´ıquelas como transien-
tes, recurrentes positivas o nulas, indicando adem´as si son aperi´odicas o peri´odicas (y el per´ıodo, si
corresponde).
Soluci´on: Se tiene








1
2
3
4
5
6
1
1
2
0
1
8
1
8
1
8
1
8
2
1
8
1
2
0
1
8
1
8
1
8
3
1
8
1
8
1
2
0
1
8
1
8
4
1
8
1
8
1
8
1
2
0
1
8
5
1
8
1
8
1
8
1
8
1
2
0
6
1
3
0
1
3
0
0
1
3








El diagrama que representa esta CMTD es
3

1
2
3
4
5
6
1/2
1/2
1/2
1/2
1/2
1/8
1/8
1/8
1/8
1/8
1/8
1/8
1/8
1/8
1/8
1/8
1/8
1/8
1/8
1/8
1/8
1/8
1/8
1/8
1/8
1/3
1/3
1/3
La cadena est´a compuesta por una ´unica clase ({1, 2, 3, 4, 5, 6}), la cual es recurrente positiva, y
aperi´odica.
(c) Se le entrega el vector de posiciones iniciales f (0) = ( 1
2, 0, 0, 1
4, 0, 1
4) . Calcule el vector de posiciones
en el turno n´umero 2.
Soluci´on: Se pide calcular f (2)
f (1)T = f (0)T · P =








1
2
0
0
1
4
0
1
4








T
·








1
2
0
1
8
1
8
1
8
1
8
1
8
1
2
0
1
8
1
8
1
8
1
8
1
8
1
2
0
1
8
1
8
1
8
1
8
1
8
1
2
0
1
8
1
8
1
8
1
8
1
8
1
2
0
1
3
0
1
3
0
0
1
3

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

35
96
1
32
17
96
3
16
1
16
17
96








f (2)T = f (1)T · P =








35
96
1
32
17
96
3
16
1
16
17
96








·








1
2
0
1
8
1
8
1
8
1
8
1
8
1
2
0
1
8
1
8
1
8
1
8
1
8
1
2
0
1
8
1
8
1
8
1
8
1
8
1
2
0
1
8
1
8
1
8
1
8
1
8
1
2
0
1
3
0
1
3
0
0
1
3

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

43
144
53
768
517
2304
29
192
79
768
355
2304








(d) Justifique la existencia (o no existencia) de distribuci´on estacionaria. En caso de existir plantee las
ecuaciones para obtener las probabilidades en el largo plazo.
Soluci´on: En este caso la CMTD posee una ´unica clase recurrente positiva aperi´odica, por lo que es
irreductible, y por ende, si posee una ´unica distribuci´on estacionaria. Para encontrarla se resuelve el
sistema de ecuaciones
Sea π = (π1, π2, π3, π4, π5, π6) el vector de probabilidades en el largo plazo
4

π1 = 1
2π1 + 1
8π2 + 1
8π3 + 1
8π4 + 1
8π5 + 1
3π6
π2 = 1
2π2 + 1
8π3 + 1
8π4 + 1
8π5
π3 = 1
8π1 + 1
2π3 + 1
8π4 + 1
8π5 + 1
3π6
π4 = 1
8π1 + 1
8π2 + 1
2π4 + 1
8π5
π5 = 1
8π1 + 1
8π2 + 1
8π3 + 1
2π5
π6 = 1
8π1 + 1
8π2 + 1
8π3 + 1
8π4 + 1
3π6
π1 + π2 + π3 + π4 + π5 + π6 = 1
(e) ¿Cu´al es la proporci´on del tiempo en el largo plazo que usted cae en el n´umero 2 viniendo desde un
n´umero impar? (Considere las probabilidades de largo plazo como conocidas)
Soluci´on: Para ello, se observa que la ´unica forma de caer en el 2 viniendo desde n´umero impar es
desde el 3 y desde el 5 por lo que la probabilidad pedida se calcula de la siguiente manera.
P(Caer en 2 despu´es de n´umero impar) = P32 · π3 + P52 · π5 = 1
8π3 + 1
8π5
(1)
5

Problema 3
Considere que usted posee un negocio que vende sobres del ´Album del Mundial. Actualmente su local solo
tiene capacidad de inventario para almacenar K (n´umero par) cajas de sobres a la vez.
Considere que las cajas llegan a su negocio por 2 distribuidoras. La primera de ellas, en cada entrega le
trae solo 1 caja, donde las llegadas se modelan mediante un Proceso Poisson de tasa λ. La segunda, en
cada env´ıo le trae K/2 cajas, donde los tiempos entre env´ıos siguen una distribuci´on exponencial con media
1/β. Si debido a la capacidad no puede almacenar cualquiera de los env´ıos, estos simplemente se ir´an a
otro local.
En cuanto a la venta, el tiempo que dura cada una de las cajas en el almac´en antes de ser vendidas sigue
una distribuci´on exponencial de tasa µ, con la salvedad que cuando hay m´as de K/2 cajas en el almac´en
se decide lanzar ofertas, las cuales aumentan la velocidad en las ventas en un X %
(a) Modele la evoluci´on temporal de la cantidad de cajas en su almac´en como una CMTC.
Soluci´on: Considerando los estados como la cantidad de cajas, tendremos que el grafo correspondiente
ser´a:
0
1
2
3
4
...
K/2 −1
K/2
K/2 + 1
...
K −2
K −1
K
λ
λ
λ
λ
λ
λ
λ
λ
λ
λ
λ
λ
β
µ
2µ
3µ
4µ
5µ
(K/2 −1)µ
(K/2)µ
(K/2 + 1)µ(1 + X)
(K/2 + 2)µ(1 + X)
(K −2)µ(1 + X)
(K −1)µ(1 + X)
Kµ(1 + X)
β
β
β
β
β
β
β
(b) Determine la distribuci´on l´ımite y plantee las ecuaciones que permitan encontrar estas probabilidades.
Soluci´on: El sistema de ecuaciones queda:
(λ + β)P0 = µP1
(λ + β + iµ)Pi = λPi−1 + (i + 1)µPi+1
∀i ∈{1, 2, ..., K
2 −1}
(λ + β + K
2 µ)PK/2 = βP0 + λPK/2−1 + (K
2 + 1)µ(1 + X)PK/2+1
(λ + iµ(1 + X))Pi = βPi−K/2 + λPi−1 + (i + 1)µ(1 + X)Pi+1
∀i ∈{K
2 + 1, ..., K −1}
Kµ(1 + X)PK = βPK/2 + λPK−1
6

K
X
i=0
Pi = 1
Ahora usted quiere ampliar su negocio, para lo que arrienda un galp´on con tal de tener m´as espacio para
las cajas de sobres. Esto le permite tener una capacidad pr´acticamente infinita en el galp´on, pero a costa
de que ya no se lanzan las ofertas que aumentan en X % la velocidad de venta. (los tiempos de duraci´on
de las cajas antes de ser vendidas solo consideran a las cajas del almac´en no a las del galp´on).
En cuanto a las distribuidoras, debido a los cambios, la segunda deja de trabajar con usted y la primera
cambia su pol´ıtica, a partir de ahora en cada entrega le trae solo 1 caja, donde las llegadas se siguen
modelando como un Proceso Poisson de tasa λ, pero si posee m´as de K cajas en su inventario (y por ende
debe ir a dejarla al galp´on) la tasa pasa a ser α.
(c) Modele esta nueva CMTC, plantee las ecuaciones para encontrar las probabilidades en el largo plazo
y especifique bajo que condiciones el sistema no colapsar´ıa.
Soluci´on: Para esta nueva configuraci´on, el grafo correspondiente ser´a:
0
1
2
...
K −1
K
K + 1
...
λ
λ
µ
2µ
λ
3µ
(K −1)µ
λ
λ
Kµ
Kµ
α
α
Kµ
En este caso, la CMTC corresponde a un proceso de nacimiento y muerte, por lo que existen formulas
cerradas para los Pn las cuales corresponde a:
Pn = λ0 · λ1 · ... · λn−1
µ1 · µ2 · ... · µn
|
{z
}
Yn
·P0
∀n
En este caso los valores para Yn corresponden a:
Yn =





λn
n!µn
∀n ≤K
λKαn−K
K!Kn−Kµn
∀n > K
Y el valor de P0 corresponde a:
P0 =
1
1 + P∞
n=1 Yn
Por ´ultimo para que el sistema no colapse, las salidas deben ser m´as r´apidas que las llegadas, por lo
que:
Kµ > α
7

(d) Considere que a usted le cobran G pesos por caja que guarde en el galp´on. Calcule el precio esperado
que deber´a pagar. (Considere conocidas las probabilidades en el largo plazo)
Soluci´on: Para obtener este valor se debe ponderar la proporci´on del tiempo que se est´a en cada uno
de los estados donde hay cajas en el galp´on por la cantidad de cajas en el galp´on, lo que corresponde
a:
E[Precio a Pagar] =
∞
X
n=K+1
G · (n −K) · Pn
8

