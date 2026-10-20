---
title: "Acceso Rápido - URLs externas - Manual del Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop Acceso Rápido - URLs externas de MyPresta.eu."
sidebar:
  label: "Acceso Rápido - URLs externas - Manual del Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Quick Access - external urls en MyPresta.eu](https://mypresta.eu/modules/administration-tools/quick-access-external-urls.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/back-office-tools/quick-access-external-urls/)
>
> ---


# Acceso Rápido - URLs externas

## 1. Requisitos y Compatibilidad

- **Versiones de PrestaShop Compatibles**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilidad con PHP**: PHP 7.1 - 8.5
- **Requisitos de Alojamiento**: Extensiones PHP estándar (cURL, JSON, OpenSSL).

## 2. Recorrido Completo por la Configuración (Cada Ajuste Agrupado por Pantalla)

Este módulo se integra directamente con el sistema de gestión de Acceso Rápido existente de PrestaShop. No hay una pantalla de configuración separada para el módulo en sí. En su lugar, modifica el comportamiento de la función predeterminada de "Acceso Rápido" en su Back Office.

### 2.1 Página de Configuración del Módulo (Back Office > Módulos > Configurar)

Cuando haga clic en "Configurar" para el módulo "Acceso Rápido - URLs externas", normalmente verá una simple confirmación de que el módulo está instalado y activo. No hay ajustes específicos que ajustar en esta página, ya que el módulo funciona anulando el comportamiento central de PrestaShop.

### 2.2 Pantallas de Administración Dedicadas y Vistas de Controlador

La funcionalidad del módulo se gestiona a través del menú estándar de Acceso Rápido de PrestaShop.

**Nombre de la Pantalla y Ubicación del Menú:**

- **Back Office > Administración > Acceso Rápido** (o **Configurar > Parámetros Avanzados > Acceso Rápido** en versiones antiguas de PrestaShop 1.7.x).
- También puede acceder directamente desde el propio menú de Acceso Rápido (el pequeño icono del reloj en la parte superior de su Back Office), haciendo clic en "Gestionar Acceso Rápido".

**Acciones y Ajustes Disponibles:**
En esta pantalla, verá una lista de sus enlaces de Acceso Rápido existentes.

- **Añadir un nuevo enlace de Acceso Rápido:**

  1.  Haga clic en el botón **"Añadir nuevo acceso rápido"** (o similar, generalmente un icono de más).
  2.  Verá un formulario con campos como:
      -   **Nombre:** El texto que aparecerá en su menú de Acceso Rápido (por ejemplo, "Portal de Envíos DHL", "Panel de Stripe", "Google Analytics").
      -   **URL:** Este es el campo crucial. **Con este módulo instalado, ahora puede introducir CUALQUIER URL válida aquí, incluyendo sitios web externos.** Por ejemplo:
          -   `https://www.dhl.com/global-en/home/tracking.html`
          -   `https://dashboard.stripe.com/`
          -   `https://analytics.google.com/`
          -   `https://mypresta.eu/`
      -   **Abrir en una nueva ventana:** (Recomendado: SÍ) Esta opción determina si el enlace se abre en una nueva pestaña/ventana del navegador.
          -   *Cuando está habilitado:* El enlace externo se abrirá en una nueva pestaña, manteniendo su Back Office de PrestaShop abierto en la pestaña actual. Esto generalmente se recomienda para enlaces externos para evitar navegar fuera de su panel de administración.
          -   *Cuando está deshabilitado:* El enlace se abrirá en la misma pestaña, reemplazando la vista de su Back Office de PrestaShop.
  3.  Haga clic en **"Guardar"**.
-   **Editar un enlace de Acceso Rápido existente:**

    1.  Encuentre el enlace en la lista y haga clic en el icono "Editar" (lápiz).
    2.  Modifique el Nombre o la URL según sea necesario.
    3.  Haga clic en "Guardar".
-   **Eliminar un enlace de Acceso Rápido:**

    1.  Encuentre el enlace en la lista y haga clic en el icono "Eliminar" (papelera).
    2.  Confirme la eliminación.

**Efecto de los cambios:**

-   Cualquier enlace de Acceso Rápido que añada, edite o elimine en esta pantalla se reflejará inmediatamente en el menú de Acceso Rápido (el icono del reloj) en la parte superior de su Back Office de PrestaShop.
-   Cuando haga clic en un enlace de Acceso Rápido que apunte a una URL externa, su navegador navegará a ese sitio externo (ya sea en la misma pestaña o en una nueva, dependiendo de su configuración de "Abrir en una nueva ventana").

**Flujo de trabajo recomendado para la gestión diaria de la tienda:**

