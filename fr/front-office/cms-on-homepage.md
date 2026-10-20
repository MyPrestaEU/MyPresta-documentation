---
title: "CMS sur la page d'accueil - Manuel du Marchand & Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop CMS sur la page d'accueil par MyPresta.eu."
sidebar:
  label: "CMS sur la page d'accueil - Manuel du Marchand & Guide de Configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module CMS on homepage sur MyPresta.eu](https://mypresta.eu/modules/front-office-features/cms-on-homepage.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/front-office/cms-on-homepage/)
>
> ---


# CMS sur la page d'accueil

## 1. Exigences et compatibilité

- **Versions PrestaShop prises en charge** : PrestaShop 9.x
- **Compatibilité PHP** : PHP 7.1 - 8.5 (Toujours étendu à PHP 8.5)
- **Exigences d'hébergement** : Les extensions PHP standard (cURL, JSON, OpenSSL) sont généralement requises pour PrestaShop lui-même, et ce module n'a pas d'exigences spéciales supplémentaires.

## 2. Guide de configuration complet (Chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

Après l'installation, cliquez sur "Configurer" à côté du module "CMS sur la page d'accueil". Vous serez redirigé vers son écran de configuration principal.

#### Sélectionner la page CMS

C'est le paramètre principal du module. Il vous permet de choisir laquelle de vos pages CMS existantes aura son contenu affiché sur la page d'accueil.

