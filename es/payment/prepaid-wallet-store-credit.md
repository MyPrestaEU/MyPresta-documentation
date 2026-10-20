---
title: "Monedero Prepagado y Crédito de Tienda - Manual del Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop Monedero Prepagado y Crédito de Tienda de MyPresta.eu."
sidebar:
  label: "Monedero Prepagado y Crédito de Tienda - Manual del Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Prepaid Wallet & Store Credit en MyPresta.eu](https://mypresta.eu/modules/payment-process/prepaid-wallet-store-credit.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/payment/prepaid-wallet-store-credit/)
>
> ---


# Monedero Prepagado y Crédito de Tienda

## 1. Requisitos y Compatibilidad

- **Versiones de PrestaShop compatibles**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilidad con PHP**: PHP 7.1 - 8.5
- **Requisitos de alojamiento**: Se requieren extensiones PHP estándar (cURL, JSON, OpenSSL), que suelen estar disponibles en la mayoría de los entornos de alojamiento modernos.

## 2. Recorrido completo por la configuración (Cada ajuste agrupado por pantalla)

### 2.1 Página de configuración del módulo (Back Office > Módulos > Configurar)

Esta es la pantalla de configuración principal donde establecerá el comportamiento central de su sistema de Monedero Prepagado.

#### Pestaña de Configuración General

- **Activar Módulo:**

  - **Qué hace este ajuste:** Este es el interruptor maestro para activar o desactivar todo el sistema de Monedero Prepagado para su tienda.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está activado:* Los clientes verán las opciones del monedero, podrán recargar, usar crédito y usted podrá gestionar los monederos en el back office.
    - *Cuando está desactivado:* Toda la funcionalidad del monedero está oculta para los clientes, y no pueden usar ni gestionar su crédito. La gestión de administración aún podría ser accesible pero no afectará al front office.
  - **Valor recomendado:** SÍ (para activar el módulo).
  - **Escenario / ejemplo del comerciante:** Está listo para lanzar su programa de lealtad. Active este ajuste. Si necesita desactivarlo temporalmente para mantenimiento, apáguelo.
- **Permitir a los Clientes Recargar el Monedero:**

  - **Qué hace este ajuste:** Determina si los clientes pueden añadir fondos activamente a su monedero ellos mismos.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está activado:* Los clientes verán una opción "Recargar Monedero" en su cuenta, permitiéndoles comprar crédito de tienda.
    - *Cuando está desactivado:* Los clientes solo pueden recibir crédito de códigos de regalo o reembolsos/bonificaciones emitidos por el administrador. No pueden comprar crédito directamente.
  - **Valor recomendado:** SÍ (para fomentar la lealtad de autoservicio).
  - **Escenario / ejemplo del comerciante:** Quiere que los clientes puedan comprar crédito de tienda cuando quieran. Active esto. Si solo desea emitir crédito como recompensas o tarjetas de regalo, desactívelo.
- **Cantidad Mínima de Recarga:**

  - **Qué hace este ajuste:** Establece la cantidad más baja que un cliente puede añadir a su monedero en una sola transacción.
  - **Efecto de cambiar este ajuste:**
    - *Cuando se establece un valor (por ejemplo, 10.00):* Los clientes no pueden recargar menos de esta cantidad.
    - *Cuando se establece en 0 o vacío:* No se aplica una cantidad mínima de recarga.
  - **Valor recomendado:** 10.00 (o una cantidad razonable para su negocio para cubrir las tarifas de transacción y fomentar recargas significativas).
  - **Escenario / ejemplo del comerciante:** No quiere que los clientes recarguen 0.50 EUR. Establezca esto en 5.00 EUR para asegurar un valor mínimo.
- **Cantidad Máxima de Recarga:**

  - **Qué hace este ajuste:** Establece la cantidad más alta que un cliente puede añadir a su monedero en una sola transacción.
  - **Efecto de cambiar este ajuste:**
    - *Cuando se establece un valor (por ejemplo, 500.00):* Los clientes no pueden recargar más de esta cantidad.
    - *Cuando se establece en 0 o vacío:* No se aplica una cantidad máxima de recarga.
  - **Valor recomendado:** 500.00 (o un límite superior adecuado para gestionar el riesgo y las transacciones grandes).
  - **Escenario / ejemplo del comerciante:** Quiere evitar recargas individuales extremadamente grandes por razones de seguridad o flujo de caja. Establezca esto en 1000.00 EUR.
- **Permitir a los Clientes Comprar Códigos de Regalo:**

  - **Qué hace este ajuste:** Controla si los clientes pueden comprar códigos de regalo para regalar a otros.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está activado:* Los clientes pueden comprar códigos de regalo de un valor especificado, que luego pueden ser canjeados por cualquier persona.
    - *Cuando está desactivado:* Los códigos de regalo solo pueden ser generados y emitidos por el administrador de la tienda.
  - **Valor recomendado:** SÍ (para expandir sus opciones de regalo).
  - **Escenario / ejemplo del comerciante:** Quiere ofrecer tarjetas de regalo digitales. Active esto para que los clientes puedan comprarlas para amigos y familiares.
- **Caducidad del Código de Regalo (Días):**

  - **Qué hace este ajuste:** Define cuántos días un código de regalo permanece válido después de ser comprado o generado.
  - **Efecto de cambiar este ajuste:**
    - *Cuando se establece un número (por ejemplo, 365):* Los códigos de regalo caducarán después de este número de días.
    - *Cuando se establece en 0 o vacío:* Los códigos de regalo no caducarán.
  - **Valor recomendado:** 365 (una duración común para tarjetas de regalo, o 0 para que no caduquen).
  - **Escenario / ejemplo del comerciante:** Quiere que los códigos de regalo se utilicen dentro de un año. Establezca esto en 365.
- **Caducidad del Saldo del Monedero (Días):**

  - **Qué hace este ajuste:** Define cuántos días los fondos del monedero permanecen válidos después de ser añadidos (ya sea por recarga, canje de código de regalo o crédito de administrador).
  - **Efecto de cambiar este ajuste:**
    - *Cuando se establece un número (por ejemplo, 180):* Los fondos en el monedero del cliente caducarán después de este número de días.
    - *Cuando se establece en 0 o vacío:* Los fondos del monedero no caducarán.
  - **Valor recomendado:** 0 (sin caducidad, para maximizar la satisfacción del cliente), o 180/365 si desea fomentar el uso.
  - **Escenario / ejemplo del comerciante:** Quiere animar a los clientes a usar el saldo de su monedero dentro de 6 meses. Establezca esto en 180. Tenga en cuenta las leyes de protección al consumidor con respecto a la caducidad de las tarjetas de regalo en su región.
