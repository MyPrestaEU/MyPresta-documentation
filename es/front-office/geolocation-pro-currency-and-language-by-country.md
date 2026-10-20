---
title: "Geolocalización pro - moneda e idioma por país - Manual del Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop Geolocalización pro - moneda e idioma por país de MyPresta.eu."
sidebar:
  label: "Geolocalización pro - moneda e idioma por país - Manual del Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Geolocation pro - currency and language by country en MyPresta.eu](https://mypresta.eu/modules/front-office-features/geolocation-pro-currency-and-language-by-country.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/front-office/geolocation-pro-currency-and-language-by-country/)
>
> ---


# Geolocalización pro - moneda e idioma por país

## 1. Requisitos y compatibilidad

- **Versiones de PrestaShop compatibles**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilidad con PHP**: PHP 5.6 - 8.5
- **Requisitos de alojamiento**: Las extensiones PHP estándar (cURL, JSON, OpenSSL) suelen ser necesarias y están disponibles en la mayoría de los entornos de alojamiento.

## 2. Recorrido completo por la configuración (Cada ajuste agrupado por pantalla)

### 2.1 Página de configuración del módulo (Back Office > Módulos > Configurar > Geolocalización pro - moneda e idioma por país)

Esta es la pantalla de configuración principal donde habilita o deshabilita la funcionalidad central del módulo y accede a las herramientas de diagnóstico.

-   **Habilitar Geolocation Pro:**

    -   **Qué hace este ajuste:** Este es el interruptor maestro para todo el módulo.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando está habilitado:* El módulo detectará activamente las ubicaciones de los clientes y aplicará sus reglas de moneda e idioma definidas.
        -   *Cuando está deshabilitado:* El módulo estará inactivo, y su tienda volverá a su configuración de moneda e idioma predeterminada para todos los visitantes, independientemente de su ubicación.
    -   **Valor recomendado:** SÍ (para utilizar las características del módulo).
    -   **Escenario / ejemplo de comerciante:** Ha terminado de configurar todas sus reglas y está listo para lanzar experiencias personalizadas. Habilite este interruptor. Si necesita deshabilitar temporalmente la función para mantenimiento, apáguelo.
-   **Mostrar banner con elección de país:**

    -   **Qué hace este ajuste:** Determina si aparece un pequeño banner o ventana emergente para informar a los clientes sobre el país detectado y ofrecerles la opción de cambiarlo.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando está habilitado:* Aparecerá un banner (generalmente en la parte superior o inferior de la pantalla) que muestra el país detectado y, potencialmente, permite al cliente anular manualmente la ubicación, moneda o idioma detectados. Esto puede ser útil para clientes que usan VPN o aquellos que prefieren la configuración de una región diferente.
        -   *Cuando está deshabilitado:* No se mostrará ningún banner. El módulo aplicará silenciosamente las reglas basadas en la detección de IP.
    -   **Valor recomendado:** SÍ (inicialmente, para dar control a los clientes, luego considere NO si prefiere una experiencia completamente fluida y confía en la detección de IP).
    -   **Escenario / ejemplo de comerciante:** Un cliente de EE. UU. está visitando su tienda, y el módulo detecta correctamente su ubicación. Si este ajuste está habilitado, un banner podría decir "Está navegando desde Estados Unidos. [¿Cambiar país?]" Esto les da la oportunidad de corregirlo si están usando una VPN o prefieren comprar desde una región diferente.
-   **Diagnósticos y herramientas:**

    -   **Qué hace este ajuste:** Esta sección proporciona herramientas para probar la funcionalidad del módulo y verificar la detección de IP. No es un ajuste para cambiar, sino una utilidad.
    -   **Efecto de cambiar este ajuste:** Al hacer clic en las herramientas de diagnóstico, se abrirán nuevas vistas o ventanas emergentes que le mostrarán información sobre su dirección IP actual, el país detectado y cómo el módulo aplicaría las reglas.
    -   **Valor recomendado:** Úselo siempre que esté configurando nuevas reglas o solucionando problemas.
    -   **Escenario / ejemplo de comerciante:** Ha creado una regla para Alemania. Puede usar la herramienta de diagnóstico para simular una visita desde Alemania y ver si se aplican la moneda y el idioma correctos, asegurándose de que sus reglas funcionen como se espera.

### 2.2 Pantalla de administración dedicada: Reglas Geo (Back Office > Módulos > Geolocalización pro > Reglas Geo)

Esta pantalla le permite definir y gestionar las reglas principales de moneda e idioma según el país.

