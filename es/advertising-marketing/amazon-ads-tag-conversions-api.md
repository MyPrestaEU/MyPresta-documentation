---
title: "API de Conversiones de Etiquetas de Amazon Ads - Manual del Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop 'API de Conversiones de Etiquetas de Amazon Ads' de MyPresta.eu."
sidebar:
  label: "API de Conversiones de Etiquetas de Amazon Ads - Manual del Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Amazon Ads Tag Conversions API en MyPresta.eu](https://mypresta.eu/modules/advertising-and-marketing/amazon-ads-tag-conversions-api.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/advertising-marketing/amazon-ads-tag-conversions-api/)
>
> ---


# API de Conversiones de Etiquetas de Amazon Ads

## 1. Requisitos y Compatibilidad

-   **Versiones de PrestaShop Compatibles**: PrestaShop 1.7.x, 8.x, 9.x
-   **Compatibilidad con PHP**: PHP 7.1 - 8.5
-   **Requisitos de Alojamiento**: Se requieren extensiones PHP estándar (cURL, JSON, OpenSSL) para que el módulo funcione correctamente, especialmente para la API de Conversiones (CAPI), que se basa en una comunicación segura de servidor a servidor. Su entorno de alojamiento también debe permitir conexiones salientes a los puntos finales de la API de Amazon.

## 2. Recorrido Completo por la Configuración (Cada Ajuste Agrupado por Pantalla)

Esta sección le guía a través de cada ajuste del módulo "API de Conversiones de Etiquetas de Amazon Ads".

### 2.1 Página de Configuración del Módulo (Back Office > Módulos > Configurar)

Esta es la pantalla de configuración principal donde configurará el seguimiento de sus Anuncios de Amazon.

**Acceso:** Navegue a **Módulos > Gestor de Módulos**, luego busque "API de Conversiones de Etiquetas de Amazon Ads" y haga clic en **Configurar**.

#### **Selección del Modo de Seguimiento**

Esta sección determina cómo su tienda envía datos a Amazon.

-   **Qué hace este ajuste:** Le permite elegir entre tres métodos principales para enviar datos de conversión a Amazon: Etiqueta de Amazon Ads (lado del cliente), API de Conversiones (lado del servidor) o una combinación de ambos.
-   **Efecto de cambiar este ajuste:**
    -   *Cuando se establece en "Etiqueta de Amazon Ads (Lado del Cliente)":* El módulo se basará principalmente en la etiqueta JavaScript colocada en el navegador del cliente para enviar datos. Esto es susceptible a los bloqueadores de anuncios.
    -   *Cuando se establece en "API de Conversiones (Lado del Servidor)":* El módulo enviará datos directamente desde su servidor PrestaShop a los servidores de Amazon. Esto es más fiable y evita los bloqueadores de anuncios.
    -   *Cuando se establece en "Modo Dual (Híbrido)":* El módulo enviará datos utilizando tanto la Etiqueta de Amazon Ads como la API de Conversiones. Esto proporciona la máxima resiliencia y precisión de los datos.
-   **Valor recomendado:** **"Modo Dual (Híbrido)"** para el seguimiento más robusto y preciso. Si está muy preocupado por la privacidad y desea minimizar los scripts del lado del cliente, "API de Conversiones (Lado del Servidor)" es una alternativa sólida.
-   **Escenario / ejemplo de comerciante:** Si ha notado una discrepancia entre las conversiones reportadas por sus Anuncios de Amazon y sus ventas reales de PrestaShop, cambiar a "Modo Dual" o "API de Conversiones" puede mejorar significativamente la precisión al recuperar las conversiones perdidas debido a los bloqueadores de anuncios.

#### **ID de Etiqueta de Amazon Ads**

-   **Qué hace este ajuste:** Este es su identificador único proporcionado por Amazon Ads para su etiqueta de seguimiento. Le dice a Amazon a qué cuenta atribuir los datos de conversión.
-   **Efecto de cambiar este ajuste:**
    -   *Cuando se introduce un ID válido:* La Etiqueta de Amazon Ads (si está habilitada en su modo de seguimiento) enviará datos correctamente a su cuenta de Amazon Ads.
    -   *Cuando se deja vacío o se introduce un ID no válido:* El seguimiento del lado del cliente no funcionará y los datos no se enviarán a su cuenta de Amazon Ads a través de la etiqueta.
-   **Valor recomendado:** Su ID de Etiqueta de Amazon Ads específico. Puede encontrarlo en su cuenta de Amazon Ads en "Administrador de Eventos" o "Audiencias".
-   **Escenario / ejemplo de comerciante:** Acaba de configurar una nueva campaña de Amazon Ads. Introducir el ID de Etiqueta correcto aquí es el primer paso para asegurar que el rendimiento de su campaña sea rastreado.

#### **Token de Acceso a la API de Conversiones de Amazon**

-   **Qué hace este ajuste:** Este es un token seguro proporcionado por Amazon Ads que autentica su servidor al enviar datos a través de la API de Conversiones. Asegura que solo las fuentes autorizadas puedan enviar datos a su cuenta de Amazon Ads.
-   **Efecto de cambiar este ajuste:**
    -   *Cuando se introduce un token válido:* Su servidor PrestaShop puede enviar datos de conversión de forma segura directamente a Amazon a través de la API de Conversiones (si está habilitada en su modo de seguimiento).
    -   *Cuando se deja vacío o se introduce un token no válido:* El seguimiento del lado del servidor a través de la API de Conversiones no funcionará y los datos no se enviarán a su cuenta de Amazon Ads a través de CAPI.
-   **Valor recomendado:** Su Token de Acceso a la API de Conversiones de Amazon específico. Este se genera en su cuenta de Amazon Ads, típicamente en "Administrador de Eventos" o "Fuentes de Datos". Trate este token como una contraseña; manténgalo seguro.
-   **Escenario / ejemplo de comerciante:** Desea mejorar la fiabilidad de su seguimiento de conversiones utilizando la API de Conversiones. Después de generar el token en Amazon Ads, péguelo aquí para habilitar la transmisión de datos del lado del servidor.

