---
title: "Homepage Products Pro - Manual de Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo Homepage Products Pro de PrestaShop por MyPresta.eu."
sidebar:
  label: "Homepage Products Pro - Manual de Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Homepage Products Pro en MyPresta.eu](https://mypresta.eu/modules/front-office-features/homepage-products-pro.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/front-office/homepage-products-pro/)
>
> ---


# Homepage Products Pro

## 1. Requisitos y compatibilidad

- **Versiones de PrestaShop compatibles**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilidad con PHP**: PHP 5.6 - 8.5
- **Requisitos de alojamiento**: Extensiones PHP estándar (cURL, JSON, OpenSSL).

## 2. Recorrido completo por la configuración (Cada ajuste agrupado por pantalla)

### 2.1 Página de configuración del módulo (Back Office > Módulos > Configurar)

Después de la instalación, al hacer clic en "Configurar" accederá a la página principal de ajustes de "Homepage Products Pro". Aquí es donde controlará el comportamiento global y las características de sus bloques de productos.

#### Ajustes generales

- **Activar pestañas internas**

  - **Qué hace este ajuste:** Controla si el módulo puede crear sus propias pestañas personalizadas en la página de inicio, de forma similar a las pestañas predeterminadas de PrestaShop "Productos Populares" o "Nuevos Productos".
  - **Efecto de cambiar este ajuste:**
    - *Cuando está activado (Sí):* Podrá crear nuevos bloques de productos que aparecerán como pestañas clicables en su página de inicio, permitiendo a los clientes cambiar entre diferentes colecciones de productos.
    - *Cuando está desactivado (No):* El módulo solo mostrará bloques de productos como secciones independientes (por ejemplo, carruseles horizontales o bloques de columna), sin la interfaz de pestañas.
  - **Valor recomendado:** **Sí** (para aprovechar toda la potencia del módulo para contenido dinámico de la página de inicio).
  - **Escenario / ejemplo de comerciante:** Desea mostrar "Novedades", "Más vendidos" y "Selecciones de temporada" en su página de inicio sin que sea demasiado larga. La activación de las pestañas internas le permite colocar cada uno de ellos en su propia pestaña.
- **Usar editor de texto enriquecido**

  - **Qué hace este ajuste:** Determina si un editor visual (WYSIWYG) está disponible cuando crea o edita descripciones o títulos de bloques de productos, lo que facilita el formato del texto.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está activado (Sí):* Obtendrá un editor fácil de usar (como TinyMCE) con opciones de formato (negrita, cursiva, enlaces, etc.) para los campos de texto dentro del módulo.
    - *Cuando está desactivado (No):* Tendrá un campo de entrada de texto sin formato, lo que le obligará a usar HTML básico si desea algún formato.
  - **Valor recomendado:** **Sí** (para una creación de contenido más fácil y un mejor control visual).
  - **Escenario / ejemplo de comerciante:** Desea añadir una breve introducción con estilo encima de un bloque de productos, como "¡Descubra nuestra colección **exclusiva**!". El editor de texto enriquecido lo hace sencillo.
- **Cargar lightslider**

  - **Qué hace este ajuste:** Controla si el módulo carga la biblioteca JavaScript LightSlider, que se utiliza para crear carruseles y deslizadores de contenido responsivos.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está activado (Sí):* Se cargará la biblioteca LightSlider, lo que permitirá que sus bloques de productos se muestren como carruseles interactivos y táctiles. Esto suele ser necesario para los efectos visuales del módulo.
    - *Cuando está desactivado (No):* La biblioteca LightSlider no se cargará. Si su tema u otro módulo proporciona una funcionalidad de carrusel similar, podría desactivar esto para evitar conflictos o cargas redundantes. Sin embargo, si no hay otra solución de carrusel presente, sus bloques de productos podrían mostrarse como cuadrículas o listas estáticas.
  - **Valor recomendado:** **Sí** (a menos que tenga una razón o conflicto específico, ya que es esencial para las características de carrusel del módulo).
  - **Escenario / ejemplo de comerciante:** Desea que su bloque de "Nuevos Productos" sea un carrusel elegante de desplazamiento horizontal. Este ajuste garantiza que se cargue el script necesario para esa funcionalidad.
- **Activar analíticas**

  - **Qué hace este ajuste:** Activa o desactiva el seguimiento interno del módulo del rendimiento de los bloques de productos, como vistas y clics.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está activado (Activado):* El módulo recopilará datos sobre la frecuencia con la que se ven y se hace clic en sus bloques de productos, proporcionando información sobre su eficacia.
    - *Cuando está desactivado (Desactivado):* No se recopilarán ni mostrarán datos de rendimiento dentro del panel de control del módulo.
  - **Valor recomendado:** **Activado** (para obtener información valiosa sobre qué bloques de productos están funcionando mejor).
  - **Escenario / ejemplo de comerciante:** Desea saber si su bloque de "Más vendidos" está obteniendo más interacción que su bloque de "En oferta". La activación de las analíticas proporciona estos datos.
- **Período de analíticas**

  - **Qué hace este ajuste:** Define el período de tiempo para el cual se mostrarán los datos de analíticas internas del módulo.
  - **Efecto de cambiar este ajuste:** Cambia el rango de datos que se muestran en los informes de analíticas.
  - **Opciones:** Últimos 7 días, Últimos 30 días, Últimos 90 días, Últimos 180 días, Últimos 365 días.
  - **Valor recomendado:** **Últimos 30 días** (un buen equilibrio para las tendencias recientes, pero ajústelo según sus necesidades de informes).
  - **Escenario / ejemplo de comerciante:** Desea revisar el rendimiento de sus bloques de productos de la página de inicio durante el último mes para ver si una promoción reciente tuvo un impacto.
