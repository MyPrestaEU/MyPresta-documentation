---
title: "Cart protection pro - Manual para el Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop Cart protection pro de MyPresta.eu."
sidebar:
  label: "Cart protection pro - Manual para el Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Cart protection pro en MyPresta.eu](https://mypresta.eu/modules/administration-tools/cart-protection-pro.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/back-office-tools/cart-protection-pro/)
>
> ---


# Cart protection pro

## 1. Requisitos y Compatibilidad

-   **Versiones de PrestaShop compatibles**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
-   **Compatibilidad con PHP**: PHP 5.6 - 8.5
-   **Requisitos de alojamiento**: Las extensiones PHP estándar (cURL, JSON, OpenSSL) suelen ser necesarias para las integraciones de API externas (como CleanTalk o StopForumSpam) si decide habilitarlas. La mayoría de los entornos de alojamiento modernos ya las proporcionan.

## 2. Recorrido completo por la configuración (Cada ajuste agrupado por pantalla)

### 2.1 Página de configuración del módulo (Back Office > Módulos > Configurar)

Este es el panel de control principal de "Cart protection pro", donde se define cómo el módulo detecta y responde a la actividad sospechosa del carrito.

#### Ajustes generales

-   **Activado**:

    -   **Qué hace este ajuste:** Este es el interruptor maestro del módulo.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando está activado:* El módulo monitorea activamente la actividad del carrito y aplica las reglas de protección elegidas.
        -   *Cuando está desactivado:* El módulo está inactivo y no protegerá su tienda de ataques de carritos falsos.
    -   **Valor recomendado:** SÍ
    -   **Escenario / ejemplo de comerciante:** Manténgalo siempre activado para asegurar que su tienda esté protegida. Desactívelo solo para solucionar problemas o realizar mantenimiento.
-   **Tipo de protección**:

    -   **Qué hace este ajuste:** Determina el método que utiliza el módulo para identificar y bloquear actividades sospechosas.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando se establece en "Dirección IP":* El módulo rastrea los intentos de carrito basándose en la dirección IP del visitante. Si una IP excede los intentos permitidos, será bloqueada.
        -   *Cuando se establece en "Cookie":* El módulo rastrea los intentos de carrito utilizando una cookie del navegador. Si un navegador (identificado por la cookie) excede los intentos, será bloqueado. Esto es menos fiable ya que las cookies pueden borrarse.
        -   *Cuando se establece en "Dirección IP + Cookie":* Combina ambos métodos para una protección más fuerte. Una IP o una cookie que exceda los límites activará un bloqueo.
        -   *Cuando se establece en "CleanTalk":* Utiliza el servicio externo anti-spam CleanTalk para verificar las solicitudes. Requiere una clave API de CleanTalk.
        -   *Cuando se establece en "StopForumSpam":* Utiliza la base de datos externa StopForumSpam para comprobar si una IP es conocida por spam. Requiere una clave de StopForumSpam.
    -   **Valor recomendado:** "Dirección IP + Cookie" para una protección local robusta, o "CleanTalk" / "StopForumSpam" si tiene cuentas con estos servicios para comprobaciones externas avanzadas.
    -   **Escenario / ejemplo de comerciante:** Si está experimentando un alto volumen de carritos falsos, comience con "Dirección IP + Cookie". Si el problema persiste o desea comprobaciones más avanzadas, considere la integración con CleanTalk o StopForumSpam.
-   **Marco de tiempo**:

    -   **Qué hace este ajuste:** Define la duración (en minutos) dentro de la cual el módulo cuenta los intentos de carrito de una sola fuente (IP o cookie).
    -   **Efecto de cambiar este ajuste:**
        -   *Un marco de tiempo más corto (por ejemplo, 5 minutos):* Protección más agresiva. Un usuario/bot será bloqueado más rápido si realiza muchos intentos en un corto período.
        -   *Un marco de tiempo más largo (por ejemplo, 60 minutos):* Menos agresivo. Permite más intentos durante un período más largo antes de bloquear.
    -   **Valor recomendado:** 10 minutos
    -   **Escenario / ejemplo de comerciante:** Si los bots están creando carritos rápidamente, un marco de tiempo más corto los detectará más rápido. Si encuentra que los usuarios legítimos están siendo bloqueados (raro), podría aumentarlo ligeramente.