#### **Habilitar Modo de Depuración**

-   **Qué hace este ajuste:** Activa un modo especial que muestra información detallada sobre los datos que se envían a Amazon, visible solo para usted (o para cualquiera con las herramientas de desarrollador abiertas) en la consola del navegador. Esto es invaluable para la resolución de problemas.
-   **Efecto de cambiar este ajuste:**
    -   *Cuando está habilitado:* Verá registros de la consola y, potencialmente, superposiciones en pantalla (dependiendo de la implementación de depuración específica) que muestran qué eventos se están activando y qué datos se están enviando a Amazon. Esto no es visible para los clientes habituales.
    -   *Cuando está deshabilitado:* No se mostrará información de depuración.
-   **Valor recomendado:** **"NO"** para tiendas de producción en vivo. Solo habilítelo temporalmente al configurar o solucionar problemas.
-   **Escenario / ejemplo de comerciante:** Ha configurado el módulo, pero las conversiones no aparecen en su cuenta de Amazon Ads. Habilitar el modo de depuración puede ayudarle a ver si los eventos se están activando correctamente en su sitio web y si la carga de datos parece precisa.

#### **Integración de Gestión de Consentimiento**

-   **Qué hace este ajuste:** Permite que el módulo se integre con la solución de consentimiento de cookies de su tienda. Esto asegura que el seguimiento de Amazon Ads solo se active después de que un cliente haya dado su consentimiento explícito, cumpliendo con las regulaciones de privacidad como GDPR o CCPA.
-   **Efecto de cambiar este ajuste:**
    -   *Cuando está habilitado e integrado con un módulo de consentimiento:* La Etiqueta de Amazon Ads (lado del cliente) solo se cargará y activará eventos si el cliente ha aceptado las cookies de seguimiento. La CAPI del lado del servidor podría seguir enviando datos anonimizados o esperar el consentimiento, dependiendo de su configuración específica y políticas de privacidad.
    -   *Cuando está deshabilitado:* El módulo intentará rastrear eventos sin comprobaciones de consentimiento explícito, lo que podría no cumplir con las leyes de privacidad en ciertas regiones.
-   **Valor recomendado:** **"SÍ"** si su tienda opera en regiones con leyes de privacidad estrictas (por ejemplo, UE, California) y utiliza un módulo de consentimiento de cookies.
-   **Escenario / ejemplo de comerciante:** Su tienda atiende a clientes en Europa y utiliza un banner de cookies compatible con GDPR. Habilitar este ajuste asegura que su seguimiento de Amazon Ads respete las elecciones de privacidad del cliente.

#### **Configuración Avanzada (por ejemplo, Capa de Datos, Mapeo de Eventos, Resolución de ID de Producto)**

El módulo puede incluir configuraciones avanzadas que permiten ajustar la recopilación y transmisión de datos. Estas son típicamente para usuarios más técnicos o escenarios específicos.

-   **Seguimiento de Capa de Datos (`Data Layer Tracking`):**
    -   **Qué hace este ajuste:** Determina si el módulo debe usar una "capa de datos" estandarizada para recopilar información de su tienda. Esto se utiliza a menudo para la compatibilidad con otras herramientas de seguimiento o implementaciones personalizadas.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando está habilitado:* El módulo buscará y enviará datos a un objeto JavaScript `dataLayer`, lo que puede ser útil para depurar o integrar con Google Tag Manager.
        -   *Cuando está deshabilitado:* El módulo recopilará datos directamente de las variables internas de PrestaShop.
    -   **Valor recomendado:** **"SÍ"** si está utilizando Google Tag Manager u otras herramientas que dependen de una capa de datos. De lo contrario, "NO" suele ser suficiente.
-   **Mapeo de Eventos (`Event Mapping`):**
    -   **Qué hace este ajuste:** Le permite personalizar cómo las acciones específicas de PrestaShop (por ejemplo, "añadir al carrito") se mapean a los nombres de eventos de Amazon Ads.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando se personaliza:* Puede enviar nombres de eventos diferentes a Amazon que los predeterminados del módulo, lo que podría ser útil para configuraciones específicas de campañas de Amazon Ads.
        -   *Cuando es predeterminado:* El módulo utiliza su mapeo predefinido.
    -   **Valor recomendado:** Dejar en el valor predeterminado a menos que tenga una razón específica para cambiarlo basada en la documentación de Amazon Ads.
-   **Resolución de ID de Producto (`Product ID Resolution`):**
    -   **Qué hace este ajuste:** Define qué identificador de producto (por ejemplo, ID de Producto, EAN, UPC, SKU) debe enviar el módulo a Amazon para eventos relacionados con productos.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando se establece en ID de Producto:* Amazon recibirá el ID de producto interno de PrestaShop.
        -   *Cuando se establece en EAN/UPC/SKU:* Amazon recibirá el identificador de producto correspondiente. Esto es crucial para hacer coincidir productos en su catálogo de productos de Amazon.
    -   **Valor recomendado:** Elija el identificador que coincida más consistentemente con los ID de producto que utiliza en sus feeds o catálogo de productos de Amazon. **EAN/UPC** a menudo se prefiere para productos minoristas.
-   **Dominios de Enlace (`Linker Domains`):**
    -   **Qué hace este ajuste:** Especifica dominios adicionales que deben incluirse en el seguimiento entre dominios. Esto es importante si su proceso de pago u otras partes de su recorrido del cliente involucran múltiples dominios (por ejemplo, un subdominio separado para un blog o una pasarela de pago que redirige).
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando está configurado:* La Etiqueta de Amazon Ads puede mantener la continuidad del seguimiento en diferentes dominios, evitando la pérdida de atribución.
        -   *Cuando no está configurado para múltiples dominios:* Las conversiones podrían ser mal atribuidas o perdidas si el cliente navega entre dominios durante su recorrido.
    -   **Valor recomendado:** Añada cualquier dominio o subdominio que forme parte del recorrido de su cliente.
