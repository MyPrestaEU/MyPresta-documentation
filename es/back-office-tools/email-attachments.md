---
title: "Archivos adjuntos de correo electrónico - Manual del Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop 'Archivos adjuntos de correo electrónico' de MyPresta.eu."
sidebar:
  label: "Archivos adjuntos de correo electrónico - Manual del Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Email attachments en MyPresta.eu](https://mypresta.eu/modules/administration-tools/email-attachments.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/back-office-tools/email-attachments/)
>
> ---


# Archivos adjuntos de correo electrónico

## 1. Requisitos y compatibilidad

- **Versiones de PrestaShop compatibles**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilidad con PHP**: PHP 5.6 - 8.5
- **Requisitos de alojamiento**: Las extensiones PHP estándar (cURL, JSON, OpenSSL) suelen ser suficientes. No se requieren configuraciones de servidor inusuales.

## 2. Recorrido completo por la configuración (Cada ajuste agrupado por pantalla)

El módulo "Archivos adjuntos de correo electrónico" ofrece un proceso de configuración sencillo, principalmente a través de una pantalla de administración dedicada donde gestiona sus archivos adjuntos y los vincula a plantillas de correo electrónico específicas.

### 2.1 Página de configuración del módulo (Back Office > Módulos > Configurar)

Cuando haga clic por primera vez en "Configurar" después de la instalación, será llevado a la página de configuración principal del módulo. Esta página sirve principalmente como punto de entrada y puede contener información general o un enlace a la pantalla de gestión de archivos adjuntos dedicada.

-   **Qué hace esta pantalla:** Esta pantalla inicial proporciona una breve descripción general del módulo y, por lo general, lo dirige a la interfaz principal para administrar los archivos adjuntos de correo electrónico. También podría contener configuraciones generales si el módulo tuviera alguna, pero para este módulo, la funcionalidad principal se gestiona en un controlador de administración separado.
-   **Efecto de cambiar la configuración:** Cualquier configuración aquí afectaría el comportamiento general del módulo. Sin embargo, para "Archivos adjuntos de correo electrónico", la acción principal es navegar a la página de gestión de "Archivos adjuntos de correo electrónico" dedicada.
-   **Valor recomendado:** Siga las instrucciones en pantalla, que generalmente implicarán hacer clic en un botón o enlace para continuar con el área de gestión de archivos adjuntos.

### 2.2 Pantalla de administración dedicada: Archivos adjuntos de correo electrónico (Back Office > Módulos > Archivos adjuntos de correo electrónico)

Este es el centro principal para administrar todos sus archivos adjuntos de correo electrónico. Normalmente encontrará un nuevo elemento de menú en **Módulos** o **Parámetros de la tienda** (según su versión de PrestaShop y el diseño del módulo) llamado "Archivos adjuntos de correo electrónico" o similar.

**Ubicación del menú:** Back Office > Módulos > Archivos adjuntos de correo electrónico (o similar, consulte su menú de administración después de la instalación)

#### Descripción general de la pantalla de gestión de "Archivos adjuntos de correo electrónico"

Esta pantalla presentará una lista (una "cuadrícula" o "tabla") de todos los archivos adjuntos de correo electrónico que ha configurado. Desde aquí, puede:

-   **Añadir nuevo archivo adjunto:** Crear una nueva regla de archivo adjunto.
-   **Editar archivo adjunto existente:** Modificar la configuración de un archivo adjunto que ya ha creado.
-   **Eliminar archivo adjunto:** Eliminar una regla de archivo adjunto.

#### Añadir/Editar un archivo adjunto de correo electrónico

Cuando haga clic en "Añadir nuevo archivo adjunto" o "Editar" uno existente, se le presentará un formulario para definir las propiedades del archivo adjunto.

**Campos y opciones del formulario:**

