---
title: "Abandoned Cart Reminder Pro – drip emails, discount codes & ROI - Manual de Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop Abandoned Cart Reminder Pro – drip emails, discount codes & ROI de MyPresta.eu."
sidebar:
  label: "Abandoned Cart Reminder Pro – drip emails, discount codes & ROI - Manual de Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Abandoned Cart Reminder Pro – drip emails, discount codes & ROI en MyPresta.eu](https://mypresta.eu/modules/advertising-and-marketing/abandoned-cart-reminder-pro-drip-emails-discount-codes-roi.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/advertising-marketing/abandoned-cart-reminder-pro-drip-emails-discount-codes-roi/)
>
> ---


# Abandoned Cart Reminder Pro – drip emails, discount codes & ROI

## 1. Requisitos y Compatibilidad

- **Versiones de PrestaShop Compatibles**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilidad con PHP**: PHP 7.1 - 8.5 (El módulo está escrito pensando en PHP 5.6+, pero PrestaShop 9.x requiere PHP 8.1+ para la tienda misma. Recomendamos usar la versión de PHP estable más alta compatible con tu instalación de PrestaShop, hasta 8.5.)
- **Requisitos de Alojamiento**: Se requieren extensiones PHP estándar como cURL, JSON y OpenSSL. Tu entorno de alojamiento también debe admitir tareas cron (tareas programadas) para que el módulo funcione correctamente, ya que procesa los recordatorios en segundo plano.

## 2. Recorrido Completo por la Configuración (Cada Ajuste Agrupado por Pantalla)

El módulo "Abandoned Cart Reminder Pro" ofrece un conjunto completo de herramientas para gestionar tus campañas. Interactuarás principalmente con sus elementos de menú dedicados en el Back Office de PrestaShop.

### 2.1 Página de Configuración del Módulo (Back Office > Módulos > Configurar)

Aunque el módulo tiene pantallas de administración dedicadas, el botón inicial "Configurar" del Gestor de Módulos puede llevar a una configuración básica o a una redirección. El módulo aprovecha la clave de configuración `PS_SSL_ENABLED` de PrestaShop.

- **Qué hace este ajuste:** Este ajuste no está directamente controlado por el módulo, sino que es una configuración central de PrestaShop que indica si tu tienda utiliza HTTPS (conexión segura). El módulo se basa en esto para generar enlaces correctos y seguros en tus correos electrónicos de recordatorio.
- **Efecto de cambiar este ajuste:**
  - *Cuando `PS_SSL_ENABLED` es SÍ:* Todos los enlaces generados por el módulo (por ejemplo, a carritos abandonados, páginas de exclusión voluntaria) usarán `https://`, asegurando una experiencia segura y confiable para tus clientes.
  - *Cuando `PS_SSL_ENABLED` es NO:* Los enlaces podrían generarse usando `http://`, lo cual es menos seguro y puede activar advertencias del navegador, reduciendo potencialmente la confianza del cliente y las tasas de conversión.
- **Valor recomendado:** **SÍ**. Tu tienda siempre debe usar SSL por razones de seguridad y SEO. Asegúrate de que toda tu tienda funcione con HTTPS.
- **Escenario / ejemplo de comerciante:** Si tus clientes reciben un correo electrónico con un enlace `http://` a su carrito, su navegador podría mostrar una advertencia de "No seguro". Esto puede hacer que duden en hacer clic en el enlace o completar la compra, incluso si tu proceso de pago es seguro. Utiliza siempre HTTPS.

### 2.2 Pantallas de Administración Dedicadas y Vistas de Controlador

Una vez instalado el módulo, encontrarás un nuevo elemento de menú en tu Back Office de PrestaShop, normalmente bajo **Marketing** o una sección dedicada para "Abandoned Cart Reminder Pro". Este menú te llevará a varias subsecciones:

#### 2.2.1 Campañas (Back Office > Abandoned Cart Reminder Pro > Campañas)

Aquí es donde creas, gestionas y optimizas tus campañas de recordatorio de carritos abandonados.

- **Nombre de la Pantalla y Ubicación del Menú:** **Abandoned Cart Reminder Pro > Campañas**
- **Acciones y Configuraciones Disponibles:**
  - **Lista de Campañas:** Una tabla que muestra todas tus campañas activas e inactivas, incluyendo su nombre, estado y estadísticas clave.
  - **Añadir Nueva Campaña:** Haz clic para crear una nueva secuencia de correos electrónicos de varios pasos.
    - **Nombre de la Campaña:** Un nombre descriptivo para tu referencia interna (por ejemplo, "Recordatorio Estándar de 2 Pasos", "Descuento para Carrito de Alto Valor").
    - **Reglas de Segmentación:**
      - **Valor Mínimo del Carrito:** Establece un valor total mínimo para que un carrito sea elegible para esta campaña.
        - *Efecto:* Los carritos por debajo de este valor no recibirán correos electrónicos de esta campaña.
        - *Escenario de Comerciante:* Crea una campaña específicamente para carritos de alto valor, quizás ofreciendo un descuento mayor.
      - **Grupos de Clientes:** Dirige la campaña a grupos de clientes específicos (por ejemplo, "Visitantes", "Clientes", "Mayoristas").
        - *Efecto:* Solo los clientes que pertenecen a los grupos seleccionados recibirán correos electrónicos.
        - *Escenario de Comerciante:* Envía diferentes recordatorios a nuevos visitantes frente a clientes leales, o excluye a clientes B2B si tienen un proceso de compra diferente.
      - **Productos en el Carrito:** Dirige la campaña a carritos que contengan productos específicos o productos de ciertas categorías.
        - *Efecto:* Solo los carritos con los productos especificados activarán la campaña.
        - *Escenario de Comerciante:* Crea una campaña para clientes que abandonaron un carrito con un producto específico de alto margen.
    - **Pasos de la Campaña (Correos Electrónicos por Goteo):** Define la secuencia de correos electrónicos a enviar.
      - **Retraso:** Cuánto tiempo después del abandono del carrito debe enviarse este correo electrónico (por ejemplo, 1 hora, 24 horas, 3 días).
        - *Efecto:* Controla el momento de tu seguimiento.
        - *Escenario de Comerciante:* Envía un recordatorio rápido después de 1 hora, uno más fuerte con un descuento después de 24 horas y uno final después de 3 días.
      - **Asunto del Correo Electrónico:** La línea de asunto del correo electrónico (admite varios idiomas).
      - **Contenido del Correo Electrónico (Constructor de Correos):** Diseña el cuerpo de tu correo electrónico usando un editor de texto enriquecido. Puedes incluir marcadores de posición dinámicos como el nombre del cliente, el enlace del carrito, la lista de productos y los códigos de descuento.
      - **Código de Descuento:** Opción para generar un código de descuento único y de un solo uso para este correo electrónico específico.
        - *Efecto:* Se crea un código de cupón único y se incluye en el correo electrónico, fomentando la conversión.
        - *Escenario de Comerciante:* Ofrece un 10% de descuento en el segundo correo electrónico de recordatorio para incentivar la finalización.
      - **Pruebas A/B:** Crea variaciones del asunto o contenido de tu correo electrónico para probar cuál funciona mejor.
        - *Efecto:* El módulo dividirá los envíos entre las variaciones y rastreará las tasas de conversión, permitiéndote optimizar tus campañas.
        - *Escenario de Comerciante:* Prueba dos líneas de asunto diferentes para ver cuál obtiene una mayor tasa de apertura.
  - **Editar/Duplicar/Eliminar Campañas:** Gestiona las campañas existentes. Duplicar es útil para crear campañas similares rápidamente.
