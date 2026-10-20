---
title: "Compari.ro - correos electrónicos de encuestas del programa de compra de confianza - Manual del Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop Compari.ro - correos electrónicos de encuestas del programa de compra de confianza de MyPresta.eu."
sidebar:
  label: "Compari.ro - correos electrónicos de encuestas del programa de compra de confianza - Manual del Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Compari.ro - trusted purchase program survey emails en MyPresta.eu](https://mypresta.eu/modules/advertising-and-marketing/compariro-trusted-purchase-program-survey-emails.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/advertising-marketing/compariro-trusted-purchase-program-survey-emails/)
>
> ---


# Compari.ro - correos electrónicos de encuestas del programa de compra de confianza

## 1. Requisitos y compatibilidad

- **Versiones de PrestaShop compatibles**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilidad PHP**: PHP 7.1 - 8.5
- **Requisitos de alojamiento**: Las extensiones PHP estándar (cURL, JSON, OpenSSL) suelen ser necesarias para PrestaShop y son suficientes para este módulo.

## 2. Recorrido completo por la configuración (Cada ajuste agrupado por pantalla)

### 2.1 Página de configuración del módulo (Back Office > Módulos > Configurar)

Esta es la pantalla de configuración principal y única para el módulo Compari.ro. Puede acceder a ella navegando a **Módulos > Gestor de módulos**, buscando "Compari.ro" y haciendo clic en el botón "Configurar".

#### **1. Compari.ro WebApiKey**

-   **Qué hace esta configuración:** Este es su identificador único proporcionado por Compari.ro que vincula su tienda PrestaShop a su cuenta de comerciante de Compari.ro. Es esencial para que el "Programa de Compra de Confianza" atribuya correctamente las solicitudes de encuesta a su tienda.
-   **Efecto de cambiar esta configuración:**
    -   *Cuando se introduce correctamente:* El módulo podrá enviar datos de pedidos a Compari.ro, permitiéndoles enviar correos electrónicos de encuestas a sus clientes.
    -   *Cuando es incorrecto o está vacío:* La integración fallará y Compari.ro no recibirá información de pedidos, lo que significa que no se enviarán correos electrónicos de encuestas.
-   **Valor recomendado:** Introduzca la WebApiKey exacta que le proporcionó Compari.ro.
-   **Escenario / ejemplo de comerciante:** Se ha registrado en el "Programa de Compra de Confianza" de Compari.ro y ha recibido un correo electrónico con su clave API. Debe copiar y pegar esta clave aquí para que la integración funcione.

#### **2. Identificador de producto (feed ITEM\_ID)**

-   **Qué hace esta configuración:** Esta configuración define qué identificador de producto de su tienda PrestaShop debe usarse como `ITEM_ID` al enviar información de producto a Compari.ro. Esto es crucial para hacer coincidir los productos de su feed de Compari.ro con los productos de sus pedidos.
-   **Efecto de cambiar esta configuración:**
    -   *Cuando se establece en `id_product` (predeterminado):* Se utilizará el ID de producto interno de PrestaShop. Esta suele ser la opción más segura si no tiene un identificador personalizado específico.
    -   *Cuando se establece en `reference`:* Se utilizará el código de referencia del producto. Elija esta opción si su feed de productos de Compari.ro utiliza la referencia del producto como `ITEM_ID`.
    -   *Cuando se establece en `ean13`:* Se utilizará el código de barras EAN-13 del producto. Elija esta opción si su feed de productos de Compari.ro utiliza EAN-13 como `ITEM_ID`.
    -   *Cuando se establece en `upc`:* Se utilizará el código UPC del producto. Elija esta opción si su feed de productos de Compari.ro utiliza UPC como `ITEM_ID`.
-   **Valor recomendado:** `id_product` (a menos que su feed de productos de Compari.ro utilice explícitamente `reference`, `ean13` o `upc` como `ITEM_ID`).
-   **Escenario / ejemplo de comerciante:** Su feed de productos de Compari.ro utiliza el código de barras EAN-13 único para cada producto. Seleccionaría `ean13` aquí para asegurarse de que Compari.ro pueda identificar correctamente los productos comprados por sus clientes.

#### **3. Requerir consentimiento del cliente**