1.  **Nombre del archivo adjunto:**

    -   **Qué hace esta configuración:** Este es un nombre interno para su referencia en el Back Office. Le ayuda a identificar la regla del archivo adjunto fácilmente.
    -   **Efecto de cambiar esta configuración:** Solo cambia la etiqueta que ve en la lista de administración. No afecta el nombre del archivo que ve el cliente.
    -   **Valor recomendado:** Un nombre descriptivo, por ejemplo, "Guía de bienvenida PDF", "T&C de confirmación de pedido", "Manual de producto para nuevos pedidos".
    -   **Escenario del comerciante:** Tiene varios archivos adjuntos para diferentes propósitos; un nombre claro le ayuda a distinguirlos.
2.  **Seleccionar plantilla(s) de correo electrónico:**

    -   **Qué hace esta configuración:** Esta configuración crucial determina *a qué* correo(s) electrónico(s) de PrestaShop se añadirá este archivo adjunto. Normalmente verá una lista de todas las plantillas de correo electrónico estándar de PrestaShop (por ejemplo, `account`, `order_conf`, `shipped`, `contact_form`). Puede seleccionar una o varias plantillas.
    -   **Efecto de cambiar esta configuración:**
        -   *Cuando está seleccionada:* El archivo adjunto se incluirá en cada correo electrónico enviado utilizando la(s) plantilla(s) elegida(s).
        -   *Cuando no está seleccionada:* El archivo adjunto no se incluirá en los correos electrónicos que utilicen esa plantilla.
    -   **Valor recomendado:** Seleccione solo las plantillas de correo electrónico relevantes. Por ejemplo, una "Guía de bienvenida" solo debe adjuntarse al correo electrónico `account` (creación de cuenta de cliente).
    -   **Escenario del comerciante:** Desea adjuntar un PDF de "Política de devoluciones" a los correos electrónicos `order_conf` (confirmación de pedido) y `shipped` (notificación de envío).
3.  **Tipo de archivo adjunto:**

    -   **Qué hace esta configuración:** Esto define la fuente de su archivo adjunto. El módulo ofrece diferentes opciones:
        -   **Subir archivo:** Adjuntar un archivo existente desde su computadora.
        -   **Generar PDF desde página CMS:** Crear un PDF a partir de una de sus páginas CMS existentes de PrestaShop.
        -   **Crear PDF desde editor de texto enriquecido:** Diseñar contenido PDF personalizado directamente dentro del módulo utilizando un editor visual.
    -   **Efecto de cambiar esta configuración:** Determina el siguiente conjunto de opciones que verá para especificar el contenido del archivo adjunto.
    -   **Valor recomendado:** Elija el tipo que mejor se adapte a su fuente de contenido.
    -   **Escenario del comerciante:** Tiene un "Garantía.pdf" prefabricado (Subir archivo), o desea convertir su página CMS "Sobre nosotros" en un PDF (Generar PDF desde página CMS), o necesita escribir un PDF personalizado de "Oferta especial" (Crear PDF desde editor de texto enriquecido).

    **Subconfiguraciones basadas en el tipo de archivo adjunto:**

    -   **Si se selecciona "Subir archivo":**

        -   **Campo de carga de archivo:**
            -   **Qué hace esta configuración:** Le permite buscar en su computadora y subir un archivo (por ejemplo, PDF, JPG, DOCX).
            -   **Efecto de cambiar esta configuración:** El archivo seleccionado se almacenará en su servidor y se utilizará como archivo adjunto.
            -   **Valor recomendado:** Suba un archivo que no sea excesivamente grande para evitar problemas de entrega de correo electrónico. Los PDFs son generalmente preferidos para documentos.
            -   **Escenario del comerciante:** Adjuntar el PDF de "Términos y condiciones" de su empresa.
    -   **Si se selecciona "Generar PDF desde página CMS":**

        -   **Seleccionar página CMS:**
            -   **Qué hace esta configuración:** Proporciona una lista desplegable de todas sus páginas CMS activas de PrestaShop.
            -   **Efecto de cambiar esta configuración:** El contenido de la página CMS elegida se convertirá en un PDF y se adjuntará.
            -   **Valor recomendado:** Seleccione una página CMS con contenido adecuado para un documento PDF (por ejemplo, "Sobre nosotros", "Política de privacidad").
            -   **Escenario del comerciante:** Adjuntar automáticamente su página CMS de "Política de devoluciones" como PDF a los correos electrónicos relevantes.
    -   **Si se selecciona "Crear PDF desde editor de texto enriquecido":**

        -   **Editor de texto enriquecido (WYSIWYG):**
            -   **Qué hace esta configuración:** Un editor visual donde puede escribir y formatear contenido personalizado, añadir imágenes, enlaces, etc. Este contenido se convertirá luego en un PDF.
            -   **Efecto de cambiar esta configuración:** El contenido que cree aquí formará el cuerpo del PDF adjunto.
            -   **Valor recomendado:** Utilícelo para contenido dinámico o único que no exista como archivo o página CMS. Mantenga el diseño simple para obtener los mejores resultados de conversión a PDF.
            -   **Escenario del comerciante:** Crear un mensaje de "Gracias" personalizado con un código de descuento como archivo adjunto PDF.
