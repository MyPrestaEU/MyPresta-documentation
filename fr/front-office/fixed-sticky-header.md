---
title: "En-tête fixe et collant - Manuel du marchand et guide de configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop En-tête fixe et collant par MyPresta.eu."
sidebar:
  label: "En-tête fixe et collant - Manuel du marchand et guide de configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Fixed sticky header sur MyPresta.eu](https://mypresta.eu/modules/front-office-features/fixed-sticky-header.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/front-office/fixed-sticky-header/)
>
> ---


# En-tête fixe et collant

## 1. Exigences et compatibilité

- **Versions de PrestaShop prises en charge** : PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilité PHP** : PHP 7.1 - 8.5
- **Exigences d'hébergement** : Extensions PHP standard (cURL, JSON, OpenSSL). Le module fonctionne avec les modèles default-bootstrap et classic et avec tous les thèmes ayant une structure similaire.

## 2. Guide de configuration complet (chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

Après l'installation, cliquez sur « Configurer » à côté du module « En-tête fixe et collant » dans votre Gestionnaire de modules. Cela vous mènera à la page de configuration principale du module.

#### Paramètres généraux

- **Ce que fait ce paramètre :** Cette section inclut généralement les paramètres standard des modules MyPresta.eu liés aux mises à jour et au support.
- **Effet de la modification de ce paramètre :**
  - *Lorsqu'il est activé :* Permet au module de vérifier les mises à jour disponibles sur MyPresta.eu et d'afficher potentiellement des notifications dans votre Back Office. Cela garantit que vous utilisez toujours la version la plus récente, la plus sécurisée et la plus riche en fonctionnalités du module.
  - *Lorsqu'il est désactivé :* Le module ne vérifiera pas automatiquement les mises à jour. Vous devrez vérifier manuellement les nouvelles versions en vous connectant à votre compte MyPresta.eu.
- **Valeur recommandée :** **OUI** (ou activé). Il est fortement recommandé de maintenir ce paramètre actif pour vous assurer de recevoir des mises à jour et des corrections de bugs en temps opportun, ce qui est crucial pour la sécurité et la compatibilité avec les futures versions de PrestaShop.
- **Scénario / exemple de marchand :** Vous souhaitez être informé si une nouvelle version du module est publiée qui corrige un bug ou ajoute une nouvelle fonctionnalité. Maintenir ce paramètre activé vous assure d'être toujours informé.

#### Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Par défaut / Recommandé | Objectif et impact |
| --- | --- | --- | --- |
| Page de configuration du module | Vérifications des mises à jour (mypresta\_updates, update\_, updatev\_) | Activé | Permet au module de vérifier et de vous informer des mises à jour disponibles sur MyPresta.eu, garantissant que vous disposez des dernières fonctionnalités et correctifs de sécurité. |

## 3. Dépannage pour les marchands et questions fréquemment posées (FAQ)

**Q1 : L'en-tête ne colle pas, ou il chevauche d'autres éléments. Que dois-je faire ?**
R1 : Cela se produit souvent en raison de conflits avec le CSS ou le JavaScript de votre thème, surtout si votre thème a une structure d'en-tête très personnalisée.
\* **Vider le cache :** Tout d'abord, essayez de vider le cache de votre PrestaShop. Allez dans **Paramètres avancés > Performances** et cliquez sur « Vider le cache » en haut à droite.
\* **Compatibilité du thème :** Le module est conçu pour fonctionner avec les thèmes PrestaShop standard (comme Classic) et les thèmes avec des structures similaires. Si vous avez un thème fortement personnalisé, des ajustements CSS mineurs pourraient être nécessaires.
\* **Contacter le support :** Si le problème persiste, rassemblez des captures d'écran et des détails sur votre thème, et contactez le support MyPresta.eu. Ils peuvent vous aider à diagnostiquer et à fournir des extraits CSS personnalisés si nécessaire.

**Q2 : Mon en-tête a l'air étrange ou a un espace supplémentaire lorsqu'il devient collant.**
R2 : Cela peut être un problème de style.
\* **Inspecter l'élément :** Utilisez les outils de développement de votre navigateur (clic droit sur votre en-tête et sélectionnez « Inspecter ») pour voir quelles règles CSS sont appliquées. Recherchez `position: fixed;` et `top: 0;`.
\* **Style du thème :** Votre thème peut avoir des règles de remplissage ou de marge spécifiques qui entrent en conflit. Vous devrez peut-être ajouter du CSS personnalisé pour ajuster l'apparence de l'en-tête collant. Le support MyPresta.eu peut vous guider.

**Q3 : Ce module va-t-il ralentir mon site web ?**
R3 : Le module « En-tête fixe et collant » est très léger, utilisant un minimum de JavaScript et de CSS. Il devrait avoir un impact négligeable sur la vitesse de chargement et les performances de votre site web. L'effet n'est activé qu'au défilement, il n'ajoute donc pas de surcharge au chargement initial de la page.

