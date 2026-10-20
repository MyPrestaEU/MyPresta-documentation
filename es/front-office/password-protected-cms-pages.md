---
title: "Páginas CMS protegidas con contraseña - Manual de Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop 'Páginas CMS protegidas con contraseña' de MyPresta.eu."
sidebar:
  label: "Páginas CMS protegidas con contraseña - Manual de Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Password protected CMS pages en MyPresta.eu](https://mypresta.eu/modules/front-office-features/password-protected-cms-pages.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/front-office/password-protected-cms-pages/)
>
> ---


# Páginas CMS protegidas con contraseña

## 1. Requisitos y Compatibilidad

- **Versiones de PrestaShop compatibles**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilidad con PHP**: PHP 5.6 - 8.5
- **Requisitos de alojamiento**: Extensiones PHP estándar (cURL, JSON, OpenSSL).

## 2. Recorrido Completo por la Configuración (Cada Ajuste Agrupado por Pantalla)

### 2.1 Página de Configuración del Módulo (Back Office > Módulos > Configurar)

Después de la instalación, al hacer clic en "Configurar" en el módulo, accederá a su pantalla de configuración principal. Esta pantalla sirve principalmente como punto de entrada al área de gestión dedicada para sus páginas CMS protegidas con contraseña.

-   **Qué hace esta pantalla:** Esta página suele proporcionar una breve descripción general o un enlace directo a la interfaz de gestión principal donde realmente configurará y gestionará sus páginas CMS protegidas con contraseña. También podría contener configuraciones generales si el módulo las tuviera, pero para este módulo, la funcionalidad principal se gestiona en una sección separada.
-   **Efecto de cambiar la configuración:** Cualquier configuración aquí impactaría directamente el comportamiento o la apariencia global del módulo.
-   **Valor recomendado:** Siga las instrucciones en pantalla, generalmente haciendo clic en un botón para proceder a la gestión de la página CMS.
-   **Escenario / ejemplo de comerciante:** Acaba de instalar el módulo. Probablemente verá un botón como "Gestionar páginas CMS protegidas" o "Configurar contraseñas CMS". Al hacer clic en él, accederá a la pantalla dedicada para empezar a proteger sus páginas.

### 2.2 Pantalla de Administración Dedicada: Gestionar Páginas CMS Protegidas (Back Office > Módulos > Páginas CMS protegidas con contraseña > Configurar > [Enlace a Gestión])

Esta es la pantalla principal donde gestionará qué páginas CMS están protegidas y cuáles son sus contraseñas. Accede a esta pantalla normalmente haciendo clic en un enlace o botón desde la página de configuración principal del módulo.

-   **Nombre de la pantalla y ubicación del menú:** Normalmente encontrará un nuevo elemento de menú en **Módulos > Gestor de módulos > Páginas CMS protegidas con contraseña > Configurar**, que luego le dirigirá a la interfaz de gestión. La URL podría ser algo como `admin/index.php?controller=AdminPcmsController`.
-   **Acciones y configuraciones disponibles:**
    -   **Tabla de listado:** Esta pantalla mostrará una tabla con todas sus páginas CMS existentes. Para cada página, verá su nombre, ID y si está protegida actualmente.
    -   **Añadir/Editar protección:** Para cada página CMS en la lista, normalmente encontrará un botón/icono de "Editar" o "Configurar". Al hacer clic en él, se abrirá un formulario donde podrá:
        -   **Activar/Desactivar protección:** Un simple interruptor (Sí/No) para activar o desactivar la protección con contraseña para esa página CMS específica.
            -   *Cuando está activada:* La página requerirá una contraseña para ver su contenido en el front office.
            -   *Cuando está desactivada:* La página será de acceso público como una página CMS estándar.
            -   *Valor recomendado:* "Sí" para las páginas que desea proteger, "No" para las páginas públicas.
            -   *Escenario de comerciante:* Desea proteger su página de "Ofertas VIP", por lo que activa la protección.
        -   **Establecer contraseña:** Un campo de entrada donde define la contraseña para esa página CMS específica.
            -   *Efecto de cambiar:* Esta es la contraseña exacta que los clientes deberán introducir para ver la página.
            -   *Valor recomendado:* Elija una contraseña fuerte y única para cada página protegida.
            -   *Escenario de comerciante:* Establece "MISECRETO" como contraseña para su página de "Ofertas VIP".
    -   **Acciones masivas:** Dependiendo de la versión del módulo, podría haber opciones para activar/desactivar la protección para varias páginas a la vez, aunque la gestión individual de páginas es más común para la configuración de contraseñas.
