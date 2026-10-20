---
title: "Etiqueta UET y API de Conversiones de Microsoft Advertising - Manual de Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop Etiqueta UET y API de Conversiones de Microsoft Advertising de MyPresta.eu."
sidebar:
  label: "Etiqueta UET y API de Conversiones de Microsoft Advertising - Manual de Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Microsoft Advertising UET Tag & Conversions API en MyPresta.eu](https://mypresta.eu/modules/advertising-and-marketing/microsoft-advertising-uet-tag-conversions-api.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/advertising-marketing/microsoft-advertising-uet-tag-conversions-api/)
>
> ---


# Etiqueta UET y API de Conversiones de Microsoft Advertising

## 1. Requisitos y Compatibilidad

- **Versiones de PrestaShop Compatibles**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilidad con PHP**: PHP 7.1 - 8.5
- **Requisitos de Alojamiento**: Se requieren extensiones PHP estándar como cURL, JSON y OpenSSL para que el módulo funcione correctamente, especialmente para las funciones de la API de Conversiones. Estas suelen estar habilitadas por defecto en la mayoría de los entornos de alojamiento modernos.

## 2. Recorrido Completo por la Configuración (Cada Ajuste Agrupado por Pantalla)

### 2.1 Página de Configuración del Módulo (Back Office > Módulos > Configurar)

Este es el centro principal para configurar tu seguimiento de Microsoft Advertising. Encontrarás una serie de pestañas y configuraciones diseñadas para guiarte a través del proceso.

#### Pestaña de Configuración Principal (Vista Inicial)

-   **Qué hace esta configuración:** Esta pestaña suele proporcionar una visión general y opciones de configuración iniciales, a menudo incluyendo un asistente para simplificar la configuración por primera vez.
-   **Efecto de cambiar esta configuración:** Completar el asistente o rellenar los detalles iniciales habilitará la funcionalidad básica de seguimiento y preparará el módulo para configuraciones más avanzadas.
-   **Valor recomendado:** Sigue cuidadosamente los pasos del asistente.
-   **Escenario / ejemplo de comerciante:** Cuando instalas el módulo por primera vez, el asistente te pedirá tu ID de etiqueta UET y te guiará para elegir tu método de seguimiento (Etiqueta UET, API de Conversiones o ambos).

#### ID de Etiqueta UET

-   **Qué hace esta configuración:** Este es tu identificador único proporcionado por Microsoft Advertising. Le dice a Microsoft con qué cuenta asociar los datos de seguimiento.
-   **Efecto de cambiar esta configuración:**
    -   *Cuando se introduce correctamente:* El módulo incrustará la etiqueta UET en tu tienda, permitiendo a Microsoft Advertising rastrear el comportamiento del usuario.
    -   *Cuando se deja vacío o es incorrecto:* No se realizará el seguimiento de la etiqueta UET y tus campañas de Microsoft Advertising no recibirán datos de conversión del front-office.
-   **Valor recomendado:** Tu ID de etiqueta UET exacto de tu cuenta de Microsoft Advertising.
-   **Escenario / ejemplo de comerciante:** Has creado una cuenta de Microsoft Advertising y configurado una etiqueta UET. Copias el ID (por ejemplo, `12345678`) y lo pegas aquí.

#### Modo de Seguimiento (Etiqueta UET, API de Conversiones o Ambos)

-   **Qué hace esta configuración:** Determina cómo se envían los datos de conversión a Microsoft Advertising.
    -   **Solo Etiqueta UET:** Seguimiento tradicional del lado del cliente a través de JavaScript en el navegador del cliente.
    -   **Solo API de Conversiones:** Seguimiento del lado del servidor, enviando datos directamente desde tu servidor PrestaShop a Microsoft. Más resistente a las configuraciones de privacidad del navegador.
    -   **Ambos (Híbrido):** Utiliza tanto la etiqueta UET como la API de Conversiones, con un mecanismo para deduplicar eventos, asegurando un recuento preciso incluso si ambos métodos informan la misma conversión.
-   **Efecto de cambiar esta configuración:**
    -   *Solo Etiqueta UET:* Se basa únicamente en el seguimiento basado en el navegador, que puede verse afectado por bloqueadores de anuncios o configuraciones de privacidad.
    -   *Solo API de Conversiones:* Proporciona un seguimiento más robusto, pero requiere configuración del lado del servidor y puede no capturar todos los eventos del lado del cliente (como las visitas a la página) tan fácilmente.
    -   *Ambos (Híbrido):* Ofrece el seguimiento más completo y fiable, combinando las fortalezas de ambos métodos al tiempo que evita conversiones duplicadas.
-   **Valor recomendado:** **Ambos (Híbrido)** se recomienda generalmente para una máxima precisión y resistencia.
-   **Escenario / ejemplo de comerciante:** Quieres los datos más precisos posibles, por lo que seleccionas "Ambos (Híbrido)" para asegurar que las conversiones se rastreen incluso si un cliente utiliza un bloqueador de anuncios.

