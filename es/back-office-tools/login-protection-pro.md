---
title: "Login protection pro - Manual del Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop Login protection pro de MyPresta.eu."
sidebar:
  label: "Login protection pro - Manual del Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Login protection pro en MyPresta.eu](https://mypresta.eu/modules/administration-tools/login-protection-pro.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/back-office-tools/login-protection-pro/)
>
> ---


# Login protection pro

## 1. Requisitos y compatibilidad

- **Versiones de PrestaShop compatibles**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilidad con PHP**: PHP 5.6 - 8.5
- **Requisitos de alojamiento**: Extensiones PHP estándar (cURL, JSON, OpenSSL).

## 2. Recorrido completo por la configuración (Cada ajuste agrupado por pantalla)

### 2.1 Página de configuración del módulo (Back Office > Módulos > Configurar)

Esta es la pantalla de configuración principal donde se definen las reglas básicas para la protección de inicio de sesión.

- **Ubicación del menú:** Back Office > Módulos > Gestor de módulos > Login protection pro > Configurar

#### Ajustes y opciones:

1.  **Habilitar protección de inicio de sesión:**

    - **Qué hace este ajuste:** Este es el interruptor maestro para el módulo. Activa o desactiva todo el sistema de protección de inicio de sesión.
    - **Efecto de cambiar este ajuste:**
      - *Cuando está habilitado:* El módulo comenzará a monitorear los intentos de inicio de sesión, aplicando las reglas que establezca a continuación.
      - *Cuando está deshabilitado:* El módulo estará inactivo y no se monitorearán ni bloquearán los intentos de inicio de sesión. Su tienda dependerá de la seguridad predeterminada de PrestaShop, que no incluye protección contra fuerza bruta.
    - **Valor recomendado:** **SÍ**
    - **Escenario / ejemplo del comerciante:** Mantenga esto siempre habilitado para garantizar que su tienda esté protegida. Desactive solo para depuración específica si lo indica el soporte.
2.  **Intentos fallidos máximos:**

    - **Qué hace este ajuste:** Define el número máximo de intentos de inicio de sesión incorrectos permitidos desde una única dirección IP dentro de un período de tiempo específico (definido por "Ventana de tiempo de intento") antes de que esa IP sea bloqueada temporalmente.
    - **Efecto de cambiar este ajuste:**
      - *Establecer un número más bajo (por ejemplo, 3):* Hace que la protección sea más agresiva, bloqueando las IP sospechosas más rápidamente. Esto podría bloquear accidentalmente a usuarios legítimos que realmente olvidan su contraseña varias veces.
      - *Establecer un número más alto (por ejemplo, 10):* Hace que la protección sea menos agresiva, permitiendo más intentos fallidos. Esto reduce la posibilidad de bloquear a usuarios legítimos, pero da a los hackers más intentos.
    - **Valor recomendado:** **5**
    - **Escenario / ejemplo del comerciante:** Si nota que muchos clientes legítimos son bloqueados, podría aumentar esto. Si ve muchos intentos de fuerza bruta en sus registros, podría disminuirlo. 5 es un buen equilibrio.
3.  **Ventana de tiempo de intento (minutos):**

    - **Qué hace este ajuste:** Especifica la duración (en minutos) durante la cual el recuento de "Intentos fallidos máximos" está activo. Si una IP realiza `Intentos fallidos máximos` dentro de esta ventana, se bloquea. Después de esta ventana, el recuento se restablece.
    - **Efecto de cambiar este ajuste:**
      - *Establecer una ventana más corta (por ejemplo, 5 minutos):* Una IP debe realizar los `Intentos fallidos máximos` muy rápidamente para ser bloqueada. Esto es bueno para ataques rápidos de fuerza bruta.
      - *Establecer una ventana más larga (por ejemplo, 60 minutos):* Una IP puede realizar `Intentos fallidos máximos` durante un período más largo para ser bloqueada. Esto detecta ataques más lentos y distribuidos, pero también podría bloquear a usuarios legítimos que intentan iniciar sesión, se distraen y lo intentan de nuevo más tarde.
    - **Valor recomendado:** **15**
    - **Escenario / ejemplo del comerciante:** Una ventana de 15 minutos suele ser suficiente para detectar ataques automatizados sin penalizar indebidamente a un usuario humano que podría estar intentando recordar su contraseña durante unos minutos.
