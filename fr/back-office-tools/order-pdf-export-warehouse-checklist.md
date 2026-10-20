---
title: "Export PDF de commande et liste de contrôle d'entrepôt - Manuel du marchand et guide de configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop Export PDF de commande et liste de contrôle d'entrepôt par MyPresta.eu."
sidebar:
  label: "Export PDF de commande et liste de contrôle d'entrepôt - Manuel du marchand et guide de configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Order PDF Export & Warehouse Checklist sur MyPresta.eu](https://mypresta.eu/modules/administration-tools/order-pdf-export-warehouse-checklist.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/back-office-tools/order-pdf-export-warehouse-checklist/)
>
> ---


# Export PDF de commande et liste de contrôle d'entrepôt

## 1. Exigences et compatibilité

- **Versions PrestaShop prises en charge** : PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilité PHP** : PHP 7.1 - 8.5
- **Exigences d'hébergement** : Les extensions PHP standard (cURL, JSON, OpenSSL) sont requises, qui sont généralement disponibles sur la plupart des environnements d'hébergement compatibles PrestaShop.

## 2. Guide de configuration complet (chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

Pour accéder à cet écran, naviguez vers **Modules > Gestionnaire de modules**, recherchez « Export PDF de commande et liste de contrôle d'entrepôt », et cliquez sur « Configurer ».

#### **Modèle PDF**

-   **Ce que fait ce paramètre :** Cela vous permet de choisir le design visuel et la mise en page des documents PDF générés par le module. Vous pouvez choisir parmi une variété de modèles pré-conçus.
-   **Effet de la modification de ce paramètre :**
    *   *Lorsqu'il est défini sur « Clean » :* Vos PDF auront un aspect minimaliste et moderne.
    *   *Lorsqu'il est défini sur « Warehouse Big » :* Le PDF sera optimisé pour une utilisation en entrepôt, potentiellement avec des polices plus grandes et des sections claires pour le prélèvement.
    *   *Lorsqu'il est défini sur « Retro » :* Vos PDF adopteront un design d'inspiration vintage.
-   **Valeur recommandée :** Commencez par « Clean » ou « Warehouse Big » en fonction de votre cas d'utilisation principal (bon de livraison client vs liste de prélèvement interne). Expérimentez pour trouver la meilleure adéquation à votre marque et à vos besoins opérationnels.
-   **Scénario / exemple de marchand :** Si vous souhaitez que vos bons de livraison reflètent une image de marque moderne et professionnelle, vous pourriez choisir « Clean » ou « Elegant Serif ». Si votre objectif principal est de fournir une liste de prélèvement très lisible pour le personnel de l'entrepôt, « Warehouse Big » pourrait être plus approprié.

#### **Activer les mises à jour MyPresta.eu** (`mypresta_updates`)

-   **Ce que fait ce paramètre :** Cela contrôle si le module peut vérifier et vous informer des mises à jour disponibles depuis MyPresta.eu.
-   **Effet de la modification de ce paramètre :**
    *   *Lorsqu'il est activé (Oui) :* Le module vérifiera périodiquement les nouvelles versions, vous assurant de rester à jour avec les dernières fonctionnalités, corrections de bugs et améliorations de compatibilité. Vous pourriez voir des notifications dans votre back office PrestaShop lorsqu'une mise à jour est disponible.
    *   *Lorsqu'il est désactivé (Non) :* Le module ne vérifiera pas les mises à jour. Vous devrez vérifier manuellement votre compte MyPresta.eu pour les nouvelles versions.
-   **Valeur recommandée :** **Oui**. Maintenir les modules à jour est crucial pour la sécurité, les performances et la compatibilité avec les nouvelles versions de PrestaShop.
-   **Scénario / exemple de marchand :** L'activation de cette option garantit que vous utilisez toujours la version la plus stable et la plus riche en fonctionnalités du module sans avoir à vérifier constamment manuellement.

