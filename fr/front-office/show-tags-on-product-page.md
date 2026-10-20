---
title: "Afficher les tags sur la page produit - Manuel du Marchand & Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop 'Afficher les tags sur la page produit' par MyPresta.eu."
sidebar:
  label: "Afficher les tags sur la page produit - Manuel du Marchand & Guide de Configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Show tags on product page sur MyPresta.eu](https://mypresta.eu/modules/front-office-features/show-tags-on-product-page.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/front-office/show-tags-on-product-page/)
>
> ---


# Afficher les tags sur la page produit

## 1. Exigences et compatibilité

- **Versions PrestaShop prises en charge** : PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilité PHP** : PHP 5.6 - 8.5
- **Exigences d'hébergement** : Extensions PHP standard (cURL, JSON, OpenSSL) généralement présentes sur tout environnement d'hébergement PrestaShop moderne.

## 2. Guide de configuration complet (Chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

Ce module dispose d'une page de configuration simple, vous permettant d'activer ou de désactiver rapidement sa fonctionnalité et de choisir où les tags apparaîtront sur vos pages produit.

**Accès :** Naviguez vers **Modules > Gestionnaire de modules**, recherchez "Afficher les tags sur la page produit", et cliquez sur "Configurer".

#### **Activer / Désactiver le module**

-   **Ce que fait ce paramètre :** C'est l'interrupteur principal de la fonctionnalité du module.
-   **Effet de la modification de ce paramètre :**
    *   *Lorsqu'il est activé :* Le module commencera à afficher les tags de produit sur vos pages produit du front office selon le hook choisi.
    *   *Lorsqu'il est désactivé :* Le module cessera d'afficher les tags de produit. Tous les autres paramètres seront sauvegardés mais inactifs.
-   **Valeur recommandée :** OUI
-   **Scénario / exemple de marchand :** Vous souhaitez tester le module ou masquer temporairement les tags pendant une refonte du site. Vous le désactiveriez puis le réactiveriez une fois prêt.

#### **Sélectionner le hook pour afficher les tags**

-   **Ce que fait ce paramètre :** Ce paramètre crucial détermine *où* sur votre page produit les tags seront affichés. PrestaShop utilise des "hooks" comme des points spécifiques dans le code de la page où les modules peuvent insérer leur contenu.
-   **Effet de la modification de ce paramètre :**
    *   *Lorsqu'il est défini sur `displayProductButtons` (PrestaShop 1.7+) :* Les tags apparaîtront généralement près du bouton "Ajouter au panier" ou d'autres boutons d'action du produit. C'est souvent un emplacement proéminent et efficace.
    *   *Lorsqu'il est défini sur `displayProductExtraContent` (PrestaShop 1.7+) :* Les tags apparaîtront dans une section dédiée au contenu supplémentaire du produit, souvent sous les informations principales du produit ou dans un onglet.
    *   *Lorsqu'il est défini sur `displayFooterProduct` (PrestaShop 1.7+) :* Les tags apparaîtront en bas de la page produit, souvent au-dessus du pied de page de l'ensemble du site web.
    *   *Lorsqu'il est défini sur `displayLeftColumnProduct` (PrestaShop 1.7+) :* Les tags apparaîtront dans la colonne de gauche spécifiquement sur la page produit.
    *   *Lorsqu'il est défini sur `displayRightColumnProduct` (PrestaShop 1.7+) :* Les tags apparaîtront dans la colonne de droite spécifiquement sur la page produit.
    *   *Autres hooks (par exemple, `displayProductTab`, `displayProductTabContent`, `displayFooter`) :* L'emplacement exact dépendra de l'implémentation de ces hooks par votre thème. `displayFooter` placerait les tags dans le pied de page général du site web, ce qui n'est généralement pas spécifique au produit.
