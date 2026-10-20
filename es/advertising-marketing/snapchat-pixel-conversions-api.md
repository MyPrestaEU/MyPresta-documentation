---
title: "Píxel de Snapchat y API de Conversiones - Manual del Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop Píxel de Snapchat y API de Conversiones de MyPresta.eu."
sidebar:
  label: "Píxel de Snapchat y API de Conversiones - Manual del Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Snapchat Pixel & Conversions API en MyPresta.eu](https://mypresta.eu/modules/advertising-and-marketing/snapchat-pixel-conversions-api.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/advertising-marketing/snapchat-pixel-conversions-api/)
>
> ---


# Píxel de Snapchat y API de Conversiones

## 1. Requisitos y Compatibilidad

- **Versiones de PrestaShop Compatibles**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilidad con PHP**: PHP 7.1 - 8.5
- **Requisitos de Alojamiento**: Se requieren extensiones PHP estándar (cURL, JSON, OpenSSL). Estas suelen estar habilitadas por defecto en la mayoría de los entornos de alojamiento modernos.

## 2. Recorrido Completo por la Configuración (Cada Ajuste Agrupado por Pantalla)

### 2.1 Página de Configuración del Módulo (Back Office > Módulos > Configurar)

Esta es la pantalla de configuración principal donde configurarás tu Píxel de Snapchat y la API de Conversiones. El módulo proporciona una interfaz fácil de usar con varias secciones para guiarte a través de la configuración.

#### **1. Configuración General y Modo de Seguimiento**

-   **Modo de Seguimiento:**
    *   **Qué hace este ajuste:** Determina cómo tu tienda envía datos a Snapchat. Puedes elegir entre el lado del cliente (Píxel), el lado del servidor (API de Conversiones) o un enfoque híbrido.
    *   **Efecto de cambiar este ajuste:**
        *   *Solo Píxel:* Solo el Píxel de Snap (código JavaScript en el navegador) rastreará eventos. Esto es más simple pero más susceptible a bloqueadores de anuncios y restricciones del navegador.
        *   *Solo API de Conversiones:* Solo se utilizará el seguimiento del lado del servidor. Esto es más fiable para la privacidad y precisión de los datos, pero requiere una configuración de servidor robusta.
        *   *Híbrido (Recomendado):* Tanto el Píxel como la CAPI rastrearán eventos. El módulo deduplica automáticamente los eventos utilizando un `event_id` compartido, asegurando informes precisos y maximizando la captura de datos. Esta es generalmente la opción más robusta y recomendada.
    *   **Valor recomendado:** `Híbrido`
    *   **Escenario / ejemplo del comerciante:** Si estás empezando, "Solo Píxel" es rápido. Para publicidad seria, "Híbrido" te ofrece lo mejor de ambos mundos, asegurando que captures la mayor cantidad de datos precisos posible para la optimización de la campaña.
-   **ID del Píxel de Snap:**
    *   **Qué hace este ajuste:** Este es tu identificador único para tu Píxel de Snapchat. Le dice a Snapchat con qué cuenta publicitaria asociar los eventos rastreados.
    *   **Efecto de cambiar este ajuste:** Si es incorrecto o está vacío, no se producirá ningún seguimiento del lado del cliente, y tus anuncios de Snapchat no podrán rastrear a los visitantes del sitio web ni las conversiones.
    *   **Valor recomendado:** Tu ID del Píxel de Snap (por ejemplo, `xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx`). Puedes encontrarlo en tu Administrador de Anuncios de Snapchat.
    *   **Escenario / ejemplo del comerciante:** Has creado una cuenta publicitaria en Snapchat y necesitas vincular tu tienda a ella. Introduce el ID del Píxel proporcionado por Snapchat aquí.
-   **Token de la API de Conversiones:**
    *   **Qué hace este ajuste:** Este es un token seguro que permite a tu servidor enviar datos directamente a la API de Conversiones de Snapchat. Autentica tus solicitudes del lado del servidor.
    *   **Efecto de cambiar este ajuste:** Si es incorrecto o está vacío, no se producirá ningún seguimiento del lado del servidor. Esto significa que pierdes los beneficios de fiabilidad y privacidad mejorados de la CAPI.
    *   **Valor recomendado:** Tu Token de la API de Conversiones. Lo generas en tu Administrador de Anuncios de Snapchat.
    *   **Escenario / ejemplo del comerciante:** Para asegurar que tus datos de compra se envíen de forma fiable a Snapchat incluso si un cliente utiliza un bloqueador de anuncios, deberás configurar e introducir tu token CAPI aquí.

#### **2. Seguimiento de Eventos y Calidad de Datos**

-   **Habilitar Coincidencia Avanzada:**
    *   **Qué hace este ajuste:** Permite que el módulo envíe datos adicionales del cliente (como correo electrónico, número de teléfono, nombre) a Snapchat, de forma segura y cifrada, para mejorar la coincidencia de eventos y la creación de audiencias.
    *   **Efecto de cambiar este ajuste:**
        *   *Habilitado:* Snapchat puede hacer coincidir con mayor precisión a los visitantes del sitio web con sus perfiles de Snapchat, mejorando la segmentación de la audiencia y la atribución de anuncios.
        *   *Deshabilitado:* Se envían menos datos, lo que podría reducir la precisión de la coincidencia de audiencia y la optimización de la campaña.
    *   **Valor recomendado:** `SÍ` (a menos que tengas estrictas preocupaciones de privacidad que anulen los beneficios).
    *   **Escenario / ejemplo del comerciante:** Quieres que Snapchat sea lo más efectivo posible para encontrar clientes similares a los que ya tienes. Habilitar esto ayuda a Snapchat a identificar a los usuarios con mayor precisión.
-   **Integración de Gestión de Consentimiento:**
    *   **Qué hace este ajuste:** Se integra con módulos populares de consentimiento de cookies (por ejemplo, módulos GDPR) para asegurar que el seguimiento de Snapchat solo ocurra después de que un cliente haya dado su consentimiento explícito.
    *   **Efecto de cambiar este ajuste:**
        *   *Habilitado:* El módulo esperará el consentimiento antes de inicializar el Píxel de Snap o enviar eventos CAPI que requieran datos de usuario.
        *   *Deshabilitado:* El seguimiento ocurrirá independientemente del consentimiento del usuario, lo que podría llevar a problemas de cumplimiento de la privacidad en algunas regiones.
    *   **Valor recomendado:** `SÍ` (altamente recomendado para GDPR, CCPA y otras regulaciones de privacidad).
    *   **Escenario / ejemplo del comerciante:** Tu tienda opera en la UE y necesita cumplir con el GDPR. Habilitar esto asegura que solo rastrees a los usuarios que han aceptado tu política de cookies.