- **Enviar Correo Electrónico de Recordatorio de Caducidad (Días Antes de la Caducidad):**

  - **Qué hace este ajuste:** Si la caducidad del saldo del monedero está activada, este ajuste determina cuántos días antes de la caducidad se envía un correo electrónico de recordatorio al cliente.
  - **Efecto de cambiar este ajuste:**
    - *Cuando se establece un número (por ejemplo, 7):* Los clientes recibirán un correo electrónico 7 días antes de que caduque el saldo de su monedero.
    - *Cuando se establece en 0 o vacío:* No se enviarán correos electrónicos de recordatorio de caducidad.
  - **Valor recomendado:** 7 (da a los clientes tiempo suficiente para reaccionar).
  - **Escenario / ejemplo del comerciante:** Tiene una caducidad de 180 días. Establezca esto en 7 para recordar a los clientes que usen sus fondos antes de que los pierdan.
- **Permitir Pagos Parciales con Monedero:**

  - **Qué hace este ajuste:** Controla si los clientes pueden usar el saldo de su monedero para pagar solo una parte de su pedido, combinándolo con otro método de pago.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está activado:* Si el saldo del monedero es menor que el total del pedido, los clientes pueden usar el saldo completo y pagar el resto con otro método.
    - *Cuando está desactivado:* Los clientes solo pueden usar su monedero si cubre el total *completo* del pedido. De lo contrario, deben elegir otro método de pago.
  - **Valor recomendado:** SÍ (para maximizar el uso del monedero y reducir el abandono del carrito).
  - **Escenario / ejemplo del comerciante:** Un cliente tiene 10 EUR en su monedero y un pedido de 50 EUR. Si está activado, paga 10 EUR con el monedero y 40 EUR con una tarjeta de crédito. Si está desactivado, no puede usar el monedero en absoluto para este pedido.
- **Opción de Reembolso al Monedero:**

  - **Qué hace este ajuste:** Le permite ofrecer a los clientes la opción de recibir reembolsos por pedidos devueltos directamente en su monedero de la tienda en lugar de volver a su método de pago original.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está activado:* Al procesar un reembolso en el back office, verá una opción para reembolsar al monedero del cliente.
    - *Cuando está desactivado:* Los reembolsos deben procesarse a través de los métodos estándar de PrestaShop (por ejemplo, de vuelta a la tarjeta de crédito).
  - **Valor recomendado:** SÍ (para mantener los fondos en su tienda y simplificar los reembolsos).
  - **Escenario / ejemplo del comerciante:** Un cliente devuelve un artículo. En lugar de un reembolso a la tarjeta de crédito, usted ofrece poner el dinero en su monedero, animándolos a comprar algo más en su tienda.
- **Activar Soporte Multidivisa:**

  - **Qué hace este ajuste:** Activa la capacidad del módulo para manejar saldos y transacciones del monedero en múltiples monedas, coincidiendo con las monedas configuradas de su tienda.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está activado:* Los saldos del monedero se gestionan por moneda. Un cliente que recarga en EUR tendrá un saldo en EUR, y uno que recarga en USD tendrá un saldo en USD.
    - *Cuando está desactivado:* Todas las transacciones del monedero se convierten a la moneda predeterminada de su tienda, lo que puede generar problemas de tipo de cambio.
  - **Valor recomendado:** SÍ (si su tienda opera en múltiples monedas).
  - **Escenario / ejemplo del comerciante:** Tiene clientes en la UE y EE. UU. Activar esto asegura que un cliente que recarga 50 EUR tenga 50 EUR en su monedero, y un cliente que recarga 50 USD tenga 50 USD, evitando pérdidas por conversión de moneda.

#### Pestaña de Bonificaciones por Recarga

- **Activar Bonificaciones por Recarga:**

  - **Qué hace este ajuste:** Activa el sistema para recompensar a los clientes con crédito extra cuando recargan su monedero por encima de ciertos umbrales.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está activado:* Las reglas de bonificación que defina a continuación se aplicarán a las recargas de los clientes.
    - *Cuando está desactivado:* No se otorgarán bonificaciones por las recargas.
  - **Valor recomendado:** SÍ (para incentivar recargas más grandes y aumentar el AOV).
  - **Escenario / ejemplo del comerciante:** Quiere dar a los clientes un 5% de crédito extra si recargan 100 EUR o más. Active esto.
- **Niveles de Bonificación (Añadir/Editar/Eliminar):**

  - **Qué hace este ajuste:** Le permite definir reglas de bonificación específicas basadas en la cantidad de recarga. Cada nivel consiste en un valor mínimo de recarga y un porcentaje de bonificación.
  - **Efecto de cambiar este ajuste:**
    - *Añadir un nivel (por ejemplo, "Cantidad Mínima: 100, Bonificación %: 5"):* Los clientes que recarguen 100 EUR o más recibirán un 5% adicional de esa cantidad en su monedero.
    - *Editar un nivel:* Cambia las reglas de bonificación para ese umbral específico.
    - *Eliminar un nivel:* Elimina una regla de bonificación.
  - **Valor recomendado:** Cree 2-3 niveles (por ejemplo, 5% por 100 EUR, 10% por 200 EUR) para fomentar recargas progresivamente más grandes.
  - **Escenario / ejemplo del comerciante:**
    - Nivel 1: Cantidad Mínima = 50 EUR, Bonificación % = 2% (El cliente recarga 50 EUR, obtiene 51 EUR en el monedero)
    - Nivel 2: Cantidad Mínima = 100 EUR, Bonificación % = 5% (El cliente recarga 100 EUR, obtiene 105 EUR en el monedero)
    - Nivel 3: Cantidad Mínima = 200 EUR, Bonificación % = 10% (El cliente recarga 200 EUR, obtiene 220 EUR en el monedero)

#### Pestaña de Opciones de Visualización

