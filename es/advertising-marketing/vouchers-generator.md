---
title: "Generador de Vales - Manual del Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo Generador de Vales de PrestaShop por MyPresta.eu."
sidebar:
  label: "Generador de Vales - Manual del Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Vouchers Generator en MyPresta.eu](https://mypresta.eu/modules/advertising-and-marketing/vouchers-generator.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/advertising-marketing/vouchers-generator/)
>
> ---


# Generador de Vales

## 1. Requisitos y Compatibilidad

- **Versiones de PrestaShop Compatibles**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilidad con PHP**: PHP 5.6 - 8.5
- **Requisitos de Alojamiento**: Las extensiones PHP estándar (cURL, JSON, OpenSSL) suelen ser suficientes. No se requieren configuraciones de servidor inusuales.

## 2. Recorrido Completo por la Configuración (Cada Ajuste Agrupado por Pantalla)

### 2.1 Página de Configuración del Módulo (Back Office > Módulos > Configurar)

Después de instalar el módulo, navega a **Módulos > Gestor de Módulos** y haz clic en "Configurar" junto a "Generador de Vales". Esta es la pantalla principal donde gestionarás todos los ajustes y generarás tus vales.

La página de configuración está diseñada para ser intuitiva, permitiéndote definir las reglas para tus nuevos vales y luego generarlos.

#### **1. Ajustes de Generación de Vales**

Esta sección te permite definir las propiedades principales de los vales que deseas generar.

-   **Nombre:**

    -   **Qué hace este ajuste:** Este es el nombre que aparecerá en tu Back Office de PrestaShop en "Catálogo > Descuentos > Reglas de carrito" para el lote de vales generado. También es el nombre base para los códigos de vale individuales (por ejemplo, si estableces "VERANO2024", los códigos podrían ser "VERANO2024-ABCDE", "VERANO2024-FGHIJ").
    -   **Efecto de cambiar este ajuste:** Un nombre claro y descriptivo te ayuda a identificar el propósito del lote de vales más tarde.
    -   **Valor recomendado:** Algo descriptivo como "Oferta de Verano 2024", "Bienvenida Nuevo Cliente" o "Recuperación de Carrito Abandonado".
    -   **Escenario / ejemplo de comerciante:** Estás ejecutando una promoción de verano. Podrías nombrarla "VERANO2024".
-   **Descripción:**

    -   **Qué hace este ajuste:** Una nota interna para tu referencia, visible solo en el Back Office. Te ayuda a recordar los detalles específicos o los objetivos de esta campaña de vales.
    -   **Efecto de cambiar este ajuste:** Proporciona contexto para ti y tu equipo.
    -   **Valor recomendado:** Una breve explicación, por ejemplo, "20% de descuento en todos los pedidos superiores a 50€, válido por 1 mes, distribuido a través de boletín de correo electrónico."
    -   **Escenario / ejemplo de comerciante:** Para la campaña "VERANO2024", podrías añadir "20% de descuento en todos los productos, compra mínima de 50€, válido hasta el 31 de agosto."
-   **Resaltar:**

    -   **Qué hace este ajuste:** Si está habilitado, este vale se mostrará en el resumen del carrito para todos los clientes, incluso si no lo han introducido. Esto se usa típicamente para promociones generales y públicas.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando está habilitado:* El vale aparece automáticamente en el resumen del carrito, animando a los clientes a usarlo.
        -   *Cuando está deshabilitado:* El vale solo se aplica si el cliente introduce explícitamente el código.
    -   **Valor recomendado:** "NO" para vales únicos y dirigidos; "SÍ" para promociones públicas en toda la tienda.
    -   **Escenario / ejemplo de comerciante:** Si estás dando códigos únicos a clientes específicos, deshabilita esto. Si es una promoción general de "10% de descuento en todo", habilítalo.
-   **Uso parcial:**

    -   **Qué hace este ajuste:** Determina si un vale puede usarse varias veces si su valor excede el total del pedido.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando está habilitado:* Si un cliente tiene un vale de 50€ y compra un artículo de 30€, tendrá un saldo restante de 20€ en ese mismo vale para una futura compra.
        -   *Cuando está deshabilitado:* Si un cliente tiene un vale de 50€ y compra un artículo de 30€, el vale completo de 50€ se consume y no queda saldo.
    -   **Valor recomendado:** "NO" para la mayoría de las promociones para fomentar el uso completo o evitar un seguimiento complejo. "SÍ" para tarjetas de regalo o crédito de tienda.
    -   **Escenario / ejemplo de comerciante:** Para un descuento estándar, normalmente deshabilitarías esto. Para un vale de regalo, lo habilitarías.
