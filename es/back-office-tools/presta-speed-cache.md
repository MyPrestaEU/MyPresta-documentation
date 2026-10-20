---
title: "Presta Speed Cache - Manual para el Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo Presta Speed Cache para PrestaShop de MyPresta.eu."
sidebar:
  label: "Presta Speed Cache - Manual para el Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Presta Speed Cache en MyPresta.eu](https://mypresta.eu/modules/administration-tools/presta-speed-cache.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/back-office-tools/presta-speed-cache/)
>
> ---


# Presta Speed Cache

## 1. Requisitos y Compatibilidad

- **Versiones de PrestaShop Soportadas**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilidad PHP**: PHP 7.1 - 8.5 (El módulo está diseñado para funcionar en este rango, asegurando una amplia compatibilidad mientras soporta las últimas versiones estables de PHP.)
- **Requisitos de Alojamiento**: Se requieren extensiones PHP estándar como cURL, JSON y OpenSSL, que suelen estar disponibles en la mayoría de los entornos de alojamiento modernos. Para métodos de caché avanzados como Redis o Memcached, estos servicios deben estar instalados y configurados en tu servidor.

## 2. Recorrido Completo por la Configuración (Cada Ajuste Agrupado por Pantalla)

### 2.1 Página de Configuración del Módulo (Back Office > Módulos > Configurar)

Esta es el área de configuración principal para Presta Speed Cache. Encontrarás varios ajustes para afinar cómo opera la caché de tu tienda.

#### Pestaña de Configuración General

- **Activar Caché:**

  - **Qué hace este ajuste:** Este es el interruptor maestro para el módulo. Activa o desactiva la funcionalidad de caché para toda tu tienda.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está activado:* El módulo comenzará a cachear páginas y a servirlas rápidamente. El rendimiento de tu tienda mejorará significativamente.
    - *Cuando está desactivado:* El módulo dejará de cachear, y tu tienda volverá a su velocidad predeterminada de PrestaShop, que suele ser más lenta.
  - **Valor recomendado:** **SÍ**. Esta es la función principal del módulo.
  - **Escenario / ejemplo del comerciante:** Acabas de instalar el módulo y quieres activar los beneficios de velocidad. Configúralo en SÍ. Si estás solucionando problemas con otro módulo y sospechas que el almacenamiento en caché podría estar interfiriendo, podrías deshabilitarlo temporalmente.
- **Tiempo de Vida de la Caché (minutos):**

  - **Qué hace este ajuste:** Determina cuánto tiempo una página en caché permanece válida antes de que el módulo la considere "obsoleta" y la reconstruya.
  - **Efecto de cambiar este ajuste:**
    - *Valor más alto (por ejemplo, 1440 para 24 horas):* Las páginas se sirven desde la caché por más tiempo, reduciendo la carga del servidor pero potencialmente mostrando contenido ligeramente desactualizado si realizas cambios frecuentes (por ejemplo, actualizaciones de precios).
    - *Valor más bajo (por ejemplo, 60 para 1 hora):* Las páginas se reconstruyen con más frecuencia, asegurando contenido más fresco pero aumentando ligeramente la carga del servidor.
  - **Valor recomendado:** Empieza con **1440** (24 horas). Ajusta según la frecuencia con la que cambian los datos de tus productos.
  - **Escenario / ejemplo del comerciante:** Si actualizas los precios o descripciones de los productos diariamente, un tiempo de vida de 24 horas está bien. Si realizas ventas flash con cambios de precios cada hora, podrías reducirlo a 60 o 120 minutos, o confiar en las funciones de invalidación automática.
- **Método de Almacenamiento de Caché:**

  - **Qué hace este ajuste:** Selecciona dónde se almacenan las páginas en caché. Diferentes métodos ofrecen distintos niveles de rendimiento y requieren configuraciones de servidor específicas.
  - **Efecto de cambiar este ajuste:**
    - *Sistema de Archivos (predeterminado):* Almacena las páginas en caché como archivos en el disco de tu servidor. El más fácil de configurar, bueno para la mayoría de las tiendas.
    - *Redis:* Almacena la caché en memoria usando el servidor Redis. Mucho más rápido que el sistema de archivos, ideal para tiendas de alto tráfico. Requiere que Redis esté instalado y configurado en tu servidor.
    - *Memcached:* Almacena la caché en memoria usando el servidor Memcached. Similar a Redis en beneficios de rendimiento, también requiere configuración del servidor.
  - **Valor recomendado:** Empieza con **Sistema de Archivos**. Si tienes una tienda de alto tráfico y tu alojamiento lo soporta, considera **Redis** o **Memcached** para un rendimiento máximo.
  - **Escenario / ejemplo del comerciante:** Tu tienda está creciendo rápidamente y experimentas ralentizaciones ocasionales. Tu host ofrece Redis. Cambiar a Redis puede mejorar drásticamente el rendimiento.
- **Excluir URLs de la Caché:**

  - **Qué hace este ajuste:** Te permite especificar ciertas páginas o secciones de tu tienda que *nunca* deben ser cacheadas. Esto es útil para páginas con contenido altamente dinámico o sensible.
  - **Efecto de cambiar este ajuste:**
    - *Añadir URLs:* Esas páginas siempre serán generadas de nuevo por PrestaShop, asegurando que su contenido esté siempre actualizado al minuto, pero sacrificando velocidad para esas páginas específicas.
    - *Dejar vacío:* Todas las páginas elegibles serán cacheadas.
  - **Valor recomendado:** Déjalo vacío a menos que tengas necesidades específicas. Úsalo con precaución.
  - **Escenario / ejemplo del comerciante:** Tienes una página de "Solicitud de Presupuesto" personalizada que genera formularios únicos basados en la entrada del usuario, o una página con actualizaciones de stock en tiempo real desde una API externa. Añadirías `/module/yourmodule/quotepage` o `/stock-updates` a esta lista.
- **Calentar Caché:**

  - **Qué hace este ajuste:** "Visita" automáticamente las páginas de tu tienda en segundo plano para precargar la caché, asegurando que incluso el primer visitante de una página experimente los beneficios de velocidad.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está activado:* Tu caché se poblará proactivamente, lo que lleva a tiempos de carga más rápidos para todos los visitantes, incluso aquellos que visitan una página por primera vez después de la invalidación de la caché. Esto puede aumentar ligeramente la carga del servidor durante el proceso de calentamiento.
    - *Cuando está desactivado:* Las páginas solo se cachearán después de la primera visita del cliente.
  - **Valor recomendado:** **SÍ**. Esto asegura los máximos beneficios de velocidad para todos los usuarios.
  - **Escenario / ejemplo del comerciante:** Acabas de borrar tu caché o has actualizado muchos productos. Habilitar el calentamiento asegurará que tu tienda sea rápida para los clientes de inmediato, en lugar de esperar a que visiten cada página primero.
