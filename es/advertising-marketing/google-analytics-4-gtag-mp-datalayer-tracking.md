---
title: "Google Analytics 4 - seguimiento gtag, MP y dataLayer - Manual del comerciante y guía de configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop Google Analytics 4 - seguimiento gtag, MP & dataLayer de MyPresta.eu."
sidebar:
  label: "Google Analytics 4 - seguimiento gtag, MP y dataLayer - Manual del comerciante y guía de configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Google Analytics 4 - gtag, MP & dataLayer tracking en MyPresta.eu](https://mypresta.eu/modules/advertising-and-marketing/google-analytics-4-gtag-mp-datalayer-tracking.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/advertising-marketing/google-analytics-4-gtag-mp-datalayer-tracking/)
>
> ---


# Google Analytics 4 - seguimiento gtag, MP y dataLayer

## 1. Requisitos y compatibilidad

- **Versiones de PrestaShop compatibles**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilidad con PHP**: PHP 7.1 - 8.5
- **Requisitos de alojamiento**: Se requieren extensiones PHP estándar como cURL, JSON y OpenSSL para que el módulo funcione correctamente, especialmente para el seguimiento del Measurement Protocol del lado del servidor.

## 2. Recorrido completo por la configuración (cada ajuste agrupado por pantalla)

El módulo "Google Analytics 4 - seguimiento gtag, MP y dataLayer" ofrece un conjunto completo de opciones de configuración, accesibles a través de su página de configuración principal y pantallas de administración dedicadas.

### 2.1 Página de configuración del módulo (Back Office > Módulos > Configurar)

Esta es la pantalla principal donde configurará su seguimiento de GA4. El módulo utiliza una interfaz tipo asistente para guiarle a través de la configuración inicial, pero siempre puede volver a visitar y ajustar la configuración.

#### **Asistente de configuración inicial**

Al configurar por primera vez, es probable que le reciba un asistente. Siga sus pasos para configurar rápidamente su propiedad principal de GA4.

- **Paso 1: Elegir el modo de seguimiento**

  - **Qué hace este ajuste:** Determina cómo su tienda envía datos a Google Analytics 4. Esta es una decisión crucial basada en su configuración técnica y requisitos de privacidad.
  - **Efecto de cambiar este ajuste:**
    - *`gtag.js` (Recomendado para la mayoría):* Esta es la etiqueta web estándar de Google Analytics 4. Carga una biblioteca JavaScript (`gtag.js`) directamente en las páginas de su tienda, que luego envía datos a GA4. Es fácil de implementar pero depende de la ejecución del navegador del lado del cliente y del consentimiento de cookies.
    - *`dataLayer` (Para usuarios de Google Tag Manager):* Este modo envía todos los datos de eventos de GA4 al objeto `dataLayer`, que su contenedor de Google Tag Manager (GTM) luego lee y envía a GA4. Elija esto si ya utiliza GTM para otras etiquetas y desea una gestión centralizada de etiquetas.
    - *`Measurement Protocol` (Avanzado, para máxima recuperación de datos):* Este modo envía datos directamente desde su servidor PrestaShop a Google Analytics 4, omitiendo completamente el navegador. Esto es ideal para recuperar datos cuando el seguimiento de `gtag.js` o `dataLayer` es bloqueado por bloqueadores de anuncios, configuraciones del navegador o consentimiento de cookies denegado. Es más complejo pero proporciona la recopilación de datos más robusta.
  - **Valor recomendado:** `gtag.js` por simplicidad, `dataLayer` si usa GTM, `Measurement Protocol` si la precisión de los datos es primordial y se siente cómodo con una configuración avanzada.
  - **Escenario / ejemplo de comerciante:** Si desea empezar rápidamente y no utiliza GTM, `gtag.js` es perfecto. Si tiene un equipo de marketing dedicado que gestiona GTM, `dataLayer` se integra sin problemas. Si está viendo discrepancias significativas entre sus ventas y los datos de GA4, `Measurement Protocol` puede ayudar a cerrar esa brecha.
- **Paso 2: Introduzca su(s) ID(s) de medición de GA4**

  - **Qué hace este ajuste:** Este es su identificador único para su propiedad de Google Analytics 4 (por ejemplo, `G-XXXXXXXXXX`). El módulo lo necesita para saber dónde enviar sus datos. Puede añadir múltiples ID si rastrea diferentes partes de su tienda en propiedades de GA4 separadas.
  - **Efecto de cambiar este ajuste:** Los datos se enviarán a la propiedad de GA4 especificada. ID incorrectos significan que no se envían datos o se envían al lugar equivocado.
  - **Valor recomendado:** Su ID de medición principal de GA4.
  - **Escenario / ejemplo de comerciante:** Tiene una propiedad principal de GA4 `G-ABCDEF1234`. Introduzca este ID. Si también desea enviar datos de productos específicos a una propiedad separada `G-XYZW5678`, también puede añadirla.
- **Paso 3: Configurar la gestión del consentimiento (si corresponde)**

  - **Qué hace este ajuste:** Se integra con la solución de consentimiento de cookies de su tienda para garantizar que el seguimiento de GA4 respete las elecciones de privacidad del usuario.
  - **Efecto de cambiar este ajuste:**
    - *Activado:* Las etiquetas de GA4 solo se activarán si el usuario ha otorgado su consentimiento para las cookies de análisis.
    - *Desactivado:* Las etiquetas de GA4 se activarán independientemente del consentimiento (no recomendado para el cumplimiento del GDPR/CCPA).
  - **Valor recomendado:** Activado, y asegúrese de tener un módulo de consentimiento de cookies robusto instalado y configurado.
  - **Escenario / ejemplo de comerciante:** Un cliente visita su tienda y rechaza las cookies de análisis. Con la gestión del consentimiento activada, los scripts `gtag.js` o `dataLayer` no se cargarán, lo que evitará el seguimiento del lado del cliente. Si está utilizando Measurement Protocol, aún podría enviar datos de compra anonimizados del lado del servidor.

