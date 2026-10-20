---
title: "Commentaires Facebook - Manuel Marchand & Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop Commentaires Facebook par MyPresta.eu."
sidebar:
  label: "Commentaires Facebook - Manuel Marchand & Guide de Configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Facebook Comments sur MyPresta.eu](https://mypresta.eu/modules/social-networks/facebook-comments.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/social-networks/facebook-comments/)
>
> ---


# Commentaires Facebook

## 1. Exigences et compatibilité

- **Versions PrestaShop prises en charge :** PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilité PHP :** PHP 7.1 - 8.5
- **Exigences d'hébergement :** Les extensions PHP standard (cURL, JSON, OpenSSL) sont généralement requises pour PrestaShop lui-même et tout module interagissant avec des API externes comme Facebook.

## 2. Guide de configuration complet (Chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

Après l'installation, cliquez sur "Configurer" pour accéder aux paramètres du module. C'est ici que vous contrôlerez l'apparence et le fonctionnement de la boîte de commentaires Facebook sur vos pages produits.

#### 2.1.1 ID d'application Facebook

-   **Ce que fait ce paramètre :** Il s'agit d'un identifiant unique pour votre application Facebook. Bien que le module puisse fonctionner sans lui, fournir un ID d'application vous donne accès aux outils de modération et aux statistiques de Facebook pour les commentaires sur votre site.
-   **Effet de la modification de ce paramètre :**
    -   *Lorsqu'il est fourni :* Vous accédez au panneau de modération des commentaires de Facebook (developers.facebook.com/tools/comments) où vous pouvez examiner, approuver ou supprimer des commentaires. Cela aide également Facebook à attribuer les commentaires à votre site spécifique.
    -   *Lorsqu'il est laissé vide :* Les commentaires apparaîtront toujours, mais vous n'aurez pas les capacités de modération avancées via les outils de développement de Facebook. Vous vous fierez au filtrage anti-spam par défaut de Facebook.
-   **Valeur recommandée :** Il est fortement recommandé de créer une application Facebook et d'entrer votre ID d'application ici pour un meilleur contrôle et une meilleure modération.
-   **Scénario/exemple marchand :** Vous voulez vous assurer que tous les commentaires sont appropriés et pertinents. En configurant un ID d'application Facebook, vous pouvez facilement modérer les commentaires directement depuis le tableau de bord des développeurs de Facebook, en supprimant le spam ou le contenu inapproprié.

#### 2.1.2 Nombre de commentaires

-   **Ce que fait ce paramètre :** Il contrôle le nombre de commentaires initialement affichés dans la boîte de commentaires Facebook avant que les utilisateurs ne doivent cliquer sur "Voir plus de commentaires" ou "Charger plus" pour voir les plus anciens.
-   **Effet de la modification de ce paramètre :**
    -   *Lorsqu'il est défini sur un nombre faible (par exemple, 5) :* La section des commentaires sera plus compacte, obligeant les utilisateurs à cliquer pour en voir plus. Cela peut être utile pour les pages avec un espace limité ou si vous voulez que le chargement initial de la page soit plus léger.
    -   *Lorsqu'il est défini sur un nombre plus élevé (par exemple, 20) :* Plus de commentaires seront visibles immédiatement, offrant plus de preuve sociale en un coup d'œil. Cependant, cela pourrait rendre la page produit plus longue.
-   **Valeur recommandée :** 5 à 10 commentaires est un bon point de départ pour équilibrer la visibilité et la longueur de la page. Ajustez en fonction de la conception de votre page produit et du volume de commentaires typique.
-   **Scénario/exemple marchand :** Pour les produits populaires avec de nombreux commentaires, vous pouvez le définir sur 5 pour garder la page propre. Pour les nouveaux produits, le définir sur 10 pourrait encourager plus d'interaction en affichant plus de commentaires existants.

#### 2.1.3 Largeur de la boîte de commentaires

-   **Ce que fait ce paramètre :** Il détermine la largeur de la boîte de commentaires Facebook en pixels.
-   **Effet de la modification de ce paramètre :**
    -   *Lorsqu'il est défini sur une valeur en pixels spécifique (par exemple, 600px) :* La boîte de commentaires conservera cette largeur fixe, créant potentiellement un espace vide ou un débordement si la zone de contenu de votre thème est plus étroite ou plus large.
    -   *Lorsqu'il est laissé vide ou défini sur 100% (si pris en charge par le module) :* La boîte de commentaires tentera de s'adapter automatiquement à la largeur disponible de son conteneur parent, la rendant réactive.
