---
title: "Notas Adhesivas del Back Office - Manual del Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo Notas Adhesivas del Back Office de PrestaShop por MyPresta.eu."
sidebar:
  label: "Notas Adhesivas del Back Office - Manual del Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Back office Sticky Notes en MyPresta.eu](https://mypresta.eu/modules/administration-tools/back-office-sticky-notes.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/back-office-tools/back-office-sticky-notes/)
>
> ---


# Notas Adhesivas del Back Office

## 1. Requisitos y Compatibilidad

- **Versiones de PrestaShop Compatibles**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x
- **Compatibilidad con PHP**: PHP 5.6 - 8.5
- **Requisitos de Alojamiento**: Las extensiones PHP estándar (cURL, JSON, OpenSSL) suelen ser suficientes y generalmente vienen preinstaladas en la mayoría de los entornos de alojamiento.

## 2. Recorrido Completo por la Configuración (Cada Ajuste Agrupado por Pantalla)

### 2.1 Página de Configuración del Módulo (Back Office > Módulos > Configurar)

Después de la instalación, al hacer clic en "Configurar" accederás a la pantalla de configuración principal del módulo "Notas Adhesivas del Back Office". Aquí es donde gestionas tus notas adhesivas.

La página de configuración en sí no tiene muchos "ajustes" en el sentido tradicional (como interruptores de encendido/apagado). En cambio, es tu centro para crear, editar y gestionar todas tus notas adhesivas.

#### **Añadir una Nueva Nota Adhesiva**

En la parte superior de la página de configuración, normalmente encontrarás un formulario o sección para añadir una nueva nota.

-   **Contenido de la Nota (Área de Texto):**

    -   **Qué hace este ajuste:** Aquí es donde escribes el mensaje o recordatorio real para tu nota adhesiva.
    -   **Efecto de cambiar este ajuste:** Lo que escribas aquí se mostrará en la nota adhesiva en tu back office.
    -   **Valor recomendado:** Sé conciso y claro. Usa viñetas o frases cortas para facilitar la lectura.
    -   **Escenario / ejemplo del comerciante:** "Recordar hacer seguimiento con el cliente #1234 sobre el estado de su pedido." o "Nuevas imágenes de productos para 'Colección de Verano' para el viernes."
-   **Color de la Nota (Selector de Color):**

    -   **Qué hace este ajuste:** Te permite elegir el color de fondo de tu nota adhesiva.
    -   **Efecto de cambiar este ajuste:** La nota adhesiva aparecerá con el color elegido en el back office. Diferentes colores pueden ayudar a categorizar las notas o resaltar la urgencia.
    -   **Valor recomendado:** Elige colores que destaquen pero que no sean demasiado distractores. Podrías usar rojo para notas urgentes, amarillo para recordatorios generales y verde para tareas completadas.
    -   **Escenario / ejemplo del comerciante:** Establece una nota sobre un error crítico en rojo y una nota sobre una nueva idea de marketing en amarillo.
-   **Botón Guardar / Añadir Nota:**

    -   **Qué hace este ajuste:** Envía el contenido y el color que has elegido para crear una nueva nota adhesiva.
    -   **Efecto de cambiar este ajuste:** Se creará una nueva nota adhesiva y aparecerá en las páginas de tu back office. También se listará en la sección "Notas Existentes" a continuación.
    -   **Valor recomendado:** Haz clic en esto después de haber finalizado el contenido y el color de tu nota.
    -   **Escenario / ejemplo del comerciante:** Después de escribir tu recordatorio y seleccionar un color, haz clic en "Guardar" para activar la nota.

#### **Gestionar Notas Adhesivas Existentes**

Debajo de la sección "Añadir Nueva Nota", verás una lista o tabla de todas las notas adhesivas que ya has creado.

-   **Lista de Notas (Tabla/Visualización):**

    -   **Qué hace este ajuste:** Muestra todas las notas adhesivas activas, su contenido y su color asignado.
    -   **Efecto de cambiar este ajuste:** Esta es una visualización de tus notas actuales. Puedes revisarlas visualmente aquí.
    -   **Valor recomendado:** Revisa regularmente esta lista para asegurarte de que las notas sigan siendo relevantes.
    -   **Escenario / ejemplo del comerciante:** Escanea rápidamente la lista para ver todas las tareas o recordatorios pendientes.
