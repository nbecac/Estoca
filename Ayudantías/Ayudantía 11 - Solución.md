Pontificia Universidad Cat´olica de Chile
Escuela de Ingenier´ıa
Departamento de Ingenier´ıa Industrial y de Sistemas
ICS2123 – Modelos Estoc´asticos
Profesores Ver´onica Godoy y Andr´es Navarro
Ayudante Jefe Joaqu´ın Vergara
Primer Semestre 2026
Ayudant´ıa 11:
CMTC II
Ayudantes: Emilio Pe˜na (emilio.penasepulveda@uc.cl) & Mart´ın Pe˜na (martinpena@uc.cl)
Resumen
CMTC
Una CMTC es un proceso estoc´astico {X(t) ∈S, t ≥0}, con espacio de estados S, que cumple las siguientes
propiedades:
⋄Cada vez que el sistema entra al estado i ∈S, permanece en ese estado un tiempo que distribuye
exponencial de par´ametro νi > 0.
⋄Cada vez que el sistema est´a en el estado i ∈S, la probabilidad de que haga una transici´on al estado
j ∈S es Pij ∈[0, 1].
⋄Las probabilidades Pij deben satisfacer:
Pii = 0 ,
X
j∈S
Pij = 1 ∀i ∈S
Sea Ti el tiempo de permanencia del proceso en el estado i ∈S. La propiedad Markoviana hace que el
proceso tenga p´erdida de memoria, por lo que
Ti ∼Exponencial (νi) , ∀i ∈S
N´otese que esta definici´on es equivalente a pedir que cumpla con la Propiedad Markoviana y Estacionaria.
Tasas de transici´on y permanencia
Se denomina tasa de transici´on instant´anea, qij > 0, a la tasa a la cual el proceso realiza una transici´on del
estado i ∈S al estado j ∈S, estando en i. Esta tasa est´a dada por:
qij = νi · Pij
Donde νi > 0 corresponde a la tasa a la cual el proceso realiza una transici´on cuando se encuentra en el
estado i ∈S (tasa de permanencia):
νi =
X
j∈S\{i}
qij
Y Pij ∈[0, 1] corresponde a la probabilidad que, estando en el estado i ∈S, la pr´oxima transici´on sea al
estado j ∈S \ {i}:
Pij = qij
νi
=
qij
P
j∈S\{i}
qij
1

Ecuaci´on de Equilibrio en el Largo Plazo
Se define
Pj = l´ım
t→∞Pij(t)
Si Pj existe y es independiente de i para todo j, se dice que es {Pj, j ∈S} es una distribuci´on de probabilidad
l´ımite, y se interpreta como la probabilidad de que el sistema se encuentre en el estado j, o como la
proporci´on del tiempo que el sistema pasa en ese estado en el largo plazo.
Para una CMTC se cumple que la tasa de salida en el largo plazo es igual a la suma de las tasas de llegada
en el largo plazo a ese mismo estado. Es decir:
νj · Pj =
X
k∈S\j
qkj · Pk
con:
X
i∈S
Pi = 1
La distribuci´on de probabilidades l´ımite corresponde a la soluci´on del sistema de Ecuaciones de Equilibrio
de Largo Plazo.
2

Problema 1
Una nave espacial tiene cuatro motores, dos en cada ala. Cada motor se da˜na en vuelo seg´un una variable
aleatoria exponencial con par´ametro λ. Si la falla se produce en vuelo, usted posee un androide que repara
los motores a tasa µ cuando hay al menos uno da˜nado. Sin embargo si en el vuelo fallan dos motores en la
misma ala la aeronave pierde estabilidad, por lo que el androide se apresura y repara los motores (todos al
mismo tiempo) a tasa 5µ.
Si se llegan a estropear todos los motores el avi´on puede seguir volando pero el androide cobrar´a Cg por
cada hora en que est´e reparando la aeronave sin ning´un motor funcionando debido al infinito estr´es que
estamos ocasionando al androide con un trabajo de tanta presi´on. Considere µ = 2λ.
a) Calcule la fracci´on de tiempo en que la aeronave se encuentra volando con todos sus motores funcio-
nando.
Soluci´on: Se modela el problema como una CMTC con estados binarios del tipo: (Motores funcio-
nando ala 1, Motores funcionando ala 2), de esta manera el grafo correspondiente ser´a:
2, 2
2, 1
2, 0
1, 2
1, 1
1, 0
0, 2
0, 1
0, 0
2λ
λ
µ
10µ
2λ
λ
µ
10µ
2λ
λ
5µ
10µ
2λ
µ
µ
2λ
5µ
2λ
10µ
λ
10µ
λ
10µ
λ
El sistema de ecuaciones para calcular las probabilidades de largo plazo:
P22(4λ) = P12µ + P21µ
P12(µ + 3λ) = P22(2λ) + P02(10µ) + P11µ
P02(10µ + 2λ) = P01(5µ) + P12λ
P21(µ + 3λ) = P20(10µ) + P11µ + P22(2λ)
P11(2µ + 2λ) = P12(2λ) + P21(2λ) + P10(10µ) + P01(10µ)
P01(15µ + λ) = P02(2λ) + P11λ + P00(10µ)
P20(10µ + 2λ) = P21λ + P10(5µ)
P10(15µ + λ) = P20(2λ) + P11λ + P00(10µ)
P00(20µ) = P01λ + P10λ
Resolviendo el sistema de ecuaciones, se obtiene que:
P22 = 0.244932
b) Escriba una expresi´on para el costo esperado de un vuelo de 10 horas.
Soluci´on: La esperanza del gasto es:
E[Gasto] = 10 · P00 · Cg = 0.00413736 · Cg
3

