---
title: "Transferencia bancaria con resumen de pedido - Manual de comerciante y guía de configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop 'Transferencia bancaria con resumen de pedido' de MyPresta.eu."
sidebar:
  label: "Transferencia bancaria con resumen de pedido - Manual de comerciante y guía de configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Bank wire with order summary en MyPresta.eu](https://mypresta.eu/modules/payment-process/bank-wire-with-order-summary.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/payment/bank-wire-with-order-summary/)
>
> ---


# Transferencia bancaria con resumen de pedido

## 1. Requisitos y compatibilidad

- **Versiones de PrestaShop compatibles**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilidad con PHP**: PHP 5.6 - 8.5
- **Requisitos de alojamiento**: Las extensiones PHP estándar (cURL, JSON, OpenSSL) suelen ser requeridas por PrestaShop y normalmente están disponibles en la mayoría de los entornos de alojamiento. No se necesitan extensiones inusuales específicas para este módulo.

## 2. Recorrido completo por la configuración (Cada ajuste agrupado por pantalla)

### 2.1 Página de configuración del módulo (Back Office > Módulos > Configurar)

Esta es la pantalla de configuración principal donde define los detalles de su cuenta bancaria y cómo se comporta el método de pago por transferencia bancaria en su tienda.

#### **Configuración de la cuenta de transferencia bancaria**

Esta sección le permite definir múltiples perfiles de cuenta bancaria. Cada perfil puede tener sus propios detalles y puede activarse o desactivarse de forma independiente. Esto es útil si tiene diferentes cuentas bancarias para diferentes monedas, países o incluso diferentes marcas.

- **Nombre del perfil:**

  - **Qué hace este ajuste:** Este es un nombre interno para su perfil de cuenta bancaria, que le ayuda a identificarlo en el back office. No es visible para los clientes.
  - **Efecto de cambiar este ajuste:** Cambiar esto solo afecta cómo ve el perfil en el panel de administración.
  - **Valor recomendado:** Un nombre descriptivo, por ejemplo, "Cuenta principal en euros", "Cuenta en USD para pedidos de EE. UU.".
  - **Escenario / ejemplo de comerciante:** Si tiene una cuenta bancaria en Alemania para pagos en EUR y otra en EE. UU. para pagos en USD, crearía dos perfiles, nombrándolos en consecuencia.
- **Activo:**

  - **Qué hace este ajuste:** Controla si este perfil de cuenta bancaria específico está disponible como opción de pago para los clientes.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está habilitado (Sí):* Este perfil de cuenta bancaria se ofrecerá a los clientes si cumple con todos los demás criterios de elegibilidad (moneda, país, etc.).
    - *Cuando está deshabilitado (No):* Este perfil no se mostrará como opción de pago, independientemente de otras configuraciones.
  - **Valor recomendado:** "Sí" para cuentas activas, "No" para cuentas inactivas o temporales.
  - **Escenario / ejemplo de comerciante:** Podría deshabilitar un perfil si una cuenta bancaria no está disponible temporalmente o si está eliminando gradualmente una moneda en particular.
- **Prioridad:**

  - **Qué hace este ajuste:** Si varios perfiles de transferencia bancaria están activos y son elegibles para el pedido de un cliente, este número determina cuál se muestra primero o se prefiere. Los números más bajos significan mayor prioridad.
  - **Efecto de cambiar este ajuste:** Influye en el orden en que se presentan las opciones de transferencia bancaria elegibles al cliente.
  - **Valor recomendado:** Use números secuenciales (por ejemplo, 1, 2, 3) para ordenar sus preferencias.
  - **Escenario / ejemplo de comerciante:** Si prefiere que los clientes usen su cuenta principal en EUR en lugar de una secundaria, asigne a la cuenta principal un número de prioridad más bajo (por ejemplo, 1) que a la secundaria (por ejemplo, 2).
