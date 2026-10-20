---
title: "Rechercher et remplacer du texte dans les champs de produit - Manuel du Marchand & Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop 'Rechercher et remplacer du texte dans les champs de produit' par MyPresta.eu."
sidebar:
  label: "Rechercher et remplacer du texte dans les champs de produit"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Search and replace text in product fields sur MyPresta.eu](https://mypresta.eu/modules/administration-tools/search-and-replace-text-in-product-fields.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/back-office-tools/search-and-replace-text-in-product-fields/)
>
> ---


# Rechercher et remplacer du texte dans les champs de produit

## 1. Exigences et compatibilité
-   **Versions de PrestaShop prises en charge** : PrestaShop 1.7.x, 8.x, 9.x
-   **Compatibilité PHP** : PHP 7.1 - 8.5
-   **Exigences d'hébergement** : Les extensions PHP standard (cURL, JSON, OpenSSL) sont généralement suffisantes. Aucune configuration serveur spéciale n'est requise au-delà d'un environnement d'hébergement PrestaShop standard.

## 2. Guide de configuration complet (Chaque paramètre regroupé par écran)

Le module "Rechercher et remplacer du texte dans les champs de produit" n'a pas de page de configuration traditionnelle avec des paramètres comme des interrupteurs ou des champs de saisie. Au lieu de cela, il s'intègre directement dans la liste des produits de PrestaShop, offrant une nouvelle action pour effectuer des opérations de recherche et de remplacement.

### 2.1 Accéder à l'outil de recherche et de remplacement

La fonctionnalité du module est accessible directement depuis votre liste de produits PrestaShop :

1.  **Naviguez vers la liste des produits :**
    -   Dans votre Back Office PrestaShop, allez dans **Catalogue > Produits**.
2.  **Sélectionnez les produits :**
    -   Vous pouvez soit sélectionner un ou plusieurs produits spécifiques en cochant les cases à côté d'eux, soit choisir d'appliquer la recherche et le remplacement à *tous* les produits actuellement affichés dans la liste (par exemple, si vous avez filtré la liste).
3.  **Accédez au menu Actions en masse :**
    -   Après avoir sélectionné des produits, un menu déroulant "Actions en masse" apparaîtra (généralement en haut ou en bas de la liste des produits).
4.  **Sélectionnez "Rechercher et remplacer du texte dans les champs de produit" :**
    -   Cliquez sur le menu déroulant "Actions en masse" et sélectionnez l'option intitulée **"Rechercher et remplacer du texte dans les champs de produit"**.

### 2.2 L'interface de recherche et de remplacement

Une fois que vous avez sélectionné l'action "Rechercher et remplacer du texte dans les champs de produit", une fenêtre modale ou une interface dédiée apparaîtra. C'est là que vous définissez votre opération de recherche et de remplacement.

**Champs disponibles pour la recherche et le remplacement :**
Le module vous permet de cibler divers champs de texte associés à vos produits. Ceux-ci incluent généralement :
-   **Nom du produit :** Le titre principal de votre produit.
-   **Description courte :** Le bref résumé souvent affiché près de l'image du produit.
-   **Description :** La description complète et détaillée du produit.
-   **Méta-titre :** Le titre affiché dans les onglets du navigateur et les résultats des moteurs de recherche.
-   **Méta-description :** Le court résumé affiché sous le titre dans les résultats des moteurs de recherche.
-   **URL simplifiée :** La partie conviviale pour le référencement de l'adresse web du produit.
-   **Mots-clés :** Mots-clés associés au produit.
-   **Caractéristiques :** Valeurs des caractéristiques de produit personnalisées (par exemple, "Couleur : Rouge" - vous pourriez remplacer "Rouge" par "Cramoisi").
-   **Valeurs d'attribut :** Valeurs pour les attributs de produit (par exemple, "Taille : S" - vous pourriez remplacer "S" par "Petit").
-   **Champs de personnalisation :** Champs de texte que les clients peuvent remplir pour la personnalisation du produit.

**Paramètres clés dans l'interface :**

-   **Rechercher :**
    -   **Ce que fait ce paramètre :** C'est la phrase de texte exacte que vous souhaitez trouver dans les champs de produit sélectionnés.
    -   **Effet de la modification de ce paramètre :** Le module recherchera cette chaîne de caractères précise. La casse est sensible par défaut, sauf si une option "Insensible à la casse" est fournie (vérifiez l'interface pour cela).
    -   **Valeur recommandée :** Saisissez le texte exact que vous souhaitez trouver.
    -   **Scénario / exemple pour le marchand :** Si vous souhaitez changer "ancien nom de marque" en "nouveau nom de marque", vous saisiriez "ancien nom de marque" ici.

-   **Remplacer par :**
    -   **Ce que fait ce paramètre :** C'est la nouvelle phrase de texte qui remplacera chaque instance du texte "Rechercher" trouvée.
    -   **Effet de la modification de ce paramètre :** Toutes les occurrences du texte "Rechercher" seront mises à jour avec ce nouveau texte. Si laissé vide, le texte "Rechercher" sera supprimé.
    -   **Valeur recommandée :** Saisissez le nouveau texte que vous souhaitez utiliser.
    -   **Scénario / exemple pour le marchand :** Suivant l'exemple ci-dessus, vous saisiriez "nouveau nom de marque" ici.

-   **Sélectionner les champs à rechercher :**
    -   **Ce que fait ce paramètre :** C'est une liste de cases à cocher ou un menu déroulant à sélection multiple où vous choisissez les champs de texte de produit spécifiques (par exemple, "Description", "Description courte", "Méta-titre") que le module doit traiter.
    -   **Effet de la modification de ce paramètre :** Seuls les champs sélectionnés seront scannés et modifiés. Les champs non sélectionnés resteront intacts.
    -   **Valeur recommandée :** Sélectionnez uniquement les champs pertinents pour votre tâche actuelle afin d'éviter des modifications involontaires.
    -   **Scénario / exemple pour le marchand :** Si vous souhaitez uniquement mettre à jour la description principale du produit, cochez uniquement "Description". Si vous mettez à jour un nom de marque partout, vous pourriez cocher "Nom du produit", "Description courte", "Description", "Méta-titre" et "Méta-description".

-   **Appliquer aux produits sélectionnés / Appliquer à tous les produits filtrés :**
    -   **Ce que fait ce paramètre :** Cela confirme si l'opération s'applique uniquement aux produits que vous avez cochés manuellement dans la liste, ou à tous les produits actuellement visibles dans la liste des produits (qui pourrait être un sous-ensemble filtré).
    -   **Effet de la modification de ce paramètre :** Détermine la portée de l'opération. Soyez très prudent avec "tous les produits filtrés" pour vous assurer que vos filtres sont correctement appliqués.
    -   **Valeur recommandée :** Vérifiez toujours votre sélection de produits avant de continuer.
    -   **Scénario / exemple pour le marchand :** Si vous avez filtré la liste des produits pour afficher uniquement les produits d'une catégorie spécifique, et que vous choisissez ensuite "Appliquer à tous les produits filtrés", les modifications n'affecteront que les produits de cette catégorie.

-   **Sensible à la casse / Insensible à la casse (si disponible) :**
    -   **Ce que fait ce paramètre :** Détermine si la recherche doit distinguer les lettres majuscules et minuscules.
    -   **Effet de la modification de ce paramètre :**
        -   *Sensible à la casse :* "Apple" ne correspondra pas à "apple".
        -   *Insensible à la casse :* "Apple" correspondra à "apple", "APPLE", "Apple", etc.
    -   **Valeur recommandée :** Utilisez l'option insensible à la casse pour les remplacements larges (par exemple, corriger une faute de frappe courante qui pourrait apparaître dans différentes casses). Utilisez l'option sensible à la casse pour les remplacements précis où la casse est importante.
    -   **Scénario / exemple pour le marchand :** Si vous souhaitez remplacer "ProduitX" par "Produit Y", mais que certaines descriptions peuvent contenir "produitX", l'utilisation de l'option insensible à la casse les détectera toutes les deux.

-   **Aperçu / Simulation (si disponible) :**
    -   **Ce que fait ce paramètre :** Certains outils de recherche et de remplacement avancés offrent un mode "aperçu" ou "simulation" qui vous montre les modifications qui *seraient* apportées sans les enregistrer réellement.
    -   **Effet de la modification de ce paramètre :** Vous permet de revoir l'impact de votre opération avant de la valider, évitant ainsi la perte accidentelle de données.
    -   **Valeur recommandée :** Utilisez toujours un aperçu si disponible, surtout pour les opérations à grande échelle.
    -   **Scénario / exemple pour le marchand :** Avant de remplacer "ancien" par "nouveau" sur 1000 produits, un aperçu vous montrerait exactement quels produits et champs seraient affectés.

### 2.3 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Valeur par défaut / Recommandée | Objectif et impact |
| :------------ | :--------------- | :-------------------- | :--------------- |
| Liste des produits (Actions en masse) | Rechercher | Défini par l'utilisateur | La chaîne de texte exacte à trouver. Sensible à la casse sauf indication contraire. |
| Liste des produits (Actions en masse) | Remplacer par | Défini par l'utilisateur | La chaîne de texte pour remplacer le texte 'Rechercher'. Vide supprime le texte. |
| Liste des produits (Actions en masse) | Sélectionner les champs à rechercher | Défini par l'utilisateur | Cases à cocher pour sélectionner les champs de produit (description, nom, méta, etc.) à modifier. |
| Liste des produits (Actions en masse) | Appliquer aux produits sélectionnés / tous les produits filtrés | Défini par l'utilisateur | Définit la portée de l'opération : uniquement les produits cochés ou tous les produits actuellement filtrés. |
| Liste des produits (Actions en masse) | Sensible à la casse / Insensible à la casse | (Vérifier l'interface du module) | Détermine si la recherche distingue les lettres majuscules et minuscules. |
| Liste des produits (Actions en masse) | Aperçu / Simulation | (Si disponible, toujours utiliser) | Affiche les modifications potentielles avant de les appliquer, évitant les erreurs. |

## 3. Dépannage pour les marchands et questions fréquemment posées (FAQ)

**Q : J'ai effectué la recherche et le remplacement, mais je ne vois pas les modifications sur mon site web.**
R : PrestaShop utilise la mise en cache pour accélérer votre boutique. Après avoir effectué des modifications dans le back office, vous devez souvent vider le cache pour qu'elles apparaissent sur le front office.
    -   Allez dans **Paramètres avancés > Performances**.
    -   Cliquez sur "Vider le cache" dans le coin supérieur droit.
    -   Si vous utilisez un module de mise en cache tiers ou un CDN, videz également leurs caches.

**Q : Le module n'apparaît pas dans le menu "Actions en masse" de la liste des produits.**
R :
    1.  **Vérifier l'installation :** Assurez-vous que le module est correctement installé et activé dans **Modules > Gestionnaire de modules**.
    2.  **Permissions :** Vérifiez que votre compte utilisateur dispose des permissions nécessaires pour gérer les modules et les produits.
    3.  **Conflits de modules :** Rarement, un autre module qui modifie fortement la liste des produits ou les actions en masse pourrait entrer en conflit. Essayez de désactiver temporairement d'autres modules récemment installés pour voir si le problème se résout.

**Q : J'ai accidentellement remplacé le mauvais texte ou fait une erreur. Comment puis-je annuler ?**
R : Malheureusement, le module effectue une mise à jour directe de la base de données, et il n'y a pas de bouton "annuler" intégré. C'est pourquoi les sauvegardes sont cruciales.
    -   **Restaurer à partir d'une sauvegarde :** Le moyen le plus sûr de revenir en arrière est de restaurer votre base de données à partir d'une sauvegarde effectuée *avant* d'exécuter l'opération.
    -   **Exécuter une opération inverse :** Si vous n'avez modifié qu'une simple phrase, vous pourriez être en mesure d'exécuter une autre opération de recherche et de remplacement pour la rétablir (par exemple, rechercher "nouveau texte" et remplacer par "ancien texte"). C'est risqué et ne fonctionne que pour les remplacements simples et directs.

**Q : Puis-je utiliser ce module pour les boutiques multilingues ?**
R : Oui, le module opère sur les champs de produit, qui sont souvent multilingues dans PrestaShop. Lorsque vous sélectionnez des champs comme "Description" ou "Nom du produit", le module appliquera généralement la recherche et le remplacement à toutes les langues actives pour ces champs. L'interface devrait vous permettre de spécifier les langues à cibler si cette option est disponible.

**Q : L'opération de recherche et de remplacement est très lente ou expire pour un grand nombre de produits.**
R :
    1.  **Ressources du serveur :** Les opérations importantes sur des milliers de produits peuvent être gourmandes en ressources. Assurez-vous que votre serveur dispose de limites de mémoire PHP et de temps d'exécution adéquats. Vous devrez peut-être augmenter `memory_limit` et `max_execution_time` dans votre `php.ini` (consultez votre hébergeur ou votre webmaster).
    2.  **Traiter par lots :** Si possible, filtrez votre liste de produits et exécutez l'opération sur de plus petits lots de produits (par exemple, par catégorie, marque ou plage d'ID) au lieu d'essayer de traiter l'ensemble de votre catalogue en une seule fois.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

Cette section fournit un aperçu technique pour les développeurs et les webmasters souhaitant comprendre, déboguer ou étendre le module "Rechercher et remplacer du texte dans les champs de produit".

### 4.1 Aperçu de l'architecture
Le module `snrp` est un module PrestaShop simple principalement axé sur l'extension de la fonctionnalité de la liste des produits du Back Office. Il utilise le système de hooks de PrestaShop pour injecter une nouvelle action en masse dans le contrôleur `AdminProducts`. La logique principale réside dans le fichier principal du module, gérant l'affichage du formulaire de recherche/remplacement et l'exécution des mises à jour de la base de données. Il n'utilise pas de classes `ObjectModel` personnalisées ou de contrôleurs d'administration dédiés, mais étend plutôt les vues d'administration PrestaShop existantes.

### 4.2 Contrôleurs (`controllers/`)
Ce module n'introduit aucun contrôleur Front-Office ou Back-Office personnalisé. Sa fonctionnalité est intégrée au contrôleur `AdminProducts` existant via des hooks.

### 4.3 Classes et modèles de base (`classes/`)
Ce module ne définit aucune classe personnalisée dans un répertoire `classes/`. Toute la logique de base est contenue dans le fichier principal du module `snrp/index.php`. Le module interagit directement avec les `ObjectModel` `Product` et `ProductLang` de PrestaShop, et potentiellement les données `FeatureValue`, `AttributeGroup` et `Tag`, en effectuant des mises à jour SQL basées sur l'entrée de l'utilisateur.

### 4.4 Actifs JavaScript (`views/js/`)

-   **`snrp/views/js/snrp.js`**
    *   **Portée :** Back-office (spécifiquement, la page de liste `AdminProducts`).
    *   **Responsabilité :** Ce script est responsable du comportement côté client de l'outil de recherche et de remplacement.
        *   Il lie probablement un écouteur d'événements à l'option "Rechercher et remplacer du texte dans les champs de produit" dans le menu déroulant "Actions en masse".
        *   Lorsqu'il est sélectionné, il déclenche l'affichage de la fenêtre modale ou du formulaire où l'utilisateur saisit le terme de recherche, le terme de remplacement et sélectionne les champs cibles.
        *   Il gère la requête AJAX vers la méthode `getContent()` du module (ou un point de terminaison AJAX dédié s'il était implémenté dans `index.php`) pour soumettre les paramètres de recherche et de remplacement.
        *   Il gère le retour d'information de l'interface utilisateur pendant et après l'opération (par exemple, indicateurs de chargement, messages de succès/erreur).
        *   Il peut inclure une logique de validation pour les champs de saisie avant la soumission.

### 4.5 Feuilles de style CSS (`views/css/`)

-   **`snrp/views/css/snrp.css`**
    *   **Portée :** Back-office (spécifiquement, la page de liste `AdminProducts`).
    *   **Responsabilité :** Cette feuille de style fournit le style visuel de l'interface de recherche et de remplacement.
        *   Elle définit l'apparence de la fenêtre modale (taille, positionnement, superposition d'arrière-plan).
        *   Elle stylise les champs de saisie, les boutons, les cases à cocher et tout autre élément d'interface utilisateur dans le formulaire de recherche et de remplacement.
        *   Elle garantit que l'interface s'intègre visuellement au thème du Back Office de PrestaShop.
    *   **Sélecteurs de classes CSS clés que les développeurs peuvent surcharger :** Les développeurs peuvent inspecter le HTML généré de la modale pour identifier des noms de classes spécifiques (par exemple, `.snrp-modal`, `.snrp-form-group`, `.snrp-button`) afin de personnaliser son apparence dans leurs thèmes d'administration personnalisés ou via `override/css/admin.css`.

### 4.6 Structure des templates Smarty (`views/templates/`)
La description du module indique qu'il n'y a pas de fichiers `.tpl` dans `views/templates/`. Cela suggère que le formulaire de configuration du module et l'interface modale de recherche/remplacement sont probablement rendus directement dans la méthode `getContent()` de `snrp/index.php` en utilisant du HTML brut et du PHP, ou en générant dynamiquement les éléments du formulaire via JavaScript.

Si une modale est utilisée, il est possible que la structure HTML soit injectée directement dans le DOM par `snrp.js` ou rendue dans le cadre de la réponse `getContent()`.

### 4.7 Schéma de la base de données et carte des hooks

-   **Tables de base de données** :
    *   Ce module ne crée aucune table de base de données personnalisée.
    *   Il modifie directement les tables PrestaShop existantes, principalement :
        *   `ps_product_lang` : Pour les noms de produits, les descriptions courtes, les descriptions, les méta-titres, les méta-descriptions et les URL simplifiées (champs spécifiques à la langue).
        *   `ps_tag` : Pour les mots-clés de produits.
        *   Potentiellement `ps_feature_product` et `ps_product_attribute_lang` si les valeurs de caractéristiques et les valeurs d'attributs sont ciblées.
    *   Les paramètres de configuration (s'il y en avait) seraient généralement stockés dans `ps_configuration`.

-   **Table des hooks enregistrés** :

| Nom du hook | Moment d'exécution | Objectif technique |
| :-------- | :--------------- | :---------------- |
| `displayBackOfficeHeader` | Rendu dans la section `<head>` du Back Office. | Utilisé pour inclure `snrp.js` et `snrp.css` sur les pages d'administration pertinentes (par exemple, `AdminProducts`). |
| `displayAdminProductsExtra` | Rend du contenu supplémentaire sur la page de liste `AdminProducts`. | Ce hook est probablement utilisé pour injecter la structure HTML de l'option "Rechercher et remplacer du texte dans les champs de produit" dans le menu déroulant "Actions en masse" ou pour ajouter un bouton qui déclenche la modale. |
| `actionProductUpdate` / `actionObjectProductUpdateAfter` | Exécuté après la mise à jour d'un produit. | Bien que non explicitement indiqué, le module pourrait se connecter à ceux-ci pour effectuer des actions supplémentaires ou de la journalisation après une opération de recherche et de remplacement réussie, bien que les mises à jour SQL directes soient plus probables pour la performance. |
| `actionAdminProductsListingResultsModifier` | Modifie les résultats de la liste des produits. | Moins probable pour ce module, mais pourrait être utilisé pour ajouter une colonne ou modifier les données affichées avant que l'action de recherche/remplacement ne soit déclenchée. |

La fonctionnalité principale d'exécution de la logique de recherche et de remplacement sera gérée dans la méthode `getContent()` du module (ou une méthode AJAX dédiée dans `index.php`) lorsque le formulaire est soumis, traitant les ID de produit et les champs sélectionnés.

## 5. Support officiel et mises à jour
Pour les dernières mises à jour, corrections de bugs et support officiel du module "Rechercher et remplacer du texte dans les champs de produit", veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu/my-account/orders/). Notre équipe de support est disponible pour vous aider avec tout problème ou question que vous pourriez avoir concernant la fonctionnalité et la compatibilité du module.
