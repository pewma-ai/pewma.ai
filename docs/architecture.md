# Documento de Arquitectura del Sitio Web de Pewma.ai v2.0

## Introducción

Este documento captura el ESTADO ACTUAL del código del sitio web de Pewma.ai. Evolucionó desde una sola página de aterrizaje a un sitio estático multipágina con integraciones de servicios de terceros. Sirve como referencia para todo el equipo y para agentes de IA.

### Alcance del documento

Enfocado en los tres archivos HTML principales (`index.html`, `contacto.html`, `gracias.html`) y en sus servicios integrados, que constituyen el sistema actual completo.

### Registro de cambios

| Fecha | Versión | Descripción | Autor |
| --- | --- | --- | --- |
| 9 de agosto de 2025 | 1.0 | Análisis brownfield inicial de la página de aterrizaje única. | Winston (Arquitecto) |
| 10 de agosto de 2025 | 2.0 | Actualizado para reflejar la estructura multipágina y la integración de EmailJS y Google Analytics. | Sarah (PO) |

## Referencia rápida - Archivos clave

- **`index.html`**: La página de aterrizaje principal.
- **`contacto.html`**: La página que contiene el formulario de contacto.
- **`gracias.html`**: La página de confirmación mostrada tras un envío exitoso del formulario.

## Arquitectura de alto nivel

### Resumen técnico

El proyecto Pewma.ai es un sitio web estático multipágina construido con HTML5 y CSS3 puros. La arquitectura se mantuvo intencionalmente simple para favorecer el rendimiento y la mantenibilidad, pero se ha mejorado con JavaScript en el cliente para aportar funcionalidad clave. Ahora se integra con el servicio EmailJS para gestionar los envíos del formulario de contacto y con Google Analytics 4 para el análisis de tráfico. Todos los estilos permanecen autocontenidos dentro de cada archivo HTML.

### Stack tecnológico actual

| Categoría | Tecnología | Versión/Detalles | Notas |
| --- | --- | --- | --- |
| Estructura | HTML5 | `<!DOCTYPE html>` | HTML semántico estándar en las tres páginas. |
| Estilos | CSS3 | Embebido en `<style>` | Usa variables CSS y es consistente en todas las páginas. |
| Scripting en cliente | JavaScript (ES6) | Embebido en `<script>` | Utilizado para habilitar el envío del formulario con EmailJS. |
| Manejo de formularios | EmailJS | SDK v4 | Servicio del lado del cliente para enviar correos sin backend. |
| Analítica | Google Analytics 4 | `gtag.js` | Script de seguimiento en cliente para analítica de usuarios. |
| Fuentes | Google Fonts | `Merriweather` | Dependencia externa para tipografía. |

### Verificación de la estructura del repositorio

- **Tipo**: Sitio estático multipágina.
- **Gestor de paquetes**: Ninguno.
- **Destacado**: La arquitectura evolucionó para incluir una integración de JavaScript en cliente, un cambio significativo desde el diseño inicial sin JS.

## Árbol de código y organización de módulos

### Estructura del proyecto (actual)

```plaintext
pewma-ai.github.io/
├── docs/
│   ├── project-brief.md
│   ├── architecture.md
│   ├── prd.md
│   └── stories/
│       └── ... (archivos de historias)
├── index.html
├── contacto.html
└── gracias.html
```

### Módulos clave y propósito

- **Página de inicio (`index.html`)**: Presenta la misión y visión. El CTA principal ahora enlaza a `contacto.html`.
- **Formulario de contacto (`contacto.html`)**: Contiene el formulario de usuario y la lógica JavaScript para enviar los datos mediante el SDK de EmailJS.
- **Página de agradecimiento (`gracias.html`)**: Destino tras un envío exitoso del formulario; entrega feedback al usuario y mensajes estratégicos.

## Modelos de datos y APIs

- **Modelos de datos**: Ninguno. El contenido es estático.
- **APIs de terceros consumidas**:
  - **EmailJS**: El sitio utiliza el SDK de EmailJS en cliente (`emailjs.sendForm`) para enviar datos del formulario. Requiere un Service ID, Template ID y Public Key, almacenados en el JavaScript del lado del cliente.

## Deuda técnica y problemas conocidos

- **Problema resuelto**: La dependencia previa de un enlace `mailto:` se reemplazó por la implementación del formulario de contacto con EmailJS.
- **Nueva consideración**: La Public Key de EmailJS queda expuesta en el código del lado del cliente (`contacto.html`). Es el diseño previsto por EmailJS, pero es un aspecto arquitectónico importante a considerar.

## Puntos de integración y dependencias externas

- **Google Fonts**: Provee la familia tipográfica `Merriweather`.
- **EmailJS**: Gestiona toda la lógica de envío del formulario de contacto. El sitio depende de la disponibilidad de su CDN y API.
- **Google Analytics**: Provee toda la medición de tráfico del sitio. Depende de que el script `gtag.js` esté disponible.

## Desarrollo y despliegue

### Configuración de desarrollo local

1. No se requiere configuración especial. Los archivos HTML pueden abrirse directamente en un navegador.
2. Probar el envío del formulario requiere conexión a internet para alcanzar la API de EmailJS.

### Proceso de build y despliegue

- **Comando de build**: Ninguno.
- **Despliegue**: Se realiza con `git push` a la rama `main` del repositorio `pewma-ai.github.io`, lo que desencadena automáticamente el build y despliegue de GitHub Pages.

## Estado de pruebas

- **Cobertura de pruebas actual**: Ninguna.
- **Enfoque de pruebas**:
  - Verificación visual manual de las tres páginas.
  - Pruebas funcionales manuales del envío del formulario de contacto, incluyendo verificación de recepción del correo y redirección del navegador.
  - Verificación manual del panel de tráfico en tiempo real de Google Analytics.
```