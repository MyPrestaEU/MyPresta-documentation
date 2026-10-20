---
title: "Zoom de atributo de color/textura - Manual del Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop 'Zoom de atributo de color/textura' de MyPresta.eu."
sidebar:
  label: "Zoom de atributo de color/textura - Manual del Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Color / texture attribute zoom en MyPresta.eu](https://mypresta.eu/modules/front-office-features/color-texture-attribute-zoom.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/front-office/color-texture-attribute-zoom/)
>
> ---


# Zoom de atributo de color/textura

## 1. Requisitos y Compatibilidad

- **Versiones de PrestaShop compatibles**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilidad con PHP**: PHP 5.6 - 8.5
- **Requisitos de alojamiento**: Las extensiones PHP estándar (cURL, JSON, OpenSSL) son típicamente requeridas por PrestaShop y son suficientes para este módulo.

## 2. Recorrido completo de la configuración (Cada ajuste agrupado por pantalla)

### 2.1 Página de configuración del módulo (Back Office > Módulos > Configurar)

Esta es la pantalla de configuración principal para el módulo "Zoom de atributo de color/textura", accesible después de la instalación haciendo clic en el botón "Configurar".

#### **Habilitar / Deshabilitar Módulo**

- **Qué hace esta configuración:** Este es el interruptor maestro para activar o desactivar la funcionalidad del módulo en toda su tienda.
- **Efecto de cambiar esta configuración:**
  - *Cuando está habilitado:* La función de zoom de color/textura estará activa en sus páginas de producto y ventanas emergentes de vista rápida, de acuerdo con las otras configuraciones que haya elegido.
  - *Cuando está deshabilitado:* La función de zoom se desactivará por completo y no aparecerán vistas previas ampliadas.
- **Valor recomendado:** **Habilitado** (para utilizar las características del módulo).
- **Escenario / ejemplo del comerciante:** Si desea deshabilitar temporalmente la función de zoom para mantenimiento o pruebas, puede desactivarla sin desinstalar el módulo.

#### **Mostrar nombre (valor) de color / textura**

- **Qué hace esta configuración:** Determina si el nombre de texto del color o la textura (por ejemplo, "Rojo", "Cuero") aparece junto a la ventana de vista previa con zoom.
- **Efecto de cambiar esta configuración:**
  - *Cuando está habilitado:* El nombre del atributo se mostrará junto a la imagen con zoom, proporcionando contexto adicional al cliente.
  - *Cuando está deshabilitado:* Solo aparecerá la imagen con zoom, sin la etiqueta de texto.
- **Valor recomendado:** **Habilitado**. Esto proporciona información más clara al cliente, especialmente si los colores son similares o las texturas son sutiles.
- **Escenario / ejemplo del comerciante:** Si tiene muchos tonos de azul (por ejemplo, "Azul Cielo", "Azul Marino"), mostrar el nombre ayuda a los clientes a diferenciarlos claramente.

#### **Deshabilitar cambio de atributo al tocar**

- **Qué hace esta configuración:** Controla el comportamiento del módulo en dispositivos táctiles (como teléfonos inteligentes y tabletas) cuando un cliente toca una muestra de color/textura.
- **Efecto de cambiar esta configuración:**
  - *Cuando está habilitado:* Tocar una muestra de color/textura solo mostrará la vista previa con zoom. La imagen principal del producto en la página NO cambiará para reflejar el atributo tocado.
  - *Cuando está deshabilitado:* Tocar una muestra de color/textura mostrará la vista previa con zoom Y también actualizará la imagen principal del producto para mostrar el producto en ese color/textura seleccionado.
- **Valor recomendado:** **Deshabilitado**. La mayoría de los clientes esperan que la imagen principal del producto se actualice cuando seleccionan un color/textura, incluso en dispositivos móviles. Habilite esto solo si tiene una razón específica para no cambiar la imagen principal al tocar.
- **Escenario / ejemplo del comerciante:** Si las imágenes de sus productos son genéricas y no cambian según los atributos de color, o si desea evitar cambios accidentales de la imagen principal en dispositivos móviles, podría habilitar esto. De lo contrario, manténgalo deshabilitado para un comportamiento estándar.

