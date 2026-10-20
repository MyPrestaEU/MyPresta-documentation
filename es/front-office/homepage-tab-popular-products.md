---
title: "Pestaña de productos populares en la página de inicio - Manual para el comerciante y guía de configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop 'Pestaña de productos populares en la página de inicio' de MyPresta.eu."
sidebar:
  label: "Pestaña de productos populares en la página de inicio - Manual para el comerciante y guía de configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Homepage tab popular products en MyPresta.eu](https://mypresta.eu/modules/front-office-features/homepage-tab-popular-products.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/front-office/homepage-tab-popular-products/)
>
> ---


# Pestaña de productos populares en la página de inicio

## 1. Requisitos y compatibilidad

- **Versiones de PrestaShop compatibles**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilidad con PHP**: PHP 7.1 - 8.5
- **Requisitos de alojamiento**: Las extensiones PHP estándar (cURL, JSON, OpenSSL) suelen ser suficientes. Normalmente no se necesitan configuraciones de servidor especiales más allá de un entorno de alojamiento estándar de PrestaShop.

## 2. Recorrido completo por la configuración (Cada ajuste agrupado por pantalla)

### 2.1 Página de configuración del módulo (Back Office > Módulos > Configurar)

Después de la instalación, haga clic en el botón "Configurar" junto al módulo "Pestaña de productos populares en la página de inicio" en el Gestor de módulos. Esto le llevará a su pantalla de configuración principal.

#### Ajustes generales

- **Qué hace este ajuste:** Este módulo se centra principalmente en mostrar productos populares. La pantalla de configuración de este módulo es bastante sencilla, a menudo incluye ajustes estándar de notificación de actualizaciones de MyPresta.eu. La funcionalidad principal de mostrar "productos populares" suele ser gestionada automáticamente por la lógica interna de PrestaShop para identificar artículos populares (por ejemplo, basándose en ventas, vistas o una combinación).
- **Efecto de cambiar este ajuste:**
  - **`mypresta_updates` (Activar/Desactivar notificaciones de actualizaciones de MyPresta.eu):**
    - *Cuando está activado:* Recibirá notificaciones en su back office de PrestaShop cuando haya nuevas versiones o actualizaciones importantes disponibles para los módulos de MyPresta.eu (incluido este). Esto le ayuda a mantener sus módulos seguros y actualizados con las últimas características y correcciones de errores.
    - *Cuando está desactivado:* No recibirá estas notificaciones. Tendría que revisar manualmente su cuenta de MyPresta.eu para buscar actualizaciones.
  - **`update_` y `updatev_` (Parámetros internos de verificación de actualizaciones):** Estos son típicamente ajustes internos utilizados por los módulos de MyPresta.eu para gestionar y rastrear las verificaciones de actualizaciones. No suelen estar destinados a la interacción directa del comerciante.
- **Valor recomendado:**
  - Para `mypresta_updates`: **SÍ** (Activado). Mantener esto activado asegura que siempre esté informado sobre actualizaciones críticas, mejorando la seguridad y el rendimiento de su tienda.
  - Para `update_` y `updatev_`: Dejar como predeterminado. Son internos y no deben modificarse.
- **Escenario / ejemplo del comerciante:**
  - Desea asegurarse de que su tienda siempre esté ejecutando las últimas versiones más seguras de sus módulos de MyPresta.eu. Al activar las notificaciones de actualización, verá una alerta clara en su panel de administración de PrestaShop cada vez que se lance una actualización para "Pestaña de productos populares en la página de inicio" (o cualquier otro módulo de MyPresta.eu). Esto le permite descargar e instalar rápidamente la nueva versión, beneficiándose de las mejoras sin tener que verificar constantemente de forma manual.

#### Nota importante sobre la lógica de "Productos populares":

Este módulo aprovecha los mecanismos existentes de PrestaShop para determinar qué constituye un "producto popular". Típicamente, PrestaShop identifica los productos populares basándose en datos de ventas (productos con más pedidos) o vistas. El módulo en sí mismo no suele ofrecer ajustes específicos para definir la "popularidad" (por ejemplo, "mostrar productos vendidos en los últimos 30 días" o "productos con X vistas"). Se basa en la funcionalidad central de PrestaShop para esto. Si necesita influir en qué productos aparecen como "populares", generalmente necesitaría aumentar sus ventas o visibilidad a través de otros esfuerzos de marketing.

### 2.2 Tabla de referencia rápida de configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| Página de configuración del módulo | Notificaciones de actualizaciones de MyPresta.eu | Activado (SÍ) | Reciba alertas de actualizaciones del módulo, garantizando seguridad y nuevas características. |
| Página de configuración del módulo | `update_` | Predeterminado | Configuración interna para el seguimiento de actualizaciones. Dejar sin cambios. |
| Página de configuración del módulo | `updatev_` | Predeterminado | Configuración interna para el seguimiento de actualizaciones. Dejar sin cambios. |

