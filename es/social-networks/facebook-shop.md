---
title: "Facebook Shop - Manual del Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo Facebook Shop para PrestaShop de MyPresta.eu."
sidebar:
  label: "Facebook Shop - Manual del Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Facebook Shop en MyPresta.eu](https://mypresta.eu/modules/social-networks/facebook-shop.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/social-networks/facebook-shop/)
>
> ---


# Facebook Shop

## 1. Requisitos y Compatibilidad

- **Versiones de PrestaShop compatibles**: PrestaShop 1.4.x, 1.5.x, 1.6.x, 1.7.x
- **Compatibilidad con PHP**: PHP 5.6 - 8.5
- **Requisitos de alojamiento**: Extensiones PHP estándar (cURL, JSON, OpenSSL).
- **Página de fans de Facebook**: Debes tener una página de fans de Facebook activa (no un perfil personal) de la que seas administrador.
- **Certificado SSL**: Tu tienda PrestaShop debe tener un certificado SSL activo (HTTPS) para que Facebook Shop funcione correctamente, ya que Facebook requiere conexiones seguras para las aplicaciones incrustadas.

## 2. Recorrido Completo por la Configuración (Cada Ajuste Agrupado por Pantalla)

### 2.1 Página de Configuración del Módulo (Back Office > Módulos > Configurar)

Esta es la pantalla de configuración principal de tu módulo Facebook Shop. Encontrarás una serie de pestañas o secciones para personalizar cómo aparece y funciona tu tienda en Facebook.

#### Pestaña de Configuración General (o vista inicial similar)

- **Mostrar actualizaciones de MyPresta.eu:**

  - **Qué hace este ajuste:** Controla si ves notificaciones sobre actualizaciones de MyPresta.eu directamente en la configuración de tu módulo.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está activado:* Recibirás alertas de nuevas versiones o noticias importantes de MyPresta.eu, lo que te ayudará a mantener tu módulo actualizado.
    - *Cuando está desactivado:* No verás estas notificaciones, lo que podría significar que te pierdes actualizaciones importantes o correcciones de errores.
  - **Valor recomendado:** SÍ
  - **Escenario / ejemplo de comerciante:** Mantén esto activado para asegurarte de estar siempre al tanto de las últimas mejoras y parches de seguridad para tu módulo Facebook Shop.
- **Mostrar idioma de Facebook Shop:** (`faceshop_lang_disp`)

  - **Qué hace este ajuste:** Determina si el selector de idioma es visible en tu Facebook Shop.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está activado:* Los clientes pueden cambiar el idioma de tu Facebook Shop, útil para tiendas internacionales.
    - *Cuando está desactivado:* La tienda se mostrará en el idioma predeterminado, o en el idioma detectado por Facebook, sin un selector explícito.
  - **Valor recomendado:** SÍ (si tienes varios idiomas activados en PrestaShop)
  - **Escenario / ejemplo de comerciante:** Si vendes a clientes en diferentes países y has traducido tu tienda PrestaShop, activa esto para permitirles navegar en su idioma preferido.
- **Mostrar moneda de Facebook Shop:** (`faceshop_curr_disp`)

  - **Qué hace este ajuste:** Determina si el selector de moneda es visible en tu Facebook Shop.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está activado:* Los clientes pueden cambiar la moneda mostrada en tu Facebook Shop, útil para tiendas internacionales.
    - *Cuando está desactivado:* La tienda mostrará los precios en tu moneda predeterminada.
  - **Valor recomendado:** SÍ (si tienes varias monedas activadas en PrestaShop)
  - **Escenario / ejemplo de comerciante:** Si aceptas pagos en USD, EUR y GBP, activa esto para que los clientes puedan ver los precios en su moneda local.
- **Activar reescritura de módulo (URLs amigables para SEO):** (`faceshop_modrew`)

  - **Qué hace este ajuste:** Controla si el módulo utiliza URLs amigables para SEO dentro de Facebook Shop, similar a tu tienda principal de PrestaShop.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está activado:* Las URLs de productos y categorías dentro de Facebook Shop serán limpias y descriptivas (por ejemplo, `tutienda.com/producto/mi-producto-increible`). Esto es generalmente mejor para el SEO y la experiencia del usuario.
    - *Cuando está desactivado:* Las URLs podrían ser menos legibles (por ejemplo, `tutienda.com/index.php?id_product=123`).
  - **Valor recomendado:** SÍ
  - **Escenario / ejemplo de comerciante:** Activa esto siempre para una mejor visibilidad en los motores de búsqueda y un aspecto más profesional para los enlaces de tus productos compartidos desde Facebook.

#### Pestaña de Configuración de la Página de Inicio

- **Mostrar recuento de elementos en la página de inicio:** (`faceshop_homepage_itemcount`)

  - **Qué hace este ajuste:** Establece el número de productos a mostrar en la página de inicio de tu Facebook Shop.
  - **Efecto de cambiar este ajuste:**
    - *Cuando se establece en 10:* La página de inicio de tu Facebook Shop mostrará 10 productos.
    - *Cuando se establece en 20:* La página de inicio de tu Facebook Shop mostrará 20 productos.
  - **Valor recomendado:** 12-24 (suficiente para mostrar variedad sin abrumar la página).
  - **Escenario / ejemplo de comerciante:** Si quieres mostrar una amplia gama de productos inmediatamente, establece un número mayor. Si prefieres un aspecto más limpio con menos elementos y más prominentes, establece un número menor.
