# Human-Gait-Biomechanics-Analysis-Visualization

### 🇦🇺 Version

### 1. Tracker Gait Analysis
- File: tracker_gait_analysis.csv
- Application: https://opensourcephysics.github.io/tracker-website/

_What it contains:_

- Raw 2D coordinates (x, y) of anatomical markers: shoulder, hip, knee, ankle, mt5.
- Each row corresponds to one frame of the video (30 fps).
- Each point represents the spatial position of a physical marker.

_Biomechanical meaning:_
- Represents the spatial trajectory of body movement during gait.

_This data allows for:_

- Visualising full-body motion as a stick figure.
- Calculating distances between markers to determine segment lengths.
- Analysing individual marker trajectories (for example, ankle vertical motion).

_Example analyses:_
1. 2D or 3D stick figure showing body motion across frames.
2. XY trajectories of individual markers.
3. Velocity and acceleration curves derived from position data.

Reference: Winter, D.A. (2009). Biomechanics and Motor Control of Human Movement.
------
### 2. Body Segments
File: body_segments.csv

_What it contains:_
2D (x, y) positions of body segments: TRK (trunk), THIGH, LEG, FOOT.
These are typically derived from raw marker data, for example, the thigh is the line between hip and knee markers.

_Biomechanical meaning:_
- Represents the spatial position and orientation of each rigid segment of the body.
- Each line defines a rigid component used to:
1. Calculate segment length (distance between endpoints).
2. Determine segment orientation (angle relative to the horizontal axis).
3. Estimate joint centres or force vectors in kinematic models.

_Example analyses:_

1. Segment line plots connecting anatomical markers.
2. Length vs time graphs to detect artefacts.
3. Segment orientation angles vs time.

Reference: Vaughan, C.L., Davis, B.L., & O’Connor, J.C. (1992). Dynamics of Human Gait.

----
#### 3. Segments in Degrees
File: segments_in_degrees.csv

_What it contains:_
- Absolute orientation angles (in degrees) of each segment (TRK, THIGH, LEG, FOOT) with respect to a global reference (typically horizontal).

_Example:_

time | TRK | THIGH | LEG | FOOT

0.00 | 10.2 | 45.7 | 70.3 | 82.1


_Biomechanical meaning:_
- Represents the absolute angular orientation of each segment in space, not the joints themselves.
- These data describe how each body segment rotates relative to the laboratory frame.

_Useful for:_

1. Assessing overall body posture.
2. Analysing segmental rotations (e.g., trunk inclination).
3. Comparing inter-segmental coordination.

_Example analyses:_

1. Segment angles vs time.
2. Cyclograms between segments (e.g., TRK–THIGH).
3. Angular heatmaps showing relative rotation amplitudes.

Reference: Kadaba, M.P., Ramakrishnan, H.K., & Wootten, M.E. (1989). Measurement of lower extremity kinematics during level walking.

### 4. Joint Angles: File: joint_angles.csv

_What it contains:_
- Relative joint angles (in degrees) for main joints: HIP, KNE, and ANK.
- Computed by subtracting adjacent segment angles, for example:

`Knee angle = THIGH − LEG`

_Biomechanical meaning:_
- Describes the internal rotation at each joint.
- These values represent the primary kinematic variables in gait analysis and define range of motion (ROM) and inter-joint coordination.

_Used for:_

1. Analysing flexion/extension patterns.
2. Quantifying range of motion per gait phase.
3. Studying coordination between joints.

_Example analyses:_
1. Joint angle vs time curves for hip, knee, and ankle.
2. Cyclograms (e.g., hip vs knee) for inter-joint coordination.
3. 3D trajectories showing hip–knee–ankle angular evolution.

Reference: Winter, D.A. (1991). The Biomechanics and Motor Control of Human Gait.

#### 5. Muscle Length Equations
File: muscle_length_equations.csv

_What it contains:_
Estimated normalised muscle lengths for specific muscles (e.g., biceps femoris, rectus femoris, vastus lateralis), derived from joint angles.

_Example:_

time | hip | knee | biceps_femoris | rectus_femoris
0.00 | 27.7 | 14.6 | 1.05 | 0.96