-   **Ce que fait ce paramètre :** Ce menu déroulant liste toutes les pages CMS que vous avez créées dans votre boutique PrestaShop (disponibles sous **Paramètres de la boutique > Pages**). Vous sélectionnez l'une de ces pages.
-   **Effet de la modification de ce paramètre :**
    *   *Lorsqu'une page CMS est sélectionnée :* Le contenu de la page CMS choisie sera récupéré et affiché sur la page d'accueil de votre boutique.
    *   *Lorsqu'aucune page CMS n'est sélectionnée (ou si vous changez d'avis) :* Le module n'affichera aucun contenu, ou il affichera le contenu de la page nouvellement sélectionnée.
-   **Valeur recommandée :** Choisissez la page CMS dont vous souhaitez afficher le contenu de manière proéminente sur votre page d'accueil. Il peut s'agir de votre page "À propos de nous", "Informations sur la livraison", "Politique de confidentialité" (si vous souhaitez qu'elle soit très visible), ou une page personnalisée avec du contenu promotionnel.
-   **Scénario / exemple de marchand :** Vous avez une page CMS intitulée "Notre histoire" qui détaille l'histoire et les valeurs de votre marque. En sélectionnant "Notre histoire" ici, chaque visiteur de votre page d'accueil verra immédiatement ce contenu, ce qui contribuera à établir un lien et une confiance avec la marque.

Après avoir fait votre sélection, n'oubliez pas de cliquer sur le bouton **"Enregistrer"** pour appliquer vos modifications.

### 2.2 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Valeur par défaut / Recommandée | Objectif et impact |
| --- | --- | --- | --- |
| Page de configuration du module | Sélectionner la page CMS | (Aucune sélectionnée initialement) | Choisir le contenu de la page CMS qui apparaît sur la page d'accueil. |

## 3. Dépannage pour les marchands et questions fréquemment posées (FAQ)

**Q : J'ai sélectionné une page CMS, mais rien n'apparaît sur ma page d'accueil. Qu'est-ce qui ne va pas ?**
R :

1.  **Vider le cache :** Allez dans **Paramètres avancés > Performances** dans votre Back Office et cliquez sur "Vider le cache" (ou "Vider le cache Smarty" dans les anciennes versions). Parfois, PrestaShop a besoin d'une actualisation du cache pour afficher le nouveau contenu.
2.  **Vérifier le statut de la page CMS :** Assurez-vous que la page CMS sélectionnée est active et visible dans votre boutique (allez dans **Paramètres de la boutique > Pages** et vérifiez son statut).
3.  **Compatibilité du thème :** Bien que le module utilise des hooks PrestaShop standard, certains thèmes très personnalisés peuvent remplacer ces hooks ou avoir des exigences de mise en page spécifiques. Si vider le cache ne résout pas le problème, contactez le développeur de votre thème ou le support MyPresta.eu.

**Q : Le contenu CMS s'affiche, mais il n'a pas l'air correct (par exemple, mauvaises polices, couleurs, mise en page).**
R : Le module injecte simplement le contenu de votre page CMS. Le style (polices, couleurs, espacement) est généralement contrôlé par le CSS de votre thème PrestaShop.

1.  **Vérifier le contenu de la page CMS :** Assurez-vous qu'il n'y a pas de HTML personnalisé ou de style en ligne en conflit dans le contenu de la page CMS elle-même qui pourrait causer des problèmes.
2.  **Personnalisation du thème :** Vous devrez peut-être ajouter du CSS personnalisé à votre thème pour mieux intégrer visuellement le contenu CMS. Un développeur web peut vous aider.

**Q : Puis-je afficher plusieurs pages CMS sur la page d'accueil ?**
R : Ce module spécifique est conçu pour afficher *une* page CMS sélectionnée. Si vous avez besoin d'afficher plusieurs blocs distincts de contenu CMS, vous devrez soit les combiner en une seule page CMS, soit rechercher un module de gestion de contenu plus avancé.

**Q : Comment traduire le contenu CMS pour différentes langues ?**
R : Le contenu de votre page CMS est géré directement dans la fonctionnalité CMS de base de PrestaShop. Lorsque vous modifiez une page CMS (**Paramètres de la boutique > Pages**), vous pouvez sélectionner la langue pour modifier son contenu. Le module affichera automatiquement le contenu dans la langue actuellement sélectionnée par le client sur votre boutique.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

### 4.1 Vue d'ensemble de l'architecture

Le module "CMS sur la page d'accueil" est un module PrestaShop léger principalement conçu pour injecter le contenu de pages CMS existantes dans divers hooks de la page d'accueil. Il suit une structure de module PrestaShop standard, tirant parti de la classe `Module` et de ses méthodes `install()` et `uninstall()` pour la configuration et le nettoyage, et `getContent()` pour la configuration du back-office. L'affichage front-office est entièrement géré par l'enregistrement des hooks et les templates Smarty. Il n'introduit pas de contrôleurs, de modèles ou de JavaScript complexes personnalisés.

### 4.2 Contrôleurs (`controllers/`)

-   **Contrôleurs Front-Office** : Aucun. Tout le rendu du contenu front-office est géré directement via les hooks enregistrés dans le fichier principal du module.
-   **Contrôleurs d'administration Back-Office** : Aucun. La configuration du module est gérée via la méthode `getContent()` de la classe principale du module.

### 4.3 Classes et modèles principaux (`classes/`)

-   Aucun. Le module s'appuie sur les classes `CMS` et `Configuration` de PrestaShop.

### 4.4 Actifs JavaScript (`views/js/`)

-   Aucun. Le module n'inclut aucun JavaScript personnalisé.

### 4.5 Feuilles de style CSS (`views/css/`)

-   Aucun. Le module n'inclut aucun CSS personnalisé. Le contenu CMS affiché hérite du style du thème PrestaShop actif.

### 4.6 Structure des templates Smarty (`views/templates/`)

-   **`cmshomepage/views/templates/hook/cmshomepage.tpl`**

    -   **Objectif :** C'est le template principal responsable du rendu du contenu réel de la page CMS sélectionnée. Il est conçu pour être accroché à `displayHome` ou `displayHomeTabContent` pour une sortie de contenu directe.
    -   **Variables :**
        -   `{$cms_content}` : Le contenu HTML de la page CMS sélectionnée, récupéré et assigné par le module.
    -   **Sortie :** Rend le contenu HTML brut de la page CMS.
-   **`cmshomepage/views/templates/hook/tab.tpl`**

    -   **Objectif :** Ce template est utilisé lorsque le module est accroché à `displayHomeTab`. Il génère le HTML pour un en-tête d'onglet qui, lorsqu'il est cliqué, révèle le contenu CMS.
    -   **Variables :**
        -   `{$tab_name}` : Le titre de l'onglet, généralement dérivé du titre de la page CMS.
        -   `{$tab_id}` : Un ID unique pour l'onglet, utilisé pour le lier à son panneau de contenu correspondant.
    -   **Sortie :** Un élément `<li>` contenant une balise `<a>`, adapté à l'inclusion dans une structure de navigation par onglets.
-   **`cmshomepage/views/templates/hook/tabContents.tpl`**

    -   **Objectif :** Ce template est utilisé lorsque le module est accroché à `displayHomeTabContent`. Il génère le HTML pour le panneau de contenu associé à un onglet.
    -   **Variables :**
        -   `{$tab_id}` : L'ID unique correspondant à l'ID de `tab.tpl`.
        -   `{$cms_content}` : Le contenu HTML de la page CMS sélectionnée.
    -   **Sortie :** Un élément `<div>` avec le contenu de l'onglet, généralement masqué par défaut et révélé via JavaScript lorsque son onglet correspondant est cliqué.

### 4.7 Schéma de la base de données et carte des hooks

-   **Tables de la base de données** :

    -   Le module ne crée aucune table de base de données personnalisée.
    -   Il stocke sa configuration dans la table `ps_configuration` en utilisant la clé `CMSHOMEPAGE_ID_CMS` pour stocker l'ID de la page CMS sélectionnée.
-   **Table des hooks enregistrés** :

| Nom du hook | Moment d'exécution | Objectif technique |
| --- | --- | --- |
| `displayHomeTabContent` | Rend le contenu dans un onglet de la page d'accueil. | Affiche le `cmshomepage.tpl` ou `tabContents.tpl` avec le contenu CMS. |
| `displayHomeTab` | Rend un en-tête d'onglet sur la page d'accueil. | Affiche le `tab.tpl` avec le titre de la page CMS comme nom d'onglet. |
| `displayHome` | Rend le contenu directement dans la zone principale de la page d'accueil. | Affiche le `cmshomepage.tpl` avec le contenu CMS. |

La méthode `install()` du module enregistre ces hooks. Les méthodes `hookDisplayHome()`, `hookDisplayHomeTab()` et `hookDisplayHomeTabContent()` dans `cmshomepage.php` sont responsables de la récupération du contenu de la page CMS sélectionnée et du rendu du template approprié.

### 4.8 Clés de configuration

Le module utilise les clés de configuration suivantes dans `ps_configuration` :

-   `CMSHOMEPAGE_ID_CMS` : Stocke l'`id_cms` de la page CMS sélectionnée par le marchand pour être affichée sur la page d'accueil.

## 5. Support officiel et mises à jour

Pour les mises à jour officielles, les corrections de bugs et le support développeur dédié, veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu/). Assurez-vous d'utiliser la dernière version du module pour des performances optimales et une compatibilité avec votre boutique PrestaShop.
