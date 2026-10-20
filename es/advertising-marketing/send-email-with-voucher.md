---
title: "Enviar correo electrónico con vale - Manual de comerciante y guía de configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop 'Enviar correo electrónico con vale' de MyPresta.eu."
sidebar:
  label: "Enviar correo electrónico con vale - Manual de comerciante y guía de configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Send email with voucher en MyPresta.eu](https://mypresta.eu/modules/advertising-and-marketing/send-email-with-voucher.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/advertising-marketing/send-email-with-voucher/)
>
> ---


# Enviar correo electrónico con vale

## 1. Requisitos y compatibilidad

- **Versiones de PrestaShop compatibles**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilidad con PHP**: PHP 5.6 - 8.5
- **Requisitos de alojamiento**: Las extensiones PHP estándar (cURL, JSON, OpenSSL) suelen ser necesarias para PrestaShop y normalmente están disponibles en cualquier entorno de alojamiento moderno.

## 2. Recorrido completo por la configuración (Cada ajuste agrupado por pantalla)

### 2.1 Página de configuración del módulo (Back Office > Módulos > Configurar > Enviar correo electrónico con vale)

Esta es la pantalla de configuración principal donde gestiona los ajustes para enviar sus correos electrónicos con vales.

#### **Sección Gestor de plantillas de correo electrónico**

Esta sección es donde define el contenido y la apariencia de los correos electrónicos que llevarán sus códigos de vale.

- **Qué hace esta sección:** Esta potente herramienta le permite crear, editar y gestionar diferentes plantillas de correo electrónico. Cada plantilla puede tener su propia línea de asunto y contenido del cuerpo, lo que facilita el envío de varios tipos de ofertas de vales (por ejemplo, "Descuento de bienvenida", "Regalo de cumpleaños", "Oferta de carrito abandonado").
- **Efecto de cambiar la configuración:**
  - *Crear una nueva plantilla:* Define un nuevo diseño de correo electrónico y una línea de asunto que podrá seleccionar más tarde al enviar vales.
  - *Editar una plantilla existente:* Los cambios en el asunto o el contenido se aplicarán a todos los correos electrónicos futuros enviados utilizando esa plantilla específica.
  - *Eliminar una plantilla:* La plantilla ya no estará disponible para su selección.
- **Flujo de trabajo recomendado:** Comience creando algunas plantillas estándar para sus campañas de vales más comunes. Por ejemplo, una plantilla de "Bienvenida" para nuevos clientes, una plantilla de "Lealtad" para compradores recurrentes y una plantilla de "Oferta especial" para promociones.

#### **Sección Motor de vales**

Esta sección es donde realmente genera y envía los códigos de vale.

- **Qué hace esta sección:** Esta es la funcionalidad principal para crear reglas de descuento (vales) y enviarlas a direcciones de correo electrónico específicas. Puede definir el tipo de descuento (porcentaje, cantidad fija), el valor, las condiciones (compra mínima, productos específicos) y el período de validez.
- **Efecto de cambiar la configuración:**
  - *Crear un nuevo vale:* Se crea una nueva regla de descuento en su catálogo de PrestaShop y se genera un código único.
  - *Enviar un vale:* Se envía un correo electrónico que contiene el código único y el contenido de la plantilla seleccionada a los destinatarios especificados.
  - *Asociar con un cliente:* El vale se puede vincular a la cuenta de un cliente específico, lo que significa que solo ese cliente puede usarlo.
- **Flujo de trabajo recomendado:**
  1. Primero, cree o seleccione una plantilla de correo electrónico adecuada en la sección "Gestor de plantillas de correo electrónico".
  2. Luego, use el "Motor de vales" para definir sus parámetros de descuento (por ejemplo, 10% de descuento, válido por 30 días, compra mínima de 50 €).
  3. Especifique la(s) dirección(es) de correo electrónico del destinatario.
  4. Elija si desea asociar el vale con una cuenta de cliente existente.
  5. Haga clic en "Enviar" para generar y enviar el vale personalizado.

