Pontificia Universidad Cat´olica de Chile
Escuela de Ingenier´ıa
Departamento de Ingenier´ıa Industrial y de Sistemas
ICS2123 – Modelos Estoc´asticos
Profesores Ver´onica Godoy y Andr´es Navarro
Ayudante Jefe Joaqu´ın Vergara
Primer Semestre 2026
Tarea 1:
Repaso de Probabilidades y Proceso de Poisson
Instrucciones
⋄Esta tarea debe ser realizada individualmente o en parejas (pueden ser de diferentes secciones
dentro de las que son coordinadas). Deben indicar en la primera plana del PDF los nombres de los/as
integrantes, junto con las secciones respectivas de c/u.
⋄Tienen plazo hasta el 09 de abril de 2026 para entregar sus soluciones.
⋄Deben entregar un archivo reporte, en formato PDF. En el archivo PDF deben entregar sus res-
puestas de los 4 problemas. Los c´odigos implementados deben adjuntarse aparte en el buz´on. En
caso de no cumplir con esto, se aplicar´a un descuento de 5 d´ecimas sobre la nota final de la tarea.
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
⋄Las preguntas se har´an a trav´es del foro de discusi´on asociado a la Tarea 1 en Canvas, por lo que les
pedimos que NO manden dudas por mail sobre la tarea. De esta manera, todos tienen acceso a las
respuestas.
⋄Seremos estrictos en que no se aceptar´an env´ıos por mail. Evite problemas de internet, del sistema
Canvas, de la calidad de la foto o cualquier otro que pudiese ocurrir al entregar sobre la hora. El/La
alumno/a que env´ıe su tarea despu´es de la hora l´ımite, tendr´a nota 1.0.
1

Problema 1 (15 puntos)
(a) Sea {Xi}i∈N una colecci´on i.i.d. de VAs, y sea Sn = X1 + · · · + Xn. Calcule E[Sn|X1] y E[X1|Sn].
Soluci´on: Sea,
E[Sn | X1] = E
"
X1 +
n
X
i=2
Xi
 X1
#
(Linealidad de la esperanza condicional)
= E[X1 | X1] +
n
X
i=2
E[Xi | X1]
(∗)
= X1 +
n
X
i=2
E[Xi]
({Xi}i i.i.d.)
= X1 +
n
X
i=2
E[X1]
= X1 + (n −1)E[X1]
donde en (∗) ocupamos que, al condicionar sobre X1, asumimos su valor como una constante conocida
(luego E[X1 | X1] = X1), y que Xi es independiente de X1 para todo i = 2, . . . , n (luego E[Xi | X1] =
E[Xi]).
Ahora calculemos E[X1 | Sn]. Primero notemos que
E[Xi | Sn] = E[Xj | Sn],
∀i ̸= j.
En efecto, como X1, . . . , Xn son i.i.d., para cualquier x y s se tiene
P(Xi = x, Sn = s) = P

Xi = x,
X
k̸=i
Xk = s −x

= P(Xi = x) P

X
k̸=i
Xk = s −x

.
An´alogamente,
P(Xj = x, Sn = s) = P(Xj = x) P

X
k̸=j
Xk = s −x

.
Como las variables son id´enticamente distribuidas, P(Xi = x) = P(Xj = x), y como las variables son
independientes, las sumas P
k̸=i Xk y P
k̸=j Xk tienen la misma distribuci´on. Por lo tanto
P(Xi = x, Sn = s) = P(Xj = x, Sn = s).
Dividiendo por P(Sn = s) obtenemos
P(Xi = x | Sn = s) = P(Xj = x | Sn = s),
lo que implica que Xi y Xj tienen la misma distribuci´on condicional dado Sn, y en consecuencia
E[Xi | Sn] = E[Xj | Sn].
Llamando a esta propiedad (∗∗), notemos que:
Sn = E[Sn | Sn]
= E
" n
X
i=1
Xi
 Sn
#
(Linealidad de la E condicional)
=
n
X
i=1
E[Xi | Sn]
(∗∗)
=
n
X
i=1
E[X1 | Sn]
2

