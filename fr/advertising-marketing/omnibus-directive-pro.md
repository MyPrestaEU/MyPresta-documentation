---
title: "Omnibus Directive Pro - Manuel du Marchand et Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop Omnibus Directive Pro par MyPresta.eu."
sidebar:
  label: "Omnibus Directive Pro - Manuel du Marchand et Guide de Configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Omnibus Directive Pro sur MyPresta.eu](https://mypresta.eu/modules/advertising-and-marketing/omnibus-directive-pro.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/advertising-marketing/omnibus-directive-pro/)
>
> ---


# Omnibus Directive Pro

## 1. Exigences et Compatibilité

- **Versions PrestaShop prises en charge** : PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilité PHP** : PHP 7.1 - 8.5
- **Exigences d'hébergement** : Extensions PHP standard (cURL, JSON, OpenSSL).

## 2. Guide de configuration complet (Chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer > Omnibus Directive Pro)

C'est l'écran de configuration principal où vous contrôlez le comportement et les options d'affichage du module Omnibus Directive Pro.

#### Paramètres généraux

- **Activer le module :**

  - **Ce que fait ce paramètre :** C'est l'interrupteur principal pour activer ou désactiver toutes les fonctionnalités du module.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé :* Le module commencera à suivre les prix, à afficher les informations sur le prix le plus bas, et toutes les autres fonctionnalités configurées deviendront actives.
    - *Lorsqu'il est désactivé :* Le module arrêtera toutes ses opérations, y compris le suivi des prix et l'affichage en front-office. Aucune information sur le prix le plus bas ne sera affichée.
  - **Valeur recommandée :** OUI
  - **Scénario / exemple de marchand :** Activez-le après l'installation pour commencer à vous conformer à la directive. Désactivez-le uniquement si vous devez suspendre temporairement sa fonctionnalité pour la maintenance ou des tests spécifiques.
- **Afficher le prix le plus bas sur la page produit :**

  - **Ce que fait ce paramètre :** Contrôle si le badge ou le texte "prix le plus bas des 30 derniers jours" apparaît sur les pages de produits individuelles lorsqu'un produit est en promotion.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé :* Les informations sur le prix le plus bas seront visibles pour les clients sur chaque page produit où une réduction de prix est active.
    - *Lorsqu'il est désactivé :* Les informations sur le prix le plus bas NE SERONT PAS affichées sur les pages produits, même si un produit est en promotion.
  - **Valeur recommandée :** OUI (Fortement recommandé pour la conformité).
  - **Scénario / exemple de marchand :** Vous devez l'activer pour vous conformer à la Directive Omnibus. Si vous le désactivez, vos pages produits n'afficheront pas les informations requises pendant les soldes.
- **Afficher le prix le plus bas sur les listes de produits (Catégorie, Recherche, etc.) :**

  - **Ce que fait ce paramètre :** Détermine si les informations sur le prix le plus bas sont affichées sur les fiches produits dans les listes (par exemple, pages de catégorie, résultats de recherche, pages de fabricant).
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé :* Le badge du prix le plus bas apparaîtra sur les fiches produits dans les vues de liste, offrant une transparence précoce aux clients.
    - *Lorsqu'il est désactivé :* Les informations sur le prix le plus bas n'apparaîtront que sur la page produit individuelle, pas dans les listes.
  - **Valeur recommandée :** OUI (Recommandé pour une transparence maximale et une visibilité de la conformité).
  - **Scénario / exemple de marchand :** L'activation de cette option aide les clients à identifier rapidement les ventes conformes directement depuis les pages de catégorie, augmentant potentiellement les taux de clics vers les pages produits.
- **Activer le graphique des prix sur la page produit :**

  - **Ce que fait ce paramètre :** Active un graphique interactif sur la page produit qui affiche visuellement l'historique des prix du produit au fil du temps.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé :* Un graphique sera intégré à la page produit, permettant aux clients de voir les fluctuations de prix passées.
    - *Lorsqu'il est désactivé :* Le graphique des prix ne sera pas affiché.
  - **Valeur recommandée :** OUI (Améliore la transparence et la confiance des clients).
  - **Scénario / exemple de marchand :** Les clients sensibles aux prix ou souhaitant vérifier la légitimité d'une vente peuvent utiliser ce graphique. Il ajoute une couche supplémentaire de confiance.
