---
title: "MyPazaruvaj - Correo electrónico de encuesta de Pazaruvaj - Manual del Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop MyPazaruvaj - Correo electrónico de encuesta de Pazaruvaj de MyPresta.eu."
sidebar:
  label: "MyPazaruvaj - Correo electrónico de encuesta de Pazaruvaj - Manual del Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo MyPazaruvaj - Pazaruvaj survey email en MyPresta.eu](https://mypresta.eu/modules/advertising-and-marketing/mypazaruvaj-pazaruvaj-survey-email.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/advertising-marketing/mypazaruvaj-pazaruvaj-survey-email/)
>
> ---


# MyPazaruvaj - Correo electrónico de encuesta de Pazaruvaj

## 1. Requisitos y compatibilidad

- **Versiones de PrestaShop compatibles**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilidad con PHP**: PHP 5.6 - 8.5 (El módulo está diseñado para ser ampliamente compatible con varias versiones de PHP, hasta la última versión estable compatible con PrestaShop 8 y 9).
- **Requisitos de alojamiento**: Las extensiones PHP estándar (cURL, JSON, OpenSSL) suelen ser requeridas por PrestaShop y son suficientes para este módulo. No se necesitan configuraciones especiales del servidor.

## 2. Recorrido completo por la configuración (Cada ajuste agrupado por pantalla)

### 2.1 Página de configuración del módulo (Back Office > Módulos > Configurar > MyPazaruvaj)

Esta es la pantalla de configuración principal y única para el módulo MyPazaruvaj. Aquí configurará todos los parámetros necesarios para conectar su tienda con Pazaruvaj.com.

#### **ID de tienda de Pazaruvaj.com**

-   **Qué hace este ajuste:** Este es su identificador único proporcionado por Pazaruvaj.com para su tienda online. Le indica a Pazaruvaj a qué tienda pertenecen los datos del pedido.
-   **Efecto de cambiar este ajuste:**
    -   *Cuando se configura correctamente:* El módulo enviará con éxito los datos del pedido a su perfil de tienda de Pazaruvaj.com.
    -   *Cuando es incorrecto o está vacío:* Pazaruvaj.com no podrá identificar su tienda y no se enviarán correos electrónicos de encuesta a sus clientes.
-   **Valor recomendado:** Introduzca el ID de tienda exacto que le ha proporcionado Pazaruvaj.com. Este es un campo obligatorio.
-   **Escenario / ejemplo de comerciante:** Ha registrado su tienda en Pazaruvaj.com y le han dado un ID de tienda como `12345`. Debe introducir `12345` aquí para que la integración funcione.

#### **Campo de ID de producto de Pazaruvaj.com**

-   **Qué hace este ajuste:** Esta opción determina qué identificador de producto de su tienda PrestaShop debe enviarse a Pazaruvaj.com. Pazaruvaj.com utiliza este ID para hacer coincidir el producto comprado con su listado en su plataforma.
-   **Efecto de cambiar este ajuste:**
    -   *Cuando se establece en "ID de producto":* Se enviará el ID de producto interno de PrestaShop (por ejemplo, `id_product`). Esta suele ser la opción más segura si su feed de Pazaruvaj.com utiliza estos IDs.
    -   *Cuando se establece en "Referencia de producto":* Se enviará el código de referencia del producto (por ejemplo, `reference`). Elija esta opción si su feed de Pazaruvaj.com coincide con los productos por su referencia.
    -   *Cuando se establece en "EAN13 de producto":* Se enviará el código de barras EAN13 del producto. Útil si su feed de Pazaruvaj.com se basa en EANs.
    -   *Cuando se establece en "UPC de producto":* Se enviará el código UPC del producto.
-   **Valor recomendado:** "ID de producto" suele ser el valor predeterminado más fiable. Sin embargo, **debe** verificar qué identificador utiliza su feed de productos en Pazaruvaj.com para hacer coincidir los productos. Si su feed utiliza referencias de producto, seleccione "Referencia de producto".
-   **Escenario / ejemplo de comerciante:** Si su feed de productos en Pazaruvaj.com utiliza el ID interno único que PrestaShop asigna a cada producto, debe seleccionar "ID de producto". Si ha subido un feed donde cada producto se identifica por un SKU o número de referencia específico (por ejemplo, `REF-001`), entonces seleccione "Referencia de producto".