#### **Ancho de la ventana de vista previa de color**

- **Qué hace esta configuración:** Establece el ancho (en píxeles) de la ventana emergente que muestra la vista previa de color con zoom.
- **Efecto de cambiar esta configuración:**
  - *Aumentar el valor:* Hace que la ventana de vista previa sea más ancha, mostrando más detalles.
  - *Disminuir el valor:* Hace que la ventana de vista previa sea más estrecha.
- **Valor recomendado:** Un valor entre **200px y 300px** suele ser un buen equilibrio. Comience con `280` y ajuste según las imágenes de sus productos y el diseño del tema.
- **Escenario / ejemplo del comerciante:** Si sus muestras de color son muy pequeñas y desea mostrar una ampliación significativa, aumente este valor. Si el diseño de su página de producto es muy estrecho, es posible que deba reducirlo.

#### **Altura de la ventana de vista previa de color**

- **Qué hace esta configuración:** Establece la altura (en píxeles) de la ventana emergente que muestra la vista previa de color con zoom.
- **Efecto de cambiar esta configuración:**
  - *Aumentar el valor:* Hace que la ventana de vista previa sea más alta, mostrando más detalles.
  - *Disminuir el valor:* Hace que la ventana de vista previa sea más corta.
- **Valor recomendado:** Un valor entre **200px y 300px** suele ser un buen equilibrio. Comience con `280` y ajuste según las imágenes de sus productos y el diseño del tema.
- **Escenario / ejemplo del comerciante:** Similar al ancho, ajuste esto para asegurar que el color con zoom sea claramente visible sin ser excesivamente grande o pequeño para su página de producto.

#### **Activar zoom en la tabla de combinaciones**

- **Qué hace esta configuración:** Determina si la función de zoom también debe aplicarse a los atributos de color/textura que se muestran dentro de una tabla de combinaciones de productos (si su tema utiliza una).
- **Efecto de cambiar esta configuración:**
  - *Cuando está habilitado:* Los clientes pueden pasar el ratón/tocar las muestras de color/textura dentro de una tabla de combinaciones para ver la vista previa con zoom.
  - *Cuando está deshabilitado:* La función de zoom solo funcionará para los atributos de color/textura fuera de cualquier tabla de combinaciones.
- **Valor recomendado:** **Habilitado**. Esto proporciona una experiencia consistente y útil en todas las áreas donde se muestran los atributos de color/textura.
- **Escenario / ejemplo del comerciante:** Si vende camisetas con una tabla que muestra tallas y colores disponibles, habilitar esto permite a los clientes hacer zoom en los colores directamente desde esa tabla.

#### **Ancho de la ventana de vista previa de textura**

- **Qué hace esta configuración:** Establece el ancho (en píxeles) de la ventana emergente que muestra la vista previa de textura con zoom. Esto es independiente del ancho de la vista previa de color, lo que le permite optimizar para diferentes tipos de imágenes de atributos.
- **Efecto de cambiar esta configuración:**
  - *Aumentar el valor:* Hace que la vista previa de textura sea más ancha.
  - *Disminuir el valor:* Hace que la vista previa de textura sea más estrecha.
- **Valor recomendado:** Similar al color, un valor entre **200px y 300px** suele ser adecuado. Comience con `280`.
- **Escenario / ejemplo del comerciante:** Si sus imágenes de textura son muy detalladas y requieren una vista más grande para apreciarlas, podría establecer un ancho mayor aquí que para las simples muestras de color.

#### **Excluir algunos grupos de atributos de color del ZOOM**