-   **Prioridad:**

    -   **Qué hace este ajuste:** Establece el orden en que se aplican las reglas de carrito si hay varias reglas activas. Un número más bajo significa mayor prioridad (se aplica primero).
    -   **Efecto de cambiar este ajuste:** Influye en cómo se acumulan los descuentos. Si se aplican dos vales, el de mayor prioridad se procesa primero.
    -   **Valor recomendado:** Déjalo en el valor predeterminado (1) a menos que tengas reglas de acumulación complejas.
    -   **Escenario / ejemplo de comerciante:** Si tienes un vale de "Envío Gratuito" (prioridad 1) y un vale de "10% de Descuento" (prioridad 2), el envío gratuito se calculará antes del descuento porcentual.
-   **Estado:**

    -   **Qué hace este ajuste:** Activa o desactiva los vales generados.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando está habilitado:* Los vales están activos y pueden ser utilizados por los clientes.
        -   *Cuando está deshabilitado:* Los vales están inactivos y no pueden ser utilizados.
    -   **Valor recomendado:** "SÍ" si quieres que los vales sean utilizables inmediatamente. Puedes deshabilitarlos más tarde si es necesario.
    -   **Escenario / ejemplo de comerciante:** Generas vales para una venta futura. Podrías habilitarlos el día en que comienza la venta.

#### **2. Condiciones del Vale**

Esta sección define cuándo y cómo se pueden usar los vales generados.

-   **Válido desde:**

    -   **Qué hace este ajuste:** Establece la fecha de inicio a partir de la cual los vales se activan.
    -   **Efecto de cambiar este ajuste:** Los vales no se pueden usar antes de esta fecha.
    -   **Valor recomendado:** La fecha actual si quieres que estén activos inmediatamente, o una fecha futura para una promoción planificada.
    -   **Escenario / ejemplo de comerciante:** Establece "2024-07-01" para una promoción de julio.
-   **Válido hasta:**

    -   **Qué hace este ajuste:** Establece la fecha de finalización después de la cual los vales caducan.
    -   **Efecto de cambiar este ajuste:** Los vales no se pueden usar después de esta fecha.
    -   **Valor recomendado:** Una fecha de caducidad razonable para tu promoción (por ejemplo, 1 semana, 1 mes, fin de temporada).
    -   **Escenario / ejemplo de comerciante:** Establece "2024-07-31" para una promoción de julio.
-   **Cantidad mínima:**

    -   **Qué hace este ajuste:** La cantidad total mínima de compra (antes del envío e impuestos) requerida para que el vale sea válido.
    -   **Efecto de cambiar este ajuste:** Si el total del carrito del cliente está por debajo de esta cantidad, el vale no se puede aplicar.
    -   **Valor recomendado:** Establece un valor que fomente valores de pedido promedio más altos, o 0 si no se requiere un mínimo.
    -   **Escenario / ejemplo de comerciante:** Establece "50.00" para ofrecer un descuento solo en pedidos superiores a 50€.
-   **Total disponible:**

    -   **Qué hace este ajuste:** El número total de veces que *todos* los vales generados en este lote pueden ser utilizados por *todos* los clientes.
    -   **Efecto de cambiar este ajuste:** Una vez que se alcanza este límite, no se pueden usar más vales de este lote, incluso si los códigos individuales aún tienen usos restantes.
    -   **Valor recomendado:** Un número alto (por ejemplo, 99999) si quieres que se apliquen los límites de códigos individuales, o un número específico para una campaña de uso total y limitado en el tiempo.
    -   **Escenario / ejemplo de comerciante:** Si generas 100 códigos únicos y estableces "Total disponible" en 50, solo los primeros 50 usos de todos los códigos serán válidos.