-   **Valeur recommandée :** Laissez vide pour la détection automatique ou définissez sur 100% si le module le prend en charge, pour assurer la réactivité. Si vous avez besoin d'une largeur fixe, assurez-vous qu'elle correspond à la zone de contenu de votre thème.
-   **Scénario/exemple marchand :** La colonne de contenu principale de votre page produit a une largeur de 700px. Vous pouvez définir la largeur à 700px pour remplir parfaitement cet espace. Si vous voulez qu'elle s'adapte au mobile, la laisser vide est généralement la meilleure option.

#### 2.1.4 Langue de la boîte de commentaires

-   **Ce que fait ce paramètre :** Il vous permet de spécifier la langue de l'interface du plugin Commentaires Facebook (par exemple, "Écrire un commentaire...", "Voir plus de commentaires").
-   **Effet de la modification de ce paramètre :**
    -   *Lorsqu'il est défini sur un code de langue spécifique (par exemple, "en\_US" pour l'anglais, "fr\_FR" pour le français) :* Le texte du plugin Facebook sera affiché dans cette langue, quelle que soit la langue du navigateur de l'utilisateur ou la langue active de votre boutique PrestaShop.
    -   *Lorsqu'il est laissé vide :* Facebook tentera généralement de détecter la langue préférée de l'utilisateur ou la langue de votre boutique PrestaShop.
-   **Valeur recommandée :** Il est généralement préférable de laisser ce champ vide afin que Facebook puisse détecter automatiquement la langue de l'utilisateur, ou de le définir sur la langue principale de votre boutique si vous souhaitez une cohérence.
-   **Scénario/exemple marchand :** Si votre boutique cible principalement des clients en Allemagne, vous pouvez le définir sur "de\_DE" pour vous assurer que tout le texte du plugin Facebook est en allemand, même si le navigateur d'un utilisateur est configuré en anglais.

#### 2.1.5 Position de la boîte de commentaires

-   **Ce que fait ce paramètre :** Il détermine où la boîte de commentaires Facebook sera affichée sur la page produit. Vous pouvez choisir parmi différents hooks PrestaShop.
-   **Effet de la modification de ce paramètre :**
    -   *Lorsqu'il est défini sur `displayProductButtons` (ou similaire) :* La boîte de commentaires peut apparaître près du bouton "Ajouter au panier" ou d'autres actions produit.
    -   *Lorsqu'il est défini sur `displayFooterProduct` (ou similaire) :* La boîte de commentaires apparaîtra plus bas sur la page produit, souvent sous les détails principaux du produit, ce qui est un emplacement courant et généralement préféré.
    -   *Lorsqu'il est défini sur `displayRightColumn` ou `displayLeftColumn` (si disponible) :* La boîte de commentaires apparaîtrait dans l'une des colonnes latérales de votre boutique, ce qui est moins courant pour les commentaires et pourrait ne pas être idéal visuellement.
-   **Valeur recommandée :** `displayFooterProduct` ou un hook similaire qui place la section des commentaires sous les informations principales du produit est généralement le placement le plus naturel et le plus efficace.
-   **Scénario/exemple marchand :** Vous voulez que les commentaires soient visibles mais ne détournent pas l'attention de l'objectif principal d'ajouter le produit au panier. Le placer dans `displayFooterProduct` garantit que les clients voient d'abord tous les détails du produit, puis peuvent interagir avec les commentaires.

#### 2.1.6 Activer les commentaires Facebook

-   **Ce que fait ce paramètre :** Il s'agit d'un simple interrupteur ON/OFF pour activer ou désactiver l'ensemble de la fonctionnalité des commentaires Facebook.
-   **Effet de la modification de ce paramètre :**
    -   *Lorsqu'il est activé (OUI) :* La boîte de commentaires Facebook apparaîtra sur vos pages produits conformément à vos autres paramètres.
    -   *Lorsqu'il est désactivé (NON) :* La boîte de commentaires Facebook sera complètement masquée de vos pages produits, et le module ne chargera aucun script lié à Facebook.
-   **Valeur recommandée :** OUI, si vous souhaitez utiliser la fonctionnalité.
-   **Scénario/exemple marchand :** Vous avez terminé de configurer le module et souhaitez le rendre actif sur votre boutique. Vous le mettez sur OUI. Plus tard, si vous décidez de désactiver temporairement les commentaires pour la maintenance, vous pouvez le mettre sur NON.

