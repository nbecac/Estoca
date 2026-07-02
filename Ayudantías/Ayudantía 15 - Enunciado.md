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
(b) Determine cu´al es el ciclo/periodo de este m´etodo. Suponga que le piden aumentar la cantidad de
n´umeros aleatorios distintos que genera este m´etodo. ¿Qu´e cambios propondr´ıa sobre los par´ametros
del LCG?
Parte 2 (Transformada inversa)
Considere una variable aleatoria continua X con la siguiente funci´on de densidad
f(x) = a |x|,
x ∈[−a, a],
donde a > 0.
(c) Encuentre el valor de a para que f(x) efectivamente sea una funci´on de densidad. Hint: Recuerde que
|x| = x si x ≥0 y |x| = −x si x < 0.
(d) Encuentre la funci´on de probabilidad acumulada de f(x).
(e) Encuentre la funci´on inversa de la funci´on de probabilidad acumulada calculada.
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
Parte 3 (A/R)
Se le pide generar realizaciones de una variable aleatoria con la siguiente funci´on de densidad
f(x) = 60 x3(1 −x)2,
0 ≤x ≤1.
Esta no se puede invertir anal´ıticamente de forma sencilla. Se le propone utilizar el algoritmo de Acepta-
ci´on/Rechazo para generar instancias de esta variable aleatoria X. Para ello:
3

(g) Encuentre t(x), una funci´on majorizing de f(x).
(h) Determine el valor de la constante c y el n´umero esperado de iteraciones hasta obtener una instancia
con el algoritmo de Aceptaci´on y Rechazo.
(i) Encuentre g(y), h(x) e indique expl´ıcitamente c´omo generar instancias de la variable aleatoria Y ∼
h(x), utilizada en el algoritmo de Aceptaci´on y Rechazo.
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
4

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
(b) ¿Qu´e condici´on deben cumplir las r´eplicas de una misma simulaci´on entre s´ı para que esta funcione
correctamente y el an´alisis estad´ıstico pueda ser v´alido? Explique, a partir del contexto del problema,
c´omo podr´ıa no cumplirse esta condici´on y qu´e efectos conllevar´ıa.
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
(e) Tras discutir sus resultados, surge la idea de que las simulaciones realizadas tienen deficiencias, y que
por consiguiente los intervalos de confianza podr´ıan verse afectados (dada la alta variabilidad y poca
convergencia de los resultados). Proponga dos ideas con las cuales se puedan mejorar las simulaciones
y as´ı obtener mejores intervalos de confianza.
5

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
6

(b) Una mesa de votaci´on cuenta con aproximadamente 400 votantes. Comente: ¿en qu´e porcentaje
aumentar´ıa la cantidad esperada de iteraciones necesarias para simular el tiempo total de votaci´on
de todos los electores si, en lugar del algoritmo que utiliza la cota trapezoidal, se empleara en el
m´etodo de Aceptaci´on y Rechazo la cota constante t(x) = k m´as eficiente posible (es decir, aquella
que maximiza la probabilidad de aceptar un candidato)?
(a) Considere un m´etodo congruencial lineal (LCG) con a = 3, c = 5 y m = 31. Utilizando la semilla
x0 = 43, genere 5 instancias Uniforme(0, 1). Redondee a 3 cifras decimales en caso de ser necesario.
Indicaci´on: La semilla no cuenta dentro de las 5 instancias Uniforme(0, 1) a generar.
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
7