4.  **Nombre del archivo adjunto (visible para el cliente):**

    -   **Qué hace esta configuración:** Este es el nombre del archivo que el cliente verá en su cliente de correo electrónico cuando reciba el archivo adjunto.
    -   **Efecto de cambiar esta configuración:** Cambia cómo aparece el archivo en la bandeja de entrada del cliente.
    -   **Valor recomendado:** Un nombre de archivo claro, descriptivo y profesional (por ejemplo, `Su-Confirmacion-de-Pedido.pdf`, `Informacion-de-Garantia.pdf`). Incluya la extensión del archivo (por ejemplo, `.pdf`).
    -   **Escenario del comerciante:** Ha subido `mi_documento_interno_v2.pdf`, pero quiere que el cliente vea `Guia-de-Producto.pdf`.
5.  **Activo:**

    -   **Qué hace esta configuración:** Un simple interruptor ON/OFF para habilitar o deshabilitar esta regla de archivo adjunto específica.
    -   **Efecto de cambiar esta configuración:**
        -   *Cuando está habilitado:* La regla del archivo adjunto está activa y se aplicará a los correos electrónicos seleccionados.
        -   *Cuando está deshabilitado:* La regla del archivo adjunto está inactiva y no añadirá archivos a los correos electrónicos.
    -   **Valor recomendado:** Establezca en "SÍ" cuando desee que se envíe el archivo adjunto.
    -   **Escenario del comerciante:** Está probando un archivo adjunto y desea deshabilitarlo temporalmente sin eliminar la configuración.

#### 2.2.1 Tabla de referencia rápida de configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| **Archivos adjuntos de correo electrónico (Controlador de administración)** | Nombre del archivo adjunto | Texto descriptivo | Etiqueta interna para una fácil identificación en el BO. |
| | Seleccionar plantilla(s) de correo electrónico | Plantillas específicas (ej., `order_conf`) | Determina qué correos electrónicos reciben el archivo adjunto. |
| | Tipo de archivo adjunto | Varía (Subir archivo, Página CMS, Texto enriquecido) | Define la fuente del contenido del archivo adjunto. |
| | *Si Subir archivo:* Campo de carga de archivo | N/A | Sube un archivo existente desde su computadora. |
| | *Si Generar PDF desde página CMS:* Seleccionar página CMS | Página CMS específica | Convierte el contenido de la página CMS elegida a PDF. |
| | *Si Crear PDF desde editor de texto enriquecido:* Editor de texto enriquecido | Contenido personalizado | Crea un PDF a partir del contenido introducido en el editor. |
| | Nombre del archivo adjunto | Nombre de archivo descriptivo (ej., `documento.pdf`) | El nombre que los clientes ven en su cliente de correo electrónico. |
| | Activo | SÍ | Habilita/deshabilita la regla del archivo adjunto. |

## 3. Solución de problemas del comerciante y preguntas frecuentes (FAQ)

**P1: Mis archivos adjuntos no se envían, o los clientes informan que no los reciben.**

