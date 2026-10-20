---
title: "Páginas de categoría protegidas con contraseña - Manual de comerciante y guía de configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop 'Páginas de categoría protegidas con contraseña' de MyPresta.eu."
sidebar:
  label: "Páginas de categoría protegidas con contraseña - Manual de comerciante y guía de configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Password protected category pages en MyPresta.eu](https://mypresta.eu/modules/front-office-features/password-protected-category-pages.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/front-office/password-protected-category-pages/)
>
> ---


# Páginas de categoría protegidas con contraseña

## 1. Requisitos y compatibilidad

- **Versiones de PrestaShop compatibles**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilidad con PHP**: PHP 7.1 - 8.5
- **Requisitos de alojamiento**: Extensiones PHP estándar (cURL, JSON, OpenSSL).

## 2. Recorrido completo por la configuración (Cada ajuste agrupado por pantalla)

### 2.1 Página de configuración del módulo (Back Office > Módulos > Configurar)

Después de instalar el módulo, haga clic en "Configurar" para acceder a sus ajustes principales. Esta pantalla proporciona opciones generales de gestión del módulo.

-   **Qué hace este ajuste:** Esta sección normalmente incluye los ajustes estándar del módulo MyPresta.eu relacionados con las actualizaciones y las licencias. Asegura que su módulo esté actualizado y correctamente licenciado.
-   **Efecto de cambiar este ajuste:**
    -   *`mypresta_updates`*: Este ajuste controla si el módulo busca actualizaciones automáticamente. Mantenerlo habilitado asegura que se le notifique de nuevas versiones.
    -   *`update_` y `updatev_`*: Estos son ajustes internos utilizados por el módulo para gestionar las comprobaciones de actualización y la información de la versión. Generalmente no necesita interactuar con ellos directamente.
-   **Valor recomendado:** Mantenga `mypresta_updates` habilitado para recibir actualizaciones importantes y correcciones de errores.
-   **Escenario / ejemplo de comerciante:** Si desea asegurarse de que su módulo siempre tenga las últimas características y parches de seguridad, mantenga la comprobación de actualizaciones habilitada. Si tiene una tienda altamente personalizada y prefiere controlar manualmente las actualizaciones después de pruebas exhaustivas, podría deshabilitarlo, pero esto generalmente no se recomienda para la mayoría de los comerciantes.

### 2.2 Pantalla de administración dedicada: Contraseñas de categoría (Back Office > Catálogo > Contraseñas de categoría)

Esta es la pantalla de gestión principal para configurar y administrar contraseñas para sus categorías.

-   **Nombre de la pantalla y ubicación del menú:** Puede encontrar esta pantalla navegando a **Catálogo > Contraseñas de categoría** en el menú de su Back Office de PrestaShop.
-   **Acciones y ajustes disponibles:**
    -   **Lista de categorías:** Esta pantalla muestra una lista de todas sus categorías. Para cada categoría, verá si está actualmente protegida con contraseña y cuántas contraseñas se le han asignado.
    -   **Añadir/Editar contraseñas:** Para cada categoría, puede hacer clic en un botón "Editar" o "Gestionar contraseñas" (o un icono similar) para abrir una interfaz dedicada. Aquí puede:
        -   **Seleccionar una categoría:** Elija la categoría específica que desea proteger.
        -   **Añadir nueva contraseña:** Introduzca una nueva contraseña para la categoría seleccionada. Puede añadir varias contraseñas para una sola categoría. Esto es útil si desea dar diferentes códigos de acceso a diferentes grupos de clientes (por ejemplo, "VIP123" para clientes premium, "WHOLESALE456" para socios B2B).
        -   **Eliminar contraseña:** Eliminar contraseñas existentes.
        -   **Habilitar/Deshabilitar protección:** Puede haber un interruptor o casilla de verificación disponible para habilitar o deshabilitar rápidamente la protección con contraseña para una categoría sin eliminar todas sus contraseñas.
