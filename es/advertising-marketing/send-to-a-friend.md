---
title: "Enviar a un amigo - Manual de comerciante y guía de configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop 'Enviar a un amigo' de MyPresta.eu."
sidebar:
  label: "Enviar a un amigo - Manual de comerciante y guía de configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Send to a friend en MyPresta.eu](https://mypresta.eu/modules/advertising-and-marketing/send-to-a-friend.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/advertising-marketing/send-to-a-friend/)
>
> ---


# Enviar a un amigo

## 1. Requisitos y compatibilidad

- **Versiones de PrestaShop compatibles**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilidad con PHP**: PHP 7.1 - 8.5
- **Requisitos de alojamiento**: Las extensiones PHP estándar (cURL, JSON, OpenSSL) suelen ser necesarias para una instalación de PrestaShop y son suficientes para este módulo.

## 2. Recorrido completo por la configuración (Cada ajuste agrupado por pantalla)

### 2.1 Página de configuración del módulo (Back Office > Módulos > Configurar)

Esta es la pantalla de configuración principal del módulo "Enviar a un amigo". Aquí puede controlar cómo se comporta y aparece la función en sus páginas de producto.

#### Ajustes generales

- **Qué hace este ajuste:** Esta sección contiene los ajustes principales para habilitar o deshabilitar el módulo y controlar su funcionalidad básica.
- **Efecto de cambiar este ajuste:**
  - *Cuando está habilitado:* El enlace/botón "Enviar a un amigo" y la funcionalidad aparecerán en sus páginas de producto según lo configurado.
  - *Cuando está deshabilitado:* La función estará completamente oculta de su tienda y no se podrán enviar correos electrónicos a través de ella.
- **Valor recomendado:** **SÍ** (Habilitado) para permitir que los clientes utilicen la función.
- **Escenario/ejemplo de comerciante:** Si desea deshabilitar temporalmente la función para mantenimiento o una campaña de marketing específica, cambiaría esto a "NO". De lo contrario, manténgalo en "SÍ" para aprovechar el marketing boca a boca.

#### Opciones de visualización

- **Qué hace este ajuste:** Estas opciones controlan dónde aparecerá el enlace o botón "Enviar a un amigo" en sus páginas de producto. El módulo utiliza el sistema de hooks de PrestaShop para colocar la función en diferentes áreas.
- **Efecto de cambiar este ajuste:**
  - *Seleccionar un hook (por ejemplo, `displayProductButtons`):* El enlace "Enviar a un amigo" se renderizará en esa área específica de su página de producto.
  - *No seleccionar ningún hook:* La función podría no aparecer en absoluto, o podría aparecer en una ubicación predeterminada si su tema tiene una renderización de reserva específica.
- **Valor recomendado:** `displayProductButtons` o `displayProductActions` son hooks comunes y recomendados, ya que colocan el enlace cerca del botón "Añadir al carrito", lo que lo hace fácilmente detectable. También podría considerar `displayFooterProduct` si prefiere que esté en la parte inferior de los detalles del producto.
- **Escenario/ejemplo de comerciante:** Si desea que el enlace "Enviar a un amigo" sea muy visible y esté cerca de la llamada a la acción principal, elija `displayProductButtons`. Si prefiere que sea menos prominente, quizás en la parte inferior de la información del producto, seleccione `displayFooterProduct`. Experimente con diferentes hooks para ver qué se ve mejor con su tema.

#### Plantilla y contenido del correo electrónico

- **Qué hace este ajuste:** Esta sección le permite personalizar el asunto y el contenido del correo electrónico que se envía al amigo.
- **Efecto de cambiar este ajuste:**
  - *Cambiar el asunto:* La línea de asunto del correo electrónico reflejará su texto personalizado, haciéndolo más atractivo o de marca.
  - *Cambiar el contenido:* El cuerpo del correo electrónico incluirá su mensaje personalizado, lo que le permitirá personalizar la recomendación. Puede usar marcadores de posición como `{product_name}` y `{product_link}` que se reemplazarán automáticamente con los detalles reales del producto.
