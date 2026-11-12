# Cuadernos de clase · 82514 Mecatrónica y Robótica
Curso 2026/27 · IQS Universitat Ramon Llull

31 cuadernos de Google Colab para las sesiones del semestre que se apoyan en cálculo,
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
`.pptx` (y desde el PDF exportado), y la sección de cada bloque en Moodle tiene un enlace por
cuaderno. Como la presentación se publica después de las clases del bloque, en el aula los
cuadernos se abren desde Moodle. Desde la replanificación de 2026/27 el número del fichero
coincide siempre con el de su sesión, así que el rótulo indica solo qué parte de la sesión
abre.

Todos se han ejecutado de principio a fin sin errores antes de entregarse. Ninguno necesita
GPU, y casi todo es sintético y offline, de modo que funcionan aunque el aula tenga mala
conexión. Las excepciones son del bloque 6: los cuadernos S16, S17a y S17b instalan OpenCV
4.14.0 en su primera celda (unos veinte segundos, solo si Colab trae otra versión); el S16
descarga, solo en casa y si se pide, las imágenes de muestra de OpenCV; y el S17b descarga un
detector de 3,8 MB, con un plan B sin red. En el bloque 7, el S22b instala OMPL 2.0.1 (unos
segundos), y el S20, el plan B de ROS 2, instala ROS 2 Jazzy sin ventanas en la máquina de
Colab (unos dos minutos, con red); el S20 solo se publica si el profesor lo ha probado antes en
un Colab real. En el bloque 8, el S24a no instala nada; el S24b instala gymnasium 1.4.0 si Colab
trae otra versión y, en su sección 5, que es de casa, stable-baselines3 2.9.0 solo si hay torch; y
el S24c, scikit-learn 1.6.1 si no está. Los tres tardan unos segundos (el PPO de la sección 5 del
S24b, unos 20 s).

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
- S13a Modelado y función de transferencia — el hombro del 2R con el motor de S7 y una reductora de 50: modelo completo y reducido, FT, polos, postura y reductora
- S13b Lazo cerrado y especificaciones — lazo proporcional, ζ y ωn, step_info frente a las fórmulas, plano s y ganancia última
- S14 Taller de PID — el hombro en vertical con gravedad y un techo de 24 V: P, PD que coloca los polos, compensación de gravedad, I con su cota, windup y dos remedios; la tabla del entregable
- S15a Espacio de estados — la articulación en estado: autovalores, controlabilidad y observabilidad, asignación de polos con el techo de 24 V y observador
- S15b Dinámica y par calculado — Euler-Lagrange del 2R con sus dos motores, M(q), c y g; PD por articulación, PD con gravedad y par calculado, con el modelo exacto y equivocado

### Bloque 6 · Percepción, estimación y SLAM
- S16 Formación de imagen y taller de calibración — la cámara de cada equipo, simulada: quince vistas, calibrar, depurar y validar, y del píxel a la mesa y al robot; se entrega en clase, cada uno los suyos (cuaderno y JSON)
- S17a Procesado clásico — la mesa del puesto: umbral, momentos, del centroide al robot (con la calibración de S16), bordes y esquinas
- S17b Percepción aprendida — núcleo aprendido, entrenar y probar, el detector clásico medido, NanoDet con cv2.dnn
- S18a Bayes y Kalman — la puerta estrecha, el pasillo y Kalman en una dimensión
- S18b Localización con EKF — el almacén, la ruta y las diez balizas; métricas, quitar balizas, la baliza lejana, la asociación equivocada y la divergencia
- S19a Filtro de partículas y MCL — el filtro de partículas en el pasillo de S18 y MCL en el almacén con el LiDAR: cuántas partículas, el EKF en el hueco equivocado y el secuestro
- S19b SLAM — EKF-SLAM con las diez balizas, la asociación, el grafo de poses de la ruta con su cierre y un cierre falso, y la rejilla de ocupación