- **Qué hace esta configuración:** Le permite especificar ciertos grupos de atributos (por ejemplo, "Talla", "Material") para los cuales la función de zoom NO debe aplicarse, incluso si utilizan imágenes de color o textura.
- **Efecto de cambiar esta configuración:**
  - *Cuando se introducen los ID de los grupos de atributos:* La función de zoom se deshabilitará para cualquier atributo que pertenezca a los grupos especificados.
  - *Cuando se deja vacío:* La función de zoom se aplicará a todos los grupos de atributos de color/textura.
- **Valor recomendado:** Dejar **vacío** a menos que tenga una razón específica para excluir grupos. Si necesita excluir, introduzca los ID numéricos de los grupos de atributos, separados por comas (por ejemplo, `1, 5, 12`). Puede encontrar los ID de los grupos de atributos en su Back Office de PrestaShop en **Catálogo > Atributos y Características > Grupos de atributos**.
- **Escenario / ejemplo del comerciante:** Podría tener un grupo de atributos de "Disponibilidad" que utiliza muestras de color (por ejemplo, verde para en stock, rojo para agotado), pero no desea que estos activen un zoom. En este caso, encontraría el ID del grupo de atributos de "Disponibilidad" y lo introduciría aquí.

#### **Tipo de animación**

- **Qué hace esta configuración:** Selecciona el efecto visual utilizado cuando aparece la ventana de vista previa con zoom.
- **Efecto de cambiar esta configuración:** Cambia la forma en que la ventana de vista previa se anima al aparecer (por ejemplo, desvaneciéndose, deslizándose).
- **Valor recomendado:** **Desvanecer**. Esta es generalmente la animación más sutil y de aspecto profesional. Experimente con otras si prefiere un efecto diferente.
- **Escenario / ejemplo del comerciante:** Puede elegir una animación que se adapte mejor a la estética general del diseño de su tienda.

#### **Actualizar tipo de animación**

- **Qué hace esta configuración:** Selecciona el efecto visual utilizado cuando el contenido de la ventana de vista previa con zoom cambia (por ejemplo, al cambiar entre diferentes colores/texturas mientras la vista previa ya está abierta).
- **Efecto de cambiar esta configuración:** Cambia la animación para las actualizaciones de contenido dentro de la vista previa.
- **Valor recomendado:** **Desvanecer**. Similar a la animación inicial, un desvanecimiento suele ser suave y no distrae.
- **Escenario / ejemplo del comerciante:** Si un cliente pasa rápidamente el ratón sobre varias muestras de color, esta animación dicta la suavidad con la que el contenido de la vista previa realiza la transición.

#### Tabla de referencia rápida de configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| Configuración del módulo | Habilitar / Deshabilitar Módulo | Habilitado | Interruptor maestro para la funcionalidad del módulo. |
| Configuración del módulo | Mostrar nombre (valor) de color / textura | Habilitado | Muestra el nombre del atributo con la vista previa con zoom. |
| Configuración del módulo | Deshabilitar cambio de atributo al tocar | Deshabilitado | Evita el cambio de imagen principal al tocar en móvil (si está habilitado). |
| Configuración del módulo | Ancho de la ventana de vista previa de color | 280 | Ancho de la ventana emergente de zoom de color en píxeles. |
| Configuración del módulo | Altura de la ventana de vista previa de color | 280 | Altura de la ventana emergente de zoom de color en píxeles. |
| Configuración del módulo | Activar zoom en la tabla de combinaciones | Habilitado | Extiende el zoom a los atributos dentro de las tablas de combinaciones. |
| Configuración del módulo | Ancho de la ventana de vista previa de textura | 280 | Ancho de la ventana emergente de zoom de textura en píxeles. |
| Configuración del módulo | Excluir algunos grupos de atributos de color del ZOOM | Vacío | ID separados por comas de los grupos de atributos a ignorar para el zoom. |
| Configuración del módulo | Tipo de animación | Desvanecer | Animación para la aparición de la vista previa con zoom. |
| Configuración del módulo | Actualizar tipo de animación | Desvanecer | Animación para los cambios de contenido dentro de la vista previa con zoom. |