= nE[X1 | Sn]
De esto sigue que E[X1 | Sn] = Sn/n.
Distribuci´on de Puntaje:
⋄(2 puntos) C´alculo correcto de E[Sn | X1].
⋄(1 punto) Uso de simetr´ıa: E[Xi | Sn] = E[X1 | Sn].
⋄(2 puntos) Concluir E[X1 | Sn] = Sn/n usando linealidad.
(b) Sean X, Y dos variables aleatorias independientes de distribuci´on Bernoulli(p), con p ∈[0, 1]. Sea
Z = 1X+Y =0. Calcule E[X|Z], E[Y |Z]. ¿Son independientes? Justifique.
Soluci´on: Notemos primero que Z = 1 si y solo si X = 0 e Y = 0. Por independencia de X e Y , se
tiene P(Z = 1) = (1 −p)2 y P(Z = 0) = p(2 −p).
Para calcular E[X|Z], evaluamos sobre el soporte de Z:
⋄Si Z = 1, entonces X = 0 con probabilidad 1, luego E[X|Z = 1] = 0.
⋄Si Z = 0, por definici´on de esperanza condicional:
E[X|Z = 0] = P(X = 1, Z = 0)
P(Z = 0)
= P(X = 1)
P(Z = 0) =
p
p(2 −p) =
1
2 −p
Luego, obtenemos que E[X|Z] = 1−Z
2−p . Por simetr´ıa en la construcci´on de Z respecto a X e Y , se
sigue que E[Y |Z] = E[X|Z] = 1−Z
2−p .
Sean W1 = E[X|Z] y W2 = E[Y |Z]. Para p ∈(0, 1), la variable Z es no degenerada (Var(Z) > 0), lo
que implica que W1 y W2 tampoco son constantes. Dado que W1 = W2, su covarianza resulta:
Cov(W1, W2) = Var(W1) = Var
1 −Z
2 −p

= Var(Z)
(2 −p)2 > 0.
Puesto que una covarianza no nula implica dependencia, concluimos que E[X|Z] e E[Y |Z] no son
independientes
Distribuci´on de Puntaje:
⋄(2 puntos) Por obtener correctamente E[X|Z].
⋄(1 punto) Por obtener correctamente E[Y |Z].
⋄(2 puntos) Por concluir que no son independientes.
(c) Considere un avi´on con n ≥2 asientos y una fila de n pasajeros debidamente numerados. El primer
pasajero ha extraviado su tarjeta de embarque y, al entrar, selecciona un asiento uniformemente al
azar entre los n disponibles. Los pasajeros restantes (k = 2, . . . , n) act´uan de la siguiente forma: si su
asiento asignado est´a libre, lo ocupan; de lo contrario, eligen un asiento uniformemente al azar entre
los asientos vac´ıos en ese momento.
(i)
Demuestre por inducci´on que la probabilidad de que el pasajero k ocupe su asiento asignado es:
P(Ak) = n −k + 1
n −k + 2,
∀k ∈{2, . . . , n}.
Soluci´on: Sean los eventos
⋄Ak: el pasajero k ocupa su asiento asignado
⋄Im: el primer pasajero se sienta en el asiento m
Notemos que P(Im) = 1/n para todo m ∈{1, . . . , n}. Procederemos por inducci´on sobre k.
Caso base (k = 2): Por la ley de probabilidad total sobre el asiento elegido por el primer
pasajero:
P(A2) =
n
X
m=1
P(A2|Im)P(Im).
3

Si m = 1, el asiento 2 est´a libre. Si m = 2, est´a ocupado. Si m > 2, el pasajero 2 encuentra su
asiento libre pues el pasajero 1 eligi´o un asiento con ´ındice superior. As´ı:
P(A2) = 1
n [1 · 1 + 0 · 1 + 1 · (n −2)] = n −1
n
.
La f´ormula propuesta entrega n−2+1
n−2+2 = n−1
n , verific´andose el caso base.
Paso inductivo: Supongamos que para un k < n fijo se cumple P(Ak) = n−k+1
n−k+2. Consideremos
el pasajero k + 1 y condicionemos sobre la elecci´on del primer pasajero:
⋄Si m = 1, todos los pasajeros posteriores encuentran su asiento libre; P(Ak+1|I1) = 1.
⋄Si m = k + 1, el asiento est´a ocupado por el pasajero 1; P(Ak+1|Ik+1) = 0.
⋄Si m > k + 1, el pasajero k + 1 encontrar´a su asiento libre; P(Ak+1|Im) = 1.
⋄Si 2 ≤m ≤k, la entrada del pasajero m a un asiento ocupado reinicia el proceso como si ´el
fuese el primer pasajero en un sistema de n−m+1 asientos totales. Por hip´otesis inductiva,
la probabilidad es (n−m+1)−(k+1−m+1)+1
(n−m+1)−(k+1−m+1)+2 = n−k+1
n−k+2.
Aplicando la ley de probabilidad total:
P(Ak+1) = 1
n
"
1 + 0 + (n −k −1) +
k
X
m=2
n −k + 1
n −k + 2
#
P(Ak+1) = 1
n

n −k + (k −1)n −k + 1
n −k + 2

.
Tras simplificar la expresi´on, se obtiene:
P(Ak+1) = 1
n
(n −k)(n −k + 2) + (k −1)(n −k + 1)
n −k + 2