1.  **Identifique las herramientas externas de uso frecuente:** Piense en los sitios web que visita diaria o semanalmente para gestionar su tienda (por ejemplo, envíos, pagos, marketing, soporte, portales de proveedores).
2.  **Añádalos a Acceso Rápido:** Vaya a **Administración > Acceso Rápido** y añada cada URL externa con un nombre claro y descriptivo.
3.  **Habilite "Abrir en una nueva ventana":** Para todos los enlaces externos, establezca "Abrir en una nueva ventana" en SÍ. Esto asegura que su Back Office de PrestaShop permanezca abierto y accesible.
4.  **Organice para su equipo:** Si tiene varios usuarios administradores, considere qué enlaces rápidos serían más beneficiosos para cada rol.

### 2.3 Tabla de Referencia Rápida de Configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| **Back Office > Administración > Acceso Rápido** | **Nombre** | Definido por el usuario | Texto mostrado en el menú de Acceso Rápido. |
| | **URL** | Definido por el usuario (URL externa) | La dirección web a la que apunta el enlace. **Este módulo habilita URLs externas aquí.** |
| | **Abrir en una nueva ventana** | SÍ (para enlaces externos) | Determina si el enlace se abre en una nueva pestaña/ventana del navegador. |

## 3. Solución de Problemas del Comerciante y Preguntas Frecuentes (FAQ)

**P1: He instalado el módulo, pero sigo sin poder añadir URLs externas a Acceso Rápido. ¿Qué ocurre?**
R1:

-   **Borrar Caché:** Después de la instalación, siempre borre la caché de PrestaShop. Vaya a **Parámetros Avanzados > Rendimiento** y haga clic en "Borrar caché" en la parte superior derecha.
-   **Verificar Estado del Módulo:** Asegúrese de que el módulo esté habilitado. Vaya a **Módulos > Gestor de Módulos**, busque "Acceso Rápido - URLs externas" y verifique que esté activo.
-   **Verificar Instalación:** A veces, una instalación puede fallar silenciosamente. Intente desinstalar y reinstalar el módulo.
-   **Caché del Navegador:** Borre la caché y las cookies de su navegador, o intente acceder al Back Office en una ventana de incógnito/privada.

**P2: Mis enlaces de Acceso Rápido se abren en la misma pestaña, incluso para sitios externos. ¿Cómo lo soluciono?**
R2:

-   Al añadir o editar un enlace de Acceso Rápido, asegúrese de que la opción **"Abrir en una nueva ventana"** esté configurada en **SÍ**. Esta configuración controla si el enlace se abre en una nueva pestaña o en la actual.

**P3: ¿Este módulo afectará el rendimiento o el SEO de mi tienda?**
R3:

-   No. Este módulo opera completamente dentro del Back Office de PrestaShop. No añade ningún código, estilo o funcionalidad al front office de su tienda (lo que ven los clientes). Por lo tanto, no tiene impacto en la velocidad de carga de su tienda, el SEO o la experiencia del cliente.

**P4: He añadido muchos enlaces de Acceso Rápido. ¿Puedo organizarlos?**
R4:

-   La función de Acceso Rápido predeterminada de PrestaShop no ofrece una organización avanzada como carpetas o categorías. Sin embargo, puede controlar el orden de los enlaces arrastrándolos y soltándolos en la página **Administración > Acceso Rápido**. También puede usar nombres descriptivos para que sean fáciles de identificar.

**P5: ¿Qué pasa si desinstalo este módulo? ¿Desaparecerán mis enlaces de Acceso Rápido externos?**
R5:

-   Si desinstala este módulo, se eliminará la capacidad de añadir *nuevas* URLs externas. Las URLs externas existentes que añadió mientras el módulo estaba activo *podrían* seguir funcionando, pero la validación central de PrestaShop podría impedir que se editen o podría causar problemas. Es mejor mantener el módulo instalado si depende de los enlaces de Acceso Rápido externos.

## 4. Guía para Desarrolladores y Webmasters (Arquitectura Técnica y Mapa de Código)

### 4.1 Resumen de la Arquitectura

El módulo "Acceso Rápido - URLs externas" (`qae`) logra su funcionalidad anulando las clases y controladores centrales de PrestaShop. Específicamente, se dirige al `ObjectModel` `QuickAccess` y al `AdminQuickAccessesController` para eliminar la validación que restringe las URLs de Acceso Rápido a rutas internas del Back Office. Este es un patrón común de anulación de PrestaShop.

### 4.2 Controladores (`controllers/`)

