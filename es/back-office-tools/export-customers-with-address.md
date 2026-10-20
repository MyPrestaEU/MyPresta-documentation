---
title: "Exportar Clientes con dirección - Manual de Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop Exportar Clientes con dirección de MyPresta.eu."
sidebar:
  label: "Exportar Clientes con dirección - Manual de Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Export Customers with address en MyPresta.eu](https://mypresta.eu/modules/administration-tools/export-customers-with-address.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/back-office-tools/export-customers-with-address/)
>
> ---


# Exportar Clientes con dirección

## 1. Requisitos y Compatibilidad

- **Versiones de PrestaShop compatibles**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilidad con PHP**: PHP 5.6 - 8.5
- **Requisitos de Alojamiento**: Las extensiones PHP estándar (cURL, JSON, OpenSSL) suelen ser suficientes para los módulos de PrestaShop. No hay requisitos de alojamiento especiales más allá de un entorno PrestaShop estándar.

## 2. Recorrido Completo por la Configuración (Cada Ajuste Agrupado por Pantalla)

### 2.1 Página de Configuración del Módulo (Back Office > Módulos > Configurar)

Después de la instalación, al hacer clic en "Configurar" en el módulo, accederá a su página de configuración principal. Esta pantalla gestiona principalmente la configuración interna del módulo relacionada con las actualizaciones.

-   **Qué hace esta configuración:** Esta sección suele gestionar las comprobaciones internas de actualización del módulo y la información de la versión. Estos ajustes suelen ser para uso interno del módulo para asegurar que está ejecutando la última versión y para proporcionar notificaciones de actualización.
-   **Efecto de cambiar esta configuración:**
    -   *`mypresta_updates`*: Es probable que sea una bandera interna para habilitar o deshabilitar las comprobaciones de actualización de MyPresta.eu.
    -   *`update_`*: Esto podría almacenar la última vez que se realizó una comprobación de actualización.
    -   *`updatev_`*: Esto podría almacenar la última versión disponible detectada.
-   **Valor recomendado:** Generalmente se recomienda dejar estos ajustes en sus valores predeterminados para asegurarse de recibir notificaciones de actualización importantes.
-   **Escenario / ejemplo de comerciante:** Normalmente no interactúa directamente con estos ajustes. Funcionan en segundo plano para informarle si hay una nueva versión del módulo disponible, asegurándose de que tenga acceso a las últimas características y correcciones de errores.

### 2.2 Pantallas de Administración Dedicadas y Vistas de Controlador

#### 2.2.1 Exportar Clientes con Dirección (Back Office > Parámetros Avanzados > Exportar Clientes con dirección)

Esta es la pantalla principal donde realizará la exportación de clientes. Puede encontrarla en el menú "Parámetros Avanzados" de su back office de PrestaShop.

-   **Nombre de la pantalla y ubicación del menú:** **Parámetros Avanzados > Exportar Clientes con dirección**
-   **Acciones y configuraciones disponibles:**
    -   Cuando navegue a esta pantalla, verá un botón o un enlace para iniciar el proceso de exportación. El módulo prepara automáticamente un archivo CSV que contiene todos los datos del cliente y sus direcciones asociadas.
    -   El archivo exportado incluirá las siguientes columnas, formateadas para la herramienta de importación de PrestaShop:
        -   **ID de Cliente**: Identificador único para el cliente.
        -   **Activo (0/1)**: Si la cuenta del cliente está activa (1) o inactiva (0).
        -   **ID de Títulos (Sr = 1, Sra = 2, otro = 0)**: El ID correspondiente al título del cliente (por ejemplo, Sr., Sra.).
        -   \*\*Email \*\*\*: La dirección de correo electrónico del cliente (obligatorio).
        -   \*\*Contraseña \*\*\*: La contraseña del cliente (obligatorio, generalmente cifrada).
        -   **Cumpleaños (aaaa-mm-dd)**: La fecha de nacimiento del cliente.
        -   \*\*Apellido \*\*\*: El apellido del cliente (obligatorio).
        -   \*\*Nombre \*\*\*: El nombre del cliente (obligatorio).
        -   **Newsletter (0/1)**: Si el cliente está suscrito al boletín (1) o no (0).
        -   **Opt-in (0/1)**: Si el cliente ha optado por ofertas de socios (1) o no (0).
        -   **Fecha de registro**: La fecha en que el cliente registró su cuenta.
        -   **Grupos (x,y,z…)**: Una lista de IDs separados por comas de los grupos de clientes a los que pertenece el cliente.
        -   **ID de grupo predeterminado**: El ID del grupo predeterminado del cliente.
        -   **ID / Nombre de la tienda**: El ID o nombre de la tienda a la que está asociado el cliente (útil en entornos multitienda).
        -   **ID de Dirección**: Identificador único para la dirección del cliente.
        -   \*\*Alias \*\*\*: Un alias para la dirección (por ejemplo, "Mi dirección de casa").
        -   \*\*Email del cliente \*\*\*: El correo electrónico asociado a esta dirección (debe coincidir con el correo electrónico del cliente).
        -   **Fabricante**: (Si aplica)
        -   **Proveedor**: (Si aplica)
        -   **Empresa**: El nombre de la empresa asociado a la dirección.
        -   … y otros campos de dirección estándar como `Dirección1`, `Dirección2`, `Código Postal`, `Ciudad`, `País`, `Teléfono`, `Teléfono Móvil`, `Número de IVA`, etc.
