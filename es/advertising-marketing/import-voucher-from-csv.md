---
title: "Importar vales desde CSV - Manual de Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop 'Importar vales desde CSV' de MyPresta.eu."
sidebar:
  label: "Importar vales desde CSV - Manual de Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Import voucher from CSV en MyPresta.eu](https://mypresta.eu/modules/advertising-and-marketing/import-voucher-from-csv.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/advertising-marketing/import-voucher-from-csv/)
>
> ---


# Importar vales desde CSV

## 1. Requisitos y compatibilidad

- **Versiones de PrestaShop compatibles**: PrestaShop 1.4.x, 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilidad con PHP**: PHP 5.6 - 8.5
- **Requisitos de alojamiento**: Las extensiones PHP estándar (cURL, JSON, OpenSSL) suelen ser suficientes y normalmente están habilitadas por defecto en la mayoría de los entornos de alojamiento.

## 2. Recorrido completo de la configuración (cada ajuste agrupado por pantalla)

### 2.1 Página de configuración del módulo (Back Office > Módulos > Configurar)

Después de la instalación, al hacer clic en "Configurar" accederá a la pantalla de configuración principal del módulo. Aquí es donde subirá su archivo CSV y definirá cómo deben importarse los códigos de vale y qué propiedades deben tener.

La página de configuración suele estar estructurada en varias secciones, guiándole a través del proceso de importación.

#### **Paso 1: Suba su archivo CSV**

-   **Qué hace este ajuste:** Aquí es donde selecciona el archivo CSV que contiene sus códigos de vale desde su ordenador.
-   **Efecto de cambiar este ajuste:** Al hacer clic en "Examinar" o "Elegir archivo" se abre un cuadro de diálogo de selección de archivos. Una vez que seleccione un archivo, su nombre aparecerá junto al botón, indicando que está listo para ser subido.
-   **Valor recomendado:** Seleccione el archivo CSV que ha preparado con sus códigos de vale.
-   **Escenario / ejemplo del comerciante:** Ha recibido una lista de 1000 códigos de vale únicos de un socio como Groupon. Ha guardado estos códigos en un archivo CSV (por ejemplo, `groupon_vouchers.csv`). Haría clic en "Elegir archivo" y seleccionaría este archivo.

#### **Paso 2: Configuración del archivo CSV**

Esta sección define cómo debe interpretar el módulo su archivo CSV.

-   **Separador CSV:**

    -   **Qué hace este ajuste:** Especifica el carácter utilizado para separar valores (columnas) dentro de su archivo CSV. Los separadores comunes son la coma (`,`), el punto y coma (`;`) o el tabulador (`\t`).
    -   **Efecto de cambiar este ajuste:** Si se elige el separador incorrecto, el módulo no analizará correctamente su archivo, y todos los datos podrían aparecer en una sola columna o dividirse incorrectamente.
    -   **Valor recomendado:** Coincida con el separador utilizado cuando creó o exportó su archivo CSV. La mayoría del software de hojas de cálculo utiliza la coma por defecto.
    -   **Escenario / ejemplo del comerciante:** Si su CSV se ve como `CODE123,10,USD`, elegiría "Coma". Si es `CODE123;10;USD`, elegiría "Punto y coma".
-   **Delimitador de texto:**

    -   **Qué hace este ajuste:** Especifica el carácter utilizado para encerrar valores de texto, especialmente aquellos que podrían contener el carácter separador. A menudo, este es una comilla doble (`"`).
    -   **Efecto de cambiar este ajuste:** Si sus campos de texto contienen el separador (por ejemplo, el nombre de un producto con una coma) y no están delimitados correctamente, el módulo podría interpretar erróneamente los datos, lo que llevaría a un análisis incorrecto.
    -   **Valor recomendado:** Coincida con el delimitador utilizado en su CSV. Normalmente "Comilla doble".
    -   **Escenario / ejemplo del comerciante:** Si la descripción de un vale es `"10% de descuento, oferta por tiempo limitado"` y su separador es una coma, las comillas dobles aseguran que "10% de descuento, oferta por tiempo limitado" se trate como un solo campo.
