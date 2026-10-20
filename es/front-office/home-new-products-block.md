---
title: "Bloque de nuevos productos en la página de inicio - Manual de comerciante y guía de configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop 'Bloque de nuevos productos en la página de inicio' de MyPresta.eu."
sidebar:
  label: "Bloque de nuevos productos en la página de inicio - Manual de comerciante y guía de configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Home new products block en MyPresta.eu](https://mypresta.eu/modules/front-office-features/home-new-products-block.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/front-office/home-new-products-block/)
>
> ---


# Bloque de nuevos productos en la página de inicio

## 1. Requisitos y compatibilidad

- **Versiones de PrestaShop compatibles**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilidad con PHP**: PHP 7.1 - 8.5
- **Requisitos de alojamiento**: Las extensiones PHP estándar (cURL, JSON, OpenSSL) suelen ser suficientes. No se necesitan configuraciones especiales del servidor más allá de un entorno de alojamiento estándar de PrestaShop.

## 2. Recorrido completo por la configuración (Cada ajuste agrupado por pantalla)

### 2.1 Página de configuración del módulo (Back Office > Módulos > Configurar)

Después de la instalación, haga clic en "Configurar" junto al módulo "Bloque de nuevos productos en la página de inicio" para acceder a sus ajustes.

#### Ajuste: Número de productos a mostrar

- **Qué hace este ajuste:** Este campo le permite controlar cuántos de sus productos más recientes se mostrarán en el bloque de su página de inicio.
- **Efecto de cambiar este ajuste:**
  - *Cuando se establece en un número mayor (por ejemplo, 10):* Más productos nuevos serán visibles en el bloque, dando a los clientes una selección más amplia de sus últimos artículos. Esto podría hacer que el bloque sea más largo o requiera más desplazamiento.
  - *Cuando se establece en un número menor (por ejemplo, 4):* Se mostrarán menos productos nuevos, haciendo que el bloque sea más compacto. Esto puede ser útil si tiene espacio limitado o desea destacar solo los artículos más frescos.
- **Valor recomendado:** Un buen punto de partida es `8` o `12` productos. Esto proporciona una selección decente sin abrumar la página.
- **Escenario / ejemplo de comerciante:** Si tiene una tienda de moda y añade 20 artículos nuevos cada semana, establecer esto en `12` asegura que siempre haya una buena variedad visible. Si solo añade unos pocos productos artesanales nuevos cada mes, `4` o `6` podría ser más apropiado para mantener el bloque conciso.

#### Ajuste: Mostrar en la página de inicio

- **Qué hace este ajuste:** Este es un simple interruptor de ENCENDIDO/APAGADO que controla si el "Bloque de nuevos productos en la página de inicio" es visible en la página de inicio de su tienda.
- **Efecto de cambiar este ajuste:**
  - *Cuando está habilitado (SÍ):* El bloque con sus nuevos productos aparecerá en su página de inicio, como se describe en la Sección 2.
  - *Cuando está deshabilitado (NO):* El bloque se ocultará de su página de inicio. Esto puede ser útil si desea eliminarlo temporalmente sin desinstalar el módulo, o si prefiere utilizar otros métodos para mostrar nuevos productos.
- **Valor recomendado:** `SÍ` (Habilitado). El propósito principal de este módulo es mostrar nuevos productos en la página de inicio.
- **Escenario / ejemplo de comerciante:** Podría deshabilitarlo temporalmente si está ejecutando una campaña estacional especial que requiere todo el espacio de la página de inicio para banners promocionales, y luego volver a habilitarlo una vez que la campaña haya terminado.

### 2.2 Tabla de referencia rápida de configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e impacto |
| --- | --- | --- | --- |
| Página de configuración del módulo | Número de productos a mostrar | 8-12 | Controla cuántos productos nuevos aparecen en el bloque. Un número mayor muestra más, un número menor lo hace más compacto. |
| Página de configuración del módulo | Mostrar en la página de inicio | SÍ | Alterna la visibilidad del bloque de nuevos productos en su página de inicio. |

## 3. Solución de problemas para comerciantes y preguntas frecuentes (FAQ)

