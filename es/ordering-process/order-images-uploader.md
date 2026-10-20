---
title: "Cargador de imágenes de pedidos - Manual del Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop 'Cargador de imágenes de pedidos' de MyPresta.eu."
sidebar:
  label: "Cargador de imágenes de pedidos - Manual del Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Order images uploader en MyPresta.eu](https://mypresta.eu/modules/ordering-process/order-images-uploader.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/ordering-process/order-images-uploader/)
>
> ---


# Cargador de imágenes de pedidos

## 1. Requisitos y Compatibilidad

- **Versiones de PrestaShop compatibles**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilidad con PHP**: PHP 5.6 - 8.5
- **Requisitos de alojamiento**: Las extensiones PHP estándar (cURL, JSON, OpenSSL) suelen ser suficientes. Asegúrese de que su servidor tenga límites de carga de archivos adecuados configurados en `php.ini` (por ejemplo, `upload_max_filesize`, `post_max_size`) para acomodar el tamaño de los archivos que sus clientes puedan subir.

## 2. Recorrido Completo por la Configuración (Cada Ajuste Agrupado por Pantalla)

### 2.1 Página de Configuración del Módulo (Back Office > Módulos > Configurar > Cargador de imágenes de pedidos)

Esta es la pantalla de configuración principal donde controla el comportamiento general y la apariencia del módulo.

#### Configuración General

- **Habilitar módulo:**

  - **Qué hace este ajuste:** Este es el interruptor principal para activar o desactivar la funcionalidad completa del módulo.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está habilitado:* Las características del módulo (formularios de carga, gestión de archivos) estarán activas en su front office y back office.
    - *Cuando está deshabilitado:* Toda la funcionalidad del módulo estará oculta para clientes y administradores, pausando efectivamente su operación.
  - **Valor recomendado:** SÍ
  - **Escenario / ejemplo de comerciante:** Si está configurando el módulo por primera vez, habilítelo para probar. Si necesita deshabilitar temporalmente las cargas de archivos por mantenimiento, configúrelo en NO.
- **Permitir a los clientes subir archivos:**

  - **Qué hace este ajuste:** Determina si los clientes tienen permitido subir archivos en absoluto.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está habilitado:* Los clientes verán formularios de carga y podrán enviar archivos.
    - *Cuando está deshabilitado:* Los clientes no verán ninguna opción de carga, incluso si el módulo está habilitado.
  - **Valor recomendado:** SÍ
  - **Escenario / ejemplo de comerciante:** Si solo desea usar el módulo para la gestión interna de archivos (por ejemplo, administradores subiendo archivos a pedidos), podría deshabilitar esto. Para la mayoría de los casos de uso, los clientes necesitan subir archivos, así que manténgalo habilitado.
- **Permitir a los clientes invitados subir archivos:**

  - **Qué hace este ajuste:** Controla si los clientes no registrados (invitados) pueden subir archivos.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está habilitado:* Los invitados pueden subir archivos, típicamente asociados con su carrito o pedido durante el proceso de compra.
    - *Cuando está deshabilitado:* Solo los clientes registrados e iniciados sesión pueden subir archivos.
  - **Valor recomendado:** SÍ (si permite la compra como invitado y necesita archivos de invitados)
  - **Escenario / ejemplo de comerciante:** Si su tienda permite la compra como invitado y requiere la carga de archivos para pedidos de invitados (por ejemplo, un trabajo de impresión rápido), habilite esto. Si desea obligar a los clientes a registrarse para subir archivos, deshabilítelo.
- **Permitir a los clientes eliminar archivos:**

  - **Qué hace este ajuste:** Da a los clientes la capacidad de eliminar archivos que han subido previamente.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está habilitado:* Los clientes verán una opción de "Eliminar" junto a sus archivos subidos en su cuenta.
    - *Cuando está deshabilitado:* Los clientes pueden subir pero no pueden eliminar archivos. Solo los administradores pueden eliminarlos.
  - **Valor recomendado:** NO (a menos que confíe en que los clientes gestionarán sus archivos perfectamente)
  - **Escenario / ejemplo de comerciante:** Para pedidos de impresión personalizados, es posible que desee deshabilitar esto para evitar que los clientes eliminen accidentalmente un archivo que ya está en producción. Si los archivos son temporales o fácilmente reemplazables, podría habilitarlo para la comodidad del cliente.
- **Permitir a los clientes descargar archivos:**

  - **Qué hace este ajuste:** Determina si los clientes pueden descargar archivos que ellos (o usted) han subido a sus pedidos.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está habilitado:* Los clientes pueden hacer clic para descargar sus archivos desde su historial de pedidos.
    - *Cuando está deshabilitado:* Los clientes no pueden descargar archivos.
  - **Valor recomendado:** SÍ (para transparencia y acceso del cliente)
  - **Escenario / ejemplo de comerciante:** Si sube una prueba o un diseño final para que el cliente lo revise, habilitar esto les permite descargarlo.
- **Permitir a los clientes subir archivos a pedidos:**

  - **Qué hace este ajuste:** Controla específicamente si los clientes pueden subir archivos *después* de que se haya realizado un pedido, desde su página de historial de pedidos.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está habilitado:* Aparecerá una opción de carga en la página de detalles del pedido individual del cliente en "Mi cuenta".
    - *Cuando está deshabilitado:* Los clientes solo pueden subir archivos durante el proceso de carrito/pago o en las páginas de productos, no a pedidos existentes.
  - **Valor recomendado:** SÍ (altamente recomendado para mayor flexibilidad)
  - **Escenario / ejemplo de comerciante:** Un cliente olvidó subir un logotipo específico después de realizar un pedido de camisetas personalizadas. Con esto habilitado, pueden añadirlo fácilmente más tarde.
- **Permitir a los clientes subir archivos a carritos:**

  - **Qué hace este ajuste:** Controla si los clientes pueden subir archivos mientras sus artículos aún están en el carrito de compras.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está habilitado:* Aparecerá una opción de carga en la página del carrito de compras.
    - *Cuando está deshabilitado:* Los clientes no pueden subir archivos a su carrito.
  - **Valor recomendado:** SÍ (conveniente para los clientes)
  - **Escenario / ejemplo de comerciante:** Un cliente está creando un álbum de fotos personalizado. Puede subir fotos directamente al carrito antes de proceder al pago.
- **Permitir a los clientes subir archivos a productos:**

  - **Qué hace este ajuste:** Controla si los clientes pueden subir archivos directamente en las páginas de productos individuales.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está habilitado:* Aparecerá una opción de carga en las páginas de productos.
    - *Cuando está deshabilitado:* Los clientes no pueden subir archivos en las páginas de productos.
  - **Valor recomendado:** SÍ (para productos altamente personalizables)
  - **Escenario / ejemplo de comerciante:** Para una taza personalizada, el cliente puede subir la foto deseada directamente en la página del producto de la taza antes de añadirla al carrito.
- **Permitir a los clientes subir archivos a la cuenta del cliente:**

  - **Qué hace este ajuste:** Habilita una sección dedicada "Mis archivos" en la cuenta del cliente, permitiéndoles subir y gestionar archivos no necesariamente vinculados a un pedido o carrito específico.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está habilitado:* Aparece un nuevo elemento de menú "Mis archivos" en el panel de control "Mi cuenta" del cliente.
    - *Cuando está deshabilitado:* Esta sección está oculta.
  - **Valor recomendado:** NO (a menos que tenga una necesidad específica de almacenamiento general de archivos)
  - **Escenario / ejemplo de comerciante:** Si desea que los clientes suban previamente activos comunes (por ejemplo, el logotipo de su empresa) que podrían usar en múltiples pedidos futuros, esto podría ser útil. De lo contrario, podría añadir una complejidad innecesaria.
- **Forzar a los clientes a subir archivos a pedidos:**

  - **Qué hace este ajuste:** Hace que la carga de archivos sea obligatoria para que un pedido se complete. Si no se suben archivos, el cliente no puede continuar.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está habilitado:* Los clientes serán bloqueados para completar el pago hasta que suban al menos un archivo.
    - *Cuando está deshabilitado:* La carga de archivos es opcional.
  - **Valor recomendado:** NO (solo habilítelo si es absolutamente crítico para cada pedido)
  - **Escenario / ejemplo de comerciante:** Para una imprenta donde *cada* pedido requiere un archivo de diseño, habilitar esto asegura que ningún pedido se procese sin los activos necesarios. Tenga precaución, ya que esto puede afectar las tasas de conversión si no todos los productos requieren un archivo.
- **Forzar a los clientes a subir archivos a productos:**

  - **Qué hace este ajuste:** Hace que la carga de archivos sea obligatoria para que un producto se añada al carrito.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está habilitado:* Los clientes no pueden añadir un producto al carrito hasta que suban al menos un archivo para ese producto.
    - *Cuando está deshabilitado:* La carga de archivos es opcional en la página del producto.
  - **Valor recomendado:** NO (solo habilítelo para productos que son *siempre* personalizados)
  - **Escenario / ejemplo de comerciante:** Para un producto "Diseña tu propia camiseta", esto asegura que el cliente proporcione su diseño antes de añadirlo al carrito.