#### **Configuración general (después del asistente)**

Una vez que el asistente haya finalizado, verá una interfaz de configuración más detallada, a menudo organizada en pestañas.

- **Gestión de ID de medición**

  - **Qué hace este ajuste:** Le permite añadir, editar o eliminar múltiples ID de medición de GA4 (`G-XXXXXXXXXX`) y asociarlos con modos de seguimiento específicos.
  - **Efecto de cambiar este ajuste:** Determina qué propiedades de GA4 reciben datos de su tienda.
  - **Valor recomendado:** Mantenga solo las propiedades de GA4 necesarias.
  - **Escenario / ejemplo de comerciante:** Ha creado una nueva propiedad de GA4 para una campaña de marketing específica. Puede añadir su ID aquí para realizar un seguimiento del rendimiento específico de la campaña.
- **Dominios de enlace (para seguimiento entre dominios)**

  - **Qué hace este ajuste:** Si su tienda opera en varios dominios (por ejemplo, `shop.example.com` y `blog.example.com`), este ajuste ayuda a Google Analytics a comprender que forman parte del mismo recorrido del usuario, evitando que se inicien nuevas sesiones cuando un usuario navega entre ellos.
  - **Efecto de cambiar este ajuste:** Garantiza un seguimiento preciso del recorrido del usuario en dominios relacionados. Sin él, los usuarios que se mueven entre sus dominios podrían contarse como nuevos usuarios o nuevas sesiones.
  - **Valor recomendado:** Añada todos los dominios relacionados que un usuario podría visitar como parte de su recorrido en su sitio.
  - **Escenario / ejemplo de comerciante:** Su tienda principal es `mistore.com` y su blog es `blog.mistore.com`. Añada `blog.mistore.com` a la lista de dominios de enlace.
- **Modo de depuración**

  - **Qué hace este ajuste:** Activa una vista de depuración especial en el front office y envía eventos de depuración a GA4, lo que le permite verificar que su seguimiento funciona correctamente.
  - **Efecto de cambiar este ajuste:**
    - *Activado:* Aparece un pequeño panel de depuración en el front office de su tienda, mostrando qué eventos de GA4 se están enviando. Los eventos también aparecen en la Vista de depuración de GA4.
    - *Desactivado:* No hay panel de depuración, seguimiento normal.
  - **Valor recomendado:** Active solo durante las pruebas y la resolución de problemas. Desactive para tiendas de producción en vivo.
  - **Escenario / ejemplo de comerciante:** Acaba de instalar el módulo y desea confirmar que los eventos `add_to_cart` se están activando correctamente. Active el modo de depuración, añada un producto a su carrito y compruebe el panel de depuración y la Vista de depuración de GA4.
- **Asesor de calidad de datos**

  - **Qué hace este ajuste:** Proporciona información y recomendaciones para mejorar la calidad y la integridad de sus datos de GA4. Comprueba problemas comunes como la falta de ID de producto, formatos de moneda incorrectos, etc.
  - **Efecto de cambiar este ajuste:** Esta es una herramienta de diagnóstico; no cambia directamente el comportamiento del front office, pero le ayuda a identificar y solucionar problemas que podrían conducir a análisis inexactos.
  - **Valor recomendado:** Revise regularmente las recomendaciones.
  - **Escenario / ejemplo de comerciante:** El asesor podría indicarle que a algunos productos les faltan códigos EAN/UPC, que son valiosos para los datos de productos de GA4. Luego puede actualizar su catálogo de productos.
- **Doctor del catálogo**

  - **Qué hace este ajuste:** Analiza su catálogo de productos en busca de posibles problemas que podrían afectar el seguimiento de GA4, como productos sin precios, imágenes o categorías válidas.
  - **Efecto de cambiar este ajuste:** Similar al Asesor de calidad de datos, esta es una herramienta de diagnóstico para garantizar que los datos de su producto sean robustos para GA4.
  - **Valor recomendado:** Ejecute esta comprobación periódicamente.
  - **Escenario / ejemplo de comerciante:** El doctor podría marcar productos que están agotados pero aún visibles, lo que podría confundir el seguimiento de GA4 de las vistas de productos.
- **Estadísticas en vivo**

  - **Qué hace este ajuste:** Muestra datos de eventos en tiempo real que se envían desde su tienda a GA4, directamente dentro del back office de PrestaShop.
  - **Efecto de cambiar este ajuste:** Proporciona una visión general inmediata de las interacciones y eventos recientes del usuario.
  - **Valor recomendado:** Útil para la monitorización, especialmente después de realizar cambios o durante picos de tráfico.
  - **Escenario / ejemplo de comerciante:** Acaba de lanzar un nuevo producto. Puede ver las estadísticas en vivo para ver los eventos `view_item` y `add_to_cart` en tiempo real.
