---
title: "Arukereso.hu - correos electrónicos de encuestas del programa de compra de confianza - Manual del Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop Arukereso.hu - correos electrónicos de encuestas del programa de compra de confianza de MyPresta.eu."
sidebar:
  label: "Arukereso.hu - correos electrónicos de encuestas del programa de compra de confianza - Manual del Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Arukereso.hu - trusted purchase program survey emails en MyPresta.eu](https://mypresta.eu/modules/advertising-and-marketing/arukeresohu-trusted-purchase-program-survey-emails.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/advertising-marketing/arukeresohu-trusted-purchase-program-survey-emails/)
>
> ---


# Arukereso.hu - correos electrónicos de encuestas del programa de compra de confianza

## 1. Requisitos y compatibilidad

- **Versiones de PrestaShop compatibles**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilidad con PHP**: PHP 7.1 - 8.5
- **Requisitos de alojamiento**: Las extensiones PHP estándar (cURL, JSON, OpenSSL) suelen ser suficientes. Normalmente no se necesitan configuraciones especiales del servidor.

## 2. Recorrido completo por la configuración (Cada ajuste agrupado por pantalla)

### 2.1 Página de configuración del módulo (Back Office > Módulos > Configurar)

Esta es la pantalla de configuración principal y única para el módulo Arukereso.hu. Puede acceder a ella navegando a **Módulos > Gestor de módulos**, buscando "Arukereso.hu" y haciendo clic en "Configurar".

#### 2.1.1 Arukereso.hu WebApiKey

-   **Qué hace esta configuración:** Este es su identificador único proporcionado por Arukereso.hu. Es esencial para que Arukereso.hu vincule las solicitudes de encuestas que provienen de su tienda PrestaShop a su cuenta de comerciante específica en su plataforma.
-   **Efecto de cambiar esta configuración:**
    *   *Cuando se introduce correctamente:* El módulo puede comunicarse con éxito con los sistemas de Arukereso.hu, lo que permite el proceso automatizado de envío de correos electrónicos de encuestas.
    *   *Cuando es incorrecto o está vacío:* Arukereso.hu no podrá identificar su tienda y los correos electrónicos de encuestas no se enviarán a sus clientes. La integración fallará.
-   **Valor recomendado:** Introduzca la clave API exacta que le ha proporcionado Arukereso.hu. Esto se encuentra generalmente en la configuración de su cuenta de comerciante en el sitio web de Arukereso.hu.
-   **Escenario / ejemplo de comerciante:** Se registra en el "Programa de Compra de Confianza" en Arukereso.hu. Le proporcionan una cadena de caracteres como `abcdef1234567890`. Copia y pega esto en este campo.

#### 2.1.2 Identificador de producto (feed ITEM\_ID)

-   **Qué hace esta configuración:** Esta configuración determina qué identificador de producto de su tienda PrestaShop se enviará a Arukereso.hu. Arukereso.hu utiliza este ID para hacer coincidir el producto comprado con su listado en su plataforma, asegurando que la encuesta sea relevante.
-   **Efecto de cambiar esta configuración:**
    *   *Cuando se establece en "ID de producto":* Se utilizará el ID interno del producto de PrestaShop (por ejemplo, `123`). Esta es la opción más común y generalmente más segura.
    *   *Cuando se establece en "Referencia de producto":* Se utilizará el código de referencia de su producto (por ejemplo, `SKU-001`). Esto requiere que sus referencias de producto sean únicas y consistentes con lo que espera Arukereso.hu.
    *   *Cuando se establece en "EAN13 de producto":* Se utilizará el código de barras EAN-13 del producto. Esto es adecuado si sus EAN se utilizan de forma consistente y coinciden con el catálogo de productos de Arukereso.hu.
    *   *Cuando se establece en "UPC de producto":* Se utilizará el código UPC del producto. Similar al EAN13, requiere datos consistentes.