4.  **Duración del bloqueo (minutos):**

    - **Qué hace este ajuste:** Determina cuánto tiempo permanece bloqueada una dirección IP una vez que excede los `Intentos fallidos máximos` dentro de la `Ventana de tiempo de intento`.
    - **Efecto de cambiar este ajuste:**
      - *Establecer una duración más corta (por ejemplo, 30 minutos):* La IP se desbloquea antes. Esto es menos perjudicial para los usuarios legítimos que podrían haber sido bloqueados accidentalmente, pero da a los hackers un reintento más rápido.
      - *Establecer una duración más larga (por ejemplo, 1440 minutos = 24 horas):* La IP permanece bloqueada durante un período significativo. Esto es muy efectivo contra ataques automatizados, pero puede ser frustrante para los usuarios legítimos que están bloqueados.
    - **Valor recomendado:** **60** (1 hora)
    - **Escenario / ejemplo del comerciante:** Un bloqueo de 60 minutos suele ser suficiente para disuadir a los bots automatizados, ya que probablemente seguirán adelante. Para un humano, proporciona un período de enfriamiento razonable.
5.  **Proteger inicio de sesión de administrador:**

    - **Qué hace este ajuste:** Este interruptor aplica específicamente las reglas de protección de inicio de sesión a la página de inicio de sesión del Back Office de PrestaShop (panel de administración).
    - **Efecto de cambiar este ajuste:**
      - *Cuando está habilitado:* Su página de inicio de sesión de administrador está protegida. Si un atacante intenta adivinar su contraseña de administrador demasiadas veces, su IP será bloqueada.
      - *Cuando está deshabilitado:* Solo se monitorean los intentos de inicio de sesión de los clientes. Su página de inicio de sesión de administrador permanece vulnerable a ataques de fuerza bruta.
    - **Valor recomendado:** **SÍ**
    - **Escenario / ejemplo del comerciante:** Es absolutamente crítico proteger su inicio de sesión de administrador, ya que el acceso no autorizado aquí puede comprometer toda su tienda. Mantenga esto siempre habilitado.
6.  **Proteger inicio de sesión de cliente:**

    - **Qué hace este ajuste:** Este interruptor aplica específicamente las reglas de protección de inicio de sesión a la página de inicio de sesión del cliente (front office).
    - **Efecto de cambiar este ajuste:**
      - *Cuando está habilitado:* Los intentos de inicio de sesión de los clientes están protegidos. Si un atacante intenta adivinar las contraseñas de los clientes, su IP será bloqueada.
      - *Cuando está deshabilitado:* Solo se monitorean los intentos de inicio de sesión de administrador. Las cuentas de los clientes permanecen vulnerables a ataques de fuerza bruta.
    - **Valor recomendado:** **SÍ**
    - **Escenario / ejemplo del comerciante:** Proteger las cuentas de los clientes es vital para la seguridad de los datos y para mantener la confianza del cliente. Mantenga esto siempre habilitado.

#### Tabla de referencia rápida de configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| Configuración del módulo | Habilitar protección de inicio de sesión | SÍ | Interruptor maestro para la funcionalidad del módulo. **Siempre SÍ.** |
| Configuración del módulo | Intentos fallidos máximos | 5 | Número de inicios de sesión incorrectos antes de que se bloquee una IP. |
| Configuración del módulo | Ventana de tiempo de intento (minutos) | 15 | Duración durante la cual se cuentan los intentos fallidos. |
| Configuración del módulo | Duración del bloqueo (minutos) | 60 | Cuánto tiempo permanece bloqueada una IP. |
| Configuración del módulo | Proteger inicio de sesión de administrador | SÍ | Aplica protección al inicio de sesión del Back Office. **Siempre SÍ.** |
| Configuración del módulo | Proteger inicio de sesión de cliente | SÍ | Aplica protección al inicio de sesión del cliente del Front Office. **Siempre SÍ.** |

### 2.2 Pantallas de administración dedicadas y vistas de controlador

El módulo proporciona dos pantallas dedicadas en su Back Office de PrestaShop para gestionar y revisar los intentos de inicio de sesión y los bloqueos.

#### 2.2.1 AdminLproAttemptsController: Registro de intentos de inicio de sesión

Esta pantalla le permite ver un registro detallado de todos los intentos de inicio de sesión fallidos registrados por el módulo.

