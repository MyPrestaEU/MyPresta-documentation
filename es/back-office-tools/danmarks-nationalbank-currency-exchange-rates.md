---
title: "Danmarks Nationalbank - tipos de cambio de divisas - Manual del Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop 'Danmarks Nationalbank - tipos de cambio de divisas' de MyPresta.eu."
sidebar:
  label: "Danmarks Nationalbank - tipos de cambio de divisas - Manual del Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Danmarks Nationalbank - currency exchange rates en MyPresta.eu](https://mypresta.eu/modules/administration-tools/danmarks-nationalbank-currency-exchange-rates.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/back-office-tools/danmarks-nationalbank-currency-exchange-rates/)
>
> ---


# Danmarks Nationalbank - tipos de cambio de divisas

## 1. Requisitos y Compatibilidad

- **Versiones de PrestaShop Soportadas**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilidad PHP**: PHP 5.6 - 8.5
- **Requisitos de Alojamiento**: Las extensiones PHP estándar (cURL, JSON, OpenSSL) suelen ser necesarias para obtener datos externos. Estas casi siempre están disponibles en entornos de alojamiento modernos.

## 2. Recorrido Completo por la Configuración (Cada Ajuste Agrupado por Pantalla)

### 2.1 Página de Configuración del Módulo (Back Office > Módulos > Configurar)

Después de la instalación, haga clic en "Configurar" junto al nombre del módulo para acceder a sus ajustes. Aquí es donde gestionará cómo se obtienen y aplican los tipos de cambio.

La página de configuración mostrará una lista de todas las monedas activas en su tienda, permitiéndole gestionar el tipo de cambio y el margen de beneficio para cada una.

**Para cada moneda listada (por ejemplo, USD, EUR, GBP):**

-   **Tipo de Cambio Actual:**

    -   **Qué hace esta configuración:** Este campo muestra el tipo de cambio actual para esta moneda con respecto a la moneda predeterminada de su tienda (por ejemplo, DKK si su tienda está basada en Dinamarca). Este valor es actualizado automáticamente por el módulo cuando se ejecuta la tarea cron.
    -   **Efecto de cambiar esta configuración:** Puede ajustarlo manualmente si es necesario, pero el propósito principal del módulo es automatizar esto. Cualquier cambio manual será sobrescrito por la próxima ejecución de la tarea cron.
    -   **Valor recomendado:** Deje que el módulo lo actualice automáticamente. Solo ajústelo manualmente para necesidades temporales y específicas.
    -   **Escenario / ejemplo de comerciante:** Si el módulo aún no se ha ejecutado, o si necesita ajustar rápidamente una tasa antes de la próxima actualización programada, podría cambiarlo manualmente. Sin embargo, para una precisión a largo plazo, confíe en las actualizaciones automáticas.
-   **Margen de Beneficio / Descuento (%):**

    -   **Qué hace esta configuración:** Esto le permite añadir un margen de beneficio (margen de beneficio) o descuento (descuento) basado en un porcentaje al tipo de cambio obtenido.
        -   Un valor positivo (por ejemplo, `+2%`) aumentará el tipo de cambio, lo que significa que los clientes pagan un poco más en esa moneda, asegurando que cubra las tarifas de conversión u obtenga una pequeña ganancia.
        -   Un valor negativo (por ejemplo, `-1%`) disminuirá el tipo de cambio, haciendo que el precio en moneda extranjera sea ligeramente inferior.
    -   **Efecto de cambiar esta configuración:** Este porcentaje se aplica *después* de que se obtiene la tasa oficial del Danmarks Nationalbank.
        -   *Cuando se establece en `+2%` para USD:* Si la tasa oficial es 1 USD = 6.50 DKK, su tienda utilizará 1 USD = 6.63 DKK (6.50 \* 1.02).
        -   *Cuando se establece en `-1%` para EUR:* Si la tasa oficial es 1 EUR = 7.45 DKK, su tienda utilizará 1 EUR = 7.3755 DKK (7.45 \* 0.99).
    -   **Valor recomendado:** Comience con `0%` y ajuste según su modelo de negocio, las tarifas de la pasarela de pago y los márgenes de beneficio deseados. Muchos comerciantes añaden un pequeño margen de beneficio (por ejemplo, `0.5%` a `2%`) para cubrir los costos de transacción.
    -   **Escenario / ejemplo de comerciante:** Su procesador de pagos cobra una tarifa del 1.5% por convertir EUR a DKK. Puede establecer un margen de beneficio de `+1.5%` para EUR para trasladar efectivamente este costo al cliente y mantener su margen de beneficio.

**URL de la Tarea Cron:**