Problema 2
Debido al estreno de una pel´ıcula muy esperada, los cines est´an experimentando una situaci´on cr´ıtica
durante estos d´ıas, con largas filas para comprar entradas. Nuestro problema se enfoca en un cine espec´ıfico
que cuenta con N ∈N cajeros, cada uno atendiendo en una ventanilla distinta.
Los clientes llegan al cine seg´un un Proceso de Poisson con tasa λ > 0 clientes/minuto y esperan su turno
en una fila ´unica. Dada la alta demanda, se decidi´o permitir que la fila crezca sin restricci´on. Sin embargo,
esto ha llevado a que, para todo k ∈N, si al llegar un cliente ve una fila de k personas, solo se quedar´a a
esperar con probabilidad pk :=
1
k+1.
Se ha determinado que el tiempo de atenci´on de cada cajero sigue una distribuci´on exponencial con media
1/µ > 0 minutos. Adem´as, este tiempo no depende del cajero ni del tipo de cliente. Por otra parte, algunos
clientes comienzan a perder la paciencia mientras esperan, y otros deciden que es mejor ver la pel´ıcula
otro d´ıa, y por tanto se retiran despu´es de un tiempo aleatorio, el cual tambi´en sigue una distribuci´on
exponencial con media 1/α > 0 minutos.
(a) Modele la situaci´on del cine como una Cadena de Markov en Tiempo Continuo (CMTC). Determi-
ne los estados y presente mediante un grafo las tasas de transici´on instant´aneas entre los estados
relevantes.
Soluci´on: Sea Xi ∈{0, 1, 2, ....}, la cantidad de personas en el sistema. La CMTD queda modelada
como:
0
1
2
3
...
N
N + 1
N + 2
...
λ
λ
λ
λ
λ
λ
λ
1+1
λ
1+2
Nµ + 3α
Nµ + 2α
Nµ + α
Nµ
4µ
3µ
2µ
µ
(b) Plantee las ecuaciones de equilibrio de largo plazo para la CMTC anterior y derive la relaci´on recursiva
para los Pn.
Soluci´on: Sea X(t) el n´umero de clientes en el sistema y πn = l´ımt→∞P(X(t) = n) (si existe). La
cadena es de nacimiento–muerte con tasas dependientes del estado:
βn =





λ,
n < N,
λ pn−N =
λ
(n −N) + 1,
n ≥N,
δn =



n µ,
1 ≤n ≤N,
N µ + α (n −N),
n ≥N + 1,
y δ0 := 0.
Recordemos que para toda CTMC con generador Q = (qij) y tasas de salida νi := −qii = P
j̸=i qij,
la estacionaria P satisface
X
j̸=i
Pjqji = Piνi
(∀i),
X
i
Pi = 1.
En este caso, con qn,n+1 = βn, qn,n−1 = δn:
Pn(βn + δn) = Pn−1βn−1 + Pn+1δn+1 (n ≥1),
P0β0 = P1δ1,
X
i
Pi = 1.
Notemos que
Pkδk = Pk−1βk−1,
∀k ≥1
(Basta aplicar inducci´on sobre k y se concluye). a partir de esto obtenemos que
Pk = Pk−1
βk−1
δk
= Pk−2
βk−1βk−2
δkδk−1
= ... = P0
k−1
Y
i=0
βi
δi+1
4

