---
title: "Gestor de menú del Back Office - Manual de Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop 'Gestor de menú del Back Office' de MyPresta.eu."
sidebar:
  label: "Gestor de menú del Back Office - Manual de Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Back office menu manager en MyPresta.eu](https://mypresta.eu/modules/administration-tools/back-office-menu-manager.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/back-office-tools/back-office-menu-manager/)
>
> ---


# Gestor de menú del Back Office

## 1. Requisitos y Compatibilidad

- **Versiones de PrestaShop compatibles**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilidad con PHP**: PHP 7.1 - 8.5
- **Requisitos de alojamiento**: Extensiones PHP estándar (cURL, JSON, OpenSSL).

## 2. Recorrido completo de configuración (Cada grupo de ajustes por pantalla)

### 2.1 Página de configuración del módulo (Back Office > Módulos > Configurar)

Después de la instalación, al hacer clic en "Configurar" se le dirigirá a la pantalla principal de configuración del módulo "Gestor de menú del Back Office".

Esta pantalla suele contener ajustes estándar del módulo, que pueden incluir:

-   **Activar/Desactivar Módulo:**

    -   **Qué hace este ajuste:** Este es un interruptor maestro para activar o desactivar la funcionalidad del módulo.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando está activado:* Las características del módulo, incluidas las nuevas opciones de gestión de menú, estarán activas en su Back Office.
        -   *Cuando está desactivado:* El módulo dejará de afectar su menú del Back Office, y el comportamiento predeterminado del menú de PrestaShop se reanudará.
    -   **Valor recomendado:** **SÍ** (Activado) para usar el módulo.
    -   **Escenario / ejemplo de comerciante:** Si está probando el módulo o desea volver temporalmente al menú predeterminado de PrestaShop, puede desactivarlo aquí.
-   **Restablecer la configuración del módulo:**

    -   **Qué hace este ajuste:** Esta opción le permite revertir todos los ajustes específicos del módulo y, potencialmente, cualquier configuración de menú personalizada a su estado predeterminado.
    -   **Efecto de cambiar este ajuste:**
        -   *Al hacer clic:* Todas sus disposiciones de menú personalizadas y preferencias del módulo se borrarán, y el módulo se comportará como si acabara de ser instalado por primera vez.
    -   **Valor recomendado:** Úselo con precaución. Solo haga clic si desea reiniciar completamente la configuración de su menú.
    -   **Escenario / ejemplo de comerciante:** Si ha realizado muchos cambios y desea empezar de nuevo, o si encuentra un problema inesperado y desea descartar problemas de configuración, este puede ser un paso útil para la resolución de problemas.

### 2.2 Pantallas de administración dedicadas y vistas de controlador

Este módulo introduce una nueva sección dedicada en su Back Office de PrestaShop para gestionar las pestañas del menú.

#### Nombre de la pantalla y ubicación del menú: `AdminMenuTabsController`

-   **Ubicación del menú:** Después de instalar el módulo, encontrará un nuevo elemento de menú, normalmente bajo **Parámetros avanzados** o una sección administrativa similar, llamado algo como **"Gestor de menú"** o **"Menú del Back Office"**. Al hacer clic en él, accederá a la pantalla `AdminMenuTabsController`.
-   **Acciones y ajustes disponibles:**
    Esta pantalla proporciona una vista de cuadrícula (tabla) completa de todas las pestañas de menú actualmente disponibles en su Back Office de PrestaShop. Para cada pestaña de menú, normalmente verá:

    -   **ID:** El identificador único de la pestaña del menú.
    -   **Nombre:** El nombre de visualización de la pestaña del menú (por ejemplo, "Pedidos", "Productos", "Clientes").
    -   **Pestaña padre:** A qué elemento del menú principal pertenece esta pestaña (por ejemplo, "Pedidos" es padre de "Pedidos", "Facturas", "Notas de crédito").
    -   **Posición:** El orden numérico de la pestaña dentro de su grupo padre.
    -   **Interruptor Activo/Inactivo:** Un conmutador para habilitar o deshabilitar la visibilidad de la pestaña del menú.
    -   **Acciones de Editar/Eliminar:** Botones para modificar los detalles de una pestaña específica o eliminarla (use eliminar con extrema precaución, ya que podría eliminar funcionalidades centrales).

    **Funcionalidades clave que puede realizar aquí:**

    -   **Reordenar elementos del menú:** Normalmente puede arrastrar y soltar filas en la cuadrícula o cambiar manualmente el valor de 'Posición' para reordenar cómo aparecen los elementos del menú.
    -   **Ocultar/Mostrar elementos del menú:** Use el interruptor activo/inactivo para ocultar elementos del menú que no usa o que desea restringir a ciertos roles del personal (si se combina con los permisos nativos de PrestaShop).
    -   **Editar detalles del elemento del menú:** Es posible que pueda cambiar el nombre de visualización de un elemento del menú, su icono o su asociación padre (aunque cambiar las asociaciones padre para las pestañas centrales generalmente no se recomienda sin conocimientos avanzados).
    -   **Agregar nuevos elementos del menú:** Aunque es menos común para este módulo específico (que se centra en la gestión de pestañas *existentes*), algunas versiones avanzadas podrían permitir agregar enlaces de menú personalizados.
