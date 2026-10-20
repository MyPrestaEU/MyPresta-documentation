---
title: "Valor mínimo de pedido por grupo de clientes - Manual de Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop 'Valor mínimo de pedido por grupo de clientes' de MyPresta.eu."
sidebar:
  label: "Valor mínimo de pedido por grupo de clientes - Manual de Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Minimum order value by customer group en MyPresta.eu](https://mypresta.eu/modules/ordering-process/minimum-order-value-by-customer-group.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/ordering-process/minimum-order-value-by-customer-group/)
>
> ---


# Valor mínimo de pedido por grupo de clientes

## 1. Requisitos y Compatibilidad

- **Versiones de PrestaShop Soportadas**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilidad PHP**: PHP 7.1 - 8.5
- **Requisitos de Alojamiento**: Extensiones PHP estándar (cURL, JSON, OpenSSL).

## 2. Recorrido Completo por la Configuración (Cada Ajuste Agrupado por Pantalla)

### 2.1 Página de Configuración del Módulo (Back Office > Módulos > Configurar)

Esta es la pantalla de configuración principal donde define los valores mínimos de pedido para cada grupo de clientes.

#### Ajustes Generales

-   **Excluir grupos de clientes específicos de la regla de valor mínimo de pedido:**

    -   **Qué hace este ajuste:** Le permite seleccionar grupos de clientes que *no* estarán sujetos a ningún valor mínimo de pedido, incluso si ha establecido uno para ellos a continuación. Siempre podrán pasar por caja independientemente del total de su carrito.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando está activado (grupos seleccionados):* Los clientes que pertenezcan a los grupos seleccionados omitirán todas las comprobaciones de valor mínimo de pedido.
        -   *Cuando está desactivado (ningún grupo seleccionado):* Todos los grupos de clientes estarán sujetos a los valores mínimos de pedido que defina.
    -   **Valor recomendado:** Depende de su modelo de negocio. Si tiene VIPs o clientes B2C específicos que desea eximir, selecciónelos aquí. De lo contrario, déjelo vacío.
    -   **Escenario / ejemplo de comerciante:** Tiene un grupo de "Clientes VIP" a quienes desea que siempre puedan pasar por caja, incluso si su pedido es pequeño. Seleccione "Clientes VIP" aquí.
-   **Incluir impuestos en el valor mínimo de pedido:**

    -   **Qué hace este ajuste:** Determina si el valor mínimo de pedido que establece debe incluir o excluir el importe del impuesto calculado para los productos en el carrito.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando está activado (SÍ):* El módulo comprobará el total del carrito *incluyendo* impuestos contra su mínimo definido.
        -   *Cuando está desactivado (NO):* El módulo comprobará el total del carrito *excluyendo* impuestos contra su mínimo definido.
    -   **Valor recomendado:** "SÍ" para la mayoría de las tiendas B2C, ya que los clientes suelen ver y pagar el precio total incluyendo impuestos. "NO" podría ser preferible para tiendas B2B donde los precios a menudo se cotizan sin impuestos.
    -   **Escenario / ejemplo de comerciante:** Si establece un mínimo de 100 € y esto está activado, un total de carrito de 90 € (sin impuestos) + 10 € (impuestos) = 100 € pasaría. Si está desactivado, el mismo carrito fallaría porque 90 € es menos de 100 €.
-   **Incluir gastos de envío en el valor mínimo de pedido:**

    -   **Qué hace este ajuste:** Determina si el costo de envío del pedido debe agregarse al total del carrito antes de verificarlo con el valor mínimo del pedido.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando está activado (SÍ):* El módulo comprobará (Total del Carrito + Costo de Envío) contra su mínimo definido.
        -   *Cuando está desactivado (NO):* El módulo comprobará solo el Total del Carrito (productos) contra su mínimo definido.
    -   **Valor recomendado:** "NO" en la mayoría de los casos, ya que los mínimos suelen referirse al valor del producto. Sin embargo, si sus costos de envío son muy altos y desea asegurar un cierto valor total de transacción, podría activar esto.
    -   **Escenario / ejemplo de comerciante:** Desea que los clientes compren al menos 50 € en productos. Si esto es "NO", un carrito de productos de 50 € pasa. Si esto es "SÍ" y el envío es de 10 €, el cliente necesitaría 50 € en productos + 10 € de envío = 60 € en total para pasar, lo que significa que necesitaría 60 € en productos para cumplir el mínimo de 50 €. Este ajuste suele ser "NO" para evitar confusiones.
