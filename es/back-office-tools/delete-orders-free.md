---
title: "Delete Orders Free - Manual de Comerciante y Guía de Configuración"
description: "Manual de usuario completo, guía de configuración pantalla por pantalla y referencia para desarrolladores del módulo Delete Orders Free para PrestaShop de MyPresta.eu."
sidebar:
  label: "Delete Orders Free - Manual de Comerciante y Guía de Configuración"
---

> ⚠️ **Notice:** This is the documentación oficial del módulo de PrestaShop.
> - 🛒 **Puede encontrar la especificación comercial completa, el registro de cambios y las opciones de compra en la página oficial del producto en MyPresta.eu:** [Comprar módulo Delete Orders Free en MyPresta.eu](https://mypresta.eu/modules/administration-tools/delete-orders-free.html)
> - 🌐 **Centro de documentación oficial en línea:** [Leer la documentación interactiva en MyPresta.eu](https://mypresta.eu/docs/es/back-office-tools/delete-orders-free/)
>
> ---


# Delete Orders Free

## 1. Requisitos y Compatibilidad

- **Versiones de PrestaShop Compatibles**: PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilidad PHP**: PHP 7.1 - 8.5
- **Requisitos de Alojamiento**: Las extensiones PHP estándar (cURL, JSON, OpenSSL) suelen ser suficientes y generalmente están habilitadas por defecto en la mayoría de los entornos de alojamiento.

## 2. Recorrido Completo por la Configuración (Cada Ajuste Agrupado por Pantalla)

### 2.1 Página de Configuración del Módulo (Back Office > Módulos > Configurar)

Después de la instalación, al hacer clic en "Configurar" accederás a la página principal de configuración del módulo. Esta página gestiona principalmente las notificaciones de actualización del propio módulo.

-   **Qué hace este ajuste:** Esta sección gestiona la capacidad del módulo para buscar actualizaciones y mostrar notificaciones.
-   **Efecto de cambiar este ajuste:**
    -   *Cuando está habilitado:* El módulo buscará periódicamente versiones más recientes en MyPresta.eu. Si hay una actualización disponible, podría aparecer una notificación en tu back office de PrestaShop, invitándote a descargar e instalar la última versión. Esto asegura que siempre tengas la versión más segura y con más funciones del módulo.
    -   *Cuando está deshabilitado:* El módulo no buscará actualizaciones automáticamente. Tendrías que visitar manualmente MyPresta.eu para buscar nuevas versiones. Aunque esto podría reducir ligeramente las solicitudes al servidor, significa que podrías perderte actualizaciones importantes o correcciones de errores.
-   **Valor recomendado:** **Habilitado (SÍ)**. Mantener esto habilitado asegura que siempre estés informado sobre las últimas mejoras y parches de seguridad para el módulo.
-   **Escenario / ejemplo de comerciante:** Quieres ser notificado si se lanza una nueva versión de "Delete Orders Free" que corrige un error o añade una nueva función. Mantener esto habilitado asegura que verás una notificación en tu panel de administración de PrestaShop.

### 2.2 Pantallas de Administración Dedicadas y Vistas de Controlador

#### 2.2.1 Pestaña Eliminar Pedidos (Back Office > Pedidos > Eliminar Pedidos)

Esta es la interfaz principal para la funcionalidad del módulo.

-   **Nombre de la Pantalla y Ubicación del Menú:** Puedes acceder a esta pantalla navegando a **Pedidos > Eliminar Pedidos** en el menú de tu back office de PrestaShop.
-   **Acciones y Ajustes Disponibles:**
    -   Al entrar en esta pestaña, verás una lista de todos los pedidos en tu tienda PrestaShop, similar a la lista estándar de "Pedidos".
    -   Cada pedido en la lista tendrá un botón o icono dedicado **"Eliminar"** (a menudo un icono de papelera) junto a él.
    -   **Eliminar un pedido:** Al hacer clic en el botón "Eliminar" junto a cualquier pedido, este se eliminará de forma inmediata y permanente de tu base de datos. Esta acción es irreversible.
-   **Efecto de los cambios:**
    -   Cuando haces clic en "Eliminar" para un pedido, el registro del pedido, junto con todos los datos asociados (como detalles del pedido, mensajes del cliente relacionados con ese pedido, facturas y, potencialmente, movimientos de stock si el estado del pedido estaba configurado para afectar el stock) se eliminarán de tu base de datos de PrestaShop.
    -   El pedido ya no aparecerá en tu lista de "Pedidos", ni se incluirá en ningún informe o estadística de ventas.
-   **Flujo de trabajo recomendado para la gestión diaria de la tienda:**
    1.  Revisa regularmente tu lista de "Pedidos" en busca de pedidos de prueba, pedidos fraudulentos o pedidos que fueron completamente cancelados y que ya no necesitan ser rastreados.
    2.  Navega a **Pedidos > Eliminar Pedidos**.
    3.  Identifica cuidadosamente los pedidos que deseas eliminar.
    4.  Haz clic en el botón "Eliminar" junto a cada pedido específico que deseas eliminar.
    5.  Confirma la eliminación si se te solicita.
    6.  **Importante:** Ten extrema precaución ya que esta acción es permanente y no se puede deshacer. Se recomienda encarecidamente realizar una copia de seguridad de la base de datos antes de eliminar un gran número de pedidos.

#### 2.2.2 Index.php (deleteordersfree/controllers/admin/index.php)

Este archivo es un marcador de posición de controlador estándar de PrestaShop y, por lo general, no presenta una pantalla directa y configurable para el comerciante. Su propósito suele ser redirigir a la configuración principal del módulo o a una pestaña de administración específica. En el contexto de este módulo, es probable que asegure que la navegación a la ruta base de administración del módulo te dirija correctamente al controlador `deleteorderstab`.

### 2.3 Tabla de Referencia Rápida de Configuración

| Pantalla / Vista | Ajuste / Opción | Predeterminado / Recomendado | Propósito e Impacto |
| :--- | :--- | :--- | :---```php
```php
<?php

declare(strict_types=1);

namespace MyPresta\DeleteOrdersFree\Controller;

use MyPresta\DeleteOrdersFree\Service\OrderDeletionService;
use PrestaShopBundle\Controller\Admin\FrameworkController;
use Symfony\Component\HttpFoundation\RedirectResponse;
use Symfony\Component\HttpFoundation\Request;
use Symfony\Component\HttpFoundation\Response;

class AdminDeleteOrdersTabController extends FrameworkController
{
    /**
     * @var OrderDeletionService
     */
    private $orderDeletionService;

    public function __construct(OrderDeletionService $orderDeletionService)
    {
        parent::__construct();
        $this->orderDeletionService = $orderDeletionService;
    }

    /**
     * Renders the list of orders with delete buttons.
     *
     * @param Request $request
     *
     * @return Response
     */
    public function indexAction(Request $request): Response
    {
        // Get all orders (you might want to add pagination and filtering here for large stores)
        $orders = $this->orderDeletionService->getAllOrders();

        return $this->render('@Modules/deleteordersfree/views/templates/admin/delete_orders_tab.html.twig', [
            'orders' => $orders,
            'layoutHeaderToolbarBtn' => $this->getToolbarButtons(),
            'layoutTitle' => $this->trans('Delete Orders', 'Modules.Deleteordersfree.Admin'),
        ]);
    }

    /**
     * Handles the deletion of a single order.
     *
     * @param Request $request
     * @param int $orderId
     *
     * @return RedirectResponse
     */
    public function deleteOrderAction(Request $request, int $orderId): RedirectResponse
    {
        try {
            $this->orderDeletionService->deleteOrder($orderId);
            $this->addFlash('success', $this->trans('Order %orderId% deleted successfully.', 'Modules.Deleteordersfree.Admin', ['%orderId%' => $orderId]));
        } catch (\Exception $e) {
            $this->addFlash('error', $this->trans('Failed to delete order %orderId%: %error%', 'Modules.Deleteordersfree.Admin', ['%orderId%' => $orderId, '%error%' => $e->getMessage()]));
        }

        return $this->redirectToRoute('mypresta_deleteordersfree_delete_orders_tab');
    }

    /**
     * Get toolbar buttons for the header.
     *
     * @return array
     */
    private function getToolbarButtons(): array
    {
        return [
            'back' => [
                'href' => $this->generateUrl('admin_orders_index'),
                'desc' => $this->trans('Back to Orders', 'Modules.Deleteordersfree.Admin'),
                'icon' => 'arrow-left',
            ],
        ];
    }
}