- **Forzar a los clientes a subir archivos a carritos:**

  - **Qué hace este ajuste:** Hace que la carga de archivos sea obligatoria para que todo el carrito sea procesado.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está habilitado:* Los clientes no pueden pasar del carrito al pago hasta que suban al menos un archivo para el carrito.
    - *Cuando está deshabilitado:* La carga de archivos es opcional en la página del carrito.
  - **Valor recomendado:** NO (use con extrema precaución, puede afectar gravemente la conversión)
  - **Escenario / ejemplo de comerciante:** Esto rara vez se recomienda a menos que *cada pedido* en su tienda requiera una carga de archivo general. Generalmente es mejor forzar las cargas a nivel de producto o pedido si es necesario.
- **Extensiones de archivo permitidas (separadas por coma):**

  - **Qué hace este ajuste:** Define qué tipos de archivo se permite a los clientes subir.
  - **Efecto de cambiar este ajuste:**
    - *Cuando se cambia:* Solo se aceptarán archivos con las extensiones especificadas (por ejemplo, `jpg,png,gif,pdf`). Cualquier otro tipo de archivo será rechazado.
  - **Valor recomendado:** `jpg,jpeg,png,gif,pdf,doc,docx,xls,xlsx,txt` (ajuste según sus necesidades)
  - **Escenario / ejemplo de comerciante:** Una imprenta podría permitir `jpg,png,pdf,ai,eps`. Una joyería personalizada podría necesitar solo `jpg,png`. Limitar las extensiones mejora la seguridad y asegura que reciba archivos utilizables.
- **Tamaño máximo de archivo (en MB):**

  - **Qué hace este ajuste:** Establece el límite superior para el tamaño de un solo archivo que un cliente puede subir.
  - **Efecto de cambiar este ajuste:**
    - *Cuando se cambia:* Los archivos más grandes que este límite serán rechazados.
  - **Valor recomendado:** `10` (o superior si espera archivos de diseño grandes)
  - **Escenario / ejemplo de comerciante:** Si los clientes suben imágenes de alta resolución o archivos de diseño grandes, podría establecer esto en `50` o `100`. Tenga en cuenta que los archivos muy grandes pueden ralentizar las cargas y consumir espacio en el servidor. Asegúrese de que `upload_max_filesize` y `post_max_size` de su servidor en `php.ini` también estén configurados para soportar este valor.
- **Número máximo de archivos por pedido:**

  - **Qué hace este ajuste:** Limita cuántos archivos individuales puede subir un cliente para un solo pedido.
  - **Efecto de cambiar este ajuste:**
    - *Cuando se cambia:* Se impedirá a los clientes subir más archivos una vez que alcancen este límite para un pedido dado.
  - **Valor recomendado:** `5` (o superior si se esperan muchos archivos)
  - **Escenario / ejemplo de comerciante:** Si un cliente está pidiendo 10 artículos personalizados diferentes, y cada uno necesita un archivo, podría establecer esto en `10` o `20`. Si generalmente solo se necesitan uno o dos archivos, un número menor evita el desorden.
- **Número máximo de archivos por producto:**

  - **Qué hace este ajuste:** Limita cuántos archivos individuales puede subir un cliente para un solo producto.
  - **Efecto de cambiar este ajuste:**
    - *Cuando se cambia:* Se impedirá a los clientes subir más archivos una vez que alcancen este límite para un producto dado.
  - **Valor recomendado:** `1` (si cada producto necesita un diseño) o `5` (si se necesitan múltiples ángulos/versiones)
  - **Escenario / ejemplo de comerciante:** Para un retrato personalizado, podría permitir `3` archivos (fotos de referencia frontal, lateral, trasera). Para una impresión de logotipo simple, `1` archivo es suficiente.
- **Número máximo de archivos por carrito:**

  - **Qué hace este ajuste:** Limita cuántos archivos individuales puede subir un cliente para todo el carrito de compras.
  - **Efecto de cambiar este ajuste:**
    - *Cuando se cambia:* Se impedirá a los clientes subir más archivos una vez que alcancen este límite para el carrito.
  - **Valor recomendado:** `5` (o superior si se esperan muchos archivos generales)
  - **Escenario / ejemplo de comerciante:** Si un cliente está subiendo un documento de instrucciones generales que se aplica a todo el carrito, podría establecer esto en `1`.
- **Mostrar formulario de carga en la página del producto:**

  - **Qué hace este ajuste:** Controla dónde aparece el formulario de carga en la página del producto.
  - **Efecto de cambiar este ajuste:**
    - *Cuando se establece en 'En pestaña de producto':* El formulario de carga aparecerá dentro de una nueva pestaña en la página del producto (por ejemplo, junto a "Descripción" o "Ficha técnica").
    - *Cuando se establece en 'Debajo de la descripción del producto':* El formulario de carga aparecerá directamente debajo de la descripción principal del producto.
    - *Cuando se establece en 'Debajo del precio del producto':* El formulario de carga aparecerá cerca del precio del producto, generalmente encima del botón "Añadir al carrito".
  - **Valor recomendado:** 'En pestaña de producto' (para una visualización menos intrusiva) o 'Debajo del precio del producto' (para alta visibilidad)
  - **Escenario / ejemplo de comerciante:** Para un producto donde la carga de archivos es crítica, colocarlo "Debajo del precio del producto" lo hace muy visible. Para cargas menos críticas, una "pestaña de producto" mantiene limpia la información principal del producto.
- **Mostrar formulario de carga en la página del carrito:**

  - **Qué hace este ajuste:** Controla dónde aparece el formulario de carga en la página del carrito de compras.
  - **Efecto de cambiar este ajuste:**
    - *Cuando se establece en 'En bloque de resumen':* El formulario de carga aparecerá dentro del área principal de resumen del carrito.
    - *Cuando se establece en 'Debajo del resumen del carrito':* El formulario de carga aparecerá debajo de todo el resumen del carrito.
  - **Valor recomendado:** 'Debajo del resumen del carrito' (a menudo proporciona más espacio)
  - **Escenario / ejemplo de comerciante:** Si los clientes necesitan subir un archivo general para todo el pedido, colocarlo claramente en la página del carrito asegura que no lo pasen por alto antes de pagar.
- **Mostrar formulario de carga en la página de historial de pedidos:**

  - **Qué hace este ajuste:** Controla dónde aparece el formulario de carga en la página de detalles del pedido individual del cliente.
  - **Efecto de cambiar este ajuste:**
    - *Cuando se establece en 'En bloque de detalles del pedido':* El formulario de carga aparecerá dentro de la sección principal de detalles del pedido.
    - *Cuando se establece en 'Debajo de los detalles del pedido':* El formulario de carga aparecerá debajo de los detalles del pedido.
  - **Valor recomendado:** 'En bloque de detalles del pedido' (para una asociación más cercana con el pedido)
  - **Escenario / ejemplo de comerciante:** Después de que un cliente realiza un pedido, puede encontrar fácilmente la opción de carga en su página de historial de pedidos para añadir archivos faltantes.
- **Mostrar formulario de carga en la página de mi cuenta:**

  - **Qué hace este ajuste:** Controla si aparece un enlace dedicado "Mis archivos" en el panel de control "Mi cuenta" del cliente.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está habilitado:* Aparecerá un enlace que lleva a una página donde los clientes pueden gestionar archivos generales.
    - *Cuando está deshabilitado:* El enlace no aparecerá.
  - **Valor recomendado:** NO (a menos que haya habilitado "Permitir a los clientes subir archivos a la cuenta del cliente" y necesite esta función)
  - **Escenario / ejemplo de comerciante:** Si desea que los clientes tengan un lugar central para todos sus archivos subidos, independientemente de pedidos específicos, habilite esto.
- **Mostrar formulario de carga en el pie de página:**

  - **Qué hace este ajuste:** Añade un enlace al gestor de carga de archivos en el pie de página de su tienda.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está habilitado:* Aparecerá un enlace en el pie de página, proporcionando otro punto de acceso al gestor de archivos.
    - *Cuando está deshabilitado:* No hay enlace en el pie de página.
  - **Valor recomendado:** NO (a menos que desee una alta visibilidad para el gestor de archivos)
  - **Escenario / ejemplo de comerciante:** Si la carga de archivos es una parte central de su negocio, un enlace en el pie de página puede hacerlo fácilmente accesible desde cualquier página.
