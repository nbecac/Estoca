Pontificia Universidad Cat´olica de Chile
Escuela de Ingenier´ıa
Departamento de Ingenier´ıa Industrial y de Sistemas
ICS2123 – Modelos Estoc´asticos
Profesores Ver´onica Godoy y Andr´es Navarro
Ayudante Jefe Joaqu´ın Vergara
Primer Semestre 2026
Ayudant´ıa 8:
CMTD II
Ayudantes: Emilio Pe˜na (emilio.penasepulveda@uc.cl) & Mart´ın Pe˜na (martinpena@uc.cl)
Resumen
Cadenas de Markov en Tiempo Discreto (CMTD)
Una CMTD es un proceso estoc´astico (una variable aleatoria que evoluciona en etapas) que toma valores
denominados estados, donde Xn = i significa que el sistema se encuentra en el estado i en la etapa n.
Es importante mencionar que un proceso estoc´astico {Xn, n ∈N} es una CMTD si cumple con 2 propie-
dades.
Estas son:
⋄Propiedad Markoviana: “La distribuci´on de probabilidad de la siguiente etapa depende de las etapas
anteriores a trav´es de la etapa actual”. Es decir, la informaci´on que se tiene del pasado es redundante
sabiendo el estado del presente. Formalmente diremos que se debe cumplir:
P(Xn+1 = j|Xn = i, Xn−1 = i0, ..., X0 = i0) = P(Xn+1 = j|Xn = i)
Para cualquier j, i, in−1, ..., i0 en el conjunto de estados posibles de Xn.
⋄Propiedad Estacionaria: “La probabilidad de que el proceso cambie de un estado a otro en un determi-
nado n´umero de etapas s´olo depende de los estados y la cantidad de etapas en cuesti´on”. Es decir, esta
probabilidad es independiente del n´umero de etapas que lleva el proceso. Formalmente esto equivale
a decir que P(Xn+1 = j|Xn = i) s´olo depende de i, j y no de n. Por ejemplo, P(Xn+k = j|Xn = i)
depende del hecho de que transcurren k etapas y de (i, j), pero no del hecho de que en la n-´esima
etapa es cuando se estuvo en el estado i.
Finalmente esto implica que la probabilidad de pasar del estado i al estado j en una etapa es constante
dada por:
Pij = P(Xn+1 = j|Xn = i) ∀n ∈Z≥0.
Esta definici´on es la base sobre la que se construye cualquier probabilidad de inter´es respecto a las CMTD,
y se trabajar´a a continuaci´on en el curso.
Ecuaci´on de Chapman-Kolmogorov
La siguiente ecuaci´on nos permite calcular la probabilidad de transici´on en n etapas;
P (n)
ij
=
∞
X
k=0
P (m)
ik
· P (n−m)
kj
∀n ≥m ≥0 y ∀i, j
Matriz de transici´on en n etapas
Denominaremos P (n) a la matriz de transici´on en n etapas. Esta matriz est´a formada con los P (n)
ij
de la
CMTD.
1

Distribuci´on de probabilidades del proceso
Sea Xn, n = 0, 1, 2, ... una CMTD donde se conoce f (0). Se puede calcular f (n) como:
f (n)⊤= f (0)⊤P n
Clasificaci´on de estados
⋄Estado recurrente: Eventualmente vuelvo. Si F(i, i) = P(T(i, i) < ∞) = 1
• Recurrente nulo: E[T(i, i)] = ∞(solo en cadenas infinitas)
• Recurrente positivo E[T(i, i)] < ∞
⋄Estado transiente: En alg´un minuto, voy a dejar de volver para siempre. Si F(i, i) = P(T(i, i) < ∞) <
1
Comunicaci´on entre estados y clases
⋄Comunicaci´on: Dos estados i, j se comunican si hay un camino para ir de i a j y un camino para ir
de j a i. Se denota como i ←→j.
• Reflexi´on: i ←→i
∀i
• Simetr´ıa: i ←→j ⇒j ←→i
• Transitividad: Si i ←→k y k ←→j ⇒i ←→j
⋄Clases: Dos estados son de la misma clase si se comunican. Las clases constituyen una partici´on del
conjunto de los estados y todos los estados de una clase son del mismo tipo.
Periodicidad
⋄Un estado es peri´odico si, partiendo desde i s´olo es posible volver a i en un n´umero de etapas que sea
m´ultiplo de un n´umero entero mayor a uno.
⋄Periodo d ∈N es el M´aximo Com´un Divisor del n´umero de etapas para que el estado vuelva a s´ı
mismo en un n´umero n ∈N de etapas.
⋄Por convenci´on si d = 1, entonces se considera aperi´odico.
2

