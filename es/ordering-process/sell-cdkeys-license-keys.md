---
title: "Vender CDKeys / Claves de licencia - Manual de comerciante y guía de configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop 'Vender CDKeys / Claves de licencia' de MyPresta.eu."
sidebar:
  label: "Vender CDKeys / Claves de licencia - Manual de comerciante y guía de configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Sell CDKeys / License keys en MyPresta.eu](https://mypresta.eu/modules/ordering-process/sell-cdkeys-license-keys.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/ordering-process/sell-cdkeys-license-keys/)
>
> ---


# Vender CDKeys / Claves de licencia

## 1. Requisitos y compatibilidad

- **Versiones de PrestaShop compatibles**: PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilidad con PHP**: PHP 5.6 - 8.5
- **Requisitos de alojamiento**: Las extensiones PHP estándar (cURL, JSON, OpenSSL) suelen ser suficientes. Por lo general, no se necesitan configuraciones especiales del servidor más allá de un entorno de alojamiento PrestaShop estándar.

## 2. Recorrido completo de configuración (Cada ajuste agrupado por pantalla)

### 2.1 Página de configuración del módulo (Back Office > Módulos > Configurar > Vender CDKeys / Claves de licencia)

Esta es el área de configuración principal donde define cómo se comporta el módulo, cuándo enviar claves y la configuración general.

#### Pestaña de Configuración General

-   **Activado:**

    -   **Qué hace esta configuración:** Este es el interruptor maestro para activar o desactivar la funcionalidad principal del módulo.
    -   **Efecto de cambiar esta configuración:**
        -   *Cuando está activado:* El módulo procesará pedidos, enviará claves de CD y mostrará las claves del cliente en el front office de acuerdo con sus otras configuraciones.
        -   *Cuando está desactivado:* El módulo detendrá todas sus operaciones. No se enviarán claves automáticamente, y la sección "Mis claves" del cliente podría desaparecer o quedar inactiva.
    -   **Valor recomendado:** SÍ
    -   **Escenario / ejemplo de comerciante:** Actívelo una vez que haya configurado todo para comenzar a vender claves. Desactívelo temporalmente si necesita realizar mantenimiento o dejar de vender claves digitales.
-   **Seleccionar estados de pedido:**

    -   **Qué hace esta configuración:** Determina qué estados de pedido activarán el envío automático de claves de CD a los clientes. Puede seleccionar varios estados.
    -   **Efecto de cambiar esta configuración:**
        -   *Cuando se alcanza un estado seleccionado:* El módulo verificará el pedido en busca de productos con clave de CD y enviará las claves.
        -   *Cuando se alcanza un estado no seleccionado:* No se enviarán claves, incluso si el pedido contiene productos con clave de CD.
    -   **Valor recomendado:** "Pago aceptado" y, potencialmente, "Entregado" si desea asegurarse de que los productos físicos también se entreguen primero.
    -   **Escenario / ejemplo de comerciante:** Si desea que las claves se envíen inmediatamente después del pago, seleccione "Pago aceptado". Si utiliza un método de pago manual como transferencia bancaria, podría seleccionar "Pago aceptado" después de haber confirmado manualmente el pago.
-   **Grupos de clientes permitidos para recibir cdkey:**

    -   **Qué hace esta configuración:** Le permite restringir la entrega de claves de CD a grupos de clientes específicos (por ejemplo, "Clientes", "Visitantes", "Invitados").
    -   **Efecto de cambiar esta configuración:**
        -   *Cuando un cliente está en un grupo seleccionado:* Recibirá claves de CD si se cumplen todas las demás condiciones.
        -   *Cuando un cliente NO está en un grupo seleccionado:* No recibirá claves de CD, incluso si compra un producto con clave de CD.
    -   **Valor recomendado:** "Cliente" (e "Invitado" si permite pagos de invitados para productos digitales).
    -   **Escenario / ejemplo de comerciante:** Podría restringir esto a "Clientes" si desea fomentar la creación de cuentas o si tiene grupos B2B especiales que reciben diferentes tipos de claves.
-   **Valor máximo del pedido:**

    -   **Qué hace esta configuración:** Establece un límite superior en el valor total de un pedido para el cual se enviarán automáticamente las claves de CD. Los pedidos que superen este valor no activarán la entrega automática de claves.
    -   **Efecto de cambiar esta configuración:**
        -   *Total del pedido inferior o igual al máximo:* Las claves se envían automáticamente.
        -   *Total del pedido superior al máximo:* Las claves NO se envían automáticamente. Tendría que enviarlas manualmente.
    -   **Valor recomendado:** Dejar vacío o establecer un valor muy alto (por ejemplo, 999999) si no desea ninguna restricción de valor.
    -   **Escenario / ejemplo de comerciante:** Utilice esto como medida de prevención de fraude. Si nota muchos pedidos fraudulentos de alto valor, podría establecer un límite para revisarlos manualmente antes de liberar claves costosas.
-   **Enviar muchos códigos en un solo correo:**

    -   **Qué hace esta configuración:** Controla si se envían varias claves de CD para el mismo producto en un solo pedido en un solo correo electrónico o en correos electrónicos separados.
    -   **Efecto de cambiar esta configuración:**
        -   *Cuando está activado:* Si un cliente compra 3 unidades de "Juego X", recibirá un correo electrónico que contiene las 3 claves de "Juego X".
        -   *Cuando está desactivado:* Si un cliente compra 3 unidades de "Juego X", recibirá 3 correos electrónicos separados, cada uno con una clave de "Juego X".
    -   **Valor recomendado:** SÍ (generalmente mejor para la experiencia del cliente y reduce el desorden de correos electrónicos).
    -   **Escenario / ejemplo de comerciante:** Si un cliente compra un "paquete de 4" de un juego, enviar las 4 claves en un solo correo electrónico es mucho más claro que 4 correos electrónicos separados.
