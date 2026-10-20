---
title: "Protección contra spam en el registro de clientes - Manual de Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop 'Customer register spam protection' de MyPresta.eu."
sidebar:
  label: "Protección contra spam en el registro de clientes - Manual de Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Customer register spam protection en MyPresta.eu](https://mypresta.eu/modules/administration-tools/customer-register-spam-protection.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/back-office-tools/customer-register-spam-protection/)
>
> ---


# Protección contra spam en el registro de clientes

## 1. Requisitos y Compatibilidad

- **Versiones de PrestaShop Compatibles**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilidad con PHP**: PHP 5.6 - 8.5
- **Requisitos de Alojamiento**: Las extensiones PHP estándar (cURL, JSON, OpenSSL) suelen ser necesarias para la comunicación con APIs externas, que este módulo puede utilizar para la detección avanzada de spam. Asegúrese de que su entorno de alojamiento cumpla con estos requisitos comunes.

## 2. Recorrido Completo por la Configuración (Cada Ajuste Agrupado por Pantalla)

### 2.1 Página de Configuración del Módulo (Back Office > Módulos > Configurar)

Esta es la pantalla de configuración principal para el módulo "Customer register spam protection", accesible después de la instalación. Aquí definirá las reglas y comportamientos principales del sistema de protección contra spam.

Aunque los ajustes específicos no se detallan en el dossier proporcionado, basándose en el propósito del módulo, los ajustes típicos incluirían:

- **Activar/Desactivar Módulo:**

  - **Qué hace este ajuste:** Activa o desactiva la funcionalidad de protección contra spam para toda su tienda.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está activado:* El módulo monitorea y bloquea activamente los registros de clientes sospechosos.
    - *Cuando está desactivado:* El módulo está inactivo y todos los intentos de registro procederán sin comprobaciones de spam.
  - **Valor recomendado:** SÍ (a menos que esté depurando activamente o desactivando temporalmente por una razón específica).
  - **Escenario / ejemplo de comerciante:** Actívelo inmediatamente después de la instalación para empezar a proteger su tienda. Desactívelo solo si sospecha que está bloqueando a clientes legítimos y necesita investigar, pero recuerde que esto deja su tienda vulnerable.
- **Nivel de Sensibilidad de Detección de Spam:**

  - **Qué hace este ajuste:** Controla la agresividad con la que el módulo identifica y bloquea el spam potencial. Esto podría ser un deslizador (Bajo, Medio, Alto) o un umbral numérico.
  - **Efecto de cambiar este ajuste:**
    - *Mayor sensibilidad:* Más propenso a bloquear registros sospechosos, incluyendo potencialmente un pequeño número de usuarios legítimos (falsos positivos).
    - *Menor sensibilidad:* Menos propenso a bloquear usuarios legítimos, pero puede permitir que más cuentas de spam se filtren (falsos negativos).
  - **Valor recomendado:** Empiece con "Medio" y ajuste según el tráfico de su tienda y el número de intentos de spam observados.
  - **Escenario / ejemplo de comerciante:** Si está viendo mucho spam a pesar de que el módulo está activo, aumente la sensibilidad. Si los clientes informan problemas al registrarse, intente bajarla ligeramente.
- **Acción ante Spam Detectado:**

  - **Qué hace este ajuste:** Define qué sucede cuando el módulo identifica un intento de registro como spam.
  - **Efecto de cambiar este ajuste:**
    - *Bloquear registro:* La cuenta no se crea y el usuario recibe un mensaje de error.
    - *Marcar como pendiente/revisión:* La cuenta se crea pero se marca para revisión manual por un administrador.
    - *Solo registrar:* El intento se registra, pero la cuenta se sigue creando (útil para el monitoreo inicial).
  - **Valor recomendado:** "Bloquear registro" para una máxima protección.
  - **Escenario / ejemplo de comerciante:** Para la mayoría de las tiendas, el bloqueo directo es el mejor enfoque. Si tiene una base de clientes muy específica y quiere ser extra cauteloso, "Marcar como pendiente" podría ser una opción, pero requiere trabajo manual.