- **Mapeo y personalización de eventos**

  - **Qué hace este ajuste:** Le permite personalizar cómo las acciones de PrestaShop se asignan a los eventos de GA4 y sus parámetros. Por ejemplo, es posible que desee enviar un parámetro personalizado con el evento `purchase`.
  - **Efecto de cambiar este ajuste:** Ajusta los datos enviados a GA4, lo que permite informes más específicos y la creación de audiencias.
  - **Valor recomendado:** Modifique solo si tiene necesidades específicas de informes de GA4.
  - **Escenario / ejemplo de comerciante:** Desea incluir un parámetro personalizado `loyalty_program_status` con cada evento `purchase`. Puede configurar este mapeo aquí.
- **Reglas de múltiples propiedades**

  - **Qué hace este ajuste:** Define reglas para enviar eventos o datos específicos a diferentes propiedades de GA4. Por ejemplo, podría enviar todos los eventos a su propiedad principal, pero solo los eventos de "compra" para una categoría específica a una propiedad separada.
  - **Efecto de cambiar este ajuste:** Permite una segmentación avanzada de sus datos analíticos en múltiples propiedades de GA4.
  - **Valor recomendado:** Utilice si tiene requisitos de seguimiento complejos que involucren múltiples propiedades de GA4.
  - **Escenario / ejemplo de comerciante:** Tiene una propiedad principal de GA4 para toda su tienda, pero también tiene una propiedad separada para su línea de "Productos Premium". Puede establecer una regla para enviar eventos `purchase` para productos de la categoría "Productos Premium" a ambas propiedades.

### 2.2 Pantallas de administración dedicadas y vistas de controlador

El módulo también proporciona pantallas dedicadas para una gestión y diagnóstico más avanzados.

#### **AdminMyanalyticsAjaxController (Back Office > Módulos > Google Analytics 4 > [Varias pestañas])**

Este controlador gestiona muchos de los elementos interactivos y las visualizaciones de datos dentro de la configuración del módulo, especialmente para las herramientas de diagnóstico y las estadísticas en vivo. No navegará directamente a este controlador; alimenta el contenido dinámico de la página de configuración principal.

- **Nombre de la pantalla y ubicación del menú:** Este controlador no es un elemento de menú independiente. Sirve las solicitudes AJAX para las diversas pestañas y secciones dentro de la página de configuración principal del módulo (por ejemplo, "Asesor de calidad de datos", "Doctor del catálogo", "Estadísticas en vivo").
- **Acciones y configuraciones disponibles:**
  - **Cuadrícula del Asesor de calidad de datos:** Muestra una tabla de problemas de calidad de datos detectados, a menudo con sugerencias de resolución.
  - **Informe del Doctor del catálogo:** Muestra un informe sobre la integridad de los datos del producto.
  - **Flujo de eventos en vivo:** Una fuente en tiempo real de eventos que se envían a GA4.
  - **Pasos del asistente:** Gestiona la progresión y el envío de datos para el asistente de configuración inicial.
- **Efecto de los cambios:** La interacción con estos elementos (por ejemplo, hacer clic en "Ejecutar comprobación" para el Asesor de calidad de datos) activa procesos en segundo plano que analizan los datos de su tienda y actualizan la información mostrada. Le ayuda a diagnosticar y solucionar problemas, pero no cambia directamente el comportamiento del front office.
- **Flujo de trabajo recomendado para la gestión diaria de la tienda:** Revise regularmente las pestañas "Asesor de calidad de datos" y "Doctor del catálogo" para asegurarse de que sus datos de GA4 sigan siendo precisos. Supervise las "Estadísticas en vivo" durante períodos críticos o después de cambios importantes en la tienda.

#### **index.php (Back Office > Módulos > Google Analytics 4)**

Este es el punto de entrada principal para la configuración del módulo en el back office. Aunque se llama `index.php`, es el núcleo del método `getContent()` que renderiza toda la interfaz de configuración, incluidas todas las pestañas y configuraciones descritas en la sección 4.1.

- **Nombre de la pantalla y ubicación del menú:** **Módulos > Gestor de módulos > Google Analytics 4 - seguimiento gtag, MP y dataLayer > Configurar**.
- **Acciones y configuraciones disponibles:** Todas las configuraciones, pestañas y pasos del asistente mencionados en la sección 4.1 se renderizan y gestionan a través de esta vista de configuración principal.
- **Efecto de los cambios:** Cualquier cambio guardado en esta pantalla afecta directamente a cómo se implementa su seguimiento de GA4 y qué datos se envían a Google Analytics.
- **Flujo de trabajo recomendado para la gestión diaria de la tienda:** Aquí es donde configurará inicialmente el módulo y volverá para cualquier cambio importante en sus propiedades de GA4, modos de seguimiento o reglas avanzadas.

