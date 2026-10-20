---
title: "Optimización de la Base de Datos - Manual del Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop 'Optimización de la Base de Datos' de MyPresta.eu."
sidebar:
  label: "Optimización de la Base de Datos - Manual del Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Database Optimization en MyPresta.eu](https://mypresta.eu/modules/administration-tools/database-optimization.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/back-office-tools/database-optimization/)
>
> ---


# Optimización de la Base de Datos

## 1. Requisitos y Compatibilidad

- **Versiones de PrestaShop Soportadas**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilidad con PHP**: PHP 5.6 - 8.5
- **Requisitos de Alojamiento**: Las extensiones PHP estándar (cURL, JSON, OpenSSL) suelen ser suficientes. No se requieren configuraciones especiales del servidor.

## 2. Recorrido Completo por la Configuración (Cada Ajuste Agrupado por Pantalla)

### 2.1 Página de Configuración del Módulo (Back Office > Módulos > Configurar)

Esta es la pantalla de configuración principal y única para el módulo Optimización de la Base de Datos. La encontrará navegando a **Módulos > Gestor de Módulos** y haciendo clic en "Configurar" junto a "Optimización de la Base de Datos".

#### **Carritos no deseados**

-   **Qué hace este ajuste:** Esta opción controla si el módulo eliminará los carritos de compra antiguos y abandonados de su base de datos. Estos son carritos que los clientes iniciaron pero nunca completaron un pedido.
-   **Efecto de cambiar este ajuste:**
    -   *Cuando se establece en "Sí":* El módulo eliminará periódicamente estos carritos antiguos e incompletos. Esto reduce el tamaño de su base de datos y puede mejorar el rendimiento, ya que PrestaShop no tiene que gestionar datos para miles de carritos abandonados.
    -   *Cuando se establece en "No":* Los carritos de compra antiguos permanecerán en su base de datos. Si bien esto mantiene los datos históricos, puede contribuir al aumento del tamaño de la base de datos con el tiempo.
-   **Valor recomendado:** **Sí**. A menos que tenga una razón comercial específica para mantener todos los datos de carritos abandonados (por ejemplo, para un análisis histórico muy profundo), limpiarlos es beneficioso para el rendimiento.
-   **Escenario / ejemplo de comerciante:** Si nota que su base de datos crece mucho y su tienda se ralentiza, habilitar esta opción es una victoria rápida para eliminar una fuente común de datos innecesarios.

#### **Conexiones**

-   **Qué hace este ajuste:** Esta opción controla si el módulo eliminará los registros de conexión antiguos de su base de datos. PrestaShop registra cada conexión de visitante a su tienda, lo que puede acumularse rápidamente.
-   **Efecto de cambiar este ajuste:**
    -   *Cuando se establece en "Sí":* El módulo eliminará periódicamente los registros de conexión antiguos. Esto reduce significativamente el tamaño de la base de datos, ya que los registros de conexión pueden ser una de las tablas más grandes en una tienda con mucho tráfico.
    -   *Cuando se establece en "No":* Los registros de conexión se retendrán indefinidamente, lo que podría llevar a una base de datos muy grande.
-   **Valor recomendado:** **Sí**. Para la mayoría de las tiendas, los registros de conexión muy antiguos no son críticos para las operaciones diarias y pueden eliminarse de forma segura para mejorar el rendimiento.
-   **Escenario / ejemplo de comerciante:** Si su tienda tiene un alto volumen de tráfico, los registros de conexión pueden crecer extremadamente rápido. Habilitar esto ayuda a evitar que su base de datos se vuelva excesivamente grande y lenta.

#### **Página de Conexiones**

-   **Qué hace este ajuste:** Esta opción se dirige específicamente a los registros de conexión relacionados con las páginas individuales visitadas. Funciona en conjunto con el ajuste "Conexiones".
-   **Efecto de cambiar este ajuste:**
    -   *Cuando se establece en "Sí":* Si "Conexiones" también está en "Sí", el módulo eliminará los registros antiguos que detallan qué páginas específicas vieron los visitantes.
    -   *Cuando se establece en "No":* Incluso si "Conexiones" está en "Sí", el módulo retendrá los registros de conexión específicos de la página.
-   **Valor recomendado:** **Sí**. Similar a las conexiones generales, los registros específicos de la página pueden ser muy numerosos y a menudo no son necesarios para un análisis a largo plazo si está utilizando herramientas de análisis externas como Google Analytics.
-   **Escenario / ejemplo de comerciante:** Si confía en Google Analytics para las estadísticas de visitas a la página, es probable que no necesite que PrestaShop almacene estos datos granulares indefinidamente, por lo que es seguro limpiarlos.

