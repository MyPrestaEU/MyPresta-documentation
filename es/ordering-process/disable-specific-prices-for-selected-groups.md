---
title: "Desactivar precios específicos para grupos seleccionados - Manual de Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop 'Desactivar precios específicos para grupos seleccionados' de MyPresta.eu."
sidebar:
  label: "Desactivar precios específicos para grupos seleccionados - Manual de Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Disable specific prices for selected groups en MyPresta.eu](https://mypresta.eu/modules/ordering-process/disable-specific-prices-for-selected-groups.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/ordering-process/disable-specific-prices-for-selected-groups/)
>
> ---


# Desactivar precios específicos para grupos seleccionados

## 1. Requisitos y compatibilidad

- **Versiones de PrestaShop compatibles**: PrestaShop 1.6.x, 1.7.x
- **Compatibilidad con PHP**: PHP 5.6 - 8.5
- **Requisitos de alojamiento**: Las extensiones PHP estándar (cURL, JSON, OpenSSL) suelen ser suficientes. No se necesitan configuraciones especiales del servidor.

## 2. Recorrido completo por la configuración (Cada ajuste agrupado por pantalla)

### 2.1 Página de configuración del módulo (Back Office > Módulos > Configurar)

Esta es la pantalla de configuración principal y única para el módulo "Desactivar precios específicos para grupos seleccionados". La encontrará navegando a **Módulos > Gestor de módulos**, buscando "Desactivar precios específicos para grupos seleccionados" y haciendo clic en "Configurar".

#### **1. Desactivar descuentos de precios específicos para grupos seleccionados**

Esta es la configuración principal del módulo. Determina qué grupos de clientes *no* recibirán descuentos de precios específicos.

- **Qué hace esta configuración:** Esta sección presenta una lista de todos los grupos de clientes definidos en su tienda PrestaShop. Puede seleccionar uno o más grupos de esta lista.
- **Efecto de cambiar esta configuración:**
  - *Cuando se selecciona uno o más grupos:* Los clientes que pertenezcan a cualquiera de los grupos seleccionados *no* verán ni se beneficiarán de ningún descuento de precio específico configurado para los productos. Siempre verán y pagarán el precio estándar del producto.
  - *Cuando no se selecciona ningún grupo:* El módulo no desactivará los precios específicos para ningún grupo. Todos los clientes recibirán descuentos de precios específicos según lo configurado en la configuración de sus productos.
- **Valor recomendado:** Seleccione los grupos de clientes específicos para los que desea desactivar los descuentos de precios específicos. Por ejemplo, si tiene un grupo de "Mayoristas" al que desea que siempre pague el precio estándar, seleccione ese grupo.
- **Escenario / ejemplo de comerciante:** Tiene un grupo de clientes "Invitados" y un grupo de "Nuevos Clientes". Desea reservar los descuentos de precios específicos (como precios por volumen o promociones temporales) solo para su grupo de "Clientes Leales". Al seleccionar "Invitados" y "Nuevos Clientes" aquí, estos dos grupos siempre verán el precio regular, mientras que los "Clientes Leales" seguirán beneficiándose de cualquier precio específico que haya configurado.

#### **2. Habilitado**

Este es el interruptor global de encendido/apagado para la funcionalidad del módulo.

- **Qué hace esta configuración:** Es un simple interruptor para activar o desactivar la lógica central del módulo.
- **Efecto de cambiar esta configuración:**
  - *Cuando está habilitado (SÍ):* El módulo desactivará activamente los precios específicos para los grupos que haya seleccionado en la sección "Desactivar descuentos de precios específicos para grupos seleccionados".
  - *Cuando está deshabilitado (NO):* El módulo estará inactivo. Todos los precios específicos funcionarán como el comportamiento estándar de PrestaShop, independientemente de los grupos seleccionados en la sección anterior. Esto desactiva efectivamente el impacto del módulo sin desinstalarlo.
