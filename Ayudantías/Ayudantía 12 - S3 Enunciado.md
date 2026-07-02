Pontificia Universidad Cat´olica de Chile
Escuela de Ingenier´ıa
Departamento de Ingenier´ıa Industrial y de Sistemas
ICS2123 – Modelos Estoc´asticos
Profesores Ver´onica Godoy y Andr´es Navarro
Ayudante Jefe Joaqu´ın Vergara
Primer Semestre 2026
Ayudant´ıa 12:
Repaso I2
Ayudantes: Emilio Pe˜na (emilio.penasepulveda@uc.cl) & Mart´ın Pe˜na (martinpena@uc.cl)
Problema 1
El fin de semana pr´oximo usted ir´a a jugar un partido de tenis en contra de su amigo/a. Usted est´a
convencido/a de que posee una probabilidad 0 < p < 1 de ganar cada punto.
En un partido de tenis, cuando los jugadores est´an empatados con 40 puntos (”iguales”), uno de los
jugadores debe ganar dos puntos m´as que su contrincante para ganar el juego. Si est´an empatados y un
jugador gana un punto, se dice que tiene ventaja, si el mismo jugador gana el siguiente punto, gana el
juego, pero si el otro jugador gana el siguiente punto, se pierde la ventaja y vuelven a quedar ”iguales”.
Considere que en un cierto momento, usted est´a ”iguales” con su contrincante.
(a) Construya la CMTD que modele el juego desde la posici´on de ”iguales” hasta el final del juego. Luego
responda, ¿Cu´al es la probabilidad que usted gane ese juego? (Considerando que se parte desde la
igualdad)
(b) ¿Cu´antos puntos, en promedio, se jugar´an hasta que termine ese juego?
(c) ¿Cu´al es la probabilidad que se disputen exactamente 4 puntos para terminar el juego?
1

Problema 2
Suponga un dado cargado que se comporta del siguiente modo: si en el lanzamiento anterior sali´o el n´umero
i (con i = 1, 2, 3, 4, 5) es imposible que obtengamos el n´umero i + 1 en el lanzamiento actual. Adem´as, cada
vez que se lanza el dado existe un 50 % de probabilidades de que salga el mismo n´umero que sali´o en el
lanzamiento anterior y un 50 % de probabilidades de que salga cualquiera de los otros posibles n´umeros (en
forma equiprobable).
Por ´ultimo, cuando obtuvimos el n´umero 6 en el lanzamiento anterior, es posible obtener solo tres resultados
equiprobables en el lanzamiento actual, pudiendo sacar los n´umeros 1, 3 y 6. A partir de lo anterior,
responda:
(a) Argumente por qu´e la situaci´on anterior se puede modelar como una CMTD.
(b) Construya el diagrama (o la matriz de probabilidades de transici´on en una etapa) de la CMTD
asociada a la situaci´on anterior. Luego, identifique las clases de estados y clasif´ıquelas como transien-
tes, recurrentes positivas o nulas, indicando adem´as si son aperi´odicas o peri´odicas (y el per´ıodo, si
corresponde).
(c) Se le entrega el vector de posiciones iniciales f (0) = ( 1
2, 0, 0, 1
4, 0, 1
4) . Calcule el vector de posiciones
en el turno n´umero 2.
(d) Justifique la existencia (o no existencia) de distribuci´on estacionaria. En caso de existir plantee las
ecuaciones para obtener las probabilidades en el largo plazo.
(e) ¿Cu´al es la proporci´on del tiempo en el largo plazo que usted cae en el n´umero 2 viniendo desde un
n´umero impar? (Considere las probabilidades de largo plazo como conocidas)
2

Problema 3
Considere que usted posee un negocio que vende sobres del ´Album del Mundial. Actualmente su local solo
tiene capacidad de inventario para almacenar K (n´umero par) cajas de sobres a la vez.
Considere que las cajas llegan a su negocio por 2 distribuidoras. La primera de ellas, en cada entrega le
trae solo 1 caja, donde las llegadas se modelan mediante un Proceso Poisson de tasa λ. La segunda, en
cada env´ıo le trae K/2 cajas, donde los tiempos entre env´ıos siguen una distribuci´on exponencial con media
1/β. Si debido a la capacidad no puede almacenar cualquiera de los env´ıos, estos simplemente se ir´an a
otro local.
En cuanto a la venta, el tiempo que dura cada una de las cajas en el almac´en antes de ser vendidas sigue
una distribuci´on exponencial de tasa µ, con la salvedad que cuando hay m´as de K/2 cajas en el almac´en
se decide lanzar ofertas, las cuales aumentan la velocidad en las ventas en un X %
(a) Modele la evoluci´on temporal de la cantidad de cajas en su almac´en como una CMTC.
(b) Determine la distribuci´on l´ımite y plantee las ecuaciones que permitan encontrar estas probabilidades.
Ahora usted quiere ampliar su negocio, para lo que arrienda un galp´on con tal de tener m´as espacio para
las cajas de sobres. Esto le permite tener una capacidad pr´acticamente infinita en el galp´on, pero a costa
de que ya no se lanzan las ofertas que aumentan en X % la velocidad de venta. (los tiempos de duraci´on
de las cajas antes de ser vendidas solo consideran a las cajas del almac´en no a las del galp´on).
En cuanto a las distribuidoras, debido a los cambios, la segunda deja de trabajar con usted y la primera
cambia su pol´ıtica, a partir de ahora en cada entrega le trae solo 1 caja, donde las llegadas se siguen
modelando como un Proceso Poisson de tasa λ, pero si posee m´as de K cajas en su inventario (y por ende
debe ir a dejarla al galp´on) la tasa pasa a ser α.
(c) Modele esta nueva CMTC, plantee las ecuaciones para encontrar las probabilidades en el largo plazo
y especifique bajo que condiciones el sistema no colapsar´ıa.
(d) Considere que a usted le cobran G pesos por caja que guarde en el galp´on. Calcule el precio esperado
que deber´a pagar. (Considere conocidas las probabilidades en el largo plazo)
3

