---
title: "Prestashop Popup Pro - Manual de Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo Prestashop Popup Pro para PrestaShop de MyPresta.eu."
sidebar:
  label: "Prestashop Popup Pro - Manual de Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Prestashop Popup Pro en MyPresta.eu](https://mypresta.eu/modules/front-office-features/prestashop-popup-pro.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/front-office/prestashop-popup-pro/)
>
> ---


# Prestashop Popup Pro

## 1. Requisitos y Compatibilidad

Para asegurar que el módulo Prestashop Popup Pro funcione sin problemas en tu tienda, por favor, verifica los siguientes requisitos:

- **Versiones de PrestaShop Compatibles**: PrestaShop 1.4.x, 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilidad con PHP**: PHP 5.6 - 8.5
- **Requisitos de Alojamiento**: Las extensiones PHP estándar (cURL, JSON, OpenSSL) suelen ser necesarias para el funcionamiento general de PrestaShop y deberían estar disponibles en cualquier entorno de alojamiento moderno. No se necesitan extensiones especiales o inusuales para este módulo.

## 2. Recorrido Completo por la Configuración (Cada Ajuste Agrupado por Pantalla)

### 2.1 Página de Configuración del Módulo (Back Office > Módulos > Configurar)

La página de configuración principal de Prestashop Popup Pro es donde defines todo sobre tu ventana emergente: su contenido, apariencia y comportamiento.

**Pestaña de Configuración General**

-   **Activar Popup Pro:**

    -   **Qué hace este ajuste:** Este es el interruptor maestro para todo el módulo.
    -   **Efecto de cambiar este ajuste:**
        -   *Cuando está activado:* El módulo comenzará a mostrar ventanas emergentes según tus otras configuraciones.
        -   *Cuando está desactivado:* No aparecerán ventanas emergentes en tu tienda, independientemente de otras configuraciones.
    -   **Valor recomendado:** SÍ (cuando quieras usar ventanas emergentes).
    -   **Escenario / ejemplo de comerciante:** Estás ejecutando una campaña y quieres activar tu ventana emergente. La activas. Después de la campaña, la desactivas sin perder tus ajustes.
-   **Contenido del Popup (Editor HTML):**

    -   **Qué hace este ajuste:** Este es el núcleo de tu ventana emergente. Es un potente editor HTML donde diseñas lo que aparece dentro de la ventana emergente. Puedes añadir texto, imágenes, enlaces, videos e incluso incrustar formularios (por ejemplo, suscripción a boletines).
    -   **Efecto de cambiar este ajuste:** Cualquier cambio aquí actualiza directamente el contenido visual que se muestra a tus clientes en la ventana emergente.
    -   **Valor recomendado:** Tu mensaje promocional deseado, imagen o llamada a la acción.
    -   **Escenario / ejemplo de comerciante:** Quieres anunciar un 15% de descuento. Escribirías "¡Obtén un 15% de descuento en tu primer pedido! Usa el código: AHORRA15" y quizás añadirías una imagen de productos populares.
-   **Ancho del Popup (px):**

    -   **Qué hace este ajuste:** Define el ancho de tu ventana emergente en píxeles.
    -   **Efecto de cambiar este ajuste:**
        -   *Aumentar el valor:* Hace la ventana emergente más ancha.
        -   *Disminuir el valor:* Hace la ventana emergente más estrecha.
    -   **Valor recomendado:** Empieza con `600px` a `800px` para escritorio, luego ajusta según tu contenido y diseño.
    -   **Escenario / ejemplo de comerciante:** Tienes una imagen de banner grande en tu ventana emergente. Podrías establecer el ancho en `800px` para asegurar que la imagen se muestre bien. Para un mensaje de texto simple, `400px` podría ser suficiente.
-   **Altura del Popup (px):**

    -   **Qué hace este ajuste:** Define la altura de tu ventana emergente en píxeles.
    -   **Efecto de cambiar este ajuste:**
        -   *Aumentar el valor:* Hace la ventana emergente más alta.
        -   *Disminuir el valor:* Hace la ventana emergente más baja.
    -   **Valor recomendado:** `auto` (dejar vacío) o un valor de píxel específico si tu contenido tiene una altura fija.
    -   **Escenario / ejemplo de comerciante:** Si el contenido de tu ventana emergente es dinámico o corto, dejarlo vacío (`auto`) permite que la ventana emergente ajuste su altura para adaptarse al contenido. Si tienes un video que requiere una relación de aspecto específica, podrías establecer una altura fija.
-   **Mostrar Popup En:**

    -   **Qué hace este ajuste:** Determina *cuándo* aparece la ventana emergente.
    -   **Efecto de cambiar este ajuste:**
        -   *Carga de Página:* La ventana emergente aparece después de que la página se carga.
        -   *Intención de Salida:* La ventana emergente aparece cuando el ratón del usuario se mueve fuera de la ventana del navegador (indicando que podría irse).
        -   *Desplazamiento:* La ventana emergente aparece después de que el usuario se desplaza un cierto porcentaje de la página.
        -   *Retraso de Tiempo:* La ventana emergente aparece después de un número específico de segundos.
    -   **Valor recomendado:** Depende de tu objetivo. "Intención de Salida" suele ser eficaz para capturar visitantes que abandonan. "Carga de Página" con un pequeño retraso (por ejemplo, 3-5 segundos) es bueno para anuncios generales.
    -   **Escenario / ejemplo de comerciante:** Para reducir el abandono del carrito, elegirías "Intención de Salida" y ofrecerías un código de descuento. Para anunciar una nueva línea de productos, podrías usar "Carga de Página" con un retraso de 3 segundos.