#### **Configuraciones específicas dentro de la página de configuración**

Si bien la interfaz principal del módulo es a través de las secciones "Gestor de plantillas de correo electrónico" y "Motor de vales", existen claves de configuración subyacentes que controlan el comportamiento predeterminado. Estas a menudo se gestionan implícitamente por la interfaz del módulo, pero es bueno comprender su propósito.

- **Título del correo**

  - **Qué hace esta configuración:** Esta es la línea de asunto predeterminada para los correos electrónicos enviados con vales, si no es anulada por una plantilla específica.
  - **Efecto de cambiar esta configuración:**
    - *Cuando se establece en "Su descuento especial":* Los correos electrónicos tendrán esta línea de asunto por defecto.
    - *Cuando se cambia a "Oferta exclusiva de [Nombre de su tienda]":* Todos los nuevos correos electrónicos (sin una plantilla específica que lo anule) usarán este nuevo asunto.
  - **Valor recomendado:** Algo claro y atractivo, como "Su vale exclusivo de [Nombre de su tienda]".
  - **Escenario / ejemplo de comerciante:** Desea que todos sus correos electrónicos de vales tengan un mensaje de marca consistente en la línea de asunto.
- **Archivo de plantilla de correo electrónico**

  - **Qué hace esta configuración:** Se refiere al archivo de plantilla de correo electrónico predeterminado utilizado para enviar vales. La sección "Gestor de plantillas de correo electrónico" proporciona una forma más fácil de usar para gestionar y seleccionar plantillas.
  - **Efecto de cambiar esta configuración:**
    - *Cuando se establece en `voucher_email.html`:* El módulo utilizará este archivo específico para el cuerpo del correo electrónico si no se selecciona otra plantilla.
  - **Valor recomendado:** Utilice la interfaz del "Gestor de plantillas de correo electrónico" para crear y seleccionar plantillas, ya que es más flexible y no requiere manipulación directa de archivos.
  - **Escenario / ejemplo de comerciante:** Tiene un archivo de plantilla de correo electrónico HTML personalizado que desea utilizar como base para todos sus correos electrónicos de vales.

#### **Otras claves de configuración (Internas)**

Estas son claves de configuración internas de PrestaShop que el módulo podría referenciar para sus operaciones, pero que normalmente no configurará directamente dentro de la interfaz del módulo.

- `PS_SHOP_EMAIL`: La dirección de correo electrónico de contacto principal de su tienda. Se utiliza como correo electrónico del remitente para los vales.
- `PS_SHOP_NAME`: El nombre de su tienda. Se utiliza en los asuntos o cuerpos de los correos electrónicos.
- `PS_LANG_DEFAULT`: El idioma predeterminado de su tienda.
- `PS_BO_ALLOW_EMPLOYEE_FORM_LANG`: Configuración relacionada con el idioma del empleado en el back office.
- `mypresta_updates`, `update_`, `updatev_`: Claves internas utilizadas por los módulos de MyPresta.eu para comprobaciones de actualizaciones y gestión de versiones.

### 2.2 Tabla de referencia rápida de configuración

| Pantalla / Vista | Configuración / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| Página de configuración del módulo | **Gestor de plantillas de correo electrónico** | N/A (crear según sea necesario) | Crear y gestionar plantillas de correo electrónico personalizadas para correos electrónicos con vales. |
| Página de configuración del módulo | **Motor de vales** | N/A (crear según sea necesario) | Generar códigos de vale únicos con reglas específicas y enviarlos por correo electrónico. |
| Página de configuración del módulo | Título del correo | "Su descuento especial" (ejemplo) | Línea de asunto predeterminada para los correos electrónicos con vales. |
| Página de configuración del módulo | Archivo de plantilla de correo electrónico | `voucher_email.html` (ejemplo) | Archivo HTML predeterminado utilizado para el contenido del correo electrónico. Utilice el Gestor de plantillas de correo electrónico para un mejor control. |

