Pontificia Universidad Cat´olica de Chile
Escuela de Ingenier´ıa
Departamento de Ingenier´ıa Industrial y de Sistemas
ICS2123 Modelos Estoc´asticos
Profesor Maximiliano Gonz´alez R.
Primer Semestre 2024
Examen
Tiempo total: 2 horas y 30 minutos
Problema 1 (13 puntos)
a) (5 pts.) Considere una moneda que al ser lanzada resulta en sello con probabilidad 0.4 y cara con probabilidad 0.6.
Considere tambi´en una variable aleatoria X que tiene una distribuci´on exponencial con par´ametro λ = 1/2 cuando la
moneda resulta en cara, y una distribuci´on normal de media 6 y desviaci´on est´andar 2 cuando la moneda resulta en
sello. Calcule la varianza de X.
b) (4 pts. c/u) Escoja 2 de las siguientes tres preguntas. Si contesta 3, se considerar´an solo dos a criterio
del/la ayudante.
Considere un proceso Poisson N(t), t ≥0 con tasa λ.
i) P(N(23) −N(16) = 9|N(20) −N(8) = 5)
ii) P(S5 ≤10|N(15) = 30)
iii) E[N(8) −N(5)|N(12) −N(4) = 10]
Problema 2 (17 puntos)
La situaci´on de venta ilegal de productos previo a las fiestas patrias se repite a˜no tras a˜no. En particular, usted est´a
analizando el caso de una comuna del litoral central donde ha logrado identificar y clasificar un d´ıa cualquiera en cuatro
situaciones comunes
⋄D´ıas de venta ”normal” de alimentos y bebidas de dudosa procedencia
⋄D´ıas donde pareciera que este comercio ilegal desapareci´o
⋄D´ıas de venta ilegal donde adem´as ocurren violentas ri˜nas entre vendedores ilegales que buscan apoderarse del negocio
⋄D´ıas donde se observa un fuerte contingente policial monitoreando la zona afectada
Este proceso ha sido analizado durante un largo tiempo, y se ha estimado que la situaci´on en un d´ıa cualquiera depende
´unicamente de lo sucedido la jornada anterior. As´ı, se sabe que:
⋄Los vendedores ”aparecen de la nada”, por lo que nunca se ha observado que el comercio desaparezca por dos d´ıas
seguidos. Al d´ıa siguiente o hay ri˜nas (lo que ocurre con probabilidad γ), o hay venta normal.
⋄La municipalidad posee recursos limitados, por lo que nunca habr´a un contingente policial a menos que el d´ıa anterior
haya existido una ri˜na. Por ello, luego de un d´ıa de venta normal el siguiente tambi´en lo ser´a con probabilidad α, o
el ambiente se tensar´a y habr´a ri˜na con probabilidad 1 −α.
⋄Luego de un d´ıa de violentas ri˜nas, al d´ıa siguiente habr´a recursos policiales para asistir con probabilidad p. En tanto,
con probabilidad q habr´a un d´ıa de venta normal (p + q < 1) y si no, incluso podr´ıa haber enfrentamientos.
⋄Cuando la polic´ıa se hace presente, los vendedores naturalmente se asustan y deciden no acudir al d´ıa siguiente para
”calmar las aguas”.

a) (5 pts.)
Modele la situaci´on de esta comuna como una CMTD. Indique el espacio de estados y dibuje el grafo
correspondiente con sus respectivas probabilidades.
b) (4 pts.) ¿Cu´al es la probabilidad de que exactamente 4 d´ıas despu´es de un operativo policial estos tengan que volver
a acudir a la zona?
c) (4 pts.) ¿Cu´antos d´ıas esperar´ıa que transcurran entre un d´ıa que no hubo ambulantes y el siguiente hecho de
violencia?
d) (4 pts.) ¿Cu´al es la probabilidad, en el largo plazo, que no se presente la misma situaci´on en dos d´ıas consecutivos?
Asuma conocida la distribuci´on correspondiente.
Problema 3 (30 puntos)
Suponga un sistema FIFO del tipo G/G/1/4 donde los tiempos entre llegadas pueden modelarse como una variable aleatoria
X acotada entre los valores x ∈[0, 1], tal que f(x) = 30x(1 −x)4. Por su parte, las atenciones tardan un tiempo que sigue
una distribuci´on Z cuya distribuci´on acumulada es
F(z) =





