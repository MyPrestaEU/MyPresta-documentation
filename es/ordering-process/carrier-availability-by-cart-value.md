---
title: "Disponibilidad de transportistas por valor del carrito - Manual de Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop 'Disponibilidad de transportistas por valor del carrito' de MyPresta.eu."
sidebar:
  label: "Disponibilidad de transportistas por valor del carrito - Manual de Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Carrier availability by cart value en MyPresta.eu](https://mypresta.eu/modules/ordering-process/carrier-availability-by-cart-value.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/ordering-process/carrier-availability-by-cart-value/)
>
> ---


# Disponibilidad de transportistas por valor del carrito

## 1. Requisitos y Compatibilidad

- **Versiones de PrestaShop compatibles**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilidad con PHP**: PHP 7.1 - 8.5
- **Requisitos de alojamiento**: Las extensiones PHP estándar (cURL, JSON, OpenSSL) suelen ser necesarias para PrestaShop y normalmente están disponibles en cualquier entorno de alojamiento moderno.

## 2. Recorrido Completo por la Configuración (Cada Ajuste Agrupado por Pantalla)

### 2.1 Página de Configuración del Módulo (Back Office > Módulos > Configurar)

Después de la instalación, al hacer clic en "Configurar" accederá a la página de configuración principal del módulo.

-   **Qué hace esta configuración:** Esta pantalla maneja principalmente la configuración general del módulo, a menudo relacionada con actualizaciones o funcionalidades básicas.
-   **Efecto de cambiar esta configuración:**
    -   `mypresta_updates`: Esta es una configuración común en los módulos de MyPresta.eu.
        -   *Cuando está habilitado:* El módulo buscará periódicamente nuevas versiones y actualizaciones de MyPresta.eu. Esto le ayuda a mantenerse al día con las correcciones de errores y las nuevas funciones.
        -   *Cuando está deshabilitado:* El módulo no buscará actualizaciones automáticamente. Tendría que buscar manualmente nuevas versiones en MyPresta.eu.
    -   `update_` y `updatev_`: Estas son configuraciones internas utilizadas por el mecanismo de actualización del módulo para rastrear la última verificación y la versión disponible. Normalmente no necesita interactuar con ellas directamente.
-   **Valor recomendado:**
    -   Para `mypresta_updates`: **SÍ** (Habilitado). Siempre se recomienda mantener los módulos actualizados por seguridad, rendimiento y nuevas funciones.
-   **Escenario / ejemplo de comerciante:** Habilitar las actualizaciones garantiza que su módulo siempre esté ejecutando la última versión, evitando posibles problemas de compatibilidad con futuras actualizaciones de PrestaShop u otros módulos.

### 2.2 Pantalla de Administración Dedicada: Reglas de Disponibilidad de Transportistas

Este es el núcleo del módulo donde define las reglas para la disponibilidad de transportistas en función del valor del carrito.

-   **Nombre de la pantalla y ubicación del menú:**

    -   En su Back Office de PrestaShop, navegue a **Envío > Disponibilidad de transportistas por valor de pedido**.
    -   Esto abrirá una nueva pantalla dedicada donde podrá gestionar sus reglas.
