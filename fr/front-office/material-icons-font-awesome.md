---
title: "Material Icons + Font Awesome - Manuel Marchand & Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop Material Icons + Font Awesome par MyPresta.eu."
sidebar:
  label: "Material Icons + Font Awesome - Manuel Marchand & Guide de Configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Material Icons + Font Awesome sur MyPresta.eu](https://mypresta.eu/modules/front-office-features/material-icons-font-awesome.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/front-office/material-icons-font-awesome/)
>
> ---


# Material Icons + Font Awesome

## 1. Exigences et compatibilité

- **Versions de PrestaShop prises en charge :** PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilité PHP :** PHP 7.1 - 8.5
- **Exigences d'hébergement :** Les extensions PHP standard (cURL, JSON, OpenSSL) sont généralement suffisantes. Aucune exigence particulière au-delà d'un environnement d'hébergement PrestaShop standard.

## 2. Présentation complète de la configuration (Chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

C'est l'écran de configuration principal et unique pour le module « Material Icons + Font Awesome ». Vous le trouverez en naviguant vers **Modules > Gestionnaire de modules**, en recherchant « Material Icons + Font Awesome », et en cliquant sur « Configurer ».

#### **Ajouter Font Awesome**

- **Ce que fait ce paramètre :** Ce commutateur contrôle si la bibliothèque d'icônes Font Awesome est chargée dans le front-office de votre boutique (ce que les clients voient) et le back-office (votre panneau d'administration).
- **Effet de la modification de ce paramètre :**
  - *Lorsqu'il est activé :* Le fichier CSS de Font Awesome sera ajouté à la section `<head>` de votre site web, rendant toutes les icônes Font Awesome disponibles. Cela corrigera toutes les icônes Font Awesome manquantes.
  - *Lorsqu'il est désactivé :* Le fichier CSS de Font Awesome ne sera PAS chargé par ce module. Si votre thème ou un autre module charge déjà Font Awesome, ou si vous n'en avez pas besoin, vous pouvez le désactiver pour éviter de le charger deux fois.
- **Valeur recommandée :**
  - **Activé** si vous remarquez des icônes Font Awesome manquantes sur votre boutique ou dans le back-office, ou si vous prévoyez d'utiliser des icônes Font Awesome dans votre contenu.
  - **Désactivé** si toutes les icônes Font Awesome s'affichent déjà correctement (ce qui signifie que votre thème ou un autre module le charge déjà) pour éviter un chargement redondant.
- **Scénario / exemple de marchand :** Vous avez installé un nouveau module de paiement, et ses icônes de méthode de paiement (par exemple, un symbole de carte de crédit) apparaissent comme des boîtes vides. Si ces icônes sont basées sur Font Awesome, l'activation de ce paramètre les fera apparaître correctement.

#### **Ajouter Material Icons**

- **Ce que fait ce paramètre :** Ce commutateur contrôle si la bibliothèque Material Icons (de Google) est chargée dans le front-office et le back-office de votre boutique.
- **Effet de la modification de ce paramètre :**
  - *Lorsqu'il est activé :* Le fichier CSS de Material Icons sera ajouté à la section `<head>` de votre site web, rendant toutes les Material Icons disponibles. Cela corrigera toutes les Material Icons manquantes.
  - *Lorsqu'il est désactivé :* Le fichier CSS de Material Icons ne sera PAS chargé par ce module. Si votre thème ou un autre module charge déjà Material Icons, ou si vous n'en avez pas besoin, vous pouvez le désactiver.
- **Valeur recommandée :**
  - **Activé** si vous remarquez des Material Icons manquantes sur votre boutique ou dans le back-office.
  - **Désactivé** si toutes les Material Icons s'affichent déjà correctement (ce qui signifie que votre thème ou un autre module le charge déjà) pour éviter un chargement redondant.
- **Scénario / exemple de marchand :** Votre thème utilise Material Icons pour ses flèches de navigation ou certains éléments de page produit, mais après une mise à jour du thème, elles ont disparu. L'activation de ce paramètre les fera probablement réapparaître.

