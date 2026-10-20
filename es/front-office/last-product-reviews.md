---
title: "Últimas reseñas de productos - Manual de comerciante y guía de configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop 'Últimas reseñas de productos' de MyPresta.eu."
sidebar:
  label: "Últimas reseñas de productos - Manual de comerciante y guía de configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Last product reviews en MyPresta.eu](https://mypresta.eu/modules/front-office-features/last-product-reviews.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/front-office/last-product-reviews/)
>
> ---


# Últimas reseñas de productos

## 1. Requisitos y compatibilidad

- **Versiones de PrestaShop compatibles**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilidad con PHP**: PHP 5.6 - 8.5
- **Requisitos de alojamiento**: Las extensiones PHP estándar (cURL, JSON, OpenSSL) suelen ser suficientes para este módulo.

## 2. Recorrido completo por la configuración (cada ajuste agrupado por pantalla)

### 2.1 Página de configuración del módulo (Back Office > Módulos > Configurar)

Esta es la pantalla de configuración principal del módulo "Últimas reseñas de productos". Aquí encontrará todos los ajustes para controlar cómo y dónde se muestran sus reseñas.

#### **Mostrar reseñas en**

- **Qué hace este ajuste:** Esta opción determina dónde aparecerá el bloque "Últimas reseñas de productos" en su sitio web. Puede elegir entre varias posiciones de hook estándar de PrestaShop.
- **Efecto de cambiar este ajuste:**
  - *Cuando se establece en "Cabecera":* El bloque de reseñas aparecerá en la parte superior de su tienda, a menudo encima o debajo de su navegación principal. Esto ofrece la máxima visibilidad.
  - *Cuando se establece en "Columna izquierda":* El bloque de reseñas aparecerá en la barra lateral izquierda de su tienda, si su tema tiene una.
  - *Cuando se establece en "Columna derecha":* El bloque de reseñas aparecerá en la barra lateral derecha de su tienda, si su tema tiene una.
  - *Cuando se establece en "Página de producto":* El bloque de reseñas aparecerá en las páginas de productos individuales. Esto es ideal para la venta cruzada o para mostrar pruebas sociales generales mientras un cliente considera una compra.
  - *Cuando se establece en "Pie de página":* El bloque de reseñas aparecerá en la parte inferior de cada página, normalmente encima de la información de derechos de autor.
- **Valor recomendado:** "Columna izquierda" o "Columna derecha" para visibilidad general, o "Página de producto" si desea enfatizar las reseñas durante el proceso de decisión de compra. "Cabecera" puede ser muy impactante, pero podría ocupar demasiado espacio principal dependiendo de su tema.
- **Escenario / ejemplo de comerciante:** Si desea que los clientes vean las reseñas recientes sin importar dónde naveguen, elija "Columna izquierda". Si desea fomentar las compras en las páginas de productos, seleccione "Página de producto".

#### **Número de reseñas a mostrar**

- **Qué hace este ajuste:** Esto controla cuántas reseñas de productos individuales se mostrarán en el bloque "Últimas reseñas de productos".
- **Efecto de cambiar este ajuste:**
  - *Cuando se establece en un número bajo (por ejemplo, 3):* El bloque será compacto, mostrando solo unas pocas reseñas. Esto es bueno para ahorrar espacio, pero podría no transmitir tanta prueba social.
  - *Cuando se establece en un número más alto (por ejemplo, 10):* El bloque será más grande, mostrando más reseñas. Esto ofrece más prueba social, pero requiere más espacio en pantalla.
- **Valor recomendado:** 3-5 para columnas, 5-8 para cabecera/pie de página, dependiendo del diseño de su tema y el espacio disponible.
- **Escenario / ejemplo de comerciante:** Si su columna izquierda es estrecha, establezca esto en 3 para evitar que el bloque se vuelva demasiado largo. Si tiene un pie de página ancho, podría establecerlo en 6 para mostrar más comentarios.

#### **Mostrar nombre del cliente**

