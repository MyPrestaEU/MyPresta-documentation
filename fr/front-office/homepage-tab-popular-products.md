---
title: "Onglet page d'accueil produits populaires - Manuel du Marchand & Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop Onglet page d'accueil produits populaires par MyPresta.eu."
sidebar:
  label: "Onglet page d'accueil produits populaires - Manuel du Marchand & Guide de Configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Homepage tab popular products sur MyPresta.eu](https://mypresta.eu/modules/front-office-features/homepage-tab-popular-products.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/front-office/homepage-tab-popular-products/)
>
> ---


# Onglet page d'accueil produits populaires

## 1. Exigences et compatibilité

- **Versions de PrestaShop prises en charge** : PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilité PHP** : PHP 7.1 - 8.5
- **Exigences d'hébergement** : Les extensions PHP standard (cURL, JSON, OpenSSL) sont généralement suffisantes. Aucune configuration de serveur spéciale n'est généralement nécessaire au-delà d'un environnement d'hébergement PrestaShop standard.

## 2. Guide de configuration complet (chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

Après l'installation, cliquez sur le bouton « Configurer » à côté du module « Onglet page d'accueil produits populaires » dans le Gestionnaire de modules. Cela vous mènera à son écran de configuration principal.

#### Paramètres généraux

- **Ce que fait ce paramètre :** Ce module se concentre principalement sur l'affichage des produits populaires. L'écran de configuration de ce module est assez simple, incluant souvent les paramètres de notification de mise à jour standard de MyPresta.eu. La fonctionnalité principale d'affichage des « produits populaires » est généralement gérée automatiquement par la logique interne de PrestaShop pour identifier les articles populaires (par exemple, en fonction des ventes, des vues ou d'une combinaison).
- **Effet de la modification de ce paramètre :**
  - **`mypresta_updates` (Activer/Désactiver les notifications de mises à jour MyPresta.eu) :**
    - *Lorsque activé :* Vous recevrez des notifications dans votre back office PrestaShop lorsque de nouvelles versions ou des mises à jour importantes pour les modules MyPresta.eu (y compris celui-ci) seront disponibles. Cela vous aide à maintenir vos modules sécurisés et à jour avec les dernières fonctionnalités et corrections de bugs.
    - *Lorsque désactivé :* Vous ne recevrez pas ces notifications. Vous devrez vérifier manuellement votre compte MyPresta.eu pour les mises à jour.
  - **`update_` et `updatev_` (Paramètres internes de vérification des mises à jour) :** Ce sont généralement des paramètres internes utilisés par les modules MyPresta.eu pour gérer et suivre les vérifications de mises à jour. Ils ne sont généralement pas destinés à une interaction directe avec le marchand.
- **Valeur recommandée :**
  - Pour `mypresta_updates` : **OUI** (Activé). Garder cette option activée garantit que vous êtes toujours informé des mises à jour critiques, améliorant la sécurité et les performances de votre boutique.
  - Pour `update_` et `updatev_` : Laisser par défaut. Ce sont des paramètres internes et ne doivent pas être modifiés.
- **Scénario/exemple pour le marchand :**
  - Vous voulez vous assurer que votre boutique utilise toujours les dernières versions les plus sécurisées de vos modules MyPresta.eu. En activant les notifications de mise à jour, vous verrez une alerte claire dans votre panneau d'administration PrestaShop chaque fois qu'une mise à jour pour « Onglet page d'accueil produits populaires » (ou tout autre module MyPresta.eu) est publiée. Cela vous permet de télécharger et d'installer rapidement la nouvelle version, bénéficiant des améliorations sans avoir à vérifier constamment manuellement.

#### Note importante sur la logique des « Produits populaires » :

Ce module s'appuie sur les mécanismes existants de PrestaShop pour déterminer ce qui constitue un « produit populaire ». Généralement, PrestaShop identifie les produits populaires en fonction des données de vente (produits avec le plus de commandes) ou des vues. Le module lui-même n'offre généralement pas de paramètres spécifiques pour définir la « popularité » (par exemple, « afficher les produits vendus au cours des 30 derniers jours » ou « produits avec X vues »). Il s'appuie sur la fonctionnalité principale de PrestaShop pour cela. Si vous devez influencer les produits qui apparaissent comme « populaires », vous devrez généralement augmenter leurs ventes ou leur visibilité par d'autres efforts marketing.

### 2.2 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Par défaut / Recommandé | Objectif et impact |
| --- | --- | --- | --- |
| Page de configuration du module | Notifications de mises à jour MyPresta.eu | Activé (OUI) | Recevez des alertes pour les mises à jour du module, garantissant la sécurité et les nouvelles fonctionnalités. |
| Page de configuration du module | `update_` | Par défaut | Paramètre interne pour le suivi des mises à jour. Ne pas modifier. |
| Page de configuration du module | `updatev_` | Par défaut | Paramètre interne pour le suivi des mises à jour. Ne pas modifier. |