- **Nombre de la pantalla y ubicación del menú:** Back Office > Módulos > Login Protection Pro > **Intentos de inicio de sesión** (o similar, dependiendo de la versión de PrestaShop y la personalización del menú).
- **Acciones y ajustes disponibles:**
  - **Tabla de listado:** Verá una tabla que muestra:
    - **Dirección IP:** La dirección IP desde la que se originó el intento fallido.
    - **Hora del intento:** La fecha y hora exactas del intento fallido.
    - **Tipo de inicio de sesión:** Si fue un intento de inicio de sesión de 'Administrador' o 'Cliente'.
    - **Nombre de usuario/Correo electrónico:** El nombre de usuario o dirección de correo electrónico que se intentó.
    - **Estado:** Indica si el intento llevó a un bloqueo o fue solo un intento fallido.
  - **Filtrado y clasificación:** Normalmente puede filtrar por dirección IP, tipo de inicio de sesión o rango de fechas para encontrar intentos específicos.
  - **Sin acciones directas:** Esta pantalla es principalmente para monitoreo y revisión. No puede bloquear o desbloquear IP directamente desde aquí, pero le ayuda a identificar patrones sospechosos.
- **Efecto de los cambios:** Ver este registro le ayuda a comprender la frecuencia y el origen de los ataques. Si nota que una dirección IP en particular realiza muchos intentos, puede agregarla manualmente a la lista de bloqueos a través de la pantalla "IPs bloqueadas".
- **Flujo de trabajo recomendado para la gestión diaria de la tienda:** Revise este registro regularmente, especialmente si sospecha un ataque o si los clientes informan problemas para iniciar sesión. Busque patrones de intentos fallidos repetidos desde la misma IP o rango de IP.

#### 2.2.2 AdminLproBansController: Gestión de IPs bloqueadas

Esta pantalla le permite ver, agregar y eliminar direcciones IP de la lista de bloqueos del módulo.

- **Nombre de la pantalla y ubicación del menú:** Back Office > Módulos > Login Protection Pro > **IPs bloqueadas** (o similar, dependiendo de la versión de PrestaShop y la personalización del menú).
- **Acciones y ajustes disponibles:**
  - **Tabla de listado:** Muestra todas las direcciones IP actualmente bloqueadas, incluyendo:
    - **Dirección IP:** La IP bloqueada.
    - **Motivo del bloqueo:** (Si aplica, por ejemplo, "Bloqueo automático debido a intentos fallidos").
    - **Hora de inicio del bloqueo:** Cuando se inició el bloqueo.
    - **Hora de finalización del bloqueo:** Cuando está programado que expire el bloqueo (si es temporal).
    - **Acciones:** Normalmente incluye una opción para "Eliminar" o "Desbloquear" una IP específica.
  - **Botón "Añadir nueva IP":** Le permite agregar manualmente una dirección IP a la lista de bloqueos. Esto es útil si identifica una IP maliciosa de los registros de su servidor o de la pantalla "Intentos de inicio de sesión" que aún no ha sido bloqueada automáticamente.
    - Al agregar, es posible que pueda especificar la IP, un motivo y un tiempo de caducidad opcional para el bloqueo.
- **Efecto de los cambios:**
  - *Agregar una IP:* Bloquea inmediatamente todos los intentos de inicio de sesión desde esa dirección IP durante la duración especificada (o permanentemente si no se establece una duración).
  - *Eliminar una IP:* Desbloquea la dirección IP, permitiendo nuevamente los intentos de inicio de sesión desde ella. Use esto con precaución, asegurándose de no desbloquear a un atacante conocido.
- **Flujo de trabajo recomendado para la gestión diaria de la tienda:**
  - Revise esta lista periódicamente.
  - Si un cliente legítimo informa que no puede iniciar sesión y ha confirmado su dirección IP (por ejemplo, pidiéndole que visite un sitio de "cuál es mi IP"), podría desbloquear temporalmente su IP aquí.
  - Si identifica una amenaza persistente, puede agregar manualmente su IP para asegurarse de que permanezca bloqueada.

#### 2.2.3 index.php (lpro/controllers/admin/index.php)

Este archivo suele servir como marcador de posición o redirigir dentro del directorio de controladores de administración. En PrestaShop, los archivos `index.php` dentro de los directorios de controladores a menudo evitan la lista directa de directorios o actúan como un punto de entrada predeterminado si no se solicita un controlador específico. No representa una pantalla configurable o una entidad gestionada en sí misma.

