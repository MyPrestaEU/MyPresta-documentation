---
title: "Productos Destacados - Manual de Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop Productos Destacados de MyPresta.eu."
sidebar:
  label: "Productos Destacados - Manual de Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Featured Products en MyPresta.eu](https://mypresta.eu/modules/front-office-features/featured-products.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/front-office/featured-products/)
>
> ---


# Productos Destacados

## 1. Requisitos y Compatibilidad

- **Versiones de PrestaShop Compatibles**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilidad con PHP**: PHP 7.1 - 8.5
- **Requisitos de Alojamiento**: Las extensiones estándar de PHP (cURL, JSON, OpenSSL) suelen ser suficientes. No se requieren configuraciones especiales del servidor.

## 2. Recorrido Completo por la Configuración (Cada Ajuste Agrupado por Pantalla)

### 2.1 Página de Configuración del Módulo (Back Office > Módulos > Configurar)

Para acceder a la configuración, navega a **Módulos > Gestor de Módulos**, busca "Productos Destacados" y haz clic en "Configurar".

Esta pantalla te permite definir qué productos se muestran y cómo aparecen en tu página de inicio.

#### Ajustes y Opciones:

1. **ID de Categoría de Origen**

   - **Qué hace este ajuste:** Este es el ajuste más crucial. Determina *qué* productos de la categoría se mostrarán como "destacados" en tu página de inicio. Debes introducir el ID numérico de la categoría que deseas mostrar.
   - **Efecto de cambiar este ajuste:**
     - *Cuando se establece un ID de Categoría válido (por ejemplo, `3` para "Ropa"):* El módulo buscará y mostrará los productos que pertenecen a la categoría con ese ID.
     - *Cuando se establece un ID inválido o inexistente:* No se mostrarán productos, o podría ocurrir un error si el ID está mal formado.
   - **Valor recomendado:** El ID de la categoría que deseas promocionar.
   - **Escenario / ejemplo de comerciante:** Si deseas destacar tu categoría "Novedades" (que tiene un ID de, digamos, `12`), introducirías `12` aquí. Para encontrar un ID de categoría, ve a **Catálogo > Categorías** en tu Back Office, haz clic en "Editar" en una categoría y mira la URL en tu navegador (por ejemplo, `id_category=12`).
2. **Número de Productos**

   - **Qué hace este ajuste:** Esto controla cuántos productos de tu "Categoría de Origen" seleccionada se mostrarán en la página de inicio.
   - **Efecto de cambiar este ajuste:**
     - *Cuando se establece en `5`:* Solo se mostrarán los primeros 5 productos de la categoría elegida.
     - *Cuando se establece en `10`:* Se mostrarán hasta 10 productos.
   - **Valor recomendado:** Un número razonable como `8` o `12` para evitar sobrecargar la página de inicio, pero suficiente para mostrar variedad. Considera el diseño de tu tema.
   - **Escenario / ejemplo de comerciante:** Si tu categoría "Novedades" tiene 50 productos, pero solo quieres mostrar los últimos 8 en la página de inicio, establecerías esto en `8`.
3. **Posición de Colocación**

   - **Qué hace este ajuste:** Esto determina *cómo* se muestran los productos destacados en tu página de inicio: directamente en el área de contenido principal (`displayHome`) o dentro de una pestaña (`displayHomeTabContent`).
   - **Efecto de cambiar este ajuste:**
     - *Cuando se establece en `Pestaña de la Página de Inicio`:* Los productos aparecerán bajo una nueva pestaña en tu página de inicio (por ejemplo, "Productos Destacados"). Esto requiere que tu tema admita pestañas en la página de inicio.
     - *Cuando se establece en `Página de Inicio`:* Los productos se mostrarán como una sección independiente directamente en tu página de inicio, sin estar ocultos detrás de una pestaña.
   - **Valor recomendado:**
     - Elige `Pestaña de la Página de Inicio` si tu tema utiliza pestañas para las listas de productos (como suelen hacer los temas predeterminados de PrestaShop) y quieres mantener tu página de inicio limpia.
     - Elige `Página de Inicio` si quieres la máxima visibilidad para estos productos y tu tema tiene amplio espacio en el área de contenido principal.
   - **Escenario / ejemplo de comerciante:** Si estás ejecutando una promoción especial y quieres que los productos sean inmediatamente visibles sin que los clientes necesiten hacer clic en una pestaña, seleccionarías `Página de Inicio`. Si tienes muchos tipos de productos destacados en tu página de inicio y quieres organizarlos de forma ordenada, `Pestaña de la Página de Inicio` es una mejor opción.

#### Tabla de Referencia Rápida de Configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| Configuración del Módulo | ID de Categoría de Origen | (Tu ID de Categoría) | Especifica qué productos de la categoría se muestran. |
| Configuración del Módulo | Número de Productos | 8-12 | Limita el número de productos mostrados de la categoría seleccionada. |
| Configuración del Módulo | Posición de Colocación | Pestaña de la Página de Inicio / Página de Inicio | Determina si los productos aparecen en una pestaña o directamente en la página de inicio. |

