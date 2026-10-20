---
title: "Píxel de TikTok / API de Eventos - Manual del Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop Píxel de TikTok / API de Eventos de MyPresta.eu."
sidebar:
  label: "Píxel de TikTok / API de Eventos - Manual del Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo TikTok Pixel / Events API en MyPresta.eu](https://mypresta.eu/modules/social-networks/tiktok-pixel-events-api.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/social-networks/tiktok-pixel-events-api/)
>
> ---


# Píxel de TikTok / API de Eventos

## 1. Requisitos y Compatibilidad

- **Versiones de PrestaShop Compatibles**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilidad con PHP**: PHP 7.1 - 8.5
- **Requisitos de Alojamiento**: Se requieren extensiones PHP estándar (cURL, JSON, OpenSSL) para que el módulo funcione correctamente, especialmente para la API de Eventos (seguimiento del lado del servidor). Estas suelen estar disponibles en la mayoría de los entornos de alojamiento modernos.

## 2. Recorrido Completo por la Configuración (Cada Ajuste Agrupado por Pantalla)

### 2.1 Página de Configuración del Módulo (Back Office > Módulos > Configurar)

Esta es el área de configuración principal donde configurarás tu Píxel de TikTok y la API de Eventos. Los ajustes están diseñados para ser intuitivos, guiándote a través del proceso de conexión de tu tienda a TikTok Ads.

#### **Configuración General**

- **ID del Píxel de TikTok:**

  - **Qué hace este ajuste:** Este es tu identificador único proporcionado por el Administrador de Anuncios de TikTok. Le dice a TikTok a qué cuenta publicitaria pertenecen los datos de tu sitio web.
  - **Efecto de cambiar este ajuste:**
    - *Cuando se introduce:* El módulo comenzará a enviar datos a tu Píxel de TikTok especificado.
    - *Cuando se deja vacío:* No se enviarán datos a TikTok a través del Píxel, y el módulo no funcionará para el seguimiento del lado del navegador.
  - **Valor recomendado:** Tu ID de Píxel de TikTok válido.
  - **Escenario / ejemplo del comerciante:** Creas una cuenta de TikTok Ad y configuras un Píxel. TikTok te proporciona un ID numérico (por ejemplo, `1234567890`). Introduces este ID aquí para vincular tu tienda a tu cuenta de TikTok.
- **Token de Acceso de TikTok (para la API de Eventos):**

  - **Qué hace este ajuste:** Este es un token seguro generado en tu Administrador de Anuncios de TikTok que autoriza a tu tienda PrestaShop a enviar datos directamente a los servidores de TikTok a través de la API de Eventos. Es crucial para el seguimiento del lado del servidor.
  - **Efecto de cambiar este ajuste:**
    - *Cuando se introduce:* Habilita el seguimiento del lado del servidor (API de Eventos), que es más fiable y menos afectado por los bloqueadores de anuncios.
    - *Cuando se deja vacío:* El seguimiento del lado del servidor se deshabilitará.
  - **Valor recomendado:** Tu Token de Acceso válido de la API de Eventos de TikTok.
  - **Escenario / ejemplo del comerciante:** Para mejorar la precisión de los datos y evitar las limitaciones del navegador, decides usar la API de Eventos. Generas un Token de Acceso en el Administrador de Anuncios de TikTok y lo pegas aquí.
- **Modo de Seguimiento:**

  - **Qué hace este ajuste:** Determina cómo se envían los datos a TikTok. Puedes elegir entre Píxel (lado del navegador), API de Eventos (lado del servidor) o Modo Dual (ambos).
  - **Efecto de cambiar este ajuste:**
    - *Solo Píxel:* Solo el seguimiento del lado del navegador está activo.
    - *Solo API de Eventos:* Solo el seguimiento del lado del servidor está activo.
    - *Modo Dual (Recomendado):* Tanto el Píxel como la API de Eventos están activos. El módulo utiliza inteligentemente un `event_id` compartido para deduplicar eventos en TikTok, asegurando la precisión.
  - **Valor recomendado:** `Modo Dual` para una máxima precisión de datos y resistencia contra los bloqueadores de anuncios.
  - **Escenario / ejemplo del comerciante:** Quieres el seguimiento más fiable posible. Seleccionas "Modo Dual" para que si un cliente usa un bloqueador de anuncios, la API de Eventos del lado del servidor aún pueda capturar la conversión, y TikTok no la contará dos veces si ambos métodos tienen éxito.
- **Habilitar Modo Depuración:**

  - **Qué hace este ajuste:** Activa un modo especial que muestra información detallada sobre los eventos de TikTok que se envían, directamente en la consola de desarrollador de tu navegador. Esto es invaluable para la resolución de problemas.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está habilitado:* Los desarrolladores y usuarios avanzados pueden ver exactamente qué datos se envían a TikTok en tiempo real, lo que ayuda a verificar la configuración correcta.
    - *Cuando está deshabilitado:* No se muestra información de depuración.
  - **Valor recomendado:** `No` para tiendas de producción en vivo. Solo habilítalo temporalmente para pruebas y depuración.
  - **Escenario / ejemplo del comerciante:** Acabas de instalar el módulo y quieres asegurarte de que los eventos `AddToCart` se están disparando correctamente. Habilitas el modo de depuración, añades un artículo a tu carrito y revisas la consola de tu navegador para ver los datos del evento de TikTok.

