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
Soluci´on: El grafo asociado a la matriz es:
1
3
4
7
2
5
6
0.2
0.4
1
1
0.4
0.5
0.5
0.3
0.9
0.1
0.7
0.8
0.2
Las clases y periodos asociadas a la matriz son las siguientes:
⋄{1, 4}: Recurrente positiva peri´odica, p = 2
⋄{3, 7}: Transiente peri´odica, p = 2
⋄{2, 5, 6}: Recurrente positiva aperi´odica
(b) Calcule F(1, 2) y F(3, 2).
Soluci´on: Ya que 1 pertenece a una clase recurrente positiva en la que no se encuentra 2, se tiene
que:
F(1, 2) = 0
Luego, para encontrar el valor de F(3, 2) se debe resolver el sistema:
F(3, 2) = 0.4F(7, 2)
F(7, 2) = 0.5F(3, 2) + 0.5
Del que se obtiene que:
F(3, 2) = 0.25
3

(c) Calcule E[(T(5, 2))].
Soluci´on: Para obtener lo pedido se debe resolver la ecuaci´on:
E[T(5, 2)] = 1 + 0.9E[T(5, 2)]
Obteniendo as´ı:
E[T(5, 2)] = 10
(d) Propuesto: Encuentre una expresi´on para Fk(6, 2), con k > 1. El resultado se debe dejar expresado
en funci´on de las probabilidades de transici´on en una etapa.
Soluci´on: Como se puede ver en el grafo que representa la matriz, para llegar de 6 a 2 se necesita
un m´ınimo de 2 transiciones. De esta manera, para obtener lo pedido se necesitar´an como m´ınimo las
dos transiciones P6,5 y P5,2. En caso de que se deseen m´as, basta con completar las transiciones con
combinaciones de P6,6 y P5,5, siempre procurando que la suma de las dos sumen k −2 transiciones,
pues las dos restantes son las necesarias para llegar del estado 6 al 2. De esta manera, la expresi´on
buscada corresponde a:
Fk(6, 2) =
k−2
X
i=0
(0.2)k−2−i(0.9)i(0.8)(0.1)
4

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
Soluci´on: Para esta situaci´on, consideremos la siguiente definici´on de estados representados de la
siguiente manera:
X(t), Y (t): X(t) representa el estado del tren en el d´ıa t (si est´a funcionando o esta en reparaci´on).
Para esto tenemos la notaci´on B que indicar´a que el tren se encuentra funcionando correctamente
y Ti que indica que el tren se encuentra en reparaci´on en el taller, en su d´ıa i. Por otro lado, Y (t)
se˜nala la cantidad de fallas que lleva registrado el tren, desde 0 hasta el m´aximo m −1.
Se utiliza tambi´en un estado auxiliar F que indica que el tren alcanz´o su tope de fallas y por tanto,
es retirado del sistema del metro.
El diagrama de la cadena (simplificado) ser´ıa as´ı:
B, 0
T1, 1
T2, 1
...
Tn, 1
B, 1
T1, 2
T2, 2
T2n, 2
B, 2
T1, 3
B,m−1
F
...
T2, 3
...
T3n, 3
B, 3
...
p
1 −p
1
1
1
p2
1 −p2
1
1
p3
1 −p3
pm
1 −pm
1
1
1
1
1
1
1
p4
1 −p4
1
La cadena posee muchas clases, la mayor´ıa son transientes aperi´odicas (que corresponde a todos los
estados excepto el ´ultimo) y una recurrente positiva aperi´odica (el ultimo estado).
5

