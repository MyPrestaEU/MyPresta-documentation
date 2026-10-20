---
title: "Actualización masiva gratuita de precios de productos - Manual de comerciante y guía de configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop 'Actualización masiva gratuita de precios de productos' de MyPresta.eu."
sidebar:
  label: "Actualización masiva gratuita de precios de productos - Manual de comerciante y guía de configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Free mass products prices update en MyPresta.eu](https://mypresta.eu/modules/administration-tools/free-mass-products-prices-update.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/back-office-tools/free-mass-products-prices-update/)
>
> ---


# Actualización masiva gratuita de precios de productos

## 1. Requisitos y compatibilidad

- **Versiones de PrestaShop compatibles**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilidad con PHP**: PHP 7.1 - 8.5
- **Requisitos de alojamiento**: Las extensiones PHP estándar (cURL, JSON, OpenSSL) suelen ser suficientes. No se requieren configuraciones especiales del servidor más allá de un entorno de alojamiento estándar de PrestaShop.

## 2. Recorrido completo por la configuración (Cada ajuste agrupado por pantalla)

### 2.1 Página de configuración del módulo (Back Office > Módulos > Configurar > Actualización masiva gratuita de precios de productos)

Esta es la pantalla de configuración principal y única para el módulo "Actualización masiva gratuita de precios de productos". Aquí, definirá cómo desea ajustar los precios de sus productos.

#### **Tipo de ajuste de precio**

- **Qué hace esta configuración:** Este ajuste crucial determina si desea aumentar o disminuir los precios de sus productos.
- **Efecto de cambiar esta configuración:**
  - *Cuando se establece en "Aumentar":* El módulo agregará el porcentaje especificado al precio actual de cada producto.
  - *Cuando se establece en "Disminuir":* El módulo restará el porcentaje especificado del precio actual de cada producto.
- **Valor recomendado:** Elija según su necesidad comercial inmediata (por ejemplo, "Aumentar" para un aumento general de precios, "Disminuir" para una oferta).
- **Escenario / ejemplo de comerciante:** Si sus costos de proveedor han aumentado, seleccionaría "Aumentar". Si está realizando una venta flash, seleccionaría "Disminuir".

#### **Valor porcentual**

- **Qué hace esta configuración:** Este campo le permite ingresar el porcentaje exacto en el que desea ajustar sus precios.
- **Efecto de cambiar esta configuración:**
  - *Cuando se establece en "10":* Si se selecciona "Aumentar", los precios subirán un 10%. Si se selecciona "Disminuir", los precios bajarán un 10%.
  - *Cuando se establece en "0":* No se producirá ningún cambio de precio.
- **Valor recomendado:** Ingrese el porcentaje preciso que necesita. Use números enteros o decimales (por ejemplo, "5" para 5%, "2.5" para 2.5%).
- **Escenario / ejemplo de comerciante:** Para ofrecer un descuento del 15% en toda la tienda, establecería "Tipo de ajuste de precio" en "Disminuir" y "Valor porcentual" en "15". Para aumentar los precios en un 7.5%, establecería "Tipo de ajuste de precio" en "Aumentar" y "Valor porcentual" en "7.5".

#### **Botón Aplicar cambios**

- **Qué hace esto:** Este botón inicia el proceso real de actualización de precios.
- **Efecto de hacer clic en este botón:** Una vez hecho clic, el módulo procesará todos los productos de su tienda de acuerdo con el "Tipo de ajuste de precio" y el "Valor porcentual" que haya establecido. **Esta acción es irreversible sin una copia de seguridad de la base de datos.**
- **Acción recomendada:** Siempre verifique dos veces su "Tipo de ajuste de precio" y "Valor porcentual" antes de hacer clic en este botón. Asegúrese de tener una copia de seguridad reciente de la base de datos.
- **Escenario / ejemplo de comerciante:** Después de configurar cuidadosamente "Disminuir" y "20" para una oferta de fin de semana, hace clic en "Aplicar cambios" para actualizar instantáneamente todos los precios de los productos en un -20%.

:::warning NOTA IMPORTANTE
El módulo "Actualización masiva gratuita de precios de productos" realiza una actualización directa de los precios de sus productos. **No hay un botón de "deshacer".** Antes de aplicar cualquier cambio, es **CRÍTICO** que cree una copia de seguridad completa de su base de datos de PrestaShop. Esto le permitirá restaurar sus precios a su estado anterior si comete un error o cambia de opinión.
:::

### 2.2 Tabla de referencia rápida de configuración

