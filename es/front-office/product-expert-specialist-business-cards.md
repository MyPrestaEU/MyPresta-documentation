---
title: "Experto de producto - Tarjetas de visita de especialista - Manual de comerciante y guía de configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop 'Experto de producto - Tarjetas de visita de especialista' de MyPresta.eu."
sidebar:
  label: "Experto de producto - Tarjetas de visita de especialista - Manual de comerciante y guía de configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Product expert - Specialist Business Cards en MyPresta.eu](https://mypresta.eu/modules/front-office-features/product-expert-specialist-business-cards.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/front-office/product-expert-specialist-business-cards/)
>
> ---


# Experto de producto - Tarjetas de visita de especialista

## 1. Requisitos y compatibilidad

Para garantizar el buen funcionamiento del módulo "Experto de producto - Tarjetas de visita de especialista", revise los siguientes requisitos:

- **Versiones de PrestaShop compatibles**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilidad con PHP**: PHP 7.1 - 8.5
- **Requisitos de alojamiento**: Se requieren extensiones PHP estándar como cURL, JSON y OpenSSL, y suelen estar disponibles en la mayoría de los entornos de alojamiento modernos. Normalmente no se necesitan configuraciones especiales del servidor.

## 2. Recorrido completo de configuración (Cada ajuste agrupado por pantalla)

El módulo "Experto de producto - Tarjetas de visita de especialista" ofrece amplias opciones de configuración en varias pantallas de su Back Office de PrestaShop.

### 2.1 Página de configuración del módulo (Back Office > Módulos > Gestor de módulos > Configurar Experto de producto - Tarjetas de visita de especialista)

Esta es la pantalla de configuración principal para los ajustes generales del módulo, accesible directamente después de la instalación o haciendo clic en "Configurar" desde el Gestor de módulos.

-   **Activar/Desactivar Módulo:**

    -   **Qué hace este ajuste:** Este es el interruptor maestro para la funcionalidad del módulo.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando está activado:* Las características del módulo (tarjetas de expertos, asignaciones) estarán activas en su front office.
        -   *Cuando está desactivado:* Toda la funcionalidad del módulo estará oculta en el front office y las tarjetas de expertos no aparecerán.
    -   **Valor recomendado:** SÍ (a menos que lo esté desactivando temporalmente para mantenimiento).
    -   **Escenario / ejemplo de comerciante:** Podría desactivarlo si está realizando una actualización importante del tema y quiere asegurarse de que no haya conflictos, luego volver a activarlo una vez que las pruebas estén completas.
-   **Mostrar expertos en la página de producto:**

    -   **Qué hace este ajuste:** Controla si las tarjetas de expertos se muestran en las páginas de productos individuales.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando está activado:* Los expertos asignados a productos, categorías, marcas o proveedores aparecerán en las páginas de productos relevantes.
        -   *Cuando está desactivado:* Los expertos no se mostrarán en las páginas de productos, independientemente de sus asignaciones.
    -   **Valor recomendado:** SÍ (esta es una característica principal del módulo).
    -   **Escenario / ejemplo de comerciante:** Si solo desea usar expertos para consultas B2B en una página dedicada y no directamente en los listados de productos, podría desactivar esto.
-   **Mostrar expertos en el hook:**

    -   **Qué hace este ajuste:** Le permite seleccionar un hook específico de PrestaShop donde se mostrarán las tarjetas de expertos. Los hooks comunes incluyen `displayProductButtons`, `displayProductExtraContent`, `displayRightColumn`, `displayLeftColumn`, `displayFooter`.
    -   **Efecto de cambiar este ajuste:** Las tarjetas de expertos se renderizarán en la ubicación elegida en sus páginas de productos u otras páginas donde el hook esté activo.
    -   **Valor recomendado:** `displayProductExtraContent` o `displayProductButtons` suelen ser buenas opciones para las páginas de productos, ya que suelen ser prominentes. Experimente para encontrar el mejor ajuste para su tema.
    -   **Escenario / ejemplo de comerciante:** Si su tema tiene una pestaña o sección dedicada de "contenido extra", `displayProductExtraContent` podría ser ideal. Si desea expertos cerca del botón "Añadir al carrito", `displayProductButtons` podría funcionar.
-   **Activar formulario de contacto:**

    -   **Qué hace este ajuste:** Determina si hay un formulario de contacto disponible para que los clientes envíen mensajes directamente a los expertos.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando está activado:* Aparecerá un botón o enlace "Contactar experto" en la tarjeta del experto, abriendo un formulario para que los clientes envíen un mensaje.
        -   *Cuando está desactivado:* La opción de formulario de contacto se eliminará de las tarjetas de expertos.
    -   **Valor recomendado:** SÍ (altamente recomendado para la interacción con el cliente).
    -   **Escenario / ejemplo de comerciante:** Habilitar esto permite a los clientes hacer preguntas específicas sobre un producto directamente al experto, lo que lleva a compras más informadas.
