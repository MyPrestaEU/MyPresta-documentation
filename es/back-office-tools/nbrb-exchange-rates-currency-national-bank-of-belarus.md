---
title: "Tasas de cambio y moneda del NBRB (Banco Nacional de Bielorrusia) - Manual del Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop NBRB Exchange Rates & Currency (National Bank of Belarus) de MyPresta.eu."
sidebar:
  label: "Tasas de cambio y moneda del NBRB (Banco Nacional de Bielorrusia) - Manual del Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo NBRB Exchange Rates & Currency (National Bank of Belarus) en MyPresta.eu](https://mypresta.eu/modules/administration-tools/nbrb-exchange-rates-currency-national-bank-of-belarus.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/back-office-tools/nbrb-exchange-rates-currency-national-bank-of-belarus/)
>
> ---


# Tasas de cambio y moneda del NBRB (Banco Nacional de Bielorrusia)

## 1. Requisitos y compatibilidad

- **Versiones de PrestaShop compatibles**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilidad con PHP**: PHP 5.6 - 8.5
- **Requisitos de alojamiento**: Las extensiones PHP estándar (cURL, JSON, OpenSSL) suelen ser necesarias y están presentes en la mayoría de los entornos de alojamiento modernos. El acceso para configurar un trabajo CRON es esencial para las actualizaciones automáticas.

## 2. Recorrido completo por la configuración (Cada ajuste agrupado por pantalla)

### 2.1 Página de configuración del módulo (Back Office > Módulos > Configurar)

Después de la instalación, haga clic en "Configurar" junto al módulo "NBRB Exchange Rates & Currency" para acceder a sus ajustes.

#### **Habilitar tasas de cambio del NBRB**

- **Qué hace este ajuste:** Este es el interruptor principal para activar o desactivar la funcionalidad principal del módulo.
- **Efecto de cambiar este ajuste:**
  - *Cuando está habilitado (SÍ):* El módulo comenzará a obtener y aplicar las tasas de cambio del NBRB para las conversiones de moneda BYN en su tienda.
  - *Cuando está deshabilitado (NO):* El módulo dejará de obtener tasas, y sus tasas de moneda BYN volverán a lo que se estableció manualmente en la sección "Monedas" de PrestaShop o por otro módulo de moneda activo.
- **Valor recomendado:** SÍ
- **Escenario / ejemplo de comerciante:** Si vende principalmente a Bielorrusia, habilite esto para asegurarse de que todos los precios en BYN sean oficiales. Si deja de vender temporalmente a Bielorrusia, podría deshabilitarlo.

#### **URL del trabajo CRON**

- **Qué hace este ajuste:** Muestra la URL única que necesita configurar como un trabajo CRON en su servidor. Cuando se accede a esta URL, el módulo obtendrá automáticamente las últimas tasas de cambio del NBRB.
- **Efecto de cambiar este ajuste:** Este es un campo de solo visualización. Copie esta URL y péguela en el programador de trabajos CRON de su panel de control de alojamiento.
- **Valor recomendado:** Copie esta URL exactamente como se muestra.
- **Escenario / ejemplo de comerciante:** Copiaría esta URL y configuraría un trabajo CRON para que se ejecute, por ejemplo, una vez cada 24 horas (por ejemplo, a las 3 AM hora local) para asegurarse de que sus tasas estén siempre actualizadas. Consulte la documentación o el soporte de su proveedor de alojamiento para configurar trabajos CRON.

#### **Ajuste de margen (%)**

- **Qué hace este ajuste:** Le permite agregar un margen porcentual (recargo o descuento) a las tasas de cambio del NBRB obtenidas. Esto es útil para cubrir tarifas de transacción, protegerse contra fluctuaciones menores o aplicar un ligero descuento/prima.
- **Efecto de cambiar este ajuste:**
  - *Introducir un valor positivo (por ejemplo, 2):* La tasa de conversión de BYN aumentará en un 2%, lo que hará que los productos sean ligeramente más caros en BYN.
  - *Introducir un valor negativo (por ejemplo, -1):* La tasa de conversión de BYN disminuirá en un 1%, lo que hará que los productos sean ligeramente más baratos en BYN.
  - *Dejarlo en 0:* Se utilizará la tasa oficial del NBRB sin ninguna modificación.