#### **Configuración Avanzada**

- **Gestión de Consentimiento (GDPR/CCPA):**

  - **Qué hace este ajuste:** Se integra con la solución de consentimiento de cookies de tu tienda (si está disponible) para asegurar que el seguimiento de TikTok solo se active después de que un cliente haya dado su consentimiento.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está habilitado:* El Píxel de TikTok/API de Eventos solo se cargará y enviará datos si el cliente ha aceptado las cookies.
    - *Cuando está deshabilitado:* El seguimiento ocurrirá independientemente del consentimiento de cookies, lo que podría no cumplir con las regulaciones de privacidad como GDPR o CCPA.
  - **Valor recomendado:** `Sí` si tu tienda opera en regiones con leyes de privacidad estrictas (por ejemplo, UE, California).
  - **Escenario / ejemplo del comerciante:** Tu tienda atiende a clientes en la Unión Europea. Para cumplir con el GDPR, habilitas este ajuste, asegurando que el seguimiento de TikTok respete las elecciones de privacidad del usuario.
- **Tipo de ID de Producto:**

  - **Qué hace este ajuste:** Determina qué identificador de producto (ID) se envía a TikTok. Las opciones suelen incluir el ID interno del producto de PrestaShop, EAN13, UPC o una referencia personalizada. Esto es crucial para hacer coincidir productos en tu Catálogo de Productos de TikTok.
  - **Efecto de cambiar este ajuste:**
    - *Cambiar el tipo:* Asegura que los ID de producto enviados a TikTok coincidan con los ID utilizados en tu Catálogo de Productos de TikTok, lo que permite anuncios de productos dinámicos.
  - **Valor recomendado:** Elige el tipo de ID que utilizas en tu Catálogo de Productos de TikTok. A menudo, el `ID de Producto` de PrestaShop o `EAN13` son opciones comunes.
  - **Escenario / ejemplo del comerciante:** Has subido un catálogo de productos a TikTok utilizando los códigos EAN13 de tus productos. Seleccionas `EAN13` aquí para asegurarte de que TikTok pueda identificar correctamente qué productos están viendo o comprando los clientes.
- **Dominios de Enlace (para seguimiento entre dominios):**

  - **Qué hace este ajuste:** Te permite especificar nombres de dominio adicionales si el viaje de tu cliente involucra múltiples dominios (por ejemplo, una tienda principal y un blog separado en un dominio diferente). Esto ayuda a TikTok a rastrear a los usuarios sin problemas a través de estos dominios.
  - **Efecto de cambiar este ajuste:**
    - *Cuando se añaden dominios:* TikTok puede mantener la coherencia del seguimiento de usuarios en los dominios listados.
    - *Cuando se deja vacío:* El seguimiento podría romperse si los clientes navegan entre diferentes dominios que forman parte de tu negocio.
  - **Valor recomendado:** Añade cualquier subdominio relevante o dominios vinculados que tus clientes puedan visitar.
  - **Escenario / ejemplo del comerciante:** Tu tienda principal es `mitienda.com`, pero tienes un blog en `blog.mitienda.com` donde enlazas a productos. Añadir `blog.mitienda.com` aquí asegura que TikTok pueda rastrear a los usuarios desde el blog hasta tu tienda.

#### **Calidad de Datos y Puntuación de Salud**

Esta sección proporciona información sobre el rendimiento y la precisión de tu seguimiento de TikTok.

- **Puntuación de Salud:**

  - **Qué hace:** Muestra una puntuación que indica la salud y precisión general de tu transmisión de datos a TikTok. Una puntuación más alta significa una mejor calidad de datos.
  - **Efecto:** Te ayuda a identificar rápidamente si hay problemas con tu configuración de seguimiento que podrían afectar el rendimiento de los anuncios.
  - **Recomendado:** Busca una puntuación alta. El módulo proporcionará recomendaciones si la puntuación es baja.
- **Radar de Recuperación:**

  - **Qué hace:** Monitorea los carritos abandonados y proporciona información sobre posibles ventas perdidas, ayudándote a identificar oportunidades para campañas de retargeting.
  - **Efecto:** Te da una visión rápida de cuántos carritos se inician frente a cuántos se completan, destacando áreas de mejora en tu proceso de pago o estrategia de retargeting.
- **Estadísticas en Vivo:**

  - **Qué hace:** Muestra datos en tiempo real sobre los eventos que se envían a TikTok, lo que te permite ver si los eventos se están disparando como se espera.
  - **Efecto:** Proporciona retroalimentación inmediata durante las pruebas y el monitoreo continuo, confirmando que tu seguimiento está activo y es preciso.

### 2.2 Pantallas de Administración Dedicadas y Vistas de Controlador

El módulo extiende el Back Office de PrestaShop con varias pantallas dedicadas para ayudarte a gestionar y monitorear tu integración con TikTok. Estas suelen ser accesibles desde la página de configuración del módulo a través de pestañas o elementos de menú dedicados.