- **Mostrar productos con descuento en la página de inicio:** (`faceshop_homepage_disphot`)

  - **Qué hace este ajuste:** Controla si los productos con descuento (en oferta) se muestran en la página de inicio de tu Facebook Shop.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está activado:* Los productos actualmente en oferta se mostrarán de forma destacada, fomentando las compras impulsivas.
    - *Cuando está desactivado:* Solo los productos a precio regular aparecerán en la página de inicio (a menos que otras opciones de visualización estén activadas).
  - **Valor recomendado:** SÍ
  - **Escenario / ejemplo de comerciante:** Utiliza esto para llamar la atención sobre tus promociones y liquidar inventario.
- **Mostrar productos nuevos en la página de inicio:** (`faceshop_homepage_dispnew`)

  - **Qué hace este ajuste:** Controla si tus productos más nuevos se muestran en la página de inicio de tu Facebook Shop.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está activado:* Los productos añadidos recientemente se mostrarán, manteniendo tu tienda fresca y emocionante para los visitantes que regresan.
    - *Cuando está desactivado:* Los productos nuevos no tendrán una sección dedicada en la página de inicio.
  - **Valor recomendado:** SÍ
  - **Escenario / ejemplo de comerciante:** Si añades artículos nuevos con frecuencia, esta es una excelente manera de destacarlos y fomentar las visitas repetidas.
- **Mostrar categoría raíz de la página de inicio:** (`faceshop_homepage_root`)

  - **Qué hace este ajuste:** Te permite seleccionar una categoría raíz específica para mostrar productos de ella en la página de inicio de tu Facebook Shop. Si se deja vacío, mostrará productos de tu categoría raíz predeterminada de PrestaShop.
  - **Efecto de cambiar este ajuste:**
    - *Cuando se selecciona una categoría específica:* Solo los productos de esa categoría y sus subcategorías aparecerán en la página de inicio.
    - *Cuando se deja vacío:* Los productos de la categoría raíz predeterminada de toda tu tienda se considerarán para la visualización en la página de inicio.
  - **Valor recomendado:** Dejar vacío a menos que tengas una estrategia de marketing específica.
  - **Escenario / ejemplo de comerciante:** Si estás ejecutando una campaña especial para la "Colección de Verano" y solo quieres esos productos en la página de inicio de tu Facebook Shop, seleccionarías la categoría "Colección de Verano" aquí.

#### Pestaña de Configuración de la Cabecera

- **Mostrar cabecera en Facebook Shop:** (`faceshop_header_disp`)
  - **Qué hace este ajuste:** Controla si la sección de la cabecera de tu tienda PrestaShop (logotipo, barra de búsqueda, resumen del carrito) es visible dentro de la tienda de Facebook incrustada.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está activado:* Tu Facebook Shop tendrá una cabecera familiar, haciéndola sentir más como tu tienda principal.
    - *Cuando está desactivado:* La cabecera estará oculta, proporcionando un aspecto más minimalista.
  - **Valor recomendado:** SÍ
  - **Escenario / ejemplo de comerciante:** Mantener la cabecera visible ayuda a mantener la coherencia de la marca y proporciona elementos de navegación esenciales como la barra de búsqueda.

#### Pestaña de Configuración de la Página de Categoría

- **Categoría raíz para Facebook Shop:** (`faceshop_cat_root`)

  - **Qué hace este ajuste:** Define la categoría principal desde la que tu Facebook Shop comenzará a mostrar productos y categorías. Esto actúa como la "raíz" para la navegación de tu Facebook Shop.
  - **Efecto de cambiar este ajuste:**
    - *Cuando se selecciona "Inicio" (raíz predeterminada de PrestaShop):* Todas las categorías y productos de toda tu tienda serán accesibles.
    - *Cuando se selecciona una categoría específica (por ejemplo, "Ropa"):* Solo "Ropa" y sus subcategorías/productos serán visibles en Facebook Shop.
  - **Valor recomendado:** "Inicio" (o la categoría raíz de tu tienda principal) a menos que quieras limitar el alcance de tu Facebook Shop.
  - **Escenario / ejemplo de comerciante:** Si solo quieres vender una línea específica de productos (por ejemplo, "Electrónica") en Facebook, lo establecerías en tu categoría "Electrónica".
- **Mostrar productos nuevos en las páginas de categoría:** (`faceshop_cat_dispnew`)

  - **Qué hace este ajuste:** Controla si los productos nuevos se resaltan o tienen una sección dedicada en las páginas de listado de categorías dentro de tu Facebook Shop.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está activado:* Los clientes que naveguen por las categorías detectarán fácilmente los artículos añadidos recientemente.
    - *Cuando está desactivado:* Los productos nuevos simplemente aparecerán en el listado regular sin un énfasis especial.
  - **Valor recomendado:** SÍ
  - **Escenario / ejemplo de comerciante:** Ayuda a los clientes a descubrir tus últimas novedades incluso cuando están navegando por tipos de productos específicos.
- **Mostrar productos con descuento en las páginas de categoría:** (`faceshop_cat_disphot`)

  - **Qué hace este ajuste:** Controla si los productos con descuento se resaltan o tienen una sección dedicada en las páginas de listado de categorías dentro de tu Facebook Shop.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está activado:* Los clientes que naveguen por las categorías detectarán fácilmente los artículos en oferta.
    - *Cuando está desactivado:* Los productos con descuento simplemente aparecerán en el listado regular sin un énfasis especial.
  - **Valor recomendado:** SÍ
  - **Escenario / ejemplo de comerciante:** Fomenta las compras haciendo que los artículos en oferta sean más visibles dentro de las categorías relevantes.
