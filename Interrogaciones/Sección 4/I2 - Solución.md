Pontificia Universidad Cat´olica de Chile
Escuela de Ingenier´ıa
Departamento de Ingenier´ıa Industrial y de Sistemas
ICS2123 – Modelos Estoc´asticos
Profesor Andr´es Navarro
Primer Semestre 2026
Interrogaci´on 2
Duraci´on: 2 horas 30 minutos
Problema 1 (18 puntos)
Responda las siguientes preguntas de manera independiente:
(a) (6 puntos) Un dado balanceado se lanza sucesivamente. La secuencia termina cuando, por primera vez, el producto
entre el resultado del lanzamiento actual y el del lanzamiento inmediatamente anterior sea igual a 12. Represente
el problema como una cadena de Markov en tiempo discreto (CMTD), definiendo un espacio de estados apropiado,
y explique (no necesariamente calcular) como obtener el esperado de la cantidad de lanzamientos necesarios para
alcanzar la condici´on de detenci´on, detallando las variables y ecuaciones necesarias.
Soluci´on: Se lanza un dado equilibrado hasta que el producto de dos lanzamientos consecutivos sea 12. Las parejas
que cumplen son (2, 6), (6, 2), (3, 4), (4, 3). Definimos los estados:
• S: inicio (a´un no hay lanzamiento previo).
• V : el ´ultimo lanzamiento es 2, 3, 4 o 6 (tiene un ´unico complemento que da 12).
• N: el ´ultimo lanzamiento es 1 o 5 (nunca puede dar producto 12).
• fin: estado absorbente (se cumple la condici´on).
Con el orden (S, V, N, fin):
P =








0
2
3
1
3
0
0
1
2
1
3
1
6
0
2
3
1
3
0
0
0
0
1








Desde V : con probabilidad 1/6 sale el complemento y se llega a 12; quedan 3 caras v´alidas (1/2) y 2 neutras (1/3).
Para obtener el valor esperado de cantidad de lanzamientos necesarios para llevar al estado 12 por primera vez se
debe resolver el siguiente sistema de ecuaciones:
E(T(S, fin)) = 1 + 2
3E(T(V, fin)) + 1
3E(T(N, fin)),
E(T(V, fin)) = 1 + 1
2E(T(V, fin)) + 1
3E(T(N, fin)),
E(T(N, fin)) = 1 + 2
3E(T(V, fin)) + 1
3E(T(N, fin)).
1

Resolviendo el sistema obtenemos (no requerido en la respuesta):
E(T(S, fin)) = 21
2 = 10,5
Otra forma de resolver el problema es definiendo el estado como el ´ultimo dado que sali´o, sumado a dos estados
posibles de inicio (estado S) y cierre (estado fin). Con esto, la matriz de transici´on es:
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








0
1
6
1
6
1
6
1
6
1
6
1
6
0
0
1
6
1
6
1
6
1
6
1
6
1
6
0
0
1
6
1
6
1
6
1
6
1
6
0
1
6
0
1
6
1
6
1
6
0
1
6
1
6
1
6
0
1
6
1
6
0
1
6
1
6
1
6
1
6
0
1
6
1
6
1
6
1
6
1
6
1
6
0
0
1
6
0
1
6
1
6
1
6
1
6
1
6
0
0
0
0
0
0
0
1
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








Para obtener el valor esperado de la cantida de lanzamientos (etapas) necesarias para alcanzar la condici´on de
detenci´on, partiendo desde un inicio, se deben plantear las ecuaciones para encontrar E(T(S, fin))
Distribuci´on de puntaje:
• 2 puntos por plantear el espacio de estados
• 2 puntos por plantear la matriz de transici´on
• 2 puntos por plantear las ecuaciones para obtener el valor esperado de la cantidad de lanzamientos necesarios
(b) (6 puntos) Una part´ıcula se mueve entre tres estados {1, 2, 3} seg´un una CMTD con la siguiente matriz de transici´on,
donde p, q, r ∈[0, 1] son par´ametros de dise˜no:
P =