#### **AdminMytiktokAjaxController (Operaciones Ajax)**

- **Nombre de la Pantalla y Ubicación del Menú:** Este controlador maneja principalmente las solicitudes AJAX en segundo plano desde la página de configuración del módulo. No navegarás directamente a una "pantalla" para esto, pero alimenta las actualizaciones dinámicas y la recuperación de datos dentro de las pestañas de configuración del módulo principal (por ejemplo, Estadísticas en Vivo, Puntuación de Salud, Registros de Eventos).
- **Acciones y Configuraciones Disponibles:** Procesa solicitudes para:
  - Obtener datos de eventos en vivo.
  - Actualizar puntuaciones de salud.
  - Recuperar información de diagnóstico.
  - Guardar partes específicas de la configuración sin una recarga completa de la página.
- **Efecto de los cambios:** Las interacciones en la página de configuración del módulo principal (como actualizar estadísticas en vivo o ejecutar diagnósticos) activan este controlador para obtener y mostrar los datos relevantes.
- **Flujo de trabajo recomendado para la gestión diaria de la tienda:** Interactúas con esto indirectamente utilizando las diversas herramientas de diagnóstico y monitoreo proporcionadas en la página de configuración del módulo principal.

#### **index.php (Punto de Entrada Principal del Módulo)**

- **Nombre de la Pantalla y Ubicación del Menú:** Este es el punto de entrada principal para la configuración del módulo, accesible a través de **Back Office > Módulos > Gestor de módulos > Configurar (para Píxel de TikTok / API de Eventos)**.
- **Acciones y Configuraciones Disponibles:** Esta pantalla presenta todas las configuraciones generales y avanzadas descritas en la sección 4.1, organizadas en pestañas o secciones lógicas. También alberga las diversas herramientas de diagnóstico como Puntuación de Salud, Estadísticas en Vivo y Radar de Recuperación.
- **Efecto de los cambios:** Cualquier cambio guardado en esta pantalla impacta directamente cómo funcionan tu Píxel de TikTok y la API de Eventos en tu tienda.
- **Flujo de trabajo recomendado para la gestión diaria de la tienda:**
  1. **Configuración Inicial:** Configura tu ID de Píxel, Token de Acceso y Modo de Seguimiento.
  2. **Monitoreo Regular:** Revisa periódicamente las pestañas "Puntuación de Salud" y "Estadísticas en Vivo" para asegurar la calidad de los datos y el disparo de eventos.
  3. **Resolución de Problemas:** Usa el "Modo Depuración" (temporalmente) y "Estadísticas en Vivo" para diagnosticar cualquier problema de seguimiento.
  4. **Optimización:** Revisa la información del "Radar de Recuperación" para informar tus estrategias de retargeting.

### 2.3 Tabla de Referencia Rápida de Configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| Configuración del Módulo | ID del Píxel de TikTok | Tu ID de Píxel | Vincula tu tienda a tu cuenta de anuncios de TikTok para el seguimiento del navegador. |
| Configuración del Módulo | Token de Acceso de TikTok | Tu Token de Acceso | Autoriza el seguimiento del lado del servidor a través de la API de Eventos. |
| Configuración del Módulo | Modo de Seguimiento | Modo Dual | Determina si se utiliza el Píxel, la API de Eventos o ambos para el seguimiento. Se recomienda el modo dual para mayor precisión. |
| Configuración del Módulo | Habilitar Modo Depuración | No (para producción) | Muestra datos detallados de eventos en la consola del navegador para la resolución de problemas. |
| Configuración del Módulo | Gestión de Consentimiento | Sí (para GDPR/CCPA) | Asegura que el seguimiento respete el consentimiento de cookies del usuario. |
| Configuración del Módulo | Tipo de ID de Producto | Coincide con tu Catálogo | Selecciona el identificador de producto enviado a TikTok para la coincidencia del catálogo. |
| Configuración del Módulo | Dominios de Enlace | Vacío (añadir si es necesario) | Permite el seguimiento entre dominios para estructuras de sitio complejas. |
| Configuración del Módulo | Puntuación de Salud | Puntuación alta | Indica la calidad general de los datos y la precisión del seguimiento. |
| Configuración del Módulo | Radar de Recuperación | Monitorear | Información sobre carritos abandonados para retargeting. |
| Configuración del Módulo | Estadísticas en Vivo | Monitorear | Vista en tiempo real de los eventos enviados a TikTok. |

## 3. Resolución de Problemas del Comerciante y Preguntas Frecuentes (FAQ)

**P1: He instalado el módulo, pero no veo ningún dato en mi Administrador de Anuncios de TikTok. ¿Qué debo hacer?**

- **R:** Primero, verifica que tu **ID de Píxel de TikTok** y **Token de Acceso** estén correctamente introducidos en la configuración del módulo. Asegúrate de que no haya errores tipográficos.
- A continuación, verifica que tu **Modo de Seguimiento** esté configurado en "Modo Dual" o "Píxel" (si solo estás usando el Píxel).
- Habilita el **Modo Depuración** en la configuración del módulo, luego visita el front office de tu tienda, realiza algunas acciones (como ver un producto, añadir al carrito) y revisa la consola de desarrollador de tu navegador (normalmente F12 > pestaña Consola) para ver los mensajes de eventos de TikTok.
- Finalmente, borra la caché de tu PrestaShop (**Parámetros Avanzados > Rendimiento > Borrar caché**).

