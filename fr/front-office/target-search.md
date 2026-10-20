---
title: "Recherche ciblée - Manuel du marchand et guide de configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop de recherche ciblée par MyPresta.eu."
sidebar:
  label: "Recherche ciblée - Manuel du marchand et guide de configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Target search sur MyPresta.eu](https://mypresta.eu/modules/front-office-features/target-search.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/front-office/target-search/)
>
> ---


# Recherche ciblée

## 1. Exigences et compatibilité

- **Versions PrestaShop prises en charge :** PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilité PHP :** PHP 5.6 - 8.5
- **Exigences d'hébergement :** Les extensions PHP standard (cURL, JSON, OpenSSL) sont généralement suffisantes. Aucune configuration de serveur inhabituelle n'est requise.

## 2. Parcours de configuration complet (chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

Après l'installation, cliquez sur « Configurer » à côté du module « Recherche ciblée » pour accéder à ses paramètres. C'est ici que vous définissez exactement où le moteur de recherche doit rechercher les mots-clés.

La page de configuration présentera une série de cases à cocher, chacune correspondant à une zone spécifique de vos données produit.

- **Ce que fait ce paramètre :** Chaque case à cocher vous permet d'activer ou de désactiver la recherche dans un champ particulier de vos informations produit.
- **Effet de la modification de ce paramètre :**
  - *Lorsque coché (activé) :* Le moteur de recherche PrestaShop inclura les données de ce champ spécifique lors du traitement des requêtes client. Par exemple, si « Nom du produit » est coché, une recherche de « robe » trouvera les produits avec « robe » dans leur nom.
  - *Lorsque décoché (désactivé) :* Le moteur de recherche PrestaShop *ignorera* les données de ce champ. Si « Description du produit » est décoché, un produit n'apparaîtra pas dans les résultats de recherche si le terme de recherche n'est trouvé que dans sa description.
- **Valeur recommandée :** Cela dépend entièrement de votre catalogue de produits et de la manière dont vous souhaitez que les clients trouvent les produits. Un bon point de départ est d'activer les champs les plus critiques, puis d'affiner en fonction des tests.
- **Scénario / exemple de marchand :**
  - **Scénario 1 : Produits très spécifiques (par exemple, pièces électroniques, livres par ISBN) :** Vous ne voudrez peut-être rechercher que dans « Nom du produit », « Référence » et « EAN13/JAN ». Cela garantit que les clients trouvent des correspondances exactes rapidement, évitant les résultats non pertinents provenant de longues descriptions.
  - **Scénario 2 : Articles de mode ou pour la maison (par exemple, « robe rouge ») :** Vous pouvez activer « Nom du produit », « Description courte », « Description longue » et « Balises ». Cela permet aux clients de trouver des produits en fonction de termes plus larges, de couleurs ou de styles mentionnés n'importe où dans les détails du produit.
  - **Scénario 3 : Produits de marque :** Activez « Nom du fabricant » afin que les clients puissent facilement trouver tous les produits d'une marque spécifique en tapant le nom de la marque dans la barre de recherche.

Voici une ventilation des paramètres typiques que vous trouverez :

