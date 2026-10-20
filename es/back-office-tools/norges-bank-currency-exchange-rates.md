---
title: "Norges Bank - tipos de cambio - Manual del Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop 'Norges Bank - tipos de cambio' de MyPresta.eu."
sidebar:
  label: "Norges Bank - tipos de cambio - Manual del Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Norges Bank - currency exchange rates en MyPresta.eu](https://mypresta.eu/modules/administration-tools/norges-bank-currency-exchange-rates.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/back-office-tools/norges-bank-currency-exchange-rates/)
>
> ---


# Norges Bank - tipos de cambio

## 1. Requisitos y Compatibilidad

- **Versiones de PrestaShop Compatibles**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilidad con PHP**: PHP 5.6 - 8.5
- **Requisitos de Alojamiento**: Las extensiones PHP estándar (cURL, JSON, OpenSSL) suelen ser necesarias para obtener datos externos. Su entorno de alojamiento también debe ser compatible con los trabajos CRON para las actualizaciones automatizadas.

## 2. Recorrido Completo por la Configuración (Cada Ajuste Agrupado por Pantalla)

### 2.1 Página de Configuración del Módulo (Back Office > Módulos > Configurar)

Después de la instalación, al hacer clic en "Configurar" accederá a la página de configuración principal del módulo "Norges Bank - tipos de cambio". Aquí es donde controla cómo y cuándo se actualizan los tipos de cambio.

#### **Ajustes y Opciones**

1. **URL CRON para actualizaciones automáticas:**

   - **Qué hace este ajuste:** Esta es una dirección web única (URL) que, al ser visitada, activa el módulo para obtener los últimos tipos de cambio del Norges Bank y actualizarlos en su tienda PrestaShop.
   - **Efecto de cambiar este ajuste:** No puede cambiar esta URL directamente. Es generada por el módulo. Necesita esta URL para configurar una tarea automatizada (un "trabajo CRON") en el servidor de su alojamiento web.
   - **Valor recomendado:** Copie esta URL exactamente como aparece.
   - **Escenario/ejemplo del comerciante:** Proporcionará esta URL a su proveedor de alojamiento o la utilizará en su panel de control de alojamiento (como cPanel o Plesk) para programar una tarea que visite esta URL regularmente (por ejemplo, una vez al día). Esto asegura que sus tipos de cambio estén siempre actualizados sin que usted tenga que hacer nada manualmente.
2. **Margen del Tipo de Cambio (%):**

   - **Qué hace este ajuste:** Esto le permite añadir un margen porcentual a los tipos de cambio obtenidos del Norges Bank. Por ejemplo, si el tipo oficial es 1 EUR = 10 NOK, y usted establece un margen del 2%, su tienda podría usar 1 EUR = 9.8 NOK (o 10.2 NOK, dependiendo de la dirección del cálculo, típicamente haciendo que la moneda extranjera sea ligeramente más cara para el cliente para cubrir los costos de conversión).
   - **Efecto de cambiar este ajuste:**
     - *Cuando se establece en 0:* Su tienda utiliza los tipos de cambio oficiales exactos proporcionados por el Norges Bank.
     - *Cuando se establece en un valor positivo (por ejemplo, 2):* El módulo ajusta los tipos de cambio para incluir este porcentaje, dándole efectivamente un pequeño colchón o margen de beneficio en las conversiones de moneda. Esto puede ayudar a cubrir las tarifas de transacción o simplemente aumentar su rentabilidad.
   - **Valor recomendado:** Comience con `0` si desea tipos exactos. Si necesita cubrir costos o añadir un pequeño beneficio, un valor entre `0.5` y `2` por ciento es común.
   - **Escenario/ejemplo del comerciante:** Si su pasarela de pago cobra una tarifa del 1% por transacciones internacionales, establecer un margen del 1% aquí puede ayudarle a absorber ese costo sin afectar el precio de sus productos en su moneda base.