**Q4 : Comment traduire le module s'il avait du texte visible ?**
R4 : Bien que ce module fournisse principalement un effet visuel et n'ait généralement pas de texte visible pour l'utilisateur, si une future version introduit du texte configurable, vous le traduiriez via :
\* **International > Traductions** dans votre Back Office PrestaShop.
\* Sélectionnez « Traductions des modules installés », choisissez votre thème, puis sélectionnez « En-tête fixe et collant » dans la liste déroulante des modules.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

### 4.1 Aperçu de l'architecture

Le module « En-tête fixe et collant » est un module de fonctionnalité front-office léger conçu pour améliorer l'expérience utilisateur en rendant l'en-tête principal collant au défilement. Il utilise principalement JavaScript pour détecter les événements de défilement et appliquer des classes CSS à l'élément d'en-tête, ce qui déclenche ensuite le style `position: fixed`. Il adhère à la structure standard des modules PrestaShop, utilisant le hook `displayHeader` pour injecter ses ressources.

### 4.2 Contrôleurs (`controllers/`)

- **Contrôleurs Front-Office** : Aucun. La fonctionnalité du module est entièrement gérée via JavaScript injecté via un hook.
- **Contrôleurs d'administration Back-Office** : Aucun. La configuration est gérée directement dans la méthode `getContent()` du fichier principal du module.

### 4.3 Classes et modèles principaux (`classes/`)

- Aucune classe personnalisée ou définition `ObjectModel` n'est utilisée. Le module fonctionne en manipulant les éléments DOM existants.

### 4.4 Ressources JavaScript (`views/js/`)

- **`fixedheader/fixedheader.js`**
  - **Portée :** Front-office.
  - **Objectif :** Ce script est responsable de la fonctionnalité principale de l'en-tête collant.
  - **Détails :**
    - Il écoute l'événement `scroll` sur l'objet `window`.
    - Il détermine la position de défilement et le décalage initial de l'élément d'en-tête.
    - Lorsque l'utilisateur fait défiler au-delà d'un certain seuil (la hauteur initiale de l'en-tête), il ajoute une classe CSS spécifique (par exemple, `fixed-header-active` ou similaire, telle que définie dans `fixedheader.css`) au conteneur principal de l'en-tête.
    - Lorsque l'utilisateur remonte au-dessus du seuil, il supprime cette classe.
    - Il cible probablement un sélecteur d'en-tête commun (par exemple, `#header`, `.header-container`, ou similaire, selon la structure du thème) pour appliquer le comportement collant.
    - Il peut également gérer l'ajout d'un `padding-top` au `body` ou à un wrapper de contenu principal pour empêcher le contenu de « sauter » ou d'être caché derrière l'en-tête fixe.

### 4.5 Feuilles de style CSS (`views/css/`)

- **`fixedheader/fixedheader.css`**
  - **Portée :** Style client front-office.
  - **Objectif :** Fournit les règles CSS nécessaires pour rendre l'en-tête collant lorsque le JavaScript ajoute la classe d'activation.
  - **Détails :**
    - Il définit les styles pour l'état actif de l'en-tête collant. Les propriétés clés incluront :
      - `position: fixed;`
      - `top: 0;`
      - `width: 100%;`
      - `z-index: 1000;` (ou une valeur élevée pour s'assurer qu'il reste au-dessus des autres contenus).
      - Potentiellement `box-shadow` ou `background-color` pour distinguer visuellement l'en-tête collant.
    - Il peut également inclure des règles pour gérer le remplissage ou la marge du `body` afin d'éviter le chevauchement du contenu.
    - **Sélecteurs de classe CSS clés que les développeurs peuvent remplacer :** La classe principale ajoutée par le JS (par exemple, `.fixed-header-active` ou similaire) et le sélecteur pour l'élément d'en-tête lui-même (par exemple, `#header`, `.header-container`). Les développeurs peuvent remplacer ces styles dans le CSS personnalisé de leur thème pour correspondre à leur design.

### 4.6 Structure du modèle Smarty (`views/templates/`)

- Aucun fichier `.tpl` personnalisé n'est utilisé. Le module injecte son JavaScript et son CSS directement dans la section `<head>` via le hook `displayHeader`.

### 4.7 Schéma de la base de données et carte des hooks

- **Tables de base de données** : Aucune table de base de données personnalisée n'est créée. La configuration est stockée dans `ps_configuration` en utilisant des clés comme `MYPRESTA_UPDATES`, `UPDATE_FIXEDHEADER`, `UPDATEV_FIXEDHEADER`.
- **Table des hooks enregistrés** :

| Nom du hook | Moment d'exécution | Objectif technique |
| --- | --- | --- |
| `displayHeader` | Dans la section `<head>` de chaque page du front-office. | Injecte les fichiers CSS (`fixedheader.css`) et JavaScript (`fixedheader.js`) du module dans la page, garantissant qu'ils sont chargés avant que le contenu de la page ne soit rendu et qu'ils soient disponibles pour une exécution immédiate. |

## 5. Support officiel et mises à jour

Pour les mises à jour officielles, le support technique et les dernières versions du module « En-tête fixe et collant », veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu). Notre équipe de support est disponible pour vous aider avec tout problème ou question que vous pourriez avoir concernant la fonctionnalité et la compatibilité du module.