-   **R:** Primero, verifique si la regla del archivo adjunto está "Activa" en la configuración del módulo.
-   **R:** Asegúrese de haber seleccionado la(s) plantilla(s) de correo electrónico correcta(s) para el archivo adjunto. Pruebe activando uno de esos correos electrónicos usted mismo (por ejemplo, realice un pedido de prueba, cree una nueva cuenta de cliente).
-   **R:** Verifique la configuración de correo electrónico de su PrestaShop (Parámetros de la tienda > Correo electrónico) para asegurarse de que los correos electrónicos se envían correctamente en general. Intente enviar un correo electrónico de prueba desde PrestaShop.
-   **R:** El archivo adjunto podría ser demasiado grande, lo que hace que los proveedores de correo electrónico rechacen el correo. Intente con un tamaño de archivo más pequeño.
-   **R:** Borre la caché de su PrestaShop (Parámetros avanzados > Rendimiento > Borrar caché).

**P2: El PDF generado desde mi página CMS se ve extraño o tiene problemas de formato.**

-   **R:** La generación de PDF a partir de HTML a veces puede ser complicada. Asegúrese de que el contenido de su página CMS sea HTML limpio sin JavaScript complejo o elementos altamente dinámicos.
-   **R:** Intente simplificar el diseño de su página CMS. Evite CSS excesivamente complejo o imágenes muy anchas que podrían no encajar bien en una página PDF estándar.
-   **R:** Si los problemas persisten, considere crear un archivo PDF dedicado externamente y usar la opción "Subir archivo" en su lugar.

**P3: ¿Puedo adjuntar diferentes archivos según el producto pedido o el grupo de clientes?**

-   **R:** Este módulo, en su configuración estándar, adjunta archivos a *todos* los correos electrónicos de un tipo seleccionado, independientemente del producto específico o grupo de clientes. Para archivos adjuntos condicionales más avanzados, podría ser necesario un desarrollo personalizado o un módulo más especializado.

**P4: ¿Cómo traduzco el contenido de un PDF creado con el Editor de texto enriquecido para diferentes idiomas?**

-   **R:** Al usar el Editor de texto enriquecido, debería ver pestañas de idioma (por ejemplo, inglés, francés, español) si su tienda PrestaShop admite varios idiomas. Deberá introducir y formatear el contenido para cada idioma por separado dentro del editor. El módulo adjuntará la versión en el idioma correcto según el idioma seleccionado por el cliente.

**P5: ¿Dónde se almacenan los archivos subidos en mi servidor?**

-   **R:** Los archivos subidos se almacenan típicamente dentro del directorio del módulo o en una carpeta de carga designada dentro del módulo. Generalmente no necesita interactuar con estos archivos directamente a través de FTP, ya que el módulo los gestiona.

## 4. Guía para desarrolladores y webmasters (Arquitectura técnica y mapa de código)

Esta sección proporciona una descripción técnica detallada para desarrolladores y webmasters que trabajan con el módulo "Archivos adjuntos de correo electrónico".

### 4.1 Descripción general de la arquitectura

El módulo "Archivos adjuntos de correo electrónico" (`mattach`) extiende la funcionalidad principal de correo electrónico de PrestaShop sobrescribiendo la clase `Mail`. Esto le permite inyectar archivos adjuntos personalizados en los correos electrónicos salientes sin modificar directamente los archivos principales. Sigue un patrón MVC estándar de PrestaShop para su interfaz de gestión del Back Office, utilizando un `AdminController` para gestionar las entidades `mailfile` que representan las configuraciones de los archivos adjuntos. La generación de PDF se maneja internamente, ya sea convirtiendo contenido CMS o la entrada del editor de texto enriquecido.

### 4.2 Controladores (`controllers/`)

-   **Controladores de Front-Office**:

    -   Este módulo **no** contiene ningún controlador de front-office dedicado. Todas sus operaciones se realizan en el Back Office o sobrescribiendo clases principales durante el envío de correo electrónico.
