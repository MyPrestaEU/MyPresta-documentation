---
title: "Envoyer à un ami - Manuel du Marchand & Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop Envoyer à un ami par MyPresta.eu."
sidebar:
  label: "Envoyer à un ami - Manuel du Marchand & Guide de Configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Send to a friend sur MyPresta.eu](https://mypresta.eu/modules/advertising-and-marketing/send-to-a-friend.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/advertising-marketing/send-to-a-friend/)
>
> ---


# Envoyer à un ami

## 1. Exigences et compatibilité

- **Versions PrestaShop prises en charge :** PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilité PHP :** PHP 7.1 - 8.5
- **Exigences d'hébergement :** Les extensions PHP standard (cURL, JSON, OpenSSL) sont généralement requises pour une installation PrestaShop et sont suffisantes pour ce module.

## 2. Guide de configuration complet (Chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

Ceci est l'écran de configuration principal du module « Envoyer à un ami ». Ici, vous pouvez contrôler le comportement et l'apparence de la fonctionnalité sur vos pages produits.

#### Paramètres généraux

-   **Ce que fait ce paramètre :** Cette section contient les paramètres essentiels pour activer ou désactiver le module et contrôler sa fonctionnalité de base.
-   **Effet de la modification de ce paramètre :**
    -   *Lorsqu'il est activé :* Le lien/bouton « Envoyer à un ami » et la fonctionnalité apparaîtront sur vos pages produits comme configuré.
    -   *Lorsqu'il est désactivé :* La fonctionnalité sera complètement masquée de votre boutique, et aucun e-mail ne pourra être envoyé via celle-ci.
-   **Valeur recommandée :** **OUI** (Activé) pour permettre aux clients d'utiliser la fonctionnalité.
-   **Scénario / exemple pour le marchand :** Si vous souhaitez désactiver temporairement la fonctionnalité pour une maintenance ou une campagne marketing spécifique, vous la passeriez à « NON ». Sinon, gardez-la à « OUI » pour tirer parti du marketing de bouche-à-oreille.

#### Options d'affichage

-   **Ce que fait ce paramètre :** Ces options contrôlent l'emplacement du lien ou du bouton « Envoyer à un ami » sur vos pages produits. Le module utilise le système de hooks de PrestaShop pour placer la fonctionnalité dans différentes zones.
-   **Effet de la modification de ce paramètre :**
    -   *Sélectionner un hook (par exemple, `displayProductButtons`) :* Le lien « Envoyer à un ami » sera rendu dans cette zone spécifique de votre page produit.
    -   *Ne sélectionner aucun hook :* La fonctionnalité pourrait ne pas apparaître du tout, ou elle pourrait apparaître à un emplacement par défaut si votre thème a un rendu de secours spécifique.
-   **Valeur recommandée :** `displayProductButtons` ou `displayProductActions` sont des hooks courants et recommandés car ils placent le lien près du bouton « Ajouter au panier », le rendant facilement découvrable. Vous pourriez également envisager `displayFooterProduct` si vous préférez qu'il soit en bas des détails du produit.
-   **Scénario / exemple pour le marchand :** Si vous souhaitez que le lien « Envoyer à un ami » soit très visible et proche de l'appel à l'action principal, choisissez `displayProductButtons`. Si vous préférez qu'il soit moins proéminent, peut-être en bas des informations du produit, sélectionnez `displayFooterProduct`. Expérimentez avec différents hooks pour voir ce qui convient le mieux à votre thème.

#### Modèle et contenu de l'e-mail

-   **Ce que fait ce paramètre :** Cette section vous permet de personnaliser l'objet et le contenu de l'e-mail envoyé à l'ami.
-   **Effet de la modification de ce paramètre :**
    -   *Modifier l'objet :* La ligne d'objet de l'e-mail reflétera votre texte personnalisé, le rendant plus engageant ou marqué.
    -   *Modifier le contenu :* Le corps de l'e-mail inclura votre message personnalisé, vous permettant de personnaliser la recommandation. Vous pouvez utiliser des placeholders comme `{product_name}` et `{product_link}` qui seront automatiquement remplacés par les détails réels du produit.