- **Qué hace este ajuste:** Este interruptor determina si el nombre del cliente que dejó la reseña será visible en el bloque de reseñas.
- **Efecto de cambiar este ajuste:**
  - *Cuando está habilitado (SÍ):* Cada reseña mostrará el nombre del cliente (por ejemplo, "Reseña de Juan D."). Esto añade autenticidad y personalización.
  - *Cuando está deshabilitado (NO):* El nombre del cliente estará oculto, y solo se mostrará el contenido de la reseña y el producto. Esto podría ser preferible por privacidad o por un diseño más minimalista.
- **Valor recomendado:** SÍ. Mostrar los nombres de los clientes añade credibilidad y hace que las reseñas se sientan más genuinas.
- **Escenario / ejemplo de comerciante:** Para maximizar la confianza, habilite esto. Si le preocupa la privacidad del cliente o prefiere un aspecto muy limpio, podría deshabilitarlo.

#### **Mostrar nombre del producto**

- **Qué hace este ajuste:** Este interruptor controla si el nombre del producto que se está reseñando se mostrará junto al texto de la reseña.
- **Efecto de cambiar este ajuste:**
  - *Cuando está habilitado (SÍ):* Cada reseña indicará claramente a qué producto se refiere (por ejemplo, "Producto: Súper Gadget"). Esto ayuda a los clientes a comprender el contexto de la reseña.
  - *Cuando está deshabilitado (NO):* Solo se mostrará el texto de la reseña y el nombre del cliente (si está habilitado), sin mención explícita del producto. Esto hace que el bloque sea más genérico.
- **Valor recomendado:** SÍ. Es crucial que los clientes sepan qué producto se está reseñando.
- **Escenario / ejemplo de comerciante:** Si un cliente ve una reseña brillante, querrá saber de qué producto se trata. Habilitar esto les permite hacer clic y potencialmente comprar ese artículo específico.

#### **Mostrar contenido de la reseña**

- **Qué hace este ajuste:** Este interruptor determina si el texto real de la reseña del cliente se mostrará en el bloque.
- **Efecto de cambiar este ajuste:**
  - *Cuando está habilitado (SÍ):* Se mostrará el texto completo o truncado de la reseña. Esto proporciona comentarios detallados a los compradores potenciales.
  - *Cuando está deshabilitado (NO):* Solo se mostrará la calificación (estrellas), el nombre del cliente y el nombre del producto, sin la reseña escrita. Esto crea un bloque muy compacto, centrándose solo en las calificaciones por estrellas.
- **Valor recomendado:** SÍ. El contenido de la reseña es la parte más valiosa de la prueba social.
- **Escenario / ejemplo de comerciante:** Para dar a los clientes una visión rápida de lo que dicen los demás, habilite esto. Si solo desea mostrar calificaciones por estrellas como una señal rápida de confianza, podría deshabilitarlo.

#### **Mostrar estrellas de la reseña**

- **Qué hace este ajuste:** Este interruptor controla si la calificación por estrellas (por ejemplo, 5 de 5 estrellas) asociada a cada reseña será visible.
- **Efecto de cambiar este ajuste:**
  - *Cuando está habilitado (SÍ):* La calificación por estrellas se mostrará prominentemente para cada reseña. Este es un indicador visual rápido de la calidad del producto.
  - *Cuando está deshabilitado (NO):* La calificación por estrellas estará oculta, y solo se mostrará el contenido del texto (si está habilitado). Esto generalmente no se recomienda, ya que las calificaciones por estrellas son una señal de confianza universal.
- **Valor recomendado:** SÍ. Las calificaciones por estrellas son increíblemente efectivas para transmitir rápidamente la satisfacción con el producto.
- **Escenario / ejemplo de comerciante:** Habilite esto siempre para dar a los clientes una señal visual instantánea de la calidad del producto y la satisfacción del cliente.

#### **Mostrar imagen del producto**

- **Qué hace este ajuste:** Este interruptor determina si la imagen principal del producto que se está reseñando se mostrará junto a su reseña.
- **Efecto de cambiar este ajuste:**
  - *Cuando está habilitado (SÍ):* Aparecerá una pequeña miniatura de la imagen del producto con cada reseña. Esto hace que el bloque sea más atractivo visualmente y ayuda a los clientes a identificar rápidamente el producto.
  - *Cuando está deshabilitado (NO):* No se mostrará ninguna imagen del producto, lo que hace que el bloque se centre más en el texto.
