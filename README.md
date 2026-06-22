# Réplica de la Página de Apple

Este proyecto es una práctica donde repliqué la página principal de Apple utilizando HTML y CSS nativo, sin usar frameworks como Bootstrap ni librerías externas. El objetivo principal era lograr ese diseño limpio y ordenado que tiene la marca, cuidando los espacios y haciendo que la página se adapte bien tanto en computadoras como en celulares.

## Secciones replicadas
Logré armar las partes más importantes de la página de referencia:
- La barra de navegación de arriba (que se queda fija al bajar y tiene el efecto borroso transparente).
- El bloque principal oscuro (la sección de la WWDC).
- Las dos secciones grandes de productos (el iPhone y la MacBook Air).
- La cuadrícula de abajo donde vienen los 6 productos secundarios (Macbook Neo, watch series 11, AirPods y MacBook pro, iPad ProS).
- La sección de Apple TV+ (maquetada de forma fija simulando el carrusel).
- Todo el pie de página con las notas legales y las columnas de enlaces.

## Cómo organicé la estructura (HTML Semántico)

Para mantener el código limpio y evitar una acumulación de divs repetidos, utilicé las etiquetas correspondientes para darle un sentido semántico a la estructura. Todo lo relacionado con la navegación lo agrupé dentro de <header> y <nav>, mientras que el contenido principal y fuerte de la página quedó dentro de <main>. Para separar de forma ordenada los productos y las tarjetas de la cuadrícula utilicé <section> y <article>, y finalmente cerré el pie de página con los links usando la etiqueta <footer>.

## Propiedades de CSS utilizadas
En cuanto a las propiedades de CSS, apliqué un reset general usando box-sizing: border-box para controlar mejor el modelo de caja, asegurando que los márgenes y rellenos no alteraran el tamaño real de los bloques. Para darle el toque característico de la web de Apple a la barra de navegación, utilicé backdrop-filter: blur, que genera ese efecto translúcido y borroso con el fondo al momento de hacer scroll. Finalmente, agregué la propiedad transition tanto en los botones como en los enlaces para que, al pasar el mouse por encima, los cambios de color se noten suaves e interactivos en lugar de saltar de golpe.

## Uso de Flexbox
Para organizar los elementos del sitio utilicé Flexbox principalmente al momento de alinear elementos en una sola dirección o centrar textos. En el menú superior me sirvió para acomodar el logo a la izquierda, los enlaces al centro y el buscador a la derecha usando justify-content: space-between. También lo apliqué en los botones de "Más información" y "Comprar" para mantenerlos juntos con una separación exacta mediante la propiedad gap. Por último, dentro de las tarjetas de los productos me ayudó a ordenar los textos verticalmente con flex-direction: column para asegurarme de que todo quedara perfectamente centrado.

## Uso de CSS Grid
El sistema de Grid lo dejé exclusivo para las secciones que necesitaban organizarse en filas y columnas al mismo tiempo. Para la cuadrícula de productos en computadoras, utilicé grid-template-columns: repeat(2, 1fr) para acomodar las tarjetas de dos en dos de forma muy rápida. En el caso del footer, apliqué la propiedad repeat(auto-fit, minmax(180px, 1fr)), lo que funciona excelente tanto en pantallas grandes como en celulares, ya que permite que las columnas de enlaces se reacomoden solas hacia abajo según el ancho de la pantalla sin necesidad de forzarlas.

## Diseño Responsivo (Celulares)
Para asegurar que la página se adaptara correctamente tanto a computadoras como a pantallas más chicas, utilicé Media Queries apuntando a los 768px. Con esto logré ocultar la lista de enlaces del menú superior en celulares para evitar que se amontonara todo el contenido horizontalmente. También configuré la cuadrícula de productos para que cambie de dos columnas a una sola (1fr), logrando que las tarjetas se vean completas y cómodas de leer al deslizar hacia abajo. Por último, el footer se reorganiza bajo esta misma lógica, asegurando que los textos legales y los links no se salgan por los lados ni generen barras horizontales incómodas en los teléfonos.

## Dificultades que tuve durante el desarrollo

En cuanto a los problemas que encontré durante el desarrollo, un reto fue acomodar el footer. Al principio intenté armar las columnas con Flexbox, pero en pantallas medianas los textos se amontonaban de forma muy fea. Para solucionarlo, decidí cambiar la lógica de esa sección a CSS Grid utilizando columnas automáticas con auto-fit. Aunque al inicio me costó un poco entender cómo funcionaba esa propiedad, al final el código quedó mucho más limpio y los enlaces se reacomodan solos de forma fluida.

Otra dificultad surgió al dar formato a los botones de compra y de información. Apple utiliza dos variantes dependiendo del fondo de la sección: unos con fondo azul sólido y otros que son transparentes con borde azul. Como al principio los nombré de forma parecida en el CSS, cuando editaba el estilo de uno se me descomponía el otro. Tuve que tomarme el tiempo de ordenar el código, separar bien las clases en .btn-primary y .btn-secondary, y revisar detalladamente el HTML para asignar a cada uno la etiqueta que le correspondía.

Por último, adaptar las imágenes de fondo del iPhone y la laptop al ancho de la pantalla fue bastante complicado. No lograba hacer que se ajustaran bien sin que se cortaran partes importantes o se vieran estiradas. Después de varios intentos erróneos, lo solucioné combinando las propiedades background-size: cover y background-position, logrando que las fotos se centren y escalen correctamente sin importar el tamaño del monitor o teléfono.

## Origen de los recursos visuales
Para las imágenes del proyecto combiné dos métodos. En la mayoría de los casos las obtuve directamente del sitio oficial de Apple Latinoamérica haciendo clic derecho, seleccionando "Abrir imagen en una nueva pestaña" y guardándolas en mi computadora. Para el resto de los productos, busqué imágenes similares en internet que coincidieran con el diseño y las descargué para completar mi pagina.
