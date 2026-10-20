---
title: "Desactivar vales para artículos en oferta - Manual de Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop 'Desactivar vales para artículos en oferta' de MyPresta.eu."
sidebar:
  label: "Desactivar vales para artículos en oferta - Manual de Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Disable vouchers for items on sale en MyPresta.eu](https://mypresta.eu/modules/advertising-and-marketing/disable-vouchers-for-items-on-sale.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/advertising-marketing/disable-vouchers-for-items-on-sale/)
>
> ---


# Desactivar vales para artículos en oferta

## 1. Requisitos y compatibilidad

- **Versiones de PrestaShop compatibles**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilidad con PHP**: PHP 5.6 - 8.5
- **Requisitos de alojamiento**: Se requieren extensiones PHP estándar (cURL, JSON, OpenSSL), que suelen estar disponibles en cualquier entorno de alojamiento PrestaShop moderno.

## 2. Recorrido completo por la configuración (Cada ajuste agrupado por pantalla)

### 2.1 Página de configuración del módulo (Back Office > Módulos > Configurar)

Esta es la pantalla de configuración principal y única para el módulo "Desactivar vales para artículos en oferta". Puede acceder a ella navegando a **Módulos > Gestor de módulos**, buscando "Desactivar vales para artículos en oferta" y luego haciendo clic en el botón "Configurar".

#### **Configuración general**

- **Desactivar vales para artículos en oferta:**

  - **Qué hace este ajuste:** Este es el interruptor principal para activar o desactivar la funcionalidad principal del módulo.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está habilitado (SÍ):* Si el carrito de un cliente contiene *cualquier* producto que esté actualmente en oferta (tiene un precio especial), se le impedirá aplicar *cualquier* código de vale.
    - *Cuando está deshabilitado (NO):* El módulo estará inactivo. Los clientes podrán aplicar códigos de vale incluso si su carrito contiene artículos en oferta, lo que permite el "doble descuento".
  - **Valor recomendado:** **SÍ** si desea evitar el doble descuento y proteger sus márgenes.
  - **Escenario / ejemplo de comerciante:** Está realizando una "Venta de Verano" con un 20% de descuento en artículos seleccionados. También tiene un vale "Bienvenida10" para nuevos clientes. Si este ajuste es **SÍ**, un nuevo cliente no podrá usar "Bienvenida10" si su carrito incluye algún artículo de la Venta de Verano.
- **Desactivar módulo para códigos que empiezan por:**

  - **Qué hace este ajuste:** Esto le permite crear una excepción. Si un código de vale comienza con una cadena específica que usted defina aquí, la restricción del módulo *no* se aplicará a ese vale, incluso si hay artículos en oferta en el carrito.
  - **Efecto de cambiar este ajuste:**
    - *Cuando se introduce una cadena (por ejemplo, "ENVÍOGRATIS"):* Cualquier código de vale que comience con "ENVÍOGRATIS" (por ejemplo, "ENVÍOGRATIS2023", "ENVÍOGRATISAHORA") omitirá la restricción del módulo. Los clientes pueden usar estos vales específicos incluso con artículos en oferta en su carrito.
    - *Cuando se deja vacío:* No se hacen excepciones basadas en prefijos de códigos de vale. Todos los vales están sujetos a la regla "Desactivar vales para artículos en oferta".
  - **Valor recomendado:** Dejar vacío a menos que tenga vales específicos que *siempre* quiera permitir, independientemente de los artículos en oferta.
  - **Escenario / ejemplo de comerciante:** Tiene un vale especial "ENVÍOGRATIS" que ofrece envío gratuito. Decide que el envío gratuito siempre debe permitirse, incluso en artículos en oferta, para fomentar pedidos más grandes. Introduciría "ENVÍOGRATIS" en este campo.
- **Mensaje para el cliente:**

  - **Qué hace este ajuste:** Este es el mensaje personalizado que los clientes verán en su carrito cuando intenten aplicar un código de vale pero sean bloqueados debido a artículos en oferta.
  - **Efecto de cambiar este ajuste:**
    - *Cuando se introduce un mensaje (por ejemplo, "Los vales no se pueden usar con artículos en oferta."):* Este mensaje exacto se mostrará al cliente.
    - *Cuando se deja vacío:* El módulo probablemente mostrará un mensaje de error predeterminado o genérico, que podría ser menos claro para el cliente.
  - **Valor recomendado:** Un mensaje claro, educado e informativo.
  - **Escenario / ejemplo de comerciante:** Desea informar claramente a los clientes: "Este vale no se puede aplicar porque su carrito contiene artículos ya en oferta. Por favor, elimine los artículos en oferta o use un vale diferente."

