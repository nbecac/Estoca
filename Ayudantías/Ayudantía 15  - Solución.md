Pontificia Universidad Cat´olica de Chile
Escuela de Ingenier´ıa
Departamento de Ingenier´ıa Industrial y de Sistemas
ICS2123 – Modelos Estoc´asticos
Profesores Ver´onica Godoy y Andr´es Navarro
Ayudante Jefe Joaqu´ın Vergara
Primer Semestre 2026
Ayudant´ıa 15:
Simulaci´on
Ayudantes: Emilio Pe˜na (emilio.penasepulveda@uc.cl) & Mart´ın Pe˜na (martinpena@uc.cl)
1.
Resumen
Simulaci´on
Diagrama de Flujo
El diagrama de flujo es una representaci´on gr´afica de un algoritmo o proceso. Se utiliza ampliamente en
´areas como programaci´on, econom´ıa, procesos industriales y psicolog´ıa cognitiva.
En simulaci´on discreta, los eventos son cambios de estado que ocurren en puntos espec´ıficos del tiempo
(por ejemplo, llegada o salida de una entidad). Las variables representan el estado del sistema en cada
instante y se actualizan como resultado de estos eventos.
⋄Eventos: Sucesos que desencadenan cambios en el sistema (e.g., llegada de un requerimiento, t´ermino
de procesamiento).
⋄Variables de estado: Describen la situaci´on actual del sistema (e.g., n´umero de elementos en cola,
estado de la m´aquina).
Nomenclatura B´asica
⋄C´ırculo: Inicio y T´ermino
⋄Rect´angulo: Evento o acci´on
⋄Rombo: Decisi´on
M´etodo de Congruencia Lineal (LCG)
El m´etodo de congruencia lineal (LCG) permite generar numeros aleatorios Uniformes (0, 1) a partir de
unos par´ametros c, m y α; y una semilla Z0
Zi = (αZi−1 + c) m´od m
Ui = Zi
m
M´etodo de la Transformada Inversa
Es un m´etodo que permite generar realizaciones de una Variable Aleatoria (cuya Funci´on de Distribuci´on
Acumulada admita inversa) a partir de n´umeros aleatorios Uniformes.
El algoritmo es el siguiente (simplificado):
(a) Generar una Instancia Ui proveniente de una U(0, 1).
(b) Sea FX(x) la funci´on de distribuci´on acumulada de la Variable Aleatoria X. Determinar F −1
X (x).
(c) Xi ser´a la realizaci´on de la Variable Aleatoria X asociada al n´umero Aleatorio Ui. Se obtiene como
Xi = F −1
X (Ui)
1

M´etodo de Aceptaci´on y Rechazo
Sea la funci´on g(x) = f(x)
t(x) (notar que 0 ≤g(x) ≤1). Sean U, Y dos v.a. independientes tales que U ∼
U(0, 1), e Y posee funci´on densidad h(y). La variable aleatoria definida como Y condicionada a que U ≤
g(Y ) distribuye seg´un la funci´on de densidad f(y)
El algoritmo es el siguiente (simplificado):
(a) Generar una instancia de U ∼U(0, 1).
(b) Generar una instancia de Y ∼h(y) (independiente de U).
(c) Si U ≤g(Y ), entonces hacer X = Y . Si no, volver al paso (a).
2

