---
title: "Envoyer une copie des e-mails (CCI) - Manuel du Marchand et Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop 'Envoyer une copie des e-mails (CCI)' par MyPresta.eu."
sidebar:
  label: "Envoyer une copie des e-mails (CCI)"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Send a copy of emails (BCC) sur MyPresta.eu](https://mypresta.eu/modules/administration-tools/send-a-copy-of-emails-bcc.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/back-office-tools/send-a-copy-of-emails-bcc/)
>
> ---


# Envoyer une copie des e-mails (CCI)

## 1. Exigences et compatibilité
- **Versions PrestaShop prises en charge** : PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilité PHP** : PHP 5.6 - 8.5
- **Exigences d'hébergement** : Les extensions PHP standard (cURL, JSON, OpenSSL) sont généralement suffisantes. Aucune configuration spéciale de serveur n'est généralement nécessaire.

## 2. Guide de configuration complet (chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)
Après l'installation, cliquer sur "Configurer" vous mènera à la page de configuration principale du module.

#### **Mises à jour MyPresta.eu et vérification de version**
En haut de la page de configuration, vous verrez généralement des paramètres liés aux mises à jour MyPresta.eu. Ceux-ci sont standard pour les modules MyPresta.eu et vous aident à maintenir votre module à jour.

-   **Ce que fait ce paramètre :** Ces champs (souvent étiquetés `mypresta_updates`, `update_`, `updatev_`) sont utilisés par le module pour vérifier les nouvelles versions disponibles sur MyPresta.eu et vous informer si une mise à jour est nécessaire. Ils sont généralement pré-remplis ou gérés automatiquement.
-   **Effet de la modification de ce paramètre :**
    -   *Si activé/actif :* Le module peut vérifier périodiquement les mises à jour, vous informant dans le back office de PrestaShop si une nouvelle version est disponible.
    -   *Si désactivé/inactif :* Vous pourriez ne pas recevoir de notifications automatiques concernant les mises à jour du module, nécessitant des vérifications manuelles.
-   **Valeur recommandée :** Laissez ces paramètres tels quels, généralement activés ou gérés automatiquement, pour vous assurer d'être toujours informé des dernières versions du module et des correctifs de sécurité.
-   **Scénario/exemple pour le marchand :** Vous souhaitez être informé lorsqu'une nouvelle version du module est publiée, incluant de nouvelles fonctionnalités ou des corrections de bugs, vous maintenez donc ces vérifications de mise à jour actives.

#### **Paramètres principaux du module**
Sous les paramètres de mise à jour, vous trouverez les options de configuration principales pour la fonctionnalité d'e-mail en CCI.

-   **Adresse e-mail pour la CCI :**
    -   **Ce que fait ce paramètre :** C'est le paramètre le plus crucial. Il définit l'adresse e-mail à laquelle toutes les copies CCI sélectionnées seront envoyées.
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsqu'une adresse e-mail valide est définie :* Tous les e-mails sélectionnés dans la liste ci-dessous auront une copie carbone invisible envoyée à cette adresse.
        -   *Lorsqu'il est laissé vide ou défini sur une adresse invalide :* Aucune copie CCI ne sera envoyée, même si des e-mails sont sélectionnés dans la liste.
    -   **Valeur recommandée :** Une adresse e-mail dédiée à l'archivage (par exemple, `archive@votreboutique.com`, `support@votreboutique.com`, ou votre adresse e-mail d'administrateur personnelle).
    -   **Scénario/exemple pour le marchand :** Vous souhaitez que toutes les confirmations de commande soient copiées dans la boîte de réception de votre équipe de service client, `support@votreboutique.com`, vous saisissez donc cette adresse ici.