Problema 1
Considere una Cadena de Markov en Tiempo Discreto con estados {1, 2, 3, 4, 5, 6, 7} dada por la siguiente
matriz de transici´on:










1
2
3
4
5
6
7
1
0
0
0
1
0
0
0
2
0
0
0
0
0.3
0.7
0
3
0.2
0
0
0.4
0
0
0.4
4
1
0
0
0
0
0
0
5
0
0.1
0
0
0.9
0
0
6
0
0
0
0
0.8
0.2
0
7
0
0.5
0.5
0
0
0
0










(a) Determine las clases de estados y clasifique todos los estados en transientes, recurrentes positivos,
o recurrentes nulos, y determine si son aperi´odicos o peri´odicos, y el valor del periodo si es que
corresponde.
(b) Calcule F(1, 2) y F(3, 2).
(c) Calcule E[(T(5, 2))].
(d) Propuesto: Encuentre una expresi´on para Fk(6, 2), con k > 1. El resultado se debe dejar expresado
en funci´on de las probabilidades de transici´on en una etapa.
3

Problema 2
Los expertos del metro de Santiago han realizado un estudio sobre la vida ´util de los trenes. Han acordado
que si un tren cualquiera est´a funcionando correctamente, entonces tiene una probabilidad p de que al d´ıa
siguiente siga funcionando correctamente, en caso contrario deber´a ser llevado a reparaci´on. En primera
instancia, el tren pasar´a n d´ıas en el taller antes de ser puesto nuevamente en funcionamiento.
Por la seguridad de todas las entidades que componen este sistema, las autoridades han designado un
n´umero m´aximo de fallas que puede sufrir un tren antes de ser quitado de servicio por completo, siendo
este m fallas totales. Si es que el tren llega a este n´umero de fallas, se saca de inmediato de circulaci´on, sin
pasar por el taller antes. Asimismo, el equipo de Metro ha descubierto que, cada vez que el tren falla su
eficiencia se ve afectada de las siguientes maneras:
⋄Por cada falla, el taller de reparaci´on necesitar´a n d´ıas m´as para arreglar el metro una vez vuelva a
circulaci´on.
⋄Luego de cada falla, la probabilidad de que siga funcionando correctamente (al volver a sus actividades
cotidianas) es ponderada por un factor p. Es decir, si el metro ha fallado k veces, la probabilidad de
no fallar en la etapa actual es de pk+1.
(a) Modele la situaci´on descrita como una Cadena de Markov en Tiempo Discreto, explicitando e indi-
cando los estados y las respectivas probabilidades de transici´on, junto con su diagrama. Clasifique las
clases de estados seg´un corresponda.
(b) Considere que el tren esta funcionando correctamente y sin ninguna falla registrada, ¿Cuantos son
los d´ıas esperados hasta que el tren funcione correctamente, pero con una falla en el historial? Deje
expresada su respuesta en funci´on de n y p.
(c) El ejecutivo de metro ha contratado al profesional Alan Brito para lidiar con la situaci´on de fallas
de los trenes. En particular, Alan interviene en el ´ultimo d´ıa de reparaci´on del tren afectado (solo en
el ´ultimo d´ıa de reparaci´on, justo antes de que este vuelva a circulaci´on) y con probabilidad q logran
disminuir en uno, el historial de fallas del tren (si llevaba i fallas registradas, volver´a a circulaci´on en
la siguiente etapa pero con i −1 fallas registradas) y con probabilidad r/k (con k el numero de fallas
que lleva de momento) consiguen limpiar por completo el historial de fallas del tren.
Modifique la CMTD para incluir los cambios descritos en esta nueva descripci´on. Indique los cambios
en los estados y caracterice las clases presentes. Considere tambi´en, por simplicidad, la asignaci´on de
valores: p = 0.9, n = 2, m = 4, q = 0.5, r = 0.3.
4

