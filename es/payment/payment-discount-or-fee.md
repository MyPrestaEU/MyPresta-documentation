---
title: "Descuento o Recargo por Método de Pago - Manual del Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop 'Descuento o Recargo por Método de Pago' de MyPresta.eu."
sidebar:
  label: "Descuento o Recargo por Método de Pago - Manual del Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Payment Discount or Fee en MyPresta.eu](https://mypresta.eu/modules/payment-process/payment-discount-or-fee.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/payment/payment-discount-or-fee/)
>
> ---


# Descuento o Recargo por Método de Pago

## 1. Requisitos y Compatibilidad

- **Versiones de PrestaShop Soportadas**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilidad PHP**: PHP 7.1 - 8.5
- **Requisitos de Alojamiento**: Se requieren extensiones PHP estándar (cURL, JSON, OpenSSL), que suelen estar disponibles en la mayoría de los entornos de alojamiento web modernos.

## 2. Recorrido Completo por la Configuración (Cada Ajuste Agrupado por Pantalla)

El módulo "Descuento o Recargo por Método de Pago" ofrece un conjunto completo de opciones para controlar con precisión cómo se aplican los descuentos o recargos.

### 2.1 Página de Configuración del Módulo (Back Office > Módulos > Configurar > Descuento o Recargo por Método de Pago)

Esta es la pantalla de configuración principal donde habilitas y configuras el comportamiento central del módulo.

- **Habilitar Módulo:**

  - **Qué hace este ajuste:** Este es el interruptor maestro para activar o desactivar la funcionalidad del módulo en toda tu tienda.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está habilitado:* El módulo comenzará a aplicar descuentos o recargos según tus reglas definidas durante el proceso de compra.
    - *Cuando está deshabilitado:* El módulo cesará todas las operaciones y no se aplicarán descuentos ni recargos.
  - **Valor recomendado:** SÍ (una vez que hayas configurado tus reglas).
  - **Escenario / ejemplo del comerciante:** Has terminado de configurar todas tus reglas y estás listo para salir en vivo. Habilita esto para activar el módulo. Si necesitas deshabilitarlo temporalmente por mantenimiento, configúralo en NO.
- **Mostrar Recargo/Descuento en el Resumen del Carrito:**

  - **Qué hace este ajuste:** Controla si el ajuste del método de pago se muestra como un elemento de línea separado en el resumen del carrito *antes* de que el cliente llegue al paso de pago.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está habilitado:* Los clientes verán un elemento de línea como "Ajuste por Método de Pago" en el resumen de su carrito, incluso antes de seleccionar un método de pago, indicando que el precio final podría cambiar.
    - *Cuando está deshabilitado:* El ajuste solo aparecerá una vez que el cliente seleccione un método de pago en la página de pago.
  - **Valor recomendado:** SÍ (para mayor transparencia).
  - **Escenario / ejemplo del comerciante:** Quieres que los clientes estén completamente informados de los posibles ajustes de pago lo antes posible. Habilitar esto proporciona la máxima transparencia.
- **Aplicar Recargo/Descuento al Costo de Envío:**

  - **Qué hace este ajuste:** Determina si el descuento o recargo calculado también debe aplicarse al costo de envío del pedido, o solo al total del producto.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está habilitado:* Si tienes un recargo del 2%, y el total del producto es $100 y el envío es $10, el recargo será el 2% de $110 ($2.20).
    - *Cuando está deshabilitado:* El recargo del 2% solo se aplicaría al total del producto de $100 ($2.00), y el envío permanecería separado.
  - **Valor recomendado:** SÍ (si las tarifas de tu pasarela de pago también se aplican al valor total del pedido, incluido el envío).
  - **Escenario / ejemplo del comerciante:** La mayoría de las pasarelas de pago cobran una tarifa porcentual sobre el monto *total* de la transacción, incluido el envío. Habilitar esto asegura que tu tarifa refleje con precisión tus costos.
- **Aplicar Recargo/Descuento al Impuesto:**

  - **Qué hace este ajuste:** Determina si el descuento o recargo calculado también debe aplicarse al monto del impuesto del pedido, o solo al total del producto (y potencialmente al envío).
  - **Efecto de cambiar este ajuste:**
    - *Cuando está habilitado:* Si tienes un recargo del 2%, y el total del producto es $100, el envío $10 y el impuesto $20, el recargo será el 2% de $130 ($2.60).
    - *Cuando está deshabilitado:* El recargo del 2% solo se aplicaría al total del producto (y al envío si está habilitado), y el impuesto permanecería separado.
  - **Valor recomendado:** SÍ (si las tarifas de tu pasarela de pago también se aplican al valor total del pedido, incluido el impuesto).
  - **Escenario / ejemplo del comerciante:** Similar al envío, las pasarelas de pago suelen cobrar sobre el total general. Habilitar esto asegura que el cálculo de tu tarifa sea completo.