-   **Total disponible para cada usuario:**

    -   **Qué hace este ajuste:** El número máximo de veces que *cada cliente individual* puede usar *cualquiera* de los vales de este lote.
    -   **Efecto de cambiar este ajuste:** Evita que un solo cliente use repetidamente diferentes códigos del mismo lote.
    -   **Valor recomendado:** "1" para la mayoría de las campañas de vales únicos para asegurar que cada cliente obtenga un uso. "0" para usos ilimitados por cliente (no recomendado para códigos únicos).
    -   **Escenario / ejemplo de comerciante:** Establece "1" para asegurar que cada cliente solo pueda beneficiarse de uno de tus códigos generados.

#### **3. Acciones del Vale**

Esta sección define lo que realmente hace el vale cuando se aplica.

-   **Envío gratuito:**

    -   **Qué hace este ajuste:** Determina si el vale otorga envío gratuito.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando está habilitado:* Los costos de envío se eximen para los pedidos que usan este vale.
        -   *Cuando está deshabilitado:* Se aplican los costos de envío estándar.
    -   **Valor recomendado:** "NO" a menos que sea una promoción específica de envío gratuito.
    -   **Escenario / ejemplo de comerciante:** Para una promoción de "Fin de Semana de Envío Gratuito", habilitarías esto.
-   **Aplicar un descuento:**

    -   **Qué hace este ajuste:** Aquí es donde defines la cantidad o el porcentaje de descuento real.
    -   **Efecto de cambiar este ajuste:** Determina el valor monetario del descuento.
    -   **Valor recomendado:** Elige un tipo de descuento (porcentaje, cantidad o producto específico) y rellena los detalles.
    -   **Escenario / ejemplo de comerciante:** Quieres ofrecer un 15% de descuento.
    -   **Porcentaje:**

        -   **Qué hace este ajuste:** Aplica un descuento porcentual al total del pedido.
        -   **Efecto de cambiar este ajuste:** Reduce el total del pedido en el porcentaje especificado.
        -   **Valor recomendado:** Un porcentaje común como 5, 10, 15, 20.
        -   **Escenario / ejemplo de comerciante:** Introduce "15" para un 15% de descuento.
    -   **Cantidad:**

        -   **Qué hace este ajuste:** Aplica un descuento monetario fijo al total del pedido.
        -   **Efecto de cambiar este ajuste:** Reduce el total del pedido en la cantidad especificada.
        -   **Valor recomendado:** Una cantidad fija como 5.00, 10.00, 25.00.
        -   **Escenario / ejemplo de comerciante:** Introduce "10.00" para 10€ de descuento.
    -   **Aplicar descuento a:**

        -   **Qué hace este ajuste:** Especifica a qué parte del pedido se aplica el descuento.
        -   **Efecto de cambiar este ajuste:**
            -   *Pedido (sin incluir envío):* El descuento se aplica solo al total del producto.
            -   *Producto específico:* El descuento se aplica solo a un producto particular o selección de productos.
            -   *Producto más barato:* El descuento se aplica al artículo de menor precio en el carrito.
            -   *Productos seleccionados:* El descuento se aplica a una lista específica de productos que definas.
        -   **Valor recomendado:** "Pedido (sin incluir envío)" para descuentos generales.
        -   **Escenario / ejemplo de comerciante:** Para un 15% de descuento general, elige "Pedido (sin incluir envío)". Si quieres un 20% de descuento solo en "Camisetas", seleccionarías "Productos seleccionados" y luego elegirías la categoría/productos de Camisetas.
-   **Enviar un regalo:**

    -   **Qué hace este ajuste:** Te permite añadir automáticamente un producto específico como regalo gratuito cuando se usa el vale.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando está habilitado:* Un producto elegido se añade al carrito del cliente de forma gratuita.
        -   *Cuando está deshabilitado:* No se proporciona ningún regalo gratuito.
    -   **Valor recomendado:** "NO" a menos que sea una promoción específica de regalo con compra.
    -   **Escenario / ejemplo de comerciante:** Quieres dar un "Llavero" gratis con cada pedido superior a 100€. Habilitarías esto y seleccionarías el producto Llavero.

#### **4. Generación de Vales**

Este es el paso final donde defines cuántos códigos generar y luego ejecutas la generación.