Problema 1
Parte 1 (LCG)
Suponga que desea encontrar 3 n´umeros aleatorios {Ui ∼U(0, 1)} considerando 1 ≤i ≤3. Considere el
m´etodo de congruencia lineal (LCG) con los siguientes par´ametros: m = 5, α = 2, c = 3 y Z0 = 1. A partir
de ello se le solicita:
(a) Complete la siguiente tabla con los valores respectivos:
i
Zi
Ui
0
1
–
1
2
3
Hint: Considere la f´ormula recursiva del LCG
Zi = (αZi−1 + c) m´od m,
Ui = Zi
m ,
donde α, c y m son los par´ametros entregados, Zi−1 el valor de la iteraci´on anterior (se parte con Z0,
la semilla), y m´od la operaci´on que entrega el resto de una divisi´on. Ui es la instancia de la U(0, 1)
que se genera.
Soluci´on: Recordando las f´ormulas Zi = (αZi−1 + c) m´od m y Ui = Zi/m, y llenando la tabla:
i
Zi
Ui
0
1
–
1
0
0
2
3
0.6
3
4
0.8
(b) Determine cu´al es el ciclo/periodo de este m´etodo. Suponga que le piden aumentar la cantidad de
n´umeros aleatorios distintos que genera este m´etodo. ¿Qu´e cambios propondr´ıa sobre los par´ametros
del LCG?
Soluci´on: Si prolongamos la tabla:
i
Zi
Ui
0
1
–
1
0
0
2
3
0.6
3
4
0.8
4
1
0.2
Notamos que en una iteraci´on m´as volvemos al valor inicial Z0, por lo que el ciclo de este m´etodo
es 4. Para aumentar la cantidad de n´umeros aleatorios distintos se debe aumentar el periodo: ne-
cesariamente hay que aumentar m (ya que a lo m´as se tendr´an m n´umeros diferentes). Luego se
pueden ajustar α y c siguiendo los criterios de periodo completo (por ejemplo, evitando que α y c
sean m´ultiplos entre s´ı, o que lo sean respecto de m).
Parte 2 (Transformada inversa)
Considere una variable aleatoria continua X con la siguiente funci´on de densidad
f(x) = a |x|,
x ∈[−a, a],
donde a > 0.
(c) Encuentre el valor de a para que f(x) efectivamente sea una funci´on de densidad. Hint: Recuerde que
|x| = x si x ≥0 y |x| = −x si x < 0.
3

Soluci´on: Imponemos que la densidad integre 1:
Z a
−a
a |x| dx = 2
Z a
0
a x dx = 2a · a2
2 = a3 = 1 ⇒a = 1.
(d) Encuentre la funci´on de probabilidad acumulada de f(x).
Soluci´on: Con a = 1, calculamos F(x):
F(x) =





1
2 −1
2x2,
−1 ≤x ≤0,
1
2 + 1
2x2,
0 < x ≤1.
(e) Encuentre la funci´on inversa de la funci´on de probabilidad acumulada calculada.
Soluci´on: Invirtiendo cada tramo:
F −1(x) =



−√1 −2x,
x ≤0.5,
√2x −1,
x > 0.5.
(f) Explique y detalle paso a paso c´omo generar instancias de la variable aleatoria continua X mediante
el m´etodo de la Transformada Inversa. Luego, complete la siguiente tabla a partir de los tres primeros
n´umeros aleatorios U(0, 1) generados en (a). Despu´es, indique de d´onde nace la idea y/o intuici´on de
este algoritmo.
i
Ui
Xi
1
0
2
0.6
3
0.8
Soluci´on: El procedimiento es:
⋄Generamos una instancia U1 a partir de U(0, 1).
⋄F −1(U1) = X1 ser´a una instancia de X, pues X y F −1(U) comparten distribuci´on de probabi-
lidades.
Usando las instancias uniformes generadas en la Parte 1:
i
Ui
Xi
1
0
−1
2
0.6
0.447214
3
0.8
0.774597
La idea del algoritmo es que, si la CDF de una variable aleatoria es invertible en su soporte y se
dispone de alg´un mecanismo para generar U(0, 1), entonces se puede recuperar una instancia de X a
trav´es de la funci´on inversa.
Parte 3 (A/R)
Se le pide generar realizaciones de una variable aleatoria con la siguiente funci´on de densidad
f(x) = 60 x3(1 −x)2,
0 ≤x ≤1.
Esta no se puede invertir anal´ıticamente de forma sencilla. Se le propone utilizar el algoritmo de Acepta-
ci´on/Rechazo para generar instancias de esta variable aleatoria X. Para ello:
(g) Encuentre t(x), una funci´on majorizing de f(x).
Soluci´on: Para elegir t(x) buscamos el valor m´aximo de f:
df(x)
dx
= 180(1 −x)2x2 −120(1 −x)x3 = 0.
El m´aximo se alcanza en x = 3/5, donde la funci´on vale 2.0736. Por lo tanto, tomamos t(x) = 2.0736.
4

