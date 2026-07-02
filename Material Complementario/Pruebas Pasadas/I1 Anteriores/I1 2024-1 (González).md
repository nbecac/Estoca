Pontificia Universidad Cat´olica de Chile
Escuela de Ingenier´ıa
Departamento de Ingenier´ıa Industrial y de Sistemas
ICS2123 Modelos Estoc´asticos
Profesor Maximiliano Gonz´alez R.
Primer Semestre 2024
Interrogaci´on 1
Tiempo total: 2 horas
Problema 1 (40 puntos)
a) (5 puntos) La probabilidad de que un neum´atico desgastado de auto sufra un pinchazo un d´ıa cualquiera es de
0.05 si se utiliza en asfalto, y de dos quintos si se utiliza en tierra y en asfalto. Cuatro de cada cinco autos con un
neum´atico desgastado circulan ´unicamente en caminos de asfalto, mientras que el porcentaje restante utiliza tambi´en
los de tierra. Suponga que usted encontr´o un auto con un neum´atico desgastado, pero no estaba pinchado. ¿Cu´al es
la probabilidad de que el auto haya circulado por caminos de tierra ese d´ıa?
b) (5 puntos) Un juego consiste en lanzar sucesivamente un dado. Los instantes en que se lanza el dado corresponden
a los instantes de ocurrencia de eventos de un Proceso de Poisson con tasa λ (lanzamientos por minuto). En cada
lanzamiento se aplica la siguiente regla: si el resultado del dado es impar, se gana esa cantidad de puntos, y si el
resultado del dado es par, se pierde esa cantidad de puntos. Determine el valor esperado del total de puntos que se
acumulan en el intervalo [0, x] (donde x > 0 y x est´a en minutos).
c) (5 puntos) Suponga que la ocurrencia de terremotos en Chile se puede modelar como un proceso de Poisson de tasa
λ eventos por cada 10 a˜nos. Calcule la probabilidad de que los pr´oximos n terremotos ocurran con una separaci´on de
no m´as de t a˜nos entre ellos.
d) (5 puntos) Sean X e Y variables aleatorias independientes con distribuci´on Poisson de par´ametros α y β, respecti-
vamente. Calcule el valor esperado del m´aximo entre X e Y condicionando en que X + Y = 5.
Para los incisos e) al h) considere un proceso de Poisson de tasa λ eventos por minuto.
e) (5 puntos) Si se sabe que han ocurrido al menos dos eventos en los primeros tres minutos. Calcule la probabilidad
de que en los primeros tres minutos ocurran m´as de 5 eventos.
f) (5 puntos) Si se sabe que n ≤N(1) ≤n + 4, donde n es un entero no negativo, calcule la probabilidad de que en el
intervalo [0, 1/4] (en minutos) no haya ocurrido ning´un evento.
g) (5 puntos) Calcule P(Sn ≤x ∩Sn+3 > x) para x > 0 y n > 0.
h) (5 puntos) Sean los instantes de tiempo x, y y t tales que 0 < x < y < t. Demuestre que
P(S1 ≤x, S2 ≤y|N(t) = 2) = 2xy −x2
t2
.
Hint: Recuerde la relaci´on entre FSk(t) y N(t).
Luego, dado t = 5 minutos, asigne al menos dos valores a x y dos valores a y (razonables), e interprete los valores
obtenidos para la probabilidad.
Problema 2 (20 puntos)
a) Suponga que usted est´a evaluando colocar un nuevo restaurante en una concurrida calle de Santiago de Janeiro. Para
atraer clientes usted decide colocar un gran y luminoso cartel, adem´as de contar con promotores que invitan a los
peatones a probar este nuevo lugar.

