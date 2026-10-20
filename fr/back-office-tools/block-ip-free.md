---
title: "Block IP free - Manuel du Marchand & Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop Block IP free par MyPresta.eu."
sidebar:
  label: "Block IP free - Manuel du Marchand & Guide de Configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Block IP free sur MyPresta.eu](https://mypresta.eu/modules/administration-tools/block-ip-free.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/back-office-tools/block-ip-free/)
>
> ---


# Block IP free

## 1. Exigences et Compatibilité

- **Versions de PrestaShop prises en charge :** PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilité PHP :** PHP 5.6 - 8.5
- **Exigences d'hébergement :** Les extensions PHP standard (cURL, JSON, OpenSSL) sont généralement suffisantes. Aucune exigence particulière au-delà d'un environnement d'hébergement PrestaShop standard.

## 2. Guide de configuration complet (Chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer > Block IP free)

Ceci est l'écran de configuration principal et unique du module « Block IP free ». Vous y trouverez tous les paramètres pour gérer vos adresses IP bloquées et le message qui leur est affiché.

**Nom de l'écran et emplacement du menu :**

-   **Chemin du menu :** Back Office > Modules > Gestionnaire de modules > Block IP free > Configurer

#### Paramètres et options :

1.  **Adresse IP (Champ de saisie)**

    -   **Ce que fait ce paramètre :** C'est ici que vous entrez l'adresse IP que vous souhaitez bloquer pour l'accès à votre boutique.
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsqu'une IP est ajoutée à la liste :* Tout visiteur tentant d'accéder à votre boutique depuis cette adresse IP spécifique se verra refuser l'accès et affichera le « Message d'accès bloqué ».
        -   *Lorsqu'une IP est supprimée de la liste :* Les visiteurs de cette adresse IP retrouveront un accès complet à votre boutique.
    -   **Valeur recommandée :** Entrez l'adresse IP exacte que vous souhaitez bloquer. Vous pouvez ajouter plusieurs IP, une à la fois, en entrant chacune et en cliquant sur « Ajouter ».
    -   **Scénario / exemple pour le marchand :** Si vous remarquez qu'une adresse IP spécifique (par exemple, `192.168.1.100`) tente à plusieurs reprises des commandes frauduleuses ou extrait vos données produit, vous entreriez `192.168.1.100` ici et cliqueriez sur « Ajouter » pour la bloquer.
2.  **Message d'accès bloqué (Zone de texte)**

    -   **Ce que fait ce paramètre :** Cela vous permet de personnaliser le message que les visiteurs bloqués verront lorsqu'ils tenteront d'accéder à votre boutique.
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsqu'un message personnalisé est saisi :* Les visiteurs bloqués verront votre message personnalisé au lieu d'un message par défaut. Cela vous permet d'être poli, informatif ou ferme.
        -   *Lorsqu'il est laissé par défaut :* Un message standard « Accès refusé » sera affiché.
    -   **Valeur recommandée :** Un message clair et concis. Quelque chose comme : « L'accès à cette boutique a été bloqué depuis votre adresse IP. Si vous pensez qu'il s'agit d'une erreur, veuillez contacter le support. »
    -   **Scénario / exemple pour le marchand :** Vous pourriez vouloir afficher un message comme « En raison d'une activité suspecte, l'accès depuis votre adresse IP a été temporairement restreint. Veuillez contacter notre équipe de support si vous pensez qu'il s'agit d'une erreur. » Cela offre une meilleure expérience utilisateur qu'une erreur générique.

#### Gestion de la liste d'IP bloquées :

Sous le champ de saisie « Adresse IP », vous verrez une liste de toutes les adresses IP actuellement bloquées.

-   **Pour ajouter une IP :** Tapez l'adresse IP dans le champ « Adresse IP » et cliquez sur le bouton « Ajouter ».
-   **Pour supprimer une IP :** À côté de chaque adresse IP listée, il y aura un bouton « Supprimer » (souvent représenté par une icône de poubelle). Cliquez sur ce bouton pour débloquer cette IP spécifique.

### 2.2 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Par défaut / Recommandé | Objectif et impact |
| --- | --- | --- | --- |
| Page de configuration du module | Adresse IP | Vide (ajouter des IP si nécessaire) | Ajoute/supprime des adresses IP spécifiques de la liste de blocage. Les IP bloquées ne peuvent pas accéder à la boutique. |
| Page de configuration du module | Message d'accès bloqué | « Accès refusé » (ou similaire) | Personnalise le message affiché aux visiteurs provenant d'adresses IP bloquées. |

