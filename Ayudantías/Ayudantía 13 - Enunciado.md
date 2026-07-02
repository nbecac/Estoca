Pontificia Universidad Cat´olica de Chile
Escuela de Ingenier´ıa
Departamento de Ingenier´ıa Industrial y de Sistemas
ICS2123 – Modelos Estoc´asticos
Profesores Ver´onica Godoy y Andr´es Navarro
Ayudante Jefe Joaqu´ın Vergara
Primer Semestre 2026
Ayudant´ıa 13:
Repaso I2
Ayudantes: Emilio Pe˜na (emilio.penasepulveda@uc.cl) & Mart´ın Pe˜na (martinpena@uc.cl)
Problema 1
La tienda de artesan´ıas ‘Al mal tiempo buena cara’ tiene un ´unico vendedor cuyo desempe˜no depende tanto
de su estado de ´animo como del clima del d´ıa. El ´animo del vendedor puede ser Bueno (B) o Malo (M), y
evoluciona d´ıa a d´ıa seg´un la siguiente matriz de transici´on:
 B
M
B
0.6
0.4
M
0.5
0.5

El clima puede ser Soleado (S) o Lluvioso (L), y evoluciona de forma independiente al ´animo del vendedor
seg´un:
 S
L
S
0.7
0.3
L
0.4
0.6

La probabilidad de que el vendedor concrete una venta en el d´ıa depende del estado conjunto (´animo, clima)
de la siguiente manera:




P(venta)
(B, S)
0.8
(B, L)
0.5
(M, S)
0.4
(M, L)
0.1




(a) Modele la situaci´on como una CMTD que describa conjuntamente el ´animo del vendedor y el clima,
dejando claramente expresadas las tasas de transici´on.
(b) Suponiendo que la tienda lleva mucho tiempo operando, ¿cu´al es la probabilidad de que en un d´ıa
dado el vendedor concrete una venta?
(c) Partiendo del peor estado posible (´animo Malo y clima Lluvioso), ¿cu´antos d´ıas se deben esperar en
promedio hasta que el vendedor recupere el buen ´animo?
1

Problema 2
Alan Brito se caracteriza por ser un alumno relajado en la escuela de ingenier´ıa. Su filosof´ıa de estudio es
simple, ”Si tengo pocas tareas, estoy tranquilo” por lo que mientras tenga M o menos tareas pendientes
las resuelve de forma independiente a una tasa de α tareas por d´ıa.
Esto cambia cuando se acerca el fin de semestre y se comienzan a acumular tareas, ya que debe activar el
’Modo serio’ por lo que ahora resolver´a las tareas a una tasa α · n donde n corresponde a la cantidad de
tareas que aun tiene pendiente. Alan mantiene este ritmo hasta que logre entregar todas sus tareas.
Considere que el tiempo entre la asignaci´on de nuevas tareas distribuye exponencial con un par´ametro λ.
(a) Modele la situaci´on como una CMTC dejando claramente expresado cuales son las tasas de transici´on
instant´aneas.
(b) Encuentre una expresi´on para las probabilidades de largo plazo.
(c) Considere ahora que mientras hayan al menos M tareas en la lista de pendientes, cada vez que llega
una nueva tarea, con probabilidad p se dar´a m´as plazo para todas las tareas, por lo que Alan vuelve
a relajarse y vuelve a su ritmo de α tareas por d´ıa. Sobre est´a din´amica puede asumir que una vez
se ha dado m´as plazo para las tareas se mantendr´a este modo hasta que vuelva a tener M tareas
pendientes. Modifique la CMTC para considerar la nueva din´amica del sistema.
2

Problema 3 (Propuesto)
Considere una f´abrica que tiene dos m´aquinas, m´aquina 1 y m´aquina 2, y dos talleres, taller 1 y taller
2. La m´aquina 1 tiene un tiempo de funcionamiento que distribuye exponencial con tasa λ, mientras
que la m´aquina 2 tiene un tiempo de funcionamiento que distribuye exponencial con tasa α. Cuando
cualquiera de las m´aquinas deja de funcionar se tiene que llevar a alguno de los dos talleres, siempre
prefiriendo el taller 1 sobre el taller 2. Si un taller est´a ocupado, entonces se llevara la m´aquina de-
fectuosa al otro taller.
El tiempo de reparaci´on de la m´aquina 1 en el taller 1 distribuye exponencial con tasa β y si se lleva
al taller 2 su tiempo tambi´en distribuye exponencial, pero con tasa σ. Por otro lado, el tiempo de
reparaci´on de la m´aquina 2 en el taller 1 es exponencial con tasa µ y en el taller 2 es tambi´en expo-
nencial, pero con tasa δ. Adem´as, existe una probabilidad p de que la m´aquina 2 siga mala despu´es
de pasar por el taller 1 y en dicho caso debe ir al taller 2. Asuma que puede haber dos m´aquinas en
el taller 2, pero s´olo se puede atender una a la vez, y se atiende primero a la primera en llegar. Por
otra parte, s´olo puede haber una m´aquina en el taller 1.
Se quiere modelar el problema como una Cadena de Markov en Tiempo Continuo que represente si
las m´aquinas est´an funcionando o no y cu´ales est´an en cada taller si es que no est´an funcionando.
a) Identifique todos los estados posibles y las tasas de transici´on instant´aneas entre estados. Puede
expresar su respuesta a trav´es de un grafo.
Hint: Piense primero en todas las situaciones posibles en las que se puede encontrar cada m´aquina
por separado, y luego en las situaciones posibles para ambas m´aquinas a la vez.
b) Escriba las ecuaciones de equilibrio para cada uno de los estados.
c) Suponga que la m´aquina 2 est´a en el taller 2 y que la m´aquina 1 est´a funcionando. ¿Cu´al es la
probabilidad de que la m´aquina 2 salga del taller antes de que la m´aquina 1 deje de funcionar?
3

