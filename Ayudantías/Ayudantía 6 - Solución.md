Pontificia Universidad Cat´olica de Chile
Escuela de Ingenier´ıa
Departamento de Ingenier´ıa Industrial y de Sistemas
ICS2123 – Modelos Estoc´asticos
Profesores Ver´onica Godoy y Andr´es Navarro
Ayudante Jefe Joaqu´ın Vergara
Primer Semestre 2026
Ayudant´ıa 6:
Repaso Interrogaci´on 1
Ayudantes: Emilio Pe˜na (emilio.penasepulveda@uc.cl) & Mart´ın Pe˜na (martinpena@uc.cl)
Pregunta 1
En un sistema de telecomunicaciones, se monitorean dos variables aleatorias continuas: X, que representa
la potencia de la se˜nal de entrada (normalizada), e Y , que representa la potencia de la se˜nal de salida.
Debido a imperfecciones del sistema, se sabe que la potencia de salida no puede exceder la de entrada
(0 ≤Y ≤X).
La distribuci´on conjunta de estas variables est´a dada por la funci´on:
fX,Y (x, y) =
(
c(x + y)
0 ≤y ≤x ≤1
0
en otro caso
(a) Determine el valor de la constante c para que fX,Y (x, y) sea una funci´on de densidad conjunta v´alida.
Soluci´on: Para que una funci´on sea una densidad de probabilidad conjunta v´alida, debe cumplir
que :
Z ∞
−∞
Z ∞
−∞
fX,Y (x, y) dy dx = 1
Aplicando los l´ımites de nuestro soporte (0 ≤y ≤x ≤1):
Z 1
0
Z x
0
c(x + y) dy dx = 1
Resolvemos la integral interna respecto a y:
Z x
0
(x + y) dy =

xy + y2
2
x
0
= x2 + x2
2 = 3x2
2
Luego, integramos respecto a x:
c
Z 1
0
3x2
2 dx = c
x3
2
1
0
= c
2
Igualando a 1 para normalizar, obtenemos que c = 2.
(b) Encuentre las funciones de densidad marginal fX(x) y fY (y).
Soluci´on:
La funci´on de densidad marginal se obtiene integrando la densidad conjunta sobre la
variable que se desea eliminar:
Es posible obtener la distribuci´on marginal de x utilizando: fX(x) =
R ∞
−∞fX,Y (x, y) dy
fX(x) =
Z x
0
2(x + y) dy = 2

xy + y2
2
x
0
= 3x2,
para 0 ≤x ≤1
1

Para la marginal de Y utilizamos la f´ormula fY (y) =
R ∞
−∞fX,Y (x, y) dx Debido a que el soporte es
y ≤x ≤1:
fY (y) =
Z 1
y
2(x + y) dx = 2
x2
2 + xy
1
y
= 2
1
2 + y

−
y2
2 + y2

fY (y) = 1 + 2y −3y2,
para 0 ≤y ≤1
(c) Obtenga la funci´on de densidad condicional de la potencia de salida dado que se conoce la potencia
de entrada, fY |X(y|x).
Soluci´on: La funci´on de densidad condicional se define como el cociente entre la densidad conjunta
y la densidad marginal de la variable conocida:
fY |X(y|x) = fX,Y (x, y)
fX(x)
,
siempre que fX(x) > 0
Sustituyendo los resultados anteriores:
fY |X(y|x) = 2(x + y)
3x2
,
para 0 ≤y ≤x
(d) Si la potencia de entrada se fija en un valor x0, ¿cu´al es la potencia de salida esperada? Calcule
E[Y |X = x0].
Soluci´on: El valor esperado condicional se calcula utilizando la densidad condicional de la siguiente
manera:
E[Y |X = x0] =
Z ∞
−∞
y · fY |X(y|x0) dy
Sustituyendo nuestra densidad condicional:
E[Y |X = x0] =
Z x0
0
y ·
2(x0 + y)
3x2
0

dy =
2
3x2
0
Z x0
0
(x0y + y2) dy
Resolviendo la integral:
E[Y |X = x0] =
2
3x2
0
x0y2
2
+ y3
3
x0
0
=
2
3x2
0
x3
0
2 + x3
0
3

E[Y |X = x0] =
2
3x2
0
5x3
0
6

= 5
9x0
Por lo tanto, si la potencia de entrada es x0, esperamos que la potencia de salida sea 5
9 de dicho valor.
Pregunta 2
El temido Don Ram´on y sus n secuaces (n > 0) conforman una famosa banda dedicada al robo del ´unico
cajero autom´atico de la comuna de Chitollo. La patrulla de esa comuna busca afanosamente reducir a la
banda, pero hasta el momento no lo han conseguido.
Don Ram´on cita a sus secuaces para que a las 9:00 AM (diremos t = 0) est´en en la sede de la banda.
Una vez reunidos, cada uno de los secuaces que asistieron a la reuni´on demorar´a un tiempo distribuido
seg´un una v.a. exponencial de par´ametro λ en acudir al cajero (variables i.i.d.). En esta din´amica, se sabe
que cada uno de estos secuaces robar´a un monto de dinero del cajero, si es que la patrulla policial no se
encuentra en el lugar, ya que de encontrarse este secuaz ser´a arrestado.
Por el lado de la patrulla policial, a partir de las 9:00 AM, la patrulla acudir´a al cajero en un tiempo
distribuido seg´un una v.a. exponencial de par´ametro µ. Una vez en el lugar, la patrulla permanecer´a
indefinidamente vigilando el cajero.
2

(a) Entregue una expresi´on para la probabilidad de que la patrulla llegue al cajero en un tiempo menor
que t.
Soluci´on:
(i)
Tp: tiempo de llegada de la patrulla policial.
(ii)
Ti: tiempo de llegada del i-esimo secuaz (i ∈(1, n) ).
Se pide la probabilidad de que la patrulla llegue al cajero antes de t, considerando que el tiempo de
llegada de la patrulla distribuye exponencial de par´ametro µ:
P(Tp ≤t) =
Z t
0
µe−µxdx = 1 −e−µt
(b) Entregue una expresi´on para la distribuci´on de probabilidad del tiempo de llegada del primer asal-
tante.
Soluci´on: Para determinar la distribuci´on de probabilidad del tiempo de llegada del primer asaltante,
definimos esta variable como el m´ınimo de los tiempos de llegada de los n secuaces:
Tm´ın = m´ın(T1, T2, . . . , Tn)
donde cada Ti ∼Exp(λ) y son variables aleatorias independientes e id´enticamente distribuidas (i.i.d.).
Calculamos primero la funci´on que representa la probabilidad de que el primer asaltante llegue despu´es
de un tiempo t:
P(Tm´ın > t) = P(T1 > t, T2 > t, . . . , Tn > t)
Debido a la independencia de los Ti, la probabilidad de la intersecci´on es el producto de las probabi-
lidades individuales:
P(Tm´ın > t) =
n
Y
i=1
P(Ti > t) =
n
Y
i=1
e−λt = e−nλt
De esta forma obtenemos la Funci´on de Distribuci´on Acumulada:
FTm´ın(t) = 1 −P(Tm´ın > t) = 1 −e−nλt,
t ≥0
Finalmente, derivamos la funci´on obtenida respecto a t para obtener la funci´on de densidad de pro-
babilidad :
fTm´ın(t) = d
dt(1 −e−nλt) = nλe−nλt,
t ≥0
Por lo tanto, el tiempo de llegada del primer asaltante sigue una distribuci´on exponencial con par´ame-
tro nλ:
Tm´ın ∼Exp(nλ)
(c) ¿Cu´al es la probabilidad de que la patrulla sorprenda a todos los asaltantes en su intento de robo al
cajero?
Soluci´on: Para que la patrulla sorprenda a todos los asaltantes, necesariamente debe acudir antes
que cualquiera de ellos. En este caso, el tiempo de la patrulla debe ser menor que el m´ınimo de los
tiempos de llegada de los secuaces. Utilizando lo obtenido en b).
P(Tp < m´ın(T1, T2, . . . , Tn)) = P(Tp < Tmin)
Donde Tmin ∼Exp(nλ)
=
Z ∞
0
P(Tp < t) · fTmin(t)dt
=
Z ∞
0
(1 −e−µt) · nλe−nλtdt = nλ
Z ∞
0
e−nλt −e−t(µ+nλ)dt
Resolviendo la integral:
= nλ
e−nλt
−nλ −e−(µ+nλ)t
−(µ + nλ)
∞
0
3