-   **Retraso Antes de que Apareza el Popup (segundos):**

    -   **Qué hace este ajuste:** Si "Mostrar Popup En" está configurado en "Carga de Página" o "Retraso de Tiempo", esto especifica cuántos segundos esperar antes de que se muestre la ventana emergente.
    -   **Efecto de cambiar este ajuste:** Un valor más alto significa que la ventana emergente aparece más tarde, dando al cliente más tiempo para navegar. Un valor más bajo significa que aparece antes.
    -   **Valor recomendado:** `3` a `5` segundos. Demasiado rápido puede ser intrusivo, demasiado lento podría perder al cliente.
    -   **Escenario / ejemplo de comerciante:** Quieres dar a los clientes un momento para ver tu página de inicio antes de mostrar un formulario de suscripción a boletines. Lo configuras en `5` segundos.
-   **Frecuencia del Popup (días):**

    -   **Qué hace este ajuste:** Controla la frecuencia con la que un cliente *recurrente* ve la ventana emergente. Una vez que un cliente cierra la ventana emergente, este ajuste determina cuántos días pasan antes de que la vea de nuevo.
    -   **Efecto de cambiar este ajuste:**
        -   *0:* La ventana emergente aparece en cada visita (puede ser molesto).
        -   *Valor más alto:* La ventana emergente aparece con menos frecuencia para los visitantes recurrentes.
    -   **Valor recomendado:** `7` a `30` días. Evita molestar a tus clientes leales.
    -   **Escenario / ejemplo de comerciante:** Estás ejecutando una oferta de un mes. Lo configuras en `7` días para que los clientes reciban un recordatorio semanal, pero no en cada visita.
-   **Mostrar Popup en Dispositivos Móviles:**

    -   **Qué hace este ajuste:** Activa o desactiva si la ventana emergente debe mostrarse en smartphones y tabletas.
    -   **Efecto de cambiar este ajuste:**
        -   *Activado:* La ventana emergente aparece en dispositivos móviles, ajustándose de forma responsiva.
        -   *Desactivado:* La ventana emergente solo aparecerá en ordenadores de escritorio.
    -   **Valor recomendado:** SÍ, pero asegúrate de que el contenido de tu ventana emergente sea compatible con dispositivos móviles.
    -   **Escenario / ejemplo de comerciante:** Tienes una ventana emergente simple, basada en texto, que se ve bien en el móvil. La activas para llegar a todos tus clientes. Si tu ventana emergente tiene imágenes o formularios complejos que se rompen en el móvil, podrías desactivarla.
-   **Color de Fondo del Popup:**

    -   **Qué hace este ajuste:** Establece el color de fondo de la propia ventana emergente.
    -   **Efecto de cambiar este ajuste:** Cambia el color visual detrás de tu contenido.
    -   **Valor recomendado:** Un color que complemente tu marca y haga que tu contenido destaque. A menudo blanco (`#FFFFFF`) o un color neutro claro.
    -   **Escenario / ejemplo de comerciante:** Tu marca usa mucho azul. Podrías elegir un fondo azul claro para la ventana emergente para que coincida.
-   **Color del Borde del Popup:**

    -   **Qué hace este ajuste:** Establece el color del borde alrededor de la ventana emergente.
    -   **Efecto de cambiar este ajuste:** Cambia el color visual del borde de la ventana emergente.
    -   **Valor recomendado:** A menudo un color sutil, o transparente si prefieres sin borde.
    -   **Escenario / ejemplo de comerciante:** Quieres un aspecto limpio, así que lo configuras en un gris muy claro o transparente.
-   **Ancho del Borde del Popup (px):**

    -   **Qué hace este ajuste:** Establece el grosor del borde alrededor de la ventana emergente.
    -   **Efecto de cambiar este ajuste:** Un valor más alto hace el borde más grueso.
    -   **Valor recomendado:** `0` a `2` píxeles para un efecto sutil.
    -   **Escenario / ejemplo de comerciante:** Quieres una ventana emergente muy definida, así que estableces un borde de `2px`. Para un diseño minimalista, lo estableces en `0`.
-   **Radio del Borde del Popup (px):**

    -   **Qué hace este ajuste:** Controla la redondez de las esquinas de la ventana emergente.
    -   **Efecto de cambiar este ajuste:**
        -   *0:* Esquinas afiladas y cuadradas.
        -   *Valor más alto:* Esquinas más redondeadas.
    -   **Valor recomendado:** `0` a `10` píxeles para un aspecto moderno.
    -   **Escenario / ejemplo de comerciante:** Quieres que tu ventana emergente tenga bordes suaves y modernos, así que lo configuras en `8px`.
-   **Color de Fondo de la Superposición:**

    -   **Qué hace este ajuste:** Establece el color de la capa semi-transparente que aparece *detrás* de la ventana emergente, oscureciendo el resto del contenido de tu tienda.
    -   **Efecto de cambiar este ajuste:** Cambia el color de la superposición. A menudo un color oscuro con transparencia.
    -   **Valor recomendado:** Negro (`#000000`) con algo de transparencia (por ejemplo, `rgba(0,0,0,0.7)` si puedes introducir RGBA).
    -   **Escenario / ejemplo de comerciante:** Quieres que la ventana emergente sea el foco absoluto, así que eliges una superposición oscura, casi opaca.
