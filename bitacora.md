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