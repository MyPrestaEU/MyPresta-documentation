---
title: "Archivos adjuntos solo para usuarios registrados - Manual de comerciante y guía de configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop 'Archivos adjuntos solo para usuarios registrados' de MyPresta.eu."
sidebar:
  label: "Archivos adjuntos solo para usuarios registrados - Manual de comerciante y guía de configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Attachments for logged users only en MyPresta.eu](https://mypresta.eu/modules/front-office-features/attachments-for-logged-users-only.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/front-office/attachments-for-logged-users-only/)
>
> ---


# Archivos adjuntos solo para usuarios registrados

## 1. Requisitos y compatibilidad

- **Versiones de PrestaShop compatibles**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilidad con PHP**: PHP 5.6 - 8.5
- **Requisitos de alojamiento**: Las extensiones PHP estándar (cURL, JSON, OpenSSL) suelen ser suficientes. Normalmente no se necesitan configuraciones especiales del servidor.

## 2. Recorrido completo por la configuración (Cada ajuste agrupado por pantalla)

### 2.1 Página de configuración del módulo (Back Office > Módulos > Configurar)

Después de instalar el módulo, haga clic en "Configurar" para acceder a sus ajustes. Esta es la pantalla principal donde controla el comportamiento del módulo.

#### **Activar función**

- **Qué hace este ajuste:** Este es el interruptor principal del módulo. Determina si la función de restricción de archivos adjuntos está activa o inactiva en su tienda.
- **Efecto de cambiar este ajuste:**
  - *Cuando está habilitado ("Activado"):* El módulo restringirá activamente las descargas de archivos adjuntos de productos solo a clientes que hayan iniciado sesión. Los usuarios que no hayan iniciado sesión no podrán descargar archivos adjuntos.
  - *Cuando está deshabilitado ("Desactivado"):* El módulo estará inactivo. Los archivos adjuntos de productos se comportarán como lo hacen por defecto en PrestaShop, lo que significa que cualquiera (registrado o invitado) puede descargarlos.
- **Valor recomendado:** "Activado" si desea restringir las descargas de archivos adjuntos.
- **Escenario / ejemplo de comerciante:** Si desea comenzar a requerir que los clientes inicien sesión para descargar manuales, establezca esto en "Activado". Si está probando o desea volver temporalmente al comportamiento predeterminado de PrestaShop, configúrelo en "Desactivado".

#### **Descargar solo para clientes**

- **Qué hace este ajuste:** Este ajuste refina la "Activar función" permitiéndole especificar *qué* clientes pueden descargar archivos adjuntos basándose en su historial de pedidos.
- **Efecto de cambiar este ajuste:**
  - *Cuando está habilitado:* Solo los clientes que han iniciado sesión Y tienen al menos un pedido con un estado seleccionado (ver "Seleccionar estados de pedido" a continuación) podrán descargar archivos adjuntos. Esto añade una capa extra de exclusividad.
  - *Cuando está deshabilitado:* Cualquier cliente que haya iniciado sesión (independientemente de su historial de pedidos) podrá descargar archivos adjuntos, siempre que la "Activar función" esté habilitada.
- **Valor recomendado:** "Desactivado" para la mayoría de los casos, permitiendo que cualquier cliente que haya iniciado sesión descargue. "Activado" si desea ofrecer archivos adjuntos como un beneficio para los clientes *de pago*.
- **Escenario / ejemplo de comerciante:** Usted vende software y desea proporcionar actualizaciones o guías premium solo a los clientes que realmente han comprado el software. Habilitaría este ajuste y seleccionaría "Pago aceptado" en la opción "Seleccionar estados de pedido".

#### **Seleccionar estados de pedido**

- **Qué hace este ajuste:** Esta opción aparece solo si "Descargar solo para clientes" está habilitado. Le permite elegir qué estados de pedido califican a un cliente para descargar archivos adjuntos. Un cliente debe tener al menos un pedido con uno de los estados seleccionados para obtener acceso.
- **Efecto de cambiar este ajuste:**
  - *Cuando se selecciona uno o más estados:* Solo los clientes que han iniciado sesión con un pedido que coincide con uno de estos estados pueden descargar archivos adjuntos.
  - *Cuando no se selecciona ningún estado (y "Descargar solo para clientes" está habilitado):* Esta configuración podría llevar a que ningún cliente pueda descargar, ya que no se definen estados de pedido que califiquen. Es crucial seleccionar al menos un estado si habilita "Descargar solo para clientes".
