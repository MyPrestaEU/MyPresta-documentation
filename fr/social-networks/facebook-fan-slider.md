---
title: "Facebook Fan Slider - Manuel Marchand & Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop Facebook Fan Slider par MyPresta.eu."
sidebar:
  label: "Facebook Fan Slider - Manuel Marchand & Guide de Configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Facebook Fan Slider sur MyPresta.eu](https://mypresta.eu/modules/social-networks/facebook-fan-slider.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/social-networks/facebook-fan-slider/)
>
> ---


# Facebook Fan Slider

## 1. Exigences et compatibilité

- **Versions PrestaShop prises en charge** : PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilité PHP** : PHP 5.6 - 8.5
- **Exigences d'hébergement** : Les extensions PHP standard (cURL, JSON, OpenSSL) sont requises pour PrestaShop lui-même et généralement disponibles sur tous les environnements d'hébergement modernes. Aucune configuration de serveur spéciale n'est nécessaire au-delà d'une installation PrestaShop standard.

## 2. Guide de configuration complet (Chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

Pour accéder aux paramètres du module, allez dans **Modules > Gestionnaire de modules**, recherchez "Facebook Fan Slider", et cliquez sur le bouton "Configurer".

Voici une description détaillée de chaque paramètre :

- **URL de la page Facebook (fs\_url)**

  - **Ce que fait ce paramètre :** C'est le paramètre le plus crucial. Il indique au module quelle page Facebook spécifique afficher dans la boîte coulissante.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est défini sur l'URL de votre page Facebook :* Le module récupérera et affichera la boîte "J'aime"/Page Plugin pour cette page exacte.
    - *Lorsqu'il est laissé vide ou défini incorrectement :* Le module n'affichera pas le contenu Facebook, ou il affichera une erreur, car il ne saura pas à quelle page se connecter.
  - **Valeur recommandée :** Saisissez l'URL complète de votre page Facebook (par exemple, `https://www.facebook.com/MyPresta.eu`).
  - **Scénario / exemple marchand :** Si la page de votre entreprise est `https://www.facebook.com/MyAwesomeShop`, vous saisiriez cette URL ici.
- **Largeur (fs\_width)**

  - **Ce que fait ce paramètre :** Contrôle la largeur de la boîte "J'aime"/Page Plugin Facebook *à l'intérieur* du panneau coulissant, en pixels.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est défini sur une valeur en pixels spécifique (par exemple, 280) :* Le contenu Facebook aura exactement cette largeur.
    - *Lorsqu'il est défini sur une valeur plus petite :* Le contenu pourrait apparaître compressé ou certains éléments pourraient être coupés.
    - *Lorsqu'il est défini sur une valeur plus grande :* Le contenu s'étendra, mais assurez-vous qu'il ne dépasse pas la largeur de l'écran ou ne semble pas disproportionné.
  - **Valeur recommandée :** Commencez par `280` ou `300` pixels. Ajustez en fonction de la quantité de contenu que vous affichez (par exemple, si vous affichez des publications, vous pourriez avoir besoin de plus de largeur).
  - **Scénario / exemple marchand :** Vous voulez que la boîte coulissante soit suffisamment large pour afficher clairement la photo de couverture de votre page et le bouton "J'aime" sans être trop encombrante.
- **Hauteur (fs\_height)**

  - **Ce que fait ce paramètre :** Contrôle la hauteur de la boîte "J'aime"/Page Plugin Facebook *à l'intérieur* du panneau coulissant, en pixels.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est défini sur une valeur en pixels spécifique (par exemple, 400) :* Le contenu Facebook aura exactement cette hauteur.
    - *Lorsqu'il est défini sur une valeur plus petite :* Le contenu pourrait être coupé, obligeant les utilisateurs à faire défiler la boîte.
    - *Lorsqu'il est défini sur une valeur plus grande :* La boîte sera plus haute, occupant potentiellement plus d'espace à l'écran.
  - **Valeur recommandée :** Commencez par `400` ou `500` pixels. Si vous activez "Afficher les publications", vous aurez probablement besoin de plus de hauteur (par exemple, `600-700px`) pour afficher quelques publications sans trop de défilement.
  - **Scénario / exemple marchand :** Vous voulez afficher quelques publications récentes de votre page Facebook, vous augmentez donc la hauteur à `600px` pour les rendre visibles.
