---
title: "Ocultar características seleccionadas - Manual de Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop 'Ocultar características seleccionadas' de MyPresta.eu."
sidebar:
  label: "Ocultar características seleccionadas - Manual de Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Hide selected features en MyPresta.eu](https://mypresta.eu/modules/front-office-features/hide-selected-features.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/front-office/hide-selected-features/)
>
> ---


# Ocultar características seleccionadas

## 1. Requisitos y Compatibilidad

- **Versiones de PrestaShop compatibles**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilidad con PHP**: PHP 5.6 - 8.5
- **Requisitos de alojamiento**: Extensiones PHP estándar (cURL, JSON, OpenSSL).

## 2. Recorrido Completo por la Configuración (Cada Ajuste Agrupado por Pantalla)

### 2.1 Página de Configuración del Módulo (Back Office > Módulos > Configurar)

Puede acceder a esta página navegando a **Módulos > Gestor de módulos** y buscando "Ocultar características seleccionadas", luego haciendo clic en "Configurar".

Esta pantalla presenta una lista de todas las características de producto actualmente definidas en su tienda PrestaShop. Para cada característica, verá un interruptor de palanca para controlar su visibilidad.

- **Qué hace esta configuración:** Esta sección enumera todas sus características de producto existentes (por ejemplo, "Material", "Color", "Peso", "Dimensiones"). Junto a cada característica, hay un interruptor que controla si esa característica específica se mostrará en las páginas de sus productos en el front office.
- **Efecto de cambiar esta configuración:**
  - *Cuando está habilitado (el interruptor está ENCENDIDO):* La característica será visible para los clientes en todas las páginas de producto donde esté asignada. Este es el comportamiento predeterminado de PrestaShop.
  - *Cuando está deshabilitado (el interruptor está APAGADO):* La característica estará oculta para los clientes en todas las páginas de producto, incluso si está asignada a un producto. Seguirá existiendo en su back office para uso interno o filtrado.
- **Valor recomendado:** Esto depende completamente de sus necesidades comerciales.
  - **Habilite** las características que son cruciales para la toma de decisiones del cliente (por ejemplo, "Material" para la ropa, "Capacidad" para la electrónica).
  - **Deshabilite** las características que son notas internas, especificaciones técnicas irrelevantes para el cliente promedio o información redundante.
- **Escenario / ejemplo de comerciante:**
  - **Escenario 1 (Ocultar notas internas):** Usted utiliza una característica llamada "SKU del proveedor" para rastrear códigos de producto internos. Esta información no es útil para los clientes. **Deshabilitaría** la característica "SKU del proveedor" aquí para mantener limpias las páginas de sus productos.
  - **Escenario 2 (Simplificar la visualización):** Usted vende camisetas y tiene características como "Material: Algodón", "Longitud de la manga: Corta", "Escote: Redondo". Decide que la "Longitud de la manga" y el "Escote" suelen ser claros a partir de la imagen del producto y desea enfatizar el "Material". **Deshabilitaría** "Longitud de la manga" y "Escote" y **habilitaría** "Material".

**Otras claves de configuración (Internas/Avanzadas):**
Es posible que vea otras claves de configuración como `mypresta_updates`, `update_`, `updatev_`, `hidefeatures_OSTATE`, `PS_OS_PREPARATION`, `hidefeatures_MIN_CHARGE`. Estas son típicamente configuraciones internas del módulo relacionadas con actualizaciones, estados de pedidos o cargos mínimos, y no son directamente configurables por el comerciante a través de la interfaz principal. Generalmente son gestionadas automáticamente por el módulo o utilizadas para escenarios específicos y avanzados no expuestos en la interfaz de usuario principal. Para este módulo, la funcionalidad principal se gestiona mediante los interruptores de las características.

### 2.2 Pantallas de Administración Dedicadas y Vistas de Controlador

#### 2.2.1 AdminFeaturesController (Back Office > Catálogo > Atributos y Características > Características)

Este módulo anula la pantalla estándar de gestión de "Características" de PrestaShop.