-   **Nombre de la pantalla y ubicación del menú:** **Back Office > Módulos > Geolocalización pro - moneda e idioma por país > Reglas Geo** (o ruta similar bajo el elemento de menú principal del módulo).
-   **Acciones y configuraciones disponibles:**
    -   **Tabla de listado:** Muestra todas sus reglas geoexistentes, mostrando el país, la moneda asignada y el idioma asignado.
    -   **Añadir nueva regla Geo:** Un botón para crear una nueva regla.
    -   **Acciones de editar/eliminar:** Iconos junto a cada regla para modificarla o eliminarla.
-   **Efecto de los cambios:**
    -   **Añadir una nueva regla:** Cuando añade una regla (por ejemplo, para "Alemania" para usar "EUR" y "Alemán"), cualquier visitante detectado como de Alemania tendrá automáticamente su moneda e idioma establecidos en estos valores.
    -   **Editar una regla:** Modificar una regla existente cambiará instantáneamente el comportamiento del módulo para los visitantes de ese país específico.
    -   **Eliminar una regla:** Eliminar una regla significa que los visitantes de ese país ya no tendrán una moneda o idioma específico aplicado por este módulo y volverán a la configuración predeterminada de su tienda.
-   **Flujo de trabajo recomendado para la gestión diaria de la tienda:**
    1.  **Identificar países objetivo:** Decida qué países desea segmentar con monedas e idiomas específicos.
    2.  **Asegurarse de que las monedas/idiomas estén habilitados:** Asegúrese de que las monedas y los idiomas que desea asignar ya estén habilitados en su tienda PrestaShop (Back Office > Internacional > Monedas / Idiomas).
    3.  **Crear reglas:** Para cada país, haga clic en "Añadir nueva regla Geo", seleccione el país del menú desplegable y luego seleccione la moneda y el idioma deseados. Guarde la regla.
    4.  **Probar con diagnósticos:** Utilice las herramientas de diagnóstico del módulo para verificar que sus reglas funcionan como se espera.

### 2.3 Pantalla de administración dedicada: Reglas de idioma (Back Office > Módulos > Geolocalización pro > Reglas de idioma)

Esta pantalla parece ser una interfaz duplicada o alternativa para gestionar reglas específicas de idioma, que potencialmente ofrece un control más granular o una vista diferente. Dada la descripción del módulo, la pantalla "Reglas Geo" es probablemente la interfaz principal para las asignaciones basadas en países. Esta pantalla podría ser para anulaciones más avanzadas y específicas de idioma no vinculadas directamente a un país.

-   **Nombre de la pantalla y ubicación del menú:** **Back Office > Módulos > Geolocalización pro - moneda e idioma por país > Reglas de idioma** (o ruta similar).
-   **Acciones y configuraciones disponibles:**
    -   **Tabla de listado:** Muestra las reglas de idioma existentes.
    -   **Añadir nueva regla de idioma:** Botón para crear una nueva regla.
    -   **Acciones de editar/eliminar:** Iconos para modificar o eliminar reglas.
-   **Efecto de los cambios:** Es probable que estas reglas anulen o complementen las reglas basadas en el país para el idioma. Por ejemplo, podría tener una regla general para "Inglés" para todos los países no especificados, y luego usar esta pantalla para excepciones o comportamientos de idioma específicos.
-   **Flujo de trabajo recomendado para la gestión diaria de la tienda:** Utilice esta pantalla si necesita gestionar la configuración de idioma independientemente de las reglas geográficas específicas del país, o si encuentra escenarios en los que una regla de país no es suficiente para la gestión del idioma. De lo contrario, concéntrese en la pantalla "Reglas Geo".

### 2.4 Tabla de referencia rápida de configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| **Configuración del módulo** | Habilitar Geolocation Pro | SÍ | Interruptor maestro para la funcionalidad del módulo. SÍ activa la detección de moneda/idioma basada en el país. |
|  | Mostrar banner con elección de país | SÍ | Muestra un banner informando a los clientes del país detectado y permitiendo la anulación manual. |
|  | Diagnósticos y herramientas | N/A | Utilidad para probar la detección de IP y la aplicación de reglas. |
| **Reglas Geo** | Añadir/Editar Regla Geo (País, Moneda, Idioma) | N/A | Define qué moneda e idioma se establecen automáticamente para los visitantes de un país específico. |
| **Reglas de idioma** | Añadir/Editar Regla de idioma | N/A | (Potencialmente) Define anulaciones de idioma o comportamientos de idioma específicos, posiblemente independientes del país. |