-   **Sélectionner les e-mails à mettre en CCI :**
    -   **Ce que fait ce paramètre :** Cette section présente une liste de tous les modèles d'e-mails (types d'e-mails) que votre boutique PrestaShop peut envoyer. Vous pouvez sélectionner les types d'e-mails spécifiques que vous souhaitez mettre en CCI.
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsqu'un type d'e-mail est coché :* Une copie CCI de ce type d'e-mail spécifique sera envoyée à l'"Adresse e-mail pour la CCI" chaque fois que votre boutique l'enverra.
        -   *Lorsqu'un type d'e-mail est décoché :* Aucune copie CCI ne sera envoyée pour ce type d'e-mail spécifique.
    -   **Valeur recommandée :** Sélectionnez uniquement les types d'e-mails qui sont critiques pour votre tenue de registres ou vos besoins opérationnels. Une sur-CCI peut inonder une boîte de réception. Les choix courants incluent :
        -   `order_conf` (Confirmation de commande)
        -   `shipped` (Commande expédiée)
        -   `contact_form` (Soumission de formulaire de contact)
        -   `password` (Réinitialisation de mot de passe)
        -   `account` (Création de nouveau compte)
    -   **Scénario/exemple pour le marchand :** Vous souhaitez conserver un enregistrement de toutes les nouvelles commandes et demandes de clients. Vous cocherez `order_conf` et `contact_form` dans la liste.

### 2.2 Écrans d'administration dédiés et vues de contrôleur

#### **Gestion des e-mails en CCI (Back Office > Paramètres avancés > E-mail en CCI)**
Ce module crée un élément de menu dédié dans votre back office PrestaShop sous "Paramètres avancés" (ou similaire, selon la version de PrestaShop) nommé "E-mail en CCI". Cet écran est géré par `AdminMailBccController`.

-   **Nom de l'écran et emplacement du menu :** **Paramètres avancés > E-mail en CCI**
-   **Actions et paramètres disponibles :** Cet écran présente généralement une grille (liste) de tous les types d'e-mails que vous avez configurés pour être mis en CCI, ainsi que l'adresse e-mail de la CCI. Il agit comme une interface de résumé et de gestion pour vos paramètres de CCI.
    -   Vous pourriez voir des colonnes comme :
        -   **ID :** Identifiant interne de la règle de CCI.
        -   **Modèle d'e-mail :** Le nom du modèle d'e-mail (par exemple, `order_conf`).
        -   **E-mail CCI :** L'adresse e-mail où la copie est envoyée.
        -   **Activé :** Un interrupteur pour activer ou désactiver rapidement la CCI pour ce type d'e-mail spécifique.
        -   **Actions :** Boutons pour modifier ou supprimer la règle de CCI (bien que souvent, la page de configuration principale du module soit utilisée pour la sélection en masse).
-   **Effet des modifications :**
    -   *Activation/Désactivation d'une règle :* Contrôle directement si une copie CCI est envoyée pour ce type d'e-mail spécifique.
    -   *Modification d'une règle :* Vous permet de modifier l'adresse e-mail de la CCI pour un type d'e-mail spécifique (si le module prend en charge les adresses CCI par e-mail, sinon cela reflétera le paramètre global).
    -   *Suppression d'une règle :* Supprime le paramètre de CCI pour ce type d'e-mail.
-   **Flux de travail recommandé pour la gestion quotidienne de la boutique :** Utilisez cet écran pour examiner rapidement quels e-mails sont mis en CCI et pour effectuer des modifications rapides d'activation/désactivation sans revenir à la configuration principale du module. Pour ajouter de nouveaux types d'e-mails ou modifier l'adresse CCI principale, la page de configuration principale du module est généralement plus efficace.

#### **index.php (bccmail/controllers/admin/index.php)**
Ce fichier est une pratique standard de PrestaShop pour sécuriser les répertoires des contrôleurs d'administration et ne présente généralement pas d'écran ou d'options de configuration directement visibles par l'utilisateur. Il contient généralement un simple `header('Location: ../../index.php?controller=AdminHome');` ou similaire pour rediriger les accès non autorisés, empêchant la navigation directe dans le répertoire. Les marchands n'interagiront pas avec ce fichier.

### 2.3 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Valeur par défaut / Recommandée | Objectif et impact |
|---|---|---|---|
| **Page de configuration du module** | Mises à jour MyPresta.eu | Activé | Vous tient informé des mises à jour du module. |
| | **Adresse e-mail pour la CCI** | Votre e-mail d'administrateur / `archive@votreboutique.com` | L'e-mail de destination pour toutes les copies CCI. Critique pour l'archivage. |
| | **Sélectionner les e-mails à mettre en CCI** | `order_conf`, `contact_form`, `shipped` | Choisissez les types d'e-mails spécifiques à copier. Empêche l'inondation de la boîte de réception. |
| **Paramètres avancés > E-mail en CCI** | Liste des modèles d'e-mails | Varie selon la sélection | Aperçu et bascule rapide pour les types d'e-mails CCI configurés. |
| | Bascule Activé | Activé | Active/désactive rapidement la CCI pour un type d'e-mail spécifique. |