- **Efecto de los cambios:** Los cambios aquí impactan directamente qué clientes reciben correos electrónicos de recordatorio, cuándo los reciben, qué contenido ven y si reciben códigos de descuento. Las campañas bien configuradas pueden aumentar significativamente la tasa de recuperación de tu tienda.
- **Flujo de trabajo recomendado para la gestión diaria de la tienda:**
  1. Comienza con una campaña simple de 2 pasos: un recordatorio después de 1-2 horas (sin descuento) y otro después de 24 horas (con un pequeño descuento).
  2. Monitoriza tu Panel de Control (ver 4.2.2) para ver qué campañas están funcionando mejor.
  3. Experimenta con pruebas A/B en las líneas de asunto o los montos de descuento para optimizar las tasas de conversión.
  4. Considera crear campañas dirigidas a segmentos de clientes específicos o productos de alto valor.

#### 2.2.2 Panel de Control (Back Office > Abandoned Cart Reminder Pro > Panel de Control)

Esta pantalla proporciona una visión general clara del rendimiento de tu módulo y las estadísticas clave.

- **Nombre de la Pantalla y Ubicación del Menú:** **Abandoned Cart Reminder Pro > Panel de Control**
- **Acciones y Configuraciones Disponibles:**
  - **Indicadores Clave de Rendimiento (KPIs):** Muestra métricas como:
    - **Carritos Abandonados:** Número total de carritos abandonados.
    - **Correos Electrónicos Enviados:** Número de correos electrónicos de recordatorio enviados.
    - **Carritos Recuperados:** Número de carritos abandonados que resultaron en un pedido completado después de recibir un recordatorio.
    - **Tasa de Recuperación:** Porcentaje de carritos abandonados recuperados.
    - **Ingresos Atribuidos:** Los ingresos totales generados por los carritos recuperados.
    - **ROI:** Retorno de la Inversión para tus campañas.
  - **Desglose del Rendimiento de la Campaña:** Una representación visual (por ejemplo, gráficos) de cómo están funcionando las campañas individuales.
  - **Actividad Reciente:** Un vistazo rápido a los carritos abandonados recientemente, los correos electrónicos enviados y los pedidos recuperados.
- **Efecto de los cambios:** Esta es una pantalla de informes; no realizas cambios directos aquí, pero los datos te ayudan a comprender el impacto de tus campañas y guían tus esfuerzos de optimización en la sección "Campañas".
- **Flujo de trabajo recomendado para la gestión diaria de la tienda:** Revisa este panel de control regularmente (por ejemplo, semanalmente) para identificar tendencias, ver qué campañas son más efectivas y detectar cualquier problema. Utiliza estos datos para refinar tus estrategias de campaña.

#### 2.2.3 Registros (Back Office > Abandoned Cart Reminder Pro > Registros)

La sección de Registros proporciona un historial detallado de todas las acciones realizadas por el módulo, ayudándote a solucionar problemas y verificar su funcionamiento.

- **Nombre de la Pantalla y Ubicación del Menú:** **Abandoned Cart Reminder Pro > Registros**
- **Acciones y Configuraciones Disponibles:**
  - **Cuadrícula de Entradas de Registro:** Una tabla con capacidad de búsqueda y filtrado que muestra:
    - **Marca de Tiempo:** Cuándo ocurrió el evento.
    - **Cliente:** El cliente asociado con el evento.
    - **ID del Carrito:** El ID del carrito abandonado.
    - **Campaña/Paso:** Qué campaña y paso activaron el evento.
    - **Tipo de Evento:** (por ejemplo, "Carrito Abandonado", "Correo Enviado", "Correo Abierto", "Enlace Clicado", "Carrito Recuperado", "Descuento Aplicado").
    - **Estado:** Éxito o fallo.
    - **Detalles:** Información adicional, como la vista previa del contenido del correo electrónico o mensajes de error.
  - **Vista Previa del Correo Electrónico:** Opción para ver el contenido exacto de un correo electrónico que fue enviado.
- **Efecto de los cambios:** Esta es una pantalla de diagnóstico y auditoría. No realizas cambios aquí, pero es crucial para entender por qué un cliente podría no haber recibido un correo electrónico o si una campaña no está funcionando como se esperaba.
- **Flujo de trabajo recomendado para la gestión diaria de la tienda:** Si un cliente informa que no recibió un correo electrónico, o si tu tasa de recuperación cae inesperadamente, revisa los registros. Puedes ver si los correos electrónicos se enviaron correctamente, si hubo algún error o si los clientes se dieron de baja.

#### 2.2.4 Ajustes (Back Office > Abandoned Cart Reminder Pro > Ajustes)

Esta pantalla contiene configuraciones globales que afectan el comportamiento general del módulo.

