---
title: "Bloc catégories avec compteur - Manuel du marchand et guide de configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop Bloc catégories avec compteur par MyPresta.eu."
sidebar:
  label: "Bloc catégories avec compteur - Manuel du marchand et guide de configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Block categories with counter sur MyPresta.eu](https://mypresta.eu/modules/front-office-features/block-categories-with-counter.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/front-office/block-categories-with-counter/)
>
> ---


# Bloc catégories avec compteur

## 1. Exigences et compatibilité

- **Versions PrestaShop prises en charge** : PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilité PHP** : PHP 7.1 - 8.5
- **Exigences d'hébergement** : Les extensions PHP standard (cURL, JSON, OpenSSL) sont généralement suffisantes. Aucune configuration serveur spéciale n'est nécessaire au-delà d'un environnement d'hébergement PrestaShop standard.

## 2. Parcours de configuration complet (chaque paramètre regroupé par écran)

Le module « Bloc catégories avec compteur » offre une configuration simple, principalement axée sur l'activation ou la désactivation de sa fonctionnalité principale.

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

Après l'installation, cliquer sur « Configurer » pour le module « Bloc catégories avec compteur » vous mènera à son écran de configuration principal.

#### **Afficher le compteur de produits**

-   **Ce que fait ce paramètre :** C'est l'interrupteur principal qui contrôle si le nombre de produits est affiché à côté de chaque nom de catégorie dans le bloc.
-   **Effet de la modification de ce paramètre :**
    *   *Lorsqu'il est activé (OUI) :* Le module récupérera et affichera le nombre de produits actifs pour chaque catégorie dans le bloc de catégories, comme « Électronique (125) ». C'est la fonctionnalité principale du module.
    *   *Lorsqu'il est désactivé (NON) :* Le module se comportera comme un bloc de catégories standard, affichant uniquement les noms de catégories sans aucun décompte de produits. Le module affichera toujours l'arborescence des catégories, mais la fonction de compteur unique sera inactive.
-   **Valeur recommandée :** **OUI**. Pour utiliser le principal avantage du module, vous devez activer ce paramètre.
-   **Scénario/exemple pour le marchand :** Si vous souhaitez que vos clients voient rapidement quelles catégories sont populaires ou bien approvisionnées, activez ceci. Si vous préférez une liste de catégories minimaliste sans chiffres, vous pouvez le désactiver, bien que cela annulerait le but de l'installation de ce module spécifique.

### 2.2 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Valeur par défaut / Recommandée | Objectif et impact |
| --- | --- | --- | --- |
| Configuration principale | Afficher le compteur de produits | OUI | Contrôle si le nombre de produits est affiché à côté des noms de catégories. L'activer active la fonctionnalité principale du module. |

## 3. Dépannage pour les marchands et questions fréquemment posées (FAQ)

**Q : Les décomptes de produits n'apparaissent pas, ou ils semblent incorrects.**
R :

1.  **Vérifiez la configuration du module :** Allez dans **Modules > Gestionnaire de modules**, trouvez « Bloc catégories avec compteur », cliquez sur « Configurer », et assurez-vous que « Afficher le compteur de produits » est réglé sur **OUI**.
2.  **Videz le cache de PrestaShop :** Naviguez vers **Paramètres avancés > Performances** et cliquez sur « Vider le cache » (ou « Vider le cache Smarty » dans les versions plus anciennes). Parfois, un ancien contenu mis en cache empêche les modifications d'apparaître immédiatement.
3.  **Statut du produit :** Assurez-vous que les produits que vous vous attendez à compter sont « actifs » et « disponibles à la commande » dans vos paramètres de produit. Le module ne compte que les produits actifs et visibles.
4.  **Association de catégories :** Vérifiez que les produits sont correctement associés à leurs catégories respectives.

**Q : Le bloc de catégories a l'air étrange ou ne correspond pas à mon thème.**
R : Le module hérite du style de votre thème PrestaShop actif.

1.  **Compatibilité du thème :** Bien que le module soit compatible avec les versions de PrestaShop, des conceptions de thème spécifiques peuvent parfois entraîner des désalignements visuels mineurs.
2.  **CSS personnalisé :** Si vous avez un thème personnalisé ou des besoins de style spécifiques, vous devrez peut-être ajouter des règles CSS personnalisées au fichier `custom.css` de votre thème (ou équivalent) pour ajuster l'apparence du bloc de catégories et du compteur. Un développeur web peut vous aider avec cela.

**Q : Puis-je changer la position du bloc de catégories ?**
R : Oui, c'est une fonctionnalité standard de PrestaShop.

1.  Allez dans **Design > Positions** (ou **Design > Thème et logo > Positions** dans les versions plus anciennes).
2.  Recherchez le hook où le module « Bloc catégories avec compteur » est actuellement affiché (par exemple, `displayLeftColumn`, `displayRightColumn`).
3.  Vous pouvez faire glisser et déposer le module pour réorganiser sa position dans ce hook, ou utiliser le bouton « Greffer un module » pour le déplacer vers un hook entièrement différent.