- **Valor recomendado:** SÍ. Las imágenes de los productos mejoran significativamente el atractivo visual y la claridad del bloque de reseñas.
- **Escenario / ejemplo de comerciante:** Para que su bloque de reseñas sea más atractivo y ayudar a los clientes a asociar rápidamente las reseñas con productos específicos, habilite las imágenes de los productos.

#### **Mostrar precio del producto**

- **Qué hace este ajuste:** Este interruptor controla si el precio actual del producto que se está reseñando se mostrará en el bloque de reseñas.
- **Efecto de cambiar este ajuste:**
  - *Cuando está habilitado (SÍ):* Se mostrará el precio del producto. Esto puede ser útil para los clientes que son sensibles al precio o que quieren ver rápidamente si un producto reseñado se ajusta a su presupuesto.
  - *Cuando está deshabilitado (NO):* El precio no se mostrará, manteniendo el enfoque únicamente en la reseña y los detalles del producto.
- **Valor recomendado:** NO, a menos que desee específicamente resaltar los precios de los productos en el bloque de reseñas. A veces puede saturar la pantalla.
- **Escenario / ejemplo de comerciante:** Si está realizando una venta y desea destacar productos reseñados que actualmente tienen descuento, podría habilitar esto. De lo contrario, a menudo es mejor mantener el enfoque en la reseña en sí.

#### **Mostrar enlace del producto**

- **Qué hace este ajuste:** Este interruptor determina si el nombre del producto (o la imagen, si está habilitada) en el bloque de reseñas será un enlace clicable que lleve al cliente directamente a la página del producto.
- **Efecto de cambiar este ajuste:**
  - *Cuando está habilitado (SÍ):* Los clientes pueden hacer clic en el nombre/imagen del producto para navegar a la página completa del producto, donde pueden obtener más información y potencialmente realizar una compra. Esto es crucial para dirigir el tráfico a las páginas de productos.
  - *Cuando está deshabilitado (NO):* El nombre/imagen del producto será texto/imagen estática, y los clientes no podrán hacer clic. Esto reduce la capacidad del módulo para impulsar conversiones.
- **Valor recomendado:** SÍ. Habilite esto siempre para permitir que los clientes exploren fácilmente los productos reseñados.
- **Escenario / ejemplo de comerciante:** Un cliente ve una excelente reseña de un "Altavoz Bluetooth". Si el nombre del producto es clicable, puede ir inmediatamente a la página del altavoz para comprarlo.

#### **Mostrar fecha de la reseña**

- **Qué hace este ajuste:** Este interruptor controla si se mostrará la fecha en que se envió la reseña.
- **Efecto de cambiar este ajuste:**
  - *Cuando está habilitado (SÍ):* Se mostrará la fecha (por ejemplo, "Reseñado el 26-10-2023"). Esto añade transparencia y asegura a los clientes que las reseñas son recientes y relevantes.
  - *Cuando está deshabilitado (NO):* La fecha estará oculta.
- **Valor recomendado:** SÍ. Las reseñas recientes son más impactantes y confiables.
- **Escenario / ejemplo de comerciante:** Mostrar la fecha ayuda a los clientes a ver que su tienda está activa y recibe constantemente nuevos comentarios, generando confianza.

#### **Mostrar título de la reseña**

- **Qué hace este ajuste:** Este interruptor determina si se mostrará el título de la reseña (si los clientes lo proporcionan).
- **Efecto de cambiar este ajuste:**
  - *Cuando está habilitado (SÍ):* Si una reseña tiene un título (por ejemplo, "¡Producto increíble!"), se mostrará, a menudo en negrita, proporcionando un resumen rápido del sentimiento de la reseña.
  - *Cuando está deshabilitado (NO):* Solo se mostrará el contenido principal de la reseña, sin un título separado.
- **Valor recomendado:** SÍ. Los títulos de las reseñas son excelentes para captar rápidamente la atención y resumir la esencia de la reseña.
- **Escenario / ejemplo de comerciante:** Un cliente que escanea rápidamente las reseñas puede captar la idea principal de títulos como "Gran valor" o "Decepcionado" antes de leer el texto completo.

