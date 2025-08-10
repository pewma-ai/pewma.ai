# Pewma.ai Website PRD v2.0

## Goals and Background Context

### Goals

- Establecer una presencia en línea creíble y profesional para la iniciativa Pewma AI.
- Proporcionar un método de contacto claro y funcional para atraer a potenciales colaboradores.
- Implementar un sistema de analítica web para medir el interés inicial y el comportamiento de los usuarios.
- Asegurar que el sitio sea desplegado de forma segura y accesible en su dominio personalizado.
- Empaquetar el proceso de desarrollo del repositorio como un ejemplo educativo para la comunidad, cumpliendo la misión de la organización.

### Background Context

Pewma AI es una nueva iniciativa enfocada en adaptar la IA para el Sur Global. Como paso fundacional, necesita un sitio web para establecer su presencia digital, comunicar su misión y empezar a construir una comunidad. Este PRD detalla los requisitos para la primera versión de este sitio, que incluirá el despliegue de la página de inicio, un flujo de contacto funcional, la integración de analítica web y una documentación ejemplar del proceso.

### Change Log

| Date | Version | Description | Author |
| --- | --- | --- | --- |
| 2025-08-09 | 1.0 | Creación inicial del PRD solo para el despliegue. | John (PM) |
| 2025-08-09 | 2.0 | Alcance expandido para incluir formulario, analítica y README. | John (PM) |

## Requirements

### Functional

1. **FR1**: La página de inicio debe ser accesible públicamente en `https://pewma.ai`.
2. **FR2**: El subdominio `www.pewma.ai` debe redirigir al dominio raíz `pewma.ai`.
3. **FR3**: El sitio web debe servirse exclusivamente a través de una conexión segura HTTPS.
4. **FR4**: Un clic en el botón "CONVERSEMOS" en `index.html` debe llevar al usuario a la página `contacto.html`.
5. **FR5**: El formulario en `contacto.html` debe enviar los datos a un endpoint de Formspree.
6. **FR6**: Tras un envío exitoso, el usuario debe ser redirigido a la página `gracias.html`.
7. **FR7**: El script de seguimiento de Google Analytics debe estar presente y activo en todas las páginas HTML del sitio.
8. **FR8**: El archivo `README.md` del repositorio debe explicar claramente el propósito del proyecto, la metodología BMAD utilizada y cómo otros pueden usarlo como un ejemplo.

### Non-Functional

1. **NFR1**: La infraestructura del sitio web debe estar alojada en GitHub Pages.
2. **NFR2**: La configuración de DNS para el dominio raíz debe usar registros `A` que apunten a las IPs de GitHub.
3. **NFR3**: La gestión de envíos de formularios debe utilizar el servicio de terceros Formspree.
4. **NFR4**: La analítica web debe ser gestionada por Google Analytics.

## Epic and Story Structure

### Epic 1: Deploy Pewma.ai Landing Page to Production

- **Epic Goal**: Hacer que la página de inicio de Pewma.ai esté en línea y accesible públicamente en el dominio personalizado `pewma.ai`, servida de forma segura a través de GitHub Pages.
- **Stories**:
    - **Story 1.1: Reconfigure Repository for PEWMA.AI Domain Deployment.**
    - **Story 1.2: Configure Custom Domain and DNS Records.**
    - **Story 1.3: Deploy to GitHub Pages and Verify HTTPS.**

### Epic 2: Implement Multi-Page Contact Form

- **Epic Goal**: Crear un flujo de contacto con una página dedicada que envíe datos a través de Formspree y redirija a una página de agradecimiento personalizada.
- **Stories**:
    - **Story 2.1: Update Homepage CTA and Create Contact Page Shell.**
    - **Story 2.2: Build and Style the Contact Form UI.**
    - **Story 2.3: Create the "Thank You" Page.**
    - **Story 2.4: Configure Formspree and Activate Submission & Redirect.**

### Epic 3: Integrate Web Analytics

- **Epic Goal**: Integrar Google Analytics en todas las páginas para medir los KPIs de éxito.
- **Stories**:
    - **Story 3.1: Set up Google Analytics Account and Obtain Tracking ID (User Task).**
    - **Story 3.2: Embed Google Analytics Tracking Script on All Pages.**

### Epic 4: Create Educational README.md as a Project Deliverable

- **Epic Goal**: Crear un archivo `README.md` completo que documente el proceso de creación del proyecto, sirviendo como una herramienta educativa.
- **Stories**:
    - **Story 4.1: Draft the `README.md` Content.**
    - **Story 4.2: Format and Publish the `README.md` File.**