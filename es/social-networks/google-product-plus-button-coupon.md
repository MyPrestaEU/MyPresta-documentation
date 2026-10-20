---
title: "Botón Google product plus + cupón - Manual del Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop 'Botón Google product plus + cupón' de MyPresta.eu."
sidebar:
  label: "Botón Google product plus + cupón - Manual del Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Google product plus button + coupon en MyPresta.eu](https://mypresta.eu/modules/social-networks/google-product-plus-button-coupon.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/social-networks/google-product-plus-button-coupon/)
>
> ---


# Botón Google product plus + cupón

## 1. Requisitos y Compatibilidad

- **Versiones de PrestaShop Soportadas**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilidad PHP**: PHP 7.1 - 8.5
- **Requisitos de Alojamiento**: Las extensiones PHP estándar (cURL, JSON, OpenSSL) son típicamente requeridas para PrestaShop en sí y para cualquier módulo que interactúe con APIs externas.

## 2. Recorrido Completo por la Configuración (Cada Ajuste Agrupado por Pantalla)

### 2.1 Página de Configuración del Módulo (Back Office > Módulos > Configurar)

Esta es la pantalla de configuración principal para el módulo "Botón Google product plus + cupón". Aquí encontrarás todos los ajustes para controlar cómo aparece el botón Google +1 y cómo se generan los cupones.

#### **Configuración General**

- **Update\_ / Updatev\_ (Configuración Interna)**

  - **Qué hace este ajuste:** Son ajustes internos del módulo utilizados para el seguimiento de actualizaciones y versiones. No están destinados a la interacción directa del comerciante.
  - **Efecto de cambiar este ajuste:** **Nunca** debes cambiar estos valores manualmente. Hacerlo podría interferir con las actualizaciones del módulo o los procesos internos.
  - **Valor recomendado:** Dejar como está.
  - **Escenario / ejemplo del comerciante:** Estos ajustes aseguran que tu módulo pueda actualizarse correctamente cuando MyPresta.eu lance nuevas versiones.
- **Código de Cupón (gc\_voucher)**

  - **Qué hace este ajuste:** Este es el **porcentaje de descuento** que se aplicará al cupón generado para los clientes que hagan clic en el botón +1.
  - **Efecto de cambiar este ajuste:**
    - *Cuando se establece en `10` (para 10%):* Los clientes que hagan +1 en un producto recibirán un cupón del 10% de descuento en su próxima compra.
    - *Cuando se establece en `0` o se deja vacío:* No se aplicará ningún descuento, lo que esencialmente hará que el cupón no tenga valor.
  - **Valor recomendado:** Un porcentaje de descuento razonable, por ejemplo, `5`, `10` o `15`.
  - **Escenario / ejemplo del comerciante:** Quieres ofrecer un 10% de descuento para fomentar el compartir en redes sociales. Introducirías `10` aquí.
- **Mostrar Precios (gc\_show\_prices)**

  - **Qué hace este ajuste:** Determina si los precios originales y con descuento se muestran junto con la oferta del cupón.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está habilitado (Sí):* El cliente verá el precio original y el precio después de aplicar el descuento, lo que hace que el valor del cupón sea más claro.
    - *Cuando está deshabilitado (No):* Solo se mostrará el código del cupón, sin comparaciones de precios explícitas.
  - **Valor recomendado:** `Sí`. Mostrar la diferencia de precio a menudo aumenta el valor percibido del cupón.
  - **Escenario / ejemplo del comerciante:** Un cliente ve un producto por 100 €. Si "Mostrar Precios" está habilitado y el cupón es del 10%, verá "100 € -> 90 € con cupón", lo cual es más atractivo.
- **Mostrar Total (gc\_show\_total)**

  - **Qué hace este ajuste:** Controla si el valor total del pedido (después del descuento) se muestra con el cupón. Esto suele ser relevante si el cupón se aplica a todo el carrito.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está habilitado (Sí):* El cliente podría ver un valor total estimado del pedido con el descuento aplicado.
    - *Cuando está deshabilitado (No):* El enfoque permanece en el precio del producto o en el propio código del cupón.
  - **Valor recomendado:** `Sí`, especialmente si el cupón es para todo el carrito, ya que ayuda al cliente a visualizar sus ahorros.
  - **Escenario / ejemplo del comerciante:** Si el cupón se aplica a todo el carrito, mostrar un posible ahorro total puede fomentar una compra mayor.