#### **Version de mise à jour** (`update_`) et **Valeur de la version de mise à jour** (`updatev_`)

-   **Ce que font ces paramètres :** Ce sont des paramètres internes utilisés par le module pour gérer son mécanisme de mise à jour. Ils stockent des informations sur la dernière version disponible ou la version actuellement installée.
-   **Effet de la modification de ce paramètre :** Ceux-ci ne sont **pas destinés à être modifiés manuellement** par le marchand. Les modifier pourrait interférer avec la capacité du module à vérifier et à appliquer correctement les mises à jour.
-   **Valeur recommandée :** Laissez ces paramètres tels quels. Ils sont gérés automatiquement par le module.
-   **Scénario / exemple de marchand :** Vous n'interagirez généralement pas avec ces paramètres. Ils font partie de la logique de mise à jour interne du module.

### 2.2 Écrans d'administration dédiés et vues de contrôleur

Le module ajoute de nouveaux éléments de menu sous **Commandes** dans votre Back Office PrestaShop, vous permettant de gérer les catégories et les éléments de votre liste de contrôle d'entrepôt.

#### **Nom de l'écran : Catégories de la liste de contrôle**

-   **Emplacement du menu :** Back Office > Commandes > **Catégories de la liste de contrôle**
-   **Actions et paramètres disponibles :** Cet écran vous permet de créer, modifier et supprimer des catégories pour votre liste de contrôle d'entrepôt. Considérez les catégories comme des regroupements logiques pour vos éléments de liste de contrôle (par exemple, « Qualité de l'emballage », « Vérification du produit », « Documents d'expédition »).
    *   **Ajouter une nouvelle catégorie :** Cliquez sur « Ajouter une nouvelle catégorie » pour définir un nouveau groupe. Vous fournirez généralement un nom pour la catégorie (par exemple, « Inspection du produit »).
    *   **Modifier/Supprimer des catégories :** Vous pouvez modifier des catégories existantes ou les supprimer si elles ne sont plus nécessaires.
-   **Effet des modifications :**
    *   *Ajout d'une catégorie :* Crée une nouvelle section sous laquelle vous pourrez ultérieurement ajouter des éléments de liste de contrôle spécifiques.
    *   *Modification d'une catégorie :* Modifie le nom ou les propriétés d'une catégorie existante.
    *   *Suppression d'une catégorie :* Supprime la catégorie et tous les éléments de liste de contrôle associés du système. Cela n'apparaîtra plus sur vos PDF générés.
-   **Flux de travail recommandé pour la gestion quotidienne de la boutique :**
    1.  Commencez par définir des catégories larges qui reflètent votre processus d'entrepôt. Par exemple : « Précision de la commande », « Intégrité de l'emballage », « Documentation ».
    2.  Assurez-vous que les noms de catégorie sont clairs et descriptifs pour votre personnel.

#### **Nom de l'écran : Éléments de la liste de contrôle**

-   **Emplacement du menu :** Back Office > Commandes > **Éléments de la liste de contrôle**
-   **Actions et paramètres disponibles :** Cet écran est l'endroit où vous définissez les éléments réels qui apparaîtront sur votre liste de contrôle d'entrepôt dans le PDF. Chaque élément peut être attribué à une catégorie que vous avez créée précédemment.
    *   **Ajouter un nouvel élément :** Cliquez sur « Ajouter un nouvel élément ». Vous spécifierez :
        *   **Nom :** Le texte de l'élément de la liste de contrôle (par exemple, « Tous les articles sont-ils présents et comptabilisés ? »).
        *   **Catégorie :** Attribuez-le à l'une des catégories que vous avez définies (par exemple, « Précision de la commande »).
        *   **Actif :** Si cet élément doit apparaître sur la liste de contrôle.
    *   **Modifier/Supprimer des éléments :** Modifiez ou supprimez des éléments individuels de la liste de contrôle.
