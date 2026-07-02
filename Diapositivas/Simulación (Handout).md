Pontificia Universidad Cat´olica de Chile
Escuela de Ingenier´ıa
Departamento de Ingenier´ıa Industrial y Sistemas
Simulaci´on
ICS2123 Modelos Estoc´asticos
Ver´onica Godoy
Andr´es Navarro
ICS2123
Simulaci´on
2026-1
1 / 58

Outline
1 Conceptos b´asicos
2 Estructura de un modelo de simulaci´on de eventos discretos
3 Generaci´on de instancias de una variable aleatoria
4 An´alisis de resultados
ICS2123
Simulaci´on
2026-1
2 / 58

Conceptos b´asicos
Outline
1 Conceptos b´asicos
2 Estructura de un modelo de simulaci´on de eventos discretos
3 Generaci´on de instancias de una variable aleatoria
4 An´alisis de resultados
ICS2123
Simulaci´on
2026-1
3 / 58

Conceptos b´asicos
Modelos estoc´asticos
¿C´omo podemos estudiar un modelo con aleatoriedad?
B´asicamente, de dos formas:
●Anal´ıticamente: Proceso Poisson, Cadenas de Markov, Sistemas de
espera
●Num´ericamente: Simulaci´on
ICS2123
Simulaci´on
2026-1
4 / 58

Conceptos b´asicos
¿Qu´e es una simulaci´on?
Podemos encontrar varias definiciones:
Definici´on (Thomas T. Goldsmith Jr. & Estle Ray Mann)
Simulaci´on es una t´ecnica num´erica para conducir experimentos en una
computadora digital. Estos experimentos comprenden ciertos tipos de
relaciones matem´aticas y l´ogicas, las cuales son necesarias para describir el
comportamiento y la estructura de sistemas complejos del mundo real a
trav´es de largos per´ıodos.
Definici´on (R. E. Shannon)
La simulaci´on es el proceso de dise˜nar un modelo de un sistema real y
llevar a t´ermino experiencias con ´el, con la finalidad de comprender el
comportamiento del sistema o evaluar nuevas estrategias -dentro de los
l´ımites impuestos por un cierto criterio o un conjunto de ellos- para el
funcionamiento del sistema.
ICS2123
Simulaci´on
2026-1
5 / 58

Conceptos b´asicos
¿Qu´e es una simulaci´on?
La definici´on que usaremos en el curso es:
Definici´on
T´ecnica para estudiar sistemas din´amicos por medio de la representaci´on
de su comportamiento usando un modelo matem´atico del sistema,
implementado en un computador.
Es decir, ”simular” implica crear un modelo que aproxima ciertos aspectos
de un sistema real y que puede ser usado para generar historias artificiales
del sistema. As´ı, se puede predecir el comportamiento del sistema real.
ICS2123
Simulaci´on
2026-1
6 / 58

Conceptos b´asicos
Tipos de simulaci´on
Una simulaci´on puede ser:
●Est´atica o Din´amica: Un modelo de simulaci´on est´atica, a veces
llamado simulaci´on de Monte Carlo, representa un sistema en un
momento particular en el tiempo. Un modelo de simulaci´on din´amica
representa sistemas a medida que cambian con el tiempo.
●Determin´ıstica o Estoc´astica: Una simulaci´on determinista no
contiene variables aleatorias, mientras que una simulaci´on estoc´astica
involucra una o m´as variables aleatorias como input.
●Discreta o Continua: Un sistema discreto es aquel en el que las
variables de estado cambian s´olo en un conjunto discreto de puntos
en el tiempo. En un sistema continuo las variables de estado cambian
continuamente con el tiempo (e.g. la cantidad de agua que fluye
sobre una represa).
Nos concentraremos en la simulaci´on de sistemas din´amicos estoc´asticos y
discretos.
ICS2123
Simulaci´on
2026-1
7 / 58

Conceptos b´asicos
¿Cu´ando usar simulaci´on?
Razones para usar simulaci´on:
●Experimentar con un sistema real puede ser costoso, peligroso o
puede causar desajustes importantes. Ej: sistema de transporte
●El sistema real no existe y la construcci´on de prototipos es muy
costosa. Ej: reactor nuclear
●Necesidad de estudiar el pasado, presente o futuro del sistema en
tiempo real. Ej: operaci´on de 10 a˜nos de un puerto
●El sistema es tan complejo que su evaluaci´on anal´ıtica es prohibitiva.
Ej: colas en redes de espera
ICS2123
Simulaci´on
2026-1
8 / 58