- **Optimización HTML:**

  - **Qué hace este ajuste:** Minimiza la salida HTML de tus páginas eliminando espacios innecesarios, comentarios y saltos de línea. Esto reduce el tamaño del archivo de la página, lo que lleva a descargas más rápidas.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está activado:* El código HTML de tu página será más compacto, reduciendo el uso de ancho de banda y acelerando ligeramente la renderización de la página. Esto es generalmente seguro.
    - *Cuando está desactivado:* El HTML se servirá tal como lo genera PrestaShop, sin minificación.
  - **Valor recomendado:** **SÍ**. Es una mejora de rendimiento sencilla y segura.
  - **Escenario / ejemplo del comerciante:** Quieres exprimir cada bit de rendimiento de tu tienda. Habilitar esto hará que tu HTML sea más ligero.

#### Pestaña de Bloques Dinámicos

Esta sección te permite definir partes de tu página que *no* deben ser cacheadas, sino cargadas dinámicamente después de que la página principal se haya cargado. Esto es crucial para contenido personalizado como el carrito de compras, el estado de inicio de sesión o las salidas de módulos específicos.

- **Activar Bloques Dinámicos:**

  - **Qué hace este ajuste:** Activa la capacidad de definir áreas específicas de tu página que se cargarán por separado y dinámicamente, incluso cuando el resto de la página se sirva desde la caché.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está activado:* Puedes configurar módulos o áreas de contenido específicos para que permanezcan dinámicos, asegurando que el contenido personalizado esté siempre fresco.
    - *Cuando está desactivado:* Todo el contenido se cacheará, lo que podría llevar a contenido dinámico obsoleto (por ejemplo, un carrito vacío mostrado incluso si se añadieron artículos).
  - **Valor recomendado:** **SÍ**. Esto es esencial para una tienda con caché funcional.
  - **Escenario / ejemplo del comerciante:** Quieres que el carrito de tu cliente siempre muestre el número correcto de artículos, incluso si la página del producto en sí está en caché.
- **Lista de Módulos Dinámicos:**

  - **Qué hace este ajuste:** Esta es una lista donde seleccionas qué módulos *siempre* deben renderizarse dinámicamente, incluso si están enganchados a una página en caché.
  - **Efecto de cambiar este ajuste:**
    - *Añadir un módulo:* La salida de ese módulo se obtendrá de nuevo para cada usuario, asegurando que su contenido esté siempre actualizado (por ejemplo, bloque del carrito, bloque de información del usuario).
    - *Eliminar un módulo:* La salida del módulo se cacheará junto con el resto de la página, lo que podría mostrar datos obsoletos.
  - **Valor recomendado:** Incluye módulos como `ps_shoppingcart`, `ps_customeraccountlinks`, `ps_languageselector`, `ps_currencyselector`, y cualquier otro módulo que muestre información específica del usuario o en tiempo real.
  - **Escenario / ejemplo del comerciante:** Instalas un nuevo módulo de "Chat en Vivo" que necesita mostrar disponibilidad en tiempo real. Lo añadirías a esta lista para asegurar que siempre sea dinámico.

#### Pestaña de Invalidación y Purga

Esta sección gestiona cómo y cuándo se borra o actualiza la caché, asegurando que tus clientes siempre vean la información más reciente del producto.

- **Invalidación Automática de Caché:**

  - **Qué hace este ajuste:** Cuando está activado, el módulo borra automáticamente las páginas en caché relevantes cada vez que realizas cambios en el back office de PrestaShop (por ejemplo, actualizando un producto, categoría o página CMS).
  - **Efecto de cambiar este ajuste:**
    - *Cuando está activado:* No tienes que borrar manualmente la caché después de cada cambio. El módulo borra inteligentemente solo las páginas afectadas, asegurando que los clientes vean las actualizaciones rápidamente.
    - *Cuando está desactivado:* Tendrías que borrar manualmente toda la caché después de cada cambio significativo, o los clientes podrían ver contenido obsoleto hasta que expire el tiempo de vida de la caché.
  - **Valor recomendado:** **SÍ**. Esta es una característica crucial de "configúralo y olvídate" para la frescura de los datos.
  - **Escenario / ejemplo del comerciante:** Actualizas el precio de un producto. Con la invalidación automática, la versión en caché de esa página de producto (y potencialmente sus páginas de categoría) se borra, por lo que los clientes ven el nuevo precio inmediatamente.
- **Purgar Caché al Actualizar Producto:**

  - **Qué hace este ajuste:** Controla específicamente si la caché relacionada con un producto se borra cuando ese producto se actualiza.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está activado:* Asegura que cualquier página que muestre el producto actualizado (página de producto, página de categoría, resultados de búsqueda) se actualice en la caché.
    - *Cuando está desactivado:* Las actualizaciones de productos podrían no reflejarse en las páginas en caché hasta que expire el tiempo de vida de la caché o la borres manualmente.
  - **Valor recomendado:** **SÍ**. Esencial para una información precisa del producto.
  - **Escenario / ejemplo del comerciante:** Cambias la imagen de un producto. Este ajuste asegura que la nueva imagen aparezca en la página del producto inmediatamente.
- **Purgar Caché al Actualizar Categoría:**

  - **Qué hace este ajuste:** Controla si la caché relacionada con una categoría se borra cuando esa categoría se actualiza.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está activado:* Asegura que las páginas de categoría y potencialmente las páginas de productos dentro de esa categoría se actualicen.
    - *Cuando está desactivado:* Las actualizaciones de categoría (por ejemplo, nombre, descripción, productos asignados) podrían no reflejarse en las páginas en caché.
  - **Valor recomendado:** **SÍ**. Importante para la navegación y la precisión del contenido de la categoría.
  - **Escenario / ejemplo del comerciante:** Renombras una categoría. Esto asegura que el nuevo nombre aparezca en tu navegación y en la página de la categoría.
