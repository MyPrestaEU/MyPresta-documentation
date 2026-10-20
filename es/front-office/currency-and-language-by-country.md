---
title: "Moneda e idioma por país - Manual del comerciante y guía de configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop 'Moneda e idioma por país' de MyPresta.eu."
sidebar:
  label: "Moneda e idioma por país - Manual del comerciante y guía de configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Currency and language by country en MyPresta.eu](https://mypresta.eu/modules/front-office-features/currency-and-language-by-country.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/front-office/currency-and-language-by-country/)
>
> ---


# Moneda e idioma por país

## 1. Requisitos y compatibilidad

- **Versiones de PrestaShop compatibles**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilidad con PHP**: PHP 7.1 - 8.5
- **Requisitos de alojamiento**: Las extensiones PHP estándar (cURL, JSON, OpenSSL) suelen ser necesarias para PrestaShop y normalmente están disponibles en cualquier entorno de alojamiento moderno. No se necesitan extensiones especiales para este módulo.

## 2. Recorrido completo de configuración (Cada ajuste agrupado por pantalla)

### 2.1 Página de configuración del módulo (Back Office > Módulos > Configurar)

Esta es la pantalla de configuración principal y única para el módulo "Moneda e idioma por país". Aquí encontrará todos los ajustes para definir cómo su tienda se adapta a los visitantes de países específicos.

**Acceso:** Back Office > Módulos > Gestor de módulos > Busque "Moneda e idioma por país" > Haga clic en "Configurar".

#### **1. Seleccionar país**

- **Qué hace este ajuste:** Este desplegable le permite elegir el país específico para el que desea aplicar los cambios automáticos de idioma y moneda.
- **Efecto de cambiar este ajuste:** Cuando selecciona un país (por ejemplo, "Francia"), el módulo aplicará la configuración de idioma y moneda que defina a continuación *solo* para los visitantes detectados como procedentes de ese país. Si no selecciona un país, el módulo no aplicará ninguna regla de geolocalización.
- **Valor recomendado:** Seleccione primero el país al que desea dirigirse. Solo puede configurar un país a la vez con esta versión gratuita.
- **Escenario / ejemplo de comerciante:** Si desea que los visitantes de Alemania vean su tienda en alemán con moneda euro, seleccionaría "Alemania" aquí.

#### **2. Activar cambio de idioma por visitante**

- **Qué hace este ajuste:** Este interruptor controla si el módulo debe cambiar automáticamente el idioma de la tienda para los visitantes del país seleccionado.
- **Efecto de cambiar este ajuste:**
  - *Cuando está activado ("Activado"):* El módulo intentará cambiar el idioma del front-office de la tienda al que especifique en el ajuste "Seleccionar idioma" a continuación, para los visitantes del país elegido.
  - *Cuando está desactivado ("Desactivado"):* El idioma no se cambiará automáticamente, incluso si ha seleccionado un idioma a continuación. El visitante verá la tienda en su idioma predeterminado o en el idioma preferido de su navegador (si el comportamiento predeterminado de PrestaShop lo permite).
- **Valor recomendado:** "Activado" si desea proporcionar una experiencia de idioma localizada.
- **Escenario / ejemplo de comerciante:** Si seleccionó "Francia" como país, habilitar este ajuste significa que puede elegir "Francés" como idioma para los visitantes franceses.

#### **3. Seleccionar idioma**

- **Qué hace este ajuste:** Este desplegable aparece solo si "Activar cambio de idioma por visitante" está habilitado. Le permite elegir qué idioma se establecerá para los visitantes del país seleccionado.
- **Efecto de cambiar este ajuste:** El idioma del front-office de la tienda cambiará automáticamente al idioma seleccionado para los visitantes del país elegido. Asegúrese de que este idioma ya esté instalado y habilitado en su tienda PrestaShop (Back Office > Internacional > Idiomas).
- **Valor recomendado:** El idioma oficial del país que seleccionó.
- **Escenario / ejemplo de comerciante:** Si seleccionó "España" como país y habilitó el cambio de idioma, seleccionaría "Español" aquí.