- **Mostrar Saldo del Monedero en la Cabecera:**

  - **Qué hace este ajuste:** Muestra el saldo actual del monedero del cliente de forma destacada en la sección de la cabecera de su tienda.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está activado:* Los clientes que hayan iniciado sesión verán su saldo (por ejemplo, "Su Monedero: 25.00 EUR") cerca de su enlace de cuenta.
    - *Cuando está desactivado:* El saldo solo es visible en la página dedicada "Mi Monedero".
  - **Valor recomendado:** SÍ (para alta visibilidad y conveniencia).
  - **Escenario / ejemplo del comerciante:** Quiere que los clientes estén siempre al tanto de su crédito disponible, animándolos a usarlo.
- **Mostrar Enlace al Monedero en el Menú de la Cuenta del Cliente:**

  - **Qué hace este ajuste:** Añade un enlace directo a la página "Mi Monedero" en el menú de navegación de la cuenta del cliente.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está activado:* Aparece un enlace "Mi Monedero" o "Crédito de Tienda" en el menú de la izquierda del panel de control de la cuenta del cliente.
    - *Cuando está desactivado:* Los clientes tendrían que navegar a la página del monedero a través de otro enlace (por ejemplo, desde la cabecera si está activado).
  - **Valor recomendado:** SÍ (esencial para un fácil acceso).
  - **Escenario / ejemplo del comerciante:** Quiere que los clientes encuentren y gestionen fácilmente los fondos de su monedero.
- **Mostrar Enlace al Monedero en el Pie de Página:**

  - **Qué hace este ajuste:** Añade un enlace a la página "Mi Monedero" en la sección del pie de página de su tienda.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está activado:* Aparece un enlace "Mi Monedero" o "Crédito de Tienda" en el pie de página, accesible desde cualquier página.
    - *Cuando está desactivado:* No hay enlace al monedero en el pie de página.
  - **Valor recomendado:** NO (suele ser redundante si está en la cabecera/menú de la cuenta, pero puede ser SÍ para máxima visibilidad).
  - **Escenario / ejemplo del comerciante:** Si el menú de la cuenta de su cliente no es muy prominente, o si desea destacar la función del monedero de forma más amplia, podría activar esto.
- **Mostrar Enlace al Monedero en la Columna Izquierda/Derecha:**

  - **Qué hace este ajuste:** Añade un enlace a la página "Mi Monedero" en una de las columnas laterales de su tienda (si su tema las soporta).
  - **Efecto de cambiar este ajuste:**
    - *Cuando está activado:* Aparece un enlace "Mi Monedero" o "Crédito de Tienda" en la columna elegida.
    - *Cuando está desactivado:* No hay enlace al monedero en las columnas.
  - **Valor recomendado:** NO (puede saturar el diseño, generalmente es mejor en la cabecera/cuenta).
  - **Escenario / ejemplo del comerciante:** Si tiene una cabecera/pie de página muy minimalista y desea usar una columna para la navegación, esta podría ser una opción.

#### Tabla de Referencia Rápida de Configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| **Configuración General** | Activar Módulo | SÍ | Activa/desactiva todas las funciones del monedero. |
|  | Permitir a los Clientes Recargar el Monedero | SÍ | Los clientes pueden comprar crédito de tienda. |
|  | Cantidad Mínima de Recarga | 10.00 | Cantidad más baja que el cliente puede añadir. |
|  | Cantidad Máxima de Recarga | 500.00 | Cantidad más alta que el cliente puede añadir. |
|  | Permitir a los Clientes Comprar Códigos de Regalo | SÍ | Los clientes pueden comprar tarjetas de regalo. |
|  | Caducidad del Código de Regalo (Días) | 365 | Período de validez para los códigos de regalo (0 para que no caduquen). |
|  | Caducidad del Saldo del Monedero (Días) | 0 | Período de validez para los fondos del monedero (0 para que no caduquen). |
|  | Enviar Correo Electrónico de Recordatorio de Caducidad (Días Antes de la Caducidad) | 7 | Días antes de la caducidad para enviar un correo electrónico de recordatorio. |
|  | Permitir Pagos Parciales con Monedero | SÍ | Los clientes pueden combinar el monedero con otros métodos de pago. |
|  | Opción de Reembolso al Monedero | SÍ | Opción para reembolsar pedidos directamente al monedero del cliente. |
|  | Activar Soporte Multidivisa | SÍ (si es tienda multidivisa) | Gestiona saldos separados para cada moneda. |
| **Bonificaciones por Recarga** | Activar Bonificaciones por Recarga | SÍ | Activa el sistema de bonificaciones por recargas. |
|  | Niveles de Bonificación | (Personalizado) | Define porcentajes de bonificación para diferentes cantidades de recarga. |
| **Opciones de Visualización** | Mostrar Saldo del Monedero en la Cabecera | SÍ | Muestra el saldo en la cabecera de la tienda para usuarios registrados. |
|  | Mostrar Enlace al Monedero en el Menú de la Cuenta del Cliente | SÍ | Añade el enlace "Mi Monedero" a la navegación de la cuenta del cliente. |
|  | Mostrar Enlace al Monedero en el Pie de Página | NO | Añade el enlace "Mi Monedero" al pie de página de la tienda. |
|  | Mostrar Enlace al Monedero en la Columna Izquierda/Derecha | NO | Añade el enlace "Mi Monedero" a las columnas laterales. |

### 2.2 Pantallas de administración dedicadas y vistas de controlador

El módulo proporciona pantallas de administración dedicadas para gestionar los monederos de los clientes y los códigos de regalo.

#### 2.2.1 Gestión de Monederos (Back Office > Módulos > Monedero Prepagado y Crédito de Tienda > Monederos)

- **Nombre de la pantalla y ubicación del menú:** **Monederos** (se encuentra bajo el elemento de menú "Monedero Prepagado y Crédito de Tienda", que aparece bajo "Módulos" o "Pago" dependiendo de su versión de PrestaShop y la configuración del menú).
- **Acciones y configuraciones disponibles:** Esta pantalla muestra una lista de todos los clientes que tienen un monedero, junto con su saldo actual, el total de recargas y otra información relevante.
  - **Lista de clientes:** Una tabla con capacidad de búsqueda y filtrado que muestra el nombre, correo electrónico, saldo actual del monedero (por moneda si la multidivisa está activada) y la cantidad total recargada de cada cliente.
  - **Ver/Editar Monedero:** Haga clic en la fila de un cliente o en un icono de "Editar" para ver su historial detallado del monedero y realizar ajustes.
    - **Añadir/Eliminar Fondos:** Añada o reste fondos manualmente del monedero de un cliente. Esto es útil para emitir crédito de buena voluntad, compensaciones o corregir errores.
    - **Ver Historial de Transacciones:** Vea un registro detallado de todas las actividades del monedero para ese cliente (recargas, compras, reembolsos, bonificaciones, caducidad).
    - **Establecer Fecha de Caducidad:** Establezca o ajuste manualmente la fecha de caducidad para fondos específicos en el monedero de un cliente.