Finalmente sabemos que
∞
X
j=0
Pj = 1 =⇒P0 +
∞
X
j=1
P0
j−1
Y
i=0
βi
δi+1
= 1 =⇒P0 =
1
1 + P∞
j=1
Qj−1
i=0
βi
δi+1
La interpretaci´on asociada a los Pn es que son la proporci´on de tiempo (o probabilidad de largo plazo)
en el estado con n clientes.
(c) Suponiendo conocidas las probabilidades estacionarias y considerando un per´ıodo de una hora, ¿Cu´antos
clientes en promedio llegan al cine y deciden ni siquiera intentar hacer la fila?
Soluci´on: Tenemos que la tasa de personas que deciden no entrar a la cola en el largo plazo para
todo nodo i ≥N es λ(1 −pi). Por tanto, la cantidad de clientes que en promedio llegan al centro de
salud y deciden ni siquiera intentar hacer la fila de espera en un rango de una hora es:
60λ
∞
X
i=0
PN+i ·

1 −
1
i + 1

(d) Argumente bajo qu´e condiciones el sistema no colapsar´ıa en el largo plazo (Enti´endase colapsar como
llegar a tener infinitas personas en el sistema)
Soluci´on: Para que el sistema no colapse se debe analizar la relaci´on entre la tasa de llegadas y la
tasa de salidas, en donde esta ´ultima debe ser mayor, es decir:
βn < δn
∀n ≥Nodo donde se establezca el ´ultimo patr´on
En este caso, el nodo desde el cual se mantiene un patr´on definido es el nodo N. Por lo tanto la
condici´on para el sistema es:
λ
(n −N) + 1 < Nµ + α(n −N)
∀n ≥N
5

Problema 3 (Propuesto)
Considera una peque˜na tienda de jardiner´ıa que desea modelar el inventario de dos de sus productos m´as
voluminosos: maceteros de 20 litros y bolsas de tierra de 40 litros. La tienda no tiene bodega, por lo que
solo puede tener un m´aximo de 3 bolsas de tierra y 4 maceteros en su establecimiento. De ahora en adelante
se asumir´a que la tienda vende solo estos dos productos.
Los clientes llegan a la tienda seg´un un Proceso de Poisson con tasa λ > 0 clientes por hora. Con probabili-
dad p1 un cliente compra un macetero, con probabilidad p2 compra una bolsa de tierra y con probabilidad
p3 compra ambos productos (donde 0 < p1, p2, p3 < 1 y p1 + p2 + p3 = 1). Considera que dichas probabi-
lidades son independientes del Proceso de Poisson y del stock de productos en tienda. Considera tambi´en
que si llega un cliente y no encuentra el/los productos que quiere, este simplemente se va. En particular, si
llega un cliente que quiere comprar un macetero y una bolsa de tierra, pero solo queda un tipo de producto,
el cliente se ir´a y no comprar´a del producto que s´ı hay.
La tienda compra sus productos al mismo proveedor, el cual solo puede entregar tres productos a la vez.
Por ende, la tienda adopt´o la siguiente pol´ıtica de inventario: cada vez que quedan dos o menos maceteros y
dos o menos bolsas de tierra, se piden dos maceteros y una bolsa de tierra. Por ejemplo, se emite una orden
al proveedor si quedan dos maceteros y una bolsa de tierra, pero no se emite la orden si no hay maceteros
y quedan tres bolsas de tierra.
Considera que el tiempo entre que se piden los productos al proveedor y que estos lleguen tiene una
distribuci´on Exponencial con tasa µ > 0 pedidos por hora. Asume que estos tiempos son independientes
del proceso de llegada, del stock en tienda y de la cantidad de productos pedidos de cada tipo. Adem´as,
asume que la tienda opera de forma continua (24 horas al d´ıa, todos los d´ıas de la semana). A partir de lo
anterior, responda:
(a) Se desea modelar el stock de maceteros y bolsas de tierra como una CMTC {X(t) ∈Ω, t ≥0}. Defina
X(t) y el conjunto (o espacio) de estados Ω.
Soluci´on: Se define las variables de estado como:
X(t) := (stock maceteros, stock bolsa de tierra)
y
Ω= {0, . . . , 4} × {0, . . . , 3}
Nota: A × B son todos los pares posibles de elementos de A con B
(b) Calcule todas las tasas de permanencia νi y tasas de transici´on instant´aneas qij para cualquier i, j ∈Ω,
con i ̸= j. Puedes dejar la soluci´on expresada de forma gr´afica y/o como f´ormulas matem´aticas que
distingan todos los casos posibles.
Soluci´on: Se define,
λ1 = λp1
λ2 = λp2
λ3 = λp3
Las tasas de transici´on inst´antaneas son las siguientes:
q(i,j)(i−1,j−1)
=
λ3,
∀i ∈{1, 2, 3, 4}, j ∈{1, 2, 3}
q(i,j)(i,j−1)
=
λ2,
∀i ∈{0, 1, 2, 3, 4}, j ∈{1, 2, 3}
q(i,j)(i−1,j)
=
λ1,
∀i ∈{1, 2, 3, 4}, j ∈{0, 1, 2, 3}
q(i,j)(i+2,j+1)
=
µ,
∀i ∈{0, 1, 2}, j ∈{0, 1, 2}
De manera gr´afica,
6