- **Moneda:**

  - **Qué hace este ajuste:** Especifica en qué moneda está configurado este perfil de cuenta bancaria para recibir pagos.
  - **Efecto de cambiar este ajuste:** Este perfil solo se ofrecerá a los clientes cuyo total de pedido esté en la moneda seleccionada.
  - **Valor recomendado:** Seleccione la moneda principal para esta cuenta bancaria.
  - **Escenario / ejemplo de comerciante:** Si tiene una cuenta bancaria que solo acepta EUR, seleccione "Euro". Si un cliente realiza un pedido en USD, este perfil no se mostrará.
- **Países elegibles:**

  - **Qué hace este ajuste:** Determina para qué países está disponible este perfil de cuenta bancaria. Puede seleccionar varios países.
  - **Efecto de cambiar este ajuste:** Este perfil solo se ofrecerá a los clientes cuya dirección de facturación se encuentre en uno de los países seleccionados.
  - **Valor recomendado:** Seleccione todos los países desde los que está dispuesto a aceptar transferencias bancarias a esta cuenta específica.
  - **Escenario / ejemplo de comerciante:** Si su cuenta bancaria alemana es solo para clientes de Alemania y Austria, seleccione "Alemania" y "Austria".
- **Zonas elegibles:**

  - **Qué hace este ajuste:** Determina para qué zonas geográficas está disponible este perfil de cuenta bancaria. Puede seleccionar varias zonas.
  - **Efecto de cambiar este ajuste:** Similar a los países, este perfil solo se ofrecerá a los clientes cuya dirección de facturación se encuentre en una de las zonas seleccionadas.
  - **Valor recomendado:** Seleccione las zonas relevantes para esta cuenta bancaria.
  - **Escenario / ejemplo de comerciante:** Si tiene una cuenta bancaria específicamente para clientes europeos, podría seleccionar la zona "Europa".
- **Grupos de clientes elegibles:**

  - **Qué hace este ajuste:** Restringe esta opción de pago a grupos de clientes específicos (por ejemplo, "Visitantes", "Invitados", "Clientes", "Mayoristas").
  - **Efecto de cambiar este ajuste:** Solo los clientes que pertenezcan a los grupos seleccionados verán esta opción de transferencia bancaria.
  - **Valor recomendado:** Normalmente "Clientes" e "Invitados", pero se puede personalizar para B2B.
  - **Escenario / ejemplo de comerciante:** Es posible que solo desee ofrecer transferencia bancaria a su grupo de "Mayoristas" para pedidos B2B grandes, y no a clientes minoristas habituales.
- **Titular de la cuenta:**

  - **Qué hace este ajuste:** El nombre completo del titular de la cuenta (el nombre de su empresa o su nombre personal) tal como aparece en la cuenta bancaria.
  - **Efecto de cambiar este ajuste:** Esta información se muestra al cliente en la página de confirmación de pago, para que sepa a quién transferir el dinero.
  - **Valor recomendado:** El nombre legal exacto de su empresa o su nombre personal.
  - **Escenario / ejemplo de comerciante:** "MyPresta.eu Sp. z o.o."
- **IBAN:**

  - **Qué hace este ajuste:** Su Número Internacional de Cuenta Bancaria. Este es un identificador de cuenta bancaria internacional estandarizado.
  - **Efecto de cambiar este ajuste:** Esta es información crucial que se muestra al cliente para realizar la transferencia bancaria.
  - **Valor recomendado:** Su IBAN completo y correcto.
  - **Escenario / ejemplo de comerciante:** "DE89370400440532013000"
- **BIC / SWIFT:**

  - **Qué hace este ajuste:** Su Código de Identificación Bancaria (BIC) o código SWIFT. Esto identifica su banco a nivel mundial.
  - **Efecto de cambiar este ajuste:** Esta es información esencial que se muestra al cliente para realizar transferencias bancarias internacionales.
  - **Valor recomendado:** Su código BIC/SWIFT completo y correcto.
  - **Escenario / ejemplo de comerciante:** "COBADEFFXXX"
- **Número de cuenta / detalles:**

  - **Qué hace este ajuste:** Su número de cuenta bancaria tradicional u otros detalles específicos requeridos por su banco o país, si el IBAN/BIC no son suficientes o aplicables.
  - **Efecto de cambiar este ajuste:** Esta información se muestra al cliente.
  - **Valor recomendado:** Su número de cuenta si no se usa IBAN, o cualquier otro detalle específico. Deje en blanco si IBAN/BIC son suficientes.
  - **Escenario / ejemplo de comerciante:** En algunos países, un número de cuenta local aún podría ser preferido junto con o en lugar del IBAN.
