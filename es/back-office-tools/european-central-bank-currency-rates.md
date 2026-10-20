---
title: "Tasas de cambio del Banco Central Europeo - Manual para el Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop 'Tasas de cambio del Banco Central Europeo' de MyPresta.eu."
sidebar:
  label: "Tasas de cambio del Banco Central Europeo - Manual para el Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo European Central Bank currency rates en MyPresta.eu](https://mypresta.eu/modules/administration-tools/european-central-bank-currency-rates.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/back-office-tools/european-central-bank-currency-rates/)
>
> ---


# Tasas de cambio del Banco Central Europeo

## 1. Requisitos y compatibilidad

- **Versiones de PrestaShop compatibles**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x
- **Compatibilidad con PHP**: PHP 5.6 - 8.5
- **Requisitos de alojamiento**: Las extensiones PHP estándar (cURL, JSON, OpenSSL) suelen ser necesarias para obtener datos externos, las cuales están casi universalmente disponibles en los entornos de alojamiento modernos.

## 2. Recorrido completo de la configuración (Cada ajuste agrupado por pantalla)

### 2.1 Página de configuración del módulo (Back Office > Módulos > Configurar)

Después de la instalación, haga clic en "Configurar" para acceder a la configuración principal del módulo. Aquí es donde usted controla cómo y cuándo se actualizan sus tipos de cambio.

La pantalla de configuración normalmente presentará un formulario con opciones para habilitar/deshabilitar la funcionalidad del módulo y, potencialmente, una forma de activar manualmente una actualización o configurar un trabajo cron.

**URL del Cronjob:**

- **Qué hace esta configuración:** Muestra una URL única que, al ser accedida, activa el módulo para obtener los últimos tipos de cambio del Banco Central Europeo y actualizarlos en su tienda PrestaShop. Este es el mecanismo principal para las actualizaciones automatizadas.
- **Efecto de cambiar esta configuración:** Esta es una URL de solo lectura generada por el módulo. No la cambia directamente.
  - *Cuando se usa en un cron job:* Sus tipos de cambio se actualizarán automáticamente a intervalos regulares sin ninguna intervención manual.
  - *Cuando no se usa:* Las tasas solo se actualizarán si hace clic manualmente en el botón "Actualizar ahora" (si está disponible) o si se utiliza el mecanismo de actualización de moneda predeterminado de PrestaShop, menos fiable.
- **Valor recomendado:** Copie esta URL y configúrela como un cron job en su servidor de alojamiento. Esta es la forma más eficiente y fiable de mantener sus tasas actualizadas.
- **Escenario / ejemplo del comerciante:** Desea que sus tipos de cambio se actualicen todos los días a las 3 AM. Copia esta URL y la añade al programador de cron jobs de su panel de control de alojamiento, configurado para ejecutarse diariamente a las 3 AM.

**Botón "Actualizar ahora" (si está presente):**

- **Qué hace esta configuración:** Este es un disparador manual para obtener y actualizar inmediatamente todos los tipos de cambio del BCE.
- **Efecto de cambiar esta configuración:**
  - *Cuando se hace clic:* El módulo se conectará instantáneamente al BCE, recuperará los últimos tipos de cambio y los aplicará a las monedas de su tienda. Esto es útil para actualizaciones inmediatas o pruebas.
- **Valor recomendado:** Úselo para pruebas de configuración inicial o si necesita una actualización inmediata fuera de sus trabajos cron programados. Para actualizaciones regulares, confíe en el cron job.
- **Escenario / ejemplo del comerciante:** Acaba de instalar el módulo y quiere asegurarse de que funciona correctamente. Hace clic en "Actualizar ahora" y luego verifica sus tipos de cambio en PrestaShop para confirmar que han cambiado.

**Configuración general del módulo (si está presente, por ejemplo, Habilitar/Deshabilitar):**

- **Qué hace esta configuración:** Este es un interruptor estándar del módulo de PrestaShop para activar o desactivar la funcionalidad principal del módulo.
- **Efecto de cambiar esta configuración:**
  - *Cuando está habilitado:* El módulo estará activo y su URL de cron job funcionará, permitiendo actualizaciones automáticas de moneda.
  - *Cuando está deshabilitado:* El módulo no realizará ninguna actualización y la URL de cron job no funcionará. Sus tipos de cambio no serán actualizados por este módulo.
