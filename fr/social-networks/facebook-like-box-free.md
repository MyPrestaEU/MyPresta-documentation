---
title: "Facebook Like Box Free - Manuel Marchand & Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop Facebook Like Box Free par MyPresta.eu."
sidebar:
  label: "Facebook Like Box Free - Manuel Marchand & Guide de Configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Facebook Like Box Free sur MyPresta.eu](https://mypresta.eu/modules/social-networks/facebook-like-box-free.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/social-networks/facebook-like-box-free/)
>
> ---


# Facebook Like Box Free

## 1. Exigences et compatibilité

- **Versions PrestaShop prises en charge :** PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilité PHP :** PHP 7.1 - 8.5
- **Exigences d'hébergement :** Les extensions PHP standard (cURL, JSON, OpenSSL) sont généralement requises par PrestaShop lui-même et sont suffisantes pour ce module. Aucune exigence d'hébergement spéciale au-delà d'une configuration PrestaShop standard.

## 2. Guide de configuration complet (Chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

C'est l'écran de configuration principal et unique du module Facebook Like Box Free. Vous y trouverez tous les paramètres pour contrôler son apparence et son comportement.

| Paramètre / Option | Ce que fait ce paramètre | Effet de la modification de ce paramètre | Valeur recommandée | Scénario / exemple marchand |
| --- | --- | --- | --- | --- |
| **Activé** / **Désactivé** | Contrôle si la boîte J'aime Facebook est active et visible sur votre boutique. | *Lorsque Activé :* La boîte J'aime apparaîtra sur votre boutique à la position choisie. *Lorsque Désactivé :* La boîte J'aime sera masquée de votre boutique. | **Activé** | Vous souhaitez commencer à promouvoir votre page Facebook. |
| **Position** | Détermine où la boîte J'aime sera affichée sur votre boutique. | *Lorsque défini sur Colonne de gauche :* La boîte J'aime apparaît dans la barre latérale gauche. *Lorsque défini sur Colonne de droite :* La boîte J'aime apparaît dans la barre latérale droite. *Lorsque défini sur Page d'accueil :* La boîte J'aime apparaît dans la zone de contenu principale de votre page d'accueil. *Lorsque défini sur Pied de page :* La boîte J'aime apparaît en bas de chaque page. | **Colonne de droite** ou **Page d'accueil** | Vous souhaitez que la boîte J'aime soit bien visible sans interférer avec la visualisation des produits. |
| **URL de la page Facebook** | C'est le lien direct vers votre Page Facebook officielle. | *Lorsque défini sur l'URL de votre page (par exemple, `https://www.facebook.com/MyPrestaEU`) :* La boîte J'aime affichera le contenu et un bouton « J'aime » pour *votre* Page Facebook spécifique. *Lorsque laissé vide ou incorrect :* La boîte J'aime peut ne pas s'afficher correctement ou affichera une erreur. | L'URL réelle de votre Page Facebook | Vous souhaitez connecter les visiteurs de votre boutique à la présence Facebook de votre marque. |
| **Largeur** | Définit la largeur de la boîte J'aime en pixels. | *Lorsque défini sur une valeur en pixels spécifique (par exemple, `280`) :* La boîte J'aime aura exactement cette largeur. *Lorsque laissé vide :* Le module essaiera d'ajuster automatiquement la largeur, mais il est souvent préférable de définir une valeur spécifique pour une conception cohérente. | `280` (ou ajustez pour s'adapter à votre colonne/mise en page) | Votre colonne de droite a une largeur de 300px, vous définissez donc la largeur de la boîte J'aime à 280px pour qu'elle s'adapte bien avec un peu de rembourrage. |
| **Hauteur** | Définit la hauteur de la boîte J'aime en pixels. | *Lorsque défini sur une valeur en pixels spécifique (par exemple, `500`) :* La boîte J'aime aura exactement cette hauteur. *Lorsque laissé vide :* Le module essaiera d'ajuster automatiquement la hauteur. | `500` (ou ajustez en fonction du contenu que vous souhaitez afficher) | Vous souhaitez afficher quelques publications récentes, vous définissez donc la hauteur à 500px pour laisser suffisamment d'espace. |
| **Masquer la couverture** | Contrôle si la grande photo de couverture de votre Page Facebook est affichée en haut de la boîte J'aime. | *Lorsque activé :* La photo de couverture sera masquée, rendant la boîte J'aime plus compacte. *Lorsque désactivé :* La photo de couverture sera visible. | **Activé** (pour un look plus épuré) | Vous préférez un design minimaliste et souhaitez que la boîte J'aime prenne moins d'espace vertical. |
| **Photos de profil** (Afficher Facepile) | Détermine si les photos de profil des personnes qui aiment votre page sont affichées sous le bouton « J'aime ». | *Lorsque activé :* Une rangée de petites photos de profil apparaîtra, montrant une preuve sociale. *Lorsque désactivé :* Ces photos de profil ne seront pas affichées. | **Activé** (pour la preuve sociale) | Vous souhaitez montrer aux visiteurs que de nombreuses autres personnes aiment déjà votre page, les encourageant à faire de même. |
| **Afficher les publications** (Afficher le flux) | Contrôle si les publications récentes de votre Page Facebook sont affichées dans la boîte J'aime. | *Lorsque activé :* Vos dernières publications Facebook seront visibles, rendant la boîte J'aime plus dynamique. *Lorsque désactivé :* Seuls le bouton « J'aime » et le facepile (si activé) seront affichés. | **Activé** | Vous publiez activement sur Facebook et souhaitez présenter votre dernier contenu directement sur votre boutique. |
| **Bouton d'appel à l'action** (Masquer CTA) | Contrôle si le bouton « Appel à l'action » (par exemple, « Envoyer un message », « Acheter maintenant ») de votre Page Facebook est masqué. | *Lorsque activé :* Le bouton CTA sera masqué. *Lorsque désactivé :* Le bouton CTA sera visible s'il est configuré sur votre Page Facebook. | **Activé** (souvent pour un look plus épuré) | Vous voulez vous concentrer uniquement sur l'obtention d'un « J'aime » et ne voulez pas qu'un autre bouton distrait les visiteurs. |
| **Petit en-tête** | Rend l'en-tête de la boîte J'aime plus petit. | *Lorsque activé :* L'en-tête (contenant le nom de votre page et le bouton « J'aime ») sera plus compact. *Lorsque désactivé :* L'en-tête aura une taille standard. | **Activé** (pour un design plus compact) | Vous souhaitez que la boîte J'aime soit moins intrusive et s'intègre plus harmonieusement dans le design de votre boutique. |
| **Bibliothèque Facebook** (Inclure l'application) | Ce paramètre contrôle si le SDK JavaScript Facebook nécessaire est chargé. | *Lorsque activé :* Le module chargera le SDK Facebook, ce qui est essentiel pour que la boîte J'aime fonctionne correctement. *Lorsque désactivé :* La boîte J'aime ne s'affichera probablement pas ou ne fonctionnera pas correctement. | **Activé** | Ceci est crucial pour que la boîte J'aime fonctionne. |

#### Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Par défaut / Recommandé | Objectif et impact |
| --- | --- | --- | --- |
| Configuration du module | Activé/Désactivé | Activé | Active/Désactive la boîte J'aime sur votre boutique. |
| Configuration du module | Position | Colonne de droite / Page d'accueil | Détermine où la boîte J'aime apparaît (Colonne de gauche/droite, Page d'accueil, Pied de page). |
| Configuration du module | URL de la page Facebook | L'URL de votre page Facebook | Lie la boîte J'aime à votre page Facebook spécifique. |
| Configuration du module | Largeur | 280 | Définit la largeur de la boîte J'aime en pixels. |
| Configuration du module | Hauteur | 500 | Définit la hauteur de la boîte J'aime en pixels. |
| Configuration du module | Masquer la couverture | Activé | Masque la grande photo de couverture pour un look plus compact. |
| Configuration du module | Photos de profil (Afficher Facepile) | Activé | Affiche les photos de profil des personnes qui aiment votre page (preuve sociale). |
| Configuration du module | Afficher les publications (Afficher le flux) | Activé | Affiche les publications récentes de votre page Facebook. |
| Configuration du module | Bouton d'appel à l'action (Masquer CTA) | Activé | Masque le bouton d'appel à l'action de la page Facebook. |
| Configuration du module | Petit en-tête | Activé | Rend l'en-tête de la boîte J'aime plus compact. |
| Configuration du module | Bibliothèque Facebook (Inclure l'application) | Activé | Charge le SDK JavaScript Facebook nécessaire au fonctionnement. |

## 3. Dépannage marchand et Foire Aux Questions (FAQ)

**Q : La boîte J'aime Facebook n'apparaît pas sur ma boutique. Que dois-je faire ?**
R :

1. **Vérifier l'état du module :** Allez dans **Modules > Gestionnaire de modules** et assurez-vous que « Facebook Like Box Free » est installé et activé.
2. **Vérifier la configuration :** Allez sur la page de configuration du module.
   - Assurez-vous que « Activé » est défini sur OUI.
   - Vérifiez à nouveau que l'« URL de la page Facebook » est correcte et complète (par exemple, `https://www.facebook.com/MyPrestaEU`).
   - Assurez-vous que la « Bibliothèque Facebook » (Inclure l'application) est activée.
3. **Vider le cache :** Allez dans **Paramètres avancés > Performances** et cliquez sur « Vider le cache » (ou « Vider le cache Smarty » dans les versions antérieures). Parfois, d'anciens fichiers mis en cache empêchent l'apparition de nouveaux modules.
4. **Vérifier la position du hook :** Assurez-vous que la « Position » que vous avez sélectionnée (par exemple, Colonne de droite, Page d'accueil) est réellement active dans votre thème. Certains thèmes peuvent ne pas afficher certaines colonnes. Vous pouvez vérifier **Design > Positions** pour voir si le module est correctement accroché.

**Q : La boîte J'aime semble trop large/étroite ou trop haute/courte.**
R : Ajustez les paramètres « Largeur » et « Hauteur » sur la page de configuration du module. Expérimentez avec différentes valeurs en pixels jusqu'à ce qu'elle s'adapte parfaitement à la mise en page de votre thème. N'oubliez pas de vider le cache de votre navigateur après avoir effectué des modifications pour voir la mise à jour.

**Q : J'ai modifié les paramètres, mais rien ne s'est passé sur ma boutique.**
R : Après avoir enregistré les modifications dans la configuration du module, videz toujours le cache de votre PrestaShop (**Paramètres avancés > Performances > Vider le cache**) puis videz le cache de votre navigateur (Ctrl+F5 ou Cmd+R) pour vous assurer de voir la dernière version de votre boutique.

**Q : La boîte J'aime affiche un message d'erreur ou ne charge pas le contenu.**
R :

1. **URL incorrecte :** La raison la plus courante est une « URL de page Facebook » incorrecte. Vérifiez-la deux fois pour les fautes de frappe.
2. **Problèmes d'API Facebook :** Occasionnellement, il peut y avoir des problèmes temporaires avec l'API de Facebook. Attendez un peu et vérifiez à nouveau.
3. **Conflits de thème :** Rarement, le JavaScript ou le CSS de votre thème peut entrer en conflit. Si les étapes ci-dessus ne fonctionnent pas, essayez de passer temporairement au thème PrestaShop par défaut pour exclure un conflit de thème.

**Q : Puis-je traduire le texte « J'aime la Page » dans d'autres langues ?**
R : Le texte à l'intérieur de la boîte J'aime Facebook elle-même (comme « J'aime la Page » ou le contenu des publications) est contrôlé par Facebook et s'adaptera automatiquement aux paramètres de langue Facebook de l'utilisateur. Les paramètres du back-office du module sont traduisibles via **International > Traductions** dans PrestaShop.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

Cette section fournit un aperçu technique pour les développeurs et les webmasters travaillant avec le module Facebook Like Box Free.

### 4.1 Aperçu de l'architecture

Le module `Facebook Like Box Free` est un module PrestaShop simple principalement conçu pour intégrer le plugin de page Facebook (anciennement Like Box) à l'aide du SDK JavaScript officiel de Facebook. Il suit une structure de module PrestaShop de base, tirant parti de la classe `Module` pour l'installation, la désinstallation et la configuration. Sa fonctionnalité principale tourne autour de l'affichage du widget Facebook via un template Smarty accroché à diverses positions du front-office. Il n'y a pas de tables de base de données personnalisées ou d'ObjectModels complexes impliqués ; toute la configuration est stockée dans `ps_configuration`.

### 4.2 Contrôleurs (`controllers/`)

Ce module ne contient **pas** de contrôleurs d'administration Front-Office ou Back-Office personnalisés. Toute la logique est encapsulée dans le fichier principal du module (`likeboxfree.php`).

### 4.3 Classes et modèles principaux (`classes/`)

Ce module ne définit **pas** de classes ou d'ObjectModels personnalisés dans le répertoire `classes/`. Toute la logique du module réside dans le fichier principal `likeboxfree.php`.

### 4.4 Actifs JavaScript (`views/js/`)

Ce module n'inclut **pas** de fichiers JavaScript personnalisés dans `views/js/`.
Le SDK JavaScript de Facebook est chargé dynamiquement par le template du module si le paramètre `lbf_includeapp` est activé. Ceci est géré par le propre script de Facebook, et non par un script de module personnalisé.

### 4.5 Feuilles de style CSS (`views/css/`)

- **`likeboxfree/css.css`**
  - **Portée :** Style client du front-office.
  - **Principaux composants et conteneurs d'interface utilisateur qu'il stylise :** Ce fichier fournit un style de base pour l'enveloppe autour de la boîte J'aime Facebook afin de garantir qu'elle s'intègre proprement dans la mise en page de PrestaShop, en particulier pour les hooks de colonne. Il peut contenir des règles pour le rembourrage, les marges ou la réactivité de base.
  - **Sélecteurs de classe CSS clés que les développeurs peuvent surcharger :** Les développeurs peuvent inspecter le code HTML généré pour trouver l'élément enveloppant (par exemple, une `div` avec un ID ou une classe spécifique générée par le module) et surcharger ses styles dans le `custom.css` ou `theme.css` de leur thème.

### 4.6 Structure du template Smarty (`views/templates/`)

- **Templates de hook (`views/templates/hook/`)** :
  - **`likeboxfree/rightcolumn.tpl`**
    - **Accroché à :** `displayHome`, `displayFooter`, `displayRightColumn`, `displayLeftColumn` (selon la configuration `likeboxfree_position`).
    - **Sortie du bloc visuel :** Ce template est responsable du rendu de la structure HTML qui intègre le plugin de page Facebook. Il génère dynamiquement l'élément `div` avec la classe `fb-page` et les attributs de données (`data-href`, `data-width`, `data-height`, etc.) basés sur les paramètres de configuration du module. Il inclut également le snippet JavaScript nécessaire pour initialiser le SDK Facebook et analyser le plugin.

### 4.7 Schéma de la base de données et carte des hooks

- **Tables de base de données** :
  Ce module ne crée aucune table de base de données personnalisée. Tous les paramètres de configuration sont stockés dans la table `ps_configuration` à l'aide de clés préfixées par `likeboxfree_` ou `lbf_`.

  - Entrées `ps_configuration` :
    - `likeboxfree_position` : Stocke la position de hook choisie (par exemple, `displayRightColumn`).
    - `lbf_width` : Largeur de la boîte J'aime.
    - `lbf_height` : Hauteur de la boîte J'aime.
    - `lbf_hide_cover` : Booléen (0/1) pour masquer la photo de couverture.
    - `lbf_show_facepile` : Booléen (0/1) pour afficher les photos de profil.
    - `lbf_show_posts` : Booléen (0/1) pour afficher les publications.
    - `lbf_hide_cta` : Booléen (0/1) pour masquer le bouton d'appel à l'action.
    - `lbf_small_header` : Booléen (0/1) pour un petit en-tête.
    - `lbf_url` : L'URL de la page Facebook.
    - `lbf_includeapp` : Booléen (0/1) pour inclure le SDK Facebook.
    - (Des clés héritées/inutilisées peuvent également exister à partir d'anciennes versions, mais celles ci-dessus sont actives).
- **Table des hooks enregistrés** :

| Nom du hook | Moment d'exécution | But technique |
| --- | --- | --- |
| `displayHome` | Rend le contenu sur la page d'accueil. | Affiche la boîte J'aime Facebook sur la zone de contenu principale de la page d'accueil si configuré. |
| `displayFooter` | Rend le contenu dans le pied de page de la boutique. | Affiche la boîte J'aime Facebook en bas de chaque page si configuré. |
| `displayRightColumn` | Rend le contenu dans la barre latérale droite. | Affiche la boîte J'aime Facebook dans la colonne de droite des pages si configuré. |
| `displayLeftColumn` | Rend le contenu dans la barre latérale gauche. | Affiche la boîte J'aime Facebook dans la colonne de gauche des pages si configuré. |

Les méthodes `hookDisplay*` du module vérifient la valeur de configuration `likeboxfree_position` et ne rendent le template `rightcolumn.tpl` que si le hook actuel correspond à la position configurée.

## 5. Support officiel et mises à jour

Pour les dernières mises à jour, corrections de bugs et support officiel du module « Facebook Like Box Free », veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu/). Notre équipe de support est disponible pour vous aider avec tout problème ou question que vous pourriez avoir concernant la fonctionnalité et l'intégration du module.
