---
title: "Homepage Products Pro - Manuel du Marchand et Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop Homepage Products Pro par MyPresta.eu."
sidebar:
  label: "Homepage Products Pro - Manuel du Marchand et Guide de Configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Homepage Products Pro sur MyPresta.eu](https://mypresta.eu/modules/front-office-features/homepage-products-pro.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/front-office/homepage-products-pro/)
>
> ---


# Homepage Products Pro

## 1. Exigences et compatibilité

- **Versions de PrestaShop prises en charge** : PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilité PHP** : PHP 5.6 - 8.5
- **Exigences d'hébergement** : Extensions PHP standard (cURL, JSON, OpenSSL).

## 2. Présentation complète de la configuration (Chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

Après l'installation, cliquer sur « Configurer » vous mènera à la page principale des paramètres de « Homepage Products Pro ». C'est ici que vous contrôlerez le comportement global et les fonctionnalités de vos blocs de produits.

#### Paramètres généraux

- **Activer les onglets internes**

  - **Ce que fait ce paramètre :** Il contrôle si le module peut créer ses propres onglets personnalisés sur la page d'accueil, similaires aux onglets par défaut de PrestaShop « Produits Populaires » ou « Nouveaux Produits ».
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'activé (Oui) :* Vous pourrez créer de nouveaux blocs de produits qui apparaissent comme des onglets cliquables sur votre page d'accueil, permettant aux clients de basculer entre différentes collections de produits.
    - *Lorsqu'désactivé (Non) :* Le module n'affichera les blocs de produits que comme des sections autonomes (par exemple, des carrousels horizontaux ou des blocs de colonnes), sans l'interface à onglets.
  - **Valeur recommandée :** **Oui** (pour exploiter toute la puissance du module pour un contenu de page d'accueil dynamique).
  - **Scénario / exemple marchand :** Vous souhaitez afficher les « Nouveautés », les « Meilleures Ventes » et les « Sélections Saisonnières » sur votre page d'accueil sans la rendre trop longue. L'activation des onglets internes vous permet de placer chacun d'eux dans son propre onglet.
- **Utiliser l'éditeur de texte riche**

  - **Ce que fait ce paramètre :** Détermine si un éditeur visuel (WYSIWYG) est disponible lorsque vous créez ou modifiez des descriptions ou des titres de blocs de produits, facilitant ainsi la mise en forme du texte.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'activé (Oui) :* Vous obtiendrez un éditeur convivial (comme TinyMCE) avec des options de formatage (gras, italique, liens, etc.) pour les champs de texte du module.
    - *Lorsqu'désactivé (Non) :* Vous aurez un champ de saisie de texte brut, vous obligeant à utiliser le HTML de base si vous souhaitez une mise en forme.
  - **Valeur recommandée :** **Oui** (pour une création de contenu plus facile et un meilleur contrôle visuel).
  - **Scénario / exemple marchand :** Vous souhaitez ajouter une courte introduction stylisée au-dessus d'un bloc de produits, comme « Découvrez notre collection **exclusive** ! » L'éditeur de texte riche rend cela simple.
- **Charger lightslider**

  - **Ce que fait ce paramètre :** Contrôle si le module charge la bibliothèque JavaScript LightSlider, qui est utilisée pour créer des carrousels et des sliders de contenu réactifs.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'activé (Oui) :* La bibliothèque LightSlider sera chargée, permettant à vos blocs de produits de s'afficher sous forme de carrousels interactifs et tactiles. Ceci est généralement requis pour les effets visuels du module.
    - *Lorsqu'désactivé (Non) :* La bibliothèque LightSlider ne sera pas chargée. Si votre thème ou un autre module fournit une fonctionnalité de carrousel similaire, vous pourriez désactiver cela pour éviter les conflits ou le chargement redondant. Cependant, si aucune autre solution de carrousel n'est présente, vos blocs de produits pourraient s'afficher sous forme de grilles ou de listes statiques.
  - **Valeur recommandée :** **Oui** (sauf si vous avez une raison spécifique ou un conflit, car c'est essentiel pour les fonctionnalités de carrousel du module).
  - **Scénario / exemple marchand :** Vous souhaitez que votre bloc « Nouveaux Produits » soit un carrousel élégant à défilement horizontal. Ce paramètre garantit que le script nécessaire est chargé pour cette fonctionnalité.
- **Activer l'analyse**

  - **Ce que fait ce paramètre :** Active ou désactive le suivi interne des performances des blocs de produits du module, telles que les vues et les clics.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'activé (Activé) :* Le module collectera des données sur la fréquence à laquelle vos blocs de produits sont consultés et cliqués, fournissant des informations sur leur efficacité.
    - *Lorsqu'désactivé (Désactivé) :* Aucune donnée de performance ne sera collectée ou affichée dans le tableau de bord du module.
  - **Valeur recommandée :** **Activé** (pour obtenir des informations précieuses sur les blocs de produits les plus performants).
  - **Scénario / exemple marchand :** Vous voulez savoir si votre bloc « Meilleures Ventes » génère plus d'engagement que votre bloc « En Promotion ». L'activation de l'analyse fournit ces données.
- **Période d'analyse**

  - **Ce que fait ce paramètre :** Définit la période pour laquelle les données d'analyse internes du module seront affichées.
  - **Effet de la modification de ce paramètre :** Modifie la plage de données affichées dans les rapports d'analyse.
  - **Options :** Les 7 derniers jours, Les 30 derniers jours, Les 90 derniers jours, Les 180 derniers jours, Les 365 derniers jours.
  - **Valeur recommandée :** **Les 30 derniers jours** (un bon équilibre pour les tendances récentes, mais ajustez en fonction de vos besoins de reporting).
  - **Scénario / exemple marchand :** Vous souhaitez examiner les performances de vos blocs de produits de la page d'accueil au cours du dernier mois pour voir si une promotion récente a eu un impact.
- **Activer le cache des blocs**

  - **Ce que fait ce paramètre :** Active un mécanisme de mise en cache pour les blocs de produits générés par le module. La mise en cache stocke une version temporaire du bloc, de sorte qu'il n'a pas besoin d'être reconstruit chaque fois qu'un client visite la page.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'activé (Oui) :* Les blocs de produits se chargeront plus rapidement pour les clients, car le serveur sert une version mise en cache. Cela peut améliorer considérablement les temps de chargement des pages et les performances du serveur, en particulier sur les boutiques à fort trafic.
    - *Lorsqu'désactivé (Non) :* Les blocs de produits seront générés dynamiquement à chaque chargement de page, ce qui peut être plus lent mais garantit que les données de produit les plus récentes sont toujours affichées (par exemple, les niveaux de stock, les prix).
  - **Valeur recommandée :** **Oui** (pour les avantages en termes de performances, sauf si vous avez des données de produit qui changent très rapidement et qui doivent être en temps réel).
  - **Scénario / exemple marchand :** Votre page d'accueil reçoit beaucoup de trafic et vous voulez vous assurer qu'elle se charge le plus rapidement possible. L'activation du cache accélérera l'affichage de vos blocs de produits.
- **TTL du cache (secondes)**

  - **Ce que fait ce paramètre :** Définit la durée (en secondes) pendant laquelle une version mise en cache d'un bloc de produits reste valide avant d'être rafraîchie. (TTL signifie « Time To Live »).
  - **Effet de la modification de ce paramètre :**
    - *Valeur plus élevée :* Les blocs sont mis en cache plus longtemps, ce qui améliore les performances mais peut potentiellement afficher des informations sur les produits légèrement obsolètes (par exemple, si un prix change, il pourrait ne pas être mis à jour sur la page d'accueil avant l'expiration du cache).
    - *Valeur plus faible :* Les blocs sont rafraîchis plus fréquemment, garantissant des informations plus à jour mais avec un gain de performance légèrement moindre.
  - **Valeur recommandée :** **3600** (1 heure) ou **7200** (2 heures) est un bon point de départ. Ajustez en fonction de la fréquence de modification de vos données de produit et de l'importance des mises à jour en temps réel.
  - **Scénario / exemple marchand :** Vous avez une vente flash où les prix changent toutes les heures. Vous pourriez définir le TTL du cache à 3600 secondes (1 heure) pour vous assurer que les prix se mettent à jour relativement rapidement sur la page d'accueil.
- **Détection automatique du thème**

  - **Ce que fait ce paramètre :** Tente de détecter automatiquement votre thème PrestaShop actif pour appliquer un style et des remplacements de modèle appropriés pour une meilleure intégration visuelle.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'activé (Oui) :* Le module essaie d'adapter sa sortie pour correspondre à la structure et au style de votre thème, en utilisant potentiellement des modèles spécifiques au thème (par exemple, `firezy-products17.tpl`). Cela se traduit souvent par un aspect plus homogène.
    - *Lorsqu'désactivé (Non) :* Le module utilisera ses modèles et son style génériques par défaut, qui pourraient ne pas correspondre parfaitement au design de votre thème. Vous pourriez avoir besoin de sélectionner manuellement un thème ou d'appliquer un CSS personnalisé.
  - **Valeur recommandée :** **Oui** (pour la meilleure intégration visuelle prête à l'emploi).
  - **Scénario / exemple marchand :** Vous avez installé le module et les blocs de produits ne semblent pas tout à fait corrects avec votre thème personnalisé. L'activation de cette option pourrait corriger automatiquement le style.

#### Paramètres cachés/avancés (Clés de configuration internes)

Ceux-ci ne sont généralement pas exposés directement en tant que paramètres utilisateur, mais sont des valeurs de configuration que le module utilise en interne. Ils sont listés ici pour l'exhaustivité et la compréhension du développeur.

- `update_`, `mypresta_updates` : Liés aux vérifications de mise à jour du module et aux notifications de MyPresta.eu.
- `hpp_analytics_enabled` : Correspond au paramètre « Activer l'analyse ».
- `hpp_cache_enabled` : Correspond au paramètre « Activer le cache des blocs ».
- `hpp_cache_ttl` : Correspond au paramètre « TTL du cache (secondes) ».
- `hpp_theme_auto_detect` : Correspond au paramètre « Détection automatique du thème ».
- `hpp_analytics_period` : Correspond au paramètre « Période d'analyse ».
- `hpp_carousel_native` : Probablement un indicateur interne pour le type de carrousel, éventuellement lié à LightSlider.
- `PS_NB_DAYS_NEW_PRODUCT` : Paramètre par défaut de PrestaShop pour le nombre de jours pendant lesquels un produit est considéré comme « nouveau ». Le module pourrait l'utiliser pour les blocs « Nouveaux Produits ».
- `PS_CURRENCY_DEFAULT` : ID de la devise par défaut de PrestaShop.
- `hpp_internal_tabs` : Correspond au paramètre « Activer les onglets internes ».
- `hpp_bxslider` : Une ancienne bibliothèque de carrousel, éventuellement un paramètre hérité ou de secours.
- `PS_LANG_DEFAULT` : ID de la langue par défaut de PrestaShop.
- `PS_BO_ALLOW_EMPLOYEE_FORM_LANG` : Paramètre de PrestaShop permettant aux employés de changer la langue du formulaire.
- `hpp_rich_text` : Correspond au paramètre « Utiliser l'éditeur de texte riche ».
- `hpp_theme` : Stocke le nom du thème détecté ou sélectionné manuellement.
- `hpp_customtplpath` : Permet de spécifier un chemin personnalisé pour les modèles, utile pour une intégration de thème avancée.

### 2.2 Écrans d'administration dédiés et vues de contrôleur

Le module « Homepage Products Pro » étend le Back Office de PrestaShop en ajoutant une section dédiée à la gestion de vos blocs de produits.

- **Nom de l'écran et emplacement du menu :**

  - Vous trouverez un nouvel élément de menu, généralement sous **Modules > Homepage Products Pro** ou un nom similaire, qui mènera au tableau de bord du module.
  - Ce tableau de bord est l'endroit où vous créez, modifiez, supprimez et organisez vos blocs de produits.
- **Actions et paramètres disponibles :**

  - **Tableau de liste des blocs de produits :** Cette vue principale affichera une liste de tous les blocs de produits que vous avez créés. Chaque entrée affichera :
    - **Nom :** Le nom interne que vous avez donné au bloc (par exemple, « Meilleures Ventes Page d'Accueil »).
    - **Titre :** Le titre public affiché aux clients (par exemple, « Nos Coups de Cœur ! »).
    - **Hook :** Où le bloc est affiché (par exemple, `displayHome`, `displayHomeTabContent`, `displayLeftColumn`).
    - **Statut :** Si le bloc est activé ou désactivé.
    - **Position :** L'ordre dans lequel les blocs apparaissent dans le même hook.
    - **Actions :** Boutons pour **Modifier**, **Dupliquer** ou **Supprimer** le bloc.
  - **Bouton « Ajouter un nouveau bloc » :** Cliquer sur ce bouton ouvrira un formulaire pour créer un tout nouveau bloc de produits.
  - **Formulaire « Modifier le bloc » :** Lors de l'ajout ou de la modification d'un bloc, vous configurerez généralement :
    - **Nom du bloc :** Un identifiant interne (par exemple, « CollectionÉté2023 »).
    - **Titre d'affichage :** Le titre que les clients voient (par exemple, « Collection d'Été »).
    - **Description :** Un court texte qui apparaît au-dessus des produits (éditeur de texte riche disponible si activé).
    - **Sélection du hook :** Choisissez où le bloc apparaît (par exemple, `displayHome`, `displayHomeTabContent` pour les onglets, `displayLeftColumn`).
    - **Sélection des produits :** C'est crucial. Vous définirez *quels* produits apparaissent dans le bloc. Les options incluent généralement :
      - **Produits spécifiques :** Sélectionnez manuellement des produits individuels à l'aide d'un outil de recherche.
      - **Produits par catégorie :** Sélectionnez une ou plusieurs catégories, et le module affichera les produits de celles-ci.
      - **Nouveaux produits :** Affichez automatiquement les derniers produits ajoutés à votre boutique.
      - **Meilleures ventes :** Affichez automatiquement les produits les plus vendus de votre boutique.
      - **Produits en promotion :** Affichez automatiquement les produits actuellement en promotion.
      - **Produits vedettes :** Produits marqués comme vedettes.
    - **Nombre de produits à afficher :** Limitez le nombre de produits affichés.
    - **Type d'affichage :** Choisissez entre un carrousel/slider ou une grille/liste statique.
    - **Paramètres du carrousel :** Si vous utilisez un carrousel, paramètres pour le nombre d'éléments par diapositive, la lecture automatique, les flèches de navigation, etc.
    - **Sélecteur de visibilité/audience :** Définissez qui voit le bloc (par exemple, tous les clients, des groupes de clients spécifiques, des pays spécifiques).
    - **Spécificité linguistique :** Configurez les titres et les descriptions pour différentes langues.
    - **Statut :** Activez/désactivez le bloc individuel.
    - **Position :** Définissez l'ordre d'affichage par rapport aux autres blocs dans le même hook.
- **Effet des modifications :**

  - **Ajout d'un nouveau bloc :** Un nouvel affichage de produit apparaîtra sur votre front-office dans le hook choisi, présentant les produits sélectionnés selon vos paramètres.
  - **Modification d'un bloc :** Les modifications apportées aux titres, descriptions, sélection de produits, type d'affichage ou paramètres seront immédiatement reflétées sur le front-office (sous réserve du TTL du cache si la mise en cache est activée).
  - **Suppression d'un bloc :** L'affichage du produit sera supprimé de votre front-office.
  - **Changement de position :** L'ordre des blocs dans un hook spécifique sera mis à jour sur le front-office.
  - **Activation/Désactivation :** Bascule la visibilité du bloc sur votre boutique.
- **Flux de travail recommandé pour la gestion quotidienne de la boutique :**

  1.  **Planifiez la mise en page de votre page d'accueil :** Décidez quels types de produits vous souhaitez mettre en avant (nouveaux, meilleures ventes, catégories spécifiques, promotions).
  2.  **Créez de nouveaux blocs :** Pour chaque section planifiée, accédez au tableau de bord du module et cliquez sur « Ajouter un nouveau bloc ».
  3.  **Configurez chaque bloc :**
      -   Donnez-lui un nom interne clair (par exemple, « HP\_Nouveautés »).
      -   Rédigez un titre d'affichage et une description attrayants.
      -   Sélectionnez le hook approprié (par exemple, `displayHome` pour le contenu principal, `displayHomeTabContent` pour les onglets).
      -   Choisissez votre méthode de sélection de produits (manuelle, catégorie, nouveau, etc.).
      -   Ajustez les paramètres d'affichage et de carrousel.
      -   Définissez la position pour contrôler son ordre.
  4.  **Vérifiez sur le front-office :** Vérifiez toujours la page d'accueil de votre boutique après avoir apporté des modifications pour vous assurer que tout semble et fonctionne comme prévu.
  5.  **Surveillez l'analyse :** Vérifiez régulièrement l'analyse du module (si activée) pour comprendre quels blocs fonctionnent bien et ajustez votre stratégie en conséquence.
  6.  **Maintenez et mettez à jour :** Au fur et à mesure que de nouveaux produits arrivent ou que les promotions changent, mettez à jour vos blocs existants ou créez-en de nouveaux pour garder votre page d'accueil fraîche et pertinente.

### 2.3 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Valeur par défaut / Recommandée | Objectif et impact |
| --- | --- | --- | --- |
| Configuration principale | Activer les onglets internes | Oui | Permet la création d'onglets de produits sur la page d'accueil. |
| Configuration principale | Utiliser l'éditeur de texte riche | Oui | Fournit un éditeur visuel pour les champs de texte. |
| Configuration principale | Charger lightslider | Oui | Active les carrousels/sliders de produits. |
| Configuration principale | Activer l'analyse | Activé | Suivi des vues et des clics pour les blocs de produits. |
| Configuration principale | Période d'analyse | Les 30 derniers jours | Définit la période pour les rapports d'analyse. |
| Configuration principale | Activer le cache des blocs | Oui | Améliore la vitesse de chargement des pages en mettant en cache les blocs. |
| Configuration principale | TTL du cache (secondes) | 3600 (1 heure) | Durée de validité des blocs mis en cache. |
| Configuration principale | Détection automatique du thème | Oui | Adapte la sortie du module à votre thème. |
| Gestion des blocs | Nom du bloc | N/A (Défini par l'utilisateur) | Identifiant interne de votre bloc de produits. |
| Gestion des blocs | Titre d'affichage | N/A (Défini par l'utilisateur) | Titre public affiché aux clients. |
| Gestion des blocs | Description | N/A (Défini par l'utilisateur) | Texte affiché au-dessus du bloc de produits. |
| Gestion des blocs | Sélection du hook | `displayHome` / `displayHomeTabContent` | Détermine où le bloc apparaît sur la boutique. |
| Gestion des blocs | Sélection des produits | N/A (Défini par l'utilisateur) | Définit les produits affichés (manuel, catégorie, nouveau, meilleures ventes, etc.). |
| Gestion des blocs | Nombre de produits | N/A (Défini par l'utilisateur) | Limite la quantité de produits affichés. |
| Gestion des blocs | Type d'affichage | Carrousel / Grille | Comment les produits sont présentés visuellement. |
| Gestion des blocs | Visibilité/Audience | Tous les clients | Restreint la visibilité du bloc à des groupes/pays spécifiques. |
| Gestion des blocs | Statut | Activé | Active/désactive la visibilité du bloc sur le front-office. |
| Gestion des blocs | Position | N/A (Défini par l'utilisateur) | Définit l'ordre d'affichage des blocs dans un hook. |

## 3. Dépannage pour les marchands et questions fréquemment posées (FAQ)

**Q1 : Mes blocs de produits n'apparaissent pas sur la page d'accueil, ou ils semblent cassés.**

-   **R :**
    1.  **Vérifier le statut du module :** Assurez-vous que le module « Homepage Products Pro » est activé dans **Modules > Gestionnaire de modules**.
    2.  **Vérifier le statut du bloc :** Allez dans le tableau de bord de configuration du module et vérifiez que les blocs de produits spécifiques que vous avez créés sont « Activés ».
    3.  **Sélection du hook :** Vérifiez à nouveau que vous avez attribué les blocs aux hooks front-office corrects (par exemple, `displayHome` pour le contenu principal, `displayHomeTabContent` pour les onglets, `displayLeftColumn` pour les colonnes).
    4.  **Vider le cache :** Allez dans **Paramètres avancés > Performances** et cliquez sur « Vider le cache ». Parfois, un ancien contenu mis en cache empêche l'affichage de la nouvelle sortie du module.
    5.  **Compatibilité du thème :** Si vous avez un thème personnalisé, essayez d'activer « Détection automatique du thème » dans la configuration principale du module. Si les problèmes persistent, votre thème pourrait nécessiter des ajustements CSS mineurs (voir Q3).

**Q2 : Mes blocs de produits s'affichent, mais les produits ne sont pas mis à jour (par exemple, anciens prix, articles en rupture de stock toujours visibles).**

-   **R :** Il s'agit généralement d'un problème de mise en cache.
    1.  **Cache du module :** Dans la configuration principale du module, vérifiez « Activer le cache des blocs » et « TTL du cache (secondes) ». Si la mise en cache est activée, le bloc pourrait afficher une version plus ancienne et mise en cache. Vous pouvez désactiver temporairement la mise en cache, enregistrer, puis la réactiver, ou simplement attendre que le TTL expire.
    2.  **Cache de PrestaShop :** Allez dans **Paramètres avancés > Performances** et cliquez sur « Vider le cache ». Cela vide tous les caches au niveau de PrestaShop.
    3.  **Cache du navigateur :** Videz le cache et les cookies de votre navigateur, ou consultez votre site dans une fenêtre de navigation privée pour vous assurer que vous ne voyez pas une version mise en cache localement.

**Q3 : Les blocs de produits apparaissent, mais le style est incorrect (par exemple, mauvaises polices, éléments mal alignés, carrousel cassé).**

-   **R :**
    1.  **Détection automatique du thème :** Dans la configuration principale du module, assurez-vous que « Détection automatique du thème » est activé. Cela aide le module à utiliser le style spécifique au thème.
    2.  **Charger LightSlider :** Si les carrousels sont cassés, assurez-vous que « Charger lightslider » est activé dans la configuration du module.
    3.  **Conflits de thème :** Les thèmes personnalisés ont parfois des CSS ou JavaScript conflictuels. Si vous suspectez cela, essayez de passer temporairement à un thème PrestaShop par défaut (comme Classic) pour voir si le problème se résout. Si c'est le cas, votre thème personnalisé nécessite des ajustements.
    4.  **CSS personnalisé :** Vous pourriez avoir besoin d'ajouter du CSS personnalisé à la feuille de style de votre thème pour remplacer les styles par défaut du module et correspondre à votre thème. Un développeur web peut vous aider.

**Q4 : J'ai créé un nouveau bloc de produits, mais il n'apparaît pas comme un onglet sur la page d'accueil.**

-   **R :**
    1.  **Activer les onglets internes :** Dans la configuration principale du module, assurez-vous que « Activer les onglets internes » est défini sur « Oui ».
    2.  **Hook correct :** Assurez-vous que la **Sélection du hook** du bloc de produits est définie sur `displayHomeTabContent`. Les blocs définis sur `displayHome` ou les colonnes n'apparaîtront pas comme des onglets.
    3.  **Positionnement :** Vérifiez la position de vos blocs à onglets. S'ils sont très bas dans l'ordre, ils pourraient ne pas apparaître si d'autres modules occupent de l'espace.

**Q5 : Mon éditeur de texte riche ne fonctionne pas, ou je ne peux pas formater le texte.**

-   **R :**
    1.  **Activer l'éditeur de texte riche :** Dans la configuration principale du module, assurez-vous que « Utiliser l'éditeur de texte riche » est défini sur « Oui ».
    2.  **Problèmes de navigateur :** Essayez un autre navigateur web ou videz le cache de votre navigateur actuel.
    3.  **Conflits JavaScript :** Occasionnellement, d'autres modules ou scripts de thème peuvent interférer avec l'éditeur de texte riche. Si le problème persiste, consultez un développeur.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

Cette section fournit une analyse approfondie de l'architecture technique et de la base de code du module « Homepage Products Pro », conçue pour les développeurs, les webmasters et les agences techniques.

### 4.1 Aperçu de l'architecture

Le module « Homepage Products Pro » (`hpp`) suit une architecture de module PrestaShop standard, exploitant principalement les hooks pour l'affichage en front-office et une méthode `getContent()` pour sa configuration en back-office. Il implémente un tableau de bord personnalisé pour la gestion des blocs de produits, qui sont stockés comme des valeurs de configuration ou potentiellement dans des tables de base de données personnalisées (bien qu'aucune classe `ObjectModel` explicite n'ait été identifiée dans l'inventaire fourni, les données complexes sont souvent sérialisées dans `ps_configuration` ou gérées via des classes d'aide). Le module s'appuie fortement sur les templates Smarty pour le rendu de ses différents blocs de produits et interfaces d'administration. Il intègre des bibliothèques externes comme LightSlider pour les carrousels et TinyMCE pour l'édition de texte riche. Les mécanismes d'analyse et de mise en cache sont intégrés pour les performances et les informations.

### 4.2 Contrôleurs (`controllers/`)

#### Contrôleurs Front-Office

-   `hpp/controllers/front/index.php`
    -   **Nom de la classe :** `HppIndexModuleFrontController` (probablement, basé sur la convention de nom de fichier)
    -   **Classe parente :** `ModuleFrontController`
    -   **Responsabilité :** Ce contrôleur sert probablement de point d'entrée général pour les actions du module en front-office qui ne rentrent pas dans des catégories AJAX ou de suivi spécifiques. Il pourrait gérer le chargement initial des données ou le rendu de types de blocs spécifiques s'il n'est pas entièrement basé sur des hooks.
-   `hpp/controllers/front/lazyblock.php`
    -   **Nom de la classe :** `HppLazyblockModuleFrontController`
    -   **Classe parente :** `ModuleFrontController`
    -   **Responsabilité :** Ce contrôleur est conçu pour gérer les requêtes AJAX pour le chargement paresseux des blocs de produits. Lorsqu'un utilisateur fait défiler la page ou interagit avec un onglet, ce contrôleur serait appelé pour récupérer les données du produit et rendre le HTML pour un bloc spécifique, améliorant ainsi les temps de chargement initiaux de la page. Il prend probablement des paramètres comme l'ID du bloc, le numéro de page ou les critères de filtre.
-   `hpp/controllers/front/track.php`
    -   **Nom de la classe :** `HppTrackModuleFrontController`
    -   **Classe parente :** `ModuleFrontController`
    -   **Responsabilité :** Ce contrôleur est responsable de la gestion des requêtes de suivi analytique. Lorsqu'un bloc de produits est consulté ou qu'un produit dans un bloc est cliqué, une requête est envoyée à ce contrôleur pour enregistrer l'événement, contribuant ainsi aux données d'analyse internes du module.

#### Contrôleurs d'administration Back-Office

Aucun fichier `AdminController` dédié n'a été identifié dans l'inventaire fourni. Cela suggère que la gestion du back-office du module (création/édition de blocs de produits) est gérée directement dans la méthode `getContent()` du fichier `hpp.php`, potentiellement en utilisant les classes `HelperForm` et `HelperList` de PrestaShop, ou une approche de rendu personnalisée au sein de la page de configuration principale du module.

### 4.3 Classes et modèles principaux (`classes/`)

Aucune classe PHP personnalisée étendant `ObjectModel` ou d'autres fonctionnalités de base n'a été explicitement listée dans le répertoire `classes/`. Cela implique que :

-   Les données complexes (comme les configurations de blocs de produits individuels) sont probablement stockées sous forme de tableaux sérialisés ou de chaînes JSON dans la table `ps_configuration`, gérées directement par le fichier de module `hpp.php`.
-   Alternativement, le module pourrait utiliser une approche plus procédurale ou s'appuyer sur des classes d'aide définies directement dans `hpp.php` ou ses bibliothèques incluses.
-   Le répertoire `lib/` contient diverses classes d'aide et bibliothèques externes (par exemple, `searchTool`, `smartyTemplatesManager`, `src`). Celles-ci sont probablement utilisées pour des fonctionnalités spécifiques comme la recherche de produits, la gestion de modèles ou l'implémentation de carrousels, plutôt que pour définir des entités commerciales de base.

### 4.4 Actifs JavaScript (`views/js/`)

-   `hpp/js/script.js`
    -   **Portée :** Front-office.
    -   **Détails :** Contient probablement la logique principale du front-office pour l'initialisation des carrousels de produits (LightSlider), la gestion du changement d'onglet et les interactions générales de l'interface utilisateur liées aux blocs de produits. Il pourrait également contenir la logique de chargement paresseux ou de suivi analytique de base.
-   `hpp/js/tinymce16-force-urls.inc.js`
    -   **Portée :** Back-office.
    -   **Détails :** Un script spécifique pour l'éditeur de texte riche TinyMCE, probablement pour garantir que les URL sont correctement gérées et formatées dans l'éditeur, en particulier dans les contextes PrestaShop 1.6 plus anciens.
-   `hpp/lib/searchTool/views/js/autocomplete.js`
    -   **Portée :** Back-office.
    -   **Détails :** Fournit la fonctionnalité JavaScript pour un champ de recherche à saisie semi-automatique, utilisé lors de la sélection de produits spécifiques pour un bloc de produits dans la configuration du back-office. Il effectue probablement des appels AJAX pour récupérer des suggestions de produits.
-   `hpp/lib/smartyTemplatesManager/js/smartyTemplatesManager.js`
    -   **Portée :** Back-office.
    -   **Détails :** Gère la création, l'édition et la sélection dynamiques de templates Smarty dans l'interface du back-office, probablement pour que les utilisateurs avancés puissent personnaliser les mises en page des blocs.
-   `hpp/lib/src/js/lightslider.js`
    -   **Portée :** Front-office.
    -   **Détails :** La bibliothèque LightSlider principale, responsable de la création de carrousels de contenu réactifs et tactiles pour les blocs de produits. Elle gère les transitions de diapositives, la navigation et la réactivité.
-   `hpp/views/js/admin-audience-picker.js`
    -   **Portée :** Back-office.
    -   **Détails :** Fournit la logique interactive pour l'interface « Sélecteur d'audience » dans le back-office, permettant aux administrateurs de sélectionner des groupes de clients ou des pays spécifiques pour la visibilité des blocs.
-   `hpp/views/js/adminHppDashboard.js`
    -   **Portée :** Back-office.
    -   **Détails :** Le JavaScript principal pour le tableau de bord du back-office du module, gérant les interactions comme l'ajout/édition de blocs, le réordonnancement par glisser-déposer et la gestion générale de l'interface utilisateur.
-   `hpp/views/js/adminHppDashboardDemo.js`
    -   **Portée :** Back-office.
    -   **Détails :** Contient probablement du JavaScript spécifique à la démo pour le tableau de bord du back-office, éventuellement pour la configuration initiale ou la présentation des fonctionnalités, et pourrait ne pas être actif dans un environnement de production.
-   `hpp/views/js/hpp-analytics.js`
    -   **Portée :** Front-office.
    -   **Détails :** Gère le côté front-office du suivi analytique, envoyant des données (par exemple, vues de blocs, clics sur les produits) au contrôleur `track.php` via AJAX.
-   `hpp/views/js/hpp-lazyload.js`
    -   **Portée :** Front-office.
    -   **Détails :** Implémente le chargement paresseux pour les blocs de produits ou leur contenu, effectuant des appels AJAX à `lazyblock.php` lorsque les blocs entrent dans la fenêtre d'affichage ou que les onglets sont activés.

### 4.5 Feuilles de style CSS (`views/css/`)

-   `hpp/css/global.css`
    -   **Portée :** Front-office.
    -   **Détails :** Contient des styles généraux et globaux pour la sortie front-office du module, assurant une cohérence visuelle de base.
-   `hpp/css/homefeaturedslider.css`
    -   **Portée :** Front-office.
    -   **Détails :** Styles spécifiques pour le composant de slider de produits vedettes de la page d'accueil, probablement pour les anciennes versions de PrestaShop ou des implémentations de carrousel spécifiques.
-   `hpp/css/hpp.css`
    -   **Portée :** Front-office.
    -   **Détails :** La feuille de style principale du front-office pour le module, définissant l'apparence des blocs de produits, des grilles et des carrousels.
-   `hpp/css/internal-tabs.css`
    -   **Portée :** Front-office.
    -   **Détails :** Styles spécifiques à l'interface à onglets interne sur la page d'accueil, y compris la navigation par onglets et les zones de contenu.
-   `hpp/css.css`
    -   **Portée :** Front-office.
    -   **Détails :** Potentiellement une feuille de style générale héritée ou supplémentaire.
-   `hpp/lib/searchTool/views/css/autocomplete.css`
    -   **Portée :** Back-office.
    -   **Détails :** Styles pour le champ de recherche à saisie semi-automatique utilisé dans le back-office pour la sélection de produits.
-   `hpp/lib/smartyTemplatesManager/css/smartyTemplatesManager.css`
    -   **Portée :** Back-office.
    -   **Détails :** Styles pour l'interface du gestionnaire de templates Smarty dans le back-office.
-   `hpp/lib/src/css/lightslider.css`
    -   **Portée :** Front-office.
    -   **Détails :** Le CSS principal de la bibliothèque LightSlider, fournissant le style de base pour le composant carrousel.
-   `hpp/views/css/admin-audience-picker.css`
    -   **Portée :** Back-office.
    -   **Détails :** Styles pour l'interface du sélecteur d'audience dans le back-office.
-   `hpp/views/css/admin-searchtool.css`
    -   **Portée :** Back-office.
    -   **Détails :** Styles supplémentaires pour l'outil de recherche dans le panneau d'administration.
-   `hpp/views/css/admin_hpp.css`
    -   **Portée :** Back-office.
    -   **Détails :** La feuille de style principale pour la configuration et le tableau de bord du back-office du module.
-   `hpp/views/templates/admin/css/css.css`
    -   **Portée :** Back-office.
    -   **Détails :** Une feuille de style spécifiquement située dans le répertoire des templates d'administration, probablement pour des besoins de style très spécifiques au sein de ces templates.

### 4.6 Structure des templates Smarty (`views/templates/`)

#### Templates de hook (`views/templates/hook/`)

Ces templates sont rendus lorsque le module est accroché à des positions spécifiques dans le front-office. Beaucoup sont des overrides spécifiques au thème.

-   `hpp/views/templates/hook/column17.tpl`
    -   **Hook :** `displayLeftColumn`, `displayRightColumn` (PrestaShop 1.7.x+).
    -   **Sortie :** Rend un bloc de produits conçu pour les colonnes gauche ou droite, généralement une liste verticale ou une petite grille.
-   `hpp/views/templates/hook/firezy-column17.tpl`
    -   **Hook :** `displayLeftColumn`, `displayRightColumn` (PrestaShop 1.7.x+ pour le thème Firezy).
    -   **Sortie :** Override spécifique au thème pour les blocs de produits de colonne, adapté au thème Firezy.
-   `hpp/views/templates/hook/firezy-homeTab.tpl`
    -   **Hook :** `displayHomeTab` (pour le thème Firezy).
    -   **Sortie :** Rend le lien de navigation de l'onglet réel (par exemple, « Collection d'été ») pour le thème Firezy.
-   `hpp/views/templates/hook/firezy-homeTabContent.tpl`
    -   **Hook :** `displayHomeTabContent` (pour le thème Firezy).
    -   **Sortie :** Rend le contenu (le bloc de produits lui-même) qui apparaît lorsqu'un onglet spécifique est actif, adapté au thème Firezy.
-   `hpp/views/templates/hook/firezy-internal-tabs.tpl`
    -   **Hook :** `displayHome` (pour le thème Firezy).
    -   **Sortie :** Rend l'interface à onglets interne entière (à la fois la navigation et l'enveloppe de contenu) pour le thème Firezy.
-   `hpp/views/templates/hook/firezy-products17.tpl`
    -   **Hook :** `displayHome` (pour le thème Firezy).
    -   **Sortie :** Rend un bloc de produits général (carrousel ou grille) pour la zone de contenu principale de la page d'accueil, adapté au thème Firezy.
-   `hpp/views/templates/hook/homeTab.tpl`
    -   **Hook :** `displayHomeTab`.
    -   **Sortie :** Rend le lien de navigation générique de l'onglet.
-   `hpp/views/templates/hook/homeTabContent.tpl`
    -   **Hook :** `displayHomeTabContent`.
    -   **Sortie :** Rend le contenu générique pour un bloc de produits à onglets.
-   `hpp/views/templates/hook/hummingbird-column17.tpl`, `hummingbird-homeTab.tpl`, `hummingbird-homeTabContent.tpl`, `hummingbird-internal-tabs.tpl`, `hummingbird-products17.tpl`
    -   **Hook :** Similaire à Firezy, ce sont des overrides spécifiques au thème Hummingbird, fournissant des mises en page adaptées pour les colonnes, la navigation par onglets, le contenu des onglets, les enveloppes d'onglets internes et les blocs de produits généraux.
-   `hpp/views/templates/hook/internal-tabs.tpl`
    -   **Hook :** `displayHome`.
    -   **Sortie :** Rend l'interface à onglets interne générique (navigation et enveloppe de contenu).
-   `hpp/views/templates/hook/products17.tpl`
    -   **Hook :** `displayHome`, `displayTopColumn`.
    -   **Sortie :** Rend un bloc de produits générique (carrousel ou grille) pour la zone de contenu principale de la page d'accueil ou de la colonne supérieure (PrestaShop 1.7.x+).
-   `hpp/views/templates/hook/warehouse-column17.tpl`, `warehouse-homeTab.tpl`, `warehouse-homeTabContent.tpl`, `warehouse-internal-tabs.tpl`, `warehouse-products17.tpl`
    -   **Hook :** Similaire à Firezy et Hummingbird, ce sont des overrides spécifiques au thème Warehouse, fournissant des mises en page adaptées pour les colonnes, la navigation par onglets, le contenu des onglets, les enveloppes d'onglets internes et les blocs de produits généraux.

#### Templates d'administration (`views/templates/admin/`)

Ces templates sont utilisés pour l'interface back-office du module.

-   `hpp/views/templates/admin/audience-picker.tpl`
    -   **Sortie :** Rend le HTML pour l'interface de sélection de groupe de clients et de pays.
-   `hpp/views/templates/admin/country-priority-picker.tpl`
    -   **Sortie :** Rend le HTML pour la sélection et la priorisation des pays.
-   `hpp/views/templates/admin/menu.tpl`
    -   **Sortie :** Rend le menu ou la navigation spécifique du module dans son tableau de bord back-office.
-   `hpp/views/templates/admin/scripts.tpl`
    -   **Sortie :** Inclut des fichiers JavaScript ou des scripts en ligne spécifiquement pour l'interface d'administration.
-   `hpp/views/templates/admin/ul-li.tpl`
    -   **Sortie :** Un template de liste générique, éventuellement utilisé pour afficher des listes d'éléments ou d'options dans les formulaires d'administration.

#### Templates de bibliothèque (`hpp/lib/`)

Ces templates font partie des bibliothèques intégrées.

-   `hpp/lib/searchTool/views/scripts.tpl`
    -   **Sortie :** Inclut des fichiers JavaScript ou des scripts en ligne pour la fonctionnalité de l'outil de recherche.
-   `hpp/lib/smartyTemplatesManager/tpl/example.tpl`
    -   **Sortie :** Un exemple de template pour le Smarty Templates Manager, probablement à des fins de démonstration ou comme base.
-   `hpp/lib/smartyTemplatesManager/views/buttonManager.tpl`
    -   **Sortie :** Rend les boutons ou les contrôles pour la gestion des templates.
-   `hpp/lib/smartyTemplatesManager/views/createTemplateForm.tpl`
    -   **Sortie :** Rend le formulaire pour la création de nouveaux templates personnalisés.
-   `hpp/lib/smartyTemplatesManager/views/editTemplateForm.tpl`
    -   **Sortie :** Rend le formulaire pour la modification de templates personnalisés existants.
-   `hpp/lib/smartyTemplatesManager/views/mainForm.tpl`
    -   **Sortie :** Le formulaire principal pour l'interface du Smarty Templates Manager.
-   `hpp/lib/smartyTemplatesManager/views/selectInput.tpl`
    -   **Sortie :** Rend un champ de saisie générique de type select/liste déroulante.

### 4.7 Schéma de la base de données et carte des hooks

#### Tables de la base de données

Aucun fichier SQL personnalisé (`.sql`) n'a été identifié, et aucune classe `ObjectModel` n'a été listée. Cela suggère fortement que le module stocke ses données de configuration et ses définitions de blocs de produits principalement dans la table `ps_configuration` de PrestaShop.

-   **`ps_configuration`** : Cette table contiendra des entrées avec des clés comme `HPP_ANALYTICS_ENABLED`, `HPP_CACHE_TTL`, `HPP_BLOCKS_DATA` (ou similaire, où `HPP_BLOCKS_DATA` contiendrait un tableau sérialisé ou une chaîne JSON de toutes les configurations de blocs de produits).

#### Tableau des hooks enregistrés

Le module s'enregistre sur divers hooks PrestaShop pour injecter son contenu et ses fonctionnalités.

| Nom du hook | Moment d'exécution | Objectif technique |
| --- | --- | --- |
| `displayHeader` | Dans la section `<head>` de chaque page. | Injecter les actifs CSS et JS (par exemple, LightSlider, `hpp.css`, `script.js`). |
| `actionFrontControllerSetMedia` | Avant qu'un contrôleur frontal ne rende sa sortie. | Ajouter des actifs CSS/JS spécifiques de manière conditionnelle en fonction de la page ou du contrôleur. |
| `displayHome` | Zone de contenu principale de la page d'accueil. | Rendre les blocs de produits généraux (carrousels, grilles) directement sur la page d'accueil. |
| `displayHomeTab` | Dans la zone de navigation des onglets de la page d'accueil. | Rendre les liens de navigation pour les onglets de produits personnalisés. |
| `displayHomeTabContent` | Dans la zone de contenu des onglets de la page d'accueil. | Rendre les blocs de produits réels qui apparaissent lorsqu'un onglet personnalisé est actif. |
| `displayLeftColumn` | Dans la colonne de gauche des pages où elle est active. | Rendre les blocs de produits verticaux dans la barre latérale gauche. |
| `displayRightColumn` | Dans la colonne de droite des pages où elle est active. | Rendre les blocs de produits verticaux dans la barre latérale droite. |
| `displayTopColumn` | Dans la zone de contenu supérieure, généralement sous l'en-tête. | Rendre les blocs de produits dans la section supérieure de la page d'accueil. |
| `displayBackOfficeHeader` | Dans la section `<head>` de chaque page du back-office. | Injecter les actifs CSS et JS pour les pages de configuration du back-office du module. |
| `actionAdminControllerSetMedia` | Avant qu'un contrôleur d'administration ne rende sa sortie. | Ajouter des actifs CSS/JS spécifiques pour les pages d'administration du module. |
| `actionProductUpdate` | Après la mise à jour d'un produit dans le back-office. | Potentiellement vider le cache des blocs contenant ce produit, ou réindexer les données du produit. |
| `actionProductDelete` | Après la suppression d'un produit dans le back-office. | Potentiellement vider le cache des blocs contenant ce produit, ou le supprimer des configurations de blocs. |
| `actionCategoryUpdate` | Après la mise à jour d'une catégorie dans le back-office. | Potentiellement vider le cache des blocs affichant des produits de cette catégorie. |

## 5. Support officiel et mises à jour

Pour les dernières mises à jour, corrections de bugs et support officiel du module « Homepage Products Pro », veuillez vous référer à votre compte client sur MyPresta.eu. Notre équipe de support dédiée est disponible pour vous aider avec tout problème technique ou question que vous pourriez avoir.

-   **Historique des commandes et téléchargements MyPresta.eu :** <https://mypresta.eu/my-account/orders/>
-   **Contact support MyPresta.eu :** <https://mypresta.eu/contact>
