ICS2123  Modelos Estocásticos
Sesión de ejercicios de repaso
Poisson  CMTD  CMTC  Sistemas de espera  Simulación
ICS2123
|
Profesores Andrés Navarro y Verónica Godoy
|
Primer Semestre 2026
Versión de enunciados + control

Enunciados + control
Agenda
1. Proceso de Poisson
2. Cadenas de Markov en Tiempo Discreto (CMTD)
3. Cadenas de Markov en Tiempo Continuo (CMTC)
4. Sistemas de espera
5. Simulación (Aceptación y Rechazo)
2

Enunciados + control
1. Proceso de Poisson
Una central de monitoreo recibe alertas de falla de una ota de plantas fotovoltaicas
según un proceso de Poisson con tasa λ = 4 [alertas/hora]. La central opera de 08:00 a
20:00. Sea N(t0, t1) el número de alertas recibidas entre t0 y t1.
(a) ¾Cuál es la probabilidad de recibir exactamente 3 alertas entre las 09:00 y las
09:45?
(b) Un turno comienza a las 14:00 sin alertas pendientes. ¾Cuál es la probabilidad de
que la primera alerta del turno ocurra después de las 14:30?
(c) Si se sabe que N(8:00, 15:00) = 2, ¾cuál es la probabilidad de que la primera
alerta del día haya ocurrido después de las 10:00?
(d) El servicio cobra c por alerta, con una facturación mínima diaria equivalente a 40
alertas. Calcule el valor esperado del pago de un día.
3

Enunciados + control
2. CMTD  Parte (a)
Una planta fotovoltaica se revisa al nal de cada día y queda en una de tres
condiciones: Normal (N), Alerta (A) o Detenida (D). La condición del día siguiente
depende solo de la actual, según:
▶Desde N: permanece en N con probabilidad 0.6 y pasa a A con 0.4.
▶Desde A: vuelve a N con 0.3, permanece en A con 0.5 y pasa a D con 0.2.
▶D es una condición de la que la planta no se recupera por sí sola (absorbente).
Modele el proceso como una CMTD (dena los estados) y plantee y resuelva el sistema
para el número esperado de días hasta la primera detención, partiendo de Normal,
E[T(N, D)].
4

Enunciados + control
2. CMTD  Cadena de 6 estados
Considere una CMTD con estados {1, 2, 3, 4, 5, 6} y matriz de transición:
P =









1
2
3
4
5
6
1
0
1
0
0
0
0
2
0
0
1
0
0
0
3
1
0
0
0
0
0
4
0.3
0
0
0.2
0.5
0
5
0
0
0
0
0.4
0.6
6
0
0
0
0
0.7
0.3









(b) Determine las clases y clasique cada estado (transiente / recurrente positivo /
recurrente nulo), indicando si es periódico o aperiódico y el período.
(c) Calcule F(4, 1) y F(4, 5). Interprete.
(d) Calcule el número esperado de pasos hasta alcanzar una clase recurrente partiendo
de 4, es decir E[T(4, R)] con R = {1, 2, 3, 5, 6}.
5

Enunciados + control
3. CMTC
Un inversor fotovoltaico puede estar en tres condiciones: Operativo (0), Degradado
(1) o en Falla (2). Desde Operativo se degrada a tasa a; desde Degradado se repara y
vuelve a Operativo a tasa b o cae en Falla a tasa c; desde Falla se repara y vuelve a
Operativo a tasa d. Use a = 1, b = 2, c = 1, d = 3 [por día].
(a) Modele como CMTC: dena los estados y dibuje el diagrama de tasas.
(b) Escriba las ecuaciones de equilibrio para cada estado y obtenga la distribución
estacionaria.
(c) En el largo plazo, ¾qué fracción del tiempo el inversor está en Falla? ¾Cuál es la
tasa promedio de entradas a Falla (por día)?
6

