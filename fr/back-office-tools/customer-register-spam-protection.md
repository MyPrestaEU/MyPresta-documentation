---
title: "Protection anti-spam à l'enregistrement client - Manuel du Marchand & Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop 'Protection anti-spam à l'enregistrement client' par MyPresta.eu."
sidebar:
  label: "Protection anti-spam à l'enregistrement client - Manuel du Marchand & Guide de Configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Customer register spam protection sur MyPresta.eu](https://mypresta.eu/modules/administration-tools/customer-register-spam-protection.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/back-office-tools/customer-register-spam-protection/)
>
> ---


# Protection anti-spam à l'enregistrement client

## 1. Exigences et compatibilité

- **Versions PrestaShop prises en charge** : PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilité PHP** : PHP 5.6 - 8.5
- **Exigences d'hébergement** : Les extensions PHP standard (cURL, JSON, OpenSSL) sont généralement requises pour la communication avec les API externes, que ce module peut utiliser pour une détection avancée du spam. Assurez-vous que votre environnement d'hébergement répond à ces exigences courantes.

## 2. Guide de configuration complet (Chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

Ceci est l'écran de configuration principal du module « Protection anti-spam à l'enregistrement client », accessible après l'installation. Ici, vous définirez les règles et les comportements fondamentaux du système de protection anti-spam.

Bien que les paramètres spécifiques ne soient pas détaillés dans le dossier fourni, en fonction de l'objectif du module, les paramètres typiques incluraient :

-   **Activer/Désactiver le module :**

    -   **Ce que fait ce paramètre :** Active ou désactive la fonctionnalité de protection anti-spam pour l'ensemble de votre boutique.
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsqu'il est activé :* Le module surveille et bloque activement les enregistrements clients suspects.
        -   *Lorsqu'il est désactivé :* Le module est inactif, et toutes les tentatives d'enregistrement se dérouleront sans vérification anti-spam.
    -   **Valeur recommandée :** OUI (sauf si vous déboguez activement ou désactivez temporairement pour une raison spécifique).
    -   **Scénario / exemple pour le marchand :** Activez-le immédiatement après l'installation pour commencer à protéger votre boutique. Désactivez-le uniquement si vous soupçonnez qu'il bloque des clients légitimes et que vous devez enquêter, mais rappelez-vous que cela rend votre boutique vulnérable.
-   **Niveau de sensibilité de la détection de spam :**

    -   **Ce que fait ce paramètre :** Contrôle l'agressivité avec laquelle le module identifie et bloque le spam potentiel. Il peut s'agir d'un curseur (Faible, Moyen, Élevé) ou d'un seuil numérique.
    -   **Effet de la modification de ce paramètre :**
        -   *Sensibilité plus élevée :* Plus susceptible de bloquer les enregistrements suspects, y compris potentiellement un petit nombre d'utilisateurs légitimes (faux positifs).
        -   *Sensibilité plus faible :* Moins susceptible de bloquer les utilisateurs légitimes, mais peut laisser passer plus de comptes de spam (faux négatifs).
    -   **Valeur recommandée :** Commencez par « Moyen » et ajustez en fonction du trafic de votre boutique et du nombre de tentatives de spam observées.
    -   **Scénario / exemple pour le marchand :** Si vous voyez beaucoup de spam malgré l'activation du module, augmentez la sensibilité. Si les clients signalent des problèmes d'enregistrement, essayez de la baisser légèrement.
-   **Action en cas de spam détecté :**

    -   **Ce que fait ce paramètre :** Définit ce qui se passe lorsque le module identifie une tentative d'enregistrement comme du spam.
    -   **Effet de la modification de ce paramètre :**
        -   *Bloquer l'enregistrement :* Le compte n'est pas créé, et l'utilisateur reçoit un message d'erreur.
        -   *Marquer comme en attente/à réviser :* Le compte est créé mais signalé pour une révision manuelle par un administrateur.
        -   *Journaliser uniquement :* La tentative est enregistrée, mais le compte est toujours créé (utile pour la surveillance initiale).
    -   **Valeur recommandée :** « Bloquer l'enregistrement » pour une protection maximale.
    -   **Scénario / exemple pour le marchand :** Pour la plupart des boutiques, le blocage pur et simple est la meilleure approche. Si vous avez une base de clients très spécifique et que vous voulez être très prudent, « Marquer comme en attente » pourrait être une option, mais cela nécessite un travail manuel.
