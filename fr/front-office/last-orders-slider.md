---
title: "Slider des dernières commandes - Manuel du marchand et guide de configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop Slider des dernières commandes par MyPresta.eu."
sidebar:
  label: "Slider des dernières commandes - Manuel du marchand et guide de configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Last orders slider sur MyPresta.eu](https://mypresta.eu/modules/front-office-features/last-orders-slider.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/front-office/last-orders-slider/)
>
> ---


# Slider des dernières commandes

## 1. Exigences et compatibilité

- **Versions PrestaShop prises en charge** : PrestaShop 1.7.6+, 8.x, 9.x
- **Compatibilité PHP** : PHP 7.1 - 8.5
- **Exigences d'hébergement** : Les extensions PHP standard (cURL, JSON, OpenSSL) sont généralement suffisantes et sont habituellement activées par défaut sur la plupart des environnements d'hébergement compatibles PrestaShop.

## 2. Parcours de configuration complet (chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

Ceci est l'écran de configuration principal du module « Slider des dernières commandes ». Vous pouvez y accéder en naviguant vers **Modules > Gestionnaire de modules** et en cliquant sur « Configurer » à côté du module « Slider des dernières commandes ».

#### Paramètres généraux

- **Ce que fait ce paramètre :** Cette section contrôle le comportement fondamental et l'apparence de votre slider de commandes.
- **Effet de la modification de ce paramètre :** L'ajustement de ces paramètres aura un impact direct sur l'apparence du slider, son emplacement et les informations qu'il affiche à vos clients.

