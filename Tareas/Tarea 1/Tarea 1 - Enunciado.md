Pontificia Universidad Cat´olica de Chile
Escuela de Ingenier´ıa
Departamento de Ingenier´ıa Industrial y de Sistemas
ICS2123 – Modelos Estoc´asticos
Profesores Ver´onica Godoy y Andr´es Navarro
Ayudante Jefe Joaqu´ın Vergara
Primer Semestre 2026
Tarea 1:
Repaso de Probabilidades y Proceso de Poisson
Instrucciones
⋄Esta tarea debe ser realizada individualmente o en parejas (pueden ser de diferentes secciones
dentro de las que son coordinadas). Deben indicar en la primera plana del PDF los nombres de los/as
integrantes, junto con las secciones respectivas de c/u.
⋄Tienen plazo hasta el 09 de abril de 2026 para entregar sus soluciones.
⋄Deben entregar un archivo reporte, en formato PDF. En el archivo PDF deben entregar sus res-
puestas de los 4 problemas. Los c´odigos implementados deben adjuntarse aparte en el buz´on. En
caso de no cumplir con esto, se aplicar´a un descuento de 5 d´ecimas sobre la nota final de la tarea.
⋄En el PDF deber´a estar el desarrollo, resumen de resultados y correspondiente an´alisis. Se recomienda
fuertemente utilizar LATEX. Sin embargo, estas tambi´en pueden ser escritas en alg´un otro editor de
texto o a mano y escaneadas, pero debe estar ordenado y legible, de lo contrario, se descontar´an
5 d´ecimas a la nota final de la tarea. Cualquier c´odigo o referencia que utilicen de internet debe ser
debidamente citado insertando el link asociado.
⋄Si realizan la tarea completa en LATEX, incluyendo todas las f´ormulas y ecuaciones, tendr´an 3 d´ecimas
extras.
⋄La tarea tiene un total de 60 puntos. La nota final ser´a calculada como la suma de las tres preguntas
mediante la f´ormula
Nota = P1 + P2 + P3 + P4
60
· 6 + 1 + Bonus −Descuentos
Donde Pi corresponde al puntaje de la pregunta i. Se aproxima a dos decimales.
⋄Las preguntas se har´an a trav´es del foro de discusi´on asociado a la Tarea 1 en Canvas, por lo que les
pedimos que NO manden dudas por mail sobre la tarea. De esta manera, todos tienen acceso a las
respuestas.
⋄Seremos estrictos en que no se aceptar´an env´ıos por mail. Evite problemas de internet, del sistema
Canvas, de la calidad de la foto o cualquier otro que pudiese ocurrir al entregar sobre la hora. El/La
alumno/a que env´ıe su tarea despu´es de la hora l´ımite, tendr´a nota 1.0.
1

Problema 1 (15 puntos)
(a) Sea {Xi}i∈N una colecci´on i.i.d. de VAs, y sea Sn = X1 + · · · + Xn. Calcule E[Sn|X1] y E[X1|Sn].
(b) Sean X, Y dos variables aleatorias independientes de distribuci´on Bernoulli(p), con p ∈[0, 1]. Sea
Z = 1X+Y =0. Calcule E[X|Z], E[Y |Z]. ¿Son independientes? Justifique.
(c) Considere un avi´on con n ≥2 asientos y una fila de n pasajeros debidamente numerados. El primer
pasajero ha extraviado su tarjeta de embarque y, al entrar, selecciona un asiento uniformemente al
azar entre los n disponibles. Los pasajeros restantes (k = 2, . . . , n) act´uan de la siguiente forma: si su
asiento asignado est´a libre, lo ocupan; de lo contrario, eligen un asiento uniformemente al azar entre
los asientos vac´ıos en ese momento.
(i)
Demuestre por inducci´on que la probabilidad de que el pasajero k ocupe su asiento asignado es:
P(Ak) = n −k + 1
n −k + 2,
∀k ∈{2, . . . , n}.
(ii)
Determine la probabilidad de que el ´ultimo pasajero en abordar se siente en el asiento que le
correspond´ıa.
2

Problema 2 (15 puntos)
(a) Un sensor de alta precisi´on detecta el impacto de part´ıculas provenientes de una fuente radiactiva.
Se modela el arribo de las part´ıculas mediante un proceso de Poisson con tasa λ part´ıculas por
minuto. Suponga que se registra un total de tres impactos durante el primer intervalo de observaci´on
de longitud r minutos. Dada esta informaci´on, determine la funci´on de densidad de probabilidades
del instante en que ocurri´o el primer impacto. Adicionalmente, determine la probabilidad de que la
primera part´ıcula haya impactado el sensor dentro de los primeros 2 minutos para r = 10.
(b) Considere ahora un segundo periodo de observaci´on que comienza inmediatamente despu´es de concluir
el primero. Sea Ti el instante del i-´esimo impacto medido desde el inicio de esta segunda etapa. Si
se sabe que el primer impacto ocurri´o despu´es de r minutos, determine la funci´on de densidad de
probabilidad del instante en que ocurre el tercer impacto.
(c) Suponga ahora que el sensor opera en un r´egimen de baja intensidad con una tasa de λ = 0.1 part´ıculas
por d´ıa. Se ha observado que cada part´ıcula, al impactar el sensor, genera un n´umero aleatorio
de se˜nales el´ectricas secundarias Yi, las cuales siguen una distribuci´on Binomial(n = 4, p = 0.05).
Asumiendo independencia entre los impactos y las se˜nales generadas, determine el valor esperado
del n´umero total de se˜nales el´ectricas registradas tras un mes de operaci´on (30 d´ıas). De manera
complementaria, calcule la probabilidad de que al cabo de un mes de operaci´on (30 d´ıas) no se haya
registrado ninguna se˜nal secundaria.
3

