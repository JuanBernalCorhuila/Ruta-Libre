# 🦽 RutaLibre — Accesibilidad Urbana Colaborativa

> *"Encuentra tu ruta, vive tu ciudad."*

**RutaLibre** es una plataforma web colaborativa que permite a ciudadanos de Neiva (Huila, Colombia) reportar y consultar el nivel de accesibilidad de lugares públicos y comerciales para personas en silla de ruedas. A través del **crowdsourcing**, la comunidad actúa como sensor social, generando información en tiempo real sobre rampas, baños adaptados, ascensores y puertas anchas, antes de que una persona tenga que desplazarse y descubrir las barreras por su propia cuenta.

---

## 📌 Contexto del Proyecto

| Campo | Detalle |
|---|---|
| **Institución** | Corporación Universitaria del Huila — CORHUILA |
| **Facultad** | Ingeniería |
| **Programa** | Ingeniería de Sistemas |
| **Semestre** | Quinto (5°) |
| **Asignatura** | Análisis y Diseño de Sistemas |
| **Tipo** | Proyecto Integrador de Aula |
| **Metodología** | Aprendizaje Basado en Proyectos (ABP) + Desarrollo Ágil |
| **Período** | Mayo 2026 |
| **Repositorio** | [github.com/JuanBernalCorhuila/Ruta-Libre](https://github.com/JuanBernalCorhuila/Ruta-Libre) |

---

## 👥 Equipo

| Nombre | Identificación | Rol |
|---|---|---|
| Juan Camilo Bernal Gordillo | 1016949442 | Estudiante |
| Laura Marcela Quintero Poveda | 1077848632 | Estudiante |
| Cristian Andrés Muñoz Montenegro | 1083878218 | Estudiante |

---

## 🎯 Problema y Solución

### Problema
Según el DANE (2018), aproximadamente **3,1 millones de personas en Colombia presentan discapacidad física**. En Neiva, la infraestructura urbana presenta barreras arquitectónicas que limitan la movilidad de personas en silla de ruedas. No existe ninguna herramienta digital local que centralice información sobre accesibilidad urbana, lo que obliga a estas personas a descubrir las barreras cuando ya están en el lugar, reduciendo su autonomía y participación social.

**Pregunta de investigación:**
> *¿De qué manera el desarrollo de una plataforma web colaborativa basada en crowdsourcing puede centralizar y hacer disponible la información sobre accesibilidad urbana para personas en silla de ruedas en la ciudad de Neiva, Huila?*

### Solución
RutaLibre resuelve la incertidumbre de si un lugar cuenta con rampas, ascensores o baños adaptados antes de realizar el desplazamiento, fomentando una ciudad más inclusiva y participativa. El sistema calcula una **Puntuación de Accesibilidad** basada en los reportes de la comunidad, y visualiza esta información directamente en un mapa interactivo integrado con Google Maps API.

---

## ✅ Requerimientos Funcionales

| ID | Descripción |
|---|---|
| **RF-01** | Registro e inicio de sesión de usuarios (Email / Google OAuth) |
| **RF-02** | Buscar lugares por nombre o categoría en el mapa interactivo |
| **RF-03** | Reportar el estado de accesibilidad de un lugar (Rampas, Puertas anchas, Baños) |
| **RF-04** | Adjuntar fotos como evidencia de accesibilidad |
| **RF-05** | Calcular una "Puntuación de Accesibilidad" basada en reportes comunitarios |
| **RF-06** | Dejar comentarios detallados sobre la experiencia en el lugar |
| **RF-07** | Filtrar lugares según nivel de accesibilidad (Verde: Accesible / Rojo: No accesible) |
| **RF-08** | Guardar "Lugares Favoritos" para acceso rápido |
| **RF-09** | Rol de Administrador para validar reportes marcados como spam o incorrectos |
| **RF-10** | Geolocalización en tiempo real del usuario para mostrar sitios cercanos |

---

## ⚙️ Requerimientos No Funcionales

| ID | Categoría | Descripción |
|---|---|---|
| **RNF-01** | Disponibilidad | El sistema debe estar disponible el **99.9%** del tiempo anual |
| **RNF-02** | Rendimiento | Tiempo de carga del mapa ≤ **3 segundos** |
| **RNF-03** | Seguridad | Contraseñas cifradas con **BCrypt** |
| **RNF-04** | Usabilidad | Interfaz conforme a **WCAG 2.1** (contraste alto, lectores de pantalla) |
| **RNF-05** | Escalabilidad | Soporte para hasta **5,000 usuarios concurrentes** sin degradación |
| **RNF-06** | Portabilidad | Web app **responsiva** (móvil y escritorio) |
| **RNF-07** | Mantenibilidad | Código documentado con control de versiones en **Git** |
| **RNF-08** | Privacidad | Cumplimiento con la **Ley de Habeas Data** (Colombia) |
| **RNF-09** | Interoperabilidad | Integración con **Google Maps API** |
| **RNF-10** | Localización | Soporte para **Español e Inglés** |

---

## 🗺️ Diagramas

El repositorio incluye **9 diagramas** en formato SVG dentro de la carpeta `/Diagramas`:

### Diagramas UML de Casos de Uso

| Archivo | Requerimiento | Actores | Descripción |
|---|---|---|---|
| [Diagrama RF-01 Registro e Inicio de Sesión.svg](https://github.com/JuanBernalCorhuila/Ruta-Libre/blob/master/Diagramas/Diagrama%20RF-01%20Registro%20e%20Inicio%20de%20Sesi%C3%B3n.svg) | RF-01 | Visitante, Usuario Registrado, Sistema | Flujos de autenticación: registro por email, inicio de sesión, Google OAuth y cierre de sesión. La validación del formulario se representa como `<<include>>`. |
| [Diagrama RF-02 Buscar lugares en el mapa.svg](https://github.com/JuanBernalCorhuila/Ruta-Libre/blob/master/Diagramas/Diagrama%20RF-02%20Buscar%20lugares%20en%20el%20mapa.svg) | RF-02 | Visitante, Usuario Registrado, Sistema | Interacción con el mapa: búsqueda por nombre, filtro por categoría y carga de Google Maps API como `<<include>>`. Ver detalle del lugar es una `<<extend>>` opcional. |
| [Diagrama RF-05 Calcular puntuación de accesibilidad.svg](https://github.com/JuanBernalCorhuila/Ruta-Libre/blob/master/Diagramas/Diagrama%20RF-05%20Calcular%20puntuaci%C3%B3n%20de%20accesibilidad.svg) | RF-05 | Usuario, Sistema | El usuario envía un reporte → el sistema calcula la puntuación → la muestra en el mapa. Actualizar puntuación es una `<<extend>>` para lugares con evaluación previa. |
| [Diagrama RNF-04 Usabilidad WCAG 2.1.svg](https://github.com/JuanBernalCorhuila/Ruta-Libre/blob/master/Diagramas/Diagrama%20RNF-04%20Usabilidad%20WCAG%202.1.svg) | RNF-04 | Usuario, Sistema | Validación automática de contraste de colores, adaptación al dispositivo, soporte para lectores de pantalla y modo alto contraste. |
| [Diagrama RNF-05 Escalabilidad.svg](https://github.com/JuanBernalCorhuila/Ruta-Libre/blob/master/Diagramas/Diagrama%20RNF-05%20Escalabilidad.svg) | RNF-05 | Usuario, Administrador, Sistema | Gestión de usuarios concurrentes: verificación de carga, advertencia de sobrecarga, escalado automático y reportes de rendimiento para el administrador. |
| [Diagrama RNF-09 Interoperabilidad con Google Maps API.svg](https://github.com/JuanBernalCorhuila/Ruta-Libre/blob/master/Diagramas/Diagrama%20RNF-09%20Interoperabilidad%20con%20Google%20Maps%20API.svg) | RNF-09 | Usuario, Sistema, Google Maps API | Integración con Google Maps: solicitud y renderización de datos cartográficos, geolocalización y manejo de fallo de API. |

### Diagramas BPMN (Business Process Model and Notation)

| Archivo | Requerimiento | Participantes | Descripción |
|---|---|---|---|
| [Diagrama BPMN - RF1.svg](https://github.com/JuanBernalCorhuila/Ruta-Libre/blob/master/Diagramas/Diagrama%20BPMN%20-%20RF1.svg) | RF-01 | Usuario, Sistema | Proceso completo de autenticación: selección de método (email o Google), validación de datos, creación de sesión y redirección al inicio. |
| [Diagrama BPMN - RF3.svg](https://github.com/JuanBernalCorhuila/Ruta-Libre/blob/master/Diagramas/Diagrama%20BPMN%20-%20RF3.svg) | RF-03, RF-04 | Usuario, Sistema, Administrador | Proceso de reporte: búsqueda y selección de lugar → registro de criterios y foto → validación → cálculo de puntuación → revisión del administrador (aprobación o eliminación por spam). |
| [Diagrama BPMN - RF5.svg](https://github.com/JuanBernalCorhuila/Ruta-Libre/blob/master/Diagramas/Diagrama%20BPMN%20-%20RF5.svg) | RF-05 | Usuario, Sistema, Base de Datos | Cálculo de puntuación: el usuario evalúa criterios → el sistema consulta reportes previos → pondera criterios → si puntuación ≥ 70 asigna marcador verde, si no, marcador rojo. |

---

## 📖 Historias de Usuario

El proyecto define **5 historias de usuario** para el Sprint 1, cada una con DoR (Definition of Ready), DoD (Definition of Done) y criterios de aceptación Gherkin:

| ID | Nombre | Módulo | Prioridad |
|---|---|---|---|
| **HU-01** | Registro e inicio de sesión | Autenticación | Alta |
| **HU-02** | Búsqueda de lugares en el mapa | Mapa / Exploración | Alta |
| **HU-03** | Reporte de accesibilidad con fotos | Reportes | Alta |
| **HU-04** | Consulta de puntuación de accesibilidad | Accesibilidad / Mapa | Alta |
| **HU-05** | Gestión de reportes por el Administrador | Administración | Alta |

### Resumen de criterios de aceptación clave

**HU-03 — Reporte de accesibilidad**
- El sistema acepta reportes solo si al menos un atributo de accesibilidad está seleccionado.
- Solo se aceptan imágenes JPG o PNG con un máximo de 5 MB.
- Un visitante sin sesión es redirigido al login al intentar reportar.
- Los reportes quedan en estado *"pendiente de validación"* hasta la aprobación del administrador.

**HU-04 — Puntuación de accesibilidad**
- Un lugar necesita mínimo 3 reportes aprobados para mostrar puntuación.
- Si no hay suficientes reportes, muestra: *"Este lugar aún no tiene suficientes evaluaciones. ¡Sé el primero en reportar!"*
- La puntuación se recalcula automáticamente cuando el administrador aprueba un nuevo reporte.

**HU-05 — Gestión por el administrador**
- Solo usuarios con rol Administrador pueden acceder al panel.
- El administrador puede aprobar o rechazar con un clic, indicando el motivo del rechazo.
- El usuario recibe notificación del resultado de su reporte.

---

## 🗂️ User Story Map

El archivo [`RutaLibre_UserStoryMap.svg`](https://github.com/JuanBernalCorhuila/Ruta-Libre/blob/master/Documentaci%C3%B3n/RutaLibre_UserStoryMap.svg) organiza el producto en **5 épicas** que siguen el flujo natural del usuario:

```
Gestión de Usuarios → Exploración del Mapa → Reporte de Lugares → Evaluación de Accesibilidad → Moderación de Contenido
```

**Sprint 1** (ciclo mínimo viable completo): HU-01 · HU-02 · HU-03 · HU-04 · HU-05

**Sprint 2** (funcionalidades complementarias): Filtro verde/rojo en el mapa · Guardar favoritos · Comentarios en lugares · Geolocalización en tiempo real

---

## 🖥️ Mockup Interactivo

El prototipo interactivo de alta fidelidad fue desarrollado con **[Google AI Studio](https://aistudio.google.com)**. Cubre las 5 pantallas principales del sistema:

| Pantalla | Descripción | HU / RF cubiertos |
|---|---|---|
| **Login** | Logo + eslogan, campos de email/contraseña, botón morado, opción "Continuar con Google" | HU-01 |
| **Mapa Interactivo** | Barra de búsqueda, marcadores verde/amarillo/rojo según accesibilidad, panel lateral con lugares de Neiva y botón coral "REPORTAR" | HU-02, RF-07, RF-10 |
| **Detalle del Lugar** | Fotos reales, puntuación de accesibilidad (ej. 94%), atributos verificados con íconos (rampas, baños, puertas) | HU-04, RF-05 |
| **Formulario de Reporte** | Checklist de atributos, zona de carga de fotos, campo de comentarios, botón coral "ENVIAR REPORTE" | HU-03, RF-03, RF-04 |
| **Panel del Administrador** | Barra lateral oscura, tabla de reportes pendientes con usuario, fecha, atributos y botón "APROBAR" | HU-05, RF-09 |

### 🔗 [Ver Mockup Interactivo →](https://rutalibre-mockup-606410931022.us-east1.run.app)

---

## 📁 Estructura del Repositorio

```
Ruta-Libre/
├── Diagramas/
│   ├── Diagrama BPMN - RF1.svg           # BPMN: Registro e inicio de sesión
│   ├── Diagrama BPMN - RF3.svg           # BPMN: Reporte de accesibilidad
│   ├── Diagrama BPMN - RF5.svg           # BPMN: Cálculo de puntuación
│   ├── Diagrama RF-01 Registro e Inicio de Sesión.svg
│   ├── Diagrama RF-02 Buscar lugares en el mapa.svg
│   ├── Diagrama RF-05 Calcular puntuación de accesibilidad.svg
│   ├── Diagrama RNF-04 Usabilidad WCAG 2.1.svg
│   ├── Diagrama RNF-05 Escalabilidad.svg
│   └── Diagrama RNF-09 Interoperabilidad con Google Maps API.svg
├── Documentación/
│   ├── Documentacion_Proyecto.pdf        # Documentación técnica completa (15 págs.)
│   ├── INFORME PROYECTO.xlsx             # Informe institucional CORHUILA
│   └── RutaLibre_UserStoryMap.svg        # User Story Map completo
└── README.md
```

---

## 📚 Objetivos del Proyecto

**Objetivo General:**
Desarrollar una plataforma web colaborativa que centralice información actualizada sobre accesibilidad urbana en Neiva mediante crowdsourcing, para mejorar la autonomía de las personas en silla de ruedas.

**Objetivos Específicos:**
1. Analizar los requerimientos funcionales y no funcionales del sistema.
2. Diseñar la arquitectura incluyendo modelo de base de datos, endpoints REST y diagramas UML y BPMN.
3. Implementar el backend con Node.js, Express y MySQL incluyendo autenticación y sistema de reportes.
4. Integrar la API de Google Maps para visualización georreferenciada y geolocalización en tiempo real.
5. Evaluar el sistema mediante pruebas funcionales y criterios de aceptación de las historias de usuario.

---

## 📎 Bibliografía

- DANE. (2018). *Censo Nacional de Población y Vivienda*. https://www.dane.gov.co
- Congreso de Colombia. (2013). *Ley 1618 de 2013*. https://www.funcionpublica.gov.co
- Pressman, R. S., & Maxim, B. R. (2021). *Ingeniería del software: Un enfoque práctico* (9.ª ed.). McGraw-Hill.

---

<div align="center">
  <sub>Proyecto Integrador · Análisis y Diseño de Sistemas · CORHUILA · Mayo 2026</sub>
</div>