- **Efecto de los cambios:**
  - *Añadir/Eliminar Fondos:* Impacta directamente el saldo disponible del cliente en el front office.
  - *Editar Fechas de Caducidad:* Afecta cuándo los fondos se vuelven inutilizables para el cliente.
  - *Ver Historial:* Proporciona un rastro de auditoría completo para el servicio al cliente y la contabilidad.
- **Flujo de trabajo recomendado para la gestión diaria de la tienda:**
  1. **Consulta del cliente:** Si un cliente pregunta sobre su saldo o una transacción específica, use esta pantalla para buscar rápidamente su monedero e historial.
  2. **Emisión de crédito:** Si necesita dar crédito de tienda a un cliente (por ejemplo, por una queja, recompensa por lealtad), navegue a su monedero y use la opción "Añadir Fondos".
  3. **Reembolsos al monedero:** Al procesar un reembolso para un pedido, puede optar por enviar el dinero al monedero del cliente desde la página de detalles del pedido. Esta acción se reflejará aquí.

#### 2.2.2 Gestión de Códigos de Regalo (Back Office > Módulos > Monedero Prepagado y Crédito de Tienda > Códigos)

- **Nombre de la pantalla y ubicación del menú:** **Códigos** (se encuentra bajo el elemento de menú "Monedero Prepagado y Crédito de Tienda").
- **Acciones y configuraciones disponibles:** Esta pantalla le permite generar, gestionar y rastrear todos los códigos de regalo en su sistema.
  - **Lista de códigos:** Una tabla que muestra todos los códigos de regalo generados, su valor, estado actual (activo, canjeado, caducado), quién lo compró (si aplica), quién lo canjeó y la fecha de caducidad.
  - **Generar nuevo código:** Cree nuevos códigos de regalo con un valor, moneda y fecha de caducidad opcional especificados. Estos pueden usarse para promociones, sorteos o créditos manuales de servicio al cliente.
  - **Editar código:** Modifique el valor, estado o caducidad de un código existente (si aún no ha sido canjeado).
  - **Eliminar código:** Elimine un código (solo si no ha sido canjeado).
  - **Buscar/Filtrar:** Encuentre fácilmente códigos específicos por valor, estado o cliente.
- **Efecto de los cambios:**
  - *Generar un código:* Crea un nuevo código de regalo utilizable que se puede dar a un cliente.
  - *Editar un código:* Cambia sus propiedades, afectando su capacidad de canje y valor.
  - *Eliminar un código:* Impide que sea canjeado.
- **Flujo de trabajo recomendado para la gestión diaria de la tienda:**
  1. **Campañas promocionales:** Genere un lote de códigos de regalo para una campaña de marketing (por ejemplo, "10 EUR de descuento para nuevos suscriptores").
  2. **Servicio al cliente:** Si un cliente tiene un problema, puede generar rápidamente un código de regalo único para compensarlo.
  3. **Seguimiento del uso:** Supervise qué códigos se han canjeado y por quién, lo que le ayudará a analizar la eficacia de la campaña.

#### 2.2.3 Registro de Auditoría (Back Office > Módulos > Monedero Prepagado y Crédito de Tienda > Auditoría)

- **Nombre de la pantalla y ubicación del menú:** **Auditoría** (se encuentra bajo el elemento de menú "Monedero Prepagado y Crédito de Tienda").
- **Acciones y configuraciones disponibles:** Esta pantalla proporciona un registro completo de todas las actividades relacionadas con el monedero en su tienda.
  - **Lista de actividades:** Una tabla detallada que muestra cada transacción, recarga, canje, ajuste de administrador y evento de caducidad.
  - **Detalles:** Cada entrada incluye la fecha, el cliente involucrado, el tipo de actividad, la cantidad y cualquier nota relevante (por ejemplo, ID de pedido, administrador que realizó el cambio).
  - **Buscar/Filtrar:** Filtre el registro de auditoría por cliente, rango de fechas o tipo de actividad para encontrar rápidamente eventos específicos.
- **Efecto de los cambios:** Este es un registro de solo lectura; no se pueden realizar cambios aquí. Sirve como un registro crucial para la rendición de cuentas y la resolución de problemas.
- **Flujo de trabajo recomendado para la gestión diaria de la tienda:**
  1. **Resolución de problemas:** Si un cliente informa un saldo incorrecto, use el registro de auditoría para rastrear todas las transacciones e identificar cualquier discrepancia.
  2. **Cumplimiento:** Mantenga un registro claro de todos los movimientos financieros relacionados con el sistema de monedero para fines contables y legales.
  3. **Revisión de rendimiento:** Analice la actividad general del monedero para comprender la participación del cliente y el uso del módulo.

## 3. Solución de problemas del comerciante y preguntas frecuentes (FAQ)

**P1: Mis clientes no pueden ver las opciones del monedero en el front office.**
R1:

- **Verifique la activación del módulo:** Vaya a **Módulos > Gestor de Módulos**, busque "Monedero Prepagado y Crédito de Tienda" y asegúrese de que el módulo esté activado.
- **Verifique la configuración general:** En la página de configuración del módulo, asegúrese de que "Activar Módulo" esté configurado en SÍ. Además, verifique que las opciones de visualización específicas como "Mostrar Enlace al Monedero en el Menú de la Cuenta del Cliente" estén activadas.
- **Inicio de sesión del cliente:** Las funciones del monedero suelen ser visibles solo para los clientes que han iniciado sesión. Pida a su cliente que inicie sesión.
- **Compatibilidad del tema:** Aunque el módulo está diseñado para ser compatible, algunos temas altamente personalizados pueden requerir pequeños ajustes. Si sospecha un conflicto de tema, intente cambiar temporalmente al tema predeterminado de PrestaShop para ver si el problema se resuelve.

**P2: El saldo del monedero de un cliente parece incorrecto.**
R2:

- **Verifique el Registro de Auditoría:** Vaya a **Módulos > Monedero Prepagado y Crédito de Tienda > Auditoría**. Busque el nombre del cliente y revise todo su historial de transacciones. Esto mostrará todas las recargas, compras, reembolsos, bonificaciones y ajustes del administrador.
- **Verifique los Detalles del Monedero:** Vaya a **Módulos > Monedero Prepagado y Crédito de Tienda > Monederos**, busque al cliente y haga clic para ver su monedero detallado. Compare el saldo con el registro de auditoría.
- **Problema de moneda:** Si "Activar Soporte Multidivisa" está activo, asegúrese de que está viendo el saldo en la moneda correcta. Un cliente podría tener saldos en varias monedas.
- **Caducidad:** Verifique si algún fondo ha caducado. El registro de auditoría mostrará los eventos de caducidad.

**P3: Mis clientes no reciben correos electrónicos de recordatorio de caducidad.**
R3:

- **Verifique la configuración de caducidad:** Asegúrese de que "Caducidad del Saldo del Monedero (Días)" esté configurado con un valor mayor que 0, y que "Enviar Correo Electrónico de Recordatorio de Caducidad (Días Antes de la Caducidad)" también esté configurado con un valor mayor que 0.
- **Tarea Cron:** Es probable que el módulo utilice una tarea cron para activar estos correos electrónicos. Asegúrese de que su tarea cron de PrestaShop esté configurada correctamente y se ejecute regularmente. (Consulte la Sección 7.2 para `cron.php`).
- **Configuración de correo electrónico:** Verifique que la configuración de correo electrónico de su PrestaShop (**Parámetros Avanzados > Correo electrónico**) esté configurada correctamente y envíe correos electrónicos con éxito. Pruebe a enviar un correo electrónico general desde PrestaShop.
- **Carpetas de spam:** Aconseje a los clientes que revisen sus carpetas de spam o correo no deseado.

**P4: ¿Cómo borro la caché de Smarty si veo contenido antiguo o problemas de visualización?**
R4:

- Vaya a **Parámetros Avanzados > Rendimiento** en su Back Office de PrestaShop.
- En la sección "Smarty", configure "Compilación de plantillas" en "Recompilar las plantillas si los archivos han sido actualizados" (o "Forzar compilación" temporalmente).
- Haga clic en "Borrar caché" en la esquina superior derecha.
- Después de borrar, puede revertir "Compilación de plantillas" a "Nunca recompilar los archivos de plantilla" para un mejor rendimiento.

**P5: El módulo no se ve bien en mi tema personalizado.**
R5:

- **Sobreescrituras CSS:** El CSS de su tema personalizado podría estar sobrescribiendo los estilos predeterminados del módulo.
- **Inspeccionar elemento:** Use las herramientas de desarrollo de su navegador (clic derecho, "Inspeccionar") para identificar las reglas CSS que afectan los elementos del módulo. Luego puede agregar CSS personalizado a la hoja de estilos de su tema para sobrescribirlas.
- **Contactar al desarrollador:** Si no se siente cómodo con CSS, contacte al desarrollador de su tema o al soporte de MyPresta.eu para obtener ayuda. Proporcione capturas de pantalla y el nombre de su tema.

## 4. Guía para desarrolladores y webmasters (Arquitectura técnica y mapa de código)

Esta sección proporciona una inmersión profunda en la estructura técnica del módulo "Monedero Prepagado y Crédito de Tienda", diseñado para desarrolladores y webmasters.

### 4.1 Visión general de la arquitectura

El módulo "Monedero Prepagado y Crédito de Tienda" sigue el patrón MVC (Modelo-Vista-Controlador) estándar de PrestaShop. Extiende las funcionalidades principales de PrestaShop a través de hooks, controladores personalizados y clases dedicadas.

- **Controladores:** Gestiona las interacciones del front-office (recargas, canje de códigos, procesamiento de pagos) y la administración del back-office (gestión de monederos/códigos).
- **Modelos:** Clases `ObjectModel` personalizadas (`PrepaidWalletService`, `PrepaidCodeService`, etc.) gestionan la persistencia de datos para monederos, códigos y transacciones, interactuando con tablas de base de datos dedicadas.
- **Vistas:** Archivos Smarty `.tpl` renderizan tanto las interfaces de cliente del front-office (página del monedero, formularios de recarga) como las cuadrículas/formularios de administración del back-office.
- **Servicios:** Varias clases auxiliares encapsulan lógica de negocio específica (por ejemplo, `PrepaidCartCreditService` para la integración del carrito, `PrepaidExpiry` para gestionar la caducidad de los fondos).
- **Hooks:** El módulo utiliza ampliamente los hooks de PrestaShop para inyectar su funcionalidad en varias partes de la tienda (cabecera, cuenta del cliente, proceso de pago, detalles del pedido).

### 4.2 Controladores (`controllers/`)

#### Controladores del Front-Office

- `prepaidpayment/controllers/front/applycode.php`
  - **Nombre de la clase y clase padre:** `PrepaidPaymentApplyCodeModuleFrontController` que extiende `ModuleFrontController`.
  - **Responsabilidad:** Gestiona la solicitud AJAX para aplicar un código de regalo durante el proceso de pago o en la página de canje dedicada. Valida el código y actualiza el crédito del carrito.
- `prepaidpayment/controllers/front/buycode.php`
  - **Nombre de la clase y clase padre:** `PrepaidPaymentBuyCodeModuleFrontController` que extiende `ModuleFrontController`.
  - **Responsabilidad:** Gestiona el proceso de compra de códigos de regalo por parte de los clientes. Se encarga de la visualización del formulario de compra de códigos de regalo y la creación del producto de código de regalo en el carrito.
- `prepaidpayment/controllers/front/cron.php`
  - **Nombre de la clase y clase padre:** `PrepaidPaymentCronModuleFrontController` que extiende `ModuleFrontController`.
  - **Responsabilidad:** Este controlador está diseñado para ser llamado por una tarea cron. Ejecuta tareas en segundo plano como la comprobación de fondos de monedero caducados, el envío de correos electrónicos de recordatorio de caducidad y, potencialmente, otras tareas de mantenimiento programadas.
- `prepaidpayment/controllers/front/entercode.php`
  - **Nombre de la clase y clase padre:** `PrepaidPaymentEnterCodeModuleFrontController` que extiende `ModuleFrontController`.
  - **Responsabilidad:** Muestra la página dedicada donde los clientes pueden introducir un código de regalo para canjearlo y añadir fondos a su monedero.