=
n −k
n −k + 1.
Esto completa el paso inductivo.
Distribuci´on de Puntaje:
⋄(1 punto) Por planteamiento del caso base.
⋄(2 puntos) Por desarrollo correcto paso inductivo.
⋄(1 punto) Por llegar al resultado correcto.
(ii)
Determine la probabilidad de que el ´ultimo pasajero en abordar se siente en el asiento que le
correspond´ıa.
Soluci´on: Para el ´ultimo pasajero (k = n), sustituyendo en la expresi´on general obtenida:
P(An) = n −n + 1
n −n + 2 = 1
2
Distribuci´on de Puntaje:
⋄(1 punto) Por reemplazar en la expresi´on obtenida anteriormente.
4

Problema 2 (15 puntos)
(a) Un sensor de alta precisi´on detecta el impacto de part´ıculas provenientes de una fuente radiactiva.
Se modela el arribo de las part´ıculas mediante un proceso de Poisson con tasa λ part´ıculas por
minuto. Suponga que se registra un total de tres impactos durante el primer intervalo de observaci´on
de longitud r minutos. Dada esta informaci´on, determine la funci´on de densidad de probabilidades
del instante en que ocurri´o el primer impacto. Adicionalmente, determine la probabilidad de que la
primera part´ıcula haya impactado el sensor dentro de los primeros 2 minutos para r = 10.
Soluci´on: Sea N(t) el proceso de Poisson de tasa λ que contabiliza los impactos de las part´ıculas,
S1 el instante del primer arribo y U1, U2, U3 ∼Uniforme(0, r). Buscamos la distribuci´on de Z := S1 |
N(r) = 3. Para t ∈[0, r],
FZ(t) = P(m´ın{U1, U2, U3} ≤t)
= 1 −P(U1 > t, U2 > t, U3 > t)
= 1 −(P(U1 > t))3
= 1 −

1 −t
r
3
Luego,
fZ(t) = d
dt
"
1 −

1 −t
r
3#
= −3

1 −t
r
2
·

−1
r

= 3
r

1 −t
r
2
,
t ∈[0, r]
Finalmente, para r = 10 y t = 2, calculamos la probabilidad de que el primer impacto ocurra en los
primeros 2 minutos:
P(Z ≤2) = 1 −

1 −2
10
3
= 1 −(0.8)3
= 1 −0.512
= 0.488
Distribuci´on de Puntaje:
⋄(2 puntos) Por obtener correctamente FZ(t)
⋄(2 puntos) Por obtener correctamente fz(t)
⋄(1 punto) Por obtener el resultado correcto
(b) Considere ahora un segundo periodo de observaci´on que comienza inmediatamente despu´es de concluir
el primero. Sea Ti el instante del i-´esimo impacto medido desde el inicio de esta segunda etapa. Si
se sabe que el primer impacto ocurri´o despu´es de r minutos, determine la funci´on de densidad de
probabilidad del instante en que ocurre el tercer impacto.
Soluci´on:
Sea {Tn}n≥1 la secuencia de tiempos de arribo del proceso de Poisson de tasa λ en el
segundo intervalo. Sabemos que T3 = X1+X2+X3, donde Xi ∼Exp(λ) son los tiempos entre arribos,
independientes e id´enticamente distribuidos. Se busca la densidad de T3 dado el evento {T1 > r}.
Por la propiedad de p´erdida de memoria de la distribuci´on exponencial, el tiempo de espera hasta el
primer impacto dado que este no ha ocurrido en el intervalo [0, r] se puede expresar como T1 = r+X′
1,
donde X′
1 ∼Exp(λ). En consecuencia, la variable condicionada resulta:
T3 | T1 > r ∼r + X′
1 + X2 + X3.
Definimos W = X′
1 + X2 + X3. Al ser la suma de tres variables aleatorias i.i.d. con distribuci´on
Exp(λ), W sigue una distribuci´on Gamma con par´ametros n = 3 y λ, cuya densidad es:
fW (w) = λ3w2e−λw
2!
,
w > 0.
5

