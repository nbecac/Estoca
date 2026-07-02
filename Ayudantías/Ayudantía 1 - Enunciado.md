Pontificia Universidad Cat´olica de Chile
Escuela de Ingenier´ıa
Departamento de Ingenier´ıa Industrial y de Sistemas
ICS2123 – Modelos Estoc´asticos
Profesores Ver´onica Godoy y Andr´es Navarro
Ayudante Jefe Joaqu´ın Vergara
Primer Semestre 2026
Ayudant´ıa 1:
Repaso de Probabilidades
Ayudantes: Emilio Pe˜na (emilio.penasepulveda@uc.cl) & Mart´ın Pe˜na (martinpena@uc.cl)
Resumen
Propiedades b´asicas
⋄Probabilidad del complemento: P(E) = 1 −P(E)
⋄Probabilidad del vac´ıo: P(∅) = 0
⋄Probabilidad para la uni´on de dos eventos: P(E ∪F) = P(E) + P(F) −P(E ∩F)
Si E y F son disjuntos (E ∩F = ∅), entonces: P(E ∪F) = P(E) + P(F)
⋄Sea E y F tal que E ⊆F, entonces: P(F) = P(F\E) + P(E), P(E) ≤P(F)
Probabilidad condicional
Sean E, F ⊆Ωeventos cualquiera. Se denota P(E|F) a la probabilidad de que ocurra el evento E dado que
ocurri´o F, y se tiene que satisface la siguiente relaci´on:
P(E|F) = P(E ∩F)
P(F)
Probabilidades totales
Sean E1, E2, ..., En eventos mutuamente excluyentes (es decir, Ei ∩Ej = ∅∀i ̸= j), tal que Sn
i=1 Ei = Ωy
F un evento cualquiera de Ω, entonces:
P(F) =
n
X
i=1
P(F|Ei) · P(Ei)
Teorema de Bayes (simple)
Sean E y F dos eventos de Ω. Se tiene que:
P(E|F) = P(F|E) · P(E)
P(F)
Teorema de Bayes (completo)
Sean E1, E2, ..., En eventos mutuamente excluyentes tal que Sn
i=1 Ei = Ωy sea F tal que P(F) > 0.
Entonces:
P(Ei|F) =
P(F|Ei) · P(Ei)
Pn
i=1 P(F|Ei) · P(Ei)
1

Eventos independientes
Diremos que los eventos E y F son independientes si y solo si
P(E|F) = P(E)
Que es equivalente, por Ley de Probabilidad Condicional, a:
P(E ∩F) = P(F) · P(E)
Variable Aleatoria
Es una funci´on X : Ω→R, que a cada elemento del espacio muestral le asigna un n´umero real. Puede ser:
⋄Discreta: toma una cantidad numerable de valores.
⋄Continua: toma valores en un conjunto continuo (no numerable).
Funci´on de Distribuci´on Acumulada
Para cada v.a X, se define su funci´on de distribuci´on acumulada (o ”cdf”) como:
FX(x) = P(X ≤x)
Esta funci´on caracteriza a la variable aleatoria X, es decir, identificando la cdf podemos reconocer a que
variable aleatoria corresponde, al igual que las siguientes funciones.
Funci´on de Probabilidad
Si X es una v.a discreta, se define como:
pX(xi) = P(X = xi)
de manera que
X
i∈ΦX
pX(xi) = 1
donde ΦX ⊆N es el soporte de X, es decir los valores tales que pX ̸= 0.
Funci´on de Densidad
Si X es una v.a continua, se define como:
fX(x) = dFX(x)
dx
de manera que
∞
Z
−∞
fX(x)dx =
Z
ΦX
fX(x)dx = 1,
fX(x) ≥0 ∀x ∈R
donde, nuevamente ΦX ⊆R es el soporte de X, dicho de otra manera donde fX ̸= 0.
Adem´as,
FX(x) =
x
Z
−∞
f(t)dt
2

y
P(a ≤X ≤b) =
b
Z
a
f(t)dt = F(a) −F(b)
M´as generalmente, una funci´on de densidad puede ser cualquier funci´on no negativa y continua a tramos
que integre 1.
3