- **Etiqueta de Recargo/Descuento en Carrito/Pedido:**

  - **Qué hace este ajuste:** Te permite personalizar la etiqueta de texto que aparece junto al monto del descuento o recargo en el resumen del carrito y los detalles del pedido.
  - **Efecto de cambiar este ajuste:**
    - *Cuando se establece en "Recargo por Método de Pago":* Se mostrará este texto.
    - *Cuando se establece en "Descuento por Pago":* Se mostrará este texto.
  - **Valor recomendado:** "Ajuste por Método de Pago" o "Recargo por Pago" / "Descuento por Pago" dependiendo de tu uso principal.
  - **Escenario / ejemplo del comerciante:** Principalmente utilizas el módulo para añadir recargos. Establecer la etiqueta en "Recargo por Pago" lo deja claro para los clientes. Si ofreces descuentos, "Descuento por Pago" es más apropiado.
- **URL de Tarea Programada (Cron Job) para Limpieza del Registro de Auditoría:**

  - **Qué hace este ajuste:** Proporciona una URL que puedes configurar como una tarea programada (cron job) en tu servidor para limpiar automáticamente las entradas antiguas del registro de auditoría del módulo, evitando que la base de datos crezca demasiado.
  - **Efecto de cambiar este ajuste:**
    - *Cuando se configura como una tarea programada:* El registro de auditoría se purgará regularmente de entradas antiguas, mejorando el rendimiento de la base de datos.
    - *Cuando no se configura:* El registro de auditoría crecerá indefinidamente, lo que podría ralentizar tu Back Office con el tiempo.
  - **Valor recomendado:** Configura una tarea programada para ejecutar esta URL diaria o semanalmente.
  - **Escenario / ejemplo del comerciante:** Quieres mantener tu base de datos ligera y rápida. Copia esta URL y añádela al programador de tareas programadas de tu panel de control de alojamiento.

### 2.2 Pantalla de Administración Dedicada: Reglas de Descuento o Recargo por Método de Pago (Back Office > Pago > Reglas de Descuento o Recargo por Método de Pago)

Esta pantalla es donde defines y gestionas todas las reglas para aplicar descuentos o recargos.

- **Nombre de la Pantalla y Ubicación del Menú:** **Reglas de Descuento o Recargo por Método de Pago** (se encuentra en **Pago** en el menú principal del Back Office de PrestaShop).
- **Acciones y Ajustes Disponibles:**

  - **Tabla de Listado de Reglas:** Muestra todas tus reglas activas e inactivas actualmente, mostrando su nombre, método de pago, tipo (descuento/recargo), valor y estado.
  - **Botón "Añadir Nueva Regla":** Haz clic aquí para crear una nueva regla de descuento o recargo.
  - **Acciones de Editar/Eliminar:** Para cada regla en la lista, puedes hacer clic para editar sus detalles o eliminarla.
  - **Campos del Formulario para Añadir/Editar una Regla:**
    - **Nombre de la Regla:**
      - **Qué hace este ajuste:** Un nombre descriptivo para tu regla, visible solo en el Back Office.
      - **Efecto de cambiar este ajuste:** Te ayuda a identificar y gestionar tus reglas fácilmente.
      - **Valor recomendado:** Claro y descriptivo (por ejemplo, "Recargo PayPal 2%", "Descuento Transferencia Bancaria 5%").
    - **Método de Pago:**
      - **Qué hace este ajuste:** Selecciona a qué pasarela de pago o método específico se aplica esta regla.
      - **Efecto de cambiar este ajuste:** La regla solo se activará cuando un cliente elija este método de pago.
      - **Valor recomendado:** Elige el método de pago exacto al que quieres dirigirte.
      - **Escenario / ejemplo del comerciante:** Quieres añadir un recargo para "PayPal", así que seleccionas "PayPal" del menú desplegable.
    - **Tipo:**
      - **Qué hace este ajuste:** Determina si la regla aplica un "Descuento" o un "Recargo".
      - **Efecto de cambiar este ajuste:**
        - *Descuento:* Reduce el total del pedido.
        - *Recargo:* Aumenta el total del pedido.
      - **Valor recomendado:** Selecciona según tu objetivo (por ejemplo, "Recargo" para los costos de procesamiento de tarjetas de crédito).
    - **Valor:**
      - **Qué hace este ajuste:** La cantidad o porcentaje del descuento/recargo.
      - **Efecto de cambiar este ajuste:**
        - *Si el "Tipo" es "Porcentaje":* Introduce "2" para el 2%.
        - *Si el "Tipo" es "Cantidad Fija":* Introduce "5.00" para $5.00.
      - **Valor recomendado:** El porcentaje o cantidad fija exactos que deseas aplicar.
    - **Tipo de Valor:**
      - **Qué hace este ajuste:** Elige si el "Valor" es un "Porcentaje" del total del pedido o una "Cantidad Fija".
      - **Efecto de cambiar este ajuste:** Dicta cómo se interpreta el campo "Valor".
      - **Valor recomendado:** El porcentaje es común para los recargos; la cantidad fija para descuentos específicos.
    - **Cantidad Mínima del Carrito (Opcional):**
      - **Qué hace este ajuste:** El total mínimo del pedido (antes del descuento/recargo) requerido para que se aplique esta regla.
      - **Efecto de cambiar este ajuste:** Si el total del carrito está por debajo de esta cantidad, la regla no se aplicará.
      - **Valor recomendado:** Deja vacío si no se requiere un mínimo.
      - **Escenario / ejemplo del comerciante:** Solo quieres aplicar un recargo en pedidos grandes para evitar micro-recargos en compras pequeñas.
    - **Cantidad Máxima del Carrito (Opcional):**
      - **Qué hace este ajuste:** El total máximo del pedido (antes del descuento/recargo) para que se aplique esta regla.
      - **Efecto de cambiar este ajuste:** Si el total del carrito está por encima de esta cantidad, la regla no se aplicará.
      - **Valor recomendado:** Deja vacío si no se requiere un máximo.
    - **Grupos de Clientes (Opcional):**
      - **Qué hace este ajuste:** Restringe la regla a grupos de clientes específicos (por ejemplo, "Mayoristas", "Invitados").
      - **Efecto de cambiar este ajuste:** Solo los clientes que pertenezcan a los grupos seleccionados se verán afectados por esta regla.
      - **Valor recomendado:** Selecciona "Todos los Grupos de Clientes" a menos que tengas estrategias de precios específicas basadas en grupos.
      - **Escenario / ejemplo del comerciante:** Quieres ofrecer un descuento especial a tus "Clientes VIP" cuando pagan por transferencia bancaria.
    - **Países (Opcional):**
      - **Qué hace este ajuste:** Restringe la regla a clientes de países específicos.
      - **Efecto de cambiar este ajuste:** La regla solo se aplicará si la dirección de envío del cliente está en uno de los países seleccionados.
      - **Valor recomendado:** Selecciona "Todos los Países" a menos que tengas estrategias de pago específicas por país.
      - **Escenario / ejemplo del comerciante:** Tienes tarifas de procesamiento más altas para pagos con tarjeta de crédito internacionales de ciertas regiones.
    - **Productos a Excluir (Opcional):**
      - **Qué hace este ajuste:** Te permite especificar productos individuales que *no* deben incluirse en el cálculo del descuento o recargo.
      - **Efecto de cambiar este ajuste:** El valor de estos productos se restará del total del carrito *antes* de que se calcule el porcentaje o la cantidad fija.
      - **Valor recomendado:** Deja vacío a menos que productos específicos deban estar exentos.
      - **Escenario / ejemplo del comerciante:** Vendes algunos productos de bajo margen donde aplicar un recargo los haría no rentables, por lo que los excluyes.
    - **Estado (Habilitar/Deshabilitar):**
      - **Qué hace este ajuste:** Activa o desactiva una regla individual sin eliminarla.
      - **Efecto de cambiar este ajuste:**
        - *Habilitado:* La regla está activa y se aplicará.
        - *Deshabilitado:* La regla está inactiva y no se aplicará.
      - **Valor recomendado:** Habilitado para reglas activas.
      - **Escenario / ejemplo del comerciante:** Quieres pausar temporalmente una regla para una promoción sin perder su configuración.
