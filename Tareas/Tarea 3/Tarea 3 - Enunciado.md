Pontificia Universidad Cat´olica de Chile
Escuela de Ingenier´ıa
Departamento de Ingenier´ıa Industrial y de Sistemas
ICS2123 – Modelos Estoc´asticos
Profesores Ver´onica Godoy y Andr´es Navarro
Ayudante Jefe Joaqu´ın Vergara
Primer Semestre 2026
Tarea 3:
Sistemas de Espera y Simulaci´on
Instrucciones
⋄Esta tarea debe ser realizada individualmente o en parejas (pueden ser de diferentes secciones
dentro de las que son coordinadas). Deben indicar en la primera plana del PDF los nombres de los/as
integrantes, junto con las secciones respectivas de c/u.
⋄Tienen plazo hasta el viernes 26 de junio a las 23:59 hrs para entregar sus soluciones.
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

Problema 1 (15 puntos)
T´u y unos amigos, felices del fin de semestre, planean realizar un paseo e invitar a todos los alumnos
de la Escuela. Para esto, deciden organizar ‘La Fuga’: una fiesta al aire libre en una parcela lejos de la
universidad. Dada la lejan´ıa del paseo, deciden contratar buses para otorgar a los mareados compa˜neros
(de tanto bailar) un seguro regreso a casa.
La empresa de buses que contratan tiene ciertas condiciones: como empresa no pueden asegurar llegadas
determin´ısticas por lo que le comentan a usted que la llegada de los buses es un Proceso de Poisson de tasa
β [buses/hora]. Adem´as, los choferes, cansados de ver alumnos felices por salir de vacaciones, no aguantan
hasta que se llene el bus, por lo que se van en un tiempo exponencial de media 1
γ horas (desde que abren
la puerta del bus), pero si se llena el bus antes, parten inmediatamente.
Por otra parte, como ya ha ido a suficientes paseos universitarios, sabe que los asistentes del paseo salen
de la fiesta al paradero despu´es de un tiempo exponencial con media 1
λ horas, independiente de los dem´as
(asuma que no pasa tiempo entre la fiesta y el paradero de micros) para sumarse a la cola que espera para
subirse a un bus.
Una vez que llega un bus, este se coloca en la fila y comienza a recibir pasajeros, los cuales, al llegar su
turno, se demoran en subir al bus con un tiempo exponencial de media 1
α horas.
Adem´as, la empresa indica que, cuando existe una fila de buses esperando atenci´on, ´unicamente el bus
ubicado frente al paradero puede abrir sus puertas para el ascenso y descenso de pasajeros. Los dem´as
buses deben permanecer cerrados hasta avanzar a dicha posici´on. Suponga que frente al paradero existe
espacio para exactamente un bus.
La empresa de buses asegura que pasar´an buses hasta que hayan salido todos los asistentes.
Ustedes ya saben de antemano que la cantidad de asistentes a la fiesta es N, la capacidad de los buses es
de K pasajeros. Asuma cola FIFO.
(a) (7.5 puntos) Simule esta situaci´on para β = 11, γ = 4, λ = 12, α = 120, N = 2000, K = 30.
Desarrolle un programa en Python que permita simular la situaci´on descrita y determine los siguientes
estad´ısticos para una corrida del programa:
(i) Tiempo total hasta que se vac´ıa la fiesta (se van todos del lugar).
(ii) Largo promedio de la cola de personas.
(iii) Largo promedio de la cola de buses.
(iv) Tiempo promedio de espera desde que una persona sale de la fiesta, hasta que parte el bus.
(v) Tiempo de espera promedio de espera en la cola.
(vi) Cantidad promedio de personas que se suben a un bus.
Comente sus resultados.
(b) (7.5 puntos) Ahora considere que los buses abren sus puertas apenas llegan a la fiesta, sin importar
si est´an justo frente al paradero, y que los asistentes a la fiesta se suben a cualquiera de los buses con
igual probabilidad. Vuelva a calcular todo lo anterior y compare.
Hint: Se recomienda utilizar y completar el c´odigo base disponible en Canvas (M´odulo Tarea 3: Sistemas
de Espera y Simulaci´on) para el desarrollo de esta pregunta.
2

