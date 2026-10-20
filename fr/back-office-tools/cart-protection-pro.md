---
title: "Cart protection pro - Manuel du Marchand & Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop Cart protection pro par MyPresta.eu."
sidebar:
  label: "Cart protection pro - Manuel du Marchand & Guide de Configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Cart protection pro sur MyPresta.eu](https://mypresta.eu/modules/administration-tools/cart-protection-pro.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/back-office-tools/cart-protection-pro/)
>
> ---


# Cart protection pro

## 1. Exigences et Compatibilité

- **Versions PrestaShop prises en charge** : PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilité PHP** : PHP 5.6 - 8.5
- **Exigences d'hébergement** : Les extensions PHP standard (cURL, JSON, OpenSSL) sont généralement requises pour les intégrations d'API externes (comme CleanTalk ou StopForumSpam) si vous choisissez de les activer. La plupart des environnements d'hébergement modernes les fournissent déjà.

## 2. Guide de configuration complet (Chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

C'est le panneau de contrôle principal de « Cart protection pro », où vous définissez comment le module détecte et répond à l'activité de panier suspecte.

#### Paramètres généraux

- **Activé** :

  - **Ce que fait ce paramètre :** C'est l'interrupteur principal du module.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé :* Le module surveille activement l'activité du panier et applique les règles de protection que vous avez choisies.
    - *Lorsqu'il est désactivé :* Le module est inactif et ne protégera pas votre boutique des attaques de faux paniers.
  - **Valeur recommandée :** OUI
  - **Scénario / exemple de marchand :** Gardez toujours cette option activée pour assurer la protection de votre boutique. Désactivez-la uniquement pour le dépannage ou la maintenance.
- **Type de protection** :

  - **Ce que fait ce paramètre :** Détermine la méthode utilisée par le module pour identifier et bloquer les activités suspectes.
  - **Effet de la modification de ce paramètre :**
    - *Lorsque défini sur « Adresse IP » :* Le module suit les tentatives de panier en fonction de l'adresse IP du visiteur. Si une IP dépasse les tentatives autorisées, elle sera bloquée.
    - *Lorsque défini sur « Cookie » :* Le module suit les tentatives de panier à l'aide d'un cookie de navigateur. Si un navigateur (identifié par cookie) dépasse les tentatives, il sera bloqué. C'est moins fiable car les cookies peuvent être effacés.
    - *Lorsque défini sur « Adresse IP + Cookie » :* Combine les deux méthodes pour une protection plus forte. Une IP ou un cookie dépassant les limites déclenchera un blocage.
    - *Lorsque défini sur « CleanTalk » :* Utilise le service anti-spam externe CleanTalk pour vérifier les requêtes. Nécessite une clé API CleanTalk.
    - *Lorsque défini sur « StopForumSpam » :* Utilise la base de données externe StopForumSpam pour vérifier si une IP est connue pour le spam. Nécessite une clé StopForumSpam.
  - **Valeur recommandée :** « Adresse IP + Cookie » pour une protection locale robuste, ou « CleanTalk » / « StopForumSpam » si vous avez des comptes avec ces services pour des vérifications externes avancées.
  - **Scénario / exemple de marchand :** Si vous rencontrez un volume élevé de faux paniers, commencez par « Adresse IP + Cookie ». Si le problème persiste ou si vous souhaitez des vérifications plus avancées, envisagez l'intégration avec CleanTalk ou StopForumSpam.
- **Période** :

  - **Ce que fait ce paramètre :** Définit la durée (en minutes) pendant laquelle le module compte les tentatives de panier provenant d'une seule source (IP ou cookie).
  - **Effet de la modification de ce paramètre :**
    - *Une période plus courte (par exemple, 5 minutes) :* Protection plus agressive. Un utilisateur/bot sera bloqué plus rapidement s'il effectue de nombreuses tentatives en peu de temps.
    - *Une période plus longue (par exemple, 60 minutes) :* Moins agressif. Permet plus de tentatives sur une période plus longue avant le blocage.
  - **Valeur recommandée :** 10 minutes
  - **Scénario / exemple de marchand :** Si les robots créent rapidement des paniers, une période plus courte les détectera plus rapidement. Si vous constatez que des utilisateurs légitimes sont bloqués (rare), vous pouvez légèrement augmenter cette valeur.