#### 2.1.7 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Par défaut / Recommandé | Objectif et impact |
| --- | --- | --- | --- |
| Configuration du module | ID d'application Facebook | (Vide) / Recommandé : Votre ID d'application | Active les outils de modération Facebook pour les commentaires. |
| Configuration du module | Nombre de commentaires | 5-10 | Définit le nombre de commentaires initialement visibles. Affecte la longueur de la page. |
| Configuration du module | Largeur de la boîte de commentaires | (Vide) / Détection automatique (Réactif) | Définit la largeur de la section des commentaires. Vide pour la réactivité. |
| Configuration du module | Langue de la boîte de commentaires | (Vide) / Détection automatique | Définit la langue de l'interface du plugin Facebook. Vide pour la langue de l'utilisateur/de la boutique. |
| Configuration du module | Position de la boîte de commentaires | `displayFooterProduct` | Détermine où la boîte de commentaires apparaît sur la page produit. |
| Configuration du module | Activer les commentaires Facebook | OUI | Active ou désactive l'ensemble de la fonctionnalité des commentaires Facebook. |

## 3. Dépannage marchand et questions fréquemment posées (FAQ)

**Q : La boîte de commentaires Facebook n'apparaît pas sur mes pages produits. Que dois-je faire ?**
R :

1.  **Vérifiez "Activer les commentaires Facebook" :** Assurez-vous que ce paramètre dans la configuration du module est défini sur OUI.
2.  **Vérifiez la position :** Assurez-vous que le paramètre "Position de la boîte de commentaires" est défini sur un hook qui est réellement présent et rendu par votre thème sur les pages produits (par exemple, `displayFooterProduct`). Certains thèmes personnalisés peuvent ne pas utiliser tous les hooks standard.
3.  **Videz le cache :** Allez dans **Paramètres avancés > Performances** dans votre Back Office PrestaShop et cliquez sur "Vider le cache" (ou "Vider le cache Smarty"). Parfois, un ancien contenu mis en cache empêche les nouveaux modules d'apparaître.
4.  **Compatibilité du thème :** Si vous utilisez un thème fortement personnalisé, il peut remplacer les modèles de page produit standard ou supprimer les hooks nécessaires. Contactez le développeur de votre thème ou un expert PrestaShop pour obtenir de l'aide.
5.  **Problèmes de navigateur :** Essayez de vider le cache et les cookies de votre navigateur, ou testez dans une fenêtre de navigation privée.