-   **Número de intentos**:

    -   **Qué hace este ajuste:** Establece el número máximo de adiciones al carrito permitidas desde una única fuente (IP o cookie) dentro del "Marco de tiempo" definido antes de que se active un bloqueo.
    -   **Efecto de cambiar este ajuste:**
        -   *Un número más bajo (por ejemplo, 3):* Muy agresivo. Un usuario/bot será bloqueado después de solo unas pocas adiciones al carrito.
        -   *Un número más alto (por ejemplo, 10):* Menos agresivo. Permite más adiciones al carrito antes de bloquear.
    -   **Valor recomendado:** 5
    -   **Escenario / ejemplo de comerciante:** Un cliente normal rara vez añade más de 5 artículos a su carrito en un período de 10 minutos. Los bots, sin embargo, a menudo intentan añadir docenas o cientos. Establecer esto en 5 ayuda a diferenciar.
-   **Título del correo electrónico al comerciante**:

    -   **Qué hace este ajuste:** Especifica la línea de asunto para la notificación por correo electrónico que se le envía a usted (el comerciante) cuando ocurre una prohibición de protección del carrito.
    -   **Efecto de cambiar este ajuste:** Cambia la línea de asunto de los correos electrónicos de alerta que recibe.
    -   **Valor recomendado:** "Cart Protection Pro - ¡Alerta de Prohibición!"
    -   **Escenario / ejemplo de comerciante:** Personalice esto para que las alertas sean fácilmente reconocibles en su bandeja de entrada, por ejemplo, "URGENTE: Bot Bloqueado en [Nombre de su tienda]".
-   **Registros**:

    -   **Qué hace este ajuste:** Controla si el módulo registra los detalles de los intentos de carrito y las prohibiciones en su base de datos de PrestaShop.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando está activado:* El módulo almacena un historial de todos los intentos y prohibiciones, que puede revisar en las secciones "Intentos" y "Prohibiciones" del módulo. Esto es crucial para monitorear y comprender los ataques.
        -   *Cuando está desactivado:* No se guardan registros, lo que dificulta el seguimiento o la resolución de problemas.
    -   **Valor recomendado:** SÍ
    -   **Escenario / ejemplo de comerciante:** Mantenga siempre los registros activados. Proporcionan información valiosa sobre los tipos y la frecuencia de los ataques que enfrenta su tienda, ayudándole a ajustar su configuración.

#### Integración con CleanTalk

-   **Activar el soporte gratuito de CleanTalk**:

    -   **Qué hace este ajuste:** Habilita la integración con el servicio anti-spam CleanTalk para comprobaciones de spam en tiempo real. CleanTalk ofrece un plan gratuito para comprobaciones básicas.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando está activado:* El módulo enviará solicitudes a CleanTalk para verificar si una dirección IP o correo electrónico (si está disponible) es conocida por spam antes de permitir adiciones al carrito.
        -   *Cuando está desactivado:* No se realizan comprobaciones de CleanTalk.
    -   **Valor recomendado:** NO (a menos que tenga una cuenta de CleanTalk y una clave API)
    -   **Escenario / ejemplo de comerciante:** Si ya utiliza CleanTalk para otra protección contra spam (por ejemplo, comentarios, registros) o desea una capa adicional de verificación externa, habilite esto.
-   **Activar el soporte de pago de CleanTalk**:

    -   **Qué hace este ajuste:** Habilita la integración con el servicio anti-spam CleanTalk, específicamente para las funciones disponibles con una suscripción de pago de CleanTalk.
    -   **Efecto de cambiar este ajuste:** Similar al soporte gratuito, pero potencialmente con comprobaciones más avanzadas si su plan de CleanTalk lo permite.
    -   **Valor recomendado:** NO (a menos que tenga una cuenta de pago de CleanTalk y una clave API)
    -   **Escenario / ejemplo de comerciante:** Elija esto si tiene una suscripción de pago de CleanTalk y desea aprovechar todas sus capacidades para la protección del carrito.