-   **Efecto de los cambios:**

    -   **Ocultar una pestaña:** La pestaña desaparecerá inmediatamente de su menú del Back Office para todos los usuarios (a menos que existan anulaciones de permisos específicos).
    -   **Reordenar pestañas:** El orden de los elementos del menú cambiará instantáneamente en la navegación del Back Office.
    -   **Editar el nombre de una pestaña:** El nombre que se muestra en el menú del Back Office se actualizará.
-   **Flujo de trabajo recomendado para la gestión diaria de la tienda:**

    1.  **Configuración inicial:** Revise todos los elementos de su menú principal y sus subelementos. Decida cuáles usa su equipo regularmente, rara vez o nunca.
    2.  **Desordenar:** Para los elementos que se usan rara vez o nunca, use el interruptor "Activo/Inactivo" para ocultarlos. Esto simplifica significativamente el menú.
    3.  **Priorizar:** Reordene los elementos de acceso frecuente para que estén en la parte superior de sus respectivas secciones. Por ejemplo, si pasa la mayor parte de su tiempo en "Pedidos", asegúrese de que "Pedidos" sea el primer subelemento bajo el menú principal "Pedidos".
    4.  **Revisar regularmente:** A medida que las operaciones de su tienda evolucionen o se instalen nuevos módulos (que a menudo añaden sus propios elementos de menú), vuelva a visitar esta pantalla para mantener su menú optimizado.

#### Nombre de la pantalla y ubicación del menú: `index.php` (`adminmenu/controllers/admin/index.php`)

Este archivo, `index.php` dentro de un directorio de controlador de administración, normalmente sirve como un marcador de posición o un punto de entrada para la funcionalidad del controlador, en lugar de una pantalla independiente con opciones configurables. En PrestaShop, la lógica y la visualización reales para un controlador de administración son manejadas por la clase principal (por ejemplo, `AdminMenuTabsController.php`).

Por lo tanto, no interactuará directamente con una pantalla "index.php". Su presencia es parte de la estructura interna del módulo, asegurando que `AdminMenuTabsController` funcione correctamente. Todas sus interacciones serán a través de la interfaz `AdminMenuTabsController` descrita anteriormente.

### 2.3 Tabla de referencia rápida de configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| Configuración del módulo | Activar/Desactivar Módulo | Activado | Activa/desactiva las funciones de gestión de menú del módulo. |
| Configuración del módulo | Restablecer la configuración del módulo | N/A (Acción) | Restablece todos los ajustes del módulo y las configuraciones de menú a los valores predeterminados. Usar con precaución. |
| `AdminMenuTabsController` | Nombre de la pestaña (ej., "Pedidos") | Nombre original de PrestaShop | Muestra el nombre del elemento del menú. Se puede editar. |
| `AdminMenuTabsController` | Pestaña padre | Padre original de PrestaShop | Muestra la categoría del menú principal para este elemento. |
| `AdminMenuTabsController` | Posición | Varía | Controla el orden de visualización del elemento del menú dentro de su padre. Se puede cambiar arrastrando y soltando o mediante entrada directa. |
| `AdminMenuTabsController` | Interruptor Activo/Inactivo | Activo | Alterna la visibilidad del elemento del menú en el Back Office. |
| `AdminMenuTabsController` | Acciones de Editar/Eliminar | N/A (Acción) | Permite la modificación de los detalles de la pestaña o su eliminación (eliminar con precaución). |

## 3. Resolución de problemas para comerciantes y preguntas frecuentes (FAQ)

**P: He ocultado un elemento del menú, pero sigue apareciendo para algunos usuarios. ¿Por qué?**
R: Este módulo gestiona la *visibilidad* y el *orden* de los elementos del menú. Los permisos de usuario nativos de PrestaShop (en **Parámetros avanzados > Equipo > Perfiles** y **Permisos**) determinan *quién puede acceder a qué*. Si un perfil de usuario tiene permiso explícito para una pestaña, es posible que aún la vea incluso si la ha marcado como inactiva en este módulo. Siempre verifique tanto la configuración de este módulo como los permisos de PrestaShop.

**P: He realizado cambios, pero el menú no se ha actualizado. ¿Qué debo hacer?**
R:

1.  **Borrar la caché de PrestaShop:** Vaya a **Parámetros avanzados > Rendimiento**. Haga clic en "Borrar caché" en la esquina superior derecha. Esto a menudo es necesario para que los cambios en el Back Office surtan efecto.
2.  **Actualizar el navegador:** A veces, es necesaria una actualización forzada de su navegador (Ctrl+F5 o Cmd+Shift+R) para borrar la caché local del navegador.
3.  **Verificar el estado del módulo:** Asegúrese de que el módulo "Gestor de menú del Back Office" siga activado en **Módulos > Gestor de módulos**.

**P: ¿Puedo añadir enlaces personalizados completamente nuevos al menú del Back Office con este módulo?**
R: Este módulo se centra principalmente en la gestión de las pestañas de menú *existentes* de PrestaShop. Aunque algunas versiones avanzadas podrían ofrecer la creación de enlaces personalizados, su propósito principal es permitir la gestión de la estructura de menú predeterminada de PrestaShop. Si necesita añadir enlaces personalizados complejos, podría requerir un módulo más avanzado o un desarrollo personalizado.

**P: Accidentalmente eliminé un elemento del menú principal de PrestaShop. ¿Cómo lo recupero?**
R: Generalmente no se recomienda eliminar elementos del menú principal. Si lo ha hecho, la forma más segura de restaurarlo es:

1.  **Desactivar y volver a activar el módulo:** Vaya a **Módulos > Gestor de módulos**, busque "Gestor de menú del Back Office", desactívelo y luego vuelva a activarlo. Esto a menudo desencadena una reinicialización de las entradas de menú predeterminadas.
2.  **Restablecer la configuración del módulo:** Si lo anterior no funciona, vaya a la página de configuración del módulo y use la opción "Restablecer la configuración del módulo". Tenga en cuenta que esto borrará TODAS sus configuraciones de menú personalizadas.
3.  **Restaurar desde una copia de seguridad:** Como último recurso, si faltan elementos críticos del menú, es posible que deba restaurar su base de datos desde una copia de seguridad realizada *antes* de la eliminación.

## 4. Guía para desarrolladores y webmasters (Arquitectura técnica y mapa de código)

Esta sección proporciona una descripción técnica para desarrolladores y webmasters que trabajan con el módulo "Gestor de menú del Back Office".

### 4.1 Resumen de la arquitectura

El módulo "Gestor de menú del Back Office" extiende principalmente la funcionalidad central del Back Office de PrestaShop anulando clases de ayuda específicas para reintroducir las capacidades de gestión de menú. Aprovecha el patrón MVC de PrestaShop, con un controlador de administración dedicado (`AdminMenuTabsController`) para proporcionar la interfaz de usuario para gestionar las pestañas del menú. El módulo interactúa con la tabla de la base de datos `ps_tab`, que almacena información sobre los elementos del menú del Back Office. La decisión arquitectónica clave es el uso de anulaciones para modificar el comportamiento central de PrestaShop sin alterar directamente los archivos centrales, lo que garantiza una mejor compatibilidad y rutas de actualización.

### 4.2 Controladores (`controllers/`)

-   **Controladores del Front-Office**:
    Este módulo no contiene ningún controlador de front-office ya que su funcionalidad es exclusivamente para el Back Office de PrestaShop.
-   **Controladores de administración del Back-Office**:

    -   `adminmenu/controllers/admin/AdminMenuTabs.php`

        -   **Nombre de la clase y clase padre**: `AdminMenuTabsController` extiende `ModuleAdminController`.
        -   **Nombre de la pestaña y entidad gestionada**: Este controlador gestiona la entidad `Tab` (que representa los elementos del menú del Back Office). Crea una entrada de menú dedicada en el Back Office para "Gestor de menú".
        -   **Responsabilidad**: Este es el controlador principal de la interfaz de usuario del módulo. Maneja la visualización de la lista de todas las pestañas del Back Office, permitiendo a los administradores ver, editar, activar/desactivar y reordenarlas. Normalmente utiliza `HelperList` para la visualización de la cuadrícula y `HelperForm` para cualquier formulario de edición. Procesa las solicitudes POST para guardar cambios (por ejemplo, actualizaciones de posición, alternancia de estado).
    -   `adminmenu/controllers/admin/index.php`

        -   **Responsabilidad**: Este archivo es un marcador de posición estándar dentro de la estructura de controladores de PrestaShop. Normalmente contiene una simple declaración `die('No direct script access allowed');` para evitar el acceso directo al directorio y asegurar que las solicitudes se enruten a través del despachador de PrestaShop. No contiene ninguna lógica funcional para el módulo en sí.

### 4.3 Clases y modelos principales (`classes/`)

El módulo utiliza anulaciones para modificar el comportamiento central de PrestaShop.