- **Mostrar Productos (gc\_show\_products)**

  - **Qué hace este ajuste:** Determina si los productos específicos a los que se aplica el cupón se enumeran cuando se muestra el cupón.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está habilitado (Sí):* El mensaje del cupón podría indicar explícitamente "Este cupón se aplica a [Nombre del Producto]".
    - *Cuando está deshabilitado (No):* El cupón se presenta de forma más general, o se podría asumir que se aplica al producto que acaba de recibir un +1.
  - **Valor recomendado:** `Sí`, para mayor claridad, a menos que tu cupón sea siempre para toda la tienda.
  - **Escenario / ejemplo del comerciante:** Si tu cupón es solo para el producto al que el cliente le dio +1, mostrar el nombre del producto aclara su uso.
- **Mostrar URL del Producto (gc\_show\_product\_url)**

  - **Qué hace este ajuste:** Controla si la URL del producto que recibió un +1 se incluye en la visualización del cupón.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está habilitado (Sí):* El cliente ve un enlace directo a la página del producto, lo que puede ser útil si navega a otro lugar.
    - *Cuando está deshabilitado (No):* La URL se omite.
  - **Valor recomendado:** `Sí`, para una mejor experiencia de usuario y navegación.
  - **Escenario / ejemplo del comerciante:** Un cliente obtiene un cupón y luego cierra la ventana emergente. Tener la URL del producto les ayuda a regresar rápidamente al producto en el que estaban interesados.
- **Última Pestaña (gc\_lasttab)**

  - **Qué hace este ajuste:** Este ajuste probablemente controla en qué pestaña o sección de la página del producto aparecerá el botón Google +1 y la información del cupón, si tu tema utiliza un área de descripción del producto con pestañas.
  - **Efecto de cambiar este ajuste:**
    - *Cuando se establece en `1` (o valor similar):* El contenido del módulo aparecerá en la última pestaña de la página del producto.
    - *Cuando se establece en `0` (o valor similar):* El contenido del módulo aparecerá en la primera pestaña o en una ubicación predeterminada.
  - **Valor recomendado:** Experimenta con `1` para ver si se ajusta al diseño de tu tema. Si tu tema no usa pestañas, este ajuste podría no tener ningún efecto visible.
  - **Escenario / ejemplo del comerciante:** Tu página de producto tiene pestañas "Descripción", "Ficha Técnica" y "Opiniones". Establecer esto en `1` podría colocar el botón +1 y el cupón en una nueva pestaña "Compartir en Redes Sociales" o al final de la pestaña "Descripción".
- **Posición (gc\_position)**

  - **Qué hace este ajuste:** Determina el área general de la página del producto donde se mostrará el botón Google +1 y la oferta del cupón. Esto se mapea al sistema de hooks de PrestaShop.
  - **Efecto de cambiar este ajuste:**
    - *Cambiar el valor:* Mueve el contenido del módulo a diferentes ubicaciones en la página del producto (por ejemplo, encima de "Añadir al carrito", debajo de la descripción, en una columna lateral).
  - **Valor recomendado:** `displayproductActions` o `displayproductFooter` son lugares comunes y efectivos. Prueba diferentes posiciones para ver cuál se integra mejor con tu tema y es más visible para los clientes.
  - **Escenario / ejemplo del comerciante:** Quieres que el botón +1 sea muy prominente, así que eliges `displayproductActions` para colocarlo cerca del botón "Añadir al carrito".
- **Número de Me Gusta (gc\_nblikes)**

  - **Qué hace este ajuste:** Este ajuste probablemente controla el número mínimo de +1 requeridos antes de que se emita un cupón, o podría ser un ajuste de visualización para el recuento de +1. Dada la funcionalidad principal del módulo, es más probable que esté relacionado con el disparador del cupón.
  - **Efecto de cambiar este ajuste:**
    - *Cuando se establece en `1` (o `0`):* Se emite un cupón inmediatamente después de un solo +1.
    - *Cuando se establece en `5`:* Un cupón podría emitirse solo después de 5 +1 únicos (menos probable dada la naturaleza de recompensa instantánea, pero posible para una función de "cupón de grupo"). Más probablemente, controla la visualización del recuento de +1.
  - **Valor recomendado:** `1` (o `0` si significa "mostrar siempre"). La fuerza del módulo es la gratificación instantánea.
  - **Escenario / ejemplo del comerciante:** Quieres que cada cliente que dé +1 obtenga un cupón, así que lo configuras en `1`.