-   **Valeur recommandée :** Utilisez une ligne d'objet claire et invitante (par exemple, « Découvrez ce produit de {your\_shop\_name} ! ») et un message amical et informatif dans le corps. Incluez toujours `{product_name}` et `{product_link}` pour vous assurer que l'ami sait ce qui est recommandé et comment le trouver.
-   **Scénario / exemple pour le marchand :** Vous pourriez personnaliser l'e-mail pour dire : « Salut {friend\_name}, {customer\_name} a pensé que vous pourriez aimer ce produit de Ma Super Boutique ! Il s'appelle {product\_name} et vous pouvez le trouver ici : {product\_link}. Bon shopping ! »

### 2.2 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Par défaut / Recommandé | Objectif et impact |
| --- | --- | --- | --- |
| Configuration du module | Activer/Désactiver le module | Activé | Contrôle si la fonctionnalité « Envoyer à un ami » est active sur votre boutique. |
| Configuration du module | Hook d'affichage | `displayProductButtons` | Détermine où le lien « Envoyer à un ami » apparaît sur les pages produits. |
| Configuration du module | Objet de l'e-mail | « Découvrez ce produit ! » | Personnalise la ligne d'objet de l'e-mail envoyé à l'ami. |
| Configuration du module | Contenu de l'e-mail | « Salut {friend\_name}, {customer\_name} a pensé que vous pourriez aimer ce produit : {product\_name}. Vous pouvez le trouver ici : {product\_link} » | Personnalise le corps de l'e-mail, y compris les détails dynamiques du produit. |

## 3. Dépannage pour les marchands et questions fréquemment posées (FAQ)

**Q : Le lien « Envoyer à un ami » n'apparaît pas sur mes pages produits. Que dois-je faire ?**
R :

1.  **Vérifier l'état du module :** Allez dans **Modules > Gestionnaire de modules** et assurez-vous que le module « Envoyer à un ami » est installé et activé.
2.  **Vérifier la configuration :** Allez sur la page de configuration du module et assurez-vous que le module est « Activé » et que vous avez sélectionné au moins un « Hook d'affichage » (par exemple, `displayProductButtons`).
3.  **Vider le cache :** PrestaShop met souvent en cache le contenu. Allez dans **Paramètres avancés > Performance** et cliquez sur « Vider le cache » (ou « Vider le cache Smarty » dans les versions plus anciennes).
4.  **Compatibilité du thème :** Si vous utilisez un thème personnalisé, il pourrait ne pas être explicitement conçu pour rendre tous les hooks de PrestaShop. Essayez de passer temporairement au thème PrestaShop par défaut pour voir si le lien apparaît. Si c'est le cas, votre thème pourrait nécessiter une petite modification par un webmaster pour afficher le hook choisi.

**Q : Mes clients envoient des e-mails, mais leurs amis ne les reçoivent pas.**
R :

1.  **Vérifier les dossiers de spam :** Demandez à l'ami de vérifier son dossier de spam ou de courrier indésirable.
2.  **Vérifier les paramètres d'e-mail :** Assurez-vous que les paramètres d'e-mail de votre boutique PrestaShop sont correctement configurés sous **Paramètres avancés > E-mail**. Testez l'envoi d'un e-mail général depuis PrestaShop pour confirmer que votre serveur de messagerie fonctionne.
3.  **Journaux du module (Vérification du développeur) :** Un développeur peut vérifier les journaux de messagerie de PrestaShop (si activés) ou les journaux d'erreurs du serveur pour les problèmes liés à l'envoi d'e-mails.

