---
title: MyFAQ - documentación y manual de usuario
sidebar:
  label: MyFAQ - documentación y manual de usuario
description: Manual de configuración y resolución de problemas para tiendas que ya tienen MyFAQ.
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo MyFAQ: product FAQ with FAQPage schema en MyPresta.eu](https://mypresta.eu/modules/front-office-features/myfaq-product-faq-with-faqpage-schema.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/front-office/myfaq-product-faq-with-faqpage-schema/)
>
> ---


## 1. Requisitos

MyFAQ funciona dentro de PrestaShop. No necesita otro módulo.

- PrestaShop 1.7.0.0 hasta PrestaShop 9. El mismo paquete y las mismas pantallas sirven en PrestaShop 8 y en PrestaShop 9.
- PHP 7.0 o más reciente, y como mínimo la versión de PHP que exige esa versión de PrestaShop. La instalación y la dirección programada usan `random_bytes`.
- cURL es necesario para generar preguntas. Sin cURL la generación se detiene y la línea de progreso muestra `curl_missing`. La comprobación de actualizaciones usa cURL cuando PHP lo tiene, y lee la dirección directamente cuando cURL falta y el servidor permite lecturas remotas.
- OpenSSL cifra la clave de IA que guarda. Sin OpenSSL la clave queda guardada tal como la pega.
- Ningún otro módulo es obligatorio. La página de producto del tema tiene que imprimir el pie del producto o las pestañas extra del producto para que el cliente vea el acordeón.
- Una cuenta en OpenAI, Anthropic, Google, DeepSeek o Mistral hace falta solo para ese proveedor. La ficha compatible puede apuntar a su propio servidor, por ejemplo Ollama, vLLM o LM Studio, y ese servidor puede funcionar sin cuenta externa.
- Un sistema externo hace falta solo cuando llama a la dirección de la FAQ desde fuera de la tienda. Un programador de tareas hace falta solo cuando el servidor debe terminar una cola con el back office cerrado.

Un catálogo grande se escribe un idioma cada vez. Deje abierta la página de generación masiva hasta que la barra llegue al 100 %, o programe la dirección de **Generación masiva**. Cada llamada trabaja unos 20 segundos y luego se detiene, para no chocar con el límite de tiempo de PHP. Una llamada escribe como máximo 30 idiomas.

## 2. Instalación

1. En el back office abra **Módulos** y después **Gestor de módulos**.
2. Suba el zip del módulo y pulse **Instalar**.
3. Abra **Configurar** en **MyFAQ**. La página se abre en **Visualización**. La barra tiene también **Entradas**, **IA**, **Generación masiva**, **API** y **Actualizaciones**.
4. MyFAQ no añade un punto propio al menú izquierdo. El catálogo, la lista de claves y el historial de solicitudes son páginas ocultas. La primera apertura de **Configurar** las crea y da al perfil del empleado actual el derecho de abrirlas.
5. La instalación no vacía la caché en un paso aparte. Si después de una actualización la página de producto sigue mostrando el diseño anterior, vacíe la caché en **Parámetros avanzados**, **Rendimiento**.

En un producto, abra el producto y el bloque **MyFAQ**. Ahí fija la ubicación de ese producto y escribe preguntas que pertenecen solo a él.

Para apagar el módulo, use el interruptor del **Gestor de módulos**. La página de producto deja de imprimir el acordeón y la ficha del producto deja de mostrar el bloque MyFAQ. Las preguntas, las claves y los ajustes se quedan. Vuelva a encenderlo y se usan como antes. El módulo no tiene un botón propio de activar o desactivar.

Para quitarlo, pulse **Desinstalar** y confirme. La desinstalación quita las páginas ocultas, las preguntas y respuestas, los vínculos, la ubicación por producto, las claves API, el historial de solicitudes, la cola de generación y los ajustes de visualización y de IA. Las dos direcciones programadas dejan de funcionar porque se borra el secreto que llevan. Los archivos del módulo siguen en el servidor hasta que borre el módulo. Instalar de nuevo empieza con entradas vacías y los ajustes de una instalación nueva. Las preguntas antiguas no vuelven. El interruptor de comprobación de actualizaciones no se borra al desinstalar.

## 3. Configuración y trabajo diario

Escriba una pregunta y una respuesta, y vincule esa entrada a un producto o a algo que el producto ya tenga: una categoría, un valor de característica, un valor de atributo, una etiqueta, una marca o un proveedor. Basta un vínculo que coincida. La FAQ de la página de producto es el acordeón que la tienda imprime después de reunir cada coincidencia activa en el idioma del cliente y de sustituir los tokens. Las entradas vinculadas directamente al producto van primero. Después, el orden es la posición que usted fije.

El pie de producto queda bajo el producto. La pestaña de producto es el mismo acordeón dentro de una pestaña. En un producto puede forzar el pie, forzar la pestaña u ocultar MyFAQ. Ocultar también quita el bloque FAQ que leen los buscadores. El cliente solo abre las preguntas. No hay un formulario para que el cliente envíe una pregunta nueva. El recorrido termina cuando la página de producto muestra el acordeón, o cuando la ubicación es **Ocultar** o ninguna entrada activa coincide: entonces ese producto no muestra bloque MyFAQ.

Escribir con un modelo es opcional. Guarde el proveedor y la clave en **IA**. Guardar ahí no genera nada. **Generar** en un producto, o **Iniciar generación** en **Generación masiva**, pone el trabajo en cola. Cada idioma de un producto es una solicitud. **Añadir** conserva las entradas de IA actuales y añade otras. **Reemplazar entradas de IA no bloqueadas vinculadas solo al producto** borra las entradas de IA no bloqueadas que están vinculadas solo a ese producto y luego escribe otras. Una entrada que usted editó queda bloqueada y se conserva. Una entrada vinculada también a una categoría u otro destino se conserva. La dirección programada no lee los filtros de **Generación masiva**. Termina una cola que ya existe o, con la segunda dirección, añade cada producto activo de esta tienda que todavía no tiene entrada de IA.

Un sistema externo es opcional. En **API** genere una clave, copie la URL base y pegue ambas en ese sistema.

Abra **Módulos**, **Gestor de módulos**, **MyFAQ**, **Configurar**. La línea bajo la barra explica la sección abierta.

Los nombres de las fichas de proveedor, los títulos de las tarjetas de datos y los textos de los botones de shortcode permanecen en inglés en pantalla. Las frases de la barra de progreso también permanecen en inglés.

### 3.1 Visualización

**Visualización** es la presentación de toda la tienda. Un producto concreto puede usar otra ubicación.

| Campo | Al inicio | Qué hace |
|---|---|---|
| **Ubicación** | Pie del producto | Valor de la tienda para cada producto que no define el suyo. **Pie del producto** imprime el acordeón bajo el producto. **Pestaña del producto** añade una pestaña en la página del producto. En un producto aún puede forzar el pie, la pestaña u ocultar MyFAQ. Los demás módulos del mismo hook se quedan donde **Diseño**, **Posiciones** los coloca. |
| **Título de la pestaña** | FAQ en cada idioma | Etiqueta de la pestaña del producto. Solo se usa cuando la ubicación es **Pestaña del producto**. Rellénela en cada idioma que vende la tienda. Si un idioma está vacío, ese idioma muestra FAQ. |
| **Encabezado sobre la lista** | FAQ en cada idioma | Encabezado impreso sobre las preguntas, en el pie y en la pestaña. Rellénelo por idioma. Los clientes ven este texto. Deje FAQ si no necesita un encabezado propio. |
| **Incluir categorías padre** | No | **Sí** muestra también una entrada vinculada a un padre de las categorías del producto, de modo que un vínculo cubre las subcategorías. El recorrido se detiene antes de Inicio, así que un vínculo a Inicio no cubre todo el catálogo. **No** coincide solo con las categorías en las que está directamente el producto. |
| **Abrir la primera pregunta** | No | **Sí** expande la primera respuesta al cargar la página. **No** deja todas las respuestas cerradas hasta que el cliente hace clic. Los clientes sin JavaScript siempre ven las respuestas. |
| **Marcado de esquema FAQ** | Sí | **Sí** añade un bloque schema.org FAQPage creado a partir de las preguntas que realmente se muestran en ese producto, después de sustituir los shortcodes. Los buscadores pueden usarlo para resultados enriquecidos de FAQ. **No** imprime la FAQ sin ese bloque. Una lista vacía o un producto oculto nunca lo generan. |

Pulse **Guardar**. La página muestra **Guardado.**

### 3.2 Entradas

**Entradas** es una vista previa de las preguntas. La línea bajo la barra dice que son las 10 entradas actualizadas más recientemente, y que **Nueva entrada** y **Editar** abren el catálogo.

| Campo | Al inicio | Qué hace |
|---|---|---|
| **Nueva entrada** | un botón | Abre el formulario del catálogo para una pregunta nueva. |
| **Ver lista completa** | un botón | Abre el catálogo con búsqueda, donde cambia el orden y borra una entrada. |
| **Pregunta** | vacía hasta que guarda una | La pregunta en el idioma actual del back office. **No hay pregunta en este idioma** significa que ese idioma no tiene texto de pregunta. |
| **Vinculada a** | vacío | Hasta cuatro vínculos y después puntos suspensivos. |
| **Origen** | Escrita a mano en una entrada que usted escribió | **IA** o **Escrita a mano**. **bloqueada** significa que un reemplazo posterior conserva esta entrada. |
| **Estado** | Activa en una entrada nueva | **Activa** se muestra en las páginas de producto que coinciden. **Inactiva** se queda en el back office y se oculta en la tienda. |

El número de la derecha es el total de entradas, no solo las diez de esta vista. **Editar** abre esa entrada en el catálogo.

Cuando no hay entradas, la página dice **Aún no hay entradas** y explica que la tienda no muestra nada hasta que una entrada activa esté vinculada a un producto, categoría, característica, atributo, etiqueta, marca o proveedor.

### 3.3 Catálogo

Abra **Ver lista completa**. El título de la página es **Entradas de FAQ**. La nota de arriba dice que la búsqueda coincide con la pregunta, el nombre o el id del producto, el idioma y los demás vínculos. La pregunta es la del idioma actual del back office. El nombre del producto abre ese producto. **Editar** abre el formulario en esta página. **Arriba** y **Abajo** mueven la entrada. Arrastre la columna de posición para fijar el mismo orden. **Eliminar** pide confirmación. **Activa** muestra u oculta la entrada. Las entradas bloqueadas se conservan cuando la IA reemplaza un producto.

Columnas: **ID**, **Pregunta**, **Producto**, **También vinculada a**, **Idiomas**, **Tienda**, **Origen**, **Activa**, **Bloqueada**, **Posición**, **Creada**, **Actualizada**.

**Tienda** muestra **Todas las tiendas** cuando la entrada se guardó con el contexto de todas las tiendas. Si no, muestra el nombre de esa tienda. La tienda pública de una tienda muestra las entradas de todas las tiendas y las guardadas para esa tienda.

**Origen** es **Escrita a mano** o **IA**. Filtre esa columna con la lista. **Activa** es un interruptor en la fila: púlselo para mostrar u ocultar la entrada. **Bloqueada** es una marca, no un interruptor. Editar una entrada existente la bloquea. Una entrada nueva no queda bloqueada.

Las acciones de fila son **Editar**, **Arriba**, **Abajo** y **Eliminar**. **Eliminar** pregunta **¿Eliminar esta entrada? Desaparecerá de todos los productos que la usaban.** La acción agrupada **Eliminar seleccionadas** pregunta **¿Eliminar las entradas seleccionadas? Desaparecerán de todos los productos que las usaban.** Si un borrado no termina, la página muestra **No se pudo eliminar la entrada.**

**Nueva entrada** en la barra abre un formulario en blanco. **Volver al módulo** vuelve a **Entradas**.

El título del formulario es **Nueva entrada** o **Editar entrada**.

| Campo | Al inicio | Qué hace |
|---|---|---|
| **Pregunta** | vacía | La línea que el cliente pulsa para abrir la respuesta. Es el encabezado del acordeón. Escriba una pregunta por idioma. La ayuda bajo el campo dice que el idioma predeterminado es obligatorio. La pregunta también puede contener shortcodes. Se sustituyen en la página del producto y se muestran como texto simple. Si todos los idiomas están vacíos, **Guardar** muestra **Escribe una pregunta en al menos un idioma.** |
| **Respuesta** | vacía | El texto que se revela cuando el cliente abre la pregunta. Use el editor para párrafos y listas. Los shortcodes se sustituyen en la página del producto y el HTML que los rodea se mantiene. La lista de shortcodes está bajo este campo: pulse un token para insertarlo en el cursor. Rellene cada idioma que venda. Un idioma vacío no se muestra en ese idioma. |
| **Shortcodes** | los botones de token | Pulse un token para insertarlo donde está el cursor, en la pregunta o en la respuesta. La tienda lo sustituye en la página del producto por los datos de ese producto, en el idioma y la moneda del cliente. El texto guardado conserva el token, así que un cambio de precio o de nombre actualiza cada entrada que lo usa. En la pregunta el resultado es texto simple. |
| **Activa** | Sí | **Sí** muestra la entrada en las páginas de producto que coinciden y la incluye en el esquema. **No** la mantiene en el back office y la oculta de la tienda. |
| **Productos** | ninguno | Escriba el nombre de un producto en el cuadro de búsqueda y selecciónelo. La entrada se muestra en esos productos aunque ningún otro vínculo coincida. Basta un vínculo coincidente. Guardar reemplaza los vínculos anteriores de esta entrada. |
| **Categorías** | ninguna | Escriba el nombre de una categoría y selecciónela. La entrada se muestra en los productos colocados en esas categorías. Un vínculo es una FAQ para toda una categoría. Las categorías padre cuentan solo si esa opción está activa en **Visualización**. |
| **Valores de característica** | ninguno | Escriba un valor de característica y selecciónelo, por ejemplo Algodón. La entrada se muestra cuando el producto tiene ese valor. |
| **Valores de atributo** | ninguno | Escriba un valor de atributo y selecciónelo, por ejemplo M. La entrada se muestra cuando cualquier combinación del producto usa ese valor. |
| **Etiquetas** | ninguna | Escriba una etiqueta y selecciónela. La entrada se muestra cuando el producto tiene esta etiqueta en el idioma de la página. |
| **Marcas** | ninguna | Escriba un nombre de marca y selecciónelo. La entrada se muestra en los productos de estas marcas. |
| **Proveedores** | ninguno | Escriba un nombre de proveedor y selecciónelo. La entrada se muestra en los productos de estos proveedores, incluido el proveedor predeterminado y los proveedores añadidos en combinaciones. |

**Guardar** sin ningún vínculo muestra **Vincula la entrada al menos a un producto, categoría, característica, atributo, etiqueta, marca o proveedor.** Si la fila no se puede guardar, la página muestra **No se pudo guardar la entrada.** Un guardado correcto se queda en el formulario y PrestaShop confirma la actualización. **Volver al listado** vuelve al catálogo.

Los botones de token, y el texto en inglés de cada botón, son:

| Token | Qué ve el cliente |
|---|---|
| `[product_name]` | Nombre del producto |
| `[product_reference]` | Referencia |
| `[product_ean13]` | EAN-13 |
| `[product_isbn]` | ISBN |
| `[product_upc]` | UPC |
| `[product_mpn]` | MPN |
| `[product_condition]` | Estado: New, Used o Refurbished |
| `[product_price]` | Precio con impuestos, en la moneda del cliente |
| `[product_price_tax_excl]` | Precio sin impuestos |
| `[product_price_before_discount]` | Precio antes de la reducción |
| `[product_discount_amount]` | Importe del descuento, vacío cuando no hay reducción |
| `[product_discount_percent]` | Porcentaje de descuento, vacío cuando no hay reducción |
| `[product_quantity]` | Cantidad disponible de la combinación predeterminada, o del producto si no hay combinaciones |
| `[product_availability]` | Etiqueta de disponible ahora si la cantidad es mayor que cero, o la etiqueta de disponible más tarde si la cantidad es cero |
| `[product_minimal_quantity]` | Cantidad mínima |
| `[product_manufacturer]` | Marca |
| `[product_supplier]` | Proveedor |
| `[product_category]` | Categoría predeterminada |
| `[product_categories]` | Todas las categorías |
| `[product_features]` | Lista de características, nombre y valor |
| `[product_feature id=ID]` | Un valor de característica. Sustituya ID por el número de la característica en **Catálogo**, **Atributos y características**. |
| `[product_tags]` | Etiquetas en el idioma actual |
| `[product_url]` | URL del producto |
| `[product_weight]` | Peso con la unidad de peso de la tienda |
| `[product_description_short]` | Descripción corta, en texto simple |
| `[shop_name]` | Nombre de la tienda |
| `[shop_url]` | URL de la tienda |

La línea bajo los botones dice que pulse un shortcode para insertarlo en el cursor. Los precios y los nombres se sustituyen en la página del producto, en la moneda y el idioma del cliente. `[product_price]` es el shortcode de precio: se convierte en el precio vivo dentro de una respuesta, en la moneda del cliente.

### 3.4 IA

**IA** guarda la conexión que usa el generador. La línea bajo la barra dice que guardar aquí no genera nada. Use **Generación masiva** para muchos productos, o el bloque del producto para uno.

Pulse una ficha. La ficha en uso muestra **Activo**. Una ficha muestra **Clave guardada**, **Sin clave**, o **Clave opcional** en la ficha compatible. Los nombres de las fichas se quedan en inglés.

| Ficha | A qué llama |
|---|---|
| **OpenAI** | Modelos GPT con la API oficial de OpenAI. La lista empieza por `gpt-4o-mini`, `gpt-4o`, `gpt-4.1-mini`, `gpt-4.1`. |
| **Anthropic Claude** | Modelos Claude con la API oficial de Anthropic. La lista empieza por `claude-sonnet-4-5`, `claude-3-5-haiku-latest`, `claude-3-5-sonnet-latest`. |
| **Google Gemini** | Modelos Gemini con la API oficial de Google. La lista empieza por `gemini-2.0-flash`, `gemini-1.5-pro`, `gemini-1.5-flash`. |
| **DeepSeek** | Modelos DeepSeek mediante una API compatible con OpenAI. La lista empieza por `deepseek-chat`. |
| **Mistral AI** | Modelos Mistral con la API oficial. La lista empieza por `mistral-small-latest`, `mistral-large-latest`. |
| **OpenAI-compatible / Ollama** | Su propio servidor: Ollama, vLLM, LM Studio. Puede funcionar totalmente en local. La lista está vacía hasta que añade un ID de modelo. |

| Campo | Al inicio | Qué hace |
|---|---|---|
| **Proveedor** | OpenAI | Pulse una ficha para elegir el servicio que escribe las preguntas. La lista de modelos cambia al momento. **Guardar** almacena el proveedor, la clave y el modelo. Los proveedores oficiales llaman a su propio host. La URL base solo aparece en la ficha compatible. |
| **Clave API** | vacía | Secreto de la cuenta del proveedor de la ficha seleccionada. Pegue una clave nueva para reemplazar la guardada. Deje el campo vacío y guarde para conservar la clave ya almacenada para ese proveedor. La clave se cifra cuando el servidor tiene OpenSSL. Cada ficha indica si hay una clave guardada. Un servidor local compatible, como Ollama, puede quedarse sin clave. |
| **Eliminar la clave guardada** | No | **Sí** elimina al guardar la clave guardada del proveedor seleccionado. Úselo cuando rota o revoca una clave. **No** deja la clave guardada en su sitio. Generar sin clave falla con los proveedores oficiales. |
| **URL base compatible** | vacía | Solo se usa cuando está seleccionada la ficha compatible. Escriba la raíz de la API que termina en `/v1`, por ejemplo `http://localhost:11434/v1` para Ollama. Los proveedores oficiales ignoran este campo. Si lo deja vacío, una ejecución no arranca y la página muestra **Define la URL base compatible en la pestaña IA antes de iniciar una ejecución.** |
| **Modelo** | `gpt-4o-mini` para OpenAI | ID del modelo enviado en cada generación para el proveedor seleccionado. La lista contiene los IDs integrados y los que añadió en el cuadro bajo este formulario. Un ID incorrecto lo rechaza el proveedor y ese idioma se marca como fallido en la cola. La ficha compatible muestra **Aún no hay modelo. Añade uno abajo.** hasta que añade uno. |
| **Temperatura** | 0,4 | Qué libre escribe el modelo, de 0 a 2. 0,4 mantiene las respuestas cerca de los datos del producto. Un valor más alto varía la redacción y puede desviarse de los hechos. Los valores fuera de 0 a 2 vuelven a ese intervalo. Algunos proveedores rechazan este ajuste. El módulo entonces reintenta una vez sin él. |
| **Tokens máximos** | 2000 | Límite superior de la longitud de una respuesta. 2000 basta para unas cuantas respuestas cortas. Súbalo si las respuestas se cortan. El proveedor puede detenerse antes. Los valores muy altos cuestan más y pueden alcanzar el límite del proveedor. El valor guardado se queda entre 200 y 8000. |
| **Preguntas por producto** | 5 | Cuántos pares pregunta-respuesta pedir para cada producto y cada idioma. Este número es el predeterminado en **Generación masiva** y en la página del producto. 5 es un inicio práctico. Una ejecución posterior puede usar otro número. El valor guardado se queda entre 1 y 20. |
| **Instrucciones adicionales** | vacío | Reglas opcionales añadidas a cada prompt: tono, longitud o temas que omitir. El módulo ya indica al modelo que escriba `[product_name]` y `[product_price]` en lugar de un nombre o un precio fijo, para que un cambio de precio posterior siga siendo correcto. Déjelo vacío para usar solo las instrucciones integradas. |

Pulse **Guardar**. La página muestra **Guardado.**

**Modelos que añadiste** está bajo el formulario. Es un cuadro aparte para los IDs que no están en la lista integrada. Renombre o elimine solo estos. Los modelos integrados permanecen en la lista **Modelo** y no tienen botón de eliminar.

| Campo | Al inicio | Qué hace |
|---|---|---|
| **Nuevo ID de modelo** | vacío | Añade el ID a la ficha de proveedor seleccionada arriba y lo elige para la próxima ejecución. Solo letras, dígitos y `.` `_` `:` `/` `@` `-`, hasta 100 caracteres. Un ID integrado se rechaza. |
| **Añadir modelo** | un botón | Guarda ese ID. |
| **Guardar** en una fila que usted añadió | el ID actual | Renombra ese ID. Si era el modelo seleccionado, la selección sigue al ID nuevo. |
| **Eliminar** | un botón en una fila que usted añadió | Pregunta **¿Eliminar este modelo?** y quita ese ID. Un ID integrado no se puede quitar. |

Hasta que añade uno, el cuadro dice **Aún no hay un modelo propio para este proveedor. Los IDs integrados siguen en la lista de arriba.**

Mensajes que puede ver aquí:

- **Elige un proveedor antes de añadir un modelo.**
- **Ese ID ya es un modelo integrado. Permanece en la lista y no se puede volver a añadir.**
- **Ese ID de modelo no es válido. Usa letras, dígitos y . _ : / @ -, hasta 100 caracteres.**
- **Los modelos integrados no se pueden editar.**
- **Ese ID es un modelo integrado. Escribe un ID diferente.**
- **No se pudo renombrar ese modelo. Usa un ID nuevo que no esté ya en la lista.**
- **Los modelos integrados no se pueden eliminar.**
- **Ese modelo no lo añadiste tú, así que se dejó en su sitio.**

### 3.5 Generación masiva

**Generación masiva** pone en cola muchos productos. La línea bajo la barra dice que los filtros vacíos se ignoran, que **Iniciar generación** escribe un idioma por solicitud y que esta página muestra una barra del 0 % al 100 %. La dirección programada no lee estos filtros.

**Productos activos en esta tienda** muestra el recuento de productos activos antes de cualquier filtro. Ese número es el catálogo de la tienda, no un valor fijo del módulo.

| Campo | Al inicio | Qué hace |
|---|---|---|
| **Categorías** | ninguna marcada | Marque cada categoría a incluir. Una subcategoría no se incluye salvo que también la marque. Deje el árbol vacío para ignorar las categorías. Un producto que esté en varias categorías marcadas se pone en cola una sola vez. |
| **Marcas** | ninguna seleccionada | Mantenga pulsado Ctrl o Cmd y haga clic en una o más marcas. Solo se ponen en cola los productos de esas marcas. Deje la lista sin tocar para ignorar la marca. Combinado con las categorías, el producto debe estar en una categoría marcada y en una de estas marcas. |
| **Proveedores** | ninguno seleccionado | Mantenga pulsado Ctrl o Cmd y haga clic en uno o más proveedores. Un producto coincide cuando ese proveedor es el predeterminado o un proveedor adicional. Deje la lista sin tocar para ignorar el proveedor. |
| **Omitir productos que ya tienen una entrada de IA** | No | **Sí** omite los productos que ya tienen una entrada de IA vinculada directamente. Las entradas escritas a mano no cuentan, así que esos productos siguen en la cola. **No** vuelve a encolar los productos que coinciden. |
| **Omitir productos que ya tienen cualquier FAQ** | No | **Sí** omite los productos que ya tienen cualquier entrada vinculada directamente, incluidas las escritas a mano. **No** solo aplica el interruptor de IA de arriba. |
| **Solo productos en stock** | No | **Sí** conserva los productos con una cantidad mayor que cero, incluida una combinación que esté en stock. **No** ignora el stock. |
| **Solo productos con imagen de portada** | No | **Sí** omite los productos que no tienen imagen de portada en esta tienda. **No** ignora las imágenes. |
| **Solo productos con descripción** | No | **Sí** conserva los productos cuya descripción corta o completa esté rellena en el idioma predeterminado de la tienda. **No** ignora el texto. |
| **Precio base desde** | vacío | Precio de catálogo sin impuestos, antes de los precios específicos. Déjelo vacío para no fijar mínimo. Un producto por debajo de este precio se omite. |
| **Precio base hasta** | vacío | Precio de catálogo sin impuestos, antes de los precios específicos. Déjelo vacío para no fijar máximo. Un producto por encima de este precio se omite. |
| **Añadidos desde** | vacío | Pone en cola solo los productos creados en esta fecha o después. Déjelo vacío para ignorar la fecha de creación. |
| **Máximo de productos** | vacío | Se detiene tras este número de productos, empezando por el ID más bajo. 0 o vacío significa sin límite. Use un número pequeño para probar los filtros antes de una ejecución completa. |
| **Idiomas** | ninguno seleccionado | Mantenga pulsado Ctrl o Cmd y haga clic en los idiomas a escribir. Cada idioma es una solicitud por producto. Deje la lista vacía para escribir todos los idiomas activos de esta tienda. Los nombres son los idiomas de esta tienda. |
| **Preguntas** | 5, el número de **IA** | Cuántos pares escribir para cada producto en esta ejecución. Sustituye el predeterminado de la pestaña **IA** solo para esta cola. Use el mismo número en todos los idiomas del producto. |
| **Entradas de IA existentes del producto** | Añadir | **Añadir** mantiene las entradas de IA actuales y añade nuevas. **Reemplazar entradas de IA no bloqueadas vinculadas solo al producto** elimina las entradas de IA no bloqueadas vinculadas solo a ese producto, una vez por producto, y después escribe las nuevas. Las entradas que editó a mano están bloqueadas y se conservan. Las entradas también vinculadas a una categoría u otro destino se conservan. |
| **Enviar al modelo** | vea las tarjetas | Elija los datos del producto que el modelo puede leer. Una tarjeta apagada no se envía. Guardar una ejecución también almacena estas tarjetas para la próxima vez. |

Los títulos de las tarjetas bajo **Enviar al modelo** se quedan en inglés. La frase bajo cada título es la ayuda de la tarjeta.

| Tarjeta | Al inicio | Ayuda de la tarjeta |
|---|---|---|
| **Name and reference** | encendida | Título y referencia del producto. |
| **Short description** | encendida | El resumen que aparece bajo el título. |
| **Full description** | encendida | La descripción larga de la página del producto. |
| **Price summary** | encendida | Precio actual y precio anterior a un descuento. |
| **Categories** | encendida | Categoría predeterminada y las demás categorías. |
| **Features** | encendida | Nombres de características y sus valores. |
| **Brand** | encendida | Nombre de la marca. |
| **Attributes and combinations** | apagada | Atributos de cada combinación. |
| **Tags** | apagada | Etiquetas en el idioma que se escribe. |
| **Supplier** | apagada | Nombre del proveedor predeterminado. |
| **Stock and availability** | apagada | Cantidad y etiqueta de disponibilidad. |
| **Weight and dimensions** | apagada | Peso, anchura, altura y profundidad. |
| **EAN, ISBN and condition** | apagada | EAN, ISBN, UPC, MPN y estado. |
| **Attachment titles** | apagada | Títulos de los archivos adjuntos al producto. |
| **Existing questions (avoid duplicates)** | apagada | Preguntas ya publicadas, para que el modelo no las repita. |

**Ejecutar** tiene dos tarjetas.

**Iniciar en este navegador.** **Iniciar generación** pone en cola los productos que cumplen los campos de arriba, una fila por idioma. Esta página permanece abierta y muestra aquí el estado, y después envía cada idioma al modelo. Deje la pestaña abierta hasta que termine la barra. Cerrar la pestaña detiene esta página. La cola se conserva y la dirección programada puede terminarla.

La barra empieza en `Starting…` y 0 %. Mientras corre, la línea es el número hecho, una barra y el total. Al final lee `Finished.` más ese recuento. Un idioma fallido añade `failed` y el último texto de error del proveedor. Cuando nada coincide, la página muestra **Ningún producto coincide con esta selección.** Cuando la cola no se puede guardar, muestra **No se pudo crear la cola.** Cuando la ejecución no puede empezar, la línea de estado muestra `The run did not start.` Una respuesta que la página no puede leer muestra `That request could not be read.` Un paso fallido muestra `The generation request failed.` o el texto de error del proveedor. Estas frases de progreso se quedan en inglés.

**Continuar en el servidor.** No es un segundo botón de inicio. No lee de este formulario las categorías, el número de preguntas ni añadir o reemplazar. Programe una URL cada pocos minutos. Cada llamada trabaja unos 20 segundos y luego se detiene.

Copie **Terminar una cola que ya existe** después de **Iniciar generación** cuando vaya a cerrar la pestaña, o cuando una ejecución se detuvo antes de que la barra llegara al final. Solo escribe las filas que ya están en cola.

Copie **Completar productos que aún no tienen entrada de IA** cuando quiera que los productos nuevos se completen sin abrir esta página. Esa dirección añade cada producto activo de esta tienda que no tiene entrada de IA, usando el número de preguntas y las opciones de datos guardadas en **IA**. Siempre añade y después vacía la cola.

Mantenga privadas las dos direcciones. Contienen el secreto que autoriza la llamada. **Guardar** en este formulario no es lo que inicia la ejecución. Lo hace **Iniciar generación**.

Antes de una ejecución, la página se niega a empezar y muestra uno de estos:

- **Elige un proveedor en la pestaña IA antes de iniciar una ejecución.**
- **Elige un modelo en la pestaña IA antes de iniciar una ejecución.**
- **Define la URL base compatible en la pestaña IA antes de iniciar una ejecución.** Rellene **URL base compatible** en la ficha compatible. Una dirección vacía no inicia la ejecución.
- **Guarda una clave API para el proveedor seleccionado en la pestaña IA antes de iniciar una ejecución.**

### 3.6 API

**API** es para un sistema fuera de la tienda. La línea bajo la barra dice que genera aquí una clave, le pone una etiqueta y copia la URL base. **Ver lista completa** abre el catálogo de claves. **Historial de solicitudes** lista cada llamada, con los parámetros y la respuesta. **Documentación de la API** lista cada acción.

| Campo | Al inicio | Qué hace |
|---|---|---|
| **URL base** | la dirección de esta tienda | Dirección a la que llama un sistema externo. Envíe `action` y `api_key` como parámetros de consulta o como campos POST. También se acepta la cabecera `X-Api-Key`. Abra **Documentación de la API** para la lista de parámetros de cada acción. Una clave ausente o revocada se rechaza. |
| **Etiqueta de la clave** | vacía | Un nombre para distinguir claves, por ejemplo ERP o staging. No es el secreto. **Generar clave** crea un secreto nuevo y lo muestra en la tabla. **Revocar** detiene una clave y la deja en la lista. **Eliminar** borra esa fila y el secreto. Las demás claves siguen funcionando. Puede crear más de una clave. |

**Generar clave** añade la clave y vuelve a esta página. La vista previa **Claves ya emitidas** lista las cinco claves más nuevas. El recuento es el número total de claves. El secreto de esta vista está acortado. **Ver lista completa** muestra el secreto entero para copiarlo en el otro sistema.

| Columna | Para qué sirve |
|---|---|
| **Etiqueta** | El nombre que escribió. |
| **Clave** | El inicio del secreto en esta vista. El secreto completo está en la lista de claves. |
| **Estado** | **Activa** o **Revocada**. |
| **Creada** | Cuándo se generó la clave. |
| **Último uso** | La última llamada aceptada, o **Aún no utilizada**. |
| **Historial** | Abre **Historial de solicitudes** filtrado a esta clave. |
| **Revocar** | Pregunta **¿Revocar esta clave? Deja de funcionar de inmediato y permanece en esta lista.** Oculto cuando la clave ya está revocada. |
| **Eliminar** | Pregunta **¿Eliminar esta clave? Se borran la fila y el secreto. Las solicitudes anteriores se mantienen en el historial.** |

Cuando no hay claves, la página dice **Aún no hay claves**.

**Documentación de la API** abre una ventana. **Copiar** copia la URL base y después muestra **OK**. Cada acción tiene **Copiar URL** y **Copiar cURL**. Sustituya `YOUR_API_KEY` del ejemplo por el secreto de la lista de claves. La ventana también lista **Parámetro**, **Obligatorio** y **Descripción**. **Cerrar** sale de la ventana.

| Acción | Qué enviar | Qué hace |
|---|---|---|
| `list` | `action=list`. Opcional `id_product`, `resolved=1`, `page`, `id_shop`. | Devuelve entradas. Con `id_product`, solo las vinculadas directamente a ese producto. Con `resolved=1`, el conjunto que mostraría la página de producto. Sin producto, `page` recorre el catálogo, 50 entradas por página. |
| `get` | `action=get` e `id`. | Devuelve una entrada con cada traducción y cada asociación. |
| `create` | `action=create`, más una pregunta y al menos un vínculo. Opcional `id_product`, `id_lang`, `question`, `answer`, `translations`, `assoc`, `active`, `id_shop`. | Crea una entrada. `id_product` la une a ese producto. `translations` es un objeto JSON con el id de idioma como clave. Los shortcodes como `[product_name]` se guardan tal cual. `active` empieza encendido. Falta de pregunta o de vínculo se rechaza. |
| `update` | `action=update` e `id`, más solo los campos que quiere cambiar. | Actualiza solo los campos que envía. `replace_assoc=1` sustituye las asociaciones. Si no, `id_product` y `assoc` se añaden. Esta llamada no bloquea la entrada. |
| `activate` | `action=activate` e `id`. | Vuelve a mostrar la entrada sin cambiar el texto. |
| `deactivate` | `action=deactivate` e `id`. | Oculta la entrada. Se queda en el back office y desaparece de la página de producto. |
| `delete` | `action=delete` e `id`. | Borra la entrada, sus traducciones y sus vínculos. |

`assoc` es una lista JSON de objetos con `type` e `id`. El tipo es `product`, `category`, `feature_value`, `attribute`, `tag`, `manufacturer` o `supplier`. El `id_shop` opcional selecciona la tienda. Sin él se usa la tienda de la URL llamada. GET basta para una llamada corta. Envíe los mismos campos con POST cuando una pregunta o una respuesta sea HTML largo.

**Historial de solicitudes** es una lista de solo lectura titulada **Historial de solicitudes**. La nota dice que cada fila es una llamada. Busque en las cajas bajo los títulos de columna. **Ver** abre los parámetros y la respuesta. El secreto de la llamada guardada está enmascarado. Las filas se quedan como se registraron. No puede añadir, editar ni borrar una fila. Si se intenta una escritura, la página muestra **El historial de solicitudes es un registro de llamadas. Abre Ver para leer una fila.**

Columnas: **ID**, **Fecha**, **Acción**, **HTTP**, **ID de clave**, **Clave**, **Detalles**, **IP**. **Claves API** en la barra abre el catálogo de claves. **Volver al módulo** vuelve a **API**. Abrir el historial desde el módulo usa un enlace de reinicio, así que un filtro anterior se limpia. **Historial** en una clave conserva el filtro de esa clave.

El catálogo de claves se titula **Claves API**. La nota dice que el secreto se muestra para que pueda copiarlo en el otro sistema. **Revocar** detiene esa clave y deja la fila. **Eliminar** borra la fila y el secreto. Las solicitudes anteriores se quedan en **Historial de solicitudes**. **Generar una clave** vuelve a la pestaña **API**. Esta lista no tiene botón **Nuevo**. Columnas: **ID**, **Etiqueta**, **Clave**, **Estado**, **Creada**, **Último uso**. **Estado** dice **Activa** o **Revocada**. **Último uso** dice **Aún no utilizada** hasta la primera llamada aceptada. Las acciones de fila son **Revocar**, **Historial** y **Eliminar**. **Revocar** se oculta en una clave revocada y pregunta **¿Revocar esta clave? Deja de funcionar de inmediato y permanece en esta lista.** **Eliminar** pregunta **¿Eliminar esta clave? Se borran la fila y el secreto. Las solicitudes anteriores se mantienen en el historial.** Las acciones agrupadas son **Revocar seleccionadas** y **Eliminar seleccionadas**, con el mismo efecto en cada fila marcada. Si el empleado no puede editar, la página muestra **No tienes permiso para editar esto.**

### 3.7 Actualizaciones

**Actualizaciones** consulta MyPresta.eu por una versión más reciente. La comprobación solo informa de una versión. Instalar el paquete sigue siendo una descarga manual desde la página del módulo. El título del formulario es **Actualizaciones de MyPresta**.

| Campo | Al inicio | Qué hace |
|---|---|---|
| **Buscar actualizaciones** | un botón **Comprobar ahora** | Comprueba a mano si hay una versión nueva de este módulo en los servidores de MyPresta.eu. **¡Nueva versión disponible!** significa que hay una versión más reciente. **¡El módulo está actualizado!** significa que esta instalación coincide con la publicada. El botón no sube un zip. |
| **Notificaciones de actualizaciones** | Activar | **Activar** repite esa comprobación aproximadamente cada tres días mientras trabaja en el back office. **Desactivar** la omite. **Activar** y **Desactivar** son las dos opciones. |
| **Página del módulo** | un enlace llamado **MyFAQ** | Enlace directo a la página oficial del complemento, donde puede leer los cambios del módulo. |

Pulse **Guardar**. La página muestra **Ajustes de actualización guardados.**

Cuando se conoce una versión más reciente, el back office puede mostrar **Hay una versión nueva disponible, consulta http://MyPresta.eu para más información** y un enlace **Más detalles en el registro de cambios**. Suba el zip nuevo desde el **Gestor de módulos**.

### 3.8 Un producto

Abra **Catálogo**, **Productos**, el producto y después el bloque **MyFAQ**. El encabezado es **FAQ en este producto**. El texto de debajo dice: elija dónde muestra este producto sus preguntas, revise lo que hereda del catálogo y escriba entradas que pertenezcan solo aquí. Si ninguna entrada está activa, o la ubicación es **Ocultar**, la tienda no muestra ningún bloque de MyFAQ en este producto.

Las pestañas son **Entradas de FAQ**, **Pregunta y respuesta** y **Generar con IA**.

**Entradas de FAQ** empieza por **Ubicación**.

| Campo | Al inicio | Qué hace |
|---|---|---|
| **Ubicación** | Usar el valor predeterminado de la tienda | **Usar el valor predeterminado de la tienda** sigue **Visualización**. **Pie del producto** o **Pestaña del producto** fuerza ese lugar solo para este producto. **Ocultar** quita MyFAQ de este producto, incluido el bloque de esquema. Los demás módulos del hook no se mueven. Su orden se mantiene en **Diseño**, **Posiciones**. |

**Guardar** muestra **Guardado.**

**FAQ en este producto** tiene dos listas. La primera es de solo lectura y procede de una categoría, característica, atributo, etiqueta, marca o proveedor. La segunda se guarda para este producto. Arrastre una fila para cambiar el orden, use el interruptor para mostrar u ocultar una pregunta y elimine para quitarla.

**Del catálogo** lista entradas que se muestran porque otro producto con el mismo vínculo también las mostraría. Cambie el texto en el catálogo del módulo. Las columnas son **Pregunta**, **Estado** y **Acciones**. **Estado** es **Activa** o **Inactiva**. **Editar en el catálogo** abre esa entrada. Una entrada de IA puede mostrar **IA** y **bloqueada**. Una entrada escrita muestra **Escrita a mano**. Cuando nada coincide, la tarjeta dice **No se hereda nada**.

**Solo este producto** lista preguntas vinculadas a este producto. Arrastre el controlador (**Arrastrar para reordenar**) para fijar su orden en la página del producto. El interruptor muestra **Activa** o **Inactiva**. **Editar** abre **Pregunta y respuesta**. **Eliminar** pregunta **¿Eliminar esta entrada?** Cuando la lista está vacía, la tarjeta dice **Aún no hay FAQ para este producto** y ofrece **Añadir una entrada**. **No hay pregunta en este idioma** significa que el idioma actual del back office no tiene texto de pregunta; otro idioma puede tenerlo.

**Pregunta y respuesta** es **Añadir una entrada** o **Editar entrada**. La nota dice que se guarda solo para este producto. Los vínculos de categoría, característica y otros siguen en la pantalla **Entradas**. La pregunta es texto simple en la tienda. La respuesta conserva el formato del editor. Los shortcodes están bajo la respuesta. El botón de idioma de la derecha cambia la pregunta y la respuesta juntas.

| Campo | Al inicio | Qué hace |
|---|---|---|
| **Pregunta** | vacía | El mismo papel que en el catálogo. La ayuda dice que el idioma predeterminado es obligatorio. Si todos los idiomas están vacíos, el bloque muestra **Escribe una pregunta en al menos un idioma.** |
| **Respuesta** | vacía | El mismo papel que en el catálogo. Un idioma vacío no se muestra en ese idioma. |
| **Shortcodes** | los botones de token | Los mismos tokens que en el catálogo. Pulse uno para insertarlo en el cursor. |
| **Activa** | Sí | **Sí** muestra la entrada. **No** la oculta de la tienda. |

**Guardar** vincula la entrada solo a este producto. Editar una fila existente la bloquea, así que un reemplazo posterior la conserva. Una fila nueva no queda bloqueada. **Nueva entrada** limpia el formulario. **Eliminar entrada** la quita después de **¿Eliminar esta entrada?** Si abre una entrada que también está vinculada a otra cosa, el bloque muestra **Esta entrada no es exclusiva del producto.** y no guarda encima. Cámbiela desde **Editar en el catálogo**.

Si el guardado no llega a la tienda, el bloque muestra en inglés `The save could not reach the shop. Reload the product and try again.`

**Generar con IA** escribe preguntas para este producto a partir de sus datos de catálogo, en todos los idiomas de la tienda. La ejecución continúa en segundo plano. Tras iniciarla aparece aquí una barra de progreso.

| Campo | Al inicio | Qué hace |
|---|---|---|
| **Preguntas** | 5, el número de **IA** | Cuántos pares escribir para este producto, en todos los idiomas de la tienda. Sustituye el predeterminado de la pestaña **IA** solo para esta ejecución. |
| **Entradas de IA existentes del producto** | Añadir | **Añadir** mantiene las entradas de IA actuales y añade nuevas. **Reemplazar entradas de IA no bloqueadas vinculadas solo al producto** elimina las entradas de IA no bloqueadas vinculadas solo a este producto y después escribe las nuevas. Las entradas que editó a mano están bloqueadas y se conservan. |
| **Enviar al modelo** | las mismas tarjetas que en **Generación masiva** | Las mismas tarjetas. Una tarjeta apagada no se envía. Esta ejecución guarda las tarjetas para la próxima vez. |

**Generar** inicia la ejecución. Aparecen los mismos cuatro mensajes que en **Generación masiva** cuando faltan el proveedor, el modelo, la dirección compatible o la clave. La barra usa las mismas frases en inglés: `Starting…`, después los recuentos, después `Finished.` Deje abierta esta página de producto hasta que termine la barra, o termine la cola con la dirección de **Generación masiva**.

## 4. Tienda

El cliente ve el bloque solo en una página de producto.

Cuando **Ubicación** es **Pie del producto**, el acordeón está bajo el producto. El encabezado es **Encabezado sobre la lista** en el idioma del cliente. Cada pregunta es un botón. La respuesta se abre debajo. **Abrir la primera pregunta** en **Sí** abre la primera respuesta al cargar. Sin JavaScript todas las respuestas están visibles.

Cuando **Ubicación** es **Pestaña del producto**, el tema añade una pestaña de producto. La etiqueta de la pestaña es **Título de la pestaña** de ese idioma, o FAQ cuando ese idioma está vacío. El contenido de la pestaña es el mismo acordeón y el mismo encabezado.

Las entradas vinculadas directamente al producto van primero. Después, el orden es la posición del catálogo y de **Arrastrar para reordenar** en el producto. Una pregunta o una respuesta vacía en el idioma del cliente se omite. Después de sustituir los tokens, una pregunta que queda vacía, o una respuesta que no deja texto, también se omite. Las entradas inactivas se omiten. **Ocultar** en ese producto no imprime nada, incluido el bloque de esquema.

**Marcado de esquema FAQ** en **Sí** es el schema FAQ que PrestaShop escribe en el código de la página: un bloque FAQPage, construido con las preguntas que el cliente puede abrir, en el idioma de la página, y apuntando a la URL del producto. El cliente no ve una caja de esquema aparte. **No**, una lista vacía u **Ocultar** no imprimen ese bloque.

El cliente no puede añadir, editar ni enviar una pregunta. No hay una página de cuenta para estas entradas.

Si el tema no imprime el pie del producto y no imprime pestañas extra de producto, el cliente no ve nada aunque existan entradas. Mueva **MyFAQ** en **Diseño**, **Posiciones**, en `displayFooterProduct` o `displayProductExtraContent`. Los demás módulos de ese hook se quedan en el orden que fije ahí.

Un tema puede tener dos posiciones de pie. El acordeón se imprime una vez.

## 5. Problemas

**La página de producto no tiene acordeón.** El producto no tiene una entrada activa en el idioma del cliente, la pregunta o la respuesta queda vacía después de sustituir los tokens, o **Ubicación** de ese producto es **Ocultar**. Abra el producto, ponga **Ubicación** en **Usar el valor predeterminado de la tienda**, **Pie del producto** o **Pestaña del producto**, y confirme una entrada **Activa**. Si el tema no tiene pie ni pestañas extra, mueva el módulo en **Diseño**, **Posiciones**.

**Una entrada vinculada a una categoría padre no se muestra.** **Incluir categorías padre** está en **No**, o el vínculo es Inicio. Ponga **Incluir categorías padre** en **Sí**. Un vínculo a Inicio no cubre el catálogo. Marque el padre que realmente quiere, bajo Inicio.

**La tienda muestra la entrada en un idioma y no en otro.** Ese idioma tiene la pregunta o la respuesta vacía. Edite la entrada y rellene las dos. La página omite un idioma vacío.

**Guardar muestra "Escribe una pregunta en al menos un idioma."** Escriba una pregunta en al menos un idioma y pulse **Guardar** otra vez.

**Guardar muestra "Vincula la entrada al menos a un producto, categoría, característica, atributo, etiqueta, marca o proveedor."** Elija al menos un resultado en **Productos**, **Categorías**, **Valores de característica**, **Valores de atributo**, **Etiquetas**, **Marcas** o **Proveedores**.

**El bloque del producto muestra "Esta entrada no es exclusiva del producto."** Esa pregunta también está vinculada a una categoría u otro destino. Pulse **Editar en el catálogo** y cámbiela allí.

**El bloque del producto muestra "The save could not reach the shop. Reload the product and try again."** Recargue el producto y guarde otra vez. Esa frase se queda en inglés.

**Generar no hace nada y muestra un mensaje sobre la pestaña IA.** Abra **IA**, elija la ficha, guarde un modelo y guarde una clave para un proveedor oficial. En la ficha compatible, rellene **URL base compatible**, por ejemplo `http://localhost:11434/v1` para Ollama. Después inicie la ejecución otra vez.

**Iniciar generación muestra "Ningún producto coincide con esta selección."** Quite un filtro o marque una categoría que contenga productos activos. Los filtros vacíos se ignoran, así que un filtro que sí definió es lo que quitó los productos.

**La barra se detiene antes del 100 %.** Deje la pestaña abierta, o copie **Terminar una cola que ya existe** y ábrala con una programación. Cerrar la pestaña no borra la cola. Una línea con `failed` y un mensaje del proveedor significa que ese idioma fue rechazado. Lea el mensaje, corrija la clave o el ID del modelo y vuelva a ejecutar. **Añadir** añade otro conjunto. **Reemplazar entradas de IA no bloqueadas vinculadas solo al producto** quita primero el conjunto de IA no bloqueado.

**La línea de progreso muestra `curl_missing`.** El servidor no tiene cURL. Pida al alojamiento que lo active. La generación no corre sin él.

**Aparece un aviso de versión nueva.** El texto es **Hay una versión nueva disponible, consulta http://MyPresta.eu para más información**. Abra **Actualizaciones** y pulse **Comprobar ahora**. Descargue el zip de la página del módulo y súbalo en el **Gestor de módulos**. **Desactivar** en **Notificaciones de actualizaciones** detiene el aviso automático.

**MyFAQ no está en el menú izquierdo.** Es lo esperado. Abra **Módulos**, **Gestor de módulos**, **MyFAQ**, **Configurar**. El catálogo, las claves y el historial se abren desde esa página. Si **Configurar** no puede abrir el catálogo, abra **Configurar** una vez mientras está conectado como un empleado que puede instalar módulos. Esa visita crea las páginas ocultas y da acceso al perfil actual.

**Una clave es rechazada.** La clave fue revocada, borrada o copiada sin el secreto completo. Abra **Claves API**, copie la **Clave** completa de una fila **Activa**, o pulse **Generar una clave**.

**No puede borrar una fila del historial de solicitudes.** La página muestra **El historial de solicitudes es un registro de llamadas. Abre Ver para leer una fila.** Use **Ver**.

**No tienes permiso para editar esto.** El perfil del empleado no puede editar la lista de claves. Abra **Configurar** como administrador, o dé al perfil acceso a las páginas del módulo.

**La primera respuesta está cerrada aunque Abrir la primera pregunta esté en Sí.** El cliente tiene JavaScript apagado. En ese caso todas las respuestas están visibles. Con JavaScript encendido, solo el primer elemento empieza abierto.

**La misma pregunta aparece dos veces.** Está vinculada dos veces solo si guardó dos entradas. Una entrada se muestra una vez. Revise **Solo este producto** y **Del catálogo** por si hay dos filas distintas con el mismo texto.

**Reemplazar dejó una pregunta de IA antigua.** Esa entrada está bloqueada, o también está vinculada a una categoría u otro destino. Bloqueada es la marca de la fila. Edítela y bórrela si quiere que desaparezca.

## 6. Para el desarrollador

### 6.1 Resumen

Clase principal `myfaq` en `myfaq.php`. Versión `1.3.1`. Etiqueta de la lista **MyFAQ**. Autor `mypresta.eu`. Pestaña `front_office_features`. `ps_versions_compliancy` es `1.7.0.0` a `9.99.99`. `need_instance` es 0. `bootstrap` es true. `config.xml` sigue diciendo versión `1.0.0`; la versión de la clase es la que ejecuta la tienda.

`getContent()` pinta `MyfaqAdminBo`. Los ajustes de visualización son claves de `Configuration`. Las entradas, los vínculos, la ubicación por producto, las claves API, el registro de solicitudes y la cola de IA son tablas. La tienda lee las coincidencias con `MyfaqMatcher`, sustituye tokens con `MyfaqShortcode` y, si corresponde, imprime `MyfaqSchema`. Las llamadas de IA salen por `MyfaqAi` y `MyfaqQueue`. La dirección pública es el controlador front `api`.

No hay `enable()` ni `disable()`.

### 6.2 Archivos

- `myfaq.php` — instalación, desinstalación, hooks, valores iniciales, entradas ajax.
- `config.xml` — metadatos del paquete. La versión ahí es `1.0.0`.
- `lib/MyfaqAdminBo.php` — formularios del back office, textos `desc`, panel de producto.
- `lib/MyfaqConfig.php` — proveedores, modelos, flags, cifrado, token de cron.
- `lib/MyfaqRepository.php` — tablas y CRUD.
- `lib/MyfaqMatcher.php` — qué entradas muestra un producto.
- `lib/MyfaqShortcode.php` — catálogo de tokens y sustitución.
- `lib/MyfaqSchema.php` — publica el JSON-LD FAQ en la página de producto.
- `lib/MyfaqAi.php` — llamadas HTTP a los proveedores. Exige cURL.
- `lib/MyfaqQueue.php` — lote y cola.
- `lib/MyfaqApi.php` — API pública.
- `lib/MyfaqApiDocumentation.php` — texto de la ventana.
- `lib/updatesChecker.php` — clase `myfaqUpdate`.
- `lib/prestashop9compatibility.php` — plantillas de ayuda, precio, listas de id.
- `lib/searchTool/searchTool.php` — autocompletado de los campos de asociación.
- `controllers/admin/AdminMyfaqController.php` — solo ajax: búsqueda, panel de producto, inicio masivo, paso masivo, reorden.
- `controllers/admin/AdminMyfaqEntriesController.php` — catálogo.
- `controllers/admin/AdminMyfaqKeysController.php` — claves.
- `controllers/admin/AdminMyfaqLogsController.php` — historial.
- `controllers/front/api.php` — API JSON pública.
- `controllers/front/cron.php` — trabajador de la cola.
- `views/templates/admin/tabs.tpl` — barra de secciones.
- `views/templates/admin/entries.tpl` — vista de las diez últimas.
- `views/templates/admin/product.tpl` — bloque de edición de producto.
- `views/templates/admin/api.tpl` — vista previa de claves.
- `views/templates/admin/_shortcodes.tpl` — botones de token.
- `views/templates/admin/_api_documentation_modal.tpl` — ventana de acciones.
- `views/templates/admin/_api_log_modal.tpl` — una llamada guardada.
- `views/templates/hook/product.tpl` — acordeón de la tienda.
- `views/css/myfaq.css`, `views/js/myfaq.js` — tienda.
- `views/css/myfaq-admin.css`, `views/css/myfaq-controls.css`, `views/js/admin.js` — back office. Varias frases de progreso en `admin.js` están fijas en inglés.
- `upgrade/upgrade-1.0.0.php` — llama a `installDb()`.
- `key.php` — opcional. Si está, la comprobación de actualización envía su valor de licencia. Si falta, la comprobación envía `nlc`.

### 6.3 Controladores

`AdminMyfaq`, `AdminMyfaqEntries`, `AdminMyfaqKeys` y `AdminMyfaqLogs` son pestañas con `id_parent` `-1`. No aparecen en el menú. `ensureSearchTab()` crea una pestaña que falta. `grantHiddenTabAccess()` concede ver, añadir, editar y borrar al perfil superadministrador y al perfil del empleado actual.

`AdminMyfaq` solo sirve ajax: `SearchTool`, `ProductPanel`, `BulkStart`, `BulkStep`, `Reorder`. Las mismas acciones existen en el objeto del módulo porque el panel de producto y la página masiva publican ahí.

`AdminMyfaqEntries` es el catálogo. **Nueva entrada** de la barra es `addmyfaq_item`. Guardar envía `submitMyfaqItem` y redirige con `conf=4`. La posición usa los enlaces de posición del helper.

`AdminMyfaqKeys` no tiene formulario de alta. **Generar una clave** vuelve a `configure=myfaq&mfq_tab=api`. `processRevoke` y la revocación agrupada llaman a `MyfaqRepository::revokeApiKey`. Borrar llama a `deleteApiKey`.

`AdminMyfaqLogs` rechaza alta, actualización y borrado con **El historial de solicitudes es un registro de llamadas. Abre Ver para leer una fila.** `action=View` devuelve la solicitud y la respuesta guardadas como JSON para la ventana. `id_api_key` en la consulta rellena el filtro de clave salvo que la lista se reinicie.

El controlador front `api` (`module/myfaq/api`) llama a `MyfaqApi::handle()` y devuelve JSON. Pone el estado HTTP a partir del resultado. El controlador front `cron` (`module/myfaq/cron`) exige `token` igual a `MYFAQ_CRON_TOKEN`. Un token malo devuelve `403` y `{"error":"forbidden"}`. `fill_missing=1` llama a `MyfaqQueue::enqueueMissing` para la tienda actual, y después la acción vacía las filas pendientes durante unos 20 segundos, como máximo 30 filas. El JSON es `ok`, `enqueued_batch`, `processed`, `finished`.

Resultados de la API: clave ausente o revocada `401` `unauthorized`. `action` desconocida `400` `unknown_action`. Id ausente o desconocido `400` `missing_id` o `not_found`. Crear sin pregunta `422` `question_required`. Crear sin vínculo `422` `association_required`. Crear con éxito `201`. Actualizar, activar, desactivar y borrar con éxito `200`. Una escritura fallida `500`.

`list` con `id_product` y `resolved=1` usa `MyfaqMatcher::forProductAllLangs`. `list` con `id_product` y sin `resolved` devuelve las entradas vinculadas directamente a ese producto. `list` sin producto pagina `MyfaqRepository::listItems` a 50 por página. La actualización usa `lock_on_update` false, así que una actualización por API no bloquea la fila.

### 6.4 Hooks

Registrados en `install()`:

| Hook | Función |
|---|---|
| `displayHeader` | En un controlador de producto, añade `views/css/myfaq.css` y `views/js/myfaq.js`. |
| `displayFooterProduct` | Pinta el acordeón cuando la ubicación resuelta es `footer`. |
| `displayProductFooter` | El mismo pintado. Una bandera estática imprime el bloque de pie solo una vez por petición. |
| `displayProductExtraContent` | Cuando la ubicación es `tab`, devuelve un `ProductExtraContent`. El título es `MYFAQ_TAB_TITLE` del idioma actual, o la cadena fuente FAQ cuando ese valor está vacío. |
| `displayAdminProductsExtra` | Bloque de edición de producto más CSS y JS. |
| `actionAdminControllerSetMedia` | CSS y JS de administración en la página de producto, en `configure=myfaq` y en los controladores de entradas, claves e historial. |

El módulo no registra hooks propios y no llama a `Hook::exec` para un hook personalizado. `displayProductExtraContent` devuelve un array vacío cuando la ubicación no es `tab`, cuando el HTML está vacío o cuando `ProductExtraContent` no existe.

### 6.5 Sobrescrituras

El módulo no sobrescribe ninguna clase ni ningún controlador de PrestaShop.

### 6.6 Base de datos

`MyfaqRepository::installDb()` crea las tablas con `_MYSQL_ENGINE_` y `utf8mb4`, y si eso falla reintenta con `utf8`. `uninstall()` las borra en este orden: `myfaq_queue`, `myfaq_batch`, `myfaq_api_log`, `myfaq_api_key`, `myfaq_product_display`, `myfaq_assoc`, `myfaq_item_lang`, `myfaq_item`. La desinstalación sí borra las tablas. Reinstalar no restaura las filas.

| Tabla | Contenido |
|---|---|
| `myfaq_item` | `id_item`, `id_shop` (`0` significa todas las tiendas), `active`, `position`, `source` (`manual` o `ai`), `locked`, `date_add`, `date_upd`. |
| `myfaq_item_lang` | `id_item`, `id_lang`, `question`, `answer`. |
| `myfaq_assoc` | `id_assoc`, `id_item`, `type`, `id_target`. Único en entrada, tipo y destino. Tipos: `product`, `category`, `feature_value`, `attribute`, `tag`, `manufacturer`, `supplier`. |
| `myfaq_product_display` | `id_product`, `id_shop`, `mode` (`inherit`, `footer`, `tab`, `hidden`). |
| `myfaq_api_key` | `id_api_key`, `api_key`, `label`, `active`, `date_add`, `last_used`. |
| `myfaq_api_log` | `id_log`, `id_api_key`, `label`, `action`, `http_code`, `ip`, `request`, `response`, `date_add`. La clave guardada está enmascarada. |
| `myfaq_batch` | `id_batch`, `id_shop`, `id_employee`, `status` (`pending`, `running`, `done`), `total`, `done`, `failed`, `options`, `date_add`, `date_upd`. |
| `myfaq_queue` | `id_queue`, `id_batch`, `id_shop`, `id_product`, `id_lang`, `status` (`pending`, `running`, `done`, `error`), `attempts`, `error`, `date_upd`. Una fila `running` de más de cinco minutos vuelve a `pending`. |

`ensureApiSchema()` corre al abrir la pestaña API, la lista de claves, el historial o una llamada pública a la API. Añade `last_used` cuando falta esa columna y crea `myfaq_api_log` cuando falta esa tabla.

El guardado del catálogo pone `lock_on_update`, así que una actualización pone `locked` a 1. `source` en una actualización se queda en el valor actual salvo que se ponga `force_source`. Una fila nueva del catálogo es `manual` y no está bloqueada. Una actualización desde la página de producto también bloquea. Una inserción desde la página de producto vincula solo ese producto y no bloquea. El reemplazo de IA borra filas con `source` `ai`, `locked` 0 y ninguna asociación distinta de ese producto.

`MyfaqMatcher::categoryIds()` añade padres solo cuando `MYFAQ_INCLUDE_PARENT_CAT` es 1. El recorrido se detiene cuando `id_parent` es menor o igual que 2, o después de 25 pasos.

### 6.7 Claves y traducciones

Las instala `installConfig()`. Las quita `deleteConfig()` al desinstalar.

| Clave | Cuando falta o al instalar |
|---|---|
| `MYFAQ_DISPLAY` | `footer` |
| `MYFAQ_TAB_TITLE` | `FAQ` por idioma |
| `MYFAQ_HEADING` | `FAQ` por idioma |
| `MYFAQ_INCLUDE_PARENT_CAT` | `0` |
| `MYFAQ_SCHEMA` | `1` |
| `MYFAQ_OPEN_FIRST` | `0` |
| `MYFAQ_AI_PROVIDER` | `openai` |
| `MYFAQ_AI_MODEL_OPENAI` | `gpt-4o-mini` |
| `MYFAQ_AI_MODEL_ANTHROPIC`, `MYFAQ_AI_MODEL_GEMINI`, `MYFAQ_AI_MODEL_DEEPSEEK`, `MYFAQ_AI_MODEL_MISTRAL`, `MYFAQ_AI_MODEL_COMPATIBLE` | vacías hasta que se guarda un modelo. `MyfaqConfig::model()` devuelve entonces el primer id integrado, o una cadena vacía para `compatible` |
| `MYFAQ_AI_KEY_` más el proveedor en mayúsculas | vacía. Se guarda con `MyfaqConfig::encrypt` (`enc:` y AES-256-CBC, clave `sha256` de `_COOKIE_KEY_`) |
| `MYFAQ_AI_BASE_URL` | vacía. `baseUrl('compatible')` usa entonces `http://localhost:11434/v1`. `aiBlockReason()` rechaza una ejecución mientras este valor está vacío, así que los botones del back office no llegan a ese respaldo |
| `MYFAQ_AI_TEMPERATURE` | `0.4`. La lectura recorta de 0 a 2 |
| `MYFAQ_AI_MAX_TOKENS` | `2000`. La lectura usa 2000 cuando el valor guardado es menor de 200, y corta en 8000 |
| `MYFAQ_AI_COUNT` | `5`. La lectura usa 5 cuando el valor guardado es menor de 1, y corta en 20 |
| `MYFAQ_AI_PROMPT` | vacía |
| `MYFAQ_AI_CONTEXT` | JSON de `MyfaqConfig::defaultFlags()`. Encendidos: `name`, `description_short`, `description`, `prices`, `categories`, `features`, `manufacturer`. Apagados: `combinations`, `tags`, `supplier`, `stock`, `dimensions`, `identifiers`, `attachments`, `existing` |
| `MYFAQ_CUSTOM_MODELS` | `{}` |
| `MYFAQ_CRON_TOKEN` | `bin2hex(random_bytes(16))`. `ensureCronToken()` crea uno cuando el valor está vacío |
| `MYFAQ_BO_TAB` | no se pone al instalar. La sección abierta se guarda en cada pintado. Los valores desconocidos vuelven a `display` |

`deleteConfig()` también borra cada `MYFAQ_AI_KEY_*` y `MYFAQ_AI_MODEL_*` de `openai`, `anthropic`, `gemini`, `deepseek`, `mistral`, `compatible`.

La desinstalación no borra `mypresta_updates`, `update_myfaq` ni `updatev_myfaq`. Pertenecen a la comprobación de actualizaciones. `mypresta_updates` queda activado cuando falta la clave. El intervalo de la comprobación automática es 259200 segundos.

Las descripciones de campo están en `MyfaqAdminBo` (`desc` y los textos `sectionBrief`) y en `MyfaqApiDocumentation`. Las cadenas del back office pasan por `$this->l()`. Añada un idioma con el archivo `translations/{iso}.php`. Cadenas que no pasan por `$this->l()`: las ayudas de shortcode en `MyfaqShortcode::catalogue()`, los nombres de las fichas de proveedor, los títulos de las tarjetas de datos en `MyfaqConfig::contextFlagDefs()` (se pasan a `$this->l()`, pero no hay traducción, así que se ven en inglés) y las frases de progreso fijas en `views/js/admin.js`. Las ayudas de las tarjetas sí están traducidas. Las etiquetas de condición de `conditionLabel()` son `New`, `Used` y `Refurbished`.

`MyfaqConfig::shopScope()` devuelve `0` cuando el contexto multitienda es todas las tiendas, y el id de la tienda actual en otro caso. Los guardados del catálogo usan ese valor. Los guardados de la página de producto usan solo el id de la tienda actual.

### 6.8 Ampliar

Sobrescriba `views/templates/hook/product.tpl` desde el tema en `themes/{theme}/modules/myfaq/views/templates/hook/product.tpl`. Las variables asignadas son `mfq_items` (`id`, `question`, `answer`), `mfq_heading`, `mfq_open_first` y `mfq_schema`. Sobrescriba `views/css/myfaq.css` y `views/js/myfaq.js` del mismo modo. El acordeón no se pinta cuando el emparejador no devuelve filas visibles, así que una sobrescritura del tema no tiene entonces qué imprimir. No edite las plantillas del módulo en su sitio si el tema puede llevar la sobrescritura.

## 7. Ayuda

Página del módulo: [https://mypresta.eu/contact.html](https://mypresta.eu/contact.html)

Para preguntar por este módulo, inicie sesión en la cuenta de cliente de [mypresta.eu](https://mypresta.eu), abra el contacto y elija el tema **Support for paid modules**. El formulario dice que para ese tema hace falta iniciar sesión. Después de iniciar sesión, elija este módulo en el historial de compras.
