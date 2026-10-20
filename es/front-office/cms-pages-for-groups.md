---
title: "Páginas CMS para grupos - Manual de Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop 'Páginas CMS para grupos' de MyPresta.eu."
sidebar:
  label: "Páginas CMS para grupos - Manual de Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo CMS pages for groups en MyPresta.eu](https://mypresta.eu/modules/front-office-features/cms-pages-for-groups.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/front-office/cms-pages-for-groups/)
>
> ---


# Páginas CMS para grupos

## 1. Requisitos y Compatibilidad

- **Versiones de PrestaShop Compatibles**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilidad PHP**: PHP 5.6 - 8.5
- **Requisitos de Alojamiento**: Extensiones PHP estándar (cURL, JSON, OpenSSL).

## 2. Recorrido Completo por la Configuración (Cada Ajuste Agrupado por Pantalla)

### 2.1 Página de Configuración del Módulo (Back Office > Módulos > Configurar > Páginas CMS para grupos)

Esta es la pantalla de configuración principal donde gestionará qué grupos de clientes pueden acceder a páginas CMS específicas.

Cuando acceda por primera vez a la página de configuración, verá una lista de todas sus páginas CMS existentes. Para cada página CMS, encontrará opciones para controlar su visibilidad.

**Estructura General de la Página:**
La página de configuración muestra una tabla. Cada fila de la tabla representa una de sus páginas CMS. Para cada página CMS, verá:

-   **Nombre de la Página:** El título de su página CMS (por ejemplo, "Sobre Nosotros", "Términos y Condiciones").
-   **Grupos de Clientes:** Una lista de casillas de verificación, una para cada grupo de clientes definido en su tienda PrestaShop (por ejemplo, "Visitante", "Invitado", "Cliente", "Mayorista").

**Qué hace esta configuración:**
Para cada página CMS, usted selecciona los grupos de clientes a los que se les **permite** ver esa página específica. Si un cliente no forma parte de ninguno de los grupos seleccionados para una página determinada, se le denegará el acceso a esa página.

**Efecto de cambiar esta configuración:**

-   **Cuando se marca un grupo para una página CMS:** Los clientes que pertenecen a este grupo podrán ver la página CMS normalmente.
-   **Cuando se desmarca un grupo para una página CMS:** Los clientes que pertenecen a este grupo **no** podrán ver la página CMS. Si intentan acceder a ella, serán redirigidos a un error de "Página no encontrada".
-   **Si no se selecciona ningún grupo para una página CMS:** Esto significa que la página está efectivamente oculta para *todos* los clientes, ya que ningún grupo tiene permiso para verla. Esto podría ser útil para páginas en construcción o contenido solo interno.
-   **Si se seleccionan todos los grupos para una página CMS:** Esto significa que la página es visible para todos, volviendo efectivamente al comportamiento predeterminado de PrestaShop para esa página específica.

**Valor recomendado:**
Esto depende completamente de sus necesidades comerciales.

-   Para páginas estándar como "Sobre Nosotros" o "Contáctenos", probablemente marcará todos los grupos.
-   Para términos legales específicos para B2B, podría marcar solo su grupo "Mayorista".
-   Para una página de "Beneficios del Club VIP", podría marcar solo su grupo "Cliente VIP".

**Escenario / ejemplo de comerciante:**
Supongamos que tiene tres grupos de clientes: "Visitante" (no conectado), "Cliente" (usuarios registrados estándar) y "Mayorista" (clientes B2B).

1.  **Escenario 1: Página "Sobre Nosotros"**

    -   **Propósito:** Información general para todos.
    -   **Acción:** Marque "Visitante", "Cliente" y "Mayorista" para la página "Sobre Nosotros".
    -   **Resultado:** Todos pueden ver la página "Sobre Nosotros".
2.  **Escenario 2: Página "Términos y Condiciones Mayoristas"**

    -   **Propósito:** Términos legales específicos solo para sus clientes B2B.
    -   **Acción:** Marque solo "Mayorista" para la página "Términos y Condiciones Mayoristas".
    -   **Resultado:** Solo los clientes del grupo "Mayorista" pueden ver esta página. A los grupos "Visitante" y "Cliente" se les denegará el acceso.
3.  **Escenario 3: Página "Detalles del Programa de Lealtad"**

    -   **Propósito:** Información para clientes registrados sobre sus puntos de lealtad.
    -   **Acción:** Marque "Cliente" y "Mayorista" (asumiendo que los clientes mayoristas también pueden formar parte del programa de lealtad) para la página "Detalles del Programa de Lealtad".
    -   **Resultado:** Solo los clientes conectados (estándar o mayoristas) pueden ver esta página. A los visitantes se les denegará el acceso.

**Guardar Sus Cambios:**
Después de hacer sus selecciones para todas las páginas CMS, recuerde hacer clic en el botón **"Guardar"** (generalmente en la parte inferior de la página) para aplicar sus cambios.