Conceptos b´asicos
Ventajas y Desventajas
Ventajas:
●Permite una complejidad arbitraria en los modelos.
●Permite estudiar modelos que no son anal´ıticamente tratables.
●Un modelo bien construido permite predecir el comportamiento de un
sistema.
Desventajas:
●Validaci´on de los modelos puede ser complicada.
●Un proyecto de simulaci´on puede tomar mucho tiempo y capacidad
computacional.
●No siempre es rentable realizar un modelo de simulaci´on.
ICS2123
Simulaci´on
2026-1
9 / 58

Estructura de un modelo de simulaci´on de eventos discretos
Outline
1 Conceptos b´asicos
2 Estructura de un modelo de simulaci´on de eventos discretos
3 Generaci´on de instancias de una variable aleatoria
4 An´alisis de resultados
ICS2123
Simulaci´on
2026-1
10 / 58

Estructura de un modelo de simulaci´on de eventos discretos
Modelo de Simulaci´on de Eventos Discretos
En este curso estudiaremos principalmente sistemas discretos, es decir,
sistemas en que los cambios de las variables de estado se producen en
instantes definidos.
Algunos ejemplos son:
●Llegada de un cliente
●T´ermino de atenci´on en la caja
●Momento en que falla un dispositivo
ICS2123
Simulaci´on
2026-1
11 / 58

Estructura de un modelo de simulaci´on de eventos discretos
Diagrama de flujo
Definici´on
El diagrama de flujo es la representaci´on gr´afica de alg´un algoritmo o
proceso. Se utiliza en disciplinas como programaci´on, econom´ıa, procesos
industriales e incluso psicolog´ıa cognitiva.
Nomenclatura b´asica:
●C´ırculo: Inicio y T´ermino
●Rect´angulo: Evento
●Rombo: Decisi´on
ICS2123
Simulaci´on
2026-1
12 / 58

Estructura de un modelo de simulaci´on de eventos discretos
Ejemplo
Procesamiento de trabajos
Considere una m´aquina que procesa trabajos. Tanto los tiempos de llegada
como los de atenci´on distribuyen exponencial de par´ametros λ y µ,
respectivamente.
1 Determine el tiempo de espera promedio en la cola de los primeros N
trabajos
2 Supongamos ahora que los tiempos de llegada siguen una distribuci´on
aleatoria F, mientras que los tiempos de atenci´on siguen una
distribuci´on aleatoria G.
Queremos obtener el tiempo de espera promedio en la cola de los primeros
N trabajos, es decir:
Wq =
N
∑
i=1
Wq(i)
N
Donde Wq(i) es el tiempo de espera en la cola del i-´esimo trabajo.
ICS2123
Simulaci´on
2026-1
13 / 58

Estructura de un modelo de simulaci´on de eventos discretos
Eventos:
●Llegada de un trabajo al sistema.
●Salida de un trabajo del sistema.
Variables de estado:
●NCOL: Cantidad de trabajos en la cola.
●STATUS: 1 si la m´aquina est´a ocupada, 0 si no.
●NCLIENTES: N´umero de trabajos que han completado su espera en
la cola.
●ESTOT: Tiempo de espera total en la cola de los trabajos que han
completado su periodo de espera.
●T: Reloj de la simulaci´on.
●TPE(1): Instante en que ocurrir´a la siguiente llegada de un trabajo.
●TPE(2): Instante en que ocurrir´a la siguiente salida de un trabajo.
●TLLEG(i): Instante de llegada del trabajo que ocupa la posici´on i en
la cola.
ICS2123
Simulaci´on
2026-1
14 / 58

Estructura de un modelo de simulaci´on de eventos discretos
ICS2123
Simulaci´on
2026-1
15 / 58

Estructura de un modelo de simulaci´on de eventos discretos
Ejemplo
Sistema G/G/1
Considere un sistema G/G/1 con atenci´on FIFO. Suponga que llegan seis
clientes y se cuenta con la informaci´on de tiempos entre llegada de cada
uno y su tiempo de servicio. Determine:
●El tiempo promedio esperado en la cola.
●El n´umero de personas esperadas en el sistema.
●La utilizaci´on del servidor
ICS2123
Simulaci´on
2026-1
16 / 58

Estructura de un modelo de simulaci´on de eventos discretos
Ejemplo
Usaremos la siguiente notaci´on:
●Ii: Tiempo entre las llegadas de los clientes i −1 e i.
●Ai =
i
∑
j=1
Ii: Instante de llegada del cliente i.
●Si: Tiempo de servicio al cliente i.
●Di = Ti + Si: Instante en que cliente i abandona el sistema.
●Ti = max{Ai,Di−1}: Instante en que empieza a atenderse el cliente i.
●Wi = Ti −Ai: Tiempo que espera en la cola el cliente i.
Notemos que las ´unicas dos expresiones que no est´an en funci´on de otras
son Ii y Si. Esto es porque ambas se deben generar como instancias de
variables aleatorias.
ICS2123
Simulaci´on
2026-1
17 / 58