#### **Calificación mínima a mostrar**

- **Qué hace este ajuste:** Este filtro le permite establecer una calificación mínima por estrellas para que las reseñas se incluyan en el bloque "Últimas reseñas de productos".
- **Efecto de cambiar este ajuste:**
  - *Cuando se establece en 1 estrella:* Se mostrarán todas las reseñas (1-5 estrellas).
  - *Cuando se establece en 3 estrellas:* Solo se mostrarán las reseñas con 3, 4 o 5 estrellas. Las reseñas con 1 o 2 estrellas se excluirán.
  - *Cuando se establece en 5 estrellas:* Solo se mostrarán las reseñas perfectas de 5 estrellas.
- **Valor recomendado:** 3 o 4 estrellas. Aunque la transparencia es buena, es posible que desee destacar principalmente los comentarios positivos en este bloque prominente.
- **Escenario / ejemplo de comerciante:** Para asegurarse de que su bloque "Últimas reseñas de productos" siempre muestre comentarios positivos, establezca esto en 4 estrellas. Esto ayuda a mantener una imagen positiva sin dejar de ser auténtico.

#### **Mostrar solo reseñas de la categoría seleccionada**

- **Qué hace este ajuste:** Esta opción le permite filtrar las reseñas mostradas para que solo sean aquellas asociadas con productos de una categoría específica.
- **Efecto de cambiar este ajuste:**
  - *Cuando se selecciona "No":* Se considerarán para mostrar reseñas de todas las categorías.
  - *Cuando se selecciona una categoría específica (por ejemplo, "Electrónica"):* Solo se mostrarán las reseñas de productos dentro de la categoría "Electrónica" (y sus subcategorías).
- **Valor recomendado:** "No" para prueba social general. Seleccione una categoría si el bloque de reseñas se coloca en un contexto donde solo son relevantes tipos de productos específicos (por ejemplo, en una página de categoría).
- **Escenario / ejemplo de comerciante:** Si coloca el bloque de reseñas en la página de su categoría "Camisetas", podría seleccionar la categoría "Camisetas" aquí para asegurarse de que solo se muestren reseñas relevantes, mejorando la experiencia del cliente.

#### **Mostrar solo reseñas del producto seleccionado**

- **Qué hace este ajuste:** Esta opción le permite filtrar las reseñas mostradas para que solo sean aquellas asociadas con un producto específico.
- **Efecto de cambiar este ajuste:**
  - *Cuando se selecciona "No":* Se considerarán para mostrar reseñas de todos los productos.
  - *Cuando se selecciona un producto específico (por ejemplo, "Mi Gadget Impresionante"):* Solo se mostrarán las reseñas de "Mi Gadget Impresionante".
- **Valor recomendado:** "No" para prueba social general. Seleccione un producto si el bloque de reseñas se coloca en un contexto donde solo son relevantes las reseñas de un solo producto (por ejemplo, en una página de destino personalizada para ese producto).
- **Escenario / ejemplo de comerciante:** Si tiene una página promocional especial para su "Cafetera más vendida", podría configurar este bloque para que solo muestre reseñas de esa cafetera específica en esa página.

#### **Mostrar reseñas como carrusel**

- **Qué hace este ajuste:** Este interruptor habilita o deshabilita un carrusel dinámico para el bloque de reseñas.
- **Efecto de cambiar este ajuste:**
  - *Cuando está habilitado (SÍ):* Las reseñas se desplazarán automáticamente o permitirán a los clientes navegar por ellas usando flechas/puntos. Esto es ideal para mostrar muchas reseñas en un espacio compacto.
  - *Cuando está deshabilitado (NO):* Las reseñas se mostrarán como una lista estática, una tras otra.
- **Valor recomendado:** SÍ, especialmente si muestra más de 3-4 reseñas o si el bloque está en una columna estrecha.
- **Escenario / ejemplo de comerciante:** Si desea mostrar 8 reseñas en su columna izquierda pero no quiere que la columna se vuelva excesivamente larga, habilitar el carrusel la hará compacta e interactiva.

#### **Reproducción automática del carrusel**