### Bloque 7 · Software robótico y planificación
- S20 Plan B: ROS 2 en Colab — ROS 2 Jazzy sin ventanas en la máquina de Colab: la comprobación de S20, un nodo con un parámetro, un servicio y una acción, la edad del dato según la cola, el paquete del almacén construido con colcon, el grafo dibujado y las dos rondas del taller de S21, para quien no tenga ROS 2 en su portátil
- S21 TF2 en el almacén — TF2 en numpy con el almacén del curso y el mismo código del simulador del taller: el cuaternión en el orden de ROS, el árbol REP 105 y el puesto de picking, la predicción de tf2_echo, odom frente a map y el instante de la medida
- S22a Planificar en una rejilla — el almacén, A*, el mapa de coste de Nav2 y la ejecución del camino
- S22b Muestrear — PRM, RRT, OMPL y el 2R con una caja

### Bloque 8 · Robótica basada en aprendizaje
- S24a El almacén: valor y Q-learning — el almacén como MDP, la iteración de valor como el frente de onda de S22, Q-learning y el muro de la tabla. No instala nada; unos segundos.
- S24b Una política sin modelo y el simulador — el péndulo sobre un carro de Gymnasium, la entropía cruzada, la brecha y la aleatorización de dominio; PPO en casa. gymnasium 1.4.0 si no está; stable-baselines3 2.9.0 si hay torch; unos segundos (PPO, unos 20 s).
- S24c Copiar al experto — la clonación de comportamiento, la deriva y DAgger, la media de dos modos, la difusión y la orden. scikit-learn 1.6.1 si no está; unos segundos.

## Cuadernos del bloque 6: qué se hace en clase y qué se entrega

El de S16 se entrega, pero sin nota: cuenta como presentado o no presentado. Es individual:
cada uno calibra en clase, solo, la cámara de su equipo y sube el cuaderno ejecutado y su
`calibracion_E<n><letra>.json` antes de la puesta en común (la letra, de la A a la D, o la E en
un equipo de cinco, por orden alfabético del primer apellido). Ese JSON es la calibración que
usáis en S17, donde cada pareja carga la de uno de los dos, y en la entrega 3, donde el equipo
usa la de uno de sus miembros, la que mejor valide; se comenta en S20, el jueves 26, con la
verdad de cada unidad. Su sección 5 y sus
ejercicios quedan para casa. Los seis de S17 a S19 tienen un taller corto en clase, de cinco a
nueve minutos, y sus ejercicios, con las soluciones al final, se hacen en casa, sin entrega ni
nota.

## Cuadernos del bloque 7: qué se hace en clase y qué se entrega

El taller de ROS 2 de S21 se hace en el portátil, con ROS 2 Jazzy y los paquetes del curso, y
su entregable es el zip del paquete de cada pareja, no un cuaderno: del S21 solo se hace en clase
la sección 3, dentro de la segunda ronda, y el resto y los ejercicios, en casa. El S22a tiene un
taller corto en clase, de siete minutos, y el S22b va entero a casa; los dos se publican el
jueves 26 de noviembre, porque con el tutorial guiado de Nav2 son la fuente de la opción B de la
entrega 3. El S20 es el plan B de ROS 2 en Colab: en clase solo lo abre quien no tiene ROS 2 en
su portátil, y su sección 8 sirve para que una pareja sin portátil haga el taller de S21. Ninguno
se sube ni tiene nota.

## Cuadernos del bloque 8: qué se hace en clase y qué se entrega

Los tres son de S24 (lunes 14 de diciembre), la única sesión de temario del bloque, y cada uno tiene
un taller corto en clase: el S24a, diez minutos (las secciones 2 a 5), antes del descanso; el S24b,
siete (las secciones 2 a 4); y el S24c, tres (las secciones 2 y 4). Lo demás y los ejercicios, con
sus soluciones al final, van a casa. Ninguno se sube ni tiene nota: es la semana más cargada del
curso, con el seminario, la memoria y el cuestionario B8 en casa.

## Sesiones sin cuaderno, y por qué

S1 a S4 (bloques 1 y 2) son conceptuales: definiciones, historia, taxonomías, normativa.
S23, el taller guiado de Nav2 y MoveIt 2, posterior a la entrega 3, se hace en el portátil con ROS 2 y la guía
del taller, porque Nav2 y MoveIt 2 no se ejecutan en Colab (su respaldo para MoveIt 2 es la
sección 6 del S22b). S25 es el seminario de artículos y S26 son las defensas del
proyecto y el cierre del curso.
