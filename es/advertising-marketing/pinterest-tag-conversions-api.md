---
title: "Etiqueta de Pinterest y API de Conversiones - Manual del Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop Etiqueta de Pinterest y API de Conversiones de MyPresta.eu."
sidebar:
  label: "Etiqueta de Pinterest y API de Conversiones - Manual del Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Pinterest Tag & Conversions API en MyPresta.eu](https://mypresta.eu/modules/advertising-and-marketing/pinterest-tag-conversions-api.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/advertising-marketing/pinterest-tag-conversions-api/)
>
> ---


# Etiqueta de Pinterest y API de Conversiones

## 1. Requisitos y Compatibilidad

- **Versiones de PrestaShop Compatibles**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilidad con PHP**: PHP 7.1 - 8.5
- **Requisitos de Alojamiento**: Extensiones PHP estándar (cURL, JSON, OpenSSL). Su servidor debe poder realizar solicitudes HTTP salientes a los puntos finales de la API de Pinterest.

## 2. Recorrido Completo por la Configuración (Cada Ajuste Agrupado por Pantalla)

### 2.1 Página de Configuración del Módulo (Back Office > Módulos > Configurar)

Este es el centro principal para configurar su seguimiento de Pinterest. Encontrará varias secciones y pestañas para gestionar su Etiqueta de Pinterest, la API de Conversiones y la calidad de los datos.

#### Configuración General y Modo de Seguimiento

- **ID de la Etiqueta de Pinterest (Obligatorio)**

  - **Qué hace este ajuste:** Este es su identificador único proporcionado por Pinterest. Le dice a Pinterest a qué cuenta de anuncios pertenecen los datos de su sitio web.
  - **Efecto de cambiar este ajuste:**
    - *Cuando se introduce:* Permite que el módulo envíe datos a su cuenta de anuncios de Pinterest. Sin él, no puede haber seguimiento.
    - *Cuando está vacío:* El módulo no puede enviar ningún dato a Pinterest.
  - **Valor recomendado:** Su ID de la Etiqueta de Pinterest. Puede encontrarlo en su Administrador de Anuncios de Pinterest en "Anuncios" > "Conversiones" > "Etiqueta de Pinterest".
  - **Escenario / ejemplo de comerciante:** Acaba de crear una cuenta de Anuncios de Pinterest y necesita vincular su tienda a ella. Copie el ID de la Etiqueta de Pinterest y péguelo aquí.
- **Modo de Seguimiento**

  - **Qué hace este ajuste:** Determina cómo su tienda envía datos a Pinterest. Puede elegir entre la Etiqueta de Pinterest tradicional (del lado del navegador), la API de Conversiones más robusta (del lado del servidor) o una combinación de ambas.
  - **Efecto de cambiar este ajuste:**
    - *Etiqueta de Pinterest (del lado del navegador):* Los datos se envían directamente desde el navegador del cliente. Esto es más simple pero puede verse afectado por bloqueadores de anuncios o configuraciones de privacidad del navegador.
    - *API de Conversiones (del lado del servidor):* Los datos se envían directamente desde su servidor PrestaShop a Pinterest. Esto es más fiable y menos propenso a bloqueos, ofreciendo una mejor precisión de los datos.
    - *Ambos (Híbrido con Deduplicación):* Los datos se envían por ambos métodos. El módulo añade automáticamente un `event_id` único a cada evento, lo que permite a Pinterest identificar e ignorar eventos duplicados, asegurando la máxima cobertura de datos sin contar en exceso.
  - **Valor recomendado:** **Ambos (Híbrido con Deduplicación)** para el seguimiento más fiable y completo.
  - **Escenario / ejemplo de comerciante:** Quiere asegurarse de que sus campañas de Pinterest sean lo más precisas posible, incluso con el aumento de las medidas de privacidad. Elegir "Ambos" proporciona lo mejor de ambos mundos.

#### Configuración de la API de Conversiones (CAPI) (Visible si se selecciona el modo CAPI o Ambos)

- **Token de Acceso a la API de Conversiones (Obligatorio para CAPI)**

  - **Qué hace este ajuste:** Este es un token seguro que autentica su servidor al enviar datos directamente a la API de Conversiones de Pinterest. Es como una contraseña para que su servidor se comunique con Pinterest.
  - **Efecto de cambiar este ajuste:**
    - *Cuando se introduce:* Permite que su servidor envíe datos a través de la API de Conversiones.
    - *Cuando está vacío:* El seguimiento de la API de Conversiones no funcionará, incluso si se selecciona como modo de seguimiento.
  - **Valor recomendado:** Su Token de Acceso a la API de Conversiones de Pinterest. Genérelo en su Administrador de Anuncios de Pinterest en "Anuncios" > "Conversiones" > "API de Conversiones".
  - **Escenario / ejemplo de comerciante:** Ha decidido utilizar la API de Conversiones para un seguimiento más fiable. Generará este token en Pinterest y lo pegará aquí.