-   **Cumplimiento GDPR para el formulario de contacto:**

    -   **Qué hace este ajuste:** Si el formulario de contacto está habilitado, este ajuste añade una casilla de verificación para que los clientes den su consentimiento al procesamiento de datos, crucial para el cumplimiento del GDPR.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando está activado:* Aparecerá una casilla de verificación obligatoria en el formulario de contacto, que requiere el consentimiento del cliente antes de enviar un mensaje.
        -   *Cuando está desactivado:* No se mostrará ninguna casilla de verificación de consentimiento GDPR.
    -   **Valor recomendado:** SÍ (esencial para el cumplimiento legal en muchas regiones).
    -   **Escenario / ejemplo de comerciante:** Siempre habilite esto si su público objetivo se encuentra en la UE o en cualquier región con leyes de protección de datos similares.
-   **Diseño predeterminado de la tarjeta de experto:**

    -   **Qué hace este ajuste:** Le permite seleccionar un diseño predefinido o personalizado para cómo se muestran las tarjetas de visita de expertos individuales. Esto incluye opciones para la ubicación de la foto, la alineación del texto y el diseño general de la tarjeta.
    -   **Efecto de cambiar este ajuste:** Cambia la apariencia visual de todas las tarjetas de expertos en su tienda, a menos que se anule por la configuración de un experto específico.
    -   **Valor recomendado:** Elija un diseño que mejor se adapte a la estética de su tienda. Puede previsualizar diferentes opciones.
    -   **Escenario / ejemplo de comerciante:** Podría elegir un diseño "Moderno" para una tienda elegante y minimalista, o un diseño "Clásico" para una sensación más tradicional.
-   **Diseño predeterminado de la lista de expertos:**

    -   **Qué hace este ajuste:** Determina cómo se organizan varias tarjetas de expertos cuando se muestra más de un experto (por ejemplo, en una cuadrícula, lista o carrusel).
    -   **Efecto de cambiar este ajuste:** Controla la presentación general de múltiples expertos en una página.
    -   **Valor recomendado:** "Cuadrícula" para una visualización compacta, "Carrusel" para ahorrar espacio y una navegación interactiva, o "Lista" para una vista más detallada y apilada.
    -   **Escenario / ejemplo de comerciante:** Si tiene muchos expertos para una categoría, un "Carrusel" puede ahorrar espacio. Si solo tiene uno o dos, una "Cuadrícula" podría verse más limpia.
-   **Mostrar herramienta de búsqueda de expertos:**

    -   **Qué hace este ajuste:** Habilita una barra de búsqueda que permite a los clientes encontrar expertos por nombre o especialidad.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando está activado:* Aparecerá un campo de entrada de búsqueda, generalmente cerca de las tarjetas de expertos, permitiendo a los clientes filtrar expertos.
        -   *Cuando está desactivado:* La herramienta de búsqueda de expertos no será visible.
    -   **Valor recomendado:** SÍ (mejora la usabilidad, especialmente con muchos expertos).
    -   **Escenario / ejemplo de comerciante:** Si tiene un gran equipo de especialistas, habilitar la herramienta de búsqueda ayuda a los clientes a encontrar rápidamente a la persona adecuada.
-   **Hook de la herramienta de búsqueda de expertos:**

    -   **Qué hace este ajuste:** Especifica dónde se mostrará la herramienta de búsqueda de expertos en su front office.
    -   **Efecto de cambiar este ajuste:** La barra de búsqueda aparecerá en la ubicación del hook elegido.
    -   **Valor recomendado:** `displayTop` o `displayNav` para visibilidad global, o `displayLeftColumn`/`displayRightColumn` si desea que esté junto a otros filtros.
    -   **Escenario / ejemplo de comerciante:** Colocarlo en `displayTop` lo hace fácilmente accesible desde cualquier página, similar a una búsqueda de productos.

### 2.2 Pantalla de administración dedicada: Expertos (Back Office > Experto de producto > Expertos)

Esta pantalla es donde gestiona los perfiles de expertos individuales, crea nuevos expertos y edita los existentes.

-   **Nombre de la pantalla y ubicación del menú:** **Experto de producto > Expertos**
-   **Acciones y configuraciones disponibles:**

    -   **Lista de expertos (vista de cuadrícula):** Muestra una tabla de todos sus expertos creados. Puede ver su nombre, rol, estado (activo/inactivo) y acciones como "Editar" o "Eliminar".
    -   **Botón "Añadir nuevo experto":** Al hacer clic en este botón, se accede a un formulario para crear un nuevo perfil de experto.
    -   **Acciones de edición/eliminación:** Para cada experto de la lista, puede hacer clic en "Editar" para modificar sus detalles o en "Eliminar" para eliminarlos.
    -   **Acciones masivas:** Le permite seleccionar varios expertos y realizar acciones como "Activar", "Desactivar" o "Eliminar" simultáneamente.
