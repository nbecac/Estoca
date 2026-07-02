Pontificia Universidad Cat´olica de Chile
ICS2123 – Modelos Estoc´asticos
Profesora: Ver´onica Godoy
Primer Semestre 2026
Control 4
Duraci´on: 30 minutos
Problema
La unidad de control de calidad de una empresa de alimentos inspecciona muestras de los lotes de producci´on antes de ser
liberados al mercado. Las muestras llegan a la unidad de control de calidad de acuerdo a un proceso de Poisson a tasa λ
[muestras/minuto].
El protocolo de inspecci´on exige la comparaci´on entre dos muestras para detectar variaciones entre lotes de producci´on.
Existe un ´unico equipo de inspecci´on que tarda un tiempo distribuido exponencial de media 1/µ minutos en procesar
simult´aneamente dos muestras. Una vez inspeccionadas las muestras son desechadas.
1. Modele el n´umero de muestras en la unidad de control de calidad como una CMTC.
Sea X(t): N´umero de muestras en la unidad de control de calidad en el instante t.
0
1
2
3
4
...
λ
λ
λ
λ
λ
µ
µ
µ
µ
µ
2. Plantee el sistema de ecuaciones que le permita obtener las probabilidades estacionarias (si es que existen)
P0 · λ = P2 · µ
P1 · λ = P0 · λ + P3 · µ
P2 · (λ + µ) = P1 · λ + P4 · µ
...
Pn · (λ + µ) = Pn−1 · λ + Pn+2 · µ
P0 + P1 + P2 + ... = 1
1