#### **Habilitar consentimiento para enviar datos a Pazaruvaj.com**

-   **Qué hace este ajuste:** Este interruptor controla si los clientes deben aceptar explícitamente que los datos de su pedido se envíen a Pazaruvaj.com para la encuesta. Cuando está habilitado, aparece una casilla de verificación durante el proceso de pago.
-   **Efecto de cambiar este ajuste:**
    -   *Cuando está habilitado (SÍ):* Aparecerá una casilla de verificación en la página de pago. Solo los clientes que marquen esta casilla tendrán los datos de su pedido enviados a Pazaruvaj.com. Esto ayuda con el GDPR y otras regulaciones de privacidad de datos.
    -   *Cuando está deshabilitado (NO):* Los datos del pedido se enviarán a Pazaruvaj.com para *todos* los pedidos completados sin requerir el consentimiento explícito del cliente. Esto es más sencillo para los clientes, pero podría no cumplir con todas las leyes de privacidad de su región.
-   **Valor recomendado:** "SÍ" se recomienda generalmente para cumplir con las regulaciones de protección de datos (como el GDPR).
-   **Escenario / ejemplo de comerciante:** Para asegurarse de que su tienda cumple plenamente con las leyes de privacidad, habilita esta configuración. Durante el proceso de pago, sus clientes verán una casilla de verificación con una etiqueta similar a "Acepto compartir los detalles de mi pedido con Pazaruvaj.com para una encuesta de opinión". Solo si la marcan se enviarán los datos.

#### **Mostrar consentimiento en**

-   **Qué hace este ajuste:** Si "Habilitar consentimiento" está configurado en SÍ, esta opción determina dónde se mostrará la casilla de verificación de consentimiento en el front-office de su tienda.
-   **Efecto de cambiar este ajuste:**
    -   *Encabezado, Columnas, Producto, Pie de página:* La casilla de verificación de consentimiento se mostrará en el área de hook seleccionada. La ubicación visual exacta depende del diseño de su tema para ese hook.
-   **Valor recomendado:** Elija una ubicación prominente pero no intrusiva. El "Pie de página" o una "Columna" específica (si su tema tiene una adecuada) suelen ser buenas opciones para avisos relacionados con la privacidad. Es posible que deba probar diferentes opciones para ver qué se ve mejor con su tema.
-   **Escenario / ejemplo de comerciante:** Ha habilitado el consentimiento. Decide mostrar la casilla de verificación de consentimiento en el "Pie de página" para que sea visible pero no sature el flujo principal de pago.

#### **Habilitar registro de errores**

-   **Qué hace este ajuste:** Este interruptor controla si el módulo registra los errores encontrados durante el proceso de transferencia de datos a Pazaruvaj.com.
-   **Efecto de cambiar este ajuste:**
    -   *Cuando está habilitado (SÍ):* El módulo guardará los detalles de cualquier envío de datos fallido en un archivo de registro. Esto es invaluable para la resolución de problemas si no se envían las encuestas.
    -   *Cuando está deshabilitado (NO):* No se registrará información de errores, lo que dificulta el diagnóstico de problemas.
-   **Valor recomendado:** "SÍ" es muy recomendable, especialmente durante la configuración inicial y para el monitoreo continuo.
-   **Escenario / ejemplo de comerciante:** No está seguro de si la integración funciona perfectamente. Habilita el registro de errores. Si Pazaruvaj.com no recibe datos, puede verificar el registro para ver si hay mensajes de error específicos, como un ID de tienda no válido o problemas de conexión.

#### **Borrar registro de errores**

-   **Qué hace este ajuste:** Este botón le permite eliminar todas las entradas del registro de errores del módulo.
-   **Efecto de cambiar este ajuste:**
    -   *Cuando se hace clic:* Todos los errores registrados anteriormente se eliminan permanentemente del archivo de registro.
-   **Valor recomendado:** Utilice esto después de haber revisado y resuelto cualquier problema, o si el archivo de registro se vuelve demasiado grande.
-   **Escenario / ejemplo de comerciante:** Ha solucionado un problema con su ID de tienda de Pazaruvaj.com. Hace clic en "Borrar registro de errores" para empezar de nuevo y asegurarse de que solo se registren errores nuevos y relevantes.

