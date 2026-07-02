PONTIFICIA UNIVERSIDAD CAT´OLICA DE CHILE
ICS2123 Modelos Estoc´asticos 2026-1
Profesor: Andr´es Navarro C.
Control 2
A un centro de salud llegan pacientes seg´un un Proceso de Poisson homog´eneo con tasa λ = 10
pacientes/hora desde las 8:00 hasta las 18:00. Cada paciente, de forma independiente, requiere examen de
sangre con probabilidad del 30 %.
1. Partiendo a las 10:40, ¿cu´al es la probabilidad de que no llegue ning´un paciente que requiera examen
de sangre en los pr´oximos 30 minutos?
Soluci´on:
P(N11:10 −N10:40 = 0) = e−10·0,3·0,5 = e−1,5
2. ¿Cu´al es la probabilidad de que hasta las 12:00 hayan llegado exactamente 8 pacientes que requieren
examen de sangre?
Soluci´on:
P(N12:00 −N8:00 = 8) = e−10·0,3·4 (10 · 0, 3 · 4)8
8!
= e−12 128
8!
3. Si el centro de salud est´a abierto hasta las 18:00 horas, ¿Cu´al es el valor esperado de personas que
llegar´a al centro de salud en un d´ıa?
Soluci´on:
E

N(8:00,18:00)

= λ × 10 = 10 × 10 =
100 .
1

