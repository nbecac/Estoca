Pontificia Universidad Cat´olica de Chile
Escuela de Ingenier´ıa
Departamento de Ingenier´ıa Industrial y de Sistemas
ICS2123 – Modelos Estoc´asticos
Profesores Ver´onica Godoy y Andr´es Navarro
Ayudante Jefe Joaqu´ın Vergara
Primer Semestre 2026
Tarea 2:
CMTD y CMTC
Instrucciones
⋄Esta tarea debe ser realizada individualmente o en parejas (pueden ser de diferentes secciones
dentro de las que son coordinadas). Deben indicar en la primera plana del PDF los nombres de los/as
integrantes, junto con las secciones respectivas de c/u.
⋄Tienen plazo hasta el jueves 28 de mayo a las 23:59 hrs para entregar sus soluciones.
⋄Deben entregar un archivo reporte, en formato PDF. En el archivo PDF deben entregar sus respues-
tas de los 2 problemas. Los c´odigos implementados deben adjuntarse como un archivo .ZIP aparte
en el buz´on. En caso de no cumplir con esto, se aplicar´a un descuento de 5 d´ecimas sobre la nota
final de la tarea.
⋄En el PDF deber´a estar el desarrollo, resumen de resultados y correspondiente an´alisis. Se recomienda
fuertemente utilizar LATEX. Sin embargo, estas tambi´en pueden ser escritas en alg´un otro editor de
texto o a mano y escaneadas, pero debe estar ordenado y legible, de lo contrario, se descontar´an
5 d´ecimas a la nota final de la tarea. Cualquier c´odigo o referencia que utilicen de internet debe ser
debidamente citado insertando el link asociado.
⋄Si realizan la tarea completa en LATEX, incluyendo todas las f´ormulas y ecuaciones, tendr´an 3 d´ecimas
extras.
⋄La tarea tiene un total de 60 puntos. La nota final ser´a calculada como la suma de las tres preguntas
mediante la f´ormula
Nota = P1 + P2 + P3 + P4
60
· 6 + 1 + Bonus −Descuentos
Donde Pi corresponde al puntaje de la pregunta i. Se aproxima a dos decimales.
⋄Las preguntas se har´an a trav´es del foro de discusi´on asociado a la Tarea 2 en Canvas, por lo que les
pedimos que NO manden dudas por mail sobre la tarea. De esta manera, todos tienen acceso a las
respuestas.
⋄El uso evidente de salidas de LLMs sin una comprensi´on adecuada de su contenido ser´a
severamente sancionado con nota 1.0.
⋄Seremos estrictos en que no se aceptar´an env´ıos por mail. Evite problemas de internet, del sistema
Canvas, de la calidad de la foto o cualquier otro que pudiese ocurrir al entregar sobre la hora. El/La
alumno/a que env´ıe su tarea despu´es de la hora l´ımite, tendr´a nota 1.0.
1

Problema 1
A continuaci´on responda cada problema de forma independiente.
1. Sea P la matriz de transici´on de una cadena de Markov (Xn)n≥0 con espacio de estados E. Se dice
que x ∈E es no esencial si existe y ∈E tal que x →y, pero y ↛x. Decimos que x es esencial si
no es no esencial. Concluya que si i es no esencial, entonces i es transiente. Adem´as, pruebe que si
|E| < +∞, entonces existe un estado esencial. Encuentre un contraejemplo cuando |E| = |N|.
Indicaci´on: Puede ser de utilidad demostrar que ser no esencial es una propiedad de clase y calcular
P

X
n≥0
1{Xn=i} = ∞, Tj < ∞|X0 = i

= 0
Soluci´on: Primero demostraremos que ser no esencial es una propiedad de clase. Sea x ∈E no
esencial: es decir, ∃z ∈E tal que x →z y z ̸→x. Consideremos y ∈[x]↔: usemos el mismo z para
probar que y es no esencial:
⋄y →z: pues y →x ∧x →z =⇒x →z.
⋄z ̸→y: por contradicci´on, si z →y, entonces z →y ∧y →x =⇒z →x, lo que contradice la
no-esencialidad de x. Luego z ̸→y
Luego y es no esencial. Como y ∈[x]↔, se concluye que la no-esencialidad es propiedad de clase.
Ahora, sea i ∈E un estado no esencial tal que existe j ∈E con i →j y j ̸→i. Queremos demostrar
que,
P

X
n≥0
1{Xn=i} = ∞, Tj < ∞

X0 = i

= 0
Sea A = {P
n≥0 1{Xn=i} = ∞} (el evento de visitar i infinitas veces). Si {Tj < ∞} ocurre, la cadena
alcanza el estado j en un tiempo finito.
Dado que j ̸→i, una vez que la cadena llega a j, la probabilidad de regresar a i es cero para todo
tiempo posterior. Esto implica que el n´umero total de visitas a i debe estar limitado por el tiempo
de llegada Tj:
{Tj < ∞} =⇒
X
n≥0
1{Xn=i} ≤Tj < ∞
De lo cual, se concluye que,
P

X
n≥0
1{Xn=i} = ∞, Tj < ∞

X0 = i

= 0
Luego, aplicando la descomposici´on sobre el espacio muestral condicionada a X0 = i:
P(A | X0 = i) = P(A ∩{Tj < ∞} | X0 = i) + P(A ∩{Tj = ∞} | X0 = i)
En donde, P(A ∩{Tj < ∞} | X0 = i) = 0. Con lo cual,
P(A | X0 = i) = P(A ∩{Tj = ∞} | X0 = i)
Por monoton´ıa se concluye,
P