-   **Título del correo electrónico:**

    -   **Qué hace esta configuración:** Le permite personalizar la línea de asunto del correo electrónico enviado a los clientes que contiene sus claves de CD.
    -   **Efecto de cambiar esta configuración:** La línea de asunto del correo electrónico reflejará su título personalizado, lo que facilitará a los clientes la identificación del correo electrónico.
    -   **Valor recomendado:** Algo claro y profesional, por ejemplo, "Sus claves / licencias de [Nombre de su tienda] - Pedido #[ID de pedido]".
    -   **Escenario / ejemplo de comerciante:** Una línea de asunto clara como "Sus claves de juego para el pedido #12345" ayuda a los clientes a encontrar rápidamente sus claves.
-   **Cambiar estado del pedido:**

    -   **Qué hace esta configuración:** Después de que las claves de CD se envían correctamente, esta opción le permite cambiar automáticamente el estado del pedido a un nuevo estado especificado.
    -   **Efecto de cambiar esta configuración:**
        -   *Cuando está activado y se selecciona un estado:* El estado del pedido se actualizará automáticamente (por ejemplo, de "Pago aceptado" a "Claves de CD enviadas").
        -   *Cuando está desactivado:* El estado del pedido permanecerá como estaba después del activador inicial (por ejemplo, "Pago aceptado").
    -   **Valor recomendado:** SÍ, y seleccione un estado distinto como "Claves de CD enviadas" (es posible que deba crear este estado en PrestaShop > Estados de pedido).
    -   **Escenario / ejemplo de comerciante:** Esto le ayuda a identificar rápidamente los pedidos para los que ya se han entregado las claves, mejorando su flujo de trabajo de gestión de pedidos.
-   **Seleccionar estado del pedido (para cambio de estado):**

    -   **Qué hace esta configuración:** Si "Cambiar estado del pedido" está activado, este menú desplegable le permite elegir el estado de pedido específico que se aplicará después de enviar las claves.
    -   **Efecto de cambiar esta configuración:** El estado elegido se aplicará al pedido.
    -   **Valor recomendado:** Un estado personalizado como "Claves de CD enviadas" o "Producto digital entregado".
    -   **Escenario / ejemplo de comerciante:** La creación de un estado específico como "Claves de CD enviadas" le permite filtrar pedidos y ver exactamente cuáles han tenido sus productos digitales cumplidos.
-   **Incluir claves en la factura:**

    -   **Qué hace esta configuración:** Determina si las claves de CD entregadas también deben imprimirse en la factura del cliente.
    -   **Efecto de cambiar esta configuración:**
        -   *Cuando está activado:* Las claves aparecerán en la factura PDF generada para el pedido.
        -   *Cuando está desactivado:* Las claves solo se enviarán por correo electrónico y/o aparecerán en la sección "Mis claves", pero no en la factura.
    -   **Valor recomendado:** SÍ (proporciona un registro adicional para el cliente).
    -   **Escenario / ejemplo de comerciante:** Algunos clientes prefieren tener todos los detalles de la compra, incluidas las claves, en su factura para fines de registro o impuestos.
-   **Activar paginación:**

    -   **Qué hace esta configuración:** Habilita la paginación para la lista de claves de CD que se muestra en la sección "Mis claves" del cliente en el front office.
    -   **Efecto de cambiar esta configuración:**
        -   *Cuando está activado:* Si un cliente tiene muchas claves, se mostrarán en varias páginas, mejorando los tiempos de carga y la legibilidad.
        -   *Cuando está desactivado:* Todas las claves se enumerarán en una sola página.
    -   **Valor recomendado:** SÍ (especialmente si los clientes pueden acumular muchas claves).
    -   **Escenario / ejemplo de comerciante:** Un cliente que compra regularmente claves de juegos apreciará la paginación para encontrar rápidamente claves específicas sin tener que desplazarse por una lista muy larga.
-   **Número de elementos de paginación:**

    -   **Qué hace esta configuración:** Si la paginación está activada, esto establece cuántas claves de CD se muestran por página en la sección "Mis claves" del cliente.
    -   **Efecto de cambiar esta configuración:** Controla la densidad de la lista de claves en cada página.
    -   **Valor recomendado:** 10-20 (un buen equilibrio para la legibilidad).
    -   **Escenario / ejemplo de comerciante:** Establecer esto en 15 significa que un cliente con 30 claves verá 2 páginas de claves.

#### Pestaña de Configuración de Importación CSV

-   **Delimitador de fila del archivo CSV:**

    -   **Qué hace esta configuración:** Especifica el carácter utilizado para separar filas individuales (líneas) en su archivo CSV al importar claves de CD.
    -   **Efecto de cambiar esta configuración:** El módulo utiliza este carácter para analizar correctamente su archivo CSV en entradas de clave individuales. Un delimitador incorrecto provocará errores de importación.
    -   **Valor recomendado:** `\n` (carácter de nueva línea, estándar para la mayoría de los archivos CSV).
    -   **Escenario / ejemplo de comerciante:** Si su lista de claves es `clave1\nclave2\nclave3`, el módulo necesita saber que `\n` separa cada clave.
-   **Delimitador de columna del archivo CSV:**

    -   **Qué hace esta configuración:** Especifica el carácter utilizado para separar columnas (campos) dentro de cada fila de su archivo CSV al importar claves de CD.
    -   **Efecto de cambiar esta configuración:** El módulo utiliza este carácter para identificar correctamente diferentes puntos de datos (por ejemplo, clave, ID de grupo) dentro de cada fila. Un delimitador incorrecto provocará errores de importación.
    -   **Valor recomendado:** `;` (punto y coma) o `,` (coma), dependiendo de cómo se generen sus archivos CSV.
    -   **Escenario / ejemplo de comerciante:** Si su CSV es `clave1;id_producto_1;id_grupo_1`, el módulo necesita saber que `;` separa los campos.

#### Pestaña de Análisis y Fraude

