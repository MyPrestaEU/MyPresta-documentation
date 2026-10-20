---
title: "Copia de seguridad de la base de datos localmente y en la nube - Manual del Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop 'Copia de seguridad de la base de datos localmente y en la nube' de MyPresta.eu."
sidebar:
  label: "Copia de seguridad de la base de datos localmente y en la nube - Manual del Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Database backup locally and in cloud en MyPresta.eu](https://mypresta.eu/modules/administration-tools/database-backup-locally-and-in-cloud.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/back-office-tools/database-backup-locally-and-in-cloud/)
>
> ---


# Copia de seguridad de la base de datos localmente y en la nube

## 1. Requisitos y compatibilidad

- **Versiones de PrestaShop compatibles**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilidad con PHP**: PHP 7.1 - 8.5
- **Requisitos de alojamiento**: Extensiones PHP estándar (cURL, JSON, OpenSSL). Recursos de servidor suficientes (CPU, memoria) para la exportación de la base de datos, especialmente para bases de datos muy grandes, aunque el módulo está diseñado para mitigar estos problemas con la fragmentación. Permisos de escritura para el directorio de copia de seguridad en su servidor.

## 2. Recorrido completo por la configuración (Cada ajuste agrupado por pantalla)

El módulo "Copia de seguridad de la base de datos localmente y en la nube" proporciona una interfaz completa para gestionar sus copias de seguridad. Interactuará principalmente con dos áreas principales: la página de configuración principal del módulo y su pantalla de administración dedicada "Mis Copias de Seguridad".

### 2.1 Página de configuración principal del módulo (Back Office > Módulos > Gestor de módulos > Configurar "Copia de seguridad de la base de datos localmente y en la nube")

Esta página de configuración inicial (`mybackups/index.php` a través de `getContent()`) gestiona la configuración básica y la integración del módulo.

#### Ajustes generales

- **Qué hace este ajuste:** Estos ajustes controlan aspectos fundamentales de cómo opera el módulo y se integra con su entorno PrestaShop.
- **Efecto de cambiar este ajuste:** Ajustarlos puede afectar el rendimiento, la seguridad y la fiabilidad general de sus copias de seguridad.
- **Valor recomendado:** Generalmente, mantenga los valores predeterminados a menos que tenga una razón específica o se lo aconseje el soporte.

#### Integraciones de almacenamiento en la nube

- **Qué hace este ajuste:** Esta sección le permite conectar su tienda PrestaShop a varios proveedores de almacenamiento en la nube donde se almacenarán sus copias de seguridad. Cada proveedor (Google Drive, Dropbox, FTP/FTPS, Amazon S3) tendrá su propio conjunto de detalles de conexión.
- **Efecto de cambiar este ajuste:** La conexión exitosa a un servicio en la nube habilita ese servicio como destino de copia de seguridad. Las credenciales incorrectas evitarán que las copias de seguridad se carguen en esa nube específica.
- **Valor recomendado:** Conéctese a al menos un proveedor de almacenamiento en la nube para copias de seguridad externas. Google Drive y Dropbox suelen ser los más fáciles de configurar para la mayoría de los comerciantes.
- **Escenario / ejemplo de comerciante:** Desea almacenar sus copias de seguridad en Google Drive. Haría clic en el botón "Conectar a Google Drive", seguiría los pasos de autenticación y otorgaría al módulo permiso para acceder a una carpeta específica en su Google Drive. Esto asegura que, incluso si su servidor falla, sus copias de seguridad estén seguras en la nube.

### 2.2 Pantalla de administración dedicada: Mis Copias de Seguridad (Back Office > Mis Copias de Seguridad)

Este es el centro neurálgico para gestionar todas sus copias de seguridad de la base de datos. Encontrará esta pantalla bajo un nuevo elemento de menú, típicamente llamado "Mis Copias de Seguridad" o similar, añadido a la navegación de su Back Office de PrestaShop. Esta pantalla funciona con `mybackups/controllers/admin/AdminMyBackupsController.php`.

#### Panel de control y lista de copias de seguridad