- **Nombre de la pantalla y ubicación del menú:** **Back Office > Catálogo > Atributos y Características > Características**.
- **Acciones y configuraciones disponibles:** Cuando acceda a esta pantalla, verá una lista de todas sus características de producto. El módulo añade una nueva columna o indicador a esta lista, típicamente etiquetado como **"Activo en front office"** o similar. Esta columna le mostrará de un vistazo si una característica está actualmente configurada para ser visible u oculta en el front-end de su tienda, basándose en las configuraciones que realizó en la página de configuración principal del módulo.
- **Efecto de los cambios:** Aunque no puede cambiar directamente la visibilidad desde esta pantalla (lo hace en la página de configuración del módulo), esta pantalla proporciona una visión general conveniente. Le ayuda a verificar rápidamente el estado de front-office de cada característica sin tener que volver al módulo.
- **Flujo de trabajo recomendado para la gestión diaria de la tienda:** Utilice esta pantalla como referencia rápida al gestionar las características de sus productos. Si añade una nueva característica, recuerde visitar la página de configuración del módulo "Ocultar características seleccionadas" para decidir si debe ser visible para los clientes.

#### 2.2.2 index.php (hidefeatures/override/controllers/admin/index.php)

Este archivo forma parte de la estructura de anulación y normalmente sirve como marcador de posición o punto de entrada para la lógica del controlador anulado. No representa una pantalla de configuración distinta y orientada al usuario, sino que facilita la modificación del módulo de las páginas de administración existentes de PrestaShop.

- **Tabla / Entidad gestionada:** Este archivo no gestiona una tabla o entidad específica directamente, sino que asegura la carga y ejecución correctas del `AdminFeaturesController` anulado.
- **Campos de formulario y columnas:** Este archivo específico no gestiona directamente ningún campo de formulario o columna. Su propósito es arquitectónico, asegurando que se apliquen los cambios del módulo a la vista de cuadrícula/gestión de "Características".
- **Efecto de los cambios:** Este archivo asegura que la columna "Activo en front office" (o un indicador similar) se muestre correctamente en la lista **Catálogo > Atributos y Características > Características**, proporcionando la vista de gestión mejorada.

### 2.3 Tabla de Referencia Rápida de Configuración

| Pantalla / Vista | Configuración / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| **Página de Configuración del Módulo** | Lista de todas las Características con interruptores ON/OFF | Varía según la característica (ON para nuevas características) | Controla si una característica de producto específica se muestra en las páginas de producto en el front office. ON = Visible, OFF = Oculta. |
| **AdminFeaturesController** (Catálogo > Atributos y Características > Características) | Columna/indicador "Activo en front office" | Refleja la configuración del módulo | Proporciona una visión general rápida del estado de visibilidad de una característica en el front office directamente en la lista de características. |

## 3. Solución de Problemas para Comerciantes y Preguntas Frecuentes (FAQ)

**P: He ocultado una característica, pero sigue apareciendo en la página de mi producto. ¿Qué está mal?**
R:

1. **Borrar caché:** La razón más común es que la caché de su PrestaShop (y posiblemente la caché de su navegador) no se ha actualizado. Vaya a **Parámetros avanzados > Rendimiento** en su Back Office y haga clic en "Borrar caché" (o "Borrar caché de Smarty" en versiones anteriores). Además, intente borrar la caché de su navegador o ver la página en una ventana de incógnito/privada.
2. **¿Configuración del módulo guardada?** Verifique que hizo clic en "Guardar" después de realizar cambios en la página de configuración del módulo.
3. **¿Característica correcta?** Asegúrese de haber deshabilitado la característica exacta que desea ocultar. Los nombres de las características a veces pueden ser similares.

**P: ¿Puedo ocultar características solo para productos específicos, no globalmente?**
R: No, este módulo oculta las características globalmente en todos los productos. Si necesita visibilidad de características específicas del producto, normalmente lo gestionaría no asignando la característica al producto en primer lugar, o utilizando una solución personalizada más avanzada. Este módulo proporciona un interruptor a nivel de tienda para los tipos de características.

**P: ¿Ocultar una característica afectará mis filtros de producto o los resultados de búsqueda?**
R: No, este módulo solo afecta la *visualización* de las características en la página del producto del front office. Los datos de la característica en sí permanecen en su base de datos. Si utiliza características para la navegación por capas (filtros) o la búsqueda, deberían seguir funcionando como se espera, siempre que la característica esté asignada al producto.

**P: La columna "Activo en front office" no aparece en mi lista de Características (Catálogo > Atributos y Características > Características).**
R:

1. **¿Módulo instalado y habilitado?** Asegúrese de que el módulo "Ocultar características seleccionadas" esté correctamente instalado y habilitado en **Módulos > Gestor de módulos**.
2. **Caché:** Borre la caché de su PrestaShop como se describió anteriormente.
3. **Compatibilidad con el tema:** En casos raros, un tema altamente personalizado podría interferir con las anulaciones. Si borrar la caché no ayuda, póngase en contacto con el soporte de MyPresta.eu.

