---
title: "Excluir descuento de grupo de productos con precio específico - Manual de Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop 'Excluir descuento de grupo de productos con precio específico' de MyPresta.eu."
sidebar:
  label: "Excluir descuento de grupo de productos con precio específico - Manual de Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Exclude group discount from products with specific price en MyPresta.eu](https://mypresta.eu/modules/ordering-process/exclude-group-discount-from-products-with-specific-price.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/ordering-process/exclude-group-discount-from-products-with-specific-price/)
>
> ---


# Excluir descuento de grupo de productos con precio específico

## 1. Requisitos y Compatibilidad

- **Versiones de PrestaShop Compatibles**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilidad PHP**: PHP 5.6 - 8.5
- **Requisitos de Alojamiento**: Las extensiones PHP estándar (cURL, JSON, OpenSSL) suelen ser suficientes. No se requieren configuraciones de servidor inusuales.

## 2. Recorrido Completo de Configuración (Cada Ajuste Agrupado por Pantalla)

### 2.1 Página de Configuración del Módulo (Back Office > Módulos > Configurar)

Después de la instalación, navegue a **Módulos > Gestor de Módulos**, busque "Excluir descuento de grupo de productos con precio específico" y haga clic en **Configurar**. Verá la pantalla de configuración principal.

#### Ajuste: Deshabilitar descuento de grupos para productos con precios específicos

- **Qué hace este ajuste:** Este es el control central de la funcionalidad del módulo. Determina si el módulo debe evitar activamente que los descuentos de grupo se apliquen a productos que ya tienen precios específicos.
- **Efecto de cambiar este ajuste:**
  - **Cuando se establece en "Activado":** Si un producto tiene un precio específico (por ejemplo, un precio de venta especial que usted ha establecido), y un cliente de un grupo que normalmente recibe un descuento (por ejemplo, "Clientes VIP" obtienen un 10% de descuento) ve o compra ese producto, el 10% de descuento de grupo *no* se aplicará. El cliente pagará el precio específico que usted estableció. Este es el comportamiento previsto del módulo.
  - **Cuando se establece en "Desactivado":** El módulo estará inactivo. El comportamiento predeterminado de PrestaShop se reanudará. Esto significa que si un producto tiene un precio específico, y un cliente de un grupo con descuento lo ve o lo compra, *tanto* el precio específico como el descuento de grupo se aplicarán, lo que podría llevar a un precio final mucho más bajo de lo previsto.
- **Valor recomendado:** **Activado**. Este es el propósito del módulo, evitar la acumulación no deseada de descuentos.
- **Escenario / ejemplo de comerciante:** Tiene una "Venta de Verano" donde una camiseta específica tiene un precio de $15 (de $25). También tiene un grupo de clientes "Mayoristas" que obtiene un 20% de descuento en todos los pedidos.
  - Si este ajuste está **Activado**: Un cliente mayorista compra la camiseta. Paga $15. El 20% de descuento mayorista se ignora para este producto específico.
  - Si este ajuste está **Desactivado**: Un cliente mayorista compra la camiseta. PrestaShop primero aplica el precio específico ($15), luego aplica el 20% de descuento mayorista a $15, haciendo que el precio final sea $12. Esto podría ser inferior a su margen de beneficio deseado.

#### Tabla de Referencia Rápida de Configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| Página de Configuración del Módulo | Deshabilitar descuento de grupos para productos con precios específicos | Activado | Controla si se evita que los descuentos de grupo se acumulen con los precios específicos. **Activado** evita la acumulación, preservando los márgenes de beneficio. **Desactivado** permite la acumulación, lo que podría llevar a precios más bajos. |

## 3. Solución de Problemas del Comerciante y Preguntas Frecuentes (FAQ)

**P: He activado el módulo, pero los descuentos de grupo todavía se aplican a mis precios específicos. ¿Qué está mal?**
R:

1. **Borrar Caché:** Siempre borre la caché de su PrestaShop después de realizar cambios de configuración. Vaya a **Parámetros Avanzados > Rendimiento**, luego haga clic en "Borrar caché" en la esquina superior derecha.
2. **Orden de Módulos:** En casos raros, otro módulo podría estar anulando los cálculos de precios. Si tiene otros módulos de precios o descuentos, intente deshabilitarlos temporalmente uno por uno para ver si hay un conflicto.
3. **Configuración de Precio Específico:** Verifique que sus "precios específicos" estén configurados correctamente para los productos en cuestión. Vaya a la página de edición del producto, luego a la pestaña "Precios" y asegúrese de que el precio específico esté activo y aplicado correctamente.
4. **Configuración de Descuento de Grupo:** Verifique que el descuento de grupo de clientes esté configurado correctamente en **Parámetros de la Tienda > Configuración de Clientes > Grupos**.

**P: ¿Este módulo afectará mis reglas de carrito o códigos de cupón regulares?**
R: No, este módulo se dirige específicamente a los "descuentos de grupo" (descuentos aplicados automáticamente según el grupo asignado a un cliente) y su interacción con los "precios específicos" (anulaciones manuales de precios para un producto). No interfiere con las reglas de carrito de PrestaShop, los códigos de cupón u otros mecanismos promocionales, a menos que esos mecanismos se basen en precios específicos o descuentos de grupo.

