# Raúl Esteban Burró Cespedes

Ingeniero de Software Senior

---

Email: <rauleburro@gmail.com>

Tel: (PY) [+595 981 365257](tel:+595981365257) | (ES) [+34 662 538 778](tel:+34662538778)

Nacionalidad: Paraguay/España

---

## Perfil

Ingeniero de software senior con más de 12 años de experiencia en desarrollo web y móvil, especializado en la construcción de aplicaciones escalables usando React, React Native, Next.js y Flutter. Historial comprobado liderando ciclos completos de proyectos — desde la definición de arquitectura hasta el despliegue — en entornos tanto de startups como empresariales.

Sólidos conocimientos de backend con Django y Node.js, y habilidades en el despliegue de infraestructuras basadas en la nube usando GCP, Docker y Kubernetes. Reconocido por mentorizar desarrolladores junior, documentar proyectos exhaustivamente y entregar soluciones de alta calidad alineadas con los objetivos de negocio.

Actualmente Tech Lead en AIMA, liderando el equipo que despliega una app multiplataforma de cuidado con IA — un avatar MetaHuman conversacional en tiempo real — e impulsando la arquitectura agéntica y los flujos de desarrollo de la empresa.

## Tecnologías

Django, Nodejs, NextJS, React, React Native, Flutter, Kotlin, Swift, C++, TypeScript, Unreal Engine, Android, iOS, GCP, Kubernetes, Docker, Firebase, WebSocket, ONNX, pgvector, Claude Code, Digital Ocean, Git, Github, Linear, Jira.

## Habilidades

- Tomar la decisión correcta y tener conocimiento sólido de nuestras herramientas.
- Mantener el código limpio y adaptable.
- Gran solucionador de problemas.
- Eficiente a través de la optimización.
- Apuntar al éxito desde el inicio.
- Auto-evaluarse durante el proceso.
- Desarrollo de software de ciclo completo usando metodologías Ágiles (SCRUM).

## Experiencia

### Tech Lead – App Multiplataforma (Ingeniero Senior Frontend & Mobile / Integración de IA)

#### AIMA (Beyond AI) | Feb 2026 – Presente

- **Tech Lead** del equipo que construye y despliega la aplicación multiplataforma de AIMA, un agente cuidador con IA representado por un avatar MetaHuman en tablets Android, trabajando con Flutter/Dart, Kotlin y Swift (integración nativa profunda con el dispositivo), C++ (integración con Unreal Engine) y TypeScript/Node.js (integración con el backend).
- **Arquitecto del SDK Core** sora-flutter-core, el SDK de IA conversacional en tiempo real (AAR de Android) que controla el avatar con interacción voz a voz.
- Logré una conversación fluida y casi instantánea integrando y optimizando la latencia de Deepgram (ASR), OpenAI GPT (LLM) y ElevenLabs (TTS) mediante WebSockets en streaming, con medición de latencia en los tres proveedores.
- Diseñé un sistema de interrupción (barge-in) estable a lo largo de más de 10 iteraciones — desde detección por RMS hasta Silero VAD on-device, con cancelación inmediata, calibración de ruido ambiente y endpointing de ASR en el cliente con guardas de seguridad multicapa.
- Construí el puente Flutter ↔ Unreal Engine (C++) para el control del MetaHuman: sincronización de visemas de lipsync, subtítulos en tiempo real y gestión de estados con FSM.
- Integré detección de palabra de activación con ONNX on-device ("Hey AiMA", "Hola AiMA") en inglés, español y catalán, y robustecí el pipeline de audio de Android con AEC, supresión de ruido y control automático de ganancia.
- **Definí y lideré Jurojin App Platform**, la reestructuración agéntica del sistema de gestión de cuidadores: arquitectura supervisor-agente con sub-agentes de investigación, tools y skills, grafo de conocimiento de entidades con memoria en pgvector y seguridad multicapa sobre Firebase/Node.js.
- **Diseñé los flujos de desarrollo y releases de la empresa** — coordinación del roadmap entre personas y agentes de IA, estrategia de ramas, proceso de release y organización del trabajo del equipo.
- Impulsé la automatización del desarrollo agéntico: skills compartidas de Claude Code y pipelines de agentes autónomos que llevan un issue de GitHub por plan, implementación test-first, revisión y testing hasta una PR lista para mergear.
- Participé en decisiones clave de producto para sacarlo adelante; redacté RFCs sobre la abstracción de proveedores ASR, la arquitectura de lipsync y el diseño del barge-in.

### Consultor de Software Senior

#### ROI UP (vía Oxigent Consulting) | Sep 2024 – Ene 2026