- **Activar caché de bloques**

  - **Qué hace este ajuste:** Activa un mecanismo de caché para los bloques de productos generados por el módulo. El almacenamiento en caché guarda una versión temporal del bloque, por lo que no tiene que reconstruirse cada vez que un cliente visita la página.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está activado (Sí):* Los bloques de productos se cargarán más rápido para los clientes, ya que el servidor sirve una versión en caché. Esto puede mejorar significativamente los tiempos de carga de la página y el rendimiento del servidor, especialmente en tiendas con mucho tráfico.
    - *Cuando está desactivado (No):* Los bloques de productos se generarán dinámicamente en cada carga de página, lo que puede ser más lento pero garantiza que siempre se muestren los datos de productos más recientes (por ejemplo, niveles de stock, precios).
  - **Valor recomendado:** **Sí** (para beneficios de rendimiento, a menos que tenga datos de productos que cambien muy rápidamente y deban ser en tiempo real).
  - **Escenario / ejemplo de comerciante:** Su página de inicio está recibiendo mucho tráfico y desea asegurarse de que se cargue lo más rápido posible. La activación de la caché acelerará la visualización de sus bloques de productos.
- **TTL de caché (segundos)**

  - **Qué hace este ajuste:** Define cuánto tiempo (en segundos) una versión en caché de un bloque de productos permanece válida antes de que se actualice. (TTL significa "Time To Live" - Tiempo de vida).
  - **Efecto de cambiar este ajuste:**
    - *Valor más alto:* Los bloques se almacenan en caché por más tiempo, lo que lleva a un mejor rendimiento pero potencialmente muestra información de productos ligeramente desactualizada (por ejemplo, si un precio cambia, es posible que no se actualice en la página de inicio hasta que expire la caché).
    - *Valor más bajo:* Los bloques se actualizan con más frecuencia, lo que garantiza información más actualizada pero con una ganancia de rendimiento ligeramente menor.
  - **Valor recomendado:** **3600** (1 hora) o **7200** (2 horas) es un buen punto de partida. Ajústelo según la frecuencia con la que cambian los datos de sus productos y la importancia de las actualizaciones en tiempo real.
  - **Escenario / ejemplo de comerciante:** Tiene una venta flash donde los precios cambian cada hora. Podría establecer el TTL de caché en 3600 segundos (1 hora) para asegurarse de que los precios se actualicen relativamente rápido en la página de inicio.
- **Detección automática de tema**

  - **Qué hace este ajuste:** Intenta detectar automáticamente su tema activo de PrestaShop para aplicar estilos y anulaciones de plantilla apropiados para una mejor integración visual.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está activado (Sí):* El módulo intenta adaptar su salida para que coincida con la estructura y el estilo de su tema, utilizando potencialmente plantillas específicas del tema (por ejemplo, `firezy-products17.tpl`). Esto a menudo resulta en un aspecto más uniforme.
    - *Cuando está desactivado (No):* El módulo utilizará sus plantillas y estilos predeterminados y genéricos, que podrían no coincidir perfectamente con el diseño de su tema. Es posible que deba seleccionar un tema manualmente o aplicar CSS personalizado.
  - **Valor recomendado:** **Sí** (para la mejor integración visual lista para usar).
  - **Escenario / ejemplo de comerciante:** Ha instalado el módulo y los bloques de productos no se ven del todo bien con su tema personalizado. La activación de esto podría corregir automáticamente el estilo.

#### Ajustes ocultos/avanzados (Claves de configuración internas)

Estos normalmente no se exponen directamente como ajustes orientados al usuario, sino que son valores de configuración que el módulo utiliza internamente. Se enumeran aquí para completar y para la comprensión del desarrollador.

- `update_`, `mypresta_updates`: Relacionado con las comprobaciones de actualización del módulo y las notificaciones de MyPresta.eu.
- `hpp_analytics_enabled`: Corresponde al ajuste "Activar analíticas".
- `hpp_cache_enabled`: Corresponde al ajuste "Activar caché de bloques".
- `hpp_cache_ttl`: Corresponde al ajuste "TTL de caché (segundos)".
- `hpp_theme_auto_detect`: Corresponde al ajuste "Detección automática de tema".
- `hpp_analytics_period`: Corresponde al ajuste "Período de analíticas".
- `hpp_carousel_native`: Probablemente una bandera interna para el tipo de carrusel, posiblemente relacionada con LightSlider.
- `PS_NB_DAYS_NEW_PRODUCT`: Ajuste predeterminado de PrestaShop para cuántos días un producto se considera "nuevo". El módulo podría usar esto para bloques de "Nuevos Productos".
- `PS_CURRENCY_DEFAULT`: ID de la moneda predeterminada de PrestaShop.
- `hpp_internal_tabs`: Corresponde al ajuste "Activar pestañas internas".
- `hpp_bxslider`: Una biblioteca de carrusel más antigua, posiblemente un ajuste heredado o de respaldo.
- `PS_LANG_DEFAULT`: ID del idioma predeterminado de PrestaShop.
- `PS_BO_ALLOW_EMPLOYEE_FORM_LANG`: Ajuste de PrestaShop para permitir a los empleados cambiar el idioma del formulario.
- `hpp_rich_text`: Corresponde al ajuste "Usar editor de texto enriquecido".
- `hpp_theme`: Almacena el nombre del tema detectado o seleccionado manualmente.
- `hpp_customtplpath`: Permite especificar una ruta personalizada para las plantillas, útil para una integración avanzada del tema.