- **Nombre de la pantalla y ubicación del menú:** Encontrará "Mis Copias de Seguridad" en el menú principal de PrestaShop, generalmente agrupado con "Administración" o "Parámetros avanzados".
- **Acciones y configuraciones disponibles:**
  - **Lista de copias de seguridad:** Esta tabla muestra todas sus copias de seguridad de la base de datos existentes, ya sean almacenadas localmente o en la nube. Cada entrada suele mostrar:
    - **Fecha/Hora:** Cuándo se creó la copia de seguridad.
    - **Tamaño:** El tamaño del archivo de copia de seguridad comprimido.
    - **Ubicación:** Dónde se almacena la copia de seguridad (Local, Google Drive, Dropbox, FTP, S3).
    - **Acciones:**
      - **Descargar:** Descargar el archivo de copia de seguridad a su computadora.
      - **Restaurar:** Iniciar un proceso de restauración de la base de datos utilizando esta copia de seguridad. (¡Tenga mucho cuidado con esta acción, ya que sobrescribirá su base de datos actual!)
      - **Eliminar:** Eliminar el archivo de copia de seguridad de su ubicación de almacenamiento.
  - **Botón Crear nueva copia de seguridad:** Un botón prominente para iniciar manualmente una nueva copia de seguridad de la base de datos.
  - **Estado del almacenamiento en la nube:** Indicadores visuales que muestran qué servicios en la nube están actualmente conectados y disponibles.
  - **Copias de seguridad programadas:** Una sección para ver y gestionar sus tareas de copia de seguridad automatizadas (tareas cron).
- **Efecto de los cambios:**
  - **Crear una nueva copia de seguridad:** Genera un nuevo volcado SQL comprimido de su base de datos y lo almacena en las ubicaciones configuradas (local y/o en la nube).
  - **Restaurar una copia de seguridad:** Reemplaza su base de datos activa actual con los datos del archivo de copia de seguridad seleccionado. Esta es una acción potente y potencialmente destructiva; asegúrese siempre de tener una copia de seguridad reciente antes de intentar una restauración.
  - **Eliminar una copia de seguridad:** Elimina permanentemente el archivo de copia de seguridad de su almacenamiento.
- **Flujo de trabajo recomendado para la gestión diaria de la tienda:**
  1.  **Configuración inicial:** Conéctese a sus proveedores de almacenamiento en la nube preferidos en la página de configuración del módulo.
  2.  **Programar copias de seguridad:** Configure una tarea cron (consulte "Casos de uso prácticos" a continuación) para crear copias de seguridad automáticamente diaria o semanalmente, según la actividad de su tienda. Asegúrese de que estas copias de seguridad programadas se envíen a al menos una ubicación en la nube.
  3.  **Monitoreo regular:** Verifique periódicamente el panel de control "Mis Copias de Seguridad" para asegurarse de que las copias de seguridad se estén creando correctamente y de que sus conexiones a la nube estén activas.
  4.  **Copia de seguridad manual (opcional):** Cree una copia de seguridad manual antes de cualquier cambio importante en la tienda (por ejemplo, instalaciones de módulos, actualizaciones de temas, importaciones de productos).
  5.  **Restauración de prueba (CRÍTICO):** Ocasionalmente, realice una restauración de prueba en un *entorno de desarrollo o staging* (NUNCA en su tienda en vivo sin extrema precaución) para asegurarse de que sus copias de seguridad sean válidas y que el proceso de restauración funcione como se espera.

#### Formulario de creación de copia de seguridad

Cuando haga clic en "Crear nueva copia de seguridad", normalmente se le presentarán opciones:

- **Nombre de la copia de seguridad:**
  - **Qué hace este ajuste:** Le permite dar un nombre personalizado a su archivo de copia de seguridad para una fácil identificación.
  - **Efecto de cambiar este ajuste:** El archivo de copia de seguridad se guardará con este nombre (por ejemplo, `mi-tienda-copia-seguridad-2023-10-27.sql.zip`).
  - **Valor recomendado:** Utilice un nombre descriptivo, quizás incluyendo la fecha o una breve nota sobre el motivo de la copia de seguridad (por ejemplo, "Copia de seguridad previa a la actualización").
- **Ubicaciones de almacenamiento:**
  - **Qué hace este ajuste:** Seleccione dónde debe guardarse el archivo de copia de seguridad. Las opciones suelen incluir "Servidor local" y cualquier servicio en la nube conectado (Google Drive, Dropbox, FTP, S3).
  - **Efecto de cambiar este ajuste:** La copia de seguridad se almacenará solo en las ubicaciones seleccionadas.
  - **Valor recomendado:** Seleccione siempre "Servidor local" y al menos una opción de almacenamiento en la nube para redundancia.