- **Habilitar Coincidencia Mejorada para CAPI**

  - **Qué hace este ajuste:** Cuando está habilitado, el módulo envía información adicional del cliente (como correo electrónico, número de teléfono, nombre, dirección, todo cifrado para la privacidad) con los eventos de la API de Conversiones. Esto ayuda a Pinterest a hacer coincidir los eventos con usuarios específicos de manera más precisa, incluso si no han iniciado sesión en Pinterest.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está habilitado:* Mejora la precisión de la coincidencia de eventos en Pinterest, lo que lleva a una mejor segmentación de la audiencia y optimización de la campaña.
    - *Cuando está deshabilitado:* Solo se envían datos básicos del evento, lo que podría reducir la precisión de la coincidencia.
  - **Valor recomendado:** **SÍ**. Esto mejora significativamente la calidad de los datos y el rendimiento de los anuncios.
  - **Escenario / ejemplo de comerciante:** Quiere asegurarse de que Pinterest pueda atribuir con precisión las ventas a sus anuncios, incluso si los clientes usan diferentes dispositivos o navegadores. La Coincidencia Mejorada ayuda a cerrar estas brechas.

#### Privacidad de Datos y Consentimiento

- **Integrar con Módulo de Consentimiento de Cookies**
  - **Qué hace este ajuste:** Si utiliza un módulo de consentimiento de cookies separado (por ejemplo, un módulo de cumplimiento del RGPD), habilitar esto asegura que el seguimiento de Pinterest solo se active después de que el cliente haya dado su consentimiento.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está habilitado:* El seguimiento de Pinterest respetará las opciones de consentimiento del cliente de su módulo de cookies. Si se deniega el consentimiento, no se enviarán datos a Pinterest.
    - *Cuando está deshabilitado:* El seguimiento de Pinterest se activará independientemente de otras configuraciones de consentimiento de cookies, lo que podría generar problemas de cumplimiento.
  - **Valor recomendado:** **SÍ** si utiliza un módulo de consentimiento de cookies. **NO** si no utiliza uno o gestiona el consentimiento manualmente.
  - **Escenario / ejemplo de comerciante:** Su tienda necesita cumplir con el RGPD. Al habilitar esto, se asegura de que el seguimiento de Pinterest se adhiera a las preferencias de privacidad de sus clientes.

#### Configuración Avanzada y Depuración

- **Habilitar Modo Depuración**

  - **Qué hace este ajuste:** Activa un modo especial que muestra información detallada sobre los eventos de Pinterest que se están enviando, directamente en la consola de desarrollador de su navegador. Esto es útil para verificar que su seguimiento funciona correctamente.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está habilitado:* Los desarrolladores y webmasters pueden ver datos de eventos de Pinterest en tiempo real en la consola del navegador. Esto **nunca** debe habilitarse en una tienda de producción en vivo para la visualización pública general.
    - *Cuando está deshabilitado:* No se muestra información de depuración.
  - **Valor recomendado:** **NO** para una tienda de producción en vivo. **SÍ** solo durante la configuración y las pruebas.
  - **Escenario / ejemplo de comerciante:** Acaba de instalar el módulo y quiere confirmar que los eventos de "Añadir al Carrito" se están activando correctamente. Habilita el modo de depuración, añade un producto a su carrito y verifica la consola del navegador para ver los datos del evento.
- **Dominios de Enlace (para seguimiento entre dominios)**

  - **Qué hace este ajuste:** Si su tienda utiliza múltiples subdominios o redirige a otro dominio durante el proceso de pago (por ejemplo, un dominio de pasarela de pago separado), puede listar esos dominios aquí. Esto ayuda a Pinterest a atribuir correctamente las acciones entre diferentes dominios.
  - **Efecto de cambiar este ajuste:**
    - *Cuando se listan dominios:* Pinterest puede mantener la continuidad del seguimiento entre estos dominios, evitando la pérdida de datos.
    - *Cuando está vacío:* El seguimiento podría romperse si los clientes navegan entre diferentes dominios durante su recorrido, lo que lleva a datos incompletos.
  - **Valor recomendado:** Dejar vacío a menos que tenga necesidades específicas de seguimiento entre dominios. Si es así, introduzca cada dominio en una nueva línea.
  - **Escenario / ejemplo de comerciante:** Su tienda principal es `shop.example.com`, pero su blog es `blog.example.com` y desea rastrear a los usuarios que visitan ambos. Añadiría `blog.example.com` aquí.

#### Calidad de Datos y Puntuación de Salud (Secciones Informativas)

Estas secciones proporcionan información sobre su configuración de seguimiento y no son configuraciones directas, sino informes generados por el módulo.

- **Puntuación de Salud**: Muestra una puntuación general que indica la calidad y la integridad de su configuración de seguimiento de Pinterest. Una puntuación más alta significa datos más fiables.
- **Doctor de Catálogo**: Ayuda a identificar posibles problemas con los datos de su catálogo de productos que podrían afectar la capacidad de Pinterest para hacer coincidir productos para anuncios dinámicos.
- **Entrenador de Calidad de Datos**: Proporciona recomendaciones y advertencias sobre los datos de sus eventos, como parámetros faltantes o formato incorrecto, para ayudarle a mejorar la precisión.
- **Estadísticas en Vivo**: Muestra los eventos recientes enviados a Pinterest, lo que le permite monitorear la actividad en tiempo real.
- **Eventos Recientes**: Un registro de los eventos más recientes procesados por el módulo.

### 2.2 Pantallas de Administración Dedicadas y Vistas de Controlador

