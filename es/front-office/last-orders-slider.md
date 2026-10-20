---
title: "Slider de últimos pedidos - Manual de comerciante y guía de configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop 'Slider de últimos pedidos' de MyPresta.eu."
sidebar:
  label: "Slider de últimos pedidos - Manual de comerciante y guía de configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Last orders slider en MyPresta.eu](https://mypresta.eu/modules/front-office-features/last-orders-slider.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/front-office/last-orders-slider/)
>
> ---


# Slider de últimos pedidos

## 1. Requisitos y compatibilidad

- **Versiones de PrestaShop compatibles**: PrestaShop 1.7.6+, 8.x, 9.x
- **Compatibilidad con PHP**: PHP 7.1 - 8.5
- **Requisitos de alojamiento**: Las extensiones PHP estándar (cURL, JSON, OpenSSL) suelen ser suficientes y normalmente están habilitadas por defecto en la mayoría de los entornos de alojamiento compatibles con PrestaShop.

## 2. Recorrido completo por la configuración (Cada ajuste agrupado por pantalla)

### 2.1 Página de configuración del módulo (Back Office > Módulos > Configurar)

Esta es la pantalla de configuración principal para el módulo "Slider de últimos pedidos". Puede acceder a ella navegando a **Módulos > Gestor de módulos** y haciendo clic en "Configurar" junto al módulo "Slider de últimos pedidos".

#### Ajustes generales

- **Qué hace este ajuste:** Esta sección controla el comportamiento fundamental y la apariencia de su slider de pedidos.
- **Efecto de cambiar este ajuste:** Ajustar estos impactará directamente cómo se ve el slider, dónde aparece y qué información muestra a sus clientes.

