---
title: "Zoom sur les images dans la liste de produits du back-office - Manuel du Marchand et Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop 'Zoom sur les images dans la liste de produits du back-office' par MyPresta.eu."
sidebar:
  label: "Zoom sur les images dans la liste de produits du back-office - Manuel du Marchand et Guide de Configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Zoom images on product list in back office sur MyPresta.eu](https://mypresta.eu/modules/administration-tools/zoom-images-on-product-list-in-back-office.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/back-office-tools/zoom-images-on-product-list-in-back-office/)
>
> ---


# Zoom sur les images dans la liste de produits du back-office

## 1. Exigences et compatibilité

- **Versions de PrestaShop prises en charge** : PrestaShop 1.6.x, 1.7.x
- **Compatibilité PHP** : PHP 5.6 - 8.5
- **Exigences d'hébergement** : Les extensions PHP standard (cURL, JSON, OpenSSL) sont généralement suffisantes. Aucune configuration spéciale du serveur n'est nécessaire.

## 2. Guide de configuration complet (chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

Après l'installation, cliquez sur « Configurer » à côté du nom du module. Vous serez dirigé vers son écran de configuration principal.

Ce module a une configuration très simple, consistant généralement en un seul interrupteur pour activer ou désactiver sa fonctionnalité.

- **Activer le zoom sur la liste de produits :**
  - **Ce que fait ce paramètre :** C'est l'interrupteur principal du module. Il contrôle si la fonction de zoom d'image est active ou inactive dans votre liste de produits du Back Office.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé (OUI) :* Lorsque vous naviguez vers **Catalogue > Produits** dans votre Back Office, survoler n'importe quelle miniature d'image de produit dans la liste affichera une version plus grande et zoomée de cette image.
    - *Lorsqu'il est désactivé (NON) :* La fonctionnalité de zoom sera désactivée. Survoler les images de produits n'aura aucun effet spécial, et vous verrez les miniatures standard.
  - **Valeur recommandée :** OUI
  - **Scénario/exemple pour le marchand :** Si vous souhaitez utiliser la fonction de zoom pratique pour vérifier rapidement les images de produits, assurez-vous que ce paramètre est défini sur « OUI ». Si vous constatez qu'il interfère avec une autre personnalisation du Back Office ou si vous préférez simplement ne pas l'utiliser, définissez-le sur « NON ».

### 2.2 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Valeur par défaut / Recommandée | Objectif et impact |
| --- | --- | --- | --- |
| Configuration du module | Activer le zoom sur la liste de produits | OUI | Active ou désactive la fonction de zoom d'image sur la liste de produits du Back Office. |

## 3. Dépannage pour les marchands et questions fréquemment posées (FAQ)

**Q : J'ai activé le module, mais le zoom ne fonctionne pas sur ma liste de produits. Que dois-je faire ?**
R :

1. **Vider le cache :** Allez dans **Paramètres avancés > Performances** dans votre Back Office et cliquez sur « Vider le cache » (ou « Vider le cache Smarty » dans les versions plus anciennes). Parfois, le cache de PrestaShop peut empêcher le chargement de nouveaux JavaScript.
2. **Vérifier la console du navigateur :** Ouvrez les outils de développement de votre navigateur (généralement F12) et recherchez les erreurs dans l'onglet « Console ». Cela pourrait indiquer un conflit avec un autre module ou thème.
3. **Conflits de modules :** Désactivez temporairement les autres modules qui modifient la liste de produits du Back Office (le cas échéant) pour voir s'il y a un conflit.
4. **Surcharges de thème :** Si vous utilisez un thème de Back Office fortement personnalisé, il pourrait surcharger la structure standard de la liste de produits, empêchant le module d'injecter son JavaScript. Contactez le développeur de votre thème ou le support MyPresta.eu.

**Q : L'image zoomée apparaît, mais elle semble floue ou pixelisée.**
R : Le module affiche l'image que PrestaShop fournit pour la liste de produits. Si l'image originale téléchargée pour ce produit est de faible résolution, la version zoomée apparaîtra également floue. Assurez-vous de télécharger des images haute résolution pour vos produits.

**Q : Ce module ralentit-il mon Back Office ?**
R : Non, le module est très léger. Il ne charge qu'une petite bibliothèque JavaScript et l'applique lorsque vous survolez une image. Il n'effectue pas d'opérations lourdes ou de requêtes de base de données qui auraient un impact sur les performances.