- **Nombre de la Pantalla y Ubicación del Menú:** **Abandoned Cart Reminder Pro > Ajustes**
- **Acciones y Configuraciones Disponibles:**
  - **Configuración General:**
    - **Habilitar Módulo:** Activa o desactiva todo el módulo.
      - *Efecto:* Cuando está deshabilitado, no se rastrearán carritos ni se enviarán correos electrónicos.
      - *Recomendado:* SÍ, a menos que lo estés deshabilitando temporalmente por mantenimiento.
    - **Valor Mínimo del Carrito para el Seguimiento:** Establece un valor mínimo global del carrito para que cualquier carrito sea considerado "abandonado" y rastreado por el módulo.
      - *Efecto:* Los carritos por debajo de este valor serán ignorados por todas las campañas.
      - *Escenario de Comerciante:* Evita enviar recordatorios para carritos muy pequeños donde el esfuerzo de recuperación podría no valer la pena.
    - **Tiempo para Considerar el Carrito Abandonado:** Cuánto tiempo después de la última actividad del carrito debe considerarse un carrito abandonado (por ejemplo, 30 minutos, 1 hora).
      - *Efecto:* Esto determina cuándo el módulo comienza a contar el retraso para el primer correo electrónico de recordatorio.
      - *Recomendado:* 30-60 minutos. Demasiado corto podría molestar a los clientes, demasiado largo podría perder la ventana de oportunidad.
    - **Límites Anti-Spam:**
      - **Máximo de Correos Electrónicos por Cliente:** Limita el número total de correos electrónicos de carrito abandonado que un solo cliente puede recibir durante un período (por ejemplo, 3 correos electrónicos cada 30 días).
        - *Efecto:* Evita que los clientes se sientan abrumados por demasiados correos electrónicos, reduciendo las tasas de cancelación de suscripción.
        - *Recomendado:* Establece límites razonables para mantener una experiencia positiva para el cliente.
      - **Tiempo Mínimo entre Correos Electrónicos:** Asegura un retraso mínimo entre dos correos electrónicos enviados al mismo cliente.
        - *Efecto:* Evita que se envíen varios correos electrónicos de diferentes campañas demasiado juntos.
    - **Configuración GDPR / Exclusión Voluntaria:**
      - **Habilitar Enlace de Exclusión Voluntaria:** Incluye un enlace en los correos electrónicos de recordatorio que permite a los clientes darse de baja de futuros recordatorios.
        - *Efecto:* Crucial para el cumplimiento del GDPR y el respeto de la privacidad del cliente.
        - *Recomendado:* SÍ.
      - **Contenido de la Página de Exclusión Voluntaria:** Personaliza el texto que se muestra en la página de confirmación de exclusión voluntaria.
    - **URL de la Tarea Cron:** Muestra la URL exacta que necesitas configurar como tarea cron en tu servidor.
      - *Efecto:* Esta URL activa el procesamiento en segundo plano del módulo, enviando correos electrónicos y actualizando estadísticas.
      - *Recomendado:* Copia esta URL y configura la tarea cron de tu servidor para que se ejecute cada 5-15 minutos.
  - **Configuración de Correo Electrónico:**
    - **Nombre y Correo Electrónico del Remitente:** El nombre y la dirección de correo electrónico que aparecerán como remitente de tus correos electrónicos de recordatorio.
      - *Efecto:* Impacta la entregabilidad del correo electrónico y cómo los clientes perciben tu marca.
      - *Recomendado:* Utiliza un nombre de tienda reconocible y una dirección de correo electrónico profesional (por ejemplo, `ventas@tutienda.com`, `noreply@tutienda.com`).
    - **Plantilla de Correo Electrónico:** Elige una plantilla base para tus correos electrónicos de recordatorio (si hay varias disponibles).
      - *Efecto:* Determina el diseño y la disposición general de tus correos electrónicos.
  - **Configuración Avanzada:**
    - **Modo Depuración:** Habilita el registro detallado (para desarrolladores).
      - *Efecto:* Proporciona información más detallada en los registros, útil para la resolución de problemas.
      - *Recomendado:* NO, a menos que lo solicite específicamente el soporte.
- **Efecto de los cambios:** Estos ajustes controlan el comportamiento fundamental del módulo, desde cuándo rastrea los carritos hasta cómo respeta la privacidad del cliente y envía correos electrónicos. Una configuración incorrecta puede llevar a oportunidades perdidas o a una mala experiencia del cliente.
- **Flujo de trabajo recomendado para la gestión diaria de la tienda:** Revisa estos ajustes durante la configuración inicial y periódicamente para asegurarte de que se alinean con las políticas y la estrategia de marketing de tu tienda. Presta mucha atención a la configuración anti-spam y GDPR.

#### 2.2.5 index.php (cartrempro/controllers/admin/index.php)

Este archivo es una práctica estándar de PrestaShop para evitar la lista directa de directorios en las carpetas de administración y, por lo general, no representa una pantalla configurable en sí misma. Garantiza la seguridad al redirigir o mostrar una página en blanco si alguien intenta acceder a la carpeta directamente.

### 2.3 Tabla de Referencia Rápida de Configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| **Configuración del Módulo** | `PS_SSL_ENABLED` (Núcleo de PrestaShop) | SÍ | Asegura enlaces HTTPS seguros en los correos electrónicos. |
| **Campañas** | Nombre de la Campaña | Descriptivo | Identificación interna de tus campañas. |
| | Valor Mínimo del Carrito | 0 (o tu umbral) | Filtra carritos según su valor para campañas específicas. |
| | Grupos de Clientes | Todos (o específicos) | Dirige la campaña a segmentos de clientes específicos. |
| | Productos en el Carrito | Ninguno (o específicos) | Dirige la campaña a carritos que contienen productos/categorías específicos. |
| | Retraso del Paso de la Campaña | 1h, 24h, 3d | Controla el momento de los correos electrónicos de recordatorio. |
| | Asunto del Correo Electrónico | Atractivo | Crucial para las tasas de apertura. |
| | Contenido del Correo Electrónico | Personalizado | Mensaje principal para recuperar el carrito. |
| | Código de Descuento | Opcional | Incentivo para la conversión. |
| | Pruebas A/B | Opcional | Optimiza el rendimiento de la campaña. |
| **Panel de Control** | Todos los KPIs | N/A (Informes) | Proporciona una visión general del rendimiento y el ROI. |
| **Registros** | Todas las Entradas de Registro | N/A (Informes) | Historial detallado para solución de problemas y auditoría. |
| **Ajustes** | Habilitar Módulo | SÍ | Activa/desactiva el módulo. |
| | Valor Mínimo del Carrito para el Seguimiento | 0 (o tu umbral) | Filtro global para todos los carritos rastreados. |
| | Tiempo para Considerar el Carrito Abandonado | 30-60 minutos | Define cuándo un carrito está "abandonado". |
| | Máximo de Correos Electrónicos por Cliente | Límite razonable | Evita el envío de spam a los clientes. |
| | Tiempo Mínimo entre Correos Electrónicos | Límite razonable | Evita el envío rápido de correos electrónicos. |
| | Habilitar Enlace de Exclusión Voluntaria | SÍ | Cumplimiento del GDPR, elección del cliente. |
| | URL de la Tarea Cron | Copiar del módulo | **CRÍTICO:** Habilita el procesamiento en segundo plano. |
| | Nombre y Correo Electrónico del Remitente | Nombre de tu Tienda, correo electrónico profesional | Impacta la entregabilidad y la confianza en la marca. |
| | Modo Depuración | NO | Solo para solución de problemas de desarrolladores. |