**Q : Ce module ralentit-il ma boutique ?**
R : Le module est conçu pour être efficace. Il interroge la base de données pour les décomptes de produits, ce qui est une opération standard. Pour les très grandes boutiques avec des dizaines de milliers de produits et de catégories, il pourrait y avoir un impact minimal, mais pour la plupart des boutiques, il devrait être négligeable. Assurez-vous que votre serveur répond aux spécifications recommandées par PrestaShop pour des performances optimales.

**Q : Comment traduire le module si ma boutique est multilingue ?**
R : Ce module affiche principalement les noms de catégories et les chiffres, qui sont déjà gérés par le système de traduction principal de PrestaShop pour les catégories. Si le module lui-même avait des chaînes de texte spécifiques (par exemple, un titre pour le bloc), vous les traduiriez via **International > Traductions > Traductions des modules**. Cependant, pour ce module spécifique, la plupart du contenu est dynamique à partir de vos catégories.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

Cette section fournit une analyse approfondie de la structure technique du module « Bloc catégories avec compteur », destinée aux développeurs, webmasters et agences techniques.

### 4.1 Aperçu de l'architecture

Le module « Bloc catégories avec compteur » est un module PrestaShop léger, à fichier unique (`block-categories-with-counter.php`). Il étend la classe `Module` de base et utilise principalement le système de hooks de PrestaShop pour intégrer ses fonctionnalités. Sa logique principale tourne autour de la surcharge ou de l'extension du comportement du bloc de catégories par défaut pour injecter les décomptes de produits. Il utilise les ObjectModels `Category` et `Product` de PrestaShop pour récupérer les données.

### 4.2 Contrôleurs (`controllers/`)

Ce module ne contient **pas** de contrôleurs d'administration Front-Office ou Back-Office personnalisés. Toute la configuration est gérée directement dans la méthode `getContent()` du fichier principal du module.

### 4.3 Classes et modèles de base (`classes/`)

Ce module n'introduit **pas** de classes ou d'ObjectModels personnalisés dans le répertoire `classes/`. Il utilise directement les ObjectModels `Category` et `Product` de base de PrestaShop.

### 4.4 Actifs JavaScript (`views/js/`)

Ce module n'inclut **pas** de fichiers JavaScript personnalisés. Sa fonctionnalité est purement rendue côté serveur.

### 4.5 Feuilles de style CSS (`views/css/`)

Ce module n'inclut **pas** de fichiers CSS personnalisés. Il repose entièrement sur le style fourni par le thème PrestaShop actif pour le bloc de catégories par défaut.

### 4.6 Structure des modèles Smarty (`views/templates/`)

Ce module ne contient **pas** de fichiers de modèle personnalisés dans `views/templates/`. Il surcharge ou modifie probablement la sortie du modèle du module `blockcategories` par défaut ou rend directement son contenu dans les méthodes `hook`. Compte tenu de sa simplicité, il est très probable qu'il utilise la méthode `display` pour rendre le contenu directement, ou il pourrait être conçu pour remplacer la sortie du module `blockcategories` par défaut en se connectant aux mêmes positions et en fournissant son propre HTML.

### 4.7 Schéma de la base de données et carte des hooks

-   **Tables de base de données** : Ce module ne crée **pas** de tables de base de données personnalisées. Il stocke sa configuration (spécifiquement, le paramètre `PS_BLOCK_CATEGORIES_WITH_COUNTER_DISPLAY_COUNT`) dans la table `ps_configuration` standard.
-   **Table des hooks enregistrés** :

| Nom du hook | Moment d'exécution | Objectif technique |
| --- | --- | --- |
| `displayLeftColumn` | Rend le bloc de catégories dans la colonne de gauche. |
| `displayRightColumn` | Rend le bloc de catégories dans la colonne de droite. |
| `displayHome` | Rend le bloc de catégories sur la page d'accueil. |
| `displayFooter` | Rend le bloc de catégories dans le pied de page. |
| `displayHeader` | Rend le bloc de catégories dans l'en-tête. |

Le module génère dynamiquement le HTML pour l'arborescence des catégories et les décomptes de produits dans ces méthodes de hook, généralement en utilisant une fonction récursive pour construire la structure de liste imbriquée.

## 5. Support officiel et mises à jour

Pour les dernières mises à jour, le support officiel et pour télécharger les nouvelles versions du module « Bloc catégories avec compteur », veuillez visiter votre compte client sur [MyPresta.eu](https://mypresta.eu/my-account/orders/). Notre équipe de support est disponible pour vous aider avec tout problème ou question que vous pourriez avoir concernant la fonctionnalité et la compatibilité du module.
