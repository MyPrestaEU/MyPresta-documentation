---
title: "Casillas de verificación adicionales durante el registro - Manual del Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop 'Casillas de verificación adicionales durante el registro' de MyPresta.eu."
sidebar:
  label: "Casillas de verificación adicionales durante el registro - Manual del Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Additional checkboxes during register en MyPresta.eu](https://mypresta.eu/modules/front-office-features/additional-checkboxes-during-register.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/front-office/additional-checkboxes-during-register/)
>
> ---


# Casillas de verificación adicionales durante el registro

## 1. Requisitos y compatibilidad

- **Versiones de PrestaShop compatibles**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilidad con PHP**: PHP 5.6 - 8.5
- **Requisitos de alojamiento**: Se requieren extensiones PHP estándar (cURL, JSON, OpenSSL), que suelen estar disponibles en la mayoría de los entornos de alojamiento compatibles con PrestaShop.

## 2. Recorrido completo por la configuración (Cada ajuste agrupado por pantalla)

### 2.1 Página de configuración del módulo (Back Office > Módulos > Configurar)

Esta es la pantalla de configuración principal del módulo, a la que se accede haciendo clic en "Configurar" después de la instalación.

-   **Qué hace este ajuste:** Esta pantalla maneja principalmente la configuración general del módulo y le permite gestionar las actualizaciones.
-   **Efecto de cambiar este ajuste:**
    -   `mypresta_updates`: Este es un ajuste general para que los módulos de MyPresta.eu busquen actualizaciones.
        -   *Cuando está habilitado:* El módulo buscará periódicamente nuevas versiones en MyPresta.eu, notificándole en el Back Office si hay una actualización disponible. Esto le ayuda a mantener su módulo seguro y actualizado con las últimas características y correcciones de errores.
        -   *Cuando está deshabilitado:* El módulo no buscará actualizaciones automáticamente. Tendría que verificar manualmente su cuenta de MyPresta.eu para nuevas versiones.
    -   `update_`: Este ajuste está relacionado con la funcionalidad de verificación de actualizaciones.
    -   `updatev_`: Este ajuste está relacionado con la funcionalidad de verificación de actualizaciones.
-   **Valor recomendado:** Para `mypresta_updates`, generalmente se **recomienda mantenerlo habilitado** para asegurarse de estar siempre informado sobre las últimas versiones del módulo. Los otros dos ajustes son internos y generalmente deben dejarse como están.
-   **Escenario / ejemplo del comerciante:** Desea asegurarse de que su tienda siempre esté ejecutando la versión más segura y con más funciones del módulo. Habilitar las verificaciones de actualización significa que se le notificará directamente en su administración de PrestaShop cuando se lance una nueva versión, lo que facilita mantenerse al día.

### 2.2 Pantallas de administración dedicadas y vistas de controlador

#### AdminAddTosListController (Back Office > Módulos > Casillas de verificación adicionales > Lista de casillas de verificación)

Esta pantalla es donde define y gestiona todas las casillas de verificación individuales que aparecerán durante el registro del cliente.