- **Dirección del banco / titular:**

  - **Qué hace este ajuste:** La dirección de su banco o la dirección registrada del titular de la cuenta.
  - **Efecto de cambiar este ajuste:** Esta información se muestra al cliente, a veces requerida para transferencias bancarias.
  - **Valor recomendado:** La dirección completa de su sucursal bancaria o la dirección registrada de su empresa.
  - **Escenario / ejemplo de comerciante:** "Banco de Ejemplo, Calle Principal 123, 10001 Ciudad, País"
- **Instrucciones adicionales:**

  - **Qué hace este ajuste:** Un campo de texto donde puede proporcionar notas adicionales para el cliente con respecto a la transferencia bancaria (por ejemplo, "Por favor, incluya su número de referencia de pedido en la descripción de la transferencia", "Los pagos suelen tardar de 1 a 3 días hábiles en compensarse").
  - **Efecto de cambiar este ajuste:** Este texto se mostrará al cliente en la página de confirmación de pago.
  - **Valor recomendado:** Instrucciones claras y concisas para ayudar a los clientes a completar la transferencia correctamente.
  - **Escenario / ejemplo de comerciante:** "Importante: Utilice su ID de pedido # [ORDER\_ID] como referencia de pago para garantizar un procesamiento rápido."

#### **Restricciones del total del carrito**

Estos ajustes le permiten controlar los valores mínimos y máximos del pedido para los cuales la opción de pago por transferencia bancaria está disponible.

- **Total mínimo del carrito:**

  - **Qué hace este ajuste:** Habilita o deshabilita la restricción del total mínimo del carrito para este método de pago.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está habilitado:* El campo "Valor total mínimo del carrito" se activa, y la transferencia bancaria solo estará disponible para pedidos superiores a ese valor.
    - *Cuando está deshabilitado:* No se aplica ninguna restricción de total mínimo del carrito.
  - **Valor recomendado:** "Habilitado" si desea establecer un mínimo, "Deshabilitado" en caso contrario.
  - **Escenario / ejemplo de comerciante:** Podría habilitar esto si las transferencias bancarias son más rentables para pedidos grandes, o para desalentar las transferencias bancarias para compras muy pequeñas.
- **Valor total mínimo del carrito:**

  - **Qué hace este ajuste:** El valor monetario real que el carrito del cliente debe exceder para que aparezca la opción de transferencia bancaria.
  - **Efecto de cambiar este ajuste:** Si el total del carrito del cliente es inferior a este valor, la opción de transferencia bancaria no se mostrará.
  - **Valor recomendado:** Un mínimo razonable, por ejemplo, "50.00".
  - **Escenario / ejemplo de comerciante:** Establezca en "50.00" si solo desea ofrecer transferencia bancaria para pedidos de 50 € o más.
- **Total máximo del carrito:**

  - **Qué hace este ajuste:** Habilita o deshabilita la restricción del total máximo del carrito para este método de pago.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está habilitado:* El campo "Valor total máximo del carrito" se activa, y la transferencia bancaria solo estará disponible para pedidos inferiores a ese valor.
    - *Cuando está deshabilitado:* No se aplica ninguna restricción de total máximo del carrito.
  - **Valor recomendado:** "Habilitado" si desea establecer un máximo, "Deshabilitado" en caso contrario.
  - **Escenario / ejemplo de comerciante:** Podría habilitar esto si prefiere otros métodos de pago (como negociación directa o facturación personalizada) para pedidos extremadamente grandes.
- **Valor total máximo del carrito:**

  - **Qué hace este ajuste:** El valor monetario real que el carrito del cliente debe ser inferior para que aparezca la opción de transferencia bancaria.
  - **Efecto de cambiar este ajuste:** Si el total del carrito del cliente es superior a este valor, la opción de transferencia bancaria no se mostrará.
  - **Valor recomendado:** Un máximo razonable, por ejemplo, "5000.00".
  - **Escenario / ejemplo de comerciante:** Establezca en "5000.00" si no desea aceptar transferencia bancaria para pedidos que superen los 5000 €.