-   **Tipo de ID de Producto para Coincidencia de Catálogo:**
    *   **Qué hace este ajuste:** Especifica qué identificador de producto (por ejemplo, ID de Producto, Referencia de Producto, EAN/UPC) debe enviar el módulo a Snapchat para la coincidencia del catálogo de productos. Esto es crucial para los anuncios de productos dinámicos.
    *   **Efecto de cambiar este ajuste:** Si el tipo de ID enviado por el módulo no coincide con los ID de tu Catálogo de Productos de Snapchat, tus anuncios dinámicos no mostrarán los productos correctos.
    *   **Valor recomendado:** Elige el tipo de ID que utilizas consistentemente en tu Catálogo de Productos de Snapchat. A menudo, `ID de Producto` o `Referencia de Producto` son buenas opciones.
    *   **Escenario / ejemplo del comerciante:** Estás ejecutando anuncios de retargeting dinámicos en Snapchat. Si tu catálogo de productos utiliza la "Referencia de Producto" como identificador único, debes seleccionar "Referencia de Producto" aquí para que los anuncios muestren los productos correctos a los clientes.
-   **Habilitar Modo de Depuración:**
    *   **Qué hace este ajuste:** Activa un modo especial que muestra información detallada sobre los eventos que se envían a Snapchat directamente en la consola de desarrollador de tu navegador.
    *   **Efecto de cambiar este ajuste:**
        *   *Habilitado:* Verás comentarios en tiempo real sobre qué datos se están enviando, lo que te ayudará a solucionar problemas y verificar tu configuración. Esto es visible solo para ti (o para cualquiera con las herramientas de desarrollador abiertas).
        *   *Deshabilitado:* No se muestra información de depuración.
    *   **Valor recomendado:** `NO` para tiendas en vivo. `SÍ` durante la configuración inicial y la resolución de problemas.
    *   **Escenario / ejemplo del comerciante:** Después de instalar el módulo, quieres confirmar que los eventos de "Añadir al Carrito" se están activando correctamente. Habilitas el modo de depuración, añades un producto a tu carrito y revisas la consola para ver los detalles del evento.

#### **3. Funciones Avanzadas**

-   **Ghost Collector (Coincidencia ScCid):**
    *   **Qué hace este ajuste:** Mejora la precisión de la coincidencia de usuarios en diferentes sesiones y dispositivos creando un identificador único y anónimo (ScCid) y almacenándolo en una cookie de origen.
    *   **Efecto de cambiar este ajuste:**
        *   *Habilitado:* Mejor atribución y creación de audiencia, especialmente en escenarios donde las cookies de terceros están restringidas.
        *   *Deshabilitado:* La capacidad de Snapchat para rastrear usuarios en diferentes sesiones podría ser menos precisa.
    *   **Valor recomendado:** `SÍ`
    *   **Escenario / ejemplo del comerciante:** Un cliente visita tu tienda, se va y regresa más tarde desde un dispositivo diferente. Ghost Collector ayuda a Snapchat a reconocerlos como el mismo usuario, mejorando tus esfuerzos de retargeting.
-   **Dominios de Enlace (Seguimiento entre Dominios):**
    *   **Qué hace este ajuste:** Te permite especificar dominios adicionales (por ejemplo, un blog separado, un subdominio para productos específicos) donde también deseas rastrear eventos de Snapchat y vincular sesiones de usuario.
    *   **Efecto de cambiar este ajuste:**
        *   *Configurado:* Snapchat puede rastrear el recorrido de un usuario sin problemas entre tu tienda principal y los dominios vinculados especificados.
        *   *Vacío:* El seguimiento se limita solo al dominio de tu tienda principal.
    *   **Valor recomendado:** Déjalo vacío a menos que tengas varios dominios/subdominios que necesiten seguimiento cruzado.
    *   **Escenario / ejemplo del comerciante:** Tienes tu tienda principal en `mitienda.com` y un blog separado en `blog.mitienda.com`. Quieres rastrear a los usuarios que visitan ambos. Añadirías `blog.mitienda.com` a este ajuste.
-   **URL de Tarea Programada para Sincronización CAPI:**
    *   **Qué hace este ajuste:** Proporciona una URL única que puedes configurar como una tarea programada (cron job) en tu servidor. Esta tarea programada envía periódicamente cualquier evento del lado del servidor en cola a Snapchat, asegurando que los datos se entreguen incluso si hay problemas temporales de red.
    *   **Efecto de cambiar este ajuste:** Este es un campo de solo lectura. Configurar la tarea programada asegura una entrega fiable y asíncrona de los eventos CAPI. Si no se configura, los eventos CAPI podrían enviarse solo en tiempo real o ante acciones específicas del usuario, perdiendo potencialmente algunos datos si el envío en tiempo real falla.
    *   **Valor recomendado:** Configura una tarea programada en tu servidor para ejecutar esta URL cada 5-15 minutos.
    *   **Escenario / ejemplo del comerciante:** Para asegurar que todos tus datos de compra se envíen a Snapchat, incluso si un cliente cierra su navegador inmediatamente después de la compra, configuras una tarea programada para procesar regularmente cualquier evento CAPI pendiente.

#### **4. Calidad de Datos y Puntuación de Salud**

Esta sección suele proporcionar información y recomendaciones de solo lectura basadas en tu configuración actual y los eventos rastreados.

-   **Puntuación de Salud:**
    *   **Qué hace este ajuste:** Muestra una puntuación general que indica la calidad y la integridad de tu configuración de seguimiento de Snapchat. Una puntuación más alta significa mejores datos.
    *   **Efecto de cambiar este ajuste:** Esta es una herramienta de diagnóstico. Mejorar tu configuración (por ejemplo, habilitar CAPI, coincidencia avanzada) aumentará esta puntuación.
    *   **Valor recomendado:** Apunta a la puntuación más alta posible.
    *   **Escenario / ejemplo del comerciante:** Tu puntuación de salud es del 60%. El módulo podría sugerir habilitar la Coincidencia Avanzada para mejorarla, indicando un área potencial para una mejor calidad de datos.
