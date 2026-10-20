---
title: "Pestañas de la página de inicio - Manual del comerciante y guía de configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop 'Pestañas de la página de inicio' de MyPresta.eu."
sidebar:
  label: "Pestañas de la página de inicio - Manual del comerciante y guía de configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Homepage tabs en MyPresta.eu](https://mypresta.eu/modules/front-office-features/homepage-tabs.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/front-office/homepage-tabs/)
>
> ---


# Pestañas de la página de inicio

## 1. Requisitos y compatibilidad

- **Versiones de PrestaShop compatibles**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilidad con PHP**: PHP 7.1 - 8.5
- **Requisitos de alojamiento**: Las extensiones PHP estándar (cURL, JSON, OpenSSL) suelen ser suficientes. No se requieren configuraciones de servidor inusuales.

## 2. Recorrido completo por la configuración (Cada ajuste agrupado por pantalla)

### 2.1 Página de configuración del módulo (Back Office > Módulos > Configurar)

Después de la instalación, haga clic en "Configurar" junto al módulo "Pestañas de la página de inicio" en el Gestor de módulos. Esto le llevará a la pantalla de configuración principal.

La página de configuración del módulo es sencilla, centrándose principalmente en asegurar que el módulo pueda recibir actualizaciones.

- **Qué hace este ajuste:** Esta sección gestiona la capacidad del módulo para buscar y recibir actualizaciones de MyPresta.eu. Mantener sus módulos actualizados es crucial para la seguridad, el rendimiento y la compatibilidad con las nuevas versiones de PrestaShop.
- **Efecto de cambiar este ajuste:**
  - *Cuando está habilitado (predeterminado):* El módulo buscará periódicamente nuevas versiones en MyPresta.eu. Si hay una actualización disponible, se le notificará en su back office de PrestaShop, lo que le permitirá descargar e instalar fácilmente la última versión. Esto asegura que su módulo siga siendo compatible y se beneficie de las últimas características y correcciones de errores.
  - *Cuando está deshabilitado:* El módulo no buscará actualizaciones. No se le notificará de nuevas versiones, perdiéndose potencialmente mejoras importantes, parches de seguridad o correcciones de compatibilidad. Tendría que buscar actualizaciones manualmente en MyPresta.eu.
- **Valor recomendado:** **SÍ (Habilitado)**. Se recomienda encarecidamente mantener este ajuste habilitado para asegurar que su módulo esté siempre actualizado y seguro.
- **Escenario / ejemplo del comerciante:** Imagine que PrestaShop lanza una nueva versión menor (por ejemplo, 8.1.5). Podría lanzarse una actualización del módulo "Pestañas de la página de inicio" para asegurar la compatibilidad total. Con las actualizaciones habilitadas, se le notificaría y podría actualizar fácilmente, evitando cualquier problema potencial. Si está deshabilitado, sus pestañas podrían dejar de funcionar correctamente después de la actualización de PrestaShop, y no sabría por qué hasta que buscara manualmente las actualizaciones del módulo.

### 2.2 Tabla de referencia rápida de configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| Página de configuración del módulo | Comprobaciones de actualización (mypresta\_updates, update\_, updatev\_) | SÍ (Habilitado) | Habilita las comprobaciones automáticas de actualizaciones del módulo desde MyPresta.eu, asegurando compatibilidad, seguridad y acceso a nuevas características. |

## 3. Solución de problemas del comerciante y preguntas frecuentes (FAQ)

**P: Mis pestañas de la página de inicio no aparecen después de la instalación.**
R:

1. **Verificar la posición del módulo:** Vaya a **Diseño > Posiciones** en su back office de PrestaShop. Busque `displayHome`. Asegúrese de que el módulo "Pestañas de la página de inicio" esté enganchado a `displayHome`. Si no está allí, use el botón "Trasplantar un módulo" para agregarlo.
2. **Borrar caché:** Siempre borre la caché de PrestaShop después de instalar o configurar módulos. Vaya a **Parámetros avanzados > Rendimiento** y haga clic en "Borrar caché" en la esquina superior derecha.
3. **Verificar conflictos de tema:** Algunos temas personalizados pueden anular el hook `displayHome` o tener un estilo específico que oculte el módulo. Cambie temporalmente al tema predeterminado de PrestaShop (Classic) para ver si aparecen las pestañas. Si lo hacen, su tema requiere CSS personalizado o ajustes de plantilla.

