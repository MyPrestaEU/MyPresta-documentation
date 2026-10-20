---
title: "Regla de carrito para el producto más caro - Manual de Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop 'Regla de carrito para el producto más caro' de MyPresta.eu."
sidebar:
  label: "Regla de carrito para el producto más caro"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Cart rule for the most expensive product en MyPresta.eu](https://mypresta.eu/modules/advertising-and-marketing/cart-rule-for-the-most-expensive-product.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/advertising-marketing/cart-rule-for-the-most-expensive-product/)
>
> ---


# Regla de carrito para el producto más caro

## 1. Requisitos y Compatibilidad

-   **Versiones de PrestaShop compatibles**: PrestaShop 1.7.x
-   **Compatibilidad con PHP**: PHP 7.1 - 8.5
-   **Requisitos de alojamiento**: Extensiones PHP estándar (cURL, JSON, OpenSSL).

## 2. Recorrido completo de la configuración (Cada ajuste agrupado por pantalla)

### 2.1 Página de configuración del módulo (Back Office > Módulos > Configurar)
Después de la instalación, haga clic en "Configurar" junto al módulo en el Gestor de módulos. Esto le llevará a la pantalla de configuración principal de "Regla de carrito para el producto más caro".

#### Ajustes y opciones:

-   **Actualizaciones en vivo de MyPresta.eu (mypresta_updates)**
    -   **Qué hace este ajuste:** Este ajuste controla si el módulo puede buscar actualizaciones directamente desde MyPresta.eu. Ayuda a asegurar que siempre esté ejecutando la última versión con correcciones de errores y nuevas funciones.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando está habilitado (SÍ):* El módulo se conectará periódicamente a MyPresta.eu para buscar nuevas versiones. Si hay una actualización disponible, es posible que vea una notificación en su back office de PrestaShop.
        -   *Cuando está deshabilitado (NO):* El módulo no buscará actualizaciones automáticamente. Deberá buscar y descargar actualizaciones manualmente desde su cuenta MyPresta.eu.
    -   **Valor recomendado:** SÍ
    -   **Escenario / ejemplo de comerciante:** Mantener esto habilitado asegura que reciba notificaciones oportunas para actualizaciones críticas, mejorando la seguridad y la compatibilidad sin esfuerzo manual.

-   **Productos excluidos (csc_excluded_products)**
    -   **Qué hace este ajuste:** Este campo le permite especificar productos que *nunca* deben considerarse para el descuento del "producto más caro", incluso si son de hecho el artículo de mayor precio en el carrito. Esto es útil para productos con márgenes muy bajos, promociones especiales o artículos que no desea descontar.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando se introducen IDs de producto:* El módulo ignorará estos productos específicos al determinar qué artículo es el "más caro" para la regla del carrito. Si uno de estos productos excluidos es el de mayor precio, el módulo buscará el siguiente producto *no excluido* más caro para aplicar el descuento.
        -   *Cuando se deja vacío:* Todos los productos en el carrito son elegibles para ser identificados como el "más caro" para el descuento.
    -   **Valor recomendado:** Dejar vacío a menos que tenga productos específicos que desee excluir.
    -   **Escenario / ejemplo de comerciante:** Usted vende un producto muy popular y de alto margen (ID 123) y algunos artículos de bajo margen (ID 456, ID 789). Desea que el descuento del "producto más caro" se aplique a sus artículos de alto margen, pero no a los de bajo margen. Introduciría `456,789` (IDs de producto separados por comas) en este campo.

#### 2.1.1 Página de edición de reglas de carrito (Back Office > Catálogo > Descuentos > Reglas de carrito > Añadir nueva / Editar)
Este módulo añade una nueva opción directamente a la página estándar de creación/edición de reglas de carrito de PrestaShop. Encontrará esta opción cuando esté creando o modificando una regla de carrito que utilice un **descuento porcentual**.

-   **Ubicación del menú:** Back Office > Catálogo > Descuentos > Reglas de carrito. Haga clic en "Añadir nueva regla de carrito" o edite una existente.
-   **Acción disponible:** En la pestaña "Acciones" de la configuración de la regla de carrito, después de seleccionar "Porcentaje" para la opción "Aplicar un descuento", aparecerá una nueva casilla de verificación.

    -   **Aplicar descuento solo al producto más caro**
        -   **Qué hace este ajuste:** Esta es la funcionalidad principal del módulo. Cuando se habilita para una regla de carrito específica, el descuento porcentual definido para esa regla solo se aplicará al producto individual más caro en el carrito del cliente.
        -   **Efecto de cambiar este ajuste:**
            -   *Cuando está habilitado (marcado):* El descuento porcentual de la regla de carrito se calculará basándose únicamente en el precio del producto de mayor precio en el carrito (excluyendo cualquier producto que haya excluido globalmente en la configuración principal del módulo).
            -   *Cuando está deshabilitado (desmarcado):* La regla de carrito se comportará como un descuento porcentual estándar de PrestaShop, aplicando el descuento al total del carrito o a los productos elegibles según otras configuraciones de reglas de carrito (por ejemplo, selección de productos, cantidad mínima).
        -   **Valor recomendado:** Habilite esto solo para reglas de carrito donde desee específicamente dirigirse al artículo más caro.
        -   **Escenario / ejemplo de comerciante:** Desea ejecutar una promoción de "20% de descuento en su artículo más grande". Crea una nueva regla de carrito, establece el descuento en 20% (porcentaje) y luego marca esta casilla. Cuando los clientes usen este vale, obtendrán un 20% de descuento en su artículo más caro, no un 20% de descuento en todo su pedido.

### 2.2 Tabla de referencia rápida de configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| :------------ | :--------------- | :-------------------- | :--------------- |
| Configuración del módulo | Actualizaciones en vivo de MyPresta.eu | SÍ | Habilita las comprobaciones automáticas de actualización para el módulo. |
| Configuración del módulo | Productos excluidos | Vacío | IDs de producto separados por comas para excluir del cálculo del "más caro". |
| Edición de regla de carrito (Pestaña Acciones) | Aplicar descuento solo al producto más caro | Desmarcado | Cuando está marcado, aplica el descuento porcentual solo al artículo de mayor precio en el carrito. |

## 3. Solución de problemas para comerciantes y preguntas frecuentes (FAQ)

**P: El descuento no se aplica al producto más caro, o no funciona en absoluto.**
R:
1.  **Verifique la configuración de la regla de carrito:** Vaya a **Catálogo > Descuentos > Reglas de carrito**, edite su regla y asegúrese de que en la pestaña "Acciones", "Aplicar un descuento" esté configurado en "Porcentaje" y la casilla de verificación "Aplicar descuento solo al producto más caro" esté **marcada**.
2.  **Verifique la elegibilidad del producto:** Verifique la configuración principal del módulo (**Módulos > Gestor de módulos > Configurar** para "Regla de carrito para el producto más caro"). Asegúrese de que el producto al que espera que se aplique el descuento no esté listado en el campo "Productos excluidos".
3.  **Borrar caché:** A veces, la caché de PrestaShop puede impedir que los cambios surtan efecto inmediatamente. Vaya a **Parámetros avanzados > Rendimiento** y haga clic en "Borrar caché" en la esquina superior derecha.
4.  **Conflictos de módulos:** Si tiene otros módulos que modifican en gran medida los cálculos del carrito o los descuentos, podría haber un conflicto. Intente deshabilitar temporalmente otros módulos relacionados con descuentos para ver si el problema se resuelve.

**P: ¿Puedo aplicar este descuento solo a una categoría específica de productos?**
R: Sí, puede combinar la funcionalidad de este módulo con las restricciones estándar de reglas de carrito de PrestaShop. En la pestaña "Condiciones" de su regla de carrito, puede añadir condiciones como "Selección de producto" para especificar que el descuento solo se aplica si un producto de una determinada categoría está en el carrito. Sin embargo, recuerde que *si* dicho producto está presente, el módulo seguirá eligiendo el producto *generalmente* más caro del carrito (a menos que ese producto esté excluido) y le aplicará el descuento, no necesariamente el producto más caro *de esa categoría específica*.

**P: ¿Este módulo funciona con descuentos de cantidad fija?**
R: No, este módulo está diseñado específicamente para funcionar **solo con descuentos porcentuales**. La opción "Aplicar descuento solo al producto más caro" solo aparecerá y funcionará cuando seleccione "Porcentaje" como tipo de descuento en la pestaña "Acciones" de la regla de carrito.

**P: Mi tema personalizado no muestra el descuento correctamente.**
R: El módulo modifica principalmente la lógica de cálculo del descuento, no la visualización en el front-office. Las plantillas predeterminadas de PrestaShop deberían mostrar el descuento correctamente. Si su tema personalizado ha modificado en gran medida el resumen del carrito o del pago, podría requerir pequeños ajustes para reflejar correctamente cómo se aplican los descuentos. En la mayoría de los casos, borrar la caché de Smarty (**Parámetros avanzados > Rendimiento > Borrar caché**) debería resolver los problemas de visualización. Si no, consulte a su desarrollador de temas.

## 4. Guía para desarrolladores y webmasters (Arquitectura técnica y mapa de código)

### 4.1 Visión general de la arquitectura
El módulo "Regla de carrito para el producto más caro" (`crexpensive`) extiende principalmente la clase central `CartRule` de PrestaShop a través de una anulación (override). Esto le permite inyectar lógica personalizada en el proceso de cálculo de descuentos sin modificar directamente los archivos centrales. El módulo también proporciona una interfaz de configuración mínima en el Back Office y registra un hook para inyectar el JavaScript necesario para los formularios de administración.

### 4.2 Controladores (`controllers/`)
Este módulo no introduce ningún controlador personalizado de front-office o back-office. Su funcionalidad se integra directamente en los procesos existentes de PrestaShop a través de anulaciones y hooks.

### 4.3 Clases y modelos centrales (`classes/`)

-   **`crexpensive/override/classes/CartRule.php`**
    *   **Nombre de la clase:** `CartRule` (anula la clase central `CartRule`)
    *   **Clase padre:** `CartRuleCore`
    *   **Responsabilidad:** Esta anulación es el corazón de la funcionalidad del módulo. Modifica el comportamiento de cómo se aplican las reglas de carrito, dirigiéndose específicamente al cálculo de `reduction_percent`.
    *   **Métodos y lógica clave:**
        *   La anulación probablemente intercepta o modifica métodos relacionados con el cálculo de `reduction_percent` dentro de la clase `CartRule`. Contendrá lógica para:
            1.  Verificar si la regla de carrito actual tiene la bandera `apply_to_most_expensive_product` habilitada (un campo personalizado añadido por el módulo).
            2.  Si está habilitada, iterar a través de los productos en el carrito para identificar el más caro, teniendo en cuenta cualquier producto globalmente excluido configurado en el módulo.
            3.  Ajustar la aplicación de `reduction_percent` para que solo afecte al producto más caro identificado, asegurando que el descuento se calcule contra su precio en lugar de contra todo el carrito u otros productos.
        *   También añade un nuevo campo a la definición de `CartRule` (`$definition`) para almacenar la bandera `apply_to_most_expensive_product` en la tabla de la base de datos `ps_cart_rule`.

### 4.4 Activos JavaScript (`views/js/`)

-   **`crexpensive/views/js/crexpensive.js`**
    *   **Alcance:** Back-office (específicamente la página de edición de reglas de carrito).
    *   **Responsabilidad:** Este script es responsable de mostrar/ocultar dinámicamente la casilla de verificación "Aplicar descuento solo al producto más caro" en la página de edición de reglas de carrito.
    *   **Lógica clave:**
        *   Probablemente escucha los cambios en el menú desplegable/botones de radio "Aplicar un descuento" (específicamente cuando se selecciona "Porcentaje").
        *   Cuando se elige "Porcentaje", hace visible la casilla de verificación personalizada.
        *   Cuando se eligen otros tipos de descuento (por ejemplo, "Cantidad", "Envío gratuito"), oculta la casilla de verificación, ya que el módulo solo se aplica a descuentos porcentuales.
        *   Asegura que el estado de la casilla de verificación se cargue correctamente al editar una regla de carrito existente.

### 4.5 Hojas de estilo CSS (`views/css/`)
Este módulo no incluye ningún archivo CSS personalizado. Se basa en el estilo predeterminado de PrestaShop para sus elementos de configuración y la casilla de verificación inyectada en la página de reglas de carrito.

### 4.6 Estructura de la plantilla Smarty (`views/templates/`)
Este módulo no incluye ningún archivo de plantilla Smarty personalizado. El formulario de configuración se renderiza a través de `getContent()` en el archivo principal del módulo, y la casilla de verificación personalizada se inyecta en la página de edición de reglas de carrito existente a través de JavaScript.

### 4.7 Esquema de la base de datos y mapa de Hooks

-   **Tablas de la base de datos**:
    *   El módulo modifica la tabla `ps_cart_rule` añadiendo una nueva columna, probablemente llamada `apply_to_most_expensive_product` (o similar), que es un campo tinyint (booleano) para almacenar el estado de la casilla de verificación personalizada para cada regla de carrito.
    *   Los valores de configuración (`mypresta_updates`, `csc_excluded_products`) se almacenan en la tabla `ps_configuration`.

-   **Tabla de Hooks registrados**:

| Nombre del Hook | Momento de ejecución | Propósito técnico |
| :-------- | :--------------- | :---------------- |
| `actionAdminControllerSetMedia` | Se ejecuta cuando un controlador de administración está configurando sus activos multimedia (JS/CSS). | Este hook se utiliza para cargar `crexpensive.js` en la página de edición de reglas de carrito en el Back Office, habilitando la visualización dinámica de la casilla de verificación "Aplicar descuento solo al producto más caro". |

## 5. Soporte oficial y actualizaciones
Para actualizaciones oficiales, soporte técnico y para acceder a las últimas versiones del módulo "Regla de carrito para el producto más caro", visite su cuenta de cliente en [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nuestro equipo de soporte está disponible para ayudarle con cualquier problema o pregunta que pueda tener.
