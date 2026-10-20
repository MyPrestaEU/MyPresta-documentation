---
title: "Carga de Archivos de Clientes - Manual del Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop 'Carga de Archivos de Clientes' de MyPresta.eu."
sidebar:
  label: "Carga de Archivos de Clientes - Manual del Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Customer Files Upload en MyPresta.eu](https://mypresta.eu/modules/ordering-process/customer-files-upload.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/ordering-process/customer-files-upload/)
>
> ---


# Carga de Archivos de Clientes

## 1. Requisitos y Compatibilidad

- **Versiones de PrestaShop Soportadas**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilidad PHP**: PHP 5.6 - 8.5
- **Requisitos de Alojamiento**: Las extensiones PHP estándar (cURL, JSON, OpenSSL) suelen ser requeridas por PrestaShop y son suficientes para este módulo. Asegúrese de que su servidor tenga suficiente espacio en disco para almacenar los archivos subidos.

## 2. Recorrido Completo por la Configuración (Cada Ajuste Agrupado por Pantalla)

### 2.1 Página de Configuración del Módulo (Back Office > Módulos > Configurar)

Esta es la pantalla de configuración principal del módulo, a la que se accede después de la instalación o haciendo clic en "Configurar" desde el Gestor de Módulos.

- **Habilitar Módulo:**

  - **Qué hace este ajuste:** Este es el interruptor maestro para activar o desactivar la funcionalidad del módulo en toda su tienda.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está habilitado:* Todas las funciones de carga de archivos, la gestión de archivos de clientes y las herramientas del back-office se activan.
    - *Cuando está deshabilitado:* Las funciones del módulo se desactivan por completo y no aparecerán formularios de carga ni secciones "Mis Archivos".
  - **Valor recomendado:** SÍ
  - **Escenario / ejemplo del comerciante:** Si está configurando el módulo por primera vez o realizando mantenimiento, podría deshabilitarlo temporalmente. De lo contrario, manténgalo habilitado para ofrecer el servicio de carga de archivos.
- **Permitir cargas en la Página de Producto:**

  - **Qué hace este ajuste:** Controla si los clientes pueden subir archivos directamente desde la página de un producto.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está habilitado:* Aparecerá un formulario de carga en las páginas de producto, permitiendo a los clientes adjuntar archivos antes de añadir el producto a su carrito.
    - *Cuando está deshabilitado:* No se verá ningún formulario de carga en las páginas de producto.
  - **Valor recomendado:** SÍ (si sus productos requieren archivos de personalización antes de la compra)
  - **Escenario / ejemplo del comerciante:** Si vende tazas personalizadas, habilitar esto permite a los clientes subir su foto directamente en la página del producto de la taza.
- **Permitir cargas en la Página del Carrito de Compras:**

  - **Qué hace este ajuste:** Determina si se muestra un área de carga en la página de resumen del carrito de compras.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está habilitado:* Los clientes pueden subir archivos generales relacionados con todo su carrito o artículos específicos antes de proceder al pago.
    - *Cuando está deshabilitado:* No se verá ningún formulario de carga en la página del carrito de compras.
  - **Valor recomendado:** SÍ (si los clientes pueden necesitar proporcionar instrucciones generales del pedido o archivos para varios artículos)
  - **Escenario / ejemplo del comerciante:** Un cliente que pide varios artículos personalizados podría subir un único documento con instrucciones generales o una guía de marca para todo el pedido.
- **Permitir cargas en la Página de Confirmación de Pedido:**

  - **Qué hace este ajuste:** Controla si los clientes pueden subir archivos inmediatamente después de realizar un pedido, en la pantalla de confirmación del pedido.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está habilitado:* Aparece un formulario de carga en la página de "Confirmación de Pedido", permitiendo a los clientes adjuntar archivos a su pedido recién realizado.
    - *Cuando está deshabilitado:* No se verá ningún formulario de carga en la página de confirmación del pedido.
  - **Valor recomendado:** SÍ (muy recomendado para la mayoría de los casos de uso)
  - **Escenario / ejemplo del comerciante:** Un cliente acaba de comprar un banner personalizado. Puede subir inmediatamente su archivo de diseño de alta resolución en la página de confirmación sin navegar a otro lugar.