- **Valor recomendado:** **SÍ** si tiene la intención de usar la funcionalidad del módulo. **NO** si desea deshabilitarlo temporalmente sin perder sus selecciones de grupo.
- **Escenario / ejemplo de comerciante:** Ha configurado el módulo para deshabilitar precios específicos para su grupo de clientes "Minoristas". Si desea ejecutar una promoción temporal donde *todos* los grupos, incluido "Minoristas", deben recibir descuentos de precios específicos, simplemente puede establecer "Habilitado" en **NO**. Una vez que termine la promoción, vuelva a cambiarlo a **SÍ** para volver a habilitar la desactivación de precios específicos para los clientes "Minoristas".

#### **3. Devolver siempre el precio más bajo**

Esta configuración ofrece una capa adicional de control, especialmente cuando los precios específicos pueden interactuar con otras reglas de precios.

- **Qué hace esta configuración:** Este interruptor determina si el módulo debe aplicar estrictamente el precio estándar para los grupos seleccionados, o si aún debe considerar el *precio más bajo posible* (que podría incluir otros tipos de descuentos no gestionados por precios específicos) si resulta ser inferior al precio estándar.
- **Efecto de cambiar esta configuración:**
  - *Cuando está habilitado (SÍ):* Para los grupos seleccionados, los precios específicos se ignorarán. Sin embargo, si existe *otro* mecanismo (por ejemplo, una regla de carrito, un descuento global o un tipo diferente de reducción de precio) que resulte en un precio inferior al precio estándar, el módulo permitirá que se aplique ese precio más bajo. Esto garantiza que los clientes siempre obtengan el precio más bajo absoluto disponible *fuera* de los precios específicos.
  - *Cuando está deshabilitado (NO):* Para los grupos seleccionados, los precios específicos se ignorarán, y el módulo aplicará estrictamente el *precio estándar del producto*. No se considerarán otros posibles precios más bajos (a menos que formen parte del precio base en sí). Esto proporciona el control más rígido sobre los precios para los grupos seleccionados.
- **Valor recomendado:** **NO** para un control estricto, asegurando que los grupos seleccionados siempre paguen el precio estándar. **SÍ** si desea deshabilitar los precios específicos pero aún permitir que se apliquen otros descuentos no relacionados con precios específicos si resultan en un precio más bajo.
- **Escenario / ejemplo de comerciante:**
  - *Escenario 1 (Recomendado: NO):* Desea que su grupo de "Mayoristas" *siempre* pague el precio completo y estándar, y nunca se beneficie de ningún descuento de precio específico ni de ninguna otra posible reducción de precio. Establecería esto en **NO**.
  - *Escenario 2 (Recomendado: SÍ):* Desea deshabilitar los precios específicos para su grupo de "Invitados", pero también tiene una regla de carrito general de "5% de descuento en todos los productos" que se aplica a todos. Si establece "Devolver siempre el precio más bajo" en **SÍ**, los invitados no obtendrán descuentos de precios específicos, pero *sí* obtendrán el descuento de la regla de carrito del 5% si hace que el precio sea inferior al precio estándar. Si se establece en **NO**, pagarían el precio estándar completo, ignorando incluso la regla de carrito del 5%.

### 2.2 Tabla de referencia rápida de configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| Configuración del módulo | Desactivar descuentos de precios específicos para grupos seleccionados | Seleccionar grupos según sea necesario | Selecciona los grupos de clientes para los que se ignorarán los descuentos de precios específicos. |
| Configuración del módulo | Habilitado | SÍ | Interruptor global de ENCENDIDO/APAGADO para la funcionalidad del módulo. |
| Configuración del módulo | Devolver siempre el precio más bajo | NO (para control estricto) / SÍ (para flexibilidad) | Determina si otros descuentos no específicos de precios aún pueden aplicarse si resultan en un precio más bajo para los grupos afectados. |

## 3. Solución de problemas del comerciante y preguntas frecuentes (FAQ)

**P: He configurado el módulo, pero los clientes del grupo seleccionado siguen viendo precios específicos. ¿Qué ocurre?**
R:

1.  **Compruebe la configuración "Habilitado":** Asegúrese de que el interruptor "Habilitado" en la configuración del módulo esté en **SÍ**.
2.  **Verifique la selección de grupo:** Vuelva a comprobar que los grupos de clientes correctos están seleccionados en "Desactivar descuentos de precios específicos para grupos seleccionados".
3.  **Borrar caché de PrestaShop:** Vaya a **Parámetros avanzados > Rendimiento** y haga clic en "Borrar caché". PrestaShop a menudo almacena en caché la información de precios.
4.  **Compruebe el grupo del cliente:** Asegúrese de que el cliente con el que está probando esté realmente asignado al grupo que ha seleccionado en el módulo. Puede comprobarlo en **Clientes > Clientes** en el Back Office.
5.  **Compatibilidad del tema:** Aunque es raro, algunos temas muy personalizados podrían interferir. Si el problema persiste, intente cambiar temporalmente al tema predeterminado de PrestaShop para descartar conflictos con el tema.

**P: ¿Qué sucede si un cliente está en varios grupos, y un grupo está seleccionado para deshabilitar precios específicos mientras que otro no?**
R: La lógica central de PrestaShop suele priorizar el precio más bajo. La anulación de este módulo intentará eliminar los precios específicos para *cualquier* grupo seleccionado. Si un cliente está en un grupo que *debería* tener los precios específicos deshabilitados, el módulo intentará aplicar el precio estándar. La configuración "Devolver siempre el precio más bajo" determinará entonces si se consideran otros descuentos no específicos de precios.

**P: ¿Este módulo afecta a otros tipos de descuentos, como las reglas de carrito o las reglas de precios de catálogo?**
R: Este módulo se dirige específicamente a los "precios específicos" tal como se definen en PrestaShop (los descuentos establecidos directamente en las páginas de productos o mediante importación CSV).

- Si "Devolver siempre el precio más bajo" está en **NO**, el módulo aplicará estrictamente el precio estándar para los grupos seleccionados, anulando potencialmente otros descuentos si resultan en un precio inferior al precio estándar.
- Si "Devolver siempre el precio más bajo" está en **SÍ**, el módulo deshabilitará los precios específicos, pero aún permitirá que se apliquen otros tipos de descuentos (como reglas de carrito o reglas de precios de catálogo) si resultan en un precio inferior al precio estándar.

**P: Quiero deshabilitar temporalmente el módulo sin perder mi configuración. ¿Cómo lo hago?**
R: Simplemente vaya a la página de configuración del módulo y establezca el interruptor "Habilitado" en **NO**. Todos sus grupos seleccionados y otras configuraciones se conservarán, y podrá volver a habilitarlo en cualquier momento volviéndolo a cambiar a **SÍ**.

**P: ¿Cómo traduzco el texto del módulo a otros idiomas?**
R: Vaya a **Internacional > Traducciones** en su Back Office de PrestaShop. Seleccione "Traducciones de módulos instalados", elija su tema y luego seleccione "Desactivar precios específicos para grupos seleccionados". A continuación, podrá traducir cualquier cadena de texto visible.

## 4. Guía para desarrolladores y webmasters (Arquitectura técnica y mapa de código)

Esta sección es estrictamente para desarrolladores, webmasters de tiendas y agencias técnicas que mantienen o extienden la tienda.

### 4.1 Resumen de la arquitectura

El módulo "Desactivar precios específicos para grupos seleccionados" funciona principalmente anulando las clases principales de PrestaShop relacionadas con la fijación de precios de productos, específicamente `Product.php` y `SpecificPrice.php`. Esto le permite interceptar y modificar la lógica que determina si los precios específicos se aplican a un producto, basándose en el grupo del cliente actual y la configuración del módulo. Sigue una estructura de módulo estándar de PrestaShop con un archivo de módulo principal y anulaciones de clases.

### 4.2 Controladores (`controllers/`)

Este módulo no utiliza ningún controlador de administración de Front-Office o Back-Office personalizado. Toda la configuración se maneja a través del método `getContent()` de la clase principal del módulo.

### 4.3 Clases y modelos principales (`classes/`)