- **Recuento de elementos por página de categoría:** (`faceshop_cat_itemcount`)

  - **Qué hace este ajuste:** Establece el número de productos a mostrar por página cuando los clientes navegan por las categorías en tu Facebook Shop.
  - **Efecto de cambiar este ajuste:**
    - *Cuando se establece en 12:* Cada página de categoría mostrará 12 productos antes de la paginación.
    - *Cuando se establece en 30:* Cada página de categoría mostrará 30 productos.
  - **Valor recomendado:** 12-24 (estándar para la mayoría de los sitios de comercio electrónico).
  - **Escenario / ejemplo de comerciante:** Un número mayor reduce los clics pero puede hacer que las páginas se carguen más lentamente. Un número menor requiere más clics pero puede sentirse menos abrumador.
- **Estilo de visualización de categoría:** (`faceshop_cat_dispstyle`)

  - **Qué hace este ajuste:** Determina cómo se presentan las categorías en Facebook Shop.
  - **Efecto de cambiar este ajuste:**
    - *Opción A (por ejemplo, "Vista de cuadrícula"):* Las categorías se muestran como una cuadrícula de imágenes/nombres.
    - *Opción B (por ejemplo, "Vista de lista"):* Las categorías se muestran como una lista vertical.
  - **Valor recomendado:** Vista de cuadrícula (a menudo más atractiva visualmente).
  - **Escenario / ejemplo de comerciante:** Elige el estilo que mejor se adapte a la estética de tu marca y a cómo quieres que los clientes naveguen por tu gama de productos.

#### Pestaña de Configuración del Slider

- **Mostrar Slider en Facebook Shop:** (`faceshop_slider_disp`)

  - **Qué hace este ajuste:** Controla si se muestra un slider de imágenes (carrusel) en tu Facebook Shop. Este slider suele mostrar productos destacados, promociones o banners.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está activado:* Aparecerá un banner giratorio o un slider de productos, llamando la atención.
    - *Cuando está desactivado:* No se mostrará ningún slider, lo que resultará en un diseño estático.
  - **Valor recomendado:** SÍ (si tienes imágenes atractivas para un slider).
  - **Escenario / ejemplo de comerciante:** Utiliza el slider para destacar tu última colección, ventas de temporada o artículos más vendidos justo en la parte superior de tu Facebook Shop.
- **Tiempo de transición del Slider (en milisegundos):** (`faceshop_slider_time`)

  - **Qué hace este ajuste:** Establece cuánto tiempo permanece visible cada diapositiva antes de pasar a la siguiente.
  - **Efecto de cambiar este ajuste:**
    - *Cuando se establece en 3000 (3 segundos):* Las diapositivas cambiarán cada 3 segundos.
    - *Cuando se establece en 5000 (5 segundos):* Las diapositivas cambiarán cada 5 segundos.
  - **Valor recomendado:** 4000-6000 (4-6 segundos) para permitir a los usuarios tiempo suficiente para leer.
  - **Escenario / ejemplo de comerciante:** Ajusta esto en función de la cantidad de información en tus diapositivas. Tiempos más cortos para diapositivas solo con imágenes, más largos para diapositivas con texto.
- **Ubicación del Slider:** (`faceshop_slider_place`)

  - **Qué hace este ajuste:** Determina dónde aparece el slider dentro de tu Facebook Shop (por ejemplo, en la parte superior de la página, debajo de las categorías).
  - **Efecto de cambiar este ajuste:**
    - *Cuando se establece en "Superior":* El slider será lo primero que vean los clientes.
    - *Cuando se establece en "Debajo de los productos":* El slider aparecerá más abajo en la página.
  - **Valor recomendado:** Superior (para máxima visibilidad).
  - **Escenario / ejemplo de comerciante:** Coloca el slider en la parte superior para captar inmediatamente la atención con tus promociones más importantes.

#### Pestaña de Configuración del Menú

- **Mostrar enlace de productos nuevos en el menú:** (`faceshop_menu_newproducts`)

  - **Qué hace este ajuste:** Añade un enlace a "Productos nuevos" en el menú de navegación de tu Facebook Shop.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está activado:* Los clientes pueden hacer clic fácilmente para ver todas tus últimas incorporaciones.
    - *Cuando está desactivado:* Este enlace específico no aparecerá en el menú.
  - **Valor recomendado:** SÍ
  - **Escenario / ejemplo de comerciante:** Esencial para tiendas que actualizan con frecuencia su inventario para ayudar a los clientes a descubrir artículos nuevos.
- **Mostrar enlace de productos en oferta en el menú:** (`faceshop_menu_saleproducts`)

  - **Qué hace este ajuste:** Añade un enlace a "Productos en oferta" o "Descuentos" en el menú de navegación de tu Facebook Shop.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está activado:* Los clientes pueden encontrar rápidamente todos tus artículos con descuento.
    - *Cuando está desactivado:* Este enlace específico no aparecerá en el menú.
  - **Valor recomendado:** SÍ
  - **Escenario / ejemplo de comerciante:** Ideal para dirigir tráfico a tus promociones y aumentar las ventas.
- **Mostrar enlace de páginas de información en el menú:** (`faceshop_menu_informations`)

  - **Qué hace este ajuste:** Añade un enlace a tus páginas CMS (Información) de PrestaShop (por ejemplo, Quiénes somos, Entrega, Términos y condiciones) en el menú de navegación.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está activado:* Los clientes pueden acceder directamente a información importante no relacionada con productos.
    - *Cuando está desactivado:* Estos enlaces no aparecerán en el menú.
  - **Valor recomendado:** SÍ
  - **Escenario / ejemplo de comerciante:** Crucial para generar confianza y proporcionar la información necesaria de servicio al cliente.
