---
title: "Login protection pro - Manuel du marchand et guide de configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop Login protection pro par MyPresta.eu."
sidebar:
  label: "Login protection pro - Manuel du marchand et guide de configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Login protection pro sur MyPresta.eu](https://mypresta.eu/modules/administration-tools/login-protection-pro.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/back-office-tools/login-protection-pro/)
>
> ---


# Login protection pro

## 1. Exigences et compatibilité

- **Versions de PrestaShop prises en charge :** PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilité PHP :** PHP 5.6 - 8.5
- **Exigences d'hébergement :** Extensions PHP standard (cURL, JSON, OpenSSL).

## 2. Guide de configuration complet (chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

C'est l'écran de configuration principal où vous définissez les règles fondamentales de protection de la connexion.

- **Emplacement du menu :** Back Office > Modules > Gestionnaire de modules > Login protection pro > Configurer

#### Paramètres et options :

1. **Activer la protection de la connexion :**

   - **Ce que fait ce paramètre :** C'est l'interrupteur principal du module. Il active ou désactive l'ensemble du système de protection de la connexion.
   - **Effet de la modification de ce paramètre :**
     - *Lorsqu'il est activé :* Le module commencera à surveiller les tentatives de connexion, en appliquant les règles que vous définissez ci-dessous.
     - *Lorsqu'il est désactivé :* Le module sera inactif, et aucune tentative de connexion ne sera surveillée ou bloquée. Votre boutique s'appuiera sur la sécurité par défaut de PrestaShop, qui n'inclut pas la protection contre la force brute.
   - **Valeur recommandée :** **OUI**
   - **Scénario / exemple de marchand :** Gardez toujours cette option activée pour assurer la protection de votre boutique. Désactivez-la uniquement pour un débogage spécifique si le support vous le demande.
2. **Nombre maximal de tentatives échouées :**

   - **Ce que fait ce paramètre :** Définit le nombre maximal de tentatives de connexion incorrectes autorisées depuis une seule adresse IP dans un laps de temps spécifique (défini par « Fenêtre de temps de tentative ») avant que cette IP ne soit temporairement bloquée.
   - **Effet de la modification de ce paramètre :**
     - *Définir un nombre inférieur (par exemple, 3) :* Rend la protection plus agressive, bloquant les IP suspectes plus rapidement. Cela pourrait accidentellement bloquer des utilisateurs légitimes qui oublient réellement leur mot de passe plusieurs fois.
     - *Définir un nombre supérieur (par exemple, 10) :* Rend la protection moins agressive, permettant plus de tentatives échouées. Cela réduit le risque de bloquer des utilisateurs légitimes mais donne plus d'essais aux pirates.
   - **Valeur recommandée :** **5**
   - **Scénario / exemple de marchand :** Si vous remarquez que de nombreux clients légitimes sont bloqués, vous pourriez augmenter ce nombre. Si vous voyez beaucoup de tentatives de force brute dans vos journaux, vous pourriez le diminuer. 5 est un bon équilibre.
3. **Fenêtre de temps de tentative (minutes) :**

   - **Ce que fait ce paramètre :** Spécifie la durée (en minutes) pendant laquelle le compte « Nombre maximal de tentatives échouées » est actif. Si une IP effectue `Nombre maximal de tentatives échouées` dans cette fenêtre, elle est bloquée. Après cette fenêtre, le compte est réinitialisé.
   - **Effet de la modification de ce paramètre :**
     - *Définir une fenêtre plus courte (par exemple, 5 minutes) :* Une IP doit effectuer le `Nombre maximal de tentatives échouées` très rapidement pour être bloquée. C'est bon pour les attaques par force brute rapides.
     - *Définir une fenêtre plus longue (par exemple, 60 minutes) :* Une IP peut effectuer `Nombre maximal de tentatives échouées` sur une période plus longue pour être bloquée. Cela attrape les attaques plus lentes et plus distribuées, mais pourrait également bloquer des utilisateurs légitimes qui essaient de se connecter, sont distraits et réessayent plus tard.
   - **Valeur recommandée :** **15**
   - **Scénario / exemple de marchand :** Une fenêtre de 15 minutes est généralement suffisante pour attraper les attaques automatisées sans pénaliser indûment un utilisateur humain qui pourrait essayer de se souvenir de son mot de passe pendant quelques minutes.