- **Estilo del Botón (gc\_button\_style)**

  - **Qué hace este ajuste:** Te permite elegir el estilo visual o el tamaño del botón Google +1.
  - **Efecto de cambiar este ajuste:**
    - *Cambiar el valor:* Altera la apariencia del botón +1 (por ejemplo, pequeño, mediano, grande, alto, con o sin recuento).
  - **Valor recomendado:** Elige un estilo que sea visible pero que no altere el diseño de tu página de producto. "Mediano" o "Estándar" suelen ser buenos puntos de partida.
  - **Escenario / ejemplo del comerciante:** Tu página de producto tiene espacio limitado, así que eliges un estilo de botón "pequeño".
- **Modo de Compartir (gcshare\_mode)**

  - **Qué hace este ajuste:** Este ajuste probablemente controla cómo funciona la funcionalidad de compartir, posiblemente ofreciendo diferentes formas para que el cliente comparta o interactúe con la plataforma de Google+.
  - **Efecto de cambiar este ajuste:**
    - *Cambiar el valor:* Podría alterar el comportamiento de la ventana emergente o el diálogo de compartir específico de Google+ que aparece.
  - **Valor recomendado:** Dejar el valor predeterminado a menos que tengas una razón específica para cambiarlo y comprendas las implicaciones para la integración con Google+.
  - **Escenario / ejemplo del comerciante:** Podrías experimentar con diferentes modos si encuentras que la experiencia de compartir predeterminada no es óptima para tus clientes.

### 2.2 Tabla de Referencia Rápida de Configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| Configuración del Módulo | Código de Cupón (gc\_voucher) | 10 | Porcentaje de descuento para el cupón generado. |
| Configuración del Módulo | Mostrar Precios (gc\_show\_prices) | Sí | Muestra precios originales y con descuento con el cupón. |
| Configuración del Módulo | Mostrar Total (gc\_show\_total) | Sí | Muestra el valor total estimado del pedido con descuento. |
| Configuración del Módulo | Mostrar Productos (gc\_show\_products) | Sí | Lista los productos específicos a los que se aplica el cupón. |
| Configuración del Módulo | Mostrar URL del Producto (gc\_show\_product\_url) | Sí | Incluye la URL del producto en la visualización del cupón. |
| Configuración del Módulo | Última Pestaña (gc\_lasttab) | 1 (o dependiente del tema) | Posición en las pestañas de la página del producto (si aplica). |
| Configuración del Módulo | Posición (gc\_position) | displayproductActions / displayproductFooter | Ubicación general del botón y el cupón en la página del producto. |
| Configuración del Módulo | Número de Me Gusta (gc\_nblikes) | 1 | Mínimo de +1 para el cupón (probablemente 1 para recompensa instantánea). |
| Configuración del Módulo | Estilo del Botón (gc\_button\_style) | Estándar / Mediano | Tamaño y estilo visual del botón Google +1. |
| Configuración del Módulo | Modo de Compartir (gcshare\_mode) | Predeterminado | Controla la interacción de compartir en Google+. |

## 3. Solución de Problemas del Comerciante y Preguntas Frecuentes (FAQ)

-   **P: El botón Google +1 no aparece en mis páginas de producto.**

    -   **R:** Primero, verifica el ajuste "Posición (gc\_position)" en la configuración del módulo. Asegúrate de haber seleccionado un hook que realmente sea renderizado por tu tema en la página del producto. Algunos temas personalizados podrían no implementar todos los hooks estándar de PrestaShop.
    -   **R:** Borra la caché de PrestaShop (Parámetros Avanzados > Rendimiento > Borrar caché).
    -   **R:** Busca errores de JavaScript en la consola de desarrollador de tu navegador (F12). Los conflictos con otros módulos o scripts del tema a veces pueden impedir que los botones se carguen.
    -   **R:** Asegúrate de que el módulo esté habilitado en el Gestor de Módulos.