-   **Omitir primera línea (encabezado):**

    -   **Qué hace este ajuste:** Si su archivo CSV tiene una fila de encabezado (por ejemplo, `Código de vale,Cantidad de descuento,Fecha de caducidad`) que describe las columnas, al habilitar esto se le indicará al módulo que ignore esa primera línea durante la importación.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando está habilitado:* La fila de encabezado se omite y solo se importan las filas de datos reales.
        -   *Cuando está deshabilitado:* La primera línea de su CSV se tratará como un código de vale o datos, lo que suele ser incorrecto y puede provocar errores.
    -   **Valor recomendado:** "SÍ" si su CSV tiene una fila de encabezado, "NO" si solo contiene datos.
    -   **Escenario / ejemplo del comerciante:** Su CSV comienza con `código,valor,moneda`. Habilitaría esto para evitar que "código" se importe como un vale real.

#### **Paso 3: Configuración de vales (Propiedades generales)**

Esta sección define las propiedades comunes para todos los vales que está importando. Estos ajustes se aplican a *todos* los códigos de su archivo CSV.

-   **Nombre:**

    -   **Qué hace este ajuste:** Este es el nombre interno de la regla de vale en su Back Office. Le ayuda a identificar el grupo de vales.
    -   **Efecto de cambiar este ajuste:** Este nombre es visible solo para usted en el Back Office, no para los clientes.
    -   **Valor recomendado:** Un nombre descriptivo, por ejemplo, "Códigos Groupon - Mayo 2024".
    -   **Escenario / ejemplo del comerciante:** Está importando códigos de una campaña "Rebajas de Verano 2024". Lo nombraría "Vales Rebajas de Verano 2024".
-   **Descripción:**

    -   **Qué hace este ajuste:** Una descripción interna opcional para la regla de vale.
    -   **Efecto de cambiar este ajuste:** Proporciona más contexto para su equipo en el Back Office.
    -   **Valor recomendado:** Una breve explicación, por ejemplo, "Códigos únicos para un 10% de descuento, un solo uso, caduca el 31/05/2024".
    -   **Escenario / ejemplo del comerciante:** "Códigos proporcionados por LivingSocial para nuevos clientes."
-   **Resaltar:**

    -   **Qué hace este ajuste:** Determina si el vale se resalta en el resumen del carrito.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando está habilitado:* El vale se mostrará de forma más prominente en el resumen del carrito, lo que podría llamar más la atención sobre el descuento.
        -   *Cuando está deshabilitado:* El vale se listará normalmente.
    -   **Valor recomendado:** "NO" para uso general, "SÍ" si desea enfatizar el descuento.
    -   **Escenario / ejemplo del comerciante:** Para una oferta especial por tiempo limitado, podría habilitar "SÍ" para asegurarse de que los clientes noten el descuento aplicado.
-   **Uso parcial:**

    -   **Qué hace este ajuste:** Permite a los clientes usar solo una parte del valor del vale y conservar el resto para futuras compras.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando está habilitado:* Si un cliente tiene un vale de 50 € y compra un artículo de 30 €, conserva un saldo de 20 € en el vale.
        -   *Cuando está deshabilitado:* El valor total del vale debe usarse en una sola transacción; cualquier saldo restante se pierde.
    -   **Valor recomendado:** "NO" para la mayoría de los códigos de descuento. "SÍ" para tarjetas de regalo o crédito de tienda.
    -   **Escenario / ejemplo del comerciante:** Si está importando códigos de tarjetas de regalo, habilitaría "SÍ". Para un cupón estándar de "10% de descuento", usaría "NO".
-   **Prioridad:**

    -   **Qué hace este ajuste:** Determina el orden en que se aplican varios vales si un cliente usa más de uno. Los vales de mayor prioridad se aplican primero.
    -   **Efecto de cambiar este ajuste:** Puede influir en el importe final del descuento si varios vales interactúan (por ejemplo, descuentos porcentuales frente a descuentos de importe fijo).
    -   **Valor recomendado:** "1" para la prioridad más alta, o dejar por defecto si no tiene interacciones complejas de vales.
    -   **Escenario / ejemplo del comerciante:** Si tiene un vale de "Envío gratuito" y un vale de "10% de descuento", podría dar al "Envío gratuito" una prioridad más alta para asegurarse de que se aplique primero, y luego el descuento porcentual.