4. **Durée du bannissement (minutes) :**

   - **Ce que fait ce paramètre :** Détermine combien de temps une adresse IP reste bloquée une fois qu'elle a dépassé le `Nombre maximal de tentatives échouées` dans la `Fenêtre de temps de tentative`.
   - **Effet de la modification de ce paramètre :**
     - *Définir une durée plus courte (par exemple, 30 minutes) :* L'IP est débloquée plus tôt. C'est moins perturbant pour les utilisateurs légitimes qui auraient pu être accidentellement bloqués, mais donne aux pirates une nouvelle tentative plus rapide.
     - *Définir une durée plus longue (par exemple, 1440 minutes = 24 heures) :* L'IP reste bloquée pendant une période significative. C'est très efficace contre les attaques automatisées mais peut être frustrant pour les utilisateurs légitimes qui sont bloqués.
   - **Valeur recommandée :** **60** (1 heure)
   - **Scénario / exemple de marchand :** Un bannissement de 60 minutes est généralement suffisant pour dissuader les bots automatisés, car ils passeront probablement à autre chose. Pour un humain, cela offre une période de repos raisonnable.
5. **Protéger la connexion administrateur :**

   - **Ce que fait ce paramètre :** Cet interrupteur applique spécifiquement les règles de protection de la connexion à la page de connexion du Back Office (panneau d'administration) de PrestaShop.
   - **Effet de la modification de ce paramètre :**
     - *Lorsqu'il est activé :* Votre page de connexion administrateur est protégée. Si un attaquant essaie de deviner votre mot de passe administrateur trop de fois, son IP sera bloquée.
     - *Lorsqu'il est désactivé :* Seules les tentatives de connexion client sont surveillées. Votre page de connexion administrateur reste vulnérable aux attaques par force brute.
   - **Valeur recommandée :** **OUI**
   - **Scénario / exemple de marchand :** Il est absolument essentiel de protéger votre connexion administrateur, car un accès non autorisé ici peut compromettre l'ensemble de votre boutique. Gardez toujours cette option activée.
6. **Protéger la connexion client :**

   - **Ce que fait ce paramètre :** Cet interrupteur applique spécifiquement les règles de protection de la connexion à la page de connexion client (front office).
   - **Effet de la modification de ce paramètre :**
     - *Lorsqu'il est activé :* Les tentatives de connexion client sont protégées. Si un attaquant essaie de deviner les mots de passe des clients, son IP sera bloquée.
     - *Lorsqu'il est désactivé :* Seules les tentatives de connexion administrateur sont surveillées. Les comptes clients restent vulnérables aux attaques par force brute.
   - **Valeur recommandée :** **OUI**
   - **Scénario / exemple de marchand :** La protection des comptes clients est vitale pour la sécurité des données et le maintien de la confiance des clients. Gardez toujours cette option activée.

#### Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Par défaut / Recommandé | Objectif et impact |
| --- | --- | --- | --- |
| Config du module | Activer la protection de la connexion | OUI | Interrupteur principal pour la fonctionnalité du module. **Toujours OUI.** |
| Config du module | Nombre maximal de tentatives échouées | 5 | Nombre de connexions incorrectes avant qu'une IP ne soit bloquée. |
| Config du module | Fenêtre de temps de tentative (minutes) | 15 | Durée sur laquelle les tentatives échouées sont comptées. |
| Config du module | Durée du bannissement (minutes) | 60 | Combien de temps une IP bloquée reste bannie. |
| Config du module | Protéger la connexion administrateur | OUI | Applique la protection à la connexion du Back Office. **Toujours OUI.** |
| Config du module | Protéger la connexion client | OUI | Applique la protection à la connexion client du Front Office. **Toujours OUI.** |

### 2.2 Écrans d'administration dédiés et vues de contrôleur

Le module fournit deux écrans dédiés dans votre Back Office PrestaShop pour gérer et examiner les tentatives de connexion et les bannissements.

#### 2.2.1 AdminLproAttemptsController : Journal des tentatives de connexion

Cet écran vous permet de visualiser un journal détaillé de toutes les tentatives de connexion échouées enregistrées par le module.

- **Nom de l'écran et emplacement du menu :** Back Office > Modules > Login Protection Pro > **Tentatives de connexion** (ou similaire, selon la version de PrestaShop et la personnalisation du menu).
- **Actions et paramètres disponibles :**
  - **Tableau de liste :** Vous verrez un tableau affichant :
    - **Adresse IP :** L'adresse IP d'où provient la tentative échouée.
    - **Heure de la tentative :** La date et l'heure exactes de la tentative échouée.
    - **Type de connexion :** S'il s'agissait d'une tentative de connexion 'Admin' ou 'Client'.
    - **Nom d'utilisateur/Email :** Le nom d'utilisateur ou l'adresse e-mail qui a été tentée.
    - **Statut :** Indique si la tentative a conduit à un bannissement ou était simplement une tentative échouée.
  - **Filtrage et tri :** Vous pouvez généralement filtrer par adresse IP, type de connexion ou plage de dates pour trouver des tentatives spécifiques.
  - **Aucune action directe :** Cet écran est principalement destiné à la surveillance et à l'examen. Vous ne pouvez pas directement bannir ou débannir des IP à partir d'ici, mais cela vous aide à identifier des schémas suspects.
- **Effet des modifications :** La consultation de ce journal vous aide à comprendre la fréquence et la source des attaques. Si vous remarquez qu'une adresse IP particulière effectue de nombreuses tentatives, vous pouvez l'ajouter manuellement à la liste des bannissements via l'écran « IP bannies ».
- **Flux de travail recommandé pour la gestion quotidienne de la boutique :** Vérifiez régulièrement ce journal, surtout si vous suspectez une attaque ou si des clients signalent des problèmes de connexion. Recherchez des schémas de tentatives échouées répétées depuis la même IP ou plage d'IP.

#### 2.2.2 AdminLproBansController : Gestion des IP bannies

Cet écran vous permet de visualiser, d'ajouter et de supprimer des adresses IP de la liste de bannissement du module.

- **Nom de l'écran et emplacement du menu :** Back Office > Modules > Login Protection Pro > **IP bannies** (ou similaire, selon la version de PrestaShop et la personnalisation du menu).
- **Actions et paramètres disponibles :**
  - **Tableau de liste :** Affiche toutes les adresses IP actuellement bannies, y compris :
    - **Adresse IP :** L'IP bloquée.
    - **Raison du bannissement :** (Le cas échéant, par exemple, « Bannissement automatique en raison de tentatives échouées »).
    - **Heure de début du bannissement :** Quand le bannissement a été initié.
    - **Heure de fin du bannissement :** Quand le bannissement est censé expirer (si temporaire).
    - **Actions :** Inclut généralement une option pour « Supprimer » ou « Débannir » une IP spécifique.
  - **Bouton « Ajouter une nouvelle IP » :** Vous permet d'ajouter manuellement une adresse IP à la liste de bannissement. Ceci est utile si vous identifiez une IP malveillante à partir de vos journaux de serveur ou de l'écran « Tentatives de connexion » qui n'a pas encore été automatiquement bannie.
    - Lors de l'ajout, vous pourrez peut-être spécifier l'IP, une raison et une heure d'expiration facultative pour le bannissement.
- **Effet des modifications :**
  - *Ajout d'une IP :* Bloque immédiatement toutes les tentatives de connexion depuis cette adresse IP pour la durée spécifiée (ou de manière permanente si aucune durée n'est définie).
  - *Suppression d'une IP :* Débloque l'adresse IP, permettant à nouveau les tentatives de connexion depuis celle-ci. Utilisez cette option avec prudence, en vous assurant que vous ne débloquez pas un attaquant connu.