Problema 3 (Propuesto)
Un amoroso t´ıo tiene N ∈N sobrinos que lo han ido a visitar a su casa esta tarde. Como este t´ıo conoce
a sus sobrinos los ha puesto en c´ırculo en la sala de estar a mirar TV (s´ı, en una televisi´on de pantalla
esf´erica!), ya que sabe que sus sobrinos toman decisiones (no siempre correctas) minuto a minuto.
Espec´ıficamente, este t´ıo sabe que si un sobrino est´a concentrado mirando la TV esf´erica en un minuto,
seguir´a concentrado mirando TV con probabilidad 1−p el siguiente minuto, o bien puede intentar pellizcar
a uno de sus primos con probabilidad p ∈(0, 1) en el siguiente minuto. En dicho caso, pellizcar´a a su primo
sentado a su izquierda o a su primo sentado a su derecha durante el siguiente minuto, decisi´on que toma
con igual probabilidad. Luego de pellizcar a alguno de sus primos pueden pasar dos cosas; con probabilidad
q ∈(0, 1) este sobrino no logra enojar a su primo, por lo que pasar´a el siguiente minuto buscando en su
celular un buen “meme” para entretenerse; o con probabilidad 1 −q este sobrino logra enfadar a su primo
por lo que se vuelve a concentrar en la TV esf´erica. Tras un minuto, si un sobrino que se encuentra mirando
su celular puede encontrar un “meme” interesante, entonces vuelve a concentrarse en la TV esf´erica -lo
que ocurre con probabilidad r ∈(0, 1)- y en caso de no encontrar un “meme” interesante en ese minuto
continua mirando el celular durante el siguiente minuto en busca de un buen “meme”.
Finalmente, este t´ıo puede aparecer en la sala de estar en cualquier momento y dada su experiencia, con
solo mirar la cara de sus sobrinos, sabe si est´an haciendo algo indebido.
(a) Modele el comportamiento de un sobrino cualquiera de este t´ıo como una Cadena de Markov en Tiem-
po Discreto. Dibuje el grafo de la cadena identificando los estados y las probabilidades de transici´on.
Luego, clasifique la cadena y indique si es que existen todos los l´ımn→∞P (n)
ij
para cualquier i, j del
conjunto de estados definido.
(b) Con respecto al comportamiento en el largo plazo, si TV es el estado donde un sobrino est´a viendo
TV ; M, el estado donde est´a viendo “memes”; y P donde est´a pellizcando, obtenga l´ımn→∞P (n)
ij
para i, j ∈S := {TV, P, M}.
Indicaci´on: Explique por qu´e los resultados, para esta cadena en espec´ıfico, no dependen de la
elecci´on del estado de origen i.
Para los siguientes incisos, considere que el sobrino parte mirando la TV en un minuto dado:
(c) ¿Cu´al es la probabilidad, luego de transcurridos muchos minutos, de que un sobrino est´e haciendo
algo indebido?
(d) ¿Cu´al es la probabilidad, luego de transcurridos muchos minutos, de que el t´ıo encuentre a exactamente
K ∈N sobrinos buscando “memes” en su celular (con K ≤N)?
(e) Si es que el t´ıo apaga la TV esf´erica en caso de ver a alguno de sus sobrinos pellizcando a otro, ¿cu´al
es la probabilidad, luego de transcurridos muchos minutos, de que el t´ıo apague la TV a sus sobrinos?
5