- **Qué hace este ajuste:** Si "Mostrar reseñas como carrusel" está habilitado, este ajuste controla si el carrusel se mueve automáticamente a la siguiente reseña sin interacción del usuario.
- **Efecto de cambiar este ajuste:**
  - *Cuando está habilitado (SÍ):* El carrusel hará la transición automáticamente entre reseñas después de un retraso establecido.
  - *Cuando está deshabilitado (NO):* El carrusel solo se moverá cuando el cliente haga clic en las flechas de navegación o en los puntos.
- **Valor recomendado:** SÍ, pero asegúrese de que la "Velocidad de reproducción automática del carrusel" esté configurada a una duración razonable.
- **Escenario / ejemplo de comerciante:** Para mantener el bloque de reseñas dinámico y asegurar que todas las reseñas obtengan algo de visibilidad, habilite la reproducción automática.

#### **Velocidad de reproducción automática del carrusel (en ms)**

- **Qué hace este ajuste:** Si la "Reproducción automática del carrusel" está habilitada, este ajuste determina cuánto tiempo (en milisegundos) se muestra cada reseña antes de que el carrusel pase automáticamente a la siguiente.
- **Efecto de cambiar este ajuste:**
  - *Un número más bajo (por ejemplo, 2000ms = 2 segundos):* Las reseñas cambiarán rápidamente.
  - *Un número más alto (por ejemplo, 5000ms = 5 segundos):* Las reseñas permanecerán visibles por más tiempo, dando a los clientes más tiempo para leer.
- **Valor recomendado:** 4000-6000 (4-6 segundos) para dar a los clientes tiempo suficiente para leer una reseña sin sentirse apurados.
- **Escenario / ejemplo de comerciante:** Establezca esto en 5000ms para que los clientes tengan tiempo suficiente para leer cada reseña a medida que se desliza.

#### **Controles del carrusel**

- **Qué hace este ajuste:** Si "Mostrar reseñas como carrusel" está habilitado, esto controla si las flechas de navegación (izquierda/derecha) son visibles para que los clientes naveguen manualmente por las reseñas.
- **Efecto de cambiar este ajuste:**
  - *Cuando está habilitado (SÍ):* Aparecerán flechas en el carrusel, permitiendo la navegación manual.
  - *Cuando está deshabilitado (NO):* No se mostrarán flechas. Los clientes solo pueden depender de la reproducción automática (si está habilitada) o de los gestos táctiles/deslizantes.
- **Valor recomendado:** SÍ. Proporcionar controles mejora la experiencia del usuario, incluso con la reproducción automática.
- **Escenario / ejemplo de comerciante:** Para dar a los clientes control total sobre la navegación por las reseñas, habilite los controles del carrusel.

#### **Paginador del carrusel**

- **Qué hace este ajuste:** Si "Mostrar reseñas como carrusel" está habilitado, esto controla si los pequeños puntos (paginación) son visibles, indicando el número total de reseñas y la reseña actual que se muestra.
- **Efecto de cambiar este ajuste:**
  - *Cuando está habilitado (SÍ):* Aparecerán puntos, mostrando el progreso y permitiendo saltos directos a reseñas específicas.
  - *Cuando está deshabilitado (NO):* No se mostrarán puntos.
- **Valor recomendado:** SÍ. Los paginadores proporcionan una indicación visual clara de cuántas reseñas están disponibles y dónde se encuentra el cliente en la secuencia.
- **Escenario / ejemplo de comerciante:** Para ayudar a los clientes a comprender cuántas reseñas hay en el carrusel y saltar fácilmente a una específica, habilite el paginador del carrusel.