### 2.2 Tabla de referencia rápida de configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| Configuración del módulo | ID de tienda de Pazaruvaj.com | Su ID de Pazaruvaj (Obligatorio) | Identificador único para su tienda en Pazaruvaj.com. Esencial para la transferencia de datos. |
| Configuración del módulo | Campo de ID de producto de Pazaruvaj.com | ID de producto (Verificar con el feed de Pazaruvaj) | Determina qué identificador de producto de PrestaShop (ID, Referencia, EAN13, UPC) se envía a Pazaruvaj.com para la coincidencia de productos. |
| Configuración del módulo | Habilitar consentimiento para enviar datos a Pazaruvaj.com | SÍ (Para cumplimiento) | Requiere el consentimiento del cliente a través de una casilla de verificación durante el proceso de pago antes de enviar datos a Pazaruvaj.com. |
| Configuración del módulo | Mostrar consentimiento en | Pie de página (Probar para la mejor ubicación) | Especifica el hook del front-office donde aparecerá la casilla de verificación de consentimiento si está habilitada. |
| Configuración del módulo | Habilitar registro de errores | SÍ (Para resolución de problemas) | Activa el registro de cualquier error durante el envío de datos a Pazaruvaj.com. |
| Configuración del módulo | Borrar registro de errores | N/A (Botón) | Elimina todas las entradas del registro de errores del módulo. |

## 3. Resolución de problemas del comerciante y preguntas frecuentes (FAQ)

**P: Mis clientes no reciben correos electrónicos de encuesta de Pazaruvaj.com. ¿Qué debo verificar?**
R:

1.  **ID de tienda de Pazaruvaj.com:** Verifique que su "ID de tienda de Pazaruvaj.com" en la configuración del módulo sea absolutamente correcto y coincida con el ID proporcionado por Pazaruvaj.com.
2.  **Registro de errores:** Habilite el "Registro de errores" en la configuración del módulo y verifique si hay errores registrados después de un pedido de prueba. Esto a menudo señalará el problema exacto.
3.  **Configuración de consentimiento:** Si "Habilitar consentimiento para enviar datos a Pazaruvaj.com" está habilitado, asegúrese de que los clientes realmente estén marcando la casilla de verificación durante el proceso de pago. Si no lo hacen, no se enviarán los datos.
4.  **Estado del pedido:** Asegúrese de que el pedido alcance un estado final de "Pago aceptado" o similar en PrestaShop, ya que el módulo generalmente se activa al completar el pedido con éxito.
5.  **Cuenta de Pazaruvaj.com:** Inicie sesión en su cuenta de Pazaruvaj.com para ver si hay algún problema o advertencia por su parte con respecto a su tienda o feed de datos.

**P: La casilla de verificación de consentimiento no aparece en mi página de pago.**
R:

1.  **Configuración de "Habilitar consentimiento":** Primero, asegúrese de que "Habilitar consentimiento para enviar datos a Pazaruvaj.com" esté configurado en SÍ en la configuración del módulo.
2.  **Configuración de "Mostrar consentimiento en":** Verifique qué hook ha seleccionado para "Mostrar consentimiento en". Si su tema no muestra activamente contenido en ese hook específico (por ejemplo, un `displayMyCustomHook` personalizado), la casilla de verificación no aparecerá. Intente cambiar a un hook común como `displayFooter` o `displayHeader` para probar.
3.  **Compatibilidad del tema:** Algunos temas altamente personalizados pueden anular las ubicaciones estándar de los hooks. Si el problema persiste, es posible que necesite que un webmaster inspeccione los archivos de plantilla de su tema.
4.  **Caché de Smarty:** Borre la caché de Smarty de su PrestaShop en **Parámetros avanzados > Rendimiento** (Forzar compilación y borrar caché).

**P: Cambié una configuración, pero no pasó nada en mi tienda.**
R: Después de realizar cualquier cambio en la configuración del módulo, siempre borre la caché de su PrestaShop. Vaya a **Parámetros avanzados > Rendimiento**, luego haga clic en "Borrar caché" y, opcionalmente, en "Forzar compilación" si está realizando cambios relacionados con la plantilla. Es posible que también deba borrar la caché de su navegador (Ctrl+F5 o Cmd+R).

