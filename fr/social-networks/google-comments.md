---
title: "Commentaires Google+ - Manuel du Marchand et Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop Commentaires Google+ par MyPresta.eu."
sidebar:
  label: "Commentaires Google+ - Manuel du Marchand et Guide de Configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Google+ Comments sur MyPresta.eu](https://mypresta.eu/modules/social-networks/google-comments.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/social-networks/google-comments/)
>
> ---


# Commentaires Google+

## 1. Exigences et Compatibilité

- **Versions PrestaShop prises en charge** : PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilité PHP** : PHP 7.1 - 8.5
- **Exigences d'hébergement** : Extensions PHP standard (cURL, JSON, OpenSSL).

## 2. Parcours de configuration complet (Chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

Ceci est l'écran de configuration principal du module Commentaires Google+. Vous y trouverez tous les paramètres pour contrôler l'apparence et le fonctionnement des commentaires sur votre boutique.

**Accès :** Naviguez vers **Modules > Gestionnaire de modules**, recherchez « Commentaires Google+ », et cliquez sur **« Configurer »**.

#### Paramètres et Options

1. **Afficher les commentaires Google+ sur la page produit**

   - **Ce que fait ce paramètre :** Ce commutateur contrôle si la section de commentaires Google+ est affichée sur vos pages produits.
   - **Effet de la modification de ce paramètre :**
     - *Lorsque activé (OUI) :* La section de commentaires Google+ apparaîtra sur toutes vos pages produits, permettant aux clients de visualiser et d'ajouter des commentaires.
     - *Lorsque désactivé (NON) :* La section de commentaires Google+ sera masquée de toutes les pages produits.
   - **Valeur recommandée :** OUI (si vous souhaitez utiliser la fonction de commentaires).
   - **Scénario / exemple de marchand :** Si vous souhaitez encourager l'interaction client et exploiter le contenu généré par l'utilisateur, activez ceci. Si vous préférez un système de commentaires différent ou pas de commentaires du tout, désactivez-le.
