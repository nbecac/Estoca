Pontificia Universidad Cat´olica de Chile
Escuela de Ingenier´ıa
Departamento de Ingenier´ıa Industrial y de Sistemas
ICS2123-2 – Modelos Estoc´asticos
Profesor Nicol´as Vargas C.
Primer Semestre 2024
Interrogaci´on 2
Duraci´on: 2 horas y 30 minutos
Problema 1 (20 pts.)
Buques de carga llegan a cargar contenedores en un puerto donde se encuentran tres gr´uas de carga. Los buques llegan a
una tasa de 60 buques por hora, y forman una cola ´unica frente a las gr´uas. Cada gr´ua toma un tiempo promedio de 4
minutos en cargar un buque.
1. (4 puntos) ¿Qu´e pasar´a con la cantidad de buques en la cola en el largo plazo?
2. (12 puntos) Suponga ahora que existe un sistema autom´atico de despacho que no permite que se formen colas mayores
a 2 buques (es decir, si llega un buque cuando hay dos buques en cola, este se ve redirigido a otro sector). Determine
el n´umero esperado de buques en la cola y el tiempo de espera promedio de los buques en la cola, en el largo plazo.
3. (4 puntos) Suponga que el costo de espera de un buque en cola es de $700 d´olares por hora. En el largo plazo, ¿cu´anto
le cuestan por hora al puerto las esperas de buques en cola? Mantenga el supuesto de que no se pueden formar colas
mayores a 2 buques.
Solucion Problema 1
1. Dado que la tasa de llegada (1 buque por minuto) es mayor que la tasa de atenci´on del sistema multiplicada por el
n´umero de servidores (3 · 0.25 = 0.75 buques por minuto), el sistema colapsar´a y la cola tender´a a infinito.
2. Este sistema corresponde a un sistema de espera M/M/3/5.
Luego, el sistema de ecuaciones a resolver es el siguiente:
λP0 = µP1
(λ + µ)P1 = λP0 + 2µP2
(λ + 2µ)P2 = λP1 + 3µP3
1

(λ + 3µ)P3 = λP2 + 3µP4
(λ + 3µ)P4 = λP3 + 3µP5
3µP5 = λP4
5
X
i=0
Pi = 1
Encontrando que:
P0 =
1
3P
n=0
λn
n!µn +
5P
n=4
λn
6 · 3n−cµn
P1 = λ
µP0
P2 = λ2
2µ2 P0
P3 = λ3
6µ3 P0
P4 =
λ4
18µ4 P0
P5 =
λ5
54µ5 P0
Para el caso del n´umero esperado de buques en la cola, se tiene que habr´a cola si se est´a en los estados 4 y 5, de esta
manera, el largo de cola esperado ser´a:
Lq =
5
X
i=4
Pi(i −3) = P4 + 2P5
Por otro lado, se tiene que la tasa de llegada efectiva es:
λe = λ(1 −P5)
As´ı, el tiempo promedio en la cola ser´a:
Wq = Lq
λe
= P4 + 2P5
λ(1 −P5)
3. En el largo plazo, las esperas de buques en la cola tendr´a un costo para el puerto de:
700Lq = 700P4 + 1400P5
Problema 2 (20 pts.)
Imagine que queremos modelar la ocupaci´on del ascensor de un edificio mediante el uso de una Cadena de Markov en Tiempo
Continuo. Este edificio tiene cuatro pisos (contando la planta baja) y un subterr´aneo. Las personas llegan al edificio a
una tasa de λ personas por hora, y cada persona se dirige equiprobablemente a uno de los tres pisos con habitaciones o
al subterr´aneo. Adem´as, el ascensor puede ser llamado desde cualquiera de los tres pisos con habitaciones a una tasa γi
personas por hora, con i ∈{1, 2, 3}.
Cuando el ascensor es llamado desde uno de los pisos con habitaciones, con probabilidad p, las personas van a la planta
baja, y con probabilidad 1 −p van al subterr´aneo. Es importante notar que el ascensor permanece en el ´ultimo piso de
destino hasta que sea llamado nuevamente desde otro piso. Supondremos que el tiempo de desplazamiento entre los pisos
es despreciable para simplificar nuestro modelo.
2

1. (8 puntos) Construya una Cadena de Markov en Tiempo Continuo que modele el estado de ocupaci´on del ascensor.
Explicite claramente los estados y sus respectivas tasas de transici´on.
Hint: Cuando el ascensor es llamado desde alg´un piso, nos interesa d´onde queda el ascensor despu´es de ser usado.
2. (4 puntos) Justifique la existencia de una distribuci´on de probabilidades estacionarias y construya el sistema de
ecuaciones que permita calcularlas.
3. (4 puntos) Suponga que los cables del ascensor requieren de un mantenimiento que cuesta $c por cada hora que el
cable est´a tensado. El cable solo no est´a tensado cuando el ascensor est´a en el subterr´aneo. Estime el valor esperado
del costo de mantenimiento del cable del ascensor luego de t horas de funcionamiento.
4. (4 puntos) Si el ascensor se encuentra en el subterr´aneo, determine el tiempo esperado para que el ascensor vuelva a
estar en el subterr´aneo.
Solucion Problema 2
1. Definimos los estados de la CMTC en funci´on del piso donde se encuentra el ascensor:
• 0: El ascensor est´a en la planta baja.
• 1: El ascensor est´a en el primer piso.
• 2: El ascensor est´a en el segundo piso.
• 3: El ascensor est´a en el tercer piso.
• −1: El ascensor est´a en el subterr´aneo.
Luego, la CMTC que modela el estado de ocupaci´on es:
3

