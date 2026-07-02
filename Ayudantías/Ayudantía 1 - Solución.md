Pontificia Universidad Cat´olica de Chile
Escuela de Ingenier´ıa
Departamento de Ingenier´ıa Industrial y de Sistemas
ICS2123 – Modelos Estoc´asticos
Profesores Ver´onica Godoy y Andr´es Navarro
Ayudante Jefe Joaqu´ın Vergara
Primer Semestre 2026
Ayudant´ıa 1:
Repaso de Probabilidades
Ayudantes: Emilio Pe˜na (emilio.penasepulveda@uc.cl) & Mart´ın Pe˜na (martinpena@uc.cl)
Resumen
Propiedades b´asicas
⋄Probabilidad del complemento: P(E) = 1 −P(E)
⋄Probabilidad del vac´ıo: P(∅) = 0
⋄Probabilidad para la uni´on de dos eventos: P(E ∪F) = P(E) + P(F) −P(E ∩F)
Si E y F son disjuntos (E ∩F = ∅), entonces: P(E ∪F) = P(E) + P(F)
⋄Sea E y F tal que E ⊆F, entonces: P(F) = P(F\E) + P(E), P(E) ≤P(F)
Probabilidad condicional
Sean E, F ⊆Ωeventos cualquiera. Se denota P(E|F) a la probabilidad de que ocurra el evento E dado que
ocurri´o F, y se tiene que satisface la siguiente relaci´on:
P(E|F) = P(E ∩F)
P(F)
Probabilidades totales
Sean E1, E2, ..., En eventos mutuamente excluyentes (es decir, Ei ∩Ej = ∅∀i ̸= j), tal que Sn
i=1 Ei = Ωy
F un evento cualquiera de Ω, entonces:
P(F) =
n
X
i=1
P(F|Ei) · P(Ei)
Teorema de Bayes (simple)
Sean E y F dos eventos de Ω. Se tiene que:
P(E|F) = P(F|E) · P(E)
P(F)
Teorema de Bayes (completo)
Sean E1, E2, ..., En eventos mutuamente excluyentes tal que Sn
i=1 Ei = Ωy sea F tal que P(F) > 0.
Entonces:
P(Ei|F) =
P(F|Ei) · P(Ei)
Pn
i=1 P(F|Ei) · P(Ei)
1

Eventos independientes
Diremos que los eventos E y F son independientes si y solo si
P(E|F) = P(E)
Que es equivalente, por Ley de Probabilidad Condicional, a:
P(E ∩F) = P(F) · P(E)
Variable Aleatoria
Es una funci´on X : Ω→R, que a cada elemento del espacio muestral le asigna un n´umero real. Puede ser:
⋄Discreta: toma una cantidad numerable de valores.
⋄Continua: toma valores en un conjunto continuo (no numerable).
Funci´on de Distribuci´on Acumulada
Para cada v.a X, se define su funci´on de distribuci´on acumulada (o ”cdf”) como:
FX(x) = P(X ≤x)
Esta funci´on caracteriza a la variable aleatoria X, es decir, identificando la cdf podemos reconocer a que
variable aleatoria corresponde, al igual que las siguientes funciones.
Funci´on de Probabilidad
Si X es una v.a discreta, se define como:
pX(xi) = P(X = xi)
de manera que
X
i∈ΦX
pX(xi) = 1
donde ΦX ⊆N es el soporte de X, es decir los valores tales que pX ̸= 0.
Funci´on de Densidad
Si X es una v.a continua, se define como:
fX(x) = dFX(x)
dx
de manera que
∞
Z
−∞
fX(x)dx =
Z
ΦX
fX(x)dx = 1,
fX(x) ≥0 ∀x ∈R
donde, nuevamente ΦX ⊆R es el soporte de X, dicho de otra manera donde fX ̸= 0.
Adem´as,
FX(x) =
x
Z
−∞
f(t)dt
2

y
P(a ≤X ≤b) =
b
Z
a
f(t)dt = F(a) −F(b)
M´as generalmente, una funci´on de densidad puede ser cualquier funci´on no negativa y continua a tramos
que integre 1.
3

