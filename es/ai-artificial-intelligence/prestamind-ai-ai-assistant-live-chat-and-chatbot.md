---
title: "PrestaMind AI - documentación y manual de usuario"
sidebar:
  label: "PrestaMind AI - documentación y manual de usuario"
description: "Configuración y resolución de problemas para una tienda que ya tiene PrestaMind AI instalado."
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo PrestaMind AI - AI assistant, live chat and chatbot en MyPresta.eu](https://mypresta.eu/ai-artificial-intelligence/prestamind-ai-ai-assistant-live-chat-and-chatbot.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/ai-artificial-intelligence/prestamind-ai-ai-assistant-live-chat-and-chatbot/)
>
> ---


Los nombres de botones y pestañas de abajo son las etiquetas en inglés de la pantalla del módulo. Si el idioma del empleado es el español, PrestaShop muestra la traducción de esa misma etiqueta cuando el módulo la tiene.

## 1. Requisitos

PrestaShop 1.7.6, 8 y 9. PHP en la versión que exige esa instalación de PrestaShop. El módulo llama a la extensión cURL y a OpenSSL o libsodium para guardar las claves de los proveedores. No exige otro módulo.

Necesita una cuenta y una clave API del proveedor que elija, salvo que se quede en la demo sin conexión. Un servidor local compatible con OpenAI (Ollama, vLLM, LM Studio) necesita una dirección que el servidor de la tienda pueda abrir. El estado en vivo de DHL necesita una clave gratuita del sitio de desarrolladores de DHL. El estado en vivo de InPost no necesita clave.

Un catálogo grande alarga la primera indexación. Los embeddings envían el texto de cada producto una vez al proveedor de embeddings, así que la primera pasada gasta tokens y tiempo. La búsqueda por palabras no lo hace.

## 2. Instalación

1. Suba el módulo en **Module Manager** y pulse **Install**.
2. La pregunta **Delete this module and all its data (conversations, knowledge index, settings)?** sale al desinstalar, no al instalar.
3. Después de instalar, el elemento **PrestaMind AI** está en **Customer service**. Si ese menú no existe, el elemento queda en **Improve**. **Configure** en la fila del módulo abre la misma página.
4. La instalación no vacía la caché de la tienda. La burbuja sigue oculta hasta que la encienda.

La desinstalación quita el elemento de menú, las tablas del módulo y los ajustes guardados, incluidas las claves. Los pedidos, productos, páginas CMS y reglas de carrito ya guardados en PrestaShop se quedan. La carpeta del módulo sigue en el disco hasta que la borre. Una instalación nueva empieza con conversaciones vacías y un índice vacío. No recupera los anteriores.

## 3. Configuración y trabajo diario

### 3.1 El proceso completo

Usted empieza en el back office. El visitante empieza en la tienda.

1. Abra **PrestaMind AI**. En **Settings**, luego **Health**, corrija cada línea que no esté OK.
2. En **Model provider**, pulse el mosaico del proveedor, pegue la clave API, elija el modelo principal y el modelo rápido, escriba los precios y pulse **Save and test the connection**.
3. En **Knowledge** de la página de ajustes, elija qué se indexa. Luego abra la pestaña **Knowledge** y pulse **Reindex now**.
4. En **Playground**, envíe una pregunta de producto, una de entrega y una de pedido. Cada envío gasta tokens del proveedor real.
5. En **Settings**, luego **Widget**, deje **Show the assistant to all visitors** apagado. Ponga su IP pública en **Preview only for these IP addresses**, guarde y abra la tienda. Cuando las respuestas estén bien, encienda el widget para todos y vacíe la caché de página completa si no ve la burbuja.
6. El visitante abre la burbuja, escribe una pregunta y pulsa la flecha. El módulo lee el precio, el stock, el envío o el pedido de la tienda cuando la pregunta lo necesita, y muestra la respuesta en la misma ventana.
7. El descuento existe solo cuando una oferta que usted guardó encaja con el carrito. **Add to cart**, **Send the return request** y **Send the quote request** esperan el clic del visitante.
8. Si el visitante pulsa **Talk to a person**, la fila está en **Escalations** y, con la consola encendida, también en el botón **Live chats**. Pulse **Take over this conversation**, escriba la respuesta, pulse **Send** y luego **Give back to the assistant**. El estado **new**, **open** o **done** no envía un correo al visitante.

### 3.2 Dónde están las pantallas

Pestañas, en este orden: **Dashboard**, **Live stats**, **History**, **Conversations**, **Knowledge**, **Triggers & offers**, **Playground**, **Quality tests**, **Escalations**, **Settings**, **Updates**.

**Settings** tiene su propia fila: **Health**, **Widget**, **Model provider**, **Knowledge**, **Limits & cost**, **Privacy**, **Escalation**, **Cart reminders**, **Couriers**, **Tools**. Cada subpágina guarda solo sus campos. **Save** muestra **Settings saved.** Guardar no borra conversaciones ni el índice.

El panel de la tienda, después de entrar, muestra un bloque con las cifras del asistente, los clientes que esperan a una persona y las últimas conversaciones.

### 3.3 Dashboard

![Dashboard](https://mypresta.eu/docs/images/docs/prestamindai-dashboard.webp)

La pantalla está en inglés. En este manual esta página se llama Dashboard.

Solo lectura. Elija **today**, **7**, **30** o **90** días, o ponga **From** y **To**. Puede limitar las llamadas de IA por modelo, proveedor, tipo (respuestas o embeddings) o estado, y pulse **Filter**. **See full history** abre **History**.

La pantalla muestra ingresos de pedidos hechos en los 7 días posteriores a un chat, conversaciones, cuántas se resolvieron sin una persona, valoraciones, tokens enviados y recibidos y el coste estimado. El coste usa el precio guardado en cada llamada. No es una factura del proveedor. El grupo de control se pone en **Settings**, luego **Privacy**, si quiere comparar el valor de los pedidos.

### 3.4 Live stats

![Live stats](https://mypresta.eu/docs/images/docs/prestamindai-live.webp)

La pantalla está en inglés. En este manual esta página se llama Live stats.

Deje la página abierta. Las líneas nuevas salen arriba cada pocos segundos. Los chips ocultan clientes, al asistente, al equipo, las herramientas o las escalaciones. Busque en el texto o escriba un número de chat. **thumbs down only** deja las respuestas que los visitantes rechazaron. **Pause** congela la vista. **Compact** aprieta las filas. **Reset filters** muestra todo. **Clear** vacía la vista de esta página. **Open chat** abre la conversación. **Take over** le deja responder.

La página solo lee conversaciones guardadas. Los filtros se quedan en este navegador. Los números de tarjeta, IBAN y PESEL enmascarados siguen enmascarados.

### 3.5 History

![History](https://mypresta.eu/docs/images/docs/prestamindai-history.webp)

La pantalla está en inglés. En este manual esta página se llama History.

La lista completa de llamadas a modelos, la más nueva primero: fecha, tipo, proveedor, modelo, tokens enviados, tokens recibidos, el precio por 1M de tokens válido entonces, el coste estimado, el tiempo y el estado, con enlace a la conversación. Los mismos filtros que en **Dashboard**. Las tarjetas de arriba usan ese filtro.

La lista no guarda el texto del mensaje. Cambiar un precio después no cambia las filas viejas. El registro se queda cuando la retención borra las conversaciones.

### 3.6 Conversations

![Conversations](https://mypresta.eu/docs/images/docs/prestamindai-conversations.webp)

La pantalla está en inglés. En este manual esta página se llama Conversations.

Filtre por **Waiting for a reply**, **Handled by a person**, escalado o sentimiento negativo. El icono del ojo abre el hilo: mensajes, modelo, tiempo de respuesta, pulgares arriba y abajo y cada llamada de herramienta. La papelera borra esa conversación, sus mensajes y sus llamadas. El borrado es definitivo.

Pulse **Take over this conversation**. El asistente calla para ese visitante. Sus respuestas se ven como **Shop team**. **Send** publica la respuesta. **Give back to the assistant** devuelve el chat.

**Live chats** es un botón flotante abajo a la derecha en cada página del back office, si **Live chat console in the back office** está encendido y usted puede abrir **PrestaMind AI**. El contador muestra clientes en espera. Puede tener varias ventanas abiertas. Apagarlo oculta el botón. Esta página sigue funcionando.

### 3.7 Knowledge

![Knowledge](https://mypresta.eu/docs/images/docs/prestamindai-knowledge.webp)

La pantalla está en inglés. En este manual esta página se llama Knowledge.

Pulse **Reindex now** después de instalar, después de cambiar exclusiones y después de cambiar el proveedor o el modelo de embeddings. **Clear answer cache** borra respuestas guardadas a preguntas repetidas de política. La caché también se vacía al editar una FAQ o un producto. Un documento que aún espera no se usa. Una FAQ nueva vale desde la pregunta siguiente.

El precio y el stock no están en el índice. Se leen del producto en el momento de la pregunta.

**Add FAQ entry** / **Edit FAQ entry**: escriba la pregunta y la respuesta como debe decirlas el asistente, y guarde.

### 3.8 Triggers

![Triggers](https://mypresta.eu/docs/images/docs/prestamindai-triggers.webp)

La pantalla está en inglés. En este manual esta página se llama Triggers.

**Triggers & offers** tiene dos subpáginas. Cree primero la oferta y luego engánchela a un disparador. Un visitante ve como máximo un mensaje proactivo por visita. Ese disparador calla después durante el enfriamiento.

Columnas: **Name**, **When**, **Threshold**, **Page**, **Message**, **Discount**, **Active**. En la fila: editar y borrar. El cuadro de estado explica por qué puede no salir la burbuja. **Open the shop in test mode** ignora el consentimiento, el enfriamiento y el límite de un mensaje por visita.

| Campo | En un disparador nuevo | Qué hace |
|---|---|---|
| **Name** | vacío | Una etiqueta para usted. Vacío usa el texto del mensaje. El visitante no la ve. |
| **Type** | **Seconds on the page** | **Seconds on the page**, **Scrolled percent of the page**, **Exit intent (desktop)**, **Seconds idle on the cart page** o **Product viewed N times in a visit**. El mensaje sale junto al botón del chat. Un clic abre el chat. |
| **Threshold** | 30 | Segundos, porcentaje de scroll o número de vistas. Exit intent lo ignora. El tiempo y el carrito quieto usan al menos 5 segundos. |
| **Page type** | **Any page** | **Any page**, **Product page**, **Category page**, **Cart / checkout** o **Home page**. En otras páginas este disparador calla. |
| **Message shown to the visitor** | vacío, obligatorio | Una o dos frases por idioma de la tienda, hasta 300 caracteres. Un idioma vacío usa el idioma por defecto. Ese texto es también la primera línea cuando el visitante abre el chat desde la burbuja. |
| **Only for these categories** | ninguna | En una ficha el producto tiene que estar en una de ellas. En una categoría, la categoría tiene que coincidir. Vacío significa todas. |
| **Only for these products** | ninguno | Limita el disparador a esos productos. Vacío significa todos. |
| **Offer the assistant may grant after this trigger** | **None** | Elija una oferta guardada o **None**. Deciden las reglas. El modelo no inventa un porcentaje. |
| **How the discount is handed out** | **Give the code at once when the visitor clicks the message** | **Only if the visitor asks or hesitates over the price**, o al momento cuando el chat se abre desde el mensaje. En ambos casos el carrito tiene que encajar con la oferta. Si **apply_offer** está desmarcado en **Tools**, el código sale al momento. |
| **Cool-down (days)** | 7 | De 0 a 365. Después de la burbuja, ese visitante no vuelve a ver este disparador hasta que pase el plazo. |

**Add trigger** o **Save trigger** guarda la fila. **Allow proactive messages** tiene que estar encendido en **Privacy**, si no ningún disparador se activa.

### 3.9 Offers

![Offers](https://mypresta.eu/docs/images/docs/prestamindai-offers.webp)

La pantalla está en inglés. En este manual esta página se llama Offers.

Columnas: **Name**, **%**, **Min. cart**, **Valid (h)**, **Max / day**. En la fila, editar y borrar. Sin ofertas el asistente no da descuento. Una conversación recibe como máximo una oferta. El código es de un solo uso, entra en el carrito y no se suma a productos que ya tienen descuento. El visitante ve el nombre de regla **PrestaMind offer**.

| Campo | En una oferta nueva | Qué hace |
|---|---|---|
| **Name** | vacío | Su etiqueta en el formulario del disparador. |
| **Discount percent (1-50)** | 5 | Porcentaje sobre productos que no están ya en oferta. |
| **Minimum cart value (tax incl.)** | 0 | 0 significa cualquier carrito. Por debajo se rechaza la oferta. El importe es la moneda por defecto de la tienda. |
| **Valid for (hours)** | 24 | De 1 a 720. Luego el código caduca. |
| **Maximum codes per day** | 20 | 0 significa sin tope. Al llegar al tope, esta oferta para hasta el día siguiente. |
| **No offer when the cart contains products from** | ninguna | Si alguna línea está en estas categorías, se rechaza todo el carrito. |

**Add offer** o **Save offer** guarda la regla. Engánchela a un disparador antes de que el asistente pueda usarla. Los recordatorios de carrito también pueden llevar una oferta.

### 3.10 Playground

![Playground](https://mypresta.eu/docs/images/docs/prestamindai-playground.webp)

La pantalla está en inglés. En este manual esta página se llama Playground.

Usa el proveedor real. Gasta tokens y cuenta para el presupuesto diario. El hilo tiene el canal playground. No se envía nada a los visitantes.

| Campo | Al empezar | Qué hace |
|---|---|---|
| **Page the customer is on** | **Other** | **Other**, **Home**, **Product page**, **Category** o **Cart**. El asistente recibe esa página como contexto. |
| **Product id (optional)** | vacío | Solo con **Product page**. El id de **Catalog**, luego **Products**. El asistente ve el precio y el stock actuales. |
| **Customer message** | vacío | La pregunta. **Send** muestra la respuesta y la traza. **New conversation** empieza de nuevo. |

### 3.11 Quality tests

![Quality tests](https://mypresta.eu/docs/images/docs/prestamindai-quality-tests.webp)

La pantalla está en inglés. En este manual esta página se llama Quality tests.

Añada una pregunta, palabras que la respuesta debe contener y palabras que no debe contener. Pulse **Run all tests**. Cada pasada pregunta al modelo real y gasta tokens. La lista muestra aprobado o no, el motivo y la respuesta. Las conversaciones de prueba se borran después de la pasada.

### 3.12 Escalations

![Escalations](https://mypresta.eu/docs/images/docs/prestamindai-escalations.webp)

La pantalla está en inglés. En este manual esta página se llama Escalations.

Las filas son clientes que pidieron una persona, solicitudes de devolución y solicitudes de presupuesto, con un resumen y el contacto que dejaron. El destino se pone en **Settings**, luego **Escalation**. Ponga el estado en **new**, **open** o **done**. El estado no envía un correo al visitante. Responda al contacto de la fila o abra el enlace del chat.

### 3.13 Health

![Health](https://mypresta.eu/docs/images/docs/prestamindai-health.webp)

La pantalla está en inglés. En este manual esta página se llama Health.

Una lista de comprobación. **OK** significa listo. **!** significa que no. **Repair hooks** registra los hooks que faltan y muestra **All hooks are registered.** o **Could not register:** con los nombres. **Test streaming** comprueba que el servidor no almacena en búfer la respuesta en vivo. Mirar la página no cambia nada más. La línea del widget está OK solo cuando la burbuja es visible para usted.

### 3.14 Widget

![Widget](https://mypresta.eu/docs/images/docs/prestamindai-widget.webp)

La pantalla está en inglés. En este manual esta página se llama Widget.

| Campo | Después de instalar | Qué hace |
|---|---|---|
| **Show the assistant to all visitors** | No | Encendido: cada visitante ve la burbuja, salvo el grupo de control. Apagado: nadie, salvo las IP de vista previa. Vacíe la caché de página completa después del cambio. |
| **Preview only for these IP addresses** | vacío | IP públicas separadas por comas. La página muestra la IP que la tienda ve ahora. Detrás de un proxy puede ser distinta de la que usted conoce. |
| **Assistant name** | PrestaMind | Nombre en la cabecera del chat, por idioma, hasta 60 caracteres. Un idioma vacío usa el idioma por defecto. |
| **Greeting** | vacío | Primer mensaje de un chat vacío, hasta 300 caracteres por idioma. Vacío usa una frase integrada. |
| **AI disclosure line** | vacío | Línea bajo la cabecera, hasta 300 caracteres por idioma. Vacío usa una frase integrada que también dice que las respuestas pueden tener errores. |
| **Color** | #2563eb | Color principal del botón, la cabecera, los botones y las burbujas del visitante. |
| **Position** | **Bottom right** | **Bottom right** o **Bottom left**. |
| **Button shape** | **Circle** | **Circle**, **Rounded square** o **Square with sharp corners**. La ventana no cambia. |
| **Button size** | **Medium (56 px)** | **Small (48 px)**, **Medium (56 px)** o **Large (68 px)**. |
| **Window corners** | **Soft (default)** | **Sharp**, **Soft (default)** o **Very round**. |
| **Button icon** | burbuja integrada | **Choose icon** abre Font Awesome y Material Icons. **Use the built-in bubble** restaura la predeterminada. El icono se guarda en la tienda. Guarde el formulario. |
| **Button color** | vacío (usa **Color**) | Fondo del botón del chat. |
| **Icon color** | #ffffff | Color del icono del botón. |
| **Header color** | vacío (usa **Color**) | Fondo de la barra superior. |
| **Header text color** | #ffffff | Nombre y botones de la barra superior. |
| **Customer bubble color** | vacío (usa **Color**) | Mensajes del visitante, y también los botones y la flecha de envío. |
| **Customer bubble text color** | #ffffff | Texto de los mensajes del visitante y de los botones principales. |
| **Preview** | muestra | Cambia con los campos. Nada se guarda antes de **Save**. |
| **Tone** | **Friendly** | **Friendly**, **Formal**, **Casual** o **Expert**. Vale para mensajes nuevos. |
| **Your instructions to the assistant** | vacío | Hasta 1500 caracteres, añadidos a cada conversación. No anulan los precios actuales, la prohibición de un descuento inventado ni la prohibición de datos de otros clientes. Un texto largo gasta tokens en cada mensaje. |

### 3.15 Proveedor del modelo y cada modelo integrado

![Proveedor del modelo y cada modelo integrado](https://mypresta.eu/docs/images/docs/prestamindai-provider.webp)

La pantalla está en inglés. En este manual esta página se llama Proveedor del modelo y cada modelo integrado.

Pulse un mosaico. Solo se llama al proveedor activo, más el de reserva si lo puso y el activo falla antes de enviar la primera palabra. Los modelos y los precios se conservan en cada proveedor.

Después de instalar, el activo es **Demo (offline)**. Sin clave y sin coste. Respuestas preparadas, solo para probar la instalación. No es un asistente de tienda.

| Campo | Después de instalar | Qué hace |
|---|---|---|
| **Fallback provider** | **None** | Segundo proveedor si el activo agota el tiempo, llega al límite o devuelve un error de servidor. Elija uno cuya clave esté guardada. Ese segundo proveedor factura su uso. La demo no puede ser reserva. |
| **API key** | vacío | Pegue la clave y guarde. Un campo vacío conserva la clave guardada. La clave se guarda cifrada y no se vuelve a mostrar, solo los primeros y últimos caracteres. **Remove the stored key** en Yes, y guardar, la borra. El servidor compatible puede quedar sin clave. |
| **Base URL** | http://localhost:11434/v1 | Solo para **OpenAI-compatible / Ollama**. La URL tiene que terminar en /v1. Las peticiones van allí, no a la nube. |
| **Main model** | tabla de ese proveedor | Consejo de producto, preguntas de pedido y cualquier respuesta que necesite herramientas. |
| **Fast model** | tabla de ese proveedor | Preguntas de política y charla. Póngalo igual que el principal si quiere un solo modelo. |
| **Your own model id** | vacío | Letras, dígitos y . _ - : / @, hasta 100 caracteres. **Add model** guarda al momento con el resto de la página. **Model added. Choose it as the main or fast model and enter its price.** Si ya está: **That model is already on the list.** Id mala: **Enter a model id: letters, digits and . _ - : / @ only.** |
| Columnas de precio | precio de lista | **USD / 1M input tokens** y **USD / 1M output tokens**. El punto es el separador decimal. **set price** significa que no hay precio por defecto conocido. Un modelo sin precio cuenta como gratis, así que el presupuesto diario en dólares no le protege. |
| **Reset prices to defaults** | - | Devuelve los precios integrados. **Prices set back to the built-in defaults.** Los precios que escribió se pierden. |
| **Remove** | - | Solo en un modelo de chat propio. **Model removed.** Un modelo integrado muestra un candado y **Built-in models cannot be removed.** |

**Save and test the connection** guarda y llama al proveedor activo con el modelo principal. **No API key stored for the selected provider.** significa que aún falta la clave.

Los precios de abajo son USD por 1 millón de tokens, primero entrada y luego salida. Son los precios de lista guardados en el módulo el 2026-10-31. El proveedor puede cambiarlos. Corrija las dos columnas si su factura difiere. DeepSeek tiene precio punta y fuera de punta. El módulo guarda el precio punta para que la estimación no quede baja.

**OpenAI.** Transmisión, herramientas y embeddings. Modelo principal por defecto **gpt-6.1-sol**. Modelo rápido por defecto **gpt-6-luna**.

| Modelo | Tipo | Entrada / salida USD por 1M | Después de instalar |
|---|---|---|---|
| gpt-6.1-sol | chat | 2 / 10 | modelo principal |
| gpt-6.1-terra | chat | 1 / 5 | no |
| gpt-6-luna | chat | 0.10 / 0.50 | modelo rápido |
| gpt-5.5 | chat | 5 / 30 | no |
| gpt-5-mini | chat | 0.25 / 2 | no |
| gpt-4.1 | chat | 2 / 8 | no |
| gpt-4.1-mini | chat | 0.40 / 1.60 | no |
| gpt-4o-mini | chat | 0.15 / 0.60 | no |
| text-embedding-3-small | embeddings | 0.02 / 0 | modelo de embeddings por defecto |
| text-embedding-3-large | embeddings | 0.13 / 0 | no |

**Anthropic Claude.** Transmisión y herramientas. Sin embeddings. Modelo principal por defecto **claude-sonnet-5-5**. Modelo rápido por defecto **claude-haiku-5-5**.

| Modelo | Tipo | Entrada / salida USD por 1M | Después de instalar |
|---|---|---|---|
| claude-fable-5-1 | chat | 10 / 50 | no |
| claude-opus-5-5 | chat | 4 / 20 | no |
| claude-opus-5 | chat | 5 / 25 | no |
| claude-sonnet-5-5 | chat | 2 / 10 | modelo principal |
| claude-sonnet-4-6 | chat | 3 / 15 | no |
| claude-haiku-5-5 | chat | 0.10 / 0.50 | modelo rápido |
| claude-haiku-4-5 | chat | 1 / 5 | no |

**Google Gemini.** Transmisión, herramientas y embeddings. Modelo principal por defecto **gemini-2.5-flash**. Modelo rápido por defecto **gemini-2.5-flash-lite**.

| Modelo | Tipo | Entrada / salida USD por 1M | Después de instalar |
|---|---|---|---|
| gemini-2.5-pro | chat | 1.25 / 10 | no |
| gemini-2.5-flash | chat | 0.30 / 2.50 | modelo principal |
| gemini-2.5-flash-lite | chat | 0.10 / 0.40 | modelo rápido |
| gemini-embedding-001 | embeddings | 0.15 / 0 | modelo de embeddings por defecto |

**DeepSeek.** API compatible con OpenAI. Sin embeddings. El modelo principal y el rápido por defecto son **deepseek-flash**.

| Modelo | Tipo | Entrada / salida USD por 1M | Después de instalar |
|---|---|---|---|
| deepseek-flash | chat | 0.30 / 1.20 | modelo principal y rápido |
| deepseek-v4-pro | chat | 1.32 / 3.96 | no |

**Mistral AI.** Transmisión, herramientas y embeddings. Modelo principal por defecto **mistral-large-latest**. Modelo rápido por defecto **mistral-small-latest**. Un precio vacío significa que el módulo no tiene precio de lista: la fila lleva **set price** hasta que usted lo escriba.

| Modelo | Tipo | Entrada / salida USD por 1M | Después de instalar |
|---|---|---|---|
| mistral-large-latest | chat | 0.50 / 1.50 | modelo principal |
| mistral-medium-latest | chat | sin precio integrado | no |
| mistral-small-latest | chat | sin precio integrado | modelo rápido |
| open-mistral-nemo | chat | sin precio integrado | no |
| mistral-embed | embeddings | sin precio integrado | modelo de embeddings por defecto |

**OpenAI-compatible / Ollama.** Su servidor. Los precios integrados son 0 / 0, también en modelos locales. El modelo principal y el rápido por defecto son **llama3.1**. El modelo de embeddings por defecto es **nomic-embed-text**.

| Modelo | Tipo | Entrada / salida USD por 1M | Después de instalar |
|---|---|---|---|
| llama3.1 | chat | 0 / 0 | modelo principal y rápido |
| llama3.2 | chat | 0 / 0 | no |
| mistral | chat | 0 / 0 | no |
| qwen2.5 | chat | 0 / 0 | no |
| nomic-embed-text | embeddings | 0 / 0 | modelo de embeddings por defecto |
| mxbai-embed-large | embeddings | 0 / 0 | no |
| bge-m3 | embeddings | 0 / 0 | no |
| snowflake-arctic-embed | embeddings | 0 / 0 | no |

**Demo (offline).** Sin clave. Precios 0 / 0.

| Modelo | Tipo | Entrada / salida USD por 1M | Después de instalar |
|---|---|---|---|
| mock | chat | 0 / 0 | modelo principal y rápido, y este proveedor es el activo |
| mock-64 | embeddings | 0 / 0 | cuando el proveedor de embeddings es la demo |

Algunos modelos nuevos de OpenAI ignoran **Temperature**. Un id que el proveedor no conoce sale como error de proveedor en **Dashboard**.

### 3.16 Ajustes de Knowledge

![Ajustes de Knowledge](https://mypresta.eu/docs/images/docs/prestamindai-knowledge-settings.webp)

La pantalla está en inglés. En este manual esta página se llama Ajustes de Knowledge.

La dirección cron está en esta página. Llámela cada 10 o 15 minutos. Cada llamada indexa páginas nuevas y cambiadas, construye embeddings, envía recordatorios de carrito si los encendió, borra conversaciones más viejas que la retención y limpia la caché de respuestas y las filas de límite de más de dos días. Sin cron, el índice se actualiza igual cuando los visitantes escriben o cuando corren los hooks de producto y CMS. La retención y los embeddings van entonces solo con los botones.

| Campo | Después de instalar | Qué hace |
|---|---|---|
| **Embeddings provider** | **None (keyword search)** | **None (keyword search)**, **openai**, **gemini**, **mistral**, **compatible** o **demo**. Anthropic y DeepSeek no están en esta lista. El cambio exige **Reindex now**. |
| **Embeddings model** | **Default for the chosen provider** | Un modelo del proveedor de arriba. Los vectores de dos modelos no se pueden comparar. Un modelo de otro proveedor se ignora y se usa el predeterminado. Reindexe después del cambio. |
| **Other embeddings model** | vacío | Id exacto de un modelo que no está en la lista, por ejemplo uno de Ollama. Si está relleno, sustituye la elección de arriba. |
| **Index products** | Sí | Indexa nombre, marca, categorías, características y descripciones de productos activos y visibles. No: las preguntas de producto no tienen texto de catálogo. |
| **Index CMS pages** | Sí | Indexa páginas CMS activas. No indexe páginas con notas internas. |
| **Never use these categories** | ninguna | Los productos de estas categorías no se indexan y no se pueden mostrar, comparar ni ofrecer al carrito. Reindexe después del cambio. |
| **Never use these products** | ninguno | Lo mismo para productos sueltos. |
| **Cache answers to repeated policy questions** | Sí | Invitados, solo la primera pregunta, y nunca una respuesta con precio o pedido. **Clear answer cache** en la pestaña Knowledge después de editar una página de política. |
| **Cache lifetime (hours)** | 24 | De 1 a 720. Después el modelo responde de nuevo. |

### 3.17 Límites y coste

![Límites y coste](https://mypresta.eu/docs/images/docs/prestamindai-limits.webp)

La pantalla está en inglés. En este manual esta página se llama Límites y coste.

La línea de arriba muestra las peticiones, los tokens y el coste estimado de hoy. Cuando se alcanza un presupuesto diario, el asistente envía un aviso corto y ofrece pasar la pregunta a su equipo hasta el día siguiente.

| Campo | Después de instalar | Qué hace |
|---|---|---|
| **Daily budget (USD)** | 0 | 0 significa sin tope. Solo funciona si los modelos que usa tienen precio. Cuando el coste de hoy llega al tope, las llamadas al modelo paran hasta medianoche. |
| **Daily token budget** | 0 | 0 significa sin tope. Cuenta tokens aunque el precio sea 0. 1000000 tokens son unos cientos de conversaciones. |
| **Messages per minute per visitor IP** | 8 | De 1 a 60. Quien envía más deprisa recibe un aviso de espera y no hay llamada al modelo. |
| **Messages per conversation per day** | 60 | De 1 a 500. Después la conversación queda bloqueada ese día. |
| **Max reply tokens** | 700 | De 150 a 3000. Con 700 son unas 450 palabras. Un límite corto corta la respuesta. |
| **Max tool steps per message** | 5 | De 1 a 8. Cuántas lecturas en vivo (búsqueda, producto, envío) puede hacer un mensaje. 1 corta la investigación en varios pasos. |
| **Max characters per customer message** | 800 | De 100 a 2000. El texto más largo se corta. |
| **Messages of history sent to the model** | 12 | De 2 a 30. 12 son los últimos seis intercambios. Más historial envía más tokens. |
| **Temperature (0-1)** | 0.3 | De 0.2 a 0.4 se queda más cerca de los datos de la tienda. Más alto varía la redacción. Algunos modelos nuevos de OpenAI lo ignoran. |

### 3.18 Privacy

![Privacy](https://mypresta.eu/docs/images/docs/prestamindai-privacy.webp)

La pantalla está en inglés. En este manual esta página se llama Privacy.

| Campo | Después de instalar | Qué hace |
|---|---|---|
| **Mask card numbers, IBAN and PESEL** | Sí | Los sustituye por [card], [iban] e [id] antes de guardar el texto y antes de enviarlo al proveedor. |
| **Delete conversations after (days)** | 90 | 0 las conserva. La URL de cron borra las conversaciones más viejas. Las estadísticas de pedidos se quedan. |
| **Order status without signing in, for registered customers** | Sí | Un visitante puede preguntar con la referencia del pedido y el correo del checkout. No: ese par solo vale para pedidos de invitado, y un cliente con cuenta tiene que iniciar sesión. Como máximo 10 intentos en 10 minutos. |
| **Allow proactive messages** | Sí | No apaga todos los disparadores. |
| **Proactive triggers wait for consent** | Sí | No hay burbuja hasta que el banner de cookies llame a la función de consentimiento. El chat sí funciona. No: los disparadores saltan para todos. |
| **Control group (% of visitors)** | 0 | De 0 a 50. Esos visitantes no ven al asistente. **Dashboard** puede comparar el valor de los pedidos. |

**Delete old conversations** es un formulario aparte. **Older than (days)** empieza ahí en 30. **Delete** borra esas conversaciones al momento. El mensaje es **Deleted N conversations.** No se puede deshacer.

### 3.19 Ajustes de Escalation

![Ajustes de Escalation](https://mypresta.eu/docs/images/docs/prestamindai-escalation.webp)

La pantalla está en inglés. En este manual esta página se llama Ajustes de Escalation.

| Campo | Después de instalar | Qué hace |
|---|---|---|
| **Live chat console in the back office** | Sí | Muestra el botón **Live chats**. Solo lo ven los empleados que pueden abrir **PrestaMind AI**. Apagado oculta el botón. **Conversations** sigue funcionando. |
| **E-mail for hand-offs** | vacío | Cada escalación envía un resumen y el contacto que dejó el visitante. Vacío significa sin correo. El correo de la tienda tiene que funcionar. |
| **Webhook type** | **Slack** | **Slack**, **Telegram** o **Generic JSON**. |
| **Webhook URL** | vacío | URL de incoming webhook de Slack, Telegram `https://api.telegram.org/bot<TOKEN>/sendMessage` o cualquier URL https. Vacío significa sin webhook. El resultado está en la lista **Escalations**. |
| **Telegram chat id** | vacío | Id numérico del chat o del grupo. Se ignora en Slack y en Generic JSON. |
| **Offer a person when sentiment falls below** | -0.5 | De -1 a 0. Más cerca de 0 reacciona antes. El asistente se disculpa y ofrece pasar el caso al equipo. |

### 3.20 Recordatorios de carrito

![Recordatorios de carrito](https://mypresta.eu/docs/images/docs/prestamindai-reminders.webp)

La pantalla está en inglés. En este manual esta página se llama Recordatorios de carrito.

No sale nada hasta que **Send cart reminders** está en Yes y la URL de cron corre. Un correo por carrito abandonado, solo a un cliente con cuenta. Los invitados no reciben correo.

| Campo | Después de instalar | Qué hace |
|---|---|---|
| **Send cart reminders** | No | Encendido: la siguiente pasada de cron envía los recordatorios que encajan. Apagado: no sale nada nuevo. Las filas ya enviadas se quedan en la lista. |
| **Only customers who subscribed to the newsletter** | Sí | Sí: los clientes sin la casilla del boletín no reciben nada. |
| **Send after (hours of inactivity)** | 3 | Al menos 1. El carrito tiene que seguir así durante esas horas. |
| **Stop after (hours since the last change)** | 72 | Tiene que ser mayor que el valor de arriba. Los carritos más viejos se saltan. |
| **Minimum cart value (tax incl.)** | 0 | 0 significa cualquier carrito. El importe es la moneda de la tienda. |
| **Discount code in the e-mail** | **No discount code** | Una de sus ofertas, o ninguna. Las reglas de la oferta siguen valiendo. Si se alcanza el tope diario, el correo sale sin código. |
| **E-mail subject** | vacío | Por idioma. Vacío usa un asunto integrado. El cliente recibe el asunto del idioma de su cuenta. |

**Send a test e-mail** usa **Send the test to** (al principio su correo del back office) y **Send test**. Sale una muestra al momento. No se registra y no crea un código. **Test e-mail sent.** o **The e-mail could not be sent. Check the e-mail settings of the shop.** Una dirección mala muestra **Enter a valid e-mail address.**

**Latest reminders** lista fecha, carrito, cliente, código y estado.

### 3.21 Couriers

![Couriers](https://mypresta.eu/docs/images/docs/prestamindai-couriers.webp)

La pantalla está en inglés. En este manual esta página se llama Couriers.

La página lista los métodos de envío de esta tienda. Si no hay ninguno, ve **Your shop has no shipping methods yet. Add them in Shipping > Carriers; they appear here automatically.**

En cada método, **tracking link** es una dirección por idioma. Ponga `{n}` donde va el número de seguimiento. Una dirección sin `{n}`, o que no empiece por http o https, se ignora. Un idioma vacío usa el idioma por defecto. Si el transportista ya tiene una URL de seguimiento en **Shipping**, luego **Carriers**, esa URL va primero. Sin ningún enlace, el asistente cita solo el número.

**live status** sale solo si el nombre contiene InPost o DHL, o si usted lo eligió antes. **No live status (tracking link only)** deja el enlace. InPost no necesita clave. DHL muestra **DHL API key**: regístrese en el sitio de desarrolladores de DHL, cree una app Shipment Tracking - Unified y pegue la clave. La clave gratuita permite unas 250 llamadas al día. La clave se guarda cifrada. Sin ella se salta el estado en vivo de DHL y se usa el enlace. Las respuestas en vivo se guardan 10 minutos.

### 3.22 Tools

![Tools](https://mypresta.eu/docs/images/docs/prestamindai-tools.webp)

La pantalla está en inglés. En este manual esta página se llama Tools.

Desmarque una herramienta para que el modelo no la reciba. Una herramienta apagada no puede ejecutarse. En modo catálogo, las herramientas de carrito, oferta y contenido del carrito quedan apagadas. Una pregunta de política o una charla solo puede llamar a **create_ticket**.

| Herramienta | Riesgo en pantalla | Necesita | Qué recibe el visitante |
|---|---|---|---|
| search_products | lectura | - | Hasta seis fichas. Precio máximo opcional y solo en stock. El visitante pulsa **Add to cart**. |
| popular_products | lectura | - | Más vendidos de pedidos reales, 90 días por defecto, de 7 a 365, hasta seis fichas. Sin cifras exactas de ventas. |
| get_product_live | lectura | - | Precio, stock, características y variantes actuales de un producto. |
| compare_products | lectura | - | Dos o tres productos uno al lado del otro. |
| suggest_substitute | lectura | - | Alternativas que están en stock. |
| get_cart | lectura | un carrito | Contenido y total. |
| add_to_cart | la pantalla marca la confirmación | confirmación del cliente | Una ficha. Cantidad de 1 a 20. El módulo no añade la línea. El visitante pulsa **Add to cart**. |
| check_shipping | lectura | - | Métodos, plazos y el umbral de envío gratis. Código ISO de país opcional. |
| get_order_status | lectura | sesión, o referencia más correo del checkout | Estado de ese pedido. |
| track_parcel | lectura | la misma identidad que el estado del pedido | Transportista, número y enlace. InPost en vivo sin clave. DHL en vivo con la clave DHL. |
| start_return | confirmación | cliente con sesión | No sale nada hasta **Send the return request**. |
| request_quote | confirmación | el formulario | Artículos, empresa y contacto. No sale nada hasta **Send the quote request**. |
| create_ticket | traspaso | a un invitado se le pide correo o teléfono | **Talk to a person** abre una escalación. |
| apply_offer | deciden las reglas | un carrito | Un código solo si una oferta guardada encaja. Si ninguna regla encaja, no hay código. |

**Save** guarda las casillas.

### 3.23 Updates

![Updates](https://mypresta.eu/docs/images/docs/prestamindai-updates.webp)

La pantalla está en inglés. En este manual esta página se llama Updates.

**Check now** compara la versión instalada con la de los servidores de MyPresta.eu. Deje los avisos automáticos encendidos para ver un aviso en el back office. El módulo no se actualiza solo. Usted instala el paquete nuevo.

## 4. Tienda

La burbuja está oculta hasta que **Show the assistant to all visitors** está encendido, salvo las IP de la lista de vista previa. Los visitantes del grupo de control no la ven.

El visitante pulsa el botón en la esquina que usted eligió. La ventana muestra el nombre del asistente, la línea de aviso y el saludo. El visitante escribe y pulsa la flecha. En la tienda no hay un botón con el texto Send. La respuesta entra en la ventana si el servidor no la almacena en búfer.

Las fichas muestran **Add to cart**. Una devolución espera a **Send the return request**. Un presupuesto espera a **Send the quote request**. **Talk to a person** pasa el chat al equipo. Mientras usted tiene la conversación, los mensajes nuevos del visitante se guardan y sus respuestas se ven como **Shop team**.

Una burbuja proactiva sale solo si los disparadores están permitidos, el visitante encaja con la regla y hay consentimiento si usted lo exige. Una burbuja por visita. El enlace de prueba de **Triggers** es para usted, no para los clientes.

La dirección cron no es una página para visitantes. Ábrala solo desde el programador del servidor. Un token malo recibe un rechazo y no hace nada.

## 5. Problemas

**No hay burbuja.** **Show the assistant to all visitors** está apagado, ese visitante está en el grupo de control o la caché de página completa guarda la página vieja. Encienda el interruptor o añada su IP a la lista de vista previa, guarde y vacíe la caché de página completa.

**Could not create the module tables.** La instalación paró antes del elemento de menú. Lea el mensaje de la base de datos, corrija los permisos del usuario de la base y vuelva a instalar.

**Could not register hook** y un nombre de hook, o **Could not register:** en **Health**. Pulse **Repair hooks**. Si la línea se queda, el usuario de la tienda no puede escribir hooks. Corrija los permisos de la base y pulse el botón otra vez.

**Could not add the menu tab.** La instalación no terminó el menú. Abra **Module Manager**, desinstale si el módulo quedó a medias y vuelva a instalar. **Configure** también intenta recrear el elemento de menú.

**No API key stored for the selected provider.** Pegue la clave en **Model provider** y pulse **Save and test the connection**. Un campo de contraseña vacío no borra la clave. **Remove the stored key** sí la borra.

**That model is already on the list.** Elíjalo como **Main model** o **Fast model** en lugar de añadirlo otra vez.

**Enter a model id: letters, digits and . _ - : / @ only.** Escriba el id de la lista de modelos del proveedor. Los espacios no valen.

**Built-in models cannot be removed.** Deje la fila. Añada un id propio si necesita otro modelo.

**Errores de proveedor en Dashboard.** La clave es mala, el proveedor no conoce el id del modelo o el proveedor no responde. Si hay reserva y el fallo es antes de la primera palabra, responde la reserva. Corrija la clave o el modelo y use **Playground**.

**La respuesta llega en un bloque, no palabra a palabra.** Pulse **Test streaming** en **Health**. Si falla, el proxy o el alojamiento almacenan la respuesta en búfer. Pida al alojamiento que lo desactive en la dirección de chat de la tienda.

**I cannot answer right now.** Se alcanzó el presupuesto diario o el de tokens, o el proveedor falló y no hay reserva. Suba el presupuesto, espere al día siguiente o arregle el proveedor. El asistente ofrece pasar la pregunta al equipo.

**Aviso de espera, o conversación bloqueada.** El visitante envió más que **Messages per minute per visitor IP** o más que **Messages per conversation per day**. Espere o suba el límite.

**Un disparador no sale nunca.** Lea el cuadro de **Triggers**. **Allow proactive messages** está apagado, el disparador está inactivo, **apply_offer** está apagado mientras el disparador espera a que el visitante pregunte, o los disparadores esperan consentimiento y el banner nunca llama a la función. Use **Open the shop in test mode**. Después de una prueba real, el enfriamiento oculta ese disparador en ese navegador.

**El descuento no sale nunca.** No hay oferta, la oferta no está enganchada al disparador, el carrito está por debajo del mínimo, se alcanzó el tope diario, un producto está en una categoría excluida o el producto ya tiene descuento. El asistente no inventa un porcentaje.

**Add to cart no añade nada solo.** La ficha es solo una ficha. El visitante pulsa **Add to cart**. En modo catálogo las herramientas de carrito siguen apagadas.

**Test e-mail sent.** es éxito. **The e-mail could not be sent. Check the e-mail settings of the shop.** significa que el correo de la tienda falló. **Enter a valid e-mail address.** significa que la dirección de prueba está vacía o es inválida. Los correos a clientes también necesitan **Send cart reminders** en Yes y una URL de cron que funcione.

**Deleted N conversations.** Pulsó **Delete** en **Privacy**. Esos hilos ya no están.

## 6. Para el desarrollador

### 6.1 Resumen

Nombre técnico `prestamindai`, clase `prestamindai`, versión en el archivo `1.8.9`, nombre en la lista **PrestaMind AI**, autor MyPresta.eu, pestaña `front_office_features`. Compatibilidad desde 1.7.6.0, máximo `99.99.99`. No hay `enable()` ni `disable()` propios. Desactivar en PrestaShop para los hooks registrados. Activar los vuelve a registrar por el núcleo.

`PmaiConfig` lee y escribe claves de `Configuration` con el prefijo `PMAI_`. `PmaiProviderRouter` elige `PmaiOpenAiProvider`, `PmaiAnthropicProvider`, `PmaiGeminiProvider` o `PmaiMockProvider`. DeepSeek y la URL compatible usan el cliente compatible con OpenAI. `PmaiOrchestrator` arma el prompt, llama al modelo y ejecuta herramientas de `PmaiToolRegistry`. Los precios usados en la llamada se copian a la fila de uso.

### 6.2 Archivos

| Archivo | Función |
|---|---|
| `prestamindai.php` | Instalación, desinstalación, hooks, pestaña de menú, redirección desde **Configure**. |
| `sql/install.php` | Crea las 16 tablas. |
| `sql/uninstall.php` | Borra esas tablas. |
| `controllers/admin/AdminPrestamindaiController.php` | Pestañas del back office y acciones POST. |
| `controllers/front/chat.php` | Dirección del chat en la tienda. |
| `controllers/front/cron.php` | Una URL de cron. |
| `src/Service/PmaiConfig.php` | Valores iniciales, listas de modelos, precios integrados, modelos propios. |
| `src/Admin/PmaiForms.php` | Cada formulario del back office y las descripciones de los campos. |
| `src/Admin/PmaiSectionHelp.php` | Texto de ayuda de cada pestaña. |
| `src/Agent/PmaiToolRegistry.php` | Las 14 herramientas y el filtro del modo catálogo. |
| `src/Llm/PmaiOpenAiProvider.php` | OpenAI, DeepSeek y la URL compatible. |
| `src/Llm/PmaiAnthropicProvider.php` | Anthropic. |
| `src/Llm/PmaiGeminiProvider.php` | Gemini. |
| `src/Llm/PmaiMockProvider.php` | Demo sin conexión. |
| `src/Knowledge/PmaiIndexer.php` | Descubrir y reindexar. |
| `src/Safety/PmaiGuardrails.php` | Sustituye tarjeta, IBAN y PESEL. |
| `upgrade/` | Las actualizaciones de versión llaman a `upgradeDb()`. |
| `translations/{iso}.php` | Cadenas del back office. |
| `views/` | Plantillas, CSS y JS del back office y de la tienda. |

### 6.3 Controladores

`AdminPrestamindai` es la clase de menú. El padre es la primera clase existente entre `AdminParentCustomerThreads`, `AdminCustomerThreads` e `IMPROVE`. La etiqueta de la pestaña es **PrestaMind AI**. `getContent()` redirige a este controlador.

`pmai_tab` es uno de `dashboard`, `live`, `history`, `conversations`, `knowledge`, `triggers`, `playground`, `evals`, `escalations`, `settings`, `updates`. Los ajustes también leen `pmai_sub`: `health`, `widget`, `provider`, `knowledge`, `limits`, `privacy`, `escalation`, `reminders`, `couriers`, `tools`.

`controllers/front/chat.php` acepta las operaciones de tienda init, message, feedback, confirm, add_to_cart, escalate, poll, event y open_trigger. `controllers/front/cron.php` exige el token de cron. Un token malo devuelve JSON `ok: false` y `error: token`.

### 6.4 Hooks

Registrados al instalar: `displayBackOfficeHeader`, `dashboardZoneTwo`, `actionAdminControllerSetMedia`, `displayHeader`, `displayBeforeBodyClosingTag`, `displayFooter`, `actionObjectProductAddAfter`, `actionObjectProductUpdateAfter`, `actionObjectProductDeleteAfter`, `actionObjectCmsAddAfter`, `actionObjectCmsUpdateAfter`, `actionObjectCmsDeleteAfter`, `actionValidateOrder`, `registerGDPRConsent`, `actionDeleteGDPRCustomer`, `actionExportGDPRData`.

`displayBeforeBodyClosingTag` pinta el widget y `displayFooter` es el respaldo. Los hooks de producto y CMS marcan documentos para reindexar. `actionValidateOrder` une el pedido a la cifra de ingresos. Los hooks GDPR exportan o borran las filas de ese cliente. **Repair hooks** llama a `ensureHooks()` para cada nombre que falte. El módulo no publica hooks propios para otros módulos.

### 6.5 Sustituciones

El módulo no sustituye ninguna clase ni controlador de PrestaShop.

### 6.6 Base de datos

La desinstalación hace `DROP TABLE` en cada tabla de abajo. La instalación usa `CREATE TABLE IF NOT EXISTS`. Una desinstalación fallida que dejara tablas conservaría filas viejas. Una desinstalación normal las borra y la siguiente instalación está vacía.

| Tabla | Contenido |
|---|---|
| `PREFIX_pmai_thread` | Una conversación: tienda, cliente, invitado, canal, estado, página. |
| `PREFIX_pmai_message` | Mensajes del hilo, incluido el payload de las fichas. |
| `PREFIX_pmai_tool_call` | Nombre de la herramienta, argumentos y resultado de un mensaje. |
| `PREFIX_pmai_doc` | Documento indexado de producto, CMS o FAQ. |
| `PREFIX_pmai_chunk` | Trozos de un documento, incluido el embedding si existe. |
| `PREFIX_pmai_cache` | Respuestas de política en caché. |
| `PREFIX_pmai_trigger` | Reglas de disparadores. |
| `PREFIX_pmai_offer` | Reglas de descuento. |
| `PREFIX_pmai_event` | Eventos de tienda para disparadores y estadísticas. |
| `PREFIX_pmai_usage` | Una llamada al modelo: proveedor, modelo, tokens, foto del precio, coste, estado. Sin texto del mensaje. |
| `PREFIX_pmai_request` | Filas del límite de peticiones. |
| `PREFIX_pmai_cart_reminder` | Un recordatorio de carrito enviado. |
| `PREFIX_pmai_escalation` | Traspaso, devolución o presupuesto, y el resultado del aviso. |
| `PREFIX_pmai_ratelimit` | Contadores de la ventana corta. |
| `PREFIX_pmai_eval_case` | Una pregunta de calidad y las palabras exigidas. |
| `PREFIX_pmai_eval_run` | Una pasada de esas pruebas. |

`PmaiConfig::PRICES_CHECKED` es `2026-10-31`. Los id de chat y de embeddings y los precios integrados están en `PmaiConfig::builtinModels()`, `builtinEmbeddingModels()` y `builtinPrices()`. Los id propios son JSON en `PMAI_CUSTOM_MODELS`. Los precios editados son JSON en `PMAI_MODEL_PRICES` y ganan al precio integrado.

### 6.7 Claves y traducciones

Cada clave es `PMAI_` más el nombre de `PmaiConfig::defaults()`. Los secretos de proveedor son `PMAI_KEY_OPENAI`, `PMAI_KEY_ANTHROPIC`, `PMAI_KEY_GEMINI`, `PMAI_KEY_DEEPSEEK`, `PMAI_KEY_MISTRAL`, `PMAI_KEY_COMPATIBLE`, `PMAI_KEY_MOCK` y `PMAI_KEY_DHLTRACK`. Se cifran con libsodium si existe `sodium_crypto_secretbox`, si no con OpenSSL. `PMAI_CRON_TOKEN` es un hex aleatorio que se crea al instalar si está vacío.

Las claves de elección de modelo son `PMAI_MODEL_MAIN_{PROVIDER}` y `PMAI_MODEL_FAST_{PROVIDER}`. Después de instalar: OpenAI `gpt-6.1-sol` / `gpt-6-luna`, Anthropic `claude-sonnet-5-5` / `claude-haiku-5-5`, Gemini `gemini-2.5-flash` / `gemini-2.5-flash-lite`, DeepSeek `deepseek-flash` / `deepseek-flash`, Mistral `mistral-large-latest` / `mistral-small-latest`, compatible `llama3.1` / `llama3.1`, mock `mock` / `mock`. `PMAI_PROVIDER` es `mock`. `PMAI_EMBED_PROVIDER` es `none`. `PMAI_EMBED_MODEL` está vacío, así que se usa el primer modelo de embeddings integrado del proveedor elegido.

`PMAI_BOT_NAME`, `PMAI_GREETING`, `PMAI_DISCLOSURE` y `PMAI_REMINDER_SUBJECT` son multilingües. La ayuda de los campos es el HTML `desc` armado en `PmaiForms`. Un idioma se añade traduciendo `translations/{iso}.php`. Las cadenas que no pasan por `$this->l()` se quedan como están en los arrays PHP (nombres de mosaicos, id de modelos, id de herramientas).

### 6.8 Ampliar

La plantilla y el CSS del widget de la tienda se pueden sustituir en el tema del modo habitual de PrestaShop, bajo `modules/prestamindai/views/`. El back office no es una sustitución de tema. No cambie los id de modelo en el tema. Añada un modelo en **Model provider**. Un banner de cookies puede llamar a `window.PrestaMindAI.setConsent(true)` cuando el visitante acepta. El módulo no trae un banner.

## 7. Ayuda

Página del módulo: [https://mypresta.eu/ai-artificial-intelligence/prestamind-ai-ai-assistant-live-chat-and-chatbot.html](https://mypresta.eu/ai-artificial-intelligence/prestamind-ai-ai-assistant-live-chat-and-chatbot.html)

Para escribir sobre este módulo, entre con su cuenta de cliente en mypresta.eu, abra el formulario de contacto y elija el tema **Support for paid modules**. El formulario indica que el inicio de sesión es obligatorio para los módulos de pago. Después de entrar, elija este módulo en el historial de compras.