- **Excluir tablas:**
  - **Qué hace este ajuste:** Le permite seleccionar tablas de base de datos específicas que *no* deben incluirse en la copia de seguridad. Esto puede ser útil para tablas muy grandes que contienen datos no críticos o fácilmente regenerables (por ejemplo, tablas de caché, tablas de registro).
  - **Efecto de cambiar este ajuste:** Las tablas seleccionadas se omitirán, lo que resultará en un archivo de copia de seguridad más pequeño.
  - **Valor recomendado:** Para la mayoría de los comerciantes, déjelo vacío para hacer una copia de seguridad de toda la base de datos. Solo excluya tablas si comprende las implicaciones y está tratando de reducir el tamaño de la copia de seguridad debido a graves restricciones de alojamiento.
- **Botón Iniciar copia de seguridad:** Inicia el proceso de copia de seguridad. Normalmente verá una barra de progreso o actualizaciones de estado a medida que se crea y carga la copia de seguridad.

### 2.3 Tabla de referencia rápida de configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| **Página de configuración del módulo** | Ajustes generales | Predeterminado | Controla las operaciones fundamentales del módulo, el rendimiento y la seguridad. |
|  | Integración con Google Drive | Conectar | Habilita Google Drive como destino de copia de seguridad. |
|  | Integración con Dropbox | Conectar | Habilita Dropbox como destino de copia de seguridad. |
|  | Integración con FTP/FTPS | Configurar | Habilita FTP/FTPS como destino de copia de seguridad. |
|  | Integración con Amazon S3 | Configurar | Habilita Amazon S3 como destino de copia de seguridad. |
| **Panel de control de Mis Copias de Seguridad** | Crear nueva copia de seguridad | N/A | Inicia manualmente una nueva copia de seguridad de la base de datos. |
|  | Lista de copias de seguridad (Descargar) | N/A | Descarga un archivo de copia de seguridad a su computadora local. |
|  | Lista de copias de seguridad (Restaurar) | N/A | **CRÍTICO:** Sobrescribe la base de datos actual con la copia de seguridad seleccionada. Úselo con extrema precaución, preferiblemente en un entorno de staging. |
|  | Lista de copias de seguridad (Eliminar) | N/A | Elimina permanentemente un archivo de copia de seguridad de su ubicación de almacenamiento. |
| **Formulario de creación de copia de seguridad** | Nombre de la copia de seguridad | Autogenerado | Nombre personalizado para el archivo de copia de seguridad. |
|  | Ubicaciones de almacenamiento | Local + Nube | Selecciona dónde se guardará la copia de seguridad (servidor local, servicios en la nube). |
|  | Excluir tablas | Ninguna | Omite las tablas especificadas de la copia de seguridad para reducir el tamaño del archivo. |

## 3. Solución de problemas para comerciantes y preguntas frecuentes (FAQ)

**P: Mis copias de seguridad están fallando o tardan demasiado. ¿Qué debo hacer?**
R:

-   **Verifique los recursos del servidor:** Las bases de datos grandes requieren una cantidad significativa de memoria del servidor y tiempo de ejecución. Si bien el módulo divide las exportaciones en fragmentos, los entornos de alojamiento muy restringidos aún pueden tener dificultades. Contacte a su proveedor de alojamiento para verificar los límites de memoria PHP (`memory_limit`) y el tiempo máximo de ejecución (`max_execution_time`).
-   **Borre la caché:** A veces, la caché de PrestaShop puede interferir. Vaya a **Parámetros avanzados > Rendimiento** y haga clic en "Borrar caché".
-   **Excluya tablas:** Considere excluir tablas no críticas (como tablas de caché o estadísticas) de la copia de seguridad si son muy grandes. Esto puede reducir significativamente el tamaño y el tiempo de la copia de seguridad.
-   **Verifique los registros de errores:** Busque en los registros de errores de PrestaShop (generalmente `var/logs/` o `app/logs/` según la versión de PS) o en los registros de errores de PHP de su servidor mensajes de error específicos.

**P: Me conecté a Google Drive/Dropbox, pero no veo mis copias de seguridad allí.**
R:

-   **Verifique el estado de la conexión:** Vaya a la página de configuración del módulo y verifique que su servicio en la nube aparezca como "Conectado". Si no, intente volver a conectarse.
-   **Permisos de carpeta:** Asegúrese de que el módulo tenga los permisos necesarios para escribir en la carpeta especificada en su almacenamiento en la nube. Para Google Drive/Dropbox, el módulo generalmente crea su propia carpeta.
-   **Prueba de carga manual:** Intente crear una pequeña copia de seguridad manual y seleccione explícitamente el servicio en la nube como destino para ver si se carga correctamente.
-   **Verifique el almacenamiento en la nube directamente:** Inicie sesión en su cuenta de Google Drive o Dropbox a través de su sitio web y explore manualmente las carpetas para ver si las copias de seguridad están allí, quizás en una ubicación inesperada.

**P: ¿Cómo restauro mi base de datos desde una copia de seguridad?**
R:

-   **ADVERTENCIA:** La restauración de una base de datos sobrescribirá su base de datos activa actual. Esta es una acción altamente destructiva. **Siempre tenga una copia de seguridad reciente de su base de datos actual antes de intentar una restauración.**
-   Vaya a **Back Office > Mis Copias de Seguridad**.
-   Localice el archivo de copia de seguridad que desea restaurar en la lista.
-   Haga clic en el botón "Restaurar" junto a esa copia de seguridad.
-   Siga las instrucciones en pantalla. El módulo lo guiará a través del proceso.
-   Si su tienda está completamente inactiva, es posible que deba cargar manualmente el archivo de copia de seguridad a través de FTP y luego usar la interfaz del módulo o una herramienta como phpMyAdmin para importarlo. En situaciones tan críticas, es mejor consultar con un desarrollador o su proveedor de alojamiento.

**P: ¿Qué sucede si mi servidor se queda sin espacio en disco durante una copia de seguridad local?**
R: Es probable que el proceso de copia de seguridad falle y verá un mensaje de error relacionado con el espacio en disco. Asegúrese de tener suficiente espacio libre en disco en su servidor, especialmente si está almacenando varias copias de seguridad locales o tiene una base de datos muy grande. Elimine regularmente las copias de seguridad locales antiguas que ya se hayan cargado de forma segura en la nube.

**P: Mi tema personalizado no se muestra correctamente después de una restauración.**
R: Las copias de seguridad de la base de datos restauran principalmente sus datos. Los archivos de tema, los archivos de módulo y las imágenes suelen almacenarse en el sistema de archivos de su servidor, no directamente en la base de datos.

-   **Borrar caché:** Vaya a **Parámetros avanzados > Rendimiento** y borre todas las cachés (Smarty, sistema de archivos, etc.).
-   **Verifique el sistema de archivos:** Asegúrese de que todos sus archivos de tema, archivos de módulo y carpetas de imágenes estén presentes y tengan los permisos correctos en el servidor. Una restauración de la base de datos no afectará a estos archivos. Si ha restaurado desde una copia de seguridad muy antigua, es posible que algunas configuraciones de módulos deban volver a guardarse en el Back Office.

## 4. Guía para desarrolladores y webmasters (Arquitectura técnica y mapa de código)

Esta sección proporciona una inmersión profunda en la arquitectura técnica y la base de código del módulo "Copia de seguridad de la base de datos localmente y en la nube" para desarrolladores y webmasters.

### 4.1 Descripción general de la arquitectura

El módulo MyBackups está diseñado con un fuerte énfasis en la robustez, la escalabilidad y la tolerancia a fallos, particularmente para manejar grandes operaciones de bases de datos e integraciones con la nube externa. Sigue un enfoque modular y orientado a objetos, aprovechando el patrón MVC de PrestaShop cuando es apropiado, pero también implementando su propia arquitectura interna orientada a servicios para la lógica central de copia de seguridad/restauración.

Los patrones arquitectónicos clave incluyen:

-   **Procesamiento en fragmentos:** La exportación e importación de la base de datos se dividen en fragmentos más pequeños y manejables para sortear los límites de tiempo de ejecución y memoria de PHP.
-   **Gestión de estados:** Un robusto sistema de gestión de estados (`MyBackupsStateManager`) rastrea el progreso de los trabajos de copia de seguridad/restauración de larga duración, lo que permite la ejecución de web-cron y la recuperación de interrupciones.
-   **Abstracción de almacenamiento:** Un diseño basado en interfaces (`MyBackupsStorageInterface`) permite una fácil integración de nuevos proveedores de almacenamiento en la nube sin alterar la lógica central de copia de seguridad.
-   **Integración OAuth:** Flujos seguros de OAuth 2.0 para Google Drive y Dropbox, gestionando el almacenamiento y la actualización de tokens.
-   **Ejecutor de Cron/Trabajos:** Controladores frontales y clases dedicadas para activar y gestionar trabajos en segundo plano a través de cron o web-cron.