**P2: Mi Puntuación de Salud de TikTok es baja. ¿Cómo puedo mejorarla?**

- **R:** Una Puntuación de Salud baja a menudo indica problemas con la calidad de los datos o la entrega de eventos.
- **Verifica si faltan datos:** Asegúrate de que toda la información requerida del producto (precio, moneda, nombre) esté completa para tus productos.
- **Verifica el consentimiento:** Si tienes la "Gestión de Consentimiento" habilitada, asegúrate de que tu banner de consentimiento de cookies esté funcionando correctamente y que los usuarios estén aceptando las cookies.
- **Revisa las Estadísticas en Vivo:** Busca cualquier error o evento faltante en la sección "Estadísticas en Vivo" del módulo.
- El propio módulo a menudo proporciona recomendaciones específicas dentro de la sección Puntuación de Salud para guiarte.

**P3: ¿Este módulo ralentizará mi sitio web?**

- **R:** El módulo está diseñado para ser ligero y eficiente. El seguimiento del Píxel del lado del navegador podría añadir una pequeña carga insignificante, similar a cualquier otro script de análisis. La API de Eventos del lado del servidor prácticamente no tiene impacto en los tiempos de carga del front office, ya que los datos se envían directamente desde tu servidor. Recomendamos usar el "Modo Dual" para un rendimiento óptimo y una precisión de datos.

**P4: Tengo un tema personalizado. ¿Funcionará el módulo correctamente?**

- **R:** Sí, el módulo está diseñado para integrarse perfectamente con los temas estándar de PrestaShop y la mayoría de los temas personalizados. Utiliza el sistema de hooks oficial de PrestaShop para inyectar sus scripts y código de seguimiento.
- Si encuentras algún problema con un tema altamente personalizado, especialmente si altera significativamente las plantillas principales de PrestaShop para las páginas de productos o el proceso de pago, es posible que debas consultar con un desarrollador para asegurarte de que los hooks sigan presentes y se rendericen correctamente.

**Q5: ¿Cómo maneja el módulo las tiendas multi-idioma y multi-moneda?**

- **R:** El módulo está diseñado para ser totalmente compatible con las funciones multi-idioma y multi-moneda de PrestaShop. Detecta automáticamente el idioma y la moneda activos en el front office y envía esta información a TikTok, asegurando que tus datos de eventos sean precisos y localizados. Los nombres y valores de los productos se enviarán en el contexto del idioma y la moneda seleccionados por el cliente.

## 4. Guía para Desarrolladores y Webmasters (Arquitectura Técnica y Mapa de Código)

Esta sección proporciona una inmersión profunda en la estructura técnica del módulo Píxel de TikTok / API de Eventos, destinada a desarrolladores, webmasters y agencias técnicas.

### 4.1 Visión General de la Arquitectura

El módulo `mytiktok` sigue una arquitectura de módulo estándar de PrestaShop, aprovechando el patrón MVC cuando es apropiado. Funciona principalmente como un rastreador de eventos, inyectando JavaScript para el seguimiento del lado del cliente (Píxel) y utilizando la lógica del lado del servidor para la API de Eventos. Los componentes clave incluyen:

- **Clase Principal del Módulo (`index.php`):** Maneja la instalación, desinstalación, configuración y registro de hooks.
- **Controladores:** Controladores frontales para solicitudes AJAX y controladores de administración para la gestión del back-office.
- **Clases Principales:** Un conjunto robusto de clases (`classes/`) para gestionar la comunicación API, el mapeo de eventos, la calidad de los datos, el consentimiento y varias estrategias de seguimiento (Píxel, CAPI, Híbrido).
- **Plantillas:** Plantillas Smarty tanto para la inyección de hooks en el front-office como para las vistas de configuración del back-office.
- **Activos:** JS y CSS dedicados para las interfaces de administración y la depuración/seguimiento del front-office.

El módulo implementa una `MytiktokTrackerInterface` y utiliza una `MytiktokTrackerFactory` para abstraer diferentes modos de seguimiento (Píxel, CAPI, Híbrido), promoviendo un diseño limpio y extensible. También incluye sofisticadas herramientas de calidad de datos y monitoreo de salud.

### 4.2 Controladores (`controllers/`)

#### Controladores del Front-Office

- `mytiktok/controllers/front/ajax.php`
  - **Nombre de la clase y clase padre:** `MytiktokAjaxModuleFrontController` extiende `ModuleFrontController`.
  - **Responsabilidad:** Maneja solicitudes asíncronas desde el front-office, principalmente para el seguimiento de eventos del lado del servidor (API de Eventos) o la recopilación de datos que no requiere una recarga completa de la página. Podría procesar datos enviados por JavaScript y reenviarlos a la API de Eventos de TikTok.