- **Mostrar enlace de página de contacto en el menú:** (`faceshop_menu_contact`)

  - **Qué hace este ajuste:** Añade un enlace a tu página de Contacto de PrestaShop en el menú de navegación.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está activado:* Los clientes pueden encontrar fácilmente cómo ponerse en contacto contigo.
    - *Cuando está desactivado:* Este enlace específico no aparecerá en el menú.
  - **Valor recomendado:** SÍ
  - **Escenario / ejemplo de comerciante:** Proporciona un canal directo para las consultas de los clientes, mejorando el soporte.
- **Estilo de visualización de categoría del menú:** (`faceshop_menu_catstyle`)

  - **Qué hace este ajuste:** Determina cómo se muestran las categorías en el menú de navegación principal de tu Facebook Shop.
  - **Efecto de cambiar este ajuste:**
    - *Opción A (por ejemplo, "Desplegable"):* Las categorías aparecen en un menú desplegable.
    - *Opción B (por ejemplo, "Lista horizontal"):* Las categorías aparecen como una lista horizontal.
  - **Valor recomendado:** Desplegable (para muchas categorías) o Lista horizontal (para pocas categorías).
  - **Escenario / ejemplo de comerciante:** Si tienes muchas categorías de productos, un menú desplegable mantiene la navegación limpia. Si solo tienes unas pocas categorías principales, una lista horizontal podría ser más directa.
- **Mostrar enlace de fabricantes en el menú:** (`faceshop_menu_manuf`)

  - **Qué hace este ajuste:** Añade un enlace a tu página de Fabricantes de PrestaShop en el menú de navegación.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está activado:* Los clientes pueden navegar por productos por marca o fabricante.
    - *Cuando está desactivado:* Este enlace específico no aparecerá en el menú.
  - **Valor recomendado:** SÍ (si vendes productos de varias marcas distintas).
  - **Escenario / ejemplo de comerciante:** Si eres un revendedor de varias marcas, esto ayuda a los clientes a encontrar productos de sus fabricantes favoritos.

#### Pestaña de Configuración de la Página de Producto

- **Mostrar navegación de ruta de navegación:** (`faceshop_display_breadcrumb`)

  - **Qué hace este ajuste:** Controla si la navegación de "ruta de navegación" (por ejemplo, Inicio > Categoría > Subcategoría > Producto) se muestra en las páginas de producto.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está activado:* Ayuda a los clientes a comprender su ubicación dentro de la jerarquía de la tienda y a navegar fácilmente de vuelta a las categorías principales.
    - *Cuando está desactivado:* La ruta de navegación estará oculta.
  - **Valor recomendado:** SÍ
  - **Escenario / ejemplo de comerciante:** Mejora la experiencia del usuario al proporcionar rutas de navegación claras, especialmente para tiendas con estructuras de categorías profundas.
- **Recortar descripción del producto:** (`faceshop_pdisp_trim`)

  - **Qué hace este ajuste:** Si está activado, acortará las descripciones largas de los productos en la página del producto, mostrando a menudo un enlace "Leer más".
  - **Efecto de cambiar este ajuste:**
    - *Cuando está activado:* Las páginas de producto aparecen más limpias y los usuarios pueden optar por expandir la descripción si están interesados.
    - *Cuando está desactivado:* Las descripciones completas de los productos siempre se muestran, lo que puede hacer que las páginas sean muy largas.
  - **Valor recomendado:** SÍ (para productos con descripciones muy largas).
  - **Escenario / ejemplo de comerciante:** Evita que las páginas de producto sean excesivamente largas, especialmente en dispositivos móviles, mostrando primero un resumen conciso.
- **Mostrar precio del producto:** (`faceshop_pdisp_price`)

  - **Qué hace este ajuste:** Controla si el precio del producto es visible en las páginas de producto.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está activado:* El precio se mostrará claramente.
    - *Cuando está desactivado:* El precio estará oculto.
  - **Valor recomendado:** SÍ
  - **Escenario / ejemplo de comerciante:** Ocultar los precios generalmente no se recomienda para una tienda de comercio electrónico a menos que tengas una estrategia B2B específica que requiera presupuestos. Para la mayoría de los minoristas, los precios son esenciales.
- **Mostrar nombre del producto:** (`faceshop_pdisp_name`)

  - **Qué hace este ajuste:** Controla si el nombre del producto es visible en las páginas de producto.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está activado:* Se mostrará el nombre del producto.
    - *Cuando está desactivado:* El nombre del producto estará oculto.
  - **Valor recomendado:** SÍ
  - **Escenario / ejemplo de comerciante:** El nombre del producto es fundamental para la identificación; mantén esto siempre activado.
- **Mostrar imagen del producto:** (`faceshop_pdisp_image`)

  - **Qué hace este ajuste:** Controla si la imagen del producto es visible en las páginas de producto.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está activado:* Se mostrará la imagen principal del producto y las imágenes adicionales.
    - *Cuando está desactivado:* Las imágenes del producto estarán ocultas.
  - **Valor recomendado:** SÍ
  - **Escenario / ejemplo de comerciante:** Las imágenes de productos son cruciales para las ventas online; mantén esto siempre activado.

#### Pestaña de Configuración de Compartir en Redes Sociales

- **Mostrar botón de compartir en Facebook:** (`faceshop_social_facebook`)

  - **Qué hace este ajuste:** Añade un botón "Compartir" de Facebook a las páginas de producto dentro de tu Facebook Shop.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está activado:* Los clientes pueden compartir fácilmente productos con sus amigos de Facebook, aumentando el marketing viral.
    - *Cuando está desactivado:* El botón de compartir en Facebook no aparecerá.
  - **Valor recomendado:** SÍ
  - **Escenario / ejemplo de comerciante:** Anima a los clientes a difundir tus productos en sus propias líneas de tiempo.