### 2.2 Tabla de Referencia Rápida de Configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| Página de Configuración del Módulo | **Nombre de la Página CMS** (ej., "Sobre Nosotros") | Varía según la página | Controla qué grupos de clientes pueden ver esta página CMS específica. |
| | Casilla de verificación para el grupo **"Visitante"** | Varía | Si está marcada, los usuarios no conectados pueden ver la página. |
| | Casilla de verificación para el grupo **"Invitado"** | Varía | Si está marcada, los usuarios que compraron como invitados pueden ver la página. |
| | Casilla de verificación para el grupo **"Cliente"** | Varía | Si está marcada, los clientes registrados estándar pueden ver la página. |
| | Casilla de verificación para el grupo **"Mayorista"** (o cualquier grupo personalizado) | Varía | Si está marcada, los clientes de este grupo específico pueden ver la página. |
| | **Botón Guardar** | N/A | Aplica todas las configuraciones de visibilidad seleccionadas a las páginas CMS. |

## 3. Solución de Problemas del Comerciante y Preguntas Frecuentes (FAQ)

**P1: He restringido una página CMS, pero sigue apareciendo en el menú de mi pie de página/encabezado. ¿Por qué?**
R1: Este módulo controla el *acceso* al contenido de la página, no su visibilidad en los menús de navegación. Si desea ocultar el enlace en sí a ciertos grupos, deberá:
\* Eliminar manualmente el enlace de los archivos de plantilla de su tema (por ejemplo, `footer.tpl`, `header.tpl`).
\* Utilizar un módulo de gestión de menús que ofrezca visibilidad basada en grupos para los elementos del menú.
\* Si un cliente hace clic en un enlace restringido, se le denegará el acceso al contenido de la página.

**P2: Un cliente ha iniciado sesión, pero aún no puede ver una página que he permitido para su grupo. ¿Qué pasa?**
R2:
\* **Borrar Caché:** Siempre comience borrando la caché de su PrestaShop. Vaya a **Parámetros Avanzados > Rendimiento** y haga clic en "Borrar caché" (o "Borrar caché de Smarty" en versiones anteriores).
\* **Verificar Asignación de Grupo:** Verifique que el cliente esté realmente asignado al grupo(s) de clientes correcto(s) que ha permitido para la página CMS. Puede verificar esto en **Clientes > Clientes** editando el perfil del cliente.
\* **Configuración del Módulo:** Vuelva a la página de configuración del módulo y asegúrese de que la casilla de verificación del grupo correcto esté marcada para esa página CMS específica.
\* **Caché del Navegador:** Pida al cliente que borre la caché de su navegador o que intente acceder a la página en una ventana de incógnito/privada.

**P3: ¿Puedo mostrar un mensaje personalizado en lugar de un error de "Página no encontrada" cuando se deniega el acceso?**
R3: Este módulo, en su versión actual, redirige a la página estándar de PrestaShop "Página no encontrada". Personalizar esto requeriría modificaciones del tema o un módulo adicional que maneje específicamente páginas de error personalizadas basadas en la denegación de acceso.

**P4: ¿Este módulo ralentizará mi tienda?**
R4: No, el módulo es muy ligero. Sobrescribe un controlador central de PrestaShop para verificar los permisos del grupo de clientes antes de cargar una página CMS. Esta verificación es eficiente y no debería afectar notablemente el rendimiento de su tienda.

**P5: He actualizado PrestaShop y ahora el módulo no funciona. ¿Qué debo hacer?**
R5:
\* **Verificar Versión del Módulo:** Asegúrese de tener la última versión del módulo "Páginas CMS para grupos" de su cuenta MyPresta.eu, compatible con su nueva versión de PrestaShop.
\* **Reinstalar/Reconfigurar:** A veces, después de una actualización importante de PrestaShop, los módulos pueden necesitar ser reinstalados o reconfigurados. Intente desinstalar y luego reinstalar el módulo (sus configuraciones deberían conservarse, pero siempre haga una copia de seguridad primero). Luego, vuelva a verificar sus configuraciones en la página de configuración del módulo.
\* **Borrar Caché:** Siempre borre la caché de su PrestaShop después de cualquier actualización o cambio de módulo.

## 4. Guía para Desarrolladores y Webmasters (Arquitectura Técnica y Mapa de Código)

### 4.1 Resumen de la Arquitectura

El módulo "Páginas CMS para grupos" funciona sobrescribiendo el `CmsController` central en el front office de PrestaShop. Esto le permite interceptar las solicitudes de páginas CMS *antes* de que se rendericen y aplicar lógica de acceso personalizada basada en los permisos de grupo de clientes configurados en el back office del módulo. El módulo almacena su configuración directamente en la tabla `ps_configuration`.

### 4.2 Controladores (`controllers/`)