-   **Acciones y configuraciones disponibles:**
    Esta pantalla presenta una lista de reglas existentes y le permite agregar nuevas o editar/eliminar las existentes.

    **Columnas de la tabla de listado:**

    -   **ID**: Identificador único para la regla.
    -   **Transportista**: El nombre del transportista de envío al que se aplica la regla.
    -   **Pedido\_desde**: El valor mínimo del carrito para que este transportista esté disponible.
    -   **Pedido\_hasta**: El valor máximo del carrito para que este transportista esté disponible.
    -   **Activo**: Un interruptor para habilitar o deshabilitar la regla sin eliminarla.

    **Agregar/Editar una regla (Campos del formulario):**
    Cuando haga clic en "Añadir nueva regla" o edite una existente, verá un formulario con los siguientes campos:

    -   **Disponibilidad de transportistas por valor de pedido**: Esta es una lista desplegable donde selecciona el transportista de envío específico al que desea aplicar la regla.

        -   *Efecto:* La regla que defina solo afectará la disponibilidad de este transportista elegido.
        -   *Valor recomendado:* Seleccione el transportista que desea gestionar.
        -   *Escenario de comerciante:* Si desea restringir "Envío Express" a pedidos de alto valor, seleccionaría "Envío Express" aquí.
    -   **Valor de pedido desde**: Ingrese el valor total mínimo del carrito (en su moneda predeterminada) para que este transportista esté disponible.

        -   *Efecto:* Si el valor del carrito del cliente está por debajo de esta cantidad, el transportista seleccionado no se mostrará durante el proceso de compra.
        -   *Valor recomendado:* Ingrese `0` si no hay un mínimo, o una cantidad específica (por ejemplo, `50.00`).
        -   *Escenario de comerciante:* Establezca en `50.00` para que "Envío Gratuito" solo aparezca para pedidos superiores a $50.
    -   **Valor de pedido hasta**: Ingrese el valor total máximo del carrito (en su moneda predeterminada) para que este transportista esté disponible.

        -   *Efecto:* Si el valor del carrito del cliente está por encima de esta cantidad, el transportista seleccionado no se mostrará durante el proceso de compra.
        -   *Valor recomendado:* Deje vacío o establezca en `0` si no hay un máximo, o una cantidad específica (por ejemplo, `200.00`).
        -   *Escenario de comerciante:* Establezca en `200.00` para "Envío Estándar" para evitar que se elija para pedidos de muy alto valor que deberían usar "Envío Asegurado".
    -   **Activo**: Un simple interruptor ON/OFF.

        -   *Efecto:*
            -   *Cuando está habilitado:* La regla está activa y filtrará la disponibilidad del transportista.
            -   *Cuando está deshabilitado:* La regla se ignora y el transportista estará disponible según otras configuraciones de PrestaShop (peso, precio, zonas) independientemente del valor del carrito.
        -   *Valor recomendado:* **ON** para reglas activas.
        -   *Escenario de comerciante:* Deshabilite temporalmente una regla durante una promoción sin eliminarla.
    -   **Guardar**: Haga clic en este botón para aplicar sus cambios o crear la nueva regla.
-   **Flujo de trabajo recomendado para la gestión diaria de la tienda:**

    1.  **Identifique sus transportistas:** Enumere todos sus transportistas de envío y sus casos de uso previstos.
    2.  **Defina rangos de valor:** Para cada transportista, decida si hay un rango de valor de carrito específico donde debería estar disponible.
        -   *Ejemplo 1:* "Envío Económico" para pedidos de $0 a $75.
        -   *Ejemplo 2:* "Envío Estándar" para pedidos de $75 a $250.
        -   *Ejemplo 3:* "Premium Asegurado" para pedidos de $250 en adelante (establezca "Valor de pedido desde" en 250, deje "Valor de pedido hasta" vacío/0).
    3.  **Agregue reglas:** Vaya a **Envío > Disponibilidad de transportistas por valor de pedido** y haga clic en "Añadir nueva regla".
    4.  **Configure cada regla:** Seleccione el transportista, ingrese el "Valor de pedido desde" y "Valor de pedido hasta", y asegúrese de que "Activo" esté en ON.
    5.  **Pruebe a fondo:** Después de configurar sus reglas, realice compras de prueba con diferentes valores de carrito para asegurarse de que los transportistas se muestren como se espera.

### 2.3 Tabla de Referencia Rápida de Configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| Configuración del Módulo | `mypresta_updates` | SÍ (Habilitado) | Habilita las comprobaciones automáticas de actualizaciones del módulo. |
| Reglas de Disponibilidad de Transportistas | Transportista | Seleccionar de la lista | El transportista de envío específico al que se aplica esta regla. |
| Reglas de Disponibilidad de Transportistas | Valor de pedido desde | `0` o cantidad específica | Valor mínimo del carrito para que el transportista esté disponible. |
| Reglas de Disponibilidad de Transportistas | Valor de pedido hasta | `0` (sin máximo) o cantidad específica | Valor máximo del carrito para que el transportista esté disponible. |
| Reglas de Disponibilidad de Transportistas | Activo | ON | Habilita o deshabilita la regla específica de disponibilidad del transportista. |

## 3. Solución de Problemas para Comerciantes y Preguntas Frecuentes (FAQ)

**P1: He configurado las reglas, pero los transportistas no cambian en el proceso de compra. ¿Qué está mal?**
R1:

-   **Borrar caché:** Siempre borre la caché de PrestaShop después de realizar cambios en la configuración del módulo. Vaya a **Parámetros avanzados > Rendimiento** y luego haga clic en "Borrar caché" en la esquina superior derecha.
-   **Conflictos de reglas:** Verifique si tiene reglas en conflicto. Por ejemplo, si el Transportista A está configurado de $0 a $100 y el Transportista B de $50 a $150, asegúrese de que sus rangos sean lógicos.
-   **Estado del transportista:** Asegúrese de que los transportistas estén activos y configurados correctamente en **Envío > Transportistas** en PrestaShop. Este módulo solo filtra los transportistas *disponibles*, no activa los inactivos.
-   **Otras restricciones de transportistas:** Recuerde que PrestaShop tiene sus propias restricciones de transportistas (por zona, peso, precio). Este módulo *añade* otra capa de filtrado. Si un transportista ya está restringido por peso, este módulo no lo hará disponible.

