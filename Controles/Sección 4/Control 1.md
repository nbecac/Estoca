PONTIFICIA UNIVERSIDAD CAT´OLICA DE CHILE
ICS2123 Modelos Estoc´asticos 2026-1
Profesor: Andr´es Navarro C.
Control 1
Se tienen tres urnas, cada una conteniendo bolas rojas y bolas verdes. En la primera urna, hay 2 bolas
rojas y 3 bolas verdes. En la segunda urna, hay 4 bolas rojas y 1 bola verde. En la tercera urna, hay 3
bolas rojas y 2 bolas verdes. Un experimentador elige una urna al azar y saca una bola al azar de ella.
a) Si la bola es roja, ¿cu´al es la probabilidad de que haya sido elegida la segunda urna?
Soluci´on:
Definimos los siguientes eventos:
• A: Se elige la primera urna.
• B: Se elige la segunda urna.
• C: Se elige la tercera urna.
• R: Se extrae una bola roja.
Queremos calcular P(B|R), la probabilidad de que se haya elegido la segunda urna dado que se
extrajo una bola roja. Usando el Teorema de Bayes:
P(B|R) = P(R|B) · P(B)
P(R)
Calculamos cada parte por separado:
• P(R|B): En la segunda urna hay 4 bolas rojas en total, y 5 bolas en total. Por lo tanto,
P(R|B) = 4
5.
• P(B): Hay tres urnas en total, y cada una tiene la misma probabilidad de ser elegida al azar.
Por lo tanto, P(B) = 1
3.
• P(R): Usaremos la regla de la probabilidad total. P(R) = P(R|A) · P(A) + P(R|B) · P(B) +
P(R|C) · P(C). Calculamos cada t´ermino por separado:
◦P(R|A): Probabilidad de extraer una bola roja de la primera urna. P(R|A) = 2
5.
◦P(A): Probabilidad de elegir la primera urna inicialmente. P(A) = 1
3.
◦P(R|C): Probabilidad de extraer una bola roja de la tercera urna. P(R|C) = 3
5.
◦P(C): Probabilidad de elegir la tercera urna inicialmente. P(C) = 1
3.
Entonces, P(R) = 2
5 · 1
3 + 4
5 · 1
3 + 3
5 · 1
3 =
2
15 +
4
15 +
3
15 =
9
15 = 3
5.
Ahora, sustituimos estos valores en la f´ormula del Teorema de Bayes:
P(B|R) =
4
5 · 1
3
3
5
=
4
15
3
5
= 4
15 · 5
3 = 4
9
Por lo tanto, la probabilidad de que se haya elegido la segunda urna dado que se extrajo una bola
roja es 4
9.
b) Si la bola es roja, ¿cu´al es la probabilidad de que haya sido elegida la primera urna?
Soluci´on:
Para esto, utilizamos el Teorema de Bayes nuevamente. Se sigue el mismo proceso de
c´alculo que en la soluci´on principal, pero calculando P(A|R) en lugar de P(B|R).
P(A|R) = P(R|A) · P(A)
P(R)
Calculamos cada parte por separado, usando los mismos valores que en la soluci´on principal:
• P(R|A) = 2
5.
• P(A) = 1
3.
1

• P(R) = 3
5.
Entonces,
P(A|R) =
2
5 · 1
3
3
5
=
2
15
3
5
= 2
15 · 5
3 = 2
9
Por lo tanto, la probabilidad de que se haya elegido la primera urna dado que se extrajo una bola
roja es 2
9.
c) ¿Cu´al es la probabilidad de que se haya elegido la segunda urna dado que se extrajo una bola verde?
Soluci´on:
Para calcular esto, nuevamente usamos el Teorema de Bayes. Pero esta vez estamos
interesados en P(B|V ), donde V es el evento de extraer una bola verde.
P(B|V ) = P(V |B) · P(B)
P(V )
Calculamos cada parte por separado:
• P(V |B): En la segunda urna hay 1 bola verde en total, y 5 bolas en total. Por lo tanto,
P(V |B) = 1
5.
• P(B): Ya lo hemos calculado antes, es 1
3.
• P(V ): Usamos la regla de la probabilidad total. P(V ) = P(V |A) · P(A) + P(V |B) · P(B) +
P(V |C) · P(C). Calculamos cada t´ermino por separado:
◦P(V |A): Probabilidad de extraer una bola verde de la primera urna. P(V |A) = 3
5.
◦P(V |C): Probabilidad de extraer una bola verde de la tercera urna. P(V |C) = 2
5.
Entonces, P(V ) = 3
5 · 1
3 + 1
5 · 1
3 + 2
5 · 1
3 =
3
15 +
1
15 +
2
15 =
6
15 = 2
5.
Entonces,
P(B|V ) =
1
5 · 1
3
2
5
=
1
15
2
5
= 1
15 · 5
2 = 1
6
Por lo tanto, la probabilidad de que se haya elegido la segunda urna dado que se extrajo una bola
verde es 1
6.
2

