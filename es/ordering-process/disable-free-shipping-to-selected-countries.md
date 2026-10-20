---
title: "Deshabilitar envío gratuito a países seleccionados - Manual de Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop 'Deshabilitar envío gratuito a países seleccionados' de MyPresta.eu."
sidebar:
  label: "Deshabilitar envío gratuito a países seleccionados - Manual de Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Disable free shipping to selected countries en MyPresta.eu](https://mypresta.eu/modules/ordering-process/disable-free-shipping-to-selected-countries.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/ordering-process/disable-free-shipping-to-selected-countries/)
>
> ---


# Deshabilitar envío gratuito a países seleccionados

## 1. Requisitos y compatibilidad

- **Versiones de PrestaShop compatibles**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilidad con PHP**: PHP 7.1 - 8.5
- **Requisitos de alojamiento**: Extensiones PHP estándar (cURL, JSON, OpenSSL).

## 2. Recorrido completo de la configuración (Cada ajuste agrupado por pantalla)

### 2.1 Página de configuración del módulo (Back Office > Módulos > Configurar)

Esta es la pantalla de configuración principal y única para el módulo "Deshabilitar envío gratuito a países seleccionados". La encontrará navegando a **Módulos > Gestor de módulos**, buscando "Deshabilitar envío gratuito a países seleccionados" y haciendo clic en "Configurar".

#### Excluir envío gratuito de países:

- **Qué hace esta configuración:** Esta es la configuración principal del módulo. Le permite seleccionar uno o más países donde el envío gratuito *no* debe ofrecerse, independientemente de otras reglas de envío gratuito que pueda tener (por ejemplo, envío gratuito a partir de un cierto monto de pedido).
- **Efecto de cambiar esta configuración:**
  - *Cuando se seleccionan países:* Si la dirección de entrega de un cliente está en cualquiera de los países seleccionados, la opción "Envío gratuito" se eliminará de la lista de transportistas disponibles durante el pago. Solo verán opciones de envío de pago.
  - *Cuando no se seleccionan países:* El módulo no tendrá ningún efecto y el envío gratuito se ofrecerá a todos los países de acuerdo con su configuración estándar de PrestaShop.
- **Valor recomendado:** Seleccione solo aquellos países donde ofrecer envío gratuito sea realmente poco rentable o problemático para su negocio.
- **Escenario/ejemplo de comerciante:** Realiza envíos internacionales, pero el envío a Australia y Nueva Zelanda es significativamente más caro debido a la distancia y las aduanas. Seleccionaría "Australia" y "Nueva Zelanda" de esta lista. Ahora, a los clientes de estos países siempre se les cobrará el envío, incluso si el valor de su pedido califica para envío gratuito en otras regiones como la UE o EE. UU.

#### Tabla de referencia rápida de configuración

| Pantalla / Vista | Configuración / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| Página de configuración del módulo | Excluir envío gratuito de países: | Ninguno seleccionado | Seleccione los países donde NO se debe ofrecer envío gratuito. Si la dirección de entrega de un cliente está en un país seleccionado, el envío gratuito no estará disponible para su pedido. |

## 3. Solución de problemas del comerciante y preguntas frecuentes (FAQ)

**P: He configurado el módulo, pero el envío gratuito sigue apareciendo para un país seleccionado. ¿Qué está mal?**
R:

1. **Borrar caché:** Siempre borre la caché de PrestaShop después de realizar cambios de configuración. Vaya a **Parámetros avanzados > Rendimiento** y haga clic en "Borrar caché" en la esquina superior derecha.
2. **Probar con un nuevo carrito:** Asegúrese de estar probando con un carrito nuevo y una dirección de entrega establecida en el país excluido. A veces, la caché del navegador o los datos de la sesión pueden interferir.
3. **Verificar la configuración del transportista:** Verifique que su transportista de envío gratuito (o el transportista que ofrece envío gratuito) esté configurado correctamente en **Envío > Transportistas**. Asegúrese de que esté activo y tenga "Envío gratuito" habilitado. Este módulo *deshabilita* la opción de envío gratuito, no crea nuevas reglas de envío.
4. **Orden del módulo:** En raras ocasiones, si tiene varios módulos relacionados con el envío, podría haber un conflicto. Intente deshabilitar temporalmente otros módulos de envío para aislar el problema.

**P: ¿Este módulo afecta otros costos de envío?**
R: No, este módulo *solo* afecta la disponibilidad de la opción "Envío gratuito". No modifica ni elimina ninguna opción de envío de pago ni sus costos. Si el envío gratuito está deshabilitado para un país, a los clientes simplemente se les presentarán las opciones de envío de pago estándar disponibles para su carrito y destino.

**P: ¿Puedo deshabilitar el envío gratuito para productos o categorías específicas en lugar de países?**
R: No, este módulo está diseñado específicamente para deshabilitar el envío gratuito según el *país de entrega*. No ofrece opciones para excluir el envío gratuito según el producto, la categoría o el grupo de clientes. Si necesita dicha funcionalidad, necesitaría un módulo de reglas de envío diferente y más avanzado.

**P: ¿Qué pasa si quiero ofrecer envío gratuito a un país para pedidos superiores a una cierta cantidad, pero deshabilitarlo para cantidades inferiores?**
R: Este módulo deshabilita *todo* el envío gratuito para los países seleccionados. Si desea envío gratuito condicional (por ejemplo, envío gratuito a partir de $X), debe configurarlo directamente en la configuración de sus transportistas de PrestaShop (Envío > Transportistas). Este módulo anularía esa configuración para los países excluidos, haciendo que el envío gratuito no esté disponible en *ninguna* cantidad para esos destinos específicos.