- **Purgar Caché al Actualizar Página CMS:**

  - **Qué hace este ajuste:** Controla si la caché relacionada con una página CMS se borra cuando esa página se actualiza.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está activado:* Asegura que las páginas CMS actualizadas (por ejemplo, "Sobre Nosotros", "Términos y Condiciones") se actualicen inmediatamente.
    - *Cuando está desactivado:* Las actualizaciones de las páginas CMS podrían no ser visibles para los clientes hasta que expire la caché.
  - **Valor recomendado:** **SÍ**. Importante para la precisión del contenido estático.
  - **Escenario / ejemplo del comerciante:** Actualizas tu página de "Política de Envío". Esto asegura que los clientes vean la última versión.

#### Pestaña de Configuración Avanzada

- **Activar Modo Depuración:**

  - **Qué hace este ajuste:** Activa un modo especial que muestra información sobre el estado de la caché directamente en tus páginas del front-office (visible solo para ti como administrador).
  - **Efecto de cambiar este ajuste:**
    - *Cuando está activado:* Verás una pequeña superposición en las páginas de tu tienda que indica si la página se sirvió desde la caché, cuándo se cacheó y otros detalles de diagnóstico. Esto es invaluable para la resolución de problemas.
    - *Cuando está desactivado:* No se muestra información de depuración.
  - **Valor recomendado:** **NO** para tiendas en producción. **SÍ** al configurar o solucionar problemas.
  - **Escenario / ejemplo del comerciante:** Acabas de configurar el módulo y quieres verificar que las páginas se están cacheando correctamente. Activa el modo de depuración, navega por tu tienda y comprueba la superposición.
- **Activar Depuración en Vivo:**

  - **Qué hace este ajuste:** Proporciona un panel de control en tiempo real en el back office para monitorear los aciertos de caché, los fallos y otras métricas de rendimiento.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está activado:* Obtienes acceso a una potente herramienta de monitoreo para ver la eficacia de tu caché.
    - *Cuando está desactivado:* No se recopilan ni se muestran estadísticas de caché en vivo.
  - **Valor recomendado:** **SÍ** si quieres monitorear activamente el rendimiento. Puede deshabilitarse si prefieres una sobrecarga mínima.
  - **Escenario / ejemplo del comerciante:** Quieres ver el impacto de tu estrategia de caché a lo largo del tiempo, observando cuántas solicitudes se sirven desde la caché en comparación con las que se generan de nuevo.
- **Activar SWR (Stale-While-Revalidate):**

  - **Qué hace este ajuste:** Una estrategia de caché avanzada donde, si una página en caché ha expirado, el módulo sirve inmediatamente la versión *obsoleta* (expirada) al usuario mientras reconstruye simultáneamente una versión fresca en segundo plano.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está activado:* Los usuarios casi siempre obtienen una carga de página instantánea, incluso si la caché ha expirado. La página podría estar ligeramente desactualizada por un momento, pero es increíblemente rápida. La versión fresca reemplaza la obsoleta para los visitantes posteriores.
    - *Cuando está desactivado:* Cuando una página en caché expira, el siguiente visitante esperará a que la página se reconstruya, lo que puede causar un ligero retraso.
  - **Valor recomendado:** **SÍ**. Esto ofrece el mejor equilibrio entre velocidad y frescura para la mayoría de las tiendas.
  - **Escenario / ejemplo del comerciante:** Quieres asegurarte de que tus clientes nunca experimenten una carga lenta, incluso si la caché necesita ser actualizada. SWR proporciona esta experiencia de "siempre rápido".
- **Caché para Usuarios Registrados:**

  - **Qué hace este ajuste:** Determina si las páginas deben ser cacheadas incluso para los clientes que han iniciado sesión en sus cuentas.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está activado:* Los usuarios registrados también se beneficiarán de las páginas en caché, pero el módulo debe ser muy inteligente con los bloques dinámicos para asegurar que el contenido personalizado (como los enlaces a "Mi Cuenta", el historial de pedidos) permanezca correcto.
    - *Cuando está desactivado:* Los usuarios registrados siempre recibirán páginas frescas, sin caché. Esto asegura una personalización perfecta pero sacrifica la velocidad para estos usuarios.
  - **Valor recomendado:** **SÍ**, pero asegúrate de que tus bloques dinámicos estén configurados correctamente para módulos como `ps_customeraccountlinks`.
  - **Escenario / ejemplo del comerciante:** Quieres que tus clientes recurrentes y registrados también disfruten de una experiencia súper rápida, no solo los invitados.
- **Caché para Dispositivos Móviles:**

  - **Qué hace este ajuste:** Controla si se generan y sirven versiones separadas en caché de las páginas para dispositivos móviles.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está activado:* El módulo creará y servirá páginas en caché optimizadas específicamente para usuarios móviles, lo cual es crucial si tu tema tiene diferencias significativas entre los diseños de escritorio y móvil.
    - *Cuando está desactivado:* Los usuarios móviles recibirán la versión en caché de escritorio (si aplica) o páginas sin caché, lo que podría llevar a contenido más lento o renderizado incorrectamente.
  - **Valor recomendado:** **SÍ** si tu tema es responsivo y se renderiza de manera diferente para móviles.
  - **Escenario / ejemplo del comerciante:** Tu tema utiliza diferentes plantillas o CSS para móviles. El almacenamiento en caché para móviles asegura que obtengan la versión correcta y rápida.
- **Activar Purga de Borde (Varnish/CDN):**

  - **Qué hace este ajuste:** Se integra con sistemas de caché externos como Varnish o Redes de Entrega de Contenido (CDN) para enviar solicitudes de purga cuando tu caché de PrestaShop se invalida. Esto asegura que la CDN también borre su contenido antiguo.
  - **Efecto de cambiar este ajuste:**
    - *Cuando está activado:* Tu CDN siempre servirá el contenido más fresco después de que realices actualizaciones, evitando que los clientes vean versiones antiguas almacenadas por la CDN.
    - *Cuando está desactivado:* Tu CDN podría seguir sirviendo contenido antiguo incluso después de que se borre tu caché de PrestaShop, lo que lleva a inconsistencias.
  - **Valor recomendado:** **SÍ** si estás utilizando Varnish o una CDN (como Cloudflare, Akamai, etc.) que soporte la purga de caché a través de API.
  - **Escenario / ejemplo del comerciante:** Usas Cloudflare para el rendimiento. Cuando actualizas un producto, este ajuste le indica a Cloudflare que borre su caché para ese producto, para que todos los usuarios vean la actualización inmediatamente.

#### Pestaña de Herramientas

