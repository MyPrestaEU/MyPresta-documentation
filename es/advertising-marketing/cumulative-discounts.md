---
title: "Descuentos acumulativos - Manual de comerciante y guía de configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop Descuentos acumulativos de MyPresta.eu."
sidebar:
  label: "Descuentos acumulativos - Manual de comerciante y guía de configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Cumulative discounts en MyPresta.eu](https://mypresta.eu/modules/advertising-and-marketing/cumulative-discounts.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/advertising-marketing/cumulative-discounts/)
>
> ---


# Descuentos acumulativos

## 1. Requisitos y compatibilidad

- **Versiones de PrestaShop compatibles**: PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilidad con PHP**: PHP 5.6 - 8.5
- **Requisitos de alojamiento**: Se requieren extensiones PHP estándar (cURL, JSON, OpenSSL), que suelen estar disponibles en la mayoría de los entornos de alojamiento compatibles con PrestaShop.

## 2. Recorrido completo por la configuración (Cada ajuste agrupado por pantalla)

### 2.1 Página de configuración del módulo (Back Office > Módulos > Configurar)

Esta es la pantalla de configuración principal donde define cómo funciona su programa de descuentos acumulativos.

#### **Activar programa**

- **Qué hace este ajuste:** Este es el interruptor principal para activar o desactivar todo el programa de descuentos acumulativos.
- **Efecto de cambiar este ajuste:**
  - *Cuando está activado:* El módulo rastreará activamente el gasto del cliente, asignará grupos y mostrará información de descuento en su front office.
  - *Cuando está desactivado:* El módulo cesará todas las operaciones, no se aplicarán descuentos y no se mostrará información.
- **Valor recomendado:** SÍ (para activar el programa).
- **Escenario / ejemplo de comerciante:** Si está configurando el módulo por primera vez, actívelo después de haber configurado todos los demás ajustes. Si necesita pausar temporalmente el programa (por ejemplo, durante una gran venta donde se aplican otros descuentos), puede desactivarlo aquí.

#### **Desactivar programa de descuentos acumulativos para grupos de clientes seleccionados**

- **Qué hace este ajuste:** Le permite seleccionar grupos de clientes específicos que *no* deben formar parte del programa de descuentos acumulativos. Los clientes de estos grupos seleccionados no recibirán descuentos acumulativos, independientemente de su gasto.
- **Efecto de cambiar este ajuste:**
  - *Cuando se selecciona un grupo:* Los clientes que pertenecen a ese grupo serán excluidos del programa.
  - *Cuando no se selecciona ningún grupo:* Todos los grupos de clientes son elegibles para el programa por defecto.
- **Valor recomendado:** Seleccione grupos como "Visitantes" o "Invitados" si solo desea que participen los clientes registrados. También podría excluir un grupo de "Mayoristas" si tienen una estructura de precios separada.
- **Escenario / ejemplo de comerciante:** Es posible que tenga un grupo de clientes "Mayoristas" que ya recibe precios especiales. Para evitar conflictos o dobles descuentos, seleccionaría el grupo "Mayoristas" aquí para excluirlos del programa de descuentos acumulativos.

#### **Marco de tiempo**

- **Qué hace este ajuste:** Define el período durante el cual se consideran los pedidos del cliente al calcular su gasto total.
- **Efecto de cambiar este ajuste:**
  - *Todos los pedidos:* Considera cada pedido realizado por el cliente.
  - *Pedidos del último año / Pedidos del último semestre / Pedidos del último trimestre / Pedidos del último mes / Pedidos de la última semana / Pedidos del último día:* Limita el cálculo a los pedidos realizados dentro del período reciente especificado.
  - *Solo el último pedido válido:* Solo considera el pedido completado más reciente.
- **Valor recomendado:** "Pedidos del último año" o "Todos los pedidos" son opciones comunes para los programas de fidelización. "Pedidos del último mes" podría usarse para un impulso de fidelización más agresivo y a corto plazo.
- **Escenario / ejemplo de comerciante:** Si desea recompensar la lealtad a largo plazo, elija "Todos los pedidos". Si desea fomentar compras recientes y frecuentes, "Pedidos del último semestre" podría ser más apropiado.

#### **Tipo de precio**

