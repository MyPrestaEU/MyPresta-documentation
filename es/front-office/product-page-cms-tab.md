---
title: "Pestaña CMS en página de producto - Manual de Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop 'Pestaña CMS en página de producto' de MyPresta.eu."
sidebar:
  label: "Pestaña CMS en página de producto - Manual de Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Product page CMS tab en MyPresta.eu](https://mypresta.eu/modules/front-office-features/product-page-cms-tab.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/front-office/product-page-cms-tab/)
>
> ---


# Pestaña CMS en página de producto

## 1. Requisitos y compatibilidad

- **Versiones de PrestaShop compatibles**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilidad con PHP**: PHP 7.1 - 8.5
- **Requisitos de alojamiento**: Las extensiones PHP estándar (cURL, JSON, OpenSSL) suelen ser necesarias para PrestaShop en sí y normalmente están disponibles por defecto en la mayoría de los entornos de alojamiento. No se necesitan extensiones especiales o inusuales para este módulo.

## 2. Recorrido completo por la configuración (Cada ajuste agrupado por pantalla)

### 2.1 Página de configuración del módulo (Back Office > Módulos > Configurar)

Después de la instalación, haga clic en "Configurar" junto al módulo "Pestaña CMS en página de producto" en su Gestor de módulos. Esto le llevará a la pantalla de configuración principal.

#### **Seleccionar página CMS para mostrar como pestaña**

Este es el ajuste principal del módulo. Determina cuál de sus páginas CMS existentes se mostrará como una nueva pestaña en todas las páginas de producto.

- **Qué hace este ajuste:** Este menú desplegable lista todas las páginas CMS que ha creado en su tienda PrestaShop (se encuentran en **Diseño > Páginas** o **Diseño > CMS** en versiones anteriores). Debe seleccionar una de estas páginas.
- **Efecto de cambiar este ajuste:**
  - *Cuando se selecciona una página CMS:* Aparecerá una nueva pestaña en cada página de producto de su tienda. El título de esta pestaña será el título de la página CMS seleccionada, y el contenido que se mostrará al hacer clic en la pestaña será el contenido de esa página CMS.
  - *Cuando se elige "--- Seleccionar ---":* No aparecerá ninguna pestaña nueva en las páginas de producto. El módulo estará efectivamente inactivo en términos de visualización en el front-office.
- **Valor recomendado:** Seleccione la página CMS que contenga información que desee compartir universalmente en todas sus páginas de producto (por ejemplo, una página de "Información de envío", "Guía de tallas" o "Detalles de la garantía").
- **Escenario / ejemplo de comerciante:** Desea proporcionar una "Guía de tallas" detallada para todos los productos de ropa. Primero, crearía una página CMS titulada "Guía de tallas" con toda la información relevante. Luego, en la configuración de este módulo, seleccionaría "Guía de tallas" del menú desplegable. Ahora, cada página de producto tendrá una pestaña de "Guía de tallas".

#### **Tipo de pestaña**

Este ajuste controla cómo se integra el módulo con el sistema de pestañas de PrestaShop, especialmente para diferentes versiones de PrestaShop.

- **Qué hace este ajuste:** Este menú desplegable le permite elegir el método que utiliza el módulo para mostrar la pestaña. Es principalmente un ajuste de compatibilidad para diferentes versiones de PrestaShop.
- **Efecto de cambiar este ajuste:**
  - *Cuando se selecciona "PrestaShop 1.7 / 8.x / 9.x":* El módulo utilizará el hook `displayProductExtraContent`, que es la forma estándar y recomendada de añadir nuevas pestañas en las versiones modernas de PrestaShop. Esto asegura un aspecto y una sensación nativos.
  - *Cuando se selecciona "PrestaShop 1.6":* El módulo utilizará hooks más antiguos como `productTab` y `productTabContent`, que eran estándar en PrestaShop 1.6. Esta opción es para compatibilidad con versiones anteriores si está ejecutando una tienda PrestaShop 1.6 antigua y no compatible (aunque el módulo es oficialmente para 1.7+).
- **Valor recomendado:** Para tiendas PrestaShop 1.7, 8.x y 9.x, seleccione siempre **"PrestaShop 1.7 / 8.x / 9.x"**.
- **Escenario / ejemplo de comerciante:** Si está ejecutando PrestaShop 8.1, seleccionaría "PrestaShop 1.7 / 8.x / 9.x" para asegurar que la pestaña se muestre correctamente y se integre sin problemas con el diseño de su tema. Si, por alguna razón, estuviera utilizando este módulo en una antigua tienda PrestaShop 1.6, seleccionaría "PrestaShop 1.6".