-   **Nombre de la pantalla y ubicación del menú:** Puede encontrar esta pantalla navegando a **Módulos > Casillas de verificación adicionales > Lista de casillas de verificación** en el menú de su Back Office de PrestaShop.
-   **Acciones y configuraciones disponibles:**
    -   **Lista de casillas de verificación:** Esta página muestra una tabla de todas las casillas de verificación personalizadas que ha creado. Cada fila muestra el nombre de la casilla de verificación, si es obligatoria, su estado (habilitada/deshabilitada) y su posición.
    -   **Añadir nueva casilla de verificación:** Habrá un botón (por ejemplo, "Añadir nueva casilla de verificación" o un icono de más) para crear una casilla de verificación completamente nueva. Al añadir/editar una casilla de verificación, normalmente configurará:
        -   **Nombre/Etiqueta:** El texto que aparece junto a la casilla de verificación (por ejemplo, "Acepto la Política de privacidad"). Debe ser claro y conciso.
        -   **Enlace (Opcional):** Una URL a una página (por ejemplo, su página de Política de privacidad, una página de términos de servicio específica) en la que los clientes pueden hacer clic para leer los detalles completos. Esto es crucial para la transparencia.
        -   **Obligatorio:** Un interruptor (Sí/No) para determinar si el cliente *debe* marcar esta casilla para completar el registro.
            -   *Cuando está habilitado (Sí):* Los clientes no pueden registrarse sin marcar esta casilla. Esto es ideal para acuerdos legales esenciales.
            -   *Cuando está deshabilitado (No):* Los clientes pueden registrarse incluso si no marcan esta casilla. Esto es adecuado para consentimientos opcionales como suscripciones a boletines.
        -   **Activo:** Un interruptor (Sí/No) para habilitar o deshabilitar la visualización de la casilla de verificación en el front office.
            -   *Cuando está habilitado (Sí):* La casilla de verificación será visible en el formulario de registro.
            -   *Cuando está deshabilitado (No):* La casilla de verificación estará oculta del formulario de registro pero se conservará en el Back Office para uso futuro.
        -   **Posición:** Un número entero para controlar el orden en que aparecen las casillas de verificación en el formulario de registro. Los números más bajos aparecen más arriba.
    -   **Editar/Eliminar:** Cada casilla de verificación en la lista tendrá acciones para editar sus detalles o eliminarla por completo.
-   **Efecto de los cambios:**
    -   **Añadir una nueva casilla de verificación:** La nueva casilla de verificación aparecerá inmediatamente en su formulario de registro de clientes (si está activa) y en la página "Mi información personal" del cliente.
    -   **Editar una casilla de verificación:** Los cambios en la etiqueta, el enlace, el estado de obligatoriedad o el estado activo se reflejarán instantáneamente en el front office.
    -   **Eliminar una casilla de verificación:** La casilla de verificación se eliminará del front office. Los consentimientos de clientes existentes para esta casilla de verificación específica permanecerán registrados en el historial, pero no se podrán dar nuevos consentimientos.
-   **Flujo de trabajo recomendado para la gestión diaria de la tienda:**
    1.  **Identificar las necesidades de consentimiento:** Antes de añadir, determine qué consentimientos específicos necesita (por ejemplo, Política de privacidad, Boletín, Verificación de edad, términos de servicio específicos).
    2.  **Crear páginas de contenido:** Asegúrese de tener páginas CMS dedicadas (o enlaces externos) para cada política o término al que desee vincular.
    3.  **Añadir casillas de verificación:** Vaya a "Lista de casillas de verificación" y haga clic en "Añadir nueva casilla de verificación". Rellene la etiqueta, el enlace, configúrelo como obligatorio/opcional y actívelo.
    4.  **Ordenar casillas de verificación:** Utilice el campo "Posición" para organizarlas lógicamente.
    5.  **Revisar el Front Office:** Siempre pruebe el proceso de registro en el front office de su tienda después de realizar cambios para asegurarse de que todo se muestre y funcione como se espera.

#### AdminAddTosHistoryController (Back Office > Módulos > Casillas de verificación adicionales > Historial)

Esta pantalla proporciona un registro histórico de los consentimientos de los clientes para cada casilla de verificación.

-   **Nombre de la pantalla y ubicación del menú:** Puede encontrar esta pantalla navegando a **Módulos > Casillas de verificación adicionales > Historial** en el menú de su Back Office de PrestaShop.
-   **Acciones y configuraciones disponibles:**
    -   **Tabla de historial de consentimiento:** Esta página muestra un registro detallado de cuándo cada cliente aceptó (o no aceptó) una casilla de verificación específica.
    -   **Las columnas suelen incluir:**
        -   **Nombre del cliente:** El nombre del cliente.
        -   **Nombre de la casilla de verificación:** La etiqueta de la casilla de verificación con la que interactuaron.
        -   **Estado del consentimiento:** Si aceptaron (marcaron) o rechazaron (desmarcaron) la casilla.
        -   **Fecha:** La marca de tiempo de cuándo se registró el consentimiento.
        -   **Dirección IP:** La dirección IP desde la que se dio el consentimiento (importante para el cumplimiento legal).
    -   **Filtrado/Búsqueda:** Normalmente puede filtrar esta lista por cliente, casilla de verificación o rango de fechas para encontrar registros de consentimiento específicos.
