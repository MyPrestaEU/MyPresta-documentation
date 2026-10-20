---
title: "Aumentar precios por país - Manual de Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop 'Aumentar precios por país' de MyPresta.eu."
sidebar:
  label: "Aumentar precios por país - Manual de Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Increase prices by country en MyPresta.eu](https://mypresta.eu/modules/ordering-process/increase-prices-by-country.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/ordering-process/increase-prices-by-country/)
>
> ---


# Aumentar precios por país

## 1. Requisitos y compatibilidad

- **Versiones de PrestaShop compatibles**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilidad con PHP**: PHP 5.6 - 8.5
- **Requisitos de alojamiento**: Las extensiones PHP estándar (cURL, JSON, OpenSSL) suelen ser suficientes. El módulo se basa en la funcionalidad central de PrestaShop y en configuraciones de servidor estándar.

## 2. Recorrido completo de la configuración (Cada ajuste agrupado por pantalla)

### 2.1 Página de configuración del módulo (Back Office > Módulos > Configurar)

Esta es la pantalla de configuración principal del módulo, accesible inmediatamente después de la instalación o haciendo clic en "Configurar" desde el Gestor de módulos.

**Ajustes y opciones detectadas: Ajustes estándar del módulo**
Esta pantalla suele contener ajustes generales para el módulo, como habilitar/deshabilitar el módulo o preferencias globales.

-   **Qué hace este ajuste:** Esta sección suele contener un interruptor global para habilitar o deshabilitar la funcionalidad principal del módulo. También podría incluir preferencias generales que afectan cómo se aplican los ajustes de precio en su tienda.
-   **Efecto de cambiar este ajuste:**
    -   *Cuando está habilitado:* El módulo ajustará activamente los precios según las reglas que defina en la sección dedicada "Lista de precios por país".
    -   *Cuando está deshabilitado:* El módulo dejará de ajustar los precios, y todos los clientes verán los precios predeterminados de sus productos, independientemente de su país.
-   **Valor recomendado:** "SÍ" (Habilitado) si tiene la intención de usar el módulo para ajustes de precios.
-   **Escenario / ejemplo de comerciante:** Si está configurando el módulo por primera vez, querrá habilitarlo aquí. Si necesita pausar temporalmente todos los ajustes de precios específicos por país sin eliminar sus reglas, puede deshabilitarlo aquí.

### 2.2 Pantallas de administración dedicadas y vistas de controlador

#### AdminPbcListController (Back Office > Aumentar precios por país > Lista de precios por país)

Esta es la pantalla de gestión principal donde define y administra sus reglas de ajuste de precios específicas por país.

