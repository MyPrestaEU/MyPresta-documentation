---
title: "CMS en la página de inicio - Manual de Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop 'CMS en la página de inicio' de MyPresta.eu."
sidebar:
  label: "CMS en la página de inicio - Manual de Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo CMS on homepage en MyPresta.eu](https://mypresta.eu/modules/front-office-features/cms-on-homepage.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/front-office/cms-on-homepage/)
>
> ---


# CMS en la página de inicio

## 1. Requisitos y compatibilidad

- **Versiones de PrestaShop compatibles**: PrestaShop 9.x
- **Compatibilidad con PHP**: PHP 7.1 - 8.5 (Siempre extendiéndose a PHP 8.5)
- **Requisitos de alojamiento**: Las extensiones PHP estándar (cURL, JSON, OpenSSL) suelen ser necesarias para PrestaShop en sí, y este módulo no tiene requisitos especiales adicionales.

## 2. Recorrido completo por la configuración (Cada ajuste agrupado por pantalla)

### 2.1 Página de configuración del módulo (Back Office > Módulos > Configurar)

Después de la instalación, haga clic en "Configurar" junto al módulo "CMS en la página de inicio". Será llevado a su pantalla de configuración principal.

#### Seleccionar página CMS

Esta es la configuración principal del módulo. Le permite elegir cuál de sus páginas CMS existentes mostrará su contenido en la página de inicio.

- **Qué hace esta configuración:** Este menú desplegable enumera todas las páginas CMS que ha creado en su tienda PrestaShop (que se encuentran en **Parámetros de la tienda > Páginas**). Selecciona una de estas páginas.
- **Efecto de cambiar esta configuración:**
  - *Cuando se selecciona una página CMS:* El contenido de la página CMS elegida se obtendrá y se mostrará en la página de inicio de su tienda.
  - *Cuando no se selecciona ninguna página CMS (o si cambia de opinión):* El módulo no mostrará ningún contenido, o mostrará el contenido de la página recién seleccionada.
- **Valor recomendado:** Elija la página CMS cuyo contenido desea destacar prominentemente en su página de inicio. Esto podría ser su "Sobre nosotros", "Información de envío", "Política de privacidad" (si desea que sea muy visible) o una página personalizada con contenido promocional.
- **Escenario / ejemplo de comerciante:** Tiene una página CMS titulada "Nuestra historia" que detalla la historia y los valores de su marca. Al seleccionar "Nuestra historia" aquí, cada visitante de su página de inicio verá inmediatamente este contenido, lo que ayudará a construir la conexión y la confianza con la marca.

Después de hacer su selección, recuerde hacer clic en el botón **"Guardar"** para aplicar sus cambios.

### 2.2 Tabla de referencia rápida de configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e impacto |
| --- | --- | --- | --- |
| Página de configuración del módulo | Seleccionar página CMS | (Ninguna seleccionada inicialmente) | Elija qué contenido de la página CMS aparece en la página de inicio. |

## 3. Resolución de problemas del comerciante y preguntas frecuentes (FAQ)

**P: He seleccionado una página CMS, pero no aparece nada en mi página de inicio. ¿Qué pasa?**
R:

1. **Borrar caché:** Vaya a **Parámetros avanzados > Rendimiento** en su Back Office y haga clic en "Borrar caché" (o "Borrar caché de Smarty" en versiones anteriores). A veces, PrestaShop necesita una actualización de caché para mostrar contenido nuevo.
2. **Verificar el estado de la página CMS:** Asegúrese de que la página CMS seleccionada esté activa y visible en su tienda (vaya a **Parámetros de la tienda > Páginas** y verifique su estado).
3. **Compatibilidad del tema:** Si bien el módulo utiliza hooks estándar de PrestaShop, algunos temas altamente personalizados pueden anular estos hooks o tener requisitos de diseño específicos. Si borrar la caché no ayuda, póngase en contacto con el desarrollador de su tema o con el soporte de MyPresta.eu.

**P: El contenido CMS se muestra, pero no se ve bien (por ejemplo, fuentes, colores, diseño incorrectos).**
R: El módulo simplemente inyecta el contenido de su página CMS. El estilo (fuentes, colores, espaciado) suele estar controlado por el CSS de su tema de PrestaShop.

1. **Verificar el contenido de la página CMS:** Asegúrese de que no haya HTML personalizado o en línea que entre en conflicto dentro del propio contenido de la página CMS que pueda estar causando problemas.
2. **Personalización del tema:** Es posible que deba agregar CSS personalizado a su tema para integrar visualmente mejor el contenido CMS. Un desarrollador web puede ayudar con esto.

**P: ¿Puedo mostrar varias páginas CMS en la página de inicio?**
R: Este módulo específico está diseñado para mostrar *una* página CMS seleccionada. Si necesita mostrar varios bloques distintos de contenido CMS, deberá combinarlos en una sola página CMS o buscar un módulo de gestión de contenido más avanzado.

**P: ¿Cómo traduzco el contenido CMS a diferentes idiomas?**
R: El contenido de su página CMS se gestiona directamente dentro de la funcionalidad CMS principal de PrestaShop. Cuando edita una página CMS (**Parámetros de la tienda > Páginas**), puede seleccionar el idioma para editar su contenido. El módulo mostrará automáticamente el contenido en el idioma actualmente seleccionado por el cliente en su tienda.

