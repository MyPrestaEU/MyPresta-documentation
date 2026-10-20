---
title: "Pages CMS pour groupes - Manuel du marchand et guide de configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop 'Pages CMS pour groupes' par MyPresta.eu."
sidebar:
  label: "Pages CMS pour groupes - Manuel du marchand et guide de configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module CMS pages for groups sur MyPresta.eu](https://mypresta.eu/modules/front-office-features/cms-pages-for-groups.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/front-office/cms-pages-for-groups/)
>
> ---


# Pages CMS pour groupes

## 1. Exigences et compatibilité

- **Versions PrestaShop prises en charge** : PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilité PHP** : PHP 5.6 - 8.5
- **Exigences d'hébergement** : Extensions PHP standard (cURL, JSON, OpenSSL).

## 2. Parcours de configuration complet (chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer > Pages CMS pour groupes)

Ceci est l'écran de configuration principal où vous gérerez quels groupes de clients peuvent accéder à des pages CMS spécifiques.

Lorsque vous accédez pour la première fois à la page de configuration, vous verrez une liste de toutes vos pages CMS existantes. Pour chaque page CMS, vous trouverez des options pour contrôler sa visibilité.

**Structure générale de la page :**
La page de configuration affiche un tableau. Chaque ligne du tableau représente l'une de vos pages CMS. Pour chaque page CMS, vous verrez :

-   **Nom de la page :** Le titre de votre page CMS (par exemple, « À propos de nous », « Conditions générales »).
-   **Groupes de clients :** Une liste de cases à cocher, une pour chaque groupe de clients défini dans votre boutique PrestaShop (par exemple, « Visiteur », « Invité », « Client », « Grossiste »).

**Ce que fait ce paramètre :**
Pour chaque page CMS, vous sélectionnez les groupes de clients qui sont **autorisés** à visualiser cette page spécifique. Si un client ne fait partie d'aucun des groupes sélectionnés pour une page donnée, l'accès à cette page lui sera refusé.

**Effet de la modification de ce paramètre :**

-   **Lorsqu'un groupe est coché pour une page CMS :** Les clients appartenant à ce groupe pourront visualiser la page CMS normalement.
-   **Lorsqu'un groupe est décoché pour une page CMS :** Les clients appartenant à ce groupe **ne pourront pas** visualiser la page CMS. S'ils tentent d'y accéder, ils seront redirigés vers une erreur « Page introuvable ».
-   **Si aucun groupe n'est sélectionné pour une page CMS :** Cela signifie que la page est effectivement masquée à *tous* les clients, car aucun groupe n'a la permission de la visualiser. Cela peut être utile pour les pages en construction ou le contenu interne uniquement.
-   **Si tous les groupes sont sélectionnés pour une page CMS :** Cela signifie que la page est visible par tous, revenant effectivement au comportement par défaut de PrestaShop pour cette page spécifique.

**Valeur recommandée :**
Cela dépend entièrement de vos besoins commerciaux.

-   Pour les pages standard comme « À propos de nous » ou « Contactez-nous », vous cocherez probablement tous les groupes.
-   Pour des conditions légales spécifiques aux B2B, vous ne cocherez peut-être que votre groupe « Grossiste ».
-   Pour une page « Avantages du club VIP », vous ne cocherez peut-être que votre groupe « Client VIP ».

**Scénario / exemple de marchand :**
Supposons que vous ayez trois groupes de clients : « Visiteur » (non connecté), « Client » (utilisateurs enregistrés standard) et « Grossiste » (clients B2B).

1.  **Scénario 1 : Page « À propos de nous »**

    *   **Objectif :** Informations générales pour tout le monde.
    *   **Action :** Cochez « Visiteur », « Client » et « Grossiste » pour la page « À propos de nous ».
    *   **Résultat :** Tout le monde peut voir la page « À propos de nous ».
2.  **Scénario 2 : Page « Conditions générales de vente en gros »**

    *   **Objectif :** Conditions légales spécifiques uniquement pour vos clients B2B.
    *   **Action :** Cochez uniquement « Grossiste » pour la page « Conditions générales de vente en gros ».
    *   **Résultat :** Seuls les clients du groupe « Grossiste » peuvent visualiser cette page. Les groupes « Visiteur » et « Client » se verront refuser l'accès.
3.  **Scénario 3 : Page « Détails du programme de fidélité »**

    *   **Objectif :** Informations pour les clients enregistrés sur leurs points de fidélité.
    *   **Action :** Cochez « Client » et « Grossiste » (en supposant que les clients grossistes peuvent également faire partie du programme de fidélité) pour la page « Détails du programme de fidélité ».
    *   **Résultat :** Seuls les clients connectés (standard ou grossistes) peuvent visualiser cette page. Les visiteurs se verront refuser l'accès.

**Enregistrement de vos modifications :**
Après avoir effectué vos sélections pour toutes les pages CMS, n'oubliez pas de cliquer sur le bouton **« Enregistrer »** (généralement en bas de la page) pour appliquer vos modifications.

