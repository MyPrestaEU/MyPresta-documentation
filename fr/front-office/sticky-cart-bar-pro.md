---
title: "Sticky Cart Bar PRO - Manuel du Marchand & Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop Sticky Cart Bar PRO par MyPresta.eu."
sidebar:
  label: "Sticky Cart Bar PRO - Manuel du Marchand & Guide de Configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Sticky Cart Bar PRO sur MyPresta.eu](https://mypresta.eu/modules/front-office-features/sticky-cart-bar-pro.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/front-office/sticky-cart-bar-pro/)
>
> ---


# Sticky Cart Bar PRO

## 1. Exigences et compatibilité

- **Versions PrestaShop prises en charge** : PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilité PHP** : PHP 7.1 - 8.5
- **Exigences d'hébergement** : Extensions PHP standard (cURL, JSON, OpenSSL).

## 2. Guide de configuration complet (Chaque paramètre regroupé par écran)

Le module Sticky Cart Bar PRO offre un ensemble puissant d'options de configuration, divisées en plusieurs zones clés pour la gestion de vos barres collantes et de vos tests A/B.

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

Lorsque vous cliquez pour la première fois sur « Configurer » le module, vous arrivez sur un tableau de bord qui fournit un aperçu et un accès aux sections principales. Cette page agit comme un hub central.

La page de configuration principale de Sticky Cart Bar PRO est structurée avec des onglets ou des sections pour gérer différents aspects du module.

#### Paramètres généraux / Aperçu du tableau de bord

Cette section présente généralement un résumé de vos barres actives, de vos tests A/B et des liens rapides vers les écrans de gestion principaux.

-   **Ce que fait cette section :** Fournit un aperçu de haut niveau de l'état de votre module et une navigation rapide pour créer de nouvelles barres, gérer celles existantes ou configurer des tests A/B.
-   **Effet de la modification de ce paramètre :** Il s'agit principalement d'un écran de navigation et d'information. Les modifications ici impliquent de cliquer sur des liens vers d'autres écrans de gestion dédiés.
-   **Valeur recommandée :** Consultez ce tableau de bord régulièrement pour surveiller vos barres collantes et vos expériences.

### 2.2 Écrans d'administration dédiés et vues de contrôleur

Le module dispose de contrôleurs d'administration dédiés pour gérer vos barres collantes et vos tests A/B, offrant une interface complète pour la conception, le ciblage et l'analyse.

#### 2.2.1 Gestion des barres de panier collantes (Back Office > Modules > Sticky Cart Bar PRO > **Gérer les barres**)

Cet écran est l'endroit où vous créez, modifiez et gérez toutes vos barres de panier collantes.

-   **Nom de l'écran et emplacement du menu :** Vous le trouverez sous **Modules > Sticky Cart Bar PRO > Gérer les barres** (ou une entrée de menu similaire directement dans la configuration du module).
-   **Actions et paramètres disponibles :**
    *   **Tableau de liste des barres :** Affiche toutes vos barres collantes créées avec des informations clés comme le nom, le statut (actif/inactif) et les expériences assignées.
        *   *Effet :* Fournit une vue organisée de toutes vos barres collantes.
        *   *Recommandé :* Gardez les noms de barre descriptifs pour une identification facile.
    *   **Bouton Ajouter une nouvelle barre :** Lance le processus de création d'une nouvelle barre collante.
        *   *Effet :* Ouvre le « Layout Studio » où vous concevez votre barre.
        *   *Recommandé :* Commencez avec un objectif clair en tête pour votre nouvelle barre (par exemple, « Barre inférieure de page produit - Livraison gratuite »).
    *   **Bouton Modifier (pour les barres existantes) :** Vous permet de modifier une barre collante existante.
        *   *Effet :* Rouvre le Layout Studio avec les paramètres actuels de la barre.
        *   *Recommandé :* Revoyez et mettez à jour régulièrement les barres en fonction des performances ou des promotions.
    *   **Bouton Dupliquer :** Crée une copie exacte d'une barre existante.
        *   *Effet :* Gagne du temps lors de la création de barres similaires ou de variations pour les tests A/B.
        *   *Recommandé :* Utilisez ceci pour créer rapidement une nouvelle barre basée sur un design réussi, puis apportez des ajustements mineurs.
    *   **Basculer le statut (Actif/Inactif) :** Un interrupteur pour activer ou désactiver une barre sans la supprimer.
        *   *Effet :* Une barre active apparaîtra sur votre front office selon ses règles de ciblage ; une barre inactive ne le fera pas.
        *   *Recommandé :* Désactivez les barres saisonnières ou non pertinentes, plutôt que de les supprimer, au cas où vous en auriez à nouveau besoin.
    *   **Bouton Supprimer :** Supprime définitivement une barre collante.
        *   *Effet :* La barre n'apparaîtra plus sur votre boutique.
        *   *Recommandé :* Ne supprimez que les barres dont vous êtes certain de ne plus jamais utiliser.
    *   **Layout Studio (lors de l'ajout/modification d'une barre) :** C'est l'interface de conception principale.
        *   **Éditeur glisser-déposer :** Vous permet de construire visuellement votre barre collante en ajoutant et en arrangeant des éléments.
            *   *Effet :* Vous pouvez personnaliser la mise en page, le contenu et l'apparence de votre barre sans codage.
            *   *Recommandé :* Expérimentez différentes combinaisons d'éléments pour trouver ce qui fonctionne le mieux pour vos produits et votre public.
        *   **Options d'élément :** Chaque élément (par exemple, « Bouton Ajouter au panier », « Image du produit », « Compteur à rebours », « Texte personnalisé ») a ses propres paramètres de style, de contenu et de comportement.
            *   *Effet :* Affinez l'apparence et la fonctionnalité de chaque partie de votre barre.
            *   *Recommandé :* Faites attention aux couleurs, aux polices et aux tailles pour qu'elles correspondent à l'image de marque de votre boutique.
        *   **Préréglages :** Choisissez parmi une bibliothèque de mises en page de barres collantes préconçues.
            *   *Effet :* Commencez rapidement avec une barre d'aspect professionnel.
            *   *Recommandé :* Utilisez les préréglages comme point de départ, puis personnalisez-les pour répondre à vos besoins spécifiques.
        *   **Règles de ciblage :** Définissez *où* et *à qui* la barre collante doit être affichée.
            *   *Effet :* Garantit que votre barre n'est affichée qu'aux clients pertinents sur des pages spécifiques.
            *   *Recommandé :* Ciblez des catégories de produits, des marques ou des groupes de clients spécifiques pour un impact maximal. Exemples :
                *   *Afficher sur :* Toutes les pages produits, ID de produits spécifiques, catégories spécifiques.
                *   *Groupes de clients :* Uniquement les clients connectés, les nouveaux visiteurs, les groupes de clients spécifiques.
                *   *Localisation géographique :* Uniquement les clients de certains pays.
                *   *Type d'appareil :* Ordinateur de bureau, mobile ou les deux.
        *   **Position d'affichage :** Choisissez si la barre apparaît en haut ou en bas de l'écran.
            *   *Effet :* Contrôle le placement visuel de la barre collante.
            *   *Recommandé :* Les barres inférieures sont souvent moins intrusives, tandis que les barres supérieures peuvent être plus proéminentes. Testez les deux !
        *   **Paramètres de visibilité :** Contrôlez quand la barre apparaît (par exemple, après avoir fait défiler une certaine distance, après un délai).
            *   *Effet :* Empêche la barre d'apparaître trop tôt ou trop tard, optimisant l'expérience utilisateur.
            *   *Recommandé :* Un léger délai ou un seuil de défilement peut rendre la barre moins agressive.