- `mytiktok/controllers/front/index.php`
  - **Nombre de la clase y clase padre:** `MytiktokIndexModuleFrontController` extiende `ModuleFrontController`.
  - **Responsabilidad:** Este controlador podría servir como un respaldo o un punto final específico para ciertas interacciones del front-office, aunque `ajax.php` suele ser más activo para el manejo de eventos. Podría usarse para redirecciones o inicializaciones específicas si es necesario.

#### Controladores de Administración del Back-Office

- `mytiktok/controllers/admin/AdminMytiktokAjaxController.php`
  - **Nombre de la clase y clase padre:** `AdminMytiktokAjaxController` extiende `ModuleAdminController`.
  - **Nombre de la pestaña y entidad gestionada:** Este controlador no es directamente accesible como una pestaña de menú. Maneja las solicitudes AJAX que se originan en la página de configuración principal del módulo (`index.php`) en el back office. Es responsable de las actualizaciones dinámicas, la obtención de estadísticas en vivo, puntuaciones de salud, registros de eventos y otros datos de diagnóstico sin requerir una actualización completa de la página.
- `mytiktok/controllers/admin/index.php`
  - **Nombre de la clase y clase padre:** `AdminMytiktokController` extiende `ModuleAdminController`.
  - **Nombre de la pestaña y entidad gestionada:** Este es el controlador de administración principal para la configuración del módulo. Es el controlador al que `index.php` (el archivo principal del módulo) envía cuando se hace clic en el botón "Configurar". Gestiona la visualización de todos los formularios de configuración, pestañas (por ejemplo, Configuración General, Calidad de Datos, Estadísticas en Vivo) y maneja el guardado de la configuración del módulo.

### 4.3 Clases y Modelos Principales (`classes/`)

- `mytiktok/classes/autoload.php`: Archivo de carga automática estándar de PrestaShop, que asegura que las clases del módulo se carguen correctamente.
- `mytiktok/classes/index.php`: Archivo vacío, a menudo utilizado para evitar la lista de directorios.
- `mytiktok/classes/MytiktokCapiClient.php`:
  - **Tabla de base de datos:** Ninguna directamente.
  - **Extiende ObjectModel:** No.
  - **Métodos públicos clave:** Maneja la comunicación con la API de Eventos de TikTok (CAPI). Contiene métodos para enviar datos de eventos, gestionar la autenticación con el Token de Acceso y manejar las respuestas de la API.
- `mytiktok/classes/MytiktokCapiTracker.php`:
  - **Tabla de base de datos:** Ninguna directamente.
  - **Extiende ObjectModel:** No.
  - **Métodos públicos clave:** Implementa `MytiktokTrackerInterface`. Responsable de preparar y enviar eventos del lado del servidor a TikTok a través de `MytiktokCapiClient`.
- `mytiktok/classes/MytiktokCatalogDoctor.php`:
  - **Tabla de base de datos:** Ninguna directamente.
  - **Extiende ObjectModel:** No.
  - **Métodos públicos clave:** Proporciona herramientas de diagnóstico y recomendaciones relacionadas con los datos del catálogo de productos, asegurando que los ID de producto y los atributos estén formateados correctamente para TikTok.
- `mytiktok/classes/MytiktokConsent.php`:
  - **Tabla de base de datos:** Ninguna directamente.
  - **Extiende ObjectModel:** No.
  - **Métodos públicos clave:** Gestiona la lógica de consentimiento de cookies, integrándose con los mecanismos de consentimiento de PrestaShop o módulos de consentimiento personalizados para garantizar el cumplimiento de GDPR/CCPA.
- `mytiktok/classes/MytiktokCurrencyHelper.php`:
  - **Tabla de base de datos:** Ninguna directamente.
  - **Extiende ObjectModel:** No.
  - **Métodos públicos clave:** Clase de utilidad para manejar el formato y las conversiones de moneda, asegurando que los valores de los eventos se envíen a TikTok en el formato y la moneda correctos.
- `mytiktok/classes/MytiktokDataQualityCoach.php`:
  - **Tabla de base de datos:** Ninguna directamente.
  - **Extiende ObjectModel:** No.
  - **Métodos públicos clave:** Analiza la calidad y la integridad de los datos que se envían a TikTok, proporcionando información y sugerencias para mejorar.
- `mytiktok/classes/MytiktokEventId.php`:
  - **Tabla de base de datos:** Ninguna directamente.
  - **Extiende ObjectModel:** No.
  - **Métodos públicos clave:** Genera y gestiona valores `event_id` únicos para eventos, crucial para la deduplicación en el seguimiento en modo dual.
- `mytiktok/classes/MytiktokEventMap.php`:
  - **Tabla de base de datos:** Ninguna directamente.
  - **Extiende ObjectModel:** No.
  - **Métodos públicos clave:** Mapea acciones y datos de PrestaShop a nombres y propiedades de eventos estándar de TikTok (por ejemplo, `ViewContent`, `AddToCart`, `CompletePayment`).
- `mytiktok/classes/MytiktokEvents.php`:
  - **Tabla de base de datos:** Ninguna directamente.
  - **Extiende ObjectModel:** No.
  - **Métodos públicos clave:** Clase central para activar y gestionar varios eventos de TikTok basados en las acciones del usuario en PrestaShop.