## 3. Resolución de Problemas para Comerciantes y Preguntas Frecuentes (FAQ)

**P: Mis productos destacados no aparecen en la página de inicio.**
R:

1. **Verifica el "ID de Categoría de Origen":** Asegúrate de haber introducido un ID de categoría correcto y existente. Ve a **Catálogo > Categorías**, edita la categoría deseada y busca su ID en la URL del navegador (por ejemplo, `id_category=X`).
2. **Verifica el "Número de Productos":** Asegúrate de que esté configurado con un valor mayor que 0.
3. **Verifica la "Posición de Colocación":** Si está configurado como "Pestaña de la Página de Inicio", asegúrate de que tu tema realmente admita y muestre pestañas en la página de inicio. Algunos temas personalizados podrían no hacerlo. Intenta cambiar a "Página de Inicio" para ver si aparecen como una sección directa.
4. **Borra la Caché:** Ve a **Parámetros Avanzados > Rendimiento** y haz clic en "Borrar caché". A veces, la caché de PrestaShop impide que los cambios aparezcan inmediatamente.

**P: Los productos se muestran, pero se ven desalineados o tienen un estilo incorrecto.**
R: Esto suele ser un problema relacionado con el tema.

1. **Compatibilidad del Tema:** Aunque el módulo es compatible con las versiones de PrestaShop, su salida visual podría entrar en conflicto con temas altamente personalizados.
2. **Conflicto de CSS:** El CSS de tu tema podría estar anulando o entrando en conflicto con el estilo predeterminado del módulo. Es posible que necesites un desarrollador web para inspeccionar el CSS y aplicar estilos personalizados a `featuredcategory.css` o al archivo CSS personalizado de tu tema.

**P: ¿Puedo destacar productos de varias categorías?**
R: No directamente con este módulo. El módulo "Productos Destacados" está diseñado para mostrar productos de *una* categoría seleccionada a la vez. Si necesitas destacar productos de varias categorías simultáneamente, tendrías que:
a) Crear una nueva categoría "Maestra Destacada" y añadir productos de varias categorías a ella.
b) Instalar varias instancias de este módulo (si tu tema lo permite) o usar un módulo diferente diseñado para mostrar varias categorías.

**P: ¿Cómo traduzco el título de la pestaña "Productos Destacados"?**
R: Si estás utilizando la colocación "Pestaña de la Página de Inicio", el título de la pestaña suele ser generado por el módulo.

1. Ve a **Internacional > Traducciones**.
2. Selecciona "Traducciones de módulos instalados", tu tema y tu idioma.
3. Busca el módulo "Productos Destacados". Deberías encontrar la cadena de texto para el título de la pestaña allí y podrás traducirla.

## 4. Guía para Desarrolladores y Webmasters (Arquitectura Técnica y Mapa de Código)

Esta sección es estrictamente para desarrolladores, webmasters de tiendas y agencias técnicas que mantienen o extienden la tienda.

### 4.1 Resumen de la Arquitectura

El módulo `Featured Products` es un módulo de PrestaShop sencillo diseñado principalmente para mostrar una lista de productos de una categoría específica en la página de inicio. Aprovecha el sistema de hooks de PrestaShop (`displayHome`, `displayHomeTab`, `displayHomeTabContent`) para inyectar su contenido. La lógica del módulo está contenida en su archivo PHP principal, `featuredcategory.php`, que maneja la configuración, instalación y renderizado del contenido. No introduce controladores personalizados, modelos o JavaScript complejo, lo que lo convierte en una solución ligera y fácilmente mantenible.

### 4.2 Controladores (`controllers/`)

- **Controladores de Front-Office**: Ninguno. Todo el renderizado de contenido de front-office se maneja directamente a través de hooks en el archivo `featuredcategory.php` principal y las plantillas Smarty asociadas.
- **Controladores de Administración de Back-Office**: Ninguno. La configuración del módulo se gestiona a través del método estándar `getContent()` en el archivo principal del módulo.

### 4.3 Clases y Modelos Principales (`classes/`)

- No hay clases personalizadas ni definiciones de `ObjectModel` presentes en este módulo. Toda la recuperación de datos (productos, categorías) se realiza utilizando las clases principales de PrestaShop `Product` y `Category`.

### 4.4 Activos JavaScript (`views/js/`)

- No se incluyen archivos JavaScript personalizados con este módulo.

### 4.5 Hojas de Estilo CSS (`views/css/`)