**P: ¿Puedo personalizar el texto de la casilla de verificación de consentimiento?**
R: Sí, el texto de la casilla de verificación de consentimiento es traducible. Puede modificarlo a través del sistema de traducción de PrestaShop:

1.  Vaya a **Internacional > Traducciones**.
2.  Seleccione "Traducciones de módulos instalados".
3.  Elija su tema, el idioma y luego seleccione "MyPazaruvaj".
4.  Allí encontrará la cadena relacionada con el mensaje de consentimiento y podrá editarla.

**P: ¿Qué pasa si tengo varias tiendas (multitienda) habilitadas?**
R: El módulo debe configurarse individualmente para cada tienda en un entorno multitienda. Asegúrese de seleccionar el contexto de tienda correcto en el back office de PrestaShop antes de configurar el módulo para esa tienda específica. Es probable que cada tienda tenga su propio ID de tienda de Pazaruvaj.com único.

## 4. Guía para desarrolladores y webmasters (Arquitectura técnica y mapa de código)

Esta sección proporciona una descripción técnica detallada para desarrolladores y webmasters que trabajan con el módulo MyPazaruvaj.

### 4.1 Descripción general de la arquitectura

El módulo MyPazaruvaj sigue una arquitectura de módulo estándar de PrestaShop, utilizando principalmente la clase `Module` y sus métodos `install()`, `uninstall()` y `getContent()` para la configuración. Su funcionalidad principal está impulsada por eventos, aprovechando los hooks de PrestaShop para interceptar los eventos de confirmación de pedidos y mostrar el consentimiento opcional. El envío de datos a Pazaruvaj.com se maneja directamente dentro del archivo PHP principal del módulo, sin controladores frontales o de administración dedicados, lo que lo convierte en una solución ligera y eficiente.

### 4.2 Controladores (`controllers/`)

Este módulo no utiliza controladores dedicados de front-office o back-office. Toda la lógica de configuración se maneja dentro del método `getContent()` del archivo principal del módulo, y la lógica de visualización del front-office se gestiona directamente a través de las plantillas de hook.

### 4.3 Clases y modelos principales (`classes/`)

Este módulo no define ninguna clase personalizada ni extiende `ObjectModel`. Toda la lógica está contenida dentro de la clase principal `MyPazaruvaj` definida en `mypazaruvaj/index.php`.

La clase principal `MyPazaruvaj` extiende `Module` y contiene:

-   `__construct()`: Establece las propiedades del módulo (nombre, pestaña, versión, autor, `need_instance`, `ps_versions_compliancy`, `bootstrap`).
-   `install()`: Registra los hooks necesarios (`displayOrderConfirmation`, `displayHeader`, `displayFooter`, `displayLeftColumn`, `displayRightColumn`), crea entradas de configuración e inicializa el archivo de registro de errores.
-   `uninstall()`: Desregistra los hooks y elimina las entradas de configuración.
-   `getContent()`: Renderiza el formulario de configuración del back-office del módulo, maneja los envíos de formularios y actualiza los valores de configuración.
-   `hookDisplayOrderConfirmation()`: El hook principal para el envío de datos. Recupera los detalles del pedido, la información del cliente y los datos del producto, luego construye y envía la solicitud a Pazaruvaj.com. También maneja la verificación de consentimiento opcional.
-   `hookDisplayHeader()`, `hookDisplayFooter()`, `hookDisplayLeftColumn()`, `hookDisplayRightColumn()`: Estos hooks se utilizan para mostrar la casilla de verificación de consentimiento si está habilitada y configurada para aparecer en estas ubicaciones. Renderizan la plantilla `consent.tpl`.
-   `_clearLog()`: Método interno para borrar el archivo de registro de errores.
-   `_writeLog()`: Método interno para escribir mensajes en el archivo de registro de errores.
-   `_displayForm()`: Método interno para renderizar el formulario de configuración utilizando `HelperForm` de PrestaShop.

### 4.4 Activos de JavaScript (`views/js/`)

Este módulo no incluye ningún archivo JavaScript personalizado.

### 4.5 Hojas de estilo CSS (`views/css/`)

