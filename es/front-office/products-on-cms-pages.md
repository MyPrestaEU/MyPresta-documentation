---
title: "Productos en páginas CMS - Manual de Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop 'Productos en páginas CMS' de MyPresta.eu."
sidebar:
  label: "Productos en páginas CMS - Manual de Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Products on CMS pages en MyPresta.eu](https://mypresta.eu/modules/front-office-features/products-on-cms-pages.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/front-office/products-on-cms-pages/)
>
> ---


# Productos en páginas CMS

## 1. Requisitos y Compatibilidad

- **Versiones de PrestaShop Compatibles**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilidad con PHP**: PHP 7.1 - 8.5
- **Requisitos de Alojamiento**: Las extensiones PHP estándar (cURL, JSON, OpenSSL) son típicamente requeridas por PrestaShop y son suficientes para este módulo.

## 2. Recorrido Completo por la Configuración (Cada Ajuste Agrupado por Pantalla)

### 2.1 Página de Configuración del Módulo (Back Office > Módulos > Configurar)

Después de la instalación, haz clic en "Configurar" junto al módulo "Productos en páginas CMS" en el Gestor de módulos. Verás la pantalla de configuración principal.

#### **Ocultar productos y códigos cortos**

- **Qué hace este ajuste:** Este ajuste controla si el módulo procesa y muestra los productos de los códigos cortos que has colocado en tus páginas CMS. También afecta si los propios códigos cortos son visibles para los clientes si el módulo no los está procesando.
- **Efecto de cambiar este ajuste:**
  - *Cuando está habilitado (SÍ):* El módulo *no* procesará los códigos cortos. En lugar de mostrar listas de productos, los códigos cortos (por ejemplo, `[products ids="1,2,3"]`) se ocultarán de la vista del cliente en el front office. Esto es útil si deseas deshabilitar temporalmente la visualización de productos sin eliminar los códigos cortos de tu contenido CMS.
  - *Cuando está deshabilitado (NO):* El módulo buscará y procesará activamente los códigos cortos en tus páginas CMS. Los reemplazará con las listas de productos correspondientes, haciendo que tus productos sean visibles para los clientes.
- **Valor recomendado:** **NO** (a menos que quieras ocultar específicamente las listas de productos y los códigos cortos).
- **Escenario / ejemplo de comerciante:**
  - Has configurado varias páginas CMS con códigos cortos de productos para una promoción estacional. Cuando la promoción termina, en lugar de editar manualmente cada página CMS para eliminar los códigos cortos, simplemente puedes habilitar "Ocultar productos y códigos cortos" para ocultar instantáneamente todos los listados de productos de esas páginas. Cuando comience la siguiente promoción, lo deshabilitas de nuevo.

### 2.2 Cómo Usar Códigos Cortos en Tus Páginas CMS

Este módulo no tiene pantallas de administración dedicadas más allá de la configuración principal. Su funcionalidad principal se controla mediante "códigos cortos" que insertas directamente en el contenido de tu página CMS.

**Para añadir productos a una página CMS:**

1. Navega a **Parámetros de la tienda > CMS** en tu Back Office de PrestaShop.
2. Edita una página CMS existente o crea una nueva.
3. En el editor de contenido principal (normalmente un editor de texto enriquecido como TinyMCE), puedes escribir o pegar los códigos cortos.

**Códigos Cortos Disponibles:**

- **Mostrar productos específicos por ID:**

  - `[products ids="1,2,3,4"]`
  - **Propósito:** Este código corto te permite mostrar una lista de productos específicos por sus números de ID únicos. Puedes encontrar los ID de producto en tu Back Office en **Catálogo > Productos**.
  - **Ejemplo:** Si quieres mostrar el Producto A (ID 1), el Producto B (ID 2) y el Producto C (ID 3), usarías `[products ids="1,2,3"]`.
- **Mostrar productos de una categoría específica:**

  - `[products category="5"]`
  - **Propósito:** Este código corto muestra todos los productos que pertenecen a una categoría específica. Puedes encontrar los ID de categoría en tu Back Office en **Catálogo > Categorías** editando una categoría y buscando en la URL o en la columna "ID" de la lista de categorías.
  - **Ejemplo:** Para mostrar todos los productos de tu categoría "Electrónica" (suponiendo que su ID sea 5), usarías `[products category="5"]`.