-   **Controladores de administración del Back-Office**:

    -   `mattach/controllers/admin/AdminMailAttachments.php`

        -   **Nombre de la clase**: `AdminMailAttachmentsController`
        -   **Clase padre**: `ModuleAdminController`
        -   **Responsabilidad**: Este es el controlador principal para gestionar las reglas de archivos adjuntos de correo electrónico. Maneja las operaciones CRUD (Crear, Leer, Actualizar, Eliminar) para la entidad `mailfile`. Muestra una lista de archivos adjuntos configurados, proporciona formularios para añadirlos/editarlos y gestiona las cargas de archivos, la selección de páginas CMS y el contenido del editor de texto enriquecido para la generación de PDF. Utiliza `HelperList` de PrestaShop para la vista de cuadrícula y `HelperForm` para los formularios de añadir/editar.
        -   **Tabla / Entidad gestionada**: `mailfile` (tabla personalizada para los datos del módulo).
        -   **Claves de configuración asociadas**: `PS_LANG_DEFAULT` (utilizado para campos multi-idioma).
    -   `mattach/controllers/admin/index.php`

        -   **Nombre de la clase**: (Sin clase explícita, típicamente un marcador de posición o redirección)
        -   **Responsabilidad**: Este archivo es a menudo una medida de seguridad (para evitar la lista directa de directorios) o una simple redirección dentro de la estructura de administración de PrestaShop. No contiene lógica de controlador activa para la funcionalidad del módulo.

### 4.3 Clases y modelos principales (`classes/`)

-   `mattach/override/classes/index.php`

    -   **Responsabilidad**: Archivo de seguridad estándar de PrestaShop para evitar la lista de directorios.
-   `mattach/override/classes/Mail.php`

    -   **Nombre de la clase**: `Mail` (sobrescribe la clase `Mail` principal de PrestaShop)
    -   **Clase padre**: `MailCore`
    -   **Responsabilidad**: Esta es la parte más crítica de la funcionalidad del módulo. Al sobrescribir la clase `Mail`, el módulo intercepta el método `send()`. Dentro del método `send()` sobrescrito, verifica si hay reglas de archivos adjuntos configuradas para la plantilla de correo electrónico específica que se está enviando. Si se encuentran coincidencias, recupera los datos del archivo adjunto (ruta del archivo subido, contenido PDF generado), crea los objetos `Swift_Attachment` necesarios y los añade al correo electrónico antes de que se envíe. Esto asegura que los archivos adjuntos se incluyan sin problemas en todos los correos electrónicos salientes relevantes.
    -   **Interacción con la base de datos**: Interactúa con la tabla `mailfile` personalizada del módulo para obtener las configuraciones de los archivos adjuntos.
    -   **Métodos públicos clave**: Sobrescribe `send()` para inyectar la lógica de archivos adjuntos.

### 4.4 Activos JavaScript (`views/js/`)

-   `mattach/views/templates/admin/js/mattach.js`
    -   **Alcance**: Back-office (AdminMailAttachmentsController).
    -   **Funcionalidad**: Este script probablemente maneja el comportamiento dinámico del formulario de configuración de archivos adjuntos. Esto podría incluir:
        -   Mostrar/ocultar campos de entrada específicos según el "Tipo de archivo adjunto" seleccionado (por ejemplo, mostrar el campo de carga de archivo solo cuando se elige "Subir archivo").
        -   Llamadas AJAX para obtener listas de páginas CMS u otros datos dinámicos.
        -   Inicialización del editor de texto enriquecido (por ejemplo, TinyMCE o CKEditor) para la opción "Crear PDF desde editor de texto enriquecido".
        -   Validación del lado del cliente o mejoras de la interfaz de usuario para la interfaz de gestión de archivos adjuntos.

### 4.5 Hojas de estilo CSS (`views/css/`)

-   Este módulo **no** parece contener ningún archivo CSS personalizado en el inventario proporcionado. Probablemente se basa en el estilo predeterminado del Back Office de PrestaShop para sus formularios y listas de configuración.

### 4.6 Estructura de plantillas Smarty (`views/templates/`)

-   **Plantillas de gancho (`views/templates/hook/`)**:

    -   Este módulo **no** contiene ninguna plantilla de gancho específica en el inventario proporcionado. Su impacto en el front-office es únicamente a través de archivos adjuntos de correo electrónico, no de elementos visuales.