0
, si z <
√
8
z2 −8
, si
√
8 ≤z ≤a
1
, si z > a
a) (2 pts.) Utilizando un M´etodo Congruencial Lineal con a = 21, c = 13, m = 100 y X0 = 78, obtenga una serie de 14
variables aleatorias Uniforme(0,1).
b) (8 pts.) Utilizando la serie uniforme (en el mismo orden en que las obtuvo), genere todas las instancias posibles de
X. Para ello, desarrolle un algoritmo de aceptaci´on y rechazo adecuado. En este ´ıtem se evaluar´a la definici´on de los
pasos adecuados para llegar a dichas instancias. El siguiente punteo puede ser de ayuda
⋄Escoja adecuadamente la mejor funci´on t(x) y defina claramente el valor de c y las funciones h(x) y g(x).
⋄Identifique claramente (facilite el trabajo del/la ayudante) cu´al instancia de la uniforme est´a utilizando en cada
evaluaci´on y si se decide aceptar o rechazar dicha instancia candidata.
Aproxime todos los valores con que trabaje al segundo decimal
c) (8 pts.) Genere la misma cantidad de instancias de Z que obtuvo para X en el apartado b). Para ello, en caso
de necesitar variables Uniforme(0,1), utilice un M´etodo Congruencial Lineal con a = 6, c = 9, m = 13 y X0 = 4
Aproxime todos los valores al segundo decimal.
d) (5 pts.) Genere una tabla como la vista en clases a partir de las variables Ii (Interarrival Time, obtenida en c))
y Si (Service Time, obtenida en d)). Recuerde que el sistema tiene capacidad m´axima. En su tabla debe incluir
adicionalmente las siguientes variables.
⋄Ai: Instante de llegada del i-´esimo cliente
⋄Ti: Instante en que empieza a atenderse el i-´esimo cliente
⋄Wi: Tiempo de espera en cola del i-´esimo cliente
⋄Di: Instante de salida del i-´esimo cliente del sistema
e) (5 pts.) Para el sistema simulado, obtenga el tiempo de espera promedio en cola, la cantidad media de clientes en el
sistema y el % del tiempo que el sistema est´a lleno.

Pontificia Universidad Cat´olica de Chile
Escuela de Ingenier´ıa
Departamento de Ingenier´ıa Industrial y de Sistemas
ICS2123 – Modelos Estoc´asticos
Profesor Maximiliano Gonz´alez
Primer Semestre 2024
Pauta Examen
Soluci´on Problema 1
(a) Primero, recordemos que la varianza de una variable aleatoria se calcula de la siguiente manera:
V ar(X) = E[X2] −(E[X])2
(1 punto) Por plantear ecuaci´on de varianza correctamente.
Ahora, comenzamos buscando cada parte de la ecuaci´on, teniendo claro que X tiene dos casos:
E[X] = E[X|cara] ∗P[cara] + E[X|sello] ∗P[sello]
Sabemos la probabilidad de sello o cara (0.4 y 0.6 respectivamente), que la media de una normal
nos indica su esperanza, y que el inverso del par´ametro de una variable exponencial es su esperanza.
Entendiendo que la esperanza de X dado que salio sello se comporta como una variable normal, y
cuando sale cara, se comporta como una exponencial, calculamos:
E[X] = 0.4 · 6 + 0.6 · 2 = 3.6
(E[X])2 = 3.62 = 12.96
(1 punto) Por encontrar esperanza al cuadrado correctamente.
Ahora, para buscar la esperanza de X2, debemos buscarlo a partir de la formula planteada an-
teriormente, donde V ar(X) = E[X2] −(E[X])2, donde nuestra inc´ognita es E[X2], y sabemos el
comportamiento de nuestra variable cuando no esta al cuadrado. Para el caso de la variable normal,
donde Y N(µ, σ), y entiendo que la variable de X condicionada a un sello se comporta as´ı:
E[Y 2] = V ar[Y ] + (E[Y ])2 = σ2 + µ2 = 22 + 62 = 40
Por otro lado, podemos recordar que una variable que distribuye exponencial con tasa λ tiene varianza
1
λ2 , por lo que siguiendo la misma l´ogica del paso anterior, tomando en cuenta que X condicionada a
cara se comporta como una variable aleatoria Z Exp(λ):
E[Z2] = V ar[Z] + (E[Z])2 = 1
λ2 + ( 1
λ)2 =
1
(1/2)2 + ( 1
1/2)2 = 8
Luego, usando esperanza condicional tomando en cuenta ambos casos:
E[X2] = E[X2|sello] ∗P(sello) + E[X2|cara] ∗P(cara)
(2 puntos) Por encontrar esperanza de X cuadrada correctamente.
E[X2] = 0.4 ∗40 + 0.6 ∗8 = 20.8
Con esto, reemplazamos en la formula original del problema, y obtenemos:
V ar(X) = E[X2] −(E[X])2 = 20.8 −12.96 = 7.84
(1 punto) Por respuesta final.