**P: Los productos en las pestañas no se ven bien (por ejemplo, tamaño incorrecto, desalineados).**
R: Esto suele ser un problema de estilo relacionado con el tema de su tienda. El módulo en sí proporciona los datos del producto, pero su tema dicta cómo se muestran las listas de productos.

1. **Borrar caché:** De nuevo, borre la caché de PrestaShop.
2. **CSS del tema:** El CSS de su tema podría estar en conflicto con el estilo predeterminado del módulo. Un desarrollador web puede inspeccionar los elementos utilizando las herramientas de desarrollo del navegador y aplicar anulaciones de CSS personalizadas en el archivo `custom.css` de su tema para corregir la apariencia.

**P: ¿Puedo cambiar el orden de las pestañas o qué productos aparecen en ellas?**
R: Este módulo restaura la *funcionalidad* de las pestañas de la página de inicio (Populares, Nuevos, Más vendidos, En oferta). Los tipos de productos específicos que se muestran (por ejemplo, "Productos populares") están determinados por la lógica central de PrestaShop para esas categorías. Este módulo no ofrece opciones para seleccionar manualmente productos para cada pestaña o reordenar las pestañas a través de su configuración. Para una personalización avanzada como selecciones de productos personalizadas u ordenación de pestañas, normalmente necesitaría un módulo más avanzado o un desarrollo personalizado.

**P: El módulo está instalado, pero no veo ninguna opción de configuración más allá de los ajustes de actualización.**
R: Este módulo está diseñado para volver a habilitar la característica principal de las pestañas de la página de inicio de PrestaShop que se eliminó. Su función principal es hacer que las pestañas vuelvan a aparecer, utilizando la lógica predeterminada de PrestaShop para productos "Populares", "Nuevos", "Más vendidos" y "En oferta". Por lo tanto, no tiene amplias opciones de configuración para la gestión de contenido dentro de las propias pestañas, ya que esa lógica es manejada por el núcleo de PrestaShop.

## 4. Guía para desarrolladores y webmasters (Arquitectura técnica y mapa de código)

### 4.1 Visión general de la arquitectura

El módulo "Pestañas de la página de inicio" (`homepagetabs`) es un módulo ligero de PrestaShop diseñado para volver a habilitar una característica central del front-office que fue eliminada en versiones más recientes de PrestaShop. Opera principalmente enganchándose a `displayHome` para renderizar las pestañas de productos y a `displayHeader` para incluir los activos necesarios. Aprovecha los mecanismos de obtención de productos existentes de PrestaShop para productos "Populares", "Nuevos", "Más vendidos" y "En oferta", actuando eficazmente como un puente para restaurar el componente visual. El módulo sigue un patrón MVC estándar de PrestaShop, aunque su lógica principal reside dentro de la clase principal del módulo (`homepagetabs.php`) para la renderización.

### 4.2 Controladores (`controllers/`)

- **Controladores de Front-Office**: Ninguno. La lógica de visualización del front-office del módulo se maneja completamente mediante el archivo del módulo `homepagetabs.php` a través de hooks.
- **Controladores de administración de Back-Office**: Ninguno. Toda la configuración se maneja directamente dentro del método `getContent()` de la clase principal del módulo.

### 4.3 Clases y modelos principales (`classes/`)

- Ninguno. El módulo no define ninguna clase personalizada ni instancias de `ObjectModel`. Se basa en las clases principales de PrestaShop para la recuperación de datos de productos.

### 4.4 Activos JavaScript (`views/js/`)

- `homepagetabs/views/js/homepagetabs.js`
  - **Alcance**: Front-office.
  - **Responsabilidad**: Este script es responsable del comportamiento interactivo de las pestañas de la página de inicio. Probablemente maneja:
    - La vinculación de los oyentes de eventos de clic a los encabezados de las pestañas.
    - El cambio de visibilidad de los bloques de contenido de productos según la pestaña activa.
    - La adición/eliminación de clases CSS activas a los encabezados y contenido de las pestañas.
    - Potencialmente el manejo de solicitudes AJAX si el contenido del producto se carga dinámicamente (aunque para este módulo, es más probable que sea un simple mecanismo de mostrar/ocultar para contenido pre-renderizado).
    - Asegurar que las pestañas funcionen correctamente en diferentes tamaños de pantalla y dispositivos.