- **Permitir cargas en la Cuenta del Cliente (Mis Archivos e Historial de Pedidos):**

  - **Qué hace este ajuste:** Habilita la sección "Mis Archivos" en la cuenta del cliente y permite cargas en las páginas de detalles de pedidos individuales dentro de su historial.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está habilitado:* Los clientes obtienen un área dedicada "Mis Archivos" para gestionar todas sus cargas y pueden añadir archivos a pedidos pasados específicos.
    - *Cuando está deshabilitado:* Los clientes no pueden gestionar archivos desde su cuenta y no aparecerán opciones de carga en las páginas del historial de pedidos.
  - **Valor recomendado:** SÍ (proporciona máxima flexibilidad y control al cliente)
  - **Escenario / ejemplo del comerciante:** Un cliente se da cuenta de que olvidó subir un archivo de fuente específico para su pedido de camiseta personalizada un día después. Puede iniciar sesión en su cuenta, ir al pedido y subirlo.
- **Tamaño Máximo de Archivo (MB):**

  - **Qué hace este ajuste:** Establece el límite superior para el tamaño de cada archivo individual que un cliente puede subir.
  - **Efecto de cambiar este ajuste:**
    - *Cuando se establece un valor (por ejemplo, 10):* Se impedirá a los clientes subir archivos de más de 10 MB.
    - *Cuando se establece en 0 o vacío:* El módulo normalmente se remitirá a los límites de carga de PHP de su servidor, que pueden ser muy altos o muy bajos.
  - **Valor recomendado:** 5-20 MB (ajuste según los tipos de archivo típicos; por ejemplo, las imágenes de alta resolución pueden necesitar más).
  - **Escenario / ejemplo del comerciante:** Si espera que los clientes suban fotos de alta resolución, podría establecer esto en 20 MB. Si solo se necesitan documentos pequeños, 5 MB podrían ser suficientes para ahorrar espacio en el servidor.
- **Tipos de Archivo Permitidos (separados por comas):**

  - **Qué hace este ajuste:** Especifica qué extensiones de archivo están permitidas para la carga.
  - **Efecto de cambiar este ajuste:**
    - *Cuando se establece en "jpg,png,pdf":* Solo se pueden subir archivos con estas extensiones. Cualquier otro tipo de archivo será rechazado.
    - *Cuando se deja vacío:* Se podrían permitir todos los tipos de archivo (no recomendado por seguridad).
  - **Valor recomendado:** Incluya solo los tipos que espera (por ejemplo, `jpg,jpeg,png,gif,pdf,doc,docx,xls,xlsx,txt,zip`). Evite los archivos ejecutables.
  - **Escenario / ejemplo del comerciante:** Si solo necesita archivos de diseño, podría listar `ai,eps,svg,psd,pdf,jpg,png`. Si necesita documentos, `doc,docx,pdf` sería apropiado.
- **Forzar Carga de Archivos para productos específicos (IDs de Producto):**

  - **Qué hace este ajuste:** Le permite hacer que las cargas de archivos sean obligatorias para ciertos productos. Introduzca los IDs de producto separados por comas.
  - **Efecto de cambiar este ajuste:**
    - *Cuando se introducen IDs de producto:* Si un cliente intenta añadir uno de estos productos al carrito o proceder al pago sin subir un archivo, se le pedirá que lo haga.
    - *Cuando se deja vacío:* Ningún producto tendrá cargas de archivos obligatorias.
  - **Valor recomendado:** Use solo para productos donde un archivo es absolutamente esencial para procesar el pedido.
  - **Escenario / ejemplo del comerciante:** Para un producto de "Diseño de Tarjetas de Visita Personalizadas" (ID 123), podría introducir `123`. El cliente no puede completar la compra sin subir su logotipo o resumen de diseño.
- **Notificación por Correo Electrónico al Cliente al Subir Archivo:**

  - **Qué hace este ajuste:** Controla si se envía un correo electrónico al cliente cuando sube un archivo con éxito.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está habilitado:* El cliente recibe un correo electrónico de confirmación de que su archivo ha sido recibido.
    - *Cuando está deshabilitado:* No se envía ninguna notificación por correo electrónico al cliente.
  - **Valor recomendado:** SÍ (mejora la confianza del cliente y proporciona confirmación)
  - **Escenario / ejemplo del comerciante:** Un cliente sube una foto para un regalo personalizado. Un correo electrónico confirma la carga, asegurándole que su archivo fue recibido correctamente.