- **Valor recomendado:** 0 (a menos que tenga una razón comercial específica para ajustar las tasas).
- **Escenario / ejemplo de comerciante:** Si su pasarela de pago cobra una tarifa del 1.5% por las transacciones en BYN, podría establecer esto en "1.5" para absorber ese costo en el tipo de cambio.

#### **Última actualización**

- **Qué hace este ajuste:** Este campo muestra la fecha y hora en que las tasas de cambio se actualizaron con éxito por última vez por el módulo (ya sea manualmente o mediante un trabajo CRON).
- **Efecto de cambiar este ajuste:** Este es un campo informativo de solo lectura. Le ayuda a verificar que su trabajo CRON se está ejecutando correctamente y que las tasas se están actualizando.
- **Valor recomendado:** N/A (supervise esto para asegurar actualizaciones regulares).
- **Escenario / ejemplo de comerciante:** Si observa que esta fecha tiene varios días de antigüedad, indica un problema con la configuración de su trabajo CRON y debe investigarlo.

#### **Botón Actualizar tasas manualmente**

- **Qué hace este ajuste:** Este botón le permite activar manualmente una actualización inmediata de las tasas de cambio del NBRB, fuera del horario del trabajo CRON.
- **Efecto de cambiar este ajuste:** Al hacer clic en este botón, se obtendrán instantáneamente las últimas tasas y se actualizarán en su tienda PrestaShop. El campo "Última actualización" reflejará la nueva hora.
- **Valor recomendado:** Úselo según sea necesario para actualizaciones inmediatas o pruebas.
- **Escenario / ejemplo de comerciante:** Si hay un evento económico significativo y desea asegurarse de que sus tasas estén absolutamente actualizadas antes de su próximo trabajo CRON programado, puede hacer clic en este botón.

### 2.2 Tabla de referencia rápida de configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| Configuración del módulo | Habilitar tasas de cambio del NBRB | SÍ | Activa/desactiva la obtención y aplicación de tasas del módulo. |
| Configuración del módulo | URL del trabajo CRON | N/A (copiar y pegar) | URL para configurar actualizaciones automáticas de tasas en su servidor. |
| Configuración del módulo | Ajuste de margen (%) | 0 | Agrega un recargo/descuento porcentual a las tasas del NBRB obtenidas. |
| Configuración del módulo | Última actualización | N/A (solo lectura) | Muestra la marca de tiempo de la última actualización exitosa de la tasa. |
| Configuración del módulo | Botón Actualizar tasas manualmente | N/A (haga clic para activar) | Activa una actualización manual e inmediata de las tasas de cambio. |

## 3. Solución de problemas del comerciante y preguntas frecuentes (FAQ)

**P: Mis precios en BYN no se actualizan o parecen incorrectos.**
R:

1. **Verifique "Habilitar tasas de cambio del NBRB":** Asegúrese de que este ajuste esté configurado en "SÍ" en la configuración del módulo.
2. **Verifique el trabajo CRON:** Asegúrese de que su trabajo CRON esté configurado correctamente en su servidor utilizando la URL proporcionada y que se ejecute regularmente. Verifique la marca de tiempo de "Última actualización" en el módulo.
3. **Actualizar manualmente:** Intente hacer clic en el botón "Actualizar tasas manualmente". Si esto funciona, el problema probablemente esté en la configuración de su trabajo CRON.
4. **Verifique el estado de la moneda BYN:** Vaya a **Internacional > Monedas** y asegúrese de que "Rublo bielorruso (BYN)" esté habilitado y su código ISO sea `BYN`.
5. **Borrar caché:** A veces, la caché de PrestaShop puede contener valores antiguos. Vaya a **Parámetros avanzados > Rendimiento** y haga clic en "Borrar caché".