-   `adminmenu/override/classes/helper/HelperList.php`

    -   **Nombre de la clase y clase padre**: `HelperList` (anula la clase `HelperList` central).
    -   **Qué hace**: Esta anulación probablemente modifica el comportamiento de `HelperList` específicamente al renderizar la lista de entidades `Tab` en el Back Office. Esto es crucial para volver a habilitar características como la reordenación por arrastrar y soltar o las visualizaciones de columnas específicas que se eliminaron de la implementación predeterminada de `HelperList` para `Tab` en versiones más recientes de PrestaShop. Podría inyectar acciones personalizadas o modificar cómo se obtienen o muestran los datos para las pestañas del menú.
-   `adminmenu/override/classes/helper/index.php`

    -   **Responsabilidad**: Similar a `controllers/admin/index.php`, este es un archivo de marcador de posición para evitar la lista o el acceso directo al directorio.
-   `adminmenu/override/classes/index.php`

    -   **Responsabilidad**: Otro archivo de marcador de posición para evitar la lista o el acceso directo al directorio.

### 4.4 Activos JavaScript (`views/js/`)

El inventario proporcionado indica que no hay archivos JavaScript personalizados dentro del módulo. Esto sugiere que la funcionalidad de gestión del menú, incluidas características como la reordenación por arrastrar y soltar, se maneja mediante:

1.  El JavaScript nativo de `HelperList` de PrestaShop (que la anulación del módulo podría volver a habilitar o configurar).
2.  Procesamiento del lado del servidor para actualizaciones de posición.
3.  JS en línea mínimo generado por las clases `HelperList` o `HelperForm`.

Los desarrolladores deben inspeccionar el HTML generado y las solicitudes de red en la página `AdminMenuTabsController` para comprender la implementación exacta de JS para los elementos interactivos.

### 4.5 Hojas de estilo CSS (`views/css/`)

El inventario proporcionado indica que no hay archivos CSS personalizados dentro del módulo. Esto implica que el módulo se basa completamente en el estilo predeterminado del Back Office de PrestaShop. Cualquier estilo personalizado para la interfaz del gestor de menú sería:

1.  Inyectado en línea a través de plantillas Smarty o PHP.
2.  Aprovechando las clases CSS existentes de PrestaShop.

### 4.6 Estructura de la plantilla Smarty (`views/templates/`)

El inventario proporcionado indica que no hay archivos de plantilla Smarty (`.tpl`) personalizados dentro del módulo. Este es un fuerte indicador de que el módulo se basa principalmente en las plantillas predeterminadas de `HelperList` y `HelperForm` de PrestaShop para renderizar su interfaz de Back Office.

El `AdminMenuTabsController` instanciaría objetos `HelperList` y `HelperForm`, pasándoles matrices de configuración, y estos ayudantes luego renderizarían la interfaz de usuario utilizando las plantillas centrales de PrestaShop (por ejemplo, `_partials/helpers/list_action_enable.tpl`, `helpers/list/list_content.tpl`, `helpers/form/form.tpl`).

### 4.7 Esquema de la base de datos y mapa de hooks

-   **Tablas de la base de datos**:
    Este módulo interactúa principalmente con la tabla central existente de PrestaShop:

    -   `ps_tab`: Esta tabla almacena todas las entradas del menú del Back Office, incluidos sus nombres, IDs de padres, posiciones y estado activo. El `AdminMenuTabsController` del módulo y la anulación de `HelperList` leen y escriben directamente en esta tabla para gestionar el menú.
    -   `ps_configuration`: Tabla de configuración estándar de PrestaShop. La configuración principal del módulo (por ejemplo, estado de activación/desactivación) se almacenaría aquí (por ejemplo, `PS_ADMINMENU_MANAGER_ENABLED`).
-   **Tabla de Hooks registrados**:
    Según la descripción y funcionalidad del módulo, no registra explícitamente ningún hook de visualización de front-office o back-office (`displayHeader`, `actionValidateOrder`, etc.) en el sentido tradicional. Su funcionalidad se logra a través de:

    1.  **Registro del controlador de administración**: El módulo registra `AdminMenuTabsController` como una nueva pestaña del Back Office, haciéndola accesible a través del menú del Back Office.
    2.  **Anulaciones de clases**: El mecanismo central se basa en anular `classes/helper/HelperList.php` para modificar cómo se gestionan y muestran las pestañas del menú en el Back Office. Esto no es un "hook" sino una modificación directa del comportamiento central.

    Por lo tanto, una tabla de hooks registrados no es aplicable en el sentido típico para este módulo. Su impacto está en el funcionamiento interno de la renderización del menú del Back Office.

## 5. Soporte oficial y actualizaciones

Para las últimas actualizaciones, correcciones de errores y soporte profesional para el módulo "Gestor de menú del Back Office", consulte su cuenta de cliente en [MyPresta.eu](https://mypresta.eu/). Nuestro equipo de soporte está disponible para ayudarle con cualquier problema o pregunta que pueda tener con respecto a la funcionalidad y compatibilidad del módulo.
"""