- **Valor recomendado:** Utilice una línea de asunto clara y atractiva (por ejemplo, "¡Echa un vistazo a este producto de {your\_shop\_name}!") y un mensaje amigable e informativo en el cuerpo. Incluya siempre `{product_name}` y `{product_link}` para asegurarse de que el amigo sepa qué se le recomienda y cómo encontrarlo.
- **Escenario/ejemplo de comerciante:** Podría personalizar el correo electrónico para que diga: "Hola {friend\_name}, {customer\_name} pensó que te gustaría este producto de Mi Tienda Impresionante. Se llama {product\_name} y puedes encontrarlo aquí: {product\_link}. ¡Felices compras!"

### 2.2 Tabla de referencia rápida de configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e impacto |
| --- | --- | --- | --- |
| Configuración del módulo | Habilitar/Deshabilitar módulo | Habilitado | Controla si la función "Enviar a un amigo" está activa en su tienda. |
| Configuración del módulo | Hook de visualización | `displayProductButtons` | Determina dónde aparece el enlace "Enviar a un amigo" en las páginas de producto. |
| Configuración del módulo | Asunto del correo electrónico | "¡Echa un vistazo a este producto!" | Personaliza la línea de asunto del correo electrónico enviado al amigo. |
| Configuración del módulo | Contenido del correo electrónico | "Hola {friend\_name}, {customer\_name} pensó que te gustaría este producto: {product\_name}. Puedes encontrarlo aquí: {product\_link}" | Personaliza el cuerpo del correo electrónico, incluyendo detalles dinámicos del producto. |

## 3. Solución de problemas del comerciante y preguntas frecuentes (FAQ)

**P: El enlace "Enviar a un amigo" no aparece en mis páginas de producto. ¿Qué debo hacer?**
R:

1. **Verifique el estado del módulo:** Vaya a **Módulos > Gestor de módulos** y asegúrese de que el módulo "Enviar a un amigo" esté instalado y habilitado.
2. **Verifique la configuración:** Vaya a la página de configuración del módulo y asegúrese de que el módulo esté "Habilitado" y de que haya seleccionado al menos un "Hook de visualización" (por ejemplo, `displayProductButtons`).
3. **Borre la caché:** PrestaShop a menudo almacena contenido en caché. Vaya a **Parámetros avanzados > Rendimiento** y haga clic en "Borrar caché" (o "Borrar caché de Smarty" en versiones anteriores).
4. **Compatibilidad con el tema:** Si está utilizando un tema personalizado, es posible que no esté diseñado explícitamente para renderizar todos los hooks de PrestaShop. Intente cambiar temporalmente al tema predeterminado de PrestaShop para ver si aparece el enlace. Si lo hace, su tema podría requerir una pequeña modificación por parte de un webmaster para mostrar el hook elegido.

**P: Mis clientes están enviando correos electrónicos, pero sus amigos no los reciben.**
R:

1. **Revise las carpetas de spam:** Pida al amigo que revise su carpeta de spam o correo no deseado.
2. **Verifique la configuración de correo electrónico:** Asegúrese de que la configuración de correo electrónico de su tienda PrestaShop esté configurada correctamente en **Parámetros avanzados > Correo electrónico**. Pruebe a enviar un correo electrónico general desde PrestaShop para confirmar que su servidor de correo funciona.
3. **Registros del módulo (Verificación del desarrollador):** Un desarrollador puede revisar los registros de correo de PrestaShop (si están habilitados) o los registros de errores del servidor para detectar problemas relacionados con el envío de correos electrónicos.

