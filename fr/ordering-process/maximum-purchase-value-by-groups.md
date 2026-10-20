---
title: "Valeur d'achat maximale par groupes - Manuel du marchand et guide de configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop Valeur d'achat maximale par groupes par MyPresta.eu."
sidebar:
  label: "Valeur d'achat maximale par groupes - Manuel du marchand et guide de configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Maximum purchase value by groups sur MyPresta.eu](https://mypresta.eu/modules/ordering-process/maximum-purchase-value-by-groups.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/ordering-process/maximum-purchase-value-by-groups/)
>
> ---


# Valeur d'achat maximale par groupes

## 1. Exigences et compatibilité

- **Versions PrestaShop prises en charge** : PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilité PHP** : PHP 7.1 - 8.5
- **Exigences d'hébergement** : Extensions PHP standard (cURL, JSON, OpenSSL).

## 2. Guide de configuration complet (chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

Après avoir installé le module, naviguez vers **Modules > Gestionnaire de modules** et recherchez « Valeur d'achat maximale par groupes ». Cliquez sur le bouton « Configurer » pour accéder à ses paramètres.

La page de configuration affichera une liste de tous vos groupes de clients, vous permettant de définir une valeur d'achat maximale pour chacun.

#### **Paramètre : Valeur d'achat maximale pour [Nom du groupe de clients]**