- **Mostrar formulario de carga en la columna izquierda:**

  - **Qué hace este ajuste:** Añade un enlace al gestor de carga de archivos en la columna izquierda de su tienda.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está habilitado:* Aparecerá un enlace en la columna izquierda.
    - *Cuando está deshabilitado:* No hay enlace en la columna izquierda.
  - **Valor recomendado:** NO (a menos que desee una alta visibilidad para el gestor de archivos)
  - **Escenario / ejemplo de comerciante:** Similar al pie de página, esto proporciona otro punto de acceso prominente.
- **Mostrar formulario de carga en la columna derecha:**

  - **Qué hace este ajuste:** Añade un enlace al gestor de carga de archivos en la columna derecha de su tienda.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está habilitado:* Aparecerá un enlace en la columna derecha.
    - *Cuando está deshabilitado:* No hay enlace en la columna derecha.
  - **Valor recomendado:** NO (a menos que desee una alta visibilidad para el gestor de archivos)
  - **Escenario / ejemplo de comerciante:** Similar al pie de página y la columna izquierda, esto proporciona otro punto de acceso prominente.
- **Enviar correo electrónico al cliente sobre nuevo archivo:**

  - **Qué hace este ajuste:** Controla si se envía una notificación por correo electrónico al cliente cuando un administrador sube un nuevo archivo a su pedido.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está habilitado:* Los clientes reciben una notificación por correo electrónico.
    - *Cuando está deshabilitado:* No se envía ninguna notificación por correo electrónico.
  - **Valor recomendado:** SÍ (para una buena comunicación con el cliente)
  - **Escenario / ejemplo de comerciante:** Si sube una prueba de diseño para que el cliente la revise, se le notificará por correo electrónico.
- **Enviar correo electrónico al propietario de la tienda sobre nuevo archivo:**

  - **Qué hace este ajuste:** Controla si se envía una notificación por correo electrónico al propietario de la tienda (o al correo electrónico de la tienda configurado) cuando un cliente sube un nuevo archivo.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está habilitado:* Usted (el propietario de la tienda) recibe una notificación por correo electrónico.
    - *Cuando está deshabilitado:* No se envía ninguna notificación por correo electrónico.
  - **Valor recomendado:** SÍ (altamente recomendado para un procesamiento oportuno)
  - **Escenario / ejemplo de comerciante:** Un cliente sube un archivo de diseño crítico. Usted recibe un correo electrónico inmediatamente, lo que le permite comenzar a procesar el pedido sin demora.
- **Adjuntar archivos al correo electrónico de confirmación de pedido:**

  - **Qué hace este ajuste:** Determina si los archivos subidos por el cliente se adjuntan al correo electrónico de confirmación de pedido estándar de PrestaShop.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está habilitado:* Los archivos se incluirán como adjuntos en el correo electrónico de confirmación de pedido enviado al cliente.
    - *Cuando está deshabilitado:* Los archivos no se adjuntan al correo electrónico.
  - **Valor recomendado:** NO (a menos que los archivos sean pequeños y pocos, ya que los archivos adjuntos grandes pueden causar problemas de entrega de correo electrónico)
  - **Escenario / ejemplo de comerciante:** Si los clientes suben archivos muy pequeños y no críticos, podría habilitar esto. Para archivos más grandes o numerosos, es mejor que los clientes los descarguen desde su cuenta para evitar problemas con el servidor de correo electrónico.
- **Adjuntar archivos al correo electrónico de atención al cliente:**

  - **Qué hace este ajuste:** Determina si los archivos subidos por el cliente se adjuntan al correo electrónico enviado al cliente cuando un administrador sube un nuevo archivo.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está habilitado:* Los archivos se incluirán como adjuntos en el correo electrónico.
    - *Cuando está deshabilitado:* Los archivos no se adjuntan al correo electrónico.
  - **Valor recomendado:** NO (similar a la confirmación de pedido, evite archivos adjuntos grandes)
  - **Escenario / ejemplo de comerciante:** Si sube una pequeña prueba para el cliente, podría habilitar esto. Para archivos más grandes, diríjalos a descargar desde su cuenta.
- **Adjuntar archivos al correo electrónico del propietario de la tienda:**

  - **Qué hace este ajuste:** Determina si los archivos subidos por el cliente se adjuntan al correo electrónico enviado al propietario de la tienda cuando un cliente sube un nuevo archivo.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está habilitado:* Los archivos se incluirán como adjuntos en la notificación por correo electrónico que reciba.
    - *Cuando está deshabilitado:* Los archivos no se adjuntan al correo electrónico.
  - **Valor recomendado:** NO (a menos que los archivos sean pequeños y pocos, ya que los archivos adjuntos grandes pueden saturar su bandeja de entrada)
  - **Escenario / ejemplo de comerciante:** Si prefiere descargar archivos directamente desde el back office, deshabilite esto. Si solo espera archivos muy pequeños y los quiere inmediatamente en su bandeja de entrada, habilítelo.
- **Habilitar comentarios para archivos:**

  - **Qué hace este ajuste:** Permite a los clientes y administradores añadir comentarios a cada archivo subido.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está habilitado:* Aparecerá un campo de texto junto a cada archivo para añadir notas o instrucciones.
    - *Cuando está deshabilitado:* No habrá campos de comentarios disponibles.
  - **Valor recomendado:** SÍ (para una mejor comunicación y contexto)
  - **Escenario / ejemplo de comerciante:** Un cliente sube un logotipo y añade un comentario: "Use este logotipo, pero por favor cambie el color a azul". Esto proporciona un contexto crucial.
- **Habilitar comentarios para carritos:**

  - **Qué hace este ajuste:** Permite a los clientes añadir un comentario general a su carrito de compras.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está habilitado:* Aparecerá un campo de texto en la página del carrito para comentarios generales del carrito.
    - *Cuando está deshabilitado:* No hay campo de comentario general del carrito.
  - **Valor recomendado:** SÍ (útil para instrucciones generales)
  - **Escenario / ejemplo de comerciante:** Un cliente podría añadir un comentario como: "Por favor, asegúrese de que todos los artículos estén envueltos para regalo juntos".
- **Habilitar comentarios para pedidos:**

  - **Qué hace este ajuste:** Permite a los clientes añadir un comentario general a su pedido.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está habilitado:* Aparecerá un campo de texto en la página de detalles del pedido para comentarios generales del pedido.
    - *Cuando está deshabilitado:* No hay campo de comentario general del pedido.
  - **Valor recomendado:** SÍ (útil para instrucciones post-pedido)
  - **Escenario / ejemplo de comerciante:** Un cliente podría añadir un comentario después de realizar un pedido: "Necesito que esto se entregue antes del viernes, por favor".
- **Habilitar comentarios para productos:**

  - **Qué hace este ajuste:** Permite a los clientes añadir un comentario específico a un producto.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está habilitado:* Aparecerá un campo de texto en la página del producto para comentarios específicos del producto.
    - *Cuando está deshabilitado:* No hay campo de comentario específico del producto.
  - **Valor recomendado:** SÍ (útil para instrucciones de personalización del producto)
  - **Escenario / ejemplo de comerciante:** Un cliente que pide un grabado personalizado podría añadir un comentario: "Grabar 'Feliz Cumpleaños Juan' en fuente cursiva".
- **Habilitar la pestaña "Mis archivos" en la cuenta del cliente:**

  - **Qué hace este ajuste:** Añade una pestaña dedicada "Mis archivos" al panel de control de la cuenta del cliente.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está habilitado:* Aparece una nueva pestaña, permitiendo a los clientes ver y gestionar todos sus archivos subidos en un solo lugar.
    - *Cuando está deshabilitado:* La pestaña está oculta.
  - **Valor recomendado:** SÍ (mejora la experiencia del cliente al centralizar los archivos)
  - **Escenario / ejemplo de comerciante:** Los clientes pueden encontrar fácilmente todos sus diseños, pruebas o documentos subidos en una ubicación conveniente.
- **Habilitar la pestaña "Mis archivos" en la página de historial de pedidos:**

  - **Qué hace este ajuste:** Añade una sección dedicada "Mis archivos" dentro de la página de historial de pedidos para cada pedido específico.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está habilitado:* Aparece una sección dentro de la página de detalles de cada pedido, mostrando los archivos relacionados con ese pedido específico.
    - *Cuando está deshabilitado:* Esta sección está oculta.
  - **Valor recomendado:** SÍ (crucial para la gestión de archivos específicos del pedido)
  - **Escenario / ejemplo de comerciante:** Cuando un cliente revisa un pedido anterior, puede ver inmediatamente todos los archivos que subió para ese pedido.
- **Habilitar la pestaña "Mis archivos" en la página del producto:**

  - **Qué hace este ajuste:** Añade una sección dedicada "Mis archivos" dentro de la página del producto.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está habilitado:* Aparece una sección en la página del producto, mostrando los archivos relacionados con ese producto específico.
    - *Cuando está deshabilitado:* Esta sección está oculta.
  - **Valor recomendado:** NO (a menos que tenga un caso de uso muy específico, ya que esto puede saturar las páginas de productos)
  - **Escenario / ejemplo de comerciante:** Esto podría ser útil si los clientes reordenan con frecuencia el mismo producto personalizado y necesitan consultar archivos subidos previamente para ese producto.
