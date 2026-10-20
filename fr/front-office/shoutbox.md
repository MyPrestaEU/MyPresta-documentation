---
title: "Shoutbox - Manuel du Marchand et Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop Shoutbox par MyPresta.eu."
sidebar:
  label: "Shoutbox - Manuel du Marchand et Guide de Configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Shoutbox sur MyPresta.eu](https://mypresta.eu/modules/front-office-features/shoutbox.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/front-office/shoutbox/)
>
> ---


# Shoutbox

## 1. Exigences et compatibilité

- **Versions PrestaShop prises en charge** : PrestaShop 9.x, 8.x, 1.7.x, 1.6.x, 1.5.x
- **Compatibilité PHP** : PHP 5.6 - 8.5
- **Exigences d'hébergement** : Extensions PHP standard (cURL, JSON, OpenSSL).

## 2. Parcours de configuration complet (Chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

Ceci est l'écran de configuration principal du module Shoutbox, accessible directement après l'installation ou en naviguant vers **Modules > Gestionnaire de modules**, en recherchant "Shoutbox" et en cliquant sur "Configurer".

| Paramètre / Option | Ce que fait ce paramètre | Effet de la modification de ce paramètre | Valeur recommandée | Scénario / exemple pour le marchand |
| --- | --- | --- | --- | --- |
| **Activer la Shoutbox** | C'est l'interrupteur principal pour activer ou désactiver toute la fonctionnalité Shoutbox dans votre boutique. | *Lorsqu'activé :* La Shoutbox apparaîtra sur votre front office aux emplacements de hook choisis. Les clients peuvent la voir et interagir avec elle. *Lorsqu'désactivé :* La Shoutbox sera complètement cachée de votre boutique, et aucun message ne sera affiché ou accepté. | **OUI** | Vous souhaitez activer la fonction de chat communautaire sur votre boutique. Si vous devez la masquer temporairement pour la maintenance ou la révision de contenu, vous la désactiveriez. |
| **Titre de la Shoutbox** | Ceci définit le texte d'en-tête qui apparaît en haut du widget Shoutbox dans le front office de votre boutique. | *Lorsque défini sur "Chat Communautaire" :* Vos clients verront "Chat Communautaire" comme titre de la boîte. *Lorsque défini sur "Posez-nous vos questions" :* Le titre change en "Posez-nous vos questions". | **Chat Communautaire** | Vous souhaitez étiqueter clairement la boîte de discussion pour vos clients. Vous pourriez la changer en "Discussions sur les produits" si vous la placez sur les pages de produits. |
| **Nombre de messages à afficher** | Ceci contrôle le nombre de messages les plus récents affichés dans la Shoutbox à un moment donné. Les messages plus anciens seront masqués. | *Lorsque défini sur 10 :* Seuls les 10 derniers messages seront visibles dans la boîte de discussion. *Lorsque défini sur 20 :* Les 20 derniers messages seront affichés. | **10** | Pour garder le chat concis et éviter qu'il ne devienne trop long, afficher les 10-15 messages les plus récents est généralement préférable. Si vous avez une communauté très active, vous pourriez augmenter ce nombre. |
| **Intervalle de rafraîchissement (secondes)** | Ceci détermine la fréquence à laquelle la Shoutbox vérifie et charge automatiquement les nouveaux messages sans que le client n'ait à rafraîchir la page. | *Lorsque défini sur 5 :* Les nouveaux messages apparaîtront toutes les 5 secondes. *Lorsque défini sur 15 :* Les nouveaux messages apparaîtront toutes les 15 secondes. | **10** | Un intervalle plus court (par exemple, 5 secondes) rend le chat plus en temps réel mais utilise plus de ressources serveur. Un intervalle plus long (par exemple, 15-20 secondes) réduit la charge du serveur mais les messages apparaissent moins instantanément. 10 secondes est un bon équilibre. |
| **Autoriser les invités à publier** | Cette option contrôle si les visiteurs qui ne sont pas connectés à un compte client peuvent publier des messages dans la Shoutbox. | *Lorsqu'activé :* Toute personne visitant votre boutique peut publier des messages, même si elle ne s'est pas inscrite ou connectée. Elle publiera généralement en tant qu'"Invité". *Lorsqu'désactivé :* Seuls les clients enregistrés et connectés peuvent publier des messages. Les invités verront le chat mais ne pourront pas y contribuer. | **NON** | Si vous souhaitez encourager l'inscription et prévenir le spam anonyme, désactivez cette option. Si vous souhaitez une interaction maximale et que les publications anonymes ne vous dérangent pas, activez-la. |
| **Afficher la Shoutbox dans** | Ce paramètre crucial détermine où le widget Shoutbox apparaîtra sur le front office de votre boutique. Vous pouvez sélectionner un ou plusieurs emplacements. | *Lorsque "Colonne de gauche" est sélectionné :* La Shoutbox apparaîtra dans la barre latérale gauche de votre boutique. *Lorsque "Pied de page" est sélectionné :* La Shoutbox apparaîtra en bas des pages de votre boutique. | **Colonne de gauche** (ou un emplacement qui correspond à votre thème) | Vous souhaitez que la Shoutbox soit facilement visible mais n'interfère pas avec le contenu principal de vos produits. La placer dans une colonne ou le pied de page est souvent un bon choix. |
| **Modération requise** | Si activé, les nouveaux messages n'apparaîtront pas dans la Shoutbox tant qu'un administrateur ne les aura pas approuvés manuellement dans le Back Office. | *Lorsqu'activé :* Tous les nouveaux messages sont mis en file d'attente. Vous devez approuver chaque message avant qu'il ne devienne visible pour les autres clients. *Lorsqu'désactivé :* Les messages apparaissent instantanément après avoir été publiés. | **NON** (sauf si vous anticipez du spam) | Si vous êtes préoccupé par le spam, le contenu inapproprié ou si vous souhaitez maintenir un contrôle strict sur la conversation, activez la modération. Pour un chat plus fluide et en temps réel, désactivez-la. |
| **Effacer tous les messages** | C'est un bouton (pas un interrupteur) qui, lorsqu'il est cliqué, supprimera définitivement tous les messages existants de la Shoutbox. | *Lorsque cliqué :* Tous les messages historiques de la Shoutbox sont supprimés de votre base de données et ne seront plus affichés. Cette action est irréversible. | **N/A** (À utiliser avec prudence) | Vous pourriez l'utiliser si le chat a accumulé trop d'anciens messages, ou si vous souhaitez démarrer une nouvelle conversation pour une nouvelle promotion ou un événement. |