Suponga que los peatones transitan por el frente de su local seg´un un proceso de Poisson de tasa α personas por hora.
Adem´as, por esta calle circulan dos tipos de veh´ıculo: autos particulares y buses de turismo, cuyo paso tambi´en se
modela como un proceso de Poisson de tasas β y µ veh´ıculos por hora, respectivamente.
Usted ha notado que los promotores son muy efectivos, logrando que dos quintas partes de los peatones pasen a probar
el local, mientras que en el caso de los veh´ıculos (autos y buses), solo un 10% de ellos se detiene en el local y prueban
la comida.
Finalmente, luego de un exhaustivo an´alisis, usted logr´o determinar que los autos particulares transportan 1, 2, 3 o
4 personas con probabilidad 0.3, 0.5, 0.15 y 0.05 respectivamente, mientras que los buses de turismo transportan una
cantidad de pasajeros que distribuye Uniforme(10, 19).
i) (5 puntos) Si cada cliente le significa en promedio una ganancia $q, ¿cu´al es la ganancia esperada en una hora
de funcionamiento?
ii) (5 puntos) Suponga α = 20, β = 8 y µ = 5. ¿Qu´e porcentaje de eficacia debiesen tener al menos los promotores
para que en promedio visiten el local m´as peatones que clientes de buses de turismo?
b) Luego de una exitosa apertura de su restaurante, usted ha comenzado a notar que muchos otros emprendedores le han
”echado el ojo” a su negocio y han decidido abrir sus propios restaurantes en la misma calle, lo que ha aumentado la
competencia por captar clientes.
Sin embargo, usted tiene la ventaja que ha tenido m´as tiempo para analizar el proceso de llegada de clientes y emplear
sus conocimientos de Modelos Estoc´asticos. Gracias a ello, usted ha identificado que las tasas de los distintos tipos de
clientes no son constantes a lo largo del d´ıa, es m´as, los clientes sin importar su medio de transporte arriban a comer
a su restaurante seg´un un proceso de Poisson de tasa λ(t) =
1
t + 2 con t en horas. Es decir, a medida que avanza el
d´ıa, m´as competencia hay y menos clientes llegan en promedio a su local.
Suponiendo que el local funciona desde las 9 de la ma˜nana (t = 0), hasta la media noche:
i) (5 puntos) Calcule el valor esperado del n´umero de pedidos que llegan entre entre el mediod´ıa y las 3 de la
tarde.
ii) (5 puntos) Calcule la probabilidad de que entre las 12:00 y las 18:00 lleguen m´as de 20 personas dado que al
almuerzo (1 a 4 p.m) llegaron exactamente 10 personas.

Pontificia Universidad Cat´olica de Chile
Escuela de Ingenier´ıa
Departamento de Ingenier´ıa Industrial y de Sistemas
ICS2123 – Modelos Estoc´asticos
Profesor Maximiliano Gonz´alez R.
Primer Semestre 2024
Pauta Interrogaci´on 1
Soluci´on Problema 1
(a) Definiremos los siguientes eventos:
• A: Un auto con neum´atico desgastado circula ´unicamente por caminos de asfalto.
• T: Un auto con neum´atico desgastado circula por caminos de tierra y asfalto.
• X: Un neum´atico desgastado de auto sufre un pinchazo.
Nos dan las siguientes probabilidades:
• P(A) = 4
5
• P(T) = 1
5
• P(X|A) = 0.05
• P(X|T) = 2
5
Luego, nos piden
P(T| ¯X)
Usando el teorema de Bayes, se tiene que
P(T| ¯X) =
P( ¯X|T)P(T)
P( ¯X|A)P(A) + P( ¯X|T)P(T)
Con P( ¯X|A) = 1 −P(X|A) = 0.95 y P( ¯X|T) = 1 −P( ¯X|T) = 3
5. Finalmente,
P(T| ¯X) =
0.6 · 0.2
0.95 · 0.8 + 0.6 · 0.2 = 0.1363
(b) Definimos las siguientes variables aleatorias:
• Nx: Cantidad de lanzamientos efectuados en el intervalo [0, x].
• Bi: Beneficio obtenido por el lanzamiento del i-´esimo dado.
Sabemos que Nx ∼Poisson(λx) y la distribuci´on de Bi es la siguiente:
P(Bi = x) = 1
6,
x ∈{1, −2, 3, −4, 5, −6}
Con esperanza
E[Bi] = 1 −2 + 3 −4 + 5 −6
6
= −1
2
Finalmente, los puntos totales vienen dados por:
Z =
Nx
X
i=1
Bi
Luego, usando esperanzas iteradas y que las variables aleatorias Bi son independientes entre s´ı, se
tiene que