-   **Controladores de Front-Office**: Este módulo no incluye ningún controlador de front-office ya que su funcionalidad es exclusivamente para el Back Office.
-   **Controladores de Administración del Back-Office**:

    -   **`qae/override/controllers/admin/AdminQuickAccessesController.php`**
        -   **Nombre de la Clase**: `AdminQuickAccessesController` (anula el `AdminQuickAccessesController` central)
        -   **Clase Padre**: `AdminController`
        -   **Responsabilidad**: Esta anulación es crucial. El `AdminQuickAccessesController` original contiene lógica para validar el campo `url` de una entrada de Acceso Rápido, asegurando que sea una ruta interna del Back Office de PrestaShop. Esta anulación modifica o elimina esa validación, permitiendo que se guarden URLs externas. Los desarrolladores deben inspeccionar los métodos `postProcess()` o `renderForm()` para ver los cambios específicos relacionados con la validación de URL.

### 4.3 Clases y Modelos Centrales (`classes/`)

-   **`qae/override/classes/index.php`**

    -   Este es típicamente un archivo vacío o un archivo que contiene solo `<?php exit; ?>` para evitar la lista directa de directorios. Es una medida de seguridad y no forma parte de la lógica central del módulo.
-   **`qae/override/classes/Link.php`**

    -   **Nombre de la Clase**: `Link` (anula la clase `Link` central)
    -   **Clase Padre**: `LinkCore`
    -   **Responsabilidad**: La clase `Link` es responsable de generar URLs en PrestaShop. Si bien el cambio principal para las URLs externas está en `QuickAccess` y `AdminQuickAccessesController`, una anulación de `Link` podría estar presente para asegurar que cualquier método de generación o validación de URL interna en el que `QuickAccess` confíe sea compatible con la nueva permisión de URL externa, o para evitar efectos secundarios no deseados. Los desarrolladores deben buscar modificaciones en los métodos relacionados con la validación o sanitización de URL.
-   **`qae/override/classes/QuickAccess.php`**

    -   **Nombre de la Clase**: `QuickAccess` (anula el `ObjectModel` `QuickAccess` central)
    -   **Clase Padre**: `ObjectModel`
    -   **Tabla de Base de Datos**: `ps_quick_access`
    -   Campos de `$definition`: Esta clase define la estructura de una entrada de Acceso Rápido, incluyendo `id_quick_access`, `name`, `url` y `new_window`.
    -   **Métodos Públicos Clave y Lógica de Negocio**: Esta anulación es fundamental. El `ObjectModel` `QuickAccess` original probablemente incluye reglas de validación para el campo `url` dentro de sus métodos `validateFields()` o `add()`/`update()`. Esta anulación elimina o relaja esas reglas de validación, permitiendo que el campo `url` almacene cualquier cadena, incluyendo URLs externas, sin activar errores de validación.

### 4.4 Activos JavaScript (`views/js/`)

Este módulo no incluye ningún archivo JavaScript personalizado. Los cambios son puramente del lado del servidor (anulaciones de PHP).

### 4.5 Hojas de Estilo CSS (`views/css/`)

Este módulo no incluye ningún archivo CSS personalizado. La presentación visual del menú de Acceso Rápido es manejada por el tema predeterminado del Back Office de PrestaShop.

### 4.6 Estructura de Plantillas Smarty (`views/templates/`)

Este módulo no incluye ningún archivo de plantilla Smarty personalizado. Aprovecha las plantillas existentes del Back Office de PrestaShop para renderizar la página de gestión de Acceso Rápido y el propio menú de Acceso Rápido.

### 4.7 Esquema de Base de Datos y Mapa de Hooks

-   **Tablas de Base de Datos**:

    -   Este módulo no crea ninguna tabla de base de datos nueva. Modifica el comportamiento de cómo se almacenan y validan los datos para la tabla `ps_quick_access` existente.
    -   Los registros de configuración no se almacenan en `ps_configuration` por este módulo, ya que se basa principalmente en anulaciones de clases/controladores.
-   **Tabla de Hooks Registrados**:
    Este módulo no registra ningún hook específico en el sentido tradicional (por ejemplo, `displayHeader`, `actionValidateOrder`). Su funcionalidad se implementa a través del sistema de anulación de PrestaShop, que modifica directamente las clases y controladores centrales en lugar de inyectar código a través de hooks.

## 5. Soporte Oficial y Actualizaciones

Para las últimas actualizaciones, correcciones de errores y soporte oficial para el módulo "Acceso Rápido - URLs externas", consulte su cuenta de cliente en [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nuestro equipo de soporte está disponible para ayudar con cualquier problema técnico o pregunta que pueda tener.