## 3. Dépannage pour le marchand et questions fréquemment posées (FAQ)

**Q : J'ai configuré le module, mais je ne reçois aucun e-mail en CCI. Que dois-je vérifier ?**
R :
1.  **Vérifiez l'adresse e-mail de la CCI :** Allez dans **Modules > Gestionnaire de modules > Configurer** pour "Envoyer une copie des e-mails (CCI)" et assurez-vous que l'"Adresse e-mail pour la CCI" est correctement orthographiée et valide.
2.  **Vérifiez les types d'e-mails sélectionnés :** Assurez-vous que les types d'e-mails spécifiques que vous attendez être copiés (par exemple, `order_conf`) sont réellement cochés dans la configuration du module.
3.  **Vérifiez le dossier de spam :** Les e-mails en CCI pourraient atterrir dans le dossier de spam ou de courrier indésirable de la boîte de réception du destinataire de la CCI.
4.  **Paramètres d'e-mail de PrestaShop :** Assurez-vous que les paramètres généraux d'e-mail de votre boutique PrestaShop (**Paramètres avancés > E-mail**) sont correctement configurés et que votre boutique peut envoyer des e-mails en général. Testez en envoyant un e-mail de test depuis PrestaShop.
5.  **Videz le cache :** Parfois, le cache de PrestaShop peut empêcher les modifications de prendre effet immédiatement. Allez dans **Paramètres avancés > Performances** et cliquez sur "Vider le cache" (ou "Vider le cache Smarty" dans les versions plus anciennes).

**Q : Puis-je envoyer des copies CCI à plusieurs adresses e-mail ?**
R : La configuration principale du module permet une seule adresse e-mail CCI principale. Si vous devez envoyer des copies à plusieurs adresses, vous avez deux options :
1.  Définissez l'adresse e-mail de la CCI sur une liste de distribution ou une adresse e-mail de groupe qui transfère à plusieurs destinataires.
2.  Configurez une règle d'e-mail dans la boîte de réception du destinataire de la CCI pour transférer automatiquement les copies à d'autres adresses en fonction de l'expéditeur ou de l'objet.

**Q : Ce module ralentira-t-il ma boutique ou l'envoi d'e-mails ?**
R : L'impact sur les performances est généralement négligeable. L'envoi d'une copie CCI supplémentaire est une opération très mineure pour le serveur de messagerie. Le module utilise le mécanisme d'envoi d'e-mails standard de PrestaShop, ajoutant simplement un destinataire supplémentaire.

**Q : Mon thème personnalisé a des modèles d'e-mails personnalisés. Ce module fonctionnera-t-il toujours ?**
R : Oui, le module s'accroche à la classe `Mail` de base de PrestaShop, qui est responsable de l'envoi de tous les e-mails, qu'ils utilisent des modèles par défaut ou personnalisés. Tant que PrestaShop envoie l'e-mail, ce module peut le mettre en CCI.

**Q : Comment traduire l'interface du module dans une autre langue ?**
R : Allez dans **International > Traductions** dans votre back office PrestaShop. Sélectionnez "Traductions des modules installés", choisissez votre thème, puis sélectionnez "Envoyer une copie des e-mails (CCI)". Vous pourrez alors traduire toutes les chaînes affichées par le module dans le back office.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

Cette section fournit une plongée approfondie dans l'implémentation technique du module "Envoyer une copie des e-mails (CCI)" pour les développeurs et les webmasters.

### 4.1 Aperçu de l'architecture
Le module "Envoyer une copie des e-mails (CCI)" (`bccmail`) fonctionne principalement en surchargeant la classe `Mail` de PrestaShop. C'est une technique courante et puissante dans PrestaShop pour modifier le comportement du cœur sans éditer directement les fichiers du cœur. En surchargeant `Mail.php`, le module intercepte toutes les opérations d'envoi d'e-mails et injecte la fonctionnalité CCI en fonction de sa configuration. Il suit une structure de module PrestaShop standard avec un fichier de module principal, des contrôleurs d'administration pour la configuration et une classe de surcharge.