= nλ

0 −

−1
nλ

−

0 −

−
1
µ + nλ

= nλ
 1
nλ −
1
µ + nλ

= 1 −
nλ
µ + nλ
Realizando la suma de fracciones obtenemos el resultado notable de carrera de exponenciales:
P(Tp < Tm´ın) =
µ
µ + nλ
Pregunta 3
Un algoritmo de trading de alta frecuencia (HFT) procesa un flujo continuo de ´ordenes financieras para
un activo en particular. El libro de ´ordenes clasifica las peticiones estrictamente en dos tipos: ´Ordenes de
Mercado (tipo M) y ´Ordenes Limitadas (tipo L).
El equipo de analistas cuantitativos ha modelado el flujo de llegada de estas ´ordenes como procesos de
Poisson independientes, con tasas λM [´ordenes/milisegundo] para las de mercado y λL [´ordenes/milisegundo]
para las limitadas.
(a) Durante un evento de alt´ısima volatilidad (conocido como flash crash) que dur´o exactamente τ mili-
segundos, los registros del servidor indican que el algoritmo proces´o un bloque denso de exactamente
N ´ordenes en total (sumando ambos tipos). El regulador financiero iniciar´a una investigaci´on au-
tom´atica por “manipulaci´on de liquidez” si, dentro de ese bloque exacto de N ´ordenes, la cantidad
de ´Ordenes de Mercado procesadas fue estrictamente superior al doble de las ´Ordenes Limitadas
procesadas. Dado este registro de llegadas totales, formule la expresi´on exacta para la probabilidad
de que el algoritmo sea investigado por el regulador.
Soluci´on:
Sean XM y XL el n´umero de ´ordenes de mercado y limitadas recibidas en el lapso τ. Sabemos que
la superposici´on es un proceso de Poisson de tasa λM + λL. Dado que el total de eventos es N, la
variable XM condicionada a XM + XL = N sigue una distribuci´on Binomial con par´ametros N y
probabilidad de ´exito p =
λM
λM+λL .
La condici´on para la investigaci´on es XM > 2XL. Como sabemos que XL = N −XM, reemplazamos
en la inecuaci´on:
XM > 2(N −XM)
XM > 2N −2XM
3XM > 2N
XM > 2N
3
Por lo tanto, necesitamos calcular la probabilidad de que nuestra variable Binomial tome valores
estrictamente mayores a 2N/3. Dado que XM es discreta, el l´ımite inferior de la sumatoria debe ser
el entero inmediatamente superior: k = ⌊2N/3⌋+ 1.
P