#### **4. Activar cambio de moneda por visitante**

- **Qué hace este ajuste:** Este interruptor controla si el módulo debe cambiar automáticamente la moneda de la tienda para los visitantes del país seleccionado.
- **Efecto de cambiar este ajuste:**
  - *Cuando está activado ("Activado"):* El módulo intentará cambiar la moneda del front-office de la tienda a la que especifique en el ajuste "Seleccionar moneda" a continuación, para los visitantes del país elegido.
  - *Cuando está desactivado ("Desactivado"):* La moneda no se cambiará automáticamente. Los precios se mostrarán en la moneda predeterminada de su tienda o en la moneda seleccionada manualmente por el cliente.
- **Valor recomendado:** "Activado" si desea mostrar los precios en la moneda local.
- **Escenario / ejemplo de comerciante:** Si seleccionó "Estados Unidos" como país, habilitar este ajuste significa que puede elegir "Dólar estadounidense" como moneda para los visitantes de EE. UU.

#### **5. Seleccionar moneda**

- **Qué hace este ajuste:** Este desplegable aparece solo si "Activar cambio de moneda por visitante" está habilitado. Le permite elegir qué moneda se establecerá para los visitantes del país seleccionado.
- **Efecto de cambiar este ajuste:** Todos los precios en el front-office de la tienda cambiarán automáticamente a la moneda seleccionada para los visitantes del país elegido. Asegúrese de que esta moneda ya esté instalada y habilitada en su tienda PrestaShop (Back Office > Internacional > Monedas).
- **Valor recomendado:** La moneda oficial del país que seleccionó.
- **Escenario / ejemplo de comerciante:** Si seleccionó "Japón" como país y habilitó el cambio de moneda, seleccionaría "Yen japonés" aquí.

#### **Nota importante sobre las anulaciones (Overrides):**

Este módulo utiliza el sistema de anulación de PrestaShop para modificar el comportamiento central de la moneda y el idioma. Si tiene otros módulos que también utilizan anulaciones para `Currency.php` o `Language.php`, podría haber conflictos. Siempre pruebe a fondo después de la instalación.

### 2.2 Tabla de referencia rápida de configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e impacto |
| --- | --- | --- | --- |
| Configuración del módulo | Seleccionar país | Su país objetivo | Define el país para el que se aplican las reglas. |
| Configuración del módulo | Activar cambio de idioma por visitante | Activado | Activa el cambio automático de idioma para el país seleccionado. |
| Configuración del módulo | Seleccionar idioma | Idioma oficial del país | Establece el idioma específico para los visitantes del país elegido. |
| Configuración del módulo | Activar cambio de moneda por visitante | Activado | Activa el cambio automático de moneda para el país seleccionado. |
| Configuración del módulo | Seleccionar moneda | Moneda oficial del país | Establece la moneda específica para los visitantes del país elegido. |

## 3. Solución de problemas del comerciante y preguntas frecuentes (FAQ)

**P: El idioma/moneda no cambia para los visitantes del país seleccionado. ¿Qué debo verificar?**
R:

1. **Módulo habilitado:** Asegúrese de que el módulo "Moneda e idioma por país" esté instalado y habilitado en el Gestor de módulos.
2. **Configuración guardada:** Vuelva a verificar que ha seleccionado un país, ha habilitado las opciones de cambio de idioma/moneda respectivas, ha elegido el idioma/moneda correctos y ha hecho clic en "Guardar" en la página de configuración del módulo.
3. **Idioma/moneda instalados y habilitados:** Verifique que el idioma y la moneda de destino estén instalados y habilitados en su Back Office de PrestaShop (Internacional > Idiomas e Internacional > Monedas).
4. **Caché:** Borre la caché de su PrestaShop (Parámetros avanzados > Rendimiento > Borrar caché) y la caché de su navegador.
5. **Precisión de la geolocalización:** Los servicios de geolocalización no siempre son 100% precisos. Pruebe con una VPN para asegurarse de que su IP se identifique correctamente como procedente del país de destino.