(b) Sea una proceso Poisson con tasa λ:
i) Nos piden encontrar
P(N(23) −N(16) = 9|N(20) −N(8) = 5)
Podemos visualizar esto de la siguiente manera:
Luego, podemos reescribir como
= P(N(23) −N(16) = 9, N(20) −N(8) = 5)
P(N(20) −N(8) = 5)
Usando incrementos estacionario e independientes:
=
5
X
i
P(N(23) −N(20) = 9 −i, N(20) −N(16) = i, N(16) −N(8) = 5 −i)
P(N(20) −N(8) = 5)
=
5
X
i
P(N(3) = 9 −i, N(4) = i, N(8) = 5 −i)
P(N(20) −N(8) = 5)
=
5
X
i
P(N(3) = 9 −i) · P(N(4) = i) · P(N(8) = 5 −i)
P(N(12) = 5)
Utilizando la definici´on de la probabilidad de un proceso de Poisson, podemos
=
5
X
i
(3λ)(9−i) · e(−3λ)
(9 −i)!
· (4λ)i · e(−4λ)
i!
· (8λ)(5−i) · e(−8λ)
(5 −i)!
·
5!
(12λ)5 · e(−12λ)
ii) Alternativa 1
Se busca
P(S5 ≤10|N(15) = 30)
Esto se puede reescribir como:
P(N(10) ≥5|N(15) = 30)
Luego, podemos utilizar las propiedades del inciso anterior para reescribir:
=
30
X
i=5
P(N(10) = i, N(15) −N(10) = 30 −i)
P(N(15) = 30))
=
30
X
i=5
P(N(10) = i) · P(N(5) = 30 −i)
P(N(15) = 30))
=
30
X
i=5
(5λ)(30−i) · e−5λ
(30 −i)!
· (10λ)(i) · e−10λ
(i)!
·
30!
(15λ)30 · e−15λ
(1 punto) Reescribir la expresi´on correctamente.
(1 punto) Plantear correctamente la probabilidad condicional.
(1.5 puntos) Por la utilizaci´on de manera correcta de las propiedades.
(0.5 puntos) Por llegar a la expresi´on correcta.
Alternativa 2
Como se conoce el tama˜no del intervalo m´as grande y se quiere calcular la probabilidad de un
intervalo que est´a contenido en este, se puede utilizar Binomial para poder hacer el calculo.
Se busca

P(S5 ≤10|N(15) = 30)
Esto se puede reescribir como:
P(N(10) ≥5|N(15) = 30) ∼Binomial(30, 10/15)
=
30
X
i=5
30
i
 10
15
i  5
15
30−i
(1 punto) Reescribir la expresi´on correctamente.
(1 punto) Definir de manera correcta los par´ametros de la distribuci´on Binomial.
(2 puntos) Por llegar a la expresi´on correcta.
iii) Se nos pregunta sobre la esperanza de E[N(8) −N(5)|N(12) −N(4) = 10]. Considerando que
la informaci´on dada encapsula al primer termino, sabemos que se trata de una distribuci´on
binomial, con par´ametros n = 10 y p = 3
8.
Sabiendo que la esperanza de una binomial es n ∗p, tenemos que es
E[N(8) −N(5)|N(12) −N(4) = 10] = 10 · 3
8 = 3.75
(1 punto) Por explicar que se tiene que utilizar la distribuci´on Binomial.
(1 punto) Definir de manera correcta los par´ametros de la distribuci´on Binomial.
(2 puntos) Por el calculo correcto de la esperanza para una distribuci´on Binomial.