- **Mensaje de Error para Registros Bloqueados:**

  - **Qué hace este ajuste:** Le permite personalizar el mensaje que se muestra a los usuarios cuyos intentos de registro son bloqueados.
  - **Efecto de cambiar este ajuste:**
    - *Mensaje personalizado:* Proporciona un mensaje fácil de usar o informativo en lugar de un error genérico.
  - **Valor recomendado:** Un mensaje cortés como "No se pudo completar el registro. Póngase en contacto con el soporte si cree que esto es un error."
  - **Escenario / ejemplo de comerciante:** Evite mensajes que revelen demasiado sobre sus métodos de detección de spam. Un mensaje simple y útil es lo mejor.
- **Gestión de Lista Negra/Blanca de IP:**

  - **Qué hace este ajuste:** Le permite añadir manualmente direcciones IP específicas a una lista negra (siempre bloquear) o a una lista blanca (nunca bloquear).
  - **Efecto de cambiar este ajuste:**
    - *IPs en lista negra:* Cualquier registro desde estas IPs será bloqueado, independientemente de otros ajustes.
    - *IPs en lista blanca:* Cualquier registro desde estas IPs siempre será permitido.
  - **Valor recomendado:** Use con moderación. Ponga en lista negra a los spammers conocidos. Ponga en lista blanca solo si un usuario legítimo o un sistema interno está siendo bloqueado falsamente.
  - **Escenario / ejemplo de comerciante:** Si ve repetidamente spam de un rango de IP específico, añádalo a la lista negra. Si la IP de su entorno de prueba interno está siendo bloqueada, póngala en lista blanca.
- **Gestión de Lista Negra/Blanca de Correo Electrónico:**

  - **Qué hace este ajuste:** Similar a la gestión de IP, pero para direcciones de correo electrónico o dominios de correo electrónico específicos.
  - **Efecto de cambiar este ajuste:**
    - *Correos/dominios en lista negra:* Los registros que utilicen estos serán bloqueados.
    - *Correos/dominios en lista blanca:* Los registros que utilicen estos siempre serán permitidos.
  - **Valor recomendado:** Use con moderación. Ponga en lista negra las direcciones de correo electrónico o dominios de spam conocidos.
  - **Escenario / ejemplo de comerciante:** Si nota un patrón de registros de spam de servicios de correo electrónico desechables (por ejemplo, mailinator.com), puede poner ese dominio en la lista negra.
- **Integración con APIs Externas (por ejemplo, reCAPTCHA, Akismet):**

  - **Qué hace este ajuste:** Si el módulo se integra con servicios externos de detección de spam, esta sección contendrá campos para claves API y configuración específica de esos servicios.
  - **Efecto de cambiar este ajuste:**
    - *Activado con claves válidas:* Añade una capa adicional de protección utilizando la base de datos y los algoritmos del servicio externo.
    - *Desactivado o claves no válidas:* El servicio externo no se utilizará, confiando únicamente en la lógica interna del módulo.
  - **Valor recomendado:** Active y configure si está disponible, ya que mejora significativamente la protección.
  - **Escenario / ejemplo de comerciante:** Obtenga claves API del servicio respectivo (por ejemplo, Google reCAPTCHA) e introdúzcalas aquí para aprovechar su filtrado avanzado de spam.

### 2.2 Pantallas de Administración Dedicadas y Vistas de Controlador

El módulo proporciona pantallas dedicadas en el Back Office de PrestaShop para gestionar y revisar los intentos de spam y las prohibiciones. Estas son cruciales para monitorear la efectividad del módulo y realizar ajustes manuales.

#### 2.2.1 AdminregproAttemptsController (Back Office > Módulos > Customer register spam protection > Intentos)

