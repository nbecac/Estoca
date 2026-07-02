Pontificia Universidad Cat´olica de Chile
Escuela de Ingenier´ıa
Departamento de Ingenier´ıa Industrial y de Sistemas
ICS2123 – Modelos Estoc´asticos
Profesores Ver´onica Godoy y Andr´es Navarro
Ayudante Jefe Joaqu´ın Vergara
Primer Semestre 2026
Ayudant´ıa 3:
Proceso Poisson II
Ayudantes: Emilio Pe˜na (emilio.penasepulveda@uc.cl) & Mart´ın Pe˜na (martinpena@uc.cl)
Resumen
Proceso de Conteo
Un proceso {N(t), t ≥0} es un proceso de conteo si N(t) representa el n´umero de eventos que han ocurrido
en el intervalo [0, t]. Algunas propiedades b´asicas son:
⋄N(t) es un entero no negativo.
⋄Si s < t, entonces N(s) ≤N(t) (N es una funci´on no decreciente).
⋄Si N(s, t) es el n´umero de eventos en el intervalo ]s, t], entonces: N(s, t) est´a dado por N(t) −N(s).1
Incrementos Independientes
El proceso de conteo {N(t), t ≥0} tiene incrementos independientes si para cualquier t, s ∈R+ la v.a.
N(s, s + t) es independiente del proceso {N(u), 0 ≤u ≤s}. Por lo tanto, el n´umero de eventos en
intervalos disjuntos son independientes. Por consiguiente, para cualquier u ∈[0, s] y k, r ∈Z+ se
tiene:
P(N(s, s + t) = k|N(u) = r) = P(N(s, s + t) = k)
Incrementos Estacionarios
El proceso de conteo {N(t), t ≥0} tiene incrementos estacionarios si la distribuci´on de probabilidades de
N(s, s + t) no depende de s. Es decir, la distribuci´on depende del largo del intervalo de tiempo y
no de su ubicaci´on temporal. Por tanto, para cualquier par s′, s ∈R+ y k ∈R+ fijo:
P(N(s, s + t) = k) = P(N(s′, s′ + t) = k)
Propiedad de orden
El proceso de conteo {N(t), t ≥0} tiene la propiedad de orden si cumple:
⋄P(N(h) = 1) = λh + o(h)
⋄P(N(h) ≥2) = o(h)
En otras palabras, si despreciamos el t´ermino o(h), y consideramos h muy peque˜no,
N(h) ≈
(
0 con probabilidad 1 −λh,
1 con probabilidad λh
En particular, el proceso solamente tendr´a “saltos” unitarios.
1Extra´ıdo de material del curso ICS2123
1

Proceso de Poisson
Un proceso de conteo {N(t), t ≥0} es un Proceso de Poisson con tasa λ > 0 si cumple con:
⋄Incrementos independientes.
⋄Incrementos estacionarios.
⋄Propiedad de orden.
N(t) ∼Poisson(λt) →P(N(t) = k) = (λt)ke−λt
k!
Distribuci´on del tiempo entre eventos en un Proceso de Poisson
Los tiempos entre eventos consecutivos en un Proceso de Poisson son variables aleatorias independientes e
id´enticamente distribuidas (iid) que siguen una distribuci´on Exponencial con par´ametro λ. En particular,
para cualquier i ∈N :
Ti ∼Exp(λ) →P(Ti ≥t) = e−λt, t ≥0
T´ıpicamente denotaremos Ti al tiempo transcurrido desde el (i −1)-´esimo evento hasta el i-´esimo evento.
Resultado Inverso
Si un Proceso de Conteo satisface Ti
iid
∼Exp(λ), luego corresponde a un Proceso Poisson de tasa λ.
P´erdida de Memoria
La distribuci´on exponencial posee falta de memoria. Es decir no importa cuanto tiempo haya pasado desde
la ocurrencia del ´ultimo evento, la distribuci´on del tiempo hasta la ocurrencia del siguiente seguir´a siendo
la misma. Es decir, si X ∼Exp(λ):
P(X > s + t|X > s) = P(X > t)
Tiempo de Ocurrencia del k-´esimo evento
Si Sk es el tiempo transcurrido hasta que ocurre el k-´esimo evento Poisson N(t), entonces se tiene que:
Sk = T1 + T2 + ... + Tk ∼Gamma(k, λ)
fSk(x) = e−λxλkxk−1
Γ(k)
FSk(x) = 1 −
k−1
X
j=0
e−λx (λx)j
j!
La relaci´on entre un Proceso Poisson y el tiempo de ocurrencia del k-´esimo evento se escribe como:
P(N(t) ≥k) = P(Sk ≤t)
Relaci´on distribuci´on Binomial y Proceso de Poisson
⋄Considere que N(u) | N(t) = n ∼Binomial(n, p = u
t ) cuando 0 < u < t.
⋄Esta idea se puede generalizar para intervalos que no necesariamente comienzan desde el origen (por
la propiedad de incrementos estacionarios).
Por tanto consideremos que N(a) −N(b) | N(c) −N(d) = n ∼Binomial(n, p = a −b
c −d) cuando
d < b < a < c.
2

Suma y Descomposici´on Proceso de Poisson
⋄Sea N(t), t ≥0 un Proceso de Poisson con tasa λ > 0. Supongamos que cada evento de este proceso
es, de forma independiente, de tipo 1, con probabilidad p ∈(0, 1) y de tipo 2, con probabilidad 1 −p.
Sea Ni(t), t ≥0 el proceso que cuenta los eventos de tipo i = 1, 2. Entonces se puede demostrar
que N1(t), t ≥0 es un Proceso de Poisson con tasa λp y N2(t), t ≥0 es un Proceso de Poisson con
tasa λ(1 −p). Adem´as N1(t), t ≥0 y N2(t), t ≥0 son procesos independientes. Esta idea se puede
generalizar para la descomposici´on en k ∈N≥2 tipo de eventos.
⋄Sea N1(t), N2(t), . . . , Nk(t), t ≥0, procesos Possion independientes con tasas λ1, λ2, . . . , λk > 0 res-
pectivamente, entonces el proceso N(t) = N1(t) + N2(t) + . . . + Nk(t) es un proceso Poisson con tasa
λ = λ1 + λ2 + . . . + λk.
3

Problema 1
Usted administra una farmacia en la que decide tener solo una caja habilitada. Despu´es de un tiempo
observando la llegada de clientes a su farmacia, determina que los tiempos de llegada entre cada cliente
distribuyen seg´un una distribuci´on Exponencial (en horas) con media de
1
λ donde λ en una constante
positiva. Se le pide determinar expresiones para:
(a) La probabilidad de que entre la segunda y la s´eptima hora lleguen entre 6 y 10 clientes, si se sabe
que la persona n´umero 15 en llegar lo hizo antes de la hora n´umero 20 de atenci´on.
Soluci´on: Debido a que los tiempos entre eventos distribuyen Exponencial el conteo de eventos se
modela seg´un un Proceso Poisson con tasa λ. Adem´as sea Sk el tiempo de ocurrencia del k-´esimo
evento, se nos pide calcular:
P(10 ≥N(7) −N(2) ≥6 | S15 ≤20)
Debido a la relaci´on que existe entre Sk y N(t) se puede reescribir la expresi´on de la siguiente manera:
P(10 ≥N(7) −N(2) ≥6 | S15 ≤20) = P(10 ≥N(7) −N(2) ≥6 | N(20) ≥15)
Para evitar las desigualdades, las reemplazamos por sumatorias, donde al reemplazar el termino
condicionado aparece un termino adicional por reglas del condicional.
P(10 ≥N(7) −N(2) ≥6 | N(20) ≥15) =
10
X
i=6
P(N(7) −N(2) = i | N(20) ≥15)
=
10
X
i=6
∞
X
k=15
P(N(7) −N(2) = i | N(20) = k) · P(N(20) = k | N(20) ≥15)
=
10
X
i=6
∞
X
k=15
P(N(7) −N(2) = i | N(20) = k) · P(N(20) = k , N(20) ≥15)
P(N(20) ≥15)
=
10
X
i=6
∞
X
k=15
P(N(7) −N(2) = i | N(20) = k) · P(N(20) = k)
P(N(20) ≥15)
En el primer termino, el intervalo condicionado tiene contenido al intervalo del lado izquierdo, por lo
que se puede aplicar la propiedad de la Binomial. En este caso, los par´ametros corresponden a n = k,
p = 7−2
20 = 1
4, por lo que la expresi´on resulta en:
=
10
X
i=6
∞
X
k=15
k
i

(1
4)i(1 −1
4)k−i ·
(20λ)ke−20λ
k!
P∞
j=15
(20λ)je−20λ
j!
(b) El valor esperado del tiempo de llegada del 2do cliente. Luego comp´arelo con la esperanza del tiempo
de llegada del 2do cliente dado que a la cuarta hora llegaron 2 clientes.
Soluci´on: La primera expresi´on solicitada corresponde a E[S2] la cual es una distribuci´on Gamma(2, λ),
por lo que su esperanza es: E[S2] = 2
λ.
Por otro lado, la esperanza dado que ya conocemos que llegaron 2 clientes corresponde a E[S2 |
N(4) = 2] la cual es m´as compleja. Esta corresponde a los estad´ısticos de orden, por lo que para
calcularlo primero necesitamos definir:
• S′
1 : Tiempo de llegada de cliente n´umero 1 dado que en t = 4 llegaron 2 ∼Uniforme(0, 4).
• S′
2 : Tiempo de llegada de cliente n´umero 2 dado que en t = 4 llegaron 2 ∼Uniforme(0, 4).
Cabe destacar que la persona 1 no es necesariamente la que llego primera, sino que es solo su n´umero
asociado para poder diferenciarlas.
Al encontrarse en desorden ambos distribuyen Uniforme, pero no sabemos espec´ıficamente cual llegar´a
2do, por lo que debemos encontrar el m´aximo entre ambas.
4

P(X ≤x) = P(max{S′
1, S′
2} ≤x) = P(S′
1 ≤x, S′
2 ≤x) = P(S′
1 ≤x) · P(S′
2 ≤x) = x
4 · x
4 = x2
16
Por lo tanto para obtener la funci´on densidad derivamos la distribuci´on acumulada.
fX(x) = d
dxP(X ≤x) = d
dx
x2
16 = x
8
Por ´ultimo, para obtener la esperanza, la calculamos usando su definici´on con la funci´on densidad.
E[X] =
Z 4
0
xfX(x)dx =
Z 4
0
x2
8 dx = 43
3 · 8 = 8
3
c) Suponga que son las 14:30 y que farmacia entra en hora de almuerzo, por lo cual cierra sus puertas
hasta las 15:00. Todas las personas que llegan en ese momento se quedan en la fila esperando a que
vuelva a abrir, ¿cual es el tiempo esperado de espera en la fila hasta que vuelve a abrir la farmacia?
Soluci´on: Debido a la perdida de memoria, las llegadas de clientes siguen correspondiente al Proceso
de Poisson N(t) donde t = 0 ahora son las 14:30 y t = 0.5 son las 15:00.
El tiempo de espera promedio no es m´as que la suma de todos los tiempos de espera divido en el
total de personas, lo que se representa como:
T =
N(0.5)
P
k=1
(0.5 −Sk)
N(0.5)
Por lo tanto, lo pedido se calcula aplicando probabilidades totales:
E[T] =
∞
X
n=0
E[T | N(0.5) = n] · P(N(0.5) = n) =
∞
X
n=0
E[
N(0.5)
P
k=1
(0.5 −Sk)
N(0.5)
| N(0.5) = n] · P(N(0.5) = n)
=
∞
X
n=0
E[
nP
k=1
(0.5 −Sk)
n
| N(0.5) = n] · P(N(0.5) = n) =
∞
X
n=0
(0.5 −E[
nP
k=1
Sk
n
| N(0.5) = n]) · P(N(0.5) = n)
El termino de la esperanza de los Sk dado que ya se conoce que ocurrieron n eventos en su intervalo
de tiempo distribuye como los estad´ısticos de orden de n variables Uniforme(0, 0.5), que luego al
sumarlos, deja de importar el orden en que se encuentran, dejando la siguiente expresi´on:
E[
nP
k=1
Sk
n
| N(0.5) = n] = E[
nP
k=1
U(k)
n
| N(0.5) = n] = E[
nP
k=1
Uk
n
| N(0.5) = n]
= E[
nP
k=1
0.25
n
| N(0.5) = n] = 0.25
Por lo tanto concluimos que:
E[T] =
∞
X
n=0
(0.5 −0.25) · P(N(0.5) = n) = 0.25
∞
X
n=0
P(N(0.5) = n) = 0.25
5