## 3. Solución de problemas del comerciante y preguntas frecuentes (FAQ)

**P: Mis clientes no reciben los correos electrónicos con vales. ¿Qué debo verificar?**
R:

1.  **Verifique la configuración de correo electrónico de su tienda:** Vaya a **Parámetros avanzados > Correo electrónico** en el back office de PrestaShop. Asegúrese de que su configuración de correo electrónico (SMTP o correo PHP) sea correcta y pruebe a enviar un correo electrónico general.
2.  **Carpetas de spam:** Pida a sus clientes que revisen sus carpetas de spam o correo no deseado.
3.  **Contenido de la plantilla de correo electrónico:** Asegúrese de que sus plantillas de correo electrónico no sean demasiado "spam" (por ejemplo, uso excesivo de mayúsculas, demasiados signos de exclamación).
4.  **Registros del módulo:** Verifique si el módulo proporciona algún registro o mensaje de error durante el proceso de envío. (Esto podría requerir asistencia de un desarrollador).

**P: El código del vale fue enviado, pero el cliente dice que no funciona.**
R:

1.  **Verifique la validez del vale:** En su back office de PrestaShop, vaya a **Catálogo > Descuentos > Reglas de carrito**. Busque el código del vale y verifique sus fechas de validez, importe mínimo, restricciones de cliente y si ya ha sido utilizado.
2.  **Asociación de cliente:** Si el vale se asoció con un cliente específico, asegúrese de que el cliente haya iniciado sesión en la cuenta correcta al intentar usarlo.
3.  **Errores tipográficos:** Pida al cliente que revise dos veces si hay errores tipográficos al introducir el código.

**P: ¿Puedo enviar el mismo código de vale a varios clientes?**
R: Sí, puede generar un único código de vale y enviarlo a varias direcciones de correo electrónico. Sin embargo, para un mejor seguimiento y para evitar el uso excesivo, generalmente se recomienda generar códigos únicos para cada destinatario, especialmente para ofertas personalizadas. El "Motor de vales" del módulo está diseñado para generar códigos únicos.

**P: ¿Cómo personalizo la apariencia de las plantillas de correo electrónico?**
R: Utilice la sección "Gestor de plantillas de correo electrónico" dentro de la configuración del módulo. Proporciona una interfaz para editar el asunto y el cuerpo de sus plantillas de correo electrónico. Para una personalización avanzada de HTML/CSS, es posible que deba editar los archivos de plantilla subyacentes (consulte la Sección 7 para desarrolladores).

**P: El módulo no se muestra correctamente después de la instalación, o veo una página en blanco.**
R:

1.  **Borrar caché de Smarty:** Vaya a **Parámetros avanzados > Rendimiento** en su back office de PrestaShop. Establezca "Compilación de plantillas" en "Recompilar las plantillas si los archivos han sido actualizados" y "Caché" en "No". Luego, haga clic en "Borrar caché" en la esquina superior derecha. Después de verificar, puede revertir "Caché" a "Sí" y "Compilación de plantillas" a "Nunca recompilar..." para mejorar el rendimiento.
2.  **Verifique la versión de PHP:** Asegúrese de que su versión de PHP esté dentro del rango compatible (PHP 5.6 - 8.5).
3.  **Registros de errores del servidor:** Verifique los registros de errores de PHP de su servidor para ver si hay mensajes de error específicos. Esto generalmente requiere acceso a su panel de control de alojamiento.

## 4. Guía para desarrolladores y webmasters (Arquitectura técnica y mapa de código)

### 4.1 Resumen de la arquitectura