-   **CDKEYS\_ANALYTICS\_DEFAULT\_CHART, CDKEYS\_ANALYTICS\_PERIOD, CDKEYS\_ANALYTICS\_CHART\_DAYS, CDKEYS\_ANALYTICS\_CHART\_WEEKS, CDKEYS\_ANALYTICS\_CHART\_MONTHS, CDKEYS\_ANALYTICS\_PREDICTION\_DAYS, CDKEYS\_ANALYTICS\_TOP\_LIMIT, CDKEYS\_ANALYTICS\_MIN\_SALES, CDKEYS\_ANALYTICS\_SHOW\_EMPTY\_GROUPS, CDKEYS\_ANALYTICS\_INCLUDE\_INACTIVE:**

    -   **Qué hacen estas configuraciones:** Estas son claves de configuración internas relacionadas con el panel de análisis y detección de fraude del módulo. Controlan cómo se muestran, agregan y filtran los datos dentro de la sección de análisis del back-office del módulo.
    -   **Efecto de cambiar estas configuraciones:** Ajusta la representación visual y los puntos de datos que se muestran en el panel del módulo, ayudándole a monitorear las ventas clave y los posibles patrones de fraude.
    -   **Valor recomendado:** Los valores predeterminados suelen ser adecuados. Ajústelos solo si necesita vistas de informes específicas.
    -   **Escenario / ejemplo de comerciante:** Podría ajustar `CDKEYS_ANALYTICS_PERIOD` para ver las tendencias de ventas durante una semana en lugar de un mes, o `CDKEYS_ANALYTICS_TOP_LIMIT` para ver más grupos de claves más vendidos.
-   **CDKEYS\_ALERT\_COOLDOWN\_HOURS:**

    -   **Qué hace esta configuración:** Define un período de enfriamiento en horas para las alertas de fraude. Si se activa una alerta para un cliente, no se activará otra alerta para el mismo cliente dentro de este período de enfriamiento.
    -   **Efecto de cambiar esta configuración:** Evita el spam de alertas por intentos fraudulentos repetidos del mismo cliente en un corto período de tiempo.
    -   **Valor recomendado:** 24-48 horas (para dar tiempo a la revisión manual sin alertas constantes).
    -   **Escenario / ejemplo de comerciante:** Si un cliente intenta múltiples pedidos fraudulentos en una hora, esto evita que reciba una alerta por cada intento, consolidándolo en una alerta inicial.
-   **CDKEYS\_EXPORT\_MASK\_CODES:**

    -   **Qué hace esta configuración:** Al exportar datos de claves de CD, esta configuración determina si los códigos de clave reales deben enmascararse (ocultarse) por razones de seguridad.
    -   **Efecto de cambiar esta configuración:**
        -   *Cuando está activado:* Los datos exportados mostrarán códigos enmascarados (por ejemplo, `*****`).
        -   *Cuando está desactivado:* Los datos exportados mostrarán los códigos de clave completos y sin enmascarar.
    -   **Valor recomendado:** SÍ (por seguridad, especialmente si se comparten archivos de exportación).
    -   **Escenario / ejemplo de comerciante:** Si necesita compartir una lista de claves usadas con un proveedor pero no desea exponer los valores de clave reales, habilite el enmascaramiento.

### 2.2 Pantallas de administración dedicadas y vistas de controlador

El módulo agrega varias secciones nuevas a su menú del Back Office de PrestaShop, generalmente bajo una pestaña principal de "Claves de CD" o "Licencias".

#### 2.2.1 Claves de CD > Grupos (AdminCdKeysGroupsController)

-   **Nombre de la pantalla y ubicación del menú:** **Back Office > Claves de CD > Grupos**
-   **Propósito:** Esta pantalla le permite crear y administrar grupos de claves de CD. Un grupo es esencialmente un conjunto de claves que se pueden asignar a uno o más productos. Esto es crucial para gestionar su inventario de claves.
-   **Acciones y configuraciones disponibles:**
    -   **Añadir nuevo grupo:** Cree un nuevo grupo con un nombre (por ejemplo, "Claves de Windows 11 Pro", "Edición Deluxe del Juego X").
    -   **Editar grupo:** Modifique el nombre de un grupo existente.
    -   **Eliminar grupo:** Elimine un grupo (asegúrese de que no haya productos activos vinculados a él y que no haya claves asignadas).
    -   **Ver claves en el grupo:** Navegue directamente a la lista de claves asociadas con un grupo específico.
-   **Efecto de los cambios:**
    -   La creación de un grupo le permite categorizar sus claves y vincularlas a productos.
    -   La eliminación de un grupo eliminará su asociación con productos y claves, lo que podría causar problemas si aún se necesitan claves.
-   **Flujo de trabajo recomendado para la gestión diaria de la tienda:**
    1.  Antes de importar cualquier clave, cree un grupo para cada producto o versión distinta de un producto que requiera una clave.
    2.  Asigne el grupo apropiado a sus productos (esto se hace en la página de edición del producto, en la pestaña "Módulos" o en una pestaña dedicada "Claves de CD" agregada por el módulo).

#### 2.2.2 Claves de CD > Lista (AdminCdKeysListController)

-   **Nombre de la pantalla y ubicación del menú:** **Back Office > Claves de CD > Lista**
-   **Propósito:** Este es su inventario central para todas las claves de CD individuales. Aquí puede importar, ver y administrar el estado de cada clave.
-   **Acciones y configuraciones disponibles:**
    -   **Importar CSV:** Suba un archivo CSV que contenga sus claves. Especificará el grupo al que pertenecen estas claves durante el proceso de importación.
    -   **Añadir nueva clave:** Agregue manualmente una sola clave, asígnela a un grupo y establezca su estado (por ejemplo, "Disponible", "Usada").
    -   **Editar clave:** Modifique el valor, el grupo o el estado de una clave existente.
    -   **Eliminar clave:** Elimine una clave del inventario.
    -   **Filtrar/Buscar:** Encuentre claves específicas por valor, grupo o estado.
    -   **Exportar:** Exporte su inventario de claves (con enmascaramiento opcional).
-   **Efecto de los cambios:**
    -   La importación de claves llena su inventario, haciéndolas disponibles para la venta.
    -   Cambiar el estado de una clave (por ejemplo, a "Usada") evita que se asigne a nuevos pedidos.
    -   La eliminación de una clave la elimina permanentemente.