- **Mostrar botón de compartir en Pinterest:** (`faceshop_social_pinterest`)

  - **Qué hace este ajuste:** Añade un botón "Pin It" de Pinterest a las páginas de producto dentro de tu Facebook Shop.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está activado:* Los clientes pueden fijar fácilmente imágenes de productos en sus tableros de Pinterest, generando tráfico desde Pinterest.
    - *Cuando está desactivado:* El botón de compartir en Pinterest no aparecerá.
  - **Valor recomendado:** SÍ (especialmente si tus productos son visualmente atractivos).
  - **Escenario / ejemplo de comerciante:** Ideal para moda, decoración del hogar, manualidades y otros productos visuales para aprovechar la audiencia de Pinterest.
- **Mostrar botón de compartir en Google+:** (`faceshop_social_google`)

  - **Qué hace este ajuste:** Añade un botón de compartir en Google+ a las páginas de producto dentro de tu Facebook Shop.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está activado:* Los clientes pueden compartir productos en Google+.
    - *Cuando está desactivado:* El botón de compartir en Google+ no aparecerá.
  - **Valor recomendado:** NO (Google+ ha sido descontinuado).
  - **Escenario / ejemplo de comerciante:** Esta plataforma ya no está activa, por lo que mantenerla activada es innecesario.

#### Pestaña de Configuración del Pie de Página

- **Mostrar pie de página en Facebook Shop:** (`faceshop_footer_disp`)
  - **Qué hace este ajuste:** Controla si la sección del pie de página de tu tienda PrestaShop (derechos de autor, enlaces, iconos de pago) es visible dentro de la tienda de Facebook incrustada.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está activado:* Tu Facebook Shop tendrá un pie de página familiar, manteniendo la coherencia de la marca y proporcionando enlaces adicionales.
    - *Cuando está desactivado:* El pie de página estará oculto.
  - **Valor recomendado:** SÍ
  - **Escenario / ejemplo de comerciante:** El pie de página a menudo contiene enlaces legales importantes (política de privacidad, términos de servicio) e información de contacto, que es bueno mantener visible para la confianza y el cumplimiento.

### 2.2 Tabla de Referencia Rápida de Configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| **Configuración general** | Mostrar actualizaciones de MyPresta.eu | SÍ | Recibir notificaciones de actualización del módulo. |
| | Mostrar idioma de Facebook Shop (`faceshop_lang_disp`) | SÍ | Permitir a los clientes cambiar el idioma de la tienda. |
| | Mostrar moneda de Facebook Shop (`faceshop_curr_disp`) | SÍ | Permitir a los clientes cambiar la moneda de la tienda. |
| | Activar reescritura de módulo (URLs amigables para SEO) (`faceshop_modrew`) | SÍ | Usar URLs limpias y descriptivas para un mejor SEO y UX. |
| **Configuración de la página de inicio** | Mostrar recuento de elementos en la página de inicio (`faceshop_homepage_itemcount`) | 12-24 | Número de productos mostrados en la página de inicio. |
| | Mostrar productos con descuento en la página de inicio (`faceshop_homepage_disphot`) | SÍ | Destacar productos en oferta en la página de inicio. |
| | Mostrar productos nuevos en la página de inicio (`faceshop_homepage_dispnew`) | SÍ | Destacar novedades en la página de inicio. |
| | Mostrar categoría raíz de la página de inicio (`faceshop_homepage_root`) | Vacío (raíz predeterminada) | Seleccionar una categoría específica para los productos de la página de inicio. |
| **Configuración de la cabecera** | Mostrar cabecera en Facebook Shop (`faceshop_header_disp`) | SÍ | Mostrar la cabecera de tu tienda (logotipo, búsqueda, carrito). |
| **Configuración de la página de categoría** | Categoría raíz para Facebook Shop (`faceshop_cat_root`) | Inicio (raíz predeterminada) | Define la categoría inicial para Facebook Shop. |
| | Mostrar productos nuevos en las páginas de categoría (`faceshop_cat_dispnew`) | SÍ | Destacar productos nuevos dentro de las categorías. |
| | Mostrar productos con descuento en las páginas de categoría (`faceshop_cat_disphot`) | SÍ | Destacar productos en oferta dentro de las categorías. |
| | Recuento de elementos por página de categoría (`faceshop_cat_itemcount`) | 12-24 | Número de productos mostrados por página de categoría. |
| | Estilo de visualización de categoría (`faceshop_cat_dispstyle`) | Vista de cuadrícula | Cómo se presentan las categorías (cuadrícula/lista). |
| **Configuración del Slider** | Mostrar Slider en Facebook Shop (`faceshop_slider_disp`) | SÍ | Mostrar un slider de imágenes/productos. |
| | Tiempo de transición del Slider (en milisegundos) (`faceshop_slider_time`) | 4000-6000 | Velocidad de las transiciones de las diapositivas. |
| | Ubicación del Slider (`faceshop_slider_place`) | Superior | Posición del slider (por ejemplo, parte superior de la página). |
| **Configuración del menú** | Mostrar enlace de productos nuevos en el menú (`faceshop_menu_newproducts`) | SÍ | Añadir "Productos nuevos" al menú de navegación. |
| | Mostrar enlace de productos en oferta en el menú (`faceshop_menu_saleproducts`) | SÍ | Añadir "Productos en oferta" al menú de navegación. |
| | Mostrar enlace de páginas de información en el menú (`faceshop_menu_informations`) | SÍ | Añadir enlaces a páginas CMS (Quiénes somos, etc.). |
| | Mostrar enlace de página de contacto en el menú (`faceshop_menu_contact`) | SÍ | Añadir un enlace "Contacto". |
| | Estilo de visualización de categoría del menú (`faceshop_menu_catstyle`) | Desplegable | Cómo aparecen las categorías en el menú (desplegable/lista). |
| | Mostrar enlace de fabricantes en el menú (`faceshop_menu_manuf`) | SÍ | Añadir un enlace a fabricantes/marcas. |
| **Configuración de la página de producto** | Mostrar navegación de ruta de navegación (`faceshop_display_breadcrumb`) | SÍ | Mostrar ruta de navegación (Inicio > Categoría > Producto). |
| | Recortar descripción del producto (`faceshop_pdisp_trim`) | SÍ | Acortar descripciones largas de productos. |
| | Mostrar precio del producto (`faceshop_pdisp_price`) | SÍ | Mostrar precio del producto. |
| | Mostrar nombre del producto (`faceshop_pdisp_name`) | SÍ | Mostrar nombre del producto. |
| | Mostrar imagen del producto (`faceshop_pdisp_image`) | SÍ | Mostrar imágenes del producto. |
| **Configuración de compartir en redes sociales** | Mostrar botón de compartir en Facebook (`faceshop_social_facebook`) | SÍ | Permitir compartir en Facebook. |
| | Mostrar botón de compartir en Pinterest (`faceshop_social_pinterest`) | SÍ | Permitir compartir en Pinterest. |
| | Mostrar botón de compartir en Google+ (`faceshop_social_google`) | NO | Google+ está descontinuado. |
| **Configuración del pie de página** | Mostrar pie de página en Facebook Shop (`faceshop_footer_disp`) | SÍ | Mostrar el pie de página de tu tienda. |