Enunciados + control
4. Sistemas de espera
Una sucursal de atención cuenta con 2 ejecutivos idénticos. Los clientes llegan según un
proceso de Poisson con tasa λ = 2 [clientes/hora] y cada ejecutivo atiende a tasa µ = 2
[clientes/hora]. Tras ser atendidos, una fracción p = 0.5 pasa a una segunda etapa con
un único cajero, que atiende a tasa µ2 = 2 [clientes/hora].
(a) Identique el tipo de sistema de la primera etapa y su condición de estabilidad.
(b) Calcule P0 y la probabilidad de que un cliente encuentre el sistema con a lo más 1
cliente (en atención y en la).
(c) Calcule L, Lq, W y Wq de la primera etapa.
(d) Para la segunda etapa: identique el tipo de sistema, su tasa efectiva de llegada y
su condición de estabilidad.
7

Enunciados + control
4. Sistemas de espera  Formulario
Sistema
P0
Pn
M/M/1
1 −ρ
 λ
µ
n
P0
M/M/1/K
1 −ρ
1 −ρK+1
 λ
µ
n
P0
M/M/c
" c
X
n=0
λn
µnn! +
λc
µcc!
ρ
1 −ρ
#−1





(λ/µ)n
n!
P0,
0 ≤n ≤c
(λ/µ)n
c! c n−c P0,
n ≥c + 1
Sistema
L
Lq
M/M/1
λ
µ −λ
λ2
µ(µ −λ)
M/M/c
λ
µ +
(λ/µ)c ρ
c! (1 −ρ)2 P0
P0
λc
c! µc
ρ
(1 −ρ)2
Con ρ =
λ
c µ y condición de estabilidad ρ < 1 para M/M/1 y M/M/c.
8

Enunciados + control
5. Simulación  Aceptación y Rechazo
Sea X ∈[0, 1] con densidad f (x) = 6x(1 −x), 0 ≤x ≤1. Para simularla se usa la cota
superior triangular t(x), con vértice en x = 1
2 y altura 3:
t(x) =
(
6x
0 ≤x ≤1
2,
6(1 −x)
1
2 < x ≤1.
0
0.5
1
0
1.5
3
x
t(x) (cota superior)
f (x) = 6x(1 −x)
9

Enunciados + control
5. Simulación  Preguntas
(a) Explicite la función de aceptación g(x), la constante de normalización c de t(x) y
la función h(x).
(b) A partir de h(x), determine la función de distribución acumulada H(x) y su inversa
H−1(U).
(c) Complete la tabla de simulación. Use U1 para generar el candidato Y = H−1(U1)
y U2 para la decisión de aceptación. Indique los valores aceptados.
n
U1
U2
1
0.08
0.30
2
0.32
0.90
3
0.50
0.40
4
0.98
0.95
10

Enunciados + control
Control 7
Instrucciones
Individual o en parejas, solo entre quienes asistieron a la clase de hoy. Entrega máximo hoy jueves 25
de junio, a las 23:59.
Los clientes llegan a una estación según un proceso de Poisson de tasa λ y son atendidos por un único
servidor en orden inverso de llegada (LIFO): al desocuparse, el servidor toma al cliente en espera que
llegó más recientemente. El tiempo de atención es exponencial de media 1/µ. Complete la siguiente
tabla de eventos para los primeros 12 clientes:
Cliente
1
2
3
4
5
6
7
8
9
10
11
12
Hora de llegada [min]
0
1
3
5
7
9
20
21
23
26
29
32
Tiempo de atención [min]
4
2
2
2
2
2
5
3
3
3
3
3
Inicio de atención [min]
Término de atención [min]
En cola [min]
11

Enunciados + control
Control 7
Responda las siguientes preguntas:
(a) Complete la tabla bajo LIFO y estime dos parámetros: el tiempo promedio en cola ˆ
Wq y la
utilización del servidor ˆρ (mida desde el primer arribo hasta que el último cliente sale).
(b) Repita el cálculo de la tabla y de ambos parámetros ahora con disciplina FIFO. Analice ˆ
Wq y ˆρ y
explique qué ocurrió con cada uno respecto a LIFO.
(c) En el largo plazo (no en la simulación anterior): si el tiempo de atención dejara de ser exponencial
y pasara a una Uniforme con la misma media 1/µ, ¾cambia la utilización del servidor? ¾Y el
tiempo promedio de espera? Justique (observe que el sistema pasa a ser un M/G/1).
12

