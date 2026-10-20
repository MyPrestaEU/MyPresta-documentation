---
title: "Pages CMS pour utilisateurs connectés uniquement - Manuel du Marchand & Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop 'Pages CMS pour utilisateurs connectés uniquement' par MyPresta.eu."
sidebar:
  label: "Pages CMS pour utilisateurs connectés uniquement - Manuel du Marchand & Guide de Configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module CMS pages for logged only sur MyPresta.eu](https://mypresta.eu/modules/front-office-features/cms-pages-for-logged-only.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/front-office/cms-pages-for-logged-only/)
>
> ---


# Pages CMS pour utilisateurs connectés uniquement

## 1. Exigences et compatibilité

- **Versions de PrestaShop prises en charge** : PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilité PHP** : PHP 5.6 - 8.5
- **Exigences d'hébergement** : Les extensions PHP standard (cURL, JSON, OpenSSL) sont généralement suffisantes. Aucune configuration de serveur spéciale n'est requise au-delà d'un environnement d'hébergement PrestaShop standard.

## 2. Guide de configuration complet (Chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

Après l'installation, cliquez sur « Configurer » à côté du module « Pages CMS pour utilisateurs connectés uniquement ». Vous verrez un seul écran de configuration.

![Exemple d'écran de configuration des pages CMS pour utilisateurs connectés uniquement](https://mypresta.eu/images/art/cms-pages-for-logged-only-configuration.png)

Cet écran présente une liste de toutes vos pages CMS existantes. Pour chaque page, vous verrez un simple interrupteur pour activer ou désactiver la restriction « connectée uniquement ».

-   **Nom du paramètre :** `cmsp` (Ceci est l'identifiant interne, vous verrez les titres réels des pages CMS).
-   **Ce que fait ce paramètre :** Ce paramètre vous permet de sélectionner les pages CMS spécifiques qui seront restreintes aux clients connectés uniquement. Chaque ligne représente une des pages CMS de votre boutique.
-   **Effet de la modification de ce paramètre :**
    -   *Lorsqu'il est activé (interrupteur sur ON/vert) :* La page CMS sélectionnée ne sera accessible qu'aux clients connectés à leur compte. Si un client non connecté tente de visiter cette page, il sera redirigé vers la page de connexion. Après une connexion réussie, il sera renvoyé à cette page CMS spécifique.
    -   *Lorsqu'il est désactivé (interrupteur sur OFF/rouge) :* La page CMS sélectionnée sera accessible publiquement à tous les visiteurs, qu'ils soient connectés ou non. C'est le comportement par défaut pour toutes les pages CMS dans PrestaShop.
-   **Valeur recommandée :** Cela dépend entièrement de vos besoins commerciaux. Activez-le pour toute page CMS contenant des informations sensibles, exclusives ou réservées aux membres.
-   **Scénario/exemple de marchand :**
    -   Vous avez une page CMS « Conditions générales de vente en gros ». Vous activeriez l'interrupteur à côté de cette page afin que seuls vos clients grossistes enregistrés puissent la consulter.
    -   Vous créez une page CMS « Guide de contenu Premium » pour les clients fidèles. Vous activeriez l'interrupteur pour cette page afin d'encourager l'inscription et de récompenser les clients existants.
    -   Vous avez une page « À propos de nous » standard. Vous laisseriez l'interrupteur désactivé, car cette page doit être visible publiquement par tous les visiteurs.

Après avoir fait vos sélections, n'oubliez pas de cliquer sur le bouton **« Enregistrer »** en bas de la page pour appliquer vos modifications.

### 2.2 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Valeur par défaut / Recommandée | Objectif et impact |
| --- | --- | --- | --- |
| Page de configuration du module | Interrupteurs individuels des pages CMS | Désactivé (OFF) | Contrôle si une page CMS spécifique nécessite qu'un client soit connecté pour la consulter. L'activation redirige les utilisateurs non connectés vers la page de connexion, puis vers la page CMS après une connexion réussie. |

## 3. Dépannage pour les marchands et questions fréquemment posées (FAQ)

**Q : J'ai activé la restriction pour une page CMS, mais les utilisateurs non connectés peuvent toujours la voir. Qu'est-ce qui ne va pas ?**
R :

1.  **Vider le cache :** La raison la plus courante est la mise en cache. Allez dans **Paramètres avancés > Performances** dans votre Back Office PrestaShop et cliquez sur « Vider le cache » (ou « Vider le cache Smarty » dans les versions plus anciennes). Le cache de votre navigateur pourrait également avoir besoin d'être vidé.
2.  **Enregistrer la configuration :** Assurez-vous d'avoir cliqué sur le bouton « Enregistrer » sur la page de configuration du module après avoir activé la restriction pour la page CMS spécifique.
3.  **Vérifier l'URL de la page CMS :** Vérifiez à nouveau que vous testez la bonne URL pour la page CMS que vous avez restreinte.

**Q : Après s'être connecté, le client est redirigé vers la page d'accueil au lieu de la page CMS restreinte. Pourquoi ?**
R : Ce module est conçu pour rediriger le client vers la page CMS restreinte d'origine après une connexion réussie. Si cela ne se produit pas, cela peut être dû à :

1.  **Redirections de connexion personnalisées :** Un autre module ou une modification de thème personnalisée pourrait outrepasser le comportement de redirection de connexion par défaut de PrestaShop. Désactivez temporairement les autres modules qui affectent la connexion/redirection pour tester.
2.  **Spécificités de la version de PrestaShop :** Bien que le module soit compatible avec de nombreuses versions, des surcharges de thème ou de noyau très spécifiques dans des versions plus anciennes/nouvelles de PrestaShop pourraient interférer. Assurez-vous que vos fichiers de base PrestaShop sont standard.

**Q : Puis-je restreindre des catégories ou des produits au lieu des pages CMS ?**
R : Non, ce module est spécifiquement conçu pour les pages CMS uniquement. Il ne fournit pas de fonctionnalité pour restreindre les catégories, les produits ou d'autres types de contenu. Vous auriez besoin d'un module différent à ces fins.

**Q : Ce module affecte-t-il le référencement ?**
R : Lorsqu'une page est restreinte, les robots d'exploration des moteurs de recherche (comme Googlebot) seront généralement redirigés vers la page de connexion, tout comme un utilisateur humain. Cela signifie que le contenu de la page CMS restreinte ne sera pas indexé par les moteurs de recherche. Si le contenu est destiné à être public et indexé, ne le restreignez pas avec ce module. Pour le contenu qui doit être masqué des moteurs de recherche mais toujours accessible aux utilisateurs connectés, ce comportement est souhaité.

**Q : Comment traduire le texte du module (le cas échéant) ?**
R : Ce module a très peu de texte en front-office, car il gère principalement la redirection. Tous les messages liés à la connexion sont gérés par la page d'authentification principale de PrestaShop. S'il y avait des textes spécifiques au module, vous les traduiriez via **International > Traductions** dans votre Back Office. Sélectionnez « Traductions des modules installés », choisissez votre thème, puis recherchez « Pages CMS pour utilisateurs connectés uniquement » dans la liste.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

### 4.1 Vue d'ensemble de l'architecture

Le module « Pages CMS pour utilisateurs connectés uniquement » (`privatecms`) fonctionne principalement en surchargeant le `CmsController` principal pour intercepter les requêtes de pages CMS. Il vérifie si une page CMS demandée est configurée pour un accès « connectée uniquement » et, si l'utilisateur n'est pas connecté, déclenche une redirection vers la page d'authentification. Après une connexion réussie, le mécanisme de redirection par défaut de PrestaShop (que le module utilise) renvoie l'utilisateur à la page initialement demandée. La configuration est gérée via une méthode `getContent()` standard dans le fichier principal du module, stockant les paramètres dans `ps_configuration`.

### 4.2 Contrôleurs (`controllers/`)

-   **Contrôleurs Front-Office** :

    -   `override/controllers/front/CmsController.php`
        -   **Nom de la classe :** `CmsController` (surcharge le `CmsController` principal de PrestaShop)
        -   **Classe parente :** `CmsControllerCore`
        -   **Responsabilité :** Cette surcharge est le cœur de la fonctionnalité du module. Elle intercepte la méthode `init()` du `CmsController`. Avant que la page CMS ne soit rendue, elle vérifie si l'ID de la page CMS actuelle (`$this->cms->id`) est présent dans la liste des pages restreintes stockées dans la configuration du module. Si la page est restreinte et que le client n'est pas connecté (`$this->context->customer->isLogged()`), elle redirige l'utilisateur vers la page d'authentification (`$this->context->link->getPageLink('authentication')`). Elle inclut également un paramètre `back` dans l'URL de redirection, garantissant que PrestaShop redirige l'utilisateur vers la page CMS d'origine après une connexion réussie.
-   **Contrôleurs d'administration Back-Office** : Aucun. Toute la configuration est gérée via la méthode `getContent()` du module principal.

### 4.3 Classes et modèles de base (`classes/`)

Aucun. Le module ne définit aucune classe personnalisée ni entité `ObjectModel`. Il interagit directement avec les classes de base PrestaShop existantes comme `Configuration`, `Cms`, `Customer` et `Link`.

### 4.4 Actifs JavaScript (`views/js/`)

Aucun. Le module n'inclut aucun fichier JavaScript personnalisé. Sa fonctionnalité est purement côté serveur (redirection basée sur PHP).

### 4.5 Feuilles de style CSS (`views/css/`)

-   `privatecms/css.css`
    -   **Portée :** Style du formulaire d'administration du Back-Office.
    -   **Principaux composants et conteneurs d'interface utilisateur qu'il stylise :** Cette feuille de style contient probablement un style minimal pour le formulaire de configuration du module dans le Back Office de PrestaShop, garantissant que la mise en page et les éléments (comme la liste des pages CMS et les interrupteurs) sont affichés correctement et de manière cohérente avec le thème d'administration de PrestaShop.
    -   **Sélecteurs de classe CSS clés que les développeurs peuvent surcharger :** Des sélecteurs spécifiques seraient trouvés dans le fichier, ciblant généralement des éléments dans le modèle `admin.tpl`.

### 4.6 Structure du modèle Smarty (`views/templates/`)

-   **Modèles d'administration (`views/templates/admin/`)** :
    -   `privatecms/admin.tpl`
        -   **Objectif :** Ce modèle est rendu par la méthode `getContent()` du fichier principal du module (`privatecms.php`). Il affiche la liste de toutes les pages CMS disponibles dans le Back Office, ainsi qu'un interrupteur à bascule pour chaque page, permettant à l'administrateur d'activer ou de désactiver la restriction « connectée uniquement ». Il itère sur les pages CMS et affiche leurs titres et l'état actuel de la restriction (coché/décoché).

### 4.7 Schéma de la base de données et carte des hooks

-   **Tables de base de données** :

    -   Le module ne crée aucune table SQL personnalisée.
    -   La configuration est stockée dans la table `ps_configuration` (ou préfixe `_configuration`).
        -   **Clé :** `cmsp`
        -   **Valeur :** Un tableau sérialisé (ou une chaîne JSON, selon la version de PrestaShop et l'implémentation du module) contenant les ID des pages CMS sélectionnées pour l'accès « connectée uniquement ».
-   **Table des hooks enregistrés** :
    Le module n'enregistre explicitement aucun hook PrestaShop standard dans sa méthode `install()`. Sa fonctionnalité principale repose sur la surcharge du `CmsController`, ce qui est un moyen plus direct d'intercepter les requêtes de pages CMS.

| Nom du hook | Moment d'exécution | Objectif technique |
| --- | --- | --- |
| `override/controllers/front/CmsController.php` | Pendant l'initialisation du `CmsController` | Intercepte les requêtes de pages CMS pour vérifier le statut de connexion et rediriger si nécessaire. |

## 5. Support officiel et mises à jour

Pour les dernières mises à jour, corrections de bugs et support officiel du module « Pages CMS pour utilisateurs connectés uniquement », veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu/). Notre équipe de support est disponible pour vous aider avec tout problème ou question concernant la fonctionnalité et la compatibilité du module.