## 3. Solución de problemas del comerciante y preguntas frecuentes (FAQ)

**P1: Mis clientes se quejan de que no pueden iniciar sesión, pero están usando la contraseña correcta. ¿Qué debo hacer?**
R1: Esto probablemente se deba a que el módulo bloquea su dirección IP después de demasiados intentos fallidos (quizás de una sesión anterior o una red compartida).
1.  Pida al cliente su dirección IP actual (puede encontrarla buscando "cuál es mi IP" en Google).
2.  Vaya a **Back Office > Módulos > Login Protection Pro > IPs bloqueadas**.
3.  Busque su dirección IP en la lista.
4.  Si la encuentra, elimine/desbloquee su IP.
5.  Aconseje al cliente que intente iniciar sesión de nuevo. También podría sugerirle que restablezca su contraseña.

**P2: ¡Estoy bloqueado de mi propio panel de administración! ¿Cómo puedo recuperar el acceso?**
R2: Esto puede suceder si ha realizado demasiados intentos fallidos.
1.  Si tiene acceso FTP a su tienda, puede deshabilitar temporalmente el módulo. Vaya a `modules/lpro/` y cambie el nombre del archivo `index.php` (por ejemplo, a `index.php.bak`). Esto deshabilitará el módulo.
2.  Inicie sesión en su panel de administración.
3.  Vaya a **Módulos > Gestor de módulos**, busque "Login protection pro" y haga clic en "Configurar".
4.  Vaya a **IPs bloqueadas** y elimine su dirección IP de la lista.
5.  Vuelva a cambiar el nombre de `index.php.bak` a `index.php` en el directorio `modules/lpro/`.
6.  Vuelva a habilitar el módulo si lo deshabilitó en el gestor de módulos.
7.  Ajuste la configuración de `Max Failed Attempts` o `Ban Duration` si se encuentra bloqueado con frecuencia.

**P3: El módulo no parece estar bloqueando ninguna IP, incluso después de muchos intentos fallidos. ¿Qué podría estar mal?**
R3:
1.  **Verifique "Habilitar protección de inicio de sesión":** Asegúrese de que el interruptor principal en la configuración del módulo esté configurado en **SÍ**.
2.  **Verifique "Proteger inicio de sesión de administrador" / "Proteger inicio de sesión de cliente":** Asegúrese de que la protección relevante (administrador o cliente) esté habilitada.
3.  **Revise la configuración:** Verifique que `Max Failed Attempts`, `Attempt Time Window` y `Ban Duration` estén configurados con valores razonables. Si la `Attempt Time Window` es demasiado corta o `Max Failed Attempts` es demasiado alto, podría ser necesario un ataque muy agresivo para activar un bloqueo.
4.  **Borrar caché:** Vaya a **Parámetros avanzados > Rendimiento** y haga clic en "Borrar caché". A veces, la configuración del módulo no se aplica inmediatamente debido al almacenamiento en caché.
5.  **Verifique los registros del servidor:** Los registros de acceso al servidor de su proveedor de alojamiento podrían mostrar si el módulo está encontrando algún error de PHP.

**P4: ¿Este módulo ralentizará mi tienda?**
R4: El módulo está diseñado para ser ligero. Solo realiza comprobaciones durante los intentos de inicio de sesión, que son relativamente poco frecuentes en comparación con las visitas a la página. El impacto en el rendimiento debería ser insignificante. Si nota alguna ralentización, asegúrese de que su instalación de PrestaShop y su servidor cumplan con los requisitos mínimos.

**P5: ¿Cómo traduzco los mensajes del módulo a otros idiomas?**
R5: Aunque este módulo funciona principalmente en segundo plano, cualquier posible mensaje del front-office (como "Demasiados intentos fallidos") o etiquetas del back-office se pueden traducir:
1.  Vaya a **Internacional > Traducciones** en su Back Office de PrestaShop.
2.  Seleccione "Traducciones de módulos instalados".
3.  Elija su tema.
4.  Seleccione el idioma que desea traducir.
5.  Busque el módulo "Login protection pro" y traduzca las cadenas de texto relevantes.

## 4. Guía para desarrolladores y webmasters (Arquitectura técnica y mapa de código)

Esta sección proporciona una inmersión profunda en la estructura técnica del módulo "Login protection pro" para desarrolladores y webmasters.