#### Token de Acceso a la API de Conversiones

-   **Qué hace esta configuración:** Este es un token seguro generado en tu cuenta de Microsoft Advertising, que autoriza a tu tienda PrestaShop a enviar datos directamente a los servidores de Microsoft a través de la API de Conversiones.
-   **Efecto de cambiar esta configuración:**
    -   *Cuando se introduce correctamente:* Habilita el seguimiento del lado del servidor para la API de Conversiones.
    -   *Cuando se deja vacío o es incorrecto:* La API de Conversiones no funcionará y no se enviarán datos de conversión del lado del servidor.
-   **Valor recomendado:** Tu Token de Acceso a la API de Conversiones exacto de tu cuenta de Microsoft Advertising.
-   **Escenario / ejemplo de comerciante:** Has generado un Token de Acceso en tu cuenta de Microsoft Advertising (por ejemplo, en "Herramientas" > "Seguimiento de Conversiones" > "API de Conversiones"). Pegas esta larga cadena de caracteres aquí.

#### Habilitar Conversiones Mejoradas

-   **Qué hace esta configuración:** Cuando está habilitada, esta función envía datos de clientes con hash (como direcciones de correo electrónico) junto con los eventos de conversión. Esto ayuda a Microsoft a hacer coincidir las conversiones con mayor precisión, especialmente cuando las cookies son limitadas, mejorando el rendimiento de tu campaña.
-   **Efecto de cambiar esta configuración:**
    -   *Cuando está habilitada:* Coincidencia de conversiones más precisa, lo que puede conducir a una mejor optimización de tus campañas publicitarias.
    -   *Cuando está deshabilitada:* Las conversiones se basan únicamente en métodos de seguimiento estándar, que podrían ser menos precisos en ciertos entornos de navegador centrados en la privacidad.
-   **Valor recomendado:** **SÍ** (Habilitado), ya que mejora significativamente la coincidencia de datos.
-   **Escenario / ejemplo de comerciante:** Quieres proporcionar a Microsoft Advertising los mejores datos posibles para optimizar tus campañas, por lo que habilitas las Conversiones Mejoradas.

#### Integración de Gestión de Consentimiento

-   **Qué hace esta configuración:** Este módulo puede integrarse con módulos de consentimiento de cookies existentes (como módulos GDPR) para garantizar que la etiqueta UET solo se active después de que un cliente haya dado su consentimiento.
-   **Efecto de cambiar esta configuración:**
    -   *Cuando está habilitada e integrada:* La etiqueta UET respetará las opciones de consentimiento del cliente. Si un cliente rechaza las cookies de seguimiento, la etiqueta UET no se cargará.
    -   *Cuando está deshabilitada o no integrada:* La etiqueta UET podría cargarse independientemente del consentimiento, lo que podría generar problemas de cumplimiento.
-   **Valor recomendado:** **SÍ** (Habilitado) si utilizas un módulo de consentimiento de cookies y necesitas cumplir con las regulaciones de privacidad (por ejemplo, GDPR, CCPA).
-   **Escenario / ejemplo de comerciante:** Tu tienda utiliza un módulo GDPR. Habilitas esta configuración para asegurar que tu seguimiento de Microsoft Advertising cumpla con las leyes de privacidad.

#### Modo Depuración

-   **Qué hace esta configuración:** Activa un modo especial que muestra información detallada sobre la etiqueta UET y los eventos de la API de Conversiones directamente en las páginas de tu front-office (visible solo para ti, el administrador, o direcciones IP específicas). Esto es invaluable para verificar que el seguimiento esté configurado correctamente.
-   **Efecto de cambiar esta configuración:**
    -   *Cuando está habilitado:* Verás una superposición de depuración o mensajes de consola en el front-office de tu tienda, mostrando qué eventos se están rastreando y qué datos se están enviando.
    -   *Cuando está deshabilitado:* El módulo funciona silenciosamente, sin información de depuración visible.
-   **Valor recomendado:** **NO** (Deshabilitado) para tiendas en producción. **SÍ** (Habilitado) temporalmente durante la configuración y la resolución de problemas.
-   **Escenario / ejemplo de comerciante:** Acabas de instalar el módulo y quieres confirmar que los eventos de "Añadir al carrito" se están enviando correctamente. Habilitas el Modo Depuración, añades un producto a tu carrito y compruebas la salida de depuración.

#### Mapeo de Eventos (Avanzado)

-   **Qué hace esta configuración:** Te permite personalizar cómo las acciones específicas de PrestaShop (por ejemplo, "Producto Añadido al Carrito") se mapean a los nombres de eventos de Microsoft Advertising (por ejemplo, "add\_to\_cart"). También puedes definir parámetros personalizados para enviar con cada evento.
-   **Efecto de cambiar esta configuración:**
    -   *Cuando está configurado:* Asegura que tus eventos se categoricen correctamente y se enriquezcan con datos relevantes en Microsoft Advertising.
    -   *Cuando está mal configurado:* Los eventos podrían no rastrearse, o los datos enviados podrían ser inexactos, lo que llevaría a una mala optimización de la campaña.
