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
Entonces se tiene que {X(t), t ≥0} es una CMTC. Tenemos las siguientes posibilidades de sistemas:
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
3

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
Soluci´on: El ´area de triage es un sistema de espera M/M/2, el ´area de tratamiento es un sistema
de espera M/M/5, y la farmacia es M/M/1.
(b) Modele mediante una Cadena de Markov en Tiempo Continuo cada ´area de atenci´on del hospital.
Indique las tasas efectivas de entrada a cada etapa y las condiciones que se deben cumplir en cada
una de ellas para asegurar que el sistema no colapse.
Soluci´on: Para esto podemos representar las tres partes del problema por separado. En cada una,
los estados representan la cantidad i de pacientes en el ´area (en atenci´on y en fila esperando atenci´on),
con i ∈[0, ∞).
• Triage: En este caso λe = λ, todo paciente que entra al sistema pasa por esta ´area. Para alcanzar
estacionalidad se requiere que la tasa de llegada de cada sistema sea menor a la tasa de atenci´on
de cada uno, en este caso la condici´on es λ < 2µ. El grafo para este sistema de la red es:
0
1
2
3
· · ·
λ
λ
λ
λ
µ
2µ
2µ
2µ
• Tratamiento: En este caso λe = λq, ya que solo la porci´on q de pacientes pasan a tratamiento
luego del triage. Para alcanzar estacionalidad se requiere que λq < 5β. El grafo es:
0
1
2
3
4
5
6
· · ·
λq
λq
λq
λq
λq
λq
λq
β
2β
3β
4β
5β
5β
5β
• Farmacia: En este caso λe = λ(1 −p), ya que solo la porci´on p de pacientes deciden retirarse y
no utilizar ning´un servicio del hospital luego del triage. Para alcanzar estacionalidad se requiere
que λ(1 −p) < γ. El grafo es:
0
1
2
· · ·
λ(1 −p)
λ(1 −p)
λ(1 −p)
γ
γ
γ
4

(c) Encuentre el tiempo medio de permanencia y el tiempo medio en cola de un paciente que tras el
triage decide recoger medicamentos en la farmacia.
Soluci´on: Este paciente primero pasa por el triage y luego se va a la farmacia, por lo que su tiempo
de permanencia promedio es:
W = WT + WF
Por la ecuaci´on de Little:
W = LT
λ +
LF
λ(1 −p)
Y su tiempo medio en cola es:
Wq = WqT + WqF
Wq = 1
λ
∞
X
i=3
(i −2)P T
i +
1
λ(1 −p)
∞
X
i=2
(i −1)P F
i
Wq = 1
λ
∞
X
i=3
(i −2)
2i−1
·
λ
µ
i
· P T
0 +
1
λ(1 −p)
∞
X
i=2
(i −1) ·
λ(1 −p)
γ
i
· P F
0
5

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
Soluci´on: Detectores: M/M/4
Guardias: M/M/3
Experto: M/M/1
Tickets: M/M/5/25
Cada estaci´on posee llegadas y salidas markovianas debido a que sus tiempos entre eventos distribu-
yen exponencial. Para la cantidad de ´cajas´ en servicio se usa el valor de la cantidad de personas o
maquinaria trabajando en paralelo en cada estaci´on. La ´unica estaci´on que posee capacidad finita es
la de tickets, en donde solo habr´a una cola de m´aximo 20 personas, y por ende, un capacidad m´axima
de 25.
(b) Dibuje un diagrama que relacione todos los sistemas de espera y se˜nale claramente las tasas de
atenci´on total y de llegada asumiendo que el sistema completo converge (es decir, el n´umero esperado
de espectadores en el sistema no tiende a infinito)
Soluci´on:
(c) ¿Qu´e relaciones deben cumplir la tasa de llegada y las tasas de atenci´on para que en el largo plazo el
sistema completo converja?
Soluci´on: Se debe cumplir que las salidas son m´as r´apidas que las llegadas en cada estaci´on, por ende:
Detectores: λp1 < 4β
6