**P: ¿Puedo configurar diferentes idiomas/monedas para varios países?**
R: El módulo gratuito "Moneda e idioma por país" le permite configurar reglas para un solo país a la vez. Si necesita una segmentación avanzada para varios países, considere actualizar al módulo "Geolocation Pro" de MyPresta.eu, que ofrece características más amplias.

**P: El idioma/moneda predeterminado de mi tienda sigue apareciendo incluso después de la configuración.**
R: Este módulo se dirige específicamente a los visitantes del país *seleccionado*. Para todos los demás visitantes, se aplicarán el idioma y la moneda predeterminados de su tienda, o la configuración preferida de su navegador si PrestaShop está configurado para respetarlos. Asegúrese de que está probando desde el país exacto que configuró.

**P: Instalé otro módulo y ahora el cambio de idioma/moneda no funciona.**
R: Este módulo utiliza el sistema de anulación de PrestaShop. Si otro módulo también anula `classes/Currency.php` o `classes/Language.php`, podría haber un conflicto. Verifique su `app/config/parameters.php` (para PS 1.7+) o `config/settings.inc.php` (para PS 1.6) para `_PS_MODE_DEV_` y configúrelo en `true` para ver los mensajes de error. Es posible que deba ponerse en contacto con el soporte para obtener ayuda para resolver conflictos de anulación.

**P: ¿Cómo detecta el módulo el país del visitante?**
R: El módulo utiliza la dirección IP del visitante para determinar su ubicación geográfica. Este es un método estándar para la geolocalización.

## 4. Guía para desarrolladores y webmasters (Arquitectura técnica y mapa de código)

Esta sección proporciona una descripción técnica detallada para desarrolladores y webmasters que trabajan con el módulo "Moneda e idioma por país".

### 4.1 Descripción general de la arquitectura

El módulo "Moneda e idioma por país" (`freegeo`) es un módulo ligero de PrestaShop diseñado principalmente para modificar el idioma y la moneda predeterminados basándose en la dirección IP de un visitante. Lo logra aprovechando el sistema de anulación de PrestaShop para las clases centrales `Currency` y `Language`, y enganchándose al evento `actionDispatcherBefore` para realizar la lógica de geolocalización antes de que se renderice el contenido principal de la página. La configuración del módulo se gestiona a través del método estándar `getContent()` en el archivo principal del módulo.

### 4.2 Controladores (`controllers/`)

Este módulo no introduce ningún controlador personalizado de Front-Office o Back-Office. Su lógica se ejecuta principalmente a través de hooks y anulaciones de clases.

### 4.3 Clases y modelos principales (`classes/`)

El módulo utiliza el sistema de anulación de PrestaShop para inyectar su lógica en las funcionalidades principales.

- **`freegeo/override/classes/Currency.php`**

  - **Nombre de la clase:** `Currency` (anula la clase `Currency` principal)
  - **Clase padre:** `CurrencyCore`
  - **Responsabilidad:** Esta anulación es crucial para establecer la moneda basándose en la geolocalización. Modifica el comportamiento de cómo se determina la moneda activa. La lógica del módulo dentro de esta anulación verificará si la configuración `FREEGEO_CURRENCY_ON` está habilitada y si el país del visitante coincide con el `FREEGEO_COUNTRY` configurado. Si es así, intentará forzar la moneda a `FREEGEO_CURRENCY`.
  - **Métodos clave:** La anulación probablemente modifica métodos relacionados con `getCurrent()` o `getCurrency()` para inyectar el ID de moneda geolocalizado.
- **`freegeo/override/classes/Language.php`**

  - **Nombre de la clase:** `Language` (anula la clase `Language` principal)
  - **Clase padre:** `LanguageCore`
  - **Responsabilidad:** Similar a la anulación de `Currency`, esta clase es responsable de establecer el idioma basándose en la geolocalización. Verifica `FREEGEO_LANGUAGE_ON` y `FREEGEO_COUNTRY` y, si se cumplen las condiciones, fuerza el idioma a `FREEGEO_LANGUAGE`.
  - **Métodos clave:** La anulación probablemente modifica métodos relacionados con `getCurrentLanguage()` o `getLanguage()` para inyectar el ID de idioma geolocalizado.
