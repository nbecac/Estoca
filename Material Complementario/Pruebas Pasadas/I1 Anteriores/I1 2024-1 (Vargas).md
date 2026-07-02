Pontificia Universidad Cat´olica de Chile
Escuela de Ingenier´ıa
Departamento de Ingenier´ıa Industrial y de Sistemas
ICS2123-2 – Modelos Estoc´asticos
Profesor Nicol´as Vargas C.
Primer Semestre 2024
Interrogaci´on 1
Duraci´on: 2 horas y 20 minutos
Problema 1 (20 pts.)
1. Sea {N(t), t ≥0} un proceso Poisson con tasa λ > 0. Calcule:
a) (5 puntos) P(N(20) −N(10) = 50|N(18) −N(15) = 11)
b) (5 puntos) P(11 < S10 ≤15|N(20) = 50)
2. Sean X e Y variables aleatorias independientes con distribuci´on exponencial de par´ametros α y β, respectivamente.
Calcule:
a) (5 puntos) P(min{X, Y } ≤w ≤max{X, Y }), con w > 0.
b) (5 puntos) E [min{X, Y }| min{X, Y } > v], con v > 0.
Solucion Problema 1
1.
a)
P(N(20) −N(10) = 50|N(18) −N(15) = 11) = P(N(20) −N(10) = 50, N(18) −N(15) = 11)
P(N(18) −N(15) = 11)
= P(N(20) −N(10) = 50, N(18) −N(15) = 11)
P(N(18) −N(15) = 11)
= P(N(20) −N(10) = 50, N(18) −N(15) = 11) · P(N(20) −N(10) = 50)
P(N(18) −N(15) = 11) · P(N(20) −N(10) = 50)
= P(N(18) −N(15) = 11|N(20) −N(10) = 50) · P(N(20) −N(10) = 50)
P(N(18) −N(15) = 11)
= P(N(18) −N(15) = 11|N(20) −N(10) = 50) · P(N(10) = 50)
P(N(3) = 11)
=
 
50
11
!
·
 3
10
11
·

1 −3
10
39
·
e−10λ(10λ)50
50!
e−3λ(3λ)11
11!
b)
P(11 < S10 ≤15|N(20) = 50) = P(N(11) ≤9, N(15) ≥10|N(20) = 50)
= P(N(11) = 9, N(15) ≥10, N(20) = 50)
P(N(20) = 50)
1

=
9
X
j=0
P(N(11) = j, N(15) ≥10, N(20) = 50)
P(N(20) = 50)
=
9
X
j=0
50−j
X
k=0
P(N(11) = j, N(15) −N(11) = k, N(20) = 50)
P(N(20) = 50)
=
9
X
j=0
50−j
X
k=0
P(N(11) = j, N(15) −N(11) = k, N(20) −N(15) = 50 −j −k)
P(N(20) = 50)
=
9
X
j=0
50−j
X
k=0
P(N(11) = j) · P(N(15) −N(11) = k) · P(N(20) −N(15) = 50 −j −k)
P(N(20) = 50)
=
9
X
j=0
50−j
X
k=0
P(N(11) = j) · P(N(4) = k) · P(N(5) = 50 −j −k)
P(N(20) = 50)
=
9
X
j=0
50−j
X
k=0
e−11λ(11λ)j
j!
· e−4λ(4λ)k
k!
· e−5λ(5λ)50−j−k
(50 −j −k)!
e−20λ(20λ)50
50!
2.
a)
P(min{X, Y } ≤w ≤max{X, Y }) = P(min{X, Y } ≤w ≤max{X, Y }|X < Y ) · P(X < Y )
+ P(min{X, Y } ≤w ≤max{X, Y }|X ≥Y ) · P(X ≥Y )
= P(X ≤w ≤Y ) · P(X < Y ) + P(Y ≤w ≤X) · P(X ≥Y )
= P(X ≤w) · P(w ≤Y ) · P(X < Y ) + P(Y ≤w) · P(w ≤X) · P(X ≥Y )
= P(X ≤w) · (1 −P(Y ≤w)) · P(X < Y ) + P(Y ≤w) · (1 −P(X ≤w)) · P(X ≥Y )
= (1 −e−αw) · e−βw
α
α + β + (1 −e−βw) · e−αw
β
α + β
= αe−βw + βe−αw −(α + β)e−(α+β)w
α + β
= αe−βw + βe−αw
α + β
−e−(α+β)w
b) En clases se demostr´o que el m´ınimo de dos variables exponenciales X ∼Exp(α) y Y ∼Exp(β) tiene la misma distribuci´on
que otra exponencial con un par´ametro igual a la suma de los dos anteriores (Z ∼Exp(α + β)). Esto se puede ocupar
directamente o demostrar. Una demostraci´on v´alida ser´ıa:
FZ(z) = P{Z ≤z}
= P{min{X, Y } ≤z}
= 1 −P{min{X, Y } > z}
= 1 −P{X > z} · P{Y > z}
= 1 −e−αz · e−βz
= 1 −e−(α+β)
Luego,
fZ(z) = F ′
Z(z) = (α + β) · e−(α+β)
2

