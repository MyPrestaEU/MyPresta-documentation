---
title: "Page produit comme page d'accueil de la boutique - Manuel du marchand et guide de configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop 'Page produit comme page d'accueil de la boutique' par MyPresta.eu."
sidebar:
  label: "Page produit comme page d'accueil de la boutique - Manuel du marchand et guide de configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Product page as shop homepage sur MyPresta.eu](https://mypresta.eu/modules/front-office-features/product-page-as-shop-homepage.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/front-office/product-page-as-shop-homepage/)
>
> ---


# Page produit comme page d'accueil de la boutique

## 1. Exigences et compatibilité

- **Versions de PrestaShop prises en charge** : PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilité PHP** : PHP 7.1 - 8.5
- **Exigences d'hébergement** : Extensions PHP standard (cURL, JSON, OpenSSL).

## 2. Guide de configuration complet (chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

Après l'installation, cliquez sur « Configurer » à côté du module « Page produit comme page d'accueil de la boutique ». Vous verrez une option de configuration unique et simple.

- **Nom du paramètre :** Produit à afficher sur la page d'accueil
  - **Ce que fait ce paramètre :** C'est le paramètre le plus crucial. Il vous permet de sélectionner exactement quel produit de votre catalogue deviendra la nouvelle page d'accueil de votre boutique.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'un produit est sélectionné :* L'URL principale de votre boutique affichera la page produit complète du produit choisi.
    - *Lorsqu'aucun produit n'est sélectionné (ou que le module est désactivé) :* Votre boutique reviendra à son comportement de page d'accueil par défaut (par exemple, affichage de produits phares, de catégories ou d'une page CMS personnalisée).
  - **Valeur recommandée :** Sélectionnez le produit que vous souhaitez mettre en avant le plus. Utilisez la barre de recherche pour trouver rapidement le produit souhaité.
  - **Scénario / exemple de marchand :** Vous venez de lancer un nouveau gadget révolutionnaire. Vous voulez que chaque visiteur de votre boutique voie ce produit en premier. Vous taperiez le nom du produit (par exemple, « Super Gadget X ») dans la boîte de recherche, le sélectionneriez dans la liste déroulante et enregistreriez. Désormais, toute personne visitant `www.votreboutique.com` atterrira directement sur la page produit « Super Gadget X ».

### 2.2 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Par défaut / Recommandé | Objectif et impact |
| --- | --- | --- | --- |
| Page de configuration du module | Produit à afficher sur la page d'accueil | (Aucun sélectionné initialement) / Sélectionnez votre produit clé | Définit quelle page produit remplacera la page d'accueil par défaut de votre boutique. |

## 3. Dépannage pour les marchands et questions fréquemment posées (FAQ)

**Q : Ma page d'accueil affiche toujours l'ancien contenu après avoir configuré le module. Que dois-je faire ?**
R : Il s'agit généralement d'un problème de cache.
1. Allez dans **Paramètres avancés > Performance** dans votre Back Office PrestaShop.
2. Cliquez sur « Vider le cache » dans le coin supérieur droit.
3. Videz également le cache et les cookies de votre navigateur, puis essayez d'accéder à nouveau à votre boutique.

**Q : Puis-je changer facilement le produit mis en avant ?**
R : Oui ! Il suffit de retourner dans **Modules > Gestionnaire de modules**, de trouver « Page produit comme page d'accueil de la boutique », de cliquer sur « Configurer » et de sélectionner un autre produit dans la liste déroulante. Enregistrez vos modifications et videz votre cache.

**Q : Que se passe-t-il si le produit sélectionné est en rupture de stock ou désactivé ?**
R : Si le produit sélectionné est en rupture de stock, sa page produit sera toujours affichée, mais le bouton « Ajouter au panier » pourrait être désactivé ou afficher un message « Rupture de stock », selon vos paramètres d'inventaire PrestaShop. Si le produit est complètement désactivé, PrestaShop pourrait afficher une erreur « Page introuvable » ou revenir à la page d'accueil par défaut. Assurez-vous toujours que le produit sélectionné est actif et disponible.

**Q : Ce module affecte-t-il mon SEO ?**
R : Lorsque vous définissez une page produit comme page d'accueil, l'URL principale de votre boutique (`www.votreboutique.com`) servira désormais le contenu de cette page produit. Les moteurs de recherche indexeront ce contenu pour votre domaine principal. Si vous aviez auparavant une page d'accueil riche et optimisée pour les mots-clés, vous pourriez constater un changement dans la façon dont votre domaine principal est classé. Assurez-vous que la page produit choisie est bien optimisée pour le SEO (titre, description, images, contenu).

**Q : Puis-je l'utiliser avec un thème personnalisé ?**
R : Oui, le module fonctionne en remplaçant la façon dont PrestaShop distribue le `IndexController`. Il devrait être compatible avec la plupart des thèmes personnalisés car il utilise le rendu standard des pages produit de PrestaShop. Si vous rencontrez des problèmes de style, cela est probablement lié au CSS de votre thème, et non à la fonctionnalité principale du module.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

### 4.1 Aperçu de l'architecture

Le module « Page produit comme page d'accueil de la boutique » fonctionne en remplaçant les contrôleurs frontaux PrestaShop principaux pour rediriger le comportement de la page d'accueil par défaut (`IndexController`). Au lieu de charger le modèle de page d'accueil standard, il force le `ProductController` à rendre la page pour un ID de produit spécifique, faisant ainsi d'une page produit la page de destination par défaut pour l'URL racine de la boutique. Ceci est réalisé grâce à une série de remplacements dans le répertoire `override/`.

### 4.2 Contrôleurs (`controllers/`)

Ce module utilise principalement des remplacements pour modifier le comportement du contrôleur.

