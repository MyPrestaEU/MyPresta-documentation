---
title: "Avis (commentaires) produits gratuits - Manuel du marchand et guide de configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop Avis (commentaires) produits gratuits par MyPresta.eu."
sidebar:
  label: "Avis (commentaires) produits gratuits"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Free product reviews (comments) sur MyPresta.eu](https://mypresta.eu/modules/advertising-and-marketing/free-product-reviews-comments.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/advertising-marketing/free-product-reviews-comments/)
>
> ---


# Avis (commentaires) produits gratuits

## 1. Exigences et compatibilité
Ce module est conçu pour une large compatibilité avec les versions modernes de PrestaShop et les environnements d'hébergement standard.

-   **Versions de PrestaShop prises en charge** : PrestaShop 1.7.x, 8.x, 9.x
-   **Compatibilité PHP** : PHP 7.1 - 8.5
-   **Exigences d'hébergement** : Les extensions PHP standard (cURL, JSON, OpenSSL) sont requises, qui sont généralement disponibles sur tout environnement d'hébergement moderne compatible PrestaShop. Aucune configuration de serveur inhabituelle ou spécialisée n'est nécessaire.

## 2. Parcours de configuration complet (chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)
Après l'installation, cliquer sur "Configurer" vous mènera à l'écran de configuration principal du module "Avis (commentaires) produits gratuits". C'est ici que vous contrôlez le comportement et l'apparence des avis sur votre boutique.

#### Paramètres généraux

-   **Activer les avis :**
    *   **Ce que fait ce paramètre :** C'est l'interrupteur principal pour l'ensemble du système d'avis.
    *   **Effet de la modification de ce paramètre :**
        *   *Lorsqu'il est activé :* La section des avis apparaîtra sur les pages produits, et les clients pourront lire et soumettre des avis.
        *   *Lorsqu'il est désactivé :* La section des avis sera masquée des pages produits, et aucun nouvel avis ne pourra être soumis ou consulté.
    *   **Valeur recommandée :** OUI
    *   **Scénario/exemple pour le marchand :** Activez ceci pour commencer à collecter et afficher les retours clients immédiatement après l'installation.

-   **Les avis doivent être approuvés par un employé :**
    *   **Ce que fait ce paramètre :** Détermine si les avis sont publiés automatiquement ou nécessitent une approbation manuelle par un administrateur de la boutique.
    *   **Effet de la modification de ce paramètre :**
        *   *Lorsqu'il est activé :* Tous les avis soumis entreront dans un état "en attente" et ne seront pas visibles sur le front office tant qu'un administrateur ne les aura pas approuvés manuellement dans la section de gestion des avis du module. Cela vous permet de filtrer le spam, le contenu inapproprié ou les avis qui ne respectent pas vos directives.
        *   *Lorsqu'il est désactivé :* Les avis sont publiés instantanément après leur soumission, sans aucune intervention humaine.
    *   **Valeur recommandée :** OUI (surtout pour les nouvelles boutiques ou pour maintenir le contrôle qualité)
    *   **Scénario/exemple pour le marchand :** Si vous voulez vous assurer que tous les avis sont appropriés et constructifs avant leur mise en ligne, activez ceci. C'est crucial pour maintenir votre image de marque et prévenir le spam.

-   **Autoriser les avis des invités :**
    *   **Ce que fait ce paramètre :** Contrôle si les visiteurs non connectés (invités) peuvent soumettre des avis.
    *   **Effet de la modification de ce paramètre :**
        *   *Lorsqu'il est activé :* Tout visiteur de votre page produit peut soumettre un avis, même s'il n'a pas de compte ou n'est pas connecté. Il lui sera généralement demandé un nom et une adresse e-mail.
        *   *Lorsqu'il est désactivé :* Seuls les clients connectés à leur compte PrestaShop peuvent soumettre des avis.
    *   **Valeur recommandée :** OUI (pour encourager plus d'avis) ou NON (pour s'assurer que les avis proviennent de clients réels).
    *   **Scénario/exemple pour le marchand :** Si vous voulez maximiser le nombre d'avis, même de la part de simples visiteurs, activez les avis des invités. Si vous préférez ne collecter les avis que de clients vérifiés qui ont acheté chez vous, désactivez ceci.

-   **Temps minimum entre 2 avis du même utilisateur (en secondes) :**
    *   **Ce que fait ce paramètre :** Définit une période de "cooldown" pour empêcher un même utilisateur de soumettre plusieurs avis rapidement pour le même produit.
    *   **Effet de la modification de ce paramètre :**
        *   *Lorsqu'une valeur est définie (par exemple, 3600 pour 1 heure) :* Un utilisateur doit attendre au moins ce nombre de secondes après avoir soumis un avis avant de pouvoir soumettre un autre avis pour le même produit.
        *   *Lorsqu'il est défini sur 0 :* Il n'y a pas de limite de temps, et les utilisateurs peuvent soumettre des avis aussi fréquemment qu'ils le souhaitent.
    *   **Valeur recommandée :** 3600 (1 heure) ou 86400 (24 heures) pour éviter le spam.
    *   **Scénario/exemple pour le marchand :** Pour empêcher un seul client d'inonder un produit de plusieurs avis, définissez ceci sur une durée raisonnable comme 3600 secondes (1 heure).

-   **Afficher les avis sur la page produit :**
    *   **Ce que fait ce paramètre :** Détermine si la liste des avis et le formulaire de soumission sont affichés directement sur la page produit.
    *   **Effet de la modification de ce paramètre :**
        *   *Lorsqu'il est activé :* La section des avis sera visible sur la page produit, permettant aux clients de lire et d'écrire des avis.
        *   *Lorsqu'il est désactivé :* La section des avis sera masquée de la page produit. Cela pourrait être utilisé si vous préférez lier à une page d'avis séparée ou gérer les avis différemment.
    *   **Valeur recommandée :** OUI
    *   **Scénario/exemple pour le marchand :** Pour rendre les avis facilement accessibles aux acheteurs qui parcourent vos produits, gardez ceci activé.

-   **Nombre d'avis par page :**
    *   **Ce que fait ce paramètre :** Contrôle le nombre d'avis affichés sur une seule page dans la liste des avis avant que la pagination ne soit appliquée.
    *   **Effet de la modification de ce paramètre :**
        *   *Lorsqu'une valeur est définie (par exemple, 5) :* Seuls 5 avis seront affichés à la fois, avec des boutons "Suivant" et "Précédent" ou des numéros de page pour naviguer à travers le reste.
        *   *Lorsqu'un nombre très élevé est défini :* Tous les avis pourraient se charger sur une seule page, ce qui peut impacter la vitesse de chargement de la page s'il y a beaucoup d'avis.
    *   **Valeur recommandée :** 5-10
    *   **Scénario/exemple pour le marchand :** Si un produit a de nombreux avis, définir ceci à 5 ou 10 gardera la page produit ordonnée et se chargera rapidement, tout en permettant aux clients de parcourir tous les commentaires.

#### Gestion des critères d'avis

Cette section vous permet de définir des critères spécifiques (par exemple, "Qualité", "Prix", "Fonctionnalités") que les clients peuvent noter en plus de la note globale du produit.

-   **Ajouter un nouveau critère :**
    *   **Ce que cela fait :** Vous permet de créer un nouvel aspect spécifique d'un produit que les clients peuvent noter (par exemple, "Rapport qualité-prix", "Facilité d'utilisation", "Durabilité").
    *   **Effet de la modification de ce paramètre :** Lorsque vous ajoutez un critère, il apparaîtra comme une option de notation supplémentaire dans le formulaire de soumission d'avis sur la page produit. Les clients pourront donner une note par étoiles pour chaque critère que vous définissez.
    *   **Valeur recommandée :** Ajoutez des critères pertinents pour vos produits.
    *   **Scénario/exemple pour le marchand :** Pour une boutique d'électronique, vous pourriez ajouter des critères comme "Performance", "Autonomie de la batterie" et "Design". Pour une boutique de vêtements, "Coupe", "Qualité du matériau" et "Style".

-   **Liste des critères existants :**
    *   **Ce que cela fait :** Affiche un tableau de tous les critères que vous avez précédemment ajoutés, avec des options pour les modifier ou les supprimer.
    *   **Effet de la modification de ce paramètre :** Vous pouvez modifier le nom d'un critère (par exemple, changer "Qualité" en "Qualité du produit") ou supprimer un critère s'il n'est plus pertinent. La suppression d'un critère le retirera des futures soumissions d'avis, mais les avis existants qui utilisaient ce critère pourraient toujours afficher leurs notes pour celui-ci (selon l'implémentation du module).
    *   **Valeur recommandée :** Gardez votre liste de critères à jour et pertinente.
    *   **Scénario/exemple pour le marchand :** Si vous introduisez une nouvelle gamme de produits avec des caractéristiques uniques, vous pourriez ajouter un nouveau critère. Si un critère devient redondant, vous pouvez le supprimer.

#### Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Valeur par défaut / Recommandée | Objectif et impact |
|---|---|---|---|
| Configuration du module | Activer les avis | OUI | Interrupteur principal pour le système d'avis. |
| Configuration du module | Les avis doivent être approuvés par un employé | OUI | Contrôle l'approbation manuelle des avis pour prévenir le spam/contenu inapproprié. |
| Configuration du module | Autoriser les avis des invités | OUI | Permet aux utilisateurs non connectés de soumettre des avis. |
| Configuration du module | Temps minimum entre 2 avis du même utilisateur (en secondes) | 3600 (1 heure) | Empêche le spam d'avis par un seul utilisateur. |
| Configuration du module | Afficher les avis sur la page produit | OUI | Affiche ou masque la section des avis sur les pages produits. |
| Configuration du module | Nombre d'avis par page | 5-10 | Contrôle la pagination pour la liste des avis sur les pages produits. |
| Configuration du module | Ajouter un nouveau critère | N/A | Crée des aspects de notation spécifiques (par exemple, "Qualité", "Prix"). |
| Configuration du module | Liste des critères existants | N/A | Gère (modifie/supprime) les critères d'avis personnalisés. |

## 3. Dépannage pour les marchands et questions fréquemment posées (FAQ)

**Q1 : Mes avis n'apparaissent pas sur la page produit après soumission.**
R : Vérifiez si "Les avis doivent être approuvés par un employé" est activé dans la configuration du module. Si c'est le cas, vous devez les approuver manuellement dans l'interface d'administration du module (généralement sur la page de configuration du module, où vous verrez une liste d'avis). Une fois approuvés, ils apparaîtront sur le front office.