## 3. Solución de Problemas del Comerciante y Preguntas Frecuentes (FAQ)

**P1: Mi Facebook Shop no aparece o veo un mensaje de error.**
R1:

-   **Verifica SSL:** Asegúrate de que tu tienda PrestaShop tenga un certificado SSL válido (HTTPS). Facebook requiere conexiones seguras para las aplicaciones incrustadas. Si tu tienda no es HTTPS, Facebook Shop no se cargará.
-   **Configuración de la página de Facebook:** Vuelve a verificar que eres administrador de la página de fans de Facebook y que la pestaña "Tienda" está correctamente añadida y configurada en el propio Facebook.
-   **Configuración del módulo:** Vuelve a la configuración del módulo en PrestaShop y asegúrate de que todos los ajustes estén guardados correctamente.
-   **Borrar caché:** En PrestaShop, ve a **Parámetros avanzados > Rendimiento** y borra la caché de Smarty, la caché del navegador y cualquier otra caché.

**P2: Los productos no se muestran correctamente o faltan imágenes.**
R2:

-   **Configuración del producto:** Verifica que los productos que esperas ver estén activos y visibles en tu tienda principal de PrestaShop.
-   **Rutas de imagen:** Asegúrate de que las imágenes de tus productos tengan rutas correctas y sean accesibles públicamente.
-   **Configuración del módulo:** Verifica las configuraciones `faceshop_pdisp_image`, `faceshop_pdisp_name`, `faceshop_pdisp_price` para asegurarte de que estén activadas.
-   **Categoría raíz:** Confirma que tus configuraciones `faceshop_cat_root` y `faceshop_homepage_root` apuntan correctamente a categorías que contienen productos.

**P3: El módulo se ve diferente en dispositivos móviles dentro de Facebook.**
R3:

-   **Aplicación de Facebook vs. Navegador:** La experiencia puede variar ligeramente entre la aplicación móvil de Facebook y el acceso a Facebook a través de un navegador móvil. El módulo está diseñado para ser adaptable, pero el propio envoltorio de Facebook puede influir en el aspecto final.
-   **Verifica la adaptabilidad:** Prueba tu tienda principal de PrestaShop en dispositivos móviles para asegurarte de que sea totalmente adaptable. Facebook Shop hereda gran parte de su estilo de tu tienda principal.
-   **CSS personalizado:** Si tienes CSS personalizado en tu tema de PrestaShop, podría estar interfiriendo. Consulta a un desarrollador web para inspeccionar el CSS dentro del iframe de Facebook.

**P4: ¿Cómo traduzco Facebook Shop a otros idiomas?**
R4:

-   **Traducciones de PrestaShop:** El módulo Facebook Shop extrae contenido (nombres de productos, descripciones, nombres de categorías) directamente de tu tienda PrestaShop. Asegúrate de que todo el contenido de tus productos y categorías esté traducido dentro del propio PrestaShop.
-   **Texto del módulo:** Para el texto de la propia interfaz del módulo (por ejemplo, el enlace "Productos nuevos"), ve a **Internacional > Traducciones** en tu Back Office de PrestaShop. Selecciona "Traducciones de módulos instalados", elige tu tema, tu idioma y luego busca el módulo "Facebook Shop" para traducir sus cadenas específicas.
-   **Selector de idioma:** Asegúrate de que `faceshop_lang_disp` esté activado en la configuración del módulo para permitir a los clientes cambiar de idioma.

**P5: Mi Facebook Shop tarda en cargar.**
R5:

-   **Optimización de imágenes:** Asegúrate de que las imágenes de tus productos estén optimizadas para su uso web (comprimidas, dimensiones adecuadas). Las imágenes grandes son una causa común de carga lenta.
-   **Rendimiento del alojamiento:** Verifica el rendimiento de tu alojamiento web. Un servidor lento afectará tanto a tu tienda principal como a tu Facebook Shop.
-   **Número de productos:** Si estás mostrando un número muy alto de productos en la página de inicio o en las páginas de categoría (`faceshop_homepage_itemcount`, `faceshop_cat_itemcount`), considera reducir estos números.
-   **Caché:** Asegúrate de que los mecanismos de caché de PrestaShop estén correctamente configurados (**Parámetros avanzados > Rendimiento**).

## 4. Guía para Desarrolladores y Webmasters (Arquitectura Técnica y Mapa de Código)

### 4.1 Resumen de la Arquitectura

El módulo Facebook Shop (`faceshop`) está diseñado como un módulo estándar de PrestaShop, extendiendo principalmente la clase `Module`. Aprovecha el sistema de configuración de PrestaShop (`Configuration::get()`, `Configuration::updateValue()`) para almacenar sus ajustes. La funcionalidad principal del módulo implica renderizar una versión simplificada del front-office de PrestaShop dentro de un iframe en una página de fans de Facebook. Esto lo logra ajustando dinámicamente la visualización en función de un parámetro de URL específico (`?fc=module&module=faceshop&controller=shop`). El módulo no introduce tablas de base de datos personalizadas ni ObjectModels complejos, sino que manipula la visualización existente del front-office de PrestaShop a través de hooks y anulaciones de plantillas.

### 4.2 Controladores (`controllers/`)

Este módulo **no** contiene controladores dedicados de front-office o back-office en el directorio `controllers/`.
Su funcionalidad de front-office se maneja principalmente mediante el archivo principal `faceshop.php`, que intercepta las solicitudes a través de un parámetro de controlador `shop` personalizado (por ejemplo, `index.php?fc=module&module=faceshop&controller=shop`). Este enfoque permite que el módulo renderice una versión modificada del front-office estándar de PrestaShop dentro del iframe de Facebook, en lugar de crear estructuras de página completamente nuevas.

### 4.3 Clases y Modelos Principales (`classes/`)

El módulo **no** introduce ninguna clase o ObjectModels personalizados en un directorio `classes/`. Toda la lógica central está encapsulada dentro del archivo principal `faceshop/faceshop.php`.

### 4.4 Activos JavaScript (`views/js/`)

El módulo incluye varios archivos JavaScript, principalmente para mejorar la visualización del front-office dentro del iframe de Facebook.

-   `faceshop/jscolor/jscolor.js`
    -   **Alcance:** Back-office (probablemente utilizado en el formulario de configuración del módulo).
    -   **Descripción:** Una biblioteca JavaScript para un selector de color. Permite a los administradores seleccionar colores fácilmente para la configuración del módulo, aunque no se identificaron configuraciones de color explícitas en las claves de configuración, es una utilidad común para la personalización de la interfaz de usuario.
-   `faceshop/js/advajax.js`
    -   **Alcance:** Front-office (dentro del iframe de Facebook).
    -   **Descripción:** Probablemente un script de utilidad AJAX personalizado. Manejaría solicitudes asíncronas para cargar datos de productos, paginación u otro contenido dinámico dentro de Facebook Shop sin recargas completas de la página. Esto mejora la experiencia del usuario al hacer que la tienda se sienta más receptiva.
-   `faceshop/js/jquery.nivo.slider.pack.js`
    -   **Alcance:** Front-office (dentro del iframe de Facebook).
    -   **Descripción:** Una versión empaquetada del plugin jQuery Nivo Slider. Este script es responsable de la funcionalidad del slider de imágenes (`faceshop_slider_disp`) en la página de inicio de Facebook Shop, manejando transiciones, navegación y reproducción automática.
-   `faceshop/js/shop2.js`
    -   **Alcance:** Front-office (dentro del iframe de Facebook).
    -   **Descripción:** Este es probablemente el archivo JavaScript personalizado principal para la lógica de front-end de Facebook Shop. Contendría código para:
        -   Inicializar el Nivo Slider.
        -   Manejar la carga de contenido dinámico (por ejemplo, botones "Cargar más" para productos).
        -   Ajustar el diseño o el comportamiento específicamente para el entorno del iframe de Facebook.
        -   Potencialmente manejar interacciones con el SDK de Facebook (aunque no se menciona explícitamente, es común para las aplicaciones de Facebook).
        -   Cualquier mejora de la interfaz de usuario personalizada o detectores de eventos específicos de la tienda incrustada.

### 4.5 Hojas de Estilo CSS (`views/css/`)

El módulo incluye varios archivos CSS para estilizar la tienda de Facebook incrustada, asegurando que se vea consistente y funcione correctamente dentro del iframe.

-   `faceshop/css.css`
    -   **Alcance:** Front-office (dentro del iframe de Facebook).
    -   **Descripción:** Una hoja de estilo general para Facebook Shop. Probablemente contiene reglas de diseño principales, tipografía y estilo básico para elementos comunes (botones, enlaces, formularios) para garantizar un aspecto consistente.
-   `faceshop/css/style.css`
    -   **Alcance:** Front-office (dentro del iframe de Facebook).
    -   **Descripción:** Esta podría ser una hoja de estilo más específica, que potencialmente anule o extienda `css.css`. Podría contener estilos para características específicas del módulo o ajustes de diseño para adaptarse mejor al entorno de Facebook.