2. Dado que todos los estados est´an conectados y que la probabilidad de estar en un estado cualquiera existe y es
independiente del estado inicial, se tiene que existe la distribuci´on l´ımite y por ende, una distribuci´on de probabilidades
estacionarias. Adem´as, a partir del diagrama se puede plantear el siguiente sistema de ecuaciones de equilibrio en el
largo plazo:
λP0 = p(γ1 + γ2 + γ3)(P1 + P2 + P3 + P−1)
(γ1 + γ2 + γ3 + 3λ
4 )P1 = λ
4 P−1 + λ
4 P0 + λ
4 P2 + λ
4 P3
(γ1 + γ2 + γ3 + 3λ
4 )P2 = λ
4 P−1 + λ
4 P0 + λ
4 P1 + λ
4 P3
(γ1 + γ2 + γ3 + 3λ
4 )P3 = λ
4 P−1 + λ
4 P0 + λ
4 P1 + λ
4 P2
(p(γ1 + γ2 + γ3) + 3λ
4 )P−1 = λ
4 P0 + ((1 −p)(γ1 + γ2 + γ3) + λ
4 )(P1 + P2 + P3)
P0 + P1 + P2 + P3 + P−1 = 1
3. El costo de mantenimiento por hora es c si el ascensor est´a en cualquier piso menos el subterr´aneo, y 0 si est´a en el
subterr´aneo. Por lo tanto, el costo esperado por hora es:
E[costo por hora] = c · (P0 + P1 + P2 + P3) = c · (1 −P−1)
El valor esperado del costo de mantenimiento del cable del ascensor luego de t horas es:
4

E[costo en t horas] = c · (1 −P−1) · t
4. Para calcular el tiempo esperado para volver al subterraneo, primero condicionamos sobre todos los posibles estados
hacia los cuales puedo ir desde el subterraneo. De este modo:
E[t volver al subterr´aneo] =
3
X
i=0
P−1,i (E[t ir desde el subterraneo a i] + E[t ir desde i al subterraneo])
donde
P−1,0 =
p(γ1 + γ2 + γ3)
p(γ1 + γ2 + γ3) + 3λ
4
P−1,1 = P−1,2 = P−1,3 =
λ
4
p(γ1 + γ2 + γ3) + 3λ
4
Luego,
E[t volver al subterr´aneo] = P−1,0
 
1
p(γ1 + γ2 + γ3) + 1
λ
4
!
+ P−1,1
 
1
λ
4
+
1
(1 −p)(γ1 + γ2 + γ3) + λ
4
!
+ P−1,2
 
1
λ
4
+
1
(1 −p)(γ1 + γ2 + γ3) + λ
4
!
+ P−1,3
 
1
λ
4
+
1
(1 −p)(γ1 + γ2 + γ3) + λ
4
!
= P−1,0

1
p(γ1 + γ2 + γ3) + 4
λ

+ (P−1,1 + P−1,2 + P−1,3)
 
4
λ +
1
(1 −p)(γ1 + γ2 + γ3) + λ
4
!
Problema 3 (20 pts.)
A un restaurante Benihana, los clientes llegan al establecimiento seg´un un proceso Poisson con tasa promedio de λ clientes
por hora. Al ingresar, los clientes se dirigen inicialmente al ´area de espera, que consiste en un bar. En este bar, los clientes
son atendidos por 5 bartenders, con un tiempo de servicio que sigue una distribuci´on exponencial con tasa µb clientes por
hora. La capacidad del bar es de 10 sillas, y cuando el bar est´a lleno, los clientes no pueden ingresar al restaurante.
Una vez que los clientes finalizan su espera en el bar, pasan al ´area de cocina, donde 4 hay chefs que preparan la comida
frente a ellos. En esta ´area, el tiempo de servicio de los chefs sigue una distribuci´on exponencial con tasa µc clientes por
hora. Finalmente, una vez que los clientes han terminado de disfrutar de su comida, abandonan el restaurante.
1. (2 puntos) En el restaurante descrito, ¿qu´e tipos de sistemas de espera existen?
2. (6 puntos) Modele mediante una Cadena de Markov en Tiempo Continuo cada ´area de atenci´on del restaurante.
Indique las tasas efectivas de entrada a cada etapa y las condiciones que se deben cumplir en cada una de ellas para
asegurar que el sistema no colapse.
3. (4 puntos) Determine el n´umero promedio de clientes en el restaurante.
5

