---
title: "Commentaires DISQUS - Manuel du Marchand & Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop de commentaires DISQUS par MyPresta.eu."
sidebar:
  label: "Commentaires DISQUS - Manuel du Marchand & Guide de Configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module DISQUS comments sur MyPresta.eu](https://mypresta.eu/modules/front-office-features/disqus-comments.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/front-office/disqus-comments/)
>
> ---


# Commentaires DISQUS

## 1. Exigences et compatibilité

- **Versions PrestaShop prises en charge** : PrestaShop 1.4.x, 1.5.x, 1.6.x, 1.7.x, 8.x
- **Compatibilité PHP** : PHP 5.6 - 8.5
- **Exigences d'hébergement** : Les extensions PHP standard (cURL, JSON, OpenSSL) sont généralement requises pour PrestaShop et pour la communication avec des services externes comme Disqus.

## 2. Présentation complète de la configuration (Chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer > Commentaires DISQUS)

Ceci est l'écran de configuration principal où vous configurerez l'intégration de Disqus avec votre boutique.

#### **1. Nom court du site (Site shortname)**

-   **Ce que fait ce paramètre :** C'est l'identifiant unique de votre site web Disqus. Vous l'obtenez de votre compte Disqus lorsque vous enregistrez votre site web. Il indique à Disqus quels fils de commentaires appartiennent à votre boutique.
-   **Effet de la modification de ce paramètre :**
    *   *Lorsqu'il est correctement défini :* Les commentaires Disqus se chargeront et s'enregistreront correctement pour vos produits.
    *   *Lorsqu'il est incorrect ou vide :* Disqus ne pourra pas charger les commentaires, ou il pourrait charger des commentaires d'un autre site, entraînant des erreurs ou des commentaires manquants.
-   **Valeur recommandée :** Votre nom court Disqus unique (par exemple, `nomdevotreboutique`).
-   **Scénario / exemple pour le marchand :** Si vous avez enregistré votre site web sur Disqus sous le nom "Ma Super Boutique", votre nom court pourrait être "masuperboutique". Saisissez cette chaîne exacte ici.

#### **2. Position du widget de commentaires (Comments widget position)**

-   **Ce que fait ce paramètre :** Il contrôle l'endroit où la section principale des commentaires Disqus apparaît sur vos pages produits.
-   **Effet de la modification de ce paramètre :**
    *   *Lorsqu'il est défini sur "Section d'onglet produit" :* Les commentaires apparaîtront dans un nouvel onglet sur la page produit (par exemple, à côté de "Description" ou "Fiche technique"). Les clients cliqueront sur l'onglet pour voir les commentaires.
    *   *Lorsqu'il est défini sur "Section de pied de page produit" :* Les commentaires apparaîtront en bas de la page produit, sous les informations principales du produit. Les clients les verront en faisant défiler la page.
-   **Valeur recommandée :** "Section d'onglet produit" pour une mise en page de page produit plus propre, ou "Section de pied de page produit" si vous souhaitez que les commentaires soient immédiatement visibles sans cliquer sur un onglet.
-   **Scénario / exemple pour le marchand :** Si vos pages produits sont déjà très longues, placer les commentaires dans un onglet permet de garder la vue initiale ordonnée. Si vous souhaitez mettre l'accent sur les commentaires des clients, les placer dans le pied de page les rend plus visibles.

#### **3. Page de témoignages (Testimonials page)**

-   **Ce que fait ce paramètre :** Il active ou désactive une page dédiée sur votre boutique qui agrège tous les commentaires Disqus de vos produits.
-   **Effet de la modification de ce paramètre :**
    *   *Lorsque "Activé" :* Une nouvelle page sera créée à une URL comme `votreboutique.com/testimonials` (ou similaire, selon vos URL conviviales) affichant tous les commentaires.
    *   *Lorsque "Désactivé" :* Aucune page de ce type ne sera disponible.
-   **Valeur recommandée :** "Activé" pour fournir un centre centralisé pour les commentaires des clients.
-   **Scénario / exemple pour le marchand :** L'activation de cette option vous permet de créer un lien vers une page "Avis clients" ou "Ce que disent nos clients" depuis votre pied de page, présentant tous les commentaires positifs en un seul endroit.

#### **4. Apparence du lien des témoignages (Testimonials link appearance)**