Problema 1
En un sistema de monitoreo de un supermercado, se estudia el tiempo continuo que transcurre hasta la
llegada del pr´oximo cliente en las cajas. Se sabe que existen dos tipos de clientes: habituales (Tipo A) y
express (Tipo B).
Sean X e Y las variables aleatorias continuas que representan el tiempo (en minutos) que transcurre hasta
la llegada del pr´oximo cliente Tipo A y Tipo B, respectivamente. Se asume que las llegadas de ambos tipos
de clientes son eventos independientes. Las funciones de densidad de probabilidad para cada variable est´an
dadas por:
fX(x) =
(
αe−αx
si x ≥0
0
en otro caso
fY (y) =
(
βe−βy
si y ≥0
0
en otro caso
donde α > 0 y β > 0 son par´ametros conocidos del sistema.
a) Calcule la probabilidad de que el pr´oximo cliente, sin importar de qu´e tipo sea, llegue despu´es de t
minutos (t > 0). Exprese su resultado en funci´on de α, β y t.
Soluci´on:
Para que el pr´oximo cliente (ya sea A o B) llegue despu´es de t minutos, debe ocurrir
simult´aneamente que el tiempo de llegada del cliente Tipo A sea mayor a t y el tiempo de llegada del
cliente Tipo B sea mayor a t. Definiendo los eventos E = {X > t} y F = {Y > t}, nos piden calcular
P(E ∩F).
Dado que el enunciado establece que la llegada de los clientes son eventos independientes, utilizamos
la propiedad de independencia:
P(E ∩F) = P(X > t) · P(Y > t)
Primero, calculamos la Funci´on de Distribuci´on Acumulada (CDF) para la variable X, es decir,
P(X ≤t):
FX(t) =
Z t
0
fX(x)dx =
Z t
0
αe−αxdx =

−e−αxt
0 = 1 −e−αt
Usando la propiedad de la probabilidad del complemento, P(E) = 1 −P(E), tenemos:
P(X > t) = 1 −P(X ≤t) = 1 −(1 −e−αt) = e−αt
Por analog´ıa, para la variable Y :
P(Y > t) = 1 −(1 −e−βt) = e−βt
Finalmente, multiplicamos ambas probabilidades:
P(X > t ∩Y > t) = e−αt · e−βt = e−(α+β)t
b) Suponga que han transcurrido s minutos (0 < s < t) y el sistema le informa que a´un no ha llegado
ning´un cliente Tipo B. Dado este escenario, ¿cu´al es la probabilidad de que el primer cliente Tipo B
llegue despu´es de t minutos? Justifique anal´ıticamente cada paso.
Soluci´on: Nos piden calcular una probabilidad condicional. Queremos saber la probabilidad de que
Y > t dado que ya sabemos que ocurri´o el evento Y > s. Utilizando la definici´on de probabilidad
condicional:
P(Y > t|Y > s) = P({Y > t} ∩{Y > s})
P(Y > s)
Aqu´ı debemos analizar la intersecci´on de los eventos {Y > t} y {Y > s}. Dado que s < t, cualquier
valor de Y que sea mayor que t ser´a, por obligaci´on, mayor que s. En t´erminos de conjuntos, {Y >
t} ⊆{Y > s}. Luego, {Y > t} ∩{Y > s} = {Y > t}.
4

Reemplazando esto en nuestra ecuaci´on:
P(Y > t|Y > s) = P(Y > t)
P(Y > s)
Utilizando los resultados del inciso anterior para la probabilidad del complemento de la CDF:
P(Y > t|Y > s) = e−βt
e−βs = e−βt−(−βs) = e−β(t−s)
c) El administrador del supermercado nota que la tasa de llegada β de los clientes Tipo B var´ıa seg´un
el clima. Si el d´ıa est´a soleado (evento S), la funci´on de densidad de Y utiliza el par´ametro β1. Si el
d´ıa est´a lluvioso (evento L), utiliza el par´ametro β2. Se sabe hist´oricamente que la probabilidad de
que un d´ıa est´e lluvioso es p. Si usted observa en las c´amaras que el primer cliente Tipo B tard´o m´as
de t minutos en llegar, ¿cu´al es la probabilidad de que hoy sea un d´ıa lluvioso?
Soluci´on: Definamos los eventos involucrados:
⋄E: El cliente Tipo B llega despu´es de t minutos, es decir, {Y > t}.
⋄L: El d´ıa est´a lluvioso, con P(L) = p.
⋄S: El d´ıa est´a soleado, con P(S) = 1 −p (por probabilidad del complemento, ya que S = L).
Nos piden calcular la probabilidad condicional de la causa dado el efecto observado: P(L|E). Para
esto, utilizamos el Teorema de Bayes:
P(L|E) = P(E|L) · P(L)
P(E)
Del enunciado y del inciso (a), sabemos las probabilidades condicionales de que el cliente tarde m´as
de t minutos dependiendo del clima:
⋄P(E|L) = e−β2t
⋄P(E|S) = e−β1t
Para calcular la probabilidad total del evento E (P(E)), notamos que los eventos L y S son mutua-
mente excluyentes y su uni´on conforma el espacio muestral completo (Ω). Por lo tanto, aplicamos el
Teorema de Probabilidades Totales:
P(E) = P(E|L) · P(L) + P(E|S) · P(S)
P(E) = e−β2t · p + e−β1t · (1 −p)
Finalmente,
P(L|E) =
e−β2t · p
e−β2t · p + e−β1t · (1 −p)
Esta expresi´on representa la probabilidad actualizada de que est´e lloviendo, habiendo incorporado la
evidencia del tiempo de llegada del cliente.
5