-   **Ayudante de Moneda (`Currency Helper`):**
    -   **Qué hace este ajuste:** Asegura que los valores de moneda enviados a Amazon estén correctamente formateados y coincidan con la moneda utilizada en su cuenta de Amazon Ads.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando está configurado correctamente:* Amazon recibe valores de moneda precisos.
        -   *Cuando está mal configurado:* Los valores de moneda podrían ser malinterpretados por Amazon, lo que lleva a informes incorrectos.
    -   **Valor recomendado:** Asegúrese de que esto se alinee con la moneda principal de su tienda y la moneda de su cuenta de Amazon Ads.

### 2.2 Pantallas de Administración Dedicadas y Vistas de Controlador

El módulo proporciona varias pantallas dedicadas para ayudarle a monitorear y optimizar su seguimiento de Amazon Ads. Estas suelen ser accesibles a través de pestañas o subsecciones dentro de la configuración principal del módulo.

#### **4.2.1 Estadísticas en Vivo**

-   **Nombre de la Pantalla y Ubicación del Menú:** Generalmente una pestaña dentro de la configuración principal del módulo (por ejemplo, "Estadísticas en Vivo").
-   **Acciones y Ajustes Disponibles:** Esta pantalla muestra datos en tiempo real o casi en tiempo real sobre los eventos que se envían a Amazon. Podría mostrar:
    -   Eventos recientes (por ejemplo, PageView, AddToCart, Purchase) con marcas de tiempo.
    -   Tipos de eventos y su frecuencia.
    -   Puntuaciones de calidad de datos.
    -   Visualizaciones de la actividad de seguimiento.
-   **Efecto de los cambios:** Esta es una pantalla de informes; no hay ajustes directos para cambiar aquí. Refleja los datos que se envían en función de su configuración principal.
-   **Flujo de trabajo recomendado para la gestión diaria de la tienda:** Revise regularmente esta pantalla para asegurarse de que los eventos se están activando como se espera, especialmente después de realizar cambios en su tienda o lanzar nuevas campañas. Es su primera línea de defensa para identificar problemas de seguimiento.

#### **4.2.2 Puntuación de Salud y Radar de Recuperación**

-   **Nombre de la Pantalla y Ubicación del Menú:** A menudo una pestaña dentro de la configuración principal del módulo (por ejemplo, "Puntuación de Salud" o "Diagnóstico").
-   **Acciones y Ajustes Disponibles:** Esta sección proporciona una puntuación de salud general para su seguimiento de Amazon Ads e identifica posibles problemas o conversiones "perdidas". Podría incluir:
    -   Una puntuación porcentual que indica la salud del seguimiento.
    -   Recomendaciones para mejorar la calidad de los datos.
    -   Un "Radar de Recuperación" que muestra las conversiones estimadas que podrían haberse perdido debido a bloqueadores de anuncios u otros problemas, y cómo CAPI está ayudando a recuperarlas.
    -   Advertencias sobre ID de Etiqueta, Tokens de Acceso o problemas de consentimiento faltantes.
-   **Efecto de los cambios:** Al igual que las Estadísticas en Vivo, esta es principalmente una pantalla de informes y diagnóstico. Las acciones que tome basándose en sus recomendaciones (por ejemplo, actualizar un ID de Etiqueta faltante) mejorarán su seguimiento.
-   **Flujo de trabajo recomendado para la gestión diaria de la tienda:** Revise periódicamente su Puntuación de Salud. Una puntuación baja o un "Radar de Recuperación" activo indican áreas donde su seguimiento podría mejorarse, lo que podría conducir a un mejor rendimiento de los anuncios.

#### **4.2.3 Entrenador de Calidad de Datos / Doctor de Catálogo**

-   **Nombre de la Pantalla y Ubicación del Menú:** Potencialmente una pestaña dentro de la configuración principal del módulo (por ejemplo, "Calidad de Datos" o "Doctor de Catálogo").
-   **Acciones y Ajustes Disponibles:** Estas herramientas le ayudan a asegurar que los datos que envía a Amazon sean de alta calidad y estén correctamente formateados. Podrían:
    -   Buscar problemas comunes de datos (por ejemplo, ID de producto faltantes, formatos de moneda incorrectos).
    -   Proporcionar sugerencias para mejorar los datos de su catálogo de productos para que coincidan mejor con los requisitos de Amazon.
    -   Resaltar discrepancias entre los datos del lado del cliente y del lado del servidor.
-   **Efecto de los cambios:** Esta pantalla proporciona información útil. Abordar los problemas resaltados aquí (por ejemplo, actualizar los EAN de los productos en su catálogo de PrestaShop) mejorará directamente la calidad y las capacidades de coincidencia de sus datos de conversión en Amazon Ads.
-   **Flujo de trabajo recomendado para la gestión diaria de la tienda:** Si está experimentando problemas con la coincidencia de productos en Amazon Ads o ve advertencias en su Puntuación de Salud, consulte estas herramientas para refinar sus datos.