-   **Efecto de los cambios:** Esta pantalla es principalmente para visualización y auditoría. No puede modificar directamente los registros de consentimiento aquí, ya que representan hechos históricos.
-   **Flujo de trabajo recomendado para la gestión diaria de la tienda:**
    -   **Auditoría y cumplimiento:** Utilice esta pantalla para verificar los consentimientos de los clientes si hay alguna disputa o para auditorías de cumplimiento internas.
    -   **Solicitudes de privacidad de datos:** Si un cliente solicita saber qué datos tiene o a qué ha dado su consentimiento, este historial proporciona un registro claro.

#### index.php (addtos/controllers/admin/index.php)

Este archivo es un marcador de posición y normalmente contiene un simple `header('Location: ../../../index.php?controller=AdminHome');` o una redirección similar para evitar el acceso directo al directorio. No representa una pantalla configurable para el comerciante.

### 2.3 Tabla de referencia rápida de configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| **Configuración del módulo** | Verificación de actualizaciones de MyPresta.eu | Habilitado | Le notifica sobre nuevas versiones del módulo para seguridad y características. |
| **Lista de casillas de verificación** | Nombre/Etiqueta de la casilla de verificación | N/A (Definido por el usuario) | El texto visible junto a la casilla de verificación en el formulario de registro. |
| **Lista de casillas de verificación** | Enlace (URL) | N/A (Definido por el usuario) | URL a una página de política; proporciona detalles para la casilla de verificación. |
| **Lista de casillas de verificación** | Obligatorio | No (Opcional) | Si es Sí, el cliente *debe* marcar para registrarse. Si es No, es opcional. |
| **Lista de casillas de verificación** | Activo | Sí | Si es Sí, la casilla de verificación es visible en el front office. Si es No, está oculta. |
| **Lista de casillas de verificación** | Posición | N/A (Definido por el usuario) | Determina el orden de visualización de las casillas de verificación en el formulario. |
| **Historial** | Nombre del cliente | N/A (Solo vista) | Muestra qué cliente dio su consentimiento. |
| **Historial** | Nombre de la casilla de verificación | N/A (Solo vista) | Muestra con qué casilla de verificación se interactuó. |
| **Historial** | Estado del consentimiento | N/A (Solo vista) | Muestra si el cliente aceptó o rechazó. |
| **Historial** | Fecha | N/A (Solo vista) | Marca de tiempo del registro de consentimiento. |
| **Historial** | Dirección IP | N/A (Solo vista) | Dirección IP desde la que se dio el consentimiento. |

## 3. Solución de problemas del comerciante y preguntas frecuentes (FAQ)

**P1: He añadido una nueva casilla de verificación, pero no aparece en la página de registro.**
**R1:**

-   **Verifique el estado "Activo":** Vaya a **Módulos > Casillas de verificación adicionales > Lista de casillas de verificación** y asegúrese de que el interruptor "Activo" de su casilla de verificación esté configurado en "Sí".
-   **Borrar caché:** A veces, la caché de PrestaShop puede evitar que el nuevo contenido aparezca inmediatamente. Vaya a **Parámetros avanzados > Rendimiento**, desplácese hasta "Borrar caché" y haga clic en "Borrar caché".
-   **Posición del módulo:** Asegúrese de que el módulo esté enganchado correctamente. Si bien el módulo generalmente lo maneja automáticamente, si ha realizado modificaciones en el tema, podría valer la pena verificar los hooks del módulo en **Diseño > Posiciones** (o **Módulos > Posiciones** en versiones anteriores). El módulo generalmente usa `displayAdditionalCustomerFormFields` o hooks similares.

**P2: El texto de mi casilla de verificación es demasiado largo y se ve mal en el móvil.**
**R2:**