**Q : Comment puis-je modérer les commentaires ?**
R : Si vous avez configuré un ID d'application Facebook et l'avez entré dans la configuration du module, vous pouvez modérer les commentaires directement via les outils de développement de Facebook. Allez sur [developers.facebook.com/tools/comments](https://developers.facebook.com/tools/comments). Vous devrez être connecté avec le compte Facebook associé à votre ID d'application.

**Q : Puis-je modifier le style (couleurs, polices) de la boîte de commentaires Facebook ?**
R : Le style du plugin de commentaires Facebook est largement contrôlé par Facebook lui-même pour maintenir une expérience de marque cohérente. Vous avez un contrôle très limité sur son apparence interne. Vous pouvez contrôler la largeur et son emplacement, mais pas son CSS interne.

**Q : Les commentaires Facebook ralentiront-ils mon site web ?**
R : Le plugin de commentaires Facebook charge des scripts externes de Facebook. Bien que Facebook les optimise, tout script externe peut ajouter un léger délai au chargement de la page. Le module est conçu pour charger ces scripts efficacement. Vous pouvez utiliser des outils comme Google PageSpeed Insights pour surveiller les performances de votre site.

**Q : Ai-je besoin d'une page professionnelle Facebook pour que ce module fonctionne ?**
R : Non, vous n'avez pas strictement besoin d'une page professionnelle Facebook. Cependant, si vous souhaitez utiliser les outils de modération avancés, vous aurez besoin d'un compte développeur Facebook et de créer une application Facebook de base, qui est une entité distincte d'une page professionnelle.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

### 4.1 Vue d'ensemble de l'architecture

Le module Commentaires Facebook (`facebook-comments`) est un module PrestaShop simple principalement conçu pour injecter le HTML et le SDK JavaScript du plugin social Commentaires Facebook dans les pages produits du front-office. Il suit une structure de module PrestaShop standard, utilisant des hooks pour l'injection de contenu et la classe `Configuration` pour le stockage des paramètres. Il n'introduit pas de contrôleurs, de modèles ou d'interactions AJAX complexes personnalisés.

### 4.2 Contrôleurs (`controllers/`)

-   Ce module ne contient **pas** de contrôleurs d'administration Front-Office ou Back-Office personnalisés. Toute la configuration est gérée via la méthode `getContent()` du fichier principal du module.

### 4.3 Classes et modèles de base (`classes/`)

-   Ce module ne contient **pas** de classes personnalisées ou de définitions `ObjectModel`. Toute la logique est encapsulée dans le fichier principal `facebook-comments.php`.

### 4.4 Actifs JavaScript (`views/js/`)

-   Ce module ne contient **pas** de fichiers JavaScript personnalisés. Le SDK JavaScript de Facebook est chargé directement depuis le CDN de Facebook par le template du module.

### 4.5 Feuilles de style CSS (`views/css/`)

-   Ce module ne contient **pas** de fichiers CSS personnalisés. Le style du plugin de commentaires Facebook est géré par les propres feuilles de style de Facebook.

### 4.6 Structure du template Smarty (`views/templates/`)

Ce module utilise principalement un seul fichier de template pour afficher la boîte de commentaires Facebook.

-   **Templates de hook (`views/templates/hook/`)** :
    -   `facebook-comments.tpl` : C'est le fichier de template principal.
        -   **Objectif :** Rend l'élément `div` que le SDK JavaScript de Facebook transforme en boîte de commentaires. Il inclut également le code d'initialisation du SDK JavaScript nécessaire.
        -   **Variables :**
            -   `{$facebook_app_id}` : L'ID d'application Facebook de la configuration du module.
            -   `{$facebook_comments_number}` : Le nombre de commentaires à afficher.
            -   `{$facebook_comments_width}` : La largeur de la boîte de commentaires.
            -   `{$facebook_comments_lang}` : Le code de langue du plugin.
            -   `{$product_link}` : L'URL de la page produit actuelle, utilisée par Facebook pour identifier le fil de commentaires.
        -   **Hooks :** Ce template est rendu via le hook spécifié dans la configuration du module (par exemple, `displayFooterProduct`).

### 4.7 Schéma de base de données et carte des hooks

-   **Tables de base de données** : Ce module ne crée **pas** de tables de base de données personnalisées. Tous les paramètres de configuration sont stockés dans la table `ps_configuration` à l'aide des méthodes standard `Configuration::get()` et `Configuration::updateValue()` de PrestaShop.

    -   Les clés de configuration incluent généralement :
        -   `FACEBOOK_COMMENTS_APP_ID`
        -   `FACEBOOK_COMMENTS_NUMBER`
        -   `FACEBOOK_COMMENTS_WIDTH`
        -   `FACEBOOK_COMMENTS_LANG`
        -   `FACEBOOK_COMMENTS_POSITION`
        -   `FACEBOOK_COMMENTS_ENABLED`
-   **Table des hooks enregistrés** :

| Nom du hook | Moment d'exécution | Objectif technique |
| --- | --- | --- |
| `displayHeader` | Dans la section `<head>` de chaque page. | Utilisé pour inclure le SDK JavaScript de Facebook une fois par page, garantissant qu'il est disponible avant que la boîte de commentaires ne soit rendue. |
| `displayProductButtons` | Près du bouton "Ajouter au panier" sur les pages produits. | Hook facultatif pour le rendu de la boîte de commentaires, si configuré par le marchand. |
| `displayFooterProduct` | En bas du contenu de la page produit. | Hook courant et recommandé pour le rendu de la boîte de commentaires, si configuré par le marchand. |
| `displayLeftColumn` | Dans la colonne latérale gauche des pages. | Hook facultatif pour le rendu de la boîte de commentaires, si configuré par le marchand. (Moins courant pour les commentaires). |
| `displayRightColumn` | Dans la colonne latérale droite des pages. | Hook facultatif pour le rendu de la boîte de commentaires, si configuré par le marchand. (Moins courant pour les commentaires). |
| `displayFooter` | Dans la section du pied de page de la boutique. | Hook facultatif pour le rendu de la boîte de commentaires, si configuré par le marchand. (Moins courant pour les commentaires spécifiques aux produits). |

Le module s'enregistre dynamiquement au hook choisi par le marchand dans la configuration. Le hook `displayHeader` est toujours utilisé pour charger le SDK Facebook.

## 5. Support officiel et mises à jour

Pour les dernières mises à jour, corrections de bugs et support officiel du module Commentaires Facebook, veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu/my-account/orders/). Notre équipe de support est disponible pour vous aider avec tout problème ou question concernant la fonctionnalité du module.