- **Flujo de trabajo recomendado para la gestión diaria de la tienda:**

  1. Comienza identificando qué métodos de pago incurren en costos u ofrecen beneficios que deseas trasladar.
  2. Haz clic en "Añadir Nueva Regla".
  3. Dale a la regla un nombre claro.
  4. Selecciona el método de pago objetivo.
  5. Elige "Recargo" o "Descuento" e introduce el valor (porcentaje o fijo).
  6. Refina la regla con cantidades mínimas/máximas del carrito, grupos de clientes, países o exclusiones de productos según sea necesario.
  7. Habilita la regla y guarda.
  8. Prueba la regla en tu front office realizando un pedido de prueba.

### 2.3 Pantalla de Administración Dedicada: Registro de Auditoría de Descuento o Recargo por Método de Pago (Back Office > Pago > Registro de Auditoría de Descuento o Recargo por Método de Pago)

Esta pantalla proporciona un registro histórico de todas las instancias en las que el módulo ha aplicado un descuento o recargo.

- **Nombre de la Pantalla y Ubicación del Menú:** **Registro de Auditoría de Descuento o Recargo por Método de Pago** (se encuentra en **Pago** en el menú principal del Back Office de PrestaShop).
- **Acciones y Ajustes Disponibles:**
  - **Tabla de Listado de Registros:** Muestra entradas con detalles como:
    - **ID de Pedido:** El ID del pedido donde se aplicó el ajuste.
    - **Nombre del Cliente:** El cliente que realizó el pedido.
    - **Método de Pago:** El método de pago elegido.
    - **Regla Aplicada:** El nombre de la regla que activó el ajuste.
    - **Tipo de Ajuste:** Si fue un descuento o un recargo.
    - **Valor del Ajuste:** La cantidad del descuento o recargo.
    - **Fecha:** Cuándo se aplicó el ajuste.
  - **Filtrado y Búsqueda:** Puedes filtrar el registro por ID de pedido, cliente, método de pago o fecha para encontrar rápidamente entradas específicas.
  - **Efecto de los cambios:** Esta pantalla es solo para visualización; no puedes modificar directamente las entradas del registro aquí. Sirve como un registro valioso para la resolución de problemas y el análisis.