-   **Asesor de Calidad de Datos:**
    *   **Qué hace este ajuste:** Ofrece recomendaciones y advertencias específicas sobre tu configuración de seguimiento, como tokens CAPI faltantes, tipos de ID de producto no configurados o posibles problemas de consentimiento.
    *   **Efecto de cambiar este ajuste:** Esta es una herramienta de diagnóstico. Abordar las recomendaciones mejorará la precisión de tu seguimiento.
    *   **Valor recomendado:** Revisa y actúa sobre todas las recomendaciones.
    *   **Escenario / ejemplo del comerciante:** El asesor te dice que tu "Tipo de ID de Producto" no coincide con tu catálogo. Luego, vuelves a la configuración y lo ajustas.
-   **Doctor de Catálogo:**
    *   **Qué hace este ajuste:** Te ayuda a diagnosticar problemas relacionados con tu catálogo de productos y cómo se está haciendo coincidir con los eventos de Snapchat. Verifica la coherencia en los identificadores de producto.
    *   **Efecto de cambiar este ajuste:** Esta es una herramienta de diagnóstico. Resolver los problemas aquí asegura que tus anuncios de productos dinámicos funcionen correctamente.
    *   **Valor recomendado:** Utiliza esta herramienta si experimentas problemas con anuncios de productos dinámicos que muestran elementos incorrectos.
    *   **Escenario / ejemplo del comerciante:** Tus anuncios dinámicos muestran productos genéricos en lugar de los que vieron los clientes. El Doctor de Catálogo podría revelar que tus ID de producto son inconsistentes.

#### **5. Estadísticas en Vivo y Eventos Recientes**

-   **Estadísticas en Vivo:**
    *   **Qué hace este ajuste:** Proporciona una visión general en tiempo real de los eventos que se envían a Snapchat (por ejemplo, Vistas de Página, Añadir al Carrito, Compras).
    *   **Efecto de cambiar este ajuste:** Esta es una herramienta de monitoreo. Te ayuda a verificar rápidamente si los eventos se están activando como se espera.
    *   **Valor recomendado:** Revisa regularmente esta sección para asegurarte de que tu seguimiento esté activo.
    *   **Escenario / ejemplo del comerciante:** Lanzas un nuevo producto y quieres ver si los eventos de "Ver Contenido" se están rastreando inmediatamente. Revisas las estadísticas en vivo.
-   **Registro de Eventos Recientes:**
    *   **Qué hace este ajuste:** Muestra un registro de los eventos más recientes enviados a Snapchat, incluyendo detalles como el tipo de evento, la marca de tiempo y si se envió a través de Píxel o CAPI.
    *   **Efecto de cambiar este ajuste:** Esta es una herramienta de registro detallada para verificación y resolución de problemas.
    *   **Valor recomendado:** Utilízala para profundizar en eventos específicos si sospechas un problema.
    *   **Escenario / ejemplo del comerciante:** Un cliente informa un problema con una compra, y quieres confirmar si el evento de "Compra" se envió correctamente a Snapchat para ese pedido.

### 2.2 Pantallas de Administración Dedicadas y Vistas de Controlador

#### **AdminMysnapapiAjaxController (Back Office > Módulos > Píxel de Snapchat y API de Conversiones > [Llamadas AJAX Internas])**

Este controlador no es directamente accesible a través de un elemento de menú, pero maneja las solicitudes AJAX en segundo plano desde la página de configuración del módulo. Es responsable de:

-   **Nombre de la Pantalla y Ubicación del Menú:** No es directamente visible en el menú. Procesa las solicitudes iniciadas desde la página de configuración principal del módulo.
-   **Acciones y Configuraciones Disponibles:** Gestiona la carga dinámica de datos para las secciones "Estadísticas en Vivo", "Eventos Recientes", "Puntuación de Salud", "Asesor de Calidad de Datos" y "Doctor de Catálogo". También maneja el guardado de configuraciones específicas sin una recarga completa de la página.
-   **Efecto de los cambios:** Cuando interactúas con elementos dinámicos en la página de configuración principal (por ejemplo, actualizando estadísticas en vivo, guardando una subconfiguración específica), este controlador procesa la solicitud y actualiza la información mostrada o guarda los datos.
-   **Flujo de trabajo recomendado para la gestión diaria de la tienda:** Los comerciantes no interactúan directamente con este controlador. Su funcionalidad está incrustada dentro de la página de configuración principal del módulo.

#### **index.php (mysnapapi/controllers/admin/index.php)**

Este archivo es un marcador de posición y normalmente no contiene funcionalidad directa ni una interfaz de usuario. En PrestaShop, los archivos `index.php` dentro de los directorios de controladores a menudo sirven para evitar la lista de directorios en lugar de proporcionar una lógica de controlador específica.

-   **Nombre de la Pantalla y Ubicación del Menú:** No es una pantalla directa.
-   **Acciones y Configuraciones Disponibles:** Ninguna.
-   **Efecto de los cambios:** No hay interacción o efecto directo del comerciante.
-   **Flujo de trabajo recomendado para la gestión diaria de la tienda:** No se requiere interacción.

### 2.3 Tabla de Referencia Rápida de Configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| **Página de Configuración del Módulo** | Modo de Seguimiento | Híbrido | Define cómo se envían los datos (Píxel, CAPI o ambos). Híbrido es el más robusto. |
| | ID del Píxel de Snap | Tu ID de Píxel | ID único para el seguimiento del lado del cliente. Esencial para el Píxel. |
| | Token de la API de Conversiones | Tu Token CAPI | Token seguro para el seguimiento del lado del servidor. Esencial para CAPI. |
| | Habilitar Coincidencia Avanzada | SÍ | Mejora la coincidencia de usuarios para una mejor segmentación de anuncios. |
| | Integración de Gestión de Consentimiento | SÍ | Garantiza el cumplimiento de la privacidad al respetar el consentimiento del usuario. |
| | Tipo de ID de Producto para Coincidencia de Catálogo | ID de Producto / Referencia | Coincide los identificadores de producto para anuncios dinámicos. |
| | Habilitar Modo de Depuración | NO (SÍ para la configuración) | Muestra información de seguimiento en la consola del navegador para solucionar problemas. |
| | Ghost Collector (Coincidencia ScCid) | SÍ | Mejora la coincidencia de usuarios entre sesiones/dispositivos. |
| | Dominios de Enlace | Vacío (o tus dominios) | Habilita el seguimiento entre dominios para múltiples sitios relacionados. |
| | URL de Tarea Programada para Sincronización CAPI | (Solo lectura) | URL para la entrega de eventos del lado del servidor, configurada como una tarea programada. |
| | Puntuación de Salud | (Diagnóstico) | Calidad general de tu configuración de seguimiento. Apunta a una puntuación alta. |
| | Asesor de Calidad de Datos | (Diagnóstico) | Recomendaciones específicas para mejorar la calidad de los datos. |
| | Doctor de Catálogo | (Diagnóstico) | Diagnostica problemas con la coincidencia del catálogo de productos. |
| | Estadísticas en Vivo | (Monitoreo) | Visión general en tiempo real de los eventos rastreados. |
| | Registro de Eventos Recientes | (Monitoreo) | Registro detallado de eventos recientes para verificación. |