-   **Flujo de trabajo recomendado para la gestión diaria de la tienda:**
    1.  Importe regularmente nuevos lotes de claves de sus proveedores a sus respectivos grupos.
    2.  Supervise el estado "Usada" para asegurarse de que las claves se asignan correctamente.
    3.  Si un cliente informa un problema con una clave, puede encontrarla aquí, verificar su estado y, potencialmente, asignar una nueva.

#### 2.2.3 Claves de CD > Archivo (AdminCdKeysArchiveController)

-   **Nombre de la pantalla y ubicación del menú:** **Back Office > Claves de CD > Archivo**
-   **Propósito:** Esta pantalla proporciona un registro histórico de todas las claves de CD que se han asignado a pedidos de clientes. Actúa como un registro de auditoría para la distribución de claves.
-   **Acciones y configuraciones disponibles:**
    -   **Ver claves asignadas:** Vea qué clave se asignó a qué pedido, para qué producto y a qué cliente.
    -   **Filtrar/Buscar:** Encuentre claves archivadas específicas por ID de pedido, nombre de cliente, producto o valor de clave.
    -   **Reenviar correo electrónico:** Opción para reenviar el correo electrónico de la clave de CD al cliente (útil si afirma no haberlo recibido).
-   **Efecto de los cambios:** Esta pantalla es principalmente para visualización y auditoría. Las acciones aquí no cambian el estado de las claves en la sección "Lista", pero permiten acciones de soporte al cliente como reenviar correos electrónicos.
-   **Flujo de trabajo recomendado para la gestión diaria de la tienda:**
    1.  Utilice esta pantalla para buscar rápidamente las claves compradas por un cliente si se pone en contacto con el soporte.
    2.  Verifique que las claves se enviaron correctamente para pedidos específicos.
    3.  Reenvíe las claves si el correo electrónico de un cliente se perdió o se eliminó accidentalmente.

#### 2.2.4 Página de edición de producto (Back Office > Catálogo > Productos > Editar producto)

-   **Nombre de la pantalla y ubicación del menú:** Al editar un producto, busque una nueva pestaña o sección relacionada con "Claves de CD" o "Módulos".
-   **Propósito:** Aquí es donde vincula un producto específico a un grupo de claves de CD, marcándolo como un "producto de clave de CD".
-   **Acciones y configuraciones disponibles:**
    -   **Habilitar clave de CD para este producto:** Un interruptor o casilla de verificación para indicar que este producto requiere la entrega de una clave de CD.
    -   **Seleccionar grupo de claves de CD:** Un menú desplegable para elegir de qué grupo de claves debe extraer este producto cuando se realiza un pedido.
-   **Efecto de los cambios:**
    -   *Cuando está habilitado y se selecciona un grupo:* Cualquier compra de este producto activará automáticamente el módulo para asignar una clave disponible del grupo elegido y enviarla al cliente.
    -   *Cuando está deshabilitado:* El producto se tratará como un producto PrestaShop normal, y no se asignarán ni enviarán claves.
-   **Flujo de trabajo recomendado para la gestión diaria de la tienda:**
    1.  Para cada producto digital que venda que requiera una clave única, navegue a su página de edición.
    2.  Habilite la opción de clave de CD y seleccione el grupo de claves correcto que creó anteriormente.
    3.  Asegúrese de tener suficientes claves en el grupo seleccionado para cubrir las ventas potenciales.

### 2.3 Tabla de referencia rápida de configuración

| Pantalla / Vista | Configuración / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| **Configuración del módulo** | Activado | SÍ | Interruptor maestro para la funcionalidad del módulo. |
| | Seleccionar estados de pedido | Pago aceptado | Activa la entrega de claves cuando el pedido alcanza este estado. |
| | Grupos de clientes permitidos para recibir cdkey | Cliente, Invitado | Restringe la entrega de claves a grupos de clientes específicos. |
| | Valor máximo del pedido | Vacío (sin límite) | Establece un límite de valor para la entrega automática de claves (prevención de fraude). |
| | Enviar muchos códigos en un solo correo | SÍ | Agrupa varias claves para el mismo producto en un solo correo electrónico. |
| | Título del correo electrónico | Sus claves de CD de [Nombre de la tienda] | Personaliza la línea de asunto de los correos electrónicos de entrega de claves. |
| | Cambiar estado del pedido | SÍ | Actualiza automáticamente el estado del pedido después de la entrega de la clave. |
| | Seleccionar estado del pedido (para cambio de estado) | "Claves de CD enviadas" (personalizado) | El estado específico que se aplicará después de enviar las claves. |
| | Incluir claves en la factura | SÍ | Imprime las claves entregadas en la factura PDF del cliente. |
| | Activar paginación | SÍ | Habilita la paginación para "Mis claves" en la cuenta del cliente. |
| | Número de elementos de paginación | 10-20 | Número de claves mostradas por página en "Mis claves". |
| | Delimitador de fila del archivo CSV | `\n` | Carácter que separa las filas en la importación de claves CSV. |
| | Delimitador de columna del archivo CSV | `;` o `,` | Carácter que separa las columnas en la importación de claves CSV. |
| | CDKEYS\_EXPORT\_MASK\_CODES | SÍ | Enmascara los códigos de clave en los archivos de exportación por seguridad. |
| **Claves de CD > Grupos** | Añadir/Editar nombre de grupo | N/A | Gestiona categorías/grupos de claves. |
| **Claves de CD > Lista** | Importar CSV | N/A | Carga masivamente claves en grupos. |
| | Añadir/Editar clave | N/A | Gestiona manualmente los valores y el estado de las claves individuales. |
| **Claves de CD > Archivo** | Reenviar correo electrónico | N/A | Reenvía el correo electrónico de entrega de claves para un pedido específico. |
| **Página de edición de producto** | Habilitar clave de CD para este producto | SÍ | Marca un producto como que requiere entrega de clave de CD. |
| | Seleccionar grupo de claves de CD | (Grupo específico) | Vincula el producto a un grupo de claves para su cumplimiento. |