- **Habilitar la pestaña "Mis archivos" en la página del carrito:**

  - **Qué hace este ajuste:** Añade una sección dedicada "Mis archivos" dentro de la página del carrito.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está habilitado:* Aparece una sección en la página del carrito, mostrando los archivos relacionados con los artículos en el carrito.
    - *Cuando está deshabilitado:* Esta sección está oculta.
  - **Valor recomendado:** NO (a menos que tenga un caso de uso muy específico, ya que esto puede saturar las páginas del carrito)
  - **Escenario / ejemplo de comerciante:** Si los clientes están construyendo un pedido complejo con muchos archivos, esto podría proporcionar una visión general de todos los archivos actualmente asociados con el carrito.
- **Mostrar botón de carga de archivos en la página del producto:**

  - **Qué hace este ajuste:** Controla la visibilidad del botón "Subir archivo" en las páginas de productos.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está habilitado:* El botón será visible.
    - *Cuando está deshabilitado:* El botón estará oculto.
  - **Valor recomendado:** SÍ (si permite la carga de archivos de producto)
  - **Escenario / ejemplo de comerciante:** Si desea que los clientes suban archivos para la personalización del producto, este botón debe ser visible.
- **Mostrar botón de carga de archivos en la página del carrito:**

  - **Qué hace este ajuste:** Controla la visibilidad del botón "Subir archivo" en la página del carrito.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está habilitado:* El botón será visible.
    - *Cuando está deshabilitado:* El botón estará oculto.
  - **Valor recomendado:** SÍ (si permite la carga de archivos del carrito)
  - **Escenario / ejemplo de comerciante:** Si los clientes necesitan subir un archivo general para todo su pedido, este botón debe ser visible en la página del carrito.
- **Mostrar botón de carga de archivos en la página de historial de pedidos:**

  - **Qué hace este ajuste:** Controla la visibilidad del botón "Subir archivo" en la página de detalles del pedido del cliente.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está habilitado:* El botón será visible.
    - *Cuando está deshabilitado:* El botón estará oculto.
  - **Valor recomendado:** SÍ (si permite la carga de archivos post-pedido)
  - **Escenario / ejemplo de comerciante:** Si los clientes necesitan añadir archivos después de realizar un pedido, este botón debe ser visible en su página de historial de pedidos.
- **Mostrar botón de carga de archivos en la página de mi cuenta:**

  - **Qué hace este ajuste:** Controla la visibilidad del botón "Subir archivo" en la página "Mi cuenta" del cliente.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está habilitado:* El botón será visible.
    - *Cuando está deshabilitado:* El botón estará oculto.
  - **Valor recomendado:** NO (a menos que haya habilitado "Permitir a los clientes subir archivos a la cuenta del cliente" y necesite esta función)
  - **Escenario / ejemplo de comerciante:** Si desea que los clientes suban archivos generales a su cuenta, este botón debe ser visible.
- **Mostrar botón de carga de archivos en el pie de página:**

  - **Qué hace este ajuste:** Controla la visibilidad del botón "Subir archivo" en el pie de página.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está habilitado:* El botón será visible.
    - *Cuando está deshabilitado:* El botón estará oculto.
  - **Valor recomendado:** NO (a menos que desee una alta visibilidad para el gestor de archivos)
  - **Escenario / ejemplo de comerciante:** Si la carga de archivos es una parte central de su negocio, un botón en el pie de página puede hacerlo fácilmente accesible desde cualquier página.
- **Mostrar botón de carga de archivos en la columna izquierda:**

  - **Qué hace este ajuste:** Controla la visibilidad del botón "Subir archivo" en la columna izquierda.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está habilitado:* El botón será visible.
    - *Cuando está deshabilitado:* El botón estará oculto.
  - **Valor recomendado:** NO (a menos que desee una alta visibilidad para el gestor de archivos)
  - **Escenario / ejemplo de comerciante:** Similar al pie de página, esto proporciona otro punto de acceso prominente.
- **Mostrar botón de carga de archivos en la columna derecha:**

  - **Qué hace este ajuste:** Controla la visibilidad del botón "Subir archivo" en la columna derecha.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está habilitado:* El botón será visible.
    - *Cuando está deshabilitado:* El botón estará oculto.
  - **Valor recomendado:** NO (a menos que desee una alta visibilidad para el gestor de archivos)
  - **Escenario / ejemplo de comerciante:** Similar al pie de página y la columna izquierda, esto proporciona otro punto de acceso prominente.

#### Configuración Avanzada

- **Habilitar modo de depuración:**

  - **Qué hace este ajuste:** Activa un modo especial que muestra información adicional y mensajes de error, principalmente para la resolución de problemas.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está habilitado:* Pueden aparecer mensajes de error más detallados e información de depuración en la pantalla o en los registros.
    - *Cuando está deshabilitado:* Operación normal, los errores se suprimen o se registran silenciosamente.
  - **Valor recomendado:** NO (solo habilítelo cuando solucione problemas con el soporte)
  - **Escenario / ejemplo de comerciante:** Si encuentra un problema y necesita proporcionar más información al soporte de MyPresta.eu, es posible que le pidan que habilite el modo de depuración.
- **Eliminar archivos cuando se elimina el pedido:**

  - **Qué hace este ajuste:** Elimina automáticamente todos los archivos subidos asociados cuando se elimina un pedido del back office de PrestaShop.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está habilitado:* Los archivos se eliminan permanentemente de su servidor cuando se elimina un pedido.
    - *Cuando está deshabilitado:* Los archivos permanecen en el servidor incluso si se elimina el pedido asociado.
  - **Valor recomendado:** SÍ (para mantener su servidor limpio y evitar archivos huérfanos)
  - **Escenario / ejemplo de comerciante:** Si elimina con frecuencia pedidos de prueba, habilitar esto evita que su servidor acumule archivos innecesarios.
- **Eliminar archivos cuando se elimina el producto:**

  - **Qué hace este ajuste:** Elimina automáticamente todos los archivos subidos asociados cuando se elimina un producto del back office de PrestaShop.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está habilitado:* Los archivos se eliminan permanentemente de su servidor cuando se elimina un producto.
    - *Cuando está deshabilitado:* Los archivos permanecen en el servidor incluso si se elimina el producto asociado.
  - **Valor recomendado:** SÍ (para mantener su servidor limpio y evitar archivos huérfanos)
  - **Escenario / ejemplo de comerciante:** Si elimina productos antiguos o descontinuados, esto asegura que sus archivos asociados también se limpien.
- **Eliminar archivos cuando se elimina el carrito:**

  - **Qué hace este ajuste:** Elimina automáticamente todos los archivos subidos asociados cuando se elimina un carrito del back office de PrestaShop.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está habilitado:* Los archivos se eliminan permanentemente de su servidor cuando se elimina un carrito.
    - *Cuando está deshabilitado:* Los archivos permanecen en el servidor incluso si se elimina el carrito asociado.
  - **Valor recomendado:** SÍ (para mantener su servidor limpio y evitar archivos huérfanos)
  - **Escenario / ejemplo de comerciante:** Los carritos suelen ser temporales. Habilitar esto evita que su servidor acumule archivos de carritos abandonados.
- **Eliminar archivos cuando se elimina el cliente:**

  - **Qué hace este ajuste:** Elimina automáticamente todos los archivos subidos asociados cuando se elimina una cuenta de cliente del back office de PrestaShop.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está habilitado:* Los archivos se eliminan permanentemente de su servidor cuando se elimina un cliente.
    - *Cuando está deshabilitado:* Los archivos permanecen en el servidor incluso si se elimina el cliente asociado.
  - **Valor recomendado:** SÍ (para la privacidad de los datos y la higiene del servidor)
  - **Escenario / ejemplo de comerciante:** Si un cliente solicita que se eliminen sus datos (cumplimiento del RGPD), esto asegura que sus archivos subidos también se eliminen.
- **Eliminar archivos cuando se elimina el archivo del cliente:**

  - **Qué hace este ajuste:** Cuando un administrador o cliente elimina un archivo específico, este ajuste controla si el archivo real se elimina del servidor.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está habilitado:* El archivo se elimina permanentemente del servidor.
    - *Cuando está deshabilitado:* El registro del archivo se elimina de la base de datos, pero el archivo real permanece en el servidor (huérfano).
  - **Valor recomendado:** SÍ (siempre, para evitar archivos huérfanos y ahorrar espacio en disco)
  - **Escenario / ejemplo de comerciante:** Cuando un cliente decide que ya no necesita un archivo, eliminarlo también libera espacio en el servidor.