Realizando el cambio de variable t = r + w, la funci´on de densidad de probabilidad para T3 condicio-
nado a T1 > r es una traslaci´on de la densidad de W:
fT3|T1>r(t) = fW (t −r) = λ3(t −r)2e−λ(t−r)
2
,
para t > r.
Para t ≤r, la densidad es nula, pues el evento {T1 > r} implica necesariamente que {T3 > r}.
Distribuci´on de Puntaje:
⋄(2 puntos) Por obtener la variable condicionada correctamente
⋄(2 puntos) Por obtener correctamente fW (w)
⋄(1 punto) Por obtener correctamente fT3|T1>r(t)
(c) Suponga ahora que el sensor opera en un r´egimen de baja intensidad con una tasa de λ = 0.1 part´ıculas
por d´ıa. Se ha observado que cada part´ıcula, al impactar el sensor, genera un n´umero aleatorio
de se˜nales el´ectricas secundarias Yi, las cuales siguen una distribuci´on Binomial(n = 4, p = 0.05).
Asumiendo independencia entre los impactos y las se˜nales generadas, determine el valor esperado
del n´umero total de se˜nales el´ectricas registradas tras un mes de operaci´on (30 d´ıas). De manera
complementaria, calcule la probabilidad de que al cabo de un mes de operaci´on (30 d´ıas) no se haya
registrado ninguna se˜nal secundaria.
Soluci´on:
Sean N(t) el n´umero de impactos de part´ıculas en el intervalo [0, t] e S(t) el n´umero de se˜nales
el´ectricas secundarias acumuladas hasta el d´ıa t ∈{1, . . . , 30}. Luego,
Y (t) =
N(t)
X
i=1
Yi
El valor esperado de un proceso de Poisson es igual al producto de la tasa de ocurrencia promedio y
el tama˜no promedio de cada ocurrencia. Entonces,
E[S(30)] = E[Yi] · E[N(30)]
donde E[N] es el n´umero esperado de impactos de part´ıculas en 30 d´ıas y E[Yi] es el n´umero esperado
de n´umero de se˜nales el´ectricas secundarias generadas por cada impacto. Utilizando las f´ormulas para
la esperanza de una distribuci´on de Poisson y una distribuci´on binomial, respectivamente, tenemos:
E[N(30)] = λ · 30
= 0.1 · 30
= 3
E[Ci] = n · p
= 4 · 0.05
= 0.2
Por lo tanto, la estimaci´on del valor esperado ddel n´umero total de se˜nales el´ectricas registradas tras
un mes de operaci´on es de E[Y (30)] = 3 · 0.2 = 0.6.
Ahora nos interesa calcular P(S(30) = 0). Note que S(30) = 0 si y solo si cada una de las N(30)
part´ıculas registradas genera exactamente cero se˜nales. Sea q = P(Yi = 0) la probabilidad de que un
impacto no genere se˜nales. Dado que Yi ∼Binomial(4, 0.05), tenemos:
q = (1 −0.05)4 = 0.954.
Utilizando la ley de probabilidad total y condicionando sobre el n´umero de impactos N(30), se tiene:
P(S(30) = 0) =
∞
X
k=0
P(S(30) = 0 | N(30) = k)P(N(30) = k)
6

=
∞
X
k=0
qk e−30λ(30λ)k
k!
= e−30λ
∞
X
k=0
(30λq)k
k!
= e−30λe30λq = e−30λ(1−q).
Sustituyendo los valores λ = 0.1 y q = 0.954:
P(S(30) = 0) = e−3(1−0.954)
Distribuci´on de Puntaje:
⋄(2 puntos) Por obtener E[Y (30)]
⋄(1 punto) Por obtener q
⋄(2 puntos) Por obtener correctamente P(S(30) = 0)
7