#### **Fuente de Conexiones**

-   **Qué hace este ajuste:** Esta opción se dirige específicamente a los registros de conexión relacionados con la fuente del visitante (por ejemplo, directo, motor de búsqueda, referencia). Funciona en conjunto con el ajuste "Conexiones".
-   **Efecto de cambiar este ajuste:**
    -   *Cuando se establece en "Sí":* Si "Conexiones" también está en "Sí", el módulo eliminará los registros antiguos que detallan de dónde vinieron los visitantes.
    -   *Cuando se establece en "No":* Incluso si "Conexiones" está en "Sí", el módulo retendrá los registros de conexión específicos de la fuente.
-   **Valor recomendado:** **Sí**. Al igual que otros datos de conexión, esto a menudo puede ser gestionado por herramientas de análisis externas.
-   **Escenario / ejemplo de comerciante:** Si su equipo de marketing utiliza herramientas como Google Analytics u otros sistemas CRM para rastrear las fuentes de tráfico, los registros internos de PrestaShop podrían ser redundantes y pueden limpiarse para ahorrar espacio en la base de datos.

#### **Invitados**

-   **Qué hace este ajuste:** Esta opción controla si el módulo eliminará las cuentas de invitados antiguas e inactivas de su base de datos. Estas son cuentas creadas para visitantes que iniciaron un proceso de pago como invitados pero nunca lo completaron, o simplemente navegaron sin registrarse.
-   **Efecto de cambiar este ajuste:**
    -   *Cuando se establece en "Sí":* El módulo eliminará periódicamente estas cuentas de invitados antiguas. Esto ayuda a mantener su base de datos de clientes limpia y enfocada en usuarios activos o registrados.
    -   *Cuando se establece en "No":* Las cuentas de invitados antiguas permanecerán en su base de datos indefinidamente.
-   **Valor recomendado:** **Sí**. A menos que tenga una necesidad específica de retener cada registro de invitado, limpiarlos ayuda a mantener una base de datos ordenada.
-   **Escenario / ejemplo de comerciante:** Si su tienda tiene muchos visitantes que navegan pero no se registran ni completan compras, la tabla de invitados puede crecer significativamente. Limpiar estos ayuda a mantener sus datos de clientes manejables.

#### **Comprobar actualizaciones**

-   **Qué hace este ajuste:** Este ajuste controla si el módulo buscará automáticamente nuevas versiones y actualizaciones disponibles en MyPresta.eu.
-   **Efecto de cambiar este ajuste:**
    -   *Cuando se establece en "Habilitar":* El módulo se conectará periódicamente a MyPresta.eu para ver si hay una versión más reciente disponible. Si es así, recibirá una notificación en su Back Office de PrestaShop.
    -   *Cuando se establece en "Deshabilitar":* El módulo no buscará actualizaciones. Deberá verificar manualmente su cuenta de MyPresta.eu para nuevas versiones.
-   **Valor recomendado:** **Habilitar**. Esto asegura que siempre esté al tanto de las actualizaciones disponibles, que a menudo incluyen correcciones de errores, mejoras de rendimiento y nuevas características.
-   **Escenario / ejemplo de comerciante:** Desea asegurarse de que sus módulos estén siempre actualizados por seguridad y rendimiento. Habilitar esto proporciona notificaciones convenientes.

#### **Notificaciones de actualizaciones**

-   **Qué hace este ajuste:** Este ajuste controla si recibe notificaciones en su Back Office de PrestaShop cuando hay una actualización disponible (si "Comprobar actualizaciones" está habilitado).
-   **Efecto de cambiar este ajuste:**
    -   *Cuando se establece en "Habilitar":* Verá una notificación en su Back Office cuando se detecte una nueva versión del módulo.
    -   *Cuando se establece en "Deshabilitar":* Incluso si "Comprobar actualizaciones" está habilitado y hay una actualización disponible, no recibirá una notificación visible en el Back Office.
-   **Valor recomendado:** **Habilitar**. Esto funciona de la mano con "Comprobar actualizaciones" para mantenerle informado.
-   **Escenario / ejemplo de comerciante:** Desea ser alertado inmediatamente cuando una actualización esté lista para poder planificar su instalación, asegurando que su tienda se beneficie de las últimas mejoras.

#### **Página del módulo**