-   **Efecto de los cambios:**
    -   Cuando activa la protección y establece una contraseña para una página CMS, esa página se protege inmediatamente con contraseña en su front office. Los clientes que visiten su URL verán la solicitud de contraseña.
    -   Desactivar la protección hace que la página vuelva a ser visible públicamente.
-   **Flujo de trabajo recomendado para la gestión diaria de la tienda:**
    1.  Decida qué páginas CMS deben ser privadas o exclusivas.
    2.  Navegue a esta pantalla de "Gestionar páginas CMS protegidas".
    3.  Encuentre la página CMS deseada en la lista.
    4.  Haga clic en "Editar" o la acción equivalente para esa página.
    5.  Active el interruptor de protección con contraseña.
    6.  Introduzca una contraseña fuerte y única.
    7.  Guarde sus cambios.
    8.  Comunique la contraseña a su público objetivo.

### 2.3 Tabla de Referencia Rápida de Configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| **Gestionar Páginas CMS Protegidas** | Activar/Desactivar Protección | No / Sí (según sea necesario) | Controla si una página CMS específica requiere una contraseña para ser vista. |
| | Contraseña para Página CMS | (Vacío) / Contraseña fuerte y única | La cadena exacta que los clientes deben introducir para acceder al contenido protegido. |

## 3. Solución de Problemas del Comerciante y Preguntas Frecuentes (FAQ)

**P: He establecido una contraseña, pero la página sigue siendo visible sin ella. ¿Qué ocurre?**
R:

1.  **Verifique si la protección está activada:** Vaya a la pantalla "Gestionar páginas CMS protegidas" y asegúrese de que el interruptor "Activar protección" para esa página CMS específica esté configurado en "Sí".
2.  **Borre la caché de su navegador:** Su navegador podría estar mostrándole una versión en caché de la página. Intente borrar la caché de su navegador o abrir la página en una ventana de incógnito/privada.
3.  **Borre la caché de PrestaShop:** Vaya a **Parámetros avanzados > Rendimiento** en su Back Office y haga clic en "Borrar caché" en la esquina superior derecha. Esto asegura que PrestaShop esté sirviendo la última configuración.

**P: ¿Puedo tener diferentes contraseñas para diferentes páginas CMS?**
R: ¡Sí! Este módulo está diseñado exactamente para eso. Cada página CMS puede tener su propia contraseña única, lo que le permite crear múltiples niveles de contenido protegido.

**P: ¿Qué sucede si un cliente introduce una contraseña incorrecta?**
R: El módulo mostrará un mensaje de error (por ejemplo, "Contraseña incorrecta. Inténtelo de nuevo.") y el formulario de entrada de contraseña reaparecerá, permitiendo al cliente volver a introducir la contraseña.

**P: ¿Puedo personalizar la apariencia del formulario de entrada de contraseña?**
R: El módulo utiliza un estilo básico para el formulario de contraseña. Para una personalización avanzada, necesitaría un webmaster o desarrollador para modificar el archivo CSS del módulo (`css.css`) o anular su plantilla (`cms.tpl`).

**P: He actualizado mi tema de PrestaShop y ahora el formulario de contraseña se ve extraño. ¿Qué debo hacer?**
R: Los temas personalizados a veces tienen su propio estilo que puede entrar en conflicto con la visualización de los módulos.

