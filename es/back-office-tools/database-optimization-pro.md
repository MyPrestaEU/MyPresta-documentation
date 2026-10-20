---
title: "Database Optimization Pro - Manual del Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo Database Optimization Pro para PrestaShop de MyPresta.eu."
sidebar:
  label: "Database Optimization Pro - Manual del Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Database Optimization Pro en MyPresta.eu](https://mypresta.eu/modules/administration-tools/database-optimization-pro.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/back-office-tools/database-optimization-pro/)
>
> ---


# Database Optimization Pro

## 1. Requisitos y Compatibilidad

- **Versiones de PrestaShop compatibles**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilidad con PHP**: PHP 5.6 - 8.5
- **Requisitos de alojamiento**: Las extensiones PHP estándar (cURL, JSON, OpenSSL) suelen ser suficientes. Se recomienda encarecidamente el acceso a su panel de control de alojamiento (cPanel, Plesk, etc.) para configurar tareas cron para las capacidades de automatización completas del módulo.

## 2. Recorrido Completo por la Configuración (Cada Ajuste Agrupado por Pantalla)

### 2.1 Página de Configuración del Módulo (Back Office > Módulos > Configurar)

Después de la instalación, al hacer clic en "Configurar" accederá a la pantalla de configuración principal de Database Optimization Pro. Aquí es donde configurará la limpieza automática y obtendrá la información necesaria para su tarea cron.

La página de configuración es sencilla y proporciona las herramientas esenciales para gestionar la optimización de su base de datos.

#### **URL de la Tarea Cron**

- **Qué hace este ajuste:** Esta es la dirección web (URL) única que, al ser visitada, activa el proceso de optimización de la base de datos. Está diseñada para ser llamada por un sistema automatizado (una tarea cron) en lugar de por un humano que navega a ella.
- **Efecto de cambiar este ajuste:** No puede cambiar esta URL directamente desde la configuración del módulo. Se genera automáticamente por el módulo.
- **Valor recomendado:** Copie esta URL exactamente como aparece. La necesitará para configurar su tarea cron en su servidor de alojamiento.
- **Escenario / ejemplo del comerciante:** Copiará esta URL y la pegará en la interfaz de configuración de tareas cron proporcionada por su proveedor de alojamiento web (por ejemplo, cPanel, Plesk o un gestor de tareas cron personalizado). Esto le dice a su servidor "cada X horas/días, visite esta URL para limpiar mi base de datos".

#### **Ejecutar Optimización Ahora**

- **Qué hace este ajuste:** Este es un disparador manual para ejecutar el proceso de optimización de la base de datos inmediatamente. Realiza las mismas acciones de limpieza que la URL de la tarea cron, pero bajo demanda.
- **Efecto de cambiar este ajuste:**
  - *Al hacer clic:* El módulo comenzará a limpiar su base de datos instantáneamente. Verá un mensaje de confirmación una vez que se complete.
- **Valor recomendado:** Utilice este botón para pruebas iniciales después de la instalación, o si necesita realizar una limpieza inmediata fuera de sus tareas cron programadas.
- **Escenario / ejemplo del comerciante:** Acaba de instalar el módulo y quiere verlo en acción, o ha realizado muchos cambios en su tienda (por ejemplo, ha importado muchos productos) y quiere limpiar inmediatamente sin esperar a la próxima tarea cron programada.

#### **Configuración de la Tarea Cron**

Esta es la parte más crucial para automatizar la optimización de su base de datos. Una tarea cron es un programador de tareas basado en tiempo en sistemas operativos tipo Unix. Le permite programar comandos o scripts para que se ejecuten automáticamente en un momento o intervalo especificado.

**Pasos para configurar una tarea cron (guía general - los pasos específicos pueden variar según el host):**

1. **Inicie sesión en su Panel de Control de Alojamiento:** Esto suele ser cPanel, Plesk o un panel de control personalizado proporcionado por su host.
2. **Busque "Tareas Cron" o "Tareas Programadas":** Busque una sección relacionada con las tareas cron, a menudo bajo "Avanzado" o "Herramientas".
3. **Agregue una Nueva Tarea Cron:**
   - Normalmente, deberá especificar la frecuencia (por ejemplo, una vez al día, una vez a la semana). Un buen punto de partida es una vez al día o una vez cada pocos días.
   - Deberá proporcionar el "Comando" o "URL a llamar". Aquí es donde pegará la **URL de la Tarea Cron** que copió de la página de configuración del módulo.
   - El formato del comando a menudo se ve así:

     Terminal window

     ```
     wget -q -O /dev/null "SU\_URL\_TAREA\_CRON\_AQUI"
     ```

     Reemplace `"SU_URL_TAREA_CRON_AQUI"` con la URL exacta del módulo. El comando `wget` obtiene la URL, y `-q -O /dev/null` asegura que se ejecute silenciosamente sin guardar la salida, lo cual es ideal para tareas en segundo plano.