### 2.3 Tabla de Referencia Rápida de Configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| Config. Principal | **Modo de Seguimiento** | Modo Dual (Híbrido) | Determina si el seguimiento es del lado del cliente, del lado del servidor o ambos. El Modo Dual ofrece máxima resiliencia. |
| Config. Principal | **ID de Etiqueta de Amazon Ads** | Su ID de Etiqueta de Amazon | Esencial para el seguimiento del lado del cliente. Vincula los datos a su cuenta de Amazon Ads. |
| Config. Principal | **Token de Acceso a la API de Conversiones de Amazon** | Su Token de Acceso a CAPI | Esencial para el seguimiento del lado del servidor. Autentica su servidor con Amazon. |
| Config. Principal | **Habilitar Modo de Depuración** | NO | Muestra datos de seguimiento en la consola del navegador para solucionar problemas. Deshabilitar en tiendas en vivo. |
| Config. Principal | **Integración de Gestión de Consentimiento** | SÍ (si aplica) | Asegura que el seguimiento respete la privacidad del cliente y el consentimiento de cookies. |
| Config. Principal | **Seguimiento de Capa de Datos** | SÍ (si usa GTM) | Utiliza una capa de datos para la recopilación de eventos, útil para GTM o integraciones personalizadas. |
| Config. Principal | **Resolución de ID de Producto** | EAN/UPC | Define qué identificador de producto se envía a Amazon para la coincidencia. Crucial para la coincidencia de catálogo. |
| Config. Principal | **Dominios de Enlace** | Vacío (añadir si es necesario) | Mantiene el seguimiento en múltiples dominios en el recorrido de su cliente. |
| Estadísticas en Vivo | (Solo Informes) | N/A | Muestra datos de eventos en tiempo real, ayudándole a verificar que el seguimiento está activo. |
| Puntuación de Salud | (Solo Informes) | N/A | Proporciona una evaluación general de la salud de su seguimiento e identifica problemas. |
| Calidad de Datos | (Solo Informes) | N/A | Ayuda a identificar y corregir problemas de calidad de datos en su catálogo de productos para una mejor coincidencia con Amazon. |

## 3. Resolución de Problemas del Comerciante y Preguntas Frecuentes (FAQ)

**P1: Mis conversiones de Amazon Ads no coinciden con mis ventas de PrestaShop. ¿Qué debo hacer?**
R1: Este es un problema común, a menudo debido a bloqueadores de anuncios.
\* **Verifique el Modo de Seguimiento:** Asegúrese de que está utilizando "Modo Dual (Híbrido)" o "API de Conversiones (Lado del Servidor)" en la configuración del módulo. Esta es la forma más efectiva de recuperar conversiones perdidas.
\* **Verifique IDs/Tokens:** Vuelva a verificar que su ID de Etiqueta de Amazon Ads y su Token de Acceso a la API de Conversiones estén correctamente introducidos en la configuración del módulo.
\* **Use el Modo de Depuración:** Habilite temporalmente el "Modo de Depuración" y realice una compra de prueba. Revise la consola de su navegador y las "Estadísticas en Vivo" del módulo para ver si los eventos se están activando.
\* **Borre la Caché:** Vaya a **Parámetros Avanzados > Rendimiento** en el back office de su PrestaShop y borre la caché de Smarty y otras cachés. A veces, el código antiguo del módulo puede persistir.

**P2: Estoy viendo advertencias sobre "Calidad de Datos" o "IDs de Producto Faltantes" en la Puntuación de Salud del módulo. ¿Cómo lo soluciono?**
R2: Amazon se basa en datos de productos de alta calidad para una coincidencia precisa.
\* **Resolución de ID de Producto:** En la configuración del módulo, asegúrese de que su ajuste de "Resolución de ID de Producto" (por ejemplo, EAN, UPC, SKU) coincida con el identificador principal utilizado en su feed de productos de Amazon.
\* **Actualice los Datos del Producto:** Vaya a **Catálogo > Productos** en el back office de su PrestaShop. Edite los productos marcados por el "Entrenador de Calidad de Datos" y asegúrese de que tengan EAN, UPC o SKU completos y precisos según sea necesario.
\* **Consistencia:** Asegúrese de que los identificadores de producto en su tienda PrestaShop sean consistentes con lo que proporciona a Amazon en sus feeds de productos.

**P3: Mi sitio web utiliza un banner de consentimiento de cookies. ¿Este módulo respetará las elecciones del cliente?**
R3: Sí, si está configurado correctamente.
\* **Habilite la Integración de Consentimiento:** En la configuración del módulo, asegúrese de que la "Integración de Gestión de Consentimiento" esté habilitada.
\* **Compatibilidad con Módulos de Cookies:** Este módulo está diseñado para integrarse con los módulos estándar de consentimiento de cookies de PrestaShop. Si utiliza una solución personalizada, es posible que deba asegurarse de que active correctamente los eventos `prestashop.on('updateProduct', ...)` o similares que los módulos escuchan para los cambios de consentimiento.
\* **CAPI vs. Etiqueta:** Recuerde que la API de Conversiones (lado del servidor) se ve menos afectada por los banners de consentimiento del lado del cliente que la Etiqueta de Amazon Ads (lado del cliente), ya que envía datos directamente desde su servidor. Sin embargo, sigue siendo una buena práctica enviar información de identificación personal (PII) a través de CAPI solo después del consentimiento.

**P4: El módulo parece estar ralentizando mi sitio. ¿Qué puedo hacer?**
R4: Este módulo está optimizado para el rendimiento, pero aquí hay algunas comprobaciones:
\* **Deshabilite el Modo de Depuración:** Asegúrese de que el "Modo de Depuración" esté deshabilitado en su tienda en vivo, ya que añade un registro adicional en la consola.
\* **Rendimiento del Servidor:** La API de Conversiones (CAPI) realiza llamadas de servidor a servidor. Aunque generalmente es rápida, asegúrese de que su servidor de alojamiento tenga recursos adecuados y una conexión a Internet estable.
\* **Otros Módulos:** Verifique si otros módulos pesados de seguimiento o publicidad también se están ejecutando simultáneamente. Demasiados scripts del lado del cliente pueden afectar el rendimiento.
\* **Borre la Caché:** Siempre borre la caché de PrestaShop después de realizar cambios en la configuración.

**Q5: Recibo un mensaje de error al intentar guardar la configuración del módulo.**
R5:
\* **Verifique los Permisos:** Asegúrese de que la carpeta del módulo (`/modules/myamazon/`) y sus subcarpetas tengan los permisos de escritura correctos (generalmente 755 para carpetas, 644 para archivos).
\* **Registros del Servidor:** Revise los registros de errores de PHP de su servidor para obtener información más detallada sobre el error. Esto a menudo se puede encontrar en su panel de control de alojamiento o contactando a su proveedor de alojamiento.
\* **Modo de Depuración de PrestaShop:** Habilite temporalmente el modo de depuración de PrestaShop (en `config/defines.inc.php`, cambie `define('_PS_MODE_DEV_', false);` a `define('_PS_MODE_DEV_', true);`) para ver mensajes de error más detallados en pantalla.