- **Qué hace este ajuste:** Determina si el cálculo del gasto acumulativo debe usar el "Precio neto" (precio antes de impuestos) o el "Precio bruto" (precio con impuestos incluidos) de los productos en los pedidos.
- **Efecto de cambiar este ajuste:**
  - *Precio neto:* El gasto total se calculará en función de los precios de los productos sin incluir impuestos.
  - *Precio bruto:* El gasto total se calculará en función de los precios de los productos con impuestos incluidos.
- **Valor recomendado:** El "Precio bruto" suele ser más intuitivo para los clientes, ya que refleja lo que realmente pagaron. Sin embargo, el "Precio neto" podría ser preferido para tiendas B2B o para la coherencia contable interna.
- **Escenario / ejemplo de comerciante:** Si su público objetivo son principalmente consumidores, usar el "Precio bruto" tiene más sentido, ya que se alinea con el precio final que ven y pagan.

#### **Seleccionar estados de pedido**

- **Qué hace este ajuste:** Le permite especificar qué estados de pedido deben incluirse al calcular el gasto total de un cliente. Solo los pedidos con estos estados seleccionados contarán para el total acumulado.
- **Efecto de cambiar este ajuste:**
  - *Cuando se seleccionan "Pago aceptado" y "Entregado":* Solo los pedidos que han sido pagados y entregados con éxito contribuirán al total de gasto del cliente.
  - *Cuando "Cancelado" o "Reembolsado" NO están seleccionados:* Estos pedidos no contarán, evitando que los clientes obtengan puntos de fidelidad por compras no completadas.
- **Valor recomendado:** Seleccione estados que indiquen una transacción completada y exitosa, como "Pago aceptado", "Entregado". Excluya estados como "Cancelado", "Reembolsado", "Error de pago", etc.
- **Escenario / ejemplo de comerciante:** Desea asegurarse de que solo las compras reales y completadas contribuyan a la fidelización. Seleccionaría "Pago aceptado" y "Entregado" para asegurarse de que los clientes solo obtengan descuentos por los pedidos que realmente han pagado y recibido.

#### **Excluir pedidos realizados con código de cupón**

- **Qué hace este ajuste:** Si está activado, los pedidos en los que se utilizó un código de cupón o vale no contarán para el total de gasto acumulado del cliente.
- **Efecto de cambiar este ajuste:**
  - *Cuando está activado:* Los pedidos con cupones se ignoran para los cálculos de fidelización.
  - *Cuando está desactivado:* Los pedidos con cupones *sí* cuentan para el total acumulado.
- **Valor recomendado:** SÍ, si desea recompensar más las compras a precio completo. NO, si desea fomentar que cualquier compra, incluso las con descuento, contribuya a la fidelización.
- **Escenario / ejemplo de comerciante:** Está ejecutando una promoción especial con un cupón del 20% de descuento. Si activa este ajuste, los clientes que utilicen ese cupón no contarán ese pedido para su progreso de descuento acumulativo, asegurando que ganen fidelidad en compras a precio completo.

#### **Excluir productos con precios específicos**

- **Qué hace este ajuste:** Si está activado, los productos que tienen un "precio específico" (por ejemplo, un precio promocional especial establecido por un tiempo limitado o para un grupo de clientes en particular) no contribuirán al cálculo del gasto acumulativo.
- **Efecto de cambiar este ajuste:**
  - *Cuando está activado:* Los productos con precios específicos se ignoran para los cálculos de fidelización.
  - *Cuando está desactivado:* Los productos con precios específicos *sí* cuentan para el total acumulado.
- **Valor recomendado:** SÍ, si desea recompensar las compras de artículos a precio regular. NO, si desea que todas las compras de productos contribuyan.
- **Escenario / ejemplo de comerciante:** Tiene una venta flash en ciertos artículos utilizando la función de precio específico de PrestaShop. Si activa esto, la compra de esos artículos en oferta no ayudará al cliente a alcanzar el siguiente nivel de fidelización, animándolos a comprar artículos a precio regular en su lugar.

#### **Excluir productos con descuentos por cantidad**

- **Qué hace este ajuste:** Si está activado, los productos que se compraron con un descuento por cantidad (por ejemplo, "Compre 3, obtenga un 10% de descuento") no contribuirán al cálculo del gasto acumulativo.
- **Efecto de cambiar este ajuste:**
  - *Cuando está activado:* Los productos comprados con descuentos por cantidad se ignoran para los cálculos de fidelización.
  - *Cuando está desactivado:* Los productos comprados con descuentos por cantidad *sí* cuentan para el total acumulado.