- **Valor recomendado:** Si "Descargar solo para clientes" está habilitado, seleccione estados relevantes como "Pago aceptado", "Entregado" o "Enviado" para otorgar acceso a los clientes que han completado un pedido con éxito.
- **Escenario / ejemplo de comerciante:** Si desea dar acceso a los archivos adjuntos solo a los clientes cuyos pedidos han sido pagados y procesados con éxito, seleccionaría "Pago aceptado" y "Entregado". Esto evita que los clientes con pedidos pendientes o cancelados accedan a los archivos.

### 2.2 Tabla de referencia rápida de configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| Configuración del módulo | Activar función | Activado | Interruptor principal para habilitar/deshabilitar la restricción de archivos adjuntos. |
| Configuración del módulo | Descargar solo para clientes | Desactivado | Si está habilitado, solo los clientes registrados con estados de pedido específicos pueden descargar. |
| Configuración del módulo | Seleccionar estados de pedido | (Ninguno seleccionado) | Si "Descargar solo para clientes" está activo, seleccione los estados de pedido que otorgan acceso a la descarga. |

## 3. Solución de problemas para comerciantes y preguntas frecuentes (FAQ)

**P: Mis archivos adjuntos siguen siendo descargables por todos, incluso después de habilitar el módulo. ¿Qué está mal?**
R:

1. **Verifique "Activar función":** Asegúrese de que la configuración "Activar función" en la página de configuración del módulo esté establecida en "Activado".
2. **Borrar caché:** PrestaShop utiliza caché. Vaya a **Parámetros avanzados > Rendimiento** y haga clic en "Borrar caché" (o "Borrar caché de Smarty" en versiones anteriores). Esto a menudo resuelve problemas de visualización después de cambios en la configuración del módulo.
3. **Posición del módulo:** Asegúrese de que el módulo esté enganchado correctamente. Aunque el módulo lo maneja automáticamente, a veces pueden ocurrir conflictos de tema.

**P: He habilitado "Descargar solo para clientes" y he seleccionado estados de pedido, pero mis clientes registrados aún no pueden descargar.**
R:

1. **Verificar estado del pedido:** Verifique que el cliente que intenta descargar realmente tenga un pedido con uno de los estados *exactos* que seleccionó en "Seleccionar estados de pedido".
2. **Inicio de sesión del cliente:** Confirme que el cliente ha iniciado sesión en su cuenta.
3. **Caché:** Borre la caché de su PrestaShop (Parámetros avanzados > Rendimiento).

**P: ¿Cómo traduzco los mensajes que se muestran a los usuarios no registrados?**
R: El módulo debería integrarse con el sistema de traducción de PrestaShop.

1. Vaya a **Internacional > Traducciones**.
2. Seleccione "Traducciones de módulos instalados".
3. Elija su tema, su idioma y luego el módulo "Archivos adjuntos solo para usuarios registrados".
4. Debería encontrar las cadenas de texto relevantes allí para traducir.

**P: ¿Funcionará este módulo con mi tema personalizado?**
R: Sí, el módulo está diseñado para funcionar con los mecanismos estándar de archivos adjuntos de PrestaShop. Principalmente intercepta la solicitud de descarga en lugar de modificar en gran medida la visualización visual de los archivos adjuntos. Sin embargo, si su tema personalizado anula completamente la forma en que se muestran o enlazan los archivos adjuntos, podrían ser necesarios pequeños ajustes. Siempre pruebe a fondo después de la instalación.

## 4. Guía para desarrolladores y webmasters (Arquitectura técnica y mapa de código)

### 4.1 Resumen de la arquitectura

El módulo "Archivos adjuntos solo para usuarios registrados" opera principalmente anulando el `AttachmentController` predeterminado para interceptar las solicitudes de descarga. Aprovecha el sistema de hooks de PrestaShop (`displayHeader`, `header`) para inyectar JavaScript y CSS necesarios, y su lógica principal reside en el archivo `atlogged.php`, que maneja la configuración y la anulación central. El módulo utiliza una estructura de configuración simple almacenada en `ps_configuration` e incluye controladores de front-office para interacciones AJAX y lógica de respaldo potencial.

### 4.2 Controladores (`controllers/`)

#### Controladores de Front-Office