#### **Visualización del resumen del pedido**

Estos ajustes controlan qué información se muestra al cliente en la página de confirmación de pago antes de que finalice su pedido. Esto es crucial para el cumplimiento legal.

- **Resumen del pedido antes de la confirmación:**

  - **Qué hace este ajuste:** Controla si se muestra un resumen detallado del pedido al cliente en la página de confirmación de pago.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está habilitado:* Se mostrará un resumen de productos, precios y totales.
    - *Cuando está deshabilitado:* No se mostrará el resumen detallado, lo que podría afectar el cumplimiento legal en algunas regiones.
  - **Valor recomendado:** "Habilitado" para garantizar el cumplimiento legal y la claridad del cliente.
  - **Escenario / ejemplo de comerciante:** Mantenga siempre esto habilitado para proporcionar total transparencia a sus clientes antes de que se comprometan con la compra.
- **Mostrar resumen del cliente antes de la confirmación:**

  - **Qué hace este ajuste:** Controla si se muestra el resumen de la dirección de facturación y envío del cliente en la página de confirmación de pago.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está habilitado:* Se mostrarán los detalles de la dirección del cliente.
    - *Cuando está deshabilitado:* No se mostrarán los detalles de la dirección.
  - **Valor recomendado:** "Habilitado" para una transparencia total.
  - **Escenario / ejemplo de comerciante:** Habilitar esto permite a los clientes verificar su información de entrega por última vez antes de realizar el pedido.

#### **Análisis avanzado (Interno)**

Estos ajustes son típicamente para análisis e informes internos del módulo, sin afectar directamente la experiencia del cliente en el front-office.

- **BANKWIREPRO\_ANALYTICS\_DEFAULT\_CHART, BANKWIREPRO\_ANALYTICS\_PERIOD, BANKWIREPRO\_ANALYTICS\_CHART\_WEEKS, BANKWIREPRO\_ANALYTICS\_CHART\_MONTHS, BANKWIREPRO\_ANALYTICS\_CHART\_YEARS:**
  - **Qué hacen estos ajustes:** Estos son valores de configuración internos relacionados con cómo el módulo podría rastrear o mostrar estadísticas de pago dentro del back office de PrestaShop (si dicha característica está implementada). Definen tipos de gráficos predeterminados, períodos de informe y marcos de tiempo para el análisis.
  - **Efecto de cambiar estos ajustes:** Estos no afectan el proceso de pago orientado al cliente. Podrían influir en cómo se presentan los datos en un panel de análisis interno, si está disponible.
  - **Valor recomendado:** Dejar como predeterminado a menos que el soporte lo indique específicamente.
  - **Escenario / ejemplo de comerciante:** No aplicable directamente a la toma de decisiones del comerciante para el procesamiento de pagos.

#### **Configuración de idioma (Interno)**

- **PS\_LANG\_DEFAULT, PS\_BO\_ALLOW\_EMPLOYEE\_FORM\_LANG:**

  - **Qué hacen estos ajustes:** Estas son variables de configuración estándar de PrestaShop que determinan el idioma predeterminado de su tienda y si los empleados pueden cambiar el idioma de los formularios del back office. Se muestran aquí como referencia, pero no son específicas de este módulo.
  - **Efecto de cambiar estos ajustes:** Los cambios en estos se realizarían en la configuración general de PrestaShop, no aquí. Influyen en el idioma predeterminado para los campos de texto en el back office.
  - **Valor recomendado:** El idioma predeterminado de su tienda.
  - **Escenario / ejemplo de comerciante:** Si el idioma principal de su tienda es el español, `PS_LANG_DEFAULT` se establecería en el ID del idioma español.
- **PS\_CURRENCY\_DEFAULT:**

  - **Qué hace este ajuste:** Esta es la moneda predeterminada de su tienda PrestaShop. Se muestra aquí como referencia.
  - **Efecto de cambiar este ajuste:** Esta es una configuración global de PrestaShop. Cambiarla afectaría todos los precios y la visualización de la moneda en su tienda.
  - **Valor recomendado:** La moneda operativa principal de su tienda.
  - **Escenario / ejemplo de comerciante:** Si su tienda opera principalmente en euros, esto se establecería en "Euro".

