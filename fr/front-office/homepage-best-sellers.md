---
title: "Meilleures Ventes Page d'Accueil - Manuel Marchand & Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop Meilleures Ventes Page d'Accueil par MyPresta.eu."
sidebar:
  label: "Meilleures Ventes Page d'Accueil"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Homepage Best Sellers sur MyPresta.eu](https://mypresta.eu/modules/front-office-features/homepage-best-sellers.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/front-office/homepage-best-sellers/)
>
> ---


# Meilleures Ventes Page d'Accueil

## 1. Exigences et compatibilité

- **Versions de PrestaShop prises en charge** : PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilité PHP** : PHP 7.1 - 8.5
- **Exigences d'hébergement** : Les extensions PHP standard (cURL, JSON, OpenSSL) sont généralement requises pour une boutique PrestaShop et sont suffisantes pour ce module. Aucune configuration de serveur inhabituelle ou avancée n'est nécessaire.

## 2. Guide de configuration complet (Chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

Après avoir installé avec succès le module « Meilleures Ventes Page d'Accueil », naviguez vers **Modules > Gestionnaire de modules**, localisez « Meilleures Ventes Page d'Accueil » et cliquez sur le bouton « Configurer ». Vous serez présenté avec un écran de configuration simple et intuitif.

#### Paramètres et options :

1.  **Nombre de produits à afficher**

    -   **Ce que fait ce paramètre :** C'est le contrôle principal du module. Il détermine exactement combien de vos produits les plus vendus seront présentés dans le bloc « Meilleures Ventes » sur la page d'accueil de votre boutique.
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsqu'activé / défini sur un nombre plus élevé (par exemple, 10) :* Votre page d'accueil présentera plus de produits les plus vendus. Cela peut être excellent pour les boutiques avec une large gamme d'articles populaires, offrant aux clients plus de choix. Cependant, gardez à l'esprit qu'un nombre très élevé pourrait rendre le bloc assez long, nécessitant plus de défilement, ou pourrait potentiellement encombrer la conception de votre page d'accueil en fonction de votre thème.
        -   *Lorsqu'désactivé / défini sur un nombre plus bas (par exemple, 4) :* Moins de produits les plus vendus seront affichés. Cela rend le bloc plus compact et ciblé, ce qui peut être idéal pour les designs minimalistes ou lorsque vous souhaitez mettre en évidence seulement les quelques articles les plus importants.
    -   **Valeur recommandée :** Un bon point de départ est généralement entre **4 et 8 produits**. Cela offre une variété suffisante sans surcharger la page. Vous devriez expérimenter avec différents nombres pour voir ce qui convient le mieux à votre thème PrestaShop spécifique et à la mise en page globale de votre page d'accueil.
    -   **Scénario / exemple pour le marchand :** Si vous gérez une boutique de mode et souhaitez montrer une sélection organisée de vos articles les plus en vogue, vous pourriez le définir sur `4`. Si vous avez une grande boutique d'électronique et souhaitez démontrer l'étendue de vos gadgets populaires, le définir sur `8` ou `10` pourrait être plus efficace.
2.  **Afficher les attributs du produit sur la page du produit** (Clé de configuration : `PS_ATTRIBUTE_CATEGORY_DISPLAY`)

    -   **Ce que fait ce paramètre :** Ce paramètre, s'il est présent dans la configuration du module, contrôle si les attributs du produit (comme la taille, la couleur, le matériau, etc.) sont affichés sur la page du produit lorsque le client consulte un produit. Il est important de noter que `PS_ATTRIBUTE_CATEGORY_DISPLAY` est généralement un paramètre global de base de PrestaShop, non géré habituellement par un module spécifique comme « Meilleures Ventes ». S'il apparaît ici, il s'agit probablement d'un lien de commodité ou d'un module tentant de gérer un paramètre global.
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsqu'activé (par exemple, « Oui » ou coché) :* Les attributs du produit seront clairement visibles sur la page du produit, permettant aux clients de sélectionner des variations spécifiques (par exemple, « Rouge, Taille M »). Ceci est crucial pour les produits avec des options.
        -   *Lorsqu'désactivé (par exemple, « Non » ou décoché) :* Les attributs du produit pourraient être masqués ou non affichés de manière standard sur la page du produit, ce qui pourrait dérouter les clients essayant de sélectionner des variations de produit.
    -   **Valeur recommandée :** **OUI** (ou activé). Pour presque toutes les boutiques de commerce électronique, il est essentiel d'afficher les attributs du produit sur la page du produit pour permettre aux clients de choisir les variations et de prendre des décisions d'achat éclairées.
    -   **Scénario / exemple pour le marchand :** Si vous vendez des chaussures, l'activation de ce paramètre garantit que les clients peuvent sélectionner « Taille 42, Noir » parmi les options de la page du produit de la chaussure. Le désactiver les empêcherait de spécifier la taille ou la couleur souhaitée.

#### Paramètres internes/non configurables :

-   `update_`, `updatev_` : Ce sont des paramètres internes de suivi de version du module et de vérification des mises à jour. Ils ne sont pas destinés à l'interaction du marchand mais garantissent que le module peut vérifier sa version et potentiellement vous informer des mises à jour.

### 2.2 Écrans d'administration dédiés et vues de contrôleur

Le module « Meilleures Ventes Page d'Accueil » est conçu pour la simplicité et l'efficacité. Il n'introduit **pas** d'écrans d'administration dédiés supplémentaires, d'éléments de menu personnalisés ou de vues de contrôleur complexes au-delà de sa page de configuration unique et simple accessible via le Gestionnaire de modules. Toute la gestion se fait directement sur cet écran unique.

### 2.3 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Valeur par défaut / Recommandée | Objectif et impact |
| :---------- | :----------------- | :----------------------------- | :----------------- |