-   **Estado:**

    -   **Qué hace este ajuste:** Activa o desactiva la regla de vale.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando está habilitado:* Los vales importados bajo esta regla pueden ser utilizados por los clientes.
        -   *Cuando está deshabilitado:* Los vales no pueden ser utilizados, incluso si son válidos.
    -   **Valor recomendado:** "SÍ" para que los vales sean utilizables inmediatamente. Puede deshabilitarlo más tarde si es necesario.
    -   **Escenario / ejemplo del comerciante:** Desea preparar vales con antelación pero solo activarlos el día del lanzamiento de una campaña. Establecería "NO" inicialmente y luego cambiaría a "SÍ" cuando esté listo.

#### **Paso 4: Configuración de vales (Condiciones)**

Esta sección define las condiciones bajo las cuales se pueden usar los vales importados.

-   **Cantidad mínima:**

    -   **Qué hace este ajuste:** Especifica el total mínimo del pedido (antes del envío e impuestos) requerido para que el vale sea válido.
    -   **Efecto de cambiar este ajuste:** Los clientes deben cumplir con este valor mínimo de compra para aplicar el descuento.
    -   **Valor recomendado:** "0" si no se requiere un mínimo, o una cantidad específica (por ejemplo, "50.00").
    -   **Escenario / ejemplo del comerciante:** "Obtenga 10 € de descuento en pedidos superiores a 100 €." Establecería "100.00".
-   **Moneda:**

    -   **Qué hace este ajuste:** Selecciona la moneda para la cantidad mínima.
    -   **Efecto de cambiar este ajuste:** Asegura que la cantidad mínima se interprete correctamente para tiendas multimoneda.
    -   **Valor recomendado:** La moneda predeterminada de su tienda (por ejemplo, "USD", "EUR").
    -   **Escenario / ejemplo del comerciante:** Si su tienda opera en varias monedas, asegúrese de que esto coincida con la moneda que espera que los clientes usen para este vale.
-   **Acumulable con otros vales:**

    -   **Qué hace este ajuste:** Determina si este vale se puede combinar con otros vales activos en el mismo pedido.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando está habilitado:* Los clientes pueden usar este vale junto con otros vales válidos.
        -   *Cuando está deshabilitado:* Este vale no se puede usar si ya se ha aplicado otro vale al carrito.
    -   **Valor recomendado:** "NO" para la mayoría de los códigos únicos para evitar descuentos excesivos. "SÍ" para promociones específicas como "envío gratuito" que desea combinar.
    -   **Escenario / ejemplo del comerciante:** Está importando códigos de "10% de descuento". Probablemente querrá "NO" para evitar que los clientes acumulen múltiples descuentos porcentuales.
-   **Fecha de caducidad (Desde):**

    -   **Qué hace este ajuste:** Establece la fecha de inicio a partir de la cual los vales importados se vuelven válidos.
    -   **Efecto de cambiar este ajuste:** Los vales no se pueden usar antes de esta fecha.
    -   **Valor recomendado:** La fecha de hoy o una fecha futura para promociones programadas.
    -   **Escenario / ejemplo del comerciante:** Desea que los vales estén activos a partir del próximo lunes. Seleccionaría la fecha del próximo lunes.
-   **Fecha de caducidad (Hasta):**

    -   **Qué hace este ajuste:** Establece la fecha de finalización después de la cual los vales importados ya no son válidos.
    -   **Efecto de cambiar este ajuste:** Los vales no se pueden usar después de esta fecha.
    -   **Valor recomendado:** Una fecha futura correspondiente al final de su promoción.
    -   **Escenario / ejemplo del comerciante:** Su campaña termina el 31 de diciembre. Seleccionaría el 31 de diciembre.
-   **Cantidad:**

    -   **Qué hace este ajuste:** Define el número total de veces que *cada código de vale individual* puede ser utilizado.
    -   **Efecto de cambiar este ajuste:**
        -   *Establecido en 1:* Cada código de su CSV se puede usar solo una vez (lo más común para códigos únicos).
        -   *Establecido en >1:* Cada código se puede usar varias veces hasta este límite.
    -   **Valor recomendado:** "1" para códigos únicos de un solo uso (por ejemplo, de Groupon).
    -   **Escenario / ejemplo del comerciante:** Para 1000 códigos únicos de Groupon, establecería esto en "1" para que cada cliente solo pueda usar su código específico una vez.
