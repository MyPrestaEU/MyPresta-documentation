---
title: "Zoom de imágenes en la lista de productos del back office - Manual del Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop 'Zoom de imágenes en la lista de productos del back office' de MyPresta.eu."
sidebar:
  label: "Zoom de imágenes en la lista de productos del back office - Manual del Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Zoom images on product list in back office en MyPresta.eu](https://mypresta.eu/modules/administration-tools/zoom-images-on-product-list-in-back-office.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/back-office-tools/zoom-images-on-product-list-in-back-office/)
>
> ---


# Zoom de imágenes en la lista de productos del back office

## 1. Requisitos y compatibilidad

- **Versiones de PrestaShop compatibles**: PrestaShop 1.6.x, 1.7.x
- **Compatibilidad con PHP**: PHP 5.6 - 8.5
- **Requisitos de alojamiento**: Las extensiones PHP estándar (cURL, JSON, OpenSSL) suelen ser suficientes. No se necesitan configuraciones especiales del servidor.

## 2. Recorrido completo por la configuración (Cada ajuste agrupado por pantalla)

### 2.1 Página de configuración del módulo (Back Office > Módulos > Configurar)

Después de la instalación, haga clic en "Configurar" junto al nombre del módulo. Será llevado a su pantalla de configuración principal.

Este módulo tiene una configuración muy simple, que generalmente consiste en un solo interruptor para habilitar o deshabilitar su funcionalidad.

- **Habilitar Zoom en la Lista de Productos:**
  - **Qué hace este ajuste:** Este es el interruptor maestro del módulo. Controla si la función de zoom de imagen está activa o inactiva en la lista de productos de su Back Office.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está habilitado (SÍ):* Cuando navega a **Catálogo > Productos** en su Back Office, al pasar el ratón por encima de cualquier miniatura de imagen de producto en la lista, se mostrará una versión más grande y ampliada de esa imagen.
    - *Cuando está deshabilitado (NO):* La funcionalidad de zoom se desactivará. Al pasar el ratón por encima de las imágenes de los productos no tendrá ningún efecto especial, y verá las miniaturas pequeñas estándar.
  - **Valor recomendado:** SÍ
  - **Escenario / ejemplo de comerciante:** Si desea utilizar la práctica función de zoom para verificar rápidamente las imágenes de los productos, asegúrese de que esté configurado en "SÍ". Si encuentra que interfiere con otra personalización del Back Office o simplemente prefiere no usarlo, configúrelo en "NO".

### 2.2 Tabla de referencia rápida de configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| Configuración del Módulo | Habilitar Zoom en la Lista de Productos | SÍ | Activa o desactiva la función de zoom de imagen en la lista de productos del Back Office. |

## 3. Solución de problemas del comerciante y preguntas frecuentes (FAQ)

**P: He habilitado el módulo, pero el zoom no funciona en mi lista de productos. ¿Qué debo hacer?**
R:

1. **Borrar caché:** Vaya a **Parámetros avanzados > Rendimiento** en su Back Office y haga clic en "Borrar caché" (o "Borrar caché de Smarty" en versiones anteriores). A veces, la caché de PrestaShop puede impedir que se cargue el nuevo JavaScript.
2. **Comprobar la consola del navegador:** Abra las herramientas de desarrollador de su navegador (normalmente F12) y busque cualquier error en la pestaña "Consola". Esto podría indicar un conflicto con otro módulo o tema.
3. **Conflictos de módulos:** Deshabilite temporalmente otros módulos que modifiquen la lista de productos del Back Office (si los hay) para ver si hay un conflicto.
4. **Sobreescrituras de temas:** Si está utilizando un tema de Back Office muy personalizado, podría estar sobrescribiendo la estructura estándar de la lista de productos, impidiendo que el módulo inyecte su JavaScript. Póngase en contacto con el desarrollador de su tema o con el soporte de MyPresta.eu.

**P: La imagen ampliada aparece, pero se ve borrosa o pixelada.**
R: El módulo muestra la imagen que PrestaShop proporciona para la lista de productos. Si la imagen original subida para ese producto es de baja resolución, la versión ampliada también aparecerá borrosa. Asegúrese de subir imágenes de alta resolución para sus productos.

**P: ¿Este módulo ralentiza mi Back Office?**
R: No, el módulo es muy ligero. Solo carga una pequeña biblioteca JavaScript y la aplica cuando pasa el ratón por encima de una imagen. No realiza operaciones pesadas ni consultas a la base de datos que puedan afectar el rendimiento.