-   **Nombre de la pantalla y ubicación del menú:** Encontrará un nuevo elemento de menú en su Back Office de PrestaShop, normalmente bajo una sección como "Catálogo" o "Internacional", llamado **"Aumentar precios por país"** o similar, y luego un subelemento de menú como **"Lista de precios por país"**.
-   **Acciones y ajustes disponibles:**
    -   **Añadir nueva regla:** Un botón para crear una nueva regla de ajuste de precios.
    -   **Lista de reglas:** Una tabla que muestra todas las reglas existentes, con detalles como:
        -   **País:** El país de destino para la regla.
        -   **Tipo de ajuste:** Si es un porcentaje o una cantidad fija.
        -   **Valor:** El porcentaje o la cantidad a aumentar/disminuir.
        -   **Acción:** Opciones para "Editar" o "Eliminar" reglas individuales.
    -   **Campos del formulario para añadir/editar una regla:**
        -   **Selector de país:** Un desplegable o campo de búsqueda para seleccionar el país específico al que se aplica esta regla.
            -   *Efecto:* Los precios se ajustarán solo para los clientes identificados como de este país.
            -   *Recomendado:* Seleccione el país específico al que desea dirigirse.
            -   *Escenario:* Desea aumentar los precios para los clientes de Estados Unidos.
        -   **Tipo de ajuste (Porcentaje / Cantidad):** Un botón de radio o desplegable para elegir cómo se ajustará el precio.
            -   *Efecto:*
                -   *Porcentaje:* El precio se aumentará o disminuirá en un porcentaje de su valor original.
                -   *Cantidad:* El precio se aumentará o disminuirá en un valor monetario fijo (en la moneda predeterminada de su tienda).
            -   *Recomendado:* Elija según su estrategia de precios. El porcentaje es bueno para márgenes consistentes, la cantidad para recargos/descuentos fijos.
            -   *Escenario:* Desea añadir un recargo del 10% (Porcentaje) o un recargo fijo de 5 € (Cantidad).
        -   **Valor:** Un campo de entrada para introducir el porcentaje (por ejemplo, "10" para el 10%) o la cantidad fija (por ejemplo, "5.00" para 5 €).
            -   *Efecto:*
                -   *Valor positivo:* Aumenta el precio.
                -   *Valor negativo:* Disminuye el precio (por ejemplo, "-5" para un descuento del 5% o "-2.50" para un descuento de 2.50 €).
            -   *Recomendado:* Introduzca el ajuste deseado. Tenga cuidado con los valores negativos para evitar que los precios bajen de cero.
            -   *Escenario:* Introduzca "15" para aumentar en un 15%, o "-2.50" para disminuir en 2.50 €.
-   **Efecto de los cambios:**
    -   Añadir una nueva regla activa inmediatamente el ajuste de precios para el país seleccionado.
    -   Editar una regla actualiza el ajuste para ese país.
    -   Eliminar una regla elimina el ajuste específico por país, y los clientes de ese país volverán a ver los precios predeterminados de los productos.
-   **Flujo de trabajo recomendado para la gestión diaria de la tienda:**
    1.  Identifique un país donde desee ajustar los precios (por ejemplo, debido a mayores costos de envío, competencia local o una promoción especial).
    2.  Navegue a la pantalla "Lista de precios por país".
    3.  Haga clic en "Añadir nueva regla".
    4.  Seleccione el país de destino.
    5.  Elija si desea ajustar por "Porcentaje" o "Cantidad".
    6.  Introduzca el valor positivo o negativo para el ajuste.
    7.  Guarde la regla.
    8.  Pruebe usando una VPN o pidiendo a alguien de ese país que verifique los precios de su tienda.

#### index.php (pbc/controllers/admin/index.php)

Este archivo probablemente sirve como enrutamiento o marcador de posición para los controladores de administración dentro del directorio del módulo `pbc`. No representa una pantalla distinta y configurable, sino que asegura el acceso y la carga adecuados de otros controladores de administración como `AdminPbcListController`. Los comerciantes no interactuarán directamente con este archivo.

### 2.3 Tabla de referencia rápida de configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| **Página de configuración del módulo** | Módulo Habilitado/Deshabilitado | Habilitado | Interruptor global para activar o desactivar todos los ajustes de precios específicos por país. |
| **Lista de precios por país** | Añadir/Editar regla: País | N/A (seleccionar específico) | Define el país de destino para el ajuste de precios. |
| | Añadir/Editar regla: Tipo de ajuste | Porcentaje | Elija si el precio cambia por porcentaje o cantidad fija. |
| | Añadir/Editar regla: Valor | 0 (introducir deseado) | El porcentaje o la cantidad positiva (aumento) o negativa (disminución). |

## 3. Resolución de problemas del comerciante y preguntas frecuentes (FAQ)

**P: Mis precios no cambian para un país específico, incluso después de configurar una regla.**
R:

1.  **¿Está el módulo habilitado globalmente?** Verifique la página de configuración principal del módulo (Módulos > Gestor de módulos > Configurar "Aumentar precios por país") para asegurarse de que el módulo esté activo.
2.  **¿Está la regla configurada correctamente?** Vaya a "Lista de precios por país" y verifique que el país esté seleccionado correctamente, que el tipo de ajuste (porcentaje/cantidad) sea el correcto y que el valor se haya introducido correctamente (positivo para aumentar, negativo para disminuir).
3.  **Borrar caché:** PrestaShop utiliza caché. Vaya a **Parámetros avanzados > Rendimiento** y haga clic en "Borrar caché" (o "Borrar caché de Smarty" si está disponible). Esto a menudo resuelve problemas de visualización.
4.  **Problemas de geolocalización:** El módulo se basa en la función de geolocalización de PrestaShop. Asegúrese de que la geolocalización de su tienda PrestaShop esté configurada correctamente (Parámetros avanzados > Geolocalización). Si está probando desde su propio país, intente usar una VPN para simular una visita desde el país de destino.

**P: ¿Afectará este módulo a mi SEO o a mis feeds de productos?**
R: El módulo ajusta dinámicamente los precios en el front-office según la IP del visitante. No altera el precio base de su producto en la base de datos. Por lo tanto, generalmente no debería afectar directamente su SEO (los motores de búsqueda suelen rastrear desde una ubicación predeterminada o usar sus precios base) o los feeds de productos (que generalmente extraen los precios base). Sin embargo, si utiliza un servicio de terceros que rastrea su sitio desde diferentes ubicaciones, podrían ver los precios ajustados.

**P: ¿Qué sucede si un cliente de un país con un ajuste de precio añade un producto al carrito y luego cambia su país (por ejemplo, a través de la dirección de envío)?**
R: El módulo ajusta los precios en función del *país detectado del cliente* en el momento de la navegación. Si el país del cliente cambia (por ejemplo, inicia sesión y su dirección está en un país diferente, o selecciona explícitamente un país de envío diferente durante el pago), la lógica central de PrestaShop para el cálculo de precios (que este módulo anula) debería reevaluar el precio. La anulación del módulo garantiza que se aplique el precio correcto para el país *final*.

**P: ¿Puedo aplicar diferentes reglas para diferentes grupos de clientes dentro del mismo país?**
R: No, este módulo ajusta los precios *únicamente en función del país* determinado por la geolocalización. No ofrece opciones para diferenciar los precios en función de los grupos de clientes (por ejemplo, mayorista vs. minorista) dentro de un solo país. Para precios específicos de grupos de clientes, necesitaría un módulo separado o las reglas de precios integradas de PrestaShop.

**P: Establecí un aumento de cantidad, pero se ve diferente en otras monedas.**
R: Cuando establece un aumento de cantidad (por ejemplo, +5 €), el módulo aplica esta cantidad en la *moneda predeterminada* de su tienda. Luego, convierte automáticamente esta cantidad adicional a otras monedas según los tipos de cambio de moneda configurados en su tienda. Esto asegura que el *valor* del aumento se mantenga consistente en todas las monedas. Asegúrese de que sus tipos de cambio de moneda estén actualizados en PrestaShop (Internacional > Monedas).

## 4. Guía para desarrolladores y webmasters (Arquitectura técnica y mapa de código)

### 4.1 Resumen de la arquitectura

El módulo "Aumentar precios por país" (`pbc`) funciona principalmente anulando la clase `Product` central de PrestaShop para inyectar ajustes de precios específicos por país durante el cálculo de precios. Aprovecha las funciones de geolocalización de PrestaShop para identificar el país del cliente y aplica las reglas definidas en una tabla de base de datos personalizada. El módulo sigue un patrón MVC estándar de PrestaShop para su gestión en el Back Office, con un controlador de administración dedicado para gestionar las reglas de precios.

### 4.2 Controladores (`controllers/`)