-   **Ce que fait ce paramètre :** Si la "Page de témoignages" est activée, cela contrôle l'endroit où un lien vers cette page apparaît dans la mise en page de votre boutique.
-   **Effet de la modification de ce paramètre :**
    *   *Lorsque "Masquer" :* La page de témoignages existera, mais aucun lien automatique ne sera ajouté par le module. Vous devrez ajouter un lien manuellement (par exemple, dans le menu de pied de page de votre thème).
    *   *Lorsque "Colonne de gauche" :* Un lien vers la page de témoignages apparaîtra dans la colonne de gauche de votre boutique.
    *   *Lorsque "Colonne de droite" :* Un lien vers la page de témoignages apparaîtra dans la colonne de droite de votre boutique.
-   **Valeur recommandée :** "Colonne de droite" ou "Colonne de gauche" pour rendre la page de témoignages facilement découvrable.
-   **Scénario / exemple pour le marchand :** Si votre boutique utilise une colonne de gauche pour les catégories, placer le lien des témoignages dans la colonne de droite pourrait être plus approprié.

#### **5. Commentaires récents sur la page d'accueil (Homepage recent comments)**

-   **Ce que fait ce paramètre :** Il contrôle si un bloc affichant les commentaires Disqus les plus récents apparaît sur la page d'accueil de votre boutique.
-   **Effet de la modification de ce paramètre :**
    *   *Lorsque "Activé" :* Un bloc avec les commentaires récents sera affiché sur votre page d'accueil.
    *   *Lorsque "Désactivé" :* Aucun bloc de commentaires récents n'apparaîtra sur la page d'accueil.
-   **Valeur recommandée :** "Activé" pour maintenir votre page d'accueil dynamique et mettre en évidence l'activité récente des clients.
-   **Scénario / exemple pour le marchand :** L'affichage des commentaires récents sur la page d'accueil peut encourager les visiteurs à explorer les produits qui font l'objet de discussions actives, ce qui peut potentiellement entraîner plus de ventes.

#### **6. Commentaires récents dans la colonne de droite (Right column recent comments)**

-   **Ce que fait ce paramètre :** Il contrôle si un bloc affichant les commentaires Disqus les plus récents apparaît dans la colonne de droite de votre boutique.
-   **Effet de la modification de ce paramètre :**
    *   *Lorsque "Activé" :* Un bloc avec les commentaires récents sera affiché dans la colonne de droite sur les pages où la colonne de droite est active.
    *   *Lorsque "Désactivé" :* Aucun bloc de commentaires récents n'apparaîtra dans la colonne de droite.
-   **Valeur recommandée :** "Activé" pour maintenir l'engagement sur votre site.
-   **Scénario / exemple pour le marchand :** Si votre boutique a une colonne de droite, l'affichage des commentaires récents peut fournir un flux constant de contenu frais et encourager l'exploration.

#### **7. Commentaires récents dans la colonne de gauche (Left column recent comments)**

-   **Ce que fait ce paramètre :** Il contrôle si un bloc affichant les commentaires Disqus les plus récents apparaît dans la colonne de gauche de votre boutique.
-   **Effet de la modification de ce paramètre :**
    *   *Lorsque "Activé" :* Un bloc avec les commentaires récents sera affiché dans la colonne de gauche sur les pages où la colonne de gauche est active.
    *   *Lorsque "Désactivé" :* Aucun bloc de commentaires récents n'apparaîtra dans la colonne de gauche.
-   **Valeur recommandée :** "Activé" pour maintenir l'engagement sur votre site.
-   **Scénario / exemple pour le marchand :** Similaire à la colonne de droite, l'utilisation de la colonne de gauche pour les commentaires récents peut être efficace si votre thème utilise principalement la colonne de gauche pour la navigation ou d'autres blocs.

#### **8. Afficher Disqus uniquement pour les utilisateurs connectés ayant acheté le produit (Show disqus only for logged users that purchased product)**

-   **Ce que fait ce paramètre :** C'est un paramètre puissant pour restreindre qui peut voir et interagir avec les commentaires Disqus sur les pages produits.
-   **Effet de la modification de ce paramètre :**
    *   *Lorsque "Activé" :* Seuls les clients connectés à leur compte ET ayant déjà acheté le produit spécifique verront la section de commentaires Disqus. Tous les autres visiteurs ne la verront pas.
    *   *Lorsque "Désactivé" :* Tous les visiteurs (connectés ou invités, acheteurs ou non) verront la section de commentaires Disqus.