Problema 3 (15 puntos)
Las ´ordenes que llegan a una plataforma digital de inversiones pueden dividirse en 3 grupos: ´ordenes de
inversionistas minoristas, ´ordenes de inversionistas profesionales y ´ordenes de inversionistas institucionales.
Cada grupo env´ıa ´ordenes seg´un un proceso de Poisson, donde las ´ordenes de inversionistas minoristas llegan
con tasa λ, las de inversionistas profesionales con tasa α y las de inversionistas institucionales con tasa β
(todas las tasas en ´ordenes por hora, respectivamente). Todos los procesos de llegada son independientes
entre s´ı. Considere que la plataforma funciona las 24 horas del d´ıa y que los procesos reinician cada d´ıa a
las 0:00 horas.
Dependiendo del tipo de orden, estas pueden requerir distintos niveles de procesamiento dentro de la
plataforma. Las ´ordenes de inversionistas minoristas utilizan un sistema avanzado de validaci´on con una
probabilidad de 0.3; tambi´en con 0.3 utilizan un sistema est´andar de ejecuci´on y con 0.4 no requieren
intervenci´on adicional (son procesadas autom´aticamente por el motor de matching). Para el caso de los
inversionistas profesionales, con 0.4 de probabilidad utilizan el sistema est´andar de ejecuci´on, con 0.1 el
sistema avanzado de validaci´on y con 0.5 se procesan autom´aticamente. Finalmente, para el caso de los
inversionistas institucionales, estos utilizan con 0.5 de probabilidad el sistema avanzado de validaci´on, con
0.3 el sistema est´andar y con 0.2 se procesan autom´aticamente.
Por otra parte, cada orden que llega puede ser seleccionada con probabilidad p (0 < p < 1) para realizar
una revisi´on adicional de cumplimiento regulatorio y gesti´on de riesgo antes de su ejecuci´on, mientras que
el resto no debe hacerlo.
Finalmente, los analistas de riesgo monitorean peri´odicamente algunas ´ordenes en proceso y el tiempo
que toman en cada revisi´on distribuye Uniforme(0.2,0.5), distribuci´on continua en horas. Este tiempo es
independiente de los procesos de llegada.
(a) ¿Cu´al es la probabilidad de que un d´ıa a las 12:00 hayan llegado 75 ´ordenes que necesiten procesa-
miento adicional (est´andar o avanzado), si se sabe que hasta las 12:00 han llegado 40 o m´as ´ordenes
institucionales que necesitaban validaci´on avanzada?
Soluci´on: Definimos los procesos:
⋄{N P (t), t ≥0} como el n´umero de ´ordenes que requieren procesamiento adicional (sistema
est´andar o validaci´on avanzada) en [0, t). Este es un proceso Poisson con tasa λ · 0.6 + α · 0.5 +
β · 0.8 = λ1.
⋄{N IA(t), t ≥0} como el n´umero de ´ordenes de inversionistas institucionales que requieren vali-
daci´on avanzada en [0, t). Este es un proceso Poisson con tasa β · 0.5 = λ2.
⋄{N R(t), t ≥0} como el n´umero de ´ordenes que requieren procesamiento adicional en [0, t),
excepto las ´ordenes institucionales que requieren validaci´on avanzada. Este es un proceso Poisson
con tasa λ · 0.6 + α · 0.5 + β · 0.3 = λ3.
Nos piden
P(N P (12 : 00) = 75 | N IA(12 : 00) ≥40)
⋄Forma 1: Ocupando la definici´on de probabilidad condicional,
= P(N P (12) = 75, N IA(12) ≥40)
P(N IA(12) ≥40)
=
P∞
i=40 P(N P (12) = 75, N IA(12) = i)
P(N IA(12) ≥40)
· P(N IA(12) = i)
P(N IA(12) = i)
=
P∞
i=40 P(N P (12) = 75 | N IA(12) = i) · P(N IA(12) = i)
P(N IA(12) ≥40)
=
P∞
i=40 P(N R(12) + N IA(12) = 75 | N IA(12) = i) · P(N IA(12) = i)
P(N IA(12) ≥40)
=
75
X
i=40
P(N R(12) = 75 −i) · P(N IA(12) = i) ·
1
P(N IA(12) ≥40)
=
75
X
i=40
(12λ3)75−i · e−12λ3
(75 −i)!
· (12λ2)i · e−12λ2
i!
·
1
P∞
j=40
(12λ2)j·e−12λ2
j!
8

⋄Forma 2: Utilizando el Teorema de Bayes,
P(N P (12 : 00) = 75 | N IA(12 : 00) ≥40) = P(N IA(12) ≥40 | N P (12) = 75) · P(N P (12) = 75)
P(N IA(12) ≥40)
=
∞
X
i=40
P(N IA(12) = i | N P (12) = 75) · P(N P (12) = 75)
P(N IA(12) ≥40)
Sabemos que
N P (t) = N R(t) + N IA(t)
⇒
N IA(t) = N P (t) −N R(t)
∀t ≥0
Luego, la probabilidad pedida es igual a,
=
∞
X
i=40
P(N P (12) −N R(12) = i | N P (12) = 75) · P(N P (12) = 75)
P(N IA(12) ≥40)
=
75
X
i=40
P(N R(12) = 75 −i) · P(N P (12) = 75) ·
1
P(N IA(12) ≥40)
=
75
X
i=40
(12λ3)75−i · e−12λ3
(75 −i)!
· (12λ1)75 · e−12λ1
75!
·
1
P∞
j=40
(12λ2)j·e−12λ2
j!
Distribuci´on de Puntaje:
⋄(1.5 puntos) Por la definici´on de los procesos con las tasas correctas. 0.5 cada uno.
⋄(0.5 puntos) Por el correcto planteamiento de la la probabilidad pedida.
⋄(1 punto) Por aplicar correctamente la definici´on de probabilidad condicional o Bayes
⋄(0.5 puntos) Por expresar la probabilidad como la suma de los casos sobre el N IA.
⋄(0.5 puntos) Por aplicar correctamente la relaci´on N P = N IA +N R ,aplicando correctamente
la sumatoria sobre i desde 40 a 75.
⋄(1 punto) Por llegar a la expresi´on correcta.
(b) Un inversionista profesional env´ıa una orden a las 16:00 y un operador le dice que hasta el momento
han realizado la revisi´on de cumplimiento a 150 ´ordenes profesionales ese d´ıa. ¿Cu´al es el n´umero
esperado de ´ordenes que se tuvieron que hacer la revisi´on desde el inicio del d´ıa y las 16:00?
Soluci´on: Se define,
⋄{N P R(t), t ≥0} como el n´umero de ´ordenes de inversionistas profesionales que han sido selec-
cionadas para revisi´on de cumplimiento en el intervalo [0, t). Este es un proceso Poisson con tasa
αp.
⋄{N OR(t), t ≥0} como el n´umero de ´ordenes de inversionistas minoristas o institucionales que
han sido seleccionadas para revisi´on de cumplimiento en [0, t). Este es un proceso Poisson con
tasa (λ + β)p.
⋄{N R(t), t ≥0} como el n´umero total de ´ordenes que han sido seleccionadas para revisi´on de
cumplimiento en [0, t). Este es un proceso Poisson con tasa (λ + α + β)p.
Notemos que, por construcci´on,
N R(t) = N P R(t) + N OR(t)
para todo t ≥0, y que ambos procesos son independientes.
Se nos pide calcular
E
 N R(16 : 00) | N P R(16 : 00) = 150