E[Z] = E[E[Z|Nx]]
= E
"
E
" Nx
X
i=1
Bi
Nx
##
= E
" Nx
X
i=1
E[Bi]
#
= −1
2E[Nx]
= −λx
2
(c) Definimos N(t): como la cantidad de terremotos que han ocurrido en [0, t], con t en a˜nos, por lo
que se debe convertir la tasa a˜nos:
λ
10
terremotos
a˜no
. Por lo tanto, N(t) ∼Poisson ( λ
10). Finalmente, nos
piden,
P(max{T1, . . . , Tn} < t) = P(T1 < t, . . . , Tn < t)
=
n
Y
i=1
P(Ti < t)
=
n
Y
i=1
(1 −e−λt
10 )
= (1 −e−λt
10 )n
(d)
E[max{X, Y }|X + Y = 5] =
5
X
i=3
i · P(max{X, Y } = i|X + Y = 5)
=
5
X
i=3
i · P(max{X, Y } = i, X + Y = 5)
P(X + Y = 5)
=
5!
(α + β)5e−(α+β)
5
X
i=3
i · P(max{X, Y } = i, X + Y = 5)
=
5!
(α + β)5e−(α+β)
5
X
i=3
i · (P(X = i)P(Y = 5 −i) + P(Y = i)P(X = 5 −i))
(e) Definimos N(t) como el n´umero de eventos que han ocurrido hasta t. N(t) ∼Poisson(λt). Nos piden,
P(N(3) > 5|N(3) ≥2) = P(N(3) > 5, N(3) ≥2)
P(N(3) ≥2)
= P(N(3) > 5)
P(N(3) ≥2)
=
1
P∞
j=2
(3λ)je−3λ
j!
∞
X
i=6
(3λ)ie−3λ
i!
=
1
1 −e3λ −3λe−3λ
 
1 −
5
X
i=0
(3λ)ie−3λ
i!
!
(f) Nos piden,
P(N(1/4) = 0|n ≤N(1) ≤n + 4) = P(N(1/4) = 0, n ≤N(1) ≤n + 4)
P(n ≤N(1) ≤n + 4)

= P(N(1/4) = 0, n ≤N(1) −N(1/4) ≤n + 4)
P(n ≤N(1) ≤n + 4)
= P(N(1/4) = 0)P(n ≤N(3/4) ≤n + 4)
P(n ≤N(1) ≤n + 4)
= e−λ
4
n+4
X
i=n
e−3λ
4 ( 3
4λ)i
i!
n+4
X
j=n
e−λλj
j!
=
n+4
X
i=n
( 3
4λ)i
i!
n+4
X
j=n
λj
j!
(g) Nos piden,
P(Sn ≤x ∩Sn+3 > x) = P(n ≤N(x) ∩N(x) < n + 3)
= P(n ≤N(x) < n + 3)
=
n+2
X
i=n
(λx)ie−λx
i!
(h) Nos piden
P(S1 ≤x, S2 ≤y|N(t) = 2) = P(N(x) ≥1, N(y) = 2|N(t) = 2)
= P(N(x) ≥1, N(y) = 2)
P(N(t) = 2)
= P(N(x) = 1, N(y) = 2)
P(N(t) = 2)
+ P(N(x) = 2, N(y) = 2)
P(N(t) = 2)
=
2
X
i=1
P(N(x) = i, N(y) −N(x) = 2 −i, N(t) −N(y) = 0)
P(N(t) = 2)
=
2
(λt)2e−λt

λxe−λxλ(y −x)e−λ(y−x)e−λ(t−y) + (λx)2e−λx
2
e−λ(y−x)e−λ(t−y)

=
2
λ2t2e−λt

λ2x(y −x)e−λt + λ2x2
2
e−λ(t)

= 2xy −x2
t2
+ x2
t2
= 2xy −x2
t2

