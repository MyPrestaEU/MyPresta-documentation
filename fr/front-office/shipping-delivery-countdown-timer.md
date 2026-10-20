---
title: "Compte à rebours de livraison - Manuel du Marchand et Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop Compte à rebours de livraison par MyPresta.eu."
sidebar:
  label: "Compte à rebours de livraison - Manuel du Marchand et Guide de Configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Shipping delivery countdown timer sur MyPresta.eu](https://mypresta.eu/modules/front-office-features/shipping-delivery-countdown-timer.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/front-office/shipping-delivery-countdown-timer/)
>
> ---


# Compte à rebours de livraison

## 1. Exigences et compatibilité

- **Versions de PrestaShop prises en charge** : PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilité PHP** : PHP 5.6 - 8.5
- **Exigences d'hébergement** : Les extensions PHP standard (cURL, JSON, OpenSSL) sont généralement suffisantes. Aucune configuration spéciale du serveur n'est généralement nécessaire.

## 2. Parcours de configuration complet (Chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

C'est l'écran de configuration principal où vous contrôlez tous les aspects du compte à rebours de livraison.

#### Paramètres généraux

- **Activé / Désactivé (Interrupteur)**
  - **Ce que fait ce paramètre :** C'est l'interrupteur principal pour activer ou désactiver l'ensemble du module sur votre boutique.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé :* Le compte à rebours apparaîtra sur votre front office selon vos autres paramètres.
    - *Lorsqu'il est désactivé :* Le compte à rebours ne sera visible nulle part sur votre boutique.
  - **Valeur recommandée :** **Activé** (une fois que vous l'avez configuré).
  - **Scénario / exemple de marchand :** Vous configurez le module pour la première fois et souhaitez le configurer entièrement avant de le rendre public. Vous le garderiez « Désactivé » jusqu'à ce qu'il soit prêt, puis passeriez à « Activé ».

#### Affichage et design

- **Où souhaitez-vous afficher le minuteur ? (Cases à cocher)**

  - **Ce que fait ce paramètre :** Il détermine les emplacements spécifiques (hooks) dans votre thème PrestaShop où le compte à rebours sera affiché.
  - **Effet de la modification de ce paramètre :**
    - *Cocher une case (par exemple, `displayProductAdditionalInfo`) :* Le minuteur apparaîtra dans cette zone spécifique de votre thème.
    - *Décocher une case :* Le minuteur sera supprimé de cette zone spécifique.
  - **Valeur recommandée :** Commencez par `displayProductAdditionalInfo` ou `displayFooterProduct` pour la visibilité sur la page produit. Vous pouvez expérimenter avec d'autres comme `displayNav1` ou `displayReassurance` en fonction de votre thème et de l'impact souhaité.
  - **Scénario / exemple de marchand :** Vous souhaitez que le minuteur soit très visible sur les pages produit. Vous cocherez `displayProductAdditionalInfo` et `displayFooterProduct`. Si vous le souhaitez également dans l'en-tête, vous pourriez cocher `displayNav1`.
  - **Options disponibles :**
    - `displayFooterProduct`
    - `displayReassurance`
    - `displayDeliveryTimer` (Hook personnalisé pour une intégration avancée du thème)
    - `displayProductAdditionalInfo`
    - `displayNav1`
- **Quel design du module souhaitez-vous utiliser ? (Boutons radio)**

  - **Ce que fait ce paramètre :** Vous permet de sélectionner un style visuel prédéfini pour votre compte à rebours. Cela inclut les schémas de couleurs et la mise en page générale.
  - **Effet de la modification de ce paramètre :** L'apparence du compte à rebours sur votre front office changera instantanément pour le design sélectionné.
  - **Valeur recommandée :** Choisissez le design qui correspond le mieux à l'image de marque de votre boutique et aux couleurs de votre thème.
  - **Scénario / exemple de marchand :** Votre boutique utilise beaucoup de bleu et de blanc. Vous pourriez sélectionner « Bleu 400x48 » ou « Bleu 200x100 » pour vous assurer que le minuteur s'intègre parfaitement à l'esthétique de votre site.

#### Heures limites d'expédition

- **Heure de rupture d'achat (Sélecteur d'heure)**
  - **Ce que fait ce paramètre :** C'est l'heure limite quotidienne à laquelle une commande doit être passée pour être éligible à l'expédition du jour même.
  - **Effet de la modification de ce paramètre :**
    - *Réglé à 14:00 :* Si un client commande avant 14h, le minuteur compte à rebours jusqu'à 14h. S'il commande après 14h, le minuteur affichera le compte à rebours jusqu'à l'heure limite du jour d'expédition suivant disponible.
  - **Valeur recommandée :** Réglez-le à votre heure limite d'expédition quotidienne réelle (par exemple, 15:00 pour 15h).
  - **Scénario / exemple de marchand :** Votre équipe d'entrepôt traite toutes les commandes reçues avant 16h pour un envoi le jour même. Vous le régleriez à `16:00`.

