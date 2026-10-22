---
title: "Block IP address Pro - Manuel du Marchand & Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop Block IP address Pro par MyPresta.eu."
sidebar:
  label: "Block IP address Pro"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Block IP address Pro sur MyPresta.eu](https://mypresta.eu/modules/administration-tools/block-ip-address-pro.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/back-office-tools/block-ip-address-pro/)
>
> ---


# Block IP address Pro

## 1. Exigences et Compatibilité
- **Versions PrestaShop Supportées :** PrestaShop 1.4.x, 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilité PHP :** PHP 5.6 - 8.5
- **Exigences d'Hébergement :** Extensions PHP standard (cURL, JSON, OpenSSL) généralement disponibles sur tout environnement d'hébergement web moderne.

## 2. Parcours de Configuration Complet (Chaque Paramètre Groupé par Écran)

### 2.1 Page de Configuration du Module (Back Office > Modules > Configurer > Block IP address Pro)

Ceci est l'écran de configuration principal du module, où vous définissez le comportement global pour les visiteurs bloqués.

-   **Emplacement du Menu :** Back Office > Modules > Gestionnaire de modules > Block IP address Pro > Configurer

#### Paramètres et Options :

1.  **Afficher les notifications de mise à jour**
    -   **Ce que fait ce paramètre :** Contrôle si vous recevez des notifications dans votre back office PrestaShop lorsqu'une nouvelle version du module "Block IP address Pro" est disponible.
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsqu'activé :* Vous verrez des alertes ou des messages dans votre panneau d'administration si une mise à jour est publiée, vous aidant à maintenir votre module à jour.
        -   *Lorsqu'désactivé :* Vous ne recevrez pas ces notifications, et vous devrez vérifier manuellement les mises à jour sur MyPresta.eu.
    -   **Valeur recommandée :** OUI
    -   **Scénario / exemple marchand :** Garder cette option activée vous assure d'être toujours informé des nouvelles fonctionnalités, corrections de bugs ou améliorations de sécurité pour le module.

2.  **Message pour les utilisateurs bloqués (`banippro_msg`)**
    -   **Ce que fait ce paramètre :** C'est le message personnalisé qui sera affiché aux utilisateurs dont l'adresse IP a été bloquée, *si* vous choisissez de ne pas les rediriger.
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsqu'il est rempli :* Les utilisateurs bloqués verront ce texte spécifique sur une page blanche au lieu du contenu de votre boutique.
        -   *Lorsqu'il est vide :* Si la redirection est également désactivée, les utilisateurs bloqués pourraient voir une erreur générique ou une page blanche sans message spécifique.
    -   **Valeur recommandée :** "L'accès à cette boutique a été refusé pour votre adresse IP." (ou un message poli mais ferme similaire).
    -   **Scénario / exemple marchand :** Vous pourriez vouloir afficher "Nous sommes désolés, mais l'accès depuis votre emplacement a été restreint en raison d'une activité inhabituelle." pour informer l'utilisateur sans donner trop de détails.

3.  **Rediriger les utilisateurs bloqués (`banippro_redirect`)**
    -   **Ce que fait ce paramètre :** Détermine si les utilisateurs bloqués voient un message ou sont automatiquement envoyés vers une autre page web.
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsqu'activé :* Les utilisateurs bloqués seront immédiatement redirigés vers l'URL spécifiée dans le paramètre "URL de redirection".
        -   *Lorsqu'désactivé :* Les utilisateurs bloqués verront le "Message pour les utilisateurs bloqués" que vous avez défini.
    -   **Valeur recommandée :** OUI (La redirection est souvent une expérience utilisateur plus propre qu'une page blanche avec un message).
    -   **Scénario / exemple marchand :** Si vous voulez éloigner complètement les spammeurs de votre site, ou diriger un client problématique vers une page de service client, activez cette option.

4.  **URL de redirection (`banippro_url`)**
    -   **Ce que fait ce paramètre :** L'adresse web spécifique (URL) vers laquelle les utilisateurs bloqués seront redirigés si le paramètre "Rediriger les utilisateurs bloqués" est activé.
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsqu'il est rempli avec une URL valide :* Les utilisateurs bloqués seront envoyés vers cette page exacte.
        -   *Lorsqu'il est vide :* Si la redirection est activée mais qu'aucune URL n'est fournie, le comportement du module pourrait être imprévisible, ou il pourrait afficher le message par défaut.
    -   **Valeur recommandée :** L'URL de la page d'accueil de votre boutique (par exemple, `https://www.votreboutique.com/`), ou une page "Contactez-nous" spécifique, ou même un site externe comme Google.
    -   **Scénario / exemple marchand :** Vous pourriez les rediriger vers `https://www.votreboutique.com/contactez-nous` si vous voulez qu'ils vous contactent, ou vers `https://www.google.com` pour simplement les retirer de votre site.

#### Tableau de Référence Rapide de la Configuration

| Écran / Vue | Paramètre / Option | Valeur par défaut / Recommandée | Objectif et Impact |
|---|---|---|---|
| Configuration du Module | Afficher les notifications de mise à jour | OUI | Affiche des alertes pour les nouvelles versions du module. |
| Configuration du Module | Message pour les utilisateurs bloqués | "L'accès à cette boutique a été refusé pour votre adresse IP." | Texte affiché aux utilisateurs bloqués s'ils ne sont pas redirigés. |
| Configuration du Module | Rediriger les utilisateurs bloqués | OUI | Si activé, envoie les utilisateurs bloqués vers une URL spécifiée. |
| Configuration du Module | URL de redirection | L'URL de la page d'accueil de votre boutique | La destination pour les utilisateurs bloqués redirigés. |

### 2.2 Écran d'Administration Dédié : Gestion des Adresses IP (Back Office > Modules > Block IP address Pro > Gérer les Adresses IP)

Ceci est l'écran de gestion principal où vous ajoutez, modifiez, activez et désactivez des adresses IP spécifiques à bloquer.

-   **Emplacement du Menu :** Après l'installation du module, un nouvel élément de menu apparaîtra sous **Modules > Block IP address Pro** (ou similaire, selon la version de PrestaShop et l'enregistrement du menu du module). Cliquez sur "Gérer les Adresses IP" ou "Bloquer les Adresses IP".

#### Actions et Paramètres Disponibles :

1.  **Tableau de Liste des Adresses IP :**
    -   Ce tableau affiche toutes les adresses IP que vous avez configurées pour le blocage.
    -   **Colonnes :**
        -   **ID :** Identifiant unique pour l'entrée IP bloquée.
        -   **Adresse IP :** L'adresse IP réelle bloquée (par exemple, `192.168.1.1`, `203.0.113.45`).
        -   **Nombre de vues :** Une statistique montrant combien de fois cette adresse IP spécifique a tenté d'accéder à votre boutique et a été bloquée. Ceci est inestimable pour identifier les menaces persistantes.
        -   **Commentaire :** Votre note interne expliquant pourquoi cette IP a été bloquée (par exemple, "Bot spammeur", "Scraping concurrent", "Client problématique").
        -   **Actif :** Un interrupteur (Activé/Désactivé) pour activer ou désactiver rapidement le blocage pour cette IP spécifique sans supprimer l'entrée.
        -   **Actions :** Boutons pour "Modifier" ou "Supprimer" les entrées IP individuelles.

2.  **Ajout d'une Nouvelle Adresse IP :**
    -   Cliquez sur le bouton "Ajouter une nouvelle adresse IP" (ou similaire, généralement une icône plus ou un bouton "Ajouter nouveau" en haut à droite du tableau).
    -   **Champs du formulaire :**
        -   **IP :** Entrez l'adresse IP exacte que vous souhaitez bloquer.
        -   **Commentaire :** Ajoutez une note descriptive pour votre référence (par exemple, "Source de spam connue d'après les analyses", "Client 'Jean Dupont' causant des problèmes").
        -   **Actif :** Choisissez "Activé" pour activer immédiatement le blocage, ou "Désactivé" pour enregistrer l'entrée mais la garder inactive pour le moment.
    -   **Enregistrer :** Cliquez sur "Enregistrer" pour ajouter la nouvelle IP à votre liste de blocage.

3.  **Modification d'une Adresse IP Existante :**
    -   Cliquez sur l'icône "Modifier" à côté d'une adresse IP dans le tableau de liste.
    -   Vous pouvez modifier l'adresse "IP", le "Commentaire" et le statut "Actif".
    -   **Enregistrer :** Cliquez sur "Enregistrer" pour appliquer vos modifications.

4.  **Suppression d'une Adresse IP :**
    -   Cliquez sur l'icône "Supprimer" à côté d'une adresse IP.
    -   Confirmez la suppression. Cela supprimera définitivement l'IP de votre liste de blocage.

#### Effet des modifications :
-   **Ajout d'une IP :** Une fois enregistrée et active, tout visiteur tentant d'accéder à votre boutique depuis cette adresse IP sera immédiatement bloqué ou redirigé selon la configuration globale de votre module.
-   **Modification d'une IP :** Les modifications de l'adresse IP, du commentaire ou du statut actif prendront effet immédiatement.
-   **Désactivation d'une IP :** L'adresse IP reste dans votre liste, mais les visiteurs de cette IP ne seront plus bloqués. Ceci est utile pour les blocages temporaires ou si une IP a été bloquée par erreur.
-   **Suppression d'une IP :** L'IP est définitivement supprimée de la liste de blocage, et les visiteurs de cette IP retrouveront un accès complet à votre boutique.

#### Flux de travail recommandé pour la gestion quotidienne de la boutique :
1.  **Surveiller les Analyses :** Vérifiez régulièrement les analyses de votre site web pour détecter des schémas de trafic suspects, des taux de rebond élevés à partir d'IPs spécifiques, ou une activité inhabituelle.
2.  **Identifier les IPs Problématiques :** Si vous trouvez une adresse IP qui cause constamment des problèmes (par exemple, tentatives de connexion échouées répétées, scraping excessif de pages, commentaires de spam), notez-la.
3.  **Ajouter à la Liste de Blocage :** Naviguez vers l'écran "Gérer les Adresses IP", cliquez sur "Ajouter une nouvelle adresse IP", entrez l'IP, ajoutez un commentaire descriptif et activez-la.
4.  **Examiner les Statistiques :** Vérifiez périodiquement la colonne "Nombre de vues" pour les IPs bloquées. Des nombres élevés indiquent des tentatives persistantes, confirmant l'efficacité de votre blocage.
5.  **Gérer et Affiner :** Si une adresse IP n'est plus une menace, vous pouvez soit la désactiver (définir "Actif" sur "Désactivé") soit la supprimer entièrement.

### 2.3 Tableau de Référence Rapide de la Configuration

| Écran / Vue | Paramètre / Option | Valeur par défaut / Recommandée | Objectif et Impact |
|---|---|---|---|
| Gestion des Adresses IP | Ajouter une nouvelle IP | N/A | Ajoute une nouvelle adresse IP à la liste de blocage. |
| Gestion des Adresses IP | Adresse IP (Champ) | N/A | L'IP spécifique à bloquer. |
| Gestion des Adresses IP | Commentaire (Champ) | N/A | Votre note interne pour l'IP bloquée. |
| Gestion des Adresses IP | Actif (Interrupteur) | Activé | Active/désactive le blocage pour une IP spécifique. |
| Gestion des Adresses IP | Nombre de vues (Colonne) | 0 | Compte le nombre de fois qu'une IP a été bloquée. |
| Gestion des Adresses IP | Actions Modifier / Supprimer | N/A | Modifie ou supprime les entrées IP bloquées existantes. |

## 3. Dépannage Marchand et Questions Fréquemment Posées (FAQ)

**Q : J'ai bloqué une IP, mais l'utilisateur peut toujours accéder à ma boutique. Qu'est-ce qui ne va pas ?**
R :
1.  **Vérifiez le statut "Actif" :** Assurez-vous que l'interrupteur "Actif" pour cette IP spécifique dans l'écran "Gérer les Adresses IP" est réglé sur "Activé".
2.  **Videz le Cache :** PrestaShop utilise la mise en cache. Allez dans **Paramètres avancés > Performances** et cliquez sur "Vider le cache" (ou "Vider le cache Smarty" pour les versions plus anciennes). Cela garantit que les paramètres du module sont rechargés.
3.  **Vérifiez l'Adresse IP :** Vérifiez à nouveau que vous avez entré la bonne adresse IP. Parfois, les IPs dynamiques changent, ou vous pourriez avoir un problème de proxy/CDN.
4.  **Cache du Navigateur :** Demandez à l'utilisateur bloqué de vider le cache de son navigateur ou d'essayer d'accéder depuis une fenêtre de navigation privée.

**Q : Mon client légitime est bloqué ! Comment puis-je résoudre ce problème ?**
R :
1.  **Identifiez son IP :** Demandez au client son adresse IP actuelle (il peut la trouver en cherchant "quelle est mon IP" sur Google).
2.  **Vérifiez votre liste de blocage :** Allez dans **Modules > Block IP address Pro > Gérer les Adresses IP** et recherchez son IP.
3.  **Désactivez ou Supprimez :** Si trouvée, soit réglez l'interrupteur "Actif" sur "Désactivé" pour cette entrée, soit supprimez-la entièrement.
4.  **Videz le Cache :** N'oubliez pas de vider votre cache PrestaShop par la suite.

**Q : Puis-je bloquer une plage d'adresses IP au lieu d'une seule ?**
R : La version actuelle du module prend en charge le blocage d'adresses IP individuelles. Pour bloquer des plages, vous devrez entrer chaque IP de la plage individuellement, ou envisager un blocage IP au niveau du serveur si vous avez accès au pare-feu de votre serveur (par exemple, via des règles `.htaccess`).

**Q : Que se passe-t-il si j'active la redirection mais que je ne fournis pas d'URL de redirection ?**
R : Si "Rediriger les utilisateurs bloqués" est activé mais que "URL de redirection" est vide, le comportement du module pourrait être incohérent. Il est préférable de toujours fournir une URL valide si la redirection est active. Si vous ne souhaitez pas rediriger, désactivez l'option "Rediriger les utilisateurs bloqués" et utilisez plutôt le message personnalisé.

**Q : Ce module va-t-il ralentir ma boutique ?**
R : Non, le module est conçu pour être très léger et efficace. Il vérifie l'adresse IP du visiteur très tôt dans le processus de chargement de PrestaShop. Si une IP est bloquée, la requête est terminée ou redirigée rapidement, souvent *avant* même que votre boutique ne commence à charger son contenu complet, ce qui peut en fait *améliorer* les performances en réduisant la charge serveur indésirable.

## 4. Guide du Développeur et du Webmaster (Architecture Technique et Carte du Code)

Cette section fournit une analyse technique approfondie du module "Block IP address Pro" pour les développeurs et les webmasters.

### 4.1 Aperçu de l'Architecture
Le module "Block IP address Pro" suit une architecture de module PrestaShop standard, exploitant principalement la classe `Module` pour l'installation/désinstallation et la configuration, et `AdminController` pour la gestion du back-office. Il utilise une table de base de données personnalisée pour stocker les adresses IP bloquées et se connecte au hook `actionFrontControllerAfterInit` pour effectuer la vérification IP le plus tôt possible dans le cycle de vie de la requête.

### 4.2 Contrôleurs (`controllers/`)

-   **Contrôleurs Front-Office** :
    Le module n'a pas de contrôleurs front-office dédiés. La logique de blocage IP est gérée directement dans le fichier principal du module (`banippro.php`) via un hook, assurant une exécution précoce.

-   **Contrôleurs Admin Back-Office** :
    1.  `banippro/controllers/admin/AdminBanIpProController.php`
        *   **Nom de la Classe et Classe Parent :** `AdminBanIpProController` étend `ModuleAdminController`.
        *   **Responsabilité :** Ce contrôleur est responsable de la gestion de la liste des adresses IP bloquées dans le Back Office de PrestaShop. Il fournit l'interface CRUD (Create, Read, Update, Delete) standard pour l'entité `BanIpPro`. Il gère :
            *   L'affichage de la liste des IPs bloquées avec leurs détails (IP, vues, commentaire, statut actif).
            *   L'ajout de nouvelles adresses IP à la liste de blocage.
            *   La modification des entrées d'adresses IP existantes.
            *   La suppression d'adresses IP de la liste de blocage.
            *   La gestion de l'interrupteur de statut "Actif" pour chaque IP.
            *   Les méthodes `initContent()`, `renderList()`, `renderForm()` sont généralement surchargées ici pour personnaliser l'affichage et les formulaires.
            *   Il est mappé à la table de base de données `ban` (ou similaire, telle que définie par le modèle `BanIpPro` s'il existait).

    2.  `banippro/controllers/admin/index.php`
        *   **Responsabilité :** Il s'agit d'un fichier `index.php` vide standard souvent trouvé dans les sous-répertoires des modules PrestaShop. Son objectif principal est d'empêcher la liste des répertoires sur les serveurs web pour des raisons de sécurité. Il ne contient aucune logique fonctionnelle pour le module.

### 4.3 Classes et Modèles de Base (`classes/`)
La description du module n'indique aucune classe personnalisée dans le répertoire `classes/`. L'entité `BanIpPro` (pour les IPs bloquées) est probablement gérée directement dans le `AdminBanIpProController` et le fichier principal `banippro.php`, potentiellement en utilisant une simple interaction avec la classe `Db` ou une structure de tableau interne si elle n'est pas entièrement conforme à `ObjectModel`. Si un `ObjectModel` était utilisé, il serait généralement nommé `BanIpPro` et résiderait dans `classes/BanIpPro.php`.

Étant donné que le `AdminBanIpProController` gère une entité "ban", cela implique une structure de données sous-jacente. Si ce n'est pas un `ObjectModel` dédié, ce seraient des requêtes directes à la base de données.

### 4.4 Actifs JavaScript (`views/js/`)
La description du module n'indique aucun fichier JavaScript personnalisé. Tous les éléments interactifs du back-office (comme les interrupteurs ou la validation de formulaire) sont probablement gérés par le JS de base de PrestaShop ou des scripts en ligne dans les templates.

### 4.5 Feuilles de Style CSS (`views/css/`)
La description du module n'indique aucun fichier CSS personnalisé. Le style pour la configuration du back-office et les écrans de gestion IP reposera entièrement sur le CSS du thème de back-office par défaut de PrestaShop.

### 4.6 Structure des Templates Smarty (`views/templates/`)
La description du module n'indique aucun fichier de template personnalisé.
-   **Templates de hook** : Le comportement front-office du module (blocage/redirection) est géré de manière programmatique dans le hook, et non via un template.
-   **Templates d'administration** : Le formulaire de configuration pour `getContent()` et les vues de liste/formulaire pour `AdminBanIpProController` sont probablement rendus à l'aide des classes d'aide par défaut de PrestaShop (`HelperForm`, `HelperList`) qui génèrent directement du HTML, ou s'appuient sur des templates en ligne très minimalistes, le cas échéant.

### 4.7 Schéma de Base de Données et Carte des Hooks

-   **Tables de Base de Données** :
    Le module crée au moins une table personnalisée lors de l'installation pour stocker les adresses IP bloquées.
    -   `ps_banippro` (ou similaire, par exemple, `ps_ban_ip_pro`) :
        *   `id_banippro` (Clé Primaire, INT)
        *   `ip_address` (VARCHAR, stocke l'adresse IP à bloquer)
        *   `comment` (TEXT, pour les notes d'administration)
        *   `views` (INT, compteur du nombre de fois que cette IP a été bloquée)
        *   `active` (TINYINT(1), 0 ou 1, pour activer/désactiver le blocage)

    Les paramètres de configuration (`mypresta_updates`, `banippro_msg`, `banippro_redirect`, `banippro_url`) sont stockés dans la table `ps_configuration`.

-   **Table des Hooks Enregistrés** :

| Nom du Hook | Moment d'Exécution | Objectif Technique |
|---|---|---|
| `actionFrontControllerAfterInit` | Exécuté après l'initialisation du contrôleur frontal mais avant le rendu de tout contenu. | **CRITIQUE :** C'est ici que le module exécute sa fonction principale : vérifier l'IP du visiteur par rapport à la liste bloquée. Si une correspondance est trouvée, il affiche le message personnalisé ou effectue une redirection, arrêtant ainsi efficacement l'exécution ultérieure de la page. |
| `displayHome` | Rend le contenu sur la page d'accueil. | Probablement utilisé pour les notifications de mise à jour ou d'autres contenus spécifiques au module si le module avait un composant front-office. Dans le contexte de ce module, il pourrait s'agir d'un hook hérité ou utilisé pour une logique très spécifique et non bloquante. |
| `home` | Alias pour `displayHome` dans certains contextes. | Identique à `displayHome`. |
| `header` | Rend le contenu dans la section `<head>` du HTML. | Utilisé pour ajouter du CSS, du JavaScript ou des balises meta. Dans ce module, il pourrait être utilisé pour les notifications de mise à jour ou pour assurer un chargement précoce des scripts/styles si nécessaire. |
| `actionAdminControllerSetMedia` | Exécuté lorsqu'un contrôleur d'administration définit ses médias (CSS/JS). | Utilisé par le module pour ajouter des fichiers CSS ou JavaScript spécifiques requis pour ses pages de configuration back-office (par exemple, pour `AdminBanIpProController`). |
| `ActionAdminControllerSetMedia` | (Duplicata du précédent, différence de casse) | Identique à `actionAdminControllerSetMedia`. Les hooks PrestaShop sont généralement insensibles à la casse, mais les modules enregistrent parfois les deux pour la compatibilité. |
| `displayHeader` | Rend le contenu dans la section `<header>` du HTML (souvent dans le `<body>` avant le contenu principal). | Similaire à `header`, mais généralement pour les éléments visibles. Dans ce module, il est moins susceptible d'avoir un impact direct sur le front-office étant donné sa nature bloquante. |

## 5. Support Officiel et Mises à Jour
Pour les dernières mises à jour du module, les corrections de bugs et le support professionnel, veuillez vous référer à votre compte client sur MyPresta.eu. Notre équipe est dédiée à fournir une assistance rapide et à assurer le bon fonctionnement de votre module.
-   **Historique des commandes et téléchargements MyPresta.eu :** [https://mypresta.eu/my-account/orders/](https://mypresta.eu/my-account/orders/)
-   **Contact Support MyPresta.eu :** [https://mypresta.eu/contact](https://mypresta.eu/contact)