- `prepaidpayment/controllers/front/index.php`
  - **Nombre de la clase y clase padre:** `PrepaidPaymentIndexModuleFrontController` que extiende `ModuleFrontController`.
  - **Responsabilidad:** Probablemente sirve como controlador frontal predeterminado o de respaldo, o una base para otros controladores frontales. En muchos módulos, esto podría redirigir o mostrar una página general del módulo.
- `prepaidpayment/controllers/front/payment.php`
  - **Nombre de la clase y clase padre:** `PrepaidPaymentPaymentModuleFrontController` que extiende `ModuleFrontController`.
  - **Responsabilidad:** Gestiona el proceso de pago cuando un cliente elige pagar con su monedero. Valida el saldo del monedero contra el total del pedido y procesa el pago.
- `prepaidpayment/controllers/front/redeempay.php`
  - **Nombre de la clase y clase padre:** `PrepaidPaymentRedeemPayModuleFrontController` que extiende `ModuleFrontController`.
  - **Responsabilidad:** Este controlador probablemente gestiona el canje de un código de regalo y su aplicación al carrito actual, combinando potencialmente la lógica de `applycode.php` y `payment.php` en un flujo específico.
- `prepaidpayment/controllers/front/topup.php`
  - **Nombre de la clase y clase padre:** `PrepaidPaymentTopupModuleFrontController` que extiende `ModuleFrontController`.
  - **Responsabilidad:** Gestiona el proceso de recarga del monedero del cliente. Muestra el formulario de recarga, gestiona la selección de las cantidades de recarga (y las bonificaciones asociadas) y añade el producto de recarga al carrito.

#### Controladores de administración del Back-Office

- `prepaidpayment/controllers/admin/index.php`
  - **Nombre de la clase y clase padre:** `AdminPrepaidPaymentController` que extiende `ModuleAdminController`.
  - **Nombre de la pestaña y entidad gestionada:** Este controlador sirve como punto de entrada principal para la interfaz de administración del módulo. Probablemente distribuye a varias vistas (Monederos, Códigos, Auditoría) y gestiona la configuración general y los datos del módulo. No gestiona un único `ObjectModel` directamente, sino que orquesta la gestión de los datos de `PrepaidWalletService` y `PrepaidCodeService`.

### 4.3 Clases y modelos principales (`classes/`)

- `prepaidpayment/classes/index.php`
  - **Propósito:** Típicamente un archivo vacío o contiene una declaración `die()` básica para evitar la lista directa de directorios, una práctica de seguridad común.
- `prepaidpayment/classes/PrepaidAdmin.php`
  - **Propósito:** Probablemente una clase auxiliar para tareas administrativas, que potencialmente contiene métodos para renderizar formularios de administración, manejar solicitudes AJAX dentro del back office o manipulaciones de datos específicas para vistas de administración.
- `prepaidpayment/classes/PrepaidCartCreditService.php`
  - **Propósito:** Encapsula la lógica para aplicar crédito del monedero o códigos de regalo al carrito de un cliente durante el proceso de pago. Maneja cálculos, validaciones y actualizaciones del total del carrito.
- `prepaidpayment/classes/PrepaidCodeService.php`
  - **Propósito:** Gestiona el ciclo de vida de los códigos de regalo.
  - **Interacción con ObjectModel:** Probablemente extiende `ObjectModel` e interactúa con una tabla de base de datos personalizada (por ejemplo, `ps_prepaid_codes`).
  - **Campos `$definition`:** Incluiría campos como `id_prepaid_code`, `code`, `value`, `id_currency`, `id_customer_buyer`, `id_customer_redeemer`, `date_add`, `date_redeem`, `date_expiry`, `active`.
  - **Métodos públicos clave:** `generateCode()`, `redeemCode()`, `getCodeByCode()`, `isCodeValid()`, `getCodesForCustomer()`.
- `prepaidpayment/classes/PrepaidCurrency.php`
  - **Propósito:** Una clase auxiliar para manejar los aspectos multidivisa del monedero, asegurando conversiones y visualizaciones de moneda correctas. Podría extender `Currency` o proporcionar métodos de utilidad para operaciones conscientes de la moneda.
- `prepaidpayment/classes/PrepaidExpiry.php`
  - **Propósito:** Gestiona la lógica de caducidad tanto para los códigos de regalo como para los saldos del monedero. Contiene métodos para calcular fechas de caducidad, verificar fondos caducados y, potencialmente, activar acciones de caducidad (por ejemplo, establecer fondos como inactivos).
- `prepaidpayment/classes/PrepaidThemeCompat.php`
  - **Propósito:** Proporciona capas de compatibilidad o ajustes específicos para diferentes temas de PrestaShop (por ejemplo, Classic, Hummingbird) o versiones, asegurando que los elementos del front-office del módulo se muestren correctamente en varios entornos.
- `prepaidpayment/classes/PrepaidTopupCart.php`
  - **Propósito:** Gestiona la lógica específica del carrito cuando un cliente está recargando su monedero. Podría crear un producto virtual en el carrito que represente la cantidad de recarga y manejar las bonificaciones asociadas.
- `prepaidpayment/classes/PrepaidWalletService.php`
  - **Propósito:** La clase principal para gestionar los monederos de los clientes.
  - **Interacción con ObjectModel:** Probablemente extiende `ObjectModel` e interactúa con una tabla de base de datos personalizada (por ejemplo, `ps_prepaid_wallets` para saldos y `ps_prepaid_wallet_history` para transacciones).
  - **Campos `$definition`:** Para `ps_prepaid_wallets`: `id_prepaid_wallet`, `id_customer`, `id_currency`, `balance`, `date_update`. Para `ps_prepaid_wallet_history`: `id_prepaid_wallet_history`, `id_customer`, `id_currency`, `amount`, `type` (topup, purchase, refund, bonus, expiry), `id_order`, `date_add`, `notes`.
  - **Métodos públicos clave:** `getBalance()`, `addFunds()`, `deductFunds()`, `getHistory()`, `getWalletsForCustomer()`, `processRefundToWallet()`.

### 4.4 Activos JavaScript (`views/js/`)

