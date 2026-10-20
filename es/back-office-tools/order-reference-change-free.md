---
title: "Cambio de referencia de pedido gratis - Manual de comerciante y guía de configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop 'Cambio de referencia de pedido gratis' de MyPresta.eu."
sidebar:
  label: "Cambio de referencia de pedido gratis - Manual de comerciante y guía de configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Order reference change free en MyPresta.eu](https://mypresta.eu/modules/administration-tools/order-reference-change-free.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/back-office-tools/order-reference-change-free/)
>
> ---


# Cambio de referencia de pedido gratis

## 1. Requisitos y compatibilidad

- **Versiones de PrestaShop compatibles**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilidad con PHP**: PHP 7.1 - 8.5
- **Requisitos de alojamiento**: Las extensiones PHP estándar (cURL, JSON, OpenSSL) suelen ser suficientes. No hay requisitos especiales más allá de un entorno de alojamiento estándar de PrestaShop.

## 2. Recorrido completo por la configuración (Cada ajuste agrupado por pantalla)

### 2.1 Página de configuración del módulo (Back Office > Módulos > Configurar)

Después de la instalación, haga clic en "Configurar" junto al módulo "Cambio de referencia de pedido gratis". Se le presentará la pantalla de configuración principal.

#### **Formato de referencia de pedido**

Este es el ajuste principal del módulo, que le permite definir el patrón para los números de referencia de sus pedidos.

-   **Qué hace este ajuste:** Este campo de entrada le permite especificar una plantilla para cómo se generarán los nuevos números de referencia de pedido. Puede usar una combinación de caracteres especiales y marcadores de posición para crear el formato deseado.
-   **Efecto de cambiar este ajuste:**
    -   *Cuando se establece en un formato específico (por ejemplo, `[0-9]{6}`):* Todos los pedidos nuevos recibirán un número de referencia que se adhiere estrictamente a este patrón. Por ejemplo, `[0-9]{6}` generaría una referencia numérica de 6 dígitos como `123456`.
    -   *Cuando se deja en el valor predeterminado (comportamiento predeterminado de PrestaShop):* El módulo no alterará la generación de referencias de pedido, y PrestaShop utilizará su formato alfanumérico estándar (por ejemplo, `ABCDEF123`).
-   **Valor recomendado:** Esto depende completamente de las necesidades de su negocio.
    -   Si necesita una referencia simple, solo numérica, pruebe `[0-9]{6}` para un número de 6 dígitos.
    -   Si desea una combinación de letras mayúsculas y números, `[A-Z0-9]{8}` le daría una referencia alfanumérica de 8 caracteres.
    -   También puede incluir prefijos estáticos, por ejemplo, `MYSTORE-[0-9]{5}` generaría `MYSTORE-12345`.
-   **Escenario / ejemplo de comerciante:**
    -   **Escenario 1: Referencias solo numéricas para contabilidad.** Su software de contabilidad requiere que todas las referencias de pedido sean puramente numéricas y de 8 dígitos. Lo establecería en `[0-9]{8}`.
    -   **Escenario 2: Referencias más cortas y memorables.** Desea referencias más cortas, de 6 caracteres, utilizando solo letras mayúsculas y números para facilitar la comunicación con el cliente. Lo establecería en `[A-Z0-9]{6}`.
    -   **Escenario 3: Referencias de marca.** Desea que todas las referencias comiencen con la inicial de su marca seguida de un número de 5 dígitos. Lo establecería en `M-[0-9]{5}`.

**Marcadores de posición y caracteres disponibles:**
El módulo utiliza una sintaxis similar a las expresiones regulares para definir el formato:

-   `[0-9]`: Representa cualquier dígito único del 0 al 9.
-   `[a-z]`: Representa cualquier letra minúscula única de la a a la z.
-   `[A-Z]`: Representa cualquier letra mayúscula única de la A a la Z.
-   `[a-zA-Z]`: Representa cualquier letra única (mayúscula o minúscula).
-   `[A-Z0-9]`: Representa cualquier letra mayúscula o dígito único.
-   `{n}`: Especifica que el carácter o grupo precedente debe repetirse exactamente `n` veces. Por ejemplo, `[0-9]{6}` significa 6 dígitos.
-   `{n,m}`: Especifica que el carácter o grupo precedente debe repetirse entre `n` y `m` veces.
-   Cualquier otro carácter (por ejemplo, `-`, `_`, `MYSTORE-`) se incluirá literalmente en la referencia.

**Nota importante:** El módulo asegura que la referencia generada sea única. Si una referencia generada ya existe, intentará generar una nueva hasta que se encuentre una referencia única.

#### **Botón Guardar**

-   **Qué hace este ajuste:** Este botón guarda todos los cambios que ha realizado en la página de configuración.
-   **Efecto de cambiar este ajuste:**
    -   *Cuando se hace clic:* Su nuevo formato de referencia de pedido se aplicará inmediatamente a todos los *nuevos* pedidos realizados en su tienda. Las referencias de pedidos existentes no se modificarán.
-   **Valor recomendado:** Haga clic siempre en "Guardar" después de realizar cualquier cambio para asegurarse de que se apliquen.

### 2.2 Tabla de referencia rápida de configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e impacto |
| --- | --- | --- | --- |
| Configuración del módulo | Formato de referencia de pedido | Predeterminado de PrestaShop (alfanumérico) | Define el patrón para los nuevos números de referencia de pedido (por ejemplo, `[0-9]{6}`, `MYSTORE-[A-Z0-9]{5}`). Afecta cómo se referencian los nuevos pedidos en su tienda y en los documentos del cliente. |

## 3. Solución de problemas del comerciante y preguntas frecuentes (FAQ)