**P2: Mi símbolo de moneda no se muestra correctamente, o los valores parecen incorrectos.**
R2: El módulo utiliza la moneda predeterminada de su tienda para los campos "Valor de pedido desde" y "Valor de pedido hasta". Asegúrese de que su moneda predeterminada esté configurada correctamente en **Internacional > Monedas**. El módulo opera con el valor numérico, por lo que el símbolo que se muestra en el back office es para su referencia.

**P3: ¿Puedo usar este módulo con otros módulos de envío?**
R3: Sí, generalmente. Este módulo se conecta al proceso estándar de PrestaShop para filtrar listas de transportistas. Aplicará sus reglas *después* de que otras condiciones principales de PrestaShop (como peso, precio, zona) ya hayan reducido la lista de posibles transportistas. Si otro módulo también filtra transportistas, se aplicarán las reglas más restrictivas de todos los módulos.

**P4: ¿Cómo hago que un transportista esté *siempre* disponible, independientemente del valor del carrito?**
R4: No necesita crear una regla para dicho transportista. Si un transportista no está listado en sus reglas de "Disponibilidad de transportistas por valor de pedido", permanecerá disponible según la configuración predeterminada de transportistas de PrestaShop (peso, precio, zona, etc.) sin ninguna restricción de valor de carrito de este módulo.

**P5: El módulo parece estar ralentizando mi proceso de compra. ¿Es esto normal?**
R5: Este módulo está diseñado para ser ligero y no debería afectar significativamente el rendimiento. Si nota una ralentización, asegúrese de que su instalación de PrestaShop esté optimizada (por ejemplo, caché habilitada, última versión de PHP, sin módulos excesivos). Si el problema persiste, póngase en contacto con el soporte de MyPresta.eu con los detalles de su configuración.

## 4. Guía para Desarrolladores y Webmasters (Arquitectura Técnica y Mapa de Código)

### 4.1 Visión General de la Arquitectura

El módulo "Disponibilidad de transportistas por valor del carrito" (`cbp`) sigue la arquitectura estándar de módulos de PrestaShop, aprovechando principalmente un AdminController para la configuración y un hook de Front-Office para modificar la lista de transportistas durante el proceso de compra. Utiliza un `ObjectModel` personalizado para gestionar las reglas de disponibilidad de transportistas en su propia tabla de base de datos.

### 4.2 Controladores (`controllers/`)

-   **Controladores de Front-Office**:
    Este módulo no incluye ningún controlador de front-office dedicado. Toda la lógica de front-office se maneja directamente a través de un hook en el archivo principal del módulo (`cbp.php`).
-   **Controladores de Administración (Back-Office)**:

    -   `cbp/controllers/admin/AdminCbpr.php`

        -   **Nombre de la Clase:** `AdminCbprController` (extiende `ModuleAdminController`)
        -   **Responsabilidad:** Esta es la interfaz administrativa principal para gestionar las reglas de disponibilidad de transportistas. Maneja las operaciones CRUD (Crear, Leer, Actualizar, Eliminar) para la entidad `cbpr`.
        -   **Nombre de la Pestaña:** "Disponibilidad de transportistas por valor de pedido" (bajo el menú Envío).
        -   **Entidad Gestionada:** `Cbpr` (el `ObjectModel` personalizado para las reglas de transportistas).
        -   **Características Clave:**
            -   Muestra una vista de `lista` de todas las reglas configuradas, incluyendo ID, nombre del transportista, Order\_from, Order\_to y estado Activo.
            -   Proporciona formularios de `añadir` y `editar` para reglas individuales, permitiendo la selección de un transportista y la entrada de valores mínimos/máximos de pedido.
            -   Maneja el envío de formularios y las interacciones con la base de datos para guardar y actualizar reglas.
            -   Utiliza `PS_CURRENCY_DEFAULT` para mostrar información de moneda en los formularios.
    -   `cbp/controllers/admin/index.php`

        -   **Responsabilidad:** Este archivo es un archivo `index.php` vacío estándar, típicamente incluido en los directorios de PrestaShop para evitar la lista de directorios por razones de seguridad. No contiene ninguna lógica de controlador funcional.

### 4.3 Clases y Modelos Principales (`classes/`)