### 2.3 Tabla de referencia rápida de configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e impacto |
| --- | --- | --- | --- |
| Configuración principal | **Modo de seguimiento** | `gtag.js` | Define cómo se envían los datos (lado del cliente, GTM o lado del servidor). Crucial para la precisión de los datos y la privacidad. |
| Configuración principal | **ID(s) de medición** | Su ID de GA4 (`G-XXXXXXXXXX`) | Especifica qué propiedad de GA4 recibe datos. Los ID incorrectos significan que no hay datos. |
| Configuración principal | **Gestión del consentimiento** | Activado (si se utiliza el módulo de consentimiento) | Garantiza que el seguimiento de GA4 respete las elecciones de privacidad del usuario. |
| Configuración principal | **Dominios de enlace** | Vacío (añadir si es entre dominios) | Permite un seguimiento preciso del usuario en múltiples dominios relacionados. |
| Configuración principal | **Modo de depuración** | Desactivado (activar para pruebas) | Muestra un panel de depuración en el front office y envía eventos de depuración a GA4. |
| Configuración principal | **Asesor de calidad de datos** | N/A (herramienta de diagnóstico) | Identifica y sugiere soluciones para problemas de calidad de datos de GA4. |
| Configuración principal | **Doctor del catálogo** | N/A (herramienta de diagnóstico) | Analiza el catálogo de productos para la preparación del seguimiento de GA4. |
| Configuración principal | **Estadísticas en vivo** | N/A (herramienta de monitorización) | Muestra eventos de GA4 en tiempo real en el back office. |
| Configuración principal | **Mapeo de eventos** | Predeterminado (modificar para necesidades personalizadas) | Personaliza cómo las acciones de PrestaShop se asignan a los eventos y parámetros de GA4. |
| Configuración principal | **Reglas de múltiples propiedades** | Ninguna (añadir para seguimiento avanzado) | Define reglas para enviar datos específicos a diferentes propiedades de GA4. |
| AdminMyanalyticsAjaxController | (Varias vistas impulsadas por AJAX) | N/A | Impulsa el contenido dinámico para herramientas de diagnóstico y estadísticas en vivo. |
| index.php | (Página de configuración principal) | N/A | Renderiza toda la interfaz de configuración del módulo. |

## 3. Solución de problemas del comerciante y preguntas frecuentes (FAQ)

**P1: He instalado el módulo, pero no veo ningún dato en mi propiedad de Google Analytics 4.**

- **R:** Primero, asegúrese de haber introducido el ID de medición de GA4 correcto (que comienza con `G-`) en la configuración del módulo.
- **R:** Compruebe la "Vista de depuración" de su propiedad de GA4 (en Google Analytics, vaya a Administrar > Vista de depuración) mientras navega por su tienda. Si ve eventos allí, se están enviando datos.
- **R:** Borre la caché de Smarty de PrestaShop (Parámetros avanzados > Rendimiento > Borrar caché).
- **R:** Si está utilizando `gtag.js` o `dataLayer`, compruebe la consola de desarrollador de su navegador (F12) en busca de errores de JavaScript. Además, asegúrese de haber aceptado las cookies de análisis si tiene un módulo de consentimiento.
- **R:** Si utiliza Measurement Protocol, asegúrese de que su servidor tenga `cURL` habilitado y de que no haya reglas de firewall que bloqueen las conexiones salientes a los servidores de Google.

**P2: Mis datos de compra de GA4 no coinciden con los datos de pedidos de PrestaShop.**

- **R:** Este es un problema común, a menudo debido a bloqueadores de anuncios, configuraciones de privacidad del navegador o usuarios que deniegan el consentimiento de cookies.
- **R:** **Considere seriamente habilitar el Measurement Protocol para los eventos de compra.** Esto envía los datos de compra directamente desde su servidor, evitando los problemas del navegador del lado del cliente.
- **R:** Utilice el "Asesor de calidad de datos" y el "Doctor del catálogo" del módulo para identificar cualquier inconsistencia de datos que pueda estar causando problemas.
- **R:** Asegúrese de que los clientes siempre lleguen a su página de confirmación de pedido después de una compra exitosa. Si los clientes son redirigidos a otro lugar o cierran el navegador demasiado pronto, es posible que los eventos de compra del lado del cliente no se activen.

**P3: El panel de depuración del módulo no aparece, o no veo eventos en la Vista de depuración de GA4.**

- **R:** Asegúrese de que el "Modo de depuración" esté explícitamente habilitado en la configuración del módulo.
- **R:** Borre la caché de su navegador y la caché de Smarty de PrestaShop.
- **R:** Asegúrese de haber iniciado sesión como administrador en el back office de PrestaShop y de estar navegando por el front office en la misma sesión del navegador.
- **R:** Compruebe la consola de desarrollador de su navegador en busca de errores de JavaScript que puedan impedir que se cargue el panel de depuración.

**P4: ¿Cómo me aseguro de que el módulo respete mi módulo de consentimiento de cookies?**

- **R:** El módulo está diseñado para integrarse con los mecanismos estándar de consentimiento de cookies. En la configuración del módulo, debería haber una opción para "Gestión del consentimiento". Asegúrese de que esté habilitada.
- **R:** Verifique que su módulo de consentimiento de cookies esté categorizando correctamente las cookies de análisis y que las elecciones de los usuarios se almacenen y respeten. El módulo de GA4 solo cargará las etiquetas del lado del cliente (`gtag.js`, `dataLayer`) si se otorga el consentimiento.
- **R:** Para una máxima recuperación de datos, considere usar el Measurement Protocol para eventos críticos como `purchase`, ya que a menudo puede evitar problemas de consentimiento del lado del cliente (aunque aún debe informar a los usuarios sobre el procesamiento de datos).

**P5: Quiero rastrear eventos o parámetros personalizados no cubiertos por la configuración predeterminada.**

- **R:** El módulo incluye una sección de "Mapeo y personalización de eventos". Aquí, puede definir cómo las acciones de PrestaShop se asignan a los eventos de GA4 y añadir parámetros personalizados.
- **R:** Para un seguimiento personalizado muy complejo, especialmente con `dataLayer`, es posible que deba combinar las capacidades de este módulo con scripts personalizados en su contenedor de Google Tag Manager.

## 4. Guía para desarrolladores y webmasters (arquitectura técnica y mapa de código)

Esta sección es estrictamente para desarrolladores, webmasters de tiendas y agencias técnicas que mantienen o extienden la tienda.

### 4.1 Resumen de la arquitectura