1 −p
p
0
0
1 −q
q
r
0
1 −r




Determine qu´e condiciones deben cumplir los factores p, q, r para que la cadena posea distribuci´on l´ımite. Justifique
distinguiendo entre la existencia de distribuci´on estacionaria y de distribuci´on l´ımite. Bajo dichas condiciones, obtenga
las ecuaciones que permiten obtener la distribuci´on de largo plazo en funci´on de p, q, r.
Soluci´on: Para tener distribuci´on l´ımite se deben cumplir dos condiciones.
Primero, la cadena debe ser irreducible. Para ello se necesita que
p > 0,
q > 0,
r > 0,
ya que si alguno fuera 0 se corta el ciclo (por ejemplo, con p = 0 el estado 1 queda absorbente) y la cadena deja de
ser irreducible.
Segundo, la cadena debe ser aperi´odica. Para ello se requiere que p, q, r no sean los tres iguales a 1, es decir
(p, q, r) ̸= (1, 1, 1).
2

Ecuaciones de la distribuci´on de largo plazo. Bajo dichas condiciones, π = (π1, π2, π3) se obtiene resolviendo
π = πP junto con la condici´on de normalizaci´on:
π1 = (1 −p) π1 + r π3,
π2 = p π1 + (1 −q) π2,
π3 = q π2 + (1 −r) π3,
π1 + π2 + π3 = 1.
Distribuci´on de puntaje:
• 2 puntos por plantear requerimiento de p > 0,
q > 0,
r > 0
• 2 puntos por plantear requerimiento de (p, q, r) ̸= (1, 1, 1).
• 2 puntos por plantear las ecuaciones para obtener la distribuci´on de largo plazo
(c) (6 puntos) Una m´aquina procesa productos y admite como m´aximo 6 productos en el sistema. Los pedidos llegan
seg´un un proceso de Poisson de tasa λ. Cada pedido es, de forma independiente, de un solo producto con probabilidad
p o de dos productos con probabilidad 1 −p, con p ∈(0, 1).
Si un pedido no cabe completo (un pedido de dos cuando queda un solo espacio, o cualquier pedido con el sistema
lleno), el pedido se pierde por completo. El procesamiento toma un tiempo exponencial de tasa µ. Mientras hay 3
o menos productos, cada procesamiento retira 1 producto; cuando hay 4 o m´as, la m´aquina procesa de a 2 (cada
procesamiento retira 2 productos).
Modele el n´umero de productos en el sistema como una CMTC: defina los estados, tasas de transici´on, y plantee las
ecuaciones de equilibrio (largo plazo) junto con la condici´on de normalizaci´on. No es necesario resolver el sistema.
Soluci´on: Estados. X(t) ∈{0, 1, 2, 3, 4, 5, 6}: n´umero de productos en el sistema.
Tasas de transici´on. El pedido de un producto llega a tasa efectiva λp y el de dos productos a tasa λ(1 −p).
• n →n + 1 a tasa λp, para n ∈{0, . . . , 5}.
• n →n + 2 a tasa λ(1 −p), para n ∈{0, . . . , 4} (en n = 5 el pedido de dos no cabe y se pierde; en n = 6 todo se
pierde).
• n →n −1 a tasa µ, para n ∈{1, 2, 3}.
• n →n −2 a tasa µ, para n ∈{4, 5, 6}.
0
1
2
3
4
5
6
λp
λp
λp
λp
λp
λp
µ
µ
µ
λ(1 −p)
λ(1 −p)
λ(1 −p)
λ(1 −p)
λ(1 −p)
µ
µ
µ
3