| Paramètre / Option | Objectif et impact | Valeur recommandée | Scénario marchand |
| --- | --- | --- | --- |
| **Rechercher dans le nom du produit** | Si activé, les requêtes de recherche correspondront au nom du produit. | **OUI** | Essentiel pour la plupart des boutiques. Les clients recherchent souvent par nom de produit. |
| **Rechercher dans la description courte du produit** | Si activé, les requêtes de recherche correspondront à la description courte du produit. | **OUI** | Utile pour trouver des produits basés sur des caractéristiques clés ou des résumés. |
| **Rechercher dans la description longue du produit** | Si activé, les requêtes de recherche correspondront à la description complète et détaillée du produit. | **OUI / NON** | **OUI** pour les recherches larges (mode, articles pour la maison). **NON** pour les articles très spécifiques (électronique, pièces) afin d'éviter le bruit. |
| **Rechercher dans la référence du produit** | Si activé, les requêtes de recherche correspondront au numéro de référence interne du produit. | **OUI / NON** | **OUI** pour le B2B, les produits techniques, ou si les clients connaissent les numéros de pièce. **NON** si les références sont uniquement internes. |
| **Rechercher dans le produit EAN13/JAN** | Si activé, les requêtes de recherche correspondront au code-barres EAN13 ou JAN du produit. | **OUI / NON** | **OUI** pour les boutiques où les clients pourraient rechercher par code-barres (par exemple, livres, épicerie). |
| **Rechercher dans le produit UPC** | Si activé, les requêtes de recherche correspondront au code-barres UPC du produit. | **OUI / NON** | Similaire à EAN13/JAN, pour les régions utilisant l'UPC. |
| **Rechercher dans les balises du produit** | Si activé, les requêtes de recherche correspondront à toutes les balises attribuées au produit. | **OUI** | Excellent pour améliorer la découvrabilité avec des mots-clés non présents dans les noms/descriptions. |
| **Rechercher dans le nom du fabricant** | Si activé, les requêtes de recherche correspondront au nom du fabricant du produit. | **OUI** | Crucial si les clients recherchent souvent des marques spécifiques. |
| **Rechercher dans le nom du fournisseur** | Si activé, les requêtes de recherche correspondront au nom du fournisseur du produit. | **NON / OUI** | **NON** pour la plupart des boutiques B2C. **OUI** pour le B2B ou les boutiques spécialisées où le fournisseur est pertinent pour les clients. |
| **Rechercher dans le nom de la catégorie** | Si activé, les requêtes de recherche correspondront au nom des catégories auxquelles le produit appartient. | **OUI** | Aide les clients à trouver des produits par nom de catégorie (par exemple, « robes » pour trouver des produits dans la catégorie « Robes »). |
| **Rechercher dans la valeur de la caractéristique** | Si activé, les requêtes de recherche correspondront aux valeurs des caractéristiques du produit (par exemple, « rouge » pour une caractéristique « Couleur »). | **OUI** | Fortement recommandé pour les boutiques avec des caractéristiques de produit riches (par exemple, couleur, taille, matériau). |

**Note importante :** Après avoir apporté des modifications à ces paramètres, cliquez toujours sur le bouton « Enregistrer ». Il est également recommandé de vider votre cache PrestaShop (Paramètres avancés > Performances) et de tester la fonctionnalité de recherche sur votre front office pour vous assurer que les modifications ont pris effet comme prévu.

### 2.2 Écrans d'administration dédiés et vues de contrôleur

Ce module n'introduit aucun nouvel écran d'administration dédié ni contrôleur personnalisé. Toute la configuration est gérée directement via la page de configuration standard du module.

### 2.3 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Par défaut / Recommandé | Objectif et impact |
| --- | --- | --- | --- |
| Page de configuration du module | Rechercher dans le nom du produit | OUI | Inclure les noms de produits dans la recherche. |
| Page de configuration du module | Rechercher dans la description courte du produit | OUI | Inclure les descriptions courtes dans la recherche. |
| Page de configuration du module | Rechercher dans la description longue du produit | OUI / NON | Inclure les descriptions complètes. |
| Page de configuration du module | Rechercher dans la référence du produit | OUI / NON | Inclure les numéros de référence des produits. |
| Page de configuration du module | Rechercher dans le produit EAN13/JAN | OUI / NON | Inclure les codes-barres EAN13/JAN. |
| Page de configuration du module | Rechercher dans le produit UPC | OUI / NON | Inclure les codes-barres UPC. |
| Page de configuration du module | Rechercher dans les balises du produit | OUI | Inclure les balises de produit. |
| Page de configuration du module | Rechercher dans le nom du fabricant | OUI | Inclure les noms de fabricants. |
| Page de configuration du module | Rechercher dans le nom du fournisseur | NON / OUI | Inclure les noms de fournisseurs. |
| Page de configuration du module | Rechercher dans le nom de la catégorie | OUI | Inclure les noms de catégories. |
| Page de configuration du module | Rechercher dans la valeur de la caractéristique | OUI | Inclure les valeurs des caractéristiques du produit. |