_Biomechanical meaning:_
- Shows how each muscle lengthens or shortens depending on joint motion.
- Even without EMG data, it allows inference of muscle activity phases (eccentric vs concentric).

_Used for:_
1. Identifying eccentric and concentric contractions.
2. Analysing timing and coordination of muscle activation.
3. Estimating muscle efficiency and torque generation.

_Example analyses:_
1. Muscle length vs time curves.
2. 3D surface plots of muscle length relative to hip and knee angles.
3. Comparative analysis of agonist–antagonist muscles.

Reference: Arnold, A.S., & Delp, S.L. (2001). Computer models of lower extremity musculoskeletal anatomy.


| File                        | Represents               | Type of data     | What you can analyse                        |
| --------------------------- | ------------------------ | ---------------- | ------------------------------------------- |
| **Tracker Gait Analysis**   | 2D marker coordinates    | Spatial (x, y)   | Trajectories, velocities, posture           |
| **Body Segments**           | Lines between markers    | Spatial (x, y)   | Segment length, orientation                 |
| **Segments in Degrees**     | Absolute segment angles  | Angular (°)      | Posture and inter-segment coordination      |
| **Joint Angles**            | Relative joint rotations | Angular (°)      | Flexion/extension, inter-joint coordination |
| **Muscle Length Equations** | Estimated muscle lengths | Normalised (0–1) | Muscle activity, efficiency, control        |

<img width="162" height="188" alt="Captura de pantalla 2025-11-05 a las 18 19 31" src="https://github.com/user-attachments/assets/cfae96cc-fe86-4ffc-82ab-b5a3ebec10fb" />

----
### 🇦🇷 Version

### Tracker Gait Analysis 
- Archivo: tracker_gait_analysis.csv
- Aplicacion: https://opensourcephysics.github.io/tracker-website/

### _Qué contiene:_

1. Crudo — son las coordenadas (x, y) de los marcadores anatómicos:
shoulder, hip, knee, ankle, mt5.

- Cada fila = un frame del video (a 30 fps).
- Cada punto = posición 2D de un marcador físico.

### _Qué significa biomecánicamente:_

Representa la trayectoria real del movimiento del cuerpo durante la marcha.
Podés:

- Visualizar el movimiento corporal completo (modelo de “stick figure”).
- Calcular distancias entre puntos → longitudes de segmentos.
- Analizar trayectorias individuales (p. ej., el movimiento vertical del tobillo o la rodilla).

Ejemplo de gráficos:

1. Stick figure 2D o 3D del cuerpo moviéndose con el tiempo.
2. Trayectorias (x,y) de un marcador (ej. “cómo sube y baja el tobillo”).
3. Velocidades o aceleraciones derivadas de la posición.

📚 Referencia: Winter, D.A. (2009). Biomechanics and Motor Control of Human Movement.

----
### Body Segments - Archivo: body_segments.csv
_Qué contiene:_

- Posiciones (x, y) de los centros o líneas de los segmentos corporales:
  - TRK (tronco), THIGH (muslo), LEG (pierna), FOOT (pie).

Estos se calculan a partir de los puntos crudos (p. ej. el muslo es la línea entre cadera y rodilla).

_Qué significa biomecánicamente:_

- Te da la posición espacial del segmento, no de los puntos anatómicos.
- Cada línea representa un componente rígido del cuerpo, útil para:

1. Calcular longitud de cada segmento (distancia entre puntos extremos).
2. Determinar su orientación angular (inclinación respecto al eje horizontal).
3. Usar en cinemática directa para estimar centros articulares o vectores de fuerza.

_Ejemplo de gráficos:_
1. Representar cada segmento como una línea entre sus puntos extremos.
2. Gráfico de longitud vs tiempo (para ver si hay desplazamiento relativo).
3. Gráfico de orientación angular del segmento.

📚 Referencia: Vaughan et al. (1992). Dynamics of Human Gait.

#### Segments in Degrees: Archivo: segments_in_degrees.csv

##### _Qué contiene:_
- Los ángulos absolutos (en grados) de cada segmento (TRK, THIGH, LEG, FOOT) respecto a una referencia (normalmente el eje horizontal).

Ejemplo:

