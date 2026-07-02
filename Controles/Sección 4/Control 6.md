PONTIFICIA UNIVERSIDAD CAT´OLICA DE CHILE
ICS2123 Modelos Estoc´asticos 2026-1
Profesor: Andr´es Navarro C.
Control 6
En uno de los puestos de venta de bebidas del Mundial, los hinchas llegan a comprar seg´un un proceso
de Poisson con tasa constante λ. El puesto cuenta con 4 cajas en paralelo, cada una con tiempo de atenci´on
exponencial de tasa constante µ. La sala de espera tiene capacidad muy grande, que para efectos pr´acticos
se considera infinita.
1. Identifique qu´e tipo de sistema de espera es.
2. Indique las condiciones de equilibrio necesarias para el sistema.
3. Calcule la cantidad promedio de personas que llegar´an en una hora y encontrar´an vac´ıas todas las
cajas de atenci´on.
Soluci´on
1. Tipo de sistema.
Llegadas exponenciales (Markovianas), atenci´on exponencial (Markoviana), c = 4
servidores en paralelo y capacidad infinita. Se trata de un sistema M/M/c con c = 4, es decir, un M/M/4.
2. Condiciones de equilibrio.
La condici´on necesaria para el equilibrio es:
λ < 4µ.
3. Tasa de llegadas con el sistema vac´ıo.
La proporci´on de tiempo en que el sistema est´a vac´ıo
es P0, dada por
P0 =
1
c
X
n=0
λn
n! µn +
λc
c! µc ·
λ
cµ
1 −
λ
cµ
.
Como las llegadas siguen un proceso de Poisson de tasa λ, la fracci´on de clientes que encuentran el sistema
vac´ıo coincide con P0. Por lo tanto, la cantidad de clientes que en promedio llegan en una hora y encuentran
el sistema vac´ıo es
λ · P0 .
1