- **Notificación por Correo Electrónico al Administrador al Subir Archivo:**

  - **Qué hace este ajuste:** Controla si se envía un correo electrónico al(los) administrador(es) de la tienda cuando un cliente sube un archivo.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está habilitado:* El administrador de la tienda recibe una alerta por correo electrónico, lo que le permite estar al tanto de los nuevos archivos que necesitan atención.
    - *Cuando está deshabilitado:* No se envía ninguna notificación por correo electrónico al administrador.
  - **Valor recomendado:** SÍ (esencial para el procesamiento oportuno de pedidos)
  - **Escenario / ejemplo del comerciante:** Un cliente sube un archivo de diseño. El administrador recibe un correo electrónico, lo que le impulsa a revisar el pedido y comenzar a procesar el artículo personalizado.
- **Mostrar Botón de Carga en Encabezado/Pie de Página/Columnas:**

  - **Qué hace este ajuste:** Le permite elegir dónde aparece un botón o enlace general de "Subir Archivos" en su tienda (por ejemplo, en el encabezado, pie de página o columnas laterales).
  - **Efecto de cambiar este ajuste:**
    - *Cuando se selecciona un hook:* Aparecerá un enlace o botón en esa ubicación, dirigiendo a los clientes a su sección "Mis Archivos" o a una página de carga general.
    - *Cuando se selecciona "Ninguno":* No se mostrará ningún botón de carga general fuera de las páginas de producto/carrito/pedido.
  - **Valor recomendado:** Considere `displayHeader` o `displayFooter` para un fácil acceso a "Mis Archivos" si espera cargas frecuentes.
  - **Escenario / ejemplo del comerciante:** Colocar un enlace "Mis Archivos" en el pie de página permite a los clientes que regresan acceder y gestionar rápidamente sus documentos subidos.

### 2.2 Pantallas de Administración Dedicadas y Vistas del Controlador

#### 2.2.1 Gestor de Archivos de Clientes (Back Office > Módulos > Carga de Archivos de Clientes > Archivos de Clientes)

Esta pantalla proporciona un lugar centralizado para que usted, el propietario de la tienda, vea y gestione todos los archivos subidos por sus clientes.

- **Nombre de la Pantalla y Ubicación del Menú:** Puede encontrar esto navegando a **Módulos > Gestor de módulos**, buscando "Carga de Archivos de Clientes" y haciendo clic en "Configurar". Dentro de la configuración del módulo, debería haber una pestaña o enlace etiquetado como "Archivos de Clientes" o "Gestionar Archivos". Alternativamente, podría aparecer directamente bajo el menú "Módulos" como "Archivos de Clientes".
- **Acciones y Ajustes Disponibles:**
  - **Tabla de Listado de Archivos:** Muestra una lista de todos los archivos subidos, incluyendo detalles como:
    - **Nombre del Archivo:** El nombre del archivo subido.
    - **Cliente:** El nombre del cliente que subió el archivo.
    - **ID de Pedido:** Si el archivo está vinculado a un pedido específico.
    - **Producto:** Si el archivo está vinculado a un producto específico.
    - **Fecha de Carga:** Cuándo se subió el archivo.
    - **Tamaño:** El tamaño del archivo.
    - **Acciones:** Normalmente incluye opciones para **Descargar** el archivo, **Ver Detalles** o **Eliminar** el archivo.
  - **Filtrado y Búsqueda:** Normalmente puede filtrar archivos por cliente, ID de pedido, producto o rango de fechas para encontrar rápidamente cargas específicas.
  - **Acciones Masivas:** Opciones para seleccionar varios archivos y realizar acciones como la eliminación masiva.
- **Efecto de los cambios:**
  - **Descargar un archivo:** Recupera el archivo subido por el cliente a su ordenador para su procesamiento.
  - **Eliminar un archivo:** Elimina permanentemente el archivo de su servidor y de la sección "Mis Archivos" del cliente. ¡Úselo con precaución!
- **Flujo de trabajo recomendado para la gestión diaria de la tienda:** Revise regularmente esta sección para nuevas cargas, especialmente después de recibir notificaciones por correo electrónico del administrador. Descargue los archivos necesarios para el cumplimiento del pedido y revise y elimine periódicamente los archivos antiguos o innecesarios para liberar espacio en el servidor.

#### 2.2.2 Integración de la Página de Detalles del Pedido (Back Office > Pedidos > Pedidos > Ver Pedido)

El módulo se integra directamente en sus páginas de detalles de pedidos existentes de PrestaShop.

