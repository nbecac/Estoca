Pontificia Universidad Cat´olica de Chile
ICS2123 – Modelos Estoc´asticos
Profesora: Ver´onica Godoy
Primer Semestre 2026
Control 7
Duraci´on: 30 minutos
Problema
Un centro de atenci´on t´ecnica recibe solicitudes de servicio seg´un un proceso de Poisson con una tasa de 10 clientes/hora.
Un ´unico t´ecnico atiende las solicitudes en un tiempo que distribuye exponencial de media 5 minutos. La sala de espera
solo tiene espacio para que esperen 3 clientes. Si un cliente llega cuando la sala de espera est´a llena, se pierde.
La gerencia desea evaluar lo siguiente:
• Cantidad total de clientes atendidos.
• Tiempo m´aximo de espera en cola.
• Proporci´on de solicitudes perdidas.
Desarrolle un diagrama de flujo del programa computacional que permita simular 8 horas de operaci´on del centro de atenci´on
t´ecnica.
DEFINICION DE VARIABLES
T: reloj de simulaci´on (en horas)
U: estado del t´ecnico (1: ocupado, 0: desocupado)
NCOL: cantidad de solicitudes en cola
NAT : cantidad de solicitudes atendidas
NREC : cantidad de solicitudes recibidas
NPER : cantidad de solicitudes perdidas
TMAX : tiempo m´aximo en cola
TPE(1): tiempo en que ocurrir´a la pr´oxima llegada
TPE(2): tiempo en que ocurrir´a la pr´oxima salida
TLLEG(i) = tiempo de llegada del trabajo que ocupa la posici´on i en la cola.
X: instancia de una v.a. exponencial (10) ( tiempo entre llegadas)
Y: instancia de una v.a. exponencial (12) (tiempo de servicio)
W: tiempo de espera en fila
INICIALIZACION
T = U = NCOL = NAT = NREC = NPER = TMAX = 0
TPE(1) = X (tiempo en que ocurrir´a la primera llegada)
TPE(2) = ∞(tiempo en que ocurrir´a la primera salida)
1

PROGRAMA PRINCIPAL
MIENTRAS T < 8 (mientras no se cumpla la condici´on de t´ermino de la simulaci´on)
SI TPE(1) < TPE(2) (¿el pr´oximo evento es de llegada?)
T = TPE(1) (avanza reloj de simulaci´on)
TPE(1) = T + X (programa pr´oxima llegada)
NREC = NREC + 1 (actualiza la cantidad de solicitudes recibidas)
SI NCOL = 3 (¿el sistema est´a lleno?)
NPER = NPER + 1 (actualiza la cantidad de solicitudes perdidas)
SINO (el sistema no est´a lleno)
SI U = 0 (¿el t´ecnico est´a desocupado?)
U = 1 (el t´ecnico pasa a ocupado)
TPE(2) = T + Y (programa pr´oxima salida)
SINO (el t´ecnico est´a ocupado)
NCOL = NCOL + 1 (la solicitud se coloca en la fila)
TLLEG(NCOL) = T (almacena su tiempo de llegada)
SINO (el pr´oximo evento es de salida)
T = TPE(2) (avanza el reloj de simulaci´on)
NAT = NAT + 1 (actualiza la cantidad de solicitudes atendidas)
SI NCOL > 0 (¿hay solicitudes en cola?)
NCOL = NCOL - 1 (la primera solicitud en cola pasa a ser atendida)
W = T - TLLEG(1) (calcula su tiempo de espera en fila)
TMAX = max(TMAX, W) (actualiza el tiempo m´aximo de espera en fila)
TPE(2) = TPE(2) + Y (programa pr´oxima salida)
PARA i=1 hasta NCOL (Si NCOL = 0 no se ejecuta esta instrucci´on)
TLLEG(i) = TLLEG(i+1) (Las solicitudes que quedan en cola avanzan un espacio)
SINO (no hay solicitudes en cola)
U = 0 (el t´ecnico queda desocupado)
TPE(2) = ∞(se programa la pr´oxima salida)
FIN(mientras)
GENERAR REPORTES
Imprimir(”Cantidad de solicitudes atendidas:”, NAT)
Imprimir(”Tiempo m´aximo de espera en cola:”, TMAX*60, ”minutos”)
Imprimir(”Proporci´on de solicitudes perdidas:”, NPER/NREC)
FIN (programa)
2

