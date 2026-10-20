---
title: "Cambio de número de nota de crédito - Manual de Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop 'Cambio de número de nota de crédito' de MyPresta.eu."
sidebar:
  label: "Cambio de número de nota de crédito - Manual de Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Credit slip number change en MyPresta.eu](https://mypresta.eu/modules/administration-tools/credit-slip-number-change.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/back-office-tools/credit-slip-number-change/)
>
> ---


# Cambio de número de nota de crédito

## 1. Requisitos y Compatibilidad

- **Versiones de PrestaShop compatibles**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilidad con PHP**: PHP 7.1 - 8.5
- **Requisitos de alojamiento**: Las extensiones PHP estándar (cURL, JSON, OpenSSL) son típicamente requeridas por PrestaShop en sí y son suficientes para este módulo.

## 2. Recorrido completo por la configuración (Cada ajuste agrupado por pantalla)

### 2.1 Página de configuración del módulo (Back Office > Módulos > Configurar)

Este módulo tiene una página de configuración muy simple, principalmente para actualizaciones internas de MyPresta.eu. La funcionalidad principal de cambiar los números de las notas de crédito se accede directamente desde la página de detalles del pedido.

-   **Ubicación del menú:** Back Office > Módulos > Gestor de módulos > Busque "Cambio de número de nota de crédito" > Haga clic en "Configurar".

| Ajuste / Opción | Qué hace este ajuste | Efecto de cambiar este ajuste | Valor recomendado | Escenario / ejemplo del comerciante |
| --- | --- | --- | --- | --- |
| **Actualizaciones de MyPresta.eu** | Este ajuste controla si el módulo busca actualizaciones de MyPresta.eu. | *Cuando está habilitado:* El módulo buscará periódicamente nuevas versiones y le notificará en el back office. *Cuando está deshabilitado:* El módulo no buscará actualizaciones automáticamente. | SÍ | Mantener esto habilitado garantiza que siempre esté al tanto de las nuevas versiones, correcciones de errores y mejoras de funciones para el módulo. |

### 2.2 Pantallas de administración dedicadas y vistas de controlador

La funcionalidad principal de este módulo está integrada directamente en la **página de Detalles del pedido** en su back office de PrestaShop. No hay pantallas de administración dedicadas separadas.

-   **Nombre de la pantalla y ubicación del menú:** Back Office > Pedidos > Pedidos > Haga clic en cualquier pedido para ver sus detalles.
-   **Acciones y configuraciones disponibles:**
    -   En la página de Detalles del pedido, desplácese hasta la sección "Notas de crédito".
    -   Para cada nota de crédito listada, verá un nuevo campo de entrada junto a su número actual.
    -   Puede escribir un nuevo número en este campo.
    -   Después de ingresar el nuevo número, haga clic en el botón "Guardar" (o un icono similar, generalmente un disquete o una marca de verificación) junto al campo de entrada para aplicar el cambio.
-   **Efecto de los cambios:**
    -   Cuando cambia un número de nota de crédito y lo guarda, el nuevo número se actualiza inmediatamente en su base de datos de PrestaShop.
    -   Este nuevo número se reflejará en el PDF de la nota de crédito generado para esa nota de crédito específica. Tanto usted como su cliente verán el número actualizado en el documento.
-   **Flujo de trabajo recomendado para la gestión diaria de la tienda:**
    1.  Vaya a **Pedidos > Pedidos** en su back office de PrestaShop.
    2.  Seleccione el pedido para el que necesita modificar un número de nota de crédito.
    3.  En la página de Detalles del pedido, localice el bloque "Notas de crédito".
    4.  Encuentre la nota de crédito específica que desea cambiar.
    5.  Introduzca el nuevo número deseado en el campo de entrada proporcionado.
    6.  Haga clic en el icono de guardar junto al campo de entrada.
    7.  Verifique el cambio descargando el PDF de la nota de crédito; ahora debería mostrar el nuevo número.

### 2.3 Tabla de referencia rápida de configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| Configuración del módulo | Actualizaciones de MyPresta.eu | SÍ | Controla las comprobaciones automáticas de actualizaciones para el módulo. |
| Página de detalles del pedido (sección Notas de crédito) | Campo de entrada del número de nota de crédito | N/A (Definido por el usuario) | Permite la modificación directa de los números individuales de las notas de crédito. Los cambios se reflejan en el PDF. |

## 3. Solución de problemas para comerciantes y preguntas frecuentes (FAQ)

**P: Cambié el número de la nota de crédito, pero no aparece en el PDF.**
R: Después de cambiar el número, asegúrese de haber hecho clic en el botón "Guardar" junto al campo de entrada. Luego, regenere o vuelva a descargar el PDF de la nota de crédito. Si aún no aparece, intente borrar la caché de su navegador o la caché de Smarty de PrestaShop (Parámetros avanzados > Rendimiento > Borrar caché).

**P: ¿Puedo cambiar el número de una nota de crédito ya validada o enviada?**
R: Sí, el módulo le permite cambiar el número de cualquier nota de crédito existente. El cambio solo afectará el número que se muestra en el PDF, no la transacción financiera subyacente en sí.

**P: ¿Hay alguna forma de editar masivamente los números de las notas de crédito?**
R: No, este módulo está diseñado para cambios individuales de números de notas de crédito directamente en la página de detalles del pedido. No ofrece una función de edición masiva. Para operaciones masivas, podría ser necesario un desarrollo personalizado.

