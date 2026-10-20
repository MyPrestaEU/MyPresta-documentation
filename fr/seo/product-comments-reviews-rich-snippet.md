---
title: "Commentaires produits - Rich snippet d'avis - Manuel du marchand et guide de configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop 'Commentaires produits - Rich snippet d'avis' par MyPresta.eu."
sidebar:
  label: "Commentaires produits - Rich snippet d'avis - Manuel du marchand et guide de configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Product Comments - Reviews rich snippet sur MyPresta.eu](https://mypresta.eu/modules/seo/product-comments-reviews-rich-snippet.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/seo/product-comments-reviews-rich-snippet/)
>
> ---


# Commentaires produits - Rich snippet d'avis

## 1. Exigences et compatibilité

- **Versions PrestaShop prises en charge** : PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilité PHP** : PHP 5.6 - 8.5
- **Exigences d'hébergement** : Extensions PHP standard (cURL, JSON, OpenSSL).
- **Dépendance** : Ce module étend les fonctionnalités du **module gratuit PrestaShop Commentaires produits**. Vous devez avoir le module officiel PrestaShop Commentaires produits installé et actif pour que ce module fonctionne correctement.

## 2. Guide de configuration complet (chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

Ce module dispose d'une page de configuration simple, principalement axée sur l'activation ou la désactivation de sa fonctionnalité principale et la sélection de l'endroit où les données du rich snippet doivent être injectées.

**Pour y accéder :** Allez dans **Modules > Gestionnaire de modules**, recherchez « Commentaires produits - Rich snippet d'avis » et cliquez sur « Configurer ».

#### **Activer / Désactiver les Rich Snippets**

- **Ce que fait ce paramètre :** C'est l'interrupteur principal pour activer ou désactiver la fonctionnalité principale du module. Lorsqu'il est activé, le module commencera à ajouter les données structurées nécessaires à vos pages produits.
- **Effet de la modification de ce paramètre :**
  - *Lorsqu'il est activé :* Le module injectera le code du rich snippet dans vos pages produits, permettant à Google d'afficher les étoiles et le nombre d'avis dans les résultats de recherche.
  - *Lorsqu'il est désactivé :* Le module cessera d'injecter le code du rich snippet. Vos listes de produits dans les résultats de recherche Google reviendront au texte standard, sans étoiles ni nombre d'avis.
- **Valeur recommandée :** **OUI** (Activé). L'objectif principal de ce module est d'afficher des rich snippets, il devrait donc presque toujours être activé.
- **Scénario / exemple pour le marchand :** Si vous testez le module ou si vous souhaitez temporairement masquer les données d'avis des résultats de recherche (par exemple, lors d'une refonte majeure du site), vous pourriez le désactiver. Sinon, gardez-le activé pour maximiser la visibilité.

#### **Afficher les Rich Snippets dans le Hook**

- **Ce que fait ce paramètre :** Cette option vous permet de choisir *où* sur votre page produit le module doit injecter les données structurées. Bien que les données soient invisibles pour le client, leur emplacement peut parfois affecter la compatibilité avec les thèmes ou d'autres modules.
- **Effet de la modification de ce paramètre :**
  - *Lorsqu'il est défini sur 'Header' :* Les données du rich snippet seront placées dans la section `<head>` du HTML de votre page produit. C'est généralement l'emplacement le plus courant et recommandé pour les données structurées.
  - *Lorsqu'il est défini sur 'Product' :* Les données du rich snippet seront placées dans la zone de contenu principal du produit.
  - *Lorsqu'il est défini sur 'Columns' :* Les données du rich snippet seront placées dans l'une des colonnes latérales de votre boutique (gauche ou droite, selon la mise en page de votre thème).
  - *Lorsqu'il est défini sur 'Footer' :* Les données du rich snippet seront placées dans la section `<footer>` du HTML de votre page produit.
- **Valeur recommandée :** **Header**. C'est l'emplacement le plus standard et le plus robuste pour les données structurées, car il est traité tôt par les robots des moteurs de recherche et est moins susceptible d'entrer en conflit avec des éléments visuels ou d'autres scripts sur votre page.
- **Scénario / exemple pour le marchand :** Si vous rencontrez des problèmes inattendus avec la mise en page de votre page produit ou d'autres modules après avoir activé les rich snippets, vous pourriez essayer de changer ce hook en 'Product' ou 'Footer' comme étape de dépannage. Cependant, 'Header' est généralement le pari le plus sûr.