-   **Qué hace este ajuste:** Este ajuste es probablemente una opción de visualización para la propia página o información del módulo dentro del Back Office. (Basado en la estructura típica de los módulos de MyPresta.eu, esto podría controlar un enlace o un elemento de visualización específico relacionado con el módulo en sí).
-   **Efecto de cambiar este ajuste:**
    -   *Cuando se establece en "Habilitar":* Probablemente muestra un enlace o sección relacionada con la información del módulo u otros módulos de MyPresta.eu.
    -   *Cuando se establece en "Deshabilitar":* Este enlace o sección se ocultará.
-   **Valor recomendado:** **Habilitar**. Generalmente proporciona acceso rápido a soporte u otros recursos útiles.
-   **Escenario / ejemplo de comerciante:** Desea un acceso fácil a los recursos de MyPresta.eu directamente desde la página de configuración de su módulo.

### 2.2 Tabla de Referencia Rápida de Configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| Configuración del Módulo | Carritos no deseados | Sí | Elimina carritos de compra antiguos y abandonados para reducir el tamaño de la base de datos y mejorar el rendimiento. |
| Configuración del Módulo | Conexiones | Sí | Elimina registros de conexión de visitantes antiguos para reducir significativamente el tamaño de la base de datos. |
| Configuración del Módulo | Página de Conexiones | Sí | Elimina registros antiguos de páginas específicas visitadas por las conexiones. |
| Configuración del Módulo | Fuente de Conexiones | Sí | Elimina registros antiguos de las fuentes de tráfico para las conexiones. |
| Configuración del Módulo | Invitados | Sí | Elimina cuentas de invitados antiguas e inactivas para mantener los datos del cliente limpios. |
| Configuración del Módulo | Comprobar actualizaciones | Habilitar | Comprueba automáticamente MyPresta.eu para actualizaciones del módulo. |
| Configuración del Módulo | Notificaciones de actualizaciones | Habilitar | Muestra notificaciones en el Back Office cuando hay actualizaciones del módulo disponibles. |
| Configuración del Módulo | Página del módulo | Habilitar | Controla la visualización de enlaces/información relacionados con el módulo en la página de configuración. |

## 3. Solución de Problemas para Comerciantes y Preguntas Frecuentes (FAQ)

**P: Después de habilitar el módulo, mi tienda no parece más rápida. ¿Qué pasa?**
R: La optimización de la base de datos es una pieza del rompecabezas del rendimiento. Si bien limpia datos innecesarios, otros factores como los recursos del servidor, la optimización de imágenes, los módulos pesados o los temas personalizados no optimizados aún pueden ralentizar su tienda. Asegúrese de haber borrado también la caché de PrestaShop (Parámetros Avanzados > Rendimiento) después de la configuración.

**P: ¿Este módulo eliminará datos importantes de clientes o pedidos?**
R: No. Este módulo está diseñado específicamente para eliminar datos *no deseados* e *inactivos*: carritos abandonados, registros de conexión antiguos y cuentas de invitados que nunca se convirtieron. No toca pedidos completados, cuentas de clientes activas, datos de productos u otra información crítica de la tienda.

**P: ¿Con qué frecuencia limpia el módulo la base de datos? ¿Es automático?**
R: El módulo realiza sus operaciones de limpieza cuando se guarda su configuración o cuando PrestaShop activa ciertas tareas en segundo plano. No es un limpiador continuo en tiempo real. El beneficio principal proviene de la eliminación de datos antiguos acumulados. Para una limpieza continua y programada, es posible que deba combinarlo con un trabajo cron que active periódicamente la lógica de limpieza del módulo (aunque este módulo se centra principalmente en la limpieza única o al guardar).

**P: Deshabilité "Comprobar actualizaciones" y "Notificaciones de actualizaciones" pero ahora quiero saber sobre las actualizaciones. ¿Cómo las vuelvo a habilitar?**
R: Simplemente regrese a la página de configuración del módulo (Módulos > Gestor de Módulos > Configurar Optimización de la Base de Datos) y establezca tanto "Comprobar actualizaciones" como "Notificaciones de actualizaciones" en "Habilitar". Guarde sus cambios y el módulo reanudará la verificación y notificación de nuevas versiones.

## 4. Guía para Desarrolladores y Webmasters (Arquitectura Técnica y Mapa de Código)

### 4.1 Visión General de la Arquitectura