**P: ¿Qué sucede si introduzco un número de nota de crédito duplicado?**
R: El sistema central de PrestaShop podría no evitar los números de nota de crédito duplicados, ya que el módulo actualiza directamente el número. Es su responsabilidad garantizar la unicidad si sus prácticas contables lo requieren. El módulo facilita el cambio, pero no impone restricciones de unicidad más allá del comportamiento predeterminado de PrestaShop.

**P: El campo de entrada para cambiar el número no aparece en mi página de pedido.**
R:

1.  **Verifique la instalación del módulo:** Asegúrese de que el módulo esté correctamente instalado y habilitado en **Módulos > Gestor de módulos**.
2.  **Borre la caché:** Vaya a **Parámetros avanzados > Rendimiento** y haga clic en "Borrar caché".
3.  **Compatibilidad del tema:** Aunque el módulo utiliza ganchos estándar de PrestaShop, los temas muy personalizados a veces pueden interferir. Si el problema persiste, cambie temporalmente al tema predeterminado de PrestaShop para ver si aparece el campo. Si lo hace, su tema podría requerir un pequeño ajuste.
4.  **Versión de PrestaShop:** Asegúrese de haber descargado la versión correcta del módulo para su instalación de PrestaShop.

## 4. Guía para desarrolladores y webmasters (Arquitectura técnica y mapa de código)

### 4.1 Visión general de la arquitectura

El módulo "Cambio de número de nota de crédito" (`creditnb`) es un módulo ligero de PrestaShop que extiende la funcionalidad del back office inyectando un campo de entrada personalizado en el hook `displayAdminOrder`. Esto permite a los administradores modificar los números de las notas de crédito directamente en la página de detalles del pedido. El módulo interactúa principalmente con el objeto `OrderSlip` de PrestaShop y su tabla de base de datos asociada para actualizar el campo `number`. Aprovecha la estructura y las plantillas estándar de los módulos de PrestaShop.

### 4.2 Controladores (`controllers/`)

Este módulo no introduce ningún controlador personalizado de front office o back office. Todas las interacciones se manejan a través del archivo principal del módulo (`creditnb.php`) y los mecanismos AJAX estándar de PrestaShop para el envío de formularios dentro de la página de administración de pedidos.

### 4.3 Clases y modelos principales (`classes/`)

Este módulo no introduce ninguna clase o modelo personalizado en el directorio `classes/`. Interactúa directamente con el objeto `OrderSlip` nativo de PrestaShop.

### 4.4 Activos JavaScript (`views/js/`)

Este módulo no incluye ningún archivo JavaScript personalizado. La funcionalidad para guardar el nuevo número de nota de crédito se maneja mediante el envío del formulario dentro de la plantilla del hook `displayAdminOrder`, probablemente aprovechando el manejo de formularios o AJAX existente de PrestaShop.

### 4.5 Hojas de estilo CSS (`views/css/`)

Este módulo no incluye ningún archivo CSS personalizado. Se espera que el estilo del campo de entrada herede del tema del back office de PrestaShop.

### 4.6 Estructura de plantillas Smarty (`views/templates/`)

El módulo utiliza plantillas de hook para inyectar su funcionalidad en el back office de PrestaShop.

-   **Plantillas de hook (`views/templates/hook/`)**:
    -   `creditnb/views/templates/hook/displayAdminOrder16.tpl`
        -   **Propósito:** Esta plantilla está diseñada para PrestaShop 1.6.x (aunque el módulo lista compatibilidad con 1.7.x, 8.x, 9.x, este archivo podría ser una inclusión heredada o para una compatibilidad más amplia). Renderiza el campo de entrada y el botón de guardar para cambiar los números de las notas de crédito dentro de la sección "Notas de crédito" de la página de detalles del pedido.
        -   **Hook:** `displayAdminOrder`
        -   **Salida:** Un bloque HTML que contiene un elemento de formulario con un campo de entrada para el número de cada nota de crédito y un mecanismo para guardar el valor actualizado.
    -   `creditnb/views/templates/hook/displayAdminOrder17.tpl`
        -   **Propósito:** Esta plantilla está diseñada para PrestaShop 1.7.x, 8.x y 9.x. Renderiza el campo de entrada y el botón de guardar para cambiar los números de las notas de crédito dentro de la sección "Notas de crédito" de la página de detalles del pedido, adaptada para la interfaz de usuario más reciente del back office.
        -   **Hook:** `displayAdminOrder`
        -   **Salida:** Un bloque HTML que contiene un elemento de formulario con un campo de entrada para el número de cada nota de crédito y un mecanismo para guardar el valor actualizado.

### 4.7 Esquema de la base de datos y mapa de hooks

-   **Tablas de la base de datos**:

    -   El módulo no crea ninguna tabla de base de datos personalizada nueva.
    -   Modifica la columna `number` en la tabla `ps_order_slip` (o `_order_slip`), que forma parte del esquema de la base de datos central de PrestaShop.
    -   La configuración (`mypresta_updates`, `update_`, `updatev_`) se almacena en la tabla `ps_configuration`.
-   **Tabla de hooks registrados**:

| Nombre del Hook | Momento de ejecución | Propósito técnico |
| --- | --- | --- |
| `displayAdminOrder` | Renderiza contenido en la página de detalles del pedido del back office de PrestaShop. | Inyecta el campo de entrada personalizado y el mecanismo de guardado para modificar los números de las notas de crédito directamente en la sección "Notas de crédito" de la vista del pedido. |

## 5. Soporte oficial y actualizaciones

Para obtener las últimas actualizaciones, correcciones de errores y soporte profesional para el módulo "Cambio de número de nota de crédito", consulte su cuenta de cliente en [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nuestro equipo se dedica a garantizar el buen funcionamiento y la mejora continua de nuestros módulos.