## 3. Solución de Problemas para Comerciantes y Preguntas Frecuentes (FAQ)

**P1: Mis clientes no reciben correos electrónicos de recordatorio. ¿Qué debo verificar?**
R1:

- **Tarea Cron:** Este es el problema más común. Asegúrate de que tu tarea cron esté configurada correctamente en tu servidor y se ejecute regularmente (cada 5-15 minutos). La URL exacta se encuentra en **Abandoned Cart Reminder Pro > Ajustes**.
- **Módulo Habilitado:** Verifica en **Abandoned Cart Reminder Pro > Ajustes** que el módulo esté habilitado globalmente.
- **Campañas Activas:** Verifica que tus campañas estén habilitadas y tengan pasos activos en **Abandoned Cart Reminder Pro > Campañas**.
- **Configuración de Correo Electrónico:** Revisa la configuración de correo electrónico de tu PrestaShop (Parámetros Avanzados > E-mail) para asegurarte de que tu tienda pueda enviar correos electrónicos en general.
- **Filtros de Spam:** Pide a un cliente de prueba que revise su carpeta de spam/correo no deseado. Asegúrate de que tu dirección de correo electrónico del remitente sea profesional y no esté en una lista negra.
- **Registros:** Ve a **Abandoned Cart Reminder Pro > Registros** para ver si los correos electrónicos están en cola, enviados o si hay algún mensaje de error.

**P2: ¿Por qué algunos carritos abandonados no activan una campaña?**
R2:

- **Valor Mínimo del Carrito:** Verifica el "Valor Mínimo del Carrito para el Seguimiento" global en **Abandoned Cart Reminder Pro > Ajustes** y el "Valor Mínimo del Carrito" específico para tus campañas en **Abandoned Cart Reminder Pro > Campañas**. Los carritos por debajo de estos valores serán ignorados.
- **Tiempo para Considerar el Carrito Abandonado:** Asegúrate de que el tiempo establecido en **Abandoned Cart Reminder Pro > Ajustes** haya transcurrido desde la última actividad del carrito.
- **Grupos de Clientes/Segmentación de Productos:** Si tu campaña tiene una segmentación específica por grupo de clientes o producto, asegúrate de que el carrito abandonado cumpla esos criterios.
- **Límites Anti-Spam:** El cliente podría haber alcanzado los límites de "Máximo de Correos Electrónicos por Cliente" o "Tiempo Mínimo entre Correos Electrónicos" establecidos en **Abandoned Cart Reminder Pro > Ajustes**.
- **Exclusión Voluntaria del Cliente:** El cliente podría haberse dado de baja previamente de recibir recordatorios. Revisa los registros.

**P3: ¿Cómo me aseguro de que los correos electrónicos de recordatorio se vean bien en dispositivos móviles?**
R3: El módulo utiliza plantillas de correo electrónico responsivas. Sin embargo, el contenido que añades en el constructor de correos puede afectar esto.

- **Mantenlo simple:** Evita diseños excesivamente complejos o imágenes muy anchas.
- **Prueba:** Siempre envíate un correo electrónico de prueba y visualízalo en diferentes dispositivos (escritorio, tableta, teléfono) antes de activar una campaña.
- **Tema de PrestaShop:** Asegúrate de que tu tema principal de PrestaShop sea adaptable a dispositivos móviles, ya que los enlaces en los correos electrónicos te llevarán de vuelta a tu tienda.

**P4: ¿Puedo traducir el contenido del correo electrónico y las líneas de asunto?**
R4: ¡Sí! Al editar un paso de campaña, verás pestañas de idioma para el asunto y el contenido del correo electrónico. Puedes proporcionar diferentes traducciones para cada idioma instalado en tu tienda PrestaShop. Esto es crucial para tiendas internacionales.

**P5: Borré mi caché de Smarty y ahora algo no se ve bien. ¿Qué pasó?**
R5: Borrar la caché de Smarty (en **Parámetros Avanzados > Rendimiento**) es un paso común para solucionar problemas de visualización. Aunque generalmente es seguro, a veces puede afectar temporalmente cómo los módulos renderizan su contenido hasta que se reconstruye la caché. Si notas problemas de visualización después de borrar la caché, intenta actualizar la página varias veces o volver a guardar la configuración del módulo (incluso sin cambiar nada) para forzar una reconstrucción de la caché para el módulo. Este módulo utiliza sus propios mecanismos de caché, por lo que borrar la caché de Smarty no debería afectar directamente su funcionalidad principal, sino la visualización de su interfaz de administración.

## 4. Guía para Desarrolladores y Webmasters (Arquitectura Técnica y Mapa de Código)

Esta sección proporciona una inmersión profunda en la estructura técnica del módulo "Abandoned Cart Reminder Pro" para desarrolladores, webmasters y agencias técnicas.

### 4.1 Visión General de la Arquitectura

El módulo sigue una arquitectura robusta y basada en eventos que se adhiere al patrón MVC de PrestaShop cuando es apropiado, pero también aprovecha un contenedor de servicios personalizado y la autocarga para una mejor organización y capacidad de prueba. Depende en gran medida de las tareas cron para el procesamiento en segundo plano, asegurando que el envío de correos electrónicos y el seguimiento de carritos no afecten el rendimiento del front-office. Los componentes clave incluyen:

- **Seguimiento de Carritos:** Se engancha a `ActionCartSave` y `ActionValidateOrder` para monitorear el estado del carrito.
- **Motor de Campañas:** Gestiona secuencias de correo electrónico de varios pasos, segmentación y generación de descuentos.
- **Procesador de Cola:** Maneja el envío asíncrono de correos electrónicos a través de cron.
- **Análisis y Atribución:** Rastrea las tasas de recuperación y los ingresos.
- **Controladores de Administración:** Controladores dedicados para gestionar campañas, ver registros y configurar ajustes.
- **Cumplimiento del GDPR:** Incluye un mecanismo de exclusión voluntaria.

### 4.2 Controladores (`controllers/`)

#### Controladores de Front-Office

Estos controladores manejan interacciones específicas del front-office, principalmente para la ejecución de cron, el seguimiento y la exclusión voluntaria.

- `controllers/front/cron.php`
  - **Nombre de la Clase:** `CartRemProCronModuleFrontController` (extiende `ModuleFrontController`)
  - **Responsabilidad:** Este es el punto final principal para la tarea cron del módulo. Cuando se accede, activa el `CartRemProQueueProcessor` para procesar la cola de carritos abandonados, enviar correos electrónicos programados y actualizar estadísticas. Está diseñado para ser llamado por una tarea cron del lado del servidor, no directamente por los usuarios.
- `controllers/front/index.php`
  - **Nombre de la Clase:** `CartRemProIndexModuleFrontController` (extiende `ModuleFrontController`)
  - **Responsabilidad:** Una práctica estándar de PrestaShop para evitar la lista directa de directorios. Normalmente redirige a la página de inicio de la tienda o muestra una página en blanco.
- `controllers/front/optout.php`
  - **Nombre de la Clase:** `CartRemProOptoutModuleFrontController` (extiende `ModuleFrontController`)
  - **Responsabilidad:** Maneja las solicitudes de los clientes para darse de baja de los recordatorios de carritos abandonados. Procesa la acción `optout`, actualiza la preferencia del cliente y muestra una página de confirmación (`optout.tpl`).
- `controllers/front/track.php`
  - **Nombre de la Clase:** `CartRemProTrackModuleFrontController` (extiende `ModuleFrontController`)
  - **Responsabilidad:** Se utiliza para rastrear las aperturas de correos electrónicos y los clics en enlaces dentro de los correos electrónicos de recordatorio. Registra estos eventos en los registros del módulo, lo que permite el análisis del compromiso con el correo electrónico.

#### Controladores de Administración del Back-Office

Estos controladores gestionan la interfaz del módulo en el Back Office de PrestaShop.

- `controllers/admin/AdminCartRemProCampaignsController.php`
  - **Nombre de la Pestaña:** Abandoned Cart Reminder Pro > Campañas
  - **Responsabilidad:** Gestiona la creación, edición, duplicación y eliminación de campañas de carritos abandonados. Maneja el envío de formularios para los detalles de la campaña, los pasos, las reglas de segmentación y las configuraciones de pruebas A/B. Interactúa con las clases `CartRemProCampaign` y `CartRemProCampaignStep`.
- `controllers/admin/AdminCartRemProDashboardController.php`
  - **Nombre de la Pestaña:** Abandoned Cart Reminder Pro > Panel de Control
  - **Responsabilidad:** Muestra las métricas de rendimiento del módulo, incluidos los carritos abandonados, los carritos recuperados, los ingresos atribuidos y el ROI. Agrega datos de `CartRemProAnalytics` y `CartRemProAbandoned` para presentar una visión general completa.
- `controllers/admin/AdminCartRemProLogsController.php`
  - **Nombre de la Pestaña:** Abandoned Cart Reminder Pro > Registros
  - **Responsabilidad:** Proporciona un registro detallado de todas las actividades del módulo, como abandonos de carritos, envíos de correos electrónicos, aperturas, clics y recuperaciones. Permite filtrar y buscar en estos registros para solucionar problemas y auditar.
- `controllers/admin/AdminCartRemProSettingsController.php`
  - **Nombre de la Pestaña:** Abandoned Cart Reminder Pro > Ajustes
  - **Responsabilidad:** Gestiona la configuración global del módulo, incluida la activación/desactivación, los límites anti-spam, las opciones de GDPR y la visualización de la URL de la tarea cron. Interactúa con la clase `Configuration` de PrestaShop.
- `controllers/admin/index.php`
  - **Responsabilidad:** Archivo de seguridad estándar de PrestaShop para evitar la lista directa de directorios.

### 4.3 Clases y Modelos Principales (`classes/`)

El módulo utiliza un rico conjunto de clases personalizadas para su lógica de negocio, muchas de las cuales extienden `ObjectModel` para la interacción con la base de datos.

- `classes/CartRemProAbandoned.php`
  - **Tabla de Base de Datos:** `ps_cartrempro_abandoned`
  - **Extiende:** `ObjectModel`
  - **Campos `$definition`:** `id_cart`, `id_customer`, `id_shop`, `id_lang`, `cart_value`, `date_add`, `date_upd`, `is_recovered`, `is_optout`
  - **Métodos Públicos Clave:** Gestiona el seguimiento y el estado de los carritos abandonados.
- `classes/CartRemProAbTesting.php`
  - **Responsabilidad:** Maneja la lógica para las pruebas A/B dentro de los pasos de la campaña, incluida la división del tráfico y el seguimiento de las tasas de conversión para diferentes variaciones.
- `classes/CartRemProAdminController.php`
  - **Extiende:** `ModuleAdminController`
  - **Responsabilidad:** Una clase base para los controladores de administración del módulo, que proporciona funcionalidades y utilidades comunes específicas de la interfaz de back-office del módulo.
- `classes/CartRemProAdminUi.php`
  - **Responsabilidad:** Clase auxiliar para generar y renderizar elementos de interfaz de usuario comunes en el panel de administración, asegurando la coherencia.
- `classes/CartRemProAnalytics.php`
  - **Responsabilidad:** Recopila y procesa datos para el panel de control, calculando KPIs como la tasa de recuperación, los ingresos atribuidos y el ROI.
