---
title: "Desactivar descuento de grupo en el carrito con código de cupón - Manual de Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop 'Desactivar descuento de grupo en el carrito con código de cupón' de MyPresta.eu."
sidebar:
  label: "Desactivar descuento de grupo en el carrito con código de cupón - Manual de Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Disable group discount in cart with voucher code en MyPresta.eu](https://mypresta.eu/modules/ordering-process/disable-group-discount-in-cart-with-voucher-code.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/ordering-process/disable-group-discount-in-cart-with-voucher-code/)
>
> ---


# Desactivar descuento de grupo en el carrito con código de cupón

## 1. Requisitos y Compatibilidad

- **Versiones de PrestaShop compatibles**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilidad con PHP**: PHP 7.1 - 8.5
- **Requisitos de alojamiento**: Extensiones PHP estándar (cURL, JSON, OpenSSL).

## 2. Recorrido completo por la configuración (Cada ajuste agrupado por pantalla)

### 2.1 Página de configuración del módulo (Back Office > Módulos > Configurar)

Después de la instalación, haga clic en "Configurar" junto al nombre del módulo para acceder a sus ajustes.

#### Ajuste: Desactivar descuento de grupos en el carrito con regla de carrito

Este es el interruptor de control principal para la funcionalidad del módulo.

- **Qué hace este ajuste:** Este ajuste determina si el módulo interviene activamente para desactivar los descuentos de grupo cuando hay un código de cupón presente en el carrito.
- **Efecto de cambiar este ajuste:**
  - ***Cuando está Habilitado:*** Si un cliente pertenece a un grupo con un descuento especial (por ejemplo, 10% de descuento para "Clientes Mayoristas") Y aplica un código de cupón (regla de carrito) a su carrito, el descuento de grupo será ignorado. Solo se aplicará el descuento del cupón al total del pedido. Esto evita que el cliente reciba ambos descuentos simultáneamente.
  - ***Cuando está Deshabilitado:*** El módulo no intervendrá. Se aplicará el comportamiento predeterminado de PrestaShop, lo que significa que si un cliente es elegible tanto para un descuento de grupo como para un descuento de cupón, ambos podrían aplicarse, lo que podría apilar los descuentos.
- **Valor recomendado:** **Habilitado**. Esta es la funcionalidad principal del módulo y generalmente se recomienda para evitar la acumulación no deseada de descuentos y proteger sus márgenes de beneficio durante las campañas de cupones.
- **Escenario / ejemplo de comerciante:**
  - *Escenario 1 (Habilitado):* Tiene un grupo de "Clientes VIP" que obtiene un 5% de descuento en todos los productos. También ejecuta un código de cupón "VERANO20" para un 20% de descuento. Un cliente VIP añade artículos a su carrito y aplica "VERANO20". Con el módulo **Habilitado**, solo obtendrá el 20% de descuento del cupón, no el 5% + 20%.
  - *Escenario 2 (Deshabilitado):* Usando el mismo ejemplo, si el módulo está **Deshabilitado**, el cliente VIP podría recibir tanto el 5% de descuento de grupo como el 20% de descuento del cupón, lo que llevaría a un descuento total del 25% (o un cálculo más complejo dependiendo del orden interno de aplicación de descuentos de PrestaShop).

### 2.2 Tabla de referencia rápida de configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| Configuración del módulo | Desactivar descuento de grupos en el carrito con regla de carrito | Habilitado | Cuando está habilitado, los descuentos de grupo se ignoran si hay un código de cupón presente en el carrito, asegurando que solo se aplique el descuento del cupón. Evita la acumulación de descuentos. |

## 3. Solución de problemas del comerciante y preguntas frecuentes (FAQ)

**P1: Habilité el módulo, pero los clientes siguen obteniendo ambos descuentos. ¿Qué está mal?**
R1: Primero, asegúrese de que el módulo esté realmente "Habilitado" en su configuración. Segundo, borre la caché de su PrestaShop (Vaya a **Parámetros avanzados > Rendimiento**, luego haga clic en "Borrar caché" en la esquina superior derecha). A veces, los datos de caché antiguos pueden evitar que los cambios surtan efecto inmediatamente. Además, pruebe con un carrito nuevo y una nueva sesión de cliente (por ejemplo, en una ventana de navegador de incógnito).

**P2: ¿Este módulo afectará mis precios específicos o reglas de precio de catálogo?**
R2: No, este módulo se dirige específicamente a los *descuentos de grupo* y las *reglas de carrito (códigos de cupón)*. No interfiere con los precios específicos establecidos para productos individuales, combinaciones de productos o reglas de precio de catálogo que se aplican según la cantidad u otras condiciones. Solo modifica la interacción entre los descuentos de grupo de clientes y los códigos de cupón.