#### 2.2.1 AdminMypinterestAjaxController (Back Office > Módulos > Etiqueta de Pinterest y API de Conversiones > Estadísticas en Vivo / Puntuación de Salud / Entrenador de Calidad de Datos)

Este controlador impulsa las secciones dinámicas e interactivas dentro de la página de configuración principal del módulo, específicamente para funciones como Estadísticas en Vivo, Puntuación de Salud y Entrenador de Calidad de Datos.

- **Nombre de la Pantalla y Ubicación del Menú:** Estos no son elementos de menú independientes, sino paneles interactivos dentro de la página de configuración principal del módulo (Back Office > Módulos > Gestor de Módulos > Configurar "Etiqueta de Pinterest y API de Conversiones").
- **Acciones y Configuraciones Disponibles:** Este controlador maneja las solicitudes AJAX para obtener y mostrar datos e informes en tiempo real.
  - **Estadísticas en Vivo**: Muestra un feed en tiempo real de eventos (por ejemplo, PageView, AddToCart, Purchase) a medida que se envían a Pinterest, incluyendo si se enviaron a través de la Etiqueta, CAPI o ambos. Esto le permite verificar rápidamente que los eventos se están activando.
  - **Puntuación de Salud**: Muestra un resumen del estado de su configuración de seguimiento, destacando áreas de mejora (por ejemplo, token CAPI faltante, baja calidad de coincidencia de eventos).
  - **Entrenador de Calidad de Datos**: Ofrece recomendaciones específicas para mejorar la calidad de los datos enviados a Pinterest, como asegurarse de que se incluyan todos los parámetros requeridos para cada tipo de evento.
  - **Doctor de Catálogo**: Analiza su feed de catálogo de productos (si usa uno para Pinterest) y señala posibles problemas que podrían obstaculizar los anuncios de productos dinámicos.
- **Efecto de los cambios:** La interacción con estos paneles (por ejemplo, actualizar las Estadísticas en Vivo) activa llamadas AJAX que obtienen los datos más recientes de su servidor o de la API de Pinterest, proporcionando información actualizada sin recargar toda la página.
- **Flujo de trabajo recomendado para la gestión diaria de la tienda:** Revise regularmente la Puntuación de Salud y el Entrenador de Calidad de Datos para asegurarse de que su seguimiento siga siendo óptimo. Utilice las Estadísticas en Vivo durante las pruebas o después de realizar cambios para verificar que los eventos se están activando correctamente.

#### 2.2.2 index.php (mypinterest/controllers/admin/index.php)

Este archivo es un marcador de posición y generalmente sirve como medida de seguridad para evitar la lista directa de directorios en las carpetas de administración de PrestaShop. No representa una pantalla configurable ni una entidad gestionada en sí misma.

### 2.3 Tabla de Referencia Rápida de Configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| Configuración del Módulo | ID de la Etiqueta de Pinterest | Su ID de Etiqueta | Vincula su tienda a su cuenta de anuncios de Pinterest para el seguimiento. |
| Configuración del Módulo | Modo de Seguimiento | Ambos (Híbrido) | Envía datos a través del navegador (Etiqueta) y el servidor (CAPI) para máxima fiabilidad. |
| Configuración del Módulo | Token de Acceso a la API de Conversiones | Su Token CAPI | Autentica el envío de datos del lado del servidor a Pinterest. |
| Configuración del Módulo | Habilitar Coincidencia Mejorada para CAPI | SÍ | Mejora la precisión de la coincidencia de eventos en Pinterest para una mejor segmentación. |
| Configuración del Módulo | Integrar con Módulo de Consentimiento de Cookies | SÍ (si aplica) | Asegura que el seguimiento de Pinterest respete las opciones de privacidad del cliente. |
| Configuración del Módulo | Habilitar Modo Depuración | NO (en tienda en vivo) | Muestra información de seguimiento detallada en la consola del navegador para pruebas. |
| Configuración del Módulo | Dominios de Enlace | Vacío (a menos que sea necesario) | Mantiene la continuidad del seguimiento en múltiples dominios relacionados. |
| Panel de Estadísticas en Vivo | N/A | N/A | Muestra eventos de Pinterest en tiempo real para verificación. |
| Panel de Puntuación de Salud | N/A | N/A | Proporciona una evaluación general de la calidad de su configuración de seguimiento. |
| Panel de Entrenador de Calidad de Datos | N/A | N/A | Ofrece recomendaciones para mejorar la precisión de los datos de eventos. |
| Panel de Doctor de Catálogo | N/A | N/A | Identifica problemas en su catálogo de productos para anuncios de Pinterest. |

## 3. Solución de Problemas del Comerciante y Preguntas Frecuentes (FAQ)

**P1: He instalado el módulo, pero no veo ningún dato en mi Administrador de Anuncios de Pinterest. ¿Qué debo hacer?**
R1: Primero, verifique que su **ID de la Etiqueta de Pinterest** y el **Token de Acceso a la API de Conversiones** (si usa CAPI) estén correctamente introducidos en la configuración del módulo. Asegúrese de que no haya errores tipográficos. A continuación, borre la caché de PrestaShop (**Parámetros Avanzados > Rendimiento > Borrar caché**). Luego, visite el front office de su tienda y realice algunas acciones (ver un producto, añadir al carrito, completar una compra de prueba). Si tiene el "Modo Depuración" habilitado en el módulo, revise la consola de desarrollador de su navegador para ver los eventos de Pinterest. Si aún no hay datos, verifique la configuración de su Administrador de Anuncios de Pinterest y asegúrese de que su cuenta esté activa.