Problema 2
El Centro de Meteorolog´ıa UC desarroll´o un aparato para medir la cantidad de mm de agua que caen en
un d´ıa de lluvia en el campus, con el fin de tomar las medidas correspondientes. Cuando se sobrepasan
los 10 mm, existe riesgo de que la infraestructura se vea afectada, lo que ocurre con una probabilidad del
45 %. Sin embargo, el aparato a´un est´a en fase de prueba y falla en la medici´on un 15 % de las veces, de
forma independiente a la cantidad de agua ca´ıda. Cuando falla, indica que se super´o el nivel de riesgo con
probabilidad 0.6 y que no se super´o con probabilidad 0.4. A partir de lo anterior, responda:
a) ¿Cu´al es la probabilidad de que el aparato indique que se sobrepas´o el l´ımite?
Soluci´on: Sean los siguientes eventos:
⋄S: Se sobrepas´o el l´ımite de 10mm
⋄F: Falla el aparato
⋄R: El aparato indica que se sobrepasaron los 10mm
Como datos tenemos P(S) = 0.45, P(F) = 0.15, P(R|F) = 0.6 y P( ¯R|F) = 0.4. Por lo tanto lo pedido
se resuelve:
P(R) = P(R|F)P(F) + P(R| ¯F)P( ¯F) = P(R|F)P(F) + P(S)P( ¯F) = 0.6 · 0.15 + 0.45 · 0.85 = 0.4725
b) Si el aparato indica que se sobrepas´o el l´ımite ¿Cu´al es la probabilidad de que efectivamente se haya
sobrepasado ese d´ıa?
Soluci´on: Se nos pide:
P(S|R) = P(S ∩R)
P(R)
= P(R|S) · P(S)
P(R)
= P(R|S) · 0.45
0.4725
Descomponemos el condicional considerando la ocurrencia de una falla:
P(R|S) = P(R|S ∩F) · P(F|S) + P(R|S ∩¯F) · P( ¯F|S) = 0.6 · 0.15 + 1 · 0.85 = 0.94
Por lo tanto:
P(S|R) = 0.94 · 0.45
0.4725
= 0.895
c) ¿Cu´al es la probabilidad de que el aparato registre lo realmente ocurrido?
Soluci´on: Sea:
⋄C: El aparato registra lo correcto
⋄C = (S ∩R) ∪( ¯S ∩¯R)
Se nos pide:
P(C) = P(C|F)P(F) + P(C| ¯F)P( ¯F)
La primera parte de la expresi´on:
P(C|F) = P((S ∩R) ∪( ¯S ∩¯R)|F) = P(S ∩R|F) + P( ¯S ∩¯R|F)
= P(S|F)P(R|S ∩F) + P( ¯S|F)P( ¯R| ¯S ∩F)
= 0.45 · 0.6 + 0.55 · 0.4 = 0.49
Por otro lado, por definici´on se tiene que P(C| ¯F) = 1. Por ´ultimo:
P(C) = 0.49 · 0.15 + 1 · 0.85 = 0.9235
6

Problema 3
Un equipo de ingenieros de datos deportivos est´a dise˜nando un modelo estoc´astico predictivo para la final
de un torneo de f´utbol. Para modelar la cantidad de goles que anota cada equipo durante los 90 minutos
reglamentarios, definen las siguientes variables aleatorias:
⋄X: Cantidad de goles anotados por el Equipo A.
⋄Y : Cantidad de goles anotados por el Equipo B.
A partir del an´alisis de datos hist´oricos, los ingenieros determinan que X e Y se pueden modelar mediante
funciones de probabilidad de Poisson con tasas α y β respectivamente (donde α, β > 0). Adem´as, asumen
que la cantidad de goles que anota un equipo no afecta la cantidad de goles que anota el otro, por lo que
X e Y son variables aleatorias independientes.
a) La probabilidad de que el Equipo A gane el partido con un marcador exacto de 3 a 1.
Soluci´on: Nos piden calcular la probabilidad conjunta del evento donde el Equipo A anota exacta-
mente 3 goles y el Equipo B anota exactamente 1 gol. Sea E = {X = 3} y F = {Y = 1}.
Por la propiedad de eventos independientes, sabemos que P(E ∩F) = P(E) · P(F).
Dado que X e Y son variables aleatorias discretas con distribuci´on Poisson, sabemos que:
pX(3) = P(X = 3) = e−α α3
3!
pY (1) = P(Y = 1) = e−β β1
1!
Por lo tanto, la probabilidad solicitada es el producto de ambas:
P(X = 3, Y = 1) =

