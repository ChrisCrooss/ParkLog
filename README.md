# 🧠 ParkLog — Tu Compañero Diario de Parkinson

[![PWA Status](https://img.shields.io/badge/PWA-Compatible-brightgreen.svg?style=flat-square)](#)
[![Accessibility](https://img.shields.io/badge/Accessibility-Parkinson--Friendly-blue.svg?style=flat-square)](#)
[![License](https://img.shields.io/badge/License-MIT-orange.svg?style=flat-square)](#)

> Una aplicación web progresiva (PWA), ergonómica, autogestionada y respaldada por evidencia científica, diseñada específicamente para mitigar los síntomas motores, de habla y deglución en pacientes con enfermedad de Parkinson.

---

## 🌟 Motivación Humana

**ParkLog** nace de una realidad personal profunda: el abuelo de su creador padece Parkinson en etapa inicial-media (clasificación Hoehn y Yahr 1-2.5). 

A menudo, la literatura médica o las herramientas tecnológicas para pacientes crónicos se enfocan en proyecciones futuras desalentadoras, lo que genera ansiedad y depresión en el núcleo familiar. En contraste, **ParkLog está diseñado desde la empatía y la resiliencia en el día a día**. 

El software se enfoca en resolver los retos inmediatos y cotidianos del paciente:
*   **Físicos:** Pérdida de destreza manual y temblor intencional al comer, rigidez articular en extremidades superiores.
*   **Deglución (Sialorrea):** Dificultades de salivación excesiva por debilitamiento de los músculos faciales y faríngeos.
*   **Emocionales:** Incertidumbre física diaria mitigada mediante rutinas claras, ordenadas y guiadas de forma autónoma o con el apoyo de un cuidador.

---

## 🔬 Sustento Científico (Referencias en Formato APA)

La dosificación, los tiempos de los temporizadores y la naturaleza de las rutinas de **ParkLog** se basan estrictamente en la evidencia clínica de los siguientes estudios científicos:

1.  **Martignon, C., et al. (2020).** *Guidelines on exercise testing and prescription in patients with Parkinson's disease: A systematic review.*  
    *   **Aporte a la App:** Este estudio demuestra clínicamente que combinar ejercicios de agilidad digital, fuerza controlada y estiramiento retarda la degeneración de la función motora. Establece la **Regla de Oro de Seguridad**: cualquier esfuerzo físico debe realizarse estrictamente en la **Fase "ON"** del paciente (45-60 minutos tras la toma de la medicación dopaminérgica) para evitar caídas y rigidez refleja.
2.  **Swarnakar, R., et al. (2023).** *Weekly exercise variations in early Parkinson's disease: The PARK-EASE randomized controlled trial.*  
    *   **Aporte a la App:** Proporciona el esquema de dosificación semanal de ParkLog. La aplicación sincroniza automáticamente el día del calendario interno del dispositivo para alternar las cargas de trabajo (Lunes/Miércoles/Viernes para Agilidad digital; Martes/Jueves para Fuerza; Sábados/Domingos para Estiramiento palmar).
3.  **Pu, T., et al. (2021).** *Lee Silverman Voice Treatment (LSVT LOUD) in Parkinson's disease swallowing and vocal disorders: A meta-analysis.*  
    *   **Aporte a la App:** Respalda el **Módulo de Voz** diario. Se implementa un cronómetro guiado de 15 segundos para la emisión sostenida del fonema "¡Ah!" de intensidad y tono constantes, estimulando la aducción de las cuerdas vocales para mitigar la disfagia y proyectar el habla.
4.  **Saleem, A., et al. (2024).** *Behavioural therapies for improving swallow and cough coordination in neurodegenerative disorders.*  
    *   **Aporte a la App:** Respalda el **Módulo de Deglución** diario. Mediante un botón ergonómico de validación, guía al usuario a realizar tragos de saliva dinámicos con inclinación de barbilla, fortaleciendo el músculo cricofaríngeo para reducir activamente la sialorrea (babeo involuntario).

---

## 🎨 Diseño de Accesibilidad Motriz (Stitch UI)

La interfaz gráfica de ParkLog está construida utilizando componentes declarativos basados en la filosofía de **Stitch**, adaptados meticulosamente para abordar los temblores musculares y la rigidez de dedos:

*   **Botones Gigantes Ergonómicos (`<s-button>`):** Todos los targets interactivos tienen una altura mínima de **80px** (superando con creces la norma general de accesibilidad web de 48px).
*   **Retroalimentación Táctil Inmediata:** Transiciones de escala activa aceleradas (`transform: scale(0.96)`) para simular la presión física de botones mecánicos, dando confirmación instantánea al paciente.
*   **Mitigación de Temblores Activa:**
    *   `touch-action: manipulation` en CSS para desactivar el zoom por doble toque rápido en teléfonos inteligentes, impidiendo desajustes del diseño cuando hay toques involuntarios.
    *   `user-select: none` para impedir el sombreado o selección molesta de textos durante los temblores incidentales.
*   **Modo Oscuro SaaS Premium:** Fondo en escala *Deep Slate* (`#0f172a`) con tipografía ultra-legible *Inter* y contrastes en verde esmeralda y ámbar de alta luminosidad para compensar posibles disminuciones de la agudeza visual.

---

## 🛠️ Arquitectura Técnica de la PWA

*   **Offline-First (`sw.js`):** Service Worker nativo que intercepta y almacena en caché la shell de la aplicación (`index.html`, `ejercicios.html`, `manifest.json`). La aplicación funciona de manera fluida en cualquier rincón del hogar, sin requerir conexión a internet activa.
*   **Persistencia Local (`localStorage`):** Almacena y lee de manera asíncrona la etapa (Inicial vs Media) y la fase de ayuda (Solo vs Asistido), eliminando pantallas confusas de inicio de sesión o contraseñas.
*   **Alertas Inteligentes de Fase ON:** Enlace integrado en el panel principal que solicita permisos de notificaciones locales nativas para recordar de manera programada la ventana de mayor seguridad y menor temblor del paciente.
*   **Modulación de Fatiga Automática:** Si la etapa seleccionada es "Media" (mayor severidad), los temporizadores de agilidad se recalculan automáticamente con una **reducción del 20%** en la duración (de 60s a 48s) para mitigar el agotamiento, activando paralelamente banners visuales de advertencia médica.

---

## 🚀 Instalación y Despliegue Local

Al ser una aplicación 100% estática y del lado del cliente, no requiere servidores complejos ni dependencias externas:

1.  Clona este repositorio:
    ```bash
    git clone https://github.com/tu-usuario/ParkLog.git
    ```
2.  Abre `index.html` en tu navegador móvil o de escritorio.
3.  **Para móviles (PWA):** En Safari (iOS) presiona "Compartir > Añadir a pantalla de inicio" o en Chrome (Android) presiona "Añadir a pantalla de inicio" para instalar de manera nativa.

---

## 📝 Licencia

Este es un proyecto de código abierto y portafolio universitario para la University of South Florida (USF) bajo la Licencia MIT.