- **Habilitar CSS personalizado:**

  - **Qué hace este ajuste:** Proporciona un área de texto donde puede añadir sus propias reglas CSS para personalizar la apariencia de los elementos del módulo.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está habilitado y se añade CSS:* Sus estilos personalizados anularán o complementarán el estilo predeterminado del módulo.
    - *Cuando está deshabilitado o vacío:* El módulo utiliza su estilo predeterminado.
  - **Valor recomendado:** NO (a menos que tenga necesidades de diseño específicas y conocimientos de CSS)
  - **Escenario / ejemplo de comerciante:** Desea cambiar el color del botón de carga para que coincida con el color principal de su marca. Añadiría reglas CSS aquí.
- **CSS personalizado:**

  - **Qué hace este ajuste:** Esta es el área de texto donde escribe o pega su código CSS personalizado.
  - **Efecto de cambiar este ajuste:** La apariencia visual de los elementos del módulo cambiará según sus reglas CSS.
  - **Valor recomendado:** Dejar vacío a menos que conozca CSS.
  - **Escenario / ejemplo de comerciante:** `button.upload-btn { background-color: #ff0000; color: white; }`

### 2.2 Pantallas de Administración Dedicadas y Vistas de Controlador

El módulo añade nuevas secciones a su back office de PrestaShop para gestionar los archivos subidos.

#### 2.2.1 Gestor de Archivos de Clientes (Back Office > Pedidos > Archivos de Clientes)

Esta pantalla proporciona un lugar centralizado para que usted vea y gestione todos los archivos subidos por sus clientes.

- **Nombre de la pantalla y ubicación del menú:** **Archivos de Clientes** (se encuentra en el menú **Pedidos** en PrestaShop 1.7/8/9. En versiones anteriores, podría estar directamente bajo el menú principal de Módulos o una pestaña personalizada).
- **Acciones y configuraciones disponibles:**
  - **Tabla de listado de archivos:** Verá una tabla que lista todos los archivos subidos. Cada fila típicamente muestra:
    - **Nombre del archivo:** El nombre del archivo subido.
    - **Cliente:** El nombre del cliente que subió el archivo (o "Invitado" si corresponde).
    - **ID del pedido:** El ID del pedido al que está asociado el archivo.
    - **Producto:** El nombre del producto si el archivo está vinculado a un producto específico.
    - **ID del carrito:** El ID del carrito al que está asociado el archivo.
    - **Fecha de subida:** Cuándo se subió el archivo.
    - **Tamaño:** El tamaño del archivo.
    - **Acciones:** Botones para **Descargar** el archivo, **Ver detalles** (incluidos los comentarios) o **Eliminar** el archivo.
  - **Filtrado y búsqueda:** Normalmente puede filtrar la lista por cliente, ID de pedido o buscar por nombre de archivo para encontrar rápidamente archivos específicos.
  - **Acciones masivas:** Opciones para seleccionar varios archivos y realizar acciones como la eliminación masiva.
- **Efecto de los cambios:**
  - **Descargar un archivo:** Guarda el archivo en su ordenador para su revisión o procesamiento.
  - **Eliminar un archivo:** Elimina el archivo de la lista y, si está configurado, de su servidor.
  - **Ver detalles:** Abre una ventana emergente o una nueva página con más información sobre el archivo, incluidos los comentarios asociados.
- **Flujo de trabajo recomendado para la gestión diaria de la tienda:**
  1. Revise regularmente esta sección, especialmente si recibe notificaciones por correo electrónico de nuevas cargas.
  2. Utilice los filtros para encontrar rápidamente archivos para pedidos específicos que esté procesando.
  3. Descargue los archivos necesarios para producción, diseño o revisión.
  4. Añada comentarios a los archivos si necesita comunicarse con el cliente o su equipo sobre ellos.
  5. Elimine archivos antiguos o innecesarios para mantener su servidor limpio.

#### 2.2.2 Integración de la Página de Detalles del Pedido (Back Office > Pedidos > Pedidos > Ver Pedido)

El módulo también se integra directamente en la página estándar de detalles del pedido de PrestaShop.

- **Nombre de la pantalla y ubicación del menú:** Cuando vea cualquier pedido específico en **Back Office > Pedidos > Pedidos**, encontrará una nueva sección o pestaña relacionada con "Archivos de Clientes" o "Archivos Subidos".
- **Acciones y configuraciones disponibles:**
  - **Archivos para este pedido:** Una lista de todos los archivos subidos específicamente para el pedido actual por el cliente o por un administrador.
  - **Subir nuevo archivo:** Una opción para subir un archivo usted mismo como administrador, asociándolo directamente con este pedido. Esto es útil para subir pruebas, diseños finales o documentos internos.
  - **Añadir comentarios:** Puede añadir comentarios a archivos individuales o un comentario general para el pedido.
  - **Descargar/Eliminar:** Opciones para descargar o eliminar archivos individuales asociados con este pedido.
- **Efecto de los cambios:**
  - **Subir un archivo como administrador:** El archivo pasa a formar parte de los adjuntos del pedido, visible para el cliente en su historial de pedidos (si está configurado).
  - **Añadir comentarios:** Proporciona contexto para el archivo o pedido, visible para el cliente y otros administradores.
- **Flujo de trabajo recomendado para la gestión diaria de la tienda:**
  1. Al procesar un pedido que requiere archivos del cliente, navegue a la página de detalles del pedido.
  2. Revise los archivos subidos en la sección dedicada.
  3. Descargue los archivos según sea necesario para la producción.
  4. Si crea una prueba o un diseño final, súbalo aquí para que el cliente pueda acceder a él.
  5. Utilice los campos de comentarios para comunicarse con el cliente o dejar notas internas.