-   **Cantidad por usuario:**

    -   **Qué hace este ajuste:** Define cuántas veces *un solo cliente* puede usar *cualquier* vale de este lote importado.
    -   **Efecto de cambiar este ajuste:**
        -   *Establecido en 1:* Un cliente solo puede usar un vale de este lote, incluso si tiene varios códigos únicos.
        -   *Establecido en >1:* Un cliente puede usar varios vales de este lote, hasta este límite.
    -   **Valor recomendado:** "1" para la mayoría de las campañas de códigos únicos para evitar que un solo cliente use muchos códigos.
    -   **Escenario / ejemplo del comerciante:** Desea que cada cliente se beneficie de un solo vale de "bienvenida". Establecería esto en "1".

#### **Paso 5: Configuración de vales (Acciones)**

Esta sección define qué tipo de descuento proporcionarán los vales importados.

-   **Envío gratuito:**

    -   **Qué hace este ajuste:** Si está habilitado, el vale otorgará envío gratuito para el pedido.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando está habilitado:* Los gastos de envío se eximen cuando se aplica el vale.
        -   *Cuando está deshabilitado:* Los gastos de envío se calculan normalmente.
    -   **Valor recomendado:** "NO" a menos que el propósito principal de estos vales sea el envío gratuito.
    -   **Escenario / ejemplo del comerciante:** Está importando códigos para una promoción de "Fin de semana de envío gratuito". Habilitaría "SÍ".
-   **Aplicar un descuento:**

    -   **Qué hace este ajuste:** Determina el tipo y el valor del descuento aplicado por el vale.
    -   **Efecto de cambiar este ajuste:** Este es el mecanismo de descuento principal.
    -   **Valor recomendado:** Elija una de las opciones siguientes según su promoción.
    -   **Escenario / ejemplo del comerciante:** Quiere dar un 10% de descuento.
    -   **Porcentaje:**

        -   **Qué hace este ajuste:** Aplica un descuento porcentual al pedido.
        -   **Efecto de cambiar este ajuste:** El campo `Valor` se interpretará como un porcentaje (por ejemplo, `10` para el 10%).
        -   **Valor recomendado:** Seleccione esto para descuentos basados en porcentaje.
        -   **Escenario / ejemplo del comerciante:** Para una promoción de "15% de descuento", seleccione "Porcentaje" e introduzca `15` en el campo `Valor`.
    -   **Cantidad:**

        -   **Qué hace este ajuste:** Aplica un descuento monetario fijo al pedido.
        -   **Efecto de cambiar este ajuste:** El campo `Valor` se interpretará como una cantidad fija en la moneda elegida (por ejemplo, `10.00` para 10 € de descuento).
        -   **Valor recomendado:** Seleccione esto para descuentos de cantidad fija.
        -   **Escenario / ejemplo del comerciante:** Para una promoción de "20 € de descuento", seleccione "Cantidad" e introduzca `20.00` en el campo `Valor`.
    -   **Ninguno:**

        -   **Qué hace este ajuste:** Si se selecciona, el vale no aplicará ningún descuento monetario o porcentual. Esto se usa típicamente cuando la única acción del vale es "Envío gratuito" o "Enviar un regalo".
        -   **Efecto de cambiar este ajuste:** No se aplica ningún valor de descuento.
        -   **Valor recomendado:** Solo seleccione "Ninguno" si está utilizando "Envío gratuito" o "Enviar un regalo" como acción principal.
        -   **Escenario / ejemplo del comerciante:** Si solo desea ofrecer envío gratuito, seleccionaría "Ninguno" aquí y habilitaría "Envío gratuito" arriba.
-   **Valor:**

    -   **Qué hace este ajuste:** El valor numérico real del descuento. Su interpretación depende de si se selecciona "Porcentaje" o "Cantidad" arriba.
    -   **Efecto de cambiar este ajuste:** Controla directamente el tamaño del descuento.
    -   **Valor recomendado:** Un valor numérico (por ejemplo, `10` para 10% o 10 €).
    -   **Escenario / ejemplo del comerciante:** Si eligió "Porcentaje" y quiere un 15% de descuento, introduzca `15`. Si eligió "Cantidad" y quiere 20 € de descuento, introduzca `20.00`.
