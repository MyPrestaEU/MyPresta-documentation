---
title: "Carrusel de contenidos personalizados - Manual de comerciante y guía de configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop 'Carrusel de contenidos personalizados' de MyPresta.eu."
sidebar:
  label: "Carrusel de contenidos personalizados - Manual de comerciante y guía de configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Custom contents carousel en MyPresta.eu](https://mypresta.eu/modules/front-office-features/custom-contents-carousel.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/front-office/custom-contents-carousel/)
>
> ---


# Carrusel de contenidos personalizados

## 1. Requisitos y compatibilidad

- **Versiones de PrestaShop compatibles**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilidad con PHP**: PHP 5.6 - 8.5
- **Requisitos de alojamiento**: Las extensiones PHP estándar (cURL, JSON, OpenSSL) suelen ser suficientes. Por lo general, no se necesitan configuraciones especiales del servidor más allá de un entorno de alojamiento PrestaShop estándar.

## 2. Recorrido completo por la configuración (Cada ajuste agrupado por pantalla)

El módulo "Carrusel de contenidos personalizados" organiza sus ajustes en varias pantallas de su Back Office de PrestaShop. Primero configurará los ajustes globales, luego creará "Grupos" (que son sus carruseles) y finalmente agregará "Elementos" (las diapositivas individuales) a cada grupo.

### 2.1 Página de configuración del módulo (Back Office > Módulos > Configurar > Carrusel de contenidos personalizados)

Esta es la pantalla de configuración principal del módulo, accesible inmediatamente después de la instalación o haciendo clic en "Configurar" desde el Gestor de módulos.

- **Qué hace este ajuste:** Esta pantalla maneja principalmente la configuración general del módulo y las comprobaciones de actualización.
- **Efecto de cambiar este ajuste:**
  - `mypresta_updates`, `update_`, `updatev_`: Estos son ajustes internos utilizados por los módulos de MyPresta.eu para gestionar actualizaciones y comprobaciones de versión. No afectan directamente la visualización del front-office, pero aseguran que su módulo se mantenga actualizado.
  - `CCAROUSEL_LIGHTSLIDER`: Este ajuste probablemente controla la activación de la biblioteca JavaScript LightSlider, que impulsa la funcionalidad del carrusel.
    - *Cuando está habilitado (SÍ)*: La biblioteca LightSlider se cargará en su front office, permitiendo que los carruseles funcionen correctamente.
    - *Cuando está deshabilitado (NO)*: La biblioteca LightSlider podría no cargarse, lo que podría romper la visualización y funcionalidad del carrusel.
- **Valor recomendado:**
  - `CCAROUSEL_LIGHTSLIDER`: **SÍ** (Habilitado). Esto es crucial para que el carrusel funcione.
  - Otros ajustes: Dejar como predeterminado.
- **Escenario/ejemplo de comerciante:** Acaba de instalar el módulo y quiere asegurarse de que se carguen todos los scripts necesarios. Comprobaría que `CCAROUSEL_LIGHTSLIDER` esté habilitado. Si alguna vez experimenta problemas con el carrusel que no se desliza, este sería uno de los primeros lugares para verificar.

### 2.2 Pantalla de administración dedicada: Grupos de contenidos personalizados (Back Office > Módulos > Carrusel de contenidos personalizados > Grupos de contenidos personalizados)

Esta pantalla le permite crear y administrar sus carruseles individuales. Cada "grupo" representa un carrusel distinto que luego puede poblar con diapositivas.

- **Nombre de la pantalla y ubicación del menú:** Lo encontrará en **Módulos > Carrusel de contenidos personalizados > Grupos de contenidos personalizados** en el menú de su Back Office de PrestaShop.
- **Acciones y ajustes disponibles:**
  - **Vista de cuadrícula**: Muestra una lista de todos sus grupos de carrusel existentes. Puede ver sus nombres, estado (activo/inactivo) y acciones.
  - **Añadir nuevo grupo**: Haga clic en el botón "Añadir nuevo" para crear un carrusel completamente nuevo.
  - **Editar/Eliminar grupo**: Para cada grupo, tendrá opciones para editar sus ajustes (por ejemplo, nombre, opciones de visualización) o eliminarlo por completo.
  - **Alternar estado**: Active o desactive rápidamente un grupo de carrusel sin eliminarlo. Un grupo inactivo no aparecerá en su front office.