-   **Controladores de Front-Office**:

    -   `groupscms/override/controllers/front/CmsController.php`
        -   **Nombre de la clase y clase padre**: `CmsController` (sobrescribe el `CmsController` central)
        -   **Responsabilidad**: Este es el componente crítico. Extiende el `CmsController` original para añadir un método `init()`. Dentro de `init()`, recupera el ID de la página CMS actual y verifica la configuración del módulo (`Configuration::get('CMSG_CMS_ID_' . (int)$cms->id)`) para determinar qué grupos de clientes tienen acceso permitido. Si el cliente actual (o visitante) no está en un grupo permitido, lo redirige a la página "Página no encontrada" (`$this->redirect_after = '404';`). Esto asegura que los usuarios no autorizados no puedan ver contenido CMS restringido.
-   **Controladores de Administración de Back-Office**: Ninguno. La configuración del módulo se maneja directamente dentro del método `getContent()` del archivo principal del módulo.

### 4.3 Clases y Modelos Centrales (`classes/`)

Ninguno. El módulo no define clases `ObjectModel` personalizadas. Interactúa directamente con los objetos `CMS` y `Group` existentes de PrestaShop y almacena su configuración en `ps_configuration`.

### 4.4 Activos JavaScript (`views/js/`)

Ninguno. El módulo no incluye ningún archivo JavaScript personalizado.

### 4.5 Hojas de Estilo CSS (`views/css/`)

-   `groupscms/css.css`
    -   **Alcance**: Estilo del formulario de administración del back-office.
    -   **Principales componentes de la interfaz de usuario y contenedores que estiliza**: Esta hoja de estilo se utiliza probablemente para estilizar la tabla de configuración del módulo en el back office de PrestaShop, asegurando que se vea consistente con el tema de administración de PrestaShop. Podría definir estilos para las filas de la tabla, casillas de verificación o etiquetas dentro del formulario de configuración del módulo.
    -   **Selectores de clase CSS clave que los desarrolladores pueden sobrescribir en su tema**: Los selectores específicos se encontrarían dentro del archivo, pero típicamente apuntarían a elementos dentro de la salida de `getContent()` del módulo, como `table.groupscms_table`, `tr.groupscms_row`, `input[type="checkbox"].groupscms_checkbox`, etc.

### 4.6 Estructura de Plantillas Smarty (`views/templates/`)

-   **Plantillas de hook (`views/templates/hook/`)**: Ninguna. El módulo no renderiza contenido a través de hooks estándar del front-office.
-   **Plantillas de administración (`views/templates/admin/`)**:

    -   `groupscms/admin.tpl`
        -   **Propósito**: Esta plantilla es renderizada por el método `getContent()` del archivo principal del módulo (`groupscms.php`). Genera toda la interfaz de configuración para el módulo en el back office de PrestaShop. Esto incluye la tabla que lista todas las páginas CMS y las casillas de verificación para cada grupo de clientes.
    -   `groupscms/cms.tpl`
        -   **Propósito**: Esta plantilla es probablemente una inclusión o un parcial utilizado dentro de `admin.tpl` para renderizar filas o secciones individuales relacionadas con las páginas CMS dentro de la tabla de configuración. Contendría el bucle para mostrar cada página CMS y sus casillas de verificación de grupo asociadas.
-   **Plantillas de front-office (`views/templates/front/`)**: Ninguna. El módulo no añade nuevas plantillas de front-office. Controla el acceso a las plantillas de páginas CMS existentes.

### 4.7 Esquema de Base de Datos y Mapa de Hooks

-   **Tablas de Base de Datos**:
    El módulo no crea ninguna tabla SQL personalizada. Todos los datos de configuración se almacenan en la tabla `ps_configuration`.

    -   **Claves de Configuración**:
        -   `CMSG_CMS_ID_[CMS_ID]`: Almacena una cadena de valores `group_id` separados por comas para cada página CMS. Por ejemplo, `CMSG_CMS_ID_12` podría almacenar `"1,2,3"` indicando que los grupos con IDs 1, 2 y 3 tienen acceso a la página CMS con ID 12.
        -   `groupscms_many_page`: (Probablemente una bandera interna o configuración heredada, no directamente configurable por el usuario).
        -   `mypresta_updates`, `update_`, `updatev_`: Estas son claves comunes utilizadas por los módulos de MyPresta.eu para comprobaciones de actualización y seguimiento de versiones.
-   **Tabla de Hooks Registrados**:

| Nombre del Hook | Momento de Ejecución | Propósito Técnico |
| --- | --- | --- |
| `actionAdminControllerSetMedia` | Se ejecuta cuando un Controlador de Administración está configurando sus medios (CSS/JS). | Utilizado por el módulo para incluir su hoja de estilo `css.css` para la página de configuración del back-office. |
| `displayBackOfficeHeader` | Se ejecuta en la sección `<head>` del Back Office. | A menudo se utiliza para incluir CSS/JS de administración global o para comprobaciones de actualización. El módulo podría usar esto para su mecanismo de actualización. |

## 5. Soporte Oficial y Actualizaciones

Para actualizaciones oficiales, soporte técnico y para descargar las últimas versiones del módulo "Páginas CMS para grupos", visite su cuenta de cliente en [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nuestro equipo de soporte está disponible para ayudarle con cualquier problema o pregunta que pueda tener.
