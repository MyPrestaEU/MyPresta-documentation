---
title: "Onglet CMS de la page produit - Manuel du marchand et guide de configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop 'Onglet CMS de la page produit' par MyPresta.eu."
sidebar:
  label: "Onglet CMS de la page produit - Manuel du marchand et guide de configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Product page CMS tab sur MyPresta.eu](https://mypresta.eu/modules/front-office-features/product-page-cms-tab.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/front-office/product-page-cms-tab/)
>
> ---


# Onglet CMS de la page produit

## 1. Exigences et compatibilité

- **Versions PrestaShop prises en charge :** PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilité PHP :** PHP 7.1 - 8.5
- **Exigences d'hébergement :** Les extensions PHP standard (cURL, JSON, OpenSSL) sont généralement requises pour PrestaShop lui-même et sont habituellement disponibles par défaut sur la plupart des environnements d'hébergement. Aucune extension spéciale ou inhabituelle n'est nécessaire pour ce module.

## 2. Parcours de configuration complet (chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

Après l'installation, cliquez sur « Configurer » à côté du module « Onglet CMS de la page produit » dans votre Gestionnaire de modules. Cela vous mènera à l'écran de configuration principal.

#### **Sélectionner la page CMS à afficher comme onglet**

C'est le paramètre principal du module. Il détermine laquelle de vos pages CMS existantes sera affichée comme un nouvel onglet sur toutes les pages produit.

- **Ce que fait ce paramètre :** Ce menu déroulant liste toutes les pages CMS que vous avez créées dans votre boutique PrestaShop (trouvées sous **Design > Pages** ou **Design > CMS** dans les versions plus anciennes). Vous devez sélectionner l'une de ces pages.
- **Effet de la modification de ce paramètre :**
  - *Lorsqu'une page CMS est sélectionnée :* Un nouvel onglet apparaîtra sur chaque page produit de votre boutique. Le titre de cet onglet sera le titre de la page CMS sélectionnée, et le contenu affiché lorsque l'onglet est cliqué sera le contenu de cette page CMS.
  - *Lorsque « --- Sélectionner --- » est choisi :* Aucun nouvel onglet n'apparaîtra sur les pages produit. Le module sera effectivement inactif en termes d'affichage front-office.