### 2.2 Tabla de referencia rápida de configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| Configuración del módulo | Mostrar reseñas en | Columna izquierda / Columna derecha | Controla la posición del bloque de reseñas en su tienda. |
| Configuración del módulo | Número de reseñas a mostrar | 3-5 (columnas), 5-8 (cabecera/pie de página) | Establece cuántas reseñas son visibles en el bloque. |
| Configuración del módulo | Mostrar nombre del cliente | SÍ | Muestra el nombre del reseñador para autenticidad. |
| Configuración del módulo | Mostrar nombre del producto | SÍ | Vincula claramente la reseña a su producto. |
| Configuración del módulo | Mostrar contenido de la reseña | SÍ | Muestra el texto real de la reseña. |
| Configuración del módulo | Mostrar estrellas de la reseña | SÍ | Indicador visual de la calificación del producto. |
| Configuración del módulo | Mostrar imagen del producto | SÍ | Hace que el bloque sea más atractivo visualmente e identificable. |
| Configuración del módulo | Mostrar precio del producto | NO | Muestra el precio del producto (puede saturar, generalmente no es necesario). |
| Configuración del módulo | Mostrar enlace del producto | SÍ | Permite a los clientes hacer clic para ir a la página del producto. |
| Configuración del módulo | Mostrar fecha de la reseña | SÍ | Muestra cuándo se envió la reseña, demostrando su actualidad. |
| Configuración del módulo | Mostrar título de la reseña | SÍ | Muestra el título de la reseña para resúmenes rápidos. |
| Configuración del módulo | Calificación mínima a mostrar | 3 o 4 estrellas | Filtra las reseñas con calificaciones más bajas para una visualización positiva. |
| Configuración del módulo | Mostrar solo reseñas de la categoría seleccionada | No | Filtra las reseñas por categoría de producto. |
| Configuración del módulo | Mostrar solo reseñas del producto seleccionado | No | Filtra las reseñas por un producto específico. |
| Configuración del módulo | Mostrar reseñas como carrusel | SÍ | Presenta las reseñas en un carrusel dinámico y desplazable. |
| Configuración del módulo | Reproducción automática del carrusel | SÍ | Hace avanzar automáticamente el carrusel. |
| Configuración del módulo | Velocidad de reproducción automática del carrusel (en ms) | 4000-6000 | Establece la duración que se muestra cada reseña en el carrusel. |
| Configuración del módulo | Controles del carrusel | SÍ | Muestra flechas de navegación para el control manual del carrusel. |
| Configuración del módulo | Paginador del carrusel | SÍ | Muestra puntos para la paginación del carrusel. |

## 3. Solución de problemas del comerciante y preguntas frecuentes (FAQ)

**P: He configurado el módulo, pero el bloque de reseñas no aparece en mi tienda.**
R:

1. **Verifique la posición del módulo:** Vaya a **Diseño > Posiciones** (o **Módulos > Posiciones** en versiones anteriores de PrestaShop) en su Back Office. Busque `displayLastReviews` (o el hook que seleccionó en la configuración del módulo). Asegúrese de que el módulo "Últimas reseñas de productos" esté listado y habilitado para ese hook. Si no, haga clic en "Trasplantar un módulo" y agréguelo al hook deseado.
2. **Borrar caché:** PrestaShop a menudo almacena contenido en caché. Vaya a **Parámetros avanzados > Rendimiento** y haga clic en "Borrar caché" (o los botones "Borrar caché de Smarty" y "Borrar caché").
3. **Verifique las reseñas:** Asegúrese de que realmente tiene reseñas de productos aprobadas en su tienda. El módulo solo puede mostrar las reseñas que existen y son visibles.
4. **Compatibilidad del tema:** Aunque el módulo está diseñado para ser compatible, algunos temas altamente personalizados pueden requerir pequeños ajustes de CSS. Verifique la consola de desarrollador de su navegador en busca de errores de JavaScript.

**P: Las reseñas se muestran, pero no se ven bien (por ejemplo, mal estilo, imágenes demasiado grandes).**
R:

1. **Conflictos de tema:** El CSS de su tema podría estar anulando los estilos del módulo. Puede intentar agregar CSS personalizado al archivo `custom.css` de su tema (si tiene uno) o editar directamente `lastreviews/views/css/lastreviews.css` (aunque esto no es seguro para las actualizaciones).
2. **Tamaños de imagen:** Si las imágenes de los productos son demasiado grandes, verifique la configuración de imágenes de su tema o el CSS del módulo. El módulo utiliza un tamaño de imagen estándar, pero su tema podría estar renderizándolo de manera diferente.
3. **Problemas con el carrusel:** Si el carrusel no funciona, asegúrese de que "Mostrar reseñas como carrusel" esté habilitado. Verifique si hay errores de JavaScript en la consola de su navegador, ya que otros módulos o scripts del tema podrían estar en conflicto.

