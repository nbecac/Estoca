Pontificia Universidad Cat´olica de Chile
Escuela de Ingenier´ıa
Departamento de Ingenier´ıa Industrial y de Sistemas
ICS2123 – Modelos Estoc´asticos
Profesor Andr´es Navarro
Primer Semestre 2026
Interrogaci´on 1
Duraci´on: 2 horas
Problema 1 (15 puntos)
Responda las siguientes preguntas de manera independiente:
(a) (5 puntos) En un remate industrial, se presentan 6 bodegas cerradas y visualmente id´enticas, donde s´olo se
distinguen por un n´umero en su puerta. Se tiene la certeza de que solo una de ellas contiene un lote de maquinaria
de alto valor, mientras que las otras 5 est´an vac´ıas. S´olo tiene dinero para adquirir una de las bodegas.
Usted, como ingeniero a cargo de la adquisici´on, selecciona inicialmente la Bodega 1. El martillero del remate, quien
conoce con exactitud el contenido de cada bodega, decide a˜nadir tensi´on al proceso: de las 5 bodegas que usted no
eligi´o, el martillero abre 4 bodegas y muestra que est´an vac´ıas. Tras este acto, solo quedan cerradas la Bodega 1
(su elecci´on original) y la Bodega 6 (una de las que usted no eligi´o). Su socio comercial le susurra: “No cambies
de decisi´on, ahora hay solo dos bodegas y la probabilidad de ganar es 50/50, as´ı que no nos conviene el riesgo del
cambio”.
¿Su compa˜nero est´a en lo correcto? Justifique con c´alculo de probabilidades.
Soluci´on:
Para evaluar la afirmaci´on del socio, definimos C1 como el evento de que el premio est´e en la bodega elegida inicial-
mente. La probabilidad a priori es P(C1) = 1/6, por lo que la probabilidad de que el premio no est´e en la Bodega 1
es P(Cc
1) = 5/6.
Al observar que el administrador abre las bodegas 2, 3, 4 y 5 (evento M), notamos que el administrador no act´ua
al azar, sino que descarta deliberadamente bodegas vac´ıas dentro del grupo que usted no eligi´o. Esto implica que si
el premio estaba originalmente en el conjunto {2, 3, 4, 5, 6}, despu´es del descarte el premio s´ı o s´ı debe estar en la
Bodega 6.
Por lo tanto, la probabilidad de ganar cambiando a la Bodega 6 es equivalente a la probabilidad de no haber acertado
inicialmente:
P(C6|M) = P(Cc
1) = 5
6 ≈83, 3%
Mientras que la probabilidad de ganar manteniendo la decisi´on sigue siendo:
P(C1|M) = P(C1) = 1
6 ≈16, 7%
Conclusi´on: El socio est´a equivocado. La probabilidad no es 50/50 porque el administrador “traspasa” toda la
probabilidad del grupo no elegido (5/6) a la ´unica bodega que dej´o cerrada (Bodega 6).
La decisi´on ´optima es
cambiar.
1

(b) (5 puntos) Sean A, B y C tres eventos definidos en un mismo espacio de probabilidad tal que A ⊆B. Suponga
que el evento C es independiente de A y tambi´en independiente de B, y que P(C) > 0. ¿es posible afirmar que
P(A|C) < P(B|C)? Justifique su respuesta.
Soluci´on:
Sabemos que A ⊆B, lo cual implica que P(A) ≤P(B)
Por definici´on de independencia, sabemos que la ocurrencia de C no altera la probabilidad de A ni de B, lo cual se
expresa matem´aticamente como:
P(A|C) = P(A)
y
P(B|C) = P(B)
Esta igualdad se deriva directamente de la definici´on de probabilidad condicional y la propiedad de independencia
(P(A ∩C) = P(A)P(C)):
P(A|C) = P(A ∩C)
P(C)
= P(A)P(C)
P(C)
= P(A)
P(B|C) = P(B ∩C)
P(C)
= P(B)P(C)
P(C)
= P(B)
Considerando lo anterior, s´olo es posible afirmar que P(A|C) ≤P(B|C) y no que P(A|C) < P(B|C)
(c) (5 puntos) el tiempo de ejecuci´on (en horas) de un proceso de optimizaci´on en un servidor se comporta como una
variable aleatoria continua X con la siguiente funci´on de densidad de probabilidad:
fX(x) =