- **Valor recomendado:** SÍ, si desea recompensar las compras de artículos individuales a precio completo. NO, si desea fomentar que las compras al por mayor contribuyan a la fidelización.
- **Escenario / ejemplo de comerciante:** Ofrece una oferta de "compre 5 y obtenga un 15% de descuento". Si activa esto, los clientes que aprovechen esa oferta no contarán esos artículos específicos para su progreso de descuento acumulativo.

#### **Grupo de clientes predeterminado**

- **Qué hace este ajuste:** Esto define el grupo de clientes predeterminado al que se asignarán los clientes si no cumplen los criterios de gasto para ningún otro grupo de descuentos acumulativos. Este suele ser su grupo "Cliente" estándar.
- **Efecto de cambiar este ajuste:** Asegura que los clientes siempre pertenezcan a un grupo válido, incluso si no han gastado lo suficiente para calificar para un nivel de descuento especial.
- **Valor recomendado:** Su grupo "Cliente" estándar (a menudo ID 3).
- **Escenario / ejemplo de comerciante:** Un nuevo cliente se registra. Aún no ha realizado ninguna compra, por lo que el módulo lo asigna al "Grupo de clientes predeterminado" (por ejemplo, "Cliente"), que podría tener un 0% de descuento. A medida que gasten, se les moverá a "Bronce", "Plata", etc.

#### **Información para clientes registrados (Página de producto)**

- **Qué hace este ajuste:** Este es un editor de texto donde puede personalizar el mensaje que se muestra a los *clientes registrados* en las páginas de producto. Este mensaje normalmente les informa sobre su estado de descuento actual o su progreso.
- **Efecto de cambiar este ajuste:** El texto que introduzca aquí aparecerá en las páginas de producto para los clientes que hayan iniciado sesión en su cuenta. Puede usar variables Smarty (como `{$total_spent}`, `{$discount_value}`, `{$next_group_name}`, `{$next_group_value}`) para personalizar el mensaje.
- **Valor recomendado:** Un mensaje de bienvenida como: "¡Hola {$customer_name}! Actualmente estás en el grupo {$current_group_name} y recibes un {$discount_value}% de descuento. ¡Gasta {$to_next_group} más para alcanzar el grupo {$next_group_name} y obtener un {$next_group_value}% de descuento!"
- **Escenario / ejemplo de comerciante:** Desea motivar a los clientes registrados. Puede decirles exactamente cuánto más necesitan gastar para obtener un descuento mayor, creando un incentivo claro.

#### **Información para clientes no registrados (Página de producto)**

- **Qué hace este ajuste:** Este es un editor de texto donde puede personalizar el mensaje que se muestra a los *clientes invitados o no registrados* en las páginas de producto. Este mensaje normalmente los anima a registrarse y participar en el programa de fidelización.
- **Efecto de cambiar este ajuste:** El texto que introduzca aquí aparecerá en las páginas de producto para los clientes que no hayan iniciado sesión en su cuenta.
- **Valor recomendado:** Un mensaje atractivo como: "¡Regístrate ahora y empieza a ganar descuentos acumulativos! ¡Cuanto más gastes, más ahorrarás!"
- **Escenario / ejemplo de comerciante:** Un nuevo visitante llega a una página de producto. Este mensaje puede incitarlos a crear una cuenta destacando los beneficios de su programa de fidelización, convirtiéndolos potencialmente en un cliente registrado.

#### **Información para clientes registrados (Página del carrito)**

- **Qué hace este ajuste:** Este es un editor de texto donde puede personalizar el mensaje que se muestra a los *clientes registrados* en la página del carrito de compras. Este mensaje puede reforzar su estado de descuento o mostrar cómo su carrito actual contribuye a su fidelización.
- **Efecto de cambiar este ajuste:** El texto que introduzca aquí aparecerá en la página del carrito para los clientes registrados. Puede usar variables Smarty.
- **Valor recomendado:** Similar al mensaje de la página de producto, pero quizás enfatizando la contribución del carrito actual: "El valor actual de tu carrito es {$cart_value}. ¡Con tu descuento de {$current_group_name}, ahorras un {$discount_value}%! ¡Gasta {$to_next_group} más para alcanzar el grupo {$next_group_name}!"
- **Escenario / ejemplo de comerciante:** Un cliente está a punto de pagar. Este mensaje les recuerda sus beneficios de fidelización e incluso podría animarles a añadir un pequeño artículo para alcanzar el siguiente nivel de descuento.