- `mytiktok/classes/MytiktokHealthScore.php`:
  - **Tabla de base de datos:** Ninguna directamente.
  - **Extiende ObjectModel:** No.
  - **Métodos públicos clave:** Calcula y muestra la puntuación de salud general de la integración de TikTok basada en la calidad de los datos, la entrega de eventos y la configuración.
- `mytiktok/classes/MytiktokHybridTracker.php`:
  - **Tabla de base de datos:** Ninguna directamente.
  - **Extiende ObjectModel:** No.
  - **Métodos públicos clave:** Implementa `MytiktokTrackerInterface`. Orquesta el seguimiento en modo dual, enviando eventos a través de Píxel y CAPI con deduplicación de `event_id`.
- `mytiktok/classes/MytiktokLiveStats.php`:
  - **Tabla de base de datos:** Ninguna directamente.
  - **Extiende ObjectModel:** No.
  - **Métodos públicos clave:** Recopila y muestra estadísticas en tiempo real de los eventos que se envían a TikTok para fines de monitoreo.
- `mytiktok/classes/MytiktokPixelTracker.php`:
  - **Tabla de base de datos:** Ninguna directamente.
  - **Extiende ObjectModel:** No.
  - **Métodos públicos clave:** Implementa `MytiktokTrackerInterface`. Responsable de inyectar y gestionar eventos del Píxel de TikTok del lado del navegador.
- `mytiktok/classes/MytiktokProductIdResolver.php`:
  - **Tabla de base de datos:** Ninguna directamente.
  - **Extiende ObjectModel:** No.
  - **Métodos públicos clave:** Resuelve el ID de producto correcto basado en la configuración del módulo (por ejemplo, ID de PrestaShop, EAN13, UPC) para enviarlo a TikTok.
- `mytiktok/classes/MytiktokPropertyRules.php`:
  - **Tabla de base de datos:** Ninguna directamente.
  - **Extiende ObjectModel:** No.
  - **Métodos públicos clave:** Define y aplica reglas para las propiedades de los eventos, asegurando que los datos enviados a TikTok se adhieran a sus especificaciones.
- `mytiktok/classes/MytiktokTrackerFactory.php`:
  - **Tabla de base de datos:** Ninguna directamente.
  - **Extiende ObjectModel:** No.
  - **Métodos públicos clave:** Patrón de fábrica para instanciar la clase de rastreador correcta (`MytiktokPixelTracker`, `MytiktokCapiTracker` o `MytiktokHybridTracker`) basada en la configuración del "Modo de Seguimiento" del módulo.
- `mytiktok/classes/MytiktokTrackerInterface.php`:
  - **Tabla de base de datos:** Ninguna directamente.
  - **Extiende ObjectModel:** No.
  - **Métodos públicos clave:** Define el contrato para todas las clases de rastreadores, asegurando una interfaz consistente para el envío de eventos.
- `mytiktok/classes/MytiktokTrans.php`:
  - **Tabla de base de datos:** Ninguna directamente.
  - **Extiende ObjectModel:** No.
  - **Métodos públicos clave:** Clase de utilidad para manejar las traducciones del módulo.
- `mytiktok/classes/MytiktokUserData.php`:
  - **Tabla de base de datos:** Ninguna directamente.
  - **Extiende ObjectModel:** No.
  - **Métodos públicos clave:** Recopila y formatea datos de usuario (por ejemplo, correo electrónico, teléfono, dirección IP) para una coincidencia mejorada en la API de Eventos de TikTok.

### 4.4 Activos JavaScript (`views/js/`)

- `mytiktok/views/js/mytiktok-admin.js`:
  - **Alcance:** Back-office.
  - **Descripción:** Maneja elementos interactivos y llamadas AJAX dentro de las páginas de administración del módulo. Esto incluye la gestión de pestañas, la actualización de estadísticas en vivo, el manejo de envíos de formularios y los pasos del asistente.
- `mytiktok/views/js/mytiktok-debug.js`:
  - **Alcance:** Front-office (cuando el modo de depuración está habilitado).
  - **Descripción:** Inyecta información de depuración en la consola del navegador, registrando eventos de TikTok, sus propiedades y posibles problemas. Esencial para verificar el correcto disparo de eventos.
- `mytiktok/views/js/mytiktok-ghost.js`:
  - **Alcance:** Front-office.
  - **Descripción:** Potencialmente maneja mecanismos de seguimiento "fantasma" u ocultos, posiblemente relacionados con la iniciación de eventos del lado del servidor o interacciones específicas del usuario que deben capturarse sin interacción directa del píxel.
- `mytiktok/views/js/mytiktok-live.js`:
  - **Alcance:** Back-office.
  - **Descripción:** Impulsa la función "Estadísticas en Vivo" en el panel de administración, obteniendo y mostrando periódicamente datos de eventos en tiempo real.
