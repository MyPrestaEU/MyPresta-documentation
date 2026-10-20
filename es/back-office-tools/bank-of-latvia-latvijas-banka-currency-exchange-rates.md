---
title: "Banco de Letonia (Latvijas Banka) - tipos de cambio de divisas - Manual del Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop 'Banco de Letonia (Latvijas Banka) - tipos de cambio de divisas' de MyPresta.eu."
sidebar:
  label: "Banco de Letonia (Latvijas Banka) - tipos de cambio de divisas - Manual del Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Bank of Latvia (Latvijas Banka) - currency exchange rates en MyPresta.eu](https://mypresta.eu/modules/administration-tools/bank-of-latvia-latvijas-banka-currency-exchange-rates.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/back-office-tools/bank-of-latvia-latvijas-banka-currency-exchange-rates/)
>
> ---


# Banco de Letonia (Latvijas Banka) - tipos de cambio de divisas

## 1. Requisitos y Compatibilidad

- **Versiones de PrestaShop compatibles**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilidad con PHP**: PHP 5.6 - 8.5
- **Requisitos de alojamiento**: Las extensiones PHP estándar (cURL, JSON, OpenSSL) suelen ser necesarias para obtener datos externos, las cuales están casi universalmente disponibles en los entornos de alojamiento modernos.

## 2. Recorrido completo por la configuración (Cada ajuste agrupado por pantalla)

### 2.1 Página de configuración del módulo (Back Office > Módulos > Configurar)

Después de la instalación, haga clic en "Configurar" para acceder a la página de configuración principal del módulo. Aquí es donde definirá cómo el módulo obtiene y aplica los tipos de cambio.

La página de configuración del módulo "Banco de Letonia (Latvijas Banka) - tipos de cambio de divisas" es sencilla y está diseñada para que pueda empezar a utilizarlo rápidamente.

**Captura de pantalla de la página de configuración (Ejemplo):**
*(Imagine una captura de pantalla aquí que muestre la página de configuración del módulo con campos para "URL CRON", "Margen", "Frecuencia de actualización" y un interruptor "Habilitado/Deshabilitado")*

#### 2.1.1 URL CRON

- **Qué hace esta configuración:** Esta es una dirección web (URL) única que, al ser visitada, activa el módulo para obtener los últimos tipos de cambio del Banco de Letonia y actualizarlos en su tienda PrestaShop. Está diseñada para ser llamada automáticamente por una "tarea cron" en su servidor.
- **Efecto de cambiar esta configuración:** No puede cambiar esta URL directamente. Es generada por el módulo. Copiar esta URL es esencial para configurar las actualizaciones automatizadas. Si no configura una tarea cron usando esta URL, los tipos de cambio no se actualizarán automáticamente.
- **Valor recomendado:** Copie esta URL exactamente como aparece.
- **Escenario/ejemplo del comerciante:** Copiará esta URL y la pegará en la sección "Tareas Cron" de su panel de control de alojamiento (por ejemplo, cPanel, Plesk o una interfaz similar) para programar actualizaciones diarias.

#### 2.1.2 Margen (%)

- **Qué hace esta configuración:** Esto le permite añadir un "buffer" o margen porcentual a los tipos de cambio oficiales. Cuando el módulo obtiene un tipo, lo aumentará en este porcentaje antes de guardarlo en su tienda. Esto ayuda a proteger sus márgenes de beneficio contra las fluctuaciones monetarias y las tarifas de transacción.
- **Efecto de cambiar esta configuración:**
  - *Cuando se establece en 0:* El módulo utilizará los tipos de cambio exactos proporcionados por el Banco de Letonia. Sus precios reflejarán directamente los tipos oficiales.
  - *Cuando se establece en un valor positivo (por ejemplo, 2%):* Los tipos de cambio en su tienda serán un 2% más altos que los tipos oficiales. Esto significa que si un producto cuesta 100 EUR y el tipo oficial a USD es 1.10, con un margen del 2%, el módulo utilizará un tipo de 1.122 (1.10 * 1.02), haciendo que el precio en USD sea 112.20.