- `atlogged/controllers/front/index.php`

  - **Nombre de la clase:** `AtloggedIndexModuleFrontController` (probablemente, basado en la convención de nombres de archivos)
  - **Clase padre:** `ModuleFrontController`
  - **Responsabilidad:** Este controlador podría servir como un punto de entrada general para acciones específicas del módulo en el front-office, potencialmente manejando redirecciones o mostrando mensajes cuando se restringe la descarga de un archivo adjunto. También podría ser un marcador de posición o usarse para enrutamiento específico.
- `atlogged/controllers/front/popuploader.php`

  - **Nombre de la clase:** `AtloggedPopuploaderModuleFrontController`
  - **Clase padre:** `ModuleFrontController`
  - **Responsabilidad:** Este controlador probablemente maneja las solicitudes AJAX relacionadas con la visualización de un mensaje de inicio de sesión/registro o un mensaje específico cuando un usuario intenta descargar un archivo adjunto restringido. Podría renderizar una pequeña plantilla (por ejemplo, `atlogged-ajax.tpl`) con el contenido apropiado.
- `atlogged/override/controllers/front/AttachmentController.php`

  - **Nombre de la clase:** `AttachmentController` (anula la clase principal)
  - **Clase padre:** `AttachmentControllerCore`
  - **Responsabilidad:** Esta es la parte más crítica de la lógica del front-office del módulo. Anula directamente el `AttachmentController` principal de PrestaShop. Su función principal es:
    1. Verificar si el módulo está habilitado (`ATLOGGED_ON`).
    2. Verificar si el usuario actual ha iniciado sesión.
    3. Si `ATLOGGED_C_ON` (Descargar solo para clientes) está habilitado, verifica además el historial de pedidos del usuario con los `atlogged_ostates` configurados.
    4. Si el usuario no cumple con los criterios, evita el proceso de descarga de archivos adjuntos predeterminado y, en su lugar, redirige al usuario o activa una acción específica del módulo (por ejemplo, mostrando un mensaje de inicio de sesión a través de AJAX).
- `atlogged/override/controllers/front/index.php`

  - **Nombre de la clase:** `IndexController` (anula la clase principal)
  - **Clase padre:** `IndexControllerCore`
  - **Responsabilidad:** Anular el `IndexController` es menos común para la lógica específica de archivos adjuntos. Esto podría usarse para:
    1. Comprobaciones globales o redirecciones relacionadas con el módulo en la página de inicio.
    2. Asegurar que ciertos activos específicos del módulo (JS/CSS) se carguen globalmente.
    3. Potencialmente manejar una redirección a la página de inicio de sesión si se accede a un enlace de archivo adjunto directamente sin haber iniciado sesión desde el contexto de la página de inicio.

#### Controladores de administración de Back-Office

- Ninguno identificado. La configuración del módulo se maneja directamente dentro del método `getContent()` del archivo principal del módulo.

### 4.3 Clases y modelos principales (`classes/`)

- Ninguno identificado. El módulo no parece definir clases `ObjectModel` personalizadas. Probablemente funciona directamente con objetos principales existentes de PrestaShop (por ejemplo, `Customer`, `Order`, `Attachment`) y valores de configuración.

### 4.4 Activos JavaScript (`views/js/`)

- `atlogged/views/js/atlogged.js`
  - **Alcance:** Front-office.
  - **Detalles:** Este script es probablemente responsable de:
    1. Interceptar clics en enlaces de descarga de archivos adjuntos (`<a>` con clases o atributos de datos específicos).
    2. Realizar llamadas AJAX a los controladores de front-office `popuploader.php` o `index.php` cuando un usuario no calificado intenta una descarga restringida.
    3. Mostrar ventanas emergentes modales o mensajes (por ejemplo, "Por favor, inicie sesión para descargar") basándose en la respuesta AJAX.
    4. Potencialmente redirigir a los usuarios a la página de inicio de sesión si la respuesta AJAX lo indica.
    5. Asegurar que la experiencia del usuario sea fluida cuando se deniega el acceso.

### 4.5 Hojas de estilo CSS (`views/css/`)