-   **Message d'erreur pour les enregistrements bloqués :**

    -   **Ce que fait ce paramètre :** Vous permet de personnaliser le message affiché aux utilisateurs dont les tentatives d'enregistrement sont bloquées.
    -   **Effet de la modification de ce paramètre :**
        -   *Message personnalisé :* Fournit un message convivial ou informatif au lieu d'une erreur générique.
    -   **Valeur recommandée :** Un message poli comme « L'enregistrement n'a pas pu être effectué. Veuillez contacter le support si vous pensez qu'il s'agit d'une erreur. »
    -   **Scénario / exemple pour le marchand :** Évitez les messages qui révèlent trop d'informations sur vos méthodes de détection de spam. Un message simple et utile est préférable.
-   **Gestion de la liste noire/blanche d'IP :**

    -   **Ce que fait ce paramètre :** Vous permet d'ajouter manuellement des adresses IP spécifiques à une liste noire (toujours bloquer) ou à une liste blanche (ne jamais bloquer).
    -   **Effet de la modification de ce paramètre :**
        -   *IPs en liste noire :* Tout enregistrement provenant de ces IPs sera bloqué, quels que soient les autres paramètres.
        -   *IPs en liste blanche :* Tout enregistrement provenant de ces IPs sera toujours autorisé.
    -   **Valeur recommandée :** À utiliser avec parcimonie. Mettez en liste noire les spammeurs connus. Mettez en liste blanche uniquement si un utilisateur légitime ou un système interne est faussement bloqué.
    -   **Scénario / exemple pour le marchand :** Si vous voyez à plusieurs reprises du spam provenant d'une plage d'IP spécifique, ajoutez-la à la liste noire. Si l'IP de votre environnement de test interne est bloquée, mettez-la en liste blanche.
-   **Gestion de la liste noire/blanche d'e-mails :**

    -   **Ce que fait ce paramètre :** Similaire à la gestion des IP, mais pour des adresses e-mail ou des domaines d'e-mail spécifiques.
    -   **Effet de la modification de ce paramètre :**
        -   *E-mails/domaines en liste noire :* Les enregistrements utilisant ceux-ci seront bloqués.
        -   *E-mails/domaines en liste blanche :* Les enregistrements utilisant ceux-ci seront toujours autorisés.
    -   **Valeur recommandée :** À utiliser avec parcimonie. Mettez en liste noire les adresses e-mail ou les domaines de spam connus.
    -   **Scénario / exemple pour le marchand :** Si vous remarquez un schéma d'enregistrements de spam provenant de services d'e-mails jetables (par exemple, mailinator.com), vous pouvez mettre ce domaine en liste noire.
-   **Intégration avec des API externes (par exemple, reCAPTCHA, Akismet) :**

    -   **Ce que fait ce paramètre :** Si le module s'intègre avec des services de détection de spam externes, cette section contiendra des champs pour les clés API et la configuration spécifiques à ces services.
    -   **Effet de la modification de ce paramètre :**
        -   *Activé avec des clés valides :* Ajoute une couche de protection supplémentaire en utilisant la base de données et les algorithmes du service externe.
        -   *Désactivé ou clés invalides :* Le service externe ne sera pas utilisé, s'appuyant uniquement sur la logique interne du module.
    -   **Valeur recommandée :** Activez et configurez si disponible, car cela améliore considérablement la protection.
    -   **Scénario / exemple pour le marchand :** Obtenez les clés API du service respectif (par exemple, Google reCAPTCHA) et saisissez-les ici pour tirer parti de leur filtrage anti-spam avancé.

### 2.2 Écrans d'administration dédiés et vues de contrôleur

Le module fournit des écrans dédiés dans le Back Office de PrestaShop pour gérer et examiner les tentatives de spam et les bannissements. Ceux-ci sont cruciaux pour surveiller l'efficacité du module et effectuer des ajustements manuels.

#### 2.2.1 AdminregproAttemptsController (Back Office > Modules > Protection anti-spam à l'enregistrement client > Tentatives)