-   **Aplicar valor mínimo de pedido solo para el primer pedido:**

    -   **Qué hace este ajuste:** Si está activado, las reglas de valor mínimo de pedido solo se aplicarán al primer pedido de un cliente en su tienda. Los pedidos posteriores no estarán sujetos a los mínimos.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando está activado (SÍ):* Solo los nuevos clientes (aquellos que no han realizado un pedido antes) se enfrentarán a las restricciones de valor mínimo de pedido.
        -   *Cuando está desactivado (NO):* Todos los pedidos, independientemente de si son el primero o el décimo de un cliente, se verificarán con el valor mínimo de pedido.
    -   **Valor recomendado:** "NO" para la mayoría de los escenarios donde desea mínimos consistentes. "SÍ" podría ser útil para fomentar compras iniciales más grandes de nuevos clientes, y luego relajar las reglas para negocios repetidos.
    -   **Escenario / ejemplo de comerciante:** Desea que los nuevos clientes B2B realicen un primer pedido sustancial de 500 € para establecer su cuenta, pero después de eso, pueden pedir cualquier cantidad. Active esto y establezca el mínimo de 500 € para su grupo B2B.

#### Valores Mínimos de Pedido por Grupo de Clientes

Debajo de la configuración general, encontrará una lista de todos sus grupos de clientes. Para cada grupo, puede definir un valor mínimo de pedido.

-   **Nombre del Grupo de Clientes (por ejemplo, "Visitante", "Invitado", "Cliente", "Mayorista"):**
    -   **Qué hace este ajuste:** Aquí es donde introduce el importe mínimo de pedido específico requerido para los clientes que pertenecen a este grupo en particular.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando se introduce un valor (por ejemplo, 50.00):* Los clientes de este grupo deben tener un total de carrito igual o superior a este valor para proceder al pago.
        -   *Cuando se deja vacío o se establece en 0.00:* No hay un valor mínimo de pedido para este grupo de clientes. Pueden pasar por caja con cualquier total de carrito.
    -   **Valor recomendado:** Establezca un valor que tenga sentido comercial para cada grupo. Déjelo vacío para grupos como "Visitante" o "Invitado" a menos que desee específicamente bloquearlos para que no realicen pedidos.
    -   **Escenario / ejemplo de comerciante:**
        -   Para el grupo "Cliente": Establezca en `25.00` para fomentar compras minoristas ligeramente más grandes.
        -   Para el grupo "Mayorista": Establezca en `200.00` para asegurar la rentabilidad en los pedidos B2B.
        -   Para el grupo "Invitado": Déjelo vacío (`0.00`) para permitir compras rápidas sin registro.

#### Consideraciones Multi-Tienda y Multi-Moneda

-   **Multi-Tienda:** Si tiene varias tiendas habilitadas, verá un menú desplegable en la parte superior de la página de configuración (normalmente junto al botón "Guardar") que le permitirá seleccionar qué tienda está configurando. Los valores mínimos de pedido se pueden establecer de forma independiente para cada tienda.
-   **Multi-Moneda:** Los valores mínimos de pedido que introduzca siempre están en la *moneda predeterminada* de su tienda PrestaShop. El módulo convierte automáticamente estos valores a la moneda seleccionada por el cliente al tipo de cambio actual al verificar el total del carrito.