-   **Flux de travail recommandé pour la gestion quotidienne de la boutique :**
    1.  **Planifier :** Décidez de l'objectif de votre nouvelle barre collante (par exemple, promouvoir un produit spécifique, offrir la livraison gratuite, réduire l'abandon de panier).
    2.  **Créer :** Utilisez le bouton « Ajouter une nouvelle barre » et le Layout Studio pour concevoir votre barre. Commencez par un préréglage si vous n'êtes pas sûr.
    3.  **Cibler :** Définissez soigneusement les règles de ciblage pour vous assurer que la barre apparaît pour le bon public sur les bonnes pages.
    4.  **Activer :** Activez la barre une fois que vous êtes satisfait de sa conception et de son ciblage.
    5.  **Surveiller :** Utilisez le tableau de bord d'analyse (voir section suivante) pour suivre ses performances.
    6.  **Optimiser :** En fonction des analyses, modifiez la barre pour améliorer son efficacité.

#### 2.2.2 Gestion des tests A/B (Back Office > Modules > Sticky Cart Bar PRO > **Tests A/B**)

Cet écran vous permet de configurer et de gérer des tests A/B pour vos barres collantes, en comparant différentes versions pour voir laquelle est la plus performante.

-   **Nom de l'écran et emplacement du menu :** Vous le trouverez sous **Modules > Sticky Cart Bar PRO > Tests A/B**.
-   **Actions et paramètres disponibles :**
    *   **Tableau de liste des expériences :** Affiche tous vos tests A/B actifs et terminés, y compris leur statut, leurs dates de début/fin et leurs métriques de performance.
        *   *Effet :* Fournit un aperçu de vos efforts de test.
        *   *Recommandé :* Vérifiez régulièrement le statut de vos expériences.
    *   **Bouton Ajouter une nouvelle expérience :** Lance le processus de création d'un nouveau test A/B.
        *   *Effet :* Vous guide dans la sélection d'une barre de contrôle et d'une ou plusieurs barres variantes.
        *   *Recommandé :* Ayez au moins deux barres collantes prêtes (une de contrôle, une variante) avant de commencer une expérience.
    *   **Configuration de l'expérience (lors de l'ajout/modification) :**
        *   **Nom :** Un nom descriptif pour votre test A/B.
            *   *Effet :* Vous aide à identifier l'expérience plus tard.
            *   *Recommandé :* Utilisez des noms comme « Barre inférieure de page produit - Test de couleur de bouton » ou « Barre supérieure vs Barre inférieure ».
        *   **Barre de contrôle :** La barre collante originale ou par défaut que vous souhaitez tester.
            *   *Effet :* C'est votre référence pour la comparaison.
            *   *Recommandé :* Choisissez votre barre la plus performante actuellement ou un design standard.
        *   **Barres variantes :** Une ou plusieurs barres collantes alternatives que vous souhaitez tester.
            *   *Effet :* Ce sont les versions avec des modifications que vous pensez pouvoir améliorer les performances.
            *   *Recommandé :* Concentrez-vous sur le test d'un changement majeur par variante (par exemple, couleur de bouton différente, message différent, position différente).
        *   **Distribution du trafic :** Définissez le pourcentage de votre audience qui voit chaque barre (contrôle vs variantes).
            *   *Effet :* Assure une comparaison équitable en distribuant le trafic uniformément ou comme souhaité.
            *   *Recommandé :* Commencez par une distribution égale (par exemple, 50/50 pour deux barres, 33/33/33 pour trois).
        *   **Objectif :** Définissez la métrique que vous souhaitez optimiser (par exemple, clics « Ajouter au panier », taux de conversion, revenus).
            *   *Effet :* Le module suivra cette métrique pour chaque barre.
            *   *Recommandé :* Choisissez un objectif clair et mesurable directement lié à votre objectif commercial.
        *   **Règles de ciblage :** Similaires au ciblage de barre, mais pour l'expérience elle-même. Garantit que le test A/B ne s'exécute que pour des segments spécifiques.
            *   *Effet :* Vous permet d'exécuter des expériences ciblées sans affecter l'ensemble de votre audience.
            *   *Recommandé :* Si vous testez une barre pour une catégorie spécifique, appliquez le même ciblage à l'expérience.
    *   **Bouton Afficher les analyses :** Accède aux données de performance détaillées pour une expérience spécifique.
        *   *Effet :* Montre quelle barre a le mieux performé en fonction de votre objectif défini.
        *   *Recommandé :* Laissez les expériences s'exécuter suffisamment longtemps pour recueillir des données statistiquement significatives avant de prendre des décisions.
    *   **Bouton Arrêter l'expérience :** Met fin à un test A/B actif.
        *   *Effet :* Le module cessera d'afficher les barres variantes et vous pourrez choisir de rendre la barre gagnante permanente.
        *   *Recommandé :* Arrêtez une expérience une fois qu'un gagnant clair est identifié ou si elle ne produit pas de résultats utiles.