Problema 2 (15 puntos)
Una sucursal bancaria opera durante el horario h´abil atendiendo a clientes que llegan a realizar tr´amites
como dep´ositos, retiros y transferencias. La sucursal cuenta con C cajeros que operan en paralelo, con
una ´unica cola de capacidad infinita y pol´ıtica FIFO. El tiempo de atenci´on de cada cajero (en minutos)
distribuye Exponencial con par´ametro µ, de forma independiente entre cajeros y clientes.
Los clientes llegan de acuerdo a un Proceso de Poisson con tasa λ clientes por minuto. No obstante, el
comportamiento de los clientes depende del estado del sistema al momento de su llegada:
⋄Si hay menos de K clientes en cola, el cliente ingresa al sistema con certeza.
⋄Si hay i ≥K clientes en cola, el cliente decide ingresar con probabilidad pi, donde 0 < pi < 1 y
pi > pi+1 para todo i ≥K, es decir, a mayor cola, menor disposici´on a esperar.
Adicionalmente, los clientes que llevan mucho tiempo esperando en cola pueden perder la paciencia y
abandonar el banco sin ser atendidos. Espec´ıficamente, cuando hay M o m´as clientes en cola (con M > K),
los ´ultimos R clientes de la cola se vuelven impacientes, y el tiempo que cada uno de ellos est´a dispuesto a
seguir esperando distribuye Exponencial con par´ametro δ, de forma independiente entre s´ı y del resto del
sistema.
Se desea modelar este sistema como una CMTC {X(t), t ≥0}, donde X(t) denota el n´umero total de
clientes en el sistema (cajeros m´as cola) en el instante t.
(a) (5 puntos) Defina el espacio de estados de la cadena e identifique claramente los distintos reg´ımenes
del sistema. Encuentre todas las tasas de transici´on instant´aneas qij y repres´entelas en un diagrama
de tasas, indicando expl´ıcitamente cada caso.
(b) (7 puntos) Escriba las ecuaciones de balance detallado (o global, seg´un corresponda) para cada
r´egimen del sistema. ¿Bajo qu´e condici´on sobre los par´ametros λ, µ, C, δ y R existe una distribuci´on
estacionaria?
(c) (3 puntos) Asumiendo que el sistema es estable y que se conocen todas las probabilidades estacio-
narias πn (n ≥0), calcule las siguientes medidas de desempe˜no en el largo plazo:
(i) (1 punto) Tasa efectiva de llegada
(ii) (1 punto) Tasa efectiva de deserci´on
(iii) (1 punto) N´umero medio de clientes en cola y tiempo medio de espera en cola
3