#### **Actualizaciones en vivo de MyPresta.eu**

Esta sección es común en los módulos de MyPresta.eu y le ayuda a gestionar las actualizaciones del módulo.

- **Qué hace este ajuste:** Esta función busca nuevas versiones del módulo directamente desde MyPresta.eu.
- **Efecto de cambiar este ajuste:**
  - *Cuando está habilitado:* El módulo buscará periódicamente actualizaciones. Si hay una nueva versión disponible, verá una notificación en su lista de módulos o en la página de configuración del módulo. Esto le ayuda a mantenerse al día con las correcciones de errores y las nuevas funciones.
  - *Cuando está deshabilitado:* El módulo no buscará actualizaciones automáticamente. Tendría que revisar manualmente su cuenta de MyPresta.eu para ver si hay nuevas versiones.
- **Valor recomendado:** **SÍ**. Mantener los módulos actualizados es crucial para la seguridad, la compatibilidad y el acceso a las últimas funciones.
- **Escenario / ejemplo de comerciante:** Desea asegurarse de que su módulo siempre tenga los últimos parches de seguridad. Al habilitar esto, se le notificará cuando haya una actualización disponible, lo que le incitará a descargarla e instalarla.

### 2.2 Tabla de referencia rápida de configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| Página de configuración del módulo | **Seleccionar página CMS para mostrar como pestaña** | --- Seleccionar --- / Su página CMS elegida | Determina qué contenido de la página CMS aparece como una nueva pestaña en todas las páginas de producto. |
| Página de configuración del módulo | **Tipo de pestaña** | PrestaShop 1.7 / 8.x / 9.x | Asegura la correcta visualización e integración de la pestaña con la arquitectura de su versión de PrestaShop. |
| Página de configuración del módulo | **Actualizaciones en vivo de MyPresta.eu** | SÍ | Habilita las comprobaciones automáticas de actualizaciones del módulo desde MyPresta.eu. |

## 3. Solución de problemas del comerciante y preguntas frecuentes (FAQ)

**P: La nueva pestaña no aparece en mis páginas de producto. ¿Qué debo hacer?**
R:

1. **Verifique la configuración del módulo:** Vaya a **Módulos > Gestor de módulos**, busque "Pestaña CMS en página de producto" y haga clic en "Configurar". Asegúrese de haber seleccionado una página CMS válida en el menú desplegable "Seleccionar página CMS para mostrar como pestaña". Si se elige "--- Seleccionar ---", no aparecerá ninguna pestaña.
2. **Verifique el tipo de pestaña:** Asegúrese de que "Tipo de pestaña" esté configurado en "PrestaShop 1.7 / 8.x / 9.x" para las versiones modernas de PrestaShop.
3. **Borrar caché:** Vaya a **Parámetros avanzados > Rendimiento** y haga clic en "Borrar caché" (o "Borrar caché de Smarty" en versiones anteriores). A veces, la caché de PrestaShop impide que los cambios aparezcan inmediatamente.
4. **Verifique el estado de la página CMS:** Asegúrese de que la página CMS seleccionada esté activa y sea visible públicamente (no deshabilitada o configurada como privada). Puede verificar esto en **Diseño > Páginas**.
5. **Compatibilidad del tema:** Aunque el módulo utiliza hooks estándar de PrestaShop, los temas muy personalizados a veces pueden interferir. Si los pasos anteriores no funcionan, cambie temporalmente al tema predeterminado de PrestaShop para ver si aparece la pestaña. Si lo hace, su tema podría requerir un pequeño ajuste.

**P: ¿Puedo tener diferentes pestañas CMS para diferentes productos?**
R: Este módulo está diseñado para mostrar *una página CMS específica* como pestaña en *todas* las páginas de producto. No admite la asignación de diferentes páginas CMS a productos individuales. Si necesita pestañas específicas del producto, normalmente necesitaría un módulo más avanzado o un desarrollo personalizado.

**P: El contenido de la pestaña se ve extraño o sin estilo.**
R: El módulo simplemente extrae el contenido de su página CMS. El estilo de este contenido suele ser manejado por el CSS de su tema de PrestaShop.