### 2.2 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Par défaut / Recommandé | Objectif et impact |
| --- | --- | --- | --- |
| Page de configuration du module | **Nom de la page CMS** (par exemple, « À propos de nous ») | Varie selon la page | Contrôle quels groupes de clients peuvent visualiser cette page CMS spécifique. |
| | Case à cocher pour le groupe **« Visiteur »** | Varie | Si cochée, les utilisateurs non connectés peuvent visualiser la page. |
| | Case à cocher pour le groupe **« Invité »** | Varie | Si cochée, les utilisateurs qui ont commandé en tant qu'invité peuvent visualiser la page. |
| | Case à cocher pour le groupe **« Client »** | Varie | Si cochée, les clients enregistrés standard peuvent visualiser la page. |
| | Case à cocher pour le groupe **« Grossiste »** (ou tout groupe personnalisé) | Varie | Si cochée, les clients de ce groupe spécifique peuvent visualiser la page. |
| | **Bouton Enregistrer** | N/A | Applique tous les paramètres de visibilité sélectionnés aux pages CMS. |

## 3. Dépannage du marchand et questions fréquemment posées (FAQ)

**Q1 : J'ai restreint une page CMS, mais elle apparaît toujours dans mon menu de pied de page/d'en-tête. Pourquoi ?**
R1 : Ce module contrôle l'*accès* au contenu de la page, pas sa visibilité dans les menus de navigation. Si vous souhaitez masquer le lien lui-même à certains groupes, vous devrez soit :
\* Supprimer manuellement le lien des fichiers de modèle de votre thème (par exemple, `footer.tpl`, `header.tpl`).
\* Utiliser un module de gestion de menu qui offre une visibilité basée sur les groupes pour les éléments de menu.
\* Si un client clique sur un lien restreint, l'accès au contenu de la page lui sera toujours refusé.

**Q2 : Un client est connecté, mais il ne peut toujours pas voir une page que j'ai autorisée pour son groupe. Quel est le problème ?**
R2 :
\* **Vider le cache :** Commencez toujours par vider le cache de votre PrestaShop. Allez dans **Paramètres avancés > Performances**, et cliquez sur « Vider le cache » (ou « Vider le cache Smarty » dans les versions plus anciennes).
\* **Vérifier l'affectation du groupe :** Vérifiez à nouveau que le client est bien affecté au(x) groupe(s) de clients correct(s) que vous avez autorisé(s) pour la page CMS. Vous pouvez le vérifier dans **Clients > Clients** en modifiant le profil du client.
\* **Configuration du module :** Revenez à la page de configuration du module et assurez-vous que la case à cocher du groupe correct est cochée pour cette page CMS spécifique.
\* **Cache du navigateur :** Demandez au client de vider le cache de son navigateur ou d'essayer d'accéder à la page dans une fenêtre de navigation privée/incognito.

**Q3 : Puis-je afficher un message personnalisé au lieu d'une erreur « Page introuvable » lorsque l'accès est refusé ?**
R3 : Ce module, dans sa version actuelle, redirige vers la page standard « Page introuvable » de PrestaShop. La personnalisation de cela nécessiterait des modifications de thème ou un module supplémentaire qui gère spécifiquement les pages d'erreur personnalisées basées sur le refus d'accès.

**Q4 : Ce module va-t-il ralentir ma boutique ?**
R4 : Non, le module est très léger. Il surcharge un contrôleur PrestaShop de base pour vérifier les permissions des groupes de clients avant de charger une page CMS. Cette vérification est efficace et ne devrait pas avoir d'impact notable sur les performances de votre boutique.

**Q5 : J'ai mis à jour PrestaShop, et maintenant le module ne fonctionne plus. Que dois-je faire ?**
R5 :
\* **Vérifier la version du module :** Assurez-vous d'avoir la dernière version du module « Pages CMS pour groupes » depuis votre compte MyPresta.eu, compatible avec votre nouvelle version de PrestaShop.
\* **Réinstaller/Reconfigurer :** Parfois, après une mise à jour majeure de PrestaShop, les modules peuvent avoir besoin d'être réinstallés ou reconfigurés. Essayez de désinstaller puis de réinstaller le module (vos paramètres devraient être conservés, mais sauvegardez toujours d'abord). Ensuite, revérifiez vos paramètres sur la page de configuration du module.
\* **Vider le cache :** Videz toujours le cache de votre PrestaShop après toute mise à jour ou modification de module.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

### 4.1 Aperçu de l'architecture

Le module « Pages CMS pour groupes » fonctionne en surchargeant le `CmsController` de base dans le front office de PrestaShop. Cela lui permet d'intercepter les requêtes pour les pages CMS *avant* qu'elles ne soient rendues et d'appliquer une logique d'accès personnalisée basée sur les permissions des groupes de clients configurées dans le back office du module. Le module stocke sa configuration directement dans la table `ps_configuration`.

### 4.2 Contrôleurs (`controllers/`)