## 3. Solución de Problemas del Comerciante y Preguntas Frecuentes (FAQ)

**P1: Mis anuncios de Snapchat no muestran ninguna conversión, pero sé que estoy obteniendo ventas. ¿Qué está mal?**
R1:

-   **Verifica el ID del Píxel y el Token CAPI:** Vuelve a verificar que tu ID del Píxel de Snap y el Token de la API de Conversiones estén correctamente introducidos en la configuración del módulo. Incluso un solo error tipográfico impedirá el seguimiento.
-   **Modo de Seguimiento:** Asegúrate de que estás utilizando "Híbrido" o al menos "Solo Píxel" si esperas un seguimiento del lado del cliente.
-   **Modo de Depuración:** Habilita el "Modo de Depuración" en la configuración del módulo y abre la consola de desarrollador de tu navegador (F12). Navega por tu tienda y realiza acciones (ver producto, añadir al carrito, completar una compra de prueba). Busca los eventos de Snapchat que se registran en la consola. Si no los ves, hay un problema de configuración fundamental.
-   **Borrar Caché:** Siempre borra la caché de tu PrestaShop (Parámetros Avanzados > Rendimiento) después de realizar cualquier cambio en la configuración del módulo.
-   **Bloqueadores de Anuncios:** Prueba con una ventana de navegador de incógnito/privada sin ningún bloqueador de anuncios habilitado, ya que pueden interferir con el seguimiento de píxeles.

**P2: He habilitado el módulo, pero me preocupa el cumplimiento del GDPR/CCPA. ¿Cómo ayuda este módulo?**
R2:

-   El módulo incluye una configuración de **"Integración de Gestión de Consentimiento"**. Cuando está habilitada, se integrará con tu solución de consentimiento de cookies existente (por ejemplo, un módulo GDPR). Esto significa que el seguimiento de Snapchat solo se activará *después* de que un usuario haya dado su consentimiento explícito a través del banner de consentimiento de tu tienda.
-   **Acción:** Asegúrate de que esta configuración esté habilitada y de que tengas un módulo de consentimiento de cookies funcional en tu tienda PrestaShop.

**P3: Mis anuncios de productos dinámicos en Snapchat muestran productos incorrectos o no funcionan en absoluto.**
R3:

-   **Tipo de ID de Producto:** Ve a la configuración del módulo y verifica el ajuste **"Tipo de ID de Producto para Coincidencia de Catálogo"**. Esto debe coincidir exactamente con el identificador único que estás utilizando en tu Catálogo de Productos de Snapchat (por ejemplo, si tu catálogo utiliza `reference`, selecciona `Referencia de Producto` aquí).
-   **Sincronización de Catálogo:** Asegúrate de que tu catálogo de productos esté correctamente sincronizado y actualizado en tu Administrador de Anuncios de Snapchat. El módulo envía los ID correctos, pero Snapchat necesita tener esos ID en su catálogo.
-   **Doctor de Catálogo:** Utiliza la herramienta "Doctor de Catálogo" dentro de la configuración del módulo para diagnosticar posibles inconsistencias entre los datos de productos de tu tienda y lo que Snapchat espera.

**P4: Estoy viendo eventos duplicados en mi Administrador de Anuncios de Snapchat (por ejemplo, dos eventos de "Compra" para un solo pedido).**
R4:

-   Esto suele ocurrir si estás utilizando tanto el Píxel como la CAPI sin una deduplicación adecuada.
-   **Acción:** Asegúrate de que tu "Modo de Seguimiento" esté configurado en **"Híbrido"**. Este módulo está diseñado para manejar automáticamente la deduplicación de eventos cuando se ejecuta en modo Híbrido, generando un `event_id` compartido para eventos del lado del cliente y del lado del servidor. Si estás viendo duplicados, verifica que el módulo esté correctamente configurado para el modo Híbrido y que no haya ningún otro código de seguimiento de Snapchat presente en tu sitio.

**P5: Las secciones "Estadísticas en Vivo" o "Puntuación de Salud" en la página de configuración del módulo no se actualizan o no muestran datos.**
R5:

-   **Problemas de AJAX:** Esto suele indicar un problema con la capacidad de tu servidor para procesar solicitudes AJAX o un error de JavaScript en tu back office.
-   **Consola del Navegador:** Abre la consola de desarrollador de tu navegador (F12) mientras estás en la página de configuración del módulo y busca cualquier mensaje de error en rojo en la pestaña "Consola".
-   **Registros del Servidor:** Revisa los registros de errores de PHP de tu servidor para ver si hay errores relacionados.
-   **Modo de Depuración de PrestaShop:** Habilita temporalmente el modo de depuración de PrestaShop (Parámetros Avanzados > Rendimiento > Modo de depuración: SÍ) para ver si aparecen errores más detallados.
-   **Contacta con Soporte:** Si no puedes resolverlo, recopila los mensajes de error y contacta con el soporte de MyPresta.eu.

## 4. Guía para Desarrolladores y Webmasters (Arquitectura Técnica y Mapa de Código)

Esta sección es estrictamente para desarrolladores, webmasters de tiendas y agencias técnicas que mantienen o extienden la tienda.

### 4.1 Resumen de la Arquitectura