Estructura de un modelo de simulaci´on de eventos discretos
Ejemplo
Utilizando la informaci´on de los tiempos entre llegada de cada cada cliente
y su tiempo de servicio, calculamos el resto de las variables aleatorias.
i
Ii
Ai
Ti
Wi
Si
Di
1
3
3
3
0
7
10
2
1
4
10
6
6
16
3
2
6
16
10
4
20
4
4
10
20
10
6
26
5
5
15
26
11
1
27
6
5
20
27
7
2
29
ICS2123
Simulaci´on
2026-1
18 / 58

Estructura de un modelo de simulaci´on de eventos discretos
Ejemplo
Tiempo de espera promedio
Tiempo de espera promedio:
6
∑
i=1
Wi
6 = 7.33
ICS2123
Simulaci´on
2026-1
19 / 58

Estructura de un modelo de simulaci´on de eventos discretos
Ejemplo
Promedio de personas en el sistema
Definamos L(t) como la cantidad de gente en el instante t. Esta variable
aleatoria solo depende de las llegadas y salidas del sistema.
t
Evento
L(t)
0
Simulaci´on empieza
0
3
Llegada de cliente 1
1
4
Llegada de cliente 2
2
6
Llegada de cliente 3
3
10
Cliente 1 se va del sistema, Llegada de cliente 4
3
15
Llegada de cliente 5
4
16
Cliente 2 se va del sistema
3
20
Cliente 3 se va del sistema, Llegada de cliente 6
3
26
Cliente 4 se va del sistema
2
27
Cliente 5 se va del sistema
1
29
Cliente 6 se va del sistema
0
ICS2123
Simulaci´on
2026-1
20 / 58

Estructura de un modelo de simulaci´on de eventos discretos
Ejemplo
Promedio de personas en el sistema
t
L(t)
1
2
3
4
3
4
6
10
15 16
20
26 27
29
Por lo tanto, la cantidad de personas en el sistema en promedio ser´ıa:
¯L = 1
29 ∫
29
0
L(t)dt = 70
29 = 2.41
O equivalentemente, podemos sumar el tiempo de estad´ıa de cada cliente
y dividirlo por el tiempo total.
¯L =
6
∑
i=1
(Di −Ai)
29
= 7 + 12 + 14 + 16 + 12 + 9
29
= 70
29
ICS2123
Simulaci´on
2026-1
21 / 58

Estructura de un modelo de simulaci´on de eventos discretos
Ejemplo
Porcentaje de utilizaci´on del servidor
t
L(t)
1
2
3
4
3
4
6
10
15 16
20
26 27
29
El servidor est´a ocupado cuando L(t) > 0. Eso ocurre en el intervalo
[3,29].
Por lo tanto, su ocupaci´on es de 26
29 = 89.66%
ICS2123
Simulaci´on
2026-1
22 / 58

Estructura de un modelo de simulaci´on de eventos discretos
Ejemplo
¿Qu´e pasar´ıa si el sistema de atenci´on fuese LIFO?
i
Ii
Ai
Ti
Wi
Si
Di
1
3
3
3
0
7
10
2
1
4
23
19
6
29
3
2
6
17
11
4
21
4
4
10
10
0
6
16
5
5
15
16
1
1
17
6
5
20
21
1
2
23
●Tiempo de espera promedio:
6
∑
i=1
Wi
6
= 5.33
●Promedio de personas en el sistema: ¯L = 58
29 = 2.0
En este caso, una atenci´on LIFO obtiene mejores resultados.
ICS2123
Simulaci´on
2026-1
23 / 58

Estructura de un modelo de simulaci´on de eventos discretos
Ejemplo computacional
Considere un puesto de venta de helados en la playa donde atiende una persona. Los
clientes llegan seg´un un Proceso de Renovaci´on donde los tiempos entre eventos
distribuyen Uniforme(4, 6) minutos, y los tiempos entre atenciones distribuyen
Exponencial con media 4 minutos. El sistema tiene una capacidad de 6 personas.
1. Desarrolle un programa computacional para simular 8 horas de operaci´on de este
puesto de helados. Luego, determine las siguientes estad´ısticas para una corrida de
la simulaci´on:
a) Cantidad total de clientes atendidos.
b) Tiempo promedio de los clientes en el sistema.
c) Tiempo en el sistema de aquel cliente que estuvo la mayor cantidad de
tiempo en el sistema.
d) Estimaci´on de la probabilidad de que el sistema se encuentre vac´ıo en
el largo plazo.
e) Estimaci´on de la proporci´on de demanda perdida.
ICS2123
Simulaci´on
2026-1
24 / 58