**P2: Mi Etiqueta de Pinterest parece estar bloqueada por los bloqueadores de anuncios. ¿Cómo puedo asegurarme de que mis datos sigan siendo recopilados?**
R2: ¡Precisamente por eso la API de Conversiones (CAPI) es tan importante! Asegúrese de que su "Modo de Seguimiento" esté configurado en **"Ambos (Híbrido con Deduplicación)"**. De esta manera, incluso si la Etiqueta de Pinterest del lado del navegador está bloqueada, su servidor PrestaShop seguirá enviando los datos del evento directamente a Pinterest a través de la API de Conversiones, asegurando que su seguimiento siga siendo robusto.

**P3: ¿Cómo maneja este módulo la privacidad del cliente y el RGPD/CCPA?**
R3: El módulo incluye una opción para **"Integrar con Módulo de Consentimiento de Cookies"**. Si tiene un módulo de consentimiento de cookies separado instalado (lo cual es muy recomendable para el cumplimiento de la privacidad), habilite esta configuración. El seguimiento de Pinterest solo se activará una vez que el cliente haya dado su consentimiento a través de su solución de consentimiento existente. El módulo también cifra los datos sensibles del cliente antes de enviarlos a través de la Coincidencia Mejorada para CAPI, añadiendo otra capa de privacidad.

**P4: Estoy viendo una "Puntuación de Salud" baja o advertencias en el "Entrenador de Calidad de Datos". ¿Qué significan?**
R4: Estas secciones están diseñadas para ayudarle a optimizar su seguimiento. Una Puntuación de Salud baja o advertencias suelen indicar que algunos parámetros de datos pueden faltar o estar formateados incorrectamente, o que su configuración no está completamente optimizada (por ejemplo, CAPI no habilitado). Revise las recomendaciones específicas proporcionadas en los paneles "Entrenador de Calidad de Datos" y "Doctor de Catálogo". Le guiarán sobre cómo mejorar la calidad de sus datos, lo que impacta directamente en la efectividad de sus anuncios de Pinterest.

**P5: ¿Este módulo ralentizará mi sitio web?**
R5: El módulo está diseñado para ser altamente optimizado. La Etiqueta de Pinterest del lado del navegador se carga de forma asíncrona, lo que significa que no bloquea la carga de su página. Las llamadas a la API de Conversiones del lado del servidor ocurren en segundo plano y no afectan los tiempos de carga de la página del front office. No debería experimentar ninguna ralentización notable debido a este módulo.

## 4. Guía para Desarrolladores y Webmasters (Arquitectura Técnica y Mapa de Código)

### 4.1 Visión General de la Arquitectura

El módulo `Etiqueta de Pinterest y API de Conversiones` (`mypinterest`) implementa una estrategia de seguimiento híbrida para Pinterest, combinando la Etiqueta de Pinterest tradicional del lado del navegador con la API de Conversiones (CAPI) del lado del servidor. Sigue el patrón MVC de PrestaShop cuando es aplicable, aprovechando los hooks para la inyección de eventos en el front office y los controladores de administración dedicados para la configuración y los informes de datos. Los componentes arquitectónicos clave incluyen:

- **Fábrica de Rastreadores**: Instancia dinámicamente el mecanismo de seguimiento apropiado (Etiqueta, CAPI o Híbrido) basándose en la configuración del módulo.
- **Mapeo de Eventos**: Traduce los eventos internos de PrestaShop (por ejemplo, `actionCartSave`, `actionValidateOrder`) a los nombres y parámetros de eventos estándar de Pinterest.
- **Herramientas de Calidad de Datos**: Clases dedicadas para la puntuación de salud, el diagnóstico del catálogo y el entrenamiento de calidad de datos, proporcionando información útil en el back office.
- **Gestión de Consentimiento**: Integración con módulos de consentimiento de cookies de terceros para garantizar el cumplimiento del RGPD/CCPA.
- **Estadísticas en Vivo**: Monitoreo de eventos en tiempo real a través de AJAX para depuración y verificación.

### 4.2 Controladores (`controllers/`)

#### Controladores del Front-Office

- `controllers/front/ajax.php`
  - **Nombre de la clase y clase padre**: `MypinterestAjaxModuleFrontController` extiende `ModuleFrontController`.
  - **Responsabilidad**: Maneja las solicitudes AJAX del front office, principalmente para enviar eventos del lado del servidor (CAPI) que se activan por acciones del lado del cliente pero que necesitan ser procesados de forma segura en el servidor. Esto puede incluir eventos que son difíciles de rastrear puramente del lado del cliente o para fines de deduplicación. Probablemente recibe datos de eventos de `mypinterest.js` y los envía al cliente CAPI.
- `controllers/front/cron.php`
  - **Nombre de la clase y clase padre**: `MypinterestCronModuleFrontController` extiende `ModuleFrontController`.
  - **Responsabilidad**: Proporciona un punto final para un trabajo cron. Esto podría usarse para tareas como el envío de eventos CAPI diferidos, la sincronización de catálogos de productos o la realización de comprobaciones periódicas de la calidad de los datos sin interacción directa del usuario.