(b) Considere que el tren esta funcionando correctamente y sin ninguna falla registrada, ¿Cuantos son
los d´ıas esperados hasta que el tren funcione correctamente, pero con una falla en el historial? Deje
expresada su respuesta en funci´on de n y p.
Soluci´on: b) En base a la cadena descrita, se solicita la cantidad de d´ıas esperados que se necesitan
para moverse desde el estado (B, 0) al (B, 1). O sea, se pide: E[T((B, 0); (B, 1))]. Desarrollando un
poco esta expresi´on:
E[T((B, 0); (B, 1))] = 1 + p · E[T((B, 0); (B, 1))] + (1 −p) · E[T((T1, 1); (B, 1))]
Ahora bien, se podr´ıa seguir desarrollando esta expresi´on de manera recursiva hasta llegar al nodo
final deseado. Sin embargo, resulta m´as sencillo darse cuenta que el termino E[T((T1, 1); (B, 1))] sale
de manera directa al observar la cadena. En particular, desde el estado (T1, 1) al (B, 1) se necesitan
n transiciones todas y cada una de ellas con probabilidad unitaria. Por ende E[T((T1, 1); (B, 1))] = n
y la expresion en un inicio se reduce a:
E[T((B, 0); (B, 1))] = 1 + p · E[T((B, 0); (B, 1))] + (1 −p) · E[T((T1, 1); (B, 1))]
E[T((B, 0); (B, 1))] = 1 + p · E[T((B, 0); (B, 1))] + (1 −p) · n
(1 −p) · E[T((B, 0); (B, 1))] = 1 + (1 −p) · n
E[T((B, 0); (B, 1))] = 1 + (1 −p) · n
1 −p
(c) El ejecutivo de metro ha contratado al profesional Alan Brito para lidiar con la situaci´on de fallas
de los trenes. En particular, Alan interviene en el ´ultimo d´ıa de reparaci´on del tren afectado (solo en
el ´ultimo d´ıa de reparaci´on, justo antes de que este vuelva a circulaci´on) y con probabilidad q logran
disminuir en uno, el historial de fallas del tren (si llevaba i fallas registradas, volver´a a circulaci´on en
la siguiente etapa pero con i −1 fallas registradas) y con probabilidad r/k (con k el numero de fallas
que lleva de momento) consiguen limpiar por completo el historial de fallas del tren.
Modifique la CMTD para incluir los cambios descritos en esta nueva descripci´on. Indique los cambios
en los estados y caracterice las clases presentes. Considere tambi´en, por simplicidad, la asignaci´on de
valores: p = 0.9, n = 2, m = 4, q = 0.5, r = 0.3.
Soluci´on: La cadena quedar´ıa representada de la siguiente manera:
6

B, 0
T1, 1
T2, 1
B, 1
T1, 2
T2, 2
T4, 2
B, 2
T1, 3
T3, 2
T2, 3
T3, 3
T4, 3
B, 3
F
T5, 3
T6, 3
0.9
0.1
0.2
0.81
0.19
1
0.72
0.28
1
1
1
1
1
0.63
0.37
1
0.8
0.5
0.15
0.35
1
1
0.5
0.1
0.4
1
La clasificaci´on de esta cadena cambia con respecto al caso anterior. Todos los estados excepto (B, 3)
que es un transiente aperi´odico, y F que es una recurrente positiva aperi´odica, se engloban en una
gran clase transiente aperi´odica.
7

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
Soluci´on: El modelo consta de 3 estados, y el grafo es el siguiente:
TV
P
M
p
1 −q
q
1 −r
r
1 −p
La cadena est´a compuesta por una ´unica clase Recurrente Positiva Aperi´odica, por lo que existen
todos l´ımites de las probabilidades l´ımite.
(b) Con respecto al comportamiento en el largo plazo, si TV es el estado donde un sobrino est´a viendo
TV ; M, el estado donde est´a viendo “memes”; y P donde est´a pellizcando, obtenga l´ımn→∞P (n)
ij
para i, j ∈S := {TV, P, M}.
Indicaci´on: Explique por qu´e los resultados, para esta cadena en espec´ıfico, no dependen de la
elecci´on del estado de origen i.
Soluci´on: Dado que se tiene que los tres estados pertenecen a una clase Recurrente Positiva Ape-
ri´odica, entonces la f´ormula a utilizar es:
l´ım
n→∞P (n)
jj
=
1
E[T(j, j)]
Esto puesto que, F(i, j) = 1 para cualquier i, j ∈S, por lo que:
l´ım
n→∞P (n)
ij
=
F(i, j)
E[T(j, j)] =
1
E[T(j, j)] = l´ım
n→∞P (n)
jj
Con eso basta obtener l´ımn→∞P (n)
jj
para j ∈S. Se obtienen por partes:
8