## 3. Solución de problemas del comerciante y preguntas frecuentes (FAQ)

**P1: Mis clientes siguen viendo la moneda/idioma incorrectos incluso después de configurar las reglas. ¿Qué pasa?**
R1:

-   **¿Está habilitado el módulo?** Vuelva a verificar la configuración "Habilitar Geolocation Pro" en la página de configuración principal.
-   **¿Son correctas sus reglas?** Vaya a "Reglas Geo" y asegúrese de que el país, la moneda y el idioma estén asignados correctamente.
-   **¿Están habilitadas las monedas/idiomas en PrestaShop?** Asegúrese de que las monedas y los idiomas que intenta asignar estén activos en su PrestaShop (Internacional > Monedas / Idiomas).
-   **Borre la caché de su navegador:** A veces, su navegador puede almacenar en caché configuraciones antiguas. Pida a los clientes que borren la caché de su navegador o que prueben una ventana de incógnito.
-   **Borre la caché de PrestaShop:** Vaya a **Parámetros avanzados > Rendimiento** y haga clic en "Borrar caché" en la parte superior derecha.
-   **Pruebe con Diagnósticos:** Utilice las herramientas de diagnóstico integradas del módulo para simular una visita desde un país específico y ver qué moneda/idioma aplica. Esto ayuda a determinar si el problema es con la detección o la aplicación de reglas.

**P2: El módulo detecta el país incorrecto para algunos clientes. ¿Por qué?**
R2:

-   **VPN y Proxies:** Los clientes que utilizan Redes Privadas Virtuales (VPN) o servidores proxy aparecerán como si estuvieran navegando desde la ubicación de su VPN/proxy, no desde su ubicación física real. El módulo se basa en la detección de direcciones IP, que puede ser falsificada.
-   **Precisión de la base de datos IP:** Las bases de datos de geolocalización son generalmente muy precisas, pero no 100% perfectas. Algunos rangos de IP pueden estar mal identificados.
-   **"Mostrar banner con elección de país":** Si esta configuración está habilitada, los clientes pueden corregir manualmente el país detectado, que es la mejor solución para estos casos extremos.

**P3: ¿Cómo añado una nueva moneda o idioma a mi tienda para poder usarlo en una regla geográfica?**
R3:

-   **Añadir una moneda:** Vaya a **Internacional > Monedas** en su Back Office de PrestaShop. Haga clic en "Añadir nueva moneda", rellene los detalles y habilítela.
-   **Añadir un idioma:** Vaya a **Internacional > Idiomas** en su Back Office de PrestaShop. Haga clic en "Añadir nuevo idioma", rellene los detalles y habilítelo. Recuerde también instalar paquetes de idioma y traducir su contenido para el nuevo idioma.

**P4: ¿Este módulo ralentizará mi sitio web?**
R4: El módulo realiza una búsqueda rápida de IP y una aplicación de reglas, lo que generalmente es muy rápido y optimizado. No debería afectar notablemente la velocidad de carga de su sitio web. Si experimenta algún problema de rendimiento, asegúrese de que la caché de su PrestaShop esté habilitada y se borre regularmente.

**Q5: Quiero personalizar el estilo del banner de elección de país para que coincida con mi tema. ¿Cómo puedo hacerlo?**
R5: El banner utiliza clases CSS específicas. Si bien no se recomienda la modificación directa de los archivos del módulo (ya que las actualizaciones los sobrescribirían), un desarrollador web puede usar el archivo CSS personalizado de su tema para anular los estilos predeterminados. Inspeccionarían el banner usando las herramientas de desarrollador del navegador para identificar los selectores CSS relevantes (por ejemplo, clases como `.progeo-banner`, `.progeo-choice`) y luego aplicarían sus propios estilos.

## 4. Guía para desarrolladores y webmasters (Arquitectura técnica y mapa de código)

Esta sección es estrictamente para desarrolladores, webmasters de tiendas y agencias técnicas que mantienen o extienden la tienda.

### 4.1 Resumen de la arquitectura

El módulo "Geolocalización pro - moneda e idioma por país" (`progeo`) está diseñado para integrarse profundamente con las características de internacionalización principales de PrestaShop. Principalmente aprovecha las anulaciones para modificar cómo PrestaShop determina la `Configuration`, `Currency` y `Language` activas basándose en la dirección IP del visitante. Sigue una estructura de módulo estándar de PrestaShop, utilizando controladores frontales y de administración, clases personalizadas (especialmente para entidades `ObjectModel`) y plantillas Smarty tanto para la configuración como para la visualización del front-office (por ejemplo, el banner de elección de país). La lógica central del módulo reside en su `index.php` (archivo principal del módulo) y las clases principales anuladas.