**Q : Puis-je modifier le texte du lien « Envoyer à un ami » ou les champs du formulaire ?**
R : Oui, vous pouvez traduire ou modifier les chaînes de texte (libellés, texte des boutons, etc.) du module à l'aide de l'outil de traduction de PrestaShop. Allez dans **International > Traductions**, sélectionnez « Traductions des modules installés », choisissez votre thème, puis sélectionnez le module « Envoyer à un ami ». Vous pourrez alors modifier tout le texte visible.

**Q : Le formulaire pop-up a une apparence étrange ou n'est pas correctement stylisé sur mon appareil mobile.**
R :

1.  **Vider le cache du navigateur :** Demandez au client de vider le cache de son navigateur sur son appareil mobile.
2.  **Conflits de thème :** Les thèmes personnalisés peuvent parfois remplacer ou entrer en conflit avec le style du module. Bien que le module inclue son propre CSS (`send2friend.css`), le CSS de votre thème pourrait prendre le pas. Un webmaster peut inspecter la page à l'aide des outils de développement du navigateur pour identifier et résoudre les conflits CSS.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

Cette section fournit un aperçu technique détaillé pour les développeurs et les webmasters.

### 4.1 Aperçu de l'architecture

Le module « Envoyer à un ami » (`send2friend`) est un module PrestaShop standard implémentant le modèle MVC. Il utilise principalement des contrôleurs frontaux pour les requêtes AJAX, des templates Smarty pour le rendu du formulaire et des hooks pour s'intégrer à la page produit. Il n'introduit pas de tables de base de données personnalisées ni d'ObjectModels complexes, s'appuyant sur la fonctionnalité de messagerie de base de PrestaShop.

### 4.2 Contrôleurs (`controllers/`)

#### Contrôleurs Front-Office

-   **`controllers/front/AjaxSend.php`**
    -   **Nom de la classe :** `Send2FriendAjaxSendModuleFrontController`
    -   **Classe parente :** `ModuleFrontController`
    -   **Responsabilité :** Ce contrôleur gère la requête AJAX initiée lorsqu'un utilisateur soumet le formulaire « Envoyer à un ami ». Il reçoit le nom de l'expéditeur, le nom de l'ami, l'e-mail de l'ami et l'ID du produit. Il construit ensuite et envoie l'e-mail en utilisant la méthode `Mail::Send()` de PrestaShop. Il renvoie une réponse JSON indiquant le succès ou l'échec.
-   **`controllers/front/index.php`**
    -   **Nom de la classe :** `Send2FriendIndexModuleFrontController`
    -   **Classe parente :** `ModuleFrontController`
    -   **Responsabilité :** Il s'agit d'un contrôleur frontal de substitution ou par défaut. Dans de nombreux modules, cela pourrait gérer une page front-office dédiée. Pour « Envoyer à un ami », son rôle principal pourrait être de s'assurer que les ressources front-office du module sont chargées ou de servir de base à d'autres contrôleurs frontaux. Compte tenu de la fonctionnalité du module, le contrôleur `AjaxSend` est le plus actif.

### 4.3 Classes et modèles de base (`classes/`)

Le module ne contient aucune classe ou modèle personnalisé dans le répertoire `classes/`. Il tire parti des fonctionnalités de base de PrestaShop, en particulier `Mail` pour l'envoi d'e-mails et `Product` pour la récupération des informations sur les produits.

### 4.4 Ressources JavaScript (`views/js/`)

