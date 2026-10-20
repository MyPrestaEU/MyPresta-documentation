---
title: "Peeling Corner Banner - Manual de Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo Peeling Corner Banner para PrestaShop de MyPresta.eu."
sidebar:
  label: "Peeling Corner Banner - Manual de Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Peeling Corner Banner en MyPresta.eu](https://mypresta.eu/modules/advertising-and-marketing/peeling-corner-banner.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/advertising-marketing/peeling-corner-banner/)
>
> ---


# Peeling Corner Banner

## 1. Requisitos y Compatibilidad

- **Versiones de PrestaShop Compatibles**: PrestaShop 1.4.x, 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilidad PHP**: PHP 5.6 - 8.5
- **Requisitos de Alojamiento**: Las extensiones PHP estándar (cURL, JSON, OpenSSL) suelen ser suficientes. Normalmente no se necesitan configuraciones especiales del servidor.

## 2. Recorrido Completo por la Configuración (Cada Ajuste Agrupado por Pantalla)

### 2.1 Página de Configuración del Módulo (Back Office > Módulos > Configurar)

Después de instalar el módulo, haz clic en "Configurar" para acceder a sus ajustes. Aquí es donde personalizarás la apariencia y el comportamiento de tu banner despegable.

#### **Imagen para la Esquina (Imagen Pequeña)**

- **Qué hace este ajuste:** Esta es la pequeña imagen que aparece en la esquina curvada de tu página. Es el avance inicial que capta la atención del cliente.
- **Efecto de cambiar este ajuste:**
  - *Cuando se sube una imagen:* Esta imagen se mostrará en la pequeña esquina curvada.
  - *Cuando no se sube ninguna imagen:* La esquina podría aparecer en blanco o usar un estilo predeterminado, lo cual es menos efectivo.
- **Valor recomendado:** Sube una imagen pequeña y atractiva (por ejemplo, un icono pequeño, una etiqueta de "Oferta" o un fragmento de logotipo) que insinúe la promoción sin revelarlo todo.
- **Escenario / ejemplo de comerciante:** Estás realizando una venta de verano. Podrías subir una pequeña imagen de un icono de sol o una pequeña insignia de "OFERTA" a este ajuste.

#### **Imagen para el Banner (Imagen Grande)**

- **Qué hace este ajuste:** Esta es la imagen principal del banner que se revela cuando un cliente pasa el ratón por encima de la esquina. Aquí es donde debe estar tu mensaje principal, imagen de producto o llamada a la acción.
- **Efecto de cambiar este ajuste:**
  - *Cuando se sube una imagen:* Esta imagen más grande se mostrará cuando la esquina se despegue.
  - *Cuando no se sube ninguna imagen:* El área despegada estará vacía, haciendo que el módulo sea ineficaz.
- **Valor recomendado:** Sube una imagen clara y atractiva que contenga tu mensaje promocional completo, una foto de producto o una fuerte llamada a la acción. Asegúrate de que tenga el tamaño adecuado para un banner (por ejemplo, 200-300px de ancho, altura similar).
- **Escenario / ejemplo de comerciante:** Siguiendo el ejemplo de la venta de verano, esta imagen sería un banner completo anunciando "¡Venta de Verano! ¡Hasta 50% de Descuento en Toda la Ropa de Baño!" con atractivas fotos de productos.

#### **Enlace para el Banner**

- **Qué hace este ajuste:** Esta es la URL (dirección web) a la que se redirigirá a los clientes cuando hagan clic en el banner revelado.
- **Efecto de cambiar este ajuste:**
  - *Cuando se introduce una URL válida:* Al hacer clic en el banner, el cliente será llevado a esa página.
  - *Cuando se deja vacío o se introduce una URL no válida:* Al hacer clic en el banner, podría no hacer nada o llevar a una página de error, frustrando a los clientes.