-   **Formulario de creación/edición de expertos:**

    -   **Nombre:** El nombre completo de su experto.
    -   **Rol/Título:** Su título o rol profesional (por ejemplo, "Gerente de ventas senior", "Especialista en soporte técnico", "Asesor de moda").
    -   **Biografía corta:** Una breve descripción de su experiencia o antecedentes. Esto ayuda a los clientes a comprender sus cualificaciones.
    -   **Foto:** Suba una foto profesional del experto. Esto es crucial para generar confianza y conexión personal.
    -   **Enlaces de contacto:**
        -   **Correo electrónico:** Dirección de correo electrónico del experto.
        -   **Teléfono:** Número de teléfono del experto.
        -   **WhatsApp:** Número de WhatsApp (generará un enlace de chat directo).
        -   **LinkedIn:** Enlace a su perfil de LinkedIn.
        -   **Otros enlaces personalizados:** Puede añadir enlaces personalizados adicionales con iconos (por ejemplo, un enlace a su blog personal, un portfolio de productos específico).
    -   **Activo:** Un interruptor para activar o desactivar al experto.
        -   *Cuando está activado:* El experto estará disponible para asignación y visualización.
        -   *Cuando está desactivado:* El experto no aparecerá en el front office, incluso si está asignado.
    -   **Anulación del diseño de la tarjeta de experto:** Le permite seleccionar un diseño de tarjeta específico para *este experto individual*, anulando el valor predeterminado global establecido en la configuración del módulo. Esto es útil para destacar a ciertos expertos o para que coincidan con su marca personal.
    -   **Asignaciones (Productos, Categorías, Marcas, Proveedores):** Aquí es donde vincula a los expertos con entidades específicas de la tienda.
        -   **Productos:** Busque y seleccione productos individuales con los que este experto esté asociado.
        -   **Categorías:** Seleccione las categorías donde la tarjeta de este experto debe aparecer en los productos dentro de esas categorías.
        -   **Marcas:** Seleccione las marcas específicas en las que este experto se especializa.
        -   **Proveedores:** Seleccione los proveedores sobre cuyos productos este experto puede asesorar.
        -   *Efecto de los cambios:* Cuando un cliente ve un producto que coincide con cualquiera de estas asignaciones, se mostrará la tarjeta del experto. Si se asignan varios expertos, se mostrarán todos los expertos relevantes según el diseño de la lista.
-   **Efecto de los cambios:**

    -   Añadir un nuevo experto lo hace disponible para su asignación a productos, categorías, etc.
    -   Editar un experto actualiza su información mostrada y sus datos de contacto en toda la tienda.
    -   Eliminar un experto lo elimina a él y a sus asignaciones de su tienda.
    -   Cambiar las asignaciones afecta inmediatamente qué tarjetas de expertos aparecen en qué páginas de productos.
-   **Flujo de trabajo recomendado para la gestión diaria de la tienda:**

    1.  **Crear nuevos expertos:** Cuando un nuevo miembro del equipo se une o se necesita una nueva especialización, cree su perfil aquí.
    2.  **Asignar expertos:** Revise regularmente su catálogo de productos y asigne expertos relevantes a nuevos productos, categorías o marcas.
    3.  **Actualizar perfiles:** Mantenga actualizadas las fotos, biografías y datos de contacto de los expertos.
    4.  **Desactivar/Reactivar:** Utilice el interruptor "Activo" para ocultar temporalmente a un experto (por ejemplo, si está de baja) sin eliminar su perfil.

### 2.3 Tabla de referencia rápida de configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| **Configuración del módulo** | Activar/Desactivar Módulo | SÍ | Interruptor maestro para la funcionalidad del módulo. |
| | Mostrar expertos en la página de producto | SÍ | Mostrar tarjetas de expertos en las páginas de productos. |
| | Mostrar expertos en el hook | `displayProductExtraContent` | Elija dónde aparecen las tarjetas de expertos en las páginas de productos. |
| | Activar formulario de contacto | SÍ | Permitir a los clientes enviar mensajes directamente a los expertos. |
| | Cumplimiento GDPR para el formulario de contacto | SÍ | Añadir casilla de verificación de consentimiento al formulario de contacto. |
| | Diseño predeterminado de la tarjeta de experto | (Elegir según el tema) | Estilo visual de las tarjetas de expertos individuales. |
| | Diseño predeterminado de la lista de expertos | Cuadrícula / Carrusel | Cómo se organizan varias tarjetas de expertos. |
| | Mostrar herramienta de búsqueda de expertos | SÍ | Habilitar una barra de búsqueda para expertos. |
| | Hook de la herramienta de búsqueda de expertos | `displayTop` / `displayNav` | Dónde aparece la herramienta de búsqueda de expertos. |
| **Experto de producto > Expertos** | Añadir nuevo experto | N/A | Crear nuevos perfiles de expertos. |
| | Editar experto | N/A | Modificar detalles del experto (nombre, rol, biografía, foto, contactos). |
| | Activo (Estado del experto) | SÍ | Activar/desactivar la visibilidad de expertos individuales. |
| | Anulación del diseño de la tarjeta de experto | N/A | Anular el diseño global de la tarjeta para un experto específico. |
| | Asignar a productos | N/A | Vincular experto a productos específicos. |
| | Asignar a categorías | N/A | Vincular experto a productos dentro de categorías específicas. |
| | Asignar a marcas | N/A | Vincular experto a productos de marcas específicas. |
| | Asignar a proveedores | N/A | Vincular experto a productos de proveedores específicos. |