#### **Afficher les Rich Snippets courts (uniquement les étoiles)**

- **Ce que fait ce paramètre :** Cette option vous permet de choisir entre afficher le rich snippet complet (étoiles + nombre d'avis) ou une version « courte » qui n'affiche que les étoiles, sans le nombre d'avis.
- **Effet de la modification de ce paramètre :**
  - *Lorsqu'il est activé :* Google n'affichera que la note en étoiles (par exemple, « ★★★★★ 4.5 ») dans les résultats de recherche, omettant la partie « (X avis) ».
  - *Lorsqu'il est désactivé :* Google affichera à la fois la note en étoiles et le nombre d'avis (par exemple, « ★★★★★ 4.5 (12 avis) »).
- **Valeur recommandée :** **NON** (Désactivé). L'affichage des étoiles et du nombre d'avis fournit des informations plus complètes et renforce souvent la confiance, surtout si vous avez un grand nombre d'avis.
- **Scénario / exemple pour le marchand :** Si vous avez très peu d'avis sur de nombreux produits, et que vous pensez que l'affichage de « 1 avis » pourrait paraître moins impressionnant que les étoiles seules, vous pourriez activer cette option. Cependant, pour la plupart des boutiques avec un nombre sain d'avis, l'affichage du compte est bénéfique.

### 2.2 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Valeur par défaut / Recommandée | Objectif et impact |
| --- | --- | --- | --- |
| Configuration du module | Activer / Désactiver les Rich Snippets | OUI (Activé) | Active/désactive l'injection du code rich snippet pour les résultats de recherche Google. |
| Configuration du module | Afficher les Rich Snippets dans le Hook | Header | Détermine où le code rich snippet invisible est placé sur la page produit. 'Header' est généralement le meilleur pour la compatibilité. |
| Configuration du module | Afficher les Rich Snippets courts (uniquement les étoiles) | NON (Désactivé) | Contrôle si seules les étoiles ou les étoiles + le nombre d'avis sont affichés dans les résultats de recherche Google. Il est recommandé d'afficher les deux. |

## 3. Dépannage pour les marchands et questions fréquemment posées (FAQ)

**Q : J'ai installé le module, mais je ne vois pas d'étoiles dans les résultats de recherche Google. Qu'est-ce qui ne va pas ?**
R : Plusieurs facteurs peuvent être en jeu :
1. **Temps d'exploration de Google :** Il faut du temps à Google pour réexplorer votre site web et mettre à jour son index. Cela peut prendre de quelques jours à quelques semaines, surtout pour les nouvelles pages ou les changements importants.
2. **Cache :** Videz le cache de votre PrestaShop (Paramètres avancés > Performances > Vider le cache) après la configuration.
3. **Google Search Console :** Vérifiez votre Google Search Console pour les « Extraits d'avis » sous « Améliorations ». S'il y a des erreurs, Google pourrait ne pas afficher les extraits.
4. **Pas d'avis :** Assurez-vous que le produit a réellement des avis approuvés dans votre boutique. Google n'affichera pas d'étoiles s'il n'y a pas d'avis.
5. **Module Commentaires produits :** Vérifiez que le module officiel PrestaShop Commentaires produits est installé et actif. Ce module en dépend.
6. **Discrétion de Google :** Bien que le module fournisse les données, Google décide en fin de compte d'afficher ou non les rich snippets. Il peut choisir de ne pas les afficher s'il estime que le contenu est non pertinent ou de faible qualité.

**Q : Ma page produit semble cassée après l'installation du module.**
R : C'est très peu probable car le module n'injecte que des données structurées invisibles. Cependant, si cela se produit :
1. **Désactivez le module :** Allez dans le Gestionnaire de modules et désactivez « Commentaires produits - Rich snippet d'avis ». Si la page redevient normale, le module pourrait en être la cause.
2. **Modifiez le paramètre « Afficher les Rich Snippets dans le Hook » :** Essayez de changer le hook de 'Header' à 'Product' ou 'Footer'. Parfois, des conflits de thème peuvent survenir avec des placements de hook spécifiques.
3. **Videz le cache :** Videz toujours le cache de votre PrestaShop après avoir effectué des modifications.

**Q : Ce module affecte-t-il la vitesse de chargement de mon site web ?**
R : Non, l'impact sur la vitesse de chargement est négligeable. Le module n'ajoute qu'un petit bloc de texte (données structurées) au HTML de votre page, qui est très léger et traité rapidement par les navigateurs et les moteurs de recherche.

**Q : Puis-je personnaliser l'apparence des étoiles dans les résultats de recherche Google ?**
R : Non, l'apparence des étoiles et du nombre d'avis dans les résultats de recherche Google est entièrement contrôlée par l'interface de Google. Ce module fournit les données ; Google les affiche. Vous ne pouvez pas modifier la couleur, la taille ou le style des étoiles dans les résultats de recherche.

**Q : Ce module fonctionnera-t-il avec des thèmes personnalisés ?**
R : Oui, ce module est conçu pour fonctionner indépendamment du style visuel de votre thème. Il injecte des données structurées dans le HTML, ce qui est une pratique standard. Tant que votre thème personnalisé implémente correctement le système de hooks de PrestaShop, le module devrait fonctionner sans problème.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

Cette section fournit une analyse approfondie de l'architecture technique du module « Commentaires produits - Rich snippet d'avis », destinée aux développeurs, webmasters et agences techniques.

### 4.1 Vue d'ensemble de l'architecture

Le module `prrs` (Product Reviews Rich Snippet) est un module PrestaShop léger conçu pour injecter des données structurées `AggregateRating` de Schema.org dans les pages produits. Il exploite les données existantes du module officiel `productcomments`. Le module fonctionne principalement en se rattachant à un point d'affichage (configurable par le marchand) et en rendant un template Smarty contenant les données structurées JSON-LD. Il suit une structure de module PrestaShop standard, avec une classe de module principale et quelques ressources de support.

### 4.2 Contrôleurs (`controllers/`)

Ce module ne contient aucun contrôleur Front-Office ou Back-Office personnalisé. Toute la logique est gérée dans le fichier principal du module `index.php` et ses templates associés.

### 4.3 Classes et modèles principaux (`classes/`)

Ce module ne définit aucune classe personnalisée et n'étend pas `ObjectModel`. Il s'appuie principalement sur les fonctionnalités de base existantes de PrestaShop et les données du module `productcomments`.

### 4.4 Ressources JavaScript (`views/js/`)

- **`prrs/lib/searchTool/views/js/autocomplete.js`**
  - **Portée :** Back-office (probablement pour un outil de recherche interne, bien que non directement utilisé par la fonctionnalité de rich snippet principale du module).
  - **Responsabilité :** Ce script semble faire partie d'un utilitaire d'autocomplétion générique. Il gère probablement les requêtes AJAX pour les suggestions de recherche, met à jour les champs de saisie et gère l'affichage des résultats de recherche dans une liste déroulante. Compte tenu de la fonction principale du module, il pourrait s'agir d'un reste ou d'une dépendance d'une bibliothèque partagée. Il n'est pas directement impliqué dans la génération du rich snippet.

### 4.5 Feuilles de style CSS (`views/css/`)

- **`prrs/lib/searchTool/views/css/autocomplete.css`**
  - **Portée :** Back-office.
  - **Responsabilité :** Fournit le style pour l'outil de recherche d'autocomplétion mentionné ci-dessus. Cela inclurait les styles pour la saisie de recherche, les suggestions déroulantes, les résultats mis en évidence, etc. Non pertinent pour l'affichage en front-office.
- **`prrs/views/css/prrs.css`**
  - **Portée :** Front-office.
  - **Responsabilité :** Cette feuille de style est probablement minimale ou vide, car la fonction principale du module est d'injecter des données structurées invisibles. Si elle contient des styles, ils seraient pour des éléments très subtils et non intrusifs, ou potentiellement pour un affichage visuel de secours si les données structurées elles-mêmes avaient un composant visible (ce qui n'est généralement pas le cas pour les rich snippets). Les développeurs devraient vérifier ce fichier pour toute sortie visuelle inattendue.

