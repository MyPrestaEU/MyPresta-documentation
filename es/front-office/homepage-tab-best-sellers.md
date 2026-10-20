---
title: "Pestaña de productos más vendidos en la página de inicio - Manual de comerciante y guía de configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop 'Pestaña de productos más vendidos en la página de inicio' de MyPresta.eu."
sidebar:
  label: "Pestaña de productos más vendidos en la página de inicio - Manual de comerciante y guía de configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Homepage tab best sellers en MyPresta.eu](https://mypresta.eu/modules/front-office-features/homepage-tab-best-sellers.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/front-office/homepage-tab-best-sellers/)
>
> ---


# Pestaña de productos más vendidos en la página de inicio

## 1. Requisitos y compatibilidad

- **Versiones de PrestaShop compatibles**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilidad con PHP**: PHP 7.1 - 8.5
- **Requisitos de alojamiento**: Las extensiones PHP estándar (cURL, JSON, OpenSSL) suelen ser necesarias para PrestaShop y normalmente están disponibles en cualquier entorno de alojamiento moderno.

## 2. Recorrido completo por la configuración (cada ajuste agrupado por pantalla)

### 2.1 Página de configuración del módulo (Back Office > Módulos > Configurar)

Después de la instalación, haga clic en "Configurar" junto al módulo "Pestaña de productos más vendidos en la página de inicio" en el Gestor de módulos. Será llevado a su página de configuración.

#### Número de productos a mostrar

- **Qué hace este ajuste:** Este ajuste controla cuántos productos más vendidos se mostrarán dentro de la pestaña "Más vendidos" en su página de inicio.
- **Efecto de cambiar este ajuste:**
  - *Cuando se establece en un número mayor (por ejemplo, 12):* Se mostrarán más productos en la pestaña, lo que dará a los clientes una selección más amplia de sus productos más vendidos para navegar. Esto puede ser bueno para tiendas con muchos artículos populares.
  - *Cuando se establece en un número menor (por ejemplo, 4):* Se mostrarán menos productos, creando una presentación más concisa y enfocada. Esto puede ser beneficioso para tiendas con menos productos más vendidos o cuando desea enfatizar unos pocos seleccionados.
- **Valor recomendado:** Un buen punto de partida suele ser entre **8 y 12** productos. Esto proporciona suficiente variedad sin abrumar al cliente o hacer que la página sea demasiado larga.
- **Escenario / ejemplo de comerciante:** Si tiene un catálogo grande y muchos productos que se venden constantemente bien, podría establecerlo en 10 o 12 para mostrar más de sus artículos populares. Si prefiere una página de inicio más limpia y minimalista, podría establecerlo en 6.

#### Tabla de referencia rápida de configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e impacto ## 5. Casos de uso prácticos y mejores prácticas (consejos profesionales)

1. **Aproveche la prueba social para nuevos visitantes:**
   - **Escenario:** Un nuevo cliente llega a su página de inicio. No conoce su marca ni sus productos.
   - **Consejo profesional:** La pestaña "Más vendidos" proporciona inmediatamente una prueba social, mostrándoles lo que otros clientes están comprando y amando. Asegúrese de que sus productos más vendidos tengan buenas imágenes de producto y descripciones claras. Considere la posibilidad de realizar una promoción temporal (por ejemplo, "Nuestros 5 productos más vendidos - ¡10% de descuento esta semana!") para atraer aún más la atención a esta sección.
2. **Optimice para productos de temporada y de tendencia:**
   - **Escenario:** Su tienda experimenta picos de ventas estacionales (por ejemplo, regalos navideños, ropa de verano) o tiene productos que de repente se ponen de moda.
   - **Consejo profesional:** Aunque el módulo identifica automáticamente los productos más vendidos, puede influir indirectamente en esto promocionando estratégicamente ciertos productos. Por ejemplo, durante el verano, si desea que sus trajes de baño aparezcan en "Más vendidos", asegúrese de que estén bien surtidos, tengan precios competitivos y quizás se presenten en otros esfuerzos de marketing. A medida que se vendan más, naturalmente subirán en las clasificaciones de los más vendidos y aparecerán en la pestaña.
