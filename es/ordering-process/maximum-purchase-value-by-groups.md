---
title: "Valor máximo de compra por grupos - Manual de Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop 'Valor máximo de compra por grupos' de MyPresta.eu."
sidebar:
  label: "Valor máximo de compra por grupos - Manual de Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Maximum purchase value by groups en MyPresta.eu](https://mypresta.eu/modules/ordering-process/maximum-purchase-value-by-groups.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/ordering-process/maximum-purchase-value-by-groups/)
>
> ---


# Valor máximo de compra por grupos

## 1. Requisitos y compatibilidad

- **Versiones de PrestaShop compatibles**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilidad con PHP**: PHP 7.1 - 8.5
- **Requisitos de alojamiento**: Extensiones PHP estándar (cURL, JSON, OpenSSL).

## 2. Recorrido completo de la configuración (Cada ajuste agrupado por pantalla)

### 2.1 Página de configuración del módulo (Back Office > Módulos > Configurar)

Después de instalar el módulo, navegue a **Módulos > Gestor de módulos** y busque "Valor máximo de compra por grupos". Haga clic en el botón "Configurar" para acceder a sus ajustes.

La página de configuración mostrará una lista de todos sus grupos de clientes, permitiéndole establecer un valor máximo de compra para cada uno.

#### **Ajuste: Valor máximo de compra para [Nombre del Grupo de Clientes]**

- **Qué hace este ajuste:** Este campo de entrada le permite definir el valor total de pedido más alto (incluyendo o excluyendo impuestos, dependiendo del ajuste "Aplicar impuestos al valor máximo de compra") que los clientes pertenecientes a un grupo específico pueden realizar.
- **Efecto de cambiar este ajuste:**
  - *Cuando se introduce un valor (por ejemplo, 500):* Los clientes de este grupo no podrán completar un pedido si el total de su carrito excede esta cantidad. Aparecerá un mensaje de advertencia en el carrito y en la caja.
  - *Cuando se deja vacío o se establece en 0:* No habrá un límite de valor máximo de compra para este grupo de clientes específico. Pueden pedir cualquier cantidad.
- **Valor recomendado:** Esto depende completamente de su modelo de negocio y segmentación de clientes.
  - Para **Grupos Mayoristas**, puede establecer un límite alto (por ejemplo, 5000) o dejarlo vacío si confía en ellos.
  - Para **Grupos de Nuevos Clientes**, puede establecer un límite inferior (por ejemplo, 200) para gestionar el riesgo.
  - Para **Grupos de Clientes Predeterminados**, puede dejarlo vacío a menos que tenga una razón específica para limitar a los clientes generales.
- **Escenario / ejemplo de comerciante:** Tiene un grupo "Mayorista Nivel 1". Quiere asegurarse de que ningún pedido individual de este grupo exceda los 10.000 € sin aprobación previa. Introduciría `10000` en el campo junto a "Mayorista Nivel 1". Si un cliente de este grupo intenta pedir 10.001 €, será bloqueado.

#### **Ajuste: Aplicar impuestos al valor máximo de compra**

- **Qué hace este ajuste:** Este interruptor determina si el valor máximo de compra que establece para cada grupo debe calcularse en función del total del carrito *incluyendo* impuestos o *excluyendo* impuestos.
- **Efecto de cambiar este ajuste:**
  - *Cuando está habilitado (SÍ):* El módulo comparará el total del carrito del cliente *incluyendo todos los impuestos aplicables* con el valor máximo que ha definido. Así es generalmente como los clientes perciben su costo total.
  - *Cuando está deshabilitado (NO):* El módulo comparará el total del carrito del cliente *excluyendo impuestos* con el valor máximo que ha definido. Esto podría ser útil si su contabilidad interna o acuerdos mayoristas se basan en valores antes de impuestos.
- **Valor recomendado:** **SÍ**. La mayoría de los comerciantes y clientes piensan en términos del precio final, incluyendo impuestos. Habilitar esto asegura que el límite se aplique a la cantidad real que el cliente pagará.
- **Escenario / ejemplo de comerciante:** Establece un valor máximo de 500 € para un grupo.
  - Si "Aplicar impuestos" es SÍ: Se permitirá a un cliente con un total de carrito de 450 € (productos) + 50 € (impuestos) = 500 €. Un carrito de 460 € (productos) + 50 € (impuestos) = 510 € será bloqueado.
  - Si "Aplicar impuestos" es NO: Se permitirá a un cliente con un total de carrito de 500 € (productos) + 50 € (impuestos) = 550 € porque el total de productos es exactamente 500 €.

#### **Ajuste: Mostrar mensaje sobre limitaciones**

