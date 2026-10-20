---
title: "Dupliquer une page CMS - Manuel du Marchand et Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop Dupliquer une page CMS par MyPresta.eu."
sidebar:
  label: "Dupliquer une page CMS - Manuel du Marchand et Guide de Configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Duplicate CMS page sur MyPresta.eu](https://mypresta.eu/modules/administration-tools/duplicate-cms-page.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/back-office-tools/duplicate-cms-page/)
>
> ---


# Dupliquer une page CMS

## 1. Exigences et compatibilité

- **Versions PrestaShop prises en charge** : PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilité PHP** : PHP 7.1 - 8.5
- **Exigences d'hébergement** : Les extensions PHP standard (cURL, JSON, OpenSSL) sont généralement requises pour PrestaShop lui-même et sont suffisantes pour ce module.

## 2. Guide de configuration complet (chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

Après l'installation, cliquez sur « Configurer » à côté du module « Dupliquer une page CMS » dans le Gestionnaire de modules. Cela vous mènera à l'écran de configuration principal du module.

#### Paramètres généraux

- **Mises à jour MyPresta.eu (mypresta\_updates)**

  - **Ce que fait ce paramètre :** Ce paramètre contrôle si le module vérifie les mises à jour depuis MyPresta.eu. Le fait de le laisser activé vous assure d'être informé des nouvelles versions, des corrections de bugs et des améliorations de fonctionnalités.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé :* Le module vérifiera périodiquement les mises à jour disponibles. Si une mise à jour est trouvée, une notification pourrait apparaître dans votre Back Office PrestaShop.
    - *Lorsqu'il est désactivé :* Le module ne vérifiera pas les mises à jour et vous ne serez pas informé automatiquement des nouvelles versions. Vous devrez vérifier manuellement les mises à jour sur MyPresta.eu.
  - **Valeur recommandée :** **OUI** (Activé).
  - **Scénario / exemple marchand :** Vous voulez vous assurer que votre module est toujours à jour avec les derniers correctifs de sécurité et fonctionnalités sans avoir à vérifier manuellement le site web MyPresta.eu chaque semaine.