Problema 3 (15 puntos)
Las ´ordenes que llegan a una plataforma digital de inversiones pueden dividirse en 3 grupos: ´ordenes de
inversionistas minoristas, ´ordenes de inversionistas profesionales y ´ordenes de inversionistas institucionales.
Cada grupo env´ıa ´ordenes seg´un un proceso de Poisson, donde las ´ordenes de inversionistas minoristas llegan
con tasa λ, las de inversionistas profesionales con tasa α y las de inversionistas institucionales con tasa β
(todas las tasas en ´ordenes por hora, respectivamente). Todos los procesos de llegada son independientes
entre s´ı. Considere que la plataforma funciona las 24 horas del d´ıa y que los procesos reinician cada d´ıa a
las 0:00 horas.
Dependiendo del tipo de orden, estas pueden requerir distintos niveles de procesamiento dentro de la
plataforma. Las ´ordenes de inversionistas minoristas utilizan un sistema avanzado de validaci´on con una
probabilidad de 0.3; tambi´en con 0.3 utilizan un sistema est´andar de ejecuci´on y con 0.4 no requieren
intervenci´on adicional (son procesadas autom´aticamente por el motor de matching). Para el caso de los
inversionistas profesionales, con 0.4 de probabilidad utilizan el sistema est´andar de ejecuci´on, con 0.1 el
sistema avanzado de validaci´on y con 0.5 se procesan autom´aticamente. Finalmente, para el caso de los
inversionistas institucionales, estos utilizan con 0.5 de probabilidad el sistema avanzado de validaci´on, con
0.3 el sistema est´andar y con 0.2 se procesan autom´aticamente.
Por otra parte, cada orden que llega puede ser seleccionada con probabilidad p (0 < p < 1) para realizar
una revisi´on adicional de cumplimiento regulatorio y gesti´on de riesgo antes de su ejecuci´on, mientras que
el resto no debe hacerlo.
Finalmente, los analistas de riesgo monitorean peri´odicamente algunas ´ordenes en proceso y el tiempo
que toman en cada revisi´on distribuye Uniforme(0.2,0.5), distribuci´on continua en horas. Este tiempo es
independiente de los procesos de llegada.
(a) ¿Cu´al es la probabilidad de que un d´ıa a las 12:00 hayan llegado 75 ´ordenes que necesiten procesa-
miento adicional (est´andar o avanzado), si se sabe que hasta las 12:00 han llegado 40 o m´as ´ordenes
institucionales que necesitaban validaci´on avanzada?
(b) Un inversionista profesional env´ıa una orden a las 16:00 y un operador le dice que hasta el momento
han realizado la revisi´on de cumplimiento a 150 ´ordenes profesionales ese d´ıa. ¿Cu´al es el n´umero
esperado de ´ordenes que se tuvieron que hacer la revisi´on desde el inicio del d´ıa y las 16:00?
(c) ¿Cu´al es la probabilidad de que durante la revisi´on de un analista a una orden, a la plataforma hayan
llegado m´as de 20 ´ordenes minoristas, m´as de 30 ´ordenes profesionales que se procesan autom´atica-
mente y menos de 35 ´ordenes institucionales que requieren alg´un tipo de procesamiento adicional?
4

Problema 4 (15 puntos)
Considere una marat´on que comienza a las 8:00 y finaliza a las 12:00. A medida que avanza la carrera, los
corredores se van separando naturalmente en grupos de acuerdo con su velocidad y capacidad atl´etica.
Sea P un punto fijo del recorrido y sea N(t) la cantidad de corredores que han pasado por dicho punto
hasta el tiempo t (medido en minutos desde las 8:00). Se modela {N(t), t ≥0} como un proceso de Poisson
no homog´eneo con tasa de llegada λ(t).
Durante la primera hora de la carrera (de 8:00 a 9:00), la tasa de corredores que pasa por el punto P
aumenta linealmente desde 0 hasta A personas por minuto. A partir de ese momento y hasta el final de la
carrera, la tasa de llegadas se modela como
λ(t) = A + β sin
2π
30 t

,
donde t est´a medido en minutos y se cumple que A > β.
Bajo este modelo, responda las siguientes preguntas:
(a) Grafique la funci´on de tasa λ(t) y calcule el n´umero esperado de corredores que pasan por el punto
P durante las cuatro horas de carrera.
(b) Calcule la probabilidad de que a mitad de la carrera (a las 10:00) hayan pasado menos de 150 personas
por el punto P, sabiendo que entre las 9:30 y las 10:15 pasaron 200 corredores.
(c) Sabiendo que entre las 10:00 y las 12:00 pasaron 500 o m´as corredores por el punto P, calcule la
probabilidad de que en toda la carrera hayan pasado 800 o m´as corredores por dicho punto.
5