## 3. Dépannage pour le marchand et questions fréquemment posées (FAQ)

**Q1 : L'onglet « Produits populaires » n'apparaît pas sur ma page d'accueil.**
R1 :

- **Vérifier l'état du module :** Allez dans **Modules > Gestionnaire de modules** et assurez-vous que « Onglet page d'accueil produits populaires » est installé et activé.
- **Vider le cache :** Parfois, le cache de PrestaShop empêche l'affichage de nouveau contenu. Allez dans **Paramètres avancés > Performance** et cliquez sur « Vider le cache » (ou « Vider le cache Smarty » si disponible).
- **Compatibilité du thème :** Bien que le module soit conçu pour PrestaShop 1.7.x, 8.x et 9.x, certains thèmes très personnalisés peuvent nécessiter des ajustements mineurs. Si vider le cache ne fonctionne pas, contactez le développeur de votre thème ou le support MyPresta.eu.
- **Vérification du hook :** Assurez-vous que le hook `displayHome` est actif et rendu par votre thème.

**Q2 : Les produits affichés dans l'onglet « Produits populaires » ne me semblent pas « populaires ».**
R2 :

- **Définition de PrestaShop :** Le module s'appuie sur la logique interne de PrestaShop pour identifier les produits populaires, qui est généralement basée sur le volume des ventes ou les vues des produits. Si votre boutique est nouvelle ou a de faibles ventes, la liste « populaire » pourrait ne pas être aussi dynamique.
- **Actualisation des données :** Assurez-vous que votre boutique dispose de données de vente récentes. La « popularité » est calculée au fil du temps.
- **Cache :** Videz le cache de votre PrestaShop comme décrit dans la Q1.

**Q3 : Puis-je changer le titre de l'onglet (par exemple, de « Produits populaires » à « Nos meilleures ventes ») ?**
R3 :

- Ce module utilise généralement un titre par défaut. Pour le modifier, vous devrez généralement éditer les fichiers de traduction du module ou, dans certains cas, modifier directement le fichier de template.
  - Allez dans **International > Traductions**.
  - Sélectionnez « Traductions des modules installés », votre thème et votre langue.
  - Trouvez le module « Onglet page d'accueil produits populaires » et recherchez la chaîne de titre de l'onglet.
  - Si ce n'est pas traduisible de cette manière, cela pourrait nécessiter une petite modification de code dans `homepagetabs.tpl` (voir Section 7).

**Q4 : Le style des produits dans l'onglet ne correspond pas à mon thème.**
R4 :

- Le module utilise son propre CSS (`homepagetabs.css`). Le CSS de votre thème peut remplacer certains styles, ou les styles du module peuvent entrer en conflit.
- **CSS personnalisé :** La meilleure approche est d'ajouter du CSS personnalisé au fichier `custom.css` de votre thème (ou équivalent) pour remplacer les styles du module et le faire correspondre parfaitement à votre thème. Utilisez les outils de développement de votre navigateur pour inspecter les éléments et identifier les sélecteurs CSS utilisés par le module.

**Q5 : Comment traduire le titre de l'onglet ou d'autres textes du module dans différentes langues ?**
R5 :

- Allez dans **International > Traductions** dans le back office de votre PrestaShop.
- Sélectionnez « Traductions des modules installés », puis choisissez votre thème et la langue que vous souhaitez traduire.
- Trouvez le module « Onglet page d'accueil produits populaires » dans la liste et vous devriez pouvoir modifier les chaînes de texte qui lui sont associées.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

Cette section fournit une analyse approfondie de la structure technique du module « Onglet page d'accueil produits populaires », destinée aux développeurs, webmasters et agences techniques.

### 4.1 Vue d'ensemble de l'architecture

Le module `Onglet page d'accueil produits populaires` (`homepagetabs`) est un module PrestaShop simple, principalement conçu pour étendre le hook `displayHome`. Il suit un modèle standard de type MVC pour les modules PrestaShop, où le fichier principal du module (`homepagetabs.php`) gère l'installation, la désinstallation, la configuration et l'enregistrement des hooks. Le module injecte un onglet personnalisé et son contenu dans la page d'accueil, en tirant parti des mécanismes existants de PrestaShop pour la récupération des « produits populaires ».

### 4.2 Contrôleurs (`controllers/`)

Ce module ne contient aucun contrôleur d'administration Front-Office ou Back-Office personnalisé. Toute la logique est encapsulée dans le fichier principal du module et ses templates et assets associés.

### 4.3 Classes et modèles principaux (`classes/`)