3. **Última Actualización:**

   - **Qué hace este ajuste:** Muestra la fecha y hora en que el módulo actualizó por última vez los tipos de cambio en su tienda.
   - **Efecto de cambiar este ajuste:** Este es un campo informativo y no se puede cambiar. Le ayuda a verificar que su trabajo CRON funciona correctamente y que sus tipos de cambio se actualizan regularmente.
   - **Valor recomendado:** Revise este campo periódicamente para asegurarse de que las actualizaciones se realizan como se espera.
   - **Escenario/ejemplo del comerciante:** Después de configurar su trabajo CRON, puede revisar este campo al día siguiente para confirmar que el módulo se ejecutó correctamente y actualizó los tipos de cambio.

#### **Botón de Actualización Manual**

- **Qué hace este botón:** Este botón le permite activar manualmente una actualización inmediata de todos los tipos de cambio del Norges Bank.
- **Efecto de hacer clic en este botón:** El módulo obtendrá instantáneamente los últimos tipos de cambio y los aplicará a su tienda. Esto es útil para realizar pruebas o si necesita una actualización inmediata fuera de su trabajo CRON programado.
- **Uso recomendado:** Úselo para las pruebas iniciales después de la configuración, o si hay una fluctuación monetaria significativa y repentina que desea reflejar de inmediato.

#### **Instrucciones de Configuración del Trabajo CRON**

Debajo de la configuración, encontrará instrucciones claras sobre cómo configurar el trabajo CRON en su servidor. Esto es crucial para el funcionamiento "sin mantenimiento" del módulo.

- **Qué hace esta sección:** Proporciona el comando o método exacto que necesita usar con el programador de trabajos CRON de su proveedor de alojamiento.
- **Efecto de seguir estas instrucciones:** Una vez configurado, su servidor visitará automáticamente la URL CRON a intervalos específicos (por ejemplo, una vez al día), asegurando que sus tipos de cambio estén siempre actualizados sin intervención manual.
- **Frecuencia recomendada:** Las actualizaciones diarias suelen ser suficientes. Para monedas muy volátiles o ventas internacionales de gran volumen, podría considerar dos veces al día.
- **Escenario/ejemplo del comerciante:** En cPanel, iría a "Trabajos Cron", seleccionaría una configuración común como "Una vez al día" y pegaría el comando proporcionado en el campo "Comando".

### 2.2 Tabla de Referencia Rápida de Configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| Configuración del Módulo | URL CRON para actualizaciones automáticas | (URL generada) | URL para activar actualizaciones automáticas de tipos de cambio mediante trabajo CRON. **Crucial para la automatización.** |
| Configuración del Módulo | Margen del Tipo de Cambio (%) | 0 | Añade un porcentaje de amortiguación a los tipos de cambio para rentabilidad/recuperación de costos. |
| Configuración del Módulo | Última Actualización | (Fecha/Hora) | Campo informativo que muestra la última actualización exitosa del tipo de cambio. |
| Configuración del Módulo | Botón de Actualización Manual | N/A | Obtiene y aplica inmediatamente los últimos tipos de cambio. Útil para pruebas/actualizaciones urgentes. |
| Configuración del Módulo | Instrucciones de Configuración del Trabajo CRON | N/A | Guía para configurar actualizaciones automatizadas en su servidor de alojamiento. |

## 3. Solución de Problemas del Comerciante y Preguntas Frecuentes (FAQ)

**P: Mis tipos de cambio no se actualizan automáticamente. ¿Qué debo hacer?**
R: Esto casi siempre está relacionado con la configuración del trabajo CRON en su servidor.
1. **Verificar Trabajo CRON:** Vuelva a verificar su panel de control de alojamiento (cPanel, Plesk, etc.) para asegurarse de que el trabajo CRON esté configurado correctamente con la URL exacta proporcionada por el módulo y que esté programado para ejecutarse.
2. **Ruta CRON:** A veces, la ruta de PHP en el comando CRON debe ser absoluta (por ejemplo, `/usr/bin/php` en lugar de solo `php`). Su proveedor de alojamiento puede confirmarlo.
3. **Verificar "Última Actualización":** Si el campo "Última Actualización" en la configuración del módulo nunca cambia, confirma que el trabajo CRON no está ejecutando el script de actualización del módulo.
4. **Actualización Manual:** Intente hacer clic en el botón "Actualización Manual" en la configuración del módulo. Si esto funciona, confirma que el módulo en sí puede obtener los tipos de cambio, lo que apunta definitivamente a un problema con el trabajo CRON.

