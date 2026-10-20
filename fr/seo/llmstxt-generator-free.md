---
title: "Générateur LLMS.txt Gratuit - Manuel Marchand & Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop Générateur LLMS.txt Gratuit par MyPresta.eu."
sidebar:
  label: "Générateur LLMS.txt Gratuit - Manuel Marchand & Guide de Configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module LLMS.txt Generator Free sur MyPresta.eu](https://mypresta.eu/modules/seo/llmstxt-generator-free.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/seo/llmstxt-generator-free/)
>
> ---


# Générateur LLMS.txt Gratuit

## 1. Exigences et compatibilité

- **Versions PrestaShop prises en charge** : PrestaShop 9.x
- **Compatibilité PHP** : PHP 7.1 - 8.5
- **Exigences d'hébergement** : Extensions PHP standard (cURL, JSON, OpenSSL). Votre serveur doit autoriser l'écriture de fichiers dans le répertoire racine de votre installation PrestaShop pour que le fichier `llms.txt` puisse être créé et mis à jour.

## 2. Guide de configuration complet (Chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

Après l'installation, cliquez sur "Configurer" pour accéder à la page des paramètres principaux du module. C'est ici que vous définirez le contenu de votre fichier `llms.txt`.

#### Paramètres généraux

-   **Profil de la boutique (pour chaque langue active)**
    *   **Ce que fait ce paramètre :** Cela vous permet de rédiger une description courte et concise de votre boutique dans chaque langue prise en charge par votre site. Ce profil sera inclus dans le fichier `llms.txt`, donnant aux modèles d'IA un aperçu rapide de votre entreprise.
    *   **Effet de la modification de ce paramètre :**
        *   *Lorsqu'il est rempli :* Le texte que vous fournissez sera ajouté au fichier `llms.txt`, aidant les modèles d'IA à comprendre le but et les offres de votre boutique dans des langues spécifiques.
        *   *Lorsqu'il est laissé vide :* Aucun profil de boutique ne sera inclus pour cette langue, ce qui pourrait rendre plus difficile pour l'IA de saisir l'essence de votre boutique.
    *   **Valeur recommandée :** Remplissez ce champ pour chaque langue active. Gardez-le bref (1-2 phrases) et descriptif.
    *   **Scénario / exemple pour le marchand :** Si votre boutique vend des aliments biologiques pour animaux de compagnie, vous pourriez écrire : "MaBoutique propose une large sélection d'aliments biologiques haut de gamme et de fournitures naturelles pour chiens et chats. Nous privilégions la santé, la durabilité et le bonheur des animaux."

#### Sélection de contenu

-   **Catégories promues**

    *   **Ce que fait ce paramètre :** Cela vous permet de sélectionner des catégories de produits spécifiques de votre boutique que vous souhaitez mettre en évidence pour les robots d'exploration d'IA. Ces catégories seront explicitement listées dans le fichier `llms.txt`.
    *   **Effet de la modification de ce paramètre :**
        *   *Lorsque des catégories sont sélectionnées :* Les modèles d'IA seront dirigés vers ces catégories, signalant leur importance et augmentant potentiellement leur visibilité dans les recherches basées sur l'IA.
        *   *Lorsqu'aucune catégorie n'est sélectionnée :* Les modèles d'IA ne recevront pas de directives spécifiques sur les catégories à prioriser à partir de votre fichier `llms.txt`.
    *   **Valeur recommandée :** Sélectionnez 3 à 5 de vos catégories les plus importantes ou les plus vendues.
    *   **Scénario / exemple pour le marchand :** Si vous êtes spécialisé dans les "Robes pour femmes", les "Chaussures pour hommes" et les "Jouets pour enfants", sélectionnez ces catégories pour indiquer à l'IA qu'il s'agit d'offres principales.
-   **Inclure les 5 meilleures ventes avec les prix**

    *   **Ce que fait ce paramètre :** Lorsqu'il est activé, le module identifiera automatiquement vos 5 produits les plus vendus et inclura leurs noms, liens et prix actuels dans le fichier `llms.txt`.
    *   **Effet de la modification de ce paramètre :**
        *   *Lorsqu'il est activé :* Les modèles d'IA auront un accès direct aux informations sur vos produits les plus populaires, y compris leurs prix, ce qui peut être crucial pour les recommandations d'achat basées sur l'IA.
        *   *Lorsqu'il est désactivé :* Vos meilleures ventes ne seront pas explicitement mises en évidence avec leurs prix dans le fichier `llms.txt`.
    *   **Valeur recommandée :** OUI. C'est une fonctionnalité puissante pour présenter vos articles les plus populaires.
    *   **Scénario / exemple pour le marchand :** Un client demande à une IA : "Quels sont les articles les plus vendus chez [Nom de votre boutique] ?" Avec cette option activée, l'IA peut fournir une réponse directe avec les prix actuels.