- **Valor recomendado:** **SÍ** (Habilitado) para asegurar que sus tipos de cambio se actualicen automáticamente.
- **Escenario / ejemplo del comerciante:** Quiere que el módulo gestione sus tipos de cambio, por lo que se asegura de que esté habilitado. Si por alguna razón quisiera detener temporalmente las actualizaciones automáticas, lo deshabilitaría.

### 2.2 Pantallas de administración dedicadas y vistas de controlador

Este módulo no introduce ninguna pantalla de administración nueva o controladores personalizados dedicados más allá de su página de configuración principal. Todas las interacciones ocurren directamente en el formulario de configuración del módulo.

### 2.3 Tabla de referencia rápida de configuración

| Pantalla / Vista | Configuración / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| Página de configuración del módulo | URL del Cronjob | Copiar y configurar en el alojamiento | Activa las actualizaciones automáticas de los tipos de cambio del BCE. Esencial para una operación sin intervención manual. |
| Página de configuración del módulo | Botón Actualizar ahora | Usar para pruebas/actualización manual | Obtiene y aplica inmediatamente las últimas tasas del BCE. |
| Página de configuración del módulo | Módulo Habilitado/Deshabilitado | Habilitado (SÍ) | Activa o desactiva la funcionalidad de actualización de moneda del módulo. |

## 3. Solución de problemas del comerciante y preguntas frecuentes (FAQ)

**P: Mis tipos de cambio no se actualizan automáticamente. ¿Qué debo verificar?**
R:

1. **Configuración del Cron Job:** El problema más común es un cron job configurado incorrectamente. Verifique la URL que ha utilizado en su panel de alojamiento y asegúrese de que la programación esté activa y sea correcta.
2. **Módulo Habilitado:** Asegúrese de que el módulo "Tasas de cambio del Banco Central Europeo" esté habilitado en su Back Office de PrestaShop (**Módulos > Gestor de módulos**).
3. **Versión de PHP:** Asegúrese de que su versión de PHP esté dentro del rango de compatibilidad del módulo (PHP 5.6 - 8.5).
4. **Registros del servidor:** Verifique los registros de cron job de su servidor (si su host los proporciona) para detectar cualquier error cuando el cron job intente ejecutarse.
5. **Actualización manual:** Intente hacer clic en el botón "Actualizar ahora" en la página de configuración del módulo. Si esto funciona, el problema es definitivamente con la configuración de su cron job.

**P: Las tasas se actualizaron, pero parecen incorrectas o diferentes de lo que esperaba.**
R:

1. **Fuente del BCE:** Este módulo obtiene las tasas directamente del Banco Central Europeo. Estas son tasas interbancarias oficiales, que pueden diferir ligeramente de las tasas al consumidor que ve en Google u otros sitios financieros debido a tarifas bancarias, márgenes o diferentes tiempos de actualización.
2. **Moneda base:** Asegúrese de que la moneda predeterminada de su PrestaShop esté configurada correctamente. El módulo actualiza las tasas en relación con la moneda base.
3. **Caché:** Borre la caché de su PrestaShop (**Parámetros avanzados > Rendimiento**) después de una actualización para asegurarse de que está viendo los datos más recientes.

**P: ¿Este módulo funciona con temas personalizados?**
R: Sí, absolutamente. Este módulo funciona en segundo plano para actualizar datos (tipos de cambio) en su base de datos. No genera ningún elemento visual ni modifica el diseño de su tema, por lo que es totalmente compatible con cualquier tema de PrestaShop.

**P: ¿Con qué frecuencia debo actualizar los tipos de cambio?**
R: Para la mayoría de las tiendas de comercio electrónico, la actualización diaria es suficiente. Si trata con artículos de alto valor u opera en mercados muy volátiles, podría considerar actualizar dos veces al día. El BCE suele publicar sus tasas de referencia una vez al día, alrededor de las 16:00 CET.

**P: Veo un "Error interno del servidor 500" al intentar acceder directamente a la URL del cron job.**
R: Esto suele indicar un error de PHP. Revise los registros de errores de PHP de su servidor para obtener detalles más específicos. Las causas comunes podrían ser permisos de archivo incorrectos, una extensión PHP faltante o un conflicto con otro módulo. Póngase en contacto con su proveedor de alojamiento o un desarrollador con los detalles del registro de errores.

