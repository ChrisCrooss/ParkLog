# ParkLog — Your Daily Parkinson's Companion

[![PWA Status](https://img.shields.io/badge/PWA-Compatible-brightgreen.svg?style=flat-square)](#)
[![Accessibility](https://img.shields.io/badge/Accessibility-Parkinson--Friendly-blue.svg?style=flat-square)](#)
[![License](https://img.shields.io/badge/License-MIT-orange.svg?style=flat-square)](#)

[English](#english) | [Español](#español)

---

## ENGLISH

> A progressive web app (PWA), ergonomic, self-managed and backed by scientific evidence, designed specifically to mitigate motor, speech and swallowing symptoms in patients with Parkinson's disease.

---

### Human Motivation

**ParkLog** is born from a deep personal reality: the creator's grandfather suffers from Parkinson's in the early-intermediate stage (Hoehn and Yahr classification 1-2.5).

As a close family member of a patient with Parkinson's disease, I have noticed that technological tools for patients with this condition focus on discouraging future projections, generating anxiety and depression in the family nucleus.

**ParkLog** adopts a paradigm of hope and present-centered action: each routine, exercise, or therapeutic activity is designed to be completed within minutes, providing the patient with clear, daily, measurable victories that counteract the sense of loss and powerlessness.

The software focuses on solving the immediate and daily challenges of the patient:
* **Physical:** Loss of manual dexterity and intentional tremor while eating, joint rigidity in upper extremities.
* **Swallowing (Sialorrhea):** Excessive salivation difficulties due to weakening of facial and pharyngeal muscles.
* **Emotional:** Daily physical uncertainty mitigated through clear, orderly routines guided autonomously or with the support of a caregiver.

---

### Scientific Support (References in APA Format)

The dosage, timer timing, and nature of **ParkLog** routines are based strictly on clinical evidence from the following scientific studies:

1. **Martignon, C., et al. (2020).** *Guidelines on exercise testing and prescription in patients with Parkinson's disease: A systematic review.*
   * **Contribution to the App:** This study clinically demonstrates that combining digital agility exercises, controlled strength training, and stretching slows the degeneration of motor function. This evidence directly supports the weekly structure of ParkLog's dexterity modules.

2. **Swarnakar, R., et al. (2023).** *Weekly exercise variations in early Parkinson's disease: The PARK-EASE randomized controlled trial.*
   * **Contribution to the App:** Provides the weekly dosage scheme for ParkLog. The application automatically synchronizes with the device's internal calendar day to alternate the physical demands of finger dexterity exercises based on muscle fatigue patterns.

3. **Pu, T., et al. (2021).** *Lee Silverman Voice Treatment (LSVT LOUD) in Parkinson's disease swallowing and vocal disorders: A meta-analysis.*
   * **Contribution to the App:** Supports the daily **Voice Module**. A guided 15-second timer is implemented for sustained emission of the phoneme "Ah!" with constant intensity and tone, based on the LSVT LOUD protocol.

4. **Saleem, A., et al. (2024).** *Behavioural therapies for improving swallow and cough coordination in neurodegenerative disorders.*
   * **Contribution to the App:** Supports the daily **Swallowing Module**. Through an ergonomic validation button, it guides the user to perform dynamic saliva swallows with chin tilt and rhythmic breathing coordination between exhalation and laryngeal closure.

---

### Motor Accessibility Design (Stitch UI)

The graphical interface of ParkLog is built using declarative components based on **Stitch** philosophy, meticulously adapted to address muscle tremors and joint rigidity in Parkinson's patients.

* **Giant Ergonomic Buttons (`<s-button>`):** All interactive targets have a minimum height of **80px** (far exceeding the general web accessibility standard of 48px). The oversized design reduces the cognitive and motor load of target acquisition, critical for users experiencing tremors.

* **Immediate Tactile Feedback:** Accelerated active scale transitions (`transform: scale(0.96)`) to simulate the physical pressure of mechanical buttons, providing instant confirmation even when fine motor control is compromised.

* **Active Tremor Mitigation:**
  * `touch-action: manipulation` in CSS to disable quick double-tap zoom on smartphones, preventing layout misalignment when involuntary touches occur.
  * `user-select: none` to prevent annoying text shadowing or selection during incidental tremors.

* **Dark Mode SaaS Premium:** Deep Slate background (`#0f172a`) with ultra-legible Inter typography and high-luminosity emerald green and amber contrasts to compensate for possible visual accommodation difficulties.

---

### Technical Architecture of the PWA

* **Offline-First (`sw.js`):** Native Service Worker that intercepts and caches the application shell (`index.html`, `ejercicios.html`, `manifest.json`). The application works offline, critical for users who may lose connectivity in clinical settings or rural areas.

* **Local Persistence (`localStorage`):** Asynchronously stores and reads the stage (Initial vs Intermediate) and assistance phase (Alone vs Assisted), eliminating confusing login screens or account creation.

* **Smart Phase ON Alerts:** Integrated link on the main panel that requests permissions for native local notifications to schedule reminders during the window of greatest safety and cognitive clarity (typically early morning).

* **Automatic Fatigue Modulation:** If the selected stage is "Intermediate" (greater severity), the dexterity timers are automatically recalculated with a **20% reduction** in duration to prevent overexertion.

---

### Installation and Local Deployment

Being a 100% static, client-side application, it requires no complex servers or external dependencies:

1. Clone this repository:
   ```bash
   git clone https://github.com/tu-usuario/ParkLog.git
   ```
2. Open `index.html` in your mobile or desktop browser.
3. **For mobile (PWA):** On Safari (iOS) press "Share > Add to Home Screen" or on Chrome (Android) press "Add to Home Screen" to install natively.

---

### Technical Notes and Frequently Asked Questions (FAQ)

**How do I activate notifications and medication reminders on iPhone (iOS)?**

Due to Apple's security policies and ecosystem restrictions, the local notifications API (`Notification`) is not activated by default in the Safari browser for web applications.

For medication reminders to work correctly on your iPhone:
1. Open the application in Safari.
2. Tap the **Share** button (box icon with upward arrow).
3. Select the option **Add to Home Screen**.
4. Open the application from the icon installed on your home screen. Doing so will activate full PWA support and you'll be able to enable alerts without issues.

*Note: Exercise and speech-language timers will continue to work natively and independently without needing this installation.*

---

### License

This is an open-source project and university portfolio for the University of South Florida (USF) under the MIT License.

---

---

## ESPAÑOL

> Una aplicación web progresiva (PWA), ergonómica, autogestionada y respaldada por evidencia científica, diseñada específicamente para mitigar los síntomas motores, de habla y deglución en pacientes con enfermedad de Parkinson.

---

### Motivación Humana

**ParkLog** nace de una realidad personal profunda: el abuelo de su creador padece Parkinson en etapa inicial-media (clasificación Hoehn y Yahr 1-2.5).

A menudo, la literatura médica o las herramientas tecnológicas para pacientes con esta enfermedad se enfocan en proyecciones futuras desalentadoras, lo que genera ansiedad y depresión en el núcleo familiar.

**ParkLog** adopta un paradigma de esperanza y acción centrada en el presente: cada rutina, ejercicio o actividad terapéutica está diseñada para ser completada en minutos, proporcionando al paciente victorias claras, diarias y medibles que contrarresten la sensación de pérdida e impotencia.

El software se enfoca en resolver los retos inmediatos y cotidianos del paciente:
* **Físicos:** Pérdida de destreza manual y temblor intencional al comer, rigidez articular en extremidades superiores.
* **Deglución (Sialorrea):** Dificultades de salivación excesiva por debilitamiento de los músculos faciales y faríngeos.
* **Emocionales:** Incertidumbre física diaria mitigada mediante rutinas claras, ordenadas y guiadas de forma autónoma o con el apoyo de un cuidador/familiar.

---

### Sustento Científico (Referencias en Formato APA)

La dosificación, los tiempos de los temporizadores y la naturaleza de las rutinas de **ParkLog** se basan estrictamente en la evidencia clínica de los siguientes estudios científicos:

1. **Martignon, C., et al. (2020).** *Guidelines on exercise testing and prescription in patients with Parkinson's disease: A systematic review.*
   * **Aporte a la App:** Este estudio demuestra clínicamente que combinar ejercicios de agilidad digital, fuerza controlada y estiramiento retarda la degeneración de la función motora. Esta evidencia respalda directamente la estructura semanal de los módulos de destreza de ParkLog.

2. **Swarnakar, R., et al. (2023).** *Weekly exercise variations in early Parkinson's disease: The PARK-EASE randomized controlled trial.*
   * **Aporte a la App:** Proporciona el esquema de dosificación semanal de ParkLog. La aplicación sincroniza automáticamente el día del calendario interno del dispositivo para alternar las demandas físicas de ejercicios de agilidad de dedos basado en patrones de fatiga muscular.

3. **Pu, T., et al. (2021).** *Lee Silverman Voice Treatment (LSVT LOUD) in Parkinson's disease swallowing and vocal disorders: A meta-analysis.*
   * **Aporte a la App:** Respalda el **Módulo de Voz** diario. Se implementa un cronómetro guiado de 15 segundos para la emisión sostenida del fonema "Ah!" de intensidad y tono constantes, basado en el protocolo LSVT LOUD.

4. **Saleem, A., et al. (2024).** *Behavioural therapies for improving swallow and cough coordination in neurodegenerative disorders.*
   * **Aporte a la App:** Respalda el **Módulo de Deglución** diario. Mediante un botón ergonómico de validación, guía al usuario a realizar tragos de saliva dinámicos con inclinación de barbilla y coordinación respiratoria rítmica entre exhalación y cierre laríngeo.

---

### Diseño de Accesibilidad Motriz (Stitch UI)

La interfaz gráfica de ParkLog está construida utilizando componentes declarativos basados en la filosofía de **Stitch**, adaptados meticulosamente para abordar los temblores musculares y la rigidez articular en pacientes con Parkinson.

* **Botones Gigantes Ergonómicos (`<s-button>`):** Todos los targets interactivos tienen una altura mínima de **80px** (superando con creces la norma general de accesibilidad web de 48px). El diseño sobredimensionado reduce la carga cognitiva y motora de la adquisición de objetivos, crítica para usuarios con temblores.

* **Retroalimentación Táctil Inmediata:** Transiciones de escala activa aceleradas (`transform: scale(0.96)`) para simular la presión física de botones mecánicos, dando confirmación instantánea incluso cuando el control motor fino está comprometido.

* **Mitigación de Temblores Activa:**
  * `touch-action: manipulation` en CSS para desactivar el zoom por doble toque rápido en teléfonos inteligentes, impidiendo desajustes del diseño cuando hay toques involuntarios.
  * `user-select: none` para impedir el sombreado o selección molesta de textos durante los temblores incidentales.

* **Modo Oscuro SaaS Premium:** Fondo en escala Deep Slate (`#0f172a`) con tipografía ultra-legible Inter y contrastes en verde esmeralda y ámbar de alta luminosidad para compensar posibles dificultades de acomodación visual.

---

### Arquitectura Técnica de la PWA

* **Offline-First (`sw.js`):** Service Worker nativo que intercepta y almacena en caché la shell de la aplicación (`index.html`, `ejercicios.html`, `manifest.json`). La aplicación funciona sin conexión, crítico para usuarios que pueden perder conectividad en entornos clínicos o áreas rurales.

* **Persistencia Local (`localStorage`):** Almacena y lee de manera asíncrona la etapa (Inicial vs Media) y la fase de ayuda (Solo vs Asistido), eliminando pantallas confusas de inicio de sesión o creación de cuentas.

* **Alertas Inteligentes de Fase ON:** Enlace integrado en el panel principal que solicita permisos de notificaciones locales nativas para recordar de manera programada la ventana de mayor seguridad y claridad cognitiva (típicamente a primera hora de la mañana).

* **Modulación de Fatiga Automática:** Si la etapa seleccionada es "Media" (mayor severidad), los temporizadores de agilidad se recalculan automáticamente con una **reducción del 20%** en la duración para prevenir el sobresfuerzo.

---

### Instalación y Despliegue Local

Al ser una aplicación 100% estática y del lado del cliente, no requiere servidores complejos ni dependencias externas:

1. Clona este repositorio:
   ```bash
   git clone https://github.com/tu-usuario/ParkLog.git
   ```
2. Abre `index.html` en tu navegador móvil o de escritorio.
3. **Para móviles (PWA):** En Safari (iOS) presiona "Compartir > Añadir a pantalla de inicio" o en Chrome (Android) presiona "Añadir a pantalla de inicio" para instalar de manera nativa.

---

### Notas Técnicas y Preguntas Frecuentes (FAQ)

**¿Cómo activar las notificaciones y recordatorios de medicación en iPhone (iOS)?**

Debido a las políticas de seguridad y restricciones del ecosistema de Apple, la API de notificaciones locales (`Notification`) no se encuentra activa de forma predeterminada en el navegador Safari para aplicaciones web.

Para que los recordatorios de medicamentos funcionen correctamente en tu iPhone:
1. Abre la aplicación en Safari.
2. Toca el botón **Compartir** (icono de la caja con la flecha hacia arriba).
3. Selecciona la opción **Añadir a pantalla de inicio** (Add to Home Screen).
4. Abre la aplicación desde el icono instalado en tu pantalla de inicio. Al hacerlo, el navegador activará el soporte completo de PWA y podrás habilitar las alertas sin inconvenientes.

*Nota: Los temporizadores de ejercicios y logopedia continuarán funcionando de forma nativa e independiente sin necesidad de realizar esta instalación.*

---

### Licencia

Este es un proyecto de código abierto y portafolio universitario para la University of South Florida (USF) bajo la Licencia MIT.