-   **Valor recomendado:** Utiliza los mapeos predeterminados a menos que tengas una razón específica para cambiarlos según tu configuración de Microsoft Advertising.
-   **Escenario / ejemplo de comerciante:** Quieres enviar la marca del producto como un parámetro personalizado con cada evento "view\_item". Configurarías este mapeo aquí.

#### Dominios de Enlace (Avanzado)

-   **Qué hace esta configuración:** Si tienes varios subdominios o sitios web relacionados que comparten la misma etiqueta UET, esta configuración ayuda a garantizar que las sesiones de usuario se vinculen correctamente entre estos dominios.
-   **Efecto de cambiar esta configuración:**
    -   *Cuando está configurado:* Permite un seguimiento fluido de los recorridos de los usuarios en múltiples dominios bajo tu control.
    -   *Cuando no está configurado (y es necesario):* Las sesiones de usuario podrían romperse, lo que llevaría a una atribución de conversión inexacta.
-   **Valor recomendado:** Déjalo vacío a menos que operes múltiples subdominios o sitios relacionados que necesiten seguimiento entre dominios.
-   **Escenario / ejemplo de comerciante:** Tienes tu tienda principal en `shop.example.com` y un blog en `blog.example.com`, ambos utilizando la misma etiqueta UET. Añadirías `blog.example.com` a la lista de dominios de enlace.

#### Tabla de Referencia Rápida de Configuración

| Pantalla / Vista | Configuración / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| Config. Principal | ID de Etiqueta UET | Tu ID de Etiqueta | Habilita el seguimiento de la etiqueta UET. Esencial para los datos del lado del cliente. |
| Config. Principal | Modo de Seguimiento | Ambos (Híbrido) | Selecciona Etiqueta UET, API de Conversiones o ambos para la transmisión de datos. Híbrido es el más robusto. |
| Config. Principal | Token de Acceso a la API de Conversiones | Tu Token de Acceso | Autoriza el envío de datos del lado del servidor a Microsoft. |
| Config. Principal | Habilitar Conversiones Mejoradas | SÍ | Mejora la precisión de la coincidencia de conversiones enviando datos de clientes con hash. |
| Config. Principal | Integración de Gestión de Consentimiento | SÍ (si aplica) | Asegura que la etiqueta UET respete las opciones de privacidad del cliente (GDPR, CCPA). |
| Config. Principal | Modo Depuración | NO (SÍ para pruebas) | Muestra datos de seguimiento en el front-office para verificación. |
| Config. Principal | Mapeo de Eventos | Predeterminado | Personaliza cómo las acciones de PrestaShop se mapean a los eventos de Microsoft. |
| Config. Principal | Dominios de Enlace | Vacío (si no es necesario) | Habilita el seguimiento entre dominios para sitios web relacionados. |

### 2.2 Pantallas de Administración Dedicadas y Vistas de Controlador

#### 2.2.1 AdminMybingAjaxController (Back Office > Módulos > Etiqueta UET y API de Conversiones de Microsoft Advertising > Estadísticas en Vivo / Puntuación de Salud / Doctor / Calidad de Datos)

Este controlador impulsa las secciones dinámicas e interactivas de la configuración del módulo, proporcionando información en tiempo real y herramientas de diagnóstico. No navegarás a un elemento de menú separado para esto, sino que interactuarás con pestañas específicas dentro de la configuración principal del módulo.

-   **Nombre de la Pantalla y Ubicación del Menú:** Estas son típicamente subpestañas dentro de la página de configuración principal del módulo (por ejemplo, "Estadísticas en Vivo", "Puntuación de Salud", "Entrenador de Calidad de Datos", "Doctor de Catálogo").
-   **Acciones y Configuraciones Disponibles:**
    -   **Estadísticas en Vivo:** Muestra los eventos recientes enviados a Microsoft Advertising, mostrando visitas a la página, adiciones al carrito, compras, etc., casi en tiempo real. Esto te ayuda a confirmar que los eventos se están activando correctamente.
    -   **Puntuación de Salud:** Analiza tu configuración de seguimiento y proporciona una puntuación basada en las mejores prácticas, destacando posibles problemas o áreas de mejora.
    -   **Entrenador de Calidad de Datos:** Ofrece recomendaciones específicas para mejorar la calidad y la integridad de los datos que estás enviando a Microsoft, especialmente para las Conversiones Mejoradas.
    -   **Doctor de Catálogo:** Ayuda a diagnosticar problemas con los datos de tus productos que podrían afectar la publicidad de feeds de productos o el remarketing dinámico.