ax + b
si 0 < x < 2
0
e.o.c.
donde a y b son constantes reales. Adem´as, se sabe que el valor esperado del tiempo de ejecuci´on es E[X] = 7
6.
I) Determine los valores de las constantes a y b. Justifique detalladamente las condiciones que deben cumplir estas
constantes para que fX(x) sea una fdp v´alida.
II) Suponga que el costo de operaci´on del servidor es C = 10X + 5. Calcule el costo esperado del proceso.
Soluci´on: a) Para que fX(x) sea una fdp v´alida, debe cumplir dos condiciones:
(a) fX(x) ≥0 para todo x en su dominio.
(b)
R ∞
−∞fX(x)dx = 1.
Aplicando la segunda condici´on:
Z 2
0
(ax + b)dx =
ax2
2
+ bx
2
0
= 2a + 2b = 1 =⇒a + b = 1
2
(Ecuaci´on 1)
Usando el dato del valor esperado E[X] = 7/6:
Z 2
0
x(ax + b)dx =
Z 2
0
(ax2 + bx)dx =
ax3
3
+ bx2
2
2
0
= 8
3a + 2b = 7
6
(Ecuaci´on 2)
Multiplicando la Ecuaci´on 1 por 2, tenemos 2a + 2b = 1. Restando esta a la Ecuaci´on 2:
8
3 −2

a = 7
6 −1 =⇒2
3a = 1
6 =⇒a = 3
12 = 1
4
Sustituyendo a en la Ecuaci´on 1:
1
4 + b = 1
2 =⇒b = 1
4.
2

b) Usando la propiedad de linealidad de la esperanza:
E[C] = E[10X + 5] = 10E[X] + 5
Sustituyendo el valor dado E[X] = 7/6:
E[C] = 10
7
6

+ 5 = 70
6 + 30
6 = 100
6
= 50
3 ≈16, 67
3

Problema 2 (20 puntos)
A un centro de distribuci´on regional llegan solicitudes de despacho de fruta siguiendo un Proceso de Poisson con una
tasa de λ = 8 solicitudes por hora. Cada solicitud puede pedir una carga de 2, 3 o 4 unidades de fruta, con probabilidades
0,2; 0,5 y 0,3, respectivamente. El tama˜no de cada pedido es independiente entre s´ı e independiente del proceso de llegada.
(a) (5 puntos) Si se registra que durante la primera hora de operaci´on se despach´o un total de 20 unidades, determine
el valor esperado de unidades que se solicitar´an en la siguiente media hora de funcionamiento.
Soluci´on:
Sea S(t) el total de unidades solicitadas hasta el tiempo t. Se busca determinar E[S(1, 5) −S(1) | S(1) = 20].
Por la propiedad de incrementos independientes del proceso de Poisson, lo ocurrido en la primera hora no afecta
el futuro del proceso. Por lo tanto:
E[S(1, 5) −S(1) | S(1) = 20] = E[S(1, 5) −S(1)]
Debido a la estacionariedad, el valor esperado en un intervalo de media hora (∆t = 0, 5) es simplemente:
E[S(0, 5)] = E[N(0, 5)] · E[D]
Donde:
• E[N(0, 5)] = λ · t = 8 · 0, 5 = 4 solicitudes.
• E[D] = (2 · 0, 2) + (3 · 0, 5) + (4 · 0, 3) = 0, 4 + 1, 5 + 1, 2 = 3, 1 unidades/solicitud.
Finalmente:
E[S(0, 5)] = 4 · 3, 1 = 12, 4 unidades
(b) (5 puntos) ¿Cu´al es la distribuci´on de probabilidades del tiempo que debe transcurrir desde el inicio del proceso
hasta que se observe una orden por 4 frutas?
Soluci´on: Sea {N(t), t ≥0} el proceso de llegada de ´ordenes con tasa λ = 8 [´ordenes/hora]. Definimos el evento de
inter´es como la llegada de una orden de tipo 4 (4 fruta), cuya probabilidad es p4 = 0, 3.
Por la propiedad de descomposici´on de un proceso de Poisson, el flujo de ´ordenes de 4 art´ıculos, {N4(t), t ≥0}, es
tambi´en un proceso de Poisson con tasa:
λ4 = λ · p4 = 8 · 0, 3 = 2, 4 [´ordenes/hora]
Sea T4 el tiempo hasta la primera orden de 4 art´ıculos. Por la relaci´on entre el proceso de Poisson y los tiempos entre
arribos:
T4 ∼Exponencial(λ4 = 2, 4)
Su funci´on de densidad es:
fT4(t) = 2, 4 · e−2,4t,
t ≥0
Suponga ahora que, por problemas de log´ıstica, un d´ıa en particular se limita la cantidad de despachos a un m´aximo de 50
despachos por jornada. Todas las solicitudes que se reciban posteriormente deber´an ser rechazadas.
4