-   **Qué hace esta configuración:** Muestra una URL única que debe configurar como una tarea cron en su servidor. Cuando se accede a esta URL, el módulo se conecta al Danmarks Nationalbank, obtiene los últimos tipos de cambio, aplica sus márgenes de beneficio/descuentos definidos y los actualiza en su tienda PrestaShop.
-   **Efecto de cambiar esta configuración:** No puede cambiar esta URL directamente. Es generada por el módulo.
-   **Valor recomendado:** Copie esta URL y configúrela en el panel de control de su alojamiento (cPanel, Plesk, etc.) o con un servicio cron.
-   **Escenario / ejemplo de comerciante:** Desea que sus tipos de cambio se actualicen diariamente a las 3 AM. Copiaría esta URL y configuraría una tarea cron en su servidor para ejecutarla todos los días a las 3 AM.

**Botón Guardar:**

-   **Qué hace esta configuración:** Aplica cualquier cambio que haya realizado en los porcentajes de Margen de Beneficio/Descuento.
-   **Efecto de cambiar esta configuración:** Sus nuevos márgenes de beneficio se guardarán y aplicarán la próxima vez que se ejecute la tarea cron y se actualicen las tasas.

### 2.2 Tabla de Referencia Rápida de Configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| Página de Configuración del Módulo | **Tipo de Cambio Actual** (por moneda) | Actualizado automáticamente por cron | Muestra la tasa actual; los cambios manuales son temporales. |
| Página de Configuración del Módulo | **Margen de Beneficio / Descuento (%)** (por moneda) | `0%` (ajustar según sea necesario) | Añade un porcentaje a la tasa obtenida para gestionar los márgenes de beneficio o cubrir tarifas. |
| Página de Configuración del Módulo | **URL de la Tarea Cron** | URL única (copiar y configurar) | La URL para activar las actualizaciones automáticas de tasas del Danmarks Nationalbank. |
| Página de Configuración del Módulo | **Botón Guardar** | N/A | Guarda sus porcentajes personalizados de Margen de Beneficio/Descuento. |

## 3. Solución de Problemas para Comerciantes y Preguntas Frecuentes (FAQ)

**P: Mis tipos de cambio no se están actualizando. ¿Qué debo hacer?**
R:

1.  **Verificar Tarea Cron:** La razón más común es una tarea cron configurada incorrectamente o que no se está ejecutando. Verifique con su proveedor de alojamiento que la URL de la tarea cron proporcionada en la configuración del módulo esté correctamente programada y ejecutándose.
2.  **Estado del Módulo:** Asegúrese de que el módulo esté habilitado en su Back Office de PrestaShop.
3.  **Conectividad del Servidor:** Confirme que su servidor tiene acceso a Internet saliente para conectarse a la API del Danmarks Nationalbank.
4.  **Borrar Caché:** A veces, la caché de PrestaShop puede impedir la visualización inmediata de las tasas actualizadas. Vaya a **Parámetros Avanzados > Rendimiento** y haga clic en "Borrar caché".

**P: ¿Puedo establecer diferentes márgenes de beneficio para diferentes monedas?**
R: ¡Sí, absolutamente! Esa es una de las características principales de este módulo. En la página de configuración del módulo, encontrará un campo separado de "Margen de Beneficio / Descuento (%)" para cada moneda activa en su tienda.

**P: ¿Qué sucede si el servicio del Danmarks Nationalbank no está disponible temporalmente?**
R: El módulo intentará obtener las tasas. Si falla, normalmente conservará las últimas tasas actualizadas con éxito. Está diseñado para ser resistente, pero los fallos consistentes podrían indicar un problema de conectividad del servidor por su parte o una interrupción prolongada de la fuente.

**P: ¿Este módulo afectará mi SEO o las URL de mis productos?**
R: No, este módulo solo gestiona los tipos de cambio de divisas. No altera las URL de los productos, las meta descripciones ni ningún otro elemento relacionado con el SEO. Su impacto es puramente en la visualización de precios.

**P: Mi tema personalizado no parece mostrar los precios actualizados correctamente.**
R: Este módulo actualiza los tipos de cambio centrales de PrestaShop. Si su tema utiliza funciones estándar de PrestaShop para mostrar precios, debería reflejar los cambios. Si no, podría ser un problema de caché (borre la caché como se indicó anteriormente) o un tema altamente personalizado que omite la representación estándar de precios de PrestaShop. En casos tan raros, es posible que necesite un desarrollador web para investigar la lógica de visualización de precios de su tema.

## 4. Guía para Desarrolladores y Webmasters (Arquitectura Técnica y Mapa de Código)

Esta sección proporciona una descripción técnica detallada para desarrolladores y webmasters que trabajan con el módulo "Danmarks Nationalbank - tipos de cambio de divisas".

### 4.1 Resumen de la Arquitectura

El módulo sigue una arquitectura de módulo estándar de PrestaShop, utilizando principalmente un enfoque basado en cron para actualizar los tipos de cambio de divisas. Se engancha al sistema de configuración de PrestaShop para los ajustes y aprovecha los controladores frontales para la ejecución de cron. La lógica central reside en el archivo principal del módulo, manejando las llamadas a la API del Danmarks Nationalbank y actualizando las entradas de la tabla `ps_currency`.

### 4.2 Controladores (`controllers/`)