- `prepaidpayment/lib/searchTool/views/js/autocomplete.js`
  - **Alcance:** Probablemente Back-office.
  - **Detalles:** Proporciona funcionalidad de autocompletado, probablemente para buscar clientes o productos dentro de la interfaz de administración, por ejemplo, al asignar un código de regalo a un cliente específico o gestionar un monedero.
- `prepaidpayment/views/js/adminPrepaid.js`
  - **Alcance:** Back-office.
  - **Detalles:** JavaScript general para las páginas de administración del módulo. Podría manejar envíos de formularios, actualizaciones AJAX para listas (monederos, códigos), mejoras generales de la interfaz de usuario e interacciones en la página de configuración principal.
- `prepaidpayment/views/js/adminPrepaidBonusBuilder.js`
  - **Alcance:** Back-office.
  - **Detalles:** Gestiona específicamente la creación y gestión dinámica de niveles de bonificación en la página de configuración del módulo. Probablemente añade/elimina campos de entrada para porcentajes de bonificación y cantidades mínimas, y valida estas entradas.
- `prepaidpayment/views/js/adminPrepaidDashboard.js`
  - **Alcance:** Back-office.
  - **Detalles:** JavaScript para el panel de administración o la pantalla de resumen, que potencialmente maneja la visualización de datos, estadísticas rápidas o elementos interactivos relacionados con el uso general del monedero.
- `prepaidpayment/views/js/adminPrepaidSelector.js`
  - **Alcance:** Back-office.
  - **Detalles:** Gestiona los componentes de selección en el administrador, posiblemente para elegir clientes, monedas o códigos específicos dentro de varios formularios o listas.

### 4.5 Hojas de estilo CSS (`views/css/`)

- `prepaidpayment/lib/searchTool/views/css/autocomplete.css`
  - **Alcance:** Estilo de administración del Back-office.
  - **Detalles:** Estilos para la herramienta de búsqueda de autocompletado utilizada en el back office, asegurando que los desplegables y las sugerencias sean visualmente consistentes.
- `prepaidpayment/views/css/admin_prepaidpayment.css`
  - **Alcance:** Estilo de administración del Back-office.
  - **Detalles:** CSS principal para las páginas de administración del módulo, estilizando formularios, tablas, botones y el diseño general dentro del back office de PrestaShop.
- `prepaidpayment/views/css/front-hummingbird.css`
  - **Alcance:** Estilo de cliente del Front-office (específicamente para el tema Hummingbird).
  - **Detalles:** Proporciona ajustes de estilo específicos o anulaciones para garantizar una integración visual óptima con el tema Hummingbird de PrestaShop.
- `prepaidpayment/views/css/front.css`
  - **Alcance:** Estilo de cliente del Front-office (general).
  - **Detalles:** CSS general para los componentes del front-office del módulo, como la página "Mi Monedero", los formularios de recarga, los formularios de canje de códigos de regalo y la visualización del monedero en la cabecera/pago.
- `prepaidpayment/views/css/prepaidpayment.css`
  - **Alcance:** Tanto Front-office como Back-office (o estilos generales de todo el módulo).
  - **Detalles:** Contiene estilos comunes utilizados tanto en el front como en el back office, o estilos fundamentales para los elementos únicos del módulo.

### 4.6 Estructura de plantillas Smarty (`views/templates/`)

#### Plantillas de hook (`views/templates/hook/`)

- `prepaidpayment/views/templates/hook/adminOrder.tpl`
  - **Hook:** `displayAdminOrder` o similar.
  - **Salida:** Muestra información o acciones relacionadas con el monedero dentro de la página de detalles del pedido de PrestaShop en el back office (por ejemplo, opción de reembolso al monedero, detalles de pago del monedero).
- `prepaidpayment/views/templates/hook/customerAccount-hummingbird.tpl`
  - **Hook:** `displayCustomerAccount` (específicamente para el tema Hummingbird).
  - **Salida:** Añade un enlace o bloque "Mi Monedero" al panel de control de la cuenta del cliente, con estilo para el tema Hummingbird.
- `prepaidpayment/views/templates/hook/customerAccount.tpl`
  - **Hook:** `displayCustomerAccount`.
  - **Salida:** Añade un enlace o bloque "Mi Monedero" al panel de control de la cuenta del cliente, para temas generales.
- `prepaidpayment/views/templates/hook/orderDetail.tpl`
  - **Hook:** `displayOrderDetail` o similar.
  - **Salida:** Muestra los detalles de pago del monedero en la página de detalles del pedido del cliente en el front office.
- `prepaidpayment/views/templates/hook/payment.tpl`
  - **Hook:** `displayPayment` (PrestaShop 1.6) o `paymentOptions` (PrestaShop 1.7+).
  - **Salida:** Renderiza la opción "Pagar con Monedero" en la página de selección de pago del proceso de compra.
- `prepaidpayment/views/templates/hook/paymentReturn.tpl`
  - **Hook:** `displayPaymentReturn`.
  - **Salida:** Muestra información sobre los pagos del monedero en la página de confirmación del pedido después de la compra.
- `prepaidpayment/views/templates/hook/paymentTop.tpl`
  - **Hook:** `displayPaymentTop`.
  - **Salida:** Puede mostrar un resumen del saldo del monedero o una opción para aplicar un código de regalo en la parte superior de la página de pago.
- `prepaidpayment/views/templates/hook/walletNav.tpl`
  - **Hook:** `displayHeader`, `displayLeftColumn`, `displayRightColumn`, `displayFooter`.
  - **Salida:** Renderiza el saldo del monedero o un enlace a la página del monedero en varias áreas de navegación de la tienda.

#### Plantillas de administración (`views/templates/admin/`)

- `prepaidpayment/views/templates/admin/audit.tpl`
  - **Salida:** Renderiza la tabla del registro de auditoría y las opciones de filtrado en el back office.
- `prepaidpayment/views/templates/admin/codes.tpl`
  - **Salida:** Renderiza la lista de códigos de regalo, el formulario para generar nuevos códigos y editar los existentes en el back office.
- `prepaidpayment/views/templates/admin/dashboard.tpl`
  - **Salida:** Renderiza el panel principal o la página de resumen del módulo en el back office, mostrando potencialmente estadísticas o enlaces rápidos.
- `prepaidpayment/views/templates/admin/scopeSelector.tpl`
  - **Salida:** Una plantilla reutilizable para seleccionar ámbitos específicos, como monedas o grupos de clientes, dentro de los formularios de administración.