Problema 2
Por el regreso a clases, el “Achoclonados´´ tendr´a ofertas exclusivas, donde ofrecer´an pizzas, sushi y em-
panadas. Suponga que las llegadas de personas al local pueden modelarse seg´un un Procesos de Poisson
de tasa λ > 0 personas por hora. Adem´as se sabe que la probabilidad de que una persona cualquiera elija
pizza es p > 0, de que elija sushi es q > 0 y de que elija empanadas es r > 0 donde p + q + r = 1. Se le pide
responder las siguientes preguntas:
(a) Obtenga la distribuci´on de probabilidad de la cantidad total de personas que llegan a comprar al
Achoclonados entre la 3era y la 5ta hora dado que en las primeras 8 horas llegaron 20 personas a
comprar empanadas.
Soluci´on: Definiremos:
⋄N(t): n´umero de personas que han llegado a comprar hasta tiempo t ∼Poisson(λt)
Dado que cada persona que llega elije uno de los 3 posibles alimentos, se pueden modelar la llegada de
personas para cada uno de estos como una descomposici´on del proceso original, por ende, se define:
⋄Np(t): n´umero de personas que han llegado a comprar pizzas hasta tiempo t ∼Poisson(pλt).
⋄Ns(t): n´umero de personas que han llegado a comprar sushi hasta tiempo t ∼Poisson(qλt)
⋄Ne(t): n´umero de personas que han llegado a comprar empanadas hasta tiempo t ∼Poisson(rλt)
Con esto, se nos pide obtener la distribuci´on de N(5) −N(3) | Ne(8) = 20 para ello calculamos:
P(N(5) −N(3) = n | Ne(8) = 20) = P(Np+s(5) −Np+s(3) + Ne(5) −Ne(3) = n | Ne(8) = 20)
Para ello condicionamos el conteo de empanadas para poder aislarlo de la suma dentro de la proba-
bilidad:
=
n
X
k=0
P(Np+s(5) −Np+s(3) + Ne(5) −Ne(3) = n | Ne(8) = 20, Ne(5) −Ne(3) = k) · P(Ne(5) −Ne(3) = k | Ne(8) = 20)
=
n
X
k=0
P(Np+s(5) −Np+s(3) = n −k | Ne(8) = 20) · P(Ne(5) −Ne(3) = k | Ne(8) = 20)
=
n
X
k=0
P(Np+s(2) = n −k) · P(Ne(5) −Ne(3) = k | Ne(8) = 20)
La primera expresi´on es la suma del Proceso Poisson de las pizzas con el de los sushis, por lo que
corresponde a un Proceso Poisson de tasa (p + q)λt. En la segunda expresi´on, al estar el intervalo
contenido dentro del intervalo condicionado se puede aplicar la propiedad de la Binomial, quedando:
=
n
X
k=0
(2(p + q)λ)n−ke−2(p+q)λ
(n −k)!
·
20
k