- **Flujo de trabajo recomendado para la gestión diaria de la tienda:**
  - Revisa regularmente el registro de auditoría para asegurarte de que las reglas se aplican correctamente.
  - Úsalo para solucionar consultas de clientes sobre discrepancias de precios.
  - Supervisa el volumen de ajustes para comprender el impacto de tus reglas.

### 2.4 Tabla de Referencia Rápida de Configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| **Configuración del Módulo** | Habilitar Módulo | SÍ | Interruptor maestro para la funcionalidad del módulo. |
|  | Mostrar Recargo/Descuento en el Resumen del Carrito | SÍ | Muestra el ajuste temprano en el carrito para mayor transparencia. |
|  | Aplicar Recargo/Descuento al Costo de Envío | SÍ | Incluye el envío en el cálculo del recargo/descuento. |
|  | Aplicar Recargo/Descuento al Impuesto | SÍ | Incluye el impuesto en el cálculo del recargo/descuento. |
|  | Etiqueta de Recargo/Descuento en Carrito/Pedido | "Ajuste por Método de Pago" | Personaliza la etiqueta mostrada a los clientes. |
|  | URL de Tarea Programada (Cron Job) para Limpieza del Registro de Auditoría | (URL proporcionada) | Automatiza la limpieza de entradas antiguas del registro de auditoría. |
| **Reglas de Descuento o Recargo por Método de Pago** | Nombre de la Regla | (Nombre descriptivo) | Nombre interno de la regla. |
|  | Método de Pago | (Método específico) | Selecciona el método de pago para la regla. |
|  | Tipo | Recargo / Descuento | Determina si es un aumento o una disminución. |
|  | Valor | (Valor numérico) | La cantidad o porcentaje del ajuste. |
|  | Tipo de Valor | Porcentaje / Cantidad Fija | Cómo se interpreta el 'Valor'. |
|  | Cantidad Mínima del Carrito | (Vacío) | Total mínimo del pedido para que se aplique la regla. |
|  | Cantidad Máxima del Carrito | (Vacío) | Total máximo del pedido para que se aplique la regla. |
|  | Grupos de Clientes | Todos los Grupos de Clientes | Restringe la regla a grupos de clientes específicos. |
|  | Países | Todos los Países | Restringe la regla a países específicos. |
|  | Productos a Excluir | (Vacío) | Productos cuyo valor se excluye del cálculo. |
|  | Estado | Habilitado | Activa o desactiva la regla. |
| **Registro de Auditoría de Descuento o Recargo por Método de Pago** | (Todos los campos) | (Solo Vista) | Proporciona un registro histórico de los ajustes aplicados. |

## 3. Resolución de Problemas del Comerciante y Preguntas Frecuentes (FAQ)

**P1: Mis descuentos/recargos no aparecen en la página de pago. ¿Qué debo verificar?**
R1:

- **¿Módulo Habilitado?** Ve a **Módulos > Gestor de Módulos** y asegúrate de que "Descuento o Recargo por Método de Pago" esté habilitado.
- **¿Reglas Activas?** Navega a **Pago > Reglas de Descuento o Recargo por Método de Pago** y verifica que tus reglas específicas estén habilitadas (columna Estado).
- **¿Condiciones de la Regla Cumplidas?** Vuelve a verificar si el total del carrito, el grupo de clientes, el país o las condiciones de productos excluidos de tus reglas se cumplen con tu pedido de prueba.
- **¿Método de Pago Seleccionado?** El ajuste solo aparece *después* de seleccionar un método de pago en la página de pago (a menos que "Mostrar Recargo/Descuento en el Resumen del Carrito" esté habilitado).
- **Borrar Caché:** Ve a **Parámetros Avanzados > Rendimiento** y haz clic en "Borrar caché" (arriba a la derecha). A veces, los datos antiguos en caché impiden que los cambios aparezcan inmediatamente.

**P2: El monto del descuento/recargo parece incorrecto.**
R2:

- **Tipo de Valor (Porcentaje vs. Fijo):** Asegúrate de haber seleccionado el "Tipo de Valor" correcto (Porcentaje o Cantidad Fija) para tu regla.
- **Aplicar a Envío/Impuesto:** Verifica en la configuración principal del módulo si "Aplicar Recargo/Descuento al Costo de Envío" y "Aplicar Recargo/Descuento al Impuesto" están habilitados o deshabilitados, ya que esto afecta el monto base para los cálculos porcentuales.
- **Productos Excluidos:** Si tienes productos excluidos del cálculo, asegúrate de que su valor se reste correctamente antes de aplicar el porcentaje/cantidad fija.
- **Moneda:** Asegúrate de que la moneda predeterminada de tu tienda esté configurada correctamente en PrestaShop, ya que el módulo se basa en esto para las cantidades fijas.

**P3: El módulo está causando un conflicto con otro módulo o mi tema.**
R3:

- **Identifica el Conflicto:** Intenta deshabilitar otros módulos uno por uno para identificar cuál está causando el conflicto.
- **Sobreescrituras del Tema:** Si tienes un tema muy personalizado, podría estar sobrescribiendo las plantillas de pago principales de PrestaShop en las que se basa el módulo. Revisa la carpeta `templates/checkout/` de tu tema en busca de archivos como `payment.tpl` o `cart-summary.tpl`.
- **Contacta con Soporte:** Si sospechas un conflicto, reúne los detalles (mensajes de error, pasos para reproducir) y contacta con el soporte de MyPresta.eu.

**P4: ¿Cómo traduzco la "Etiqueta de Recargo/Descuento" a otros idiomas?**
R4:

- Ve a **Internacional > Traducciones**.
- Selecciona "Traducciones de módulos instalados", tu tema y el idioma que deseas traducir.
- Busca el módulo "Descuento o Recargo por Método de Pago". Deberías ver el campo para traducir la configuración "Etiqueta de Recargo/Descuento en Carrito/Pedido".

**P5: Mi registro de auditoría se está haciendo demasiado grande. ¿Cómo lo gestiono?**
R5:

- En la configuración principal del módulo, encontrarás una "URL de Tarea Programada (Cron Job) para Limpieza del Registro de Auditoría".
- Copia esta URL y configúrala como una tarea programada en tu servidor de alojamiento. La mayoría de los paneles de control de alojamiento (cPanel, Plesk) tienen una sección de "Tareas Programadas" donde puedes añadir una nueva tarea.
- Configúrala para que se ejecute diaria o semanalmente (por ejemplo, `wget -q -O /dev/null "TU_URL_CRON_AQUI"`). Esto eliminará automáticamente las entradas de registro antiguas y mantendrá tu base de datos optimizada.

## 4. Guía para Desarrolladores y Webmasters (Arquitectura Técnica y Mapa de Código)

Esta sección proporciona una descripción técnica detallada del módulo "Descuento o Recargo por Método de Pago" para desarrolladores, webmasters y agencias técnicas.

### 4.1 Visión General de la Arquitectura

El módulo "Descuento o Recargo por Método de Pago" sigue un patrón MVC (Modelo-Vista-Controlador) estándar de PrestaShop, con un fuerte énfasis en los hooks para integrarse en el flujo de pago. Utiliza `ObjectModel` para gestionar reglas y registros de auditoría, y controladores personalizados tanto para interacciones AJAX del front-office como para la gestión del back-office. La lógica central para calcular y aplicar recargos/descuentos está encapsulada en clases de motor dedicadas, asegurando la separación de preocupaciones. Se utilizan clases de compatibilidad para salvar las diferencias entre PrestaShop 1.7, 8 y 9.

### 4.2 Controladores (`controllers/`)

#### Controladores del Front-Office

- `controllers/front/ajax.php`
  - **Nombre de la Clase:** `PaydisorfeeAjaxModuleFrontController` (extiende `ModuleFrontController`)
  - **Responsabilidad:** Maneja las solicitudes AJAX de la página de pago. Cuando un cliente selecciona un método de pago, este controlador recibe la solicitud, calcula el descuento/recargo aplicable basándose en las reglas activas y devuelve los datos actualizados del resumen del carrito (por ejemplo, nuevo total, elemento de línea de recargo/descuento) para que se muestren dinámicamente.
- `controllers/front/cron.php`
  - **Nombre de la Clase:** `PaydisorfeeCronModuleFrontController` (extiende `ModuleFrontController`)
  - **Responsabilidad:** Proporciona el endpoint para la tarea programada de limpieza del registro de auditoría. Cuando se accede, activa la lógica de limpieza dentro del módulo, eliminando entradas de registro antiguas basándose en las políticas de retención configuradas.
- `controllers/front/index.php`
  - **Nombre de la Clase:** `PaydisorfeeIndexModuleFrontController` (extiende `ModuleFrontController`)
  - **Responsabilidad:** Un controlador frontal de marcador de posición, típicamente utilizado para páginas de módulo predeterminadas o para evitar la lista de directorios. En este módulo, su función principal podría ser manejar el enrutamiento predeterminado si no se solicita ninguna acción específica, o podría redirigir a la página principal de la tienda.

#### Controladores de Administración del Back-Office

- `controllers/admin/AdminPaydisorfeeAuditLog.php`
  - **Nombre de la Clase:** `AdminPaydisorfeeAuditLogController` (extiende `ModuleAdminController`)
  - **Nombre de la Pestaña:** Registro de Auditoría de Descuento o Recargo por Método de Pago
  - **Entidad Gestionada:** `PaydisorfeeAuditLog` (se mapea a la tabla de base de datos `paydisorfee_log`)
  - **Responsabilidad:** Gestiona la visualización y el filtrado de las entradas del registro de auditoría en el Back Office de PrestaShop. Utiliza `HelperList` para renderizar la vista de cuadrícula de los registros.
