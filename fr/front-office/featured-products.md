---
title: "Produits Phares - Manuel Marchand & Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop Produits Phares par MyPresta.eu."
sidebar:
  label: "Produits Phares - Manuel Marchand & Guide de Configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Featured Products sur MyPresta.eu](https://mypresta.eu/modules/front-office-features/featured-products.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/front-office/featured-products/)
>
> ---


# Produits Phares

## 1. Exigences et compatibilité

- **Versions de PrestaShop prises en charge** : PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilité PHP** : PHP 7.1 - 8.5
- **Exigences d'hébergement** : Les extensions PHP standard (cURL, JSON, OpenSSL) sont généralement suffisantes. Aucune configuration de serveur spéciale n'est requise.

## 2. Guide de configuration complet (Chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

Pour accéder à la configuration, naviguez vers **Modules > Gestionnaire de modules**, recherchez « Produits Phares » et cliquez sur « Configurer ».

Cet écran vous permet de définir quels produits sont affichés et comment ils apparaissent sur votre page d'accueil.

#### Paramètres et options :

1. **ID de la catégorie source**

   - **Ce que fait ce paramètre :** C'est le paramètre le plus crucial. Il détermine *quelle* catégorie de produits sera affichée comme « phare » sur votre page d'accueil. Vous devez entrer l'ID numérique de la catégorie que vous souhaitez mettre en avant.
   - **Effet de la modification de ce paramètre :**
     - *Lorsqu'il est défini sur un ID de catégorie valide (par exemple, `3` pour « Vêtements ») :* Le module récupérera et affichera les produits appartenant à la catégorie avec cet ID.
     - *Lorsqu'il est défini sur un ID invalide ou inexistant :* Aucun produit ne sera affiché, ou une erreur pourrait se produire si l'ID est mal formé.
   - **Valeur recommandée :** L'ID de la catégorie que vous souhaitez promouvoir.
   - **Scénario / exemple marchand :** Si vous souhaitez mettre en avant votre catégorie « Nouveautés » (qui a un ID de, disons, `12`), vous entreriez `12` ici. Pour trouver un ID de catégorie, allez dans **Catalogue > Catégories** dans votre Back Office, cliquez sur « Modifier » sur une catégorie, et regardez l'URL dans votre navigateur (par exemple, `id_category=12`).
2. **Nombre de produits**

   - **Ce que fait ce paramètre :** Cela contrôle le nombre de produits de votre « Catégorie source » sélectionnée qui seront affichés sur la page d'accueil.
   - **Effet de la modification de ce paramètre :**
     - *Lorsqu'il est défini sur `5` :* Seuls les 5 premiers produits de la catégorie choisie seront affichés.
     - *Lorsqu'il est défini sur `10` :* Jusqu'à 10 produits seront affichés.
   - **Valeur recommandée :** Un nombre raisonnable comme `8` ou `12` pour éviter de surcharger la page d'accueil, mais suffisant pour présenter de la variété. Tenez compte de la mise en page de votre thème.
   - **Scénario / exemple marchand :** Si votre catégorie « Nouveautés » contient 50 produits, mais que vous ne souhaitez afficher que les 8 derniers sur la page d'accueil, vous définiriez ce paramètre sur `8`.
