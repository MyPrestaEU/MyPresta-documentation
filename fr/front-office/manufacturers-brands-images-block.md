---
title: "Bloc d'images des fabricants (marques) - Manuel du marchand et guide de configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop Bloc d'images des fabricants (marques) par MyPresta.eu."
sidebar:
  label: "Bloc d'images des fabricants (marques) - Manuel du marchand et guide de configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Manufacturers (brands) images block sur MyPresta.eu](https://mypresta.eu/modules/front-office-features/manufacturers-brands-images-block.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/front-office/manufacturers-brands-images-block/)
>
> ---


# Bloc d'images des fabricants (marques)

## 1. Exigences et compatibilité

- **Versions PrestaShop prises en charge** : PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilité PHP** : PHP 7.1 - 8.5
- **Exigences d'hébergement** : Les extensions PHP standard (cURL, JSON, OpenSSL) sont généralement suffisantes. Aucune configuration de serveur spéciale n'est généralement nécessaire au-delà d'un environnement d'hébergement PrestaShop standard.

## 2. Guide de configuration complet (chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

Après l'installation, cliquer sur « Configurer » vous mènera à la page principale des paramètres du module « Bloc d'images des fabricants (marques) ». Ici, vous pouvez personnaliser l'apparence et le comportement du bloc de marques sur votre boutique.

#### **Position du bloc des fabricants**

- **Ce que fait ce paramètre :** Ce paramètre crucial détermine où le bloc d'images de marque apparaîtra sur votre site web. Vous pouvez choisir parmi différentes positions prédéfinies (hooks) dans votre thème PrestaShop.
- **Effet de la modification de ce paramètre :**
  - *Lorsqu'il est défini sur `displayRightColumn` (ou `displayLeftColumn`) :* Le bloc de marques apparaîtra dans la barre latérale droite (ou gauche) de votre boutique, généralement à côté d'autres blocs comme les catégories ou les meilleures ventes. C'est excellent pour une visibilité constante.
  - *Lorsqu'il est défini sur `displayFooter` :* Le bloc apparaîtra tout en bas de votre site web, souvent utilisé pour la navigation supplémentaire.
  - *Lorsqu'il est défini sur `displayTop` (ou `displayTopColumn`) :* Le bloc sera visible près du haut de votre page, souvent dans la zone de l'en-tête, rendant les marques immédiatement perceptibles.
  - *Lorsqu'il est défini sur `displayHome` :* Le bloc n'apparaîtra que sur la page d'accueil de votre boutique, en faisant une caractéristique centrale pour la découverte des marques.
- **Valeur recommandée :** `displayHome` pour une fonctionnalité de page d'accueil proéminente, ou `displayRightColumn` (ou `displayLeftColumn`) pour une visibilité constante sur les pages de produits et de catégories.
- **Scénario / exemple de marchand :** Si vous souhaitez que les clients puissent facilement parcourir les marques tout en achetant des produits, choisissez `displayRightColumn`. Si vous souhaitez faire une forte déclaration de marque sur votre page d'accueil, choisissez `displayHome`.

#### **Activer le carrousel**

- **Ce que fait ce paramètre :** Ce paramètre transforme la grille statique de logos de marque en un carrousel animé et défilant.
- **Effet de la modification de ce paramètre :**
  - *Lorsqu'il est activé (OUI) :* Les logos de marque défileront horizontalement, vous permettant d'afficher de nombreuses marques dans un espace compact. C'est visuellement dynamique et économise de l'espace d'écran.
  - *Lorsqu'il est désactivé (NON) :* Les logos de marque seront affichés sous forme de grille statique, montrant tous les logos disponibles en une seule fois (ou autant que les dimensions du bloc le permettent). Cela offre un aperçu immédiat sans interaction.
- **Valeur recommandée :** `OUI` si vous avez de nombreuses marques ou si vous souhaitez un look plus moderne et dynamique. `NON` si vous n'avez que quelques marques et préférez un affichage statique.
- **Scénario / exemple de marchand :** Si vous proposez plus de 50 marques, l'activation du carrousel est essentielle pour éviter un bloc très long et encombré. Si vous n'avez que 5 à 10 marques, un affichage statique pourrait être suffisant.

#### **Activer le filtre de catégories**

- **Ce que fait ce paramètre :** Cela permet au module d'afficher uniquement les fabricants associés aux produits de la *catégorie actuellement consultée*.
- **Effet de la modification de ce paramètre :**
  - *Lorsqu'il est activé (OUI) :* Sur une page de catégorie (par exemple, « T-shirts »), le bloc de marques n'affichera que les logos des fabricants qui produisent des T-shirts. Cela rend le bloc très pertinent par rapport au contexte de navigation actuel du client.
  - *Lorsqu'il est désactivé (NON) :* Le bloc de marques affichera toujours *tous* les fabricants actifs de votre boutique, quelle que soit la page ou la catégorie actuelle.
