---
title: "Se connecter en tant que client - Manuel du Marchand & Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop 'Se connecter en tant que client' par MyPresta.eu."
sidebar:
  label: "Se connecter en tant que client - Manuel du Marchand & Guide de Configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Log in as customer sur MyPresta.eu](https://mypresta.eu/modules/administration-tools/log-in-as-customer.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/back-office-tools/log-in-as-customer/)
>
> ---


# Se connecter en tant que client

## 1. Exigences et compatibilité

- **Versions PrestaShop prises en charge** : PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilité PHP** : PHP 5.6 - 8.5
- **Exigences d'hébergement** : Les extensions PHP standard (cURL, JSON, OpenSSL) sont généralement suffisantes. Aucune configuration de serveur spéciale n'est généralement nécessaire.

## 2. Parcours de configuration complet (chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

Le module « Se connecter en tant que client » a une configuration très simple. Après l'installation, lorsque vous cliquez sur « Configurer », vous serez dirigé vers un écran simple.

**Nom de l'écran et emplacement du menu :** Back Office > Modules > Gestionnaire de modules > Se connecter en tant que client > Configurer

Sur cet écran, vous trouverez généralement une simple confirmation que le module est installé et prêt. La fonctionnalité principale de ce module est intégrée directement dans votre liste de clients, plutôt que de nécessiter des paramètres étendus sur une page de configuration dédiée.

-   **Ce que fait cet écran :** Cette page confirme l'installation du module et fournit toute information de base ou liens rapides. Pour « Se connecter en tant que client », son objectif principal est de confirmer que le module est actif et prêt à l'emploi.
-   **Effet de la modification des paramètres :** Il n'y a pas de paramètres complexes à modifier ici. La fonctionnalité du module est activée dès l'installation.
-   **Valeur recommandée :** Aucune valeur spécifique à définir. Assurez-vous simplement que le module est installé et activé.
-   **Scénario/exemple pour le marchand :** Après l'installation, vous verrez un message confirmant que le module est actif. Vous pouvez ensuite vous rendre directement dans la section Clients de votre Back Office pour utiliser ses fonctionnalités.

### 2.2 Utilisation de la fonctionnalité « Se connecter en tant que client »

La fonctionnalité principale de ce module est accessible directement depuis votre liste de clients PrestaShop.

**Nom de l'écran et emplacement du menu :** Back Office > Clients > Clients

1.  **Naviguer vers les Clients :** Dans votre Back Office PrestaShop, allez dans le menu **Clients** puis cliquez sur **Clients**.
2.  **Localiser le client :** Trouvez le client pour lequel vous souhaitez vous connecter dans la liste des clients. Vous pouvez utiliser les options de recherche et de filtre pour le localiser rapidement.
3.  **Cliquer sur le bouton « Se connecter en tant que client » :** Pour chaque client de la liste, vous verrez désormais un bouton supplémentaire (souvent une icône comme une personne ou une clé, ou un bouton texte) dans la colonne « Actions ». Ce bouton est ajouté par le module « Se connecter en tant que client ».
    -   **Ce que fait ce bouton :** Lorsque vous cliquez sur ce bouton, le module effectue un processus de connexion sécurisé. Il vous déconnecte de votre compte administrateur (temporairement) puis vous connecte en tant que client sélectionné.
    -   **Effet de cliquer sur ce bouton :** Vous serez immédiatement redirigé vers le front office de votre boutique. Vous verrez la boutique exactement comme ce client la voit, y compris son panier actif, son historique de commandes, ses adresses et tout contenu ou prix personnalisé.
    -   **Scénario/exemple pour le marchand :** Un client signale un problème pour ajouter un produit spécifique à son panier. Vous naviguez vers « Clients », trouvez son nom, cliquez sur « Se connecter en tant que client », et êtes instantanément redirigé vers le front office en tant que lui. Vous pouvez alors essayer d'ajouter le produit vous-même, résoudre le problème ou vérifier le contenu de son panier.