-   **Flux de travail recommandé pour la gestion quotidienne de la boutique :**
    1.  **Émettre une hypothèse :** Identifiez un domaine d'amélioration (par exemple, « Je pense qu'un bouton 'Ajouter au panier' rouge sera plus performant qu'un vert »).
    2.  **Créer des variantes :** Dupliquez votre barre collante existante et apportez la modification spécifique que vous souhaitez tester (par exemple, changer la couleur du bouton).
    3.  **Configurer l'expérience :** Allez à l'écran Tests A/B, cliquez sur « Ajouter une nouvelle expérience » et configurez votre contrôle, vos variantes, votre trafic et votre objectif.
    4.  **Lancer et surveiller :** Démarrez l'expérience et vérifiez régulièrement le tableau de bord d'analyse pour suivre les progrès.
    5.  **Analyser et implémenter :** Une fois l'expérience terminée ou qu'un gagnant clair émerge, implémentez la barre gagnante comme votre barre par défaut.

#### 2.2.3 Tableau de bord d'analyse (Back Office > Modules > Sticky Cart Bar PRO > **Analyses**)

Cet écran fournit des métriques de performance détaillées pour vos barres collantes et vos tests A/B.

-   **Nom de l'écran et emplacement du menu :** Vous le trouverez sous **Modules > Sticky Cart Bar PRO > Analyses**.
-   **Actions et paramètres disponibles :**
    *   **Vue du tableau de bord :** Affiche des graphiques et des diagrammes montrant les métriques clés comme les impressions, les clics, les taux de clics (CTR) et les conversions pour vos barres collantes.
        *   *Effet :* Vous donne une représentation visuelle claire de la performance de vos barres.
        *   *Recommandé :* Utilisez ces données pour comprendre quelles barres sont efficaces et lesquelles nécessitent des améliorations.
    *   **Options de filtre :** Filtrez les données par plage de dates, barre collante spécifique ou expérience.
        *   *Effet :* Vous permet d'explorer des périodes spécifiques ou de comparer les performances de barres individuelles.
        *   *Recommandé :* Comparez les performances avant et après un changement majeur ou une promotion.
    *   **Résultats des tests A/B :** Pour les expériences actives ou terminées, cette section montrera clairement quelle variante est plus performante par rapport au contrôle, souvent avec des indicateurs de signification statistique.
        *   *Effet :* Fournit les preuves nécessaires pour prendre des décisions basées sur les données concernant la conception de vos barres collantes.
        *   *Recommandé :* Ne prenez pas de décisions basées sur de petits échantillons ; attendez une signification statistique.
-   **Flux de travail recommandé pour la gestion quotidienne de la boutique :**
    1.  **Examen régulier :** Vérifiez le tableau de bord d'analyse chaque semaine ou chaque mois pour comprendre les tendances générales de performance.
    2.  **Analyse approfondie :** Si une barre est sous-performante, utilisez les filtres pour enquêter sur des périodes spécifiques ou la comparer à d'autres barres.
    3.  **Prise de décision :** Utilisez les résultats des tests A/B pour choisir en toute confiance les designs gagnants et les implémenter dans votre boutique.

#### 2.2.4 AdminStickyCartBarAbController (stickycartbarpro/controllers/admin/AdminStickyCartBarAbController.php)

Ce contrôleur gère les expériences de test A/B. Il gère la création, la modification, la liste et la suppression des entités `stickycartbar_experiment`.

#### 2.2.5 AdminStickyCartBarProController (stickycartbarpro/controllers/admin/AdminStickyCartBarProController.php)

Ce contrôleur gère les barres de panier collantes individuelles. Il gère la création, la modification, la liste et la suppression des entités `stickycartbar_bar`, y compris l'accès au Layout Studio pour la conception.

#### 2.2.6 index.php (stickycartbarpro/controllers/admin/index.php)

Ceci est un fichier de substitution, généralement utilisé pour empêcher la liste directe des répertoires et ne représente pas un écran configurable en soi.