-   **Clave API de CleanTalk**:

    -   **Qué hace este ajuste:** Esta es la clave única proporcionada por CleanTalk que autentica su tienda con su servicio.
    -   **Efecto de cambiar este ajuste:** Sin una clave API válida, la integración de CleanTalk no funcionará, incluso si está habilitada.
    -   **Valor recomendado:** Su clave API real de CleanTalk (déjela vacía si no usa CleanTalk).
    -   **Escenario / ejemplo de comerciante:** Después de registrarse en CleanTalk, recibirá una clave API. Introdúzcala aquí para activar su servicio.

#### Integración con StopForumSpam

-   **Activar el soporte de StopForumSpam**:

    -   **Qué hace este ajuste:** Habilita la integración con la base de datos StopForumSpam, que lista IPs, correos electrónicos y nombres de usuario conocidos por enviar spam en foros y sitios web.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando está activado:* El módulo consultará StopForumSpam para verificar si la dirección IP del visitante está listada como un spammer conocido.
        -   *Cuando está desactivado:* No se realizan comprobaciones de StopForumSpam.
    -   **Valor recomendado:** NO (a menos que tenga una clave de StopForumSpam)
    -   **Escenario / ejemplo de comerciante:** Esta es una buena capa adicional de protección si desea bloquear IPs que son globalmente reconocidas como spammers, incluso si aún no han activado sus límites de carrito locales.
-   **Clave de StopForumSpam**:

    -   **Qué hace este ajuste:** Esta es la clave única proporcionada por StopForumSpam que autentica su tienda con su servicio.
    -   **Efecto de cambiar este ajuste:** Sin una clave válida, la integración de StopForumSpam no funcionará, incluso si está habilitada.
    -   **Valor recomendado:** Su clave API real de StopForumSpam (déjela vacía si no usa StopForumSpam).
    -   **Escenario / ejemplo de comerciante:** Después de registrarse en StopForumSpam, recibirá una clave API. Introdúzcala aquí para activar su servicio.

### 2.2 Pantallas de administración dedicadas y vistas de controlador

#### 2.2.1 Cart Protection Pro > Intentos (Back Office > Módulos > Cart Protection Pro > Intentos)

-   **Nombre de la pantalla y ubicación del menú:** Puede encontrar esta pantalla navegando a **Módulos > Gestor de módulos**, luego haciendo clic en "Configurar" en "Cart protection pro", y luego seleccionando la pestaña "Intentos" (o un elemento de menú similar si el módulo añade su propio menú de nivel superior).
-   **Acciones y configuraciones disponibles:** Esta pantalla muestra una lista (vista de cuadrícula) de todos los intentos de carrito registrados que activaron el registro del módulo. Muestra detalles como:
    -   **Dirección IP:** La dirección IP del visitante.
    -   **ID de Cookie:** El identificador único de la cookie (si la protección "Cookie" está activada).
    -   **Intentos:** El número de adiciones al carrito realizadas por esta fuente dentro del marco de tiempo configurado.
    -   **Marca de tiempo:** Cuándo se registró el intento.
    -   **Estado:** Si llevó a una prohibición o fue solo un intento.
-   **Efecto de los cambios:** Este es un registro de solo lectura. No puede modificar directamente los intentos aquí. Su propósito es proporcionar transparencia y datos para que usted comprenda los posibles ataques. Normalmente puede filtrar y ordenar la lista para analizar patrones.
-   **Flujo de trabajo recomendado para la gestión diaria de la tienda:** Revise este registro regularmente, especialmente si sospecha de actividad de bots. Busque patrones:
    -   Muchos intentos desde la misma IP o cookie.
    -   Intentos concentrados en un corto período.
    -   Rangos de IP o ubicaciones geográficas inusuales.
    Estos datos le ayudan a ajustar sus configuraciones de "Marco de tiempo" y "Número de intentos".

#### 2.2.2 Cart Protection Pro > Prohibiciones (Back Office > Módulos > Cart Protection Pro > Prohibiciones)