(h) Determine el valor de la constante c y el n´umero esperado de iteraciones hasta obtener una instancia
con el algoritmo de Aceptaci´on y Rechazo.
Soluci´on: La constante c es
c =
Z +∞
−∞
t(x) dx =
Z 1
0
2.0736 dx = 2.0736,
y el n´umero esperado de iteraciones hasta aceptar una instancia es c = 2.0736.
(i) Encuentre g(y), h(x) e indique expl´ıcitamente c´omo generar instancias de la variable aleatoria Y ∼
h(x), utilizada en el algoritmo de Aceptaci´on y Rechazo.
Soluci´on: La funci´on de aceptaci´on es
g(y) = f(y)
t(y) = 60 y3(1 −y)2
2.0736
,
y la densidad de candidatos es
h(x) = t(x)
c
= 2.0736
2.0736 = 1,
0 ≤x ≤1,
es decir, h(x) ∼U(0, 1). Usando transformada inversa sobre una uniforme (cuya CDF es F(y) = y
en [0, 1]), se genera el candidato directamente como Y = W, con W ∼U(0, 1) una nueva instancia
uniforme.
(j) Describa paso a paso un algoritmo de Aceptaci´on y Rechazo para obtener muestras de f(x). Luego,
complete la siguiente tabla, reemplazando en Ui los tres n´umeros aleatorios U(0, 1) que gener´o en la
parte (a). Posteriormente, indique de d´onde nace la idea y/o intuici´on de este algoritmo. Hint: El W
que se entrega en la tabla es el que deben utilizar para generar instancias de Y ∼h(x).
i
Ui
Yi
Wi
g(Yi)
¿Acepto o Rechazo?
1
0
0.986
2
0.6
0.5632
3
0.8
0.2623
Soluci´on: Descripci´on del algoritmo:
⋄Generar una instancia U ∼U(0, 1).
⋄Generar una instancia Y ∼h(y) (independiente de U).
⋄Si U ≤g(Y ), hacer X = Y . Si no, volver al primer paso.
Reemplazando los valores de la tabla:
i
Ui
Yi
Wi
g(Yi)
¿Acepto o Rechazo?
1
0
0.986
0.986
0.00543642
Acepto
2
0.6
0.5632
0.5632
0.986233
Acepto
3
0.8
0.2623
0.2623
0.284172
Rechazo
Este algoritmo nace de que hay funciones que no se pueden invertir f´acilmente, lo que complica usar
la Transformada Inversa. La idea es encontrar una funci´on que acote superiormente a la objetivo,
que sea similar a ella y de la cual s´ı se puedan generar instancias de forma sencilla. Iterativamente
se generan candidatos y solo se acepta una fracci´on de ellos, en la proporci´on entre el ´area real y el
´area de la funci´on que acota superiormente.
5

