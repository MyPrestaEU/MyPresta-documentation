---
title: "Bloquear dirección IP Pro - Manual de Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop Bloquear dirección IP Pro de MyPresta.eu."
sidebar:
  label: "Bloquear dirección IP Pro"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Block IP address Pro en MyPresta.eu](https://mypresta.eu/modules/administration-tools/block-ip-address-pro.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/back-office-tools/block-ip-address-pro/)
>
> ---


# Bloquear dirección IP Pro

## 1. Requisitos y Compatibilidad
- **Versiones de PrestaShop compatibles**: PrestaShop 1.4.x, 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilidad con PHP**: PHP 5.6 - 8.5
- **Requisitos de alojamiento**: Extensiones PHP estándar (cURL, JSON, OpenSSL) típicamente disponibles en cualquier entorno de alojamiento web moderno.

## 2. Recorrido completo por la configuración (Cada ajuste agrupado por pantalla)

### 2.1 Página de configuración del módulo (Back Office > Módulos > Configurar > Bloquear dirección IP Pro)

Esta es la pantalla de configuración principal del módulo, donde se define el comportamiento global para los visitantes bloqueados.

-   **Ubicación del menú:** Back Office > Módulos > Gestor de módulos > Bloquear dirección IP Pro > Configurar

#### Ajustes y opciones:

1.  **Mostrar notificaciones de actualización**
    -   **Qué hace este ajuste:** Controla si recibe notificaciones en su back office de PrestaShop cuando hay una nueva versión del módulo "Bloquear dirección IP Pro" disponible.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando está habilitado:* Verá alertas o mensajes en su panel de administración si se lanza una actualización, lo que le ayudará a mantener su módulo actualizado.
        -   *Cuando está deshabilitado:* No recibirá estas notificaciones y tendrá que buscar actualizaciones manualmente en MyPresta.eu.
    -   **Valor recomendado:** SÍ
    -   **Escenario / ejemplo de comerciante:** Mantener esto habilitado garantiza que siempre esté al tanto de las nuevas funciones, correcciones de errores o mejoras de seguridad para el módulo.

2.  **Mensaje para usuarios bloqueados (`banippro_msg`)**
    -   **Qué hace este ajuste:** Este es el mensaje personalizado que se mostrará a los usuarios cuya dirección IP ha sido bloqueada, *si* elige no redirigirlos.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando está lleno:* Los usuarios bloqueados verán este texto específico en una página en blanco en lugar del contenido de su tienda.
        -   *Cuando está vacío:* Si la redirección también está deshabilitada, los usuarios bloqueados podrían ver un error genérico o una página en blanco sin un mensaje específico.
    -   **Valor recomendado:** "El acceso a esta tienda ha sido denegado para su dirección IP." (o un mensaje similar, educado pero firme).
    -   **Escenario / ejemplo de comerciante:** Es posible que desee mostrar "Lo sentimos, pero el acceso desde su ubicación ha sido restringido debido a actividad inusual" para informar al usuario sin dar demasiados detalles.

3.  **Redirigir usuarios bloqueados (`banippro_redirect`)**
    -   **Qué hace este ajuste:** Determina si a los usuarios bloqueados se les muestra un mensaje o se les envía automáticamente a una página web diferente.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando está habilitado:* Los usuarios bloqueados serán redirigidos inmediatamente a la URL especificada en el ajuste "URL de redirección".
        -   *Cuando está deshabilitado:* Los usuarios bloqueados verán el "Mensaje para usuarios bloqueados" que usted definió.
    -   **Valor recomendado:** SÍ (La redirección suele ser una experiencia de usuario más limpia que una página en blanco con un mensaje).
    -   **Escenario / ejemplo de comerciante:** Si desea alejar a los spammers de su sitio por completo, o dirigir a un cliente problemático a una página de servicio al cliente, habilite esto.

4.  **URL de redirección (`banippro_url`)**
    -   **Qué hace este ajuste:** La dirección web específica (URL) a la que se redirigirá a los usuarios bloqueados si el ajuste "Redirigir usuarios bloqueados" está habilitado.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando se rellena con una URL válida:* Los usuarios bloqueados serán enviados a esta página exacta.
        -   *Cuando está vacío:* Si la redirección está habilitada pero no se proporciona una URL, el comportamiento del módulo podría ser impredecible, o podría mostrar el mensaje por defecto.
    -   **Valor recomendado:** La URL de la página de inicio de su tienda (por ejemplo, `https://www.sutieneda.com/`), o una página específica de "Contacto", o incluso un sitio externo como Google.
    -   **Escenario / ejemplo de comerciante:** Podría redirigirlos a `https://www.sutieneda.com/contactenos` si desea que se pongan en contacto, o a `https://www.google.com` para simplemente eliminarlos de su sitio.

#### Tabla de referencia rápida de configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
|---|---|---|---|
| Configuración del módulo | Mostrar notificaciones de actualización | SÍ | Muestra alertas para nuevas versiones del módulo. |
| Configuración del módulo | Mensaje para usuarios bloqueados | "El acceso a esta tienda ha sido denegado para su dirección IP." | Texto que se muestra a los usuarios bloqueados si no se redirigen. |
| Configuración del módulo | Redirigir usuarios bloqueados | SÍ | Si está habilitado, envía a los usuarios bloqueados a una URL especificada. |
| Configuración del módulo | URL de redirección | La URL de la página de inicio de su tienda | El destino para los usuarios bloqueados redirigidos. |

### 2.2 Pantalla de administración dedicada: Gestión de direcciones IP (Back Office > Módulos > Bloquear dirección IP Pro > Gestionar direcciones IP)

Esta es la pantalla de gestión principal donde se añaden, editan, activan y desactivan direcciones IP específicas para ser bloqueadas.

-   **Ubicación del menú:** Después de instalar el módulo, aparecerá un nuevo elemento de menú en **Módulos > Bloquear dirección IP Pro** (o similar, dependiendo de la versión de PrestaShop y el registro del menú del módulo). Haga clic en "Gestionar direcciones IP" o "Bloquear direcciones IP".

#### Acciones y ajustes disponibles:

1.  **Tabla de listado de direcciones IP:**
    -   Esta tabla muestra todas las direcciones IP que ha configurado para bloquear.
    -   **Columnas:**
        -   **ID:** Identificador único para la entrada de IP bloqueada.
        -   **Dirección IP:** La dirección IP real que se está bloqueando (por ejemplo, `192.168.1.1`, `203.0.113.45`).
        -   **Número de visitas:** Una estadística que muestra cuántas veces esta dirección IP específica ha intentado acceder a su tienda y fue bloqueada. Esto es invaluable para identificar amenazas persistentes.
        -   **Comentario:** Su nota interna sobre por qué se bloqueó esta IP (por ejemplo, "Bot de spam", "Scraping de la competencia", "Cliente problemático").
        -   **Activo:** Un interruptor (Activado/Desactivado) para habilitar o deshabilitar rápidamente el bloqueo de esta IP específica sin eliminar la entrada.
        -   **Acciones:** Botones para "Editar" o "Eliminar" entradas de IP individuales.

2.  **Añadir una nueva dirección IP:**
    -   Haga clic en el botón "Añadir nueva dirección IP" (o similar, generalmente un icono de más o un botón "Añadir nuevo" en la parte superior derecha de la tabla).
    -   **Campos del formulario:**
        -   **IP:** Introduzca la dirección IP exacta que desea bloquear.
        -   **Comentario:** Añada una nota descriptiva para su referencia (por ejemplo, "Fuente de spam conocida de análisis", "Cliente 'Juan Pérez' causando problemas").
        -   **Activo:** Elija "Activado" para activar el bloqueo inmediatamente, o "Desactivado" para guardar la entrada pero mantenerla inactiva por ahora.
    -   **Guardar:** Haga clic en "Guardar" para añadir la nueva IP a su lista de bloqueo.

3.  **Editar una dirección IP existente:**
    -   Haga clic en el icono "Editar" junto a una dirección IP en la tabla de listado.
    -   Puede modificar la "IP", el "Comentario" y el estado "Activo".
    -   **Guardar:** Haga clic en "Guardar" para aplicar sus cambios.

4.  **Eliminar una dirección IP:**
    -   Haga clic en el icono "Eliminar" junto a una dirección IP.
    -   Confirme la eliminación. Esto eliminará permanentemente la IP de su lista de bloqueo.

#### Efecto de los cambios:
-   **Añadir una IP:** Una vez guardada y activa, cualquier visitante que intente acceder a su tienda desde esa dirección IP será bloqueado o redirigido inmediatamente según la configuración global de su módulo.
-   **Editar una IP:** Los cambios en la dirección IP, el comentario o el estado activo surtirán efecto inmediatamente.
-   **Desactivar una IP:** La dirección IP permanece en su lista, pero los visitantes de esa IP ya no serán bloqueados. Esto es útil para bloqueos temporales o si una IP fue bloqueada por error.
-   **Eliminar una IP:** La IP se elimina permanentemente de la lista de bloqueo, y los visitantes de esa IP recuperarán el acceso completo a su tienda.

#### Flujo de trabajo recomendado para la gestión diaria de la tienda:
1.  **Monitorear análisis:** Revise regularmente los análisis de su sitio web en busca de patrones de tráfico sospechosos, altas tasas de rebote de IPs específicas o actividad inusual.
2.  **Identificar IPs problemáticas:** Si encuentra una dirección IP que constantemente causa problemas (por ejemplo, repetidos intentos de inicio de sesión fallidos, raspado excesivo de páginas, comentarios de spam), anótela.
3.  **Añadir a la lista de bloqueo:** Navegue a la pantalla "Gestionar direcciones IP", haga clic en "Añadir nueva dirección IP", introduzca la IP, añada un comentario descriptivo y configúrela como "Activado".
4.  **Revisar estadísticas:** Verifique periódicamente la columna "Número de visitas" para las IPs bloqueadas. Los números altos indican intentos persistentes, confirmando la efectividad de su bloqueo.
5.  **Gestionar y refinar:** Si una dirección IP ya no es una amenaza, puede desactivarla (establecer "Activo" en "Desactivado") o eliminarla por completo.

### 2.3 Tabla de referencia rápida de configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
|---|---|---|---|
| Gestión de direcciones IP | Añadir nueva IP | N/A | Añade una nueva dirección IP a la lista de bloqueo. |
| Gestión de direcciones IP | Dirección IP (Campo) | N/A | La IP específica a bloquear. |
| Gestión de direcciones IP | Comentario (Campo) | N/A | Su nota interna para la IP bloqueada. |
| Gestión de direcciones IP | Activo (Interruptor) | Activado | Habilita/deshabilita el bloqueo para una IP específica. |
| Gestión de direcciones IP | Número de visitas (Columna) | 0 | Rastrea cuántas veces se bloqueó una IP. |
| Gestión de direcciones IP | Acciones de Editar / Eliminar | N/A | Modificar o eliminar entradas de IP bloqueadas existentes. |

## 3. Solución de problemas del comerciante y preguntas frecuentes (FAQ)

**P: He bloqueado una IP, pero el usuario todavía puede acceder a mi tienda. ¿Qué pasa?**
R:
1.  **Verifique el estado "Activo":** Asegúrese de que el interruptor "Activo" para esa IP específica en la pantalla "Gestionar direcciones IP" esté configurado en "Activado".
2.  **Borrar caché:** PrestaShop utiliza caché. Vaya a **Parámetros avanzados > Rendimiento** y haga clic en "Borrar caché" (o "Borrar caché de Smarty" para versiones anteriores). Esto asegura que la configuración del módulo se recargue.
3.  **Verificar dirección IP:** Verifique dos veces que ha introducido la dirección IP correcta. A veces, las IPs dinámicas cambian, o podría tener un problema de proxy/CDN.
4.  **Caché del navegador:** Pida al usuario bloqueado que borre la caché de su navegador o que intente acceder desde una ventana de incógnito.

**P: ¡Mi cliente legítimo está bloqueado! ¿Cómo lo soluciono?**
R:
1.  **Identifique su IP:** Pida al cliente su dirección IP actual (puede encontrarla buscando "cuál es mi IP" en Google).
2.  **Verifique su lista de bloqueo:** Vaya a **Módulos > Bloquear dirección IP Pro > Gestionar direcciones IP** y busque su IP.
3.  **Desactivar o Eliminar:** Si se encuentra, configure el interruptor "Activo" en "Desactivado" para esa entrada o elimínela por completo.
4.  **Borrar caché:** Recuerde borrar la caché de su PrestaShop después.

**P: ¿Puedo bloquear un rango de direcciones IP en lugar de solo una?**
R: La versión actual del módulo admite el bloqueo de direcciones IP individuales. Para bloquear rangos, tendría que introducir cada IP dentro del rango individualmente, o considerar el bloqueo de IP a nivel de servidor si tiene acceso al firewall de su servidor (por ejemplo, a través de reglas `.htaccess`).

**P: ¿Qué sucede si habilito la redirección pero no proporciono una URL de redirección?**
R: Si "Redirigir usuarios bloqueados" está habilitado pero "URL de redirección" está vacío, el comportamiento del módulo podría ser inconsistente. Es una buena práctica proporcionar siempre una URL válida si la redirección está activa. Si no desea redirigir, deshabilite la opción "Redirigir usuarios bloqueados" y use el mensaje personalizado en su lugar.

**P: ¿Este módulo ralentizará mi tienda?**
R: No, el módulo está diseñado para ser muy ligero y eficiente. Verifica la dirección IP del visitante muy temprano en el proceso de carga de PrestaShop. Si una IP está bloqueada, la solicitud se termina o se redirige rápidamente, a menudo *antes* de que su tienda comience a cargar su contenido completo, lo que en realidad puede *mejorar* el rendimiento al reducir la carga no deseada del servidor.

## 4. Guía para desarrolladores y webmasters (Arquitectura técnica y mapa de código)

Esta sección proporciona una inmersión técnica profunda en el módulo "Bloquear dirección IP Pro" para desarrolladores y webmasters.

### 4.1 Descripción general de la arquitectura
El módulo "Bloquear dirección IP Pro" sigue una arquitectura de módulo estándar de PrestaShop, aprovechando principalmente la clase `Module` para la instalación/desinstalación y configuración, y `AdminController` para la gestión del back-office. Utiliza una tabla de base de datos personalizada para almacenar las direcciones IP bloqueadas y se engancha al hook `actionFrontControllerAfterInit` para realizar la verificación de IP lo antes posible en el ciclo de vida de la solicitud.

### 4.2 Controladores (`controllers/`)

-   **Controladores de Front-Office**:
    El módulo no tiene controladores de front-office dedicados. La lógica de bloqueo de IP se maneja directamente dentro del archivo principal del módulo (`banippro.php`) a través de un hook, asegurando una ejecución temprana.

-   **Controladores de administración de Back-Office**:
    1.  `banippro/controllers/admin/AdminBanIpProController.php`
        *   **Nombre de la clase y clase padre:** `AdminBanIpProController` extiende `ModuleAdminController`.
        *   **Responsabilidad:** Este controlador es responsable de gestionar la lista de direcciones IP bloqueadas en el Back Office de PrestaShop. Proporciona la interfaz CRUD (Crear, Leer, Actualizar, Eliminar) estándar para la entidad `BanIpPro`. Maneja:
            *   Mostrar la lista de IPs bloqueadas con sus detalles (IP, visitas, comentario, estado activo).
            *   Añadir nuevas direcciones IP a la lista de bloqueo.
            *   Editar entradas de direcciones IP existentes.
            *   Eliminar direcciones IP de la lista de bloqueo.
            *   Gestionar el interruptor de estado "Activo" para cada IP.
            *   Los métodos `initContent()`, `renderList()`, `renderForm()` suelen ser sobrescritos aquí para personalizar la visualización y los formularios.
            *   Se mapea a la tabla de base de datos `ban` (o similar, según lo definido por el modelo `BanIpPro` si existiera).

    2.  `banippro/controllers/admin/index.php`
        *   **Responsabilidad:** Este es un archivo `index.php` vacío estándar que a menudo se encuentra en los subdirectorios de módulos de PrestaShop. Su propósito principal es evitar la lista de directorios en los servidores web por razones de seguridad. No contiene ninguna lógica funcional para el módulo.

### 4.3 Clases y modelos principales (`classes/`)
La descripción del módulo indica que no hay clases personalizadas en el directorio `classes/`. La entidad `BanIpPro` (para IPs bloqueadas) probablemente se gestiona directamente dentro de `AdminBanIpProController` y el archivo principal `banippro.php`, potencialmente utilizando una interacción simple de la clase `Db` o una estructura de matriz interna si no es totalmente compatible con `ObjectModel`. Si se utilizara un `ObjectModel`, normalmente se llamaría `BanIpPro` y residiría en `classes/BanIpPro.php`.

Dado que `AdminBanIpProController` gestiona una entidad "ban", implica una estructura de datos subyacente. Si no es un `ObjectModel` dedicado, serían consultas directas a la base de datos.

### 4.4 Activos de JavaScript (`views/js/`)
La descripción del módulo indica que no hay archivos JavaScript personalizados. Cualquier elemento interactivo en el back office (como interruptores o validación de formularios) probablemente se maneja mediante el JS central de PrestaShop o scripts en línea dentro de las plantillas.

### 4.5 Hojas de estilo CSS (`views/css/`)
La descripción del módulo indica que no hay archivos CSS personalizados. El estilo para la configuración del back-office y las pantallas de gestión de IP se basará completamente en el CSS del tema predeterminado del back-office de PrestaShop.

### 4.6 Estructura de plantillas Smarty (`views/templates/`)
La descripción del módulo indica que no hay archivos de plantilla personalizados.
-   **Plantillas de hook**: El comportamiento de front-office del módulo (bloqueo/redirección) se maneja programáticamente en el hook, no a través de una plantilla.
-   **Plantillas de administración**: El formulario de configuración para `getContent()` y las vistas de lista/formulario para `AdminBanIpProController` probablemente se renderizan utilizando las clases de ayuda predeterminadas de PrestaShop (`HelperForm`, `HelperList`) que generan HTML directamente, o se basan en plantillas en línea muy mínimas si las hay.

### 4.7 Esquema de la base de datos y mapa de Hooks

-   **Tablas de la base de datos**:
    El módulo crea al menos una tabla personalizada durante la instalación para almacenar las direcciones IP bloqueadas.
    -   `ps_banippro` (o similar, por ejemplo, `ps_ban_ip_pro`):
        *   `id_banippro` (Clave primaria, INT)
        *   `ip_address` (VARCHAR, almacena la dirección IP a bloquear)
        *   `comment` (TEXT, para notas del administrador)
        *   `views` (INT, contador de cuántas veces se bloqueó esta IP)
        *   `active` (TINYINT(1), 0 o 1, para habilitar/deshabilitar el bloqueo)

    La configuración (`mypresta_updates`, `banippro_msg`, `banippro_redirect`, `banippro_url`) se almacena en la tabla `ps_configuration`.

-   **Tabla de Hooks registrados**:

| Nombre del Hook | Momento de ejecución | Propósito técnico |
|---|---|---|
| `actionFrontControllerAfterInit` | Se ejecuta después de que el controlador frontal se ha inicializado pero antes de que se renderice cualquier contenido. | **CRÍTICO:** Aquí es donde el módulo realiza su función principal: verificar la IP del visitante contra la lista de bloqueados. Si se encuentra una coincidencia, muestra el mensaje personalizado o realiza una redirección, deteniendo efectivamente la ejecución posterior de la página. |
| `displayHome` | Renderiza contenido en la página de inicio. | Probablemente utilizado para notificaciones de actualización u otro contenido específico del módulo si el módulo tuviera un componente de front-office. En el contexto de este módulo, podría ser un hook heredado o utilizado para una lógica muy específica y no bloqueante. |
| `home` | Alias para `displayHome` en algunos contextos. | Igual que `displayHome`. |
| `header` | Renderiza contenido dentro de la sección `<head>` del HTML. | Se utiliza para añadir CSS, JavaScript o metaetiquetas. En este módulo, podría utilizarse para notificaciones de actualización o para asegurar la carga temprana de scripts/estilos si fuera necesario. |
| `actionAdminControllerSetMedia` | Se ejecuta cuando un controlador de administración está configurando sus medios (CSS/JS). | Utilizado por el módulo para añadir cualquier archivo CSS o JavaScript específico requerido para sus páginas de configuración de back-office (por ejemplo, para `AdminBanIpProController`). |
| `ActionAdminControllerSetMedia` | (Duplicado del anterior, diferencia sensible a mayúsculas y minúsculas) | Igual que `actionAdminControllerSetMedia`. Los hooks de PrestaShop son generalmente insensibles a mayúsculas y minúsculas, pero los módulos a veces registran ambos para compatibilidad. |
| `displayHeader` | Renderiza contenido dentro de la sección `<header>` del HTML (a menudo en el `<body>` antes del contenido principal). | Similar a `header`, pero típicamente para elementos visibles. En este módulo, es menos probable que tenga un impacto directo en el front-office dada su naturaleza de bloqueo. |

## 5. Soporte oficial y actualizaciones
Para las últimas actualizaciones del módulo, correcciones de errores y soporte profesional, consulte su cuenta de cliente en MyPresta.eu. Nuestro equipo se dedica a brindar asistencia oportuna y garantizar que su módulo funcione sin problemas.
-   **Historial de pedidos y descargas de MyPresta.eu:** [https://mypresta.eu/my-account/orders/](https://mypresta.eu/my-account/orders/)
-   **Contacto de soporte de MyPresta.eu:** [https://mypresta.eu/contact](https://mypresta.eu/contact)