| Ajuste / Opción | Qué hace este ajuste | Efecto de cambiar este ajuste | Valor recomendado | Escenario / ejemplo de comerciante |
| --- | --- | --- | --- | --- |
| **Habilitar módulo** | Activa o desactiva toda la funcionalidad del slider. | *Cuando está habilitado:* El slider aparecerá en su front office según otros ajustes. *Cuando está deshabilitado:* El slider no será visible para los clientes. | SÍ | Desea ocultar temporalmente el slider para mantenimiento o una campaña especial. |
| **Número de pedidos a mostrar** | Determina cuántos pedidos recientes recorrerá el slider. | *Cuando se establece en 5:* El slider mostrará información de los 5 pedidos más recientes. *Cuando se establece en 10:* Mostrará 10. | 5-10 (dependiendo del volumen de pedidos) | Si tiene un volumen muy alto de pedidos, mostrar más podría ser abrumador. Si tiene menos pedidos, mostrar más asegura que siempre haya contenido. |
| **Estados de pedido a mostrar** | Selecciona qué estados de pedido (por ejemplo, "Pago aceptado", "Entregado") se consideran "pedidos recientes" para el slider. | *Cuando se selecciona "Pago aceptado":* Solo aparecerán los pedidos que hayan alcanzado este estado. *Cuando se selecciona "Cancelado":* Podrían aparecer pedidos cancelados (no recomendado para prueba social). | "Pago aceptado", "Procesando", "Entregado" | Solo desea mostrar pedidos que estén confirmados y en proceso o que hayan sido entregados con éxito, para generar confianza positiva. |
| **Mostrar nombre del cliente** | Controla si se muestra el primer nombre y la inicial del apellido del cliente. | *Cuando está habilitado:* "John D. de Nueva York..." *Cuando está deshabilitado:* "Alguien de Nueva York..." | SÍ | Mostrar un nombre parcial añade un toque personal y hace que los pedidos se sientan más reales, mejorando la prueba social. |
| **Mostrar ciudad del cliente** | Controla si se muestra la ciudad del cliente. | *Cuando está habilitado:* "...de Nueva York acaba de comprar..." *Cuando está deshabilitado:* "...acaba de comprar..." | SÍ | Mostrar la ciudad añade una capa de autenticidad y puede resonar con los clientes locales. |
| **Mostrar nombre del producto** | Controla si se muestra el nombre del producto comprado. | *Cuando está habilitado:* "...acaba de comprar una camiseta." *Cuando está deshabilitado:* "...acaba de realizar un pedido." | SÍ | Mostrar el nombre del producto hace que la compra sea más tangible y puede resaltar artículos populares. |
| **Mostrar imagen del producto** | Controla si se muestra una pequeña imagen del producto comprado. | *Cuando está habilitado:* Aparecerá una pequeña miniatura del producto junto al texto. *Cuando está deshabilitado:* Solo se mostrará texto. | SÍ | Los elementos visuales son atractivos. Una imagen de producto hace que el slider sea más atractivo e informativo. |
| **Velocidad de animación (milisegundos)** | Establece la velocidad con la que el slider realiza la transición entre diferentes pedidos. | *Valor más bajo (por ejemplo, 3000):* Transiciones más rápidas, los pedidos cambian cada 3 segundos. *Valor más alto (por ejemplo, 8000):* Transiciones más lentas, los pedidos cambian cada 8 segundos. | 5000 (5 segundos) | Una velocidad moderada mantiene el slider dinámico sin ser demasiado rápido para leer o demasiado lento para actualizar. |
| **Color del texto** | Establece el color del texto que se muestra en el slider. | *Cuando se establece en #000000 (negro):* El texto será negro. *Cuando se establece en #FF0000 (rojo):* El texto será rojo. | #FFFFFF (blanco) o un color que contraste con su fondo | Elija un color que destaque sobre el color de fondo elegido y que coincida con la estética de su marca. |
| **Color de fondo** | Establece el color de fondo de la barra del slider. | *Cuando se establece en #FFFFFF (blanco):* El fondo del slider será blanco. *Cuando se establece en #000000 (negro):* El fondo del slider será negro. | #000000 (negro) o un color que contraste con su tema | Elija un color que haga visible el slider y complemente el diseño de su tienda. |
| **Hook para mostrar el slider** | Selecciona dónde aparecerá el slider en su tema de PrestaShop. | *Cuando se selecciona "displayTop":* El slider aparece cerca de la parte superior de su tienda. *Cuando se selecciona "displayFooter":* El slider aparece en la parte inferior. | displayTop o displayNavFullWidth | Elija una ubicación prominente donde los clientes lo vean fácilmente sin obstruir contenido crítico. |

#### 2.1.1 Tabla de referencia rápida de configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e impacto |
| --- | --- | --- | --- |
| Configuración del módulo | Habilitar módulo | SÍ | Activa/desactiva el slider. |
| Configuración del módulo | Número de pedidos a mostrar | 5-10 | Controla cuántos pedidos recientes se muestran. |
| Configuración del módulo | Estados de pedido a mostrar | Pago aceptado, Procesando, Entregado | Filtra los pedidos por su estado para su visualización. |
| Configuración del módulo | Mostrar nombre del cliente | SÍ | Muestra el primer nombre y la inicial del apellido del cliente. |
| Configuración del módulo | Mostrar ciudad del cliente | SÍ | Muestra la ciudad del cliente. |
| Configuración del módulo | Mostrar nombre del producto | SÍ | Muestra el nombre del producto comprado. |
| Configuración del módulo | Mostrar imagen del producto | SÍ | Muestra una pequeña imagen del producto comprado. |
| Configuración del módulo | Velocidad de animación (milisegundos) | 5000 | Establece la velocidad de transición entre pedidos. |
| Configuración del módulo | Color del texto | #FFFFFF (blanco) | Define el color del texto en el slider. |
| Configuración del módulo | Color de fondo | #000000 (negro) | Define el color de fondo del slider. |
| Configuración del módulo | Hook para mostrar el slider | displayTop / displayNavFullWidth | Determina la posición del slider en su tema. |

