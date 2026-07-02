Pontificia Universidad Cat´olica de Chile
ICS2123 – Modelos Estoc´asticos
Profesora: Ver´onica Godoy
Primer Semestre 2026
Control 6
Duraci´on: 30 minutos
Problema
Un centro de atenci´on t´ecnica recibe solicitudes de servicio seg´un un proceso de Poisson con una tasa de 10 clientes/hora.
Un ´unico t´ecnico atiende las solicitudes en un tiempo que distribuye exponencial de media 5 minutos.
La gerencia desea evaluar la utilizaci´on del servicio y el tiempo de permanencia del cliente en el sistema para los siguientes
escenarios:
1. La sala de espera es ilimitada, por lo que cualquier cliente que llegue puede esperar su turno.
Es un sistema M/M/1, con λ = 10 y µ = 12
L =
λ
µ−λ =
10
12−10 = 5 clientes, W = L
λ =
5
10 = 0.5 horas, U = λ
µ = 10
12
R: El tiempo promedio de permanencia de los clientes es de 30 minutos y el porcentaje de utilizaci´on del servicio es
del 83.3%
2. La sala de espera solo tiene espacio para que esperen 3 clientes. Si un cliente llega cuando la sala de espera est´a llena,
se pierde.
Es un sistema M/M/1/4, con λ = 10 y µ = 12. Sea ρ = λ
µ
P0 =
1−ρ
1−ρK+1 = 0.2786; Pn = ρn · P0
P0 = 0.2786; P1 = 0.2322; P2 = 0.1935; P3 = 0.1613; P4 = 0.1344.
L = 0 · P0 + 1 · P1 + 2 · P2 + 3 · P3 + 4 · P4 = 1.6407
Para calcular L tambi´en se puede utilizar la ecuaci´on L =
ρ
1−ρ · 1−ρK−K·ρK+KρK+1
1−ρK+1
=
0.83
1−0.83 · 1−0.834−4·0.834+4·0.835
1−0.835
=
1, 6405
λe = λ · (1 −P4) = 8.656, W = 1.641
8.656 = 0, 1896 horas, U = 8.656
12
= 0.7213
R: El tiempo promedio de permanencia de los clientes es de 11,37 minutos y el porcentaje de utilizaci´on del ser-
vicio es del 72.1%
1