Problema 2
Desde hace unos a˜nos, la novedosa cafeter´ıa Cozy Mug empez´o a operar en la ciudad. Sus tiendas se
caracterizan por contar solo con m´aquinas de caf´e autom´aticas, las cuales son iguales entre s´ı. En el campus
hay una de estas tiendas, que cuenta con un total de tres m´aquinas. Considere que cada m´aquina de caf´e
tiene cola ´unica, es decir, hay tres filas distintas.
Para evaluar el funcionamiento de las m´aquinas, un grupo de estudiantes de ingenier´ıa decide realizar
simulaciones para determinar el tiempo de espera promedio por m´aquina. El grupo realiz´o un levantamiento
de datos, y tras este, llevaron a cabo simulaciones para cada una de las m´aquinas, con un total de 5 r´eplicas
y un tiempo de simulaci´on de 15 minutos de operaci´on para cada una de ellas, en las cuales se analiz´o el
tiempo promedio de espera en cola en la m´aquina correspondiente. Los resultados de la simulaci´on para
cada m´aquina se presentan a continuaci´on:
Tiempo de Espera Promedio por M´aquina (minutos)
Repetici´on
M´aquina A
M´aquina B
M´aquina C
1°
1.0
0.2
2.5
2°
1.8
0.1
1.4
3°
2.4
0.3
0.6
4°
3.1
0.7
1.7
5°
1.1
0.9
2.0
Promedio
1.88
0.44
1.64
Varianza
0.79
0.12
0.50
(a) Para el an´alisis de resultados, ¿a cu´al de los dos tipos de simulaci´on vistos en clases corresponde
la situaci´on planteada anteriormente? Justifique su respuesta y explique qu´e cambios se le deber´ıan
hacer al modelo para que correspondiese al otro tipo de simulaci´on de an´alisis de resultados.
Soluci´on: Esta situaci´on corresponde a una Simulaci´on Terminal (o de Corto Plazo), debido a
que la duraci´on de la simulaci´on est´a enmarcada en un acotado periodo de tiempo, en este caso de 15
minutos. Para que fuese una Simulaci´on en Estado de R´egimen (o de Largo Plazo), esta deber´ıa
tener una duraci´on considerablemente mayor, de modo que las condiciones iniciales del sistema dejen
de tener efecto. Por ejemplo, operaci´on del sistema en un periodo de un a˜no, o el tiempo de espera
en cola considerando los siguientes 100.000 clientes.
(b) ¿Qu´e condici´on deben cumplir las r´eplicas de una misma simulaci´on entre s´ı para que esta funcione
correctamente y el an´alisis estad´ıstico pueda ser v´alido? Explique, a partir del contexto del problema,
c´omo podr´ıa no cumplirse esta condici´on y qu´e efectos conllevar´ıa.
Soluci´on: La condici´on que debe cumplirse entre las r´eplicas de una misma simulaci´on es que estas
deben ser independientes entre s´ı. Bajo el contexto planteado, esta condici´on podr´ıa no cumplirse
si cada repetici´on tomase en cuenta los resultados almacenados de iteraciones anteriores, y a partir
de ello fuese calculando el tiempo de espera promedio en las siguientes reiteraciones. Esto podr´ıa
provocar la obtenci´on de resultados sesgados e incluso err´oneos, lo cual llevar´ıa a un an´alisis con
informaci´on falsa que no reflejar´ıa la situaci´on propuesta.
(c) Considere“t4.0975 = 2.27764” para el desarrollo de sus respuestas:
Con la informaci´on proporcionada en las tablas y su elecci´on anterior, construya un intervalo de
confianza al 95 % para cada uno de los tres casos de sistemas. Hint: El intervalo de confianza a
considerar es
¯X(n) ± t
r
S2(n)
n
,
donde n es el tama˜no de la muestra, t el valor de tabla de la t-Student, y ¯X(n), S2(n) el promedio y
la varianza muestral, respectivamente.
Soluci´on: El valor a utilizar es el de sub´ındice 4 (grados de libertad, n −1 = 4) y 0.975, es decir
t4,0.975 = 2.7764, lo que se deduce de la propia f´ormula del intervalo (dos colas al 95 %). Con esto:
M´aquina A: ¯A(5) = 1.88, S2
A(5) = 0.79
1.88 ± 2.7764
r
0.79
5
= 1.88 ± 1.1 = [0.78; 2.98].
M´aquina B: ¯B(5) = 0.44, S2
B(5) = 0.12
0.44 ± 2.7764
r
0.12
5
= 0.44 ± 0.43 = [0.01; 0.87].
6

M´aquina C: ¯C(5) = 1.64, S2
C(5) = 0.50
1.64 ± 2.7764
r
0.50
5
= 1.64 ± 0.88 = [0.76; 2.52].
(d) Se desea determinar el ranking de las m´aquinas en t´erminos de eficiencia, en relaci´on al tiempo
promedio de espera. Para ello considere las siguientes m´etricas definidas:
Wi = Ai −Bi,
Yi = Bi −Ci,
Zi = Ci −Ai,
donde Ai/Bi/Ci representa el tiempo de espera promedio de la m´aquina A/B/C en la repetici´on i,
respectivamente. La siguiente tabla le puede ser de ayuda:
Repetici´on
W = A −B
Y = B −C
Z = C −A
1°
2°
3°
4°
5°
A partir de los resultados de cada m´aquina, confeccione intervalos de confianza al 95 % que le permitan
elaborar el ranking solicitado. ¿Es posible con dicho nivel de confianza establecer el ranking? Hint:
La varianza muestral es S2(n) =
1
n −1
Pn
i=1
 Xi −¯X(n)
