# Leonardo García — Portafolio Fotográfico

Sitio web de portafolio personal desarrollado con **HTML5 y CSS3 puro**, sin frameworks ni dependencias de JavaScript externas. El proyecto nació como un ejercicio de diseño visual orientado a UI, con énfasis en tipografía editorial, composición y experiencia de usuario.

---

## Vista previa

![Portafolio Leonardo García](preview.jpg)

> Portafolio fotográfico con secciones de Retrato, Producto, MotorSport, Eventos y Sociales.  
> Diseño minimalista en escala de grises con tipografía de tipo editorial.

---

## Tecnologías utilizadas

| Tecnología | Uso |
|---|---|
| HTML5 | Estructura semántica del sitio |
| CSS3 | Diseño, layout, animaciones y responsive |
| JavaScript (Vanilla) | Scroll reveal con `IntersectionObserver` |
| Google Fonts | Tipografías Cormorant Garamond + Inter |
| WebP | Formato de imagen optimizado |

No se utilizó ningún framework de CSS (Bootstrap, Tailwind, etc.) ni librería de JavaScript externa. Todo el comportamiento interactivo —incluyendo el menú hamburguesa— está implementado con CSS puro.

---

## Estructura del proyecto

```
Portfolio/
├── index.html        # Estructura principal del sitio
├── style.css         # Estilos globales, layout y responsive
├── LeoIcon.png       # Favicon personalizado
└── img/              # Imágenes en formato WebP
    ├── yo.webp
    ├── ann.webp
    ├── yas.webp
    ├── yunblanco.webp
    ├── yunrosa.webp
    ├── BALLANTINES Jp.webp
    ├── cafe.webp
    ├── spaguetti.webp
    ├── cubierto.webp
    ├── collar.webp
    ├── trofeo.webp
    ├── 720.webp
    ├── drift.webp
    ├── corvette.webp
    ├── gt3blanco.webp
    ├── gt3gris.webp
    ├── gt3negro.webp
    ├── challenger.webp
    ├── catrina.webp
    ├── soldado.webp
    ├── Charro.webp
    ├── f35Bahia.webp
    ├── f35epic.webp
    ├── SyO-16.webp
    ├── NIC-19.webp
    └── L&A-47.webp
```

---

## Secciones del sitio

- **Portada** — Nombre del autor en tipografía de gran escala, subtítulo en versalitas.
- **Sobre mí** — Breve biografía con foto del fotógrafo.
- **Retrato** — Galería en grid de 4 columnas.
- **Producto** — Layout asimétrico tipo editorial (grid de 5 columnas con filas combinadas).
- **MotorSport** — Galería en grid de 3 columnas + sección hero a pantalla completa con tagline.
- **Eventos** — Galería en grid de 4 columnas + sección hero a pantalla completa con tagline.
- **Sociales** — Galería de eventos sociales en grid de 3 columnas.
- **Contacto** — Links a Instagram, teléfono y correo electrónico. Footer con datos del autor.

---

## Características de diseño y UI

### Menú hamburguesa (CSS puro)
El menú lateral se implementa sin JavaScript, usando el patrón `<input type="checkbox">` + selector CSS `~` (hermano siguiente). Al activarse, un panel lateral oscuro entra desde la derecha con transición suave.

### Scroll Reveal
Las secciones y elementos del contenido aparecen con una animación de entrada (`opacity` + `translateY`) al ingresar al viewport, implementada con la API nativa `IntersectionObserver`.

```js
const observer = new IntersectionObserver((entries) => {
  entries.forEach(e => {
    if (e.isIntersecting) {
      e.target.classList.add('visible');
      observer.unobserve(e.target);
    }
  });
}, { threshold: 0.12 });
```

### Secciones hero a pantalla completa
Las secciones `#motorsport-hero` y `#eventos-hero` utilizan imagen de fondo posicionada en `absolute` con `inset: 0`, sobre la cual se superpone un tagline en cursiva con `text-shadow` para legibilidad.

### Botón flotante de WhatsApp
Icono SVG inline sobre fondo oscuro, posicionado en `position: fixed`, con efecto `scale` en hover.

### Responsive Design
Breakpoints en `900px` y `540px` para adaptar las grillas y el layout de la sección "Sobre mí" a pantallas pequeñas. Respeta `prefers-reduced-motion` deshabilitando las animaciones cuando el usuario lo solicita desde su sistema operativo.

---

## Proceso de diseño

### Objetivo
El punto de partida fue una pregunta concreta: ¿cómo presentar fotografías en una página web sin que el diseño compita con las imágenes? La respuesta definió todas las decisiones que siguieron. El sitio debía ser un marco, no el cuadro.

### Principio rector: la imagen como protagonista
Se optó deliberadamente por una paleta sobria en escala de grises y una tipografía elegante pero discreta. Tanto el fondo como los textos existen para contextualizar y presentar, no para destacar por sí mismos. Los títulos de sección y las descripciones son funcionales: introducen, y ceden el espacio a las fotografías.

### Narrativa de scroll
El flujo del sitio fue diseñado como una experiencia progresiva. La portada invita a entrar con el nombre del autor a gran escala. A medida que el usuario baja, el contenido fotográfico va ganando presencia. Las secciones hero —páginas completas ocupadas por una sola fotografía con una pequeña frase en la esquina inferior— funcionan como respiros narrativos: momentos donde la imagen toma todo el espacio sin ninguna distracción. El contacto queda al final, como destino natural de quien llegó hasta ahí porque el contenido le interesó.

### Decisiones de layout
El grid asimétrico de la sección **Producto** responde a una necesidad concreta: incluir una fotografía adicional sin romper la coherencia visual de la cuadrícula. En pantallas anchas, dos columnas se extienden verticalmente para dar espacio a la imagen extra; en dispositivos móviles, el layout colapsa a columnas apiladas, resolviendo la complejidad sin sacrificar legibilidad.

### Herramientas y flujo de trabajo
El proceso no partió directamente del código. Primero se realizó una maqueta en **Canva**, trabajando la composición visual: disposición de fotografías, jerarquía tipográfica, paleta de color y proporciones de cada sección. Este documento sirvió como referencia directa para traducir el diseño a HTML y CSS, manteniendo la fidelidad visual entre la maqueta y el resultado final.

> Este proyecto es un ejercicio de **UI Design aplicado**: sin fase de research ni testing de usuarios, el proceso se centró en la toma de decisiones visuales fundamentadas en el objetivo comunicacional del sitio.

---

## Instalación y uso

No requiere instalación. Es un sitio estático que puede ejecutarse directamente en el navegador.

1. Clona o descarga el repositorio.
2. Abre `index.html` en cualquier navegador moderno.

Para publicarlo en la web puede usarse GitHub Pages, Netlify, Vercel u otro servicio de hosting estático.

---

## Contacto

**Leonardo García**  
📸 Instagram: [@leogar.20](https://www.instagram.com/leogar.20/)  
📞 +52 55 47 32 89 35  
✉️ leogar.ux.ui@gmail.com  
💬 [WhatsApp](https://wa.me/5215547328935)

---

*© 2026 Leonardo García — Portafolio Fotográfico*