- **Qué hace este ajuste:** Este interruptor controla si el mensaje informativo sobre la superación del valor máximo de compra se muestra al cliente en el front-office.
- **Efecto de cambiar este ajuste:**
  - *Cuando está habilitado (SÍ):* Los clientes verán un mensaje claro y fácil de usar en las páginas del carrito y de pago si el total de su pedido excede el límite para su grupo. Esto les ayuda a entender por qué no pueden continuar.
  - *Cuando está deshabilitado (NO):* La limitación seguirá aplicándose (se bloqueará a los clientes para que no realicen pedidos), pero no se mostrará ningún mensaje explícito. Esto puede generar confusión y una mala experiencia para el cliente, ya que no sabrán *por qué* no pueden completar su pedido.
- **Valor recomendado:** **SÍ**. Informe siempre a sus clientes claramente. Ocultar el mensaje solo generará frustración y tickets de soporte.
- **Escenario / ejemplo de comerciante:** Un cliente intenta pedir demasiado. Si esto está habilitado, verá "Su pedido excede el valor máximo permitido para su grupo de clientes (500 €). Reduzca el total de su carrito para continuar". Si está deshabilitado, solo verá un error o el botón "Ir a la caja" permanecerá inactivo sin explicación.

#### **Ajuste: Mensaje a mostrar**

- **Qué hace este ajuste:** Esta área de texto le permite personalizar el mensaje que ven los clientes cuando exceden el valor máximo de compra de su grupo. Puede hacerlo más específico para la marca o las políticas de su tienda.
- **Efecto de cambiar este ajuste:**
  - *Cuando se introduce un mensaje personalizado:* Este mensaje se mostrará a los clientes en lugar del mensaje predeterminado del módulo. Puede usar HTML para un formato básico.
  - *Cuando se deja vacío:* El módulo mostrará un mensaje genérico predeterminado (por ejemplo, "Su pedido excede el valor máximo permitido para su grupo de clientes.").
- **Valor recomendado:** Personalícelo para que sea amigable y útil. Incluya marcadores de posición como `{max_value}` y `{currency_sign}` si el módulo los admite (verifique el comportamiento real del módulo, ya que este módulo específico podría no usar marcadores de posición directamente, sino que inserta el valor dinámicamente). Un buen valor predeterminado suele ser suficiente.
- **Escenario / ejemplo de comerciante:** En lugar de un mensaje genérico, es posible que desee decir: "Estimado cliente, el total de su pedido actual excede el valor máximo de compra permitido de {max_value} {currency_sign} para su tipo de cuenta. Ajuste su carrito o póngase en contacto con nuestro equipo de ventas para pedidos más grandes."

Recuerde hacer clic en el botón **"Guardar"** en la parte inferior de la página de configuración después de realizar cualquier cambio.

### 2.2 Tabla de referencia rápida de configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| Configuración del módulo | Valor máximo de compra para [Nombre del Grupo] | Vacío / Varía | Establece el límite superior de gasto para un grupo de clientes específico. Vacío significa sin límite. |
| Configuración del módulo | Aplicar impuestos al valor máximo de compra | SÍ | Determina si el límite se aplica al total del carrito con o sin impuestos. Recomendado: SÍ (precio final). |
| Configuración del módulo | Mostrar mensaje sobre limitaciones | SÍ | Controla si los clientes ven una explicación cuando son bloqueados. Recomendado: SÍ (para mayor claridad). |
| Configuración del módulo | Mensaje a mostrar | Mensaje predeterminado | Personaliza el mensaje de advertencia que se muestra a los clientes. |

## 3. Solución de problemas del comerciante y preguntas frecuentes (FAQ)

**P: He establecido un límite, pero los clientes aún pueden pedir más. ¿Qué está mal?**
R:

1. **Verifique el grupo del cliente:** Asegúrese de que el cliente con el que está probando realmente pertenece al grupo para el que ha establecido el límite.
2. **Configuración de "Aplicar impuestos":** Verifique si la configuración "Aplicar impuestos al valor máximo de compra" está configurada correctamente. Si su límite es 500 y está configurado en "NO" (excluir impuestos), un cliente podría pedir 500 en productos + impuestos, lo que parece exceder los 500.
3. **Módulo habilitado:** Asegúrese de que el módulo esté realmente habilitado en su Gestor de módulos.
4. **Caché:** Borre la caché de PrestaShop (Parámetros avanzados > Rendimiento > Borrar caché) y la caché de su navegador.

**P: El mensaje sobre la limitación no se muestra, pero los clientes siguen bloqueados.**
R: Verifique la configuración "Mostrar mensaje sobre limitaciones" en la configuración del módulo. Asegúrese de que esté configurada en "SÍ". Si está configurada en "NO", el módulo aplicará el límite en silencio, lo que puede ser confuso para los clientes.