Problema 3 (15 puntos)
En una planta manufacturera, los productos que requieren control de calidad ingresan al sistema seg´un un
proceso de Poisson de tasa λ. El proceso de revisi´on est´a compuesto por cuatro unidades de atenci´on espe-
cializadas, cada una con una capacidad limitada de servidores id´enticos y tiempos de servicio exponenciales.
La Unidad i dispone de ci servidores y cada servidor atiende a tasa µi, para i = 1, . . . , 4.
Todo producto que ingresa por la entrada principal es sometido inicialmente a una inspecci´on. Como
resultado de ella, los productos son clasificados en tres categor´ıas mutuamente excluyentes: una fracci´on
pA es considerada conforme y abandona inmediatamente el sistema; una fracci´on pB requiere una revisi´on
de fallas menores; y una fracci´on pC requiere una revisi´on de fallas graves, donde pA + pB + pC = 1.
Los productos clasificados con fallas menores son derivados a una unidad especializada y, una vez completada
dicha revisi´on, pasan a una revisi´on final antes de abandonar el sistema.
Los productos clasificados con fallas graves son enviados a una unidad de ingenier´ıa. Tras dicha evaluaci´on,
una proporci´on p3 requiere adem´as una revisi´on de fallas menores antes de continuar, mientras que el resto
puede avanzar directamente a la revisi´on final. Todos ellos abandonan el sistema una vez concluida esta
´ultima etapa.
Adicionalmente, existe una corriente independiente de productos provenientes de reprocesos externos que
ingresa directamente a la unidad de ingenier´ıa seg´un un proceso de Poisson de tasa γ. Estos productos no
son sometidos a revisi´on final y abandonan el sistema inmediatamente despu´es de ser atendidos en dicha
unidad.
Suponga que todas las estaciones operan de manera independiente y pueden modelarse como colas M/M/c.
(a) (4 puntos) Modele el proceso como una red abierta M/M/c, construya el grafo de flujo, deduzca
cada tasa efectiva λi por balance de flujo, identifique los cuatro tipos (A, B, C, D) con su recorrido
y su fracci´on del total, y escriba las condiciones de estabilidad indicando cu´al unidad restringe m´as a
λ.
(b) (3 puntos) Suponiendo conocidos los tiempos promedio de permanencia en cada etapa del sistema,
obtenga el tiempo promedio total de permanencia para cada categor´ıa de producto (A, B, C y D). A
partir de ello, determine el tiempo promedio de permanencia de un producto arbitrario y analice la
relaci´on entre ambas cantidades.
(c) (4 puntos) Para la Unidad 3, eval´ue agregar (c3 + 1) versus eliminar (c3 −1) un servidor sobre ρ3,
L3, W3, WC, WD y W. D´e la condici´on exacta de inestabilidad al eliminar un servidor.
(d) (4 puntos) Compare reducir el tiempo de servicio de la Unidad 2 (µ2 →µ′
2) con agregar un servidor
en ella, indicando en qu´e r´egimen conviene cada medida.
4

Problema 4 (15 puntos)
Responda las siguientes preguntas de manera independiente:
1. (5 puntos) La distribuci´on Weibull es una distribuci´on de probabilidad continua que se utiliza
generalmente para modelar el tiempo hasta el fallo de un componente. La funci´on de densidad de una
v.a. X ∼W(λ, k) es:
f(x) = k
λ
x
λ
k−1
e−(x/λ)k
Describa un algoritmo basado en el M´etodo de la Transformada Inversa para obtener instancias de X
a partir de instancias de una variable aleatoria Uniforme(0, 1). Sea expl´ıcito al calcular la funci´on de
probabilidades acumuladas de X, su inversa y el procedimiento a seguir para generar las instancias.
Por ´ultimo, utilice el procedimiento desarrollado para generar instancias de X a partir de las siguientes
instancias de una variable aleatoria Uniforme(0, 1): 0.19, 0.37, 0.91 (Considere λ = 10 y k = 2).
2. (10 puntos) Considere una variable aleatoria continua X con la siguiente funci´on de densidad:
f(x) = b

sin(πx) + π
2

para x ∈[0, π]
(a) (2 puntos) Encuentre el valor de b para que f(x) efectivamente sea una funci´on de densidad.
(b) (2 puntos) Desarrolle un algoritmo de Aceptaci´on y Rechazo para generar instancias de X.
Apoye su desarrollo con gr´aficos de las funciones relevantes.
(c) (2 puntos) Si se usa su algoritmo, ¿cu´al es el valor esperado de la cantidad de rechazos necesarios
para generar una instancia?
(d) (2 puntos) Utilice su algoritmo con los siguientes n´umeros aleatorios Uniforme(0,1): 0.672,
0.236, 0.464, 0.711, 0.283, 0.111.
(e) (2 puntos) Utilice alg´un m´etodo computacional para generar 10.000 instancias de una v.a. Uni-
forme(0,1) y genere instancias de X a partir de estos n´umeros, utilizando el m´etodo desarrollado.
¿Cu´antas instancias se generaron para X? Compare este valor con el valor te´orico. Adicional-
mente, presente un histograma de las instancias generadas para X. Compare este histograma
con un gr´afico de la funci´on de densidad de probabilidades de X.
5