- **Flux de travail recommandé pour la gestion quotidienne de la boutique :**
  - Examinez cette liste périodiquement.
  - Si un client légitime signale qu'il ne peut pas se connecter et que vous avez confirmé son adresse IP (par exemple, en lui demandant de visiter un site « quelle est mon IP »), vous pouvez temporairement débannir son IP ici.
  - Si vous identifiez une menace persistante, vous pouvez ajouter manuellement son IP pour vous assurer qu'elle reste bloquée.

#### 2.2.3 index.php (lpro/controllers/admin/index.php)

Ce fichier sert généralement de marqueur de position ou de redirigeur dans le répertoire des contrôleurs d'administration. Dans PrestaShop, les fichiers `index.php` dans les répertoires de contrôleurs empêchent souvent la liste directe des répertoires ou agissent comme un point d'entrée par défaut si aucun contrôleur spécifique n'est demandé. Il ne représente pas un écran configurable ou une entité gérée en soi.

## 3. Dépannage marchand et questions fréquemment posées (FAQ)

**Q1 : Mes clients se plaignent de ne pas pouvoir se connecter, mais ils utilisent le bon mot de passe. Que dois-je faire ?**
R1 : Cela est probablement dû au fait que le module bloque leur adresse IP après trop de tentatives échouées (peut-être d'une session précédente ou d'un réseau partagé).
1. Demandez au client son adresse IP actuelle (il peut la trouver en cherchant « quelle est mon IP » sur Google).
2. Allez dans **Back Office > Modules > Login Protection Pro > IP bannies**.
3. Recherchez son adresse IP dans la liste.
4. Si elle est trouvée, supprimez/débannissez son IP.
5. Conseillez au client d'essayer de se connecter à nouveau. Vous pouvez également lui suggérer de réinitialiser son mot de passe.

