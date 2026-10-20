---
title: "Enviar una copia de correos electrónicos (CCO) - Manual del Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop 'Enviar una copia de correos electrónicos (CCO)' de MyPresta.eu."
sidebar:
  label: "Enviar una copia de correos electrónicos (CCO)"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Send a copy of emails (BCC) en MyPresta.eu](https://mypresta.eu/modules/administration-tools/send-a-copy-of-emails-bcc.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/back-office-tools/send-a-copy-of-emails-bcc/)
>
> ---


# Enviar una copia de correos electrónicos (CCO)

## 1. Requisitos y compatibilidad
- **Versiones de PrestaShop compatibles**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilidad con PHP**: PHP 5.6 - 8.5
- **Requisitos de alojamiento**: Las extensiones PHP estándar (cURL, JSON, OpenSSL) suelen ser suficientes. Normalmente no se necesitan configuraciones especiales del servidor.

## 2. Recorrido completo por la configuración (Cada ajuste agrupado por pantalla)

### 2.1 Página de configuración del módulo (Back Office > Módulos > Configurar)
Después de la instalación, al hacer clic en "Configurar" se le dirigirá a la página de configuración principal del módulo.

#### **Actualizaciones y verificación de versión de MyPresta.eu**
En la parte superior de la página de configuración, normalmente verá ajustes relacionados con las actualizaciones de MyPresta.eu. Estos son estándar para los módulos de MyPresta.eu y le ayudan a mantener su módulo actualizado.

-   **Qué hace este ajuste:** Estos campos (a menudo etiquetados como `mypresta_updates`, `update_`, `updatev_`) son utilizados por el módulo para verificar si hay nuevas versiones disponibles en MyPresta.eu e informarle si es necesaria una actualización. Suelen estar prellenados o gestionados automáticamente.
-   **Efecto de cambiar este ajuste:**
    -   *Si está habilitado/activo:* El módulo puede verificar periódicamente si hay actualizaciones, notificándole en el back office de PrestaShop si hay una nueva versión disponible.
    -   *Si está deshabilitado/inactivo:* Es posible que no reciba notificaciones automáticas sobre las actualizaciones del módulo, lo que requerirá verificaciones manuales.
-   **Valor recomendado:** Deje estos ajustes tal como están, generalmente habilitados o gestionados automáticamente, para asegurarse de estar siempre informado sobre las últimas versiones del módulo y las correcciones de seguridad.
-   **Escenario / ejemplo del comerciante:** Desea recibir notificaciones cuando se lance una nueva versión del módulo que incluya nuevas características o correcciones de errores, por lo que mantiene activas estas verificaciones de actualización.

#### **Configuración principal del módulo**
Debajo de la configuración de actualización, encontrará las opciones de configuración principales para la funcionalidad de correo electrónico CCO.

-   **Dirección de correo electrónico para CCO:**
    -   **Qué hace este ajuste:** Este es el ajuste más crucial. Define la dirección de correo electrónico a la que se enviarán todas las copias CCO seleccionadas.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando se establece una dirección de correo electrónico válida:* Todos los correos electrónicos seleccionados en la lista siguiente tendrán una copia oculta enviada a esta dirección.
        -   *Cuando se deja vacío o se establece una dirección no válida:* No se enviarán copias CCO, incluso si se seleccionan correos electrónicos en la lista.
    -   **Valor recomendado:** Una dirección de correo electrónico dedicada para archivar (por ejemplo, `archivo@sutienda.com`, `soporte@sutienda.com` o su correo electrónico de administrador personal).
    -   **Escenario / ejemplo del comerciante:** Desea que todas las confirmaciones de pedido se copien en la bandeja de entrada de su equipo de servicio al cliente, `soporte@sutienda.com`, por lo que introduce esta dirección aquí.

-   **Seleccionar correos electrónicos para CCO:**
    -   **Qué hace este ajuste:** Esta sección presenta una lista de todas las plantillas de correo electrónico (tipos de correos electrónicos) que su tienda PrestaShop puede enviar. Puede seleccionar qué tipos de correo electrónico específicos desea enviar con CCO.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando se marca un tipo de correo electrónico:* Se enviará una copia CCO de ese tipo de correo electrónico específico a la "Dirección de correo electrónico para CCO" cada vez que su tienda lo envíe.
        -   *Cuando se desmarca un tipo de correo electrónico:* No se enviará ninguna copia CCO para ese tipo de correo electrónico específico.
    -   **Valor recomendado:** Seleccione solo los tipos de correo electrónico que son críticos para su mantenimiento de registros o necesidades operativas. Un exceso de CCO puede inundar una bandeja de entrada. Las opciones comunes incluyen:
        -   `order_conf` (Confirmación de pedido)
        -   `shipped` (Pedido enviado)
        -   `contact_form` (Envío de formulario de contacto)
        -   `password` (Restablecimiento de contraseña)
        -   `account` (Creación de nueva cuenta)
    -   **Escenario / ejemplo del comerciante:** Desea mantener un registro de todos los nuevos pedidos y consultas de clientes. Marcaría `order_conf` y `contact_form` de la lista.

### 2.2 Pantallas de administración dedicadas y vistas de controlador

#### **Gestión de CCO de correo (Back Office > Parámetros avanzados > CCO de correo)**
Este módulo crea un elemento de menú dedicado en su back office de PrestaShop en "Parámetros avanzados" (o similar, según la versión de PrestaShop) llamado "CCO de correo". Esta pantalla es gestionada por `AdminMailBccController`.

-   **Nombre de la pantalla y ubicación del menú:** **Parámetros avanzados > CCO de correo**
-   **Acciones y configuraciones disponibles:** Esta pantalla suele presentar una cuadrícula (lista) de todos los tipos de correo electrónico que ha configurado para ser CCO, junto con la dirección de correo electrónico CCO. Actúa como una interfaz de resumen y gestión para sus configuraciones de CCO.
    -   Puede ver columnas como:
        -   **ID:** Identificador interno de la regla CCO.
        -   **Plantilla de correo electrónico:** El nombre de la plantilla de correo electrónico (por ejemplo, `order_conf`).
        -   **Correo electrónico CCO:** La dirección de correo electrónico a la que se envía la copia.
        -   **Habilitado:** Un interruptor para habilitar o deshabilitar rápidamente el CCO para ese tipo de correo electrónico específico.
        -   **Acciones:** Botones para editar o eliminar la regla CCO (aunque a menudo, la página de configuración principal del módulo se utiliza para la selección masiva).
-   **Efecto de los cambios:**
    -   *Habilitar/Deshabilitar una regla:* Controla directamente si se envía una copia CCO para ese tipo de correo electrónico específico.
    -   *Editar una regla:* Le permite cambiar la dirección de correo electrónico CCO para un tipo de correo electrónico específico (si el módulo admite direcciones CCO por correo electrónico, de lo contrario, reflejará la configuración global).
    -   *Eliminar una regla:* Elimina la configuración CCO para ese tipo de correo electrónico.
-   **Flujo de trabajo recomendado para la gestión diaria de la tienda:** Utilice esta pantalla para revisar rápidamente qué correos electrónicos se están enviando con CCO y para realizar cambios rápidos de habilitación/deshabilitación sin volver a la configuración principal del módulo. Para agregar nuevos tipos de correo electrónico o cambiar la dirección CCO principal, la página de configuración principal del módulo suele ser más eficiente.

#### **index.php (bccmail/controllers/admin/index.php)**
Este archivo es una práctica estándar de PrestaShop para proteger los directorios de los controladores de administración y, por lo general, no presenta una pantalla de usuario ni opciones de configuración directamente. Suele contener un simple `header('Location: ../../index.php?controller=AdminHome');` o similar para redirigir el acceso no autorizado, evitando la navegación directa del directorio. Los comerciantes no interactuarán con este archivo.

### 2.3 Tabla de referencia rápida de configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
|---|---|---|---|
| **Página de configuración del módulo** | Actualizaciones de MyPresta.eu | Habilitado | Le mantiene informado sobre las actualizaciones del módulo. |
| | **Dirección de correo electrónico para CCO** | Su correo electrónico de administrador / `archivo@sutienda.com` | El correo electrónico de destino para todas las copias CCO. Crítico para el archivo. |
| | **Seleccionar correos electrónicos para CCO** | `order_conf`, `contact_form`, `shipped` | Elija qué tipos de correo electrónico específicos copiar. Evita la inundación de la bandeja de entrada. |
| **Parámetros avanzados > CCO de correo** | Lista de plantillas de correo electrónico | Varía según la selección | Resumen y alternancia rápida para los tipos de correo electrónico CCO configurados. |
| | Alternar habilitado | Habilitado | Activa/desactiva rápidamente el CCO para un tipo de correo electrónico específico. |

## 3. Solución de problemas del comerciante y preguntas frecuentes (FAQ)

**P: He configurado el módulo, pero no recibo ningún correo electrónico CCO. ¿Qué debo verificar?**
R:
1.  **Verifique la dirección de correo electrónico CCO:** Vaya a **Módulos > Gestor de módulos > Configurar** para "Enviar una copia de correos electrónicos (CCO)" y asegúrese de que la "Dirección de correo electrónico para CCO" esté correctamente escrita y sea válida.
2.  **Verifique los tipos de correo electrónico seleccionados:** Asegúrese de que los tipos de correo electrónico específicos que espera que se copien (por ejemplo, `order_conf`) estén realmente marcados en la configuración del módulo.
3.  **Revise la carpeta de spam:** Los correos electrónicos CCO podrían estar llegando a la carpeta de spam o correo no deseado de la bandeja de entrada del destinatario CCO.
4.  **Configuración de correo electrónico de PrestaShop:** Asegúrese de que la configuración general de correo electrónico de su tienda PrestaShop (**Parámetros avanzados > Correo electrónico**) esté configurada correctamente y que su tienda pueda enviar correos electrónicos en general. Pruebe enviando un correo electrónico de prueba desde PrestaShop.
5.  **Borrar caché:** A veces, la caché de PrestaShop puede evitar que los cambios surtan efecto inmediatamente. Vaya a **Parámetros avanzados > Rendimiento** y haga clic en "Borrar caché" (o "Borrar caché de Smarty" en versiones anteriores).

**P: ¿Puedo enviar copias CCO a varias direcciones de correo electrónico?**
R: La configuración principal del módulo permite una dirección de correo electrónico CCO principal. Si necesita enviar copias a varias direcciones, tiene dos opciones:
1.  Establezca la dirección de correo electrónico CCO en una lista de distribución o dirección de correo electrónico de grupo que reenvíe a varios destinatarios.
2.  Configure una regla de correo electrónico en la bandeja de entrada del destinatario CCO para reenviar automáticamente copias a otras direcciones según el remitente o el asunto.

**P: ¿Este módulo ralentizará mi tienda o el envío de correos electrónicos?**
R: El impacto en el rendimiento es generalmente insignificante. Enviar una copia CCO adicional es una operación muy pequeña para el servidor de correo. El módulo utiliza el mecanismo estándar de envío de correo electrónico de PrestaShop, simplemente agregando un destinatario adicional.

**P: Mi tema personalizado tiene plantillas de correo electrónico personalizadas. ¿Seguirá funcionando este módulo?**
R: Sí, el módulo se conecta a la clase `Mail` central de PrestaShop, que es responsable de enviar todos los correos electrónicos, independientemente de si utilizan plantillas predeterminadas o personalizadas. Siempre que PrestaShop esté enviando el correo electrónico, este módulo puede enviarlo con CCO.

**P: ¿Cómo traduzco la interfaz del módulo a otro idioma?**
R: Vaya a **Internacional > Traducciones** en su back office de PrestaShop. Seleccione "Traducciones de módulos instalados", elija su tema y luego seleccione "Enviar una copia de correos electrónicos (CCO)". Luego podrá traducir cualquier cadena mostrada por el módulo en el back office.

## 4. Guía para desarrolladores y webmasters (Arquitectura técnica y mapa de código)

Esta sección proporciona una inmersión profunda en la implementación técnica del módulo "Enviar una copia de correos electrónicos (CCO)" para desarrolladores y webmasters.

### 4.1 Resumen de la arquitectura
El módulo "Enviar una copia de correos electrónicos (CCO)" (`bccmail`) funciona principalmente anulando la clase `Mail` central de PrestaShop. Esta es una técnica común y potente en PrestaShop para modificar el comportamiento central sin editar directamente los archivos centrales. Al anular `Mail.php`, el módulo intercepta todas las operaciones de envío de correo electrónico e inyecta la funcionalidad CCO según su configuración. Sigue una estructura de módulo estándar de PrestaShop con un archivo de módulo principal, controladores de administración para la configuración y una clase de anulación.

### 4.2 Controladores (`controllers/`)

-   **Controladores de Front-Office**: Este módulo no tiene controladores de front-office dedicados, ya que su funcionalidad es completamente de back-office y del lado del servidor.

-   **Controladores de administración de Back-Office**:
    *   `bccmail/controllers/admin/AdminMailBcc.php`
        *   **Nombre de la clase y clase padre:** `AdminMailBccController` extiende `ModuleAdminController`.
        *   **Nombre de la pestaña y entidad gestionada:** Este controlador gestiona la pestaña "CCO de correo" en "Parámetros avanzados". Es responsable de mostrar y gestionar la lista de tipos de correo electrónico CCO configurados. Probablemente utiliza `HelperList` o `HelperView` de PrestaShop para renderizar una cuadrícula de objetos `MailBcc` (o una representación de la configuración del módulo).
        *   **Responsabilidad:** Maneja la visualización del resumen de la configuración CCO, permitiendo potencialmente la activación/desactivación o eliminación de reglas individuales. Interactúa con los datos de configuración del módulo (probablemente almacenados en `ps_configuration` o una tabla personalizada si se necesitan datos más complejos por regla CCO).
    *   `bccmail/controllers/admin/index.php`
        *   **Nombre de la clase y clase padre:** No es una clase, sino un archivo de seguridad.
        *   **Responsabilidad:** Este archivo es una medida de seguridad estándar de PrestaShop. Normalmente contiene `header('Location: ../../index.php?controller=AdminHome');` o similar para evitar la lista directa de directorios y el acceso no autorizado al directorio `controllers/admin`. No proporciona ninguna lógica funcional para el módulo en sí.

### 4.3 Clases y modelos principales (`classes/`)

-   `bccmail/override/classes/Mail.php`
    *   **Con qué tabla de base de datos interactúa:** Interactúa indirectamente con `ps_configuration` para recuperar la configuración del módulo (dirección de correo electrónico CCO y plantillas de correo electrónico seleccionadas).
    *   **Si extiende `ObjectModel`:** No, anula la clase `Mail` central.
    *   **Métodos públicos clave y lógica de negocio encapsulada:**
        *   Este archivo contiene la lógica central para interceptar el envío de correo electrónico. Anula el método `send()` (o un método similar) de la clase `Mail` original.
        *   Dentro del método `send()` anulado, hará lo siguiente:
            1.  Recuperar la configuración del módulo: la dirección de correo electrónico CCO global y la lista de plantillas de correo electrónico seleccionadas para CCO.
            2.  Verificar si el correo electrónico actual que se está enviando (identificado por el nombre de su plantilla, por ejemplo, `order_conf`) está en la lista de plantillas CCO seleccionadas.
            3.  Si se encuentra una coincidencia, modifica los encabezados o parámetros del correo electrónico para incluir la dirección de correo electrónico CCO configurada antes de llamar al método `Mail::send()` padre para enviar el correo electrónico.
        *   Esto asegura que el destinatario CCO se agregue a la lista de copia oculta del correo electrónico, haciéndolos invisibles para los destinatarios principales.

-   `bccmail/override/classes/index.php`
    *   **Responsabilidad:** Similar a `controllers/admin/index.php`, este es un archivo de seguridad para evitar la lista directa de directorios del directorio `override/classes`. Normalmente contiene una etiqueta PHP en blanco o una redirección.

### 4.4 Activos de JavaScript (`views/js/`)

-   `bccmail/views/templates/admin/js/bccmail.js`
    *   **Alcance:** Back-office.
    *   **Qué escuchadores de eventos vincula:** Este script probablemente se usa en la página de configuración del módulo o en la pantalla `AdminMailBccController`. Podría vincular escuchadores para:
        *   Eventos de envío de formularios para manejar el guardado de la configuración.
        *   Cambios de casilla de verificación para seleccionar plantillas de correo electrónico para CCO.
        *   Validación de campos de entrada para la dirección de correo electrónico CCO.
        *   Llamadas AJAX para actualizar la configuración dinámicamente sin una recarga completa de la página.
    *   **Qué manipulación del DOM, ventanas emergentes modales, animaciones o llamadas a SDK de terceros ejecuta:** Podría realizar manipulaciones simples del DOM como mostrar/ocultar elementos basados en selecciones, mostrar mensajes de éxito/error o validación básica de formularios. Es poco probable que involucre animaciones complejas o SDK de terceros para la funcionalidad de este módulo.

### 4.5 Hojas de estilo CSS (`views/css/`)
El módulo no parece incluir ningún archivo CSS personalizado en su archivo. Probablemente se basa en el estilo predeterminado del back-office de PrestaShop para sus formularios y listas de configuración, o en estilos en línea si es absolutamente necesario.

### 4.6 Estructura de plantillas Smarty (`views/templates/`)

-   **Plantillas de gancho (`views/templates/hook/`)**: Ninguna explícitamente listada, pero el formulario de configuración principal del módulo (`getContent()`) renderizaría sus ajustes utilizando una plantilla Smarty, típicamente ubicada en `views/templates/admin/configure.tpl` o similar, incluso si no está explícitamente listada en el inventario como un archivo separado.
-   **Plantillas de administración (`views/templates/admin/`)**:
    *   `bccmail/lib/searchTool/views/scripts.tpl`
        *   **Propósito:** Esta plantilla es probablemente parte de una biblioteca de ayuda o utilidad dentro del módulo (por ejemplo, una herramienta de búsqueda para plantillas de correo electrónico). Contendría lógica JavaScript o Smarty para renderizar entradas de búsqueda, filtrar listas o manejar la carga dinámica de contenido dentro de la interfaz de administración. No es una página independiente, sino un componente.
-   **Plantillas de front-office (`views/templates/front/`)**: Ninguna. El módulo no tiene presencia en el front-office.

### 4.7 Esquema de la base de datos y mapa de ganchos

-   **Tablas de la base de datos**:
    *   El módulo almacena principalmente su configuración en la tabla `ps_configuration` de PrestaShop.
        *   Las claves de `PS_CONFIGURATION` incluirían:
            *   `BCCMAIL_EMAIL_ADDRESS`: Almacena la dirección de correo electrónico principal para CCO.
            *   `BCCMAIL_SELECTED_TEMPLATES`: Almacena una matriz serializada o una cadena separada por comas de los nombres de las plantillas de correo electrónico seleccionadas para CCO.
            *   `MYPRESTA_UPDATES`, `UPDATE_`, `UPDATEV_`: Para las comprobaciones de actualización del módulo.
    *   No se crean tablas SQL personalizadas explícitamente por este módulo según el inventario proporcionado.

-   **Tabla de ganchos registrados**:
    El módulo no registra ningún gancho de visualización estándar (como `displayHeader`, `displayRightColumn`, `displayFooter`) ya que no tiene presencia en el front-office. Su funcionalidad principal se basa en anular la clase `Mail` en lugar de utilizar los ganchos tradicionales de PrestaShop para el envío de correo electrónico.

    Sin embargo, "se engancha" implícitamente en el proceso de envío de correo electrónico a través de su anulación.
    *   **`actionEmailSend` (Implícito a través de anulación)**: Aunque no es un gancho formalmente registrado, el archivo `override/classes/Mail.php` del módulo intercepta efectivamente el método `Mail::send()`, que es la acción central de enviar un correo electrónico. Aquí es donde se inyecta la lógica CCO.
        *   **Momento de ejecución:** Cada vez que PrestaShop llama a `Mail::send()` (por ejemplo, en la confirmación de un pedido, el registro de un cliente, el envío de un formulario de contacto).
        *   **Propósito técnico:** Agregar el destinatario CCO configurado al correo electrónico antes de que sea enviado por el sistema de correo de PrestaShop.

## 5. Soporte oficial y actualizaciones
Para las últimas actualizaciones del módulo, soporte técnico y recursos adicionales, visite su cuenta de cliente en [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nuestro equipo de soporte está disponible para ayudarle con cualquier problema o pregunta que pueda tener con respecto al módulo "Enviar una copia de correos electrónicos (CCO)".