(1
4)k(1 −1
4)20−k
(b) Encuentre la probabilidad de que en las primeras 4 horas lleguen 6 personas a comprar empanadas
dado que entre las horas 2 y 5 llegaron en total 20 personas.
Soluci´on: La expresi´on a desarrollar corresponde a: P(Ne(4) = 6 | N(5) −N(2) = 20)
Dado que N(t) y Ne(t) no son independientes, se debe descomponer este ´ultimo t´ermino y luego
separar los intervales de tiempo, dando lugar a la expresi´on:
6

= P(Ne(4) = 6, N(5) −N(2) = 20)
P(N(5) −N(2) = 20)
= P(Ne(4) = 6, Np+s(5) −Np+s(2) + Ne(5) −Ne(2) = 20)
P(N(5) −N(2) = 20)
=
6
X
k=0
P(Ne(4) = 6, Np+s(5) −Np+s(2) + Ne(5) −Ne(2) = 20 | Ne(4) −Ne(2) = k) · P(Ne(4) −Ne(2) = k)
P(N(3) = 20)
=
6
X
k=0
P(Ne(2) = 6 −k, Np+s(5) −Np+s(2) + Ne(5) −Ne(4) = 20 −k) · P(Ne(2) = k)
P(N(3) = 20)
=
6
X
k=0
P(Ne(2) = 6 −k) · P(Np+s(5) −Np+s(2) + Ne(5) −Ne(4) = 20 −k) · P(Ne(2) = k)
P(N(3) = 20)
=
6
X
k=0
20−k
X
i=0
P(Ne(2) = 6 −k) · P(Np+s(5) −Np+s(2) + Ne(5) −Ne(4) = 20 −k | Ne(5) −Ne(4) = i) · P(Ne(5) −Ne(4) = i) · P(Ne(2) = k)
P(N(3) = 20)
=
6
X
k=0
20−k
X
i=0
P(Ne(2) = 6 −k) · P(Np+s(5) −Np+s(2) = 20 −k −i) · P(Ne(1) = i) · P(Ne(2) = k)
P(N(3) = 20)
=
6
X
k=0
20−k
X
i=0
(2rλ)6−ke−2rλ
(6−k)!
· (3(p+q)λ)20−k−ie−3(p+q)λ
(20−k−i)!
· (rλ)ie−rλ
i!
· (2rλ)ke−2rλ
k!
(3λ)20e−3λ
20!
7