4.  **Se déconnecter en tant que client :** Pour revenir à votre session administrateur du Back Office, il suffit de vous déconnecter du front office (comme si vous étiez un client régulier). Cela mettra fin à la session client, et vous pourrez ensuite vous reconnecter à votre Back Office.

### 2.3 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Par défaut / Recommandé | Objectif et impact |
| --- | --- | --- | --- |
| Page de configuration du module | (Pas de paramètres directs) | N/A | Confirme l'installation et la disponibilité du module. |
| Liste des clients (Back Office) | Bouton « Se connecter en tant que client » | N/A | Permet une connexion instantanée au front office en tant que client sélectionné pour le dépannage et les tests. |

## 3. Dépannage pour le marchand et questions fréquemment posées (FAQ)

**Q : J'ai installé le module, mais je ne vois pas le bouton « Se connecter en tant que client » dans la liste des clients.**
R :

1.  **Vider le cache :** Allez dans **Paramètres avancés > Performances** et cliquez sur « Vider le cache » (ou « Vider le cache Smarty » dans les versions plus anciennes).
2.  **Statut du module :** Assurez-vous que le module est activé. Allez dans **Modules > Gestionnaire de modules**, recherchez « Se connecter en tant que client » et vérifiez qu'il est actif.
3.  **Compatibilité du thème :** Bien que rare, certains thèmes fortement personnalisés peuvent interférer avec l'affichage des nouveaux boutons. Si le problème persiste, contactez le support MyPresta.eu.
4.  **Version de PrestaShop :** Assurez-vous d'avoir téléchargé la version correcte du module pour votre installation PrestaShop.

**Q : Lorsque je clique sur le bouton, je suis redirigé vers le front office, mais je ne suis pas connecté en tant que client.**
R :

1.  **Cookies du navigateur :** Assurez-vous que votre navigateur accepte les cookies. Essayez de vider le cache et les cookies de votre navigateur, puis réessayez.
2.  **Configuration de la session :** Vérifiez les paramètres `_PS_COOKIE_DOMAIN_` et `_PS_COOKIE_PATH_` dans le fichier `config/defines.inc.php` de votre PrestaShop. Assurez-vous qu'ils sont correctement configurés pour votre domaine.
3.  **Configuration du serveur :** Vérifiez que les paramètres de session PHP de votre serveur sont standard et non excessivement restrictifs.

**Q : Puis-je me connecter en tant que client et ensuite effectuer des actions comme passer une commande pour lui ?**
R : Oui, vous le pouvez. Cependant, faites preuve d'une extrême prudence. Obtenez toujours l'autorisation explicite du client avant d'effectuer toute action en son nom, en particulier passer des commandes ou modifier des données personnelles. Il est généralement préférable d'utiliser cette fonctionnalité pour la visualisation et le dépannage, et non pour apporter des modifications sans consentement.

**Q : Est-il sûr d'utiliser ce module ? Stocke-t-il les mots de passe des clients ?**
R : Le module ne stocke ni n'accède aux mots de passe des clients. Il utilise la gestion de session interne de PrestaShop pour simuler une connexion client, de manière similaire au fonctionnement de la fonctionnalité « Mot de passe oublié » de PrestaShop qui génère une session sécurisée temporaire. Il est conçu pour être sécurisé.

**Q : Que se passe-t-il si je me connecte en tant que client et que je ferme mon navigateur sans me déconnecter ?**
R : La session client expirera éventuellement en fonction des paramètres de délai d'expiration de session de votre PrestaShop. Pour revenir à votre panneau d'administration, il vous suffira de naviguer vers l'URL de votre Back Office et de vous reconnecter en tant qu'administrateur.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

### 4.1 Vue d'ensemble de l'architecture

Le module « Se connecter en tant que client » (`lac`) est un module PrestaShop léger principalement axé sur l'extension de la fonctionnalité de la liste des clients du Back Office. Il s'appuie sur les classes `Customer` et `Context` de PrestaShop pour gérer les sessions utilisateur et la redirection. Le module injecte du JavaScript dans le Back Office pour ajouter le bouton « Se connecter en tant que client » et utilise un contrôleur frontal dédié pour gérer le processus de connexion sécurisée et la redirection vers le front office. Il suit une architecture de module PrestaShop standard, s'intégrant de manière transparente sans tables de base de données personnalisées ni modèles d'objets complexes.

