---
title: "Métodos de envío (transportistas) del producto más caro - Manual del Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop 'Métodos de envío (transportistas) del producto más caro' de MyPresta.eu."
sidebar:
  label: "Métodos de envío (transportistas) del producto más caro - Manual del Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Shipping methods (carriers) from the most expensive product en MyPresta.eu](https://mypresta.eu/modules/ordering-process/shipping-methods-carriers-from-the-most-expensive-product.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/ordering-process/shipping-methods-carriers-from-the-most-expensive-product/)
>
> ---


# Métodos de envío (transportistas) del producto más caro

## 1. Requisitos y compatibilidad

- **Versiones de PrestaShop compatibles**: PrestaShop 1.6.x, 1.7.x, 8.x
- **Compatibilidad con PHP**: PHP 5.6 - 8.5
- **Requisitos de alojamiento**: Extensiones PHP estándar (cURL, JSON, OpenSSL).

## 2. Recorrido completo por la configuración (Cada ajuste agrupado por pantalla)

### 2.1 Página de configuración del módulo (Back Office > Módulos > Configurar)

Después de la instalación, haga clic en "Configurar" junto al nombre del módulo para acceder a sus ajustes.

#### **Activar / Desactivar Módulo**

- **Qué hace este ajuste:** Este es el interruptor principal para activar o desactivar la funcionalidad principal del módulo.
- **Efecto de cambiar este ajuste:**
  - *Cuando está activado:* El módulo modificará la lógica de selección de transportistas predeterminada de PrestaShop, asegurando que solo se muestren los transportistas asociados con el producto más caro del carrito durante el proceso de pago.
  - *Cuando está desactivado:* PrestaShop volverá a su comportamiento predeterminado, donde los transportistas solo se muestran si pueden enviar *todos* los productos del carrito.
- **Valor recomendado:** "Activado" si desea utilizar la funcionalidad del módulo.
- **Escenario / ejemplo del comerciante:** Si está probando el módulo o desea revertir temporalmente al comportamiento predeterminado de PrestaShop sin desinstalar, puede desactivarlo aquí.

#### **¿Cómo obtener transportistas?**

- **Qué hace este ajuste:** Este ajuste crucial define *cómo* el módulo identifica el "producto más caro" y, posteriormente, determina los transportistas disponibles. Ofrece dos métodos distintos.
- **Efecto de cambiar este ajuste:**
  - *Cuando se establece en "Del producto más caro (por precio)":* El módulo calculará el precio total de cada producto único en el carrito (cantidad * precio unitario) e identificará el producto con el precio total más alto. Los transportistas asociados con *ese producto específico* se utilizarán luego para filtrar las opciones de envío disponibles.
  - *Cuando se establece en "Del producto más caro (por precio) - ENVÍO GRATIS":* Esta opción funciona de manera similar a la primera, pero también considera si el producto más caro califica para envío gratis. Si el producto más caro tiene envío gratis habilitado, entonces las opciones de envío gratis se priorizarán o se harán disponibles de acuerdo con la configuración de su transportista.
  - *Cuando se establece en "Del producto más caro (por precio) - COSTE":* Esta opción también identifica el producto más caro por precio, pero se enfoca específicamente en el *costo* asociado con el envío de ese producto. Asegura que los costos de envío y las opciones presentadas estén directamente vinculados a la configuración de envío del artículo más caro.
- **Valor recomendado:**
  - "Del producto más caro (por precio)" es la opción más común y recomendada para uso general, ya que implementa directamente la promesa central del módulo.
  - Elija "Del producto más caro (por precio) - ENVÍO GRATIS" si ofrece con frecuencia envío gratis en artículos de alto valor y desea que esto sea una consideración principal en la selección del transportista.
  - Elija "Del producto más caro (por precio) - COSTE" si tiene reglas de costo de envío complejas vinculadas a productos específicos de alto valor y desea que esas reglas dicten los transportistas disponibles.