-   **Opacidad de la Superposición (0-100):**

    -   **Qué hace este ajuste:** Controla cuán transparente u opaco es el fondo de la superposición. `0` es completamente transparente (invisible), `100` es completamente opaco (color sólido).
    -   **Efecto de cambiar este ajuste:**
        -   *Valor más alto:* Más opaco, fondo más oscuro, más enfoque en la ventana emergente.
        -   *Valor más bajo:* Más transparente, fondo más claro, más contenido de tu tienda visible.
    -   **Valor recomendado:** `50` a `80`.
    -   **Escenario / ejemplo de comerciante:** Quieres atenuar ligeramente el fondo pero aún permitir que los clientes vean tu tienda detrás de la ventana emergente. Lo configuras en `60`.
-   **Mostrar Botón de Cerrar:**

    -   **Qué hace este ajuste:** Activa o desactiva la visibilidad del botón de cierre "X" estándar en la ventana emergente.
    -   **Efecto de cambiar este ajuste:**
        -   *Activado:* Aparece un botón de cierre, permitiendo a los clientes descartar fácilmente la ventana emergente.
        -   *Desactivado:* No hay botón "X". Los clientes deberán hacer clic fuera de la ventana emergente o pulsar ESC (si está activado) para cerrarla.
    -   **Valor recomendado:** SÍ, para una buena experiencia de usuario.
    -   **Escenario / ejemplo de comerciante:** Quieres facilitar a los clientes el cierre de la ventana emergente, así que activas el botón de cierre.
-   **Permitir Cerrar Haciendo Clic Fuera:**

    -   **Qué hace este ajuste:** Determina si hacer clic en cualquier parte de la superposición (fuera del contenido de la ventana emergente) cerrará la ventana emergente.
    -   **Efecto de cambiar este ajuste:**
        -   *Activado:* Hacer clic en la superposición cierra la ventana emergente.
        -   *Desactivado:* Solo el botón de cierre o la tecla ESC descartarán la ventana emergente.
    -   **Valor recomendado:** SÍ, para una buena experiencia de usuario.
    -   **Escenario / ejemplo de comerciante:** Quieres proporcionar múltiples formas para que los clientes descarten la ventana emergente, así que activas esto.
-   **Permitir Cerrar con la Tecla ESC:**

    -   **Qué hace este ajuste:** Determina si al pulsar la tecla ESC del teclado se cerrará la ventana emergente.
    -   **Efecto de cambiar este ajuste:**
        -   *Activado:* La tecla ESC cierra la ventana emergente.
        -   *Desactivado:* La tecla ESC no tiene efecto en la ventana emergente.
    -   **Valor recomendado:** SÍ, para una buena experiencia de usuario.
    -   **Escenario / ejemplo de comerciante:** Quieres proporcionar una forma accesible para que los clientes descarten la ventana emergente, así que activas esto.
-   **CSS Personalizado:**

    -   **Qué hace este ajuste:** Te permite añadir tus propias reglas CSS personalizadas para estilizar aún más la ventana emergente o su contenido. Esto es para usuarios avanzados o desarrolladores.
    -   **Efecto de cambiar este ajuste:** Cualquier regla CSS válida que añadas aquí se aplicará a la ventana emergente, potencialmente anulando los estilos predeterminados.
    -   **Valor recomendado:** Déjalo vacío a menos que tengas necesidades de estilo específicas.
    -   **Escenario / ejemplo de comerciante:** Quieres cambiar el tamaño de la fuente de un párrafo específico dentro de tu ventana emergente, o añadir un efecto de sombra único no disponible en otros ajustes. Añadirías el CSS aquí.

**Pestaña de Configuración Avanzada (o agrupación similar si está disponible)**

-   **Animación del Popup (Efecto de Entrada):**

    -   **Qué hace este ajuste:** Selecciona un efecto de animación para cuando la ventana emergente aparece en pantalla.
    -   **Efecto de cambiar este ajuste:** La ventana emergente se animará para aparecer usando el efecto elegido (por ejemplo, fundido de entrada, deslizar hacia abajo, zoom).
    -   **Valor recomendado:** "Fundido de Entrada" o "Deslizar Hacia Abajo" suelen ser sutiles y profesionales.
    -   **Escenario / ejemplo de comerciante:** Quieres que tu ventana emergente aparezca suavemente en lugar de simplemente aparecer al instante, así que eliges "Fundido de Entrada".
-   **Animación del Popup (Efecto de Salida):**

    -   **Qué hace este ajuste:** Selecciona un efecto de animación para cuando la ventana emergente desaparece de la pantalla.
    -   **Efecto de cambiar este ajuste:** La ventana emergente se animará para desaparecer usando el efecto elegido.
    -   **Valor recomendado:** "Fundido de Salida" o "Deslizar Hacia Arriba" para que coincida con el efecto de entrada.
    -   **Escenario / ejemplo de comerciante:** Para mantener una experiencia de usuario consistente y fluida, eliges "Fundido de Salida" como animación de salida.
-   **Mostrar Popup en Páginas Específicas (URLs):**

    -   **Qué hace este ajuste:** Te permite especificar URLs exactas o patrones de URL donde la ventana emergente debe (o no debe) aparecer.
    -   **Efecto de cambiar este ajuste:** La ventana emergente solo se mostrará en las páginas que coincidan con tus criterios, o se ocultará de ellas.
    -   **Valor recomendado:** Usa esto para dirigir tus ventanas emergentes de manera efectiva.
    -   **Escenario / ejemplo de comerciante:** Tienes una oferta especial para una categoría de producto específica. Introducirías la URL de esa página de categoría aquí para asegurar que la ventana emergente solo aparezca para visitantes relevantes.