-   **Qué hace esta configuración:** Esta opción determina si sus clientes deben aceptar explícitamente participar en el programa de encuestas de Compari.ro durante el proceso de pago. Esto es importante para el cumplimiento del GDPR y para respetar las preferencias de privacidad del cliente.
-   **Efecto de cambiar esta configuración:**
    -   *Cuando está habilitado (establecido en "Sí"):* Aparecerá una casilla de verificación durante el proceso de pago (por ejemplo, en la página de pago o en el resumen del pago). Los clientes deben marcar esta casilla para permitir que los datos de su pedido se envíen a Compari.ro para fines de encuesta. Si no dan su consentimiento, no se enviará ningún correo electrónico de encuesta para su pedido.
    -   *Cuando está deshabilitado (establecido en "No"):* No se mostrará ninguna casilla de verificación de consentimiento. Los datos del pedido se enviarán a Compari.ro para todos los pedidos, asumiendo que la `WebApiKey` es correcta.
-   **Valor recomendado:** "Sí" si opera en regiones con leyes estrictas de privacidad de datos (como el GDPR) o si desea dar a los clientes control total sobre el intercambio de sus datos. "No" si ha determinado que el consentimiento explícito no es necesario para su contexto legal específico o si desea maximizar la participación en la encuesta.
-   **Escenario / ejemplo de comerciante:** Para cumplir con las regulaciones del GDPR, habilita esta configuración. Durante el proceso de pago, los clientes ven una casilla de verificación "Acepto participar en la encuesta del Programa de Compra de Confianza de Compari.ro". Solo los clientes que marquen esta casilla recibirán un correo electrónico de encuesta.

#### **4. Escribir errores en log.txt**

-   **Qué hace esta configuración:** Esta es una opción de depuración que controla si el módulo registra los errores encontrados durante su funcionamiento (por ejemplo, problemas al enviar datos a Compari.ro) en un archivo `log.txt` dentro del directorio del módulo.
-   **Efecto de cambiar esta configuración:**
    -   *Cuando está habilitado (establecido en "Sí"):* Cualquier error técnico se escribirá en `compari/log.txt`. Este archivo puede ser muy útil para su webmaster o el soporte de MyPresta.eu para diagnosticar problemas.
    -   *Cuando está deshabilitado (establecido en "No"):* Los errores no se registrarán explícitamente en un archivo. Esto generalmente se prefiere para las tiendas de producción en vivo para evitar generar archivos de registro grandes, a menos que esté solucionando activamente un problema.
-   **Valor recomendado:** "No" para una tienda de producción en vivo. "Sí" si está experimentando problemas con la integración y necesita depurar. Recuerde deshabilitarlo una vez que el problema esté resuelto.
-   **Escenario / ejemplo de comerciante:** Ha configurado el módulo, pero los clientes no reciben correos electrónicos de encuestas. Habilita "Escribir errores en log.txt" y luego realiza un pedido de prueba. Luego, verifica el archivo `log.txt` en busca de pistas sobre por qué la integración podría estar fallando.

### 2.2 Tabla de referencia rápida de configuración

| Pantalla / Vista | Configuración / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| Configuración del módulo | Compari.ro WebApiKey | Su clave API única | Vincula su tienda a Compari.ro para la automatización de encuestas. **Crítico para la funcionalidad.** |
| Configuración del módulo | Identificador de producto (feed ITEM\_ID) | `id_product` (o coincidir con su feed) | Especifica qué ID de producto (interno, referencia, EAN, UPC) enviar a Compari.ro. |
| Configuración del módulo | Requerir consentimiento del cliente | Sí (para GDPR) | Muestra una casilla de verificación de consentimiento durante el proceso de pago. Si no se marca, no se envía ningún correo electrónico de encuesta. |
| Configuración del módulo | Escribir errores en log.txt | No (habilitar para depuración) | Registra errores técnicos en `compari/log.txt` para la resolución de problemas. |

## 3. Resolución de problemas del comerciante y preguntas frecuentes (FAQ)

**P1: Mis clientes no reciben correos electrónicos de encuestas de Compari.ro, pero el módulo está configurado.**
R1:

-   **Verifique la WebApiKey:** Vuelva a verificar que su "Compari.ro WebApiKey" esté ingresada correcta y exactamente como la proporcionó Compari.ro. Incluso un solo error tipográfico impedirá que la integración funcione.
-   **Verifique la configuración de consentimiento:** Si "Requerir consentimiento del cliente" está configurado en "Sí", asegúrese de que sus clientes de prueba realmente marquen la casilla de consentimiento durante el proceso de pago.
-   **Verifique la cuenta de Compari.ro:** Inicie sesión en su cuenta de comerciante de Compari.ro para ver si hay algún mensaje de error o si se están recibiendo pedidos de su tienda.
-   **Habilite el registro:** Establezca "Escribir errores en log.txt" en "Sí" en la configuración del módulo, realice un pedido de prueba y luego verifique el archivo `compari/log.txt` en busca de mensajes de error. Esto proporcionará detalles técnicos específicos.
-   **Borrar caché:** A veces, la caché de PrestaShop puede interferir. Vaya a **Parámetros avanzados > Rendimiento** y haga clic en "Borrar caché".

**P2: Habilité "Requerir consentimiento del cliente", pero no veo una casilla de verificación durante el proceso de pago.**
R2:

-   **Compatibilidad del tema:** El módulo utiliza hooks estándar de PrestaShop (`displayGDPRConsent`, `displayPaymentTop`, `displayCheckoutSummaryTop`) para mostrar la casilla de verificación de consentimiento. Si su tema personalizado modifica en gran medida el proceso de pago, es posible que estos hooks no se rendericen o que el estilo haga que la casilla de verificación sea invisible.
-   **Caché:** Borre la caché de su PrestaShop (**Parámetros avanzados > Rendimiento**).
-   **Posición del módulo:** Asegúrese de que el módulo no esté deshabilitado para los hooks específicos que utiliza. Aunque es menos común para una casilla de verificación de consentimiento, vale la pena verificarlo en **Diseño > Posiciones**.

**P3: ¿Qué sucede si un cliente cambia de opinión sobre el consentimiento después de realizar un pedido?**
R3: El módulo procesa el consentimiento en el momento de realizar el pedido. Si un cliente desea revocar el consentimiento para futuras encuestas, normalmente tendría que gestionarlo directamente con Compari.ro o a través de las herramientas generales de gestión de datos GDPR de su tienda (si las tiene). El módulo en sí no ofrece una "deshacer" directa para pedidos anteriores, pero se integra con los hooks GDPR de PrestaShop para la eliminación y exportación de datos.

**P4: Veo que un archivo `log.txt` está creciendo mucho. ¿Qué debo hacer?**
R4: Si no está solucionando activamente un problema, establezca la opción "Escribir errores en log.txt" en "No" en la configuración del módulo. Esto evitará que el módulo escriba más entradas en el archivo de registro. Luego puede eliminar de forma segura el archivo `log.txt` para liberar espacio.

## 4. Guía para desarrolladores y webmasters (Arquitectura técnica y mapa de código)

Esta sección es estrictamente para desarrolladores, webmasters de tiendas y agencias técnicas que mantienen o extienden la tienda.

### 4.1 Descripción general de la arquitectura

El módulo `Compari` es un módulo de PrestaShop sencillo centrado principalmente en la integración con una API externa (Compari.ro) basada en eventos de pedidos. Sigue una estructura de módulo estándar de PrestaShop, aprovechando los hooks para inyectar contenido (consentimiento GDPR) y activar acciones (envío de datos de pedidos). No introduce controladores personalizados ni ObjectModels complejos, basándose en los datos centrales de `Order` y `Customer` de PrestaShop. La lógica principal reside en el archivo `compari.php`, que maneja la configuración, la instalación y las devoluciones de llamada de los hooks.

### 4.2 Controladores (`controllers/`)

-   Este módulo **no** contiene ningún controlador de administración de Front-Office o Back-Office personalizado. Toda la lógica se maneja dentro del archivo principal `compari.php` a través de hooks.

### 4.3 Clases y modelos principales (`classes/`)

-   Este módulo **no** contiene ninguna clase personalizada u ObjectModels en el directorio `classes/`. Todo el manejo de datos se realiza directamente dentro del archivo `compari.php` utilizando las entidades centrales `Order`, `Customer` y `Product` de PrestaShop.

### 4.4 Activos de JavaScript (`views/js/`)