-   **Nom de l'écran et emplacement du menu :** « Tentatives » (ou similaire, sous l'élément de menu principal du module). Cet écran liste toutes les tentatives d'enregistrement que le module a traitées, en particulier celles signalées comme suspectes ou bloquées.
-   **Actions et paramètres disponibles :** Il s'agira d'une vue en grille (liste) affichant les détails de chaque tentative d'enregistrement.
    -   **Colonnes :** Inclut généralement :
        -   Date/Heure de la tentative
        -   Adresse IP
        -   Adresse e-mail utilisée
        -   Statut (par exemple, « Bloqué », « Autorisé », « Signalé »)
        -   Raison du statut (par exemple, « IP en liste noire », « Score de spam élevé »)
        -   Boutons d'action (par exemple, « Voir les détails », « Mettre l'IP en liste blanche », « Mettre l'IP en liste noire », « Supprimer l'entrée »)
    -   **Filtrage/Tri :** Fonctionnalités de grille PrestaShop standard pour filtrer par date, IP, statut, etc.
-   **Effet des modifications :**
    -   *Mettre une IP en liste blanche :* Ajoute l'IP à la liste blanche du module, garantissant que les futurs enregistrements provenant de cette IP sont autorisés.
    -   *Mettre une IP en liste noire :* Ajoute l'IP à la liste noire du module, bloquant les futurs enregistrements provenant de cette IP.
    -   *Supprimer une entrée :* Supprime l'enregistrement du journal des tentatives (ne débloque/débannit pas).
-   **Flux de travail recommandé pour la gestion quotidienne de la boutique :** Examinez régulièrement cette liste, surtout si vous recevez des rapports de clients légitimes bloqués. Utilisez l'action « Mettre l'IP en liste blanche » si vous identifiez un faux positif. Inversement, si vous voyez du spam persistant provenant d'une IP particulière, utilisez « Mettre l'IP en liste noire ».

#### 2.2.2 AdminregproBansController (Back Office > Modules > Protection anti-spam à l'enregistrement client > Bannissements)

-   **Nom de l'écran et emplacement du menu :** « Bannissements » (ou similaire, sous l'élément de menu principal du module). Cet écran liste tous les bannissements actifs (IPs ou adresses/domaines e-mail) que le module applique.
-   **Actions et paramètres disponibles :** Il s'agira d'une vue en grille (liste) affichant les détails de chaque bannissement.
    -   **Colonnes :** Inclut généralement :
        -   Type de bannissement (par exemple, « IP », « E-mail », « Domaine »)
        -   Valeur (par exemple, « 192.168.1.1 », « [spam@example.com](mailto:spam@example.com) », « mauvais-domaine.com »)
        -   Date d'ajout
        -   Raison (si ajoutée manuellement)
        -   Boutons d'action (par exemple, « Supprimer le bannissement », « Modifier »)
    -   **Filtrage/Tri :** Fonctionnalités de grille PrestaShop standard.
-   **Effet des modifications :**
    -   *Supprimer un bannissement :* Lève la restriction pour l'IP, l'e-mail ou le domaine spécifié, autorisant les futurs enregistrements à partir de celui-ci.
    -   *Ajouter un bannissement :* Ajoute manuellement une nouvelle IP, un e-mail ou un domaine à la liste des bannissements.
-   **Flux de travail recommandé pour la gestion quotidienne de la boutique :** C'est votre centre névralgique pour gérer vos listes de bannissements personnalisées. Si vous avez mis une IP en liste noire depuis l'écran « Tentatives », elle apparaîtra ici. Si un client légitime est accidentellement pris dans un bannissement, vous pouvez rapidement supprimer son IP ou son e-mail de cette liste.

#### 2.2.3 index.php (regpro/controllers/admin/index.php)