Esta pestaña proporciona acciones manuales para gestionar tu caché.

- **Borrar Toda la Caché:**

  - **Qué hace este ajuste:** Este botón elimina inmediatamente todas las páginas en caché generadas por Presta Speed Cache.
  - **Efecto de cambiar este ajuste:** Se elimina todo el contenido en caché. La próxima vez que se visite una página, PrestaShop la generará de nuevo y luego la volverá a cachear. Esto ralentizará temporalmente tu sitio hasta que la caché se reconstruya.
  - **Valor recomendado:** Úsalo solo cuando sea necesario (por ejemplo, después de una actualización importante del tema, instalación de un módulo o si sospechas problemas de caché).
  - **Escenario / ejemplo del comerciante:** Has realizado cambios extensos en el CSS de tu tema y quieres asegurarte de que todos los visitantes vean el nuevo diseño inmediatamente. Haz clic en "Borrar Toda la Caché".
- **Ejecutar Calentamiento de Caché:**

  - **Qué hace este ajuste:** Activa manualmente el proceso de calentamiento de la caché, que visita las páginas de tu tienda para precargar la caché.
  - **Efecto de cambiar este ajuste:** El módulo comenzará a generar versiones en caché de tus páginas en segundo plano. Esto puede llevar algún tiempo dependiendo del tamaño de tu tienda y puede consumir recursos del servidor durante el proceso.
  - **Valor recomendado:** Úsalo después de borrar la caché o después de importaciones importantes de productos/categorías para reconstruir rápidamente la caché.
  - **Escenario / ejemplo del comerciante:** Acabas de borrar la caché y quieres que tu tienda sea rápida para los clientes lo antes posible.

### 2.2 Pantallas de Administración Dedicadas y Vistas de Controlador

#### 2.2.1 Gestión de Caché (Back Office > Presta Speed Cache > Gestión de Caché)

Esta pantalla proporciona una visión general detallada y una interfaz de gestión para tus páginas en caché.

- **Nombre de la Pantalla y Ubicación del Menú:** Puedes encontrarla navegando a **Presta Speed Cache** en el menú principal de tu back office de PrestaShop, luego seleccionando **Gestión de Caché**.
- **Acciones y Ajustes Disponibles:**
  - **Cuadrícula de Lista de Caché:** Esta tabla muestra una lista de las páginas actualmente en caché, incluyendo detalles como la URL, cuándo se cacheó por última vez, su tamaño y su estado actual (por ejemplo, activa, expirada).
  - **Filtrar y Buscar:** Puedes filtrar la lista por URL, estado u otros criterios para encontrar entradas de caché específicas.
  - **Borrar Caché Seleccionada:** Te permite seleccionar páginas en caché específicas de la lista y borrarlas individualmente.
  - **Borrar Toda la Caché (botón):** Un botón prominente para borrar toda la caché, similar al de la página de configuración principal.
  - **Ejecutar Calentamiento (botón):** Un botón prominente para iniciar manualmente el proceso de calentamiento de la caché.
- **Efecto de los cambios:**
  - *Borrar entradas individuales:* Solo las páginas seleccionadas se eliminarán de la caché, permitiendo que se reconstruyan en la próxima visita. Esto es útil para actualizaciones específicas sin afectar a toda la tienda.
  - *Borrar toda la caché:* Restablece toda la caché, forzando la reconstrucción de todas las páginas.
  - *Ejecutar calentamiento:* Rellena proactivamente la caché, asegurando una carga más rápida para los visitantes posteriores.
- **Flujo de trabajo recomendado para la gestión diaria de la tienda:** Utiliza esta pantalla para monitorear tu caché, identificar cualquier página que pueda no estar cacheándose correctamente o para realizar purgas de caché específicas si has realizado una actualización muy concreta que la invalidación automática podría haber pasado por alto.

#### 2.2.2 Panel de Control (Back Office > Presta Speed Cache > Panel de Control)

Esta pantalla proporciona una visión general visual del rendimiento y las estadísticas de tu caché.

- **Nombre de la Pantalla y Ubicación del Menú:** Puedes encontrarla navegando a **Presta Speed Cache** en el menú principal de tu back office de PrestaShop, luego seleccionando **Panel de Control**.
- **Acciones y Ajustes Disponibles:**
  - **Métricas de Rendimiento:** Muestra gráficos y estadísticas sobre aciertos de caché, fallos de caché, tiempos de carga promedio de la página (con y sin caché) y otros indicadores de rendimiento relevantes.
  - **Estado de Salud de la Caché:** Proporciona una visión general rápida del estado de salud del sistema de caché, indicando si hay algún problema o si está funcionando de manera óptima.
  - **Eventos de Invalidación Recientes:** Muestra un registro de las invalidaciones de caché recientes, ayudándote a rastrear cuándo y por qué se borraron partes de tu caché.
- **Efecto de los cambios:** Esta pantalla es principalmente para monitoreo e informes. No se realizan cambios directos en la configuración de la caché aquí, pero te ayuda a comprender el impacto de tus ajustes.
- **Flujo de trabajo recomendado para la gestión diaria de la tienda:** Revisa regularmente el panel de control para asegurarte de que tu caché está funcionando como se espera. Busca altas tasas de aciertos de caché y bajos tiempos de carga. Si ves una caída repentina en los aciertos de caché o un aumento en los tiempos de carga, podría indicar un problema de configuración o un problema con tu servidor.