2.
Soluci´on: Los valores a utilizar son:
Repetici´on
W
Y
Z
1°
0.8
−2.3
1.5
2°
1.7
−1.3
−0.4
3°
2.1
−0.3
−1.8
4°
2.4
−1.0
−1.4
5°
0.2
−1.1
0.9
Con t4,0.975 = 2.7764 (igual que en el inciso anterior):
Wi: ¯W(5) = 1.44, S2
W (5) = 0.84
1.44 ± 2.7764
r
0.84
5
= 1.44 ± 1.14 = [0.3; 2.58].
Yi: ¯Y (5) = −1.2, S2
Y (5) = 0.52
−1.2 ± 2.7764
r
0.52
5
= −1.2 ± 0.9 = [−2.1; −0.3].
Zi: ¯Z(5) = −0.24, S2
Z(5) = 2.03
−0.24 ± 2.7764
r
2.03
5
= −0.24 ± 1.77 = [−2.01; 1.53].
Conclusiones:
⋄En el primer caso (W = A −B) el intervalo es totalmente positivo. Como para la eficiencia
buscamos los valores m´as peque˜nos, la M´aquina B es mejor que la A.
⋄En el segundo (Y = B −C) el intervalo es totalmente negativo, lo que implica nuevamente que
la M´aquina B es mejor que la C.
⋄En el ´ultimo (Z = C −A) el intervalo incluye valores positivos y negativos, por lo que no se
puede concluir si A o C es mejor.
As´ı, el ranking posicionar´ıa a la M´aquina B en primer lugar, mientras que A y C quedan indeter-
minadas. Por lo tanto, no es posible armar un ranking completo a ese nivel de confianza.
7

(e) Tras discutir sus resultados, surge la idea de que las simulaciones realizadas tienen deficiencias, y que
por consiguiente los intervalos de confianza podr´ıan verse afectados (dada la alta variabilidad y poca
convergencia de los resultados). Proponga dos ideas con las cuales se puedan mejorar las simulaciones
y as´ı obtener mejores intervalos de confianza.
Soluci´on: Dos ideas ser´ıan:
⋄Dejar que cada r´eplica tenga una duraci´on mayor en tiempo de simulaci´on (por ejemplo, pasar
de 15 minutos a 8 horas). De esta forma, los resultados de tiempo de espera promedio ser´ıan
m´as cercanos entre r´eplicas.
⋄Realizar una mayor cantidad de r´eplicas (por ejemplo, 100 o m´as, en vez de solo 5), lo que
entrega m´as informaci´on sobre los promedios buscados.
Ambas ideas buscan reducir la varianza del tiempo de espera promedio, lo que permite construir
intervalos de confianza m´as acotados y, por ende, m´as certeros (pueden implementarse de forma
simult´anea). Otra idea v´alida es que podr´ıan haberse cometido errores en el levantamiento de datos;
corregir esa estrategia tambi´en mejorar´ıa la simulaci´on del modelo.
8

Problema 3 (Propuesto)
Suponga que el tiempo (en horas) que una persona tarda en ejercer su voto durante la segunda vuelta de
las elecciones presidenciales se modela mediante una variable aleatoria continua X, acotada en el intervalo
[0, 1], cuya funci´on de densidad de probabilidad (PDF) es f(x) := 6x(1 −x). Con el fin de planificar la
jornada de votaci´on junto a su familia, usted decide aplicar los conceptos de simulaci´on, en particular la
generaci´on de variables aleatorias utilizando un m´etodo de Aceptaci´on y Rechazo. Para ello considere la
funci´on de cota superior t(x) dada por la funci´on lineal por tramos con forma trapezoidal mostrada en la
Figura 1:
t(x) :=





6x,
0 ≤x ≤0.25,
1.5,
0.25 < x ≤0.75,
−6x + 6,
0.75 < x ≤1.
x
0.25
0.75
1
1.5
t(x)
f(x)
Figura 1: Cota superior t(x) y funci´on objetivo f(x) utilizadas para el m´etodo de Aceptaci´on y Rechazo.
considere los siguientes resultados:
c = 9
8
g(x) =