-   **Efecto de los cambios:** Al hacer clic en el botón de exportar, se generará y descargará un archivo CSV en su ordenador. Esta acción no modifica ningún dato en su tienda PrestaShop; solo los extrae.
-   **Flujo de trabajo recomendado para la gestión diaria de la tienda:**
    1.  **Copias de seguridad regulares:** Exporte periódicamente sus datos de clientes como copia de seguridad, especialmente antes de actualizaciones importantes de la tienda o migraciones.
    2.  **Generación de listas de marketing:** Exporte datos de clientes para crear listas para campañas de marketing por correo electrónico, segmentando por grupos o fechas de registro.
    3.  **Actualizaciones de CRM:** Si utiliza un CRM externo, exporte datos para mantenerlo sincronizado con su base de clientes de PrestaShop.

#### 2.2.2 AdminExportCustomersController (index.php)

Este archivo probablemente sirve como punto de entrada o ayudante para el `AdminExportCustomersController`, asegurando que la interfaz administrativa del módulo funcione correctamente dentro del back office de PrestaShop. No presenta una pantalla configurable separada, sino que facilita la visualización y funcionalidad de la pantalla de exportación principal.

### 2.3 Tabla de Referencia Rápida de Configuración

| Pantalla / Vista | Configuración / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| Página de Configuración del Módulo | `mypresta_updates` | Habilitado | Bandera interna para las comprobaciones de actualización de MyPresta.eu. Mantener habilitado para notificaciones. |
| Página de Configuración del Módulo | `update_` | (Interno) | Almacena la marca de tiempo de la última comprobación de actualización. |
| Página de Configuración del Módulo | `updatev_` | (Interno) | Almacena la última versión del módulo disponible. |
| Parámetros Avanzados > Exportar Clientes con dirección | Botón Exportar | N/A | Inicia la descarga de un archivo CSV que contiene todos los datos de clientes y direcciones. |
| Parámetros Avanzados > Exportar Clientes con dirección | Columnas CSV Exportadas | N/A | Incluye ID de Cliente, Activo, ID de Títulos, Email, Contraseña, Cumpleaños, Apellido, Nombre, Newsletter, Opt-in, Fecha de registro, Grupos, ID de grupo predeterminado, ID/Nombre de la Tienda, ID de Dirección, Alias, Email del cliente, Empresa y todos los campos de dirección estándar. |

## 3. Solución de Problemas para Comerciantes y Preguntas Frecuentes (FAQ)

**P1: Hice clic en el botón de exportar, pero no pasó nada o el archivo está vacío.**
**R1:**