Por lo tanto, Z ∼Exp(α + β). Como sabemos que la distribuci´on exponencial no tiene memoria, entonces:
E[min{X, Y }| min{X, Y } > v] = E[Z|Z > v] = E[Z] + v
Finalmente, como el valor esperado de una variable aleatoria exponencial es el inverso de su par´ametro:
E [min{X, Y }| min{X, Y } > v] =
1
α + β + v
Problema 2 (20 pts.)
Un conocido ”mago” del Paseo Ahumada ha hecho una respetable fortuna con el siguiente juego de azar: en una mesa
tiene tres vasos (no transparentes) boca-abajo y dos bolitas que se colocan (juntas o por separado) debajo de alguno de los
vasos. Luego, con una habilidad y rapidez impresionantes, el mago procede a mover las bolitas de un vaso a otro. En cada
movimiento cambia de posici´on solo una bolita. Esto lo hace incontables veces hasta que un jugador deseoso de apostar le
dice stop. En ese momento el jugador tiene que escoger uno de los vasos. Si debajo del vaso hay dos bolitas, el jugador gana
la cantidad apostada. De lo contrario, pierde. Para simplificar el juego, asuma que en cada movimiento el mago escoge con
igual probabilidad cualquiera de las bolitas, y tambi´en equiprobablemente escoge a cu´al de los otros vasos la cambia.
a) (6 puntos) Muestre que el juego anterior se puede modelar como una CMTD con solo 6 estados. Identifique estos
estados y la matriz de probabilidades de transici´on.
b) (4 puntos) Determine las clases de estados y clasifique estas clases en transientes, recurrentes positivas o nulas, y
determine si son aperi´odicas o peri´odicas. Adem´as, determine el valor del per´ıodo cuando corresponda.
c) (3 puntos) Argumente si esta CMTD admite probabilidades estacionarias y l´ımite. De ser as´ı, indique el sistema de
ecuaciones que se debe resolver para encontrar estas probabilidades.
d) (3 puntos) Sea rk el n´umero de vasos vac´ıos en el estado k, y πk = 3−rk
9
. Demuestre que el vector definido por estos
πk corresponde a una soluci´on estacionaria.
e) (4 puntos) Ignorando el hecho de que usted pueda tener una vista muy aguda, ¿cu´al es la esperanza de la ganancia
obtenida al apostar $5.000? Considere que el mago hace ”muchos” movimientos antes de que usted diga stop y que
usted escoge equiprobablemente cualquiera de los tres vasos.
Solucion Problema 2
a) Para modelar el juego como una cadena de Markov en tiempo discreto, definimos 6 estados posibles:
– Estado 1: Dos bolitas bajo el primer vaso.
– Estado 2: Dos bolitas bajo el segundo vaso.
– Estado 3: Dos bolitas bajo el tercer vaso.
– Estado 4: Una bolita bajo el primer vaso y una bajo el segundo vaso.
– Estado 5: Una bolita bajo el primer vaso y una bajo el tercer vaso.
– Estado 6: Una bolita bajo el segundo vaso y una bajo el tercer vaso.
3