1 −x,
0 ≤x ≤0.25,
4x(1 −x),
0.25 < x ≤0.75,
x,
0.75 < x ≤1.
h(x) =
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
16
3 x,
0 ≤x ≤0.25,
4
3,
0.25 < x ≤0.75,
−16
3 x + 16
3 ,
0.75 < x ≤1.
H(x) =
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
8
3x2,
0 ≤x ≤0.25,
4
3x −1
6,
0.25 < x ≤0.75,
−8
3x2 + 16
3 x −5
3,
0.75 < x ≤1,
H−1(y) =

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

r
3y
8 ,
0 ≤y ≤1
6,
3y
4 + 1
8,
1
6 < y ≤5
6,
1 −
r
1 −5 + 3y
8
,
5
6 < y ≤1.
(a) En la Tabla, los valores de ´ındice par se utilizan, en orden, para generar candidatos, mientras que los
valores de ´ındice impar se emplean (tambi´en en orden) para aceptar o rechazar dichos candidatos.
A partir de estas muestras, y utilizando apropiadamente g(x) y H−1(x), aplique el algoritmo de
Aceptaci´on y Rechazo para generar muestras de X. Con ello, simule el tiempo que tardar´an en votar
los n integrantes de su grupo familiar, donde n corresponde al n´umero de instancias que efectivamente
logre generar con su algoritmo.
Muestra
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
Ui
0.498
0.186
0.270
0.323
0.432
0.125
0.021
0.464
0.250
0.011
Uso
A/R1
G1
A/R2
G2
A/R3
G3
A/R4
G4
A/R5
G5
9

Soluci´on: Cada iteraci´on del algoritmo de Aceptaci´on y Rechazo es de la forma:
(a) Generar instancia uniforme U1.
(b) Generar segunda instancia uniforme U2.
(c) Generar instancia candidata Y evaluando U2 en H−1(y).
(d) Evaluar la instancia candidata Y en la funci´on de aceptaci´on g(y).
(e) Si U1 ≤g(Y ), aceptar Y como instancia de X; si no, regresar al primer paso.
Aplicando el algoritmo a la Tabla 1:
i
Ui
Y = H−1(Ui)
g(Y )
Decisi´on
1
0.498
–
–
–
2
0.186
0.265
0.778
Aceptamos 0.265
3
0.270
–
–
–
4
0.323
0.367
0.930
Aceptamos 0.367
5
0.432
–
–
–
6
0.125
0.217
0.783
Aceptamos 0.217
7
0.021
–
–
–
8
0.464
0.473
0.997
Aceptamos 0.473
9
0.250
–
–
–
10
0.011
0.064
0.936
Aceptamos 0.064
De este modo, los n = 5 integrantes que ir´an a votar juntos tardar´an un total de 0.265 + 0.367 +
0.217 + 0.473 + 0.064 = 1.385 horas.
(b) Una mesa de votaci´on cuenta con aproximadamente 400 votantes. Comente: ¿en qu´e porcentaje
aumentar´ıa la cantidad esperada de iteraciones necesarias para simular el tiempo total de votaci´on
de todos los electores si, en lugar del algoritmo que utiliza la cota trapezoidal, se empleara en el
m´etodo de Aceptaci´on y Rechazo la cota constante t(x) = k m´as eficiente posible (es decir, aquella
que maximiza la probabilidad de aceptar un candidato)?
Soluci´on: En el inciso (b) se determin´o c = 9
8. Por tanto, el algoritmo actual requiere en promedio
400 × 9
8 = 450
iteraciones para generar las 400 muestras. La mejor cota constante es t(x) = 1.5, de modo que c′ = 1.5
y el n´umero esperado de iteraciones ser´ıa
400 × 1.5 = 600.
En consecuencia, el uso de esta cota constante implica un aumento de
600 −450
450
= 33.3 %
en la cantidad esperada de iteraciones necesarias para simular el tiempo de votaci´on de todos los
electores.
(a) Considere un m´etodo congruencial lineal (LCG) con a = 3, c = 5 y m = 31. Utilizando la semilla
x0 = 43, genere 5 instancias Uniforme(0, 1). Redondee a 3 cifras decimales en caso de ser necesario.
Indicaci´on: La semilla no cuenta dentro de las 5 instancias Uniforme(0, 1) a generar.
Soluci´on: Utilizando Xn+1 = (aXn + c) m´od m y Un = Xn
m , la secuencia de valores uniformes
obtenida es:
i
xi
Ui
0
43
–
1
10
0.323
2
4
0.129
3
17
0.548
4
25
0.806
5
18
0.581
10