- **URL Cron de nettoyage de l'historique des prix :**

  - **Ce que fait ce paramètre :** Fournit une URL unique qui, lorsqu'elle est accédée, déclenche le processus automatisé du module pour nettoyer les anciennes données d'historique des prix. Cela permet d'optimiser votre base de données.
  - **Effet de la modification de ce paramètre :** C'est un champ en lecture seule. Vous devez configurer une tâche cron sur votre serveur pour visiter régulièrement cette URL.
  - **Valeur recommandée :** Copiez cette URL et configurez une tâche cron.
  - **Scénario / exemple de marchand :** Configurez une tâche cron pour exécuter cette URL une fois par jour (par exemple, à 3h du matin) afin de garantir que votre base de données d'historique des prix reste légère et efficace, l'empêchant de devenir trop volumineuse au fil du temps.
- **Activer le journal d'audit CSV :**

  - **Ce que fait ce paramètre :** S'il est activé, le module générera un fichier CSV contenant un journal détaillé des changements de prix et des calculs du prix le plus bas, ce qui peut être utile pour l'audit et la vérification de la conformité.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé :* Un fichier CSV sera généré et mis à jour avec les informations d'audit.
    - *Lorsqu'il est désactivé :* Aucun journal d'audit ne sera créé ou maintenu.
  - **Valeur recommandée :** NON (Sauf si spécifiquement requis pour l'audit interne ou à des fins légales, car cela peut consommer de l'espace disque).
  - **Scénario / exemple de marchand :** Si votre équipe juridique ou vos auditeurs exigent un enregistrement vérifiable de vos activités de conformité, activez cette option. Sinon, elle n'est généralement pas nécessaire pour le fonctionnement quotidien.

#### Badge Studio

Cette section vous permet de personnaliser l'apparence visuelle du badge "prix le plus bas" affiché dans votre boutique.

- **Type de badge :**

  - **Ce que fait ce paramètre :** Choisissez entre un "Badge intelligent" (hautement personnalisable avec icônes, couleurs et texte) ou un affichage "Texte simple".
  - **Effet de la modification de ce paramètre :**
    - *Badge intelligent :* Débloque des options de personnalisation supplémentaires pour un badge visuellement riche.
    - *Texte simple :* Affiche uniquement du texte brut sans style avancé.
  - **Valeur recommandée :** Badge intelligent (Offre plus de contrôle et une meilleure intégration avec votre thème).
  - **Scénario / exemple de marchand :** Si vous souhaitez un badge proéminent et de marque, choisissez "Badge intelligent". Si vous préférez une approche minimaliste, "Texte simple" pourrait être mieux.
- **Position du badge (Page produit) :**

  - **Ce que fait ce paramètre :** Sélectionnez l'endroit où le badge apparaît sur la page produit. Les options incluent généralement "Près du prix", "Sous le prix", "Hook personnalisé", etc.
  - **Effet de la modification de ce paramètre :** Modifie le placement visuel du badge sur la page produit.
  - **Valeur recommandée :** Près du prix (Placement le plus courant et légalement clair).
  - **Scénario / exemple de marchand :** Testez différentes positions pour voir ce qui s'intègre le mieux à votre thème et est le plus visible pour les clients sans être intrusif.
- **Position du badge (Listes de produits) :**

  - **Ce que fait ce paramètre :** Sélectionnez l'endroit où le badge apparaît sur les fiches produits dans les pages de liste. Les options incluent généralement "Sous le nom du produit", "Sous le prix", "Hook personnalisé", etc.
  - **Effet de la modification de ce paramètre :** Modifie le placement visuel du badge sur les fiches produits.
  - **Valeur recommandée :** Sous le prix (Clair et cohérent avec le placement sur la page produit).
  - **Scénario / exemple de marchand :** Assurez-vous que le badge ne chevauche pas d'autres éléments sur vos fiches produits, surtout sur mobile.