**P: ¿Este módulo ralentiza mi tienda?**
R: No, el módulo es muy ligero. Funciona anulando una clase central de PrestaShop (`Product.php`) para modificar cómo se calculan los precios. Este es un proceso altamente optimizado y no debería introducir ninguna degradación notable del rendimiento.

**P: ¿Qué pasa si quiero que los descuentos de grupo *a veces* se apliquen a precios específicos?**
R: Este módulo ofrece un enfoque de "todo o nada": o los descuentos de grupo se excluyen de *todos* los productos con precios específicos, o no. Si necesita un control más granular (por ejemplo, excluir para el Producto A pero permitir para el Producto B, ambos con precios específicos), este módulo por sí solo no lo logrará. Tendría que gestionar los precios específicos y los descuentos de grupo manualmente o considerar un módulo de precios más avanzado. Para este módulo, la recomendación es activarlo para evitar la acumulación no deseada.

## 4. Guía para Desarrolladores y Webmasters (Arquitectura Técnica y Mapa de Código)

Esta sección es estrictamente para desarrolladores, webmasters de tiendas y agencias técnicas que mantienen o extienden la tienda.

### 4.1 Resumen de la Arquitectura

El módulo `Exclude group discount from products with specific price` implementa su funcionalidad principal a través de una anulación de la clase `Product`. Este es un patrón de desarrollo común y efectivo de PrestaShop para modificar comportamientos centrales sin alterar directamente los archivos centrales. Al anular `Product::getPriceStatic()`, el módulo intercepta la lógica de cálculo de precios para evitar que se apliquen descuentos específicos de grupo cuando un producto tiene un precio específico activo.

### 4.2 Controladores (`controllers/`)

- **Controladores de Front-Office**: Ninguno. Toda la lógica del front-office se maneja a través de la anulación de la clase `Product`.
- **Controladores de Administración de Back-Office**: Ninguno. La configuración del módulo se maneja directamente dentro del método `getContent()` del archivo principal del módulo.

### 4.3 Clases y Modelos Centrales (`classes/`)

La funcionalidad principal del módulo reside en su anulación de clase.

- **Ruta del Archivo**: `exgdis/override/classes/Product.php`
- **Nombre de la Clase**: `Product` (anula la clase `Product` central)
- **Clase Padre**: `ProductCore`
- **Responsabilidad**: Esta anulación modifica el método `getPriceStatic()`, que es fundamental para cómo PrestaShop calcula los precios de los productos en todo el front office (páginas de productos, carrito, pago) y el back office.
  - **Lógica Clave**: Dentro del método `getPriceStatic()` anulado, el módulo verifica si su configuración `exgdis_groups` (que corresponde a "Deshabilitar descuento de grupos para productos con precios específicos") está activada.
  - Si está activada, y si el producto que se está valorando actualmente tiene un precio específico activo, el módulo asegura que el parámetro `$use_group_reduction` pasado al método original `ProductCore::getPriceStatic()` se establezca en `false`. Esto le dice efectivamente a PrestaShop que *no* aplique ningún descuento específico de grupo para ese cálculo de precio en particular.
  - El archivo `index.php` en `override/classes/` es un archivo vacío estándar para evitar la lista de directorios.

### 4.4 Activos JavaScript (`views/js/`)

- Ninguno. El módulo no tiene componentes JavaScript de front-end o back-end.

### 4.5 Hojas de Estilo CSS (`views/css/`)

- Ninguno. El módulo no tiene estilos CSS personalizados.

### 4.6 Estructura de Plantillas Smarty (`views/templates/`)

- Ninguno. La configuración del módulo se renderiza directamente a través de `getContent()` en el archivo principal del módulo, y su funcionalidad se basa puramente en la lógica, no en la visualización.

### 4.7 Esquema de Base de Datos y Mapa de Hooks

- **Tablas de Base de Datos**: El módulo no crea ninguna tabla de base de datos personalizada. Almacena su configuración en la tabla `ps_configuration`.

  - Entrada `ps_configuration`: `exgdis_groups` (almacena el estado activado/desactivado del ajuste principal).
- **Tabla de Hooks Registrados**: El módulo no registra explícitamente ningún hook en la tabla `ps_hook_module`. Su funcionalidad se implementa a través de una anulación de clase, que es cargada por el mecanismo de anulación de PrestaShop.

| Nombre del Hook | Momento de Ejecución | Propósito Técnico |
| --- | --- | --- |
| `override/classes/Product.php` | Durante las llamadas a `Product::getPriceStatic()` | Intercepta el cálculo de precios para evitar descuentos de grupo en productos con precios específicos. |

## 5. Soporte Oficial y Actualizaciones

Para las últimas actualizaciones, correcciones de errores y soporte oficial para el módulo "Excluir descuento de grupo de productos con precio específico", consulte su cuenta de cliente de MyPresta.eu. Puede descargar las versiones más recientes y acceder a los recursos de soporte directamente desde [MyPresta.eu](https://mypresta.eu).