- **Valeur recommandée :** Sélectionnez la page CMS qui contient les informations que vous souhaitez partager universellement sur toutes vos pages produit (par exemple, une page « Informations d'expédition », « Guide des tailles » ou « Détails de la garantie »).
- **Scénario / exemple de marchand :** Vous souhaitez fournir un « Guide des tailles » détaillé pour tous les produits vestimentaires. Vous créeriez d'abord une page CMS intitulée « Guide des tailles » avec toutes les informations pertinentes. Ensuite, dans la configuration de ce module, vous sélectionneriez « Guide des tailles » dans le menu déroulant. Désormais, chaque page produit aura un onglet « Guide des tailles ».

#### **Type d'onglet**

Ce paramètre contrôle la manière dont le module s'intègre au système d'onglets de PrestaShop, en particulier pour les différentes versions de PrestaShop.

- **Ce que fait ce paramètre :** Ce menu déroulant vous permet de choisir la méthode utilisée par le module pour afficher l'onglet. Il s'agit principalement d'un paramètre de compatibilité pour les différentes versions de PrestaShop.
- **Effet de la modification de ce paramètre :**
  - *Lorsque « PrestaShop 1.7 / 8.x / 9.x » est sélectionné :* Le module utilisera le hook `displayProductExtraContent`, qui est la manière standard et recommandée d'ajouter de nouveaux onglets dans les versions modernes de PrestaShop. Cela garantit un aspect et une convivialité natifs.
  - *Lorsque « PrestaShop 1.6 » est sélectionné :* Le module utilisera des hooks plus anciens comme `productTab` et `productTabContent`, qui étaient standard dans PrestaShop 1.6. Cette option est pour la rétrocompatibilité si vous utilisez une ancienne boutique PrestaShop 1.6 non prise en charge (bien que le module soit officiellement pour 1.7+).
- **Valeur recommandée :** Pour les boutiques PrestaShop 1.7, 8.x et 9.x, sélectionnez toujours **« PrestaShop 1.7 / 8.x / 9.x »**.
- **Scénario / exemple de marchand :** Si vous utilisez PrestaShop 8.1, vous sélectionneriez « PrestaShop 1.7 / 8.x / 9.x » pour vous assurer que l'onglet s'affiche correctement et s'intègre parfaitement au design de votre thème. Si, pour une raison quelconque, vous utilisiez ce module sur une ancienne boutique PrestaShop 1.6, vous sélectionneriez « PrestaShop 1.6 ».

#### **Mises à jour en direct MyPresta.eu**

Cette section est commune à tous les modules MyPresta.eu et vous aide à gérer les mises à jour des modules.

- **Ce que fait ce paramètre :** Cette fonctionnalité vérifie les nouvelles versions du module directement depuis MyPresta.eu.
- **Effet de la modification de ce paramètre :**
  - *Lorsque activé :* Le module vérifiera périodiquement les mises à jour. Si une nouvelle version est disponible, vous verrez une notification dans votre liste de modules ou sur la page de configuration du module. Cela vous aide à rester à jour avec les corrections de bugs et les nouvelles fonctionnalités.
  - *Lorsque désactivé :* Le module ne vérifiera pas les mises à jour automatiquement. Vous devrez vérifier manuellement votre compte MyPresta.eu pour les nouvelles versions.
- **Valeur recommandée :** **OUI**. Maintenir les modules à jour est crucial pour la sécurité, la compatibilité et l'accès aux dernières fonctionnalités.
- **Scénario / exemple de marchand :** Vous voulez vous assurer que votre module dispose toujours des derniers correctifs de sécurité. En activant cette option, vous serez averti lorsqu'une mise à jour est disponible, vous invitant à la télécharger et à l'installer.

### 2.2 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Valeur par défaut / Recommandée | Objectif et impact |
| --- | --- | --- | --- |
| Page de configuration du module | **Sélectionner la page CMS à afficher comme onglet** | --- Sélectionner --- / Votre page CMS choisie | Détermine quel contenu de page CMS apparaît comme un nouvel onglet sur toutes les pages produit. |
| Page de configuration du module | **Type d'onglet** | PrestaShop 1.7 / 8.x / 9.x | Assure l'affichage correct de l'onglet et l'intégration avec l'architecture de votre version de PrestaShop. |
| Page de configuration du module | **Mises à jour en direct MyPresta.eu** | OUI | Active les vérifications automatiques des mises à jour du module depuis MyPresta.eu. |

## 3. Dépannage du marchand et questions fréquemment posées (FAQ)

**Q : Le nouvel onglet n'apparaît pas sur mes pages produit. Que dois-je faire ?**
R :

1.  **Vérifiez la configuration du module :** Allez dans **Modules > Gestionnaire de modules**, trouvez « Onglet CMS de la page produit » et cliquez sur « Configurer ». Assurez-vous d'avoir sélectionné une page CMS valide dans le menu déroulant « Sélectionner la page CMS à afficher comme onglet ». Si « --- Sélectionner --- » est choisi, aucun onglet n'apparaîtra.
2.  **Vérifiez le type d'onglet :** Assurez-vous que le « Type d'onglet » est défini sur « PrestaShop 1.7 / 8.x / 9.x » pour les versions modernes de PrestaShop.
3.  **Videz le cache :** Allez dans **Paramètres avancés > Performances** et cliquez sur « Vider le cache » (ou « Vider le cache Smarty » dans les versions plus anciennes). Parfois, le cache de PrestaShop empêche les modifications d'apparaître immédiatement.
4.  **Vérifiez le statut de la page CMS :** Assurez-vous que la page CMS sélectionnée est active et visible publiquement (non désactivée ou définie comme privée). Vous pouvez vérifier cela sous **Design > Pages**.
5.  **Compatibilité du thème :** Bien que le module utilise des hooks PrestaShop standard, des thèmes très fortement personnalisés peuvent parfois interférer. Si les étapes ci-dessus ne fonctionnent pas, passez temporairement au thème PrestaShop par défaut pour voir si l'onglet apparaît. Si c'est le cas, votre thème pourrait nécessiter un petit ajustement.

**Q : Puis-je avoir différents onglets CMS pour différents produits ?**
R : Ce module est conçu pour afficher *une page CMS spécifique* comme onglet sur *toutes* les pages produit. Il ne prend pas en charge l'affectation de différentes pages CMS à des produits individuels. Si vous avez besoin d'onglets spécifiques aux produits, vous auriez généralement besoin d'un module plus avancé ou d'un développement personnalisé.

**Q : Le contenu de l'onglet semble étrange ou non stylisé.**
R : Le module extrait simplement le contenu de votre page CMS. Le style de ce contenu est généralement géré par le CSS de votre thème PrestaShop.

1.  **Vérifiez le contenu de la page CMS :** Assurez-vous que le contenu de votre page CMS originale (sous **Design > Pages**) est correctement formaté et ne contient pas de HTML cassé.
2.  **CSS du thème :** Le CSS de votre thème pourrait ne pas avoir de styles spécifiques pour le contenu des onglets de produit, ou il pourrait remplacer les styles par défaut. Si vous avez un développeur web, il peut inspecter la page pour identifier et corriger tout conflit de style.

**Q : J'ai mis à jour ma page CMS, mais le contenu de l'onglet sur les pages produit n'a pas changé.**
R : Après avoir mis à jour une page CMS, videz toujours le cache de votre PrestaShop (**Paramètres avancés > Performances > Vider le cache**). Votre boutique pourrait servir une version plus ancienne et mise en cache du contenu.

**Q : Comment traduire le titre de l'onglet si ma boutique est multilingue ?**
R : Le titre de l'onglet est automatiquement tiré du titre de la page CMS sélectionnée. Pour le traduire, vous devez modifier la page CMS elle-même (**Design > Pages**) et fournir des traductions pour son titre et son contenu pour chaque langue que vous prenez en charge. Le module affichera alors le titre traduit correct en fonction de la langue sélectionnée par le client.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

Cette section est strictement destinée aux développeurs, aux webmasters de boutiques et aux agences techniques qui maintiennent ou étendent la boutique.

### 4.1 Vue d'ensemble de l'architecture

Le module « Onglet CMS de la page produit » (`cmstab`) est un module PrestaShop léger conçu pour injecter le contenu d'une page CMS existante dans les pages produit sous forme de nouvel onglet. Il exploite principalement le système de hooks de PrestaShop pour y parvenir. La logique principale du module réside dans son fichier PHP principal, `cmstab.php`, qui gère l'installation, la désinstallation, la configuration et l'enregistrement des hooks. Il n'introduit pas de tables de base de données personnalisées ni d'ObjectModels complexes, s'appuyant plutôt sur la classe `CMS` native de PrestaShop pour la récupération du contenu. Le module fournit deux ensembles de templates pour assurer la compatibilité avec les mécanismes de rendu des onglets de PrestaShop 1.6 et 1.7+, sélectionnables via la configuration du back-office.

### 4.2 Contrôleurs (`controllers/`)

Ce module n'introduit aucun contrôleur d'administration Front-Office ou Back-Office personnalisé. Toutes les fonctionnalités sont gérées via la classe principale du module et le système de hooks de PrestaShop.

### 4.3 Classes et modèles principaux (`classes/`)

Ce module n'introduit aucune classe ou ObjetModel personnalisé dans le répertoire `classes/`. Il utilise directement la classe `CMS` de PrestaShop pour récupérer le contenu en fonction de l'ID de la page CMS configurée.

### 4.4 Actifs JavaScript (`views/js/`)

- **`cmstab/trusted.js`**
  - **Portée :** Back-office (page de configuration du module).
  - **Objectif :** Ce script est généralement inclus dans les modules MyPresta.eu pour gérer la fonctionnalité « Mises à jour en direct MyPresta.eu ». Il communique avec l'API MyPresta.eu pour vérifier les nouvelles versions du module et afficher les notifications de mise à jour dans le back office de PrestaShop. Il n'affecte pas l'affichage front-office ou l'interaction client.

### 4.5 Feuilles de style CSS (`views/css/`)

Ce module n'inclut aucun fichier CSS personnalisé. Le style de l'onglet et de son contenu est hérité du thème PrestaShop actif. Les développeurs souhaitant styliser l'onglet doivent cibler les sélecteurs appropriés fournis par le thème ou le système d'onglets principal de PrestaShop.

### 4.6 Structure des templates Smarty (`views/templates/`)

Le module fournit deux ensembles de templates pour s'adapter aux différentes approches de rendu des onglets des versions de PrestaShop. L'ensemble spécifique utilisé est déterminé par le paramètre « Type d'onglet » dans la configuration du module.

- **Templates de hook (`views/templates/hook/`)** : Ce répertoire n'est pas explicitement utilisé pour le rendu direct des hooks dans ce module. Les templates sont directement référencés depuis `views/front/`.
- **Templates Front-office (`views/templates/front/`)** :

  - **`cmstab/views/front/tab.tpl`**

    - **Objectif :** Ce template est conçu pour la compatibilité PrestaShop 1.6. Il est rendu lorsque le « Type d'onglet » est défini sur « PrestaShop 1.6 ». Il génère le HTML pour l'*en-tête* de l'onglet (la partie cliquable de l'onglet) en utilisant le titre de la page CMS.
    - **Hook :** `productTab` (spécifique à PrestaShop 1.6)
    - **Variables :** `$cmstab_title` (le titre de la page CMS sélectionnée).
  - **`cmstab/views/front/tab16.tpl`**

    - **Objectif :** Ce template est également pour la compatibilité PrestaShop 1.6. Il génère le HTML pour la zone de *contenu* de l'onglet, affichant le contenu réel de la page CMS sélectionnée.
    - **Hook :** `productTabContent` (spécifique à PrestaShop 1.6)
    - **Variables :** `$cmstab_content` (le contenu HTML de la page CMS sélectionnée).
  - **`cmstab/views/front/tabcontents.tpl`**

    - **Objectif :** Ce template est pour la compatibilité PrestaShop 1.7, 8.x et 9.x. Il est rendu lorsque le « Type d'onglet » est défini sur « PrestaShop 1.7 / 8.x / 9.x ». Il génère la structure complète de l'onglet, y compris l'en-tête de l'onglet et son contenu, comme prévu par le hook `displayProductExtraContent`.
    - **Hook :** `displayProductExtraContent` (standard PrestaShop 1.7+)
    - **Variables :**
      - `$cmstab_title` : Le titre de la page CMS sélectionnée.
      - `$cmstab_content` : Le contenu HTML de la page CMS sélectionnée.
      - `$cmstab_id` : Un ID unique pour l'onglet, dérivé de l'ID de la page CMS.
  - **`cmstab/views/front/tabcontents16.tpl`**

    - **Objectif :** Ce template semble être une version redondante ou alternative de `tab16.tpl` ou `tabcontents.tpl`, probablement pour des scénarios 1.6 spécifiques ou une implémentation plus ancienne. Compte tenu de la logique actuelle du module, `tabcontents.tpl` est utilisé pour 1.7+ et `tab.tpl`/`tab16.tpl` pour 1.6. Les développeurs devraient principalement se concentrer sur `tabcontents.tpl` pour les versions modernes de PrestaShop.