- `featuredcategory/css/featuredcategory.css`
  - **Alcance:** Estilo de front-office para el cliente.
  - **Componentes e contenedores principales de la interfaz de usuario que estiliza:** Esta hoja de estilo proporciona un estilo básico para la lista de productos generada por el módulo, asegurando que se vea presentable dentro del contexto de la página de inicio. Probablemente apunta a contenedores genéricos de listas de productos y elementos de productos individuales.
  - **Selectores de clase CSS clave que los desarrolladores pueden anular en su tema:** Los desarrolladores pueden inspeccionar la salida HTML del módulo para identificar clases específicas (por ejemplo, `.featuredcategory-products`, `.product-item`, `.product-name`) y anularlas en el archivo CSS personalizado de su tema para que coincidan con el diseño general de la tienda.

### 4.6 Estructura de Plantillas Smarty (`views/templates/`)

El módulo utiliza plantillas Smarty para renderizar su contenido, principalmente para los hooks de la página de inicio.

- **Plantillas de hook (`views/templates/hook/`)**:
  - `featuredcategory/views/templates/hook/featuredcategory17-tabContents.tpl`
    - **Hook:** `displayHomeTabContent`
    - **Propósito:** Esta plantilla es responsable de renderizar la lista real de productos destacados cuando la "Posición de Colocación" se establece en "Pestaña de la Página de Inicio". Típicamente contiene el bucle para iterar a través de los productos y mostrar sus detalles (imagen, nombre, precio, botón de añadir al carrito).
  - `featuredcategory/views/templates/hook/featuredcategory17.tpl`
    - **Hook:** `displayHome`
    - **Propósito:** Esta plantilla renderiza la lista de productos destacados cuando la "Posición de Colocación" se establece en "Página de Inicio" (es decir, no en una pestaña). Producirá la misma estructura de lista de productos que `featuredcategory17-tabContents.tpl` pero directamente en el hook `displayHome` principal.
  - `featuredcategory/views/templates/hook/tab.tpl`
    - **Hook:** `displayHomeTab`
    - **Propósito:** Esta plantilla renderiza el título real de la pestaña (por ejemplo, "Productos Destacados") que aparece en la página de inicio cuando la "Posición de Colocación" se establece en "Pestaña de la Página de Inicio". Proporciona el elemento clicable que revela el contenido de `featuredcategory17-tabContents.tpl`.
- **Plantillas de administración (`views/templates/admin/`)**: Ninguna.
- **Plantillas de front-office (`views/templates/front/`)**: Ninguna.

### 4.7 Esquema de Base de Datos y Mapa de Hooks

- **Tablas de Base de Datos**: Este módulo no crea ninguna tabla de base de datos personalizada. Almacena sus ajustes de configuración en la tabla `ps_configuration` de PrestaShop.

  - Entradas de `ps_configuration`:
    - `CFEATURED_NBR`: Almacena el ajuste "Número de Productos".
    - `CFEATURED_ID`: Almacena el ajuste "ID de Categoría de Origen".
    - `CFEATURED_WHERE`: Almacena el ajuste "Posición de Colocación" (por ejemplo, 'tab' o 'home').
    - `mypresta_updates`: Utilizado para las comprobaciones de actualización del módulo por MyPresta.eu.
- **Tabla de Hooks Registrados**:

| Nombre del Hook | Momento de Ejecución | Propósito Técnico |
| --- | --- | --- |
| `displayHomeTab` | Renderiza contenido para una nueva pestaña en la página de inicio. | Genera el HTML para el título de la pestaña "Productos Destacados". |
| `displayHomeTabContent` | Renderiza contenido para la pestaña seleccionada en la página de inicio. | Genera el HTML para la lista de productos destacados cuando la pestaña está activa. |
| `displayHome` | Renderiza contenido directamente en el área principal de la página de inicio. | Genera el HTML para la lista de productos destacados cuando no se utilizan pestañas. |
| `displayHeader` | Se ejecuta en la sección `<head>` de cada página. | Se utiliza para incluir la hoja de estilo CSS del módulo (`featuredcategory.css`) para la visualización en el front-office. |
| `actionProductDelete` | Se activa después de que se elimina un producto. | Potencialmente utilizado para borrar la caché o reevaluar los productos destacados si el producto eliminado estaba en la categoría destacada. |
| `actionProductUpdate` | Se activa después de que se actualiza un producto. | Potencialmente utilizado para borrar la caché o reevaluar los productos destacados si el producto actualizado está en la categoría destacada. |
| `actionProductAdd` | Se activa después de que se añade un nuevo producto. | Potencialmente utilizado para borrar la caché o reevaluar los productos destacados si el nuevo producto está en la categoría destacada. |
| `actionCategoryUpdate` | Se activa después de que se actualiza una categoría. | Potencialmente utilizado para borrar la caché o reevaluar los productos destacados si la propia categoría destacada se actualiza. |

## 5. Soporte Oficial y Actualizaciones

Para las últimas actualizaciones del módulo, correcciones de errores y soporte oficial, consulta tu cuenta de cliente en [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nuestro equipo de soporte está disponible para ayudarte con cualquier problema o pregunta relacionada con el módulo "Productos Destacados".