-   **Aplicar descuento a:**

    -   **Qué hace este ajuste:** Determina a qué se aplica el descuento.
    -   **Efecto de cambiar este ajuste:**
        -   *Pedido (sin envío):* El descuento se aplica al valor total del producto en el carrito.
        -   *Producto específico:* El descuento se aplica solo a un producto particular que especifique.
        -   *Producto más barato:* El descuento se aplica al producto de menor precio en el carrito.
        -   *Productos seleccionados:* El descuento se aplica a una selección de productos.
    -   **Valor recomendado:** "Pedido (sin envío)" para descuentos generales.
    -   **Escenario / ejemplo del comerciante:** Para una campaña general de "10% de descuento en todo", elija "Pedido (sin envío)". Si es "10% de descuento en todas las camisetas", seleccionaría "Productos seleccionados" y luego elegiría su categoría/productos de camisetas.
-   **Enviar un regalo:**

    -   **Qué hace este ajuste:** Si está habilitado, el vale añadirá un producto específico al carrito del cliente como regalo gratuito.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando está habilitado:* Se le pedirá que seleccione un producto para añadir como regalo.
        -   *Cuando está deshabilitado:* No se añade ningún regalo.
    -   **Valor recomendado:** "NO" a menos que esté ejecutando una promoción del tipo "compre X y obtenga Y gratis".
    -   **Escenario / ejemplo del comerciante:** "Compre cualquier producto, obtenga un llavero gratis." Habilitaría "SÍ" y seleccionaría el producto llavero.

Después de configurar todos los ajustes, normalmente encontrará un botón "Guardar" o "Importar". Haga clic en él para iniciar el proceso de importación. El módulo leerá su archivo CSV y creará las reglas de vale correspondientes en su base de datos de PrestaShop basándose en los ajustes que haya definido.

### 2.2 Tabla de referencia rápida de configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| **Configuración del módulo** | Subir archivo CSV | Su CSV preparado | Selecciona el archivo que contiene los códigos de vale. |
| | Separador CSV | Coma (`,`) | Carácter que separa las columnas en su CSV. Debe coincidir con su archivo. |
| | Delimitador de texto | Comilla doble (`"`) | Carácter que encierra los campos de texto en su CSV. Debe coincidir con su archivo. |
| | Omitir primera línea (encabezado) | SÍ (si existe encabezado) | Ignora la primera fila de su CSV si es un encabezado. |
| | **Configuración de vales (General)** | | |
| | Nombre | Nombre descriptivo | Nombre interno de la regla de vale en el BO. |
| | Descripción | Texto opcional | Descripción interna de la regla de vale. |
| | Resaltar | NO | Resalta el vale en el resumen del carrito. |
| | Uso parcial | NO | Permite el uso parcial del valor del vale. SÍ para tarjetas de regalo. |
| | Prioridad | 1 | Orden de aplicación para múltiples vales. |
| | Estado | SÍ | Activa/desactiva la regla de vale. |
| | **Configuración de vales (Condiciones)** | | |
| | Cantidad mínima | 0 | Total mínimo del pedido para la validez del vale. |
| | Moneda | Predeterminada de la tienda | Moneda para la cantidad mínima. |
| | Acumulable con otros vales | NO | Permite combinar con otros vales. |
| | Fecha de caducidad (Desde) | Fecha actual | Fecha de inicio de la validez del vale. |
| | Fecha de caducidad (Hasta) | Fecha futura | Fecha de finalización de la validez del vale. |
| | Cantidad | 1 | Usos totales por código de vale *individual*. |
| | Cantidad por usuario | 1 | Usos totales por *cliente* de este lote. |
| | **Configuración de vales (Acciones)** | | |
| | Envío gratuito | NO | Otorga envío gratuito. |
| | Aplicar un descuento | Porcentaje / Cantidad | Tipo de descuento (porcentaje o cantidad fija). |
| | Valor | Valor numérico | El valor real del descuento (por ejemplo, 10 para 10% o 10 €). |
| | Aplicar descuento a | Pedido (sin envío) | A qué se aplica el descuento (pedido, producto específico, etc.). |
| | Enviar un regalo | NO | Añade un producto gratuito como regalo. |

## 3. Solución de problemas del comerciante y preguntas frecuentes (FAQ)

**P: He importado mi CSV, pero los vales no funcionan o no aparecen.**
R:

1.  **Verifique el estado del módulo:** Asegúrese de que el módulo esté habilitado en **Módulos > Gestor de módulos**.
2.  **Verifique el estado del vale:** Vaya a **Catálogo > Descuentos > Reglas de carrito** (o **Reglas de precio > Reglas de carrito** en versiones anteriores). Busque la regla de vale creada por la importación (tendrá el "Nombre" que especificó durante la configuración). Asegúrese de que su "Estado" esté establecido en "SÍ" (activo).
3.  **Fechas de caducidad:** Vuelva a verificar la configuración de "Fecha de caducidad (Desde)" y "Fecha de caducidad (Hasta)". Si la fecha actual está fuera de este rango, los vales no funcionarán.
4.  **Cantidad mínima:** Verifique si el carrito del cliente cumple con la condición de "Cantidad mínima" que estableció.
5.  **Códigos de vale:** Asegúrese de que los códigos de su CSV sean exactamente como los introducen los clientes (sensibles a mayúsculas y minúsculas, sin espacios adicionales).

**P: Mi archivo CSV no se analiza correctamente. Todos los datos están en una columna o las columnas están mezcladas.**
R: Esto casi siempre se debe a una configuración incorrecta del "Separador CSV" o del "Delimitador de texto".

1.  **Abra su archivo CSV** en un editor de texto plano (como Notepad, Sublime Text, VS Code, o incluso Excel/Google Sheets, pero luego guárdelo de nuevo como CSV).
2.  **Identifique el separador:** Observe cómo se separan los valores. ¿Es una coma (`,`), un punto y coma (`;`) o un tabulador? Seleccione el correcto en la configuración del módulo.
3.  **Identifique el delimitador:** Busque caracteres que encierren el texto, generalmente comillas dobles (`"`). Si están presentes, asegúrese de que el "Delimitador de texto" esté establecido en "Comilla doble".
4.  **Fila de encabezado:** Si su CSV tiene un encabezado, asegúrese de que "Omitir primera línea (encabezado)" esté establecido en "SÍ".

**P: He importado vales, pero ahora quiero eliminarlos o deshabilitarlos.**
R:

1.  Vaya a **Catálogo > Descuentos > Reglas de carrito** (o **Reglas de precio > Reglas de carrito**).
2.  Busque la regla de vale que creó con el módulo (usando el "Nombre" que le asignó).
3.  Puede:
    -   **Deshabilitar:** Haga clic en la marca de verificación verde junto a la regla para convertirla en una "X" roja. Esto desactiva todos los vales bajo esa regla.
    -   **Eliminar:** Seleccione la regla y use las acciones masivas o haga clic en el icono de eliminar para eliminar toda la regla y todos los códigos de vale asociados.

La eliminación de una regla de carrito es permanente y no se puede deshacer.

**P: ¿Puedo actualizar vales existentes con este módulo?**
R: No, este módulo está diseñado para importar vales *nuevos*. No tiene funcionalidad para actualizar códigos de vale o reglas de carrito existentes. Si necesita modificar un vale existente, debe hacerlo manualmente a través de **Catálogo > Descuentos > Reglas de carrito**.

**P: ¿Por qué mis vales importados no son acumulables con otros descuentos?**
R: Verifique la configuración de "Acumulable con otros vales" en la configuración del módulo. Si lo configuró en "NO" (lo que a menudo se recomienda para códigos únicos), los clientes no podrán usar estos vales junto con otros descuentos activos en su carrito. Si desea que sean acumulables, configúrelo en "SÍ" durante la importación.

## 4. Guía para desarrolladores y webmasters (Arquitectura técnica y mapa de código)

Esta sección proporciona una descripción técnica detallada para desarrolladores y webmasters que trabajan con el módulo "Importar vales desde CSV".

### 4.1 Descripción general de la arquitectura

El módulo `importvoucher` es un módulo estándar de PrestaShop centrado principalmente en la funcionalidad del Back Office. Aprovecha los ObjectModels centrales `CartRule` y `CartRuleProduct` de PrestaShop para crear y gestionar códigos de descuento. La lógica principal del módulo reside en su archivo PHP principal, que gestiona la carga de archivos, el análisis de CSV y las interacciones con la base de datos. No introduce patrones MVC complejos con controladores frontales o de administración dedicados, sino que utiliza el método `getContent()` para su interfaz de configuración.

### 4.2 Controladores (`controllers/`)