### 4.1 Resumen de la arquitectura

El módulo `Login protection pro` sigue una arquitectura de módulo estándar de PrestaShop, aprovechando principalmente los Controladores de Administración para su interfaz de gestión y los hooks para su funcionalidad principal. No introduce controladores complejos de front-office ni clases `ObjectModel` personalizadas, sino que se basa en la clase `Configuration` de PrestaShop para la configuración y la interacción directa con la base de datos para registrar intentos y gestionar bloqueos. La lógica del módulo para detectar y bloquear intentos se inyecta a través de los hooks de PrestaShop, específicamente en torno al proceso de autenticación.

### 4.2 Controladores (`controllers/`)

#### Controladores de Front-Office

El módulo **no** contiene ningún controlador de front-office dedicado. Toda la lógica relacionada con el front-office (monitoreo de intentos de inicio de sesión de clientes) se maneja directamente dentro del archivo principal del módulo (`lpro/index.php`) mediante la conexión al proceso de autenticación de PrestaShop.

#### Controladores de administración de Back-Office

El módulo proporciona controladores de administración dedicados para gestionar los intentos de inicio de sesión y los bloqueos.

-   **`controllers/admin/AdminLproAttempts.php`**

    -   **Nombre de la clase:** `AdminLproAttemptsController` (extiende `ModuleAdminController`)
    -   **Responsabilidad:** Este controlador es responsable de mostrar una lista de todos los intentos de inicio de sesión fallidos registrados. Proporciona una vista de cuadrícula de solo lectura de los datos de `lattempt`, lo que permite a los administradores monitorear actividades sospechosas. Normalmente utiliza `HelperList` para renderizar la tabla.
    -   **Entidad gestionada:** `lattempt` (representa un registro de intento de inicio de sesión fallido).
    -   **Nombre de la pestaña:** Intentos de inicio de sesión (visible bajo la entrada del menú principal del módulo).
-   **`controllers/admin/AdminLproBans.php`**

    -   **Nombre de la clase:** `AdminLproBansController` (extiende `ModuleAdminController`)
    -   **Responsabilidad:** Este controlador gestiona la lista de direcciones IP bloqueadas. Proporciona una vista de cuadrícula de los datos de `lban` y permite a los administradores agregar nuevos bloqueos, editar los existentes y eliminar (desbloquear) IPs. Probablemente utiliza `HelperList` para la tabla y `HelperForm` para los formularios de agregar/editar.
    -   **Entidad gestionada:** `lban` (representa un registro de dirección IP bloqueada).
    -   **Nombre de la pestaña:** IPs bloqueadas (visible bajo la entrada del menú principal del módulo).
-   **`controllers/admin/index.php`**

    -   **Ruta exacta del archivo:** `lpro/controllers/admin/index.php`
    -   **Nombre de la clase y clase padre:** No es un archivo de clase.
    -   **Responsabilidad:** Este es un archivo de marcador de posición estándar de PrestaShop. Su propósito principal es evitar la lista de directorios si la configuración del servidor web lo permite, y a veces puede contener una simple redirección o una comprobación de seguridad. No contiene ninguna lógica funcional para el módulo en sí.

### 4.3 Clases y modelos principales (`classes/`)

El módulo **no** contiene ninguna clase personalizada en el directorio `classes/`. Probablemente maneja las interacciones con la base de datos directamente dentro del archivo principal del módulo (`lpro/index.php`) o sus controladores de administración, utilizando métodos de consulta de base de datos estándar de PrestaShop. Esto implica que las entidades `lattempt` y `lban` se gestionan sin clases `ObjectModel` dedicadas, basándose en SQL directo o llamadas a `Db::getInstance()`.

### 4.4 Activos JavaScript (`views/js/`)

El módulo **no** contiene ningún archivo JavaScript personalizado. Esto sugiere que sus interfaces de configuración y gestión se basan completamente en las bibliotecas y comportamientos JavaScript predeterminados de PrestaShop (por ejemplo, para el envío de formularios, el filtrado de tablas).

### 4.5 Hojas de estilo CSS (`views/css/`)

El módulo **no** contiene ningún archivo CSS personalizado. Esto indica que sus interfaces de Back Office (configuración, registros de intentos, listas de bloqueos) heredan el estilo directamente del tema del Back Office de PrestaShop, lo que garantiza una apariencia coherente sin introducir elementos visuales personalizados.