Soluci´on Problema 2
(a)
i) La ganancia esperada corresponder´a a la suma de las ganancias esperadas por cada proceso
Poisson. Podemos definir los siguientes procesos:
{Np(t), t ≥0} proceso Poisson(α) −→tr´ansito de peatones frente al local
{Na(t), t ≥0} proceso Poisson(β) −→tr´ansito de autos particulares frente al local
{Nb(t), t ≥0} proceso Poisson(µ) −→tr´ansito de buses de turismo frente al local
Para el proceso de tr´ansito de peatones, la ganancia esperada en una hora de funcionamiento
corresponde a:
E[Gp] = E[Np(1)] · 2
5 · $q
= α · 2
5 · $q
Luego, para el proceso de tr´ansito de autos identificamos que este corresponde a un proceso de
Poisson compuesto, por lo que el tr´ansito de pasajeros frente al local en realidad corresponde a:
Za(t) =
Na(t)
X
i=1
Xi
donde Xi es la cantidad de pasajeros en el auto particular.
Adem´as, sabemos que:
E[Za(t)] = E[Xi] · E[Na(t)]
Con esto, la cantidad esperada de pasajeros que transitan frente al local en autos particulares,
durante una hora de funcionamiento es:
E[Za(1)] = E[Xi] · E[Na(1)]
= (1 · 0, 3 + 2 · 0, 5 + 3 · 0, 15 + 4 · 0, 05) · β
= 1, 95 · β
Considerando que solo un 10% de los autos se detiene, la ganancia esperada es:
E[Ga] = E[Za(1)] · 0, 1 · $q
= 1, 95 · β · 0, 1 · $q
= 0, 195 · β · $q
De manera similar, el proceso de tr´ansito de buses de turismo tambi´en corresponde a un proceso
de Poisson compuesto:
Zb(t) =
Nb(t)
X
i=1
Yi
donde Yi es la cantidad de pasajeros en el bus de turismo.
As´ı, la cantidad esperada de pasajeros que transitan frente al local en buses de turismo, durante
una hora de funcionamiento es:
E[Zb(1)] = E[Yi] · E[Nb(1)]
= 10 + 19
2
· µ
= 14, 5 · µ
Considerando que solo un 10% de los buses se detiene, la ganancia esperada es:
E[Gb] = E[Zb(1)] · 0, 1 · $q

= 14, 5 · µ · 0, 1 · $q
= 1, 45 · µ · $q
Finalmente, la ganancia total esperada es:
E[G] = E[Gp + Ga + Gb]
= E[Gp] + E[Ga] + E[Gb]
= $q(0, 4 · α + 0, 195 · β + 1, 45 · µ)
ii) Para que en promedio visiten el local m´as peatones que clientes de buses de turismo, se necesita
cumplir que:
p · E[Np(t)] ≥0, 1 · E[Zb(t)]
donde p es la eficacia de los promotores.
Del inciso anterior sabemos:
E[Np(t)] = α · t
E[Zb(t)] = 14, 5 · µ · t
Por lo tanto, despejando p se tiene:
p ≥0, 1 · 14, 5 · µ · t
α · t
Reemplazando con los valores del enunciado:
p ≥0, 3625
Con esto, los promotores deben tener un porcentaje de eficacia de al menos 36,25% para que en
promedio visiten el local m´as peatones que clientes de buses de turismo.
(b)
i) {X(t), t ≥0} proceso Poisson(λ(t)) −→llegada de clientes al restaurante
Nos piden:
E(N(15:00) −N(12:00))
= m(6) −m(3)
Con m(t) =
R t
0 λ(t)dt
m(6) −m(3) =
Z 6
3
λ(t)dt
=
Z 6
3
1
t + 2dt
= ln(t + 2)

6
3
= ln(8) −ln(5)
≈0, 47
ii) La probabilidad que nos piden es la siguiente:
P(N(18:00) −N(12:00) > 20 | N(16:00) −N(13:00) = 10)
Por probabilidad condicional tenemos:
P(N(18:00) −N(12:00) > 20 , N(16:00) −N(13:00) = 10)
P(N(16:00) −N(13:00) = 10)
Utilizando una l´ınea de tiempo, podemos definir intervalos disjuntos:
12:00
13:00
16:00
18:00
> 20
10
i
j −i

∞
X
j=21
j
X
i=0
P(N(18:00) −N(16:00) = j −i , N(16:00) −N(13:00) = 10 , N(13:00) −N(12:00) = i)
P(N(16:00) −N(13:00) = 10)
Por incrementos independientes:
∞
X
j=21
j
X
i=0
P(N(18:00) −N(16:00) = j −i) · P(N(16:00) −N(13:00) = 10) · P(N(13:00) −N(12:00) = i)
P(N(16:00) −N(13:00) = 10)
∞
X
j=21
j
X
i=0
P(N(18 : 00) −N(16 : 00) = j −i) · P(N(13 : 00) −N(12 : 00) = i)
=
∞
X
j=21
j
X
i=0
(e−(m(9)−m(7)) · (m(9) −m(7))j−i
(j −i)!
) · (e−(m(4)−m(3)) · (m(4) −m(3))i
i!
)
=
∞
X
j=21
j
X
i=0
(e−ln(11/9) · (ln(11/9))j−i
(j −i)!
) · (e−ln(6/5) · (ln(6/5))i
i!
)