## 3. Dépannage pour les marchands et questions fréquemment posées (FAQ)

**Q : J'ai bloqué une IP, mais l'utilisateur peut toujours accéder à ma boutique. Pourquoi ?**
R :

1.  **Mise en cache :** Votre boutique PrestaShop ou votre serveur peut avoir la mise en cache activée. Videz le cache de votre PrestaShop (**Paramètres avancés > Performances > Vider le cache**) et tout cache côté serveur (comme Varnish, LiteSpeed cache, Cloudflare) si applicable.
2.  **IP dynamique :** L'utilisateur peut avoir une adresse IP dynamique qui a changé depuis que vous avez bloqué la précédente.
3.  **Proxy/VPN :** L'utilisateur peut utiliser un VPN ou un serveur proxy, ce qui masque sa véritable adresse IP. Vous devrez bloquer l'IP du serveur VPN/proxy si vous pouvez l'identifier.
4.  **IP incorrecte :** Vérifiez que vous avez entré la bonne adresse IP.

**Q : J'ai accidentellement bloqué ma propre adresse IP et maintenant je ne peux plus accéder à mon Back Office ! Que dois-je faire ?**
R : C'est une situation critique mais réparable. Vous devez accéder directement à votre serveur :

1.  **Via FTP/SFTP :** Connectez-vous au serveur de votre boutique à l'aide d'un client FTP (comme FileZilla).
2.  **Naviguez vers le dossier des modules :** Allez dans `votre_racine_prestashop/modules/`.
3.  **Renommez le dossier du module :** Trouvez le dossier `banipfree` et renommez-le en quelque chose comme `banipfree_DISABLED`. Cela désactivera efficacement le module.
4.  **Accédez au Back Office :** Vous devriez maintenant pouvoir vous connecter à votre Back Office PrestaShop.
5.  **Réactivez et configurez :** Renommez le dossier en `banipfree`, puis allez dans **Modules > Gestionnaire de modules**, trouvez « Block IP free », et cliquez sur « Configurer » pour supprimer votre IP de la liste bloquée.

**Q : Puis-je bloquer une plage d'adresses IP au lieu d'une seule ?**
R : La version actuelle du module « Block IP free » permet de bloquer des adresses IP individuelles. Pour bloquer des plages entières (par exemple, `192.168.1.0/24`), vous auriez généralement besoin d'une configuration au niveau du serveur (par exemple, des règles `.htaccess` ou des paramètres de pare-feu) ou d'un module de sécurité plus avancé.

**Q : Ce module va-t-il ralentir ma boutique ?**
R : Non, le module est très léger. Il vérifie l'adresse IP du visiteur très tôt dans le processus de chargement de PrestaShop. Si l'IP est bloquée, le contenu de la boutique n'est pas chargé du tout, ce qui peut en fait économiser des ressources serveur en empêchant le trafic indésirable de traiter entièrement les requêtes.

**Q : Comment trouver l'adresse IP d'un visiteur problématique ?**
R : Vous pouvez trouver les adresses IP à plusieurs endroits :

-   **Journaux d'accès au serveur :** Le panneau de contrôle de votre hébergement web (cPanel, Plesk) fournit généralement un accès aux journaux d'accès bruts, qui listent l'adresse IP de chaque visiteur.
-   **Détails de la commande PrestaShop :** Pour les commandes, l'adresse IP du client est généralement enregistrée sur la page des détails de la commande dans le Back Office.
-   **Outils d'analyse :** Certains outils d'analyse avancés peuvent afficher les adresses IP des visiteurs, bien que souvent anonymisées.
-   **Modules de sécurité tiers :** D'autres modules de sécurité peuvent enregistrer les activités suspectes avec les adresses IP.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

Cette section fournit un aperçu technique détaillé pour les développeurs et les webmasters travaillant avec le module « Block IP free ».

### 4.1 Vue d'ensemble de l'architecture

Le module « Block IP free » est un module PrestaShop simple, à fichier unique (`banipfree.php`), qui exploite principalement le hook `actionDispatcher`. Ce hook est exécuté très tôt dans le cycle de vie de la requête PrestaShop, permettant au module de vérifier l'adresse IP du visiteur avant que tout traitement ou rendu significatif du contenu de la boutique ne se produise. Si l'IP est trouvée dans la liste bloquée, le module termine immédiatement la requête et affiche un message personnalisé, agissant efficacement comme un pare-feu précoce. La configuration est gérée via la méthode standard `getContent()`, stockant les paramètres dans `ps_configuration`.