## 3. Solución de problemas del comerciante y preguntas frecuentes (FAQ)

**P1: Mis clientes no reciben sus claves de CD. ¿Qué debo verificar primero?**
R1:

1.  **¿Módulo activado?** Vaya a `Módulos > Gestor de módulos > Vender CDKeys / Claves de licencia` y asegúrese de que el módulo esté "Activado".
2.  **Estado del pedido:** Verifique la configuración de su módulo en "Seleccionar estados de pedido". ¿Está seleccionado el estado actual del pedido del cliente (por ejemplo, "Pago aceptado") en esta lista?
3.  **Producto vinculado al grupo:** En la página de edición del producto (`Catálogo > Productos > Editar producto`), asegúrese de que la casilla "Habilitar clave de CD para este producto" esté marcada y que el "Grupo de claves de CD" correcto esté seleccionado.
4.  **Claves en el grupo:** Vaya a `Claves de CD > Lista` y verifique si hay claves disponibles (sin usar) en el grupo asignado al producto. Si no, importe más claves.
5.  **Grupo de clientes:** Verifique que el grupo de clientes tenga permiso para recibir claves en "Grupos de clientes permitidos para recibir cdkey" en la configuración del módulo.
6.  **Configuración de correo electrónico:** Verifique la configuración de correo electrónico de su PrestaShop (`Parámetros avanzados > E-mail`) para asegurarse de que los correos electrónicos se envían correctamente desde su tienda. Además, pida al cliente que revise su carpeta de spam/correo no deseado.

**P2: Importé un archivo CSV, pero las claves no aparecen o son incorrectas.**
R2:

1.  **Configuración de delimitadores:** Vuelva a verificar la configuración de "Delimitador de fila del archivo CSV" y "Delimitador de columna del archivo CSV" en la configuración del módulo. Estos deben coincidir exactamente con la estructura de su archivo CSV. Los problemas comunes son usar coma (`,`) en lugar de punto y coma (`;`) o viceversa.
2.  **Formato de archivo:** Asegúrese de que su archivo CSV sea texto sin formato, no un archivo de Excel guardado como CSV con formato complejo.
3.  **Grupo de destino:** ¿Seleccionó el Grupo de claves de CD correcto durante el proceso de importación?

**P3: La sección "Mis claves" no aparece en la cuenta del cliente.**
R3:

1.  **Módulo activado:** Asegúrese de que el módulo esté activo.
2.  **Compatibilidad del tema:** Si bien el módulo utiliza ganchos estándar de PrestaShop, algunos temas muy personalizados podrían anular el gancho `displayCustomerAccount` predeterminado. Verifique si su tema ha modificado esta área. Si es así, es posible que necesite pequeños ajustes en el tema (consulte la Sección 7.6 para las plantillas de ganchos).
3.  **Caché:** Borre la caché de su PrestaShop (`Parámetros avanzados > Rendimiento > Borrar caché`).

**P4: ¿Cómo creo un nuevo estado de pedido como "Claves de CD enviadas"?**
R4:

1.  Vaya a `Parámetros de la tienda > Configuración de pedidos > Estados`.
2.  Haga clic en "Añadir nuevo estado de pedido".
3.  Asígnele un nombre claro (por ejemplo, "Claves de CD enviadas").
4.  Elija un color distinto (por ejemplo, azul claro) para identificarlo fácilmente en su lista de pedidos.
5.  Asegúrese de que la casilla "Considerar el pedido asociado como validado" esté marcada si desea que cuente como un pedido completado.
6.  Guarde el nuevo estado, luego regrese a la configuración del módulo para seleccionarlo para "Seleccionar estado del pedido (para cambio de estado)".

**P5: ¿Puedo asignar manualmente una clave a un pedido o cliente?**
R5: El módulo automatiza esto principalmente. Si necesita asignar manualmente una clave (por ejemplo, para un reemplazo), normalmente haría lo siguiente:

1.  Vaya a `Claves de CD > Lista`, encuentre una clave disponible y anote su valor.
2.  Vaya al pedido del cliente (`Pedidos > Pedidos`) y agregue una nota privada con la clave.
3.  Envíe manualmente la clave por correo electrónico al cliente.
4.  Luego, regrese a `Claves de CD > Lista`, encuentre esa clave y cambie manualmente su estado a "Usada" para evitar que se asigne nuevamente.

## 4. Guía para desarrolladores y webmasters (Arquitectura técnica y mapa de código)

Esta sección proporciona una inmersión profunda en la estructura técnica del módulo "Vender CDKeys / Claves de licencia", destinada a desarrolladores, webmasters y agencias técnicas.

### 4.1 Descripción general de la arquitectura

El módulo sigue un patrón MVC (Modelo-Vista-Controlador) estándar de PrestaShop. Extiende `Module` para su funcionalidad principal y `AdminController` para sus interfaces de Back Office. Aprovecha `ObjectModel` de PrestaShop para gestionar grupos de claves de CD, claves individuales y su historial de uso. La entrega de claves se basa principalmente en eventos, activada por los ganchos `actionOrderStatusPostUpdate` y `actionOrderStatusUpdate`. La interacción del front-office es mínima, principalmente proporcionando una sección "Mis claves" orientada al cliente.

### 4.2 Controladores (`controllers/`)

#### Controladores de Front-Office

-   `controllers/front/index.php`:
    -   **Nombre de la clase:** `CdkeysIndexModuleFrontController` (extiende `ModuleFrontController`)
    -   **Responsabilidad:** Probablemente un marcador de posición o un controlador de redirección. En muchos módulos, `index.php` en el directorio del controlador frontal podría manejar el enrutamiento predeterminado o simplemente redirigir a un controlador más específico.