### 4.7 Schéma de la base de données et carte des hooks

- **Tables de base de données** :

  - Ce module ne crée aucune table de base de données personnalisée.
  - Il stocke ses paramètres de configuration dans la table `ps_configuration` de PrestaShop :
    - `CMSTAB_ID` : Stocke l'ID de la page CMS sélectionnée.
    - `CMSTAB_TYPE` : Stocke le type d'onglet sélectionné (par exemple, '17' pour PrestaShop 1.7+, '16' pour PrestaShop 1.6).
    - `MYPRESTA_UPDATES` : Stocke le paramètre pour les mises à jour en direct.
- **Table des hooks enregistrés** :

| Nom du hook | Moment d'exécution | Objectif technique |
| --- | --- | --- |
| `displayHeader` | Dans la section `<head>` de chaque page. | Utilisé par le module pour enregistrer son JavaScript pour les mises à jour en direct dans le back office. |
| `displayBackOfficeHeader` | Dans la section `<head>` de chaque page du back office. | Utilisé par le module pour enregistrer son JavaScript pour les mises à jour en direct dans le back office. |
| `displayProductExtraContent` | Sur les pages produit, pour ajouter de nouveaux onglets (PrestaShop 1.7+). | Hook principal pour le rendu de l'onglet CMS et de son contenu sur les versions modernes de PrestaShop. |
| `productTab` | Sur les pages produit, pour ajouter de nouveaux en-têtes d'onglet (PrestaShop 1.6). | Utilisé pour la rétrocompatibilité pour rendre l'en-tête de l'onglet sur PrestaShop 1.6. |
| `productTabContent` | Sur les pages produit, pour ajouter du nouveau contenu d'onglet (PrestaShop 1.6). | Utilisé pour la rétrocompatibilité pour rendre le contenu de l'onglet sur PrestaShop 1.6. |
| `actionAdminControllerSetMedia` | Lorsqu'un contrôleur d'administration définit ses ressources média. | Utilisé par le module pour enregistrer son JavaScript pour les mises à jour en direct dans le back office. |

## 5. Support officiel et mises à jour

Pour les dernières mises à jour du module, les corrections de bugs et le support professionnel, veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu/my-account/orders/). Notre équipe est dédiée à fournir une assistance rapide et à assurer la performance optimale de vos modules.