### 2.3 Tabla de Referencia Rápida de Configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| **Configuración del Módulo** | Activar Caché | SÍ | Interruptor maestro para el almacenamiento en caché. SÍ = tienda más rápida. |
|  | Tiempo de Vida de la Caché (minutos) | 1440 (24 horas) | Cuánto tiempo permanece una página en caché. Más alto = menos carga del servidor, contenido potencialmente más antiguo. |
|  | Método de Almacenamiento de Caché | Sistema de Archivos | Dónde se almacena la caché. Sistema de Archivos (fácil), Redis/Memcached (más rápido, requiere configuración del servidor). |
|  | Excluir URLs de la Caché | Vacío | URLs que nunca deben ser cacheadas (por ejemplo, páginas altamente dinámicas). |
|  | Calentar Caché | SÍ | Construye proactivamente la caché en segundo plano. SÍ = más rápido para los primeros visitantes. |
|  | Optimización HTML | SÍ | Minimiza el HTML para tamaños de página más pequeños. SÍ = ligero aumento de velocidad. |
|  | Activar Bloques Dinámicos | SÍ | Permite que el contenido específico (carrito, inicio de sesión) permanezca dinámico. SÍ = esencial para contenido personalizado. |
|  | Lista de Módulos Dinámicos | `ps_shoppingcart`, `ps_customeraccountlinks`, etc. | Módulos que siempre deben ser dinámicos. |
|  | Invalidación Automática de Caché | SÍ | Borra la caché relevante en los cambios del back office. SÍ = contenido fresco sin intervención manual. |
|  | Purgar Caché al Actualizar Producto | SÍ | Borra la caché relacionada con el producto cuando se actualizan los productos. |
|  | Purgar Caché al Actualizar Categoría | SÍ | Borra la caché relacionada con la categoría cuando se actualizan las categorías. |
|  | Purgar Caché al Actualizar Página CMS | SÍ | Borra la caché relacionada con la página CMS cuando se actualizan las páginas CMS. |
|  | Activar Modo Depuración | NO (SÍ para solucionar problemas) | Muestra información de caché en el front office. |
|  | Activar Depuración en Vivo | SÍ | Proporciona estadísticas de caché en tiempo real en el BO. |
|  | Activar SWR (Stale-While-Revalidate) | SÍ | Sirve caché obsoleta mientras reconstruye la fresca. SÍ = siempre rápido. |
|  | Caché para Usuarios Registrados | SÍ | Cachea páginas para usuarios registrados. |
|  | Caché para Dispositivos Móviles | SÍ | Cachea versiones separadas para móviles. |
|  | Activar Purga de Borde (Varnish/CDN) | NO (SÍ si se usa CDN) | Se integra con CDN/Varnish externos para purgar la caché. |
|  | Borrar Toda la Caché (botón) | Usar cuando sea necesario | Borra toda la caché manualmente. |
|  | Ejecutar Calentamiento de Caché (botón) | Usar cuando sea necesario | Activa manualmente la precarga de la caché. |
| **Pantalla de Gestión de Caché** | Cuadrícula de Lista de Caché | N/A | Muestra y permite la gestión de páginas individuales en caché. |
|  | Borrar Caché Seleccionada | N/A | Borra entradas de caché específicas. |
| **Pantalla del Panel de Control** | Métricas de Rendimiento | N/A | Visualiza aciertos, fallos y tiempos de carga de la caché. |
|  | Estado de Salud de la Caché | N/A | Muestra la salud general del sistema de caché. |

## 3. Solución de Problemas para Comerciantes y Preguntas Frecuentes (FAQ)

**P: Mi tienda se ve rota o muestra contenido antiguo después de habilitar la caché. ¿Qué debo hacer?**
R: Primero, intenta borrar toda tu caché usando el botón "Borrar Toda la Caché" en la configuración del módulo o en la pantalla de "Gestión de Caché". Además, borra la caché de tu navegador. Si el problema persiste, revisa tu "Lista de Módulos Dinámicos" para asegurarte de que todos los módulos que muestran contenido personalizado o en tiempo real estén incluidos. Deshabilita temporalmente la "Optimización HTML" para ver si está causando conflictos.

**P: Mi carrito de compras no se actualiza correctamente, o los usuarios a veces aparecen como desconectados.**
R: Esto casi siempre se debe a que el contenido dinámico no se excluye correctamente del almacenamiento en caché. Ve a la pestaña "Bloques Dinámicos" y asegúrate de que módulos como `ps_shoppingcart`, `ps_customeraccountlinks`, `ps_languageselector` y `ps_currencyselector` estén añadidos a la "Lista de Módulos Dinámicos". Si tienes otros módulos personalizados que muestran datos específicos del usuario, añádelos también.

**P: Mi sitio web sigue siendo lento, incluso con el módulo activado.**
R:

1.  **Verifica el Modo Depuración:** Habilita el "Modo Depuración" (en Configuración Avanzada) y navega por tu front office. ¿Muestra que las páginas se están sirviendo desde la caché ("Cache HIT")? Si ves "Cache MISS", las páginas no se están cacheando.
2.  **Verifica la Tasa de Aciertos de Caché:** Revisa el "Panel de Control" para ver tu tasa de aciertos de caché. Si es baja, revisa tus ajustes de "Tiempo de Vida de la Caché" y "Excluir URLs".
3.  **Recursos del Servidor:** Aunque el almacenamiento en caché reduce la carga, tu servidor aún necesita recursos adecuados. Revisa tu plan de alojamiento y los registros del servidor en busca de otros cuellos de botella.
4.  **Otras Optimizaciones:** El almacenamiento en caché es una parte de la velocidad. Asegúrate de que tus imágenes estén optimizadas, tu tema sea eficiente y no estés ejecutando demasiados módulos pesados y no optimizados.

**P: ¿Cómo me aseguro de que mi tienda multi-idioma o multi-moneda funcione correctamente con el almacenamiento en caché?**
R: Presta Speed Cache está diseñado para manejar tiendas multi-idioma y multi-moneda generando entradas de caché separadas para cada combinación. Asegúrate de que tus módulos selectores de idioma y moneda estén añadidos a la "Lista de Módulos Dinámicos". Si notas problemas, habilita "Caché para Usuarios Registrados" y "Caché para Dispositivos Móviles" si corresponde, ya que estos también pueden afectar cómo se cachean las diferentes versiones de las páginas.

**P: He actualizado un producto, pero la información antigua sigue apareciendo en el front office.**
R:

1.  **Invalidación Automática:** Asegúrate de que "Invalidación Automática de Caché" y "Purgar Caché al Actualizar Producto" estén habilitados en la pestaña "Invalidación y Purga".
2.  **Borrado Manual:** Si la configuración es correcta, intenta borrar manualmente la caché para esa página de producto específica desde la pantalla de "Gestión de Caché", o borra toda la caché.
3.  **CDN/Varnish:** Si utilizas una CDN o Varnish, asegúrate de que "Activar Purga de Borde" esté configurado correctamente, ya que tu CDN podría estar sirviendo una versión antigua.

## 4. Guía para Desarrolladores y Webmasters (Arquitectura Técnica y Mapa de Código)

### 4.1 Visión General de la Arquitectura