-   **Contrôleurs Front-Office** :

    -   `groupscms/override/controllers/front/CmsController.php`
        -   **Nom de la classe et classe parente** : `CmsController` (surcharge le `CmsController` de base)
        -   **Responsabilité** : C'est le composant critique. Il étend le `CmsController` original pour ajouter une méthode `init()`. À l'intérieur de `init()`, il récupère l'ID de la page CMS actuelle et vérifie la configuration du module (`Configuration::get('CMSG_CMS_ID_' . (int)$cms->id)`) pour déterminer quels groupes de clients sont autorisés à y accéder. Si le client actuel (ou visiteur) ne fait pas partie d'un groupe autorisé, il le redirige vers la page « Page introuvable » (`$this->redirect_after = '404';`). Cela garantit que les utilisateurs non autorisés ne peuvent pas visualiser le contenu CMS restreint.
-   **Contrôleurs d'administration Back-Office** : Aucun. La configuration du module est gérée directement dans la méthode `getContent()` du fichier principal du module.

### 4.3 Classes et modèles de base (`classes/`)

Aucun. Le module ne définit pas de classes `ObjectModel` personnalisées. Il interagit directement avec les objets `CMS` et `Group` PrestaShop existants et stocke sa configuration dans `ps_configuration`.

### 4.4 Actifs JavaScript (`views/js/`)

Aucun. Le module n'inclut aucun fichier JavaScript personnalisé.

### 4.5 Feuilles de style CSS (`views/css/`)

-   `groupscms/css.css`
    -   **Portée** : Style du formulaire d'administration du Back-Office.
    -   **Principaux composants et conteneurs d'interface utilisateur qu'il stylise** : Cette feuille de style est probablement utilisée pour styliser le tableau de configuration du module dans le back office de PrestaShop, garantissant qu'il est cohérent avec le thème d'administration de PrestaShop. Elle pourrait définir des styles pour les lignes du tableau, les cases à cocher ou les étiquettes dans le formulaire de configuration du module.
    -   **Sélecteurs de classe CSS clés que les développeurs peuvent surcharger dans leur thème** : Des sélecteurs spécifiques se trouveraient dans le fichier, mais ils cibleraient généralement des éléments dans la sortie `getContent()` du module, tels que `table.groupscms_table`, `tr.groupscms_row`, `input[type="checkbox"].groupscms_checkbox`, etc.

### 4.6 Structure des modèles Smarty (`views/templates/`)

-   **Modèles de hook (`views/templates/hook/`)** : Aucun. Le module ne rend pas de contenu via des hooks front-office standard.
-   **Modèles d'administration (`views/templates/admin/`)** :

    -   `groupscms/admin.tpl`
        -   **Objectif** : Ce modèle est rendu par la méthode `getContent()` du fichier principal du module (`groupscms.php`). Il génère l'interface de configuration complète du module dans le back office de PrestaShop. Cela inclut le tableau listant toutes les pages CMS et les cases à cocher pour chaque groupe de clients.
    -   `groupscms/cms.tpl`
        -   **Objectif** : Ce modèle est probablement un include ou un partiel utilisé dans `admin.tpl` pour rendre des lignes ou des sections individuelles liées aux pages CMS dans le tableau de configuration. Il contiendrait la boucle pour afficher chaque page CMS et ses cases à cocher de groupe associées.
-   **Modèles Front-Office (`views/templates/front/`)** : Aucun. Le module n'ajoute pas de nouveaux modèles Front-Office. Il contrôle l'accès aux modèles de pages CMS existants.

### 4.7 Schéma de base de données et carte des hooks

-   **Tables de base de données** :
    Le module ne crée aucune table SQL personnalisée. Toutes les données de configuration sont stockées dans la table `ps_configuration`.

    -   **Clés de configuration** :
        -   `CMSG_CMS_ID_[CMS_ID]` : Stocke une chaîne de valeurs `group_id` séparées par des virgules pour chaque page CMS. Par exemple, `CMSG_CMS_ID_12` pourrait stocker `"1,2,3"` indiquant que les groupes avec les ID 1, 2 et 3 ont accès à la page CMS avec l'ID 12.
        -   `groupscms_many_page` : (Probablement un drapeau interne ou un paramètre hérité, non directement configurable par l'utilisateur).
        -   `mypresta_updates`, `update_`, `updatev_` : Ce sont des clés courantes utilisées par les modules MyPresta.eu pour les vérifications de mise à jour et le suivi des versions.
-   **Table des hooks enregistrés** :

| Nom du hook | Moment d'exécution | Objectif technique |
| --- | --- | --- |
| `actionAdminControllerSetMedia` | Exécuté lorsqu'un contrôleur d'administration définit ses médias (CSS/JS). | Utilisé par le module pour inclure sa feuille de style `css.css` pour la page de configuration du back-office. |
| `displayBackOfficeHeader` | Exécuté dans la section `<head>` du Back Office. | Souvent utilisé pour inclure des CSS/JS d'administration globaux ou pour des vérifications de mise à jour. Le module pourrait l'utiliser pour son mécanisme de mise à jour. |

## 5. Support officiel et mises à jour

Pour les mises à jour officielles, le support technique et pour télécharger les dernières versions du module « Pages CMS pour groupes », veuillez visiter votre compte client sur [MyPresta.eu](https://mypresta.eu/my-account/orders/). Notre équipe de support est disponible pour vous aider avec toutes les questions ou problèmes que vous pourriez avoir.