**P: Mi bloque de nuevos productos no aparece en la página de inicio después de la instalación.**
R:

1. **Verifique la configuración del módulo:** Vaya a **Módulos > Gestor de módulos**, busque "Bloque de nuevos productos en la página de inicio" y haga clic en "Configurar". Asegúrese de que "Mostrar en la página de inicio" esté configurado en `SÍ`.
2. **Borrar caché:** A veces, la caché de PrestaShop impide que los cambios aparezcan inmediatamente. Vaya a **Parámetros avanzados > Rendimiento** y haga clic en "Borrar caché" en la esquina superior derecha.
3. **Verifique la posición del hook:** Aunque el módulo está diseñado para engancharse automáticamente, a veces los conflictos de temas u otros módulos pueden interferir. Vaya a **Diseño > Posiciones**. Busque `displayHome` (o `displayHomeTabContent` si su tema usa pestañas). Asegúrese de que `home-new-products-block` esté listado y habilitado dentro de uno de estos hooks. Si no, es posible que deba "Trasplantar un módulo" a `displayHome`.

**P: El bloque muestra productos antiguos, no nuevos.**
R: El módulo muestra los productos según su "fecha de adición" en PrestaShop. Asegúrese de que cuando añada nuevos productos, su fecha de creación esté correctamente establecida en la fecha actual. Si importó productos con fechas antiguas, es posible que no aparezcan como "nuevos". Es posible que deba actualizar manualmente el campo `date_add` para esos productos en su base de datos (tarea avanzada, consulte a un desarrollador) o volver a añadirlos.

**P: Quiero cambiar dónde aparece el bloque en mi página de inicio (por ejemplo, más arriba o en una columna).**
R: Puede ajustar la posición del módulo utilizando la función "Edición en vivo" incorporada de PrestaShop.

1. Vaya a **Diseño > Posiciones**.
2. Haga clic en el botón "Ejecutar edición en vivo" (normalmente en la parte superior derecha).
3. Navegue a su página de inicio.
4. Debería ver contornos alrededor de varios bloques de módulos. Busque el "Bloque de nuevos productos en la página de inicio" y arrástrelo a la posición deseada. También puede usar el botón "Trasplantar un módulo" para moverlo a un hook diferente (por ejemplo, `displayLeftColumn`, `displayRightColumn`, `displayFooter`).

**P: El bloque se ve extraño o no coincide con el estilo de mi tema.**
R: Este módulo utiliza plantillas de visualización de productos estándar de PrestaShop, que deberían heredar la mayor parte del estilo de su tema. Si se ve mal:

1. **Borrar caché:** Como se indicó anteriormente, borre la caché de su PrestaShop.
2. **Sobreescrituras del tema:** Su tema podría tener CSS específico que entre en conflicto. Esto generalmente requiere que un desarrollador web inspeccione el CSS de su sitio y, potencialmente, añada estilos personalizados al archivo `custom.css` de su tema o equivalente para anular el valor predeterminado.
3. **Actualización del módulo:** Asegúrese de tener la última versión del módulo de MyPresta.eu.

## 4. Guía para desarrolladores y webmasters (Arquitectura técnica y mapa de código)

### 4.1 Resumen de la arquitectura

El módulo "Bloque de nuevos productos en la página de inicio" es un módulo de PrestaShop sencillo que sigue la estructura de módulo estándar. Utiliza principalmente la clase `Module` para gestionar su ciclo de vida (instalación, desinstalación) y métodos `hook` para renderizar contenido en el front office. Recupera datos de productos directamente de las tablas de la base de datos central de PrestaShop, aprovechando las funcionalidades existentes de `Product` y `Category`. No hay controladores personalizados ni ObjectModels complejos, lo que lo hace ligero y fácil de integrar.

### 4.2 Controladores (`controllers/`)

- Este módulo **no** contiene ningún controlador personalizado de Front-Office o Back-Office. Toda la lógica está encapsulada dentro del archivo principal del módulo y se ejecuta a través de hooks.

### 4.3 Clases y modelos principales (`classes/`)