El módulo `Píxel de Snapchat y API de Conversiones` (`mysnapapi`) implementa una solución de seguimiento robusta que aprovecha tanto el seguimiento de eventos del lado del cliente (Píxel de Snap) como del lado del servidor (API de Conversiones - CAPI). Sigue un enfoque modular y orientado a objetos, adhiriéndose al patrón MVC de PrestaShop cuando es aplicable.

Componentes arquitectónicos clave:

-   **Seguimiento Híbrido:** El módulo admite el modo solo Píxel, solo CAPI y un modo Híbrido recomendado. En el modo Híbrido, genera un `event_id` único para cada evento, compartido entre las cargas útiles del Píxel y la CAPI para garantizar la deduplicación en el lado de Snapchat.
-   **Mapeo de Eventos:** Un mapeo completo de las acciones de PrestaShop (por ejemplo, `actionCartSave`, `actionValidateOrder`) a los eventos estándar de Snapchat (`ADD_CART`, `PURCHASE`, `VIEW_CONTENT`, `PAGE_VIEW`).
-   **Gestión de Consentimiento:** Puntos de integración para módulos de consentimiento populares para garantizar el cumplimiento del GDPR/CCPA.
-   **Herramientas de Calidad de Datos:** Diagnósticos integrados como Puntuación de Salud, Asesor de Calidad de Datos y Doctor de Catálogo para ayudar en la configuración y resolución de problemas.
-   **CAPI Asíncrona:** Los eventos CAPI a menudo se ponen en cola y se envían de forma asíncrona, ya sea en tiempo real o mediante una tarea programada, para mejorar el rendimiento y la fiabilidad.
-   **Datos de Primera Parte:** Utiliza un "Ghost Collector" para crear cookies de primera parte para la coincidencia de `ScCid`, mejorando la identificación del usuario en un entorno centrado en la privacidad.

### 4.2 Controladores (`controllers/`)

#### Controladores del Front-Office

-   `mysnapapi/controllers/front/ajax.php`
    *   **Nombre de la clase y clase padre:** `MysnapapiAjaxModuleFrontController` extiende `ModuleFrontController`.
    *   **Responsabilidad:** Maneja varias solicitudes AJAX desde el front-office, principalmente para la funcionalidad "Ghost Collector" (ScCid). Podría recopilar datos de usuario anónimos o actualizar cookies de primera parte sin una recarga completa de la página.
-   `mysnapapi/controllers/front/cron.php`
    *   **Nombre de la clase y clase padre:** `MysnapapiCronModuleFrontController` extiende `ModuleFrontController`.
    *   **Responsabilidad:** Este controlador está diseñado para ser llamado por una tarea programada externa. Su función principal es procesar cualquier evento del lado del servidor (CAPI) en cola que no se envió en tiempo real. Asegura que todos los datos CAPI se entreguen finalmente a Snapchat, mejorando la fiabilidad.
-   `mysnapapi/controllers/front/index.php`
    *   **Nombre de la clase y clase padre:** `MysnapapiIndexModuleFrontController` extiende `ModuleFrontController`.
    *   **Responsabilidad:** Típicamente un marcador de posición o un punto de entrada predeterminado. Podría manejar la inicialización básica del módulo o redirigir si se accede directamente. A menudo, `index.php` en un directorio de controlador evita la lista de directorios.
-   `mysnapapi/controllers/front/sync.php`
    *   **Nombre de la clase y clase padre:** `MysnapapiSyncModuleFrontController` extiende `ModuleFrontController`.
    *   **Responsabilidad:** Probablemente maneja tareas específicas de sincronización de datos, potencialmente relacionadas con actualizaciones del catálogo de productos u otro intercambio de datos con la API de Snapchat, separado del seguimiento de eventos principal.

#### Controladores de Administración del Back-Office

-   `mysnapapi/controllers/admin/AdminMysnapapiAjaxController.php`
    *   **Nombre de la clase y clase padre:** `AdminMysnapapiAjaxController` extiende `AdminController`.
    *   **Nombre de la pestaña y entidad gestionada:** No es una pestaña de menú directa. Este controlador maneja las solicitudes AJAX que se originan en la página de configuración principal del módulo (método `getContent()` de `mysnapapi.php`). Es responsable de cargar dinámicamente datos para las diversas herramientas de diagnóstico (Estadísticas en Vivo, Puntuación de Salud, etc.) y guardar configuraciones específicas sin una recarga completa de la página.
-   `mysnapapi/controllers/admin/index.php`
    *   **Nombre de la clase y clase padre:** No es un controlador funcional.
    *   **Nombre de la pestaña y entidad gestionada:** Marcador de posición. Evita la lista de directorios.

### 4.3 Clases y Modelos Principales (`classes/`)

-   `mysnapapi/classes/autoload.php`: Archivo de carga automática estándar de PrestaShop.
-   `mysnapapi/classes/index.php`: Marcador de posición para evitar la lista de directorios.
-   `mysnapapi/classes/MysnapapiCapiClient.php`:
    *   **Interactúa con:** Punto final de la API de Conversiones de Snapchat.
    *   **Extiende ObjectModel:** No.
    *   **Métodos clave:** Maneja el envío de eventos del lado del servidor a Snapchat. Encapsula la lógica de solicitud de la API, la autenticación (usando el token CAPI) y el manejo de errores.
-   `mysnapapi/classes/MysnapapiCapiTracker.php`:
    *   **Interactúa con:** `ps_configuration` (para el token CAPI), `MysnapapiCapiClient`.
    *   **Extiende ObjectModel:** No.
    *   **Métodos clave:** Responsable de preparar y enviar datos de eventos específicamente para la API de Conversiones. Formatea las cargas útiles de eventos de acuerdo con las especificaciones CAPI de Snapchat.
-   `mysnapapi/classes/MysnapapiCatalogDoctor.php`:
    *   **Interactúa con:** Datos de productos (de los ObjectModels `Product` y `ProductSupplier`).
    *   **Extiende ObjectModel:** No.
    *   **Métodos clave:** Proporciona lógica de diagnóstico para verificar la coherencia y los problemas relacionados con los identificadores de producto utilizados para la coincidencia del catálogo (por ejemplo, `id_product`, `reference`, `ean13`).
-   `mysnapapi/classes/MysnapapiConsent.php`:
    *   **Interactúa con:** `ps_configuration` (para la configuración de consentimiento), potencialmente otros módulos de consentimiento.
    *   **Extiende ObjectModel:** No.
    *   **Métodos clave:** Gestiona el estado del consentimiento. Verifica si se requiere el consentimiento del usuario y si se ha otorgado antes de permitir que se activen los scripts de seguimiento o los eventos CAPI.
