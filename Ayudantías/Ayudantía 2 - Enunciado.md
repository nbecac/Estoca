Pontificia Universidad Cat´olica de Chile
Escuela de Ingenier´ıa
Departamento de Ingenier´ıa Industrial y de Sistemas
ICS2123 – Modelos Estoc´asticos
Profesores Ver´onica Godoy y Andr´es Navarro
Ayudante Jefe Joaqu´ın Vergara
Primer Semestre 2026
Ayudant´ıa 2:
Repaso de Probabilidades II & Proceso Poisson I
Ayudantes: Emilio Pe˜na (emilio.penasepulveda@uc.cl) & Mart´ın Pe˜na (martinpena@uc.cl)
Resumen
Esperanza
⋄Caso Discreto: si X es una v.a discreta, su esperanza o valor esperado est´a dado por:
E[X] =
X
i∈ΦX
xi · P(X = xi)
⋄Caso Continuo: si X es una v.a continua, su esperanza o valor esperado est´a dado por:
E[X] =
∞
Z
−∞
xfX(x)dx
M´as generalmente, se tiene para una funci´on g cualquiera que:
E[g(X)] =





P
i g(xi) · P(X = xi)
si X es discreta
R ∞
−∞g(x)fX(x)dx
si X es continua
Varianza
Es una medida de la tendencia de una v.a de alejarse de su valor esperado. Est´a dada por:
Var[X] = E[(X −E[X])2] = E[X2] −E[X]2
Esperanza Condicional
⋄Caso Discreto: si X e Y son v.a discretas, la esperanza o valor esperado de X condicionado a que
Y = y est´a dado por:
E[X|Y = y] =
X
i∈ΦX
xi · P(X = xi|Y = y)
⋄Caso Continuo: si X e Y son v.a continuas, la esperanza o valor esperado de X condicionado a que
Y = y est´a dado por:
E[X|Y = y] =
∞
Z
−∞
xfX|Y (x, y)dx
1

Ley de Probabilidades Totales
⋄Caso Discreto: Si X e Y son v.a discretas, entonces:
P(X = k) =
X
i∈ΦX
P(X = k|Y = yi) · P(Y = yi)
⋄Caso Continuo: Si X e Y son v.a continuas, entonces:
FX(x) =
∞
Z
−∞
P(X ≤x|Y = y)fY (y)dy
Ley de Probabilidades Totales para la Esperanza
⋄Caso Discreto: Si X e Y son v.a discretas, entonces:
E[X] =
X
i∈ΦX
E[X|Y = yi] · P(Y = yi)
⋄Caso Continuo: Si X e Y son v.a continuas, entonces:
E[X] =
∞
Z
−∞
E[X|Y = y]fY (y)dy
Proceso de Conteo
Un proceso {N(t), t ≥0} es un proceso de conteo si N(t) representa el n´umero de eventos que han ocurrido
en el intervalo [0, t]. Algunas propiedades b´asicas son:
⋄N(t) es un entero no negativo.
⋄Si s < t, entonces N(s) ≤N(t) (N es una funci´on no decreciente).
⋄Si N(s, t) es el n´umero de eventos en el intervalo ]s, t], entonces: N(s, t) est´a dado por N(t) −N(s).1
Incrementos Independientes
El proceso de conteo {N(t), t ≥0} tiene incrementos independientes si para cualquier t, s ∈R+ la v.a.
N(s, s + t) es independiente del proceso {N(u), 0 ≤u ≤s}. Por lo tanto, el n´umero de eventos en
intervalos disjuntos son independientes. Por consiguiente, para cualquier u ∈[0, s] y k, r ∈Z+ se
tiene:
P(N(s, s + t) = k|N(u) = r) = P(N(s, s + t) = k)
Incrementos Estacionarios
El proceso de conteo {N(t), t ≥0} tiene incrementos estacionarios si la distribuci´on de probabilidades de
N(s, s + t) no depende de s. Es decir, la distribuci´on depende del largo del intervalo de tiempo y
no de su ubicaci´on temporal. Por tanto, para cualquier par s′, s ∈R+ y k ∈R+ fijo:
P(N(s, s + t) = k) = P(N(s′, s′ + t) = k)
1Extra´ıdo de material del curso ICS2123
2