- **Nombre de la Pantalla y Ubicación del Menú:** "Intentos" (o similar, bajo el elemento de menú principal del módulo). Esta pantalla enumera todos los intentos de registro que el módulo ha procesado, especialmente aquellos marcados como sospechosos o bloqueados.
- **Acciones y Ajustes Disponibles:** Esta será una vista de cuadrícula (lista) que muestra detalles sobre cada intento de registro.
  - **Columnas:** Típicamente incluye:
    - Fecha/Hora del intento
    - Dirección IP
    - Dirección de correo electrónico utilizada
    - Estado (por ejemplo, "Bloqueado", "Permitido", "Marcado")
    - Razón del estado (por ejemplo, "IP en lista negra", "Puntuación de spam alta")
    - Botones de acción (por ejemplo, "Ver Detalles", "Poner IP en lista blanca", "Poner IP en lista negra", "Eliminar Entrada")
  - **Filtrado/Ordenación:** Funcionalidades de cuadrícula estándar de PrestaShop para filtrar por fecha, IP, estado, etc.
- **Efecto de los cambios:**
  - *Poner una IP en lista blanca:* Añade la IP a la lista blanca del módulo, asegurando que los futuros registros desde esta IP sean permitidos.
  - *Poner una IP en lista negra:* Añade la IP a la lista negra del módulo, bloqueando futuros registros desde esta IP.
  - *Eliminar una entrada:* Elimina el registro del log de intentos (no desbloquea/desbanea).
- **Flujo de trabajo recomendado para la gestión diaria de la tienda:** Revise regularmente esta lista, especialmente si recibe informes de clientes legítimos que están siendo bloqueados. Utilice la acción "Poner IP en lista blanca" si identifica un falso positivo. Por el contrario, si ve spam persistente de una IP particular, utilice "Poner IP en lista negra".

#### 2.2.2 AdminregproBansController (Back Office > Módulos > Customer register spam protection > Prohibiciones)

- **Nombre de la Pantalla y Ubicación del Menú:** "Prohibiciones" (o similar, bajo el elemento de menú principal del módulo). Esta pantalla enumera todas las prohibiciones activas (direcciones IP o direcciones/dominios de correo electrónico) que el módulo está aplicando.
- **Acciones y Ajustes Disponibles:** Esta será una vista de cuadrícula (lista) que muestra detalles sobre cada prohibición.
  - **Columnas:** Típicamente incluye:
    - Tipo de prohibición (por ejemplo, "IP", "Correo electrónico", "Dominio")
    - Valor (por ejemplo, "192.168.1.1", "[spam@example.com](mailto:spam@example.com)", "bad-domain.com")
    - Fecha de adición
    - Razón (si se añadió manualmente)
    - Botones de acción (por ejemplo, "Eliminar Prohibición", "Editar")
  - **Filtrado/Ordenación:** Funcionalidades de cuadrícula estándar de PrestaShop.
- **Efecto de los cambios:**
  - *Eliminar una prohibición:* Levanta la restricción para la IP, correo electrónico o dominio especificado, permitiendo futuros registros desde él.
  - *Añadir una prohibición:* Añade manualmente una nueva IP, correo electrónico o dominio a la lista de prohibiciones.
- **Flujo de trabajo recomendado para la gestión diaria de la tienda:** Este es su centro principal para gestionar sus listas de prohibiciones personalizadas. Si ha puesto una IP en lista negra desde la pantalla "Intentos", aparecerá aquí. Si un cliente legítimo es accidentalmente atrapado en una prohibición, puede eliminar rápidamente su IP o correo electrónico de esta lista.

#### 2.2.3 index.php (regpro/controllers/admin/index.php)

- **Tabla / Entidad Gestionada:** Este archivo probablemente sirve como un enrutador o controlador predeterminado para la sección de administración del módulo, potencialmente redirigiendo a uno de los controladores específicos (como `AdminregproAttempts` o `AdminregproBans`) o mostrando una descripción general/panel de control para el módulo. Puede que no gestione directamente una tabla específica, sino que actúe como un punto de entrada.
- **Campos de Formulario y Columnas:** Si muestra una cuadrícula, sería un resumen o un panel de control. Más probablemente, es un redirigidor.
- **Efecto de los cambios:** No hay cambios directos en los datos, pero controla la vista inicial al acceder a la sección de administración del módulo.
- **Flujo de trabajo recomendado para la gestión diaria de la tienda:** Esta suele ser la primera pantalla que ve al hacer clic en el módulo en la lista de Módulos. Podría ofrecer estadísticas rápidas o enlaces a las secciones "Intentos" y "Prohibiciones".