Presta Speed Cache es una solución de caché altamente optimizada para PrestaShop, que emplea una arquitectura sofisticada para ofrecer velocidad sin comprometer el contenido dinámico. Aprovecha el patrón MVC de PrestaShop anulando clases centrales (`Controller`, `FrontController`, `Dispatcher`, `Hook`) para interceptar solicitudes y respuestas, sirviendo HTML en caché cuando está disponible. Utiliza un motor de almacenamiento flexible (Archivo, Redis, Memcached) e implementa características avanzadas como SWR (Stale-While-Revalidate), renderizado de bloques dinámicos a través de AJAX e invalidación inteligente de caché. El diseño del módulo se centra en una sobrecarga mínima y una compatibilidad máxima, proporcionando una capa de caché robusta y extensible.

### 4.2 Controladores (`controllers/`)

#### Controladores del Front-Office

Estos controladores manejan solicitudes AJAX específicas o tareas en segundo plano relacionadas con el almacenamiento en caché.

- `prestaspeedcache/controllers/front/api.php`
  - **Nombre de la clase y clase padre:** `PrestaSpeedCacheApiModuleFrontController` extiende `ModuleFrontController`.
  - **Responsabilidad:** Maneja las solicitudes de API, principalmente para la obtención de contenido dinámico. Cuando se sirve una página en caché y contiene bloques dinámicos, este controlador es responsable de entregar el HTML fresco para esos bloques a través de AJAX. Recibe parámetros que identifican el módulo y el hook, renderiza el módulo y devuelve el HTML.
- `prestaspeedcache/controllers/front/cron.php`
  - **Nombre de la clase y clase padre:** `PrestaSpeedCacheCronModuleFrontController` extiende `ModuleFrontController`.
  - **Responsabilidad:** Diseñado para ser llamado por una tarea cron del lado del servidor. Activa tareas en segundo plano como el calentamiento de la caché, el procesamiento de la cola de invalidación y otras operaciones de mantenimiento. Esto descarga el procesamiento pesado de las solicitudes de los usuarios.
- `prestaspeedcache/controllers/front/dynamic.php`
  - **Nombre de la clase y clase padre:** `PrestaSpeedCacheDynamicModuleFrontController` extiende `ModuleFrontController`.
  - **Responsabilidad:** Similar a `api.php`, este controlador maneja específicamente las solicitudes de bloques de contenido dinámico que se cargan asincrónicamente en páginas en caché. Asegura que los elementos personalizados como el carrito o la información del usuario estén siempre actualizados.
- `prestaspeedcache/controllers/front/index.php`
  - **Nombre de la clase y clase padre:** `PrestaSpeedCacheIndexModuleFrontController` extiende `ModuleFrontController`.
  - **Responsabilidad:** Un controlador de front-office de marcador de posición o de reserva. En muchos módulos, `index.php` en `controllers/front` sirve como un punto de entrada predeterminado si no se coincide con ningún otro controlador específico. Podría manejar el enrutamiento básico a nivel de módulo o simplemente redirigir.

#### Controladores de Administración del Back-Office

Estos controladores gestionan la configuración y los datos del módulo dentro del Back Office de PrestaShop.

- `prestaspeedcache/controllers/admin/AdminPrestaSpeedCacheController.php`
  - **Nombre de la clase y clase padre:** `AdminPrestaSpeedCacheController` extiende `ModuleAdminController`.
  - **Nombre de la pestaña y entidad gestionada:** Este es el controlador administrativo principal para el módulo, que gestiona las entradas de caché y proporciona las vistas de "Gestión de Caché" y "Panel de Control". Maneja la lista, el filtrado y la eliminación de entradas de caché. No gestiona directamente una entidad `ObjectModel` específica, sino que interactúa con `PscCacheRepository` para las operaciones de caché.
- `prestaspeedcache/controllers/admin/index.php`
  - **Nombre de la clase y clase padre:** `AdminPrestaSpeedCacheIndexController` extiende `ModuleAdminController`.
  - **Nombre de la pestaña y entidad gestionada:** Similar al `index.php` del front-office, este es probablemente un marcador de posición o controlador predeterminado para la sección de administración del módulo, asegurando un punto de entrada válido si no se solicita ninguna acción específica.

### 4.3 Clases y Modelos Centrales (`classes/`)

El directorio `classes/` del módulo contiene la lógica central, los servicios y las estructuras de datos.

- `prestaspeedcache/classes/PscAdminChips.php`: Gestiona los componentes de la interfaz de usuario para la interfaz de administración.
- `prestaspeedcache/classes/PscAfterDefaults.php`: Maneja la configuración predeterminada o las configuraciones posteriores a la instalación.
- `prestaspeedcache/classes/PscAutoload.php`: Autocargador personalizado para las clases del módulo.
- `prestaspeedcache/classes/PscCacheEngine.php`: El motor de caché principal, que orquesta las operaciones de caché.
- `prestaspeedcache/classes/PscCacheInvalidator.php`: Gestiona la lógica para invalidar páginas en caché basándose en acciones del back office.
- `prestaspeedcache/classes/PscCacheKey.php`: Genera claves únicas para las entradas en caché basándose en la URL, el contexto, etc.
- `prestaspeedcache/classes/PscCacheLock.php`: Implementa mecanismos de bloqueo para evitar condiciones de carrera durante la generación de la caché.
- `prestaspeedcache/classes/PscCacheRepository.php`: Gestiona la interacción con el almacenamiento de caché, proporcionando una capa de abstracción.
- `prestaspeedcache/classes/PscCacheStorage.php`: Clase base abstracta o interfaz para implementaciones de almacenamiento de caché.
- `prestaspeedcache/classes/PscCacheTags.php`: Gestiona las etiquetas de caché para una invalidación granular (por ejemplo, todas las páginas relacionadas con el ID de producto 123).
- `prestaspeedcache/classes/PscConfig.php`: Maneja la configuración del módulo (lee y escribe en `ps_configuration`).
- `prestaspeedcache/classes/PscDynamicBlocks.php`: Lógica para identificar y manejar bloques de contenido dinámico.
- `prestaspeedcache/classes/PscDynamicModules.php`: Gestiona la lista de módulos cuya salida siempre debe ser dinámica.
- `prestaspeedcache/classes/PscEdgePurge.php`: Maneja la integración con sistemas de caché externos (Varnish, CDN) para la purga.
- `prestaspeedcache/classes/PscFrontAssign.php`: Gestiona las asignaciones de variables de Smarty para las plantillas del front-office.
- `prestaspeedcache/classes/PscFrontDebug.php`: Lógica para mostrar información de depuración en el front office.
- `prestaspeedcache/classes/PscHealth.php`: Proporciona métodos para verificar la salud y el estado del sistema de caché.
- `prestaspeedcache/classes/PscHtmlOptimizer.php`: Implementa la lógica de minificación HTML.
- `prestaspeedcache/classes/PscHttpProbe.php`: Utilizado para solicitudes HTTP internas, por ejemplo, para el calentamiento de la caché.
- `prestaspeedcache/classes/PscInstaller.php`: Maneja las rutinas de instalación y desinstalación del módulo (tablas de base de datos, hooks, valores predeterminados de configuración).
- `prestaspeedcache/classes/PscInvalidationQueue.php`: Gestiona una cola de páginas a invalidar, a menudo procesada por cron.
- `prestaspeedcache/classes/PscLiveDebug.php`: Proporciona capacidades de depuración y monitoreo en tiempo real.
- `prestaspeedcache/classes/PscMetrics.php`: Recopila e informa métricas de rendimiento para el panel de control.
- `prestaspeedcache/classes/PscOps.php`: Métodos de utilidad operativa general.
- `prestaspeedcache/classes/PscPresets.php`: Gestiona configuraciones de caché predefinidas o preajustes.
- `prestaspeedcache/classes/PscRequestGuard.php`: Protege contra solicitudes maliciosas o asegura un manejo adecuado de las solicitudes.
- `prestaspeedcache/classes/PscTiming.php`: Utilidad para medir tiempos de ejecución.
- `prestaspeedcache/classes/PscTranslate.php`: Maneja las traducciones del módulo.
- `prestaspeedcache/classes/PscWarmup.php`: Implementa la lógica de calentamiento de la caché.
- `prestaspeedcache/classes/PscWizard.php`: Guía a los usuarios a través de la configuración inicial.
- `prestaspeedcache/classes/storage/PscFileStorage.php`: Implementación concreta para el almacenamiento de caché basado en archivos.
- `prestaspeedcache/classes/storage/PscMemcachedStorage.php`: Implementación concreta para el almacenamiento de caché de Memcached.
- `prestaspeedcache/classes/storage/PscRedisStorage.php`: Implementación concreta para el almacenamiento de caché de Redis.
- `prestaspeedcache/classes/storage/PscStorageFactory.php`: Patrón de fábrica para crear instancias de almacenamiento de caché apropiadas.
- `prestaspeedcache/classes/storage/PscStorageInterface.php`: Interfaz que define métodos para implementaciones de almacenamiento de caché.