## 3. Solución de problemas para comerciantes y preguntas frecuentes (FAQ)

**P1: El slider no aparece en mi tienda. ¿Qué debo hacer?**
R:

- **Verificar el estado del módulo:** Vaya a **Módulos > Gestor de módulos** y asegúrese de que "Slider de últimos pedidos" esté instalado y habilitado.
- **Verificar la selección del hook:** En la configuración del módulo, verifique que haya seleccionado un "Hook para mostrar el slider" válido (por ejemplo, `displayTop`, `displayNavFullWidth`). Algunos hooks pueden no estar presentes o activos en todos los temas.
- **Borrar caché:** Vaya a **Parámetros avanzados > Rendimiento** y haga clic en "Borrar caché" (o "Borrar caché de Smarty" en versiones anteriores). A veces, la caché de PrestaShop impide que el nuevo contenido aparezca inmediatamente.
- **Verificar estados de pedido:** Asegúrese de haber seleccionado al menos un "Estado de pedido a mostrar" que tenga pedidos recientes asociados. Si ningún pedido coincide con los estados seleccionados, el slider estará vacío.
- **Compatibilidad con el tema:** Si bien el módulo está diseñado para una amplia compatibilidad, los temas muy personalizados pueden requerir ajustes menores. Si todo lo demás falla, póngase en contacto con el soporte de MyPresta.eu.

**P2: El slider se muestra, pero los colores no coinciden con mi tema.**
R:

- **Ajustar colores en la configuración:** Vaya a la página de configuración del módulo. Utilice los ajustes "Color del texto" y "Color de fondo" para seleccionar colores que complementen el diseño de su tienda. Puede usar una herramienta de selección de color (disponible en línea o como extensiones de navegador) para encontrar los códigos hexadecimales exactos de su tema.
- **CSS personalizado (avanzado):** Si las opciones de color del módulo no son suficientes, su webmaster puede añadir reglas CSS personalizadas a la hoja de estilos de su tema para anular los estilos predeterminados del módulo. (Consulte la Sección 7.5 para obtener detalles para desarrolladores).

**P3: El slider está vacío o no se actualiza con nuevos pedidos.**
R:

- **Estados de pedido:** Asegúrese de que la configuración "Estados de pedido a mostrar" incluya los estados de sus pedidos más recientes (por ejemplo, "Pago aceptado", "Entregado"). Si sus pedidos recientes están en un estado no seleccionado, no aparecerán.
- **Pedidos recientes:** El módulo muestra pedidos *recientes*. Si su tienda no ha tenido ningún pedido en un tiempo, o si el "Número de pedidos a mostrar" está configurado demasiado bajo, puede aparecer vacío.
- **Caché:** Una vez más, borrar la caché de PrestaShop (**Parámetros avanzados > Rendimiento**) puede ayudar a garantizar que el módulo obtenga los datos más recientes.

**P4: ¿Cómo traduzco el texto del slider a otros idiomas?**
R:

- **Herramienta de traducción de PrestaShop:** Vaya a **Internacional > Traducciones**.
- Seleccione "Traducciones de módulos instalados", elija su tema y luego seleccione su idioma.
- Busque el módulo "Slider de últimos pedidos" en la lista. Podrá traducir cualquier cadena de texto codificada (como "acaba de comprar" o "de") que utilice el módulo.
- **Contenido dinámico:** Los nombres de los clientes, las ciudades y los nombres de los productos se extraen directamente de los datos de su tienda y aparecerán en el idioma en el que se introdujeron o configuraron en su catálogo de productos.

**P5: El slider es demasiado rápido/lento o muestra demasiados/pocos pedidos.**
R:

- **Velocidad de animación:** Ajuste la configuración "Velocidad de animación (milisegundos)" en la configuración del módulo. Un número más alto significa transiciones más lentas.
- **Número de pedidos:** Modifique la configuración "Número de pedidos a mostrar" para controlar cuántos pedidos únicos se muestran. Experimente con estos valores para encontrar el equilibrio perfecto para el tráfico y el volumen de pedidos de su tienda.

## 4. Guía para desarrolladores y webmasters (Arquitectura técnica y mapa de código)

Esta sección proporciona una inmersión técnica profunda en el módulo "Slider de últimos pedidos", destinada a desarrolladores, webmasters y agencias técnicas.

### 4.1 Resumen de la arquitectura

El módulo "Slider de últimos pedidos" (`lastord`) es un módulo estándar de PrestaShop diseñado principalmente para mostrar contenido dinámico en el front office. Aprovecha el sistema de hooks de PrestaShop para inyectar su contenido en varias partes del tema. La lógica central reside dentro del archivo principal del módulo (`index.php`), que maneja la configuración, la recuperación de datos y la representación de plantillas. No introduce controladores personalizados ni ObjectModels complejos, sino que se basa en consultas directas a la base de datos (a través de `Db::getInstance()`) para obtener datos de pedidos y plantillas Smarty para la presentación. El estilo se gestiona a través de un archivo CSS dedicado.

### 4.2 Controladores (`controllers/`)

Este módulo **no** utiliza controladores de administración de Front Office o Back Office personalizados. Toda la configuración se maneja a través del método `getContent()` dentro del archivo principal del módulo, y la representación del front office se realiza directamente a través de métodos de hook.

### 4.3 Clases y modelos principales (`classes/`)

Este módulo **no** define ninguna clase u ObjectModels personalizados dentro del directorio `classes/`. Toda la obtención de datos y la lógica de negocio están encapsuladas dentro de la clase `Lastord` en `index.php`.

### 4.4 Activos de JavaScript (`views/js/`)

Este módulo **no** incluye ningún archivo JavaScript personalizado. La funcionalidad de animación y slider probablemente se maneja mediante animaciones CSS o un script en línea muy ligero dentro de la plantilla, o mediante una biblioteca de terceros ya cargada por PrestaShop.

### 4.5 Hojas de estilo CSS (`views/css/`)

- **`lastord/views/css/lastord.css`**
  - **Alcance:** Estilo del front office para el cliente.
  - **Componentes e contenedores principales de la interfaz de usuario que estiliza:** Esta hoja de estilos es responsable de la apariencia visual de la propia barra del slider de pedidos, incluyendo su posicionamiento, fondo, estilos de texto y, potencialmente, las propiedades de animación.
  - **Selectores de clase CSS clave que los desarrolladores pueden anular en su tema:**
    - `.lastord_wrapper`: El contenedor principal para todo el slider.
    - `.lastord_item`: Elemento de pedido individual dentro del slider.
    - `.lastord_text`: El contenido de texto (cliente, producto, ciudad).
    - `.lastord_image`: El contenedor de la imagen del producto.
    - Reglas `@keyframes` (si se definen para la animación).
      Los desarrolladores pueden anular estos selectores en el `custom.css` o `theme.css` de su tema para que coincidan con sus requisitos de diseño específicos.

### 4.6 Estructura de la plantilla Smarty (`views/templates/`)