### 2.3 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Valeur par défaut / Recommandée | Objectif et impact |
| --- | --- | --- | --- |
| **Gérer les barres** | Nom de la barre | Descriptif | Identifie la barre dans le back office. |
| | Layout Studio | N/A | Éditeur glisser-déposer pour le contenu et le style de la barre. |
| | Options d'élément | Varie | Personnalise les éléments individuels (boutons, texte, images). |
| | Préréglages | N/A | Modèles de démarrage rapide pour la conception de la barre. |
| | Règles de ciblage | Toutes les pages produits | Définit où et à qui la barre est affichée. |
| | Position d'affichage | Bas | Contrôle si la barre est en haut ou en bas de l'écran. |
| | Paramètres de visibilité | Après défilement | Contrôle quand la barre apparaît (délai, défilement). |
| | Statut (Actif/Inactif) | Inactif (initialement) | Active/désactive l'affichage de la barre sur le front office. |
| **Tests A/B** | Nom de l'expérience | Descriptif | Identifie le test A/B. |
| | Barre de contrôle | Barre existante | La barre de référence pour la comparaison. |
| | Barres variantes | Nouvelle(s) barre(s) modifiée(s) | Les versions alternatives testées. |
| | Distribution du trafic | Répartition égale | Comment l'audience est divisée entre les barres. |
| | Objectif | Clics Ajouter au panier | La métrique à optimiser (par exemple, clics, conversions). |
| | Règles de ciblage | Toutes les pages produits | Définit où l'expérience s'exécute. |
| | Statut (Actif/Arrêté) | Actif | Contrôle si l'expérience est en cours. |
| **Analyses** | Filtre de plage de dates | Les 30 derniers jours | Filtre les données de performance par période. |
| | Filtre Barre/Expérience | Tout | Filtre les données pour des barres ou des tests spécifiques. |
| | Affichage des métriques | Impressions, Clics, CTR | Affiche les données de performance pour les barres/expériences. |

## 3. Dépannage du marchand et questions fréquemment posées (FAQ)

**Q1 : Ma barre collante n'apparaît pas sur mes pages produits. Que dois-je vérifier ?**
**R1 :**

-   **La barre est-elle « Active » ?** Allez dans **Modules > Sticky Cart Bar PRO > Gérer les barres** et assurez-vous que l'interrupteur de votre barre est réglé sur « Actif ».
-   **Vérifiez les règles de ciblage :** Modifiez votre barre et examinez les « Règles de ciblage ». Assurez-vous qu'elle est configurée pour s'afficher sur les bonnes pages (par exemple, « Toutes les pages produits » ou des catégories/produits spécifiques) et pour les bons groupes de clients.
-   **Videz le cache :** Allez dans **Paramètres avancés > Performances** et cliquez sur « Vider le cache » (ou « Vider le cache Smarty » dans les versions antérieures). Parfois, le cache de PrestaShop empêche les nouvelles modifications du module d'apparaître immédiatement.
-   **Position du module :** Assurez-vous que le module est correctement accroché. Bien que le module gère généralement cela, si vous l'avez désaccroché manuellement, il n'apparaîtra pas. Vérifiez **Design > Positions** et recherchez « Sticky Cart Bar PRO » pour vous assurer qu'il est accroché à `displayHeader` ou `displayFooter` (selon la position de votre barre).

**Q2 : La barre collante a l'air étrange ou ne correspond pas au design de mon thème.**
**R2 :**

-   **Style du Layout Studio :** Allez dans **Modules > Sticky Cart Bar PRO > Gérer les barres**, modifiez votre barre et utilisez les options de style du Layout Studio. Vous pouvez personnaliser les couleurs, les polices, les tailles, le rembourrage et plus encore pour chaque élément et la barre elle-même.
-   **Conflits de thème :** Parfois, le CSS de votre thème personnalisé peut remplacer le style du module. Si les options de style de base du Layout Studio ne résolvent pas le problème, vous pourriez avoir besoin d'un webmaster pour inspecter le CSS (voir la section Développeur).
-   **Compatibilité du module :** Assurez-vous d'avoir téléchargé la version correcte du module pour votre version de PrestaShop.

**Q3 : Comment puis-je traduire le texte de ma barre collante dans d'autres langues ?**
**R3 :**

-   **Traductions du module :** Pour les textes statiques du module (comme les étiquettes de bouton si non personnalisées), allez dans **International > Traductions**. Sélectionnez « Traductions des modules installés », choisissez votre thème, sélectionnez « Sticky Cart Bar PRO », puis la langue que vous souhaitez traduire.
-   **Éléments de texte personnalisés :** Si vous avez ajouté des éléments de texte personnalisés à l'aide du Layout Studio, vous devrez modifier la barre pour chaque langue. Lors de la modification de la barre, vous devriez voir une option pour changer de langue pour les champs de texte, vous permettant de saisir les traductions directement dans le Layout Studio.

**Q4 : Mon test A/B n'affiche pas de résultats clairs ou semble bloqué.**
**R4 :**

-   **Durée et trafic :** Les tests A/B nécessitent suffisamment de temps et de trafic pour recueillir des données statistiquement significatives. Assurez-vous que votre expérience a duré suffisamment longtemps (au moins quelques semaines) et a reçu suffisamment de visiteurs pour tirer des conclusions.
-   **Objectif clair :** Vérifiez que votre test A/B a un « Objectif » clairement défini (par exemple, clics « Ajouter au panier »). Sans objectif, le module ne peut pas mesurer le succès.
-   **Pas de changements majeurs dans la boutique :** Évitez d'apporter des changements importants à votre boutique (par exemple, nouveau thème, promotions majeures) pendant qu'un test A/B est en cours, car cela peut fausser les résultats.