-   `controllers/front/mykeys.php`:
    -   **Nombre de la clase:** `CdkeysMykeysModuleFrontController` (extiende `ModuleFrontController`)
    -   **Responsabilidad:** Maneja la visualización de las claves de CD compradas por el cliente en su sección "Mi cuenta". Recupera los registros `cdkey_used` asociados con el cliente actual, aplica la paginación si está habilitada y renderiza `views/templates/front/mykeys.tpl`.

#### Controladores de administración de Back-Office

-   `controllers/admin/AdminCdKeysArchiveController.php`:
    -   **Nombre de la pestaña:** Claves de CD > Archivo
    -   **Entidad gestionada:** `cdkey_used` (registros de claves asignadas)
    -   **Responsabilidad:** Proporciona una interfaz de gestión de listas para todas las claves de CD que se han asignado a pedidos. Permite ver, filtrar y, potencialmente, reenviar correos electrónicos de claves. Utiliza `HelperList` para su visualización.
-   `controllers/admin/AdminCdKeysGroupsController.php`:
    -   **Nombre de la pestaña:** Claves de CD > Grupos
    -   **Entidad gestionada:** `cdkey_group`
    -   **Responsabilidad:** Gestiona la creación, edición y eliminación de grupos de claves de CD. Estos grupos actúan como categorías para sus claves y están vinculados a productos. Utiliza `HelperList` y `HelperForm` para sus interfaces.
-   `controllers/admin/AdminCdKeysListController.php`:
    -   **Nombre de la pestaña:** Claves de CD > Lista
    -   **Entidad gestionada:** `cdkey`
    -   **Responsabilidad:** Gestiona el inventario de claves de CD individuales. Esto incluye la importación de archivos CSV, la adición/edición/eliminación de claves y la visualización de su estado (disponible, usada). Utiliza `HelperList` y `HelperForm`.
-   `controllers/admin/index.php`:
    -   **Nombre de la pestaña:** Claves de CD (Panel principal)
    -   **Entidad gestionada:** N/A (Panel)
    -   **Responsabilidad:** Probablemente sirve como el panel principal del módulo, mostrando análisis, estadísticas clave y, potencialmente, alertas de fraude. Agrega datos de las tablas `cdkey_used` y `cdkey`.

### 4.3 Clases y modelos principales (`classes/`)

El dossier del módulo no indica un directorio `classes/` explícito. Esto sugiere que las definiciones principales de `ObjectModel` y la lógica de negocio central probablemente están encapsuladas dentro del propio archivo `cdkeys.php`, o dentro de los respectivos archivos de controlador.

Si las definiciones de `ObjectModel` están presentes en `cdkeys.php`, normalmente se verían así:

-   `CdKeyGroup` (para la tabla `ps_cdkey_group`): Gestiona grupos de claves.
    -   `$definition` incluiría `id_cdkey_group`, `name`.
-   `CdKey` (para la tabla `ps_cdkey`): Gestiona claves individuales.
    -   `$definition` incluiría `id_cdkey`, `id_cdkey_group`, `key_value`, `status` (por ejemplo, 'available', 'used').
-   `CdKeyUsed` (para la tabla `ps_cdkey_used`): Gestiona claves asignadas.
    -   `$definition` incluiría `id_cdkey_used`, `id_cdkey`, `id_order`, `id_customer`, `id_product`, `date_add`.

### 4.4 Activos JavaScript (`views/js/`)

-   `cdkeys/lib/emailTemplatesManager/js/emailTemplatesManager.js`:
    -   **Alcance:** Back-office.
    -   **Responsabilidad:** Gestiona la interfaz de usuario para crear, editar y seleccionar plantillas de correo electrónico dentro de la configuración del módulo. Probablemente maneja llamadas AJAX para guardar el contenido de la plantilla, previsualizar correos electrónicos y cambiar entre diferentes versiones de plantilla.
-   `cdkeys/lib/searchTool/views/js/autocomplete.js`:
    -   **Alcance:** Back-office.
    -   **Responsabilidad:** Proporciona funcionalidad de autocompletado para campos de búsqueda dentro de las interfaces de administración del módulo (por ejemplo, buscar productos, clientes o grupos de claves). Se vincula a los campos de entrada y realiza solicitudes AJAX para obtener sugerencias.
-   `cdkeys/views/js/adminCdKeysDashboard.js`:
    -   **Alcance:** Back-office (AdminCdKeysDashboardController o panel principal del módulo).
    -   **Responsabilidad:** Impulsa los elementos interactivos del panel principal del módulo. Esto podría incluir la representación de gráficos (por ejemplo, usando Chart.js o una biblioteca similar), el filtrado de datos y las actualizaciones dinámicas de estadísticas.
-   `cdkeys/views/js/cdkeys-dashboard-demo-console.js`:
    -   **Alcance:** Back-office.
    -   **Responsabilidad:** Probablemente un script de desarrollo/depuración o una consola de demostración para el panel, posiblemente registrando eventos o proporcionando datos de prueba. No debe estar activo en producción.
-   `cdkeys/views/js/cdkeys-fraud-demo-console.js`:
    -   **Alcance:** Back-office.
    -   **Responsabilidad:** Similar a la consola de demostración del panel, este es probablemente un script de desarrollo/depuración para las funciones de detección de fraude. No debe estar activo en producción.
-   `cdkeys/views/js/cdkeys-pagination.js`:
    -   **Alcance:** Front-office (`mykeys.tpl`).
    -   **Responsabilidad:** Maneja la lógica del lado del cliente para la paginación en la sección "Mis claves" del cliente. Esto podría implicar llamadas AJAX para cargar nuevas páginas de claves sin una recarga completa de la página, o simplemente gestionar la visualización de números de página y la navegación.

### 4.5 Hojas de estilo CSS (`views/css/`)

-   `cdkeys/lib/emailTemplatesManager/css/emailTemplatesManager.css`:
    -   **Alcance:** Back-office.
    -   **Componentes principales de la interfaz de usuario:** Estiliza la interfaz de gestión de plantillas de correo electrónico, incluidos formularios, botones y áreas de vista previa.
    -   **Selectores de clase CSS clave:** `.email-template-manager`, `.template-form`, `.template-preview`.