**P: Cambié el formato, pero los pedidos antiguos todavía tienen la referencia antigua. ¿Por qué?**
R: Este módulo solo afecta a los *nuevos* pedidos realizados después de guardar la configuración. No cambia retroactivamente las referencias de pedidos existentes, ya que eso podría causar inconsistencias de datos con registros pasados, facturas y comunicaciones con el cliente.

**P: Mis nuevas referencias de pedido no siguen el formato que establecí.**
R:

1.  **¿Hizo clic en "Guardar"?** Asegúrese de haber hecho clic en el botón "Guardar" después de realizar cambios en la página de configuración del módulo.
2.  **Verifique la sintaxis del formato:** Revise su cadena de `Formato de referencia de pedido` en busca de errores tipográficos o caracteres incorrectos. Consulte la sección "Marcadores de posición y caracteres disponibles" anterior.
3.  **Borrar caché:** A veces, la caché de PrestaShop puede evitar que los cambios surtan efecto de inmediato. Vaya a **Parámetros avanzados > Rendimiento** y haga clic en "Borrar caché" (o "Borrar caché de Smarty" en versiones anteriores).
4.  **Conflictos de módulos:** Aunque es raro, otro módulo que modifique en gran medida el proceso de pedido podría entrar en conflicto. Intente deshabilitar temporalmente otros módulos instalados recientemente para ver si el problema se resuelve.

**P: ¿Puedo hacer que la referencia del pedido sea más corta o más larga?**
R: ¡Sí, absolutamente! Use la sintaxis `{n}` o `{n,m}` para especificar la longitud exacta o un rango. Por ejemplo, `[0-9]{4}` para un número de 4 dígitos, o `[A-Z0-9]{10}` para una referencia alfanumérica de 10 caracteres.

**P: ¿Qué sucede si el módulo genera una referencia que ya existe?**
R: El módulo está diseñado para garantizar la unicidad. Si genera una referencia que ya está en uso, intentará automáticamente generar otra hasta que se encuentre una referencia única. Este proceso suele ser instantáneo y asegura que no haya dos pedidos que compartan la misma referencia.

**P: ¿Este módulo afecta el SEO o el rendimiento de mi tienda?**
R: No, este módulo opera puramente en la lógica de backend de la generación de referencias de pedido. No tiene un impacto directo en el SEO de su tienda ni en el rendimiento del front-office.

## 4. Guía para desarrolladores y webmasters (Arquitectura técnica y mapa de código)

### 4.1 Resumen de la arquitectura

El módulo "Cambio de referencia de pedido gratis" logra su funcionalidad a través de una anulación de la clase `Order` central de PrestaShop. En lugar de engancharse directamente a los oyentes de eventos, modifica el comportamiento predeterminado del método `Order::generateReference()`, que es responsable de crear la referencia de pedido única. Este enfoque garantiza que la lógica de generación de referencia personalizada se aplique cada vez que se crea un nuevo pedido, independientemente del flujo específico del front-office.

### 4.2 Controladores (`controllers/`)

Este módulo no introduce ningún controlador personalizado de front-office o back-office. Toda la configuración se maneja a través del método `getContent()` del archivo principal del módulo.

### 4.3 Clases y modelos principales (`classes/`)

-   **`refchange/override/classes/order/Order.php`**
    -   **Propósito**: Este archivo contiene la anulación de la clase `Order` central de PrestaShop. Su función principal es reemplazar el método `generateReference()` predeterminado con una lógica personalizada que aplica el formato definido en la configuración del módulo.
    -   **Clase padre**: Extiende `OrderCore`.
    -   **Métodos clave**:
        -   `generateReference()`: Este método anulado es el corazón del módulo.
            -   Recupera el formato de referencia personalizado de `Configuration::get('REFCHANGE_FORMAT')`.
            -   Si se define un formato personalizado, utiliza un bucle para generar una cadena de referencia basada en el patrón configurado (utilizando `preg_match` y `rand` para la selección de caracteres).
            -   Luego verifica la tabla `ps_orders` para asegurarse de que la referencia generada sea única. Si no es única, la regenera hasta que se encuentre una única.
            -   Si no se define ningún formato personalizado, recurre al método `OrderCore::generateReference()` padre.
    -   **Interacción con la base de datos**: Interactúa con la tabla `ps_orders` para verificar las referencias existentes.

### 4.4 Activos de JavaScript (`views/js/`)

Este módulo no incluye ningún archivo JavaScript personalizado.

### 4.5 Hojas de estilo CSS (`views/css/`)

Este módulo no incluye ningún archivo CSS personalizado.

### 4.6 Estructura de la plantilla Smarty (`views/templates/`)

Este módulo no incluye ningún archivo de plantilla Smarty personalizado. La interfaz de configuración se renderiza directamente dentro del método `getContent()` del archivo principal del módulo.

### 4.7 Esquema de la base de datos y mapa de hooks

-   **Tablas de la base de datos**:
    -   `ps_configuration`: Almacena la configuración del módulo:
        -   `REFCHANGE_FORMAT`: La cadena de formato de referencia de pedido personalizada (por ejemplo, `[0-9]{6}`).
-   **Tabla de hooks registrados**:
    Este módulo no registra explícitamente ningún hook en la tabla `ps_hook_module`. Su funcionalidad se implementa a través de una anulación de clase, lo que significa que modifica el comportamiento central directamente en lugar de responder a eventos de hook específicos.

## 5. Soporte oficial y actualizaciones

Para obtener las últimas actualizaciones, correcciones de errores y soporte profesional para el módulo "Cambio de referencia de pedido gratis", consulte su cuenta de cliente en [MyPresta.eu](https://mypresta.eu). Nuestro equipo se dedica a garantizar que el módulo funcione de manera óptima con su tienda PrestaShop.