-   **Valeur recommandée :** "Désactivé" pour un engagement maximal et des avantages SEO. "Activé" si vous souhaitez vous assurer que seuls les acheteurs vérifiés peuvent commenter, ce qui peut augmenter la crédibilité des avis mais réduire le volume de commentaires.
-   **Scénario / exemple pour le marchand :** Si vous rencontrez des problèmes de spam ou de commentaires non pertinents, l'activation de cette option peut filtrer les non-acheteurs. Cependant, si votre objectif est une discussion large et le référencement, gardez-la désactivée.

#### **9. Combien de commentaires récents afficher ? (How many recent comments to show?)**

-   **Ce que fait ce paramètre :** Il détermine le nombre de commentaires récents affichés dans les blocs "Commentaires récents" (sur la page d'accueil, les colonnes de gauche ou de droite).
-   **Effet de la modification de ce paramètre :**
    *   *Lorsqu'il est défini sur un nombre (par exemple, 5) :* Les blocs afficheront ce nombre de commentaires les plus récents.
    *   *Lorsqu'il est défini sur 0 ou vide :* Aucun commentaire récent ne sera affiché dans les blocs, même si les blocs sont activés.
-   **Valeur recommandée :** 3 à 5 commentaires pour un bloc compact, ou jusqu'à 10 pour un affichage plus proéminent.
-   **Scénario / exemple pour le marchand :** L'affichage de 5 commentaires offre un bon équilibre entre l'affichage de l'activité et le fait de ne pas rendre le bloc trop long.

#### **Tableau de référence rapide de la configuration**

| Écran / Vue | Paramètre / Option | Par défaut / Recommandé | Objectif et impact |
| --- | --- | --- | --- |
| Configuration du module | Nom court du site | Votre nom court Disqus | Identifiant unique de votre compte Disqus ; essentiel pour le chargement des commentaires. |
| Configuration du module | Position du widget de commentaires | Section d'onglet produit | Où la section principale des commentaires apparaît sur les pages produits (onglet ou pied de page). |
| Configuration du module | Page de témoignages | Activé | Crée une page dédiée agrégeant tous les commentaires. |
| Configuration du module | Apparence du lien des témoignages | Colonne de droite | Où un lien vers la page de témoignages apparaît (si activé). |
| Configuration du module | Commentaires récents sur la page d'accueil | Activé | Affiche un bloc de commentaires récents sur la page d'accueil. |
| Configuration du module | Commentaires récents dans la colonne de droite | Activé | Affiche un bloc de commentaires récents dans la colonne de droite. |
| Configuration du module | Commentaires récents dans la colonne de gauche | Activé | Affiche un bloc de commentaires récents dans la colonne de gauche. |
| Configuration du module | Afficher Disqus uniquement pour les utilisateurs connectés ayant acheté le produit | Désactivé | Restreint la visibilité/interaction des commentaires aux acheteurs vérifiés. |
| Configuration du module | Combien de commentaires récents afficher ? | 5 | Nombre de commentaires à afficher dans les blocs de commentaires récents. |

## 3. Dépannage pour les marchands et questions fréquemment posées (FAQ)

**Q1 : Mes commentaires Disqus n'apparaissent pas sur les pages produits. Que dois-je faire ?**

-   **R :** Tout d'abord, vérifiez votre "Nom court du site" dans la configuration du module. Il doit correspondre exactement au nom court de votre compte Disqus. Assurez-vous également d'avoir défini "Position du widget de commentaires" sur "Section d'onglet produit" ou "Section de pied de page produit". Enfin, videz votre cache PrestaShop (Paramètres avancés > Performances > Vider le cache) et le cache de votre navigateur.

**Q2 : Les blocs "Commentaires récents" n'apparaissent pas dans mes colonnes/page d'accueil.**

-   **R :** Vérifiez que vous avez activé "Commentaires récents sur la page d'accueil", "Commentaires récents dans la colonne de droite" ou "Commentaires récents dans la colonne de gauche" dans la configuration du module. Assurez-vous également que "Combien de commentaires récents afficher ?" est défini sur un nombre supérieur à 0. Si votre thème n'affiche pas les colonnes de gauche/droite sur certaines pages, les blocs n'apparaîtront pas. Videz le cache après avoir effectué des modifications.

**Q3 : J'ai activé la "Page de témoignages", mais je ne trouve pas de lien vers celle-ci.**

-   **R :** Si vous avez défini "Apparence du lien des témoignages" sur "Masquer", le module n'ajoutera pas automatiquement de lien. Vous devrez ajouter un lien manuellement vers la page (par exemple, dans le menu de pied de page de votre thème). L'URL de la page de témoignages est généralement `votreboutique.com/module/disqus/testimonials` (ou une version d'URL conviviale si activée). Si vous avez choisi "Colonne de gauche" ou "Colonne de droite", assurez-vous que ces colonnes sont actives sur les pages que vous consultez.

**Q4 : Seuls certains utilisateurs peuvent voir les commentaires, ou je ne peux pas les voir en tant qu'invité.**

-   **R :** Vérifiez le paramètre "Afficher Disqus uniquement pour les utilisateurs connectés ayant acheté le produit". Si cette option est activée, seuls les clients connectés qui ont acheté le produit spécifique verront les commentaires. Désactivez ce paramètre si vous souhaitez que tous les visiteurs puissent voir et interagir avec les commentaires.

**Q5 : Le style de mon thème personnalisé entre en conflit avec les commentaires Disqus.**

-   **R :** Le widget Disqus lui-même est en grande partie autonome et stylisé par Disqus. Cependant, le conteneur ou l'onglet qui contient le widget peut être affecté par le CSS de votre thème. Vous devrez peut-être faire appel à un développeur web pour inspecter les éléments à l'aide des outils de développement du navigateur et ajouter du CSS personnalisé à votre thème pour ajuster l'espacement, les polices ou les couleurs autour du widget Disqus.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

Cette section fournit un aperçu technique détaillé du module de commentaires DISQUS pour les développeurs et les webmasters.

### 4.1 Vue d'ensemble de l'architecture

Le module de commentaires DISQUS suit une architecture de module PrestaShop standard, exploitant principalement les hooks pour l'affichage en front-office et une méthode `getContent()` pour la configuration en back-office. Il intègre dynamiquement le code d'intégration universel de Disqus. Le module utilise un contrôleur frontal personnalisé pour la page de témoignages, et un autre pour les appels AJAX (bien qu'actuellement, le contrôleur AJAX semble être un espace réservé ou peu utilisé pour les fonctionnalités principales de Disqus). La configuration est stockée dans `ps_configuration`.

### 4.2 Contrôleurs (`controllers/`)

-   **Contrôleurs Front-Office** :

    -   `controllers/front/index.php`
        -   **Nom de la classe :** `DisqusIndexModuleFrontController` (étend `ModuleFrontController`)
        -   **Responsabilité :** Ce contrôleur est probablement une valeur par défaut ou un contrôleur de secours pour le routage front-office du module. Dans le contexte de Disqus, il pourrait être utilisé pour des actions front-end générales liées au module, bien que l'intégration principale de Disqus soit généralement gérée via des hooks. Il pourrait servir de base pour de futures fonctionnalités AJAX ou de simples affichages de pages si nécessaire.
    -   `controllers/front/testimonials.php`
        -   **Nom de la classe :** `DisqusTestimonialsModuleFrontController` (étend `ModuleFrontController`)
        -   **Responsabilité :** Ce contrôleur est responsable du rendu de la page dédiée "Témoignages". Il récupère la configuration nécessaire (par exemple, `disqus_shortname`) et la transmet au template `testimonials.tpl`, qui intègre ensuite le code d'intégration universel de Disqus configuré pour afficher tous les commentaires pour le nom court donné. Ce contrôleur gère la route `module/disqus/testimonials`.
-   **Contrôleurs d'administration Back-Office** : Aucun explicitement défini dans l'inventaire fourni. Toute la configuration est gérée via la méthode `getContent()` du fichier de module principal.

### 4.3 Classes et modèles principaux (`classes/`)

Aucune classe personnalisée ou définition d'`ObjectModel` n'est présente dans le répertoire `classes/` selon l'inventaire. Le module s'appuie sur la classe `Configuration` de PrestaShop pour stocker ses paramètres.

### 4.4 Actifs JavaScript (`views/js/`)

Aucun fichier JavaScript personnalisé n'est présent dans le répertoire `views/js/` selon l'inventaire. Le module intègre directement le code d'intégration universel de Disqus (généralement une balise `<script>` avec `DISQUS.init()` ou une logique similaire) dans les templates Smarty pertinents. Cela signifie que le propre JavaScript de Disqus est chargé directement depuis `disqus.com`.

### 4.5 Feuilles de style CSS (`views/css/`)

Aucun fichier CSS personnalisé n'est présent dans le répertoire `views/css/` selon l'inventaire. Le style du widget de commentaires Disqus lui-même est géré par Disqus. Tout style spécifique à l'intégration (par exemple, pour les blocs de commentaires récents ou la mise en page de la page de témoignages) serait soit minimal, hérité du thème, soit en ligne dans les templates.

### 4.6 Structure des templates Smarty (`views/templates/`)

-   **Templates de hook (`views/templates/hook/`)** :

    -   `last-comments.tpl` : Ce template est utilisé pour afficher le bloc "Commentaires récents". Il itère sur une liste de commentaires récents (récupérés de Disqus via JavaScript ou un appel côté serveur si implémenté) et les affiche. Ce template est probablement rendu dans les hooks `displayHome`, `displayLeftColumn` et `displayRightColumn`.
    -   `leftColumn.tpl` : Ce template est probablement un wrapper ou un contenu spécifique pour le hook `displayLeftColumn`, incluant potentiellement `last-comments.tpl` ou le lien des témoignages.
    -   `productfooter.tpl` : Ce template est rendu dans le hook `displayProductFooter`. Il contient le code d'intégration universel de Disqus pour les commentaires de produits lorsque la "Position du widget de commentaires" est définie sur "Section de pied de page produit".
    -   `rightColumn.tpl` : Similaire à `leftColumn.tpl`, c'est pour le hook `displayRightColumn`, incluant potentiellement `last-comments.tpl` ou le lien des témoignages.
-   **Templates d'administration (`views/templates/admin/`)** : Aucun.
-   **Templates front-office (`views/templates/front/`)** :

    -   `testimonials.tpl` : Ce template est rendu par le `DisqusTestimonialsModuleFrontController`. Il contient le code d'intégration universel de Disqus configuré pour afficher tous les commentaires pour le nom court du site, créant ainsi la page de témoignages agrégée.

### 4.7 Schéma de base de données et carte des hooks

-   **Tables de base de données** : Le module ne crée aucune table SQL personnalisée. Tous les paramètres de configuration sont stockés dans la table `ps_configuration` à l'aide de clés telles que `DISQUS_SHORTNAME`, `DISQUS_HOOK`, `DISQUS_TEST`, `DISQUS_TEST_WHERE`, `DISQUS_RIGHTRECENT`, `DISQUS_LEFTRECENT`, `DISQUS_FORLOGGED`, `DISQUS_LASTCOMMENTS`, `DISQUS_LASTC_NB`.
-   **Table des hooks enregistrés** :

| Nom du hook | Moment d'exécution | Objectif technique |
| --- | --- | --- |
| `displayHeader` | Dans la section `<head>` de chaque page. | Potentiellement utilisé pour inclure des variables de configuration globales Disqus ou du CSS/JS si nécessaire, bien que l'intégration principale se fasse dans des hooks de contenu spécifiques. |
| `displayProductExtraContent` | Dans la page produit, souvent utilisé pour les onglets ou les blocs de contenu supplémentaires. | Utilisé pour afficher la section de commentaires Disqus dans un onglet produit lorsque la "Position du widget de commentaires" est définie sur "Section d'onglet produit". |
| `displayRightColumn` | Dans la colonne de droite des pages. | Utilisé pour afficher le bloc "Commentaires récents" ou le "Lien des témoignages" si configuré. |
| `displayProductFooter` | En bas du contenu de la page produit. | Utilisé pour afficher la section de commentaires Disqus lorsque la "Position du widget de commentaires" est définie sur "Section de pied de page produit". |
| `displayLeftColumn` | Dans la colonne de gauche des pages. | Utilisé pour afficher le bloc "Commentaires récents" ou le "Lien des témoignages" si configuré. |
| `displayHome` | Sur la page d'accueil. | Utilisé pour afficher le bloc "Commentaires récents" sur la page d'accueil. |
| `actionValidateOrder` | Après qu'une commande a été validée avec succès. | Ce hook est listé dans la méthode `install()` du module, suggérant une fonctionnalité future potentielle ou une vérification des produits achetés. Il est probablement utilisé conjointement avec le paramètre "Afficher Disqus uniquement pour les utilisateurs connectés ayant acheté le produit" pour vérifier l'historique des achats. |

## 5. Support officiel et mises à jour

Pour les dernières mises à jour du module, les corrections de bugs et le support officiel, veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu/my-account/orders/). Notre équipe de support est disponible pour vous aider avec tout problème ou question concernant le module de commentaires DISQUS.