- **Valeur recommandée :** `OUI` pour une meilleure expérience utilisateur et pertinence, en particulier dans les boutiques avec des catégories de produits diverses.
- **Scénario / exemple de marchand :** Un client naviguant dans « Smartphones » ne verra que des marques comme Apple, Samsung et Xiaomi si cette option est activée, plutôt que de voir également des marques de vêtements. Cela l'aide à affiner sa recherche.

#### **Activer le défilement automatique pour le carrousel**

- **Ce que fait ce paramètre :** Si le carrousel est activé, ce paramètre contrôle si les logos de marque défilent automatiquement sans interaction du client.
- **Effet de la modification de ce paramètre :**
  - *Lorsqu'il est activé (OUI) :* Le carrousel fera défiler automatiquement les logos de marque à une vitesse définie, créant un effet visuel dynamique.
  - *Lorsqu'il est désactivé (NON) :* Le carrousel ne défilera que lorsque le client cliquera manuellement sur les flèches de navigation ou fera glisser le carrousel.
- **Valeur recommandée :** `OUI` pour un affichage plus engageant et dynamique, mais assurez-vous que la vitesse n'est pas trop rapide.
- **Scénario / exemple de marchand :** Vous voulez vous assurer que toutes vos marques bénéficient d'une certaine visibilité même si les clients n'interagissent pas avec le carrousel. L'activation du défilement automatique y parvient.

#### **Vitesse du défilement automatique**

- **Ce que fait ce paramètre :** Ce paramètre définit la vitesse à laquelle le carrousel défile automatiquement d'un ensemble de marques à l'autre, mesurée en millisecondes. (Applicable uniquement si « Activer le défilement automatique pour le carrousel » est OUI).
- **Effet de la modification de ce paramètre :**
  - *Valeur plus élevée (par exemple, 5000ms = 5 secondes) :* Vitesse de défilement plus lente, donnant aux clients plus de temps pour visualiser chaque ensemble de logos.
  - *Valeur plus faible (par exemple, 2000ms = 2 secondes) :* Vitesse de défilement plus rapide, rendant le carrousel plus dynamique mais potentiellement plus difficile à lire.
- **Valeur recommandée :** 3000-5000 millisecondes (3-5 secondes) pour une expérience de visionnage confortable.
- **Scénario / exemple de marchand :** Si vous avez de nombreuses marques et que vous souhaitez que les clients les voient toutes sans se sentir pressés, définissez une vitesse plus lente comme 4000ms.

#### **Mettre en pause le carrousel au survol de la souris**

- **Ce que fait ce paramètre :** Si le défilement automatique est activé, ce paramètre contrôle si le carrousel arrête temporairement de défiler lorsqu'un client déplace son curseur de souris sur le bloc de marques.
- **Effet de la modification de ce paramètre :**
  - *Lorsqu'il est activé (OUI) :* Le carrousel se mettra en pause, permettant au client d'examiner confortablement un logo de marque ou de cliquer dessus sans que le carrousel ne bouge. Cela améliore l'expérience utilisateur.
  - *Lorsqu'il est désactivé (NON) :* Le carrousel continuera à défiler automatiquement même si la souris est dessus, ce qui peut être frustrant pour les clients qui essaient d'interagir.
- **Valeur recommandée :** `OUI` pour une meilleure expérience utilisateur.
- **Scénario / exemple de marchand :** Un client voit une marque qu'il aime et déplace sa souris pour cliquer dessus. Si le carrousel se met en pause, il peut facilement cliquer. Sinon, la marque pourrait défiler avant qu'il ne puisse réagir.

#### **Taille de l'image de marque**

- **Ce que fait ce paramètre :** Ce paramètre vous permet de définir la largeur maximale des images de marque affichées dans le bloc. La hauteur sera mise à l'échelle proportionnellement.
- **Effet de la modification de ce paramètre :**
  - *Valeur plus grande (par exemple, 150px) :* Les logos de marque apparaîtront plus grands, les rendant plus proéminents et plus faciles à voir. Cela pourrait prendre plus d'espace dans le bloc.
  - *Valeur plus petite (par exemple, 80px) :* Les logos de marque apparaîtront plus petits, permettant à plus de logos de s'adapter dans un espace donné mais les rendant potentiellement moins perceptibles.