-   **No Mostrar Popup en Páginas Específicas (URLs):**

    -   **Qué hace este ajuste:** Te permite especificar URLs exactas o patrones de URL donde la ventana emergente *no* debe aparecer.
    -   **Efecto de cambiar este ajuste:** La ventana emergente se ocultará de las páginas que coincidan con tus criterios.
    -   **Valor recomendado:** Usa esto para evitar mostrar ventanas emergentes en páginas sensibles como el proceso de pago o el inicio de sesión.
    -   **Escenario / ejemplo de comerciante:** No quieres que la ventana emergente interrumpa el proceso de pago. Añadirías la URL de tu página de pago (por ejemplo, `/order`) aquí.
-   **Mostrar Popup para Grupos de Clientes Específicos:**

    -   **Qué hace este ajuste:** Restringe la visibilidad de la ventana emergente a ciertos grupos de clientes (por ejemplo, Visitantes, Clientes, Invitados, Mayoristas).
    -   **Efecto de cambiar este ajuste:** Solo los clientes que pertenezcan a los grupos seleccionados verán la ventana emergente.
    -   **Valor recomendado:** Depende de tu público objetivo. "Visitantes" e "Invitados" son comunes para la generación de leads.
    -   **Escenario / ejemplo de comerciante:** Tienes una oferta especial exclusivamente para tus clientes registrados. Seleccionarías "Clientes" aquí.
-   **Mostrar Popup para Idiomas Específicos:**

    -   **Qué hace este ajuste:** Restringe la visibilidad de la ventana emergente a clientes que navegan en idiomas específicos.
    -   **Efecto de cambiar este ajuste:** Solo los clientes que utilicen el idioma seleccionado verán la ventana emergente.
    -   **Valor recomendado:** Todos los idiomas, o específicos si el contenido de tu ventana emergente depende del idioma.
    -   **Escenario / ejemplo de comerciante:** Tienes una ventana emergente con contenido solo traducido al inglés y al francés. Seleccionarías "Inglés" y "Francés" aquí.
-   **Mostrar Popup para Monedas Específicas:**

    -   **Qué hace este ajuste:** Restringe la visibilidad de la ventana emergente a clientes que navegan con monedas específicas.
    -   **Efecto de cambiar este ajuste:** Solo los clientes que utilicen la moneda seleccionada verán la ventana emergente.
    -   **Valor recomendado:** Todas las monedas, o específicas si el contenido de tu ventana emergente depende de la moneda.
    -   **Escenario / ejemplo de comerciante:** Tienes una oferta especial solo válida para clientes que pagan en USD. Seleccionarías "USD" aquí.
-   **Mostrar Popup para Países Específicos:**

    -   **Qué hace este ajuste:** Restringe la visibilidad de la ventana emergente a clientes de países específicos.
    -   **Efecto de cambiar este ajuste:** Solo los clientes detectados como procedentes de los países seleccionados verán la ventana emergente.
    -   **Valor recomendado:** Todos los países, o específicos para campañas geo-dirigidas.
    -   **Escenario / ejemplo de comerciante:** Estás ejecutando una promoción exclusivamente para clientes en Francia. Seleccionarías "Francia" aquí.

### 2.2 Tabla de Referencia Rápida de Configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| **Página de Configuración del Módulo** | Activar Popup Pro | SÍ | Interruptor maestro para activar/desactivar la ventana emergente. |
| | Contenido del Popup (Editor HTML) | (Vacío) | Diseña lo que aparece dentro de la ventana emergente (texto, imágenes, enlaces). |
| | Ancho del Popup (px) | 600-800px | Establece el tamaño horizontal de la ventana emergente. |
| | Altura del Popup (px) | auto (vacío) | Establece el tamaño vertical de la ventana emergente, o se ajusta automáticamente. |
| | Mostrar Popup En | Intención de Salida / Carga de Página (retraso de 3-5s) | Determina el disparador para la aparición de la ventana emergente. |
| | Retraso Antes de que Apareza el Popup (segundos) | 3-5 | Retraso de tiempo antes de que se muestre la ventana emergente (si se selecciona "Carga de Página"). |
| | Frecuencia del Popup (días) | 7-30 | Con qué frecuencia un cliente recurrente ve la ventana emergente. |
| | Mostrar Popup en Dispositivos Móviles | SÍ | Controla la visibilidad de la ventana emergente en teléfonos/tabletas. |
| | Color de Fondo del Popup | #FFFFFF (Blanco) | Color del fondo de la ventana emergente. |
| | Color del Borde del Popup | Transparente / Gris Claro | Color del borde de la ventana emergente. |
| | Ancho del Borde del Popup (px) | 0-2 | Grosor del borde de la ventana emergente. |
| | Radio del Borde del Popup (px) | 0-10 | Redondez de las esquinas de la ventana emergente. |
| | Color de Fondo de la Superposición | #000000 (Negro) | Color del fondo semi-transparente detrás de la ventana emergente. |
| | Opacidad de la Superposición (0-100) | 50-80 | Nivel de transparencia de la superposición. |
| | Mostrar Botón de Cerrar | SÍ | Muestra el botón 'X' para cerrar la ventana emergente. |
| | Permitir Cerrar Haciendo Clic Fuera | SÍ | Permite cerrar haciendo clic en la superposición. |
| | Permitir Cerrar con la Tecla ESC | SÍ | Permite cerrar pulsando la tecla ESC. |
| | CSS Personalizado | (Vacío) | Añade CSS personalizado para un estilo avanzado. |
| | Animación del Popup (Efecto de Entrada) | Fundido de Entrada / Deslizar Hacia Abajo | Efecto visual cuando aparece la ventana emergente. |
| | Animación del Popup (Efecto de Salida) | Fundido de Salida / Deslizar Hacia Arriba | Efecto visual cuando desaparece la ventana emergente. |
| | Mostrar Popup en Páginas Específicas (URLs) | (Vacío) | Muestra la ventana emergente solo en las URLs especificadas. |
| | No Mostrar Popup en Páginas Específicas (URLs) | (Vacío) | Oculta la ventana emergente de las URLs especificadas (por ejemplo, pago). |
| | Mostrar Popup para Grupos de Clientes Específicos | Todos | Dirige la ventana emergente a tipos de clientes específicos. |
| | Mostrar Popup para Idiomas Específicos | Todos | Dirige la ventana emergente a idiomas específicos. |
| | Mostrar Popup para Monedas Específicas | Todos | Dirige la ventana emergente a monedas específicas. |
| | Mostrar Popup para Países Específicos | Todos | Dirige la ventana emergente a países específicos. |