## 3. Solución de problemas del comerciante y preguntas frecuentes (FAQ)

Aquí tiene algunas preguntas comunes y consejos para la solución de problemas para los propietarios de tiendas que utilizan el módulo "Experto de producto - Tarjetas de visita de especialista":

**P1: Mis tarjetas de experto no aparecen en la página del producto.**

-   **R:** Primero, verifique si el módulo está **activado** en **Módulos > Gestor de módulos**.
-   **R:** A continuación, vaya a la página de configuración del módulo y asegúrese de que "Mostrar expertos en la página de producto" esté configurado en **SÍ**.
-   **R:** Verifique que realmente haya **asignado** un experto al producto específico, su categoría, marca o proveedor en **Experto de producto > Expertos > [Editar experto] > Asignaciones**.
-   **R:** Verifique el interruptor "Activo" para el experto individual en **Experto de producto > Expertos**. Si está inactivo, no se mostrará.
-   **R:** Borre la caché de su PrestaShop: Vaya a **Parámetros avanzados > Rendimiento**, luego haga clic en "Borrar caché" en la esquina superior derecha. A veces, el contenido antiguo en caché impide que aparezcan nuevos elementos del módulo.

**P2: Las tarjetas de experto se ven extrañas o no coinciden con el diseño de mi tema.**

-   **R:** El módulo proporciona un "Diseño predeterminado de la tarjeta de experto" y un "Diseño predeterminado de la lista de expertos" en su configuración. Experimente con diferentes opciones para ver cuál se integra mejor con su tema.
-   **R:** Si tiene un tema personalizado, podría tener CSS específico que entre en conflicto con el estilo del módulo. Es posible que necesite un desarrollador web para inspeccionar el CSS y realizar pequeños ajustes.
-   **R:** Asegúrese de que su tema esté actualizado. Los temas desactualizados a veces pueden causar problemas de visualización con módulos más nuevos.

**P3: El formulario de contacto no envía correos electrónicos.**

-   **R:** Primero, asegúrese de que "Activar formulario de contacto" esté configurado en **SÍ** en la configuración del módulo.
-   **R:** Verifique que la dirección de correo electrónico del experto esté correctamente introducida en su perfil (**Experto de producto > Expertos > [Editar experto]**).
-   **R:** Verifique la configuración de correo electrónico de su PrestaShop (**Parámetros avanzados > Correo electrónico**). Envíe un correo electrónico de prueba desde PrestaShop para asegurarse de que la configuración de correo electrónico de su tienda funciona correctamente. Si PrestaShop no puede enviar correos electrónicos, el módulo tampoco podrá.
-   **R:** Verifique los registros de correo de su servidor en busca de errores. Esto podría requerir la asistencia de su proveedor de alojamiento.

**P4: ¿Cómo traduzco el texto del módulo a otros idiomas?**

-   **R:** Vaya a **Internacional > Traducciones** en su Back Office de PrestaShop.
-   **R:** Seleccione "Traducciones de módulos instalados", elija su tema y luego seleccione el módulo "Experto de producto - Tarjetas de visita de especialista".
-   **R:** Luego puede traducir todas las cadenas del módulo a los idiomas deseados. Recuerde guardar sus cambios.

**P5: Quiero mostrar expertos en una ubicación diferente a los hooks disponibles.**

-   **R:** El módulo proporciona una selección de hooks estándar de PrestaShop. Si necesita mostrar expertos en una ubicación muy específica y no estándar (por ejemplo, dentro de una pestaña personalizada o una sección única de la plantilla de su página de producto), esto requerirá un desarrollo de tema personalizado. Un desarrollador web necesitaría llamar manualmente a la función de hook del módulo directamente en los archivos `.tpl` de su tema.

## 4. Guía para desarrolladores y webmasters (Arquitectura técnica y mapa de código)

Esta sección proporciona una inmersión profunda en la arquitectura técnica y la base de código del módulo "Experto de producto - Tarjetas de visita de especialista", destinada a desarrolladores, webmasters y agencias técnicas.

### 4.1 Visión general de la arquitectura

El módulo "Experto de producto - Tarjetas de visita de especialista" sigue un patrón MVC (Modelo-Vista-Controlador) estándar de PrestaShop, aprovechando en gran medida `ObjectModel` para la persistencia de datos. Introduce controladores de administración personalizados para gestionar expertos y sus asignaciones, y controladores frontales para interacciones AJAX y la visualización de información de expertos. El módulo utiliza una sólida estructura de clases para gestionar los diseños de tarjetas de expertos, los estilos y la lógica de presentación, lo que permite una alta personalización. Se integra con varios hooks de PrestaShop para inyectar su contenido dinámicamente en el front office.

### 4.2 Controladores (`controllers/`)

#### Controladores del Front-Office