- **Escenario / ejemplo del comerciante:**
  - Usted vende un televisor de $1000 y un control remoto de $10. Si el televisor está configurado con transportistas específicos (por ejemplo, flete asegurado) y el control remoto con servicio postal estándar, elegir "Del producto más caro (por precio)" asegurará que se muestren los transportistas del televisor.
  - Si su televisor de $1000 viene con envío gratis, seleccionar "Del producto más caro (por precio) - ENVÍO GRATIS" aseguraría que se presenten las opciones de envío gratis si están disponibles para el televisor.

#### **Tabla de referencia rápida de configuración**

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| Página de configuración del módulo | Activar / Desactivar Módulo | Activado | Activa/desactiva la lógica del módulo para la selección de transportistas basada en el producto más caro. |
| Página de configuración del módulo | ¿Cómo obtener transportistas? | Del producto más caro (por precio) | Define el método para identificar el "producto más caro" y sus transportistas asociados. Opciones: "por precio", "por precio - ENVÍO GRATIS", "por precio - COSTE". |

## 3. Solución de problemas del comerciante y preguntas frecuentes (FAQ)

**P: He habilitado el módulo, pero sigo viendo las opciones de transportista antiguas o ningún transportista.**
R:

1. **Borrar caché:** Siempre borre la caché de su PrestaShop después de realizar cambios en la configuración del módulo. Vaya a **Parámetros avanzados > Rendimiento** y haga clic en "Borrar caché" en la esquina superior derecha.
2. **Verificar asociaciones de transportistas de productos:** Asegúrese de que sus productos, especialmente los más caros, estén correctamente asociados con los transportistas deseados en la configuración de sus productos (**Catálogo > Productos > Editar producto > pestaña Envío**).
3. **Verificar que el módulo esté habilitado:** Vuelva a verificar que la configuración "Activar / Desactivar Módulo" esté establecida en "Activado" en la configuración del módulo.
4. **Compatibilidad del tema:** Aunque es raro para este tipo de módulo, un tema altamente personalizado podría interferir. Cambie temporalmente al tema predeterminado de PrestaShop para descartar esto.

**P: ¿Cómo maneja el módulo dos productos con exactamente el mismo precio más alto?**
R: En los casos en que dos o más productos comparten exactamente el precio más alto, el módulo generalmente seleccionará uno de ellos basándose en el orden interno del ID de producto de PrestaShop o el orden en que se agregaron al carrito. Luego utilizará los transportistas asociados con ese producto seleccionado. Para mayor consistencia, es mejor asegurarse de que sus configuraciones de transportistas sean lo suficientemente robustas como para cubrir artículos de alto valor similares.

**P: ¿Este módulo afecta los costos de envío o solo la disponibilidad del transportista?**
R: Este módulo afecta principalmente la *disponibilidad del transportista*. Determina *qué* transportistas se muestran. Los costos de envío reales para el transportista elegido seguirán siendo calculados por los mecanismos estándar de PrestaShop (basados en peso, precio, zona, etc.) para el *carrito completo*, pero solo para los transportistas que estén disponibles según la lógica de este módulo.

**P: ¿Qué sucede si el producto más caro no tiene transportistas asociados?**
R: Si el producto más caro del carrito no tiene transportistas asociados explícitamente en la configuración de su producto, entonces no se mostrará ningún transportista durante el proceso de pago, lo que podría llevar a un mensaje de "no hay método de envío disponible". Siempre asegúrese de que sus productos de alto valor tengan asignados los transportistas adecuados.

## 4. Guía para desarrolladores y webmasters (Arquitectura técnica y mapa de código)

Esta sección es estrictamente para desarrolladores, webmasters de tiendas y agencias técnicas que mantienen o extienden la tienda.

### 4.1 Resumen de la arquitectura

El módulo "Métodos de envío (transportistas) del producto más caro" logra su funcionalidad sobrescribiendo una clase central de PrestaShop, `Cart`. Este es un método común y potente en PrestaShop para alterar comportamientos fundamentales sin modificar directamente los archivos centrales. Al sobrescribir `Cart::getAvailableCarriers()`, el módulo inyecta su lógica personalizada para filtrar los transportistas basándose en el producto más caro, en lugar de la regla predeterminada de "todos los productos deben ser compatibles".