## 3. Solución de Problemas para Comerciantes y Preguntas Frecuentes (FAQ)

**P1: Mi ventana emergente no aparece en absoluto. ¿Qué debo revisar primero?**
**R1:**

1.  **¿Está el módulo activado?** Ve a **Módulos > Gestor de Módulos** y asegúrate de que "Prestashop Popup Pro" esté instalado y activado.
2.  **¿Está "Activar Popup Pro" configurado en SÍ en la configuración del módulo?** Este es el interruptor maestro.
3.  **Revisa tus ajustes de "Mostrar Popup En":** Si está configurado en "Retraso de Tiempo", asegúrate de que el retraso no sea demasiado largo. Si es "Intención de Salida", asegúrate de que lo estás activando correctamente (moviendo el ratón fuera de la ventana del navegador).
4.  **Borra la caché de PrestaShop:** Ve a **Parámetros Avanzados > Rendimiento**, desplázate hacia abajo y haz clic en "Borrar caché". A veces, los archivos de caché antiguos impiden que los nuevos ajustes del módulo surtan efecto.
5.  **Busca conflictos:** Desactiva temporalmente otros módulos de ventanas emergentes o superposiciones para ver si hay un conflicto.

**P2: Mi ventana emergente se ve extraña o rota en dispositivos móviles.**
**R2:**

1.  **¿Está activado "Mostrar Popup en Dispositivos Móviles"?** Si no, no se mostrará en absoluto.
2.  **Revisa tu "Contenido del Popup":** HTML complejo, imágenes muy grandes o contenido no diseñado para pantallas pequeñas pueden causar problemas. Intenta simplificar el contenido o usar imágenes más pequeñas y optimizadas.
3.  **Verifica "Ancho del Popup" y "Altura del Popup":** Aunque el módulo es responsivo, a veces los valores de píxeles fijos pueden causar problemas en pantallas muy pequeñas. Considera dejar "Altura del Popup" vacío para `auto`.
4.  **CSS Personalizado:** Si has añadido CSS personalizado, es posible que no sea compatible con dispositivos móviles. Prueba tu CSS usando las herramientas de desarrollador del navegador (inspeccionar elemento) en diferentes tamaños de pantalla.

**P3: La ventana emergente aparece con demasiada frecuencia para mis clientes. ¿Cómo puedo controlar esto?**
**R3:**

1.  **Ajusta "Frecuencia del Popup (días)":** Este es el ajuste clave. Un número más alto significa que los clientes verán la ventana emergente con menos frecuencia. Por ejemplo, configurarlo en `30` significa que solo la verán una vez al mes después de cerrarla.
2.  **Considera tu ajuste de "Mostrar Popup En":** Si es "Carga de Página" con un retraso corto, podría sentirse más intrusivo que "Intención de Salida".

**P4: Quiero traducir el contenido de mi ventana emergente a varios idiomas. ¿Cómo lo hago?**
**R4:** El editor HTML de "Contenido del Popup" debería admitir la entrada multi-idioma de PrestaShop. Al editar el contenido, busca pestañas o desplegables de idioma (normalmente en la parte superior derecha del editor) para cambiar entre idiomas y proporcionar contenido diferente para cada uno. Asegúrate de tener los idiomas deseados instalados en PrestaShop. Si el editor no muestra pestañas de idioma, es posible que debas introducir el contenido para cada idioma manualmente cambiando el idioma de tu back office.

**P5: El contenido de la ventana emergente es demasiado pequeño/grande, o la fuente es incorrecta.**
**R5:**

1.  **Usa el editor HTML:** El editor HTML incorporado suele proporcionar opciones para cambiar el tamaño de la fuente, el color y otros estilos para tu texto.
2.  **CSS Personalizado:** Para un control más preciso, usa el campo "CSS Personalizado". Por ejemplo, para cambiar el tamaño de la fuente de todo el texto en la ventana emergente, podrías añadir:

    ```
    .popuppro-content p { font-size: 16px !important;}
    ```

    (Es posible que necesites inspeccionar la ventana emergente en tu navegador para encontrar los selectores CSS correctos como `.popuppro-content`).