Propiedad de orden
El proceso de conteo {N(t), t ≥0} tiene la propiedad de orden si cumple:
⋄P(N(h) = 1) = λh + o(h)
⋄P(N(h) ≥2) = o(h)
En otras palabras, si despreciamos el t´ermino o(h), y consideramos h muy peque˜no,
N(h) ≈
(
0 con probabilidad 1 −λh,
1 con probabilidad λh
En particular, el proceso solamente tendr´a “saltos” unitarios.
Proceso de Poisson
Un proceso de conteo {N(t), t ≥0} es un Proceso de Poisson con tasa λ > 0 si cumple con:
⋄Incrementos independientes.
⋄Incrementos estacionarios.
⋄Propiedad de orden.
N(t) ∼Poisson(λt) →P(N(t) = k) = (λt)ke−λt
k!
Distribuci´on del tiempo entre eventos en un Proceso de Poisson
Los tiempos entre eventos consecutivos en un Proceso de Poisson son variables aleatorias independientes e
id´enticamente distribuidas (iid) que siguen una distribuci´on Exponencial con par´ametro λ. En particular,
para cualquier i ∈N :
Ti ∼Exp(λ) →P(Ti ≥t) = e−λt, t ≥0
T´ıpicamente denotaremos Ti al tiempo transcurrido desde el (i −1)-´esimo evento hasta el i-´esimo evento.
Resultado Inverso
Si un Proceso de Conteo satisface Ti
iid
∼Exp(λ), luego corresponde a un Proceso Poisson de tasa λ.
3

Problema 1
(a) Considere dos monedas, M1 y M2, con las siguientes caracter´ısticas,
P(obtener cara|M1) = 3/5
P(obtener cara|M2) = 1/5
Suponga que se escoge una de las dos monedas al azar y se lanza repetidamente al aire. Si los dos
primeros lanzamientos de la moneda escogida resultaron ser sello, ¿cu´al es el n´umero esperado de
lanzamiento adicionales para obtener una cara?
Hint: Si la probabilidad de tener ´exito en un experimento es θ, entonces X ∼Geom´etrica(θ) modela
el n´umero de necesarios de experimentos hasta obtener un ´exito. Adem´as,
E[X] = 1
θ
(b) Considere ahora un modelo m´as general. Suponga que la probabilidad de obtener cara al lanzar una
moneda es desconocida y se denota por X. Ante la ausencia de informaci´on previa sobre su valor, se
modela como
X ∼Uniforme(0, 1).
Condicional en X = x, se realizan 5 lanzamientos independientes de la moneda. Sea Y la variable
aleatoria que denota el n´umero de caras obtenidas. Luego,
Y | X = x ∼Binomial(5, x).
Suponga que en los cinco lanzamientos se observaron exactamente 3 caras, es decir, Y = 3. Calcule
E[X | Y = 3].
4

Problema 2
Una central telef´onica recibe llamadas siguiendo un Proceso de Poisson con tasa λ > 0 llamadas por minuto.
(a) Entre el minuto 10 y el 20 se registraron exactamente 5 llamadas. Calcule la probabilidad de que
entre el minuto 15 y el 30 se registren exactamente 8 llamadas.
(b) Suponga que a los 20 minutos ya han llegado 50 llamadas en total. ¿Cu´al es la probabilidad de que
en los primeros 11 minutos hayan entrado a lo m´as 9 llamadas y, adem´as, en los primeros 15 minutos
hayan entrado al menos 10 llamadas?
5

Problema 3 [T1- 2025-2]
Sea {N(t), t ≥0} un Proceso de Poisson de par´ametro λ > 0. Se consideran los instantes de ocurrencia
(Sj)j∈N y los tiempos entre eventos (Tj)j∈N.
Desarrolle una expresi´on expl´ıcita para
P(N(4, 12) = 10,
N(2)+5
X
j=1
Tj ≤8 | S9 > 6).
Hint: Reescriba la probabilidad solicitada utilizando s´olo la notaci´on del Proceso de Conteo N(t), para
luego calcular.
6

