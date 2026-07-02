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
(b) Muestre que esta cadena de Markov cumple que
P

l´ım
n→∞Xn = ∞|X0 = 0

= 1.
(c) Si se tiene que:
pi,i+1 =
i + 1
i
α
pi,i−1,
α > 0
¿C´omo cambiar´ıa su respuesta a la pregunta anterior?
2

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
(b) Determine si la cadena de Markov admite una distribuci´on estacionaria. En caso afirmativo, escriba
el sistema de ecuaciones que permite calcular dicha distribuci´on.
(c) Considerando el largo plazo (asuma conocidas las probabilidades estacionarias), calcule la proporci´on
del tiempo en que ambas potrancas est´an corriendo cuando el potro est´a lesionado.
(d) Calcule la probabilidad, en el largo plazo (asuma conocidas las probabilidades estacionarias), de que
al menos haya un caballo (potro o potranca) lesionado.
(e) Si un nuevo estudio indica que en promedio un potro corriendo reporta utilidades semanales por
1[u.g.h] (unidades de ganancias h´ıpicas) y una potranca 3[u.g.h] y asumiendo que un caballo -potro
o potranca- corre much´ısimas semanas antes de irse al campo, ¿a cu´anto ascender´an las ganancias de
este afamado profesor?
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
3

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
(b) Justifique la existencia de una distribuci´on de probabilidades estacionarias y construya el sistema de
ecuaciones que permite calcularlas.
(c) Indique la proporci´on del tiempo en que ambos detectives se encuentran desocupados.
(d) Indique la cantidad promedio de casos que se encuentran resolviendo en un instante cualquiera de
tiempo.
(e) Si los detectives se encuentran actualmente resolviendo un crimen, indique el tiempo promedio que
le tomar´a volver a resolver un caso de crimen.
4

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
(b) Considere el vector w = (w0, . . . , w2n) definido por
wi =
 2n
i

22n ,
i = 0, . . . , 2n.
1. Verifique que w define una distribuci´on de probabilidad.
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
(c) Demuestre que para todo i = 1, . . . , 2n −1
wi = wi−1
2n −(i −1)
2n
+ wi+1
i + 1
2n .
Explique brevemente qu´e sugiere este resultado sobre la distribuci´on de las part´ıculas entre las urnas
cuando el sistema ha evolucionado durante un per´ıodo considerable de tiempo.
(d) Realice una simulaci´on del proceso descrito anteriormente utilizando Python. Considere 2n = 40.
⋄Comience con todas las part´ıculas en la urna 1, es decir
X0 = 40.
⋄Simule el sistema durante T = 100000 pasos.
Luego, grafique la evoluci´on temporal de Xt. Compare este histograma con la distribuci´on te´orica.
¿Qu´e sugieren sus resultados acerca del comportamiento del sistema en el largo plazo?. Comente.
5