**Q2 : Je suis bloqué de mon propre panneau d'administration ! Comment puis-je retrouver l'accès ?**
R2 : Cela peut arriver si vous avez fait trop de tentatives échouées.
1. Si vous avez un accès FTP à votre boutique, vous pouvez temporairement désactiver le module. Allez dans `modules/lpro/` et renommez le fichier `index.php` (par exemple, en `index.php.bak`). Cela désactivera le module.
2. Connectez-vous à votre panneau d'administration.
3. Allez dans **Modules > Gestionnaire de modules**, trouvez « Login protection pro », et cliquez sur « Configurer ».
4. Allez dans **IP bannies** et supprimez votre adresse IP de la liste.
5. Renommez `index.php.bak` en `index.php` dans le répertoire `modules/lpro/`.
6. Réactivez le module si vous l'avez désactivé dans le gestionnaire de modules.
7. Ajustez les paramètres `Nombre maximal de tentatives échouées` ou `Durée du bannissement` si vous vous retrouvez fréquemment bloqué.

**Q3 : Le module ne semble pas bloquer les IP, même après de nombreuses tentatives échouées. Qu'est-ce qui pourrait ne pas aller ?**
R3 :
1. **Vérifiez « Activer la protection de la connexion » :** Assurez-vous que l'interrupteur principal dans la configuration du module est réglé sur **OUI**.
2. **Vérifiez « Protéger la connexion administrateur » / « Protéger la connexion client » :** Assurez-vous que la protection pertinente (administrateur ou client) est activée.
3. **Examinez les paramètres :** Vérifiez que `Nombre maximal de tentatives échouées`, `Fenêtre de temps de tentative` et `Durée du bannissement` sont définis sur des valeurs raisonnables. Si la `Fenêtre de temps de tentative` est trop courte, ou `Nombre maximal de tentatives échouées` est trop élevé, il pourrait falloir une attaque très agressive pour déclencher un bannissement.
4. **Videz le cache :** Allez dans **Paramètres avancés > Performances** et cliquez sur « Vider le cache ». Parfois, les paramètres du module ne s'appliquent pas immédiatement en raison de la mise en cache.
5. **Vérifiez les journaux du serveur :** Les journaux d'accès au serveur de votre hébergeur pourraient montrer si le module rencontre des erreurs PHP.

**Q4 : Ce module va-t-il ralentir ma boutique ?**
R4 : Le module est conçu pour être léger. Il n'effectue des vérifications que lors des tentatives de connexion, qui sont relativement peu fréquentes par rapport aux vues de page. L'impact sur les performances devrait être négligeable. Si vous remarquez un ralentissement, assurez-vous que votre installation PrestaShop et votre serveur répondent aux exigences minimales.

**Q5 : Comment traduire les messages du module dans d'autres langues ?**
R5 : Bien que ce module fonctionne principalement en arrière-plan, tous les messages potentiels du front-office (comme « Trop de tentatives échouées ») ou les étiquettes du back-office peuvent être traduits :
1. Allez dans **International > Traductions** dans votre Back Office PrestaShop.
2. Sélectionnez « Traductions des modules installés ».
3. Choisissez votre thème.
4. Sélectionnez la langue que vous souhaitez traduire.
5. Trouvez le module « Login protection pro » et traduisez les chaînes de texte pertinentes.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

Cette section fournit une exploration approfondie de la structure technique du module « Login protection pro » pour les développeurs et les webmasters.

### 4.1 Vue d'ensemble de l'architecture