-   **P: Los clientes hacen clic en +1 pero no reciben un cupón.**

    -   **R:** Verifica que el ajuste "Código de Cupón (gc\_voucher)" tenga un porcentaje de descuento válido (por ejemplo, `10` para 10%). Si es `0` o está vacío, no se generará un cupón efectivo.
    -   **R:** Revisa el ajuste "Número de Me Gusta (gc\_nblikes)". Si está configurado con un valor mayor que 1, el cupón no se emitirá hasta que se cumpla ese umbral. Para cupones instantáneos, debe ser 1.
    -   **R:** Asegúrate de que no haya errores del lado del servidor que impidan la generación del cupón. Revisa los registros de errores de PrestaShop (Parámetros Avanzados > Registros).
-   **P: El botón se ve extraño o está desalineado en mi sitio móvil.**

    -   **R:** Esto suele ser un conflicto de CSS con tu tema. El módulo incluye su propio CSS, pero los estilos de tu tema podrían anularlo o entrar en conflicto con él. Es posible que necesites un desarrollador web para inspeccionar el CSS y realizar pequeños ajustes.
    -   **R:** Prueba diferentes opciones de "Estilo del Botón (gc\_button\_style)" para ver si un tamaño diferente se renderiza mejor.
-   **P: ¿Puedo personalizar el mensaje o la validez del cupón?**

    -   **R:** La configuración del módulo controla principalmente el porcentaje de descuento y las opciones de visualización. Para reglas de cupón avanzadas (por ejemplo, compra mínima, categorías específicas, período de validez), normalmente las gestionarías dentro de la sección nativa de PrestaShop "Reglas de Precios de Catálogo" o "Reglas de Carrito" (Descuentos), y el módulo generaría un código que se adhiere a esas reglas si corresponde, o podrías necesitar crear manualmente una regla específica que coincida con el cupón generado por el módulo. El módulo en sí genera un descuento porcentual básico.

## 4. Guía para Desarrolladores y Webmasters (Arquitectura Técnica y Mapa de Código)

Esta sección proporciona una inmersión técnica profunda en el módulo "Botón Google product plus + cupón" para desarrolladores y webmasters.

### 4.1 Visión General de la Arquitectura

El módulo sigue una arquitectura de módulo estándar de PrestaShop, aprovechando principalmente la clase `Module` y sus métodos `install()`, `uninstall()` y `getContent()`. Se integra con el front-office a través de varios hooks de visualización para inyectar el botón Google +1 y la lógica de cupón asociada. La generación y visualización del cupón se manejan dinámicamente utilizando JavaScript y plantillas Smarty. No hay clases `ObjectModel` personalizadas ni Controladores de Administración dedicados más allá de la configuración principal del módulo.

### 4.2 Controladores (`controllers/`)

-   **Controladores de Front-Office**: Ninguno. Toda la funcionalidad de front-office se maneja a través de hooks del módulo y renderizado directo de plantillas.
-   **Controladores de Administración (Back-Office)**: Ninguno. La configuración se realiza completamente dentro del método `getContent()` del módulo principal.

### 4.3 Clases y Modelos Principales (`classes/`)

-   No hay clases personalizadas ni definiciones de `ObjectModel` presentes en el directorio `classes/`. Toda la lógica principal reside dentro de `googlecoupon/googlecoupon.php`.

### 4.4 Activos JavaScript (`views/js/`)

-   `googlecoupon/lib/voucherengine/script.js`
    -   **Alcance:** Front-office.
    -   **Responsabilidad:** Este script es probablemente responsable de la lógica central de la generación y visualización del cupón. Escucharía el evento de clic del botón Google +1, activaría el proceso de generación del cupón (posiblemente a través de una llamada AJAX al archivo principal del módulo o una función JavaScript directa), y luego mostraría el código del cupón al usuario. También podría manejar la interacción con la API de Google+ (aunque las APIs de Google+ han sido en gran parte deprecadas o integradas en otros servicios).
-   `googlecoupon/trusted.js`
    -   **Alcance:** Front-office.
    -   **Responsabilidad:** El propósito de este script es menos claro solo por el nombre, pero podría estar relacionado con asegurar la integridad de la acción +1, el seguimiento o la integración con otros servicios de confianza. También podría ser un remanente de integraciones antiguas de la API de Google+.

### 4.5 Hojas de Estilo CSS (`views/css/`)