**P: ¿Puedo mostrar reseñas de un producto o categoría específica solamente?**
R: ¡Sí! En la configuración del módulo, tiene opciones para "Mostrar solo reseñas de la categoría seleccionada" y "Mostrar solo reseñas del producto seleccionado". Utilice estos desplegables para filtrar las reseñas que se muestran en el bloque.

**P: Mis reseñas están en varios idiomas. ¿Las mostrará el módulo correctamente?**
R: El módulo se basa en el sistema de reseñas estándar de PrestaShop. Si sus reseñas están correctamente asociadas con los idiomas en PrestaShop, el módulo debería mostrar las reseñas en el idioma activo del front office. Asegúrese de que su tema y PrestaShop estén configurados correctamente para contenido multilingüe.

**P: ¿Cómo consigo que se muestren más reseñas?**
R: Este módulo solo *muestra* las reseñas existentes. Para obtener más reseñas, debe animar a los clientes a dejarlas. Considere usar un módulo separado para recordatorios de reseñas, ofrecer incentivos o hacer que el proceso de envío de reseñas sea muy fácil en sus páginas de productos.

## 4. Guía para desarrolladores y webmasters (arquitectura técnica y mapa de código)

### 4.1 Descripción general de la arquitectura

El módulo "Últimas reseñas de productos" es un módulo estándar de PrestaShop que sigue un patrón similar a MVC. Opera principalmente como una característica de front-office, enganchándose en varios puntos de visualización para renderizar un bloque de reseñas de productos recientes. Aprovecha la funcionalidad central de `ProductComment` de PrestaShop (o similar) para obtener datos de reseñas. La lógica principal del módulo reside en `index.php`, que maneja la configuración y el registro de hooks, mientras que las plantillas y los activos gestionan la visualización del front-end. Utiliza una biblioteca JavaScript de terceros, `lightslider.js`, para la funcionalidad de carrusel.

### 4.2 Controladores (`controllers/`)

Este módulo no contiene ningún controlador de administración de Front-Office o Back-Office personalizado. Toda la configuración se maneja directamente dentro del método `getContent()` de la clase principal del módulo.

### 4.3 Clases y modelos principales (`classes/`)

Este módulo no define ninguna clase personalizada u `ObjectModel` en un directorio `classes/`. Se basa en el `ProductComment` central de PrestaShop (o equivalente, dependiendo de la versión de PrestaShop y si el módulo oficial de Comentarios de productos está instalado) para obtener datos de reseñas.

### 4.4 Activos JavaScript (`views/js/`)

- **`lastreviews/lib/src/js/lightslider.js`**
  - **Alcance:** Front-office.
  - **Propósito:** Esta es la biblioteca JavaScript principal para crear carruseles/deslizadores de contenido responsivos. Proporciona la funcionalidad para la característica "Mostrar reseñas como carrusel".
  - **Funcionalidad:** Se enlaza a un elemento `<ul>` (o contenedor similar) para transformarlo en un carrusel responsivo. Maneja la reproducción automática, los controles de navegación (flechas), la paginación (puntos), los gestos táctiles/deslizantes y el redimensionamiento responsivo.
  - **Dependencias:** Normalmente requiere jQuery.

### 4.5 Hojas de estilo CSS (`views/css/`)

- **`lastreviews/lib/src/css/lightslider.css`**

  - **Alcance:** Estilo del cliente del Front-office.
  - **Propósito:** Proporciona el estilo predeterminado para la biblioteca `lightslider.js`, incluyendo el diseño básico, las flechas de navegación, los puntos del paginador y los estilos de animación para el carrusel.
  - **Selectores clave:** `.lightSlider`, `.lSAction > .lSPrev`, `.lSAction > .lSNext`, `.lSPager`, etc. Los desarrolladores pueden anularlos para que coincidan con la estética de su tema.
