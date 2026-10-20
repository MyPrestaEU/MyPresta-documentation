---
title: "Pages CMS protégées par mot de passe - Manuel du Marchand & Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop 'Pages CMS protégées par mot de passe' par MyPresta.eu."
sidebar:
  label: "Pages CMS protégées par mot de passe - Manuel du Marchand & Guide de Configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Password protected CMS pages sur MyPresta.eu](https://mypresta.eu/modules/front-office-features/password-protected-cms-pages.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/front-office/password-protected-cms-pages/)
>
> ---


# Pages CMS protégées par mot de passe

## 1. Exigences et compatibilité

- **Versions PrestaShop prises en charge** : PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilité PHP** : PHP 5.6 - 8.5
- **Exigences d'hébergement** : Extensions PHP standard (cURL, JSON, OpenSSL).

## 2. Parcours de configuration complet (Chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

Après l'installation, cliquer sur « Configurer » sur le module vous mènera à son écran de configuration principal. Cet écran sert principalement de point d'entrée vers la zone de gestion dédiée de vos pages CMS protégées.

- **Ce que fait cet écran :** Cette page fournit généralement un bref aperçu ou un lien direct vers l'interface de gestion principale où vous configurerez et gérerez réellement vos pages CMS protégées par mot de passe. Elle pourrait également contenir des paramètres généraux si le module en avait, mais pour ce module, la fonctionnalité principale est gérée dans une section distincte.
- **Effet de la modification des paramètres :** Tout paramètre ici aurait un impact direct sur le comportement global ou l'apparence du module.
- **Valeur recommandée :** Suivez les instructions à l'écran, généralement en cliquant sur un bouton pour passer à la gestion des pages CMS.
- **Scénario/exemple pour le marchand :** Vous venez d'installer le module. Vous verrez probablement un bouton comme « Gérer les pages CMS protégées » ou « Configurer les mots de passe CMS ». Cliquer dessus vous mènera à l'écran dédié pour commencer à protéger vos pages.

### 2.2 Écran d'administration dédié : Gérer les pages CMS protégées (Back Office > Modules > Pages CMS protégées par mot de passe > Configurer > [Lien vers la gestion])

C'est l'écran principal où vous gérerez quelles pages CMS sont protégées et quels sont leurs mots de passe. Vous accédez à cet écran généralement en cliquant sur un lien ou un bouton depuis la page de configuration principale du module.

- **Nom de l'écran et emplacement du menu :** Vous trouverez généralement un nouvel élément de menu sous **Modules > Gestionnaire de modules > Pages CMS protégées par mot de passe > Configurer**, qui vous dirige ensuite vers l'interface de gestion. L'URL pourrait ressembler à `admin/index.php?controller=AdminPcmsController`.
- **Actions et paramètres disponibles :**
  - **Tableau de liste :** Cet écran affichera un tableau listant toutes vos pages CMS existantes. Pour chaque page, vous verrez son nom, son ID et si elle est actuellement protégée.
  - **Ajouter/Modifier la protection :** Pour chaque page CMS de la liste, vous trouverez généralement un bouton/icône « Modifier » ou « Configurer ». Cliquer dessus ouvrira un formulaire où vous pourrez :
    - **Activer/Désactiver la protection :** Un simple interrupteur (Oui/Non) pour activer ou désactiver la protection par mot de passe pour cette page CMS spécifique.
      - *Lorsque activé :* La page nécessitera un mot de passe pour afficher son contenu sur le front office.
      - *Lorsque désactivé :* La page sera publiquement accessible comme une page CMS standard.
      - *Valeur recommandée :* « Oui » pour les pages que vous souhaitez protéger, « Non » pour les pages publiques.
      - *Scénario pour le marchand :* Vous souhaitez protéger votre page « Offres VIP », vous activez donc la protection.
    - **Définir le mot de passe :** Un champ de saisie où vous définissez le mot de passe pour cette page CMS spécifique.
      - *Effet de la modification :* C'est le mot de passe exact que les clients devront saisir pour afficher la page.
      - *Valeur recommandée :* Choisissez un mot de passe fort et unique pour chaque page protégée.
      - *Scénario pour le marchand :* Vous définissez « MONOFFRESECRETE » comme mot de passe pour votre page « Offres VIP ».
  - **Actions en masse :** Selon la version du module, il peut y avoir des options pour activer/désactiver la protection pour plusieurs pages à la fois, bien que la gestion individuelle des pages soit plus courante pour les paramètres de mot de passe.
