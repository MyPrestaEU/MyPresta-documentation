---
title: "Puntos de fidelidad - Manual del Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop 'Puntos de fidelidad' de MyPresta.eu."
sidebar:
  label: "Puntos de fidelidad - Manual del Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Loyalty points en MyPresta.eu](https://mypresta.eu/modules/advertising-and-marketing/loyalty-points.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/advertising-marketing/loyalty-points/)
>
> ---


# Puntos de fidelidad

## 1. Requisitos y compatibilidad

- **Versiones de PrestaShop compatibles**: PrestaShop 8.x, 9.x
- **Compatibilidad con PHP**: PHP 7.1 - 8.5
- **Requisitos de alojamiento**: Las extensiones PHP estándar (cURL, JSON, OpenSSL) suelen ser suficientes para este módulo.

## 2. Recorrido completo por la configuración (Cada ajuste agrupado por pantalla)

### 2.1 Página de configuración del módulo (Back Office > Módulos > Configurar)

Para acceder a la configuración del módulo, vaya a **Módulos > Gestor de módulos** en su back office de PrestaShop, busque "Puntos de fidelidad" y haga clic en el botón "Configurar".

Esta pantalla le permite definir las reglas principales de su programa de fidelización.

#### **Tasa de cambio de puntos de fidelidad**

- **Qué hace este ajuste:** Esta configuración crucial define cuántos puntos de fidelidad gana un cliente por una cantidad específica de dinero gastada en su tienda. Es la base de su programa de fidelización.
- **Efecto de cambiar este ajuste:**
  - *Si se establece en "1 punto por cada 10 € gastados":* Un cliente que gasta 50 € ganará 5 puntos.
  - *Si se establece en "1 punto por cada 5 € gastados":* Un cliente que gasta 50 € ganará 10 puntos.
  - Un valor más alto (por ejemplo, 10 €) significa que los clientes ganan puntos más lentamente, mientras que un valor más bajo (por ejemplo, 1 €) significa que ganan puntos más rápidamente.
- **Valor recomendado:** Esto depende de sus márgenes de beneficio y del incentivo deseado para el cliente. Un punto de partida común es "1 punto por cada 10 € gastados" o "1 punto por cada 5 € gastados".
- **Escenario / ejemplo de comerciante:** Si el valor promedio de su pedido es de 50 € y desea que los clientes se sientan recompensados rápidamente, "1 punto por cada 5 € gastados" podría ser mejor. Si sus márgenes son más ajustados, "1 punto por cada 10 € gastados" podría ser más sostenible.

#### **Valor de los puntos de fidelidad**

- **Qué hace este ajuste:** Esta configuración determina el valor monetario de cada punto de fidelidad cuando un cliente decide convertirlos en un vale de descuento.
- **Efecto de cambiar este ajuste:**
  - *Si se establece en "1 punto = 0,10 €":* Un cliente con 100 puntos puede obtener un vale de 10 €.
  - *Si se establece en "1 punto = 0,05 €":* Un cliente con 100 puntos puede obtener un vale de 5 €.
  - Un valor más alto hace que los puntos sean más atractivos y valiosos para el cliente, pero le cuesta más a su tienda en descuentos.
- **Valor recomendado:** Esto debe equilibrarse con la "Tasa de cambio de puntos de fidelidad" para garantizar que su programa sea atractivo para los clientes y financieramente viable para su negocio. Una proporción común es que 10 puntos (ganados al gastar 100 € si la tasa es de 1 punto por cada 10 €) valen 1 €.
- **Escenario / ejemplo de comerciante:** Si da 1 punto por cada 10 € gastados, y 1 punto vale 0,10 €, entonces un cliente que gasta 100 € obtiene 10 puntos, que pueden canjearse por un vale de 1 €. Esto significa que obtienen un 1% de descuento en sus compras. Podría aumentar esto al 2% o 3% para ser más competitivo.

#### **Puntos mínimos para convertir**