## 4. Guía para Desarrolladores y Webmasters (Arquitectura Técnica y Mapa de Código)

Esta sección proporciona una inmersión profunda en la estructura técnica del módulo "API de Conversiones de Etiquetas de Amazon Ads", destinada a desarrolladores y webmasters.

### 4.1 Visión General de la Arquitectura

El módulo `myamazon` está construido siguiendo el patrón MVC (Modelo-Vista-Controlador) de PrestaShop, con un fuerte énfasis en la modularidad y el seguimiento basado en eventos. Aprovecha tanto los mecanismos del lado del cliente (Etiqueta de Amazon Ads) como del lado del servidor (API de Conversiones), a menudo en un enfoque híbrido.

Componentes arquitectónicos clave:

-   **Clase Principal del Módulo (`myamazon/index.php`):** Gestiona la instalación, desinstalación, registro de hooks y el método principal `getContent()` para la configuración del back-office.
-   **Controladores:** Controladores frontales dedicados para interacciones AJAX y controladores de administración para gestionar la configuración del módulo y las vistas de diagnóstico.
-   **Clases Core (`classes/`):** Un conjunto robusto de clases gestiona varios aspectos:
    -   **Lógica de Seguimiento:** `MyamazonAatTracker.php` (lado del cliente), `MyamazonCapiTracker.php` (lado del servidor), `MyamazonHybridTracker.php` (modo dual), `MyamazonTrackerFactory.php` (instancia de rastreadores).
    -   **Manejo de Datos:** `MyamazonUserData.php` (datos del cliente), `MyamazonEventMap.php` (traducción de eventos), `MyamazonProductIdResolver.php` (lógica de ID de producto), `MyamazonCurrencyHelper.php`.
    -   **Cliente API:** `MyamazonCapiClient.php` (gestiona la comunicación con la CAPI de Amazon).
    -   **Diagnóstico y Salud:** `MyamazonHealthScore.php`, `MyamazonCatalogDoctor.php`, `MyamazonDataQualityCoach.php`, `MyamazonLiveStats.php`.
    -   **Consentimiento:** `MyamazonConsent.php` (se integra con los mecanismos de consentimiento).
-   **Hooks:** Uso extensivo de los hooks de PrestaShop para inyectar JavaScript, capturar eventos y enviar datos en puntos críticos del recorrido del cliente.
-   **Plantillas Smarty:** Utilizadas para renderizar tanto las vistas de configuración del back-office como los scripts de seguimiento del front-office.
-   **JavaScript:** Gestiona la inyección de etiquetas del lado del cliente, la escucha de eventos y las interacciones de la capa de datos.

### 4.2 Controladores (`controllers/`)

#### Controladores del Front-Office

-   `controllers/front/ajax.php`
    -   **Nombre de la Clase:** `MyamazonAjaxModuleFrontController` (extiende `ModuleFrontController`)
    -   **Responsabilidad:** Gestiona las solicitudes asíncronas (AJAX) desde el front-office. Esto se utiliza típicamente para el envío de eventos del lado del servidor a través de CAPI que no se pueden realizar directamente en el navegador (por ejemplo, eventos posteriores a la compra donde el navegador podría estar cerrado, o eventos que requieren procesamiento de datos del lado del servidor). Recibe datos de JavaScript del lado del cliente y los envía a `MyamazonCapiTracker`.
-   `controllers/front/index.php`
    -   **Nombre de la Clase:** `MyamazonIndexModuleFrontController` (extiende `ModuleFrontController`)
    -   **Responsabilidad:** Este controlador podría servir como un respaldo o un punto de entrada simple, aunque su caso de uso principal podría ser mínimo si `ajax.php` maneja la mayoría de las interacciones del front-end. Podría usarse para redirecciones específicas o visualizaciones de datos simples si es necesario, pero a menudo sirve como un marcador de posición.

#### Controladores de Administración del Back-Office

-   `controllers/admin/AdminMyamazonAjaxController.php`
    -   **Nombre de la Clase:** `AdminMyamazonAjaxController` (extiende `ModuleAdminController`)
    -   **Nombre de la Pestaña:** No es directamente una pestaña de menú, sino un punto final AJAX para la interfaz de administración.
    -   **Responsabilidad:** Gestiona las solicitudes AJAX que se originan en las páginas de configuración del back-office del módulo. Esto incluye la obtención de datos para estadísticas en vivo, puntuaciones de salud o la realización de comprobaciones en segundo plano (por ejemplo, validación de tokens de API) sin recargar toda la página. Interactúa con clases como `MyamazonLiveStats`, `MyamazonHealthScore` y `MyamazonCapiClient`.
-   `controllers/admin/index.php`
    -   **Nombre de la Clase:** `AdminMyamazonIndexController` (extiende `ModuleAdminController`)
    -   **Nombre de la Pestaña:** No es una pestaña de menú directa.
    -   **Responsabilidad:** Similar al `index.php` del front-office, esto podría ser un marcador de posición o manejar interacciones de administración muy específicas y no AJAX. La lógica de configuración principal reside en el método `getContent()` del módulo principal.

### 4.3 Clases Core y Modelos (`classes/`)

-   `classes/autoload.php`: Archivo de carga automática estándar de PrestaShop.
-   `classes/index.php`: Archivo de marcador de posición, común en directorios vacíos.
-   `classes/MyamazonAatTracker.php`:
    -   **Responsabilidad:** Implementa la lógica para el seguimiento de la Etiqueta de Amazon Ads del lado del cliente. Genera el JavaScript necesario para `aa.js` y envía eventos a la capa de datos del navegador o directamente a la Etiqueta de Amazon Ads.