#### Messages quotidiens et disponibilité

- **Afficher le dimanche / lundi / mardi / mercredi / jeudi / vendredi / samedi (Cases à cocher)**

  - **Ce que fait ce paramètre :** Ces cases à cocher contrôlent si le compte à rebours est actif et affiché des jours spécifiques de la semaine.
  - **Effet de la modification de ce paramètre :**
    - *Cocher un jour (par exemple, « Afficher le dimanche ») :* Le minuteur sera actif et affiché le dimanche.
    - *Décocher un jour :* Le minuteur ne s'affichera pas ce jour spécifique, et le message pour ce jour ne sera pas affiché.
  - **Valeur recommandée :** Cochez tous les jours où vous expédiez réellement. Si vous n'expédiez pas le week-end, décochez samedi et dimanche.
  - **Scénario / exemple de marchand :** Votre entreprise fonctionne du lundi au vendredi. Vous cocherez du lundi au vendredi et décocherez samedi et dimanche.
- **Message (Champ de texte pour chaque jour : dimanche, lundi, mardi, mercredi, jeudi, vendredi, samedi)**

  - **Ce que fait ce paramètre :** Vous permet de personnaliser le message affiché à côté du compte à rebours pour chaque jour de la semaine. Vous pouvez utiliser des placeholders pour le contenu dynamique.
  - **Effet de la modification de ce paramètre :** Le texte affiché au client changera en fonction de votre saisie pour ce jour spécifique.
  - **Valeur recommandée :** Rédigez des messages clairs et concis. Utilisez des placeholders comme `{time}` pour le temps restant et `{date}` pour la date de livraison estimée.
  - **Scénario / exemple de marchand :**
    - *Message du lundi :* « Commandez dans les {time} pour une livraison d'ici mardi ! »
    - *Message du samedi (si pas d'expédition) :* « Les commandes passées le samedi seront expédiées le lundi. »

#### Exclusions/Inclusions de produits et catégories

- **Afficher uniquement pour les produits en stock (Interrupteur)**

  - **Ce que fait ce paramètre :** Contrôle si le compte à rebours est affiché uniquement pour les produits actuellement en stock.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé :* Le minuteur n'apparaîtra que sur les pages produit où le produit a du stock disponible.
    - *Lorsqu'il est désactivé :* Le minuteur apparaîtra quel que soit l'état du stock (bien que cela puisse être déroutant pour les articles en rupture de stock).
  - **Valeur recommandée :** **Activé**. Il n'y a pas beaucoup de sens à afficher un compte à rebours d'expédition pour un article qui ne peut pas être expédié immédiatement.
  - **Scénario / exemple de marchand :** Vous voulez éviter de promettre une expédition rapide pour des articles que vous n'avez pas. L'activation de cette option garantit que le minuteur ne s'affiche que pour les produits disponibles.
- **Exclure le module des produits sélectionnés / Visibilité du module pour les produits sélectionnés (Boutons radio)**

  - **Ce que fait ce paramètre :** C'est un paramètre crucial pour définir si les sélections de produits/catégories/fabricants suivantes sont destinées à *exclure* le module ou à l'*inclure* (le rendant visible uniquement pour les articles sélectionnés).
  - **Effet de la modification de ce paramètre :**
    - *Exclure le module des produits sélectionnés :* Le minuteur s'affichera partout *sauf* pour les articles que vous sélectionnez ci-dessous.
    - *Visibilité du module pour les produits sélectionnés :* Le minuteur s'affichera *uniquement* pour les articles que vous sélectionnez ci-dessous, et nulle part ailleurs.
  - **Valeur recommandée :** Dépend de votre stratégie. Si vous avez quelques produits spécifiques qui ne peuvent pas utiliser le minuteur, choisissez « Exclure ». Si vous ne voulez le minuteur que sur quelques produits sélectionnés, choisissez « Visibilité du module ».
  - **Scénario / exemple de marchand :**
    - *Exclure :* Vous vendez principalement de petits articles avec une expédition rapide, mais aussi quelques gros meubles qui prennent plus de temps. Vous choisiriez « Exclure » puis sélectionneriez les produits de meubles.
    - *Visibilité :* Vous organisez une promotion spéciale sur une catégorie spécifique de produits et ne voulez que le minuteur apparaisse là. Vous choisiriez « Visibilité du module » et sélectionneriez cette catégorie.
- **Exclusions/Inclusions de produits (Recherche et sélection)**

  - **Ce que fait ce paramètre :** Vous permet de rechercher et de sélectionner des produits spécifiques pour en exclure le minuteur ou pour rendre le minuteur visible uniquement pour eux (selon le paramètre « Exclure le module des produits sélectionnés » ci-dessus).
  - **Effet de la modification de ce paramètre :** Ajoute ou supprime des produits spécifiques de la liste d'exclusion/inclusion.
  - **Valeur recommandée :** Utilisez ceci pour un contrôle précis sur les produits individuels.
  - **Scénario / exemple de marchand :** Vous avez un nouveau produit en précommande qui ne sera pas expédié avant des semaines. Vous l'ajouteriez à la liste d'exclusion pour empêcher l'affichage du compte à rebours.
- **Exclusions/Inclusions de catégories (Recherche et sélection)**

  - **Ce que fait ce paramètre :** Similaire aux exclusions de produits, mais s'applique à des catégories entières.
  - **Effet de la modification de ce paramètre :** Ajoute ou supprime des catégories entières de la liste d'exclusion/inclusion.
  - **Valeur recommandée :** Utile pour appliquer des règles à de grands groupes de produits.
  - **Scénario / exemple de marchand :** Tous les produits de votre catégorie « Sur mesure » ont des délais de fabrication longs. Vous ajouteriez cette catégorie à la liste d'exclusion.
- **Exclusions/Inclusions de fabricants (Recherche et sélection)**

  - **Ce que fait ce paramètre :** Similaire aux exclusions de produits/catégories, mais s'applique aux produits de fabricants spécifiques.
  - **Effet de la modification de ce paramètre :** Ajoute ou supprime des fabricants de la liste d'exclusion/inclusion.
  - **Valeur recommandée :** Pratique si certaines marques ont des politiques d'expédition différentes.
  - **Scénario / exemple de marchand :** L'un de vos fournisseurs est connu pour des expéditions plus lentes. Vous ajouteriez son fabricant à la liste d'exclusion.

#### Autres paramètres

- **mypresta\_updates, update\_, updatev\_ (Paramètres internes)**
  - **Ce que fait ce paramètre :** Ce sont des paramètres internes utilisés par les modules MyPresta.eu pour les vérifications de mise à jour et la gestion des versions. Ils ne sont pas destinés à une interaction directe avec le marchand.
  - **Effet de la modification de ce paramètre :** La modification de ces paramètres pourrait interférer avec la capacité du module à vérifier les mises à jour.
  - **Valeur recommandée :** Laissez-les tels quels.

### 2.2 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Valeur par défaut / Recommandée | Objectif et impact |
| --- | --- | --- | --- |
| Configuration du module | Activé | Activé | Interrupteur principal pour la fonctionnalité du module. |
| Configuration du module | Heure de rupture d'achat | Votre heure limite d'expédition quotidienne | Définit l'heure quotidienne à laquelle une commande doit être passée pour l'expédition du jour même. |
| Configuration du module | Où souhaitez-vous afficher le minuteur ? | `displayProductAdditionalInfo`, `displayFooterProduct` | Sélectionne les emplacements du thème pour le minuteur. |
| Configuration du module | Quel design du module souhaitez-vous utiliser ? | Correspond à votre thème | Style visuel du compte à rebours. |
| Configuration du module | Afficher le dimanche/lundi/.../samedi | Cocher tous les jours d'expédition | Contrôle les jours où le minuteur est actif. |
| Configuration du module | Message (pour chaque jour) | « Commandez dans les {time} pour une livraison d'ici {date} ! » | Texte personnalisable affiché avec le minuteur. |
| Configuration du module | Afficher uniquement pour les produits en stock | Activé | Le minuteur n'apparaît que pour les produits avec du stock disponible. |
| Configuration du module | Exclure le module des produits sélectionnés / Visibilité du module pour les produits sélectionnés | Dépend de la stratégie | Définit si les sélections sont pour l'exclusion ou l'inclusion. |
| Configuration du module | Exclusions/Inclusions de produits | Vide | Sélectionne des produits spécifiques à inclure/exclure. |
| Configuration du module | Exclusions/Inclusions de catégories | Vide | Sélectionne des catégories spécifiques à inclure/exclure. |
| Configuration du module | Exclusions/Inclusions de fabricants | Vide | Sélectionne des fabricants spécifiques à inclure/exclure. |

## 3. Dépannage pour les marchands et questions fréquemment posées (FAQ)

**Q1 : Le minuteur n'apparaît pas sur ma boutique, ou il s'affiche au mauvais endroit.**
R1 :

-   **Vérifier l'état du module :** Tout d'abord, assurez-vous que le module est « Activé » sur la page de configuration.
-   **Vérifier la sélection des hooks :** Vérifiez que vous avez coché les bonnes cases « Où souhaitez-vous afficher le minuteur ? ». Si votre thème est fortement personnalisé, certains hooks standard pourraient ne pas être rendus, ou vous pourriez avoir besoin d'utiliser un hook différent.
-   **Vider le cache :** Allez dans **Paramètres avancés > Performances** et cliquez sur « Vider le cache » (ou « Vider le cache Smarty » dans les versions plus anciennes). Parfois, PrestaShop met en cache les anciennes positions des modules.
-   **Compatibilité du thème :** Si votre thème est très personnalisé, il pourrait ne pas implémenter les hooks PrestaShop standard de la manière habituelle. Vous pourriez avoir besoin de consulter le développeur de votre thème ou un webmaster pour insérer manuellement le hook `displayDeliveryTimer` dans les fichiers `.tpl` de votre thème.

**Q2 : Le message du compte à rebours est incorrect, ou l'heure limite semble fausse.**
R2 :

-   **Vérifier l'« Heure de rupture d'achat » :** Vérifiez que l'« Heure de rupture d'achat » est correctement définie à votre heure limite d'expédition quotidienne.
-   **Vérifier les messages quotidiens :** Assurez-vous que le « Message » pour le jour de la semaine en cours est correctement configuré et a du sens.
-   **Fuseau horaire du serveur :** Assurez-vous que le fuseau horaire du serveur de votre boutique PrestaShop est correctement configuré. Si l'heure du serveur est incorrecte, le compte à rebours sera inexact. Vous pouvez vérifier cela dans **Paramètres avancés > Informations de configuration** ou auprès de votre hébergeur.

**Q3 : Le minuteur s'affiche pour les produits en rupture de stock.**
R3 :

-   **Paramètre « Afficher uniquement pour les produits en stock » :** Assurez-vous que l'interrupteur « Afficher uniquement pour les produits en stock » est réglé sur **Activé** dans la configuration du module. S'il est désactivé, le minuteur apparaîtra quel que soit l'état du stock.

**Q4 : Je veux changer les couleurs ou les polices du minuteur au-delà des designs prédéfinis.**
R4 :

-   Le module propose plusieurs designs prédéfinis. Pour une personnalisation plus poussée (par exemple, des polices spécifiques, des codes couleur exacts non disponibles dans les designs), vous aurez besoin d'un webmaster ou d'un développeur. Ils peuvent surcharger les styles CSS du module en ajoutant du CSS personnalisé à la feuille de style de votre thème. Reportez-vous à la section 7.5 pour les détails des fichiers CSS.

**Q5 : Le minuteur ne se traduit pas dans d'autres langues.**
R5 :

-   Allez dans **International > Traductions** dans votre Back Office PrestaShop.
-   Sélectionnez « Traductions des modules installés », choisissez votre thème, puis sélectionnez « Compte à rebours de livraison » dans la liste déroulante des modules.
-   Vous pourrez alors traduire tous les messages quotidiens et autres chaînes du module dans les langues souhaitées.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

### 4.1 Vue d'ensemble de l'architecture

Le module `Compte à rebours de livraison` (`deliverycountdown`) est un module PrestaShop standard suivant un modèle de type MVC dans le cadre du module. Il étend principalement `Module` et utilise le système de hooks de PrestaShop pour injecter son contenu et ses fonctionnalités dans le front office. La configuration est gérée via la méthode `getContent()`, stockant les paramètres dans `ps_configuration`. L'affichage du front office repose sur les templates Smarty et un fichier JavaScript dédié pour la logique du compte à rebours.

### 4.2 Contrôleurs (`controllers/`)

Ce module n'utilise pas de contrôleurs front-office ou back-office personnalisés. Toute la configuration est gérée dans la méthode `getContent()` du fichier de module principal. Le rendu du front-office est réalisé directement via des hooks et les templates associés.

### 4.3 Classes et modèles principaux (`classes/`)

Ce module ne définit aucune classe personnalisée ni `ObjectModel` dans le répertoire `classes/`. Toutes les données sont stockées directement dans `ps_configuration` à l'aide de clés de configuration.

### 4.4 Actifs JavaScript (`views/js/`)

-   **`deliverycountdown/views/js/deliverycountdown.js`**
    -   **Portée :** Front-office.
    -   **Responsabilité :** C'est le fichier JavaScript principal responsable de la logique du compte à rebours.
    -   **Détails :**
        -   Il initialise probablement un compte à rebours sur des éléments identifiés par des classes CSS ou des ID spécifiques.
        -   Il calcule le temps restant jusqu'à l'« Heure de rupture d'achat » pour le jour en cours ou le prochain jour d'expédition disponible.
        -   Il met à jour dynamiquement l'heure affichée (heures, minutes, secondes) dans le template du front-office.
        -   Il gère la transition des messages lorsque l'heure limite est atteinte (par exemple, passer de « Commandez dans X temps » à « Les commandes passées maintenant seront expédiées demain »).
        -   Il peut utiliser `setInterval` ou `setTimeout` pour les mises à jour en temps réel.
        -   Il lit probablement les valeurs de configuration (comme l'heure limite, les messages quotidiens et les jours activés) passées depuis le template Smarty ou le JavaScript en ligne.

### 4.5 Feuilles de style CSS (`views/css/`)

Le module inclut un fichier CSS de base et plusieurs fichiers CSS spécifiques au thème pour différents designs visuels.

-   **`deliverycountdown/views/css/deliverycountdown.css`**

    -   **Portée :** Front-office.
    -   **Responsabilité :** Contient le style structurel fondamental et par défaut du compte à rebours. Cela inclut la mise en page de base, les tailles de police et les éléments communs partagés par tous les designs.
    -   **Sélecteurs clés :** Les développeurs peuvent inspecter la sortie HTML du minuteur pour identifier des classes comme `.deliverycountdown-container`, `.deliverycountdown-message`, `.deliverycountdown-timer`, etc., afin de surcharger les styles dans le fichier `custom.css` ou `theme.css` de leur thème.
-   **`deliverycountdown/views/css/deliverycountdown-{color}-{size}.css`** (par exemple, `deliverycountdown-black-200x100.css`, `deliverycountdown-blue-400x48.css`)

    -   **Portée :** Front-office.
    -   **Responsabilité :** Ces fichiers fournissent les schémas de couleurs spécifiques, les images d'arrière-plan (le cas échéant) et les ajustements de taille pour les différentes options de design sélectionnées dans le back office. Ils surchargent ou étendent généralement les styles définis dans `deliverycountdown.css`.
    -   **Sélecteurs clés :** Ces fichiers cibleront les mêmes sélecteurs de base mais appliqueront des `background-color`, `color`, `width`, `height`, `border`, etc., spécifiques pour obtenir le style visuel choisi.

### 4.6 Structure des templates Smarty (`views/templates/`)

-   **Templates de hook (`views/templates/hook/`)** :

    -   **`deliverycountdown/views/hook/displayFooterProduct.tpl`**
        -   **Hook :** `displayFooterProduct` (et potentiellement d'autres comme `displayProductAdditionalInfo`, `displayReassurance`, `displayNav1`, `displayDeliveryTimer` si configuré).
        -   **Objectif :** C'est le template principal responsable du rendu de la structure HTML du compte à rebours et de son message associé sur le front office.
        -   **Contenu :**
            -   Il contiendra les principaux éléments `div` pour le conteneur du minuteur.
            -   Il affichera le message dynamique (par exemple, « Commandez dans les... ») et les chiffres du compte à rebours.
            -   Il transmet probablement les variables de configuration nécessaires (comme l'heure limite, les messages quotidiens, les jours activés, l'état du stock du produit actuel, les règles d'exclusion/inclusion) au script `deliverycountdown.js`, soit via des attributs de données, soit via des balises `<script>` en ligne.
            -   Il inclut le fichier de design CSS sélectionné et le script `deliverycountdown.js`.
-   **Templates d'administration (`views/templates/admin/`)** :

    -   **`deliverycountdown/views/admin/datepicker.tpl`**
        -   **Objectif :** Probablement un template réutilisable pour le rendu d'un champ de saisie de sélecteur de date dans la configuration du back-office du module. (Bien qu'il ne soit pas explicitement utilisé pour les dates dans la configuration actuelle, il pourrait s'agir d'un composant de bibliothèque).
    -   **`deliverycountdown/views/admin/selectedExcludedProducts.tpl`**
        -   **Objectif :** Rend la liste des produits qui ont été sélectionnés pour l'exclusion ou l'inclusion dans la configuration du module. Cela fait partie de l'interface de sélection de produits/catégories/fabricants.
    -   **`deliverycountdown/views/admin/selectedProducts.tpl`**
        -   **Objectif :** Similaire à `selectedExcludedProducts.tpl`, mais potentiellement pour un contexte de sélection différent (par exemple, s'il y avait des listes d'inclusion et d'exclusion séparées).
    -   **`deliverycountdown/views/admin/timepicker.tpl`**
        -   **Objectif :** Rend le champ de saisie du sélecteur d'heure utilisé pour définir l'« Heure de rupture d'achat » dans la configuration du back-office.
-   **Templates de bibliothèque (`deliverycountdown/lib/searchTool/views/scripts.tpl`)** :

    -   **`deliverycountdown/lib/searchTool/views/scripts.tpl`**
        -   **Objectif :** Contient probablement la logique JavaScript ou Smarty liée à l'outil de recherche et de sélection de produits/catégories/fabricants utilisé dans la configuration du module. Ce script facilite la recherche basée sur AJAX et l'affichage des éléments sélectionnés.

### 4.7 Schéma de base de données et carte des hooks

-   **Tables de base de données** :

    -   Ce module ne crée pas de tables SQL personnalisées. Tous les paramètres de configuration sont stockés dans la table standard `ps_configuration` de PrestaShop.
    -   **Enregistrements de configuration clés (exemples) :**
        -   `DC_LAYOUT` : Stocke la mise en page de design sélectionnée (par exemple, 'black-200x100').
        -   `DC_SUNDAY_MSG`, `DC_MONDAY_MSG`, etc. : Stocke le message personnalisé pour chaque jour.
        -   `DC_TIME` : Stocke l'« Heure de rupture d'achat » (par exemple, '16:00').
        -   `DC_EXCL` : Booléen pour la règle d'exclusion (0 ou 1).
        -   `DC_INSTOCK` : Booléen pour « Afficher uniquement pour les produits en stock ».
        -   `dc_exclusions_products`, `dc_exclusions_cat`, `DC_EXCL_MANUF` : Listes d'ID JSON ou séparées par des virgules pour les entités exclues/incluses.
        -   `DC_SUNDAY`, `DC_MONDAY`, etc. : Booléens pour activer/désactiver le minuteur des jours spécifiques.
        -   `DC_HOOK_displayFooterProduct`, `DC_HOOK_displayReassurance`, etc. : Booléens indiquant quels hooks sont activés pour l'affichage.
-   **Table des hooks enregistrés** :

| Nom du hook | Portée | Moment d'exécution | Objectif technique |
| --- | --- | --- | --- |
| `displayHeader` | Front-office | Dans la section `<head>` de chaque page. | Utilisé pour charger les actifs CSS et JS du module globalement, ou pour l'affichage général du minuteur sur le site. |
| `displayNav1` | Front-office | Généralement dans la barre de navigation supérieure. | Affiche le minuteur dans la zone de navigation principale. |
| `displayNav2` | Front-office | Souvent dans une barre de navigation secondaire ou des liens utilitaires. | Affiche le minuteur dans une zone de navigation secondaire. |
| `displayTop` | Front-office | Dans la section d'en-tête principale, sous `displayNav`. | Affiche le minuteur dans l'en-tête principal. |
| `displayProductAdditionalInfo` | Front-office | Sur la page produit, souvent près du bouton « Ajouter au panier ». | Placement stratégique pour l'urgence spécifique au produit. |
| `displayFooterProduct` | Front-office | Sur la page produit, généralement sous la description ou les détails du produit. | Autre placement spécifique au produit pour l'urgence. |
| `displayReassurance` | Front-office | Dans un bloc de réassurance (si le thème le prend en charge), souvent sous les informations du produit. | Intègre le minuteur avec d'autres éléments de renforcement de la confiance. |
| `displayDeliveryTimer` | Front-office | Hook personnalisé. | Permet aux développeurs de thèmes de placer le minuteur précisément n'importe où dans le thème. |
| `actionAdminControllerSetMedia` | Back-office | Lorsqu'un contrôleur d'administration charge ses actifs multimédias. | Utilisé pour charger les CSS/JS spécifiques au module pour la page de configuration du back-office (par exemple, pour l'outil de recherche, le sélecteur d'heure). |

## 5. Support officiel et mises à jour

Pour les dernières mises à jour, corrections de bugs et support officiel du module « Compte à rebours de livraison », veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu/). Notre équipe de support est disponible pour vous aider avec tout problème ou question que vous pourriez avoir concernant la fonctionnalité et l'intégration du module.