-   **Sea conciso:** Intente acortar la etiqueta de la casilla de verificación a su esencia (por ejemplo, "Aceptar Política de privacidad" en lugar de "He leído y acepto los términos y condiciones de la política de privacidad de este sitio web").
-   **Use enlaces:** Coloque la información detallada en una página CMS separada y vincúlela desde la etiqueta de la casilla de verificación. Esto mantiene el formulario limpio al tiempo que proporciona total transparencia.
-   **Personalización del tema:** Si el problema persiste, el CSS de su tema podría estar limitando la visualización. Un webmaster puede ajustar el CSS para las clases `.addtos-checkbox` o similares para mejorar la capacidad de respuesta.

**P3: ¿Puedo traducir las etiquetas de las casillas de verificación a diferentes idiomas?**
**R3:** ¡Sí! Cuando edite una casilla de verificación en **Módulos > Casillas de verificación adicionales > Lista de casillas de verificación**, debería ver un selector de idioma junto al campo "Nombre/Etiqueta" (a menudo un icono de bandera). Haga clic en la bandera para cambiar a otro idioma e introduzca el texto traducido para ese idioma. Recuerde guardar sus cambios para cada idioma.

**P4: ¿Qué sucede si elimino una casilla de verificación? ¿Se elimina el historial de consentimiento del cliente?**
**R4:** No, eliminar una casilla de verificación de la "Lista de casillas de verificación" la eliminará del formulario de registro del front-office, pero **no eliminará los registros de consentimiento históricos** que los clientes dieron previamente para esa casilla de verificación. Esos registros permanecen en la sección "Historial" para fines de auditoría y cumplimiento. Los nuevos clientes simplemente ya no verán esa casilla de verificación.

**P5: Quiero cambiar el orden de las casillas de verificación en la página de registro.**
**R5:** Vaya a **Módulos > Casillas de verificación adicionales > Lista de casillas de verificación**. En la tabla, debería ver una columna "Posición". Normalmente puede arrastrar y soltar las filas para reordenarlas, o podría haber flechas hacia arriba/abajo o un campo numérico editable para cambiar la posición. Recuerde guardar sus cambios si es necesario.

## 4. Guía para desarrolladores y webmasters (Arquitectura técnica y mapa de código)

### 4.1 Resumen de la arquitectura

El módulo "Casillas de verificación adicionales durante el registro" sigue un patrón MVC (Modelo-Vista-Controlador) estándar de PrestaShop, extendiendo principalmente `Module` para su funcionalidad principal y `AdminController` para la gestión del Back Office. Aprovecha el sistema de hooks de PrestaShop para inyectar campos personalizados en los formularios de registro e identidad del cliente y para registrar datos de consentimiento. El módulo introduce tablas de base de datos personalizadas para almacenar las definiciones de las casillas de verificación y el historial de consentimiento del cliente.

### 4.2 Controladores (`controllers/`)

-   **Controladores de Front-Office**: Este módulo no utiliza controladores frontales dedicados. Todas las interacciones del front-office (mostrar casillas de verificación, procesar el consentimiento) se manejan directamente a través de los controladores de clientes principales de PrestaShop aprovechando hooks específicos.
-   **Controladores de administración de Back-Office**:

    -   `addtos/controllers/admin/AdminAddTosHistory.php`
        -   **Nombre de la clase y clase padre**: `AdminAddTosHistoryController` extiende `ModuleAdminController`.
        -   **Nombre de la pestaña y entidad gestionada**: Gestiona los registros históricos de los consentimientos de los clientes. Es accesible a través de la pestaña "Historial" en el menú principal del módulo. Este controlador muestra una vista de `list` de los objetos `TosHistory`, mostrando el cliente, la casilla de verificación, el estado del consentimiento, la fecha y la IP. No permite editar ni añadir registros, ya que es un registro histórico.
    -   `addtos/controllers/admin/AdminAddTosList.php`
        -   **Nombre de la clase y clase padre**: `AdminAddTosListController` extiende `ModuleAdminController`.
        -   **Nombre de la pestaña y entidad gestionada**: Gestiona la definición de las casillas de verificación personalizadas. Es accesible a través de la pestaña "Lista de casillas de verificación". Este controlador proporciona vistas de `list`, `add` y `edit` para objetos `Tos`, lo que permite a los administradores definir la etiqueta de la casilla de verificación, el enlace, el estado de obligatoriedad, el estado activo y la posición.
    -   `addtos/controllers/admin/index.php`
        -   Este es un archivo de marcador de posición estándar para evitar la lista de directorios. Normalmente contiene `header('Location: ../../../index.php?controller=AdminHome');` o similar. No tiene ningún papel funcional en la lógica del módulo.