-   `classes/MyamazonCapiClient.php`:
    -   **Responsabilidad:** Gestiona las solicitudes HTTP reales a los puntos finales de la API de Conversiones de Amazon. Encapsula la lógica de cURL o Guzzle (si se usa), la autenticación con el token de acceso y el manejo de errores para la comunicación de servidor a servidor.
-   `classes/MyamazonCapiTracker.php`:
    -   **Responsabilidad:** Implementa la lógica para el seguimiento de la API de Conversiones del lado del servidor. Formatea los datos de eventos de acuerdo con las especificaciones de CAPI de Amazon y utiliza `MyamazonCapiClient` para enviarlos.
-   `classes/MyamazonCatalogDoctor.php`:
    -   **Responsabilidad:** Analiza los datos del catálogo de productos de la tienda en busca de posibles problemas que podrían afectar la coincidencia de productos de Amazon (por ejemplo, EAN faltantes, SKU incorrectos). Proporciona comentarios de diagnóstico para la interfaz de administración.
-   `classes/MyamazonConsent.php`:
    -   **Responsabilidad:** Gestiona la integración del consentimiento de cookies. Comprueba el estado del consentimiento del cliente y habilita/deshabilita condicionalmente los scripts de seguimiento del lado del cliente. Se integra con el evento `prestashop.on('updateProduct', ...)` de PrestaShop para los cambios de consentimiento.
-   `classes/MyamazonCurrencyHelper.php`:
    -   **Responsabilidad:** Proporciona métodos de utilidad para formatear los valores de moneda correctamente para Amazon Ads, manejando decimales y códigos de moneda.
-   `classes/MyamazonDataLayerTracker.php`:
    -   **Responsabilidad:** Gestiona el envío de datos de eventos a un objeto JavaScript `dataLayer`, a menudo utilizado para la compatibilidad con Google Tag Manager u otros consumidores de la capa de datos.
-   `classes/MyamazonDataQualityCoach.php`:
    -   **Responsabilidad:** Proporciona información y recomendaciones para mejorar la calidad general de los datos enviados a Amazon, cubriendo aspectos más allá de los ID de producto.
-   `classes/MyamazonEventId.php`:
    -   **Responsabilidad:** Genera ID de evento únicos para cada evento, crucial para la deduplicación al usar el seguimiento en modo dual (asegurando que Amazon no cuente el mismo evento dos veces desde el lado del cliente y del servidor).
-   `classes/MyamazonEventMap.php`:
    -   **Responsabilidad:** Define el mapeo entre los eventos internos de PrestaShop (por ejemplo, `actionCartSave`) y los nombres de eventos estándar de Amazon Ads (por ejemplo, `AddToCart`). Permite la personalización de estos mapeos.
-   `classes/MyamazonEvents.php`:
    -   **Responsabilidad:** Una clase central o colección de métodos para activar y gestionar varios eventos de Amazon Ads (por ejemplo, `PageView`, `ViewContent`, `AddToCart`, `Purchase`).
-   `classes/MyamazonHealthScore.php`:
    -   **Responsabilidad:** Calcula y presenta una "puntuación de salud" general para el seguimiento del módulo, identificando problemas de configuración, datos faltantes o posibles lagunas de seguimiento.
-   `classes/MyamazonHybridTracker.php`:
    -   **Responsabilidad:** Orquesta el seguimiento en modo dual, combinando `MyamazonAatTracker` y `MyamazonCapiTracker` para enviar eventos a través de métodos del lado del cliente y del servidor, gestionando la deduplicación.
-   `classes/MyamazonLiveStats.php`:
    -   **Responsabilidad:** Recopila y procesa datos de eventos en tiempo real o casi en tiempo real para su visualización en la vista de back-office "Estadísticas en Vivo".
-   `classes/MyamazonProductIdResolver.php`:
    -   **Responsabilidad:** Determina qué identificador de producto (ID, EAN, UPC, SKU) debe usarse al enviar datos de producto a Amazon, basándose en la configuración del módulo.
-   `classes/MyamazonPropertyRules.php`:
    -   **Responsabilidad:** Define reglas y validaciones para las propiedades de los eventos, asegurando que los datos enviados a Amazon cumplan con sus especificaciones de API.
-   `classes/MyamazonTrackerFactory.php`:
    -   **Responsabilidad:** Una clase de patrón de fábrica responsable de instanciar el rastreador correcto (`AatTracker`, `CapiTracker` o `HybridTracker`) basándose en la configuración del módulo.
-   `classes/MyamazonTrackerInterface.php`:
    -   **Responsabilidad:** Define una interfaz común para todas las clases de rastreadores (`AatTracker`, `CapiTracker`, `HybridTracker`), asegurando que implementen un conjunto consistente de métodos para el seguimiento de eventos.
-   `classes/MyamazonUserData.php`:
    -   **Responsabilidad:** Recopila y formatea datos relacionados con el cliente (por ejemplo, correo electrónico, teléfono, dirección) para su inclusión en los eventos de Amazon Ads, especialmente para la API de Conversiones donde la PII puede ser hash y enviada.

### 4.4 Activos JavaScript (`views/js/`)

-   `views/js/myamazon-admin.js`:
    -   **Alcance:** Back-office.
    -   **Detalles:** Gestiona elementos interactivos en las páginas de configuración del módulo, como el cambio de pestañas, las llamadas AJAX para estadísticas en vivo, la validación de formularios y las actualizaciones dinámicas de las herramientas de diagnóstico.
-   `views/js/myamazon-debug.js`:
    -   **Alcance:** Front-office (cargado condicionalmente cuando el modo de depuración está activo).
    -   **Detalles:** Proporciona un registro detallado en la consola del navegador, mostrando los eventos que se activan, las cargas de datos y el estado de las llamadas a la Etiqueta de Amazon Ads y CAPI. Puede incluir superposiciones visuales para una depuración rápida.