- `controllers/admin/AdminPaydisorfeeRules.php`
  - **Nombre de la Clase:** `AdminPaydisorfeeRulesController` (extiende `ModuleAdminController`)
  - **Nombre de la Pestaña:** Reglas de Descuento o Recargo por Método de Pago
  - **Entidad Gestionada:** `PaydisorfeeRule` (se mapea a la tabla de base de datos `paydisorfee_rule`)
  - **Responsabilidad:** Proporciona la interfaz para crear, editar, eliminar y listar reglas de descuento/recargo por pago. Utiliza `HelperList` para la descripción general de las reglas y `HelperForm` para los formularios de añadir/editar reglas, incluyendo selectores dinámicos para productos, grupos de clientes y países.
- `controllers/admin/index.php`
  - **Nombre de la Clase:** `PaydisorfeeAdminIndexModuleFrontController` (extiende `ModuleAdminController`)
  - **Responsabilidad:** Similar al `index.php` frontal, este podría servir como un controlador de administración predeterminado o un redirigidor si no se solicita ninguna acción específica para el contexto de administración.

### 4.3 Clases y Modelos Principales (`classes/`)

- `classes/index.php`: Archivo vacío estándar para evitar la lista de directorios.
- `classes/PaydisorfeeAdmin.php`
  - **Responsabilidad:** Probablemente contiene métodos de ayuda o funciones de utilidad específicas para la administración del Back Office, potencialmente para manejar envíos de formularios, validación de datos o renderización de componentes de administración específicos.
- `classes/PaydisorfeeAuditLog.php`
  - **Extiende:** `ObjectModel`
  - **Tabla de Base de Datos:** `paydisorfee_log`
  - **Campos `$definition`:** Define la estructura de las entradas del registro de auditoría (por ejemplo, `id_order`, `id_customer`, `payment_method`, `rule_name`, `type`, `value`, `date_add`).
  - **Métodos Públicos Clave:** Métodos para añadir nuevas entradas de registro, recuperar datos de registro y, potencialmente, para operaciones de limpieza.
- `classes/PaydisorfeeCartState.php`
  - **Responsabilidad:** Gestiona el estado del carrito durante el proceso de pago, específicamente relacionado con el descuento/recargo aplicado por el módulo. Probablemente almacena y recupera el ajuste calculado para asegurar que persista en los diferentes pasos del pago y se aplique correctamente al pedido.
- `classes/PaydisorfeeCompatibility.php`
  - **Responsabilidad:** Contiene métodos para manejar problemas de compatibilidad entre diferentes versiones de PrestaShop (1.7.x, 8.x, 9.x). Esta clase abstrae el código específico de la versión, como las diferencias en los nombres de los hooks, las estructuras de las clases o las llamadas a la API, asegurando que el módulo funcione correctamente en todas las versiones compatibles.
- `classes/PaydisorfeeDashboard.php`
  - **Responsabilidad:** Probablemente proporciona datos o lógica para una posible vista de panel o análisis dentro de la interfaz de administración del módulo, resumiendo el impacto de los descuentos/recargos.
- `classes/PaydisorfeeEngine.php`
  - **Responsabilidad:** Esta es la clase de lógica central para calcular y aplicar el descuento o recargo. Toma el carrito actual, el método de pago seleccionado y las reglas activas como entrada, luego determina el monto final del ajuste. Maneja cálculos de porcentaje vs. fijos, montos mínimos/máximos del carrito y exclusiones de productos.
- `classes/PaydisorfeeFeeProduct.php`
  - **Responsabilidad:** Potencialmente una clase de ayuda para crear un "producto virtual" que represente el recargo/descuento en el carrito, permitiendo que se muestre como un elemento de línea. Esta es una técnica común en PrestaShop para integrar ajustes de precios dinámicos en el resumen del carrito.
- `classes/PaydisorfeeLog.php`
  - **Responsabilidad:** Esto podría ser un alias o una versión anterior de `PaydisorfeeAuditLog.php`, o un mecanismo de registro más simple para fines de depuración.
- `classes/PaydisorfeeRule.php`
  - **Extiende:** `ObjectModel`
  - **Tabla de Base de Datos:** `paydisorfee_rule`
  - **Campos `$definition`:** Define la estructura de una regla de pago (por ejemplo, `name`, `id_payment_module`, `type`, `value`, `value_type`, `min_cart_amount`, `max_cart_amount`, `customer_groups`, `countries`, `excluded_products`, `active`).
  - **Métodos Públicos Clave:** Métodos para operaciones CRUD en reglas, recuperación de reglas activas y validación de condiciones de reglas.

### 4.4 Activos JavaScript (`views/js/`)

- `paydisorfee/lib/searchTool/views/js/autocomplete.js`
  - **Alcance:** Back-office (utilizado en `AdminPaydisorfeeRules` para el selector de exclusión de productos).
  - **Descripción:** Proporciona funcionalidad de autocompletado para buscar productos al configurar el campo "Productos a Excluir" en una regla. Probablemente envía solicitudes AJAX a un controlador de back-office para obtener sugerencias de productos.