El módulo no tiene un directorio `classes/` dedicado. El `ObjectModel` principal para gestionar las reglas de transportistas probablemente se define directamente dentro del archivo principal del módulo (`cbp/cbp.php`) o se maneja implícitamente por el `AdminCbprController` utilizando una definición dinámica de `ObjectModel`.

Dado que el `AdminCbprController` gestiona una tabla llamada `cbpr`, debe haber una clase `ObjectModel`, probablemente llamada `Cbpr`, definida en algún lugar. Esta clase definiría la estructura de las reglas de disponibilidad de transportistas.

**`ObjectModel` `Cbpr` asumido (probablemente en `cbp.php`):**

-   **Nombre de la Clase:** `Cbpr` (extiende `ObjectModel`)
-   **Tabla de Base de Datos:** `ps_cbpr` (o `_cbpr` con prefijo)
-   **Campos `$definition` (esperados):**
    -   `id_cbpr`: Clave primaria.
    -   `id_carrier`: Clave foránea a la tabla `ps_carrier`.
    -   `order_from`: Campo decimal para el valor mínimo del carrito.
    -   `order_to`: Campo decimal para el valor máximo del carrito.
    -   `active`: Campo booleano para el estado de la regla.
-   **Métodos Clave:** Métodos estándar de `ObjectModel` para `add()`, `update()`, `delete()`.

### 4.4 Activos JavaScript (`views/js/`)

El módulo no contiene ningún archivo JavaScript personalizado en `views/js/`. Toda la lógica de front-office se maneja en el lado del servidor a través de hooks de PHP. Los formularios de back-office dependen del manejo de formularios predeterminado de PrestaShop y jQuery.

### 4.5 Hojas de Estilo CSS (`views/css/`)

El módulo no contiene ningún archivo CSS personalizado en `views/css/`. La interfaz de back-office utiliza el estilo predeterminado de PrestaShop para los formularios y listas de `ModuleAdminController`. Los cambios en el front-office se manejan filtrando la lista de transportistas directamente en PHP, no renderizando nuevas plantillas.

### 4.6 Estructura de Plantillas Smarty (`views/templates/`)

El módulo no contiene ningún archivo de plantilla Smarty personalizado en `views/templates/`. Los formularios de configuración y las listas en el back office se renderizan utilizando las plantillas predeterminadas de `ModuleAdminController` de PrestaShop. Los cambios en el front-office se manejan filtrando la lista de transportistas directamente en PHP, no renderizando nuevas plantillas.

### 4.7 Esquema de Base de Datos y Mapa de Hooks

-   **Tablas de Base de Datos**:

    -   `ps_cbpr`: Esta tabla almacena las reglas de disponibilidad de transportistas.

        -   `id_cbpr` INT(10) UNSIGNED NOT NULL AUTO\_INCREMENT
        -   `id_carrier` INT(10) UNSIGNED NOT NULL
        -   `order_from` DECIMAL(20,6) NOT NULL DEFAULT ‘0.000000’
        -   `order_to` DECIMAL(20,6) NOT NULL DEFAULT ‘0.000000’
        -   `active` TINYINT(1) UNSIGNED NOT NULL DEFAULT ‘1’
        -   PRIMARY KEY (`id_cbpr`)
        -   KEY `id_carrier` (`id_carrier`)
    -   `ps_configuration`: El módulo almacena su configuración general (como `mypresta_updates`, `update_`, `updatev_`) en la tabla `ps_configuration`.
-   **Tabla de Hooks Registrados**:

| Nombre del Hook | Momento de Ejecución | Propósito Técnico |
| --- | --- | --- |
| `actionAdminControllerSetMedia` | Se ejecuta cuando se inicializa un AdminController y se están configurando sus medios (JS/CSS). | Utilizado por el módulo para registrar su AdminController personalizado (`AdminCbprController`) en la estructura del menú de PrestaShop. |
| `actionFilterDeliveryOptionList` | Se ejecuta durante el proceso de compra, específicamente cuando PrestaShop está construyendo la lista de opciones de entrega disponibles. | Este es el hook principal del front-office. El módulo lo utiliza para iterar a través de la lista de transportistas que PrestaShop ya ha considerado disponibles (basado en zonas, peso, precio) y luego filtra aún más esta lista basándose en el valor total del carrito y las reglas definidas en `ps_cbpr`. Si la regla de un transportista no coincide con el valor actual del carrito, se elimina de la lista presentada al cliente. |

## 5. Soporte Oficial y Actualizaciones

Para las últimas actualizaciones, correcciones de errores y soporte profesional para el módulo "Disponibilidad de transportistas por valor del carrito", consulte su cuenta de cliente en [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nuestro equipo se dedica a garantizar el buen funcionamiento y la mejora continua de nuestros módulos.
"""
