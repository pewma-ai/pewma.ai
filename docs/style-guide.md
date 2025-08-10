# Manual de Estilos Visuales de Pewma.ai

Este documento sirve como la fuente única de verdad para la identidad visual y los componentes de la interfaz de usuario del sitio web de Pewma AI. Su propósito es asegurar la consistencia, eficiencia y mantenibilidad a medida que el proyecto evolucione.

## 1. Paleta de Colores

La paleta de colores se basa en un tema formal, limpio y profesional. Se gestiona a través de variables CSS para facilitar su mantenimiento.

| Variable CSS | Valor HEX | Uso Principal |
| :--- | :--- | :--- |
| `--bg-color` | `#FDFDFD` | Color de fondo principal del sitio. |
| `--text-primary`| `#2c3e50` | Texto principal, encabezados. |
| `--text-secondary`| `#596a7b` | Texto secundario, párrafos de apoyo. |
| `--accent` | `#D35400` | Botones principales (CTA), enlaces y acentos visuales. |
| `--highlight-bg`| `rgba(211, 84, 0, 0.07)` | Fondo para secciones destacadas. |
| `--border-color`| `#e0e0e0` / `#ccc` | Bordes sutiles para elementos como formularios. |

## 2. Tipografía

La tipografía principal busca ser formal, legible y elegante.

* **Familia Principal:** `Merriweather`, 'Georgia', serif (cargada desde Google Fonts).
* **Grosores Utilizados:** 300 (Light), 400 (Regular), 700 (Bold).
* **Altura de Línea (General):** `1.8` para una legibilidad óptima.

| Elemento | Tamaño de Fuente (Desktop) | Peso (Weight) | Color |
| :--- | :--- | :--- | :--- |
| Logo (`h1.logo`) | `2.5rem` | 400 | `var(--text-primary)` |
| Tagline (`p.tagline`)| `1.6rem` | 300 | `var(--text-secondary)`|
| Encabezado 2 (`h2`)| `1.5rem` | 700 | `var(--accent)` |
| Encabezado 3 (`h3`)| `1.2rem` | 700 | `var(--text-primary)` |
| Encabezado 4 (`h4`)| `1.0rem` | 700 | `var(--text-secondary)`|
| Párrafo (`p`) | `1.1rem` | 300 | `var(--text-primary)` |
| Texto Secundario (`p`)| `1.05rem`| 300 | `var(--text-secondary)`|
| Lista (`li`) | `1.05rem`| N/A | `var(--text-secondary)`|

## 3. Layout (Maquetación)

La estructura principal del sitio se basa en un contenedor centralizado.

* **Clase:** `.container`
* **Ancho Máximo:** `850px`
* **Padding (Desktop):** `80px 40px`
* **Padding (Mobile):** `60px 20px`

## 4. Componentes Clave

Estos son los bloques de construcción reutilizables de la interfaz.

### Botón Principal (CTA)
* **Clase:** `.cta-button`
* **Descripción:** Es el principal llamado a la acción, usado para los botones más importantes.
```css
.cta-button {
    display: inline-block;
    padding: 15px 40px;
    background: var(--accent);
    color: #FFFFFF;
    text-decoration: none;
    border-radius: 4px;
    font-weight: 700;
    text-transform: uppercase;
    letter-spacing: 0.05em;
    transition: all 0.3s ease;
}

.cta-button:hover {
    background: #2c3e50;
    transform: translateY(-2px);
    box-shadow: 0 5px 15px rgba(0,0,0,0.1);
}
```

### Formulario de Contacto

- **Descripción:** Estilos para todos los elementos del formulario en `contacto.html`.

```css
form label {
    display: block;
    margin-bottom: 8px;
    font-weight: 700;
    font-size: 0.9rem;
    color: var(--text-secondary);
}

form input[type="text"],
form input[type="email"],
form select,
form textarea {
    width: 100%;
    padding: 12px;
    border: 1px solid var(--border-color);
    border-radius: 4px;
    font-size: 1rem;
}

form input:focus,
form select:focus,
form textarea:focus {
    outline: none;
    border-color: var(--accent);
    box-shadow: 0 0 0 2px rgba(211, 84, 0, 0.2);
}
```

### Bloque de Firma

- **Clase:** `.signature`
- **Descripción:** Utilizado en la página de agradecimiento para firmar el mensaje.

```css
.signature {
    margin-top: 50px;
    padding-top: 20px;
    border-top: 1px solid var(--border-color);
}
.signature .name {
    font-weight: 700;
}
.signature .title {
    font-size: 0.9rem;
    color: var(--text-secondary);
}
```

## 5. Animaciones

Se utilizan animaciones sutiles para mejorar la experiencia de carga de la página.

- **`fadeInUp`**: El elemento aparece desde abajo con un efecto de desvanecimiento. Usado en el `<header>`.
- **`fadeIn`**: El elemento aparece con un efecto de desvanecimiento. Usado en las secciones y el tagline.

## 6. Diseño Responsivo (Mobile)

El sitio utiliza un único punto de quiebre (`breakpoint`) para adaptarse a pantallas más pequeñas.

- **Breakpoint:** `max-width: 768px`
- **Cambios Principales:**
    - Se reduce el `padding` del `.container`.
    - Se reduce el tamaño de la fuente del `.logo`, `.tagline` y los párrafos para mejorar la legibilidad.