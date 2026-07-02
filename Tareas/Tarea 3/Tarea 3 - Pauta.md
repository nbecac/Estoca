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
Soluci´on:
M´etrica
Parte (a)
(i) Tiempo total
18.374577 h
(ii) Largo promedio cola personas
941.570102
(iii) Largo promedio cola buses
57.081362
(iv) Tiempo promedio desde salida de la fiesta hasta partida del bus
8.771347 h
(v) Tiempo promedio de espera en cola
8.642092 h
(vi) Personas promedio por bus
20.618557
(vii) Buses con pasajeros
97
Cuadro 1: Resultados Parte (a): Un bus frente al paradero (FIFO)
Se observa una congesti´on importante en el sistema, con colas promedio de 941.57 personas y 57.08
buses. La restricci´on de que solo un bus pueda ubicarse frente al paradero genera un cuello de botella
que provoca largas esperas para los pasajeros (8.64 horas en promedio). Sin embargo, los buses
son utilizados de manera relativamente eficiente, transportando en promedio 20.62 pasajeros de una
capacidad m´axima de 30.
2

(b) (7.5 puntos) Ahora considere que los buses abren sus puertas apenas llegan a la fiesta, sin importar
si est´an justo frente al paradero, y que los asistentes a la fiesta se suben a cualquiera de los buses con
igual probabilidad. Vuelva a calcular todo lo anterior y compare.
Soluci´on:
M´etrica
Parte (a)
Parte (b)
(i) Tiempo total
18.3746 h
17.1515 h
(ii) Largo promedio cola personas
941.5701
873.1370
(iii) Largo promedio cola buses
57.0814
1.5702
(iv) Espera promedio fiesta →bus parte
8.7713 h
7.5973 h
(v) Espera promedio en cola
8.6421 h
7.4880 h
(vi) Promedio pasajeros por bus
20.6186
18.5185
(vii) Buses con pasajeros
97
108
Cuadro 2: Comparaci´on de resultados: Parte (a) vs Parte (b)
Permitir m´ultiples buses abiertos simult´aneamente reduce dr´asticamente la congesti´on de buses (de
57.08 a 1.57) y disminuye tanto el tiempo total de evacuaci´on como las esperas de los pasajeros. Sin
embargo, la ocupaci´on promedio por bus baja de 20.62 a 18.52 pasajeros y se requieren m´as buses
(108 versus 97), por lo que se obtiene una evacuaci´on m´as r´apida a costa de una menor eficiencia en
el uso de la flota.
Hint: Se recomienda utilizar y completar el c´odigo base disponible en Canvas (M´odulo Tarea 3: Sistemas
de Espera y Simulaci´on) para el desarrollo de esta pregunta.
3

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
Soluci´on: Ω= {0, 1, 2, . . .}, donde el estado n representa el n´umero total de clientes en el sistema
(en atenci´on m´as en cola).
Se identifican cuatro reg´ımenes seg´un el n´umero de clientes en cola n −C:
⋄R´egimen 1: 0 ≤n ≤C — no hay cola, todos los clientes que llegan son atendidos de inmediato.
Hay n cajeros ocupados.
⋄R´egimen 2: C < n ≤C + K −1 — hay cola pero con menos de K clientes esperando, por lo
que todo cliente que llega ingresa con certeza.
⋄R´egimen 3: C + K ≤n ≤C + M −1 — hay K o m´as clientes en cola pero menos de M, por
lo que los clientes que llegan ingresan con probabilidad pn−C. A´un no hay deserci´on.
⋄R´egimen 4: n ≥C + M — hay M o m´as clientes en cola. Los clientes que llegan ingresan con
probabilidad pn−C, y adem´as los clientes impacientes pueden desertar. El n´umero de clientes
impacientes crece de uno en uno a partir de n = C + M hasta saturar en R, esto es, m´ın(n −
C −M + 1, R) impacientes, cada uno con tasa δ.
Tasas de transici´on instant´aneas:
qn,n+1 =
(
λ
0 ≤n ≤C + K −1
pn−C λ
n ≥C + K
qn,n−1 =







nµ
1 ≤n ≤C
Cµ
C < n ≤C + M −1
Cµ + m´ın(n −C −M + 1, R) δ
n ≥C + M
Todas las dem´as tasas qij = 0 para |i −j| > 1.
0
1
· · ·
C
C+K
· · ·
C+M
· · ·
C+M+R
· · ·
λ
µ
λ
2µ
λ
Cµ
λ
Cµ
pKλ
Cµ
pM−1λ
Cµ
pMλ
Cµ + δ
pM+R−1λ
Cµ + Rδ
pM+Rλ
Cµ + Rδ
Nota: la transici´on C + M →C + M −1 tiene tasa Cµ + δ (un solo impaciente), y a partir de ah´ı
el t´ermino de deserci´on crece en incrementos de δ hasta saturar en Rδ una vez alcanzado el estado
C + M + R −1, manteni´endose constante en Cµ + Rδ para todo n ≥C + M + R −1.
4

(b) (7 puntos) Escriba las ecuaciones de balance detallado (o global, seg´un corresponda) para cada
r´egimen del sistema. ¿Bajo qu´e condici´on sobre los par´ametros λ, µ, C, δ y R existe una distribuci´on
estacionaria?
Soluci´on:
Como se trata de un proceso de nacimiento y muerte, el balance detallado es v´alido
y equivalente al balance global. Las ecuaciones de balance detallado tienen la forma qn,n+1 πn =
qn+1,n πn+1, es decir, el flujo entre estados adyacentes se iguala en ambas direcciones.
R´egimen 1: 0 ≤n ≤C −1
λ πn = (n + 1)µ πn+1 =⇒πn+1 =
λ
(n + 1)µ πn
Aplicando recursivamente desde π0:
πn =
λn
n! µn π0 = 1
n!
λ
µ
n
π0,
0 ≤n ≤C
R´egimen 2: C ≤n ≤C + K −1
λ πn = Cµ πn+1 =⇒πn+1 =
λ
Cµ πn
Definiendo ρ = λ
Cµ, y aplicando desde πC:
πC+j = ρj πC = ρj 1
C!
λ
µ
C
π0,
0 ≤j ≤K −1
R´egimen 3: C +K ≤n ≤C +M −1, es decir, hay K ≤n−C ≤M −1 clientes en cola, con rechazo
pero sin deserci´on:
pn−C λ πn = Cµ πn+1 =⇒πn+1 = pn−C λ
Cµ
πn
Aplicando recursivamente desde πC+K:
πC+K+j =
 λ
Cµ
j  j−1
Y
ℓ=0
pK+ℓ
!
πC+K,
0 ≤j ≤M −K −1
R´egimen 4a: C + M ≤n ≤C + M + R −1, hay entre M y M + R −1 clientes en cola: rechazo y
deserci´on parcial (entre 1 y R −1 impacientes), con m´ın(n −C −M + 1, R) = n −C −M + 1 en este
rango:
pn−C λ πn =
 Cµ + (n −C −M + 1) δ

πn+1
πn+1 =
pn−C λ
Cµ + (n −C −M + 1) δ πn
R´egimen 4b: n ≥C +M +R−1, hay M +R−1 o m´as clientes en cola: rechazo y deserci´on m´axima
(R impacientes):
pn−C λ πn = (Cµ + Rδ) πn+1 =⇒πn+1 =
pn−C λ
Cµ + Rδ πn
Como pi es decreciente y acotada inferiormente por 0, el l´ımite p∞= l´ımi→∞pi existe, con 0 ≤p∞<
1. En el r´egimen 4b la raz´on de la recursi´on satisface:
pn−C λ
Cµ + Rδ −−−−→
n→∞
p∞λ
Cµ + Rδ
Con lo cual, basta pedir
p∞λ < Cµ + Rδ
En particular, si p∞= 0 (los clientes eventualmente nunca ingresan al saturarse la cola), la condici´on
se cumple para cualquier valor de λ, µ, C, δ, R.
(c) (3 puntos) Asumiendo que el sistema es estable y que se conocen todas las probabilidades estacio-
narias πn (n ≥0), calcule las siguientes medidas de desempe˜no en el largo plazo:
5

(i) (1 punto) Tasa efectiva de llegada
Soluci´on:
La tasa efectiva de llegada es la tasa a la que los clientes realmente ingresan al
sistema, ponderando por la probabilidad de ingreso en cada estado:
λef =
C+K−1
X
n=0
λ πn +
∞
X
n=C+K
pn−C λ πn = λ
 C+K−1
X
n=0
πn +
∞
X
n=C+K
pn−C πn
!
(ii) (1 punto) Tasa efectiva de deserci´on
Soluci´on:
La deserci´on ocurre solo cuando hay M o m´as clientes en cola, es decir, cuando
n ≥C + M. En ese r´egimen, el n´umero de desertores potenciales es m´ın(n −C −M + 1, R),
cada uno con tasa δ:
δef =
C+M+R−2
X
n=C+M
(n −C −M + 1) δ πn +
∞
X
n=C+M+R−1
R δ πn
= δ
 C+M+R−2
X
n=C+M
(n −C −M + 1) πn + R
∞
X
n=C+M+R−1
πn
!
(iii) (1 punto) N´umero medio de clientes en cola y tiempo medio de espera en cola
Soluci´on: El n´umero medio de clientes en cola considera solo los que est´an esperando, es decir,
cuando n > C:
Lq =
∞
X
n=C+1
(n −C) πn
El tiempo medio de espera en cola se obtiene por la ley de Little, usando la tasa efectiva de
llegada (la tasa a la que los clientes realmente ingresan al sistema):
Wq = Lq
λef
6

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
Soluci´on: Por el flujo descrito, las cuatro unidades son:
⋄Unidad 1: inspecci´on inicial.
⋄Unidad 2: revisi´on de fallas menores.
⋄Unidad 3: ingenier´ıa (fallas graves).
⋄Unidad 4: revisi´on final.
Grafo de flujo:
λ
γ
Estación 1
Inspección inicial
M/M/c1 , µ1
Estación 3
Ingeniería
M/M/c3 , µ3
Estación 2
Fallas menores
M/M/c2 , µ2
Estación 4
Revisión nal
M/M/c4 , µ4
salida
(tipo A)
salida
(tipo D)
salida
(tipos B, C)
λ
γ
pA
pC
pB
p3
1 −p3
γ
λ1 = λ
λ2 = λ(pB + pCp3)
λ3 = λpC + γ
λ4 = λ(1 −pA)
Igualando el flujo de entrada a cada unidad:
λ1 = λ
λ2 = λpB + λpC p3 = λ (pB + pC p3)
λ3 = λpC + γ
λ4 = λpB + λpC = λ (pB + pC) = λ (1 −pA)
7

La tasa total de ingreso al sistema es λ + γ (entrada principal m´as reproceso externo):
Tipo
Recorrido
Fracci´on del total
A
1 →salida
λpA
λ + γ
B
1 →2 →4
λpB
λ + γ
C
1 →3 [→2] →4
λpC
λ + γ
D
3 →salida
γ
λ + γ
Dentro del Tipo C, una subfracci´on p3 visita adem´as la Unidad 2.
Cada estaci´on M/M/ci es estable si su utilizaci´on es menor que 1:
ρi =
λi
ci µi
< 1,
i = 1, . . . , 4 =⇒







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







λ
c1µ1
< 1
λ(pB + pCp3)
c2µ2
< 1
λpC + γ
c3µ3
< 1
λ(1 −pA)
c4µ4
< 1
Despejando λ de cada condici´on:
λ < c1µ1,
λ <
c2µ2
pB + pCp3
,
λ < c3µ3 −γ
pC
,
λ <
c4µ4
1 −pA
.
La unidad m´as restrictiva es aquella con la menor cota superior para λ:
λm´ax = m´ın

c1µ1,
c2µ2
pB + pCp3
, c3µ3 −γ
pC
,
c4µ4
1 −pA

.
El cuello de botella es la unidad que alcanza este m´ınimo, y depende de los valores num´ericos de los
ci, µi, las fracciones y γ.
(b) (3 puntos) Suponiendo conocidos los tiempos promedio de permanencia en cada etapa del sistema,
obtenga el tiempo promedio total de permanencia para cada categor´ıa de producto (A, B, C y D). A
partir de ello, determine el tiempo promedio de permanencia de un producto arbitrario y analice la
relaci´on entre ambas cantidades.
Soluci´on: Cada tipo de producto suma los tiempos Wi de las unidades que efectivamente recorre:
WA = W1
WB = W1 + W2 + W4
WC = W1 + W3 + p3 W2 + W4
WD = W3
Ponderando por la tasa de llegada de cada categor´ıa sobre la tasa total λ + γ:
W = λpA WA + λpB WB + λpC WC + γ WD
λ + γ
.
De forma equivalente, por la ley de Little aplicada a todo el sistema, W = Ltot/(λ + γ), con Ltot =
L1 + L2 + L3 + L4.
Note que el tiempo global W ̸= P
i Wi, pues cada producto visita solo un subconjunto de unidades.
De esta manera, W es un promedio ponderado de los recorridos y siempre resulta menor que W1 +
W2 + W3 + W4.
(c) (4 puntos) Para la Unidad 3, eval´ue agregar (c3 + 1) versus eliminar (c3 −1) un servidor sobre ρ3,
L3, W3, WC, WD y W. D´e la condici´on exacta de inestabilidad al eliminar un servidor.
8

Soluci´on: La Unidad 3 tiene tasa efectiva λ3 = λpC + γ y utilizaci´on ρ3 = λpC + γ
c3 µ3
.
Agregar un servidor (c3 →c3 + 1). La utilizaci´on baja a
ρ+
3 =
λpC + γ
(c3 + 1) µ3
< ρ3.
Al disminuir ρ3, tambi´en disminuyen P0, Lq,3 y por tanto L3 y W3 = L3/λ3. Como W3 forma parte
de
WC = W1 + W3 + p3W2 + W4,
WD = W3,
ambos tiempos se reducen, y con ellos el tiempo global W (que pondera WC y WD por sus tasas λpC
y γ). Las dem´as unidades no se ven afectadas, pues sus tasas efectivas no dependen de c3.
Eliminar un servidor (c3 →c3 −1). La utilizaci´on sube a
ρ−
3 =
λpC + γ
(c3 −1) µ3
> ρ3.
Esto aumenta L3, W3 y, en consecuencia, WC, WD y W. La unidad deja de ser estable cuando ρ−
3 ≥1,
es decir:
λpC + γ ≥(c3 −1) µ3
Bajo esta condici´on la cola crece sin cota, L3, W3 →∞y el sistema no alcanza r´egimen estacionario.
(d) (4 puntos) Compare reducir el tiempo de servicio de la Unidad 2 (µ2 →µ′
2) con agregar un servidor
en ella, indicando en qu´e r´egimen conviene cada medida.
Soluci´on: La Unidad 2 tiene tasa efectiva λ2 = λ(pB + pC p3) y utilizaci´on ρ2 =
λ2
c2 µ2
. Los tipos
que la utilizan son el B (siempre) y el C (con probabilidad p3):
WB = W1 + W2 + W4,
WC = W1 + W3 + p3W2 + W4.
Analizaremos cada situaci´on por separado.
Acelerar el servicio (µ2 →µ′
2, con µ′
2 > µ2): El tiempo en la unidad es
W2 =
1
µ2
|{z}
servicio
+ Wq,2
|{z}
espera
.
Aumentar µ2 reduce ambos t´erminos: baja directamente el tiempo de servicio 1/µ2 y, al reducir
ρ2 = λ2/(c2µ2), tambi´en disminuye la espera en cola. Esto reduce W2, y por ende WB (con peso 1)
y WC (con peso p3).
Agregar un servidor (c2 →c2 + 1):. Reduce ρ2 y por tanto la espera en cola Wq,2, pero no altera
el tiempo de servicio individual 1/µ2.
Con lo cual,
⋄Si la unidad est´a muy congestionada (ρ2 cercano a 1), el tiempo est´a dominado por la espera en
cola, que crece como 1/(1 −ρ2). Agregar un servidor reduce ρ2 de forma escalonada y produce
la mayor ca´ıda de W2: conviene agregar servidor.
⋄Si la unidad est´a poco cargada (ρ2 bajo), la cola ya es despreciable y el tiempo est´a dominado
por el servicio 1/µ2. Un segundo servidor aportar´ıa poco, mientras que acelerar el servicio s´ı
reduce el componente dominante, es decir, conviene acelerar el servicio.
9

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
Soluci´on:
Para encontrar la inversa de la CDF. primero igualamos la CDF a una variable u que
sigue una distribuci´on Uniforme(0, 1):
u = 1 −e−(x/λ)k
Despejamos x en t´erminos de u:
e−(x/λ)k = 1 −u
−(x/λ)k = ln(1 −u)
x = λ(−ln(1 −u))1/k
Dado que u es una variable aleatoria Uniforme(0, 1), se puede simplificar la expresi´on a:
x = λ(−ln(1 −u))1/k
Luego el procediemiento para generar instancias de X es el siguiente:
⋄Generar una instancia u de una variable aleatoria Uniforme(0, 1).
⋄Calcular x usando la f´ormula inversa de la CDF:
x = λ(−ln(1 −u))1/k
Finalmente, generamos instancias de X utilizando las instancias dadas de Uniforme(0, 1), conside-
rando λ = 10 y k = 2.
⋄Para u = 0.19:
x = 10(−ln(1 −0.19))1/2 = 10(−ln(0.81))1/2 ≈4.57
⋄Para u = 0.37:
x = 10(−ln(1 −0.37))1/2 = 10(−ln(0.63))1/2 ≈6.07
⋄Para u = 0.91:
x = 10(−ln(1 −0.91))1/2 = 10(−ln(0.09))1/2 ≈15.60
As´ı, los valores generados de X son aproximadamente 4.57, 6.07 y 15.60. Cabe destacar que no importa
en el orden en que se evaluan los n´umeros aleatorios mientras el desarrollo est´e correcto.
2. (10 puntos) Considere una variable aleatoria continua X con la siguiente funci´on de densidad:
f(x) = b

sin(πx) + π
2

para x ∈[0, π]
(a) (2 puntos) Encuentre el valor de b para que f(x) efectivamente sea una funci´on de densidad.
Soluci´on: Para que f(x) sea densidad se requiere
R π
0 f(x) dx = 1:
b
Z π
0
sin(πx) dx +
Z π
0
π
2 dx

= b
1 −cos(π2)
π
+ π2
2

= 1
b =
1
1 −cos(π2)
π
+ π2
2
10

(b) (2 puntos) Desarrolle un algoritmo de Aceptaci´on y Rechazo para generar instancias de X.
Apoye su desarrollo con gr´aficos de las funciones relevantes.
Soluci´on: C´odigo disponible en Canvas.
(c) (2 puntos) Si se usa su algoritmo, ¿cu´al es el valor esperado de la cantidad de rechazos necesarios
para generar una instancia?
Soluci´on:
⋄Valor calculado de b: 0.18049
⋄Valor calculado de c: 1.45772
⋄Valor esperado de rechazos por instancia (c −1): 0.45772
(d) (2 puntos) Utilice su algoritmo con los siguientes n´umeros aleatorios Uniforme(0,1): 0.672,
0.236, 0.464, 0.711, 0.283, 0.111.
Soluci´on:
⋄Par 1 (U1=0.672, U2=0.236): Y=2.111, L´ımite=0.744, Aceptado
⋄Par 2 (U1=0.464, U2=0.711): Y=1.458, L´ımite=0.225, Rechazado
⋄Par 3 (U1=0.283, U2=0.111): Y=0.889, L´ımite=0.744, Aceptado
(e) (2 puntos) Utilice alg´un m´etodo computacional para generar 10.000 instancias de una v.a. Uni-
forme(0,1) y genere instancias de X a partir de estos n´umeros, utilizando el m´etodo desarrollado.
¿Cu´antas instancias se generaron para X? Compare este valor con el valor te´orico. Adicional-
mente, presente un histograma de las instancias generadas para X. Compare este histograma
con un gr´afico de la funci´on de densidad de probabilidades de X.
Soluci´on:
Figura 1: Histograma de las instancias generadas para la variable aleatoria X.
⋄Total de n´umeros Uniformes usados: 10000
⋄Total de intentos de generaci´on (pares): 5000
⋄Instancias de X generadas (emp´ırico): 3451
⋄Instancias esperadas (te´orico = Intentos/c): 3430.0
11