El módulo `myanalytics` para PrestaShop está diseñado para proporcionar una integración robusta y flexible con Google Analytics 4. Sigue un enfoque modular y orientado a objetos, aprovechando el patrón MVC de PrestaShop y el sistema de hooks.

Componentes arquitectónicos clave:

- **Clase principal del módulo (`Myanalytics`):** Gestiona la instalación, desinstalación, registro de hooks y el método `getContent()` principal para la configuración del back office.
- **Fábrica de rastreadores (`MyanalyticsTrackerFactory`):** Instancia dinámicamente el mecanismo de seguimiento apropiado (`gtag.js`, `dataLayer` o `Measurement Protocol`) basándose en la configuración del módulo.
- **Clases de rastreadores dedicadas:** Cada método de seguimiento (`MyanalyticsGtagTracker`, `MyanalyticsDataLayerTracker`, `MyanalyticsMpTracker`) implementa `MyanalyticsTrackerInterface` y encapsula la lógica para enviar eventos de GA4 a través de su método específico.
- **Mapeo de eventos y gestión de la capa de datos:** Clases como `MyanalyticsEvents` y `MyanalyticsDataLayerTracker` son responsables de traducir las acciones de PrestaShop (por ejemplo, vista de producto, añadir al carrito) en nombres de eventos y parámetros compatibles con GA4.
- **Herramientas de diagnóstico:** Clases como `MyanalyticsDataQualityCoach`, `MyanalyticsCatalogDoctor` y `MyanalyticsHealthScore` proporcionan información en el back office sobre la integridad de los datos y el estado del seguimiento.
- **Controladores de administración:** Gestionan las solicitudes AJAX para contenido dinámico en el back office (por ejemplo, estadísticas en vivo, informes de diagnóstico).
- **Controladores frontales:** Se utilizan principalmente para puntos finales AJAX, especialmente para el fallback del Measurement Protocol o acciones relacionadas con el consentimiento.
- **Plantillas Smarty:** Se utilizan para renderizar tanto las vistas de configuración del back office como los scripts de seguimiento del front office inyectados a través de hooks.

### 4.2 Controladores (`controllers/`)

#### Controladores del Front Office

- `controllers/front/ajax.php`
  - **Nombre de la clase y clase padre:** `MyanalyticsAjaxModuleFrontController` extiende `ModuleFrontController`.
  - **Responsabilidad:** Gestiona las solicitudes AJAX del front office. Esto podría incluir el envío de eventos del Measurement Protocol en escenarios específicos (por ejemplo, cuando el seguimiento del lado del cliente está bloqueado), la actualización del estado del consentimiento u otras interacciones dinámicas que no requieren una recarga completa de la página. Normalmente devuelve respuestas JSON.
- `controllers/front/index.php`
  - **Nombre de la clase y clase padre:** `MyanalyticsIndexModuleFrontController` extiende `ModuleFrontController`.
  - **Responsabilidad:** Este controlador podría servir como un fallback o un punto final específico para ciertas funcionalidades del módulo, aunque a menudo la clase principal del módulo gestiona la mayoría de la inyección de scripts del front office a través de hooks. Podría usarse para redirecciones específicas o procesamiento de datos si fuera necesario.

#### Controladores de administración del Back Office

- `controllers/admin/AdminMyanalyticsAjaxController.php`
  - **Nombre de la clase y clase padre:** `AdminMyanalyticsAjaxController` extiende `AdminController`.
  - **Nombre de la pestaña y entidad gestionada:** Este controlador no es directamente accesible como una pestaña de menú. Sirve las solicitudes AJAX de la página de configuración principal del módulo (`getContent()`). Gestiona las actualizaciones dinámicas para secciones como el Asesor de calidad de datos, el Doctor del catálogo, las Estadísticas en vivo y los pasos del asistente de configuración.
  - **Responsabilidad:** Procesa solicitudes de informes de diagnóstico, datos de eventos en vivo y envíos de pasos del asistente, devolviendo datos JSON para actualizar la interfaz de usuario del back office.
- `controllers/admin/index.php`
  - **Nombre de la clase y clase padre:** `AdminMyanalyticsIndexController` extiende `AdminController`.
  - **Nombre de la pestaña y entidad gestionada:** Similar a `AdminMyanalyticsAjaxController`, este es probablemente un controlador interno o un marcador de posición. La configuración principal del back office se gestiona mediante el método `getContent()` de la clase principal del módulo `Myanalytics`.

### 4.3 Clases y modelos principales (`classes/`)

- `classes/autoload.php`: Archivo de carga automática estándar de PrestaShop para clases de módulos.
- `classes/index.php`: Archivo vacío, práctica común para evitar la lista de directorios.
- `classes/MyanalyticsCatalogDoctor.php`
  - **Qué hace:** Analiza el catálogo de productos de PrestaShop en busca de problemas de calidad de datos relevantes para el seguimiento de GA4 (por ejemplo, precios faltantes, imágenes, categorías no válidas).
  - **Métodos públicos clave:** Métodos para ejecutar comprobaciones y recuperar informes sobre el estado del catálogo.
- `classes/MyanalyticsConsent.php`
  - **Qué hace:** Gestiona e interactúa con los mecanismos de consentimiento de cookies, determinando si el seguimiento analítico está permitido según las elecciones del usuario.
  - **Métodos públicos clave:** Métodos para verificar el estado del consentimiento, establecer el consentimiento y, potencialmente, integrarse con módulos de consentimiento de terceros.
- `classes/MyanalyticsCurrencyHelper.php`
  - **Qué hace:** Proporciona funciones de utilidad para manejar el formato y la conversión de moneda, asegurando que GA4 reciba los datos de moneda en el formato correcto.