-   **Verifique los bloqueadores de ventanas emergentes del navegador:** Su navegador podría estar bloqueando la descarga del archivo. Busque una notificación o icono en la barra de direcciones de su navegador y permita las descargas desde su administración de PrestaShop.
-   **Permisos del módulo:** Asegúrese de que el módulo tenga los permisos necesarios del sistema de archivos para crear y servir el archivo CSV. Aunque es raro, los permisos incorrectos pueden impedir la generación del archivo.
-   **Límites de memoria del servidor:** Si tiene un número muy grande de clientes, el proceso de exportación podría alcanzar los límites de memoria PHP en su servidor. Revise los registros de errores PHP de su servidor (a menudo encontrados en `var/logs` o en su panel de control de alojamiento) en busca de errores relacionados con la memoria. Es posible que necesite aumentar temporalmente `memory_limit` en su archivo `php.ini`.
-   **Base de datos de clientes vacía:** Verifique que realmente tiene clientes registrados en su tienda.

**P2: El archivo CSV exportado se ve ilegible o tiene caracteres extraños.**
**R2:** Esto suele ser un problema de codificación.

-   **Abrir con la codificación correcta:** Al abrir el archivo CSV en un programa de hoja de cálculo (como Excel), asegúrese de seleccionar **UTF-8** como origen o codificación del archivo. La mayoría de los sistemas modernos utilizan UTF-8, y las exportaciones de PrestaShop suelen estar en este formato.
-   **Verifique la configuración de idioma de PrestaShop:** Asegúrese de que el idioma predeterminado y el conjunto de caracteres de su tienda PrestaShop estén configurados correctamente en **Internacional > Localización**.

**P3: ¿Puedo elegir qué campos exportar?**
**R3:** Este módulo exporta un conjunto predefinido de campos de cliente y dirección que son compatibles con la herramienta de importación nativa de PrestaShop. No ofrece opciones para seleccionar o deseleccionar campos individuales. Si necesita una exportación altamente personalizada, es posible que necesite un módulo de exportación más avanzado o un desarrollo personalizado.

**P4: ¿La exportación de clientes afectará el rendimiento de mi tienda?**
**R4:** Para la mayoría de las tiendas, una exportación única tendrá un impacto insignificante. Para tiendas con cientos de miles de clientes, el proceso de exportación podría tardar unos momentos y consumir algunos recursos del servidor. Generalmente se recomienda realizar grandes exportaciones durante las horas de menor actividad si anticipa un tiempo de procesamiento muy largo. El módulo está diseñado para ser eficiente, pero los recursos del servidor son siempre un factor.

**P5: Quiero volver a importar los clientes después de hacer cambios. ¿Cómo lo hago?**
**R5:** Este módulo solo maneja la exportación. Para volver a importar, usaría la herramienta de importación nativa de PrestaShop:

1.  Vaya a **Parámetros Avanzados > Importar**.
2.  Seleccione "Clientes" o "Direcciones" como la entidad a importar.
3.  Suba su archivo CSV modificado.
4.  Mapee cuidadosamente las columnas de su CSV a los campos de la base de datos de PrestaShop.

Siempre pruebe las importaciones en un entorno de desarrollo o de prueba primero, y asegúrese de tener una copia de seguridad completa de la base de datos antes de realizar cualquier importación a gran escala en su tienda en vivo. Las importaciones incorrectas pueden provocar la pérdida o corrupción de datos.

## 4. Guía para Desarrolladores y Webmasters (Arquitectura Técnica y Mapa de Código)

### 4.1 Resumen de la Arquitectura

El módulo "Exportar Clientes con dirección" (`exportcustomers`) es un módulo de PrestaShop sencillo centrado principalmente en la funcionalidad de back-office. Sigue un patrón MVC estándar de PrestaShop para su interfaz administrativa. La lógica central reside en el archivo principal del módulo y en un controlador de administración dedicado. No introduce nuevas tablas de base de datos, sino que aprovecha las estructuras `ObjectModel` existentes de `Customer` y `Address` de PrestaShop para recuperar y formatear datos para la exportación. La simplicidad del módulo significa que no tiene componentes de front-office, clases personalizadas o activos complejos de JavaScript/CSS.

### 4.2 Controladores (`controllers/`)