### 4.6 Structure des templates Smarty (`views/templates/`)

- **`prrs/lib/searchTool/views/scripts.tpl`**
  - **Portée :** Back-office.
  - **Objectif :** Ce template inclut probablement le JavaScript pour l'outil de recherche d'autocomplétion (`autocomplete.js`) et potentiellement d'autres scripts ou configurations de scripts en ligne. Il serait rendu dans un contexte d'administration.
- **`prrs/views/templates/prrs-json.tpl`**
  - **Portée :** Front-office (page produit).
  - **Objectif :** C'est le template principal responsable de la génération des données structurées JSON-LD pour le rich snippet `AggregateRating`. Il récupère dynamiquement la note moyenne du produit et le nombre d'avis du module `productcomments` et les formate selon les spécifications de Schema.org. Ce template est rendu lorsque l'option « Afficher les Rich Snippets courts » est désactivée.
  - **Points de données clés :** `product.id_product`, `product.name`, `product.link_rewrite`, `product.link`, `product.cover.bySize.home_default.url`, `average_grade`, `nb_comments`.
- **`prrs/views/templates/prrs.tpl`**
  - **Portée :** Front-office (page produit).
  - **Objectif :** Ce template est probablement un wrapper ou une alternative à `prrs-json.tpl`, potentiellement utilisé pour les anciennes versions de PrestaShop ou des intégrations de hooks spécifiques. Il génère également les données du rich snippet. Il est important de vérifier quel template est activement utilisé en fonction de la logique `getContent()` du module et de l'enregistrement des hooks.