4. (4 puntos) Si en promedio un cliente de Benihana gasta cb en el bar y cc en el ´area de cocina, estime la el monto que
deja de recibir Benihana en un per´ıodo de t horas porque el bar se encuentra lleno.
5. (4 puntos) Encuentre el tiempo medio de permanencia y el tiempo medio en cola de un cliente en el restaurante
Benihana.
Solucion Problema 3
1. El ´area de espera en el bar es un sistema de espera M/M/5/10 y la cocina es un sistema de espera M/M/4.
2. Para esto podemos representar las dos partes del problema por separado. En cada una, los estados representan la
cantidad i de pacientes en el ´area (en atenci´on y en fila esperando atenci´on), con i ∈[0, ∞).
• Bar: Como el sistema capacidad finita, no se requiere de ninguna condici´on para asegurar que el sistema no
colapse. El grafo para este sistema de la red es:
• Cocina: En este caso λe = min{λ(1−P10), 5µb} y alcanzar estacionalidad se requiere que min{λ(1−P10), 5µb} <
4µc. El grafo para este sistema de la red es:
3. El n´umero promedio de clientes en el restaurante es la suma de los n´umeros promedio de clientes en cada ´area.
L = Lb + Lc
Para el bar:
Lb =
10
X
i=0
i · P b
i
donde
P b
0 =


5
X
n=0
λn
n!µn
b
+ λ5
5!µ5
b
· λ
5µ ·
1 −

λ
5µb
5
1 −
λ
5µb


−1
P b
n =







λn
n!µn
b
P b
0
si 0 < n ≤5
λn
5!5n−5µn
b
P b
0
si 5 < n ≤10
Para el ´area de cocina:
Lc =
∞
X
i=0
i · P c
i =
 4
X
i=0
i
i! ·
λe
µc
i
+
∞
X
i=5
i
4! · 4i−4 ·
λe
µc
i!
· P c
0
donde
P c
0 =
"
1 +
4
X
i=1
1
i! ·
λe
µc
i
+
∞
X
i=5
1
4! · 4i−4 ·
λe
µc
i#−1
6

4.
λP10(cb + cc)t
5. Para el tiempo medio de permanencia de un cliente en el restaurante, consideramos el tiempo en el bar y en el ´area
de cocina.
W = Wb + Wc
Por la ecuaci´on de Little:
W =
Lb
λ(1 −P10) +
Lc
min{λ(1 −P10), 5µb}
Y su tiempo medio en cola es:
Wq = Wqb + Wqc
=
Lqb
λ(1 −P10) +
Lqc
min{λ(1 −P10), 5µb}
=
10
X
i=5
(i −5) · P b
i
λ(1 −P10)
+
∞
X
i=4
(i −4) · P c
i
min{λ(1 −P10), 5µb}
=
10
X
i=6
(i −5) · P b
i
λ(1 −P10)
+
∞
X
i=5
(i −4) · P c
i
min{λ(1 −P10), 5µb}
=
10
X
i=6
(i −5) · P b
i
λ(1 −P10)
+
∞
X
i=5
(i −4) · P c
i
min{λ(1 −P10), 5µb}
=
10
X
i=6
(i −5)λn
5!5n−5µn
b
P b
0
λ(1 −P10)
+
∞
X
i=5
(i −4)λn
4!4n−4µn
b
P c
0
min{λ(1 −P10), 5µb}
7

Distribuci´on
PDF (f(x))
CDF (F (x))
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
Sistema
P0
Pn
L
Lq
M/M/1
1 −λ
µ

λ
µ
n
P0
∀i ∈{1, 2, ...}
λ
µ−λ
λ2
µ(µ−λ)
M/M/1/K
1 −λ
µ
1 −

λ
µ
K+1

λ
µ
n
P0
∀i ∈{1, 2, ..., K}
λ
µ




1 −

λ
µ
K
−K

λ
µ
K
+ K

λ
µ
K+1

1 −λ
µ
 
1 −

λ
µ
K+1




L −λ(1−PK)
µ
M/M/c
"
cP
n=0
 λn
n!µn

+ λc
c!µc ·
λ
cµ
1 −
λ
cµ
#−1
λn
n!µn P0
∀i ∈{1, 2, ..., c}
λn
c!cn−cµn P0
∀i ∈{c + 1, ...}
λ
µ +
( λ
µ)
c
c!(1−λ
cµ)2
λ
µ
L −λ
µ
M/M/c/K


cP
n=0
 λn
n!µn

+ λc
c!µc · λ
cµ ·
1 −

λ
cµ
K−c
1 −
λ
cµ


−1
λn
n!µn P0
∀i ∈{1, 2, ..., c}
λn
c!cn−cµn P0
∀i ∈{c + 1, ..., K}
K
X
n=0
nPn
L −λ(1−PK)
µ