**P: Los tipos de cambio parecen incorrectos o no han cambiado mucho.**
R:
1. **Verificar Norges Bank:** Compare los tipos de cambio en su tienda con los tipos oficiales publicados por el Norges Bank (su sitio web suele ser accesible mediante una búsqueda rápida).
2. **Configuración del Margen:** Recuerde que su configuración de "Margen del Tipo de Cambio (%)" ajustará ligeramente los tipos de cambio. Asegúrese de que esté configurado según lo previsto.
3. **Última Actualización:** Verifique el campo "Última Actualización". Si es antiguo, su trabajo CRON no se está ejecutando.

**P: ¿Este módulo afecta mi moneda predeterminada?**
R: No, el módulo solo actualiza los tipos de cambio para monedas no predeterminadas en relación con su moneda predeterminada. El valor de su moneda predeterminada permanece sin cambios.

**P: He actualizado mi tema y ahora el selector de moneda no funciona correctamente.**
R: Este módulo solo actualiza los *valores* de los tipos de cambio. La visualización y funcionalidad del selector de moneda en sí son manejadas por el núcleo de PrestaShop o su tema. Si el selector no funciona, es probable que sea un problema del tema o del núcleo de PrestaShop, no directamente relacionado con este módulo. Borre su caché de Smarty (**Parámetros Avanzados > Rendimiento**) y verifique la configuración de su tema.

**P: ¿Puedo usar este módulo con otros módulos de moneda?**
R: Generalmente no se recomienda ejecutar varios módulos que intenten actualizar los tipos de cambio, ya que podrían entrar en conflicto o sobrescribir los datos del otro. Este módulo está diseñado para ser una solución independiente para los tipos de cambio del Norges Bank. Si necesita tipos de cambio de una fuente diferente, debe deshabilitar este módulo y usar el otro.

## 4. Guía para Desarrolladores y Webmasters (Arquitectura Técnica y Mapa de Código)

Esta sección proporciona una descripción técnica detallada para desarrolladores y webmasters.

### 4.1 Descripción General de la Arquitectura

El módulo "Norges Bank - tipos de cambio" (`nbrates`) es un módulo ligero de PrestaShop centrado principalmente en una tarea única y crítica: obtener y actualizar los tipos de cambio de moneda. Aprovecha la clase `Module` de PrestaShop para la instalación y configuración y utiliza un controlador frontal para exponer un punto final CRON para actualizaciones automatizadas. La lógica central implica realizar una solicitud HTTP a la API del Norges Bank, analizar la respuesta XML, calcular los tipos de cambio cruzados y actualizar la tabla `ps_currency` de PrestaShop.

### 4.2 Controladores (`controllers/`)

- **Controladores de Front-Office**:

  - `controllers/front/cronjob.php`
    - **Nombre de la clase**: `NbratesCronjobModuleFrontController`
    - **Clase padre**: `ModuleFrontController`
    - **Responsabilidad**: Este controlador gestiona la ejecución del trabajo CRON. Cuando se accede a través de su URL (proporcionada en la configuración del módulo), activa el método `cronjob()` dentro de la clase principal del módulo `nbrates`. Está diseñado para ser llamado por un programador externo (CRON) y genera un mensaje simple de éxito/fallo. No renderiza ningún contenido visual para el usuario.
  - `controllers/front/index.php`
    - **Nombre de la clase**: `NbratesIndexModuleFrontController`
    - **Clase padre**: `ModuleFrontController`
    - **Responsabilidad**: Este es un controlador de marcador de posición, a menudo incluido en módulos pero no utilizado activamente en la funcionalidad principal de este módulo específico. Típicamente sirve como un punto de entrada predeterminado si un módulo tiene una página dedicada en el front-office. En este módulo, su propósito principal es probablemente evitar la lista de directorios si se accede a `cronjob.php` directamente sin una acción específica.
- **Controladores de Administración de Back-Office**:

  - Ninguno. Toda la configuración se maneja directamente dentro del método `getContent()` del módulo principal.

### 4.3 Clases y Modelos Principales (`classes/`)