| Pantalla / Vista | Configuración / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| Configuración del módulo | Tipo de ajuste de precio | (Seleccionar Aumentar/Disminuir) | Determina si los precios subirán o bajarán. |
| Configuración del módulo | Valor porcentual | (Introducir el porcentaje deseado) | El porcentaje exacto para el ajuste de precios. |
| Configuración del módulo | Botón Aplicar cambios | (Hacer clic con precaución) | Ejecuta la actualización masiva de precios. **Irreversible sin copia de seguridad.** |

## 3. Solución de problemas del comerciante y preguntas frecuentes (FAQ)

**P1: He actualizado los precios, pero no se muestran en mi tienda. ¿Qué pasa?**
R1: Después de cualquier cambio significativo de datos en PrestaShop, especialmente relacionado con productos, es una buena práctica borrar la caché de su tienda.
\* Vaya a **Parámetros avanzados > Rendimiento** en su Back Office.
\* Haga clic en el botón "Borrar caché" en la esquina superior derecha.
\* Además, asegúrese de que la caché de su navegador esté borrada, o intente ver su tienda en una ventana de navegación de incógnito/privada.

**P2: Cometí un error y actualicé los precios incorrectamente. ¿Cómo puedo revertir?**
R2: Como se mencionó, este módulo no tiene un botón de "deshacer". Por eso una copia de seguridad de la base de datos es crucial.
\* Si hizo una copia de seguridad *antes* de aplicar los cambios, deberá restaurar su base de datos desde esa copia de seguridad. Esto generalmente requiere acceso a su panel de control de alojamiento (por ejemplo, cPanel, Plesk) o el uso de un módulo de copia de seguridad de PrestaShop.
\* Si *no* hizo una copia de seguridad, tendrá que volver a introducir manualmente los precios correctos para sus productos, o usar el módulo de nuevo con un cálculo inverso (por ejemplo, si disminuyó en un 20%, necesitaría aumentar en un 25% para volver al valor original, pero esto podría no ser perfectamente preciso debido al redondeo).

**P3: ¿Este módulo afecta precios específicos o combinaciones?**
R3: El módulo actualiza el *precio base* de sus productos. No gestiona directamente precios específicos (descuentos, descuentos por cantidad) o impactos de precios de combinaciones de productos. Si tiene precios específicos configurados, el cambio de precio base afectará el punto de partida de esos precios específicos.

**P4: ¿Es posible actualizar precios solo para categorías o fabricantes específicos?**
R4: No, esta versión gratuita del módulo realiza una actualización masiva en *todos* los productos de su tienda. No ofrece filtrado por categoría, fabricante u otros criterios. Para actualizaciones de precios más avanzadas y filtradas, normalmente necesitaría un módulo de importación/exportación o actualización masiva más sofisticado, a menudo de pago.

**P5: El módulo parece atascado o no responde cuando hago clic en "Aplicar cambios".**
R5: Para tiendas con un número muy grande de productos (miles), el proceso de actualización puede llevar algún tiempo.
\* Asegúrese de que el límite de tiempo de ejecución de PHP de su servidor sea suficiente. Podría ver un "Error interno del servidor 500" o un tiempo de espera si es demasiado bajo. Este es un problema de configuración del servidor, no un error del módulo.
\* Revise los registros de errores de PrestaShop (ubicados en `var/logs/` en PrestaShop 1.7/8/9) para ver si hay errores específicos.
\* Si el problema persiste, póngase en contacto con su proveedor de alojamiento o con un desarrollador web para que revise los registros del servidor y la configuración de PHP.

## 4. Guía para desarrolladores y webmasters (Arquitectura técnica y mapa de código)

### 4.1 Descripción general de la arquitectura

El módulo "Actualización masiva gratuita de precios de productos" es un módulo de PrestaShop sencillo diseñado principalmente para la administración del Back Office. Sigue una estructura básica de módulo de PrestaShop, aprovechando la clase `Module` y su método `getContent()` para la configuración. Interactúa directamente con la base de datos de PrestaShop para actualizar los precios de los productos sin controladores personalizados, modelos o interacciones complejas de JavaScript. La lógica del módulo está autocontenida dentro de su archivo PHP principal.

### 4.2 Controladores (`controllers/`)

Este módulo **no** utiliza ningún controlador de Front Office o Back Office Admin personalizado. Toda la funcionalidad se maneja directamente dentro del método `getContent()` de la clase principal del módulo.

### 4.3 Clases y modelos principales (`classes/`)

Este módulo **no** define ninguna clase personalizada ni extiende `ObjectModel`. Interactúa directamente con los métodos `Product` y `Product::updatePrice()` proporcionados por el núcleo de PrestaShop.

### 4.4 Activos de JavaScript (`views/js/`)

Este módulo **no** incluye ningún archivo JavaScript personalizado.

### 4.5 Hojas de estilo CSS (`views/css/`)