-   **Nombre de la pantalla y ubicación del menú:** Similar a la pantalla de Intentos, se accede a esta a través de **Módulos > Gestor de módulos > Configurar "Cart protection pro" > Pestaña/elemento de menú Prohibiciones**.
-   **Acciones y configuraciones disponibles:** Esta pantalla muestra una lista (vista de cuadrícula) de todas las direcciones IP o IDs de cookies que han sido bloqueadas por el módulo. Normalmente muestra:
    -   **Dirección IP:** La IP bloqueada.
    -   **ID de Cookie:** La cookie bloqueada (si corresponde).
    -   **Razón:** Por qué ocurrió la prohibición (por ejemplo, "Demasiados intentos").
    -   **Hora de inicio/fin de la prohibición:** Cuándo se inició la prohibición y si es temporal.
    -   **Acciones:** A menudo incluye opciones para "Desbloquear" manualmente una entrada.
-   **Efecto de los cambios:**
    -   *Desbloquear una entrada:* Elimina el bloqueo para esa IP o cookie específica, permitiéndoles acceder de nuevo a la funcionalidad del carrito. ¡Úselo con precaución!
-   **Flujo de trabajo recomendado para la gestión diaria de la tienda:**
    -   Revise periódicamente la lista de prohibiciones. Si observa que una dirección IP legítima (por ejemplo, la suya o la de un socio conocido) ha sido bloqueada accidentalmente, puede desbloquearla aquí.
    -   Busque direcciones IP recurrentes o patrones en las prohibiciones, lo que podría indicar ataques persistentes.
    -   Esta pantalla es crucial para garantizar que el módulo esté bloqueando eficazmente el tráfico malicioso sin afectar inadvertidamente a los clientes reales.

### 2.3 Tabla de referencia rápida de configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| Configuración del módulo | Activado | SÍ | Interruptor maestro para la funcionalidad del módulo. |
| Configuración del módulo | Tipo de protección | Dirección IP + Cookie | Método para identificar y bloquear actividad sospechosa (IP, Cookie, ambos, CleanTalk, StopForumSpam). |
| Configuración del módulo | Marco de tiempo | 10 minutos | Duración (minutos) para contar los intentos de carrito. |
| Configuración del módulo | Número de intentos | 5 | Máximo de adiciones al carrito dentro del marco de tiempo antes de un bloqueo. |
| Configuración del módulo | Título del correo electrónico al comerciante | Cart Protection Pro - ¡Alerta de Prohibición! | Línea de asunto para los correos electrónicos de notificación al comerciante. |
| Configuración del módulo | Registros | SÍ | Habilita/deshabilita el registro de intentos y prohibiciones. |
| Configuración del módulo | Activar el soporte gratuito de CleanTalk | NO | Activa las comprobaciones anti-spam gratuitas de CleanTalk. |
| Configuración del módulo | Activar el soporte de pago de CleanTalk | NO | Activa las comprobaciones anti-spam de pago de CleanTalk. |
| Configuración del módulo | Clave API de CleanTalk | (vacío) | Su clave API única de CleanTalk. |
| Configuración del módulo | Activar el soporte de StopForumSpam | NO | Activa las comprobaciones de la base de datos de IP de StopForumSpam. |
| Configuración del módulo | Clave de StopForumSpam | (vacío) | Su clave API única de StopForumSpam. |
| AdminCproAttempts | Vista de cuadrícula / gestión | N/A | Muestra un registro de todos los intentos de carrito. |
| AdminCproBans | Vista de cuadrícula / gestión | N/A | Muestra una lista de todas las IPs/cookies bloqueadas, con opción de desbloqueo. |

## 3. Solución de problemas para comerciantes y preguntas frecuentes (FAQ)

**P1: Mis clientes se quejan de que no pueden añadir artículos al carrito, pero no veo ninguna prohibición.**
R1: Primero, compruebe si el módulo "Cart protection pro" está "Activado" en su configuración. Si lo está, navegue a la sección "Prohibiciones" dentro de la configuración del módulo. Vea si alguna IP de cliente legítimo aparece allí. Si es así, es posible que haya configurado el "Número de intentos" o el "Marco de tiempo" de forma demasiado agresiva. Intente aumentar ligeramente el "Número de intentos" (por ejemplo, de 3 a 5 o 7) o extender el "Marco de tiempo" (por ejemplo, de 5 a 10-15 minutos). Además, asegúrese de que su tema u otros módulos no estén interfiriendo con el proceso del carrito.