-   **Effet des modifications :**
    *   *Ajout d'un élément :* Le nouvel élément apparaîtra sur la liste de contrôle PDF générée sous sa catégorie attribuée.
    *   *Modification d'un élément :* Modifie le texte ou la catégorie d'un élément de liste de contrôle existant.
    *   *Suppression d'un élément :* Supprime l'élément de la liste de contrôle sur les PDF.
-   **Flux de travail recommandé pour la gestion quotidienne de la boutique :**
    1.  Une fois les catégories configurées, remplissez-les avec des éléments de liste de contrôle spécifiques et exploitables.
    2.  Exemples : « La quantité de produit correspond-elle à la commande ? », « Les articles fragiles sont-ils correctement amortis ? », « L'étiquette d'expédition est-elle correcte ? », « La facture est-elle incluse ? ».
    3.  Examinez et mettez à jour régulièrement vos éléments de liste de contrôle pour refléter les changements dans vos produits, emballages ou procédures d'expédition.

#### **Nom de l'écran : Liste des commandes (avec bouton d'exportation)**

-   **Emplacement du menu :** Back Office > Commandes > **Commandes**
-   **Actions et paramètres disponibles :** Ce module s'intègre directement dans votre liste de commandes PrestaShop standard. Vous trouverez de nouveaux boutons ou options pour générer des PDF pour des commandes individuelles ou potentiellement en masse.
    *   **Exportation de commande individuelle :** Lors de la visualisation d'une commande spécifique dans le Back Office, vous verrez un nouveau bouton (par exemple, « Exporter PDF » ou « Imprimer la liste de prélèvement ») qui vous permet de générer le PDF personnalisé pour cette commande.
    *   **Exportation de commandes en masse :** (Selon la version du module et la version de PrestaShop) Vous pourriez être en mesure de sélectionner plusieurs commandes dans la liste des commandes et de générer des PDF pour toutes en une seule fois.
-   **Effet des modifications :** Cliquer sur ces boutons téléchargera un document PDF sur votre ordinateur, formaté selon le modèle choisi et incluant votre liste de contrôle personnalisée.
-   **Flux de travail recommandé pour la gestion quotidienne de la boutique :**
    1.  Une fois qu'une commande est passée et validée, naviguez vers la liste des commandes.
    2.  Ouvrez la commande spécifique que vous devez traiter.
    3.  Cliquez sur le bouton « Exporter PDF » pour générer la liste de prélèvement/le bon de livraison avec la liste de contrôle.
    4.  Imprimez le PDF et remettez-le à votre personnel d'entrepôt pour traitement.
    5.  Le personnel utilise le PDF pour prélever les articles, vérifier l'exactitude à l'aide de la liste de contrôle et potentiellement recueillir des signatures avant l'emballage.

### 2.3 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Par défaut / Recommandé | Objectif et impact |
| --- | --- | --- | --- |
| **Configuration du module** | Modèle PDF | Clean / Warehouse Big | Sélectionne la mise en page visuelle et le design des documents PDF générés. |
| **Configuration du module** | Activer les mises à jour MyPresta.eu | Oui | Permet au module de vérifier et de notifier les nouvelles versions. |
| **Catégories de la liste de contrôle** | Ajouter/Modifier/Supprimer une catégorie | N/A | Gère les regroupements logiques pour les éléments de votre liste de contrôle d'entrepôt. |
| **Éléments de la liste de contrôle** | Ajouter/Modifier/Supprimer un élément | N/A | Définit les éléments spécifiques qui apparaissent sur votre liste de contrôle d'entrepôt dans le PDF. |
| **Liste des commandes / Vue de la commande** | Bouton Exporter PDF | N/A | Génère un document PDF pour la ou les commandes sélectionnées en utilisant le modèle et la liste de contrôle configurés. |

## 3. Dépannage du marchand et questions fréquemment posées (FAQ)

**Q : Le PDF semble étrange ou présente des problèmes de formatage. Que dois-je faire ?**
R :