-   **Inclure les pages CMS**

    *   **Ce que fait ce paramètre :** Cela vous permet de sélectionner des pages de contenu statique importantes (comme "À propos de nous", "Contactez-nous", "Politique de confidentialité", "Informations de livraison") dont vous souhaitez que les modèles d'IA soient informés.
    *   **Effet de la modification de ce paramètre :**
        *   *Lorsque des pages CMS sont sélectionnées :* Les modèles d'IA seront dirigés vers ces pages d'information, les aidant à comprendre les politiques de votre boutique, son historique et comment vous contacter.
        *   *Lorsqu'aucune page CMS n'est sélectionnée :* Les modèles d'IA pourraient devoir découvrir ces pages par une exploration générale, ce qui pourrait être moins efficace.
    *   **Valeur recommandée :** Sélectionnez toutes les pages d'information essentielles qui renforcent la confiance et fournissent des détails sur le service client.
    *   **Scénario / exemple pour le marchand :** Assurez-vous que vos pages "Politique de retour" et "FAQ" sont incluses afin que l'IA puisse répondre avec précision aux questions des clients sur ces sujets.

#### Action

-   **Enregistrer et régénérer le fichier llms.txt**
    *   **Ce que fait ce bouton :** Ce bouton enregistre tous les paramètres que vous avez configurés sur cette page et régénère immédiatement le fichier `llms.txt` dans le répertoire racine de votre boutique avec les informations mises à jour.
    *   **Effet de cliquer sur ce bouton :** Votre fichier `llms.txt` sera mis à jour avec vos dernières sélections. Cette action est également déclenchée automatiquement lorsque vous mettez à jour des produits ou des catégories dans votre boutique.
    *   **Valeur recommandée :** Cliquez toujours sur ce bouton après avoir apporté des modifications pour vous assurer que votre fichier `llms.txt` est à jour.
    *   **Scénario / exemple pour le marchand :** Après avoir ajouté une nouvelle description de "Profil de la boutique", cliquez sur ce bouton pour vous assurer que les robots d'exploration d'IA obtiennent les nouvelles informations.

#### Mise à niveau vers la version Pro (Bloc de vente incitative)

Cette section est un bloc d'information promouvant la version Pro du module. Elle met en évidence les fonctionnalités supplémentaires disponibles dans la version payante, telles que l'exportation complète du catalogue, l'analyse des robots d'exploration, les filtres et la prise en charge des tâches cron. Ce n'est pas un paramètre configurable mais une suggestion pour des besoins avancés.

### 2.2 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Valeur par défaut / Recommandée | Objectif et impact |
| --- | --- | --- | --- |
| Configuration du module | Profil de la boutique (par langue) | Remplir pour toutes les langues | Fournit aux modèles d'IA une brève description structurée de votre boutique. |
| Configuration du module | Catégories promues | Sélectionner 3 à 5 catégories clés | Dirige les robots d'exploration d'IA vers vos catégories de produits les plus importantes. |
| Configuration du module | Inclure les 5 meilleures ventes avec les prix | OUI | Met en évidence vos produits les plus populaires avec les prix actuels pour l'IA. |
| Configuration du module | Inclure les pages CMS | Sélectionner toutes les pages essentielles | Guide l'IA vers les pages d'information importantes (par exemple, À propos de nous, Contact). |
| Configuration du module | Enregistrer et régénérer le fichier llms.txt | Cliquer après toute modification | Enregistre les paramètres et met à jour le fichier `llms.txt` à la racine de votre boutique. |

## 3. Dépannage pour les marchands et questions fréquemment posées (FAQ)