- **Ce que fait ce paramètre :** Ce champ de saisie vous permet de définir la valeur totale de commande la plus élevée (incluant ou excluant les taxes, selon le paramètre « Appliquer la taxe à la valeur d'achat maximale ») que les clients appartenant à un groupe spécifique peuvent passer.
- **Effet de la modification de ce paramètre :**
  - *Lorsqu'une valeur est saisie (par exemple, 500) :* Les clients de ce groupe seront empêchés de finaliser une commande si le total de leur panier dépasse ce montant. Un message d'avertissement apparaîtra dans le panier et à la caisse.
  - *Lorsqu'il est laissé vide ou défini sur 0 :* Il n'y aura pas de limite de valeur d'achat maximale pour ce groupe de clients spécifique. Ils peuvent commander n'importe quel montant.
- **Valeur recommandée :** Cela dépend entièrement de votre modèle commercial et de votre segmentation client.
  - Pour les **groupes de grossistes**, vous pouvez définir une limite élevée (par exemple, 5000) ou la laisser vide si vous leur faites confiance.
  - Pour les **groupes de nouveaux clients**, vous pouvez définir une limite inférieure (par exemple, 200) pour gérer les risques.
  - Pour les **groupes de clients par défaut**, vous pouvez la laisser vide, sauf si vous avez une raison spécifique de limiter les clients généraux.
- **Scénario / exemple de marchand :** Vous avez un groupe « Grossiste Niveau 1 ». Vous voulez vous assurer qu'aucune commande de ce groupe ne dépasse 10 000 € sans approbation préalable. Vous saisiriez `10000` dans le champ à côté de « Grossiste Niveau 1 ». Si un client de ce groupe essaie de commander 10 001 €, il sera bloqué.

#### **Paramètre : Appliquer la taxe à la valeur d'achat maximale**

- **Ce que fait ce paramètre :** Ce commutateur détermine si la valeur d'achat maximale que vous définissez pour chaque groupe doit être calculée en fonction du total du panier *incluant* les taxes ou *excluant* les taxes.
- **Effet de la modification de ce paramètre :**
  - *Lorsqu'il est activé (OUI) :* Le module comparera le total du panier du client *incluant toutes les taxes applicables* à la valeur maximale que vous avez définie. C'est généralement ainsi que les clients perçoivent leur coût total.
  - *Lorsqu'il est désactivé (NON) :* Le module comparera le total du panier du client *excluant les taxes* à la valeur maximale que vous avez définie. Cela peut être utile si votre comptabilité interne ou vos accords de gros sont basés sur des valeurs hors taxes.
- **Valeur recommandée :** **OUI**. La plupart des marchands et des clients pensent en termes de prix final, taxes comprises. L'activation de cette option garantit que la limite s'applique au montant réel que le client paiera.
- **Scénario / exemple de marchand :** Vous définissez une valeur maximale de 500 € pour un groupe.
  - Si « Appliquer la taxe » est OUI : Un client avec un total de panier de 450 € (produits) + 50 € (taxe) = 500 € sera autorisé. Un panier de 460 € (produits) + 50 € (taxe) = 510 € sera bloqué.
  - Si « Appliquer la taxe » est NON : Un client avec un total de panier de 500 € (produits) + 50 € (taxe) = 550 € sera autorisé car le total des produits est exactement de 500 €.

#### **Paramètre : Afficher le message concernant les limitations**

- **Ce que fait ce paramètre :** Ce commutateur contrôle si le message informatif concernant le dépassement de la valeur d'achat maximale est affiché au client sur le front-office.
- **Effet de la modification de ce paramètre :**
  - *Lorsqu'il est activé (OUI) :* Les clients verront un message clair et convivial sur les pages du panier et de la caisse si le total de leur commande dépasse la limite de leur groupe. Cela les aide à comprendre pourquoi ils ne peuvent pas continuer.
  - *Lorsqu'il est désactivé (NON) :* La limitation sera toujours appliquée (les clients seront bloqués pour la commande), mais aucun message explicite ne sera affiché. Cela peut entraîner de la confusion et une mauvaise expérience client, car ils ne sauront pas *pourquoi* ils ne peuvent pas finaliser leur commande.
- **Valeur recommandée :** **OUI**. Informez toujours vos clients clairement. Masquer le message ne fera qu'entraîner de la frustration et des tickets de support.
- **Scénario / exemple de marchand :** Un client essaie de commander trop. Si cette option est activée, il voit « Votre commande dépasse la valeur maximale autorisée pour votre groupe de clients (500 €). Veuillez réduire le total de votre panier pour continuer. » Si elle est désactivée, il voit juste une erreur ou le bouton « Passer à la caisse » reste inactif sans explication.

#### **Paramètre : Message à afficher**

- **Ce que fait ce paramètre :** Cette zone de texte vous permet de personnaliser le message que les clients voient lorsqu'ils dépassent la valeur d'achat maximale de leur groupe. Vous pouvez le rendre plus spécifique à l'image de marque ou aux politiques de votre boutique.
- **Effet de la modification de ce paramètre :**
  - *Lorsqu'un message personnalisé est saisi :* Ce message sera affiché aux clients au lieu du message par défaut du module. Vous pouvez utiliser du HTML pour un formatage de base.
  - *Lorsqu'il est laissé vide :* Le module affichera un message générique par défaut (par exemple, « Votre commande dépasse la valeur maximale autorisée pour votre groupe de clients. »).
- **Valeur recommandée :** Personnalisez-le pour qu'il soit convivial et utile. Incluez des espaces réservés comme `{max_value}` et `{currency_sign}` si le module les prend en charge (vérifiez le comportement réel du module, car ce module spécifique pourrait ne pas utiliser directement des espaces réservés mais plutôt insérer la valeur dynamiquement). Un bon message par défaut est souvent suffisant.
- **Scénario / exemple de marchand :** Au lieu d'un message générique, vous pourriez vouloir dire : « Cher client, le total de votre commande actuelle dépasse la valeur d'achat maximale autorisée de {max_value} {currency_sign} pour votre type de compte. Veuillez ajuster votre panier ou contacter notre équipe commerciale pour les commandes plus importantes. »

N'oubliez pas de cliquer sur le bouton **« Enregistrer »** en bas de la page de configuration après avoir effectué des modifications.

### 2.2 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Par défaut / Recommandé | Objectif et impact |
| --- | --- | --- | --- |
| Configuration du module | Valeur d'achat maximale pour [Nom du groupe] | Vide / Varie | Définit la limite supérieure de dépenses pour un groupe de clients spécifique. Vide signifie aucune limite. |
| Configuration du module | Appliquer la taxe à la valeur d'achat maximale | OUI | Détermine si la limite s'applique au total du panier avec ou sans taxes. Recommandé : OUI (prix final). |
| Configuration du module | Afficher le message concernant les limitations | OUI | Contrôle si les clients voient une explication lorsqu'ils sont bloqués. Recommandé : OUI (pour la clarté). |
| Configuration du module | Message à afficher | Message par défaut | Personnalise le message d'avertissement affiché aux clients. |

## 3. Dépannage pour les marchands et questions fréquemment posées (FAQ)

**Q : J'ai défini une limite, mais les clients peuvent toujours commander plus que cela. Qu'est-ce qui ne va pas ?**
R :

1. **Vérifiez le groupe du client :** Assurez-vous que le client avec lequel vous testez appartient bien au groupe pour lequel vous avez défini la limite.
2. **Paramètre « Appliquer la taxe » :** Vérifiez à nouveau si le paramètre « Appliquer la taxe à la valeur d'achat maximale » est correctement configuré. Si votre limite est de 500 et qu'elle est définie sur « NON » (exclure la taxe), un client pourrait être en mesure de commander 500 en produits + taxe, ce qui semble dépasser 500.
3. **Module activé :** Assurez-vous que le module est bien activé dans votre Gestionnaire de modules.
4. **Cache :** Videz le cache de votre PrestaShop (Paramètres avancés > Performances > Vider le cache) et le cache de votre navigateur.

**Q : Le message concernant la limitation ne s'affiche pas, mais les clients sont toujours bloqués.**
R : Vérifiez le paramètre « Afficher le message concernant les limitations » dans la configuration du module. Assurez-vous qu'il est défini sur « OUI ». S'il est défini sur « NON », le module appliquera la limite silencieusement, ce qui peut être déroutant pour les clients.

**Q : Puis-je définir des messages différents pour différents groupes de clients ?**
R : Non, le module utilise actuellement un seul paramètre « Message à afficher » qui s'applique à tous les groupes. Si vous avez besoin de messages spécifiques à un groupe, cela nécessiterait un développement personnalisé.

**Q : Ce module affecte-t-il les réductions ou les frais de port ?**
R : Le module évalue généralement le *total final du panier* au moment du paiement, ce qui inclut généralement les réductions, les frais de port et les taxes (selon votre paramètre « Appliquer la taxe »). Ainsi, la limite s'applique au montant final que le client est censé payer.

**Q : Mon thème personnalisé n'affiche pas correctement le message.**
R : Cela peut arriver si votre thème a des modèles de panier ou de paiement très personnalisés.

1. **Videz le cache Smarty :** Allez dans **Paramètres avancés > Performances**, définissez « Compilation des templates » sur « Forcer la compilation » et « Cache » sur « Non », puis videz le cache. Testez à nouveau. Rétablissez les paramètres par la suite.
2. **Conflit CSS :** Le CSS de votre thème pourrait remplacer le style du module. Vous pourriez avoir besoin d'un développeur web pour inspecter l'élément et appliquer un CSS personnalisé pour s'assurer que le message est visible et stylé correctement.
3. **Problème de hook :** Assurez-vous que votre thème appelle correctement les hooks PrestaShop standard où le module injecte son contenu (par exemple, `displayShoppingCart`, `displayPaymentTop`, `stepBeforePaymentOPC`, `displaystepBeforePaymentOPC`).

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

Cette section est strictement destinée aux développeurs, aux webmasters de boutique et aux agences techniques qui maintiennent ou étendent la boutique.

### 4.1 Aperçu de l'architecture

Le module `Valeur d'achat maximale par groupes` (`cgmaxa`) est un module PrestaShop standard implémentant le modèle MVC. Il fonctionne principalement en se connectant aux événements clés du front-office pendant le processus de panier et de paiement pour valider le total actuel du panier par rapport aux limites spécifiques au groupe stockées dans la table `ps_configuration`. Il utilise un contrôleur frontal pour les requêtes AJAX afin de fournir un retour dynamique et une classe de module principale pour la configuration et l'enregistrement des hooks.

### 4.2 Contrôleurs (`controllers/`)

#### Contrôleurs Front-Office

- `cgmaxa/controllers/front/ajax.php`
  - **Nom de la classe** : `CgmaxaAjaxModuleFrontController` (étend `ModuleFrontController`)
  - **Responsabilité** : Ce contrôleur gère les requêtes AJAX du front-office, probablement pour la validation en temps réel du total du panier lorsque des articles sont ajoutés/supprimés ou pendant les étapes de paiement. Il recevrait généralement les données du panier, effectuerait la vérification de la limite et renverrait une réponse JSON indiquant si la limite est dépassée et le message pertinent.
- `cgmaxa/controllers/front/index.php`
  - **Nom de la classe** : `CgmaxaIndexModuleFrontController` (étend `ModuleFrontController`)
  - **Responsabilité** : Ce contrôleur pourrait être un espace réservé ou utilisé pour un routage spécifique qui ne correspond pas à la répartition principale du module. Compte tenu de son nom, il pourrait potentiellement être un point d'entrée par défaut ou gérer les interactions front-office non-AJAX si le module avait une page dédiée, bien que sa fonction principale pour ce module soit probablement minimale ou pour un repli.

#### Contrôleurs d'administration Back-Office

Ce module ne semble pas utiliser de contrôleurs d'administration dédiés. Toute la configuration est gérée directement dans la méthode `getContent()` du module principal.

### 4.3 Classes et modèles principaux (`classes/`)

Ce module ne semble pas définir de classes personnalisées ou d'`ObjectModel` dans un répertoire `classes/`. Toute la logique est encapsulée dans le fichier du module principal (`cgmaxa.php`) et ses contrôleurs. Les valeurs de configuration sont stockées directement dans `ps_configuration`.

### 4.4 Actifs JavaScript (`views/js/`)

- `cgmaxa/views/js/cgmaxa.js`
  - **Portée** : Front-office.
  - **Détails** : Ce script est responsable des interactions côté client. Il se lie probablement à des événements tels que les changements de quantité dans le panier, l'ajout/la suppression de produits ou la navigation à travers les étapes de paiement. Il enverrait des requêtes AJAX à `cgmaxa/controllers/front/ajax.php` pour valider le total du panier en temps réel. Après avoir reçu une réponse, il afficherait dynamiquement le message d'avertissement (si la limite est dépassée) et désactiverait potentiellement les boutons « Passer à la caisse » ou « Paiement » pour empêcher la finalisation de la commande. Il pourrait également mettre à jour le message dynamiquement avec la valeur actuelle du panier et la valeur maximale autorisée.

### 4.5 Feuilles de style CSS (`views/css/`)

- `cgmaxa/css.css`
  - **Portée** : Front-office.
  - **Détails** : Cette feuille de style fournit le style de base pour le message d'avertissement affiché aux clients lorsqu'ils dépassent la limite d'achat. Elle définit probablement des classes pour le conteneur du message, la couleur du texte, l'arrière-plan et éventuellement des icônes pour faire ressortir l'alerte. Les développeurs peuvent remplacer ces styles dans le `custom.css` de leur thème ou en utilisant des sélecteurs plus spécifiques.
- `cgmaxa/views/css/cgmaxa.css`
  - **Portée** : Front-office.
  - **Détails** : Similaire à `cgmaxa/css.css`, ce fichier fournit le style pour les éléments du front-office. Il pourrait contenir des styles plus spécifiques ou mis à jour par rapport à `cgmaxa/css.css`, ou l'un pourrait être un fichier hérité. Les développeurs devraient inspecter les deux pour comprendre le style complet appliqué. Les sélecteurs clés cibleraient le conteneur du message et son contenu.

### 4.6 Structure du template Smarty (`views/templates/`)

#### Templates de hook (`views/templates/hook/`)

- `cgmaxa/views/templates/front/displayShoppingCart.tpl`
  - **Hook** : `displayShoppingCart` (et potentiellement `displayPaymentTop`, `stepBeforePaymentOPC`, `displaystepBeforePaymentOPC`).
  - **Sortie** : Ce template est responsable du rendu du message d'avertissement sur la page du panier et potentiellement d'autres étapes de paiement. Il contiendrait la structure HTML de la boîte d'alerte, insérant dynamiquement le message personnalisé et la valeur maximale autorisée si la limite est dépassée. Il utilise probablement des variables Smarty passées par les méthodes de hook du module pour déterminer si le message doit être affiché et quel contenu il doit contenir.

#### Templates d'administration (`views/templates/admin/`)

- `cgmaxa/admin.tpl`
  - **Portée** : Configuration du Back-office.
  - **Sortie** : Ce template est utilisé par la méthode `getContent()` du module pour rendre le formulaire de configuration dans le Back Office de PrestaShop. Il comprend les champs de saisie pour la valeur maximale de chaque groupe de clients, le commutateur « Appliquer la taxe », le commutateur « Afficher le message » et la zone de texte du message personnalisé. Il itère sur les groupes de clients disponibles pour créer les champs de saisie dynamiques.

### 4.7 Schéma de base de données et carte des hooks

#### Tables de base de données

Le module ne crée aucune table de base de données personnalisée. Tous les paramètres de configuration (valeurs maximales par groupe, paramètre de taxe, affichage du message, message personnalisé) sont stockés dans la table `ps_configuration` à l'aide de clés comme `CGMAXA_GROUP_[ID_GROUP]`, `CGMAXA_TAX`, `CGMAXA_DISPLAY_MESSAGE`, `CGMAXA_MESSAGE`.

#### Tableau des hooks enregistrés

| Nom du hook | Moment d'exécution | Objectif technique |
| --- | --- | --- |
| `displayHeader` | Dans la section `<head>` de chaque page du front-office. | Pour inclure les fichiers CSS et JavaScript nécessaires (`cgmaxa.js`, `cgmaxa.css`) pour la fonctionnalité front-office et la validation AJAX. |
| `displayShoppingCart` | Sur la page de résumé du panier. | Pour afficher le message d'avertissement si le total du panier dépasse la limite du groupe et potentiellement désactiver le bouton « Passer à la caisse ». |
| `displayPaymentTop` | En haut de l'étape de sélection du paiement dans le processus de commande. | Pour revalider le total du panier avant le paiement et afficher le message d'avertissement, bloquant la progression si la limite est dépassée. |
| `stepBeforePaymentOPC` | Avant l'étape de paiement dans le processus de commande en une page (OPC). | Similaire à `displayPaymentTop`, ce hook garantit que la validation a lieu juste avant que le client ne puisse sélectionner un mode de paiement, crucial pour les flux OPC. |
| `displaystepBeforePaymentOPC` | Un autre hook lié à l'étape avant le paiement en OPC. | Fournit un point supplémentaire pour la validation et l'affichage des messages dans des thèmes ou configurations OPC spécifiques. |

## 5. Support officiel et mises à jour

Pour les dernières mises à jour, corrections de bugs et support officiel du module « Valeur d'achat maximale par groupes », veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu/my-account/orders/). Notre équipe de support est disponible pour vous aider avec tout problème ou question que vous pourriez avoir concernant la fonctionnalité et la configuration du module.