| Paramètre / Option | Ce que fait ce paramètre | Effet de la modification de ce paramètre | Valeur recommandée | Scénario / exemple pour le marchand |
| --- | --- | --- | --- | --- |
| **Activer le module** | Active ou désactive l'ensemble de la fonctionnalité du slider. | *Lorsqu'activé :* Le slider apparaîtra sur votre front office en fonction des autres paramètres. *Lorsqu'il est désactivé :* Le slider ne sera pas visible pour les clients. | OUI | Vous souhaitez masquer temporairement le slider pour la maintenance ou une campagne spéciale. |
| **Nombre de commandes à afficher** | Détermine le nombre de commandes récentes que le slider fera défiler. | *Lorsqu'il est réglé sur 5 :* Le slider affichera les informations des 5 commandes les plus récentes. *Lorsqu'il est réglé sur 10 :* Il affichera 10. | 5-10 (selon le volume de commandes) | Si vous avez un très grand volume de commandes, en afficher plus pourrait être accablant. Si vous avez moins de commandes, en afficher plus garantit qu'il y a toujours du contenu. |
| **États de commande à afficher** | Sélectionne les statuts de commande (par exemple, « Paiement accepté », « Livré ») qui sont considérés comme des « commandes récentes » pour le slider. | *Lorsque « Paiement accepté » est sélectionné :* Seules les commandes ayant atteint ce statut apparaîtront. *Lorsque « Annulé » est sélectionné :* Les commandes annulées pourraient apparaître (non recommandé pour la preuve sociale). | « Paiement accepté », « Préparation en cours », « Livré » | Vous ne voulez afficher que les commandes qui sont confirmées et en cours de traitement ou qui ont été livrées avec succès, pour renforcer la confiance positive. |
| **Afficher le nom du client** | Contrôle si le prénom et l'initiale du nom du client sont affichés. | *Lorsqu'activé :* « Jean D. de Paris… » *Lorsqu'il est désactivé :* « Quelqu'un de Paris… » | OUI | Afficher un nom partiel ajoute une touche personnelle et rend les commandes plus réelles, améliorant la preuve sociale. |
| **Afficher la ville du client** | Contrôle si la ville du client est affichée. | *Lorsqu'activé :* « …de Paris vient d'acheter… » *Lorsqu'il est désactivé :* « …vient de passer une commande. » | OUI | Afficher la ville ajoute une couche d'authenticité et peut résonner avec les clients locaux. |
| **Afficher le nom du produit** | Contrôle si le nom du produit acheté est affiché. | *Lorsqu'activé :* « …vient d'acheter un T-Shirt. » *Lorsqu'il est désactivé :* « …vient de passer une commande. » | OUI | Afficher le nom du produit rend l'achat plus tangible et peut mettre en évidence les articles populaires. |
| **Afficher l'image du produit** | Contrôle si une petite image du produit acheté est affichée. | *Lorsqu'activé :* Une petite vignette du produit apparaîtra à côté du texte. *Lorsqu'il est désactivé :* Seul le texte sera affiché. | OUI | Les visuels sont engageants. Une image de produit rend le slider plus attrayant et informatif. |
| **Vitesse d'animation (millisecondes)** | Définit la vitesse à laquelle le slider passe d'une commande à l'autre. | *Valeur inférieure (par exemple, 3000) :* Transitions plus rapides, les commandes changent toutes les 3 secondes. *Valeur supérieure (par exemple, 8000) :* Transitions plus lentes, les commandes changent toutes les 8 secondes. | 5000 (5 secondes) | Une vitesse modérée maintient le slider dynamique sans être trop rapide à lire ou trop lent à mettre à jour. |
| **Couleur du texte** | Définit la couleur du texte affiché dans le slider. | *Lorsqu'il est réglé sur #000000 (noir) :* Le texte sera noir. *Lorsqu'il est réglé sur #FF0000 (rouge) :* Le texte sera rouge. | #FFFFFF (blanc) ou une couleur contrastant avec votre arrière-plan | Choisissez une couleur qui se démarque de la couleur d'arrière-plan choisie et qui correspond à l'esthétique de votre marque. |
| **Couleur de fond** | Définit la couleur d'arrière-plan de la barre du slider. | *Lorsqu'il est réglé sur #FFFFFF (blanc) :* L'arrière-plan du slider sera blanc. *Lorsqu'il est réglé sur #000000 (noir) :* L'arrière-plan du slider sera noir. | #000000 (noir) ou une couleur contrastant avec votre thème | Choisissez une couleur qui rend le slider visible et complète le design de votre boutique. |
| **Hook pour afficher le slider** | Sélectionne l'endroit où le slider apparaîtra dans votre thème PrestaShop. | *Lorsque « displayTop » est sélectionné :* Le slider apparaît près du haut de votre boutique. *Lorsque « displayFooter » est sélectionné :* Le slider apparaît en bas. | `displayTop` ou `displayNavFullWidth` | Choisissez un emplacement proéminent où les clients le verront facilement sans obstruer le contenu critique. |

#### 2.1.1 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Par défaut / Recommandé | Objectif et impact |
| --- | --- | --- | --- |
| Configuration du module | Activer le module | OUI | Active/désactive le slider. |
| Configuration du module | Nombre de commandes à afficher | 5-10 | Contrôle le nombre de commandes récentes affichées. |
| Configuration du module | États de commande à afficher | Paiement accepté, Préparation, Livré | Filtre les commandes par leur statut pour l'affichage. |
| Configuration du module | Afficher le nom du client | OUI | Affiche le prénom et l'initiale du nom du client. |
| Configuration du module | Afficher la ville du client | OUI | Affiche la ville du client. |
| Configuration du module | Afficher le nom du produit | OUI | Affiche le nom du produit acheté. |
| Configuration du module | Afficher l'image du produit | OUI | Affiche une petite image du produit acheté. |
| Configuration du module | Vitesse d'animation (millisecondes) | 5000 | Définit la vitesse de transition entre les commandes. |
| Configuration du module | Couleur du texte | #FFFFFF (blanc) | Définit la couleur du texte dans le slider. |
| Configuration du module | Couleur de fond | #000000 (noir) | Définit la couleur de fond du slider. |
| Configuration du module | Hook pour afficher le slider | `displayTop` / `displayNavFullWidth` | Détermine la position du slider dans votre thème. |