Le module `Login protection pro` suit une architecture de module PrestaShop standard, exploitant principalement les contrôleurs d'administration pour son interface de gestion et les hooks pour sa fonctionnalité principale. Il n'introduit pas de contrôleurs front-office complexes ou de classes `ObjectModel` personnalisées, s'appuyant plutôt sur la classe `Configuration` de PrestaShop pour les paramètres et l'interaction directe avec la base de données pour l'enregistrement des tentatives et la gestion des bannissements. La logique du module pour détecter et bloquer les tentatives est injectée via les hooks PrestaShop, spécifiquement autour du processus d'authentification.

### 4.2 Contrôleurs (`controllers/`)

#### Contrôleurs Front-Office

Le module ne contient **pas** de contrôleurs front-office dédiés. Toute la logique liée au front-office (surveillance des tentatives de connexion client) est gérée directement dans le fichier principal du module (`lpro/index.php`) en s'accrochant au processus d'authentification de PrestaShop.

#### Contrôleurs d'administration Back-Office

Le module fournit des contrôleurs d'administration dédiés pour gérer les tentatives de connexion et les bannissements.

- **`controllers/admin/AdminLproAttempts.php`**

  - **Nom de la classe :** `AdminLproAttemptsController` (étend `ModuleAdminController`)
  - **Responsabilité :** Ce contrôleur est responsable de l'affichage d'une liste de toutes les tentatives de connexion échouées enregistrées. Il fournit une vue en grille en lecture seule des données `lattempt`, permettant aux administrateurs de surveiller les activités suspectes. Il utilise généralement `HelperList` pour le rendu du tableau.
  - **Entité gérée :** `lattempt` (représente un enregistrement de tentative de connexion échouée).
  - **Nom de l'onglet :** Tentatives de connexion (visible sous l'entrée de menu principale du module).
- **`controllers/admin/AdminLproBans.php`**

  - **Nom de la classe :** `AdminLproBansController` (étend `ModuleAdminController`)
  - **Responsabilité :** Ce contrôleur gère la liste des adresses IP bannies. Il fournit une vue en grille des données `lban` et permet aux administrateurs d'ajouter de nouveaux bannissements, de modifier ceux existants et de supprimer (débannir) des IP. Il utilise probablement `HelperList` pour le tableau et `HelperForm` pour les formulaires d'ajout/édition.
  - **Entité gérée :** `lban` (représente un enregistrement d'adresse IP bannie).
  - **Nom de l'onglet :** IP bannies (visible sous l'entrée de menu principale du module).
- **`controllers/admin/index.php`**

  - **Chemin exact du fichier :** `lpro/controllers/admin/index.php`
  - **Nom de la classe et classe parente :** Pas un fichier de classe.
  - **Responsabilité :** Il s'agit d'un fichier de remplacement PrestaShop standard. Son objectif principal est d'empêcher la liste des répertoires si la configuration du serveur web le permet, et parfois il peut contenir une simple redirection ou une vérification de sécurité. Il ne contient aucune logique fonctionnelle pour le module lui-même.

### 4.3 Classes et modèles principaux (`classes/`)

Le module ne contient **pas** de classes personnalisées dans le répertoire `classes/`. Il gère probablement les interactions avec la base de données directement dans le fichier principal du module (`lpro/index.php`) ou ses contrôleurs d'administration, en utilisant les méthodes de requête de base de données standard de PrestaShop. Cela implique que les entités `lattempt` et `lban` sont gérées sans classes `ObjectModel` dédiées, en s'appuyant sur des requêtes SQL directes ou des appels `Db::getInstance()`.

### 4.4 Actifs JavaScript (`views/js/`)

Le module ne contient **pas** de fichiers JavaScript personnalisés. Cela suggère que ses interfaces de configuration et de gestion reposent entièrement sur les bibliothèques et comportements JavaScript par défaut de PrestaShop (par exemple, pour la soumission de formulaires, le filtrage de tableaux).

### 4.5 Feuilles de style CSS (`views/css/`)

Le module ne contient **pas** de fichiers CSS personnalisés. Cela indique que ses interfaces Back Office (configuration, journaux de tentatives, listes de bannissements) héritent directement du style du thème du Back Office de PrestaShop, garantissant une apparence cohérente sans introduire d'éléments visuels personnalisés.

### 4.6 Structure des templates Smarty (`views/templates/`)