Estructura de un modelo de simulaci´on de eventos discretos
Ejemplo computacional
Considere un puesto de venta de helados en la playa donde atiende una persona. Los
clientes llegan seg´un un Proceso de Renovaci´on donde los tiempos entre eventos
distribuyen Uniforme(4, 6) minutos, y los tiempos entre atenciones distribuyen
Exponencial con media 4 minutos. El sistema tiene una capacidad de 6 personas.
2. Suponga ahora que los tiempos entre las llegadas de clientes distribuyen
Uniforme(1, 9) minutos. Simule 8 horas de operaci´on del sistema y vuelva a
calcular los mismos indicadores que en la parte anterior. Compare con los
resultados obtenidos anteriormente.
3. Suponga ahora que los tiempos entre las llegadas de clientes distribuyen
Uniforme(1,9) minutos, y que el sistema tiene una capacidad para 3 personas.
Simule 8 horas de operaci´on del sistema y vuelva a calcular los mismos indicadores
que en la parte anterior. Compare estos resultados con los obtenidos
anteriormente.
ICS2123
Simulaci´on
2026-1
25 / 58

Generaci´on de instancias de una variable aleatoria
Outline
1 Conceptos b´asicos
2 Estructura de un modelo de simulaci´on de eventos discretos
3 Generaci´on de instancias de una variable aleatoria
4 An´alisis de resultados
ICS2123
Simulaci´on
2026-1
26 / 58

Generaci´on de instancias de una variable aleatoria
Generaci´on de variables aleatorias
En los ejemplos anteriores se sabe c´omo calcular cada valor, ¿d´onde est´a la
aleatoriedad entonces?
Para el ejemplo 1: TPE(1)= T + F, TPE(2) = T + G
T es la ”hora actual” de la simulaci´on, pero ¿Qu´e es F? ¿Qu´e es G?
¿C´omo se calculan?
F y G son instancias de unas v.a. de distribuci´on F(x) y G(x),
respectivamente.
Para el ejemplo 2 conoc´ıamos estas instancias, no se habl´o de c´omo
calcularlas.
En este cap´ıtulo estudiaremos 3 m´etodos para generar instancias de
variables aleatorias:
●M´etodo de la transformada inversa
●M´etodo de congruencia lineal
●M´etodo de aceptaci´on y rechazo
ICS2123
Simulaci´on
2026-1
27 / 58

Generaci´on de instancias de una variable aleatoria
M´etodo de la transformada inversa
Supongamos que queremos generar instancias de una variable aleatoria
continua X con distribuci´on de probabilidades F. Entonces, sabemos que:
F(x) = P(X ≤x)
Sea U una v.a. con distribuci´on de probabilidad uniforme sobre [0,1].
Entonces:
P(U ≤u) = u,
0 ≤u ≤1
Por lo tanto, como 0 ≤F(x) ≤1, podemos plantear la siguiente igualdad:
P(U ≤F(x)) = F(x) = P(X ≤x)
(1)
ICS2123
Simulaci´on
2026-1
28 / 58

Generaci´on de instancias de una variable aleatoria
M´etodo de la transformada inversa
Como F(⋅) siempre es mon´otona y no decreciente, entonces el evento
{U ≤F(x)} es equivalente {F −1(U) ≤x}.
F(x)
U
x = F −1(F(x))
F −1(U)
ICS2123
Simulaci´on
2026-1
29 / 58

Generaci´on de instancias de una variable aleatoria
M´etodo de la transformada inversa
La equivalencia de los dos eventos implica que:
P(U ≤F(x)) = P(F −1(U) ≤x)
(2)
Observe que F −1(U) es una funci´on de una v.a. por lo que tambi´en es
una variable aleatoria. Luego, las ecuaciones (1) y (2) implican que:
P(X ≤x) = P(U ≤F(x)) = P(F −1(U) ≤x)
Y por lo tanto, las variables aleatorias X y F −1(U) tienen la misma
distribuci´on de probabilidades.
ICS2123
Simulaci´on
2026-1
30 / 58