### 2.3 Tabla de Referencia Rápida de Configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| **Configuración del Módulo** | Habilitar módulo | SÍ | Interruptor principal para la funcionalidad del módulo. |
| | Permitir a los clientes subir archivos | SÍ | Permitir a los clientes enviar archivos. |
| | Permitir a los clientes invitados subir archivos | SÍ | Permitir a los usuarios no registrados subir archivos. |
| | Permitir a los clientes eliminar archivos | NO | Evitar que los clientes eliminen archivos. |
| | Permitir a los clientes descargar archivos | SÍ | Permitir a los clientes recuperar sus archivos. |
| | Permitir a los clientes subir archivos a pedidos | SÍ | Habilitar cargas post-pedido a través del historial de pedidos. |
| | Permitir a los clientes subir archivos a carritos | SÍ | Habilitar cargas en la página del carrito de compras. |
| | Permitir a los clientes subir archivos a productos | SÍ | Habilitar cargas en páginas de productos individuales. |
| | Permitir a los clientes subir archivos a la cuenta del cliente | NO | Habilitar el almacenamiento general de archivos en "Mi cuenta". |
| | Forzar a los clientes a subir archivos a pedidos | NO | Hacer que la carga de archivos sea obligatoria para completar el pedido. |
| | Forzar a los clientes a subir archivos a productos | NO | Hacer que la carga de archivos sea obligatoria para añadir el producto al carrito. |
| | Forzar a los clientes a subir archivos a carritos | NO | Hacer que la carga de archivos sea obligatoria para proceder desde el carrito. |
| | Extensiones de archivo permitidas | `jpg,jpeg,png,gif,pdf,doc,docx,xls,xlsx,txt` | Restringir tipos de archivo por seguridad y usabilidad. |
| | Tamaño máximo de archivo (MB) | `10` | Limitar el tamaño de archivo individual. |
| | Número máximo de archivos por pedido | `5` | Limitar archivos por pedido. |
| | Número máximo de archivos por producto | `1` | Limitar archivos por producto. |
| | Número máximo de archivos por carrito | `5` | Limitar archivos por carrito. |
| | Mostrar formulario de carga en la página del producto | 'En pestaña de producto' o 'Debajo del precio del producto' | Posición del formulario de carga en la página del producto. |
| | Mostrar formulario de carga en la página del carrito | 'Debajo del resumen del carrito' | Posición del formulario de carga en la página del carrito. |
| | Mostrar formulario de carga en la página de historial de pedidos | 'En bloque de detalles del pedido' | Posición del formulario de carga en la página de historial de pedidos. |
| | Mostrar formulario de carga en la página de mi cuenta | NO | Mostrar/ocultar enlace "Mis archivos" en la cuenta del cliente. |
| | Mostrar formulario de carga en el pie de página | NO | Mostrar/ocultar enlace "Mis archivos" en el pie de página. |
| | Mostrar formulario de carga en la columna izquierda | NO | Mostrar/ocultar enlace "Mis archivos" en la columna izquierda. |
| | Mostrar formulario de carga en la columna derecha | NO | Mostrar/ocultar enlace "Mis archivos" en la columna derecha. |
| | Enviar correo electrónico al cliente sobre nuevo archivo | SÍ | Notificar al cliente cuando el administrador sube un archivo. |
| | Enviar correo electrónico al propietario de la tienda sobre nuevo archivo | SÍ | Notificar al propietario de la tienda cuando el cliente sube un archivo. |
| | Adjuntar archivos al correo electrónico de confirmación de pedido | NO | Adjuntar archivos subidos a la confirmación del pedido. |
| | Adjuntar archivos al correo electrónico de atención al cliente | NO | Adjuntar archivos subidos al correo electrónico de atención al cliente. |
| | Adjuntar archivos al correo electrónico del propietario de la tienda | NO | Adjuntar archivos subidos a la notificación del propietario de la tienda. |
| | Habilitar comentarios para archivos | SÍ | Permitir comentarios en archivos individuales. |
| | Habilitar comentarios para carritos | SÍ | Permitir comentarios generales en carritos. |
| | Habilitar comentarios para pedidos | SÍ | Permitir comentarios generales en pedidos. |
| | Habilitar comentarios para productos | SÍ | Permitir comentarios en productos individuales. |
| | Habilitar la pestaña "Mis archivos" en la cuenta del cliente | SÍ | Mostrar la pestaña dedicada "Mis archivos" en la cuenta del cliente. |
| | Habilitar la pestaña "Mis archivos" en la página de historial de pedidos | SÍ | Mostrar la sección de archivos en la página de historial de pedidos. |
| | Habilitar la pestaña "Mis archivos" en la página del producto | NO | Mostrar la sección de archivos en la página del producto. |
| | Habilitar la pestaña "Mis archivos" en la página del carrito | NO | Mostrar la sección de archivos en la página del carrito. |
| | Mostrar botón de carga de archivos en la página del producto | SÍ | Controlar la visibilidad del botón de carga en la página del producto. |
| | Mostrar botón de carga de archivos en la página del carrito | SÍ | Controlar la visibilidad del botón de carga en la página del carrito. |
| | Mostrar botón de carga de archivos en la página de historial de pedidos | SÍ | Controlar la visibilidad del botón de carga en la página de historial de pedidos. |
| | Mostrar botón de carga de archivos en la página de mi cuenta | NO | Controlar la visibilidad del botón de carga en la página de mi cuenta. |
| | Mostrar botón de carga de archivos en el pie de página | NO | Controlar la visibilidad del botón de carga en el pie de página. |
| | Mostrar botón de carga de archivos en la columna izquierda | NO | Controlar la visibilidad del botón de carga en la columna izquierda. |
| | Mostrar botón de carga de archivos en la columna derecha | NO | Controlar la visibilidad del botón de carga en la columna derecha. |
| **Configuración Avanzada** | Habilitar modo de depuración | NO | Mostrar mensajes de error detallados. |
| | Eliminar archivos cuando se elimina el pedido | SÍ | Eliminar archivos cuando se elimina el pedido asociado. |
| | Eliminar archivos cuando se elimina el producto | SÍ | Eliminar archivos cuando se elimina el producto asociado. |
| | Eliminar archivos cuando se elimina el carrito | SÍ | Eliminar archivos cuando se elimina el carrito asociado. |
| | Eliminar archivos cuando se elimina el cliente | SÍ | Eliminar archivos cuando se elimina el cliente asociado. |
| | Eliminar archivos cuando se elimina el archivo del cliente | SÍ | Eliminar el archivo real del servidor cuando se elimina. |
| | Habilitar CSS personalizado | NO | Activar la entrada de CSS personalizado. |
| | CSS personalizado | Dejar vacío | Área de texto para reglas CSS personalizadas. |

## 3. Solución de Problemas del Comerciante y Preguntas Frecuentes (FAQ)

**P1: Mis clientes no pueden subir archivos o reciben un mensaje de error.**
R1:

- **Verificar el estado del módulo:** Asegúrese de que "Habilitar módulo" y "Permitir a los clientes subir archivos" estén configurados en SÍ en la configuración del módulo.
- **Tipo y tamaño de archivo:** Verifique que el tipo de archivo (extensión) y el tamaño estén dentro de los límites de "Extensiones de archivo permitidas" y "Tamaño máximo de archivo" que ha establecido.
- **Límites del servidor:** Su proveedor de alojamiento podría tener límites de carga de PHP más bajos (`upload_max_filesize`, `post_max_size` en `php.ini`) que la configuración de su módulo. Contacte a su proveedor de alojamiento o webmaster para aumentarlos si es necesario.
- **Permisos:** Asegúrese de que el directorio de carga del módulo (generalmente `modules/orderfiles/uploads/`) tenga permisos de escritura (por ejemplo, 755 o 777, aunque 777 generalmente no se recomienda por seguridad).
- **Modo de depuración:** Habilite temporalmente el "Modo de depuración" en la configuración avanzada del módulo y verifique si hay mensajes de error específicos.

**P2: El formulario de carga no aparece en mi página de producto/carrito/pedido.**
R2:

- **Configuración del módulo:** Vuelva a verificar la configuración "Mostrar formulario de carga en..." para la página específica (producto, carrito, historial de pedidos) en la configuración del módulo.
- **Conflictos de hooks:** Otro módulo podría estar interfiriendo con los hooks de visualización. Intente deshabilitar temporalmente otros módulos que modifiquen las páginas de productos, carritos o pedidos para ver si aparece el formulario.
- **Compatibilidad del tema:** Los temas personalizados podrían no renderizar correctamente los hooks estándar de PrestaShop. Si está utilizando un tema personalizado, es posible que necesite que un webmaster integre manualmente los hooks del módulo en los archivos de su tema.
- **Caché:** Borre la caché de su PrestaShop (Parámetros avanzados > Rendimiento > Borrar caché) y la caché de su navegador.

**P3: No recibo notificaciones por correo electrónico cuando los clientes suben archivos.**
R3:

- **Configuración del módulo:** Asegúrese de que "Enviar correo electrónico al propietario de la tienda sobre nuevo archivo" esté configurado en SÍ.
- **Correo electrónico de la tienda:** Verifique que la dirección de correo electrónico de su tienda (`PS_SHOP_EMAIL` en Parámetros avanzados > Correo electrónico) esté configurada correctamente y funcione.
- **Configuración de correo electrónico:** Verifique la configuración de correo electrónico de su PrestaShop (Parámetros avanzados > Correo electrónico) y asegúrese de que los correos electrónicos se envíen correctamente (por ejemplo, intente enviar un correo electrónico de prueba).
- **Carpeta de spam:** Revise su carpeta de spam o correo no deseado para las notificaciones.
- **Servidor de correo:** La función de correo de su servidor podría estar mal configurada. Consulte a su proveedor de alojamiento.

**P4: ¿Cómo traduzco el texto del módulo a otros idiomas?**
R4:

- En su back office de PrestaShop, navegue a **Internacional > Traducciones**.
- Seleccione "Traducciones de módulos instalados".
- Elija su tema, el idioma al que desea traducir y luego seleccione "Cargador de imágenes de pedidos" de la lista de módulos.
- Luego podrá traducir todas las cadenas de texto visibles del módulo.

**P5: Mis archivos subidos no se eliminan cuando elimino un pedido/producto/cliente.**
R5:

- **Configuración del módulo:** Asegúrese de que la configuración correspondiente "Eliminar archivos cuando..." (por ejemplo, "Eliminar archivos cuando se elimina el pedido") esté configurada en SÍ en la configuración avanzada del módulo.
- **Eliminación manual:** Si estas configuraciones estaban deshabilitadas, es posible que se hayan acumulado archivos. Es posible que deba limpiar manualmente el directorio `modules/orderfiles/uploads/` en su servidor para archivos antiguos y huérfanos.

## 4. Guía para Desarrolladores y Webmasters (Arquitectura Técnica y Mapa de Código)

### 4.1 Resumen de la Arquitectura

El módulo "Cargador de imágenes de pedidos" sigue una arquitectura de módulo estándar de PrestaShop, aprovechando los principios MVC. Extiende la clase `Module` para su funcionalidad principal y utiliza `ModuleFrontController` y `AdminController` para manejar las solicitudes del front-office y back-office, respectivamente. Las cargas de archivos se gestionan a través de controladores dedicados y JavaScript, asegurando una experiencia de usuario fluida. La configuración se almacena en `ps_configuration`, y los datos personalizados (registros de archivos) se gestionan a través de la interacción directa con la base de datos o, potencialmente, un `ObjectModel` personalizado (aunque no se listó explícitamente ninguno en el inventario, el módulo probablemente utiliza SQL directo para los registros de archivos).

### 4.2 Controladores (`controllers/`)

#### Controladores del Front-Office

Estos controladores gestionan las interacciones del cliente y la gestión de archivos en la tienda.

- `controllers/front/customerfiles.php`
  - **Nombre de la clase y clase padre:** `OrderFilesCustomerfilesModuleFrontController` que extiende `ModuleFrontController`
  - **Responsabilidad:** Gestiona la sección "Mis archivos" del cliente, mostrando una lista de sus archivos subidos, permitiéndoles verlos, descargarlos y, potencialmente, eliminarlos. Probablemente maneja solicitudes AJAX para operaciones de archivos dentro de este contexto.