- **Effet des modifications :**
  - Lorsque vous activez la protection et définissez un mot de passe pour une page CMS, cette page devient immédiatement protégée par mot de passe sur votre front office. Les clients visitant son URL verront l'invite de mot de passe.
  - La désactivation de la protection rend la page à nouveau publiquement visible.
- **Flux de travail recommandé pour la gestion quotidienne de la boutique :**
  1. Décidez quelles pages CMS doivent être privées ou exclusives.
  2. Naviguez vers cet écran « Gérer les pages CMS protégées ».
  3. Trouvez la page CMS souhaitée dans la liste.
  4. Cliquez sur « Modifier » ou l'action équivalente pour cette page.
  5. Activez l'interrupteur de protection par mot de passe.
  6. Entrez un mot de passe fort et unique.
  7. Enregistrez vos modifications.
  8. Communiquez le mot de passe à votre public cible.

### 2.3 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Par défaut / Recommandé | Objectif et impact |
| --- | --- | --- | --- |
| **Gérer les pages CMS protégées** | Activer/Désactiver la protection | Non / Oui (selon les besoins) | Contrôle si une page CMS spécifique nécessite un mot de passe pour être visualisée. |
| | Mot de passe pour la page CMS | (Vide) / Mot de passe fort et unique | La chaîne exacte que les clients doivent saisir pour accéder au contenu protégé. |

## 3. Dépannage pour les marchands et questions fréquemment posées (FAQ)

**Q : J'ai défini un mot de passe, mais la page est toujours visible sans. Qu'est-ce qui ne va pas ?**
R :

1. **Vérifiez si la protection est activée :** Allez dans l'écran « Gérer les pages CMS protégées » et assurez-vous que l'interrupteur « Activer la protection » pour cette page CMS spécifique est réglé sur « Oui ».
2. **Videz le cache de votre navigateur :** Votre navigateur pourrait vous montrer une version mise en cache de la page. Essayez de vider le cache de votre navigateur ou d'ouvrir la page dans une fenêtre de navigation privée/incognito.
3. **Videz le cache de PrestaShop :** Allez dans **Paramètres avancés > Performances** dans votre Back Office et cliquez sur « Vider le cache » dans le coin supérieur droit. Cela garantit que PrestaShop sert la dernière configuration.

**Q : Puis-je avoir des mots de passe différents pour différentes pages CMS ?**
R : Oui ! Ce module est conçu précisément pour cela. Chaque page CMS peut avoir son propre mot de passe unique, vous permettant de créer plusieurs niveaux de contenu protégé.

**Q : Que se passe-t-il si un client saisit un mot de passe incorrect ?**
R : Le module affichera un message d'erreur (par exemple, « Mot de passe incorrect. Veuillez réessayer. ») et le formulaire de saisie du mot de passe réapparaîtra, permettant au client de ressaisir le mot de passe.

**Q : Puis-je personnaliser l'apparence du formulaire de saisie du mot de passe ?**
R : Le module utilise un style de base pour le formulaire de mot de passe. Pour une personnalisation avancée, vous auriez besoin d'un webmaster ou d'un développeur pour modifier le fichier CSS du module (`css.css`) ou surcharger son template (`cms.tpl`).

**Q : J'ai mis à jour mon thème PrestaShop, et maintenant le formulaire de mot de passe semble étrange. Que dois-je faire ?**
R : Les thèmes personnalisés ont parfois leur propre style qui peut entrer en conflit avec l'affichage des modules.

