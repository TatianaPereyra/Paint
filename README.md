# TPE 2 - Paint y Filtros de Imagen

## Descripción

Se desarrolló una aplicación tipo Paint que permite dibujar sobre un lienzo, cargar imágenes y aplicar distintos filtros de procesamiento.

Para ello se utilizó la etiqueta `<canvas>` de HTML5 junto con JavaScript para la manipulación de píxeles, la implementación de herramientas de dibujo y la aplicación de filtros sobre las imágenes.

## Demo

 [GitHub Pages](URL_DEL_DEPLOY)

## Capturas

![Pantalla principal](img/screenshot.png)

## Tecnologías utilizadas

- HTML5
- CSS3
- JavaScript 
- Canvas

## Implementación

Algunos aspectos relevantes de la implementación fueron los siguientes:

Se trabajó utilizando clases y objetos para representar las diferentes herramientas y filtros de la aplicación. Además, se diseñaron dos controladores independientes: uno encargado de gestionar los eventos de las herramientas de dibujo (lápiz y goma) y otro responsable de la carga de imágenes y la aplicación de filtros. Esta separación permitió mantener las responsabilidades bien definidas y evitar concentrar toda la lógica en `Main.js`.

Para la implementación de filtros basados en convolución se desarrolló una clase genérica (`ConvolutionFilter.js`) cuyo constructor recibe el kernel correspondiente. Complementariamente, se creó el archivo `kernels.js`, encargado de almacenar un diccionario con los distintos kernels disponibles y sus filtros asociados.

De esta manera, el controlador puede instanciar dinámicamente el filtro adecuado según la opción seleccionada por el usuario. Este enfoque facilita la incorporación de nuevos filtros basados en kernels sin necesidad de crear nuevas clases específicas.

## Uso

La aplicación permite cargar una imagen mediante el botón de selección de archivos y descargar posteriormente el resultado obtenido.

Sobre la imagen cargada se pueden aplicar los siguientes filtros:

- Escala de grises
- Sepia
- Brillo (con control de intensidad)
- Blanco y negro
- Negativo
- Blur
- Saturación (con control de intensidad)
- Detección de bordes
- Sharpen
- Bajorrelieve

> Los filtros no son acumulativos. Cada filtro se aplica sobre la imagen original cargada.

Además, el usuario dispone de herramientas de dibujo como lápiz y goma. En el caso del lápiz, es posible seleccionar el color de trazo y, para ambas herramientas, ajustar el grosor.

## Limitaciones

Al cargar una imagen, esta se adapta automáticamente al tamaño del lienzo. Dependiendo de sus dimensiones originales, puede producirse cierta deformación debido al escalado.

## Pruebas

Para verificar el funcionamiento de la aplicación se utilizó la imagen `prueba.jpeg`, disponible dentro de la carpeta `img`.

## Bibliografía

Durante el desarrollo del proyecto se consultaron los siguientes artículos y recursos:

- **Kernel (Image Processing):** explicación del funcionamiento de los kernels utilizados para el procesamiento de imágenes.  
  https://en.wikipedia.org/wiki/Kernel_(image_processing)

- **Image Kernels:** explicación visual e interactiva de distintos kernels y sus efectos.  
  https://setosa.io/ev/image-kernels/

- **Códigos de color HTML:** descripción de los distintos modelos de color soportados por HTML y sus características.  
  https://docs.aspose.com/html/es/net/tutorial/html-colors

- **Colorfulness:** definición de conceptos relacionados con el color, como saturación y chroma.  
  https://en.wikipedia.org/wiki/Colorfulness

- **HSL and HSV:** explicación de los modelos HSL y HSV y su relación con RGB. Las fórmulas utilizadas para el filtro de saturación fueron obtenidas de este recurso.  
  https://en.wikipedia.org/wiki/HSL_and_HSV