**Q2 : La section des avis semble étrange ou ne correspond pas au design de mon thème.**
R : Il s'agit souvent d'un conflit CSS avec votre thème PrestaShop personnalisé.
    *   **Vider le cache :** Tout d'abord, essayez de vider le cache de votre PrestaShop sous **Paramètres avancés > Performances**.
    *   **Surcharges de thème :** Votre thème peut avoir son propre style pour les éléments d'avis ou peut manquer de style spécifique pour ce module. Vous pourriez avoir besoin d'un webmaster pour inspecter le CSS et appliquer des styles personnalisés pour qu'il s'intègre parfaitement. Le module fournit ses propres fichiers CSS (`myprestacomments.css`, etc.), mais les styles de votre thème pourraient les remplacer.

**Q3 : Les clients se plaignent de ne pas pouvoir soumettre d'avis, ou le formulaire n'apparaît pas.**
R :
    *   **Vérifiez "Activer les avis" :** Assurez-vous que l'interrupteur principal dans la configuration du module est réglé sur OUI.
    *   **Vérifiez "Afficher les avis sur la page produit" :** Assurez-vous que ceci est également activé.
    *   **Avis des invités :** Si les utilisateurs non connectés ne peuvent pas soumettre, vérifiez "Autoriser les avis des invités". S'il est désactivé, seuls les clients connectés peuvent soumettre.
    *   **Temps minimum entre les avis :** Si un utilisateur spécifique ne peut pas soumettre, il pourrait atteindre la limite de "Temps minimum entre 2 avis".

**Q4 : Comment traduire le texte du module dans d'autres langues ?**
R : Vous pouvez traduire le texte du module directement dans PrestaShop :
    1.  Allez dans **International > Traductions**.
    2.  Sélectionnez "Traductions des modules installés" pour le "Type de traduction".
    3.  Choisissez votre thème.
    4.  Sélectionnez la langue que vous souhaitez traduire.
    5.  Recherchez "Avis (commentaires) produits gratuits" dans la liste des modules et cliquez sur "Modifier". Vous pourrez alors modifier toutes les chaînes traduisibles.