1.  **Borre la caché de PrestaShop:** Siempre intente esto primero (**Parámetros avanzados > Rendimiento > Borrar caché**).
2.  **Contacte con el desarrollador de su tema:** Podrían tener instrucciones específicas para la compatibilidad del módulo.
3.  **Consulte a un webmaster:** Un desarrollador puede inspeccionar el CSS y HTML para identificar y resolver conflictos de estilo.

## 4. Guía para Desarrolladores y Webmasters (Arquitectura Técnica y Mapa de Código)

Esta sección es estrictamente para desarrolladores, webmasters de tiendas y agencias técnicas que mantienen o extienden la tienda.

### 4.1 Resumen de la Arquitectura

El módulo "Páginas CMS protegidas con contraseña" (`passcms`) funciona principalmente anulando el `CmsController` principal para interceptar las solicitudes de páginas CMS. Cuando se solicita una página CMS protegida, verifica si hay una contraseña válida en la sesión. Si no se encuentra una contraseña válida, renderiza un formulario de entrada de contraseña en lugar del contenido real de la CMS. El módulo utiliza un controlador de administración dedicado (`AdminPcmsController`) para gestionar la configuración de contraseñas para cada página CMS.

### 4.2 Controladores (`controllers/`)

-   **Controladores de Front-Office**:

    -   `passcms/override/controllers/front/CmsController.php`
        -   **Nombre de la clase y clase padre**: `CmsController` (anula el `CmsController` principal)
        -   **Responsabilidad**: Este es el núcleo de la funcionalidad del front-office. Intercepta el método `initContent()` del `CmsController` original. Comprueba si la página CMS solicitada (identificada por `id_cms`) está configurada como protegida con contraseña. Si lo está, y no hay una contraseña válida en la sesión, renderiza la plantilla `cms.tpl` con el formulario de entrada de contraseña. También maneja la solicitud POST para el envío de la contraseña, validándola contra la contraseña almacenada y estableciendo una variable de sesión al tener éxito.
    -   `passcms/override/controllers/front/index.php`
        -   **Nombre de la clase y clase padre**: No es una clase, típicamente un archivo vacío o una medida de seguridad básica para evitar la lista directa de directorios.
        -   **Responsabilidad**: Práctica estándar de PrestaShop para directorios `override`.
-   **Controladores de Administración (Back-Office)**:

    -   `passcms/controllers/admin/AdminPcmsController.php`
        -   **Nombre de la pestaña y entidad gestionada**: Gestiona la configuración de protección con contraseña para páginas CMS individuales. Este controlador extiende `ModuleAdminController` y proporciona la interfaz para listar páginas CMS y configurar sus contraseñas. Maneja las operaciones CRUD para la entidad `pcms` (aunque no se lista un `ObjectModel` explícito, es probable que interactúe directamente con `ps_configuration` o una tabla personalizada para el almacenamiento de contraseñas). Renderiza la vista de cuadrícula de las páginas CMS y el formulario para editar la configuración de contraseñas.
    -   `passcms/controllers/admin/index.php`
        -   **Nombre de la clase y clase padre**: No es una clase, típicamente un archivo vacío o una medida de seguridad básica para evitar la lista directa de directorios.
        -   **Responsabilidad**: Práctica estándar de PrestaShop para directorios de controladores.

### 4.3 Clases y Modelos Principales (`classes/`)

El dossier del módulo no indica clases personalizadas en el directorio `classes/`. Esto sugiere que el módulo probablemente almacena su configuración directamente en la tabla `ps_configuration`, utilizando claves como `PCMS_PASSWORD_ID_CMS_X` donde `X` es el `id_cms`, o podría usar una tabla personalizada que es gestionada directamente por el `AdminPcmsController` sin un `ObjectModel` dedicado.

### 4.4 Activos JavaScript (`views/js/`)

El dossier del módulo no indica archivos JavaScript personalizados. El envío de la contraseña probablemente se maneja a través de un formulario HTML POST estándar o un JS en línea simple si hay algún comportamiento dinámico presente.

### 4.5 Hojas de Estilo CSS (`views/css/`)