- `classes/CartRemProAntiSpam.php`
  - **Responsabilidad:** Implementa la lógica para los límites anti-spam, asegurando que los clientes no reciban demasiados correos electrónicos en un período determinado.
- `classes/CartRemProAttribution.php`
  - **Responsabilidad:** Determina si un carrito recuperado puede atribuirse a una campaña específica de recordatorio de carrito abandonado.
- `classes/CartRemProAutoload.php`
  - **Responsabilidad:** Autocargador personalizado para las clases del módulo, asegurando que se carguen de manera eficiente sin entrar en conflicto con el autocargador predeterminado de PrestaShop.
- `classes/CartRemProCampaign.php`
  - **Tabla de Base de Datos:** `ps_cartrempro_campaign`
  - **Extiende:** `ObjectModel`
  - **Campos `$definition`:** `name`, `active`, `min_cart_value`, `customer_groups`, `products`, `categories`, `date_add`, `date_upd`
  - **Métodos Públicos Clave:** Representa una campaña de carrito abandonado, gestionando su configuración, reglas de segmentación y pasos asociados.
- `classes/CartRemProCampaignEngine.php`
  - **Responsabilidad:** La lógica central para evaluar los carritos abandonados frente a las campañas activas, determinando qué campaña (si la hay) debe activarse y programando el siguiente paso del correo electrónico.
- `classes/CartRemProCampaignStep.php`
  - **Tabla de Base de Datos:** `ps_cartrempro_campaign_step`
  - **Extiende:** `ObjectModel`
  - **Campos `$definition`:** `id_cartrempro_campaign`, `delay_hours`, `subject`, `content`, `discount_type`, `discount_value`, `ab_test_active`, `ab_test_variations`
  - **Métodos Públicos Clave:** Define un solo paso dentro de una campaña, incluido el contenido del correo electrónico, el retraso y el descuento.
- `classes/CartRemProCartTracker.php`
  - **Responsabilidad:** Monitorea los carritos de los clientes, identifica cuándo se abandonan y los registra en la tabla `ps_cartrempro_abandoned`.
- `classes/CartRemProChannelEmail.php`
  - **Implementa:** `CartRemProChannelInterface`
  - **Responsabilidad:** Maneja el envío real de correos electrónicos de recordatorio, incluida la renderización de plantillas de correo electrónico y la integración con la clase `Mail` de PrestaShop.
- `classes/CartRemProChannelInterface.php`
  - **Responsabilidad:** Define una interfaz común para diferentes canales de comunicación (actualmente solo correo electrónico, pero extensible para SMS, notificaciones push web).
- `classes/CartRemProCompat.php`
  - **Responsabilidad:** Proporciona capas de compatibilidad para diferentes versiones de PrestaShop (1.7, 8.x, 9.x) para garantizar un funcionamiento fluido en todo el rango compatible.
- `classes/CartRemProDiscountGenerator.php`
  - **Responsabilidad:** Crea códigos de descuento únicos y de un solo uso (Reglas de Carrito) para los clientes que reciben un correo electrónico de recordatorio con una oferta de descuento.
- `classes/CartRemProEmailRenderer.php`
  - **Responsabilidad:** Renderiza las plantillas Smarty para los correos electrónicos de recordatorio, inyectando datos dinámicos como detalles del carrito, información del cliente y códigos de descuento.
- `classes/CartRemProGdpr.php`
  - **Responsabilidad:** Gestiona las características de cumplimiento del GDPR, particularmente el mecanismo de exclusión voluntaria del cliente.
- `classes/CartRemProProductBlocks.php`
  - **Responsabilidad:** Ayuda a generar bloques relacionados con productos dentro de las plantillas de correo electrónico, como listas de productos de carritos abandonados o productos recomendados.
- `classes/CartRemProQueueProcessor.php`
  - **Responsabilidad:** El corazón de la tarea cron. Recupera las tareas programadas de la cola (por ejemplo, enviar correo electrónico, verificar el estado del carrito), las procesa y actualiza los registros.
- `classes/CartRemProScheduleGuard.php`
  - **Responsabilidad:** Asegura que las tareas programadas se ejecuten solo una vez y dentro de sus plazos previstos, evitando correos electrónicos o acciones duplicadas.
- `classes/CartRemProSegmentation.php`
  - **Responsabilidad:** Implementa la lógica para segmentar clientes y carritos según las reglas de segmentación de la campaña (por ejemplo, valor del carrito, grupo de clientes, productos).
- `classes/CartRemProServiceContainer.php`
  - **Responsabilidad:** Un contenedor de inyección de dependencias personalizado para gestionar y proporcionar instancias de los servicios y clases principales del módulo, mejorando la modularidad y la capacidad de prueba.
- `classes/CartRemProStockChecker.php`
  - **Responsabilidad:** Verifica los niveles de stock de los productos antes de enviar recordatorios para asegurar que los artículos en un carrito abandonado sigan disponibles.
- `classes/CartRemProTabInstaller.php`
  - **Responsabilidad:** Maneja la instalación y desinstalación de las pestañas del menú de administración del módulo en el Back Office de PrestaShop.
- `classes/index.php`
  - **Responsabilidad:** Archivo de seguridad estándar de PrestaShop para evitar la lista directa de directorios.

### 4.4 Activos JavaScript (`views/js/`)

- `cartrempro/devtools/crp-ab-stats-demo-console.js`
  - **Alcance:** Back-office (herramientas de desarrollador)
  - **Responsabilidad:** Probablemente un script de tiempo de desarrollo para demostrar o depurar estadísticas de pruebas A/B en la consola del navegador. No para uso en producción.
- `cartrempro/devtools/crp-dashboard-demo-console.js`
  - **Alcance:** Back-office (herramientas de desarrollador)
  - **Responsabilidad:** Similar al anterior, para demostrar o depurar datos del panel de control. No para uso en producción.
- `cartrempro/lib/searchTool/views/js/autocomplete.js`
  - **Alcance:** Back-office (formularios de administración)
  - **Responsabilidad:** Proporciona funcionalidad de autocompletado para campos de entrada, probablemente utilizada para seleccionar productos o categorías en la segmentación de campañas. Se vincula a eventos de entrada y realiza llamadas AJAX para sugerencias de búsqueda.
