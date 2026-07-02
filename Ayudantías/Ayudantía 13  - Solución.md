Pontificia Universidad Cat´olica de Chile
Escuela de Ingenier´ıa
Departamento de Ingenier´ıa Industrial y de Sistemas
ICS2123 – Modelos Estoc´asticos
Profesores Ver´onica Godoy y Andr´es Navarro
Ayudante Jefe Joaqu´ın Vergara
Primer Semestre 2026
Ayudant´ıa 13:
Repaso I2
Ayudantes: Emilio Pe˜na (emilio.penasepulveda@uc.cl) & Mart´ın Pe˜na (martinpena@uc.cl)
Problema 1
La tienda de artesan´ıas ‘Al mal tiempo buena cara’ tiene un ´unico vendedor cuyo desempe˜no depende tanto
de su estado de ´animo como del clima del d´ıa. El ´animo del vendedor puede ser Bueno (B) o Malo (M), y
evoluciona d´ıa a d´ıa seg´un la siguiente matriz de transici´on:
 B
M
B
0.6
0.4
M
0.5
0.5

El clima puede ser Soleado (S) o Lluvioso (L), y evoluciona de forma independiente al ´animo del vendedor
seg´un:
 S
L
S
0.7
0.3
L
0.4
0.6

La probabilidad de que el vendedor concrete una venta en el d´ıa depende del estado conjunto (´animo, clima)
de la siguiente manera:




P(venta)
(B, S)
0.8
(B, L)
0.5
(M, S)
0.4
(M, L)
0.1




(a) Modele la situaci´on como una CMTD que describa conjuntamente el ´animo del vendedor y el clima,
dejando claramente expresadas las tasas de transici´on.
Soluci´on:
El estado del sistema en el d´ıa t es el par (at, ct), donde at ∈{B, M} es el ´animo del vendedor y
ct ∈{S, L} el clima. El espacio de estados es:
Ω= {(B, S), (B, L), (M, S), (M, L)}
Dado que el ´animo y el clima evolucionan de forma independiente entre s´ı, la probabilidad de transici´on
conjunta es el producto de ambas probabilidades:
P(a,c),(a′,c′) = P ´animo
(a,a′) · P clima
(c,c′)
Las tasas de transici´on instant´aneas del sistema conjunto son:
P =




(B, S)
(B, L)
(M, S)
(M, L)
(B, S)
0.42
0.18
0.28
0.12
(B, L)
0.24
0.36
0.16
0.24
(M, S)
0.35
0.15
0.35
0.15
(M, L)
0.20
0.30
0.20
0.30




1

Por ejemplo, P(B,S),(M,L) = P ´animo
(B,M) · P clima
(S,L) = 0.4 × 0.3 = 0.12.
(b) Suponiendo que la tienda lleva mucho tiempo operando, ¿cu´al es la probabilidad de que en un d´ıa
dado el vendedor concrete una venta?
Soluci´on:
Sea π = (π(B,S), π(B,L), π(M,S), π(M,L)) la distribuci´on estacionaria. Las ecuaciones de balance πP =
π son:
π(B,S) = P(B,S),(B,S) π(B,S) + P(B,L),(B,S) π(B,L) + P(M,S),(B,S) π(M,S) + P(M,L),(B,S) π(M,L)
π(B,L) = P(B,S),(B,L) π(B,S) + P(B,L),(B,L) π(B,L) + P(M,S),(B,L) π(M,S) + P(M,L),(B,L) π(M,L)
π(M,S) = P(B,S),(M,S) π(B,S) + P(B,L),(M,S) π(B,L) + P(M,S),(M,S) π(M,S) + P(M,L),(M,S) π(M,L)
π(M,L) = P(B,S),(M,L) π(B,S) + P(B,L),(M,L) π(B,L) + P(M,S),(M,L) π(M,S) + P(M,L),(M,L) π(M,L)
1 = π(B,S) + π(B,L) + π(M,S) + π(M,L)
La probabilidad de que el vendedor concrete una venta en el largo plazo es:
P(venta) = 0.8 · π(B,S) + 0.5 · π(B,L) + 0.4 · π(M,S) + 0.1 · π(M,L)
= 0.8 · 20
63 + 0.5 · 5
21 + 0.4 · 16
63 + 0.1 · 4
21
= 16
63 + 5
42 + 32
315 +
2
105 = 311
630 ≈0.494
(c) Partiendo del peor estado posible (´animo Malo y clima Lluvioso), ¿cu´antos d´ıas se deben esperar en
promedio hasta que el vendedor recupere el buen ´animo?
Soluci´on:
Se parte del estado (M, L). El vendedor recupera el buen ´animo cuando el sistema alcanza por primera
vez cualquier estado con a = B, es decir el conjunto {(B, S), (B, L)}.
E