1.  **Vider le cache Smarty :** Allez dans **Paramètres avancés > Performances** dans votre Back Office PrestaShop. Faites défiler jusqu'à « Cache » et cliquez sur « Vider le cache ». Parfois, d'anciens fichiers de modèle peuvent causer des problèmes d'affichage.
2.  **Essayer un autre modèle PDF :** Dans la configuration du module, essayez de sélectionner un autre « Modèle PDF » pour voir si le problème est spécifique à une mise en page.
3.  **Vérifier les conflits de thème :** Si vous utilisez un thème fortement personnalisé, il pourrait avoir du CSS ou du JS qui interfère. Passez temporairement au thème PrestaShop par défaut (par exemple, Classic) et retestez. Si cela fonctionne, votre thème pourrait nécessiter des ajustements.
4.  **Contacter le support :** Si les problèmes persistent, rassemblez des captures d'écran et des détails, puis contactez le support MyPresta.eu.

**Q : Mes éléments de liste de contrôle personnalisés n'apparaissent pas sur le PDF.**
R :

1.  **Vérifier les « Catégories de la liste de contrôle » :** Assurez-vous d'avoir créé des catégories sous **Commandes > Catégories de la liste de contrôle**.
2.  **Vérifier les « Éléments de la liste de contrôle » :** Vérifiez que vous avez ajouté des éléments sous **Commandes > Éléments de la liste de contrôle** et qu'ils sont attribués à une catégorie active. Assurez-vous également que le commutateur « Actif » pour chaque élément est défini sur « Oui ».
3.  **Configuration du module :** Assurez-vous que le module est correctement configuré et enregistré.

**Q : Je ne vois pas le bouton « Exporter PDF » sur mes pages de commande.**
R :

1.  **Module installé et activé :** Vérifiez que le module est installé et activé dans **Modules > Gestionnaire de modules**.
2.  **Permissions :** Assurez-vous que votre profil d'employé dispose des permissions nécessaires pour accéder et utiliser ce module. Allez dans **Paramètres avancés > Équipe > Profils** et vérifiez les permissions pour le profil attribué à votre compte d'employé.
3.  **Version de PrestaShop :** Confirmez que votre version de PrestaShop est compatible (1.7.x, 8.x, 9.x).
4.  **Vider le cache :** Videz le cache de votre PrestaShop (**Paramètres avancés > Performances**).

**Q : Puis-je personnaliser davantage les modèles PDF (par exemple, ajouter mon logo, changer les polices) ?**
R : Oui, mais cela nécessite des connaissances techniques. Le module fournit plusieurs modèles, mais pour une personnalisation approfondie (comme l'ajout de votre logo spécifique, la modification des polices ou l'altération de la mise en page au-delà de ce que les paramètres du module offrent), vous devrez :

1.  **Identifier le fichier de modèle :** Localisez le fichier `.tpl` du modèle PDF choisi dans le répertoire `pdf/en/` du module.
2.  **Modifier le modèle :** Cela implique l'édition du code de modèle Smarty et potentiellement du HTML/CSS. C'est une tâche pour un webmaster ou un développeur.
3.  **Envisager un modèle personnalisé :** Pour des changements significatifs, il est souvent préférable de créer un nouveau modèle personnalisé plutôt que de modifier les fichiers du module principal, afin de garantir que vos modifications ne soient pas écrasées lors des mises à jour du module.

**Q : Le module ne vérifie pas les mises à jour.**
R :