- **Plantillas de hook (`views/templates/hook/`)**:

  - **`lastord/views/templates/hook/lo_orders.tpl`**
    - **Hook:** Esta es la plantilla principal renderizada por los métodos `hook` del módulo (por ejemplo, `hookDisplayTop`, `hookDisplayNavFullWidth`, `hookDisplayFooter`, etc.).
    - **Propósito:** Contiene la estructura HTML para el contenedor del slider e itera a través de la variable `$orders` (pasada desde la lógica PHP del módulo) para mostrar cada pedido reciente. Incluye lógica condicional para mostrar/ocultar el nombre del cliente, la ciudad, el nombre del producto y la imagen según la configuración del módulo. También aplica estilos en línea para los colores de texto y fondo.
  - **`lastord/views/templates/hook/displayBanner.tpl`**
    - **Hook:** `displayBanner`
    - **Propósito:** Esta plantilla probablemente actúa como un envoltorio o punto de inclusión directa para `lo_orders.tpl` cuando el módulo está enganchado a `displayBanner`. Asegura que el contenido del slider se renderice correctamente dentro de este hook específico.
  - **`lastord/views/templates/hook/displayNavFullWidth.tpl`**
    - **Hook:** `displayNavFullWidth`
    - **Propósito:** Similar a `displayBanner.tpl`, esta plantilla se utiliza para renderizar el contenido de `lo_orders.tpl` cuando el módulo está enganchado a `displayNavFullWidth`.
  - **`lastord/views/templates/hook/displayTop.tpl`**
    - **Hook:** `displayTop`
    - **Propósito:** Esta plantilla se utiliza para renderizar el contenido de `lo_orders.tpl` cuando el módulo está enganchado a `displayTop`.
- **Plantillas de administración (`views/templates/admin/`)**:

  - **`lastord/views/templates/admin/orderstates.tpl`**
    - **Propósito:** Esta plantilla se utiliza dentro del método `getContent()` del módulo para renderizar la lista de casillas de verificación de estados de pedido en la página de configuración del back office. Itera a través de los estados de pedido disponibles y los muestra con su estado de selección actual.
- **Plantillas de front office (`views/templates/front/`)**: Ninguna identificada.

### 4.7 Esquema de la base de datos y mapa de Hooks

- **Tablas de la base de datos**:

  - Este módulo no crea tablas SQL personalizadas.
  - Almacena sus configuraciones en la tabla `ps_configuration` utilizando claves como `LASTORD_ENABLED`, `LASTORD_ORDERS_COUNT`, `LASTORD_ORDER_STATES`, `LASTORD_DISPLAY_NAME`, `LASTORD_DISPLAY_CITY`, `LASTORD_DISPLAY_PRODUCT`, `LASTORD_DISPLAY_IMAGE`, `LASTORD_ANIMATION_SPEED`, `LASTORD_TEXT_COLOR`, `LASTORD_BACKGROUND_COLOR`, `LASTORD_HOOK`.
- **Tabla de Hooks registrados**:

| Nombre del Hook | Momento de ejecución | Propósito técnico |
| --- | --- | --- |
| `displayHeader` | En la sección `<head>` del front office. | Se utiliza para registrar activos (CSS) y potencialmente JavaScript en línea. |
| `displayTop` | Típicamente en la parte superior de la página, debajo de la cabecera. | Renderiza el slider en una posición superior prominente. |
| `displayNavFullWidth` | A menudo una sección de ancho completo encima o debajo de la navegación principal. | Renderiza el slider en un área de navegación de ancho completo. |
| `displayBanner` | Un hook común para banners, a menudo en la parte superior. | Renderiza el slider como un banner. |
| `displayLeftColumn` | En la barra lateral izquierda. | Renderiza el slider en la columna izquierda. |
| `displayRightColumn` | En la barra lateral derecha. | Renderiza el slider en la columna derecha. |
| `displayFooter` | En la sección del pie de página. | Renderiza el slider en la parte inferior de la página. |
| `displayProductButtons` | En la página del producto, cerca del botón de añadir al carrito. | Renderiza el slider en la página del producto para enfocar la conversión. |
| `displayFooterProduct` | En la sección del pie de página del producto. | Renderiza el slider en la parte inferior de la página del producto. |

## 5. Soporte oficial y actualizaciones

Para las últimas actualizaciones, correcciones de errores y soporte oficial para el módulo "Slider de últimos pedidos", consulte su cuenta de cliente en [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nuestro equipo de soporte está disponible para ayudar con cualquier problema técnico o pregunta que pueda tener con respecto a la funcionalidad e integración del módulo.