-   **Botón Editar (para cada nota):**

    -   **Qué hace este ajuste:** Te permite modificar el contenido o el color de una nota adhesiva existente.
    -   **Efecto de cambiar este ajuste:** Al hacer clic en esto, normalmente se cargará el contenido de la nota de nuevo en el formulario "Añadir Nueva Nota" (que podría cambiar a modo "Editar Nota"), permitiéndote realizar cambios. Una vez guardada, la nota se actualizará en todo tu back office.
    -   **Valor recomendado:** Úsalo para actualizar el estado de las tareas, añadir más detalles o cambiar la urgencia.
    -   **Escenario / ejemplo del comerciante:** Una nota dice "Revisar nuevas imágenes de productos". Una vez revisadas, puedes editarla a "Nuevas imágenes de productos aprobadas".
-   **Botón Eliminar (para cada nota):**

    -   **Qué hace este ajuste:** Elimina permanentemente una nota adhesiva.
    -   **Efecto de cambiar este ajuste:** La nota desaparecerá de tu back office y ya no se listará en la configuración. Esta acción suele ser irreversible.
    -   **Valor recomendado:** Elimina las notas solo cuando la tarea esté completada o la información ya no sea relevante.
    -   **Escenario / ejemplo del comerciante:** Una vez que se resuelve un problema de pedido, elimina la nota adhesiva relacionada con él.

### 2.2 Tabla de Referencia Rápida de Configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| Página de Configuración del Módulo | **Contenido de la Nota (Área de Texto)** | Texto claro y conciso | El mensaje real que se muestra en la nota adhesiva. |
| Página de Configuración del Módulo | **Color de la Nota (Selector de Color)** | Seleccionado por el usuario | Establece el color de fondo de la nota para categorización/urgencia. |
| Página de Configuración del Módulo | **Botón Guardar / Añadir Nota** | Haz clic después de establecer el contenido/color | Crea una nueva nota adhesiva visible en el back office. |
| Página de Configuración del Módulo | **Botón Editar (por nota)** | Haz clic para modificar | Permite actualizar el contenido o el color de una nota existente. |
| Página de Configuración del Módulo | **Botón Eliminar (por nota)** | Haz clic para eliminar | Elimina permanentemente una nota adhesiva del back office. |

## 3. Resolución de Problemas del Comerciante y Preguntas Frecuentes (FAQ)

**P1: Mis notas adhesivas no aparecen en el back office después de guardarlas.**
R1:

-   **Borrar Caché:** La razón más común de los problemas de visualización es la caché. Ve a **Parámetros Avanzados > Rendimiento** en tu back office de PrestaShop. Haz clic en "Borrar caché" (o "Borrar caché de Smarty" en versiones anteriores).
-   **Verificar Estado del Módulo:** Asegúrate de que el módulo esté instalado y habilitado en **Módulos > Gestor de Módulos**.
-   **Caché del Navegador:** Intenta borrar la caché de tu navegador o abrir tu back office en una ventana de incógnito/privada para descartar problemas específicos del navegador.

**P2: ¿Puedo mover las notas adhesivas por la pantalla?**
R2: Sí, una vez que una nota adhesiva se muestra en tu back office, deberías poder hacer clic y arrastrarla a cualquier posición de la página. El módulo está diseñado para recordar su posición por ti.

**P3: ¿Pueden diferentes administradores ver las notas adhesivas de los demás?**
R3: Sí, por defecto, todas las notas adhesivas creadas a través de este módulo son visibles para todos los administradores que tienen acceso al back office. Esta es una característica clave para la colaboración en equipo.

**P4: Los colores de mis notas adhesivas se ven extraños o no se aplican correctamente.**
R4:

-   **Verificar Selector de Color:** Asegúrate de estar usando la herramienta de selección de color correctamente en la página de configuración del módulo.
-   **Conflictos con Temas Personalizados:** Si estás utilizando un tema de back office muy personalizado, podría haber conflictos de CSS. Intenta cambiar temporalmente al tema predeterminado del back office de PrestaShop para ver si el problema persiste. Si se resuelve, es probable que el CSS de tu tema esté sobrescribiendo los estilos del módulo.
-   **Compatibilidad del Navegador:** Asegúrate de que tu navegador esté actualizado.

**Q5: ¿Cómo traduzco la interfaz del módulo a otro idioma?**
R5:

-   Ve a **Internacional > Traducciones** en tu back office de PrestaShop.
-   Selecciona "Traducciones de módulos instalados", elige tu tema y luego selecciona el idioma al que deseas traducir.
-   Busca "Notas Adhesivas del Back Office" en la lista y traduce las cadenas de texto disponibles.