- `classes/MyanalyticsDataLayerTracker.php`
  - **Qué hace:** Implementa `MyanalyticsTrackerInterface` para el seguimiento de `dataLayer`. Envía datos de eventos de GA4 a la matriz `dataLayer` de JavaScript, poniéndolos a disposición de Google Tag Manager.
  - **Métodos públicos clave:** Métodos para añadir eventos a la dataLayer, manejar eventos específicos de comercio electrónico (por ejemplo, `add_to_cart`, `purchase`).
- `classes/MyanalyticsDataQualityCoach.php`
  - **Qué hace:** Proporciona una herramienta de diagnóstico para identificar e informar sobre posibles problemas de calidad de datos en el flujo de eventos de GA4 o en la configuración.
  - **Métodos públicos clave:** Métodos para ejecutar comprobaciones de calidad de datos y generar informes.
- `classes/MyanalyticsEventId.php`
  - **Qué hace:** Probablemente una clase de utilidad para generar ID de eventos únicos, lo que puede ser útil para la deduplicación en GA4, especialmente con Measurement Protocol.
- `classes/MyanalyticsEventMap.php`
  - **Qué hace:** Define el mapeo entre las acciones/datos de PrestaShop y los nombres y parámetros de eventos estándar de GA4.
  - **Métodos públicos clave:** Métodos para recuperar definiciones de eventos y mapeos de parámetros.
- `classes/MyanalyticsEvents.php`
  - **Qué hace:** Una clase central para activar y gestionar eventos de GA4 dentro del módulo. Orquesta qué rastreador (gtag, datalayer, MP) debe manejar qué evento.
  - **Métodos públicos clave:** Métodos como `trackPageView()`, `trackAddToCart()`, `trackPurchase()`, etc.
- `classes/MyanalyticsGtagTracker.php`
  - **Qué hace:** Implementa `MyanalyticsTrackerInterface` para el seguimiento de `gtag.js`. Genera e inyecta el código JavaScript necesario para enviar eventos directamente a GA4 a través de `gtag()`.
  - **Métodos públicos clave:** Métodos para generar llamadas `gtag()` para varios eventos de GA4.
- `classes/MyanalyticsHealthScore.php`
  - **Qué hace:** Calcula y muestra una "puntuación de salud" para la integración de GA4, basada en varias comprobaciones y mejores prácticas.
- `classes/MyanalyticsLiveStats.php`
  - **Qué hace:** Recopila y proporciona estadísticas en tiempo real sobre los eventos que se envían a GA4, mostradas en el back office.
- `classes/MyanalyticsMpClient.php`
  - **Qué hace:** Gestiona las solicitudes HTTP reales para enviar datos a Google Analytics 4 a través del Measurement Protocol.
  - **Métodos públicos clave:** Métodos para construir y enviar cargas útiles del Measurement Protocol.
- `classes/MyanalyticsMpTracker.php`
  - **Qué hace:** Implementa `MyanalyticsTrackerInterface` para el seguimiento del `Measurement Protocol`. Prepara los datos del evento y utiliza `MyanalyticsMpClient` para enviarlos del lado del servidor.
  - **Métodos públicos clave:** Métodos para formatear y enviar eventos del lado del servidor.
- `classes/MyanalyticsProductIdResolver.php`
  - **Qué hace:** Resuelve varios identificadores de producto (ID, referencia, EAN, UPC) para garantizar que se envíen datos de producto consistentes a GA4.
- `classes/MyanalyticsPropertyRules.php`
  - **Qué hace:** Gestiona la lógica para el seguimiento de múltiples propiedades, definiendo reglas para qué eventos van a qué propiedades de GA4.
- `classes/MyanalyticsTrackerFactory.php`
  - **Qué hace:** Una clase de patrón de fábrica responsable de crear y devolver la implementación correcta de `MyanalyticsTrackerInterface` basada en la configuración del módulo (gtag, datalayer o MP).
- `classes/MyanalyticsTrackerInterface.php`
  - **Qué hace:** Define la interfaz común que todas las clases de rastreadores de GA4 deben implementar, asegurando la coherencia en cómo se manejan los eventos.
- `classes/MyanalyticsUserData.php`
  - **Qué hace:** Recopila y formatea datos específicos del usuario (por ejemplo, ID de usuario, datos demográficos) para el seguimiento de GA4, respetando la configuración de privacidad.

### 4.4 Activos JavaScript (`views/js/`)

- `myanalytics/views/js/myanalytics-admin.js`
  - **Alcance:** Back office.
  - **Qué hace:** Proporciona funcionalidad interactiva para las páginas de configuración del back office del módulo. Esto incluye la gestión de envíos de formularios, llamadas AJAX para herramientas de diagnóstico (Asesor de calidad de datos, Doctor del catálogo), la actualización de estadísticas en vivo y la gestión de reglas de múltiples propiedades.
- `myanalytics/views/js/myanalytics-debug.js`
  - **Alcance:** Front office (cuando el modo de depuración está habilitado).
  - **Qué hace:** Inyecta un panel de depuración en el front office, mostrando los eventos de GA4 a medida que se activan. Escucha las llamadas `gtag()` o los eventos `dataLayer.push()` y los renderiza para una fácil verificación.
- `myanalytics/views/js/myanalytics-ghost.js`
  - **Alcance:** Front office.
  - **Qué hace:** Este script podría estar relacionado con el seguimiento "fantasma" o "sombra", potencialmente para el fallback del Measurement Protocol o para capturar eventos que de otro modo podrían perderse. Podría implicar escuchar eventos DOM específicos y activar llamadas del lado del servidor.