### 2.2 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Par défaut / Recommandé | Objectif et impact |
| --- | --- | --- | --- |
| Configuration du module | Activer la Shoutbox | OUI | Active/désactive toute la fonctionnalité Shoutbox. |
| Configuration du module | Titre de la Shoutbox | Chat Communautaire | Définit le titre visible du widget Shoutbox. |
| Configuration du module | Nombre de messages à afficher | 10 | Contrôle le nombre de messages récents affichés. |
| Configuration du module | Intervalle de rafraîchissement (secondes) | 10 | Fréquence de mise à jour du chat avec de nouveaux messages. |
| Configuration du module | Autoriser les invités à publier | NON | Détermine si les utilisateurs non connectés peuvent publier des messages. |
| Configuration du module | Afficher la Shoutbox dans | Colonne de gauche | Sélectionne le(s) emplacement(s) front-office pour la Shoutbox. |
| Configuration du module | Modération requise | NON | Nécessite l'approbation de l'administrateur pour les messages avant qu'ils n'apparaissent. |
| Configuration du module | Effacer tous les messages | N/A | Supprime définitivement tous les messages de la Shoutbox. |

## 3. Dépannage pour les marchands et questions fréquemment posées (FAQ)

**Q1 : La Shoutbox n'apparaît pas sur ma boutique, même si je l'ai activée.**
**R1 :**