-   **Efecto de los cambios:**
    -   **Añadir una contraseña:** La categoría seleccionada se protegerá inmediatamente con contraseña en el front office. Los clientes deberán introducir una de las contraseñas asignadas para ver sus productos.
    -   **Eliminar una contraseña:** Esa contraseña específica ya no concederá acceso. Si era la única contraseña para una categoría, la categoría podría quedar desprotegida (dependiendo de la lógica exacta del módulo, es más seguro deshabilitar explícitamente la protección si desea que esté abierta).
    -   **Deshabilitar protección:** La categoría volverá a ser de acceso público, y los clientes verán sus productos sin necesidad de una contraseña.
-   **Flujo de trabajo recomendado para la gestión diaria de la tienda:**
    1.  Vaya a **Catálogo > Contraseñas de categoría**.
    2.  Identifique la categoría que desea proteger.
    3.  Haga clic en el icono "Gestionar contraseñas" o "Editar" junto a ella.
    4.  En la nueva pantalla, añada una o más contraseñas. Recuerde que cada contraseña que añada concederá acceso.
    5.  Guarde sus cambios.
    6.  Para eliminar la protección, elimine todas las contraseñas de esa categoría o utilice un interruptor "Habilitar/Deshabilitar" si está disponible.

### 2.3 Tabla de referencia rápida de configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e impacto |
| --- | --- | --- | --- |
| Página de configuración del módulo | `mypresta_updates` | Habilitado | Controla las comprobaciones automáticas de actualización del módulo. Mantener habilitado para las últimas características y seguridad. |
| Página de configuración del módulo | `update_`, `updatev_` | (Interno) | Ajustes internos para la gestión de actualizaciones. No se necesita interacción del comerciante. |
| Contraseñas de categoría (Catálogo > Contraseñas de categoría) | Lista de categorías | N/A | Resumen de todas las categorías y su estado de protección con contraseña. |
| Contraseñas de categoría (Catálogo > Contraseñas de categoría) | Añadir/Editar contraseñas | N/A | Permite añadir, editar o eliminar contraseñas para categorías específicas. Se admiten varias contraseñas por categoría. |
| Contraseñas de categoría (Catálogo > Contraseñas de categoría) | Habilitar/Deshabilitar protección | N/A | Activa o desactiva la protección con contraseña para una categoría. |

## 3. Solución de problemas del comerciante y preguntas frecuentes (FAQ)

**P1: He establecido una contraseña, pero la categoría sigue siendo visible sin ella. ¿Qué pasa?**
R1:

-   **Borrar caché:** La razón más común es el almacenamiento en caché. Vaya a **Parámetros avanzados > Rendimiento** en su Back Office de PrestaShop y haga clic en "Borrar caché" (o "Borrar caché de Smarty" y "Borrar caché" para todas las cachés).
-   **Verificar estado de la categoría:** Asegúrese de que la categoría en sí esté activa y visible en su tienda.
-   **Verificar entrada de contraseña:** Vuelva a comprobar que ha introducido y guardado correctamente la(s) contraseña(s) en la sección **Catálogo > Contraseñas de categoría**.
-   **Posición del módulo:** Asegúrese de que el módulo esté correctamente enganchado. Aunque el módulo lo gestiona automáticamente, si tiene temas muy personalizados, a veces los hooks pueden ser anulados.

**P2: ¿Puedo tener varias contraseñas para una categoría?**
R2: ¡Sí! Este módulo admite explícitamente un número ilimitado de contraseñas para una sola categoría. Esto es útil para dar diferentes códigos de acceso a diferentes grupos (por ejemplo, contraseña "VIP", contraseña "Mayorista").

**P3: ¿Qué sucede si un cliente intenta acceder a un producto directamente desde una categoría protegida a través de su URL?**
R3: Si un producto pertenece a una categoría protegida con contraseña, el acceso directo a la página del producto seguirá requiriendo la introducción previa de la contraseña de la categoría. El módulo garantiza que se respete el contexto de la categoría, impidiendo el acceso directo a los productos dentro de una categoría segura sin autenticación.