-   **Controladores de Front-Office**:

    -   `dnbrates/controllers/front/cronjob.php`
        -   **Nombre de la clase y clase padre**: `DnbratesCronjobModuleFrontController` que extiende `ModuleFrontController`.
        -   **Responsabilidad**: Este controlador es el punto de entrada para la tarea cron. Cuando se accede a través de la URL única proporcionada en la configuración de back-office del módulo, activa el proceso de actualización de la tasa. Está diseñado para ser llamado externamente por un programador cron del lado del servidor. Maneja la lógica para obtener datos del Danmarks Nationalbank y actualizar la tabla `ps_currency`.
    -   `dnbrates/controllers/front/index.php`
        -   **Nombre de la clase y clase padre**: `DnbratesIndexModuleFrontController` que extiende `ModuleFrontController`.
        -   **Responsabilidad**: Este es un controlador de marcador de posición, a menudo incluido en módulos pero no utilizado activamente para una visualización específica de front-office en el contexto de este módulo. Podría servir como punto de entrada predeterminado o para futuras expansiones.
-   **Controladores de Administración de Back-Office**: Ninguno. Toda la configuración de back-office se maneja directamente dentro del método `getContent()` del archivo principal del módulo.

### 4.3 Clases y Modelos Principales (`classes/`)

No se encuentran clases personalizadas ni definiciones de `ObjectModel` en el directorio `classes/`. El módulo interactúa directamente con la clase `Currency` y la clase `Configuration` de PrestaShop para gestionar los tipos de cambio y los ajustes.

### 4.4 Activos JavaScript (`views/js/`)

No se encuentran archivos JavaScript personalizados en el archivo del módulo.

### 4.5 Hojas de Estilo CSS (`views/css/`)

No se encuentran archivos CSS personalizados en el archivo del módulo.

### 4.6 Estructura de Plantillas Smarty (`views/templates/`)

-   **Plantillas de administración (`views/templates/admin/`)**:
    -   `dnbrates/views/admin.tpl`
        -   **Propósito**: Esta plantilla renderiza el formulario de configuración del módulo en el Back Office de PrestaShop. Muestra la lista de monedas, sus tipos de cambio actuales, los campos de entrada para los porcentajes de margen de beneficio/descuento y la URL de la tarea cron. Se renderiza mediante el método `getContent()` del archivo principal del módulo.

### 4.7 Esquema de Base de Datos y Mapa de Ganchos

-   **Tablas de Base de Datos**:

    -   El módulo no crea ninguna tabla SQL personalizada.
    -   Interactúa principalmente con la tabla `ps_currency` (específicamente la columna `conversion_rate`) para actualizar los tipos de cambio.
    -   Los ajustes específicos del módulo (como los porcentajes de margen de beneficio/descuento para cada moneda y la URL de cron) se almacenan en la tabla `ps_configuration` utilizando claves típicamente prefijadas con `DNBRATES_`.
-   **Tabla de Ganchos Registrados**:

| Nombre del Gancho | Momento de Ejecución | Propósito Técnico |
| --- | --- | --- |
| `displayHeader` | Renderiza contenido en la sección `<head>` de las páginas del front-office. | No se utiliza directamente para la salida de contenido, pero los módulos a menudo se registran aquí para cargar activos o inicialización. |
| `displayLeftColumn` | Renderiza contenido en la columna izquierda de las páginas del front-office. | No se utiliza directamente para la salida de contenido por este módulo. |
| `displayRightColumn` | Renderiza contenido en la columna derecha de las páginas del front-office. | No se utiliza directamente para la salida de contenido por este módulo. |
| `displayFooter` | Renderiza contenido en el pie de página de las páginas del front-office. | No se utiliza directamente para la salida de contenido por este módulo. |
| `displayProductAdditionalInfo` | Renderiza contenido en la página del producto, típicamente debajo de la información principal del producto. | No se utiliza directamente para la salida de contenido por este módulo. |
| `actionUpdateCurrency` | Se ejecuta después de que se actualizan los detalles de una moneda. | El módulo probablemente utiliza este o un gancho similar internamente para asegurar que su lógica se aplique cuando cambian los datos de la moneda. |
| `actionAdminControllerSetMedia` | Se ejecuta cuando un controlador de administración está configurando sus medios (JS/CSS). | Podría usarse para cargar activos específicos para la página de configuración del módulo, aunque no hay archivos JS/CSS personalizados presentes. |

*Nota: La función principal del módulo (actualizar tasas) se activa mediante el controlador frontal a través de cron, no mediante un gancho estándar de PrestaShop dentro del ciclo de vida de la solicitud.*

## 5. Soporte Oficial y Actualizaciones

Para las últimas actualizaciones, correcciones de errores y soporte oficial para el módulo "Danmarks Nationalbank - tipos de cambio de divisas", consulte su cuenta de cliente en [MyPresta.eu](https://mypresta.eu/). Nuestro equipo de soporte está disponible para ayudar con cualquier problema o pregunta que pueda tener con respecto a la funcionalidad e integración del módulo.