### 4.2 Controladores (`controllers/`)

#### Controladores de Front-Office

Estos controladores se utilizan principalmente para tareas en segundo plano y devoluciones de llamada de OAuth, no para renderizar contenido orientado al cliente.

-   `mybackups/controllers/front/cron.php`
    -   **Nombre de la clase y clase padre:** `MyBackupsCronModuleFrontController` que extiende `ModuleFrontController`.
    -   **Responsabilidad:** Este controlador sirve como punto de entrada para las tareas cron programadas. Cuando se accede con el token correcto, activa el `MyBackupsCronRunner` para procesar las tareas de copia de seguridad pendientes. Está diseñado para ser llamado externamente por un demonio cron del servidor o un servicio web-cron.
-   `mybackups/controllers/front/index.php`
    -   **Nombre de la clase y clase padre:** `MyBackupsIndexModuleFrontController` que extiende `ModuleFrontController`.
    -   **Responsabilidad:** Un controlador frontal de marcador de posición o predeterminado, a menudo utilizado para el enrutamiento de módulos o redirecciones simples si no se solicita ninguna acción específica. En este módulo, podría servir como base o respaldo.
-   `mybackups/controllers/front/job.php`
    -   **Nombre de la clase y clase padre:** `MyBackupsJobModuleFrontController` que extiende `ModuleFrontController`.
    -   **Responsabilidad:** Maneja las solicitudes AJAX relacionadas con el progreso y el estado de los trabajos de copia de seguridad/restauración en curso. Interactúa con `MyBackupsJobRunner` y `MyBackupsStateManager` para proporcionar actualizaciones en tiempo real a la interfaz de usuario del Back Office.
-   `mybackups/controllers/front/oauthdropbox.php`
    -   **Nombre de la clase y clase padre:** `MyBackupsOauthdropboxModuleFrontController` que extiende `ModuleFrontController`.
    -   **Responsabilidad:** Esta es la URI de devolución de llamada para el flujo OAuth 2.0 de Dropbox. Después de que un comerciante autoriza el módulo en Dropbox, Dropbox redirige a este controlador, que luego maneja el intercambio del código de autorización por un token de acceso y lo almacena de forma segura.
-   `mybackups/controllers/front/oauthgdrive.php`
    -   **Nombre de la clase y clase padre:** `MyBackupsOauthgdriveModuleFrontController` que extiende `ModuleFrontController`.
    -   **Responsabilidad:** Similar a `oauthdropbox.php`, esta es la URI de devolución de llamada para el flujo OAuth 2.0 de Google Drive. Procesa el código de autorización de Google y obtiene/almacena los tokens de acceso y actualización necesarios.

#### Controladores de administración de Back-Office

Estos controladores gestionan la interfaz del módulo dentro del Back Office de PrestaShop.

-   `mybackups/controllers/admin/AdminMyBackupsController.php`
    -   **Nombre de la clase y clase padre:** `AdminMyBackupsController` que extiende `ModuleAdminController`.
    -   **Nombre de la pestaña y entidad gestionada:** Este es el controlador de administración principal para el panel de control "Mis Copias de Seguridad". Gestiona la lista, creación, descarga, restauración y eliminación de archivos de copia de seguridad. Orquesta las interacciones con `MyBackupsCatalog`, `MyBackupsExporter`, `MyBackupsImporter` y las diversas clases de almacenamiento.
-   `mybackups/controllers/admin/index.php`
    -   **Nombre de la clase y clase padre:** Archivo `index.php` estándar de PrestaShop para directorios de controladores de administración.
    -   **Responsabilidad:** Evita la lista directa de directorios y garantiza el acceso seguro a los controladores de administración.

### 4.3 Clases y modelos principales (`classes/`)

