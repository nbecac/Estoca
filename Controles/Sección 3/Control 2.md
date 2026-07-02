Pontificia Universidad Cat´olica de Chile
ICS2123 – Modelos Estoc´asticos
Profesora: Ver´onica Godoy
Primer Semestre 2026
Control 2
Duraci´on: 20 minutos
Problema
Usted tiene dos urnas con bolas rojas y blancas. La primera urna tiene N bolas rojas y M blancas, mientras que la segunda
urna tiene U bolas rojas y V bolas blancas.
Considere el siguiente juego: usted lanza una moneda cargada, cuya probabilidad de obtener cara en un lanzamiento es q.
Si en el lanzamiento de la moneda obtiene cara, extrae una bola de la urna 1 y la agrega a la urna 2; en caso contrario,
extrae una bola de la urna 2 y la agrega a la urna 1.
Asuma que N, M, U, V > 0.
1. Especifique todas las configuraciones posibles de la urna 1 despu´es de una jugada.
2. Calcule la probabilidad de ocurrencia de cada una de las configuraciones especificadas anteriormente.
Se define:
U1 : saco bola de urna 1, U2 : saco bola de urna 2, R : saco bola roja, B : saco bola blanca
Si la urna 1 tiene N bolas rojas y M bolas blancas, en una jugada pueden ocurrir los siguientes eventos:
• Saca bola roja de urna 1, implica que en urna 1 habr´a una bola roja menos (quedan N −1 rojas y M blancas).
P(R|U1) · P(U1) =
N
N + M · q
• Saca bola blanca de urna 1, implica que en urna 1 habr´a una bola blanca menos (quedan N rojas, M −1 blancas)
P(B|U1) · P(U1) =
M
N + M · q
• Saca bola roja de urna 2, implica que en urna 1 habr´a una bola roja m´as (quedan N + 1 rojas, M blancas)
P(R|U2) · P(U2) =
U
U + V · (1 −q)
• Saca bola blanca de urna 2, implica que en urna 1 habr´a una bola blanca m´as (quedan N rojas, M + 1 blancas).
P(B|U2) · P(U2) =
V
U + V · (1 −q)
1