- **Texte du badge :**

  - **Ce que fait ce paramètre :** Personnalisez le texte réel affiché dans le badge. Vous pouvez utiliser des placeholders comme `{lowest_price}` pour la valeur réelle du prix le plus bas.
  - **Effet de la modification de ce paramètre :** Modifie le message que les clients lisent.
  - **Valeur recommandée :** "Prix le plus bas des 30 derniers jours : {lowest\_price}" (Clair et conforme).
  - **Scénario / exemple de marchand :** Vous pouvez traduire ce texte pour différentes langues ou le reformuler légèrement pour correspondre au ton de votre marque, tant que le sens reste clair et conforme.
- **Couleur de fond du badge :**

  - **Ce que fait ce paramètre :** Définit la couleur de fond du Badge intelligent.
  - **Effet de la modification de ce paramètre :** Modifie le fond visuel du badge.
  - **Valeur recommandée :** Une couleur qui contraste bien avec votre texte et votre thème, par exemple, un gris clair ou une couleur d'accent de la marque.
  - **Scénario / exemple de marchand :** Choisissez une couleur qui fait ressortir le badge mais qui reste professionnelle et s'intègre au design de votre boutique.
- **Couleur du texte du badge :**

  - **Ce que fait ce paramètre :** Définit la couleur du texte dans le Badge intelligent.
  - **Effet de la modification de ce paramètre :** Modifie la couleur visuelle du texte.
  - **Valeur recommandée :** Une couleur très lisible sur la couleur de fond choisie, par exemple, noir ou gris foncé.
  - **Scénario / exemple de marchand :** Assurez un contraste élevé pour l'accessibilité et la lisibilité.
- **Icône du badge :**

  - **Ce que fait ce paramètre :** Vous permet de sélectionner une icône à afficher à côté du texte dans le Badge intelligent.
  - **Effet de la modification de ce paramètre :** Ajoute une icône visuelle au badge.
  - **Valeur recommandée :** Une icône pertinente, telle qu'une icône "étiquette" ou "info".
  - **Scénario / exemple de marchand :** Une petite icône claire peut attirer l'attention sur le badge et rendre son objectif plus intuitif.

#### Panneau d'analyse

Cette section fournit des informations sur les performances de votre module et son statut de conformité.

- **Afficher les analyses :**
  - **Ce que fait ce paramètre :** Ce bouton ouvre un panneau dédié dans votre Back Office, affichant des statistiques liées au suivi des prix, aux produits en promotion et au statut de conformité.
  - **Effet de la modification de ce paramètre :** Cliquer sur ce bouton vous dirige vers le tableau de bord d'analyse.
  - **Valeur recommandée :** Vérifiez-le régulièrement.
  - **Scénario / exemple de marchand :** Utilisez le panneau d'analyse pour surveiller le nombre de produits affichant actuellement le prix le plus bas, identifier tout problème potentiel ou examiner le statut de conformité global de votre boutique.