-   `mybackups/classes/index.php`: `index.php` vacío estándar para evitar la lista de directorios.
-   `mybackups/classes/MyBackupsAdminAjax.php`: Maneja varias solicitudes AJAX desde la interfaz de administración, como la obtención de listas de copias de seguridad, el inicio de acciones específicas o la actualización de elementos de la interfaz de usuario.
-   `mybackups/classes/MyBackupsAdminForms.php`: Probablemente responsable de renderizar y procesar los formularios de configuración del módulo en el Back Office, incluida la configuración de integración en la nube.
-   `mybackups/classes/MyBackupsCatalog.php`: Gestiona el catálogo de archivos de copia de seguridad, ya sean locales o en la nube. Proporciona métodos para listar, filtrar y recuperar información sobre las copias de seguridad existentes.
-   `mybackups/classes/MyBackupsCloudUi.php`: Ayuda a generar los elementos de la interfaz de usuario y la lógica para la integración del almacenamiento en la nube dentro del Back Office (por ejemplo, botones de conexión, indicadores de estado).
-   `mybackups/classes/MyBackupsCronRunner.php`: La lógica central para ejecutar trabajos de copia de seguridad programados. Comprueba las tareas pendientes e inicia `MyBackupsJobRunner` para cada una.
-   `mybackups/classes/MyBackupsDumpVerifier.php`: Responsable de verificar la integridad y validez de los archivos de volcado SQL, potencialmente buscando errores comunes o volcados incompletos.
-   `mybackups/classes/MyBackupsExporter.php`: Maneja el proceso real de exportación de la base de datos, incluyendo la fragmentación del volcado SQL, el filtrado de tablas y la compresión.
-   `mybackups/classes/MyBackupsImporter.php`: Gestiona el proceso de importación (restauración) de la base de datos, analizando el volcado SQL y ejecutando consultas en fragmentos.
-   `mybackups/classes/MyBackupsJobLock.php`: Implementa un mecanismo de bloqueo para evitar que se ejecuten múltiples trabajos de copia de seguridad/restauración simultáneamente, asegurando la coherencia de los datos y evitando la contención de recursos.
-   `mybackups/classes/MyBackupsJobRunner.php`: Orquesta todo el trabajo de copia de seguridad o restauración, gestionando la secuencia de pasos (exportar, comprimir, cargar/descargar, importar) e interactuando con `MyBackupsStateManager`.
-   `mybackups/classes/MyBackupsMemoryGuard.php`: Una clase de utilidad para monitorear y gestionar el uso de memoria PHP durante operaciones intensivas, ayudando a prevenir errores de falta de memoria.
-   `mybackups/classes/MyBackupsOAuthReturn.php`: Maneja los pasos finales del proceso de devolución de llamada de OAuth, procesando el código de autorización devuelto y gestionando el almacenamiento de tokens.
-   `mybackups/classes/MyBackupsOAuthState.php`: Gestiona el parámetro de estado durante los flujos de OAuth para prevenir ataques CSRF.
-   `mybackups/classes/MyBackupsPaths.php`: Proporciona una gestión centralizada de las rutas de archivo y directorios utilizados por el módulo (por ejemplo, directorio de almacenamiento de copias de seguridad).
-   `mybackups/classes/MyBackupsStateManager.php`: Crucial para trabajos de larga duración. Almacena y recupera el estado actual de una operación de copia de seguridad/restauración, lo que permite pausar y reanudar trabajos en múltiples solicitudes HTTP (por ejemplo, durante la ejecución de cron o actualizaciones de progreso basadas en la web).
-   `mybackups/classes/MyBackupsTableFilter.php`: Implementa la lógica para filtrar tablas de base de datos durante la exportación, según las selecciones del usuario.
-   `mybackups/classes/MyBackupsTimeBudget.php`: Ayuda a gestionar los límites de tiempo de ejecución para procesos de larga duración, permitiendo que el módulo se detenga y guarde el estado de forma elegante antes de alcanzar `max_execution_time`.
-   `mybackups/classes/MyBackupsTokenCrypto.php`: Maneja el cifrado y descifrado de tokens OAuth sensibles y claves API para un almacenamiento seguro.
-   `mybackups/classes/MyBackupsZip.php`: Gestiona la compresión y descompresión de archivos de copia de seguridad en archivos ZIP.

#### Subclases de almacenamiento (`classes/storage/`)

Este directorio contiene clases que implementan la `MyBackupsStorageInterface` para varios backends de almacenamiento.