Utilizando la descomposici´on anterior,
E
 N R(16) | N P R(16) = 150

= E
 N P R(16) + N OR(16) | N P R(16) = 150

9

Aplicando la linealidad de la esperanza condicional,
= E
 N P R(16) | N P R(16) = 150

+ E
 N OR(16) | N P R(16) = 150

El primer t´ermino es inmediato,
E
 N P R(16) | N P R(16) = 150

= 150
Por otra parte, dado que los procesos N P R y N OR son independientes, se tiene
E
 N OR(16) | N P R(16) = 150

= E
 N OR(16)

Como N OR(t) es un proceso Poisson con tasa (λ + β)p, se sigue que
E
 N OR(16)

= 16(λ + β)p
Por lo tanto,
E
 N R(16 : 00) | N P R(16 : 00) = 150

= 150 + 16(λ + β)p
Distribuci´on de Puntaje:
⋄(1.5 puntos) Por la definici´on de los procesos con las tasas correctas. 0.5 cada uno.
⋄(0.5 puntos) Por el correcto planteamiento de la probabilidad pedida.
⋄(0.5 puntos) Por plantear correctamente la relaci´on entre los procesos.
⋄(1 punto) Por aplicar correctamente propiedad de linealidad de la esperanza condicional.
⋄(1 punto)
Por reconocer que los procesos son independientes aplicar correctamente en la
expresi´on condicional.
⋄(0.5 puntos) Por llegar a la expresi´on correcta.
(c) ¿Cu´al es la probabilidad de que durante la revisi´on de un analista a una orden, a la plataforma hayan
llegado m´as de 20 ´ordenes minoristas, m´as de 30 ´ordenes profesionales que se procesan autom´atica-
mente y menos de 35 ´ordenes institucionales que requieren alg´un tipo de procesamiento adicional?
Soluci´on:
Sea V la duraci´on de la revisi´on que realiza un analista a una orden. Seg´un el enunciado,
V ∼Uniforme(0.2, 0.5)
Definimos los siguientes procesos de llegada:
⋄{N M(t), t ≥0} como el n´umero de ´ordenes de inversionistas minoristas que llegan a la plataforma
en el intervalo [0, t). Este es un proceso Poisson con tasa λ.
⋄{N P A(t), t ≥0} como el n´umero de ´ordenes de inversionistas profesionales que se procesan
autom´aticamente en [0, t). Dado que este tipo de ´ordenes ocurre con probabilidad 0.5, este
proceso es Poisson con tasa 0.5α.
⋄{N IP (t), t ≥0} como el n´umero de ´ordenes de inversionistas institucionales que requieren alg´un
tipo de procesamiento adicional (est´andar o avanzado) en [0, t). Dado que estas ocurren con
probabilidad 0.8, este proceso es Poisson con tasa 0.8β.
Se desea calcular
P(N M(V ) > 20, N P A(V ) > 30, N IP (V ) < 35)
Utilizando la ley de probabilidades totales respecto de la variable aleatoria V , se obtiene
P(N M(V ) > 20, N P A(V ) > 30, N IP (V ) < 35)
10