Ecuaciones de equilibrio.
λ π0 = µ π1,
(λ + µ) π1 = λp π0 + µ π2,
(λ + µ) π2 = λ(1 −p) π0 + λp π1 + µ π3 + µ π4,
(λ + µ) π3 = λ(1 −p) π1 + λp π2 + µ π5,
(λ + µ) π4 = λ(1 −p) π2 + λp π3 + µ π6,
(λp + µ) π5 = λ(1 −p) π3 + λp π4,
µ π6 = λ(1 −p) π4 + λp π5,
6
X
n=0
πn = 1.
Distribuci´on de puntaje:
• 2 puntos por plantear el espacio de estados correctamente
• 2 puntos por plantear las tasas de transici´on correctamente
• 2 puntos por plantear las ecuaciones de equilibrio
4

Problema 2 (24 puntos)
Una m´aquina de precisi´on termina cada d´ıa en una de dos condiciones: calibrada (C) o descalibrada (D). Despu´es de
mucho estudiar su comportamiento los t´ecnicos comprobaron que la condici´on de la m´aquina en un d´ıa cualquiera sigue las
siguientes reglas:
• Tras una racha de dos d´ıas calibrada, al d´ıa siguiente sigue calibrada con probabilidad 0,75.
• Si el d´ıa anterior estaba calibrada y luego se descalibr´o, al d´ıa siguiente se recalibra con probabilidad 0,40.
• Si el d´ıa anterior estaba descalibrada y reci´en se recuper´o, al d´ıa siguiente se mantiene calibrada s´olo con probabilidad
0,50 (la recuperaci´on es fr´agil).
• Tras dos d´ıas descalibrada, al d´ıa siguiente logra calibrarse con probabilidad 0,60 (intervenci´on del equipo t´ecnico).
(a) (6 puntos) Modele la operaci´on de la m´aquina como una CMTD. Defina claramente el espacio de estados y obtenga
la matriz de transici´on.
Soluci´on:
La regla depende de las condiciones de los dos ´ultimos d´ıas, de modo que el estado debe registrar el par
(ayer, hoy):
S = {CC, CD, DC, DD}
(primera letra = ayer).
Cada d´ıa el estado avanza de (X, Y ) a (Y, Z), donde Z es la condici´on de ma˜nana seg´un las reglas.
P =






0,75
0,25
0
0
0
0
0,40
0,60
0,50
0,50
0
0
0
0
0,60
0,40






.
CC
DC
CD
DD
0, 75
0, 25
0, 5
0, 5
0, 4
0, 6
0, 6
0, 4
Distribuci´on de puntaje:
• 3 puntos por plantear el espacio de estados
• 3 puntos por plantear la matriz de transici´on o el grafo asociado
(b) (6 puntos) En el largo plazo: ¿qu´e fracci´on de los d´ıas la m´aquina opera calibrada? Adem´as, ¿cu´antas veces por
cada 100 d´ıas, en promedio, la m´aquina “se cae” (un d´ıa calibrada seguido de uno descalibrada)?
5

Soluci´on: Sea π = (πCC, πCD, πDC, πDD). Tenemos el siguiente sistema de ecuaciones:
πCC = 0,75 πCC + 0,50 πDC
πCD = 0,25 πCC + 0,50 πDC
πDC = 0,40 πCD + 0,60 πDD
πDD = 0,60 πCD + 0,40 πDD
1 = πCC + πCD + πDC + πDD
Resolviendo obtenemos:
π = (πCC, πCD, πDC, πDD) = (0,4, 0,2, 0,2, 0,2)
La m´aquina opera calibrada cuando hoy = C (estados CC o DC):
Pr(calibrada) = πCC + πDC = 0,4 + 0,2 = 0,6.
Una “ca´ıda” es estar en un d´ıa calibrada (CC o DC) y pasar a descalibrada al d´ıa siguiente. En r´egimen estacionario
su frecuencia es
πCC(0,25) + πDC(0,50) = 0,4(0,25) + 0,2(0,50) = 0,2 ⇒20 ca´ıdas por cada 100 d´ıas.
Distribuci´on de puntaje:
• 2 puntos por plantear las ecuaciones de equilibrio
• 2 puntos por plantear que la proporci´on de d´ıas que se est´a en un estado calibrado es πCC + πDC
• 2 puntos por plantear que la cantidad de veces que la m´aquina se ”cae” cada 100 d´ıas es 100(πCC(0,25) +
πDC(0,50))
(c) (6 puntos) La m´aquina acaba de recuperarse: ayer estuvo descalibrada y hoy amaneci´o calibrada. ¿Cu´antos d´ıas en
promedio operar´a sin caerse, es decir, hasta el pr´oximo d´ıa descalibrada?
Soluci´on: El primer d´ıa descalibrada corresponde al primer arribo al estado CD: partiendo de un d´ıa calibrado, los
estados CC y DC s´olo transitan entre s´ı o caen a CD (nunca se alcanza DD antes que CD). Con esto, el sistema de
ecuaciones a resolver es:
E(T(CC, CD)) = 1 + 0,75 E(T(CC, CD))
E(T(DC, CD)) = 1 + 0,50 E(T(CC, CD))
Resolviendo el sistema de ecuaciones:
E(T(CC, CD)) = 4.
Y:
E(T(DC, CD)) = 1 + 0,50 · 4 = 3 d´ıas.
Distribuci´on de puntaje:
• 4 puntos por plantear las ecuaciones para obtener E(T(CC, CD))
• 2 puntos por calcular E(T(DC, CD))
6