- `paydisorfee/views/js/adminPaydisorfeeDashboard.js`
  - **Alcance:** Back-office (si existe una vista de panel).
  - **Descripción:** JavaScript para cualquier función de panel o análisis dentro de la interfaz de administración del módulo. Esto podría incluir la representación de gráficos, el filtrado de datos o la carga dinámica de contenido.
- `paydisorfee/views/js/adminPaydisorfeeSelector.js`
  - **Alcance:** Back-office (utilizado en `AdminPaydisorfeeRules`).
  - **Descripción:** Maneja la selección dinámica de grupos de clientes, países y, potencialmente, métodos de pago dentro del formulario de configuración de reglas. Podría gestionar cuadros de selección múltiple o proporcionar elementos interactivos para estos campos.
- `paydisorfee/views/js/checkout.js`
  - **Alcance:** Front-office (página de pago).
  - **Descripción:** Este es un script crítico para la funcionalidad del front-office. Escucha los cambios en el método de pago seleccionado en la página de pago. Cuando se elige un método de pago, activa una llamada AJAX a `controllers/front/ajax.php` para recalcular el total del carrito y actualizar dinámicamente el resumen del pedido con el nuevo elemento de línea de descuento/recargo. También maneja la lógica de visualización para estas actualizaciones.

### 4.5 Hojas de Estilo CSS (`views/css/`)

- `paydisorfee/lib/searchTool/views/css/autocomplete.css`
  - **Alcance:** Back-office.
  - **Descripción:** Estilos para la entrada de búsqueda de autocompletado y su menú desplegable de sugerencias, utilizado en el selector de exclusión de productos dentro de la configuración de reglas.
- `paydisorfee/views/css/admin_paydisorfee.css`
  - **Alcance:** Back-office.
  - **Descripción:** Estilo general para las páginas del Back Office del módulo, incluyendo la lista de reglas, el registro de auditoría y los formularios de configuración. Asegura una apariencia consistente con el tema de administración de PrestaShop.
- `paydisorfee/views/css/front.css`
  - **Alcance:** Front-office.
  - **Descripción:** Estilos para mostrar el elemento de línea de descuento/recargo y cualquier mensaje relacionado en la página de pago o el resumen del carrito. Asegura que el ajuste sea claramente visible y esté bien integrado en el diseño de la tienda.

### 4.6 Estructura de Plantillas Smarty (`views/templates/`)

- `paydisorfee/lib/searchTool/views/scripts.tpl`
  - **Alcance:** Back-office.
  - **Descripción:** Contiene código Smarty para incluir JavaScript y potencialmente CSS para la herramienta de búsqueda (por ejemplo, `autocomplete.js`). Es probable que se incluya en el formulario `AdminPaydisorfeeRules`.
- `paydisorfee/views/templates/admin/auditPreview.tpl`
  - **Alcance:** Back-office (`AdminPaydisorfeeAuditLogController`).
  - **Descripción:** Plantilla para renderizar las entradas del registro de auditoría, típicamente utilizada por `HelperList` para mostrar la cuadrícula de datos.
- `paydisorfee/views/templates/admin/cron_setup.tpl`
  - **Alcance:** Back-office (Configuración Principal del Módulo).
  - **Descripción:** Muestra la URL de la tarea programada e instrucciones para configurarla, como se ve en la página de configuración principal del módulo.
- `paydisorfee/views/templates/admin/rulesPreview.tpl`
  - **Alcance:** Back-office (`AdminPaydisorfeeRulesController`).
  - **Descripción:** Plantilla para renderizar la lista de reglas de pago, utilizada por `HelperList` para mostrar la cuadrícula de datos.
- `paydisorfee/views/templates/admin/scopeSelector.tpl`
  - **Alcance:** Back-office (`AdminPaydisorfeeRulesController`).
  - **Descripción:** Plantilla para los selectores dinámicos (grupos de clientes, países, productos a excluir) dentro del formulario de configuración de reglas, a menudo utilizada junto con `adminPaydisorfeeSelector.js`.
- `paydisorfee/views/templates/hook/admin_order.tpl`
  - **Alcance:** Back-office (Hook `displayAdminOrderTabContent` o similar).
  - **Descripción:** Muestra información sobre el descuento o recargo por pago aplicado dentro de la página de detalles del pedido de PrestaShop en el Back Office. Esto permite a los administradores ver el ajuste directamente en el pedido.
- `paydisorfee/views/templates/hook/payment_top.tpl`
  - **Alcance:** Front-office (Hook `displayPaymentTop` o similar).
  - **Descripción:** Esta plantilla probablemente se utiliza para mostrar la información dinámica de descuento/recargo en la página de pago, generalmente encima de la selección del método de pago, o como parte del resumen del pedido. Se actualiza mediante `checkout.js` a través de AJAX.

### 4.7 Esquema de Base de Datos y Mapa de Hooks

#### Tablas de Base de Datos