### 4.6 Estructura de plantillas Smarty (`views/templates/`)

-   **Plantillas de administración (`views/templates/admin/`)**:
    -   **`lpro/views/templates/admin/main.tpl`**:
        -   **Propósito:** Esta plantilla se utiliza probablemente para la página de configuración principal del módulo, renderizada por el método `getContent()` en `lpro/index.php`. Contiene la estructura HTML para la configuración descrita en la sección 4.1 (Habilitar protección de inicio de sesión, Intentos fallidos máximos, etc.). Normalmente incluiría elementos de formulario (interruptores, campos de entrada) y potencialmente enlaces a los controladores `AdminLproAttempts` y `AdminLproBans`.

### 4.7 Esquema de la base de datos y mapa de hooks

#### Tablas de la base de datos

El módulo crea tablas de base de datos personalizadas durante su método `install()` (definido en `lpro/index.php`).

-   **`ps_lpro_attempt`**:
    -   **Propósito:** Almacena registros de todos los intentos de inicio de sesión fallidos.
    -   **Campos probables:**
        -   `id_lpro_attempt` (Clave primaria)
        -   `ip_address` (VARCHAR): La dirección IP del intento fallido.
        -   `attempt_time` (DATETIME): Marca de tiempo del intento.
        -   `login_type` (VARCHAR): 'admin' o 'customer'.
        -   `username` (VARCHAR): El nombre de usuario/correo electrónico intentado.
        -   `is_banned` (TINYINT): Indicador que señala si este intento llevó a un bloqueo.
-   **`ps_lpro_ban`**:
    -   **Propósito:** Almacena registros de los bloqueos de IP actualmente activos.
    -   **Campos probables:**
        -   `id_lpro_ban` (Clave primaria)
        -   `ip_address` (VARCHAR): La dirección IP bloqueada.
        -   `ban_start_time` (DATETIME): Cuando comenzó el bloqueo.
        -   `ban_end_time` (DATETIME): Cuando está programado que expire el bloqueo (NULL para bloqueos permanentes).
        -   `reason` (TEXT): Motivo opcional del bloqueo.
        -   `is_permanent` (TINYINT): Indicador para bloqueos permanentes.

#### Tabla de hooks registrados

El módulo registra hooks para interceptar los intentos de inicio de sesión y aplicar su lógica de protección.

| Nombre del Hook | Momento de ejecución | Propósito técnico |
| --- | --- | --- |
| `actionAuthentication` | Después de que un cliente intenta iniciar sesión (front office). | Comprueba si el intento de inicio de sesión del cliente fue exitoso o fallido. Si falló, registra el intento y comprueba las condiciones de bloqueo. |
| `actionAdminLoginController` | Después de que un administrador intenta iniciar sesión (back office). | Comprueba si el intento de inicio de sesión del administrador fue exitoso o fallido. Si falló, registra el intento y comprueba las condiciones de bloqueo. |
| `displayHeader` | En la sección `<head>` de cada página del front-office. | Potencialmente utilizado para incluir CSS/JS (aunque no hay ninguno presente) o para comprobaciones tempranas, aunque es menos probable para la lógica central. Más a menudo para la inicialización general del módulo. |
| `displayRightColumn` | En la columna derecha de las páginas del front-office. | No directamente relevante para la lógica de seguridad. Si se usa, sería para mostrar un mensaje o bloque, lo cual es poco probable para este módulo. |
| `displayLeftColumn` | En la columna izquierda de las páginas del front-office. | Igual que `displayRightColumn`. |
| `displayFooter` | En el pie de página de cada página del front-office. | No directamente relevante para la lógica de seguridad. |
| `displayProductExtraContent` | En la página del producto, dentro de la sección de "contenido extra". | No directamente relevante para la lógica de seguridad. |

**Nota sobre los Hooks:** La lógica central para detectar y bloquear intentos residirá principalmente dentro de los hooks `actionAuthentication` y `actionAdminLoginController`. Otros hooks `display` probablemente se registran por defecto pero no se utilizan activamente para la funcionalidad de seguridad principal del módulo.

## 5. Soporte oficial y actualizaciones

Para las últimas actualizaciones del módulo, correcciones de errores y soporte oficial, inicie sesión en su cuenta de cliente en [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nuestro equipo de soporte está disponible para ayudarle con cualquier problema o pregunta que pueda tener con respecto al módulo "Login protection pro".
