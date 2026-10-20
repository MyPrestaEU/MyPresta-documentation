---
title: "Valeurs d'attributs dans le nom du produit - Manuel du Marchand & Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop 'Valeurs d'attributs dans le nom du produit' par MyPresta.eu."
sidebar:
  label: "Valeurs d'attributs dans le nom du produit - Manuel du Marchand & Guide de Configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Attribute values in product name sur MyPresta.eu](https://mypresta.eu/modules/front-office-features/attribute-values-in-product-name.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/front-office/attribute-values-in-product-name/)
>
> ---


# Valeurs d'attributs dans le nom du produit

## 1. Exigences et Compatibilité

- **Versions PrestaShop prises en charge** : PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilité PHP** : PHP 7.1 - 8.5
- **Exigences d'hébergement** : Les extensions PHP standard (cURL, JSON, OpenSSL) sont généralement suffisantes. Aucune configuration de serveur spéciale n'est nécessaire.

## 2. Parcours de configuration complet (Chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

Après avoir installé le module, cliquez sur « Configurer » pour accéder à ses paramètres.

#### Classe CSS du nom du produit

- **Ce que fait ce paramètre :** Ce champ vous permet de spécifier la classe CSS de l'élément HTML qui affiche le nom du produit sur vos pages produits. Le module a besoin de connaître cette classe pour pouvoir identifier et modifier correctement l'élément du nom du produit lorsqu'un client sélectionne une nouvelle combinaison d'attributs.
- **Effet de la modification de ce paramètre :**
  - *Lorsqu'une classe CSS correcte est saisie :* Le module localisera avec succès le nom du produit sur la page et y ajoutera dynamiquement les valeurs d'attributs sélectionnées.
  - *Lorsqu'une classe CSS incorrecte ou aucune classe CSS n'est saisie :* Le module ne pourra pas trouver l'élément du nom du produit, et par conséquent, les valeurs d'attributs ne seront pas ajoutées au nom du produit. Le nom du produit restera statique.
- **Valeur recommandée :** Cette valeur dépend de votre thème PrestaShop.
  - Pour les **thèmes par défaut de PrestaShop (Classic)**, une classe courante pour le nom du produit est `h1.product-detail-name` ou `h1[itemprop="name"]`. Vous devrez peut-être inspecter votre page produit à l'aide des outils de développement de votre navigateur pour trouver la classe ou l'ID exact de la balise `<h1>` contenant le nom du produit.
  - Si vous n'êtes pas sûr, essayez d'abord `h1.product-detail-name`. Si cela ne fonctionne pas, vous devrez consulter le développeur de votre thème ou utiliser les outils de développement du navigateur (clic droit sur le nom du produit, sélectionnez « Inspecter ») pour trouver le sélecteur CSS correct pour le titre principal du nom du produit.
- **Scénario / exemple de marchand :**
  - Vous avez installé un thème personnalisé, et le nom du produit est enveloppé dans une balise `<h2>` avec la classe `my-custom-product-title`. Vous saisiriez `h2.my-custom-product-title` dans ce champ.
  - Si votre thème utilise la structure standard du thème PrestaShop Classic, la saisie de `h1.product-detail-name` devrait fonctionner parfaitement, garantissant que lorsqu'un client sélectionne « Bleu » pour une chemise, le titre passe de « T-Shirt » à « T-Shirt (Bleu) ».

#### Autres clés de configuration (Internes)

Vous pouvez voir d'autres clés de configuration comme `PS_BO_ALLOW_EMPLOYEE_FORM_LANG`, `mypresta_updates`, `update_`, `updatev_`. Ce sont des paramètres internes utilisés par PrestaShop et MyPresta.eu pour gérer les mises à jour des modules et les préférences linguistiques. Vous n'avez pas besoin d'interagir avec ceux-ci.

### 2.2 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Valeur par défaut / Recommandée | Objectif et impact |
| --- | --- | --- | --- |
| Page de configuration du module | Classe CSS du nom du produit | `h1.product-detail-name` (pour le thème Classic) | Spécifie le sélecteur CSS pour l'élément du nom du produit. Essentiel pour que le module identifie et modifie le titre du produit sur la page produit. |