-   `views/js/myamazon-ghost.js`:
    -   **Alcance:** Front-office.
    -   **Detalles:** Probablemente relacionado con mecanismos de seguimiento "fantasma" o en segundo plano, potencialmente para capturar eventos que de otro modo podrían perderse o para aplazamientos específicos relacionados con el consentimiento.
-   `views/js/myamazon-live.js`:
    -   **Alcance:** Back-office.
    -   **Detalles:** Impulsa el panel de "Estadísticas en Vivo", realizando solicitudes AJAX a `AdminMyamazonAjaxController` para obtener y mostrar datos de eventos en tiempo real.
-   `views/js/myamazon-tcf.js`:
    -   **Alcance:** Front-office.
    -   **Detalles:** Se integra con soluciones de consentimiento de cookies compatibles con el Marco de Transparencia y Consentimiento (TCF), asegurando que el seguimiento del lado del cliente se adhiera a las preferencias de consentimiento del usuario.
-   `views/js/myamazon-wizard.js`:
    -   **Alcance:** Back-office.
    -   **Detalles:** Proporciona pasos interactivos para el asistente de configuración inicial, guiando al comerciante a través de la configuración esencial.
-   `views/js/myamazon.js`:
    -   **Alcance:** Front-office.
    -   **Detalles:** El JavaScript principal del lado del cliente para el módulo. Inyecta la Etiqueta de Amazon Ads (script `aa.js`), escucha varios eventos DOM (por ejemplo, `click` en los botones de añadir al carrito), captura datos de la página, envía eventos a la capa de datos y, potencialmente, realiza llamadas AJAX a `MyamazonAjaxModuleFrontController` para el procesamiento del lado del servidor. También gestiona la lógica de deduplicación de eventos.

### 4.5 Hojas de Estilo CSS (`views/css/`)

-   `myamazon/opis/sugestie/style1.css`, `myamazon/opis/sugestie/style2.css`, `myamazon/opis/sugestie/sugestie/style1.css`, `myamazon/opis/sugestie/sugestie/style2.css`, `myamazon/opis/sugestie/sugestie/tailwind-new-7.css`, `myamazon/opis/sugestie/tailwind-new-7.css`:
    -   **Alcance:** Back-office.
    -   **Detalles:** Estos archivos parecen estar relacionados con un marco de interfaz de usuario personalizado o un estilo para sugerencias/pistas dentro de la configuración del back-office, posiblemente para una configuración guiada o comentarios de diagnóstico. `tailwind-new-7.css` sugiere el uso de Tailwind CSS para un estilo de utilidad primero.
-   `views/css/myamazon-admin.css`:
    -   **Alcance:** Estilo del formulario de administración del back-office.
    -   **Detalles:** Proporciona un estilo específico para los formularios de configuración del módulo, pestañas, paneles de diagnóstico y otros elementos de interfaz de usuario personalizados dentro del back office de PrestaShop.
-   `views/css/myamazon-debug.css`:
    -   **Alcance:** Front-office (cargado condicionalmente).
    -   **Detalles:** Estilos para la superposición de depuración o los mensajes de la consola, asegurando que sean legibles y distintos cuando el modo de depuración está activo.

### 4.6 Estructura de Plantillas Smarty (`views/templates/`)

#### Plantillas de Hook (`views/templates/hook/`)

-   `views/templates/hook/capi-pageview.tpl`:
    -   **Hook:** `displayHeader` (o similar).
    -   **Salida:** Inyecta datos de eventos PageView del lado del servidor (CAPI), potencialmente como una entrada oculta o una variable JavaScript, para ser recogidos por el controlador `ajax.php` para el envío del lado del servidor.
-   `views/templates/hook/debug.tpl`:
    -   **Hook:** `displayHeader` (condicionalmente).
    -   **Salida:** Inyecta el script `myamazon-debug.js` y cualquier variable de depuración inicial necesaria cuando el modo de depuración está habilitado.
-   `views/templates/hook/displayOrderConfirmation.tpl`:
    -   **Hook:** `displayOrderConfirmation`.
    -   **Salida:** Renderiza los datos críticos del evento "Purchase", incluidos los detalles del pedido, los productos y la información del cliente, tanto para la etiqueta del lado del cliente como para la transmisión CAPI del lado del servidor. Aquí es donde se captura el valor de la conversión.
-   `views/templates/hook/ghost.tpl`:
    -   **Hook:** `displayHeader` (o similar).
    -   **Salida:** Relacionado con el mecanismo de seguimiento "fantasma", potencialmente para carga diferida o lógica específica relacionada con el consentimiento.
-   `views/templates/hook/header.tpl`:
    -   **Hook:** `displayHeader`.
    -   **Salida:** La plantilla principal para inyectar la Etiqueta de Amazon Ads (script `aa.js`), `myamazon.js` y las variables de configuración iniciales en la sección `<head>` de cada página.
-   `views/templates/hook/payment.tpl`:
    -   **Hook:** `displayPaymentTop` (o similar).
    -   **Salida:** Puede usarse para rastrear eventos "InitiateCheckout" u otros eventos relacionados con el pago antes de la confirmación final del pedido.
-   `views/templates/hook/product-details.tpl`:
    -   **Hook:** `displayProductButtons` o `displayProductExtraContent`.
    -   **Salida:** Inyecta JavaScript para rastrear eventos "ViewContent" cuando se carga una página de producto, capturando datos específicos del producto.

#### Plantillas de Administración (`views/templates/admin/`)