- **Nombre de la Pantalla y Ubicación del Menú:** Cuando ve un pedido específico en su Back Office (por ejemplo, **Pedidos > Pedidos**, luego haga clic en "Ver" junto a un pedido).
- **Acciones y Ajustes Disponibles:**
  - Dentro de la página de detalles del pedido, aparecerá una nueva sección o pestaña, específicamente para "Archivos de Clientes" o "Archivos Subidos".
  - Esta sección listará todos los archivos que el cliente ha subido para *ese pedido específico*.
  - Verá los nombres de los archivos, las fechas de carga y las opciones para **Descargar** cada archivo.
  - También podría haber una opción para que el administrador **Suba un archivo** en nombre del cliente o para uso interno relacionado con el pedido.
- **Efecto de los cambios:**
  - **Descargar archivos desde aquí:** Le permite acceder rápidamente a los archivos relevantes para el pedido que está viendo actualmente, agilizando el procesamiento del pedido.
  - **Carga del Administrador:** Si está disponible, le permite añadir notas internas o archivos relacionados con el pedido directamente a la lista de archivos del pedido.
- **Flujo de trabajo recomendado para la gestión diaria de la tienda:** Al procesar un pedido que requiere archivos de clientes, navegue a la página de detalles del pedido, localice la sección "Archivos de Clientes" y descargue todos los documentos necesarios antes de comenzar la producción o el cumplimiento.

### 2.3 Tabla de Referencia Rápida de Configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| **Configuración del Módulo** | Habilitar Módulo | SÍ | Interruptor maestro para la funcionalidad del módulo. |
|  | Permitir cargas en la Página de Producto | SÍ (si es necesario) | Muestra el formulario de carga en las páginas de producto. |
|  | Permitir cargas en la Página del Carrito de Compras | SÍ (si es necesario) | Muestra el formulario de carga en la página del carrito. |
|  | Permitir cargas en la Página de Confirmación de Pedido | SÍ | Muestra el formulario de carga después de realizar el pedido. |
|  | Permitir cargas en la Cuenta del Cliente | SÍ | Habilita "Mis Archivos" y las cargas del historial de pedidos. |
|  | Tamaño Máximo de Archivo (MB) | 5-20 MB | Limita el tamaño de carga de archivos individuales. |
|  | Tipos de Archivo Permitidos | `jpg,png,pdf,...` | Restringe las extensiones de archivo por seguridad/relevancia. |
|  | Forzar Carga de Archivos para productos específicos (IDs) | Vacío (usar según sea necesario) | Hace que la carga sea obligatoria para los productos especificados. |
|  | Notificación por Correo Electrónico al Cliente | SÍ | Envía confirmación por correo electrónico al cliente al subir. |
|  | Notificación por Correo Electrónico al Administrador | SÍ | Envía alerta por correo electrónico al administrador sobre nueva carga. |
|  | Mostrar Botón de Carga en Encabezado/Pie de Página/Columnas | `displayFooter` (o según sea necesario) | Coloca un enlace general de "Subir Archivos" en el hook seleccionado. |
| **Gestor de Archivos de Clientes** | Listado de Archivos | N/A | Ver, filtrar, descargar y eliminar todos los archivos de clientes. |
|  | Acciones Masivas | N/A | Realizar acciones en varios archivos seleccionados. |
| **Página de Detalles del Pedido** | Sección de Archivos de Clientes | N/A | Ver y descargar archivos específicos del pedido actual. |

## 3. Solución de Problemas del Comerciante y Preguntas Frecuentes (FAQ)

**P1: Mis clientes no pueden ver los formularios de carga o la sección "Mis Archivos".**
R:

- **Verificar el Estado del Módulo:** Asegúrese de que el módulo esté habilitado en **Módulos > Gestor de módulos**.
- **Verificar la Configuración:** Vaya a la página de configuración del módulo y verifique que "Habilitar Módulo" esté configurado en SÍ y que las ubicaciones de carga específicas (Página de Producto, Carrito, Cuenta del Cliente) también estén habilitadas.
- **Borrar Caché:** A veces, la caché de PrestaShop puede impedir que los cambios aparezcan inmediatamente. Vaya a **Parámetros Avanzados > Rendimiento** y haga clic en "Borrar caché".
- **Compatibilidad del Tema:** Si está utilizando un tema altamente personalizado, es posible que no se esté conectando correctamente a los puntos de visualización del módulo. Contacte con el soporte de MyPresta.eu o con su desarrollador web.

**P2: Los clientes reciben un error al intentar subir archivos.**
R:

- **Verificar el Límite de Tamaño de Archivo:** Verifique el "Tamaño Máximo de Archivo (MB)" en la configuración del módulo. El archivo del cliente podría ser demasiado grande.
- **Verificar los Tipos de Archivo Permitidos:** Asegúrese de que el tipo de archivo que el cliente intenta subir esté listado en la configuración de "Tipos de Archivo Permitidos" (por ejemplo, si está subiendo un archivo `.zip`, `zip` debe estar en la lista).
- **Límites del Servidor:** Su proveedor de alojamiento web podría tener límites de carga de PHP (`upload_max_filesize`, `post_max_size`) en el lado del servidor que son más bajos que la configuración de su módulo. Es posible que deba contactar a su proveedor o ajustar su archivo `php.ini`.

**P3: No recibo notificaciones por correo electrónico cuando los clientes suben archivos.**
R:

- **Verificar la Configuración de Notificaciones por Correo Electrónico:** En la configuración del módulo, asegúrese de que "Notificación por Correo Electrónico al Administrador al Subir Archivo" esté configurado en SÍ.
- **Configuración de Correo Electrónico de PrestaShop:** Verifique que la configuración de correo electrónico de su tienda PrestaShop esté configurada correctamente y que los correos electrónicos se envíen con éxito (**Parámetros Avanzados > E-mail**). Envíe un correo electrónico de prueba desde allí.
- **Carpeta de Spam:** Revise su carpeta de spam o correo no deseado para las notificaciones.
- **Servidor de Correo:** Asegúrese de que la función de correo de su servidor esté funcionando correctamente.

**P4: ¿Cómo traduzco el texto del módulo a otros idiomas?**
R:

- Navegue a **Internacional > Traducciones** en su Back Office de PrestaShop.
- Seleccione "Traducciones de módulos instalados", elija su tema y luego seleccione "Carga de Archivos de Clientes" del menú desplegable del módulo.
- Luego podrá traducir todas las cadenas visibles utilizadas por el módulo.

**P5: ¿Dónde se almacenan los archivos subidos en mi servidor?**
R: El módulo normalmente almacena los archivos en una carpeta dedicada dentro de su instalación de PrestaShop, a menudo llamada `upload` o `orderfiles_uploads` dentro del directorio del módulo o un directorio `upload` general. Puede acceder a estos a través de FTP/SFTP, pero siempre es mejor gestionarlos a través de la interfaz del Back Office para mantener la integridad de la base de datos.

## 4. Guía para Desarrolladores y Webmasters (Arquitectura Técnica y Mapa de Código)

### 4.1 Resumen de la Arquitectura

El módulo "Carga de Archivos de Clientes" sigue una arquitectura de módulo estándar de PrestaShop, aprovechando los principios MVC. Extiende `Module` para su funcionalidad y configuración principales, utiliza `ModuleFrontController` para interacciones de front-office (carga, gestión de archivos) y `AdminController` para la gestión de back-office. Los datos se almacenan en el sistema de archivos y potencialmente se vinculan a través de `ps_configuration` para la configuración. El módulo depende en gran medida del sistema de hooks de PrestaShop para inyectar su funcionalidad en varias partes de la tienda.

### 4.2 Controladores (`controllers/`)

#### Controladores de Front-Office

- `controllers/front/customerfiles.php`
  - **Nombre de la clase y clase padre:** `CustomerfilesCustomerfilesModuleFrontController` extiende `ModuleFrontController`
  - **Responsabilidad:** Probablemente maneja la página principal "Mis Archivos" orientada al cliente, mostrando una lista de archivos subidos y proporcionando opciones de gestión. Obtendría los archivos asociados con el cliente que ha iniciado sesión.
- `controllers/front/download.php`
  - **Nombre de la clase y clase padre:** `DownloadCustomerfilesModuleFrontController` extiende `ModuleFrontController`
  - **Responsabilidad:** Gestiona las descargas seguras de archivos. Toma un ID o ruta de archivo, verifica los permisos del cliente (si corresponde) y sirve el archivo al navegador, a menudo forzando una descarga.
- `controllers/front/filesmanager.php`
  - **Nombre de la clase y clase padre:** `FilesmanagerCustomerfilesModuleFrontController` extiende `ModuleFrontController`
  - **Responsabilidad:** Podría ser una interfaz genérica de gestión de archivos, potencialmente utilizada para llamadas AJAX relacionadas con operaciones de archivos (por ejemplo, eliminar un archivo de la vista del cliente).
- `controllers/front/index.php`
  - **Nombre de la clase y clase padre:** `IndexCustomerfilesModuleFrontController` extiende `ModuleFrontController`
  - **Responsabilidad:** A menudo un marcador de posición o un controlador de redirección. En algunos módulos, podría servir como punto de entrada predeterminado o manejar el enrutamiento básico.