### 4.2 Controladores (`controllers/`)

#### Controladores de Front-Office

-   `progeo/controllers/front/choice.php`
    -   **Nombre de la clase y clase padre:** `ProgeoChoiceModuleFrontController` extiende `ModuleFrontController`.
    -   **Responsabilidad:** Este controlador maneja las solicitudes AJAX relacionadas con el banner de elección de país. Cuando un cliente interactúa con el banner (por ejemplo, selecciona un país, moneda o idioma diferente), este controlador procesa la solicitud, actualiza las variables de sesión o las cookies y, potencialmente, redirige al usuario para aplicar las nuevas configuraciones. Es crucial para el aspecto interactivo del banner.
-   `progeo/controllers/front/index.php`
    -   **Nombre de la clase y clase padre:** `ProgeoIndexModuleFrontController` extiende `ModuleFrontController`.
    -   **Responsabilidad:** Este controlador podría servir como un respaldo o un punto de entrada simple para las acciones del módulo en el front-office, aunque `choice.php` es más específico para la interactividad del banner. En muchos módulos, `index.php` en `controllers/front` es un marcador de posición o maneja solicitudes de front-office muy básicas y no específicas.

#### Controladores de administración de Back-Office

-   `progeo/controllers/admin/AdminGeorulesController.php`
    -   **Nombre de la pestaña y entidad gestionada:** "Reglas Geo" (bajo el menú principal del módulo). Gestiona entidades `Georule`.
    -   **Responsabilidad:** Este es el controlador principal para gestionar las asignaciones de moneda e idioma específicas del país. Proporciona la interfaz CRUD (Crear, Leer, Actualizar, Eliminar) para los registros `ps_progeo_georule`, lo que permite a los administradores definir qué moneda e idioma deben estar activos para los visitantes de países específicos. Extiende `AdminController` y utiliza `HelperList` para la cuadrícula y `HelperForm` para los formularios de añadir/editar.
-   `progeo/controllers/admin/AdminLangrules.php`
    -   **Nombre de la pestaña y entidad gestionada:** "Reglas de idioma" (bajo el menú principal del módulo). Gestiona entidades `Langrule`.
    -   **Responsabilidad:** Este controlador gestiona las reglas específicas del idioma. Proporciona una interfaz CRUD para los registros `ps_progeo_langrule`. Es probable que se utilice para un control de idioma más granular, que potencialmente anule o complemente el idioma establecido en `AdminGeorulesController`.
-   `progeo/controllers/admin/AdminLangrulesController.php`
    -   **Nombre de la pestaña y entidad gestionada:** "Reglas de idioma" (bajo el menú principal del módulo). Gestiona entidades `Langrule`.
    -   **Responsabilidad:** Esto parece ser un duplicado o una implementación alternativa de `AdminLangrules.php`. En un módulo PrestaShop típico, `AdminLangrulesController.php` sería la convención de nomenclatura estándar. Los desarrolladores deben verificar qué archivo está siendo utilizado realmente por el registro del menú del módulo.
-   `progeo/controllers/admin/index.php`
    -   **Nombre de la pestaña y entidad gestionada:** No es una pestaña directa, sino un marcador de posición estándar.
    -   **Responsabilidad:** Este archivo suele estar presente en los directorios `controllers/admin`, pero normalmente está vacío o contiene medidas de seguridad básicas (por ejemplo, `die('Forbidden');`). No gestiona una entidad específica ni proporciona una interfaz de usuario.

### 4.3 Clases y modelos principales (`classes/`)

El módulo utiliza anulaciones para inyectar su lógica en el comportamiento principal de PrestaShop.

-   `progeo/override/classes/Configuration.php`
    -   **Responsabilidad:** Anula la clase `Configuration` principal. Esto es fundamental para que el módulo modifique los valores de configuración global (como `PS_CURRENCY_DEFAULT` o `PS_LANG_DEFAULT`) sobre la marcha basándose en la geolocalización, sin cambiar realmente los valores de la base de datos para otros visitantes. Garantiza que cuando PrestaShop solicita un valor de configuración, el módulo pueda interceptarlo y devolver uno localizado.
