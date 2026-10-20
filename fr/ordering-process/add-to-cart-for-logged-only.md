---
title: "Ajouter au panier pour les utilisateurs connectés uniquement - Manuel du Marchand et Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop Ajouter au panier pour les utilisateurs connectés uniquement par MyPresta.eu."
sidebar:
  label: "Ajouter au panier pour les utilisateurs connectés uniquement - Manuel du Marchand et Guide de Configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Add to cart for logged only sur MyPresta.eu](https://mypresta.eu/modules/ordering-process/add-to-cart-for-logged-only.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/ordering-process/add-to-cart-for-logged-only/)
>
> ---


# Ajouter au panier pour les utilisateurs connectés uniquement

## 1. Exigences et compatibilité

- **Versions PrestaShop prises en charge** : PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilité PHP** : PHP 5.6 - 8.5
- **Exigences d'hébergement** : Les extensions PHP standard (cURL, JSON, OpenSSL) sont généralement suffisantes. Aucune configuration de serveur spéciale n'est généralement nécessaire.

## 2. Guide de configuration complet (Chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

Après l'installation, cliquez sur « Configurer » à côté du module « Ajouter au panier pour les utilisateurs connectés uniquement » pour accéder à ses paramètres.

#### **Afficher**

- **Ce que fait ce paramètre :** C'est le commutateur principal pour activer ou désactiver la fonctionnalité principale du module.
- **Effet de la modification de ce paramètre :**
  - *Lorsqu'il est activé (Oui) :* Le module sera actif. Les utilisateurs non connectés seront empêchés d'ajouter des produits à leur panier, et un message sera affiché les invitant à se connecter.
  - *Lorsqu'il est désactivé (Non) :* Le module sera inactif. Tous les utilisateurs, qu'ils soient connectés ou non, pourront ajouter des produits à leur panier selon le comportement standard de PrestaShop.
- **Valeur recommandée :** **Oui** si vous souhaitez appliquer la règle du panier « uniquement pour les utilisateurs connectés ». **Non** si vous souhaitez désactiver temporairement la fonctionnalité sans désinstaller le module.
- **Scénario / exemple de marchand :** Si vous gérez une boutique B2B et que vous souhaitez que seuls vos clients professionnels enregistrés passent des commandes, vous définirez cette option sur « Oui ». Si vous ouvrez temporairement votre boutique à la navigation publique et aux ajouts au panier pour une promotion spéciale, vous pouvez la définir sur « Non » pendant cette période.

#### **Tableau de référence rapide de la configuration**

| Écran / Vue | Paramètre / Option | Par défaut / Recommandé | Objectif et impact |
| --- | --- | --- | --- |
| Configuration du module | Afficher | Oui | Active/désactive la fonctionnalité principale du module, restreignant « Ajouter au panier » aux utilisateurs connectés. |

## 3. Dépannage pour les marchands et questions fréquemment posées (FAQ)

**Q : J'ai activé le module, mais les utilisateurs non connectés peuvent toujours ajouter des produits au panier. Qu'est-ce qui ne va pas ?**
R :

1. **Vider le cache :** Le problème le plus courant est la mise en cache. Allez dans **Paramètres avancés > Performances** dans votre Back Office PrestaShop et cliquez sur « Vider le cache » (ou « Vider le cache Smarty » dans les versions antérieures).
2. **Position du module :** Assurez-vous que le module est correctement accroché. Bien que le module gère cela automatiquement, des conflits de thème peuvent parfois interférer. Vérifiez la configuration du module et assurez-vous qu'il est actif.
3. **Compatibilité du thème :** Très rarement, un thème fortement personnalisé peut remplacer les comportements standard des boutons de PrestaShop. Si vider le cache ne fonctionne pas, passez temporairement au thème PrestaShop par défaut (par exemple, Classic) pour voir si le problème persiste. Si cela résout le problème, votre thème est probablement à l'origine d'un conflit, et vous devrez peut-être faire appel à un développeur pour enquêter.