#### **Información para clientes no registrados (Página del carrito)**

- **Qué hace este ajuste:** Este es un editor de texto donde puede personalizar el mensaje que se muestra a los *clientes invitados o no registrados* en la página del carrito de compras. Este mensaje los anima a registrarse antes de completar su compra para empezar a ganar fidelización.
- **Efecto de cambiar este ajuste:** El texto que introduzca aquí aparecerá en la página del carrito para los clientes no registrados.
- **Valor recomendado:** "¡No te pierdas los descuentos por fidelización! ¡Regístrate antes de pagar para empezar a ganar recompensas en tus compras!"
- **Escenario / ejemplo de comerciante:** Un cliente invitado tiene artículos en su carrito. Este mensaje proporciona un último empujón para registrar una cuenta, convirtiendo a un comprador ocasional en un cliente potencial leal.

### 2.2 Pantallas de administración dedicadas y vistas de controlador

#### AdminCudiListController (Back Office > Descuentos acumulativos > Gestionar descuentos)

- **Nombre de la pantalla y ubicación del menú:** Puede encontrar esta pantalla navegando a **Catálogo > Descuentos acumulativos** (o una ubicación similar según su versión de PrestaShop y la personalización del menú). La etiqueta exacta podría ser "Gestionar descuentos" o "Reglas de descuento acumulativo".
- **Acciones y ajustes disponibles:** Esta pantalla presenta una cuadrícula (lista) de sus reglas de descuento acumulativo definidas. Cada regla especifica:
  - **Cantidad mínima de gasto:** La cantidad total que un cliente debe gastar para calificar para este grupo.
  - **Grupo de clientes:** El grupo de clientes de PrestaShop al que se asignarán los clientes que cumplan los criterios de gasto.
  - **Porcentaje de descuento:** El porcentaje de descuento asociado a ese grupo de clientes.
  - **Acciones:** Puede "Añadir nuevas" reglas, "Editar" reglas existentes o "Eliminar" reglas.
- **Efecto de los cambios:**
  - **Añadir una nueva regla:** Crea un nuevo nivel en su programa de fidelización. Por ejemplo, "Gaste 500 € para unirse al grupo Oro y obtener un 15% de descuento".
  - **Editar una regla:** Modifica el umbral de gasto o el grupo/descuento asignado para un nivel existente. Los cambios afectarán las futuras asignaciones de grupo y los recálculos.
  - **Eliminar una regla:** Elimina un nivel de fidelización. Los clientes que estaban previamente en ese grupo serán reasignados en función de las reglas restantes.
- **Flujo de trabajo recomendado para la gestión diaria de la tienda:**
  1. **Planifique sus niveles:** Decida sus umbrales de gasto y los grupos de descuento correspondientes (por ejemplo, Bronce: 100 € para el 5%, Plata: 500 € para el 10%, Oro: 1000 € para el 15%).
  2. **Cree grupos de clientes:** Asegúrese de tener grupos de clientes correspondientes en PrestaShop (Back Office > Clientes > Grupos) para cada nivel (por ejemplo, "Cliente Bronce", "Cliente Plata", "Cliente Oro"). Asigne el porcentaje de descuento global apropiado a cada uno de estos grupos.
  3. **Añada reglas:** Utilice el botón "Añadir nuevo" para crear cada nivel, vinculando la cantidad de gasto al grupo de clientes correcto.
  4. **Ordene las reglas:** El módulo procesa las reglas de menor a mayor gasto. Asegúrese de que sus reglas estén ordenadas lógicamente.
  5. **Revise y ajuste:** Revise periódicamente sus niveles para asegurarse de que sigan siendo efectivos y rentables.

#### index.php (cudi/controllers/admin/index.php)

Este archivo es típicamente un marcador de posición o un redireccionador dentro de la estructura del controlador de administración y no representa una pantalla directa y configurable para el comerciante. Es parte del enrutamiento interno del módulo para el back office. Toda la configuración orientada al comerciante para los descuentos acumulativos se realiza en la página de configuración principal del módulo o a través del `AdminCudiListController`.