-   **Número de vales a generar:**

    -   **Qué hace este ajuste:** Especifica cuántos códigos de vale únicos quieres que cree el módulo.
    -   **Efecto de cambiar este ajuste:** Determina la cantidad de códigos de descuento individuales que se añadirán a tus Reglas de Carrito de PrestaShop.
    -   **Valor recomendado:** El número exacto de códigos únicos que necesitas para tu campaña (por ejemplo, 100 para una lista de correo electrónico, 500 para un sorteo en redes sociales).
    -   **Escenario / ejemplo de comerciante:** Necesitas 250 códigos únicos para una campaña de marketing. Introduce "250".
-   **Botón Generar Vales:**

    -   **Qué hace este ajuste:** Este botón inicia el proceso de creación de todos los vales basándose en los ajustes que has configurado anteriormente.
    -   **Efecto de cambiar este ajuste:** Al hacer clic en este botón se creará el número especificado de reglas de carrito únicas en tu tienda PrestaShop. Aparecerá un mensaje de confirmación y podrás descargar un archivo CSV/Excel que contiene los códigos generados.
    -   **Valor recomendado:** Haz clic en esto solo después de estar absolutamente seguro de que todos tus ajustes son correctos.
    -   **Escenario / ejemplo de comerciante:** Después de revisar todos los ajustes para tu campaña "VERANO2024" y establecer el número de vales en 250, haces clic en "Generar Vales".

#### **5. Actualizaciones e Información de MyPresta.eu**

Esta sección suele contener información sobre la versión del módulo, la disponibilidad de actualizaciones y enlaces a MyPresta.eu.

-   **Actualizaciones de MyPresta.eu / Comprobación de Actualizaciones:**
    -   **Qué hace este ajuste:** Permite que el módulo compruebe si hay nuevas versiones disponibles en MyPresta.eu.
    -   **Efecto de cambiar este ajuste:** Te ayuda a mantener tu módulo actualizado con las últimas características y correcciones de errores.
    -   **Valor recomendado:** Mantén esto habilitado para recibir notificaciones sobre actualizaciones.
    -   **Escenario / ejemplo de comerciante:** Ves una notificación de que hay una nueva versión disponible, asegurándote de tener la versión más estable y con más funciones.

### 2.2 Tabla de Referencia Rápida de Configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| Configuración del Módulo | Nombre | Texto descriptivo | Nombre interno para el lote de vales. |
| Configuración del Módulo | Descripción | Texto opcional | Notas internas para detalles de la campaña. |
| Configuración del Módulo | Resaltar | NO | Mostrar vale en el resumen del carrito (SÍ para público, NO para privado). |
| Configuración del Módulo | Uso parcial | NO | Permitir que el vale se use varias veces si el valor > pedido. |
| Configuración del Módulo | Prioridad | 1 | Orden de aplicación para múltiples reglas de carrito (menor = mayor prioridad). |
| Configuración del Módulo | Estado | SÍ | Activar/desactivar los vales generados. |
| Configuración del Módulo | Válido desde | Fecha actual | Fecha de inicio de validez del vale. |
| Configuración del Módulo | Válido hasta | Fecha futura | Fecha de fin de validez del vale. |
| Configuración del Módulo | Cantidad mínima | 0.00 | Compra mínima requerida para el uso del vale. |
| Configuración del Módulo | Total disponible | Número alto (ej. 99999) | Usos totales para TODOS los vales de este lote. |
| Configuración del Módulo | Total disponible para cada usuario | 1 | Usos máximos por cliente para cualquier vale de este lote. |
| Configuración del Módulo | Envío gratuito | NO | Otorgar envío gratuito con el vale. |
| Configuración del Módulo | Aplicar un descuento | SÍ | Habilitar la aplicación de descuento. |
| Configuración del Módulo | Porcentaje | (ej. 10) | Descuento porcentual. |
| Configuración del Módulo | Cantidad | (ej. 10.00) | Descuento monetario fijo. |
| Configuración del Módulo | Aplicar descuento a | Pedido (sin incluir envío) | Alcance del descuento (pedido, producto específico, etc.). |
| Configuración del Módulo | Enviar un regalo | NO | Añadir un producto gratuito como regalo. |
| Configuración del Módulo | Número de vales a generar | (ej. 100) | Cantidad de códigos únicos a crear. |
| Configuración del Módulo | Botón Generar Vales | Clic cuando esté listo | Inicia la creación de vales y la exportación CSV. |
| Configuración del Módulo | Actualizaciones de MyPresta.eu | SÍ | Comprobar actualizaciones del módulo. |