## 3. Dépannage marchand et questions fréquemment posées (FAQ)

**Q1 : J'ai modifié les paramètres, mais les résultats de recherche n'ont pas changé. Qu'est-ce qui ne va pas ?**
R : PrestaShop utilise la mise en cache pour accélérer votre boutique. Après avoir modifié les paramètres du module, vous devez souvent vider le cache.

- **Solution :** Allez dans **Paramètres avancés > Performances** dans votre Back Office PrestaShop. Cliquez sur « Vider le cache » (ou « Vider le cache Smarty » dans les versions antérieures). Ensuite, testez à nouveau votre recherche.

**Q2 : La barre de recherche de mon thème personnalisé a un aspect différent. Ce module fonctionnera-t-il toujours ?**
R : Oui, le module « Recherche ciblée » remplace principalement la *logique* de la façon dont PrestaShop traite les requêtes de recherche, et non l'apparence visuelle de la barre de recherche elle-même. Il devrait fonctionner de manière transparente avec la plupart des thèmes personnalisés.

- **Solution :** Si vous rencontrez des problèmes visuels inattendus ou si la recherche ne semble pas fonctionner, il peut s'agir d'un rare conflit avec le modèle de recherche personnalisé de votre thème. Contactez le support MyPresta.eu avec les détails de votre thème.

**Q3 : Ce module affecte-t-il l'optimisation pour les moteurs de recherche (SEO) ?**
R : Directement, non. Ce module améliore l'expérience de recherche *interne* pour vos clients sur votre site web. Il n'a pas d'impact direct sur la façon dont les moteurs de recherche externes (comme Google) explorent ou classent votre site. Cependant, en améliorant l'expérience de recherche sur le site, vous pouvez réduire les taux de rebond et augmenter le temps passé sur le site, ce qui sont des signaux positifs pour le SEO.

**Q4 : Puis-je traduire les paramètres ou les messages du module ?**
R : Le module « Recherche ciblée » fonctionne principalement en arrière-plan et n'introduit pas de nouveau texte front-office nécessitant une traduction. Les options de configuration dans le back office sont généralement en anglais. Si un nouveau texte était introduit, vous le traduiriez via **International > Traductions** dans votre Back Office PrestaShop, en sélectionnant « Traductions des modules installés » puis le module « Recherche ciblée ».

**Q5 : Que faire si je veux rechercher dans un champ non listé dans les paramètres du module ?**
R : Le module propose des options pour les champs de produit les plus courants et les plus impactants. Si vous avez un champ personnalisé très spécifique que vous devez inclure dans la recherche, cela nécessiterait un développement personnalisé.

- **Solution :** Contactez le support MyPresta.eu ou un développeur PrestaShop pour discuter des modifications personnalisées.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

Cette section est strictement destinée aux développeurs, aux webmasters de boutique et aux agences techniques qui maintiennent ou étendent la boutique.

### 4.1 Aperçu de l'architecture

Le module « Recherche ciblée » fonctionne principalement en surchargeant la classe `Search` de base de PrestaShop. Cela lui permet d'intercepter et de modifier la logique de requête de recherche par défaut avant qu'elle n'atteigne la base de données. Le module utilise le système de surcharge de PrestaShop pour injecter ses paramètres de recherche personnalisés basés sur la configuration du marchand. C'est un module léger, qui se concentre sur la modification du comportement de base existant plutôt que sur l'introduction de nouvelles entités ou contrôleurs complexes.