-   `passcms/css.css`
    -   **Alcance**: Estilo del cliente en el front-office.
    -   **Principales componentes de la interfaz de usuario y contenedores que estiliza**: Este archivo contiene el estilo básico para el formulario de entrada de contraseña que se muestra en las páginas CMS protegidas. Probablemente apunta a elementos como el contenedor del formulario, el campo de entrada y el botón de envío.
    -   **Selectores de clase CSS clave que los desarrolladores pueden anular**: Los desarrolladores pueden inspeccionar el HTML renderizado del formulario de contraseña para identificar clases específicas (por ejemplo, `.passcms-form`, `.passcms-input`, `.passcms-button`, `.passcms-error`) y anularlas en el archivo `custom.css` o `theme.css` de su tema para que coincidan con la marca de la tienda.

### 4.6 Estructura de Plantillas Smarty (`views/templates/`)

-   **Plantillas de administración (`views/templates/admin/`)**:

    -   `passcms/admin.tpl`
        -   **Propósito**: Esta plantilla probablemente se utiliza para la página de configuración principal del módulo, proporcionando el punto de entrada o información general, y potencialmente enlazando a la interfaz de gestión de `AdminPcmsController`.
    -   `passcms/views/templates/admin/script.tpl`
        -   **Propósito**: Esta plantilla podría contener JavaScript en línea o variables Smarty que se renderizan dentro del Back Office para que el `AdminPcmsController` maneje el comportamiento dinámico o el paso de datos.
-   **Plantillas de front-office (`views/templates/front/`)**:

    -   `passcms/views/templates/front/cms.tpl`
        -   **Propósito**: Esta es la plantilla crucial renderizada por el `CmsController` anulado cuando se accede a una página CMS protegida sin una contraseña válida. Contiene la estructura HTML para el formulario de entrada de contraseña, incluyendo el campo de entrada, el botón de envío y cualquier mensaje de error.

### 4.7 Esquema de Base de Datos y Mapa de Hooks

-   **Tablas de Base de Datos**:

    -   El módulo no crea explícitamente una tabla SQL personalizada según el dossier. Es muy probable que la configuración de la contraseña para cada página CMS se almacene en la tabla `ps_configuration` utilizando claves de configuración únicas, por ejemplo, `PCMS_PASSWORD_ID_CMS_X` donde `X` es el `id_cms`.
    -   `ps_configuration`: Almacena los valores de configuración del módulo, incluyendo potencialmente las contraseñas para cada página CMS.
-   **Tabla de Hooks Registrados**:
    El módulo opera principalmente a través de la anulación del controlador en lugar de los hooks tradicionales para su funcionalidad principal. Sin embargo, podría registrar algunos hooks estándar para la integración o visualización general del módulo.

    | Nombre del Hook | Momento de Ejecución | Propósito Técnico |
    | --- | --- | --- |
    | `displayBackOfficeHeader` | Se renderiza en la sección `<head>` de las páginas del Back Office. | Se utiliza para incluir CSS (`css.css`) o JS para la interfaz de `AdminPcmsController`. |
    | `displayHeader` | Se renderiza en la sección `<head>` de las páginas del front-office. | Podría usarse para incluir CSS (`css.css`) o JS del front-office si es necesario globalmente, aunque es más probable que se cargue condicionalmente mediante la anulación de `CmsController`. |
    | `actionFrontControllerSetMedia` | Se ejecuta cuando un controlador frontal establece sus activos multimedia. | Alternativa a `displayHeader` para cargar condicionalmente activos según el controlador actual. |

## 5. Soporte Oficial y Actualizaciones

Para las últimas actualizaciones, correcciones de errores y soporte oficial para el módulo "Páginas CMS protegidas con contraseña", consulte su cuenta de cliente en [MyPresta.eu](https://mypresta.eu). Nuestro equipo de soporte está disponible para ayudarle con cualquier problema o pregunta que pueda tener con respecto a la funcionalidad y compatibilidad del módulo.
"""