### 2.3 Tabla de referencia rápida de configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| **Página de configuración del módulo** | Activar programa | SÍ | Interruptor principal para el programa de fidelización. |
|  | Desactivar programa de descuentos acumulativos para grupos de clientes seleccionados | Seleccionar "Invitado", "Visitante" | Excluye grupos de clientes específicos del programa. |
|  | Marco de tiempo | Pedidos del último año / Todos los pedidos | Define el período para el cálculo del gasto total. |
|  | Tipo de precio | Precio bruto | Determina si se utilizan precios netos o brutos para el cálculo del gasto. |
|  | Seleccionar estados de pedido | Pago aceptado, Entregado | Especifica qué estados de pedido cuentan para el gasto total. |
|  | Excluir pedidos realizados con código de cupón | SÍ | Evita que los pedidos con cupones contribuyan a la fidelización. |
|  | Excluir productos con precios específicos | SÍ | Evita que los productos en promociones de precios específicos contribuyan. |
|  | Excluir productos con descuentos por cantidad | SÍ | Evita que los productos con descuentos por cantidad contribuyan. |
|  | Grupo de clientes predeterminado | Su grupo "Cliente" estándar | El grupo asignado si no se cumple ningún nivel de fidelización. |
|  | Información para clientes registrados (Página de producto) | Texto personalizable con variables Smarty | Mensaje para usuarios registrados en las páginas de producto. |
|  | Información para clientes no registrados (Página de producto) | Texto personalizable | Mensaje para invitados en las páginas de producto, animando al registro. |
|  | Información para clientes registrados (Página del carrito) | Texto personalizable con variables Smarty | Mensaje para usuarios registrados en las páginas del carrito. |
|  | Información para clientes no registrados (Página del carrito) | Texto personalizable | Mensaje para invitados en las páginas del carrito, animando al registro. |
| **AdminCudiListController** | Cantidad mínima de gasto | Varía según el nivel | Umbral para calificar para un grupo de descuento específico. |
|  | Grupo de clientes | Sus grupos de fidelización personalizados (por ejemplo, Bronce, Plata) | El grupo de PrestaShop asignado cuando se cumple el umbral de gasto. |
|  | Porcentaje de descuento | Varía según el nivel | El descuento aplicado al grupo de clientes asignado. |

## 3. Solución de problemas del comerciante y preguntas frecuentes (FAQ)

**P1: Mis clientes no se asignan a los grupos correctos o los descuentos no se aplican.**
R1:

- **Verifique "Activar programa":** Asegúrese de que el interruptor principal en la configuración del módulo esté en SÍ.
- **Verifique "Marco de tiempo" y "Seleccionar estados de pedido":** Asegúrese de que los pedidos que espera que cuenten estén dentro del marco de tiempo seleccionado y tengan los estados de pedido correctos (por ejemplo, "Entregado", "Pago aceptado").
- **Revise los ajustes de "Excluir":** Compruebe si "Excluir pedidos realizados con código de cupón", "Excluir productos con precios específicos" o "Excluir productos con descuentos por cantidad" están activados y podrían estar impidiendo que los pedidos cuenten.
- **Borrar caché:** Vaya a **Parámetros avanzados > Rendimiento** y haga clic en "Borrar caché". A veces, la caché de PrestaShop puede impedir que los cambios surtan efecto inmediatamente.
- **Verifique los grupos de clientes:** Asegúrese de que los grupos de clientes que ha vinculado en el `AdminCudiListController` realmente existan en PrestaShop (Clientes > Grupos) y tengan el porcentaje de descuento global correcto asignado.
- **Orden de las reglas:** Asegúrese de que sus reglas en `AdminCudiListController` estén ordenadas lógicamente de menor a mayor umbral de gasto.

**P2: La información de descuento no aparece en mis páginas de producto o carrito.**
R2:

- **Verifique los hooks del módulo:** Asegúrese de que el módulo esté enganchado a `displayProductAdditionalInfo` y `displayShoppingCart`. Puede verificar esto en **Diseño > Posiciones** (o **Módulos > Posiciones** en versiones anteriores de PS). Busque "Descuentos acumulativos" bajo estos hooks. Si no, intente reinstalar el módulo o engancharlo manualmente.
- **Texto de configuración del módulo:** Asegúrese de haber introducido texto en los campos "Información para clientes registrados" e "Información para clientes no registrados" para las páginas de producto y carrito. Si estos campos están vacíos, no se mostrará nada.
- **Compatibilidad del tema:** Su tema personalizado podría anular las posiciones de hook estándar. Si la información aún no aparece, es posible que necesite un desarrollador web para ajustar los archivos `.tpl` de su tema para incluir explícitamente los hooks del módulo.