-   **Valeur recommandée :** `displayProductButtons` ou `displayProductExtraContent` sont généralement les plus efficaces pour la visibilité et le contexte. Expérimentez pour voir ce qui convient le mieux à votre thème.
-   **Scénario / exemple de marchand :** Vous souhaitez que les tags soient très visibles pour encourager la découverte immédiate de produits similaires, vous choisissez donc `displayProductButtons`. Si vous préférez qu'ils soient moins intrusifs et fassent partie d'informations supplémentaires, `displayProductExtraContent` pourrait être mieux.

#### **Titre du bloc de tags**

-   **Ce que fait ce paramètre :** Cela vous permet de définir un titre personnalisé qui apparaîtra au-dessus de la liste des tags sur la page produit.
-   **Effet de la modification de ce paramètre :**
    *   *Lorsqu'un titre est saisi (par exemple, "Tags de produit", "Mots-clés associés") :* Ce titre sera affiché au-dessus de la liste des tags, fournissant un en-tête clair pour vos clients.
    *   *Lorsqu'il est laissé vide :* Aucun titre ne sera affiché, et seule la liste des tags apparaîtra.
-   **Valeur recommandée :** "Tags de produit" ou "Mots-clés"
-   **Scénario / exemple de marchand :** Vous souhaitez étiqueter clairement la section afin que les clients comprennent son objectif. Définir le titre sur "Tags associés" aide à guider leur interaction.

### 2.2 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Par défaut / Recommandé | Objectif et impact |
| --- | --- | --- | --- |
| Configuration du module | Activer le module | OUI | Active/désactive la fonctionnalité d'affichage des tags du module. |
| Configuration du module | Sélectionner le hook pour afficher les tags | `displayProductButtons` ou `displayProductExtraContent` | Détermine la position exacte des tags sur la page produit. |
| Configuration du module | Titre du bloc de tags | "Tags de produit" | Définit un en-tête pour les tags affichés, améliorant la clarté pour les clients. |

## 3. Dépannage pour les marchands et questions fréquemment posées (FAQ)

**Q1 : J'ai installé et configuré le module, mais les tags n'apparaissent pas sur mes pages produit. Qu'est-ce qui ne va pas ?**
**R1 :**

-   **Vérifier le statut du module :** Assurez-vous que le module est "Activé" dans sa configuration.
-   **Vider le cache :** Allez dans **Paramètres avancés > Performances** et cliquez sur "Vider le cache" (ou "Vider le cache Smarty" dans les versions plus anciennes). PrestaShop met souvent en cache le contenu, et la nouvelle sortie du module pourrait ne pas apparaître tant que le cache n'est pas vidé.
-   **Vérifier les tags du produit :** Assurez-vous que le produit spécifique que vous consultez a bien des tags qui lui sont assignés. Modifiez le produit dans le Back Office et vérifiez l'onglet "SEO" ou "Tags".
-   **Compatibilité du thème :** Certains thèmes très personnalisés peuvent remplacer les hooks PrestaShop standard ou avoir des mises en page uniques. Essayez de passer temporairement au thème PrestaShop par défaut (par exemple, Classic) pour voir si les tags apparaissent. Si c'est le cas, votre thème personnalisé pourrait nécessiter un petit ajustement (voir Q3).
-   **Sélection du hook :** Vérifiez à nouveau que vous avez sélectionné un hook approprié dans la configuration du module. Certains hooks pourraient ne pas être rendus par votre thème dans un emplacement visible.

**Q2 : Les tags s'affichent, mais ils ont l'air simples ou ne correspondent pas au style de mon thème.**
**R2 :**