## 3. Dépannage pour les marchands et questions fréquemment posées (FAQ)

**Q1 : Le slider n'apparaît pas sur ma boutique. Que dois-je faire ?**
R :

-   **Vérifier le statut du module :** Allez dans **Modules > Gestionnaire de modules** et assurez-vous que « Slider des dernières commandes » est installé et activé.
-   **Vérifier la sélection du hook :** Dans la configuration du module, vérifiez que vous avez sélectionné un « Hook pour afficher le slider » valide (par exemple, `displayTop`, `displayNavFullWidth`). Certains hooks peuvent ne pas être présents ou actifs dans tous les thèmes.
-   **Vider le cache :** Allez dans **Paramètres avancés > Performances** et cliquez sur « Vider le cache » (ou « Vider le cache Smarty » dans les versions antérieures). Parfois, le cache de PrestaShop empêche l'apparition immédiate de nouveau contenu.
-   **Vérifier les états de commande :** Assurez-vous d'avoir sélectionné au moins un « État de commande à afficher » qui a des commandes récentes associées. Si aucune commande ne correspond aux états sélectionnés, le slider sera vide.
-   **Compatibilité du thème :** Bien que le module soit conçu pour une large compatibilité, les thèmes très fortement personnalisés peuvent nécessiter des ajustements mineurs. Si tout le reste échoue, contactez le support MyPresta.eu.

**Q2 : Le slider s'affiche, mais les couleurs ne correspondent pas à mon thème.**
R :