El módulo "Enviar correo electrónico con vale" sigue una arquitectura de módulo estándar de PrestaShop, aprovechando principalmente la clase `Module` para su funcionalidad y configuración principales. Integra JavaScript y CSS personalizados para su interfaz de back office, particularmente para las herramientas de gestión de plantillas de correo electrónico y generación de vales. El módulo no introduce controladores de front office personalizados ni entidades `ObjectModel` complejas, sino que interactúa con las clases `CartRule` (descuento) y `Mail` integradas de PrestaShop.

### 4.2 Controladores (`controllers/`)

Este módulo no contiene ningún controlador de front office o back office personalizado en el directorio `controllers/`. Toda la lógica administrativa y la configuración se manejan dentro del método `getContent()` del archivo principal del módulo (`sendvouchers.php`).

### 4.3 Clases y modelos principales (`classes/`)

Este módulo no define ninguna clase o modelo personalizado dentro de un directorio `classes/`. Se basa en las clases principales de PrestaShop, como `CartRule` para la gestión de descuentos y `Mail` para el envío de correos electrónicos.

### 4.4 Recursos JavaScript (`views/js/`)

- **`sendvouchers/lib/emailTemplatesManager/js/emailTemplatesManager.js`**

  - **Alcance:** Back office (página de configuración del módulo).
  - **Responsabilidad:** Gestiona los elementos interactivos de la interfaz de creación, edición y eliminación de plantillas de correo electrónico. Este script probablemente maneja llamadas AJAX para guardar/actualizar datos de plantillas, renderiza formularios dinámicamente y gestiona las interacciones del usuario dentro de la sección "Gestor de plantillas de correo electrónico". Podría usar jQuery para la manipulación del DOM y la vinculación de eventos.
- **`sendvouchers/lib/voucherengine/script.js`**

  - **Alcance:** Back office (página de configuración del módulo).
  - **Responsabilidad:** Impulsa la sección "Motor de vales". Este script es responsable de manejar la generación de códigos de vale, configurar reglas de descuento (por ejemplo, porcentaje, cantidad fija, condiciones), seleccionar plantillas de correo electrónico e iniciar el proceso de envío de vales. Probablemente realiza validación del lado del cliente y solicitudes AJAX al método `getContent()` del módulo para el procesamiento del lado del servidor.

### 4.5 Hojas de estilo CSS (`views/css/`)

- **`sendvouchers/lib/emailTemplatesManager/css/emailTemplatesManager.css`**

  - **Alcance:** Estilo del formulario de administración del back office.
  - **Responsabilidad:** Proporciona estilo para la interfaz del "Gestor de plantillas de correo electrónico", incluidos formularios para crear/editar plantillas, botones y, potencialmente, vistas de lista.
  - **Selectores de clase CSS clave:** Los desarrolladores pueden inspeccionar la salida HTML del módulo en el back office para identificar clases específicas (por ejemplo, `.email-template-form`, `.template-list-item`) para anularlas en sus temas de administración personalizados o mediante `override.css`.
- **`sendvouchers/lib/voucherengine/ps16.css`**

  - **Alcance:** Estilo del formulario de administración del back office, específicamente para la compatibilidad con PrestaShop 1.6.
  - **Responsabilidad:** Proporciona estilo para la sección "Motor de vales", que potencialmente incluye diseños de formularios, campos de entrada y botones, con ajustes para adaptarse al tema del back office de PrestaShop 1.6. Este archivo también podría cargarse en versiones más nuevas de PS para compatibilidad con versiones anteriores, pero su propósito principal es para PS 1.6.
  - **Selectores de clase CSS clave:** Similar a `emailTemplatesManager.css`, los desarrolladores deben inspeccionar el HTML generado para selectores específicos a los que apuntar para anulaciones.

### 4.6 Estructura de plantillas Smarty (`views/templates/`)

Todas las plantillas se encuentran dentro del directorio `sendvouchers/lib/emailTemplatesManager/views/`, lo que indica que se utilizan principalmente para renderizar la interfaz de back office del gestor de plantillas de correo electrónico.