-   **Valor recomendado:** "ID de producto" es generalmente la opción más segura y confiable, a menos que tenga una razón específica (y verificada con Arukereso.hu) para usar otro identificador.
-   **Escenario / ejemplo de comerciante:** Si tiene un producto "Camiseta Roja" con un ID interno de `15`, una referencia `TSHIRT-RED` y un EAN `1234567890123`, elegir "ID de producto" enviará `15` a Arukereso.hu. Si elige "Referencia de producto", se enviará `TSHIRT-RED`. Asegúrese de que el identificador elegido sea el que Arukereso.hu espera para vincular correctamente los productos.

#### 2.1.3 Requerir consentimiento del cliente

-   **Qué hace esta configuración:** Esta configuración crucial controla si sus clientes deben aceptar explícitamente participar en el programa de encuestas de Arukereso.hu durante el proceso de pago. Esto es vital para cumplir con las regulaciones de privacidad de datos como el GDPR.
-   **Efecto de cambiar esta configuración:**
    *   *Cuando está habilitado ("Sí"):* Aparecerá una casilla de verificación o un mecanismo de consentimiento similar durante el proceso de pago. Solo los clientes que marquen esta casilla tendrán sus datos de pedido enviados a Arukereso.hu para fines de encuesta. Esto garantiza el cumplimiento del GDPR.
    *   *Cuando está deshabilitado ("No"):* No se mostrará ninguna opción de consentimiento. Todos los clientes que completen un pedido se inscribirán automáticamente en el programa de encuestas de Arukereso.hu. **Úselo con precaución y solo si está seguro de que sus regulaciones locales no requieren un consentimiento explícito para este tipo de intercambio de datos.**
-   **Valor recomendado:** "Sí". Se recomienda encarecidamente habilitar esta opción para garantizar el cumplimiento del GDPR y otras leyes de privacidad, dando a los clientes control sobre sus datos.
-   **Escenario / ejemplo de comerciante:** Opera en la UE. Para cumplir con el GDPR, habilita esta configuración. Durante el proceso de pago, los clientes ven una casilla de verificación: "Sí, acepto recibir una encuesta de satisfacción del cliente de Arukereso.hu con respecto a mi compra". Solo si marcan esta casilla se compartirán sus datos.

#### 2.1.4 Escribir errores en log.txt

-   **Qué hace esta configuración:** Esta configuración controla si el módulo registra los errores o problemas que encuentra durante su funcionamiento en un archivo `log.txt` dentro del directorio del módulo.
-   **Efecto de cambiar esta configuración:**
    *   *Cuando está habilitado ("Sí"):* Cualquier problema (por ejemplo, fallo al conectar con Arukereso.hu, problemas de clave API no válida) se escribirá en `arukereso/log.txt`. Esto es extremadamente útil para la resolución de problemas.
    *   *Cuando está deshabilitado ("No"):* Los errores no se registrarán en un archivo. Aunque esto reduce ligeramente la actividad del disco, dificulta mucho el diagnóstico de problemas.
-   **Valor recomendado:** "Sí" durante la configuración inicial y si experimenta algún problema. Una vez que el módulo funcione sin problemas, puede deshabilitarlo si lo prefiere, pero a menudo es mejor dejarlo habilitado para una supervisión continua.
-   **Escenario / ejemplo de comerciante:** Ha configurado el módulo, pero los clientes no reciben encuestas. Habilita esta configuración y, después de algunos pedidos de prueba, comprueba `arukereso/log.txt` y encuentra un mensaje de error que indica "Clave API no válida". Esto le indica inmediatamente dónde buscar el problema.

### 2.2 Tabla de referencia rápida de configuración

