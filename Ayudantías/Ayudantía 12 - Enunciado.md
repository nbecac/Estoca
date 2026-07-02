Pontificia Universidad Cat´olica de Chile
Escuela de Ingenier´ıa
Departamento de Ingenier´ıa Industrial y de Sistemas
ICS2123 – Modelos Estoc´asticos
Profesores Ver´onica Godoy y Andr´es Navarro
Ayudante Jefe Joaqu´ın Vergara
Primer Semestre 2026
Ayudant´ıa 12:
Sistemas de Espera I
Ayudantes: Emilio Pe˜na (emilio.penasepulveda@uc.cl) & Mart´ın Pe˜na (martinpena@uc.cl)
Resumen
Modelos Markovianos
Consideremos el estado X(t) como el n´umero de personas en el sistema (servidor + cola) en el instante t.
Entonces se tiene que {X(t), t ≤0} es una CMTC. Tenemos las siguientes posibilidades de sistemas:
Sistema M/M/1
⋄Llegadas seg´un un proceso de Poisson a tasa λ.
⋄Tiempos de atenci´on exponenciales con par´ametro µ
⋄Un servidor
⋄Capacidad infinita del sistema.
⋄Coincide con la estructura base de un proceso de nacimiento y muerte.
0
1
2
3
...
λ
µ
µ
λ
λ
λ
µ
µ
Pn = λn−1λn−2...λ0
µnµn−1...µ1
P0 = (λ
µ)nP0
Donde:
P0 =
1
P∞
n=0(λ
µ)n
Si λ
µ < 1 (el sistema converge), entonces:
P0 = 1 −λ
µ
Pn =
λ
µ
n 
1 −λ
µ

1

Y para las medidas de desempe˜no del sistema:
L =
∞
X
n=0
nPn =
λ
µ −λ
W = L
λe
=
1
µ −λ
Donde se puede obtener las m´etricas para la cola:
Lq =
∞
X
n=0
(n −1)Pn =
λ2
µ(µ −λ)
Wq = Lq
λe
=
λ
µ(µ −λ)
Sistema M/M/1/K
⋄Llegadas seg´un un proceso de Poisson a tasa λ.
⋄Tiempos de atenci´on exponenciales con par´ametro µ
⋄Un servidor
⋄Capacidad finita. Pueden haber m´aximo K entidades en el sistema.
⋄Es muy similar al sistema M/M/1, con la diferencia que si una entidad llega al sistema y esta lleno,
entonces se va. Por lo tanto, la tasa de entrada efectiva al sistema λe es:
λe = λ(1 −Pk)
0
1
2
...
K −1
K
λ
λ
µ
µ
µ
λ
λ
µ
λ
µ
Pn = λn−1λn−2 · · · λ0
µnµn−1 · · · µ1
P0 =
λ
µ
n
P0
K
X
n=0
Pn = 1
Donde hay que recordar que el sistema siempre converger´a al haber una capacidad asociada:
P0 =
1
K
X
n=0
λ
µ
n =
1 −λ
µ
1 −
λ
µ
K+1
Y para las medidas de desempe˜no del sistema:
L =
K
X
n=0
nPn =




λ
µ
1 −λ
µ









1 −
λ
µ
K
−K
λ
µ
K
+ K
λ
µ
K+1
1 −
λ
µ
K+1





2

W = L
λe
=
L
λe(1 −PK) =




λ
µ
1 −λ
µ










1 −
λ
µ
K
−K
λ
µ
K
+ K
λ
µ
K+1
λ(1 −PK)
 
1 −
λ
µ
K+1!






Para la cola:
Lq =
K
X
n=0
(n −1)Pn
Wq = Lq
λe
Sistema M/M/c
⋄Llegadas seg´un un proceso de Poisson a tasa λ.
⋄Tiempos de atenci´on exponenciales con par´ametro µ
⋄c servidores
⋄Capacidad infinita.
⋄Es parecido al sistema M/M/1, pero ahora se pueden atender hasta c entidades al mismo tiempo. Por
ende, si hay menos de c entidades en el sistema, la cola ser´a nula.
0
1
2
...
c −1
c
c + 1
...
λ
λ
µ
2µ
3µ
λ
λ
(c −1)µ
λ
cµ
λ
cµ
λ
cµ
Para las tasas de salida tendremos lo siguiente:
µn =



nµ
0 < n ≤c
cµ
n > c
Y como
Pn = λn−1λn−2...λ0
µnµn−1...µ1
P0
Tendremos entonces:
Pn =









λn
n!µn P0
0 < n ≤c
λn
c!cn−cµn P0
n > c
∞
X
n=0
Pn = 1
3

