---
title: "Configuración de localización Multistore - idioma y moneda - Manual de Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop 'Configuración de localización Multistore - idioma y moneda' de MyPresta.eu."
sidebar:
  label: "Configuración de localización Multistore - idioma y moneda - Manual de Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Multistore localization settings - language and currency en MyPresta.eu](https://mypresta.eu/modules/administration-tools/multistore-localization-settings-language-and-currency.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/back-office-tools/multistore-localization-settings-language-and-currency/)
>
> ---


# Configuración de localización Multistore - idioma y moneda

## 1. Requisitos y Compatibilidad

- **Versiones de PrestaShop compatibles**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilidad con PHP**: PHP 7.1 - 8.5
- **Requisitos de alojamiento**: Extensiones PHP estándar (cURL, JSON, OpenSSL). Su entorno de alojamiento debe ser compatible con la función Multistore de PrestaShop.

## 2. Recorrido completo de configuración (Cada ajuste agrupado por pantalla)

Este módulo introduce un nuevo elemento de menú en su Back Office de PrestaShop para gestionar las reglas de localización de cada una de sus tiendas.

### 2.1 Página de configuración del módulo (Back Office > Módulos > Configurar)

Cuando haga clic por primera vez en "Configurar" después de la instalación, aterrizará en una página de configuración básica. Esta página sirve principalmente como punto de entrada a la interfaz de gestión principal.

-   **Qué hace este ajuste:** Esta pantalla probablemente contendrá un mensaje simple o un botón que lo dirigirá al área de gestión dedicada para las reglas de localización Multistore. También podría incluir información sobre la versión del módulo o un enlace de soporte.
-   **Efecto de cambiar este ajuste:** Al hacer clic en cualquier botón o enlace aquí, navegará a la interfaz principal donde definirá sus reglas de idioma y moneda específicas de la tienda.
-   **Valor recomendado:** Siga las instrucciones en pantalla, generalmente haciendo clic en un botón para continuar con la configuración principal.
-   **Escenario / ejemplo de comerciante:** Después de la instalación, verá un mensaje como "Haga clic aquí para gestionar sus reglas de localización Multistore". Hará clic en esto para acceder a la funcionalidad principal.

### 2.2 Pantalla de administración dedicada: Reglas de localización Multistore (Back Office > Reglas de localización Multistore)

Este es el panel de control principal del módulo. Encontrará este nuevo elemento de menú en **Parámetros de la tienda > Reglas de localización Multistore** (o similar, dependiendo de su versión de PrestaShop y la estructura del menú).

Al ingresar a esta pantalla, verá una lista (cuadrícula) de sus tiendas existentes. Para cada tienda, podrá definir sus configuraciones específicas de idioma y moneda.

**Acciones y configuraciones disponibles:**

1.  **Lista de tiendas / Vista de cuadrícula:**

    -   **Propósito:** Esta tabla muestra todas las tiendas que ha configurado en su configuración Multistore de PrestaShop.
    -   **Columnas:** Normalmente verá columnas como "Nombre de la tienda" y, potencialmente, "Acciones" o "Configurar".
    -   **Efecto de los cambios:** Esta vista le permite ver rápidamente qué tiendas están configuradas y proporciona el punto de entrada para editar sus configuraciones de localización.
2.  **Botón Editar/Configurar para cada tienda:**

    -   **Qué hace este botón:** Al hacer clic en este botón (a menudo un icono de lápiz) junto al nombre de una tienda, se abrirá un formulario de configuración detallado específicamente para esa tienda.
    -   **Efecto de cambiar este ajuste:** Aquí es donde define los idiomas y monedas específicos para la tienda seleccionada.

**Dentro del formulario de configuración específico de la tienda:**

Cuando haga clic para editar una tienda, verá dos secciones principales: **Idiomas** y **Monedas**.

#### 2.2.1 Configuración de idiomas para [Nombre de la tienda]

-   **Lista de idiomas disponibles:**

    -   **Qué hace este ajuste:** Esta sección presenta una lista de todos los idiomas instalados en su tienda PrestaShop. Para cada idioma, normalmente verá una casilla de verificación.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando está marcado:* El idioma estará disponible para su selección por parte de los clientes en el front office de esta tienda específica.
        -   *Cuando no está marcado:* El idioma NO se mostrará en el selector de idioma para esta tienda, y los clientes no podrán cambiar a él.
    -   **Valor recomendado:** Marque solo los idiomas relevantes para el público objetivo de esta tienda específica.
    -   **Escenario / ejemplo de comerciante:** Para su "Tienda francesa", marcaría "Français (Francés)" y desmarcaría todos los demás idiomas.