T(M,S),(B,·)

= 1 + P(M,S),(M,S) E

T(M,S),(B,·)

+ P(M,S),(M,L) E

T(M,L),(B,·)

E

T(M,L),(B,·)

= 1 + P(M,L),(M,S) E

T(M,S),(B,·)

+ P(M,L),(M,L) E

T(M,L),(B,·)

Sustituyendo los valores de la matriz:
E

T(M,S),(B,·)

= 1 + 0.35 E

T(M,S),(B,·)

+ 0.15 E

T(M,L),(B,·)

E

T(M,L),(B,·)

= 1 + 0.20 E

T(M,S),(B,·)

+ 0.30 E

T(M,L),(B,·)

Reordenando :
0.65 E

T(M,S),(B,·)

−0.15 E

T(M,L),(B,·)

= 1
−0.20 E

T(M,S),(B,·)

+ 0.70 E

T(M,L),(B,·)

= 1
Resolviendo:
E

T(M,S),(B,·)

= E

T(M,L),(B,·)

= 2 d´ıas
Independientemente del estado del clima, partiendo con ´animo Malo se esperan en promedio 2 d´ıas
hasta que el vendedor recupere el buen ´animo. Este resultado es intuitivo: como el clima es indepen-
diente del ´animo, no afecta el tiempo de recuperaci´on, que depende ´unicamente de la din´amica del
´animo con π´animo
M
= 4
9, lo que implica un tiempo medio de retorno de
1
P ´animo
(M,B) =
1
0.5 = 2 d´ıas.
Problema 2
Alan Brito se caracteriza por ser un alumno relajado en la escuela de ingenier´ıa. Su filosof´ıa de estudio es
simple, ”Si tengo pocas tareas, estoy tranquilo” por lo que mientras tenga M o menos tareas pendientes
las resuelve de forma independiente a una tasa de α tareas por d´ıa.
2

Esto cambia cuando se acerca el fin de semestre y se comienzan a acumular tareas, ya que debe activar el
’Modo serio’ por lo que ahora resolver´a las tareas a una tasa α · n donde n corresponde a la cantidad de
tareas que aun tiene pendiente. Alan mantiene este ritmo hasta que logre entregar todas sus tareas.
Considere que el tiempo entre la asignaci´on de nuevas tareas distribuye exponencial con un par´ametro λ.
(a) Modele la situaci´on como una CMTC dejando claramente expresado cuales son las tasas de transici´on
instant´aneas.
Soluci´on: Para modelar la situaci´on como una CMTC definimos el vector de estados (X, Y ), donde
X ∈N0 corresponde a la cantidad de tareas que Alan tiene pendiente e Y corresponde al modo actual
de Alan (relajado o serio).
0, R
1, R
· · ·
M−1, R
M, R
1, S
· · ·
M−1, S
M, S
M+1, S
M+2, S
· · ·
λ
λ
λ
λ
α
α
α
α
λ
λ
λ
2α
nα
Mα
λ
λ
λ
(M+1)α
(M+2)α
nα
λ
α
(b) Encuentre una expresi´on para las probabilidades de largo plazo.
Soluci´on: Sean Pn,m las probabilidades estacionarias de encontrar a la cadena en el estado (n, m)
en el largo plazo.
⋄Estado (0, R):
λP0,R = αP1,R + αP1,S
⋄Estados (n, R) para 1 ≤n ≤M −1:
(λ + α)Pn,R = λPn−1,R + αPn+1,R
⋄Estado (M, R):
(λ + α)PM,R = λPM−1,R
⋄Estado (1, S):
(λ + α)P1,S = 2αP2,S
⋄Estados (n, S) para 2 ≤n ≤M:
(λ + nα)Pn,S = λPn−1,S + (n + 1)αPn+1,S
⋄Estado (M + 1, S):
(λ + (M + 1)α)PM+1,S = λPM,R + λPM,S + (M + 2)αPM+2,S
⋄Estados (n, S) para n ≥M + 2:
(λ + nα)Pn,S = λPn−1,S + (n + 1)αPn+1,S
3