-   `faceshop/default/default.css`
    -   **Alcance:** Front-office (dentro del iframe de Facebook).
    -   **Descripción:** Esta hoja de estilo es probablemente parte del plugin Nivo Slider, proporcionando un estilo predeterminado para la navegación, los subtítulos y la apariencia general del slider. Los desarrolladores pueden anular estos estilos para que coincidan con el tema de la tienda.
-   `faceshop/style.css`
    -   **Alcance:** Front-office (dentro del iframe de Facebook).
    -   **Descripción:** Similar a `faceshop/css/style.css`, este podría ser otra hoja de estilo principal o un archivo de respaldo/legado. Definiría la presentación visual de los elementos de la tienda, asegurando que se rendericen correctamente dentro del iframe de Facebook.

### 4.6 Estructura de Plantillas Smarty (`views/templates/`)

El dossier del módulo indica que no se encontraron archivos `.tpl` específicos en `views/templates/`. Esto sugiere que el módulo funciona principalmente mediante:

1.  **Interceptar solicitudes estándar del front-office de PrestaShop:** Cuando se accede a través de la URL de Facebook Shop, el módulo probablemente modifica las variables globales de Smarty o las rutas de las plantillas para renderizar las plantillas de temas existentes de PrestaShop.
2.  **Uso de métodos `display` dentro de `faceshop.php`:** Los métodos `display()` del módulo podrían renderizar HTML directamente o incluir fragmentos del tema principal de PrestaShop, añadiendo o eliminando elementos dinámicamente según su configuración.
3.  **Renderizado impulsado por JavaScript:** Algunos elementos podrían ser inyectados o modificados dinámicamente por los archivos JavaScript después de la carga inicial de la página.

Si hubiera plantillas personalizadas, normalmente se encontrarían en:

-   `views/templates/hook/`: Para contenido renderizado en hooks específicos de PrestaShop.
-   `views/templates/admin/`: Para formularios o pantallas de back-office personalizados.
-   `views/templates/front/`: Para páginas de front-office independientes o contenido específico del módulo.

La ausencia de archivos `.tpl` explícitos implica una manipulación más directa del proceso de renderizado existente del front-office de PrestaShop.

### 4.7 Esquema de Base de Datos y Mapa de Hooks

-   **Tablas de base de datos**:
    El módulo no crea ninguna tabla de base de datos personalizada. Todos sus ajustes de configuración se almacenan en la tabla `ps_configuration` (o `_configuration` según el prefijo de la tabla) utilizando las claves de configuración enumeradas en la sección 4.1.
-   **Tabla de Hooks Registrados**:
    El módulo interactúa principalmente con la visualización del front-office de PrestaShop. Si bien el dossier enumera "Cabecera, Columnas, Producto o Pie de página" como hooks de front-office, la funcionalidad principal del módulo es incrustar el *front-office completo*. Probablemente utiliza una combinación de:

    -   **`hookDisplayHeader`**: Para inyectar sus activos CSS y JavaScript, y potencialmente para modificar la sección `<head>` para la compatibilidad con el iframe de Facebook.
    -   **`hookDisplayFooter`**: Para inyectar scripts o contenido adicional en la parte inferior de la página.
    -   **`actionFrontControllerSetMedia`**: (PrestaShop 1.7+) Para registrar sus archivos CSS y JS.
    -   **Lógica interna para renderizar la tienda**: El módulo probablemente tiene una lógica interna que, cuando se detecta que se está cargando dentro del iframe de Facebook, modifica la salida estándar del front-office de PrestaShop para ocultar/mostrar elementos según sus ajustes de configuración (por ejemplo, `faceshop_header_disp`, `faceshop_footer_disp`). Esto a menudo se logra anulando o manipulando variables Smarty y asignaciones de plantillas dentro de los métodos `display()` o `hook` del módulo.

| Nombre del Hook | Momento de Ejecución | Propósito Técnico |
| --- | --- | --- |
| `displayHeader` | Antes del contenido principal de la página, dentro de la sección `<head>`. | Inyectar archivos CSS y JavaScript del módulo, potencialmente modificar metaetiquetas para el iframe de Facebook. |
| `displayFooter` | Al final del contenido de la página, antes de la etiqueta de cierre `</body>`. | Inyectar scripts adicionales o códigos de seguimiento, o modificar el contenido del pie de página si `faceshop_footer_disp` está activado. |
| `actionFrontControllerSetMedia` (PS 1.7+) | Durante la fase de configuración de medios de un controlador frontal. | Registrar archivos CSS y JS para una carga óptima. |
| (Implícito) Hooks de la página de producto | En las páginas de detalles del producto. | Modificar la visualización de la página de producto según `faceshop_pdisp_trim`, `faceshop_pdisp_price`, etc., e inyectar botones para compartir en redes sociales. |
| (Implícito) Hooks de la página de categoría | En las páginas de listado de categorías. | Modificar la visualización de la página de categoría según `faceshop_cat_dispnew`, `faceshop_cat_disphot`, etc. |
| (Implícito) Hooks de la página de inicio | En la página de inicio de la tienda. | Renderizar el slider, productos destacados, productos nuevos y productos con descuento según la configuración del módulo. |

## 5. Soporte Oficial y Actualizaciones

Para las últimas actualizaciones, correcciones de errores y soporte profesional para tu módulo Facebook Shop, consulta tu cuenta de cliente en MyPresta.eu. Nuestro equipo se dedica a garantizar que tu módulo funcione de manera óptima y te ayude a maximizar tus ventas online.

-   **Historial de pedidos y descargas de MyPresta.eu:** <https://mypresta.eu/my-account/orders/>
-   **Contacto de soporte de MyPresta.eu:** <https://mypresta.eu/contact>
"""