- `mytiktok/views/js/mytiktok-tcf.js`:
  - **Alcance:** Front-office.
  - **Descripción:** Se integra con el Marco de Transparencia y Consentimiento (TCF) u otras soluciones de consentimiento de cookies para gestionar el consentimiento del usuario antes de inicializar el Píxel de TikTok.
- `mytiktok/views/js/mytiktok-wizard.js`:
  - **Alcance:** Back-office.
  - **Descripción:** Gestiona el asistente de configuración paso a paso para la configuración inicial del módulo, guiando al comerciante a través de los ajustes esenciales.
- `mytiktok/views/js/mytiktok.js`:
  - **Alcance:** Front-office.
  - **Descripción:** El archivo JavaScript principal del front-office. Inicializa el Píxel de TikTok, activa eventos estándar (PageView, ViewContent, AddToCart, InitiateCheckout) y recopila los datos necesarios del DOM para enviarlos a TikTok. También maneja la generación de `event_id` para la deduplicación.

### 4.5 Hojas de Estilo CSS (`views/css/`)

- `mytiktok/views/css/mytiktok-admin.css`:
  - **Alcance:** Estilo del formulario de administración del back-office.
  - **Descripción:** Estiliza la página de configuración del módulo, incluyendo pestañas, campos de entrada, botones y pantallas de diagnóstico (Puntuación de Salud, Estadísticas en Vivo, etc.) para garantizar una interfaz consistente y fácil de usar dentro del back office de PrestaShop.
- `mytiktok/views/css/mytiktok-debug.css`:
  - **Alcance:** Estilo del cliente del front-office (solo cuando el modo de depuración está activo).
  - **Descripción:** Proporciona un estilo mínimo para cualquier elemento de depuración visual que pueda aparecer en el front office cuando el modo de depuración está habilitado (por ejemplo, una pequeña superposición o banner que indica el estado de depuración).

### 4.6 Estructura de Plantillas Smarty (`views/templates/`)

#### Plantillas de hook (`views/templates/hook/`)

- `mytiktok/views/templates/hook/capi-pageview.tpl`:
  - **Hook:** Potencialmente `displayHeader` o `displayBeforeBodyClosingTag`.
  - **Salida:** Renderiza el evento `PageView` del lado del servidor para la API de Eventos. Esta plantilla podría contener campos ocultos o estructuras de datos utilizadas por la lógica del lado del servidor para iniciar el evento CAPI PageView.
- `mytiktok/views/templates/hook/debug.tpl`:
  - **Hook:** `displayHeader` o `displayBeforeBodyClosingTag`.
  - **Salida:** Renderiza un pequeño bloque HTML o etiqueta de script para fines de depuración, a menudo incluyendo `mytiktok-debug.js` y datos de depuración iniciales.
- `mytiktok/views/templates/hook/displayOrderConfirmation.tpl`:
  - **Hook:** `displayOrderConfirmation`.
  - **Salida:** Renderiza los datos del evento `CompletePayment`, incluyendo el valor del pedido, la moneda y los detalles del producto, para ser enviados al Píxel de TikTok y/o la API de Eventos después de una compra exitosa.
- `mytiktok/views/templates/hook/ghost.tpl`:
  - **Hook:** Varios hooks del front-office.
  - **Salida:** Renderiza elementos o scripts ocultos para el seguimiento "fantasma", potencialmente relacionados con disparadores de eventos del lado del servidor o recopilación avanzada de datos.
- `mytiktok/views/templates/hook/header.tpl`:
  - **Hook:** `displayHeader`.
  - **Salida:** Inyecta el código base principal del Píxel de TikTok, `mytiktok.js`, y las variables de configuración iniciales en la sección `<head>` de todas las páginas del front-office. Aquí es donde se inicializa el Píxel.
- `mytiktok/views/templates/hook/payment.tpl`:
  - **Hook:** Potencialmente `displayPaymentTop` o `displayPaymentOptions`.
  - **Salida:** Puede renderizar datos del evento `InitiateCheckout` o scripts relacionados cuando un cliente llega al paso de selección de pago durante el proceso de compra.
- `mytiktok/views/templates/hook/product-details.tpl`:
  - **Hook:** `displayProductAdditionalInfo` o un hook similar de la página de producto.
  - **Salida:** Renderiza los datos del evento `ViewContent`, incluyendo el ID del producto, nombre, precio y categoría, para el producto actualmente visto.

#### Plantillas de administración (`views/templates/admin/`)