Por lo que:
P0 =
1
Pc
n=0
λn
n!µn + P∞
n=c+1
λn
c!cn−cµn
La primera sumatoria siempre converger´a. Pero para la segunda es necesario pedir que λ
cµ < 1. Con ello,
se tendr´a que:
∞
X
n=c+1
λn
c!cn−cµn = λc
c!µc
λ
cµ
1 −λ
cµ
P0 =
1
Pc
n=0
λn
n!µn + λc
c!µc
λ
cµ
1 −λ
cµ
Las medidas de desempe˜no:
L =
∞
X
n=0
nPn
W = L
λe
Lq =
∞
X
n=c
(n −c)Pn
Wq = Lq
λe
Sistema M/M/c/K
⋄Llegadas seg´un un proceso de Poisson a tasa λ.
⋄Tiempos de atenci´on exponenciales con par´ametro µ
⋄c servidores
⋄Capacidad finita. Pueden haber m´aximo K entidades en el sistema (K ≥c para que tenga sentido).
Donde la tasa de entrada efectiva al sistema λe es:
λe = λ(1 −PK)
0
1
2
...
c −1
c
c + 1
...
K −1
K
λ
λ
µ
2µ
3µ
λ
λ
(c −1)µ
λ
cµ
λ
cµ
λ
cµ
λ
λ
cµ
cµ
Para las tasas de salida tendremos lo mismo que para el sistema M/M/c:
µn =



nµ
0 < n ≤c
cµ
n > c
4

Y como:
Pn = λn−1λn−2...λ0
µnµn−1...µ1
P0
Tendremos entonces:
Pn =









λn
n!µn P0
0 < n ≤c
λn
c!cn−cµn P0
n > c
K
X
n=0
Pn = 1
Por lo que:
P0 =
1
Pc
n=0
λn
n!µn + PK
n=c+1
λn
c!cn−cµn
Y como estas suma siempre converger´an, entonces:
K
X
n=c+1
λn
c!cn−cµn = λc
c!µc
λ
cµ
1 −( λ
cµ)K−c
1 −λ
cµ
P0 =
1
Pc
n=0
λn
n!µn + λc
c!µc
λ
cµ
1 −( λ
cµ)K−c
1 −λ
cµ
Las medidas de desempe˜no:
L =
K
X
n=0
nPn
W = L
λe
Lq =
K
X
n=c
(n −c)Pn
Wq = Lq
λe
Sistema M/G/1
⋄Llegadas seg´un un proceso de Poisson a tasa λ.
⋄Tiempos de atenci´on seg´un v.a. distinta a exponencial
⋄un servidores
⋄Capacidad infinita.
Sea D la v.a. que controla los timepos de llegada (D ∼Exp(λ)) y S la v.a. que modele tiempos de salida,
se tiene:
Si λE[S] < 1 (el sistema converge), entonces:
P0 =
E[D]
E[D] + E[O]
con E[O] =
E[S]
1 −λE[S]
5

Y para las medidas de desempe˜no del sistema:
L =
∞
X
n=0
nPn =
λ2E[S2]
2(1 −λE[S]) + λE[S]
W = L
λe
= L
λ
Donde se puede obtener las m´etricas para la cola:
Lq =
∞
X
n=0
(n −1)Pn =
λ2
µ(µ −λ)
Wq = Lq
λe
= Lq
λ
6

Problema 1
En un hospital, los pacientes llegan a la sala de emergencias seg´un un proceso Poisson con tasa λ. En
el hospital hay tres ´areas principales: triage, tratamiento y farmacia. Al llegar, todos los pacientes se
dirigen a la zona de triage, donde dos enfermeros atienden a cada paciente, demorando un tiempo aleatorio
exponencialmente distribuido con tasa µ. Tras ser evaluados, pueden ocurrir tres situaciones:
1. Con probabilidad q > 0, el paciente es admitido para tratamiento y se dirige a la sala de tratamiento.
2. Con probabilidad p > 0, el paciente es dado de alta y se va a su casa.
3. Con probabilidad r > 0, el paciente necesita recoger medicamentos en la farmacia antes de irse a
casa.
Se cumple que p + q + r = 1. La sala de tratamiento cuenta con cinco doctores, y cada uno de ellos tarda
en atender a cada paciente un tiempo aleatorio exponencialmente distribuido con tasa β. En la farmacia
hay un solo farmac´eutico que se encarga de despachar los medicamentos, tardando en cada atenci´on un
tiempo tambi´en aleatorio exponencialmente distribuido con tasa γ. Tras recibir tratamiento, los pacientes
deben dirigirse obligatoriamente a la farmacia para obtener sus medicamentos. Existe una fila ´unica para
esperar atenci´on en triage, y otra fila ´unica para esperar atenci´on en tratamiento (es decir, hay tres filas
en total en el hospital). Una vez que los pacientes obtienen sus medicamentos o son dados de alta, salen
del hospital. Se desea analizar el comportamiento del hospital en estado estacionario.
(a) En el hospital descrito, ¿qu´e tipos de sistemas de espera existen?
(b) Modele mediante una Cadena de Markov en Tiempo Continuo cada ´area de atenci´on del hospital.
Indique las tasas efectivas de entrada a cada etapa y las condiciones que se deben cumplir en cada
una de ellas para asegurar que el sistema no colapse.
(c) Encuentre el tiempo medio de permanencia y el tiempo medio en cola de un paciente que tras el
triage decide recoger medicamentos en la farmacia.
7