2. **Choisir le Hook pour les commentaires Google+**

   - **Ce que fait ce paramètre :** Ce menu déroulant vous permet de sélectionner l'emplacement sur la page produit (ou d'autres pages) où le bloc de commentaires Google+ sera affiché. Les hooks sont des emplacements spécifiques dans votre thème PrestaShop où les modules peuvent injecter du contenu.
   - **Effet de la modification de ce paramètre :**
     - *Sélectionner `displayProductExtraContent` (ou un hook similaire de page produit) :* Les commentaires apparaîtront dans la zone de contenu principale de la page produit, généralement sous la description du produit ou les onglets. C'est l'emplacement le plus courant et recommandé.
     - *Sélectionner `displayLeftColumn` ou `displayRightColumn` :* Le bloc de commentaires apparaîtra dans la barre latérale gauche ou droite de votre boutique (si votre thème en a et qu'elles sont actives sur les pages produits). Ce n'est généralement pas idéal pour une section de commentaires complète.
     - *Sélectionner `displayFooter` :* Le bloc de commentaires apparaîtra dans la section du pied de page de votre boutique. Encore une fois, pas idéal pour les commentaires spécifiques aux produits.
   - **Valeur recommandée :** `displayProductExtraContent` ou un hook similaire qui place les commentaires directement dans la zone de contenu de la page produit. Le nom exact du hook peut varier légèrement entre les versions de PrestaShop ou les thèmes, mais visez-en un qui s'intègre bien aux détails du produit.
   - **Scénario / exemple de marchand :** Vous souhaitez que les commentaires soient facilement visibles lorsqu'un client examine un produit. Choisir `displayProductExtraContent` garantit qu'il fait partie du flux d'informations principal du produit.
3. **Largeur du bloc de commentaires Google+ (en pixels)**

   - **Ce que fait ce paramètre :** Ce champ de saisie vous permet de définir la largeur fixe de la section de commentaires Google+ en pixels.
   - **Effet de la modification de ce paramètre :**
     - *Définir une valeur en pixels spécifique (par exemple, `600`) :* Le bloc de commentaires tentera toujours de s'afficher à cette largeur exacte. Si l'écran est plus petit, il pourrait déborder ou causer des problèmes de mise en page.
     - *Laisser vide ou définir à `100%` (si autorisé par le module, bien qu'il attende généralement des pixels) :* Le module pourrait essayer de s'ajuster automatiquement, mais pour les commentaires Google+, une largeur fixe en pixels est souvent attendue.
   - **Valeur recommandée :** Une valeur qui s'intègre bien dans la zone de contenu principale de votre page produit, généralement de `600` à `800` pixels, selon la mise en page de votre thème. Vous devrez peut-être expérimenter pour trouver le meilleur ajustement.
   - **Scénario / exemple de marchand :** La zone de contenu de votre page produit a une largeur de 700px. Définir ceci à `650`px garantit que le bloc de commentaires s'intègre parfaitement sans casser la mise en page.
4. **Nombre de commentaires à afficher**

   - **Ce que fait ce paramètre :** Ce champ de saisie contrôle le nombre de commentaires initialement chargés et affichés dans la section de commentaires Google+. Plus de commentaires peuvent généralement être chargés par l'utilisateur en cliquant sur un bouton « Charger plus » fourni par Google.
   - **Effet de la modification de ce paramètre :**
     - *Définir un nombre faible (par exemple, `5`) :* Seuls quelques commentaires s'afficheront initialement, ce qui rendra le chargement de la page plus rapide et moins encombré. Les utilisateurs devront cliquer pour en voir plus.
     - *Définir un nombre élevé (par exemple, `20`) :* Plus de commentaires seront immédiatement visibles, ce qui peut être bon pour les produits très commentés mais pourrait rendre la page plus longue.
   - **Valeur recommandée :** `5` à `10`. Cela offre un bon équilibre entre l'affichage de l'engagement et la concision de la page.
   - **Scénario / exemple de marchand :** Vous avez de nombreux commentaires sur des produits populaires. Définir ceci à `7` montre suffisamment d'engagement sans submerger le client avec un très long défilement.

#### Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Par défaut / Recommandé | Objectif et Impact |
| --- | --- | --- | --- |
| Configuration du module | Afficher les commentaires Google+ sur la page produit | OUI | Active/désactive la section de commentaires sur les pages produits. |
| Configuration du module | Choisir le Hook pour les commentaires Google+ | `displayProductExtraContent` | Détermine où le bloc de commentaires apparaît sur la page. |
| Configuration du module | Largeur du bloc de commentaires Google+ (en pixels) | `600` - `800` | Définit la largeur fixe de la section de commentaires. Ajustez pour s'adapter à votre thème. |
| Configuration du module | Nombre de commentaires à afficher | `5` - `10` | Contrôle le nombre de commentaires initialement visibles. |

## 3. Dépannage pour les marchands et questions fréquemment posées (FAQ)

**Q : La section des commentaires n'apparaît pas sur mes pages produits après l'installation.**
R :

1. **Vérifiez la configuration du module :** Allez dans **Modules > Gestionnaire de modules > Commentaires Google+ > Configurer**. Assurez-vous que « Afficher les commentaires Google+ sur la page produit » est réglé sur OUI.
2. **Vérifiez la sélection du hook :** Assurez-vous que « Choisir le Hook pour les commentaires Google+ » est défini sur un hook de page produit pertinent comme `displayProductExtraContent`. Si votre thème utilise un hook personnalisé pour le contenu du produit, vous devrez peut-être le sélectionner ou consulter votre développeur de thème.
3. **Videz le cache :** Allez dans **Paramètres avancés > Performances** et cliquez sur « Vider le cache » (ou « Vider le cache Smarty »). Parfois, le cache de PrestaShop empêche le nouveau contenu du module d'apparaître immédiatement.
4. **Compatibilité du thème :** Certains thèmes très personnalisés peuvent remplacer les hooks PrestaShop standard. Si le problème persiste, contactez votre développeur de thème ou le support MyPresta.eu.

**Q : La section des commentaires semble trop large/étroite ou casse ma mise en page.**
R :

1. **Ajustez le paramètre de largeur :** Dans la configuration du module, modifiez le paramètre « Largeur du bloc de commentaires Google+ (en pixels) ». Expérimentez avec différentes valeurs (par exemple, 600, 700, 800) jusqu'à ce qu'il s'adapte à la mise en page de votre page produit.
2. **Vérifiez le CSS du thème :** Si l'ajustement de la largeur ne résout pas le problème, le CSS de votre thème pourrait interférer. Vous devrez peut-être demander à un webmaster d'inspecter l'élément et d'ajouter du CSS personnalisé à votre thème pour assurer un affichage correct.

**Q : Puis-je modérer les commentaires avant qu'ils n'apparaissent ?**
R : Le module Commentaires Google+ utilise le propre système de commentaires de Google. Les capacités de modération sont généralement gérées au sein de la plateforme Google elle-même, et non directement dans PrestaShop. Vous devrez vérifier les politiques et les outils de Google pour la modération des commentaires liés aux widgets intégrés.

**Q : Mes clients ont du mal à publier des commentaires.**
R :

1. **Exigence de compte Google :** Rappelez aux clients qu'ils doivent être connectés à un compte Google pour publier des commentaires.
2. **Problèmes de navigateur :** Conseillez aux clients d'essayer un autre navigateur ou de vider le cache et les cookies de leur navigateur.
3. **État du service Google :** Occasionnellement, les services Google peuvent subir des pannes temporaires. Vérifiez les pages d'état de Google si de nombreux utilisateurs signalent des problèmes simultanément.

**Q : Ce module fonctionne-t-il toujours depuis la fermeture de Google+ ?**
R : Bien que Google+ en tant que réseau social ait été déprécié, Google fournit toujours des widgets de commentaires intégrés qui exploitent les comptes Google. Ce module s'intègre à cette infrastructure de commentaires Google sous-jacente. Il ne fournit peut-être plus le « coup de pouce SEO » direct des « +1 » comme il le faisait autrefois, mais il fonctionne toujours comme un système de commentaires alimenté par Google.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

Cette section fournit un aperçu technique pour les développeurs et les webmasters travaillant avec le module Commentaires Google+.

### 4.1 Aperçu de l'architecture

Le module `Commentaires Google+` est un module PrestaShop simple principalement implémenté dans son fichier PHP principal (`google-comments.php`). Il utilise la classe `Module` et la classe `Configuration` de PrestaShop pour gérer les paramètres. Sa fonctionnalité principale consiste à injecter un extrait JavaScript fourni par Google dans le front-office, qui affiche ensuite le widget de commentaires. Il n'y a pas de contrôleurs, de modèles ou d'interactions AJAX complexes personnalisés au sein du module lui-même ; il repose fortement sur le script externe de Google pour sa fonctionnalité front-end.

### 4.2 Contrôleurs (`controllers/`)

- **Contrôleurs Front-Office** : Aucun. L'affichage front-office du module est géré en se connectant aux hooks d'affichage PrestaShop standard et en rendant un template Smarty contenant le code d'intégration des commentaires Google.
- **Contrôleurs d'administration Back-Office** : Aucun. Toute la configuration est gérée via la méthode `getContent()` dans le fichier principal du module.

### 4.3 Classes et modèles de base (`classes/`)

- Aucune classe personnalisée ou définition d'`ObjectModel` n'est présente dans ce module. Toutes les données sont stockées directement dans la table `ps_configuration` de PrestaShop.

### 4.4 Actifs JavaScript (`views/js/`)

- Aucun fichier JavaScript personnalisé n'est inclus dans ce module. La fonctionnalité du module repose entièrement sur la bibliothèque JavaScript externe de Google qu'il intègre.

### 4.5 Feuilles de style CSS (`views/css/`)

- Aucun fichier CSS personnalisé n'est inclus dans ce module. Le style du widget de commentaires Google est contrôlé par les propres styles intégrés de Google. Toute personnalisation de style devrait cibler l'iframe/les éléments Google générés via des remplacements de thème (ce qui peut être difficile en raison des restrictions d'iframe inter-domaines).

### 4.6 Structure du template Smarty (`views/templates/`)

Le module utilise un seul template Smarty pour afficher le widget de commentaires Google.

- **Templates de hook (`views/templates/hook/`)** :
  - `googlecomments.tpl` : Ce template est rendu lorsque le module est accroché. Il contient la structure HTML du widget de commentaires Google, y compris l'élément `<div>` avec les attributs `data-href`, `data-width` et `data-num-comments`, et la balise `script` pour charger le SDK JavaScript de la plateforme Google.
    - **Objectif :** Intégrer le widget de commentaires Google sur le front-office.
    - **Variables utilisées :**
      - `{$link->getModuleLink('googlecomments', 'ajax', array(), true)|escape:'htmlall':'UTF-8'}` : Il s'agit probablement d'un vestige ou d'un espace réservé car le module n'utilise pas de contrôleur AJAX. L'attribut `data-href` pour les commentaires Google pointe généralement vers l'URL canonique de la page où les commentaires sont affichés (par exemple, l'URL de la page produit).
      - `{Configuration::get('GOOGLE_COMMENTS_WIDTH')}` : Récupère la largeur configurée pour le bloc de commentaires.
      - `{Configuration::get('GOOGLE_COMMENTS_NUM')}` : Récupère le nombre de commentaires à afficher.

### 4.7 Schéma de base de données et carte des hooks

- **Tables de base de données** :
  Le module ne crée aucune table de base de données personnalisée. Tous ses paramètres de configuration sont stockés dans la table `ps_configuration` :

  - `GOOGLE_COMMENTS_ENABLED` : Stocke `1` (activé) ou `0` (désactivé) pour l'affichage des commentaires.
  - `GOOGLE_COMMENTS_HOOK` : Stocke le nom du hook sélectionné (par exemple, `displayProductExtraContent`).
  - `GOOGLE_COMMENTS_WIDTH` : Stocke la largeur du bloc de commentaires en pixels.
  - `GOOGLE_COMMENTS_NUM` : Stocke le nombre de commentaires à afficher.
- **Table des hooks enregistrés** :

| Nom du Hook | Moment d'exécution | Objectif technique |
| --- | --- | --- |
| `displayHeader` | Dans la section `<head>` de chaque page. | Utilisé pour enregistrer des actifs (bien que ce module ne l'utilise pas pour cela, c'est un hook courant). |
| `displayProductExtraContent` | Dans la zone de contenu principale d'une page produit, souvent dans un onglet ou sous la description. | **Hook principal pour afficher le bloc de commentaires sur les pages produits.** |
| `displayLeftColumn` | Dans la barre latérale gauche de la boutique. | Hook optionnel pour afficher le bloc de commentaires (moins courant pour les commentaires complets). |
| `displayRightColumn` | Dans la barre latérale droite de la boutique. | Hook optionnel pour afficher le bloc de commentaires (moins courant pour les commentaires complets). |
| `displayFooter` | Dans la section du pied de page de la boutique. | Hook optionnel pour afficher le bloc de commentaires (moins courant pour les commentaires complets). |
| `actionFrontControllerSetMedia` | Avant que le contrôleur frontal ne rende la page, permettant aux modules d'ajouter du JS/CSS. | Utilisé pour ajouter le SDK JavaScript de la plateforme Google à la page. |

## 5. Support officiel et mises à jour

Pour les dernières mises à jour, corrections de bugs et support professionnel pour le module Commentaires Google+, veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu/my-account/orders/). Notre équipe est dédiée à fournir une assistance et à assurer le bon fonctionnement de vos modules.