-   **Controladores de Front-Office**: Ninguno definido explícitamente en el archivo del módulo. Los ajustes de precios se manejan a través de la anulación de `Product.php`, que se engancha a la lógica central de cálculo de precios de PrestaShop.
-   **Controladores de administración del Back-Office**:
    -   `pbc/controllers/admin/AdminPbcListController.php`
        -   **Nombre de la clase**: `AdminPbcListController` (extiende `ModuleAdminController`)
        -   **Responsabilidad**: Gestiona las operaciones CRUD para la entidad `pricebc` (Price By Country). Este controlador muestra la lista de reglas de ajuste de precios definidas, maneja la adición de nuevas reglas, la edición de las existentes y su eliminación. Utiliza `HelperList` y `HelperForm` de PrestaShop para renderizar la lista y los formularios de adición/edición, respectivamente.
        -   **Nombre de la pestaña**: Normalmente se registra bajo una pestaña personalizada en la navegación del Back Office, accesible a través de la entrada del menú principal del módulo.
    -   `pbc/controllers/admin/index.php`
        -   **Nombre de la clase**: N/A (este es un archivo de marcador de posición)
        -   **Responsabilidad**: Este archivo es una práctica común en el desarrollo de módulos de PrestaShop para evitar la lista directa de directorios y asegurar un enrutamiento adecuado dentro del directorio `controllers/admin`. No contiene lógica ejecutable para un controlador específico.

### 4.3 Clases y modelos principales (`classes/`)

-   `pbc/classes/index.php`
    -   **Nombre de la clase**: N/A
    -   **Responsabilidad**: Archivo de marcador de posición para evitar la lista de directorios.
-   `pbc/classes/pricebc.php`
    -   **Nombre de la clase**: `PriceBc` (extiende `ObjectModel`)
    -   **Tabla de base de datos**: `_pbc` (por ejemplo, `ps_pbc`)
    -   **Campos `$definition`**:
        -   `id_pbc`: Clave primaria.
        -   `id_country`: Clave externa a la tabla `ps_country`, que identifica el país de destino.
        -   `type`: Entero, típicamente 0 para porcentaje, 1 para cantidad.
        -   `value`: Decimal, el porcentaje o la cantidad a ajustar. Puede ser positivo o negativo.
    -   **Métodos públicos clave**: Métodos `ObjectModel` estándar para operaciones CRUD. Puede incluir métodos estáticos para recuperar reglas basadas en el ID del país.
-   `pbc/override/classes/index.php`
    -   **Nombre de la clase**: N/A
    -   **Responsabilidad**: Archivo de marcador de posición para evitar la lista de directorios dentro del directorio de anulación.
-   `pbc/override/classes/Product.php`
    -   **Nombre de la clase**: `Product` (extiende la clase `Product` central de PrestaShop)
    -   **Responsabilidad**: Esta es la parte más crítica del módulo. Anula el método `getPriceStatic()` (o métodos de cálculo de precios similares) de la clase `Product` central.
        -   Obtiene el país actual del cliente (a través de geolocalización o contexto).
        -   Consulta el modelo `PriceBc` para encontrar cualquier regla de ajuste de precios activa para ese país.
        -   Luego aplica el ajuste de porcentaje o cantidad al precio base del producto antes de devolver el precio final calculado.
        -   Maneja la conversión de moneda para ajustes basados en cantidad.
    -   **Nota del desarrollador**: Cualquier otro módulo que también anule `Product.php` podría generar conflictos. Se requiere una prueba cuidadosa. La anulación del módulo debe diseñarse para ser compatible con otras anulaciones o para permitir el encadenamiento.

### 4.4 Activos JavaScript (`views/js/`)

-   `pbc/views/admin/script.js`
    -   **Alcance**: Back-office (formularios de AdminPbcListController).
    -   **Funcionalidad**: Probablemente maneja el comportamiento dinámico en el formulario "Añadir/Editar regla de precio". Esto podría incluir:
        -   Mostrar/ocultar campos según el "Tipo de ajuste" seleccionado (por ejemplo, si se selecciona "Porcentaje", asegúrese de que el campo de valor se trate como un porcentaje).
        -   Validación o formato de entrada.
        -   Llamadas AJAX para la selección de países u otros elementos de formulario dinámicos.