### 4.2 Contrôleurs (`controllers/`)

-   **Contrôleurs Front-Office** : Ce module n'a pas de contrôleurs front-office dédiés car sa fonctionnalité est entièrement côté back-office et côté serveur.

-   **Contrôleurs d'administration Back-Office** :
    *   `bccmail/controllers/admin/AdminMailBcc.php`
        *   **Nom de la classe et classe parente :** `AdminMailBccController` étend `ModuleAdminController`.
        *   **Nom de l'onglet et entité gérée :** Ce contrôleur gère l'onglet "E-mail en CCI" sous "Paramètres avancés". Il est responsable de l'affichage et de la gestion de la liste des types d'e-mails CCI configurés. Il utilise probablement `HelperList` ou `HelperView` de PrestaShop pour afficher une grille d'objets `MailBcc` (ou une représentation de la configuration du module).
        *   **Responsabilité :** Gère l'affichage du résumé de la configuration CCI, permettant potentiellement l'activation/désactivation ou la suppression de règles individuelles. Il interagit avec les données de configuration du module (probablement stockées dans `ps_configuration` ou une table personnalisée si des données plus complexes sont nécessaires par règle CCI).
    *   `bccmail/controllers/admin/index.php`
        *   **Nom de la classe et classe parente :** Pas une classe, mais un fichier de sécurité.
        *   **Responsabilité :** Ce fichier est une mesure de sécurité standard de PrestaShop. Il contient généralement `header('Location: ../../index.php?controller=AdminHome');` ou similaire pour empêcher la liste directe des répertoires et l'accès non autorisé au répertoire `controllers/admin`. Il ne fournit aucune logique fonctionnelle pour le module lui-même.

### 4.3 Classes et modèles de base (`classes/`)

-   `bccmail/override/classes/Mail.php`
    *   **Avec quelle table de base de données interagit-il :** Interagit indirectement avec `ps_configuration` pour récupérer les paramètres du module (adresse e-mail CCI et modèles d'e-mails sélectionnés).
    *   **S'il étend `ObjectModel` :** Non, il surcharge la classe `Mail` de base.
    *   **Méthodes publiques clés et logique métier encapsulée :**
        *   Ce fichier contient la logique de base pour intercepter l'envoi d'e-mails. Il surcharge la méthode `send()` (ou une méthode similaire) de la classe `Mail` originale.
        *   Dans la méthode `send()` surchargée, il va :
            1.  Récupérer la configuration du module : l'adresse e-mail CCI globale et la liste des modèles d'e-mails sélectionnés pour la CCI.
            2.  Vérifier si l'e-mail en cours d'envoi (identifié par son nom de modèle, par exemple, `order_conf`) figure dans la liste des modèles CCI sélectionnés.
            3.  Si une correspondance est trouvée, il modifie les en-têtes ou les paramètres de l'e-mail pour inclure l'adresse e-mail CCI configurée avant d'appeler la méthode `Mail::send()` parente pour envoyer l'e-mail.
        *   Cela garantit que le destinataire CCI est ajouté à la liste de copie carbone invisible de l'e-mail, les rendant invisibles aux destinataires principaux.

-   `bccmail/override/classes/index.php`
    *   **Responsabilité :** Similaire à `controllers/admin/index.php`, il s'agit d'un fichier de sécurité pour empêcher la liste directe des répertoires `override/classes`. Il contient généralement une balise PHP vide ou une redirection.

### 4.4 Actifs JavaScript (`views/js/`)

-   `bccmail/views/templates/admin/js/bccmail.js`
    *   **Portée :** Back-office.
    *   **Quels écouteurs d'événements il lie :** Ce script est probablement utilisé sur la page de configuration du module ou l'écran `AdminMailBccController`. Il pourrait lier des écouteurs pour :
        *   Les événements de soumission de formulaire pour gérer la sauvegarde de la configuration.
        *   Les changements de case à cocher pour sélectionner les modèles d'e-mails à mettre en CCI.
        *   La validation des champs de saisie pour l'adresse e-mail de la CCI.
        *   Les appels AJAX pour mettre à jour les paramètres dynamiquement sans rechargement complet de la page.
    *   **Quelles manipulations DOM, pop-ups modaux, animations ou appels SDK tiers externes il exécute :** Pourrait effectuer de simples manipulations DOM comme afficher/masquer des éléments en fonction des sélections, afficher des messages de succès/erreur, ou une validation de formulaire de base. Il est peu probable qu'il implique des animations complexes ou des SDK tiers pour la fonctionnalité de ce module.

### 4.5 Feuilles de style CSS (`views/css/`)
Le module ne semble pas inclure de fichiers CSS personnalisés dans son archive. Il s'appuie probablement sur le style par défaut du back-office de PrestaShop pour ses formulaires et listes de configuration, ou sur des styles en ligne si absolument nécessaire.

### 4.6 Structure des modèles Smarty (`views/templates/`)

-   **Modèles de hook (`views/templates/hook/`)** : Aucun explicitement listé, mais le formulaire de configuration principal du module (`getContent()`) rendrait ses paramètres à l'aide d'un modèle Smarty, généralement situé dans `views/templates/admin/configure.tpl` ou similaire, même s'il n'est pas explicitement listé dans l'inventaire comme un fichier séparé.
-   **Modèles d'administration (`views/templates/admin/`)** :
    *   `bccmail/lib/searchTool/views/scripts.tpl`
        *   **Objectif :** Ce modèle fait probablement partie d'une bibliothèque d'aide ou d'utilitaire au sein du module (par exemple, un outil de recherche pour les modèles d'e-mails). Il contiendrait du JavaScript ou de la logique Smarty pour rendre les entrées de recherche, filtrer les listes ou gérer le chargement de contenu dynamique dans l'interface d'administration. Ce n'est pas une page autonome mais un composant.