### 2.2 Tabla de referencia rápida de configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e impacto |
| --- | --- | --- | --- |
| Configuración del módulo | Nombre del perfil | Nombre descriptivo | Identificación interna de la cuenta bancaria. |
| Configuración del módulo | Activo | Sí | Habilita/deshabilita este perfil de cuenta bancaria para uso del cliente. |
| Configuración del módulo | Prioridad | 1 (o secuencial) | Ordena la visualización de múltiples opciones de transferencia bancaria elegibles. |
| Configuración del módulo | Moneda | Moneda de su tienda | Restringe el perfil a pedidos en esta moneda. |
| Configuración del módulo | Países elegibles | Todos los países | Restringe el perfil a clientes de los países seleccionados. |
| Configuración del módulo | Zonas elegibles | Todas las zonas | Restringe el perfil a clientes de las zonas seleccionadas. |
| Configuración del módulo | Grupos de clientes elegibles | Todos los grupos | Restringe el perfil a los grupos de clientes seleccionados. |
| Configuración del módulo | Titular de la cuenta | Su empresa/nombre | Se muestra al cliente para la transferencia bancaria. |
| Configuración del módulo | IBAN | Su IBAN | Se muestra al cliente para la transferencia bancaria. |
| Configuración del módulo | BIC / SWIFT | Su BIC/SWIFT | Se muestra al cliente para la transferencia bancaria internacional. |
| Configuración del módulo | Número de cuenta / detalles | (Opcional) | Detalles bancarios adicionales para el cliente. |
| Configuración del módulo | Dirección del banco / titular | Dirección de su banco/empresa | Se muestra al cliente para la transferencia bancaria. |
| Configuración del módulo | Instrucciones adicionales | Instrucciones claras | Notas adicionales para el cliente (por ejemplo, número de referencia). |
| Configuración del módulo | Total mínimo del carrito | Deshabilitado | Habilita/deshabilita la restricción de valor mínimo del pedido. |
| Configuración del módulo | Valor total mínimo del carrito | 0.00 | Valor mínimo del pedido para que la transferencia bancaria esté disponible. |
| Configuración del módulo | Total máximo del carrito | Deshabilitado | Habilita/deshabilita la restricción de valor máximo del pedido. |
| Configuración del módulo | Valor total máximo del carrito | 0.00 | Valor máximo del pedido para que la transferencia bancaria esté disponible. |
| Configuración del módulo | Resumen del pedido antes de la confirmación | Habilitado | Muestra un resumen detallado del producto en la página de confirmación. |
| Configuración del módulo | Mostrar resumen del cliente antes de la confirmación | Habilitado | Muestra el resumen de la dirección del cliente en la página de confirmación. |
| Configuración del módulo | BANKWIREPRO\_ANALYTICS\_\* | Predeterminado | Ajustes de análisis internos (sin impacto en el front-office). |
| Configuración del módulo | PS\_LANG\_DEFAULT | Predeterminado de la tienda | Configuración de idioma predeterminada de PrestaShop. |
| Configuración del módulo | PS\_BO\_ALLOW\_EMPLOYEE\_FORM\_LANG | Predeterminado de la tienda | Configuración de idioma del formulario de empleado de PrestaShop. |
| Configuración del módulo | PS\_CURRENCY\_DEFAULT | Predeterminado de la tienda | Configuración de moneda predeterminada de PrestaShop. |

## 3. Solución de problemas para comerciantes y preguntas frecuentes (FAQ)

**P1: ¿Por qué la opción de Transferencia Bancaria no aparece para mis clientes?**
R1: Verifique los siguientes ajustes en la configuración del módulo:
\* El interruptor **"Activo"** para el perfil de la cuenta bancaria: Asegúrese de que esté configurado en "Sí".
\* **"Moneda"**: ¿Coincide la moneda del pedido del cliente con la moneda del perfil?
\* **"Países elegibles" / "Zonas elegibles"**: ¿Está incluido el país/zona de la dirección de facturación del cliente?
\* **"Grupos de clientes elegibles"**: ¿Se permite al grupo del cliente utilizar este método de pago?
\* **"Total mínimo del carrito" / "Total máximo del carrito"**: ¿El valor del carrito del cliente se encuentra dentro del rango permitido?
\* **Caché de PrestaShop**: A veces, borrar la caché de Smarty (Parámetros avanzados > Rendimiento > Borrar caché) puede resolver problemas de visualización.