### 2.2 Pantallas de administración dedicadas y vistas de controlador

El módulo "Homepage Products Pro" extiende el Back Office de PrestaShop añadiendo una sección dedicada para gestionar sus bloques de productos.

- **Nombre de la pantalla y ubicación del menú:**

  - Encontrará un nuevo elemento de menú, normalmente en **Módulos > Homepage Products Pro** o un nombre similar, que le llevará al panel de control del módulo.
  - Este panel de control es donde crea, edita, elimina y organiza sus bloques de productos.
- **Acciones y ajustes disponibles:**

  - **Tabla de listado de bloques de productos:** Esta vista principal mostrará una lista de todos los bloques de productos que ha creado. Cada entrada mostrará:
    - **Nombre:** El nombre interno que le ha dado al bloque (por ejemplo, "Más vendidos de la página de inicio").
    - **Título:** El título público que se muestra a los clientes (por ejemplo, "¡Nuestras selecciones principales!").
    - **Hook:** Dónde se muestra el bloque (por ejemplo, `displayHome`, `displayHomeTabContent`, `displayLeftColumn`).
    - **Estado:** Si el bloque está activado o desactivado.
    - **Posición:** El orden en que aparecen los bloques dentro del mismo hook.
    - **Acciones:** Botones para **Editar**, **Duplicar** o **Eliminar** el bloque.
  - **Botón "Añadir nuevo bloque":** Al hacer clic en este botón, se abrirá un formulario para crear un nuevo bloque de productos.
  - **Formulario "Editar bloque":** Al añadir o editar un bloque, normalmente configurará:
    - **Nombre del bloque:** Un identificador interno (por ejemplo, "ColecciónVerano2023").
    - **Título de visualización:** El título que ven los clientes (por ejemplo, "Colección de Verano").
    - **Descripción:** Un texto corto que aparece encima de los productos (editor de texto enriquecido disponible si está activado).
    - **Selección de hook:** Elija dónde aparece el bloque (por ejemplo, `displayHome`, `displayHomeTabContent` para pestañas, `displayLeftColumn`).
    - **Selección de productos:** Esto es crucial. Definirá *qué* productos aparecen en el bloque. Las opciones suelen incluir:
      - **Productos específicos:** Seleccione manualmente productos individuales utilizando una herramienta de búsqueda.
      - **Productos de categoría:** Seleccione una o más categorías, y el módulo mostrará productos de ellas.
      - **Nuevos productos:** Muestra automáticamente los últimos productos añadidos a su tienda.
      - **Más vendidos:** Muestra automáticamente los productos más vendidos de su tienda.
      - **Productos en oferta:** Muestra automáticamente los productos actualmente en oferta.
      - **Productos destacados:** Productos marcados como destacados.
    - **Número de productos a mostrar:** Limite cuántos productos se muestran.
    - **Tipo de visualización:** Elija entre un carrusel/deslizador o una cuadrícula/lista estática.
    - **Ajustes del carrusel:** Si usa un carrusel, ajustes para elementos por diapositiva, reproducción automática, flechas de navegación, etc.
    - **Selector de visibilidad/audiencia:** Defina quién ve el bloque (por ejemplo, todos los clientes, grupos de clientes específicos, países específicos).
    - **Especificidad del idioma:** Configure títulos y descripciones para diferentes idiomas.
    - **Estado:** Activar/Desactivar el bloque individual.
    - **Posición:** Establezca el orden de visualización en relación con otros bloques en el mismo hook.
- **Efecto de los cambios:**

  - **Añadir un nuevo bloque:** Aparecerá una nueva visualización de productos en su front-office en el hook elegido, mostrando los productos seleccionados según sus ajustes.
  - **Editar un bloque:** Los cambios en títulos, descripciones, selección de productos, tipo de visualización o ajustes se reflejarán inmediatamente en el front-office (sujeto al TTL de caché si la caché está activada).
  - **Eliminar un bloque:** La visualización de productos se eliminará de su front-office.
  - **Cambiar posición:** El orden de los bloques dentro de un hook específico se actualizará en el front-office.
  - **Activar/Desactivar:** Alterna la visibilidad del bloque en su tienda.
- **Flujo de trabajo recomendado para la gestión diaria de la tienda:**

  1.  **Planifique el diseño de su página de inicio:** Decida qué tipos de productos desea destacar (nuevos, más vendidos, categorías específicas, promociones).
  2.  **Cree nuevos bloques:** Para cada sección planificada, vaya al panel de control del módulo y haga clic en "Añadir nuevo bloque".
  3.  **Configure cada bloque:**
      - Dele un nombre interno claro (por ejemplo, "HP\_Novedades").
      - Escriba un título y una descripción atractivos.
      - Seleccione el hook apropiado (por ejemplo, `displayHome` para el contenido principal, `displayHomeTabContent` para las pestañas).
      - Elija su método de selección de productos (manual, categoría, nuevo, etc.).
      - Ajuste la visualización y la configuración del carrusel.
      - Establezca la posición para controlar su orden.
  4.  **Revise en el front-office:** Siempre revise la página de inicio de su tienda después de realizar cambios para asegurarse de que todo se vea y funcione como se espera.
  5.  **Supervise las analíticas:** Revise regularmente las analíticas del módulo (si están activadas) para comprender qué bloques están funcionando bien y ajuste su estrategia en consecuencia.
  6.  **Mantenga y actualice:** A medida que lleguen nuevos productos o cambien las promociones, actualice sus bloques existentes o cree nuevos para mantener su página de inicio fresca y relevante.

