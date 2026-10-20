---
title: "Hot Info - barra lateral inferior - Manual de Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop Hot Info - barra lateral inferior de MyPresta.eu."
sidebar:
  label: "Hot Info - barra lateral inferior - Manual de Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Hot Info - bottom sidebar en MyPresta.eu](https://mypresta.eu/modules/front-office-features/hot-info-bottom-sidebar.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/front-office/hot-info-bottom-sidebar/)
>
> ---


# Hot Info - barra lateral inferior

## 1. Requisitos y Compatibilidad

- **Versiones de PrestaShop compatibles**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilidad con PHP**: PHP 7.1 - 8.5
- **Requisitos de alojamiento**: Las extensiones PHP estándar (cURL, JSON, OpenSSL) suelen ser necesarias para PrestaShop y normalmente están disponibles en cualquier entorno de alojamiento moderno.

## 2. Recorrido Completo por la Configuración (Cada Ajuste Agrupado por Pantalla)

### 2.1 Página de Configuración del Módulo (Back Office > Módulos > Configurar)

Después de instalar el módulo, haga clic en "Configurar" para acceder a sus ajustes. Aquí es donde definirá el contenido y la apariencia de su barra lateral "Hot Info".

#### **Contenido para el Bloque Hot Info**

- **Qué hace este ajuste:** Esta es el área principal donde introducirá el contenido real que los clientes verán en la barra lateral inferior. Es un editor de texto enriquecido (WYSIWYG - Lo que ves es lo que obtienes), similar a lo que podría usar para descripciones de productos o publicaciones de blog.
- **Efecto de cambiar este ajuste:**
  - *Cuando se añade contenido:* El texto, las imágenes, los enlaces o el HTML que introduzca aquí se mostrarán en el bloque "Hot Info" de su tienda.
  - *Cuando se deja vacío:* El bloque "Hot Info" podría seguir apareciendo, pero estará vacío, o el módulo podría no mostrarse en absoluto (dependiendo de otros ajustes y del comportamiento del tema). Es crucial añadir contenido aquí para que el módulo sea útil.
- **Valor recomendado:** Introduzca aquí su "información candente" deseada. Utilice un lenguaje claro y conciso y llamadas a la acción contundentes.
- **Escenario / ejemplo de comerciante:** Podría añadir "¡VENTA FLASH! ¡Obtenga un 20% de descuento en todos los artículos de verano con el código VERANO20! [Comprar ahora]" con un enlace a su colección de verano. O "¡Envío gratuito en todos los pedidos superiores a 50 €!"

#### **Color de Fondo**