- **Valor recomendado:** Proporciona siempre una URL completa y válida (por ejemplo, `https://tutienda.com/categoria-venta-verano`).
- **Escenario / ejemplo de comerciante:** Enlazarías esto a tu página de categoría dedicada a la "Venta de Verano" o a una página de producto específica que quieras destacar.

#### **Posición del Banner**

- **Qué hace este ajuste:** Esto controla en qué esquina de tu sitio web aparece el banner despegable.
- **Efecto de cambiar este ajuste:**
  - *Izquierda:* El banner aparecerá en la esquina superior izquierda de la ventana del navegador.
  - *Derecha:* El banner aparecerá en la esquina superior derecha de la ventana del navegador.
- **Valor recomendado:** Elige la esquina que mejor se adapte al diseño de tu sitio web y no oculte elementos importantes. "Derecha" suele ser un buen valor predeterminado, ya que es menos común que la navegación o los logotipos estén allí.
- **Escenario / ejemplo de comerciante:** Si tu logotipo principal y la navegación están a la izquierda, elegirías "Derecha" para evitar el desorden visual.

#### **Habilitar/Deshabilitar Módulo**

- **Qué hace este ajuste:** Este es un interruptor maestro para activar o desactivar la función completa del banner despegable sin desinstalar el módulo.
- **Efecto de cambiar este ajuste:**
  - *Habilitado:* El banner despegable será visible en tu front office según tus otros ajustes.
  - *Deshabilitado:* El banner despegable no aparecerá en tu front office.
- **Valor recomendado:** "Habilitado" cuando quieras usar el banner, "Deshabilitado" si necesitas ocultarlo temporalmente para mantenimiento o durante períodos específicos.
- **Escenario / ejemplo de comerciante:** Has terminado tu promoción navideña y quieres ocultar temporalmente el banner hasta tu próxima campaña. Lo deshabilitarías aquí.

### 2.2 Tabla de Referencia Rápida de Configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| --- | --- | --- | --- |
| Configuración del Módulo | Imagen para la Esquina | Subir pequeña imagen de avance | Pequeña imagen en la esquina curvada. Capta la atención. |
| Configuración del Módulo | Imagen para el Banner | Subir imagen promocional más grande | Imagen principal del banner revelada al pasar el ratón. Contiene el mensaje principal. |
| Configuración del Módulo | Enlace para el Banner | URL completa (ej., `https://tutienda.com/promo`) | URL de destino cuando se hace clic en el banner. Dirige el tráfico. |
| Configuración del Módulo | Posición del Banner | Derecha | En qué esquina de la pantalla aparece el banner (Izquierda/Derecha). |
| Configuración del Módulo | Habilitar/Deshabilitar Módulo | Habilitado | Interruptor maestro para mostrar u ocultar el banner en la tienda. |

## 3. Solución de Problemas para Comerciantes y Preguntas Frecuentes (FAQ)

**P: Mi banner no aparece después de la configuración. ¿Qué debo hacer?**
R:

1. **Verifica "Habilitar/Deshabilitar Módulo":** Asegúrate de que el módulo esté habilitado en su configuración.
2. **Verifica las Cargas de Imágenes:** Asegúrate de que tanto "Imagen para la Esquina" como "Imagen para el Banner" se hayan subido correctamente.
3. **Borrar Caché:** Ve a **Parámetros avanzados > Rendimiento** en el back office de tu PrestaShop y haz clic en "Borrar caché" (o "Borrar caché de Smarty" en versiones anteriores). A veces, los archivos antiguos en caché impiden que aparezca el nuevo contenido del módulo.
4. **Hook del Módulo:** El módulo debería engancharse automáticamente a `displayHeader`. Si no aparece, asegúrate de que esté correctamente enganchado. Puedes verificar esto en **Diseño > Posiciones** (o **Módulos > Posiciones**). Busca `peelingcornerbanner` y confirma que está asociado con `displayHeader`.

**P: Las imágenes del banner se ven borrosas o estiradas.**
R: Esto generalmente significa que las imágenes que subiste no están optimizadas para el tamaño de visualización del banner.

