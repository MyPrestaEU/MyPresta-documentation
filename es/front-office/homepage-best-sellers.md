---
title: "Los más vendidos en la página de inicio - Manual de comerciante y guía de configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop 'Los más vendidos en la página de inicio' de MyPresta.eu."
sidebar:
  label: "Los más vendidos en la página de inicio"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Homepage Best Sellers en MyPresta.eu](https://mypresta.eu/modules/front-office-features/homepage-best-sellers.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/front-office/homepage-best-sellers/)
>
> ---


# Los más vendidos en la página de inicio

## 1. Requisitos y compatibilidad

- **Versiones de PrestaShop compatibles**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilidad con PHP**: PHP 7.1 - 8.5
- **Requisitos de alojamiento**: Las extensiones PHP estándar (cURL, JSON, OpenSSL) suelen ser necesarias para una tienda PrestaShop y son suficientes para este módulo. No se necesitan configuraciones de servidor inusuales o avanzadas.

## 2. Recorrido completo por la configuración (Cada ajuste agrupado por pantalla)

### 2.1 Página de configuración del módulo (Back Office > Módulos > Configurar)

Después de instalar correctamente el módulo "Los más vendidos en la página de inicio", navegue a **Módulos > Gestor de módulos**, localice "Los más vendidos en la página de inicio" y haga clic en el botón "Configurar". Se le presentará una pantalla de configuración sencilla e intuitiva.

#### Ajustes y opciones:

1.  **Número de productos a mostrar**

    -   **Qué hace este ajuste:** Este es el control principal del módulo. Determina exactamente cuántos de sus productos más vendidos se mostrarán dentro del bloque "Los más vendidos" en la página de inicio de su tienda.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando está habilitado / configurado con un número mayor (por ejemplo, 10):* Su página de inicio mostrará más productos más vendidos. Esto puede ser excelente para tiendas con una amplia gama de artículos populares, ofreciendo a los clientes más opciones. Sin embargo, tenga en cuenta que un número muy alto podría hacer que el bloque sea bastante largo, requiriendo más desplazamiento, o podría potencialmente saturar el diseño de su página de inicio dependiendo de su tema.
        -   *Cuando está deshabilitado / configurado con un número menor (por ejemplo, 4):* Se mostrarán menos productos más vendidos. Esto hace que el bloque sea más compacto y enfocado, lo que puede ser ideal para diseños minimalistas o cuando desea destacar solo los pocos elementos principales.
    -   **Valor recomendado:** Un buen punto de partida suele ser entre **4 y 8 productos**. Esto proporciona suficiente variedad sin abrumar la página. Debe experimentar con diferentes números para ver qué se ve mejor con su tema específico de PrestaShop y el diseño general de su página de inicio.
    -   **Escenario / ejemplo de comerciante:** Si tiene una tienda de moda y desea mostrar una selección curada de sus artículos más populares, podría configurarlo en `4`. Si tiene una gran tienda de electrónica y desea demostrar la amplitud de sus gadgets populares, configurarlo en `8` o `10` podría ser más efectivo.
2.  **Mostrar atributos del producto en la página del producto** (Clave de configuración: `PS_ATTRIBUTE_CATEGORY_DISPLAY`)

    -   **Qué hace este ajuste:** Este ajuste, si está presente en la configuración del módulo, controla si los atributos del producto (como tamaño, color, material, etc.) se muestran en la página del producto real cuando un cliente ve un producto. Es importante tener en cuenta que `PS_ATTRIBUTE_CATEGORY_DISPLAY` es típicamente una configuración global central de PrestaShop, no suele ser gestionada por un módulo específico como "Los más vendidos". Si aparece aquí, es probable que sea un enlace de conveniencia o un módulo que intenta gestionar una configuración global.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando está habilitado (por ejemplo, "Sí" o marcado):* Los atributos del producto serán claramente visibles en la página del producto, permitiendo a los clientes seleccionar variaciones específicas (por ejemplo, "Rojo, Talla M"). Esto es crucial para productos con opciones.
        -   *Cuando está deshabilitado (por ejemplo, "No" o desmarcado):* Los atributos del producto podrían estar ocultos o no mostrarse de la manera estándar en la página del producto, lo que podría confundir a los clientes que intentan seleccionar variaciones del producto.
    -   **Valor recomendado:** **SÍ** (o habilitado). Para casi todas las tiendas de comercio electrónico, es esencial mostrar los atributos del producto en la página del producto para permitir a los clientes elegir variaciones y tomar decisiones de compra informadas.
    -   **Escenario / ejemplo de comerciante:** Si vende zapatos, habilitar esto asegura que los clientes puedan seleccionar "Talla 9, Negro" de las opciones en la página del producto del zapato. Deshabilitarlo haría imposible que especificaran su talla o color deseado.

#### Ajustes internos/no configurables:

-   `update_`, `updatev_`: Estos son parámetros internos de seguimiento de la versión del módulo y de verificación de actualizaciones. No están destinados a la interacción del comerciante, pero aseguran que el módulo pueda verificar su versión y potencialmente notificarle sobre actualizaciones.

### 2.2 Pantallas de administración dedicadas y vistas de controlador

El módulo "Los más vendidos en la página de inicio" está diseñado para la simplicidad y la eficiencia. **No** introduce ninguna pantalla de administración adicional dedicada, elementos de menú personalizados o vistas de controlador complejas más allá de su única y sencilla página de configuración accesible a través del Gestor de módulos. Toda la gestión se realiza directamente en esa única pantalla.

### 2.3 Tabla de referencia rápida de configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e impacto
