---
title: "Pestaña de Ofertas en la Página de Inicio - Manual de Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop 'Pestaña de Ofertas en la Página de Inicio' de MyPresta.eu."
sidebar:
  label: "Pestaña de Ofertas en la Página de Inicio - Manual de Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Specials Homepage Tab en MyPresta.eu](https://mypresta.eu/modules/front-office-features/specials-homepage-tab.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/front-office/specials-homepage-tab/)
>
> ---


# Pestaña de Ofertas en la Página de Inicio

## 1. Requisitos y Compatibilidad

- **Versiones de PrestaShop Compatibles**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilidad con PHP**: PHP 5.6 - 8.5
- **Requisitos de Alojamiento**: Las extensiones estándar de PHP (cURL, JSON, OpenSSL) suelen ser necesarias para una instalación de PrestaShop y son suficientes para este módulo.

## 2. Recorrido Completo por la Configuración (Cada Ajuste Agrupado por Pantalla)

### 2.1 Página de Configuración del Módulo (Back Office > Módulos > Configurar)

Después de la instalación, haz clic en "Configurar" junto al módulo "Pestaña de Ofertas en la Página de Inicio" para acceder a sus ajustes.

#### Ajustes y Opciones:

- **Número de productos**

  - **Qué hace este ajuste:** Controla cuántos productos en oferta se mostrarán dentro de la pestaña "Ofertas" en tu página de inicio.
  - **Efecto de cambiar este ajuste:**
    - *Cuando se establece un número mayor (por ejemplo, 12):* Más productos serán visibles en la pestaña, ofreciendo a los clientes una selección más amplia de ofertas. Esto podría requerir más desplazamiento o paginación dependiendo de tu tema.
    - *Cuando se establece un número menor (por ejemplo, 4):* Se mostrarán menos productos, creando una visualización más concisa. Esto puede ser útil si deseas destacar solo tus mejores ofertas o mantener la página de inicio limpia.
  - **Valor recomendado:** Comienza con un número que se ajuste bien al diseño de tu tema (por ejemplo, 8 o 12) y ajústalo según cuántas ofertas especiales tengas normalmente y cuánto espacio quieras que ocupen.
  - **Escenario / ejemplo de comerciante:** Si tienes muchos productos en oferta y quieres mostrar variedad, configúralo en 12. Si prefieres una página de inicio minimalista y solo quieres destacar algunas ofertas estrella, configúralo en 4.
- **Productos aleatorios**

  - **Qué hace este ajuste:** Determina si los productos en oferta mostrados en la pestaña se presentan en un orden fijo (por ejemplo, por ID, fecha de adición) o en un orden aleatorio cada vez que se carga la página.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está habilitado (SÍ):* Cada vez que un cliente visita tu página de inicio, el orden de los productos en la pestaña "Ofertas" se aleatorizará. Esto asegura que diferentes productos obtengan visibilidad y evita que los mismos pocos artículos estén siempre en la parte superior.
    - *Cuando está deshabilitado (NO):* Los productos se mostrarán en un orden consistente y no aleatorio (normalmente por ID de producto o fecha de creación, dependiendo de la clasificación predeterminada de PrestaShop para ofertas). Esto significa que los mismos productos siempre aparecerán primero.
  - **Valor recomendado:** **SÍ**. Aleatorizar productos es generalmente recomendable para dar a todas tus ofertas especiales una oportunidad justa de ser vistas y para mantener la página de inicio fresca para los clientes que regresan.
  - **Escenario / ejemplo de comerciante:** Si tienes 20 productos en oferta pero solo muestras 8, habilitar "Productos aleatorios" asegura que, con el tiempo, los 20 productos aparecerán eventualmente en la pestaña, en lugar de solo los primeros 8.

#### Otras Claves de Configuración (Ajustes Internos de PrestaShop):

El módulo también interactúa con varias claves de configuración centrales de PrestaShop. Aunque estas no son directamente configurables dentro del propio módulo, comprender su propósito ayuda en la resolución de problemas o la personalización avanzada:

- `PS_CATALOG_MODE`: Si tu tienda está en modo catálogo (sin precios, sin añadir al carrito), los precios especiales no serán relevantes.
- `PS_LANG_DEFAULT`: El idioma predeterminado de tu tienda, utilizado para recuperar nombres y descripciones de productos.
- `PS_BO_ALLOW_EMPLOYEE_FORM_LANG`: Determina si los empleados pueden cambiar el idioma de los formularios en el back office.
- `PS_TAX_ADDRESS_TYPE`: Cómo se calculan los impuestos (por ejemplo, según la dirección de entrega o de factura).
- `PS_COUNTRY_DEFAULT`: El país predeterminado para tu tienda, que afecta los cálculos de impuestos y envío.
- `PS_NB_DAYS_NEW_PRODUCT`: El número de días que un producto se considera "nuevo". (No directamente relacionado con las ofertas, pero a menudo se encuentra en módulos que listan productos).

### 2.2 Tabla de Referencia Rápida de Configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| Configuración del Módulo | Número de productos | 8-12 (Ajustar al tema) | Establece cuántos productos en oferta se muestran en la pestaña. |
| Configuración del Módulo | Productos aleatorios | SÍ | Aleatoriza el orden de los productos en la pestaña para una visualización fresca. |

## 3. Resolución de Problemas del Comerciante y Preguntas Frecuentes (FAQ)

**P1: Mi pestaña "Ofertas" está vacía o no muestra ningún producto, pero tengo productos en oferta.**

- **R:** Primero, asegúrate de que tus productos estén correctamente marcados como "en oferta" en la configuración de sus productos en el back office de PrestaShop (en la pestaña "Precios", asegúrate de que los "Precios específicos" estén configurados y activos). Además, verifica la configuración de "Número de productos" en la configuración del módulo; si está configurado en 0, no se mostrarán productos. Finalmente, borra la caché de PrestaShop (**Parámetros Avanzados > Rendimiento > Borrar caché**).

**P2: La pestaña "Ofertas" no aparece en mi página de inicio en absoluto.**

- **R:**
  1.  **Módulo Habilitado:** Ve a **Módulos > Gestor de Módulos** y asegúrate de que el módulo "Pestaña de Ofertas en la Página de Inicio" esté habilitado.
  2.  **Enganchado Correctamente:** El módulo utiliza `displayHomeTab` y `displayHomeTabContent`. Tu tema debe ser compatible con estos hooks para que la pestaña aparezca. La mayoría de los temas estándar de PrestaShop lo son. Si estás utilizando un tema muy personalizado, es posible que no esté llamando a estos hooks.
  3.  **Caché:** Siempre borra la caché de PrestaShop (**Parámetros Avanzados > Rendimiento > Borrar caché**) después de instalar o configurar módulos.
  4.  **Compatibilidad del Tema:** Aunque el módulo está diseñado para ser compatible, los temas muy antiguos o altamente personalizados podrían requerir pequeños ajustes. Si los problemas persisten, contacta con el soporte de MyPresta.eu.

**P3: Los productos en la pestaña "Ofertas" no se ven bien o no coinciden con el diseño de mi tema.**

- **R:** El módulo utiliza el estilo existente de tu tema para las listas de productos. Si los productos se ven mal, suele ser un problema de CSS con tu tema en lugar del módulo en sí.
  - **Verificar CSS del Tema:** Inspecciona el CSS de tu tema para los estilos de lista de productos.
  - **CSS Personalizado:** Es posible que necesites añadir CSS personalizado al archivo `custom.css` de tu tema (si está disponible) o editar directamente la hoja de estilos de tu tema para ajustar la apariencia.
  - **Responsividad Móvil:** Prueba en diferentes dispositivos. Si se ve bien en el escritorio pero no en el móvil, es un problema de responsividad con el CSS de tu tema.

**Q4: ¿Puedo cambiar el título de la pestaña "Ofertas" (por ejemplo, a "Gangas" o "Promociones")?**