1. **Verifique el contenido de la página CMS:** Asegúrese de que el contenido de su página CMS original (en **Diseño > Páginas**) esté formateado correctamente y no contenga HTML roto.
2. **CSS del tema:** El CSS de su tema podría no tener estilos específicos para el contenido dentro de las pestañas del producto, o podría estar anulando los estilos predeterminados. Si tiene un desarrollador web, puede inspeccionar la página para identificar y solucionar cualquier conflicto de estilo.

**P: Actualicé mi página CMS, pero el contenido de la pestaña en las páginas de producto no ha cambiado.**
R: Después de actualizar una página CMS, siempre borre la caché de PrestaShop (**Parámetros avanzados > Rendimiento > Borrar caché**). Su tienda podría estar sirviendo una versión anterior en caché del contenido.

**P: ¿Cómo traduzco el título de la pestaña si mi tienda es multilingüe?**
R: El título de la pestaña se toma automáticamente del título de la página CMS seleccionada. Para traducirlo, debe editar la propia página CMS (**Diseño > Páginas**) y proporcionar traducciones para su título y contenido para cada idioma que admita. El módulo mostrará entonces el título traducido correcto según el idioma seleccionado por el cliente.

## 4. Guía para desarrolladores y webmasters (Arquitectura técnica y mapa de código)

Esta sección es estrictamente para desarrolladores, webmasters de tiendas y agencias técnicas que mantienen o extienden la tienda.

### 4.1 Resumen de la arquitectura

El módulo "Pestaña CMS en página de producto" (`cmstab`) es un módulo ligero de PrestaShop diseñado para inyectar contenido de páginas CMS existentes en las páginas de producto como una nueva pestaña. Principalmente aprovecha el sistema de hooks de PrestaShop para lograr esto. La lógica central del módulo reside en su archivo PHP principal, `cmstab.php`, que maneja la instalación, desinstalación, configuración y registro de hooks. No introduce tablas de base de datos personalizadas ni ObjectModels complejos, sino que se basa en la clase `CMS` nativa de PrestaShop para la recuperación de contenido. El módulo proporciona dos conjuntos de plantillas para garantizar la compatibilidad con los mecanismos de renderizado de pestañas de PrestaShop 1.6 y 1.7+, seleccionables a través de la configuración del back-office.

### 4.2 Controladores (`controllers/`)

Este módulo no introduce ningún controlador de Front-Office o Back-Office Admin personalizado. Toda la funcionalidad se gestiona a través de la clase principal del módulo y el sistema de hooks de PrestaShop.

### 4.3 Clases y modelos principales (`classes/`)

Este módulo no introduce ninguna clase o Modelo de Objeto personalizado en el directorio `classes/`. Utiliza directamente la clase `CMS` principal de PrestaShop para obtener contenido basado en el ID de la página CMS configurada.

### 4.4 Activos JavaScript (`views/js/`)

- **`cmstab/trusted.js`**
  - **Alcance:** Back-office (página de configuración del módulo).
  - **Propósito:** Este script se incluye típicamente en los módulos de MyPresta.eu para manejar la funcionalidad de "Actualizaciones en vivo de MyPresta.eu". Se comunica con la API de MyPresta.eu para buscar nuevas versiones del módulo y mostrar notificaciones de actualización dentro del back office de PrestaShop. No afecta la visualización del front-office ni la interacción del cliente.

### 4.5 Hojas de estilo CSS (`views/css/`)

Este módulo no incluye ningún archivo CSS personalizado. El estilo de la pestaña y su contenido se hereda del tema activo de PrestaShop. Los desarrolladores que deseen estilizar la pestaña deben apuntar a los selectores apropiados proporcionados por el tema o el sistema de pestañas principal de PrestaShop.

### 4.6 Estructura de plantillas Smarty (`views/templates/`)

El módulo proporciona dos conjuntos de plantillas para adaptarse a los diferentes enfoques de renderizado de pestañas de las versiones de PrestaShop. El conjunto específico utilizado se determina mediante la configuración "Tipo de pestaña" en la configuración del módulo.