- **`prrs/views/templates/shortprrs.tpl`**
  - **Portée :** Front-office (page produit).
  - **Objectif :** Ce template génère un extrait de données structurées JSON-LD simplifié, incluant généralement uniquement la note moyenne en étoiles sans le nombre explicite d'avis. Il est rendu lorsque l'option « Afficher les Rich Snippets courts » est activée.

### 4.7 Schéma de base de données et carte des Hooks

- **Tables de base de données** :

  - Ce module ne crée aucune table de base de données personnalisée.
  - Il s'appuie sur la table `ps_configuration` pour stocker ses paramètres (par exemple, `PRRS_ENABLED`, `PRRS_HOOK`, `PRRS_SHORT`).
  - Il récupère les données d'avis des tables créées par le module officiel `productcomments` (par exemple, `ps_product_comment`, `ps_product_comment_criterion`).
- **Table des Hooks enregistrés** :

| Nom du Hook | Moment d'exécution / Contexte | Objectif technique |
| --- | --- | --- |
| `displayHeader` | Rendu dans la section `<head>` de la page. | Injecte les données structurées JSON-LD pour les rich snippets tôt dans le chargement de la page. Configurable via les paramètres du module. |
| `displayProductAdditionalInfo` | Rendu dans la page produit, généralement sous les détails principaux du produit. | Hook alternatif pour l'injection de données structurées JSON-LD. Configurable via les paramètres du module. |
| `displayLeftColumn` / `displayRightColumn` | Rendu dans les colonnes latérales respectives. | Moins courant, mais disponible comme hook alternatif pour l'injection de données structurées JSON-LD. Configurable via les paramètres du module. |
| `displayFooter` | Rendu dans la section `<footer>` de la page. | Hook alternatif pour l'injection de données structurées JSON-LD, généralement à la fin de la page. Configurable via les paramètres du module. |
| `actionFrontControllerSetMedia` | Exécuté lorsqu'un contrôleur frontal définit ses ressources média. | Utilisé pour enregistrer les fichiers CSS et JavaScript pour le front office. |
| `actionAdminControllerSetMedia` | Exécuté lorsqu'un contrôleur d'administration définit ses ressources média. | Utilisé pour enregistrer les fichiers CSS et JavaScript pour le back office (par exemple, `autocomplete.js`, `autocomplete.css`). |

## 5. Support officiel et mises à jour

Pour les dernières mises à jour du module, les corrections de bugs et le support officiel, veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu/my-account/orders/). Notre équipe de support est disponible pour vous aider avec toutes les questions ou problèmes concernant le module « Commentaires produits - Rich snippet d'avis ».