- `mytiktok/views/templates/admin/consent-guide.tpl`: Muestra una guía sobre cómo configurar el consentimiento de cookies.
- `mytiktok/views/templates/admin/doctor.tpl`: Renderiza la interfaz de diagnóstico del "Doctor de Catálogo".
- `mytiktok/views/templates/admin/dq.tpl`: Muestra información y recomendaciones sobre la calidad de los datos.
- `mytiktok/views/templates/admin/health.tpl`: Renderiza el panel de control de "Puntuación de Salud".
- `mytiktok/views/templates/admin/linker-domains.tpl`: Campo de formulario para configurar dominios de enlace.
- `mytiktok/views/templates/admin/live-maintain.tpl`: Vista de marcador de posición o mantenimiento para estadísticas en vivo.
- `mytiktok/views/templates/admin/live.tpl`: Muestra el panel de control de "Estadísticas en Vivo".
- `mytiktok/views/templates/admin/mode-context.tpl`: Información contextual sobre el modo de seguimiento seleccionado.
- `mytiktok/views/templates/admin/mode-note-both.tpl`: Nota/explicación para el seguimiento en "Modo Dual".
- `mytiktok/views/templates/admin/mode-note-capi.tpl`: Nota/explicación para el seguimiento "Solo API de Eventos".
- `mytiktok/views/templates/admin/mode-note-pixel.tpl`: Nota/explicación para el seguimiento "Solo Píxel".
- `mytiktok/views/templates/admin/mode-picker.tpl`: La interfaz para seleccionar el modo de seguimiento (Píxel, CAPI, Dual).
- `mytiktok/views/templates/admin/properties-list.tpl`: Muestra una lista de propiedades de eventos.
- `mytiktok/views/templates/admin/recent-events.tpl`: Muestra un registro de eventos recientes enviados.
- `mytiktok/views/templates/admin/tabs.tpl`: Estructura para la interfaz con pestañas en la página de configuración del módulo.
- `mytiktok/views/templates/admin/tag-chips.tpl`: Componentes visuales para mostrar etiquetas o ID.
- `mytiktok/views/templates/admin/tag-ids.tpl`: Campos de entrada para el ID del Píxel de TikTok y el Token de Acceso.
- `mytiktok/views/templates/admin/wizard.tpl`: La interfaz del asistente de configuración paso a paso.

#### Plantillas del front-office (`views/templates/front/`)

- No se listan plantillas de página independientes dedicadas, ya que el módulo inyecta principalmente scripts y datos a través de hooks.

### 4.7 Esquema de Base de Datos y Mapa de Hooks

#### Tablas de Base de Datos

El módulo almacena principalmente su configuración en la tabla `ps_configuration` de PrestaShop.

- `ps_configuration`: Almacena pares clave-valor para la configuración del módulo, como `MYTIKTOK_PIXEL_ID`, `MYTIKTOK_ACCESS_TOKEN`, `MYTIKTOK_TRACKING_MODE`, etc.

#### Tabla de Hooks Registrados

| Nombre del Hook | Momento de Ejecución | Propósito Técnico |
| --- | --- | --- |
| `displayHeader` | En la sección `<head>` de cada página del front-office. | Inicializa el código base del Píxel de TikTok, carga `mytiktok.js` y configura variables de configuración globales. |
| `displayBeforeBodyClosingTag` | Justo antes de la etiqueta `</body>`. | Puede inyectar scripts o datos adicionales que necesitan ejecutarse después de que se carga el DOM, o para eventos CAPI PageView. |
| `displayProductAdditionalInfo` | En la página del producto, típicamente cerca de los detalles del producto. | Activa el evento `ViewContent`, pasando datos específicos del producto a TikTok. |
| `displayShoppingCartFooter` | En la página del carrito, generalmente debajo del resumen del carrito. | Activa el evento `AddToCart` (si no se ha manejado ya por AJAX) y potencialmente `InitiateCheckout`. |
| `displayPaymentTop` | En la parte superior de la página de selección de pago durante el proceso de compra. | Activa el evento `InitiateCheckout`. |
| `displayOrderConfirmation` | En la página de confirmación del pedido después de una compra exitosa. | Activa el crucial evento `CompletePayment`, enviando los detalles completos del pedido (valor, productos, moneda) a TikTok. |
| `actionFrontControllerSetMedia` | Cuando un controlador frontal establece sus activos multimedia. | Inyecta archivos JS/CSS específicos del módulo en el front office. |
| `actionAdminControllerSetMedia` | Cuando un controlador de administración establece sus activos multimedia. | Inyecta archivos JS/CSS específicos del módulo en el back office. |
| `actionValidateOrder` | Después de que un pedido ha sido validado con éxito. | Disparador del lado del servidor para el evento `CompletePayment` a través de la API de Eventos, asegurando un seguimiento de conversión fiable. |
| `actionCartSave` | Cuando se actualiza el carrito (por ejemplo, añadir/eliminar producto). | Disparador del lado del servidor para los eventos `AddToCart` o `RemoveFromCart` a través de la API de Eventos. |
| `actionProductUpdate` | Cuando se actualiza un producto en el back office. | Potencialmente utilizado para la sincronización del catálogo o comprobaciones de calidad de datos. |
| `actionObjectProductAddAfter` | Después de que se añade un nuevo producto. | Potencialmente utilizado para la sincronización del catálogo o comprobaciones de calidad de datos. |
| `actionObjectProductUpdateAfter` | Después de que se actualiza un producto. | Potencialmente utilizado para la sincronización del catálogo o comprobaciones de calidad de datos. |

## 5. Soporte Oficial y Actualizaciones

Para las últimas actualizaciones, correcciones de errores y soporte oficial para el módulo "Píxel de TikTok / API de Eventos", consulta tu cuenta de cliente en [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nuestro equipo de soporte dedicado está disponible para ayudarte con cualquier problema técnico o pregunta relacionada con la funcionalidad del módulo.