## 4. Guía para Desarrolladores y Webmasters (Arquitectura Técnica y Mapa de Código)

Esta sección es estrictamente para desarrolladores, webmasters de tiendas y agencias técnicas que mantienen o extienden la tienda.

### 4.1 Visión General de la Arquitectura

El módulo "Notas Adhesivas del Back Office" es un módulo clásico de PrestaShop diseñado principalmente para el Back Office. Aprovecha la arquitectura de módulos de PrestaShop, utilizando la clase `Module` para la instalación, desinstalación y configuración. La funcionalidad principal gira en torno a la visualización y gestión de "notas adhesivas" creadas por el usuario dentro del panel de administración. Depende en gran medida de JavaScript para la interacción front-end (arrastrar, posicionar) y AJAX para guardar los datos de las notas. La persistencia de datos se maneja a través de `ps_configuration` para la configuración del módulo y probablemente tablas de base de datos personalizadas o `ps_configuration` para las notas mismas.

### 4.2 Controladores (`controllers/`)

Este módulo no parece utilizar controladores de administración de Front-Office o Back-Office dedicados en el sentido tradicional de PrestaShop MVC (es decir, archivos en `controllers/front/` o `controllers/admin/`). Toda la configuración y el manejo de AJAX parecen gestionarse directamente dentro del archivo principal del módulo (`addstickynote.php`) utilizando el método `getContent()` para la configuración y potencialmente métodos `ajaxProcess` o llamadas AJAX directas para la gestión dinámica de notas.

### 4.3 Clases y Modelos Principales (`classes/`)

Según el inventario proporcionado, no hay clases personalizadas o definiciones de `ObjectModel` dentro de un directorio `classes/`. Esto sugiere que los datos de las notas adhesivas probablemente se almacenan directamente en la tabla `ps_configuration`, donde el contenido, el color y la posición de cada nota podrían serializarse o almacenarse como claves de configuración individuales.

### 4.4 Activos JavaScript (`views/js/`)

El módulo depende en gran medida de JavaScript para sus características interactivas en el back office.

-   `stickynotes/js/advajax.js`:
    -   **Alcance:** Back-office.
    -   **Responsabilidad:** Probablemente un script de utilidad AJAX personalizado, posiblemente un envoltorio para las funciones AJAX de jQuery o una implementación independiente para manejar la comunicación asíncrona con el backend PHP del módulo para guardar/cargar notas.
-   `stickynotes/js/joverlay.js`:
    -   **Alcance:** Back-office.
    -   **Responsabilidad:** Sugiere funcionalidad relacionada con superposiciones o ventanas emergentes modales, potencialmente utilizadas para editar el contenido de las notas en una interfaz más fácil de usar, o para mostrar mensajes de confirmación.
-   `stickynotes/js/jscolor/jscolor.js`:
    -   **Alcance:** Back-office (específicamente en la página de configuración del módulo).
    -   **Responsabilidad:** Una biblioteca JavaScript de terceros para proporcionar una interfaz de selección de color. Esto se utiliza para permitir a los administradores seleccionar el color de fondo de sus notas adhesivas.
-   `stickynotes/js/script.js`:
    -   **Alcance:** Back-office.
    -   **Responsabilidad:** Este es probablemente el script principal para la lógica front-end del módulo. Manejaría:
        -   Inicialización de notas adhesivas al cargar la página.
        -   Funcionalidad de arrastrar y soltar para reposicionar notas.
        -   Guardar posiciones de notas a través de AJAX.
        -   Detectores de eventos para editar/eliminar notas.
        -   Interacción con `advajax.js` para la persistencia de datos.
        -   Potencialmente renderizar nuevas notas dinámicamente.
-   `stickynotes/js/script17.js`:
    -   **Alcance:** Back-office (específico para PrestaShop 1.7.x y 8.x).
    -   **Responsabilidad:** Este script probablemente contiene adaptaciones o código específico para entornos PrestaShop 1.7+, abordando diferencias en la estructura del DOM, versiones de jQuery o cambios en el tema del back office en comparación con versiones anteriores de PrestaShop (1.5/1.6). Aseguraría la compatibilidad y el funcionamiento adecuado en plataformas más nuevas.

### 4.5 Hojas de Estilo CSS (`views/css/`)