- **Qué hace este ajuste:** Esto establece el número mínimo de puntos de fidelidad que un cliente debe acumular antes de que se le permita convertirlos en un vale de descuento.
- **Efecto de cambiar este ajuste:**
  - *Si se establece en "50 puntos":* Los clientes no pueden canjear puntos hasta que tengan al menos 50.
  - *Si se establece en "10 puntos":* Los clientes pueden canjear puntos mucho antes.
  - Un mínimo más alto anima a los clientes a realizar más compras para alcanzar el umbral, lo que potencialmente aumenta su valor de vida útil. Un mínimo más bajo ofrece una gratificación más rápida.
- **Valor recomendado:** Establezca un valor que fomente las compras repetidas sin ser tan alto que los clientes sientan que es inalcanzable. 50-100 puntos es un buen rango inicial, dependiendo de su tasa de acumulación de puntos.
- **Escenario / ejemplo de comerciante:** Si se gana 1 punto por cada 10 €, y se necesitan 50 puntos, un cliente necesita gastar 500 € para obtener su primer vale. Esto asegura que sea un cliente comprometido antes de recibir un descuento significativo.

#### **Validez del vale (días)**

- **Qué hace este ajuste:** Esto define cuántos días será válido un vale de descuento generado a partir de puntos de fidelidad.
- **Efecto de cambiar este ajuste:**
  - *Si se establece en "30 días":* El vale caduca 30 días después de su generación.
  - *Si se establece en "365 días":* El vale es válido por un año completo.
  - Un período de validez más corto anima a los clientes a usar su vale antes, impulsando compras repetidas más rápidas. Un período más largo ofrece más flexibilidad pero podría retrasar las compras.
- **Valor recomendado:** De 30 a 90 días es un rango común. Esto crea una sensación de urgencia sin ser excesivamente restrictivo.
- **Escenario / ejemplo de comerciante:** Un período de validez de 60 días les da a los clientes tiempo suficiente para encontrar algo que quieran comprar sin dejar que el vale permanezca sin usar indefinidamente.

#### **Habilitar programa de fidelidad**

- **Qué hace este ajuste:** Este es un interruptor maestro para activar o desactivar todo el programa de puntos de fidelidad.
- **Efecto de cambiar este ajuste:**
  - *Cuando está habilitado (SÍ):* El programa de fidelidad está activo. Los clientes ganarán puntos, verán información de puntos en las páginas de productos y en su carrito, y podrán administrar puntos en su cuenta.
  - *Cuando está deshabilitado (NO):* El programa de fidelidad está inactivo. No se ganarán puntos, no se mostrará información de puntos y los clientes no podrán canjear puntos. Los puntos existentes se conservarán pero serán inaccesibles hasta que se vuelvan a habilitar.
- **Valor recomendado:** SÍ, una vez que haya configurado todos los demás ajustes.
- **Escenario / ejemplo de comerciante:** Podría deshabilitarlo temporalmente para mantenimiento o si está ejecutando una campaña promocional diferente que entra en conflicto con el programa de fidelización.

#### **Mostrar puntos de fidelidad en la página de producto**

- **Qué hace este ajuste:** Esto controla si la información sobre los puntos de fidelidad ganados por un producto se muestra en las páginas de productos individuales de su tienda.
- **Efecto de cambiar este ajuste:**
  - *Cuando está habilitado (SÍ):* Los clientes verán un texto como "Gane X puntos con esta compra" en cada página de producto.
  - *Cuando está deshabilitado (NO):* Esta información no aparecerá en las páginas de productos.
- **Valor recomendado:** SÍ. Mostrar esta información de manera prominente ayuda a los clientes a comprender la propuesta de valor de su programa de fidelización y fomenta las compras.
- **Escenario / ejemplo de comerciante:** Mantener esto habilitado asegura que los clientes siempre estén al tanto de las recompensas que pueden ganar, lo que puede ser un factor decisivo en su compra.

#### **Mostrar puntos de fidelidad en el carrito de compras**