-   `controllers/front/ajax.php`
    -   **Nombre de la clase:** `ProductexpertAjaxModuleFrontController` (extiende `ModuleFrontController`)
    -   **Responsabilidad:** Maneja las solicitudes AJAX del front office. Esto típicamente incluye el procesamiento de los envíos del formulario de contacto del experto, la carga dinámica de datos del experto o cualquier otro elemento interactivo que requiera comunicación con el servidor sin una recarga completa de la página. Devuelve respuestas JSON.
-   `controllers/front/index.php`
    -   **Nombre de la clase:** `ProductexpertIndexModuleFrontController` (extiende `ModuleFrontController`)
    -   **Responsabilidad:** Un controlador frontal de marcador de posición o predeterminado. En muchos módulos, esto podría manejar una página de módulo dedicada si existe, o simplemente redirigir si su función principal es a través de hooks o AJAX. Para este módulo, su papel principal es probablemente mínimo, con `ajax.php` manejando la mayoría de las interacciones del front-end.

#### Controladores de administración del Back-Office

-   `controllers/admin/AdminProductExpertController.php`
    -   **Nombre de la clase:** `AdminProductExpertController` (extiende `ModuleAdminController`)
    -   **Nombre de la pestaña:** "Expertos" bajo el menú "Experto de producto".
    -   **Entidad gestionada:** `ProductExpertExpert` (a través de `classes/ProductExpertExpert.php`).
    -   **Responsabilidad:** Este es el controlador de administración principal para gestionar perfiles de expertos individuales. Maneja la lista de expertos (usando `HelperList`) y los formularios de creación/edición de expertos (usando `HelperForm`). Gestiona las operaciones CRUD para los datos de los expertos, incluyendo su nombre, rol, biografía, foto, enlaces de contacto y, lo que es más importante, sus asignaciones a productos, categorías, marcas y proveedores. También gestiona las anulaciones de diseño para las tarjetas de expertos individuales.
-   `controllers/admin/index.php`
    -   **Nombre de la clase:** (Sin clase específica, a menudo una redirección o medida de seguridad)
    -   **Responsabilidad:** Este archivo es típicamente una medida de seguridad para evitar la lista o el acceso directo al directorio. A menudo contiene un simple `header('Location: ../../index.php'); exit;` o similar para redirigir al panel de administración principal. No gestiona una entidad o formulario específico.

### 4.3 Clases y modelos principales (`classes/`)

Este módulo tiene un rico conjunto de clases para gestionar sus complejas características, especialmente en torno a los diseños y configuraciones de las tarjetas de expertos.

-   `classes/ProductExpertExpert.php`
    -   **Tabla de base de datos:** `ps_productexpert_expert`
    -   **Extiende:** `ObjectModel`
    -   **Campos `$definition`:** Define el esquema para los perfiles de expertos (id\_expert, name, role, bio, photo\_id, active, date\_add, date\_upd, layout\_preset\_id). Maneja campos multi-idioma si corresponde.
    -   **Métodos públicos clave:** Métodos para guardar, recuperar y eliminar datos de expertos. Incluye lógica para manejar cargas de fotos y asociaciones.
-   `classes/ProductExpertExpertLinks.php`
    -   **Tabla de base de datos:** `ps_productexpert_expert_link`
    -   **Extiende:** `ObjectModel`
    -   **Campos `$definition`:** Define el esquema para los enlaces de contacto de expertos (id\_expert\_link, id\_expert, type, value, icon, position).
    -   **Métodos públicos clave:** Gestiona los diversos enlaces de contacto (correo electrónico, teléfono, WhatsApp, LinkedIn, personalizados) asociados con un experto.
-   `classes/ProductExpertExpertPhoto.php`
    -   **Tabla de base de datos:** `ps_productexpert_expert_photo`
    -   **Extiende:** `ObjectModel`
    -   **Campos `$definition`:** Gestiona los detalles de la foto del experto (id\_photo, filename, mime\_type, size).
    -   **Métodos públicos clave:** Maneja el almacenamiento y la recuperación de imágenes de perfil de expertos.
-   `classes/ProductExpertConfig.php`
    -   **Tabla de base de datos:** `ps_configuration` (almacena valores de configuración)
    -   **Extiende:** (Probablemente no `ObjectModel`, sino una clase de utilidad)
    -   **Métodos públicos clave:** Proporciona métodos estáticos para obtener y establecer valores de configuración específicos del módulo (por ejemplo, `PE_DISPLAY_ON_PRODUCT_PAGE`, `PE_CONTACT_FORM_ENABLED`).
-   `classes/ProductExpertResolver.php`
    -   **Extiende:** (Probablemente una clase personalizada)
    -   **Métodos públicos clave:** Contiene la lógica central para determinar qué expertos deben mostrarse para un producto dado en función de su categoría, marca, proveedor y asignaciones directas de productos. Resuelve la lista de expertos para el front office.
-   `classes/ProductExpertListPresenter.php`
    -   **Extiende:** (Probablemente una clase personalizada)
    -   **Métodos públicos clave:** Responsable de preparar los datos de los expertos resueltos en un formato adecuado para su visualización en las plantillas de Smarty, aplicando los diseños de lista seleccionados (cuadrícula, carrusel, lista).