**P: ¿Puedo cambiar el texto del enlace "Enviar a un amigo" o los campos del formulario?**
R: Sí, puede traducir o modificar las cadenas de texto (etiquetas, texto de botones, etc.) del módulo utilizando la herramienta de traducción de PrestaShop. Vaya a **Internacional > Traducciones**, seleccione "Traducciones de módulos instalados", elija su tema y luego seleccione el módulo "Enviar a un amigo". A continuación, podrá editar todo el texto visible.

**P: El formulario emergente se ve extraño o no tiene el estilo correcto en mi dispositivo móvil.**
R:

1. **Borre la caché del navegador:** Pida al cliente que borre la caché de su navegador en su dispositivo móvil.
2. **Conflictos de tema:** Los temas personalizados a veces pueden anular o entrar en conflicto con el estilo del módulo. Si bien el módulo incluye su propio CSS (`send2friend.css`), el CSS de su tema podría estar teniendo prioridad. Un webmaster puede inspeccionar la página utilizando las herramientas de desarrollo del navegador para identificar y resolver conflictos de CSS.

## 4. Guía para desarrolladores y webmasters (Arquitectura técnica y mapa de código)

Esta sección proporciona una descripción técnica detallada para desarrolladores y webmasters.

### 4.1 Descripción general de la arquitectura

El módulo "Enviar a un amigo" (`send2friend`) es un módulo estándar de PrestaShop que implementa el patrón MVC. Utiliza principalmente controladores frontales para solicitudes AJAX, plantillas Smarty para renderizar el formulario y hooks para integrarse en la página del producto. No introduce tablas de base de datos personalizadas ni ObjectModels complejos, basándose en la funcionalidad de correo principal de PrestaShop.

### 4.2 Controladores (`controllers/`)

#### Controladores Front-Office

- **`controllers/front/AjaxSend.php`**
  - **Nombre de la clase:** `Send2FriendAjaxSendModuleFrontController`
  - **Clase padre:** `ModuleFrontController`
  - **Responsabilidad:** Este controlador maneja la solicitud AJAX iniciada cuando un usuario envía el formulario "Enviar a un amigo". Recibe el nombre del remitente, el nombre del amigo, el correo electrónico del amigo y el ID del producto. Luego construye y envía el correo electrónico utilizando el método `Mail::Send()` de PrestaShop. Devuelve una respuesta JSON que indica éxito o fracaso.
- **`controllers/front/index.php`**
  - **Nombre de la clase:** `Send2FriendIndexModuleFrontController`
  - **Clase padre:** `ModuleFrontController`
  - **Responsabilidad:** Este es un controlador frontal de marcador de posición o predeterminado. En muchos módulos, esto podría manejar una página dedicada del front-office. Para "Enviar a un amigo", su función principal podría ser asegurar que se carguen los activos del front-office del módulo o servir como base para otros controladores frontales. Dada la funcionalidad del módulo, el controlador `AjaxSend` es el más activo.

### 4.3 Clases y modelos principales (`classes/`)

El módulo no contiene ninguna clase o modelo personalizado en el directorio `classes/`. Aprovecha las funcionalidades principales de PrestaShop, en particular `Mail` para enviar correos electrónicos y `Product` para recuperar información del producto.

### 4.4 Activos JavaScript (`views/js/`)

- **`views/js/send2friend.js`**
  - **Alcance:** Front-office.
  - **Detalles:** Este script es responsable de la interacción front-end de la función "Enviar a un amigo".
    - Probablemente adjunta un detector de eventos al enlace/botón "Enviar a un amigo" para abrir el modal o mostrar el formulario.
    - Maneja el envío del formulario, recopilando datos (nombre del remitente, nombre del amigo, correo electrónico del amigo, ID del producto).
    - Envía una solicitud AJAX al controlador frontal `AjaxSend.php`.
    - Procesa la respuesta JSON del servidor (éxito/error) y proporciona retroalimentación al usuario (por ejemplo, "¡Correo electrónico enviado con éxito!" o "Error al enviar el correo electrónico.").
    - Podría incluir lógica para la validación del formulario (por ejemplo, verificar formatos de correo electrónico válidos).
    - Utiliza jQuery para la manipulación del DOM y las llamadas AJAX, común en el front-office de PrestaShop.