- `controllers/front/myfiles.php`
  - **Nombre de la clase y clase padre:** `MyfilesCustomerfilesModuleFrontController` extiende `ModuleFrontController`
  - **Responsabilidad:** Similar a `customerfiles.php`, este probablemente maneja la sección específica "Mis Archivos" dentro de la cuenta del cliente, mostrando sus archivos subidos y potencialmente un formulario de carga.
- `controllers/front/thumb.php`
  - **Nombre de la clase y clase padre:** `ThumbCustomerfilesModuleFrontController` extiende `ModuleFrontController`
  - **Responsabilidad:** Genera y sirve miniaturas para archivos de imagen subidos, mejorando el rendimiento y la visualización en las páginas de listado de archivos.
- `controllers/front/upload.php`
  - **Nombre de la clase y clase padre:** `UploadCustomerfilesModuleFrontController` extiende `ModuleFrontController`
  - **Responsabilidad:** El manejador de carga principal. Recibe las cargas de archivos (a través de AJAX o envío de formulario estándar), valida el tipo y tamaño del archivo, mueve el archivo al directorio designado y registra la información del archivo en la base de datos.

#### Controladores de Administración de Back-Office

- `controllers/admin/customerFiles.php`
  - **Nombre de la clase y clase padre:** `AdminCustomerFilesController` extiende `ModuleAdminController`
  - **Nombre de la pestaña y entidad gestionada:** "Archivos de Clientes" (o similar). Este controlador gestiona la vista de cuadrícula principal de todos los archivos subidos por los clientes en el Back Office. Proporciona funcionalidad para listar, filtrar, ver detalles, descargar y eliminar archivos.
  - **Claves de Configuración Asociadas:** `PS_SHOP_EMAIL`, `PS_SHOP_NAME` (para notificaciones por correo electrónico), `OF_CEMAIL_CUSTOMER`, `OF_CEMAIL_ATTACH` (probablemente relacionadas con la configuración de plantillas de correo electrónico para notificaciones al cliente).
- `controllers/admin/index.php`
  - **Nombre de la clase y clase padre:** `IndexCustomerfilesModuleAdminController` extiende `ModuleAdminController`
  - **Nombre de la pestaña y entidad gestionada:** Similar a `index.php` del front-office, este podría ser un marcador de posición o un controlador de redirección para la sección de administración del módulo.

### 4.3 Clases y Modelos Principales (`classes/`)

El inventario proporcionado no indica clases personalizadas en el directorio `classes/`. Esto sugiere que el módulo podría estar utilizando `ObjectModel` directamente dentro del archivo principal del módulo o los controladores de administración, o es una estructura de módulo heredada donde el manejo de datos está incrustado. Si los datos se almacenan en una tabla personalizada, el método `install()` del módulo principal definiría su esquema.

### 4.4 Activos JavaScript (`views/js/`)

- `js/jquery.form.js`
  - **Alcance:** Probablemente Front-office y Back-office.
  - **Explicación:** Un plugin de jQuery para enviar formularios fácilmente a través de AJAX, incluyendo cargas de archivos. Maneja las complejidades de `multipart/form-data` y proporciona callbacks de progreso.
- `js/orders.js`
  - **Alcance:** Back-office (específicamente páginas de detalles de pedidos).
  - **Explicación:** Este script probablemente añade funcionalidad a la página de detalles de pedidos de PrestaShop, como mostrar la sección de archivos subidos, manejar las descargas de archivos del lado del administrador o potencialmente permitir a los administradores subir archivos a un pedido.
- `js/script-customers.js`
  - **Alcance:** Front-office (páginas de cuenta de cliente).
  - **Explicación:** Maneja la lógica del lado del cliente para la sección "Mis Archivos" en la cuenta del cliente, incluyendo la visualización de listas de archivos, la gestión de acciones de eliminación y el inicio de nuevas cargas.
- `js/script.js`
  - **Alcance:** Front-office (general, páginas de producto, carrito) y potencialmente configuración de Back-office.
  - **Explicación:** Un script de propósito general para el módulo. Probablemente inicializa formularios de carga, maneja la validación de archivos (tamaño, tipo) antes del envío, muestra el progreso de la carga y gestiona las interacciones de la interfaz de usuario relacionadas con las cargas de archivos en varias ubicaciones del front-office.

### 4.5 Hojas de Estilo CSS (`views/css/`)

- `css/ajaxuploader.css`
  - **Alcance:** Front-office.
  - **Explicación:** Estilos para la interfaz de carga de archivos basada en AJAX, incluyendo barras de progreso, zonas de arrastrar y soltar y elementos de entrada de archivos.