**P: ¿Cómo traduzco el texto del módulo (si lo hay)?**
R: Aunque este módulo utiliza principalmente nombres de características existentes de PrestaShop, si hay algún texto o etiqueta específica del módulo, puede traducirlos yendo a **Internacional > Traducciones** en su Back Office. Seleccione "Traducciones de módulos instalados", elija su tema, seleccione su idioma y luego busque el módulo "Ocultar características seleccionadas" para editar sus traducciones.

## 4. Guía para Desarrolladores y Webmasters (Arquitectura Técnica y Mapa de Código)

### 4.1 Visión General de la Arquitectura

El módulo "Ocultar características seleccionadas" funciona anulando clases y controladores centrales de PrestaShop para inyectar su lógica de visibilidad. Extiende las clases `Feature` y `Product` para añadir una nueva propiedad para la visibilidad en el front-office y modifica el `AdminFeaturesController` para mostrar este estado en el back office. El módulo utiliza un hook personalizado (`displayHiddenFeatures`) para renderizar la lista real de características en la página del producto, lo que le permite filtrar las características ocultas antes de la visualización.

### 4.2 Controladores (`controllers/`)

- **Controladores de Front-Office**: Este módulo no introduce ningún controlador de front-office personalizado. Toda la lógica de front-office se maneja mediante anulaciones de clases y hooks centrales.
- **Controladores de Administración de Back-Office**:

  - `hidefeatures/override/controllers/admin/AdminFeaturesController.php`
    - **Nombre de la clase y clase padre**: `AdminFeaturesController` (anula el `AdminFeaturesController` central)
    - **Responsabilidad**: Esta anulación modifica el `AdminFeaturesController` para mostrar el estado de visibilidad en el front-office de cada característica en la lista de características. Probablemente añade una nueva columna a la tabla de la lista, permitiendo a los administradores ver rápidamente qué características están ocultas/visibles sin tener que ir a la configuración del módulo. Aprovecha la anulación de la clase `Feature` para recuperar este estado.
  - `hidefeatures/override/controllers/admin/index.php`
    - **Nombre de la clase y clase padre**: No es un archivo de clase, típicamente un `index.php` vacío para evitar la lista de directorios.
    - **Responsabilidad**: Práctica estándar para los directorios `override` para evitar el acceso directo y garantizar la seguridad. No contiene código funcional.

### 4.3 Clases y Modelos Centrales (`classes/`)

- `hidefeatures/override/classes/Feature.php`

  - **Con qué tabla de base de datos interactúa**: `ps_feature` (tabla principal de características) y `ps_configuration` (para la configuración del módulo).
  - **Extiende `ObjectModel`**: Sí, extiende la clase `Feature` central que a su vez extiende `ObjectModel`.
  - **Campos `$definition`**: Esta anulación probablemente añade un nuevo campo al array `$definition` de la clase `Feature`, o más comúnmente, añade una propiedad dinámica al objeto `Feature` para almacenar su estado de visibilidad en el front-office, que luego se recupera de `ps_configuration` o de una tabla personalizada. También contendría métodos para recuperar y establecer este estado de visibilidad.
  - **Métodos públicos clave y lógica de negocio encapsulada**:
    - Métodos para recuperar el estado de visibilidad de una característica específica.
    - Métodos para actualizar el estado de visibilidad, probablemente interactuando con `Configuration::updateValue()`.
    - Potencialmente modifica `getFeatures()` o métodos similares para filtrar resultados basándose en la visibilidad.
- `hidefeatures/override/classes/index.php`

  - **Nombre de la clase y clase padre**: No es un archivo de clase, típicamente un `index.php` vacío para evitar la lista de directorios.
  - **Responsabilidad**: Práctica estándar para los directorios `override` para evitar el acceso directo y garantizar la seguridad. No contiene código funcional.
- `hidefeatures/override/classes/Product.php`

  - **Con qué tabla de base de datos interactúa**: `ps_product` y `ps_feature_product`.
  - **Extiende `ObjectModel`**: Sí, extiende la clase `Product` central que a su vez extiende `ObjectModel`.
  - **Campos `$definition`**: No se espera una modificación directa a `$definition` aquí.
  - **Métodos públicos clave y lógica de negocio encapsulada**: Esta anulación es crucial para filtrar características en la página del producto. Probablemente modifica métodos como `getFeatures()` o `getFrontFeatures()` (si existen en la clase `Product` central) para:
    1. Obtener todas las características asignadas a un producto.
    2. Iterar a través de estas características.
    3. Para cada característica, verificar su estado de visibilidad utilizando la lógica de la clase `Feature` anulada.
    4. Devolver solo las características que están marcadas como visibles.
       Esto asegura que cuando se recuperan las características de un producto para su visualización, las ocultas se excluyen automáticamente.

