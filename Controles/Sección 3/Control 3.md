Pontificia Universidad Cat´olica de Chile
ICS2123 – Modelos Estoc´asticos
Profesora: Ver´onica Godoy
Primer Semestre 2026
Control 3
Duraci´on: 30 minutos
Problema
Usted tiene tres bolas rojas y tres bolas blancas. Inicialmente las distribuye al azar entre dos urnas de forma tal que cada
urna contenga tres bolas. Luego realiza el siguiente juego: en cada etapa extrae una bola de cada urna y las intercambia.
Si Xn es la cantidad de bolas rojas en la primera urna en la etapa n.
1. Determine la matriz de transici´on P.
2. Determine la distribuci´on inicial de probabilidades del proceso f(0).
3. ¿El proceso tiene distribuci´on de probabilidades l´ımite? Justifique por SI o por NO.
Soluci´on:
1. Estados posibles: {0, 1, 2, 3}, cantidad de bolas rojas en la primera urna.
P =






0
1
0
0
1/9
4/9
4/9
0
0
4/9
4/9
1/9
0
0
1
0






2. Como inicialmente las bolas se distribuyen al azar entre las dos urnas, se tiene que:
• P(X0 = 0) = P(BBB) = 3
6
2
5
1
4 =
1
20
• P(X0 = 1) = P(BBR) + P(BRB) + P(RBB) = 3 · 3
6
2
5
3
4 =
9
20
• P(X0 = 2) = P(BRR) + P(RBR) + P(RRB) = 3 · 3
6
3
5
2
4 =
9
20
• P(X0 = 3) = P(RRR) = 3
6
2
5
1
4 =
1
20
3. El proceso SI tiene distribuci´on de probabilidades l´ımite, porque la cadena es irreducible (los estados son finitos y
todos se comunican entre s´ı, formando una ´unica clase recurrente positiva) y aperi´odica (no tiene periodo).
1