- **Valeur recommandée :** 100-120 pixels pour un bon équilibre entre visibilité et efficacité de l'espace. Ajustez en fonction de la mise en page de votre thème.
- **Scénario / exemple de marchand :** Si votre barre latérale est étroite, vous devrez peut-être définir une taille d'image plus petite (par exemple, 80px) pour éviter que les logos ne débordent. Sur un large bloc de page d'accueil, vous pourriez utiliser 150px pour un plus grand impact.

#### Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Par défaut / Recommandé | Objectif et impact |
| --- | --- | --- | --- |
| Configuration du module | Position du bloc des fabricants | `displayHome` ou `displayRightColumn` | Détermine où le bloc de marques apparaît (par exemple, page d'accueil, barre latérale, pied de page). |
| Configuration du module | Activer le carrousel | `OUI` | Transforme la grille statique en un carrousel défilant pour un affichage dynamique. |
| Configuration du module | Activer le filtre de catégories | `OUI` | Affiche uniquement les marques pertinentes pour la catégorie actuellement consultée. |
| Configuration du module | Activer le défilement automatique pour le carrousel | `OUI` | Fait défiler automatiquement le carrousel à travers les marques. |
| Configuration du module | Vitesse du défilement automatique | 3000-5000ms | Contrôle la vitesse de défilement du carrousel (en millisecondes). |
| Configuration du module | Mettre en pause le carrousel au survol de la souris | `OUI` | Arrête le défilement automatique lorsqu'un client survole le bloc. |
| Configuration du module | Taille de l'image de marque | 100-120px | Définit la largeur maximale des logos de marque dans le bloc. |

## 3. Dépannage pour les marchands et questions fréquemment posées (FAQ)

**Q1 : Mon bloc de marques n'apparaît pas après l'installation, ou il est au mauvais endroit.**

- **R :** Tout d'abord, vérifiez la page de configuration du module dans votre Back Office. Assurez-vous que le paramètre « Position du bloc des fabricants » est correctement choisi. S'il est défini sur `displayHome`, il n'apparaîtra que sur la page d'accueil. S'il est défini sur une colonne, assurez-vous que votre thème affiche réellement cette colonne sur les pages que vous consultez.
- **R :** Videz votre cache PrestaShop. Allez dans **Paramètres avancés > Performances**, puis cliquez sur « Vider le cache » en haut à droite. Parfois, les modifications de thème ou les nouvelles installations de modules nécessitent un rafraîchissement du cache.
- **R :** Vérifiez les « Positions » de votre thème (Design > Positions dans PS 1.7/8). Assurez-vous que le module est accroché à la position souhaitée. S'il n'est pas listé, essayez de réenregistrer la configuration du module.

**Q2 : Mes images de marque sont déformées ou n'ont pas la bonne taille.**

- **R :** Allez dans la configuration du module et ajustez le paramètre « Taille de l'image de marque ». Cela contrôle la largeur maximale.
- **R :** Assurez-vous que les images de fabricant originales téléchargées sur PrestaShop (Catalogue > Fabricants) sont de bonne qualité et ont idéalement un rapport d'aspect cohérent. Bien que le module les mette à l'échelle, des images sources fortement déformées auront toujours un mauvais aspect.
- **R :** Après avoir modifié les tailles d'image, il est souvent judicieux de régénérer les miniatures. Allez dans **Design > Paramètres des images** (ou **Préférences > Images** dans les anciennes versions de PS) et cliquez sur « Régénérer les miniatures ». Sélectionnez « fabricants » comme type d'image.

**Q3 : Le carrousel ne défile pas, ou le défilement automatique ne fonctionne pas.**

- **R :** Vérifiez si « Activer le carrousel » est défini sur `OUI`. Sinon, ce sera un bloc statique.
- **R :** Si le carrousel est activé, vérifiez si « Activer le défilement automatique pour le carrousel » est également défini sur `OUI`. Si c'est `NON`, le carrousel ne bougera que manuellement.
- **R :** Si les deux sont activés, vérifiez la console de développement de votre navigateur (F12) pour toute erreur JavaScript. Des conflits avec d'autres modules ou scripts de thème peuvent parfois empêcher les carrousels de fonctionner. Essayez de désactiver temporairement d'autres modules pour isoler le problème.

**Q4 : Le « Filtre de catégories » ne fonctionne pas ; je vois toujours toutes les marques sur les pages de catégories.**

- **R :** Assurez-vous que ce paramètre est défini sur `OUI` dans la configuration du module.
- **R :** Vérifiez que vos produits sont correctement associés à la fois à une catégorie et à un fabricant dans votre catalogue PrestaShop. Si un produit n'est pas lié à un fabricant, ou si le fabricant n'est lié à aucun produit dans cette catégorie, il n'apparaîtra pas lorsqu'il est filtré.
- **R :** Videz votre cache PrestaShop après avoir effectué des modifications aux associations produit/fabricant.

**Q5 : Comment traduire le titre ou le texte du module ?**

- **R :** Allez dans **International > Traductions** dans votre Back Office PrestaShop.
- Sélectionnez « Traductions des modules installés », choisissez votre thème et sélectionnez la langue que vous souhaitez traduire.
- Trouvez le module « Bloc d'images des fabricants (marques) » dans la liste et vous pourrez modifier toutes les chaînes traduisibles qu'il fournit (par exemple, le titre du bloc).

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

### 4.1 Vue d'ensemble de l'architecture

Le module « Bloc d'images des fabricants (marques) » (`mib`) est un module PrestaShop standard suivant un modèle de type MVC. Il exploite principalement le système de hooks de PrestaShop pour injecter son contenu dans diverses positions du front-office. La logique principale réside dans le fichier `mib.php`, qui gère l'installation, la désinstallation, la configuration et le rendu du contenu pour les hooks. Il utilise une bibliothèque JavaScript tierce (`lightslider.js`) pour la fonctionnalité de carrousel et des CSS personnalisés pour le style. Les paramètres de configuration sont stockés dans `ps_configuration`.

### 4.2 Contrôleurs (`controllers/`)

Ce module n'utilise pas de contrôleurs d'administration Front-Office ou Back-Office personnalisés. Toute la configuration est gérée via la méthode `getContent()` dans le fichier principal du module, et le rendu du front-office est effectué directement via les méthodes de hook.

### 4.3 Classes et modèles principaux (`classes/`)

Ce module ne définit aucune classe personnalisée ou entité `ObjectModel`. Il interagit directement avec les objets `Manufacturer` et `Category` et `Configuration` de PrestaShop pour les paramètres.

### 4.4 Actifs JavaScript (`views/js/`)

- **`mib/lib/js/lightslider.js`**
  - **Portée :** Front-office.
  - **Description :** Il s'agit d'un plugin jQuery tiers responsable de la création du carrousel de contenu réactif. Il gère l'animation de défilement, les contrôles de navigation et le comportement réactif pour les logos de marque lorsque l'option carrousel est activée.
  - **Fonctionnalité clé :** Initialise `lightSlider` sur un élément HTML spécifié, gère les transitions de diapositives, les gestes tactiles/de balayage et les ajustements réactifs.
- **`mib/views/js/mib.js`**
  - **Portée :** Front-office.
  - **Description :** Il s'agit du fichier JavaScript personnalisé du module. Il contient la logique d'initialisation du plugin `lightslider.js` basée sur les paramètres de configuration du module.
  - **Fonctionnalité clé :**
    - Vérifie si le carrousel est activé (configuration `MIB_CAROUSEL`).
    - Initialise le `lightSlider` sur l'élément `#lightSlider` dans le template du module.
    - Transmet les options de configuration à `lightSlider` telles que `auto`, `pause`, `pauseOnHover`, `item`, `slideMove`, `speed`, `loop`, `controls`, `responsive` basées sur les paramètres `MIB_ASCROLL`, `MIB_PAUSE`, `MIB_SPEED` et `MIB_IMG`.
    - S'assure que le curseur n'est initialisé que si l'élément existe.

### 4.5 Feuilles de style CSS (`views/css/`)

- **`mib/lib/css/lightslider.css`**
  - **Portée :** Style client du front-office.
  - **Description :** Il s'agit de la feuille de style principale du plugin `lightslider.js`. Elle fournit le style nécessaire pour la structure du carrousel, les flèches de navigation et les points de pagination.
  - **Sélecteurs CSS clés :** `.lightSlider`, `.lSAction`, `.lSPager`, `.lslide`, etc. Les développeurs peuvent les surcharger pour personnaliser l'apparence du carrousel.
- **`mib/mib.css`**
  - **Portée :** Style client du front-office.
  - **Description :** Il s'agit de la feuille de style personnalisée du module. Elle fournit un style spécifique pour le conteneur du bloc de marques, les images de marques individuelles et tout effet de survol.
  - **Sélecteurs CSS clés :**
    - `#manufacturers_block_top`, `#manufacturers_block_left`, `#manufacturers_block_right`, `#manufacturers_block_home`, `#manufacturers_block_footer` : ID des conteneurs principaux pour différentes positions de hook.
    - `.mib_manufacturer_item` : Styles pour les liens/conteneurs de fabricants individuels.
    - `.mib_manufacturer_item img` : Styles pour les images de marque, y compris les ajustements `max-width` et `height`.
    - `.mib_manufacturer_item:hover img` : Définit l'animation de survol (par exemple, `transform: scale(1.1)` pour un effet de zoom).

### 4.6 Structure des templates Smarty (`views/templates/`)

- **Templates de hook (`views/templates/hook/`)** :
  - **`mib/views/templates/hook/mib.tpl`**
    - **Accroché à :** `displayRightColumn`, `displayFooter`, `displayTop`, `displayLeftColumn`, `displayHome`, `displayTopColumn`.
    - **Objectif :** C'est le template principal du front-office responsable du rendu du bloc de marques. Il génère dynamiquement la structure HTML pour une grille statique de logos de fabricants ou le carrousel `lightSlider`, en fonction de la configuration du module.
    - **Éléments clés :**
      - Rendu conditionnel pour le carrousel (`{if $mib_carousel}`).
      - Boucle sur le tableau `$manufacturers` pour afficher l'image et le lien de chaque marque.
      - Inclut `mib.js` et `lightslider.js` si le carrousel est activé.
      - Inclut `mib.css` et `lightslider.css`.
      - Utilise `{$link->getManufacturerLink($manufacturer.id_manufacturer, $manufacturer.link_rewrite)}` pour les URL des fabricants.
      - Utilise `{$manufacturer.image}` pour les chemins des images de marque.
- **Templates d'administration (`views/templates/admin/`)** :
  - **`mib/views/templates/admin/admin.tpl`**
    - **Objectif :** Ce template rend le formulaire de configuration du module dans le Back Office de PrestaShop. Il affiche tous les paramètres (position, options du carrousel, taille de l'image, etc.) sous forme de champs de saisie, de listes déroulantes et de commutateurs.
    - **Éléments clés :**
      - Structure de formulaire d'aide PrestaShop standard (`{include file="{$smarty.const._PS_ROOT_DIR_}/src/PrestaShopBundle/Resources/views/Admin/Configure/AdvancedParameters/Blocks/form_block_content.html.twig"}`).
      - Champs de saisie pour `MIB_WHERE`, `MIB_CAROUSEL`, `MIB_ASCROLL`, `MIB_PAUSE`, `MIB_SPEED`, `MIB_FROM_CAT`, `MIB_IMG`.
      - Utilise `{$mib_form_action}` pour la soumission du formulaire.

### 4.7 Schéma de la base de données et carte des hooks

- **Tables de la base de données** :
  - Ce module ne crée aucune table de base de données personnalisée.
  - Les paramètres de configuration sont stockés dans la table `ps_configuration` à l'aide de clés telles que `MIB_CAROUSEL`, `MIB_ASCROLL`, `MIB_PAUSE`, `MIB_SPEED`, `MIB_FROM_CAT`, `MIB_IMG`, `MIB_WHERE`.
- **Table des hooks enregistrés** :

| Nom du hook | Moment et emplacement d'exécution | Objectif technique |
| --- | --- | --- |
| `displayRightColumn` | Rendu dans la barre latérale droite du front-office. | Affiche le bloc de marques dans la colonne de droite. |
| `displayFooter` | Rendu dans la section du pied de page du front-office. | Affiche le bloc de marques dans le pied de page de la boutique. |
| `displayTop` | Rendu dans la section supérieure du front-office (souvent l'en-tête). | Affiche le bloc de marques dans la zone de l'en-tête. |
| `actionAdminControllerSetMedia` | Exécuté lorsqu'un contrôleur d'administration définit ses actifs multimédias. | Utilisé pour inclure les fichiers CSS et JS du module dans le Back Office pour la configuration. |
| `displayLeftColumn` | Rendu dans la barre latérale gauche du front-office. | Affiche le bloc de marques dans la colonne de gauche. |
| `displayHome` | Rendu sur la page d'accueil du front-office. | Affiche le bloc de marques de manière proéminente sur la page d'accueil. |
| `displayHeader` | Exécuté dans la section `<head>` de chaque page du front-office. | Utilisé pour inclure les fichiers CSS et JS nécessaires à l'affichage du front-office. |
| `displayTopColumn` | Rendu dans la section de la colonne supérieure du front-office (sous `displayTop`). | Affiche le bloc de marques dans la zone de la colonne supérieure. |

## 5. Support officiel et mises à jour

Pour les dernières mises à jour, corrections de bugs et support officiel du module « Bloc d'images des fabricants (marques) », veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu/my-account/orders/). Notre équipe de support est disponible pour vous aider avec tout problème ou question que vous pourriez avoir concernant la fonctionnalité et l'intégration du module.