Guardias: λ(1 −p1) < 3α
Experto: λp1p2 + λ(1 −p1)p3 < δ
Tickets: Es finita
(d) Calcula las siguientes medidas de desempe˜no en el largo plazo:
(i) N´umero medio de espectadores en el sistema completo. Deja tu soluci´on expresada en funci´on
de las tasa del problema.
(ii) Tiempo medio en el sistema.
(iii) N´umero medio de espectadores en cola esperando para ser atendidos por primera vez (por un
guardia o un detector de metales).
Soluci´on: Se nos pide calcular L, W y LD
q +LG
q . Para ello primero se necesitan determinar los valores
de P j
n con j ∈{D, G, E, T}.
Sean:
λD = λp1
λG = λ(1 −p1)
λE = λp1p2 + λ(1 −p1)p3
λT = λp1(1 −p2) + λ(1 −p1)(1 −p3) + (λp1p2 + λ(1 −p1)p3)(1 −p4) = λ(1 −(p1p2 + (1 −p1)p3)p4)
Con ello:
λD
n−1 ... λD
0
µD
n ... µD
1
=
( (λD)n
n!βn
si n ≤4
(λD)n
4!4n−4βn
si n > 4
λG
n−1 ... λG
0
µG
n ... µG
1
=
( (λG)n
n!αn
si n ≤3
(λG)n
3!3n−3αn
si n > 3
λE
n−1 ... λE
0
µE
n ... µE
1
= (λE)n
δn
λT
n−1 ... λT
0
µTn ... µT
1
=
( (λT )n
n!γn
si n ≤5
(λT )n
5!5n−5γn
si 5 < n ≤25
Con estas expresiones se procede a calcular los Pn:
P D
n = λD
n−1 ... λD
0
µD
n ... µD
1
P D
0
con P D
0 = (1 +
∞
X
n=1
λD
n−1 ... λD
0
µD
n ... µD
1
)−1
P G
n = λG
n−1 ... λG
0
µG
n ... µG
1
P G
0
con P G
0 = (1 +
∞
X
n=1
λG
n−1 ... λG
0
µG
n ... µG
1
)−1
P E
n = (λE)n
δn
P E
0
con P E
0 = 1 −λE
δ
P T
n = λT
n−1 ... λT
0
µTn ... µT
1
P T
0
con P T
0 = (1 +
25
X
n=1
λT
n−1 ... λT
0
µTn ... µT
1
)−1
Con ello, se procede con el calculo de las m´etricas pedidas:
L = LD + LG + LE + LT =
∞
X
n=0
nP D
n + nP G
n + nP E
n +
25
X
n=0
nP T
n
7

W = p1W D + (1 −p1)W G + (p1p2 + (1 −p1)p3)W E + (1 −(p1p2 + (1 −p1)p3)p4)W T
LD
q + LG
q =
∞
X
n=4
(n −4)P D
n +
∞
X
n=3
(n −3)P G
n
En donde:
W D = LD
λD
W G = LG
λG
W D = LE
λE
W D = LT
λTe
=
LT
λT (1 −P T
25)
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
Soluci´on: La situaci´on anterior descrita corresponde a un sistema de espera del tipo M/M/1/K,
donde 1 representa el n´umero de servidores y K que tiene capacidad m´axima. En este caso, ser´ıa un
M/M/1/N.
El grafo es el siguiente:
0
1
2
...
S
S + 1
S + 2
N −1
N
...
λ
λ
λ
λ
λ
λ
λ
λ
λ
1.1µH
µH
µH
µH
µH
(1.1)N−SµH
(1.1)N−1−SµH
(1.1)3µH
(1.1)2µH
Las tasas de transici´on instant´anea para cada estado son las siguientes:
qi,i+1 = λ,
i = 0, 1, ..., N −1
qi,i−1 = µH,
i = 1, 2, ..., S
qi,i−1 = (1.1)i−SµH,
i = S + 1, S + 2, ..., N
Las tasas de permanencia para cada estado son las siguientes:
νi = λ,
i = 0
νi = λ + µH,
i = 1, 2, ..., S
νi = λ + (1.1)i−SµH,
i = S + 1, ..., N −1
νi = (1.1)i−SµH,
i = N
9

(b) Escriba las ecuaciones de equilibrio en el largo plazo para este sistema, sin calcularlas expl´ıcitamente.
Soluci´on: Las ecuaciones de equilibrio son las siguientes:
λP H
0 = µHP H
1
(µH + λ)P H
i
= λP H
i−1 + µHP H
i+1
i = 1, 2, ..., S −1
(µH + λ)P H
S = λP H
S−1 + (1.1)µHP H
S+1
((1.1)i−SµH + λ)P H
i
= λP H
i−1 + (1.1)i+1−SµHP H
i+1
i = S + 1, ..., N −1
(1.1)N−SµHP H
N = λP H
N−1
N
X
i=0
P H
i
= 1
(c) Indique que propiedades cumple el sistema para que no colapse. Adem´as, se˜nale qu´e se deber´ıa
modificar para que pudiese colapsar.
Soluci´on: Se˜nalar que al tener un m´aximo de almas en total, este nunca podr´a colapsar, por lo que
no se necesitar´ıan propiedades adicionales.
Existen dos condiciones que deben cumplirse para que un sistema de espera colapse: que no haya
capacidad m´axima y que la tasa de llegada sea mayor a la de atenci´on.
Como las tasas van cambiando, deber´ıamos pensar en los ´ultimos estados del sistema, donde ya no
hay modificaci´on de tasas seg´un indicaciones (considerando que ya no hay capacidad m´axima). En
este problema, sin embargo, las tasas cambian incluso luego por la relaci´on que se establece con la
tasa de salida seg´un el estado en el que se encuentra.
Suponiendo que no hubiese capacidad m´axima de almas, se debe tener en mente que la tasa de sali-
das va aumentando cada vez que llega una alma, por lo que ser´ıa l´ogico pensar que la cola no podr´ıa
extenderse hasta el infinito, ya que en alg´un punto se del sistema en adelante la tasa de llegada ser´ıa
menor a la de salidas.
(d) Calcule el porcentaje de tiempo en el cual el sistema se encuentra ocupado.
Soluci´on: N´otese que el tiempo en el cual el sistema se encuentra ocupado, corresponde a todo aquel
tiempo en el cual hay al menos 1 alma en el sistema, es decir, el complemento de que el sistema se
encuentre vac´ıo.
Ocupaci´on % =
N
X
i=1
Pi = 1 −P H
0
10