**P: ¿Qué sucede en días festivos bancarios o fines de semana cuando el NBRB no publica nuevas tasas?**
R: El módulo está diseñado para manejar esto de forma inteligente. Si la API del NBRB no proporciona nuevas tasas para un día determinado (por ejemplo, debido a un fin de semana o día festivo), el módulo seguirá utilizando la última tasa obtenida con éxito. Solo se actualizará cuando haya nuevas tasas oficiales disponibles.

**P: ¿Puedo usar este módulo con otros módulos de conversión de moneda?**
R: Generalmente no se recomienda ejecutar varios módulos de conversión de moneda simultáneamente, ya que pueden entrar en conflicto y generar resultados impredecibles. Este módulo se dirige específicamente a las tasas del NBRB para BYN. Si necesita otras monedas, asegúrese de que este módulo sea la fuente principal para BYN y que otros módulos manejen diferentes monedas sin superponerse.

**P: He establecido un margen, pero los precios no parecen reflejarlo.**
R:

1. **Guardar cambios:** Asegúrese de haber guardado la configuración del módulo después de establecer el margen.
2. **Actualizar tasas:** El margen se aplica cuando se obtienen las tasas. Espere la próxima ejecución del trabajo CRON o haga clic en "Actualizar tasas manualmente".
3. **Borrar caché:** Borre la caché de su PrestaShop (**Parámetros avanzados > Rendimiento**).
4. **Verificar moneda base:** El margen se aplica a la conversión de la moneda base de su tienda a BYN. Asegúrese de que su moneda base esté configurada correctamente en PrestaShop.

**P: Estoy recibiendo un error al intentar instalar o configurar el módulo.**
R:

1. **Versión de PrestaShop:** Asegúrese de haber descargado el archivo ZIP del módulo correcto para su versión específica de PrestaShop (1.6, 1.7, 8.x, 9.x).
2. **Compatibilidad con PHP:** Verifique que la versión de PHP de su servidor esté dentro del rango compatible (PHP 5.6 - 8.5).
3. **Registros del servidor:** Verifique los registros de errores de PHP de su servidor (a menudo se encuentran en el panel de control de su alojamiento) para obtener mensajes de error más detallados. Esto puede ayudar a identificar el problema exacto.

## 4. Guía para desarrolladores y webmasters (Arquitectura técnica y mapa de código)

Esta sección es estrictamente para desarrolladores, webmasters de tiendas y agencias técnicas que mantienen o extienden la tienda.

### 4.1 Resumen de la arquitectura

El módulo NBRB Exchange Rates & Currency es un módulo ligero de PrestaShop centrado principalmente en una única tarea crítica: obtener y actualizar el tipo de cambio del rublo bielorruso (BYN) de la API del Banco Nacional de la República de Bielorrusia (NBRB). Aprovecha el objeto `Currency` de PrestaShop para actualizar la `conversion_rate` para BYN. El módulo utiliza un trabajo CRON para actualizaciones automatizadas y proporciona un activador manual en el back office. Se adhiere al patrón MVC de PrestaShop para su configuración y ejecución del trabajo cron del front-office.

### 4.2 Controladores (`controllers/`)

- **Controladores del Front-Office**:

  - `controllers/front/cronjob.php`
    - **Nombre de clase y clase padre:** `NbrbratesCronjobModuleFrontController` que extiende `ModuleFrontController`.
    - **Responsabilidad:** Este controlador está diseñado para ser llamado por un trabajo CRON externo. Cuando se accede a él, activa la lógica de obtención de tasas del módulo (`$this->module->updateRates()`). Emite un simple mensaje de éxito/fracaso, lo que lo hace adecuado para la ejecución automatizada sin un navegador. No renderiza una página completa.
  - `controllers/front/index.php`
    - **Nombre de clase y clase padre:** `NbrbratesIndexModuleFrontController` que extiende `ModuleFrontController`.
    - **Responsabilidad:** Este es un controlador de marcador de posición, a menudo incluido en los módulos para evitar la lista de directorios o proporcionar una página "vacía" predeterminada si se accede al controlador frontal del módulo directamente sin acciones específicas. En el contexto de este módulo, probablemente sirve como un recurso alternativo y no tiene una lógica de negocio específica.