**Q : Puis-je personnaliser le message affiché aux utilisateurs non connectés ?**
R : Oui, le message est généralement traduisible. Allez dans **International > Traductions** dans votre Back Office. Sélectionnez « Traductions des modules installés », choisissez votre thème, puis sélectionnez « Ajouter au panier pour les utilisateurs connectés uniquement ». Vous devriez y trouver la chaîne de texte à modifier pour chaque langue.

**Q : Ce module affectera-t-il mon référencement ?**
R : Non, ce module affecte principalement la fonctionnalité du bouton « Ajouter au panier » pour les utilisateurs du front-office. Il ne bloque pas les robots des moteurs de recherche d'indexer vos pages de produits ou votre contenu. Vos produits resteront visibles et découvrables.

**Q : Que se passe-t-il si un client se déconnecte après avoir ajouté des articles au panier ?**
R : Le module empêche *d'ajouter* au panier lorsque l'utilisateur n'est pas connecté. Si un client se connecte, ajoute des articles, puis se déconnecte, les articles restent généralement dans son panier (associés à son compte) pour le moment où il se reconnectera. La restriction du module s'applique à l'action d'ajouter de nouveaux articles sans être connecté.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

Cette section fournit un aperçu technique détaillé du module « Ajouter au panier pour les utilisateurs connectés uniquement » pour les développeurs et les webmasters.

### 4.1 Aperçu de l'architecture

Le module « Ajouter au panier pour les utilisateurs connectés uniquement » est un module PrestaShop léger principalement conçu pour intercepter et modifier le comportement de l'action « Ajouter au panier » en fonction du statut de connexion de l'utilisateur. Il y parvient en tirant parti du système de hooks de PrestaShop et en injectant du JavaScript pour désactiver ou modifier le bouton « Ajouter au panier » et afficher un message pour les utilisateurs non connectés. Il n'introduit pas de nouvelles tables de base de données ou de modèles d'objets complexes, se concentrant plutôt sur l'interaction front-end et les fonctionnalités de base existantes de PrestaShop.

### 4.2 Contrôleurs (`controllers/`)

Ce module n'utilise pas de contrôleurs d'administration Front-Office ou Back-Office personnalisés. Toute la configuration est gérée dans la méthode `getContent()` du fichier principal du module.

### 4.3 Classes et modèles de base (`classes/`)

Ce module n'introduit aucune classe personnalisée et n'étend pas `ObjectModel`. Sa logique est principalement contenue dans le fichier principal `cartforlogged.php`.

### 4.4 Actifs JavaScript (`views/js/`)

- **`cartforlogged/views/js/cfl-17500.js`**

  - **Portée :** Front-office.
  - **Objectif :** Ce script est probablement conçu pour les versions PrestaShop 1.7.x et 8.x (indiqué par `17500`). Il cible le bouton « Ajouter au panier » (`#add_to_cart button`, `.add-to-cart`) et potentiellement d'autres éléments comme les champs de quantité.
  - **Fonctionnalité :**
    - Vérifie si l'utilisateur est connecté (`isLogged`).
    - Si l'utilisateur n'est pas connecté, il désactive le bouton « Ajouter au panier », modifie son texte (par exemple, en « Seuls les utilisateurs connectés… »), et ajoute potentiellement une classe CSS pour le styliser visuellement comme désactivé.
    - Il peut également empêcher la soumission de formulaires ou les appels AJAX liés à l'ajout de produits au panier.
    - Il utilise probablement `prestashop.on('updateCart', ...)` ou des écouteurs d'événements similaires pour réappliquer sa logique après les mises à jour du panier ou les changements de page (par exemple, lorsque les attributs du produit sont modifiés).