1. **Videz le cache de PrestaShop :** Essayez toujours ceci en premier (**Paramètres avancés > Performances > Vider le cache**).
2. **Contactez le développeur de votre thème :** Il pourrait avoir des instructions spécifiques pour la compatibilité des modules.
3. **Consultez un webmaster :** Un développeur peut inspecter le CSS et le HTML pour identifier et résoudre les conflits de style.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

Cette section est strictement destinée aux développeurs, webmasters de boutique et agences techniques qui maintiennent ou étendent la boutique.

### 4.1 Aperçu de l'architecture

Le module « Pages CMS protégées par mot de passe » (`passcms`) fonctionne principalement en surchargeant le `CmsController` de base pour intercepter les requêtes de pages CMS. Lorsqu'une page CMS protégée est demandée, il vérifie la présence d'un mot de passe valide dans la session. Si aucun mot de passe valide n'est trouvé, il affiche un formulaire de saisie de mot de passe au lieu du contenu réel du CMS. Le module utilise un contrôleur d'administration dédié (`AdminPcmsController`) pour gérer les paramètres de mot de passe pour chaque page CMS.

### 4.2 Contrôleurs (`controllers/`)

- **Contrôleurs Front-Office** :

  - `passcms/override/controllers/front/CmsController.php`
    - **Nom de la classe et classe parente** : `CmsController` (surcharge le `CmsController` de base)
    - **Responsabilité** : C'est le cœur de la fonctionnalité front-office. Il intercepte la méthode `initContent()` du `CmsController` original. Il vérifie si la page CMS demandée (identifiée par `id_cms`) est configurée comme protégée par mot de passe. Si c'est le cas, et qu'aucun mot de passe valide n'est dans la session, il rend le template `cms.tpl` avec le formulaire de saisie du mot de passe. Il gère également la requête POST pour la soumission du mot de passe, la validant par rapport au mot de passe stocké et définissant une variable de session en cas de succès.
  - `passcms/override/controllers/front/index.php`
    - **Nom de la classe et classe parente** : Pas une classe, généralement un fichier vide ou une mesure de sécurité de base pour empêcher la liste directe des répertoires.
    - **Responsabilité** : Pratique PrestaShop standard pour les répertoires `override`.
- **Contrôleurs d'administration Back-Office** :

  - `passcms/controllers/admin/AdminPcmsController.php`
    - **Nom de l'onglet et entité gérée** : Gère les paramètres de protection par mot de passe pour les pages CMS individuelles. Ce contrôleur étend `ModuleAdminController` et fournit l'interface pour lister les pages CMS et configurer leurs mots de passe. Il gère les opérations CRUD pour l'entité `pcms` (bien qu'aucun `ObjectModel` explicite ne soit listé, il interagit probablement directement avec `ps_configuration` ou une table personnalisée pour le stockage des mots de passe). Il rend la vue en grille des pages CMS et le formulaire pour modifier les paramètres de mot de passe.
  - `passcms/controllers/admin/index.php`
    - **Nom de la classe et classe parente** : Pas une classe, généralement un fichier vide ou une mesure de sécurité de base pour empêcher la liste directe des répertoires.
    - **Responsabilité** : Pratique PrestaShop standard pour les répertoires de contrôleurs.

### 4.3 Classes et modèles de base (`classes/`)

Le dossier du module n'indique aucune classe personnalisée dans le répertoire `classes/`. Cela suggère que le module stocke probablement sa configuration directement dans la table `ps_configuration`, en utilisant des clés comme `PCMS_PASSWORD_ID_CMS_X` où `X` est l'`id_cms`, ou il pourrait utiliser une table personnalisée gérée directement par l'`AdminPcmsController` sans `ObjectModel` dédié.

### 4.4 Actifs JavaScript (`views/js/`)

Le dossier du module n'indique aucun fichier JavaScript personnalisé. La soumission du mot de passe est probablement gérée via un formulaire HTML POST standard ou un simple JS en ligne si un comportement dynamique est présent.