## 3. Solución de problemas del comerciante y preguntas frecuentes (FAQ)

**P: El zoom no aparece en mi página de producto. ¿Qué debo verificar?**
R:

1. **Módulo habilitado:** Vaya a **Módulos > Gestor de módulos** y asegúrese de que "Zoom de atributo de color/textura" esté habilitado.
2. **Configuración de atributos:** Verifique que sus atributos de producto estén configurados correctamente como tipo "Color" o "Textura" en **Catálogo > Atributos y Características > Atributos**. Asegúrese de haber subido imágenes reales para estos atributos, no solo códigos de color.
3. **Caché:** Borre la caché de su PrestaShop. Vaya a **Parámetros avanzados > Rendimiento**, desplácese hasta "Borrar caché" y haga clic en "Borrar caché". Además, borre la caché de su navegador.
4. **Compatibilidad del tema:** Aunque el módulo está diseñado para una amplia compatibilidad, los temas muy personalizados a veces pueden interferir. Si los pasos anteriores no funcionan, cambie temporalmente al tema predeterminado de PrestaShop para ver si aparece el zoom. Si lo hace, su tema podría requerir un pequeño ajuste.

**P: La ventana de vista previa del zoom es demasiado pequeña/grande.**
R: Ajuste las configuraciones "Ancho de la ventana de vista previa de color", "Altura de la ventana de vista previa de color" y "Ancho de la ventana de vista previa de textura" en la página de configuración del módulo. Aumente los valores para hacer la ventana más grande, disminúyalos para hacerla más pequeña. Recuerde guardar los cambios y borrar la caché.

**P: El nombre del color/textura no aparece con el zoom.**
R: Verifique la configuración "Mostrar nombre (valor) de color / textura" en la configuración del módulo. Asegúrese de que esté configurado como "Habilitado".

**P: En el móvil, cuando toco un color, la imagen principal del producto no cambia, pero quiero que lo haga.**
R: Vaya a la configuración del módulo y asegúrese de que "Deshabilitar cambio de atributo al tocar" esté configurado como "Deshabilitado". Esto permitirá que la imagen principal del producto se actualice cuando se toque un color/textura.

**P: Quiero excluir un grupo de atributos específico de tener la función de zoom.**
R: Navegue a **Catálogo > Atributos y Características > Grupos de atributos** en su Back Office de PrestaShop. Encuentre el grupo de atributos que desea excluir y anote su ID (generalmente visible en la URL cuando lo edita, o en la propia tabla). Luego, vaya a la configuración del módulo, busque "Excluir algunos grupos de atributos de color del ZOOM" e introduzca los ID separados por comas (por ejemplo, `1,5,12`).

## 4. Guía para desarrolladores y webmasters (Arquitectura técnica y mapa de código)

Esta sección es estrictamente para desarrolladores, webmasters de tiendas y agencias técnicas que mantienen o extienden la tienda.

### 4.1 Resumen de la arquitectura

El módulo "Zoom de atributo de color/textura" (`colorzoom`) es un módulo de características de front-office diseñado para mejorar la visualización de atributos de producto. Principalmente aprovecha el sistema de hooks de PrestaShop para inyectar sus activos JavaScript y CSS en el encabezado del front-office y para renderizar su plantilla de zoom específica en las páginas de producto. Utiliza la biblioteca `tooltipster` para la funcionalidad real de zoom/tooltip, adjuntándola dinámicamente a los elementos de atributos de color y textura. La configuración se gestiona a través del método estándar `getContent()` en el archivo principal del módulo, almacenando la configuración en `ps_configuration`.

### 4.2 Controladores (`controllers/`)

El módulo incluye dos controladores de front-office, aunque su función principal en este módulo suele ser mínima o para necesidades AJAX específicas, con gran parte de la lógica manejada del lado del cliente a través de JavaScript.