-   Le module fournit un style de base. Si vous voulez qu'ils correspondent parfaitement à votre thème, vous devrez ajouter du CSS personnalisé.
-   **Comment faire :**
    1.  Inspectez les tags sur votre page produit à l'aide des outils de développement de votre navigateur (clic droit, puis "Inspecter").
    2.  Identifiez les classes CSS utilisées par les tags (par exemple, `ptags_block`, `ptags_item`).
    3.  Ajoutez des règles CSS personnalisées au fichier `custom.css` de votre thème (s'il en a un) ou directement dans le fichier `ptags.css` du module (bien que la modification directe des fichiers du module ne soit pas recommandée car les mises à jour les écraseront).
    -   **Exemple CSS :**

    ```css
    .ptags_block { margin-top: 20px; padding: 15px; border: 1px solid #eee; background-color: #f9f9f9;}
    .ptags_block h3 { font-size: 18px; color: #333; margin-bottom: 10px;}
    .ptags_item { display: inline-block; margin-right: 8px; margin-bottom: 8px;}
    .ptags_item a { background-color: #007bff; color: white; padding: 5px 10px; border-radius: 3px; text-decoration: none; font-size: 14px;}
    .ptags_item a:hover { background-color: #0056b3;}
    ```

**Q3 : Les tags apparaissent, mais ils sont dans une position maladroite, ou je les veux à un endroit très spécifique non listé dans les options de hook.**
**R3 :**

-   Le module s'appuie sur les hooks PrestaShop standard. Si vous avez besoin d'un placement très spécifique et non standard, cela nécessite généralement une modification du thème.
-   **Solution :** Vous ou votre développeur web devrez insérer manuellement la fonction d'affichage du module dans le modèle de page produit de votre thème (`product.tpl` ou `product-details.tpl` dans le dossier de votre thème).
    *   Trouvez l'emplacement exact dans le fichier `.tpl` de votre thème où vous souhaitez que les tags apparaissent.
    *   Insérez le code Smarty suivant : `{hook h='displayProductTags' product=$product}` (Note : `displayProductTags` est un nom de hook personnalisé que vous enregistreriez dans le module, ou vous pouvez utiliser `displayProductButtons` si c'est ce que vous avez configuré).
    *   Alternativement, vous pouvez appeler le module directement : `{Module::getInstanceByName('ptags')->hookDisplayProductTags(['product' => $product])}`. C'est plus direct mais moins flexible que d'utiliser un hook.
-   **Important :** Cela nécessite des connaissances de base en développement de thème PrestaShop.

**Q4 : Ce module va-t-il ralentir ma boutique ?**
**R4 :**

-   Non, ce module est très léger. Il effectue une simple requête de base de données pour récupérer les tags associés au produit actuel. Cette opération est hautement optimisée par le cœur de PrestaShop et n'aura pas d'impact notable sur les temps de chargement de vos pages.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

### 4.1 Vue d'ensemble de l'architecture

Le module "Afficher les tags sur la page produit" (`ptags`) est un module PrestaShop simple conçu pour étendre les fonctionnalités du front-office. Il suit une architecture de module PrestaShop classique, exploitant principalement la classe `Module` et ses méthodes `install()`, `uninstall()` et `hook`. Il n'introduit pas de contrôleurs, de modèles ou de JavaScript complexes personnalisés. Sa fonction principale est de récupérer les tags de produit et de les rendre via un modèle Smarty dans un hook de front-office choisi.

### 4.2 Contrôleurs (`controllers/`)

Ce module ne contient **pas** de contrôleurs Front-Office ou Back-Office personnalisés. Toute la logique est encapsulée dans la classe principale du module (`ptags/index.php`) et exécutée via le système de hooks de PrestaShop.

### 4.3 Classes et modèles de base (`classes/`)

Ce module n'introduit **pas** de classes personnalisées ou de définitions `ObjectModel`. Il utilise directement les classes `Tag` et `Product` de PrestaShop pour récupérer les données nécessaires.

### 4.4 Assets JavaScript (`views/js/`)

Ce module ne contient **pas** de fichiers JavaScript personnalisés. Sa fonctionnalité est purement le rendu HTML côté serveur.

### 4.5 Feuilles de style CSS (`views/css/`)

-   **Chemin du fichier** : `ptags/views/css/ptags.css`
-   **Portée** : Style client du front-office.
-   **Principaux composants d'interface utilisateur et conteneurs qu'il stylise** : Cette feuille de style fournit un style de base pour le bloc contenant les tags de produit et les liens de tags individuels.
-   **Sélecteurs de classes CSS clés que les développeurs peuvent surcharger dans leur thème** :
    *   `.ptags_block` : Style le bloc conteneur principal des tags.
    *   `.ptags_block h3` : Style le titre du bloc de tags.
    *   `.ptags_item` : Style chaque élément de tag individuel (par exemple, `display: inline-block`, marges).
    *   `.ptags_item a` : Style les liens de tags cliquables (par exemple, arrière-plan, couleur, rembourrage, rayon de bordure).

### 4.6 Structure du modèle Smarty (`views/templates/`)

-   **Modèles de hook (`views/templates/hook/`)** :
    *   **Chemin du fichier** : `ptags/views/front/ptags.tpl`
    *   **Rendu dans le hook** : Ce modèle est rendu par les méthodes `hook` du module (par exemple, `hookDisplayProductButtons`, `hookDisplayProductExtraContent`, etc., selon la configuration).
    *   **Sortie du bloc visuel** : Ce modèle est responsable de la sortie de la structure HTML pour le bloc de tags, y compris le titre facultatif et la liste des liens de tags cliquables. Il itère sur la variable `$tags` (un tableau d'objets tag) passée par la méthode hook du module.

### 4.7 Schéma de base de données et carte des hooks

-   **Tables de base de données** : Ce module ne crée aucune table de base de données personnalisée. Il s'appuie sur les tables PrestaShop existantes, principalement `ps_tag`, `ps_product_tag` et `ps_lang` pour les données de tags.

    -   Les paramètres de configuration sont stockés dans `ps_configuration` avec des clés comme `PTAGS_ENABLED`, `PTAGS_HOOK`, `PTAGS_TITLE`.
-   **Table des hooks enregistrés** :

    | Nom du hook | Moment d'exécution | Objectif technique |
    | --- | --- | --- |
    | `displayHeader` | Dans la section `<head>` de chaque page. | Utilisé pour charger la feuille de style CSS du module (`ptags.css`). |
    | `displayProductButtons` | Sur la page produit, généralement près du bouton "Ajouter au panier". | Affiche le bloc de tags de produit. (PrestaShop 1.7+) |
    | `displayProductExtraContent` | Sur la page produit, dans une section dédiée au contenu supplémentaire. | Affiche le bloc de tags de produit. (PrestaShop 1.7+) |
    | `displayFooterProduct` | En bas du contenu de la page produit. | Affiche le bloc de tags de produit. (PrestaShop 1.7+) |
    | `displayLeftColumnProduct` | Dans la colonne de gauche spécifiquement sur la page produit. | Affiche le bloc de tags de produit. (PrestaShop 1.7+) |
    | `displayRightColumnProduct` | Dans la colonne de droite spécifiquement sur la page produit. | Affiche le bloc de tags de produit. (PrestaShop 1.7+) |
    | `displayProductTab` | Ajoute un nouvel onglet à la page produit. | (Si configuré) Affiche les tags de produit dans un onglet. |
    | `displayProductTabContent` | Contenu pour un onglet de page produit. | (Si configuré) Affiche les tags de produit comme contenu pour un onglet. |
    | `displayFooter` | Dans le pied de page général du site web. | (Si configuré) Affiche le bloc de tags de produit dans le pied de page global. |
    | `displayLeftColumn` | Dans la colonne de gauche des pages (non spécifique au produit). | (Si configuré) Affiche le bloc de tags de produit dans la colonne de gauche globale. |
    | `displayRightColumn` | Dans la colonne de droite des pages (non spécifique au produit). | (Si configuré) Affiche le bloc de tags de produit dans la colonne de droite globale. |

    Le module s'enregistre dynamiquement au hook sélectionné dans sa configuration. Le fichier `index.php` contient les méthodes `hook[NomDuHook]` qui récupèrent l'ID du produit, récupèrent les tags associés et les transmettent à `ptags.tpl` pour le rendu.

## 5. Support officiel et mises à jour

Pour les dernières mises à jour, corrections de bugs et support officiel du module "Afficher les tags sur la page produit", veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu/my-account/orders/). Notre équipe de support est disponible pour aider les marchands et les développeurs avec tout problème ou question lié à la fonctionnalité et à l'intégration du module.