-   `mybackups/classes/storage/index.php`: `index.php` vacío estándar.
-   `mybackups/classes/storage/MyBackupsCloudUploader.php`: Una clase genérica para gestionar el proceso de carga a almacenamiento en la nube, que potencialmente maneja cargas fragmentadas y seguimiento del progreso.
-   `mybackups/classes/storage/MyBackupsDropboxStorage.php`: Implementa `MyBackupsStorageInterface` para interactuar con la API de Dropbox.
-   `mybackups/classes/storage/MyBackupsFtpStorage.php`: Implementa `MyBackupsStorageInterface` para interactuar con servidores FTP/FTPS.
-   `mybackups/classes/storage/MyBackupsGoogleDriveStorage.php`: Implementa `MyBackupsStorageInterface` para interactuar con la API de Google Drive.
-   `mybackups/classes/storage/MyBackupsHttp.php`: Una clase de utilidad para realizar solicitudes HTTP, probablemente utilizada por las clases de almacenamiento en la nube para llamadas a la API.
-   `mybackups/classes/storage/MyBackupsLocalStorage.php`: Implementa `MyBackupsStorageInterface` para almacenar y recuperar copias de seguridad en el sistema de archivos del servidor local.
-   `mybackups/classes/storage/MyBackupsS3Storage.php`: Implementa `MyBackupsStorageInterface` para interactuar con Amazon S3.
-   `mybackups/classes/storage/MyBackupsStorageFactory.php`: Una clase de patrón de fábrica responsable de instanciar la clase de almacenamiento correcta según la configuración.
-   `mybackups/classes/storage/MyBackupsStorageInterface.php`: Define el contrato (métodos) que todas las clases de almacenamiento deben implementar (por ejemplo, `upload`, `download`, `delete`, `list_files`).

### 4.4 Activos JavaScript (`views/js/`)

-   `mybackups/lib/searchTool/views/js/autocomplete.js`:
    -   **Alcance:** Probablemente Back-office.
    -   **Detalles:** Proporciona funcionalidad de autocompletado, posiblemente para buscar tablas de bases de datos al configurar exclusiones o para filtrar listas de copias de seguridad.
-   `mybackups/views/js/mybackups-cloud.js`:
    -   **Alcance:** Back-office.
    -   **Detalles:** Maneja las interacciones del lado del cliente para la configuración del almacenamiento en la nube. Esto incluye llamadas AJAX para conectar/desconectar de servicios, actualizar la interfaz de usuario según el estado de la conexión y, potencialmente, manejar la navegación de carpetas dentro de los servicios en la nube.
-   `mybackups/views/js/mybackups-job.js`:
    -   **Alcance:** Back-office.
    -   **Detalles:** Gestiona la visualización del progreso en tiempo real para los trabajos de copia de seguridad y restauración. Utiliza AJAX para sondear el controlador frontal `job.php` en busca de actualizaciones sobre el estado del trabajo, actualizando barras de progreso, mensajes de estado y manejando notificaciones de finalización o fallo del trabajo.
-   `mybackups/views/js/mybackups-table-picker.js`:
    -   **Alcance:** Back-office.
    -   **Detalles:** Proporciona la interfaz interactiva para seleccionar o excluir tablas de bases de datos durante la creación de copias de seguridad, incluyendo potencialmente funciones de búsqueda y selección múltiple.

### 4.5 Hojas de estilo CSS (`views/css/`)

-   `mybackups/lib/searchTool/views/css/autocomplete.css`:
    -   **Alcance:** Estilo de administración del Back-office.
    -   **Detalles:** Estilos para los campos de entrada de autocompletado y las listas de sugerencias utilizadas en el Back Office.
-   `mybackups/views/css/admin.css`:
    -   **Alcance:** Estilo de administración del Back-office.
    -   **Detalles:** Contiene el estilo principal para la interfaz del Back Office del módulo, incluyendo el panel de control, la lista de copias de seguridad, los formularios, las barras de progreso y las secciones de integración en la nube. Los desarrolladores pueden anular estos estilos en su tema de administración personalizado o añadiendo CSS personalizado a través de un hook si es necesario.

### 4.6 Estructura de la plantilla Smarty (`views/templates/`)

-   `mybackups/lib/searchTool/views/scripts.tpl`:
    -   **Alcance:** Back-office.
    -   **Detalles:** Probablemente incluye activos JavaScript y CSS para la herramienta de búsqueda/autocompletado, potencialmente enganchado a `displayBackOfficeHeader` o similar.
-   `mybackups/views/templates/admin/backups.tpl`:
    -   **Alcance:** Plantilla de administración.
    -   **Detalles:** La plantilla principal para mostrar la lista de copias de seguridad existentes, incluyendo columnas para fecha, tamaño, ubicación y botones de acción (descargar, restaurar, eliminar). Este es el núcleo de la visualización de `AdminMyBackupsController`.