Este módulo **no** incluye ningún archivo CSS personalizado. El estilo de la página de configuración se maneja mediante el tema predeterminado del Back Office de PrestaShop.

### 4.6 Estructura de la plantilla Smarty (`views/templates/`)

El módulo utiliza dos plantillas Smarty simples:

- **`masspricefree/views/advert.tpl`**:
  - **Alcance:** Back-office (página de configuración del módulo).
  - **Propósito:** Probablemente se utiliza para mostrar un anuncio o mensaje promocional de MyPresta.eu dentro de la interfaz de configuración del módulo. Normalmente se renderiza en la parte superior o inferior de la salida de `getContent()`.
- **`masspricefree/views/script.tpl`**:
  - **Alcance:** Back-office (página de configuración del módulo).
  - **Propósito:** Esta plantilla podría contener JavaScript en línea o elementos HTML simples que forman parte del formulario de configuración del módulo, aunque la descripción del módulo sugiere un JS mínimo. Dada la simplicidad del módulo, es más probable que sea un marcador de posición o que contenga elementos de interfaz de usuario muy básicos.

### 4.7 Esquema de la base de datos y mapa de hooks

- **Tablas de la base de datos**:

  - Este módulo **no** crea ninguna tabla de base de datos personalizada.
  - Modifica directamente los datos en la tabla `ps_product` (específicamente la columna `price`) y potencialmente `ps_product_shop` (para contextos multitienda) llamando a los métodos principales de PrestaShop.
  - La configuración (Tipo de ajuste de precio, Valor porcentual) se almacena en la tabla `ps_configuration` utilizando claves de configuración estándar de PrestaShop (por ejemplo, `PS_MASS_PRICE_FREE_TYPE`, `PS_MASS_PRICE_FREE_VALUE`).
- **Tabla de Hooks registrados**:
  Este módulo **no** registra ningún hook específico para la visualización del front-office o acciones del back-office más allá de los estándares `displayBackOfficeHeader` (implícitamente para la configuración del módulo) y `actionModuleInstall`/`actionModuleUninstall`. Su función principal es una manipulación directa de la base de datos activada por el envío del formulario de administración.

| Nombre del Hook | Momento de ejecución | Propósito técnico |
| --- | --- | --- |
| `displayBackOfficeHeader` | Se renderiza en la sección `<head>` del Back Office. | Utilizado por `getContent()` para cargar potencialmente activos o mostrar avisos, aunque no se utiliza explícitamente para activos personalizados en este módulo. |
| `actionModuleInstall` | Se activa cuando se instala el módulo. | Se utiliza para establecer valores de configuración predeterminados en `ps_configuration`. |
| `actionModuleUninstall` | Se activa cuando se desinstala el módulo. | Se utiliza para limpiar los valores de configuración de `ps_configuration`. |

### 4.8 Archivo principal del módulo (`masspricefree/index.php`)

La lógica central reside en `masspricefree/index.php`.

- **Nombre de la clase:** `MassPriceFree`
- **Clase padre:** `Module`
- **Métodos clave:**
  - `__construct()`: Inicializa las propiedades del módulo (nombre, pestaña, versión, autor, need\_instance, bootstrap).
  - `install()`: Registra el módulo, establece los valores de configuración predeterminados (por ejemplo, `PS_MASS_PRICE_FREE_TYPE` a 'increase', `PS_MASS_PRICE_FREE_VALUE` a '0').
  - `uninstall()`: Elimina los valores de configuración.
  - `getContent()`: Este es el método principal para la funcionalidad del módulo.
    - Maneja el envío del formulario (`Tools::isSubmit('submitMassPriceFree')`).
    - Recupera `price_type` y `price_value` del formulario enviado.
    - Actualiza `ps_configuration` con la nueva configuración.
    - **Crucialmente, itera a través de todos los productos activos (`Product::getProducts(Context::getContext()->language->id, 0, 0, 'id_product', 'ASC', false, true)`) y actualiza sus precios basándose en el porcentaje y tipo configurados.** Utiliza `Product::updatePrice()` para esto.
    - Renderiza el formulario de configuración utilizando `displayForm()` e incluye las plantillas `advert.tpl` y `script.tpl`.
  - `displayForm()`: Genera el HTML para el formulario de configuración del módulo, incluyendo los botones de radio para aumentar/disminuir y el campo de entrada para el porcentaje.

## 5. Soporte oficial y actualizaciones

Para actualizaciones oficiales, correcciones de errores y soporte dedicado para el módulo "Actualización masiva gratuita de precios de productos", consulte su cuenta de cliente en [MyPresta.eu](https://mypresta.eu/). Nuestro equipo de soporte está disponible para ayudarle con cualquier problema o pregunta que pueda tener con respecto a la funcionalidad del módulo.
"""