### 4.2 Controladores (`controllers/`)

- **Controladores de Front-Office**: Ninguno. El módulo opera sobrescribiendo una clase central, no introduciendo nuevas rutas o páginas de front-office.
- **Controladores de Back-Office Admin**: Ninguno. La configuración del módulo se maneja directamente dentro del método `getContent()` de la clase principal del módulo.

### 4.3 Clases y modelos principales (`classes/`)

La lógica central del módulo reside en una sobrescritura de la clase `Cart`.

- **`cfep/override/classes/Cart.php`**

  - **Nombre de la clase**: `Cart` (sobrescribe `PrestaShop\Classes\Cart\Cart` o `CartCore` dependiendo de la versión y el contexto de PrestaShop).
  - **Clase padre**: `CartCore`
  - **Responsabilidad**: Este archivo contiene el método `getAvailableCarriers()` sobrescrito. Este método es crucial para determinar qué transportistas de envío se presentan al cliente durante el proceso de pago. La sobrescritura introduce la lógica para:
    1. Identificar el producto más caro en el carrito actual basándose en la configuración del módulo (`CFEP`, `CFEP_FREE`, `CFEP_COST`).
    2. Recuperar los transportistas específicamente asociados con este producto más caro.
    3. Filtrar la lista de todos los transportistas disponibles para incluir solo aquellos compatibles con el producto más caro.
    4. Devolver esta lista filtrada de transportistas.
  - **Métodos públicos clave**:
    - `getAvailableCarriers(bool $return_full_list = false, int $id_zone = null, bool $use_cache = true)`: Este es el método sobrescrito. Extiende el `CartCore::getAvailableCarriers` original para implementar la lógica de filtrado de transportistas personalizada. Primero llama al método padre para obtener todos los transportistas potencialmente disponibles, luego aplica su propio filtrado basado en el producto más caro.
- **`cfep/override/classes/index.php`**

  - **Responsabilidad**: Este es un archivo `index.php` vacío estándar, típicamente colocado en directorios para evitar la lista de directorios cuando se accede directamente a través de un navegador web. No tiene ningún impacto funcional en la lógica del módulo.

### 4.4 Activos de JavaScript (`views/js/`)

- Ninguno. El módulo no añade ningún JavaScript personalizado al front o back office.

### 4.5 Hojas de estilo CSS (`views/css/`)

- Ninguno. El módulo no añade ningún CSS personalizado al front o back office.

### 4.6 Estructura de plantillas Smarty (`views/templates/`)

- Ninguno. El módulo no utiliza ninguna plantilla Smarty personalizada. Su interfaz de configuración se genera dinámicamente por `getContent()` en el archivo principal del módulo.

### 4.7 Esquema de la base de datos y mapa de hooks

- **Tablas de la base de datos**:
  El módulo no crea ninguna tabla de base de datos personalizada. Almacena sus configuraciones en la tabla estándar `ps_configuration`.

  - Entradas de `ps_configuration`:
    - `CFEP`: Almacena el método seleccionado para obtener transportistas (por ejemplo, 'price', 'free', 'cost').
    - `mypresta_updates`: Utilizado para comprobaciones internas de actualización de MyPresta.eu.
    - `update_`: Utilizado para comprobaciones internas de actualización de MyPresta.eu.
    - `updatev_`: Utilizado para comprobaciones internas de actualización de MyPresta.eu.
- **Tabla de Hooks registrados**:
  El módulo no registra explícitamente ningún hook en la tabla `ps_hook_module`. Su funcionalidad se implementa a través de una sobrescritura de clase, que es una forma más directa de alterar el comportamiento central de PrestaShop sin depender de puntos de ejecución de hooks específicos.

## 5. Soporte oficial y actualizaciones

Para las últimas actualizaciones, correcciones de errores y soporte profesional para el módulo "Métodos de envío (transportistas) del producto más caro", consulte su cuenta de cliente en [MyPresta.eu](https://mypresta.eu/). Nuestro equipo de soporte está disponible para ayudar con cualquier problema o pregunta que pueda tener con respecto a la funcionalidad y compatibilidad del módulo.