-   **Idioma predeterminado para [Nombre de la tienda]:**

    -   **Qué hace este ajuste:** Una selección de menú desplegable o botón de radio que le permite elegir uno de los idiomas *habilitados* como predeterminado para esta tienda.
    -   **Efecto de cambiar este ajuste:** Cuando un cliente visita esta tienda por primera vez, se cargará automáticamente en el idioma predeterminado seleccionado. Si el cliente ha seleccionado previamente un idioma, su preferencia podría ser recordada, pero para los nuevos visitantes, se aplica este valor predeterminado.
    -   **Valor recomendado:** Establezca el idioma principal para el público objetivo de la tienda.
    -   **Escenario / ejemplo de comerciante:** Para su "Tienda francesa", establecería "Français (Francés)" como idioma predeterminado.

#### 2.2.2 Configuración de monedas para [Nombre de la tienda]

-   **Lista de monedas disponibles:**

    -   **Qué hace este ajuste:** Esta sección presenta una lista de todas las monedas instaladas en su tienda PrestaShop. Para cada moneda, normalmente verá una casilla de verificación.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando está marcado:* La moneda estará disponible para su selección por parte de los clientes en el front office de esta tienda específica. Los precios se mostrarán en esta moneda si se selecciona.
        -   *Cuando no está marcado:* La moneda NO se mostrará en el selector de moneda para esta tienda, y los clientes no podrán ver los precios en ella.
    -   **Valor recomendado:** Marque solo las monedas relevantes para el público objetivo de esta tienda específica.
    -   **Escenario / ejemplo de comerciante:** Para su "Tienda de EE. UU.", marcaría "Dólar estadounidense ($)" y desmarcaría "Euro (€)" y otras monedas.
-   **Moneda predeterminada para [Nombre de la tienda]:**

    -   **Qué hace este ajuste:** Una selección de menú desplegable o botón de radio que le permite elegir una de las monedas *habilitadas* como predeterminada para esta tienda.
    -   **Efecto de cambiar este ajuste:** Cuando un cliente visita esta tienda por primera vez, todos los precios se mostrarán automáticamente en la moneda predeterminada seleccionada.
    -   **Valor recomendado:** Establezca la moneda principal para el público objetivo de la tienda.
    -   **Escenario / ejemplo de comerciante:** Para su "Tienda de EE. UU.", establecería "Dólar estadounidense ($)" como moneda predeterminada.

**Flujo de trabajo recomendado para la gestión diaria de la tienda:**

1.  Navegue a **Parámetros de la tienda > Reglas de localización Multistore**.
2.  Identifique la tienda que desea configurar de la lista.
3.  Haga clic en el botón "Editar" o "Configurar" junto a esa tienda.
4.  En la sección "Idiomas", marque todos los idiomas que desea que estén disponibles para esta tienda específica.
5.  Seleccione uno de los idiomas *marcados* como "Idioma predeterminado" para esta tienda.
6.  En la sección "Monedas", marque todas las monedas que desea que estén disponibles para esta tienda específica.
7.  Seleccione una de las monedas *marcadas* como "Moneda predeterminada" para esta tienda.
8.  Haga clic en "Guardar" para aplicar sus cambios.
9.  Repita para cualquier otra tienda en su configuración Multistore.
10. **Siempre borre la caché de PrestaShop** (Parámetros avanzados > Rendimiento) después de realizar cambios para asegurarse de que se reflejen inmediatamente en el front office.

### 2.3 Tabla de referencia rápida de configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e impacto |
| --- | --- | --- | --- |
| **Reglas de localización Multistore (Vista de lista)** | Botón Editar/Configurar | N/A | Accede a la configuración detallada de idioma/moneda para una tienda específica. |
| **Configuración específica de la tienda (Idiomas)** | Idiomas disponibles (casillas de verificación) | Marcar los relevantes | Controla qué idiomas aparecen en el selector del front office para esta tienda. |
| **Configuración específica de la tienda (Idiomas)** | Idioma predeterminado | Idioma principal para el público de la tienda | Establece el idioma inicial para los nuevos visitantes de esta tienda. |
| **Configuración específica de la tienda (Monedas)** | Monedas disponibles (casillas de verificación) | Marcar las relevantes | Controla qué monedas aparecen en el selector del front office para esta tienda. |
| **Configuración específica de la tienda (Monedas)** | Moneda predeterminada | Moneda principal para el público de la tienda | Establece la moneda inicial para los nuevos visitantes de esta tienda. |

## 3. Solución de problemas del comerciante y preguntas frecuentes (FAQ)

**P: He configurado los idiomas/monedas, pero no cambian en mi front office.**
R: La razón más común para esto es la caché. Vaya a **Parámetros avanzados > Rendimiento** en su Back Office de PrestaShop y haga clic en "Borrar caché" (o "Borrar caché de Smarty" y "Borrar caché" para todas las cachés). Además, intente borrar la caché de su navegador.

