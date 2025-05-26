# CSS Grid Avanzado

## Introducción

CSS Grid es un sistema de diseño bidimensional que revoluciona la forma de estructurar layouts en la web moderna. Este repositorio contiene ejemplos prácticos para dominar conceptos avanzados de CSS Grid.

## Estructura del Repositorio

- `index.html`: Ejemplo principal con layout básico usando grid-template-areas
- `example02.html`: Demostración de técnicas avanzadas de grid
- `made-in-class.html`: Ejemplos desarrollados durante la clase
- `grid-template-areas/`: Carpeta con ejemplos específicos de grid-template-areas
- `grillas-fluidas/`: Carpeta con ejemplos de grids fluidos y responsivos

## Conceptos Fundamentales de CSS Grid

### Grid Container y Grid Items

```css
.contenedor {
  display: grid; /* Convierte el elemento en un grid container */
}
```

Los hijos directos de este contenedor se convierten automáticamente en grid items.

### Grid Template Areas

Una técnica poderosa para definir layouts de manera visual:

```css
.contenedor {
  display: grid;
  grid-template-columns: 100px 1fr;
  grid-template-rows: 48px 1fr 48px;
  grid-template-areas:
    "encabezado encabezado"
    "barra-lateral contenido"
    "pie-de-pagina pie-de-pagina";
}

.encabezado { grid-area: encabezado; }
.contenido { grid-area: contenido; }
.barra-lateral { grid-area: barra-lateral; }
.pie-de-pagina { grid-area: pie-de-pagina; }
```

### Unidades Flexibles y Fracciones (fr)

La unidad `fr` representa una fracción del espacio disponible:

```css
grid-template-columns: 1fr 2fr 1fr; /* Proporción 1:2:1 */
```

## Técnicas Avanzadas de CSS Grid

### 1. Funciones de Repetición y Rango

```css
/* Repetir valores */
grid-template-columns: repeat(3, 1fr);

/* Repetir patrones */
grid-template-columns: repeat(2, 100px 1fr);

/* Rangos de líneas */
grid-column: 1 / 3; /* Desde línea 1 hasta línea 3 */
grid-column: 1 / span 2; /* Abarca 2 columnas desde la línea 1 */
```

### 2. Grillas Responsivas Auto-Fill y Auto-Fit

```css
/* Auto-fill: Crea tantas columnas como quepan */
grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));

/* Auto-fit: Similar, pero colapsa las celdas vacías */
grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
```

### 3. Función minmax()

```css
/* Columnas con ancho mínimo y máximo */
grid-template-columns: minmax(100px, 1fr) 2fr;

/* Filas con alto mínimo y adaptable */
grid-template-rows: minmax(100px, auto);
```

### 4. Nombrar Líneas de Grid

```css
grid-template-columns: 
  [sidebar-start] 250px 
  [sidebar-end content-start] 1fr 
  [content-end];
```

### 5. Alineación Avanzada

```css
/* Alineación horizontal de los items */
justify-items: start | end | center | stretch;

/* Alineación vertical de los items */
align-items: start | end | center | stretch;

/* Alineación del contenido completo */
justify-content: start | end | center | stretch | space-around | space-between | space-evenly;
align-content: start | end | center | stretch | space-around | space-between | space-evenly;
```

### 6. Grid Implícito vs. Explícito

```css
/* Control del grid implícito */
grid-auto-rows: 100px;
grid-auto-columns: 1fr;
grid-auto-flow: row | column | dense;
```

## Casos de Uso Avanzados

### Layout Holy Grail (Santo Grial)

```css
.contenedor {
  display: grid;
  grid-template: 
    "header header header" 80px
    "nav contenido aside" 1fr
    "footer footer footer" 80px /
    200px 1fr 200px;
}
```

### Grid responsivo con breakpoints

```css
.contenedor {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  gap: 1rem;
}

@media (max-width: 768px) {
  .contenedor {
    grid-template-columns: 1fr;
  }
}
```

### Grids Anidados

```css
.item {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 10px;
}
```

## Ejercicios Prácticos

1. Crear un diseño de dashboard con áreas de diferentes tamaños
2. Implementar una galería de imágenes con grid-auto-flow: dense
3. Desarrollar un layout que cambie completamente su estructura en móviles
4. Experimentar con grid-template-areas para crear patrones complejos

## Compatibilidad con Navegadores

CSS Grid es compatible con todos los navegadores modernos. Para navegadores antiguos, considere usar:

```css
@supports (display: grid) {
  /* Código de CSS Grid aquí */
}
```

## Recursos Adicionales

- [MDN Web Docs: CSS Grid Layout](https://developer.mozilla.org/es/docs/Web/CSS/CSS_Grid_Layout)
- [CSS Tricks: Guía Completa de Grid](https://css-tricks.com/snippets/css/complete-guide-grid/)
- [Grid Garden](https://cssgridgarden.com/) - Juego para practicar CSS Grid
- [Grid by Example](https://gridbyexample.com/) - Ejemplos de Rachel Andrew

---

¡Experimenta con los ejemplos y lleva tus habilidades de CSS Grid al siguiente nivel!