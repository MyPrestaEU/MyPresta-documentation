---
title: "Compartir producto en Facebook + código de descuento - Manual de Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop 'Compartir producto en Facebook + código de descuento' de MyPresta.eu."
sidebar:
  label: "Compartir producto en Facebook + código de descuento"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Facebook product share + discount code en MyPresta.eu](https://mypresta.eu/modules/social-networks/facebook-product-share-discount-code.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/social-networks/facebook-product-share-discount-code/)
>
> ---


# Compartir producto en Facebook + código de descuento

## 1. Requisitos y compatibilidad
-   **Versiones de PrestaShop compatibles**: PrestaShop 1.4.x, 1.5.x, 1.6.x, 1.7.x, 8.x
-   **Compatibilidad con PHP**: PHP 5.6 - 8.5
-   **Requisitos de alojamiento**: Las extensiones PHP estándar (cURL, JSON, OpenSSL) suelen ser necesarias para PrestaShop y generalmente están disponibles en la mayoría de los entornos de alojamiento.

## 2. Recorrido completo por la configuración (Cada ajuste agrupado por pantalla)

### 2.1 Página de configuración del módulo (Back Office > Módulos > Configurar)
Después de la instalación, navegue a **Módulos > Gestor de módulos** y haga clic en "Configurar" junto a "Compartir producto en Facebook + código de descuento". Esta pantalla le permite controlar la funcionalidad principal y la apariencia del módulo.

#### **Configuración general**

-   **Activar / Desactivar Módulo:**
    -   **Qué hace este ajuste:** Este es el interruptor principal para todo el módulo.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando está activado:* El botón de compartir en Facebook aparecerá en las páginas de producto y la funcionalidad de código de descuento estará activa.
        -   *Cuando está desactivado:* El módulo estará completamente inactivo. El botón de compartir no aparecerá y no se generarán códigos de descuento.
    -   **Valor recomendado:** SÍ (para activar las funciones del módulo).
    -   **Escenario / ejemplo de comerciante:** Si está configurando el módulo por primera vez o realizando mantenimiento, podría desactivarlo temporalmente. Una vez listo, actívelo para empezar a generar compartidos y descuentos.

-   **ID de la aplicación de Facebook:**
    -   **Qué hace este ajuste:** Este campo requiere su ID de aplicación de Facebook único. Este ID es crucial para que Facebook identifique correctamente su sitio web y rastree los compartidos. Necesita crear una aplicación de Facebook en la plataforma de desarrolladores de Facebook (developers.facebook.com) para obtener este ID.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando se introduce correctamente:* El módulo se comunicará correctamente con Facebook, permitiendo que se rastreen los compartidos y que funcione el mecanismo de descuento.
        -   *Cuando es incorrecto o está vacío:* La funcionalidad de compartir en Facebook puede no funcionar, o los compartidos pueden no ser rastreados, impidiendo la emisión de códigos de descuento.
    -   **Valor recomendado:** Su ID de aplicación de Facebook válido (por ejemplo, `123456789012345`).
    -   **Escenario / ejemplo de comerciante:** Ha creado una aplicación de Facebook para su tienda. Copie el ID de la aplicación de su panel de control de desarrollador de Facebook y péguelo aquí. Esta es una configuración única.

-   **Tipo de descuento:**
    -   **Qué hace este ajuste:** Determina el tipo de descuento que los clientes reciben después de compartir.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando se establece en "Porcentaje":* El código de descuento ofrecerá un porcentaje de descuento sobre el total del pedido (por ejemplo, 10% de descuento).
        -   *Cuando se establece en "Cantidad":* El código de descuento ofrecerá un valor monetario fijo de descuento sobre el total del pedido (por ejemplo, 5 € de descuento).
    -   **Valor recomendado:** "Porcentaje" o "Cantidad" según su estrategia de marketing.
    -   **Escenario / ejemplo de comerciante:** Si desea fomentar pedidos más grandes, un descuento porcentual podría ser más atractivo. Para compras más pequeñas y frecuentes, una cantidad fija podría ser más efectiva.

-   **Valor del descuento:**
    -   **Qué hace este ajuste:** Especifica el valor real del descuento.
    -   **Efecto de cambiar este ajuste:**
        -   *Si el "Tipo de descuento" es Porcentaje:* Introduzca el valor porcentual (por ejemplo, `10` para 10%).
        -   *Si el "Tipo de descuento" es Cantidad:* Introduzca el valor monetario (por ejemplo, `5.00` para 5 €).
    -   **Valor recomendado:** Un valor que sea atractivo para los clientes pero también rentable para su negocio (por ejemplo, `10` para 10% de descuento, o `5.00` para 5 € de descuento).
    -   **Escenario / ejemplo de comerciante:** Decide ofrecer un 15% de descuento por compartir. Establecería "Tipo de descuento" en "Porcentaje" y "Valor del descuento" en `15`.

-   **Cantidad mínima para el descuento:**
    -   **Qué hace este ajuste:** Establece un total de pedido mínimo (antes del envío) que un cliente debe cumplir para usar el código de descuento generado.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando se introduce un valor (por ejemplo, `50.00`):* El código de descuento solo será válido si el total del carrito del cliente es igual o superior a esta cantidad.
        -   *Cuando se deja vacío o se establece en `0`:* El código de descuento se puede usar en cualquier pedido, independientemente de su valor total.
    -   **Valor recomendado:** Un valor que anime a los clientes a añadir más artículos a su carrito, o `0` si no desea un mínimo.
    -   **Escenario / ejemplo de comerciante:** Para evitar que los clientes usen un descuento del 10% en un artículo de 1 €, podría establecer una cantidad mínima de `25.00 €`.

-   **Validez del código de descuento (en días):**
    -   **Qué hace este ajuste:** Define cuántos días será válido el código de descuento generado desde el momento en que se emite.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando se introduce un valor (por ejemplo, `7`):* El código de descuento caducará después de 7 días, creando una sensación de urgencia.
        -   *Cuando se deja vacío o se establece en `0`:* El código de descuento no tendrá fecha de caducidad (no recomendado, ya que reduce la urgencia).
    -   **Valor recomendado:** `7` a `30` días para fomentar un uso rápido.
    -   **Escenario / ejemplo de comerciante:** Desea que los clientes usen su descuento rápidamente. Establecer esto en `7` días los impulsará a realizar una compra en una semana.

-   **Prefijo del código de descuento:**
    -   **Qué hace este ajuste:** Le permite añadir un prefijo personalizado a todos los códigos de descuento generados. Esto le ayuda a identificar los códigos generados por este módulo en su gestión de descuentos de PrestaShop.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando se introduce un prefijo (por ejemplo, `FBSHARE-`):* Todos los códigos generados comenzarán con este prefijo (por ejemplo, `FBSHARE-XYZ123`).
        -   *Cuando se deja vacío:* Los códigos se generarán sin un prefijo específico.
    -   **Valor recomendado:** Un prefijo corto y descriptivo (por ejemplo, `FB-`, `SHARE-`, `SOCIAL-`).
    -   **Escenario / ejemplo de comerciante:** Para rastrear fácilmente el éxito de su campaña de compartidos en Facebook, podría usar `FB2023-` como prefijo.

-   **Mostrar botón de compartir en:**
    -   **Qué hace este ajuste:** Determina dónde aparecerá el botón de compartir en Facebook en sus páginas de producto. Esto suele ser una selección de menú desplegable o de botón de radio.
    -   **Efecto de cambiar este ajuste:**
        -   *Cabecera:* El botón aparece en la cabecera de la tienda (menos común para compartidos específicos de productos).
        -   *Columnas (Izquierda/Derecha):* El botón aparece en una de las columnas laterales.
        -   *Página de producto (Contenido principal):* El botón aparece dentro del área de información principal del producto (más común y recomendado).
        -   *Pie de página:* El botón aparece en el pie de página de la tienda.
    -   **Valor recomendado:** "Página de producto (Contenido principal)" para máxima visibilidad y relevancia.
    -   **Escenario / ejemplo de comerciante:** Desea que el botón de compartir sea fácilmente visible justo al lado de la imagen y descripción del producto. Seleccionar "Página de producto (Contenido principal)" asegura esto.

-   **Texto para el botón de compartir:**
    -   **Qué hace este ajuste:** Le permite personalizar el texto que se muestra en el botón de compartir en Facebook.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando se introduce texto (por ejemplo, "¡Comparte y obtén descuento!"):* El botón mostrará su texto personalizado.
        -   *Cuando se deja vacío:* Se utilizará un texto predeterminado (por ejemplo, "Compartir en Facebook").
    -   **Valor recomendado:** Texto claro y orientado a la acción que resalte el beneficio (por ejemplo, "¡Comparte para un descuento!", "¡Obtén X% de descuento - Comparte ahora!").
    -   **Escenario / ejemplo de comerciante:** Para atraer a los clientes, podría cambiar el texto del botón a "¡Comparte y desbloquea tu descuento!".

-   **Título del mensaje emergente:**
    -   **Qué hace este ajuste:** Establece el título de la ventana emergente que aparece después de un compartido exitoso, mostrando el código de descuento.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando se introduce un título (por ejemplo, "¡Felicidades!"):* La ventana emergente mostrará su título personalizado.
        -   *Cuando se deja vacío:* Se utilizará un título predeterminado.
    -   **Valor recomendado:** Un título acogedor y de felicitación (por ejemplo, "¡Tu código de descuento!", "¡Gracias por compartir!").
    -   **Escenario / ejemplo de comerciante:** Desea que el cliente se sienta recompensado, por lo que establece el título en "¡Aquí tienes tu descuento exclusivo!".

-   **Contenido del mensaje emergente:**
    -   **Qué hace este ajuste:** Le permite personalizar el contenido de texto principal dentro de la ventana emergente del código de descuento. Puede incluir instrucciones o mensajes adicionales.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando se introduce contenido:* La ventana emergente mostrará su mensaje personalizado.
        -   *Cuando se deja vacío:* Se utilizará un mensaje predeterminado.
    -   **Valor recomendado:** Un mensaje claro que instruya al cliente a copiar el código y cómo usarlo (por ejemplo, "Copia este código y aplícalo en la caja para recibir tu descuento.").
    -   **Escenario / ejemplo de comerciante:** Desea recordar a los clientes dónde usar el código: "¡Gracias por compartir! Usa el código a continuación en la caja para tus ahorros."

#### **Configuración avanzada (si está disponible)**

-   **Hoja de estilos CSS para botón/ventana emergente:**
    -   **Qué hace este ajuste:** Le permite seleccionar o introducir CSS personalizado para estilizar el botón de compartir y/o la ventana emergente de descuento para que coincidan mejor con su tema.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando se aplica CSS personalizado:* La apariencia visual (colores, fuentes, tamaños) del botón y la ventana emergente cambiará según sus estilos.
        -   *Cuando se usa el predeterminado:* El módulo utilizará su estilo incorporado.
    -   **Valor recomendado:** Dejar vacío inicialmente, luego personalizar si el estilo predeterminado no coincide con su marca.
    -   **Escenario / ejemplo de comerciante:** Su tienda utiliza un tono específico de azul para los botones. Puede añadir una regla CSS aquí para cambiar el color de fondo del botón de compartir a ese tono.

### 2.2 Tabla de referencia rápida de configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| :------------ | :--------------- | :-------------------- | :--------------- |
| Configuración del módulo | Activar / Desactivar Módulo | SÍ | Activa/desactiva todas las funciones del módulo. |
| | ID de la aplicación de Facebook | Su ID de aplicación | Vincula su tienda a su aplicación de Facebook para rastrear compartidos. |
| | Tipo de descuento | Porcentaje | Define si el descuento es un porcentaje o una cantidad fija. |
| | Valor del descuento | por ejemplo, 10 (para 10%) | El valor real del descuento ofrecido. |
| | Cantidad mínima para el descuento | 0 (sin mínimo) | Establece un valor de pedido mínimo para el uso del código de descuento. |
| | Validez del código de descuento (en días) | 7-30 días | Establece un período de caducidad para los códigos de descuento generados. |
| | Prefijo del código de descuento | FB- | Añade un prefijo personalizado a los códigos generados para una fácil identificación. |
| | Mostrar botón de compartir en | Página de producto (Contenido principal) | Controla la ubicación del botón de compartir en las páginas de producto. |
| | Texto para el botón de compartir | ¡Comparte para un descuento! | Personaliza el texto que se muestra en el botón de compartir. |
| | Título del mensaje emergente | ¡Tu código de descuento! | Establece el título de la ventana emergente del código de descuento. |
| | Contenido del mensaje emergente | Copia este código... | Personaliza el mensaje principal dentro de la ventana emergente del código de descuento. |

## 3. Solución de problemas del comerciante y preguntas frecuentes (FAQ)

**P1: El botón de compartir en Facebook no aparece en mis páginas de producto.**
**R1:**
*   **Verificar estado del módulo:** Asegúrese de que el módulo esté activado en la configuración.
*   **Verificar ID de la aplicación de Facebook:** Vuelva a comprobar que su ID de aplicación de Facebook esté correctamente introducido en la configuración del módulo. Un ID incorrecto o faltante impedirá que el botón se cargue.
*   **Verificar ubicación del botón:** Confirme que la configuración "Mostrar botón de compartir en" esté correctamente elegida (por ejemplo, "Página de producto (Contenido principal)"). Si su tema tiene ganchos muy personalizados, es posible que deba probar diferentes ubicaciones o consultar a un desarrollador.
*   **Borrar caché:** Vaya a **Parámetros avanzados > Rendimiento** en su Back Office de PrestaShop y borre la caché de Smarty y todas las cachés. A veces, los archivos de caché antiguos impiden que aparezcan nuevos elementos del módulo.

**P2: Los clientes están compartiendo, pero no reciben un código de descuento.**
**R2:**
*   **ID de la aplicación de Facebook:** Esta es la causa más común. El módulo se basa en el ID de la aplicación de Facebook para rastrear los compartidos exitosos. Asegúrese de que sea correcto y de que su aplicación de Facebook esté configurada correctamente (por ejemplo, la URL del sitio web está añadida).
*   **Permisos/Privacidad de Facebook:** A veces, la configuración de privacidad de Facebook de un cliente o los bloqueadores de anuncios del navegador pueden interferir con el seguimiento de compartidos. Esto es menos común, pero puede suceder.
*   **Configuración del módulo:** Revise todos los ajustes relacionados con el descuento (Tipo de descuento, Valor, Validez). Asegúrese de que estén configurados con valores válidos.
*   **Configuración de vales de PrestaShop:** Asegúrese de que la configuración general de vales/reglas de carrito de su tienda PrestaShop no impida la creación de nuevos códigos (por ejemplo, se alcanzó el número máximo de vales, aunque esto es raro).

**P3: La ventana emergente del código de descuento se ve extraña o no coincide con el diseño de mi tienda.**
**R3:**
*   **Conflictos de tema:** Su tema personalizado de PrestaShop podría tener estilos CSS en conflicto.
*   **CSS del módulo:** El módulo incluye su propio CSS. Puede intentar anularlo.
*   **Solución:** En la configuración del módulo, busque cualquier opción de "CSS personalizado" o "Hoja de estilos". Es posible que deba añadir reglas CSS personalizadas allí para ajustar la apariencia de la ventana emergente. Si no se siente cómodo con CSS, un webmaster o desarrollador puede ayudarle. Borrar la caché de su navegador también puede resolver a veces problemas menores de visualización.

**P4: ¿Puedo traducir el texto del botón y los mensajes emergentes a otros idiomas?**
**R4:** Sí, el sistema de traducción de PrestaShop admite traducciones de módulos.
*   Vaya a **Internacional > Traducciones** en su Back Office.
*   Seleccione "Traducciones de módulos instalados", elija su tema y luego seleccione su idioma.
*   Busque el módulo "Compartir producto en Facebook + código de descuento" y podrá traducir todos los textos orientados al usuario, incluido el texto del botón y los mensajes emergentes.

**P5: ¿Qué sucede si un cliente comparte un producto varias veces? ¿Obtiene varios descuentos?**
**R5:** El módulo está diseñado para emitir un código de descuento único por *evento de compartido exitoso* para un usuario determinado. Sin embargo, dependiendo de la implementación exacta, un usuario podría compartir diferentes productos y recibir varios códigos. Generalmente, la mejor práctica es fomentar compartidos únicos para recompensas únicas. Si desea limitarlo a un código por cliente, independientemente de los compartidos, es posible que necesite un desarrollo personalizado o gestionar manualmente los vales generados.

## 4. Guía para desarrolladores y webmasters (Arquitectura técnica y mapa de código)
Esta sección proporciona una inmersión profunda en la estructura técnica del módulo "Compartir producto en Facebook + código de descuento" para desarrolladores y webmasters.

### 4.1 Resumen de la arquitectura
El módulo sigue una arquitectura de módulo estándar de PrestaShop, aprovechando principalmente la clase `Module` para la instalación, desinstalación y configuración. Se integra con el front-office a través de ganchos para mostrar el botón de compartir y utiliza AJAX para manejar la generación del código de descuento posterior al compartido. La lógica central para la creación de vales probablemente está encapsulada dentro de la clase principal del módulo o un ayudante.

### 4.2 Controladores (`controllers/`)
Este módulo no parece utilizar archivos `ModuleFrontController` o `AdminController` dedicados en el directorio `controllers/` según el inventario proporcionado. Las interacciones AJAX del front-office probablemente se manejan directamente dentro del archivo principal del módulo (`ajax_productlike.php`) o a través de un despachador AJAX genérico de PrestaShop.

### 4.3 Clases y modelos principales (`classes/`)
Según el inventario proporcionado, no hay clases `ObjectModel` personalizadas definidas en un directorio `classes/`. El módulo probablemente gestiona su configuración directamente a través de `Configuration::get()` y `Configuration::updateValue()` y crea objetos `CartRule` de PrestaShop para los descuentos.

### 4.4 Activos JavaScript (`views/js/`)
El módulo incluye varios archivos JavaScript, lo que indica una lógica del lado del cliente para la interacción con Facebook y la visualización de ventanas emergentes.

-   `productlike/js/productlike.js`:
    *   **Alcance:** Front-office.
    *   **Responsabilidad:** Probablemente maneja la lógica central para iniciar el diálogo de compartir de Facebook, escuchar el evento de finalización de compartido del SDK de Facebook y luego realizar una llamada AJAX de vuelta a la tienda PrestaShop para solicitar el código de descuento. También gestionaría la visualización de la ventana emergente del código de descuento.
    *   **Funcionalidades clave:** Inicialización del SDK de Facebook, llamadas al método `FB.ui` para compartir, solicitudes AJAX al backend del módulo, manipulación del DOM para la visualización de ventanas emergentes.

-   `productlike/js/script.js`:
    *   **Alcance:** Front-office.
    *   **Responsabilidad:** Podría ser un script de utilidad general o una alternativa/respaldo a `productlike.js`. Podría contener oyentes de eventos para el clic del botón de compartir, o manejar la lógica de visualización/ocultación de la ventana emergente de descuento.
    *   **Funcionalidades clave:** Enlace de eventos, potencialmente animaciones simples o manipulación del DOM.

-   `productlike/lib/voucherengine/script.js`:
    *   **Alcance:** Front-office.
    *   **Responsabilidad:** Sugiere un script dedicado para la visualización e interacción del vale. Esto podría manejar la copia del código del vale al portapapeles, el cierre de la ventana emergente u otros elementos de la interfaz de usuario relacionados con el descuento.
    *   **Funcionalidades clave:** Interacción con la API del portapapeles, eventos de cierre de ventanas emergentes, retroalimentación de la interfaz de usuario.

### 4.5 Hojas de estilo CSS (`views/css/`)
El módulo utiliza varios archivos CSS para estilizar sus componentes del front-office.

-   `productlike/css/css.css`:
    *   **Alcance:** Estilo del cliente del front-office.
    *   **Responsabilidad:** Contiene estilos generales para el botón de compartir en Facebook y potencialmente la ventana emergente del código de descuento.
    *   **Selectores clave:** `.productlike-button`, `.productlike-popup`, `.productlike-voucher-code`. Los desarrolladores pueden anularlos en el `custom.css` de su tema o utilizando la entrada CSS personalizada del módulo si está disponible.

-   `productlike/css.css`:
    *   **Alcance:** Estilo del cliente del front-office.
    *   **Responsabilidad:** Potencialmente una hoja de estilos más antigua o alternativa, o estilos específicos para ciertos elementos no cubiertos por `css.css`.
    *   **Selectores clave:** Similares a `css.css`, dependiendo de su contenido.

-   `productlike/lib/voucherengine/ps16.css`:
    *   **Alcance:** Estilo del cliente del front-office, específicamente para la compatibilidad con PrestaShop 1.6.
    *   **Responsabilidad:** Proporciona ajustes de estilo para asegurar que la ventana emergente del vale y el botón se vean correctamente en los temas de PrestaShop 1.6, que podrían tener diferentes estilos de elementos predeterminados.
    *   **Selectores clave:** Probablemente apunta a elementos comunes de la interfaz de usuario de PrestaShop 1.6 para asegurar la coherencia visual.

### 4.6 Estructura de plantillas Smarty (`views/templates/`)
El módulo utiliza plantillas Smarty para renderizar sus componentes del front-office.

-   **Plantillas de gancho (`views/templates/hook/`)**:
    *   `productlike/header.tpl`:
        *   **Gancho:** `displayHeader`
        *   **Propósito:** Esta plantilla es probablemente responsable de inicializar el SDK de JavaScript de Facebook, cargar los archivos JavaScript necesarios y potencialmente pasar variables de configuración (como el ID de la aplicación de Facebook) del backend del módulo al JavaScript del front-end. Asegura que la API de Facebook esté lista antes de que se renderice el botón de compartir.
    *   `productlike/share.tpl`:
        *   **Gancho:** `displayProductButtons`, `displayRightColumnProduct`, `displayLeftColumnProduct`, `displayFooterProduct` (o ganchos similares de la página de producto, según la configuración).
        *   **Propósito:** Renderiza el botón real "Compartir en Facebook" en la página del producto. Contendrá la estructura HTML para el botón y potencialmente un marcador de posición para la ventana emergente del código de descuento, que luego es poblada dinámicamente por JavaScript.

-   **Plantillas de administración (`views/templates/admin/`)**: Ninguna listada explícitamente, lo que implica que la configuración se maneja directamente por `getContent()` en el archivo principal del módulo.

-   **Plantillas de front-office (`views/templates/front/`)**: Ninguna listada explícitamente, ya que la interacción principal es a través de ganchos y ventanas emergentes.

### 4.7 Esquema de la base de datos y mapa de ganchos

-   **Tablas de la base de datos**:
    *   Es probable que el módulo no cree tablas de base de datos personalizadas.
    *   La configuración (ID de la aplicación de Facebook, valores de descuento, etc.) se almacena en la tabla `ps_configuration` utilizando claves como `PRODUCTLIKE_FACEBOOK_APP_ID`, `PRODUCTLIKE_DISCOUNT_TYPE`, `PRODUCTLIKE_DISCOUNT_VALUE`, etc.
    *   Los códigos de descuento generados son entradas estándar de `CartRule` de PrestaShop, almacenadas en `ps_cart_rule` y tablas relacionadas.

-   **Tabla de ganchos registrados**:

| Nombre del gancho | Momento de ejecución | Propósito técnico |
| :-------- | :--------------- | :---------------- |
| `displayHeader` | En la sección `<head>` de cada página. | Inicializa el SDK de Facebook, carga JS/CSS del módulo, pasa variables de configuración. |
| `displayProductButtons` | En la página del producto, típicamente cerca del botón Añadir al carrito. | Renderiza el botón de compartir en Facebook. (Común para PS 1.7+) |
| `displayRightColumnProduct` | En la columna derecha de la página del producto. | Renderiza el botón de compartir en Facebook (si está configurado). |
| `displayLeftColumnProduct` | En la columna izquierda de la página del producto. | Renderiza el botón de compartir en Facebook (si está configurado). |
| `displayFooterProduct` | En el área del pie de página de la página del producto. | Renderiza el botón de compartir en Facebook (si está configurado). |
| `displayProductExtraContent` | En la página del producto, para pestañas/bloques de contenido extra. | Gancho alternativo para la ubicación del botón (PS 1.7+). |
| `actionFrontControllerSetMedia` | Antes de que el controlador frontal renderice la página. | Registra los archivos JS y CSS del módulo. |
| `actionObjectCartRuleAddAfter` | Después de que se añade una nueva regla de carrito (vale). | Potencialmente utilizado para el registro o procesamiento adicional de vales generados. |

## 5. Soporte oficial y actualizaciones
Para las últimas actualizaciones, correcciones de errores y soporte profesional para su módulo "Compartir producto en Facebook + código de descuento", consulte su cuenta de cliente en [MyPresta.eu](https://mypresta.eu/). Nuestro equipo se dedica a brindar asistencia y garantizar que su módulo funcione de manera óptima.