- `controllers/front/index.php`
  - **Nombre de la clase y clase padre**: `MypinterestIndexModuleFrontController` extiende `ModuleFrontController`.
  - **Responsabilidad**: Un controlador frontal de marcador de posición, típicamente utilizado para evitar la lista directa de directorios o como un respaldo para rutas específicas del módulo que no encajan en otros controladores. En este módulo, probablemente tiene un propósito mínimo o redirige.

#### Controladores de Administración del Back-Office

- `controllers/admin/AdminMypinterestAjaxController.php`
  - **Nombre de la clase y clase padre**: `AdminMypinterestAjaxController` extiende `ModuleAdminController`.
  - **Nombre de la pestaña y entidad gestionada**: Este controlador no se expone directamente como una pestaña de menú, sino que sirve como un punto final AJAX para la página de configuración del módulo. Maneja las solicitudes de datos dinámicos mostrados en los paneles "Estadísticas en Vivo", "Puntuación de Salud", "Entrenador de Calidad de Datos" y "Doctor de Catálogo" dentro de la configuración principal del módulo. Obtiene registros de eventos en tiempo real, métricas de salud e informes de diagnóstico.
- `controllers/admin/index.php`
  - **Nombre de la clase y clase padre**: No es un controlador funcional.
  - **Nombre de la pestaña y entidad gestionada**: Este es un marcador de posición de seguridad, que evita la lista de directorios.

### 4.3 Clases y Modelos Principales (`classes/`)

- `classes/autoload.php`: Archivo de carga automática estándar de PrestaShop, que garantiza que las clases del módulo se carguen correctamente.
- `classes/MypinterestCapiClient.php`:
  - **Tabla de base de datos**: Ninguna directamente.
  - **Extiende**: No `ObjectModel`.
  - **Métodos públicos clave**: Maneja las solicitudes HTTP reales al punto final de la API de Conversiones de Pinterest. Encapsula la lógica para construir cargas útiles de CAPI, incluyendo datos de eventos, datos de usuario y tokens de acceso.
- `classes/MypinterestCapiTracker.php`:
  - **Tabla de base de datos**: Ninguna.
  - **Extiende**: Implementa `MypinterestTrackerInterface`.
  - **Métodos públicos clave**: Gestiona la lógica para rastrear eventos específicamente a través de la API de Conversiones. Formatea los datos para CAPI, maneja la deduplicación de eventos (`event_id`) y delega el envío a `MypinterestCapiClient`.
- `classes/MypinterestCatalogDoctor.php`:
  - **Tabla de base de datos**: Ninguna.
  - **Extiende**: No `ObjectModel`.
  - **Métodos públicos clave**: Contiene lógica para analizar datos de productos (por ejemplo, de feeds de productos u objetos `Product`) e identificar posibles problemas que podrían afectar la capacidad de Pinterest para hacer coincidir productos para anuncios dinámicos. Proporciona informes de diagnóstico.
- `classes/MypinterestConsent.php`:
  - **Tabla de base de datos**: Ninguna.
  - **Extiende**: No `ObjectModel`.
  - **Métodos públicos clave**: Gestiona la integración con módulos de consentimiento de cookies de terceros. Comprueba el estado de consentimiento del usuario y determina si el seguimiento de Pinterest debe habilitarse o deshabilitarse según el consentimiento.
- `classes/MypinterestCurrencyHelper.php`:
  - **Tabla de base de datos**: Ninguna.
  - **Extiende**: No `ObjectModel`.
  - **Métodos públicos clave**: Clase de utilidad para manejar el formato y la conversión de moneda, asegurando que los eventos de Pinterest envíen valores de moneda en el formato correcto.
- `classes/MypinterestDataQualityCoach.php`:
  - **Tabla de base de datos**: Ninguna.
  - **Extiende**: No `ObjectModel`.
  - **Métodos públicos clave**: Analiza la calidad de los datos de eventos que se envían (por ejemplo, presencia de parámetros requeridos, tipos de datos correctos) y proporciona recomendaciones para mejorar.
- `classes/MypinterestEventId.php`:
  - **Tabla de base de datos**: Ninguna.
  - **Extiende**: No `ObjectModel`.
  - **Métodos públicos clave**: Genera y gestiona valores `event_id` únicos para la deduplicación de eventos, crucial para el seguimiento híbrido.
- `classes/MypinterestEventMap.php`:
  - **Tabla de base de datos**: Ninguna.
  - **Extiende**: No `ObjectModel`.
  - **Métodos públicos clave**: Define el mapeo entre las acciones/datos de PrestaShop y los nombres de eventos estándar de Pinterest y sus parámetros requeridos/recomendados.
- `classes/MypinterestEvents.php`:
  - **Tabla de base de datos**: Ninguna.
  - **Extiende**: No `ObjectModel`.
  - **Métodos públicos clave**: Centraliza la lógica para activar y gestionar varios eventos de Pinterest (PageView, AddToCart, Purchase, etc.) en todo el módulo.
- `classes/MypinterestHealthScore.php`:
  - **Tabla de base de datos**: Ninguna.
  - **Extiende**: No `ObjectModel`.
  - **Métodos públicos clave**: Calcula una "puntuación de salud" general para la configuración de seguimiento de Pinterest basándose en varios factores como la presencia del token CAPI, el modo de seguimiento y la calidad de los datos.