1. **Dimensiones de la Imagen:** Verifica el tamaño real del banner cuando se despega (es posible que necesites usar las herramientas de desarrollador de tu navegador). Luego, cambia el tamaño de tu "Imagen para el Banner" para que coincida con estas dimensiones o sea ligeramente más grande, asegurando una buena calidad.
2. **Tamaño del Archivo:** Si bien la calidad es importante, mantén los tamaños de archivo de imagen lo más pequeños posible (menos de 100-200KB) para asegurar una carga rápida de la página. Utiliza herramientas como TinyPNG u optimizadores de imágenes en línea.

**P: El banner aparece, pero al hacer clic no hace nada.**
R:

1. **Verifica "Enlace para el Banner":** Vuelve a la configuración del módulo y verifica la URL que introdujiste para el enlace del banner. Asegúrate de que sea una URL completa y válida (por ejemplo, `https://www.tutienda.com/categoria/producto.html`).
2. **Prueba el Enlace:** Copia y pega el enlace directamente en tu navegador para asegurarte de que funciona correctamente fuera del módulo.

**P: El banner se superpone con otros elementos de mi página.**
R:

1. **Cambiar Posición:** Intenta cambiar la "Posición del Banner" de Izquierda a Derecha (o viceversa) en la configuración del módulo.
2. **Conflictos de Tema:** Si cambiar la posición no ayuda, podría ser un conflicto con el CSS de tu tema específico de PrestaShop. Esto podría requerir que un webmaster ajuste el CSS del módulo o del tema (consulta la Sección 7 para detalles de desarrollador).

**P: ¿Puedo tener varios banners despegables?**
R: No, este módulo está diseñado para mostrar un solo banner despegable a la vez. Si necesitas varios, tendrías que duplicar y modificar el módulo, lo que requiere experiencia de desarrollador.

## 4. Guía para Desarrolladores y Webmasters (Arquitectura Técnica y Mapa de Código)

Esta sección es estrictamente para desarrolladores, webmasters de tiendas y agencias técnicas que mantienen o extienden la tienda.

### 4.1 Resumen de la Arquitectura

El módulo Peeling Corner Banner (`pcb`) es un módulo de PrestaShop sencillo diseñado principalmente para inyectar un efecto visual impulsado por JavaScript en el front-office. Sigue una estructura básica de módulo de PrestaShop, utilizando la clase `Module` para la instalación, desinstalación y configuración (`getContent()`). La funcionalidad principal se basa en un archivo JavaScript personalizado (`peelback.js`) que maneja la manipulación del DOM y la animación, y una plantilla Smarty (`header.tpl`) para renderizar la estructura HTML inicial en el hook `displayHeader`. Los ajustes de configuración se almacenan en `ps_configuration`.

### 4.2 Controladores (`controllers/`)

- No hay Controladores de Front-Office personalizados.
- No hay Controladores de Administración de Back-Office personalizados.
  La configuración del módulo se maneja directamente dentro del método `getContent()` de la clase principal del módulo.

### 4.3 Clases y Modelos Principales (`classes/`)

- No hay clases personalizadas ni definiciones de `ObjectModel`.
  Toda la configuración se gestiona a través de `Configuration::get()` y `Configuration::updateValue()`.

### 4.4 Activos JavaScript (`views/js/`)

- `pcb/peelback.js`
  - **Alcance:** Front-office.
  - **Descripción:** Este es el archivo JavaScript principal responsable de la animación del banner de esquina despegable. Probablemente inicializa un plugin de jQuery o un script personalizado que:
    - Detecta la presencia de la estructura HTML del banner (por ejemplo, un `div` con un ID específico como `#peelback`).
    - Adjunta oyentes de eventos, principalmente `mouseover` y `mouseout`, al elemento de la esquina.
    - En `mouseover`, anima la imagen del banner más grande para que "se despegue" a la vista (por ejemplo, cambiando propiedades CSS como `width`, `height`, `top`, `left`, `z-index`).
    - En `mouseout`, anima el banner de vuelta a su estado inicial curvado.
    - Maneja el evento de clic en el banner para redirigir a la URL configurada.
    - Probablemente utiliza la función `animate()` de jQuery para transiciones suaves.