=
Z 0.5
0.2
P(N M(V ) ≥21, N P A(V ) ≥31, N IP (V ) ≤34 | V = v) fV (v) dv
Dado que V es independiente de los procesos de llegada,
=
Z 0.5
0.2
P(N M(v) ≥21, N P A(v) ≥31, N IP (v) ≤34) fV (v) dv
Como V ∼Uniforme(0.2, 0.5), su densidad es
fV (v) = 1
0.3,
0.2 ≤v ≤0.5
Por lo tanto,
=
Z 0.5
0.2
P(N M(v) ≥21, N P A(v) ≥31, N IP (v) ≤34) · 1
0.3 dv
Por independencia de los procesos de llegada,
=
Z 0.5
0.2
P(N M(v) ≥21)P(N P A(v) ≥31)P(N IP (v) ≤34) · 1
0.3 dv
Finalmente, utilizando la distribuci´on Poisson de cada proceso,
=
Z 0.5
0.2
 ∞
X
i=21
(λv)ie−λv
i!
! 

∞
X
j=31
(0.5αv)je−0.5αv
j!


 34
X
k=0
(0.8βv)ke−0.8βv
k!
!
1
0.3 dv
Distribuci´on de Puntaje:
⋄(1.5 puntos) Por la definici´on de los procesos con las tasas correctas. 0.5 cada uno.
⋄(1 punto) Por planteamiento de la probabilidad haciendo uso de la ley de probabilidades totales
⋄(1 punto) Por el correcto planteamiento de la probabilidad pedida como una integral
⋄(0.5 puntos) Por escribir correctamente la funci´on de densidad de V .
⋄(0.5 puntos) Por aplicar independencia de procesos correctamente.
⋄(0.5 puntos) Por llegar a la expresi´on correcta.
11

Problema 4 (15 puntos)
Considere una marat´on que comienza a las 8:00 y finaliza a las 12:00. A medida que avanza la carrera, los
corredores se van separando naturalmente en grupos de acuerdo con su velocidad y capacidad atl´etica.
Sea P un punto fijo del recorrido y sea N(t) la cantidad de corredores que han pasado por dicho punto
hasta el tiempo t (medido en minutos desde las 8:00). Se modela {N(t), t ≥0} como un proceso de Poisson
no homog´eneo con tasa de llegada λ(t).
Durante la primera hora de la carrera (de 8:00 a 9:00), la tasa de corredores que pasa por el punto P
aumenta linealmente desde 0 hasta A personas por minuto. A partir de ese momento y hasta el final de la
carrera, la tasa de llegadas se modela como
λ(t) = A + β sin
2π
30 t

,
donde t est´a medido en minutos y se cumple que A > β.
Bajo este modelo, responda las siguientes preguntas:
(a) Grafique la funci´on de tasa λ(t) y calcule el n´umero esperado de corredores que pasan por el punto
P durante las cuatro horas de carrera.
Soluci´on: El gr´afico es el siguiente,
La media en la primera hora es A
2 . Como la parte de la sinusoide tiene ciclos completos, su media es
A. Luego,
¯λ = 1
4 · A
2 + 3
4 · A = 7
8A
Alternativamente, se puede calcular
¯λ =
R 60
0
A
60 · tdt +
R 240
60
 A + β sin
  1
30 · 2πt

dt
240
=
A
60 · 602
2 +
 (240 −60) · A + β · 30
2π ·
 cos
  1
30 · 2π · 240

−cos
  1
30 · 2π · 60

240
= A
8 + 3
4A + 0
= 7
8A
12

Distribuci´on de Puntaje:
⋄(2 puntos) Gr´afico correcto de λ(t)
⋄(1 punto) Planteamiento correcto del n´umero esperado
⋄(2 puntos) C´alculo y resultado correcto del n´umero esperado
(b) Calcule la probabilidad de que a mitad de la carrera (a las 10:00) hayan pasado menos de 150 personas
por el punto P, sabiendo que entre las 9:30 y las 10:15 pasaron 200 corredores.
Soluci´on: Fijemos t = 0 a las 8:00. Nos piden:
P(N(120) ≤149|N(135) −N(90) = 200)
Para el desarrollo, resulta ´util visualizar la situaci´on. Tomando i ≤149, j ≤i, tenemos:
0
90
120
135
200
i-j
j
200 - j
i
La probabilidad anterior es equivalente a:
149
X
i=0
P(N(120) = i|N(135) −N(90) = 200)
=
149
X
i=0
P(N(120) = i, N(135) −N(90) = 200)
P(N(135) −N(90) = 200)
=
149
X
i=0
i
X
j=0
P(N(90) = i −j, N(120) −N(90) = j, N(135) −N(120) = 200 −j)
P(N(135) −N(90) = 200)
i.i.
=
149
X
i=0
i
X
j=0
P(N(90) = i −j)P(N(120) −N(90) = j)P(N(135) −N(120) = 200 −j)
P(N(135) −N(90) = 200)
Ahora debemos calcular cada t´ermino por separado. Para esto, necesitamos m(90), m(120) y m(135).
m(90) =
Z 60
0
A
60t · dt +
Z 90
60

A + β sin
 1