Problema 2
Para las carreras de la F´ormula 1 se han dispuesto el siguiente conjunto de sistemas para la entrada
del p´ublico, los asistentes llegan con una tasa λ personas por minuto a la puerta de entrada. Al entrar,
estos son derivados a los detectores de metales con una probabilidad 0 < p1 < 1 y con probabilidad
(1 −p1) van a una revisi´on manual por parte de 3 guardias de seguridad. Existen 4 detectores de metal,
que trabajan en paralelo, cuyos tiempo de detecci´on distribuyen Exponencial(β) en minutos para cada
detector. Los guardias de seguridad tambi´en trabajan en paralelo, pero cada uno libera a las personas con
tiempo que distribuyen Exponencial(α) personas por minuto. Asuma que tanto los detectores como los
guardias puede estar trabajando con una persona a la vez. Asume que con probabilidad p2 alg´un detector
de metal encuentra un objeto sospechoso y con probabilidad p3 el objeto es detectado por alg´un guardia
(0 < p2, p3 < 1). Aquellas personas con objetos sospechosos son derivadas a una sala donde los someten a
una revisi´on exhaustiva por parte de un experto en seguridad, cuyo tiempo de revisi´on es Exponencial(δ)
en minutos. Estos expertos deciden expulsar del Gran Premio a las personas que se someten a revisi´on
con probabilidad 0 < p4 < 1. Aquellas personas que no les encontraron nada (tanto del primer paso de
detectores o guardias, o de la revisi´on exhaustiva), deben pasar finalmente a la revisi´on de los tickets,
donde hay 5 m´aquinas que escanean tickets cuyo tiempo en minutos de escaneo distribuye Exponencial(γ),
adem´as considere que los espectadores son bastante impacientes, por lo que si en la cola para revisi´on de
tickets hay 20 personas, estas no ingresaran y simplemente se ir´an. Asume que todas las probabilidades pi
con i ∈{1, ..., 4}, el proceso de llegada y todos los tiempos de atenci´on son independientes entre s´ı.
(a) Identifique los diferentes sistemas de espera que componen el sistema de entrada a las carreras,
especificando su clasificaci´on en el formato X1/X2/X3/X4. Justifica tu respuesta
(b) Dibuje un diagrama que relacione todos los sistemas de espera y se˜nale claramente las tasas de
atenci´on total y de llegada asumiendo que el sistema completo converge (es decir, el n´umero esperado
de espectadores en el sistema no tiende a infinito)
(c) ¿Qu´e relaciones deben cumplir la tasa de llegada y las tasas de atenci´on para que en el largo plazo el
sistema completo converja?
(d) Calcula las siguientes medidas de desempe˜no en el largo plazo:
(i) N´umero medio de espectadores en el sistema completo. Deja tu soluci´on expresada en funci´on
de las tasa del problema.
(ii) Tiempo medio en el sistema.
(iii) N´umero medio de espectadores en cola esperando para ser atendidos por primera vez (por un
guardia o un detector de metales).
8

Problema 3 (Propuesto)
Hades, debe lidiar d´ıa a d´ıa con el trabajo de administrar la entrada de almas a sus dominios y juzgarlas
debidamente (mucho papeleo). En la Casa de Hades, las almas forman una fila frente al escritorio del dios
y esperan a que les toque su turno. Las almas llegan seg´un un Proceso de Poisson a tasa λ y el tiempo de
atenci´on de Hades se comporta como una variable aleatoria Exponencial con tasa µH.
La cantidad m´axima de almas que pueden entrar a su casa son un total de N, contando la que est´a siendo
atendida. Adem´as, cuando hay al menos S almas en cola, el m´usico de la corte Orfeo, junto a su musa, se
dispone a tocar una melod´ıa del agrado de su jefe, lo cual lo hacen con una unidad extra de pasi´on por
cada nueva alma que llega a la cola. Si las almas en cola se reducen a una cantidad menor a S, dejan de
tocar.
Hades se ve afectado por la m´usica, y por cada unidad de pasi´on que haya en la melod´ıa, aumentar´a su
eficiencia en un 10 % respecto al momento anterior.
(a) Indique a qu´e tipo de sistema corresponde la situaci´on descrita y realice un diagrama con los estados
y tasas correspondientes, Adem´as, explicite las tasas de transici´on instant´anea y las de permanencia
para cada estado.
(b) Escriba las ecuaciones de equilibrio en el largo plazo para este sistema, sin calcularlas expl´ıcitamente.
(c) Indique que propiedades cumple el sistema para que no colapse. Adem´as, se˜nale qu´e se deber´ıa
modificar para que pudiese colapsar.
(d) Calcule el porcentaje de tiempo en el cual el sistema se encuentra ocupado.
9