**P: ¿Puedo establecer diferentes mensajes para diferentes grupos de clientes?**
R: No, el módulo actualmente utiliza una única configuración de "Mensaje a mostrar" que se aplica a todos los grupos. Si necesita mensajes específicos para cada grupo, esto requeriría un desarrollo personalizado.

**P: ¿Este módulo afecta los descuentos o los gastos de envío?**
R: El módulo normalmente evalúa el *total final del carrito* en el momento de la compra, que generalmente incluye descuentos, gastos de envío e impuestos (dependiendo de su configuración de "Aplicar impuestos"). Por lo tanto, el límite se aplica a la cantidad final que se espera que pague el cliente.

**P: Mi tema personalizado no muestra el mensaje correctamente.**
R: Esto puede ocurrir si su tema tiene plantillas de carrito o de pago muy personalizadas.

1. **Borrar caché de Smarty:** Vaya a **Parámetros avanzados > Rendimiento**, establezca "Compilación de plantillas" en "Forzar compilación" y "Caché" en "No", luego borre la caché. Pruebe de nuevo. Revierta la configuración después.
2. **Conflicto de CSS:** El CSS de su tema podría estar anulando el estilo del módulo. Es posible que necesite un desarrollador web para inspeccionar el elemento y aplicar CSS personalizado para asegurarse de que el mensaje sea visible y tenga el estilo correcto.
3. **Problema de hook:** Asegúrese de que su tema llama correctamente a los hooks estándar de PrestaShop donde el módulo inyecta su contenido (por ejemplo, `displayShoppingCart`, `displayPaymentTop`).

## 4. Guía para desarrolladores y webmasters (Arquitectura técnica y mapa de código)

Esta sección es estrictamente para desarrolladores, webmasters de tiendas y agencias técnicas que mantienen o extienden la tienda.

### 4.1 Resumen de la arquitectura

El módulo `Maximum purchase value by groups` (`cgmaxa`) es un módulo estándar de PrestaShop que implementa el patrón MVC. Opera principalmente enganchándose a eventos clave del front-office durante el proceso de carrito y pago para validar el total actual del carrito contra los límites específicos del grupo almacenados en la tabla `ps_configuration`. Utiliza un controlador frontal para las solicitudes AJAX para proporcionar retroalimentación dinámica y una clase de módulo principal para la configuración y el registro de hooks.

### 4.2 Controladores (`controllers/`)

#### Controladores de Front-Office

- `cgmaxa/controllers/front/ajax.php`
  - **Nombre de la clase**: `CgmaxaAjaxModuleFrontController` (extiende `ModuleFrontController`)
  - **Responsabilidad**: Este controlador maneja las solicitudes AJAX desde el front-office, probablemente para la validación en tiempo real del total del carrito a medida que se añaden/eliminan elementos o durante los pasos de pago. Normalmente recibiría datos del carrito, realizaría la verificación del límite y devolvería una respuesta JSON indicando si se excede el límite y el mensaje relevante.
- `cgmaxa/controllers/front/index.php`
  - **Nombre de la clase**: `CgmaxaIndexModuleFrontController` (extiende `ModuleFrontController`)
  - **Responsabilidad**: Este controlador podría ser un marcador de posición o usarse para un enrutamiento específico que no encaja en el despacho principal del módulo. Dado su nombre, podría ser un punto de entrada predeterminado o manejar interacciones del front-office que no sean AJAX si el módulo tuviera una página dedicada, aunque su función principal para este módulo es probablemente mínima o para casos de respaldo.

#### Controladores de administración de Back-Office

Este módulo no parece utilizar ningún controlador de administración dedicado. Toda la configuración se maneja directamente dentro del método `getContent()` del módulo principal.

### 4.3 Clases y modelos principales (`classes/`)

Este módulo no parece definir ninguna clase personalizada u `ObjectModel` en un directorio `classes/`. Toda la lógica está encapsulada dentro del archivo principal del módulo (`cgmaxa.php`) y sus controladores. Los valores de configuración se almacenan directamente en `ps_configuration`.

### 4.4 Activos JavaScript (`views/js/`)

- `cgmaxa/views/js/cgmaxa.js`
  - **Alcance**: Front-office.
  - **Detalles**: Este script es responsable de las interacciones del lado del cliente. Probablemente se vincula a eventos como cambios de cantidad en el carrito, adición/eliminación de productos o navegación a través de los pasos de pago. Enviaría solicitudes AJAX a `cgmaxa/controllers/front/ajax.php` para validar el total del carrito en tiempo real. Al recibir una respuesta, mostraría dinámicamente el mensaje de advertencia (si se excede el límite) y potencialmente deshabilitaría los botones "Ir a la caja" o "Pago" para evitar la finalización del pedido. También podría actualizar el mensaje dinámicamente con el valor actual del carrito y el valor máximo permitido.

