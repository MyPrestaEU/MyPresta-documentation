---
title: "Moderación de comentarios/reseñas en el Panel de Control - Manual de Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop 'Moderación de comentarios/reseñas en el Panel de Control' de MyPresta.eu."
sidebar:
  label: "Moderación de comentarios/reseñas en el Panel de Control"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Dashboard comments / reviews moderation en MyPresta.eu](https://mypresta.eu/modules/administration-tools/dashboard-comments-reviews-moderation.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/back-office-tools/dashboard-comments-reviews-moderation/)
>
> ---


# Moderación de comentarios/reseñas en el Panel de Control

## 1. Requisitos y Compatibilidad
- **Versiones de PrestaShop Compatibles**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilidad con PHP**: PHP 7.1 - 8.5
- **Requisitos de Alojamiento**: Se requieren extensiones PHP estándar (cURL, JSON, OpenSSL) para PrestaShop en sí y suelen estar disponibles en todos los entornos de alojamiento modernos.

## 2. Recorrido Completo de Configuración (Cada Ajuste Agrupado por Pantalla)

### 2.1 Página de Configuración del Módulo (Back Office > Módulos > Configurar)

Después de la instalación, al hacer clic en "Configurar" accederás a la pantalla de configuración principal del módulo. Este módulo está diseñado para ser muy sencillo, con ajustes mínimos, ya que su función principal es mostrar información en tu panel de control.

**Nombre de la Pantalla:** Configuración de Moderación de comentarios/reseñas en el Panel de Control

**Ubicación del Menú:** Back Office > Módulos > Gestor de Módulos > Moderación de comentarios/reseñas en el Panel de Control > Configurar

| Ajuste / Opción | Qué hace este ajuste | Efecto de cambiar este ajuste | Valor recomendado | Escenario / ejemplo de comerciante |
|---|---|---|---|---|
| **Actualizaciones de MyPresta.eu** | Esta sección generalmente se relaciona con la comprobación de actualizaciones para los módulos de MyPresta.eu. Podría incluir opciones para habilitar/deshabilitar las comprobaciones de actualización o mostrar notificaciones de actualización. | *Cuando está habilitado:* El módulo comprobará periódicamente MyPresta.eu en busca de versiones más recientes y te notificará en el back office si hay una actualización disponible. Esto te ayuda a mantener tu módulo actualizado con las últimas características y correcciones de errores. *Cuando está deshabilitado:* El módulo no comprobará las actualizaciones automáticamente. Tendrías que comprobar manualmente las actualizaciones en MyPresta.eu. | **Habilitado (Sí)** | Mantener esto habilitado asegura que siempre estés al tanto de las nuevas versiones, lo que te permite beneficiarte de mejoras y actualizaciones de seguridad sin comprobaciones manuales. |
| **Update_ (Interno)** | Este es un ajuste interno, probablemente relacionado con el mecanismo de actualización en sí. No está destinado a la interacción directa del comerciante. | No se recomienda cambiar este ajuste, ya que podría interferir con la capacidad del módulo para comprobar y aplicar actualizaciones. | **Dejar como predeterminado** | Este es un ajuste técnico; los propietarios de la tienda no deben modificarlo. |
| **Updatev_ (Interno)** | Similar a `update_`, este es un ajuste interno relacionado con la versión para el mecanismo de actualización. | No se recomienda cambiar este ajuste, ya que podría interferir con la capacidad del módulo para comprobar y aplicar actualizaciones. | **Dejar como predeterminado** | Este es un ajuste técnico; los propietarios de la tienda no deben modificarlo. |

**Nota Importante:** La funcionalidad principal de mostrar comentarios y reseñas en tu panel de control no requiere una configuración extensa. Una vez instalado, el módulo se integra automáticamente con tu panel de control para mostrar las reseñas pendientes y los comentarios reportados, asumiendo que tienes el módulo estándar de PrestaShop "Comentarios de productos" (o una alternativa compatible) instalado y activo.

### 2.2 Pantallas de Administración Dedicadas y Vistas de Controlador
Este módulo **no** introduce ninguna nueva pantalla de administración dedicada ni vistas de controlador personalizadas. Su funcionalidad se integra directamente en el panel de control existente de PrestaShop.

### 2.3 Tabla de Referencia Rápida de Configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
|---|---|---|---|
| Página de Configuración del Módulo | Actualizaciones de MyPresta.eu | Habilitado (Sí) | Habilita las comprobaciones automáticas de actualizaciones del módulo desde MyPresta.eu. |
| Página de Configuración del Módulo | Update_ | Dejar como predeterminado | Ajuste interno para el mecanismo de actualización. |
| Página de Configuración del Módulo | Updatev_ | Dejar como predeterminado | Ajuste interno de versión para el mecanismo de actualización. |

## 3. Solución de Problemas para Comerciantes y Preguntas Frecuentes (FAQ)

**P1: He instalado el módulo, pero no veo ningún comentario/reseña en mi panel de control.**
**R1:**
*   **Verifica el módulo "Comentarios de productos":** Este módulo depende del módulo estándar de PrestaShop "Comentarios de productos" (o un módulo de reseñas de terceros compatible) para funcionar. Asegúrate de que el módulo "Comentarios de productos" esté instalado, habilitado y configurado correctamente en tu tienda.
*   **Borrar caché:** Ve a **Parámetros avanzados > Rendimiento** y haz clic en "Borrar caché" en la parte superior derecha. A veces, la caché de PrestaShop necesita ser actualizada para que aparezcan nuevos elementos del panel de control.
*   **Verifica si hay reseñas pendientes:** ¿Realmente tienes reseñas esperando moderación o comentarios reportados como abusivos? El módulo solo mostrará contenido que necesite tu atención. Si no hay tales elementos, el bloque del panel de control podría aparecer vacío o no mostrarse si no hay nada que mostrar.

**P2: El bloque del panel de control se ve extraño o no está estilizado correctamente.**
**R2:**
*   **Borrar caché del navegador:** A veces, tu navegador web almacena en caché archivos CSS antiguos. Intenta borrar la caché de tu navegador o abrir tu back office en una ventana de incógnito/privada.
*   **Verifica conflictos de tema:** Aunque es raro para los módulos del panel de control, un tema de administración altamente personalizado podría potencialmente entrar en conflicto. Si sospechas esto, intenta cambiar temporalmente al tema de administración predeterminado de PrestaShop (si es posible) para ver si el problema persiste. Si se resuelve, consulta a tu desarrollador de temas.
*   **Borrar caché de PrestaShop:** Como se mencionó anteriormente, borrar la caché de Smarty en **Parámetros avanzados > Rendimiento** puede resolver problemas de visualización.

**P3: ¿Cómo traduzco el texto del módulo a otro idioma?**
**R3:**
*   Navega a **Internacional > Traducciones** en tu Back Office de PrestaShop.
*   Selecciona "Traducciones de módulos instalados" para el "Tipo de traducción".
*   Elige tu tema (por ejemplo, "Classic") y el idioma al que deseas traducir.
*   Busca "Moderación de comentarios/reseñas en el Panel de Control" en la lista, haz clic en "Modificar", y podrás traducir todas las cadenas de texto disponibles.

**P4: Hice clic en "Configurar" pero solo veo la configuración de actualización, no las herramientas de moderación.**
**R4:** El botón "Configurar" para este módulo lleva a su página de configuración mínima, principalmente para la gestión de actualizaciones. Las herramientas de moderación reales (la lista de comentarios/reseñas) se muestran directamente en tu panel de control principal de PrestaShop, generalmente en una de las áreas de "Zona del Panel de Control". Navega a tu "Panel de Control" principal (la primera página que ves después de iniciar sesión) para encontrar la salida del módulo.

## 4. Guía para Desarrolladores y Webmasters (Arquitectura Técnica y Mapa de Código)

### 4.1 Resumen de la Arquitectura
El módulo "Moderación de comentarios/reseñas en el Panel de Control" (`dashcomments`) es un módulo ligero de PrestaShop diseñado para extender el panel de control del Back Office. Aprovecha el sistema de hooks de PrestaShop para inyectar un bloque personalizado en el panel de control, mostrando las reseñas de productos pendientes y los comentarios reportados. No introduce nuevas tablas de base de datos ni estructuras `ObjectModel` complejas, sino que se basa en los datos existentes del módulo `ps_product_comment`. Su función principal es la presentación y la interacción con los datos existentes a través de AJAX.

### 4.2 Controladores (`controllers/`)
Este módulo **no** incluye ningún controlador personalizado de front-office o back-office. Todas las interacciones se manejan directamente dentro de la clase principal del módulo (`dashcomments.php`) o a través de llamadas AJAX procesadas por los métodos `ajaxProcess` del módulo.

### 4.3 Clases y Modelos Principales (`classes/`)
Este módulo **no** define ninguna clase o modelo personalizado en el directorio `classes/`. Interactúa directamente con las funcionalidades principales de PrestaShop e, implícitamente, con la clase `ProductComment` del módulo `ps_product_comments` (si está instalado).

### 4.4 Activos JavaScript (`views/js/`)

-   **`dashcomments/js/dashcomments.js`**
    *   **Ámbito:** Back-office (Panel de Control).
    *   **Propósito:** Gestiona las interacciones AJAX para moderar comentarios y reseñas directamente desde el widget del panel de control.
    *   **Funcionalidad Clave:**
        *   Vincula los escuchadores de eventos de clic a los botones "Aprobar", "Desaprobar" y "Eliminar" dentro del widget del panel de control.
        *   Envía solicitudes AJAX a los métodos `ajaxProcess` del módulo (por ejemplo, `ajaxProcessApproveComment`, `ajaxProcessDisapproveComment`, `ajaxProcessDeleteComment`) para realizar acciones de moderación.
        *   Actualiza el DOM (elimina la fila del comentario moderado, actualiza los recuentos) tras una respuesta AJAX exitosa.
        *   Puede incluir lógica para manejar acciones de "reportar como abusivo" si se implementa para los propios comentarios.
        *   Utiliza `$.ajax` para la comunicación asíncrona.

### 4.5 Hojas de Estilo CSS (`views/css/`)

-   **`dashcomments/css/dashcomments.css`**
    *   **Ámbito:** Back-office (Panel de Control).
    *   **Propósito:** Proporciona estilos para el widget del panel de control que muestra los comentarios y reseñas pendientes.
    *   **Estilo Clave:**
        *   Estilos para la lista de comentarios, filas de comentarios individuales, botones de acción (aprobar, desaprobar, eliminar) y potencialmente contadores para elementos pendientes.
        *   Asegura que el widget se integre visualmente con el tema del back-office de PrestaShop 1.7+/8+.
        *   **Selectores de Clase CSS Clave:** Los desarrolladores pueden inspeccionar el HTML generado en busca de clases específicas (por ejemplo, `.dashcomments-widget`, `.dashcomments-item`, `.dashcomments-actions`) para anular o extender el estilo en sus temas de administración personalizados.

### 4.6 Estructura de Plantillas Smarty (`views/templates/`)

-   **`dashcomments/dashboardZoneOne.tpl`**
    *   **Ámbito:** Back-office (Panel de Control).
    *   **Hook:** `displaydashboardZoneTwo` (o `dashboardZoneTwo` en versiones anteriores).
    *   **Propósito:** Esta plantilla es responsable de renderizar la estructura HTML del widget de moderación de comentarios/reseñas en el panel de control de PrestaShop.
    *   **Contenido:**
        *   Muestra una lista de comentarios de productos que están pendientes de aprobación.
        *   Muestra una lista de comentarios de productos que han sido reportados como abusivos.
        *   Para cada comentario, generalmente muestra el nombre del producto, el nombre del cliente, el contenido del comentario, la calificación y los botones de acción (Aprobar, Desaprobar, Eliminar).
        *   Incluye lógica para iterar sobre las variables `$pending_comments` y `$reported_comments` pasadas desde el módulo.
        *   Contiene los elementos HTML y atributos de datos necesarios para que el script `dashcomments.js` adjunte sus escuchadores de eventos y realice acciones AJAX.

### 4.7 Esquema de Base de Datos y Mapa de Hooks

-   **Tablas de Base de Datos**: Este módulo no crea ninguna tabla de base de datos personalizada. Se basa en la tabla `ps_product_comment` (y tablas relacionadas como `ps_product_comment_grade`, `ps_product_comment_criterion`) que son creadas por el módulo oficial `ps_product_comments`.
-   **Registros de Configuración**:
    *   `PS_DASHCOMMENTS_UPDATES`: Almacena el estado de las comprobaciones de actualización.
    *   `PS_DASHCOMMENTS_UPDATE_`: Bandera de actualización interna.
    *   `PS_DASHCOMMENTS_UPDATEV_`: Bandera de versión interna para actualizaciones.

-   **Tabla de Hooks Registrados**:

| Nombre del Hook | Momento de Ejecución | Propósito Técnico |
|---|---|---|
| `actionAdminControllerSetMedia` | Se ejecuta cuando un controlador de administración está configurando sus activos multimedia (CSS/JS). | Se utiliza para registrar los archivos `dashcomments.js` y `dashcomments.css` del módulo para el panel de control del Back Office. |
| `displaydashboardZoneTwo` | Renderiza contenido en la segunda zona del panel de control del Back Office de PrestaShop. | Este es el hook principal utilizado para mostrar el widget de moderación de comentarios/reseñas. |
| `dashboardZoneTwo` | (Hook heredado, similar a `displaydashboardZoneTwo`) | Proporciona compatibilidad para versiones anteriores de PrestaShop o diseños de panel de control alternativos para mostrar el widget. |

## 5. Soporte Oficial y Actualizaciones
Para soporte oficial, actualizaciones del módulo y cualquier asistencia adicional, consulta tu cuenta de cliente en [MyPresta.eu](https://mypresta.eu/). Puedes descargar las últimas versiones del módulo desde tu historial de pedidos y acceder a nuestros canales de soporte dedicados para cualquier consulta o problema técnico.