**P3: ¿Cómo traduzco los mensajes del módulo a otros idiomas?**
R3:

- Vaya a **Internacional > Traducciones** en su Back Office de PrestaShop.
- Seleccione "Traducciones de módulos instalados", elija su tema y luego seleccione "Descuentos acumulativos" en el menú desplegable del módulo.
- A continuación, puede traducir todas las cadenas estáticas del módulo. Para los mensajes personalizados que ha introducido en la configuración (por ejemplo, "Información para clientes registrados"), deberá utilizar el selector de idioma en la parte superior derecha de la página de configuración del módulo para cambiar de idioma e introducir el texto traducido para cada idioma.

**P4: ¿Puedo asignar manualmente un cliente a un grupo de descuentos acumulativos?**
R4: Sí, puede cambiar manualmente el grupo de un cliente en su perfil de cliente (Back Office > Clientes > Clientes > Editar cliente). Sin embargo, el módulo reevaluará automáticamente su grupo en función de su historial de gastos durante la próxima actualización del estado del pedido o cuando se active la lógica del módulo. Si desea que un cliente permanezca *permanentemente* en un grupo específico, independientemente del gasto, es posible que deba excluir ese grupo del programa de descuentos acumulativos (utilizando el ajuste "Desactivar programa de descuentos acumulativos para grupos de clientes seleccionados") y gestionarlos manualmente.

**P5: ¿Qué sucede si el gasto total de un cliente cae por debajo de un nivel (por ejemplo, debido a un reembolso)?**
R5: El módulo recalcula el gasto total del cliente en función del "Marco de tiempo" y los "Estados de pedido seleccionados" configurados cada vez que se actualiza el estado de un pedido. Si un reembolso hace que su total caiga por debajo de un nivel, el módulo los reasignará automáticamente al grupo de nivel inferior apropiado durante el siguiente recálculo, asegurando la precisión.

## 4. Guía para desarrolladores y webmasters (Arquitectura técnica y mapa de código)

Esta sección es estrictamente para desarrolladores, webmasters de tiendas y agencias técnicas que mantienen o extienden la tienda.

### 4.1 Resumen de la arquitectura

El módulo "Descuentos acumulativos" (`cudi`) sigue una arquitectura de módulo estándar de PrestaShop, aprovechando los principios MVC. Opera principalmente enganchándose a varios eventos del front-office y back-office para calcular el gasto del cliente y asignarlos dinámicamente a los grupos de clientes apropiados. La configuración se gestiona a través del método principal `getContent()` y un `AdminCudiListController` dedicado para gestionar los niveles de descuento. No introduce tablas de base de datos personalizadas, sino que se basa en `ps_configuration` de PrestaShop para la configuración y `ps_customer_group` para las asignaciones de grupo.

### 4.2 Controladores (`controllers/`)

#### Controladores de Front-Office

- `cudi/controllers/front/index.php`
  - **Nombre de la clase y clase padre:** `CudiIndexModuleFrontController` extiende `ModuleFrontController`.
  - **Responsabilidad:** Este controlador probablemente sirve como predeterminado o de reserva para el enrutamiento del front-office del módulo. Podría manejar la configuración inicial o la redirección, aunque `mydiscount.php` es más específico para el contenido orientado al cliente.
- `cudi/controllers/front/mydiscount.php`
  - **Nombre de la clase y clase padre:** `CudiMydiscountModuleFrontController` extiende `ModuleFrontController`.
  - **Responsabilidad:** Este controlador es responsable de renderizar la página dedicada "Mis descuentos" en el área de la cuenta del cliente. Obtiene el gasto total del cliente, el grupo actual y el progreso hacia el siguiente nivel, luego pasa estos datos a la plantilla `myDiscount.tpl` para su visualización. Responde a una ruta como `sutieneda.com/module/cudi/mydiscount`.

#### Controladores de administración de Back-Office