- **`lastreviews/views/css/lastreviews.css`**

  - **Alcance:** Estilo del cliente del Front-office.
  - **Propósito:** Contiene estilos personalizados específicos para el bloque de visualización del módulo "Últimas reseñas de productos". Esto incluye el estilo para el contenedor de reseñas, los elementos individuales de las reseñas, las imágenes de los productos, las calificaciones por estrellas y los elementos de texto.
  - **Selectores clave:** `.last-reviews-block`, `.last-review-item`, `.review-product-image`, `.review-stars`, `.review-customer-name`, `.review-product-name`, etc. Estos selectores están diseñados para ser fácilmente anulados por el CSS de un tema personalizado para su integración.

### 4.6 Estructura de la plantilla Smarty (`views/templates/`)

- **Plantillas de hook (`views/templates/hook/`)**:
  - **`lastreviews/views/templates/hook/admin-tips.tpl`**
    - **Propósito:** Esta plantilla probablemente se utiliza en la página de configuración del Back Office (`getContent()`) para mostrar consejos o instrucciones administrativas al comerciante. No se renderiza en el front office.
    - **Contenido:** Normalmente contiene HTML para mensajes informativos, enlaces a documentación o advertencias.
  - **`lastreviews/views/templates/hook/last-reviews.tpl`**
    - **Propósito:** Esta es la plantilla principal del front-office responsable de renderizar el bloque "Últimas reseñas de productos". Está enganchada a varios puntos de visualización (por ejemplo, `displayLeftColumn`, `displayFooter`).
    - **Datos:** Recibe una matriz de datos de reseñas (nombre del cliente, nombre del producto, calificación, contenido, fecha, imagen, enlace) de la lógica PHP del módulo.
    - **Estructura:** Itera a través de las reseñas proporcionadas, mostrando condicionalmente elementos basados en la configuración del módulo (por ejemplo, nombre del cliente, imagen del producto, carrusel). Incluye la estructura HTML necesaria para que `lightslider.js` se inicialice si la opción de carrusel está habilitada.

### 4.7 Esquema de la base de datos y mapa de hooks

- **Tablas de la base de datos**:

  - Este módulo no crea sus propias tablas de base de datos personalizadas. Se basa en las tablas principales de PrestaShop para las reseñas de productos, normalmente `ps_product_comment` y tablas relacionadas (si el módulo oficial de Comentarios de productos está instalado y activo).
  - La configuración se almacena en la tabla `ps_configuration`, con claves típicamente prefijadas por `LASTREVIEWS_` (por ejemplo, `LASTREVIEWS_DISPLAY_IN`, `LASTREVIEWS_NUM_REVIEWS`).
- **Tabla de hooks registrados**:

  | Nombre del Hook | Momento de ejecución | Propósito técnico |
  | --- | --- | --- |
  | `displayHeader` | En la sección `<head>` de todas las páginas del front-office. | Se utiliza para incluir activos CSS/JS y potencialmente renderizar el bloque de reseñas en la parte superior de la página. |
  | `displayLeftColumn` | En la barra lateral izquierda de las páginas del front-office. | Renderiza el bloque de reseñas en la columna izquierda. |
  | `displayRightColumn` | En la barra lateral derecha de las páginas del front-office. | Renderiza el bloque de reseñas en la columna derecha. |
  | `displayFooter` | En la sección del pie de página de todas las páginas del front-office. | Renderiza el bloque de reseñas en el pie de página. |
  | `displayProductAdditionalInfo` (o hook similar de página de producto) | En la página del producto, normalmente debajo de la información principal del producto. | Renderiza el bloque de reseñas en las páginas de productos individuales. |
  | `actionFrontControllerSetMedia` | Se ejecuta cuando un controlador frontal establece sus medios (CSS/JS). | Se utiliza para registrar los archivos CSS y JavaScript del módulo (`lightslider.js`, `lastreviews.css`) para que se carguen en el front office. |

## 5. Soporte oficial y actualizaciones

Para obtener las últimas actualizaciones, correcciones de errores y soporte oficial para el módulo "Últimas reseñas de productos", consulte su cuenta de cliente en [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nuestro equipo de soporte está disponible para ayudarle con cualquier problema o pregunta que pueda tener con respecto a la funcionalidad y compatibilidad del módulo.
