Pontificia Universidad Cat´olica de Chile
Escuela de Ingenier´ıa
Departamento de Ingenier´ıa Industrial y de Sistemas
ICS2123 – Modelos Estoc´asticos
Profesores Ver´onica Godoy y Andr´es Navarro
Ayudante Jefe Joaqu´ın Vergara
Primer Semestre 2026
Ayudant´ıa 14:
Sistemas de Espera II
Ayudantes: Emilio Pe˜na (emilio.penasepulveda@uc.cl) & Mart´ın Pe˜na (martinpena@uc.cl)
Problema 1
Considere que al Achoclonados de la Universidad llegan alumnos hambrientos seg´un un Proceso Poisson a
tasa λ > 0 alumnos/minuto. El local cuenta con una ´unica fila y se atiende seg´un l´ogica FIFO. Se cuenta
con cinco trabajadores cuyos tiempos de atenci´on distribuyen exponencial, de par´ametro µ > 0, en minutos.
Cuando hay m > 14 personas en cola, la tasa de llegada disminuye a 0 < αm < λ alumnos/minuto (notar
que depende de la cantidad m personas en cola). Asimismo, una vez que hay n ≥15 personas en el sistema,
los trabajadores aumentan su velocidad de atenci´on, pasando a una tasa γ > 0 alumnos/minuto. Tambi´en,
cuando hay m ≥20 personas en cola, cada una de estas personas en la cola, con probabilidad pn ∈(0, 1)
(estrictamente creciente en n) puede irse, esto seg´un un tiempo que distribuye exponencial con par´ametro
βn > 0, en minutos, donde n representa la cantidad de personas en el sistema. Dos de los trabajadores se
amurran cuando hay n > 30 personas en el sistema, momento en el cual se toman un descanso forzado
hasta que la cantidad de gente vuelva a restaurarse. Por ´ultimo, considere que para no sobreexplotar a los
trabajadores, se establece un m´aximo de 40 personas en el sistema. A partir de lo anterior, responda:
(a) Modele la ocupaci´on de Achoclonados seg´un una Cadena de Markov en Tiempo Continuo, identifi-
cando claramente la variable de estado, el espacio de estados y las tasas de transici´on instant´anea. Se
le recomienda apoyarse de un grafo.
(b) Obtenga una expresi´on expl´ıcita (en funci´on de las tasas enunciadas) para la probabilidad de que en
el largo plazo el local est´e vac´ıo.
(c) Suponga por solo este inciso que el sistema cuenta con capacidad infinita, indique la(s) condicion(es)
para que el sistema no colapse.
(d) Indique como obtener las probabilidades en el largo plazo para cada estado. Luego, determine expre-
siones para obtener las m´etricas de desempe˜no L, Lq, W y Wq.
1

Problema 2
Consideremos una plaza de peaje donde llegan veh´ıculos de acuerdo a un proceso de Poisson con tasa
λ veh´ıculos/minuto. Cada veh´ıculo tiene, independientemente, una probabilidad p, 0 < p < 1, de ser
autom´ovil y una probabilidad 1 −p de ser un cami´on. La plaza de peajes cuenta con tres cajas, que
llamaremos caja 1, 2 y 3. Las cajas 1 y 2 atienden solamente autom´oviles y la caja 3 atiende solamente
camiones. Si hay al menos una caja disponible del tipo que le corresponde, un veh´ıculo que llega es atendido
de inmediato, si esto no es el caso los autom´oviles que llegan esperan en una cola hasta ser atendidos y
los camiones esperan su turno en otra cola. La atenci´on de autom´oviles y de camiones es por orden de
llegada. El tiempo de atenci´on de cada caja de autom´oviles es exponencial con valor esperado 1
µ minutos y
el tiempo para la caja de camiones es exponencial con valor esperado 1
β . Los tiempos de atenci´on son todos
independientes y suponga que µ > λ y β > λ
a) Defina variables de estado. Indique cual es el conjunto de estados posibles.
b) Especifique las transiciones posibles y las tasas de transici´on instant´aneas.
c) Obtenga las expresiones explicitas para las probabilidades en el largo plazo.
d) Escriba una expresi´on para la fracci´on de tiempo, en el largo plazo, en que hay m´as autom´oviles que
camiones en la plaza de peaje. Asuma conocidas las probabilidades de largo plazo.
e) Se propone calcular el tiempo medio de permanencia (en el largo plazo) de un veh´ıculo cualquiera en
la plaza de peajes empleando la expresi´on LA+LC
λ
, donde LA es el n´umero medio de autos en la plaza
y LC es el n´umero medio de camiones en la plaza. Justifique si esta expresi´on es correcta o no.
2

Problema 3 (Propuesto)
Clientes llegan a una peluquer´ıa con una tasa media de 5 clientes por hora y los tiempos entre llegadas
est´an distribuidos exponencialmente. En esta peluquer´ıa hay un solo peluquero y 4 sillas para los clientes
que llegan cuando el peluquero est´a ocupado. La ley de prevenci´on de incendios limita el n´umero total
de clientes en la peluquer´ıa, en cualquier momento, a un m´aximo de 5. Los clientes que llegan cuando la
peluquer´ıa est´a llena no pueden entrar. El tiempo de servicio distribuye exponencialmente con una media
que depende del n´umero de clientes en la peluquer´ıa (Cuadro 1).
N´umero de clientes en la peluquer´ıa
1
2
3
4
5
Tiempo medio de servicio por cliente (min.)
9
10
10
13
20
Cuadro 1: Tiempo de servicio en minutos en funci´on de la cantidad de clientes
(a) Determine el n´umero promedio de clientes en espera.
(b) Determine el tiempo de espera promedio.
(c) Determine el porcentaje del tiempo que el peluquero est´a inactivo en el largo plazo.
(d) Determine el valor esperado de clientes que no ingresan a la peluquer´ıa.
3