-   `cdkeys/lib/searchTool/views/css/autocomplete.css`:
    -   **Alcance:** Back-office.
    -   **Componentes principales de la interfaz de usuario:** Estiliza los menús desplegables de autocompletado y los campos de entrada.
    -   **Selectores de clase CSS clave:** `.autocomplete-suggestions`, `.autocomplete-selected`, `.autocomplete-suggestion`.
-   `cdkeys/views/css/admin_cdkeys.css`:
    -   **Alcance:** Back-office.
    -   **Componentes principales de la interfaz de usuario:** Estilo general para las páginas de administración del módulo, incluidas listas, formularios y elementos del panel.
    -   **Selectores de clase CSS clave:** `.cdkeys-admin-panel`, `.cdkeys-table`, `.cdkeys-form-group`.
-   `cdkeys/views/css/cdkeys-admin.css`:
    -   **Alcance:** Back-office.
    -   **Componentes principales de la interfaz de usuario:** Estilo adicional o específico para interfaces de administración, que potencialmente anula o extiende `admin_cdkeys.css`.
    -   **Selectores de clase CSS clave:** `.cdkeys-dashboard-widget`, `.cdkeys-alert`.
-   `cdkeys/views/css/css.css`:
    -   **Alcance:** Potencialmente tanto Front-office como Back-office, o estilos de utilidad generales.
    -   **Componentes principales de la interfaz de usuario:** Podría contener estilos básicos para elementos utilizados en diferentes partes del módulo.
    -   **Selectores de clase CSS clave:** Clases genéricas que podrían aplicarse a varios elementos del módulo.

### 4.6 Estructura de plantillas Smarty (`views/templates/`)

#### Plantillas de gancho (`views/templates/hook/`)

-   `cdkeys/views/templates/hook/adminOrder.tpl`:
    -   **Gancho:** `displayAdminOrder`
    -   **Salida:** Muestra información de la clave de CD directamente dentro de la página de detalles del pedido del Back Office de PrestaShop. Esto permite a los administradores ver rápidamente qué claves se asignaron a un pedido.
-   `cdkeys/views/templates/hook/adminOrderFraud.tpl`:
    -   **Gancho:** `displayAdminOrderTop` (o similar, potencialmente `displayAdminOrder`)
    -   **Salida:** Muestra información o alertas relacionadas con el fraude para un pedido en la página de detalles del pedido del Back Office.
-   `cdkeys/views/templates/hook/my-account-16.tpl`:
    -   **Gancho:** `displayCustomerAccount` (para PrestaShop 1.6.x)
    -   **Salida:** Agrega un enlace o bloque a la página "Mi cuenta" del cliente, dirigiéndolos a su sección "Mis claves".
-   `cdkeys/views/templates/hook/my-account-17.tpl`:
    -   **Gancho:** `displayCustomerAccount` (para PrestaShop 1.7.x, 8.x, 9.x)
    -   **Salida:** Similar a `my-account-16.tpl`, pero adaptado para la diferente estructura de plantilla de las versiones más nuevas de PrestaShop, agregando un enlace a la sección "Mis claves".
-   `cdkeys/views/templates/hook/orderDetailDisplayed.tpl`:
    -   **Gancho:** `displayOrderDetailDisplayed`
    -   **Salida:** Muestra información de la clave de CD en la página de detalles del pedido del front-office del cliente.

#### Plantillas de administración (`views/templates/admin/`)

-   `cdkeys/lib/emailTemplatesManager/views/buttonManager.tpl`:
    -   **Propósito:** Renderiza botones o controles para el gestor de plantillas de correo electrónico.
-   `cdkeys/lib/emailTemplatesManager/views/createTemplateForm.tpl`:
    -   **Propósito:** Renderiza el formulario para crear nuevas plantillas de correo electrónico.
-   `cdkeys/lib/emailTemplatesManager/views/editTemplateForm.tpl`:
    -   **Propósito:** Renderiza el formulario para editar plantillas de correo electrónico existentes.
-   `cdkeys/lib/emailTemplatesManager/views/mainForm.tpl`:
    -   **Propósito:** El contenedor principal o formulario para la interfaz de gestión de plantillas de correo electrónico.
-   `cdkeys/lib/emailTemplatesManager/views/selectInput.tpl`:
    -   **Propósito:** Renderiza una entrada de selección desplegable, probablemente para elegir plantillas de correo electrónico o idiomas.
-   `cdkeys/lib/searchTool/views/scripts.tpl`:
    -   **Propósito:** Incluye scripts JavaScript para la herramienta de búsqueda/funcionalidad de autocompletado.
-   `cdkeys/views/templates/admin/cdkeys/helpers/list/list_action_email.tpl`:
    -   **Propósito:** Renderiza un botón de acción específico (por ejemplo, "Reenviar correo electrónico") dentro de una tabla `HelperList` en los controladores de administración (por ejemplo, `AdminCdKeysArchiveController`).
-   `cdkeys/views/templates/admin/customerGroups.tpl`:
    -   **Propósito:** Renderiza la interfaz de selección de grupos de clientes en la configuración del módulo.
-   `cdkeys/views/templates/admin/getCombinations.tpl`:
    -   **Propósito:** Potencialmente utilizado para mostrar o seleccionar combinaciones de productos relacionadas con claves de CD (por ejemplo, si diferentes combinaciones requieren diferentes grupos de claves).
-   `cdkeys/views/templates/admin/orderstates.tpl`:
    -   **Propósito:** Renderiza el menú desplegable de selección múltiple para "Seleccionar estados de pedido" en la configuración del módulo.
-   `cdkeys/views/templates/admin/orderstatesRadio.tpl`:
    -   **Propósito:** Renderiza la selección de botones de radio para "Seleccionar estado del pedido" (para cambio de estado) en la configuración del módulo.
-   `cdkeys/views/templates/admin/script.tpl`:
    -   **Propósito:** Inclusión general de scripts para páginas de administración, posiblemente para JS específico del módulo.

#### Plantillas de front-office (`views/templates/front/`)