- Ninguno. La lógica central del módulo está autocontenida dentro del archivo principal `nbrates/cronjob.php`. Esto es común para módulos más simples que no requieren estructuras de datos complejas o interacciones extensas con la base de datos más allá de la configuración estándar.

### 4.4 Activos JavaScript (`views/js/`)

- Ninguno. El módulo no incluye ningún JavaScript personalizado para la funcionalidad del front-office o del back-office.

### 4.5 Hojas de Estilo CSS (`views/css/`)

- Ninguno. El módulo no incluye ninguna hoja de estilo CSS personalizada. La configuración del back-office se basa en el estilo predeterminado del panel de administración de PrestaShop.

### 4.6 Estructura de Plantillas Smarty (`views/templates/`)

- **Plantillas de administración (`views/templates/admin/`)**:
  - `views/templates/admin/admin.tpl`
    - **Propósito**: Esta plantilla es renderizada por el método `getContent()` de la clase principal del módulo (`nbrates/cronjob.php`) para mostrar el formulario de configuración del módulo en el Back Office de PrestaShop.
    - **Contenido**: Típicamente contiene la estructura HTML para la visualización de la URL CRON, el campo de entrada del margen del tipo de cambio, la información de "Última Actualización", el botón de actualización manual y las instrucciones de configuración del trabajo CRON. Utiliza los ayudantes de formulario y el estilo estándar de PrestaShop.

### 4.7 Esquema de Base de Datos y Mapa de Ganchos

- **Tablas de Base de Datos**:

  - El módulo no crea ninguna tabla de base de datos personalizada.
  - Interactúa con la tabla estándar `ps_configuration` de PrestaShop para almacenar sus configuraciones (por ejemplo, `NBS_LAST_UPDATE`, `NBS_MARGIN`).
  - Actualiza la tabla `ps_currency`, específicamente la columna `conversion_rate` para monedas no predeterminadas.
- **Tabla de Ganchos Registrados**:

| Nombre del Gancho | Momento de Ejecución | Propósito Técnico |
| --- | --- | --- |
| `displayBackOfficeHeader` | Se renderiza en la sección `<head>` del Back Office. | Se utiliza para incluir cualquier CSS/JS necesario para la página de configuración del módulo (aunque no se utiliza ninguno en este módulo). |
| `actionAdminControllerSetMedia` | Se llama antes de renderizar un controlador de administración. | Se utiliza para registrar activos (JS/CSS) para páginas de administración. |
| `actionCronJob` | Gancho personalizado, activado por el controlador frontal `cronjob`. | El gancho principal donde se ejecuta la lógica de actualización de moneda del módulo. |
| `displayHeader` | Renderiza contenido en la sección `<head>` del front office. | (No utilizado explícitamente por este módulo para la salida, pero a menudo registrado por módulos). |
| `displayLeftColumn` | Renderiza contenido en la columna izquierda del front office. | (No utilizado explícitamente por este módulo para la salida). |
| `displayRightColumn` | Renderiza contenido en la columna derecha del front office. | (No utilizado explícitamente por este módulo para la salida). |
| `displayFooter` | Renderiza contenido en el pie de página del front office. | (No utilizado explícitamente por este módulo para la salida). |
| `displayProductExtraContent` | Renderiza contenido en la página del producto. | (No utilizado explícitamente por este módulo para la salida). |

*Nota: Aunque la descripción del módulo menciona ganchos de Front-Office como Header, Columns, Product o Footer, el inventario de código proporcionado no muestra ninguna plantilla o lógica específica para renderizar contenido en estos ganchos. Es posible que estos sean ganchos genéricos registrados durante la instalación pero no utilizados activamente para la salida visual por este módulo específico, ya que su función es puramente la sincronización de datos de backend.*

## 5. Soporte Oficial y Actualizaciones

Para las últimas actualizaciones, correcciones de errores y soporte oficial para el módulo "Norges Bank - tipos de cambio", consulte su cuenta de cliente en [MyPresta.eu](https://mypresta.eu/). Puede descargar las versiones más recientes desde su historial de pedidos y acceder a los recursos de soporte directamente desde la plataforma MyPresta.eu.