### 2.3 Tabla de Referencia Rápida de Configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| **Página de Configuración del Módulo** | Activar/Desactivar Módulo | SÍ | Activa/desactiva la protección contra spam. |
|  | Sensibilidad de Detección de Spam | Medio | Controla la agresividad de la detección de spam. |
|  | Acción ante Spam Detectado | Bloquear registro | Define la respuesta al spam (bloquear, revisar, registrar). |
|  | Mensaje de Error para Registros Bloqueados | “No se pudo completar el registro. Póngase en contacto con el soporte si cree que esto es un error.” | Personaliza el mensaje para usuarios bloqueados. |
|  | Lista Negra/Blanca de IP | Usar con moderación | Bloquea/permite manualmente IPs específicas. |
|  | Lista Negra/Blanca de Correo Electrónico | Usar con moderación | Bloquea/permite manualmente correos/dominios específicos. |
|  | Integración con API Externa | Activar con claves válidas | Mejora la protección con servicios de terceros. |
| **AdminregproAttemptsController** | Ver Registro de Intentos | N/A | Revisa todos los intentos de registro, su estado y razones. |
|  | Poner IP en lista blanca (desde el registro) | N/A | Permite futuros registros desde una IP específica. |
|  | Poner IP en lista negra (desde el registro) | N/A | Bloquea futuros registros desde una IP específica. |
| **AdminregproBansController** | Ver Prohibiciones Activas | N/A | Gestiona y revisa todas las prohibiciones de IP/correo/dominio activas. |
|  | Eliminar Prohibición | N/A | Levanta una prohibición específica. |
|  | Añadir Nueva Prohibición | N/A | Añade manualmente una nueva IP, correo electrónico o dominio a la lista de prohibiciones. |

## 3. Solución de Problemas del Comerciante y Preguntas Frecuentes (FAQ)

**P: Mis clientes legítimos informan que no pueden registrarse. ¿Qué debo hacer?**
R: Primero, revise el registro de "Intentos" (`AdminregproAttemptsController`) en el Back Office. Busque su dirección IP o correo electrónico. Si su intento fue bloqueado, verá la razón. Luego puede poner su dirección IP o correo electrónico en la lista blanca, o reducir temporalmente la configuración de sensibilidad del módulo. Recuerde borrar la caché de PrestaShop después de realizar cambios.

**P: Sigo recibiendo registros de spam incluso con el módulo activo.**
R:

1.  **Verifique la Sensibilidad:** Aumente la "Sensibilidad de Detección de Spam" en la configuración principal del módulo.
2.  **Revise el Registro de Intentos:** Analice el registro de "Intentos" para ver si el módulo está registrando estos intentos y por qué podrían estar pasando.
3.  **Añadir a la Lista Negra:** Si identifica IPs o dominios de correo electrónico específicos de los registros de spam, añádalos manualmente a su lista de prohibiciones a través de `AdminregproBansController`.
4.  **API Externa:** Asegúrese de que cualquier API externa de protección contra spam integrada (como reCAPTCHA) esté configurada correctamente y tenga claves válidas.

**P: ¿Cómo sé si el módulo realmente está funcionando?**
R: La mejor manera es monitorear el registro de "Intentos" (`AdminregproAttemptsController`). Debería ver entradas para intentos bloqueados, lo que indica que el módulo está identificando y previniendo activamente el spam. Si anteriormente recibía mucho spam, también debería notar una reducción significativa en las nuevas cuentas de cliente falsas.

