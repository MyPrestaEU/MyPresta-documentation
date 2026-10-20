---
title: "IVA 0% para grupos de clientes seleccionados - Manual del Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop 'IVA 0% para grupos de clientes seleccionados' de MyPresta.eu."
sidebar:
  label: "IVA 0% para grupos de clientes seleccionados"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo VAT 0% for selected groups of customers en MyPresta.eu](https://mypresta.eu/modules/ordering-process/vat-0-for-selected-groups-of-customers.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/ordering-process/vat-0-for-selected-groups-of-customers/)
>
> ---


# IVA 0% para grupos de clientes seleccionados

## 1. Requisitos y Compatibilidad
- **Versiones de PrestaShop Compatibles**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilidad con PHP**: PHP 7.1 - 8.5
- **Requisitos de Alojamiento**: Se requieren extensiones PHP estándar (cURL, JSON, OpenSSL) para PrestaShop y para las comprobaciones de actualización del módulo.

## 2. Recorrido Completo por la Configuración (Cada Ajuste Agrupado por Pantalla)

### 2.1 Página de Configuración del Módulo (Back Office > Módulos > Configurar)
Después de la instalación, al hacer clic en "Configurar" accederá a la página de configuración principal del módulo "IVA 0% para grupos de clientes seleccionados". Esta página se divide en varias secciones.

#### Pestaña de Configuración

Esta es la pestaña principal donde define qué grupos de clientes se beneficiarán del 0% de IVA.

**1. Grupos de clientes que tendrán IVA 0%**
-   **Qué hace esta configuración:** Este es el ajuste más crucial. Le permite seleccionar uno o más grupos de clientes de su tienda PrestaShop que estarán exentos de IVA.
-   **Efecto de cambiar esta configuración:**
    -   *Cuando se selecciona uno o más grupos:* Cualquier cliente que pertenezca a *al menos uno* de los grupos seleccionados tendrá todos los precios de los productos, el envío y los totales del pedido calculados con un 0% de IVA.
    -   *Cuando no se selecciona ningún grupo:* El módulo no aplicará ninguna exención de IVA, y a todos los clientes se les cobrará el IVA según las reglas fiscales estándar de su PrestaShop.
-   **Valor recomendado:** Seleccione todos los grupos de clientes que desea que estén exentos de IVA (por ejemplo, "Clientes Mayoristas", "Clientes B2B").
-   **Escenario / ejemplo de comerciante:** Usted tiene una tienda B2B. Tiene un grupo de clientes llamado "Clientes Mayoristas" que son todas empresas registradas a efectos de IVA. Seleccionaría "Clientes Mayoristas" de esta lista. Cuando un cliente de este grupo inicie sesión, verá todos los precios sin IVA.

**2. Seleccionar regla de impuestos**
-   **Qué hace esta configuración:** Esta opción le permite especificar una regla de impuestos particular que el módulo debe usar al aplicar el 0% de IVA. Aunque el módulo establece la tasa de impuestos en 0%, PrestaShop a menudo requiere que una regla de impuestos válida esté asociada con el cálculo.
-   **Efecto de cambiar esta configuración:**
    -   *Cuando se selecciona una regla de impuestos específica:* El módulo intentará usar esta regla de impuestos, pero con una tasa del 0%, para los grupos de clientes exentos. Esto puede ser útil para garantizar la compatibilidad con otros módulos o configuraciones contables específicas que esperan que una regla de impuestos esté siempre presente.
    -   *Cuando se selecciona "Ninguno" o ninguna regla específica (comportamiento predeterminado):* El módulo manejará la aplicación del 0% de IVA directamente, a menudo anulando la tasa de impuestos al 0% sin adherirse estrictamente a una regla de impuestos predefinida, lo cual suele ser suficiente.
-   **Valor recomendado:** Dejar como predeterminado a menos que encuentre problemas de compatibilidad específicos con otros módulos o tenga un requisito contable muy particular. Si selecciona uno, elija una regla de impuestos genérica del 0% si tiene una, o una regla de impuestos estándar que el módulo pueda anular al 0%.
-   **Escenario / ejemplo de comerciante:** Su contable requiere que todas las transacciones, incluso las de IVA 0%, estén vinculadas a un ID de regla de impuestos específico para fines de informes. Podría crear una regla de impuestos "IVA 0% (Exento)" en PrestaShop y seleccionarla aquí.

#### Pestaña de Reparación de Hooks
Esta pestaña es para la resolución avanzada de problemas y para asegurar que los hooks del módulo estén correctamente registrados.

-   **Qué hace esta configuración:** Esta sección proporciona herramientas para volver a registrar los hooks del módulo en caso de que se desregistren o se corrompan, lo que a veces puede ocurrir después de cambios de tema, conflictos de módulos o problemas de base de datos.
-   **Efecto de cambiar esta configuración:**
    -   *Al hacer clic en "Reparar hooks":* Esta acción intentará volver a registrar todos los hooks necesarios que el módulo utiliza para funcionar correctamente. Si el módulo no funcionaba como se esperaba (por ejemplo, el IVA no se eliminaba), esto podría resolver el problema.
-   **Valor recomendado:** Utilice esto solo si sospecha que el módulo no funciona correctamente (por ejemplo, todavía se cobra el IVA a los grupos exentos) y después de confirmar que su configuración principal es correcta.
-   **Escenario / ejemplo de comerciante:** Acaba de actualizar el tema de su PrestaShop, y ahora a sus clientes exentos de IVA se les está cobrando el IVA de repente. Ha comprobado la configuración de sus grupos y son correctas. Hacer clic en "Reparar hooks" aquí podría solucionar el problema subyacente.

#### Pestaña de Actualizaciones
Esta pestaña proporciona información sobre las actualizaciones del módulo.

-   **Qué hace esta configuración:** Esta sección busca actualizaciones disponibles para el módulo y proporciona información sobre su versión actual.
-   **Efecto de cambiar esta configuración:**
    -   *Comprobación de actualizaciones:* Le informa si hay una versión más reciente del módulo disponible, lo que le permite mantener su módulo actualizado con las últimas características y correcciones de errores.
-   **Valor recomendado:** Revise periódicamente esta pestaña para asegurarse de que está ejecutando la última versión para un rendimiento y seguridad óptimos.
-   **Escenario / ejemplo de comerciante:** Desea asegurarse de que su tienda siempre esté ejecutando el software más estable y seguro. Visita esta pestaña una vez al mes para ver si hay nuevas actualizaciones para sus módulos de MyPresta.eu.

### 2.2 Tabla de Referencia Rápida de Configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
|---|---|---|---|
| Página de Configuración del Módulo | **Grupos de clientes que tendrán IVA 0%** | Seleccionar grupos relevantes (por ejemplo, "Clientes Mayoristas") | Define a qué grupos de clientes se les aplicará el 0% de IVA a todos los precios y totales. |
| Página de Configuración del Módulo | **Seleccionar regla de impuestos** | Dejar como predeterminado (o seleccionar una regla de impuestos del 0% si es necesario para la contabilidad) | Asocia el cálculo del 0% de IVA con una regla de impuestos específica para compatibilidad o informes. |
| Pestaña de Reparación de Hooks | **Botón Reparar hooks** | Solo usar para solucionar problemas | Vuelve a registrar los hooks del módulo para resolver problemas de funcionalidad (por ejemplo, el IVA no se elimina). |
| Pestaña de Actualizaciones | **Buscar actualizaciones** | Comprobar periódicamente | Informa sobre las actualizaciones disponibles del módulo para nuevas características y correcciones de errores. |

## 3. Resolución de Problemas del Comerciante y Preguntas Frecuentes (FAQ)

**P1: Todavía se cobra el IVA a pesar de que he seleccionado el grupo de clientes.**
R1:
*   **Comprobar Asignación de Grupo:** Asegúrese de que el cliente con el que está probando esté realmente asignado a uno de los grupos exentos de IVA seleccionados. Inicie sesión como el cliente, vaya a los detalles de su cuenta o verifique en el Back Office en `Clientes > Clientes`.
*   **Configuración del Módulo:** Vuelva a verificar que los grupos correctos estén seleccionados en la página de configuración del módulo (`Módulos > Gestor de módulos > Configurar` para "IVA 0% para grupos de clientes seleccionados").
*   **Caché:** Borre la caché de su PrestaShop (en `Parámetros avanzados > Rendimiento`) y la caché de su navegador. A veces, se pueden mostrar datos antiguos.
*   **Reparación de Hooks:** Vaya a la pestaña "Reparación de hooks" en la configuración del módulo y haga clic en el botón "Reparar hooks". Esto puede resolver problemas en los que los puntos de integración del módulo con PrestaShop podrían haberse desregistrado.

**P2: ¿Este módulo afectará mis reglas fiscales existentes para clientes no exentos?**
R2: No, este módulo está diseñado para aplicar *solo* el 0% de IVA a los clientes que pertenecen a los grupos específicos que usted seleccione. Para todos los demás clientes, se aplicarán sus reglas y configuraciones fiscales estándar de PrestaShop como de costumbre.

**P3: ¿Este módulo también funciona para los gastos de envío?**
R3: Sí, el módulo está diseñado para aplicar el 0% de IVA a todos los aspectos del pedido, incluidos los precios de los productos, los gastos de envío y cualquier otro elemento sujeto a impuestos, lo que resulta en un valor total del pedido con 0% de IVA para los grupos de clientes seleccionados.

**P4: Tengo un tema personalizado. ¿Funcionará este módulo con él?**
R4: Sí, este módulo funciona modificando la lógica central de cálculo de impuestos de PrestaShop a través de hooks, en lugar de alterar directamente las plantillas del front-office. Por lo tanto, debería ser compatible con la mayoría de los temas personalizados sin problemas. Si experimenta problemas de visualización (por ejemplo, los precios no se actualizan), es probable que sea un problema de caché o un conflicto con otro módulo que también modifique en gran medida los cálculos de impuestos.

**P5: ¿Cómo traduzco el texto del módulo a otros idiomas?**
R5: Si el módulo introduce nuevas cadenas de texto (aunque este módulo funciona principalmente en segundo plano), puede traducirlas a través de la interfaz de traducción de PrestaShop:
1.  Vaya a `Internacional > Traducciones`.
2.  Seleccione "Traducciones de módulos instalados".
3.  Elija su tema, el idioma y luego seleccione "IVA 0% para grupos de clientes seleccionados" de la lista de módulos.
4.  Luego puede modificar cualquier cadena traducible.

## 4. Guía para Desarrolladores y Webmasters (Arquitectura Técnica y Mapa de Código)

### 4.1 Visión General de la Arquitectura
El módulo "IVA 0% para grupos de clientes seleccionados" opera aprovechando el sistema de hooks de PrestaShop para interceptar y modificar los cálculos de impuestos en varias etapas del proceso de pedido. Utiliza principalmente los hooks `actionTaxManager` y `actionProductPriceCalculation` para ajustar dinámicamente la tasa de impuestos al 0% para los clientes que pertenecen a grupos específicos. También incluye una clase `TaxManager` personalizada para manejar la lógica de anulación de impuestos. El módulo sigue una estructura de módulo estándar de PrestaShop, con un archivo de módulo principal, una clase dedicada para la gestión de impuestos y plantillas Smarty para su configuración de Back Office.

### 4.2 Controladores (`controllers/`)
Este módulo no utiliza controladores de Front-Office o Back-Office Admin personalizados. Toda la configuración se maneja a través del método `getContent()` en el archivo principal del módulo.

### 4.3 Clases y Modelos Principales (`classes/`)

-   **`groupvat/classes/GroupvatTaxManager.php`**
    *   **Nombre de la Clase:** `GroupvatTaxManager`
    *   **Clase Padre:** `TaxManager` (la clase `TaxManager` central de PrestaShop)
    *   **Responsabilidad:** Esta clase es el núcleo de la funcionalidad del módulo. Extiende el `TaxManager` predeterminado de PrestaShop para anular su comportamiento. Su método principal, `getTaxCalculator()`, es crucial. Cuando se identifica que un cliente pertenece a un grupo exento de IVA, esta clase asegura que el `TaxCalculator` devuelva una tasa de impuestos del 0%, eliminando efectivamente el IVA de los precios. También contiene lógica para verificar si el cliente actual está en uno de los grupos exentos configurados.
    *   **Métodos Clave:**
        *   `getTaxCalculator(array $params)`: Anula el calculador de impuestos predeterminado para devolver una tasa de impuestos del 0% si el cliente está en un grupo exento.
        *   `isCustomerInGroup(int $id_customer)`: Método auxiliar para determinar si un ID de cliente dado pertenece a alguno de los grupos exentos de IVA configurados.

-   **`groupvat/classes/index.php`**
    *   **Responsabilidad:** Archivo `index.php` vacío estándar para evitar la lista de directorios.

### 4.4 Activos JavaScript (`views/js/`)
Este módulo no incluye ningún archivo JavaScript personalizado.

### 4.5 Hojas de Estilo CSS (`views/css/`)
Este módulo no incluye ningún archivo CSS personalizado. El estilo para la configuración del Back Office se maneja mediante el tema de administración predeterminado de PrestaShop.

### 4.6 Estructura de Plantillas Smarty (`views/templates/`)

-   **`groupvat/views/templates/admin/configure.tpl`**
    *   **Alcance:** Configuración de administración del Back Office.
    *   **Propósito:** Esta es la plantilla principal para la página de configuración del módulo, renderizada por `getContent()` en `groupvat.php`. Incluye otras plantillas para secciones específicas como la selección de grupos de clientes y la reparación de hooks. Normalmente envuelve todo el formulario de configuración.

-   **`groupvat/views/templates/admin/customerGroups.tpl`**
    *   **Alcance:** Configuración de administración del Back Office.
    *   **Propósito:** Esta plantilla renderiza la sección donde el comerciante selecciona los grupos de clientes que tendrán 0% de IVA. Muestra una lista de grupos de clientes disponibles con casillas de verificación.
    *   **Variables:** Probablemente usa `$groups` (array de grupos de clientes), `$selected_groups` (array de IDs de grupos actualmente seleccionados), `$tax_rules` (array de reglas de impuestos disponibles), `$selected_tax_rule` (ID de la regla de impuestos actualmente seleccionada).

-   **`groupvat/views/templates/admin/hooksRepair.tpl`**
    *   **Alcance:** Configuración de administración del Back Office.
    *   **Propósito:** Esta plantilla renderiza la sección "Reparación de hooks", proporcionando un botón para volver a registrar los hooks del módulo.

### 4.7 Esquema de Base de Datos y Mapa de Hooks

-   **Tablas de Base de Datos**:
    *   Este módulo no crea tablas de base de datos personalizadas.
    *   Almacena su configuración en la tabla `ps_configuration` de PrestaShop.
        *   `groupvat_groups`: Almacena una lista de IDs de grupos de clientes separados por comas seleccionados para la exención de IVA.
        *   `groupvat_tax`: Almacena el ID de la regla de impuestos seleccionada (si la hay).
        *   `mypresta_updates`: Almacena información relacionada con las actualizaciones del módulo.

-   **Tabla de Hooks Registrados**:

| Nombre del Hook | Momento de Ejecución | Propósito Técnico |
|---|---|---|
| `actionDispatcher` | Antes de que se despache un controlador. | Se utiliza para anular o modificar potencialmente el comportamiento de despacho, aunque a menudo se usa para la configuración general. |
| `ActionDispatcher` | (Alias de `actionDispatcher`) | Igual que el anterior. |
| `actionCartGetPackageShippingCost` | Al calcular los gastos de envío de un paquete en el carrito. | Crucial para asegurar que los gastos de envío también se calculen con 0% de IVA para grupos exentos. |
| `displayTaxManager` | (Obsoleto/menos común) | Históricamente utilizado para mostrar información relacionada con impuestos. |
| `ActionGetProductPropertiesAfter` | Después de recuperar las propiedades del producto. | Permite la modificación de los datos del producto, incluyendo precio e impuestos, antes de la visualización. |
| `taxManager` | (Obsoleto/menos común) | Históricamente utilizado para la gestión de impuestos. |
| `ActionAuthentication` | Después de que un cliente se autentica (inicia sesión). | Se puede utilizar para establecer variables de sesión o realizar acciones basadas en el grupo de clientes después del inicio de sesión. |
| `ActionTaxManager` | Cuando se instancia la clase `TaxManager` o se llaman a sus métodos. | **Hook principal para este módulo.** Permite que el módulo inyecte su `GroupvatTaxManager` personalizado o modifique la lógica de cálculo de impuestos. |
| `ActionPresentCart` | Antes de que el carrito se presente al usuario. | Permite la modificación de los datos del carrito, incluyendo precios y totales, antes de la renderización. |
| `ActionProductPriceCalculation` | Durante el proceso de cálculo del precio del producto. | **Hook principal para este módulo.** Permite que el módulo modifique la tasa de impuestos aplicada a los precios de los productos. |
| `actionGetProductPropertiesAfter` | (Alias de `ActionGetProductPropertiesAfter`) | Igual que el anterior. |
| `ActionFilterDeliveryOptionList` | Antes de que se muestre la lista de opciones de entrega. | Permite la modificación de las opciones de entrega, afectando potencialmente sus precios (y por lo tanto los impuestos). |

## 5. Soporte Oficial y Actualizaciones
Para soporte oficial, actualizaciones y las últimas versiones del módulo "IVA 0% para grupos de clientes seleccionados", visite su cuenta de cliente en [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nuestro equipo de soporte está disponible para ayudarle con cualquier problema o pregunta que pueda tener.