30 · 2πt

dt
= 1
2
A
60t2|60
0 + (At −β 30
2π cos( 1
30 · 2πt))|90
60
= 30A + 30A −β 30
2π (cos( 1
30 · 2π · 90) −cos( 1
30 · 2π · 60))
= 60A −β 30
2π (1 −1) = 60A
m(120) =
Z 60
0
A
60t · dt +
Z 120
60

A + β sin
 1
30 · 2πt

dt
= 30A + 60A −β 30
2π (cos( 1
30 · 2π · 120) −cos( 1
30 · 2π · 60))
= 90A −β 30
2π (1 −1) = 90A
m(135) =
Z 60
0
A
60t · dt +
Z 135
60

A + β sin
 1
30 · 2πt

dt
= 30A + 75A −β 30
2π (cos( 1
30 · 2π · 135) −cos( 1
30 · 2π · 60))
= 105A −β 30
2π (−1 −1) = 105A + 30
π β
13

Luego, tenemos que:
P(N(90) = i −j) = (60A)i−j · e−60A
(i −j)!
P(N(120) −N(90) = j) = (m(120) −m(90))j · e−(m(120)−m(90))
j!
= (30A)j · e−30A
j!
P(N(135) −N(120) = 200 −j) = (m(135) −m(120))200−j · e−(m(135)−m(120))
(200 −j)!
= (15A + 30
π β)200−j · e−(15A+ 30
π β)
(200 −j)!
P(N(135) −N(90) = 200) = (m(135) −m(90))200 · e−(m(135)−m(90))
200!
= (45A + 30
π β)200 · e−(45A+ 30
π β)
200!
Uniendo todo, obtenemos:
P(N(120) ≤149|N(135) −N(90) = 200) =
149
X
i=0
i
X
j=0
(60A)i−j · e−60A
(i −j)!
· (30A)j · e−30A
j!
· (15A + 30
π β)200−j · e−(15A+ 30
π β)
(200 −j)!
·
 
(45A + 30
π β)200 · e−(45A+ 30
π β)
200!
!−1
Distribuci´on de Puntaje:
⋄(1 punto) Planteamiento correcto de probabilidad condicional
⋄(1 punto) Correcta descomposici´on por incrementos independientes
⋄(1.5 puntos) C´alculo correcto de m(90), m(120) y m(135)
⋄(1.5 puntos) Expresi´on final correcta
(c) Sabiendo que entre las 10:00 y las 12:00 pasaron 500 o m´as corredores por el punto P, calcule la
probabilidad de que en toda la carrera hayan pasado 800 o m´as corredores por dicho punto.
Soluci´on: Nos piden:
P(N(240) ≥800|N(240) −N(120) ≥500)
Vi´endolo gr´aficamente, podemos descomponer el problema de la siguiente forma:
0
120
240
j
i-j
i
Luego, la probabilidad enunciada es equivalente a:
∞
X
i=800
P(N(240) = i|N(240) −N(120) ≥500)
=
∞
X
i=800
P(N(240) = i, N(240) −N(120) ≥500)
P(N(240) −N(120) ≥500)
=
∞
X
i=800
i
X
j=500
P(N(240) = i, N(240) −N(120) = j)
P(N(240) −N(120) ≥500)
=
∞
X
i=800
i
X
j=500
P(N(120) = i −j, N(240) −N(120) = j)
P(N(240) −N(120) ≥500)
14

i.i.
=
∞
X
i=800
i
X
j=500
P(N(120) = i −j)P(N(240) −N(120) = j)
P(N(240) −N(120) ≥500)
Calculamos las tasas que necesitamos:
m(120) = 90A
m(240) =
Z 60
0
A
60t · dt +
Z 240
60

A + β sin
 1
30 · 2πt

dt
= 30A + 180A −β 30
2π (cos( 1
30 · 2π · 240) −cos( 1
30 · 2π · 60))
= 210A −β 30
2π (1 −1) = 210A
Con esto, tenemos que:
P(N(120) = i −j) = (90A)i−j · e−90A
(i −j)!
P(N(240) −N(120) = j) = (m(240) −m(120))j · e−(m(240)−m(120))
j!
= (120A)j · e−120A
j!
Uniendo todo, obtenemos:
∞
X
i=800
i
X
j=500
(90A)i−j · e−90A
(i −j)!
· (120A)j · e−120A
j!
·
 
∞
X
k=500
(120A)k · e−120A
k!
!−1
Distribuci´on de Puntaje:
⋄(1 punto) Planteamiento correcto del evento
⋄(1 punto) Correcta descomposici´on por incrementos independientes
⋄(2 puntos) C´alculo correcto de m(120) y m(240)
⋄(1 punto) Expresi´on final correcta
15