-   **Efecto de los cambios:** La interacción con estas pantallas proporciona principalmente información y retroalimentación de diagnóstico. No hay "configuraciones" directas para cambiar aquí, pero la información obtenida informará los ajustes que puedas realizar en la configuración principal o en tu catálogo de productos.
-   **Flujo de trabajo recomendado para la gestión diaria de la tienda:**
    -   Verifica regularmente las **Estadísticas en Vivo** después de realizar cambios o lanzar nuevas campañas para asegurarte de que los eventos se estén rastreando.
    -   Revisa periódicamente la **Puntuación de Salud** y el **Entrenador de Calidad de Datos** para obtener recomendaciones para optimizar tu configuración de seguimiento.
    -   Si encuentras problemas con los anuncios relacionados con productos, consulta el **Doctor de Catálogo**.

#### 2.2.2 index.php (Back Office > Módulos > Etiqueta UET y API de Conversiones de Microsoft Advertising)

Esto se refiere al punto de entrada principal para la interfaz de back-office del módulo, que es la propia página de configuración. Todas las configuraciones descritas en la sección 4.1 se gestionan a través de esta vista principal. No hay una pantalla "index.php" separada a la que navegar más allá de la configuración inicial del módulo.

## 3. Resolución de Problemas del Comerciante y Preguntas Frecuentes (FAQ)

**P: Mis conversiones no aparecen en Microsoft Advertising. ¿Qué debo hacer?**
R:

1.  **Verifica el ID de la Etiqueta UET y el Token de Acceso:** Vuelve a verificar que tu ID de la Etiqueta UET y el Token de Acceso a la API de Conversiones estén correctamente introducidos en la configuración del módulo. Incluso un solo error tipográfico puede impedir el seguimiento.
2.  **Verifica el Modo de Seguimiento:** Asegúrate de que tu "Modo de Seguimiento" esté configurado en "Ambos (Híbrido)" para una máxima fiabilidad.
3.  **Habilita el Modo Depuración:** Activa el "Modo Depuración" en la configuración del módulo y realiza una compra de prueba en tu tienda. Busca la superposición de depuración o los mensajes de la consola para ver si los eventos se están activando.
4.  **Borra la Caché:** Ve a **Parámetros Avanzados > Rendimiento** en tu Back Office de PrestaShop y borra la caché de Smarty y cualquier otra caché. A veces, las configuraciones antiguas pueden persistir.
5.  **Verifica la Cuenta de Microsoft Advertising:** Inicia sesión en tu cuenta de Microsoft Advertising y verifica el estado de la Etiqueta UET y la configuración del objetivo de conversión. Asegúrate de que tus objetivos de conversión estén configurados correctamente para que coincidan con los eventos enviados por el módulo (por ejemplo, "Compra").

**P: El módulo dice que la "Integración de Gestión de Consentimiento" está habilitada, pero no tengo un módulo GDPR. ¿Es esto un problema?**
R: Si no tienes un módulo de consentimiento de cookies dedicado instalado y configurado, esta configuración no tendrá ningún efecto práctico. El módulo asumirá el consentimiento por defecto. Sin embargo, para el cumplimiento legal (por ejemplo, GDPR, CCPA), se recomienda encarecidamente utilizar un módulo de consentimiento de cookies adecuado. Si instalas uno más tarde, este módulo se integrará automáticamente con él.

**P: Mi tema personalizado se ve un poco raro después de instalar el módulo, o veo una página en blanco.**
R: Este módulo funciona principalmente en segundo plano y no debería afectar la apariencia visual de tu tema.

1.  **Borra la Caché:** La solución más común para problemas de visualización después de la instalación del módulo es borrar la caché de PrestaShop (**Parámetros Avanzados > Rendimiento**).
2.  **Verifica Conflictos:** Si el problema persiste, deshabilita temporalmente otros módulos instalados recientemente para buscar conflictos.
3.  **Errores de PHP:** Si ves una página en blanco, habilita la notificación de errores de PHP en tu servidor (o revisa los registros de errores de tu servidor) para identificar cualquier error crítico.
    Si el problema continúa, contacta con el soporte de MyPresta.eu con los detalles de tu tema y cualquier mensaje de error.

**P: ¿Cómo traduzco los textos del módulo a otros idiomas?**
R:

1.  Ve a **Internacional > Traducciones** en tu Back Office de PrestaShop.
2.  Selecciona "Traducciones de módulos instalados" como tipo de traducción.
3.  Elige tu tema, el idioma al que quieres traducir y luego selecciona "Etiqueta UET y API de Conversiones de Microsoft Advertising" de la lista de módulos.
4.  Luego podrás traducir cualquier cadena visible utilizada por el módulo.

**P: ¿Por qué el "Entrenador de Calidad de Datos" o la "Puntuación de Salud" muestran advertencias?**
R: Estas herramientas están diseñadas para ayudarte a optimizar tu seguimiento. Las advertencias a menudo indican:

-   **Faltan Datos de Conversión Mejorados:** Asegúrate de que los datos del cliente (como el correo electrónico) estén disponibles y se estén enviando.
-   **Problemas con los Datos del Producto:** Tu catálogo de productos podría tener GTIN, MPN u otros identificadores faltantes cruciales para la publicidad de feeds de productos.
-   **Bajo Volumen de Eventos:** Si tu tienda tiene muy poco tráfico, las herramientas podrían no tener suficientes datos para proporcionar un análisis completo.
    Aborda las recomendaciones específicas proporcionadas por las herramientas para mejorar la calidad de tus datos y la salud del seguimiento.

## 4. Guía para Desarrolladores y Webmasters (Arquitectura Técnica y Mapa de Código)

### 4.1 Visión General de la Arquitectura

El módulo `Etiqueta UET y API de Conversiones de Microsoft Advertising` (`mybing`) está construido siguiendo el patrón MVC (Modelo-Vista-Controlador) de PrestaShop, con un fuerte énfasis en la modularidad y la extensibilidad. Utiliza un patrón de fábrica para la instanciación del rastreador (`MybingTrackerFactory`) para admitir diferentes modos de seguimiento (UET, CAPI, Híbrido) y aprovecha un sistema de eventos robusto (`MybingEvents`) para capturar varias acciones de comercio electrónico. La calidad de los datos y los diagnósticos son gestionados por clases dedicadas (`MybingHealthScore`, `MybingDataQualityCoach`, `MybingCatalogDoctor`). El módulo se integra con el sistema de hooks de PrestaShop para la inyección de eventos en el front-office y utiliza controladores de administración dedicados para su configuración avanzada y herramientas de diagnóstico.

### 4.2 Controladores (`controllers/`)

#### Controladores del Front-Office

-   `mybing/controllers/front/ajax.php`
    -   **Nombre de la Clase:** `MybingAjaxModuleFrontController` (extiende `ModuleFrontController`)
    -   **Responsabilidad:** Maneja las solicitudes AJAX del front-office, principalmente para enviar eventos o datos del lado del cliente que no pueden ser manejados directamente por la etiqueta UET (por ejemplo, para la integración de la gestión de consentimiento, o la recopilación de datos específicos antes de una redirección de página). También podría usarse para enviar eventos CAPI que se activan del lado del cliente pero necesitan procesamiento del lado del servidor.
-   `mybing/controllers/front/cron.php`
    -   **Nombre de la Clase:** `MybingCronModuleFrontController` (extiende `ModuleFrontController`)
    -   **Responsabilidad:** Proporciona un punto final para un trabajo cron. Esto se usa típicamente para tareas del lado del servidor que necesitan ejecutarse periódicamente, como enviar eventos de la API de Conversiones diferidos, sincronizar datos o realizar tareas de mantenimiento relacionadas con la funcionalidad del módulo.
-   `mybing/controllers/front/index.php`
    -   **Nombre de la Clase:** `MybingIndexModuleFrontController` (extiende `ModuleFrontController`)
    -   **Responsabilidad:** Un controlador frontal genérico, a menudo utilizado como respaldo o para interacciones simples del front-office que no son AJAX. En este módulo, podría usarse para redirecciones específicas o para manejar solicitudes iniciales relacionadas con la configuración del seguimiento.

#### Controladores de Administración del Back-Office

-   `mybing/controllers/admin/AdminMybingAjaxController.php`
    -   **Nombre de la Clase:** `AdminMybingAjaxController` (extiende `AdminController`)
    -   **Nombre de la Pestaña:** No es una pestaña independiente, sino un punto final AJAX para la configuración principal del módulo.
    -   **Entidad Gestionada:** Maneja la carga y el procesamiento dinámico de datos para las pestañas de diagnóstico y estadísticas del módulo (Estadísticas en Vivo, Puntuación de Salud, Entrenador de Calidad de Datos, Doctor de Catálogo). Procesa solicitudes de registros de eventos, comprobaciones de salud e informes de calidad de datos, devolviendo respuestas JSON al JavaScript de administración.
-   `mybing/controllers/admin/index.php`
    -   **Nombre de la Clase:** `AdminMybingIndexController` (extiende `AdminController`)
    -   **Nombre de la Pestaña:** No es una pestaña independiente. Este es un marcador de posición o un controlador de administración genérico que podría usarse para redirecciones o acciones internas específicas dentro de la interfaz de administración del módulo, pero la configuración principal se maneja mediante el método `getContent()` de la clase principal del módulo.

### 4.3 Clases y Modelos Principales (`classes/`)