- `controllers/front/download.php`
  - **Nombre de la clase y clase padre:** `OrderFilesDownloadModuleFrontController` que extiende `ModuleFrontController`
  - **Responsabilidad:** Gestiona descargas seguras de archivos. Verifica los permisos del usuario (por ejemplo, si el archivo pertenece al cliente que ha iniciado sesión o si el usuario es un administrador) antes de servir el archivo, evitando el acceso no autorizado.
- `controllers/front/filesmanager.php`
  - **Nombre de la clase y clase padre:** `OrderFilesFilesmanagerModuleFrontController` que extiende `ModuleFrontController`
  - **Responsabilidad:** Este es probablemente un controlador central para la interfaz principal de gestión de archivos, potencialmente utilizado para cargas de archivos generales no vinculadas a un pedido/producto específico, o como un centro para todos los archivos del cliente.
- `controllers/front/index.php`
  - **Nombre de la clase y clase padre:** `OrderFilesIndexModuleFrontController` que extiende `ModuleFrontController`
  - **Responsabilidad:** Un controlador frontal de marcador de posición o predeterminado. En PrestaShop, `index.php` en un directorio de controlador a menudo sirve como un respaldo o una simple redirección.
- `controllers/front/myfiles.php`
  - **Nombre de la clase y clase padre:** `OrderFilesMyfilesModuleFrontController` que extiende `ModuleFrontController`
  - **Responsabilidad:** Similar a `customerfiles.php`, este controlador probablemente gestiona la sección "Mis archivos" en la cuenta del cliente, proporcionando la interfaz para ver y gestionar archivos personales.
- `controllers/front/thumb.php`
  - **Nombre de la clase y clase padre:** `OrderFilesThumbModuleFrontController` que extiende `ModuleFrontController`
  - **Responsabilidad:** Genera y sirve miniaturas para archivos de imagen subidos, mejorando el rendimiento y la visualización en los listados de archivos.
- `controllers/front/upload.php`
  - **Nombre de la clase y clase padre:** `OrderFilesUploadModuleFrontController` que extiende `ModuleFrontController`
  - **Responsabilidad:** El controlador principal para gestionar todas las solicitudes de carga de archivos desde el front office (página de producto, página de carrito, historial de pedidos, "Mis archivos"). Procesa el archivo subido, valida su tipo y tamaño, lo almacena en el servidor y registra sus detalles en la base de datos. Probablemente gestiona las respuestas AJAX para el progreso y el estado de la carga.

#### Controladores de Administración del Back-Office

Estos controladores proporcionan la interfaz administrativa para gestionar los archivos subidos.

- `controllers/admin/customerFiles.php`
  - **Nombre de la clase y clase padre:** `AdminCustomerFilesController` que extiende `ModuleAdminController`
  - **Nombre de la pestaña y entidad gestionada:** "Archivos de Clientes" (bajo el menú Pedidos). Gestiona el listado, visualización, descarga y eliminación de todos los archivos subidos por los clientes en toda la tienda. Proporciona una vista de cuadrícula completa con opciones de filtrado.
- `controllers/admin/index.php`
  - **Nombre de la clase y clase padre:** `AdminOrderFilesIndexController` que extiende `ModuleAdminController`
  - **Nombre de la pestaña y entidad gestionada:** Similar al `index.php` del front-office, este podría ser un marcador de posición o una simple redirección para la sección de administración. La gestión principal de archivos la maneja `AdminCustomerFilesController`.

### 4.3 Clases y Modelos Principales (`classes/`)

El inventario proporcionado indica que no hay clases personalizadas en el directorio `classes/`. Esto sugiere que el módulo podría estar utilizando consultas directas a la base de datos para la gestión de archivos o almacenando la información de los archivos directamente en `ps_configuration` o en una tabla personalizada sin un `ObjectModel` dedicado. Dada la complejidad de la gestión de archivos, es más probable que los registros de archivos se almacenen en una tabla de base de datos personalizada y se gestionen mediante SQL directo o una clase auxiliar simple dentro del archivo principal del módulo.

### 4.4 Activos JavaScript (`views/js/`)

Estos scripts mejoran la experiencia del usuario para la carga y gestión de archivos.

- `orderfiles/js/jquery.form.js`
  - **Alcance:** Front-office y Back-office (dondequiera que los formularios se envíen a través de AJAX).
  - **Descripción:** Un plugin de jQuery para enviar fácilmente formularios HTML a través de AJAX, incluyendo la carga de archivos. Maneja el seguimiento del progreso y simplifica los envíos de formularios asíncronos.
- `orderfiles/js/orders.js`
  - **Alcance:** Back-office (específicamente dentro de las páginas de detalles del pedido).
  - **Descripción:** Probablemente maneja la funcionalidad AJAX para subir archivos directamente desde la página de detalles del pedido del administrador, mostrando los archivos asociados con un pedido y gestionando los comentarios dentro del contexto del pedido.
- `orderfiles/js/script-customers.js`
  - **Alcance:** Front-office (páginas de cuenta de cliente, sección "Mis archivos").
  - **Descripción:** Gestiona los elementos interactivos dentro de la sección "Mis archivos" del cliente, incluyendo la visualización de listas de archivos, el manejo de acciones de descarga/eliminación y, potencialmente, actualizaciones AJAX para el estado o los comentarios de los archivos.
- `orderfiles/js/script.js`
  - **Alcance:** Front-office (páginas de productos, páginas de carritos, formularios de carga generales).
  - **Descripción:** El JavaScript principal del front-office para gestionar la carga de archivos. Probablemente inicializa los formularios de carga, maneja la funcionalidad de arrastrar y soltar, muestra el progreso de la carga, valida los tipos/tamaños de archivo en el lado del cliente y envía solicitudes AJAX a `upload.php`.

### 4.5 Hojas de Estilo CSS (`views/css/`)

Estas hojas de estilo controlan la presentación visual de los elementos del módulo.

- `orderfiles/css/ajaxuploader.css`
  - **Alcance:** Front-office y Back-office (dondequiera que se utilice la interfaz del cargador AJAX).
  - **Descripción:** Estilos para el widget de carga de archivos en sí, incluyendo barras de progreso, áreas de arrastrar y soltar y elementos de vista previa de archivos.
  - **Selectores de clase CSS clave:** `.ajax-uploader-container`, `.upload-drop-zone`, `.file-list`, `.progress-bar`
- `orderfiles/css/backoffice.css`
  - **Alcance:** Back-office (controladores de administración).
  - **Descripción:** Estilos específicos para las interfaces administrativas del módulo, como el listado de "Archivos de Clientes" y la integración dentro de la página de detalles del pedido.
  - **Selectores de clase CSS clave:** `.orderfiles-admin-table`, `.orderfiles-order-details-block`
- `orderfiles/css/orderfiles.css`
  - **Alcance:** Front-office (elementos generales del módulo).
  - **Descripción:** Estilos generales para los componentes del front-office del módulo, incluyendo botones, listados de archivos y secciones de comentarios en las páginas de productos, carritos e historial de pedidos.
  - **Selectores de clase CSS clave:** `.orderfiles-upload-form`, `.orderfiles-file-item`, `.orderfiles-comments`
- `orderfiles/css.css`
  - **Alcance:** Potencialmente estilos globales o de reserva.
  - **Descripción:** Esta podría ser una hoja de estilo más antigua o genérica. Los desarrolladores deben verificar su contenido para comprender su impacto específico, ya que `orderfiles.css` es más descriptiva.
  - **Selectores de clase CSS clave:** (Requiere inspección)

### 4.6 Estructura de Plantillas Smarty (`views/templates/`)

#### Plantillas de hook (`views/templates/hook/`)

Estas plantillas se renderizan a través de hooks de PrestaShop para inyectar contenido del módulo en varias partes de la tienda.