- `myanalytics/views/js/myanalytics-live.js`
  - **Alcance:** Back office.
  - **Qué hace:** Impulsa la función "Estadísticas en vivo" en el back office. Probablemente utiliza AJAX para obtener periódicamente eventos recientes de GA4 del servidor y actualiza la pantalla en tiempo real.
- `myanalytics/views/js/myanalytics-wizard.js`
  - **Alcance:** Back office.
  - **Qué hace:** Proporciona la lógica interactiva para el asistente de configuración del módulo, guiando al usuario a través de los pasos de configuración inicial, validando entradas y enviando datos a través de AJAX.
- `myanalytics/views/js/myanalytics.js`
  - **Alcance:** Front office.
  - **Qué hace:** El archivo JavaScript principal del front office. Gestiona la lógica central de seguimiento de GA4 del lado del cliente, incluyendo:
    - Inicialización de `gtag.js` o `dataLayer`.
    - Escucha de eventos DOM (por ejemplo, clics en botones "Añadir al carrito", vistas de imágenes de productos).
    - Recopilación de datos relevantes de productos y usuarios.
    - Envío de eventos a `dataLayer` o llamadas a comandos `gtag()`.
    - Potencialmente, gestión de la integración del consentimiento de cookies.

### 4.5 Hojas de estilo CSS (`views/css/`)

- `myanalytics/views/css/myanalytics-admin.css`
  - **Alcance:** Estilo del formulario de administración del back office.
  - **Qué hace:** Estiliza la página de configuración del módulo, incluyendo pestañas, campos de entrada, botones, informes de diagnóstico y pantallas de estadísticas en vivo, asegurando una interfaz consistente y fácil de usar dentro del back office de PrestaShop.
- `myanalytics/views/css/myanalytics-debug.css`
  - **Alcance:** Estilo del cliente del front office (cuando el modo de depuración está habilitado).
  - **Qué hace:** Estiliza el panel de depuración del front office, haciéndolo visualmente distinto y legible para desarrolladores y administradores.

### 4.6 Estructura de plantillas Smarty (`views/templates/`)

#### Plantillas de hook (`views/templates/hook/`)

- `myanalytics/views/templates/hook/debug.tpl`
  - **Hook:** Probablemente inyectado a través de `displayHeader` o `displayFooter` condicionalmente cuando el modo de depuración está activo.
  - **Salidas:** La estructura HTML para el panel de depuración del front office.
- `myanalytics/views/templates/hook/displayOrderConfirmation.tpl`
  - **Hook:** `displayOrderConfirmation`.
  - **Salidas:** El código JavaScript necesario o las inserciones de `dataLayer` para el evento `purchase`, que normalmente incluyen detalles de la transacción, información del producto y, potencialmente, parámetros del Measurement Protocol.
- `myanalytics/views/templates/hook/ghost.tpl`
  - **Hook:** Podría ser `displayHeader` o `displayFooter`.
  - **Salidas:** Código JavaScript relacionado con el seguimiento "fantasma", potencialmente para el fallback del Measurement Protocol o la captura avanzada de eventos.
- `myanalytics/views/templates/hook/header.tpl`
  - **Hook:** `displayHeader`.
  - **Salidas:** El script de inicialización principal de `gtag.js` o `dataLayer`, incluyendo los ID de medición de GA4 y cualquier configuración global. Esto es crucial para el seguimiento inicial de la vista de página.
- `myanalytics/views/templates/hook/mp-pageview.tpl`
  - **Hook:** Probablemente `displayHeader` o `displayFooter` (condicionalmente para el Measurement Protocol).
  - **Salidas:** Código renderizado del lado del servidor para enviar un evento `page_view` a través del Measurement Protocol, especialmente útil cuando el seguimiento del lado del cliente está bloqueado o se deniega el consentimiento.
- `myanalytics/views/templates/hook/payment.tpl`
  - **Hook:** `displayPaymentTop` o hooks similares relacionados con el pago.
  - **Salidas:** Inserciones de JavaScript o `dataLayer` para eventos `add_payment_info` o `begin_checkout`, capturando la selección del método de pago.
- `myanalytics/views/templates/hook/product-details.tpl`
  - **Hook:** `displayProductButtons`, `displayProductExtraContent` o hooks similares de la página de producto.
  - **Salidas:** Inserciones de JavaScript o `dataLayer` para eventos `view_item` y `add_to_cart`, incluyendo información detallada del producto.

#### Plantillas de administración (`views/templates/admin/`)