### 4.5 Hojas de estilo CSS (`views/css/`)

- **`views/css/send2friend.css`**
  - **Alcance:** Estilo del cliente del front-office.
  - **Detalles:** Esta hoja de estilo proporciona el estilo visual básico para el enlace "Enviar a un amigo", el modal emergente (si se usa) y los campos del formulario dentro de él.
    - Define estilos para el botón/enlace, los campos de entrada, las etiquetas y cualquier mensaje de éxito/error.
    - Los selectores de clase CSS clave que los desarrolladores pueden anular en su tema incluirían típicamente clases como `.send2friend-button`, `.send2friend-modal`, `.send2friend-form`, `.send2friend-input`, etc. Los desarrolladores pueden inspeccionar el HTML renderizado para encontrar las clases exactas utilizadas.

### 4.6 Estructura de la plantilla Smarty (`views/templates/`)

- **`views/templates/hook/send2friend-extra.tpl`**
  - **Alcance:** Front-office.
  - **Renderizado de Hook:** Esta plantilla está diseñada para ser renderizada en varios hooks de la página de producto (por ejemplo, `displayProductButtons`, `displayProductActions`, `displayFooterProduct`).
  - **Bloque visual:** Genera la estructura HTML para el enlace/botón "Enviar a un amigo" y el modal asociado o el formulario en línea. Esto incluye los campos de entrada para nombres y direcciones de correo electrónico, y el botón de envío. También contiene los campos ocultos necesarios (como `product_id`) y potencialmente la estructura para mostrar mensajes de éxito/error.

### 4.7 Esquema de la base de datos y mapa de hooks

#### Tablas de la base de datos

El módulo "Enviar a un amigo" no crea ninguna tabla de base de datos personalizada. Almacena sus ajustes de configuración (como el estado habilitado, el hook elegido, el asunto y el contenido del correo electrónico) en la tabla `ps_configuration` de PrestaShop.

- **`ps_configuration`**: Almacena la configuración del módulo con claves típicamente prefijadas por `SEND2FRIEND_`.

#### Tabla de Hooks registrados

| Nombre del Hook | Momento de ejecución | Propósito técnico |
| --- | --- | --- |
| `displayHeader` | En la sección `<head>` de cada página. | Se utiliza para cargar los activos CSS y JavaScript del módulo globalmente. |
| `displayProductButtons` | Cerca del botón "Añadir al carrito" en las páginas de producto. | Ubicación común para el enlace "Enviar a un amigo". |
| `displayProductActions` | Otro hook común cerca de las acciones del producto. | Ubicación alternativa para el enlace "Enviar a un amigo". |
| `displayFooterProduct` | En la parte inferior del bloque de información del producto. | Ubicación menos prominente para el enlace "Enviar a un amigo". |
| `displayRightColumnProduct` | En la columna derecha de la página del producto (si está habilitado por el tema). | Posible ubicación para el enlace "Enviar a un amigo". |
| `displayLeftColumnProduct` | En la columna izquierda de la página del producto (si está habilitado por el tema). | Posible ubicación para el enlace "Enviar a un amigo". |

El método `install()` del módulo registra estos hooks, y el método `uninstall()` los anula. El hook específico elegido por el comerciante en la configuración determina cuál se utiliza activamente para mostrar la plantilla.

## 5. Soporte oficial y actualizaciones

Para obtener las últimas actualizaciones, correcciones de errores y soporte oficial para el módulo "Enviar a un amigo", consulte su cuenta de cliente de MyPresta.eu. Puede descargar las versiones más recientes y acceder a los recursos de soporte directamente desde [MyPresta.eu](https://mypresta.eu).