- `css/backoffice.css`
  - **Alcance:** Back-office.
  - **Explicación:** Estilos específicos para las páginas de administración del módulo, como la cuadrícula del "Gestor de Archivos de Clientes", los formularios de configuración y la integración en la página de detalles del pedido.
- `css/orderfiles.css`
  - **Alcance:** Front-office.
  - **Explicación:** Estilo general para los componentes del front-office del módulo, incluyendo listas de archivos, botones y mensajes mostrados a los clientes.
- `css.css`
  - **Alcance:** Front-office.
  - **Explicación:** Podría ser una hoja de estilo heredada o general, que potencialmente contenga estilos centrales para los elementos visuales del módulo.

### 4.6 Estructura de Plantillas Smarty (`views/templates/`)

#### Plantillas de Hook (`views/templates/hook/`)

- `displayProductPageUploadFormSmall.tpl`: Renderiza un formulario de carga compacto en la página del producto.
- `filesmanager-orderhistory.tpl`: Muestra la sección de gestión/carga de archivos dentro de la página de detalles del historial de pedidos del cliente.
- `force-redirect.tpl`: Una plantilla de utilidad, posiblemente para manejar redirecciones después de ciertas acciones o para mostrar mensajes antes de la redirección.
- `header.tpl`: Inyectado en `displayHeader`, típicamente para cargar activos CSS/JS o metaetiquetas requeridas por el módulo.
- `my-account-17.tpl`: Renderiza el enlace o bloque "Mis Archivos" en el panel de control de la cuenta del cliente para PrestaShop 1.7.x y versiones posteriores.
- `my-account.tpl`: Renderiza el enlace o bloque "Mis Archivos" en el panel de control de la cuenta del cliente para versiones antiguas de PrestaShop (1.5.x, 1.6.x).
- `orderConfirmation.tpl`: Muestra el formulario de carga o la lista de archivos en la página de confirmación del pedido.
- `product-files-button.tpl`: Renderiza un botón o enlace en la página del producto que podría abrir un modal de carga o redirigir a una sección de carga.
- `product-files.tpl`: Muestra una lista de archivos asociados con un producto o un formulario de carga en la página del producto.
- `shopping-cart-force-files-alert.tpl`: Muestra una alerta en el carrito de compras si faltan archivos obligatorios para ciertos productos.
- `shopping-cart-qty-infos-alert.tpl`: Potencialmente relacionado con alertas para requisitos de archivos basados en la cantidad en el carrito.
- `shopping-cart.tpl`: Muestra el formulario de carga o la lista de archivos en la página de resumen del carrito de compras.
- `tab.tpl`: Una plantilla de pestaña genérica, posiblemente utilizada para mostrar una pestaña "Archivos" en las páginas de producto o en la cuenta del cliente.

#### Plantillas de Administración (`views/templates/admin/`)

- `admin.tpl`: Plantilla de administración general, posiblemente para la página de configuración principal del módulo o un panel de control.
- `adminOrderDetailUpload.tpl`: Integra la sección de carga/gestión de archivos en la página de detalles del pedido de PrestaShop en el Back Office.
- `boscript.tpl`: Contiene JavaScript específico del Back Office, potencialmente para inicializar formularios o manejar AJAX en las páginas de administración.
- `bulk-delete-files.tpl`: Plantilla para una confirmación de eliminación masiva o interfaz dentro del gestor de archivos de administración.
- `comments_cartfiles.tpl`: Muestra comentarios o notas relacionadas con archivos subidos para un carrito específico.
- `comments_orderfiles.tpl`: Muestra comentarios o notas relacionadas con archivos subidos para un pedido específico.
- `comments_productfiles.tpl`: Muestra comentarios o notas relacionadas con archivos subidos para un producto específico.
- `customerfilesmanager.tpl`: La plantilla principal para la vista de cuadrícula del "Gestor de Archivos de Clientes" en el Back Office.
- `_configure/helpers/list/list_action_details.tpl`: Plantilla para un botón de acción "detalles" en un ayudante de lista.
- `_configure/helpers/list/list_content.tpl`: Plantilla para el contenido principal de un ayudante de lista (por ejemplo, las filas de la lista de archivos).
- `_configure/prestashopbug/helpers/list/*.tpl`: Estas plantillas (`list.tpl`, `list_action_delete.tpl`, `list_action_details.tpl`, `list_content.tpl`, `list_footer.tpl`, `list_header.tpl`) sugieren una implementación de ayudante de lista personalizada o sobrescrita, posiblemente para abordar necesidades de visualización específicas o errores en versiones antiguas de PrestaShop.

