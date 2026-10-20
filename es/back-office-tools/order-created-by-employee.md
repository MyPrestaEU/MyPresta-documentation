---
title: "Pedido creado por empleado - Manual de Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop 'Pedido creado por empleado' de MyPresta.eu."
sidebar:
  label: "Pedido creado por empleado - Manual de Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Order created by employee en MyPresta.eu](https://mypresta.eu/modules/administration-tools/order-created-by-employee.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/back-office-tools/order-created-by-employee/)
>
> ---


# Pedido creado por empleado

## 1. Requisitos y Compatibilidad

- **Versiones de PrestaShop compatibles**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilidad con PHP**: PHP 5.6 - 8.5
- **Requisitos de Alojamiento**: Extensiones PHP estándar (cURL, JSON, OpenSSL) típicamente disponibles en cualquier entorno de alojamiento compatible con PrestaShop.

## 2. Recorrido completo por la configuración (Cada ajuste agrupado por pantalla)

### 2.1 Página de configuración del módulo (Back Office > Módulos > Configurar)

Después de la instalación, al hacer clic en el botón "Configurar" se le dirigirá a la página de configuración principal del módulo.

Este módulo está diseñado para ser extremadamente simple y efectivo, requiriendo una configuración mínima. Tras la instalación, comienza automáticamente a recopilar los datos necesarios.

**Qué hace esta pantalla:**
Esta página sirve como confirmación de que el módulo está instalado y activo. No presenta ninguna configuración configurable porque la funcionalidad principal del módulo (registrar pedidos creados por empleados) está habilitada por defecto tras la instalación.

**Efecto de cambiar esta configuración:**
No hay configuraciones que cambiar en esta pantalla. La funcionalidad del módulo está "siempre activa" una vez instalado.

**Valor recomendado:**
No hay valores que establecer. Simplemente asegúrese de que el módulo esté instalado y habilitado.

**Escenario / ejemplo de comerciante:**
Acaba de instalar el módulo. Navega a su página de configuración y ve un mensaje simple que confirma su estado. A partir de este momento, cada nuevo pedido creado por un empleado a través del Back Office de PrestaShop se marcará como tal. Cuando vea los detalles de un pedido, verá una nueva sección que indica si fue creado por un empleado y qué empleado lo hizo.

### 2.2 Pantallas de administración dedicadas y vistas de controlador

Este módulo no añade nuevos elementos de menú dedicados ni pantallas de administración complejas. Su funcionalidad se integra directamente en la página de detalles de pedido existente de PrestaShop.

**Nombre de la pantalla y ubicación del menú:**
La información proporcionada por este módulo se muestra directamente en la **Página de Detalles del Pedido**.
Para acceder a ella:

1.  Navegue a **Pedidos > Pedidos** en su Back Office de PrestaShop.
2.  Haga clic en cualquier pedido de la lista para ver sus detalles.

**Acciones y configuraciones disponibles:**
En la Página de Detalles del Pedido, encontrará una nueva sección (normalmente cerca de la parte superior o en un bloque dedicado) que muestra si el pedido fue creado por un empleado. Si lo fue, también mostrará el nombre del empleado que lo creó.

**Efecto de los cambios:**
No hay acciones o configuraciones que cambiar en esta vista. Esta sección es puramente informativa, proporcionándole los datos recopilados por el módulo.

**Flujo de trabajo recomendado para la gestión diaria de la tienda:**
Al revisar los pedidos, especialmente aquellos que parecen inusuales, o al realizar auditorías internas, siempre verifique la sección "Pedido creado por empleado" en la página de detalles del pedido. Esta verificación rápida puede proporcionar un contexto inmediato sobre el origen del pedido, ayudándole a comprender si fue una compra directa de un cliente o una entrada interna.

### 2.3 Tabla de referencia rápida de configuración

| Pantalla / Vista | Configuración / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| Página de Configuración del Módulo | *(Sin configuraciones configurables)* | N/A | Confirma la instalación y activación del módulo. La funcionalidad del módulo está siempre activa. |
| Página de Detalles del Pedido (Back Office) | Bloque de información "Pedido creado por empleado" | N/A | Muestra si el pedido fue creado por un empleado y su nombre. Puramente informativo. |

## 3. Solución de problemas del comerciante y preguntas frecuentes (FAQ)

**P: He instalado el módulo, pero no veo ningún cambio en los pedidos antiguos.**
R: Este módulo comienza a recopilar datos desde el momento en que se instala. No puede determinar retroactivamente si los pedidos anteriores fueron creados por un empleado. Solo verá la información de "Pedido creado por empleado" en los pedidos realizados *después* de que el módulo se haya instalado y activado correctamente.