-   `mysnapapi/classes/MysnapapiCurrencyHelper.php`:
    *   **Interactúa con:** La clase `Currency` de PrestaShop.
    *   **Extiende ObjectModel:** No.
    *   **Métodos clave:** Proporciona funciones de utilidad para manejar el formato y la conversión de moneda, asegurando que los valores de los eventos se envíen en el formato y código de moneda correctos a Snapchat.
-   `mysnapapi/classes/MysnapapiDataQualityCoach.php`:
    *   **Interactúa con:** Configuración del módulo.
    *   **Extiende ObjectModel:** No.
    *   **Métodos clave:** Analiza la configuración del módulo y proporciona recomendaciones o advertencias para mejorar la calidad de los datos y la efectividad del seguimiento.
-   `mysnapapi/classes/MysnapapiEventId.php`:
    *   **Interactúa con:** Sesión, cookies.
    *   **Extiende ObjectModel:** No.
    *   **Métodos clave:** Genera y gestiona valores `event_id` únicos para cada evento rastreado. Crucial para la deduplicación cuando se utiliza el modo de seguimiento Híbrido.
-   `mysnapapi/classes/MysnapapiEventMap.php`:
    *   **Interactúa con:** N/A.
    *   **Extiende ObjectModel:** No.
    *   **Métodos clave:** Define el mapeo entre los eventos/datos internos de PrestaShop y los nombres y parámetros de eventos estándar de Snapchat.
-   `mysnapapi/classes/MysnapapiEvents.php`:
    *   **Interactúa con:** Varias clases principales de PrestaShop (por ejemplo, `Cart`, `Product`, `Order`).
    *   **Extiende ObjectModel:** No.
    *   **Métodos clave:** Clase centralizada para recopilar y formatear datos de eventos (por ejemplo, `PageView`, `ViewContent`, `AddToCart`, `Purchase`) del contexto de PrestaShop en una estructura compatible con Snapchat.
-   `mysnapapi/classes/MysnapapiHealthScore.php`:
    *   **Interactúa con:** Configuración del módulo, potencialmente datos de eventos en vivo.
    *   **Extiende ObjectModel:** No.
    *   **Métodos clave:** Calcula una "puntuación de salud" general para la configuración de seguimiento basada en las opciones configuradas y los problemas detectados.
-   `mysnapapi/classes/MysnapapiHybridTracker.php`:
    *   **Interactúa con:** `MysnapapiPixelTracker`, `MysnapapiCapiTracker`, `MysnapapiEventId`.
    *   **Extiende ObjectModel:** No.
    *   **Métodos clave:** Orquesta el seguimiento en modo "Híbrido", asegurando que tanto los eventos del Píxel como los de la CAPI se envíen con el mismo `event_id` para la deduplicación.
-   `mysnapapi/classes/MysnapapiLiveStats.php`:
    *   **Interactúa con:** Potencialmente un registro temporal de eventos recientes o datos en tiempo real.
    *   **Extiende ObjectModel:** No.
    *   **Métodos clave:** Recopila y presenta estadísticas en tiempo real sobre los eventos rastreados para el panel de administración.
-   `mysnapapi/classes/MysnapapiPixelTracker.php`:
    *   **Interactúa con:** `ps_configuration` (para el ID del Píxel).
    *   **Extiende ObjectModel:** No.
    *   **Métodos clave:** Responsable de generar el código JavaScript para el Píxel de Snap e incrustarlo en el front-office, incluyendo los datos del evento.
-   `mysnapapi/classes/MysnapapiProductIdResolver.php`:
    *   **Interactúa con:** Datos del producto.
    *   **Extiende ObjectModel:** No.
    *   **Métodos clave:** Determina el identificador de producto correcto (por ejemplo, `id_product`, `reference`, `ean13`) a utilizar según la configuración del módulo para la coincidencia del catálogo.
-   `mysnapapi/classes/MysnapapiPropertyRules.php`:
    *   **Interactúa con:** N/A.
    *   **Extiende ObjectModel:** No.
    *   **Métodos clave:** Define reglas y validaciones para las propiedades de los eventos, asegurando que los datos enviados a Snapchat se adhieran a sus especificaciones de API.
-   `mysnapapi/classes/MysnapapiTrackerFactory.php`:
    *   **Interactúa con:** Configuración del módulo (modo de seguimiento).
    *   **Extiende ObjectModel:** No.
    *   **Métodos clave:** Patrón de fábrica para instanciar la clase de seguimiento correcta (`MysnapapiPixelTracker`, `MysnapapiCapiTracker` o `MysnapapiHybridTracker`) según el modo de seguimiento configurado del módulo.
-   `mysnapapi/classes/MysnapapiTrackerInterface.php`:
    *   **Interactúa con:** N/A.
    *   **Extiende ObjectModel:** No.
    *   **Métodos clave:** Define una interfaz común para todas las clases de seguimiento, asegurando firmas de métodos consistentes para el seguimiento de eventos.
-   `mysnapapi/classes/MysnapapiUserData.php`:
    *   **Interactúa con:** Datos del cliente (del ObjectModel `Customer`), sesión, cookies.
    *   **Extiende ObjectModel:** No.
    *   **Métodos clave:** Recopila y formatea datos específicos del usuario (por ejemplo, correo electrónico, teléfono, dirección IP, agente de usuario) para una coincidencia avanzada, asegurando que los datos estén cifrados y cumplan con la normativa.

### 4.4 Activos JavaScript (`views/js/`)

-   `mysnapapi/tools/console-simulate-bo-ui.js`:
    *   **Alcance:** Back-office (herramienta de desarrollador).
    *   **Descripción:** Un script de utilidad, probablemente para desarrollo/depuración, para simular o interactuar con la interfaz de usuario del Back Office desde la consola del navegador.
-   `mysnapapi/views/js/mp-collect.js`:
    *   **Alcance:** Front-office.
    *   **Descripción:** Script principal de recopilación de datos del lado del cliente. Podría escuchar eventos DOM específicos o interacciones del usuario para activar eventos del Píxel de Snapchat.