- **Qué hace este ajuste:** Esto controla si el total de puntos de fidelidad a ganar por el pedido actual se muestra en el resumen del carrito de compras.
- **Efecto de cambiar este ajuste:**
  - *Cuando está habilitado (SÍ):* Los clientes verán un resumen de los puntos que ganarán por el contenido actual de su carrito.
  - *Cuando está deshabilitado (NO):* Esta información no aparecerá en el carrito de compras.
- **Valor recomendado:** SÍ. Esto sirve como un incentivo final antes de la compra, recordando a los clientes los beneficios futuros de su compra.
- **Escenario / ejemplo de comerciante:** Mostrar puntos en el carrito puede reducir el abandono al agregar otra capa de valor a la compra, especialmente si el cliente está indeciso.

#### **Descripción del programa de puntos de fidelidad**

- **Qué hace este ajuste:** Esto le permite proporcionar una descripción o explicación personalizada de su programa de fidelización. Este texto se mostrará típicamente en la sección "Mi cuenta" del cliente, donde administran sus puntos.
- **Efecto de cambiar este ajuste:**
  - *Cuando se rellena con texto:* Los clientes verán su mensaje personalizado explicando cómo funciona el programa, sus beneficios o cualquier regla específica.
  - *Cuando se deja vacío:* No se mostrará ninguna descripción personalizada, lo que podría dejar a los clientes con menos información.
- **Valor recomendado:** Proporcione una descripción clara, concisa y atractiva. Explique cómo se ganan los puntos, su valor y cómo canjearlos.
- **Escenario / ejemplo de comerciante:** "¡Gane 1 punto por cada 10 € que gaste! Acumule 50 puntos y obtenga un vale de 5 € para su próxima compra. ¡Es nuestra forma de agradecerle por ser un cliente leal!"

### 2.2 Tabla de referencia rápida de configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| Configuración del módulo | Tasa de cambio de puntos de fidelidad | 1 punto por cada 10 € gastados | Define cuántos puntos se ganan por unidad de moneda gastada. |
| Configuración del módulo | Valor de los puntos de fidelidad | 1 punto = 0,10 € | Define el valor monetario de cada punto cuando se convierte en un vale. |
| Configuración del módulo | Puntos mínimos para convertir | 50 puntos | Establece los puntos mínimos requeridos antes de que un cliente pueda canjearlos por un vale. |
| Configuración del módulo | Validez del vale (días) | 60 días | Cuánto tiempo es válido un vale generado. |
| Configuración del módulo | Habilitar programa de fidelidad | SÍ | Interruptor maestro para activar/desactivar todo el programa de fidelidad. |
| Configuración del módulo | Mostrar puntos de fidelidad en la página de producto | SÍ | Muestra información de acumulación de puntos en las páginas de productos individuales. |
| Configuración del módulo | Mostrar puntos de fidelidad en el carrito de compras | SÍ | Muestra el total de puntos a ganar en el resumen del carrito de compras. |
| Configuración del módulo | Descripción del programa de puntos de fidelidad | Texto personalizado | Proporciona una explicación detallada del programa a los clientes. |

## 3. Solución de problemas del comerciante y preguntas frecuentes (FAQ)

**P: Mis clientes no ven la información de los puntos de fidelidad en las páginas de productos o en el carrito. ¿Qué pasa?**
R:

1. **Verifique "Habilitar programa de fidelidad":** Asegúrese de que esta configuración esté establecida en SÍ en la configuración del módulo.
2. **Verifique la configuración de visualización:** Verifique que "Mostrar puntos de fidelidad en la página de producto" y "Mostrar puntos de fidelidad en el carrito de compras" estén ambos establecidos en SÍ.
3. **Borrar caché:** Vaya a **Parámetros avanzados > Rendimiento** en su back office de PrestaShop y haga clic en "Borrar caché" (o "Borrar caché de Smarty" en versiones anteriores). A veces, los cambios no aparecen hasta que se actualiza la caché.
4. **Compatibilidad con el tema:** Si bien el módulo está diseñado para ser compatible, los temas personalizados a veces pueden anular los hooks de visualización predeterminados. Si borrar la caché no funciona, póngase en contacto con el soporte de MyPresta.eu.