Este módulo no utiliza controladores dedicados de front office o back office en los directorios `controllers/front` o `controllers/admin`. Toda la lógica administrativa, incluido el formulario de configuración y el proceso de importación de CSV, se gestiona directamente dentro del método `getContent()` del archivo principal del módulo.

### 4.3 Clases y modelos principales (`classes/`)

El módulo no define clases personalizadas en un directorio `classes/`. Interactúa directamente con los ObjectModels centrales `CartRule` y `CartRuleProduct` de PrestaShop para crear y gestionar códigos de descuento.

-   **`CartRule` (Clase central de PrestaShop):**

    -   Interactúa con la tabla de base de datos `ps_cart_rule`.
    -   El módulo rellena las propiedades de los objetos `CartRule` (por ejemplo, `name`, `description`, `code`, `quantity`, `quantity_per_user`, `date_from`, `date_to`, `minimum_amount`, `reduction_percent`, `reduction_amount`, `free_shipping`, `active`, `highlight`, `partial_use`, `priority`, `cumulative_with_other_rules`) basándose en la configuración y los datos CSV.
    -   El método `add()` de `CartRule` se utiliza para persistir las nuevas reglas de vale en la base de datos.
-   **`CartRuleProduct` (Clase central de PrestaShop):**

    -   Interactúa con las tablas `ps_cart_rule_product_rule_group` y `ps_cart_rule_product_rule`.
    -   Se utiliza cuando se elige la opción "Aplicar descuento a: Productos seleccionados" para vincular la regla de carrito a productos, categorías o fabricantes específicos.

### 4.4 Activos JavaScript (`views/js/`)

-   `importvoucher/lib/voucherengine/script.js`:
    -   **Alcance:** Back office.
    -   **Propósito:** Este script probablemente maneja interacciones dinámicas en la página de configuración del módulo. Esto podría incluir:
        -   Mostrar/ocultar campos según las opciones seleccionadas (por ejemplo, mostrar la entrada "Valor" solo cuando se selecciona el tipo de descuento "Porcentaje" o "Cantidad").
        -   Llamadas AJAX para la validación o procesamiento de formularios.
        -   Inicialización del selector de fechas para "Fecha de caducidad (Desde)" y "Fecha de caducidad (Hasta)".
        -   Posiblemente vistas previas de análisis de CSV del lado del cliente o manejo de errores.
    -   **Interacción:** Vincula oyentes de eventos a elementos de formulario (por ejemplo, eventos `change` en botones de radio, `click` en botones).

### 4.5 Hojas de estilo CSS (`views/css/`)

-   `importvoucher/lib/voucherengine/ps16.css`:

    -   **Alcance:** Back office (probablemente para compatibilidad con PrestaShop 1.6, pero puede cargarse en versiones más nuevas para estilos generales).
    -   **Propósito:** Proporciona estilos para la interfaz de configuración del módulo, asegurando que se integre visualmente con el tema del Back Office de PrestaShop 1.6. Puede contener estilos generales de elementos de formulario, ajustes de diseño y estilos específicos basados en clases para los componentes del módulo.
    -   **Selectores clave:** Probablemente apunta a elementos de formulario genéricos (`.form-group`, `.control-label`, `.form-control`) y posiblemente a envoltorios específicos del módulo (por ejemplo, `#module_form_importvoucher`).
-   `importvoucher/views/css/css.css`:

    -   **Alcance:** Back office.
    -   **Propósito:** Contiene reglas de estilo generales o específicas para la página de configuración del módulo. Esto podría anular o extender `ps16.css` para versiones más nuevas de PrestaShop o proporcionar estilos únicos para elementos personalizados dentro de la plantilla del módulo.
    -   **Selectores clave:** Similar a `ps16.css`, centrándose en los elementos de la interfaz de usuario del módulo. Los desarrolladores deben inspeccionar este archivo para ver los nombres de clase específicos que deben anularse en sus temas de administración personalizados si es necesario.

### 4.6 Estructura de la plantilla Smarty (`views/templates/`)

El módulo utiliza plantillas Smarty para renderizar su interfaz de configuración del Back Office.