- **Masquer la photo de couverture (fs\_hide\_cover)**

  - **Ce que fait ce paramètre :** Détermine si la grande photo de couverture de votre page Facebook est affichée en haut de la boîte "J'aime"/Page Plugin.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé (coché) :* La photo de couverture ne sera pas affichée, rendant la boîte "J'aime" plus compacte.
    - *Lorsqu'il est désactivé (décoché) :* La photo de couverture sera affichée, rendant la boîte "J'aime" visuellement plus riche mais aussi plus haute.
  - **Valeur recommandée :** *Désactivé* (décoché) si vous voulez une boîte plus attrayante visuellement. *Activé* (coché) si vous avez besoin de gagner de l'espace vertical.
  - **Scénario / exemple marchand :** Vous avez une belle photo de couverture sur Facebook et vous voulez la mettre en valeur, vous laissez donc cette option décochée. Si vous manquez d'espace, vous pourriez la cocher.
- **Afficher les visages des amis (fs\_show\_facepile)**

  - **Ce que fait ce paramètre :** Contrôle si les photos de profil des amis qui aiment déjà votre page sont affichées sous le bouton "J'aime".
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé (coché) :* Une rangée de photos de profil d'amis mutuels qui aiment votre page apparaîtra, ajoutant une preuve sociale.
    - *Lorsqu'il est désactivé (décoché) :* Ces photos de profil ne seront pas affichées.
  - **Valeur recommandée :** *Activé* (coché). La preuve sociale peut encourager d'autres personnes à aimer votre page.
  - **Scénario / exemple marchand :** Vous voulez tirer parti de la preuve sociale pour encourager de nouveaux "J'aime", vous activez donc cette option pour montrer les amis qui aiment déjà votre page.
- **Afficher les publications (fs\_show\_posts)**

  - **Ce que fait ce paramètre :** Détermine si les publications récentes de la chronologie de votre page Facebook sont affichées dans la boîte "J'aime"/Page Plugin.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé (coché) :* Vos dernières publications Facebook apparaîtront, rendant la boîte plus dynamique et engageante. Vous devrez probablement augmenter le paramètre `Hauteur`.
    - *Lorsqu'il est désactivé (décoché) :* Seule la fonctionnalité de base "J'aime la page" et les visages d'amis (si activé) seront affichés.
  - **Valeur recommandée :** *Activé* (coché) si vous publiez régulièrement du contenu engageant et que vous souhaitez le mettre en valeur. N'oubliez pas d'ajuster la `Hauteur`.
  - **Scénario / exemple marchand :** Vous publiez fréquemment des informations sur les nouveaux produits et les promotions sur Facebook. L'activation de cette option permet aux clients de voir vos dernières mises à jour directement depuis votre boutique.
- **Masquer l'appel à l'action (fs\_hide\_cta)**

  - **Ce que fait ce paramètre :** Contrôle la visibilité du bouton "Appel à l'action" (par exemple, "Envoyer un message", "Acheter maintenant") que vous avez peut-être configuré sur votre page Facebook.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé (coché) :* Le bouton CTA ne sera pas affiché dans la boîte "J'aime".
    - *Lorsqu'il est désactivé (décoché) :* Le bouton CTA (s'il est configuré sur votre page Facebook) sera visible.
  - **Valeur recommandée :** *Désactivé* (décoché) si votre CTA est pertinent pour les visiteurs de votre boutique. *Activé* (coché) si vous préférez vous concentrer uniquement sur l'obtention de "J'aime".
  - **Scénario / exemple marchand :** Votre page Facebook a un bouton "Acheter maintenant". Vous voulez que les clients l'utilisent, vous laissez donc cette option décochée.
- **Petit en-tête (fs\_small\_header)**

  - **Ce que fait ce paramètre :** Utilise une version plus petite de l'en-tête pour la boîte "J'aime"/Page Plugin Facebook.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé (coché) :* La zone d'en-tête de la boîte "J'aime" sera plus compacte, économisant de l'espace vertical.
    - *Lorsqu'il est désactivé (décoché) :* L'en-tête standard, plus grand, sera utilisé.
  - **Valeur recommandée :** *Activé* (coché) si vous souhaitez un look plus épuré ou si vous avez besoin de gagner de l'espace.
  - **Scénario / exemple marchand :** Vous voulez que la boîte coulissante soit aussi compacte que possible sans masquer les informations essentielles, vous activez donc le petit en-tête.
