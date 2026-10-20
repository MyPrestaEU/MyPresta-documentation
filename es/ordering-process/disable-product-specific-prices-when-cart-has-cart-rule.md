---
title: "Desactivar precios específicos de productos cuando el carrito tiene una regla de carrito - Manual de Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop 'Desactivar precios específicos de productos cuando el carrito tiene una regla de carrito' de MyPresta.eu."
sidebar:
  label: "Desactivar precios específicos de productos cuando el carrito tiene una regla de carrito - Manual de Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Disable product specific prices when cart has cart rule en MyPresta.eu](https://mypresta.eu/modules/ordering-process/disable-product-specific-prices-when-cart-has-cart-rule.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/ordering-process/disable-product-specific-prices-when-cart-has-cart-rule/)
>
> ---


# Desactivar precios específicos de productos cuando el carrito tiene una regla de carrito

## 1. Requisitos y Compatibilidad

Este módulo está diseñado para funcionar sin problemas con instalaciones modernas de PrestaShop.

- **Versiones de PrestaShop compatibles**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilidad con PHP**: PHP 7.1 - 8.5
- **Requisitos de alojamiento**: Se requieren extensiones PHP estándar (cURL, JSON, OpenSSL) para PrestaShop en sí y suelen estar disponibles en cualquier entorno de alojamiento web moderno. No hay requisitos de alojamiento especiales más allá de una configuración estándar de PrestaShop.

## 2. Recorrido completo por la configuración (Cada ajuste agrupado por pantalla)

Este módulo tiene una única y sencilla pantalla de configuración.

### 2.1 Página de configuración del módulo (Back Office > Módulos > Configurar)

Para acceder a la configuración, navegue a **Módulos > Gestor de módulos**, busque "Desactivar precios específicos de productos cuando el carrito tiene una regla de carrito" y haga clic en el botón "Configurar".

![Marcador de posición de captura de pantalla de configuración del módulo]
*(Imagine una captura de pantalla aquí mostrando un formulario simple con un único interruptor de palanca etiquetado "Desactivar el uso de precios específicos en el carrito con regla de carrito" y las opciones "Activado" / "Desactivado".)*

**Ajuste: Desactivar el uso de precios específicos en el carrito con regla de carrito**

- **Qué hace este ajuste:** Este es el interruptor de control principal para la funcionalidad central del módulo. Determina si el módulo interviene activamente para desactivar los precios específicos cuando hay una regla de carrito (código de cupón) presente en el carrito del cliente.
- **Efecto de cambiar este ajuste:**
  - **Cuando está activado (SÍ):** Si un cliente aplica cualquier regla de carrito (código de cupón) a su carrito, el módulo evitará que se apliquen precios específicos de productos a los productos de ese carrito. Los precios de los productos volverán a su precio base antes de que se aplique el descuento de la regla de carrito, asegurando que solo el descuento de la regla de carrito afecte el precio final. Esto evita el doble descuento.
  - **Cuando está desactivado (NO):** El módulo estará inactivo. Los precios específicos y las reglas de carrito funcionarán de forma independiente, lo que significa que pueden acumularse en el mismo producto, lo que lleva a la aplicación simultánea de múltiples descuentos. Este es el comportamiento predeterminado de PrestaShop.
- **Valor recomendado:** **Activado (SÍ)**. Este es el propósito principal del módulo y le permite proteger sus márgenes de beneficio y controlar su estrategia de descuentos.
- **Escenario / ejemplo de comerciante:**
  - **Elija "Activado"** si desea asegurarse de que cuando un cliente utiliza un código de cupón (por ejemplo, "AHORRA10" para un 10% de descuento), se ignoren los precios específicos existentes en los productos de su carrito. Esto significa que el 10% de descuento se aplicará al precio regular del producto, no a un precio específico ya descontado. Esto evita que un producto se descuente dos veces.
  - **Elija "Desactivado"** si prefiere el comportamiento predeterminado de PrestaShop donde los precios específicos y las reglas de carrito pueden acumularse, lo que podría llevar a descuentos más profundos de lo previsto. Esto podría ser deseado en campañas promocionales muy específicas y agresivas, pero generalmente, "Activado" se recomienda para la protección de beneficios.