**Q : Puis-je personnaliser la taille de la boîte de zoom ou le niveau de zoom ?**
R : Le module utilise un outil standard « elevateZoom », qui a des comportements par défaut. Bien que le module lui-même n'offre pas d'options de configuration pour ces aspects visuels spécifiques, un développeur pourrait potentiellement modifier le fichier `zplb.js` pour ajuster ces paramètres. Cela nécessiterait un codage personnalisé.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

Cette section est strictement destinée aux développeurs, aux webmasters de boutiques et aux agences techniques qui maintiennent ou étendent la boutique.

### 4.1 Vue d'ensemble de l'architecture

Le module « Zoom sur les images dans la liste de produits du back-office » (`zplb`) est un module PrestaShop simple mais efficace, principalement conçu pour injecter du JavaScript côté client dans la liste de produits du Back Office. Il tire parti du système de hooks de PrestaShop pour charger ses ressources et s'appuie sur une bibliothèque JavaScript tierce (elevateZoom, bien qu'intégrée dans `zplb.js`) pour fournir la fonctionnalité de zoom. Il n'introduit pas de nouvelles tables de base de données ni de logique métier complexe.

### 4.2 Contrôleurs (`controllers/`)

- **Contrôleurs Front-Office** : Aucun. Ce module est exclusivement destiné au Back Office.
- **Contrôleurs Admin Back-Office** : Aucun. La configuration du module est gérée directement dans la méthode `getContent()` du fichier principal du module.

### 4.3 Classes et modèles principaux (`classes/`)

- Aucun. Le module ne définit aucune classe personnalisée ni aucune instance d'`ObjectModel`. Toute la logique est contenue dans le fichier principal `zplb/index.php`.

### 4.4 Ressources JavaScript (`views/js/`)

- `zplb/lib/js/zplb.js`
  - **Portée :** Back-office. Ce script est chargé spécifiquement sur la page de liste de produits du Back Office.
  - **Fonctionnalité :** Ce fichier contient la logique JavaScript principale pour la fonction de zoom. Il inclut ou intègre probablement la bibliothèque « elevateZoom ». Il cible les éléments d'image de produit dans le tableau de la liste de produits du Back Office (par exemple, `img.img-thumbnail` ou des sélecteurs similaires utilisés par la liste de produits de PrestaShop). Il lie les événements mouseover/hover à ces images et initialise la fonctionnalité de zoom, créant la vue agrandie.

### 4.5 Feuilles de style CSS (`views/css/`)

- Aucune. Le module n'inclut aucun fichier CSS personnalisé. Le style de la boîte de zoom est généralement géré par la bibliothèque JavaScript elle-même, souvent en injectant des styles en ligne ou en utilisant un style par défaut minimal qui s'intègre bien avec le Back Office de PrestaShop.

### 4.6 Structure des templates Smarty (`views/templates/`)

- Aucun. Le module n'utilise aucun fichier `.tpl`. Sa fonctionnalité est injectée directement via JavaScript dans la structure HTML existante de la liste de produits du Back Office.

### 4.7 Schéma de la base de données et carte des hooks

- **Tables de base de données** :
  - Le module ne crée aucune table de base de données personnalisée.
  - Il stocke sa configuration (par exemple, le paramètre « Activer le zoom ») dans la table `ps_configuration`, en utilisant une clé comme `ZPLB_ENABLED`.
- **Table des hooks enregistrés** :

| Nom du hook | Moment d'exécution | Objectif technique |
| --- | --- | --- |
| `displayBackOfficeHeader` | Exécuté dans la section `<head>` de chaque page du Back Office. | Utilisé pour charger conditionnellement le script `zplb.js` uniquement lorsque la page actuelle du Back Office est la liste de produits (`AdminProducts`). Cela garantit que le script n'est pas chargé inutilement sur d'autres pages d'administration, optimisant les performances. |

## 5. Support officiel et mises à jour

Pour les dernières mises à jour, corrections de bugs et support officiel du module « Zoom sur les images dans la liste de produits du back-office », veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu). Notre équipe de support est disponible pour vous aider avec toutes les questions ou problèmes que vous pourriez avoir concernant la fonctionnalité et la compatibilité du module.