**P2: He configurado CleanTalk/StopForumSpam, pero no parece funcionar.**
R2: Vuelva a comprobar lo siguiente:
1.  Asegúrese de que "Activar el soporte de CleanTalk/StopForumSpam" esté habilitado.
2.  Verifique que su "Clave API de CleanTalk" o "Clave de StopForumSpam" esté introducida correctamente y esté activa con el servicio respectivo. Incluso un solo error tipográfico impedirá que funcione.
3.  Confirme que su entorno de alojamiento permite solicitudes cURL salientes, que son necesarias para comunicarse con estos servicios externos. Su host puede confirmarlo.
4.  Revise los registros de "Intentos" y "Prohibiciones" del módulo para ver si hay alguna entrada que indique un bloqueo por parte de estos servicios.

**P3: Mi tienda sigue recibiendo muchos carritos falsos incluso con el módulo activado.**
R3: Esto podría indicar un bot sofisticado o que su configuración no es lo suficientemente agresiva.
1.  **Revise su configuración:** Intente disminuir el "Número de intentos" (por ejemplo, de 5 a 3) y/o acortar el "Marco de tiempo" (por ejemplo, de 10 a 5 minutos).
2.  **Habilite servicios externos:** Si aún no lo ha hecho, considere habilitar y configurar CleanTalk o StopForumSpam para una capa adicional de protección.
3.  **Busque conflictos:** Deshabilite temporalmente otros módulos de seguridad o caché para ver si hay un conflicto.
4.  **Borrar caché:** A veces, la caché Smarty de PrestaShop puede impedir que la nueva configuración del módulo surta efecto inmediatamente. Vaya a **Parámetros avanzados > Rendimiento** y haga clic en "Borrar caché".

**P4: ¿Este módulo ralentizará mi tienda?**
R4: El módulo está diseñado para ser ligero. Las comprobaciones principales (IP/Cookie) son muy rápidas. Si habilita servicios externos como CleanTalk o StopForumSpam, habrá un ligero retraso ya que su servidor se comunica con sus APIs. Sin embargo, estos servicios están optimizados para la velocidad, y el impacto suele ser insignificante. El beneficio de prevenir la sobrecarga del servidor por carritos falsos supera con creces cualquier tiempo de procesamiento mínimo.

**P5: ¿Cómo traduzco el título del correo electrónico u otros textos del módulo?**
R5: Para el "Título del correo electrónico al comerciante", simplemente puede cambiar el texto directamente en la configuración del módulo. Para otros textos del módulo (si alguno fuera visible para los clientes, lo cual este módulo generalmente no lo es), normalmente iría a **Internacional > Traducciones** en su Back Office de PrestaShop. Seleccione "Traducciones de módulos instalados", elija su tema y luego seleccione "Cart protection pro" para encontrar y editar las cadenas traducibles.

## 4. Guía para desarrolladores y webmasters (Arquitectura técnica y mapa de código)

Esta sección proporciona una inmersión profunda en la estructura técnica del módulo "Cart protection pro", destinada a desarrolladores y webmasters que necesitan comprender, depurar o extender su funcionalidad.

### 4.1 Visión general de la arquitectura

El módulo "Cart protection pro" sigue una arquitectura de módulo estándar de PrestaShop, aprovechando principalmente los hooks para su funcionalidad principal y los Controladores de administración dedicados para la gestión del back-office. Integra servicios anti-spam externos (CleanTalk, StopForumSpam) a través de solicitudes cURL. La lógica del módulo está encapsulada dentro de su clase principal y clases auxiliares, con la configuración almacenada en `ps_configuration` y los registros en tablas de base de datos personalizadas.

### 4.2 Controladores (`controllers/`)

#### Controladores de Front-Office