- `cartrempro/views/js/admin-common.js`
  - **Alcance:** Back-office (administración global)
  - **Responsabilidad:** Contiene funciones JavaScript comunes y oyentes de eventos utilizados en varias pantallas de administración del módulo, como el manejo general de formularios, funciones de utilidad AJAX y mejoras de la interfaz de usuario.
- `cartrempro/views/js/admin-dashboard.js`
  - **Alcance:** Back-office (Panel de Control)
  - **Responsabilidad:** Maneja los elementos interactivos y la visualización de datos en el panel de control del módulo, potencialmente renderizando gráficos o actualizando estadísticas dinámicamente.
- `cartrempro/views/js/campaigns-admin.js`
  - **Alcance:** Back-office (Campañas)
  - **Responsabilidad:** Gestiona la compleja interfaz de usuario para la creación y edición de campañas, incluida la adición/eliminación de pasos de campaña, la configuración de reglas de segmentación, el manejo de opciones de descuento y la gestión de variaciones de pruebas A/B. Se vincula a eventos de clic en botones, eventos de cambio en cuadros de selección y envíos de formularios.
- `cartrempro/views/js/email-builder.js`
  - **Alcance:** Back-office (Campañas - Contenido del Correo Electrónico)
  - **Responsabilidad:** Mejora el editor de texto enriquecido utilizado para el contenido del correo electrónico, potencialmente añadiendo botones personalizados para marcadores de posición dinámicos (por ejemplo, `{{customer_name}}`, `{{cart_link}}`) o proporcionando vistas previas en tiempo real.
- `cartrempro/views/js/logs-admin.js`
  - **Alcance:** Back-office (Registros)
  - **Responsabilidad:** Proporciona funciones interactivas para la tabla de registros, como filtrado, búsqueda, paginación y potencialmente ventanas emergentes modales para ver vistas previas de correos electrónicos.

### 4.5 Hojas de Estilo CSS (`views/css/`)

- `cartrempro/lib/searchTool/views/css/autocomplete.css`
  - **Alcance:** Back-office (formularios de administración)
  - **Componentes principales de la interfaz de usuario:** Estiliza las sugerencias desplegables de autocompletado y los campos de entrada utilizados en la herramienta de búsqueda.
  - **Selectores de clase CSS clave:** `.autocomplete-suggestions`, `.autocomplete-selected`, `.autocomplete-suggestion`
- `cartrempro/views/css/admin.css`
  - **Alcance:** Back-office (administración global)
  - **Componentes principales de la interfaz de usuario:** Proporciona un estilo general para la interfaz de administración del módulo, incluidos los diseños del panel de control, los formularios de campaña, las tablas de registro y el estilo general de botones/entradas.
  - **Selectores de clase CSS clave:** `.cartrempro-dashboard`, `.cartrempro-campaign-form`, `.cartrempro-logs-table`, `.crp-badge`, `.crp-stat-card`, etc.

### 4.6 Estructura de Plantillas Smarty (`views/templates/`)

#### Plantillas de gancho (`views/templates/hook/`)

El módulo no lista explícitamente plantillas en un directorio `hook/`, lo que sugiere que la renderización del front-office para los ganchos podría manejarse directamente dentro del archivo principal del módulo o a través de controladores frontales específicos.

#### Plantillas de administración (`views/templates/admin/`)

Estas plantillas renderizan la interfaz del Back Office del módulo.

- `cartrempro/views/templates/admin/ab_email_preview.tpl`
  - **Propósito:** Muestra una vista previa de una variación de correo electrónico de prueba A/B.
- `cartrempro/views/templates/admin/campaigns.tpl`
  - **Propósito:** La plantilla principal para la pantalla de administración de "Campañas", que lista las campañas y proporciona formularios para añadir/editar.
- `cartrempro/views/templates/admin/dashboard.tpl`
  - **Propósito:** La plantilla principal para la pantalla de "Panel de Control", que muestra los KPIs y los gráficos de rendimiento.
- `cartrempro/views/templates/admin/logs.tpl`
  - **Propósito:** La plantilla principal para la pantalla de "Registros", que presenta la tabla de actividades del módulo.
- `cartrempro/views/templates/admin/logs_email_preview.tpl`
  - **Propósito:** Muestra una vista previa de un correo electrónico de los registros.
- `cartrempro/views/templates/admin/settings.tpl`
  - **Propósito:** La plantilla principal para la pantalla de "Ajustes", que contiene las opciones de configuración global.
- `cartrempro/views/templates/admin/_partials/ab_stats.tpl`
  - **Propósito:** Renderiza estadísticas para las variaciones de pruebas A/B dentro de una campaña.
- `cartrempro/views/templates/admin/_partials/campaign_form.tpl`
  - **Propósito:** Parcial reutilizable para el formulario de creación/edición de campañas, incluidos los pasos, la segmentación y la configuración general.
- `cartrempro/views/templates/admin/_partials/campaign_list_compact.tpl`
  - **Propósito:** Renderiza una lista compacta de campañas, posiblemente para widgets del panel de control o vistas rápidas.
- `cartrempro/views/templates/admin/_partials/campaign_targeting.tpl`
  - **Propósito:** Renderiza la sección de reglas de segmentación dentro del formulario de campaña.
- `cartrempro/views/templates/admin/_partials/copy_box.tpl`
  - **Propósito:** Un componente reutilizable para mostrar texto que se puede copiar fácilmente (por ejemplo, la URL de la tarea cron).
- `cartrempro/views/templates/admin/_partials/empty_state.tpl`
  - **Propósito:** Muestra un mensaje cuando una lista o sección está vacía (por ejemplo, "No se encontraron campañas").
- `cartrempro/views/templates/admin/_partials/icon_duplicate.tpl`
  - **Propósito:** Renderiza un icono de duplicar.
- `cartrempro/views/templates/admin/_partials/icon_edit.tpl`
  - **Propósito:** Renderiza un icono de edición.
- `cartrempro/views/templates/admin/_partials/icon_trash.tpl`
  - **Propósito:** Renderiza un icono de papelera/eliminar.
- `cartrempro/views/templates/admin/_partials/page_header.tpl`
  - **Propósito:** Renderiza un encabezado consistente para las páginas de administración dentro del módulo.