### 2.2 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Par défaut / Recommandé | Objectif et impact |
| --- | --- | --- | --- |
| **Configuration du module** | Activer le module | OUI | Active/désactive toutes les fonctionnalités du module. |
|  | Afficher le prix le plus bas sur la page produit | OUI | Affiche le prix le plus bas des 30 jours sur les pages produits pendant les soldes. |
|  | Afficher le prix le plus bas sur les listes de produits | OUI | Affiche le prix le plus bas des 30 jours sur les pages de catégorie/recherche pendant les soldes. |
|  | Activer le graphique des prix sur la page produit | OUI | Affiche un graphique interactif de l'historique des prix sur les pages produits. |
|  | URL Cron de nettoyage de l'historique des prix | (Copier et configurer) | URL pour le nettoyage automatisé de la base de données. À exécuter quotidiennement. |
|  | Activer le journal d'audit CSV | NON | Crée un journal détaillé des changements de prix pour l'audit. |
| **Badge Studio** | Type de badge | Badge intelligent | Choisissez entre un badge personnalisable ou un texte simple. |
|  | Position du badge (Page produit) | Près du prix | Définit le placement du badge sur les pages produits individuelles. |
|  | Position du badge (Listes de produits) | Sous le prix | Définit le placement du badge sur les fiches produits dans les listes. |
|  | Texte du badge | "Prix le plus bas des 30 derniers jours : {lowest\_price}" | Texte personnalisable pour le badge. |
|  | Couleur de fond du badge | (Dépend du thème) | Définit la couleur de fond du Badge intelligent. |
|  | Couleur du texte du badge | (Dépend du thème) | Définit la couleur du texte du Badge intelligent. |
|  | Icône du badge | (Icône pertinente) | Ajoute une icône visuelle au Badge intelligent. |
| **Panneau d'analyse** | Afficher les analyses | (Cliquer sur le bouton) | Ouvre un tableau de bord pour les statistiques de conformité et de suivi des prix. |

## 3. Dépannage pour les marchands et questions fréquemment posées (FAQ)

**Q1 : Le badge du prix le plus bas n'apparaît pas sur mes pages produits, même si je l'ai activé.**
R :

1.  **Vérifier le statut du module :** Assurez-vous que le paramètre "Activer le module" est réglé sur OUI.
2.  **Produit en promotion ?** Le badge n'apparaît que pour les produits qui sont actuellement en promotion (ont un prix spécifique ou une réduction appliquée). Assurez-vous que le produit que vous testez a une réduction de prix active.
3.  **Vider le cache :** Allez dans **Paramètres avancés > Performances** dans votre Back Office PrestaShop et videz le cache Smarty, le cache du navigateur, et tout autre cache (par exemple, cache CDN) que vous pourriez utiliser.
4.  **Compatibilité du thème :** Bien que le module soit conçu pour une large compatibilité, les thèmes très fortement personnalisés pourraient nécessiter des ajustements mineurs. Si le problème persiste, contactez le support MyPresta.eu.

**Q2 : Le graphique de l'historique des prix n'affiche aucune donnée ou semble incomplet.**
R :

1.  **Module activé :** Assurez-vous que "Activer le graphique des prix sur la page produit" est réglé sur OUI.
2.  **Changements de prix :** Le graphique n'affichera des données que si le produit a eu des changements de prix enregistrés depuis l'installation et l'activation du module. Si le prix d'un produit n'a jamais changé, il n'y aura pas d'historique à afficher.
3.  **Temps de collecte des données :** Il faut du temps au module pour collecter l'historique des prix. Si vous venez de l'installer, les données s'accumuleront au fur et à mesure que les prix changent au fil des jours/semaines.

**Q3 : À quelle fréquence dois-je exécuter la tâche Cron de nettoyage de l'historique des prix ?**
R : Nous recommandons d'exécuter la tâche cron une fois toutes les 24 heures. Cette fréquence est suffisante pour maintenir votre base de données optimisée sans surcharger excessivement votre serveur.

**Q4 : Le style de mon thème personnalisé entre en conflit avec le badge du module. Comment puis-je résoudre ce problème ?**
R : Le "Badge Studio" offre une personnalisation étendue des couleurs, du texte et des icônes. Essayez d'abord d'ajuster ces paramètres pour qu'ils correspondent à votre thème. Si vous rencontrez toujours des conflits de style, vous devrez peut-être demander à un webmaster d'appliquer des remplacements CSS personnalisés. Les fichiers CSS du module sont conçus pour être facilement remplacés par la feuille de style de votre thème.

**Q5 : Que se passe-t-il si je désactive le module ? Est-ce qu'il supprime mes données d'historique des prix ?**
R : La désactivation du module arrêtera son affichage en front-office et ses processus en arrière-plan, mais elle ne supprime généralement pas les données d'historique des prix collectées. Si vous le réactivez plus tard, les données devraient toujours être disponibles. Cependant, pour une suppression complète des données, vous devrez désinstaller le module et choisir de supprimer ses données.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