- `classes/MypinterestHybridTracker.php`:
  - **Tabla de base de datos**: Ninguna.
  - **Extiende**: Implementa `MypinterestTrackerInterface`.
  - **Métodos públicos clave**: Orquesta el seguimiento cuando se selecciona el modo "Ambos". Llama tanto a `MypinterestTagTracker` como a `MypinterestCapiTracker`, asegurando que `event_id` sea consistente para la deduplicación.
- `classes/MypinterestLiveStats.php`:
  - **Tabla de base de datos**: Almacena registros de eventos recientes (por ejemplo, en `ps_configuration` o una tabla personalizada).
  - **Extiende**: No `ObjectModel`.
  - **Métodos públicos clave**: Registra y recupera eventos recientes de Pinterest para mostrarlos en el panel "Estadísticas en Vivo" en el back office.
- `classes/MypinterestProductIdResolver.php`:
  - **Tabla de base de datos**: Ninguna.
  - **Extiende**: No `ObjectModel`.
  - **Métodos públicos clave**: Ayuda a resolver y formatear los ID de producto para que coincidan con los requisitos del catálogo de Pinterest, asegurando una coincidencia precisa del producto para anuncios dinámicos.
- `classes/MypinterestPropertyRules.php`:
  - **Tabla de base de datos**: Ninguna.
  - **Extiende**: No `ObjectModel`.
  - **Métodos públicos clave**: Define reglas y validaciones para las propiedades de los eventos de Pinterest, asegurando que los datos enviados a Pinterest se adhieran a sus especificaciones.
- `classes/MypinterestTagTracker.php`:
  - **Tabla de base de datos**: Ninguna.
  - **Extiende**: Implementa `MypinterestTrackerInterface`.
  - **Métodos públicos clave**: Gestiona la lógica para inyectar el script de la Etiqueta de Pinterest del lado del navegador y activar eventos a través de llamadas `pintrk()`.
- `classes/MypinterestTrackerFactory.php`:
  - **Tabla de base de datos**: Ninguna.
  - **Extiende**: No `ObjectModel`.
  - **Métodos públicos clave**: Una clase de patrón de fábrica responsable de crear y devolver la instancia de rastreador correcta (`MypinterestTagTracker`, `MypinterestCapiTracker` o `MypinterestHybridTracker`) basándose en la configuración del módulo.
- `classes/MypinterestTrackerInterface.php`:
  - **Tabla de base de datos**: Ninguna.
  - **Extiende**: No `ObjectModel`.
  - **Métodos públicos clave**: Define la interfaz común para todos los rastreadores de Pinterest, asegurando la coherencia en cómo se manejan los eventos, independientemente del método de seguimiento subyacente.
- `classes/MypinterestUserData.php`:
  - **Tabla de base de datos**: Ninguna.
  - **Extiende**: No `ObjectModel`.
  - **Métodos públicos clave**: Recopila y formatea datos del cliente (correo electrónico, teléfono, dirección, etc.) para la "Coincidencia Mejorada", asegurando que estén cifrados y cumplan con los requisitos de Pinterest.

### 4.4 Activos JavaScript (`views/js/`)

- `mypinterest/views/js/mypinterest-admin.js`:
  - **Alcance**: Back-office.
  - **Descripción**: Contiene JavaScript para la interfaz de administración del módulo. Maneja las llamadas AJAX a `AdminMypinterestAjaxController` para obtener estadísticas en vivo, puntuaciones de salud y otro contenido dinámico. Gestiona las interacciones de la interfaz de usuario en la página de configuración.
- `mypinterest/views/js/mypinterest-debug.js`:
  - **Alcance**: Front-office.
  - **Descripción**: Se carga cuando el "Modo Depuración" está habilitado. Proporciona registro en la consola y superposiciones visuales para mostrar los datos de eventos de Pinterest a medida que se envían, lo que ayuda en la solución de problemas y la verificación.
- `mypinterest/views/js/mypinterest-ghost.js`:
  - **Alcance**: Front-office.
  - **Descripción**: Potencialmente relacionado con el seguimiento "fantasma" o diferido, o un mecanismo de respaldo para eventos que podrían no activarse inmediatamente. Podría usarse para tipos de eventos específicos o retrasos relacionados con el consentimiento.
- `mypinterest/views/js/mypinterest-live.js`:
  - **Alcance**: Back-office.
  - **Descripción**: Específicamente para el panel "Estadísticas en Vivo". Gestiona la actualización en tiempo real de los registros de eventos, consultando al servidor a través de AJAX para mostrar los eventos recientes de Pinterest.
- `mypinterest/views/js/mypinterest-tcf.js`:
  - **Alcance**: Front-office.
  - **Descripción**: Maneja la integración con módulos de consentimiento de cookies compatibles con el Marco de Transparencia y Consentimiento (TCF). Escucha los eventos de consentimiento y habilita/deshabilita el seguimiento de Pinterest en consecuencia.
- `mypinterest/views/js/mypinterest-wizard.js`:
  - **Alcance**: Back-office.
  - **Descripción**: Impulsa la funcionalidad del asistente de configuración dentro de la configuración del módulo. Guía al comerciante a través de los pasos de configuración inicial, validando las entradas y proporcionando retroalimentación.