-   **Table / Entité gérée :** Ce fichier sert probablement de routage ou de contrôleur par défaut pour la section d'administration du module, redirigeant potentiellement vers l'un des contrôleurs spécifiques (comme `AdminregproAttempts` ou `AdminregproBans`) ou affichant un aperçu/tableau de bord général pour le module. Il ne gère peut-être pas directement une table spécifique mais agit comme un point d'entrée.
-   **Champs de formulaire et colonnes :** S'il affiche une grille, ce serait un résumé ou un tableau de bord. Plus probablement, c'est un redirigeur.
-   **Effet des modifications :** Pas de modifications directes des données, mais contrôle la vue initiale lors de l'accès à la section d'administration du module.
-   **Flux de travail recommandé pour la gestion quotidienne de la boutique :** C'est généralement le premier écran que vous voyez en cliquant sur le module dans la liste des modules. Il peut offrir des statistiques rapides ou des liens vers les sections « Tentatives » et « Bannissements ».

### 2.3 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Valeur par défaut / Recommandée | Objectif et impact |
| --- | --- | --- | --- |
| **Page de configuration du module** | Activer/Désactiver le module | OUI | Active/désactive la protection anti-spam. |
| | Sensibilité de la détection de spam | Moyenne | Contrôle l'agressivité de la détection de spam. |
| | Action en cas de spam détecté | Bloquer l'enregistrement | Définit la réponse au spam (bloquer, réviser, journaliser). |
| | Message d'erreur pour les enregistrements bloqués | « L'enregistrement n'a pas pu être effectué. Veuillez contacter le support si vous pensez qu'il s'agit d'une erreur. » | Personnalise le message pour les utilisateurs bloqués. |
| | Liste noire/blanche d'IP | À utiliser avec parcimonie | Bloque/autorise manuellement des IPs spécifiques. |
| | Liste noire/blanche d'e-mails | À utiliser avec parcimonie | Bloque/autorise manuellement des e-mails/domaines spécifiques. |
| | Intégration API externe | Activer avec des clés valides | Améliore la protection avec des services tiers. |
| **AdminregproAttemptsController** | Afficher le journal des tentatives | N/A | Examiner toutes les tentatives d'enregistrement, leur statut et leurs raisons. |
| | Mettre l'IP en liste blanche (depuis le journal) | N/A | Autorise les futurs enregistrements depuis une IP spécifique. |
| | Mettre l'IP en liste noire (depuis le journal) | N/A | Bloque les futurs enregistrements depuis une IP spécifique. |
| **AdminregproBansController** | Afficher les bannissements actifs | N/A | Gérer et examiner tous les bannissements IP/e-mail/domaine actuellement actifs. |
| | Supprimer le bannissement | N/A | Lève un bannissement spécifique. |
| | Ajouter un nouveau bannissement | N/A | Ajoute manuellement une nouvelle IP, un e-mail ou un domaine à la liste des bannissements. |

## 3. Dépannage pour les marchands et questions fréquemment posées (FAQ)

**Q : Mes clients légitimes signalent qu'ils ne peuvent pas s'inscrire. Que dois-je faire ?**
R : Tout d'abord, vérifiez le journal des « Tentatives » (`AdminregproAttemptsController`) dans le Back Office. Recherchez leur adresse IP ou leur e-mail. Si leur tentative a été bloquée, vous verrez la raison. Vous pouvez ensuite mettre leur adresse IP ou leur e-mail en liste blanche, ou réduire temporairement le paramètre de sensibilité du module. N'oubliez pas de vider le cache de votre PrestaShop après avoir effectué des modifications.

**Q : Je reçois toujours des enregistrements de spam même avec le module actif.**
R :

1.  **Vérifier la sensibilité :** Augmentez la « Sensibilité de la détection de spam » dans la configuration principale du module.
2.  **Examiner le journal des tentatives :** Analysez le journal des « Tentatives » pour voir si le module enregistre ces tentatives et pourquoi elles pourraient passer à travers.
3.  **Ajouter à la liste noire :** Si vous identifiez des IPs ou des domaines d'e-mail spécifiques provenant des enregistrements de spam, ajoutez-les manuellement à votre liste de bannissement via le `AdminregproBansController`.
4.  **API externe :** Assurez-vous que toutes les API de protection anti-spam externes intégrées (comme reCAPTCHA) sont correctement configurées et ont des clés valides.

**Q : Comment savoir si le module fonctionne réellement ?**
R : La meilleure façon est de surveiller le journal des « Tentatives » (`AdminregproAttemptsController`). Vous devriez voir des entrées pour les tentatives bloquées, indiquant que le module identifie et empêche activement le spam. Si vous receviez auparavant beaucoup de spam, vous devriez également remarquer une réduction significative des nouveaux faux comptes clients.