(b) A partir de las instancias uniformes generadas en (a), obtenga todas las instancias num´ericas posibles
de la variable aleatoria X mediante el m´etodo de la transformada inversa, considerando que su funci´on
de densidad de probabilidad (PDF) est´a dada por
f(x) =
(
a(x + 1)3,
x ∈[−1, 1],
0,
en otro caso,
donde a corresponde a la constante de normalizaci´on asociada a la distribuci´on de X.
Soluci´on: Primero determinamos a para que f(x) sea una densidad. Con el cambio u = x + 1:
Z 1
−1
a(x + 1)3 dx =
Z 2
0
a u3 du = a · u4
4

2
0 = 4a = 1 ⇒a = 1
4.
Luego, la CDF se obtiene integrando (u = t + 1):
F(x) =
Z x
−1
1
4(t + 1)3 dt = 1
4 · (x + 1)4
4
= (x + 1)4
16
.
Aplicando el m´etodo de transformada inversa:
U = (x + 1)4
16
⇒(x + 1)4 = 16U ⇒x + 1 = (16U)1/4 ⇒X = 2U 1/4 −1.
Sustituyendo las instancias de (a):
Ui
Xi = 2U 1/4
i
−1
0.323
0.507
0.129
0.199
0.548
0.721
0.806
0.895
0.581
0.746
(c) Sea Y una variable aleatoria cuya distribuci´on est´a dada por
Y =





0,
con probabilidad 1
2,
U,
con probabilidad 1
2,
donde U ∼Uniforme(−5, 15). A partir de las instancias Uniforme(0, 1) generadas en (a), obtenga las
correspondientes realizaciones num´ericas de la variable aleatoria Y , empleando un m´etodo adecuado
basado en la transformada inversa (u otro procedimiento equivalente).
Soluci´on: Se trata de una distribuci´on mixta. Identificamos cada componente:
⋄Parte discreta: P(Y = 0) = 1/2.
⋄Parte continua: condicional a Y ̸= 0, Y ∼Uniforme(−5, 15) con densidad
1
20; escalada por
P(Y ̸= 0) = 1/2, queda f(y) = 1
2 · 1
20 =
1
40 para y ∈[−5, 15], y ̸= 0.
Construyendo la CDF F(x) = P(Y ≤x), notando que F(0) = P(Y < 0) + P(Y = 0) = 0+5
40 + 1
2 =
1
8 + 1
2 = 5
8:
F(x) =
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
0,
x < −5,
x + 5
40 ,
−5 ≤x < 0,
5
8,
x = 0,
5
8 + x
40,
0 < x ≤15,
1,
x > 15.
11

x
F(x)
0.5
1
−5
0
5
10
15
Para generar instancias dividimos el rango de U ∼U(0, 1) seg´un los saltos de F:
⋄Si 0 < U ≤0.125 (es decir Y ∈[−5, 0)), usamos U = x + 5
40 , por ende x = 40U −5.
⋄Si 0.125 < U ≤0.625 (es decir Y = 0), asignar Y = 0.
⋄Si 0.625 < U ≤1 (es decir Y ∈(0, 15]), usamos U = 5
8 + x
40, por ende x = 40U −25.
Finalmente, para los valores entregados:
Ui
Caso
Yi
0.323
0.125 < U ≤0.625
0
0.129
0.125 < U ≤0.625
0
0.548
0.125 < U ≤0.625
0
0.806
0.625 < U ≤1
40 · 0.806 −25 = 7.258
0.581
0.125 < U ≤0.625
0
12

