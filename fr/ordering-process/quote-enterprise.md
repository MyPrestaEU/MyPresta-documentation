---
title: "Quote Enterprise - Manuel Marchand & Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop Quote Enterprise par MyPresta.eu."
sidebar:
  label: "Quote Enterprise - Manuel Marchand & Guide de Configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Quote Enterprise sur MyPresta.eu](https://mypresta.eu/modules/ordering-process/quote-enterprise.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/ordering-process/quote-enterprise/)
>
> ---


# Quote Enterprise

## 1. Exigences et compatibilité

- **Versions PrestaShop prises en charge** : PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilité PHP** : PHP 7.1 - 8.5
- **Exigences d'hébergement** : Les extensions PHP standard (cURL, JSON, OpenSSL) sont requises. Assurez-vous que votre serveur répond aux exigences minimales de PrestaShop.

## 2. Guide de configuration complet (chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer > Quote Enterprise)

C'est l'écran de configuration principal où vous définissez le comportement et l'apparence du module Quote Enterprise.

#### Onglet Paramètres généraux

-   **Activer Quote Enterprise :**
    *   **Ce que fait ce paramètre :** C'est l'interrupteur principal pour l'ensemble du module.
    *   **Effet de la modification de ce paramètre :**
        *   *Lorsqu'il est activé :* Le système de devis devient actif sur votre boutique, et les clients peuvent commencer à demander des devis.
        *   *Lorsqu'il est désactivé :* Toutes les fonctionnalités de devis sont masquées du front office, et aucun nouveau devis ne peut être demandé. Les devis existants dans le back office restent accessibles pour la gestion.
    *   **Valeur recommandée :** OUI
    *   **Scénario / exemple marchand :** Activez-le lorsque vous êtes prêt à offrir des services de devis. Désactivez-le temporairement pendant la maintenance ou si vous décidez d'arrêter d'offrir des devis.
-   **Autoriser les demandes de devis depuis le panier :**
    *   **Ce que fait ce paramètre :** Détermine si les clients peuvent convertir l'intégralité de leur panier en une demande de devis.
    *   **Effet de la modification de ce paramètre :**
        *   *Lorsqu'il est activé :* Un bouton ou un lien "Demander un devis" apparaîtra dans le récapitulatif du panier, permettant aux clients de soumettre tous les articles de leur panier pour un devis.
        *   *Lorsqu'il est désactivé :* Les clients ne peuvent demander des devis que depuis les pages de produits individuelles ou via le bouton flottant (si activé), pas directement depuis leur panier.
    *   **Valeur recommandée :** OUI (pour la plupart des scénarios B2B et de commandes en gros)
    *   **Scénario / exemple marchand :** Si vous traitez principalement des commandes importantes de plusieurs articles où les prix sont souvent négociés, activez ceci. Si vos devis concernent généralement des produits uniques et personnalisés, vous pouvez le désactiver.
-   **Autoriser les demandes de devis depuis la page produit :**
    *   **Ce que fait ce paramètre :** Contrôle si un bouton "Demander un devis" apparaît sur les pages de produits individuelles.
    *   **Effet de la modification de ce paramètre :**
        *   *Lorsqu'il est activé :* Les clients peuvent ajouter un produit spécifique à une demande de devis directement depuis sa page, au lieu de l'ajouter au panier.
        *   *Lorsqu'il est désactivé :* L'option de demande de devis est supprimée des pages de produits.
    *   **Valeur recommandée :** OUI
    *   **Scénario / exemple marchand :** Essentiel pour les produits personnalisés, les articles de grande valeur, ou lorsque vous souhaitez offrir une alternative à l'achat direct pour tout produit.