- **Contrôleurs Front-Office** :
  - `homepageproduct/override/controllers/front/index.php`
    - Ce fichier est un espace réservé ou un ancien remplacement. Dans PrestaShop moderne, le `IndexController` est généralement remplacé directement. Sa présence suggère un mécanisme de compatibilité ou une approche plus ancienne.
  - `homepageproduct/override/controllers/front/IndexController.php`
    - **Nom de la classe et classe parente :** `IndexController` (remplace `IndexControllerCore`)
    - **Responsabilité :** C'est le remplacement principal. Lorsque l'URL racine de la boutique est accédée, PrestaShop distribue normalement `IndexController`. Ce remplacement intercepte cette distribution. Il vérifie la configuration du module pour un ID `homepageproduct_product`. Si un ID de produit est défini, il redirige ou transfère ensuite la requête en interne vers le `ProductController` pour ce produit spécifique, rendant ainsi la page produit au lieu de la page d'accueil par défaut. Il garantit que le contexte du contrôleur actuel est correctement défini sur `ProductController` et que les données du produit sont chargées.

### 4.3 Classes et modèles de base (`classes/`)

Ce module utilise des remplacements pour modifier le comportement des classes de base, spécifiquement lié à la gestion des contrôleurs.

- `homepageproduct/override/classes/controller/FrontController.php`
  - **Nom de la classe et classe parente :** `FrontController` (remplace `FrontControllerCore`)
  - **Responsabilité :** Ce remplacement contient probablement une logique pour garantir que le remplacement de `IndexController` fonctionne correctement dans le processus de distribution de `FrontController`. Il pourrait ajuster la façon dont le contrôleur est initialisé ou comment les modèles sont attribués lorsque la page d'accueil est servie comme page produit.
- `homepageproduct/override/classes/controller/index.php`
  - Similaire à `override/controllers/front/index.php`, cela semble être un espace réservé ou un ancien mécanisme de remplacement.
- `homepageproduct/override/classes/index.php`
  - Un autre espace réservé ou ancien remplacement.

### 4.4 Actifs JavaScript (`views/js/`)

Le module n'inclut aucun fichier JavaScript personnalisé. Toute l'interactivité front-office pour la page produit provient du JS de la page produit de base de PrestaShop.

### 4.5 Feuilles de style CSS (`views/css/`)

Le module n'inclut aucun fichier CSS personnalisé. Le style de la page produit est entièrement géré par le thème PrestaShop actif.

### 4.6 Structure des modèles Smarty (`views/templates/`)

Le module n'introduit pas de nouveaux modèles front-office pour l'affichage. Il réutilise les modèles de page produit PrestaShop existants.

- **Modèles d'administration (`views/templates/admin/`)** :
  - `homepageproduct/lib/searchTool/views/scripts.tpl`
    - Ce modèle est probablement utilisé dans la méthode `getContent()` du module dans le back office. Il contient probablement du JavaScript ou de la logique Smarty pour rendre le champ de saisie de recherche de produit, permettant à l'administrateur de trouver et de sélectionner facilement un produit par nom ou ID pour la page d'accueil. Il pourrait inclure des appels AJAX à `AdminProducts` ou des contrôleurs similaires pour des suggestions de produits.

### 4.7 Schéma de base de données et carte des hooks

- **Tables de base de données** :

  - Le module ne crée aucune table de base de données personnalisée.
  - Il stocke sa configuration dans la table `ps_configuration` :
    - `homepageproduct_product` : Stocke l'ID du produit sélectionné pour être la page d'accueil.
    - `mypresta_updates`, `update_`, `updatev_` : Utilisés pour les vérifications de mise à jour du module par MyPresta.eu.
    - `PS_BO_ALLOW_EMPLOYEE_FORM_LANG` : Une clé de configuration PrestaShop standard, non directement gérée par ce module mais potentiellement accessible.
- **Table des hooks enregistrés** :
  Le module n'enregistre explicitement aucun nouveau hook d'affichage. Sa fonctionnalité est obtenue par des remplacements de contrôleurs. Cependant, comme il rend une page produit standard, tous les hooks normalement présents sur une page produit (par exemple, `displayHeader`, `displayProductButtons`, `displayFooter`, `displayLeftColumn`, `displayRightColumn`, `displayProductExtraContent`, `actionValidateOrder`) seront exécutés comme s'il s'agissait d'une page produit normale.

| Nom du hook | Moment d'exécution | Objectif technique |
| --- | --- | --- |
| `displayHeader` | Avant le contenu de la page | Pour inclure CSS, JS, balises meta. |
| `displayLeftColumn` | Colonne de gauche de la page produit | Affichage de blocs comme les catégories, les filtres. |
| `displayRightColumn` | Colonne de droite de la page produit | Affichage de blocs comme le panier, le contenu personnalisé. |
| `displayFooter` | En bas de la page | Pour inclure JS, contenu du pied de page. |
| `displayProductButtons` | Près du bouton Ajouter au panier | Ajout de boutons ou d'actions personnalisés sur la page produit. |
| `displayProductExtraContent` | Sous la description du produit | Ajout d'onglets ou de contenu supplémentaires à la page produit. |
| `actionValidateOrder` | Après la validation d'une commande | Pour le traitement post-commande (par exemple, le suivi). |
| *(Tout autre hook normalement sur une page produit)* | Varie | Exécution standard des hooks de page produit PrestaShop. |

## 5. Support officiel et mises à jour

Pour les dernières mises à jour, corrections de bugs et support professionnel pour le module « Page produit comme page d'accueil de la boutique », veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu/my-account/orders/). Notre équipe est dédiée à assurer le bon fonctionnement et l'amélioration continue de nos modules.