### 2.2 Tabla de referencia rápida de configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| Configuración del módulo | Desactivar el uso de precios específicos en el carrito con regla de carrito | Activado | Cuando está activado, los precios específicos se ignoran si hay una regla de carrito activa en el carrito, evitando dobles descuentos. |

## 3. Solución de problemas del comerciante y preguntas frecuentes (FAQ)

**P1: Habilité el módulo, pero los precios específicos siguen apareciendo incluso con un código de cupón. ¿Qué pasa?**

- **R:** Primero, asegúrese de haber guardado la configuración después de habilitar el módulo.
- **R:** Borre la caché de su PrestaShop. Vaya a **Parámetros avanzados > Rendimiento** y haga clic en "Borrar caché" en la esquina superior derecha.
- **R:** Pruebe con un carrito nuevo. A veces, la caché del navegador o los datos de sesión pueden interferir. Intente en una ventana de incógnito.
- **R:** Verifique que la regla de carrito con la que está probando esté realmente activa y se aplique correctamente a los productos del carrito.

**P2: Mis clientes se quejan de que sus precios específicos desaparecieron cuando usaron un cupón. ¿Es esto lo esperado?**

- **R:** Sí, este es el comportamiento previsto del módulo. Cuando el módulo está habilitado y un cliente aplica una regla de carrito (cupón), los precios específicos de los productos en el carrito se desactivan temporalmente para evitar el doble descuento. El precio del producto se calculará entonces en función de su precio original, aplicándose el descuento de la regla de carrito. Es posible que desee actualizar sus términos y condiciones o mensajes promocionales para aclarar cómo interactúan los descuentos.

**P3: ¿Este módulo afecta a otros tipos de descuentos, como descuentos por categoría o descuentos por grupo de clientes?**

- **R:** Este módulo se dirige específicamente a los "precios específicos" (descuentos establecidos directamente en productos individuales o combinaciones) y su interacción con las "reglas de carrito" (códigos de cupón). No interfiere directamente con otros mecanismos de descuento como descuentos por categoría, descuentos por grupo de clientes o descuentos por cantidad, a menos que estos se implementen como precios específicos.

**P4: ¿Este módulo ralentizará mi tienda?**

- **R:** El módulo realiza pequeñas anulaciones en las clases principales de PrestaShop para ajustar la lógica de cálculo de precios. Estos cambios están altamente optimizados y deberían tener un impacto insignificante en el rendimiento de su tienda. El módulo solo activa su lógica cuando hay una regla de carrito presente, por lo que no está funcionando constantemente.

**P5: Quiero permitir temporalmente que los precios específicos y las reglas de carrito se acumulen para una promoción especial. ¿Cómo lo hago?**

- **R:** Simplemente vaya a la página de configuración del módulo (**Módulos > Gestor de módulos > Configurar** para "Desactivar precios específicos de productos cuando el carrito tiene una regla de carrito") y establezca la opción "Desactivar el uso de precios específicos en el carrito con regla de carrito" en **"Desactivado"**. Recuerde volver a activarlo después de que finalice su promoción especial para restaurar el comportamiento de protección predeterminado.

## 4. Guía para desarrolladores y webmasters (Arquitectura técnica y mapa de código)

Esta sección proporciona una descripción técnica detallada para desarrolladores y webmasters que trabajan con el módulo "Desactivar precios específicos de productos cuando el carrito tiene una regla de carrito".

### 4.1 Descripción general de la arquitectura

Este módulo funciona principalmente anulando las clases principales de PrestaShop relacionadas con el cálculo de precios y la gestión de precios específicos. Aprovecha el mecanismo de anulación de PrestaShop para inyectar su lógica en las clases `Cart`, `Product` y `SpecificPrice`. La idea central es detectar la presencia de una regla de carrito en el carrito actual y, si se encuentra, modificar el comportamiento de la recuperación de precios específicos para ignorarlos efectivamente durante los cálculos de precios.