-   **Vérifier la sélection du hook :** Allez dans la configuration du module et assurez-vous d'avoir sélectionné au moins un emplacement "Afficher la Shoutbox dans" (par exemple, Colonne de gauche, Pied de page).
-   **Vider le cache :** Le cache de PrestaShop peut parfois empêcher l'apparition de nouveaux modules. Allez dans **Paramètres avancés > Performances** et cliquez sur "Vider le cache" (ou "Vider le cache Smarty" dans les versions antérieures).
-   **Compatibilité du thème :** Certains thèmes très personnalisés peuvent ne pas rendre correctement les hooks de module standard. Si vider le cache ne fonctionne pas, essayez de passer temporairement au thème PrestaShop par défaut pour voir si la Shoutbox apparaît. Si c'est le cas, votre thème a probablement besoin d'un petit ajustement (contactez le développeur de votre thème ou un webmaster).

**Q2 : Les nouveaux messages n'apparaissent pas en temps réel ; je dois rafraîchir la page.**
**R2 :**

-   **Vérifier l'intervalle de rafraîchissement :** Dans la configuration du module, assurez-vous que "Intervalle de rafraîchissement (secondes)" est défini sur un nombre raisonnable (par exemple, 5-15 secondes) et non sur 0 ou un nombre très élevé.
-   **Conflits JavaScript :** Un autre module ou le JavaScript de votre thème pourrait provoquer un conflit. Vérifiez la console de développement de votre navigateur (touche F12, puis regardez l'onglet "Console") pour toute erreur JavaScript. Si des erreurs apparaissent, essayez de désactiver d'autres modules récemment installés un par un pour identifier le coupable.

**Q3 : Je reçois beaucoup de messages de spam dans la Shoutbox.**
**R3 :**

-   **Activer la modération :** Allez dans la configuration du module et définissez "Modération requise" sur OUI. Cela mettra tous les nouveaux messages en attente, vous permettant de les approuver avant qu'ils ne soient publiés.
-   **Désactiver la publication par les invités :** Si le spam provient d'utilisateurs anonymes, définissez "Autoriser les invités à publier" sur NON. Cela exigera que les utilisateurs soient connectés à un compte client pour publier, ce qui réduit souvent le spam.

**Q4 : Comment traduire le titre de la Shoutbox ou d'autres textes dans différentes langues ?**
**R4 :**

-   Naviguez vers **International > Traductions** dans votre Back Office PrestaShop.
-   Sélectionnez "Traductions des modules installés", choisissez votre thème, puis sélectionnez votre langue.
-   Recherchez le module "Shoutbox" dans la liste et vous pourrez modifier les chaînes traduisibles, y compris le titre de la Shoutbox.

**Q5 : La Shoutbox a l'air un peu bizarre ou ne correspond pas au style de mon thème.**
**R5 :**

-   Le module utilise un style de base. Pour une apparence personnalisée, vous aurez besoin d'un webmaster ou d'un développeur pour ajouter des règles CSS personnalisées à la feuille de style de votre thème. Ils pourront cibler les éléments de la Shoutbox et ajuster les couleurs, les polices, les bordures, etc., pour qu'ils correspondent parfaitement à votre marque.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

Cette section fournit une analyse approfondie de la structure technique du module Shoutbox, destinée aux développeurs, webmasters et agences techniques.

### 4.1 Aperçu de l'architecture

Le module Shoutbox suit une structure de module PrestaShop classique, exploitant les contrôleurs frontaux pour les interactions AJAX et le fichier de module principal (`index.php`) pour la configuration et l'enregistrement des hooks. C'est un module léger, principalement axé sur l'affichage et la soumission de messages via AJAX sans modèles d'objets complexes ni tables de base de données dédiées au-delà de `ps_configuration` pour les paramètres. La fonctionnalité principale repose sur l'interaction directe avec la base de données pour le stockage et la récupération des messages.

### 4.2 Contrôleurs (`controllers/`)

Le module utilise des contrôleurs frontaux pour gérer les requêtes AJAX de chargement et d'insertion de messages, garantissant une expérience utilisateur dynamique sans rechargement complet de la page.

-   **Contrôleurs Front-Office** :

    -   `controllers/front/ajaxload.php`
        -   **Nom de la classe** : `ShoutboxAjaxloadModuleFrontController` (étend `ModuleFrontController`)
        -   **Responsabilité** : Ce contrôleur gère la requête AJAX pour le chargement des messages existants. Il récupère généralement un nombre spécifié des messages les plus récents de la base de données et les renvoie, probablement sous forme de JSON ou de HTML brut, pour être affichés dans le widget Shoutbox. C'est le point d'accès pour le mécanisme de rafraîchissement automatique.
    -   `controllers/front/index.php`
        -   **Nom de la classe** : `ShoutboxIndexModuleFrontController` (étend `ModuleFrontController`)
        -   **Responsabilité** : Ce contrôleur pourrait servir de solution de repli ou de point d'accès direct à la Shoutbox si elle devait avoir une page dédiée. Compte tenu de la nature du module, il s'agit plus probablement d'un espace réservé ou il gère la logique de rendu initiale si la Shoutbox est intégrée directement plutôt que via un hook. Dans la plupart des cas, la Shoutbox est rendue via `shoutbox.tpl` dans un hook.
    -   `controllers/front/insert.php`
        -   **Nom de la classe** : `ShoutboxInsertModuleFrontController` (étend `ModuleFrontController`)
        -   **Responsabilité** : Ce contrôleur gère la requête AJAX pour la soumission de nouveaux messages. Il reçoit le contenu du message (et potentiellement l'ID/nom de l'utilisateur) du front-end, effectue toute validation nécessaire (par exemple, publication par les invités, modération), stocke le message dans la base de données et renvoie une réponse de succès/échec.
-   **Contrôleurs d'administration Back-Office** :

    -   Aucun. Toute la configuration est gérée dans la méthode `getContent()` du fichier de module principal.

### 4.3 Classes et modèles principaux (`classes/`)

Le module ne définit aucune classe personnalisée ou `ObjectModel` dans le répertoire `classes/`. Le stockage et la récupération des messages sont gérés directement dans les fichiers PHP du module, probablement en utilisant `Db::getInstance()` pour les requêtes SQL. Cela implique que les messages sont stockés dans une table personnalisée créée lors de l'installation ou directement dans `ps_configuration` si les messages sont très peu nombreux et simples (bien qu'une table dédiée soit plus probable pour les messages de chat).