### 2.3 Tabla de referencia rápida de configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| Config. principal | Activar pestañas internas | Sí | Permite la creación de pestañas de productos en la página de inicio. |
| Config. principal | Usar editor de texto enriquecido | Sí | Proporciona un editor visual para campos de texto. |
| Config. principal | Cargar lightslider | Sí | Activa carruseles/deslizadores de productos. |
| Config. principal | Activar analíticas | Activado | Rastrea vistas y clics para bloques de productos. |
| Config. principal | Período de analíticas | Últimos 30 días | Establece el período de tiempo para los informes de analíticas. |
| Config. principal | Activar caché de bloques | Sí | Mejora la velocidad de carga de la página al almacenar en caché los bloques. |
| Config. principal | TTL de caché (segundos) | 3600 (1 hora) | Cuánto tiempo permanecen válidos los bloques en caché. |
| Config. principal | Detección automática de tema | Sí | Adapta la salida del módulo para que coincida con su tema. |
| Gestión de bloques | Nombre del bloque | N/A (Definido por el usuario) | Identificador interno para su bloque de productos. |
| Gestión de bloques | Título de visualización | N/A (Definido por el usuario) | Título público que se muestra a los clientes. |
| Gestión de bloques | Descripción | N/A (Definido por el usuario) | Texto que se muestra encima del bloque de productos. |
| Gestión de bloques | Selección de hook | `displayHome` / `displayHomeTabContent` | Determina dónde aparece el bloque en la tienda. |
| Gestión de bloques | Selección de productos | N/A (Definido por el usuario) | Define qué productos se muestran (manual, categoría, nuevos, más vendidos, etc.). |
| Gestión de bloques | Número de productos | N/A (Definido por el usuario) | Limita la cantidad de productos mostrados. |
| Gestión de bloques | Tipo de visualización | Carrusel / Cuadrícula | Cómo se presentan visualmente los productos. |
| Gestión de bloques | Visibilidad/Audiencia | Todos los clientes | Restringe la visibilidad del bloque a grupos/países específicos. |
| Gestión de bloques | Estado | Activado | Alterna la visibilidad del bloque en el front-office. |
| Gestión de bloques | Posición | N/A (Definido por el usuario) | Establece el orden de visualización de los bloques dentro de un hook. |

## 3. Solución de problemas del comerciante y preguntas frecuentes (FAQ)

**P1: Mis bloques de productos no aparecen en la página de inicio o se ven rotos.**

-   **R:**
    1.  **Verifique el estado del módulo:** Asegúrese de que el módulo "Homepage Products Pro" esté activado en **Módulos > Gestor de módulos**.
    2.  **Verifique el estado del bloque:** Vaya al panel de configuración del módulo y verifique que los bloques de productos específicos que creó estén "Activados".
    3.  **Selección de Hook:** Vuelva a verificar que ha asignado los bloques a los hooks correctos del front-office (por ejemplo, `displayHome` para el contenido principal, `displayHomeTabContent` para las pestañas, `displayLeftColumn` para las columnas).
    4.  **Borrar caché:** Vaya a **Parámetros avanzados > Rendimiento** y haga clic en "Borrar caché". A veces, el contenido antiguo en caché impide que aparezca la nueva salida del módulo.
    5.  **Compatibilidad del tema:** Si tiene un tema personalizado, intente activar "Detección automática de tema" en la configuración principal del módulo. Si los problemas persisten, su tema podría requerir pequeños ajustes de CSS (consulte la P3).

**P2: Mis bloques de productos se muestran, pero los productos no se actualizan (por ejemplo, precios antiguos, artículos agotados aún visibles).**

-   **R:** Esto suele ser un problema de caché.
    1.  **Caché del módulo:** En la configuración principal del módulo, verifique "Activar caché de bloques" y "TTL de caché (segundos)". Si la caché está activada, el bloque podría estar mostrando una versión antigua en caché. Puede deshabilitar temporalmente la caché, guardar, luego volver a activarla, o simplemente esperar a que expire el TTL.
    2.  **Caché de PrestaShop:** Vaya a **Parámetros avanzados > Rendimiento** y haga clic en "Borrar caché". Esto borra todas las cachés a nivel de PrestaShop.
    3.  **Caché del navegador:** Borre la caché y las cookies de su navegador, o vea su sitio en una ventana de incógnito/privada para asegurarse de que no está viendo una versión almacenada en caché localmente.

**P3: Los bloques de productos aparecen, pero el estilo es incorrecto (por ejemplo, fuentes incorrectas, elementos desalineados, carrusel roto).**

-   **R:**
    1.  **Detección automática de tema:** En la configuración principal del módulo, asegúrese de que "Detección automática de tema" esté activada. Esto ayuda al módulo a usar estilos específicos del tema.
    2.  **Cargar LightSlider:** Si los carruseles están rotos, asegúrese de que "Cargar lightslider" esté activado en la configuración del módulo.
    3.  **Conflictos de tema:** Los temas personalizados a veces tienen CSS o JavaScript conflictivos. Si sospecha esto, intente cambiar temporalmente a un tema predeterminado de PrestaShop (como Classic) para ver si el problema se resuelve. Si lo hace, su tema personalizado necesita ajustes.
    4.  **CSS personalizado:** Es posible que deba agregar CSS personalizado a la hoja de estilos de su tema para anular los estilos predeterminados del módulo y que coincidan con su tema. Un desarrollador web puede ayudar con esto.