#### **Tabla de referencia rápida de configuración**

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| Configuración del módulo | Desactivar vales para artículos en oferta | SÍ | Activa/desactiva la funcionalidad principal para bloquear vales en artículos en oferta. |
| Configuración del módulo | Desactivar módulo para códigos que empiezan por: | Dejar vacío | Permite que códigos de vale específicos (por prefijo) omitan las restricciones del módulo. |
| Configuración del módulo | Mensaje para el cliente | "Los vales no se pueden usar con artículos en oferta." (o similar) | Personaliza el mensaje de error que se muestra a los clientes cuando se bloquea un vale. |

## 3. Solución de problemas para comerciantes y preguntas frecuentes (FAQ)

**P: He habilitado el módulo, pero los clientes aún pueden usar vales en artículos en oferta. ¿Qué pasa?**
R:

1. **Verifique la configuración "Desactivar vales para artículos en oferta":** Asegúrese de que esté configurada en **SÍ** en la configuración del módulo.
2. **Borrar caché:** Vaya a **Parámetros avanzados > Rendimiento** en su Back Office de PrestaShop y haga clic en "Borrar caché" (o "Borrar caché de Smarty" en versiones anteriores). Los cambios en el módulo a veces requieren una actualización de la caché.
3. **Verifique el estado de la oferta:** Vuelva a verificar que los productos con los que está probando estén realmente marcados como "en oferta" en PrestaShop (por ejemplo, tienen un precio específico definido que los hace más baratos que su precio regular).
4. **Verifique la excepción del prefijo del código de vale:** Si ha introducido una cadena en "Desactivar módulo para códigos que empiezan por:", asegúrese de que el vale que está probando no comience con esa cadena.

**P: El módulo está bloqueando los vales, pero el mensaje no aparece o muestra un error genérico.**
R:

1. **Personalice el mensaje:** Vaya a la configuración del módulo y asegúrese de haber introducido un mensaje personalizado en el campo "Mensaje para el cliente".
2. **Compatibilidad con el tema:** Aunque el módulo intenta integrarse sin problemas, algunos temas altamente personalizados pueden anular los mecanismos de visualización de errores predeterminados de PrestaShop. Si el mensaje no aparece, podría ser un problema del tema del front-office. Póngase en contacto con el desarrollador de su tema o con un webmaster para obtener ayuda.

**P: ¿Puedo deshabilitar este módulo para grupos de clientes específicos o productos individuales?**
R: No, este módulo funciona globalmente en función de la presencia de *cualquier* artículo en oferta en el carrito. No ofrece un control granular para grupos de clientes específicos o exclusiones de productos más allá de la excepción del prefijo del código de vale. Si necesita una lógica más avanzada, es posible que se requiera un desarrollo personalizado.

**P: ¿Afectará este módulo a mi SEO o a mis listados de productos?**
R: No, este módulo opera puramente en la lógica de aplicar vales en el carrito. No altera los precios de los productos, descripciones, URL ni ningún otro elemento del front-office que pueda afectar al SEO.

**P: Actualicé mi versión de PrestaShop y ahora el módulo no funciona.**
R:

1. **Verifique la compatibilidad del módulo:** Asegúrese de haber descargado e instalado la versión del módulo diseñada específicamente para su versión de PrestaShop desde su cuenta MyPresta.eu.
2. **Reinstalar/Reconfigurar:** A veces, después de una actualización importante de PrestaShop, los módulos pueden necesitar ser reinstalados o reconfigurados. Intente desinstalar y luego reinstalar el módulo (recuerde hacer una copia de seguridad de su configuración si es posible, aunque este módulo tiene datos mínimos).
3. **Borrar caché:** Siempre borre la caché de su PrestaShop después de cualquier actualización o cambio de módulo.

## 4. Guía para desarrolladores y webmasters (Arquitectura técnica y mapa de código)

### 4.1 Descripción general de la arquitectura

El módulo "Desactivar vales para artículos en oferta" (`dvfis`) funciona principalmente anulando el `CartController` principal para interceptar el proceso de aplicación de vales. Aprovecha el mecanismo de anulación de PrestaShop para inyectar su lógica antes de que un vale sea validado y aplicado. La configuración del módulo se almacena en `ps_configuration` y se accede a ella a través de la clase principal del módulo.

### 4.2 Controladores (`controllers/`)