Problema 3 [T1- 2025-2]
Suponga que uno de sus conocidos se encuentra trabajando en el puerto de embarque de barcos de Puerto
Chalupa. Este puerto opera con n > 1 compa˜n´ıas navieras todos los d´ıas de la semana de 08:00 a 20:00.
Le piden realizar un estudio del comportamiento de los barcos y de los marineros con el fin de mejorar la
eficiencia del servicio brindado.
Para lograr su cometido, una primera revisi´on estad´ıstica le permiti´o concluir que el tiempo de llegada entre
cada barco de la compa˜n´ıa i ∈{1, . . . , n} distribuye Exponencial de par´ametro λi > 0 barcos por hora.
Adem´as, la llegada de los marineros corresponde a un Proceso de Poisson de par´ametro α > 0 marineros
por hora. Suponga que los tiempos de llegada de los barcos son todos independientes e independientes de
la llegada de los marineros.
Considere que solo quedan dos barcos en el puerto, uno de la compa˜n´ıa 1 y otro de la compa˜n´ıa 2, cada uno
con capacidad para M ∈Z+ marineros m´as. Con probabilidad p ∈(0, 1), los marineros que lleguen decidir´an
tomar el barco de la compa˜n´ıa 1, y con probabilidad 1 −p el de la compa˜n´ıa 2. Antes de partir, en el barco
de la compa˜n´ıa 1, el capit´an esperar´a un tiempo que distribuye Uniforme(a, b) con 0 < a < b, en minutos,
mientras que en el barco de la compa˜n´ıa 2, el capit´an esperar´a un tiempo que distribuye Exponencial de
par´ametro β > 0, en minutos. Considere que si llega un marinero y el barco de su preferencia ya no est´a
disponible, simplemente se va. Una vez los barcos partieron, determine la probabilidad de que el barco de
la compa˜n´ıa 1 haya recibido al menos r ∈Z+ veces el n´umero de marineros que recibi´o el barco de la
compa˜n´ıa 2.
Soluci´on: Definamos los siguientes Procesos de Poisson
⋄N1(t): N´umero de personas que han llegado a subirse al barco de la compa˜n´ıa 1 hasta el tiempo t. Es
un Proceso de Poisson de tasa αp, as´ı N1(t) ∼P(p · αt).
⋄N2(t): N´umero de personas que han llegado a subirse al barco de la compa˜n´ıa 2 hasta el tiempo t. Es
un Proceso de Poisson de tasa α(1 −p), as´ı N2(t) ∼P((1 −p) · αt).
An´alogamente, consideremos las siguientes variables aleatorias
⋄U: Tiempo en que sale el barco de la compa˜n´ıa 1 del terminal. U ∼Uniforme(a, b).
⋄V : Tiempo en que sale el barco de la compa˜n´ıa 2 del terminal. V ∼Exp(β).
Notemos que para responder lo solicitado se requiere de
P (N1(U) ≥rN2(V ))
Se desarrolla con probabilidades totales
P (N1(U) ≥rN2(V )) =
M
X
k=0
P (N1(U) ≥rN2(V )|N2(V ) = k) · P(N2(V ) = k)
=
M
X
k=0
P (N1(U) ≥rk) · P(N2(V ) = k)
=
M
X
k=0
"Z b
a
P(N1(U) ≥rk|U = u) · fU(u)du
#
·
Z ∞
0
P(N2(V ) = k|V = v) · fV (v)dv

=
M
X
k=0
"Z b
a
P(N1(u) ≥rk) ·
1
b −adu
#
·
Z ∞
0
P(N2(v) = k) · βe−βvdv

=
M
X
k=0
"Z b
a
( M
X
i=rk
(p · αu)i e−p·αu
i!
)
·
1
b −adu
#
·
Z ∞
0
((1 −p) · αv)k e−(1−p)·αv
k!
· βe−βvdv

8