El módulo incluye archivos CSS para estilizar la apariencia de las notas adhesivas.

-   `stickynotes/css/stickynotes-twig-shit.css`:
    -   **Alcance:** Estilo de administración del back-office.
    -   **Responsabilidad:** El nombre sugiere que este archivo contiene ajustes de estilo específicos o anulaciones para los back offices de PrestaShop 1.7+, que utilizan plantillas Twig. Probablemente apunta a elementos dentro del nuevo tema del back office para asegurar que las notas se muestren correcta y consistentemente.
    -   **Selectores CSS clave:** `.sticky-note`, `.sticky-note-content`, `.sticky-note-header` (hipotéticos, basados en convenciones de nombres comunes).
-   `stickynotes/css/stickynotes.css`:
    -   **Alcance:** Estilo de administración del back-office.
    -   **Responsabilidad:** Esta es la hoja de estilo principal para las notas adhesivas, definiendo su apariencia predeterminada, posicionamiento y estados interactivos (por ejemplo, cuando se arrastran). Contendría estilos generales aplicables a diferentes versiones de PrestaShop.
    -   **Selectores CSS clave:** `.sticky-note`, `.draggable`, `.resizable`, `.note-text`, `.note-controls` (hipotéticos). Los desarrolladores pueden anular estas clases en sus temas de back office personalizados si es necesario.

### 4.6 Estructura de Plantillas Smarty (`views/templates/`)

El módulo utiliza una única plantilla Smarty para renderizar las notas adhesivas en el back office.

-   **Plantillas de hook (`views/templates/hook/`)**:
    -   `stickynotes/sticky-notes-back-office.tpl`:
        -   **Renderizado en hook:** Esta plantilla probablemente está enganchada a un hook global del back office, como `displayBackOfficeHeader` o `displayAdminAfterHeader`, para inyectar la estructura HTML y la inicialización JavaScript necesarias para las notas adhesivas en todas las páginas de administración.
        -   **Salida de bloque visual:** Genera los contenedores HTML para las notas adhesivas, potencialmente incluyendo una plantilla oculta para nuevas notas, y las llamadas JavaScript para inicializar la visualización de las notas y la funcionalidad de arrastre. También contendría la lógica para iterar a través de las notas existentes y renderizarlas.

### 4.7 Esquema de Base de Datos y Mapa de Hooks

-   **Tablas de Base de Datos**:

    -   Este módulo no parece crear tablas SQL personalizadas. Es muy probable que todos los datos de las notas adhesivas (contenido, color, posición, ID) se almacenen en la tabla `ps_configuration`. Cada nota podría corresponder a una clave de configuración `PS_STICKY_NOTE_X` única, donde `X` es un identificador, y el valor es una matriz serializada o una cadena JSON que contiene las propiedades de la nota.
-   **Tabla de Hooks Registrados**:

| Nombre del Hook | Momento de Ejecución | Propósito Técnico |
| --- | --- | --- |
| `displayBackOfficeHeader` | Se ejecuta en la sección `<head>` de cada página del back office. | Inyecta los archivos CSS y JavaScript necesarios para la funcionalidad y el estilo de las notas adhesivas. |
| `displayAdminAfterHeader` (o similar) | Se ejecuta después del encabezado principal de cada página del back office. | Renderiza la estructura HTML para las notas adhesivas e inicializa su visualización y comportamiento interactivo. |
| `actionAdminControllerSetMedia` | Se ejecuta cuando un controlador de administración establece sus medios (JS/CSS). | Potencialmente utilizado para cargar condicionalmente activos JS/CSS según la página de administración actual, aunque `displayBackOfficeHeader` es más común para activos globales. |
| `actionModuleInstall` | Se ejecuta cuando se instala el módulo. | Crea entradas de configuración iniciales en `ps_configuration` (si las hay) y registra los hooks necesarios. |
| `actionModuleUninstall` | Se ejecuta cuando se desinstala el módulo. | Limpia las entradas de configuración y anula el registro de los hooks. |

## 5. Soporte Oficial y Actualizaciones

Para actualizaciones oficiales, soporte técnico y para descargar las últimas versiones del módulo "Notas Adhesivas del Back Office", visita tu cuenta de cliente en [MyPresta.eu](https://mypresta.eu/). Nuestro equipo de soporte está disponible para ayudarte con cualquier problema o pregunta que puedas tener con respecto a la funcionalidad y compatibilidad del módulo.
