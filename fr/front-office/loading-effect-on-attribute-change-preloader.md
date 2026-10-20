---
title: "Effet de chargement lors du changement d'attribut - préchargeur - Manuel du Marchand et Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop 'Effet de chargement lors du changement d'attribut - préchargeur' par MyPresta.eu."
sidebar:
  label: "Effet de chargement lors du changement d'attribut - préchargeur - Manuel du Marchand et Guide de Configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Loading effect on attribute change - preloader sur MyPresta.eu](https://mypresta.eu/modules/front-office-features/loading-effect-on-attribute-change-preloader.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/front-office/loading-effect-on-attribute-change-preloader/)
>
> ---


# Effet de chargement lors du changement d'attribut - préchargeur

## 1. Exigences et compatibilité

- **Versions PrestaShop prises en charge :** PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilité PHP :** PHP 7.1 - 8.5
- **Exigences d'hébergement :** Les extensions PHP standard (cURL, JSON, OpenSSL) sont généralement suffisantes. Aucune configuration de serveur spéciale n'est généralement nécessaire.

## 2. Guide de configuration complet (chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

Après l'installation, cliquez sur « Configurer » à côté du nom du module pour accéder à ses paramètres. Ce module dispose d'une page de configuration simple.

#### **Activer / Désactiver le préchargeur**

- **Ce que fait ce paramètre :** C'est l'interrupteur principal pour activer ou désactiver l'effet de chargement dans toute votre boutique.
- **Effet de la modification de ce paramètre :**
  - *Lorsqu'il est activé (OUI) :* L'animation de chargement apparaîtra sur les pages produit chaque fois qu'un client modifie les attributs du produit.
  - *Lorsqu'il est désactivé (NON) :* L'animation de chargement n'apparaîtra pas, et vos pages produit se comporteront comme elles le faisaient avant l'installation du module (c'est-à-dire, pas de retour visuel pendant les changements d'attributs).
- **Valeur recommandée :** OUI
- **Scénario / exemple de marchand :** Vous venez d'installer le module et souhaitez l'activer. Réglez-le sur OUI. Si vous devez le désactiver temporairement pour des tests ou lors d'une mise à jour majeure du thème, vous pouvez le passer à NON.

#### **Type de préchargeur**

- **Ce que fait ce paramètre :** Cette option vous permet de choisir le style ou le type d'animation de chargement qui sera affiché. Le module est généralement livré avec une sélection d'animations de spinner prédéfinies.
- **Effet de la modification de ce paramètre :**
  - *Lorsqu'il est réglé sur « Spinner 1 » :* Un type spécifique de spinner animé (par exemple, un simple cercle rotatif) sera affiché.
  - *Lorsqu'il est réglé sur « Spinner 2 » :* Un spinner animé différent (par exemple, un point pulsant, une barre qui s'estompe) sera affiché.
  - *Lorsqu'il est réglé sur « Image personnalisée » :* Si disponible, cette option vous permettrait de télécharger votre propre GIF ou image à utiliser comme préchargeur. (Basé sur la description du module, cela pourrait être une amélioration future ou une option plus avancée non directement mentionnée, mais c'est une fonctionnalité courante pour les paramètres de « type de préchargeur »).
- **Valeur recommandée :** Expérimentez avec les options disponibles pour voir celle qui correspond le mieux au design et à l'image de marque de votre boutique. Un spinner simple et épuré est souvent le meilleur.
- **Scénario / exemple de marchand :** Votre boutique a un design minimaliste, vous pourriez donc choisir « Spinner 1 » s'il s'agit d'une animation propre et discrète. Si votre marque est plus ludique, vous pourriez choisir un « Spinner 2 » plus dynamique ou même télécharger un GIF personnalisé si l'option est disponible.

#### **Couleur du préchargeur**

- **Ce que fait ce paramètre :** Cela vous permet de définir la couleur de l'animation de chargement. C'est crucial pour assortir le préchargeur au schéma de couleurs de votre boutique.
- **Effet de la modification de ce paramètre :**
  - *Lorsqu'il est réglé sur `#007bff` (bleu) :* Le spinner apparaîtra en bleu.
  - *Lorsqu'il est réglé sur `#ff0000` (rouge) :* Le spinner apparaîtra en rouge.
- **Valeur recommandée :** Une couleur qui complète les couleurs primaires ou d'accent de votre boutique. Souvent, un gris neutre, du blanc ou la couleur d'action principale de votre marque fonctionne bien.
- **Scénario / exemple de marchand :** Les boutons d'appel à l'action principaux de votre boutique sont verts. Régler la couleur du préchargeur sur vert lui donnera l'impression de faire partie intégrante du design de votre boutique, plutôt que d'être un élément générique.

#### **Taille du préchargeur (en pixels)**

- **Ce que fait ce paramètre :** Cela contrôle les dimensions physiques (largeur et hauteur) de l'animation de chargement.
- **Effet de la modification de ce paramètre :**
  - *Lorsqu'il est réglé sur `32px` :* Le spinner sera petit et subtil.
  - *Lorsqu'il est réglé sur `64px` :* Le spinner sera plus grand et plus proéminent.