#### **Tableau de référence rapide de la configuration**

| Écran / Vue | Paramètre / Option | Par défaut / Recommandé | Objectif et impact |
| --- | --- | --- | --- |
| Configuration du module | Ajouter Font Awesome | Activé (si nécessaire) | Charge la bibliothèque d'icônes Font Awesome pour le front et le back office. Corrige les icônes Font Awesome manquantes. |
| Configuration du module | Ajouter Material Icons | Activé (si nécessaire) | Charge la bibliothèque Material Icons pour le front et le back office. Corrige les Material Icons manquantes. |

## 3. Dépannage marchand et questions fréquemment posées (FAQ)

**Q : J'ai activé les paramètres, mais les icônes sont toujours manquantes. Que dois-je faire ?**
R : Tout d'abord, videz votre cache PrestaShop. Allez dans **Paramètres avancés > Performances**, et cliquez sur « Vider le cache » en haut à droite. Videz également le cache de votre navigateur (Ctrl+F5 ou Cmd+Shift+R). Si les icônes sont toujours manquantes, il est possible que les icônes que vous recherchez appartiennent à une bibliothèque d'icônes différente non couverte par ce module, ou qu'il y ait un conflit CSS dans votre thème.

**Q : Ce module va-t-il ralentir mon site web ?**
R : Le module charge des fichiers CSS standard pour les bibliothèques d'icônes. Si vous n'activez que les bibliothèques dont vous avez besoin, et qu'elles ne sont pas déjà chargées par votre thème, l'impact sur les performances est minimal et nécessaire pour un affichage correct. Si vous activez une bibliothèque déjà chargée par votre thème, vous la chargerez deux fois, ce qui peut entraîner un léger ralentissement. Vérifiez toujours si votre thème inclut déjà ces bibliothèques avant de les activer ici.