- **Templates d'administration (`views/templates/admin/`)** :
  - **`lpro/views/templates/admin/main.tpl`** :
    - **Objectif :** Ce template est probablement utilisé pour la page de configuration principale du module, rendue par la méthode `getContent()` dans `lpro/index.php`. Il contient la structure HTML pour les paramètres décrits dans la section 4.1 (Activer la protection de la connexion, Nombre maximal de tentatives échouées, etc.). Il inclurait généralement des éléments de formulaire (interrupteurs, champs de saisie) et potentiellement des liens vers les contrôleurs `AdminLproAttempts` et `AdminLproBans`.

### 4.7 Schéma de la base de données et carte des hooks

#### Tables de la base de données

Le module crée des tables de base de données personnalisées lors de sa méthode `install()` (définie dans `lpro/index.php`).

- **`ps_lpro_attempt`** :
  - **Objectif :** Stocke les enregistrements de toutes les tentatives de connexion échouées.
  - **Champs probables :**
    - `id_lpro_attempt` (Clé primaire)
    - `ip_address` (VARCHAR) : L'adresse IP de la tentative échouée.
    - `attempt_time` (DATETIME) : Horodatage de la tentative.
    - `login_type` (VARCHAR) : 'admin' ou 'customer'.
    - `username` (VARCHAR) : Le nom d'utilisateur/email tenté.
    - `is_banned` (TINYINT) : Indicateur si cette tentative a conduit à un bannissement.
- **`ps_lpro_ban`** :
  - **Objectif :** Stocke les enregistrements des bannissements d'IP actuellement actifs.
  - **Champs probables :**
    - `id_lpro_ban` (Clé primaire)
    - `ip_address` (VARCHAR) : L'adresse IP bannie.
    - `ban_start_time` (DATETIME) : Quand le bannissement a commencé.
    - `ban_end_time` (DATETIME) : Quand le bannissement est censé expirer (NULL pour les bannissements permanents).
    - `reason` (TEXT) : Raison facultative du bannissement.
    - `is_permanent` (TINYINT) : Indicateur pour les bannissements permanents.

#### Tableau des hooks enregistrés

Le module enregistre des hooks pour intercepter les tentatives de connexion et appliquer sa logique de protection.

| Nom du hook | Moment d'exécution | Objectif technique |
| --- | --- | --- |
| `actionAuthentication` | Après qu'un client tente de se connecter (front office). | Vérifie si la tentative de connexion client a réussi ou échoué. Si elle a échoué, enregistre la tentative et vérifie les conditions de bannissement. |
| `actionAdminLoginController` | Après qu'un administrateur tente de se connecter (back office). | Vérifie si la tentative de connexion admin a réussi ou échoué. Si elle a échoué, enregistre la tentative et vérifie les conditions de bannissement. |
| `displayHeader` | Dans la section `<head>` de chaque page du front-office. | Potentiellement utilisé pour inclure du CSS/JS (bien qu'aucun ne soit présent) ou pour des vérifications précoces, bien que moins probable pour la logique principale. Plus souvent pour l'initialisation générale du module. |
| `displayRightColumn` | Dans la colonne de droite des pages du front-office. | Non directement pertinent pour la logique de sécurité. S'il est utilisé, ce serait pour afficher un message ou un bloc, ce qui est peu probable pour ce module. |
| `displayLeftColumn` | Dans la colonne de gauche des pages du front-office. | Identique à `displayRightColumn`. |
| `displayFooter` | Dans le pied de page de chaque page du front-office. | Non directement pertinent pour la logique de sécurité. |
| `displayProductExtraContent` | Sur la page produit, dans la section « contenu supplémentaire ». | Non directement pertinent pour la logique de sécurité. |

**Remarque sur les Hooks :** La logique principale pour détecter et bloquer les tentatives résidera principalement dans les hooks `actionAuthentication` et `actionAdminLoginController`. D'autres hooks `display` sont probablement enregistrés par défaut mais ne sont pas activement utilisés pour la fonctionnalité de sécurité principale du module.

## 5. Support officiel et mises à jour

Pour les dernières mises à jour du module, les corrections de bugs et le support officiel, veuillez vous connecter à votre compte client sur [MyPresta.eu](https://mypresta.eu/my-account/orders/). Notre équipe de support est disponible pour vous aider avec toutes les questions ou problèmes que vous pourriez avoir concernant le module « Login protection pro ».