-   `mysnapapi/views/js/mp-consent.js`:
    *   **Alcance:** Front-office.
    *   **Descripción:** Maneja la integración con los mecanismos de consentimiento de cookies. Verifica el estado del consentimiento y carga/inicializa condicionalmente el Píxel de Snapchat o el seguimiento relacionado. Puede interactuar con `prestashop.on('updateConsent')`.
-   `mysnapapi/views/js/mp-front.js`:
    *   **Alcance:** Front-office.
    *   **Descripción:** JavaScript general del front-office para el módulo. Probablemente contiene la lógica principal para inicializar el código base del Píxel de Snap, enviar eventos al objeto `snap` y manejar los disparadores de eventos del lado del cliente.
-   `mysnapapi/views/js/mp-inspect.js`:
    *   **Alcance:** Front-office (modo de depuración).
    *   **Descripción:** Se utiliza cuando el modo de depuración está habilitado. Intercepta y muestra los eventos de Snapchat en la consola del navegador, proporcionando información detallada sobre los datos que se envían.
-   `mysnapapi/views/js/mysnapapi-admin.js`:
    *   **Alcance:** Back-office.
    *   **Descripción:** JavaScript para la interfaz de administración del módulo. Maneja las interacciones del formulario, las llamadas AJAX a `AdminMysnapapiAjaxController`, las actualizaciones dinámicas de las secciones de diagnóstico (Estadísticas en Vivo, Puntuación de Salud) y los pasos del asistente.
-   `mysnapapi/views/js/mysnapapi-debug.js`:
    *   **Alcance:** Front-office (modo de depuración).
    *   **Descripción:** Similar a `mp-inspect.js`, proporciona utilidades de depuración adicionales o superposiciones visuales para que los desarrolladores verifiquen el seguimiento.
-   `mysnapapi/views/js/mysnapapi-ghost.js`:
    *   **Alcance:** Front-office.
    *   **Descripción:** Implementa la funcionalidad "Ghost Collector". Gestiona la creación y lectura de cookies de primera parte para la coincidencia de `ScCid` (ID de Clic de Snapchat), mejorando la identificación del usuario.
-   `mysnapapi/views/js/mysnapapi-live.js`:
    *   **Alcance:** Back-office.
    *   **Descripción:** Impulsa la sección "Estadísticas en Vivo" en el panel de administración, realizando llamadas AJAX para obtener y mostrar datos de eventos en tiempo real.
-   `mysnapapi/views/js/mysnapapi-tcf.js`:
    *   **Alcance:** Front-office.
    *   **Descripción:** Específicamente para la integración con soluciones de consentimiento compatibles con el Marco de Transparencia y Consentimiento (TCF), asegurando que el seguimiento de Snapchat se adhiera a las señales del TCF.
-   `mysnapapi/views/js/mysnapapi-wizard.js`:
    *   **Alcance:** Back-office.
    *   **Descripción:** Proporciona lógica interactiva para el asistente de configuración del módulo, guiando al comerciante a través de los pasos de configuración inicial.
-   `mysnapapi/views/js/mysnapapi.js`:
    *   **Alcance:** Front-office.
    *   **Descripción:** Punto de entrada principal o JavaScript de utilidad general para el front-office, que potencialmente carga otros scripts o contiene funciones globales específicas del módulo.

### 4.5 Hojas de Estilo CSS (`views/css/`)

-   `mysnapapi/views/css/mp-inspect.css`:
    *   **Alcance:** Front-office (modo de depuración).
    *   **Descripción:** Estilos para la superposición de depuración o la salida de la consola cuando `mp-inspect.js` está activo.
-   `mysnapapi/views/css/mysnapapi-admin.css`:
    *   **Alcance:** Estilo del formulario de administración del Back-office.
    *   **Descripción:** Estilos para la página de configuración del módulo, incluyendo el diseño, los botones, las secciones de diagnóstico (Puntuación de Salud, Asesor de Calidad de Datos) y los pasos del asistente.
-   `mysnapapi/views/css/mysnapapi-debug.css`:
    *   **Alcance:** Front-office (modo de depuración).
    *   **Descripción:** Estilos adicionales para elementos de depuración, potencialmente indicadores visuales o bordes para elementos rastreados.

### 4.6 Estructura de Plantillas Smarty (`views/templates/`)

#### Plantillas de Hook (`views/templates/hook/`)

-   `mysnapapi/views/templates/hook/capi-pageview.tpl`:
    *   **Hook:** Potencialmente `displayHeader` o `displayFooter` (contexto del lado del servidor).
    *   **Salida:** Renderiza un elemento oculto o una llamada del lado del servidor para activar un evento CAPI `PAGE_VIEW`, a menudo utilizado como respaldo o para la carga inicial de la página.
-   `mysnapapi/views/templates/hook/debug.tpl`:
    *   **Hook:** `displayHeader` o `displayFooter` (condicional al modo de depuración).
    *   **Salida:** Renderiza información de depuración o inicializa scripts de depuración en el front-office.
-   `mysnapapi/views/templates/hook/displayOrderConfirmation.tpl`:
    *   **Hook:** `displayOrderConfirmation`.
    *   **Salida:** Renderiza el evento `PURCHASE` del Píxel de Snap y/o activa el evento `PURCHASE` de la CAPI en la página de confirmación del pedido, pasando los detalles del pedido.
-   `mysnapapi/views/templates/hook/ghost.tpl`:
    *   **Hook:** `displayHeader` o `displayFooter`.
    *   **Salida:** Renderiza el JavaScript para el "Ghost Collector" para gestionar las cookies `ScCid`.
-   `mysnapapi/views/templates/hook/header.tpl`:
    *   **Hook:** `displayHeader`.
    *   **Salida:** La plantilla principal para inicializar el código base del Píxel de Snap, el objeto `snap` y potencialmente los eventos `PAGE_VIEW`. Carga los archivos JavaScript necesarios.
-   `mysnapapi/views/templates/hook/payment.tpl`:
    *   **Hook:** `displayPayment` o `displayPaymentTop`.
    *   **Salida:** Renderiza `INITIATE_CHECKOUT` u otros eventos relevantes durante la fase de selección de pago del proceso de compra.
-   `mysnapapi/views/templates/hook/product-details.tpl`:
    *   **Hook:** `displayProductButtons` o `displayFooterProduct`.
    *   **Salida:** Renderiza el evento `VIEW_CONTENT` del Píxel de Snap y el evento `ADD_CART` (o JS relacionado) en la página del producto, pasando datos específicos del producto.