e−α α3
3!

·

e−β β
1!

= e−(α+β) α3β
6
b) La probabilidad marginal de que el Equipo A gane el partido durante los 90 minutos reglamentarios
(es decir, que anote estrictamente m´as goles que el Equipo B).
Soluci´on:
El evento de inter´es es G = {X > Y }. Definimos los eventos mutuamente excluyentes
Ek = {Y = k} para k ∈{0, 1, 2, . . . }, los cuales forman una partici´on del espacio muestral Ω(ya que
S∞
k=0{Y = k} = Ω). Aplicando el teorema de probabilidades totales para el evento G:
P(X > Y ) =
∞
X
k=0
P(X > Y |Y = k) · P(Y = k)
Sustituyendo la condici´on Y = k en la probabilidad condicional, obtenemos:
P(X > Y ) =
∞
X
k=0
P(X > k|Y = k) · P(Y = k)
Dado que X e Y son independientes, P(X > k|Y = k) = P(X > k). Reemplazando:
P(X > Y ) =
∞
X
k=0
P(X > k) ·

e−β βk
k!

Luego,
P(X > k) =
∞
X
j=k+1
P(X = j) =
∞
X
j=k+1
e−α αj
j!
Finalmente, reemplazando esta expresi´on en la sumatoria exterior, obtenemos la expresi´on completa:
P(X > Y ) =
∞
X
k=0


∞
X
j=k+1
e−α αj
j!

e−β βk
k!
7

c) Suponga que el partido acaba de terminar y el sensor del estadio reporta que, en total, hubo n goles
en el partido (n ≥1), pero por una falla de transmisi´on no se sabe qui´en los anot´o. Dado este evento,
encuentre la probabilidad de que el Equipo A haya ganado el partido.
Soluci´on: Definamos el evento F = {X +Y = n} (ocurrieron n goles en total) y queremos encontrar
la probabilidad de que el Equipo A gane, es decir E = {X > Y }.
Por definici´on de probabilidad condicional:
P(X > Y |X + Y = n) = P({X > Y } ∩{X + Y = n})
P(X + Y = n)
Primero, condicionaremos sobre los goles del Equipo A (evento Ei = {X = i} para i desde 0 hasta
n):
P(X + Y = n) =
n
X
i=0
P(X + Y = n|X = i) · P(X = i)
=
n
X
i=0
P(Y = n −i|X = i) · P(X = i)
Por independencia de X e Y , P(Y = n −i|X = i) = P(Y = n −i). Luego:
P(X + Y = n) =
n
X
i=0

e−β βn−i
(n −i)!
 
e−α αi
i!

= e−(α+β) 1
n!
n
X
i=0
n!
i!(n −i)!αiβn−i
Reconociendo el coeficiente binomial
 n
i

, y usando el Teorema del Binomio de Newton, el denominador
es:
P(X + Y = n) = e−(α+β) (α + β)n
n!
Por otro lado, si sabemos que X + Y = n, la condici´on para que gane el Equipo A (X > Y ) implica
que X > n −X, lo que equivale a 2X > n, es decir, X > n
2 . Definamos m = ⌊n
2 ⌋+ 1 (el m´ınimo
entero estrictamente mayor a la mitad de los goles). El evento conjunto ocurre cuando X toma un
valor k (desde m hasta n) e Y toma el valor restante n −k.
P(X > Y, X + Y = n) =
n
X
k=m
P(X = k, Y = n −k)
(Por independencia)
=
n
X
k=m
P(X = k) · P(Y = n −k)
=
n
X
k=m
e−α αk
k! e−β
βn−k
(n −k)!
Sustituimos el numerador y el denominador en la expresi´on condicional inicial:
P(X > Y |X + Y = n) =
Pn
k=m e−(α+β) αkβn−k
k!(n−k)!
e−(α+β) (α+β)n
n!
=
n
X
k=m
n!
k!(n −k)!
αkβn−k
(α + β)n
=
n
X
k=m
n
k
 
α
α + β
k 
β
α + β
n−k
Lo que demuestra que condicionado a n eventos totales, la distribuci´on de los goles de un equipo sigue
una distribuci´on Binomial con probabilidad de ´exito p =
α
α+β .
8