## 4. Guía para Desarrolladores y Webmasters (Arquitectura Técnica y Mapa de Código)

Esta sección proporciona una visión técnica detallada del módulo Prestashop Popup Pro, destinada a desarrolladores, webmasters y agencias técnicas.

### 4.1 Visión General de la Arquitectura

El módulo Prestashop Popup Pro sigue una arquitectura de módulo estándar de PrestaShop, aprovechando principalmente la clase `Module` para su funcionalidad principal y `ModuleFrontController` para las interacciones AJAX. Depende en gran medida de JavaScript para la lógica de visualización del front-office, animaciones y manejo de eventos (como la intención de salida). La configuración se gestiona a través del método `getContent()` en el archivo principal del módulo, almacenando los ajustes en `ps_configuration`. El módulo integra un Gestor de Plantillas Smarty para una creación de contenido flexible y un selector de color para la personalización de la interfaz de usuario.

### 4.2 Controladores (`controllers/`)

-   **Controladores del Front-Office**:

    -   `popuppro/controllers/front/index.php`
        -   **Nombre de la Clase:** `PopupproIndexModuleFrontController` (probablemente, basado en la convención de nombres de archivo)
        -   **Clase Padre:** `ModuleFrontController`
        -   **Responsabilidad:** Este controlador podría servir como un punto de entrada general o un respaldo para las solicitudes del front-office relacionadas con el módulo. Podría ser responsable de la carga inicial de datos o de la renderización de una vista básica del módulo si no se solicita ninguna acción específica.
    -   `popuppro/controllers/front/popuploader.php`
        -   **Nombre de la Clase:** `PopupproPopuploaderModuleFrontController`
        -   **Clase Padre:** `ModuleFrontController`
        -   **Responsabilidad:** Este controlador es muy probable que sea responsable de cargar el contenido y la configuración de la ventana emergente dinámicamente a través de AJAX. Cuando un usuario visita una página, un script JavaScript enviaría una solicitud AJAX a este controlador para obtener el HTML, el estilo y la configuración de comportamiento de la ventana emergente basándose en la configuración del módulo. Devolvería una carga útil JSON o HTML.
    -   `popuppro/controllers/front/popupstat.php`
        -   **Nombre de la Clase:** `PopupproPopupstatModuleFrontController`
        -   **Clase Padre:** `ModuleFrontController`
        -   **Responsabilidad:** Este controlador está diseñado para manejar datos estadísticos relacionados con la ventana emergente. Recibiría solicitudes AJAX del JavaScript del front-office para registrar impresiones de la ventana emergente, clics en el botón de cerrar u otras interacciones, permitiendo al módulo rastrear el rendimiento (aunque no se lista explícitamente una vista de estadísticas dedicada en los controladores de administración, estos datos podrían almacenarse para uso futuro o registro interno).
-   **Controladores de Administración del Back-Office**: Ninguno listado explícitamente, lo que indica que toda la administración se maneja a través del método `getContent()` del archivo principal del módulo.

### 4.3 Clases y Modelos Principales (`classes/`)

No se listan clases personalizadas ni definiciones de `ObjectModel` en el directorio `classes/`. Esto sugiere que el módulo almacena principalmente su configuración directamente en la tabla `ps_configuration` utilizando `Configuration::updateValue()` y `Configuration::get()`, y no gestiona entidades de datos personalizadas complejas que requieran tablas de base de datos dedicadas o mapeo de `ObjectModel`.

### 4.4 Activos JavaScript (`views/js/`)

-   `popuppro/js/popup-engine.js`:
    -   **Alcance:** Front-office.
    -   **Detalle:** Este es probablemente el archivo JavaScript principal responsable de la mecánica fundamental de la ventana emergente. Manejaría la creación de los elementos DOM de la ventana emergente (la superposición, el contenedor de la ventana emergente, el botón de cerrar), la inyección del contenido, la gestión de animaciones (efectos de entrada/salida) y el posicionamiento de la ventana emergente en la pantalla. Probablemente define el objeto principal `PopupPro` o similar.
-   `popuppro/js/popup-events.js`:
    -   **Alcance:** Front-office.
    -   **Detalle:** Este script gestionaría todos los escuchadores de eventos que activan la ventana emergente. Esto incluye:
        -   `DOMContentLoaded` o `window.load` para la configuración inicial.
        -   `setTimeout` para ventanas emergentes con retraso de tiempo.
        -   Escuchadores de eventos de desplazamiento para ventanas emergentes activadas por desplazamiento.
        -   `mouseleave` o eventos similares en `document.body` para la detección de intención de salida.
        -   Escuchadores de clics para el botón de cerrar y el cierre por clic fuera.
        -   Escuchador de `keyup` para la tecla ESC.
        -   Llamadas AJAX a `popuploader.php` para obtener contenido y a `popupstat.php` para registrar eventos.
-   `popuppro/js/popup-scripts.js`:
    -   **Alcance:** Front-office.
    -   **Detalle:** Este archivo podría contener scripts adicionales, quizás más específicos, relacionados con el comportamiento o las interacciones de la ventana emergente, posiblemente manejando envíos de formularios dentro de la ventana emergente, actualizaciones de contenido dinámico o integración con otros elementos del front-office.