(d) (6 puntos) Una falla en el sistema de control deterior´o la recuperaci´on: la probabilidad de mantenerse calibrada tras
reci´en haberse recuperado baja de 0,50 a 0,25 (las dem´as reglas no cambian). Bajo esta nueva condici´on, cada d´ıa
calibrada genera una utilidad de $210 y cada d´ıa descalibrada $0. Los due˜nos eval´uan dos inversiones excluyentes,
con su costo ya expresado como valor diario equivalente:
• Inversi´on 1 (nuevo controlador): sube de 0,75 a 0,875 la probabilidad de seguir calibrada tras una racha; costo
$6 por d´ıa.
• Inversi´on 2 (recalibrador autom´atico): sube de 0,25 a 0,75 la probabilidad de mantenerse tras reci´en recuperarse;
costo $24 por d´ıa.
¿Cu´al inversi´on conviene? Justifique s´olo bas´andose en la utilidad neta de largo plazo. Adem´as, asumiendo que el
costo diario de la opci´on elegida no cambia, ¿por debajo de qu´e costo diario de la opci´on no elegida cambiar´ıa de
decisi´on?
Soluci´on:
Tras la falla, resolviendo π = πP se obtiene π = (0,25; 0,25; 0,25; 0,25), luego Pr(C) = πCC + πDC = 0,5. Utilidad
sin invertir: 210 · 0,5 = $105/d´ıa.
Inversi´on 1: con la nueva matriz, π = (0,4; 0,2; 0,2; 0,2), Pr(C) = 0,6.
Utilidad bruta 210 · 0,6 = $126; neta
126 −6 = $120/d´ıa .
Inversi´on 2: π = (0,5; 1
6; 1
6; 1
6), Pr(C) = 0,5 + 1
6 = 2
3. Utilidad bruta 210 · 2
3 = $140; neta 140 −24 = $116/d´ıa .
Conviene la Inversi´on 1 ($120 > $116).
la Inversi´on 2 supera a la 1 cuando 140 −x > 120, es decir con costo diario x < $20. Hoy cuesta $24, por lo que no
conviene; bajo $20/d´ıa s´ı ser´ıa la mejor.
Distribuci´on de puntaje:
• 2 puntos por plantear el ahorro diario con inversi´on 1
• 2 puntos por plantear el ahorro diario con inversi´on 2
• 1 punto por plantear que la inversi´on 1 es m´as conveniente
• 1 punto por plantear el que la inversi´on 2 conviene cuando su costo es menor a $20/d´ıa
7