La configuración principal del módulo se gestiona a través del método `getContent()` en el archivo principal del módulo, almacenando un simple indicador booleano en `ps_configuration`.

### 4.2 Controladores (`controllers/`)

Este módulo no introduce ningún controlador personalizado de front-office o back-office. Su lógica está completamente incrustada dentro de las anulaciones de clase.

- **Controladores de Front-Office**: Ninguno
- **Controladores de Administración de Back-Office**: Ninguno

### 4.3 Clases y modelos principales (`classes/`)

La funcionalidad principal del módulo reside en sus anulaciones de clase. Estos archivos se encuentran en `cartspecdis/override/classes/`. PrestaShop carga automáticamente estas anulaciones, reemplazando las clases principales originales con las versiones modificadas del módulo.

- **`cartspecdis/override/classes/Cart.php`**

  - **Nombre de la clase y clase padre**: `Cart` (anula `\Cart`)
  - **Responsabilidad**: Esta anulación es crucial. Probablemente introduce un método o modifica uno existente (por ejemplo, `getProducts()`, `getPackageList()` o un ayudante de cálculo de precios) para verificar la presencia de reglas de carrito. Si se encuentran reglas de carrito, establece un indicador o modifica parámetros que influyen en cómo se recuperan o aplican posteriormente los precios específicos. El método `hasCartRules()` es un candidato probable para verificar las reglas de carrito.
  - **Lógica clave**: La anulación probablemente agregará una verificación dentro de los métodos de cálculo de precios para ver si `Cart::getCartRules()` devuelve alguna regla activa. Si es así, influirá en las llamadas a `Product::getPriceStatic()` o `SpecificPrice::getSpecificPrice()` para ignorar los precios específicos.
- **`cartspecdis/override/classes/Product.php`**

  - **Nombre de la clase y clase padre**: `Product` (anula `\Product`)
  - **Responsabilidad**: Se espera que esta anulación modifique el método `getPriceStatic()`, que es central para cómo se recuperan los precios de los productos en todo PrestaShop.
  - **Lógica clave**: Dentro de `getPriceStatic()`, el módulo probablemente agregará una condición. Si el objeto `Cart` actual (pasado como parámetro o accesible globalmente) contiene reglas de carrito activas, y la configuración del módulo está habilitada, entonces los parámetros pasados a `SpecificPrice::getSpecificPrice()` se alterarán (por ejemplo, `id_specific_price` o indicadores `use_specific_price`) para asegurar que no se devuelva ningún precio específico, o que se omita el cálculo del precio específico.
- **`cartspecdis/override/classes/SpecificPrice.php`**

  - **Nombre de la clase y clase padre**: `SpecificPrice` (anula `\SpecificPrice`)
  - **Responsabilidad**: Es probable que esta anulación modifique el método `getSpecificPrice()`, que es responsable de obtener los detalles de precios específicos para un producto dado.
  - **Lógica clave**: Esta anulación contendrá la lógica directa para evitar que se devuelvan precios específicos. Verificará si el `Cart` actual tiene reglas de carrito y si el módulo está habilitado. Si ambas condiciones son verdaderas, `getSpecificPrice()` se hará que devuelva `false` o un array vacío, indicando efectivamente que no se aplica ningún precio específico, incluso si existe uno en la base de datos. Este es el guardián final de los precios específicos.
- **`cartspecdis/override/classes/index.php`**

  - **Nombre de la clase y clase padre**: Ninguno
  - **Responsabilidad**: Este es un archivo `index.php` vacío estándar, típicamente colocado en directorios para evitar la lista de directorios cuando se accede directamente a través de un navegador web. No tiene ningún impacto funcional en la lógica del módulo.

### 4.4 Activos JavaScript (`views/js/`)

Este módulo no incluye ningún archivo JavaScript personalizado. Toda su lógica se maneja en el lado del servidor.

### 4.5 Hojas de estilo CSS (`views/css/`)