La matriz de probabilidades de transici´on es:
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
0
0
0
1/2
1/2
0
0
0
0
1/2
0
1/2
0
0
0
0
1/2
1/2
1/4
1/4
0
0
1/4
1/4
1/4
0
1/4
1/4
0
1/4
0
1/4
1/4
1/4
1/4
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
b) Como todos los estados se comunican entre s´ı, por lo que es una CMTD irreductible.
Por lo tanto, solo existe una clase
recurrente positiva. Para determinar el per´ıodo de esta clase podemos pararnos en el estado 1 y obtener el m´aximo com´un
divisor de los n para los cuales P (n)
11
> 0. Analizando la CMTD podemos ver que es posible volver en 2, 3, 4, 5, 6, etc. etapas.
Luego, como el m´aximo com´un divisor es 1, la clase es aperi´odica.
c) Como la CMTD es irreducible y aperi´odica, entonces el proceso tiene distribuci´on l´ımite y distribuci´on estacionaria (las cuales
coinciden). Para calcular estas probabilidades, se debe resolver el siguiente sistema de ecuaciones:
πT = πT · P
6
X
i=1
πi = 1
πi ≥0
∀i ∈{1, ..., 6}
d) De acuerdo a la definici´on r1 = r2 = r3 = 2 y r4 = r5 = r6 = 1. Entonces: π1 = π2 = π3 = 1
9 y π4 = π5 = π6 = 2
9.
Luego, basta con verificar que se cumple el siguiente sistema de ecuaciones:
(1
9, 1
9, 1
9, 2
9, 2
9, 2
9) = (1
9, 1
9, 1
9, 2
9, 2
9, 2
9) ·
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
0
0
0
1/2
1/2
0
0
0
0
1/2
0
1/2
0
0
0
0
1/2
1/2
1/4
1/4
0
0
1/4
1/4
1/4
0
1/4
1/4
0
1/4
0
1/4
1/4
1/4
1/4
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
6
X
i=1
πi = 1
πi ≥0
∀i ∈{1, ..., 6}
4

e) Para ganar, debemos detener el juego en un estado en el que sea posible ganar y, adem´as, elegir correctamente el vaso ganador.
Luego, la esperanza de las ganancias vienen dadas por:
E[Ganancias] =
6
X
i=1
E[Ganancias|El juego se detiene en el estado i] · P[Detener el juego en el estado i]
=
6
X
i=1
E[Ganancias|El juego se detiene en el estado i] · πi
=

$5.000
1
3

−$5.000
2
3

· π1
+

$5.000
1
3

−$5.000
2
3

· π2
+

$5.000
1
3

−$5.000
2
3

· π3
−$5.000 · π4 −$5.000 · π5 −$5.000 · π6
= −
$5.000
3

· (π1 + π2 + π3) −$5.000 · (π4 + π5 + π6)
= −
$5.000
3

· 1
3 −$5.000 · 2
3
= −$25.000
9
= −$2.777, 7
Problema 3 (20 pts.)
Considere una Cadena de Markov en Tiempo Discreto con espacio de estados {1, 2, 3, 4, 5, 6} y la siguiente matriz de
probabilidades de transici´on:
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
0.4
0.4
0.2
0
0
0
0
0
0
0
0
1
0.7
0
0
0.3
0
0
0
0
0
1
0
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
a) (2 puntos) Determine las clases de estados y clasifique todos los estados en transientes, recurrentes positivos o nulos,
y determine si son aperi´odicos o peri´odicos, y el valor del per´ıodo si es que corresponde.
b) (2 puntos) ¿Existe limn→∞P (n)
ij
para todo (i, j)? Justifique.
c) (3 puntos) ¿Existe alguna distribuci´on estacionaria? Si su respuesta es afirmativa, especifique al menos una dis-
tribuci´on estacionaria y verifique que cumple con su correspondiente sistema de ecuaciones.
d) (4 puntos) Asumiendo que el estado inicial es el estado 1, calcule la probabilidad de eventualmente visitar el estado 4.
e) (2 puntos) Calcule P(T(3, 2) = k), con k ∈{1, ..., 9}.
f) (3 puntos) Determine E[T(1, 5)].
g) (4 puntos) Asumiendo que f (0) = [0.3, 0, 0.7, 0, 0, 0]T , calcule P(X4 = 2).
5