Problema 3 (18 puntos)
Una empresa de log´ıstica tiene una estaci´on interna de carga de combustible para su flota. La estaci´on cuenta con
un surtidor y espacio para un veh´ıculo en espera (capacidad total: 2 veh´ıculos). Los veh´ıculos llegan a cargar seg´un
un proceso de Poisson de tasa λ = 3 por hora y el tiempo de carga es exponencial de tasa µ = 3 por hora. Si un veh´ıculo
llega cuando la estaci´on est´a llena (ya hay 2 veh´ıculos), no puede esperar y debe ir a cargar a una bomba externa.
(a) (4 puntos) Modele la ocupaci´on de la estaci´on como una CMTC. Defina el espacio de estados, dibuje el diagrama
de transici´on e indique las tasas.
Soluci´on:
El estado es el n´umero de veh´ıculos en la estaci´on (cargando + esperando), S = {0, 1, 2}. Las llegadas
Poisson dan las subidas a tasa λ; el ´unico surtidor da las bajadas a tasa µ. En el estado 2 (lleno) una llegada no sube
el estado (se va a la bomba externa): no hay transici´on 2→3.
0
1
2
λ
µ
λ
µ
Distribuci´on de puntaje:
• 1 punto por plantear el espacio de estados
• 2 puntos por plantear las tasas de transici´on
• 1 punto por plantear el diagrama de transici´on
(b) (8 puntos) La bomba externa empez´o a cobrar un recargo por cada veh´ıculo que deba cargar all´ı, as´ı que interesa
reducir cu´antos veh´ıculos se van afuera. Por un mismo costo, la gerencia puede elegir solo uno de dos arreglos:
(A) reemplazar el surtidor por uno m´as eficiente, con un tiempo de carga de tasa tasa µ = 1, 2 por hora, manteniendo
1 espacio de espera;
(B) ampliar la espera a 2 veh´ıculos (capacidad total 3), manteniendo el surtidor original.
¿Cu´al arreglo se deber´ıa elegir para enviar menos veh´ıculos a la bomba externa? Justifique.
Soluci´on:
En el estado lleno los veh´ıculos siguen llegando a tasa λ, pero deben ir a la bomba externa. Como en el
largo plazo el sistema est´a lleno una fracci´on π2 del tiempo, el flujo de veh´ıculos enviados afuera es λ π2 por hora.
Para obtener π2 planteamos las ecuaciones de equilibrio de la CMTC y resolvemos. Situaci´on actual (estados 0, 1, 2).
Las ecuaciones de equilibrio son
λπ0 = µπ1,
λπ1 = µπ2,
y como λ = µ = 3 cada una da πn+1 = πn. Con π0 + π1 + π2 = 1, los tres estados quedan equiprobables: π2 = 1
3.
(A) Surtidor 20% m´as r´apido. La tasa de carga pasa a 1,2µ = 3,6. Las ecuaciones de equilibrio son
λπ0 = 1,2µ π1,
λπ1 = 1,2µ π2,
de donde π1 =
3
3,6π0 = 5
6π0 y π2 = 5
6π1 = 25
36π0.
8

Normalizando, π0
 1 + 5
6 + 25
36