Este módulo no incluye ningún archivo CSS personalizado. Cualquier estilo para la casilla de verificación de consentimiento se basaría en el estilo predeterminado de los elementos del formulario del tema.

### 4.6 Estructura de plantillas Smarty (`views/templates/`)

-   **Plantillas de hook (`views/templates/hook/`)**:

    -   `mypazaruvaj/views/templates/hook/consent.tpl`:
        -   **Propósito:** Renderiza la casilla de verificación de consentimiento opcional para enviar datos a Pazaruvaj.com.
        -   **Renderizado en hooks:** `displayHeader`, `displayFooter`, `displayLeftColumn`, `displayRightColumn` (dependiendo de la configuración del módulo).
        -   **Variables:** Normalmente verifica `$consent_enabled` y muestra una entrada de formulario.
        -   **Salida:** Una simple casilla de verificación HTML y una etiqueta.
    -   `mypazaruvaj/views/templates/hook/displayOrderConfirmation.tpl`:
        -   **Propósito:** Esta plantilla es probablemente un marcador de posición o se utiliza para la lógica interna del módulo que no genera contenido visible directamente al cliente. La lógica principal de envío de datos para `displayOrderConfirmation` se maneja en el propio método del hook PHP, no necesariamente a través de una salida de plantilla. Podría usarse para pasar variables o activar JS si el módulo tuviera alguno. En el contexto de este módulo, es principalmente el método del hook PHP el que realiza la acción.
-   **Plantillas de administración (`views/templates/admin/`)**:

    -   Este módulo no utiliza plantillas de administración dedicadas. El formulario de configuración se genera programáticamente utilizando `HelperForm` dentro de `getContent()`.
-   **Plantillas de front-office (`views/templates/front/`)**:

    -   Este módulo no incluye ninguna plantilla de front-office dedicada más allá de las plantillas de hook.

### 4.7 Esquema de la base de datos y mapa de hooks

-   **Tablas de la base de datos**:

    -   Este módulo no crea ninguna tabla SQL personalizada.
    -   Almacena sus configuraciones en la tabla estándar `ps_configuration` de PrestaShop.
        -   `MYPAZARUVAJ_SHOP_ID`: Almacena el ID de tienda de Pazaruvaj.com.
        -   `MYPAZARUVAJ_PRODUCT_ID_FIELD`: Almacena el campo de ID de producto seleccionado (por ejemplo, 'id\_product', 'reference').
        -   `MYPAZARUVAJ_CONSENT_ENABLED`: Booleano (0 o 1) para habilitar/deshabilitar el consentimiento.
        -   `MYPAZARUVAJ_CONSENT_HOOK`: Almacena el nombre del hook donde se muestra el consentimiento.
        -   `MYPAZARUVAJ_ERROR_LOG_ENABLED`: Booleano (0 o 1) para habilitar/deshabilitar el registro de errores.
-   **Tabla de hooks registrados**:

| Nombre del Hook | Momento de Ejecución | Propósito Técnico |
| --- | --- | --- |
| `displayOrderConfirmation` | Después de que un cliente completa un pedido con éxito. | **Hook principal para el envío de datos.** Recupera los detalles del pedido y del producto, construye la solicitud de Pazaruvaj.com y la envía. Verifica el consentimiento si está habilitado. |
| `displayHeader` | En la sección `<head>` o en la parte superior de cada página. | Renderiza `consent.tpl` si está configurado para mostrar el consentimiento aquí. |
| `displayFooter` | En la sección del pie de página de cada página. | Renderiza `consent.tpl` si está configurado para mostrar el consentimiento aquí. |
| `displayLeftColumn` | En la columna de la barra lateral izquierda (si está activa en el tema). | Renderiza `consent.tpl` si está configurado para mostrar el consentimiento aquí. |
| `displayRightColumn` | En la columna de la barra lateral derecha (si está activa en el tema). | Renderiza `consent.tpl` si está configurado para mostrar el consentimiento aquí. |

## 5. Soporte oficial y actualizaciones

Para las últimas actualizaciones del módulo, correcciones de errores y soporte oficial, consulte su cuenta de cliente en [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nuestro equipo de soporte está disponible para ayudarle con cualquier problema o pregunta que pueda tener con respecto al módulo MyPazaruvaj.