- Este módulo **no** contiene ninguna clase personalizada u ObjectModels en un directorio `classes/`. Se basa en las clases `Product` y `Category` principales de PrestaShop para la recuperación de datos.

### 4.4 Activos JavaScript (`views/js/`)

- Este módulo **no** incluye ningún archivo JavaScript personalizado. Cualquier comportamiento dinámico (por ejemplo, carruseles) normalmente sería manejado por el JS existente del tema o un módulo separado.

### 4.5 Hojas de estilo CSS (`views/css/`)

- Este módulo **no** incluye ningún archivo CSS personalizado. Se basa en el estilo predeterminado del tema para las listas y cuadrículas de productos. Los desarrolladores que deseen estilizar este bloque específicamente deben apuntar a su estructura HTML (por ejemplo, `div#home_new_products`) en el archivo `custom.css` de su tema o equivalente.

### 4.6 Estructura de la plantilla Smarty (`views/templates/`)

- Este módulo utiliza principalmente un único archivo de plantilla para renderizar su contenido.

  - **Plantillas de hook (`views/templates/hook/`)**:
    - `views/templates/hook/home-new-products-block.tpl`: Este es el archivo de plantilla principal responsable de renderizar el bloque de nuevos productos en la página de inicio.
      - **Hook:** Principalmente destinado a `displayHome` (o `displayHomeTabContent` en algunos temas).
      - **Propósito:** Itera a través de la variable `$products` (un array de objetos `Product`) pasada desde el método `hookDisplayHome` y muestra la imagen, el nombre, el precio y el botón "Añadir al carrito" de cada producto, típicamente usando un bucle e incluyendo una plantilla de elemento de lista de productos estándar (por ejemplo, `product-miniature.tpl` o similar, dependiendo de la versión de PrestaShop y el tema).

### 4.7 Esquema de la base de datos y mapa de hooks

- **Tablas de la base de datos**:

  - Este módulo **no** crea ninguna tabla de base de datos personalizada.
  - Almacena sus ajustes de configuración (por ejemplo, `HOME_NEW_PRODUCTS_NBR`, `HOME_NEW_PRODUCTS_DISPLAY`) en la tabla estándar `ps_configuration`.
- **Tabla de hooks registrados**:

| Nombre del Hook | Momento de ejecución | Propósito técnico |
| --- | --- | --- |
| `displayHome` | Renderiza contenido en el área principal de la página de inicio. | Muestra el bloque de nuevos productos en la página de inicio de la tienda. |
| `displayHeader` | Se ejecuta en la sección `<head>` de cada página. | Se utiliza para registrar activos (CSS/JS) si hubiera alguno, aunque este módulo no lo usa para eso. Podría usarse para metaetiquetas u otros elementos globales. |
| `displayLeftColumn` | Renderiza contenido en la barra lateral izquierda. | Permite que el bloque de nuevos productos se mueva a la columna izquierda a través de "Diseño > Posiciones". |
| `displayRightColumn` | Renderiza contenido en la barra lateral derecha. | Permite que el bloque de nuevos productos se mueva a la columna derecha a través de "Diseño > Posiciones". |
| `displayFooter` | Renderiza contenido en el pie de página de la tienda. | Permite que el bloque de nuevos productos se mueva al pie de página a través de "Diseño > Posiciones". |
| `actionProductAdd` | Se ejecuta después de añadir un nuevo producto. | Podría usarse para borrar la caché o reindexar, aunque no es utilizado explícitamente por este módulo. |
| `actionProductUpdate` | Se ejecuta después de actualizar un producto. | Podría usarse para borrar la caché o reindexar, aunque no es utilizado explícitamente por este módulo. |
| `actionProductDelete` | Se ejecuta después de eliminar un producto. | Podría usarse para borrar la caché o reindexar, aunque no es utilizado explícitamente por este módulo. |

## 5. Soporte oficial y actualizaciones

Para las últimas actualizaciones, correcciones de errores y soporte oficial para el módulo "Bloque de nuevos productos en la página de inicio", consulte su cuenta de cliente de MyPresta.eu. Puede descargar las versiones más recientes y acceder a los recursos de soporte directamente desde [MyPresta.eu](https://mypresta.eu).
"""