### 4.2 Contrôleurs (`controllers/`)

Ce module n'introduit aucun contrôleur d'administration Front-Office ou Back-Office personnalisé. Sa fonctionnalité est intégrée en surchargeant une classe de base et via la méthode `getContent()` standard du module pour la configuration.

### 4.3 Classes et modèles de base (`classes/`)

Le cœur de la fonctionnalité de ce module réside dans sa surcharge de la classe `Search`.

- **`targetsearch/override/classes/index.php`** :

  - Il s'agit d'un fichier `index.php` vide standard, généralement placé dans les répertoires pour empêcher l'affichage du contenu du répertoire pour des raisons de sécurité. Il ne contient aucun code fonctionnel.
- **`targetsearch/override/classes/Search.php`** :

  - **Nom de la classe** : `Search` (surcharge la classe de base `classes/Search.php`)
  - **Classe parente** : `SearchCore`
  - **Responsabilité** : Cette classe est responsable de la modification de la méthode `search` de la classe `Search` de base. Elle lit les paramètres de configuration stockés dans `ps_configuration` (par exemple, `TARGETSEARCH_PRODUCT_NAME`, `TARGETSEARCH_DESCRIPTION`, etc.) et ajuste dynamiquement la requête SQL utilisée pour la recherche de produits.
  - **Méthodes publiques clés** :
    - `search($id_lang, $expr, $page_number = 1, $page_size = 10, $order_by = 'position', $order_way = 'desc', $ajax = false, $use_cookie = true, Context $context = null)` : Cette méthode est surchargée pour injecter les conditions de recherche personnalisées. Elle construit la clause `WHERE` de la requête SQL en fonction des cibles de recherche activées. Elle vérifie `Configuration::get('TARGETSEARCH_...')` pour chaque cible (nom du produit, description, référence, EAN13, UPC, balises, fabricant, fournisseur, catégorie, valeur de la caractéristique) et ajoute les conditions `LIKE` correspondantes à la requête.
  - **Interaction avec la base de données** : Elle n'interagit pas avec des tables de base de données personnalisées. Elle modifie la requête qui interagit avec les tables standard de PrestaShop pour les produits, catégories, fabricants, fournisseurs et caractéristiques.
  - **`$definition`** : Non applicable car elle surcharge une classe de base et ne définit pas de nouveau `ObjectModel`.

### 4.4 Actifs JavaScript (`views/js/`)

- **`targetsearch/targetsearch.js`** :
  - **Portée** : Back-office (potentiellement, mais généralement non utilisé pour la logique de recherche front-office).
  - **Objectif** : Ce fichier est généralement vide ou contient un JavaScript minimal, souvent pour des interactions UI de base sur la page de configuration du module si une logique client-side avancée était nécessaire. Étant donné que la fonction principale du module est la logique de recherche côté serveur, ce fichier est peu susceptible de contenir un JS complexe lié à la recherche front-office. Il pourrait s'agir d'un espace réservé ou d'améliorations mineures de formulaire back-office.
  - **Écouteurs d'événements/Manipulation du DOM** : Peu susceptible de contenir des écouteurs d'événements front-office ou une manipulation du DOM significatifs liés à la recherche. Son rôle principal serait pour la page de configuration du module dans le back office.

### 4.5 Feuilles de style CSS (`views/css/`)

- **`targetsearch/targetsearch.css`** :

  - **Portée** : Back-office.
  - **Objectif** : Cette feuille de style est généralement utilisée pour styliser la page de configuration du module dans le Back Office de PrestaShop, garantissant qu'elle est cohérente avec le thème d'administration. Elle peut contenir des styles pour les éléments de formulaire, les alertes ou des ajustements de mise en page spécifiques pour les paramètres du module.
  - **Sélecteurs de classe CSS clés** : Cible probablement les classes d'administration PrestaShop standard ou des ID/classes spécifiques dans la sortie de `getContent()` du module.