**P4: He creado un nuevo bloque de productos, pero no aparece como una pestaña en la página de inicio.**

-   **R:**
    1.  **Activar pestañas internas:** En la configuración principal del módulo, asegúrese de que "Activar pestañas internas" esté configurado en "Sí".
    2.  **Hook correcto:** Asegúrese de que la **Selección de Hook** del bloque de productos esté configurada en `displayHomeTabContent`. Los bloques configurados en `displayHome` o columnas no aparecerán como pestañas.
    3.  **Posicionamiento:** Verifique la posición de sus bloques con pestañas. Si están muy abajo en el orden, es posible que no aparezcan si otros módulos están ocupando espacio.

**P5: Mi editor de texto enriquecido no funciona o no puedo formatear texto.**

-   **R:**
    1.  **Activar editor de texto enriquecido:** En la configuración principal del módulo, asegúrese de que "Usar editor de texto enriquecido" esté configurado en "Sí".
    2.  **Problemas del navegador:** Intente con un navegador web diferente o borre la caché de su navegador actual.
    3.  **Conflictos de JavaScript:** Ocasionalmente, otros módulos o scripts de temas pueden interferir con el editor de texto enriquecido. Si el problema persiste, consulte a un desarrollador.

## 4. Guía para desarrolladores y webmasters (Arquitectura técnica y mapa de código)

Esta sección proporciona una inmersión profunda en la arquitectura técnica y la base de código del módulo "Homepage Products Pro", diseñada para desarrolladores, webmasters y agencias técnicas.

### 4.1 Resumen de la arquitectura

El módulo "Homepage Products Pro" (`hpp`) sigue una arquitectura de módulo estándar de PrestaShop, aprovechando principalmente los hooks para la visualización en el front-office y un método `getContent()` para su configuración en el back-office. Implementa un panel de control personalizado para gestionar bloques de productos, que se almacenan como valores de configuración o potencialmente en tablas de base de datos personalizadas (aunque no se identificaron clases `ObjectModel` explícitas en el inventario proporcionado, los datos complejos a menudo se serializan en `ps_configuration` o se gestionan a través de clases auxiliares). El módulo depende en gran medida de las plantillas Smarty para renderizar sus diversos bloques de productos e interfaces de administración. Integra bibliotecas externas como LightSlider para carruseles y TinyMCE para la edición de texto enriquecido. Los mecanismos de análisis y caché están integrados para el rendimiento y la información.

### 4.2 Controladores (`controllers/`)

#### Controladores del Front-Office

-   `hpp/controllers/front/index.php`
    -   **Nombre de la clase:** `HppIndexModuleFrontController` (probablemente, según la convención de nombres de archivo)
    -   **Clase padre:** `ModuleFrontController`
    -   **Responsabilidad:** Este controlador probablemente sirve como un punto de entrada general para las acciones del módulo del front-office que no encajan en categorías específicas de AJAX o seguimiento. Podría manejar la carga inicial de datos o la representación de tipos de bloques específicos si no está completamente impulsado por hooks.
-   `hpp/controllers/front/lazyblock.php`
    -   **Nombre de la clase:** `HppLazyblockModuleFrontController`
    -   **Clase padre:** `ModuleFrontController`
    -   **Responsabilidad:** Este controlador está diseñado para manejar solicitudes AJAX para la carga diferida de bloques de productos. Cuando un usuario se desplaza o interactúa con una pestaña, este controlador sería llamado para obtener datos de productos y renderizar el HTML para un bloque específico, mejorando los tiempos de carga inicial de la página. Probablemente toma parámetros como ID de bloque, número de página o criterios de filtro.
-   `hpp/controllers/front/track.php`
    -   **Nombre de la clase:** `HppTrackModuleFrontController`
    -   **Clase padre:** `ModuleFrontController`
    -   **Responsabilidad:** Este controlador es responsable de manejar las solicitudes de seguimiento de análisis. Cuando se ve un bloque de productos o se hace clic en un producto dentro de un bloque, se envía una solicitud a este controlador para registrar el evento, contribuyendo a los datos de análisis internos del módulo.

#### Controladores de administración del Back-Office

No se identificaron archivos `AdminController` dedicados en el inventario proporcionado. Esto sugiere que la gestión del back-office del módulo (creación/edición de bloques de productos) se maneja directamente dentro del método `getContent()` del archivo `hpp.php`, utilizando potencialmente las clases `HelperForm` y `HelperList` de PrestaShop, o un enfoque de renderizado personalizado dentro de la página de configuración principal del módulo.

### 4.3 Clases y modelos principales (`classes/`)

No se enumeraron explícitamente clases PHP personalizadas que extiendan `ObjectModel` u otras funcionalidades principales en el directorio `classes/`. Esto implica que:

-   Los datos complejos (como las configuraciones de bloques de productos individuales) probablemente se almacenan como arrays serializados o cadenas JSON dentro de la tabla `ps_configuration`, gestionados directamente por el archivo del módulo `hpp.php`.
-   Alternativamente, el módulo podría usar un enfoque más procedural o depender de clases auxiliares definidas directamente dentro de `hpp.php` o sus bibliotecas incluidas.
-   El directorio `lib/` contiene varias clases auxiliares y bibliotecas externas (por ejemplo, `searchTool`, `smartyTemplatesManager`, `src`). Es probable que se utilicen para funcionalidades específicas como la búsqueda de productos, la gestión de plantillas o la implementación de carruseles, en lugar de definir entidades comerciales principales.