3. **Promoción cruzada con otras secciones de la página de inicio:**
   - **Escenario:** Tiene otras secciones de productos en su página de inicio (por ejemplo, "Nuevos productos", "Productos destacados").
   - **Consejo profesional:** Utilice la pestaña "Más vendidos" como una sección complementaria. Si un producto es nuevo y se vende excepcionalmente bien, podría aparecer tanto en "Nuevos productos" como en "Más vendidos", reforzando su popularidad. Evite tener demasiados productos superpuestos si es posible, para dar a los clientes más variedad, pero no oculte un producto nuevo genuinamente más vendido solo por el bien de la variedad. La naturaleza automática del módulo se encargará de esto de forma natural.

## 3. Solución de problemas para comerciantes y preguntas frecuentes (FAQ)

**P1: Mi pestaña "Más vendidos" no aparece en la página de inicio.**

- **R:** Primero, asegúrese de que el módulo esté instalado y habilitado en **Módulos > Gestor de módulos**. Luego, revise su configuración. Si la pestaña sigue sin aparecer, podría ser un problema de caché. Vaya a **Parámetros avanzados > Rendimiento** y haga clic en "Borrar caché" (o "Borrar caché de Smarty" en versiones anteriores). Si su tema está muy personalizado, es posible que no se esté enganchando correctamente a `displayHomeTab` y `displayHomeTabContent`. En este caso, es posible que deba consultar con el desarrollador de su tema o un experto en PrestaShop.

**P2: Los productos de la pestaña "Más vendidos" no parecen ser mis productos más vendidos reales.**

- **R:** El módulo se basa en los datos de ventas internos de PrestaShop para determinar los productos más vendidos.
  - Asegúrese de tener datos de ventas reales para los productos. Las tiendas nuevas o las tiendas con muy pocas ventas podrían no tener suficientes datos para una lista significativa de "productos más vendidos".
  - El cálculo de los "productos más vendidos" suele basarse en el número de unidades vendidas durante un período. Podría llevar algún tiempo que las ventas recientes se reflejen en la lista.
  - Borre la caché de su PrestaShop (**Parámetros avanzados > Rendimiento > Borrar caché**) para asegurarse de que se estén extrayendo los datos más recientes.

**P3: ¿Con qué frecuencia se actualiza la lista de "Más vendidos"?**

- **R:** La lista de los productos más vendidos es generada dinámicamente por PrestaShop basándose en los datos de ventas. Se actualiza automáticamente a medida que se realizan y procesan los pedidos. Sin embargo, para que los cambios sean visibles en el front office, es posible que deba borrar la caché de su PrestaShop, especialmente si tiene una caché agresiva habilitada.

**P4: ¿Puedo cambiar el título de la pestaña (por ejemplo, de "Más vendidos" a "Nuestras mejores selecciones")?**

- **R:** Sí, puede. El título de la pestaña suele ser una cadena traducible dentro del módulo.
  1. Vaya a **Internacional > Traducciones**.
  2. Seleccione "Traducciones de módulos instalados".
  3. Elija su tema.
  4. Seleccione su idioma.
  5. Busque el módulo "Pestaña de productos más vendidos en la página de inicio" en la lista.
  6. Localice la cadena de texto para el título de la pestaña (por ejemplo, "Más vendidos") y cámbiela por el texto deseado. Recuerde guardar sus cambios.

**P5: Los productos se ven extraños o desalineados en la pestaña.**

- **R:** Esto suele ser un conflicto de estilo CSS con su tema de PrestaShop. El módulo proporciona los datos del producto, pero su tema es responsable de cómo se muestran esos datos (diseño, fuentes, colores, tamaños de imagen).
  - Asegúrese de que su tema esté actualizado.
  - Intente borrar la caché de su PrestaShop (**Parámetros avanzados > Rendimiento**).
  - Si el problema persiste, es posible que deba añadir CSS personalizado a su tema para anular el estilo predeterminado del módulo o del tema. Esto suele requerir un desarrollador web.

## 4. Guía para desarrolladores y webmasters (arquitectura técnica y mapa de código)

Esta sección proporciona una descripción técnica detallada del módulo "Pestaña de productos más vendidos en la página de inicio" para desarrolladores y webmasters.

### 4.1 Descripción general de la arquitectura