### 4.4 Actifs JavaScript (`views/js/`)

Le module s'appuie sur JavaScript pour sa fonctionnalité AJAX et ses mises à jour dynamiques.

-   `js/advajax.js`
    -   **Portée** : Front-office.
    -   **Détails** : Ce fichier contient probablement un utilitaire AJAX générique ou des fonctions d'encapsulation utilisées par le module. Il pourrait fournir une compatibilité inter-navigateurs pour les requêtes AJAX ou simplifier le processus d'envoi et de réception de données depuis les contrôleurs frontaux. Il pourrait s'agir d'une implémentation personnalisée ou d'une bibliothèque légère.
-   `js/script.js`
    -   **Portée** : Front-office.
    -   **Détails** : C'est le fichier JavaScript principal pour la logique front-end de la Shoutbox.
        -   **Écouteurs d'événements** : Se lie aux événements de soumission de formulaire pour la publication de nouveaux messages, et potentiellement aux événements de clic pour des actions comme l'effacement des messages (si exposé au front-end).
        -   **Appels AJAX** : Lance des requêtes AJAX vers `ajaxload.php` pour rafraîchir les messages à l'intervalle spécifié et vers `insert.php` pour soumettre de nouveaux messages.
        -   **Manipulation du DOM** : Met à jour l'affichage de la Shoutbox avec de nouveaux messages, fait défiler vers le bas du chat et gère l'effacement du champ de saisie.
        -   **Minuteurs** : Configure `setInterval` pour le chargement périodique des messages basé sur le paramètre "Intervalle de rafraîchissement".

### 4.5 Feuilles de style CSS (`views/css/`)

Le module ne liste pas explicitement de fichiers CSS personnalisés dans le répertoire `views/css/`. Cela suggère que :