Cette section fournit une analyse approfondie de l'architecture technique du module Omnibus Directive Pro, destinée aux développeurs, webmasters et agences techniques.

### 4.1 Vue d'ensemble de l'architecture

Le module Omnibus Directive Pro suit un modèle MVC (Modèle-Vue-Contrôleur) PrestaShop standard, en se concentrant sur les hooks basés sur les événements pour l'intégration. Il étend principalement `Module` pour ses fonctionnalités et sa configuration de base, utilise `ModuleFrontController` pour des actions spécifiques en front-office (comme le nettoyage cron), et exploite les templates Smarty pour le rendu. L'historique des prix est géré par interaction directe avec la base de données et les valeurs de `Configuration`. Le module intègre un "Badge Studio" et un "Panneau d'analyse" dans le Back Office pour un contrôle et des informations améliorés pour le marchand.

### 4.2 Contrôleurs (`controllers/`)

#### Contrôleurs Front-Office

- `omnipro/controllers/front/cleanupcron.php`
  - **Nom de la classe et classe parente :** `OmniproCleanupcronModuleFrontController` étend `ModuleFrontController`.
  - **Responsabilité :** Ce contrôleur est conçu pour être accédé via une tâche cron. Lorsqu'il est invoqué, il exécute la logique de nettoyage interne du module pour les données d'historique des prix, supprimant généralement les anciens enregistrements pour maintenir les performances de la base de données. Il ne rend aucune sortie visuelle au navigateur, renvoyant généralement un simple message de succès ou d'erreur.
- `omnipro/controllers/front/index.php`
  - **Nom de la classe et classe parente :** `OmniproIndexModuleFrontController` étend `ModuleFrontController`.
  - **Responsabilité :** Ce contrôleur sert probablement de solution de repli ou de point d'entrée général pour les actions du module en front-office qui ne nécessitent pas de routage spécifique, ou il pourrait s'agir d'un espace réservé. Compte tenu de la fonction principale du module, il est moins susceptible de gérer directement des interactions utilisateur complexes, mais pourrait être utilisé pour une simple récupération de données ou des vérifications de statut.

#### Contrôleurs d'administration Back-Office

Aucun contrôleur d'administration dédié (`controllers/admin/`) n'a été identifié, ce qui suggère que toutes les configurations et analyses du Back Office sont gérées directement dans la méthode `getContent()` du fichier principal du module.

### 4.3 Classes et modèles de base (`classes/`)

Aucune classe personnalisée étendant `ObjectModel` n'a été identifiée dans le répertoire `classes/`. Cela indique que les données d'historique des prix sont probablement stockées directement dans `ps_configuration` ou une table personnalisée gérée par le fichier principal du module (`omnipro/index.php`) sans un wrapper `ObjectModel` dédié.

### 4.4 Actifs JavaScript (`views/js/`)

- `omnipro/views/js/admin-analytics.js`
  - **Portée :** Back-office.
  - **Description :** Ce script est responsable de l'alimentation des éléments interactifs et de la visualisation des données dans le "Panneau d'analyse" du module dans le Back Office. Il gère probablement les requêtes AJAX pour récupérer les données d'analyse, rend les graphiques (par exemple, en utilisant Chart.js ou des bibliothèques similaires), et met à jour l'interface utilisateur en fonction des interactions de l'utilisateur dans le tableau de bord d'analyse.
- `omnipro/views/js/admin-badge-studio.js`
  - **Portée :** Back-office.
  - **Description :** Ce script fournit la fonctionnalité interactive pour l'écran de configuration du "Badge Studio". Il gère les aperçus en temps réel du badge lorsque le marchand ajuste les couleurs, le texte, les icônes et les positions. Il gère probablement les sélecteurs de couleurs, les mises à jour des champs de saisie et le rendu dynamique d'un badge d'aperçu.