-   `mybing/classes/autoload.php`: Archivo de carga automática estándar de PrestaShop, que garantiza que las clases del módulo se carguen correctamente.
-   `mybing/classes/index.php`: Archivo de marcador de posición, a menudo para evitar la lista de directorios.
-   `mybing/classes/MybingCapiClient.php`: Maneja la comunicación con el punto final de la API de Conversiones de Microsoft Advertising. Encapsula las solicitudes HTTP, la autenticación (Token de Acceso) y el formato de datos para el envío de eventos del lado del servidor.
-   `mybing/classes/MybingCapiTracker.php`: Implementa `MybingTrackerInterface` para el seguimiento del lado del servidor (API de Conversiones). Responsable de recopilar datos de eventos, prepararlos para el cliente CAPI y enviarlos.
-   `mybing/classes/MybingCatalogDoctor.php`: Proporciona lógica de diagnóstico para analizar la calidad de los datos del producto, identificando problemas que podrían afectar los feeds de productos o el remarketing dinámico en Microsoft Advertising.
-   `mybing/classes/MybingConsent.php`: Gestiona la integración con módulos de consentimiento de cookies. Determina si el usuario ha dado su consentimiento para el seguimiento y controla la activación de la etiqueta UET en consecuencia.
-   `mybing/classes/MybingCurrencyHelper.php`: Clase de utilidad para manejar conversiones y formato de moneda, asegurando que los valores de los eventos se envíen correctamente a Microsoft Advertising.
-   `mybing/classes/MybingDataQualityCoach.php`: Analiza la calidad y la integridad de los datos que se envían para los eventos, especialmente para las Conversiones Mejoradas, y proporciona recomendaciones para mejorar.
-   `mybing/classes/MybingEventId.php`: Genera y gestiona IDs de eventos únicos para la deduplicación, crucial para el seguimiento híbrido (UET + CAPI).
-   `mybing/classes/MybingEventMap.php`: Define el mapeo entre las acciones de PrestaShop (por ejemplo, `actionCartSave`) y los nombres de eventos de Microsoft Advertising (por ejemplo, `add_to_cart`), incluyendo parámetros personalizados.
-   `mybing/classes/MybingEvents.php`: Clase central para definir y activar todos los eventos de comercio electrónico rastreados (por ejemplo, `PageView`, `AddToCart`, `Purchase`). Actúa como un despachador de eventos dentro del módulo.
-   `mybing/classes/MybingHealthScore.php`: Calcula una "puntuación de salud" para la configuración general del seguimiento, evaluando la configuración, la calidad de los datos y la activación de eventos.
-   `mybing/classes/MybingHybridTracker.php`: Implementa `MybingTrackerInterface` para el seguimiento híbrido. Orquesta tanto el seguimiento de la etiqueta UET como el de la API de Conversiones, asegurando la deduplicación de eventos utilizando `event_id`.
-   `mybing/classes/MybingLiveStats.php`: Recopila y proporciona estadísticas en tiempo real sobre los eventos que se están rastreando, mostradas en la interfaz de administración.
-   `mybing/classes/MybingProductIdResolver.php`: Ayuda a resolver y formatear los IDs de productos según los requisitos de Microsoft Advertising (por ejemplo, GTIN, MPN, custom\_label).
-   `mybing/classes/MybingPropertyRules.php`: Define reglas y lógica para extraer y formatear varias propiedades de eventos (por ejemplo, precio del producto, cantidad, categoría) para Microsoft Advertising.
-   `mybing/classes/MybingTrackerFactory.php`: Clase de fábrica responsable de crear la instancia de rastreador apropiada (`MybingUetTracker`, `MybingCapiTracker` o `MybingHybridTracker`) según la configuración del módulo.
-   `mybing/classes/MybingTrackerInterface.php`: Define el contrato para todas las clases de rastreadores, asegurando una interfaz consistente para los métodos de seguimiento de eventos.
-   `mybing/classes/MybingUetTracker.php`: Implementa `MybingTrackerInterface` para el seguimiento del lado del cliente (Etiqueta UET). Responsable de generar el código JavaScript que se inyectará en el front-office.
-   `mybing/classes/MybingUserData.php`: Recopila y formatea datos específicos del usuario (por ejemplo, correo electrónico, teléfono, dirección) para las Conversiones Mejoradas, incluyendo el hashing.

### 4.4 Activos JavaScript (`views/js/`)

-   `mybing/views/js/mybing-admin.js`: JavaScript del back-office para la funcionalidad general de administración, interacciones de formularios y actualizaciones dinámicas dentro de la página de configuración del módulo.
-   `mybing/views/js/mybing-debug.js`: JavaScript del front-office específicamente para el modo de depuración, mostrando información de seguimiento y cargas útiles de eventos al administrador.
-   `mybing/views/js/mybing-ghost.js`: JavaScript del front-office, potencialmente para manejar eventos "fantasma" o interacciones específicas del lado del cliente que necesitan ser rastreadas sin una acción directa del usuario.
-   `mybing/views/js/mybing-live.js`: JavaScript del back-office para la pestaña "Estadísticas en Vivo", manejando las solicitudes AJAX a `AdminMybingAjaxController` y actualizando el feed de eventos en vivo.
-   `mybing/views/js/mybing-tcf.js`: JavaScript del front-office para la integración con el Marco de Transparencia y Consentimiento (TCF) u otras plataformas de gestión de consentimiento, asegurando que la etiqueta UET se active solo con consentimiento.
-   `mybing/views/js/mybing-wizard.js`: JavaScript del back-office para el asistente de configuración inicial, guiando al comerciante a través de los pasos de configuración.
-   `mybing/views/js/mybing.js`: Archivo JavaScript principal del front-office. Contiene la lógica central para inicializar la etiqueta UET, capturar eventos del lado del cliente (por ejemplo, `add_to_cart`) y enviar datos a la etiqueta UET o al controlador AJAX del módulo para el procesamiento CAPI. Se vincula a varios eventos DOM y eventos `prestashop.on` de PrestaShop.