Solucion Problema 3
a) Las clases de estado son:
• {1, 3}: Transiente aperi´odica.
• {2, 5, 6}: Recurrente positiva peri´odica, con per´ıodo 3.
• {4}: Recurrente positiva aperi´odica.
b) Como existe una clase recurrente positiva peri´odica, no existe limn→∞P (n)
ij
para todo (i, j)
c) Para determinar si existe alguna distribuci´on estacionaria, debemos encontrar un vector π tal que π⊺= π⊺P con π ≥0 y
π1 + . . . + π6 = 1.
Analizando la cadena, se aprecia que si partimos en el estado 4, una soluci´on estacionaria es π = (0, 0, 0, 1, 0, 0). Por otro lado,
si partimos desde un estado de la clase {2, 5, 6}, otra soluci´on estacionaria es π = (0, 1
3, 0, 0, 1
3, 1
3).
d) Nos piden calcular F(1, 4), luego:
F(1, 4) = P1,4 + P1,3F(3, 4) + P1,1F(1, 4)
F(1, 4) = 0 + 0.2F(3, 4) + 0.4F(1, 4)
F(3, 4) = P3,4 + P3,1F(1, 4)
F(3, 4) = 0.3 + 0.7F(1, 4)
⇒F(1, 4) = 0.2(0.3 + 0.7F(1, 4)) + 0.4F(1, 4)
F(1, 4) = 0.06 + 0.14F(1, 4) + 0.4F(1, 4)
F(1, 4) = 0.06
0.46 = 0.13043478
e)
P(T(3, 2) = 1) = P32 = 0
P(T(3, 2) = 2) = P31P12 = 0.7 · 0.4
Como para llegar del estado 3 al estado 2 por primera vez en k ≥3 etapas siempre tendremos que ir del estado 3 al estado 1
en la primera transici´on y del estado 1 al estado 2 en la ultima, se cumple que P(T(3, 2) = k) = P31P (k−2)
11
P12. Por lo tanto,
solo falta determinar P (n)
11
para n ∈{1, ..., 7}.
P (1)
11 = P11 = 0.4
P (2)
11 = P 2
11 + P13P31
= 0.42 + 0.7 · 0.2
= 0.3
P (3)
11 = P 3
11 + P11P13P31 + P13P31P11
= 0.43 + 0.4 · 0.7 · 0.2 + 0.7 · 0.2 · 0.4
= 0.176
P (4)
11 = P 4
11 + P 2
11P13P31 + P13P31P 2
11 + (P13P31)2
= 0.44 + 0.42 · 0.7 · 0.2 + 0.7 · 0.2 · 0.42 + (0.7 · 0.2)2
= 0.1124
P (5)
11 = P 5
11 + P 3
11P13P31 + P13P31P11P13P31 + P13P31P 3
11
= 0.45 + 0.43 · 0.7 · 0.2 + 0.7 · 0.2 · 0.4 · 0.7 · 0.2 + 0.7 · 0.2 · 0.43
6