### 2.2 Tabla de Referencia Rápida de Configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| Configuración del Módulo | Excluir grupos de clientes específicos | Vacío | Seleccionar grupos para omitir las reglas de pedido mínimo. |
| Configuración del Módulo | Incluir impuestos en el valor mínimo de pedido | SÍ | Determina si el impuesto forma parte del total mínimo. |
| Configuración del Módulo | Incluir gastos de envío en el valor mínimo de pedido | NO | Determina si el envío forma parte del total mínimo. |
| Configuración del Módulo | Aplicar valor mínimo de pedido solo para el primer pedido | NO | Aplica mínimos solo a la compra inicial de un cliente. |
| Configuración del Módulo | Valor mínimo de pedido para [Nombre del Grupo de Clientes] | 0.00 (vacío) | Establece el total de carrito requerido para cada grupo de clientes. |

## 3. Solución de Problemas para Comerciantes y Preguntas Frecuentes (FAQ)

**P: Mis clientes ven el mensaje de pedido mínimo aunque el total de su carrito parece correcto. ¿Qué está mal?**
R:

1.  **Verifique la configuración de Impuestos/Envío:** Vuelva a verificar si "Incluir impuestos en el valor mínimo de pedido" o "Incluir gastos de envío en el valor mínimo de pedido" están habilitados. El total del carrito mostrado podría ser diferente del valor con el que el módulo está comparando.
2.  **Conversión de Moneda:** Si opera en varias monedas, asegúrese de que los tipos de cambio estén actualizados. El módulo convierte sus mínimos de moneda predeterminada a la moneda seleccionada por el cliente.
3.  **Asignación de Grupo de Clientes:** Verifique que el cliente esté asignado correctamente al grupo de clientes que desea, y que el valor mínimo para ese grupo esté configurado como se espera.
4.  **Borrar Caché:** Vaya a **Parámetros Avanzados > Rendimiento** y haga clic en "Borrar caché" (o "Borrar caché de Smarty" en versiones anteriores). A veces, los datos antiguos en caché pueden causar problemas.

**P: He establecido un mínimo, pero un grupo de clientes específico aún puede pasar por caja con cualquier cantidad. ¿Por qué?**
R: Verifique la configuración "Excluir grupos de clientes específicos de la regla de valor mínimo de pedido" en la página de configuración del módulo. Si ese grupo de clientes está seleccionado allí, omitirán todas las comprobaciones de pedido mínimo. Elimínelos de esta lista de exclusión si desea que se aplique el mínimo.

**P: El mensaje del módulo no aparece, o se ve extraño en mi tema personalizado.**
R:

1.  **Compatibilidad del Tema:** Los temas personalizados pueden anular las plantillas o CSS estándar de PrestaShop, lo que podría afectar la forma en que se muestran los mensajes del módulo.
2.  **Conflictos de CSS:** Otro módulo o el CSS de su tema podría estar en conflicto con el estilo del módulo.
3.  **Caché de Smarty:** Borre su caché de Smarty (Parámetros Avanzados > Rendimiento > Borrar caché) para asegurarse de que se estén utilizando los archivos de plantilla más recientes.
    Para problemas visuales, es posible que deba consultar a un desarrollador web para inspeccionar el CSS y los archivos de plantilla de su tema.

**P: ¿Puedo establecer diferentes mínimos para diferentes productos?**
R: No, este módulo establece un mínimo para el *valor total del carrito* basado en el grupo de clientes, no para productos individuales. Si necesita mínimos específicos por producto, necesitaría un tipo de módulo diferente.

**P: ¿Cómo maneja este módulo las configuraciones multi-tienda?**
R: El módulo es compatible con multi-tienda. Al configurar, use el selector de "Contexto de tienda" en la parte superior del back office de PrestaShop (normalmente junto al botón "Guardar") para cambiar entre sus tiendas. Luego puede establecer valores mínimos de pedido únicos para cada grupo de clientes, por tienda.

## 4. Guía para Desarrolladores y Webmasters (Arquitectura Técnica y Mapa de Código)

### 4.1 Visión General de la Arquitectura