Soluci´on Problema 2
(a) Para representar la situaci´on como una cadena de Markov en tiempo discreto, se tendr´an los siguientes
estados:
• N: d´ıa normal de ventas
• R: d´ıa donde ocurre una pelea
• P: d´ıa donde llega la polic´ıa
• V: d´ıa que este vac´ıo
Luego, se podra representar de la siguiente manera:
V
N
R
P
1
α
1 −α
γ
1 −γ
p
1 −p −q
q
(2 puntos) Definici´on correcta de los estados.
(3 puntos) por definir correctamente las probabilidades de transici´on .
(b) Nos est´an pidiendo encontrar F4(P, P), o en otras palabras, la probabilidad de ir de el estado de
polic´ıa de vuelta a polic´ıa en 4 movimientos (d´ıas). Para calcular este valor, usamos la definici´on de
Fk:
F4(P, P) = PP V · F3(V, P)
F3(V, P) = PV R · F2(R, P) + PV N · F2(N, P)
F3(V, P) = PV R · PRR · PRP + PV N · PNR · PRP
F4(P, P) = PP V · (PV R · PRR · PRP + PV N · PNR · PRP )
F4(P, P) = γ(1 −p −q)p + (1 −γ)(1 −α)p
(1 punto) Por definir de manera correcta F4(P, P).
(2 puntos) Por desarrollo correcto.
(1 punto) Por llegar a la expresi´on correcta.
(c) Ahora, se busca la esperanza de d´ıas entre un d´ıa vac´ıo y uno normal (notar que no es necesario hacer
la sumatoria ya que del estado vaci´o solo se mueve a d´ıa normal):
E[T(V, R)] = 1 + PV N · E[T(N, R)]
Luego, buscamos el valor esperado de movernos de un d´ıa normal a un d´ıa con pelea (nuevamente
notar que no es necesario la sumaria ya que de un d´ıa normal, solo se puede ir a pelea o a repetir el
normal).

E[T(N, R)] = 1 + PNN · E[T(N, R)]
E[T(N, R)] =
1
1 −PNN
=
1
1 −α
Reemplazando en el valor anterior:
E[T(V, R)] = 1 + PV N ·
1
1 −α = 1 + 1 −γ
1 −α
(1 punto) Por definir de manera correcta E[T(N, R)].
(2 puntos) Por desarrollo correcto.
(1 punto) Por llegar a la expresi´on correcta.
(d) En el largo plazo, tomando por conocido la distribuci´on estacionaria, buscamos la probabilidad de
que no se repitan situaciones, y, espec´ıficamente, solo se puede repetir una pelea o un d´ıa normal de
venta. Es decir:
1 −πN · α −πR · (1 −p −q)
Tambi´en, podemos verlo desde otro punto de vista, lo cual es equivalente a la siguiente expresi´on:
πP + πD + (p + q) · πR + (1 −α) · πN
(4 puntos) Por llegar a una de las expresiones correctas.