- **Controladores de Front-Office**:

  - `controllers/front/index.php`
    - Nombre de la clase: `ColorzoomIndexModuleFrontController` (extiende `ModuleFrontController`)
    - Responsabilidad: Este controlador probablemente sirve como un recurso alternativo o un punto de entrada genérico. Dada la función principal del módulo de mejora de la interfaz de usuario a través de JS/CSS, este controlador podría no tener una lógica extensa o podría usarse para una simple recuperación de datos si es necesario para el front-end.
  - `controllers/front/loader.php`
    - Nombre de la clase: `ColorzoomLoaderModuleFrontController` (extiende `ModuleFrontController`)
    - Responsabilidad: Este controlador podría usarse para cargar recursos o datos específicos dinámicamente, potencialmente para solicitudes AJAX relacionadas con la funcionalidad de zoom, aunque la lógica central del zoom es del lado del cliente.
- **Controladores de administración de Back-Office**: Ninguno. Toda la configuración se maneja a través del método `getContent()` del módulo principal.

### 4.3 Clases y modelos principales (`classes/`)

El módulo no define ninguna clase `ObjectModel` personalizada ni clases de lógica de negocio dedicadas en el directorio `classes/`. Su funcionalidad principal se implementa dentro del archivo principal `colorzoom.php` y a través de sus activos JavaScript.

### 4.4 Activos JavaScript (`views/js/`)

El módulo depende en gran medida de JavaScript para su funcionalidad de zoom interactivo, particularmente de la biblioteca `tooltipster`.

- `colorzoom/lib/tooltipster/dist/js/plugins/tooltipster/SVG/tooltipster-SVG.js`
  - Alcance: Front-office.
  - Detalles: Un plugin para la biblioteca `tooltipster`, específicamente para manejar elementos SVG dentro de los tooltips. Esto podría usarse si las imágenes de atributos están basadas en SVG o si el módulo necesita interactuar con elementos SVG en la página.
- `colorzoom/lib/tooltipster/dist/js/tooltipster.bundle.js`
  - Alcance: Front-office.
  - Detalles: La versión completa empaquetada de la biblioteca `tooltipster`, que proporciona la funcionalidad principal para crear tooltips flexibles y personalizables. Esta es la biblioteca principal responsable de las ventanas emergentes de zoom.
- `colorzoom/lib/tooltipster/dist/js/tooltipster.core.js`
  - Alcance: Front-office.
  - Detalles: El archivo JavaScript principal para la biblioteca `tooltipster`. Es posible que `tooltipster.bundle.js` ya incluya esto, pero se enumera por separado, lo que indica una inclusión modular.
- `colorzoom/views/js/colorzoom-combinationstable.js`
  - Alcance: Front-office.
  - Detalles: Este script se dirige específicamente a las tablas de combinaciones de productos. Probablemente contiene lógica para identificar atributos de color/textura dentro de estas tablas e inicializar la funcionalidad de zoom de `tooltipster` en ellos, respetando la configuración `cz_ctab`. Vincula oyentes de eventos a elementos dentro de estas tablas.
- `colorzoom/views/js/colorzoom.js`
  - Alcance: Front-office.
  - Detalles: Este es el JavaScript personalizado principal para el módulo. Es responsable de:
    - Identificar elementos de atributos de color/textura en la página del producto (fuera de las tablas de combinaciones).
    - Inicializar `tooltipster` en estos elementos con configuraciones específicas del módulo (ancho, alto, tipo de animación, mostrar nombre).
    - Manejar la lógica de "Deshabilitar cambio de atributo al tocar" para dispositivos móviles.
    - Potencialmente escuchar eventos `prestashop.on` como `updateProduct` para reinicializar los tooltips si el contenido del producto cambia a través de AJAX.

### 4.5 Hojas de estilo CSS (`views/css/`)

El módulo incluye CSS para estilizar las vistas previas de zoom y la biblioteca `tooltipster`.