-   Este módulo **no** contiene ningún archivo JavaScript personalizado.

### 4.5 Hojas de estilo CSS (`views/css/`)

-   Este módulo **no** contiene ningún archivo CSS personalizado. Se espera que el estilo de la casilla de verificación de consentimiento se herede del tema o lo maneje el estilo del módulo GDPR central de PrestaShop.

### 4.6 Estructura de la plantilla Smarty (`views/templates/`)

-   **Plantillas de hook (`views/templates/hook/`)**:
    -   `compari/views/templates/hook/consent.tpl`:
        -   **Hook:** `displayGDPRConsent`, `displayPaymentTop`, `displayCheckoutSummaryTop`
        -   **Propósito:** Renderiza la casilla de verificación de consentimiento GDPR y el texto asociado, permitiendo a los clientes optar por participar o no en el programa de encuestas de Compari.ro. Esta plantilla solo se renderiza si la configuración `COMPARI_CONSENT` está habilitada.
        -   **Salida:** Un campo de entrada de casilla de verificación con una etiqueta.
    -   `compari/views/templates/hook/displayOrderConfirmation.tpl`:
        -   **Hook:** `displayOrderConfirmation`
        -   **Propósito:** Esta plantilla se incluye en el hook `displayOrderConfirmation`. Aunque es un archivo de plantilla, su función principal aquí es activar la lógica de backend dentro de `hookDisplayOrderConfirmation` en `compari.php` para enviar datos de pedidos a Compari.ro. No produce contenido visible para el usuario.

### 4.7 Esquema de la base de datos y mapa de hooks

-   **Tablas de la base de datos**:

    -   El módulo **no** crea ninguna tabla SQL personalizada.
    -   Almacena sus configuraciones en la tabla `ps_configuration`:
        -   `COMPARI_FILE_LOG`: Almacena el valor booleano para registrar errores.
        -   `COMPARI_ID`: Almacena la WebApiKey de Compari.ro.
        -   `COMPARI_PRODUCT_ID`: Almacena el tipo de identificador de producto seleccionado (por ejemplo, `id_product`, `reference`).
        -   `COMPARI_CONSENT`: Almacena el valor booleano para requerir el consentimiento del cliente.
-   **Tabla de hooks registrados**:

| Nombre del Hook | Momento de ejecución | Propósito técnico |
| --- | --- | --- |
| `install()` | Durante la instalación del módulo | Establece los valores de configuración predeterminados, registra los hooks. |
| `uninstall()` | Durante la desinstalación del módulo | Elimina los valores de configuración, anula el registro de los hooks. |
| `hookDisplayGDPRConsent` | Se renderiza en páginas donde se recopila el consentimiento GDPR (por ejemplo, checkout) | Muestra la casilla de verificación de consentimiento para la participación en la encuesta de Compari.ro. |
| `hookActionDeleteGDPRCustomer` | Cuando un cliente solicita la eliminación de datos GDPR | Maneja la eliminación de cualquier dato de cliente relacionado con Compari.ro (aunque el módulo no almacena ninguno directamente, es un hook de cumplimiento). |
| `hookActionExportGDPRData` | Cuando un cliente solicita la exportación de datos GDPR | Maneja la exportación de cualquier dato de cliente relacionado con Compari.ro (ninguno almacenado directamente). |
| `hookDisplayOrderConfirmation` | En la página de confirmación del pedido después de una compra exitosa | Activa el envío de datos del pedido a Compari.ro si se da el consentimiento (o no se requiere). |
| `hookDisplayPaymentTop` | Parte superior del paso de pago en el checkout | Hook alternativo para mostrar la casilla de verificación de consentimiento. |
| `hookDisplayCheckoutSummaryTop` | Parte superior del paso de resumen del checkout | Hook alternativo para mostrar la casilla de verificación de consentimiento. |

## 5. Soporte oficial y actualizaciones

Para las últimas actualizaciones, correcciones de errores y soporte oficial para el módulo "Compari.ro - correos electrónicos de encuestas del programa de compra de confianza", consulte su cuenta de cliente en [MyPresta.eu](https://mypresta.eu/). Nuestro equipo de soporte está disponible para ayudarle con cualquier problema técnico o pregunta que pueda tener.