**P2: Mis datos bancarios son incorrectos o están desactualizados. ¿Cómo los cambio?**
R2: Vaya a **Módulos > Gestor de módulos**, busque "Transferencia bancaria con resumen de pedido" y haga clic en "Configurar". Verá sus perfiles de cuenta bancaria existentes. Haga clic en el botón "Editar" (icono de lápiz) junto al perfil que desea actualizar, modifique los campos "Titular de la cuenta", "IBAN", "BIC / SWIFT", etc., y luego guarde sus cambios.

**P3: El resumen del pedido no aparece en la página de confirmación. ¿Hay algo mal?**
R3: Asegúrese de que los ajustes "Resumen del pedido antes de la confirmación" y "Mostrar resumen del cliente antes de la confirmación" estén ambos configurados en "Habilitado" en la configuración del módulo. Si lo están, y ha borrado la caché de PrestaShop, podría haber un conflicto de tema. Pruebe con el tema predeterminado de PrestaShop para descartar esto.

**P4: ¿Puedo ofrecer diferentes cuentas bancarias para diferentes tipos de clientes o productos?**
R4: ¡Sí, absolutamente! Este módulo admite múltiples perfiles de cuenta bancaria. Puede crear perfiles separados y usar los ajustes "Grupos de clientes elegibles", "Moneda", "Países elegibles" y "Total del carrito" para definir cuándo se ofrece cada cuenta bancaria específica. Por ejemplo, una cuenta para clientes minoristas en EUR, otra para clientes mayoristas en USD.

**P5: Después de actualizar mi tema o PrestaShop, la página de transferencia bancaria se ve extraña. ¿Qué debo hacer?**
R5: Esto a menudo indica un conflicto de CSS o un problema de anulación de plantilla.
1. **Borrar caché:** Siempre comience borrando la caché de PrestaShop (Parámetros avanzados > Rendimiento).
2. **Verificar actualizaciones del módulo:** Asegúrese de tener la última versión del módulo "Transferencia bancaria con resumen de pedido" de MyPresta.eu, ya que las actualizaciones a menudo incluyen correcciones de compatibilidad.
3. **Conflicto de tema:** Si el problema persiste, cambie temporalmente al tema predeterminado de PrestaShop (por ejemplo, "Classic") para ver si el problema desaparece. Si lo hace, es probable que su tema personalizado esté anulando o entrando en conflicto con el estilo o las plantillas del módulo. Es posible que deba consultar a su desarrollador de temas o a un webmaster para ajustar el CSS o los archivos de plantilla del tema.

## 4. Guía para desarrolladores y webmasters (Arquitectura técnica y mapa de código)

Esta sección es estrictamente para desarrolladores, webmasters de tiendas y agencias técnicas que mantienen o extienden la tienda.

### 4.1 Resumen de la arquitectura

El módulo `bankwirepro` sigue la arquitectura estándar de módulos de PrestaShop, aprovechando `ModuleFrontController` para las interacciones del front-office y la clase principal `Module` para la configuración. Se integra en el flujo de pago a través de los hooks de pago (`displayPaymentOptions`, `paymentOptions`, `displayPaymentReturn`). La configuración se gestiona a través de entradas en la tabla `Configuration`, y los detalles de la cuenta bancaria se almacenan como arrays serializados o claves individuales de `Configuration`, lo que permite múltiples perfiles. La función principal del módulo es presentar los detalles bancarios y un resumen del pedido al cliente antes y después de la validación del pedido.

### 4.2 Controladores (`controllers/`)

