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
(b) Encuentre las funciones de densidad marginal fX(x) y fY (y).
(c) Obtenga la funci´on de densidad condicional de la potencia de salida dado que se conoce la potencia
de entrada, fY |X(y|x).
(d) Si la potencia de entrada se fija en un valor x0, ¿cu´al es la potencia de salida esperada? Calcule
E[Y |X = x0].
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
(a) Entregue una expresi´on para la probabilidad de que la patrulla llegue al cajero en un tiempo menor
que t.
(b) Entregue una expresi´on para la distribuci´on de probabilidad del tiempo de llegada del primer asal-
tante.
(c) ¿Cu´al es la probabilidad de que la patrulla sorprenda a todos los asaltantes en su intento de robo al
cajero?
1

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
(b) El algoritmo utiliza un “Indicador de Presi´on de Libro” para predecir cambios bruscos en el precio.
Este indicador rastrea la secuencia cronol´ogica de las ´ordenes y se satura (alcanzando el 100 %) en
el instante preciso en que el sistema registra la llegada de la K-´esima Orden Limitada de la sesi´on
operativa (K ≥3). Determine la probabilidad exacta de que el indicador se sature habiendo permitido
que el algoritmo procese, a lo sumo, 2 ´Ordenes de Mercado desde el inicio de la sesi´on.
(c) Si la sesi´on de mercado abre en t = 0, ¿cu´al es la probabilidad de que la primera Orden Limitada del
d´ıa se registre antes de los primeros τ0 milisegundos, y que adem´as, en ese preciso instante en que
entra dicha Orden Limitada, el algoritmo a´un no haya recibido ninguna Orden de Mercado?
2