- `ps_paydisorfee_log`: Almacena entradas del registro de auditoría para cada descuento o recargo aplicado.
  - `id_paydisorfee_log` (CLAVE PRIMARIA)
  - `id_order` (INT)
  - `id_customer` (INT)
  - `payment_method` (VARCHAR)
  - `rule_name` (VARCHAR)
  - `type` (VARCHAR, 'discount' o 'fee')
  - `value` (DECIMAL)
  - `date_add` (DATETIME)
- `ps_paydisorfee_rule`: Almacena la configuración de cada regla de descuento/recargo por pago.
  - `id_paydisorfee_rule` (CLAVE PRIMARIA)
  - `name` (VARCHAR)
  - `id_payment_module` (INT)
  - `type` (VARCHAR, 'discount' o 'fee')
  - `value` (DECIMAL)
  - `value_type` (VARCHAR, 'percentage' o 'fixed')
  - `min_cart_amount` (DECIMAL)
  - `max_cart_amount` (DECIMAL)
  - `customer_groups` (TEXT, array serializado de IDs)
  - `countries` (TEXT, array serializado de IDs)
  - `excluded_products` (TEXT, array serializado de IDs)
  - `active` (TINYINT)
  - `date_add` (DATETIME)
  - `date_upd` (DATETIME)
- `ps_configuration`: La configuración del módulo se almacena aquí con claves como `PAYDISORFEE_ENABLED`, `PAYDISORFEE_DISPLAY_CART`, `PAYDISORFEE_APPLY_SHIPPING`, `PAYDISORFEE_APPLY_TAX`, `PAYDISORFEE_LABEL`.

#### Tabla de Hooks Registrados

| Nombre del Hook | Momento de Ejecución | Propósito Técnico |
| --- | --- | --- |
| `actionFrontControllerSetMedia` | Antes de que el controlador frontal renderice | Registra CSS (`front.css`) y JS (`checkout.js`) del front-office. |
| `actionAdminControllerSetMedia` | Antes de que el controlador de administración renderice | Registra CSS (`admin_paydisorfee.css`, `autocomplete.css`) y JS (`adminPaydisorfeeDashboard.js`, `adminPaydisorfeeSelector.js`, `autocomplete.js`) del back-office. |
| `displayHeader` | En la sección `<head>` de cada página | Potencialmente para cargar JS/CSS globales o metaetiquetas. |
| `displayPaymentTop` | En la parte superior del bloque de selección de pago en la página de pago | Muestra la información dinámica de recargo/descuento al cliente. |
| `actionCartSummary` | Después de que se genera el resumen del carrito | Se utiliza para inyectar el elemento de línea de recargo/descuento en el resumen del carrito. |
| `actionPaymentConfirmation` | Después de que un pedido se realiza con éxito | Registra el descuento/recargo aplicado en el registro de auditoría. |
| `actionValidateOrder` | Cuando se valida un pedido | Asegura que el total final del pedido refleje el ajuste del método de pago. |
| `displayAdminOrderTabContent` | Dentro de la página de detalles del pedido en el Back Office | Muestra los detalles del ajuste de pago para el pedido. |
| `displayAdminOrder` | En la página de detalles del pedido en el Back Office | Similar a `displayAdminOrderTabContent`, para mostrar datos del módulo específicos del pedido. |
| `actionGetExtraMailTemplateVars` | Antes de enviar un correo electrónico de confirmación de pedido | Inyecta los detalles de recargo/descuento en las plantillas de correo electrónico. |
| `actionObjectOrderAddAfter` | Después de que se añade un nuevo objeto de pedido | Potencialmente para procesamiento final o registro relacionado con el pedido. |
| `actionObjectOrderUpdateAfter` | Después de que se actualiza un objeto de pedido | Potencialmente para reevaluar tarifas si se modifica un pedido. |
| `actionObjectCartUpdateAfter` | Después de que se actualiza un objeto de carrito | Activa el recálculo de posibles recargos/descuentos. |
| `actionObjectCartAddAfter` | Después de que se añade un nuevo objeto de carrito | Activa el recálculo de posibles recargos/descuentos. |
| `actionAjaxDie` | Antes de `die()` en el contexto AJAX | Permite que el módulo realice acciones antes de que se envíe la respuesta AJAX. |
| `displayBackOfficeHeader` | En la sección `<head>` de cada página del Back Office | Registra JS/CSS de administración global. |
| `displayModuleConfigureExtraButtons` | En la página de configuración del módulo | Añade botones adicionales (por ejemplo, "Gestionar Reglas", "Ver Registro de Auditoría"). |
| `displayPaymentOptions` | Muestra las opciones de pago en el proceso de compra | Potencialmente modifica las opciones de pago según las reglas. |
| `actionPaymentOptionsModifier` | Modifica las opciones de pago antes de la visualización | Permite que el módulo añada/elimine/modifique las opciones de pago. |

## 5. Soporte Oficial y Actualizaciones

Para las últimas actualizaciones, correcciones de errores y soporte oficial para el módulo "Descuento o Recargo por Método de Pago", consulta tu cuenta de cliente en [MyPresta.eu](https://mypresta.eu). Nuestro equipo de soporte está disponible para ayudarte con cualquier problema o pregunta relacionada con la funcionalidad e integración del módulo.