-   **`views/js/send2friend.js`**
    -   **Portée :** Front-office.
    -   **Détails :** Ce script est responsable de l'interaction front-end de la fonctionnalité « Envoyer à un ami ».
        -   Il attache probablement un écouteur d'événements au lien/bouton « Envoyer à un ami » pour ouvrir la modale ou afficher le formulaire.
        -   Il gère la soumission du formulaire, collectant les données (nom de l'expéditeur, nom de l'ami, e-mail de l'ami, ID du produit).
        -   Il envoie une requête AJAX au contrôleur frontal `AjaxSend.php`.
        -   Il traite la réponse JSON du serveur (succès/erreur) et fournit un retour à l'utilisateur (par exemple, « E-mail envoyé avec succès ! » ou « Erreur lors de l'envoi de l'e-mail. »).
        -   Il peut inclure une logique de validation de formulaire (par exemple, vérification des formats d'e-mail valides).
        -   Il utilise jQuery pour la manipulation du DOM et les appels AJAX, courants dans le front-office de PrestaShop.

### 4.5 Feuilles de style CSS (`views/css/`)

-   **`views/css/send2friend.css`**
    -   **Portée :** Style client du Front-office.
    -   **Détails :** Cette feuille de style fournit le style visuel de base pour le lien « Envoyer à un ami », la modale pop-up (si utilisée) et les champs du formulaire qu'elle contient.
        -   Elle définit les styles pour le bouton/lien, les champs de saisie, les étiquettes et les messages de succès/erreur.
        -   Les sélecteurs de classe CSS clés que les développeurs peuvent remplacer dans leur thème incluraient généralement des classes comme `.send2friend-button`, `.send2friend-modal`, `.send2friend-form`, `.send2friend-input`, etc. Les développeurs peuvent inspecter le HTML rendu pour trouver les classes exactes utilisées.

### 4.6 Structure du template Smarty (`views/templates/`)

-   **`views/templates/hook/send2friend-extra.tpl`**
    -   **Portée :** Front-office.
    -   **Rendu du hook :** Ce template est conçu pour être rendu dans divers hooks de page produit (par exemple, `displayProductButtons`, `displayProductActions`, `displayFooterProduct`).
    -   **Bloc visuel :** Il génère la structure HTML pour le lien/bouton « Envoyer à un ami » et la modale ou le formulaire en ligne associé. Cela inclut les champs de saisie pour les noms et les adresses e-mail, et le bouton de soumission. Il contient également les champs cachés nécessaires (comme `product_id`) et potentiellement la structure pour afficher les messages de succès/erreur.

### 4.7 Schéma de la base de données et carte des hooks

#### Tables de la base de données

Le module « Envoyer à un ami » ne crée aucune table de base de données personnalisée. Il stocke ses paramètres de configuration (comme l'état activé, le hook choisi, l'objet et le contenu de l'e-mail) dans la table `ps_configuration` de PrestaShop.

-   **`ps_configuration`** : Stocke les paramètres du module avec des clés généralement préfixées par `SEND2FRIEND_`.

#### Tableau des hooks enregistrés

| Nom du hook | Moment d'exécution | Objectif technique |
| --- | --- | --- |
| `displayHeader` | Dans la section `<head>` de chaque page. | Utilisé pour charger les ressources CSS et JavaScript du module globalement. |
| `displayProductButtons` | Près du bouton « Ajouter au panier » sur les pages produits. | Emplacement courant pour le lien « Envoyer à un ami ». |
| `displayProductActions` | Un autre hook courant près des actions produit. | Emplacement alternatif pour le lien « Envoyer à un ami ». |
| `displayFooterProduct` | En bas du bloc d'informations produit. | Emplacement moins proéminent pour le lien « Envoyer à un ami ». |
| `displayRightColumnProduct` | Dans la colonne de droite de la page produit (si activé par le thème). | Emplacement possible pour le lien « Envoyer à un ami ». |
| `displayLeftColumnProduct` | Dans la colonne de gauche de la page produit (si activé par le thème). | Emplacement possible pour le lien « Envoyer à un ami ». |

La méthode `install()` du module enregistre ces hooks, et la méthode `uninstall()` les désenregistre. Le hook spécifique choisi par le marchand dans la configuration détermine celui qui est activement utilisé pour afficher le template.

## 5. Support officiel et mises à jour

Pour les dernières mises à jour, corrections de bugs et support officiel du module « Envoyer à un ami », veuillez vous référer à votre compte client MyPresta.eu. Vous pouvez télécharger les versions les plus récentes et accéder aux ressources de support directement depuis [MyPresta.eu](https://mypresta.eu).