XM > 2N
3
 Total = N

=
N
X
k=⌊2N/3⌋+1
N
k
 
λM
λM + λL
k 
λL
λM + λL
N−k
(b) El algoritmo utiliza un “Indicador de Presi´on de Libro” para predecir cambios bruscos en el precio.
Este indicador rastrea la secuencia cronol´ogica de las ´ordenes y se satura (alcanzando el 100 %) en
el instante preciso en que el sistema registra la llegada de la K-´esima Orden Limitada de la sesi´on
operativa (K ≥3). Determine la probabilidad exacta de que el indicador se sature habiendo permitido
que el algoritmo procese, a lo sumo, 2 ´Ordenes de Mercado desde el inicio de la sesi´on.
Soluci´on:
Si ignoramos la escala de tiempo y solo observamos el proceso de saltos embebido, cada evento que
llega es una Orden Limitada (´exito, con probabilidad p =
λL
λM+λL ) o una Orden de Mercado (fracaso,
con probabilidad 1 −p =
λM
λM+λL ).
4

Sea Y el n´umero de ´Ordenes de Mercado (fracasos) observadas antes de que ocurra la K-´esima Orden
Limitada (el K-´esimo ´exito). Por definici´on, Y ∼Binomial Negativa(K, p).
Nos piden la probabilidad de que el indicador se sature habiendo procesado “a lo sumo 2 ´Ordenes de
Mercado”, es decir, P(Y ≤2). Esto requiere sumar las probabilidades de que lleguen 0, 1 o 2 ´ordenes
de mercado antes de la K-´esima limitada:
P(Y ≤2) = P(Y = 0) + P(Y = 1) + P(Y = 2)
Usando la funci´on de masa de la Binomial Negativa, P(Y = y) =
 y+K−1
y

pK(1 −p)y:
P(Y = 0) =
K −1
0

pK(1 −p)0 = pK
P(Y = 1) =
K
1

pK(1 −p)1 = KpK(1 −p)
P(Y = 2) =
K + 1
2

pK(1 −p)2 = (K + 1)K
2
pK(1 −p)2
Reemplazando las probabilidades por las tasas:
P(Y ≤2) =

λL
λM + λL
K "
1 + K

λM
λM + λL

+ K(K + 1)
2

λM
λM + λL
2#
(c) Si la sesi´on de mercado abre en t = 0, ¿cu´al es la probabilidad de que la primera Orden Limitada del
d´ıa se registre antes de los primeros τ0 milisegundos, y que adem´as, en ese preciso instante en que
entra dicha Orden Limitada, el algoritmo a´un no haya recibido ninguna Orden de Mercado?
Soluci´on:
El problema nos exige que se cumplan dos condiciones simult´aneamente: 1. El tiempo hasta que
ocurra el primer evento de cualquier tipo (sea M o L), que llamaremos T1, debe ser menor a τ0. 2.
Ese primer evento que llega debe ser estrictamente del tipo Limitada (L). (Si el primer evento es L,
garantiza por defecto que no ha llegado ninguna de Mercado antes).
Por las propiedades de superposici´on de procesos de Poisson, sabemos que: - El tiempo hasta el primer
evento T1 sigue una distribuci´on Exponencial con tasa combinada λtotal = λM +λL. - La probabilidad
de que un evento sea de tipo L es p =
λL
λM+λL .
Por lo tanto, la probabilidad conjunta es simplemente el producto de las probabilidades individuales:
P(T1 < τ0 ∩Primer evento es L) = P(T1 < τ0) · P(Primer evento es L)
Evaluando la CDF de la exponencial y la probabilidad del tipo de evento:
P =

1 −e−(λM+λL)τ0
·

λL
λM + λL

5