-   `classes/ExpertCardLayout.php`, `ExpertCardLayoutPresets.php`, `ExpertCardLayoutPresetsBuiltin.php`, `ExpertCardLayoutPresetsBuiltinData.php`, `ExpertCardLayoutPresetsFilesystem.php`, `ExpertCardLayoutInstances.php`
    -   **Extiende:** (Probablemente clases personalizadas)
    -   **Responsabilidad:** Un complejo conjunto de clases dedicadas a gestionar el diseño visual y la estructura de las tarjetas de visita de expertos. Esto incluye la definición de elementos de diseño, estilos, gradientes y el manejo de preajustes incorporados, así como diseños personalizados guardados por el usuario. Este es el núcleo de la funcionalidad del "Diseñador de tarjetas de visita visual".
-   `classes/ExpertCardAdminUi.php`, `ProductExpertSettingsAdminUi.php`, `ProductExpertListLayoutAdminUi.php`
    -   **Extiende:** (Probablemente clases personalizadas)
    -   **Responsabilidad:** Clases auxiliares para renderizar los complejos elementos de la interfaz de usuario en los formularios de configuración del Back Office, particularmente para el estudio de diseño y la configuración general del módulo.
-   `classes/PeCompatibility.php`
    -   **Extiende:** (Probablemente una clase de utilidad)
    -   **Métodos públicos clave:** Proporciona métodos para manejar problemas de compatibilidad entre diferentes versiones de PrestaShop (por ejemplo, diferencias en los nombres de los hooks, llamadas a la API o funciones obsoletas).
-   `classes/ProductExpertInstallSamples.php`
    -   **Extiende:** (Probablemente una clase de utilidad)
    -   **Métodos públicos clave:** Contiene lógica para instalar datos de muestra (por ejemplo, expertos de muestra, diseños) durante la instalación del módulo para proporcionar un inicio rápido a los comerciantes.

### 4.4 Activos JavaScript (`views/js/`)

-   `lib/searchTool/views/js/autocomplete.js`
    -   **Alcance:** Front-office.
    -   **Descripción:** Proporciona funcionalidad de autocompletado para la herramienta de búsqueda de expertos, sugiriendo nombres de expertos o especialidades a medida que el usuario escribe.
-   `lib/searchTool/views/pe-searchtool-init.js`
    -   **Alcance:** Front-office.
    -   **Descripción:** Inicializa la herramienta de búsqueda de expertos, vinculando los oyentes de eventos a la entrada de búsqueda e integrando la funcionalidad de autocompletado.
-   `views/js/admin-element-editor.js`
    -   **Alcance:** Back-office.
    -   **Descripción:** Impulsa el editor visual para elementos individuales dentro de un diseño de tarjeta de experto (por ejemplo, campos de texto, imágenes, iconos). Maneja arrastrar y soltar, redimensionar y ajustes de propiedades de estilo.
-   `views/js/admin-expert-photo.js`
    -   **Alcance:** Back-office.
    -   **Descripción:** Gestiona la funcionalidad de carga y vista previa de fotos para perfiles de expertos en el panel de administración.
-   `views/js/admin-layout-studio.js`
    -   **Alcance:** Back-office.
    -   **Descripción:** El JavaScript principal para el "Diseñador de tarjetas de visita visual". Maneja el lienzo de diseño general, la gestión de elementos, el guardado/carga de diseños y la aplicación de estilos.
-   `views/js/admin-list-layout-studio.js`
    -   **Alcance:** Back-office.
    -   **Descripción:** Gestiona el estudio para diseñar cómo se muestran varias tarjetas de expertos (cuadrícula, carrusel, lista), incluyendo opciones de adaptabilidad y navegación.
-   `views/js/front.js`
    -   **Alcance:** Front-office.
    -   **Descripción:** Contiene JavaScript general del front-office para el módulo, incluyendo:
        -   Oyentes de eventos para el envío del formulario de contacto (llamadas AJAX a `ajax.php`).
        -   Lógica para mostrar y ocultar el modal del formulario de contacto.
        -   Inicialización de cualquier funcionalidad de carrusel o deslizador para listas de expertos.
        -   Mejoras generales de la interfaz de usuario para las tarjetas de expertos.

### 4.5 Hojas de estilo CSS (`views/css/`)

#### CSS del Front-Office

-   `lib/searchTool/views/css/autocomplete.css`
    -   **Alcance:** Front-office.
    -   **Descripción:** Estilos para las sugerencias desplegables de autocompletado en la herramienta de búsqueda de expertos.
-   `views/css/front.css`
    -   **Alcance:** Front-office.
    -   **Descripción:** Estilos generales del front-office para el módulo, incluyendo diseño básico, tipografía y adaptabilidad para tarjetas y listas de expertos.
-   `views/css/pe-expert-card-front.css`
    -   **Alcance:** Front-office.
    -   **Descripción:** Estilos específicos para las tarjetas de visita de expertos individuales, aplicando el diseño y los estilos de elementos elegidos.
-   `views/css/pe-front-contact.css`
    -   **Alcance:** Front-office.
    -   **Descripción:** Estilos para el formulario de contacto del experto, incluyendo la presentación modal, los campos de entrada y los botones.