| Pantalla / Vista | Configuración / Opción | Predeterminado / Recomendado | Propósito e impacto |
| --- | --- | --- | --- |
| Configuración del módulo | Arukereso.hu WebApiKey | Su clave de Arukereso.hu | Identificador único para su tienda en Arukereso.hu. **Requerido para la integración.** |
| Configuración del módulo | Identificador de producto (feed ITEM\_ID) | ID de producto | Define qué ID de producto (ID de PrestaShop, Referencia, EAN, UPC) se envía a Arukereso.hu. |
| Configuración del módulo | Requerir consentimiento del cliente | Sí | Muestra una casilla de verificación de consentimiento durante el proceso de pago. **Altamente recomendado para el cumplimiento del GDPR.** |
| Configuración del módulo | Escribir errores en log.txt | Sí | Registra los errores del módulo en `arukereso/log.txt` para la resolución de problemas. |

## 3. Resolución de problemas del comerciante y preguntas frecuentes (FAQ)

**P: Mis clientes no reciben correos electrónicos de encuestas de Arukereso.hu. ¿Qué debo verificar?**
R:

1.  **Arukereso.hu WebApiKey:** Verifique que su clave API esté correctamente introducida en la configuración del módulo. Incluso un solo error tipográfico impedirá que la integración funcione.
2.  **Configuración de consentimiento:** Si "Requerir consentimiento del cliente" está habilitado, asegúrese de que los clientes realmente marquen la casilla de consentimiento durante el proceso de pago. Si no lo hacen, no se envían datos.
3.  **Archivo de registro:** Habilite "Escribir errores en log.txt" en la configuración del módulo y verifique el archivo `arukereso/log.txt` en busca de mensajes de error después de un pedido de prueba. Esta es la forma más directa de diagnosticar problemas.
4.  **Cuenta de Arukereso.hu:** Inicie sesión en su cuenta de comerciante de Arukereso.hu y verifique el estado de la integración de su "Programa de Compra de Confianza". Podrían tener registros o indicadores de estado específicos.
5.  **Estado del pedido:** Asegúrese de que el estado del pedido que activa la encuesta (generalmente "Pago aceptado" o "Entregado") esté correctamente configurado en el lado de Arukereso.hu, y que sus pedidos de PrestaShop alcancen ese estado.

**P: Habilité "Requerir consentimiento del cliente", pero no veo la casilla de verificación durante el proceso de pago.**
R:

1.  **Compatibilidad del tema:** El módulo utiliza ganchos estándar de PrestaShop (`displayGDPRConsent`, `displayPaymentTop`, `displayCheckoutSummaryTop`). Si su tema está muy personalizado, es posible que no renderice estos ganchos correctamente.
2.  **Caché:** Borre la caché de su PrestaShop (Parámetros avanzados > Rendimiento > Borrar caché).
3.  **Posición del módulo:** Vaya a Diseño > Posiciones y busque los ganchos mencionados anteriormente. Asegúrese de que el módulo Arukereso.hu esté listado y activo en estos ganchos. Si no, intente trasplantarlo.
4.  **Conflictos de módulos:** Deshabilite temporalmente otros módulos que modifiquen el proceso de pago para descartar conflictos.

**P: ¿Qué sucede si un cliente solicita que se eliminen sus datos (Derecho al olvido del GDPR)?**
R: El módulo está diseñado para integrarse con las herramientas GDPR de PrestaShop. Cuando un cliente solicita la eliminación de datos a través del módulo GDPR de PrestaShop, este módulo Arukereso.hu responderá al gancho `actionDeleteGDPRCustomer`, asegurando que cualquier dato relacionado con el cliente que tenga el módulo (por ejemplo, registros de consentimiento) sea eliminado. Sin embargo, es importante tener en cuenta que este módulo *envía* datos a Arukereso.hu. También deberá ponerse en contacto directamente con Arukereso.hu para solicitar la eliminación de los datos de ese cliente de sus sistemas.

**P: ¿Puedo personalizar la apariencia de la casilla de verificación de consentimiento?**
R: La apariencia de la casilla de verificación de consentimiento está controlada principalmente por el CSS de su tema de PrestaShop. El módulo proporciona la estructura HTML a través de su plantilla `consent.tpl`. Puede anular esta plantilla en su tema o añadir CSS personalizado para estilizar el elemento si necesita cambiar su aspecto.