4. **Guarde la Tarea Cron:** Confirme su configuración para activar la tarea programada.

**Ejemplos de Frecuencias de Tareas Cron:**

- **Una vez al día (por ejemplo, 3 AM):**
  `0 3 * * * wget -q -O /dev/null "SU_URL_TAREA_CRON_AQUI"`
- **Una vez a la semana (por ejemplo, cada domingo a las 4 AM):**
  `0 4 * * 0 wget -q -O /dev/null "SU_URL_TAREA_CRON_AQUI"`

Elija un momento en el que su tienda tenga poco tráfico para minimizar cualquier impacto potencial (aunque generalmente insignificante) en el rendimiento durante la limpieza.

### 2.2 Tabla de Referencia Rápida de Configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| Configuración del Módulo | URL de la Tarea Cron | (Generada automáticamente) | La URL que debe ser llamada por el sistema de tareas cron de su alojamiento para activar la optimización automática de la base de datos. Cópiela exactamente. |
| Configuración del Módulo | Ejecutar Optimización Ahora | Haga clic para ejecutar | Activa manualmente una limpieza inmediata de la base de datos. Útil para pruebas o optimización bajo demanda. |

## 3. Solución de Problemas del Comerciante y Preguntas Frecuentes (FAQ)

**P: He configurado la tarea cron, pero no veo ninguna diferencia en la velocidad de mi tienda.**
R: La optimización de la base de datos proporciona mejoras incrementales. Si su tienda ya era relativamente rápida, el cambio podría no ser dramático.
- **Verifique su tarea cron:** Asegúrese de que esté configurada correctamente en su host y que se esté ejecutando. Algunos hosts proporcionan registros para la ejecución de tareas cron.
- **Ejecutar manualmente:** Haga clic en "Ejecutar Optimización Ahora" en la configuración del módulo. Si esto funciona, el problema probablemente esté en la configuración de su tarea cron.
- **Borrar caché de Smarty:** A veces, los cambios visuales o las mejoras de velocidad requieren borrar el caché de PrestaShop. Vaya a **Parámetros Avanzados > Rendimiento**, desplácese hasta "Borrar caché" y haga clic en "Borrar caché".

**P: ¿Qué datos limpia realmente este módulo?**
R: El módulo se dirige a varios tipos de datos temporales y obsoletos que se acumulan en su base de datos, como:
- Carritos de invitados antiguos que nunca se convirtieron en pedidos.
- Sesiones caducadas.
- Entradas de registro antiguas (registros de acceso, registros de página no encontrada).
- Archivos temporales y datos de caché almacenados en la base de datos.
NO elimina datos de clientes, pedidos, productos ni ninguna información esencial de la tienda.

**P: ¿Puede este módulo dañar mi tienda?**
R: Este módulo está diseñado para eliminar de forma segura solo datos no esenciales, temporales u obsoletos. No toca datos críticos de la tienda como productos, pedidos, clientes o categorías. Sin embargo, como con cualquier módulo que interactúa con su base de datos, siempre se recomienda tener una copia de seguridad reciente antes de la instalación y configuración.

**P: Mi proveedor de alojamiento no admite tareas cron, o tengo problemas para configurarlas.**
R: Si no puede configurar una tarea cron, aún puede usar el módulo haciendo clic manualmente en el botón "Ejecutar Optimización Ahora" en la página de configuración del módulo cada vez que sienta que su tienda necesita una limpieza (por ejemplo, una vez a la semana o una vez al mes). Aunque no es automático, aún proporciona los beneficios de la optimización de la base de datos. Póngase en contacto con el soporte de su proveedor de alojamiento para obtener ayuda con la configuración de tareas cron; suelen ser muy útiles con esta tarea común.

**P: ¿Este módulo afecta mi SEO?**
R: Indirectamente, sí. Los tiempos de carga de página más rápidos son un factor de clasificación positivo para los motores de búsqueda como Google. Al mejorar la velocidad de su sitio, este módulo contribuye a una mejor experiencia de usuario, lo que puede influir positivamente en su rendimiento SEO.

## 4. Guía para Desarrolladores y Webmasters (Arquitectura Técnica y Mapa de Código)

Esta sección es estrictamente para desarrolladores, webmasters de tiendas y agencias técnicas que mantienen o extienden la tienda.

### 4.1 Resumen de la Arquitectura

