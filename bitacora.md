1.  URL completa: http://127.0.0.1:5500/index.html 
    protocolo: http://
    host:127.0.0.1:5500
    puerto: Highest
    ruta: /index.html
    método de la petición:
    código de estado: 200 OK

Se agrega en la barra de direciones /alquileres
Aparece: "No se ha podido acceder al archivo" Es posible que se haya movido, editado o eliminado.
ERR_FILE_NOT_FOUND
Significa que el navegador no puede encontrar esa dirección URL.

2.  Rol HTML: Me dará la estructura de la escritura, titulos, subtitulos, parrafos, listas, etiquetas.  
    Rol CSS: Me dará el código de la parte visual, los colores de fondo, de las letras, hover (style).
    Rol JavaScript: Se pondran establecer los párametros de login, ingreso de información en la página creada.

3. Tabla de rutas relativas del trabajo
--------------------------------------------------
Origen              | Destino             | Ruta escrita
--------------------|---------------------|----------------------
index.html          | paginas/tarifas.html| paginas/tarifas.html
index.html          | paginas/reservas.html| paginas/reservas.html
paginas/tarifas.html| index.html          | ../index.html
paginas/tarifas.html| paginas/reservas.html| reservas.html
paginas/reservas.html| index.html         | ../index.html
paginas/reservas.html| paginas/tarifas.html| tarifas.html

4. Deje la etiqueta <div> ya que me sirve como contenedor de los enlaces o etiquetas <a>.

5. Para la realización del formulario voy a explicar los siguientes 3:
type="radio" para que deje realizar la lista despegable en el formulario.
textarea para poder copiar un mensaje en comentarios.
type="number" para que el campo deje diligenciar números.

6. Campo        |   Prueba 
----------------|---------------------------------------------------
Nombre          |   Al ingresar dos caracteres me rechaza la información y que aumente los caracteres.
Documento	    |   Al ingresar cinco dígitos me rechaza la información y me solicita el número.
Correo	        |   Al ingresar un correo sin @ me solicita formato válido.
Celular	        |   Al ingresar un número que inicia por 2, no me deja registrar la información.
Fecha	        |   No me deja seleccionar una fecha diferente a las establecidas en el rango.
Tipo de bicicleta|  Al intentar enviar sin seleccionar una opción me solicita escogr una opción.
Plan	        |   Al intentar enviar sin seleccionar una opción me solicita escogr una opción.
Cantidad	    |   Al ingresar 0 bicicletas me requiere seleccionar la cantidad.
Comentarios	    |   Al intentar escribir más de 300 caracteres no me deja copiar más.
Políticas	    |   Al enviar sin aceptarlas se ve un mensaje de que debo aceptarlo para poder continuar.

7. Se elimina el stylo en el body y se llama en el archivo css, se incluyen las paletas de colores.

8. Realizó la inspección de los estilos utilizando las DevTools:
Propiedad que se hereda: font-family - Se comprobó que los párrafos reciben la tipografía Open Sans definida en el selector body.
Propiedad que no se hereda: background-color - Se verificó que el color de fondo crema aplicado al body no se transmite automáticamente a los párrafos, debido a que esta propiedad no se hereda por defecto en CSS.

9. Durante la revisión de los estilos se identificó un conflicto entre los selectores #menu a y .activo: Al inspeccionar el enlace mediante las herramientas DevTools, se evidenció que la propiedad color definida en .activo aparecía tachada, debido a que el selector #menu a tenía mayor especificidad.
Para resolver el conflicto se implementó el selector #menu a.activo, aumentando su especificidad sin utilizar !important ni estilos en línea.

10. Se realizó una prueba con DevTools sobre el elemento .tarjeta-servicio.
Al mantener activa la propiedad box-sizing: border-box, se obtuvo un ancho exterior de 206 px. Posteriormente, al desactivar temporalmente esta propiedad, el ancho aumentó a 240 px.
Se evidenció una diferencia de 34 px, correspondiente al espacio adicional generado por el padding y los bordes al utilizar el modelo content-box.