- **`targetsearch/targetsearch15.css`** :

  - **Portée** : Back-office (spécifiquement pour PrestaShop 1.5.x).
  - **Objectif** : Ce fichier fournit des ajustements de style spécifiques pour la page de configuration du module lors de l'exécution sur PrestaShop 1.5.x, tenant compte des différences dans la structure et le CSS du thème d'administration.
  - **Sélecteurs de classe CSS clés** : Similaire à `targetsearch.css` mais adapté à l'environnement d'administration de PS 1.5.

### 4.6 Structure des modèles Smarty (`views/templates/`)

- **`targetsearch/targetsearch-top.tpl`** :
  - **Portée** : Front-office.
  - **Hook** : Ce modèle est probablement conçu pour être accroché à `displayHeader` ou `displayTop` (ou des hooks similaires qui affichent du contenu dans la zone d'en-tête).
  - **Objectif** : Bien que la fonction principale du module soit la logique de recherche, ce modèle pourrait être utilisé pour afficher un champ de saisie caché, un petit script ou un élément visuel spécifique lié à la présence du module, bien que ce ne soit pas strictement nécessaire pour la surcharge de recherche elle-même. Compte tenu de la description du module, il est plus probable que ce modèle soit un espace réservé ou pour un composant visuel très mineur et non critique, car l'impact principal du module est sur les *résultats* de recherche, et non sur l'*entrée* de recherche. Il pourrait également s'agir d'un vestige d'une version antérieure ou d'un modèle destiné à une fonctionnalité future.

### 4.7 Schéma de base de données et carte des hooks

- **Tables de base de données** :

  - Le module ne crée aucune table de base de données personnalisée.
  - Il stocke ses paramètres de configuration dans la table standard `ps_configuration` de PrestaShop.
    - Clés : `TARGETSEARCH_PRODUCT_NAME`, `TARGETSEARCH_DESCRIPTION`, `TARGETSEARCH_SHORT_DESCRIPTION`, `TARGETSEARCH_REFERENCE`, `TARGETSEARCH_EAN13`, `TARGETSEARCH_UPC`, `TARGETSEARCH_TAGS`, `TARGETSEARCH_MANUFACTURER`, `TARGETSEARCH_SUPPLIER`, `TARGETSEARCH_CATEGORY`, `TARGETSEARCH_FEATURE_VALUE`.
    - Valeurs : `1` (activé) ou `0` (désactivé).
- **Table des hooks enregistrés** :
  Le module enregistre des hooks standard principalement pour son installation et sa désinstallation, et potentiellement pour l'affichage de sa configuration. Sa fonctionnalité principale est via la surcharge de classe, et non directement via des hooks.

| Nom du hook | Moment d'exécution | Objectif technique |
| --- | --- | --- |
| `install` | Lors de l'installation du module. | Crée des entrées de configuration dans `ps_configuration` avec des valeurs par défaut. |
| `uninstall` | Lors de la désinstallation du module. | Supprime les entrées de configuration de `ps_configuration`. |
| `displayHeader` (ou similaire) | Affiche le contenu dans la section `<head>` ou en haut de la page. | Potentiellement utilisé pour inclure `targetsearch.js` ou `targetsearch.css` s'ils contiennent des actifs front-office, ou pour afficher `targetsearch-top.tpl`. |
| `displayBackOfficeHeader` | Affiche le contenu dans la section `<head>` du Back Office. | Utilisé pour inclure `targetsearch.css` (et `targetsearch15.css` conditionnellement) pour styliser la page de configuration du module. |

## 5. Support officiel et mises à jour

Pour les mises à jour officielles, le support technique et toute assistance supplémentaire concernant le module « Recherche ciblée », veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu/my-account/orders/). Notre équipe de support est disponible pour vous aider avec toutes les questions ou problèmes que vous pourriez avoir.