- **Nombre de tentatives** :

  - **Ce que fait ce paramètre :** Définit le nombre maximum d'ajouts au panier autorisés à partir d'une seule source (IP ou cookie) dans la « Période » définie avant qu'un blocage ne soit déclenché.
  - **Effet de la modification de ce paramètre :**
    - *Un nombre plus faible (par exemple, 3) :* Très agressif. Un utilisateur/bot sera bloqué après seulement quelques ajouts au panier.
    - *Un nombre plus élevé (par exemple, 10) :* Moins agressif. Permet plus d'ajouts au panier avant le blocage.
  - **Valeur recommandée :** 5
  - **Scénario / exemple de marchand :** Un client normal ajoute rarement plus de 5 articles à son panier en 10 minutes. Les robots, cependant, essaient souvent d'en ajouter des dizaines ou des centaines. Définir cette valeur à 5 aide à faire la distinction.
- **Titre de l'e-mail au marchand** :

  - **Ce que fait ce paramètre :** Spécifie la ligne d'objet de la notification par e-mail qui vous est envoyée (au marchand) lorsqu'un bannissement de protection de panier se produit.
  - **Effet de la modification de ce paramètre :** Modifie la ligne d'objet des e-mails d'alerte que vous recevez.
  - **Valeur recommandée :** « Cart Protection Pro - Alerte de bannissement ! »
  - **Scénario / exemple de marchand :** Personnalisez ceci pour que les alertes soient facilement reconnaissables dans votre boîte de réception, par exemple, « URGENT : Bot bloqué sur [Nom de votre boutique] ».
- **Journaux** :

  - **Ce que fait ce paramètre :** Contrôle si le module enregistre les détails des tentatives de panier et des bannissements dans votre base de données PrestaShop.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé :* Le module stocke un historique de toutes les tentatives et bannissements, que vous pouvez consulter dans les sections « Tentatives » et « Bannissements » du module. C'est crucial pour surveiller et comprendre les attaques.
    - *Lorsqu'il est désactivé :* Aucun journal n'est conservé, ce qui rend plus difficile le suivi ou le dépannage des problèmes.
  - **Valeur recommandée :** OUI
  - **Scénario / exemple de marchand :** Gardez toujours les journaux activés. Ils fournissent des informations précieuses sur les types et la fréquence des attaques auxquelles votre boutique est confrontée, vous aidant à affiner vos paramètres.

#### Intégration CleanTalk

- **Activer le support gratuit CleanTalk** :

  - **Ce que fait ce paramètre :** Active l'intégration avec le service anti-spam CleanTalk pour des vérifications anti-spam en temps réel. CleanTalk propose un plan gratuit pour les vérifications de base.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé :* Le module enverra des requêtes à CleanTalk pour vérifier si une adresse IP ou un e-mail (si disponible) est connu pour le spam avant d'autoriser les ajouts au panier.
    - *Lorsqu'il est désactivé :* Les vérifications CleanTalk ne sont pas effectuées.
  - **Valeur recommandée :** NON (sauf si vous avez un compte CleanTalk et une clé API)
  - **Scénario / exemple de marchand :** Si vous utilisez déjà CleanTalk pour d'autres protections anti-spam (par exemple, commentaires, inscriptions) ou si vous souhaitez une couche supplémentaire de vérification externe, activez cette option.
- **Activer le support payant CleanTalk** :

  - **Ce que fait ce paramètre :** Active l'intégration avec le service anti-spam CleanTalk, spécifiquement pour les fonctionnalités disponibles avec un abonnement payant CleanTalk.
  - **Effet de la modification de ce paramètre :** Similaire au support gratuit, mais potentiellement avec des vérifications plus avancées si votre plan CleanTalk le permet.
  - **Valeur recommandée :** NON (sauf si vous avez un compte CleanTalk payant et une clé API)
  - **Scénario / exemple de marchand :** Choisissez cette option si vous avez un abonnement payant CleanTalk et que vous souhaitez exploiter toutes ses capacités pour la protection du panier.