El módulo `Homepage tab best sellers` es un módulo de PrestaShop sencillo diseñado para integrarse sin problemas con el sistema de pestañas de la página de inicio. Sigue una estructura de módulo de PrestaShop clásica, utilizando principalmente la clase `Module` y los hooks del front office. No introduce controladores, modelos o JavaScript/CSS complejos personalizados, sino que se basa en las funcionalidades principales de PrestaShop para la recuperación de datos de productos y el estilo de tema existente para la presentación. Su lógica principal reside en el archivo `homebestsellerstab.php`, que gestiona la configuración y el registro de hooks.

### 4.2 Controladores (`controllers/`)

- **Controladores de Front Office**: Ninguno. El contenido del front office del módulo se renderiza directamente a través de plantillas Smarty enganchadas a `displayHomeTab` y `displayHomeTabContent`.
- **Controladores de administración de Back Office**: Ninguno. La configuración del módulo se gestiona mediante el método `getContent()` dentro de la clase principal del módulo.

### 4.3 Clases y modelos principales (`classes/`)

- Ninguno. El módulo no define ninguna clase personalizada ni extiende `ObjectModel`. Aprovecha las clases principales `Product` y `ProductSale` de PrestaShop (o mecanismos internos similares) para recuperar datos de productos más vendidos.

### 4.4 Activos de JavaScript (`views/js/`)

- Ninguno. El módulo no incluye ningún archivo JavaScript personalizado. Se espera que cualquier comportamiento interactivo (como el cambio de pestañas) sea manejado por el JavaScript existente del tema de PrestaShop.

### 4.5 Hojas de estilo CSS (`views/css/`)

- Ninguno. El módulo no incluye ningún archivo CSS personalizado. El estilo de la pestaña y las listas de productos dentro de ella dependen completamente del tema de PrestaShop activo. Los desarrolladores deben inspeccionar el HTML generado y apuntar a las clases/ID relevantes en el CSS de su tema para personalizar la apariencia.

### 4.6 Estructura de la plantilla Smarty (`views/templates/`)

El módulo utiliza dos archivos de plantilla Smarty, ambos ubicados en el directorio `views/templates/hook/`, para renderizar su contenido en el front office.

- **`views/templates/hook/tab.tpl`**

  - **Hook**: `displayHomeTab`
  - **Propósito**: Esta plantilla es responsable de renderizar el elemento de pestaña clicable real en la página de inicio. Normalmente contiene la etiqueta `<li>` o `<a>` que representa la pestaña "Más vendidos", incluido su título traducible.
  - **Salida**: Un elemento de pestaña que, al hacer clic, revela el contenido renderizado por `homebestsellerstab.tpl`.
- **`views/templates/hook/homebestsellerstab.tpl`**

  - **Hook**: `displayHomeTabContent`
  - **Propósito**: Esta plantilla renderiza la lista o cuadrícula real de productos más vendidos cuando la pestaña "Más vendidos" está activa. Recibe una matriz de datos de productos de la lógica PHP del módulo.
  - **Salida**: Marcado HTML para mostrar productos (por ejemplo, contenedores `div`, imágenes de productos, nombres, precios, botones de añadir al carrito). Normalmente itera sobre la variable `$products` que se le pasa.

### 4.7 Esquema de la base de datos y mapa de hooks

- **Tablas de la base de datos**: El módulo no crea ninguna tabla de base de datos personalizada. Almacena su configuración (por ejemplo, `HOME_BEST_NBR`) en la tabla `ps_configuration` de PrestaShop.
- **Tabla de Hooks registrados**:

| Nombre del Hook | Momento de ejecución | Propósito técnico La clave de configuración `HOME_BEST_NBR` se utiliza para almacenar el número de productos a mostrar.
`PS_LANG_DEFAULT` y `PS_BO_ALLOW_EMPLOYEE_FORM_LANG` son claves de configuración principales de PrestaShop que se utilizan para gestionar la configuración del idioma predeterminado y del idioma del formulario de empleado. Estas no son configuradas directamente por el módulo, pero se acceden para el contexto.

## 5. Soporte oficial y actualizaciones

Para obtener las últimas actualizaciones, correcciones de errores y soporte oficial para el módulo "Pestaña de productos más vendidos en la página de inicio", consulte su cuenta de cliente en [MyPresta.eu](https://mypresta.eu). Puede descargar la versión más reciente del módulo desde su historial de pedidos. Para asistencia técnica o consultas, utilice los canales de soporte proporcionados en el sitio web de MyPresta.eu.