**P: Mi tema personalizado no parece respetar la configuración del módulo para los selectores de idioma/moneda.**
R: Este módulo controla *qué* opciones están disponibles, pero su tema dicta *cómo* se muestran esas opciones. Si su tema tiene selectores de idioma/moneda muy personalizados, podría estar anulando el comportamiento estándar de PrestaShop.
\* **Solución:** Consulte la documentación de su tema o póngase en contacto con el desarrollador de su tema. Es posible que deba realizar pequeños ajustes en los archivos `.tpl` de su tema para asegurarse de que estén utilizando las variables estándar `languages` y `currencies` de PrestaShop, que este módulo modifica.

**P: ¿Puedo establecer diferentes idiomas/monedas predeterminados para diferentes grupos de clientes?**
R: No, este módulo establece el idioma y la moneda predeterminados *por tienda*, no por grupo de clientes. El valor predeterminado se aplica a todos los visitantes de esa tienda específica. Los clientes pueden cambiarlo manualmente si hay otras opciones disponibles.

**P: ¿Qué sucede si desactivo un idioma/moneda que actualmente está configurado como predeterminado para una tienda?**
R: El módulo debería evitar que haga esto o revertir automáticamente al siguiente idioma/moneda disponible. Asegúrese siempre de que su valor predeterminado elegido sea una de las opciones *habilitadas* para esa tienda. Si encuentra problemas, vuelva a habilitar un valor predeterminado adecuado y borre su caché.

**P: Solo tengo una tienda. ¿Necesito este módulo?**
R: No, este módulo está diseñado específicamente para la función Multistore de PrestaShop. Si solo tiene una tienda, la configuración de localización predeterminada de PrestaShop (en Internacional > Localización) es suficiente.

## 4. Guía para desarrolladores y webmasters (Arquitectura técnica y mapa de código)

Esta sección proporciona una inmersión profunda en la implementación técnica del módulo "Configuración de localización Multistore - idioma y moneda" para desarrolladores y webmasters.

### 4.1 Resumen de la arquitectura

El módulo extiende principalmente el comportamiento de localización central de PrestaShop al anular las clases `Currency` y `Language`. Introduce un controlador de administración personalizado (`AdminMultirulesController`) para gestionar las reglas de localización específicas de la tienda, que se almacenan en una tabla de base de datos personalizada. El módulo aprovecha el patrón MVC de PrestaShop para su interfaz de Back Office y utiliza anulaciones para inyectar su lógica en el proceso de selección de idioma y moneda del front office.

### 4.2 Controladores (`controllers/`)

-   **Controladores de Front-Office**: Este módulo no incluye ningún controlador de front-office dedicado. Su lógica de front-office se inyecta a través de anulaciones de clases y hooks.
-   **Controladores de administración de Back-Office**:

    -   `multishoplang/controllers/admin/AdminMultirules.php`
        -   **Nombre de la clase y clase padre**: `AdminMultirulesController` extiende `ModuleAdminController`.
        -   **Responsabilidad**: Este controlador gestiona la lista y edición de las reglas de localización para cada tienda. Es responsable de mostrar la cuadrícula de tiendas, manejar el formulario para seleccionar los idiomas y monedas disponibles para una tienda específica y guardar estas configuraciones en la base de datos. Probablemente utiliza `HelperList` para la cuadrícula de tiendas y `HelperForm` para la configuración específica de la tienda.
        -   **Nombre de la pestaña**: "Reglas de localización Multistore" (o similar, definido en el método `installTab()`).
    -   `multishoplang/controllers/admin/index.php`
        -   **Nombre de la clase y clase padre**: Este suele ser un archivo vacío o un archivo que contiene una declaración de seguridad `die()` para evitar el acceso directo al directorio. No representa un controlador activo.

### 4.3 Clases y modelos principales (`classes/`)

El módulo se basa en gran medida en anulaciones para modificar el comportamiento central de PrestaShop.

-   `multishoplang/override/classes/Currency.php`
    -   **Nombre de la clase y clase padre**: `Currency` (anula la clase `Currency` central de PrestaShop).
    -   **Responsabilidad**: Esta anulación intercepta las llamadas relacionadas con la recuperación y selección de moneda. Modifica métodos como `getCurrencies()` o `getDefaultCurrency()` para filtrar la lista de monedas disponibles según la configuración de la tienda actual definida por el módulo. Asegura que solo las monedas habilitadas para la tienda activa se presenten en el front office.
-   `multishoplang/override/classes/Language.php`
    -   **Nombre de la clase y clase padre**: `Language` (anula la clase `Language` central de PrestaShop).
    -   **Responsabilidad**: Similar a la anulación de `Currency`, esta clase intercepta las llamadas relacionadas con el idioma. Modifica métodos como `getLanguages()` o `getDefaultLanguage()` para filtrar la lista de idiomas disponibles según la configuración de la tienda actual. Asegura que solo los idiomas habilitados para la tienda activa se presenten en el front office.