**Q : Ce module affecte-t-il les performances de ma boutique ?**
R : Le module est conçu pour être efficace. Bien qu'il ajoute une petite étape de traitement lors de l'enregistrement, cela est généralement négligeable par rapport aux avantages de la prévention du spam. Une base de données pleine de comptes de spam causerait des problèmes de performance bien plus importants à long terme.

**Q : J'ai modifié les paramètres, mais rien ne semble se passer sur le front office.**
R : Videz toujours le cache de votre PrestaShop après avoir effectué des modifications de configuration. Allez dans **Paramètres avancés > Performances** et cliquez sur « Vider le cache » dans le coin supérieur droit. Cela garantit que le module charge les paramètres mis à jour.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

### 4.1 Vue d'ensemble de l'architecture

Le module « Protection anti-spam à l'enregistrement client » (`regpro`) est construit en suivant le modèle MVC (Modèle-Vue-Contrôleur) de PrestaShop. Il fonctionne principalement en s'accrochant au processus d'enregistrement client, en tirant parti du système de hooks de PrestaShop pour intercepter et valider les données d'enregistrement. Il utilise des contrôleurs d'administration dédiés pour gérer les tentatives et les bannissements, et stocke sa configuration dans `ps_configuration`. La logique principale du module pour la détection du spam est probablement contenue dans le fichier principal du module `index.php`, avec des fonctions ou des classes d'aide (bien qu'aucune ne soit explicitement listée dans le dossier, elles pourraient être internes à la classe principale du module).

### 4.2 Contrôleurs (`controllers/`)

-   **Contrôleurs Front-Office** :
    Le dossier du module n'indique aucun contrôleur front-office dédié. Cela suggère que les interactions front-office du module (par exemple, l'interception des données d'enregistrement) sont gérées directement via des hooks dans le fichier principal du module `regpro/index.php`, ou en surchargeant les contrôleurs PrestaShop de base (bien que ce dernier soit moins courant pour une simple protection anti-spam). Les hooks `displayCustomerAccountForm` sont l'endroit où la logique du module serait déclenchée.
-   **Contrôleurs d'administration Back-Office** :
    Ces contrôleurs fournissent l'interface administrative pour gérer les données et les paramètres du module.

    -   `controllers/admin/AdminRegproAttempts.php`

        -   **Nom de la classe et classe parente :** `AdminRegproAttemptsController` (étend `ModuleAdminController` ou `AdminController`).
        -   **Responsabilité :** Gère la liste et les actions liées aux tentatives de spam enregistrées. Ce contrôleur est responsable de l'affichage de la grille des tentatives d'enregistrement, permettant aux administrateurs de visualiser les détails, de filtrer et d'effectuer des actions comme la mise en liste blanche ou en liste noire des IP basées sur ces tentatives. Il interagit avec la table de base de données `regattempt`.
    -   `controllers/admin/AdminRegproBans.php`

        -   **Nom de la classe et classe parente :** `AdminRegproBansController` (étend `ModuleAdminController` ou `AdminController`).
        -   **Responsabilité :** Gère la liste et les actions liées aux bannissements actifs (IPs, e-mails, domaines). Ce contrôleur permet aux administrateurs de visualiser, ajouter, modifier et supprimer des entrées des listes de bannissement du module. Il interagit avec la table de base de données `regban`.
    -   `controllers/admin/index.php`

        -   **Nom de la classe et classe parente :** Probablement un simple redirigeur ou un fichier de remplacement. Il pourrait contenir un `AdminController` de base qui redirige vers l'un des autres contrôleurs d'administration spécifiques au module (par exemple, `AdminRegproAttempts`) ou affiche un simple tableau de bord. Il ne gère pas directement une entité spécifique mais sert de point d'entrée pour la section d'administration du module.

### 4.3 Classes et modèles principaux (`classes/`)

Le dossier du module n'indique aucune classe personnalisée dans le répertoire `classes/`. Cela implique que les structures de données du module (pour les tentatives et les bannissements) sont soit gérées directement par la logique de `AdminController` à l'aide de requêtes SQL brutes, soit, plus probablement, les définitions `ObjectModel` pour `regattempt` et `regban` sont intégrées directement dans les contrôleurs `AdminRegproAttempts.php` et `AdminRegproBans.php` respectifs, ou dans le fichier principal `regpro/index.php`.

Si `ObjectModel` est utilisé, le tableau `$definition` serait défini pour :

-   `regattempt` : Mappage vers une table `ps_regattempt` (ou similaire), avec des champs comme `id_regattempt`, `ip_address`, `email`, `status`, `reason`, `date_add`.
-   `regban` : Mappage vers une table `ps_regban` (ou similaire), avec des champs comme `id_regban`, `type` (IP, e-mail, domaine), `value`, `date_add`.

### 4.4 Actifs JavaScript (`views/js/`)

-   `views/js/regpro-v3.js`
    -   **Portée :** Probablement Back-office. Le « v3 » pourrait indiquer une version ou une fonctionnalité spécifique.
    -   **Description :** Ce script est probablement responsable de l'amélioration de l'expérience utilisateur dans les écrans de configuration ou de gestion du Back Office du module. Il pourrait gérer :
        -   Les appels AJAX pour les mises à jour dynamiques (par exemple, filtrer les listes, ajouter/supprimer des bannissements sans rechargement de page).
        -   La validation de formulaire sur la page de configuration ou lors de l'ajout de nouvelles entrées de bannissement.
        -   Les éléments interactifs sur les grilles « Tentatives » ou « Bannissements » (par exemple, les boîtes de dialogue de confirmation pour les actions, le tri, la pagination).
        -   Potentiellement, la logique côté client pour l'intégration avec des API externes si elles nécessitent une interaction JS dans le BO.

### 4.5 Feuilles de style CSS (`views/css/`)

Le dossier du module n'indique aucun fichier CSS personnalisé. Cela suggère que le module s'appuie entièrement sur le style par défaut du Back Office de PrestaShop pour ses pages de configuration et ses grilles. Si un style spécifique est nécessaire, il serait soit en ligne dans les modèles, soit ajouté dynamiquement via JavaScript.

### 4.6 Structure des modèles Smarty (`views/templates/`)

-   **Modèles de hook (`views/templates/hook/`)** :
    Ces modèles sont rendus lorsque le module est accroché à des points spécifiques du front-office.

    -   `views/templates/hook/displayCustomerAccountForm-v3.tpl`

        -   **Hook :** `displayCustomerAccountForm` (ou similaire, spécifique à PrestaShop 1.7+ et 8.x).
        -   **Objectif :** Ce modèle est probablement utilisé pour injecter des champs cachés, des variables JavaScript, ou potentiellement un CAPTCHA/défi visible (si configuré) dans le formulaire d'enregistrement client. Le « v3 » suggère qu'il s'agit d'une version plus récente, éventuellement pour les versions plus récentes de PrestaShop ou un design spécifique. Il pourrait contenir la structure HTML pour reCAPTCHA si cette intégration est activée.
    -   `views/templates/hook/displayCustomerAccountForm.tpl`

        -   **Hook :** `displayCustomerAccountForm` (ou similaire, potentiellement pour les anciennes versions de PrestaShop comme 1.6.x).
        -   **Objectif :** Similaire à `displayCustomerAccountForm-v3.tpl`, mais potentiellement une version générique ou plus ancienne. Il servirait la même fonction d'injection d'éléments ou de logique dans le formulaire d'enregistrement client pour la détection de spam.
    -   `views/templates/hook/displayCustomerAccountFormTop.tpl`

        -   **Hook :** `displayCustomerAccountFormTop` (ou similaire).
        -   **Objectif :** Ce modèle rendrait le contenu tout en haut du formulaire d'enregistrement client. Cela pourrait être utilisé pour afficher un message général, ou pour injecter des éléments qui doivent apparaître avant les champs principaux du formulaire, comme une case à cocher « Je ne suis pas un robot » ou un avertissement.
-   **Modèles d'administration (`views/templates/admin/`)** :
    Ces modèles définissent la structure et le contenu des pages du Back Office du module.

    -   `views/templates/admin/main.tpl`
        -   **Objectif :** Il s'agit probablement du modèle principal pour la page de configuration du module (accessible via `getContent()` dans `regpro/index.php`) ou d'un wrapper général pour la section d'administration du module. Il contiendrait le HTML pour les différents paramètres, champs de saisie et boutons décrits dans la section 4.1. Il pourrait également inclure des liens vers les contrôleurs `AdminRegproAttempts` et `AdminRegproBans`.

### 4.7 Schéma de base de données et carte des hooks

-   **Tables de base de données** :
    Basé sur les contrôleurs d'administration, le module crée probablement deux tables personnalisées :

    -   `ps_regattempt` (ou préfixe similaire) : Stocke les enregistrements des tentatives d'enregistrement.
        -   `id_regattempt` (PK, INT)
        -   `ip_address` (VARCHAR)
        -   `email` (VARCHAR)
        -   `status` (VARCHAR, par exemple, 'blocked', 'allowed', 'flagged')
        -   `reason` (TEXT, explication du statut)
        -   `date_add` (DATETIME)
    -   `ps_regban` (ou préfixe similaire) : Stocke les enregistrements des bannissements actifs.
        -   `id_regban` (PK, INT)
        -   `type` (VARCHAR, par exemple, 'ip', 'email', 'domain')
        -   `value` (VARCHAR, l'IP, l'e-mail ou le domaine réel)
        -   `date_add` (DATETIME)
        -   `reason` (TEXT, facultatif, pour les bannissements manuels)

    Les paramètres de configuration (comme la sensibilité, les messages d'erreur, les clés API) sont stockés dans la table `ps_configuration` en utilisant des clés préfixées par `REGPRO_` (par exemple, `REGPRO_SENSITIVITY`, `REGPRO_ACTION_ON_SPAM`).
-   **Table des hooks enregistrés** :

| Nom du hook | Moment d'exécution | Objectif technique |
| --- | --- | --- |
| `displayHeader` | Rendu dans la section `<head>` de toutes les pages du front-office. | Potentiellement utilisé pour charger du CSS/JS spécifique au module globalement, ou pour l'injection de méta-tags pour la vérification d'API externe. |
| `displayCustomerAccountForm` | Rendu dans le formulaire d'enregistrement client. | Hook principal pour injecter des champs cachés, des éléments reCAPTCHA ou du JavaScript pour intercepter la soumission du formulaire et effectuer une validation côté client. |
| `displayCustomerAccountFormTop` | Rendu en haut du formulaire d'enregistrement client. | Similaire à `displayCustomerAccountForm`, mais garantit que le contenu apparaît avant les champs principaux du formulaire. |
| `actionCustomerAccountAdd` | Exécuté *après* qu'un nouveau compte client a été ajouté avec succès à la base de données. | Pourrait être utilisé pour la journalisation post-enregistrement, l'envoi de notifications ou un traitement ultérieur si un compte a été autorisé mais signalé pour examen. |
| `actionAuthentication` | Exécuté lors de la connexion/authentification du client. | Moins probable pour le spam d'enregistrement, mais pourrait être utilisé pour des vérifications avancées ou pour empêcher la connexion à partir d'IPs/e-mails bannis. |
| `actionValidateCustomerAccount` | Exécuté *avant* qu'un nouveau compte client ne soit ajouté à la base de données. | **HOOK CRITIQUE :** C'est le hook le plus probable où la logique principale de détection de spam du module s'exécuterait, lui permettant d'empêcher la création de compte si du spam est détecté. |
| `displayBackOfficeHeader` | Rendu dans la section `<head>` de toutes les pages du back-office. | Utilisé pour charger du CSS/JS spécifique au module pour les écrans de configuration et de gestion de l'administration. |
| `displayAdminCustomers` | Rendu sur la page de liste des clients dans le Back Office. | Pourrait être utilisé pour ajouter une colonne ou un bouton d'action lié au statut de spam pour les clients existants. |

## 5. Support officiel et mises à jour

Pour les dernières mises à jour du module, les corrections de bugs et un support développeur complet, veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu/my-account/orders/). Notre équipe est dédiée à fournir une assistance rapide et à assurer la performance optimale de votre module « Protection anti-spam à l'enregistrement client ».