= 0.0696
P (6)
11 = P 6
11 + P 4
11P13P31 + P13P31P 2
11P13P31 + P13P31P 4
11 + (P13P31)3
= 0.46 + 0.44 · 0.7 · 0.2 + 0.7 · 0.2 · 0.42 · 0.7 · 0.2 + 0.7 · 0.2 · 0.44 + (0.7 · 0.2)3
= 0.0436
P (7)
11 = P 7
11 + P 5
11P13P31 + P 3
11(P13P31)2 + P13P31P 3
11P13P31 + (P13P31)2P11P13P31
+ P13P31P11(P13P31)2 + P11(P13P31)3 + P13P31P 5
11 + (P13P31)2P 3
11 + (P13P31)3P11
= 0.47 + 0.45 · 0.7 · 0.2 + 0.43(0.7 · 0.2)2 + 0.7 · 0.2 · 0.43 · 0.7 · 0.2 + (0.7 · 0.2)2 · 0.4 · 0.7 · 0.2
+ 0.7 · 0.2 · 0.4(0.7 · 0.2)2 + 0.4(0.7 · 0.2)3 + 0.7 · 0.2 · 0.45 + (0.7 · 0.2)20.43 + (0.7 · 0.2)30.4
= 0.0272
Finalmente tenemos que:
P(T(3, 2) = 3) = P31P11P12 = 0.7 · 0.4 · 0.4 = 0.112
P(T(3, 2) = 4) = P31P (2)
11 P12 = 0.7 · 0.3 · 0.4 = 0.084
P(T(3, 2) = 5) = P31P (3)
11 P12 = 0.7 · 0.176 · 0.4 = 0.0493
P(T(3, 2) = 6) = P31P (4)
11 P12 = 0.7 · 0.1124 · 0.4 = 0.0315
P(T(3, 2) = 7) = P31P (5)
11 P12 = 0.7 · 0.0696 · 0.4 = 0.0195
P(T(3, 2) = 8) = P31P (6)
11 P12 = 0.7 · 0.0436 · 0.4 = 0.0122
P(T(3, 2) = 9) = P31P (7)
11 P12 = 0.7 · 0.0272 · 0.4 = 0.0076
f) Utilizando E(T(i, j)) = 1 + P
m̸=j E(T(m, j)) · Pi,m tenemos que:
E(T(1, 5)) = 1 + P1,1 · E(T(1, 5)) + P1,3 · E(T(3, 5)) + P1,2 · E(T(2, 5))
= 1 + P1,3 · E(T(3, 5)) + P1,2 · E(T(2, 5))
1 −P1,1
E(T(3, 5)) = 1 + P3,1 · E(T(1, 5)) + P3,4 · E(T(4, 5))
E(T(4, 5)) = ∞
→E(T(3, 5)) = ∞
→E(T(1, 5)) = ∞
g)
P(X4 = 2) = P(X4 = 2|X0 = 1) · P(X0 = 1) + P(X4 = 2|X0 = 3) · P(X0 = 3)
= P(X4 = 2|X0 = 1) · f (0)
1
+ P(X4 = 2|X0 = 3) · f (0)
3
= P (4)
12 · f (0)
1
+ P (4)
32 · f (0)
3
= (P 3
11P12 + P11P13P31P12 + P13P31P11P12 + P12P26P65P52) · f (0)
1
+ (P31P 2
11P12 + P31P13P31P12) · f (0)
3
= (0.430.4 + 0.4 · 0.2 · 0.7 · 0.4 + 0.2 · 0.7 · 0.4 · 0.4 + 0.4 · 1 · 1 · 1) · 0.3 + (0.7 · 0.42 · 0.4 + 0.7 · 0.2 · 0.7 · 0.4) · 0.7
= 0.1992
7

Distribuci´on
PDF
CDF
Esperanza
Varianza
Poisson(λ)
f(x) = λxe−λ
x!
F(x) = P⌊x⌋
k=0
λke−λ
k!
λ
λ
Exponencial(λ)
f(x) = λe−λx
F(x) = 1 −e−λx
1
λ
1
λ2
Binomial(n, p)
f(x) =
 n
x

px(1 −p)n−x
F(x) = P⌊x⌋
k=0
 n
k

pk(1 −p)n−k
np
np(1 −p)
Uniforme(a, b)
f(x) =
1
b−a
F(x) = x−a
b−a
a+b
2
(b−a)2
12
8