Soluci´on Problema 3
(a) Utilizando el M´etodo Congruencia Lineal vista en clases utilizamos el algoritmo visto en clases,
reemplazamos los par´ametros en el.
Xi = (21 · Xi−1 + 13)
mod
100
Ui = Xi
100
A continuaci´on se presenta la tabla con las 14 iteraciones:
Iteraci´on
Xi
Ui
0
78
-
1
51
0.51
2
84
0.84
3
77
0.77
4
30
0.30
5
43
0.43
6
16
0.16
7
49
0.49
8
42
0.42
9
95
0.85
10
08
0.08
11
81
0.81
12
14
0.14
13
07
0.07
14
60
0.60
(1.5 puntos) Por el calculo correcto de Xi.
(1.5 punto) Por el calculo correcto de Ui.
(b) En primer lugar, se debe determinar una funci´on t(x) que acote superiormente a la funci´on f(x)
en todo su dominio. Una manera simple de realizar esto es crear una funci´on constante cuyo valor
es el m´aximo de f(x) en el dominio respectivo. Matem´aticamente se obtiene derivando la funci´on,
igualando a 0 y se eval´ua los puntos cr´ıticos:
f(x) = 30x(1 −x)4
f ′(x) = 30x(1 −x)4 −120x(1 −x)3
0 = (1 −x)3(30 −150x)
Las soluciones son x1 = 1 y x2 = 30
150. Ahora evaluamos:
f(1) = 30 · 1 · (1 −1)4 = 0
f
1
5

= 30 · 1
5 ·

1 −1
5
4
= 2.46
Por lo tanto t(x) = 2.46
Para hallar c tenemos que integrar t(x) en el dominio de f(x):
c =
Z 1
0
2.46dx = 2.46
= 2.46

Para hallar h(x) y g(x) se utiliza los visto en clases:
h(x) = t(x)
c
= 2.46
2.46
= 1
g(x) = f(x)
t(x)
= 30x(1 −x)4
2.46
Notar que h(x) corresponde a una distribuci´on Uniforme (0,1).
Finalmente utilizando la funci´on g(x), evaluamos Ui para cada i de iteraciones. Adem´as, los n´umeros
de color rojo ser´an los candidatos para aceptar o rechazar aquellas instancias.
Iteraci´on
Xi
Ui
g(Ui)
Aceptaci´on/Rechazo
0
78
-
-
-
1
51
0.51
0.36
-
2
84
0.84
0.01
U1 > g(U2) Rechazo 0.84
3
77
0.77
0.03
-
4
30
0.30
0.88
U3 ≤g(U4) Acepto 0.30
5
43
0.43
0.55
-
6
16
0.16
0.97
U5 ≤g(U6) Acepto 0.16
7
49
0.49
0.40
-
8
42
0.42
0.58
U7 ≤g(U8) Acepto 0.42
9
95
0.85
0.00
-
10
08
0.08
0.70
U9 > g(U10) Rechazo 0.08
11
81
0.81
0.01
-
12
14
0.14
0.93
U11 ≤g(U12) Acepto 0.14
13
07
0.07
0.64
-
14
60
0.60
0.19
U13 ≤g(U14) Acepto 0.60
Nota: tambi´en se considerar´a correcto si la evaluaci´on se hizo al rev´es (i.e. comparar U2 vs. g(U1)
y as´ı en adelante).
(2 puntos) Por hallar t(x) correctamente.
(1 punto) Por hallar c correctamente.
(1 punto) Por hallar h(x) correctamente.
(1 punto) Por hallar g(x) correctamente.
(3 puntos) Por utilizar el m´etodo de aceptaci´on y rechazo correctamente y encontrar de manera cor-
recta a los candidatos.
(c) Primero, encontramos la transformada de la funci´on de distribuci´on acumulada de Z. Para hacer esto,
debemos encontrar el valor de a correspondiente.
F(a) = a2 −8 = 1 −→a =
√
9 = 3
Luego, encontramos la inversa de la funci´on de distribuci´on acumulada para z ∈[
√
8, a]:
F −1(u) =
√
u + 8
Ahora, encontramos iteraciones de una variable uniforme para as´ı generar instancias de Z, tomando
en cuenta que solo hay 5 valores que fueron aceptados por el m´etodo en b) :