- **Efecto de los cambios:**
  - **Añadir un nuevo grupo**: Crea un nuevo contenedor de carrusel vacío. Luego deberá agregarle elementos (diapositivas).
  - **Editar un grupo**: Le permite cambiar el nombre del carrusel, sus ajustes de visualización (por ejemplo, reproducción automática, velocidad, número de diapositivas visibles) y su posición.
  - **Activar/Desactivar**: Controla si el carrusel es visible para sus clientes en el front office.
  - **Eliminar un grupo**: Elimina permanentemente el carrusel y todos sus elementos (diapositivas) asociados.
- **Flujo de trabajo recomendado para la gestión diaria de la tienda:**
  1. Comience creando un nuevo grupo para cada carrusel que desee mostrar (por ejemplo, "Carrusel de banners de la página de inicio", "Slider de novedades").
  2. Asigne a cada grupo un nombre claro y descriptivo.
  3. Configure los ajustes de visualización del grupo (por ejemplo, reproducción automática, bucle, pausa al pasar el ratón) para que coincidan con la experiencia de usuario deseada.
  4. Una vez creado el grupo, vaya a la pantalla "Elementos de contenidos personalizados" para añadirle diapositivas.

### 2.3 Pantalla de administración dedicada: Elementos de contenidos personalizados (Back Office > Módulos > Carrusel de contenidos personalizados > Elementos de contenidos personalizados)

Esta pantalla es donde gestiona las diapositivas individuales (elementos) dentro de sus carruseles. Cada elemento puede ser una imagen, un video, texto o contenido incrustado.

- **Nombre de la pantalla y ubicación del menú:** Lo encontrará en **Módulos > Carrusel de contenidos personalizados > Elementos de contenidos personalizados** en el menú de su Back Office de PrestaShop.
- **Acciones y ajustes disponibles:**
  - **Vista de cuadrícula**: Lista todas las diapositivas individuales, mostrando a qué grupo pertenecen, su tipo de contenido y su estado.
  - **Añadir nuevo elemento**: Haga clic en "Añadir nuevo" para crear una nueva diapositiva. Luego elegirá el grupo al que pertenece y definirá su contenido.
  - **Editar/Eliminar elemento**: Modifique el contenido, el enlace o el orden de visualización de una diapositiva existente, o elimínela.
  - **Alternar estado**: Active o desactive diapositivas individuales. Una diapositiva inactiva no aparecerá en su carrusel.
  - **Reordenación por arrastrar y soltar**: Cambie fácilmente el orden de visualización de las diapositivas dentro de un grupo.
- **Efecto de los cambios:**
  - **Añadir un nuevo elemento**: Crea una nueva diapositiva. Especificará su contenido (carga de imagen, URL de video, texto, HTML), un enlace y lo asignará a uno de sus grupos de carrusel existentes.
  - **Editar un elemento**: Le permite actualizar el contenido, cambiar el enlace, modificar la imagen o ajustar su posición dentro del carrusel.
  - **Activar/Desactivar**: Controla si una diapositiva específica es visible dentro de su carrusel.
  - **Eliminar un elemento**: Elimina permanentemente la diapositiva de su carrusel.
- **Flujo de trabajo recomendado para la gestión diaria de la tienda:**
  1. Seleccione el grupo de carrusel al que desea añadir diapositivas (si tiene varios).
  2. Haga clic en "Añadir nuevo elemento" y elija el tipo de contenido (imagen, video, texto, HTML).
  3. Suba su imagen, pegue la URL de su video o introduzca su texto/HTML.
  4. Añada un enlace relevante si la diapositiva debe dirigir a los clientes a un producto, categoría o página externa.
  5. Establezca el orden de visualización.
  6. Repita para todas las diapositivas de su carrusel.
  7. Utilice la función de arrastrar y soltar para ajustar el orden de sus diapositivas.

### 2.4 Pantalla de administración dedicada: index.php (`ccarousel/controllers/admin/index.php`)

Este archivo es una práctica estándar de PrestaShop para asegurar los directorios de administración. Normalmente contiene una simple declaración `die('No direct script access allowed');` y no presenta una pantalla configurable ni una entidad gestionada en sí misma. Es una medida de seguridad, no una interfaz de configuración.