- **Controladores del Front-Office**:
  - `controllers/front/index.php`
    - **Nombre de la clase**: `BankwireproIndexModuleFrontController` (extiende `ModuleFrontController`)
    - **Responsabilidad**: Este controlador probablemente sirve como punto de entrada predeterminado o como respaldo. En muchos módulos, los controladores `index.php` redirigen a un controlador más específico o manejan la visualización básica del módulo si no se solicita ninguna otra acción específica. Podría manejar la configuración inicial o la redirección a la selección de pago.
  - `controllers/front/payment.php`
    - **Nombre de la clase**: `BankwireproPaymentModuleFrontController` (extiende `ModuleFrontController`)
    - **Responsabilidad**: Este controlador es responsable de renderizar la página de selección de pago cuando se elige la opción de transferencia bancaria. Recopila los detalles necesarios de la cuenta bancaria en función del carrito actual, el cliente y la moneda, y los prepara para su visualización en la plantilla `payment.tpl`. Actúa como el puente entre la selección de la opción de pago y el paso de validación final.
  - `controllers/front/validation.php`
    - **Nombre de la clase**: `BankwireproValidationModuleFrontController` (extiende `ModuleFrontController`)
    - **Responsabilidad**: Este es el controlador crítico que maneja el paso final del proceso de pago por transferencia bancaria. Valida el pedido, crea el pedido en la base de datos de PrestaShop y luego renderiza la plantilla `validation.tpl`. Esta plantilla muestra el resumen completo del pedido, el resumen de la dirección del cliente y los detalles de la cuenta bancaria elegida, junto con instrucciones adicionales, antes de que el cliente sea redirigido a la página estándar de `order-confirmation`. Asegura que toda la información necesaria se presente para el cumplimiento legal.

### 4.3 Clases y modelos principales (`classes/`)

El dossier del módulo no indica clases personalizadas en `classes/`. La lógica central para manejar los perfiles de cuenta bancaria y la configuración probablemente está contenida dentro del archivo principal `bankwirepro.php`, utilizando `Configuration::get()` y `Configuration::updateValue()` para almacenar la configuración, posiblemente con arrays serializados para múltiples perfiles de cuenta bancaria.

### 4.4 Activos JavaScript (`views/js/`)

El dossier del módulo no indica archivos JavaScript personalizados. Esto sugiere que la funcionalidad del front-office del módulo se renderiza principalmente en el lado del servidor y se basa en el JavaScript estándar de PrestaShop para interacciones básicas, o que cualquier JS mínimo está en línea en las plantillas.

### 4.5 Hojas de estilo CSS (`views/css/`)

El dossier del módulo no indica archivos CSS personalizados. Esto implica que el módulo se basa completamente en el estilo del tema predeterminado de PrestaShop, o que cualquier estilo mínimo está en línea dentro de las plantillas. Los desarrolladores deben tener en cuenta que la apariencia del módulo estará dictada en gran medida por el CSS del tema activo.

### 4.6 Estructura de la plantilla Smarty (`views/templates/`)

- **Plantillas de administración (`views/templates/admin/`)**:

  - `accountSelector.tpl`: Esta plantilla probablemente se utiliza en la configuración del back-office del módulo para mostrar una lista de perfiles de cuenta bancaria configurados, permitiendo al administrador seleccionarlos, editarlos o eliminarlos. Normalmente renderizaría una tabla o lista con nombres de perfil, estado y botones de acción.
- **Plantillas del front-office (`views/templates/front/`)**:

  - `validation.tpl`: Esta es una plantilla crucial renderizada por `BankwireproValidationModuleFrontController`. Muestra el resumen completo del pedido (productos, totales), el resumen de la dirección del cliente y los detalles de la cuenta bancaria seleccionada (titular de la cuenta, IBAN, BIC/SWIFT, instrucciones) al cliente antes de que el pedido se confirme por completo. Esta plantilla es clave para el cumplimiento legal.