**P: Los clientes están ganando puntos, pero no pueden convertirlos en vales.**
R:

1. **Verifique "Puntos mínimos para convertir":** Asegúrese de que el cliente haya acumulado al menos el número de puntos especificado en esta configuración. Si el mínimo es 50 y solo tienen 45, no verán la opción de conversión.
2. **Proceso de generación de vales:** Guíe a sus clientes a su sección "Mi cuenta", luego a la sección "Mis puntos de fidelidad" (o similar), donde deberían encontrar una opción para convertir sus puntos en un vale.

**P: Un cliente generó un vale, pero no funciona o ha desaparecido.**
R:

1. **Verifique "Validez del vale (días)":** El vale podría haber caducado si el cliente esperó demasiado para usarlo.
2. **Código del vale:** Asegúrese de que el cliente esté introduciendo el código del vale correctamente durante el proceso de compra.
3. **Estado del vale:** En el back office de PrestaShop, vaya a **Catálogo > Descuentos > Reglas de carrito**. Busque el código del vale generado. Verifique sus fechas de validez, importe mínimo y si ya ha sido utilizado.

**P: ¿Puedo añadir o eliminar manualmente puntos de fidelidad para un cliente?**
R: La versión actual del módulo no proporciona una interfaz directa en el back office para ajustar manualmente los puntos de fidelidad del cliente. Los puntos se calculan automáticamente en función de los pedidos. Si necesita realizar ajustes manuales, es posible que deba considerar un desarrollo personalizado o ponerse en contacto con el soporte de MyPresta.eu para opciones avanzadas.

**P: La descripción del programa de fidelidad no se muestra correctamente en varios idiomas.**
R: Cuando configure la "Descripción del programa de puntos de fidelidad", asegúrese de utilizar el selector de idioma en la parte superior derecha del campo de texto para proporcionar traducciones para todos los idiomas habilitados en su tienda. Si solo introduce texto en un idioma, solo aparecerá en ese idioma.

## 4. Guía para desarrolladores y webmasters (Arquitectura técnica y mapa de código)

Esta sección es estrictamente para desarrolladores, webmasters de tiendas y agencias técnicas que mantienen o extienden la tienda.

### 4.1 Resumen de la arquitectura

El módulo `Loyalty points` (`myprestaloyalty`) sigue una arquitectura de módulo estándar de PrestaShop, aprovechando principalmente la clase `Module` para su funcionalidad y configuración principales. Se integra en el front office a través de varios hooks para mostrar información de fidelidad y proporciona una página de cuenta de cliente dedicada para la gestión de puntos. El módulo no introduce tablas de base de datos personalizadas ni clases `ObjectModel`, confiando en la `Configuration` de PrestaShop para la configuración y potencialmente extendiendo los datos de clientes o pedidos existentes a través de hooks.

### 4.2 Controladores (`controllers/`)

- **Controladores del Front-Office**:

  - `myprestaloyalty/controllers/front/default.php`
    - **Nombre de la clase y clase padre**: `MyPrestaLoyaltyDefaultModuleFrontController` que extiende `ModuleFrontController`.
    - **Responsabilidad**: Este controlador probablemente sirve como un punto de entrada genérico o de respaldo para acciones del front-office relacionadas con el módulo. Podría manejar solicitudes iniciales o redirecciones si no se encuentra un controlador más específico. Dado el controlador `index.php`, `default.php` podría ser menos crítico o servir a un propósito específico y menos común.
  - `myprestaloyalty/controllers/front/index.php`
    - **Nombre de la clase y clase padre**: `MyPrestaLoyaltyIndexModuleFrontController` que extiende `ModuleFrontController`.
    - **Responsabilidad**: Este es el controlador principal del front-office para el módulo. Es responsable de mostrar la información de los puntos de fidelidad del cliente y de manejar la lógica para convertir puntos en vales. Probablemente obtiene los puntos actuales del cliente, calcula los posibles valores de los vales y procesa la solicitud de generación de vales. Renderiza la plantilla `loyalty.tpl`.