-   **Modèles Front-office (`views/templates/front/`)** : Aucun. Le module n'a aucune présence en front-office.

### 4.7 Schéma de base de données et carte des hooks

-   **Tables de base de données** :
    *   Le module stocke principalement sa configuration dans la table `ps_configuration` de PrestaShop.
        *   Les clés `PS_CONFIGURATION` incluraient :
            *   `BCCMAIL_EMAIL_ADDRESS` : Stocke l'adresse e-mail principale pour la CCI.
            *   `BCCMAIL_SELECTED_TEMPLATES` : Stocke un tableau sérialisé ou une chaîne de caractères séparée par des virgules des noms de modèles d'e-mails sélectionnés pour la CCI.
            *   `MYPRESTA_UPDATES`, `UPDATE_`, `UPDATEV_` : Pour les vérifications de mise à jour du module.
    *   Aucune table SQL personnalisée n'est explicitement créée par ce module sur la base de l'inventaire fourni.

-   **Table des hooks enregistrés** :
    Le module n'enregistre aucun hook d'affichage standard (comme `displayHeader`, `displayRightColumn`, `displayFooter`) car il n'a aucune présence en front-office. Sa fonctionnalité principale repose sur la surcharge de la classe `Mail` plutôt que sur l'utilisation de hooks PrestaShop traditionnels pour l'envoi d'e-mails.

    Cependant, il "s'accroche" implicitement au processus d'envoi d'e-mails via sa surcharge.
    *   **`actionEmailSend` (Implicite via surcharge)** : Bien qu'il ne s'agisse pas d'un hook formellement enregistré, `override/classes/Mail.php` du module intercepte effectivement la méthode `Mail::send()`, qui est l'action principale d'envoi d'un e-mail. C'est là que la logique de la CCI est injectée.
        *   **Moment d'exécution :** Chaque fois que `Mail::send()` est appelé par PrestaShop (par exemple, lors de la confirmation de commande, de l'inscription du client, de la soumission du formulaire de contact).
        *   **Objectif technique :** Ajouter le destinataire CCI configuré à l'e-mail avant qu'il ne soit envoyé par le système de messagerie de PrestaShop.

## 5. Support officiel et mises à jour
Pour les dernières mises à jour du module, le support technique et les ressources supplémentaires, veuillez visiter votre compte client sur [MyPresta.eu](https://mypresta.eu/my-account/orders/). Notre équipe de support est disponible pour vous aider avec toutes les questions ou problèmes que vous pourriez avoir concernant le module "Envoyer une copie des e-mails (CCI)".