## 4. Guía para desarrolladores y webmasters (Arquitectura técnica y mapa de código)

Esta sección es estrictamente para desarrolladores, webmasters de tiendas y agencias técnicas que mantienen o extienden la tienda.

### 4.1 Resumen de la arquitectura

El módulo "Deshabilitar envío gratuito a países seleccionados" opera anulando las clases principales de PrestaShop relacionadas con el comportamiento del transportista y del carrito. Específicamente, modifica la lógica que determina si un transportista ofrece envío gratuito y si un carrito califica para él, basándose en el país de entrega del cliente. Esto se logra a través del sistema de anulación de PrestaShop, asegurando que la lógica del módulo se aplique cada vez que se realizan cálculos de envío.

### 4.2 Controladores (`controllers/`)

Este módulo no utiliza ningún controlador de administración de Front-Office o Back-Office personalizado. Su lógica se inyecta directamente en la funcionalidad principal de PrestaShop a través de anulaciones de clases.

### 4.3 Clases y modelos principales (`classes/`)

El módulo implementa su funcionalidad principalmente a través de anulaciones de clases, ubicadas en el directorio `override/classes/` dentro de la carpeta del módulo.

- **`exfsc/override/classes/Carrier.php`**

  - **Nombre de la clase y clase padre:** `Carrier` (anula la clase `Carrier` principal)
  - **Responsabilidad:** Esta anulación modifica el método `isFree()` de la clase `Carrier`. Cuando PrestaShop verifica si un transportista en particular ofrece envío gratuito, esta anulación intercepta la llamada. Verifica si el país de entrega del carrito actual se encuentra entre los configurados para excluir el envío gratuito. Si lo está, y el método `isFree()` original hubiera devuelto `true`, esta anulación lo obliga a devolver `false`, deshabilitando efectivamente el envío gratuito para ese transportista para el país excluido.
  - **Métodos clave:**
    - `isFree($cart)`: Modificado para verificar la configuración `exfsc_country` y devolver `false` si el país de entrega del carrito está excluido y el método original hubiera devuelto `true`.
- **`exfsc/override/classes/Cart.php`**

  - **Nombre de la clase y clase padre:** `Cart` (anula la clase `Cart` principal)
  - **Responsabilidad:** Esta anulación modifica el método `getDeliveryOptionList()`. Este método es responsable de generar la lista de opciones de entrega disponibles (incluidos los transportistas y sus servicios) durante el pago. La anulación garantiza que si un transportista está marcado como "envío gratuito" pero el país de entrega está excluido por el módulo, ese transportista se presente correctamente con sus opciones de envío *de pago*, o si solo ofrece envío gratuito, se excluya por completo.
  - **Métodos clave:**
    - `getDeliveryOptionList(Country $default_country = null, $product_list = null, $id_zone = null)`: Modificado para garantizar que los transportistas marcados como gratuitos se evalúen correctamente con la lista de exclusión de países del módulo.
- **`exfsc/override/classes/index.php`**

  - **Propósito:** Este es un archivo `index.php` vacío, típicamente incluido en directorios para evitar la lista de directorios cuando se accede directamente a través de un navegador web, mejorando la seguridad. No tiene ningún impacto funcional en la lógica del módulo.

### 4.4 Activos de JavaScript (`views/js/`)

El módulo no incluye ningún archivo JavaScript personalizado. Toda la funcionalidad se maneja en el lado del servidor.

### 4.5 Hojas de estilo CSS (`views/css/`)

El módulo no incluye ningún archivo CSS personalizado. Toda la funcionalidad se maneja en el lado del servidor.

### 4.6 Estructura de la plantilla Smarty (`views/templates/`)

El módulo no incluye ningún archivo de plantilla Smarty personalizado. Sus efectos se integran en las plantillas de pago existentes de PrestaShop modificando los datos subyacentes que se les pasan.

### 4.7 Esquema de la base de datos y mapa de hooks

- **Tablas de la base de datos**:

  - El módulo no crea ninguna tabla SQL personalizada.
  - La configuración se almacena en la tabla `ps_configuration`.
    - `exfsc_country`: Almacena una lista de valores `id_country` separados por comas para los países donde el envío gratuito está deshabilitado.
    - `mypresta_updates`, `update_`, `updatev_`: Claves de configuración internas utilizadas por los módulos de MyPresta.eu para las comprobaciones de actualización.
    - `exfsc_visibility_cat`, `exfsc_visibility_products`: Estas claves están presentes en el método `getContent()` pero no son utilizadas activamente por la lógica central del módulo como se describe en el conjunto de características. Podrían ser restos o marcadores de posibles características futuras.
- **Tabla de hooks registrados**:
  El módulo no registra explícitamente ningún hook de front-office. Su funcionalidad se implementa a través de anulaciones de clases, que son activadas automáticamente por los procesos centrales de PrestaShop cuando se calculan las opciones de envío.
  El método `install()` del módulo puede registrar hooks estándar de back-office para la gestión de módulos (por ejemplo, `displayBackOfficeHeader`), pero estos son para fines administrativos y no afectan el comportamiento del front-office.

## 5. Soporte oficial y actualizaciones

Para obtener las últimas actualizaciones, correcciones de errores y soporte profesional para el módulo "Deshabilitar envío gratuito a países seleccionados", consulte su cuenta de cliente en [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nuestro equipo se dedica a garantizar que su módulo funcione perfectamente con su tienda PrestaShop.
"""