### 4.5 Hojas de Estilo CSS (`views/css/`)

- No se encuentran archivos CSS dedicados en el archivo del módulo.
  Esto implica que el estilo del banner (posición inicial, dimensiones, z-index, etc.) es:
  1. Inyectado directamente a través de estilos en línea dentro de la plantilla `header.tpl`.
  2. Manejado completamente por JavaScript, que establece dinámicamente las propiedades CSS.
  3. Se basa en un estilo de navegador predeterminado mínimo o espera que el tema proporcione restablecimientos básicos.
     Los desarrolladores que deseen personalizar la apariencia deberán inspeccionar el HTML y JavaScript generados en busca de estilos en línea o clases/estilos aplicados dinámicamente.

### 4.6 Estructura de Plantillas Smarty (`views/templates/`)

- **Plantillas de hook (`views/templates/hook/`)**:
  - `pcb/header.tpl`
    - **Hook:** `displayHeader` (o `displayTop` en versiones anteriores, pero `displayHeader` es el estándar para inyectar elementos globales).
    - **Salida:** Esta plantilla renderiza la estructura HTML inicial para el banner despegable. Típicamente incluye:
      - Un `div` contenedor para todo el banner.
      - Una etiqueta `img` para la pequeña imagen de la esquina.
      - Una etiqueta `img` para la imagen del banner más grande (inicialmente oculta o parcialmente oculta).
      - Una etiqueta `<a>` que envuelve estas imágenes, enlazada a la URL configurada.
      - Probablemente utilizará variables Smarty pasadas desde el método `hookDisplayHeader()` del módulo para generar las URL de las imágenes, la URL del enlace y la posición del banner (izquierda/derecha).
      - Puede contener etiquetas `<style>` en línea o depender de `peelback.js` para aplicar estilos dinámicamente.

### 4.7 Esquema de Base de Datos y Mapa de Hooks

- **Tablas de Base de Datos**:

  - El módulo no crea tablas SQL personalizadas.
  - Los ajustes de configuración se almacenan en la tabla `ps_configuration` (o prefijo `_configuration`) con claves como:
    - `PCB_CORNER_IMAGE` (ruta a la pequeña imagen de la esquina)
    - `PCB_BANNER_IMAGE` (ruta a la imagen grande del banner)
    - `PCB_BANNER_LINK` (la URL para el banner)
    - `PCB_BANNER_POSITION` (por ejemplo, 'left' o 'right')
    - `PCB_ENABLED` (1 para habilitado, 0 para deshabilitado)
- **Tabla de Hooks Registrados**:

| Nombre del Hook | Momento de Ejecución | Propósito Técnico |
| --- | --- | --- |
| `displayHeader` | Se ejecuta en la sección `<head>` de cada página. | Inyecta la estructura HTML necesaria para el banner y registra el script `peelback.js`. |
| `actionFrontControllerSetMedia` | Se ejecuta cuando se configuran los medios (JS/CSS) para un controlador frontal. | (Utilizado implícitamente por `displayHeader` o `hookDisplayHeader` para registrar JS/CSS, aunque no se lista explícitamente como un hook separado en el método `install()` del módulo, es como PrestaShop maneja el registro de medios). |

## 5. Soporte Oficial y Actualizaciones

Para las últimas actualizaciones, correcciones de errores y soporte profesional para el módulo Peeling Corner Banner, consulta tu cuenta de cliente en [MyPresta.eu](https://mypresta.eu/my-account/orders/). Nuestro equipo se dedica a garantizar el buen funcionamiento y la mejora continua de nuestros módulos.