Problema 1
En un sistema de monitoreo de un supermercado, se estudia el tiempo continuo que transcurre hasta la
llegada del pr´oximo cliente en las cajas. Se sabe que existen dos tipos de clientes: habituales (Tipo A) y
express (Tipo B).
Sean X e Y las variables aleatorias continuas que representan el tiempo (en minutos) que transcurre hasta
la llegada del pr´oximo cliente Tipo A y Tipo B, respectivamente. Se asume que las llegadas de ambos tipos
de clientes son eventos independientes. Las funciones de densidad de probabilidad para cada variable est´an
dadas por:
fX(x) =
(
αe−αx
si x ≥0
0
en otro caso
fY (y) =
(
βe−βy
si y ≥0
0
en otro caso
donde α > 0 y β > 0 son par´ametros conocidos del sistema.
a) Calcule la probabilidad de que el pr´oximo cliente, sin importar de qu´e tipo sea, llegue despu´es de t
minutos (t > 0). Exprese su resultado en funci´on de α, β y t.
b) Suponga que han transcurrido s minutos (0 < s < t) y el sistema le informa que a´un no ha llegado
ning´un cliente Tipo B. Dado este escenario, ¿cu´al es la probabilidad de que el primer cliente Tipo B
llegue despu´es de t minutos? Justifique anal´ıticamente cada paso.
c) El administrador del supermercado nota que la tasa de llegada β de los clientes Tipo B var´ıa seg´un
el clima. Si el d´ıa est´a soleado (evento S), la funci´on de densidad de Y utiliza el par´ametro β1. Si el
d´ıa est´a lluvioso (evento L), utiliza el par´ametro β2. Se sabe hist´oricamente que la probabilidad de
que un d´ıa est´e lluvioso es p. Si usted observa en las c´amaras que el primer cliente Tipo B tard´o m´as
de t minutos en llegar, ¿cu´al es la probabilidad de que hoy sea un d´ıa lluvioso?
4

Problema 2
El Centro de Meteorolog´ıa UC desarroll´o un aparato para medir la cantidad de mm de agua que caen en
un d´ıa de lluvia en el campus, con el fin de tomar las medidas correspondientes. Cuando se sobrepasan
los 10 mm, existe riesgo de que la infraestructura se vea afectada, lo que ocurre con una probabilidad del
45 %. Sin embargo, el aparato a´un est´a en fase de prueba y falla en la medici´on un 15 % de las veces, de
forma independiente a la cantidad de agua ca´ıda. Cuando falla, indica que se super´o el nivel de riesgo con
probabilidad 0.6 y que no se super´o con probabilidad 0.4. A partir de lo anterior, responda:
a) ¿Cu´al es la probabilidad de que el aparato indique que se sobrepas´o el l´ımite?
b) Si el aparato indica que se sobrepas´o el l´ımite ¿Cu´al es la probabilidad de que efectivamente se haya
sobrepasado ese d´ıa?
c) ¿Cu´al es la probabilidad de que el aparato registre lo realmente ocurrido?
5

Problema 3
Un equipo de ingenieros de datos deportivos est´a dise˜nando un modelo estoc´astico predictivo para la final
de un torneo de f´utbol. Para modelar la cantidad de goles que anota cada equipo durante los 90 minutos
reglamentarios, definen las siguientes variables aleatorias:
⋄X: Cantidad de goles anotados por el Equipo A.
⋄Y : Cantidad de goles anotados por el Equipo B.
A partir del an´alisis de datos hist´oricos, los ingenieros determinan que X e Y se pueden modelar mediante
funciones de probabilidad de Poisson con tasas α y β respectivamente (donde α, β > 0). Adem´as, asumen
que la cantidad de goles que anota un equipo no afecta la cantidad de goles que anota el otro, por lo que
X e Y son variables aleatorias independientes.
a) La probabilidad de que el Equipo A gane el partido con un marcador exacto de 3 a 1.
b) La probabilidad marginal de que el Equipo A gane el partido durante los 90 minutos reglamentarios
(es decir, que anote estrictamente m´as goles que el Equipo B).
c) Suponga que el partido acaba de terminar y el sensor del estadio reporta que, en total, hubo n goles
en el partido (n ≥1), pero por una falla de transmisi´on no se sabe qui´en los anot´o. Dado este evento,
encuentre la probabilidad de que el Equipo A haya ganado el partido.
6