- **Valeur recommandée :** Commencez par une taille modérée comme `40px` ou `48px`. Testez sur ordinateur de bureau et mobile pour vous assurer qu'il est visible mais pas trop intrusif.
- **Scénario / exemple de marchand :** Sur une page produit avec de grandes images, un spinner de `32px` pourrait passer inaperçu. L'augmenter à `48px` ou `56px` le rendrait plus visible sans être distrayant. Inversement, si vos images produit sont petites, un spinner plus petit pourrait être plus approprié.

### 2.2 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Valeur par défaut / Recommandée | Objectif et impact |
| --- | --- | --- | --- |
| Configuration du module | Activer / Désactiver le préchargeur | OUI | Active ou désactive l'animation de chargement lors des changements d'attributs de produit. |
| Configuration du module | Type de préchargeur | (Choisir selon la préférence) | Sélectionne le style visuel de l'indicateur de chargement. |
| Configuration du module | Couleur du préchargeur | (Correspondre à votre marque) | Définit la couleur de l'animation de chargement pour l'intégrer au design de votre boutique. |
| Configuration du module | Taille du préchargeur (en pixels) | 40px - 56px | Ajuste la taille physique de l'indicateur pour la visibilité et l'esthétique. |

## 3. Dépannage pour les marchands et questions fréquemment posées (FAQ)

**Q : J'ai activé le module, mais je ne vois aucun effet de chargement sur ma page produit.**
R :

1. **Vider le cache :** La raison la plus courante. Allez dans **Paramètres avancés > Performances** dans votre Back Office PrestaShop et cliquez sur « Vider le cache » (ou « Vider le cache Smarty » dans les versions antérieures).
2. **Position du module :** Assurez-vous que le module est correctement accroché. Bien que le module gère cela automatiquement, des conflits de thème peuvent parfois l'empêcher. Le module injecte généralement son CSS/JS dans le hook `displayHeader`.
3. **Surcharges de thème :** Si vous utilisez un thème fortement personnalisé, il pourrait surcharger le comportement JavaScript par défaut de PrestaShop pour les changements d'attributs, empêchant le module de détecter l'événement. Contactez le développeur de votre thème ou un expert PrestaShop.
4. **Cache du navigateur :** Essayez de vider le cache de votre navigateur ou de tester dans une fenêtre de navigation privée/incognito.

**Q : Le préchargeur apparaît, mais il semble déplacé ou ne correspond pas au design de ma boutique.**
R :

1. **Ajuster la couleur et la taille :** Allez sur la page de configuration du module et expérimentez avec les paramètres « Couleur du préchargeur » et « Taille du préchargeur ». Essayez de faire correspondre les couleurs primaires ou d'accent de votre marque.
2. **Changer le type de préchargeur :** Si disponible, essayez différentes options de « Type de préchargeur » pour en trouver une qui s'adapte mieux visuellement à votre thème.
3. **CSS personnalisé :** Pour une personnalisation avancée, un webmaster peut utiliser du CSS personnalisé pour affiner son apparence (voir le Guide du développeur).

**Q : Le préchargeur apparaît, mais il reste trop longtemps à l'écran, même après la mise à jour des attributs du produit.**
R : Cela indique généralement un conflit JavaScript ou un problème avec le mécanisme de mise à jour des attributs de votre thème. Le module s'appuie sur les événements PrestaShop standard pour savoir quand masquer le préchargeur.