## 4. Guía para desarrolladores y webmasters (Arquitectura técnica y mapa de código)

Esta sección proporciona una descripción técnica detallada para desarrolladores y webmasters.

### 4.1 Resumen de la arquitectura

El módulo "Tasas de cambio del Banco Central Europeo" (`ecbrates`) es un módulo ligero de PrestaShop diseñado principalmente para automatizar la actualización de los tipos de cambio de `ps_currency`. Sigue un patrón de diseño simple:

- Un único archivo principal del módulo (`cronjob.php`) maneja la instalación, desinstalación y la lógica central para obtener y actualizar los tipos de cambio.
- El módulo expone un método `getContent()` para su configuración en el Back Office, que renderiza una plantilla básica.
- La funcionalidad principal se activa mediante una llamada directa al archivo `cronjob.php` del módulo, típicamente por un trabajo cron del lado del servidor, omitiendo el enrutamiento estándar del controlador de front/admin de PrestaShop para mayor eficiencia.

### 4.2 Controladores (`controllers/`)

Este módulo no utiliza los controladores estándar de Front-Office o Back-Office de PrestaShop. Su lógica de actualización principal es directamente accesible a través del archivo `cronjob.php`, que actúa como un script independiente cuando se llama a través de la URL del cron.

### 4.3 Clases y modelos principales (`classes/`)

Este módulo no define ninguna clase personalizada ni extiende `ObjectModel`. Toda la lógica está contenida dentro del archivo principal `ecbrates/cronjob.php`. Interactúa directamente con la clase `Currency` y la clase `Configuration` de PrestaShop.

### 4.4 Activos JavaScript (`views/js/`)

Este módulo no incluye ningún archivo JavaScript personalizado.

### 4.5 Hojas de estilo CSS (`views/css/`)

Este módulo no incluye ningún archivo CSS personalizado.

### 4.6 Estructura de la plantilla Smarty (`views/templates/`)

- **Plantillas de administración (`views/templates/admin/`)**:
  - `ecbrates/views/admin.tpl`: Esta plantilla es renderizada por el método `getContent()` del archivo principal del módulo. Muestra el formulario de configuración del módulo, incluyendo la URL del cron job y, potencialmente, un botón de actualización manual. Es una plantilla simple para la configuración del módulo.

### 4.7 Esquema de la base de datos y mapa de hooks

- **Tablas de la base de datos**:

  - Este módulo no crea ninguna tabla de base de datos personalizada.
  - Interactúa con la tabla estándar `ps_currency` de PrestaShop para actualizar la columna `conversion_rate` para las monedas activas.
  - Almacena su configuración (por ejemplo, el estado de habilitación del módulo) en la tabla `ps_configuration`, utilizando claves como `ECBRATES_LAST_UPDATE` o similar, aunque las claves específicas no se detallan explícitamente en la información proporcionada.
- **Tabla de Hooks registrados**:
  Este módulo no se registra explícitamente en ningún hook estándar de PrestaShop en el sentido tradicional (por ejemplo, `displayHeader`, `actionValidateOrder`) para su funcionalidad principal. Su mecanismo principal es una llamada directa a su archivo `cronjob.php`.

  Sin embargo, como módulo de PrestaShop, utiliza implícitamente:

  | Nombre del Hook | Momento de ejecución | Propósito técnico |
  | --- | --- | --- |
  | `install()` | Durante la instalación del módulo | Crea entradas de configuración, potencialmente establece tasas iniciales. |
  | `uninstall()` | Durante la desinstalación del módulo | Limpia las entradas de configuración. |
  | `getContent()` | Al acceder a la configuración del módulo en el BO | Renderiza el formulario de configuración del módulo. |

  La funcionalidad principal del módulo (obtener y actualizar tasas) se activa mediante el acceso HTTP directo a `cronjob.php`, no por un hook de PrestaShop.

## 5. Soporte oficial y actualizaciones

Para actualizaciones oficiales, soporte técnico y asistencia adicional con el módulo "Tasas de cambio del Banco Central Europeo", consulte su cuenta de cliente en [MyPresta.eu](https://mypresta.eu/). Puede descargar las últimas versiones del módulo desde su historial de pedidos. Para soporte, utilice los canales de soporte dedicados proporcionados en el sitio web de MyPresta.eu.