## 3. Solución de problemas del comerciante y preguntas frecuentes (FAQ)

**P1: La pestaña "Productos populares" no aparece en mi página de inicio.**
R1:

- **Verificar el estado del módulo:** Vaya a **Módulos > Gestor de módulos** y asegúrese de que "Pestaña de productos populares en la página de inicio" esté instalado y activado.
- **Borrar caché:** A veces, la caché de PrestaShop impide que aparezca contenido nuevo. Vaya a **Parámetros avanzados > Rendimiento** y haga clic en "Borrar caché" (o "Borrar caché de Smarty" si está disponible).
- **Compatibilidad con el tema:** Aunque el módulo está diseñado para PrestaShop 1.7.x, 8.x y 9.x, algunos temas altamente personalizados podrían requerir pequeños ajustes. Si borrar la caché no funciona, póngase en contacto con el desarrollador de su tema o con el soporte de MyPresta.eu.
- **Verificación de hook:** Asegúrese de que el hook `displayHome` esté activo y sea renderizado por su tema.

**P2: Los productos mostrados en la pestaña "Productos populares" no me parecen "populares".**
R2:

- **Definición de PrestaShop:** El módulo se basa en la lógica interna de PrestaShop para identificar productos populares, que típicamente se basa en el volumen de ventas o las vistas del producto. Si su tienda es nueva o tiene pocas ventas, la lista de "populares" podría no ser tan dinámica.
- **Actualización de datos:** Asegúrese de que su tienda tenga datos de ventas recientes. La "popularidad" se calcula con el tiempo.
- **Caché:** Borre la caché de PrestaShop como se describe en la P1.

**P3: ¿Puedo cambiar el título de la pestaña (por ejemplo, de "Productos populares" a "Nuestros más vendidos")?**
R3:

- Este módulo suele utilizar un título predeterminado. Para cambiarlo, normalmente necesitaría editar los archivos de traducción del módulo o, en algunos casos, modificar directamente el archivo de plantilla.
  - Vaya a **Internacional > Traducciones**.
  - Seleccione "Traducciones de módulos instalados", su tema y su idioma.
  - Busque el módulo "Pestaña de productos populares en la página de inicio" y busque la cadena del título de la pestaña.
  - Si no es traducible de esta manera, podría requerir un pequeño cambio de código en `homepagetabs.tpl` (ver Sección 7).

**P4: El estilo de los productos en la pestaña no coincide con mi tema.**
R4:

- El módulo utiliza su propio CSS (`homepagetabs.css`). El CSS de su tema podría anular algunos estilos, o los estilos del módulo podrían entrar en conflicto.
- **CSS personalizado:** El mejor enfoque es añadir CSS personalizado al archivo `custom.css` de su tema (o equivalente) para anular los estilos del módulo y hacer que coincida perfectamente con su tema. Utilice las herramientas de desarrollo de su navegador para inspeccionar los elementos e identificar los selectores CSS utilizados por el módulo.

**P5: ¿Cómo traduzco el título de la pestaña u otros textos del módulo a diferentes idiomas?**
R5:

- Vaya a **Internacional > Traducciones** en su back office de PrestaShop.
- Seleccione "Traducciones de módulos instalados", luego elija su tema y el idioma al que desea traducir.
- Busque el módulo "Pestaña de productos populares en la página de inicio" en la lista y debería poder editar las cadenas de texto asociadas a él.

## 4. Guía para desarrolladores y webmasters (Arquitectura técnica y mapa de código)

Esta sección proporciona una inmersión profunda en la estructura técnica del módulo "Pestaña de productos populares en la página de inicio", destinada a desarrolladores, webmasters y agencias técnicas.

### 4.1 Visión general de la arquitectura

El módulo `Pestaña de productos populares en la página de inicio` (`homepagetabs`) es un módulo de PrestaShop sencillo diseñado principalmente para extender el hook `displayHome`. Sigue un patrón estándar de PrestaShop similar a MVC para módulos, donde el archivo principal del módulo (`homepagetabs.php`) maneja la instalación, desinstalación, configuración y registro de hooks. El módulo inyecta una pestaña personalizada y su contenido en la página de inicio, aprovechando los mecanismos existentes de PrestaShop para la obtención de "productos populares".

### 4.2 Controladores (`controllers/`)

Este módulo no contiene ningún controlador de Front-Office o Back-Office Admin personalizado. Toda la lógica está encapsulada dentro del archivo principal del módulo y sus plantillas y activos asociados.

### 4.3 Clases y modelos principales (`classes/`)

Este módulo no define ninguna clase personalizada ni extiende `ObjectModel`. Opera utilizando las funcionalidades principales de PrestaShop para la recuperación de productos.