A este sistema de ecuaciones se le debe a˜nadir la condici´on para asegurar que las probabilidades
sumen 1:
M
X
n=0
Pn,R +
∞
X
n=1
Pn,S = 1
(c) Considere ahora que mientras hayan al menos M tareas en la lista de pendientes, cada vez que llega
una nueva tarea, con probabilidad p se dar´a m´as plazo para todas las tareas, por lo que Alan vuelve
a relajarse y vuelve a su ritmo de α tareas por d´ıa. Sobre est´a din´amica puede asumir que una vez
se ha dado m´as plazo para las tareas se mantendr´a este modo hasta que vuelva a tener M tareas
pendientes. Modifique la CMTC para considerar la nueva din´amica del sistema.
Soluci´on: Para incorporar los cambios agregamos los estados donde Alan vuelve a estar relajado.
Notese que es posible entrar a la nueva rama de dos formas, ya sea con la llegada de una nueva tarea
estando ya en el modo relajado, o pasando del modo serio al relajado al llegar una nueva tarea.
0, R
1, R
· · ·
M−1, R
M, R
1, S
· · ·
M−1, S
M, S
M+1, S
M+2, S
· · ·
M+1, R
M+2, R
· · ·
λ
λ
λ
λ
α
α
α
α
λ
λ
λ
2α
nα
Mα
α
λ(1 −p)
λp
λ(1 −p)
λ(1 −p)
λ(1 −p)
(M+1)α
(M+2)α
nα
λ
λ
α
α
λp
λp
λp
α
Problema 3 (Propuesto)
Considere una f´abrica que tiene dos m´aquinas, m´aquina 1 y m´aquina 2, y dos talleres, taller 1 y taller 2.
La m´aquina 1 tiene un tiempo de funcionamiento que distribuye exponencial con tasa λ, mientras que la
m´aquina 2 tiene un tiempo de funcionamiento que distribuye exponencial con tasa α. Cuando cualquie-
ra de las m´aquinas deja de funcionar se tiene que llevar a alguno de los dos talleres, siempre prefiriendo
el taller 1 sobre el taller 2. Si un taller est´a ocupado, entonces se llevara la m´aquina defectuosa al otro taller.
El tiempo de reparaci´on de la m´aquina 1 en el taller 1 distribuye exponencial con tasa β y si se lleva al
taller 2 su tiempo tambi´en distribuye exponencial, pero con tasa σ. Por otro lado, el tiempo de reparaci´on
de la m´aquina 2 en el taller 1 es exponencial con tasa µ y en el taller 2 es tambi´en exponencial, pero con
tasa δ. Adem´as, existe una probabilidad p de que la m´aquina 2 siga mala despu´es de pasar por el taller 1
y en dicho caso debe ir al taller 2. Asuma que puede haber dos m´aquinas en el taller 2, pero s´olo se puede
atender una a la vez, y se atiende primero a la primera en llegar. Por otra parte, s´olo puede haber una
m´aquina en el taller 1.
Se quiere modelar el problema como una Cadena de Markov en Tiempo Continuo que represente si las
m´aquinas est´an funcionando o no y cu´ales est´an en cada taller si es que no est´an funcionando.
a) Identifique todos los estados posibles y las tasas de transici´on instant´aneas entre estados. Puede
expresar su respuesta a trav´es de un grafo.
Hint: Piense primero en todas las situaciones posibles en las que se puede encontrar cada m´aquina
por separado, y luego en las situaciones posibles para ambas m´aquinas a la vez.
4

b) Escriba las ecuaciones de equilibrio para cada uno de los estados.
c) Suponga que la m´aquina 2 est´a en el taller 2 y que la m´aquina 1 est´a funcionando. ¿Cu´al es la
probabilidad de que la m´aquina 2 salga del taller antes de que la m´aquina 1 deje de funcionar?
Soluci´on:
a) Sea (Xt, Yt) el estado del sistema en el instante t, donde Xt es el estado de la m´aquina 1 en t y Yt es el
estado de la m´aquina 2 en t. Los estados para cada m´aquina son los siguientes:
⋄0: Si la m´aquina esta funcionando
⋄1: Si la m´aquina esta en el taller 1
⋄2: Si la m´aquina esta en el taller 2
Nos queda el siguiente grafo:
0, 0
0, 1
2, 1
2, 0
1, 0
1, 2
2, 2
0, 2
α
(1 −p)µ
λ
σ
(1 −p)µ
α
λ
β
α
δ
β
λ
pµ
pµ
σ
σ
δ
(b) Las ecuaciones de largo plazo son:
P(0,0)(λ + α) = βP(1,0) + (1 −p)µP(0,1) + σP(2,0) + δP(0,2)
P(0,1)(λ + µ) = αP(0,0) + σP(2,1)
P(1,0)(β + α) = λP(00) + δP(1,2)
P(2,0)(α + σ) = (1 −p)µP(2,1)
P(0,2)(λ + δ) = pµP(0,1) + σP(2,2) + βP(1,2)
P(2,1)(σ + µ) = λP(0,1) + αP(2,0)
P(1,2)(β + δ) = αP(1,0) + λP(0,2)
P(2,2)(σ) = pµP(2,1)
(c) El resultado se puede obtener simplemente comparando las tasas de permanencia y transici´on de los
estados solicitados:
P(0,2)(0,0) =
δ
δ + λ
5