Generaci´on de instancias de una variable aleatoria
M´etodo de la transformada inversa
Luego, podemos utilizar el siguiente algoritmo para generar instancias de
X:
M´etodo de la transformada inversa
1 Generar una instancia U1 de U, en que U ∼U(0,1)
2 Sea X1 = F −1(U1). Entonces X1 es una instancia de X.
Note que F −1(U) es una v.a. distinta de X, pero que comparten
distribuci´on de probabilidades. Por lo tanto, generar una instancia de
F −1(U) es equivalente a generar una instancia de X.
Para generar una secuencia X1,...,Xn de instancias de X, independientes
entre s´ı, debemos generar una secuencia U1,...,Un independientes entre s´ı.
ICS2123
Simulaci´on
2026-1
31 / 58

Generaci´on de instancias de una variable aleatoria
Generaci´on de n´umeros aleatorios U(0,1)
Caracter´ısticas de un buen m´etodo de generaci´on de n´umeros aleatorios:
●Los n´umeros generados aparentan distribuir U(0,1).
●Los n´umeros generados aparentan ser independientes.
●El m´etodo es r´apido y no requiere mucha memoria.
●Es reproducible.
ICS2123
Simulaci´on
2026-1
32 / 58

Generaci´on de instancias de una variable aleatoria
Generaci´on de n´umeros aleatorios U(0,1)
M´etodo congruencial lineal
Este es el m´etodo est´andar.
M´etodo congruencial lineal
1 Se elige un valor inicial X0 (semilla)
2 Xi = (aXi−1 + c) mod m
3 Ui = Xi
m
Los valores de Ui aparentan tener una distribuci´on U(0,1) y ser
independientes entre s´ı.
Dependiendo de las constantes a,c y m el m´etodo puede tener mejores o
peores propiedades.
ICS2123
Simulaci´on
2026-1
33 / 58

Generaci´on de instancias de una variable aleatoria
Ejemplo
Variable aleatoria continua
Suponga que a trav´es de un m´etodo congruencial se generaron dos
instancias de una v.a. Uniforme(0,1): 0.2 y 0.8. A partir de ellas genere
dos instancias de una v.a. con distribuci´on Exponencial de media 3.
ICS2123
Simulaci´on
2026-1
34 / 58

Generaci´on de instancias de una variable aleatoria
Ejemplo: Soluci´on
Sea F la funci´on distribuci´on. Sabemos que F(x) = 1 −e−λx. Por lo tanto,
debemos calcular F −1.
y
=
1 −e−λx
1 −y
=
e−λx
−1
λln(1 −y)
=
x
Por lo tanto, F −1(U) = −1
λln(1 −U). As´ı, ocupando las dos instancias
dadas en el enunciado, podemos obtener:
●X1 = −1
1/3ln(1 −0.2) = 0.669
●X2 = −1
1/3ln(1 −0.8) = 4.828
Nota: Si se hubiera usado F −1(U) = −1
λln(U), hubiese estado correcto
tambi´en. (¿Por qu´e?)
ICS2123
Simulaci´on
2026-1
35 / 58

Generaci´on de instancias de una variable aleatoria
Ejemplo
Variable aleatoria discreta
Suponga que a trav´es de un m´etodo congruencial se generaron dos
instancias de una v.a. Uniforme(0,1): 0.4 y 0.75. A partir de ellas genere
dos v.a. con distribuci´on Geom´etrica de par´ametro 0,3.
ICS2123
Simulaci´on
2026-1
36 / 58

Generaci´on de instancias de una variable aleatoria
Ejemplo: Soluci´on
Sabemos que la distribuci´on geom´etrica tiene probabilidad
P(X = k) = (1 −p)k−1p. La funci´on acumulada en este caso es
F(k) = 1 −(1 −p)k. Se puede deducir que:
F −1(u) = ln(1 −u)
ln(1 −p)
Sin embargo, si usamos directamente la funci´on, obtendr´ıamos X1 = 1.43,
X2 = 3.88.
¡No tiene sentido!
Esto se produce porque queremos generar instancias de una v.a. discreta.
Por lo tanto, se debe hacer lo siguiente:
ICS2123
Simulaci´on
2026-1
37 / 58

Generaci´on de instancias de una variable aleatoria
Ejemplo
Se debe hacer:
X = min{k ∶F(k) ≥U} = ⌈F −1(U)⌉
Es decir, se busca el menor k tal que la funci´on distribuci´on sea mayor o
igual al n´umero obtenido de U(0,1). En este caso, deber´ıa ser:
Xi = ⌈ln(1 −Ui)
ln(1 −p) ⌉
Por lo tanto, X1 = 2 y X2 = 4.
ICS2123
Simulaci´on
2026-1
38 / 58