## 4. Guía para desarrolladores y webmasters (Arquitectura técnica y mapa de código)

### 4.1 Resumen de la arquitectura

El módulo Arukereso.hu es un módulo ligero de PrestaShop centrado principalmente en la integración con el "Programa de Compra de Confianza" de Arukereso.hu. Aprovecha el sistema de ganchos de PrestaShop para inyectar una opción de consentimiento durante el proceso de pago y para enviar datos de pedidos a Arukereso.hu tras la confirmación del pedido. Sigue una estructura de módulo estándar de PrestaShop, con su lógica central residiendo en el archivo principal del módulo (`arukereso.php`) y utilizando plantillas Smarty para la visualización en el front-office. No introduce controladores ni ObjectModels personalizados, sino que se basa en la clase `Configuration` de PrestaShop para el almacenamiento de la configuración.

### 4.2 Controladores (`controllers/`)

Este módulo **no** contiene ningún controlador personalizado de Front-Office o Back-Office. Toda la lógica se gestiona dentro del archivo principal del módulo `arukereso.php`, principalmente a través de métodos de gancho.

### 4.3 Clases y modelos principales (`classes/`)

Este módulo **no** define ninguna clase u ObjectModels personalizados en el directorio `classes/`. Opera directamente dentro del archivo `arukereso.php`, utilizando clases y funciones estándar de PrestaShop.

### 4.4 Activos JavaScript (`views/js/`)

Este módulo **no** incluye ningún archivo JavaScript personalizado. Toda la interacción del front-office (por ejemplo, la casilla de verificación de consentimiento) se maneja a través de formularios HTML estándar y procesamiento del lado del servidor.

### 4.5 Hojas de estilo CSS (`views/css/`)

Este módulo **no** incluye ningún archivo CSS personalizado. Cualquier estilo para la casilla de verificación de consentimiento u otros elementos se heredaría del tema activo de PrestaShop.

### 4.6 Estructura de la plantilla Smarty (`views/templates/`)

#### Plantillas de gancho (`views/templates/hook/`)

-   `arukereso/views/templates/hook/consent.tpl`
    *   **Gancho:** `displayGDPRConsent`, `displayPaymentTop`, `displayCheckoutSummaryTop` (dependiendo del tema y la versión de PrestaShop, uno de estos renderizará el consentimiento).
    *   **Propósito:** Esta plantilla renderiza el HTML para la casilla de verificación de consentimiento del cliente durante el proceso de pago. Normalmente incluye una etiqueta, el campo de entrada de la casilla de verificación y, potencialmente, un enlace a la política de privacidad o más información sobre Arukereso.hu.
    *   **Salida:** Un pequeño elemento de formulario que permite al cliente optar por el programa de encuestas.
-   `arukereso/views/templates/hook/displayOrderConfirmation.tpl`
    *   **Gancho:** `displayOrderConfirmation`
    *   **Propósito:** Esta plantilla se renderiza en la página de confirmación del pedido después de una compra exitosa. Puede mostrar un mensaje al cliente confirmando su participación en el programa de encuestas (si se dio el consentimiento) o proporcionar información sobre la próxima encuesta.
    *   **Salida:** Un pequeño bloque informativo en la página de confirmación del pedido.

#### Plantillas de administración (`views/templates/admin/`)

Este módulo **no** contiene ninguna plantilla de administración personalizada más allá de lo que se renderiza por `getContent()` en el archivo principal del módulo.

#### Plantillas de front-office (`views/templates/front/`)

Este módulo **no** contiene ninguna plantilla de página de front-office independiente dedicada.

### 4.7 Esquema de la base de datos y mapa de ganchos

#### Tablas de la base de datos

Este módulo **no** crea ninguna tabla de base de datos personalizada. Todas sus configuraciones se almacenan en la tabla `ps_configuration` de PrestaShop utilizando las siguientes claves:

-   `ARUKERESO_FILE_LOG`: Almacena el valor booleano para el registro de errores.
-   `ARUKERESO_ID`: Almacena la clave API web de Arukereso.hu.
-   `ARUKERESO_PRODUCT_ID`: Almacena el tipo de identificador de producto elegido (por ejemplo, 'id\_product', 'reference').
-   `ARUKERESO_CONSENT`: Almacena el valor booleano para requerir el consentimiento del cliente.
-   `PS_BO_ALLOW_EMPLOYEE_FORM_LANG`: Una clave de configuración estándar de PrestaShop, no gestionada directamente por este módulo, pero potencialmente utilizada para la gestión de idiomas en el back office.

#### Tabla de ganchos registrados

| Nombre del gancho | Momento de ejecución | Propósito técnico |
| --- | --- | --- |
| `displayGDPRConsent` | Durante el proceso de pago, normalmente cerca del consentimiento de la política de privacidad. | Renderiza la casilla de verificación de consentimiento del cliente para la participación en la encuesta de Arukereso.hu. |
| `actionDeleteGDPRCustomer` | Se activa cuando un cliente solicita la eliminación de datos a través del módulo GDPR de PrestaShop. | Gestiona la eliminación de cualquier dato específico del cliente almacenado por el módulo (por ejemplo, el estado del consentimiento). |
| `actionExportGDPRData` | Se activa cuando un cliente solicita la exportación de datos a través del módulo GDPR de PrestaShop. | Proporciona cualquier dato específico del cliente almacenado por el módulo para su exportación. |
| `displayOrderConfirmation` | En la página de confirmación del pedido después de una compra exitosa. | Renderiza un mensaje informativo al cliente y, crucialmente, envía los datos del pedido a la API de Arukereso.hu si se da el consentimiento. |
| `displayPaymentTop` | En la parte superior de la sección de pago durante el proceso de pago. | Gancho alternativo para renderizar la casilla de verificación de consentimiento del cliente, dependiendo del tema. |
| `displayCheckoutSummaryTop` | En la parte superior de la sección de resumen del proceso de pago. | Gancho alternativo para renderizar la casilla de verificación de consentimiento del cliente, dependiendo del tema. |
| `DisplayGDPRConsent` | (Alias/Versión anterior de `displayGDPRConsent`) | Renderiza la casilla de verificación de consentimiento del cliente. |
| `DisplayPaymentTop` | (Alias/Versión anterior de `displayPaymentTop`) | Renderiza la casilla de verificación de consentimiento del cliente. |
| `DisplayOrderConfirmation` | (Alias/Versión anterior de `displayOrderConfirmation`) | Renderiza información y envía datos del pedido. |
| `ActionDeleteGDPRCustomer` | (Alias/Versión anterior de `actionDeleteGDPRCustomer`) | Gestiona la eliminación de datos del cliente. |
| `ActionExportGDPRData` | (Alias/Versión anterior de `actionExportGDPRData`) | Gestiona la exportación de datos del cliente. |
| `DisplayCheckoutSummaryTop` | (Alias/Versión anterior de `displayCheckoutSummaryTop`) | Renderiza la casilla de verificación de consentimiento del cliente. |

La lógica central del módulo para enviar datos de pedidos a Arukereso.hu reside en el método `hookDisplayOrderConfirmation` en `arukereso.php`. Este método verifica el consentimiento del cliente (si es necesario) y luego construye y envía una solicitud HTTP a la API de Arukereso.hu con los detalles del pedido.

## 5. Soporte oficial y actualizaciones

Para las últimas actualizaciones del módulo, correcciones de errores y soporte oficial, consulte su cuenta de cliente en [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nuestro equipo de soporte está disponible para ayudarle con cualquier problema técnico o pregunta que pueda tener con respecto al módulo Arukereso.hu - correos electrónicos de encuestas del programa de compra de confianza.