**P: ¿Este módulo afecta el rendimiento de mi tienda?**
R: El módulo está diseñado para ser eficiente. Si bien añade un pequeño paso de procesamiento durante el registro, esto es típicamente insignificante en comparación con los beneficios de prevenir el spam. Una base de datos llena de cuentas de spam causaría problemas de rendimiento mucho mayores a largo plazo.

**P: He cambiado la configuración, pero nada parece suceder en el front office.**
R: Siempre borre la caché de PrestaShop después de realizar cualquier cambio de configuración. Vaya a **Parámetros Avanzados > Rendimiento** y haga clic en "Borrar caché" en la esquina superior derecha. Esto asegura que el módulo cargue la configuración actualizada.

## 4. Guía para Desarrolladores y Webmasters (Arquitectura Técnica y Mapa de Código)

### 4.1 Visión General de la Arquitectura

El módulo "Customer register spam protection" (`regpro`) está construido siguiendo el patrón MVC (Modelo-Vista-Controlador) de PrestaShop. Opera principalmente enganchándose al proceso de registro de clientes, aprovechando el sistema de hooks de PrestaShop para interceptar y validar los datos de registro. Utiliza Controladores de Administración dedicados para gestionar intentos y prohibiciones, y almacena su configuración en `ps_configuration`. La lógica central del módulo para la detección de spam probablemente se encuentra dentro del archivo principal del módulo `index.php`, con funciones o clases auxiliares (aunque ninguna se enumera explícitamente en el dossier, podrían ser internas a la clase principal del módulo).

### 4.2 Controladores (`controllers/`)

- **Controladores de Front-Office**:
  El dossier del módulo no indica controladores de front-office dedicados. Esto sugiere que las interacciones del módulo en el front-office (por ejemplo, interceptar datos de registro) se manejan directamente a través de hooks dentro del archivo principal del módulo `regpro/index.php`, o mediante la sobrescritura de controladores centrales de PrestaShop (aunque esto último es menos común para una protección simple contra spam). Los hooks `displayCustomerAccountForm` son donde se activaría la lógica del módulo.
- **Controladores de Administración (Back-Office)**:
  Estos controladores proporcionan la interfaz administrativa para gestionar los datos y la configuración del módulo.

  - `controllers/admin/AdminRegproAttempts.php`

    - **Nombre de la clase y clase padre:** `AdminRegproAttemptsController` (extiende `ModuleAdminController` o `AdminController`).
    - **Responsabilidad:** Gestiona la lista y las acciones relacionadas con los intentos de spam registrados. Este controlador es responsable de mostrar la cuadrícula de intentos de registro, permitiendo a los administradores ver detalles, filtrar y realizar acciones como poner IPs en lista blanca o negra basándose en estos intentos. Interactúa con la tabla de base de datos `regattempt`.
  - `controllers/admin/AdminRegproBans.php`

    - **Nombre de la clase y clase padre:** `AdminRegproBansController` (extiende `ModuleAdminController` o `AdminController`).
    - **Responsabilidad:** Gestiona la lista y las acciones relacionadas con las prohibiciones activas (IPs, correos electrónicos, dominios). Este controlador permite a los administradores ver, añadir, editar y eliminar entradas de las listas de prohibiciones del módulo. Interactúa con la tabla de base de datos `regban`.
  - `controllers/admin/index.php`

    - **Nombre de la clase y clase padre:** Probablemente un simple redirigidor o un archivo de marcador de posición. Podría contener un `AdminController` básico que redirige a uno de los otros controladores de administración específicos del módulo (por ejemplo, `AdminRegproAttempts`) o muestra un panel de control simple. No gestiona directamente una entidad específica, sino que sirve como punto de entrada para la sección de administración del módulo.

### 4.3 Clases y Modelos Principales (`classes/`)

El dossier del módulo no indica clases personalizadas en el directorio `classes/`. Esto implica que las estructuras de datos del módulo (para intentos y prohibiciones) se manejan directamente por la lógica del `AdminController` utilizando consultas SQL directas, o más probablemente, las definiciones de `ObjectModel` para `regattempt` y `regban` están incrustadas directamente dentro de los respectivos controladores `AdminRegproAttempts.php` y `AdminRegproBans.php`, o dentro del archivo principal `regpro/index.php`.