- `omnipro/views/js/admin-config.js`
  - **Portée :** Back-office.
  - **Description :** Un script à usage général pour la page de configuration principale du module. Il peut gérer la validation de formulaire, l'affichage conditionnel des paramètres en fonction d'autres sélections (par exemple, afficher la personnalisation du badge uniquement si "Badge intelligent" est sélectionné), et les améliorations générales de l'interface utilisateur pour le formulaire de configuration.
- `omnipro/views/js/front-chart.js`
  - **Portée :** Front-office.
  - **Description :** Ce script est responsable du rendu du graphique interactif de l'historique des prix sur la page produit. Il récupère probablement les données de prix via AJAX (éventuellement à partir d'un contrôleur frontal dédié ou d'un hook), initialise une bibliothèque de graphiques (par exemple, Chart.js), et affiche visuellement l'évolution des prix au client.

### 4.5 Feuilles de style CSS (`views/css/`)

- `omnipro/views/css/admin-analytics.css`
  - **Portée :** Style d'administration du Back-office.
  - **Description :** Feuilles de style spécifiquement pour la mise en page et l'apparence du "Panneau d'analyse" dans la configuration du Back Office du module.
- `omnipro/views/css/admin-badge-studio.css`
  - **Portée :** Style d'administration du Back-office.
  - **Description :** Feuilles de style pour l'interface du "Badge Studio", y compris le style des sélecteurs de couleurs, des éléments d'aperçu et de la mise en page des options de personnalisation.
- `omnipro/views/css/admin-config.css`
  - **Portée :** Style d'administration du Back-office.
  - **Description :** Style général pour le formulaire de configuration principal du module dans le Back Office, garantissant une interface cohérente et conviviale.
- `omnipro/views/css/omnibus-classic.css`
  - **Portée :** Style client du Front-office.
  - **Description :** Fournit un style par défaut pour le badge du prix le plus bas et potentiellement le graphique des prix, spécifiquement adapté aux anciens thèmes "Classic" de PrestaShop ou aux thèmes qui imitent leur structure.
- `omnipro/views/css/omnibus-hummingbird.css`
  - **Portée :** Style client du Front-office.
  - **Description :** Fournit un style par défaut pour le badge du prix le plus bas et potentiellement le graphique des prix, spécifiquement optimisé pour le nouveau thème "Hummingbird" de PrestaShop.
- `omnipro/views/css/omnibus.css`
  - **Portée :** Style client du Front-office.
  - **Description :** Styles de base du front-office pour le badge du prix le plus bas et le graphique des prix, applicables à divers thèmes. Cela contient probablement les règles visuelles fondamentales, avec `omnibus-classic.css` et `omnibus-hummingbird.css` fournissant des remplacements ou des ajouts spécifiques au thème.

### 4.6 Structure des templates Smarty (`views/templates/`)

- `omnipro/lib/searchTool/views/scripts.tpl`
  - **Portée :** Non claire sans contexte, mais `lib` suggère une bibliothèque tierce ou un utilitaire interne. `scripts.tpl` inclut souvent des actifs JS ou CSS.
  - **Description :** Ce template inclut probablement des fichiers JavaScript ou CSS requis par un outil de recherche interne ou un utilitaire utilisé par le module, éventuellement pour le traitement des données ou des composants d'interface utilisateur spécifiques dans l'administration.
- `omnipro/views/templates/admin/analytics-panel.tpl`
  - **Portée :** Template d'administration.
  - **Description :** Rend la structure HTML du "Panneau d'analyse" dans le Back Office, y compris les placeholders pour les graphiques, les statistiques et les tableaux de données.
- `omnipro/views/templates/admin/badge-studio.tpl`
  - **Portée :** Template d'administration.
  - **Description :** Rend le formulaire HTML et la zone d'aperçu pour la configuration du "Badge Studio", permettant aux marchands de personnaliser l'apparence du badge du prix le plus bas.
- `omnipro/views/templates/admin/configure.tpl`
  - **Portée :** Template d'administration.
  - **Description :** Le template de configuration principal du module, rendu par `getContent()` dans `omnipro/index.php`. Il inclut tous les paramètres généraux, et inclut probablement `analytics-panel.tpl` et `badge-studio.tpl` ou des liens vers ceux-ci.