-   `googlecoupon/css.css`
    -   **Alcance:** Front-office.
    -   **Responsabilidad:** Proporciona el estilo principal para el botón Google +1, el área de visualización del cupón y cualquier ventana emergente o notificación asociada.
    -   **Selectores de clase CSS clave:** Los desarrolladores deben inspeccionar este archivo para identificar clases específicas (por ejemplo, `.googlecoupon-button-container`, `.googlecoupon-voucher-display`, `.googlecoupon-modal`) que pueden ser anuladas en el `custom.css` o `theme.css` de un tema personalizado para que coincidan con la marca de la tienda.
-   `googlecoupon/css/css.css`
    -   **Alcance:** Front-office.
    -   **Responsabilidad:** Esto parece ser una hoja de estilo duplicada o alternativa. Es importante verificar si ambas se cargan o si una es un respaldo. Probablemente contendría reglas de estilo similares a `googlecoupon/css.css`.

### 4.6 Estructura de Plantillas Smarty (`views/templates/`)

-   **Plantillas de Hook (`views/templates/hook/`)**: Ninguna listada explícitamente, pero `share.tpl` probablemente cumple este propósito.
-   **Plantillas de Administración (`views/templates/admin/`)**: Ninguna.
-   **Plantillas de Front-office (`views/templates/front/`)**: Ninguna listada explícitamente, pero `share.tpl` es la plantilla clave de front-office.
    -   `googlecoupon/share.tpl`
        -   **Alcance:** Front-office.
        -   **Propósito:** Esta plantilla es responsable de renderizar el botón Google +1 y el contenedor donde se mostrará la información del cupón. Se inyectará en los diversos hooks de front-office configurados en el módulo. Probablemente contiene marcadores de posición para el script de Google+ y el código de cupón generado dinámicamente.

### 4.7 Esquema de Base de Datos y Mapa de Hooks

-   **Tablas de Base de Datos**:

    -   El módulo no parece crear tablas SQL personalizadas.
    -   La configuración se almacena en la tabla `ps_configuration` utilizando claves como `GC_VOUCHER`, `GC_SHOW_PRICES`, `GC_SHOW_TOTAL`, `GC_SHOW_PRODUCTS`, `GC_SHOW_PRODUCT_URL`, `GC_LASTTAB`, `GC_POSITION`, `GC_NBLIKES`, `GC_BUTTON_STYLE`, `GCSHARE_MODE`.
-   **Tabla de Hooks Registrados**:

| Nombre del Hook | Momento de Ejecución | Propósito Técnico |
| --- | --- | --- |
| `displayproductActions` | En la página del producto, típicamente cerca del botón "Añadir al carrito". | Inyecta el botón Google +1 y la visualización del cupón en un área prominente. |
| `displayproductFooter` | En la página del producto, en la parte inferior del bloque de información del producto. | Inyecta el botón Google +1 y la visualización del cupón después de los detalles principales del producto. |
| `productFooter` | En la página del producto, similar a `displayproductFooter`, a menudo utilizado para contenido adicional. | Ubicación alternativa para el botón Google +1 y la visualización del cupón. |
| `extraLeft` | En la página del producto, en la columna izquierda (si está habilitada por el tema). | Coloca el contenido del módulo en la barra lateral izquierda. |
| `productActions` | En la página del producto, específicamente alrededor de los selectores de "Añadir al carrito" y cantidad. | Ubicación alternativa para el botón Google +1 y la visualización del cupón, a menudo muy prominente. |
| `displayextraleft` | En la página del producto, en la columna izquierda. | Similar a `extraLeft`, para inyectar contenido en la barra lateral izquierda. |
| `extraRight` | En la página del producto, en la columna derecha (si está habilitada por el tema). | Coloca el contenido del módulo en la barra lateral derecha. |
| `displayextraright` | En la página del producto, en la columna derecha. | Similar a `extraRight`, para inyectar contenido en la barra lateral derecha. |
| `displayHeader` | En la sección `<head>` de cada página. | Se utiliza para incluir los archivos CSS y JavaScript necesarios para el módulo. |
| `header` | En la sección `<head>` de cada página (versiones antiguas de PrestaShop). | Similar a `displayHeader`, para incluir activos. |

## 5. Soporte Oficial y Actualizaciones

Para actualizaciones oficiales, soporte técnico y para descargar las últimas versiones del módulo "Botón Google product plus + cupón", por favor, inicia sesión en tu cuenta de cliente en [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nuestro equipo de soporte está disponible para ayudarte con cualquier problema o pregunta que puedas tener.