El módulo "Valor mínimo de pedido por grupo de clientes" (`cgma`) está construido siguiendo la arquitectura de módulo estándar de PrestaShop. Utiliza principalmente hooks para inyectar su lógica en el proceso de carrito y pago del front-office. La configuración se gestiona a través del método `getContent()` de la clase principal del módulo, almacenando los ajustes en `ps_configuration`. La interacción del front-office se maneja mediante un controlador AJAX dedicado para la validación del carrito en tiempo real.

### 4.2 Controladores (`controllers/`)

-   **Controladores del Front-Office**:

    -   `cgma/controllers/front/ajax.php`
        -   **Nombre de la Clase:** `CgmaAjaxModuleFrontController` (extiende `ModuleFrontController`)
        -   **Responsabilidad:** Este controlador maneja las solicitudes AJAX del front-office, principalmente para la validación en tiempo real del total del carrito contra el valor mínimo de pedido del grupo de clientes. Probablemente devuelve una respuesta JSON indicando si el carrito cumple los requisitos y, potencialmente, un mensaje para mostrar al usuario. Esto es crucial para las actualizaciones dinámicas sin recargas completas de la página.
    -   `cgma/controllers/front/index.php`
        -   **Nombre de la Clase:** `CgmaIndexModuleFrontController` (extiende `ModuleFrontController`)
        -   **Responsabilidad:** Este es un controlador de marcador de posición o de reserva. En muchos módulos, si no se define una acción específica, las solicitudes pueden caer en un controlador `index`. También podría usarse para redirecciones simples o para asegurar que exista una ruta de módulo válida, aunque su función principal en este módulo es probablemente mínima en comparación con `ajax.php`.
-   **Controladores de Administración del Back-Office**:

    -   Ninguno definido explícitamente en el inventario. Toda la configuración del back-office se maneja directamente dentro del método `getContent()` del archivo principal del módulo.

### 4.3 Clases y Modelos Principales (`classes/`)

-   No se enumeran explícitamente clases personalizadas o definiciones de `ObjectModel` en el inventario. El módulo probablemente se basa en las clases principales de PrestaShop `Customer`, `Group`, `Cart` y `Configuration` para su funcionalidad. Los valores de configuración se almacenan directamente en la tabla `ps_configuration`.

### 4.4 Activos JavaScript (`views/js/`)

-   `cgma/views/js/cgma.js`
    -   **Alcance:** Front-office.
    -   **Detalles:** Este script es responsable de la interacción y validación del lado del cliente. Probablemente escucha los cambios en el carrito de compras (por ejemplo, actualizaciones de cantidad, eliminaciones de productos) o los intentos de proceder al pago. Luego, activaría llamadas AJAX a `cgma/controllers/front/ajax.php` para validar el total del carrito contra el valor mínimo de pedido. Al recibir una respuesta, actualizaría dinámicamente el resumen del carrito o los botones de pago, mostrando mensajes al usuario si no se cumple el mínimo y, potencialmente, deshabilitando el botón "Proceder al Pago". También podría encargarse de mostrar el mensaje de valor mínimo de pedido en varias ubicaciones del front-office.

### 4.5 Hojas de Estilo CSS (`views/css/`)

-   `cgma/css.css`
    -   **Alcance:** Probablemente front-office.
    -   **Detalles:** Esta hoja de estilo proporciona el estilo básico para los mensajes o elementos del front-office del módulo, como el mensaje de advertencia que se muestra cuando no se cumple el valor mínimo de pedido.
    -   **Selectores de clase CSS clave:** Los desarrolladores deben inspeccionar este archivo en busca de clases como `.cgma-warning-message`, `.cgma-disabled-button` o similares, que pueden ser anuladas en un tema personalizado.
-   `cgma/views/css/cgma.css`
    -   **Alcance:** Probablemente front-office.
    -   **Detalles:** Similar a `cgma/css.css`, este archivo proporciona estilo adicional o más específico para los componentes del front-office del módulo. Podría contener ajustes responsivos o reglas de diseño específicas.
    -   **Selectores de clase CSS clave:** Busque selectores relacionados con el resumen del carrito, los botones de pago o los contenedores de mensajes específicos.