- **Glisser sur (fanslider\_slideon)**

  - **Ce que fait ce paramètre :** Détermine la méthode d'interaction qui fait coulisser la boîte Facebook.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est défini sur "Clic" :* La boîte ne coulissera que lorsque le client cliquera explicitement sur l'onglet.
    - *Lorsqu'il est défini sur "Survol" :* La boîte coulissera lorsque le client déplacera son curseur de souris sur l'onglet.
  - **Valeur recommandée :** "Clic" est généralement moins intrusif et évite les ouvertures accidentelles. "Survol" peut être plus immédiat mais pourrait agacer certains utilisateurs.
  - **Scénario / exemple marchand :** Vous voulez vous assurer que le curseur n'apparaît que lorsqu'un client choisit activement de le voir, vous le réglez donc sur "Clic".
- **Position (fs\_pos)**

  - **Ce que fait ce paramètre :** Contrôle l'emplacement de l'onglet coulissant sur votre site web.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est défini sur "Gauche" :* L'onglet apparaîtra sur le côté gauche de la fenêtre du navigateur.
    - *Lorsqu'il est défini sur "Droite" :* L'onglet apparaîtra sur le côté droit de la fenêtre du navigateur.
  - **Valeur recommandée :** "Gauche" ou "Droite", selon la disposition de votre thème et l'endroit où il cause le moins d'interférences avec d'autres éléments.
  - **Scénario / exemple marchand :** Votre thème a un widget de chat en direct sur la droite, vous définissez donc le Facebook Fan Slider sur "Gauche" pour éviter les conflits.