- **`freegeo/override/classes/index.php`**

  - **Propósito:** Este es un archivo `index.php` vacío estándar, típicamente colocado en directorios para evitar la lista de directorios en los servidores web, mejorando la seguridad. No tiene ningún impacto funcional en la lógica del módulo.

### 4.4 Activos de JavaScript (`views/js/`)

Este módulo no incluye ningún archivo JavaScript personalizado. Toda su funcionalidad se gestiona en el lado del servidor.

### 4.5 Hojas de estilo CSS (`views/css/`)

Este módulo no incluye ningún archivo CSS personalizado. Su funcionalidad no implica ningún estilo específico de front-office.

### 4.6 Estructura de la plantilla Smarty (`views/templates/`)

- **`freegeo/views/advert.tpl`**
  - **Alcance:** Back-office (página de configuración del módulo).
  - **Propósito:** Esta plantilla se utiliza probablemente para mostrar un anuncio o mensaje promocional para el módulo "Geolocation Pro" de MyPresta.eu en la página de configuración del módulo. Sirve como un elemento de marketing dentro de la interfaz de administración.
  - **Hook:** Esta plantilla se renderiza dentro del método `getContent()` del archivo principal del módulo, típicamente antes o después del formulario de configuración principal.

### 4.7 Esquema de la base de datos y mapa de Hooks

- **Tablas de la base de datos**:
  El módulo no crea ninguna tabla de base de datos personalizada. Almacena su configuración directamente en la tabla `ps_configuration` de PrestaShop.
- **Registros de configuración en `ps_configuration`**:

  - `FREEGEO_CURRENCY_ON`: Almacena un booleano (0 o 1) que indica si el cambio de moneda está habilitado.
  - `FREEGEO_LANGUAGE_ON`: Almacena un booleano (0 o 1) que indica si el cambio de idioma está habilitado.
  - `FREEGEO_CURRENCY`: Almacena el ID de la moneda a establecer (por ejemplo, `id_currency`).
  - `FREEGEO_LANGUAGE`: Almacena el ID del idioma a establecer (por ejemplo, `id_lang`).
  - `FREEGEO_COUNTRY`: Almacena el código ISO o ID del país a segmentar.
- **Tabla de Hooks registrados**:

| Nombre del Hook | Momento de ejecución | Propósito técnico |
| --- | --- | --- |
| `actionAdminControllerSetMedia` | Se ejecuta cuando un controlador de administración establece sus activos multimedia (JS/CSS). | Aunque está listado, este módulo probablemente lo usa mínimamente o para la carga específica de scripts/estilos del lado del administrador si hubiera alguno (ninguno detectado en el inventario). |
| `actionDispatcherBefore` | Se ejecuta muy temprano en el ciclo de vida de la solicitud de PrestaShop, antes de que el despachador procese la URL. | **HOOK CRÍTICO:** Aquí reside la lógica central de geolocalización del módulo. Se utiliza para detectar la IP del visitante, determinar su país y luego, basándose en la configuración del módulo, potencialmente anular `Context::getContext()->language` y `Context::getContext()->currency` antes de que se renderice la página. |
| `actionFrontControllerAfterInit` | Se ejecuta después de que se ha inicializado un controlador de Front-Office. | Este hook podría usarse para realizar comprobaciones o ajustes adicionales después de que se configure el controlador principal, pero antes de la renderización. Podría servir como un punto de respaldo o suplementario para los ajustes de idioma/moneda si `actionDispatcherBefore` no es suficiente en todos los escenarios. |

## 5. Soporte oficial y actualizaciones

Para obtener las últimas actualizaciones, correcciones de errores y soporte oficial para el módulo "Moneda e idioma por país", consulte su cuenta de cliente en [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nuestro equipo de soporte está disponible para ayudarle con cualquier problema o pregunta que pueda tener con respecto a la funcionalidad y compatibilidad del módulo.