### 4.3 Clases y modelos principales (`classes/`)

Las clases principales del módulo probablemente se definen dentro del archivo principal `addtos.php` o directamente dentro del directorio `classes/` si está presente (aunque el inventario sugiere que podrían estar en el archivo principal).

-   `Tos` (Probablemente definido dentro de `addtos.php` o `classes/Tos.php`):

    -   **Tabla de base de datos**: `ps_addtos_tos` (o similar, basado en el nombre de la entidad `tos`).
    -   **Extiende `ObjectModel`**: Sí.
    -   **Campos de `$definition`**:
        -   `id_tos`: Clave primaria.
        -   `name`: Campo `HTML`, `isLang` (multilingüe) - la etiqueta de la casilla de verificación.
        -   `link`: Campo `HTML`, `isLang` (multilingüe) - la URL para más información.
        -   `required`: `BOOL` - si la casilla de verificación es obligatoria.
        -   `active`: `BOOL` - si la casilla de verificación se muestra actualmente.
        -   `position`: `INT` - orden de visualización.
    -   **Métodos públicos clave**: Métodos `ObjectModel` estándar para operaciones CRUD.
-   `TosHistory` (Probablemente definido dentro de `addtos.php` o `classes/TosHistory.php`):

    -   **Tabla de base de datos**: `ps_addtos_toshistory` (o similar, basado en el nombre de la entidad `toshistory`).
    -   **Extiende `ObjectModel`**: Sí.
    -   **Campos de `$definition`**:
        -   `id_toshistory`: Clave primaria.
        -   `id_customer`: `INT` - ID del cliente que dio su consentimiento.
        -   `id_tos`: `INT` - ID de la casilla de verificación.
        -   `accepted`: `BOOL` - `1` si se aceptó, `0` si se rechazó (o `NULL` si es opcional y no se marcó).
        -   `date_add`: `DATE` - marca de tiempo del consentimiento.
        -   `ip_address`: `STRING` - dirección IP del cliente en el momento del consentimiento.
    -   **Métodos públicos clave**: Principalmente para operaciones `add` y `read`, ya que los registros de historial son inmutables.

### 4.4 Activos JavaScript (`views/js/`)

El inventario indica que no hay archivos JavaScript específicos presentes. Esto sugiere que cualquier validación del lado del cliente o comportamiento dinámico para las casillas de verificación se maneja mediante el JS principal de PrestaShop, el JS del tema, o no es una característica principal de este módulo (confiando en la validación del lado del servidor).

### 4.5 Hojas de estilo CSS (`views/css/`)

El inventario indica que no hay archivos CSS específicos presentes. Esto implica que el módulo se basa en el estilo predeterminado de PrestaShop para los elementos del formulario o en el CSS del tema activo para estilizar las casillas de verificación. Los desarrolladores que deseen personalizar la apariencia deberían apuntar a selectores de entrada de formulario estándar o, potencialmente, a clases añadidas por el módulo en sus plantillas.

### 4.6 Estructura de plantillas Smarty (`views/templates/`)

-   **Plantillas de hook (`views/templates/hook/`)**:
    -   `addtos/views/templates/hook/addtos_bo.tpl`: Esta plantilla probablemente se utiliza en el Back Office, posiblemente para mostrar un bloque de módulo o información dentro de una página de administración, o para renderizar contenido dentro de la página de configuración del módulo (por ejemplo, notificaciones de actualización).