- **Couleur de fond (fs\_bg\_color)**

  - **Ce que fait ce paramètre :** Définit la couleur de fond du panneau coulissant lui-même (pas le contenu Facebook, mais le conteneur dans lequel il coulisse).
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est défini sur une couleur spécifique (par exemple, #FFFFFF pour le blanc, #0000FF pour le bleu) :* L'arrière-plan de la boîte coulissante changera pour cette couleur.
  - **Valeur recommandée :** Une couleur qui correspond à l'image de marque de votre boutique ou une couleur neutre comme le blanc (`#FFFFFF`) ou le gris clair (`#F0F0F0`).
  - **Scénario / exemple marchand :** Votre marque utilise une nuance de bleu spécifique. Vous saisissez le code hexadécimal de ce bleu pour vous assurer que le curseur correspond à l'identité de votre marque.
- **Couleur de la bordure (fs\_br\_color)**

  - **Ce que fait ce paramètre :** Définit la couleur de la bordure autour du panneau coulissant.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est défini sur une couleur spécifique (par exemple, #CCCCCC pour le gris clair) :* La bordure de la boîte coulissante changera pour cette couleur.
  - **Valeur recommandée :** Une couleur subtile qui complète votre couleur de fond, ou une couleur qui correspond à votre marque.
  - **Scénario / exemple marchand :** Vous voulez une bordure subtile autour du curseur, vous choisissez donc une couleur gris clair (`#DDDDDD`).
- **Langue (fs\_langarray)**

  - **Ce que fait ce paramètre :** Vous permet de sélectionner la langue de la boîte "J'aime"/Page Plugin Facebook. Cela garantit que le bouton "J'aime la page" et les autres textes générés par Facebook sont dans la bonne langue pour votre public.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est défini sur une langue spécifique (par exemple, "en\_US" pour l'anglais, "fr\_FR" pour le français) :* Le plugin Facebook s'affichera dans cette langue.
  - **Valeur recommandée :** Sélectionnez la langue principale de votre boutique ou de votre public cible.
  - **Scénario / exemple marchand :** Votre boutique dessert principalement des clients en France, vous sélectionnez donc "fr\_FR" pour afficher le contenu Facebook en français.
- **Adapter la largeur du conteneur (fs\_adapt\_container\_width)**

  - **Ce que fait ce paramètre :** Indique au Page Plugin Facebook d'adapter sa largeur à la largeur de son conteneur parent (la boîte coulissante).
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé (coché) :* Le contenu Facebook tentera de remplir la `Largeur` que vous avez spécifiée pour la boîte coulissante, le rendant réactif à l'intérieur de ce conteneur.
    - *Lorsqu'il est désactivé (décoché) :* Le contenu Facebook pourrait utiliser sa largeur par défaut, ce qui pourrait entraîner un débordement ou un espace vide s'il ne correspond pas à votre paramètre `Largeur`.
  - **Valeur recommandée :** *Activé* (coché) pour une meilleure réactivité et pour s'assurer que le contenu Facebook s'intègre bien dans votre `Largeur` spécifiée.
  - **Scénario / exemple marchand :** Vous voulez que le contenu Facebook s'ajuste automatiquement à la largeur de votre curseur, vous activez donc cette option pour un look plus propre.

### 2.2 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Valeur par défaut / Recommandée | Objectif et impact |
| --- | --- | --- | --- |
| Configuration du module | URL de la page Facebook (fs\_url) | URL de votre page Facebook | Spécifie la page Facebook à afficher. **CRITIQUE !** |
| Configuration du module | Largeur (fs\_width) | 280-300px | Définit la largeur du contenu Facebook à l'intérieur du curseur. |
| Configuration du module | Hauteur (fs\_height) | 400-500px (plus si affichage de publications) | Définit la hauteur du contenu Facebook à l'intérieur du curseur. |
| Configuration du module | Masquer la photo de couverture (fs\_hide\_cover) | Désactivé (décoché) | Affiche/masque la grande photo de couverture de votre page Facebook. |
| Configuration du module | Afficher les visages des amis (fs\_show\_facepile) | Activé (coché) | Affiche les photos de profil des amis qui aiment votre page (preuve sociale). |
| Configuration du module | Afficher les publications (fs\_show\_posts) | Activé (coché) | Affiche les publications récentes de votre chronologie Facebook. Nécessite plus de hauteur. |
| Configuration du module | Masquer l'appel à l'action (fs\_hide\_cta) | Désactivé (décoché) | Affiche/masque le bouton CTA configuré sur votre page Facebook. |
| Configuration du module | Petit en-tête (fs\_small\_header) | Activé (coché) | Utilise un en-tête plus compact pour le plugin Facebook. |
| Configuration du module | Glisser sur (fanslider\_slideon) | Clic | Détermine si la boîte coulisse au "Clic" ou au "Survol". "Clic" est moins intrusif. |
| Configuration du module | Position (fs\_pos) | Gauche / Droite | Définit le côté de l'écran où l'onglet apparaît. |
| Configuration du module | Couleur de fond (fs\_bg\_color) | Correspond au thème / Blanc (#FFFFFF) | Définit la couleur de fond du panneau coulissant. |
| Configuration du module | Couleur de la bordure (fs\_br\_color) | Gris subtil (#DDDDDD) | Définit la couleur de la bordure du panneau coulissant. |
| Configuration du module | Langue (fs\_langarray) | Langue principale de votre boutique | Définit la langue du texte du plugin Facebook. |
| Configuration du module | Adapter la largeur du conteneur (fs\_adapt\_container\_width) | Activé (coché) | Rend le contenu Facebook réactif à la largeur du curseur. |

## 3. Dépannage marchand et questions fréquemment posées (FAQ)

**Q1 : Le curseur Facebook n'apparaît pas sur ma boutique. Que dois-je vérifier en premier ?**
R1 :

- **Module activé :** Allez dans **Modules > Gestionnaire de modules** et assurez-vous que le module "Facebook Fan Slider" est installé et activé.
- **URL de la page Facebook :** Vérifiez à nouveau l'`URL de la page Facebook (fs_url)` dans la configuration du module. Assurez-vous qu'il s'agit de l'URL *exacte* de votre page Facebook (par exemple, `https://www.facebook.com/MyPresta.eu`) et non seulement de votre profil ou d'un groupe.
- **Cache :** Videz le cache de votre PrestaShop (Allez dans **Paramètres avancés > Performances**, puis cliquez sur "Vider le cache" en haut à droite). Videz également le cache de votre navigateur.
- **Conflits de thème :** Basculez temporairement vers le thème PrestaShop par défaut pour voir si le curseur apparaît. Si c'est le cas, votre thème personnalisé pourrait avoir des conflits CSS ou JavaScript.

**Q2 : Le contenu Facebook à l'intérieur du curseur semble coupé ou trop petit/grand.**
R2 :

- **Largeur et hauteur :** Ajustez les paramètres `Largeur (fs_width)` et `Hauteur (fs_height)` dans la configuration du module. Si vous affichez des publications, vous aurez certainement besoin de plus de hauteur.
- **Adapter la largeur du conteneur :** Assurez-vous que `Adapter la largeur du conteneur (fs_adapt_container_width)` est activé (coché). Cela aide le contenu Facebook à s'adapter de manière réactive à l'intérieur du curseur.
- **Petit en-tête :** Si vous essayez de gagner de l'espace vertical, essayez d'activer `Petit en-tête (fs_small_header)`.

**Q3 : La langue de la boîte "J'aime" Facebook est incorrecte.**
R3 :

- **Paramètre de langue :** Allez dans la configuration du module et vérifiez le paramètre `Langue (fs_langarray)`. Sélectionnez le code de langue correct pour votre public cible (par exemple, `en_US` pour l'anglais américain, `fr_FR` pour le français).

**Q4 : J'ai modifié les paramètres, mais rien ne se passe sur le front office.**
R4 :

- **Enregistrer les modifications :** Cliquez toujours sur le bouton "Enregistrer" après avoir effectué des modifications dans la configuration du module.
- **Vider le cache :** PrestaShop dépend fortement de la mise en cache. Après avoir enregistré, videz toujours le cache de votre PrestaShop (**Paramètres avancés > Performances > Vider le cache**) et le cache de votre navigateur. C'est la raison la plus courante pour laquelle les modifications n'apparaissent pas immédiatement.

**Q5 : Le curseur chevauche un autre élément de mon site.**
R5 :

- **Position :** Ajustez le paramètre `Position (fs_pos)` (Gauche ou Droite) pour voir si le déplacement du curseur de l'autre côté résout le conflit.
- **Ajustements CSS (développeur nécessaire) :** Si le problème persiste, cela pourrait nécessiter des ajustements CSS personnalisés soit au curseur, soit à l'élément en conflit. Cela impliquerait généralement un webmaster ou un développeur.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

Cette section est strictement destinée aux développeurs, aux webmasters de boutique et aux agences techniques qui maintiennent ou étendent la boutique.

### 4.1 Vue d'ensemble de l'architecture

Le module Facebook Fan Slider (`fanslider`) est un module PrestaShop standard implémentant la classe `Module`. Il utilise principalement le système de hooks de PrestaShop pour injecter son HTML, CSS et JavaScript dans le front-office. La fonctionnalité principale tourne autour de l'affichage du plugin officiel de page Facebook dans un élément d'interface utilisateur coulissant personnalisé. La configuration est gérée via la méthode `getContent()`, stockant les paramètres dans `ps_configuration`. Le module n'utilise pas de tables de base de données personnalisées ni de classes `ObjectModel`.

### 4.2 Contrôleurs (`controllers/`)

- **Contrôleurs Front-Office** : Aucun. Tout le rendu et la logique du front-office sont gérés directement dans le fichier principal du module (`fanslider.php`) via des hooks et du JavaScript injecté.
- **Contrôleurs d'administration Back-Office** : Aucun. La configuration est gérée par la méthode `getContent()` de la classe principale du module.

### 4.3 Classes et modèles principaux (`classes/`)

- Aucune classe personnalisée ou définition `ObjectModel` n'est présente dans le répertoire `classes/`. La logique du module est autonome dans `fanslider/fanslider.php`.

### 4.4 Actifs JavaScript (`views/js/`)

Le module inclut plusieurs fichiers JavaScript, principalement pour l'animation coulissante et la fonctionnalité de sélecteur de couleurs.

- `fanslider/jscolor/jscolor.js`

  - **Portée :** Back-office (utilisé dans `getContent()` pour les entrées de sélecteur de couleurs).
  - **Responsabilité :** Fournit un utilitaire de sélecteur de couleurs JavaScript, permettant aux administrateurs de sélectionner visuellement les couleurs pour l'arrière-plan et la bordure du curseur. Il s'attache aux champs de saisie avec la classe `jscolor`.
- `fanslider/js/fanslider-click.js`

  - **Portée :** Front-office.
  - **Responsabilité :** Ce script gère l'interaction "clic" pour le curseur. Il écoute les événements de clic sur l'onglet du curseur et bascule la visibilité et la position du conteneur principal du curseur (`#fanslider`). Il gère également la classe `fanslider_open` pour contrôler l'état ouvert/fermé.
- `fanslider/js/fanslider.js`

  - **Portée :** Front-office.
  - **Responsabilité :** Il s'agit probablement du script principal pour l'animation et la configuration initiale du curseur. Il gère l'interaction "survol" si configurée, et calcule potentiellement les positions initiales ou applique des transformations CSS pour l'effet de glissement. Il interagit avec les éléments `#fanslider` et `#fanslider_tab`.
- `fanslider/script.js`

  - **Portée :** Front-office.
  - **Responsabilité :** Ce script contient probablement la logique principale pour initialiser le plugin de page Facebook (FB.init et FB.XFBML.parse) et potentiellement d'autres configurations générales ou liaisons d'événements liées au comportement du curseur. Il garantit que le SDK Facebook est chargé et que le plugin est rendu correctement.

### 4.5 Feuilles de style CSS (`views/css/`)

Le module ne liste pas explicitement les fichiers CSS dans `views/css/`. Le style du curseur est probablement intégré directement dans la méthode `hookDisplayHeader` du fichier `fanslider.php` ou dans le template `rightcolumn.tpl`, ou généré dynamiquement en fonction de la configuration. Les développeurs doivent inspecter le HTML généré et le fichier principal du module pour les styles en ligne ou les blocs `<style>`.

### 4.6 Structure du template Smarty (`views/templates/`)

- **Templates de hook (`views/templates/hook/`)** :
  - `fanslider/views/templates/hook/rightcolumn.tpl`
    - **Hook :** Ce template est principalement conçu pour être rendu dans un hook qui permet l'injection de contenu dans la page, tel que `displayFooter` ou `displayHeader` (même si son nom suggère `displayRightColumn`, l'implémentation du module le place comme un élément fixe).
    - **Bloc visuel :** Ce template génère la structure HTML principale du Facebook Fan Slider. Il inclut généralement :
      - Le conteneur principal du curseur (`#fanslider`).
      - L'onglet cliquable (`#fanslider_tab`).
      - Le conteneur du plugin de page Facebook (`<div class="fb-page">`).
      - Il reçoit des variables de configuration du module pour définir dynamiquement les attributs du plugin de page Facebook (par exemple, `data-href`, `data-width`, `data-height`, `data-hide-cover`, `data-show-facepile`, `data-show-posts`, `data-hide-cta`, `data-small-header`, `data-adapt-container-width`).
      - Il inclut également le `div` nécessaire pour que le SDK Facebook rende le plugin.

### 4.7 Schéma de la base de données et carte des hooks

- **Tables de base de données** :

  - Le module ne crée aucune table de base de données personnalisée.
  - Tous les paramètres de configuration sont stockés dans la table `ps_configuration` en utilisant des clés préfixées par `FS_` ou `FANSIDER_` (par exemple, `FS_WIDTH`, `FANSIDER_SLIDEON`).
- **Table des hooks enregistrés** :

| Nom du hook | Moment d'exécution | Objectif technique |
| --- | --- | --- |
| `displayHeader` | Exécuté dans la section `<head>` de chaque page. | Injecte les fichiers CSS et JavaScript nécessaires, et potentiellement le script d'initialisation du SDK Facebook. Peut également générer des styles en ligne basés sur la configuration. |
| `displayFooter` | Exécuté en bas de chaque page, avant la balise de fermeture `</body>`. | Rend la structure HTML principale du Facebook Fan Slider (à partir de `rightcolumn.tpl`) et garantit que le SDK Facebook est chargé et que le Page Plugin est initialisé après que le DOM est prêt. C'est là que le composant visuel est ajouté à la page. |

## 5. Support officiel et mises à jour

Pour les dernières versions, les mises à jour et le support professionnel du module Facebook Fan Slider, veuillez visiter votre compte client sur [MyPresta.eu](https://mypresta.eu/my-account/orders/). Notre équipe de support est disponible pour vous aider avec toutes les questions ou problèmes que vous pourriez rencontrer.