### 4.4 Activos JavaScript (`views/js/`)

-   `hpp/js/script.js`
    -   **Alcance:** Front-office.
    -   **Detalles:** Probablemente contiene la lógica principal del front-office para inicializar carruseles de productos (LightSlider), manejar el cambio de pestañas y las interacciones generales de la interfaz de usuario relacionadas con los bloques de productos. También podría contener lógica para la carga diferida o el seguimiento básico de análisis.
-   `hpp/js/tinymce16-force-urls.inc.js`
    -   **Alcance:** Back-office.
    -   **Detalles:** Un script específico para el editor de texto enriquecido TinyMCE, probablemente para garantizar que las URL se manejen y formateen correctamente dentro del editor, especialmente en contextos de PrestaShop 1.6 más antiguos.
-   `hpp/lib/searchTool/views/js/autocomplete.js`
    -   **Alcance:** Back-office.
    -   **Detalles:** Proporciona la funcionalidad JavaScript para un campo de entrada de búsqueda con autocompletado, utilizado al seleccionar productos específicos para un bloque de productos en la configuración del back-office. Probablemente realiza llamadas AJAX para obtener sugerencias de productos.
-   `hpp/lib/smartyTemplatesManager/js/smartyTemplatesManager.js`
    -   **Alcance:** Back-office.
    -   **Detalles:** Gestiona la creación, edición y selección dinámica de plantillas Smarty dentro de la interfaz del back-office, probablemente para que los usuarios avanzados personalicen los diseños de los bloques.
-   `hpp/lib/src/js/lightslider.js`
    -   **Alcance:** Front-office.
    -   **Detalles:** La biblioteca LightSlider principal, responsable de crear carruseles de contenido responsivos y táctiles para los bloques de productos. Maneja las transiciones de diapositivas, la navegación y la capacidad de respuesta.
-   `hpp/views/js/admin-audience-picker.js`
    -   **Alcance:** Back-office.
    -   **Detalles:** Proporciona la lógica interactiva para la interfaz del "Selector de audiencia" en el back-office, permitiendo a los administradores seleccionar grupos de clientes o países específicos para la visibilidad del bloque.
-   `hpp/views/js/adminHppDashboard.js`
    -   **Alcance:** Back-office.
    -   **Detalles:** El JavaScript principal para el panel de control del back-office del módulo, que maneja interacciones como añadir/editar bloques, reordenación por arrastrar y soltar y la gestión general de la interfaz de usuario.
-   `hpp/views/js/adminHppDashboardDemo.js`
    -   **Alcance:** Back-office.
    -   **Detalles:** Probablemente contiene JavaScript específico de demostración para el panel de control del back-office, posiblemente para la configuración inicial o para mostrar características, y podría no estar activo en un entorno de producción.
-   `hpp/views/js/hpp-analytics.js`
    -   **Alcance:** Front-office.
    -   **Detalles:** Maneja el lado del front-office del seguimiento de análisis, enviando datos (por ejemplo, vistas de bloques, clics en productos) al controlador `track.php` a través de AJAX.
-   `hpp/views/js/hpp-lazyload.js`
    -   **Alcance:** Front-office.
    -   **Detalles:** Implementa la carga diferida para bloques de productos o su contenido, realizando llamadas AJAX a `lazyblock.php` cuando los bloques entran en la ventana gráfica o se activan las pestañas.

### 4.5 Hojas de estilo CSS (`views/css/`)

-   `hpp/css/global.css`
    -   **Alcance:** Front-office.
    -   **Detalles:** Contiene estilos generales y globales para la salida del front-office del módulo, asegurando una coherencia visual básica.
-   `hpp/css/homefeaturedslider.css`
    -   **Alcance:** Front-office.
    -   **Detalles:** Estilos específicos para el componente deslizador de productos destacados de la página de inicio, probablemente para versiones antiguas de PrestaShop o implementaciones específicas de carrusel.
-   `hpp/css/hpp.css`
    -   **Alcance:** Front-office.
    -   **Detalles:** La hoja de estilos principal del front-office para el módulo, que define el aspecto de los bloques de productos, las cuadrículas y los carruseles.
-   `hpp/css/internal-tabs.css`
    -   **Alcance:** Front-office.
    -   **Detalles:** Estilos específicos para la interfaz de pestañas internas en la página de inicio, incluida la navegación por pestañas y las áreas de contenido.
-   `hpp/css.css`
    -   **Alcance:** Front-office.
    -   **Detalles:** Potencialmente una hoja de estilos general heredada o adicional.
-   `hpp/lib/searchTool/views/css/autocomplete.css`
    -   **Alcance:** Back-office.
    -   **Detalles:** Estilos para el campo de búsqueda con autocompletado utilizado en el back-office para la selección de productos.
-   `hpp/lib/smartyTemplatesManager/css/smartyTemplatesManager.css`
    -   **Alcance:** Back-office.
    -   **Detalles:** Estilos para la interfaz del gestor de plantillas Smarty en el back-office.
-   `hpp/lib/src/css/lightslider.css`
    -   **Alcance:** Front-office.
    -   **Detalles:** El CSS principal de la biblioteca LightSlider, que proporciona el estilo base para el componente de carrusel.