### 4.5 Hojas de Estilo CSS (`views/css/`)

-   `mybing/views/css/mybing-admin.css`: CSS del back-office para estilizar la página de configuración del módulo, las herramientas de diagnóstico y el asistente, asegurando una interfaz de administración consistente y fácil de usar.
-   `mybing/views/css/mybing-debug.css`: CSS del front-office para estilizar la superposición de depuración, haciendo que la información de seguimiento sea claramente visible para el administrador sin interrumpir el diseño de la tienda.

### 4.6 Estructura de Plantillas Smarty (`views/templates/`)

#### Plantillas de Hook (`views/templates/hook/`)

-   `mybing/views/templates/hook/capi-pageview.tpl`: Renderiza un elemento o script oculto para activar un evento PageView del lado del servidor a través de CAPI, a menudo utilizado cuando la etiqueta UET podría estar bloqueada.
-   `mybing/views/templates/hook/debug.tpl`: Renderiza la estructura HTML para la superposición de depuración del front-office, mostrando datos de eventos.
-   `mybing/views/templates/hook/displayOrderConfirmation.tpl`: Inyectado en el hook `displayOrderConfirmation`. Renderiza el script del evento de compra de la etiqueta UET y/o activa el evento de compra de CAPI después de un pedido exitoso.
-   `mybing/views/templates/hook/ghost.tpl`: Renderiza un script o elemento oculto para el seguimiento "fantasma", potencialmente para eventos de fondo específicos o recopilación de datos.
-   `mybing/views/templates/hook/header.tpl`: Inyectado en el hook `displayHeader`. Renderiza el script base principal de la etiqueta UET, la integración de la gestión de consentimiento y los eventos iniciales de PageView.
-   `mybing/views/templates/hook/payment.tpl`: Potencialmente utilizado para rastrear eventos relacionados con la selección o inicio del método de pago, aunque `displayOrderConfirmation` es más común para la compra final.
-   `mybing/views/templates/hook/product-details.tpl`: Inyectado en un hook de página de producto (por ejemplo, `displayProductButtons` o `displayProductExtraContent`). Renderiza scripts para eventos `view_item` y oyentes de eventos `add_to_cart`.

#### Plantillas de Administración (`views/templates/admin/`)

-   `mybing/views/templates/admin/consent-guide.tpl`: Muestra orientación e información sobre la integración de la gestión de consentimiento.
-   `mybing/views/templates/admin/doctor.tpl`: Renderiza la interfaz para la herramienta de diagnóstico "Doctor de Catálogo".
-   `mybing/views/templates/admin/dq.tpl`: Renderiza la interfaz para las recomendaciones del "Entrenador de Calidad de Datos".
-   `mybing/views/templates/admin/health.tpl`: Renderiza la interfaz para la visión general de la "Puntuación de Salud".
-   `mybing/views/templates/admin/linker-domains.tpl`: Renderiza el campo de entrada y la explicación para configurar los dominios de enlace.
-   `mybing/views/templates/admin/live-maintain.tpl`: Renderiza un mensaje de mantenimiento o estado para la función de estadísticas en vivo.
-   `mybing/views/templates/admin/live.tpl`: Renderiza la interfaz para "Estadísticas en Vivo", mostrando eventos recientes.
-   `mybing/views/templates/admin/mode-context.tpl`: Proporciona información contextual sobre el modo de seguimiento elegido.
-   `mybing/views/templates/admin/mode-note-both.tpl`: Muestra una nota o explicación específica cuando se selecciona el modo "Ambos (Híbrido)".
-   `mybing/views/templates/admin/mode-note-capi.tpl`: Muestra una nota o explicación específica cuando se selecciona el modo "Solo API de Conversiones".
-   `mybing/views/templates/admin/mode-note-uet.tpl`: Muestra una nota o explicación específica cuando se selecciona el modo "Solo Etiqueta UET".
-   `mybing/views/templates/admin/mode-picker.tpl`: Renderiza los botones de radio o el menú desplegable para seleccionar el modo de seguimiento.
-   `mybing/views/templates/admin/properties-list.tpl`: Renderiza una lista o tabla de propiedades de eventos y sus valores para configuración o visualización.
-   `mybing/views/templates/admin/recent-events.tpl`: Renderiza una tabla o lista de eventos rastreados recientemente, a menudo parte de las "Estadísticas en Vivo".
-   `mybing/views/templates/admin/tabs.tpl`: Renderiza la estructura de navegación por pestañas para la página de configuración del módulo (por ejemplo, General, Estadísticas en Vivo, Puntuación de Salud).
-   `mybing/views/templates/admin/tag-chips.tpl`: Renderiza "chips" o indicadores visuales para los IDs de etiqueta UET configurados.
-   `mybing/views/templates/admin/tag-ids.tpl`: Renderiza el campo de entrada para los IDs de etiqueta UET.
-   `mybing/views/templates/admin/wizard.tpl`: Renderiza la interfaz paso a paso para el asistente de configuración inicial.