**P4: ¿Cómo elimino la protección con contraseña de una categoría?**
R4: Vaya a **Catálogo > Contraseñas de categoría**. Busque la categoría que desea desproteger. Puede eliminar todas las contraseñas asociadas a esa categoría, o si hay un interruptor explícito de "Habilitar/Deshabilitar" para la protección de la categoría, úselo. Una vez que se eliminen todas las contraseñas o se desactive la protección, la categoría volverá a ser de acceso público.

**P5: El formulario de contraseña no se ve bien en mi tema personalizado. ¿Cómo puedo solucionarlo?**
R5: El módulo utiliza plantillas y CSS estándar de PrestaShop. Si no se ve bien, es probable que sea un conflicto de CSS con su tema personalizado.

-   **Inspeccionar elemento:** Utilice las herramientas de desarrollo de su navegador (F12) para inspeccionar los elementos del formulario de contraseña. Busque reglas CSS conflictivas de su tema.
-   **CSS personalizado:** Puede añadir CSS personalizado al archivo `custom.css` de su tema (o similar) para anular el estilo predeterminado del módulo y hacer que coincida con su tema.
-   **Contactar con soporte:** Si no se siente cómodo con CSS, póngase en contacto con el desarrollador de su tema o con el soporte de MyPresta.eu para obtener ayuda.

## 4. Guía para desarrolladores y webmasters (Arquitectura técnica y mapa de código)

### 4.1 Resumen de la arquitectura

El módulo "Páginas de categoría protegidas con contraseña" se integra en la arquitectura MVC de PrestaShop principalmente anulando el `CategoryController` principal para interceptar las solicitudes a las páginas de categoría. Utiliza un controlador de administración dedicado (`AdminCatPasswordController`) para gestionar las asociaciones categoría-contraseña, almacenándolas en una tabla de base de datos personalizada. La visualización en el front-office se gestiona mediante una plantilla Smarty personalizada para el formulario de entrada de contraseña.

### 4.2 Controladores (`controllers/`)

-   **Controladores de Front-Office**:

    -   `catpswd/override/controllers/front/listing/CategoryController.php`
        -   **Nombre de la clase:** `CategoryController` (anula el `CategoryController` principal de PrestaShop)
        -   **Clase padre:** `CategoryControllerCore`
        -   **Responsabilidad:** Esta anulación es el núcleo de la funcionalidad de front-office del módulo. Intercepta las solicitudes a las páginas de categoría. Antes de mostrar el contenido real de la categoría, comprueba si la categoría está protegida con contraseña. Si lo está, y el usuario aún no ha introducido la contraseña correcta (o la sesión ha caducado), renderiza el formulario de entrada de contraseña (`category.tpl`) en lugar de la página de categoría estándar. Gestiona el envío del formulario de contraseña, valida la contraseña introducida y establece una variable de sesión tras una autenticación exitosa.
    -   `catpswd/override/controllers/front/listing/index.php`
        -   **Responsabilidad:** Este es un archivo `index.php` estándar de PrestaShop dentro de un directorio de anulación, típicamente utilizado para evitar la lista directa de directorios y asegurar la carga correcta del módulo. No contiene lógica de controlador activa en sí mismo.
-   **Controladores de administración de Back-Office**:

    -   `catpswd/controllers/admin/AdminCatPasswordController.php`
        -   **Nombre de la pestaña:** "Contraseñas de categoría" (bajo el menú Catálogo)
        -   **Entidad gestionada:** `CatPassword` (aunque no se lista explícitamente ningún `ObjectModel`, este controlador gestiona las relaciones categoría-contraseña, probablemente interactuando directamente con la base de datos o una clase auxiliar).
        -   **Responsabilidad:** Este controlador proporciona la interfaz en el Back Office de PrestaShop para que los administradores gestionen la protección con contraseña de las categorías. Lista las categorías, permite añadir varias contraseñas a una categoría y eliminarlas. Gestiona las operaciones CRUD para los datos de categoría-contraseña.
    -   `catpswd/controllers/admin/index.php`
        -   **Responsabilidad:** Similar al `index.php` del front-office, este archivo evita la lista directa de directorios para el directorio de controladores de administración.