- **Controladores de administración del Back-Office**:

  - Este módulo no utiliza controladores de administración dedicados. Toda la configuración del back-office se maneja directamente dentro del método `getContent()` del archivo principal del módulo.

### 4.3 Clases y modelos principales (`classes/`)

Este módulo no define ninguna clase personalizada en el directorio `classes/`. Su lógica central para obtener y actualizar tasas está encapsulada dentro del archivo principal del módulo `nbrbrates/cronjob.php`.

### 4.4 Activos de JavaScript (`views/js/`)

Este módulo no incluye ningún archivo JavaScript personalizado.

### 4.5 Hojas de estilo CSS (`views/css/`)

Este módulo no incluye ningún archivo CSS personalizado. El estilo de la página de configuración de administración se maneja típicamente mediante el CSS predeterminado del back-office de PrestaShop.

### 4.6 Estructura de la plantilla Smarty (`views/templates/`)

- **Plantillas de administración (`views/templates/admin/`)**:
  - `nbrbrates/views/admin.tpl`
    - **Propósito:** Esta plantilla es renderizada por el método `getContent()` en el archivo principal del módulo (`nbrbrates/cronjob.php`). Define la estructura y la visualización del formulario de configuración del módulo en el Back Office de PrestaShop. Incluye campos de entrada para habilitar/deshabilitar el módulo, ajuste de margen, visualización de la URL del trabajo CRON, hora de la última actualización y el botón de actualización manual.

### 4.7 Esquema de la base de datos y mapa de ganchos

- **Tablas de la base de datos**:

  - Este módulo no crea ninguna tabla SQL personalizada.
  - Almacena sus configuraciones en la tabla `ps_configuration` de PrestaShop. Las claves de configuración clave incluyen:
    - `Nbrbrates_ENABLED`: (int) 1 si está habilitado, 0 si está deshabilitado.
    - `Nbrbrates_MARGIN`: (float) El margen porcentual a aplicar.
    - `Nbrbrates_LAST_UPDATE`: (datetime) Marca de tiempo de la última actualización exitosa de la tasa.
- **Tabla de ganchos registrados**:
  Este módulo no registra explícitamente ganchos que muestren contenido en el front office (como `displayHeader`, `displayRightColumn`, `displayFooter`). Su interacción principal con PrestaShop es a través de:

| Nombre del gancho | Momento de ejecución | Propósito técnico |
| --- | --- | --- |
| `actionModuleInstall` | Se ejecuta cuando se instala el módulo. | Inicializa los valores de configuración predeterminados en `ps_configuration`. |
| `actionModuleUninstall` | Se ejecuta cuando se desinstala el módulo. | Limpia los valores de configuración de `ps_configuration`. |
| `actionUpdateCurrency` | (Implícito) Se activa cuando se actualiza una moneda. | El método `updateRates()` del módulo modifica directamente la `conversion_rate` del objeto de moneda BYN, actuando eficazmente sobre las actualizaciones de moneda. |

El controlador `cronjob.php` del front-office actúa como un punto de entrada externo, no como un gancho tradicional de PrestaShop.

## 5. Soporte oficial y actualizaciones

Para obtener actualizaciones oficiales, soporte técnico y acceder a las últimas versiones del módulo NBRB Exchange Rates & Currency, visite su cuenta de cliente en [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nuestro equipo de soporte está disponible para ayudarle con cualquier problema o pregunta que pueda tener con respecto a la funcionalidad o integración del módulo.