Iteraci´on
Xi
Ui
0
4
-
1
17
0.54
2
12
0.92
3
3
0.23
4
1
0.08
5
2
0.15
Usando estos valores, generamos 5 instancias de Z, reemplaz´andolos en la inversa encontrada:
Iteraci´on
Xi
Ui
F −1(Ui)
0
4
-
-
1
17
0.54
2.92
2
12
0.92
2.99
3
3
0.23
2.87
4
1
0.08
2.84
5
2
0.15
2.86
(1.5 puntos) Por calcular correctamente Xi.
(1.5 puntos) Por calcular correctamente Ui.
(1 punto) Por hallar F −1(u) correctamente.
(4 puntos) Por hallar F −1(Ui) correctamente.
(d) Usando las generaciones de X y Z en el inciso b y c respectivamente. I corresponde al tiempo entre
llega de los clientes, A el momento de llegada (por ende suma los valores que vienen de antes de
I), T es el momento en el que son atendidos, W es el tiempo de espera (desde que llegan hasta que
comenzar ser atendidos) y D es el instante de tiempo en que salen del sistema (desde que los parten
atendiendo m´as el tiempo de servicio):
Ai = Ai−1 + Ii
Ti = max(Di−1, Ai)
Wi = Ti −Ai
Di = Wi + Si
Ahora realizamos los c´alculos para cada persona:
Persona 1
• I1 = 0.30
• A1 = 0 + 0.30 = 0.30
• T1 = max(D0, A1) = max(0, 0.30) = 0.30
• W1 = 0.00
• S1 = 2.92
• D1 = T1 + S1 = 0 + 2.92 = 3.22
Persona 2
• I2 = 0.16
• A2 = A1 + I2 = 0.30 + 0.16 = 0.46
• T2 = max(D1, A2) = max(3.22, 0.46) = 3.22
• W2 = T2 −A2 = 3.22 −0.46 = 2.76
• S2 = 2.99
• D2 = T2 + S2 = 2.76 + 2.99 = 6.21

Persona 3
• I3 = 0.42
• A3 = A2 + I3 = 0.46 + 0.42 = 0.88
• T3 = max(D2, A3) = max(6.21, 0.88) = 6.21
• W3 = T3 −A3 = 6.21 −0.88 = 5.33
• S3 = 2.87
• D3 = T3 + S3 = 5.33 + 2.87 = 9.08
Persona 3
• I3 = 0.42
• A3 = A2 + I3 = 0.46 + 0.42 = 0.88
• T3 = max(D2, A3) = max(6.21, 0.88) = 6.21
• W3 = T3 −A3 = 6.21 −0.88 = 5.33
• S3 = 2.87
• D3 = T3 + S3 = 5.33 + 2.87 = 9.08
Persona 4
• I4 = 0.14
• A4 = A3 + I4 = 0.88 + 0.14 = 1.02
• T4 = max(D3, A4) = max(9.08, 1.02) = 9.08
• W4 = T4 −A4 = 9.08 −1.02 = 8.06
• S4 = 2.84
• D4 = T4 + S4 = 8.06 + 2.84 = 11.92
Finalmente, se realiza un cuadro resumen de lo que se pidi´o en el enunciado.
Persona
Ii
Ai
Ti
Wi
Si
Di
Entrada
cola cuando llega
cantidad en el sistema
1
0.30
0.30
0.30
0.00
2.92
3.22
S´ı
0
0
2
0.16
0.46
3.22
2.76
2.99
6.21
S´ı
0
1
3
0.42
0.88
6.21
5.33
2.87
9.08
S´ı
1
2
4
0.14
1.02
9.08
8.06
2.84
11.92
S´ı
2
3
5
0.60
1.62
No
3
4
Notar que el quinto cliente no entra al sistema puesto que llega cuando hay 4 clientes dentro.
(1.5 puntos) Por poner las f´ormulas a utilizar de manera correcta.
(3.5 puntos) Por calcular de manera correcta lo que se est´a pidiendo.
(1 punto) Por decir que la persona n´umero 5 no entra al sistema debido a que lleg´o a su capacidad.
(e) Calculamos las medidas de desempe˜nos pedidas en el enunciado:
Tiempo de espera
Wq =
4
X
i=1
Wi
N = 0 + 2.76 + 5.33 + 8.06
4
= 4.04
Cantidad media de clientes en el sistema
L =
4
X
i=1
(Di −Ai)
D4
= 2.33

Porcentaje del tiempo en que el sistema est´a lleno
%tiempo sistema lleno = D4 −A4
D4
= 0.9144 = 91.44%
(1.5 puntos) Por definir de manera correcta las 3 f´ormulas a utilizar
(3.5 puntos) Por calcular de manera correcta lo pedido.