-   **Ajuster les couleurs dans la configuration :** Allez sur la page de configuration du module. Utilisez les paramètres « Couleur du texte » et « Couleur de fond » pour sélectionner des couleurs qui complètent le design de votre boutique. Vous pouvez utiliser un outil de sélection de couleurs (disponible en ligne ou sous forme d'extensions de navigateur) pour trouver les codes hexadécimaux exacts de votre thème.
-   **CSS personnalisé (Avancé) :** Si les options de couleur du module ne suffisent pas, votre webmaster peut ajouter des règles CSS personnalisées à la feuille de style de votre thème pour remplacer les styles par défaut du module. (Voir la section 7.5 pour les détails du développeur).

**Q3 : Le slider est vide ou ne se met pas à jour avec les nouvelles commandes.**
R :

-   **États de commande :** Assurez-vous que le paramètre « États de commande à afficher » inclut les statuts de vos commandes les plus récentes (par exemple, « Paiement accepté », « Livré »). Si vos commandes récentes sont dans un statut non sélectionné, elles n'apparaîtront pas.
-   **Commandes récentes :** Le module affiche les commandes *récentes*. Si votre boutique n'a pas eu de commandes depuis un certain temps, ou si le « Nombre de commandes à afficher » est réglé trop bas, il peut apparaître vide.
-   **Cache :** Encore une fois, vider votre cache PrestaShop (**Paramètres avancés > Performances**) peut aider à garantir que le module récupère les dernières données.

**Q4 : Comment traduire le texte du slider dans d'autres langues ?**
R :

-   **Outil de traduction PrestaShop :** Allez dans **International > Traductions**.
-   Sélectionnez « Traductions des modules installés », choisissez votre thème, puis sélectionnez votre langue.
-   Recherchez le module « Slider des dernières commandes » dans la liste. Vous pourrez traduire toutes les chaînes de caractères codées en dur (comme « vient d'acheter » ou « de ») que le module utilise.
-   **Contenu dynamique :** Les noms de clients, les villes et les noms de produits sont extraits directement des données de votre boutique et apparaîtront dans la langue dans laquelle ils ont été saisis ou configurés dans votre catalogue de produits.

**Q5 : Le slider est trop rapide/lent ou affiche trop/pas assez de commandes.**
R :

-   **Vitesse d'animation :** Ajustez le paramètre « Vitesse d'animation (millisecondes) » dans la configuration du module. Un nombre plus élevé signifie des transitions plus lentes.
-   **Nombre de commandes :** Modifiez le paramètre « Nombre de commandes à afficher » pour contrôler le nombre de commandes uniques qui défilent. Expérimentez avec ces valeurs pour trouver l'équilibre parfait pour le trafic et le volume de commandes de votre boutique.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

Cette section fournit une analyse technique approfondie du module « Slider des dernières commandes », destinée aux développeurs, webmasters et agences techniques.

### 4.1 Aperçu de l'architecture

Le module « Slider des dernières commandes » (`lastord`) est un module PrestaShop standard principalement conçu pour afficher du contenu dynamique dans le front office. Il utilise le système de hooks de PrestaShop pour injecter son contenu dans diverses parties du thème. La logique principale réside dans le fichier principal du module (`index.php`), qui gère la configuration, la récupération des données et le rendu des templates. Il n'introduit pas de contrôleurs personnalisés ni d'ObjectModels complexes, s'appuyant plutôt sur des requêtes directes à la base de données (via `Db::getInstance()`) pour récupérer les données de commande et sur les templates Smarty pour la présentation. Le style est géré via un fichier CSS dédié.

### 4.2 Contrôleurs (`controllers/`)

Ce module n'utilise **pas** de contrôleurs d'administration Front-Office ou Back-Office personnalisés. Toute la configuration est gérée via la méthode `getContent()` dans le fichier principal du module, et le rendu du front-office est effectué directement via les méthodes de hook.

### 4.3 Classes et modèles principaux (`classes/`)

Ce module ne définit **pas** de classes ou d'ObjectModels personnalisés dans le répertoire `classes/`. Toute la récupération des données et la logique métier sont encapsulées dans la classe `Lastord` dans `index.php`.

### 4.4 Actifs JavaScript (`views/js/`)

Ce module n'inclut **pas** de fichiers JavaScript personnalisés. La fonctionnalité d'animation et de slider est probablement gérée soit par des animations CSS, soit par un script très léger et en ligne dans le template, soit par une bibliothèque tierce déjà chargée par PrestaShop.

### 4.5 Feuilles de style CSS (`views/css/`)

-   **`lastord/views/css/lastord.css`**
    -   **Portée :** Style du front-office client.
    -   **Principaux composants et conteneurs d'interface utilisateur qu'il stylise :** Cette feuille de style est responsable de l'apparence visuelle de la barre du slider de commandes elle-même, y compris son positionnement, son arrière-plan, les styles de texte et potentiellement les propriétés d'animation.
    -   **Sélecteurs de classe CSS clés que les développeurs peuvent remplacer dans leur thème :**
        -   `.lastord_wrapper` : Le conteneur principal pour l'ensemble du slider.
        -   `.lastord_item` : Élément de commande individuel dans le slider.
        -   `.lastord_text` : Le contenu textuel (client, produit, ville).
        -   `.lastord_image` : Le conteneur de l'image du produit.
        -   Règles `@keyframes` (si elles sont définies pour l'animation).
        Les développeurs peuvent remplacer ces sélecteurs dans le fichier `custom.css` ou `theme.css` de leur thème pour correspondre à leurs exigences de conception spécifiques.

### 4.6 Structure des templates Smarty (`views/templates/`)

-   **Templates de hook (`views/templates/hook/`)** :

    -   **`lastord/views/templates/hook/lo_orders.tpl`**
        -   **Hook :** C'est le template principal rendu par les méthodes `hook` du module (par exemple, `hookDisplayTop`, `hookDisplayNavFullWidth`, `hookDisplayFooter`, etc.).
        -   **Objectif :** Il contient la structure HTML pour le wrapper du slider et itère sur la variable `$orders` (passée depuis la logique PHP du module) pour afficher chaque commande récente. Il inclut une logique conditionnelle pour afficher/masquer le nom du client, la ville, le nom du produit et l'image en fonction de la configuration du module. Il applique également des styles en ligne pour les couleurs de texte et d'arrière-plan.
    -   **`lastord/views/templates/hook/displayBanner.tpl`**
        -   **Hook :** `displayBanner`
        -   **Objectif :** Ce template agit probablement comme un wrapper ou un point d'inclusion direct pour `lo_orders.tpl` lorsque le module est accroché à `displayBanner`. Il garantit que le contenu du slider est rendu correctement dans ce hook spécifique.
    -   **`lastord/views/templates/hook/displayNavFullWidth.tpl`**
        -   **Hook :** `displayNavFullWidth`
        -   **Objectif :** Similaire à `displayBanner.tpl`, ce template est utilisé pour rendre le contenu de `lo_orders.tpl` lorsque le module est accroché à `displayNavFullWidth`.
    -   **`lastord/views/templates/hook/displayTop.tpl`**
        -   **Hook :** `displayTop`
        -   **Objectif :** Ce template est utilisé pour rendre le contenu de `lo_orders.tpl` lorsque le module est accroché à `displayTop`.
-   **Templates d'administration (`views/templates/admin/`)** :

    -   **`lastord/views/templates/admin/orderstates.tpl`**
        -   **Objectif :** Ce template est utilisé dans la méthode `getContent()` du module pour rendre la liste des cases à cocher des états de commande sur la page de configuration du back-office. Il itère sur les états de commande disponibles et les affiche avec leur statut de sélection actuel.
-   **Templates du front-office (`views/templates/front/`)** : Aucun identifié.

### 4.7 Schéma de la base de données et carte des hooks

-   **Tables de la base de données** :

    -   Ce module ne crée pas de tables SQL personnalisées.
    -   Il stocke ses paramètres de configuration dans la table `ps_configuration` en utilisant des clés telles que `LASTORD_ENABLED`, `LASTORD_ORDERS_COUNT`, `LASTORD_ORDER_STATES`, `LASTORD_DISPLAY_NAME`, `LASTORD_DISPLAY_CITY`, `LASTORD_DISPLAY_PRODUCT`, `LASTORD_DISPLAY_IMAGE`, `LASTORD_ANIMATION_SPEED`, `LASTORD_TEXT_COLOR`, `LASTORD_BACKGROUND_COLOR`, `LASTORD_HOOK`.
-   **Table des hooks enregistrés** :

| Nom du hook | Moment d'exécution | Objectif technique |
| --- | --- | --- |
| `displayHeader` | Dans la section `<head>` du front office. | Utilisé pour enregistrer les actifs (CSS) et potentiellement le JavaScript en ligne. |
| `displayTop` | Généralement tout en haut de la page, sous l'en-tête. | Rend le slider dans une position supérieure proéminente. |
| `displayNavFullWidth` | Souvent une section pleine largeur au-dessus ou en dessous de la navigation principale. | Rend le slider dans une zone de navigation pleine largeur. |
| `displayBanner` | Un hook commun pour les bannières, souvent tout en haut. | Rend le slider comme une bannière. |
| `displayLeftColumn` | Dans la barre latérale gauche. | Rend le slider dans la colonne de gauche. |
| `displayRightColumn` | Dans la barre latérale droite. | Rend le slider dans la colonne de droite. |
| `displayFooter` | Dans la section du pied de page. | Rend le slider en bas de la page. |
| `displayProductButtons` | Sur la page produit, près du bouton d'ajout au panier. | Rend le slider sur la page produit pour la focalisation sur la conversion. |
| `displayFooterProduct` | Dans la section du pied de page de la page produit. | Rend le slider en bas de la page produit. |

## 5. Support officiel et mises à jour

Pour les dernières mises à jour, corrections de bugs et support officiel du module « Slider des dernières commandes », veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu/my-account/orders/). Notre équipe de support est disponible pour vous aider avec tout problème technique ou question que vous pourriez avoir concernant la fonctionnalité et l'intégration du module.
