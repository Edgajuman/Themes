# CubicLauncher Themes

Repositorio comunitario de temas personalizados para CubicLauncher, un launcher de Minecraft.

## ¿Qué es esto?

Este repositorio funciona como un **registro centralizado de temas visuales** creados por la comunidad. Cada tema define la apariencia completa del launcher mediante **variables CSS**, imágenes de fondo y fuentes personalizadas.

Los temas se distribuyen como archivos `.zip` que contienen:

* `theme.json` → Definición del tema
* Imagen de fondo opcional (`bg.png`, `bg.jpg`, `bg.gif`, `bg.webp`)
* `Showcase.png` → Vista previa del tema
* Archivos de fuente personalizados (`.woff2`, `.ttf`, `.otf`, etc.) opcionales

## Estructura

```text
src/
  Author/
    ThemeName/
      ThemeName:Author.zip
      Showcase.png
```

Cada tema se organiza bajo `src/` con el formato `Autor/NombreDelTema/`.

## ¿Cómo crear un tema?

1. Crea una carpeta `src/TuNombre/TuTema/`.
2. Añade un archivo `theme.json` válido.
3. El archivo debe cumplir con el esquema definido en `theme-schema.json`.
4. Incluye una imagen de fondo opcional (máximo 25 MB; formatos soportados: PNG, JPG, GIF y WEBP).
5. Incluye un archivo `Showcase.png` como vista previa.
6. Empaqueta el contenido en un archivo `.zip`.

### Estructura mínima

```json
{
  "name": "Mi Tema",
  "author": "TuNombre",
  "version": "1.0.0",
  "type": "user",
  "variables": {
    "--bg-main": "#121212",
    "--text-primary": "#ffffff",
    "--accent": "#4caf50"
  }
}
```

## Propiedades principales

### Metadatos

| Propiedad | Descripción                                                 |
| --------- | ----------------------------------------------------------- |
| `name`    | Nombre visible del tema                                     |
| `author`  | Autor del tema                                              |
| `version` | Versión del tema                                            |
| `type`    | `user` para temas externos, `builtin` para temas integrados |

### Fondo

| Propiedad          | Descripción                              |
| ------------------ | ---------------------------------------- |
| `bg_image`         | Nombre del archivo de imagen de fondo    |
| `bg_image_blur`    | Desenfoque aplicado al fondo (ej: `8px`) |
| `bg_image_opacity` | Opacidad del fondo (`0` a `1`)           |

### Fuentes personalizadas

Los temas pueden incluir fuentes mediante la propiedad `fonts`.

Ejemplo:

```json
{
  "fonts": [
    {
      "family": "Inter",
      "src": "Inter-Regular.woff2",
      "format": "woff2",
      "weight": "400",
      "style": "normal"
    }
  ]
}
```

## Variables CSS disponibles

### Fondos

* `--bg-main`
* `--bg-sidebar`
* `--bg-card`
* `--bg-item-active`
* `--bg-overlay`
* `--bg-input`
* `--bg-sidebar-gradient`
* `--bg-card-gradient`

### Texto

* `--text-primary`
* `--text-secondary`
* `--text-muted`

### Bordes

* `--border`
* `--border-color`
* `--border-width`
* `--border-radius`
* `--border-radius-sm`
* `--border-radius-lg`

### Colores de acento

* `--accent`
* `--accent-rgb`
* `--accent-hover`
* `--accent-primary`
* `--accent-text`

### Sombras y efectos

* `--shadow-sm`
* `--shadow-md`
* `--glow-accent`
* `--glow-error`
* `--glow-success`

### Colores semánticos

* `--color-success`
* `--color-success-rgb`
* `--color-error`
* `--color-error-rgb`
* `--color-warning`
* `--color-warning-rgb`

### Estados de servidor

* `--color-status-starting`
* `--color-status-started`

### Colores de loaders

* `--clr-loader-vanilla`
* `--clr-loader-fabric`
* `--clr-loader-forge`
* `--clr-loader-quilt`

### Iconos

* `--icon-filter`
* `--icon-filter-error`

### Layout

* `--sidebar-width`

### Scrollbar

* `--scrollbar-track`
* `--scrollbar-thumb`

### Tipografía

* `--font-family`
* `--font-size-base`
* `--font-size-sm`
* `--font-size-lg`

Además, el esquema permite variables CSS personalizadas adicionales mediante propiedades extra dentro de `variables`.

## Ejemplo completo

```json
{
  "name": "Dark Emerald",
  "author": "Example",
  "version": "1.0.0",
  "type": "user",
  "bg_image": "bg.webp",
  "bg_image_blur": "12px",
  "bg_image_opacity": 0.35,
  "variables": {
    "--bg-main": "#0f1115",
    "--bg-sidebar": "#171a21",
    "--bg-card": "#1d212b",
    "--text-primary": "#ffffff",
    "--text-secondary": "#c0c5d0",
    "--accent": "#3ddc84",
    "--accent-rgb": "61,220,132",
    "--accent-hover": "#57e594",
    "--accent-text": "#0f1115",
    "--border-radius": "12px",
    "--shadow-md": "0 8px 30px rgba(0,0,0,.35)"
  }
}
```

## Validación

[`theme-schema.json`](theme-schema.json) es el esquema oficial basado en JSON Schema Draft-07 utilizado por CubicLauncher para validar temas.

Todo tema enviado al repositorio debe cumplir este esquema.

## Licencia

Este proyecto está bajo [CC0 1.0 Universal](LICENSE) — dominio público. Siéntete libre de usar, modificar y distribuir.