- `myanalytics/views/templates/admin/doctor.tpl`: Renderiza la interfaz para el Doctor del Catálogo, mostrando informes y recomendaciones.
- `myanalytics/views/templates/admin/dq.tpl`: Renderiza la interfaz para el Asesor de Calidad de Datos, mostrando problemas de calidad de datos.
- `myanalytics/views/templates/admin/health.tpl`: Muestra la puntuación de salud general y las métricas relacionadas para la integración de GA4.
- `myanalytics/views/templates/admin/linker-domains.tpl`: Renderiza el campo de entrada y la lista para gestionar los dominios de enlace entre dominios.
- `myanalytics/views/templates/admin/live-maintain.tpl`: Probablemente una subplantilla para las estadísticas en vivo, posiblemente para mensajes o controles de mantenimiento.
- `myanalytics/views/templates/admin/live.tpl`: Renderiza la interfaz principal para la función de Estadísticas en Vivo, mostrando datos de eventos en tiempo real.
- `myanalytics/views/templates/admin/measurement-ids.tpl`: Renderiza la sección para gestionar múltiples ID de medición de GA4.
- `myanalytics/views/templates/admin/mode-context.tpl`: Proporciona información contextual o explicaciones para el modo de seguimiento elegido.
- `myanalytics/views/templates/admin/mode-note-datalayer.tpl`: Notas o instrucciones específicas para el modo de seguimiento `dataLayer`.
- `myanalytics/views/templates/admin/mode-note-gtag.tpl`: Notas o instrucciones específicas para el modo de seguimiento `gtag.js`.
- `myanalytics/views/templates/admin/mode-note-mp.tpl`: Notas o instrucciones específicas para el modo de seguimiento `Measurement Protocol`.
- `myanalytics/views/templates/admin/mode-picker.tpl`: Renderiza los botones de radio o el desplegable para seleccionar el modo de seguimiento de GA4.
- `myanalytics/views/templates/admin/properties-list.tpl`: Muestra una lista de propiedades de GA4 configuradas.
- `myanalytics/views/templates/admin/recent-events.tpl`: Una subplantilla para mostrar una lista de eventos recientes, a menudo utilizada en estadísticas en vivo o vistas de depuración.
- `myanalytics/views/templates/admin/tabs.tpl`: Renderiza la estructura de navegación por pestañas para la página de configuración del módulo.
- `myanalytics/views/templates/admin/tag-chips.tpl`: Muestra "chips" o etiquetas visuales para las etiquetas/propiedades de GA4 configuradas.
- `myanalytics/views/templates/admin/wizard.tpl`: Renderiza la estructura general y los pasos del asistente de configuración del módulo.

#### Plantillas del Front Office (`views/templates/front/`)

El módulo no parece tener plantillas de página de front office independientes dedicadas, sino que se basa en la inyección de scripts y datos a través de hooks.

### 4.7 Esquema de la base de datos y mapa de hooks

- **Tablas de la base de datos**:

  - El módulo almacena principalmente su configuración en la tabla `ps_configuration` de PrestaShop.
  - También podría crear tablas personalizadas para:
    - `ps_myanalytics_events`: Para registrar eventos del Measurement Protocol u otros datos de eventos internos para depuración/estadísticas en vivo.
    - `ps_myanalytics_properties`: Para almacenar detalles sobre múltiples propiedades de GA4 y sus reglas asociadas.
    - `ps_myanalytics_consent`: Para almacenar el estado del consentimiento o integrarse con módulos de consentimiento.
    - `ps_myanalytics_health_log`: Para almacenar los resultados de las comprobaciones de estado y los informes de calidad de datos.
- **Tabla de hooks registrados**:

| Nombre del Hook | Momento de ejecución | Propósito técnico |
| --- | --- | --- |
| `displayHeader` | En la sección `<head>` de cada página. | Inyectar scripts de inicialización de `gtag.js` o `dataLayer`, configuración global de GA4 y, potencialmente, eventos `page_view`. |
| `displayFooter` | Antes de la etiqueta de cierre `</body>` de cada página. | Inyectar scripts de seguimiento adicionales, paneles de depuración o llamadas de fallback del Measurement Protocol. |
| `displayOrderConfirmation` | En la página de confirmación del pedido después de una compra exitosa. | Enviar el evento crucial `purchase` a GA4, incluyendo detalles de la transacción y datos del producto. Aquí es donde a menudo se aprovecha el Measurement Protocol. |
| `displayProductButtons` | Cerca de los botones de acción del producto (por ejemplo, "Añadir al carrito") en la página del producto. | Inyectar JavaScript para capturar eventos `add_to_cart`. |
| `displayProductExtraContent` | En la sección de contenido extra de la página del producto. | Inyectar JavaScript para eventos `view_item` u otras interacciones de detalles del producto. |
| `displayPaymentTop` | Antes de las opciones de pago en la página de pago. | Capturar eventos `begin_checkout` y `add_payment_info`. |
| `actionFrontControllerSetMedia` | Cuando un controlador frontal está configurando sus activos multimedia. | Poner en cola archivos JS/CSS específicos del módulo para el front office. |
| `actionAdminControllerSetMedia` | Cuando un controlador de administración está configurando sus activos multimedia. | Poner en cola archivos JS/CSS específicos del módulo para el back office. |
| `actionValidateOrder` | Después de que un pedido ha sido validado con éxito. | Activar eventos `purchase` del Measurement Protocol del lado del servidor, asegurando la captura de datos incluso si falla el lado del cliente. |
| `actionObjectProductAddAfter` | Después de añadir un nuevo producto. | Potencialmente activar comprobaciones del doctor del catálogo o actualizar cachés internos de datos de productos. |
| `actionObjectProductUpdateAfter` | Después de actualizar un producto existente. | Similar a `actionObjectProductAddAfter`. |
| `actionObjectProductDeleteAfter` | Después de eliminar un producto. | Limpiar cualquier dato de seguimiento o cachés asociados. |

## 5. Soporte oficial y actualizaciones

Para obtener actualizaciones oficiales, soporte técnico y para asegurarse de que está ejecutando la última versión más compatible del módulo "Google Analytics 4 - seguimiento gtag, MP y dataLayer", consulte su cuenta de cliente en [MyPresta.eu](https://mypresta.eu/).

MyPresta.eu proporciona soporte dedicado para todos sus módulos, asegurando que la integración de análisis de su tienda permanezca robusta y actualizada con los últimos estándares de GA4 y versiones de PrestaShop.