- **Valor recomendado:** Esto depende de su modelo de negocio, las tarifas de la pasarela de pago y los márgenes de beneficio deseados. Un punto de partida común podría ser del 0.5% al 2% para cubrir los costos de transacción y las fluctuaciones menores.
- **Escenario/ejemplo del comerciante:** Si su procesador de pagos cobra una tarifa del 1% por transacciones internacionales, establecer un margen del 1.5% podría ayudarle a absorber ese costo y aún así mantener su margen de beneficio deseado.

#### 2.1.3 Frecuencia de actualización

- **Qué hace esta configuración:** Esta configuración determina con qué frecuencia el módulo *debería* intentar actualizar los tipos de cambio. Si bien la tarea cron (ver URL CRON) es lo que realmente activa la actualización, esta configuración actúa como una salvaguarda para evitar actualizaciones demasiado frecuentes, lo que podría ser innecesario o incluso problemático para algunos entornos de alojamiento.
- **Efecto de cambiar esta configuración:**
  - *Cuando se establece en "Diario":* El módulo solo procesará una actualización una vez cada 24 horas, incluso si la tarea cron se ejecuta con más frecuencia.
  - *Cuando se establece en "Cada hora":* El módulo procesará una actualización una vez cada hora.
  - *Cuando se establece en "Cada 15 minutos":* El módulo procesará una actualización cada 15 minutos.
- **Valor recomendado:** "Diario" suele ser suficiente para la mayoría de las tiendas de comercio electrónico, ya que los tipos de cambio oficiales no suelen fluctuar drásticamente en cuestión de minutos. Si tiene artículos de muy alto valor u opera en mercados extremadamente volátiles, podría considerarse "Cada hora".
- **Escenario/ejemplo del comerciante:** Usted configura su tarea cron para que se ejecute cada 6 horas, pero establece la "Frecuencia de actualización" aquí en "Diario". El módulo solo realizará una actualización de tipo real una vez dentro de un período de 24 horas, aunque la tarea cron intente activarla con más frecuencia. Esto evita llamadas API y uso de recursos innecesarios.

#### 2.1.4 Habilitar módulo

- **Qué hace esta configuración:** Este es un simple interruptor de encendido/apagado para la funcionalidad principal del módulo.
- **Efecto de cambiar esta configuración:**
  - *Cuando está habilitado (SÍ):* El módulo obtendrá y actualizará activamente los tipos de cambio de acuerdo con su configuración y el programa de la tarea cron.
  - *Cuando está deshabilitado (NO):* El módulo dejará de obtener y actualizar los tipos de cambio. Su tienda seguirá utilizando los últimos tipos conocidos, o el comportamiento predeterminado de PrestaShop para las actualizaciones de tipos si tiene otros mecanismos implementados.
- **Valor recomendado:** "SÍ" para garantizar las actualizaciones automáticas de divisas.
- **Escenario/ejemplo del comerciante:** Podría deshabilitar temporalmente el módulo si necesita realizar un mantenimiento en su tienda o si decide administrar los tipos de cambio manualmente durante un corto período. Recuerde volver a habilitarlo después.

### 2.2 Tabla de referencia rápida de configuración

| Pantalla / Vista | Configuración / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| Configuración del módulo | URL CRON | Copiar exactamente | URL para activar las actualizaciones de tipos a través de la tarea cron del servidor. Esencial para la automatización. |
| Configuración del módulo | Margen (%) | 0% - 2% (depende del negocio) | Añade un margen porcentual a los tipos de cambio obtenidos para proteger los beneficios. |
| Configuración del módulo | Frecuencia de actualización | Diario | Controla con qué frecuencia el módulo *realmente* procesa una actualización, incluso si la tarea cron se ejecuta con más frecuencia. |
| Configuración del módulo | Habilitar módulo | SÍ | Activa o desactiva la funcionalidad de actualización de tipos del módulo. |

## 3. Solución de problemas para comerciantes y preguntas frecuentes (FAQ)