- **Plantillas de hook (`views/templates/hook/`)**:

  - `infos.tpl`: Esta plantilla probablemente está enganchada a `displayPaymentReturn` o un hook similar en la página `order-confirmation`. Reitera las instrucciones de pago por transferencia bancaria y los detalles bancarios después de que el pedido se haya realizado con éxito, sirviendo como recordatorio para que el cliente complete la transferencia.
  - `payment.tpl`: Esta plantilla probablemente se utiliza para el hook `displayPayment` (PrestaShop 1.6.x) o `paymentOptions` (PrestaShop 1.7+). Renderiza la opción de transferencia bancaria en la página de selección de pago durante el proceso de compra, presentándola como un método de pago disponible para el cliente.
  - `payment_return.tpl`: Similar a `infos.tpl`, esta plantilla también está probablemente enganchada a `displayPaymentReturn`. Proporciona el mensaje de confirmación final y los detalles bancarios en la página de confirmación del pedido, asegurando que el cliente tenga toda la información para proceder con la transferencia bancaria.

### 4.7 Esquema de la base de datos y mapa de Hooks

- **Tablas de la base de datos**:

  - El módulo no crea tablas SQL personalizadas. Todas las configuraciones, incluidos múltiples perfiles de cuenta bancaria, se almacenan en la tabla `ps_configuration`.
  - Claves de configuración utilizadas:
    - `BANK_WIRE_PRO_MINCART`, `BANK_WIRE_PRO_MINCART_V`, `BANK_WIRE_PRO_MAXCART`, `BANK_WIRE_PRO_MAXCART_V`: Para restricciones de total del carrito.
    - `BANK_WIRE_PRO_OWNER_`, `BANK_WIRE_PRO_DETAILS_`, `BANK_WIRE_PRO_ADDRESS_`, `BANK_WIRE_PRO_SWIFT_`, `BANK_WIRE_PRO_IBAN_`, `BANK_WIRE_PRO_MORE_`: Estos son probablemente prefijos para almacenar detalles de *cada* perfil de cuenta bancaria, posiblemente con un ID de idioma o un sufijo de ID de perfil (por ejemplo, `BANK_WIRE_PRO_OWNER_1_1` para el perfil 1, idioma 1).
    - `BANK_WIRE_PRO_OWNER_SUMMARY`, `BANK_WIRE_PRO_CSUMMARY`, `BANK_WIRE_PRO_ASUMMARY`: Para controlar la visualización de los resúmenes de pedidos y direcciones.
    - `BANKWIREPRO_ANALYTICS_*`: Configuraciones de análisis internos.
    - Las claves estándar de PrestaShop como `PS_LANG_DEFAULT`, `PS_BO_ALLOW_EMPLOYEE_FORM_LANG`, `PS_CURRENCY_DEFAULT` se leen pero no son gestionadas por el módulo.
- **Tabla de Hooks registrados**:

| Nombre del Hook | Alcance | Momento de ejecución | Propósito técnico |
| --- | --- | --- | --- |
| `displayPayment` | Front-Office | Paso de selección de pago (PrestaShop 1.6.x) | Renderiza la opción de pago por transferencia bancaria en la página de pago. |
| `paymentOptions` | Front-Office | Paso de selección de pago (PrestaShop 1.7.x, 8.x, 9.x) | Proporciona objetos `PaymentOption` para transferencia bancaria a la página de pago. |
| `displayPaymentReturn` | Front-Office | Página de confirmación del pedido (`order-confirmation`) | Muestra los detalles bancarios y las instrucciones después de la validación del pedido. |
| `displayPaymentOptions` | Front-Office | Paso de selección de pago (PrestaShop 1.7.x, 8.x, 9.x) | Hook alternativo o complementario para renderizar opciones de pago. |
| `actionPaymentConfirmation` | Back-Office | Después de que un pedido se confirma como pagado | (Implícito, común para módulos de pago) Puede actualizar el estado del pedido o realizar acciones posteriores al pago. |
| `actionValidateOrder` | Back-Office | Después de que un pedido es validado | (Implícito, común para módulos de pago) Se utiliza para establecer el estado inicial del pedido, guardar los detalles de pago. |

## 5. Soporte oficial y actualizaciones

Para obtener actualizaciones oficiales, soporte técnico y para asegurarse de que está ejecutando la versión más segura y compatible del módulo "Transferencia bancaria con resumen de pedido", consulte su cuenta de cliente en [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nuestro equipo de soporte está disponible para ayudar con cualquier problema o pregunta relacionada con la funcionalidad e integración del módulo.