- **Mise à jour (update\_)**

  - **Ce que fait ce paramètre :** Il s'agit généralement d'un champ d'affichage ou d'un bouton lié à la vérification des mises à jour, affichant l'état actuel ou permettant une vérification manuelle. Il fonctionne en conjonction avec le paramètre « Mises à jour MyPresta.eu ».
  - **Effet de la modification de ce paramètre :** Cliquer sur un bouton ici (s'il est présent) lancerait une vérification immédiate des mises à jour.
  - **Valeur recommandée :** N/A (Basé sur l'interaction).
  - **Scénario / exemple marchand :** Après avoir activé « Mises à jour MyPresta.eu », vous pourriez cliquer ici pour voir immédiatement si une nouvelle version est disponible, plutôt que d'attendre la prochaine vérification automatique.
- **Version de mise à jour (updatev\_)**

  - **Ce que fait ce paramètre :** Ce champ affiche généralement la dernière version disponible du module telle que détectée par le vérificateur de mises à jour.
  - **Effet de la modification de ce paramètre :** Il s'agit d'un champ d'affichage uniquement et ne peut pas être modifié directement. Il fournit des informations sur la dernière version.
  - **Valeur recommandée :** N/A (Affichage uniquement).
  - **Scénario / exemple marchand :** Vous voyez « 1.2.3 » ici, indiquant qu'une version plus récente que votre version actuelle (par exemple, 1.2.2) est disponible.
- **Dernière version (dupcms\_LATEST)**

  - **Ce que fait ce paramètre :** Similaire à « Version de mise à jour », ce champ affiche la version la plus récente du module disponible.
  - **Effet de la modification de ce paramètre :** Il s'agit d'un champ d'affichage uniquement.
  - **Valeur recommandée :** N/A (Affichage uniquement).
  - **Scénario / exemple marchand :** Vous pouvez rapidement vérifier si votre module installé est le plus récent en comparant cette valeur à votre version installée.
- **Miniatures (dupcms\_MINIATURES)**

  - **Ce que fait ce paramètre :** Ce paramètre contrôle probablement si des images miniatures ou des icônes sont affichées dans l'interface du module, éventuellement liées au vérificateur de mises à jour ou à d'autres éléments visuels dans le panneau d'administration du module.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé :* Vous pourriez voir de petites icônes ou images dans la configuration du module ou les notifications de mise à jour.
    - *Lorsqu'il est désactivé :* Ces éléments visuels seraient masqués, ce qui donnerait une interface plus textuelle.
  - **Valeur recommandée :** **OUI** (Activé).
  - **Scénario / exemple marchand :** Vous préférez une interface plus riche visuellement dans votre Back Office, vous laissez donc ceci activé pour voir toutes les icônes pertinentes.
- **ID Catégorie CMS (dupcms\_ID\_CMSCAT)**

  - **Ce que fait ce paramètre :** Ce paramètre est crucial pour la fonctionnalité principale du module. Il vous permet de sélectionner une catégorie CMS par défaut où les pages CMS dupliquées seront placées.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'une catégorie spécifique est sélectionnée :* Toutes les nouvelles pages CMS dupliquées seront automatiquement attribuées à cette catégorie. Cela aide à organiser votre contenu.
    - *Lorsqu'aucune catégorie n'est sélectionnée (ou par défaut) :* Le module pourrait utiliser par défaut la même catégorie que la page originale, ou une catégorie racine, selon sa logique interne. La définition d'une catégorie spécifique vous donne plus de contrôle.
  - **Valeur recommandée :** Sélectionnez une catégorie par défaut logique, telle que « Informations » ou une catégorie spécifique que vous utilisez pour les nouvelles pages.
  - **Scénario / exemple marchand :** Vous dupliquez fréquemment des pages de « Mentions légales » pour différentes régions. Vous pouvez définir ceci sur votre catégorie CMS « Pages légales » afin que toutes les nouvelles duplications y atterrissent automatiquement, ce qui les rend plus faciles à trouver et à gérer.

#### Comment utiliser la fonction de duplication

L'action de duplication réelle se produit sur la liste standard des pages CMS de PrestaShop :

1. Naviguez vers **Améliorer > Design > Pages** dans votre Back Office PrestaShop.
2. Vous verrez une liste de vos pages CMS existantes.
3. Localisez la page CMS que vous souhaitez dupliquer.
4. Dans la colonne « Actions » (généralement représentée par trois points ou un menu déroulant) pour cette page CMS spécifique, vous trouverez une nouvelle option ajoutée par ce module : **« Dupliquer »** (ou une icône/texte similaire).
5. Cliquez sur « Dupliquer ».
6. Le module créera une copie exacte de la page, y compris son contenu, ses méta-informations, son URL conviviale et son statut actif. La nouvelle page aura généralement un nom comme « Copie de [Nom de la page originale] » ou similaire, que vous pourrez ensuite modifier.
7. La page dupliquée sera placée dans la catégorie CMS que vous avez sélectionnée dans la configuration du module (si `dupcms_ID_CMSCAT` est défini) ou dans la même catégorie que l'originale.
8. Vous pouvez ensuite modifier la page nouvellement dupliquée pour changer son titre, son contenu, son URL et d'autres paramètres selon vos besoins.

### 2.2 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Par défaut / Recommandé | Objectif et impact |
| --- | --- | --- | --- |
| Configuration du module | Mises à jour MyPresta.eu | OUI | Active les vérifications automatiques des mises à jour du module. |
| Configuration du module | Mise à jour | N/A (Bouton) | Lance une vérification manuelle des mises à jour du module. |
| Configuration du module | Version de mise à jour | N/A (Affichage) | Affiche la dernière version disponible du module. |
| Configuration du module | Dernière version | N/A (Affichage) | Affiche la version la plus récente du module détectée. |
| Configuration du module | Miniatures | OUI | Contrôle l'affichage des éléments visuels/icônes dans l'interface du module. |
| Configuration du module | ID Catégorie CMS | Sélectionner une catégorie | Définit la catégorie CMS par défaut pour les pages dupliquées. |
| Liste des pages CMS (Design > Pages) | Action Dupliquer | N/A (Bouton) | Crée une copie exacte de la page CMS sélectionnée. |

## 3. Dépannage marchand et questions fréquemment posées (FAQ)

**Q : J'ai dupliqué une page, mais je ne la trouve pas.**
R : Vérifiez la catégorie CMS que vous avez sélectionnée dans la configuration du module (`dupcms_ID_CMSCAT`). Si vous n'en avez pas défini, elle pourrait se trouver dans la même catégorie que la page originale ou dans la catégorie CMS racine. Assurez-vous également de rechercher « Copie de [Nom de la page originale] » ou similaire, car le module ajoute un préfixe au titre de la page dupliquée.

**Q : La page dupliquée a la même URL conviviale que l'originale. Est-ce un problème ?**
R : Oui, cela peut entraîner des conflits et des problèmes de référencement. Après avoir dupliqué une page, **modifiez toujours la nouvelle page immédiatement** et changez son URL conviviale (également appelée « Réécriture d'URL » ou « Slug ») pour quelque chose d'unique et de descriptif pour le nouveau contenu. PrestaShop ajoute généralement un numéro (par exemple, `-1`) à l'URL, mais il est préférable de la personnaliser vous-même.

**Q : Je ne vois pas l'option « Dupliquer » dans la liste des pages CMS.**
R :

1. Allez dans **Modules > Gestionnaire de modules** et assurez-vous que le module « Dupliquer une page CMS » est installé et activé.
2. Videz votre cache PrestaShop : Allez dans **Paramètres avancés > Performances**, faites défiler vers le bas et cliquez sur « Vider le cache ».
3. Si cela n'apparaît toujours pas, essayez de réinstaller le module (après avoir sauvegardé votre boutique). Si le problème persiste, contactez le support MyPresta.eu.

**Q : Ce module duplique-t-il les images et les fichiers liés dans le contenu de la page CMS ?**
R : Oui, le module duplique l'intégralité du contenu HTML de la page. Si vos images sont liées à l'aide de chemins relatifs dans le contenu, elles continueront de fonctionner. Si elles sont téléchargées directement via l'éditeur de texte enrichi, les références seront copiées. Cependant, le module ne duplique pas les *fichiers* image réels sur votre serveur ; il duplique les *références* à ceux-ci. C'est généralement le comportement souhaité.

**Q : Puis-je dupliquer une catégorie CMS ?**
R : Non, ce module est spécifiquement conçu pour dupliquer des *pages* CMS individuelles, et non des *catégories* CMS entières.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

Cette section fournit un aperçu technique pour les développeurs et les webmasters souhaitant comprendre, déboguer ou étendre le module « Dupliquer une page CMS ».

### 4.1 Aperçu de l'architecture

Le module « Dupliquer une page CMS » est un module PrestaShop léger principalement axé sur l'extension de la fonctionnalité du `AdminCmsController` existant. Il utilise le système de hooks de PrestaShop (`actionAdminControllerSetMedia`) pour injecter du JavaScript qui modifie le tableau de liste des pages CMS par défaut, ajoutant une action « Dupliquer ». La logique de duplication principale est gérée par le fichier `dupcms.php` du module, qui intercepte les requêtes AJAX pour effectuer les opérations de base de données requises pour copier les données de la page CMS. Il n'introduit pas de nouvelles tables de base de données ou de modèles d'objets complexes, s'appuyant plutôt sur la manipulation directe des tables `ps_cms` et `ps_cms_lang` existantes.

### 4.2 Contrôleurs (`controllers/`)

Ce module n'introduit aucun contrôleur front-office ou back-office personnalisé. Sa fonctionnalité est intégrée au `AdminCmsController` existant via des hooks et AJAX.

### 4.3 Classes et modèles principaux (`classes/`)

Ce module n'introduit aucune classe personnalisée ou définition de `ObjectModel`. Il interagit directement avec les classes principales de PrestaShop `CMS` et `CMSCategory` et leurs tables de base de données associées.

### 4.4 Actifs JavaScript (`views/js/`)

- **`dupcms/views/js/dupcms.js`**
  - **Portée :** Back-office (spécifiquement, la page `AdminCms`).
  - **Responsabilité :**
    - Ce script est injecté dans la page `AdminCmsController` (Améliorer > Design > Pages) via le hook `actionAdminControllerSetMedia`.
    - Il attend que le DOM soit prêt.
    - Il identifie la colonne « Actions » dans le tableau de liste des pages CMS.
    - Pour chaque ligne de page CMS, il ajoute dynamiquement un nouveau bouton ou lien d'action « Dupliquer » au menu déroulant d'actions existant.
    - Il attache un écouteur d'événements (par exemple, `click`) à ces éléments « Dupliquer » nouvellement ajoutés.
    - Lorsqu'une action « Dupliquer » est cliquée, il extrait l'`id_cms` de la page à dupliquer.
    - Il envoie ensuite une requête AJAX au fichier PHP principal du module (`dupcms/dupcms.php`) avec l'`id_cms` et un paramètre d'action (par exemple, `action=duplicateCms`).
    - Il gère la réponse AJAX, affichant généralement un message de succès ou d'erreur et rafraîchissant potentiellement la liste des pages CMS pour afficher la page nouvellement dupliquée.
    - Il peut également inclure une logique pour les notifications de mise à jour ou d'autres éléments d'interface utilisateur dynamiques liés à la configuration du module.

### 4.5 Feuilles de style CSS (`views/css/`)

- **`dupcms/views/css/dupcms.css`**
  - **Portée :** Back-office (spécifiquement, la page `AdminCms`).
  - **Responsabilité :**
    - Fournit un style pour le lien/bouton d'action « Dupliquer » ajouté dynamiquement pour s'assurer qu'il s'intègre visuellement au thème du Back Office de PrestaShop.
    - Peut inclure des styles pour toutes les notifications ou éléments d'interface utilisateur spécifiques au module dans le contexte `AdminCms`.
    - Sélecteurs de classe CSS clés que les développeurs peuvent remplacer : Recherchez des classes comme `.dupcms-duplicate-action` ou similaires dans le HTML injecté pour personnaliser son apparence.

### 4.6 Structure des modèles Smarty (`views/templates/`)

Ce module n'utilise aucun fichier de modèle Smarty personnalisé (`.tpl`). Toutes ses modifications d'interface utilisateur dans le Back Office sont effectuées dynamiquement via JavaScript.

### 4.7 Schéma de base de données et carte des hooks

- **Tables de base de données** :

  - Le module ne crée aucune nouvelle table de base de données personnalisée.
  - Il opère sur les tables PrestaShop existantes :
    - `ps_cms` : Stocke les informations générales des pages CMS (statut actif, position, etc.).
    - `ps_cms_lang` : Stocke le contenu des pages CMS spécifiques à la langue (titre, méta description, contenu, URL conviviale).
    - `ps_cms_shop` : Lie les pages CMS à des boutiques spécifiques dans un environnement multi-boutiques.
    - `ps_configuration` : Stocke les paramètres de configuration du module (par exemple, `dupcms_ID_CMSCAT`, `mypresta_updates`).
- **Table des hooks enregistrés** :

| Nom du hook | Moment d'exécution | Objectif technique |
| --- | --- | --- |
| `actionAdminControllerSetMedia` | Exécuté lorsqu'un contrôleur du Back Office définit ses médias (JS/CSS). | C'est le hook principal utilisé par le module. Il injecte `dupcms.js` et `dupcms.css` dans la page `AdminCmsController`, permettant au module de modifier la liste des pages CMS et d'ajouter l'action « Dupliquer ». |

## 5. Support officiel et mises à jour

Pour le support officiel, les mises à jour et pour télécharger la dernière version du module « Dupliquer une page CMS », veuillez vous connecter à votre compte client sur [MyPresta.eu](https://mypresta.eu/my-account/orders/). Notre équipe de support est disponible pour vous aider avec tout problème ou question que vous pourriez avoir concernant la fonctionnalité du module.
