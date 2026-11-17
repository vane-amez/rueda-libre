# 🚲 Rueda Libre — Ecosistema Web v2.0 & Campaña Rueda Nocturna
Plataforma web oficial de movilidad urbana y alquiler de bicicletas en Medellín, compuesta por el sitio institucional multi-página Rueda Libre v2.0 y la landing page promocional de recorridos nocturnos Rueda Nocturna.

## 🌐 Enlaces Publicados (GitHub Pages)

-Index principal con todos los enlances: https://github.com/vane-amez/rueda-libre 
https://vane-amez.github.io/rueda-libre/

## 🗂️ Estructura y Páginas del Proyecto
`index.html` — Portada institucional con carrusel de campaña, servicios y flota destacada.
`paginas/tarifas.html` — Tabla responsiva de planes, horarios y tarifas de alquiler.
`paginas/reservas.html` — Formulario de reserva de bicicletas con validación visual y modal de políticas.
`nocturna/index.html` — Landing page *mobile-first* de la campaña **Rueda Nocturna** (rutas, planes, paso a paso e inscripción).
`nocturna/src/input.css` & `output.css` — Tema personalizado de marca (`@theme`), componentes reutilizables (`@apply`) y CSS minificado para producción.

## 🛠️ Tecnologías Utilizadas
-HTML5 Semántico: Estructura accesible (`<header>`, `<nav>`, `<main>`, `<section>`, `<article>`, `<fieldset>`, `<legend>`, `<footer>`).
-Bootstrap 5.3 & Bootstrap Icons: Sistema de grillas, carrusel, modal y personalización mediante variables CSS (`--bs-*`) en el sitio v2.0.
-Tailwind CSS v4 (CLI): Arquitectura *utility-first*, tokens de diseño en `@theme`, variante `dark:` manual y compilación optimizada (`--minify`) en la landing.
-JavaScript (ES6+): Control de menú móvil accesible, alternancia de modo claro/oscuro con persistencia en `localStorage` y validación nativa de formularios.

## ⚖️ Decisión Técnica: Bootstrap 5.3 vs. Tailwind CSS v4
Tras construir y medir ambos productos bajo la misma identidad visual de Rueda Libre, se evaluaron cuatro criterios clave:

| Criterio | Bootstrap 5.3 (Sitio v2.0) | Tailwind CSS v4 (Landing Nocturna) |
| :------- | :------------------------- | :--------------------------------- |
| **Curva de aprendizaje** | Rápida para componentes estándar; requiere mayor esfuerzo al sobrescribir estilos base. | Moderada al inicio; muy ágil y predecible una vez dominado el sistema de utilidades. |
| **Personalización** | Limitada a sobrescritura de variables (`--bs-*`) y hojas CSS adicionales. | Total y nativa mediante `@theme`, sin conflictos de especificidad ni `!important`. |
| **Tamaño final (Network)** | ~51.9 KB totales (~22.4 KB CSS + ~29.5 KB JS obligatorio). | ~51 KB en disco (~12 KB de CSS puro purificado con `--minify`, 0 KB de JS obligatorio). |
| **Casos de uso** | Prototipos rápidos, paneles administrativos y estructuras estándar. | Landings de marca, diseños a medida, soporte nativo de modo oscuro y alto rendimiento. |

-Recomendación para Rueda Libre: Adoptar Tailwind CSS v4 como estándar para la próxima versión integral del sitio. Permite mantener los colores y tipografías exactos de la marca (`#1E7A4F`, `#F39A2B`, `#14213D`, `#FAF6EF`, `#FFD166`), elimina dependencias obligatorias de JavaScript para la interfaz y reduce el peso transferido en red.

## 📸 Capturas del Producto
Vista Escritorio (1280 px) | [Escritorio](./img/captura-escritorio.png)
Vista Celular (360 px) | Modo Oscuro (Rueda Nocturna) | [Celular](./img/captura-movil.png) 

## 💡 Principales Aprendizajes
1. Arquitectura Mobile-First y Layout: Uso combinado de Flexbox para alineaciones unidimensionales (headers, footers y anclaje inferior de botones en tarjetas) y CSS Grid para cuadrículas simétricas responsivas.
2. Accesibilidad y Contraste: Implementación de etiquetas asociadas, validación nativa sin depender de librerías pesadas, navegación completa por teclado (`Tab` / `Esc`) y cumplimiento de contraste WCAG AA/AAA en modo claro y oscuro.
3. Optimización de Producción: Comprensión del rastreo estático de Tailwind CLI (`--minify`) frente a frameworks tradicionales de componentes.

## 👩‍💻 Autora
Desarrollado por Vanessa Palacio Amezquita — Proyecto *Rueda Libre* (Nodo Digital, 2026).