Generaci´on de instancias de una variable aleatoria
M´etodo de Aceptaci´on y Rechazo
¿Qu´e pasa si la funci´on de distribuci´on no se puede invertir de forma
eficiente?
La idea detr´as del m´etodo de Aceptaci´on y Rechazo es obtener muestras a
partir de una funci´on “parecida”, de las cuales se aceptar´an solamente
algunas de ellas.
Necesitamos encontrar una funci´on h(x) ≡t(x)
c
con la cual ojal´a sea f´acil
de generar instancias.
Esta funci´on debe cumplir con:
●f(x) ≤t(x)
∀x
●∞> c =
∞
∫
−∞
t(x)dx ≥
∞
∫
−∞
f(x)dx = 1
Es decir, t(x) es mayor que f(x) para todo x, y c es el “´area bajo la
curva” de t(x).
ICS2123
Simulaci´on
2026-1
39 / 58

Generaci´on de instancias de una variable aleatoria
M´etodo de Aceptaci´on y Rechazo
Teorema (von Neumann, 1951)
Sea la funci´on g(x) = f(x)
t(x) (notar que 0 ≤g(x) ≤1). Sean U,Y dos v.a.
independientes tales que U ∼U(0,1), e Y posee funci´on densidad h(y).
La variable aleatoria definida como Y condicionada a que U ≤g(Y )
distribuye seg´un la funci´on de densidad f(y).
Esto nos permite encontrar una expresi´on que posee la misma distribuci´on
que buscamos. Luego, de este teorema se deriva el algoritmo de
Aceptaci´on-Rechazo
M´etodo de Aceptaci´on y Rechazo
1 Generar una instancia de U ∼U(0,1).
2 Generar una instancia de Y ∼h(y) (independiente de U).
3 Si U ≤g(Y ), entonces hacer X = Y . Si no, volver al paso 1.
ICS2123
Simulaci´on
2026-1
40 / 58

Generaci´on de instancias de una variable aleatoria
M´etodo de Aceptaci´on y Rechazo
Hay dos factores a considerar al ocupar este m´etodo:
●Se debe poder generar f´acilmente instancias a partir de h(y). Si no,
no ofrece ventaja con respecto al m´etodo anterior.
●El tama˜no de c est´a directamente relacionado con qu´e tan cercana es
la funci´on t(x) a la funci´on f(x). Por lo tanto, se desea que c sea
peque˜no, debido a que:
P(U ≤g(Y )) = 1
c
Entonces, el n´umero de iteraciones hasta obtener una instancia
distribuye Geom´etrica(1
c), por lo que el n´umero esperado de
iteraciones es c.
ICS2123
Simulaci´on
2026-1
41 / 58

Generaci´on de instancias de una variable aleatoria
M´etodo de Aceptaci´on y Rechazo
Ejemplo
Considere una variable aleatoria continua X con la siguiente funci´on de densidad:
f(x) = b (3 −x2) (1 −x2) para x ∈[−1, 1].
(a) Encuentre el valor de b para que f(x) efectivamente sea una funci´on de densidad.
Si lo necesita, utilice un m´etodo num´erico para ´este prop´osito.
(b) Desarrolle un algoritmo de Aceptaci´on y Rechazo para generar instancias de X.
(c) Si se usa su algoritmo, ¿cu´al es el valor esperado de la cantidad de rechazos
necesarios para generar una instancia?
(d) Utilice su algoritmo con los siguientes n´umeros aleatorios Uniforme(0,1): 0.672,
0.236, 0.464, 0.711, 0.283, 0.111.
(e) Utilice alg´un m´etodo computacional para generar 1000 instancias de una v.a.
Uniforme(0,1) y genere instancias de X a partir de estos n´umeros, utilizando el
m´etodo desarrollado. ¿Cu´antas instancias se generaron para X? Presente un
histograma de las instancias generadas para X. Compare este histograma con un
gr´afico de la funci´on de densidad de probabilidades de X.
ICS2123
Simulaci´on
2026-1
42 / 58

Generaci´on de instancias de una variable aleatoria
M´etodo de Aceptaci´on y Rechazo
Demostraci´on del Teorema
Sea A el evento de aceptar el valor de Y como instancia de X, i.e.
U ≤g(Y )
La funci´on de distribuci´on de X es:
Fx (X) = P(X ≤x) = P(Y ≤x∣A) = P(A,Y ≤x)
P(A)
Luego:
P(A,Y ≤x) = ∫
∞
−∞P(A,Y ≤x∣Y = y)h(y)dy
= 1
c ∫
x
−∞P(A∣Y = y)t(y)dy
ICS2123
Simulaci´on
2026-1
43 / 58