- `mypinterest/views/js/mypinterest.js`:
  - **Alcance**: Front-office.
  - **Descripción**: El JavaScript principal del front office para la Etiqueta de Pinterest. Inyecta la biblioteca `pintrk()`, inicializa la Etiqueta de Pinterest con el ID de la Etiqueta y activa eventos estándar (PageView, AddToCart, Checkout, Purchase) basándose en eventos DOM o hooks de JavaScript de PrestaShop. También es responsable de generar `event_id` para la deduplicación y potencialmente enviar llamadas AJAX a `controllers/front/ajax.php` para eventos CAPI.

### 4.5 Hojas de Estilo CSS (`views/css/`)

- `mypinterest/views/css/mypinterest-admin.css`:
  - **Alcance**: Estilo del formulario de administración del back office.
  - **Descripción**: Estilos para la página de configuración del módulo, incluyendo el diseño de pestañas, campos de entrada, botones y los paneles dinámicos para Estadísticas en Vivo, Puntuación de Salud, etc.
  - **Selectores de clase CSS clave**: `.mypinterest-config`, `.mypinterest-tab-content`, `.mypinterest-health-score`, `.mypinterest-live-stats`.
- `mypinterest/views/css/mypinterest-debug.css`:
  - **Alcance**: Estilo del cliente del front office (solo cuando el modo de depuración está activo).
  - **Descripción**: Proporciona estilo para la superposición de depuración o la salida de la consola, haciendo que la información de depuración sea más legible para los desarrolladores.

### 4.6 Estructura de Plantillas Smarty (`views/templates/`)

#### Plantillas de Hook (`views/templates/hook/`)

- `mypinterest/views/templates/hook/capi-pageview.tpl`:
  - **Hook**: Probablemente `displayHeader` o `displayFooter`.
  - **Salida**: Renderiza un elemento oculto o un pequeño script para activar un evento PageView del lado del servidor a través de CAPI, a menudo utilizado para el seguimiento de la carga inicial de la página o como respaldo.
- `mypinterest/views/templates/hook/debug.tpl`:
  - **Hook**: `displayHeader` o `displayFooter` (renderizado condicionalmente).
  - **Salida**: Inyecta el script `mypinterest-debug.js` y potencialmente una estructura HTML de superposición de depuración cuando el modo de depuración está activo.
- `mypinterest/views/templates/hook/displayOrderConfirmation.tpl`:
  - **Hook**: `displayOrderConfirmation`.
  - **Salida**: Renderiza el script del evento "Purchase" de Pinterest, incluyendo detalles del pedido (valor, moneda, ID del pedido, productos) tanto para la Etiqueta de Pinterest como para CAPI (a través de una llamada AJAX).
- `mypinterest/views/templates/hook/ghost.tpl`:
  - **Hook**: `displayHeader` o `displayFooter`.
  - **Salida**: Potencialmente relacionado con el script `mypinterest-ghost.js`, utilizado para mecanismos de seguimiento específicos, posiblemente diferidos o en segundo plano.
- `mypinterest/views/templates/hook/header.tpl`:
  - **Hook**: `displayHeader`.
  - **Salida**: Inyecta el código base principal de la Etiqueta de Pinterest (`pintrk()`) y el script `mypinterest.js`. Inicializa la Etiqueta de Pinterest con el ID de la Etiqueta y potencialmente activa el evento "PageView" inicial.
- `mypinterest/views/templates/hook/payment.tpl`:
  - **Hook**: `displayPayment` o `displayPaymentTop`.
  - **Salida**: Podría usarse para rastrear el inicio del proceso de pago o la selección de un método de pago, activando potencialmente un evento "Checkout" o "InitiateCheckout".
- `mypinterest/views/templates/hook/product-details.tpl`:
  - **Hook**: `displayProductButtons` o `displayFooterProduct`.
  - **Salida**: Renderiza JavaScript para rastrear eventos "ViewContent" cuando se carga una página de producto, incluyendo ID de producto, nombre, precio y categoría. También es probable que incluya lógica para eventos "Add To Cart".

#### Plantillas de Administración (`views/templates/admin/`)

