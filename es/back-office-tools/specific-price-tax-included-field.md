---
title: "Campo de precio específico con impuestos incluidos - Manual de comerciante y guía de configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop 'Specific price tax included field' de MyPresta.eu."
sidebar:
  label: "Campo de precio específico con impuestos incluidos - Manual de comerciante y guía de configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Specific price tax included field en MyPresta.eu](https://mypresta.eu/modules/administration-tools/specific-price-tax-included-field.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/back-office-tools/specific-price-tax-included-field/)
>
> ---


# Campo de precio específico con impuestos incluidos

## 1. Requisitos y compatibilidad

- **Versiones de PrestaShop compatibles**: PrestaShop 1.7.x
- **Compatibilidad con PHP**: PHP 7.1 - 8.5
- **Requisitos de alojamiento**: Extensiones PHP estándar (cURL, JSON, OpenSSL).

## 2. Recorrido completo por la configuración (Cada ajuste agrupado por pantalla)

### 2.1 Página de configuración del módulo (Back Office > Módulos > Configurar)

Después de la instalación, haga clic en "Configurar" junto al módulo "Specific price tax included field" en el Gestor de módulos. Esto le llevará a la pantalla de configuración principal del módulo.

#### Ajustes generales

- **Qué hace este ajuste:** Esta sección normalmente contiene ajustes generales relacionados con las actualizaciones del módulo y las comprobaciones de versión.
- **Efecto de cambiar este ajuste:**
  - *Cuando está activado:* El módulo comprobará periódicamente si hay nuevas versiones disponibles en MyPresta.eu y le notificará en el Back Office. Esto garantiza que siempre esté ejecutando la versión más reciente, segura y con más funciones.
  - *Cuando está desactivado:* El módulo no realizará comprobaciones automáticas de actualizaciones. Tendría que comprobar manualmente las actualizaciones visitando su cuenta de MyPresta.eu.
- **Valor recomendado:** **SÍ** (o activado). Mantener esto activado garantiza que se mantenga informado sobre actualizaciones importantes y correcciones de errores.
- **Escenario / ejemplo de comerciante:** Desea recibir una notificación si se lanza una nueva versión del módulo que incluye correcciones de compatibilidad para una nueva versión de PrestaShop o mejoras de rendimiento. Mantener esto activado mostrará una notificación en su Back Office.

### 2.2 Tabla de referencia rápida de configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| Configuración del módulo | Comprobaciones de actualización (mypresta\_updates, update\_, updatev\_) | Activado | Comprueba periódicamente si hay nuevas versiones del módulo y le notifica en el Back Office. |

## 3. Resolución de problemas del comerciante y preguntas frecuentes (FAQ)

**P: He instalado el módulo, pero no veo el nuevo campo "Precio con impuestos incluidos".**
R: Primero, asegúrese de que el módulo esté activado en **Módulos > Gestor de módulos**. Luego, navegue a la página de un producto, vaya a la pestaña "Precios" y haga clic en "Añadir un nuevo precio específico" o "Editar" uno existente. El nuevo campo debería aparecer dentro del formulario de creación/edición de precios específicos. Si aún no está visible, intente borrar la caché de PrestaShop (**Parámetros avanzados > Rendimiento**, luego haga clic en "Borrar caché").

**P: El precio calculado sin impuestos parece incorrecto.**
R: El módulo se basa en la regla fiscal asignada al producto.
1. **Verifique la regla fiscal del producto:** Vaya a la página del producto, pestaña "Precios", y verifique que la "Regla fiscal" correcta esté seleccionada para el producto.
2. **Verifique la configuración de la regla fiscal:** Vaya a **Internacional > Impuestos > Reglas de impuestos** y asegúrese de que los tipos impositivos definidos para la regla fiscal seleccionada sean correctos para sus países/zonas objetivo.
3. **Borre la caché:** Después de verificar y posiblemente corregir la configuración de impuestos, borre la caché de PrestaShop.

**P: ¿Este módulo afecta a los precios específicos existentes?**
R: No, este módulo solo añade un nuevo campo de entrada al formulario de creación/edición de precios específicos. No altera ni recalcula ningún precio específico que se haya creado antes de su instalación o utilizando el campo predeterminado "Precio sin impuestos". Simplemente proporciona una forma alternativa de introducir nuevos precios específicos.

**P: ¿Funcionará este módulo con mi tema personalizado?**
R: Sí, este módulo modifica principalmente un formulario estándar del Back Office de PrestaShop. Utiliza hooks estándar de PrestaShop y JavaScript para inyectar el nuevo campo. Es muy poco probable que entre en conflicto con temas personalizados del front-office, ya que no tiene componentes de visualización en el front-office.