Generaci´on de instancias de una variable aleatoria
M´etodo de Aceptaci´on y Rechazo
Tenemos:
P(A∣Y = y) = P(U ≤g(Y )∣Y = y)
= P(U ≤g(y))
= g(y)
(U ∼Uniforme(0,1))
Entonces:
P(A,Y ≤x) = 1
c ∫
x
−∞P(A∣Y = y)t(y)dy
= 1
c ∫
x
−∞g(y)t(y)dy
= 1
c ∫
x
−∞f(y)dy
ICS2123
Simulaci´on
2026-1
44 / 58

Generaci´on de instancias de una variable aleatoria
M´etodo de Aceptaci´on y Rechazo
Tambi´en necesitamos:
P(A) = P(U ≤g(y)) = 1
c
As´ı:
Fx (X) = P(A,Y ≤x)
P(A)
=
1
c ∫
x
−∞f(y)dy
1
c
= ∫
x
−∞f(y)dy
Luego, la funci´on de densidad de probabilidades de X es f(x)
ICS2123
Simulaci´on
2026-1
45 / 58

Generaci´on de instancias de una variable aleatoria
M´etodo de Aceptaci´on y Rechazo
¿Podemos utilizar Aceptaci´on y Rechazo para generar instancias de
una distribuci´on normal?
Si queremos generar una instancia de X ∼N(µ,σ2), podemos hacer
X = σZ + µ, donde Z denota una v.a. con una distribuci´on N(0,1).
Por lo tanto, es suficiente encontrar un algoritmo para generar
Z ∼N(0,1).
Adem´as, si podemos generar una instancia para el valor absoluto ∣Z∣, luego
por simetr´ıa podemos obtener una instancia para Z generando de forma
independiente una v.a. S (para el signo) que es 1 con probabilidad 1/2 y
−1 con probabilidad 1/2, para luego generar Z = S ∣Z∣.
ICS2123
Simulaci´on
2026-1
46 / 58

Generaci´on de instancias de una variable aleatoria
M´etodo de Aceptaci´on y Rechazo
Lo interesante es que ∣Z∣tiene la siguiente funci´on de densidad:
f(x) =
2
√
2π
e
−x2
2 ,
x ≥0
Ahora, observamos que t(x) =
√
2e/π e−x ≥f(x)
∀x ≥0
Con esto, tomamos h(x) = e−x,x ≥0, la densidad exponencial con tasa 1,
algo que podemos simular f´acilmente con el m´etodo de transformada
inversa.
Y tenemos c =
√
2e/π ≈1.32 y g(y) = f(y)/t(y) = e−(y−1)2/2.
ICS2123
Simulaci´on
2026-1
47 / 58

Generaci´on de instancias de una variable aleatoria
M´etodo de Aceptaci´on y Rechazo
Distribuci´on Normal(0, 1)
1 Generar U
2 Generar Y con una distribuci´on exponencial a la tasa 1; es decir,
generar U′ y establecer Y = −ln(1 −U ′).
3 Si U ≤e−(Y −1)2/2, hacer ∣Z∣= Y , en otro caso volver a 1.
4 Generar U′′. Sea Z = ∣Z∣si U′′ ≤0.5, hacer Z = −∣Z∣si U′′ > 0.5
ICS2123
Simulaci´on
2026-1
48 / 58

An´alisis de resultados
Outline
1 Conceptos b´asicos
2 Estructura de un modelo de simulaci´on de eventos discretos
3 Generaci´on de instancias de una variable aleatoria
4 An´alisis de resultados
ICS2123
Simulaci´on
2026-1
49 / 58

An´alisis de resultados
Tipos de simulaci´on
Para analizar los resultados, existen dos tipos de simulaci´on:
●Simulaci´on en Estado de R´egimen (Largo plazo)
Interesa evaluar el desempe˜no del sistema despu´es que ha pasado
mucho tiempo, de modo que las condiciones iniciales del sistema
dejan de tener efecto. Ejemplos:
●Operaci´on de una f´abrica durante un a˜no
●Operaci´on de un puerto durante un a˜no
●Tiempo promedio de espera de trabajos en cola considerando 10.000
trabajos
●Simulaci´on terminal (Corto plazo)
Se simula un sistema hasta que ocurre un cierto evento terminal,
habitualmente en el corto plazo. Ejemplos:
●Operaci´on de un banco entre 12:00 y 14:00
●Simulaci´on de la m´aquina hasta que se han atendido 100 productos
●Operaci´on de estaci´on de metro Baquedano durante hora punta
ICS2123
Simulaci´on
2026-1
50 / 58