-   `views/css/pe-front-experts.css`
    -   **Alcance:** Front-office.
    -   **Descripción:** Estilos para la visualización general de múltiples expertos, como diseños de cuadrícula, diseños de lista o navegación de carrusel.

#### CSS del Back-Office

-   `views/css/admin-config.css`
    -   **Alcance:** Back-office.
    -   **Descripción:** Estilo general para la página de configuración principal del módulo en el panel de administración.
-   `views/css/admin-element-editor.css`
    -   **Alcance:** Back-office.
    -   **Descripción:** Estilos para el editor visual de elementos dentro del estudio de diseño.
-   `views/css/admin-expert-card-studio.css`
    -   **Alcance:** Back-office.
    -   **Descripción:** CSS principal para la interfaz del estudio de diseño de tarjetas de expertos.
-   `views/css/admin-expert-photo.css`
    -   **Alcance:** Back-office.
    -   **Descripción:** Estilos para el área de carga y vista previa de fotos de expertos en los formularios de administración.
-   `views/css/admin-experts-list.css`
    -   **Alcance:** Back-office.
    -   **Descripción:** Estilos para la vista de lista de expertos en `AdminProductExpertController`.
-   `views/css/admin-layout-builder.css`
    -   **Alcance:** Back-office.
    -   **Descripción:** Estilos relacionados con los componentes de construcción de diseño.
-   `views/css/admin-layout-studio.css`
    -   **Alcance:** Back-office.
    -   **Descripción:** Estilos generales para la interfaz del estudio de diseño.
-   `views/css/admin-list-layout-studio.css`
    -   **Alcance:** Back-office.
    -   **Descripción:** Estilos para la interfaz del estudio de diseño de listas.
-   `views/css/admin-pe-overrides.css`
    -   **Alcance:** Back-office.
    -   **Descripción:** Anulaciones o ajustes CSS específicos para los estilos de administración predeterminados de PrestaShop para garantizar la coherencia de la interfaz de usuario del módulo.
-   `views/css/admin-searchtool.css`
    -   **Alcance:** Back-office.
    -   **Descripción:** Estilos para la herramienta de búsqueda dentro del panel de administración (si corresponde, por ejemplo, para buscar productos/categorías durante la asignación).

### 4.6 Estructura de la plantilla Smarty (`views/templates/`)

-   `lib/searchTool/views/scripts.tpl`
    -   **Alcance:** Front-office.
    -   **Descripción:** Probablemente incluye el JavaScript y CSS necesarios para la herramienta de búsqueda, a menudo enganchado en `displayHeader` o `displayFooter` para cargar activos.
-   `views/templates/admin/configure.tpl`
    -   **Alcance:** Back-office.
    -   **Descripción:** La plantilla principal para la página de configuración del módulo (método `getContent()`), que renderiza el formulario de configuración general.
-   `views/templates/admin/list-layout.tpl`
    -   **Alcance:** Back-office.
    -   **Descripción:** Plantilla para el estudio de diseño de listas en el administrador, que permite la configuración de cómo se muestran varias tarjetas de expertos.
-   `views/templates/admin/product-tab.tpl`
    -   **Alcance:** Back-office.
    -   **Descripción:** Esta plantilla probablemente se utiliza para inyectar una pestaña o sección personalizada en la página de edición de productos de PrestaShop, permitiendo la asignación directa de expertos a un producto desde su pantalla de edición.
-   `views/templates/hook/product-experts.tpl`
    -   **Alcance:** Front-office.
    -   **Hook:** `displayProductButtons`, `displayProductExtraContent`, `displayRightColumn`, `displayLeftColumn`, `displayFooter` (según configuración).
    -   **Descripción:** La plantilla principal responsable de renderizar el bloque de tarjetas de expertos en el front office. Itera a través de los expertos resueltos e incluye `_pe-expert-card-element.tpl` para cada uno.
-   `views/templates/hook/_pe-expert-card-element.tpl`
    -   **Alcance:** Front-office.
    -   **Hook:** Incluido por `product-experts.tpl`.
    -   **Descripción:** Renderiza una única tarjeta de visita de experto, aplicando el diseño elegido y mostrando la foto, el nombre, el rol, la biografía y los enlaces de contacto del experto. Probablemente incluye `_pe-expert-card-row.tpl` para contenido estructurado.
-   `views/templates/hook/_pe-expert-card-row.tpl`
    -   **Alcance:** Front-office.
    -   **Hook:** Incluido por `_pe-expert-card-element.tpl`.
    -   **Descripción:** Renderiza una sola fila o sección dentro de una tarjeta de experto, utilizada para estructurar los elementos de contenido (por ejemplo, una fila para iconos de contacto, una fila para nombre y rol).

### 4.7 Esquema de la base de datos y mapa de hooks

#### Tablas de la base de datos