- `displayProductPageUploadFormSmall.tpl`: Renderiza un formulario de carga compacto en la página del producto.
- `filesmanager-orderhistory.tpl`: Muestra la interfaz del gestor de archivos dentro de la página de historial de pedidos del cliente.
- `force-redirect.tpl`: Una plantilla de utilidad, posiblemente utilizada para redirecciones después de ciertas acciones o para forzar la carga de archivos.
- `header.tpl`: Inyecta activos CSS/JS u otro código necesario en la sección `<head>` del front office.
- `my-account-17.tpl`: Renderiza el enlace/pestaña "Mis archivos" para los paneles de control de la cuenta de cliente de PrestaShop 1.7.x y posteriores.
- `my-account.tpl`: Renderiza el enlace/pestaña "Mis archivos" para las versiones anteriores de PrestaShop (por ejemplo, 1.6.x) de los paneles de control de la cuenta de cliente.
- `orderConfirmation.tpl`: Muestra opciones de carga de archivos o un resumen en la página de confirmación del pedido.
- `product-files-button.tpl`: Renderiza el botón "Subir archivo" en la página del producto.
- `product-files.tpl`: Muestra una lista de archivos asociados con un producto, potencialmente con opciones de carga.
- `shopping-cart-force-files-alert.tpl`: Muestra un mensaje de alerta si la carga de archivos es obligatoria en la página del carrito y no se suben archivos.
- `shopping-cart-qty-infos-alert.tpl`: Probablemente muestra una alerta relacionada con la información de cantidad en el carrito, posiblemente vinculada a la carga de archivos.
- `shopping-cart.tpl`: Integra la funcionalidad de carga de archivos o listados de archivos en la página del carrito de compras.
- `tab.tpl`: Una plantilla de pestaña genérica, posiblemente utilizada para crear nuevas pestañas en páginas de productos o en la cuenta del cliente.

#### Plantillas de administración (`views/templates/admin/`)

Estas plantillas se utilizan para las interfaces del back-office del módulo.

- `admin.tpl`: La plantilla de configuración principal para el método `getContent()` del módulo, que renderiza el formulario de configuración.
- `adminOrderDetailUpload.tpl`: Integra la interfaz de carga y gestión de archivos directamente en la página de detalles del pedido de PrestaShop en el back office.
- `boscript.tpl`: Contiene código JavaScript específicamente para el back office, probablemente incluido en las páginas de administración.
- `bulk-delete-files.tpl`: Plantilla para una interfaz o confirmación de eliminación masiva de archivos.
- `comments_cartfiles.tpl`: Renderiza la sección de comentarios para archivos asociados con un carrito.
- `comments_orderfiles.tpl`: Renderiza la sección de comentarios para archivos asociados con un pedido.
- `comments_productfiles.tpl`: Renderiza la sección de comentarios para archivos asociados con un producto.
- `customerfilesmanager.tpl`: La plantilla principal para `AdminCustomerFilesController`, que muestra la cuadrícula de todos los archivos subidos.
- `_configure/helpers/list/list_action_details.tpl`: Una plantilla auxiliar para mostrar un botón de acción "detalles" en una lista.
- `_configure/helpers/list/list_content.tpl`: Una plantilla auxiliar para renderizar las filas de contenido de una lista.
- `_configure/prestashopbug/helpers/list/*.tpl`: Estas plantillas parecen ser anulaciones o correcciones específicas para los ayudantes de lista predeterminados de PrestaShop, posiblemente para abordar problemas de compatibilidad o personalizar la visualización de la lista para las cuadrículas de administración del módulo. Incluyen `list.tpl`, `list_action_delete.tpl`, `list_action_details.tpl`, `list_content.tpl`, `list_footer.tpl`, `list_header.tpl`.

#### Plantillas del Front-office (`views/templates/front/`)

Estas son plantillas independientes para páginas dedicadas del front-office.

- `access-denied.tpl`: Muestra un mensaje cuando un cliente intenta acceder a un archivo o página sin los permisos adecuados.
- `customerfilesmanager.tpl`: La plantilla principal para la página "Mis archivos" del cliente, que muestra sus archivos subidos.
- `filesmanager.tpl`: Una plantilla de gestor de archivos general, potencialmente utilizada para una página de gestión de archivos más amplia.
- `my-files.tpl`: Otra plantilla para la sección "Mis archivos", probablemente similar a `customerfilesmanager.tpl` o una vista específica dentro de ella.

### 4.7 Esquema de la Base de Datos y Mapa de Hooks

#### Tablas de la Base de Datos

El módulo probablemente crea al menos una tabla de base de datos personalizada para almacenar información sobre los archivos subidos.

- **`ps_orderfiles_files` (o similar):**
  - `id_order_file` (Clave Primaria)
  - `id_customer` (Enlace a `ps_customer`)
  - `id_order` (Enlace a `ps_order`)
  - `id_cart` (Enlace a `ps_cart`)
  - `id_product` (Enlace a `ps_product`)
  - `filename` (Nombre original del archivo)
  - `filepath` (Ruta al archivo almacenado en el servidor)
  - `file_extension`
  - `file_size`
  - `comment` (Comentarios de usuario/administrador)
  - `date_add`
  - `date_upd`
  - `is_admin_upload` (Booleano, para distinguir cargas de clientes de cargas de administradores)
- **`ps_configuration`:** Almacena todas las configuraciones del módulo (por ejemplo, `OF_ALLOW_CUSTOMER_UPLOAD`, `OF_MAX_FILE_SIZE`, `OF_ALLOWED_EXTENSIONS`, `OF_CEMAIL_CUSTOMER`, `OF_CEMAIL_ATTACH`, etc.). Estas claves tienen el prefijo `OF_` (Order Files).

#### Tabla de Hooks Registrados

| Nombre del Hook | Momento de Ejecución | Propósito Técnico |
| --- | --- | --- |
| `displayHeader` | En la sección `<head>` de cada página del front-office. | Inyecta los archivos CSS (`orderfiles.css`, `ajaxuploader.css`) y JavaScript (`jquery.form.js`, `script.js`, `script-customers.js`) del módulo. |
| `displayProductAdditionalInfo` (o hook similar de página de producto) | En la página del producto, típicamente debajo de los detalles principales del producto. | Renderiza `product-files.tpl` o `displayProductPageUploadFormSmall.tpl` para cargas de archivos específicas del producto. |
| `displayShoppingCartFooter` (o hook similar de página de carrito) | En la parte inferior del resumen del carrito de compras. | Renderiza `shopping-cart.tpl` para cargas de archivos a nivel de carrito y alertas. |
| `displayCustomerAccount` | En el panel de control "Mi cuenta" del cliente. | Renderiza `my-account.tpl` o `my-account-17.tpl` para añadir el enlace "Mis archivos". |
| `displayMyAccountBlock` | En el panel de control "Mi cuenta" del cliente (alternativa para algunos temas). | Renderiza `my-account.tpl` o `my-account-17.tpl` para añadir el enlace "Mis archivos". |
| `displayOrderConfirmation` | En la página de confirmación del pedido después de una compra exitosa. | Renderiza `orderConfirmation.tpl` para mostrar opciones de carga o resúmenes de archivos. |
| `displayOrderDetail` | En la página de detalles del pedido del cliente en "Mi cuenta". | Renderiza `filesmanager-orderhistory.tpl` para mostrar archivos relacionados con el pedido específico. |
| `displayLeftColumn` | En la columna izquierda del front office. | Renderiza `tab.tpl` (o similar) para mostrar un enlace al gestor de archivos. |
| `displayRightColumn` | En la columna derecha del front office. | Renderiza `tab.tpl` (o similar) para mostrar un enlace al gestor de archivos. |
| `displayFooter` | En el pie de página del front office. | Renderiza `tab.tpl` (o similar) para mostrar un enlace al gestor de archivos. |
| `actionObjectOrderAddAfter` | Después de que un nuevo pedido se añade correctamente a la base de datos. | Activa notificaciones por correo electrónico al propietario de la tienda si un cliente subió archivos durante el proceso de compra. |
| `actionObjectOrderDeleteAfter` | Después de que un pedido se elimina de la base de datos. | Activa la eliminación de archivos del servidor si "Eliminar archivos cuando se elimina el pedido" está habilitado. |
| `actionObjectProductDeleteAfter` | Después de que un producto se elimina de la base de datos. | Activa la eliminación de archivos del servidor si "Eliminar archivos cuando se elimina el producto" está habilitado. |
| `actionObjectCartDeleteAfter` | Después de que un carrito se elimina de la base de datos. | Activa la eliminación de archivos del servidor si "Eliminar archivos cuando se elimina el carrito" está habilitado. |
| `actionObjectCustomerDeleteAfter` | Después de que un cliente se elimina de la base de datos. | Activa la eliminación de archivos del servidor si "Eliminar archivos cuando se elimina el cliente" está habilitado. |
| `actionAdminOrdersControllerSaveAfter` | Después de que un pedido se guarda/actualiza en el back office. | Potencialmente gestiona las cargas de archivos del administrador o las actualizaciones de comentarios desde la página de detalles del pedido. |
| `actionAdminControllerSetMedia` | Cuando se carga un controlador de administración y se configuran sus activos multimedia. | Inyecta los archivos CSS (`backoffice.css`) y JavaScript (`orders.js`, `jquery.form.js`, `boscript.tpl`) del módulo para la funcionalidad del back-office. |

## 5. Soporte Oficial y Actualizaciones

Para las últimas actualizaciones del módulo, correcciones de errores y soporte técnico, consulte su cuenta de cliente en [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nuestro equipo de soporte está disponible para ayudarle con cualquier problema o pregunta relacionada con el módulo "Cargador de imágenes de pedidos".