An´alisis de resultados
An´alisis de resultados
R´eplicas independientes
Considere un modelo de simulaci´on en que se desea estimar el valor
esperado de X. El m´etodo consiste en hacer N corridas independientes
(diferentes semillas) del modelo para obtener una muestra de X a partir
de cada corrida, es decir, {X1,X2,...,Xn}. El estimador ser´a:
¯X =
N
∑
i=1
Xi
N
Adem´as, se puede sacar la varianza del estimador y construir un intervalo
de confianza sobre el valor esperado de X.
Este es uno de los m´etodos m´as comunes para el an´alisis de output.
ICS2123
Simulaci´on
2026-1
51 / 58

An´alisis de resultados
Intervalos de Confianza para un par´ametro
Supongamos que tenemos una muestra de v.a. i.i.d
X1,X2,...,Xn ∼N(µ,σ2), con σ2 conocido y µ desconocido.
Un estimador de µ es:
¯X(n) =
n
∑
i=1
Xi
n
Queremos construir un intervalo de confianza a nivel 1 −α para µ
(P(µ ∈intervalo) = 1 −α). Pero sabemos que:
¯X(n) −µ
σ/√n
∼N(0,1)
Luego,
1 −α = P(µ ∈intervalo) = P(−z1−α/2 ≤
¯X(n) −µ
σ/√n
≤z1−α/2)
→¯X(n) −z1−α/2
σ
√n ≤µ ≤¯X(n) + z1−α/2
σ
√n
ICS2123
Simulaci´on
2026-1
52 / 58

An´alisis de resultados
Intervalos de Confianza para una Simulaci´on Terminal
Se tiene lo siguiente:
●n r´eplicas independientes del modelo
●Largo de cada corrida queda determinado para un evento terminal E.
●Condiciones iniciales son las mismas para todas las corridas.
Sea Xj el valor del estimador de la medida de desempe˜no en la corrida
n´umero j. X1,...,Xn son v.a. i.i.d., pero no conocemos su distribuci´on.
Queremos construir un intervalo de confianza para µ = E(X).
Estudiaremos dos m´etodos para construir un intervalo de confianza.
ICS2123
Simulaci´on
2026-1
53 / 58

An´alisis de resultados
Intervalos de Confianza para una Simulaci´on Terminal
M´etodo 1:
Si X1,...,Xn son v.a. i.i.d., entonces cuando n →∞se tiene que:
¯X(n) −µ
√
S2(n)/n
∼N(0,1) por el Teorema Central del L´ımite
S2(n) es el estimador de Var(x):
S2(n) =
1
n −1
n
∑
j=1
(Xj −¯X(n))2
La desventaja de este m´etodo es que el intervalo solamente ser´a v´alido
para n grande.
ICS2123
Simulaci´on
2026-1
54 / 58

An´alisis de resultados
Intervalos de Confianza para una Simulaci´on Terminal
M´etodo 2:
Si se asume que X1,...,Xn ∼N(µ,σ2) entonces se puede demostrar que:
T(n) =
¯X(n) −µ
√
S2(n)/n
∼t(n−1)
tiene distribuci´on de t student con n −1 grados de libertad.
As´ı, el intervalo de confianza a nivel 1 −α para E[X] ser´ıa:
¯X(n) ± tn−1,1−α/2
√
S2(n)/n
ICS2123
Simulaci´on
2026-1
55 / 58

An´alisis de resultados
Ejemplo
Intervalos de confianza
Suponga que la sucursal de un banco con 5 cajeros y una sola cola de
clientes, atiende de 9 am a 5 pm, pero permanece abierta hasta que todos
los clientes que han llegado hasta las 5 pm han sido atendidos. La llegada
de clientes es distribuye Poisson a tasa de 1 por minuto y los tiempos de
servicio son exponenciales con media 4 minutos. La atenci´on es FIFO.
Queremos construir un intervalo de confianza al 90% para la demora
promedio en la cola.
ICS2123
Simulaci´on
2026-1
56 / 58

An´alisis de resultados
La siguiente tabla muestra los resultados de 10 r´eplicas:
R´eplica
No atendidos
Demora promedio en cola (Di)
Largo promedio cola
1
484
1.53
1.52
2
475
1.66
1.62
3
484
1.24
1.23
4
483
2.34
2.34
5
455
2.00
1.89
6
461
1.69
1.56
7
451
2.69
2.50
8
486
2.86
2.83
9
502
1.70
1.74
10
475
2.60
2.50
ICS2123
Simulaci´on
2026-1
57 / 58

An´alisis de resultados
Nos piden construir un intervalo de confianza al 90% para la demora
promedio en la cola.
De los datos tenemos que:
¯X(10) = 2.03
S2(10) = 0.31
⇒E(X) = ¯X(10) ± t9,0.95
√
S2(10)/10 = 2.03 ± 0.32
ICS2123
Simulaci´on
2026-1
58 / 58