**Q5 : Je souhaite supprimer un avis inapproprié ou du spam.**
R : Naviguez vers la page de configuration du module dans le Back Office. Vous devriez voir une liste de tous les avis soumis. De là, vous pouvez généralement "Supprimer" ou "Désapprouver" les avis. Si vous avez activé "Les avis doivent être approuvés par un employé", vous pouvez simplement choisir de ne pas l'approuver.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)
Cette section est strictement destinée aux développeurs, aux webmasters de boutiques et aux agences techniques qui maintiennent ou étendent la boutique.

### 4.1 Aperçu de l'architecture
Le module "Avis (commentaires) produits gratuits" (`myprestacomments`) suit une architecture de module PrestaShop standard, utilisant `ModuleFrontController` pour les interactions front-office et `Module` pour sa configuration principale et la gestion des hooks. Il utilise une table de base de données personnalisée pour stocker les données d'avis et s'appuie sur les templates Smarty pour le rendu des affichages d'avis front-office et des formulaires de configuration back-office. Le module s'intègre au système de hooks de PrestaShop pour injecter son contenu dans les pages produits.

### 4.2 Contrôleurs (`controllers/`)

-   **Contrôleurs Front-Office** :
    *   `controllers/front/default.php`
        *   **Nom de la classe et classe parente** : `MyPrestaCommentsDefaultModuleFrontController` étendant `ModuleFrontController`
        *   **Responsabilité** : Ce contrôleur gère probablement l'affichage initial des avis sur la page produit ou sert de solution de repli pour les actions générales liées aux avis. Il récupérerait généralement les avis pour un produit donné et les transmettrait au template Smarty.
    *   `controllers/front/feedback.php`
        *   **Nom de la classe et classe parente** : `MyPrestaCommentsFeedbackModuleFrontController` étendant `ModuleFrontController`
        *   **Responsabilité** : Ce contrôleur est dédié à la gestion de la soumission de nouveaux avis. Il traite les requêtes POST du formulaire d'avis, valide l'entrée (note, commentaire, critères), vérifie les permissions d'avis des invités et les limites de temps, puis enregistre l'avis dans la base de données. Il gère également le statut d'approbation en fonction de la configuration du module.
    *   `controllers/front/index.php`
        *   **Nom de la classe et classe parente** : `MyPrestaCommentsIndexModuleFrontController` étendant `ModuleFrontController`
        *   **Responsabilité** : Ce contrôleur pourrait servir de point d'entrée général ou gérer les requêtes AJAX liées aux avis, telles que le chargement de plus d'avis via la pagination ou la gestion de la fonctionnalité "signaler un abus".

-   **Contrôleurs d'administration Back-Office** :
    *   Aucun contrôleur d'administration personnalisé (`controllers/admin/`) n'est listé. Cela suggère que l'administration des avis (liste, approbation, suppression) est gérée directement dans la méthode `getContent()` du fichier de module principal (`index.php`) ou via un `AdminController` standard que le module étend ou avec lequel il s'intègre. La présence des templates `list_action_approve.tpl` et `list_action_noabuse.tpl` indique fortement que la gestion des avis est intégrée dans une vue de liste PrestaShop standard, probablement au sein de la page de configuration du module.

### 4.3 Classes et modèles principaux (`classes/`)
Aucune classe personnalisée n'est listée dans le répertoire `classes/`. Cela implique que le module pourrait utiliser une approche plus directe pour l'interaction avec la base de données dans son fichier de module principal ou ses contrôleurs, ou qu'il pourrait exploiter les `ObjectModel`s PrestaShop existants si applicable (bien que peu probable pour des données d'avis personnalisées). Il est probable que la structure des données d'avis soit gérée directement dans `install.sql` et le fichier `index.php` du module.

### 4.4 Actifs JavaScript (`views/js/`)

-   `js/jquery.rating.pack.js`
    *   **Portée** : Front-office
    *   **Description** : Un plugin jQuery pour créer des widgets interactifs de notation par étoiles. Il gère l'affichage visuel des étoiles et capture la sélection de la note de l'utilisateur dans le formulaire de soumission d'avis.