-   `ps_productexpert_expert`: Almacena la información principal del perfil del experto (nombre, rol, biografía, ID de foto, estado activo, preajuste de diseño).
-   `ps_productexpert_expert_lang`: Almacena campos multi-idioma para expertos (si los hay, por ejemplo, biografía).
-   `ps_productexpert_expert_link`: Almacena enlaces de contacto individuales para cada experto (tipo, valor, icono).
-   `ps_productexpert_expert_photo`: Almacena metadatos para las imágenes de perfil de expertos.
-   `ps_productexpert_expert_product`: Tabla de relación muchos a muchos que vincula expertos a productos.
-   `ps_productexpert_expert_category`: Tabla de relación muchos a muchos que vincula expertos a categorías.
-   `ps_productexpert_expert_manufacturer`: Tabla de relación muchos a muchos que vincula expertos a marcas (fabricantes).
-   `ps_productexpert_expert_supplier`: Tabla de relación muchos a muchos que vincula expertos a proveedores.
-   `ps_productexpert_layout_preset`: Almacena definiciones de diseños de tarjetas de expertos personalizados creados por el comerciante.
-   `ps_productexpert_list_layout`: Almacena definiciones de diseños de listas de expertos personalizados (cuadrícula, carrusel, etc.).
-   `ps_configuration`: Almacena la configuración global del módulo (por ejemplo, `PE_DISPLAY_ON_PRODUCT_PAGE`, `PE_DEFAULT_CARD_LAYOUT_ID`).

#### Tabla de Hooks registrados

| Nombre del Hook | Momento de ejecución | Propósito técnico |
| --- | --- | --- |
| `displayHeader` | En la sección `<head>` de cada página. | Cargar los activos CSS y JS del módulo para el front-office. |
| `displayBackOfficeHeader` | En la sección `<head>` de cada página del Back Office. | Cargar los activos CSS y JS del módulo para las pantallas de administración. |
| `displayModuleConfigureExtraButtons` | En la página del gestor de módulos, junto al botón "Configurar". | Añadir enlaces rápidos a "Gestionar expertos" o "Estudio de diseño". |
| `displayAdminProductsExtra` | En la página de edición de productos en el Back Office. | Inyectar la pestaña/sección de asignación de expertos para productos. |
| `displayProductButtons` | Cerca del botón "Añadir al carrito" en las páginas de productos. | Mostrar tarjetas de expertos en un área prominente específica del producto. |
| `displayProductExtraContent` | En una sección/pestaña dedicada en las páginas de productos. | Mostrar tarjetas de expertos como contenido adicional del producto. |
| `displayLeftColumn` | En la barra lateral izquierda de las páginas aplicables. | Mostrar tarjetas de expertos o la herramienta de búsqueda de expertos en la columna izquierda. |
| `displayRightColumn` | En la barra lateral derecha de las páginas aplicables. | Mostrar tarjetas de expertos o la herramienta de búsqueda de expertos en la columna derecha. |
| `displayFooter` | En la sección del pie de página de todas las páginas. | Mostrar tarjetas de expertos o un enlace a una página de expertos en el pie de página. |
| `displayTop` | En la sección superior de la tienda (cabecera). | Mostrar la herramienta de búsqueda de expertos para acceso global. |
| `displayNav` | En la barra de navegación (a menudo encima de `displayTop`). | Mostrar la herramienta de búsqueda de expertos para acceso global. |
| `actionFrontControllerSetMedia` | Antes de que el controlador frontal renderice, para añadir activos. | Añadir dinámicamente JS/CSS específicos del front-office según el contexto. |
| `actionAdminControllerSetMedia` | Antes de que el controlador de administración renderice, para añadir activos. | Añadir dinámicamente JS/CSS específicos del back-office según el contexto. |
| `actionObjectProductAddAfter` | Después de añadir un nuevo producto. | Potencialmente activar la lógica de asignación de expertos o la limpieza de la caché. |
| `actionObjectProductUpdateAfter` | Después de actualizar un producto. | Potencialmente activar la lógica de asignación de expertos o la limpieza de la caché. |
| `actionObjectProductDeleteAfter` | Después de eliminar un producto. | Limpiar cualquier asignación de expertos relacionada con el producto eliminado. |
| `actionObjectCategoryUpdateAfter` | Después de actualizar una categoría. | Borrar la caché relacionada con las asignaciones de expertos basadas en categorías. |
| `actionObjectManufacturerUpdateAfter` | Después de actualizar un fabricante (marca). | Borrar la caché relacionada con las asignaciones de expertos basadas en marcas. |
| `actionObjectSupplierUpdateAfter` | Después de actualizar un proveedor. | Borrar la caché relacionada con las asignaciones de expertos basadas en proveedores. |

## 5. Soporte oficial y actualizaciones

Para las últimas actualizaciones del módulo, correcciones de errores y soporte técnico oficial, consulte su cuenta de cliente en MyPresta.eu. Nuestro equipo se dedica a proporcionar asistencia integral y garantizar que su módulo funcione sin problemas.

-   **Historial de pedidos y descargas de MyPresta.eu:** <https://mypresta.eu/my-account/orders/>
-   **Soporte de MyPresta.eu:** Acceda a nuestro portal de soporte a través de su cuenta para obtener asistencia directa.