- `colorzoom/lib/tooltipster/dist/css/tooltipster.bundle.css`
  - Alcance: Estilo del cliente del Front-office.
  - Detalles: El CSS empaquetado para la biblioteca `tooltipster`, que proporciona un estilo predeterminado para los tooltips (las ventanas de vista previa con zoom).
- `colorzoom/lib/tooltipster/dist/css/tooltipster.core.css`
  - Alcance: Estilo del cliente del Front-office.
  - Detalles: El CSS principal para `tooltipster`, que define estilos fundamentales.
- `colorzoom/views/css/colorszoom.css`
  - Alcance: Estilo del cliente del Front-office.
  - Detalles: CSS personalizado específico para el módulo "Zoom de atributo de color/textura". Este archivo probablemente contiene anulaciones o estilos adicionales para integrar los tooltips de `tooltipster` sin problemas en la página de producto de PrestaShop, asegurando un posicionamiento correcto, tamaños de fuente para los nombres de los atributos y capacidad de respuesta. Los desarrolladores pueden inspeccionar este archivo para encontrar selectores clave para anular en el CSS personalizado de su tema.

### 4.6 Estructura de la plantilla Smarty (`views/templates/`)

El módulo utiliza plantillas Smarty para inyectar su JavaScript y CSS, y para renderizar el contenido de la vista previa con zoom.

- **Plantillas de hook (`views/templates/hook/`)**:
  - `colorzoom/views/header.tpl`
    - Hook: `displayHeader`
    - Propósito: Esta plantilla es responsable de incluir los archivos CSS y JavaScript del módulo en la sección `<head>` de las páginas del front-office. También pasa variables de configuración del back office (como `cz_width`, `cz_height`, `cz_animation`, `cz_name`, `cz_disableclick`, `cz_ctab`, `cz_exclusions`) al JavaScript del front-end, haciéndolas accesibles para la inicialización dinámica.
- **Plantillas de front-office (`views/templates/front/`)**:
  - `colorzoom/views/quickview.tpl`
    - Propósito: Esta plantilla está probablemente diseñada para ser renderizada dentro de una ventana emergente de vista rápida de producto. Contiene el marcado o la lógica necesarios para asegurar que la funcionalidad de zoom se inicialice correctamente para los atributos mostrados en los modales de vista rápida.
  - `colorzoom/views/zoom.tpl`
    - Propósito: Esta es la plantilla principal para el contenido que se muestra dentro de la vista previa con zoom (tooltip). Recibe dinámicamente la URL de la imagen del atributo y el nombre del atributo, renderizándolos dentro de la estructura del tooltip. Es el componente visual que mostrará la biblioteca `tooltipster`.

### 4.7 Esquema de la base de datos y mapa de Hooks

- **Tablas de la base de datos**:
  El módulo no crea ninguna tabla SQL personalizada. Todas sus configuraciones se almacenan en la tabla `ps_configuration` utilizando claves con el prefijo `cz_` (por ejemplo, `cz_width`, `cz_height`, `cz_animation`, `cz_name`, `cz_disableclick`, `cz_exclusions`, `cz_ctab`) y `mypresta_updates`, `update_`, `updatev_` para la gestión de actualizaciones.
- **Tabla de Hooks registrados**:

  | Nombre del Hook | Momento de ejecución | Propósito técnico |
  | --- | --- | --- |
  | `displayHeader` | En la sección `<head>` de cada página del front-office. | Inyecta los archivos CSS y JavaScript del módulo, y pasa variables de configuración al front-end. |
  | `displayProductAdditionalInfo` | Dentro del bloque de información del producto en la página del producto. | Este hook se utiliza para renderizar la inicialización JavaScript necesaria o el marcado específico para la función de zoom en la página del producto, asegurando que esté activa para los atributos de color/textura. |

## 5. Soporte oficial y actualizaciones

Para soporte oficial, actualizaciones del módulo y cualquier asistencia adicional, consulte su cuenta de cliente en MyPresta.eu. Nuestro equipo se dedica a brindar soporte oportuno y garantizar que su módulo funcione de manera óptima.