- **`cartforlogged/views/js/cfl.js`**

  - **Portée :** Front-office.
  - **Objectif :** Ce script est probablement une version plus générique ou de secours, potentiellement pour les anciennes versions de PrestaShop (1.5.x, 1.6.x) ou comme base pour le plus spécifique `cfl-17500.js`.
  - **Fonctionnalité :** Similaire à `cfl-17500.js`, il identifie le bouton « Ajouter au panier » (par exemple, `#add_to_cart button`, `.exclusive button`), vérifie le statut de connexion et désactive le bouton pour les utilisateurs non connectés. Il peut utiliser `$(document).ready()` de jQuery et la délégation d'événements pour gérer le contenu dynamique.

### 4.5 Feuilles de style CSS (`views/css/`)

- **`cartforlogged/views/css/cfl.css`**
  - **Portée :** Style client du front-office.
  - **Objectif :** Fournit un style de base pour le bouton « Ajouter au panier » désactivé ou le message affiché aux utilisateurs non connectés.
  - **Sélecteurs de classe CSS clés que les développeurs peuvent remplacer :**
    - `.cfl_disabled_button` : Probablement appliqué au bouton « Ajouter au panier » lorsqu'il est désactivé par le module. Les développeurs peuvent l'utiliser pour modifier la couleur d'arrière-plan, le curseur, l'opacité, etc., afin d'indiquer clairement qu'il est inactif.
    - `.cfl_message` : Si le module injecte un élément de message spécifique, cette classe le styliserait.

### 4.6 Structure des templates Smarty (`views/templates/`)

- **`cartforlogged/views/templates/admin/json.tpl`**
  - **Portée :** Templates d'administration.
  - **Objectif :** Ce template est probablement utilisé en interne par la méthode `getContent()` du module pour produire des données JSON, éventuellement pour des requêtes AJAX au sein de la page de configuration ou pour des mises à jour de contenu dynamique. Ce n'est pas un template visible en front-office. Il pourrait être utilisé pour renvoyer le statut de la configuration ou d'autres données au JavaScript de la page d'administration.

### 4.7 Schéma de la base de données et carte des hooks

- **Tables de base de données** : Ce module ne crée aucune table de base de données personnalisée. Il stocke ses paramètres de configuration (par exemple, `CFL_LOGIN`) dans la table standard `ps_configuration`.
- **Table des hooks enregistrés** :

| Nom du hook | Moment d'exécution | Objectif technique |
| --- | --- | --- |
| `displayHeader` | Dans la section `<head>` de chaque page du front-office. | Utilisé pour inclure les actifs CSS et JavaScript (`cfl.css`, `cfl.js`, `cfl-17500.js`) qui modifient le comportement du bouton « Ajouter au panier ». |
| `actionCartSave` | Après qu'un panier est enregistré ou mis à jour. | Ce hook pourrait potentiellement être utilisé pour réévaluer le contenu du panier ou appliquer des restrictions, mais étant donné la description du module, sa fonction principale est probablement l'injection JS front-end via `displayHeader`. Il pourrait s'agir d'un mécanisme de secours ou d'un moyen d'assurer la validation côté serveur, bien que la description du module mette l'accent sur le côté client. |
| `actionAdminControllerSetMedia` | Lorsqu'un contrôleur d'administration est chargé et que ses médias (JS/CSS) sont définis. | Utilisé pour inclure tout JavaScript ou CSS nécessaire pour la page de configuration Back Office du module. |
| `header` | Similaire à `displayHeader`, souvent utilisé de manière interchangeable ou pour des thèmes hérités spécifiques. | Utilisé pour inclure les actifs CSS et JavaScript, assurant la compatibilité entre les différentes versions et thèmes de PrestaShop. |

## 5. Support officiel et mises à jour

Pour les dernières mises à jour, corrections de bugs et support officiel du module « Ajouter au panier pour les utilisateurs connectés uniquement », veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu/my-account/orders/). Notre équipe de support est disponible pour vous aider avec tout problème ou question que vous pourriez avoir concernant la fonctionnalité et la compatibilité du module.