- **Mostrar productos de un fabricante/marca específico:**

  - `[products manufacturer="1"]`
  - **Propósito:** Este código corto muestra todos los productos asociados con un fabricante o marca en particular. Los ID de fabricante se pueden encontrar en **Catálogo > Marcas y Proveedores > Marcas**.
  - **Ejemplo:** Para mostrar todos los productos de "Apple" (suponiendo que su ID sea 1), usarías `[products manufacturer="1"]`.
- **Mostrar productos nuevos:**

  - `[products new="5"]`
  - **Propósito:** Este código corto muestra los productos añadidos más recientemente a tu tienda. El número "5" indica cuántos productos nuevos quieres mostrar.
  - **Ejemplo:** Para mostrar los 5 productos más nuevos, usa `[products new="5"]`.
- **Mostrar productos más vendidos:**

  - `[products bestseller="5"]`
  - **Propósito:** Este código corto muestra tus productos más vendidos. El número "5" indica cuántos productos más vendidos quieres mostrar.
  - **Ejemplo:** Para mostrar tus 5 productos más vendidos, usa `[products bestseller="5"]`.
- **Mostrar productos en oferta:**

  - `[products sale="5"]`
  - **Propósito:** Este código corto muestra productos que están actualmente en oferta. El número "5" indica cuántos productos en oferta quieres mostrar.
  - **Ejemplo:** Para mostrar 5 productos que están actualmente con descuento, usa `[products sale="5"]`.
- **Mostrar productos destacados (de la página de inicio):**

  - `[products featured="5"]`
  - **Propósito:** Este código corto muestra productos que están marcados como "destacados" en tu página de inicio (normalmente controlados por el módulo "Productos destacados"). El número "5" indica cuántos productos destacados quieres mostrar.
  - **Ejemplo:** Para mostrar 5 de tus productos destacados, usa `[products featured="5"]`.

**Notas Importantes:**

- Puedes combinar códigos cortos en la misma página, pero cada código corto generará su propia lista de productos.
- Asegúrate de que no haya espacios adicionales o errores tipográficos dentro de los corchetes `[]` del código corto.
- Después de añadir los códigos cortos, guarda tu página CMS. Los productos aparecerán en el front office automáticamente (a menos que tengas "Ocultar productos y códigos cortos" habilitado en la configuración del módulo).

### 2.3 Tabla de Referencia Rápida de Configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| Configuración del Módulo | Ocultar productos y códigos cortos | NO | Controla si las listas de productos de los códigos cortos se muestran (NO) u ocultan (SÍ) en las páginas CMS. |
| Editor de Páginas CMS | `[products ids="1,2,3"]` | N/A | Muestra productos específicos por sus ID. |
| Editor de Páginas CMS | `[products category="5"]` | N/A | Muestra todos los productos de una categoría específica. |
| Editor de Páginas CMS | `[products manufacturer="1"]` | N/A | Muestra todos los productos de un fabricante específico. |
| Editor de Páginas CMS | `[products new="5"]` | N/A | Muestra los 5 productos más nuevos. |
| Editor de Páginas CMS | `[products bestseller="5"]` | N/A | Muestra los 5 productos más vendidos. |
| Editor de Páginas CMS | `[products sale="5"]` | N/A | Muestra los 5 productos actualmente en oferta. |
| Editor de Páginas CMS | `[products featured="5"]` | N/A | Muestra los 5 productos destacados de la página de inicio. |

## 3. Solución de Problemas para Comerciantes y Preguntas Frecuentes (FAQ)

**P: Mis productos no aparecen en la página CMS, pero los códigos cortos son visibles.**
R: Revisa la página de configuración del módulo (**Módulos > Gestor de módulos > Configurar** para "Productos en páginas CMS"). Asegúrate de que "Ocultar productos y códigos cortos" esté configurado en **NO**. Si está configurado en SÍ, el módulo ocultará los productos y los propios códigos cortos. Además, verifica la sintaxis de tu código corto para detectar errores tipográficos o comillas faltantes.

**P: Mis productos no aparecen, y tampoco los códigos cortos (solo espacio en blanco).**
R: Esto suele significar que el módulo está activo e intentando procesar los códigos cortos, pero está encontrando un problema.
1. **Borrar Caché de PrestaShop:** Ve a **Parámetros avanzados > Rendimiento** y haz clic en "Borrar caché" en la esquina superior derecha.
2. **Verificar ID de Producto/Categoría:** Asegúrate de que los ID que estás utilizando en `[products ids="..."]`, `[products category="..."]` o `[products manufacturer="..."]` sean correctos y correspondan a productos/categorías/fabricantes existentes y activos en tu tienda.
3. **Visibilidad del Producto:** Asegúrate de que los productos que intentas mostrar estén activos y visibles en tu tienda (no deshabilitados, agotados si la gestión de stock es estricta o configurados como "ocultos").