**Q1 : J'ai configuré le module, mais je ne vois aucun changement sur mon site web. Est-ce que ça fonctionne ?**
R1 : Oui, il est probable que cela fonctionne correctement ! Le fichier `llms.txt` est un fichier technique destiné aux robots d'exploration d'IA, pas aux visiteurs humains. Vous ne verrez aucun changement visuel sur le front-office de votre boutique. Pour vérifier que cela fonctionne, vous pouvez essayer d'accéder à `votreboutique.com/llms.txt` dans votre navigateur. Vous devriez y voir le contenu généré.

**Q2 : Je reçois une erreur indiquant que le module ne peut pas écrire le fichier `llms.txt`.**
R2 : Cela indique généralement un problème de permissions de fichier sur votre serveur. Le module a besoin de la permission de créer et de mettre à jour le fichier `llms.txt` dans le répertoire racine de votre PrestaShop.
- **Solution :** Contactez votre hébergeur et demandez-lui de s'assurer que l'application PrestaShop dispose des permissions d'écriture (par exemple, chmod 755 ou 775 pour les répertoires, 644 ou 664 pour les fichiers) dans le dossier racine de votre boutique.

**Q3 : À quelle fréquence le fichier `llms.txt` est-il mis à jour ?**
R3 : Le fichier `llms.txt` est régénéré automatiquement chaque fois que vous :
- Cliquez sur le bouton "Enregistrer et régénérer le fichier llms.txt" dans la configuration du module.
- Mettez à jour un produit (par exemple, modifiez le prix, le nom, la description).
- Mettez à jour une catégorie (par exemple, modifiez le nom, la description).
Cela garantit que le fichier est toujours à jour avec les dernières données de votre boutique.

**Q4 : Mon thème personnalisé ne semble pas être affecté par ce module. Y a-t-il un conflit ?**
R4 : Non, il ne devrait pas y avoir de conflit. Ce module fonctionne entièrement en arrière-plan, générant un fichier texte. Il ne modifie pas la conception de votre thème, le CSS ou le JavaScript. Son but est de fournir des données structurées aux robots d'exploration d'IA, et non de modifier l'apparence visuelle de votre boutique.

**Q5 : Puis-je modifier manuellement le fichier `llms.txt` ?**
R5 : Il est fortement recommandé de **ne pas** modifier manuellement le fichier `llms.txt` directement. Toute modification que vous apporterez sera écrasée la prochaine fois que le module régénérera le fichier (par exemple, lorsque vous enregistrez les paramètres ou mettez à jour des produits/catégories). Utilisez toujours l'interface de configuration du module pour contrôler son contenu.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

Cette section est strictement destinée aux développeurs, aux webmasters de boutiques et aux agences techniques qui maintiennent ou étendent la boutique.

### 4.1 Aperçu de l'architecture

Le module `Générateur LLMS.txt Gratuit` est un module PrestaShop léger principalement axé sur la génération d'un fichier texte statique (`llms.txt`) dans le répertoire racine de la boutique. Il suit une structure de module PrestaShop standard, utilisant la classe `Module` pour l'installation, la désinstallation et la configuration. La logique principale réside dans le fichier principal du module, gérant la persistance de la configuration et la génération de fichiers. Il utilise la classe `Configuration` de PrestaShop pour les paramètres et les hooks pour la régénération automatique.

### 4.2 Contrôleurs (`controllers/`)

Ce module ne contient **pas** de contrôleurs d'administration Front-Office ou Back-Office personnalisés. Toute la logique est gérée dans la méthode `getContent()` du fichier principal du module pour la configuration et via des hooks pour les opérations en arrière-plan.

### 4.3 Classes et modèles principaux (`classes/`)

Ce module ne contient **pas** de classes personnalisées ou de définitions `ObjectModel` dans le répertoire `classes/`. Il utilise directement les classes principales de PrestaShop comme `Configuration`, `Product`, `Category`, `CMS`, `Language` et `Shop`.

### 4.4 Actifs JavaScript (`views/js/`)

Ce module ne contient **pas** de fichiers JavaScript personnalisés.

### 4.5 Feuilles de style CSS (`views/css/`)

-   **`llmstxtfree/views/css/admin-config.css`**
    *   **Portée :** Style du formulaire d'administration du Back-office.
    *   **Principaux composants et conteneurs d'interface utilisateur qu'il stylise :** Fournit un style de base pour la page de configuration du module, probablement pour la mise en page, l'espacement et potentiellement quelques repères visuels pour le bloc de vente incitative.
    *   **Sélecteurs de classe CSS clés que les développeurs peuvent surcharger dans leur thème :** Cible généralement les éléments dans la sortie `getContent()` du module, tels que `.panel`, `.form-group`, ou les classes personnalisées définies dans `configure.tpl`.