Este módulo no incluye ningún archivo CSS personalizado. No tiene componentes visuales de front-office y su configuración de back-office utiliza elementos de formulario estándar de PrestaShop.

### 4.6 Estructura de plantillas Smarty (`views/templates/`)

Este módulo no utiliza ninguna plantilla Smarty personalizada. Su formulario de configuración se genera dinámicamente mediante el método `getContent()` en el archivo principal del módulo utilizando los formularios de ayuda de PrestaShop.

### 4.7 Esquema de la base de datos y mapa de hooks

- **Tablas de la base de datos**:

  - El módulo no crea ninguna tabla SQL personalizada.
  - Almacena su configuración en la tabla `ps_configuration`:
    - Clave `PS_CONFIGURATION`: `cartspecdis` (almacena el valor booleano para habilitar/deshabilitar la funcionalidad principal del módulo).
- **Tabla de Hooks registrados**:

| Nombre del Hook | Momento de ejecución | Propósito técnico |
| --- | --- | --- |
| `actionAdminControllerSetMedia` | Se ejecuta cuando un Controlador de Administración está configurando sus activos multimedia (CSS/JS). | Este hook es típicamente utilizado por los módulos para añadir sus propios archivos CSS o JavaScript al Back Office. Para este módulo, es probable que se utilice para asegurar que se carguen los estilos o scripts necesarios del lado del administrador (aunque no se enumeran explícitamente en el inventario), o podría ser un remanente de una estructura de módulo de plantilla. Dado que no se enumeran archivos JS/CSS, su propósito principal aquí es probablemente mínimo o para futuras expansiones. |

### 4.8 Archivo principal del módulo (`cartspecdis/cartspecdis.php`)

- **Nombre de la clase**: `Cartspecdis` (extiende `Module`)
- **`__construct()`**: Inicializa los metadatos del módulo (nombre, pestaña, versión, autor, `need_instance`, `ps_versions_compliancy`).
- **`install()`**:
  - Llama a `parent::install()`.
  - Registra el hook `actionAdminControllerSetMedia`.
  - Establece el valor de configuración predeterminado para `cartspecdis` en `1` (activado) en `ps_configuration`.
  - Registra las anulaciones de clase (`Cart`, `Product`, `SpecificPrice`).
- **`uninstall()`**:
  - Llama a `parent::uninstall()`.
  - Desregistra el hook `actionAdminControllerSetMedia`.
  - Elimina el valor de configuración `cartspecdis` de `ps_configuration`.
  - Desregistra las anulaciones de clase.
- **`getContent()`**:
  - Gestiona el envío del formulario para la configuración del módulo.
  - Actualiza el valor de configuración `cartspecdis` en `ps_configuration` basándose en la entrada del usuario.
  - Muestra un mensaje de confirmación.
  - Renderiza el formulario de configuración utilizando la clase `HelperForm` de PrestaShop, incluyendo el único interruptor de palanca para "Desactivar el uso de precios específicos en el carrito con regla de carrito".
- **`hookActionAdminControllerSetMedia()`**:
  - Este método se llama cuando se ejecuta el hook `actionAdminControllerSetMedia`.
  - Se utiliza típicamente para añadir archivos CSS o JavaScript al Back Office. En el estado actual de este módulo (basado en el inventario), probablemente contiene poco o ningún código activo para añadir activos, o es un marcador de posición.

## 5. Soporte oficial y actualizaciones

Para obtener las últimas actualizaciones, correcciones de errores y soporte oficial para el módulo "Desactivar precios específicos de productos cuando el carrito tiene una regla de carrito", consulte su cuenta de cliente en MyPresta.eu.

- **Actualizaciones del módulo**: Inicie sesión en su cuenta de MyPresta.eu y navegue a su historial de pedidos y sección de descargas para obtener la versión más reciente del módulo.
- **Soporte técnico**: Si encuentra algún problema o tiene preguntas que no están cubiertas en esta documentación, abra un ticket de soporte a través de su cuenta de cliente de MyPresta.eu. Nuestro equipo estará encantado de ayudarle.