**P: Los productos aparecen, pero no se ven bien con el estilo de mi tema.**
R: El módulo utiliza un estilo básico, pero el CSS de tu tema podría anularlo o entrar en conflicto con él.
1. **Personalización del Tema:** La mayoría de los temas tienen opciones para CSS personalizado. Tú o tu webmaster pueden añadir reglas CSS personalizadas para apuntar a los listados de productos generados por este módulo.
2. **Contactar al Desarrollador del Tema:** Si no estás seguro, contacta al desarrollador de tu tema para obtener consejos sobre cómo estilizar mejor las cuadrículas de productos.
3. **Contactar al Soporte de MyPresta.eu:** Si sospechas un problema de estilo específico del módulo, comunícate con el soporte de MyPresta.eu.

**P: ¿Puedo usar varios códigos cortos en la misma página CMS?**
R: Sí, puedes usar tantos códigos cortos diferentes como quieras en una sola página CMS. Cada código corto generará su propia lista separada de productos.

**P: ¿Este módulo es compatible con tiendas multi-idioma?**
R: Sí, el módulo funciona con las capacidades multi-idioma de PrestaShop. Los nombres y descripciones de los productos mostrados estarán en el idioma seleccionado por el cliente, al igual que en las páginas de productos o categorías regulares. Los códigos cortos en sí (`[products ids="..."]`) permanecen iguales en todos los idiomas.

## 4. Guía para Desarrolladores y Webmasters (Arquitectura Técnica y Mapa de Código)

Esta sección es estrictamente para desarrolladores, webmasters de tiendas y agencias técnicas que mantienen o extienden la tienda.

### 4.1 Resumen de la Arquitectura

El módulo "Productos en páginas CMS" funciona principalmente anulando el `CmsController` principal para interceptar y procesar el contenido antes de que se renderice al usuario. Utiliza expresiones regulares para encontrar códigos cortos específicos dentro del contenido de la página CMS y los reemplaza con listas de productos generadas dinámicamente. Los datos del producto se obtienen utilizando los métodos `Product::getProducts` y `Product::getProductsProperties` de PrestaShop, y luego se renderizan a través de plantillas Smarty.

### 4.2 Controladores (`controllers/`)

Este módulo utiliza una anulación para extender la funcionalidad principal de PrestaShop.

- **Controladores del Front-Office**:

  - `cmsproducts/override/controllers/front/CmsController.php`
    - **Nombre de la clase y clase padre**: `CmsController` (anula `CmsControllerCore`)
    - **Responsabilidad**: Este es el núcleo de la funcionalidad del módulo. Anula el método `initContent()` del `CmsController` estándar. Dentro de `initContent()`, recupera el contenido de la página CMS, lo escanea en busca de los códigos cortos definidos (por ejemplo, `[products ids="..."]`), procesa estos códigos cortos obteniendo los datos de producto relevantes y luego reemplaza los códigos cortos con el HTML de producto renderizado antes de que se muestre el contenido de la página. También asegura que se cargue el CSS del módulo.
  - `cmsproducts/override/controllers/front/index.php`
    - **Nombre de la clase y clase padre**: N/A (archivo vacío)
    - **Responsabilidad**: Este es un archivo `index.php` vacío estándar colocado en subdirectorios para evitar la lista de directorios, una práctica de seguridad común. No tiene impacto funcional en la lógica del módulo.
- **Controladores de Administración del Back-Office**: Ninguno. La configuración del módulo se maneja directamente dentro del método `getContent()` de la clase principal del módulo.

### 4.3 Clases y Modelos Principales (`classes/`)

No hay clases personalizadas ni definiciones de `ObjectModel` presentes en este módulo. Aprovecha las clases principales existentes de PrestaShop como `Product`, `Category`, `Manufacturer`, `Context`, `Tools` y `Configuration`.

### 4.4 Activos JavaScript (`views/js/`)

No se incluyen archivos JavaScript personalizados en este módulo. Toda la funcionalidad se maneja en el lado del servidor a través de PHP.

### 4.5 Hojas de Estilo CSS (`views/css/`)

El módulo incluye dos archivos CSS para estilizar los listados de productos. Estos se cargan a través del hook `actionAdminControllerSetMedia` (para el contexto del back-office, aunque la anulación maneja la carga del front-office).