X
n≥0
1{Xn=i} = ∞

X0 = i

≤P(Tj = ∞| X0 = i)
La condici´on i →j implica que:
P(Tj < ∞| X0 = i) > 0 =⇒P(Tj = ∞| X0 = i) < 1
Con lo cual,
P

X
n≥0
1{Xn=i} = ∞

X0 = i

< 1
2

Recordando que para cualquier estado i, la probabilidad de visitarlo infinitas veces es 1 si es recurrente
y 0 si es transiente. Como hemos demostrado que esta probabilidad es estrictamente menor a 1,
concluimos que,
P

X
n≥0
1{Xn=i} = ∞

X0 = i

= 0
Lo cual define al estado i como un estado transiente.
Para demostrar que si |E| ≤+∞entonces existe un estado esencial, procederemos por contradicci´on.
Supongamos que todos los estados en E son no esenciales. Sea x0 ∈E. Por definici´on de no esenciali-
dad, existe x1 ∈E tal que x0 →x1 y x1 ̸→x0. De igual forma, para x1 existe x2 ∈E tal que x1 →x2
y x2 ̸→x1. N´otese que x2 debe ser distinto de x0 y x1; de lo contrario, se perder´ıa la condici´on de no
retorno por transitividad.
Repitiendo el argumento, podemos construir una sucesi´on {xn}n∈N de estados distintos tales que
xn →xn+1 pero xn+1 ̸→xn. Dado que E es un conjunto finito, llegamos a una contradicci´on.
Por otro lado, consideremos el espacio de estados E = {0, 1, 2, . . . } (|E| = +∞) con probabilidades
de transici´on:
pi,j =
(
1
si j = i + 1
0
en otro caso
Para cualquier i ∈E, se cumple que i →i + 1, pero i + 1 ̸→i (la cadena nunca retrocede). Por lo
tanto, todo estado i ∈E es no esencial.
Distribuci´on de Puntaje:
⋄(0.5 puntos) Iniciar la demostraci´on de la propiedad de clase tomando un estado x no esencial
y un estado y que comunique con ´el
⋄(1.0 puntos) Probar rigurosamente que y →z y z ̸→y apoy´andose de forma correcta en la
transitividad
⋄(1.0 puntos) Justificar matem´aticamente que la probabilidad conjunta de realizar visitas infi-
nitas al estado i y alcanzar j en tiempo finito es cero
⋄(1.0 puntos)
Aplicar la descomposici´on condicionada al estado inicial X0 = i y acotar la
expresi´on mediante monoton´ıa
⋄(1.0 puntos)
Usar la condici´on i →j para concluir que la probabilidad de recurrencia es
estrictamente menor a 1, probando as´ı la transigencia del estado i
⋄(0.5 puntos) Plantear correctamente el inicio de la demostraci´on por contradicci´on asumiendo
que todos los estados son no esenciales para un espacio finito
⋄(1.0 puntos) Construir la sucesi´on infinita de estados distintos xn y deducir la contradicci´on
apoy´andose en la cardinalidad finita del conjunto
⋄(0.5 puntos) Proponer un espacio de estados de cardinalidad infinita v´alido para construir el
contraejemplo
⋄(1.0 puntos)
Definir la din´amica o matriz de transici´on y justificar claramente por qu´e la
cadena nunca retrocede, haciendo que todo estado sea no esencial
2. Sea (Xn)n≥0 una cadena de Markov con espacio de estados N0 y probabilidades de transici´on
pi,j =













1
si i = 0, j = 1,
pi,i+1
si i ≥1, j = i + 1,
pi,i−1
si i ≥1, j = i −1,
0
en otro caso,
donde, para todo i ≥1,
pi,i−1 + pi,i+1 = 1,
pi,i+1 =
i + 1
i
2
pi,i−1.
3

(a) Demuestre que,
P (Xn ≥1, ∀n ≥1| X0 = 0) = 6
π2 .
Indicaci´on: Puede ser de utilidad el siguiente resultado,
∞
X
n=0
1
n2 = π2
6
Soluci´on: Sea
T0 = ´ınf{n ≥1 : Xn = 0}
el tiempo de retorno al estado 0. Para cada i ≥0, definimos
ui = P(T0 < ∞| X0 = i),
es decir, ui corresponde a la probabilidad de que la cadena alcance el estado 0 en alg´un instante
futuro cuando parte desde i.
Nuestro objetivo es calcular la probabilidad de que la cadena nunca vuelva a 0 cuando parte
desde 1, es decir,
1 −u1 = P(T0 = ∞| X0 = 1).
Por la propiedad de Markov y utilizando un an´alisis de primer paso, para todo i ≥1 se cumple
ui = pi,i+1ui+1 + pi,i−1ui−1.
Como pi,i+1 + pi,i−1 = 1, esta relaci´on puede reescribirse como
pi,i+1(ui −ui+1) = pi,i−1(ui−1 −ui).
Definimos ahora la sucesi´on
di = ui−1 −ui,
i ≥1.
Usando la relaci´on dada en el enunciado
pi,i−1
pi,i+1
=
i2
(i + 1)2 ,
se obtiene
di+1 =
i2
(i + 1)2 di.
Aplicando esta relaci´on de manera recursiva se deduce que
dk = 1
k2 d1,
k ≥1.
Sumando las diferencias telesc´opicas y utilizando que l´ımn→∞un = 0, obtenemos
u0 −l´ım
n→∞un =
∞
X
k=1
dk,
y por lo tanto
1 = d1
∞
X
k=1
1
k2 .
Utilizando el resultado
∞
X
k=1
1
k2 = π2
6 ,
se concluye que
d1 = 6
π2 .
Finalmente, como d1 = u0 −u1 = 1 −u1, obtenemos
P(Xn ≥1, ∀n ≥1 | X0 = 0) = 6
π2 .
Distribuci´on de Puntaje:
4

⋄(0.5 puntos)
Definir el tiempo de retorno y la probabilidad de absorci´on planteando
claramente el objetivo 1 −u1
⋄(0.5 puntos) Establecer la ecuaci´on de an´alisis de primer paso bas´andose en la propiedad
de Markov
⋄(0.5 puntos) Definir las diferencias di y encontrar la relaci´on recursiva a partir del cociente
de probabilidades
⋄(0.5 puntos) Deducir algebraicamente el t´ermino general de la sucesi´on dk en funci´on de
d1
⋄(0.5 puntos) Plantear la suma telesc´opica reconociendo expl´ıcitamente que el l´ımite de un
tiende a cero
⋄(0.5 puntos) Reemplazar el valor conocido de la serie y concluir correctamente el valor
final de la probabilidad pedida
(b) Muestre que esta cadena de Markov cumple que
P

l´ım
n→∞Xn = ∞|X0 = 0

= 1.
Soluci´on:
Del resultado anterior se tiene que
P(Xn ≥1, ∀n ≥1 | X0 = 0) = 6
π2 .
Por lo tanto, la probabilidad de que la cadena retorne al estado 0 partiendo de 0 es
f00 = P(T0 < ∞| X0 = 0) = 1 −6
π2 .
Como f00 < 1, se concluye que el estado 0 es transiente. Adem´as, para todo i ≥1 se tiene
pi,i+1 > 0 y pi,i−1 > 0, por lo que cada estado puede alcanzarse desde cualquier otro mediante
una sucesi´on finita de transiciones. Por lo tanto, la cadena es irreducible en el espacio de estados
E = N0. En una cadena de Markov irreducible, si un estado es transiente entonces todos los
estados del espacio de estados son transientes. Por consiguiente, todo estado j ∈N0 es transiente.
Sea Vj = P∞
n=0 1{Xn=j} el n´umero total de visitas al estado j. La transiencia de j implica que
P(Vj < ∞| X0 = 0) = 1.
Como esto ocurre para todo j ∈N0, se deduce que cada estado es visitado solo un n´umero finito
de veces casi seguramente. En particular, para cualquier M ∈N el conjunto finito {0, 1, . . . , M}
puede ser visitado solo un n´umero finito de veces. Por lo tanto, existe un instante aleatorio N
tal que
Xn > M
para todo n ≥N.
Dado que M es arbitrario, se concluye que
P

l´ım
n→∞Xn = ∞| X0 = 0

= 1.
Distribuci´on de Puntaje:
⋄(0.5 puntos)
Calcular la probabilidad de retorno f00 y deducir que el estado inicial es
transiente al ser menor que 1
⋄(0.5 puntos) Argumentar que la cadena es irreducible debido a que las probabilidades de
transici´on adyacentes son siempre estrictamente positivas
⋄(0.5 puntos) Concluir te´oricamente que todos los estados son transientes y por ende se
visitan una cantidad finita de veces casi seguramente
⋄(0.5 puntos) Explicar que al agotarse las visitas a cualquier subconjunto finito de estados
la cadena necesariamente tiende a infinito
(c) Si se tiene que:
pi,i+1 =
i + 1
i
α
pi,i−1,
α > 0
¿C´omo cambiar´ıa su respuesta a la pregunta anterior?
Soluci´on: Procedemos de manera an´aloga al ejercicio anterior. Recordemos que si
ui = P(T0 < ∞| X0 = i),
di = ui−1 −ui,
5

entonces se obtiene la relaci´on
dk = 1
kα d1.
Sumando las diferencias telesc´opicas,
1 = u0 −l´ım
n→∞un =
∞
X
k=1
dk = d1
∞
X
k=1
k−α.
Si α > 1: la serie P∞
k=1 k−α converge y
d1 =
 ∞
X
k=1
k−α
!−1
=
1
ζ(α) > 0.
Por lo tanto la probabilidad de escape es positiva, la cadena es transiente y
P

l´ım
n→∞Xn = ∞| X0 = 0

= 1.
Si α ≤1: la serie P∞
k=1 k−α diverge, lo que implica d1 = 0. En consecuencia u1 = 1, el estado 0
es recurrente y
P

l´ım
n→∞Xn = ∞| X0 = 0

= 0.
Distribuci´on de Puntaje:
⋄(0.5 puntos) Adaptar la relaci´on recursiva y la suma telesc´opica incorporando el par´ametro
gen´erico α
⋄(1.0 puntos) Analizar correctamente el caso α > 1 justificando la convergencia de la serie
junto con la transigencia de la cadena y el l´ımite hacia infinito
⋄(1.0 puntos) Analizar correctamente el caso α ≤1 deduciendo que la serie diverge haciendo
el estado recurrente y provocando que la probabilidad pedida sea nula
6

Pregunta 2
Un afamado profesor universitario ha decidido tener caballos de carreras, por lo cual ha comprado 1 potro
y 2 potrancas. La intenci´on de este profesor es que sus finasangres se encuentren compitiendo cada fin de
semana. Lo ´unico que puede impedir que sus caballos compitan son las lesiones. Dado esto, ha encomendado
un estudio que permita determinar las probabilidades de que un caballo se lesione. El resultado de este
estudio ha arrojado que la probabilidad que un potro se lesione es de p y la probabilidad de que una
potranca se lesione es de q. Adem´as, el tratamiento para recuperar estas lesiones dura exactamente una
semana y es seguro que durante la primera semana despu´es del tratamiento el caballo no se lesiona.
Lamentablemente, nuestro profesor no cuenta con el tiempo suficiente para responder este problema, por
lo que a usted se le pide que:
(a) Muestre que el problema descrito anteriormente puede modelarse mediante una Cadena de Markov
en Tiempo Discreto. Para ello, defina claramente el espacio de estados y determine la matriz de
probabilidades de transici´on correspondiente.
Soluci´on: Sea n ∈N0. Para la semana n, definimos el estado del potro:
X(1)
n
=
(
1,
si el potro est´a sano y puede competir
0,
si el potro est´a lesionado y en recuperaci´on
De manera an´aloga, para las dos potrancas (i ∈{2, 3}), definimos:
X(i)
n
=
(
1,
si la potranca i −1 est´a sana y puede competir
0,
si la potranca i −1 est´a lesionada y en recuperaci´on
El estado global del sistema se define como,
Xn = (X(1)
n , X(2)
n , X(3)
n )
Por lo tando
Ω= {(1, 1, 1), (0, 1, 1), (1, 0, 1), (1, 1, 0), (0, 0, 1), (0, 1, 0), (1, 0, 0), (0, 0, 0)}
Note que,
⋄La probabilidad de que un caballo se lesione depende exclusivamente de que se encuentre sano
en la semana actual (probabilidad p o q).
⋄Si un caballo se lesiona (estado 0), la recuperaci´on dura un tiempo determinista de exactamente
una semana, tras la cual pasa inevitablemente a estar sano (estado 1)
En consecuencia, el estado del sistema en la semana n+1 est´a condicionado ´unicamente por el estado
en la semana n. Luego, la matriz de probabilidades de transici´on esta dada por,
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


(1, 1, 1)
(0, 1, 1)
(1, 0, 1)
(1, 1, 0)
(0, 0, 1)
(0, 1, 0)
(1, 0, 0)
(0, 0, 0)
(1, 1, 1)
(1 −p)(1 −q)2
p(1 −q)2
(1 −p)q(1 −q)
(1 −p)q(1 −q)
pq(1 −q)
pq(1 −q)
(1 −p)q2
pq2
(0, 1, 1)
(1 −q)2
0
q(1 −q)
q(1 −q)
0
0
q2
0
(1, 0, 1)
(1 −p)(1 −q)
p(1 −q)
0
(1 −p)q
0
pq
0
0
(1, 1, 0)
(1 −p)(1 −q)
p(1 −q)
(1 −p)q
0
pq
0
0
0
(0, 0, 1)
1 −q
0
0
q
0
0
0
0
(0, 1, 0)
1 −q
0
q
0
0
0
0
0
(1, 0, 0)
1 −p
p
0
0
0
0
0
0
(0, 0, 0)
1
0
0
0
0
0
0
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


Distribuci´on de Puntaje:
⋄(0.5 puntos)
Definir correctamente las variables de estado individuales para el potro y las
potrancas
⋄(1.0 puntos) Establecer expl´ıcitamente el espacio de estados global Ω
⋄(0.5 puntos) Justificar la propiedad de Markov notando que el estado de la semana siguiente
depende exclusivamente del estado actual
⋄(2.0 puntos) Construir correctamente la matriz de probabilidades de transici´on P con todos
sus coeficientes bien calculados
7

(b) Determine si la cadena de Markov admite una distribuci´on estacionaria. En caso afirmativo, escriba
el sistema de ecuaciones que permite calcular dicha distribuci´on.
Soluci´on: Es f´acil notar que desde cada uno de los estados es posible llegar a cualquier otro estado, ya
sea directamente o pasando por alg´un estado intermedio. Por lo tanto, todos los estados se comunican
y la cadena posee una ´unica clase de comunicaci´on. Dado que el espacio de estados es finito, la cadena
es irreducible. En consecuencia, existe una ´unica distribuci´on estacionaria.
La distribuci´on estacionaria π debe satisfacer
π = πP,
junto con la condici´on de normalizaci´on
X
x∈S
π(x) = 1,
donde Ω= {(1, 1, 1), (0, 1, 1), (1, 0, 1), (1, 1, 0), (0, 0, 1), (0, 1, 0), (1, 0, 0), (0, 0, 0)}.
En forma matricial, si
π =
 π(1,1,1)
π(0,1,1)
π(1,0,1)
π(1,1,0)
π(0,0,1)
π(0,1,0)
π(1,0,0)
π(0,0,0)

,
entonces debe cumplirse
π = πP,
lo que equivale al siguiente sistema de ecuaciones:
π111 = π111(1 −p)(1 −q)2 + π011(1 −q)2 + π101(1 −p)(1 −q)
+ π110(1 −p)(1 −q) + π001(1 −q) + π010(1 −q)
+ π100(1 −p) + π000,
π011 = π111p(1 −q)2 + π101p(1 −q) + π110p(1 −q) + π100p,
π101 = π111(1 −p)q(1 −q) + π011q(1 −q) + π110(1 −p)q + π010q,
π110 = π111(1 −p)(1 −q)q + π011(1 −q)q + π101(1 −p)q + π001q,
π001 = π111pq(1 −q) + π110pq,
π010 = π111p(1 −q)q + π101pq,
π100 = π111(1 −p)q2 + π011q2,
π000 = π111pq2,
1 = π111 + π011 + π101 + π110 + π001 + π010 + π100 + π000.
Distribuci´on de Puntaje:
⋄(1.0 puntos) Argumentar correctamente la existencia y unicidad de la distribuci´on estacionaria
mediante la irreducibilidad de la cadena
⋄(0.5 puntos) Plantear la condici´on matricial π = πP y la condici´on de normalizaci´on P π(x) =
1
⋄(2.0 puntos) Desarrollar correctamente el sistema de ecuaciones expl´ıcito para todos los estados
del problema
(c) Considerando el largo plazo (asuma conocidas las probabilidades estacionarias), calcule la proporci´on
del tiempo en que ambas potrancas est´an corriendo cuando el potro est´a lesionado.
Soluci´on: En este caso se pide simplemente la probabilidad de estar en el estado (0, 1, 1), es decir,
π011.
Distribuci´on de Puntaje:
⋄(1.0 puntos) Identificar directamente que la proporci´on solicitada en el largo plazo corresponde
a la probabilidad estacionaria π011
(d) Calcule la probabilidad, en el largo plazo (asuma conocidas las probabilidades estacionarias), de que
al menos haya un caballo (potro o potranca) lesionado.
Soluci´on: En este caso se pide la probabilidad de estar en un estado en que al menos un caballo est´e
lesionado. Esto es igual a 1 menos la probabilidad de que no haya ning´un lesionado, es decir, 1−π111.
Distribuci´on de Puntaje:
8

⋄(1.5 puntos) Plantear la soluci´on como el complemento del estado en que todos est´an sanos,
es decir, deducir que la probabilidad es 1 −π111
(e) Si un nuevo estudio indica que en promedio un potro corriendo reporta utilidades semanales por
1[u.g.h] (unidades de ganancias h´ıpicas) y una potranca 3[u.g.h] y asumiendo que un caballo -potro
o potranca- corre much´ısimas semanas antes de irse al campo, ¿a cu´anto ascender´an las ganancias de
este afamado profesor?
Soluci´on: Sea U la utilidad esperada del profesor. Esta se obtiene como la suma de las utilidades
asociadas a cada estado ponderadas por la probabilidad estacionaria de encontrarse en dicho estado.
Por lo tanto, se tiene
U = 7π111 + 6π011 + 4π101 + 4π110 + π100 + 3π010 + 3π001 + 0π000
Distribuci´on de Puntaje:
⋄(0.5 puntos) Plantear que la utilidad esperada es la suma de las utilidades ponderadas por su
respectiva probabilidad estacionaria
⋄(1.0 puntos) Asignar los valores correctos de ganancia para cada estado en la ecuaci´on de la
utilidad esperada U
Ahora, asuma que una de las potrancas, “Zenyatta”, ha terminado sus labores como corredora y el profesor
la destinar´a a la reproducci´on. Para ello, la env´ıa al campo y la deja suelta junto con los K potros que
posee. El proceso de cruza de esta potranca es al azar, por lo tanto, cualquiera de los potros posee la misma
probabilidad de ser el pr´oximo en cruzarse con ella. La probabilidad de que quede pre˜nada por el potro k un
a˜no cualquiera es de pk, siendo 1 −pk la probabilidad de que no la deje pre˜nada. Adem´as, el profesor sabe
que su yegua regalona no se cruzar´a m´as de 3 veces por a˜no, sabiendo tambi´en que si un a˜no cualquiera
no queda pre˜nada al a˜no siguiente la probabilidad de quedar pre˜nada en su ´ultima cruza (y entonces la
tercera de ese a˜no) ser´a igual a 1.
(f) Con esta informaci´on, construya una Cadena de Markov en Tiempo Discreto que permita modelar si
la potranca estar´a pre˜nada o no un a˜no cualquiera.
Soluci´on: Sea,
NP1: A˜no 1 sin pre˜nar
NP2: A˜no 2 sin pre˜nar
P: A˜no pre˜nado
En este caso α corresponde a la probabilidad de que la yegua quede pre˜nada:
α = [Probabilidad de que quede pre˜nada]
α = [Probabilidad de que quede pre˜nada 1er o 2do o 3er Intento]
α = [Prob. de que quede pre˜nada 1er Intento] + [Prob. de que quede pre˜nada 2do y no 1ro]
+ [Prob. de que quede pre˜nada 3er y no 2do ni 1ro]
De esta manera, se puede dejar expresada la probabilidad α como la suma de 3 probabilidades:
NP1
NP2
P
α
α
1 −α
1
1 −α
Con
α = P1 + P2 + P3
9

En donde cada una de las probabilidades es:
P1 =
K
X
k=1
pk · 1
K
P2 =
" K
X
k=1
pk · 1
K
#
·
"
1 −
K
X
k=1
pk · 1
K
#
P3 =
" K
X
k=1
pk · 1
K
#
·
"
1 −
" K
X
k=1
pk · 1
K
# "
1 −
K
X
k=1
pk · 1
K
##
Se asume que el mismo potro puede cruzarse m´as de una vez
Distribuci´on de Puntaje:
⋄(1.0 puntos) Definir claramente los nuevos estados de la cadena y proponer un esquema de
transiciones v´alido
⋄(0.5 puntos)
Plantear que la probabilidad total de pre˜nez α corresponde a la suma de las
probabilidades de ´exito de los tres intentos posibles
⋄(2.0 puntos)
Calcular de manera correcta las probabilidades P1, P2 y P3 considerando la
independencia y el factor pk
10

Problema 3
Los detectives privados Valerian y Chico se dedican a resolver cr´ımenes y a encontrar personas perdidas en
la ciudad. Valerian logra encontrar a una persona a una tasa µV personas/semana. Por su parte, Chico tiene
una tasa de µC personas/semana. La gente del pueblo llega a la oficina de estos investigadores privados a
una tasa de λP clientes/semana. Cada investigador no atiende m´as de un caso a la vez, por lo que si un
cliente aparece y ambos detectives se encuentran trabajando en un caso, la secretaria de los detectives, la
se˜norita Willow los enviar´a a una agencia amiga.
En caso que llegue un crimen, cosa que sucede seg´un una tasa de λC cr´ımenes/semana, ambos detectives
le dar´an prioridad. Esto quiere decir que ambos trabajar´an en el caso y que si estuvieran atendiendo un
caso de persona perdida lo dejar´an en espera hasta que logren resolver el crimen para el que est´an siendo
contratados. La tasa a la que resuelven casos de crimen es µCV cr´ımenes/semana. Si mientras se encuentran
resolviendo un crimen se les solicita resolver otro caso similar, ellos se sentir´an frustrados por no poder
atenderlo y le pedir´an a la se˜norita Willow que borre todos los registros actuales. Si los registros actuales
son borrados cualquier caso de personas perdidas que hubiesen dejado en espera ser´a enviado a una agencia
amiga.
(a) Construya una Cadena de Markov en Tiempo Continuo que permita modelar el estado de ocupaci´on
de los detectives.
Soluci´on: En primer lugar, los estados deben detectar la ocupaci´on de los detectives. Esta puede ser
distinta cuando se trata de atender casos de personas perdidas, pero coincide cuando se encuentran
resolviendo un crimen. Como la cadena que se desea construir debe cumplir con las propiedades
de una Cadena de Markov en Tiempo Continuo, las probabilidades de transici´on del proceso deben
respetar la siguiente ecuaci´on:
Pij(t) = P(X(t + s) = j|X(s) = i),
∀i, j
∀s, t ≥0
Donde X(·) corresponde al estado actual de cada detective. Esta variable puede contener informaci´on
sobre el estado inmediatamente anterior ya que existe la posibilidad de dejar clientes en espera si en
el instante anterior el detective se encontraba resolviendo un caso de tipo crimen. Los estados posibles
son los siguientes:
(0) : Ambos detectives se encuentran desocupados.
(1) : Chico est´a ocupado resolviendo un caso normal y Valerian se encuentra desocupado.
(2) : Ambos detectives se encuentran resolviendo un caso normal.
(3) : Valerian est´a ocupado resolviendo un caso normal y Chico se encuentra desocupado.
(4) : Ambos detectives resuelven un crimen, Chico deja su caso normal en pausa y Valerian no tiene
otros casos en pausa.
(5) : Ambos detectives resuelven un crimen y dejan sus casos normales en pausa.
(6) : Ambos detectives resuelven un crimen, Valerian deja su caso normal en pausa y Chico no tiene
otros casos en pausa.
(7) : Ambos detectives resuelven un crimen y no tienen otros casos en pausa.
A partir de estos estados, podemos construir la siguiente cadena de estados:
11

1
3
4
5
7
2
6
0
µc
λp
λc
λc
λc
µcv
µcv
λc
λc
µcv
λp/2
µc
λp/2
µv
λc
λc
µcv
µv
λp
Distribuci´on de Puntaje:
⋄(0.5 puntos) Indicar la relaci´on de transici´on o propiedad subyacente para el modelo de tiempo
continuo
⋄(1.5 puntos) Identificar y definir claramente los 8 estados del sistema detallando la ocupaci´on
de ambos detectives
⋄(3.0 puntos) Construir el diagrama de transiciones asignando todas las tasas correctas corres-
pondientes a λ y µ
(b) Justifique la existencia de una distribuci´on de probabilidades estacionarias y construya el sistema de
ecuaciones que permite calcularlas.
Soluci´on: Dado que todos los estados est´an conectados y que la probabilidad de estar en un estado
cualquiera existe y es independiente del estado inicial, se tiene que existe la distribuci´on l´ımite y
por ende, una distribuci´on de probabilidades estacionarias. Adem´as, a partir del diagrama se puede
plantear un sistema de ecuaciones en torno a los estados, donde la tasa a la cual el proceso deja un
cierto estado j cualquiera debe ser igual a la tasa a la cual el proceso entra al estado j.
P0 · (λP + λC) = P1 · µC + P3 · µV + P7 · µCV
P1 · (λP + λC + µC) = P0 · λP /2 + P2 · µV + P4 · µCV
P2 · (µV + µC + λC) = P1 · λP + P3 · λP + P5 · µCV
P3 · (λP + µV + λC) = P0 · λP /2 + P2 · µC + P6 · µCV
P4 · (µCV + λC) = P1 · λC
P5 · (µCV + λC) = P2 · λC
P6 · (µCV + λC) = P3 · λC
P7 · µCV = λC · (P0 + P4 + P5 + P6)
P0 + P1 + P2 + P3 + P4 + P5 + P6 + P7 = 1
Distribuci´on de Puntaje:
⋄(1.0 puntos)
Justificar correctamente la existencia de la distribuci´on estacionaria argumen-
tando que los estados est´an conectados
12

⋄(0.5 puntos)
Establecer el principio fundamental de balance donde la tasa de salida debe
igualar a la tasa de entrada
⋄(2.5 puntos)
Construir correctamente el sistema de ecuaciones de balance para todos los
estados de la cadena
⋄(0.5 puntos) Incluir expl´ıcitamente la ecuaci´on de normalizaci´on obligatoria
(c) Indique la proporci´on del tiempo en que ambos detectives se encuentran desocupados.
Soluci´on: La proporci´on del tiempo en que ambos detectives se encuentran desocupados est´a dada
por el estado asociado a la condici´on de desocupaci´on de ambos, en este caso, el estado 0.
Proporci´on del tiempo desocupados = P0
Distribuci´on de Puntaje:
⋄(1.0 puntos) Identificar directamente que la proporci´on del tiempo solicitada corresponde a la
probabilidad del estado 0 denotada por P0
(d) Indique la cantidad promedio de casos que se encuentran resolviendo en un instante cualquiera de
tiempo.
Soluci´on:
La cantidad de casos que se encontrar´an resolviendo est´a dada por la probabilidad de
resolver un caso por la cantidad de casos que se est´an resolviendo en ese estado.
Cantidad de casos = P1 · 1 + P2 · 2 + P3 · 1 + (P4 + P5 + P6 + P7) · 1
Distribuci´on de Puntaje:
⋄(0.5 puntos) Plantear la m´etrica solicitada como un valor esperado sobre la cantidad de casos
⋄(1.5 puntos) Asignar los pesos correctos a las probabilidades estacionarias en la suma, multi-
plicando por 2 para el estado 2 y por 1 para el resto de los estados activos
(e) Si los detectives se encuentran actualmente resolviendo un crimen, indique el tiempo promedio que
le tomar´a volver a resolver un caso de crimen.
Soluci´on: Dado que los detectives se encuentran resolviendo un caso actualmente, se debe estimar
el tiempo esperado que les tomar´a cerrar el caso, sumado al tiempo esperado necesario para que se
presente un nuevo caso.
Como el tiempo de resoluci´on de un crimen es una variable exponencial de tasa

1
µCV

, este no posee
memoria, por lo que el tiempo remanente esperado ser´a de
1
µCV semanas.
Por otro lado, el tiempo esperado para que se presente un nuevo caso de crimen corresponde a la tasa
asociada a la aparici´on de un crimen

1
λC

semanas.
As´ı, el tiempo promedio que les tomar´a volver a resolver un crimen ser´a:
Tiempo esperado para retomar un crimen =
1
µCV
+ 1
λC
Distribuci´on de Puntaje:
⋄(1.0 puntos) Justificar mediante la p´erdida de memoria de la distribuci´on exponencial que el
tiempo remanente del crimen actual es 1/µCV
⋄(1.0 puntos) Identificar que el tiempo esperado para la llegada de un nuevo caso de crimen
corresponde a 1/λC
⋄(0.5 puntos)
Sumar ambos componentes para obtener el tiempo promedio total de forma
correcta
13

Problema 4
Considere el siguiente experimento probabil´ıstico. Se tienen 2n part´ıculas indistinguibles distribuidas entre
dos urnas, denominadas urna 1 y urna 2. El sistema evoluciona en tiempos discretos t = 0, 1, 2, . . . . En
cada instante de tiempo se selecciona una de las 2n part´ıculas al azar, todas con la misma probabilidad de
ser elegidas. Una vez seleccionada, la part´ıcula se traslada a la urna opuesta: si la part´ıcula se encontraba
en la urna 1 pasa a la urna 2, y si se encontraba en la urna 2 pasa a la urna 1.
Para describir el estado del sistema en cada instante t, definimos la variable aleatoria
Xt = n´umero de part´ıculas que se encuentran en la urna 1 en el instante t.
En consecuencia, los posibles valores de Xt pertenecen al conjunto {0, 1, 2, . . . , 2n}.
Este proceso describe la evoluci´on temporal de la distribuci´on de las part´ıculas entre ambas urnas. En lo que
sigue estudiaremos las probabilidades de transici´on entre los distintos estados del sistema y analizaremos
su comportamiento a largo plazo.
(a) Justifique porqu´e el proceso {Xt}t≥0 puede modelarse como una cadena de Markov. Determine la ma-
triz de probabilidades de transici´on asociada al proceso {Xt}t≥0, identificando claramente el conjunto
de estados.
Soluci´on: El proceso {Xt}t≥0 es una cadena de Markov porque satisface la propiedad de Markov:
P(Xt+1 = j | Xt = i, Xt−1, . . . , X0) = P(Xt+1 = j | Xt = i).
En efecto, si Xt = k (hay k part´ıculas en la urna 1), en el instante siguiente se elige una part´ıcula
uniformemente entre las 2n. Por tanto,
P(Xt+1 = k −1 | Xt = k) = k
2n,
P(Xt+1 = k + 1 | Xt = k) = 2n −k
2n
,
y cero en otro caso.
Estas probabilidades dependen solo del estado actual k y no del tiempo t, por lo que la cadena es
estacionaria en sus probabilidades de transici´on. El espacio de estados es {0, 1, . . . , 2n}.
Distribuci´on de Puntaje:
⋄(1.0 puntos)
Justificar la propiedad de Markov indicando que el estado siguiente depende
´unicamente de la cantidad actual de part´ıculas y no de la historia previa
⋄(0.5 puntos) Identificar expl´ıcitamente el espacio de estados
⋄(1.5 puntos) Determinar correctamente las probabilidades de transici´on hacia k −1 y hacia
k + 1
(b) Considere el vector w = (w0, . . . , w2n) definido por
wi =
 2n
i

22n ,
i = 0, . . . , 2n.
1. Verifique que w define una distribuci´on de probabilidad.
Soluci´on: Para verificar que w es una distribuci´on de probabilidad basta comprobar que wi ≥0
y que P2n
i=0 wi = 1.
Claramente wi ≥0 para todo i porque
 2n
i

≥0. Adem´as, por el teorema binomial,
2n
X
i=0
wi =
2n
X
i=0
 2n
i

22n =
1
22n
2n
X
i=0
2n
i

= (1 + 1)2n
22n
= 1.
Por lo tanto, w define una distribuci´on de probabilidad.
Distribuci´on de Puntaje:
⋄(0.5 puntos) Verificar y argumentar que todas las componentes del vector son no negativas
⋄(1.5 puntos)
Demostrar que la suma de los elementos es 1 utilizando el teorema del
binomio o un desarrollo equivalente
14

2. Considere 2n variables aleatorias independientes Y1, . . . , Y2n tales que
P(Yk = 1) = P(Yk = 0) = 1
2.
Defina
S =
2n
X
k=1
Yk.
Determine la distribuci´on de S y deduzca que
P(S = i) = wi.
Soluci´on: Como Y1, . . . , Y2n son variables independientes con
P(Yk = 1) = P(Yk = 0) = 1
2,
entonces Yk ∼Bernoulli
  1
2

. Por lo tanto, la suma
S =
2n
X
k=1
Yk
sigue una distribuci´on binomial con par´ametros (2n, 1
2).
En consecuencia,
P(S = i) =
2n
i
   1
2
i   1
2
2n−i =
 2n
i

22n = wi,
i = 0, . . . , 2n.
Distribuci´on de Puntaje:
⋄(1.0 puntos) Identificar que las variables aleatorias individuales siguen una distribuci´on
de Bernoulli con probabilidad de ´exito 1/2
⋄(1.0 puntos) Deducir que la suma S corresponde a una distribuci´on Binomial con par´ame-
tros 2n y 1/2
⋄(0.5 puntos)
Concluir algebraicamente que la probabilidad del evento S = i coincide
exactamente con la expresi´on de wi
(c) Demuestre que para todo i = 1, . . . , 2n −1
wi = wi−1
2n −(i −1)
2n
+ wi+1
i + 1
2n .
Explique brevemente qu´e sugiere este resultado sobre la distribuci´on de las part´ıculas entre las urnas
cuando el sistema ha evolucionado durante un per´ıodo considerable de tiempo.
Soluci´on: Soluci´on: Usando wi =
 2n
i

22n y las identidades
 2n
i −1
2n −(i −1)
i
=
2n
i

,
 2n
i + 1
 i + 1
2n −i =
2n
i

,
se obtiene
wi−1
2n −(i −1)
2n
=
  2n
i−1

22n
2n −(i −1)
2n
=
 2n
i

22n
i
2n,
y
wi+1
i + 1
2n
=
  2n
i+1

22n
i + 1
2n
=
 2n
i

22n
2n −i
2n
.
Sumando,
wi−1
2n −(i −1)
2n
+ wi+1
i + 1
2n
=
 2n
i

22n = wi.
Esto muestra que w es una distribuci´on estacionaria de la cadena. Por lo tanto, despu´es de mucho
tiempo el n´umero de part´ıculas en la urna 1 se distribuye aproximadamente como Binomial(2n, 1
2),
es decir, las part´ıculas tienden a repartirse de manera casi equilibrada entre ambas urnas.
Distribuci´on de Puntaje:
15

⋄(2.0 puntos)
Utilizar identidades combinatorias para expandir correctamente los t´erminos
asociados a wi−1 y wi+1
⋄(1.0 puntos) Realizar correctamente la suma algebraica demostrando que el resultado equivale
a wi
⋄(1.0 puntos) Explicar que el resultado prueba que es una distribuci´on estacionaria y concluir
que las part´ıculas tender´an a un equilibrio en el largo plazo
(d) Realice una simulaci´on del proceso descrito anteriormente utilizando Python. Considere 2n = 40.
⋄Comience con todas las part´ıculas en la urna 1, es decir
X0 = 40.
⋄Simule el sistema durante T = 100000 pasos.
Luego, grafique la evoluci´on temporal de Xt. Compare este histograma con la distribuci´on te´orica.
¿Qu´e sugieren sus resultados acerca del comportamiento del sistema en el largo plazo?. Comente.
Soluci´on:
0
20000
40000
60000
80000
100000
t
10
15
20
25
30
35
40
X_t
Evolución de Xt
Figura 1: Evoluci´on de Xt con X0 = 40 y T = 100000.
0
5
10
15
20
25
30
35
40
i
0.00
0.02
0.04
0.06
0.08
0.10
0.12
Probabilidad
Distribución empírica vs teórica
Figura 2: Distribuci´on emp´ırica de Xt vs. wi = (
40
i )
240 .
El histograma de los valores visitados por Xt coincide aproximadamente con la distribuci´on te´orica
wi =
 40
i

240 .
16

Esto sugiere que, tras un n´umero grande de iteraciones, la cadena converge a su distribuci´on es-
tacionaria. En el largo plazo, el n´umero de part´ıculas en la urna 1 se comporta aproximadamente
como una Binomial(40, 1
2), concentr´andose alrededor de 20. Es decir, el sistema tiende a un reparto
aproximadamente equilibrado de part´ıculas entre ambas urnas.
Distribuci´on de Puntaje:
⋄(1.5 puntos)
Comparar las gr´aficas e indicar correctamente que el histograma emp´ırico se
ajusta a la distribuci´on te´orica analizada
⋄(1.0 puntos)
Concluir expl´ıcitamente que la cadena converge a su distribuci´on estacionaria
tras muchas iteraciones
⋄(1.0 puntos) Interpretar de forma pr´actica que el sistema se equilibra concentrando aproxi-
madamente la mitad de las part´ıculas en la urna 1
17