### 4.5 Feuilles de style CSS (`views/css/`)

- `passcms/css.css`
  - **Portée** : Style client Front-office.
  - **Principaux composants d'interface utilisateur et conteneurs qu'il stylise** : Ce fichier contient le style de base pour le formulaire de saisie du mot de passe affiché sur les pages CMS protégées. Il cible probablement des éléments comme le conteneur du formulaire, le champ de saisie et le bouton de soumission.
  - **Sélecteurs de classe CSS clés que les développeurs peuvent surcharger** : Les développeurs peuvent inspecter le HTML rendu du formulaire de mot de passe pour identifier des classes spécifiques (par exemple, `.passcms-form`, `.passcms-input`, `.passcms-button`, `.passcms-error`) et les surcharger dans le `custom.css` ou `theme.css` de leur thème pour correspondre à l'image de marque de la boutique.

### 4.6 Structure des templates Smarty (`views/templates/`)

- **Templates d'administration (`views/templates/admin/`)** :

  - `passcms/admin.tpl`
    - **Objectif** : Ce template est probablement utilisé pour la page de configuration principale du module, fournissant le point d'entrée ou des informations générales, potentiellement en lien avec l'interface de gestion `AdminPcmsController`.
  - `passcms/views/templates/admin/script.tpl`
    - **Objectif** : Ce template pourrait contenir du JavaScript en ligne ou des variables Smarty qui sont rendues dans le Back Office pour que l'`AdminPcmsController` gère le comportement dynamique ou le passage de données.
- **Templates Front-office (`views/templates/front/`)** :

  - `passcms/views/templates/front/cms.tpl`
    - **Objectif** : C'est le template crucial rendu par le `CmsController` surchargé lorsqu'une page CMS protégée est accédée sans mot de passe valide. Il contient la structure HTML du formulaire de saisie du mot de passe, y compris le champ de saisie, le bouton de soumission et tout message d'erreur.

### 4.7 Schéma de la base de données et carte des hooks

- **Tables de la base de données** :

  - Le module ne crée pas explicitement de table SQL personnalisée selon le dossier. Il est très probable que les paramètres de mot de passe pour chaque page CMS soient stockés dans la table `ps_configuration` en utilisant des clés de configuration uniques, par exemple, `PCMS_PASSWORD_ID_CMS_X` où `X` est l'`id_cms`.
  - `ps_configuration` : Stocke les valeurs de configuration du module, y compris potentiellement les mots de passe pour chaque page CMS.
- **Table des hooks enregistrés** :
Le module fonctionne principalement via la surcharge de contrôleur plutôt que par des hooks traditionnels pour sa fonctionnalité principale. Cependant, il peut enregistrer certains hooks standard pour l'intégration ou l'affichage général du module.

  | Nom du Hook | Moment d'exécution | Objectif technique |
  | --- | --- | --- |
  | `displayBackOfficeHeader` | Rendu dans la section `<head>` des pages du Back Office. | Utilisé pour inclure du CSS (`css.css`) ou du JS pour l'interface `AdminPcmsController`. |
  | `displayHeader` | Rendu dans la section `<head>` des pages du front-office. | Pourrait être utilisé pour inclure du CSS (`css.css`) ou du JS du front-office si nécessaire globalement, bien qu'il soit plus probable qu'il soit chargé conditionnellement par la surcharge du `CmsController`. |
  | `actionFrontControllerSetMedia` | Exécuté lorsqu'un contrôleur frontal définit ses ressources média. | Alternative à `displayHeader` pour le chargement conditionnel des ressources en fonction du contrôleur actuel. |

## 5. Support officiel et mises à jour

Pour les dernières mises à jour, corrections de bugs et support officiel du module « Pages CMS protégées par mot de passe », veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu). Notre équipe de support est disponible pour vous aider avec tout problème ou question que vous pourriez avoir concernant la fonctionnalité et la compatibilité du module.