### 2.5 Tabla de referencia rápida de configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e impacto |
| --- | --- | --- | --- |
| Configuración del módulo | `CCAROUSEL_LIGHTSLIDER` | SÍ | Habilita/deshabilita la biblioteca JavaScript principal para la funcionalidad del carrusel. **Debe ser SÍ para que los carruseles funcionen.** |
| Grupos de contenidos personalizados | Nombre del grupo | Definido por el usuario | Identifica su carrusel (por ejemplo, "Banners de la página de inicio"). |
| Grupos de contenidos personalizados | Estado | Habilitado | Controla la visibilidad de todo el carrusel en el front office. |
| Grupos de contenidos personalizados | Ajustes del carrusel | Definido por el usuario | Controla la reproducción automática, la velocidad, el bucle, la navegación, etc., para cada carrusel. |
| Elementos de contenidos personalizados | Contenido del elemento | Definido por el usuario | El contenido real de la diapositiva (imagen, video, texto, HTML). |
| Elementos de contenidos personalizados | Enlace del elemento | URL opcional | A dónde dirige la diapositiva a los clientes cuando se hace clic. |
| Elementos de contenidos personalizados | Estado | Habilitado | Controla la visibilidad de las diapositivas individuales dentro de un carrusel. |
| Elementos de contenidos personalizados | Posición | Definido por el usuario | Determina el orden de las diapositivas dentro de un carrusel. |

## 3. Solución de problemas para comerciantes y preguntas frecuentes (FAQ)

**P1: Mi carrusel no aparece en la página de inicio.**

- **R:** Primero, verifique si el módulo "Carrusel de contenidos personalizados" está habilitado en **Módulos > Gestor de módulos**. Luego, navegue a **Módulos > Carrusel de contenidos personalizados > Grupos de contenidos personalizados** y asegúrese de que su grupo de carrusel esté activo (marca de verificación verde). Finalmente, asegúrese de tener al menos un "Elemento de contenido personalizado" activo asignado a ese grupo. Además, verifique que la configuración `CCAROUSEL_LIGHTSLIDER` en la página de configuración principal del módulo esté habilitada.

**P2: Las imágenes de mi carrusel están borrosas o distorsionadas.**

- **R:** Asegúrese de que las imágenes que sube sean de alta calidad y tengan las dimensiones adecuadas para el espacio donde se muestra el carrusel. Si su tema tiene recomendaciones específicas de tamaño de imagen para banners o sliders, intente igualarlas. El módulo escalará las imágenes, pero comenzar con una buena imagen de origen es clave.

**P3: El carrusel no se desliza ni se reproduce automáticamente.**

- **R:** Esto suele ser un problema de JavaScript.
  1. Vaya a **Módulos > Configurar > Carrusel de contenidos personalizados** y asegúrese de que `CCAROUSEL_LIGHTSLIDER` esté configurado en "SÍ".
  2. Borre la caché de su PrestaShop (**Parámetros avanzados > Rendimiento > Borrar caché**).
  3. Borre la caché de su navegador.
  4. Si el problema persiste, podría haber un conflicto de JavaScript con otro módulo o su tema. Verifique la consola de desarrollador de su navegador (F12) en busca de errores de JavaScript.

**P4: ¿Cómo cambio el orden de las diapositivas en mi carrusel?**

- **R:** Vaya a **Módulos > Carrusel de contenidos personalizados > Elementos de contenidos personalizados**. Debería ver una lista de sus diapositivas. Busque una columna con flechas o un icono de arrastrar y soltar. Normalmente puede arrastrar y soltar las filas para reordenarlas, o podría haber un campo "Posición" que puede editar. Recuerde guardar sus cambios.

**P5: ¿Puedo tener varios carruseles en diferentes páginas?**

- **R:** El módulo utiliza principalmente el hook `displayHome`, lo que significa que está diseñado para la página de inicio. Si bien puede crear múltiples *grupos* (carruseles), todos se renderizarán típicamente en la misma posición enganchada. Para mostrar carruseles en diferentes páginas o en diferentes posiciones, se requeriría una integración de tema personalizada o un registro de hook adicional (consulte la Guía para desarrolladores).

## 4. Guía para desarrolladores y webmasters (Arquitectura técnica y mapa de código)

Esta sección proporciona una descripción técnica detallada para desarrolladores y webmasters que mantienen o extienden el módulo "Carrusel de contenidos personalizados".

### 4.1 Descripción general de la arquitectura