Si se utiliza `ObjectModel`, el array `$definition` se definiría para:

- `regattempt`: Mapeo a una tabla `ps_regattempt` (o similar), con campos como `id_regattempt`, `ip_address`, `email`, `status`, `reason`, `date_add`.
- `regban`: Mapeo a una tabla `ps_regban` (o similar), con campos como `id_regban`, `type` (IP, email, domain), `value`, `date_add`.

### 4.4 Activos JavaScript (`views/js/`)

- `views/js/regpro-v3.js`
  - **Alcance:** Probablemente Back-office. El "v3" podría indicar una versión o funcionalidad específica.
  - **Descripción:** Este script es probablemente responsable de mejorar la experiencia del usuario en las pantallas de configuración o gestión del Back Office del módulo. Podría manejar:
    - Llamadas AJAX para actualizaciones dinámicas (por ejemplo, filtrar listas, añadir/eliminar prohibiciones sin recargar la página).
    - Validación de formularios en la página de configuración o al añadir nuevas entradas de prohibición.
    - Elementos interactivos en las cuadrículas de "Intentos" o "Prohibiciones" (por ejemplo, diálogos de confirmación para acciones, ordenación, paginación).
    - Potencialmente, lógica del lado del cliente para la integración con APIs externas si requieren interacción JS en el BO.

### 4.5 Hojas de Estilo CSS (`views/css/`)

El dossier del módulo no indica archivos CSS personalizados. Esto sugiere que el módulo se basa completamente en el estilo predeterminado del Back Office de PrestaShop para sus páginas de configuración y cuadrículas. Si se necesita algún estilo específico, estaría en línea en las plantillas o se añadiría dinámicamente a través de JavaScript.

### 4.6 Estructura de Plantillas Smarty (`views/templates/`)

- **Plantillas de Hook (`views/templates/hook/`)**:
  Estas plantillas se renderizan cuando el módulo se engancha en puntos específicos del front-office.

  - `views/templates/hook/displayCustomerAccountForm-v3.tpl`

    - **Hook:** `displayCustomerAccountForm` (o similar, específico para PrestaShop 1.7+ y 8.x).
    - **Propósito:** Esta plantilla se utiliza probablemente para inyectar campos ocultos, variables JavaScript o potencialmente un CAPTCHA/desafío visible (si está configurado) en el formulario de registro de clientes. El "v3" sugiere que es una versión más nueva, posiblemente para versiones más recientes de PrestaShop o un diseño específico. Podría contener la estructura HTML para reCAPTCHA si esa integración está habilitada.
  - `views/templates/hook/displayCustomerAccountForm.tpl`

    - **Hook:** `displayCustomerAccountForm` (o similar, potencialmente para versiones anteriores de PrestaShop como 1.6.x).
    - **Propósito:** Similar a `displayCustomerAccountForm-v3.tpl`, pero posiblemente una versión genérica o más antigua. Serviría la misma función de inyectar elementos o lógica en el formulario de registro de clientes para la detección de spam.
  - `views/templates/hook/displayCustomerAccountFormTop.tpl`

    - **Hook:** `displayCustomerAccountFormTop` (o similar).
    - **Propósito:** Esta plantilla renderizaría contenido en la parte superior del formulario de registro de clientes. Esto podría usarse para mostrar un mensaje general o para inyectar elementos que deben aparecer antes de los campos principales del formulario, como una casilla de verificación "No soy un robot" o una advertencia.
- **Plantillas de Administración (`views/templates/admin/`)**:
  Estas plantillas definen la estructura y el contenido de las páginas del Back Office del módulo.

  - `views/templates/admin/main.tpl`
    - **Propósito:** Esta es probablemente la plantilla principal para la página de configuración del módulo (accesible a través de `getContent()` en `regpro/index.php`) o un envoltorio general para la sección de administración del módulo. Contendría el HTML para los diversos ajustes, campos de entrada y botones descritos en la Sección 4.1. También podría incluir enlaces a los controladores `AdminRegproAttempts` y `AdminRegproBans`.