- **Clé API CleanTalk** :

  - **Ce que fait ce paramètre :** C'est la clé unique fournie par CleanTalk qui authentifie votre boutique auprès de leur service.
  - **Effet de la modification de ce paramètre :** Sans une clé API valide, l'intégration CleanTalk ne fonctionnera pas, même si elle est activée.
  - **Valeur recommandée :** Votre clé API CleanTalk réelle (laissez vide si vous n'utilisez pas CleanTalk).
  - **Scénario / exemple de marchand :** Après vous être inscrit à CleanTalk, vous recevrez une clé API. Saisissez-la ici pour activer leur service.

#### Intégration StopForumSpam

- **Activer le support StopForumSpam** :

  - **Ce que fait ce paramètre :** Active l'intégration avec la base de données StopForumSpam, qui répertorie les adresses IP, les e-mails et les noms d'utilisateur connus pour spammer les forums et les sites web.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé :* Le module interrogera StopForumSpam pour vérifier si l'adresse IP du visiteur est répertoriée comme un spammeur connu.
    - *Lorsqu'il est désactivé :* Les vérifications StopForumSpam ne sont pas effectuées.
  - **Valeur recommandée :** NON (sauf si vous avez une clé StopForumSpam)
  - **Scénario / exemple de marchand :** C'est une bonne couche de protection supplémentaire si vous souhaitez bloquer les adresses IP mondialement reconnues comme spammeurs, même si elles n'ont pas encore déclenché vos limites de panier locales.
- **Clé StopForumSpam** :

  - **Ce que fait ce paramètre :** C'est la clé unique fournie par StopForumSpam qui authentifie votre boutique auprès de leur service.
  - **Effet de la modification de ce paramètre :** Sans une clé valide, l'intégration StopForumSpam ne fonctionnera pas, même si elle est activée.
  - **Valeur recommandée :** Votre clé API StopForumSpam réelle (laissez vide si vous n'utilisez pas StopForumSpam).
  - **Scénario / exemple de marchand :** Après vous être inscrit à StopForumSpam, vous recevrez une clé API. Saisissez-la ici pour activer leur service.

### 2.2 Écrans d'administration dédiés et vues de contrôleur

#### 2.2.1 Cart Protection Pro > Tentatives (Back Office > Modules > Cart Protection Pro > Tentatives)

- **Nom de l'écran et emplacement du menu :** Vous pouvez trouver cet écran en naviguant vers **Modules > Gestionnaire de modules**, puis en cliquant sur « Configurer » sur « Cart protection pro », puis en sélectionnant l'onglet « Tentatives » (ou un élément de menu similaire si le module ajoute son propre menu de niveau supérieur).
- **Actions et paramètres disponibles :** Cet écran affiche une liste (vue en grille) de toutes les tentatives de panier enregistrées qui ont déclenché la journalisation du module. Il affiche des détails tels que :
  - **Adresse IP :** L'adresse IP du visiteur.
  - **ID du cookie :** L'identifiant unique du cookie (si la protection par « Cookie » est activée).
  - **Tentatives :** Le nombre d'ajouts au panier effectués par cette source dans la période configurée.
  - **Horodatage :** Quand la tentative a été enregistrée.
  - **Statut :** Si cela a conduit à un bannissement ou s'il s'agissait simplement d'une tentative.
- **Effet des modifications :** Il s'agit d'un journal en lecture seule. Vous ne pouvez pas modifier directement les tentatives ici. Son but est de fournir de la transparence et des données pour que vous puissiez comprendre les attaques potentielles. Vous pouvez généralement filtrer et trier la liste pour analyser les modèles.
- **Flux de travail recommandé pour la gestion quotidienne de la boutique :** Vérifiez régulièrement ce journal, surtout si vous suspectez une activité de bot. Recherchez des modèles :
  - Nombreuses tentatives depuis la même IP ou le même cookie.
  - Tentatives concentrées sur une courte période.
  - Plages d'IP ou emplacements géographiques inhabituels.
    Ces données vous aident à affiner vos paramètres de « Période » et de « Nombre de tentatives ».

#### 2.2.2 Cart Protection Pro > Bannissements (Back Office > Modules > Cart Protection Pro > Bannissements)

- **Nom de l'écran et emplacement du menu :** Similaire à l'écran des tentatives, celui-ci est accessible via **Modules > Gestionnaire de modules > Configurer « Cart protection pro » > Onglet/élément de menu Bannissements**.
- **Actions et paramètres disponibles :** Cet écran affiche une liste (vue en grille) de toutes les adresses IP ou ID de cookies qui ont été bloqués par le module. Il affiche généralement :
  - **Adresse IP :** L'IP bloquée.
  - **ID du cookie :** Le cookie bloqué (le cas échéant).
  - **Raison :** Pourquoi le bannissement a eu lieu (par exemple, « Trop de tentatives »).
  - **Heure de début/fin du bannissement :** Quand le bannissement a été initié et s'il est temporaire.
  - **Actions :** Inclut souvent des options pour « Débannir » manuellement une entrée.
- **Effet des modifications :**
  - *Débannir une entrée :* Supprime le blocage pour cette IP ou ce cookie spécifique, leur permettant d'accéder à nouveau à la fonctionnalité de votre panier. À utiliser avec prudence !
- **Flux de travail recommandé pour la gestion quotidienne de la boutique :**
  - Examinez périodiquement la liste des bannissements. Si vous remarquez qu'une adresse IP légitime (par exemple, la vôtre ou celle d'un partenaire connu) a été accidentellement bannie, vous pouvez la débannir ici.
  - Recherchez les adresses IP récurrentes ou les modèles de bannissements, ce qui pourrait indiquer des attaques persistantes.
  - Cet écran est crucial pour s'assurer que le module bloque efficacement le trafic malveillant sans affecter involontairement les vrais clients.

### 2.3 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Valeur par défaut / Recommandée | Objectif et impact |
| --- | --- | --- | --- |
| Configuration du module | Activé | OUI | Interrupteur principal pour la fonctionnalité du module. |
| Configuration du module | Type de protection | Adresse IP + Cookie | Méthode pour identifier et bloquer les activités suspectes (IP, Cookie, les deux, CleanTalk, StopForumSpam). |
| Configuration du module | Période | 10 minutes | Durée (minutes) pour le comptage des tentatives de panier. |
| Configuration du module | Nombre de tentatives | 5 | Nombre max d'ajouts au panier dans la période avant un blocage. |
| Configuration du module | Titre de l'e-mail au marchand | Cart Protection Pro - Alerte de bannissement ! | Ligne d'objet pour les e-mails de notification du marchand. |
| Configuration du module | Journaux | OUI | Active/désactive la journalisation des tentatives et des bannissements. |
| Configuration du module | Activer le support gratuit CleanTalk | NON | Active les vérifications anti-spam gratuites de CleanTalk. |
| Configuration du module | Activer le support payant CleanTalk | NON | Active les vérifications anti-spam payantes de CleanTalk. |
| Configuration du module | Clé API CleanTalk | (vide) | Votre clé API CleanTalk unique. |
| Configuration du module | Activer le support StopForumSpam | NON | Active les vérifications de la base de données IP de StopForumSpam. |
| Configuration du module | Clé StopForumSpam | (vide) | Votre clé API StopForumSpam unique. |
| AdminCproAttempts | Vue grille / Gestion | N/A | Affiche un journal de toutes les tentatives de panier. |
| AdminCproBans | Vue grille / Gestion | N/A | Affiche une liste de toutes les IP/cookies bloqués, avec option de débannissement. |

## 3. Dépannage pour les marchands et questions fréquemment posées (FAQ)

**Q1 : Mes clients se plaignent de ne pas pouvoir ajouter d'articles au panier, mais je ne vois aucun bannissement.**
R1 : Tout d'abord, vérifiez si le module « Cart protection pro » est « Activé » dans sa configuration. Si c'est le cas, naviguez vers la section « Bannissements » dans la configuration du module. Vérifiez si des adresses IP de clients légitimes y sont répertoriées. Si c'est le cas, vous avez peut-être réglé le « Nombre de tentatives » ou la « Période » de manière trop agressive. Essayez d'augmenter légèrement le « Nombre de tentatives » (par exemple, de 3 à 5 ou 7) ou de prolonger la « Période » (par exemple, de 5 à 10-15 minutes). Assurez-vous également que votre thème ou d'autres modules n'interfèrent pas avec le processus du panier.

**Q2 : J'ai configuré CleanTalk/StopForumSpam, mais cela ne semble pas fonctionner.**
R2 : Vérifiez les points suivants :
1. Assurez-vous que « Activer le support CleanTalk/StopForumSpam » est activé.
2. Vérifiez que votre « Clé API CleanTalk » ou « Clé StopForumSpam » est correctement saisie et est active auprès du service respectif. Même une seule faute de frappe l'empêchera de fonctionner.
3. Confirmez que votre environnement d'hébergement autorise les requêtes cURL sortantes, qui sont nécessaires pour communiquer avec ces services externes. Votre hébergeur peut le confirmer.
4. Vérifiez les journaux « Tentatives » et « Bannissements » du module pour toute entrée indiquant un blocage par ces services.

**Q3 : Ma boutique reçoit toujours beaucoup de faux paniers même avec le module activé.**
R3 : Cela pourrait indiquer un bot sophistiqué ou que vos paramètres ne sont pas assez agressifs.
1. **Vérifiez vos paramètres :** Essayez de diminuer le « Nombre de tentatives » (par exemple, de 5 à 3) et/ou de raccourcir la « Période » (par exemple, de 10 à 5 minutes).
2. **Activez les services externes :** Si vous ne l'avez pas déjà fait, envisagez d'activer et de configurer CleanTalk ou StopForumSpam pour une couche de protection supplémentaire.
3. **Vérifiez les conflits :** Désactivez temporairement d'autres modules de sécurité ou de mise en cache pour voir s'il y a un conflit.
4. **Videz le cache :** Parfois, le cache Smarty de PrestaShop peut empêcher les nouveaux paramètres du module de prendre effet immédiatement. Allez dans **Paramètres avancés > Performances** et cliquez sur « Vider le cache ».

**Q4 : Ce module va-t-il ralentir ma boutique ?**
R4 : Le module est conçu pour être léger. Les vérifications primaires (IP/Cookie) sont très rapides. Si vous activez des services externes comme CleanTalk ou StopForumSpam, il y aura un léger délai car votre serveur communique avec leurs API. Cependant, ces services sont optimisés pour la vitesse, et l'impact est généralement négligeable. L'avantage de prévenir la surcharge du serveur due aux faux paniers l'emporte largement sur tout temps de traitement minimal.

**Q5 : Comment traduire le titre de l'e-mail ou d'autres textes du module ?**
R5 : Pour le « Titre de l'e-mail au marchand », vous pouvez simplement modifier le texte directement dans la configuration du module. Pour les autres textes du module (s'il y en avait qui étaient visibles pour les clients, ce qui n'est généralement pas le cas de ce module), vous iriez généralement dans **International > Traductions** dans votre Back Office PrestaShop. Sélectionnez « Traductions des modules installés », choisissez votre thème, puis sélectionnez « Cart protection pro » pour trouver et modifier les chaînes traduisibles.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

Cette section fournit une analyse approfondie de la structure technique du module « Cart protection pro », destinée aux développeurs et aux webmasters qui ont besoin de comprendre, de déboguer ou d'étendre ses fonctionnalités.

### 4.1 Vue d'ensemble de l'architecture

Le module « Cart protection pro » suit une architecture de module PrestaShop standard, exploitant principalement les hooks pour sa fonctionnalité principale et des contrôleurs d'administration dédiés pour la gestion du back-office. Il intègre des services anti-spam externes (CleanTalk, StopForumSpam) via des requêtes cURL. La logique du module est encapsulée dans sa classe principale et ses classes d'aide, avec une configuration stockée dans `ps_configuration` et des journaux dans des tables de base de données personnalisées.

### 4.2 Contrôleurs (`controllers/`)

#### Contrôleurs Front-Office

Ce module ne définit pas explicitement de contrôleurs front-office personnalisés. Sa logique front-office est principalement exécutée via des hooks dans le fichier de module principal `cpro.php`, interceptant les actions du panier avant qu'elles ne soient entièrement traitées.

#### Contrôleurs d'administration Back-Office

Ces contrôleurs gèrent les écrans d'administration dédiés du module, fournissant des vues en grille pour les tentatives et les bannissements.

- `cpro/controllers/admin/AdminCproAttempts.php`

  - **Nom de la classe et classe parente** : `AdminCproAttemptsController` étend `ModuleAdminController`.
  - **Responsabilité** : Gère l'affichage et l'interaction pour le journal des « Tentatives » dans le Back Office de PrestaShop. Il récupère les données de la table de base de données `cattempt` et les affiche sous forme de liste, permettant à l'administrateur de visualiser toutes les tentatives de panier enregistrées. Il ne permet pas la modification directe des tentatives, agissant comme un visualiseur de journal en lecture seule.
- `cpro/controllers/admin/AdminCproBans.php`

  - **Nom de la classe et classe parente** : `AdminCproBansController` étend `ModuleAdminController`.
  - **Responsabilité** : Gère l'affichage et l'interaction pour la liste des « Bannissements » dans le Back Office de PrestaShop. Il récupère les données de la table de base de données `cban` et les présente sous forme de liste. Ce contrôleur gère également des actions comme « Débannir », permettant à un administrateur de supprimer une IP ou un cookie spécifique de la liste des bannissements.
- `cpro/controllers/admin/index.php`

  - **Nom de la classe et classe parente** : Ce fichier sert généralement de mesure de sécurité dans PrestaShop, contenant `die('No direct script access');` pour empêcher l'accès direct au répertoire. Il ne contient pas de classe de contrôleur fonctionnelle.

### 4.3 Classes et modèles de base (`classes/`)

Le dossier du module n'indique aucune classe personnalisée dans le répertoire `classes/`. La logique principale pour la gestion des tentatives et des bannissements, y compris les interactions avec la base de données, est probablement gérée directement dans le fichier de module principal `cpro.php` ou via des appels directs à `Db::getInstance()`.

### 4.4 Actifs JavaScript (`views/js/`)

Le dossier du module n'indique aucun fichier JavaScript personnalisé. Tout comportement dynamique dans le back office est probablement géré par le JS de base de PrestaShop ou des scripts en ligne dans les templates.

### 4.5 Feuilles de style CSS (`views/css/`)

Le dossier du module n'indique aucun fichier CSS personnalisé. Le style des écrans du back-office reposera sur le thème d'administration par défaut de PrestaShop.

### 4.6 Structure des templates Smarty (`views/templates/`)

- **Templates d'administration (`views/templates/admin/`)** :
  - `cpro/views/templates/admin/main.tpl`
    - **Objectif** : Ce template est probablement utilisé pour la page de configuration principale du module, rendue par la méthode `getContent()` dans `cpro.php`. Il contient la structure HTML de tous les paramètres décrits dans la section 4.1, y compris les champs de formulaire pour le « Type de protection », la « Période », le « Nombre de tentatives », les clés API et l'interrupteur « Activé ». Il peut également inclure des onglets de navigation ou des liens vers les contrôleurs `AdminCproAttempts` et `AdminCproBans`.

### 4.7 Schéma de la base de données et carte des hooks

- **Tables de la base de données** :

  - `ps_cattempt` : Stocke les journaux des tentatives de panier.
    - `id_cattempt` (Clé primaire)
    - `ip_address` (VARCHAR) : Adresse IP du visiteur.
    - `cookie_id` (VARCHAR) : Identifiant unique du cookie du navigateur.
    - `attempts` (INT) : Nombre d'ajouts au panier.
    - `date_add` (DATETIME) : Horodatage de la tentative.
    - `status` (TINYINT) : Statut, par exemple, 0 pour tentative, 1 pour banni.
  - `ps_cban` : Stocke les enregistrements des IP/cookies bannis.
    - `id_cban` (Clé primaire)
    - `ip_address` (VARCHAR) : Adresse IP bannie.
    - `cookie_id` (VARCHAR) : ID du cookie banni.
    - `reason` (TEXT) : Raison du bannissement (par exemple, « Trop de tentatives »).
    - `date_add` (DATETIME) : Quand le bannissement a été initié.
    - `date_expire` (DATETIME) : Si le bannissement est temporaire.
  - **Enregistrements de configuration (dans `ps_configuration`)** :
    - `CPRO_PTYPE_5` : Paramètre du type de protection (par exemple, IP, Cookie, CleanTalk).
    - `CPRO_CTALK_APIKEY` : Clé API CleanTalk.
    - `CPRO_CTALK` : Support gratuit CleanTalk activé/désactivé.
    - `CPRO_CTALK_PAID` : Support payant CleanTalk activé/désactivé.
    - `CPRO_ATMPT` : Nombre de tentatives autorisées.
    - `CPRO_TIME` : Période en minutes.
    - `CPRO_PTYPE_1`, `CPRO_PTYPE_2`, `CPRO_PTYPE_3`, `CPRO_PTYPE_4` : Drapeaux internes pour les types de protection.
    - `CPRO_SFS` : Support StopForumSpam activé/désactivé.
    - `CPRO_SFS_KEY` : Clé API StopForumSpam.
    - `CPRO_MTITLE` : Titre de l'e-mail pour les notifications du marchand.
    - `CPRO_LOGS` : Journalisation activée/désactivée.
    - `mypresta_updates`, `update_`, `updatev_` : Clés internes pour les mises à jour du module.
- **Table des hooks enregistrés** :

| Nom du hook | Moment d'exécution | Objectif technique |
| --- | --- | --- |
| `actionObjectCartAddAfter` | Après qu'un objet panier a été ajouté/mis à jour dans la base de données. | Potentiellement utilisé pour enregistrer les ajouts de panier réussis ou le post-traitement après l'enregistrement d'un panier. |
| `actionCartSave` | Après qu'un panier a été enregistré (inséré ou mis à jour). | Similaire à `actionObjectCartAddAfter`, utilisé pour surveiller ou enregistrer les modifications du panier. |
| `actionFrontControllerInitBefore` | Avant l'initialisation du contrôleur frontal. | Point d'interception précoce pour vérifier les IP/cookies bannis avant que tout contenu de page ne soit rendu, potentiellement en redirigeant ou en affichant un message de blocage. |
| `actionObjectCartAddBefore` | Avant qu'un objet panier ne soit ajouté/mis à jour dans la base de données. | **CRITIQUE** : C'est le hook principal pour intercepter et valider les ajouts au panier. Le module effectuera ses vérifications (IP, cookie, CleanTalk, StopForumSpam) ici et peut empêcher l'ajout au panier si les limites sont dépassées ou si un bannissement est détecté. |
| `displayHeader` | Dans la section `<head>` des pages du front-office. | Pourrait être utilisé pour injecter le JavaScript nécessaire (bien qu'aucun n'ait été détecté) ou le CSS, ou pour définir des cookies de suivi. |
| `actionDispatcherBefore` | Avant que le dispatcher ne traite la requête. | Un autre point d'interception précoce, similaire à `actionFrontControllerInitBefore`, permettant au module d'effectuer des vérifications et potentiellement de bloquer les requêtes avant qu'elles n'atteignent un contrôleur spécifique. |

### 4.8 Intégrations d'API externes

- **CleanTalk** : Utilise cURL pour envoyer des adresses IP et potentiellement d'autres données à l'API de CleanTalk pour la vérification du spam.
- **StopForumSpam** : Utilise cURL pour interroger la base de données StopForumSpam avec des adresses IP afin de vérifier les spammeurs connus.

## 5. Support officiel et mises à jour

Pour les dernières mises à jour, corrections de bugs et support professionnel pour votre module « Cart protection pro », veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu). Notre équipe est dédiée à assurer le fonctionnement optimal de votre module et la sécurité de votre boutique.