-   **Plantillas de administración (`views/templates/admin/`)**:

    -   `mattach/views/templates/admin/orderstates.tpl`
        -   **Propósito**: El nombre de esta plantilla sugiere que podría usarse para mostrar o gestionar estados de pedido en relación con los archivos adjuntos, o quizás para seleccionar estados de pedido para archivos adjuntos condicionales (aunque la descripción del módulo no menciona explícitamente esta característica avanzada). Podría ser parte del formulario `AdminMailAttachmentsController`, potencialmente para seleccionar qué cambios de estado de pedido activan un correo electrónico con un archivo adjunto.
    -   `mattach/lib/searchTool/views/scripts.tpl`
        -   **Propósito**: Esta plantilla probablemente contiene lógica JavaScript o Smarty relacionada con una herramienta de búsqueda o filtrado utilizada dentro de la interfaz de administración, posiblemente para buscar plantillas de correo electrónico o páginas CMS. Es una plantilla de utilidad para mejorar la interfaz de usuario de administración.
-   **Plantillas de front-office (`views/templates/front/`)**:

    -   Este módulo **no** contiene ninguna plantilla de front-office.

### 4.7 Esquema de la base de datos y mapa de ganchos

-   **Tablas de la base de datos**:

    -   `ps_mailfile`: Esta es la tabla personalizada principal creada por el módulo para almacenar cada configuración de archivo adjunto de correo electrónico.
        -   `id_mailfile`: Clave primaria.
        -   `name`: Nombre interno de la regla del archivo adjunto.
        -   `file_name`: El nombre de archivo real (o nombre generado) del archivo adjunto.
        -   `file_path`: Ruta al archivo subido o donde se almacena temporalmente el PDF generado.
        -   `file_type`: Tipo de archivo adjunto (por ejemplo, 'upload', 'cms', 'editor').
        -   `id_cms`: Si `file_type` es 'cms', almacena el ID de la página CMS.
        -   `content`: Si `file_type` es 'editor', almacena el contenido de texto enriquecido (multi-idioma).
        -   `mail_templates`: Una matriz serializada o una cadena separada por comas de nombres de plantillas de correo electrónico (por ejemplo, `account`, `order_conf`) a las que se aplica este archivo adjunto.
        -   `active`: Booleano (0 o 1) que indica si la regla del archivo adjunto está activa.
    -   `ps_mailfile_lang`: Tabla complementaria para campos multi-idioma como `content` (si `file_type` es 'editor').
        -   `id_mailfile`: Clave foránea a `ps_mailfile`.
        -   `id_lang`: ID de idioma.
        -   `content`: Contenido de texto enriquecido traducido.
-   **Tabla de ganchos registrados**:

    -   El módulo opera principalmente sobrescribiendo la clase `Mail` principal, que es un método más directo y potente que depender únicamente de ganchos para la modificación del correo electrónico. Si bien podría registrar algunos ganchos estándar para la instalación/desinstalación del módulo o la integración del menú del Back Office, su lógica principal de inyección de archivos adjuntos se encuentra en la sobrescritura de `Mail`.
    -   **Método `install()`**:
        -   Registra el módulo en el menú del Back Office.
        -   Crea las tablas de la base de datos `ps_mailfile` y `ps_mailfile_lang`.
        -   Instala la sobrescritura de la clase `Mail`.
    -   **Método `uninstall()`**:
        -   Elimina el módulo del menú del Back Office.
        -   Elimina las tablas de la base de datos `ps_mailfile` y `ps_mailfile_lang`.
        -   Desinstala la sobrescritura de la clase `Mail`.

## 5. Soporte oficial y actualizaciones

Para las últimas actualizaciones, correcciones de errores y soporte oficial para el módulo "Archivos adjuntos de correo electrónico", consulte su cuenta de cliente en [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nuestro equipo de soporte está disponible para ayudarle con cualquier problema o pregunta relacionada con la funcionalidad y configuración del módulo.