- `omnipro/views/templates/hook/omnibus-badge.tpl`
  - **Portée :** Template de hook (Front-office).
  - **Description :** Ce template est rendu dans divers hooks du front-office (par exemple, `displayProductPriceBlock`, `displayProductListFunctionalButtons`) pour afficher le HTML du badge du prix le plus bas sur les pages produits et les listes. Il reçoit des variables contenant le prix le plus bas et d'autres options de personnalisation du badge.
- `omnipro/views/templates/hook/omnibus.tpl`
  - **Portée :** Template de hook (Front-office).
  - **Description :** Un template de hook plus général, potentiellement utilisé pour intégrer le graphique des prix (`front-chart.js`) ou d'autres contenus liés au module sur la page produit, ou pour l'initialisation générale du module dans `displayHeader` ou `displayFooter`.

### 4.7 Schéma de base de données et carte des hooks

- **Tables de base de données** :

  - Le module stocke probablement ses principaux paramètres de configuration dans `ps_configuration` (par exemple, `OMNIPRO_ENABLED`, `OMNIPRO_DISPLAY_PRODUCT_PAGE`).
  - Compte tenu de la fonctionnalité "historique des prix" et du "nettoyage cron", il est fort probable que le module crée au moins une table de base de données personnalisée (par exemple, `ps_omnipro_price_history`) pour stocker les enregistrements de prix des produits au fil du temps. Cette table contiendrait généralement les champs `id_product`, `id_product_attribute`, `id_shop`, `id_currency`, `price` et `date_add`.
  - Si le "Journal d'audit CSV" est activé, il pourrait stocker des références aux fichiers CSV générés ou aux entrées de journal dans une table dédiée.
- **Table des hooks enregistrés** :

| Nom du hook | Moment d'exécution | Objectif technique |
| --- | --- | --- |
| `displayHeader` | Dans la section `<head>` de chaque page. | Injecter les actifs CSS/JS pour le front-office, initialiser les variables JS à l'échelle du module. |
| `displayProductPriceBlock` | Près du prix du produit sur la page produit. | Rendre le badge du prix le plus bas (`omnibus-badge.tpl`) sur la page produit. |
| `displayProductListFunctionalButtons` | Dans les listes de produits (catégorie, recherche, etc.). | Rendre le badge du prix le plus bas (`omnibus-badge.tpl`) sur les fiches produits. |
| `displayFooterProduct` | En bas de la page produit. | Potentiellement rendre le graphique des prix (`omnibus.tpl` avec `front-chart.js`). |
| `actionProductUpdate` | Après la mise à jour d'un produit dans le Back Office. | Déclencher l'enregistrement de l'historique des prix pour le produit mis à jour. |
| `actionProductAdd` | Après l'ajout d'un nouveau produit. | Initialiser l'enregistrement de l'historique des prix pour le nouveau produit. |
| `actionProductDelete` | Après la suppression d'un produit. | Nettoyer les données d'historique des prix associées. |
| `actionUpdateQuantity` | Après le changement de quantité du produit. | (Moins probable pour l'historique des prix, mais possible pour une logique connexe). |
| `actionUpdateSpecificPrice` | Après l'ajout/la mise à jour d'un prix spécifique (remise). | Crucial pour déclencher le calcul du prix le plus bas et la logique d'affichage. |
| `actionFrontControllerSetMedia` | Avant qu'un contrôleur frontal ne rende sa sortie. | Ajouter conditionnellement du CSS/JS de front-office en fonction du contexte de la page. |
| `actionAdminControllerSetMedia` | Avant qu'un contrôleur d'administration ne rende sa sortie. | Ajouter conditionnellement du CSS/JS de back-office pour les pages de configuration. |

## 5. Support officiel et mises à jour

Pour les dernières mises à jour, corrections de bugs et support officiel du module Omnibus Directive Pro, veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu/). Notre équipe de support est disponible pour vous aider avec tout problème ou question que vous pourriez avoir concernant la fonctionnalité et l'intégration du module.