### 4.2 Contrôleurs (`controllers/`)

-   **Contrôleurs Front-Office** :

    -   `lac/controllers/front/index.php`
        -   **Nom de la classe** : `LacIndexModuleFrontController` (probable, basé sur la convention de nommage des fichiers)
        -   **Classe parente** : `ModuleFrontController`
        -   **Responsabilité** : Ce contrôleur sert probablement de point d'atterrissage ou de repli. Étant donné le contrôleur `login.php`, `index.php` pourrait être moins critique ou gérer la configuration/redirection initiale si `login.php` est le gestionnaire d'actions principal. Il pourrait également s'agir d'un espace réservé.
    -   `lac/controllers/front/login.php`
        -   **Nom de la classe** : `LacLoginModuleFrontController` (probable)
        -   **Classe parente** : `ModuleFrontController`
        -   **Responsabilité** : C'est le contrôleur principal de la fonctionnalité « Se connecter en tant que client ».
            -   Il reçoit l'ID du client via un paramètre GET ou POST depuis le Back Office.
            -   Il effectue les étapes nécessaires pour déconnecter la session administrateur actuelle.
            -   Il connecte ensuite en toute sécurité le client spécifié en manipulant les objets `Context` et `Customer` (par exemple, `Context::getContext()->customer = new Customer($id_customer); Context::getContext()->cookie->id_customer = $id_customer;`).
            -   Il redirige ensuite le navigateur vers la page d'accueil du front office ou une page spécifique liée au client (`my-account`, `history`, etc.).
-   **Contrôleurs d'administration Back-Office** :

    -   Aucun. Le module s'intègre directement dans la vue du contrôleur `AdminCustomers` existant via des hooks et du JavaScript.

### 4.3 Classes et modèles principaux (`classes/`)

-   Aucun. Ce module n'introduit pas de classes `ObjectModel` personnalisées ni de tables de base de données. Il opère directement sur les objets natifs `Customer` et `Context` de PrestaShop.

### 4.4 Assets JavaScript (`views/js/`)

Ces fichiers JavaScript sont responsables de l'injection du bouton « Se connecter en tant que client » dans la liste des clients du Back Office et de la gestion de l'événement de clic pour lancer le processus de connexion. Les différents noms de fichiers suggèrent des ajustements de compatibilité pour diverses versions de PrestaShop.

-   `lac/views/js/16customers.js`
    -   **Portée** : Back-office (liste `AdminCustomers` de PrestaShop 1.6.x).
    -   **Fonctionnalité** : Ce script cible le tableau de la liste des clients dans PrestaShop 1.6.x. Il utilise probablement des sélecteurs jQuery pour trouver la colonne « Actions » de chaque ligne client et ajoute un nouveau bouton ou lien. Le gestionnaire de clic pour ce bouton construira ensuite une URL pointant vers le contrôleur frontal du module (`lac/controllers/front/login.php`) avec l'ID du client et redirigera le navigateur.
-   `lac/views/js/176orders.js`
    -   **Portée** : Back-office (vue des commandes de PrestaShop 1.7.6.x).
    -   **Fonctionnalité** : Ce script pourrait être destiné à ajouter un bouton « Se connecter en tant que client » directement depuis la vue des commandes dans 1.7.6.x, permettant un accès rapide au client associé à une commande spécifique. Il extrairait l'ID du client de la page de détails de la commande et l'utiliserait pour la redirection de connexion.
-   `lac/views/js/177orders.js`
    -   **Portée** : Back-office (vue des commandes de PrestaShop 1.7.7.x+).
    -   **Fonctionnalité** : Similaire à `176orders.js`, mais adapté aux changements DOM potentiels ou aux différentes structures de tableau dans PrestaShop 1.7.7.x et les versions ultérieures de la vue des commandes.