• Para j = TV :
E[T(TV, TV )] = 1 + pE[T(P, TV )]
E[T(P, TV )] = 1 + qE[T(M, TV )]
E[T(M, TV )] = 1 + (1 −r)E[T(M, TV )]
De la ´ultima ecuaci´on se desprende que
E[T(M, TV )] = 1
r
Y reemplzando en la segunda
E[T(P, TV )] = 1 + q
r = r + q
r
Y en la primera
E[T(TV, TV )] = 1 + pE[T(P, TV )] = 1 + pr + q
r
= 1 + pr + pq
r
= r + pr + qp
r
Por lo tanto
πT V := l´ım
n→∞P (n)
T V T V =
1
r+pr+qp
r
=
r
r + pr + qp
Por otra parte notar que
l´ım
n→∞P (n)
P T V = F(P, TV )
r+pr+qp
r
=
1
r+pr+qp
r
=
r
r + pr + qp = πT V
l´ım
n→∞P (n)
MT V = F(M, TV )
r+pr+qp
r
=
1
r+pr+qp
r
=
r
r + pr + qp = πT V
Queda propuesto verificar que F(i, j) ≡1
• Para j = M:
E[T(M, M)] = 1 + rE[T(TV, M)]
E[T(TV, M)] = 1 + (1 −p)E[T(TV, M)] + pE[T(P, M)]
E[T(P, M)] = 1 + (1 −q)E[T(TV, M)]
Resolviendo de manera an´aloga al caso anterior, tendr´ıamos
E[T(M, M)] = r + pr + qp
qp
Y
πM := l´ım
n→∞P (n)
MM =
1
r+pr+qp
qp
=
qp
r + pr + qp
An´alogamente al c´alculo de πT V , se obtiene que l´ımn→∞P (n)
MM = l´ımn→∞P (n)
T V M = l´ımn→∞P (n)
P M.
• Para j = P:
E[T(P, P)] = 1 + (1 −q)E[T(TV, P)] + qE[T(M, P)]
E[T(TV, P)] = 1 + (1 −p)E[T(TV, P)]
E[T(M, P)] = 1 + (1 −r)E[T(M, P)] + rE[T(TV, P)]
An´alogamente, resolviendo tendr´ıamos
E[T(P, P)] = r + pr + qp
pr
Y reemplazando
πP := l´ım
n→∞P (n)
P P =
1
r+pr+qp
pr
=
pr
r + pr + qp = l´ım
n→∞P (n)
MP = l´ım
n→∞P (n)
T V P
9

Para los siguientes incisos, considere que el sobrino parte mirando la TV en un minuto dado:
(c) ¿Cu´al es la probabilidad, luego de transcurridos muchos minutos, de que un sobrino est´e haciendo
algo indebido?
Soluci´on: Notar que las probabilidades l´ımite no dependen del estado inicial, por lo que el resultado
de las probabilidades l´ımite no se ve afectado. As´ı, la probabilidad de hacer algo indebido es:
πP + πM =
pr + pq
r + pr + pq
Si decimos la probabilidad de ver exactamente un ni˜no haciendo algo indebido tenemos:
 N
1

(πP + πM) πN−1
T V
Si en cambio lo vemos como la probabilidad de ver al menos un ni˜no haciendo algo indebido tenemos:
N
X
i=1
 N
i

(πP + πM)i πN−i
T V
(d) ¿Cu´al es la probabilidad, luego de transcurridos muchos minutos, de que el t´ıo encuentre a exactamente
K ∈N sobrinos buscando “memes” en su celular (con K ≤N)?
Soluci´on: Al igual que el inciso anterior, el estado inicial no afecta al resultado de las probabilidades
l´ımite, por lo que la probabilidad de encontrar exactamente K ni˜nos viendo memes es:
 N
K

πK
M (πP + πT V )N−K
(e) Si es que el t´ıo apaga la TV esf´erica en caso de ver a alguno de sus sobrinos pellizcando a otro, ¿cu´al
es la probabilidad, luego de transcurridos muchos minutos, de que el t´ıo apague la TV a sus sobrinos?
Soluci´on: Al igual que los incisos anteriores, el estado inicial no afecta al resultado de las probabilida-
des l´ımite. As´ı, la probabilidad de encontrar alg´un sobrino pellizcando a otro es igual al complemento
de no encontrar ninguno, o sea:
1 −(πT V + πM)N
10