Por otro lado, las tasas de permanencia son las siguientes,
v(0,0)
=
µ
v(0,j)
=
λp2 + µ
∀j ∈{1, 2}
v(0,3)
=
λp2
v(i,0)
=
λp1 + µ
∀i ∈{1, 2}
v(i,0)
=
λp1
∀i ∈{3, 4}
v(i,j)
=
λ + µ
∀i, j ∈{1, 2}
v(i,j)
=
λ
∀i ∈{3, 4}, j ∈{1, 2}
v(i,3)
=
λ
∀i ∈{1, . . . , 4}
(c) Escriba las ecuaciones de equilibrio de largo plazo de la CMTC.
Soluci´on:
Para cada (i, j) ∈Ω= {0, . . . , 4} × {0, . . . , 3} se cumple:
Pi,j v(i,j) = λ1 1{i+1≤4} Pi+1,j+λ2 1{j+1≤3} Pi,j+1+λ3 1{i+1≤4, j+1≤3} Pi+1,j+1+µ 1{i−2≥0, j−1≥0} Pi−2,j−1,
donde v(i,j) es la tasa de permanencia y λ1 = λp1, λ2 = λp2, λ3 = λp3. En forma expl´ıcita:
7

(i, j) = (0, 0) :
P0,0v(0,0) = λ1P1,0 + λ2P0,1 + λ3P1,1,
(i, j) = (0, 1) :
P0,1v(0,1) = λ1P1,1 + λ2P0,2 + λ3P1,2,
(i, j) = (0, 2) :
P0,2v(0,2) = λ1P1,2 + λ2P0,3 + λ3P1,3,
(i, j) = (0, 3) :
P0,3v(0,3) = λ1P1,3,
(i, j) = (1, 0) :
P1,0v(1,0) = λ1P2,0 + λ2P1,1 + λ3P2,1,
(i, j) = (1, 1) :
P1,1v(1,1) = λ1P2,1 + λ2P1,2 + λ3P2,2,
(i, j) = (1, 2) :
P1,2v(1,2) = λ1P2,2 + λ2P1,3 + λ3P2,3,
(i, j) = (1, 3) :
P1,3v(1,3) = λ1P2,3,
(i, j) = (2, 0) :
P2,0v(2,0) = λ1P3,0 + λ2P2,1 + λ3P3,1,
(i, j) = (2, 1) :
P2,1v(2,1) = λ1P3,1 + λ2P2,2 + λ3P3,2 + µP0,0,
(i, j) = (2, 2) :
P2,2v(2,2) = λ1P3,2 + λ2P2,3 + λ3P3,3 + µP0,1,
(i, j) = (2, 3) :
P2,3v(2,3) = λ1P3,3 + µP0,2,
(i, j) = (3, 0) :
P3,0v(3,0) = λ1P4,0 + λ2P3,1 + λ3P4,1,
(i, j) = (3, 1) :
P3,1v(3,1) = λ1P4,1 + λ2P3,2 + λ3P4,2 + µP1,0,
(i, j) = (3, 2) :
P3,2v(3,2) = λ1P4,2 + λ2P3,3 + λ3P4,3 + µP1,1,
(i, j) = (3, 3) :
P3,3v(3,3) = λ1P4,3 + µP1,2,
(i, j) = (4, 0) :
P4,0v(4,0) = λ2P4,1,
(i, j) = (4, 1) :
P4,1v(4,1) = λ2P4,2 + µP2,0,
(i, j) = (4, 2) :
P4,2v(4,2) = λ2P4,3 + µP2,1,
(i, j) = (4, 3) :
P4,3v(4,3) = µP2,2.
4
X
i=0
3
X
j=0
Pi,j = 1,
Pi,j ≥0.
(d) En el largo plazo, ¿qu´e fracci´on de clientes logra comprar (al menos un producto) y qu´e fracci´on se
va sin comprar?
Soluci´on: Sea Pi,j la probabilidad estacionaria de estar con i maceteros y j bolsas. Un cliente compra
si: quiere s´olo macetero y i ≥1; quiere s´olo tierra y j ≥1; quiere ambos y i ≥1, j ≥1. Por tanto,
s
|{z}
fracci´on de llegadas atendidas
= p1
4
X
i=1
3
X
j=0
Pi,j + p2
4
X
i=0
3
X
j=1
Pi,j + p3
4
X
i=1
3
X
j=1
Pi,j.
La fracci´on que se va sin comprar es 1 −s.
8