- **Controladores de Front-Office**:

  - `dvfis/override/controllers/front/CartController.php`
    - **Nombre de la clase y clase padre**: `CartController` (anula la clase `CartController` principal)
    - **Responsabilidad**: Este es el archivo más crítico. Extiende el `CartController` principal para modificar el método `postProcess()`. Específicamente, intercepta la lógica cuando un cliente intenta añadir un vale (`addDiscount()`). Comprueba si el módulo está habilitado y si el carrito contiene algún producto con un precio especial. Si se cumplen ambas condiciones (y el código del vale no coincide con un prefijo de exclusión), impide que se añada el vale y muestra un mensaje de error personalizado.
  - `dvfis/override/controllers/front/index.php`
    - **Nombre de la clase y clase padre**: No es un archivo de clase, normalmente un archivo vacío o un archivo con un `<?php exit;` básico para evitar la lista directa de directorios. Es una práctica estándar para los directorios de anulación de PrestaShop.
- **Controladores de administración de Back-Office**: Ninguno. El módulo utiliza el método `getContent()` estándar dentro de su archivo principal del módulo para la configuración.

### 4.3 Clases y modelos principales (`classes/`)

Ninguno. El módulo no define ninguna clase `ObjectModel` personalizada ni otras clases PHP independientes en el directorio `classes/`. Toda la lógica está contenida dentro del archivo principal del módulo y la anulación del `CartController`.

### 4.4 Activos de JavaScript (`views/js/`)

Ninguno. El módulo no incluye ningún archivo JavaScript personalizado. Todas las interacciones del front-office se gestionan en el lado del servidor mediante la anulación del `CartController`.

### 4.5 Hojas de estilo CSS (`views/css/`)

Ninguno. El módulo no incluye ningún archivo CSS personalizado. Cualquier mensaje que se muestre al cliente heredará el estilo de los mensajes de error/notificación del tema activo de PrestaShop.

### 4.6 Estructura de la plantilla Smarty (`views/templates/`)

Ninguno. El módulo no utiliza archivos de plantilla Smarty personalizados. Los mensajes de error se pasan directamente al array `errors` del `CartController`, que luego son renderizados por el mecanismo de visualización de errores estándar del tema.

### 4.7 Esquema de la base de datos y mapa de hooks

- **Tablas de la base de datos**:
  El módulo no crea ninguna tabla de base de datos personalizada. Todas sus configuraciones se almacenan en la tabla `ps_configuration`:

  - `DVFIS_MESSAGE`: Almacena el mensaje personalizado para los clientes.
  - `DVFIS_ENABLED`: Almacena el valor booleano (0 o 1) para habilitar/deshabilitar el módulo.
  - `DVFIS_STR`: Almacena el prefijo de cadena para las excepciones de códigos de vale.
  - `DVFIS_STRV`: (Probablemente una clave de versionado heredada o interna, no directamente configurable por el usuario).
  - `mypresta_updates`, `update_`, `updatev_`: Claves relacionadas con el sistema de actualización de MyPresta.eu.
  - `PS_LANG_DEFAULT`, `PS_BO_ALLOW_EMPLOYEE_FORM_LANG`: Claves de configuración estándar de PrestaShop utilizadas para la gestión de idiomas en el `getContent()` del módulo.
- **Tabla de Hooks registrados**:

| Nombre del Hook | Momento de ejecución | Propósito técnico |
| --- | --- | --- |
| `actionAdminControllerSetMedia` | Durante la inicialización del controlador del Back Office | Utilizado por el módulo para incluir sus propios archivos CSS/JS (si los hay) en el Back Office. En el caso de este módulo, es probable que se utilice para el sistema de actualización de MyPresta.eu o la configuración general del módulo, no para estilos/scripts personalizados. |
| `actionFrontControllerInitAfter` | Después de que se haya inicializado un controlador del Front Office | Utilizado por el módulo para realizar potencialmente acciones o modificar el comportamiento del controlador al principio del ciclo de vida de la solicitud. Para este módulo, es probable que se utilice para asegurar que la anulación del `CartController` se cargue y esté activa correctamente. |

## 5. Soporte oficial y actualizaciones

Para las últimas actualizaciones, correcciones de errores y soporte oficial para el módulo "Desactivar vales para artículos en oferta", consulte su cuenta de cliente en [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nuestro equipo de soporte está disponible para ayudarle con cualquier problema o pregunta que pueda tener con respecto a la funcionalidad y compatibilidad del módulo.