-   `hpp/views/css/admin-audience-picker.css`
    -   **Alcance:** Back-office.
    -   **Detalles:** Estilos para la interfaz del selector de audiencia en el back-office.
-   `hpp/views/css/admin-searchtool.css`
    -   **Alcance:** Back-office.
    -   **Detalles:** Estilos adicionales para la herramienta de búsqueda en el panel de administración.
-   `hpp/views/css/admin_hpp.css`
    -   **Alcance:** Back-office.
    -   **Detalles:** La hoja de estilos principal para la configuración y el panel de control del back-office del módulo.
-   `hpp/views/templates/admin/css/css.css`
    -   **Alcance:** Back-office.
    -   **Detalles:** Una hoja de estilos ubicada específicamente dentro del directorio de plantillas de administración, probablemente para necesidades de estilo muy específicas dentro de esas plantillas.

### 4.6 Estructura de plantillas Smarty (`views/templates/`)

#### Plantillas de hook (`views/templates/hook/`)

Estas plantillas se renderizan cuando el módulo se engancha en posiciones específicas del front-office. Muchas son anulaciones específicas del tema.

-   `hpp/views/templates/hook/column17.tpl`
    -   **Hook:** `displayLeftColumn`, `displayRightColumn` (PrestaShop 1.7.x+).
    -   **Salida:** Renderiza un bloque de productos diseñado para las columnas izquierda o derecha, normalmente una lista vertical o una pequeña cuadrícula.
-   `hpp/views/templates/hook/firezy-column17.tpl`
    -   **Hook:** `displayLeftColumn`, `displayRightColumn` (PrestaShop 1.7.x+ para el tema Firezy).
    -   **Salida:** Anulación específica del tema para bloques de productos de columna, adaptada para el tema Firezy.
-   `hpp/views/templates/hook/firezy-homeTab.tpl`
    -   **Hook:** `displayHomeTab` (para el tema Firezy).
    -   **Salida:** Renderiza el enlace de navegación de la pestaña real (por ejemplo, "Colección de Verano") para el tema Firezy.
-   `hpp/views/templates/hook/firezy-homeTabContent.tpl`
    -   **Hook:** `displayHomeTabContent` (para el tema Firezy).
    -   **Salida:** Renderiza el contenido (el bloque de productos en sí) que aparece cuando una pestaña específica está activa, adaptado para el tema Firezy.
-   `hpp/views/templates/hook/firezy-internal-tabs.tpl`
    -   **Hook:** `displayHome` (para el tema Firezy).
    -   **Salida:** Renderiza toda la interfaz de pestañas internas (tanto la navegación como el contenedor de contenido) para el tema Firezy.
-   `hpp/views/templates/hook/firezy-products17.tpl`
    -   **Hook:** `displayHome` (para el tema Firezy).
    -   **Salida:** Renderiza un bloque de productos general (carrusel o cuadrícula) para el área de contenido principal de la página de inicio, adaptado para el tema Firezy.
-   `hpp/views/templates/hook/homeTab.tpl`
    -   **Hook:** `displayHomeTab`.
    -   **Salida:** Renderiza el enlace de navegación de la pestaña genérica.
-   `hpp/views/templates/hook/homeTabContent.tpl`
    -   **Hook:** `displayHomeTabContent`.
    -   **Salida:** Renderiza el contenido genérico para un bloque de productos con pestañas.
-   `hpp/views/templates/hook/hummingbird-column17.tpl`, `hummingbird-homeTab.tpl`, `hummingbird-homeTabContent.tpl`, `hummingbird-internal-tabs.tpl`, `hummingbird-products17.tpl`
    -   **Hook:** Similar a Firezy, estas son anulaciones específicas del tema para el tema Hummingbird, que proporcionan diseños adaptados para columnas, navegación por pestañas, contenido de pestañas, contenedores de pestañas internas y bloques de productos generales.
-   `hpp/views/templates/hook/internal-tabs.tpl`
    -   **Hook:** `displayHome`.
    -   **Salida:** Renderiza la interfaz de pestañas internas genérica (navegación y contenedor de contenido).
-   `hpp/views/templates/hook/products17.tpl`
    -   **Hook:** `displayHome`, `displayTopColumn`.
    -   **Salida:** Renderiza un bloque de productos genérico (carrusel o cuadrícula) para el área de contenido principal de la página de inicio o la columna superior (PrestaShop 1.7.x+).
-   `hpp/views/templates/hook/warehouse-column17.tpl`, `warehouse-homeTab.tpl`, `warehouse-homeTabContent.tpl`, `warehouse-internal-tabs.tpl`, `warehouse-products17.tpl`
    -   **Hook:** Similar a Firezy y Hummingbird, estas son anulaciones específicas del tema para el tema Warehouse, que proporcionan diseños adaptados para columnas, navegación por pestañas, contenido de pestañas, contenedores de pestañas internas y bloques de productos generales.

#### Plantillas de administración (`views/templates/admin/`)

Estas plantillas se utilizan para la interfaz del back-office del módulo.

-   `hpp/views/templates/admin/audience-picker.tpl`
    -   **Salida:** Renderiza el HTML para la interfaz de selección de grupos de clientes y países.
-   `hpp/views/templates/admin/country-priority-picker.tpl`
    -   **Salida:** Renderiza el HTML para seleccionar y priorizar países.
-   `hpp/views/templates/admin/menu.tpl`
    -   **Salida:** Renderiza el menú o la navegación específica del módulo dentro de su panel de control del back-office.