## 3. Solución de Problemas del Comerciante y Preguntas Frecuentes (FAQ)

**P1: Generé vales, pero no parecen funcionar en el front office.**
R1:

-   **Verifica el Estado y las Fechas:** Ve a "Catálogo > Descuentos > Reglas de carrito" en tu Back Office de PrestaShop. Busca los vales que generaste. Asegúrate de que su "Estado" esté configurado en "Sí" y que las fechas "Válido desde" y "Válido hasta" sean actuales.
-   **Cantidad Mínima:** Verifica si el carrito del cliente cumple con el requisito de "Cantidad mínima" establecido para el vale.
-   **Condiciones:** Vuelve a verificar cualquier otra condición que hayas establecido (por ejemplo, productos específicos, grupos de clientes).
-   **Caché:** Borra la caché de tu PrestaShop (Parámetros Avanzados > Rendimiento > Borrar Caché).

**P2: ¿Puedo editar los vales generados después de haberlos creado?**
R2: Sí, una vez generados, cada vale se convierte en una "Regla de Carrito" estándar en PrestaShop. Puedes ir a "Catálogo > Descuentos > Reglas de carrito" en tu Back Office, buscar los vales individuales (normalmente compartirán el mismo nombre base que proporcionaste) y editar sus propiedades (por ejemplo, fecha de caducidad, cantidad de descuento, condiciones) individualmente. Sin embargo, generalmente es mejor configurar todos los ajustes correctamente antes de la generación.

**P3: ¿Cómo obtengo la lista de códigos de vale generados?**
R3: Inmediatamente después de hacer clic en el botón "Generar Vales", el módulo te pedirá que descargues un archivo CSV/Excel que contiene todos los códigos únicos. Si te perdiste esto, no puedes volver a descargar la lista directamente desde el módulo. Tendrías que exportar manualmente las "Reglas de Carrito" desde "Catálogo > Descuentos > Reglas de carrito" en PrestaShop, o acceder directamente a la base de datos (tarea de desarrollador). Es crucial guardar el archivo CSV inmediatamente después de la generación.

**P4: El módulo dice "Actualizaciones de MyPresta.eu" pero no muestra una nueva versión.**
R4: Esto significa que tu módulo está actualmente actualizado con la última versión oficial disponible en MyPresta.eu. No se requiere ninguna acción.

**P5: Mi tema personalizado no muestra correctamente el campo de entrada de vales.**
R5: El módulo Generador de Vales no añade elementos al front-office. El campo de entrada de vales es una característica estándar de PrestaShop. Si no se muestra correctamente, es probable que sea un problema con el estilo de tu tema personalizado o las anulaciones de plantilla para las páginas del carrito/pago. Tendrías que consultar a tu desarrollador de temas o a un webmaster para ajustar los archivos CSS o TPL relacionados con los hooks `displayCart` o `displayPaymentTop` donde suele aparecer el campo del vale.

## 4. Guía para Desarrolladores y Webmasters (Arquitectura Técnica y Mapa de Código)

### 4.1 Visión General de la Arquitectura

El módulo Generador de Vales (`vouchers`) es un módulo estándar de PrestaShop que opera principalmente dentro del Back Office. Aprovecha la funcionalidad central de `CartRule` de PrestaShop para crear múltiples códigos de descuento de manera eficiente. La lógica principal del módulo reside en su archivo `vouchers.php`, que maneja la configuración y el proceso de generación. No introduce patrones MVC complejos ni tablas de base de datos personalizadas, sino que interactúa directamente con el modelo de objetos `CartRule` existente de PrestaShop.

### 4.2 Controladores (`controllers/`)

-   **Controladores de Front-Office**: Ninguno. El módulo no añade ningún controlador de front-office personalizado. Todas las interacciones de front-office relacionadas con los vales son manejadas por el `CartController` o `OrderController` nativos de PrestaShop.
-   **Controladores de Administración de Back-Office**: Ninguno. La lógica de configuración y generación del módulo está completamente contenida dentro del método `getContent()` de la clase principal del módulo, que es renderizado por el `AdminModulesController` estándar.