- **`sendvouchers/lib/emailTemplatesManager/views/buttonManager.tpl`**

  - **Alcance:** Plantilla de administración.
  - **Propósito:** Probablemente renderiza botones o controles relacionados con la gestión de plantillas de correo electrónico (por ejemplo, "Añadir nueva plantilla", "Gestionar plantillas").
- **`sendvouchers/lib/emailTemplatesManager/views/createTemplateForm.tpl`**

  - **Alcance:** Plantilla de administración.
  - **Propósito:** Renderiza el formulario HTML para crear una nueva plantilla de correo electrónico, incluidos los campos para el asunto, el cuerpo y, potencialmente, la selección de idioma.
- **`sendvouchers/lib/emailTemplatesManager/views/editTemplateForm.tpl`**

  - **Alcance:** Plantilla de administración.
  - **Propósito:** Renderiza el formulario HTML para editar una plantilla de correo electrónico existente, rellenando previamente los campos con los datos de la plantilla actual.
- **`sendvouchers/lib/emailTemplatesManager/views/mainForm.tpl`**

  - **Alcance:** Plantilla de administración.
  - **Propósito:** Esta es probablemente la plantilla envolvente principal para la sección "Gestor de plantillas de correo electrónico", que orquesta la visualización de la lista de plantillas, el formulario de creación y el formulario de edición.
- **`sendvouchers/lib/emailTemplatesManager/views/selectInput.tpl`**

  - **Alcance:** Plantilla de administración.
  - **Propósito:** Un fragmento de plantilla reutilizable para renderizar un campo de entrada HTML `<select>`, posiblemente para la selección de idioma o la elección de una plantilla existente.

### 4.7 Esquema de la base de datos y mapa de hooks

- **Tablas de la base de datos**:

  - El módulo no crea explícitamente tablas SQL personalizadas durante `install()`.
  - Almacena su configuración (como `sendvouchersTemplate`, `sendvouchersTitle`) en la tabla `ps_configuration` de PrestaShop.
  - Interactúa con las tablas principales `ps_cart_rule` y `ps_cart_rule_lang` de PrestaShop al crear y gestionar vales de descuento.
- **Tabla de Hooks registrados**:
  La funcionalidad principal del módulo se ejecuta a través de su método `getContent()` en el back office. Si bien la descripción del módulo menciona "Hooks de Front-Office: Cabecera, Columnas, Producto o Pie de página", el inventario de código proporcionado no muestra archivos de plantilla correspondientes o métodos `hook` explícitos en `sendvouchers.php` que renderizarían contenido en estos hooks de front office. Esto sugiere que si se registran hooks de front office, son para procesamiento interno (por ejemplo, `actionFrontControllerSetMedia` para cargar recursos) o son restos de versiones anteriores y no se utilizan activamente para mostrar contenido visual.

  La funcionalidad principal de enviar correos electrónicos con vales se activa por la acción del usuario en el back office, no por las cargas de páginas del front office.

| Nombre del Hook | Momento de ejecución | Propósito técnico |
| --- | --- | --- |
| `displayBackOfficeHeader` | En cada carga de página del back office. | Potencialmente utilizado para cargar CSS/JS específicos del módulo para su página de configuración. |
| `moduleRoutes` | Durante la inicialización del enrutamiento de URL. | (Si se implementa) Para definir URL amigables personalizadas para las páginas del módulo. (No detectado explícitamente en este módulo). |
| `actionAdminControllerSetMedia` | Cuando se carga un controlador de administración. | Para añadir archivos JavaScript y CSS específicos del módulo a la página de configuración del back office. |

## 5. Soporte oficial y actualizaciones

Para obtener actualizaciones oficiales, soporte técnico y descargar las últimas versiones del módulo "Enviar correo electrónico con vale", visite su cuenta de cliente en [MyPresta.eu](https://mypresta.eu/). Nuestro equipo de soporte está disponible para ayudarle con cualquier problema o pregunta que pueda tener con respecto a la funcionalidad y compatibilidad del módulo.