### 4.3 Clases y modelos principales (`classes/`)

El dossier del módulo indica que no hay clases explícitas en el directorio `classes/`. Esto sugiere que el `AdminCatPasswordController` probablemente maneja las interacciones con la base de datos directamente o utiliza una función auxiliar simple dentro del archivo principal del módulo (`catpswd.php`) para la gestión de datos, en lugar de un `ObjectModel` dedicado.

### 4.4 Activos JavaScript (`views/js/`)

El dossier del módulo indica que no hay archivos JavaScript específicos. El envío y la validación de la contraseña probablemente se manejan mediante el envío de formularios HTML estándar y el procesamiento del lado del servidor dentro de la anulación del `CategoryController`.

### 4.5 Hojas de estilo CSS (`views/css/`)

El dossier del módulo indica que no hay archivos CSS específicos. El estilo del formulario de entrada de contraseña es probablemente mínimo y se basa en el estilo base del tema predeterminado de PrestaShop. Los desarrolladores que deseen personalizar la apariencia deben apuntar a los elementos del formulario dentro de la plantilla `category.tpl` utilizando el CSS personalizado de su tema.

### 4.6 Estructura de la plantilla Smarty (`views/templates/`)

-   **Plantillas de hook (`views/templates/hook/`)**:
    -   `catpswd/lib/searchTool/views/scripts.tpl`
        -   **Hook:** Probablemente utilizado en `displayHeader` o `actionAdminControllerSetMedia` (si contiene inclusiones de JS/CSS para una herramienta de búsqueda).
        -   **Salida:** Esta plantilla probablemente contiene inclusiones de JavaScript o CSS, posiblemente para una utilidad de búsqueda utilizada dentro de la interfaz de administración del módulo o para la funcionalidad del front-office.
-   **Plantillas de front-office (`views/templates/front/`)**:
    -   `catpswd/views/templates/front/category.tpl`
        -   **Propósito:** Esta es la plantilla renderizada por el `CategoryController` anulado cuando se accede a una categoría protegida con contraseña sin autenticación. Muestra el formulario de entrada de contraseña al cliente. Normalmente incluye campos para la contraseña, un botón de envío y mensajes para intentos exitosos o fallidos.

### 4.7 Esquema de la base de datos y mapa de hooks

-   **Tablas de la base de datos**:
    -   `ps_catpassword`: Esta tabla personalizada es creada por el módulo durante la instalación. Almacena las asociaciones entre los ID de categoría y sus respectivas contraseñas.
        -   **Columnas (esperadas):** `id_catpassword` (clave primaria), `id_category` (clave foránea a `ps_category`), `password` (la cadena de contraseña en texto plano o hash).
-   **Tabla de Hooks registrados**:

| Nombre del Hook | Momento de ejecución | Propósito técnico |
| --- | --- | --- |
| `displayHeader` | En la sección `<head>` de cada página del front-office. | Potencialmente utilizado para incluir activos CSS o JS globales, o para establecer metaetiquetas relacionadas con la funcionalidad del módulo. |
| `actionAdminControllerSetMedia` | Cuando se carga un controlador de administración y se están configurando sus medios (JS/CSS). | Utilizado por el módulo para inyectar sus archivos JavaScript y CSS específicos en el Back Office para el `AdminCatPasswordController` u otras páginas de administración donde se necesitan los activos del módulo. |

## 5. Soporte oficial y actualizaciones

Para las últimas actualizaciones del módulo, correcciones de errores y soporte profesional, consulte su cuenta de cliente en [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nuestro equipo se dedica a proporcionar asistencia oportuna y garantizar que su módulo funcione sin problemas.