El módulo "Carrusel de contenidos personalizados" sigue un patrón MVC (Modelo-Vista-Controlador) estándar de PrestaShop para sus componentes de Back Office. Aprovecha la clase `Module` de PrestaShop para la funcionalidad principal y `AdminController` para gestionar grupos y elementos de contenido. La visualización del front-office se maneja principalmente a través de una plantilla Smarty enganchada a `displayHome`, con activos JavaScript (LightSlider) y CSS cargados a través de `displayHeader`. La persistencia de datos se gestiona a través de clases `ObjectModel` personalizadas.

### 4.2 Controladores (`controllers/`)

- **Controladores de Front-Office**:
  El módulo no contiene ningún controlador de front-office dedicado. Toda la renderización del front-office se maneja directamente a través de la clase principal del módulo (`ccarousel.php`) registrando hooks y renderizando plantillas.
- **Controladores de administración de Back-Office**:

  - `controllers/admin/AdminCustomContentsGroupsController.php`
    - Nombre de la clase: `AdminCustomContentsGroupsController`
    - Clase padre: `ModuleAdminController`
    - Responsabilidad: Gestiona la entidad `gcarousel` (grupos de carrusel). Este controlador maneja la lista, adición, edición y eliminación de grupos de carrusel. Define los campos del formulario para la configuración del grupo (por ejemplo, nombre, estado, ajustes del carrusel como reproducción automática, velocidad).
  - `controllers/admin/AdminCustomContentsItemsController.php`
    - Nombre de la clase: `AdminCustomContentsItemsController`
    - Clase padre: `ModuleAdminController`
    - Responsabilidad: Gestiona la entidad `gcitem` (diapositivas/elementos individuales del carrusel). Este controlador maneja la lista, adición, edición y eliminación de diapositivas. Define los campos del formulario para el contenido de la diapositiva (carga de imagen, URL de video, texto/HTML, enlace, posición, grupo asociado). También gestiona la funcionalidad de reordenación por arrastrar y soltar para las diapositivas.
  - `controllers/admin/index.php`
    - Nombre de la clase: N/A (archivo PHP simple)
    - Clase padre: N/A
    - Responsabilidad: Una medida de seguridad para evitar la lista o el acceso directo al directorio. Contiene `die('No direct script access allowed');`.

### 4.3 Clases y modelos principales (`classes/`)

El dossier del módulo no indica clases personalizadas en el directorio `classes/`. Esto sugiere que las definiciones de `ObjectModel` para `gcarousel` y `gcitem` probablemente están incrustadas directamente dentro del archivo principal del módulo (`ccarousel.php`) o dentro de los archivos `AdminController` respectivos.

- **`gcarousel` (Modelo de grupo de carrusel)**:

  - Probablemente extiende `ObjectModel`.
  - Interactúa con una tabla de base de datos personalizada (por ejemplo, `ps_gcarousel`).
  - Los campos `$definition` incluirían: `id_gcarousel`, `name`, `active`, `settings` (posiblemente un array serializado o una cadena JSON para las opciones de visualización del carrusel).
  - Métodos clave: `add()`, `update()`, `delete()`, `getGroups()`.
- **`gcitem` (Modelo de elemento/diapositiva de carrusel)**:

  - Probablemente extiende `ObjectModel`.
  - Interactúa con una tabla de base de datos personalizada (por ejemplo, `ps_gcitem`).
  - Los campos `$definition` incluirían: `id_gcitem`, `id_gcarousel` (clave externa), `position`, `active`, `type` (imagen, video, texto, html), `content` (ruta a la imagen, URL de video, texto), `link`, `title`, `description` (para soporte multilingüe).
  - Métodos clave: `add()`, `update()`, `delete()`, `getItemsByGroup()`, `updatePosition()`.

### 4.4 Activos JavaScript (`views/js/`)

- `ccarousel/lib/src/js/lightslider.js`
  - Alcance: Front-office.
  - Responsabilidad: Esta es la biblioteca principal de LightSlider. Inicializa y gestiona la funcionalidad del carrusel. Vincula los oyentes de eventos para la navegación (flechas, puntos), maneja los gestos táctiles/de deslizamiento, la reproducción automática, el bucle y los ajustes responsivos. El método `hookDisplayHeader` o `hookDisplayHome` del módulo normalmente pondría en cola este script, y luego un script en línea o un archivo JS de módulo separado llamaría a `$('#your-carousel-selector').lightSlider({...});` para inicializar carruseles específicos.