- **R:** El módulo utiliza la traducción predeterminada de PrestaShop para "Ofertas". Para cambiarlo, normalmente irías a **Internacional > Traducciones**, seleccionarías "Traducciones de módulos instalados", elegirías tu tema y luego buscarías el módulo "Pestaña de Ofertas en la Página de Inicio". Luego podrás editar la traducción para el título de la pestaña.

**P5: ¿Por qué algunos productos que están en oferta no aparecen en la pestaña?**

- **R:**
  1.  **Límite de Número de Productos:** Verifica la configuración de "Número de productos" en la configuración del módulo. Si tienes más ofertas que este límite, solo se mostrará el primer conjunto (o aleatorio, si está habilitado).
  2.  **Visibilidad del Producto:** Asegúrate de que el producto esté activo, visible y tenga un precio específico real configurado (no solo una reducción de precio regular).
  3.  **Caché:** Borra la caché de PrestaShop.

## 4. Guía para Desarrolladores y Webmasters (Arquitectura Técnica y Mapa de Código)

### 4.1 Visión General de la Arquitectura

El módulo "Pestaña de Ofertas en la Página de Inicio" (`blockspecialstab`) es un módulo ligero de PrestaShop centrado principalmente en la visualización en el front-office. Se adhiere a la arquitectura estándar de módulos de PrestaShop, aprovechando los hooks para inyectar contenido en la página de inicio. No introduce controladores, modelos o JavaScript/CSS complejos personalizados más allá de lo necesario para el templating básico. Su funcionalidad principal gira en torno a la obtención de productos con precios específicos y su renderización dentro de una estructura de pestañas.

### 4.2 Controladores (`controllers/`)

Este módulo **no** incluye ningún controlador de Front-Office o Back-Office Admin personalizado. Toda la lógica está encapsulada dentro de la clase principal del módulo (`blockspecialstab.php`).

### 4.3 Clases y Modelos Principales (`classes/`)

Este módulo **no** introduce ninguna clase personalizada o definiciones de `ObjectModel`. Se basa en las clases principales de PrestaShop `Product` y `SpecificPrice` para recuperar datos de productos.

### 4.4 Activos JavaScript (`views/js/`)

Este módulo **no** incluye ningún archivo JavaScript personalizado. La funcionalidad de cambio de pestañas y la visualización de productos son manejadas por el JavaScript existente del tema (por ejemplo, jQuery, Bootstrap JS) que típicamente gestiona las interacciones de `displayHomeTab` y `displayHomeTabContent`.

### 4.5 Hojas de Estilo CSS (`views/css/`)

Este módulo **no** incluye ningún archivo CSS personalizado. Está diseñado para heredar el estilo del tema activo de PrestaShop para las listas de productos, asegurando una integración perfecta. Los desarrolladores deben consultar el CSS de su tema para estilizar las cuadrículas y pestañas de productos.

### 4.6 Estructura de Plantillas Smarty (`views/templates/`)

El módulo utiliza dos plantillas Smarty principales, ambas ubicadas en el directorio `views/templates/hook/`, para renderizar la pestaña y su contenido.

-   **`blockspecialstab/views/templates/hook/blockspecialstab.tpl`**

    -   **Propósito:** Esta plantilla es responsable de renderizar el *encabezado* real de la pestaña "Ofertas" que aparece junto a otras pestañas (por ejemplo, "Novedades").
    -   **Hook:** Principalmente renderizado a través de `displayHomeTab`.
    -   **Salida:** Típicamente genera un elemento `<li>` que contiene una etiqueta `<a>` con un enlace al contenido de la pestaña (por ejemplo, `#blockspecialstab`).
    -   **Elementos clave para desarrolladores:**
        -   `id="home-page-tabs"`: El contenedor para todas las pestañas de la página de inicio (generalmente en el tema).
        -   `id="blockspecialstab"`: El ID de la propia pestaña, utilizado para enlazar a su contenido.
        -   `{l s='Specials' mod='blockspecialstab'}`: El texto traducible para el título de la pestaña.