-   `views/templates/admin/consent-guide.tpl`: Muestra una guía sobre cómo integrarse con los módulos de consentimiento de cookies.
-   `views/templates/admin/doctor.tpl`: Renderiza la vista de diagnóstico "Doctor de Catálogo", mostrando problemas de datos de productos.
-   `views/templates/admin/dq.tpl`: Renderiza la vista "Entrenador de Calidad de Datos", proporcionando información sobre la calidad de los datos.
-   `views/templates/admin/health.tpl`: Muestra la "Puntuación de Salud" general y los diagnósticos relacionados.
-   `views/templates/admin/linker-domains.tpl`: Renderiza el campo de entrada para configurar los dominios de enlace.
-   `views/templates/admin/live-maintain.tpl`: Posiblemente una vista de mantenimiento para estadísticas en vivo.
-   `views/templates/admin/live.tpl`: Renderiza el panel de "Estadísticas en Vivo".
-   `views/templates/admin/mode-context.tpl`, `views/templates/admin/mode-note-aat.tpl`, `views/templates/admin/mode-note-both.tpl`, `views/templates/admin/mode-note-capi.tpl`, `views/templates/admin/mode-note-datalayer.tpl`, `views/templates/admin/mode-picker.tpl`: Estas plantillas se utilizan para la sección "Selección del Modo de Seguimiento", proporcionando explicaciones y el botón de radio/desplegable para elegir el método de seguimiento.
-   `views/templates/admin/properties-list.tpl`: Muestra una lista de propiedades de eventos y sus valores, posiblemente para depuración o configuración.
-   `views/templates/admin/recent-events.tpl`: Renderiza una tabla o lista de eventos rastreados recientemente, parte de "Estadísticas en Vivo".
-   `views/templates/admin/tabs.tpl`: Renderiza la estructura de navegación por pestañas para la configuración del back-office del módulo.
-   `views/templates/admin/tag-chips.tpl`: Muestra "chips" o etiquetas visuales para las etiquetas/tokens configurados.
-   `views/templates/admin/tag-ids.tpl`: Renderiza los campos de entrada para el ID de Etiqueta de Amazon Ads y el Token de Acceso a CAPI.
-   `views/templates/admin/wizard.tpl`: Renderiza la interfaz del asistente de configuración inicial.

### 4.7 Esquema de Base de Datos y Mapa de Hooks

#### Tablas de Base de Datos

El módulo almacena principalmente su configuración en la tabla `ps_configuration` de PrestaShop.

-   `ps_configuration`: Almacena pares clave-valor para la configuración del módulo (por ejemplo, `MYAMAZON_TAG_ID`, `MYAMAZON_CAPI_TOKEN`, `MYAMAZON_TRACKING_MODE`).
    No se crean tablas SQL personalizadas explícitamente por este módulo según el inventario proporcionado.

#### Tabla de Hooks Registrados

| Nombre del Hook | Momento de Ejecución | Propósito Técnico |
| --- | --- | --- |
| `displayHeader` | En la sección `<head>` de cada página. | Inyecta el script de la Etiqueta de Amazon Ads (`aa.js`), `myamazon.js` y las variables de configuración iniciales. También se usa para `capi-pageview.tpl` y `debug.tpl`. |
| `displayOrderConfirmation` | En la página de confirmación del pedido después de una compra exitosa. | Captura y envía datos del evento "Purchase", incluidos los detalles del pedido y los productos, a Amazon a través de métodos del lado del cliente y del servidor. |
| `actionCartSave` | Cuando se añade o elimina un producto del carrito, o cambia la cantidad del carrito. | Activa los eventos "AddToCart" o "RemoveFromCart". |
| `actionProductAdd` | Cuando se añade un nuevo producto al catálogo. | Potencialmente utilizado por `MyamazonCatalogDoctor` para comprobaciones de calidad de datos. |
| `actionProductUpdate` | Cuando se actualiza un producto existente en el catálogo. | Potencialmente utilizado por `MyamazonCatalogDoctor` para comprobaciones de calidad de datos. |
| `actionFrontControllerSetMedia` | Antes de que un controlador frontal renderice su plantilla, permitiendo la adición de JS/CSS. | Inyecta archivos JS/CSS específicos del módulo (`myamazon.js`, `myamazon-debug.js`, etc.) en el front office. |
| `actionAdminControllerSetMedia` | Antes de que un controlador de administración renderice su plantilla. | Inyecta archivos JS/CSS específicos del módulo (`myamazon-admin.js`, `myamazon-admin.css`, etc.) en el back office. |
| `actionValidateOrder` | Después de que un pedido ha sido validado y guardado con éxito en la base de datos. | Crucial para el envío de eventos "Purchase" del lado del servidor a través de CAPI, asegurando que los datos se envíen incluso si el cliente cierra el navegador antes de llegar a la página de confirmación. |
| `displayProductButtons` / `displayProductExtraContent` | En la página del producto, cerca del botón de añadir al carrito o la descripción del producto. | Inyecta JavaScript para rastrear eventos "ViewContent". |
| `displayPaymentTop` | En la parte superior de la página de selección de pago durante el proceso de compra. | Potencialmente utilizado para rastrear eventos "InitiateCheckout". |
| `displayFooter` | En la sección del pie de página de cada página. | Menos común para el seguimiento principal, pero podría usarse para la carga diferida de scripts o ventanas emergentes de consentimiento específicas. |
| `actionObjectCustomerAddAfter` | Después de que se crea una nueva cuenta de cliente. | Potencialmente utilizado para enviar eventos "SignUp" o "Lead" a Amazon. |
| `actionObjectCustomerUpdateAfter` | Después de que se actualizan los detalles de un cliente. | Podría usarse para actualizar los datos del cliente para CAPI. |

## 5. Soporte Oficial y Actualizaciones

Para las últimas actualizaciones del módulo, correcciones de errores y soporte oficial, consulte su cuenta de cliente en MyPresta.eu.

-   **Actualizaciones del Módulo:** Inicie sesión en su cuenta en [Historial de Pedidos y Descargas de MyPresta.eu](https://mypresta.eu/my-account/orders/) para descargar las versiones más recientes del módulo "API de Conversiones de Etiquetas de Amazon Ads".
-   **Soporte Técnico:** Si encuentra algún problema o tiene preguntas sobre la funcionalidad, configuración o integración del módulo, abra un ticket de soporte a través de su cuenta de cliente de MyPresta.eu. Nuestro equipo de expertos está listo para ayudarle.