-   `js/jquery.textareaCounter.plugin.js`
    *   **Portée** : Front-office
    *   **Description** : Un plugin jQuery pour compter les caractères ou les mots dans une zone de texte, souvent utilisé pour fournir un retour d'information en temps réel aux utilisateurs sur la longueur de leur avis.
-   `js/moderate.js`
    *   **Portée** : Back-office
    *   **Description** : Ce script gère probablement les actions AJAX pour la modération des avis dans le Back Office. Il serait responsable de l'approbation, de la désapprobation ou de la suppression des avis sans rechargement complet de la page, en interagissant avec la méthode `getContent()` du module ou un contrôleur d'administration caché.
-   `js/myprestacomments.js`
    *   **Portée** : Front-office
    *   **Description** : Le principal JavaScript personnalisé pour le module. Il orchestre la fonctionnalité d'avis du front-office, y compris :
        *   L'initialisation de `jquery.rating.pack.js` pour les notes par étoiles.
        *   La gestion de la soumission du formulaire d'avis (potentiellement via AJAX).
        *   L'affichage des messages de succès ou d'erreur.
        *   La gestion de la pagination ou de la fonctionnalité "charger plus" pour les avis.
        *   Potentiellement la gestion des clics "signaler un abus".
-   `js/productCriterion.js`
    *   **Portée** : Back-office
    *   **Description** : Ce script est utilisé dans le Back Office pour gérer les critères d'avis. Il gère probablement l'ajout, la modification et la suppression dynamiques des champs de critères sur la page de configuration du module, éventuellement en utilisant AJAX pour mettre à jour la base de données.

### 4.5 Feuilles de style CSS (`views/css/`)

-   `myprestacomments.css`
    *   **Portée** : Front-office et Back-office
    *   **Description** : La feuille de style principale du module, contenant les styles généraux pour la section des avis, les notes par étoiles, les formulaires d'avis et potentiellement quelques styles de base du panneau d'administration.
    *   **Sélecteurs clés** : `.myprestacomments_block`, `.myprestacomments_review_list`, `.myprestacomments_form`, `.star_content`, `.comment_item`, `.review_rating`.
-   `myprestacomments16.css`
    *   **Portée** : Front-office et Back-office
    *   **Description** : Probablement une feuille de style de compatibilité pour PrestaShop 1.6.x, contenant des surcharges ou des ajustements spécifiques pour la structure de thème par défaut de cette version.
-   `myprestacomments24.css`
    *   **Portée** : Front-office et Back-office
    *   **Description** : Probablement une feuille de style de compatibilité pour PrestaShop 1.7.x ou 8.x, contenant des surcharges ou des ajustements spécifiques pour la structure de thème par défaut de ces versions (par exemple, thème Classic).
-   `myprestacomments32.css`
    *   **Portée** : Front-office et Back-office
    *   **Description** : Probablement une feuille de style de compatibilité pour PrestaShop 9.x, contenant des surcharges ou des ajustements spécifiques pour la dernière structure de thème par défaut.

### 4.6 Structure des templates Smarty (`views/templates/`)

-   **Templates de hook (`views/templates/hook/`)** :
    *   `myprestacomments/mypresta_myprestacomments.tpl`
        *   **Hook** : Probablement `displayProductButtons` ou `displayProductExtraContent` (ou des hooks similaires de page produit).
        *   **Sortie** : C'est le template principal pour afficher le résumé des avis (note moyenne, nombre d'avis) et le bouton/lien "Écrire un avis" sur la page produit. Il agit souvent comme un wrapper pour la liste complète des avis et le formulaire.
    *   `myprestacomments/mypresta_myprestacomments_reviews_list.tpl`
        *   **Hook** : Rendu dans `mypresta_myprestacomments.tpl` ou directement hooké si le module utilise un onglet séparé.
        *   **Sortie** : Affiche la liste réelle des avis clients individuels, y compris leurs notes, titres, commentaires et informations sur l'évaluateur. Il gérera également la pagination.