-   **Plantillas de administración (`views/templates/admin/`)**: No se enumeran plantillas de administración dedicadas, lo que sugiere que `AdminAddTosListController` y `AdminAddTosHistoryController` se basan en las plantillas predeterminadas `list.tpl` y `form.tpl` de PrestaShop para renderizar sus vistas.
-   **Plantillas de front-office (`views/templates/front/`)**:
    -   `addtos/views/templates/front/identity.tpl`: Esta plantilla probablemente está enganchada a la página "Mi información personal" (Identidad) del cliente. Mostraría la lista de casillas de verificación y el estado de consentimiento actual del cliente, lo que podría permitirles actualizar sus preferencias.

### 4.7 Esquema de la base de datos y mapa de Hooks

-   **Tablas de la base de datos**:

    -   `ps_addtos_tos`: Almacena las definiciones de cada casilla de verificación personalizada (etiqueta, enlace, estado de obligatoriedad, estado activo, posición).
    -   `ps_addtos_tos_lang`: Almacena el contenido multilingüe para los campos `name` y `link` de la tabla `ps_addtos_tos`.
    -   `ps_addtos_toshistory`: Almacena los registros históricos de los consentimientos de los clientes (ID de cliente, ID de casilla de verificación, estado aceptado, marca de tiempo, dirección IP).
-   **Tabla de Hooks registrados**:

| Nombre del Hook | Momento de ejecución | Propósito técnico |
| --- | --- | --- |
| `actionValidateOrder` | Después de que se valida un pedido. | Potencialmente utilizado para registrar el consentimiento relacionado con los términos específicos del pedido, aunque menos común para las casillas de verificación de registro. |
| `validateCustomerFormFields` | Durante la validación del envío del formulario de registro del cliente. | Crucial para la validación del lado del servidor de las casillas de verificación obligatorias. Si una casilla de verificación obligatoria no está marcada, este hook evitaría el registro. |
| `displayAdditionalCustomerFormFields` | Renderiza campos adicionales en el formulario de registro del cliente. | Hook principal para mostrar las casillas de verificación personalizadas en la página de registro del front-office. |
| `displaytermsAndConditions` | Renderiza el contenido de los términos y condiciones. | Podría usarse para mostrar casillas de verificación cerca de los T&C estándar, o como alternativa. |
| `displayvalidateCustomerFormFields` | Renderiza mensajes de validación para los campos del formulario del cliente. | Se utiliza para mostrar mensajes de error si una casilla de verificación obligatoria no está marcada. |
| `additionalCustomerFormFields` | Similar a `displayAdditionalCustomerFormFields`, potencialmente para diferentes contextos o versiones. | Otro hook para inyectar campos personalizados en los formularios de clientes. |
| `termsAndConditions` | Similar a `displaytermsAndConditions`. | Otro hook para inyectar términos y condiciones. |
| `actionCustomerAccountAdd` | Después de que se crea una nueva cuenta de cliente con éxito. | Se utiliza para registrar las opciones de consentimiento del cliente para todas las casillas de verificación activas en la tabla `ps_addtos_toshistory`. |
| `displayAdminCustomers` | Renderiza contenido en la página de lista/edición de clientes de administración. | Podría usarse para mostrar un resumen de los consentimientos de un cliente directamente en su perfil del Back Office. |
| `displayCustomerAccountForm` | Renderiza contenido en la página "Mi información personal" (Identidad) del cliente. | Se utiliza para mostrar las casillas de verificación y permitir a los clientes ver/actualizar sus preferencias de consentimiento después del registro. |

## 5. Soporte oficial y actualizaciones

Para obtener las últimas actualizaciones, correcciones de errores y soporte oficial para el módulo "Casillas de verificación adicionales durante el registro", consulte su cuenta de cliente en [MyPresta.eu](https://mypresta.eu/). Nuestro equipo de soporte está disponible para ayudarle con cualquier problema o pregunta que pueda tener con respecto a la funcionalidad y configuración del módulo.
"""