- `mypinterest/views/templates/admin/consent-guide.tpl`: Muestra información y orientación sobre la integración con módulos de consentimiento de cookies.
- `mypinterest/views/templates/admin/doctor.tpl`: Renderiza el panel "Doctor de Catálogo", mostrando diagnósticos para los datos del catálogo de productos.
- `mypinterest/views/templates/admin/dq.tpl`: Renderiza el panel "Entrenador de Calidad de Datos", proporcionando recomendaciones para mejorar los datos de eventos.
- `mypinterest/views/templates/admin/health.tpl`: Renderiza el panel "Puntuación de Salud", mostrando la salud general del seguimiento.
- `mypinterest/views/templates/admin/linker-domains.tpl`: Plantilla para el campo de entrada "Dominios de Enlace".
- `mypinterest/views/templates/admin/live-maintain.tpl`: Posiblemente un mensaje de mantenimiento o estado para la función de estadísticas en vivo.
- `mypinterest/views/templates/admin/live.tpl`: Renderiza el panel "Estadísticas en Vivo", mostrando registros de eventos en tiempo real.
- `mypinterest/views/templates/admin/mode-context.tpl`: Proporciona información contextual sobre el modo de seguimiento seleccionado.
- `mypinterest/views/templates/admin/mode-note-both.tpl`: Nota/explicación específica para el modo de seguimiento "Ambos (Híbrido)".
- `mypinterest/views/templates/admin/mode-note-capi.tpl`: Nota/explicación específica para el modo de seguimiento "API de Conversiones".
- `mypinterest/views/templates/admin/mode-note-tag.tpl`: Nota/explicación específica para el modo de seguimiento "Etiqueta de Pinterest".
- `mypinterest/views/templates/admin/mode-picker.tpl`: Renderiza los botones de radio o el desplegable para seleccionar el "Modo de Seguimiento".
- `mypinterest/views/templates/admin/properties-list.tpl`: Muestra una lista de propiedades de eventos y su estado (por ejemplo, requerido, recomendado).
- `mypinterest/views/templates/admin/recent-events.tpl`: Renderiza una tabla o lista de eventos recientes para el panel "Estadísticas en Vivo".
- `mypinterest/views/templates/admin/tabs.tpl`: Renderiza la estructura de navegación por pestañas para la página de configuración del módulo.
- `mypinterest/views/templates/admin/tag-chips.tpl`: Probablemente para mostrar los ID de la Etiqueta de Pinterest en un formato visualmente atractivo de "chips".
- `mypinterest/views/templates/admin/tag-ids.tpl`: Renderiza los campos de entrada para el ID de la Etiqueta de Pinterest y el Token de Acceso a CAPI.
- `mypinterest/views/templates/admin/wizard.tpl`: Renderiza la interfaz del asistente de configuración paso a paso.

#### Plantillas del Front-office (`views/templates/front/`)

- `mypinterest/views/templates/front/index.tpl`: Una plantilla de marcador de posición, probablemente no utilizada para la renderización directa, sino como predeterminada para el `MypinterestIndexModuleFrontController`.

### 4.7 Esquema de Base de Datos y Mapa de Hooks

- **Tablas de Base de Datos**:

  - El módulo utiliza principalmente `ps_configuration` para almacenar su configuración (por ejemplo, `MYPINTEREST_TAG_ID`, `MYPINTEREST_TRACKING_MODE`, `MYPINTEREST_CAPI_TOKEN`).
  - También puede usar una tabla personalizada (por ejemplo, `ps_mypinterest_events_log`) para almacenar datos de eventos recientes para la función "Estadísticas en Vivo", aunque esto también podría almacenarse en `ps_configuration` como datos serializados. (No se encontraron archivos SQL explícitos, por lo que probablemente `ps_configuration` o creación dinámica de tablas).
- **Tabla de Hooks Registrados**:

| Nombre del Hook | Momento de Ejecución | Propósito Técnico |
| --- | --- | --- |
| `displayHeader` | En la sección `<head>` de cada página. | Inyecta el JavaScript base de la Etiqueta de Pinterest, `mypinterest.js`, y potencialmente los eventos iniciales de PageView. |
| `displayOrderConfirmation` | En la página de confirmación del pedido después de una compra exitosa. | Activa el evento "Purchase", enviando datos detallados del pedido y del producto a Pinterest. |
| `displayProductButtons` | En la página del producto, cerca del botón "Añadir al Carrito". | Inyecta JavaScript para rastrear eventos "ViewContent" y eventos "Add To Cart". |
| `displayFooter` | Al final de la sección `<body>` de cada página. | Puede usarse como una ubicación alternativa o adicional para inyectar scripts, especialmente para eventos que no necesitan bloquear la renderización de la página. |
| `actionCartSave` | Cuando se actualiza un carrito (por ejemplo, se añade/elimina un producto). | Activa eventos "AddToCart" o "RemoveFromCart", a menudo manejados del lado del servidor a través de CAPI o del lado del cliente a través de AJAX. |
| `actionValidateOrder` | Después de que un pedido ha sido validado con éxito. | Activa el evento "Purchase" del lado del servidor a través de CAPI para una máxima fiabilidad, complementando el evento `displayOrderConfirmation` del lado del cliente. |
| `actionFrontControllerSetMedia` | Cuando un controlador frontal está configurando sus medios (JS/CSS). | Permite que el módulo registre sus archivos JavaScript y CSS del front office. |
| `actionAdminControllerSetMedia` | Cuando un controlador de administración está configurando sus medios (JS/CSS). | Permite que el módulo registre sus archivos JavaScript y CSS del back office. |
| `actionObjectProductUpdateAfter` / `actionObjectProductAddAfter` | Después de que un producto es actualizado o añadido. | Potencialmente utilizado para actualizar datos del catálogo de productos o activar diagnósticos del catálogo. |
| `actionObjectProductDeleteAfter` | Después de que un producto es eliminado. | Potencialmente utilizado para actualizar datos del catálogo de productos. |

## 5. Soporte Oficial y Actualizaciones

Para las últimas actualizaciones, correcciones de errores y soporte oficial para el módulo Etiqueta de Pinterest y API de Conversiones, consulte su cuenta de cliente en [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nuestro equipo de soporte está disponible para ayudarle con cualquier problema técnico o pregunta relacionada con la funcionalidad del módulo.