- **Desarrollador Senior** liderando una aplicación móvil de fidelización global para Hitachi usando React Native con framework Expo, funcionando como referencia técnica y principal tomador de decisiones para la dirección del proyecto y hoja de ruta técnica.
- **Propiedad del proyecto**: Colaborar con PM para definir hitos del proyecto, coordinar progreso del equipo y servir como persona de referencia para actualizaciones de estado del proyecto entre todos los stakeholders.
- **Liderazgo Técnico**: Guiar y mentorizar un squad de desarrollo React Native, incluyendo incorporación de desarrolladores junior y establecimiento de mejores prácticas técnicas.
- Arquitecturé la aplicación móvil completa desde cero, seleccionando e implementando tecnologías core: Redux Toolkit, React Navigation, Apollo Client, Async Storage y React Native Paper.
- Integré servicios backend usando Apollo Client para consultas GraphQL y conexiones REST API, implementando autenticación basada en JWT y autorización basada en roles.
- Implementé Firebase Analytics y Crashlytics para monitoreo y reporte de errores.
- Establecí flujos de trabajo de desarrollo incluyendo manejo de formularios con validación Formik y Yup, e internacionalización usando i18n-js.
- Creé documentación técnica integral e implementé Storybook para documentación de componentes con soporte TypeScript.
- Implementé estrategia de testing con Jest y React Native Testing Library para pruebas unitarias/funcionales, y Maestro para pruebas end-to-end.
- **Reconocimiento del Cliente**: Logré calificación de 100% autonomía y recibí feedback excepcional por liderazgo técnico, capacidades de resolución de problemas y propiedad del proyecto por parte de la gerencia del cliente.

### Ingeniero de Software Frontend

#### 1950Labs | Dic 2023 - Sep 2024

- Colaborar con cliente basado en USA para desarrollar el proyecto Caddie.
- Utilizar Next.js, React y Redux para desarrollo frontend.
- Implementar servicios de chat en tiempo real usando PubNub.
- Desarrollar sistemas de notificaciones con Knock.app.
- Crear aplicación móvil wrapper usando Flutter para mostrar la aplicación web.
- Integrar la aplicación móvil wrapper con servicios del teléfono como notificaciones y contactos.
- Desplegar y gestionar el proyecto en AWS Amplify.
- Organizar tareas y colaborar usando herramientas como Asana, Figma y Slack.

### Ingeniero de Software FullStack / SRE/DevOps

#### Bucksapp | Sep 2021 - Jul 2024

- Desarrollar nuevas funcionalidades para la aplicación móvil Bucksapp escrita en React Native.
- Desarrollar nueva webapp desde cero usando Next.js, React, Redux y Sagas.
- Desarrollar aplicación simuladora móvil para la webapp usando framework Flutter.
- Mantener servicios escritos en python django.
- Desarrollar nuevos servicios escritos en python django con django-rest-framework.
- Mantener la infraestructura antigua en Google Cloud Platform.
- Gestionar redes, VMS, balanceadores de carga, DNS, bases de datos, Redis y Cloud Run Apps en GCP.
- Crear nuevas infraestructuras usando GKE.
- Implementar monitoreo usando Prometheus, Grafana y Alert manager.
- Gestionar los entornos para la infraestructura usando Kustomize.
- Implementar DevOps usando GitHub Actions, GitHub Super Linter, Testing Actions y Continuous Deployment construyendo imágenes en el pipeline.

### Co-Fundador / Ingeniero de Software Fullstack

#### Bellbird | Ene 2020 - Sep 2021

- Fundé esta empresa para desarrollar soluciones tecnológicas para clientes.
- Desarrollé aplicación móvil para PuntoFarma, la cadena de farmacias más grande de Paraguay, usando Flutter 2.0 con null safety y flutter_bloc para gestión de estado.
- Conecté su backend Oracle usando un backend intermedio escrito en Node.js con Express.js.
- Desplegué el backend y manejé tráfico de 9k+ usuarios diarios.
- Desarrollé backends usando Python con Django y Django Rest Framework.
- Desarrollé frontends usando React, Next.js, Redux y Sagas.
- Construí aplicaciones móviles usando Flutter, React Native, Android e iOS.
- Implementé infraestructura usando Docker y Docker Compose.
- Construí nueva infraestructura usando Kubernetes con Kubeadm.
- Configuré pipelines CI/CD usando GitLab CI.

### Ingeniero de Software Fullstack / Tech Lead

#### Softec SRL | Sep 2016 - Ene 2020

- Desarrollé aplicaciones fullstack con Django y JavaScript.
- Construí aplicaciones móviles para Android e iOS.
- Desarrollé aplicación de transporte tipo Uber llamada MUV usando Android/iOS/React Native y backend Node.js.
- Lideré un equipo de 3 desarrolladores y luego gestioné 4 equipos después de ser promovido a Tech Lead.
- Implementé pipelines CI/CD y desplegué aplicaciones usando Docker, Kubernetes en GKE.

### Ingeniero de Software FullStack

#### Freelance | Ene 2012 - Sep 2016

- Desarrollé sitios web usando HTML5/CSS3/JS.
- Creé aplicaciones web con Django, Django Rest Framework, jQuery y AngularJS.
- Construí aplicaciones nativas de Android.

## Idiomas

Inglés (Intermedio), Español (Nativo)