El módulo `Database Optimization Pro` es una herramienta de administración ligera centrada principalmente en el mantenimiento de la base de datos. Su funcionalidad principal gira en torno a la ejecución de una serie de consultas SQL para limpiar datos no esenciales. El aspecto "Pro" introduce un mecanismo automatizado a través de un controlador de front-office diseñado para ser activado por una tarea cron, lo que permite una optimización programada y desatendida. Se adhiere a la estructura de módulos de PrestaShop, utilizando un archivo de módulo principal para la instalación/configuración y un controlador frontal dedicado para la ejecución de la tarea cron.

### 4.2 Controladores (`controllers/`)

- **Controladores de Front-Office**:

  - `controllers/front/CronCleaner.php`
    - **Nombre de la Clase**: `DboptimizationproCronCleanerModuleFrontController`
    - **Clase Padre**: `ModuleFrontController`
    - **Responsabilidad**: Este es el controlador crítico para la funcionalidad de la tarea cron. Cuando se accede a él, ejecuta la lógica de limpieza de la base de datos. Está diseñado para ser llamado externamente (por ejemplo, por `wget` a través de una tarea cron) y no renderiza una página visible para el usuario. Realiza las consultas de optimización de la base de datos reales.
  - `controllers/front/index.php`
    - **Nombre de la Clase**: (No es una clase, típicamente un archivo vacío o una redirección)
    - **Responsabilidad**: Este archivo a menudo se incluye en los módulos de PrestaShop para evitar la lista de directorios al navegar `sutienda.com/modules/dboptimizationpro/controllers/front/`. Típicamente contiene un simple `header('Location: ../../../index.php'); exit;` o similar para redirigir a la página de inicio, garantizando la seguridad.
- **Controladores de Administración de Back-Office**:

  - No hay controladores de administración dedicados presentes. Toda la configuración del back-office se maneja directamente dentro del método `getContent()` del archivo principal del módulo.

### 4.3 Clases y Modelos Principales (`classes/`)

No hay clases personalizadas o definiciones de `ObjectModel` presentes en el directorio `classes/`. La lógica del módulo está encapsulada dentro del archivo principal del módulo (`dboptimizationpro/cronjob.php`) y el controlador frontal `CronCleaner`. Las interacciones con la base de datos son probablemente consultas SQL directas ejecutadas a través de `Db::getInstance()->execute()`.

### 4.4 Activos JavaScript (`views/js/`)

No se encuentran archivos JavaScript personalizados en el archivo del módulo. La funcionalidad del módulo es del lado del servidor.

### 4.5 Hojas de Estilo CSS (`views/css/`)

No se encuentran archivos CSS personalizados en el archivo del módulo. La página de configuración del módulo utiliza el estilo estándar del back-office de PrestaShop.

### 4.6 Estructura de Plantillas Smarty (`views/templates/`)

No se encuentran archivos de plantilla Smarty (`.tpl`) personalizados en el archivo del módulo. El formulario de configuración del módulo se renderiza directamente dentro del método `getContent()` del archivo principal del módulo utilizando los formularios de ayuda de PrestaShop o HTML sin procesar.

### 4.7 Esquema de la Base de Datos y Mapa de Ganchos

- **Tablas de la Base de Datos**:

  - El módulo no crea ninguna tabla de base de datos personalizada.
  - Interactúa con las tablas existentes de PrestaShop para eliminar datos obsoletos (por ejemplo, `ps_cart`, `ps_connections`, `ps_log`, `ps_guest`, `ps_pagenotfound`).
  - La configuración (como la URL de la tarea cron o una bandera que indica la última ejecución) se almacena en la tabla `ps_configuration`, típicamente con claves prefijadas por `DBOPTIMIZATIONPRO_`.
- **Tabla de Ganchos Registrados**:
  El módulo no registra explícitamente ningún gancho de front-office (por ejemplo, `displayHeader`, `displayRightColumn`, `displayFooter`) para mostrar contenido. Su interacción principal con el sistema de ganchos de PrestaShop es para la instalación/desinstalación del módulo y potencialmente para la integración del menú del back-office (aunque no se enumera explícitamente como un controlador de administración, el módulo mismo aparece en la lista de Módulos).

  La funcionalidad principal del módulo se activa mediante:

  - Acceso al método `getContent()` en el back office para configuración y ejecución manual.
  - Acceso al controlador frontal `CronCleaner` a través de una tarea cron externa.

## 5. Soporte Oficial y Actualizaciones

Para actualizaciones oficiales, soporte técnico y para descargar las últimas versiones del módulo "Database Optimization Pro", inicie sesión en su cuenta de cliente en [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nuestro equipo de soporte está disponible para ayudarle con cualquier problema o pregunta que pueda tener con respecto a la funcionalidad y configuración del módulo.