-   `popuppro/js/script.js`:
    -   **Alcance:** Front-office/Back-office (nombre genérico, podría ser cualquiera).
    -   **Detalle:** Dado su nombre genérico, este podría ser un script de utilidad general, o podría contener lógica de inicialización para la ventana emergente en el front-office, o incluso algunos scripts menores del back-office si se carga allí. Es común que los módulos tengan un `script.js` para código de propósito general.
-   `popuppro/js/tinymce16-force-urls.inc.js`, `popuppro/js/tinymce16.inc.js`:
    -   **Alcance:** Back-office.
    -   **Detalle:** Estos archivos están relacionados con el editor de texto enriquecido TinyMCE, específicamente la versión 1.6. Se incluyen para proporcionar la funcionalidad del editor HTML para el campo "Contenido del Popup" en la configuración del back-office del módulo. `tinymce16-force-urls.inc.js` probablemente se encarga de asegurar que las URLs estén correctamente formateadas dentro del editor.
-   `popuppro/jscolor/jscolor.js`:
    -   **Alcance:** Back-office.
    -   **Detalle:** Esta es la biblioteca JavaScript para la funcionalidad del selector de color utilizada en la configuración del back-office (por ejemplo, para el Color de Fondo del Popup, Color del Borde, Color de la Superposición). Proporciona la interfaz interactiva de selección de color.
-   `popuppro/lib/smartyTemplatesManager/js/smartyTemplatesManager.js`:
    -   **Alcance:** Back-office.
    -   **Detalle:** Este script forma parte de una biblioteca interna para gestionar plantillas Smarty dentro de la configuración del módulo. Probablemente proporciona funcionalidad para previsualizar plantillas, seleccionarlas o insertar dinámicamente contenido basado en plantillas en el editor HTML.

### 4.5 Hojas de Estilo CSS (`views/css/`)

-   `popuppro/css.css`:
    -   **Alcance:** Front-office.
    -   **Detalle:** Esta es probablemente la hoja de estilo principal para la ventana emergente del front-office, definiendo su apariencia predeterminada: posicionamiento, tamaño, borde, sombra, estilo del botón de cerrar y, potencialmente, ajustes responsivos.
    -   **Selectores Clave:** `.popuppro-overlay`, `.popuppro-popup`, `.popuppro-close-btn`, `.popuppro-content`.
-   `popuppro/lib/smartyTemplatesManager/css/smartyTemplatesManager.css`:
    -   **Alcance:** Back-office.
    -   **Detalle:** Hojas de estilo para la interfaz del Gestor de Plantillas Smarty dentro de la configuración del back-office del módulo. Estilizaría la selección de plantillas, las áreas de vista previa y los elementos de la interfaz de usuario relacionados.
-   `popuppro/popuppro.css`:
    -   **Alcance:** Front-office.
    -   **Detalle:** Similar a `css.css`, este podría contener estilos adicionales o específicos para la ventana emergente, potencialmente para diferentes estados de animación o elementos de contenido específicos. Podría haber cierta superposición o separación de responsabilidades entre `css.css` y `popuppro.css`.
    -   **Selectores Clave:** Probablemente similares a `css.css`, centrándose en los componentes principales de la ventana emergente.

### 4.6 Estructura de Plantillas Smarty (`views/templates/`)

-   **Plantillas de Hook (`views/templates/hook/`)**: (Ninguna listada explícitamente en `views/templates/hook/`, pero `views/header.tpl` probablemente está enganchada)

    -   `popuppro/views/header.tpl`:
        -   **Hook:** `displayHeader`
        -   **Salida:** Esta plantilla está casi con certeza enganchada a `displayHeader`. Sería responsable de inyectar los archivos JavaScript y CSS necesarios en la sección `<head>` del front-office, y potencialmente alguna estructura HTML inicial o datos de configuración para que JavaScript los use.
    -   `popuppro/views/header_address.tpl`, `popuppro/views/header_carrier.tpl`:
        -   **Hook:** Potencialmente `displayHeader` u otros hooks específicos relacionados con la información de dirección/transportista.
        -   **Salida:** Estas parecen ser plantillas de encabezado especializadas, posiblemente para mostrar contenido dinámico relacionado con la dirección del cliente o la información del transportista *dentro* de una ventana emergente, o para escenarios específicos de ventanas emergentes. Su uso exacto dependería de la lógica del módulo.
    -   `popuppro/views/popup.tpl`:
        -   **Hook:** No enganchado directamente, pero renderizado por JavaScript.
        -   **Salida:** Esta es la plantilla principal para la estructura de la ventana emergente del front-office. Define el HTML para la superposición, el contenedor de la ventana emergente, el botón de cerrar y un marcador de posición para el contenido dinámico cargado a través de AJAX.
