# Cuadernos de clase · 82514 Mecatrónica y Robótica
Curso 2026/27 · IQS Universitat Ramon Llull

29 cuadernos de Google Colab para las sesiones del semestre que se apoyan en cálculo,
simulación o programación. Las sesiones son de 2 h, así que varias tienen más de un
cuaderno: el sufijo a, b o c indica el orden dentro de la sesión. Los ocho documentos de
apuntes y las presentaciones son independientes: estos cuadernos son la parte ejecutable.

## Cómo usarlos

Sube toda esta carpeta a tu Google Drive (por ejemplo dentro de `Mecatronica`). Para abrir
uno: botón derecho sobre el fichero → Abrir con → Google Colaboratory. La primera celda
instala lo que falte; en Colab tarda uno o dos minutos, y en los del bloque 4 algo más
porque instala la Robotics Toolbox.

En clase no hace falta pasar por Drive: la portadilla de cada sesión de las presentaciones
lleva un enlace **Abrir en Colab** por cuaderno, que salta al fichero desde el propio
`.pptx` (y desde el PDF exportado). Desde la replanificación de 2026/27 el número del
fichero coincide siempre con el de su sesión, así que el rótulo indica solo qué parte de la
sesión abre.

Todos se han ejecutado de principio a fin sin errores antes de entregarse. Ninguno
descarga datos de internet ni necesita GPU: todo es sintético y offline, de modo que
funcionan aunque el aula tenga mala conexión.

## Estructura de cada cuaderno

Cabecera con la sesión, la fecha y las fuentes · celda de instalación · tres a cinco
secciones con explicación antes de cada bloque de código · tres ejercicios para los
estudiantes · soluciones al final · un cierre de «para llevarse de esta sesión».

Las afirmaciones teóricas llevan la misma cita con página que los apuntes, verificada
contra los PDF de la carpeta de bibliografía.

## Índice

### Bloque 3 · Sensores y actuadores
- S5a Características de sensores — transferencia, histéresis, resolución, respuesta dinámica
- S5b Encoders e IMU — cuadratura, deriva del giróscopo, fusión complementaria
- S6 Fuerza, tacto y rango — galga y puente de Wheatstone, LiDAR 2D simulado
- S7a Actuadores eléctricos — modelo del motor DC, curva par-velocidad, punto de operación
- S7b Transmisiones y selección — inercia reflejada, relación de transmisión, selección razonada

### Bloque 4 · Cinemática y estática
- S8 Pose y rotaciones — SO(2)/SE(2), SO(3)/SE(3), bloqueo de cardán, cuaterniones
- S9a Cinemática directa — 2R y 3R a mano, Denavit-Hartenberg, producto de exponenciales
- S9b Taller de cinemática directa 6R — Robotics Toolbox, Puma560 e IRB140
- S10 Cinemática inversa — analítica del 2R, las ocho ramas del PUMA, ikine_LM
- S11a Jacobiano — deducción a mano, diferencias finitas, jacob0
- S11b Singularidades y manipulabilidad — det J, elipsoide, Yoshikawa, número de condición
- S12 Estática y trayectorias — tau = J^T·F, dualidad, quíntico y trapezoidal

### Bloque 5 · Modelado y control en Python
- S13a Modelado y función de transferencia — del motor DC a la FT, polos, constantes de tiempo
- S13b Respuesta con python-control — escalón, indicadores, Bode y márgenes
- S14 Taller de PID — efecto de cada ganancia, Ziegler-Nichols, saturación y anti-windup
- S15a Espacio de estados — conversión, controlabilidad, observabilidad, asignación de polos
- S15b Dinámica y par calculado — Euler-Lagrange del 2R, par calculado frente a PD

### Bloque 6 · Percepción, estimación y SLAM
- S17a Formación de imagen y calibración — modelo estenopeico, distorsión, calibración sintética
- S17b Procesado clásico — convolución, bordes, regiones y momentos, esquinas
- S17c Percepción aprendida — filtros diseñados frente a aprendidos, campo receptivo, clasificador
- S18a Bayes, Kalman y EKF — pasillo discreto, KF en 1D, EKF con baliza
- S18b Localización con EKF — mapa de balizas, elipses de covarianza
- S19a Filtro de partículas y MCL — localización global en pasillo simétrico
- S19b SLAM — EKF-SLAM y optimización de grafo de poses con cierre de bucle

### Bloque 7 · Software robótico y planificación
- S21 Entorno ROS 2 y TF2 — diagnóstico de la instalación local, cadena de transformadas en numpy
- S22 Planificación — mapa de coste, transformada de distancia, A*, PRM, RRT

### Bloque 8 · Robótica basada en aprendizaje
- S24a MDP y Q-learning — gridworld, iteración de valor, Q-learning tabular
- S24b RL profundo y sim-to-real — CartPole, política lineal por CEM, aleatorización de dominio
- S24c Imitación y VLA — clonación de comportamiento, deriva, multimodalidad, modelos VLA

## Cuadernos que se terminan en casa

Los cuatro cuadernos del tramo probabilístico del bloque 6 (S18a, S18b, S19a y S19b) se
inician en clase y se terminan en casa, sin entrega ni nota, porque la fusión de sesiones
recortó el taller. El de calibración (S17a) sí se entrega: es el entregable de taller del
bloque, con plazo en Moodle el domingo 22 de noviembre y comentario en clase en S20.

## Sesiones sin cuaderno, y por qué

S1 a S4 (bloques 1 y 2) son conceptuales: definiciones, historia, taxonomías, normativa.
S16 es la formación de imagen con el taller de calibración y S23 el taller de Nav2 y MoveIt 2. S20 y la segunda mitad de S22 son de ROS 2,
Nav2 y MoveIt 2, que no se ejecutan en Colab; el diagnóstico y la parte conceptual de TF2
están en el cuaderno de S21. S25 es el seminario de artículos y S26 son las defensas del
proyecto y el cierre del curso.