- **Controladores de administración del Back-Office**: Ninguno identificado. Toda la configuración se maneja a través del método `getContent()` del módulo principal.

### 4.3 Clases y modelos principales (`classes/`)

No se identificaron clases o modelos personalizados (extensiones de `ObjectModel`) en el inventario de módulos proporcionado. El módulo probablemente gestiona la lógica de los puntos de fidelidad directamente dentro del archivo principal `myprestaloyalty.php` y a través de la `Configuration` de PrestaShop para la configuración.

### 4.4 Activos de JavaScript (`views/js/`)

- `myprestaloyalty/views/js/admin_manual_customer_search.js`
  - **Alcance**: Back-office.
  - **Descripción**: Este script sugiere la funcionalidad para buscar clientes manualmente dentro del panel de administración. Aunque no se enumeraron controladores de administración explícitamente, este archivo JS implica que podría haber una interfaz de administración (quizás integrada en una página existente de PrestaShop o un formulario personalizado dentro de `getContent()`) donde un administrador puede buscar clientes, posiblemente para ver o administrar sus puntos de fidelidad (aunque la modificación directa de puntos no está confirmada por la descripción del módulo). Probablemente utiliza AJAX para obtener datos de clientes.
- `myprestaloyalty/views/js/myprestaloyalty.js`
  - **Alcance**: Front-office.
  - **Descripción**: Este es el JavaScript principal del front-office para el módulo. Probablemente maneja interacciones dinámicas en la página de fidelidad del cliente (`loyalty.tpl`), como:
    - Mostrar los puntos actuales y los posibles valores de los vales.
    - Manejar el evento de clic para el botón "Convertir puntos en vale".
    - Realizar solicitudes AJAX al controlador frontal `index.php` para procesar la generación del vale.
    - Actualizar la interfaz de usuario para mostrar el código del vale recién generado o mensajes de éxito/error.

### 4.5 Hojas de estilo CSS (`views/css/`)

- `myprestaloyalty/views/css/myprestaloyalty.css`
  - **Alcance**: Front-office (y potencialmente algunos elementos del back-office si se utilizan estilos comunes).
  - **Descripción**: Esta hoja de estilo proporciona el estilo visual para los componentes del front-office del módulo. Esto incluye:
    - La visualización de puntos de fidelidad en las páginas de productos.
    - El resumen de puntos en el carrito de compras.
    - El diseño y estilo de la sección "Mis puntos de fidelidad" en la cuenta del cliente, incluyendo el saldo de puntos, el historial y el formulario de generación de vales.
    - Selectores de clase CSS clave que los desarrolladores pueden anular en su tema: Busque clases con el prefijo `myprestaloyalty-` o similar, como `.myprestaloyalty-product-points`, `.myprestaloyalty-cart-summary`, `.myprestaloyalty-account-section`, `.myprestaloyalty-voucher-form`, etc.

### 4.6 Estructura de plantillas Smarty (`views/templates/`)

- **Plantillas de administración (`views/templates/admin/`)**:

  - `myprestaloyalty/views/templates/admin/advert.tpl`
    - **Descripción**: Esta plantilla probablemente se utiliza para mostrar contenido promocional o anuncios de MyPresta.eu dentro de la página de configuración del módulo en el back office. Es una práctica común para los desarrolladores de módulos incluir tales elementos.
  - `myprestaloyalty/views/templates/admin/_configure/helpers/form/form.tpl`
    - **Descripción**: Esta plantilla es una plantilla auxiliar estándar de PrestaShop utilizada para renderizar el formulario de configuración del módulo. No es única de este módulo, pero se incluye para garantizar que la página de configuración (`getContent()`) se renderice correctamente, potencialmente con campos personalizados o estilos específicos.
