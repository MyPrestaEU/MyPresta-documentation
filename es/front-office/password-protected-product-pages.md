---
title: "Páginas de producto protegidas con contraseña - Manual de comerciante y guía de configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop 'Páginas de producto protegidas con contraseña' de MyPresta.eu."
sidebar:
  label: "Páginas de producto protegidas con contraseña"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Password protected product pages en MyPresta.eu](https://mypresta.eu/modules/front-office-features/password-protected-product-pages.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/front-office/password-protected-product-pages/)
>
> ---


# Páginas de producto protegidas con contraseña

## 1. Requisitos y compatibilidad
- **Versiones de PrestaShop compatibles**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilidad con PHP**: PHP 7.1 - 8.5
- **Requisitos de alojamiento**: Las extensiones PHP estándar (cURL, JSON, OpenSSL) suelen ser suficientes.

## 2. Recorrido completo de configuración (Cada ajuste agrupado por pantalla)

### 2.1 Página de configuración del módulo (Back Office > Módulos > Configurar)
Esta es la pantalla de configuración principal del módulo, a la que se accede haciendo clic en "Configurar" después de la instalación o desde el Gestor de módulos.

- **Qué hace este ajuste:** Esta pantalla suele contener ajustes generales para el módulo, aunque para "Páginas de producto protegidas con contraseña", la gestión principal de contraseñas para productos específicos se maneja en una pantalla de administración dedicada (ver 4.2). Esta pantalla podría ofrecer opciones para la apariencia de la página de entrada de contraseña o el comportamiento general del módulo.
- **Efecto de cambiar este ajuste:** Cualquier cambio aquí afectaría cómo se comporta el mecanismo de protección por contraseña globalmente, o la apariencia predeterminada del formulario de entrada de contraseña.
- **Valor recomendado:** Los valores predeterminados suelen ser un buen punto de partida.
- **Escenario / ejemplo de comerciante:** Si hay una opción para personalizar el mensaje que se muestra en la página de la contraseña, podría cambiarlo de "Introducir contraseña" a "Por favor, introduzca su código de acceso VIP".

### 2.2 Pantalla de administración dedicada: Contraseñas de producto (Back Office > Catálogo > Contraseñas de producto)
Esta es la pantalla más importante para gestionar qué productos están protegidos con contraseña y cuáles son esas contraseñas. Encontrará este nuevo elemento de menú en **Catálogo** en su Back Office de PrestaShop.

- **Nombre de la pantalla y ubicación del menú:** **Catálogo > Contraseñas de producto**
- **Acciones y ajustes disponibles:**
    -   **Tabla de listado:** Esta pantalla muestra una lista de todos los productos que actualmente tienen una contraseña asignada. Normalmente verá columnas como:
        -   **Nombre del producto:** El nombre del producto que se está protegiendo.
        -   **ID del producto:** El identificador único del producto.
        -   **Contraseña:** La contraseña necesaria para acceder a la página del producto.
        -   **Acciones:** Botones para "Editar" o "Eliminar" la contraseña de un producto específico.
    -   **Añadir nueva contraseña:** Habrá un botón (por ejemplo, "Añadir nueva contraseña de producto" o un icono de más) para añadir una nueva entrada de protección por contraseña. Al hacer clic en él, normalmente se le presentará un formulario:
        -   **Selector de producto:** Un campo para buscar y seleccionar el producto que desea proteger. Podría ser un campo de autocompletar donde escribe el nombre del producto.
        -   **Campo de contraseña:** Un campo de entrada donde define la contraseña para ese producto específico.
    -   **Editar contraseña:** Al hacer clic en "Editar" junto a una entrada existente, puede cambiar la contraseña de ese producto o, potencialmente, cambiar el producto asociado.
    -   **Eliminar contraseña:** Al hacer clic en "Eliminar", se elimina la protección por contraseña de ese producto, haciéndolo accesible públicamente de nuevo.
- **Efecto de los cambios:**
    -   **Añadir una contraseña:** La página del producto seleccionado se protegerá inmediatamente con contraseña en el front office.
    -   **Cambiar una contraseña:** Los clientes deberán usar la nueva contraseña para acceder a la página del producto.
    -   **Eliminar una contraseña:** La página del producto volverá a ser accesible públicamente sin necesidad de contraseña.
- **Flujo de trabajo recomendado para la gestión diaria de la tienda:**
    1.  Para proteger un nuevo producto: Navegue a **Catálogo > Contraseñas de producto**, haga clic en "Añadir nueva contraseña de producto", seleccione su producto y establezca una contraseña fuerte y única.
    2.  Para actualizar una contraseña: Encuentre el producto en la lista, haga clic en "Editar" e introduzca la nueva contraseña.
    3.  Para eliminar la protección: Encuentre el producto en la lista y haga clic en "Eliminar".
    4.  Revise regularmente sus productos protegidos para asegurarse de que las contraseñas sigan siendo relevantes y seguras.

### 2.3 Tabla de referencia rápida de configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e impacto |
|---|---|---|---|
| Página de configuración del módulo | (Ajustes generales, si los hay) | (Predeterminado del módulo) | Comportamiento global o apariencia de la página de entrada de contraseña. |
| Catálogo > Contraseñas de producto | Añadir nueva contraseña de producto | N/A | Seleccione un producto y asigne una contraseña para restringir el acceso a su página. |
| Catálogo > Contraseñas de producto | Editar contraseña de producto | N/A | Modificar la contraseña de un producto ya protegido. |
| Catálogo > Contraseñas de producto | Eliminar contraseña de producto | N/A | Eliminar la protección por contraseña, haciendo que la página del producto vuelva a ser pública. |

## 3. Solución de problemas del comerciante y preguntas frecuentes (FAQ)

**P1: He establecido una contraseña, pero la página del producto sigue siendo pública. ¿Qué pasa?**
R1:
*   **Verifique la entrada de la contraseña:** Vuelva a comprobar en **Catálogo > Contraseñas de producto** que el producto está listado y la contraseña está configurada correctamente.
*   **Borrar caché:** PrestaShop utiliza caché. Vaya a **Parámetros avanzados > Rendimiento** y haga clic en "Borrar caché" (o "Borrar caché de Smarty" si está disponible). Esto asegura que su tienda esté cargando la última configuración.
*   **Estado del módulo:** Asegúrese de que el módulo "Páginas de producto protegidas con contraseña" esté habilitado en **Módulos > Gestor de módulos**.
*   **Estado del producto:** Asegúrese de que el producto en sí esté habilitado y visible en su catálogo.

**P2: ¿Puedo tener diferentes contraseñas para diferentes productos?**
R2: ¡Sí, absolutamente! El módulo está diseñado para esto. Puede asignar una contraseña única a cada producto individual que desee proteger a través de la pantalla **Catálogo > Contraseñas de producto**.

**P3: ¿Qué sucede si un cliente intenta acceder a una página de producto protegida directamente a través de su URL sin la contraseña?**
R3: Será redirigido a la página de entrada de contraseña. No podrá ver el contenido del producto hasta que introduzca la contraseña correcta.

**P4: ¿Cómo traduzco el texto de la página de entrada de contraseña (por ejemplo, "Introducir contraseña")?**
R4: Normalmente puede traducir los textos del módulo a través de la interfaz de traducción de PrestaShop. Vaya a **Internacional > Traducciones**, seleccione "Traducciones de módulos instalados", elija su tema y luego seleccione el módulo "Páginas de producto protegidas con contraseña". Debería encontrar las cadenas de texto editables allí.

**P5: ¿Funcionará este módulo con mi tema personalizado?**
R5: El módulo está diseñado para integrarse perfectamente con los temas estándar de PrestaShop. Sin embargo, los temas altamente personalizados podrían requerir pequeños ajustes de CSS para asegurar que el formulario de entrada de contraseña se vea perfecto. Si encuentra problemas de estilo, consulte a su webmaster o desarrollador de temas.

## 4. Guía para desarrolladores y webmasters (Arquitectura técnica y mapa de código)

Esta sección es estrictamente para desarrolladores, webmasters de tiendas y agencias técnicas que mantienen o extienden la tienda.

### 4.1 Resumen de la arquitectura
El módulo "Páginas de producto protegidas con contraseña" opera principalmente anulando el `ProductController` predeterminado para interceptar las solicitudes de productos protegidos. Utiliza un controlador de administración dedicado para gestionar las asociaciones producto-contraseña, que se almacenan en la base de datos. La lógica del front-office verifica una cookie de sesión válida que contiene la contraseña de un producto dado antes de renderizar la página del producto real.

### 4.2 Controladores (`controllers/`)

-   **Controladores de Front-Office**:
    *   `prodpswd/controllers/front/ProductPasswd.php`
        *   **Nombre de la clase y clase padre:** `ProductPasswdModuleFrontController` que extiende `ModuleFrontController`.
        *   **Responsabilidad:** Este controlador es probablemente responsable de renderizar el formulario de entrada de contraseña cuando se accede a un producto protegido. Maneja la solicitud POST cuando un usuario envía una contraseña, la valida contra la contraseña almacenada para el producto y establece una sesión o cookie al autenticarse con éxito para otorgar acceso. También podría manejar la redirección a la página del producto real.
    *   `prodpswd/override/controllers/front/ProductController.php`
        *   **Nombre de la clase y clase padre:** `ProductController` (anulado).
        *   **Responsabilidad:** Esta es una anulación crucial. Intercepta el método `init()` o `postProcess()` del `ProductController` central. Antes de que se cargue el contenido estándar de la página del producto, esta anulación verifica si el producto actual está protegido con contraseña y si el usuario ya ha proporcionado la contraseña correcta (por ejemplo, a través de una cookie de sesión). Si el producto está protegido y no se encuentra una contraseña válida, redirige al usuario al `ProductPasswdModuleFrontController` (o renderiza directamente su plantilla) para solicitar la contraseña.

-   **Controladores de administración de Back-Office**:
    *   `prodpswd/controllers/admin/AdminProdPasswordController.php`
        *   **Nombre de la pestaña y entidad gestionada:** Accesible a través de **Catálogo > Contraseñas de producto**. Gestiona las entidades `prodpassword` (ID de producto y contraseña asociada).
        *   **Responsabilidad:** Este es un `AdminController` estándar responsable de las operaciones CRUD (Crear, Leer, Actualizar, Eliminar) para las asociaciones producto-contraseña. Muestra la lista de productos protegidos, permite a los administradores añadir nuevas entradas de producto-contraseña, editar contraseñas existentes y eliminarlas. Probablemente utiliza `HelperList` para la vista de cuadrícula y `HelperForm` para los formularios de añadir/editar.
    *   `prodpswd/controllers/admin/index.php`
        *   **Responsabilidad:** Este archivo es típicamente un archivo `index.php` vacío colocado en subdirectorios de módulos de PrestaShop para evitar el listado de directorios, mejorando la seguridad. No contiene ninguna lógica de controlador funcional.

### 4.3 Clases y modelos principales (`classes/`)
El dossier del módulo no indica clases personalizadas en el directorio `classes/`. La entidad `prodpassword` es probablemente gestionada directamente por el `AdminProdPasswordController` utilizando una definición simple de `ObjectModel` dentro del archivo principal del módulo o el propio controlador, o podría estar interactuando directamente con `Configuration` o una tabla personalizada sin un `ObjectModel` dedicado. Dado que el `AdminProdPasswordController` gestiona una tabla `prodpassword`, es muy probable que haya un `ObjectModel` definido para ella, incluso si no está en una carpeta `classes/` separada.

### 4.4 Activos JavaScript (`views/js/`)
El dossier del módulo no indica archivos JavaScript personalizados. Se espera que el formulario de contraseña del front-office y la cuadrícula/formulario del back-office dependan del JS estándar de PrestaShop o de simples envíos de formularios HTML.

### 4.5 Hojas de estilo CSS (`views/css/`)
El dossier del módulo no indica archivos CSS personalizados. El estilo para la página de entrada de contraseña en el front office y los formularios de administración probablemente se heredará del tema activo de PrestaShop y los estilos del back-office.

### 4.6 Estructura de plantillas Smarty (`views/templates/`)

-   **Plantillas de hook (`views/templates/hook/`)**:
    *   No se enumeran plantillas de hook específicas, lo que sugiere que el módulo opera principalmente a través de anulaciones de controlador y plantillas dedicadas del front-office en lugar de inyectar contenido en hooks estándar.
-   **Plantillas de administración (`views/templates/admin/`)**:
    *   No se enumeran plantillas de administración específicas. El `AdminProdPasswordController` probablemente utiliza las plantillas estándar `HelperList` y `HelperForm` de PrestaShop para su interfaz.
-   **Plantillas de front-office (`views/templates/front/`)**:
    *   `prodpswd/views/templates/front/product.tpl`
        *   **Propósito:** Esta plantilla es probablemente el formulario de entrada de contraseña personalizado que se muestra a los clientes cuando intentan acceder a una página de producto protegida. Contiene la estructura HTML para el campo de entrada de contraseña, el botón de envío y cualquier mensaje adjunto (por ejemplo, "Introducir contraseña para ver este producto").
    *   `prodpswd/lib/searchTool/views/scripts.tpl`
        *   **Propósito:** Esta plantilla probablemente contiene lógica JavaScript o Smarty relacionada con una herramienta de búsqueda, posiblemente utilizada dentro de la configuración de administración para seleccionar productos a proteger. Podría incluir llamadas AJAX o capacidades de filtrado dinámico para la selección de productos.

### 4.7 Esquema de la base de datos y mapa de hooks

-   **Tablas de la base de datos**:
    *   `ps_prodpassword` (o similar): Se espera que esta tabla personalizada almacene el ID del producto (`id_product`) y la contraseña asociada (`password`) para cada producto protegido. Se crea durante el método `install()` del módulo.
    *   Registros de configuración en `ps_configuration`: Los ajustes generales del módulo (si los hay) se almacenarían aquí.

-   **Tabla de Hooks registrados**:

| Nombre del Hook | Momento de ejecución | Propósito técnico |
|---|---|---|
| `actionFrontControllerSetMedia` | Antes de que se carguen los medios (JS/CSS) de un controlador de front-office. | Potencialmente para cargar JS/CSS personalizado para el formulario de contraseña, aunque no se enumeran en el dossier. |
| `displayHeader` | En la sección `<head>` del front office. | Podría usarse para metaetiquetas o JS/CSS condicional, pero no se usa explícitamente para contenido. |
| `displayRightColumn` | En la columna derecha del front office. | No se usa directamente para la funcionalidad principal del módulo. |
| `displayLeftColumn` | En la columna izquierda del front office. | No se usa directamente para la funcionalidad principal del módulo. |
| `displayFooter` | En el pie de página del front office. | No se usa directamente para la funcionalidad principal del módulo. |
| `actionProductControllerSetMedia` | Después de que el `ProductController` haya establecido sus medios. | Podría usarse para inyectar JS/CSS específico para la página del producto, pero es poco probable dada la anulación. |
| `actionDispatcherBefore` | Antes de que se despache un controlador de front-office. | El `override/controllers/front/ProductController.php` actúa eficazmente en esta etapa para las páginas de productos. |
| `actionDispatcherAfter` | Después de que se haya despachado un controlador de front-office. | Menos probable para la funcionalidad principal de este módulo. |

El mecanismo principal de este módulo es la anulación del `ProductController`, que actúa como un hook implícito, interceptando las solicitudes antes de que los hooks estándar sean procesados para el contenido de la página del producto.

## 5. Soporte oficial y actualizaciones
Para las últimas actualizaciones, correcciones de errores y soporte oficial para el módulo "Páginas de producto protegidas con contraseña", consulte su cuenta de cliente en [MyPresta.eu](https://mypresta.eu/). Nuestro equipo de soporte está disponible para ayudarle con cualquier problema o pregunta que pueda tener.
"""