**P: Creé un pedido en el Back Office, pero no veo la información del empleado en la página de detalles del pedido.**
R: Primero, asegúrese de que el módulo esté instalado y habilitado (verifique **Módulos > Gestor de módulos**). Si lo está, borre la caché de PrestaShop (**Parámetros avanzados > Rendimiento**). Si el problema persiste, asegúrese de que está viendo un pedido que *realmente fue creado por un empleado* en el Back Office *después* de la instalación del módulo.

**P: ¿Este módulo afecta el rendimiento de mi tienda?**
R: No, el módulo es muy ligero. Solo añade una pequeña pieza de datos durante el proceso de creación de pedidos en el Back Office y muestra esos datos en la página de detalles del pedido. No tiene ningún impacto en el rendimiento de su front office ni en la experiencia del cliente.

**P: ¿Puedo deshabilitar la funcionalidad del módulo sin desinstalarlo?**
R: Este módulo no tiene un interruptor de encendido/apagado en su configuración. Para detener su funcionalidad, deberá deshabilitar o desinstalar el módulo a través del Gestor de Módulos. Sin embargo, dada su naturaleza beneficiosa para el seguimiento interno, generalmente se recomienda mantenerlo activo.

## 4. Guía para desarrolladores y webmasters (Arquitectura técnica y mapa de código)

### 4.1 Resumen de la arquitectura

El módulo "Pedido creado por empleado" (`logoe`) es un módulo de PrestaShop sencillo diseñado para extender la funcionalidad principal de `Order`. Opera principalmente enganchándose al proceso de creación de pedidos dentro del Back Office para registrar el `id_employee` responsable del pedido. Esta información se muestra luego en la página de detalles de pedido existente en el Back Office. Sigue un patrón simple basado en eventos utilizando los hooks de PrestaShop.

### 4.2 Controladores (`controllers/`)

Este módulo no introduce ningún controlador personalizado de front-office o back-office. Toda su lógica se maneja dentro del archivo principal del módulo y a través de hooks.

### 4.3 Clases y modelos principales (`classes/`)

Este módulo no introduce ninguna clase personalizada o definiciones de `ObjectModel`. Interactúa directamente con el objeto `Order` y `Configuration` para sus configuraciones.

### 4.4 Activos de JavaScript (`views/js/`)

Este módulo no incluye ningún archivo JavaScript personalizado.

### 4.5 Hojas de estilo CSS (`views/css/`)

Este módulo no incluye ningún archivo CSS personalizado. El estilo para la información mostrada es típicamente mínimo y se basa en los estilos existentes del Back Office de PrestaShop.

### 4.6 Estructura de la plantilla Smarty (`views/templates/`)

Este módulo utiliza un único archivo de plantilla para mostrar información en el Back Office.

-   **Plantillas de administración (`views/templates/admin/`)**:
    -   `logoe/views/templates/admin/logoelog.tpl`: Esta plantilla es responsable de renderizar el bloque de información "Pedido creado por empleado" en la página de detalles de pedido del Back Office de PrestaShop. Típicamente muestra el nombre del empleado si el pedido fue creado por un empleado. Es probable que se renderice a través de un hook como `displayAdminOrder` o `displayAdminOrderTabContent`.

### 4.7 Esquema de la base de datos y mapa de hooks

-   **Tablas de la base de datos**:
    El módulo no crea una nueva tabla de base de datos dedicada. En su lugar, extiende la tabla `ps_orders` existente añadiendo una nueva columna durante la instalación.

    -   `ps_orders`: Se añade una nueva columna, probablemente `id_employee_created`, a esta tabla para almacenar el ID del empleado que creó el pedido. Esta columna sería `INT(10) UNSIGNED` y anulable, con un valor predeterminado de `NULL`.
-   **Tabla de Hooks Registrados**:

    | Nombre del Hook | Momento de Ejecución | Propósito Técnico |
    | --- | --- | --- |
    | `actionOrderAdd` | Después de que un nuevo pedido se añade correctamente a la base de datos. | Este hook es crucial. Se utiliza para capturar el `id_employee` de la sesión actual del Back Office y actualizar la columna `id_employee_created` del pedido recién creado en `ps_orders`. |
    | `displayAdminOrder` (o similar, por ejemplo, `displayAdminOrderTabContent`, `displayAdminOrderMain`) | Cuando se renderiza la página de detalles de pedido del Back Office. | Este hook se utiliza para inyectar la plantilla `logoelog.tpl` en la página de detalles del pedido, mostrando la información de `id_employee_created` (por ejemplo, el nombre del empleado). |

## 5. Soporte oficial y actualizaciones

Para soporte oficial, actualizaciones del módulo y cualquier asistencia adicional, visite su cuenta de cliente en [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nuestro equipo se dedica a proporcionar soporte oportuno y asegurar que su módulo funcione perfectamente.
"""