-   **`blockspecialstab/views/templates/hook/blockspecialstabcontents.tpl`**

    -   **Propósito:** Esta plantilla renderiza el *contenido* que aparece cuando se hace clic en la pestaña "Ofertas". Contiene la lista real de productos en oferta.
    -   **Hook:** Principalmente renderizado a través de `displayHomeTabContent`.
    -   **Salida:** Típicamente genera un elemento `<div>` que contiene un bucle que itera a través de la variable `$products` (pasada desde el módulo) y muestra cada producto utilizando un parcial común de lista de productos del tema (por ejemplo, `product-list.tpl` o un fragmento similar).
    -   **Elementos clave para desarrolladores:**
        -   `id="blockspecialstab"`: El ID para el bloque de contenido, que coincide con el encabezado de la pestaña.
        -   `{$products}`: Un array de objetos `Product` (o arrays asociativos que representan productos) pasados desde el módulo, que contienen detalles como ID, nombre, precio, imagen, etc.
        -   `{include file='catalog/_partials/miniatures/product.tpl' product=$product}` (ejemplo para PS 1.7/8): El módulo típicamente utiliza un parcial de tema estándar para renderizar cada producto, asegurando un estilo consistente. Los desarrolladores deben verificar el archivo `_partials/miniatures/product.tpl` o `product-list.tpl` de su tema para ver cómo se renderizan los productos individuales.

### 4.7 Esquema de Base de Datos y Mapa de Hooks

-   **Tablas de Base de Datos**:

    -   Este módulo no crea ninguna tabla SQL personalizada.
    -   Almacena sus ajustes de configuración en la tabla `ps_configuration` utilizando claves como `BLOCKSTAB_NB_CACHES` (legado), `BLOCKSTABS_NB_CACHES` (actual) y `BLOCKSTABS_RAND`.
-   **Tabla de Hooks Registrados**:

| Nombre del Hook | Momento de Ejecución | Propósito Técnico |
| --- | --- | --- |
| `displayHomeTab` | Se renderiza en el área de navegación de la pestaña de la página de inicio. | Inyecta el encabezado de la pestaña "Ofertas" (`blockspecialstab.tpl`) en la lista principal de pestañas de la página de inicio. |
| `displayHomeTabContent` | Se renderiza en el área de contenido de la página de inicio, correspondiente a la pestaña. | Inyecta la lista de productos en oferta (`blockspecialstabcontents.tpl`) cuando la pestaña "Ofertas" está activa. |
| `addproduct` | Después de añadir un producto. | Borra la caché interna del módulo para asegurar que los nuevos productos se consideren para las ofertas. |
| `updateproduct` | Después de actualizar un producto. | Borra la caché interna del módulo para reflejar los cambios en los precios o el estado de los productos. |
| `deleteproduct` | Después de eliminar un producto. | Borra la caché interna del módulo para eliminar los productos eliminados de las ofertas. |
| `displayAddProduct` | (Hook legado, a menudo utilizado para formularios de administración) | Borra la caché interna del módulo. |
| `displayUpdateProduct` | (Hook legado, a menudo utilizado para formularios de administración) | Borra la caché interna del módulo. |
| `displayDeleteProduct` | (Hook legado, a menudo utilizado para formularios de administración) | Borra la caché interna del módulo. |

Los hooks `addproduct`, `updateproduct`, `deleteproduct`, `displayAddProduct`, `displayUpdateProduct` y `displayDeleteProduct` se utilizan principalmente para activar una limpieza de caché dentro del módulo. Esto asegura que la lista de productos especiales mostrados en la página de inicio esté siempre actualizada cuando la información del producto (especialmente precios o estado) cambia.

## 5. Soporte Oficial y Actualizaciones

Para las últimas actualizaciones, correcciones de errores y soporte oficial para el módulo "Pestaña de Ofertas en la Página de Inicio", consulta tu cuenta de cliente en MyPresta.eu. Nuestro equipo de soporte está disponible para ayudarte con cualquier problema técnico o pregunta relacionada con la funcionalidad del módulo.