-   **Afficher le bouton de devis flottant :**
    *   **Ce que fait ce paramètre :** Ajoute un bouton flottant persistant au front office de votre boutique, permettant aux clients d'initier une demande de devis depuis presque n'importe quelle page.
    *   **Effet de la modification de ce paramètre :**
        *   *Lorsqu'il est activé :* Un petit bouton cliquable (souvent dans un coin de l'écran) apparaîtra, ouvrant le formulaire de demande de devis ou une liste de devis existants.
        *   *Lorsqu'il est désactivé :* Le bouton flottant ne sera pas visible.
    *   **Valeur recommandée :** OUI (pour une grande visibilité et une facilité d'accès)
    *   **Scénario / exemple marchand :** Utilisez ceci pour rendre l'option de devis très visible dans votre boutique, encourageant plus de demandes.
-   **Valeur minimale de commande pour la demande de devis :**
    *   **Ce que fait ce paramètre :** Définit une valeur totale minimale (dans votre devise par défaut) qu'une demande de devis doit atteindre pour être soumise.
    *   **Effet de la modification de ce paramètre :**
        *   *Lorsqu'une valeur est définie (par exemple, 100) :* Les clients ne peuvent pas soumettre une demande de devis si la valeur totale des articles de leur demande est inférieure à ce montant. Un message d'erreur sera affiché.
        *   *Lorsqu'il est défini sur 0 ou laissé vide :* Aucune valeur minimale n'est appliquée.
    *   **Valeur recommandée :** 0 (ou une valeur qui filtre les demandes triviales)
    *   **Scénario / exemple marchand :** Si vous ne souhaitez traiter les devis que pour des commandes importantes, définissez une valeur minimale (par exemple, 500 €) pour réduire la charge administrative des petites demandes.
-   **Validité par défaut du devis (jours) :**
    *   **Ce que fait ce paramètre :** Définit le nombre de jours pendant lesquels un devis nouvellement créé sera valide, par défaut.
    *   **Effet de la modification de ce paramètre :**
        *   *Lorsqu'il est défini sur un nombre (par exemple, 30) :* Tous les nouveaux devis créés par votre équipe auront automatiquement une date d'expiration 30 jours après leur création.
        *   *Lorsqu'il est défini sur 0 ou laissé vide :* Les devis n'auront pas de période de validité par défaut, et votre équipe devra en définir une manuellement ou les gérer sans expiration.
    *   **Valeur recommandée :** 30 (ou une période typique pour votre secteur)
    *   **Scénario / exemple marchand :** Définir une validité de 30 jours encourage les clients à agir dans un délai raisonnable et vous protège des fluctuations de prix.

#### Onglet Modèles d'e-mail

Cette section vous permet de personnaliser les notifications par e-mail envoyées par le module.

-   **Gestionnaire de modèles d'e-mail :**
    *   **Ce que fait ce paramètre :** Fournit une interface visuelle pour modifier le contenu de divers modèles d'e-mail liés aux devis (par exemple, nouvelle demande de devis, devis mis à jour, devis accepté).
    *   **Effet de la modification de ce paramètre :**
        *   *Lorsque vous modifiez un modèle :* L'e-mail correspondant envoyé aux clients ou à votre équipe reflétera vos modifications, y compris le texte, la marque et la mise en page.
    *   **Valeur recommandée :** Personnalisez pour correspondre à la voix de votre marque et fournir des instructions claires.
    *   **Scénario / exemple marchand :** Modifiez l'e-mail "Nouvelle demande de devis" pour inclure des instructions spécifiques pour votre équipe de vente ou ajoutez une salutation personnalisée pour les clients.

#### Onglet Paramètres avancés

-   **Activer l'API REST :**
    *   **Ce que fait ce paramètre :** Active une interface programmatique (API) pour le module, permettant aux systèmes externes ou aux applications personnalisées d'interagir avec vos devis.
    *   **Effet de la modification de ce paramètre :**
        *   *Lorsqu'il est activé :* Le module expose des points de terminaison qui peuvent être utilisés par les développeurs pour créer, lire, mettre à jour et supprimer des devis par programme.
        *   *Lorsqu'il est désactivé :* L'API est inactive et ne peut pas être consultée.
    *   **Valeur recommandée :** NON (sauf si vous avez des besoins d'intégration spécifiques)
    *   **Scénario / exemple marchand :** Si vous intégrez un CRM, un ERP ou une application mobile personnalisée, l'activation de l'API permet à ces systèmes de créer ou de mettre à jour automatiquement des devis dans PrestaShop. Nécessite une expertise de développeur.
-   **Gestion des clés API :**
    *   **Ce que fait ce paramètre :** Vous permet de générer et de gérer des clés API, qui sont nécessaires pour authentifier les requêtes vers l'API REST du module.
    *   **Effet de la modification de ce paramètre :**
        *   *Lorsque vous créez une clé :* Vous obtenez un identifiant unique que les applications externes doivent utiliser pour accéder à l'API.
        *   *Lorsque vous révoquez une clé :* Toute application utilisant cette clé perdra l'accès à l'API.
    *   **Valeur recommandée :** Générez des clés uniquement lorsque cela est nécessaire pour des intégrations spécifiques.
    *   **Scénario / exemple marchand :** Créez une nouvelle clé API pour votre système CRM afin de pousser de nouveaux prospects en tant que demandes de devis dans PrestaShop.
-   **URL de la tâche Cron pour l'expiration et le résumé :**
    *   **Ce que fait ce paramètre :** Fournit une URL qui, lorsqu'elle est consultée, déclenche des tâches d'arrière-plan telles que la vérification des expirations de devis et l'envoi de résumés quotidiens à votre équipe.
    *   **Effet de la modification de ce paramètre :**
        *   *Lorsqu'il est configuré sur votre serveur :* Le module effectuera automatiquement ces tâches à intervalles réguliers (par exemple, quotidiennement), garantissant que les devis sont marqués comme expirés et que votre équipe reçoit des résumés en temps opportun.
        *   *Lorsqu'il n'est pas configuré :* Les vérifications d'expiration et les e-mails de résumé ne seront pas automatisés.
    *   **Valeur recommandée :** Configurez cette URL comme une tâche cron quotidienne sur votre serveur d'hébergement.
    *   **Scénario / exemple marchand :** Configurez une tâche cron pour exécuter cette URL une fois par jour afin de vous assurer que les clients sont informés des devis expirés et que votre équipe de vente reçoit un résumé quotidien des nouvelles demandes.

### 2.2 Écrans d'administration dédiés et vues de contrôleur

#### 2.2.1 Gestion des devis (Back Office > Quote Enterprise > Devis)

C'est le centre névralgique pour votre équipe de vente afin de gérer toutes les demandes de devis.

-   **Nom de l'écran et emplacement du menu :** **Quote Enterprise > Devis**
-   **Actions et paramètres disponibles :**
    *   **Tableau de la liste des devis :** Affiche tous les devis soumis avec des informations clés telles que le nom du client, le statut, la valeur totale et la date de création.
    *   **Filtrage et recherche :** Outils pour trouver des devis spécifiques par client, statut, plage de dates, etc.
    *   **Afficher/Modifier le devis :** Cliquez sur n'importe quel devis pour ouvrir une vue détaillée où vous pouvez :
        *   **Ajuster les produits et les quantités :** Modifier les articles, les quantités et les prix dans le devis.
        *   **Ajouter/Supprimer des produits :** Rechercher et ajouter de nouveaux produits au devis ou supprimer des produits existants.
        *   **Appliquer des remises :** Offrir des remises spécifiques sur le total du devis ou sur des articles individuels.
        *   **Définir la validité :** Définir la date d'expiration du devis.
        *   **Ajouter des notes/messages :** Communiquer avec le client directement via l'interface du devis.
        *   **Changer le statut :** Mettre à jour le statut du devis (par exemple, En attente, Envoyé, Accepté, Rejeté, Expiré).
        *   **Générer un PDF :** Créer une facture proforma PDF professionnelle pour le client.
        *   **Convertir en commande :** En un seul clic, convertir un devis accepté en une commande PrestaShop standard, prête pour le paiement.
        *   **Envoyer un e-mail :** Envoyer les détails du devis mis à jour ou des messages au client.
    *   **Actions groupées :** Sélectionnez plusieurs devis pour effectuer des actions telles que changer le statut, supprimer ou exporter.
-   **Effet des modifications :**
    *   La modification d'un devis met à jour ses détails dans la base de données et peut déclencher des notifications par e-mail au client.
    *   La conversion en commande crée une nouvelle commande dans le système de gestion des commandes standard de PrestaShop, pré-remplie avec les articles et les prix du devis.
    *   Le changement de statut met à jour la vue du client dans son compte et peut déclencher des modèles d'e-mail spécifiques.
-   **Flux de travail recommandé pour la gestion quotidienne du magasin :**
    1.  Vérifiez régulièrement la liste "Devis" pour les nouvelles demandes "En attente".
    2.  Ouvrez chaque nouvelle demande, examinez les articles, ajustez les prix/quantités si nécessaire, et ajoutez des notes internes.
    3.  Définissez une période de validité et générez une proforma PDF.
    4.  Changez le statut en "Envoyé" et envoyez le devis au client par e-mail.
    5.  Faites un suivi des devis "Envoyés". S'ils sont acceptés, convertissez-les en commande. S'ils sont rejetés ou expirés, mettez à jour le statut en conséquence.

#### 2.2.2 Journal d'audit (Back Office > Quote Enterprise > Journal d'audit)

Cet écran fournit un historique détaillé de toutes les actions effectuées sur les devis.

-   **Nom de l'écran et emplacement du menu :** **Quote Enterprise > Journal d'audit**
-   **Actions et paramètres disponibles :**
    *   **Tableau de la liste des journaux :** Affiche une liste chronologique des événements liés aux devis, y compris qui a effectué l'action, quelle action a été effectuée (par exemple, "Devis créé", "Prix modifié", "Statut mis à jour") et quand elle s'est produite.
    *   **Filtrage :** Filtrez le journal par date, utilisateur ou type d'action pour trouver des événements spécifiques.
-   **Effet des modifications :** Il s'agit d'un journal en lecture seule ; vous ne pouvez pas y apporter de modifications. Il sert de registre historique.
-   **Flux de travail recommandé pour la gestion quotidienne du magasin :**
    *   Utilisez le journal d'audit pour suivre les modifications, résoudre les problèmes ou examiner l'activité de l'équipe sur les devis. Il est inestimable pour la responsabilité et la compréhension du cycle de vie de chaque devis.

### 2.3 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Valeur par défaut / Recommandée | Objectif et impact |
| --- | --- | --- | --- |
| **Configuration du module** | Activer Quote Enterprise | OUI | Interrupteur principal pour la fonctionnalité du module. |
| | Autoriser les demandes de devis depuis le panier | OUI | Ajoute un bouton de devis à la page du panier. |
| | Autoriser les demandes de devis depuis la page produit | OUI | Ajoute un bouton de devis aux pages produits. |
| | Afficher le bouton de devis flottant | OUI | Affiche un bouton de devis persistant sur le front office. |
| | Valeur minimale de commande pour la demande de devis | 0 | Définit une valeur minimale pour les soumissions de devis. |
| | Validité par défaut du devis (jours) | 30 | Définit l'expiration par défaut pour les nouveaux devis. |
| | Gestionnaire de modèles d'e-mail | Personnaliser | Modifier le contenu des e-mails pour divers événements de devis. |
| | Activer l'API REST | NON | Active l'API pour les intégrations externes (développeur uniquement). |
| | Gestion des clés API | N/A | Gérer les clés API pour un accès sécurisé à l'API (développeur uniquement). |
| | URL de la tâche Cron pour l'expiration et le résumé | Configurer | Automatise les vérifications d'expiration des devis et les résumés d'équipe. |
| **Gestion des devis** | Liste des devis | N/A | Afficher, filtrer et gérer tous les devis. |
| | Afficher/Modifier le devis | N/A | Ajuster les articles, les prix, le statut, générer un PDF, convertir en commande. |
| | Actions groupées | N/A | Appliquer des actions à plusieurs devis sélectionnés. |
| **Journal d'audit** | Liste des journaux | N/A | Examiner les actions historiques sur tous les devis. |

## 3. Dépannage marchand et questions fréquemment posées (FAQ)

**Q : Mes boutons "Demander un devis" n'apparaissent pas sur le front office.**
R :

1.  **Vérifier le statut du module :** Assurez-vous que "Activer Quote Enterprise" est défini sur OUI dans la configuration du module.
2.  **Vérifier les paramètres spécifiques :** Vérifiez que "Autoriser les demandes de devis depuis le panier" et "Autoriser les demandes de devis depuis la page produit" sont activés si nécessaire.
3.  **Vider le cache :** Allez dans **Paramètres avancés > Performances** et videz le cache de votre PrestaShop (cache Smarty, cache du système de fichiers). Parfois, les modifications n'apparaissent pas tant que le cache n'est pas actualisé.
4.  **Compatibilité du thème :** Si vous utilisez un thème personnalisé, il peut y avoir un problème de compatibilité. Contactez le support MyPresta.eu avec les détails de votre thème.

**Q : Les clients ne reçoivent pas les e-mails de notification de devis.**
R :

1.  **Vérifier les modèles d'e-mail :** Dans la configuration du module, accédez à l'onglet "Modèles d'e-mail" et assurez-vous que les modèles sont correctement configurés et enregistrés.
2.  **Paramètres d'e-mail de PrestaShop :** Vérifiez vos paramètres d'e-mail généraux de PrestaShop (SMTP, e-mail PHP) sous **Paramètres avancés > E-mail**. Envoyez un e-mail de test à partir de là pour confirmer que le système de messagerie de votre boutique fonctionne.
3.  **Dossiers de spam :** Conseillez aux clients de vérifier leurs dossiers de spam ou de courrier indésirable.
4.  **Tâche Cron (pour les résumés/rappels) :** S'il s'agit de rappels d'expiration ou de résumés quotidiens, assurez-vous que l'URL de la tâche cron est correctement configurée sur votre serveur pour s'exécuter régulièrement.

**Q : Puis-je personnaliser l'apparence du formulaire de demande de devis ou des boutons ?**
R : Oui, le module utilise le système de templating standard de PrestaShop. Pour des changements de style de base (couleurs, polices), vous pouvez souvent surcharger le CSS du module dans le fichier CSS personnalisé de votre thème. Pour des changements de mise en page plus complexes, vous devrez surcharger les fichiers TPL du module dans votre thème. Cela nécessite généralement un développeur web.

**Q : Comment convertir un devis accepté en commande normale ?**
R : Dans le Back Office de PrestaShop, naviguez vers **Quote Enterprise > Devis**. Ouvrez le devis spécifique que vous souhaitez convertir. Dans la vue détaillée du devis, il y aura un bouton (par exemple, "Convertir en commande" ou "Créer une commande"). Cliquer dessus générera une nouvelle commande dans votre liste de commandes PrestaShop standard, pré-remplie avec les articles et les prix du devis.

**Q : Que se passe-t-il si un devis expire ?**
R : Si la tâche cron est configurée, le module marquera automatiquement les devis expirés comme "Expirés". Les clients ne pourront plus accepter ou convertir un devis expiré en commande. Votre équipe de vente peut toujours consulter les devis expirés et potentiellement les réactiver ou créer un nouveau devis si nécessaire.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

### 4.1 Aperçu de l'architecture

Le module Quote Enterprise suit une architecture MVC (Modèle-Vue-Contrôleur) PrestaShop robuste, tirant fortement parti d'`ObjectModel` pour la persistance des données. Il s'intègre de manière transparente au système de hooks de PrestaShop pour l'affichage en front-office et les actions en back-office. Le module comprend des contrôleurs d'administration dédiés pour la gestion des devis et des journaux d'audit, des contrôleurs frontaux pour l'interaction client (demande, liste, vue, API) et un ensemble complet de classes d'aide pour la logique métier, la génération de PDF, la gestion des e-mails, et plus encore. Une API REST est également fournie pour l'intégration de systèmes externes.

### 4.2 Contrôleurs (`controllers/`)

#### Contrôleurs Front-Office

-   `controllers/front/api.php`
    *   Nom de la classe : `QuoteenterpriseApiModuleFrontController` (étend `ModuleFrontController`)
    *   Responsabilité : Gère les requêtes API depuis le front-office, probablement pour des intégrations spécifiques côté client ou le chargement de contenu dynamique.
-   `controllers/front/cron.php`
    *   Nom de la classe : `QuoteenterpriseCronModuleFrontController` (étend `ModuleFrontController`)
    *   Responsabilité : Sert de point d'accès pour la tâche cron, déclenchant des tâches d'arrière-plan telles que la vérification des expirations de devis et l'envoi d'e-mails de résumé.
-   `controllers/front/index.php`
    *   Nom de la classe : `QuoteenterpriseIndexModuleFrontController` (étend `ModuleFrontController`)
    *   Responsabilité : Probablement un contrôleur de secours ou de base, ou gère une route par défaut pour la section front-office du module.
-   `controllers/front/list.php`
    *   Nom de la classe : `QuoteenterpriseListModuleFrontController` (étend `ModuleFrontController`)
    *   Responsabilité : Affiche une liste de devis pour le client connecté dans son espace compte.
-   `controllers/front/pdf.php`
    *   Nom de la classe : `QuoteenterprisePdfModuleFrontController` (étend `ModuleFrontController`)
    *   Responsabilité : Génère et sert des versions PDF des devis pour que les clients puissent les télécharger.
-   `controllers/front/quoteList.php`
    *   Nom de la classe : `QuoteenterpriseQuoteListModuleFrontController` (étend `ModuleFrontController`)
    *   Responsabilité : Similaire à `list.php`, potentiellement une vue alternative ou spécifique pour les listes de devis, éventuellement pour le chargement AJAX.
-   `controllers/front/request.php`
    *   Nom de la classe : `QuoteenterpriseRequestModuleFrontController` (étend `ModuleFrontController`)
    *   Responsabilité : Gère l'affichage et la soumission du formulaire de demande de devis depuis les pages produits, le panier ou le bouton flottant. Traite les données du formulaire et crée de nouvelles entrées de devis.
-   `controllers/front/view.php`
    *   Nom de la classe : `QuoteenterpriseViewModuleFrontController` (étend `ModuleFrontController`)
    *   Responsabilité : Affiche la vue détaillée d'un seul devis pour le client, montrant les articles, les prix, le statut et les messages.

#### Contrôleurs d'administration Back-Office

-   `controllers/admin/AdminQuoteEnterpriseAuditLog.php`
    *   Nom de la classe : `AdminQuoteEnterpriseAuditLogController` (étend `ModuleAdminController`)
    *   Nom de l'onglet : Quote Enterprise > Journal d'audit
    *   Entité gérée : `quote_audit_log` (probablement un `ObjectModel` personnalisé pour les entrées d'audit)
    *   Responsabilité : Fournit une vue en grille aux administrateurs pour examiner toutes les actions et modifications historiques liées aux devis.
-   `controllers/admin/AdminQuoteEnterpriseQuotes.php`
    *   Nom de la classe : `AdminQuoteEnterpriseQuotesController` (étend `ModuleAdminController`)
    *   Nom de l'onglet : Quote Enterprise > Devis
    *   Entité gérée : `quote` (probablement un `ObjectModel` personnalisé pour les devis)
    *   Responsabilité : L'interface principale pour la gestion des devis, y compris la liste, la visualisation, la modification, la conversion en commande et l'envoi de communications.
-   `controllers/admin/index.php`
    *   Nom de la classe : `QuoteenterpriseAdminIndexModuleFrontController` (étend `ModuleAdminController`)
    *   Responsabilité : Probablement un contrôleur d'administration de remplacement ou de base, redirigeant potentiellement vers la liste principale des devis ou le tableau de bord.

### 4.3 Classes et modèles principaux (`classes/`)

-   `classes/index.php` : Fichier vide, pratique courante pour empêcher la liste des répertoires.
-   `classes/QuoteAdmin.php` : Contient la logique pour les tâches spécifiques à l'administration, potentiellement liées à la configuration du module ou aux utilitaires d'administration généraux.
-   `classes/QuoteAdminAjax.php` : Gère les requêtes AJAX provenant du back-office, telles que la recherche dynamique de produits à ajouter à un devis.
-   `classes/QuoteAdminQuoteForm.php` : Gère la logique complexe du formulaire pour l'édition et la création de devis dans le back-office.
-   `classes/QuoteApi.php` : Classe principale pour l'API REST du module, gérant l'authentification, le routage et la sérialisation des données.
-   `classes/QuoteApiDocumentation.php` : Fournit des méthodes pour générer ou afficher la documentation des points de terminaison de l'API du module.
-   `classes/QuoteBulkActions.php` : Implémente la logique pour effectuer des actions sur plusieurs devis sélectionnés dans la liste d'administration (par exemple, changement de statut en masse).
-   `classes/QuoteConverter.php` : Gère la logique cruciale de conversion d'un devis accepté en une commande PrestaShop standard.
-   `classes/QuoteDashboard.php` : Fournit des données et de la logique pour la vue du tableau de bord du module dans le back-office (si présente), résumant l'activité des devis.
-   `classes/QuoteDuplicator.php` : Logique pour dupliquer des devis existants.
-   `classes/QuoteenterpriseModuleFrontController.php` : Classe de base pour les contrôleurs front-office, fournissant des méthodes et des propriétés communes.
-   `classes/QuoteExpiry.php` : Gère la logique de vérification de la validité des devis, de marquage des devis comme expirés et d'envoi des notifications associées.
-   `classes/QuoteExporter.php` : Gère l'exportation des données de devis (par exemple, CSV, Excel).
-   `classes/QuoteFeeProduct.php` : Probablement un `ObjectModel` ou un helper pour gérer des produits "frais" spéciaux qui peuvent être ajoutés aux devis (par exemple, pour les services, les frais personnalisés).
-   `classes/QuoteListHelper.php` : Fournit des méthodes utilitaires pour afficher et filtrer les listes de devis en front et back office.
-   `classes/QuoteMailer.php` : Classe centralisée pour l'envoi de diverses notifications par e-mail liées aux devis.
-   `classes/QuoteNotifyDigest.php` : Logique pour compiler et envoyer des résumés quotidiens ou périodiques de l'activité des devis aux administrateurs.
-   `classes/QuotePdf.php` : Gère la génération de factures proforma PDF pour les devis.
-   `classes/QuoteProductHelper.php` : Méthodes utilitaires pour interagir avec les produits PrestaShop dans le contexte d'un devis.
-   `classes/QuoteQtyHelper.php` : Aide à la gestion et à la validation des quantités dans les devis.
-   `classes/QuoteQuotesManager.php` : Logique métier principale pour la gestion des devis, y compris la création, les mises à jour et les changements de statut.
-   `classes/QuoteReference.php` : Gère la génération et l'unicité des numéros de référence de devis.
-   `classes/QuoteRequestHelper.php` : Aide au traitement et à la validation des demandes de devis soumises par les clients.
-   `classes/QuoteSchema.php` : Définit le schéma de la base de données pour les tables personnalisées utilisées par le module (par exemple, `ps_quote`, `ps_quote_product`, `ps_quote_audit_log`).
-   `classes/QuoteSettingDescTrait.php` : Un trait PHP probablement utilisé pour fournir des descriptions ou des métadonnées communes pour les paramètres du module.
-   `classes/QuoteTaxHelper.php` : Gère les calculs de taxes spécifiques aux devis.
-   `classes/QuoteThemeCompat.php` : Contient la logique pour assurer la compatibilité avec divers thèmes PrestaShop, potentiellement en détectant les fonctionnalités du thème ou en fournissant des surcharges.
-   `classes/QuoteTimeline.php` : Gère et affiche la chronologie des événements pour un devis spécifique (similaire à l'historique des commandes).
-   `classes/QuoteValidityHelper.php` : Méthodes utilitaires pour calculer et valider les dates d'expiration des devis.
-   `classes/QuoteVisibility.php` : Contrôle la visibilité des éléments liés aux devis sur le front office (par exemple, qui peut demander un devis, où les boutons apparaissent).

### 4.4 Actifs JavaScript (`views/js/`)

-   `lib/emailTemplatesManager/js/emailTemplatesManager.js` : Logique front-end pour l'éditeur de modèles d'e-mail dans le back-office.
-   `lib/searchTool/views/js/autocomplete.js` : Fournit la fonctionnalité d'autocomplétion pour la recherche de produits ou de clients dans l'éditeur de devis du back-office.
-   `views/js/admin-audience-picker.js` : Gère la logique de sélection des groupes de clients ou des clients spécifiques pour la visibilité ou le ciblage des devis dans l'administration.
-   `views/js/adminQuoteApi.js` : JavaScript pour l'écran de configuration de l'API d'administration, gérant potentiellement la génération de clés ou l'affichage de la documentation de l'API.
-   `views/js/adminQuoteDashboard.js` : Scripts pour les éléments interactifs ou la visualisation des données sur le tableau de bord d'administration.
-   `views/js/adminQuoteDetail.js` : Gère les interactions dynamiques dans la vue détaillée du devis dans le back-office (par exemple, ajout de produits, application de remises, changements de statut).
-   `views/js/adminQuoteEditor.js` : JavaScript principal pour le formulaire de création/édition de devis du back-office, y compris la sélection de produits, les mises à jour de quantité et les ajustements de prix.
-   `views/js/adminQuoteSelector.js` : Utilisé pour sélectionner des devis, éventuellement dans une modale ou un contexte lié.
-   `views/js/adminQuotesList.js` : Scripts pour la liste des devis d'administration, y compris le filtrage, le tri et les actions groupées.
-   `views/js/front.js` : JavaScript général du front-office pour le module, gérant les clics sur les boutons, les pop-ups modales pour les demandes de devis, les soumissions de formulaires et les mises à jour dynamiques.

### 4.5 Feuilles de style CSS (`views/css/`)

-   `lib/emailTemplatesManager/css/emailTemplatesManager.css` : Style pour l'éditeur de modèles d'e-mail dans le back-office.
-   `lib/searchTool/views/css/autocomplete.css` : Styles pour les résultats de recherche d'autocomplétion (par exemple, recherche de produits).
-   `views/css/admin-audience-picker.css` : Style pour l'interface de sélection de client/public dans l'administration.
-   `views/css/admin_quoteenterprise.css` : Feuille de style principale pour les interfaces du back-office du module (liste des devis, détail, journal d'audit).
-   `views/css/front-hummingbird.css` : Ajustements de style spécifiques au front-office pour le thème par défaut "Hummingbird" de PrestaShop.
-   `views/css/front.css` : Style général du front-office pour les boutons de devis, les formulaires et les vues du compte client. Les développeurs peuvent surcharger des classes comme `.quoteenterprise-button`, `.quoteenterprise-form`, `.quoteenterprise-list` dans leur thème.

### 4.6 Structure des templates Smarty (`views/templates/`)

#### Templates de hook (`views/templates/hook/`)

-   `hook/adminOrderQuote.tpl` : Rend un bloc lié au devis dans la page de détail de commande standard de PrestaShop dans l'administration.
-   `hook/cartQuoteButton.tpl` : Affiche le bouton ou le lien "Demander un devis" sur la page du panier.
-   `hook/customerAccount-hummingbird.tpl` : Rend le lien de la liste des devis dans l'espace compte du client pour le thème Hummingbird.
-   `hook/customerAccount.tpl` : Rend le lien de la liste des devis dans l'espace compte du client pour les thèmes classiques.
-   `hook/productListQuote.tpl` : Affiche un bouton ou une option de devis sur les pages de liste de produits (catégorie, résultats de recherche).
-   `hook/quoteFloatButton.tpl` : Rend le bouton de devis flottant persistant sur le front office.
-   `hook/quoteListModal.tpl` : Template pour une fenêtre modale affichant une liste de devis.
-   `hook/quoteRequestButton.tpl` : Affiche le bouton "Demander un devis" sur les pages de produits individuelles.
-   `hook/quoteRequestModal.tpl` : Template pour la fenêtre modale qui ouvre le formulaire de demande de devis.

#### Templates d'administration (`views/templates/admin/`)

-   `admin/api.tpl` : Rend l'interface de configuration de l'API et de gestion des clés.
-   `admin/audience-picker.tpl` : Template pour l'outil de sélection de client/groupe dans l'administration.
-   `admin/audit.tpl` : Affiche le tableau du journal d'audit dans le back-office.
-   `admin/dashboard.tpl` : Rend l'aperçu du tableau de bord du module dans le back-office.
-   `admin/notifications.tpl` : Affiche les notifications d'administration liées aux devis.
-   `admin/quoteDetail.tpl` : Le template complet pour visualiser et modifier un seul devis dans le back-office.
-   `admin/quotes.tpl` : Rend le tableau principal de la liste des devis dans le back-office.
-   `admin/quotesOverview.tpl` : Une section de résumé ou d'aperçu pour les devis, éventuellement sur le tableau de bord.
-   `admin/scopeSelector.tpl` : Template pour la sélection de la portée (par exemple, boutique, langue) dans l'administration.
-   `admin/visibilityConfigurator.tpl` : Template pour la configuration des règles de visibilité des devis.
-   `admin/_api_documentation_modal.tpl` : Rend une fenêtre modale avec la documentation de l'API pour les développeurs.
-   `admin/_bulk_options.tpl` : Template pour les listes déroulantes d'actions groupées dans les listes d'administration.

#### Templates Front-office (`views/templates/front/`)

-   `front/list.tpl` : Affiche la liste des devis du client dans son compte.
-   `front/request.tpl` : Le template principal pour le formulaire de demande de devis du client.
-   `front/view.tpl` : Affiche la vue détaillée d'un seul devis pour le client.
-   `front/_requestComplianceFields.tpl` : Template partiel pour les champs supplémentaires liés à la conformité dans le formulaire de demande de devis.
-   `front/_requestLinesTable.tpl` : Template partiel pour l'affichage des lignes de produits dans un formulaire de demande de devis.

#### Templates PDF (`views/templates/pdf/`)

-   `pdf/quote.tpl` : Template utilisé pour générer le contenu de la facture proforma PDF.

### 4.7 Schéma de la base de données et carte des hooks

#### Tables de la base de données

Le module crée des tables personnalisées, généralement préfixées par `ps_` (ou votre préfixe personnalisé). Les tables clés incluent :

-   `ps_quote` : Stocke les détails principaux du devis (ID client, statut, total, validité, référence, etc.).
-   `ps_quote_product` : Stocke les produits individuels et leurs quantités/prix associés à chaque devis.
-   `ps_quote_audit_log` : Enregistre toutes les modifications et actions effectuées sur les devis à des fins d'audit.
-   `ps_quote_api_key` : Stocke les clés API pour les intégrations externes.
-   `ps_configuration` : Les paramètres du module y sont stockés avec des clés comme `QUOTEENTERPRISE_ENABLE`, `QUOTEENTERPRISE_MIN_VALUE`, etc.

#### Tableau des hooks enregistrés

| Nom du hook | Moment d'exécution | Objectif technique |
| --- | --- | --- |
| `displayHeader` | Dans la section `<head>` de chaque page. | Injection d'actifs CSS/JS, de balises meta ou d'initialisation globale du module. |
| `displayRightColumn` | Dans la colonne de droite de votre boutique (si activée par le thème). | Affichage du bouton de devis flottant ou d'un bloc de demande de devis statique. |
| `displayLeftColumn` | Dans la colonne de gauche de votre boutique (si activée par le thème). | Affichage du bouton de devis flottant ou d'un bloc de demande de devis statique. |
| `displayFooter` | Dans la section du pied de page de chaque page. | Affichage du bouton de devis flottant ou d'un bloc de demande de devis statique. |
| `displayProductButtons` | Sur la page produit, près du bouton "Ajouter au panier". | Affichage du bouton "Demander un devis" sur les pages produits. |
| `displayShoppingCartFooter` | Dans le récapitulatif du panier, sous la liste des produits. | Affichage du bouton "Demander un devis" pour convertir le panier en devis. |
| `displayCustomerAccount` | Sur la page "Mon compte" du client. | Ajout d'un lien vers la liste des devis du client. |
| `actionValidateOrder` | Après qu'une commande a été validée avec succès. | Potentiellement utilisé pour lier un devis à la commande résultante ou mettre à jour le statut du devis. |
| `actionAdminControllerSetMedia` | Lorsqu'un contrôleur d'administration charge ses actifs. | Injection d'actifs CSS/JS spécifiques au module pour les pages du back-office. |
| `displayAdminOrder` | Sur la page de détail de commande de l'administration PrestaShop. | Affichage d'un bloc avec des informations sur le devis si la commande provient d'un devis. |
| `actionObjectProductUpdateAfter` | Après la mise à jour d'un produit. | Potentiellement pour mettre à jour les prix des devis si les prix des produits changent (fonctionnalité avancée). |
| `actionObjectProductDeleteAfter` | Après la suppression d'un produit. | Pour gérer les produits supprimés des devis. |
| `actionObjectCustomerDeleteAfter` | Après la suppression d'un client. | Pour gérer les devis associés à un client supprimé. |
| `displayBackOfficeHeader` | Dans le `<head>` de chaque page du back-office. | Injection générale d'actifs du back-office ou configuration globale du module d'administration. |
| `displayBackOfficeTop` | En haut de la zone de contenu du back-office. | Affichage d'alertes spécifiques au module ou de widgets de tableau de bord. |

## 5. Support officiel et mises à jour

Pour les dernières mises à jour du module, les corrections de bugs et le support officiel, veuillez vous connecter à votre compte client sur [MyPresta.eu](https://mypresta.eu/my-account/orders/). Notre équipe de support est disponible pour vous aider avec tout problème ou question que vous pourriez avoir concernant le module Quote Enterprise.
