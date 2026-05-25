# Contexto del Proyecto: ParkLog (Parkinson App - GitHub Portfolio)

## 1. Perfil del Desarrollador y Objetivo
- **Desarrollador:** Estudiante ingresando a la carrera de Computer Science (CS) en la University of South Florida (USF). Conoce lógica de programación y está desarrollando sus primeras habilidades técnicas reales.
- **Objetivo del Archivo:** Proporcionar contexto inmediato, absoluto y estructurado a Antigravity IDE para avanzar en el diseño, maquetación y desarrollo del software sin redundancias ni consumo excesivo de tokens de la API.
- **Meta del Proyecto:** Crear una Web App accesible, moderna y open-source para el portafolio de GitHub, resolviendo un problema humano real en lugar de replicar tutoriales genéricos.

## 2. Inspiración y Enfoque Humano
- **Motivación:** El abuelo del desarrollador padece Parkinson en etapa inicial-media (Hoehn and Yahr 1-2.5).
- **Problemas de Usuario a Resolver:**
  - Físicos: Temblores al comer (pérdida de destreza manual), rigidez en brazos/manos, dificultad para conducir y episodios de sialorrea (caída de saliva/baba) por compromiso de los músculos faciales y de deglución.
  - Emocionales: Ansiedad y depresión causadas por la incertidumbre del avance de la enfermedad.
- **Enfoque de la App:** Mejorar la calidad de vida *actual* mediante ejercicios prácticos, independientes y guiados en casa. La interfaz debe mantener un tono motivacional, enfocándose en el día a día y evitando proyecciones futuras desmotivadoras.

## 3. Sustento Científico (Referencias Clave para el README)
La aplicación se basa estrictamente en la evidencia clínica de cuatro papers provistos por el usuario:
1. **Martignon et al. (2020) - *Guidelines on exercise testing and prescription...*:** Demuestra que la combinación de fuerza, flexibilidad y resistencia ralentiza los síntomas motores. Establece una regla crítica de seguridad: los ejercicios deben realizarse obligatoriamente en la fase "ON" del paciente (45-60 min después de tomar su medicación).
2. **Swarnakar et al. (2023) - *PARK-EASE trial*:** Ensayo clínico aleatorizado en etapa temprana que aporta la estructura y la rutina específica de ejercicios semanales (fuerza, agilidad, estiramientos) demostrando que la rutina debe variar según el día de la semana.
3. **Pu et al. (2021) - *Lee Silverman Voice Treatment (LSVT LOUD)...*:** Metaanálisis que demuestra que la terapia de voz intensa mejora notablemente el volumen del habla y la función de deglución (capacidad de tragar para mitigar la saliva).
4. **Saleem et al. (2024) - *Behavioural therapies for improving swallow and cough...*:** Respalda el entrenamiento muscular conductual de la garganta y la deglución dinámica para controlar la papada, evitar la caída de saliva y mejorar la seguridad al comer.

## 4. Arquitectura, Stack Técnico y Alcance (Fase 1)
- **Stack:** HTML5, JavaScript nativo (ES6+) y **Stitch** (vía CDN en el `<head>`) para el diseño y renderizado de componentes de la interfaz de usuario (UI).
- **Estrategia Mobile (iOS / Android):** Diseñado obligatoriamente como una PWA (Progressive Web App) estática. Esto permite que se instale directamente desde el navegador en iOS (Safari) y Android (Chrome), habilitando el disparo de notificaciones locales nativas sin depender de servidores externos.
- **Persistencia Local:** La configuración del usuario y el estado de las rutinas se guardan en el `localStorage` del navegador para evitar sistemas complejos de bases de datos o pantallas de login.
- **Estilo Visual (Moderno + Accesible):**
  - **Diseño con Stitch:** Estilo limpio, minimalista, espaciado, con estética premium tipo SaaS moderno.
  - **Accesibilidad Parkinson:** Botones gigantes para mitigar el efecto de los temblores musculares (fáciles de presionar), desactivación del doble toque de zoom en móviles, tipografías del sistema altamente legibles (`Inter` o `System-UI`) y contrastes de color elevados.

## 5. Funcionalidades de la Interfaz y Lógica de Código
- **Detección Automática Multilenguaje (i18n):** El script debe leer las preferencias del sistema mediante `navigator.languages` o `navigator.language`. Si el dispositivo utiliza español o variantes regionales (español, catalán, gallego, etc.), la app arranca automáticamente en **Español**. Para cualquier otro idioma del mundo (inglés, chino, francés, alemán, etc.), se aplica el **Inglés** por defecto como idioma universal. Debe incluir un diccionario JSON (`i18n`) para mapear los textos de Stitch de forma dinámica.
- **Barra de Estado Superior:** Un apartado permanente en la parte superior de la UI que muestra el modo actual (Ej: "Modo: Inicial - Solo") con un botón de Stitch moderno para "Cambiar Fase / Rectificar" de forma inmediata en caso de que el usuario se equivoque al pulsar un botón.
- **Detección de Rutina Diaria Inteligente:** La app lee el calendario interno del dispositivo y dosifica automáticamente el tipo de ejercicio (fuerza, agilidad o estiramientos de manos) combinando las tablas del *PARK-EASE trial* y *Martignon*, adaptando la intensidad y los tiempos de los cronómetros según la etapa seleccionada (Inicial vs. Media).
- **Módulo Fijo de Voz y Deglución:** Ejercicios diarios basados en el "¡Ah!" sostenido de intensidad constante (LSVT LOUD) y tragado de saliva dinámico para el control muscular.
- **Recordatorios Locales:** Un botón ergonómico que configura alarmas automáticas en el dispositivo del usuario para notificarle cuándo es su fase "ON" según la hora de su pastilla.

## 6. Instrucciones para Antigravity IDE / Reglas de Interacción
1. **Ahorro de Tokens:** Sé conciso, directo e implementa código modular. No repitas explicaciones teóricas ni resúmenes a menos que se te solicite explícitamente.
2. **Uso de Stitch:** Estructura las vistas utilizando componentes nativos y declarativos de Stitch (`s-card`, `s-button`, etc.), asegurando dimensiones generosas en los elementos interactivos para evitar errores por temblores.
3. **Comentarios de Código Académicos:** Agrega comentarios breves y limpios en las funciones clave de JavaScript que conecten el código con los papers de investigación (ej. `// Ejercicio de voz basado en el metaanálisis de Pu et al. (2021)`). Esto es fundamental para la revisión del portafolio en la universidad.
4. **Simplicidad:** Mantén el desarrollo al alcance de un estudiante de primer año de CS, priorizando la elegancia en JavaScript del lado del cliente.