**Q5 : Puis-je avoir plusieurs barres collantes actives en même temps ?**
**R5 :** Oui, vous pouvez créer et activer plusieurs barres collantes. Cependant, vous devez configurer soigneusement leurs **Règles de ciblage** pour éviter les conflits. Par exemple, vous pourriez avoir une barre pour « Toutes les pages produits » en bas, et une autre barre spécifique pour les « Produits de la catégorie X » en haut. Le module priorisera les barres en fonction de leur spécificité et de leur logique interne, mais il est préférable de s'assurer que vos règles de ciblage ne se chevauchent pas de manière à ce que deux barres tentent de s'afficher à la même position sur la même page.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

Cette section est strictement destinée aux développeurs, aux webmasters de boutiques et aux agences techniques qui maintiennent ou étendent la boutique.

### 4.1 Aperçu de l'architecture

Le module Sticky Cart Bar PRO suit une architecture PrestaShop MVC (Model-View-Controller) robuste, tirant fortement parti d'`ObjectModel` pour la persistance des données et de `ModuleFrontController`/`AdminController` pour la gestion des requêtes. Il utilise un système sophistiqué pour la construction de la mise en page, les tests A/B et l'analyse, avec des classes dédiées pour la configuration, le style, le ciblage et la résolution des expériences. Le module utilise une approche modulaire, séparant les préoccupations en classes distinctes pour une meilleure maintenabilité et extensibilité. Le rendu du front-office est principalement basé sur des hooks, avec AJAX pour les interactions dynamiques.

### 4.2 Contrôleurs (`controllers/`)

#### Contrôleurs Front-Office

-   `controllers/front/ajax.php`
    *   **Nom de la classe :** `StickyCartBarProAjaxModuleFrontController` (étend `ModuleFrontController`)
    *   **Responsabilité :** Gère toutes les requêtes AJAX de la barre collante du front-office. Cela inclut :
        *   Le suivi des impressions et des clics pour l'analyse.
        *   La mise à jour dynamique des informations du panier (par exemple, ajout de produits, modification des quantités).
        *   La résolution de la variante de barre collante à afficher pour les tests A/B.
        *   La récupération des données produit pour les sélecteurs de variantes ou les suggestions de vente croisée.
        *   Retourne des réponses JSON.
-   `controllers/front/index.php`
    *   **Nom de la classe :** `StickyCartBarProIndexModuleFrontController` (étend `ModuleFrontController`)
    *   **Responsabilité :** Un contrôleur frontal de substitution. Généralement, il pourrait être utilisé pour une page de module par défaut, mais dans ce module, le rendu du front-office est principalement géré via des hooks et AJAX. Il pourrait servir de solution de repli ou de base pour de futures fonctionnalités.

#### Contrôleurs d'administration Back-Office

-   `controllers/admin/AdminStickyCartBarAbController.php`
    *   **Nom de la classe :** `AdminStickyCartBarAbController` (étend `AdminController`)
    *   **Nom de l'onglet :** Tests A/B (dans le menu principal du module)
    *   **Entité gérée :** `StickyCartBarExperiment` (mappée à la table `ps_stickycartbar_experiment`).
    *   **Responsabilité :** Gère les opérations CRUD pour les expériences de test A/B. Cela inclut :
        *   La liste de toutes les expériences dans un `HelperList`.
        *   La fourniture d'un `HelperForm` pour la création et la modification des détails de l'expérience (nom, barre de contrôle, barres variantes, distribution du trafic, objectif, règles de ciblage).
        *   La gestion de l'activation/désactivation de l'expérience et de la visualisation des résultats.
-   `controllers/admin/AdminStickyCartBarProController.php`
    *   **Nom de la classe :** `AdminStickyCartBarProController` (étend `AdminController`)
    *   **Nom de l'onglet :** Gérer les barres (dans le menu principal du module)
    *   **Entité gérée :** `StickyCartBarLayout` (mappée à la table `ps_stickycartbar_bar`).
    *   **Responsabilité :** Gère les opérations CRUD pour les barres de panier collantes individuelles. Ce contrôleur s'intègre au « Layout Studio » pour la conception visuelle.
        *   La liste de toutes les barres collantes dans un `HelperList`.
        *   La fourniture de l'interface pour le Layout Studio glisser-déposer, y compris la configuration des éléments, le style et les règles de ciblage.
        *   La gestion de la sauvegarde et du chargement des configurations de barre, y compris la structure HTML, le CSS et les paramètres JavaScript.
-   `controllers/admin/index.php`
    *   **Nom de la classe :** N/A (fichier de substitution)
    *   **Responsabilité :** Empêche la liste directe des répertoires pour des raisons de sécurité.

### 4.3 Classes et modèles principaux (`classes/`)