11. Minireto 12: Implementación de posicionamiento relativo, absoluto y fijo; incorporación de la etiqueta «Nuevo» y acceso flotante a WhatsApp; consolidación de estilos y publicación de la versión 1.0.

12. Minireto 01 semana 2 - Un encabezado que se acomada: Flexbox: Se implementó el modelo de distribución flexible Flexbox en la hoja de estilos CSS compartida por las tres páginas del sitio Rueda Libre.

13. Minireto 02 semana 2 - La flota en cuadrícula: Grid: Se realizaron pruebas mediante el modo dispositivo de DevTools en tres resoluciones: 1280 px, 900 px y 500 px. Se evidenció una distribución de cuatro, tres y una columna, respectivamente. Se comprobó que la cuadrícula reorganiza automáticamente las tarjetas de acuerdo con el ancho disponible, sin requerir modificaciones en CSS.

14. Minireto 03 semana 2 - Layout en dos dimensiones: Utilice flexbox en la portada porque necesitabas alinear dos elementos (organización horizontal) y Layout - Grid en reservas porque necesitabas distribuir dos áreas de contenido(1 era el formulario y la otra era el contacto.)

15. Minireto 04 semana 2 - mobile-first para que el sitio funcione en móvil, tablet y escritorio: En la inspección de la página se observa que no se desborda las tablas, auqnue se observa en algunas que no se corren verticalmente, sino que se quedan horizontalmente y se alargan en tipo de pantalla para celular, lo mismo paso con el formulario y contacto que tienen layaout. Para corregir esto se cambio grid-template-columns: 2fr; a una sola/grid-template-columns: 1fr.
En tarifas y rutas, las tablas quedan por fuera del contenedor igual que el boton del WhatsApp, no se adaptan a la versión del celular, se añade regla responsiva con overflow-x: auto en pantallas menores a 768 px.

16. Minireto 05 semana 2 - Prueba con Bootstrap: 
Tiempo invertido: 20 minutos.
Cantidad de código (CSS propio vs. Bootstrap):**
- Versión CSS propio: 35 líneas dedicadas exclusivamente a la distribución y presentación de la flota (`.cuadricula-flota` con Grid `auto-fit`, `.tarjeta-flota` con Flexbox, alturas de imagen y alineación del botón), sumadas a las reglas heredadas de `.tarjeta-servicio` y `.boton-reservar`.
- Versión Bootstrap 5.3: 0 líneas de CSS escrito. Toda la distribución se resolvió directamente en el HTML utilizando 6 clases del sistema de grillas (`container`, `row`, `g-4`, `col-12`, `col-sm-6`, `col-lg-4`, `col-xl-3`) más clases utilitarias de tarjeta (`card`, `h-100`).
-¿Qué me dio Bootstrap sin esfuerzo?: Breakpoints responsivos exactos (1, 2, 3 y 4 columnas) sin escribir `@media` queries.
Espaciado uniforme (*gutters* horizontales y verticales con `g-4`) y tarjetas de igual altura (`h-100`) alineadas automáticamente.
Imágenes adaptables al ancho de la tarjeta (`card-img-top`) y resets tipográficos limpios desde el primer momento.
- ¿Qué control perdí?: Identidad visual de marca:** Se perdieron nuestra paleta de colores personalizada (`--color-azul`, `--color-verde`, `--color-crema`, `--color-naranja`) y nuestras tipografías (`Montserrat` y `Open Sans`), adoptando los tonos y fuentes genéricos de Bootstrap.
Alturas de imagen fijas: En CSS propio teníamos `height: 180px; object-fit: cover;` para recortar todas las fotos al mismo alto exacto; sin CSS adicional en Bootstrap, las imágenes conservan su proporción original y pueden variar ligeramente de altura si las fotos tienen dimensiones distintas.