## 3. Dépannage pour les marchands et questions fréquemment posées (FAQ)

**Q : Le nom du produit ne change pas lorsque je sélectionne des attributs. Qu'est-ce qui ne va pas ?**
R : La raison la plus courante est un paramètre « Classe CSS du nom du produit » incorrect.
- **Solution** :
1. Accédez à votre page produit dans votre navigateur.
2. Faites un clic droit sur le nom du produit et sélectionnez « Inspecter » (ou « Inspecter l'élément »).
3. Recherchez la balise `<h1>` ou `<h2>` qui contient le nom du produit. Notez sa classe (par exemple, `class="product-detail-name"`) ou son ID (par exemple, `id="product_name"`).
4. Saisissez le sélecteur CSS correct dans la configuration du module. Par exemple, si la balise est `<h1 class="my-product-title">`, vous saisiriez `h1.my-product-title`. Si c'est `<h2 id="product_heading">`, vous saisiriez `h2#product_heading`.
5. Enregistrez la configuration du module et videz votre cache PrestaShop (Paramètres avancés > Performances > Vider le cache).

**Q : Le module a fonctionné initialement, mais après la mise à jour de mon thème, il a cessé de fonctionner.**
R : Les mises à jour de thème modifient souvent la structure HTML et les classes CSS.
- **Solution** : Vérifiez à nouveau le paramètre « Classe CSS du nom du produit » comme décrit ci-dessus. Votre nouveau thème pourrait utiliser une classe ou un ID différent pour le nom du produit.

**Q : Ce module affectera-t-il mon SEO ?**
R : Non, ce module ne modifie le nom du produit dynamiquement que côté client (dans le navigateur du client) à l'aide de JavaScript. Il n'altère pas le nom original du produit stocké dans votre base de données ni la balise `<h1>` que les moteurs de recherche indexent généralement. Votre SEO reste inchangé.

**Q : Ce module prend-il en charge plusieurs langues ?**
R : Oui, le module fonctionne avec les valeurs d'attributs telles qu'elles sont configurées dans votre back office PrestaShop, qui sont déjà compatibles multilingues. Le module ajoute simplement les valeurs d'attributs actuellement sélectionnées dans la langue active au nom du produit.

**Q : Je vois les valeurs d'attributs, mais elles sont mal stylisées (par exemple, mauvaise police, couleur).**
R : Le module ajoute du texte à un élément HTML existant. Son style héritera du CSS de votre thème pour cet élément du nom du produit.
- **Solution** : Si vous souhaitez styliser différemment les valeurs d'attributs ajoutées, vous aurez besoin d'un CSS personnalisé. Vous pouvez cibler l'élément du nom du produit et potentiellement utiliser des pseudo-éléments ou des sélecteurs spécifiques si le module enveloppe le texte ajouté dans un `<span>` unique (bien que ce module ajoute généralement simplement du texte). Un développeur web peut vous aider avec un CSS personnalisé.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

Cette section fournit un aperçu technique détaillé pour les développeurs, les webmasters et les agences.

### 4.1 Vue d'ensemble de l'architecture

Le module « Valeurs d'attributs dans le nom du produit » (`anpn`) est un module PrestaShop léger principalement axé sur la manipulation côté client en front-office. Il exploite le système de hooks de PrestaShop pour injecter son JavaScript dans l'en-tête de la page produit. La logique principale réside dans un seul fichier JavaScript qui écoute les changements dans les sélections d'attributs de produit et met à jour dynamiquement le contenu textuel du nom du produit. Il n'introduit pas de nouvelles tables de base de données ni de logique complexe côté serveur au-delà de sa configuration.

### 4.2 Contrôleurs (`controllers/`)

- **Contrôleurs Front-Office** : Aucun. Toutes les fonctionnalités front-office sont gérées via JavaScript injecté par des hooks.
- **Contrôleurs Admin Back-Office** : Aucun. La configuration est gérée directement dans la méthode `getContent()` du fichier principal du module.

### 4.3 Classes et modèles principaux (`classes/`)

- Aucune classe personnalisée ou instance `ObjectModel` n'est définie. Le module fonctionne directement sur les valeurs de configuration et la manipulation du DOM en front-office.

### 4.4 Actifs JavaScript (`views/js/`)

- **`anpn/views/js/anpn.js`**
  - **Portée** : Front-office (page produit).
  - **Objectif** : Ce script est responsable de la mise à jour dynamique du nom du produit.
  - **Fonctionnalité** :
    1. **DOM Ready / `prestashop.on`** : Il attend que le DOM soit entièrement chargé et écoute spécifiquement l'événement `updatedProduct` déclenché par le JavaScript principal de PrestaShop lorsqu'une combinaison de produit est modifiée (par exemple, en sélectionnant une taille ou une couleur différente).
    2. **Identification du nom du produit** : Il récupère le sélecteur CSS pour le nom du produit à partir de la configuration du module (passé via la variable globale `anpn_pn_class` ou un mécanisme similaire). Il utilise ensuite ce sélecteur pour trouver l'élément HTML cible sur la page.
    3. **Extraction des valeurs d'attributs** : Lorsque `updatedProduct` est déclenché, il accède aux données de la combinaison de produit actuelle (qui incluent les valeurs d'attributs sélectionnées) à partir de la charge utile de l'événement.
    4. **Mise à jour dynamique** : Il construit une chaîne des valeurs d'attributs sélectionnées (par exemple, « (M, Bleu) ») et l'ajoute au nom du produit original (qu'il stocke généralement lors du chargement initial ou récupère à partir d'un attribut de données).
    5. **Manipulation du DOM** : Le script met à jour le `textContent` ou `innerText` de l'élément du nom du produit identifié avec la nouvelle chaîne combinée.
  - **Dépendances** : Repose sur jQuery (si PrestaShop 1.7.x) ou les API DOM natives, et le système d'événements `prestashop.on` de PrestaShop.