### 4.6 Structure du template Smarty (`views/templates/`)

-   **Templates d'administration (`views/templates/admin/`)** :
    *   **`llmstxtfree/views/templates/admin/configure.tpl`**
        *   **Objectif :** C'est le template Smarty principal rendu par la méthode `getContent()` du module. Il définit la structure et les champs de la page de configuration du module dans le Back Office de PrestaShop.
        *   **Contenu :** Contient le formulaire HTML pour tous les paramètres décrits dans la Section 4.1, y compris les champs de saisie pour le profil de la boutique, la sélection de catégories, le basculement des meilleures ventes, la sélection de pages CMS et le bouton d'enregistrement. Il inclut également le template `pro-upsell.tpl`.
    *   **`llmstxtfree/views/templates/admin/pro-upsell.tpl`**
        *   **Objectif :** Ce template est inclus dans `configure.tpl` et affiche le contenu promotionnel pour la version Pro du module.
        *   **Contenu :** Contient généralement du texte, des images et des liens encourageant le marchand à passer à la version payante, en mettant en évidence les fonctionnalités supplémentaires.

### 4.7 Schéma de la base de données et carte des hooks

-   **Tables de base de données** :

    *   Ce module ne crée **pas** de tables SQL personnalisées.
    *   Il stocke ses paramètres de configuration (par exemple, catégories sélectionnées, pages CMS, profils de boutique, bascule des meilleures ventes) dans la table standard `ps_configuration` de PrestaShop. Les clés de configuration suivent généralement le modèle `LLMSTXTFREE_SETTING_NAME`.
-   **Table des hooks enregistrés** :

| Nom du hook | Moment d'exécution | Objectif technique |
| --- | --- | --- |
| `displayHeader` | Rend le contenu dans la section `<head>` des pages du front-office. | Non utilisé directement pour la sortie de contenu, mais souvent enregistré par les modules pour le chargement d'actifs ou la configuration initiale. Dans ce module, il est probablement destiné à l'initialisation générale du module ou potentiellement à de futures fonctionnalités. |
| `displayRightColumn` | Rend le contenu dans la colonne de droite des pages du front-office. | Non utilisé pour la sortie de contenu dans ce module. |
| `displayLeftColumn` | Rend le contenu dans la colonne de gauche des pages du front-office. | Non utilisé pour la sortie de contenu dans ce module. |
| `displayFooter` | Rend le contenu dans le pied de page des pages du front-office. | Non utilisé pour la sortie de contenu dans ce module. |
| `displayProductExtraContent` | Rend le contenu supplémentaire sur la page produit. | Non utilisé pour la sortie de contenu dans ce module. |
| `actionProductUpdate` | Exécuté après la mise à jour d'un produit dans le Back Office. | **Crucial pour ce module :** Déclenche la régénération automatique du fichier `llms.txt` pour garantir que les données des meilleures ventes et les liens des produits sont à jour. |
| `actionCategoryUpdate` | Exécuté après la mise à jour d'une catégorie dans le Back Office. | **Crucial pour ce module :** Déclenche la régénération automatique du fichier `llms.txt` pour garantir que les liens et les noms des catégories promues sont à jour. |
| `actionObjectCmsUpdateAfter` | Exécuté après la mise à jour d'une page CMS. | Déclenche la régénération automatique du fichier `llms.txt` pour garantir que les liens et les titres des pages CMS sélectionnées sont à jour. |
| `actionObjectCmsAddAfter` | Exécuté après l'ajout d'une nouvelle page CMS. | Déclenche la régénération automatique du fichier `llms.txt`. |
| `actionObjectCmsDeleteAfter` | Exécuté après la suppression d'une page CMS. | Déclenche la régénération automatique du fichier `llms.txt`. |

## 5. Support officiel et mises à jour

Pour les mises à jour officielles, le support technique et pour explorer des modules et services supplémentaires, veuillez visiter votre compte client sur [MyPresta.eu](https://mypresta.eu/my-account/orders/). Notre équipe de support est disponible pour vous aider avec tout problème ou question concernant le module Générateur LLMS.txt Gratuit.