### 4.4 Activos JavaScript (`views/js/`)

- **`homepagetabs/views/js/homepagetabs.js`**
  - **Alcance:** Front-office.
  - **Propósito:** Este archivo probablemente contiene la lógica JavaScript para manejar la funcionalidad de cambio de pestañas en la página de inicio. Podría escuchar eventos de clic en la pestaña "Productos populares", mostrar/ocultar el contenido del producto correspondiente y, potencialmente, interactuar con otras pestañas de la página de inicio para asegurar que solo el contenido de una pestaña sea visible a la vez. También puede incluir lógica para el comportamiento responsivo o la carga diferida de imágenes de productos dentro de la pestaña.
  - **Funcionalidad clave:**
    - Escuchadores de eventos para clics en pestañas.
    - Manipulación del DOM para alternar la visibilidad de las listas de productos.
    - Potencialmente se integra con el comportamiento de pestañas predeterminado de PrestaShop o con sistemas de pestañas de temas personalizados.

### 4.5 Hojas de estilo CSS (`views/css/`)

- **`homepagetabs/views/css/homepagetabs.css`**
  - **Alcance:** Estilo del cliente en el Front-office.
  - **Propósito:** Esta hoja de estilo define la apariencia visual de la pestaña "Productos populares" y las listas de productos dentro de ella. Asegura que la pestaña esté correctamente posicionada, estilizada y que la cuadrícula/lista de productos se presente de forma ordenada.
  - **Componentes principales de la interfaz de usuario con estilo:**
    - El encabezado de la pestaña en sí (por ejemplo, `.homepagetabs-tab-title`).
    - El contenedor para los productos populares (por ejemplo, `.homepagetabs-products-container`).
    - Elementos individuales del producto dentro de la pestaña (por ejemplo, imágenes de productos, nombres, precios, botones).
    - Ajustes responsivos para diferentes tamaños de pantalla.
  - **Selectores de clase CSS clave para anular:** Los desarrolladores pueden inspeccionar el HTML generado para encontrar selectores específicos. Los comunes podrían incluir:
    - `.homepagetabs-tab`
    - `.homepagetabs-tab-content`
    - `.homepagetabs-product-list`
    - `.homepagetabs-product-item`

### 4.6 Estructura de la plantilla Smarty (`views/templates/`)

- **Plantillas de hook (`views/templates/hook/`)**:
  - **`homepagetabs/views/templates/hook/homepagetabs.tpl`**
    - **Hook:** `displayHome`
    - **Propósito:** Esta es la plantilla principal del front-office. Es responsable de renderizar el encabezado de la pestaña "Productos populares" y el contenedor para la lista de productos. Típicamente iterará sobre una colección de productos populares que le pasa el método `hookDisplayHome` del módulo y renderizará cada producto utilizando un parcial estándar de lista de productos de PrestaShop (o uno personalizado definido dentro del módulo). Esta plantilla es donde se genera la estructura HTML real para la pestaña y su contenido.
- **Plantillas de administración (`views/templates/admin/`)**:
  - **`homepagetabs/views/templates/admin/homepagetabs.tpl`**
    - **Propósito:** Esta plantilla renderiza el formulario de configuración del módulo en el Back Office de PrestaShop. Muestra los ajustes para las notificaciones de actualización (`mypresta_updates`) y, potencialmente, otras opciones específicas del módulo si se añadieran. Utiliza las clases de formulario de ayuda de PrestaShop para generar los campos de entrada y los botones de guardar.

### 4.7 Esquema de la base de datos y mapa de hooks

- **Tablas de la base de datos**: Este módulo no crea ninguna tabla de base de datos personalizada. Almacena sus ajustes de configuración (como `mypresta_updates`) en la tabla estándar `ps_configuration`.
- **Tabla de Hooks registrados**:

| Nombre del Hook | Momento de ejecución | Propósito técnico |
| --- | --- | --- |
| `displayHome` | Renderiza contenido en la página de inicio de la tienda. | Inyecta la pestaña "Productos populares" y su contenido en el área principal de la página de inicio. |
| `displayHeader` | Se ejecuta en la sección `<head>` de cada página. | Se utiliza para encolar los archivos CSS (`homepagetabs.css`) y JavaScript (`homepagetabs.js`) del módulo, asegurando que se carguen correctamente para la visualización en el front-office. |

## 5. Soporte oficial y actualizaciones

Para actualizaciones oficiales, soporte técnico y cualquier consulta relacionada con el módulo "Pestaña de productos populares en la página de inicio", consulte su cuenta de cliente en [MyPresta.eu](https://mypresta.eu/). Nuestro equipo de soporte y recursos están disponibles para ayudarle con la instalación, configuración y solución de problemas.