time | TRK | THIGH | LEG | FOOT

0.00 | 10.2 | 45.7 | 70.3 | 82.1

_Qué significa biomecánicamente:_
- Describe la orientación angular de cada segmento corporal en el espacio.
- No mide articulaciones, sino el ángulo del segmento completo.

Sirve para:

1. Evaluar postura general del cuerpo.
2. Analizar rotaciones absolutas (por ejemplo, inclinación del tronco).
3. Comparar patrones entre segmentos (coordinación intersegmentaria).

_Ejemplo de gráficos:_
1. Segment angles vs time (3D) → muestra cómo gira cada parte.
2. Cyclograms entre segmentos → relación TRK–THIGH, etc.
3. Heatmap angular → qué segmento rota más o menos.

📚 Referencia: Kadaba et al. (1989). Measurement of lower extremity kinematics during level walking.

-----
### Joint Angles: Archivo: joint_angles.csv

_Qué contiene:_

- Los ángulos articulares relativos (en grados) de las principales articulaciones:
HIP, KNE, ANK.

Estos se obtienen restando los ángulos absolutos de los segmentos adyacentes, por ejemplo:

`
Angulo de rodilla = THIGH − LEG 
`

_Qué significa biomecánicamente:_

- Representa la rotación interna de la articulación.
- Es el dato central de un análisis de marcha, porque define la amplitud de movimiento (ROM) y la coordinación entre articulaciones.

_Sirve para:_

1. Analizar flexión y extensión.
2. Calcular rangos de movimiento.
3. Comparar patrones entre sujetos o condiciones.

_Ejemplo de gráficos:_

1. Joint angles vs time → curvas típicas de marcha (hip, knee, ankle).
2. Cyclogramas (hip vs knee, etc.) → coordinación interarticular.
3. 3D trajectories → hip-knee-ankle coordination with time.

📚 Referencia: Winter, D.A. (1991). The biomechanics and motor control of human gait.

-------
#### Muscle Length Equations: Archivo: muscle_length_equations.csv

_Qué contiene:_

- Estimaciones de la longitud normalizada de músculos específicos (p. ej. bíceps femoral, gastrocnemio, recto femoral), derivadas de los ángulos articulares.

Ejemplo:

time | hip | knee | biceps_femoris | rectus_femoris

0.00 | 27.7 | 14.6 | 1.05 | 0.96

_Qué significa biomecánicamente:_

- Muestra cómo varía la longitud de un músculo según los ángulos articulares.
- Permite inferir actividad o tensión muscular, incluso sin EMG.

_Sirve para:_

1. Identificar fases excéntricas y concéntricas (alargamiento/acortamiento).
2. Evaluar sincronización muscular con la marcha.
3. Predecir momentos articulares o eficiencia muscular.

_Ejemplo de gráficos:_

1. 3D Surface Plot: longitud muscular vs ángulos de cadera y rodilla.
2. Muscle length vs time: evolución durante el ciclo.
3. Comparación entre músculos.

📚 Referencia: Arnold & Delp (2001). Computer models of lower extremity musculoskeletal anatomy.

| Archivo                     | Qué representa                  | Tipo de variable  | Qué podés analizar                      |
| --------------------------- | ------------------------------- | ----------------- | --------------------------------------- |
| **Tracker Gait Analysis**   | Coordenadas 2D de marcadores    | Espacial (x, y)   | Trayectorias, velocidades, postura      |
| **Body Segments**           | Líneas rígidas entre marcadores | Espacial (x, y)   | Longitud, orientación segmentaria       |
| **Segments in Degrees**     | Ángulo absoluto del segmento    | Angular (°)       | Postura y coordinación entre segmentos  |
| **Joint Angles**            | Ángulo relativo entre segmentos | Angular (°)       | Flexo-extensión, coordinación articular |
| **Muscle Length Equations** | Longitud estimada de músculos   | Normalizada (0–1) | Actividad, eficiencia, control muscular |

<img width="162" height="188" alt="Captura de pantalla 2025-11-05 a las 18 19 31" src="https://github.com/user-attachments/assets/cfae96cc-fe86-4ffc-82ab-b5a3ebec10fb" />