### 4.4 Activos JavaScript (`views/js/`)

El módulo no parece contener ningún archivo JavaScript personalizado. Su funcionalidad es principalmente del lado del servidor a través de anulaciones de PHP y lógica de plantilla Smarty.

### 4.5 Hojas de Estilo CSS (`views/css/`)

El módulo no parece contener ningún archivo CSS personalizado. Cualquier estilo para la columna añadida en el AdminFeaturesController se manejaría típicamente mediante el CSS predeterminado del back-office de PrestaShop.

### 4.6 Estructura de Plantillas Smarty (`views/templates/`)

- **Plantillas de Hook (`views/templates/hook/`)**:

  - `hidefeatures/views/templates/front/hook/displayHiddenFeatures.tpl`
    - **Hook**: `displayHiddenFeatures` (hook personalizado, probablemente llamado dentro de la clase `Product` anulada o en el `product.tpl` de un tema)
    - **Salida**: Esta plantilla es responsable de renderizar la lista de características del producto en la página del producto del front office. Recibe la lista filtrada de características (después de que las ocultas hayan sido eliminadas por la anulación de la clase `Product`) y las muestra en el formato estándar de tabla/lista de características de PrestaShop. Los desarrolladores pueden inspeccionar esta plantilla para entender cómo se iteran y muestran las características.
- **Plantillas de Administración (`views/templates/admin/`)**:

  - `hidefeatures/views/templates/admin/_configure/helpers/list/list_content.tpl`
    - **Propósito**: Esta plantilla es una anulación de la plantilla estándar de contenido de lista de PrestaShop, utilizada específicamente dentro del `AdminFeaturesController`. Es responsable de renderizar las filas de la tabla de la lista de características en el back office.
    - **Contenido**: Contendrá lógica para mostrar la columna "Activo en front office" (o similar) para cada característica, mostrando un indicador visual (por ejemplo, una marca de verificación, una X roja o un interruptor) basado en el estado de visibilidad de la característica. Esta plantilla funciona en conjunto con la anulación del `AdminFeaturesController` para presentar la información adicional.
- **Plantillas de Front-office (`views/templates/front/`)**:

  - No hay plantillas de página de front-office dedicadas e independientes.

### 4.7 Esquema de Base de Datos y Mapa de Hooks

- **Tablas de Base de Datos**:

  - El módulo no crea nuevas tablas de base de datos personalizadas.
  - Almacena su configuración (qué características están ocultas/visibles) en la tabla `ps_configuration`. Las claves de configuración seguirían típicamente un patrón como `HIDEFEATURES_FEATURE_ID_X` o similar, donde `X` es el `id_feature`.
- **Tabla de Hooks Registrados**:

| Nombre del Hook | Momento de Ejecución | Propósito Técnico |
| --- | --- | --- |
| `displayHiddenFeatures` | Hook personalizado, probablemente llamado dentro de `product.tpl` o a través de la anulación de `Product::getFrontFeatures()`. | Renderiza la lista filtrada de características del producto en la página del producto del front-office, asegurando que solo se muestren las características visibles. |
| `actionProductUpdate` | Después de que se actualiza un producto. | (Implícito, si el módulo necesita reevaluar la visibilidad de las características al guardar el producto, aunque no se enumera explícitamente como un hook principal para la función central de este módulo). |
| `actionFeatureSave` / `actionFeatureDelete` | Después de que se guarda o elimina una característica. | (Implícito, si el módulo necesita actualizar su configuración interna cuando se añaden/eliminan características). |
| `displayBackOfficeHeader` | Renderiza contenido en la sección `<head>` del Back Office. | (Posible, para inyectar JS/CSS si es necesario para la interfaz de usuario de administración, pero no presente en el inventario). |

## 5. Soporte Oficial y Actualizaciones

Para actualizaciones oficiales, soporte técnico y cualquier consulta relacionada con el módulo "Ocultar características seleccionadas", consulte su cuenta de cliente en [MyPresta.eu](https://mypresta.eu). Nuestro equipo de soporte está disponible para ayudarle con cualquier problema o pregunta que pueda tener.
"""