Ce module ne définit aucune classe personnalisée et n'étend pas `ObjectModel`. Il fonctionne en utilisant les fonctionnalités de base de PrestaShop pour la récupération des produits.

### 4.4 Assets JavaScript (`views/js/`)

- **`homepagetabs/views/js/homepagetabs.js`**
  - **Portée :** Front-office.
  - **Objectif :** Ce fichier contient probablement la logique JavaScript pour gérer la fonctionnalité de commutation d'onglets sur la page d'accueil. Il peut écouter les événements de clic sur l'onglet « Produits populaires », afficher/masquer le contenu du produit correspondant, et potentiellement interagir avec d'autres onglets de la page d'accueil pour s'assurer que le contenu d'un seul onglet est visible à la fois. Il peut également inclure une logique pour le comportement réactif ou le chargement paresseux des images de produits dans l'onglet.
  - **Fonctionnalité clé :**
    - Écouteurs d'événements pour les clics sur les onglets.
    - Manipulation du DOM pour basculer la visibilité des listes de produits.
    - S'intègre potentiellement avec le comportement d'onglet par défaut de PrestaShop ou les systèmes d'onglets de thème personnalisés.

### 4.5 Feuilles de style CSS (`views/css/`)

- **`homepagetabs/views/css/homepagetabs.css`**
  - **Portée :** Style client Front-office.
  - **Objectif :** Cette feuille de style définit l'apparence visuelle de l'onglet « Produits populaires » et des listes de produits qu'il contient. Elle garantit que l'onglet est correctement positionné, stylisé et que la grille/liste de produits est présentée de manière ordonnée.
  - **Principaux composants d'interface utilisateur stylisés :**
    - L'en-tête de l'onglet lui-même (par exemple, `.homepagetabs-tab-title`).
    - Le conteneur des produits populaires (par exemple, `.homepagetabs-products-container`).
    - Les éléments de produit individuels dans l'onglet (par exemple, images de produits, noms, prix, boutons).
    - Ajustements réactifs pour différentes tailles d'écran.
  - **Sélecteurs de classe CSS clés pour la surcharge :** Les développeurs peuvent inspecter le HTML généré pour trouver des sélecteurs spécifiques. Les plus courants pourraient inclure :
    - `.homepagetabs-tab`
    - `.homepagetabs-tab-content`
    - `.homepagetabs-product-list`
    - `.homepagetabs-product-item`

### 4.6 Structure des templates Smarty (`views/templates/`)

- **Templates de hook (`views/templates/hook/`)** :
  - **`homepagetabs/views/templates/hook/homepagetabs.tpl`**
    - **Hook :** `displayHome`
    - **Objectif :** C'est le template principal du front-office. Il est responsable du rendu de l'en-tête de l'onglet « Produits populaires » et du conteneur de la liste de produits. Il itérera généralement sur une collection de produits populaires qui lui est transmise par la méthode `hookDisplayHome` du module et rendra chaque produit en utilisant un partiel de liste de produits PrestaShop standard (ou un partiel personnalisé défini dans le module). Ce template est l'endroit où la structure HTML réelle de l'onglet et de son contenu est générée.
- **Templates d'administration (`views/templates/admin/`)** :
  - **`homepagetabs/views/templates/admin/homepagetabs.tpl`**
    - **Objectif :** Ce template rend le formulaire de configuration du module dans le Back Office de PrestaShop. Il affiche les paramètres pour les notifications de mise à jour (`mypresta_updates`) et potentiellement d'autres options spécifiques au module si elles devaient être ajoutées. Il utilise les classes de formulaire d'aide de PrestaShop pour générer les champs de saisie et les boutons d'enregistrement.

### 4.7 Schéma de la base de données et carte des hooks

- **Tables de base de données** : Ce module ne crée aucune table de base de données personnalisée. Il stocke ses paramètres de configuration (comme `mypresta_updates`) dans la table standard `ps_configuration`.
- **Table des hooks enregistrés** :

| Nom du hook | Moment d'exécution | Objectif technique |
| --- | --- | --- |
| `displayHome` | Rend le contenu sur la page d'accueil de la boutique. | Injecte l'onglet « Produits populaires » et son contenu dans la zone principale de la page d'accueil. |
| `displayHeader` | Exécuté dans la section `<head>` de chaque page. | Utilisé pour mettre en file d'attente les fichiers CSS (`homepagetabs.css`) et JavaScript (`homepagetabs.js`) du module, garantissant qu'ils sont chargés correctement pour l'affichage du front-office. |

## 5. Support officiel et mises à jour

Pour les mises à jour officielles, le support technique et toute question concernant le module « Onglet page d'accueil produits populaires », veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu/). Notre équipe de support et nos ressources sont disponibles pour vous aider avec l'installation, la configuration et le dépannage.