-   `hpp/views/templates/admin/scripts.tpl`
    -   **Salida:** Incluye archivos JavaScript o scripts en línea específicamente para la interfaz de administración.
-   `hpp/views/templates/admin/ul-li.tpl`
    -   **Salida:** Una plantilla de lista genérica, posiblemente utilizada para mostrar listas de elementos u opciones dentro de los formularios de administración.

#### Plantillas de biblioteca (`hpp/lib/`)

Estas plantillas forman parte de bibliotecas integradas.

-   `hpp/lib/searchTool/views/scripts.tpl`
    -   **Salida:** Incluye archivos JavaScript o scripts en línea para la funcionalidad de la herramienta de búsqueda.
-   `hpp/lib/smartyTemplatesManager/tpl/example.tpl`
    -   **Salida:** Una plantilla de ejemplo para el Gestor de Plantillas Smarty, probablemente para demostración o como base.
-   `hpp/lib/smartyTemplatesManager/views/buttonManager.tpl`
    -   **Salida:** Renderiza botones o controles para gestionar plantillas.
-   `hpp/lib/smartyTemplatesManager/views/createTemplateForm.tpl`
    -   **Salida:** Renderiza el formulario para crear nuevas plantillas personalizadas.
-   `hpp/lib/smartyTemplatesManager/views/editTemplateForm.tpl`
    -   **Salida:** Renderiza el formulario para editar plantillas personalizadas existentes.
-   `hpp/lib/smartyTemplatesManager/views/mainForm.tpl`
    -   **Salida:** El formulario principal para la interfaz del Gestor de Plantillas Smarty.
-   `hpp/lib/smartyTemplatesManager/views/selectInput.tpl`
    -   **Salida:** Renderiza un campo de entrada genérico de selección/desplegable.

### 4.7 Esquema de la base de datos y mapa de hooks

#### Tablas de la base de datos

No se identificaron archivos SQL personalizados (`.sql`), y no se enumeraron clases `ObjectModel`. Esto sugiere fuertemente que el módulo almacena sus datos de configuración y definiciones de bloques de productos principalmente dentro de la tabla `ps_configuration` de PrestaShop.

-   **`ps_configuration`**: Esta tabla contendrá entradas con claves como `HPP_ANALYTICS_ENABLED`, `HPP_CACHE_TTL`, `HPP_BLOCKS_DATA` (o similar, donde `HPP_BLOCKS_DATA` contendría un array serializado o una cadena JSON de todas las configuraciones de bloques de productos).

#### Tabla de hooks registrados

El módulo se registra en varios hooks de PrestaShop para inyectar su contenido y funcionalidad.

| Nombre del Hook | Momento de ejecución | Propósito técnico |
| --- | --- | --- |
| `displayHeader` | En la sección `<head>` de cada página. | Inyectar activos CSS y JS (por ejemplo, LightSlider, `hpp.css`, `script.js`). |
| `actionFrontControllerSetMedia` | Antes de que un controlador frontal renderice su salida. | Añadir activos CSS/JS específicos condicionalmente según la página o el controlador. |
| `displayHome` | Área de contenido principal de la página de inicio. | Renderizar bloques de productos generales (carruseles, cuadrículas) directamente en la página de inicio. |
| `displayHomeTab` | Dentro del área de navegación de pestañas de la página de inicio. | Renderizar los enlaces de navegación para pestañas de productos personalizadas. |
| `displayHomeTabContent` | Dentro del área de contenido de pestañas de la página de inicio. | Renderizar los bloques de productos reales que aparecen cuando una pestaña personalizada está activa. |
| `displayLeftColumn` | En la columna izquierda de las páginas donde está activa. | Renderizar bloques de productos verticales en la barra lateral izquierda. |
| `displayRightColumn` | En la columna derecha de las páginas donde está activa. | Renderizar bloques de productos verticales en la barra lateral derecha. |
| `displayTopColumn` | En el área de contenido superior, generalmente debajo del encabezado. | Renderizar bloques de productos en la sección superior de la página de inicio. |
| `displayBackOfficeHeader` | En la sección `<head>` de cada página del back-office. | Inyectar activos CSS y JS para las páginas de configuración del back-office del módulo. |
| `actionAdminControllerSetMedia` | Antes de que un controlador de administración renderice su salida. | Añadir activos CSS/JS específicos para las páginas de administración del módulo. |
| `actionProductUpdate` | Después de que un producto se actualiza en el back-office. | Potencialmente borrar la caché de los bloques que contienen este producto, o reindexar los datos del producto. |
| `actionProductDelete` | Después de que un producto se elimina en el back-office. | Potencialmente borrar la caché de los bloques que contienen este producto, o eliminarlo de las configuraciones de los bloques. |
| `actionCategoryUpdate` | Después de que una categoría se actualiza en el back-office. | Potencialmente borrar la caché de los bloques que muestran productos de esta categoría. |

## 5. Soporte oficial y actualizaciones

Para las últimas actualizaciones, correcciones de errores y soporte oficial para el módulo "Homepage Products Pro", consulte su cuenta de cliente en MyPresta.eu. Nuestro equipo de soporte dedicado está disponible para ayudarle con cualquier problema técnico o pregunta que pueda tener.

-   **Historial de pedidos y descargas de MyPresta.eu:** <https://mypresta.eu/my-account/orders/>
-   **Contacto de soporte de MyPresta.eu:** <https://mypresta.eu/contact>