-   `mybackups/views/templates/admin/configure.tpl`:
    -   **Alcance:** Plantilla de administración.
    -   **Detalles:** Renderiza el formulario de configuración principal del módulo, generalmente accesible a través de `getContent()` en el archivo principal del módulo. Esto incluye la configuración general y la configuración inicial para las integraciones de servicios en la nube.
-   `mybackups/views/templates/admin/dashboard.tpl`:
    -   **Alcance:** Plantilla de administración.
    -   **Detalles:** La plantilla general del panel de control para la sección "Mis Copias de Seguridad", que combina elementos como la lista de copias de seguridad, el botón "Crear nueva copia de seguridad", los indicadores de estado de la nube y, potencialmente, la información de las copias de seguridad programadas.
-   `mybackups/views/templates/admin/job-progress.tpl`:
    -   **Alcance:** Plantilla de administración.
    -   **Detalles:** Muestra la barra de progreso y los mensajes de estado para los trabajos de copia de seguridad o restauración en curso, actualizados dinámicamente por `mybackups-job.js`.
-   `mybackups/views/templates/admin/table-picker.tpl`:
    -   **Alcance:** Plantilla de administración.
    -   **Detalles:** Renderiza la interfaz para seleccionar o excluir tablas de bases de datos durante la creación de copias de seguridad.

### 4.7 Esquema de la base de datos y mapa de hooks

-   **Tablas de la base de datos**:

    -   El módulo no crea tablas SQL personalizadas para almacenar los datos de copia de seguridad en sí, ya que las copias de seguridad son archivos.
    -   Almacenará valores de configuración en la tabla `ps_configuration` de PrestaShop, como:
        -   Claves/secretos de la API de la nube (cifrados).
        -   Tokens OAuth (cifrados).
        -   Configuraciones específicas del módulo (por ejemplo, ubicaciones predeterminadas de copia de seguridad, token cron).
        -   Información de estado del trabajo para `MyBackupsStateManager`.
-   **Tabla de Hooks registrados**:
    El módulo utiliza principalmente hooks del Back Office y controladores frontales para su funcionalidad. Los hooks de front-office listados (Header, Columns, Product, Footer) probablemente *no* son utilizados por este módulo, ya que su funcionalidad es puramente administrativa y centrada en el backend. Si se usaran, sería para propósitos muy específicos y no visibles, como cargar activos o realizar verificaciones en segundo plano.

| Nombre del Hook | Momento de ejecución | Propósito técnico |
| --- | --- | --- |
| `displayBackOfficeHeader` | Se renderiza en la sección `<head>` de las páginas del Back Office. | Se utiliza para inyectar CSS (`admin.css`) y JavaScript (`mybackups-cloud.js`, `mybackups-job.js`, `mybackups-table-picker.js`, `autocomplete.js`) específicos del módulo en el panel de administración. |
| `displayAdminProductsExtra` (o similar) | Potencialmente para añadir una opción de copia de seguridad en la página de edición de productos, aunque poco probable para este módulo. | (Si se usa) Para añadir una acción de copia de seguridad específica o información relacionada con los datos del producto. |
| `actionModuleInstall` | Se ejecuta cuando se instala el módulo. | Crea los directorios necesarios, establece los valores de configuración predeterminados, registra las pestañas del menú de administración y, potencialmente, configura las instrucciones iniciales de la tarea cron. |
| `actionModuleUninstall` | Se ejecuta cuando se desinstala el módulo. | Limpia los valores de configuración, elimina las pestañas del menú de administración y elimina los directorios específicos del módulo (aunque a menudo deja los archivos de copia de seguridad por seguridad). |
| `actionAdminControllerSetMedia` | Se ejecuta antes de que un controlador de administración renderice su página. | Se utiliza para añadir activos CSS/JS específicos solo a las propias páginas de administración del módulo (`AdminMyBackupsController`). |

## 5. Soporte oficial y actualizaciones

Para obtener las últimas actualizaciones, correcciones de errores y soporte oficial para el módulo "Copia de seguridad de la base de datos localmente y en la nube", consulte su cuenta de cliente en [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nuestro equipo de soporte está disponible para ayudarle con cualquier problema técnico o pregunta que pueda tener con respecto a la funcionalidad y configuración del módulo.