### 4.3 Clases y Modelos Principales (`classes/`)

-   Ninguno. El módulo no define ninguna clase personalizada ni extiende `ObjectModel`. Utiliza directamente la clase `CartRule` nativa de PrestaShop para crear y gestionar vales.

### 4.4 Activos JavaScript (`views/js/`)

-   `vouchers/lib/voucherengine/script.js`
    -   **Alcance:** Back-office.
    -   **Propósito:** Este script probablemente contiene la lógica del lado del cliente para la página de configuración del módulo. Esto podría incluir:
        -   Validación de formularios antes de la generación de vales.
        -   Llamadas AJAX al método `getContent()` del módulo para actualizaciones o procesamiento dinámicos.
        -   Mejoras de la interfaz de usuario o interacciones específicas del formulario de generación de vales.
        -   Potencialmente, el manejo de la descarga del archivo CSV generado.
    -   **Detectores de Eventos:** Probablemente se vincula a eventos de envío de formularios, eventos de cambio de entrada y clics de botones en la página de configuración del módulo.
    -   **Manipulación del DOM:** Puede mostrar/ocultar elementos según las selecciones del usuario (por ejemplo, mostrar campos de selección de productos específicos si se elige "Aplicar descuento a: Producto específico").

### 4.5 Hojas de Estilo CSS (`views/css/`)

-   `vouchers/lib/voucherengine/ps16.css`
    -   **Alcance:** Estilo del formulario de administración del Back-office.
    -   **Propósito:** Proporciona un estilo específico para la interfaz de configuración del módulo, potencialmente para asegurar una apariencia consistente en diferentes versiones de PrestaShop (por ejemplo, adaptándose a la estructura específica del tema de administración de PrestaShop 1.6).
    -   **Componentes principales de la interfaz de usuario:** Estilos de campos de formulario, botones y elementos de diseño dentro de la salida de `getContent()` del módulo.
    -   **Selectores de clase CSS clave:** Los desarrolladores pueden inspeccionar la página de configuración del módulo en el navegador para identificar clases específicas (por ejemplo, `.vouchers-generator-form`, `.mypresta-update-block`) que pueden ser anuladas en un tema de administración personalizado si es necesario.

### 4.6 Estructura de Plantillas Smarty (`views/templates/`)

-   `vouchers/views/pdf.tpl`
    -   **Alcance:** Back-office / Utilidad.
    -   **Propósito:** Esta plantilla se utiliza probablemente para generar un documento PDF imprimible o descargable que contiene la lista de vales generados. Si bien la descripción del módulo menciona la exportación CSV/Excel, una plantilla PDF sugiere un formato de salida alternativo o adicional para la lista de vales, posiblemente para imprimir vales físicos.
    -   **Uso:** Se renderizaría cuando el módulo necesite presentar los códigos de vale generados en un formato estructurado e imprimible. Recibiría una matriz de datos de vales (código, valor, caducidad, etc.) de la lógica PHP.

### 4.7 Esquema de Base de Datos y Mapa de Hooks

-   **Tablas de Base de Datos**:

    -   El módulo no crea ninguna tabla de base de datos personalizada.
    -   Interactúa con las tablas nativas `ps_cart_rule` y `ps_cart_rule_lang` de PrestaShop para almacenar los vales generados.
    -   Los ajustes de configuración (como `vg_counter`, `mypresta_updates`) se almacenan en la tabla `ps_configuration`.
-   **Tabla de Hooks Registrados**:

| Nombre del Hook | Momento de Ejecución | Propósito Técnico |
| --- | --- | --- |
| `actionAdminControllerSetMedia` | Se ejecuta cuando se inicializa un Controlador de Administración y se están configurando sus medios (JS/CSS). | Utilizado por el módulo para incluir sus archivos JavaScript (`script.js`) y CSS (`ps16.css`) del Back Office específicamente en su página de configuración, asegurando que se carguen solo cuando sea necesario. |

## 5. Soporte Oficial y Actualizaciones

Para las últimas actualizaciones, correcciones de errores y soporte oficial para el módulo Generador de Vales, consulta tu cuenta de cliente en [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nuestro equipo de soporte está disponible para ayudarte con cualquier problema o pregunta que puedas tener con respecto a la funcionalidad y compatibilidad del módulo.