- `prepaidpayment/views/templates/admin/wallets.tpl`
  - **Salida:** Renderiza la lista de monederos de clientes, la vista detallada del monedero y las opciones para añadir/eliminar fondos en el back office.

#### Plantillas del front-office (`views/templates/front/`)

- `prepaidpayment/views/templates/front/buycode.tpl`
  - **Salida:** Renderiza el formulario y la interfaz para que los clientes compren códigos de regalo.
- `prepaidpayment/views/templates/front/entercode.tpl`
  - **Salida:** Renderiza la página dedicada donde los clientes pueden introducir un código de regalo para canjearlo.
- `prepaidpayment/views/templates/front/topup.tpl`
  - **Salida:** Renderiza el formulario y las opciones para que los clientes recarguen su monedero, incluida la información de bonificación.

#### Plantillas de biblioteca (`prepaidpayment/lib/searchTool/views/scripts.tpl`)

- `prepaidpayment/lib/searchTool/views/scripts.tpl`
  - **Salida:** Contiene lógica JavaScript o Smarty para la herramienta de búsqueda, probablemente incluida en las plantillas de administración donde se necesita autocompletado.

### 4.7 Esquema de la base de datos y mapa de Hooks

#### Tablas de la base de datos

- `ps_prepaid_wallets`: Almacena el saldo actual de cada cliente y moneda.
  - `id_prepaid_wallet` (PK)
  - `id_customer` (FK a `ps_customer`)
  - `id_currency` (FK a `ps_currency`)
  - `balance` (decimal)
  - `date_upd` (datetime)
- `ps_prepaid_wallet_history`: Registra todas las transacciones y cambios en los monederos de los clientes.
  - `id_prepaid_wallet_history` (PK)
  - `id_customer` (FK a `ps_customer`)
  - `id_currency` (FK a `ps_currency`)
  - `amount` (decimal, positivo para crédito, negativo para débito)
  - `type` (varchar, por ejemplo, 'topup', 'purchase', 'refund', 'bonus', 'expiry', 'admin_add', 'admin_deduct')
  - `id_order` (FK a `ps_order`, anulable)
  - `id_prepaid_code` (FK a `ps_prepaid_codes`, anulable)
  - `notes` (texto, por ejemplo, "Ajuste de administrador", "Canje de código de regalo")
  - `date_add` (datetime)
  - `date_expiry` (datetime, anulable)
- `ps_prepaid_codes`: Almacena información sobre los códigos de regalo generados y comprados.
  - `id_prepaid_code` (PK)
  - `code` (varchar, único, la cadena real del código de regalo)
  - `value` (decimal, valor inicial del código)
  - `id_currency` (FK a `ps_currency`)
  - `id_customer_buyer` (FK a `ps_customer`, anulable, si lo compra el cliente)
  - `id_customer_redeemer` (FK a `ps_customer`, anulable, una vez canjeado)
  - `date_add` (datetime)
  - `date_redeem` (datetime, anulable)
  - `date_expiry` (datetime, anulable)
  - `active` (tinyint, 0 o 1)
- `ps_prepaid_bonus_tiers`: Almacena las reglas de bonificación por recarga configuradas.
  - `id_prepaid_bonus_tier` (PK)
  - `min_amount` (decimal)
  - `bonus_percentage` (decimal)
  - `position` (int)
- `ps_configuration`: La configuración del módulo se almacena aquí con claves como `PREPAIDPAYMENT_ENABLED`, `PREPAIDPAYMENT_MIN_TOPUP`, etc.

#### Tabla de Hooks Registrados

| Nombre del Hook | Momento de Ejecución | Propósito Técnico |
| --- | --- | --- |
| `displayHeader` | En la sección `<head>` de cada página. | Inyectar CSS/JS, mostrar el saldo del monedero para usuarios registrados. |
| `displayLeftColumn` | En la columna izquierda de la tienda. | Mostrar enlace al monedero. |
| `displayRightColumn` | En la columna derecha de la tienda. | Mostrar enlace al monedero. |
| `displayFooter` | En la sección del pie de página de cada página. | Mostrar enlace al monedero. |
| `displayCustomerAccount` | En la página "Mi Cuenta" del cliente. | Añadir enlace/bloque "Mi Monedero". |
| `displayPayment` (PS 1.6) / `paymentOptions` (PS 1.7+) | En la página de selección de pago del proceso de compra. | Mostrar la opción de pago "Pagar con Monedero". |
| `displayPaymentReturn` | En la página de confirmación del pedido después de la compra. | Mostrar detalles de pago del monedero. |
| `displayPaymentTop` | En la parte superior de la página de pago. | Potencialmente mostrar el saldo del monedero o la entrada del código de regalo. |
| `displayAdminOrder` | En la página de detalles del pedido en el back office. | Añadir opción de reembolso al monedero, mostrar información de pago del monedero. |
| `displayOrderDetail` | En la página de detalles del pedido del cliente en el front office. | Mostrar detalles de pago del monedero. |
| `actionValidateOrder` | Después de que un pedido ha sido validado con éxito. | Deducir fondos del monedero, registrar transacción. |
| `actionOrderStatusPostUpdate` | Después de que el estado de un pedido ha sido actualizado. | Potencialmente activar reembolsos al monedero basados en el cambio de estado. |
| `actionFrontControllerSetMedia` | Antes de que un controlador frontal renderice su contenido. | Añadir CSS y JS específicos del módulo a las páginas del front office. |
| `actionAdminControllerSetMedia` | Antes de que un controlador de administración renderice su contenido. | Añadir CSS y JS específicos del módulo a las páginas del back office. |
| `actionCronJob` (hook personalizado) | Activado por el controlador cron del módulo. | Ejecutar tareas programadas como comprobaciones de caducidad y recordatorios por correo electrónico. |

## 5. Soporte oficial y actualizaciones

Para actualizaciones oficiales, soporte técnico y cualquier otra asistencia con el módulo "Monedero Prepagado y Crédito de Tienda", consulte su cuenta de cliente en MyPresta.eu. Nuestro equipo se dedica a proporcionar un soporte integral y a garantizar que su módulo funcione sin problemas.

- **Historial de Pedidos y Descargas de MyPresta.eu:** <https://mypresta.eu/my-account/orders/>
- **Contacto de Soporte de MyPresta.eu:** <https://mypresta.eu/contact>