### 4.6 Estructura de Plantillas Smarty (`views/templates/`)

-   **Plantillas de hook (`views/templates/hook/`)**:

    -   Ninguna enumerada explícitamente en el inventario, pero la implementación del hook `displayShoppingCart` del módulo probablemente renderizaría una plantilla. Es posible que `displayShoppingCart.tpl` esté directamente en `views/templates/front/` y sea utilizado por el hook.
-   **Plantillas de administración (`views/templates/admin/`)**:

    -   `cgma/admin.tpl`
        -   **Alcance:** Configuración del Back-office.
        -   **Detalles:** Esta plantilla es renderizada por el método `getContent()` de la clase principal del módulo (`cgma.php`). Contiene la estructura HTML para el formulario de configuración del módulo, incluyendo campos de entrada para la configuración general (excluir grupos, inclusión de impuestos/envío, solo primer pedido) y campos dinámicos para establecer valores mínimos de pedido para cada grupo de clientes.
-   **Plantillas del Front-office (`views/templates/front/`)**:

    -   `cgma/views/templates/front/displayShoppingCart.tpl`
        -   **Alcance:** Front-office, específicamente la página del carrito de compras.
        -   **Detalles:** Esta plantilla probablemente se renderiza cuando el módulo se engancha a `displayShoppingCart`. Muestra el mensaje de advertencia al cliente si el total de su carrito no cumple con el valor mínimo de pedido para su grupo. También podría contener lógica para deshabilitar el botón "Proceder al Pago" o proporcionar instrucciones sobre cómo cumplir el mínimo.

### 4.7 Esquema de Base de Datos y Mapa de Hooks

-   **Tablas de Base de Datos**:

    -   El módulo no crea tablas SQL personalizadas.
    -   La configuración se almacena en la tabla `ps_configuration` utilizando claves como `CGMA_EXCV`, `CGMA_TAX`, `CGMA_FREE`, `CGMA_FIRST_ORDER` y `CGMA_[GROUP_ID]_[CURRENCY_ID]` para los valores mínimos por grupo y moneda. También se hace referencia a `PS_CURRENCY_DEFAULT`.
-   **Tabla de Hooks Registrados**:

| Nombre del Hook | Momento de Ejecución | Propósito Técnico |
| --- | --- | --- |
| `stepBeforePaymentOPC` | Antes del paso de pago en el Proceso de Pago en Una Página (OPC). | Impide que los clientes procedan al pago si no se cumple el valor mínimo del pedido. |
| `displayPaymentTop` | En la parte superior de la sección de opciones de pago durante el proceso de compra. | Muestra un mensaje de advertencia si no se cumple el valor mínimo del pedido. |
| `displaystepBeforePaymentOPC` | Similar a `stepBeforePaymentOPC`, a menudo utilizado para mostrar contenido o comprobaciones adicionales. | Asegura que se cumpla el valor mínimo del pedido antes del pago, mostrando potencialmente un mensaje. |
| `displayShoppingCart` | En la página de resumen del carrito de compras. | Valida el total del carrito y muestra un mensaje de advertencia si no se cumple el mínimo, deshabilitando potencialmente los botones de pago. |
| `displayHeader` | En la sección `<head>` de cada página del front-office. | Inyecta los archivos CSS (`cgma.css`) y JavaScript (`cgma.js`) necesarios para la funcionalidad y el estilo del front-office. |

## 5. Soporte Oficial y Actualizaciones

Para actualizaciones oficiales, soporte técnico y para acceder a las últimas versiones del módulo "Valor mínimo de pedido por grupo de clientes", visite su cuenta de cliente en [MyPresta.eu](https://mypresta.eu/). Nuestro equipo de soporte está disponible para ayudarle con cualquier problema o pregunta que pueda tener.