-   **Controladores de Front-Office**: Ninguno. Este módulo no tiene funcionalidad de front-office.
-   **Controladores de Administración de Back-Office**:

    -   `exportcustomers/controllers/admin/AdminExportCustomers.php`
        -   **Nombre de la clase y clase padre**: `AdminExportCustomersController` que extiende `ModuleAdminController`.
        -   **Responsabilidad**: Este es el controlador principal responsable de manejar la lógica de exportación de clientes y direcciones. Cuando se accede a través del menú del back office de PrestaShop, inicia el proceso de obtención de datos de clientes y direcciones de la base de datos, los formatea en una cadena CSV y los envía como un archivo descargable al navegador. Construye la fila de encabezado CSV con todos los campos especificados (ID de Cliente, Email, ID de Dirección, Alias, etc.) y luego itera a través de los objetos `Customer` y `Address` para poblar las filas de datos.
    -   `exportcustomers/controllers/admin/index.php`
        -   **Responsabilidad**: Este es un archivo de marcador de posición común en los directorios de controladores de administración de módulos de PrestaShop. Normalmente contiene un simple `header('Location: ../../index.php?controller=AdminHome')` o una redirección similar para evitar la lista directa de directorios o el acceso, garantizando la seguridad y el enrutamiento adecuado dentro del back office de PrestaShop. No contiene ninguna lógica funcional para el módulo en sí.

### 4.3 Clases y Modelos Principales (`classes/`)

Este módulo no introduce ninguna clase o modelo personalizado en el directorio `classes/`. Utiliza directamente las clases `ObjectModel` principales de PrestaShop `Customer` y `Address` para recuperar datos de la base de datos.

### 4.4 Activos de JavaScript (`views/js/`)

Este módulo no incluye ningún archivo JavaScript personalizado. El proceso de exportación se inicia típicamente mediante un simple envío de formulario o un enlace directo, manejado completamente por el controlador PHP.

### 4.5 Hojas de Estilo CSS (`views/css/`)

Este módulo no incluye ningún archivo CSS personalizado. Su interfaz de back-office se basa completamente en el estilo predeterminado del back-office de PrestaShop.

### 4.6 Estructura de Plantillas Smarty (`views/templates/`)

Este módulo no incluye ningún archivo de plantilla Smarty personalizado. El `AdminExportCustomersController` probablemente renderiza una vista muy simple, posiblemente solo un botón o un mensaje, directamente dentro de su método `renderForm()` o `initContent()`, o directamente activa una descarga de archivo sin renderizar una plantilla compleja.

### 4.7 Esquema de Base de Datos y Mapa de Hooks

-   **Tablas de Base de Datos**: Este módulo no crea ninguna tabla de base de datos personalizada. Lee datos de las tablas existentes de PrestaShop, principalmente `ps_customer` y `ps_address`.

    -   `ps_configuration`: El módulo almacena su configuración interna (`mypresta_updates`, `update_`, `updatev_`) en la tabla `ps_configuration`.
-   **Tabla de Hooks Registrados**:
    Este módulo no registra ningún hook de front-office. Su funcionalidad está completamente confinada al back office.
    Probablemente utiliza el hook `actionAdminControllerSetMedia` (implícita o explícitamente) para su controlador de administración, y potencialmente `displayAdminProductsExtra` o similar para su elemento de menú de back-office.

| Nombre del Hook | Momento de Ejecución | Propósito Técnico |
| --- | --- | --- |
| `actionAdminControllerSetMedia` | Se ejecuta cuando se inicializa un controlador de administración. | Utilizado por `ModuleAdminController` para añadir activos CSS/JS (aunque este módulo no tiene ninguno). |
| `displayAdminAdvancedParameters` | Renderiza contenido en la sección "Parámetros Avanzados" del back office. | Probablemente utilizado para añadir el enlace/punto de entrada del módulo al menú "Parámetros Avanzados". |

## 5. Soporte Oficial y Actualizaciones

Para actualizaciones oficiales, soporte técnico y las últimas versiones del módulo "Exportar Clientes con dirección", consulte su cuenta de cliente en [MyPresta.eu](https://mypresta.eu). Nuestro equipo de soporte está disponible para ayudar con cualquier problema o pregunta relacionada con la funcionalidad y compatibilidad del módulo.