#### Plantillas del Front-office (`views/templates/front/`)

-   No se identifican plantillas de página independientes dedicadas. La renderización del front-office se maneja principalmente a través de plantillas de hook.

### 4.7 Esquema de la Base de Datos y Mapa de Hooks

#### Tablas de la Base de Datos

El módulo no crea explícitamente tablas SQL personalizadas basadas en el inventario proporcionado. Los registros de configuración se almacenan en la tabla `ps_configuration` de PrestaShop, utilizando claves con el prefijo `MYBING_` (por ejemplo, `MYBING_UET_ID`, `MYBING_CAPI_TOKEN`, `MYBING_TRACKING_MODE`).

#### Tabla de Hooks Registrados

| Nombre del Hook | Momento de Ejecución | Propósito Técnico |
| --- | --- | --- |
| `displayHeader` | En la sección `<head>` de cada página del front-office. | Inyecta el JavaScript base de la etiqueta UET, inicializa la gestión de consentimiento y activa los eventos `PageView`. |
| `displayOrderConfirmation` | En la página de confirmación del pedido después de una compra exitosa. | Activa los eventos `Purchase` tanto para la etiqueta UET como para la API de Conversiones, incluyendo los detalles del pedido. |
| `actionFrontControllerSetMedia` | Cuando un controlador frontal establece sus activos multimedia. | Inyecta JavaScript y CSS específicos del módulo en el front-office. |
| `actionCartSave` | Cuando se añade o elimina un producto del carrito. | Activa los eventos `AddToCart` o `RemoveFromCart`. |
| `actionProductAdd` | Cuando se añade un producto al carrito (específico de algunos temas/módulos). | Hook alternativo o suplementario para eventos `AddToCart`. |
| `actionProductUpdate` | Cuando se actualiza un producto en el Back Office. | Potencialmente utilizado por el `Catalog Doctor` para reevaluar la calidad de los datos del producto. |
| `actionObjectProductUpdateAfter` | Después de que se actualiza un `ObjectModel` de producto. | Similar a `actionProductUpdate`, para comprobaciones de calidad de datos o invalidación de caché. |
| `actionObjectOrderAddAfter` | Después de que se añade un `ObjectModel` de pedido. | Activa los eventos `Purchase` del lado del servidor a través de la API de Conversiones, asegurando un seguimiento robusto. |
| `actionObjectOrderUpdateAfter` | Después de que se actualiza un `ObjectModel` de pedido. | Potencialmente para rastrear cambios de estado del pedido (por ejemplo, reembolso, cancelación) si se configura en Microsoft Ads. |
| `displayProductExtraContent` | En la página del producto, a menudo debajo del contenido principal. | Se puede utilizar para inyectar scripts de seguimiento específicos del producto o datos para eventos `ViewItem`. |
| `displayFooter` | Al final de la sección `<body>` en cada página del front-office. | Se puede utilizar para la carga diferida de scripts o elementos de seguimiento adicionales. |
| `actionAdminControllerSetMedia` | Cuando un controlador de administración establece sus activos multimedia. | Inyecta JavaScript y CSS específicos del módulo en el Back Office para la página de configuración. |
| `actionAdminMybingAjaxController` | Hook personalizado para `AdminMybingAjaxController` para manejar acciones AJAX específicas. | Utilizado internamente para actualizaciones dinámicas y recuperación de datos en las pestañas de diagnóstico del módulo. |
| `actionModuleInstall` | Durante la instalación del módulo. | Realiza la configuración inicial, crea entradas de configuración y registra hooks. |
| `actionModuleUninstall` | Durante la desinstalación del módulo. | Limpia las entradas de configuración y anula el registro de hooks. |

## 5. Soporte Oficial y Actualizaciones

Para las últimas actualizaciones del módulo, correcciones de errores y soporte oficial para desarrolladores, consulta tu cuenta de cliente en [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nuestro equipo de soporte está disponible para ayudarte con cualquier problema técnico o pregunta relacionada con la funcionalidad del módulo.