- `cartrempro/views/templates/admin/_partials/status_badge.tpl`
  - **Propósito:** Renderiza una insignia visual que indica el estado (por ejemplo, "Activo", "Inactivo").
- `cartrempro/views/templates/admin/_partials/stat_card.tpl`
  - **Propósito:** Renderiza una única tarjeta estadística para el panel de control (por ejemplo, "Carritos Recuperados").
- `cartrempro/views/templates/admin/_partials/step_subject_lang.tpl`
  - **Propósito:** Renderiza el campo de entrada de la línea de asunto con pestañas de idioma para los pasos de la campaña.
- `cartrempro/views/templates/admin/_partials/toggle_row.tpl`
  - **Propósito:** Renderiza una fila con un interruptor de palanca (por ejemplo, para habilitar/deshabilitar una configuración).

#### Plantillas de front-office (`views/templates/front/`)

- `cartrempro/views/templates/front/optout.tpl`
  - **Propósito:** Muestra la página de confirmación después de que un cliente se da de baja de los recordatorios de carritos abandonados.

#### Plantillas de correo electrónico (`views/templates/email/`)

- `cartrempro/views/templates/email/default_recovery.tpl`
  - **Propósito:** La plantilla base predeterminada para los correos electrónicos de recordatorio de carritos abandonados. Incluye marcadores de posición para contenido dinámico como el nombre del cliente, el enlace del carrito, la lista de productos y los códigos de descuento. Los desarrolladores pueden personalizar esta plantilla o crear otras nuevas para diferentes diseños de correo electrónico.

### 4.7 Esquema de Base de Datos y Mapa de Ganchos

#### Tablas de Base de Datos

El módulo crea las siguientes tablas personalizadas durante la instalación:

- `ps_cartrempro_abandoned`: Almacena detalles de los carritos abandonados.
  - `id_cartrempro_abandoned` (PK)
  - `id_cart` (FK a `ps_cart`)
  - `id_customer` (FK a `ps_customer`)
  - `id_shop` (FK a `ps_shop`)
  - `id_lang` (FK a `ps_lang`)
  - `cart_value` (decimal)
  - `date_add` (datetime)
  - `date_upd` (datetime)
  - `is_recovered` (tinyint)
  - `is_optout` (tinyint)
- `ps_cartrempro_campaign`: Almacena detalles de cada campaña de recordatorio.
  - `id_cartrempro_campaign` (PK)
  - `name` (varchar)
  - `active` (tinyint)
  - `min_cart_value` (decimal)
  - `customer_groups` (text - array serializado)
  - `products` (text - array serializado)
  - `categories` (text - array serializado)
  - `date_add` (datetime)
  - `date_upd` (datetime)
- `ps_cartrempro_campaign_step`: Almacena detalles de cada paso dentro de una campaña.
  - `id_cartrempro_campaign_step` (PK)
  - `id_cartrempro_campaign` (FK a `ps_cartrempro_campaign`)
  - `delay_hours` (int)
  - `subject` (text - multi-idioma)
  - `content` (text - multi-idioma)
  - `discount_type` (varchar)
  - `discount_value` (decimal)
  - `ab_test_active` (tinyint)
  - `ab_test_variations` (text - array serializado)
- `ps_cartrempro_log`: Almacena registros detallados de las actividades del módulo.
  - `id_cartrempro_log` (PK)
  - `id_cart`
  - `id_customer`
  - `id_cartrempro_campaign`
  - `id_cartrempro_campaign_step`
  - `event_type` (varchar)
  - `details` (text)
  - `date_add` (datetime)
- `ps_cartrempro_queue`: Almacena tareas programadas para la tarea cron.
  - `id_cartrempro_queue` (PK)
  - `id_cart`
  - `id_cartrempro_campaign`
  - `id_cartrempro_campaign_step`
  - `task_type` (varchar)
  - `scheduled_at` (datetime)
  - `processed_at` (datetime)
  - `status` (varchar)
  - `error_message` (text)

#### Tabla de Ganchos Registrados

| Nombre del Gancho | Momento de Ejecución | Propósito Técnico |
| --- | --- | --- |
| `ActionObjectCartUpdateAfter` | Después de que se actualiza un objeto `Cart` (por ejemplo, producto añadido/eliminado, cantidad cambiada). | Se utiliza para rastrear cambios en los carritos de los clientes e identificar posibles abandonos. |
| `actionDispatcher` | Antes de que se despache un controlador. | Potencialmente utilizado para enrutamiento, reescritura de URL o inicialización temprana. |
| `ActionCronJob` | Cuando se ejecuta la tarea cron nativa de PrestaShop (si está configurada). | Activa el controlador `cron.php` del módulo para procesar la cola. |
| `ActionFrontControllerInit` | Antes de que se inicialice cualquier controlador frontal. | Se utiliza para la configuración temprana, como el registro de activos del módulo o el enrutamiento específico. |
| `moduleRoutes` | Durante la generación de enrutamiento de URL. | Permite que el módulo defina URL personalizadas y amigables para sus controladores frontales (por ejemplo, `/cartrempro/optout`). |
| `displayModuleRoutes` | Similar a `moduleRoutes`, a menudo utilizado para mostrar o depurar rutas. | Menos común para la lógica funcional, más para la depuración. |
| `ActionCartSave` | Después de que un carrito se guarda en la base de datos. | Crucial para rastrear la actividad del carrito e identificar cuándo un carrito se abandona. |
| `ActionValidateOrder` | Después de que un pedido ha sido validado con éxito. | Se utiliza para marcar un carrito abandonado como "recuperado" si conduce a una compra completada. |
| `ActionCustomerAccountAdd` | Después de que se crea una nueva cuenta de cliente. | Potencialmente utilizado para la segmentación o el seguimiento inicial del cliente, aunque menos crítico para la lógica central del carrito abandonado. |

## 5. Soporte Oficial y Actualizaciones

Para las últimas actualizaciones del módulo, correcciones de errores y soporte oficial, consulta tu cuenta de cliente en MyPresta.eu. Nuestro equipo se dedica a proporcionar asistencia oportuna y garantizar que tu módulo funcione sin problemas.

- **Historial de Pedidos y Descargas de MyPresta.eu:** <https://mypresta.eu/my-account/orders/>
- **Contacto de Soporte:** [support@mypresta.eu](mailto:support@mypresta.eu)