-   **Plantillas de Administración (`views/templates/admin/`)**:

    -   `popuppro/views/admin/admin.tpl`:
        -   **Propósito:** La plantilla principal para la página de configuración del módulo en el back office. Contendría el diseño general, las pestañas y la estructura para los formularios de configuración.
    -   `popuppro/views/admin/boscript.tpl`:
        -   **Propósito:** Plantilla JavaScript del back-office. Esto probablemente inyecta código JavaScript específico necesario para la página de configuración de administración, como la inicialización de TinyMCE, el selector de color o la validación de formularios personalizada.
    -   `popuppro/views/admin/popup_preview.tpl`:
        -   **Propósito:** Plantilla para mostrar una vista previa en vivo o simulada de la ventana emergente dentro de la configuración del back-office, permitiendo a los comerciantes ver los cambios a medida que los realizan.
    -   `popuppro/views/admin/presets.tpl`:
        -   **Propósito:** Plantilla para gestionar o mostrar plantillas o estilos de ventanas emergentes predefinidos.
    -   `popuppro/views/admin/shadow_editor.tpl`:
        -   **Propósito:** Una plantilla especializada para configurar efectos de sombra para la ventana emergente, ofreciendo potencialmente controles avanzados más allá del color/opacidad simples.
    -   `popuppro/views/admin/stats.tpl`:
        -   **Propósito:** Si el módulo recopila estadísticas (como sugiere `popupstat.php`), esta plantilla se usaría para mostrar esas estadísticas en el back office.
    -   `popuppro/views/templates/admin/_configure/helpers/form/form.tpl`:
        -   **Propósito:** Esta es una plantilla de anulación estándar de PrestaShop para la clase `HelperForm`, específicamente para el formulario de configuración del módulo. Permite al módulo personalizar cómo se renderiza su formulario de configuración, potencialmente añadiendo campos o diseño personalizados.
-   **Plantillas de la Biblioteca SmartyTemplatesManager (`popuppro/lib/smartyTemplatesManager/tpl/` y `views/`)**:

    -   `popuppro/lib/smartyTemplatesManager/tpl/cartMini.tpl`, `example.tpl`, `freeShippingBar.tpl`, `helloCustomer.tpl`, `lastOrder.tpl`, `productHighlight.tpl`, `showReachedQtyInCart.tpl`:
        -   **Propósito:** Estas son plantillas de contenido predefinidas que el comerciante puede seleccionar o usar como punto de partida para el contenido de su ventana emergente. Ofrecen casos de uso comunes como pantallas de mini-carrito, anuncios de envío gratuito, mensajes de bienvenida, detalles del último pedido, destacados de productos o mensajes de cantidad alcanzada en el carrito. Se renderizarían dinámicamente en el área de contenido principal de la ventana emergente.
    -   `popuppro/lib/smartyTemplatesManager/views/buttonManager.tpl`, `buttonManagerNoJs.tpl`, `createTemplateForm.tpl`, `editTemplateForm.tpl`, `mainForm.tpl`, `selectInput.tpl`:
        -   **Propósito:** Estas plantillas forman parte de la biblioteca interna Smarty Templates Manager, utilizadas dentro de la configuración del back-office para gestionar e interactuar con las plantillas de contenido. Proporcionan una interfaz de usuario para crear, editar y seleccionar estos bloques de contenido predefinidos.

### 4.7 Esquema de Base de Datos y Mapa de Hooks

-   **Tablas de Base de Datos**:

    -   El módulo no parece crear tablas SQL personalizadas.
    -   Todos los ajustes de configuración se almacenan en la tabla `ps_configuration`. Los nombres clave de configuración suelen seguir el patrón `POPUPPRO_SETTING_NAME`. Ejemplos incluyen:
        -   `POPUPPRO_ENABLED`
        -   `POPUPPRO_CONTENT` (probablemente multi-idioma)
        -   `POPUPPRO_WIDTH`
        -   `POPUPPRO_DISPLAY_ON`
        -   `POPUPPRO_FREQUENCY`
        -   `POPUPPRO_BG_COLOR`
        -   …y así sucesivamente para todas las opciones de configuración.
-   **Tabla de Hooks Registrados**:

| Nombre del Hook | Momento de Ejecución | Propósito Técnico |
| --- | --- | --- |
| `displayHeader` | Ejecutado en la sección `<head>` de cada página del front-office. | Inyecta los archivos CSS y JavaScript necesarios para que la ventana emergente funcione, y potencialmente inicializa variables JavaScript globales o datos de configuración. |
| `displayRightColumn` | Ejecutado en la columna derecha de las páginas (si está habilitado por el tema). | Aunque la descripción del módulo menciona "Columnas", es menos probable para una ventana emergente de pantalla completa. Si se usa, podría renderizar un disparador para la ventana emergente o un elemento más pequeño, sin superposición. |
| `displayLeftColumn` | Ejecutado en la columna izquierda de las páginas (si está habilitado por el tema). | Similar a `displayRightColumn`, menos probable para la ventana emergente principal, pero podría usarse para un disparador. |
| `displayFooter` | Ejecutado en la parte inferior de cada página del front-office, antes de la etiqueta de cierre `</body>`. | Podría usarse para inyectar JavaScript que necesita ejecutarse después de que el DOM esté completamente cargado, o para colocar la estructura HTML de la ventana emergente al final del documento. |
| `displayProductAdditionalInfo` (o hook similar de página de producto) | Ejecutado en la página del producto, típicamente debajo de los detalles principales del producto. | Si el módulo admite ventanas emergentes específicas de productos, podría usar este hook para inyectar un disparador o una lógica de ventana emergente específica relevante para el producto. |
| `actionFrontControllerSetMedia` | Ejecutado cuando un controlador frontal establece sus medios (CSS/JS). | Un hook común para que los módulos registren sus activos (CSS/JS) de manera eficiente, asegurando que se carguen solo cuando sea necesario. |

## 5. Soporte Oficial y Actualizaciones

Para soporte oficial, actualizaciones del módulo y cualquier asistencia adicional con tu módulo Prestashop Popup Pro, visita tu cuenta de cliente en [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nuestro equipo de soporte dedicado está listo para ayudarte a maximizar el potencial de tu módulo.