(c) (5 puntos) Calcule el valor esperado de la cantidad de solicitudes que ser´an rechazadas durante una jornada de 8
horas.
Soluci´on:
Sea N(t) el n´umero de solicitudes recibidas en un intervalo de tiempo de t horas. Para una jornada de
8 horas, t = 8. Por las propiedades del proceso de Poisson, N(8) se distribuye seg´un una variable de Poisson con
par´ametro α = λ · t = 8 · 8 = 64 solicitudes. Es decir, N(8) ∼Poisson(64).
Definimos R como la cantidad de solicitudes rechazadas en la jornada. Luego,
R = max(0, N(8) −50)
Utilizando la definici´on de esperanza ,
E[R] =
∞
X
k=51
(k −50)P(N(8) = k)
Reordenando,
E[R] =
∞
X
k=51
kP(N(8) = k) −50
∞
X
k=51
P(N(8) = k)
Con lo cual,
E[R] =
∞
X
k=51
k e−64 64k
k! −50
∞
X
k=51
e−64 64k
k! .
(d) (5 puntos) ¿Cu´al es la probabilidad de que se tengan que rechazar m´as de 2 solicitudes durante una jornada de 8
horas?
Soluci´on:
Siguiendo la definici´on de la parte anterior, tenemos que N(8) ∼Poisson(64) representa el n´umero total
de solicitudes que llegan durante la jornada de 8 horas.
Se requiere calcular la probabilidad de que se tengan que rechazar m´as de 2 solicitudes. Para que esto ocurra, el total
de solicitudes recibidas en el d´ıa debe superar la capacidad m´axima de la jornada (50) en estrictamente m´as de 2
unidades. Es decir, el sistema debe recibir m´as de 52 solicitudes.
Luego, buscamos la probabilidad del evento P(R > 2):
P(R > 2) = P(N(8) −50 > 2) = P(N(8) > 52)
Por simplicidad calcularemos,
P(N(8) > 52) = 1 −P(N(8) ≤52)
Por lo tanto,
P(R > 2) = 1 −
52
X
k=0
e−6464k
k!
5

Problema 3 (25 puntos)
Una empresa de retail ha decidido clasificar a sus clientes en clientes tipo A y tipo B. La raz´on de aquello es que se
pretende hacer una discriminaci´on de precios para la venta de una nueva l´ınea de camisas.
• Para los clientes de tipo A existen QA camisas en stock.
• Para los clientes de tipo B existen QB camisas en stock.
Cada cliente, independiente del tipo que sea, comprar´a solo una camisa. El precio cobrado a los clientes tipo A ser´a fijo e
igual a P. En cambio, para los clientes de tipo B se cobrar´a un precio creciente Bi si se trata de la i-´esima camisa vendida
dentro de las QB almacenadas.
Se ha estudiado el comportamiento de llegada para ambos tipos de clientes, determinando que siguen procesos de Poisson
independientes con los siguientes par´ametros:
• λA [clientes/hora] para los clientes de tipo A.
• λB [clientes/hora] para los clientes de tipo B.
(a) (4 puntos) ¿A qu´e hora se espera que se agoten las camisas tipo A?
Soluci´on:
Sea NA(t) el proceso de Poisson que describe la llegada de clientes tipo A con tasa λA clientes por hora.
Las camisas tipo A se agotan cuando llega el cliente n´umero QA. El tiempo hasta la QA-´esima llegada en un proceso
de Poisson corresponde al tiempo de arribo TQA.
Sabemos que
TQA =
QA
X
i=1
Ti
donde Ti ∼Exp(λA) son los tiempos entre llegadas, independientes.
Por lo tanto,
E[TQA] =
QA
X
i=1
E[Ti] = QA · 1
λA
(b) (5 puntos) Si en las primeras 6 horas han llegado M clientes en total, ¿cu´al es la probabilidad que k de ellos hayan
sido de tipo A?
Soluci´on:
P(NA(6) = k|NT (6) = M) = P(NA(6) = k ∧NT (6) = M)
P(NT (6) = M)
= P(NA(6) = k) · P(NB(6) = M −k)
P(NT (6) = M)
=
(6λA)k·e−6λA
k!
· (6λB)M−k·e−6λB
(M−k)!
(6(λA+λB))M·e−6(λA+λB)
M!
=
M
k
 