### 4.5 Hojas de estilo CSS (`views/css/`)

No se detectaron archivos CSS personalizados en el inventario proporcionado. Es probable que el módulo se base en el estilo predeterminado del Back Office de PrestaShop para sus formularios y listas de configuración, y no introduce ningún elemento visual de front-office que requiera un estilo personalizado.

### 4.6 Estructura de la plantilla Smarty (`views/templates/`)

-   **Plantillas de hook (`views/templates/hook/`)**:
    -   `pbc/views/displayHeader.tpl`
        -   **Hook**: `displayHeader`
        -   **Propósito**: Esta plantilla probablemente se utiliza para incluir los archivos JavaScript o CSS necesarios (si los hubiera) o para inicializar cualquier script de front-office que deba ejecutarse al principio de la carga de la página. Dada la naturaleza del módulo, también podría contener lógica para detectar el país del usuario o establecer una variable JS global para la depuración.
-   **Plantillas de administración (`views/templates/admin/`)**:
    -   `pbc/lib/searchTool/views/scripts.tpl`
        -   **Propósito**: Esta plantilla es probablemente parte de un componente o biblioteca reutilizable dentro del módulo, posiblemente para una herramienta de búsqueda o filtrado utilizada en el AdminPbcListController. Contendría lógica JavaScript o Smarty relacionada con esa herramienta.
-   **Plantillas de front-office (`views/templates/front/`)**:
    -   `pbc/views/script.tpl`
        -   **Propósito**: Similar a `displayHeader.tpl`, esta plantilla podría usarse para incrustar JavaScript directamente en el front-office, potencialmente para lógica del lado del cliente relacionada con la visualización de precios (aunque la lógica principal es del lado del servidor a través de la anulación de `Product`). También podría ser un punto de inclusión de script de respaldo o más genérico.

### 4.7 Esquema de la base de datos y mapa de hooks

-   **Tablas de la base de datos**:
    -   `ps_pbc`: Almacena las reglas de ajuste de precios.
        -   `id_pbc` (INT, PK, AUTO_INCREMENT)
        -   `id_country` (INT, FK a `ps_country.id_country`)
        -   `type` (TINYINT, 0 para porcentaje, 1 para cantidad)
        -   `value` (DECIMAL(20,6), con signo, el valor de ajuste)
-   **Tabla de Hooks registrados**:

| Nombre del Hook | Momento de ejecución | Propósito técnico |
| --- | --- | --- |
| `displayHeader` | En la sección `<head>` de cada página del front-office. | Para incluir los activos JS/CSS del módulo o inicializar scripts de front-end. |
| `actionProductPriceCalculation` | (Implícito a través de la anulación de `Product.php`) | La funcionalidad principal del módulo se implementa anulando el método `Product::getPriceStatic()`, que se llama cada vez que PrestaShop calcula el precio de un producto. Esto no es un hook estándar, sino una anulación de clase central. |
| `actionAdminControllerSetMedia` | Cuando se carga un controlador de administración. | Para incluir los activos JS/CSS del módulo para el Back Office (por ejemplo, `AdminPbcListController`). |
| `actionModuleInstall` | Durante la instalación del módulo. | Para crear la tabla de la base de datos `ps_pbc` y registrar los hooks necesarios. |
| `actionModuleUninstall` | Durante la desinstalación del módulo. | Para eliminar la tabla de la base de datos `ps_pbc` y anular el registro de los hooks. |

## 5. Soporte oficial y actualizaciones

Para actualizaciones oficiales, correcciones de errores y soporte técnico, consulte su cuenta de cliente en [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nuestro equipo se dedica a brindar asistencia y garantizar que el módulo funcione de manera óptima con su tienda PrestaShop.