- **Qué hace este ajuste:** Controla el color de fondo del bloque "Hot Info". Puede seleccionar un color utilizando una herramienta de selección de color.
- **Efecto de cambiar este ajuste:**
  - *Cuando se establece un color específico (por ejemplo, #FF0000 para rojo):* El fondo del bloque "Hot Info" se mostrará en ese color elegido.
  - *Cuando se deja por defecto o transparente:* Normalmente heredará el color de fondo de su tema o será transparente, lo que podría hacer que se mezcle demasiado o sea difícil de leer.
- **Valor recomendado:** Elija un color que complemente la marca de su tienda o que destaque para llamar la atención, según su objetivo. Un color contrastante puede ser muy efectivo.
- **Escenario / ejemplo de comerciante:** Si su tienda utiliza mucho azul, podría elegir un naranja o amarillo vibrante para que un anuncio de venta destaque.

#### **Color del Borde**

- **Qué hace este ajuste:** Controla el color del borde alrededor del bloque "Hot Info".
- **Efecto de cambiar este ajuste:**
  - *Cuando se establece un color específico (por ejemplo, #000000 para negro):* El borde del bloque "Hot Info" se mostrará en ese color elegido.
  - *Cuando se deja por defecto o transparente:* El bloque podría aparecer sin un borde visible, o podría heredar un color de borde de su tema.
- **Valor recomendado:** A menudo, un color de borde que coincida con el color de su texto o un tono ligeramente más oscuro que el color de fondo funciona bien.
- **Escenario / ejemplo de comerciante:** Si su fondo es azul claro, un borde azul más oscuro puede darle un aspecto limpio y definido.

#### **Tamaño del Borde (en píxeles)**

- **Qué hace este ajuste:** Determina el grosor del borde alrededor del bloque "Hot Info", medido en píxeles.
- **Efecto de cambiar este ajuste:**
  - *Cuando se establece un valor como '2':* El bloque tendrá un borde de 2 píxeles de grosor.
  - *Cuando se establece en '0':* No se mostrará ningún borde.
- **Valor recomendado:** Comience con un valor pequeño como '1' o '2' para un borde sutil. Auméntelo si desea un marco más pronunciado.
- **Escenario / ejemplo de comerciante:** Un borde de 2px puede enmarcar sutilmente su mensaje, haciéndolo parecer un elemento distinto en la página.

#### **Altura (en píxeles)**

- **Qué hace este ajuste:** Controla la altura fija del bloque "Hot Info", medida en píxeles.
- **Efecto de cambiar este ajuste:**
  - *Cuando se establece un valor como '50':* El bloque tendrá 50 píxeles de alto.
  - *Cuando el contenido excede la altura:* Si su contenido es más alto que la altura especificada, aparecerá una barra de desplazamiento dentro del bloque, permitiendo a los clientes desplazarse por el contenido.
- **Valor recomendado:** Mantenga este valor relativamente pequeño (por ejemplo, 40-60px) para evitar ocupar demasiado espacio en la pantalla, especialmente en dispositivos móviles. Ajuste según la cantidad de contenido que tenga.
- **Escenario / ejemplo de comerciante:** Si tiene un mensaje corto de una sola línea, una altura de 40px podría ser perfecta. Si tiene varias líneas de texto, podría necesitar 60-80px.

#### **Idioma Predeterminado (PS\_LANG\_DEFAULT)**

- **Qué hace este ajuste:** Este es un ajuste estándar de PrestaShop que define el idioma predeterminado para su tienda. Aunque no es configurado directamente por este módulo, el campo de contenido del módulo normalmente mostrará el contenido para el idioma actualmente seleccionado en el back office, por defecto este.
- **Efecto de cambiar este ajuste:** Esto afecta el idioma predeterminado de toda su tienda PrestaShop y cómo se gestiona el contenido multilingüe. Para este módulo, significa que el contenido que introduzca se asociará con el idioma que esté editando actualmente en el back office.
- **Valor recomendado:** Esto debe establecerse en el idioma principal de su tienda.
- **Escenario / ejemplo de comerciante:** Si su mercado principal es España, esto se establecería en español. Cuando introduzca contenido para el bloque "Hot Info", asegúrese de que está editando en el idioma correcto si su tienda admite varios idiomas.

#### **Actualizaciones de MyPresta.eu (mypresta\_updates, update\_, updatev\_)**

- **Qué hacen estos ajustes:** Estos son ajustes internos utilizados por los módulos de MyPresta.eu para buscar y gestionar actualizaciones. Normalmente almacenan información sobre la versión del módulo y cuándo se verificó por última vez si había actualizaciones.
- **Efecto de cambiar estos ajustes:**
  - *Cuando está habilitado/activo:* El módulo puede comunicarse con los servidores de MyPresta.eu para notificarle nuevas versiones o parches de seguridad.
  - *Cuando está deshabilitado/inactivo:* El módulo no buscará actualizaciones automáticamente.
- **Valor recomendado:** Deje estos ajustes tal como están. Son esenciales para mantener su módulo actualizado y seguro.
- **Escenario / ejemplo de comerciante:** Normalmente no interactúa con estos directamente. Aseguran que se le solicite en su back office de PrestaShop cuando haya una nueva versión del módulo disponible para descargar desde su cuenta de MyPresta.eu.

### 2.2 Tabla de Referencia Rápida de Configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| Configuración del Módulo | **Contenido para el Bloque Hot Info** | Su mensaje personalizado | El texto, imágenes y enlaces reales que se muestran en la barra lateral inferior. |
| Configuración del Módulo | **Color de Fondo** | Elegir para que coincida/contraste con el tema | Establece el color de fondo del bloque de información. |
| Configuración del Módulo | **Color del Borde** | Elegir para que coincida/contraste con el tema | Establece el color del borde alrededor del bloque de información. |
| Configuración del Módulo | **Tamaño del Borde (en píxeles)** | 1 o 2 | Define el grosor del borde. Establezca en 0 para no tener borde. |
| Configuración del Módulo | **Altura (en píxeles)** | 40-60 | Establece la altura fija del bloque de información. El contenido que exceda esto se desplazará. |
| Configuración del Módulo | **PS\_LANG\_DEFAULT** | Idioma principal de su tienda | Configuración de idioma predeterminada de PrestaShop, afecta la edición de contenido. |
| Configuración del Módulo | **Actualizaciones de MyPresta.eu** | Habilitado | Ajustes internos para las comprobaciones de actualización del módulo. |

## 3. Solución de Problemas para Comerciantes y Preguntas Frecuentes (FAQ)

**P1: Mi bloque "Hot Info" no aparece en el front office.**

- **R:** Primero, asegúrese de que el módulo esté instalado y habilitado en **Módulos > Gestor de módulos**. Segundo, verifique si realmente ha añadido contenido en el campo "Contenido para el Bloque Hot Info" en la configuración del módulo. Un bloque vacío podría no renderizarse. Finalmente, borre la caché de PrestaShop (**Parámetros avanzados > Rendimiento > Borrar caché**) y la caché de su navegador.

**P2: El bloque "Hot Info" se ve extraño o no coincide con el estilo de mi tema.**

- **R:** El módulo proporciona opciones de estilo básicas (fondo, color/tamaño del borde, altura). Si aún así choca con su tema, el CSS de su tema podría estar anulando los estilos del módulo.
  - **Solución para Comerciantes:** Intente ajustar los colores de fondo y borde en la configuración del módulo para ver si puede encontrar una mejor coincidencia. Si no, es posible que necesite un webmaster para añadir CSS personalizado a su tema para apuntar y estilizar específicamente el bloque del módulo.
  - **Solución para Webmasters:** Inspeccione el elemento en las herramientas de desarrollo del navegador para identificar reglas CSS conflictivas y aplique reglas más específicas o `!important` en el archivo CSS personalizado de su tema.

**P3: ¿Cómo añado imágenes o enlaces al contenido de "Hot Info"?**

- **R:** Utilice el editor de texto enriquecido proporcionado para el ajuste "Contenido para el Bloque Hot Info". Tiene botones para insertar imágenes, crear enlaces, formatear texto (negrita, cursiva) y más, como un procesador de texto estándar. Haga clic en el icono "Imagen" para subir e insertar una imagen, o seleccione texto y haga clic en el icono "Enlace" para añadir un hipervínculo.

**P4: ¿Puedo hacer que el bloque "Hot Info" aparezca solo en ciertas páginas?**

- **R:** Este módulo, en su versión actual, está diseñado para aparecer globalmente en todas las páginas donde se ejecuta el hook `displayHeader`. Si necesita visibilidad específica de la página, necesitaría un desarrollo personalizado para modificar la lógica de visualización del módulo o usar un módulo separado diseñado para la visualización condicional de contenido.

**P5: El selector de color no funciona o no aparece.**

- **R:** Asegúrese de que JavaScript esté habilitado en su navegador. A veces, los conflictos con otros módulos o el JavaScript del tema pueden impedir que el selector de color se cargue correctamente. Intente borrar la caché y las cookies de su navegador. Si el problema persiste, podría indicar un conflicto de JavaScript más complejo, que un webmaster debería investigar.

## 4. Guía para Desarrolladores y Webmasters (Arquitectura Técnica y Mapa de Código)

Esta sección proporciona una descripción técnica detallada del módulo "Hot Info - barra lateral inferior" para desarrolladores y webmasters.

### 4.1 Descripción General de la Arquitectura

El módulo `hotinfo` es un módulo estándar de PrestaShop que sigue el patrón MVC cuando es aplicable. Funciona principalmente como un módulo de visualización, inyectando contenido en el hook `displayHeader`. La configuración se gestiona a través del método `getContent()` de la clase principal del módulo, almacenando los ajustes directamente en `ps_configuration`. Utiliza un editor de texto enriquecido (TinyMCE) para la entrada de contenido y un selector de color JavaScript para las opciones de estilo.

### 4.2 Controladores (`controllers/`)

Este módulo no utiliza controladores personalizados de front-office o back-office. Toda la configuración se gestiona dentro del archivo principal del módulo `hotinfo.php` a través del método `getContent()`.

### 4.3 Clases y Modelos Principales (`classes/`)

Este módulo no define ninguna clase personalizada ni extiende `ObjectModel`. Todos los datos (configuración) se almacenan directamente en la tabla `ps_configuration`.

### 4.4 Recursos JavaScript (`views/js/`)

- **`hotinfo/jscolor/jscolor.js`**

  - **Ámbito:** Back-office (página de configuración del módulo).
  - **Descripción:** Esta es una biblioteca JavaScript de terceros que proporciona una interfaz de selección de color fácil de usar. Normalmente se inicializa en campos de entrada con una clase específica (por ejemplo, `jscolor`) para permitir a los administradores seleccionar visualmente los colores para el fondo y el borde del bloque "Hot Info". Se vincula a los campos de entrada y actualiza sus valores en función de la selección de color del usuario.
- **`hotinfo/tinymce16.js`**

  - **Ámbito:** Back-office (página de configuración del módulo).
  - **Descripción:** Este script probablemente inicializa y configura una versión del editor de texto enriquecido TinyMCE para el área de texto "Contenido para el Bloque Hot Info". Transforma un `<textarea>` HTML estándar en un editor con muchas funciones, lo que permite a los administradores formatear texto, insertar imágenes, crear enlaces y gestionar contenido HTML sin codificación directa. Este script se vincularía al elemento textarea relevante y proporcionaría la interfaz del editor.

### 4.5 Hojas de Estilo CSS (`views/css/`)

- **`hotinfo/css/hotinfo.css`**
  - **Ámbito:** Front-office (tienda orientada al cliente).
  - **Descripción:** Esta hoja de estilo contiene las reglas CSS principales para la barra lateral inferior "Hot Info". Define el posicionamiento fijo, las dimensiones, el fondo, el borde y el estilo del texto para el bloque.
  - **Selectores clave (los desarrolladores pueden anular):**
    - `#hotinfo_block`: El contenedor principal para todo el bloque "Hot Info". Aquí es donde se aplican `position: fixed; bottom: 0; width: 100%;` y otros estilos globales.
    - `#hotinfo_block .hotinfo_content`: El contenedor interno para el contenido real, donde `overflow-y: auto;` podría aplicarse si el contenido excede la altura definida.
    - Estilos para `p`, `a`, `img` dentro de `#hotinfo_block` para asegurar que el contenido se vea bien.
  - **Estrategia de anulación:** Los desarrolladores pueden anular estos estilos añadiendo reglas CSS más específicas en el archivo `custom.css` o `theme.css` de su tema, o creando un tema hijo y modificando directamente el CSS del módulo si es necesario.

### 4.6 Estructura de Plantillas Smarty (`views/templates/`)

- **`hotinfo/hotinfo.tpl`**

  - **Ámbito:** Back-office (página de configuración del módulo).
  - **Descripción:** Esta plantilla se utiliza para renderizar el formulario de configuración dentro del back office de PrestaShop al acceder a la página de configuración del módulo. Contiene la estructura HTML para el editor de texto enriquecido, los selectores de color y los campos de entrada para los ajustes de altura y borde. Utiliza variables Smarty para rellenar previamente los campos del formulario con los valores de configuración actuales.
- **`hotinfo/views/templates/hook/hotinfo.tpl`**

  - **Ámbito:** Front-office (tienda orientada al cliente).
  - **Descripción:** Esta plantilla es responsable de renderizar el bloque "Hot Info" en la tienda. Está enganchada a `displayHeader`. Recupera el contenido configurado, el color de fondo, el color del borde, el tamaño del borde y la altura de las variables Smarty pasadas por el módulo y las aplica a la estructura HTML.
  - **Elementos clave:**
    - Un `div` principal con un ID como `hotinfo_block` para el posicionamiento fijo.
    - Un `div` interno para el contenido, potencialmente con `overflow: auto;` para el desplazamiento.
    - El contenido real se renderiza utilizando `{html_entity_decode($hotinfo_body)}` para mostrar el HTML del editor de texto enriquecido.
  - **Hook:** `displayHeader` (aunque visualmente aparece en la parte inferior, el hook está en el encabezado para asegurar que se cargue temprano).

### 4.7 Esquema de Base de Datos y Mapa de Hooks

- **Tablas de Base de Datos**:
  El módulo no crea ninguna tabla SQL personalizada. Todos los ajustes de configuración se almacenan en la tabla estándar `ps_configuration` de PrestaShop.

  - Entradas de `PS_CONFIGURATION`:
    - `HOTINFO_BODY`: Almacena el contenido HTML para el bloque "Hot Info" (multilingüe).
    - `HOTINFO_BG_COLOR`: Almacena el valor hexadecimal del color de fondo.
    - `HOTINFO_BR_COLOR`: Almacena el valor hexadecimal del color del borde.
    - `HOTINFO_BR_SIZE`: Almacena el valor entero para el grosor del borde.
    - `HOTINFO_HEIGHT`: Almacena el valor entero para la altura del bloque.
    - `MYPRESTA_UPDATES`, `UPDATE_`, `UPDATEV_`: Claves internas para el mecanismo de actualización de MyPresta.eu.
- **Tabla de Hooks Registrados**:

| Nombre del Hook | Momento de Ejecución | Propósito Técnico |
| --- | --- | --- |
| `displayHeader` | Se ejecuta en la sección `<head>` de cada página. | El módulo utiliza este hook para inyectar sus archivos CSS y JavaScript, y para renderizar la estructura HTML principal del bloque "Hot Info". Aunque el bloque se posiciona visualmente en la parte inferior, renderizarlo a través de `displayHeader` asegura que esté disponible temprano en la carga de la página y pueda ser estilizado con `position: fixed;` de manera efectiva. |

## 5. Soporte Oficial y Actualizaciones

Para las últimas actualizaciones, correcciones de errores y soporte oficial para el módulo "Hot Info - barra lateral inferior", consulte su cuenta de cliente en [MyPresta.eu](https://mypresta.eu/). Puede descargar la versión más reciente del módulo desde su historial de pedidos. Para cualquier asistencia técnica o consulta, póngase en contacto directamente con el soporte de MyPresta.eu.