### 4.5 Feuilles de style CSS (`views/css/`)

- Aucun fichier CSS personnalisé n'est fourni par le module. Les valeurs d'attributs ajoutées héritent du style de l'élément de nom de produit existant dans le thème.

### 4.6 Structure du template Smarty (`views/templates/`)

- Aucun fichier de template personnalisé n'est fourni par le module. Toute la sortie est gérée par le fichier principal du module (`anpn.php`) pour la configuration, et JavaScript pour l'affichage en front-office.

### 4.7 Schéma de la base de données et carte des hooks

- **Tables de base de données** :
  - Le module ne crée aucune table de base de données personnalisée.
  - Il stocke ses paramètres de configuration dans la table `ps_configuration` :
    - `ANPN_PN_CLASS` : Stocke la classe/sélecteur CSS pour l'élément du nom du produit.
- **Table des hooks enregistrés** :

  | Nom du hook | Moment d'exécution | Objectif technique |
  | --- | --- | --- |
  | `displayHeader` | Dans la section `<head>` de chaque page front-office. | Utilisé pour enregistrer le JavaScript du module (`anpn.js`) et transmettre la valeur de configuration `ANPN_PN_CLASS` au script front-end. |
  | `displayProductAdditionalInfo` | Sur la page produit, généralement sous les informations principales du produit. | Bien que non explicitement utilisé pour la sortie visuelle dans ce module, c'est un hook courant pour les modules afin d'injecter du contenu ou des scripts sur la page produit. Dans le contexte de ce module, il pourrait être utilisé pour s'assurer que le JS est chargé au bon moment, ou il pourrait s'agir d'un enregistrement de hook hérité. L'interaction principale se fait via `displayHeader` et l'événement `updatedProduct`. |

## 5. Support officiel et mises à jour

Pour les dernières mises à jour, corrections de bugs et support officiel du module « Valeurs d'attributs dans le nom du produit », veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu/my-account/orders/). Notre équipe de support est disponible pour vous aider avec toutes les questions ou problèmes que vous pourriez rencontrer.