#### Plantillas de Front-office (`views/templates/front/`)

- `access-denied.tpl`: Muestra un mensaje cuando un cliente intenta acceder a un archivo o página sin los permisos adecuados.
- `customerfilesmanager.tpl`: La plantilla principal para la página "Mis Archivos" del cliente, mostrando sus archivos subidos y opciones de gestión.
- `filesmanager.tpl`: Una plantilla de gestor de archivos genérica, potencialmente utilizada para varios escenarios de listado y carga de archivos en el front-office.
- `my-files.tpl`: Otra plantilla para la sección "Mis Archivos" del cliente, probablemente similar a `customerfilesmanager.tpl` o utilizada en conjunto.

### 4.7 Esquema de Base de Datos y Mapa de Hooks

- **Tablas de Base de Datos**:

  - El módulo probablemente crea al menos una tabla personalizada para almacenar metadatos sobre los archivos subidos. Una estructura de tabla típica sería `ps_orderfiles` (o similar), que contendría campos como:
    - `id_order_file` (Clave Primaria)
    - `id_customer` (Clave foránea a `ps_customer`)
    - `id_order` (Clave foránea a `ps_order`, anulable)
    - `id_product` (Clave foránea a `ps_product`, anulable)
    - `filename` (Nombre original del archivo)
    - `filepath` (Ruta al archivo almacenado en el servidor)
    - `filesize` (Tamaño en bytes)
    - `file_extension`
    - `date_add` (Marca de tiempo de la carga)
    - `comment` (Comentario opcional del cliente o administrador)
  - La configuración se almacena en `ps_configuration` con claves como `OF_CEMAIL_CUSTOMER`, `OF_CEMAIL_ATTACH` y otras configuraciones específicas del módulo.
- **Tabla de Hooks Registrados**:

| Nombre del Hook | Momento de Ejecución | Propósito Técnico |
| --- | --- | --- |
| `displayHeader` | En la sección `<head>` de cada página. | Inyectar CSS, JavaScript y potencialmente metaetiquetas para el módulo. |
| `displayProductAdditionalInfo` (o hook similar de página de producto) | En la página del producto, típicamente debajo de la descripción del producto o el botón de añadir al carrito. | Mostrar el formulario o botón de carga específico del producto. |
| `displayShoppingCartFooter` (o hook similar de página de carrito) | En la página de resumen del carrito de compras. | Mostrar el formulario de carga o la lista de archivos de todo el carrito. |
| `displayOrderConfirmation` | En la página de confirmación del pedido después de una compra exitosa. | Mostrar el formulario de carga posterior a la compra. |
| `displayCustomerAccount` | En el panel de control "Mi Cuenta" del cliente. | Añadir un enlace o bloque a la sección "Mis Archivos". |
| `displayMyAccountBlock` (PrestaShop 1.6.x) | En el panel de control "Mi Cuenta" del cliente. | Añadir un enlace o bloque a la sección "Mis Archivos". |
| `displayRightColumn` / `displayLeftColumn` | En las columnas laterales de la tienda. | Mostrar un botón/enlace general de "Subir Archivos" si está configurado. |
| `displayFooter` | En el pie de página de cada página. | Mostrar un botón/enlace general de "Subir Archivos" si está configurado. |
| `actionValidateOrder` | Después de que un pedido ha sido validado con éxito. | Potencialmente utilizado para vincular archivos subidos al ID de pedido recién creado o activar notificaciones de administrador. |
| `actionProductUpdate` / `actionProductAdd` | Cuando un producto es actualizado o añadido. | Podría usarse para gestionar los requisitos de archivos específicos del producto o limpiar archivos asociados. |
| `actionCustomerAccountAdd` | Cuando se crea una nueva cuenta de cliente. | (Menos probable para este módulo, pero posible para la configuración inicial). |
| `actionAdminOrdersView` | Cuando un administrador ve un pedido en el Back Office. | Inyectar la sección de gestión de archivos del módulo en la página de detalles del pedido. |

## 5. Soporte Oficial y Actualizaciones

Para las últimas actualizaciones, correcciones de errores y soporte profesional para el módulo "Carga de Archivos de Clientes", consulte su cuenta de cliente en [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nuestro equipo se dedica a garantizar que su módulo funcione perfectamente y le ayude a maximizar el potencial de su tienda.