### 4.5 Hojas de estilo CSS (`views/css/`)

- `cgmaxa/css.css`
  - **Alcance**: Front-office.
  - **Detalles**: Esta hoja de estilo proporciona el estilo básico para el mensaje de advertencia que se muestra a los clientes cuando exceden el límite de compra. Probablemente define clases para el contenedor del mensaje, el color del texto, el fondo y posiblemente iconos para que la alerta se destaque. Los desarrolladores pueden anular estos estilos en el `custom.css` de su tema o utilizando selectores más específicos.
- `cgmaxa/views/css/cgmaxa.css`
  - **Alcance**: Front-office.
  - **Detalles**: Similar a `cgmaxa/css.css`, este archivo proporciona estilo para los elementos del front-office. Podría contener estilos más específicos o actualizados en comparación con `cgmaxa/css.css`, o uno podría ser un archivo heredado. Los desarrolladores deben inspeccionar ambos para comprender el estilo completo aplicado. Los selectores clave apuntarían al contenedor del mensaje y su contenido.

### 4.6 Estructura de la plantilla Smarty (`views/templates/`)

#### Plantillas de hook (`views/templates/hook/`)

- `cgmaxa/views/templates/front/displayShoppingCart.tpl`
  - **Hook**: `displayShoppingCart` (y potencialmente `displayPaymentTop`, `stepBeforePaymentOPC`, `displaystepBeforePaymentOPC`).
  - **Salida**: Esta plantilla es responsable de renderizar el mensaje de advertencia en la página del carrito de compras y potencialmente en otros pasos de pago. Contendría la estructura HTML para el cuadro de alerta, insertando dinámicamente el mensaje personalizado y el valor máximo permitido si se excede el límite. Probablemente utiliza variables Smarty pasadas desde los métodos de hook del módulo para determinar si el mensaje debe mostrarse y qué contenido debe contener.

#### Plantillas de administración (`views/templates/admin/`)

- `cgmaxa/admin.tpl`
  - **Alcance**: Configuración del Back-office.
  - **Salida**: Esta plantilla es utilizada por el método `getContent()` del módulo para renderizar el formulario de configuración en el Back Office de PrestaShop. Incluye los campos de entrada para el valor máximo de cada grupo de clientes, el interruptor "Aplicar impuestos", el interruptor "Mostrar mensaje" y el área de texto del mensaje personalizado. Itera a través de los grupos de clientes disponibles para crear los campos de entrada dinámicos.

### 4.7 Esquema de la base de datos y mapa de hooks

#### Tablas de la base de datos

El módulo no crea ninguna tabla de base de datos personalizada. Todas las configuraciones (valores máximos por grupo, configuración de impuestos, visualización de mensajes, mensaje personalizado) se almacenan en la tabla `ps_configuration` utilizando claves como `CGMAXA_GROUP_[ID_GROUP]`, `CGMAXA_TAX`, `CGMAXA_DISPLAY_MESSAGE`, `CGMAXA_MESSAGE`.

#### Tabla de Hooks registrados

| Nombre del Hook | Momento de Ejecución | Propósito Técnico |
| --- | --- | --- |
| `displayHeader` | En la sección `<head>` de cada página del front-office. | Para incluir los archivos CSS y JavaScript necesarios (`cgmaxa.js`, `cgmaxa.css`) para la funcionalidad del front-office y la validación AJAX. |
| `displayShoppingCart` | En la página de resumen del carrito de compras. | Para mostrar el mensaje de advertencia si el total del carrito excede el límite del grupo y potencialmente deshabilitar el botón "Ir a la caja". |
| `displayPaymentTop` | En la parte superior del paso de selección de pago en el proceso de pago. | Para revalidar el total del carrito antes del pago y mostrar el mensaje de advertencia, bloqueando el progreso si se excede el límite. |
| `stepBeforePaymentOPC` | Antes del paso de pago en el Pago en una página (OPC). | Similar a `displayPaymentTop`, este hook asegura que la validación ocurra justo antes de que el cliente pueda seleccionar un método de pago, crucial para los flujos de OPC. |
| `displaystepBeforePaymentOPC` | Otro hook relacionado con el paso anterior al pago en OPC. | Proporciona un punto adicional para la validación y la visualización de mensajes en temas o configuraciones de OPC específicos. |

## 5. Soporte oficial y actualizaciones

Para obtener las últimas actualizaciones, correcciones de errores y soporte oficial para el módulo "Valor máximo de compra por grupos", consulte su cuenta de cliente en [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nuestro equipo de soporte está disponible para ayudarle con cualquier problema o pregunta que pueda tener con respecto a la funcionalidad y configuración del módulo.