-   `cdkeys/views/templates/front/mykeys.tpl`:
    -   **Propósito:** La plantilla principal para mostrar la lista de claves de CD compradas por el cliente en su sección "Mi cuenta". Iterará a través de los datos de `cdkey_used` y presentará las claves, los detalles del pedido y, potencialmente, los controles de paginación.

#### Plantillas de correo electrónico (`views/templates/email/`)

-   `cdkeys/views/templates/email/multikey-instance.tpl`:
    -   **Propósito:** Esta es la plantilla principal para el correo electrónico enviado a los clientes que contiene sus claves de CD. Se rellenará dinámicamente con el nombre del cliente, los detalles del pedido y la(s) clave(s) real(es).

### 4.7 Esquema de la base de datos y mapa de ganchos

#### Tablas de la base de datos

-   `ps_cdkey_group`: Almacena información sobre grupos de claves de CD.
    -   `id_cdkey_group` (PK)
    -   `name`
    -   `date_add`
    -   `date_upd`
-   `ps_cdkey`: Almacena claves de CD individuales.
    -   `id_cdkey` (PK)
    -   `id_cdkey_group` (FK a `ps_cdkey_group`)
    -   `key_value` (la cadena de clave de CD real)
    -   `status` (por ejemplo, 'available', 'used')
    -   `date_add`
    -   `date_upd`
-   `ps_cdkey_used`: Almacena registros de claves de CD asignadas a pedidos.
    -   `id_cdkey_used` (PK)
    -   `id_cdkey` (FK a `ps_cdkey`)
    -   `id_order` (FK a `ps_orders`)
    -   `id_customer` (FK a `ps_customer`)
    -   `id_product` (FK a `ps_product`)
    -   `date_add`

#### Registros de configuración (`ps_configuration`)

-   `CDKEYS_ENABLED`: (bool) Interruptor maestro.
-   `CDKEYS_OSTATES`: (string) Lista de estados de pedido separados por comas para la entrega de claves.
-   `CDKEYS_GROUPS`: (string) Lista de grupos de clientes separados por comas para la entrega de claves.
-   `CDKEYS_MAX_ORDERTOTAL`: (float) Valor máximo del pedido para la entrega automática.
-   `CDKEY_HOWDELIVER`: (bool) Enviar muchos códigos en un solo correo.
-   `CDKEYS_MULTITITLE`: (string) Título del asunto del correo electrónico.
-   `CDKEY_STATUSCHANGE`: (bool) Cambiar el estado del pedido después de la entrega.
-   `CDKEYS_OSTATES_RADIO`: (int) ID del estado del pedido al que cambiar.
-   `CDKEY_INC_INV`: (bool) Incluir claves en la factura.
-   `CDKEY_PAGINATION`: (bool) Habilitar paginación para Mis claves.
-   `CDKEY_PAGINATION_NB`: (int) Elementos por página para la paginación de Mis claves.
-   `IV_ROW_DELIMITER`: (string) Delimitador de fila CSV.
-   `IV_COL_DELIMITER`: (string) Delimitador de columna CSV.
-   `CDKEYS_ANALYTICS_*`: Varias configuraciones para el análisis del panel.
-   `CDKEYS_ALERT_COOLDOWN_HOURS`: (int) Período de enfriamiento para alertas de fraude.
-   `CDKEYS_EXPORT_MASK_CODES`: (bool) Enmascarar códigos en la exportación.

#### Tabla de ganchos registrados

| Nombre del gancho | Momento de ejecución | Propósito técnico |
| --- | --- | --- |
| `actionOrderStatusPostUpdate` | Después de que el estado de un pedido se haya actualizado (y guardado). | Activador principal para la entrega de claves de CD. Comprueba si el nuevo estado coincide con los estados configurados y envía las claves. |
| `displayAdminOrder` | Renderiza contenido dentro de la página de detalles del pedido del Back Office. | Muestra las claves de CD asignadas para el pedido actual en el panel de administración. |
| `ActionAdminControllerSetMedia` | Cuando se inicializa un controlador de administración y se están configurando los medios (JS/CSS). | Inyecta archivos JS y CSS específicos del módulo en el Back Office para los controladores de administración. |
| `displayCustomerAccount` | Renderiza contenido en la página "Mi cuenta" del cliente. | Agrega un enlace o bloque para "Mis claves" en la cuenta del front office del cliente. |
| `DisplayAdminOrderTop` | Renderiza contenido en la parte superior de la página de detalles del pedido del Back Office. | Potencialmente utilizado para mostrar alertas de fraude o información resumida relacionada con las claves de CD para el pedido. |
| `actionOrderStatusUpdate` | Antes de que se actualice el estado de un pedido (gancho más antiguo, se prefiere `actionOrderStatusPostUpdate`). | Activador secundario o de respaldo para la entrega de claves de CD, asegurando la compatibilidad con versiones anteriores de PrestaShop o escenarios específicos. |
| `DisplayBackOfficeHeader` | Renderiza contenido en el encabezado de todas las páginas del Back Office. | Inyecta JS/CSS global del Back Office o elementos de menú para el módulo. |
| `displayHeader` | Renderiza contenido en la sección `<head>` de las páginas del front-office. | Inyecta JS/CSS o metaetiquetas específicas del front-office. |
| `displayOrderDetailDisplayed` | Renderiza contenido dentro de la página de detalles del pedido del front-office del cliente. | Muestra las claves de CD asignadas directamente en la página de resumen del pedido del cliente. |
| `actionOrderHistoryAddAfter` | Después de que se haya agregado una entrada de historial de pedidos (cambio de estado). | Podría usarse como un activador alternativo para la entrega de claves o para fines de registro relacionados con los cambios de estado. |

## 5. Soporte oficial y actualizaciones

Para obtener las últimas actualizaciones del módulo, correcciones de errores y soporte oficial, inicie sesión en su cuenta de cliente en [MyPresta.eu](https://mypresta.eu/my-account/orders/). Allí encontrará acceso a sus módulos comprados y canales de soporte dedicados.