- `cudi/controllers/admin/AdminCudiList.php`
  - **Nombre de la pestaña y entidad gestionada:** "Descuentos acumulativos" (o similar, accesible a través del menú Catálogo). Gestiona la entidad `cudi`, que representa las reglas de descuento acumulativo (umbrales de gasto vinculados a grupos de clientes).
  - **Responsabilidad:** Este es el controlador de administración principal para gestionar los niveles de descuento. Extiende `AdminController` y utiliza `HelperList` para la visualización de la cuadrícula y `HelperForm` para añadir/editar reglas individuales. Maneja las operaciones CRUD para las reglas de descuento acumulativo, incluida la definición del gasto mínimo, el grupo de clientes objetivo y el descuento asociado.
- `cudi/controllers/admin/index.php`
  - **Responsabilidad:** Este archivo suele servir como punto de entrada o redireccionador dentro del directorio del controlador de administración. En muchos módulos, podría contener un simple `header('Location: ...')` para redirigir al controlador de administración principal (`AdminCudiList.php` en este caso) o ser un marcador de posición. No representa una pantalla directa y configurable.

### 4.3 Clases y modelos principales (`classes/`)

El dossier del módulo no indica clases personalizadas en el directorio `classes/`. La lógica central para calcular el gasto acumulativo y asignar grupos probablemente está encapsulada dentro del propio archivo principal del módulo `cudi.php`, particularmente dentro de sus métodos de hook y potencialmente funciones de ayuda. Interactúa directamente con los `ObjectModel` de PrestaShop `Customer`, `Order`, `OrderState` y `Group`.

### 4.4 Activos de JavaScript (`views/js/`)

- `cudi/views/admin/js/cudi.js`
  - **Alcance:** Back-office.
  - **Responsabilidad:** Este script probablemente maneja las interacciones del lado del cliente en la página de configuración del módulo o en el `AdminCudiListController`. Esto podría incluir:
    - Visibilidad dinámica de los campos del formulario basada en las opciones seleccionadas (por ejemplo, mostrar/ocultar opciones de exclusión).
    - Llamadas AJAX para guardar la configuración sin una recarga completa de la página.
    - Validación de entrada o elementos interactivos específicos de la interfaz de administración del módulo.
    - Escuchadores de eventos para cambios de formulario o clics de botones dentro del panel de administración.

### 4.5 Hojas de estilo CSS (`views/css/`)

- `cudi/views/admin/css/cudi.css`
  - **Alcance:** Estilo del formulario de administración del Back-office.
  - **Responsabilidad:** Proporciona estilo para la página de configuración del módulo y la interfaz de `AdminCudiListController`, asegurando que se integre visualmente con el tema del back office de PrestaShop.
  - **Selectores de clase CSS clave:** Probablemente apunta a ID o clases específicas dentro de las plantillas de administración del módulo (por ejemplo, `.cudi-settings-panel`, `.cudi-list-table`).
- `cudi/views/css/cudi.css`
  - **Alcance:** Estilo del cliente del Front-office.
  - **Responsabilidad:** Estiliza la información mostrada a los clientes en las páginas de producto, páginas de carrito y la página "Mis descuentos".
  - **Selectores de clase CSS clave:** Apuntará a elementos generados por las plantillas del front-office del módulo (por ejemplo, `.cudi-info-block`, `.cudi-discount-message`, `.cudi-progress-bar`). Los desarrolladores pueden anularlos en el `custom.css` de su tema o creando un tema hijo.

### 4.6 Estructura de la plantilla Smarty (`views/templates/`)

#### Plantillas de hook (`views/templates/hook/`)

- `cudi/views/templates/hook/displayProductAdditionalInfo-unlogged.tpl`
  - **Hook:** `displayProductAdditionalInfo` (específicamente para usuarios no registrados).
  - **Salida:** Muestra el mensaje personalizable para clientes no registrados en las páginas de producto, animando al registro y destacando el programa de fidelización.
- `cudi/views/templates/hook/displayProductAdditionalInfo.tpl`
  - **Hook:** `displayProductAdditionalInfo` (para usuarios registrados).
  - **Salida:** Muestra el mensaje personalizable para clientes registrados en las páginas de producto, mostrando su estado de descuento actual y el progreso hacia el siguiente nivel.
- `cudi/views/templates/hook/myAccount.tpl`
  - **Hook:** `displayCustomerAccount`.
  - **Salida:** Renderiza un enlace o bloque en la sección "Mi cuenta" del cliente, típicamente etiquetado como "Mis descuentos", que lleva a la página dedicada `mydiscount`.

#### Plantillas de administración (`views/templates/admin/`)