3. **Position de placement**

   - **Ce que fait ce paramètre :** Cela détermine *comment* les produits phares sont affichés sur votre page d'accueil : soit directement dans la zone de contenu principale (`displayHome`), soit dans un onglet (`displayHomeTabContent`).
   - **Effet de la modification de ce paramètre :**
     - *Lorsqu'il est défini sur `Onglet de la page d'accueil` :* Les produits apparaîtront sous un nouvel onglet sur votre page d'accueil (par exemple, « Produits Phares »). Cela nécessite que votre thème prenne en charge les onglets de la page d'accueil.
     - *Lorsqu'il est défini sur `Page d'accueil` :* Les produits seront affichés comme une section autonome directement sur votre page d'accueil, sans être cachés derrière un onglet.
   - **Valeur recommandée :**
     - Choisissez `Onglet de la page d'accueil` si votre thème utilise des onglets pour les listes de produits (comme le font souvent les thèmes PrestaShop par défaut) et que vous souhaitez garder votre page d'accueil propre.
     - Choisissez `Page d'accueil` si vous souhaitez une visibilité maximale pour ces produits et que votre thème dispose de suffisamment d'espace dans la zone de contenu principale.
   - **Scénario / exemple marchand :** Si vous organisez une promotion spéciale et que vous souhaitez que les produits soient immédiatement visibles sans que les clients aient besoin de cliquer sur un onglet, vous sélectionneriez `Page d'accueil`. Si vous avez de nombreux types de produits présentés sur votre page d'accueil et que vous souhaitez les organiser proprement, `Onglet de la page d'accueil` est un meilleur choix.

#### Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Par défaut / Recommandé | Objectif et impact |
| --- | --- | --- | --- |
| Configuration du module | ID de la catégorie source | (Votre ID de catégorie) | Spécifie les produits de quelle catégorie sont affichés. |
| Configuration du module | Nombre de produits | 8-12 | Limite le nombre de produits affichés de la catégorie sélectionnée. |
| Configuration du module | Position de placement | Onglet de la page d'accueil / Page d'accueil | Détermine si les produits apparaissent dans un onglet ou directement sur la page d'accueil. |

## 3. Dépannage marchand et questions fréquemment posées (FAQ)

**Q : Mes produits phares n'apparaissent pas sur la page d'accueil.**
R :

1. **Vérifiez l'« ID de la catégorie source » :** Assurez-vous d'avoir entré un ID de catégorie correct et existant. Allez dans **Catalogue > Catégories**, modifiez la catégorie souhaitée et trouvez son ID dans l'URL du navigateur (par exemple, `id_category=X`).
2. **Vérifiez le « Nombre de produits » :** Assurez-vous qu'il est défini sur une valeur supérieure à 0.
3. **Vérifiez la « Position de placement » :** Si elle est définie sur « Onglet de la page d'accueil », assurez-vous que votre thème prend réellement en charge et affiche les onglets de la page d'accueil. Certains thèmes personnalisés pourraient ne pas le faire. Essayez de passer à « Page d'accueil » pour voir s'ils apparaissent comme une section directe.
4. **Videz le cache :** Allez dans **Paramètres avancés > Performance** et cliquez sur « Vider le cache ». Parfois, le cache de PrestaShop empêche les modifications d'apparaître immédiatement.

**Q : Les produits s'affichent, mais ils semblent mal alignés ou ont un style incorrect.**
R : Il s'agit généralement d'un problème lié au thème.

1. **Compatibilité du thème :** Bien que le module soit compatible avec les versions de PrestaShop, sa sortie visuelle peut entrer en conflit avec des thèmes fortement personnalisés.
2. **Conflit CSS :** Le CSS de votre thème peut remplacer ou entrer en conflit avec le style par défaut du module. Vous pourriez avoir besoin d'un développeur web pour inspecter le CSS et appliquer des styles personnalisés au fichier `featuredcategory.css` ou au fichier CSS personnalisé de votre thème.

**Q : Puis-je présenter des produits de plusieurs catégories ?**
R : Pas directement avec ce module. Le module « Produits Phares » est conçu pour afficher les produits d'une *seule* catégorie sélectionnée à la fois. Si vous avez besoin de présenter des produits de plusieurs catégories simultanément, vous devrez soit :
a) Créer une nouvelle catégorie « Maître des produits phares » et y ajouter des produits de différentes catégories.
b) Installer plusieurs instances de ce module (si votre thème le permet) ou utiliser un module différent conçu pour les affichages multi-catégories.

**Q : Comment traduire le titre de l'onglet « Produits Phares » ?**
R : Si vous utilisez le placement « Onglet de la page d'accueil », le titre de l'onglet est généralement généré par le module.

1. Allez dans **International > Traductions**.
2. Sélectionnez « Traductions des modules installés », votre thème et votre langue.
3. Recherchez le module « Produits Phares ». Vous devriez y trouver la chaîne de texte pour le titre de l'onglet et pouvoir la traduire.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

Cette section est strictement destinée aux développeurs, aux webmasters de boutiques et aux agences techniques qui maintiennent ou étendent la boutique.

### 4.1 Aperçu de l'architecture

Le module `Featured Products` est un module PrestaShop simple, principalement conçu pour afficher une liste de produits d'une catégorie spécifiée sur la page d'accueil. Il utilise le système de hooks de PrestaShop (`displayHome`, `displayHomeTab`, `displayHomeTabContent`) pour injecter son contenu. La logique du module est contenue dans son fichier PHP principal, `featuredcategory.php`, qui gère la configuration, l'installation et le rendu du contenu. Il n'introduit pas de contrôleurs, de modèles ou de JavaScript complexes personnalisés, ce qui en fait une solution légère et facilement maintenable.

### 4.2 Contrôleurs (`controllers/`)

- **Contrôleurs Front-Office** : Aucun. Tout le rendu du contenu front-office est géré directement via des hooks dans le fichier `featuredcategory.php` principal et les templates Smarty associés.
- **Contrôleurs d'administration Back-Office** : Aucun. La configuration du module est gérée via la méthode standard `getContent()` dans le fichier principal du module.

### 4.3 Classes et modèles principaux (`classes/`)

- Aucune classe personnalisée ou définition d'`ObjectModel` n'est présente dans ce module. Toutes les récupérations de données (produits, catégories) sont effectuées à l'aide des classes `Product` et `Category` de base de PrestaShop.

### 4.4 Actifs JavaScript (`views/js/`)

- Aucun fichier JavaScript personnalisé n'est inclus avec ce module.

### 4.5 Feuilles de style CSS (`views/css/`)

- `featuredcategory/css/featuredcategory.css`
  - **Portée :** Style client Front-Office.
  - **Principaux composants et conteneurs d'interface utilisateur qu'il stylise :** Cette feuille de style fournit un style de base pour la liste de produits générée par le module, garantissant qu'elle est présentable dans le contexte de la page d'accueil. Elle cible probablement les conteneurs génériques de liste de produits et les éléments de produit individuels.
  - **Sélecteurs de classe CSS clés que les développeurs peuvent remplacer dans leur thème :** Les développeurs peuvent inspecter la sortie HTML du module pour identifier des classes spécifiques (par exemple, `.featuredcategory-products`, `.product-item`, `.product-name`) et les remplacer dans le fichier CSS personnalisé de leur thème pour correspondre à la conception globale de la boutique.

### 4.6 Structure des templates Smarty (`views/templates/`)

Le module utilise des templates Smarty pour rendre son contenu, principalement pour les hooks de la page d'accueil.

- **Templates de hook (`views/templates/hook/`)** :
  - `featuredcategory/views/templates/hook/featuredcategory17-tabContents.tpl`
    - **Hook :** `displayHomeTabContent`
    - **Objectif :** Ce template est responsable du rendu de la liste réelle des produits phares lorsque la « Position de placement » est définie sur « Onglet de la page d'accueil ». Il contient généralement la boucle pour itérer sur les produits et afficher leurs détails (image, nom, prix, bouton ajouter au panier).
  - `featuredcategory/views/templates/hook/featuredcategory17.tpl`
    - **Hook :** `displayHome`
    - **Objectif :** Ce template rend la liste des produits phares lorsque la « Position de placement » est définie sur « Page d'accueil » (c'est-à-dire, pas dans un onglet). Il produira la même structure de liste de produits que `featuredcategory17-tabContents.tpl` mais directement dans le hook `displayHome` principal.
  - `featuredcategory/views/templates/hook/tab.tpl`
    - **Hook :** `displayHomeTab`
    - **Objectif :** Ce template rend le titre réel de l'onglet (par exemple, « Produits Phares ») qui apparaît sur la page d'accueil lorsque la « Position de placement » est définie sur « Onglet de la page d'accueil ». Il fournit l'élément cliquable qui révèle le contenu de `featuredcategory17-tabContents.tpl`.
- **Templates d'administration (`views/templates/admin/`)** : Aucun.
- **Templates Front-Office (`views/templates/front/`)** : Aucun.

### 4.7 Schéma de la base de données et carte des hooks

- **Tables de base de données** : Ce module ne crée aucune table de base de données personnalisée. Il stocke ses paramètres de configuration dans la table `ps_configuration` de PrestaShop.

  - Entrées `ps_configuration` :
    - `CFEATURED_NBR` : Stocke le paramètre « Nombre de produits ».
    - `CFEATURED_ID` : Stocke le paramètre « ID de la catégorie source ».
    - `CFEATURED_WHERE` : Stocke le paramètre « Position de placement » (par exemple, 'tab' ou 'home').
    - `mypresta_updates` : Utilisé pour les vérifications de mise à jour du module par MyPresta.eu.
- **Table des hooks enregistrés** :

| Nom du hook | Moment d'exécution | Objectif technique |
| --- | --- | --- |
| `displayHomeTab` | Rend le contenu d'un nouvel onglet sur la page d'accueil. | Affiche le HTML pour le titre de l'onglet « Produits Phares ». |
| `displayHomeTabContent` | Rend le contenu de l'onglet sélectionné sur la page d'accueil. | Affiche le HTML pour la liste des produits phares lorsque l'onglet est actif. |
| `displayHome` | Rend le contenu directement dans la zone principale de la page d'accueil. | Affiche le HTML pour la liste des produits phares lorsque les onglets ne sont pas utilisés. |
| `displayHeader` | Exécuté dans la section `<head>` de chaque page. | Utilisé pour inclure la feuille de style CSS du module (`featuredcategory.css`) pour l'affichage front-office. |
| `actionProductDelete` | Déclenché après la suppression d'un produit. | Potentiellement utilisé pour vider le cache ou réévaluer les produits phares si le produit supprimé était dans la catégorie phare. |
| `actionProductUpdate` | Déclenché après la mise à jour d'un produit. | Potentiellement utilisé pour vider le cache ou réévaluer les produits phares si le produit mis à jour est dans la catégorie phare. |
| `actionProductAdd` | Déclenché après l'ajout d'un nouveau produit. | Potentiellement utilisé pour vider le cache ou réévaluer les produits phares si le nouveau produit est dans la catégorie phare. |
| `actionCategoryUpdate` | Déclenché après la mise à jour d'une catégorie. | Potentiellement utilisé pour vider le cache ou réévaluer les produits phares si la catégorie phare elle-même est mise à jour. |

## 5. Support officiel et mises à jour

Pour les dernières mises à jour du module, les corrections de bugs et le support officiel, veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu/my-account/orders/). Notre équipe de support est disponible pour vous aider avec tout problème ou question concernant le module « Produits Phares ».