-   `progeo/override/classes/Currency.php`
    -   **Responsabilidad:** Anula la clase `Currency` principal. Esta anulación permite al módulo manipular qué moneda se considera "activa" o "predeterminada" para el visitante actual, asegurando que los precios se muestren correctamente según la regla geográfica.
-   `progeo/override/classes/Language.php`
    -   **Responsabilidad:** Anula la clase `Language` principal. Similar a `Currency.php`, esta anulación permite al módulo establecer el idioma activo para el visitante actual basándose en la geolocalización, asegurando que el contenido se muestre en el idioma correcto.
-   `progeo/override/classes/index.php`
    -   **Responsabilidad:** Archivo `index.php` vacío estándar para seguridad en un directorio.
-   `progeo/override/classes/_Configuration.php`
    -   **Responsabilidad:** Este nombre de archivo sugiere una posible copia de seguridad o una versión anterior de la anulación de `Configuration`. En un entorno de producción, solo una anulación de `Configuration.php` debería estar activa. Los desarrolladores deben verificar el proceso de instalación del módulo para asegurarse de que se utiliza la anulación correcta.

### 4.4 Activos JavaScript (`views/js/`)

-   `progeo/views/js/banner.js`
    -   **Alcance:** Front-office.
    -   **Responsabilidad:** Este script maneja el banner interactivo de elección de país.
        -   **Escuchadores de eventos:** Vincula eventos a elementos dentro del banner (por ejemplo, eventos de clic en botones de "cambiar país", cambios en cuadros de selección para moneda/idioma).
        -   **Llamadas AJAX:** Realiza solicitudes AJAX al `ProgeoChoiceModuleFrontController` (por ejemplo, `choice.php`) para actualizar el país, la moneda o el idioma seleccionados por el usuario.
        -   **Manipulación del DOM:** Muestra/oculta el banner, actualiza el contenido de texto basándose en las selecciones del usuario y, potencialmente, redirige el navegador después de realizar una elección.
        -   **Cookies/Almacenamiento local:** Puede almacenar las preferencias del usuario en cookies o almacenamiento local para recordar su elección en diferentes sesiones.

### 4.5 Hojas de estilo CSS (`views/css/`)

-   `progeo/views/css/admin.css`
    -   **Alcance:** Estilo del formulario de administración del Back-office.
    -   **Responsabilidad:** Proporciona estilos específicos para las páginas de configuración del módulo y los controladores de administración (por ejemplo, `AdminGeorulesController`, `AdminLangrulesController`). Esto garantiza una apariencia consistente dentro del back office de PrestaShop y mejora la usabilidad de los formularios y listas del módulo.
-   `progeo/views/css/banner.css`
    -   **Alcance:** Estilo del cliente del Front-office.
    -   **Responsabilidad:** Estiliza el banner de elección de país que aparece en el front office. Define la posición, los colores, las fuentes, la capacidad de respuesta y la presentación visual general del banner. Los desarrolladores pueden anular estos estilos en el CSS personalizado de su tema para integrar el banner sin problemas con el diseño de la tienda. Los selectores clave pueden incluir `.progeo-banner`, `.progeo-choice-form`, etc.

### 4.6 Estructura de plantillas Smarty (`views/templates/`)

-   **Plantillas de gancho (`views/templates/hook/`)**:
    -   `progeo/views/displayHeader.tpl`: Es probable que esta plantilla esté enganchada a `displayHeader` (o `actionFrontControllerSetMedia`) para incluir los archivos CSS y JS necesarios para el banner del front-office, o para inyectar variables JavaScript iniciales.
-   **Plantillas de administración (`views/templates/admin/`)**:
    -   `progeo/views/advert.tpl`: Probablemente se utiliza para mostrar mensajes promocionales o enlaces a otros módulos de MyPresta.eu dentro de la configuración del módulo.
    -   `progeo/views/banner.tpl`: Esta plantilla probablemente se utiliza dentro de la configuración del módulo para previsualizar o gestionar la configuración relacionada con el banner del front-office.
    -   `progeo/views/currenciesForm.tpl`: Plantilla para gestionar la configuración relacionada con la moneda, posiblemente dentro de la configuración principal o una pantalla de administración dedicada.
    -   `progeo/views/diagnostics-layer1.tpl`, `progeo/views/diagnostics-layer2.tpl`, `progeo/views/diagnostics-overview.tpl`, `progeo/views/diagnostics-result.tpl`, `progeo/views/diagnostics.tpl`: Estas plantillas se utilizan para renderizar las diversas herramientas de diagnóstico y su salida, ayudando al administrador a solucionar problemas de detección de IP y aplicación de reglas.
    -   `progeo/views/languagesForm.tpl`: Plantilla para gestionar la configuración relacionada con el idioma, similar a `currenciesForm.tpl`.
    -   `progeo/views/tabs.tpl`: Se utiliza para renderizar pestañas de navegación dentro de la interfaz de configuración del módulo, lo que permite al administrador cambiar entre diferentes secciones de configuración (por ejemplo, "Reglas Geo", "Reglas de idioma", "Configuración").
    -   `progeo/views/tools-hint.tpl`, `progeo/views/tools.tpl`: Plantillas para mostrar sugerencias o herramientas generales dentro de la interfaz de back-office del módulo.