#### Plantillas de Administración (`views/templates/admin/`)

-   `mysnapapi/views/templates/admin/consent-guide.tpl`: Muestra orientación sobre la integración con la gestión de consentimiento.
-   `mysnapapi/views/templates/admin/doctor.tpl`: Renderiza la interfaz para la herramienta de diagnóstico "Doctor de Catálogo".
-   `mysnapapi/views/templates/admin/dq.tpl`: Renderiza las recomendaciones del "Asesor de Calidad de Datos".
-   `mysnapapi/views/templates/admin/health.tpl`: Muestra la "Puntuación de Salud" y la información relacionada.
-   `mysnapapi/views/templates/admin/linker-domains.tpl`: Campo de entrada y explicación para el seguimiento entre dominios.
-   `mysnapapi/views/templates/admin/live-maintain.tpl`: Interfaz para mantener o borrar estadísticas en vivo.
-   `mysnapapi/views/templates/admin/live.tpl`: Muestra el panel de "Estadísticas en Vivo".
-   `mysnapapi/views/templates/admin/mode-context.tpl`: Proporciona contexto o explicación para el modo de seguimiento elegido.
-   `mysnapapi/views/templates/admin/mode-note-both.tpl`: Nota específica para el modo de seguimiento "Híbrido".
-   `mysnapapi/views/templates/admin/mode-note-capi.tpl`: Nota específica para el modo de seguimiento "Solo API de Conversiones".
-   `mysnapapi/views/templates/admin/mode-note-pixel.tpl`: Nota específica para el modo de seguimiento "Solo Píxel".
-   `mysnapapi/views/templates/admin/mode-picker.tpl`: La interfaz de selección para elegir el modo de seguimiento.
-   `mysnapapi/views/templates/admin/properties-list.tpl`: Muestra una lista de propiedades de eventos y sus reglas.
-   `mysnapapi/views/templates/admin/recent-events.tpl`: Tabla o lista que muestra los eventos rastreados más recientes.
-   `mysnapapi/views/templates/admin/tabs.tpl`: Renderiza la estructura de navegación por pestañas para la página de configuración del módulo.
-   `mysnapapi/views/templates/admin/tag-chips.tpl`: Componentes visuales para mostrar etiquetas o identificadores.
-   `mysnapapi/views/templates/admin/tag-ids.tpl`: Campos de entrada para el ID del Píxel y el Token CAPI.
-   `mysnapapi/views/templates/admin/wizard.tpl`: La plantilla para el asistente de configuración paso a paso.

#### Plantillas del Front-office (`views/templates/front/`)

(No hay plantillas de página independientes dedicadas, todas las plantillas del front-office están basadas en hooks).

### 4.7 Esquema de la Base de Datos y Mapa de Hooks

#### Tablas de la Base de Datos

El módulo utiliza principalmente la tabla `ps_configuration` de PrestaShop para almacenar su configuración.

-   `ps_configuration`: Almacena pares clave-valor para la configuración del módulo (por ejemplo, `MYSNAPAPI_PIXEL_ID`, `MYSNAPAPI_CAPI_TOKEN`, `MYSNAPAPI_TRACKING_MODE`).
-   No se crean explícitamente tablas SQL personalizadas por el módulo según el inventario proporcionado. Los eventos CAPI podrían ponerse en cola temporalmente en la memoria o en un sistema basado en archivos antes de ser enviados, en lugar de una tabla de base de datos dedicada.

#### Tabla de Hooks Registrados

| Nombre del Hook | Momento de Ejecución | Propósito Técnico |
| --- | --- | --- |
| `displayHeader` | Se renderiza en la sección `<head>` de cada página del front-office. | Inicializa el código base del Píxel de Snap, carga los activos JS, activa los eventos `PAGE_VIEW` y configura `ScCid` (Ghost Collector). |
| `displayFooter` | Se renderiza al final de la sección `<body>` de cada página del front-office. | Puede incluir la carga diferida de scripts, disparadores de eventos adicionales o la gestión de `ScCid`. |
| `displayProductButtons` | En la página del producto, cerca del botón "Añadir al Carrito". | Activa los eventos `VIEW_CONTENT` y potencialmente `ADD_CART` con los detalles del producto. |
| `displayFooterProduct` | En la página del producto, en el área del pie de página. | Ubicación alternativa o adicional para los eventos `VIEW_CONTENT` y `ADD_CART`. |
| `actionCartSave` | Se ejecuta cada vez que se modifica un carrito (añadir, actualizar, eliminar producto). | Activa los eventos `ADD_CART` o `REMOVE_FROM_CART`. |
| `actionValidateOrder` | Se ejecuta después de que se realiza un pedido con éxito. | Activa el evento crucial `PURCHASE`, enviando los detalles completos del pedido (valor, moneda, productos). |
| `displayOrderConfirmation` | En la página de confirmación del pedido después de una compra exitosa. | Renderiza el evento `PURCHASE` del lado del cliente para el Píxel de Snap. |
| `displayPayment` | Antes de la selección del método de pago. | Activa el evento `INITIATE_CHECKOUT`. |
| `displayPaymentTop` | En la parte superior de la página de selección de pago. | Ubicación alternativa o adicional para el evento `INITIATE_CHECKOUT`. |
| `actionFrontControllerSetMedia` | Se ejecuta cuando un controlador frontal está configurando sus activos multimedia. | Inyecta archivos CSS y JavaScript específicos del módulo en el front-office. |
| `actionAdminControllerSetMedia` | Se ejecuta cuando un controlador de administración está configurando sus activos multimedia. | Inyecta archivos CSS y JavaScript específicos del módulo en la página de configuración del back-office. |
| `actionModuleInstall` | Se ejecuta cuando se instala el módulo. | Establece los valores de configuración predeterminados en `ps_configuration`. |
| `actionModuleUninstall` | Se ejecuta cuando se desinstala el módulo. | Limpia los valores de configuración de `ps_configuration`. |

## 5. Soporte Oficial y Actualizaciones

Para actualizaciones oficiales, soporte técnico y las últimas versiones del módulo Píxel de Snapchat y API de Conversiones, consulta tu cuenta de cliente en [MyPresta.eu](https://mypresta.eu/). Nuestro equipo de soporte está disponible para ayudarte con cualquier problema o pregunta que puedas tener con respecto a la funcionalidad e integración del módulo.
