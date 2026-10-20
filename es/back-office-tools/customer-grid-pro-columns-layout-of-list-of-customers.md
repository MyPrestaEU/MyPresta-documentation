---
title: "Customer Grid Pro - columnas y diseño de la lista de clientes - Manual del Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop Customer Grid Pro - columnas y diseño de la lista de clientes de MyPresta.eu."
sidebar:
  label: "Customer Grid Pro - columnas y diseño de la lista de clientes"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Customer Grid Pro - columns & layout of list of customers en MyPresta.eu](https://mypresta.eu/modules/administration-tools/customer-grid-pro-columns-layout-of-list-of-customers.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/back-office-tools/customer-grid-pro-columns-layout-of-list-of-customers/)
>
> ---


# Customer Grid Pro - columnas y diseño de la lista de clientes

## 1. Requisitos y compatibilidad
- **Versiones de PrestaShop compatibles**: PrestaShop 9.x, 8.x, 1.7.8.x, 1.7.7.x
- **Compatibilidad con PHP**: PHP 7.1 - 8.5
- **Requisitos de alojamiento**: Extensiones PHP estándar (cURL, JSON, OpenSSL).

## 2. Recorrido completo de la configuración (Cada ajuste agrupado por pantalla)

### 2.1 Página de configuración del módulo (Back Office > Módulos > Configurar)
Después de instalar el módulo, haga clic en "Configurar" para acceder a sus ajustes. Esta página le permite seleccionar qué columnas aparecen en su lista de clientes y en qué orden.

La página de configuración mostrará una lista de todas las columnas disponibles para su cuadrícula de clientes. Estas incluyen columnas estándar de PrestaShop y nuevas añadidas por el módulo (como teléfono, dirección, estadísticas de pedidos).

**Cómo usar la interfaz de configuración:**

1.  **Lista de columnas disponibles:** En el lado izquierdo, verá una lista de todas las columnas que *pueden* mostrarse.
2.  **Lista de columnas activas:** En el lado derecho, verá una lista de columnas que están actualmente *activas* y se mostrarán en su lista de clientes.
3.  **Añadir una columna:** Para añadir una columna a su lista de clientes, simplemente arrástrela desde la lista de "Columnas disponibles" de la izquierda y suéltela en la lista de "Columnas activas" de la derecha.
4.  **Eliminar una columna:** Para eliminar una columna de su lista de clientes, arrástrela desde la lista de "Columnas activas" de la derecha y suéltela de nuevo en la lista de "Columnas disponibles" de la izquierda.
5.  **Reordenar columnas:** Dentro de la lista de "Columnas activas", puede arrastrar y soltar columnas hacia arriba o hacia abajo para cambiar su orden de visualización en su cuadrícula de clientes. La columna en la parte superior de la lista aparecerá primero (más a la izquierda) en su lista de clientes.
6.  **Botón Guardar:** Después de realizar cualquier cambio (añadir, eliminar o reordenar columnas), recuerde hacer clic en el botón **"Guardar"** en la parte inferior de la página para aplicar su nueva configuración.

**Lista de columnas disponibles y su propósito:**

| Nombre de la columna (Ejemplo) | Qué hace este ajuste | Efecto de cambiar este ajuste | Valor recomendado | Escenario / ejemplo de comerciante |
|---|---|---|---|---|
| **ID** | Muestra el número de identificación único para cada cliente. | *Cuando está activo:* Muestra el ID del cliente. *Cuando está inactivo:* Oculta la columna ID. | Activo | Útil para referenciar rápidamente a los clientes por su ID interno, especialmente al tratar con tickets de soporte. |
| **Título social** | Muestra el título elegido por el cliente (por ejemplo, Sr., Sra.). | *Cuando está activo:* Muestra el título social. *Cuando está inactivo:* Oculta la columna del título social. | Activo (opcional) | Bueno para la comunicación formal o si su negocio requiere saludos específicos. |
| **Nombre** | Muestra el nombre del cliente. | *Cuando está activo:* Muestra el nombre. *Cuando está inactivo:* Oculta la columna del nombre. | Activo | Esencial para identificar clientes. |
| **Apellido** | Muestra el apellido del cliente. | *Cuando está activo:* Muestra el apellido. *Cuando está inactivo:* Oculta la columna del apellido. | Activo | Esencial para identificar clientes. |
| **Dirección de correo electrónico** | Muestra la dirección de correo electrónico del cliente. | *Cuando está activo:* Muestra la dirección de correo electrónico. *Cuando está inactivo:* Oculta la columna de correo electrónico. | Activo | Crucial para contactar a los clientes y a menudo se utiliza como identificador principal. |
| **Edad** | Muestra la edad del cliente (si se proporciona la fecha de nacimiento). | *Cuando está activo:* Muestra la edad calculada del cliente. *Cuando está inactivo:* Oculta la columna de edad. | Activo (opcional) | Útil para la segmentación de marketing o productos con restricción de edad. |
| **Fecha de registro** | Muestra la fecha en que el cliente registró su cuenta. | *Cuando está activo:* Muestra la fecha de registro. *Cuando está inactivo:* Oculta la columna de fecha de registro. | Activo | Ayuda a rastrear la adquisición de clientes e identificar clientes nuevos vs. antiguos. |
| **Última visita** | Muestra la fecha del último inicio de sesión/visita del cliente. | *Cuando está activo:* Muestra la fecha de la última visita. *Cuando está inactivo:* Oculta la columna de la última visita. | Activo (opcional) | Útil para identificar clientes activos vs. inactivos para campañas de reenganche. |
| **Pedidos totales** | Muestra el número total de pedidos realizados por el cliente. | *Cuando está activo:* Muestra un recuento de todos los pedidos. *Cuando está inactivo:* Oculta esta columna. | Activo | Excelente para identificar compradores frecuentes o clientes con múltiples compras. |
| **Total gastado** | Muestra el valor monetario total gastado por el cliente en todos los pedidos. | *Cuando está activo:* Muestra la suma de todos los totales de pedidos. *Cuando está inactivo:* Oculta esta columna. | Activo | Crítico para identificar clientes de alto valor (VIP) y para la gestión de cuentas B2B. |
| **Número de teléfono** | Muestra el número de teléfono principal del cliente (de su dirección predeterminada). | *Cuando está activo:* Muestra el número de teléfono. *Cuando está inactivo:* Oculta esta columna. | Activo | Esencial para el contacto directo, especialmente para problemas de entrega o consultas urgentes. |
| **Teléfono móvil** | Muestra el número de teléfono móvil del cliente (de su dirección predeterminada). | *Cuando está activo:* Muestra el número de teléfono móvil. *Cuando está inactivo:* Oculta esta columna. | Activo | Proporciona un método de contacto alternativo, a menudo preferido para una comunicación rápida. |
| **Dirección 1** | Muestra la primera línea de la dirección predeterminada del cliente. | *Cuando está activo:* Muestra la línea de dirección. *Cuando está inactivo:* Oculta esta columna. | Activo (opcional) | Útil para una referencia rápida de la ubicación sin abrir la dirección completa. |
| **Dirección 2** | Muestra la segunda línea de la dirección predeterminada del cliente. | *Cuando está activo:* Muestra la línea de dirección. *Cuando está inactivo:* Oculta esta columna. | Activo (opcional) | Proporciona detalles adicionales de la dirección. |
| **Código postal** | Muestra el código postal de la dirección predeterminada del cliente. | *Cuando está activo:* Muestra el código postal. *Cuando está inactivo:* Oculta esta columna. | Activo (opcional) | Útil para la segmentación geográfica o la planificación de entregas. |
| **Ciudad** | Muestra la ciudad de la dirección predeterminada del cliente. | *Cuando está activo:* Muestra la ciudad. *Cuando está inactivo:* Oculta esta columna. | Activo (opcional) | Útil para la segmentación geográfica o el marketing local. |
| **Estado/Provincia** | Muestra el estado/provincia de la dirección predeterminada del cliente. | *Cuando está activo:* Muestra el estado/provincia. *Cuando está inactivo:* Oculta esta columna. | Activo (opcional) | Importante para la segmentación regional y el envío. |
| **País** | Muestra el país de la dirección predeterminada del cliente. | *Cuando está activo:* Muestra el país. *Cuando está inactivo:* Oculta esta columna. | Activo (opcional) | Esencial para tiendas internacionales y logística de envío. |
| **Newsletter** | Indica si el cliente está suscrito a su boletín. | *Cuando está activo:* Muestra un indicador "Sí" o "No". *Cuando está inactivo:* Oculta esta columna. | Activo | Ayuda a identificar oportunidades de marketing y gestionar listas de correo electrónico. |
| **Opt-in** | Indica si el cliente ha optado por recibir ofertas de socios. | *Cuando está activo:* Muestra un indicador "Sí" o "No". *Cuando está inactivo:* Oculta esta columna. | Activo (opcional) | Útil para gestionar los esfuerzos de marketing de socios. |
| **Activo** | Indica si la cuenta del cliente está actualmente activa. | *Cuando está activo:* Muestra un indicador "Sí" o "No". *Cuando está inactivo:* Oculta esta columna. | Activo | Ayuda a identificar cuentas deshabilitadas. |
| **Grupo predeterminado** | Muestra el grupo de clientes principal del cliente. | *Cuando está activo:* Muestra el nombre del grupo predeterminado. *Cuando está inactivo:* Oculta esta columna. | Activo | Crucial para tiendas B2B o tiendas con precios/acceso por niveles. |
| **Nombre de la tienda** | Muestra el nombre de la tienda si se utiliza el modo multi-tienda. | *Cuando está activo:* Muestra el nombre de la tienda. *Cuando está inactivo:* Oculta esta columna. | Activo (si es multi-tienda) | Esencial para entornos multi-tienda para diferenciar a los clientes por tienda. |
| **Cantidad pendiente** | Muestra cualquier saldo pendiente que el cliente deba (si corresponde, por ejemplo, para crédito B2B). | *Cuando está activo:* Muestra la cantidad pendiente. *Cuando está inactivo:* Oculta esta columna. | Activo (si corresponde) | Importante para la gestión de crédito B2B. |
| **Permitir pedidos pendientes** | Indica si el cliente puede realizar pedidos pendientes. | *Cuando está activo:* Muestra "Sí" o "No". *Cuando está inactivo:* Oculta esta columna. | Activo (si corresponde) | Relevante para la gestión de inventario y acuerdos específicos con clientes. |

### 2.2 Tabla de referencia rápida de configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e impacto |
|---|---|---|---|
| Página de configuración del módulo | Orden de columnas arrastrar y soltar | Definido por el usuario | Controla el orden visual de las columnas en la lista de clientes del Back Office. |
| Página de configuración del módulo | Lista de columnas activas | Definido por el usuario | Determina qué columnas son visibles en la lista de clientes del Back Office. |
| Página de configuración del módulo | Lista de columnas disponibles | Definido por el usuario | Enumera todas las posibles columnas que se pueden añadir a la lista de clientes. |
| Página de configuración del módulo | Botón Guardar | Hacer clic después de los cambios | Aplica todos los cambios de visibilidad y orden de las columnas a la cuadrícula de clientes. |

## 3. Solución de problemas del comerciante y preguntas frecuentes (FAQ)

**P: He configurado las columnas, pero no veo ningún cambio en mi lista de clientes.**
R:
1.  **¿Hizo clic en "Guardar"?** Después de realizar cambios en la página de configuración del módulo, debe hacer clic en el botón "Guardar".
2.  **Borrar caché de PrestaShop:** A veces, la caché de PrestaShop puede evitar que los cambios aparezcan inmediatamente. Vaya a **Parámetros avanzados > Rendimiento** y haga clic en "Borrar caché" (o "Borrar caché de Smarty" en versiones anteriores).
3.  **Verificar caché del navegador:** Intente borrar la caché de su navegador o abrir el Back Office en una ventana de navegación de incógnito/privada.

**P: Algunas columnas que espero ver (como "Nombre de la empresa" o "Cantidad pendiente") no están disponibles en la lista.**
R:
1.  **Compatibilidad del módulo:** Asegúrese de haber descargado e instalado la versión correcta del módulo para su versión específica de PrestaShop.
2.  **Características de PrestaShop:** Algunas columnas (por ejemplo, "Cantidad pendiente") solo son relevantes si tiene habilitadas características específicas de PrestaShop (como el modo B2B) o si tiene instalados otros módulos que proporcionan estos datos. Si los datos no existen en su tienda, es posible que el módulo no pueda mostrarlos.

**P: La funcionalidad de arrastrar y soltar no funciona en la página de configuración.**
R:
1.  **Compatibilidad del navegador:** Asegúrese de estar utilizando un navegador web moderno (Chrome, Firefox, Edge, Safari) y de que JavaScript esté habilitado.
2.  **Módulos en conflicto:** En raras ocasiones, otro módulo o una modificación de tema personalizada podría interferir con JavaScript. Intente deshabilitar temporalmente otros módulos para ver si el problema se resuelve. Si lo hace, póngase en contacto con el soporte de MyPresta.eu.

**P: ¿Puedo traducir los nuevos nombres de columna a otros idiomas?**
R: Sí, el sistema de traducción de PrestaShop debería permitirle traducir las cadenas del módulo.
1.  Vaya a **Internacional > Traducciones**.
2.  Seleccione "Traducciones de módulos instalados".
3.  Elija su tema, su idioma y luego seleccione "Customer Grid Pro".
4.  Debería encontrar las cadenas para los nombres de las columnas allí para traducir.

**P: ¿Este módulo ralentizará mi Back Office?**
R: El módulo está optimizado para integrarse con la cuadrícula de clientes principal de PrestaShop. Si bien añadir muchas columnas complejas (especialmente aquellas que requieren cálculos como "Total gastado") podría aumentar ligeramente el tiempo de carga en comparación con una lista básica, el impacto es generalmente insignificante en un servidor bien configurado. Los beneficios en eficiencia suelen superar con creces cualquier diferencia menor de rendimiento.

## 4. Guía para desarrolladores y webmasters (Arquitectura técnica y mapa de código)

### 4.1 Resumen de la arquitectura
El módulo `Customer Grid Pro` extiende principalmente la funcionalidad de la lista de clientes del Back Office de PrestaShop. Lo logra enganchándose a los hooks `actionCustomerGridDefinitionModifier` y `actionCustomerGridDataModifier`, que forman parte del nuevo sistema de cuadrículas de PrestaShop introducido en 1.7.x. Esto permite al módulo añadir, eliminar y reordenar columnas y sus datos asociados dinámicamente sin modificar directamente los archivos principales. La configuración se gestiona a través de un método `getContent()` estándar en el archivo principal del módulo, utilizando JavaScript y CSS personalizados para la interfaz de arrastrar y soltar.

### 4.2 Controladores (`controllers/`)
Este módulo no introduce ningún controlador personalizado de Front-Office o Back-Office. Toda la configuración se maneja dentro del método `getContent()` del archivo principal del módulo.

### 4.3 Clases y modelos principales (`classes/`)
Este módulo no define ninguna clase personalizada o entidades `ObjectModel` en un directorio `classes/`. Toda la lógica está autocontenida dentro del archivo principal del módulo `index.php`.

### 4.4 Activos JavaScript (`views/js/`)

-   **`mycustomergridpro/views/js/customer_grid_admin.js`**
    *   **Alcance:** Back-office (específicamente la página de configuración del módulo).
    *   **Propósito:** Este script proporciona la funcionalidad de arrastrar y soltar para la interfaz de selección de columnas en la página de configuración del módulo. Utiliza el widget `sortable` de jQuery UI para permitir la reordenación y el movimiento de elementos entre las listas de "Columnas disponibles" y "Columnas activas".
    *   **Funcionalidad clave:**
        *   Inicializa dos listas ordenables: `#available_columns` y `#active_columns`.
        *   Configura `connectWith` para permitir que los elementos se muevan entre estas dos listas.
        *   Maneja el evento `update` para las listas ordenables para potencialmente activar el guardado o actualizar campos de entrada ocultos (aunque el guardado real se maneja mediante el envío del formulario).
        *   Asegura que el orden de los elementos en la lista `#active_columns` se envíe correctamente con el formulario.

### 4.5 Hojas de estilo CSS (`views/css/`)

-   **`mycustomergridpro/views/css/customer_grid_admin.css`**
    *   **Alcance:** Back-office (específicamente la página de configuración del módulo).
    *   **Propósito:** Proporciona estilos para la interfaz de selección de columnas de arrastrar y soltar.
    *   **Estilo clave:**
        *   Estilos para los contenedores de la lista de columnas (`#available_columns`, `#active_columns`).
        *   Estilos para los elementos de columna individuales (`.column-item`).
        *   Pistas visuales para operaciones de arrastrar y soltar (por ejemplo, `ui-sortable-helper`, `ui-sortable-placeholder`).
        *   Asegura que las dos listas de columnas se muestren una al lado de la otra o en un diseño claro para la usabilidad.

### 4.6 Estructura de la plantilla Smarty (`views/templates/`)
Este módulo no utiliza archivos `.tpl` separados para su configuración o visualización en el front-office. Todo el HTML del formulario de configuración se genera directamente dentro del método `getContent()` del archivo principal del módulo `index.php`.

### 4.7 Esquema de la base de datos y mapa de hooks

-   **Tablas de la base de datos**:
    *   Este módulo no crea ninguna tabla SQL personalizada.
    *   Almacena su configuración (la lista de columnas activas y su orden) en la tabla `ps_configuration` utilizando claves como `MYCUSTOMERGRIDPRO_ACTIVE_COLUMNS`. Esta configuración se almacena como una matriz serializada o una cadena JSON.

-   **Tabla de Hooks registrados**:

| Nombre del Hook | Momento de ejecución | Propósito técnico |
|---|---|---|
| `actionCustomerGridDefinitionModifier` | Se ejecuta cuando se está construyendo la definición de la cuadrícula de clientes en el Back Office. | Permite al módulo añadir nuevas columnas (por ejemplo, teléfono, pedidos totales, total gastado, campos de dirección) y eliminar las existentes de la definición de la cuadrícula. Este hook recibe el objeto `GridDefinition`. |
| `actionCustomerGridDataModifier` | Se ejecuta después de que se hayan obtenido los datos de la cuadrícula de clientes, pero antes de que se rendericen. | Permite al módulo rellenar los datos de las columnas personalizadas añadidas a través de `actionCustomerGridDefinitionModifier`. Este hook recibe el objeto `QueryResult`, permitiendo la modificación de las filas de datos. |
| `displayBackOfficeHeader` | Se ejecuta en la sección `<head>` de las páginas del Back Office. | Se utiliza para incluir los archivos CSS (`customer_grid_admin.css`) y JavaScript (`customer_grid_admin.js`) personalizados del módulo en la página de configuración del módulo, habilitando la interfaz de arrastrar y soltar. |

## 5. Soporte oficial y actualizaciones
Para las últimas actualizaciones, correcciones de errores y soporte oficial para el módulo "Customer Grid Pro - columnas y diseño de la lista de clientes", consulte su cuenta de cliente en [MyPresta.eu](https://mypresta.eu/). Nuestro equipo de soporte está disponible para ayudar a comerciantes y desarrolladores con cualquier problema o pregunta relacionada con la funcionalidad e integración del módulo.