## 4. Guía para desarrolladores y webmasters (Arquitectura técnica y mapa de código)

### 4.1 Visión general de la arquitectura

El módulo "CMS en la página de inicio" es un módulo ligero de PrestaShop diseñado principalmente para inyectar contenido de páginas CMS existentes en varios hooks de la página de inicio. Sigue una estructura de módulo estándar de PrestaShop, aprovechando la clase `Module` y sus métodos `install()` y `uninstall()` para la configuración y limpieza, y `getContent()` para la configuración del back-office. La visualización en el front-office se maneja completamente a través del registro de hooks y las plantillas Smarty. No introduce controladores, modelos o JavaScript complejos personalizados.

### 4.2 Controladores (`controllers/`)

- **Controladores de Front-Office**: Ninguno. Toda la renderización de contenido del front-office se maneja directamente a través de hooks registrados dentro del archivo principal del módulo.
- **Controladores de Administración de Back-Office**: Ninguno. La configuración del módulo se gestiona a través del método `getContent()` de la clase principal del módulo.

### 4.3 Clases y modelos principales (`classes/`)

- Ninguno. El módulo se basa en las clases principales `CMS` y `Configuration` de PrestaShop.

### 4.4 Activos de JavaScript (`views/js/`)

- Ninguno. El módulo no incluye ningún JavaScript personalizado.

### 4.5 Hojas de estilo CSS (`views/css/`)

- Ninguno. El módulo no incluye ningún CSS personalizado. El contenido CMS mostrado hereda el estilo del tema activo de PrestaShop.

### 4.6 Estructura de la plantilla Smarty (`views/templates/`)

- **`cmshomepage/views/templates/hook/cmshomepage.tpl`**

  - **Propósito:** Esta es la plantilla principal responsable de renderizar el contenido real de la página CMS seleccionada. Está diseñada para ser enganchada en `displayHome` o `displayHomeTabContent` para la salida directa de contenido.
  - **Variables:**
    - `{$cms_content}`: El contenido HTML de la página CMS seleccionada, obtenido y asignado por el módulo.
  - **Salida:** Renderiza el contenido HTML sin procesar de la página CMS.
- **`cmshomepage/views/templates/hook/tab.tpl`**

  - **Propósito:** Esta plantilla se utiliza cuando el módulo está enganchado en `displayHomeTab`. Genera el HTML para un encabezado de pestaña que, al hacer clic, revela el contenido CMS.
  - **Variables:**
    - `{$tab_name}`: El título de la pestaña, normalmente derivado del título de la página CMS.
    - `{$tab_id}`: Un ID único para la pestaña, utilizado para vincularla a su panel de contenido correspondiente.
  - **Salida:** Un elemento `<li>` que contiene una etiqueta `<a>`, adecuado para su inclusión en una estructura de navegación de pestañas.
- **`cmshomepage/views/templates/hook/tabContents.tpl`**

  - **Propósito:** Esta plantilla se utiliza cuando el módulo está enganchado en `displayHomeTabContent`. Genera el HTML para el panel de contenido asociado a una pestaña.
  - **Variables:**
    - `{$tab_id}`: El ID único que coincide con el ID de `tab.tpl`.
    - `{$cms_content}`: El contenido HTML de la página CMS seleccionada.
  - **Salida:** Un elemento `<div>` con el contenido de la pestaña, normalmente oculto por defecto y revelado mediante JavaScript cuando se hace clic en su pestaña correspondiente.

### 4.7 Esquema de la base de datos y mapa de hooks

- **Tablas de la base de datos**:

  - El módulo no crea ninguna tabla de base de datos personalizada.
  - Almacena su configuración en la tabla `ps_configuration` utilizando la clave `CMSHOMEPAGE_ID_CMS` para almacenar el ID de la página CMS seleccionada.
- **Tabla de Hooks registrados**:

| Nombre del Hook | Momento de ejecución | Propósito técnico |
| --- | --- | --- |
| `displayHomeTabContent` | Renderiza contenido dentro de una pestaña de la página de inicio. | Muestra `cmshomepage.tpl` o `tabContents.tpl` con el contenido CMS. |
| `displayHomeTab` | Renderiza un encabezado de pestaña en la página de inicio. | Muestra `tab.tpl` con el título de la página CMS como nombre de la pestaña. |
| `displayHome` | Renderiza contenido directamente en el área principal de la página de inicio. | Muestra `cmshomepage.tpl` con el contenido CMS. |

El método `install()` del módulo registra estos hooks. Los métodos `hookDisplayHome()`, `hookDisplayHomeTab()` y `hookDisplayHomeTabContent()` en `cmshomepage.php` son responsables de obtener el contenido de la página CMS seleccionada y renderizar la plantilla adecuada.

### 4.8 Claves de configuración

El módulo utiliza las siguientes claves de configuración en `ps_configuration`:

- `CMSHOMEPAGE_ID_CMS`: Almacena el `id_cms` de la página CMS seleccionada por el comerciante para ser mostrada en la página de inicio.

## 5. Soporte oficial y actualizaciones

Para actualizaciones oficiales, correcciones de errores y soporte técnico dedicado, consulte su cuenta de cliente en [MyPresta.eu](https://mypresta.eu/). Asegúrese de utilizar la última versión del módulo para un rendimiento óptimo y compatibilidad con su tienda PrestaShop.
"""