1.  **Activer la vérification des mises à jour :** Allez sur la page de configuration du module (**Modules > Gestionnaire de modules > Configurer** pour « Export PDF de commande et liste de contrôle d'entrepôt ») et assurez-vous que « Activer les mises à jour MyPresta.eu » est défini sur « Oui ».
2.  **Connectivité du serveur :** Assurez-vous que votre serveur a un accès Internet sortant pour se connecter aux serveurs de mise à jour de MyPresta.eu. Cela pourrait impliquer de vérifier les paramètres de pare-feu ou les configurations de proxy avec votre hébergeur.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

Cette section fournit un aperçu technique détaillé du module « Export PDF de commande et liste de contrôle d'entrepôt » pour les développeurs et les webmasters.

### 4.1 Aperçu de l'architecture

Le module suit un modèle MVC (Modèle-Vue-Contrôleur) PrestaShop standard, étendant principalement `Module` pour sa fonctionnalité principale et `AdminController` pour ses écrans de gestion du Back Office. Il utilise `ObjectModel` pour gérer les entités de base de données personnalisées (catégories et éléments de liste de contrôle). La génération de PDF est gérée par une classe dédiée (`OrderPdfGenerator`) qui utilise des modèles Smarty pour le rendu du contenu PDF, intégrant probablement une bibliothèque comme Dompdf ou TCPDF (bien que la bibliothèque spécifique ne soit pas explicitement indiquée, la structure `.tpl` suggère un moteur de rendu). Les hooks sont utilisés pour intégrer la fonctionnalité du module dans le Back Office de PrestaShop, en particulier pour ajouter des boutons d'exportation PDF aux pages de commande.

### 4.2 Contrôleurs (`controllers/`)

#### Contrôleurs d'administration du Back-Office

-   `orderexportpdf/controllers/admin/AdminOrderExportChecklistCategoriesController.php`

    *   **Nom de la classe :** `AdminOrderExportChecklistCategoriesController`
    *   **Classe parente :** `ModuleAdminController`
    *   **Responsabilité :** Gère les opérations CRUD (Créer, Lire, Mettre à jour, Supprimer) pour les objets `OrderExportChecklistCategory`. Il fournit l'interface du Back Office pour lister, ajouter, modifier et supprimer des catégories de liste de contrôle. Ce contrôleur est mappé à l'élément de menu « Catégories de la liste de contrôle » sous « Commandes ».
    *   **Nom de l'onglet :** Catégories de la liste de contrôle
    *   **Entité gérée :** `OrderExportChecklistCategory` (mappée à la table `ps_orderexport_checklist_cat`).
-   `orderexportpdf/controllers/admin/AdminOrderExportChecklistElementsController.php`

    *   **Nom de la classe :** `AdminOrderExportChecklistElementsController`
    *   **Classe parente :** `ModuleAdminController`
    *   **Responsabilité :** Gère les opérations CRUD pour les objets `OrderExportChecklistElement`. Il fournit l'interface du Back Office pour lister, ajouter, modifier et supprimer des éléments de liste de contrôle individuels, permettant l'affectation à des catégories. Ce contrôleur est mappé à l'élément de menu « Éléments de la liste de contrôle » sous « Commandes ».
    *   **Nom de l'onglet :** Éléments de la liste de contrôle
    *   **Entité gérée :** `OrderExportChecklistElement` (mappée à la table `ps_orderexport_checklist_elem`).
-   `orderexportpdf/controllers/admin/index.php`

    *   **Responsabilité :** Il s'agit généralement d'un fichier vide ou d'un fichier contenant une instruction de sécurité `die()` pour empêcher la liste directe des répertoires. Il ne contient pas de logique de contrôleur en soi.

### 4.3 Classes et modèles principaux (`classes/`)

-   `orderexportpdf/classes/index.php`

    *   **Responsabilité :** Fichier de sécurité PrestaShop standard, contient généralement `<?php exit;` pour empêcher la liste des répertoires.
-   `orderexportpdf/classes/OrderExport.php`

    *   **Nom de la classe :** `OrderExport`
    *   **Classe parente :** `Object` (probablement, ou une classe de base personnalisée)
    *   **Responsabilité :** Cette classe contient probablement des méthodes d'aide ou une logique de base liée au processus global d'exportation de commande, gérant éventuellement la récupération des données, le formatage ou l'interaction avec la classe de génération de PDF. Il pourrait ne pas s'agir d'un `ObjectModel` mais d'une classe utilitaire.
-   `orderexportpdf/classes/OrderExportChecklistCategory.php`

    *   **Nom de la classe :** `OrderExportChecklistCategory`
    *   **Classe parente :** `ObjectModel`
    *   **Table de base de données :** `ps_orderexport_checklist_cat`
    *   **Champs `$definition` :** Définit la structure d'une catégorie de liste de contrôle, y compris des champs comme `id_orderexport_checklist_cat`, `name` (multilingue), `active`, `position`.
    *   **Méthodes publiques clés :** Méthodes `ObjectModel` standard (`add`, `update`, `delete`, `getFields`, `validateFields`, `validateController`). Peut inclure des méthodes pour récupérer toutes les catégories actives ou les catégories par ID.
-   `orderexportpdf/classes/OrderExportChecklistElement.php`

    *   **Nom de la classe :** `OrderExportChecklistElement`
    *   **Classe parente :** `ObjectModel`
    *   **Table de base de données :** `ps_orderexport_checklist_elem`
    *   **Champs `$definition` :** Définit la structure d'un élément de liste de contrôle, y compris des champs comme `id_orderexport_checklist_elem`, `id_orderexport_checklist_cat` (clé étrangère), `name` (multilingue), `active`, `position`.
    *   **Méthodes publiques clés :** Méthodes `ObjectModel` standard. Peut inclure des méthodes pour récupérer des éléments par catégorie, ou tous les éléments actifs.
-   `orderexportpdf/classes/OrderPdfGenerator.php`

    *   **Nom de la classe :** `OrderPdfGenerator`
    *   **Classe parente :** Probablement `Object` ou une classe de base personnalisée.
    *   **Responsabilité :** C'est la classe principale responsable de la génération des documents PDF. Elle prend un ID de commande, un modèle sélectionné et des données de liste de contrôle, puis rend le contenu au format PDF. Elle utilise probablement une bibliothèque PDF tierce (par exemple, Dompdf, mPDF) en interne.
    *   **Méthodes publiques clés :** `generatePdf($orderId, $templateName, $checklistData)`, `renderTemplate($templatePath, $data)`, `downloadPdf()`.

### 4.4 Actifs JavaScript (`views/js/`)

-   `orderexportpdf/lib/pdfTemplatesManager/js/pdfTemplatesManager.js`

    *   **Portée :** Back-office.
    *   **Responsabilité :** Gère probablement la gestion dynamique des modèles PDF dans l'interface de configuration du module. Cela pourrait inclure des appels AJAX pour enregistrer les paramètres de modèle, prévisualiser les modèles ou basculer entre différentes options de modèle.
-   `orderexportpdf/views/js/order-list-legacy.js`

    *   **Portée :** Back-office (pour PrestaShop 1.7.x ou les versions antérieures utilisant du JS hérité).
    *   **Responsabilité :** Intègre la fonctionnalité du bouton d'exportation PDF dans la vue de la liste des commandes du Back Office de PrestaShop pour les anciennes versions de PrestaShop. Il lie les événements de clic aux boutons, effectue potentiellement des appels AJAX pour déclencher la génération de PDF et gère le téléchargement du PDF généré.
-   `orderexportpdf/views/js/order-list-modern.js`

    *   **Portée :** Back-office (pour PrestaShop 8.x, 9.x ou les versions plus récentes utilisant du JS moderne).
    *   **Responsabilité :** Similaire à `order-list-legacy.js`, mais adapté aux nouvelles interfaces du Back Office de PrestaShop et utilisant potentiellement des pratiques JavaScript modernes (par exemple, ES6, actifs compilés par Webpack). Il garantit que le bouton d'exportation PDF est correctement affiché et fonctionnel sur la liste des commandes et les pages de vue de commande individuelle.

### 4.5 Feuilles de style CSS (`views/css/`)

-   `orderexportpdf/lib/pdfTemplatesManager/css/pdfTemplatesManager.css`

    *   **Portée :** Style du formulaire d'administration du Back-office.
    *   **Responsabilité :** Fournit le style pour l'interface de configuration du module, spécifiquement pour la section du gestionnaire de modèles PDF. Cela pourrait inclure des styles pour les boutons, les listes déroulantes, les zones de prévisualisation ou les éléments de formulaire liés à la sélection de modèles.
-   `orderexportpdf/views/css/order-export.css`

    *   **Portée :** Style du formulaire d'administration du Back-office.
    *   **Responsabilité :** Style général pour les composants du Back Office du module, tels que les écrans de gestion des catégories et des éléments de la liste de contrôle, ou potentiellement le style des boutons ajoutés sur les pages de commande.
    *   **Sélecteurs de classe CSS clés :** Les développeurs peuvent inspecter le HTML généré pour des classes comme `.orderexportpdf-button`, `.orderexport-checklist-table`, etc., pour remplacer les styles dans leur thème d'administration personnalisé.

### 4.6 Structure des modèles Smarty (`views/templates/`)

#### Modèles de hook (`views/templates/hook/`)

-   `orderexportpdf/lib/pdfTemplatesManager/views/buttonManager.tpl`

    *   **Hook :** Probablement rendu dans un hook au sein de la configuration du module ou d'une page de commande d'administration pour afficher des boutons liés à la gestion des modèles (par exemple, « Gérer les modèles », « Créer un nouveau modèle »).
    *   **Sortie :** HTML pour les boutons ou les liens pour gérer les modèles PDF.
-   `orderexportpdf/lib/pdfTemplatesManager/views/createTemplateForm.tpl`

    *   **Hook :** Interne au gestionnaire de modèles du module, affiché lors de la création d'un nouveau modèle PDF.
    *   **Sortie :** Formulaire HTML pour définir les propriétés d'un nouveau modèle PDF.
-   `orderexportpdf/lib/pdfTemplatesManager/views/editTemplateForm.tpl`

    *   **Hook :** Interne au gestionnaire de modèles du module, affiché lors de la modification d'un modèle PDF existant.
    *   **Sortie :** Formulaire HTML pour modifier les propriétés d'un modèle PDF existant.
-   `orderexportpdf/lib/pdfTemplatesManager/views/mainForm.tpl`

    *   **Hook :** Le formulaire de configuration principal du module (par exemple, méthode `getContent()`).
    *   **Sortie :** Le formulaire HTML principal contenant la liste déroulante de sélection de « Modèle PDF » et d'autres paramètres au niveau du module.
-   `orderexportpdf/lib/pdfTemplatesManager/views/selectInput.tpl`

    *   **Hook :** Un modèle partiel réutilisable, probablement inclus dans `mainForm.tpl` ou d'autres formulaires, pour rendre une entrée déroulante (`<select>`) pour choisir des modèles.
    *   **Sortie :** HTML pour un élément `<select>` rempli avec les modèles PDF disponibles.
-   `orderexportpdf/pdf/en/*.tpl` (par exemple, `blue-line-dompdf.tpl`, `boxed-layout-dompdf.tpl`, `clean-dompdf.tpl`, `warehouse-big-dompdf.tpl`, etc.)

    *   **Hook :** Ce ne sont **pas** des modèles de hook PrestaShop. Ce sont les **modèles de mise en page PDF** réels utilisés par `OrderPdfGenerator` pour rendre le contenu de la liste de prélèvement/bon de livraison. Ils sont choisis via la configuration du module.
    *   **Sortie :** Structure HTML/CSS qui sera convertie en document PDF. Ces modèles contiennent des espaces réservés pour les détails de la commande, les listes de produits, les informations client et la liste de contrôle personnalisée.
    *   **Note :** Le suffixe `dompdf` suggère l'utilisation de la bibliothèque Dompdf pour la conversion HTML vers PDF.
-   `orderexportpdf/pdf/fr/kids-play.tpl`

    *   **Hook :** Similaire aux modèles `en`, mais une version spécifique au français de la mise en page PDF « kids-play ». Cela indique la prise en charge multilingue des modèles PDF.
-   `orderexportpdf/pdf/en/order-export.tpl`

    *   **Hook :** Il pourrait s'agir d'un modèle de base générique ou d'un modèle de secours pour la génération de PDF.
    *   **Sortie :** Une structure générale pour le PDF d'exportation de commande.

### 4.7 Schéma de la base de données et carte des hooks

#### Tables de la base de données

-   `ps_orderexport_checklist_cat` : Stocke les informations sur les catégories de liste de contrôle personnalisées.

    *   `id_orderexport_checklist_cat` (Clé primaire, INT)
    *   `name` (VARCHAR, Multilingue) : Le nom de la catégorie de la liste de contrôle.
    *   `active` (TINYINT) : Indique si la catégorie est active.
    *   `position` (INT) : Ordre d'affichage des catégories.
    *   `date_add` (DATETIME)
    *   `date_upd` (DATETIME)
-   `ps_orderexport_checklist_elem` : Stocke les informations sur les éléments individuels de la liste de contrôle.

    *   `id_orderexport_checklist_elem` (Clé primaire, INT)
    *   `id_orderexport_checklist_cat` (Clé étrangère vers `ps_orderexport_checklist_cat`, INT) : La catégorie à laquelle cet élément appartient.
    *   `name` (VARCHAR, Multilingue) : Le texte de l'élément de la liste de contrôle.
    *   `active` (TINYINT) : Indique si l'élément est actif.
    *   `position` (INT) : Ordre d'affichage des éléments dans une catégorie.
    *   `date_add` (DATETIME)
    *   `date_upd` (DATETIME)
-   `ps_configuration` : Le module stocke ses principaux paramètres de configuration ici.

    *   `PS_BO_ALLOW_EMPLOYEE_FORM_LANG` : (Paramètre principal de PrestaShop, non spécifique au module)
    *   `MYPRESTA_UPDATES` : (Paramètre du module) Stocke l'état de la vérification des mises à jour (1 pour activé, 0 pour désactivé).
    *   `UPDATE_` : (Paramètre du module) Suivi interne de la version de mise à jour.
    *   `UPDATEV_` : (Paramètre du module) Valeur interne de la version de mise à jour.
    *   `ORDEREXPORTPDF_TEMPLATE` : (Paramètre du module) Stocke le nom du modèle PDF actuellement sélectionné.

#### Tableau des hooks enregistrés

| Nom du hook | Moment d'exécution | Objectif technique |
| --- | --- | --- |
| `actionAdminControllerSetMedia` | Exécuté lorsqu'un AdminController charge ses actifs. | Injecte les CSS (`order-export.css`, `pdfTemplatesManager.css`) et JavaScript (`order-list-legacy.js`, `order-list-modern.js`, `pdfTemplatesManager.js`) spécifiques au module dans le Back Office, en particulier pour les pages de commande et la configuration du module. |
| `displayAdminOrder` | Exécuté sur la page de vue de commande individuelle dans le Back Office. | Rend le bouton « Exporter PDF » ou un widget similaire sur la page des détails de la commande, permettant la génération de PDF pour une seule commande. |
| `actionGetAdminOrderButtons` | Exécuté pour permettre aux modules d'ajouter des boutons personnalisés à la vue de commande de l'administration. | Fournit un mécanisme pour injecter des boutons personnalisés (comme « Exporter PDF ») dans la vue de commande de PrestaShop 1.7+, assurant la compatibilité avec l'interface utilisateur moderne. |

## 5. Support officiel et mises à jour

Pour les mises à jour officielles, le support technique et pour télécharger les dernières versions du module « Export PDF de commande et liste de contrôle d'entrepôt », veuillez visiter votre compte client sur [MyPresta.eu](https://mypresta.eu/my-account/orders/). Notre équipe de support est disponible pour vous aider avec toutes les questions ou problèmes que vous pourriez avoir concernant la fonctionnalité ou la configuration du module.
