ICS2123  Modelos Estocásticos
ICS2123
|
Profesores Andrés Navarro y Verónica Godoy
|
Primer Semestre 2026
Solución del control

Solución del control
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
2

Solución del control
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
3

Solución del control
Control 7  Solución (a): LIFO
Orden de atención bajo LIFO (se toma siempre al más reciente en espera): C1, C3, C4, C5, C6, C2
(ocio 1420), C7, C9, C10, C11, C12, C8.
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
0
12
4
6
8
10
20
37
25
28
31
34
Término de atención [min]
4
14
6
8
10
12
25
40
28
31
34
37
En cola [min]
0
11
1
1
1
1
0
16
2
2
2
2
ˆ
Wq = 0 + 11 + 1 + 1 + 1 + 1 + 0 + 16 + 2 + 2 + 2 + 2
12
= 39
12 = 3.25 min.
Servidor ocupado 34 min
en [0, 40]:
ˆρ = 34
40 = 0.85.
4

Solución del control
Control 7  Solución (b): FIFO
Orden de atención bajo FIFO (orden de llegada): C1, C2, C3, C4, C5, C6 (ocio 1420), C7, C8, C9,
C10, C11, C12.
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
0
4
6
8
10
12
20
25
28
31
34
37
Término de atención [min]
4
6
8
10
12
14
25
28
31
34
37
40
En cola [min]
0
3
3
3
3
3
0
4
5
5
5
5
ˆ
Wq = 39
12 = 3.25 min;
ˆρ = 34
40 = 0.85.
Análisis. Los dos parámetros son iguales bajo LIFO y FIFO: ˆ
Wq = 3.25 min y ˆρ = 0.85 no cambian.
Lo que cambia es la variabilidad de las esperas. Bajo LIFO muchos esperan poco (1 o 2 min) pero
unos pocos esperan mucho (C2 espera 11, C8 espera 16): las esperas son muy dispares. Bajo FIFO las
esperas son parejas (3 en la primera ráfaga; 45 en la segunda): casi todos esperan algo parecido.
5

Solución del control
Control 7  Solución (c)
Utilización del servidor: no cambia. La utilización depende solo de la media del tiempo de servicio,
que se mantiene al pasar de Exponencial a Uniforme con la misma media.
Tiempo promedio de espera: disminuye. Al cambiar la distribución del servicio (conservando su
media), el sistema deja de ser M/M/1 y pasa a ser un M/G/1. En un M/G/1 la espera promedio no
depende solo de la media del servicio, sino también de su variabilidad: mientras más variables sean los
tiempos de atención, más larga es la cola. Como la Uniforme es menos variable que la Exponencial de
igual media, el tiempo promedio de espera se reduce.
6