-   **`importvoucher/views/backoffice.tpl`**:

    -   **Alcance:** Plantilla de administración.
    -   **Propósito:** Este es probablemente el archivo de plantilla principal renderizado por el método `getContent()`. Actúa como contenedor para todo el formulario de configuración del módulo, incluidos todos los ajustes, campos de entrada y botones. Probablemente incluye otras plantillas parciales.
    -   **Contenido:** Contiene la estructura HTML para la página de configuración del módulo, incluidas las etiquetas de formulario, los fieldsets y posiblemente llamadas para incluir otros archivos `.tpl`.
-   **`importvoucher/views/csv.tpl`**:

    -   **Alcance:** Plantilla de administración.
    -   **Propósito:** Esta plantilla probablemente maneja la visualización de la sección de carga de archivos CSV y los ajustes relacionados (separador, delimitador, omitir encabezado). Es una plantilla parcial incluida dentro de `backoffice.tpl`.
-   **`importvoucher/views/csv_file.tpl`**:

    -   **Alcance:** Plantilla de administración.
    -   **Propósito:** Una plantilla parcial más granular, posiblemente específicamente para el campo de entrada de archivo en sí, o para mostrar información sobre el archivo CSV cargado.
-   **`importvoucher/views/file_settings.tpl`**:

    -   **Alcance:** Plantilla de administración.
    -   **Propósito:** Esta plantilla probablemente renderiza la sección "Configuración del archivo CSV", incluidas las entradas para el separador CSV, el delimitador de texto y la casilla de verificación "omitir primera línea".

### 4.7 Esquema de la base de datos y mapa de hooks

-   **Tablas de la base de datos:**
    El módulo no crea tablas de base de datos personalizadas. Interactúa directamente con las tablas centrales de PrestaShop relacionadas con las reglas de carrito:

    -   `ps_cart_rule`: Almacena las propiedades principales de cada regla de descuento (nombre, código, fechas, cantidad mínima, etc.).
    -   `ps_cart_rule_lang`: Almacena campos específicos del idioma para las reglas de carrito (por ejemplo, `name` si es multilingüe).
    -   `ps_cart_rule_product_rule_group`: Se utiliza al aplicar descuentos a productos/categorías específicos.
    -   `ps_cart_rule_product_rule`: Define las reglas de producto reales dentro de un grupo.
    -   `ps_cart_rule_product_rule_exclusion`: Para excluir productos específicos de una regla.
    -   `ps_cart_rule_carrier`: Para restricciones de transportista.
    -   `ps_cart_rule_country`: Para restricciones de país.
    -   `ps_cart_rule_group`: Para restricciones de grupo de clientes.
    -   `ps_cart_rule_shop`: Para el contexto de múltiples tiendas.
-   **Tabla de Hooks registrados:**
    La función principal del módulo está en la configuración del Back Office. Si bien la descripción del módulo menciona "Hooks del Front Office: Encabezado, Columnas, Producto o Pie de página", el inventario de archivos proporcionado y la funcionalidad típica de un módulo de importación sugieren que no renderiza activamente contenido en estos hooks del front office. Estas menciones podrían ser genéricas o referirse a dónde se ven los *efectos* de los vales importados (por ejemplo, un vale aplicado en el carrito, que forma parte del flujo de pago, potencialmente influenciado por hooks).

    El módulo utiliza principalmente el siguiente hook para su interfaz de Back Office:

    | Nombre del Hook | Momento de ejecución | Propósito técnico |
    | --- | --- | --- |
    | `displayBackOfficeHeader` | Se renderiza en la sección `<head>` de las páginas del Back Office. | Se utiliza para incluir activos CSS y JavaScript para la página de configuración del módulo. |
    | `moduleRoutes` (PrestaShop 1.7+) | Cuando se inicializan las rutas del módulo. | Si el módulo tuviera controladores frontales personalizados, este hook definiría sus URL. (No aplicable aquí ya que no hay controladores frontales personalizados). |

    La lógica central del módulo para *crear* vales no se basa en hooks específicos de PrestaShop, sino en llamadas directas a los métodos de `CartRule` activadas por el envío del formulario en `getContent()`.

## 5. Soporte oficial y actualizaciones

Para obtener las últimas actualizaciones, correcciones de errores y soporte oficial para el módulo "Importar vales desde CSV", consulte su cuenta de cliente en [MyPresta.eu](https://mypresta.eu). Nuestro equipo de soporte está disponible para ayudarle con cualquier problema o pregunta que pueda tener con respecto a la funcionalidad y compatibilidad del módulo.