-   `classes/index.php` : Fichier de substitution pour empêcher la liste des répertoires.
-   `classes/ScbpCompatibility.php` : Gère les couches de compatibilité pour différentes versions de PrestaShop (par exemple, différences de `Context`, méthodes d'aide spécifiques).
-   `classes/StickyCartBarAdminUi.php` : Classe utilitaire pour générer des éléments d'interface utilisateur courants ou gérer une logique d'interface utilisateur spécifique dans le panneau d'administration.
-   `classes/StickyCartBarAnalytics.php` : Gère la collecte, le stockage et la récupération des données d'analyse pour les barres collantes et les tests A/B (impressions, clics, conversions).
-   `classes/StickyCartBarConfig.php` : Gère les paramètres de configuration spécifiques au module stockés dans `ps_configuration` (par exemple, activation/désactivation globale du module, paramètres par défaut).
-   `classes/StickyCartBarElementStyles.php` : Gère les propriétés de style et la génération de CSS pour les éléments individuels d'une barre collante.
-   `classes/StickyCartBarExperiment.php`
    *   **Étend :** `ObjectModel`
    *   **Table de base de données :** `ps_stickycartbar_experiment`
    *   **Champs `$definition` :** `id_stickycartbar_experiment`, `name`, `id_control_bar`, `id_variant_bars` (JSON), `traffic_distribution` (JSON), `goal`, `targeting_rules` (JSON), `active`, `date_add`, `date_upd`.
    *   **Méthodes publiques clés :** Opérations CRUD, méthodes pour récupérer les barres de contrôle/variantes, calculer les résultats de l'expérience.
-   `classes/StickyCartBarExperimentMatcher.php` : Détermine si les règles de ciblage d'une expérience donnée correspondent au contexte actuel (client, page, appareil).
-   `classes/StickyCartBarExperimentResolver.php` : Étant donné un ensemble d'expériences actives, détermine quelle barre collante (contrôle ou variante) doit être affichée au visiteur actuel en fonction de la distribution du trafic et des règles de l'expérience.
-   `classes/StickyCartBarExperimentRule.php` : Représente une seule règle de ciblage dans une expérience.
-   `classes/StickyCartBarExperimentVariant.php` : Représente une barre collante variante dans un test A/B.
-   `classes/StickyCartBarLayout.php`
    *   **Étend :** `ObjectModel`
    *   **Table de base de données :** `ps_stickycartbar_bar`
    *   **Champs `$definition` :** `id_stickycartbar_bar`, `name`, `content` (JSON pour les éléments, styles, paramètres), `targeting_rules` (JSON), `position`, `active`, `date_add`, `date_upd`.
    *   **Méthodes publiques clés :** Opérations CRUD, méthodes pour rendre la barre, récupérer ses éléments, appliquer les styles.
-   `classes/StickyCartBarLayoutInstances.php` : Gère les instances de mises en page de barres collantes, potentiellement pour la mise en cache ou l'accès en temps réel.
-   `classes/StickyCartBarLayoutPreset.php` : Représente une seule mise en page de barre collante préconçue.
-   `classes/StickyCartBarLayoutPresets.php` : Gère la collection de préréglages de mise en page disponibles.
-   `classes/StickyCartBarLayoutPresetsBuiltin.php` : Contient les définitions des préréglages de mise en page intégrés par défaut du module.
-   `classes/StickyCartBarListPresenter.php` : Classe d'aide pour le formatage et la présentation des données dans les listes d'administration (par exemple, `HelperList`).
-   `classes/StickyCartBarMatcher.php` : Détermine si les règles de ciblage d'une barre collante (pour une barre non expérimentale) correspondent au contexte actuel.
-   `classes/StickyCartBarRule.php` : Représente une seule règle de ciblage pour une barre collante.
-   `classes/StickyCartBarTargeting.php` : Classe centrale pour l'évaluation de toutes les règles de ciblage (pour les barres et les expériences) par rapport au contexte actuel du front-office.

### 4.4 Actifs JavaScript (`views/js/`)

-   `lib/searchTool/views/js/autocomplete.js` : Fournit la fonctionnalité d'autocomplétion, probablement utilisée dans l'administration pour sélectionner des produits, des catégories ou des fabricants pour les règles de ciblage.
-   `views/js/admin-ab-dashboard.js` : Gère les éléments interactifs et la visualisation des données sur le tableau de bord des tests A/B dans le back office.
-   `views/js/admin-analytics-dashboard.js` : Gère les graphiques, les filtres et l'affichage des données sur le tableau de bord d'analyse.
-   `views/js/admin-audience-picker.js` : Alimente l'interface interactive pour définir les règles de ciblage d'audience (par exemple, sélection de groupes de clients, de pays).
-   `views/js/admin-element-editor.js` : Fournit la logique JavaScript pour l'édition d'éléments individuels dans le Layout Studio (par exemple, ouverture d'une modale pour la saisie de texte, sélecteurs de couleurs).
-   `views/js/admin-layout-builder.js` : Le JavaScript principal pour le Layout Studio glisser-déposer, gérant le placement, le redimensionnement et l'interaction des éléments.
-   `views/js/admin-layout-preview.js` : Gère l'aperçu en temps réel de la barre collante dans le Layout Studio.
-   `views/js/admin-layout-studio.js` : Orchestre tous les composants du Layout Studio, combinant les fonctionnalités de construction, d'édition et d'aperçu.
-   `views/js/admin.js` : JavaScript à usage général pour les pages du back-office du module, y compris les écouteurs d'événements globaux, les soumissions de formulaires et les appels AJAX.
-   `views/js/front.js` : Le JavaScript principal du front-office pour la barre collante.
    *   **Portée :** Front-office.
    *   **Écouteurs d'événements :** Défilements (pour détecter quand afficher/masquer la barre), clics sur les boutons « Ajouter au panier » dans la barre, clics sur les sélecteurs de variantes, soumissions de formulaires.
    *   **Manipulation du DOM :** Insère le HTML de la barre collante dans le DOM, met à jour les quantités du panier, modifie les variantes de produit, affiche/masque les éléments (par exemple, les compteurs FOMO).
    *   **Appels AJAX :** Communique avec `controllers/front/ajax.php` pour suivre les événements, mettre à jour le panier et récupérer le contenu dynamique.
    *   **SDK tiers :** Aucun explicitement listé, mais pourrait potentiellement s'intégrer à des plateformes d'analyse si configuré.

### 4.5 Feuilles de style CSS (`views/css/`)

-   `lib/searchTool/views/css/autocomplete.css` : Styles pour l'outil de recherche d'autocomplétion dans l'administration.
-   `views/css/admin-audience-picker.css` : Styles pour l'interface de ciblage d'audience dans l'administration.
-   `views/css/admin-bars-list.css` : Styles pour la liste des barres collantes dans l'administration.
-   `views/css/admin-config.css` : Styles généraux pour la page de configuration principale du module.
-   `views/css/admin-dashboard.css` : Styles pour le tableau de bord principal du module et potentiellement les aperçus d'analyse/tests A/B.
-   `views/css/admin-element-editor.css` : Styles pour les modales/panneaux d'édition d'éléments dans le Layout Studio.
-   `views/css/admin-layout-builder.css` : Styles principaux pour l'interface de construction de mise en page glisser-déposer.
-   `views/css/admin-layout-preview.css` : Styles pour la zone d'aperçu en temps réel dans le Layout Studio.
-   `views/css/admin-layout-studio.css` : Styles généraux pour le Layout Studio, combinant tous ses composants.
-   `views/css/admin-searchtool.css` : Styles spécifiques pour l'outil de recherche utilisé dans l'administration.
-   `views/css/front-classic.css` : Styles front-office spécifiques pour le thème « Classic » de PrestaShop.
    *   **Composants d'interface utilisateur principaux :** Remplace ou ajoute des styles pour garantir que la barre collante s'intègre bien aux éléments par défaut du thème Classic.
    *   **Sélecteurs de classes CSS clés :** `.scbp-bar`, `.scbp-button`, `.scbp-product-info`, etc., potentiellement avec des remplacements spécifiques au thème.
-   `views/css/front-hummingbird.css` : Styles front-office spécifiques pour le thème « Hummingbird » de PrestaShop (PrestaShop 8.1+).
    *   **Composants d'interface utilisateur principaux :** Similaire à `front-classic.css` mais adapté à la structure et au design du thème Hummingbird.
    *   **Sélecteurs de classes CSS clés :** `.scbp-bar`, `.scbp-button`, etc., avec des ajustements spécifiques à Hummingbird.
-   `views/css/front.css` : Styles front-office généraux pour la barre collante, appliqués à tous les thèmes.
    *   **Composants d'interface utilisateur principaux :** Style de base pour le conteneur de la barre collante, ses éléments (boutons, texte, images, minuteries) et son positionnement (fixe en haut/bas).
    *   **Sélecteurs de classes CSS clés :** `.scbp-bar`, `.scbp-element`, `.scbp-add-to-cart`, `.scbp-product-name`, `.scbp-price`, `.scbp-quantity-selector`, `.scbp-countdown`, `.scbp-stock-indicator`. Les développeurs peuvent remplacer ces classes dans le CSS personnalisé de leur thème.

### 4.6 Structure des modèles Smarty (`views/templates/`)

#### Modèles de hook (`views/templates/hook/`)

-   `sticky-cart-bar-classic.tpl` : Rend la barre collante spécifiquement pour le thème Classic. Ce modèle inclut probablement une structure HTML ou des noms de classes spécifiques au thème pour assurer une intégration transparente.
    *   **Hook :** `displayHeader` ou `displayFooter` (selon la position de la barre et la logique interne du module).
    *   **Sortie :** La structure HTML principale de la barre collante, y compris les espaces réservés pour le contenu dynamique.
-   `sticky-cart-bar-element-inner.tpl` : Rend le contenu interne d'un seul élément dans la barre collante. C'est un partiel réutilisable.
    *   **Hook :** N/A (inclus par d'autres modèles).
    *   **Sortie :** HTML pour un type d'élément spécifique (par exemple, nom du produit, prix, champ de quantité).
-   `sticky-cart-bar-element.tpl` : Rend un seul élément (par exemple, bouton, image, bloc de texte) de la barre collante, enveloppant `sticky-cart-bar-element-inner.tpl` avec des enveloppes d'éléments communes.
    *   **Hook :** N/A (inclus par d'autres modèles).
    *   **Sortie :** HTML pour un seul composant de barre collante stylisé.
-   `sticky-cart-bar-hummingbird.tpl` : Rend la barre collante spécifiquement pour le thème Hummingbird. Similaire à `sticky-cart-bar-classic.tpl` mais adapté au thème plus récent.
    *   **Hook :** `displayHeader` ou `displayFooter`.
    *   **Sortie :** La structure HTML principale de la barre collante, optimisée pour Hummingbird.
-   `sticky-cart-bar-inner.tpl` : Rend le contenu interne de l'ensemble de la barre collante, contenant tous les éléments individuels.
    *   **Hook :** N/A (inclus par `sticky-cart-bar.tpl`).
    *   **Sortie :** Le HTML combiné de tous les éléments configurés pour une barre collante.
-   `sticky-cart-bar.tpl` : Le modèle principal responsable du rendu de la barre de panier collante sur le front office. Il détermine quel modèle spécifique au thème (classic/hummingbird) inclure ou utilise une structure générique.
    *   **Hook :** `displayHeader` ou `displayFooter` (le module s'enregistre sur ces hooks).
    *   **Sortie :** La barre de panier collante complète et rendue, y compris son conteneur, ses éléments et les attributs de données nécessaires pour JavaScript.

#### Modèles d'administration (`views/templates/admin/`)

-   `ab-test-dashboard.tpl` : Rend le tableau de bord principal pour les tests A/B, affichant les listes d'expériences et les données récapitulatives.
-   `ab-tests-tab.tpl` : Rend le contenu de l'onglet « Tests A/B » dans la configuration du module.
-   `analytics-dashboard.tpl` : Rend le tableau de bord d'analyse avec des graphiques et des métriques de performance.
-   `audience-picker.tpl` : Rend le HTML pour l'interface de sélection de ciblage d'audience (par exemple, sélecteurs de pays, de groupes de clients).
-   `bars-tab.tpl` : Rend le contenu de l'onglet « Gérer les barres », y compris la liste des barres collantes.
-   `configure.tpl` : Le modèle de configuration principal du module, agissant comme l'enveloppe pour tous les autres modèles et onglets d'administration.
-   `country-priority-picker.tpl` : Rend un composant d'interface utilisateur spécifique pour la sélection et la priorisation des pays dans les règles de ciblage.

### 4.7 Schéma de base de données et carte des hooks

#### Tables de base de données

-   `ps_stickycartbar_bar` : Stocke la configuration de chaque barre de panier collante individuelle.
    *   `id_stickycartbar_bar` (PK, INT)
    *   `name` (VARCHAR)
    *   `content` (TEXT, encodé en JSON : contient les éléments, les styles, la position, les paramètres de visibilité)
    *   `targeting_rules` (TEXT, encodé en JSON : conditions d'affichage)
    *   `active` (TINYINT)
    *   `date_add` (DATETIME)
    *   `date_upd` (DATETIME)
-   `ps_stickycartbar_experiment` : Stocke la configuration de chaque expérience de test A/B.
    *   `id_stickycartbar_experiment` (PK, INT)
    *   `name` (VARCHAR)
    *   `id_control_bar` (INT, FK vers `ps_stickycartbar_bar`)
    *   `id_variant_bars` (TEXT, tableau encodé en JSON de FK vers `ps_stickycartbar_bar`)
    *   `traffic_distribution` (TEXT, encodé en JSON : pourcentage pour chaque barre)
    *   `goal` (VARCHAR : par exemple, 'add\_to\_cart', 'conversion')
    *   `targeting_rules` (TEXT, encodé en JSON)
    *   `active` (TINYINT)
    *   `date_add` (DATETIME)
    *   `date_upd` (DATETIME)
-   `ps_stickycartbar_analytics` : Stocke les données d'analyse (impressions, clics, conversions) pour les barres et les expériences.
    *   `id_stickycartbar_analytics` (PK, INT)
    *   `id_stickycartbar_bar` (INT, FK)
    *   `id_stickycartbar_experiment` (INT, FK, NULLABLE)
    *   `type` (VARCHAR : 'impression', 'click', 'add\_to\_cart', 'conversion')
    *   `id_customer` (INT, NULLABLE)
    *   `id_guest` (INT, NULLABLE)
    *   `date_add` (DATETIME)
-   **`ps_configuration`** : Stocke les paramètres globaux du module (par exemple, `STICKYCARTBARPRO_ENABLED`, `STICKYCARTBARPRO_ANALYTICS_ENABLED`).

#### Tableau des hooks enregistrés

| Nom du hook | Moment d'exécution | Objectif technique |
| --- | --- | --- |
| `displayHeader` | Dans la section `<head>` de chaque page. | Injecte les fichiers CSS et JavaScript pour la barre collante, et potentiellement la structure HTML initiale si la barre est positionnée en haut. |
| `displayFooter` | Avant la balise `</body>` fermante de chaque page. | Injecte la structure HTML pour les barres collantes positionnées en bas, et toute initialisation JavaScript nécessaire. |
| `actionFrontControllerSetMedia` | Après qu'un contrôleur frontal a défini ses ressources multimédias. | Permet au module d'ajouter conditionnellement son JS/CSS en fonction du contexte de la page actuelle (par exemple, uniquement sur les pages produits). |
| `actionProductUpdate` | Après la mise à jour d'un produit dans le back office. | Potentiellement utilisé pour vider le cache lié aux données produit qui pourraient être affichées dans les barres collantes. |
| `actionObjectProductAddAfter` | Après l'ajout d'un nouveau produit. | Similaire à `actionProductUpdate`. |
| `actionObjectProductUpdateAfter` | Après la mise à jour d'un produit existant. | Similaire à `actionProductUpdate`. |
| `actionObjectProductDeleteAfter` | Après la suppression d'un produit. | Potentiellement utilisé pour nettoyer toute référence au produit supprimé dans les configurations de barre collante. |
| `actionCartSave` | Après la sauvegarde ou la mise à jour d'un panier. | Utilisé pour suivre les événements « Ajouter au panier » pour les objectifs d'analyse et de test A/B. |
| `actionValidateOrder` | Après la validation réussie d'une commande. | Utilisé pour suivre les événements de conversion pour les objectifs d'analyse et de test A/B. |
| `displayBackOfficeHeader` | Dans la section `<head>` de chaque page du back-office. | Injecte le CSS et le JavaScript pour les interfaces d'administration du module (Layout Studio, tableaux de bord). |
| `moduleRoutes` | Lors de l'initialisation du routage d'URL. | Enregistre des routes front-office personnalisées pour les contrôleurs AJAX si nécessaire. |

## 5. Support officiel et mises à jour

Pour les dernières mises à jour, corrections de bugs et support officiel du module Sticky Cart Bar PRO, veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu). Notre équipe de support est disponible pour vous aider avec tout problème ou question concernant la fonctionnalité et la compatibilité du module.