El módulo Optimización de la Base de Datos es un módulo de PrestaShop sencillo diseñado principalmente para ejecutar operaciones de limpieza de la base de datos. Sigue la estructura estándar de los módulos de PrestaShop, aprovechando la clase `Module` y sus métodos `install()` y `uninstall()` para la configuración e eliminación. Su funcionalidad principal reside dentro del método `getContent()`, que maneja el formulario de configuración del Back Office y activa la lógica de optimización de la base de datos al enviar el formulario. No introduce controladores, modelos o activos de front-office personalizados, lo que lo convierte en una utilidad ligera y enfocada.

### 4.2 Controladores (`controllers/`)

-   **Controladores de Front-Office**: Ninguno. Todas las operaciones se manejan en el Back Office o a través de la clase principal del módulo.
-   **Controladores de Administración del Back-Office**: Ninguno. La configuración se gestiona directamente dentro del método `getContent()` del archivo `dboptimization.php`.

### 4.3 Clases y Modelos Principales (`classes/`)

-   **Clase Principal del Módulo**: `dboptimization/dboptimization.php`
    -   **Nombre de la Clase**: `DbOptimization`
    -   **Clase Padre**: `Module`
    -   **Responsabilidad**:
        -   Maneja la instalación (`install()`) y desinstalación (`uninstall()`) del módulo.
        -   Gestiona la visualización y el envío del formulario de configuración del Back Office (`getContent()`).
        -   Contiene la lógica central para la limpieza de la base de datos basada en las opciones configuradas.
        -   Registra y anula el registro de hooks (aunque este módulo utiliza principalmente `displayBackOfficeHeader` para las comprobaciones de actualización, no para la visualización en el front-office).
        -   Gestiona los valores de configuración utilizando `Configuration::get()` y `Configuration::updateValue()`.
        -   Incluye la lógica de comprobación de actualizaciones (`checkforupdates()`) y la visualización de notificaciones.

### 4.4 Activos JavaScript (`views/js/`)

-   Ninguno. El módulo no incluye ningún archivo JavaScript personalizado.

### 4.5 Hojas de Estilo CSS (`views/css/`)

-   Ninguno. El módulo no incluye ningún archivo CSS personalizado.

### 4.6 Estructura de Plantillas Smarty (`views/templates/`)

-   Ninguno. El módulo renderiza su formulario de configuración directamente dentro del método `getContent()` utilizando `HelperForm` de PrestaShop (o una lógica de renderizado interna similar), en lugar de archivos `.tpl` externos.

### 4.7 Esquema de la Base de Datos y Mapa de Hooks

-   **Tablas de la Base de Datos**:

    -   El módulo no crea ninguna tabla de base de datos personalizada.
    -   Interactúa con las tablas existentes de PrestaShop, principalmente:
        -   `ps_cart`: Para "Carritos no deseados".
        -   `ps_connections`: Para "Conexiones".
        -   `ps_connections_page`: Para "Página de Conexiones".
        -   `ps_connections_source`: Para "Fuente de Conexiones".
        -   `ps_guest`: Para "Invitados".
    -   Los valores de configuración se almacenan en la tabla `ps_configuration`:
        -   `dbopt_cart`
        -   `dbopt_connections`
        -   `dbopt_connections_page`
        -   `dbopt_connections_source`
        -   `dbopt_guest`
        -   `update_dboptimization` (para la marca de tiempo de comprobación de actualización)
        -   `mypresta_updates` (configuración global de notificación de actualización)
        -   `dbopt_check_updates`
        -   `dbopt_updates_notifications`
        -   `dbopt_module_page`
-   **Tabla de Hooks Registrados**:

| Nombre del Hook | Archivo / Método | Momento de Ejecución | Propósito Técnico |
| --- | --- | --- | --- |
| `displayBackOfficeHeader` | `dboptimization.php` | Se renderiza en la cabecera de las páginas del Back Office. | Utilizado por el módulo para inyectar notificaciones de actualización si `dbopt_check_updates` y `dbopt_updates_notifications` están habilitados. |
| `actionAdminControllerSetMedia` | `dboptimization.php` | Se ejecuta cuando un controlador de administración establece sus medios (CSS/JS). | Potencialmente utilizado para comprobaciones de actualización o para asegurar que se carguen los activos necesarios (si existieran) en el administrador. |

## 5. Soporte Oficial y Actualizaciones

Para las últimas actualizaciones, correcciones de errores y soporte completo para el módulo Optimización de la Base de Datos, consulte su cuenta de cliente en [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nuestro equipo de soporte dedicado está disponible para ayudar a comerciantes y desarrolladores con cualquier pregunta o problema relacionado con la funcionalidad e integración del módulo.