-   **Plantillas de front-office (`views/templates/front/`)**:
    -   `progeo/views/banner.tpl`: Esta es la plantilla real para el banner de elección de país del front-office, renderizada al cliente. Contiene la estructura HTML para mostrar el país, la moneda, el idioma detectados y las opciones de selección manual.

### 4.7 Esquema de la base de datos y mapa de ganchos

-   **Tablas de la base de datos**:

    -   `ps_progeo_georule`: Almacena las reglas principales de geolocalización.
        -   `id_progeo_georule` (Clave primaria)
        -   `id_country` (Clave externa a `ps_country`)
        -   `id_currency` (Clave externa a `ps_currency`)
        -   `id_lang` (Clave externa a `ps_lang`)
    -   `ps_progeo_langrule`: Almacena reglas específicas del idioma (los detalles dependerían de su implementación específica, pero probablemente una estructura similar para las anulaciones de idioma).
        -   `id_progeo_langrule` (Clave primaria)
        -   `id_lang` (Clave externa a `ps_lang`)
        -   (Potencialmente otros campos para comportamientos de idioma específicos)
    -   Registros de configuración en `ps_configuration`:
        -   `PROGEO_ENABLED`: (1 o 0) Interruptor maestro para el módulo.
        -   `PROGEO_SHOW_BANNER`: (1 o 0) Si se muestra el banner de elección de país.
        -   (Otras claves de configuración según se definen en `getContent()` e `install()`)
-   **Tabla de ganchos registrados**:

| Nombre del gancho | Momento de ejecución | Propósito técnico |
| --- | --- | --- |
| `displayHeader` | En la sección `<head>` de cada página del front-office. | Para incluir activos CSS y JavaScript (`banner.css`, `banner.js`) para el banner del front-office, y potencialmente para inyectar variables JavaScript iniciales o renderizar el propio banner. |
| `actionFrontControllerSetMedia` | Se ejecuta cuando un controlador frontal está configurando sus activos multimedia. | Similar a `displayHeader`, utilizado para añadir archivos CSS y JS condicionalmente o de una manera más moderna de PrestaShop. |
| `actionModuleInstall` | Durante la instalación del módulo. | Para crear tablas de la base de datos (`ps_progeo_georule`, `ps_progeo_langrule`), registrar ganchos y establecer valores de configuración predeterminados. |
| `actionModuleUninstall` | Durante la desinstalación del módulo. | Para eliminar tablas de la base de datos, anular el registro de ganchos y limpiar los valores de configuración. |
| `displayBackOfficeHeader` | En la sección `<head>` de cada página del back-office. | Para incluir `admin.css` para las páginas de configuración del módulo y, potencialmente, JavaScript específico de administración. |
| `actionAdminControllerSetMedia` | Se ejecuta cuando un controlador de administración está configurando sus activos multimedia. | Similar a `displayBackOfficeHeader`, para añadir CSS y JS de administración. |
| `actionDispatcherBefore` | Antes de que el despachador procese una solicitud. | Crucial para la lógica central del módulo: para detectar la IP del visitante, aplicar la regla geográfica y establecer la moneda y el idioma correctos del `Context` *antes* de que PrestaShop renderice la página. Aquí es donde se activan efectivamente las anulaciones. |
| `displayBanner` (Gancho personalizado) | Potencialmente un gancho personalizado para renderizar el banner del front-office. | Si `displayBanner` es un gancho personalizado, el módulo se registraría para renderizar `banner.tpl` en esta ubicación específica. |

## 5. Soporte oficial y actualizaciones

Para obtener las últimas actualizaciones, correcciones de errores y soporte profesional para el módulo "Geolocalización pro - moneda e idioma por país", consulte su cuenta de cliente en [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nuestro equipo se dedica a garantizar que su módulo funcione de manera óptima y se integre sin problemas con su tienda PrestaShop.