**P: ¿Puedo personalizar el tamaño del cuadro de zoom o el nivel de zoom?**
R: El módulo utiliza una herramienta estándar "elevateZoom", que tiene algunos comportamientos predeterminados. Si bien el módulo en sí no ofrece opciones de configuración para estos aspectos visuales específicos, un desarrollador podría modificar el archivo `zplb.js` para ajustar estos parámetros. Esto requeriría codificación personalizada.

## 4. Guía para desarrolladores y webmasters (Arquitectura técnica y mapa de código)

Esta sección es estrictamente para desarrolladores, webmasters de tiendas y agencias técnicas que mantienen o extienden la tienda.

### 4.1 Resumen de la arquitectura

El módulo "Zoom de imágenes en la lista de productos del back office" (`zplb`) es un módulo de PrestaShop simple pero efectivo, diseñado principalmente para inyectar JavaScript del lado del cliente en la lista de productos del Back Office. Aprovecha el sistema de hooks de PrestaShop para cargar sus activos y se basa en una biblioteca JavaScript de terceros (elevateZoom, aunque integrada en `zplb.js`) para proporcionar la funcionalidad de zoom. No introduce nuevas tablas de base de datos ni lógica de negocio compleja.

### 4.2 Controladores (`controllers/`)

- **Controladores de Front-Office**: Ninguno. Este módulo es exclusivamente para el Back Office.
- **Controladores de Administración de Back-Office**: Ninguno. La configuración del módulo se maneja directamente dentro del método `getContent()` del archivo principal del módulo.

### 4.3 Clases y modelos principales (`classes/`)

- Ninguno. El módulo no define ninguna clase personalizada ni instancias de `ObjectModel`. Toda la lógica está contenida dentro del archivo principal `zplb/index.php`.

### 4.4 Activos JavaScript (`views/js/`)

- `zplb/lib/js/zplb.js`
  - **Alcance:** Back-office. Este script se carga específicamente en la página de lista de productos del Back Office.
  - **Funcionalidad:** Este archivo contiene la lógica JavaScript central para la función de zoom. Probablemente incluye o integra la biblioteca "elevateZoom". Se dirige a los elementos de imagen del producto dentro de la tabla de lista de productos del Back Office (por ejemplo, `img.img-thumbnail` o selectores similares utilizados por la lista de productos de PrestaShop). Vincula eventos de mouseover/hover a estas imágenes e inicializa la funcionalidad de zoom, creando la vista ampliada.

### 4.5 Hojas de estilo CSS (`views/css/`)

- Ninguno. El módulo no incluye ningún archivo CSS personalizado. El estilo del cuadro de zoom suele ser manejado por la propia biblioteca JavaScript, a menudo inyectando estilos en línea o utilizando un estilo predeterminado mínimo que se integra bien con el Back Office de PrestaShop.

### 4.6 Estructura de la plantilla Smarty (`views/templates/`)

- Ninguno. El módulo no utiliza ningún archivo `.tpl`. Su funcionalidad se inyecta directamente a través de JavaScript en la estructura HTML existente de la lista de productos del Back Office.

### 4.7 Esquema de la base de datos y mapa de hooks

- **Tablas de la base de datos**:
  - El módulo no crea ninguna tabla de base de datos personalizada.
  - Almacena su configuración (por ejemplo, el ajuste "Habilitar Zoom") en la tabla `ps_configuration`, utilizando una clave como `ZPLB_ENABLED`.
- **Tabla de Hooks registrados**:

| Nombre del Hook | Momento de Ejecución | Propósito Técnico |
| --- | --- | --- |
| `displayBackOfficeHeader` | Se ejecuta en la sección `<head>` de cada página del Back Office. | Se utiliza para cargar condicionalmente el script `zplb.js` solo cuando la página actual del Back Office es la lista de productos (`AdminProducts`). Esto asegura que el script no se cargue innecesariamente en otras páginas de administración, optimizando el rendimiento. |

## 5. Soporte oficial y actualizaciones

Para obtener las últimas actualizaciones, correcciones de errores y soporte oficial para el módulo "Zoom de imágenes en la lista de productos del back office", consulte su cuenta de cliente en [MyPresta.eu](https://mypresta.eu). Nuestro equipo de soporte está disponible para ayudarle con cualquier problema o pregunta que pueda tener con respecto a la funcionalidad y compatibilidad del módulo.
"""