#### Sobreescrituras (Overrides)

El módulo utiliza sobreescrituras para integrarse profundamente con el comportamiento central de PrestaShop.

- `prestaspeedcache/override/classes/controller/Controller.php`: Sobreescribe la clase base `Controller`, permitiendo que el módulo intercepte el proceso de renderizado tanto para el front como para el back office, inyectando potencialmente lógica de caché o marcadores de bloques dinámicos.
- `prestaspeedcache/override/classes/controller/FrontController.php`: Sobreescribe `FrontController` para manejar específicamente las solicitudes de páginas del front-office, permitiendo que el módulo sirva contenido en caché o prepare páginas para el almacenamiento en caché.
- `prestaspeedcache/override/classes/Dispatcher.php`: Sobreescribe el `Dispatcher` para controlar cómo se enrutan y procesan las URLs, redirigiendo potencialmente a contenido en caché o activando la generación de caché.
- `prestaspeedcache/override/classes/Hook.php`: Sobreescribe la clase `Hook` para permitir la renderización dinámica de módulos dentro de páginas en caché, asegurando que los hooks específicos siempre se ejecuten de nuevo.

### 4.4 Activos JavaScript (`views/js/`)

Estos scripts mejoran la experiencia del usuario tanto en el front como en el back office.

- `prestaspeedcache/views/js/admin.js`:
  - **Alcance:** Back-office.
  - **Detalles:** Maneja elementos interactivos en la configuración de administración del módulo, como el cambio de pestañas, el envío de formularios, las llamadas AJAX para borrar la caché, ejecutar el calentamiento y las actualizaciones dinámicas del panel de control o la lista de caché.
- `prestaspeedcache/views/js/after/lang-currency.js`:
  - **Alcance:** Front-office.
  - **Detalles:** Probablemente un pequeño script ejecutado después de la carga principal de la página, diseñado específicamente para asegurar que los selectores de idioma y moneda (que a menudo son dinámicos) funcionen correctamente dentro de un contexto de página en caché. Podría reinicializar su comportamiento o asegurar que su estado sea consistente.
- `prestaspeedcache/views/js/dynamic.js`:
  - **Alcance:** Front-office.
  - **Detalles:** Este es un script crítico para los bloques dinámicos. Identifica marcadores de posición para contenido dinámico dentro de una página en caché, realiza solicitudes AJAX (a los controladores `api.php` o `dynamic.php`) para obtener el HTML fresco para esos bloques y luego inyecta el contenido de nuevo en el DOM. Asegura que elementos como el carrito, el estado de inicio de sesión, etc., estén siempre actualizados.
- `prestaspeedcache/views/js/fo_debug.js`:
  - **Alcance:** Front-office (solo para administradores cuando el modo de depuración está activado).
  - **Detalles:** Muestra la superposición de depuración de caché en el front office. Obtiene información del estado de la caché (acierto/fallo, marca de tiempo, etc.) y la renderiza en un elemento visible y no intrusivo para los administradores.
- `prestaspeedcache/views/js/psc-dom-mock.js`:
  - **Alcance:** Front-office.
  - **Detalles:** Potencialmente un script de utilidad que proporciona una capa ligera de manipulación o simulación del DOM, posiblemente utilizada durante el proceso de inyección de bloques dinámicos para asegurar la compatibilidad u optimizar la renderización.

### 4.5 Hojas de Estilo CSS (`views/css/`)

- `prestaspeedcache/views/css/admin.css`:
  - **Alcance:** Estilo del formulario de administración del back-office.
  - **Detalles:** Estiliza las páginas de configuración del módulo, el panel de control y las cuadrículas de gestión de caché. Asegura una interfaz consistente y fácil de usar dentro del back office de PrestaShop.
  - **Selectores de clase CSS clave:** `prestaspeedcache-dashboard`, `prestaspeedcache-config-form`, `prestaspeedcache-table`, `psc-debug-overlay`.

### 4.6 Estructura de Plantillas Smarty (`views/templates/`)

#### Plantillas de administración (`views/templates/admin/`)

Estas plantillas se utilizan para la interfaz del back-office del módulo.