**P: Recibo un error después de actualizar PrestaShop.**
R: Después de cualquier actualización importante de PrestaShop, es una buena práctica:
1. Borrar la caché de PrestaShop (**Parámetros avanzados > Rendimiento**).
2. Buscar una nueva versión del módulo "Specific price tax included field" en su cuenta de MyPresta.eu, ya que las actualizaciones a menudo incluyen correcciones de compatibilidad.
3. Si el problema persiste, póngase en contacto con el soporte de MyPresta.eu.

## 4. Guía para desarrolladores y webmasters (Arquitectura técnica y mapa de código)

### 4.1 Visión general de la arquitectura

El módulo "Specific price tax included field" (`sptincl`) es un módulo ligero de PrestaShop 1.7.x diseñado para mejorar la interfaz de gestión de precios específicos en el Back Office. Opera principalmente inyectando JavaScript en el hook `actionAdminControllerSetMedia`, que luego modifica el DOM del formulario de precios específicos para añadir el campo "Precio con impuestos incluidos" e implementar la lógica de cálculo necesaria en el lado del cliente. No introduce nuevas tablas de base de datos, controladores o lógica de negocio compleja en el lado del servidor más allá de su configuración.

### 4.2 Controladores (`controllers/`)

Este módulo no introduce ningún controlador de administración de Front-Office o Back-Office personalizado. Toda su funcionalidad se inyecta en las páginas de administración existentes de PrestaShop a través de hooks y JavaScript.

### 4.3 Clases y modelos principales (`classes/`)

Este módulo no introduce ninguna clase PHP personalizada o definiciones de `ObjectModel`. Su lógica central reside en el archivo principal del módulo (`sptincl.php`).

### 4.4 Activos JavaScript (`views/js/`)

- **`sptincl/views/js/sptincl.js`**
  - **Alcance:** Back-office (específicamente, el formulario de creación/edición de precios específicos).
  - **Propósito:** Este script es responsable de la funcionalidad principal del módulo.
    - **Manipulación del DOM:** Añade dinámicamente un nuevo campo de entrada para "Precio con impuestos incluidos" al formulario de precios específicos. También modifica el comportamiento del campo existente "Precio sin impuestos".
    - **Detectores de eventos:** Adjunta detectores de eventos (por ejemplo, `keyup`, `change`) tanto al nuevo campo "Precio con impuestos incluidos" como al campo existente "Precio sin impuestos", así como al selector de reglas fiscales.
    - **Lógica de cálculo:** Cuando un usuario introduce un valor en el campo "Precio con impuestos incluidos" o cambia la regla fiscal, el script calcula el valor correspondiente de "Precio sin impuestos" utilizando el tipo impositivo seleccionado. Por el contrario, si se modifica el campo "Precio sin impuestos", calcula el valor de "Precio con impuestos incluidos".
    - **AJAX (Implícito):** Aunque no realiza directamente llamadas AJAX, se basa en los tipos impositivos disponibles en el DOM o obtenidos por los mecanismos existentes de PrestaShop para realizar sus cálculos. Utiliza la función `getTaxRate()` (que podría ser una función JS global de PrestaShop o una personalizada definida dentro del script) para recuperar el tipo impositivo actual basándose en la regla fiscal seleccionada.

### 4.5 Hojas de estilo CSS (`views/css/`)

Este módulo no incluye ningún archivo CSS personalizado. Se basa en el estilo predeterminado de PrestaShop para los elementos del formulario, lo que garantiza una integración perfecta con la interfaz de usuario del Back Office.

### 4.6 Estructura de la plantilla Smarty (`views/templates/`)

Este módulo no utiliza archivos de plantilla Smarty personalizados. Su configuración se gestiona directamente dentro del método `getContent()` de la clase principal del módulo, y sus modificaciones de front-end son puramente impulsadas por JavaScript.

### 4.7 Esquema de la base de datos y mapa de hooks

- **Tablas de la base de datos**: Este módulo no crea ninguna tabla de base de datos personalizada. Almacena sus ajustes de configuración (como `mypresta_updates`, `update_`, `updatev_`) en la tabla estándar `ps_configuration`.
- **Tabla de Hooks registrados**:

| Nombre del Hook | Momento de ejecución | Propósito técnico |
| --- | --- | --- |
| `actionAdminControllerSetMedia` | Se ejecuta cuando se inicializa un controlador de administración y se están configurando sus activos multimedia (JS/CSS). | Este es el hook principal utilizado por el módulo. Inyecta el archivo JavaScript `sptincl.js` en el Back Office, dirigiéndose específicamente al formulario de creación/edición de precios específicos. Esto permite que el módulo modifique el DOM del formulario y añada su lógica de cálculo en el lado del cliente. |

## 5. Soporte oficial y actualizaciones

Para las últimas actualizaciones, correcciones de errores y soporte oficial para el módulo "Specific price tax included field", consulte su cuenta de cliente en [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nuestro equipo de soporte está disponible para ayudarle con cualquier problema o pregunta que pueda tener con respecto a la funcionalidad y compatibilidad del módulo.
"""