- **Plantillas de hook (`views/templates/hook/`)**: Este directorio no se utiliza explícitamente para la renderización directa de hooks en este módulo. Las plantillas se referencian directamente desde `views/front/`.
- **Plantillas de front-office (`views/templates/front/`)**:

  - **`cmstab/views/front/tab.tpl`**

    - **Propósito:** Esta plantilla está diseñada para la compatibilidad con PrestaShop 1.6. Se renderiza cuando el "Tipo de pestaña" se establece en "PrestaShop 1.6". Genera el HTML para el *encabezado* de la pestaña (la parte clicable de la pestaña) utilizando el título de la página CMS.
    - **Hook:** `productTab` (específico de PrestaShop 1.6)
    - **Variables:** `$cmstab_title` (el título de la página CMS seleccionada).
  - **`cmstab/views/front/tab16.tpl`**

    - **Propósito:** Esta plantilla también es para la compatibilidad con PrestaShop 1.6. Genera el HTML para el área de *contenido* de la pestaña, mostrando el contenido real de la página CMS seleccionada.
    - **Hook:** `productTabContent` (específico de PrestaShop 1.6)
    - **Variables:** `$cmstab_content` (el contenido HTML de la página CMS seleccionada).
  - **`cmstab/views/front/tabcontents.tpl`**

    - **Propósito:** Esta plantilla es para la compatibilidad con PrestaShop 1.7, 8.x y 9.x. Se renderiza cuando el "Tipo de pestaña" se establece en "PrestaShop 1.7 / 8.x / 9.x". Genera toda la estructura de la pestaña, incluyendo tanto el encabezado de la pestaña como su contenido, como se espera del hook `displayProductExtraContent`.
    - **Hook:** `displayProductExtraContent` (estándar de PrestaShop 1.7+)
    - **Variables:**
      - `$cmstab_title`: El título de la página CMS seleccionada.
      - `$cmstab_content`: El contenido HTML de la página CMS seleccionada.
      - `$cmstab_id`: Un ID único para la pestaña, derivado del ID de la página CMS.
  - **`cmstab/views/front/tabcontents16.tpl`**

    - **Propósito:** Esta plantilla parece ser una versión redundante o alternativa de `tab16.tpl` o `tabcontents.tpl`, probablemente para escenarios específicos de 1.6 o una implementación anterior. Dada la lógica actual del módulo, `tabcontents.tpl` se utiliza para 1.7+ y `tab.tpl`/`tab16.tpl` para 1.6. Los desarrolladores deben centrarse principalmente en `tabcontents.tpl` para las versiones modernas de PrestaShop.

### 4.7 Esquema de la base de datos y mapa de hooks

- **Tablas de la base de datos**:

  - Este módulo no crea ninguna tabla de base de datos personalizada.
  - Almacena sus ajustes de configuración en la tabla `ps_configuration` de PrestaShop:
    - `CMSTAB_ID`: Almacena el ID de la página CMS seleccionada.
    - `CMSTAB_TYPE`: Almacena el tipo de pestaña seleccionada (por ejemplo, '17' para PrestaShop 1.7+, '16' para PrestaShop 1.6).
    - `MYPRESTA_UPDATES`: Almacena el ajuste para las actualizaciones en vivo.
- **Tabla de Hooks registrados**:

| Nombre del Hook | Momento de ejecución | Propósito técnico |
| --- | --- | --- |
| `displayHeader` | En la sección `<head>` de cada página. | Utilizado por el módulo para registrar su JavaScript para actualizaciones en vivo en el back office. |
| `displayBackOfficeHeader` | En la sección `<head>` de cada página del back-office. | Utilizado por el módulo para registrar su JavaScript para actualizaciones en vivo en el back office. |
| `displayProductExtraContent` | En las páginas de producto, para añadir nuevas pestañas (PrestaShop 1.7+). | Hook principal para renderizar la pestaña CMS y su contenido en las versiones modernas de PrestaShop. |
| `productTab` | En las páginas de producto, para añadir nuevos encabezados de pestaña (PrestaShop 1.6). | Utilizado para la compatibilidad con versiones anteriores para renderizar el encabezado de la pestaña en PrestaShop 1.6. |
| `productTabContent` | En las páginas de producto, para añadir nuevo contenido de pestaña (PrestaShop 1.6). | Utilizado para la compatibilidad con versiones anteriores para renderizar el contenido de la pestaña en PrestaShop 1.6. |
| `actionAdminControllerSetMedia` | Cuando un controlador de administración establece sus activos multimedia. | Utilizado por el módulo para registrar su JavaScript para actualizaciones en vivo en el back office. |

## 5. Soporte oficial y actualizaciones

Para las últimas actualizaciones del módulo, correcciones de errores y soporte profesional, consulte su cuenta de cliente en [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nuestro equipo se dedica a proporcionar asistencia oportuna y garantizar el rendimiento óptimo de sus módulos.