= π0 · 91
36 = 1, luego π(A)
2
= 25
91.
(B) Espera ampliada (estados 0, 1, 2, 3). Las ecuaciones de equilibrio son
λπ0 = µπ1,
λπ1 = µπ2,
λπ2 = µπ3,
y con λ = µ = 3 los cuatro estados quedan equiprobables: π(B)
3
= 1
4.
Comparaci´on. Basta comparar π(A)
2
y π(B)
3
. Dado que π(A)
2
> π(B)
3
. Por lo tanto el arreglo (B), ampliar la
espera, env´ıa menos veh´ıculos afuera (25% frente a ≈27,5%)
Distribuci´on de puntaje:
• 3 puntos por calcular proporci´on de autos que se van a la estaci´on externa en escenario (A)
• 3 puntos por calcular proporci´on de autos que se van a la estaci´on externa en escenario (B)
• 2 puntos por plantear justificaci´on de qu´e arreglo es mejor
(c) (6 puntos) Suponga que la empresa no implement´o ninguno de los arreglos anteriores. En cambio, como compr´o
veh´ıculos di´esel, instal´o un segundo surtidor de di´esel y ampli´o la espera a 3 veh´ıculos (capacidad total 5: hasta
3 esperando y 2 cargando). El surtidor de di´esel tambi´en puede entregar combustible com´un. El 30% de los veh´ıculos
usa di´esel y el 70%, com´un. Reglas:
• Un veh´ıculo de combustible com´un puede usar el surtidor de di´esel s´olo si est´a al frente de la fila, el surtidor
com´un est´a ocupado y no hay ning´un veh´ıculo di´esel en la fila.
• Si hay alg´un veh´ıculo di´esel en la fila, este tiene prioridad para usar el surtidor de di´esel.
Modele la nueva situaci´on como una CMTC indicando claramente el espacio de estados y las tasas de transici´on.
Soluci´on:
Nota: El puntaje de esta pregunta no se considerar´a para el puntaje m´aximo de la interrogaci´on, quedando con 54
puntos para la nota m´axima
Definimos el espacio de estados de la siguiente forma:
X(t) = (a, b, d, c),
donde:
• a ∈{0, 1}: indica si el surtidor com´un est´a ocupado;
• b ∈{0, 1}: indica si el surtidor di´esel est´a ocupado;
• c ∈{0, 1, 2, 3}: n´umero de veh´ıculos di´esel en espera;
• d ∈{0, 1, 2, 3}: n´umero de veh´ıculos comunes en espera, con d + c ≤3.
• c s´olo puede tomar valores distintos a 0 cuando b = 1.
• d s´olo puede tomar valores distintos a 0 cuando a = b = 1
En cuanto a las tasas:
9

Llegada di´esel (tasa λD = 0,9).
(a, 0, 0, 0) −→(a, 1, 0, 0)
(ocupa el surtidor di´esel),
(a, 1, d, c) −→(a, 1, d + 1, c)
si d + c < 3.
Llegada com´un (tasa λC = 2,1).
(0, b, d, 0) −→(1, b, d, 0)
(ocupa el surtidor com´un),
(1, 0, 0, 0) −→(1, 1, 0, 0)
(ocupa el surtidor di´esel: com´un ocupado, di´esel libre, sin di´esel en fila),
(1, 1, d, c) −→(1, 1, d, c + 1)
si d + c < 3.
Fin de servicio en el surtidor com´un (tasa µ = 3, si a = 1).
(1, b, d, 0) −→(0, b, d, 0)
(no hay comunes esperando; los di´esel no pueden usarlo),
(1, 1, d, c) −→(1, 1, d, c −1)
si c ≥1 (entra el siguiente com´un).
Fin de servicio en el surtidor di´esel (tasa µ = 3, si b = 1).
(a, 1, 0, 0) −→(a, 0, 0, 0),
(a, 1, d, 0) −→(a, 1, d −1, 0)
si d ≥1 (entra el siguiente di´esel, por prioridad),
(1, 1, d, c) −→(1, 1, d −1, c)
si d ≥1,
(1, 1, 0, c) −→(1, 1, 0, c −1)
si c ≥1 (el com´un del frente ocupa el surtidor di´esel).
Tasas agregadas.
Hay dos casos en que transiciones distintas conducen al mismo estado y sus tasas se suman:
[itemsep=2pt]
• Desde (1, 0, 0, 0), tanto una llegada di´esel como una com´un llevan a (1, 1, 0, 0); la tasa de esa transici´on es
λD + λC = λ = 3.
• Desde (1, 1, 0, c) con c ≥1, ambos fines de servicio llevan a (1, 1, 0, c −1): al liberarse el surtidor com´un entra el
siguiente com´un y, al liberarse el di´esel, el com´un del frente lo ocupa. La tasa de esa transici´on es 2µ = 6.
Distribuci´on de puntaje:
• 3 puntos por definir el espacio de estados
• 3 punto por definir las tasas de transici´on
10