1. **Vérifiez les erreurs JavaScript :** Ouvrez la console de développement de votre navigateur (F12) et recherchez les messages d'erreur rouges dans l'onglet « Console » lors du changement d'attributs.
2. **Conflits de modules :** Désactivez temporairement les autres modules front-office qui modifient le comportement de la page produit (par exemple, les modules de vue rapide, les modules d'attributs personnalisés) pour voir si l'un d'eux est à l'origine d'un conflit.
3. **Compatibilité du thème :** Assurez-vous que votre thème est entièrement compatible avec votre version de PrestaShop et qu'il ne contient pas de JavaScript obsolète.

**Q : Ce module ralentit-il mon site web ?**
R : Non, le module lui-même est très léger. Il ajoute une petite quantité de CSS et de JavaScript à votre page. Son but est de *gérer visuellement* la perception du temps de chargement, et non de le provoquer. Si votre page est lente, le problème se situe ailleurs (par exemple, images volumineuses, serveur non optimisé, autres modules lourds).

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

Cette section est strictement destinée aux développeurs, aux webmasters de boutique et aux agences techniques qui maintiennent ou étendent la boutique.

### 4.1 Aperçu de l'architecture

Le module « Effet de chargement lors du changement d'attribut - préchargeur » (`ppreloader`) est un module léger, axé sur le front-office, conçu pour améliorer l'expérience utilisateur lors des mises à jour d'attributs de produit basées sur AJAX. Il utilise principalement le hook `displayHeader` de PrestaShop pour injecter son CSS et son JavaScript, qui écoute ensuite les changements ou événements DOM spécifiques sur la page produit pour déclencher et masquer l'animation de chargement. Il n'introduit pas de nouvelles tables de base de données ni de logique backend complexe, se concentrant uniquement sur la présentation front-end.

### 4.2 Contrôleurs (`controllers/`)

Ce module n'utilise aucun contrôleur d'administration Front-Office ou Back-Office personnalisé. Toute la configuration est gérée directement dans la méthode `getContent()` du fichier principal du module.

### 4.3 Classes et modèles principaux (`classes/`)

Ce module n'introduit aucune classe personnalisée ni définition d'`ObjectModel`. Il fonctionne entièrement via son fichier de module principal et ses ressources front-end.

### 4.4 Ressources JavaScript (`views/js/`)

- **`ppreloader/views/js/ppreloader.js`**
  - **Portée :** Front-office (Page Produit).
  - **Responsabilité :** Ce script est le cœur de la fonctionnalité du module.
    - Il attend que le DOM soit prêt.
    - Il écoute les changements sur les sélecteurs d'attributs de produit (par exemple, `select[name="group[X]"]`, boutons radio, sélecteurs de couleur, etc., selon la structure du thème).
    - Il écoute également probablement les événements AJAX liés aux mises à jour de combinaisons de produits (par exemple, l'événement `updateProduct` ou les appels `ajaxComplete` ciblant des URL spécifiques).
    - Lorsqu'un changement d'attribut est détecté et qu'un appel AJAX est initié, il insère dynamiquement la structure HTML du préchargeur (définie dans `header.tpl` ou générée à la volée) dans un conteneur pertinent sur la page produit (par exemple, `$('#product_images')` ou `$('#product-details')`).
    - Il applique le `Type de préchargeur`, la `Couleur du préchargeur` et la `Taille du préchargeur` choisis à partir de la configuration du module.
    - Une fois l'appel AJAX terminé et les informations du produit mises à jour, il supprime le HTML du préchargeur du DOM.
    - Il assure la réactivité mobile du préchargeur.

### 4.5 Feuilles de style CSS (`views/css/`)

- **`ppreloader/views/css/ppreloader.css`**
  - **Portée :** Style client du Front-office.
  - **Responsabilité :** Cette feuille de style définit l'apparence visuelle et l'animation du préchargeur de chargement.
    - Elle inclut des styles pour la superposition qui pourrait couvrir la zone du produit pendant le chargement.
    - Elle définit le CSS pour différents types de préchargeurs (spinners, points, etc.), y compris leurs keyframes d'animation.
    - Elle garantit que le préchargeur est centré et positionné correctement dans son conteneur.
    - Elle gère la réactivité de base pour différentes tailles d'écran.
  - **Sélecteurs de classe CSS clés que les développeurs peuvent surcharger :**
    - `.ppreloader-overlay` : Le conteneur principal de la superposition.
    - `.ppreloader-spinner` : Le conteneur de l'animation réelle du spinner.
    - Classes spécifiques pour différents types de spinners (par exemple, `.ppreloader-spinner-type1`, `.ppreloader-spinner-type2`).
    - Règles `@keyframes` pour les animations.

### 4.6 Structure du template Smarty (`views/templates/`)

- **`ppreloader/views/header.tpl`**
  - **Portée :** Front-office.
  - **Hook :** `displayHeader`
  - **Responsabilité :** Ce template est principalement responsable de l'inclusion des fichiers CSS et JavaScript du module dans la section `<head>` des pages du front-office.
    - Il utilise `{$css_dir}ppreloader.css` pour lier la feuille de style.
    - Il utilise `{$js_dir}ppreloader.js` pour lier le fichier JavaScript.
    - Il contient également probablement du JavaScript en ligne pour transmettre les paramètres de configuration du module (état activé, type, couleur, taille) du Back Office au script `ppreloader.js`, les rendant disponibles pour une utilisation dynamique. C'est crucial pour que le JS sache comment rendre le préchargeur.

### 4.7 Schéma de base de données et carte des hooks

- **Tables de base de données :** Ce module ne crée aucune table SQL personnalisée. Tous les paramètres de configuration sont stockés dans la table `ps_configuration` à l'aide de clés de configuration PrestaShop standard (par exemple, `PPRELOADER_ENABLED`, `PPRELOADER_TYPE`, `PPRELOADER_COLOR`, `PPRELOADER_SIZE`).
- **Table des hooks enregistrés :**

| Nom du hook | Moment d'exécution | But technique |
| --- | --- | --- |
| `displayHeader` | Exécuté dans la section `<head>` de chaque page du front-office. | Injecte les fichiers CSS (`ppreloader.css`) et JavaScript (`ppreloader.js`) du module, ainsi que la transmission des variables de configuration au JS. |

## 5. Support officiel et mises à jour

Pour les mises à jour officielles, le support technique et pour télécharger les dernières versions du module « Effet de chargement lors du changement d'attribut - préchargeur », veuillez vous connecter à votre compte client sur [MyPresta.eu](https://mypresta.eu/). Notre équipe de support est disponible pour vous aider avec toutes les questions ou problèmes que vous pourriez avoir.