Este módulo no define explícitamente controladores de front-office personalizados. Su lógica de front-office se ejecuta principalmente a través de hooks dentro del archivo principal del módulo `cpro.php`, interceptando las acciones del carrito antes de que se procesen por completo.

#### Controladores de administración del Back-Office

Estos controladores gestionan las pantallas de administración dedicadas del módulo, proporcionando vistas de cuadrícula para intentos y prohibiciones.

-   `cpro/controllers/admin/AdminCproAttempts.php`

    -   **Nombre de la clase y clase padre**: `AdminCproAttemptsController` extiende `ModuleAdminController`.
    -   **Responsabilidad**: Gestiona la visualización e interacción para el registro de "Intentos" en el Back Office de PrestaShop. Obtiene datos de la tabla de base de datos `cattempt` y los renderiza en formato de lista, permitiendo al administrador ver todos los intentos de carrito registrados. No permite la modificación directa de los intentos, actuando como un visor de registros de solo lectura.
-   `cpro/controllers/admin/AdminCproBans.php`

    -   **Nombre de la clase y clase padre**: `AdminCproBansController` extiende `ModuleAdminController`.
    -   **Responsabilidad**: Gestiona la visualización e interacción para la lista de "Prohibiciones" en el Back Office de PrestaShop. Recupera datos de la tabla de base de datos `cban` y los presenta en una lista. Este controlador también maneja acciones como "Desbloquear", permitiendo a un administrador eliminar una IP o cookie específica de la lista de prohibiciones.
-   `cpro/controllers/admin/index.php`

    -   **Nombre de la clase y clase padre**: Este archivo suele servir como medida de seguridad en PrestaShop, conteniendo `die('No direct script access');` para evitar el acceso directo al directorio. No contiene una clase de controlador funcional.

### 4.3 Clases y modelos principales (`classes/`)

El dossier del módulo no indica clases personalizadas en el directorio `classes/`. La lógica central para manejar intentos y prohibiciones, incluidas las interacciones con la base de datos, probablemente se gestiona directamente dentro del archivo principal del módulo `cpro.php` o mediante llamadas directas a `Db::getInstance()`.

### 4.4 Activos de JavaScript (`views/js/`)

El dossier del módulo no indica archivos JavaScript personalizados. Cualquier comportamiento dinámico en el back office probablemente se maneja mediante el JS principal de PrestaShop o scripts en línea dentro de las plantillas.

### 4.5 Hojas de estilo CSS (`views/css/`)

El dossier del módulo no indica archivos CSS personalizados. El estilo para las pantallas del back-office se basará en el tema de administración predeterminado de PrestaShop.

### 4.6 Estructura de la plantilla Smarty (`views/templates/`)

-   **Plantillas de administración (`views/templates/admin/`)**:
    -   `cpro/views/templates/admin/main.tpl`
        -   **Propósito**: Esta plantilla se utiliza probablemente para la página de configuración principal del módulo, renderizada por el método `getContent()` en `cpro.php`. Contiene la estructura HTML para todos los ajustes descritos en la Sección 4.1, incluidos los campos de formulario para "Tipo de protección", "Marco de tiempo", "Número de intentos", claves API y el interruptor "Activado". También podría incluir pestañas de navegación o enlaces a los controladores `AdminCproAttempts` y `AdminCproBans`.

### 4.7 Esquema de la base de datos y mapa de hooks