- `atlogged/views/css/atlogged.css`
  - **Alcance:** Estilo del cliente del front-office.
  - **Detalles:** Esta hoja de estilo proporciona el estilo necesario para cualquier elemento personalizado introducido por el módulo, como:
    1. Estilo para el modal o cuadro de mensaje de inicio de sesión/registro.
    2. Ajustes a la apariencia del enlace del archivo adjunto si están deshabilitados o alterados visualmente cuando están restringidos.
  - **Selectores de clase CSS clave que los desarrolladores pueden anular:** Los desarrolladores deben inspeccionar la salida HTML generada por las plantillas del módulo (por ejemplo, `atlogged-ajax.tpl`) para identificar clases específicas (por ejemplo, `.atlogged-modal`, `.atlogged-message`, `.atlogged-login-button`) para la integración y personalización del tema.

### 4.6 Estructura de la plantilla Smarty (`views/templates/`)

- **Plantillas de administración (`views/templates/admin/`)**:

  - `atlogged/views/templates/admin/orderstates.tpl`
    - **Propósito:** Esta plantilla se utiliza dentro del método `getContent()` del módulo en el Back Office. Renderiza la lista de estados de pedido (`atlogged_ostates`) para la opción de configuración "Seleccionar estados de pedido", típicamente como un menú desplegable de selección múltiple o una lista de casillas de verificación.
- **Plantillas de front-office (`views/templates/front/`)**:

  - `atlogged/views/templates/front/atlogged-ajax.tpl`
    - **Propósito:** Esta plantilla es probablemente renderizada por el controlador de front-office `popuploader.php` en respuesta a una solicitud AJAX. Contiene el contenido HTML para el mensaje que se muestra a los usuarios que no pueden descargar un archivo adjunto (por ejemplo, "Por favor, inicie sesión para continuar", con enlaces para iniciar sesión/registrarse).
  - `atlogged/views/templates/front/atlogged.tpl`
    - **Propósito:** Esta plantilla podría incluirse a través de un hook (por ejemplo, `displayHeader`) o directamente por un controlador de front-office. Podría contener:
      1. Elementos ocultos o atributos de datos utilizados por `atlogged.js`.
      2. Configuración inicial o variables de configuración para JavaScript.
      3. Mensajes de respaldo o elementos que siempre están presentes pero que se muestran condicionalmente por JS.

### 4.7 Esquema de la base de datos y mapa de hooks

- **Tablas de la base de datos**:

  - El módulo no crea tablas SQL personalizadas.
  - Los registros de configuración se almacenan en la tabla `ps_configuration`:
    - `ATLOGGED_ON`: Almacena el valor booleano para la configuración "Activar función".
    - `ATLOGGED_C_ON`: Almacena el valor booleano para la configuración "Descargar solo para clientes".
    - `atlogged_ostates`: Almacena una matriz serializada o una cadena separada por comas de los ID de estado de pedido seleccionados para la configuración "Seleccionar estados de pedido".
    - `mypresta_updates`, `update_`, `updatev_`: Utilizados para las comprobaciones de actualización del módulo por MyPresta.eu.
    - `PS_BO_ALLOW_EMPLOYEE_FORM_LANG`: Una clave de configuración principal de PrestaShop, probablemente accedida para el contexto de idioma en el Back Office.
- **Tabla de hooks registrados**:

  | Nombre del Hook | Momento de ejecución | Propósito técnico |
  | --- | --- | --- |
  | `displayHeader` | En la sección `<head>` de cada página del front-office. | Se utiliza para inyectar `atlogged.js` y `atlogged.css` en la página, asegurando que la lógica y el estilo del lado del cliente del módulo se carguen. |
  | `header` | Alias para `displayHeader` en algunas versiones/contextos de PrestaShop. | Mismo propósito que `displayHeader`. |
  | `actionFrontControllerSetMedia` | Cuando un controlador de front-office está configurando sus activos multimedia. | Podría usarse para cargar condicionalmente JS/CSS solo en páginas específicas (por ejemplo, páginas de productos) para optimización del rendimiento. |
  | `actionDispatcherBefore` | Antes de que se despache un controlador de front-office. | Potencialmente utilizado por la anulación de `AttachmentController` para interceptar la solicitud de descarga muy temprano. |

## 5. Soporte oficial y actualizaciones

Para obtener las últimas actualizaciones, correcciones de errores y soporte técnico dedicado para el módulo "Archivos adjuntos solo para usuarios registrados", consulte su cuenta de cliente en [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nuestro equipo de soporte está listo para ayudarle con cualquier pregunta o problema que pueda encontrar.