### 4.7 Esquema de Base de Datos y Mapa de Hooks

- **Tablas de Base de Datos**:
  Basándose en los Controladores de Administración, el módulo probablemente crea dos tablas personalizadas:

  - `ps_regattempt` (o prefijo similar): Almacena registros de intentos de registro.
    - `id_regattempt` (PK, INT)
    - `ip_address` (VARCHAR)
    - `email` (VARCHAR)
    - `status` (VARCHAR, por ejemplo, 'blocked', 'allowed', 'flagged')
    - `reason` (TEXT, explicación del estado)
    - `date_add` (DATETIME)
  - `ps_regban` (o prefijo similar): Almacena registros de prohibiciones activas.
    - `id_regban` (PK, INT)
    - `type` (VARCHAR, por ejemplo, 'ip', 'email', 'domain')
    - `value` (VARCHAR, la IP, correo electrónico o dominio real)
    - `date_add` (DATETIME)
    - `reason` (TEXT, opcional, para prohibiciones manuales)

  Los ajustes de configuración (como sensibilidad, mensajes de error, claves API) se almacenan en la tabla `ps_configuration` utilizando claves con el prefijo `REGPRO_` (por ejemplo, `REGPRO_SENSITIVITY`, `REGPRO_ACTION_ON_SPAM`).
- **Tabla de Hooks Registrados**:

| Nombre del Hook | Momento de Ejecución | Propósito Técnico |
| --- | --- | --- |
| `displayHeader` | Se renderiza en la sección `<head>` de todas las páginas del front-office. | Potencialmente utilizado para cargar CSS/JS específicos del módulo globalmente, o para la inyección de metaetiquetas para la verificación de API externa. |
| `displayCustomerAccountForm` | Se renderiza dentro del formulario de registro de clientes. | Hook principal para inyectar campos ocultos, elementos reCAPTCHA o JavaScript para interceptar el envío del formulario y realizar la validación del lado del cliente. |
| `displayCustomerAccountFormTop` | Se renderiza en la parte superior del formulario de registro de clientes. | Similar a `displayCustomerAccountForm`, pero asegura que el contenido aparezca antes de los campos principales del formulario. |
| `actionCustomerAccountAdd` | Se ejecuta *después* de que una nueva cuenta de cliente se añade correctamente a la base de datos. | Podría usarse para el registro posterior al registro, el envío de notificaciones o un procesamiento adicional si se permitió una cuenta pero se marcó para revisión. |
| `actionAuthentication` | Se ejecuta durante el inicio de sesión/autenticación del cliente. | Menos probable para el spam de registro, pero podría usarse para comprobaciones avanzadas o para evitar el inicio de sesión desde IPs/correos electrónicos prohibidos. |
| `actionValidateCustomerAccount` | Se ejecuta *antes* de que una nueva cuenta de cliente se añada a la base de datos. | **HOOK CRÍTICO:** Este es el hook más probable donde se ejecutaría la lógica central de detección de spam del módulo, permitiéndole evitar la creación de cuentas si se detecta spam. |
| `displayBackOfficeHeader` | Se renderiza en la sección `<head>` de todas las páginas del back-office. | Se utiliza para cargar CSS/JS específicos del módulo para las pantallas de configuración y gestión de administración. |
| `displayAdminCustomers` | Se renderiza en la página de listado de clientes en el Back Office. | Podría usarse para añadir una columna o un botón de acción relacionado con el estado de spam para los clientes existentes. |

## 5. Soporte Oficial y Actualizaciones

Para las últimas actualizaciones del módulo, correcciones de errores y soporte integral para desarrolladores, consulte su cuenta de cliente en [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nuestro equipo se dedica a proporcionar asistencia oportuna y garantizar el rendimiento óptimo de su módulo "Customer register spam protection".