- **Plantillas del front-office (`views/templates/front/`)**:

  - `myprestaloyalty/views/templates/front/loyalty.tpl`
    - **Descripción**: Esta es la plantilla principal para la página dedicada "Mis puntos de fidelidad" del cliente, renderizada por `MyPrestaLoyaltyIndexModuleFrontController`. Muestra el saldo actual de puntos del cliente, el historial de puntos ganados y gastados, y la interfaz para convertir puntos en vales de descuento.
- **Plantillas de hook (`views/templates/hook/`)**:

  - `myprestaloyalty/views/templates/hook/my-account.tpl`
    - **Hook**: `displayCustomerAccount` (o similar, por ejemplo, `displayMyAccountBlock`).
    - **Descripción**: Esta plantilla añade un enlace o un bloque a la página "Mi cuenta" del cliente, dirigiéndolos a la página dedicada de puntos de fidelidad del módulo (`loyalty.tpl`).
  - `myprestaloyalty/views/templates/hook/product.tpl`
    - **Hook**: `displayProductExtraContent`, `displayProductButtons` o `displayProductActions` (dependiendo de la versión y el tema de PrestaShop).
    - **Descripción**: Esta plantilla muestra la información sobre cuántos puntos de fidelidad ganará un cliente al comprar el producto específico en su página de producto.
  - `myprestaloyalty/views/templates/hook/shopping-cart.tpl`
    - **Hook**: `displayShoppingCartFooter`, `displayCartExtraProductActions` o `displayReassurance` (dependiendo de la versión y el tema de PrestaShop).
    - **Descripción**: Esta plantilla muestra un resumen del total de puntos de fidelidad que el cliente ganará por los artículos actualmente en su carrito de compras.

### 4.7 Esquema de la base de datos y mapa de Hooks

- **Tablas de la base de datos**: Este módulo no crea tablas SQL personalizadas. Todas las configuraciones del módulo se almacenan en la tabla `ps_configuration` de PrestaShop, típicamente con claves prefijadas por `MYPRESTALOYALTY_`.

  - Ejemplos de claves de configuración: `MYPRESTALOYALTY_EXCHANGE_RATE`, `MYPRESTALOYALTY_POINT_VALUE`, `MYPRESTALOYALTY_MIN_POINTS`, `MYPRESTALOYALTY_VOUCHER_VALIDITY`, `MYPRESTALOYALTY_ENABLED`, `MYPRESTALOYALTY_DISPLAY_PRODUCT`, `MYPRESTALOYALTY_DISPLAY_CART`, `MYPRESTALOYALTY_DESCRIPTION`.
- **Tabla de Hooks registrados**:

| Nombre del Hook | Momento de ejecución | Propósito técnico |
| --- | --- | --- |
| `displayHeader` | En la sección `<head>` de cada página. | Para incluir activos CSS y JS para el front-office. |
| `displayCustomerAccount` | En la página "Mi cuenta" del cliente. | Para añadir un enlace a la sección "Mis puntos de fidelidad". |
| `displayProductExtraContent` (o similar) | En la página del producto, cerca de los detalles/botones del producto. | Para mostrar los puntos ganados por el producto específico. |
| `displayShoppingCartFooter` (o similar) | En el resumen del carrito de compras. | Para mostrar el total de puntos ganados por el pedido actual. |
| `actionValidateOrder` | Después de que un pedido ha sido validado con éxito. | Para calcular y otorgar puntos de fidelidad al cliente en función del total del pedido. |
| `displayLeftColumn` / `displayRightColumn` / `displayFooter` (opcional) | En las respectivas áreas de columna/pie de página. | Potencialmente utilizado para mostrar un enlace rápido o un resumen del programa de fidelidad, si está configurado. |

## 5. Soporte oficial y actualizaciones

Para las últimas actualizaciones, correcciones de errores y soporte técnico dedicado para el módulo "Puntos de fidelidad", consulte su cuenta de cliente en [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nuestro equipo de soporte está disponible para ayudar a comerciantes y desarrolladores con cualquier problema o pregunta relacionada con la funcionalidad e integración del módulo.
"""