λA
λA + λB
k
·

λB
λA + λB
M−k
6

(c) (8 puntos) ¿Cu´al es la probabilidad de que se vendan exactamente k camisas para los clientes de tipo B, antes de
que se agoten las camisas para los clientes de tipo A?
Hint: al momento de vender la ´ultima camisa para cliente tipo A se han vendido exactamente k camisas del tipo B
Soluci´on:
Sean NA(t) y NB(t) procesos de Poisson independientes. La probabilidad b de que un cliente que llega sea de tipo B
es:
b =
λB
λA + λB
Para que se vendan exactamente k camisas de tipo B antes de agotar las QA de tipo A, debe ocurrir que entre los
primeros (QA + k −1) clientes, exactamente k sean de tipo B, y que el cliente n´umero (QA + k) sea obligatoriamente
de tipo A.
Definiendo ρk como esta probabilidad:
ρk =
QA −1 + k
k

bk(1 −b)QA−1 · (1 −b)
Sustituyendo b:
ρk =
QA + k −1
k
 
λB
λA + λB
k 
λA
λA + λB
QA
Ahora suponga que la empresa no quiere que sus clientes se vayan con las manos vac´ıas, por lo que decide entregarles un
regalo a cualquier cliente que haya llegado, hayan comprado una camisa o no. Los clientes que llegan se ordenan en una fila
para recibir el obsequio, el cual es entregado por un promotor en un tiempo exponencialmente distribuido con media 1/µ
horas, no importando el tipo de cliente de que se trata. Asuma que los clientes llegan donde el promotor seg´un el mismo
proceso de llegada a la tienda de la empresa y que el promotor atiende a un cliente a la vez.
(d) (8 puntos) Si el promotor est´a atendiendo a un cliente de tipo A y cuando comenz´o a atender a dicho cliente hab´ıa
solo un tipo de cliente B (y nadie m´as de tipo A) en la fila. ¿Cu´al es la distribuci´on de probabilidades del n´umero de
clientes (totales) en la cola al finalizar la atenci´on del cliente de tipo A?
Soluci´on: Llamemos P(n) a la probabilidad de que hayan n clientes en la fila justo al finalizar la atenci´on del cliente
tipo A. Llamaremos T al tiempo de atenci´on de la persona que est´a en la fila. Condicionando en la duraci´on de la
atenci´on de este cliente se tiene:
P(n) =
Z ∞
0
P(n|atenci´on dura t)fT (t)dt =
Z ∞
0
P(n|atenci´on dura t)µe−µtdt
Adem´as, ya que hay 1 cliente esperando, para que hayan n clientes en la fila al finalizar la atenci´on, deben llegar n−1
clientes durante la misma. As´ı:
P(n|atenci´on dura t) = e−t(λA+λB)(t(λA + λB))n−1
(n −1)!
Luego,
P(n) =
Z ∞
0
e−t(λA+λB)(t(λA + λB))n−1
(n −1)!
µe−µtdt
= (λA + λB)n−1µ
(λA + λB + µ)n
Z ∞
0
e−t(λA+λB+µ)(λA + λB + µ)ntn−1
(n −1)!
dt
7

= (λA + λB)n−1µ
(λA + λB + µ)n
Ya que dentro de la integral queda la densidad de una distribuci´on gamma de par´ametros n y λA + λB + µ.
Formulario Distribuciones
Distribuci´on
PDF
CDF
Esperanza
Varianza
Poisson(λ)
λxe−λ
x!
P⌊x⌋
k=0
λke−λ
k!
λ
λ
Exponencial(λ)
λe−λx
1 −e−λx
1
λ
1
λ2
Binomial(n, p)
 n
x

px(1 −p)n−x
P⌊x⌋
k=0
 n
k

pk(1 −p)n−k
np
np(1 −p)
Uniforme(a, b)
1
b−a
x−a
b−a
a+b
2
(b−a)2
12
Geom´etrica(p)
(1 −p)x−1p
1 −(1 −p)x
1
p
1−p
p2
Gamma(k, λ)
λkxk−1e−λx
Γ(k)
R x
0
λktk−1e−λt
Γ(k)
dt
k
λ
k
λ2
Normal(µ, σ2)
1
σ
√
2πe−(x−µ)2
2σ2
Φ
  x−µ
σ

µ
σ2
8