La funcionalidad principal del módulo se implementa a través de anulaciones de clases.

- **`exsdis/override/classes/index.php`**:

  - Este es un archivo `index.php` vacío estándar, típicamente colocado en directorios para evitar la lista de directorios. No tiene ningún impacto funcional en la lógica del módulo.
- **`exsdis/override/classes/Product.php`**:

  - **Clase original**: `classes/Product.php`
  - **Propósito**: Esta anulación modifica la clase `Product`, que es central para cómo se recupera y calcula la información del producto, incluidos los precios, en PrestaShop. La lógica del módulo dentro de esta anulación intercepta las llamadas para recuperar precios específicos para un producto.
  - **Lógica clave**: Comprueba si el módulo está habilitado y si el grupo de clientes actual se encuentra entre los seleccionados para tener los precios específicos deshabilitados. Si es así, manipula el proceso de recuperación de precios específicos para garantizar que no se devuelvan precios específicos para ese cliente. También considera la configuración `exsdis_lowest` para determinar si el precio más bajo absoluto (excluyendo los precios específicos) aún debe devolverse.
- **`exsdis/override/classes/SpecificPrice.php`**:

  - **Clase original**: `classes/SpecificPrice.php`
  - **Propósito**: Esta anulación se dirige a la clase `SpecificPrice`, que es responsable de gestionar y aplicar las reglas de precios específicos.
  - **Lógica clave**: Probablemente modifica métodos dentro de esta clase (por ejemplo, `getSpecificPrice()`, `getSpecificPrices()`) para evitar que se creen o devuelvan objetos de precios específicos para clientes en los grupos designados. Esto funciona en conjunto con la anulación de `Product.php` para garantizar que los precios específicos se ignoren eficazmente.

### 4.4 Activos de JavaScript (`views/js/`)

Este módulo no incluye ningún archivo JavaScript personalizado.

### 4.5 Hojas de estilo CSS (`views/css/`)

Este módulo no incluye ningún archivo CSS personalizado.

### 4.6 Estructura de la plantilla Smarty (`views/templates/`)

Este módulo no incluye ningún archivo de plantilla Smarty personalizado. El formulario de configuración se renderiza dinámicamente mediante el método `getContent()` en `exsdis.php`.

### 4.7 Esquema de la base de datos y mapa de hooks

- **Tablas de la base de datos**:
  El módulo no crea ninguna tabla de base de datos personalizada. Almacena su configuración en la tabla estándar `ps_configuration`.

  - Entradas de `ps_configuration`:
    - `exsdis_`: (Prefijo para la configuración general del módulo)
    - `exsdis_groups`: Almacena un array serializado o una cadena separada por comas de IDs de grupos de clientes para los que se deshabilitan los precios específicos.
    - `exsdis_lowest`: Almacena el valor (0 o 1) para la configuración "Devolver siempre el precio más bajo".
    - `mypresta_updates`, `update_`, `updatev_`: Relacionado con las comprobaciones de actualización de MyPresta.eu.
- **Tabla de Hooks registrados**:
  El módulo no registra explícitamente ningún hook estándar de PrestaShop en su método `install()`. Su funcionalidad se logra principalmente a través de anulaciones de clases, que modifican directamente el comportamiento central de PrestaShop en lugar de reaccionar a eventos de hook.
  La descripción del módulo menciona "Hooks de Front-Office: Encabezado, Columnas, Producto o Pie de página", pero esto es probablemente una declaración genérica sobre dónde *podrían* mostrarse los precios, no dónde el módulo en sí inyecta contenido a través de hooks. Las anulaciones manejan la lógica de precios a un nivel inferior.

## 5. Soporte oficial y actualizaciones

Para las últimas actualizaciones, correcciones de errores y soporte oficial para el módulo "Desactivar precios específicos para grupos seleccionados", consulte su cuenta de cliente de MyPresta.eu. Puede descargar las versiones más recientes desde su historial de pedidos y acceder a los canales de soporte dedicados proporcionados por MyPresta.eu.
"""