### 4.2 Contrôleurs (`controllers/`)

-   Ce module ne contient **pas** de contrôleurs Front-Office ou Back-Office personnalisés. Toute la logique est encapsulée dans le fichier principal du module.

### 4.3 Classes et modèles principaux (`classes/`)

-   Ce module ne contient **pas** de classes personnalisées ou de définitions `ObjectModel` dans le répertoire `classes/`. Toute la gestion des données est directe via `Configuration::get()` et `Configuration::updateValue()`.

### 4.4 Actifs JavaScript (`views/js/`)

-   Ce module ne contient **pas** de fichiers JavaScript personnalisés.

### 4.5 Feuilles de style CSS (`views/css/`)

-   Ce module ne contient **pas** de fichiers CSS personnalisés. Le message d'accès bloqué est affiché avec un style minimal, en ligne ou le style par défaut du navigateur.

### 4.6 Structure des modèles Smarty (`views/templates/`)

-   Ce module ne contient **pas** de fichiers de modèle Smarty personnalisés. Le message d'accès bloqué est directement affiché sous forme de HTML/texte brut dans la méthode `hookActionDispatcher`.

### 4.7 Schéma de la base de données et carte des hooks

#### Tables de la base de données

Le module ne crée aucune table de base de données personnalisée. Il stocke ses paramètres de configuration dans la table standard `ps_configuration` :

-   `BANIPFREE_LIST` : Stocke une chaîne d'adresses IP bloquées séparées par des virgules.
-   `BANIPFREE_MSG` : Stocke le message personnalisé affiché aux utilisateurs bloqués.
-   `mypresta_updates`, `update_`, `updatev_` : Clés internes utilisées par MyPresta.eu pour les vérifications de mise à jour du module.

#### Tableau des hooks enregistrés

| Nom du hook | Moment d'exécution | Objectif technique |
| --- | --- | --- |
| `actionDispatcher` | Exécuté très tôt dans le cycle de vie de la requête PrestaShop, avant la répartition du contrôleur. | C'est le hook principal utilisé par le module. Il récupère l'adresse IP du visiteur, la vérifie par rapport à la `BANIPFREE_LIST`, et si une correspondance est trouvée, il affiche le `BANIPFREE_MSG` et termine l'exécution du script (`die()`), empêchant le chargement ultérieur de la boutique. |

### 4.8 Fichier principal du module (`banipfree/banipfree.php`)

C'est le cœur du module.

-   **`__construct()`** : Initialise les métadonnées du module (nom, onglet, version, auteur, etc.).
-   **`install()`** :
    -   Appelle `parent::install()`.
    -   Enregistre le hook `actionDispatcher`.
    -   Définit les valeurs de configuration initiales pour `BANIPFREE_LIST` (vide) et `BANIPFREE_MSG` (message par défaut).
-   **`uninstall()`** :
    -   Appelle `parent::uninstall()`.
    -   Désenregistre le hook `actionDispatcher`.
    -   Supprime les valeurs de configuration (`BANIPFREE_LIST`, `BANIPFREE_MSG`).
-   **`getContent()`** :
    -   Gère la soumission du formulaire pour enregistrer les adresses IP et le message personnalisé.
    -   Récupère et affiche la liste actuelle des IP bloquées.
    -   Rend le formulaire de configuration à l'aide des éléments `HelperForm` standard de PrestaShop (champ de texte pour l'IP, zone de texte pour le message, liste des IP bloquées avec boutons de suppression).
-   **`hookActionDispatcher()`** :
    -   C'est la méthode critique pour le blocage.
    -   Elle récupère l'adresse IP du visiteur (`$_SERVER['REMOTE_ADDR']`).
    -   Elle récupère la `BANIPFREE_LIST` de `Configuration`.
    -   Elle vérifie si l'IP actuelle est présente dans la liste séparée par des virgules.
    -   Si l'IP est bloquée, elle récupère `BANIPFREE_MSG`, affiche une simple page HTML avec le message, et appelle `die()` pour arrêter toute exécution ultérieure.

## 5. Support officiel et mises à jour

Pour les dernières mises à jour, corrections de bugs et support officiel du module « Block IP free », veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu/my-account/orders/). Notre équipe de support est disponible pour vous aider avec tout problème ou question que vous pourriez avoir concernant la fonctionnalité du module.