-   `multishoplang/override/classes/index.php`
    -   **Nombre de la clase y clase padre**: Este suele ser un archivo vacío o un archivo que contiene una declaración de seguridad `die()` para evitar el acceso directo al directorio. No representa una clase activa.

### 4.4 Activos JavaScript (`views/js/`)

El módulo no incluye ningún archivo JavaScript personalizado. Todas las interacciones en el Back Office son manejadas por el JavaScript estándar de `HelperForm` y `HelperList` de PrestaShop, y el comportamiento del front office es gestionado por las anulaciones de clases.

### 4.5 Hojas de estilo CSS (`views/css/`)

El módulo no incluye ningún archivo CSS personalizado. Su interfaz de Back Office se basa en el estilo del tema de administración predeterminado de PrestaShop. La visualización del front office está controlada por el tema activo.

### 4.6 Estructura de plantillas Smarty (`views/templates/`)

-   **Plantillas de hook (`views/templates/hook/`)**: Ninguna explícitamente listada, pero la lógica del módulo opera principalmente a través de anulaciones de clases en lugar de plantillas de hook directas.
-   **Plantillas de administración (`views/templates/admin/`)**:
    -   `multishoplang/views/advert.tpl`
        -   **Propósito**: Probablemente una plantilla para mostrar mensajes promocionales o información sobre otros módulos de MyPresta.eu dentro de la interfaz de configuración del módulo.
    -   `multishoplang/views/currenciesForm.tpl`
        -   **Propósito**: Esta plantilla se utiliza dentro de `AdminMultirulesController` para renderizar la sección del formulario para configurar las monedas disponibles y la moneda predeterminada para una tienda específica. Contendrá casillas de verificación para las monedas y un menú desplegable para la predeterminada.
    -   `multishoplang/views/languagesForm.tpl`
        -   **Propósito**: Esta plantilla se utiliza dentro de `AdminMultirulesController` para renderizar la sección del formulario para configurar los idiomas disponibles y el idioma predeterminado para una tienda específica. Contendrá casillas de verificación para los idiomas y un menú desplegable para el predeterminado.
-   **Plantillas de front-office (`views/templates/front/`)**: Ninguna.

### 4.7 Esquema de la base de datos y mapa de hooks

-   **Tablas de la base de datos**:

    -   `ps_multirule`: Esta es la tabla personalizada creada por el módulo para almacenar las reglas de localización. Probablemente contiene campos como:
        -   `id_shop`: Clave externa que hace referencia a `ps_shop.id_shop`.
        -   `id_lang_default`: El ID del idioma predeterminado para esa tienda.
        -   `id_currency_default`: El ID de la moneda predeterminada para esa tienda.
        -   `available_languages`: Un array serializado o una cadena separada por comas de valores `id_lang` habilitados para la tienda.
        -   `available_currencies`: Un array serializado o una cadena separada por comas de valores `id_currency` habilitados para la tienda.
    -   Los registros de configuración se almacenan en `ps_configuration` para la configuración general del módulo (si la hay).
-   **Tabla de Hooks registrados**:
    El módulo opera principalmente a través de anulaciones de clases en lugar de la ejecución directa de hooks en el front office. Sin embargo, registrará hooks estándar del Back Office para su interfaz de administración.

| Nombre del Hook | Momento de ejecución | Propósito técnico |
| --- | --- | --- |
| `actionAdminControllerSetMedia` | Cuando se carga un controlador de administración | Para cargar CSS/JS específicos del módulo (aunque no hay ninguno presente en este módulo). |
| `displayBackOfficeHeader` | En el encabezado del Back Office | Potencialmente para mostrar alertas o avisos específicos del módulo. |
| `moduleRoutes` | Durante la inicialización del enrutamiento de URL | Si el módulo definió rutas personalizadas de front-office (no aplicable aquí). |
| `actionObjectLanguageAddAfter` | Después de agregar un nuevo idioma | Para actualizar potencialmente los datos internos del módulo para nuevos idiomas. |
| `actionObjectCurrencyAddAfter` | Después de agregar una nueva moneda | Para actualizar potencialmente los datos internos del módulo para nuevas monedas. |
| `actionShopDataDuplication` | Cuando se duplica una tienda | Para asegurar que las reglas de localización se copien para la nueva tienda. |

## 5. Soporte oficial y actualizaciones

Para las últimas actualizaciones, correcciones de errores y soporte profesional, consulte su cuenta de cliente en [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nuestro equipo se dedica a garantizar el buen funcionamiento y la mejora continua de sus módulos de PrestaShop.