17. Minireto 06 semana 2 - utilidades: 
-`d-none d-md-block` (Display utilities): Permite controlar la visibilidad responsiva de un elemento. Oculta por defecto el elemento en pantallas móviles (`d-none`) y lo muestra como bloque (`d-block`) únicamente a partir del breakpoint mediano `md` (≥768px). Se utilizó para el elemento decorativo de la franja final.
-`flex-column flex-md-row` (Flexbox direction): Modifica la dirección del flujo de los elementos flexibles según el ancho de pantalla. Apila los elementos en columna de forma vertical en celulares (`flex-column`) y los reorganiza en una línea horizontal a partir del breakpoint `md` (`flex-md-row`).
-`gap-4` (Flexbox / Grid gap): Define un espacio de separación uniforme y estandarizado (equivalente a `1.5rem`) entre los elementos hijos directos de un contenedor flexible (`d-flex`) o de grilla, evitando la necesidad de aplicar márgenes manuales.
-`text-bg-dark` (Color and background): Aplica simultáneamente un color de fondo oscuro corporativo o temático (`dark`) y ajusta automáticamente el color del texto a claro para garantizar el contraste adecuado y la accesibilidad web.
-`rounded-4` (Borders / Border-radius): Modifica el radio de las esquinas del contenedor aplicando un borde redondeado amplio y moderno (equivalente a `1rem`), dándole un acabado visual estilizado a la franja principal sin escribir reglas en CSS.

18. Minireto 07 semana 2 - Migración del Index con Bootstrap:
-Conflicto 1: Tamaños y pesos de los encabezados (`h1`, `h2`, `h3`).
Diagnóstico con DevTools: Bootstrap aplica un sistema tipográfico estricto basado en tamaños relativos fijos (`rem`) a nivel global para las etiquetas HTML, lo que anulaba el estilo de los selectores base.
Solución: Se resolvieron aplicando de forma explícita clases utilitarias de Bootstrap directamente en el marcado HTML donde se requería control estricto (como `fw-bold`, `text-center`, `fs-5`), permitiendo coexistir las fuentes globales de marca cargadas en el head ,con la jerarquía visual del framework sin usar `!important`.

-Conflicto 2: Comportamiento de los enlaces (`<a>`) y colores heredados.
Diagnóstico con DevTools: Las reglas globales de Bootstrap para los enlaces (`color: var(--bs-link-color)`) sobreescribían el color verde corporativo que teníamos configurado en nuestros estilos generales para la etiqueta.Solución: Se respetó la cascada cargando `styles.css` después de Bootstrap y se utilizaron clases utilitarias de texto específicas de Bootstrap en los elementos críticos (como `text-success` en los precios y botones) para asegurar la identidad visual sin romper los enlaces predeterminados del menú.

-Conflicto 3: Márgenes automáticos y espaciados (*gutters*) en contenedores principales.
Diagnóstico con DevTools:* Los estilos de la clase `.container` de Bootstrap y nuestros márgenes de sección personalizados competían por el espacio, generando saltos de línea indeseados en pantallas medianas al usar simultáneamente contenedores flex antiguos y la nueva grilla `row g-4`.
Solución:* Se eliminaron del archivo `styles.css` las reglas obsoletas de `.portada` y `.galeria-rutas`, delegando toda la distribución espacial y separación de columnas exclusivamente a las clases de utilidad de Bootstrap.

19. Minireto 08 semana 2 - migración completa a Bootstrap:
-Tiempo invertido en el rediseño y migración: Versión inicial en CSS puro (Flexbox/Grid manual): ~6 horas de desarrollo, pruebas de media queries y ajuste de desbordamientos en tablas y formularios.
Migración y refactorización a Bootstrap 5.3: ~2 horas (aprovechando componentes nativos y grillas predefinidas).

-Reducción de líneas de código:
 CSS styles: ~350 líneas de código (incluyendo layouts de grillas complejas, media queries para diferentes dispositivos, posicionamientos y clases de tarjetas manuales).
 Con Bootstrap: ~110 líneas de código. El archivo ahora se limita exclusivamente a la capa de identidad visual, variables de marca, tipografías y bordes/tablas personalizadas.

-Ventajas:
Adaptabilidad inmediata (*responsiveness*) sin necesidad de escribir media queries personalizadas.
Menor costo de mantenimiento técnico gracias al uso de clases utilitarias estandarizadas (`g-4`, `col-12`, `d-flex`).
Formularios y tablas limpios, con accesibilidad integrada por defecto.

 -Desventajas:
Curva inicial para adaptar los selectores globales de tipografía y colores de marca (`--color-verde`, `--color-azul`) sin que colisionen con las clases nativas de Bootstrap.

-Conclusión:¿Bootstrap realmente redujo el trabajo? 
R// Sí, la adopción del framework redujo drásticamente el código CSS personalizado, eliminó los errores comunes de desbordamiento horizontal en móviles y aceleró la maquetación de nuevas secciones, permitiendo enfocar los esfuerzos en la experiencia del usuario y la identidad de marca de Rueda Libre.

20. Minireto 09 semana 2 - organización navbar y botones: el navbar ya lo habi migrado, reviso los botones y realizo las pruebas. 

21. Minireto 10 semana 2 - card y carousel sobre la grilla existente: En la página principal index, se añadió un componente carrusel de Bootstrap (carousel, carousel-inner, carousel-item) configurado con un intervalo de rotación automática (data-bs-ride="carousel"), las cartas en la sección de alquiler de bicicletas, nuestras rutas y por que Rueda libre, ya se tenian implementadas.

22. Minireto 11 semana 2 - validación visual, alerta y modal:
--Alerta superior: Se agregó una franja de advertencia en la parte alta del formulario para recordarle al usuario que debe llevar su documento de identidad original.   
-Validación visual con Bootstrap: Se configuró el formulario con novalidate y el script oficial para que, si el usuario intenta enviar datos vacíos o incorrectos, aparezcan mensajes de error claros y específicos debajo de cada campo obligatorio.   
-Modal de políticas: Se creó una ventana emergente que se abre con un botón al lado de la casilla de aceptación. Muestra las 5 políticas de alquiler en una lista y se puede cerrar con el mouse (clic en la "X" o en "Entendido") o presionando la tecla Esc.

23. Minireto 12 semana 2 - Rueda Libre v2.0 con identidad propia:
-Identidad visual aplicada: Se sobrescribieron las variables globales de Bootstrap en root y las variables de componente de botón para integrar el Verde Ruta, el Azul Profundo y el fondo Crema, junto con la variante propia btn-naranja.

-Clases propias e íconos: Se crearon e integraron tres clases complementarias (`.hero-rueda-libre`, `.titulo-seccion-marca` y `.footer-marca`) respetando la cascada sin usar `!important` ni modificar el archivo de Bootstrap. 
Se incorporaron íconos de Bootstrap Icons en la barra de navegación, beneficios, datos de contacto y botón flotante de WhatsApp con atributos `aria-hidden="true"` y `aria-label` para accesibilidad.

-Pruebas finales (v2.0): Se verificó la adaptabilidad en móvil (375 px), tablet (768 px) y escritorio (1280 px), la navegación completa con teclado (`Tab` y `Esc` en el modal) y el cumplimiento del ratio de contraste mínimo de 4.5:1 en textos, botones y pie de página.
  - Antes (Bootstrap por defecto): `./img/antes-rueda-libre.PNG`
  - Después (Personalización v2.0): `./img/despues-rueda-libre.PNG`

24. Minireto 01 semana 3: Prototipo nocturno con Play CDN:
-Construcción del botón en Semana 2 (Bootstrap 5.3):
  En `index.html` y `paginas/reservas.html` utilizamos clases semánticas de componente predefinidas como `class="btn btn-primary fw-bold px-4 py-2 shadow-sm"` o nuestra variante personalizada `class="btn btn-naranja fw-bold px-4 py-2 shadow-sm"`. La clase base `.btn` ya traía encapsulado el `display: inline-block`, el relleno interno (`padding`), los bordes redondeados y las transiciones, y para darle la identidad naranja de Rueda Libre tuvimos que crear una clase adicional en `styles.css` sobrescribiendo las variables internas del componente (`--bs-btn-bg`, `--bs-btn-border-color`, `--bs-btn-hover-bg`).