- `cmsproducts/cmsproducts.css`
  - **Alcance**: Estilo del cliente del front-office.
  - **Principales componentes de la interfaz de usuario y contenedores que estiliza**: Contiene el estilo general para la cuadrícula/lista de productos generada por los códigos cortos. Esto incluiría estilos para los contenedores de productos, imágenes, nombres, precios y, potencialmente, botones de "Añadir al carrito" para asegurar una apariencia consistente.
  - **Selectores de clase CSS clave que los desarrolladores pueden anular**: Probablemente apunta a clases como `.cmsproducts-product-list`, `.cmsproducts-product-item`, `.cmsproducts-product-image`, `.cmsproducts-product-name`, `.cmsproducts-product-price`.
- `cmsproducts/css.css`
  - **Alcance**: Estilo del cliente del front-office.
  - **Principales componentes de la interfaz de usuario y contenedores que estiliza**: Similar a `cmsproducts.css`, este archivo probablemente proporciona reglas de estilo adicionales o específicas para la visualización del producto, potencialmente para la capacidad de respuesta o ajustes de diseño específicos.
  - **Selectores de clase CSS clave que los desarrolladores pueden anular**: Similar a `cmsproducts.css`.

### 4.6 Estructura de Plantillas Smarty (`views/templates/`)

El módulo utiliza plantillas Smarty para renderizar las listas de productos.

- **Plantillas de hook (`views/templates/hook/`)**: Ninguna definida explícitamente como plantillas de hook. Las plantillas son renderizadas directamente por la anulación del `CmsController`.
- **Plantillas de administración (`views/templates/admin/`)**: Ninguna.
- **Plantillas del front-office (`views/templates/front/`)**:
  - `cmsproducts/html.tpl`
    - **Propósito**: Esta plantilla probablemente sirve como envoltorio o contenedor general para las listas de productos. Podría incluir una estructura HTML básica que rodea los elementos del producto.
  - `cmsproducts/products-carousel.tpl`
    - **Propósito**: Esta plantilla está diseñada para renderizar productos en formato de carrusel o deslizador. Contendría la estructura HTML necesaria y, potencialmente, la inicialización de JavaScript para un carrusel de productos. Esta plantilla probablemente se usa cuando un parámetro de código corto específico o una configuración del módulo (no expuesta en la configuración actual) implica una visualización de carrusel.
  - `cmsproducts/products.tpl`
    - **Propósito**: Esta es la plantilla principal para renderizar una cuadrícula o lista estándar de productos. Itera a través de los datos del producto pasados desde el controlador PHP y muestra los detalles individuales del producto (imagen, nombre, precio, botón de añadir al carrito, etc.). Esta es la plantilla más utilizada para los códigos cortos `[products ...]`.

### 4.7 Esquema de Base de Datos y Mapa de Hooks

- **Tablas de Base de Datos**: Este módulo no crea ninguna tabla de base de datos personalizada. Almacena sus configuraciones en la tabla estándar `ps_configuration`.
  - Entradas de `ps_configuration`:
    - `mypresta_updates`: Almacena información relacionada con las actualizaciones del módulo de MyPresta.eu.
    - `cmsproducts_hide`: Almacena el valor del ajuste "Ocultar productos y códigos cortos" (1 para habilitado/SÍ, 0 para deshabilitado/NO).
- **Tabla de Hooks Registrados**:

| Nombre del Hook | Momento de Ejecución | Propósito Técnico |
| --- | --- | --- |
| `actionAdminControllerSetMedia` | Se ejecuta cuando un Controlador de Administración establece sus activos de medios. | Aunque está listado, la carga principal de CSS para el front office es manejada por la anulación del `CmsController`. Este hook podría usarse para un posible estilo futuro del lado del administrador o si el módulo tuviera un controlador de administración. |

La funcionalidad principal de procesamiento de códigos cortos y renderizado de productos se logra a través de la anulación del `CmsController`, que manipula directamente el contenido antes de la visualización, en lugar de depender de un hook específico del front-office para la inyección de contenido.

## 5. Soporte Oficial y Actualizaciones

Para obtener actualizaciones oficiales, soporte técnico y acceder a las últimas versiones del módulo "Productos en páginas CMS", visita tu cuenta de cliente en [MyPresta.eu](https://mypresta.eu/). Nuestro equipo de soporte está disponible para ayudar a comerciantes y desarrolladores con cualquier pregunta o problema relacionado con el módulo.
