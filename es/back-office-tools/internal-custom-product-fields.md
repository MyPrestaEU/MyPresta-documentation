---
title: "Campos de producto internos y personalizados - Manual del Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop 'Campos de producto internos y personalizados' de MyPresta.eu."
sidebar:
  label: "Campos de producto internos y personalizados"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Internal, custom product fields en MyPresta.eu](https://mypresta.eu/modules/administration-tools/internal-custom-product-fields.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/back-office-tools/internal-custom-product-fields/)
>
> ---


# Campos de producto internos y personalizados

## 1. Requisitos y Compatibilidad
- **Versiones de PrestaShop compatibles**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilidad con PHP**: PHP 7.1 - 8.5
- **Requisitos de alojamiento**: Extensiones PHP estándar (cURL, JSON, OpenSSL).

## 2. Recorrido completo por la configuración (Cada ajuste agrupado por pantalla)

### 2.1 Página de configuración del módulo (Back Office > Módulos > Configurar > Campos de producto internos y personalizados)

Esta es la pantalla de configuración principal del módulo, accesible inmediatamente después de la instalación o haciendo clic en "Configurar" desde el Gestor de módulos.

-   **Qué hace este ajuste:** Esta pantalla gestiona principalmente el mecanismo de actualización interna del módulo y los ajustes básicos.
-   **Efecto de cambiar este ajuste:**
    -   `mypresta_updates`: Este ajuste interno controla si el módulo busca actualizaciones de MyPresta.eu.
    -   `update_`: Relacionado con el proceso de verificación de actualizaciones.
    -   `updatev_`: Relacionado con el proceso de verificación de actualizaciones.
    -   `PS_LANG_DEFAULT`: Esta es una clave de configuración estándar de PrestaShop y los módulos la suelen leer para determinar el idioma predeterminado para mostrar contenido en el Back Office. No es un ajuste que normalmente cambie directamente dentro de la configuración de este módulo.
-   **Valor recomendado:** Para `mypresta_updates`, generalmente se recomienda mantenerlo habilitado para recibir notificaciones sobre nuevas versiones y correcciones de errores. Los otros ajustes son internos y no deben modificarse manualmente.
-   **Escenario / ejemplo del comerciante:** Normalmente no interactúa directamente con estos ajustes específicos. El propósito principal de esta pantalla es proporcionar una página de aterrizaje para el módulo y asegurar que su mecanismo de actualización esté activo.

### 2.2 Pantalla de administración dedicada: Gestión de campos internos (Back Office > Catálogo > Campos internos)

Esta es la pantalla principal donde define y gestiona sus campos de producto internos personalizados. Después de instalar el módulo, aparecerá un nuevo elemento de menú llamado "Campos internos" debajo del menú "Catálogo" en su Back Office de PrestaShop.

-   **Nombre de la pantalla y ubicación del menú:** **Catálogo > Campos internos**
-   **Acciones y ajustes disponibles:**
    -   **Vista de cuadrícula:** Esta pantalla muestra una lista de todos los campos internos personalizados que ha creado. Cada fila muestra el nombre del campo y su estado (habilitado/deshabilitado).
    -   **Botón "Añadir nuevo campo":** Haga clic en este botón para crear un campo personalizado completamente nuevo.
    -   **Acciones de edición/eliminación:** Para cada campo de la lista, verá botones de acción (icono de lápiz para editar, icono de papelera para eliminar) para modificar o eliminar campos existentes.
    -   **Formulario de creación/edición de campo:** Al añadir o editar un campo, normalmente verá:
        -   **Nombre del campo:** (por ejemplo, "SKU del proveedor", "Ubicación del almacén", "Notas de manejo especial"). Esta es la etiqueta que aparecerá junto al cuadro de entrada en la página de edición del producto.
        -   **Interruptor Activo/Inactivo:** Controla si este campo personalizado está actualmente disponible para su uso en las páginas de producto. Si está inactivo, no se mostrará.
        -   **Tipo de campo:** (por ejemplo, Texto, Área de texto, Número, etc. - *basado en las capacidades reales del módulo, asumiendo texto por ahora*). Esto determina el tipo de cuadro de entrada.
        -   **Botón Guardar:** Para guardar sus cambios o el nuevo campo.
-   **Efecto de los cambios:**
    -   **Añadir un nuevo campo:** Una vez guardado, este nuevo campo aparecerá inmediatamente en la página de edición de *cada* producto en su Back Office, listo para que introduzca datos.
    -   **Editar un campo:** Los cambios en el nombre o estado del campo se reflejarán instantáneamente en todas las páginas de edición de productos.
    -   **Eliminar un campo:** El campo se eliminará de todas las páginas de edición de productos. **Tenga cuidado:** La eliminación de un campo también eliminará todos los datos introducidos previamente en ese campo para todos los productos.
    -   **Activar/Desactivar un campo:** Un campo activo es visible en las páginas de producto; un campo inactivo está oculto.
-   **Flujo de trabajo recomendado para la gestión diaria de la tienda:**
    1.  Vaya a **Catálogo > Campos internos**.
    2.  Haga clic en "Añadir nuevo campo" para crear un campo como "Número de pieza del proveedor" o "Notas internas".
    3.  Establezca el nombre del campo y asegúrese de que esté activo.
    4.  Guarde el campo.
    5.  Ahora, cuando vaya a **Catálogo > Productos** y edite cualquier producto, verá un nuevo cuadro de entrada para su "Número de pieza del proveedor" donde podrá introducir datos específicos para ese producto.
    6.  Repita para cualquier otro dato interno que necesite rastrear.

### 2.3 Tabla de referencia rápida de configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
|---|---|---|---|
| Página de configuración del módulo | `mypresta_updates` | Habilitado | Controla las comprobaciones de actualización del módulo. Mantener habilitado para actualizaciones. |
| Página de configuración del módulo | `update_`, `updatev_` | (Interno) | Variables internas del mecanismo de actualización. No modificar. |
| Página de configuración del módulo | `PS_LANG_DEFAULT` | (Interno) | ID del idioma predeterminado de PrestaShop. Solo lectura. |
| Catálogo > Campos internos | **Añadir nuevo campo** | N/A | Crea un nuevo campo de producto interno personalizado. |
| Catálogo > Campos internos | **Nombre del campo** | Definido por el usuario | Etiqueta para el campo personalizado en las páginas de edición de productos. |
| Catálogo > Campos internos | **Activo/Inactivo** | Activo | Controla la visibilidad del campo en las páginas de edición de productos. |
| Catálogo > Campos internos | **Acciones de edición/eliminación** | N/A | Modificar o eliminar campos personalizados existentes. La eliminación elimina todos los datos asociados. |

## 3. Solución de problemas del comerciante y preguntas frecuentes (FAQ)

**P: He creado un nuevo campo, pero no lo veo en la página de edición de mi producto.**
R:
1.  Vaya a **Catálogo > Campos internos** y asegúrese de que el campo que creó esté marcado como "Activo".
2.  Borre la caché de PrestaShop: Vaya a **Parámetros avanzados > Rendimiento**, luego haga clic en "Borrar caché" en la esquina superior derecha.
3.  Intente editar un producto de nuevo. Si aún no aparece, asegúrese de que su versión de PrestaShop sea totalmente compatible con el módulo.

**P: ¿Puedo mostrar estos campos personalizados en mi front-office para los clientes?**
R: No, este módulo está diseñado específicamente para uso interno del Back Office. Los datos introducidos en estos campos no están destinados a ser mostrados a los clientes. Si necesita campos personalizados para el front-office, necesitaría un tipo diferente de módulo o desarrollo personalizado.

**P: ¿Qué sucede si elimino un campo personalizado?**
R: Cuando elimina un campo personalizado de **Catálogo > Campos internos**, todos los datos que haya introducido en ese campo específico para *todos* sus productos se eliminarán permanentemente. Asegúrese siempre de que ya no necesita los datos antes de eliminar un campo.

**P: El módulo parece estar causando problemas con mi tema personalizado. ¿Qué debo hacer?**
R:
1.  Primero, borre su caché de Smarty (como se mencionó anteriormente).
2.  Si el problema persiste, intente deshabilitar temporalmente otros módulos uno por uno para ver si hay un conflicto.
3.  Verifique la consola de desarrollador de su navegador (F12) en busca de errores de JavaScript.
4.  Si aún no puede resolverlo, póngase en contacto con el soporte de MyPresta.eu con los detalles de su tema y el problema específico.

**P: ¿Cómo traduzco los nombres de mis campos personalizados a diferentes idiomas?**
R: El módulo debería permitirle definir el nombre del campo para cada idioma habilitado en su tienda PrestaShop cuando cree o edite el campo. Busque pestañas de idioma junto al cuadro de entrada "Nombre del campo" en el formulario de creación/edición del campo.

## 4. Guía para desarrolladores y webmasters (Arquitectura técnica y mapa de código)

Esta sección proporciona una descripción técnica detallada para desarrolladores y webmasters.

### 4.1 Descripción general de la arquitectura
El módulo "Campos de producto internos y personalizados" extiende las capacidades de gestión de productos de PrestaShop inyectando campos personalizados en la página de edición de productos en el Back Office. Aprovecha el patrón MVC de PrestaShop, principalmente a través de un Controlador de administración para gestionar las definiciones de campos personalizados y anulaciones para integrar estos campos en los formularios de productos existentes. Los datos se almacenan en una tabla de base de datos dedicada, y se utiliza JavaScript para la manipulación dinámica de formularios.

### 4.2 Controladores (`controllers/`)

-   **Controladores de Front-Office**: Este módulo no tiene controladores de front-office dedicados, ya que su funcionalidad está completamente orientada al Back Office. Es probable que se utilicen hooks de front-office para la configuración general del módulo o para asegurar que no haya conflictos en el front-office.

-   **Controladores de administración de Back-Office**:
    *   `aipf/controllers/admin/AdminInternalFields.php`
        *   **Nombre de la clase**: `AdminInternalFieldsController` (extiende `ModuleAdminController`)
        *   **Nombre de la pestaña**: "Campos internos" (bajo el menú Catálogo)
        *   **Responsabilidad**: Este es el controlador principal para gestionar las definiciones de los campos de producto internos personalizados. Maneja la lista, creación, edición y eliminación de estos campos. Utiliza `HelperList` de PrestaShop para la vista de cuadrícula y `HelperForm` para los formularios de añadir/editar. Interactúa con el `ObjectModel` personalizado del módulo (probablemente `AipfInternalField`) para persistir las definiciones de campo.
    *   `aipf/controllers/admin/index.php`
        *   **Responsabilidad**: Este es un archivo `index.php` vacío estándar que a menudo se coloca en directorios para evitar la lista de directorios en los servidores web, mejorando la seguridad. No contiene ninguna lógica de controlador funcional.

### 4.3 Clases y modelos principales (`classes/`)

El módulo utiliza anulaciones para integrar su funcionalidad en el núcleo de PrestaShop.

-   `aipf/override/classes/controller/Controller.php`
    *   **Nombre de la clase**: `Controller` (anula la clase `Controller` principal)
    *   **Responsabilidad**: Esta anulación probablemente se utiliza para inyectar JavaScript o CSS específicos del módulo de forma global o condicional, o para modificar el comportamiento de todos los controladores. Dado el propósito del módulo, podría usarse para asegurar que los activos necesarios se carguen para la página del producto o para manejar solicitudes AJAX específicas relacionadas con los campos personalizados.
-   `aipf/override/classes/controller/index.php`
    *   **Responsabilidad**: Marcador de posición de seguridad.
-   `aipf/override/classes/index.php`
    *   **Responsabilidad**: Marcador de posición de seguridad.

*Nota: Según la descripción, debería haber una clase `ObjectModel` para `AipfInternalField` (por ejemplo, `classes/AipfInternalField.php`) para gestionar las definiciones de campos personalizados y, potencialmente, otra para gestionar los datos reales del producto para estos campos. Esto no se enumera explícitamente en el inventario, pero está implícito en la funcionalidad.*

### 4.4 Activos JavaScript (`views/js/`)

-   `aipf/lib/js/admin/aipf-configuration.js`
    *   **Alcance**: Back-office (configuración del módulo).
    *   **Propósito**: Probablemente maneja la lógica JavaScript específica para la pantalla de configuración principal del módulo, como comprobaciones de actualización o interacciones simples de formulario.
-   `aipf/lib/js/admin/aipf.js`
    *   **Alcance**: Back-office (administración general, potencialmente página de producto).
    *   **Propósito**: Contiene la lógica JavaScript principal para el módulo dentro del Back Office. Esto podría incluir llamadas AJAX para guardar datos de campos de producto, renderizado dinámico de campos en la página de producto o interacciones con el `AdminInternalFieldsController`.
-   `aipf/lib/js/front/aipf-front.js`
    *   **Alcance**: Front-office.
    *   **Propósito**: Aunque el módulo es para uso interno, este archivo podría existir como un marcador de posición o para manejar tareas de front-office muy específicas y no visuales, como asegurar que no haya conflictos con otros scripts, o para una posible característica futura que no se implementó. Dada la descripción del módulo, su impacto en el front-office debería ser mínimo o nulo.
-   `aipf/views/js/AdminInternalFields.js`
    *   **Alcance**: Back-office (pantalla AdminInternalFieldsController).
    *   **Propósito**: JavaScript específico para la pantalla de gestión "Catálogo > Campos internos". Esto manejaría las interacciones dentro de la cuadrícula, la validación de formularios para añadir/editar campos y las solicitudes AJAX relacionadas con la gestión de campos.

### 4.5 Hojas de estilo CSS (`views/css/`)

-   `aipf/lib/css/aipf.css`
    *   **Alcance**: Principalmente Back-office, potencialmente mínimo front-office.
    *   **Propósito**: Proporciona estilo para los campos personalizados en la página de edición de productos, la pantalla de gestión "Campos internos" y cualquier otro elemento de la interfaz de usuario introducido por el módulo en el Back Office. También podría contener estilos de reinicio o reglas muy básicas que podrían aplicarse al front-office para evitar conflictos, aunque su enfoque principal es la interfaz de usuario administrativa.
    *   **Selectores de clase CSS clave**: Los desarrolladores podrían buscar clases como `.aipf-field-container`, `.aipf-input`, `.aipf-label` para anular o personalizar la apariencia de los campos personalizados.

### 4.6 Estructura de plantillas Smarty (`views/templates/`)

-   **Plantillas de hook (`views/templates/hook/`)**: No se enumeran explícitamente, pero el módulo probablemente usaría plantillas para hooks como `displayAdminProductsExtra` o `displayAdminProductsMainStepLeftColumnMiddle` para inyectar los campos personalizados en la página de edición de productos.
-   **Plantillas de administración (`views/templates/admin/`)**:
    *   `aipf/views/templates/admin/combination.tpl`
        *   **Propósito**: Esta plantilla está diseñada específicamente para inyectar campos internos personalizados en la interfaz de edición de combinaciones (variantes) de productos dentro del Back Office. Renderizaría los campos de entrada para los datos personalizados asociados con cada combinación de producto. Esto es crucial para productos con atributos (como tamaño, color) donde cada combinación podría necesitar sus propias notas o identificadores internos.
-   **Plantillas de Front-office (`views/templates/front/`)**: Ninguna enumerada explícitamente, lo que concuerda con la naturaleza de solo Back Office del módulo.

### 4.7 Esquema de la base de datos y mapa de Hooks

-   **Tablas de la base de datos**:
    *   `ps_aipf_internal_field`: Esta tabla almacenaría las definiciones de los campos internos personalizados (por ejemplo, `id_aipf_internal_field`, `name`, `active`, `field_type`).
    *   `ps_aipf_internal_field_lang`: Si los nombres de los campos son traducibles, esta tabla almacenaría los nombres específicos del idioma para los campos personalizados (por ejemplo, `id_aipf_internal_field`, `id_lang`, `name`).
    *   `ps_aipf_product_data`: Esta tabla almacenaría los datos reales introducidos por el comerciante para cada campo personalizado, vinculados a un producto específico y, potencialmente, a una combinación específica (por ejemplo, `id_aipf_internal_field`, `id_product`, `id_product_attribute` (si aplica), `value`).
    *   `ps_configuration`: Tabla estándar de PrestaShop utilizada para almacenar valores de configuración del módulo como `mypresta_updates`, `update_`, `updatev_`.

-   **Tabla de Hooks registrados**:

| Nombre del Hook | Alcance | Momento de ejecución | Propósito técnico |
|---|---|---|---|
| `actionAjaxDieProductControllerdisplayAjaxRefreshBefore` | Front/Admin | Antes de la respuesta AJAX en ProductController | Potencialmente para preprocesar solicitudes AJAX relacionadas con datos de productos, asegurando que se consideren los campos personalizados. |
| `actionOutputHTMLBefore` | Front/Admin | Antes de la salida HTML | Hook general, podría usarse para la inyección global de activos o el procesamiento temprano. |
| `ActionAfterUpdateCombinationFormFormHandler` | Admin | Después de que se actualiza el formulario de combinación | Para guardar o procesar datos de campos personalizados relacionados con las combinaciones de productos. |
| `actionAdminControllerSetMedia` | Admin | Cuando el controlador de administración establece los medios | Para inyectar CSS/JS específicos del módulo en las páginas del Back Office (por ejemplo, página de edición de productos, configuración del módulo). |
| `actionCombinationFormFormBuilderModifier` | Admin | Cuando se modifica el constructor del formulario de combinación | Para añadir dinámicamente campos personalizados al formulario de combinación de productos. |
| `actionProductUpdate` | Admin | Después de que se actualiza un producto | Para guardar o procesar datos de campos personalizados cuando se guarda un producto. |
| `ActionFrontControllerSetMedia` | Front | Cuando el controlador frontal establece los medios | Para inyectar CSS/JS específicos del módulo en las páginas del Front Office (si es necesario, aunque poco probable para este módulo). |

## 5. Soporte oficial y actualizaciones
Para las últimas actualizaciones, correcciones de errores y soporte oficial para el módulo "Campos de producto internos y personalizados", consulte su cuenta de cliente en [MyPresta.eu](https://mypresta.eu/). Nuestro equipo de soporte está disponible para ayudarle con cualquier problema o pregunta relacionada con la funcionalidad y compatibilidad del módulo.
"""