-Construcción del botón hoy (Tailwind CSS):
  En `nocturna/prototipo.html` construimos el enlace `"Inscríbete"` partiendo desde cero sin ninguna clase de componente ni CSS propio, combinando exclusivamente utilidades atómicas de un solo propósito directamente en el HTML:
  `class="inline-block bg-emerald-600 hover:bg-emerald-500 text-white text-base font-bold uppercase tracking-wide px-8 py-4 rounded-xl shadow-lg"`.
  Cada propiedad visual (el comportamiento de bloque en línea, el color de fondo, el cambio al pasar el cursor, el grosor tipográfico, el espaciado horizontal/vertical y el radio del borde) se declaró de forma explícita.

-Diferencia clave entre un framework de componentes y uno utility-first:
  Un framework de componentes (como Bootstrap) entrega piezas de interfaz ya diseñadas, que aceleran el armado estándar, pero obligan a pelear contra sus estilos base o sobrescribir variables en una hoja CSS externa cuando se busca un diseño a medida. En cambio, un framework utility-first (como Tailwind CSS) no impone componentes prediseñados; ofrece bloques de construcción de bajo nivel (utilidades) que permiten diseñar interfaces totalmente personalizadas directamente en el HTML sin escribir CSS adicional ni sufrir conflictos de especificidad.

25. Minireto 02 semana 3 - Tailwind con la CLI y botones: 
-Clase utilizada (`bg-emerald-600`): Aparece compilada en el archivo `output.css` junto con sus reglas CSS traducidas, ya que la CLI escanea el código HTML para inyectar únicamente las reglas que se están implementando.
-Clase no utilizada (`bg-pink-500`): No aparece registrada en absoluto dentro de `output.css`. 
¿Por qué ocurre?: A diferencia del Play CDN (que descarga e interpreta todo el motor de Tailwind de forma dinámica en el navegador), la CLI funciona bajo un sistema de rastreo estático (*jit* / *on-demand*). Lee los archivos fuente y descarta de forma inteligente todas las clases inútiles o no declaradas en el marcado, generando un archivo CSS final extremadamente ligero y optimizado para producción.

26. Minireto 03 semana 3 - cards de rutas nocturnas: Se crean 3 tarjetas en organización vertical con los botones y utilidades.

27. Minireto 04 semana 3 - Kit de componentes Rueda Nocturna v0.1:
Para garantizar consistencia visual entre todos los elementos de la campaña, se definieron y aplicaron las siguientes reglas de diseño con utilidades de Tailwind CSS:

-Paleta de colores unificada:
Superficies oscuras (modo nocturno):* `bg-slate-950` para el fondo general y campos de entrada (`input`), `bg-slate-900` para contenedores principales y cards, y `border-slate-800` / `border-slate-700` para delimitaciones sutiles.
Acentos de marca y estados:* `emerald-600` / `emerald-500` para acciones principales y foco activo (`focus:ring-emerald-400/50`), `amber-400` para etiquetas destacadas, precios y advertencias, y `sky-400` para mensajes informativos.
Jerarquía tipográfica de texto:* `text-white` para encabezados (`h1`–`h3`), `text-slate-100` / `text-slate-300` para lectura general y `text-slate-400` para etiquetas secundarias y textos de ayuda.

-Radios de borde consistentes:
`rounded-3xl` para contenedores mayores y cards completas.
`rounded-xl` para elementos interactivos y bloques internos (botones, inputs y alertas).
`rounded-full` exclusivamente para insignias o etiquetas tipo píldora (badges).

-Escala de espaciado y foco:
Relleno interno estandarizado en `p-6` / `p-8` para cajas y alertas, `px-4 py-3.5` para inputs, y `px-6` a `px-8` con `py-3.5` a `py-4` para botones.
Separación vertical rítmica mediante `space-y-2` (campos de formulario), `space-y-4` / `space-y-6` (bloques internos) y `space-y-16` (secciones principales).
Accesibilidad uniforme por teclado: todos los botones e inputs reemplazan el contorno nativo (`focus:outline-none`) por un anillo visible de 4 px (`focus:ring-4`).