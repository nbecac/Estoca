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
b) Escriba una expresi´on para el costo esperado de un vuelo de 10 horas.
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
(b) Plantee las ecuaciones de equilibrio de largo plazo para la CMTC anterior y derive la relaci´on recur-
siva para los Pn.
(c) Suponiendo conocidas las probabilidades estacionarias y considerando un per´ıodo de una hora, ¿Cu´antos
clientes en promedio llegan al cine y deciden ni siquiera intentar hacer la fila?
(d) Argumente bajo qu´e condiciones el sistema no colapsar´ıa en el largo plazo (Enti´endase colapsar como
llegar a tener infinitas personas en el sistema)
4

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
(b) Calcule todas las tasas de permanencia νi y tasas de transici´on instant´aneas qij para cualquier i, j ∈Ω,
con i ̸= j. Puedes dejar la soluci´on expresada de forma gr´afica y/o como f´ormulas matem´aticas que
distingan todos los casos posibles.
(c) Escriba las ecuaciones de equilibrio de largo plazo de la CMTC.
(d) En el largo plazo, ¿qu´e fracci´on de clientes logra comprar (al menos un producto) y qu´e fracci´on se
va sin comprar?
5