- `cudi/views/admin/assignButton.tpl`
  - **Alcance:** Back-office.
  - **Salida:** Probablemente renderiza un botón o enlace de acción dentro de la interfaz de administración, posiblemente para activar un recálculo manual o la asignación de grupos de clientes.
- `cudi/views/admin/orderstates.tpl`
  - **Alcance:** Back-office.
  - **Salida:** Se utiliza dentro del formulario de configuración principal del módulo (`getContent()`) para renderizar el menú desplegable de selección múltiple o las casillas de verificación para "Seleccionar estados de pedido".

#### Plantillas de front-office (`views/templates/front/`)

- `cudi/views/templates/front/myDiscount.tpl`
  - **Alcance:** Front-office.
  - **Salida:** Esta es la plantilla de página dedicada para el `CudiMydiscountModuleFrontController`. Muestra una visión general completa del estado de fidelización del cliente, incluyendo el total gastado, el grupo actual, el porcentaje de descuento y el progreso hacia niveles superiores.

### 4.7 Esquema de la base de datos y mapa de hooks

#### Tablas de la base de datos

El módulo no crea tablas SQL personalizadas. Almacena su configuración en la tabla `ps_configuration` de PrestaShop, utilizando claves como `CUDI_ACTIVE`, `CUDI_ORDERSDATE`, `CUDI_PRICETYPE`, `CUDI_ORDERSTATES`, `CUDI_EX_SP`, `CUDI_EX_SP_QTY`, `CUDI_ORDERCOUPON`, `CUDI_DEFGROUP`, `CUDI_GROUPSNOT`, `CUDI_SHOWINFO_PRODUCT`, `CUDI_SHOWINFO_CART`, `logged_cudi_contents`, `unlogged_cudi_contents`.
Las reglas de descuento acumulativo (umbrales de gasto y grupos de clientes asociados) probablemente se almacenan como datos serializados dentro de una entrada de `ps_configuration` o se gestionan directamente por el `AdminCudiListController`, que podría usar una tabla personalizada (aunque no se enumera explícitamente en `classes/` o `sql/`). *Autocorrección: Dado el `AdminCudiListController` y su gestión de la entidad `cudi`, es muy probable que exista una tabla personalizada `ps_cudi`, incluso si no se enumera explícitamente en `classes/` o `sql/` en el dossier proporcionado. Esta tabla almacenaría el `id_cudi`, `min_spend`, `id_group`, `discount_percentage` para cada regla.*

#### Tabla de Hooks registrados

| Nombre del Hook | Momento de ejecución | Propósito técnico |
| --- | --- | --- |
| `displayHeader` | Se renderiza en la sección `<head>` de todas las páginas del front-office. | Se utiliza para incluir los activos CSS/JS del módulo para el front-office, o para inicializar variables JS globales. |
| `displayProductAdditionalInfo` | En las páginas de producto, típicamente debajo de la descripción del producto o del botón de añadir al carrito. | Muestra información del programa de fidelización (descuento actual, progreso) a los clientes. |
| `displayCustomerAccount` | En la página "Mi cuenta" del cliente. | Añade un enlace a la página dedicada "Mis descuentos". |
| `displayShoppingCart` | En la página de resumen del carrito de compras. | Muestra información del programa de fidelización (descuento actual, contribución del carrito) a los clientes. |
| `updateOrderStatus` | Se activa cuando se cambia el estado de un pedido en el back office. | **Crucial para recalcular el gasto total del cliente y reasignar su grupo.** |
| `actionOrderStatusUpdate` | Similar a `updateOrderStatus`, proporciona un control más granular después de una actualización del estado del pedido. | **También crucial para recalcular el gasto total del cliente y reasignar su grupo.** |
| `actionAdminControllerSetMedia` | En el back office, cuando se carga un controlador de administración. | Se utiliza para incluir los activos CSS/JS del módulo para el back-office (por ejemplo, `cudi.js`, `cudi.css`). |

## 5. Soporte oficial y actualizaciones

Para las últimas actualizaciones del módulo, correcciones de errores y soporte oficial, inicie sesión en su cuenta de cliente en [MyPresta.eu](https://mypresta.eu/my-account/orders/). Allí encontrará sus módulos comprados y sus enlaces de descarga. Para asistencia técnica, utilice los canales de soporte proporcionados en MyPresta.eu.