**Q : Mon thème personnalisé a son propre jeu d'icônes. Ce module va-t-il interférer ?**
R : Il ne devrait pas interférer directement. Ce module ajoute les bibliothèques d'icônes spécifiées. Si votre thème utilise un jeu d'icônes différent (par exemple, des SVG personnalisés ou une autre bibliothèque d'icônes de polices), ce module ajoutera simplement Font Awesome et/ou Material Icons à côté. Si vous rencontrez des conflits, vous pouvez essayer de désactiver une ou les deux options du module pour voir si cela résout le problème.

**Q : Comment savoir si mon thème charge déjà Font Awesome ou Material Icons ?**
R : Le moyen le plus simple est de faire un clic droit sur la page de votre boutique (front-office) et de sélectionner « Afficher le code source de la page » ou « Inspecter l'élément ». Ensuite, recherchez « font-awesome.css » ou « material-icons.css » dans la section `<head>`. Si vous les trouvez, votre thème les charge probablement déjà. Alternativement, si toutes les icônes s'affichent correctement sans ce module, alors votre thème ou un autre module s'en occupe déjà.

**Q : Puis-je utiliser Font Awesome et Material Icons en même temps ?**
R : Oui, absolument. Vous pouvez activer les deux options dans la configuration du module. C'est souvent nécessaire si différentes parties de votre boutique (par exemple, votre thème et un module tiers) dépendent de différentes bibliothèques d'icônes.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

### 4.1 Aperçu de l'architecture

Le module « Material Icons + Font Awesome » est un module PrestaShop léger principalement conçu pour injecter des feuilles de style CSS externes pour les bibliothèques d'icônes. Il suit une structure de module PrestaShop standard, tirant parti des hooks pour intégrer sa fonctionnalité dans le front-office et le back-office. Il n'introduit pas de contrôleurs, de modèles ou de tables de base de données personnalisés, se concentrant uniquement sur la gestion des actifs.

### 4.2 Contrôleurs (`controllers/`)

Ce module ne contient aucun contrôleur front-office ou back-office personnalisé. Toute la logique est gérée dans le fichier principal du module (`fonticons.php`) via des hooks.

### 4.3 Classes et modèles de base (`classes/`)

Ce module ne définit aucune classe personnalisée ni n'étend `ObjectModel`. Toute la configuration est stockée directement dans `ps_configuration` en utilisant les clés définies ci-dessous.

### 4.4 Actifs JavaScript (`views/js/`)

Ce module n'inclut aucun fichier JavaScript personnalisé.

### 4.5 Feuilles de style CSS (`views/css/`)

La fonctionnalité principale du module repose sur ces fichiers CSS :

- **`fonticons/views/css/font-awesome.css`** :

  - **Portée** : Front-office et Back-office.
  - **Objectif** : Contient les règles CSS et les déclarations `@font-face` pour la bibliothèque d'icônes Font Awesome. Ce fichier est responsable de rendre les icônes Font Awesome disponibles dans toute la boutique.
  - **Sélecteurs de classe CSS clés** : `fa`, `fas`, `far`, `fal`, `fab` (pour différents styles Font Awesome), suivis de classes d'icônes spécifiques comme `fa-shopping-cart`, `fa-user`, etc. Les développeurs peuvent les remplacer en ciblant ces classes dans le CSS de leur thème.
- **`fonticons/views/css/material-icons.css`** :

  - **Portée** : Front-office et Back-office.
  - **Objectif** : Contient les règles CSS et les déclarations `@font-face` pour la bibliothèque Material Icons de Google. Ce fichier rend les Material Icons disponibles.
  - **Sélecteurs de classe CSS clés** : `material-icons`. Les icônes sont généralement rendues en plaçant le nom de la ligature de l'icône dans un élément avec cette classe (par exemple, `<i class="material-icons">shopping_cart</i>`). Les développeurs peuvent remplacer le style de cette classe.

### 4.6 Structure des templates Smarty (`views/templates/`)

- **`fonticons/views/advert.tpl`** :
  - **Portée** : Back-office (page de configuration du module).
  - **Objectif** : Ce template est utilisé pour afficher une publicité ou un message promotionnel dans la page de configuration du module dans le back-office de PrestaShop. Il est rendu par la méthode `getContent()`.

### 4.7 Schéma de la base de données et carte des hooks

- **Tables de la base de données** :
  Ce module ne crée aucune table de base de données personnalisée. Il stocke ses paramètres de configuration dans la table standard `ps_configuration`.

  - Entrées `ps_configuration` :
    - `fonticons_FA` : Stocke l'état (1 pour activé, 0 pour désactivé) de l'inclusion de Font Awesome pour le front-office.
    - `fonticons_MI` : Stocke l'état (1 pour activé, 0 pour désactivé) de l'inclusion de Material Icons pour le front-office.
    - `BO_fonticons_FA` : Stocke l'état (1 pour activé, 0 pour désactivé) de l'inclusion de Font Awesome pour le back-office.
    - `BO_fonticons_MI` : Stocke l'état (1 pour activé, 0 pour désactivé) de l'inclusion de Material Icons pour le back-office.
- **Table des hooks enregistrés** :

| Nom du hook | Moment d'exécution | Objectif technique |
| --- | --- | --- |
| `displayHeader` | Exécuté dans la section `<head>` de chaque page du front-office. | Utilisé pour charger les fichiers CSS Font Awesome et/ou Material Icons pour la partie visible par le client de la boutique, en fonction de la configuration `fonticons_FA` et `fonticons_MI`. |
| `actionAdminControllerSetMedia` | Exécuté lorsqu'un `AdminController` définit ses actifs multimédias (CSS/JS). | Utilisé pour charger les fichiers CSS Font Awesome et/ou Material Icons pour le back-office de PrestaShop, en fonction de la configuration `BO_fonticons_FA` et `BO_fonticons_MI`. |

## 5. Support officiel et mises à jour

Pour les dernières mises à jour du module, les corrections de bugs et le support officiel, veuillez vous connecter à votre compte client sur [MyPresta.eu](https://mypresta.eu/my-account/orders/). Vous y trouverez vos modules achetés et les liens de téléchargement. Pour une assistance technique ou toute question, veuillez utiliser les canaux de support fournis sur MyPresta.eu.