### 4.5 Hojas de estilo CSS (`views/css/`)

- `homepagetabs/views/css/homepagetabs.css`
  - **Alcance**: Estilo del cliente del front-office.
  - **Responsabilidad**: Esta hoja de estilo proporciona la presentación visual predeterminada para las pestañas de la página de inicio y su contenido. Define estilos para:
    - El contenedor de la pestaña en sí.
    - Los encabezados de las pestañas individuales (por ejemplo, `ul.home-tabs li a`).
    - El estado de la pestaña activa (por ejemplo, `ul.home-tabs li.active a`).
    - El contenedor de la cuadrícula de productos para cada pestaña (por ejemplo, `.tab-content`).
    - Ajustes responsivos básicos para diferentes tamaños de pantalla.
  - **Selectores de clase CSS clave que los desarrolladores pueden anular**: Los desarrolladores pueden apuntar a clases como `.home-tabs`, `.home-tabs li`, `.home-tabs li.active`, `.tab-content` y los elementos de la cuadrícula de productos dentro de `.tab-content` para integrar la apariencia del módulo sin problemas con su tema personalizado.

### 4.6 Estructura de la plantilla Smarty (`views/templates/`)

- **Plantillas de hook (`views/templates/hook/`)**:
  - `homepagetabs/views/templates/hook/homepagetabs.tpl`
    - **Hook**: `displayHome`
    - **Propósito**: Esta es la plantilla principal del front-office responsable de renderizar todo el bloque de pestañas de la página de inicio. Contendrá la estructura HTML para los encabezados de las pestañas (por ejemplo, `<ul>` para los títulos de las pestañas) y las áreas de contenido correspondientes (por ejemplo, `<div>` para las listas de productos). Itera a través de los datos del producto que le pasa el método `hookDisplayHome()` del módulo, mostrando productos "Populares", "Nuevos", "Más vendidos" y "En oferta" en sus respectivas áreas de contenido de pestañas. Esta plantilla es donde se renderizan las tarjetas de productos (imágenes, nombres, precios, botones de añadir al carrito) para cada tipo de producto.
- **Plantillas de administración (`views/templates/admin/`)**:
  - `homepagetabs/views/templates/admin/homepagetabs.tpl`
    - **Propósito**: Esta plantilla renderiza el formulario de configuración del módulo en el back office de PrestaShop. Muestra los ajustes relacionados con las comprobaciones de actualización (`mypresta_updates`, `update_`, `updatev_`) y cualquier otro elemento de configuración estándar del módulo.

### 4.7 Esquema de la base de datos y mapa de Hooks

- **Tablas de la base de datos**: El módulo no crea ninguna tabla de base de datos personalizada. Almacena sus ajustes de configuración (por ejemplo, `mypresta_updates`) en la tabla estándar `ps_configuration`.
- **Tabla de Hooks registrados**:

| Nombre del Hook | Momento de ejecución | Propósito técnico |
| --- | --- | --- |
| `displayHome` | Renderiza contenido en la página de inicio de la tienda. | Este hook se utiliza para generar la estructura HTML completa de las pestañas de la página de inicio, incluyendo los encabezados de las pestañas y las listas de productos. |
| `displayHeader` | Se ejecuta en la sección `<head>` de cada página del front-office. | Este hook se utiliza para incluir los archivos CSS (`homepagetabs.css`) y JavaScript (`homepagetabs.js`) del módulo, asegurando un estilo adecuado y la funcionalidad interactiva de las pestañas. |

## 5. Soporte oficial y actualizaciones

Para obtener actualizaciones oficiales, soporte técnico y asistencia adicional con el módulo "Pestañas de la página de inicio", visite su cuenta de cliente en [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nuestro equipo de soporte está disponible para ayudarle con cualquier pregunta o problema que pueda encontrar.
"""