**P3: ¿Este módulo funciona con todos los tipos de códigos de cupón (porcentaje, cantidad fija, envío gratuito)?**
R3: Sí, la lógica del módulo está diseñada para detectar la presencia de *cualquier* regla de carrito (código de cupón) activa en el carrito. Una vez que se detecta una regla de carrito, deshabilitará el descuento de grupo, independientemente del tipo de descuento que proporcione el cupón (porcentaje, cantidad fija, envío gratuito, etc.).

**P4: ¿Qué pasa si quiero permitir descuentos de grupo Y un código de cupón para una promoción específica?**
R4: Si tiene una promoción específica en la que *sí* desea permitir que ambos descuentos se acumulen, deberá **Deshabilitar** temporalmente este módulo en su configuración. Recuerde volver a habilitarlo una vez que finalice esa promoción específica si desea volver al comportamiento de descuento "solo cupón".

## 4. Guía para desarrolladores y webmasters (Arquitectura técnica y mapa de código)

### 4.1 Resumen de la arquitectura

Este módulo funciona principalmente a través de una anulación de una clase central de PrestaShop. En lugar de usar hooks, modifica directamente el comportamiento de la clase `Product` para ajustar cómo se calculan los precios cuando hay un descuento de grupo de cliente involucrado y una regla de carrito activa. Este enfoque asegura que la lógica de descuento se aplique a un nivel fundamental durante la recuperación del precio del producto.

### 4.2 Controladores (`controllers/`)

- Este módulo no incluye ningún controlador personalizado de front-office o back-office. Su funcionalidad se implementa mediante anulaciones de clases.

### 4.3 Clases y modelos principales (`classes/`)

- **Ruta del archivo**: `exgcr/override/classes/Product.php`

  - **Nombre de la clase**: `Product` (anula la clase `Product` principal)
  - **Clase padre**: `ProductCore`
  - **Responsabilidad**: Esta anulación modifica el método `getPriceStatic` de la clase `Product`. El método `getPriceStatic` es crucial ya que es responsable de calcular el precio final de un producto, teniendo en cuenta varios factores como impuestos, precios específicos, grupos de clientes y reglas de carrito.
  - **Lógica clave**:
    - La anulación verifica si el módulo `exgcr` está habilitado.
    - Luego verifica si hay una `CartRule` (código de cupón) activa aplicada al carrito actual.
    - Si se cumplen ambas condiciones (módulo habilitado Y cupón presente), modifica los parámetros pasados al método `getPriceStatic` padre para ignorar efectivamente el descuento de grupo de cliente. Específicamente, establece el parámetro `$use_group_reduction` en `false` al llamar al método padre, evitando así que se aplique el descuento de grupo.
    - Esto asegura que cuando se utiliza un cupón, el cálculo del precio procede como si el cliente no perteneciera a un grupo con descuento, evitando así la acumulación de descuentos de grupo con descuentos de cupón.
- **Ruta del archivo**: `exgcr/override/classes/index.php`

  - **Propósito**: Este es un archivo `index.php` vacío estándar colocado en directorios para evitar la lista de directorios (medida de seguridad). No contiene código funcional.

### 4.4 Activos de JavaScript (`views/js/`)

- Este módulo no incluye ningún archivo JavaScript personalizado.

### 4.5 Hojas de estilo CSS (`views/css/`)

- Este módulo no incluye ningún archivo CSS personalizado.

### 4.6 Estructura de plantillas Smarty (`views/templates/`)

- Este módulo no incluye ningún archivo de plantilla Smarty personalizado. Su configuración se maneja directamente dentro del método `getContent()` del archivo principal del módulo.

### 4.7 Esquema de la base de datos y mapa de hooks

- **Tablas de la base de datos**:

  - Este módulo no crea ninguna tabla de base de datos personalizada.
  - Almacena su configuración (`exgcr`) en la tabla estándar `ps_configuration`.
    - Entrada `PS_CONFIGURATION`: `EXGCR_ENABLED` (almacena `1` para habilitado, `0` para deshabilitado).
- **Tabla de Hooks registrados**:

  - Este módulo no registra ningún hook específico en la tabla `ps_hook_module`. Su funcionalidad se implementa a través de una anulación de clase, que es una forma más directa de modificar el comportamiento central sin depender de la ejecución de hooks.

## 5. Soporte oficial y actualizaciones

Para las últimas actualizaciones, correcciones de errores y soporte profesional para el módulo "Desactivar descuento de grupo en el carrito con código de cupón", consulte su cuenta de cliente en [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nuestro equipo de soporte está disponible para ayudar con cualquier problema o pregunta que pueda tener con respecto a la funcionalidad del módulo y su integración con su tienda PrestaShop.