1.  Le module s'appuie sur des styles en ligne ou des styles de navigateur par défaut de base.
2.  Il pourrait être conçu pour hériter directement du style du thème PrestaShop actif, nécessitant un minimum de CSS personnalisé.
3.  Tout style est intégré directement dans le fichier `shoutbox.tpl` ou le fichier PHP du module principal.
    Les développeurs souhaitant styliser la Shoutbox devront inspecter le HTML généré et ajouter des règles CSS personnalisées à la feuille de style de leur thème, en ciblant les ID et classes spécifiques utilisés par les éléments de la Shoutbox.

### 4.6 Structure du template Smarty (`views/templates/`)

-   **Templates de hook (`views/templates/hook/`)** :
    -   `shoutbox/shoutbox.tpl`
        -   **Hook(s) rendus** : `displayHeader`, `displayLeftColumn`, `displayRightColumn`, `displayFooter`, `displayProductButtons` (ou un hook de page produit similaire). Le hook réel dépend de la configuration du marchand dans le Back Office.
        -   **Sortie du bloc visuel** : Ce template rend la structure HTML complète du widget Shoutbox. Cela inclut :
            -   Le conteneur principal de la boîte de discussion.
            -   Le titre (par exemple, "Chat Communautaire").
            -   La zone où les messages sont affichés (une div défilante).
            -   Le champ de saisie pour taper de nouveaux messages.
            -   Le bouton "Envoyer".
            -   Le rendu conditionnel pour les capacités de publication par les invités.
            -   Il inclura également le JavaScript nécessaire et potentiellement du CSS en ligne.

### 4.7 Schéma de la base de données et carte des hooks

-   **Tables de base de données** :

    -   Le module ne déclare pas explicitement d' `ObjectModel` personnalisé ni de fichier SQL. Le stockage des messages est probablement géré directement via `Db::getInstance()` dans le fichier de module principal ou les contrôleurs frontaux. Un modèle courant pour de tels modules est de créer une table comme `ps_shoutbox_messages` avec des champs tels que `id_shoutbox_message`, `id_customer`, `customer_name`, `message_content`, `date_add`, `ip_address`, `approved`.
    -   **Enregistrements de configuration** : Les paramètres du module (par exemple, `SHOUTBOX_ENABLED`, `SHOUTBOX_TITLE`, `SHOUTBOX_NUM_MESSAGES`, `SHOUTBOX_REFRESH_INTERVAL`, `SHOUTBOX_ALLOW_GUEST`, `SHOUTBOX_MODERATION`, `SHOUTBOX_HOOK`) sont stockés dans la table `ps_configuration`.
-   **Table des hooks enregistrés** :

| Nom du hook | Moment d'exécution | But technique |
| --- | --- | --- |
| `displayHeader` | Rend le contenu dans la section `<head>` du HTML ou tout en haut du `<body>`. | Utilisé pour injecter des fichiers CSS, JavaScript, ou le widget Shoutbox lui-même s'il est configuré pour l'affichage dans l'en-tête. |
| `displayLeftColumn` | Rend le contenu dans la barre latérale gauche de la boutique. | Hook courant pour afficher le widget Shoutbox comme élément de la barre latérale. |
| `displayRightColumn` | Rend le contenu dans la barre latérale droite de la boutique. | Hook courant pour afficher le widget Shoutbox comme élément de la barre latérale. |
| `displayFooter` | Rend le contenu dans la section du pied de page de la boutique. | Utilisé pour afficher le widget Shoutbox en bas de la page. |
| `displayProductButtons` (ou un hook de page produit similaire) | Rend le contenu sur la page produit, souvent près du bouton "ajouter au panier" ou de la description du produit. | Utilisé pour afficher la Shoutbox spécifiquement sur les pages produits pour les discussions liées aux produits. |
| `actionFrontControllerSetMedia` | Exécuté lorsqu'un contrôleur frontal définit ses médias (CSS/JS). | Utilisé pour enregistrer les fichiers JavaScript spécifiques au module (`advajax.js`, `script.js`) et tout fichier CSS potentiel à charger sur le front office. |

## 5. Support officiel et mises à jour

Pour les dernières mises à jour, corrections de bugs et support professionnel pour le module Shoutbox, veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu). Notre équipe de support dédiée est prête à vous aider pour toute question ou problème que vous pourriez rencontrer.