**P: Mis tipos de cambio no se están actualizando. ¿Qué debo hacer?**
R:

1.  **Verifique su tarea Cron:** La razón más común es una tarea cron configurada incorrectamente o faltante en su servidor de alojamiento. Verifique que haya copiado la URL CRON exacta de la página de configuración del módulo y que su tarea cron esté programada para ejecutarse.
2.  **¿Módulo habilitado?** Asegúrese de que el interruptor "Habilitar módulo" en la página de configuración esté configurado en "SÍ".
3.  **Frecuencia de actualización:** Verifique la configuración de "Frecuencia de actualización". Si su tarea cron se ejecuta cada hora pero la frecuencia está configurada en "Diario", solo se actualizará una vez al día.
4.  **Caché de PrestaShop:** A veces, borrar la caché de PrestaShop (en **Parámetros avanzados > Rendimiento**) puede ayudar a actualizar los datos mostrados, aunque es menos probable que afecte las actualizaciones de tipos en el backend.

**P: ¿Puedo anular manualmente un tipo de cambio después de que el módulo lo actualice?**
R: Sí, puede. El módulo actualiza los tipos en el sistema de gestión de monedas estándar de PrestaShop. Si va a **Internacional > Monedas** en su Back Office, puede editar manualmente el tipo de cambio de cualquier moneda. Sin embargo, tenga en cuenta que el módulo sobrescribirá sus cambios manuales la próxima vez que se ejecute la tarea cron y active una actualización.

**P: ¿Qué sucede si el servicio del Banco de Letonia no está disponible temporalmente?**
R: El módulo está diseñado para obtener tipos de una fuente externa. Si el servicio del Banco de Letonia está caído o inaccesible, es probable que el módulo no pueda recuperar nuevos tipos. En tales casos, su tienda seguirá utilizando los *últimos tipos de cambio actualizados con éxito*. No volverá a los tipos predeterminados o incorrectos. Una vez que se restaure el servicio, la próxima ejecución de la tarea cron actualizará los tipos nuevamente.

**P: ¿Este módulo crea nuevas monedas en mi tienda?**
R: No, este módulo solo actualiza los tipos de cambio de las monedas que usted *ya ha habilitado* en su tienda PrestaShop (en **Internacional > Monedas**). Primero debe añadir y habilitar las monedas deseadas en la configuración estándar de PrestaShop para que este módulo pueda gestionar sus tipos.

**P: Mi tema personalizado no muestra los precios correctamente después de las actualizaciones.**
R: Este módulo solo cambia los tipos de cambio subyacentes. Si los precios se muestran incorrectamente, es muy poco probable que sea un problema directo del módulo.

1.  **Borrar caché de Smarty:** Vaya a **Parámetros avanzados > Rendimiento** y haga clic en "Borrar caché".
2.  **Compatibilidad del tema:** Asegúrese de que su tema personalizado sea totalmente compatible con su versión de PrestaShop.
3.  **Código personalizado:** Si su tema tiene código personalizado para la visualización de precios, es posible que no esté interpretando correctamente los tipos de cambio actualizados de PrestaShop. Consulte a su desarrollador de temas o a un experto en PrestaShop.

## 4. Guía para desarrolladores y webmasters (Arquitectura técnica y mapa de código)

### 4.1 Resumen de la arquitectura

El módulo "Banco de Letonia (Latvijas Banka) - tipos de cambio de divisas" (`lbrates`) es un módulo ligero de PrestaShop diseñado principalmente para automatizar las actualizaciones de los tipos de cambio de divisas. Sigue un patrón MVC simple donde el archivo principal del módulo (`cronjob.php`) actúa como el controlador principal para la configuración y el controlador frontal (`cronjob.php`) maneja la lógica real de obtención de tipos. Aprovecha las clases `Currency` y `Configuration` de PrestaShop para gestionar tipos y configuraciones. El módulo se activa mediante llamadas externas de tareas cron, lo que lo convierte en un proceso asíncrono en segundo plano.

### 4.2 Controladores (`controllers/`)