-   **Templates d'administration (`views/templates/admin/`)** :
    *   `myprestacomments/views/templates/admin/advert.tpl`
        *   **Sortie** : Affiche probablement une publicité ou un message promotionnel de MyPresta.eu dans la page de configuration du module.
    *   `myprestacomments/views/templates/admin/list_action_approve.tpl`
        *   **Sortie** : Un fragment de template pour un bouton ou un lien d'action "Approuver", utilisé dans une liste d'avis en attente dans le Back Office.
    *   `myprestacomments/views/templates/admin/list_action_noabuse.tpl`
        *   **Sortie** : Un fragment de template pour un bouton ou un lien d'action "Marquer comme non abusif", utilisé dans une liste d'avis signalés dans le Back Office.
    *   `myprestacomments/views/templates/admin/_configure/helpers/form/form.tpl`
        *   **Sortie** : Il s'agit d'une surcharge de template d'aide PrestaShop standard, utilisée pour rendre le formulaire de configuration du module (paramètres généraux, gestion des critères) dans le Back Office. Il définit la mise en page et les champs de saisie pour la méthode `getContent()`.
    *   `myprestacomments/views/templates/admin/_configure/helpers/list/list_content.tpl`
        *   **Sortie** : Une autre surcharge de template d'aide PrestaShop standard, utilisée pour rendre la liste des avis (ou des critères) dans le Back Office, y compris les colonnes pour les détails de l'avis, le statut et les boutons d'action (approuver, supprimer).

-   **Templates Front-office (`views/templates/front/`)** :
    *   `myprestacomments/views/templates/front/feedback.tpl`
        *   **Sortie** : Le template du formulaire de soumission d'avis lui-même. Cela inclut la saisie de la note par étoiles, les champs de texte pour le titre et le commentaire, et potentiellement les champs pour les notes de critères personnalisés. Il est rendu lorsqu'un client clique sur "Écrire un avis".

### 4.7 Schéma de la base de données et carte des hooks

-   **Tables de la base de données** :
    *   `myprestacomments/install.sql` : Ce fichier contient les instructions SQL exécutées lors de l'installation du module. Il définira au moins une table personnalisée :
        *   `ps_myprestacomments_reviews` : Stocke les données d'avis réelles (ID produit, ID client, note, titre, commentaire, date, statut d'approbation, statut d'abus).
        *   `ps_myprestacomments_criteria` : Stocke les critères d'avis personnalisés définis par le marchand (par exemple, "Qualité", "Prix").
        *   `ps_myprestacomments_review_criterion` : Une table de liaison si les avis peuvent noter plusieurs critères.

-   **Table des hooks enregistrés** :

| Nom du hook | Moment d'exécution | Objectif technique |
|---|---|---|
| `displayHeader` | Dans la section `<head>` de chaque page. | Pour inclure les fichiers CSS et JS du module globalement ou conditionnellement. |
| `displayProductExtraContent` | Sur la page produit, généralement sous la description principale du produit ou dans un onglet. | Pour afficher le résumé des avis, la liste des avis et le formulaire "Écrire un avis". |
| `displayProductButtons` | Sur la page produit, près du bouton Ajouter au panier. | Pour afficher un lien rapide ou un bouton vers la section des avis. |
| `displayFooter` | Dans le pied de page de chaque page. | Moins courant, mais pourrait être utilisé pour un lien général vers les avis ou un contenu spécifique au module. |
| `displayLeftColumn` / `displayRightColumn` | Dans la barre latérale gauche ou droite. | Pourrait être utilisé pour afficher un bloc d'avis récents ou un résumé des avis. |
| `actionValidateOrder` | Après qu'une commande a été validée avec succès. | Potentiellement utilisé pour déclencher un e-mail au client lui demandant un avis sur les produits achetés. |
| `actionProductUpdate` | Après la mise à jour d'un produit dans le Back Office. | Pour vider le cache lié aux avis produits si nécessaire. |
| `actionObjectProductAddAfter` / `actionObjectProductUpdateAfter` | Après l'ajout ou la mise à jour d'un produit. | Pour assurer l'intégrité des données d'avis ou l'invalidation du cache. |

## 5. Support officiel et mises à jour
Pour les mises à jour officielles, le support technique et toute assistance supplémentaire concernant le module "Avis (commentaires) produits gratuits", veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu/). Notre équipe de support est disponible pour vous aider avec les problèmes liés au module et assurer le bon fonctionnement de votre boutique.
