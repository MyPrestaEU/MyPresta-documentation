---
title: "Pestaña de nuevos productos en la página de inicio - Manual del Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo de PrestaShop 'Pestaña de nuevos productos en la página de inicio' de MyPresta.eu."
sidebar:
  label: "Pestaña de nuevos productos en la página de inicio"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Homepage tab new products en MyPresta.eu](https://mypresta.eu/modules/front-office-features/homepage-tab-new-products.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/front-office/homepage-tab-new-products/)
>
> ---


# Pestaña de nuevos productos en la página de inicio

## 1. Requisitos y Compatibilidad
- **Versiones de PrestaShop compatibles**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilidad con PHP**: PHP 7.1 - 8.5
- **Requisitos de alojamiento**: Extensiones PHP estándar (cURL, JSON, OpenSSL).

## 2. Recorrido Completo por la Configuración (Cada Ajuste Agrupado por Pantalla)

### 2.1 Página de Configuración del Módulo (Back Office > Módulos > Configurar)
Después de la instalación, haga clic en "Configurar" junto al módulo "Pestaña de nuevos productos en la página de inicio" en el Gestor de Módulos. Será llevado a la pantalla de configuración principal.

#### **Número de productos a mostrar**
-   **Qué hace esta configuración:** Controla cuántos de sus productos más recientes se mostrarán en la pestaña "Nuevos Productos" de su página de inicio.
-   **Efecto de cambiar esta configuración:**
    -   *Cuando se establece un número mayor (por ejemplo, 12):* Más productos nuevos serán visibles para los clientes sin que necesiten navegar a una página completa de "Nuevos Productos". Esto puede ser excelente para tiendas con un alto volumen de nuevas llegadas.
    -   *Cuando se establece un número menor (por ejemplo, 4):* Se mostrarán menos productos, lo que resultará en un aspecto más limpio y menos saturado. Esto podría ser preferible si desea destacar solo los artículos más frescos o tiene espacio limitado.
-   **Valor recomendado:** Comience con `8` o `12`. Ajuste según el diseño de su tema y la cantidad de productos que suele añadir.
-   **Escenario / ejemplo de comerciante:** Si tiene una tienda de moda y añade 20 artículos nuevos semanalmente, establecer esto en `12` asegura que una buena selección sea siempre visible. Si vende productos de alto valor y nicho y solo añade 2-3 artículos nuevos mensualmente, `4` podría ser suficiente para evitar espacios vacíos.

#### **Clases de la lista de productos**
-   **Qué hace esta configuración:** Esta configuración avanzada le permite añadir clases CSS personalizadas al contenedor que alberga la lista de nuevos productos. Se utiliza principalmente con fines de estilo, a menudo para integrarse sin problemas con el diseño específico del tema de su PrestaShop.
-   **Efecto de cambiar esta configuración:**
    -   *Cuando se añaden clases (por ejemplo, `product-grid-container my-custom-style`):* El CSS de su tema o su CSS personalizado pueden entonces apuntar a estas clases para aplicar un estilo específico (por ejemplo, cambiar el diseño de columnas, el espaciado, los tamaños de fuente, los colores) a la lista de nuevos productos.
    -   *Cuando se deja vacío:* El módulo utilizará su estilo predeterminado o heredará los estilos de la lista general de productos de su tema.
-   **Valor recomendado:** Déjelo vacío a menos que usted o su desarrollador web necesiten aplicar un estilo personalizado específico a la lista de productos. Si no está seguro, no cambie esta configuración.
-   **Escenario / ejemplo de comerciante:** Su tema muestra cuadrículas de productos con 3 columnas, pero desea que la pestaña "Nuevos Productos" muestre 4 columnas. Su desarrollador web podría indicarle que añada una clase como `col-lg-3` (si su tema utiliza clases de cuadrícula de Bootstrap) aquí, y luego añada CSS personalizado para que funcione.

### 2.2 Tabla de Referencia Rápida de Configuración

| Pantalla / Vista | Ajuste / Opción            | Predeterminado / Recomendado | Propósito e Impacto |
|---|---|---|---|
| Página de Configuración del Módulo | Número de productos a mostrar | 8 o 12 | Controla cuántos productos nuevos se muestran en la pestaña. |
| Página de Configuración del Módulo | Clases de la lista de productos | Vacío | Permite añadir clases CSS personalizadas para el estilo de la lista de productos. |
