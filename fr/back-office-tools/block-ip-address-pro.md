---
title: Ban IP Pro - documentation et manuel utilisateur
sidebar:
  label: Ban IP Pro - documentation et manuel utilisateur
description: Manuel de configuration et de dépannage pour les boutiques qui ont déjà Ban IP Pro.
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Block IP address Pro sur MyPresta.eu](https://mypresta.eu/modules/administration-tools/block-ip-address-pro.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/back-office-tools/block-ip-address-pro/)
>
> ---


## 1. Exigences

Ban IP Pro tourne dans PrestaShop. Il n'a pas besoin d'un autre module.

Les libellés du module à l'écran sont en anglais. Ce manuel les reprend tels qu'ils apparaissent dans le back-office.

- PrestaShop 1.7.1.0 jusqu'à PrestaShop 9.
- PHP 7.1 ou plus récent, et au moins la version de PHP exigée par cette version de PrestaShop. L'installation s'arrête si PHP est plus ancien que 7.1.
- La recherche de pays et le blocage par pays demandent PHP 7.2 ou plus récent, et un fichier pays MaxMind que vous téléversez vous-même. Les bannissements, la liste d'autorisation, le contrôle des connexions et la limite de requêtes fonctionnent sans ce fichier, y compris sous PHP 7.1.
- Aucune extension PHP supplémentaire n'est requise. Le contrôle de mise à jour utilise cURL quand le serveur l'a. Sans cURL, le contrôle lit l'adresse seulement si le serveur autorise les lectures distantes.
- Aucun autre module n'est requis. Un compte MaxMind n'est utile que si vous voulez le fichier pays. Le module ne télécharge pas ce fichier.
- Un import accepte jusqu'à 5000 lignes et un fichier jusqu'à 2 Mo. Une longue liste de règles est lue dans un fichier de cache à chaque visite, donc une très longue liste grossit ce fichier. Après un gros import, utilisez **Rebuild cache** dans **Tools** si les compteurs semblent en retard.

## 2. Installation

1. Dans le back-office, ouvrez **Modules**, puis **Gestionnaire de modules**.
2. Téléversez le zip du module et cliquez sur **Installer**.
3. Ouvrez **Configurer** sur **Ban IP pro**. La page s'ouvre sur **Dashboard**. La barre contient aussi **Statistics**, **Behavior**, **Automation**, **Network**, **Tools** et **Updates**.
4. Le menu de gauche gagne **Ban IP** sous **Paramètres avancés**. Cette page est la liste des règles. **Manage rules** sur la page du module mène à la même liste.

L'installation écrit un cache de règles vide. Elle ne vide pas le cache PrestaShop. Si l'entrée de menu manque après une mise à jour, ouvrez **Configurer** une fois. La page met à jour les tables du module. Si cette mise à jour échoue, la page affiche **The module database could not be updated.**

Pour couper le module, utilisez l'interrupteur du **Gestionnaire de modules**. Les contrôles s'arrêtent. Les règles, les journaux et les réglages restent. Rallumez le module et les mêmes règles sont utilisées. Le module n'a pas de bouton activer ou désactiver qui lui soit propre.

Pour le retirer, cliquez sur **Désinstaller** et confirmez. La désinstallation retire l'entrée **Ban IP** et décroche les contrôles. Les règles, le journal des blocages, les totaux journaliers, les compteurs d'échecs de connexion, la liste des actions du personnel et les réglages restent dans la base. Le fichier pays téléversé reste dans le dossier du module. Une nouvelle installation conserve ces règles et ne remplit que les réglages encore vides.

## 3. Configuration et travail quotidien

Un visiteur ouvre la boutique. Avant que la page soit construite, le module lit son adresse IP. Une règle Allow l'emporte sur un bannissement. Si un bannissement correspond à la boutique, si le pays du visiteur est sur la liste, si le visiteur a ouvert un chemin de sonde, ou si l'adresse a dépassé la limite de requêtes, le visiteur voit la page de blocage ou la redirection que vous avez fixée. Le blocage est écrit dans le journal. Le travail du personnel commence sur **Dashboard** ou dans **Paramètres avancés**, **Ban IP**. Vous ajoutez une règle, vous importez une liste, ou vous laissez **Automation** créer des bannissements. Un bannissement peut expirer. À la première requête de chaque jour, les règles expirées sont coupées et les vieilles lignes du journal sont retirées. Le parcours se termine quand le visiteur est bloqué, redirigé ou laissé passer.

Ouvrez **Modules**, **Gestionnaire de modules**, **Ban IP pro**, **Configurer**.

### 3.1 Dashboard

![Dashboard](https://mypresta.eu/docs/images/docs/banippro-configure-dashboard.webp)

L'écran est en anglais. Dans ce manuel, cette partie s'appelle **Dashboard**.

**Dashboard** est le premier onglet. **Manage rules** ouvre la liste des règles.

Les sept compteurs n'affichent que des nombres. Ils n'enregistrent aucun réglage.

| Champ | Au départ | Effet |
|---|---|---|
| **Manage rules** | un bouton | Ouvre **Ban IP** sous **Paramètres avancés**. |
| **Active bans** | 0 | Règles de bannissement encore actives. Les règles Allow n'entrent pas dans ce nombre. |
| **Blocked today** | 0 | Requêtes bloquées depuis minuit, à partir des totaux journaliers. |
| **Blocked in 7 days** | 0 | Requêtes bloquées sur les 7 derniers jours, aujourd'hui compris. |
| **Blocked in 30 days** | 0 | Requêtes bloquées sur les 30 derniers jours, aujourd'hui compris. |
| **Unique IPs today** | 0 | Adresses IP distinctes dans le journal du jour. |
| **Expiring in 48 hours** | 0 | Bannissements actifs dont la fin tombe dans les 48 prochaines heures. |
| **Active automatic bans** | 0 | Bannissements actifs pour un échec de connexion, un chemin de sonde ou la limite de requêtes. |

**Blocked requests** est un graphique des 30 derniers jours. Il lit les totaux journaliers. Il n'enregistre rien.

**Recent blocks** liste les dernières requêtes bloquées : date, adresse IP, pays, chemin et motif. Le pays reste vide tant que vous n'avez pas téléversé le fichier pays dans **Network**. Une liste vide dit **No blocked requests yet.**

**Your current IP** montre l'adresse que voit ce back-office. **Add to allow list** enregistre cette adresse comme règle Allow pour la boutique et le back-office. La page dit alors **Your current IP address is on the allow list.** Si l'adresse ne peut pas être lue, la page dit **Your current IP address could not be detected.** Si la ligne ne peut pas être enregistrée, elle dit **The address could not be added to the allow list.**

**Module status** montre quatre lignes.

| Ligne | Au départ | Effet |
|---|---|---|
| **Front hook** | **Registered** après une installation normale | **Registered** signifie que la boutique exécute le contrôle. **Missing** signifie que le contrôle n'est pas accroché. Réinstallez le module ou ouvrez **Configurer** après une mise à jour. |
| **Cached rules** | 0 | Combien de règles actives le cache a acceptées. |
| **Unreadable rules** | 0 | Lignes actives que le cache n'a pas pu lire comme une adresse. |
| PHP et PrestaShop | les versions de ce serveur | Pour les comparer aux exigences. |

**Quick ban** écrit un bannissement. La portée est celle de **Default scope of new bans** dans **Behavior**. Un bannissement ajouté ici n'envoie pas le courriel d'alerte.

| Champ | Au départ | Effet |
|---|---|---|
| **IP address** | vide | Une adresse, un motif comme `192.168.1.*`, un réseau comme `10.0.0.0/8`, ou une plage comme `192.168.1.10-192.168.1.20`. |
| **Reason** | **Manual** | **Manual**, **Fraud**, **Spam**, **Scanner**, **Chargeback** ou **Competitor**. Les statistiques utilisent cette étiquette. |
| **Duration** | **Permanent** | **1 hour**, **24 hours**, **7 days**, **30 days**, ou **Permanent** jusqu'à ce que vous supprimiez la règle. |
| **Comment** | vide | Une note privée. Le visiteur ne la voit jamais. |
| **I confirm blocking my own IP** | éteint | Requis seulement quand le bannissement correspondrait à l'IP avec laquelle vous êtes dans le back-office et que la portée inclut le back-office. |
| **Ban this address** | un bouton | Enregistre le bannissement et affiche **The address was banned.** |

**Test an address** ne crée ni ne supprime de règle.

| Champ | Au départ | Effet |
|---|---|---|
| **IP address** | vide | L'adresse que vous voulez vérifier. |
| **Test** | un bouton | Montre le résultat boutique, le résultat back-office et le pays. |
| **Front office** | masqué jusqu'au test | **No matching rule.**, **Allowed by rule #…** ou **Blocked by rule #…**. |
| **Back office** | masqué jusqu'au test | Les trois mêmes résultats pour le panneau. |
| Note sous la ligne back-office | quand la protection est éteinte | **Back office protection is disabled, so back-office bans are not enforced.** |
| **Country** | **Unknown** si le fichier manque | Le code pays, plus **Blocked by country rule** quand ce pays est sur la liste. |

**Recent admin actions** liste les dernières actions du personnel, par exemple création, import, autorisation, déverrouillage et reconstruction du cache. Une liste vide dit **No admin actions yet.**

### 3.2 Statistics

![Statistics](https://mypresta.eu/docs/images/docs/banippro-configure-stats.webp)

L'écran est en anglais. Dans ce manuel, cette partie s'appelle **Statistics**.

**Statistics** lit le journal des blocages. **24h**, **7 days** et **30 days** rechargent la page pour cette période. À la première ouverture, la période est **30 days**.

| Champ | Au départ | Effet |
|---|---|---|
| **24h** | un bouton | Les 24 dernières heures. Le graphique a un point par heure. |
| **7 days** | un bouton | Les 7 derniers jours, aujourd'hui compris. Un point par jour. |
| **30 days** | un bouton, choisi au départ | Les 30 derniers jours, aujourd'hui compris. |
| **Export CSV** | un bouton | Télécharge `banippro-hits.csv` pour la période à l'écran. Ne change pas les règles. |
| **From** | le premier jour de la période ouverte | Utilisé avec **To** et **Apply**. |
| **To** | aujourd'hui | Utilisé avec **From** et **Apply**. Si **From** est après **To**, les deux jours sont échangés. |
| **Apply** | un bouton | Recharge l'onglet pour ces jours. N'enregistre aucun réglage. |
| **Blocked requests** | 0 | Combien de blocages tombent dans la période. |
| **Unique IPs** | 0 | Combien d'adresses distinctes ont été bloquées dans la période. |

Le graphique **Blocked requests** suit les boutons du dessus. En dessous :

| Bloc | Ce qu'il montre |
|---|---|
| **Top IP addresses** | Un graphique en barres des 10 adresses avec le plus de blocages dans la période. |
| **Top paths** | Les 10 chemins les plus souvent bloqués, avec un compte. |
| **Top reasons** | Les 10 motifs des règles correspondantes, avec un compte. |
| **Top countries** | Les 10 codes pays, avec un compte. Vide tant que le fichier pays n'est pas téléversé. |
| **Block log** | Date, adresse IP, pays, chemin, adresse de la règle et motif. Jusqu'à 100 lignes. |

Un détail vide dit **No data for this period.** Un journal vide dit **No blocked requests in this period.**

Les totaux journaliers derrière le graphique du tableau de bord restent quand vous raccourcissez **Keep logs for days**. Ce réglage efface le journal ligne par ligne et la liste des actions du personnel. Il n'efface pas les totaux journaliers.

### 3.3 Behavior

![Behavior](https://mypresta.eu/docs/images/docs/banippro-configure-behavior.webp)

L'écran est en anglais. Dans ce manuel, cette partie s'appelle **Behavior**.

Cliquez sur **Save**. La page affiche **Settings updated**.

| Champ | Au départ | Effet |
|---|---|---|
| **Message for blocked visitors** | **You are blocked** en anglais. Les boutiques en polonais, en espagnol et en portugais reçoivent aussi une phrase dans cette langue. Toute autre langue reçoit la phrase anglaise. | Le texte de la page de blocage. Remplissez chaque langue de la boutique. Le visiteur voit la phrase de la langue de la page. |
| **Redirect blocked visitors** | **No** | **Yes** envoie les visiteurs bloqués vers **Redirect URL** au lieu du message. **No** garde la page de blocage. |
| **Redirect URL** | vide | Un lien `http` ou `https` complet. Ignoré tant que l'interrupteur du dessus est sur **No**. Un mauvais lien remet l'interrupteur sur **No** et affiche **Enter a valid http or https URL for the redirect.** |
| **Default scope of new bans** | **Front office** | Utilisé par **Quick ban** et **Import** quand ces écrans ne demandent pas la portée. **Front office** est la boutique. **Back office** est ce panneau. **Front office and back office** est les deux. |
| **Protect the back office** | **No** | **Yes** applique aussi les bannissements dans ce panneau. L'enregistrement refuse **Yes** tant que votre IP actuelle n'est pas sur la liste d'autorisation, et affiche **Add your current IP to the allow list before you protect the back office.** L'interrupteur reste sur **No**. |

Le formulaire montre aussi cet avis : **Back office protection stays off until your current IP is on the allow list. Rules still apply to the shop front by default.**

### 3.4 Automation

![Automation](https://mypresta.eu/docs/images/docs/banippro-configure-automation.webp)

L'écran est en anglais. Dans ce manuel, cette partie s'appelle **Automation**.

Cliquez sur **Save**. La page affiche **Settings updated**. Les bannissements automatiques s'appliquent à la boutique, pour chaque boutique de l'installation. Ils n'allument pas **Protect the back office**. Une adresse qui correspond déjà à une règle Allow n'est pas bannie. Une adresse qui a déjà un bannissement actif est laissée telle quelle.

| Champ | Au départ | Effet |
|---|---|---|
| **Block known probe paths** | **Yes** | **Yes** bannit un visiteur de la boutique qui ouvre un chemin de la liste ci-dessous. Votre dossier d'administration n'est jamais banni de cette façon. **No** arrête ce contrôle. |
| **Probe ban length in hours** | 24 | Combien de temps ce bannissement dure. 24 est un jour. 0 le garde jusqu'à ce que vous le supprimiez. |
| **Probe paths** | `/.env`, `/wp-login.php`, `/wp-admin`, `/xmlrpc.php`, `/vendor/phpunit`, `/phpmyadmin`, `/.git/`, `/boaform`, `/cgi-bin/`, un par ligne | Une requête dont le chemin contient une de ces lignes est bannie tout de suite. Une liste vide est remplacée par cette liste par défaut à l'enregistrement. Une ligne qui n'est que `/`, et une ligne qui est votre dossier d'administration, sont écartées. |
| **Ban customers after failed logins** | **No** | **Yes** compte les mauvais mots de passe client. Une connexion client réussie remet le compteur à zéro. |
| **Ban employees after failed logins** | **No** | Le même compte pour le formulaire de connexion employé. Mettez votre propre IP sur la liste d'autorisation avant de l'allumer. Le bannissement s'applique à la boutique, pas au panneau, sauf si cette IP est aussi couverte par un bannissement dont la portée inclut le back-office. |
| **Failed logins before a ban** | 5 | Avec 5, le prochain échec dans la fenêtre crée le bannissement. La plus petite valeur enregistrée est 1. |
| **Failed login window in minutes** | 15 | Les échecs plus anciens que cela sont oubliés. La plus petite valeur enregistrée est 1. |
| **Login ban length in hours** | 24 | Combien de temps dure le bannissement de connexion. 0 le garde jusqu'à ce que vous le supprimiez. |
| **Limit requests per IP** | **No** | **Yes** compte les requêtes de pages de la boutique. Les images et les autres fichiers qui n'entrent jamais dans PrestaShop ne sont pas comptés. Laissez **No** pendant un trafic normal. Dans une boutique chargée, une limite basse bannit de vrais clients. |
| **Requests allowed in the window** | 120 | Combien de requêtes de page une IP peut faire pendant la fenêtre. La plus petite valeur enregistrée est 1. |
| **Rate limit window in minutes** | 1 | Durée de cette fenêtre. 1 signifie que la limite ci-dessus est comptée par minute. |
| **Rate limit ban in minutes** | 15 | Combien de minutes dure le bannissement après le dépassement. La plus petite valeur enregistrée est 1. |
| **Email me when an automatic ban is created** | **No** | **Yes** envoie un courriel quand le module crée un bannissement. Les bannissements ajoutés à la main ne l'envoient pas. Au plus un courriel par heure. |
| **Alert email** | vide | La boîte qui reçoit l'alerte. Laissez vide pour utiliser le courriel de la boutique. Une valeur qui n'est pas un courriel est effacée et la page affiche **Enter a valid alert email address.** |

L'objet du courriel est **Ban IP Pro alert**. Le message nomme l'IP, le motif (`auto-login`, `auto-honeypot` ou `auto-rate`), l'heure de fin ou le mot `permanent`, et le nom de la boutique.

### 3.5 Network

![Network](https://mypresta.eu/docs/images/docs/banippro-configure-network.webp)

L'écran est en anglais. Dans ce manuel, cette partie s'appelle **Network**.

Cliquez sur **Save**. La page affiche **Settings updated**.

| Champ | Au départ | Effet |
|---|---|---|
| **Trust Cloudflare** | **No** | Allumez ceci seulement quand le domaine de la boutique passe par Cloudflare. Le module lit alors l'IP du visiteur depuis Cloudflare, et seulement si la connexion vient vraiment de Cloudflare. Laissez **No** si vous n'êtes pas sûr, sinon chaque visiteur peut ressembler au proxy. |
| **Trusted reverse proxies** | vide | Si un proxy ou un répartiteur de charge est devant la boutique, mettez ici son adresse IP ou son réseau, un par ligne. Le module lit l'IP du visiteur seulement depuis ce proxy. Laissez vide si vous n'êtes pas sûr. |
| **Block selected countries** | **No** | **Yes** bloque chaque visiteur dont le pays est sur la liste ci-dessous. Cela commence après le téléversement de la base pays. Ne mettez pas votre propre pays. Un blocage par pays n'ajoute pas de ligne dans **Ban IP**. Il bloque cette requête et écrit une ligne de journal avec le motif **Country**. |
| **Country codes** | vide | Codes de deux lettres, par exemple `PL`, `DE` ou `US`. Séparez-les par des virgules, des espaces ou des retours à la ligne. Tout ce qui n'a pas deux lettres est écarté. |
| **Keep logs for days** | 90 | Combien de jours l'historique des blocages et la liste des actions du personnel sont gardés. Les lignes plus anciennes sont retirées à la première requête d'un jour suivant. La plus petite valeur enregistrée est 1. Les valeurs au-dessus de 3650 sont enregistrées comme 3650. |
| **GeoLite2 country database** | pas de fichier | Facultatif. Choisissez un fichier dont le nom se termine par `.mmdb`. Après **Save**, les statistiques peuvent montrer le pays et le blocage par pays peut fonctionner. Le reste du module n'a pas besoin de ce fichier. |

Au-dessus du champ fichier, la page montre une de ces lignes :

| Ce que vous voyez | Ce que vous faites |
|---|---|
| **GeoIP database is ready.** | Rien. La recherche de pays fonctionne. |
| **Country lookup needs PHP 7.2 or newer. The rest of the module keeps working.** | Les bannissements continuent. Les statistiques de pays et les blocages par pays restent éteints tant que PHP n'est pas 7.2 ou plus récent. |
| **Upload GeoLite2-Country.mmdb to enable country statistics and country blocks. MaxMind distributes that file.** | Téléversez le fichier et cliquez sur **Save**. |

Un mauvais fichier affiche **Upload a GeoLite2 Country file that ends with .mmdb.** Si le fichier ne peut pas être stocké, la page affiche **The GeoIP database could not be saved.** Un téléversement réussi affiche **The GeoIP database was uploaded.**

### 3.6 Tools

![Tools](https://mypresta.eu/docs/images/docs/banippro-configure-tools.webp)

L'écran est en anglais. Dans ce manuel, cette partie s'appelle **Tools**.

**Import rules** crée des bannissements. La portée est **Default scope of new bans**. Chaque nouvelle ligne est active, permanente, et utilise le motif **Manual** sauf si la ligne dit autre chose.

| Champ | Au départ | Effet |
|---|---|---|
| **Addresses** | vide, avec un exemple dans l'espace réservé | Une adresse par ligne. Une ligne CSV peut être adresse, commentaire, motif. Les lignes qui commencent par `#` sont ignorées. Une adresse qui existe déjà est sautée. |
| **File** | vide | Un fichier texte. Ses lignes s'ajoutent au cadre du dessus. Un fichier plus grand que 2 Mo affiche **The import file is larger than 2 MB.** et rien n'est importé. |
| **Import** | un bouton | Crée les bannissements et affiche **%d rules were imported.** Les lignes sautées affichent aussi **%d lines were skipped.** L'import s'arrête après 5000 lignes. |
| **Export rules CSV** | un bouton | Télécharge `banippro-rules.csv` pour chaque règle. Ne change pas la liste. |

**Web server snippet** montre deux cadres, Apache 2.4 et nginx. Le titre indique combien d'adresses ont été exportées. Seuls les bannissements actifs et permanents qui sont une IP seule ou un réseau sont inclus. Un motif comme `192.168.1.*` est écrit comme un réseau. Les plages et les bannissements temporaires sont laissés de côté. **Copy** copie le cadre. Le module ne modifie pas vos fichiers serveur. Vous collez le texte dans la configuration du serveur vous-même. S'il n'y a rien à exporter, les deux cadres le disent.

**Emergency unlock** montre une adresse. Ouvrez-la depuis un navigateur qui est verrouillé. Le module ajoute l'IP de ce navigateur à la liste d'autorisation, pour la boutique et le back-office, et laisse passer cette requête.

| Bouton | Effet |
|---|---|
| **Copy** | Copie l'adresse de déverrouillage. La clé reste la même. |
| **Create a new key** | Remplace la clé. La page dit **A new emergency key was created. The previous unlock link no longer works.** |
| **Rebuild cache** | Réécrit le cache des règles à partir de la liste actuelle. La page dit **The rule cache was rebuilt.** |

Gardez l'adresse de déverrouillage hors de la boutique. Quiconque l'ouvre est ajouté à la liste d'autorisation.

### 3.7 Updates

![Updates](https://mypresta.eu/docs/images/docs/banippro-configure-updates.webp)

L'écran est en anglais. Dans ce manuel, cette partie s'appelle **Updates**.

| Champ | Au départ | Effet |
|---|---|---|
| **Check now** | un bouton | Demande à MyPresta si une version plus récente existe. **New version available!** ou **Module is up to date!** La boutique ne fait jamais cet appel. |
| **Updates notifications** | **Disable** | **Enable** fait le même contrôle quand vous ouvrez cet onglet, au plus une fois tous les trois jours. Une version plus récente affiche aussi un avis sur la page du module : **New version available, check MyPresta.eu for more informations**, avec **More details in changelog**. |
| **Save** | un bouton | Enregistre **Enable** ou **Disable**. Ne télécharge pas de fichier. La page dit **Settings updated**. |

Le lien sous le formulaire ouvre la page du module sur mypresta.eu, où le journal des changements est publié. Ce manuel ne liste pas les versions.

### 3.8 Ban IP, la liste des règles

![Ban IP, la liste des règles](https://mypresta.eu/docs/images/docs/banippro-rules-list.webp)

L'écran est en anglais. Dans ce manuel, cette partie s'appelle **Ban IP, la liste des règles**.

Ouvrez **Paramètres avancés**, **Ban IP**, ou **Manage rules** sur **Dashboard**. La ligne au-dessus de la liste dit que le tableau de bord, les statistiques et l'automatisation sont sur la page de configuration du module, et propose **Open dashboard**.

**Add new** ouvre une règle vide. Sur une nouvelle règle vous pouvez coller plusieurs adresses, une par ligne. Elles partagent le commentaire, le motif, le type de règle, la portée, l'expiration, le drapeau actif et la boutique.

Les colonnes sont **ID**, **IP address**, **Match**, **Rule**, **Scope**, **Hits**, **Last hit**, **Expires**, **Reason** et **Active**. Quand la boutique utilise plus d'une boutique, **Shop** s'ajoute.

| Colonne | Ce que vous voyez |
|---|---|
| **Match** | **Exact**, **Wildcard**, **CIDR** ou **Range**. |
| **Rule** | **Ban** ou **Allow**. |
| **Scope** | **Front office**, **Back office**, ou **Front office and back office**. |
| **Hits** | Combien de requêtes bloquées ont été journalisées pour cette règle. |
| **Last hit** | Date de la dernière. |
| **Expires** | Une date et une heure, ou **Permanent**. |
| **Reason** | **Manual**, **Fraud**, **Spam**, **Scanner**, **Chargeback**, **Competitor**, **Auto ban (login)**, **Auto ban (probe)**, **Auto ban (rate limit)** ou **Country**. |
| **Active** | L'icône d'état. Cliquez pour allumer ou éteindre la ligne. Une règle inactive reste sur la liste et ne correspond à personne. |
| **Shop** | **All shops**, ou le nom d'une boutique. Affiché seulement en multiboutique. |

Utilisez la ligne de filtres pour chercher. Filtrer ne bloque personne et n'autorise personne.

Actions de ligne :

| Action | Effet |
|---|---|
| **Edit** | Ouvre la règle. Sur une ligne existante, une seule adresse peut être enregistrée. |
| **Whitelist** | Affiché sur un bannissement. Change cette ligne en **Allow** et reconstruit le cache. Masqué sur une ligne qui est déjà **Allow**. |
| **Delete** | Retire la ligne et reconstruit le cache. |

Actions groupées, après avoir coché des lignes :

| Action | Effet |
|---|---|
| **Enable selection** | Allume les lignes cochées et reconstruit le cache. |
| **Disable selection** | Éteint les lignes cochées et reconstruit le cache. Elles restent sur la liste. |
| **Delete selected** | Demande **Delete selected items?** puis retire les lignes cochées et reconstruit le cache. |

Une règle Allow est vérifiée avant les bannissements. Une règle Allow qui correspond laisse passer le visiteur même quand un bannissement correspondrait aussi.

Une règle dont l'heure de fin est passée cesse de correspondre tout de suite. À la première requête du jour suivant, elle est aussi passée en inactive.

### 3.9 Le formulaire de règle

![Le formulaire de règle](https://mypresta.eu/docs/images/docs/banippro-rule-form.webp)

L'écran est en anglais. Dans ce manuel, cette partie s'appelle **Le formulaire de règle**.

**Save** écrit la règle, reconstruit le cache et revient à la liste quand chaque ligne est valide.

| Champ | Au départ | Effet |
|---|---|---|
| **IP address** | vide | Sur une nouvelle règle, une adresse par ligne. Sur une modification, une adresse. Une IP seule, un motif comme `192.168.1.*`, un réseau comme `10.0.0.0/8`, ou une plage comme `192.168.1.10-192.168.1.20`. Les motifs sont en IPv4, et les étoiles doivent être à la fin. IPv6 fonctionne pour une adresse seule, un réseau et une plage. |
| **Comment** | vide | Une note privée que vous seul voyez dans cette liste. Les visiteurs ne la voient jamais. |
| **Reason** | **Manual** | Pourquoi cette adresse est listée. Les statistiques s'en servent pour distinguer un bannissement manuel d'un automatique. Les motifs automatiques ne sont pas dans cette liste déroulante. Le module les écrit lui-même. |
| **Rule** | **Ban** | **Ban** bloque l'adresse. **Allow** la laisse toujours passer, même quand une autre règle la bloquerait. |
| **Scope** | la valeur de **Default scope of new bans** | **Front office** est ce que les clients voient. **Back office** est ce panneau. **Front office and back office** signifie que la règle fonctionne dans la boutique et dans le panneau. |
| **Expires at** | vide | Laissez vide pour garder la règle jusqu'à ce que vous la supprimiez. Ou tapez la date et l'heure où elle doit s'arrêter, par exemple `2026-12-31 18:00`. Une mauvaise valeur affiche **The expiry date is not valid.** |
| **Active** | **Yes** | **No** garde la règle sur la liste, mais elle ne bloque personne et n'autorise personne. |
| **I confirm blocking my own IP** | **No** | La ligne d'aide montre votre IP actuelle, ou **unknown**. La confirmation est requise quand un bannissement correspondrait à cette IP dans le back-office. |
| **Shop** | **All shops** | Affiché seulement en multiboutique. **All shops** signifie que la règle fonctionne dans chaque boutique de cette installation. Choisissez une boutique pour limiter la règle à celle-ci. |
| **Save** | un bouton | Enregistre les lignes. |

Une saisie vide affiche **Enter an IP address.** Un motif qui correspondrait à chaque adresse, comme `*.*.*.*` ou un réseau de préfixe `0`, affiche **This rule would block every address.** Une mauvaise adresse affiche **This IP address or range is not valid.** Une seconde règle active avec la même adresse et le même type bannissement ou autorisation affiche **This rule already exists.** Un bannissement qui correspond à votre IP actuelle dans le back-office, sans l'interrupteur de confirmation, affiche **This ban matches your current IP in the back office. Confirm it before saving.** Plus d'une ligne sur une modification affiche **Edit one address at a time.** Une mauvaise ligne sur une nouvelle règle est sautée avec **Line … was skipped:** et le motif. Une ligne en double est sautée avec **Line was skipped because it already exists:** et l'adresse. Quand certaines lignes ont été enregistrées et d'autres non, la page affiche aussi **%d rules were saved.** et reste sur le formulaire. Si la ligne ne peut pas être écrite, la page affiche **The rule could not be saved.** Une ligne absente affiche **Rule not found.**

## 4. Devanture de la boutique

Le thème n'imprime ni bloc, ni pastille, ni widget pour ce module. Sur une page produit, panier ou accueil ordinaire, il n'y a rien à photographier.

Un visiteur qui n'est pas bloqué voit la boutique comme d'habitude. Un visiteur bloqué voit une page simple : le logo de la boutique quand elle en a un, le titre 403, le **Message for blocked visitors** dans la langue de la page, et l'IP du visiteur. La page demande aux moteurs de ne pas l'indexer. Si **Redirect blocked visitors** est sur **Yes** et que **Redirect URL** est un lien `http` ou `https` valide, le visiteur est envoyé à cette adresse et ne voit pas le message.

La même page de blocage est utilisée dans le back-office quand **Protect the back office** est sur **Yes** et que l'IP de l'employé correspond là à un bannissement et ne correspond pas à une règle Allow.

Ces contrôles ne tournent que sur les requêtes qui entrent dans PrestaShop. Les fichiers servis directement par le serveur web, comme les images, ne sont pas contrôlés et ne sont pas comptés par **Limit requests per IP**.

Il n'y a pas de page de compte client ni de formulaire de recours. Le visiteur passe, voit la page de blocage, ou arrive sur la redirection.

| Ce que le visiteur voit | Ce que vous faites |
|---|---|
| La boutique, comme d'habitude | Aucun bannissement ne correspond, ou une règle Allow a correspondu. |
| La page de blocage avec votre message et son IP | Un bannissement a correspondu, le pays est bloqué, un chemin de sonde a été ouvert, ou la limite de requêtes a été dépassée. La redirection est sur **No**. |
| Un autre site, sans message | La redirection est sur **Yes** et l'URL est valide. |
| Le back-office, comme d'habitude | **Protect the back office** est sur **No**, ou cette IP est sur la liste d'autorisation. |

## 5. Problèmes

**La page du module dit Ban IP Pro requires PHP 7.1 or newer.**  
Le serveur est sur un PHP plus ancien que 7.1. L'installation est refusée et **Configurer** ne montre que cette phrase. Passez la boutique à PHP 7.1 ou plus récent, puis installez de nouveau.

**Configurer dit The module database could not be updated.**  
Les tables n'ont pas pu être créées ou mises à jour. Demandez à l'hébergeur d'autoriser l'utilisateur de base à créer et modifier des tables, puis ouvrez **Configurer** encore une fois.

**Front hook dit Missing.**  
Le contrôle n'est pas accroché. Réinstallez le module, ou désactivez-le puis réactivez-le depuis le **Gestionnaire de modules**. Les règles existantes restent.

**L'enregistrement dans Behavior refuse Protect the back office.**  
La page dit **Add your current IP to the allow list before you protect the back office.** Sur **Dashboard**, cliquez sur **Add to allow list**, puis mettez l'interrupteur sur **Yes** et enregistrez encore.

**Vous vous êtes enfermé hors du back-office.**  
Ouvrez l'adresse d'urgence de **Tools**, **Emergency unlock**, dans un navigateur qui atteint encore la boutique. L'IP de ce navigateur est ajoutée à la liste d'autorisation et la requête est laissée passer. Si vous ne pouvez pas ouvrir **Tools**, utilisez une copie de l'adresse que vous aviez gardée. **Create a new key** rend l'ancienne adresse inutile, donc mettez votre copie à jour après usage.

**Un bannissement de votre propre IP est refusé.**  
La page dit **This ban matches your current IP in the back office. Confirm it before saving.** Allumez **I confirm blocking my own IP**, ou changez la portée en **Front office** si vous ne voulez bloquer cette IP que sur la boutique.

**L'import dit The import file is larger than 2 MB.**  
Découpez le fichier. Chaque import s'arrête après 5000 lignes et montre alors que l'import s'est arrêté. Passez le reste dans un autre import. Les lignes sautées affichent **%d lines were skipped.** Les adresses déjà présentes sont sautées exprès.

**L'adresse a été enregistrée, mais la boutique la laisse encore passer.**  
Vérifiez **Active**, **Scope** et **Expires at**. Une règle de back-office ne touche pas la boutique. Une règle Allow pour cette IP l'emporte. Sur **Dashboard**, utilisez **Test an address**. Puis cliquez sur **Rebuild cache** dans **Tools**.

**Les bannissements du back-office ne font rien.**  
**Test an address** ajoute **Back office protection is disabled, so back-office bans are not enforced.** Allumez **Protect the back office** dans **Behavior** une fois que votre IP est sur la liste d'autorisation.

**Le blocage par pays ne fait rien.**  
**Block selected countries** doit être sur **Yes**, les codes doivent faire deux lettres, et la page doit dire **GeoIP database is ready.** Sous PHP plus ancien que 7.2, la page dit que la recherche de pays demande PHP 7.2 ou plus récent. Ne mettez pas votre propre pays dans la liste.

**Des clients sont bannis pendant une vente ordinaire.**  
**Limit requests per IP** est allumé et la limite est basse pour cette boutique. Mettez-le sur **No**, ou augmentez **Requests allowed in the window**. Supprimez les bannissements automatiques dans **Ban IP**. Leur motif est **Auto ban (rate limit)**.

**Un échec de connexion employé n'a pas bloqué le back-office.**  
Ce bannissement automatique s'applique à la boutique. Le panneau n'est bloqué que quand **Protect the back office** est sur **Yes** et qu'un bannissement dont la portée inclut le back-office correspond à cette IP.

**Le courriel d'alerte n'arrive jamais.**  
**Email me when an automatic ban is created** doit être sur **Yes**. Les bannissements manuels n'envoient pas de courriel. Un second bannissement automatique dans la même heure n'envoie pas un autre courriel. La boîte est **Alert email**, ou le courriel de la boutique quand ce champ est vide. La boutique doit déjà savoir envoyer du courrier.

**Le graphique montre encore d'anciens jours après que vous avez raccourci le journal.**  
**Keep logs for days** retire le journal ligne par ligne et les actions du personnel. Les totaux journaliers utilisés par le graphique du tableau de bord restent.

**New version available, check MyPresta.eu for more informations.**  
Ouvrez **Updates** et utilisez le lien, ou cliquez sur **Check now**. Ce manuel ne liste pas les changements.

## 6. Pour le développeur

### 6.1 Vue d'ensemble

Nom technique `banippro`, version 2.0.0, classe `banippro`, nom affiché **Ban IP pro**, auteur MyPresta.eu, onglet `administration`. Page produit : `https://mypresta.eu/modules/administration-tools/block-ip-address-pro.html`.

`actionDispatcherBefore` appelle `BanIpGuard::protect()`. Le guard résout l'IP, applique le déverrouillage d'urgence, puis `BanIpMatcher::decide()` sur le cache de `cache/rules.php`. Allow l'emporte sur ban. Le blocage par pays, les bannissements de sonde et la limite de requêtes tournent sur la boutique. Un blocage journalise un hit et soit redirige, soit rend `blocked.tpl` avec le statut 403 et termine la requête. `actionDispatcherAfter` lance `BanIpAutoBan::evaluate()` pour une connexion armée plus tôt. Les réglages sont des valeurs de configuration globales lues par `BanIpInstaller`. Le contrôleur de menu `AdminBanIpPro` édite la table `ban`.

Il n'y a pas de surcharge de `enable()` ni de `disable()`. La désactivation PrestaShop décroche les hooks, donc le guard ne tourne pas. Les données restent.

### 6.2 Fichiers

| Fichier | Rôle |
|---|---|
| `banippro.php` | Installation, hooks, onglets, bannissement rapide, import, test. |
| `controllers/admin/AdminBanIpProController.php` | Liste, formulaire, export CSV, action de liste blanche. |
| `models/banip.php` | Modèle de `ban`, plus `storeRule()` et `importLines()`. |
| `classes/BanIpGuard.php` | Contrôle de requête, page de blocage, entretien quotidien. |
| `classes/BanIpMatcher.php` | Analyse exact, wildcard, CIDR et range. Décide allow puis ban. |
| `classes/BanIpClientIp.php` | Adresse distante, Cloudflare, proxies de confiance. |
| `classes/BanIpCache.php` | Construit et inclut `cache/rules.php`. |
| `classes/BanIpAutoBan.php` | Sonde, échec de connexion, limite, courriel d'alerte. |
| `classes/BanIpStats.php` | Tableau de bord, rapport, CSV, extraits serveur. |
| `classes/BanIpGeo.php` | Lit `geo/GeoLite2-Country.mmdb` sans la bibliothèque MaxMind. |
| `classes/BanIpInstaller.php` | Tables et configuration par défaut. |
| `classes/BanIpUpdate.php` | Contrôle de version contre `dev.mypresta.eu`. |
| `views/templates/admin/*.tpl` | Tableau de bord, statistiques, outils, coque. |
| `views/templates/front/blocked.tpl` | Page de blocage. |
| `views/js/dashboard.js` | Graphiques et boutons de copie. |
| `mails/en/banippro_alert.txt`, `mails/pl/banippro_alert.txt` | Corps de l'alerte. L'objet est fixé dans `BanIpAutoBan::alert()`. |
| `upgrade/upgrade-2.0.0.php` | Lance `BanIpInstaller::upgrade()`, remplace les anciens hooks par le jeu 2.0.0, reconstruit le cache. |
| `lib/searchTool/` | Chargé sur la page de configuration. Aucun champ de configuration ne l'appelle. |
| `tests/matcher_test.php` | Contrôles CLI du matcher. |

### 6.3 Contrôleurs

`AdminBanIpPro` étend `ModuleAdminController`. L'onglet parent est `AdminAdvancedParameters`. Nom de classe `AdminBanIpPro`. Table `ban`, identifiant `id_ban`, objet `banip`.

Les filtres de liste utilisent les noms habituels du helper (`banFilter_ip` et les autres champs). Actions de ligne : édition, `displayWhitelistLink` (`banippro_whitelist`), suppression. Actions groupées : delete, enable, disable. `exportHits` envoie le CSV des hits. `exportRules` envoie le CSV des règles.

Il n'y a pas de contrôleur front. La réponse de blocage est rendue dans le hook du dispatcher et la requête se termine.

`?banippro_unlock=` est lu par `BanIpGuard::tryUnlock()`. La valeur doit correspondre à `banippro_emergency_key` avec `hash_equals`. Une correspondance appelle `BanIpAutoBan::ensureAllow()` avec la portée boutique et back-office (`apply_to` 3, `id_shop` 0) et audite `unlock`.

### 6.4 Hooks

Enregistrés à l'installation :

| Hook | Appel |
|---|---|
| `actionDispatcherBefore` | `BanIpGuard::protect()`. |
| `actionDispatcherAfter` | `BanIpAutoBan::evaluate()`. Enregistré aussi après le contrôle principal d'installation. |
| `actionFrontControllerSetMedia` | `BanIpAutoBan::arm('customer')`. |
| `actionAuthentication` | `BanIpAutoBan::markSuccess('customer')`. |
| `actionAdminControllerInitAfter` | `BanIpAutoBan::arm('employee')`. |

`upgrade-2.0.0.php` désenregistre `header`, `displayHeader`, `home`, `displayHome`, `actionFrontControllerAfterInit` et `actionAdminControllerSetMedia`.

Le module n'expose pas de hook à lui. L'armement de la connexion cherche `submitLogin` dans la requête. Une connexion client réussie efface le compteur d'échecs client. Le succès employé est détecté quand l'employé est connecté dans `evaluate()`.

### 6.5 Surcharges

Le module ne surcharge aucune classe ni aucun contrôleur PrestaShop.

### 6.6 Base

La désinstallation ne supprime pas ces tables et ne supprime pas les clés de configuration. `BanIpInstaller::ensure()` ajoute les colonnes manquantes de `{prefix}ban` à l'ouverture de **Configurer**, donc une ancienne table `ban` est conservée et étendue. Une réinstallation ne vide pas les lignes.

| Table | Contenu |
|---|---|
| `{prefix}ban` | `id_ban`, `ip`, `ip_end`, `match_type` (`exact`, `wildcard`, `cidr`, `range`), `rule_type` (1 ban, 2 allow), `apply_to` (1 boutique, 2 back-office, 3 les deux), `views`, `comment`, `reason`, `active`, `date_add`, `date_upd`, `date_end`, `last_hit`, `id_employee`, `id_shop` (0 signifie toutes les boutiques), `range_start`, `range_end`. |
| `{prefix}banippro_hit` | Une ligne par blocage : `id_ban`, `ip`, `request_uri`, `user_agent`, `country_iso`, `id_shop`, `date_add`. |
| `{prefix}banippro_daily` | `day`, `id_shop`, `blocked`, `auto_banned`. N'est pas supprimée quand les journaux sont élagués. |
| `{prefix}banippro_fail` | `ip`, `context` (`customer`, `employee`, `rate`), `hits`, `window_start`. |
| `{prefix}banippro_audit` | `id_employee`, `action`, `details`, `date_add`. |

`BanIpGuard::dailyMaintenance()` tourne une fois par jour calendaire. Il met `active` à 0 sur les règles dont `date_end` est passé, reconstruit le cache si une ligne a changé, et supprime les lignes hit et audit plus anciennes que `banippro_log_days`.

### 6.7 Clés et traductions

Toutes les clés sont globales (`id_shop` 0). Une clé absente retombe sur la valeur par défaut entre parenthèses.

| Clé | Défaut |
|---|---|
| `banippro_emergency_key` | 32 caractères hex de `random_bytes`, ou OpenSSL, ou `md5` |
| `banippro_msg` | Par langue. `en` You are blocked. `pl` Dostęp został zablokowany. `es` El acceso ha sido bloqueado. `pt` et `br` O acesso foi bloqueado. Les autres langues reçoivent la phrase anglaise. Le HTML est permis dans le stockage. |
| `banippro_redirect` | 0 |
| `banippro_url` | vide |
| `banippro_default_apply` | 1 |
| `banippro_protect_admin` | 0 |
| `banippro_honeypot` | 1 |
| `banippro_honeypot_hours` | 24 |
| `banippro_honeypot_paths` | `BanIpInstaller::defaultHoneypotPaths()` |
| `banippro_autoban_customer` | 0 |
| `banippro_autoban_employee` | 0 |
| `banippro_autoban_threshold` | 5 |
| `banippro_autoban_window` | 15 |
| `banippro_autoban_hours` | 24 |
| `banippro_ratelimit` | 0 |
| `banippro_ratelimit_max` | 120 |
| `banippro_ratelimit_window` | 1 |
| `banippro_ratelimit_ban_minutes` | 15 |
| `banippro_alert` | 0 |
| `banippro_alert_email` | vide |
| `banippro_alert_last` | temps unix du dernier courriel d'alerte, écrit à l'envoi |
| `banippro_cloudflare` | 0 |
| `banippro_trusted_proxies` | vide |
| `banippro_countries_enabled` | 0 |
| `banippro_countries` | vide |
| `banippro_log_days` | 90 |
| `banippro_last_maintenance` | `Y-m-d` du dernier entretien quotidien |
| `mypresta_updates` | non initialisé ; le formulaire traite une valeur absente comme 0 |
| `update_banippro` | 0, puis le temps unix du dernier contrôle |
| `updatev_banippro` | chaîne de version distante du dernier contrôle |

`BanIpInstaller::seedConfig()` copie un ancien `banippro_redirect` et `banippro_url` liés à la boutique vers les clés globales quand la valeur globale est vide. Un ancien `banippro_msg` non vide est copié dans chaque langue avant l'usage des phrases par défaut.

Les textes du back-office passent par `$this->l()` / `$this->module->l()`. Les fichiers de traduction sont dans `translations/{iso}.php`. Le message de la page de blocage est la valeur de configuration, pas une clé de traduction. L'objet du courriel `Ban IP Pro alert` est un littéral dans `BanIpAutoBan::alert()`. L'aide des champs est le `desc` de chaque input HelperForm dans `banippro.php` et `AdminBanIpProController.php`.

Les valeurs automatiques de `reason` écrites par le module sont `auto-login`, `auto-honeypot` et `auto-rate`. Les blocages par pays journalisent `country` et n'insèrent pas de ligne `ban`. `banip::importLines()` s'arrête après 5000 lignes non vides qui ne sont pas un commentaire. Les téléversements au-dessus de 2097152 octets sont refusés. `BanIpMatcher` refuse une valeur vide, un réseau `/0` et un joker de quatre étoiles (`too_broad`). Un doublon est une ligne active avec la même IP stockée et le même `rule_type`.

`BanIpAutoBan::ensureBan()` stocke toujours `apply_to` 1 et `id_shop` 0. `ensureAllow()` stocke `apply_to` 3 et `id_shop` 0.

### 6.8 Extension

Le thème peut surcharger `views/templates/front/blocked.tpl`. Le module appelle `$module->fetch('blocked.tpl')`. Les variables assignées sont `banippro_message`, `banippro_shop`, `banippro_logo`, `banippro_year`, `banippro_ip` et `banippro_lang`. Si le fetch échoue, le guard imprime une page HTML minimale avec le même message et termine quand même avec le statut 403.

Aucun modèle produit, panier ou accueil n'est rendu. Il n'y a pas de hook pour qu'un thème ajoute un widget en boutique. Les modèles d'administration sont sous `views/templates/admin/` et ne font pas partie du thème.

## 7. Aide

Page du module : [Ban IP pro](https://mypresta.eu/modules/administration-tools/block-ip-address-pro.html).

Connectez-vous à votre compte client sur [mypresta.eu](https://mypresta.eu), ouvrez le formulaire de contact et choisissez **Support for paid modules**. Le formulaire indique que la connexion est requise pour ce sujet. Après la connexion, choisissez ce module dans l'historique d'achats.