- **Controladores de Front-Office**:

  - `lbrates/controllers/front/cronjob.php`
    - Nombre de la clase: `LbratesCronjobModuleFrontController`
    - Clase padre: `ModuleFrontController`
    - Responsabilidad: Este controlador es el núcleo de la funcionalidad del módulo. Está diseñado para ser llamado por una tarea cron externa. Cuando se accede, obtiene los últimos tipos de referencia del Euro de la API oficial del Banco de Letonia, aplica el margen configurado y actualiza los tipos de cambio de todas las monedas activas en la base de datos de PrestaShop. También maneja el registro y evita actualizaciones demasiado frecuentes basándose en la clave de configuración `PS_LBRATES_LAST_UPDATE`.
  - `lbrates/controllers/front/index.php`
    - Nombre de la clase: `LbratesIndexModuleFrontController`
    - Clase padre: `ModuleFrontController`
    - Responsabilidad: Este es un archivo `index.php` estándar vacío que a menudo se incluye en los directorios de controladores frontales de módulos de PrestaShop para evitar la lista de directorios. No contiene ninguna lógica funcional.
- **Controladores de administración de Back-Office**:

  - Ninguno. Toda la administración se maneja directamente dentro del método `getContent()` del archivo principal del módulo.

### 4.3 Clases y modelos principales (`classes/`)

- Ninguno. El módulo interactúa directamente con las clases principales `Currency` y `Configuration` de PrestaShop.

### 4.4 Activos de JavaScript (`views/js/`)

- Ninguno. El módulo no utiliza ningún JavaScript personalizado.

### 4.5 Hojas de estilo CSS (`views/css/`)

- Ninguno. El módulo no utiliza ningún CSS personalizado.

### 4.6 Estructura de plantillas Smarty (`views/templates/`)

- **Plantillas de administración (`views/templates/admin/`)**:
  - `lbrates/views/admin.tpl`
    - Esta plantilla es renderizada por el método `getContent()` en el archivo principal del módulo `cronjob.php`. Muestra el formulario de configuración del módulo en el Back Office de PrestaShop. Esto incluye campos para la URL CRON, el Margen, la Frecuencia de actualización y el interruptor Habilitar/Deshabilitar. Utiliza los ayudantes de formulario y el estilo estándar de PrestaShop.

### 4.7 Esquema de la base de datos y mapa de hooks

- **Tablas de la base de datos**:

  - El módulo no crea ninguna tabla SQL personalizada.
  - Almacena sus configuraciones en la tabla `ps_configuration`:
    - `PS_LBRATES_SPREAD`: Almacena el margen porcentual configurado.
    - `PS_LBRATES_UPDATE_FREQUENCY`: Almacena la frecuencia de actualización configurada (por ejemplo, diaria, cada hora).
    - `PS_LBRATES_LAST_UPDATE`: Almacena la marca de tiempo de la última actualización exitosa para evitar llamadas demasiado frecuentes.
    - `PS_LBRATES_ENABLED`: Almacena el estado habilitado/deshabilitado del módulo.
  - Actualiza la columna `exchange_rate` en la tabla `ps_currency` para las monedas activas.
- **Tabla de Hooks registrados**:

  - El módulo no registra ningún hook de visualización tradicional (`displayHeader`, `displayFooter`, etc.) en el front office. Su función principal es el procesamiento en segundo plano.
  - Utiliza implícitamente el hook `actionUpdateCurrency` (o mecanismos internos similares) modificando directamente los tipos de cambio de divisas, pero no se registra explícitamente en él.
  - El método `install()` del módulo registraría el módulo en el sistema de módulos de PrestaShop, haciendo que su configuración sea accesible.

## 5. Soporte oficial y actualizaciones

Para las últimas actualizaciones, correcciones de errores y soporte oficial para el módulo "Banco de Letonia (Latvijas Banka) - tipos de cambio de divisas", consulte su cuenta de cliente en [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nuestro equipo de soporte está disponible para ayudar a comerciantes y desarrolladores con cualquier problema o pregunta relacionada con la funcionalidad e integración del módulo.