- `prestaspeedcache/views/templates/admin/cache_list.tpl`: Renderiza la tabla y la interfaz para listar y gestionar las páginas en caché.
- `prestaspeedcache/views/templates/admin/configure.tpl`: El formulario de configuración principal del módulo, que contiene todos los ajustes descritos en la Sección 4.1.
- `prestaspeedcache/views/templates/admin/dashboard.tpl`: Muestra las métricas de rendimiento, gráficos y el estado de salud de la caché.
- `prestaspeedcache/views/templates/admin/dynamic_modules.tpl`: La interfaz para seleccionar y gestionar los módulos que deben renderizarse dinámicamente.
- `prestaspeedcache/views/templates/admin/live_debug.tpl`: Renderiza el panel de información de depuración en tiempo real en el back office.
- `prestaspeedcache/views/templates/admin/ops.tpl`: Probablemente contiene plantillas para herramientas o acciones operativas (por ejemplo, borrado manual de caché, calentamiento).
- `prestaspeedcache/views/templates/admin/tabs.tpl`: Renderiza la estructura de navegación por pestañas para las páginas de configuración del módulo.
- `prestaspeedcache/views/templates/admin/wizard.tpl`: Plantilla para el asistente de configuración inicial, que guía a los usuarios a través de la configuración básica.

### 4.7 Esquema de Base de Datos y Mapa de Hooks

#### Tablas de Base de Datos

El módulo utiliza principalmente la tabla `ps_configuration` de PrestaShop para sus ajustes. Para el almacenamiento en caché, utiliza el sistema de archivos o servicios externos (Redis/Memcached). Puede crear tablas personalizadas para:

- `ps_prestaspeedcache_cache_tags`: Almacena las relaciones entre las páginas en caché y sus etiquetas asociadas (por ejemplo, IDs de producto, IDs de categoría) para una invalidación eficiente.
- `ps_prestaspeedcache_invalidation_queue`: Almacena una lista de páginas o etiquetas que deben invalidarse, procesadas asincrónicamente.
- `ps_prestaspeedcache_metrics`: Almacena métricas de rendimiento para el panel de control.

#### Tabla de Hooks Registrados

El módulo registra varios hooks para integrarse con el ciclo de vida de PrestaShop.

| Nombre del Hook | Momento de Ejecución | Propósito Técnico |
| --- | --- | --- |
| `displayHeader` | Antes de que el contenido de la página se renderice en la cabecera. | Inyección de JavaScript del front-office (por ejemplo, `dynamic.js`, `fo_debug.js`), configuración del contexto inicial de la caché. |
| `displayFooter` | Antes de la etiqueta de cierre `</body>`. | Inyección de scripts adicionales, información de depuración o finalización de operaciones de caché. |
| `displayLeftColumn` | En la columna izquierda del tema. | Potencialmente utilizado para la renderización dinámica de módulos si un módulo en la columna izquierda está marcado como dinámico. |
| `displayRightColumn` | En la columna derecha del tema. | Potencialmente utilizado para la renderización dinámica de módulos si un módulo en la columna derecha está marcado como dinámico. |
| `displayProductAdditionalInfo` | En la página del producto, debajo de la descripción del producto. | Si un módulo enganchado aquí es dinámico, su contenido se obtendrá por separado. |
| `actionFrontControllerSetMedia` | Después de que el controlador frontal haya establecido los medios (JS/CSS). | Añadir JS/CSS específicos del módulo a la página. |
| `actionFrontControllerInit` | Al comienzo de la ejecución de un controlador frontal. | Interceptar solicitudes para buscar contenido en caché o prepararse para el almacenamiento en caché. |
| `actionDispatcherBefore` | Antes de que el despachador procese la solicitud. | Intercepción temprana para servir contenido en caché o omitir el despacho. |
| `actionDispatcherAfter` | Después de que el despachador haya procesado la solicitud. | Finalizar la generación de caché para la página actual. |
| `actionObjectUpdate` | Cuando se actualiza cualquier `ObjectModel` (por ejemplo, Producto, Categoría, CMS). | Activar la invalidación de caché para las páginas afectadas. |
| `actionObjectAdd` | Cuando se añade cualquier `ObjectModel`. | Activar la invalidación de caché para las páginas potencialmente afectadas. |
| `actionObjectDelete` | Cuando se elimina cualquier `ObjectModel`. | Activar la invalidación de caché para las páginas afectadas. |
| `actionProductUpdate` | Específico para actualizaciones de productos. | Invalidación granular de caché para páginas de productos. |
| `actionCategoryUpdate` | Específico para actualizaciones de categorías. | Invalidación granular de caché para páginas de categorías. |
| `actionCmsUpdate` | Específico para actualizaciones de páginas CMS. | Invalidación granular de caché para páginas CMS. |
| `actionClearCache` | Cuando se borra la caché nativa de PrestaShop. | Sincronizar el borrado de caché del módulo con el de PrestaShop. |
| `actionModuleInstall` | Cuando se instala un módulo. | Potencialmente borrar la caché o actualizar la lista de módulos dinámicos. |
| `actionModuleUninstall` | Cuando se desinstala un módulo. | Borrar la caché o eliminar el módulo de la lista dinámica. |
| `actionAdminControllerSetMedia` | En los controladores de administración, después de que se establecen los medios. | Inyectar JS/CSS específicos de administración. |
| `actionAdminControllerPreProcess` | Antes de que un controlador de administración procese su solicitud. | Configurar el contexto de administración para el módulo. |
| `actionAdminControllerPostProcess` | Después de que un controlador de administración procese su solicitud. | Manejar el post-procesamiento para acciones de administración. |
| `actionOutputHTMLBefore` | Antes de que la salida HTML final se envíe al navegador. | Realizar la optimización HTML (minificación). |
| `actionOutputHTMLAfter` | Después de que se envía la salida HTML final. | Finalizar el almacenamiento en caché. |
| `actionAjaxDie` | Cuando una solicitud AJAX llama a `die()`. | Asegurar un manejo adecuado de la caché para las respuestas AJAX. |
| `actionGetContent` | Para la página de configuración principal del módulo. | Renderizar el formulario de configuración del módulo. |

## 5. Soporte Oficial y Actualizaciones

Para las últimas actualizaciones del módulo, correcciones de errores y soporte oficial, consulta tu cuenta de cliente en [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nuestro equipo se dedica a proporcionar asistencia integral para garantizar que tu módulo Presta Speed Cache funcione de manera óptima.