### 4.5 Hojas de estilo CSS (`views/css/`)

- `ccarousel/css.css`
  - Alcance: Front-office.
  - Responsabilidad: Probablemente contiene estilos personalizados específicos del módulo "Carrusel de contenidos personalizados", que anulan o extienden los estilos base de LightSlider para que coincidan con el tema predeterminado de PrestaShop o para proporcionar ajustes visuales específicos del módulo.
- `ccarousel/lib/src/css/ccarousel.css`
  - Alcance: Front-office.
  - Responsabilidad: Podría ser una hoja de estilo base para la estructura del módulo o un marcador de posición. Dado el nombre, es probable que sea un estilo específico del módulo.
- `ccarousel/lib/src/css/lightslider.css`
  - Alcance: Front-office.
  - Responsabilidad: La hoja de estilo predeterminada para la biblioteca LightSlider. Proporciona el estilo esencial para el contenedor del carrusel, las diapositivas, las flechas de navegación y los puntos de paginación. Los desarrolladores pueden anular estos estilos en el `custom.css` de su tema o modificando `ccarousel/css.css`.

### 4.6 Estructura de la plantilla Smarty (`views/templates/`)

- **Plantillas de hook (`views/templates/hook/`)**:
  - `ccarousel/views/templates/hook/ccarousel.tpl`
    - Renderizado en: `displayHome` (y potencialmente otros hooks si se configura en el módulo).
    - Salidas: La estructura HTML para uno o más carruseles. Esta plantilla itera a través de los grupos de carrusel y sus elementos asociados, generando los elementos `<ul>` y `<li>` necesarios que LightSlider espera. Incluye etiquetas de imagen, incrustaciones de video o contenido HTML sin formato según el tipo de elemento, junto con enlaces. También es probable que contenga la llamada de inicialización de JavaScript para LightSlider, pasando las opciones de configuración recuperadas de los ajustes de `gcarousel`.

### 4.7 Esquema de la base de datos y mapa de hooks

- **Tablas de la base de datos**:

  - `ps_gcarousel`: Almacena información sobre cada grupo de carrusel.
    - `id_gcarousel` (PK, INT)
    - `name` (VARCHAR)
    - `active` (TINYINT)
    - `settings` (TEXT o JSON, para opciones serializadas de LightSlider)
    - `date_add` (DATETIME)
    - `date_upd` (DATETIME)
  - `ps_gcitem`: Almacena información sobre cada diapositiva/elemento individual.
    - `id_gcitem` (PK, INT)
    - `id_gcarousel` (FK a `ps_gcarousel`, INT)
    - `position` (INT)
    - `active` (TINYINT)
    - `type` (VARCHAR, por ejemplo, 'image', 'video', 'text', 'html')
    - `content` (TEXT, almacena la ruta de la imagen, la URL del video o texto/HTML sin formato)
    - `link` (VARCHAR)
    - `title` (VARCHAR, para varios idiomas)
    - `description` (TEXT, para varios idiomas)
    - `date_add` (DATETIME)
    - `date_upd` (DATETIME)
  - `ps_configuration`: Almacena valores de configuración específicos del módulo, como `CCAROUSEL_LIGHTSLIDER`, `MYPRESTA_UPDATES`, etc.
- **Tabla de Hooks registrados**:

| Nombre del Hook | Momento de ejecución | Propósito técnico |
| --- | --- | --- |
| `displayHeader` | En la sección `<head>` de cada página. | Pone en cola los archivos CSS (`lightslider.css`, `ccarousel.css`) y JavaScript (`lightslider.js`) necesarios para que el carrusel funcione y se estilice correctamente. |
| `displayHome` | En el área de contenido principal de la página de inicio. | Renderiza la plantilla `ccarousel.tpl`, que genera la estructura HTML para los grupos de carrusel activos y sus elementos, junto con el script de inicialización de LightSlider. |

## 5. Soporte oficial y actualizaciones

Para obtener actualizaciones oficiales, soporte técnico y para asegurarse de que está ejecutando la versión más reciente y segura del módulo "Carrusel de contenidos personalizados", consulte su cuenta de cliente en [MyPresta.eu](https://mypresta.eu/). Nuestro equipo de soporte está disponible para ayudar con cualquier problema o pregunta relacionada con la funcionalidad y compatibilidad del módulo.