-   **Tablas de la base de datos**:

    -   `ps_cattempt`: Almacena registros de intentos de carrito.
        -   `id_cattempt` (Clave primaria)
        -   `ip_address` (VARCHAR): Dirección IP del visitante.
        -   `cookie_id` (VARCHAR): Identificador único de la cookie del navegador.
        -   `attempts` (INT): Número de adiciones al carrito.
        -   `date_add` (DATETIME): Marca de tiempo del intento.
        -   `status` (TINYINT): Estado, por ejemplo, 0 para intento, 1 para prohibido.
    -   `ps_cban`: Almacena registros de IPs/cookies prohibidas.
        -   `id_cban` (Clave primaria)
        -   `ip_address` (VARCHAR): Dirección IP prohibida.
        -   `cookie_id` (VARCHAR): ID de cookie prohibida.
        -   `reason` (TEXT): Razón de la prohibición (por ejemplo, "Demasiados intentos").
        -   `date_add` (DATETIME): Cuándo se inició la prohibición.
        -   `date_expire` (DATETIME): Si la prohibición es temporal.
    -   **Registros de configuración (en `ps_configuration`)**:
        -   `CPRO_PTYPE_5`: Configuración del tipo de protección (por ejemplo, IP, Cookie, CleanTalk).
        -   `CPRO_CTALK_APIKEY`: Clave API de CleanTalk.
        -   `CPRO_CTALK`: Soporte gratuito de CleanTalk habilitado/deshabilitado.
        -   `CPRO_CTALK_PAID`: Soporte de pago de CleanTalk habilitado/deshabilitado.
        -   `CPRO_ATMPT`: Número de intentos permitidos.
        -   `CPRO_TIME`: Marco de tiempo en minutos.
        -   `CPRO_PTYPE_1`, `CPRO_PTYPE_2`, `CPRO_PTYPE_3`, `CPRO_PTYPE_4`: Banderas internas para tipos de protección.
        -   `CPRO_SFS`: Soporte de StopForumSpam habilitado/deshabilitado.
        -   `CPRO_SFS_KEY`: Clave API de StopForumSpam.
        -   `CPRO_MTITLE`: Título del correo electrónico para notificaciones al comerciante.
        -   `CPRO_LOGS`: Registro habilitado/deshabilitado.
        -   `mypresta_updates`, `update_`, `updatev_`: Claves internas para actualizaciones del módulo.
-   **Tabla de Hooks Registrados**:

| Nombre del Hook | Momento de Ejecución | Propósito Técnico |
| --- | --- | --- |
| `actionObjectCartAddAfter` | Después de que un objeto de carrito ha sido añadido/actualizado en la base de datos. | Potencialmente utilizado para registrar adiciones exitosas al carrito o post-procesamiento después de que se guarda un carrito. |
| `actionCartSave` | Después de que un carrito ha sido guardado (insertado o actualizado). | Similar a `actionObjectCartAddAfter`, utilizado para monitorear o registrar cambios en el carrito. |
| `actionFrontControllerInitBefore` | Antes de que el controlador frontal se inicialice. | Punto de intercepción temprano para verificar IPs/cookies prohibidas antes de que se renderice cualquier contenido de la página, potencialmente redirigiendo o mostrando un mensaje de bloqueo. |
| `actionObjectCartAddBefore` | Antes de que un objeto de carrito sea añadido/actualizado en la base de datos. | **CRÍTICO**: Este es el hook principal para interceptar y validar las adiciones al carrito. El módulo realizará sus comprobaciones (IP, cookie, CleanTalk, StopForumSpam) aquí y puede evitar la adición al carrito si se exceden los límites o se detecta una prohibición. |
| `displayHeader` | En la sección `<head>` de las páginas del front-office. | Podría usarse para inyectar JavaScript necesario (aunque no se detectó ninguno) o CSS, o para establecer cookies para el seguimiento. |
| `actionDispatcherBefore` | Antes de que el despachador procese la solicitud. | Otro punto de intercepción temprano, similar a `actionFrontControllerInitBefore`, que permite al módulo realizar comprobaciones y potencialmente bloquear solicitudes antes de que lleguen a un controlador específico. |

### 4.8 Integraciones de API externas

-   **CleanTalk**: Utiliza cURL para enviar direcciones IP y potencialmente otros datos a la API de CleanTalk para la verificación de spam.
-   **StopForumSpam**: Utiliza cURL para consultar la base de datos de StopForumSpam con direcciones IP para buscar spammers conocidos.

## 5. Soporte oficial y actualizaciones

Para las últimas actualizaciones, correcciones de errores y soporte profesional para su módulo "Cart protection pro", consulte su cuenta de cliente en [MyPresta.eu](https://mypresta.eu). Nuestro equipo se dedica a garantizar que su módulo funcione de manera óptima y que su tienda permanezca segura.
"""