-   `lac/views/js/17carts.js`
    -   **Portée** : Back-office (vue du panier de PrestaShop 1.7.x).
    -   **Fonctionnalité** : Ce script ajoute probablement le bouton « Se connecter en tant que client » à la page de détails du panier du Back Office, permettant à un administrateur de se connecter en tant que client associé à un panier spécifique.
-   `lac/views/js/17customersview.js`
    -   **Portée** : Back-office (liste `AdminCustomers` de PrestaShop 1.7.x, 8.x, 9.x).
    -   **Fonctionnalité** : C'est le script principal pour injecter le bouton dans la liste des clients pour les versions modernes de PrestaShop. Il ciblera la liste `AdminCustomers`, identifiera l'ID du client pour chaque ligne et ajoutera le bouton d'action « Se connecter en tant que client ». Il utilise la délégation d'événements pour gérer les clics sur ces boutons ajoutés dynamiquement, construisant l'URL appropriée pour le contrôleur `lac/controllers/front/login.php`.

### 4.5 Feuilles de style CSS (`views/css/`)

-   Aucun. Le module n'inclut pas de fichiers CSS personnalisés. Il s'appuie probablement sur le style par défaut de PrestaShop pour les boutons ou utilise des styles en ligne si nécessaire, ou le bouton est stylé par le thème du Back Office lui-même.

### 4.6 Structure des templates Smarty (`views/templates/`)

-   Aucun. Le module n'utilise pas de templates Smarty personnalisés. Son intégration au Back Office se fait uniquement par injection JavaScript, et la connexion au front office est gérée par une redirection directe depuis le contrôleur.

### 4.7 Schéma de la base de données et carte des hooks

-   **Tables de la base de données** :
    -   Le module ne crée aucune table de base de données personnalisée. Il stocke sa configuration (le cas échéant, bien qu'aucune n'ait été explicitement identifiée au-delà du statut de base du module) dans la table standard `ps_configuration`.
-   **Table des hooks enregistrés** :

| Nom du hook | Moment d'exécution | Objectif technique |
| --- | --- | --- |
| `displayBackOfficeHeader` | Exécuté dans la section `<head>` de chaque page du Back Office. | Utilisé pour inclure les fichiers JavaScript nécessaires (`16customers.js`, `17customersview.js`, etc.) dans le Back Office, spécifiquement lorsque le contrôleur `AdminCustomers` est actif. Cela garantit que le bouton « Se connecter en tant que client » est ajouté à la liste des clients. |
| `displayAdminCustomers` | Exécuté sur la page du contrôleur `AdminCustomers`. | Ce hook est spécifiquement conçu pour que les modules ajoutent du contenu ou des actions à la liste des clients. Le module pourrait utiliser ce hook pour rendre un petit template ou injecter directement du JavaScript pour ajouter le bouton. |
| `actionAdminControllerSetMedia` | Exécuté lorsqu'un contrôleur du Back Office définit ses médias (JS/CSS). | Un hook plus robuste pour ajouter du JS/CSS de manière conditionnelle en fonction du contrôleur actif. Le module l'utiliserait pour charger ses fichiers JS spécifiques uniquement sur les pages `AdminCustomers` ou `AdminOrders`. |
| `displayAdminOrder` | Exécuté sur la page du contrôleur `AdminOrders`. | Si le module ajoute un bouton « Se connecter en tant que client » à la vue des commandes (comme suggéré par `176orders.js`, `177orders.js`), ce hook serait utilisé pour injecter le JavaScript ou le HTML du bouton nécessaire. |
| `displayAdminCarts` | Exécuté sur la page du contrôleur `AdminCarts`. | Si le module ajoute un bouton « Se connecter en tant que client » à la vue du panier (comme suggéré par `17carts.js`), ce hook serait utilisé. |

## 5. Support officiel et mises à jour

Pour les dernières mises à jour, corrections de bugs et support officiel du module « Se connecter en tant que client », veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu/my-account/orders/). Notre équipe de support est disponible pour vous aider avec toute question ou problème technique que vous pourriez rencontrer.
