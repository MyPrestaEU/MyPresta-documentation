---
title: Contact page - spam protection PRO - documentation et manuel utilisateur
sidebar:
  label: Contact page - spam protection PRO - documentation et manuel utilisateur
description: Guide de réglage et de dépannage pour les boutiques qui ont déjà la protection antispam de la page de contact.
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Contact page - spam protection PRO sur MyPresta.eu](https://mypresta.eu/modules/administration-tools/contact-page-spam-protection-pro.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/back-office-tools/contact-page-spam-protection-pro/)
>
> ---


## 1. Prérequis

Le module tourne sur PrestaShop 1.7.7 à 9. PHP dans la version exigée par cette version de PrestaShop. La page de contact de la boutique suffit. Aucun autre module n'est nécessaire.

Un compte Google reCAPTCHA n'est utile que pour la case ou le score invisible. Après l'installation, l'interrupteur reCAPTCHA est activé, mais le contrôle reste éteint tant que les deux clés ne sont pas enregistrées.

Un compte CleanTalk n'est utile que pour l'API payante. Le contrôle gratuit passe par le proxy MyPresta et ne demande pas de compte CleanTalk. Le CleanTalk gratuit a besoin des fonctions OpenSSL de PHP. Si elles manquent, ce seul contrôle est ignoré et le message passe.

StopForumSpam est une consultation publique. Le compte et la clé API sont facultatifs. La clé enregistrée n'est pas utilisée pour la consultation.

Les consultations utilisent cURL quand PHP l'a. Sans cURL, StopForumSpam, CleanTalk et la vérification des mises à jour lisent l'adresse directement si le serveur l'autorise. La vérification reCAPTCHA utilise cURL quand il est disponible.

## 2. Installation

Ouvrez **Modules**, puis **Gestionnaire de modules**. Envoyez le zip et cliquez sur **Installer**.

Le menu de gauche gagne **Protection du contact**. Ouvrez-le pour arriver à la configuration. En dessous se trouvent **Tentatives d'envoi de messages** et **Adresses IP bannies**.

L'installation ne vide pas le cache dans une étape séparée.

Pour l'éteindre, utilisez l'interrupteur du gestionnaire de modules. La page de contact n'est plus contrôlée. Les réglages, les tentatives et les bannissements restent. En le rallumant, ils servent de nouveau. Les entrées de menu sont cachées tant que le module est éteint.

Pour le retirer, cliquez sur **Désinstaller** et confirmez **Voulez-vous vraiment désinstaller ce module ?** La désinstallation retire les entrées de menu, les réglages enregistrés et les deux listes. Les fichiers restent sur le serveur jusqu'à ce que vous supprimiez le module. Une nouvelle installation repart avec des listes vides et les réglages d'une installation neuve. Les anciennes tentatives et les anciens bannissements ne reviennent pas.

## 3. Configuration et travail quotidien

Les captures de ce chapitre sont le back-office en anglais. Les noms ci-dessous sont ceux du panneau en français.

Ouvrez **Protection du contact**. Les onglets sont **Vue d'ensemble**, **Anti-flood**, **CleanTalk**, **StopForumSpam**, **reCAPTCHA**, **Filtres de messages**, **Liste blanche**, **Protection** et **E-mail**. **Mises à jour** est en bout de rangée. **Enregistrer** sur un onglet l'enregistre et confirme **Paramètres enregistrés.** L'onglet des mises à jour confirme **Paramètres de mise à jour enregistrés.**

Tant que la condition dure, une page de configuration peut afficher :

**reCAPTCHA est activé, mais la clé du site ou la clé secrète est vide. Le captcha reste désactivé tant que les deux clés ne sont pas enregistrées.**

**L'API payante CleanTalk est activée, mais la clé d'accès est vide.**

Le second avertissement apparaît quand l'interrupteur payant est activé et que la clé est vide. Après une installation neuve, cet interrupteur est éteint, donc l'avertissement n'est pas là tant que vous n'activez pas l'API payante sans clé.

Un message est contrôlé dans cet ordre. Le premier résultat décide.

1. Une adresse de la liste blanche, et un client connecté quand **Ignorer les contrôles pour les clients connectés** est activé, continue vers le formulaire. La tentative n'est pas écrite dans **Tentatives d'envoi de messages**.
2. Si tous les contrôles sont éteints et que l'adresse n'est pas sur la liste des bannissements, le message continue et n'est pas enregistré. L'interrupteur reCAPTCHA seul ne compte pas comme contrôle tant que les deux clés sont vides.
3. Ensuite : bannissement actif, honeypot, temps minimum, identifiant de navigateur vide, anti-flood, doublon d'un message d'au moins 20 caractères, trop de liens, mot bloqué, e-mail jetable, reCAPTCHA (seulement quand les deux clés sont enregistrées), StopForumSpam, CleanTalk gratuit, puis CleanTalk payant.
4. Si rien ne correspond, la tentative est enregistrée comme autorisée et le formulaire envoie le message.
5. Un blocage **Trop rapide** ou **reCAPTCHA** arrête seulement ce message. Il ne bannit pas l'adresse, n'envoie pas d'e-mail à la boutique et ne redirige pas. Pour reCAPTCHA, le client voit **La vérification captcha a échoué. Veuillez réessayer.** S'il est allé trop vite, il voit **Votre message n'a pas pu être envoyé. Veuillez réessayer dans quelques minutes.**
6. Tout autre blocage peut bannir l'adresse, écrire à la boutique et rediriger, selon les cases de **Protection**. Si plusieurs redirections sont cochées, la page d'accueil passe en premier, puis la page CMS, puis Google. Sans redirection, le visiteur reste sur la page de contact et voit **Votre message n'a pas pu être envoyé. Veuillez réessayer dans quelques minutes.**

L'anti-flood compte chaque tentative de la fenêtre, y compris celles déjà bloquées. Plusieurs essais de captcha peuvent donc atteindre la limite de messages.

Un doublon regarde les tentatives précédentes avec le même texte. Les tentatives qui n'ont échoué que pour **Trop rapide** ou **reCAPTCHA** ne comptent pas comme copie précédente.

StopForumSpam et les deux contrôles CleanTalk laissent passer le message quand le service ne répond pas. reCAPTCHA fait l'inverse : si Google ne répond pas, le message est bloqué.

### 3.1 Vue d'ensemble

![Vue d'ensemble](https://mypresta.eu/docs/images/docs/mycontactprotectionpro-overview.webp)

La **Vue d'ensemble** compte les messages de contact, les messages bloqués et les bannissements actifs pour les dates des **Paramètres d'analyse**. Un client qui passe compte comme un message. Un visiteur qui rate un contrôle compte comme bloqué et apparaît en dessous avec le motif.

Les cartes sont **Messages**, **Autorisés**, **Bloqués**, **Taux de blocage**, **Adresses IP bloquées** et **Bannissements actifs**.

Le graphique **Bloqués et autorisés** montre **Par jour** et **Par semaine** quand la période a plus de 7 jours. **Par semaine** groupe les jours par sept depuis le début de la période. Le dernier groupe peut être plus court. La légende est **Autorisés**, **Bloqués** et **Total**. Sans ligne dans la période, le graphique dit **Aucun message pendant cette période.**

**Blocages par motif** montre combien de blocages chaque contrôle a produits. Les noms de cette page sont **IP bannie**, **Honeypot**, **Trop rapide**, **User agent vide**, **Anti-flood**, **Message en double**, **Trop de liens**, **Mot bloqué**, **E-mail jetable**, **reCAPTCHA**, **StopForumSpam** et **CleanTalk**. Un motif vide s'affiche comme **Inconnu**.

**Derniers messages bloqués** a les colonnes **Date**, **IP**, **E-mail** et **Motif**. Si rien n'a été bloqué, le tableau dit **Rien n'a été bloqué pendant cette période.**

Les boutons **Tentatives d'envoi de messages** et **Adresses IP bannies** ouvrent ces listes.

Les pastilles de couleur sous le graphique montrent quels contrôles sont actifs. **reCAPTCHA** n'est vert que lorsque les deux clés sont enregistrées. L'interrupteur seul ne rend pas cette pastille verte. Après l'installation, **Anti-flood**, **Honeypot**, **Temps minimum** et **Limite de liens** sont actifs.

La ligne sous les pastilles a la forme **Messages : 0 entre le 2026-10-13 et le 2026-11-11. Bloqués : 0, autorisés : 0. Nouveaux bannissements pendant cette période : 0.** Les dates suivent la période choisie. Une période glissante se termine aujourd'hui. Les dates sont la fenêtre actuelle de la boutique, pas une valeur fixe du module.

### 3.2 Paramètres d'analyse

![Paramètres d'analyse](https://mypresta.eu/docs/images/docs/mycontactprotectionpro-overview-analytics.webp)

Ouvrez le panneau fermé **Paramètres d'analyse** dans la **Vue d'ensemble**.

| Champ | Au départ | Ce qu'il fait |
|---|---|---|
| **Période des statistiques** | 30 derniers jours | **7 derniers jours**, **30 derniers jours**, **90 derniers jours**, **180 derniers jours**, **365 derniers jours** ou **Période personnalisée**. Les cartes, le graphique et la dernière liste utilisent cette fenêtre. Le départ est les 30 derniers jours. Les 7 derniers jours montrent une pointe courte et retirent les blocages plus anciens du graphique. Les 365 derniers jours couvrent une année, donc une journée chargée n'est qu'une petite part. La période personnalisée utilise **Du** et **Au**. Les autres choix ignorent ces dates et se terminent toujours aujourd'hui. |
| **Du** | le début de la fenêtre en cours | Date AAAA-MM-JJ. Utilisée quand la **Période des statistiques** est **Période personnalisée**. Une date postérieure à **Au** est échangée avec **Au**. Une plage de plus de 366 jours est raccourcie de ce côté. Une date future revient à aujourd'hui. Une date vide ou invalide est remplacée par la date d'il y a 30 jours. Les périodes glissantes ignorent ce champ. |
| **Au** | aujourd'hui | Date AAAA-MM-JJ. Utilisée quand la **Période des statistiques** est **Période personnalisée**. Une date future revient à aujourd'hui. Si **Au** est antérieur à **Du**, les dates sont échangées. Une date vide ou invalide est remplacée par aujourd'hui. Les périodes glissantes ignorent ce champ et se terminent toujours aujourd'hui. |

**Enregistrer** enregistre la période. La page confirme **Paramètres enregistrés.**

### 3.3 Anti-flood

![Anti-flood](https://mypresta.eu/docs/images/docs/mycontactprotectionpro-antiflood.webp)

L'anti-flood compte combien de messages de contact une adresse IP envoie dans la fenêtre. Un client qui écrit quelques fois passe encore. Le message suivant au-delà de la limite est refusé, et **Protection** peut bannir cette adresse si la case de bannissement est cochée.

| Champ | Au départ | Ce qu'il fait |
|---|---|---|
| **Activer l'anti-flood** | Oui | Activé : chaque IP est comptée dans la fenêtre, et le message suivant au-delà de la limite est bloqué. Désactivé : un script peut continuer à envoyer depuis la même IP sans limite de ce contrôle. Une limite basse bloque aussi un client qui envoie une correction depuis le même bureau. Laissez-le activé sur une page de contact publique. Éteignez-le seulement le temps d'envoyer des messages de test depuis une adresse. |
| **Fenêtre de temps** | 10 minutes | Minutes. Seuls les messages de contact des X dernières minutes comptent pour la limite. 1 ou 2 minutes attrapent une pointe puis l'oublient, un script lent peut donc continuer. 60 minutes ou plus comptent aussi un client qui écrit, attend et réécrit depuis la même IP. Un 0 enregistré est traité comme 1. |
| **Messages autorisés** | 5 | Combien de messages de contact une IP peut envoyer dans la fenêtre. Le suivant est bloqué. 5 laisse corriger un message et le renvoyer. 1 bloque le second envoi, donc les scripts et aussi un client qui clique deux fois sur envoyer. Une valeur haute, par exemple 20, laisse passer beaucoup de messages. Le compteur inclut les envois précédents de cette IP, y compris ceux bloqués, plusieurs essais de captcha peuvent donc atteindre la limite. Un 0 enregistré est traité comme 1. |

### 3.4 CleanTalk

![CleanTalk](https://mypresta.eu/docs/images/docs/mycontactprotectionpro-cleantalk.webp)

CleanTalk contrôle l'IP et l'e-mail dans une base de spam. Activez l'option gratuite pour passer par le proxy MyPresta sans compte CleanTalk, ou l'option payante si vous avez votre propre clé. Une adresse inconnue est acceptée. Une adresse déjà signalée comme spam est refusée. Si le service ne répond pas, le message passe.

| Champ | Au départ | Ce qu'il fait |
|---|---|---|
| **Activer CleanTalk gratuit** | Non | Demande au proxy CleanTalk de MyPresta si cette IP ou cet e-mail est déjà connu comme spam. Aucun compte CleanTalk n'est nécessaire. Désactivé ignore ce contrôle. Si le proxy ne répond pas, ou si PHP n'a pas le chiffrement OpenSSL, le message passe. Un robot absent de la base passe aussi. Activez-le si vous n'avez pas de clé payante. |
| **Activer l'API payante CleanTalk** | Non | Utilise la clé d'accès de votre compte CleanTalk. Activez-la après avoir collé la clé. Laissez-la éteinte si vous n'avez pas d'abonnement. Une clé vide ou refusée ne bloque personne, le spam que seul ce contrôle aurait pris est donc accepté. Une adresse de la liste est refusée, et un client sur la même IP peut l'être aussi. |
| **Clé d'accès** | vide | Collez la clé de votre compte CleanTalk, sans espaces en trop. Le contrôle payant ne tourne que si ce champ a une clé. Vide, avec l'interrupteur payant activé, signifie pas de contrôle payant, et la page affiche **L'API payante CleanTalk est activée, mais la clé d'accès est vide.** Une clé révoquée est traitée comme un contrôle raté et le message passe. |
| **Seuil du taux de spam** | 1 | Un score de 0.0 à 1.0. Un taux de spam CleanTalk égal ou supérieur à cette valeur est traité comme du spam. Une adresse que CleanTalk marque comme présente dans le spam est bloquée quelle que soit la valeur. 1 bloque les adresses dont CleanTalk est sûr. Une valeur plus basse, par exemple 0.5, bloque aussi les résultats incertains et peut arrêter un vrai client sur une IP partagée. Un 0 enregistré est traité comme 1, le contrôle reste donc strict. |

Le lien **Ouvrir la page du compte CleanTalk** ouvre le compte dans un nouvel onglet.

### 3.5 StopForumSpam

![StopForumSpam](https://mypresta.eu/docs/images/docs/mycontactprotectionpro-stopforumspam.webp)

StopForumSpam est une base gratuite d'adresses IP et d'e-mails signalés pour spam. Le contrôle n'a pas besoin de clé API. Un client qui n'a jamais été signalé est accepté. Une adresse avec assez de signalements est refusée. Si le service ne répond pas, le message passe.

| Champ | Au départ | Ce qu'il fait |
|---|---|---|
| **Activer StopForumSpam** | Non | L'IP du visiteur et l'e-mail du formulaire sont consultés. Désactivé ignore le contrôle. Si le service ne répond pas, le message passe : un problème de réseau ne bloque pas les clients, et le spam que ce contrôle aurait pris passe aussi. Laissez-le activé sur une page de contact publique. |
| **Signalements minimum** | 1 | Bloquer quand StopForumSpam a enregistré cette IP ou cet e-mail au moins autant de fois. À 1, un seul signalement bloque l'adresse, y compris un client signalé une fois par erreur. À 5 ou plus, les adresses peu signalées passent, donc plus de spam arrive. Un 0 enregistré est traité comme 1. |
| **Clé API** | vide | Facultative. La consultation publique fonctionne sans clé. Laissez-la vide, ou enregistrez une clé si vous avez déjà un compte StopForumSpam. Le module utilise quand même la consultation publique, une mauvaise clé ne change donc pas qui est bloqué. |

Le lien **S'inscrire** ouvre l'inscription StopForumSpam.

### 3.6 reCAPTCHA

![reCAPTCHA](https://mypresta.eu/docs/images/docs/mycontactprotectionpro-recaptcha.webp)

Google reCAPTCHA tourne dans le navigateur, sur la page de contact. Utilisez-le quand des robots envoient des messages qui ressemblent à du texte ordinaire, et choisissez le même type que celui de la clé dans la console Google. v2 montre une case. v3 note la visite sans défi : un score qui passe est accepté, un score qui échoue refuse le message sans bannir l'IP.

Le texte **Comment obtenir la clé du site et la clé secrète** dit : créez la clé dans la console Google, puis collez ci-dessous la clé du site et la clé secrète. Le type choisi ici doit être le même que celui de cette clé. Un type différent fait échouer chaque visiteur, y compris un vrai client.

| Champ | Au départ | Ce qu'il fait |
|---|---|---|
| **Activer reCAPTCHA** | Oui | La page de contact demande de passer reCAPTCHA avant d'accepter le message. Avec des clés vides, le captcha reste éteint même si cet interrupteur est activé, et la page affiche **reCAPTCHA est activé, mais la clé du site ou la clé secrète est vide. Le captcha reste désactivé tant que les deux clés ne sont pas enregistrées.** Un client qui échoue peut réessayer. Cet échec ne bannit pas l'IP. |
| **Type de reCAPTCHA** | reCAPTCHA v2 | **reCAPTCHA v2** montre une case. **reCAPTCHA v3** note la visite en arrière-plan et ne montre pas de défi. Utilisez le même type que celui choisi pour la clé dans la console Google. Un décalage fait échouer chaque envoi, y compris ceux des vrais clients. v2 est plus clair quand vous voulez un contrôle visible. v3 se voit moins et utilise le seuil ci-dessous. |
| **Clé du site** | vide | La clé publique de l'administration Google reCAPTCHA pour le domaine de cette boutique. Collez la clé du site qui appartient au type choisi au-dessus, sans espaces. Les deux clés sont nécessaires. Une clé du site vide laisse le captcha éteint. Une clé d'un autre domaine ou d'un autre type fait échouer les vrais clients. |
| **Clé secrète** | vide | La clé secrète reste sur le serveur. Elle n'est jamais envoyée au navigateur. Utilisez la clé secrète de la même paire que la clé du site. Une clé secrète vide laisse le captcha éteint. Une clé secrète d'un autre site fait rejeter chaque visite par Google, les clients ne peuvent pas envoyer le formulaire. |
| **Thème v2** | Clair | Couleur **Clair** ou **Sombre** de la case v2. Clair sur une page de contact blanche, Sombre sur une page sombre. v3 ignore ce réglage et utilise le badge standard de Google. Le thème ne change pas qui est bloqué. Un widget sombre sur une page blanche se voit moins, plus de gens sautent la case et le message est refusé. |
| **Seuil de score v3** | 0.5 | Un score de 0.0 à 1.0. Utilisé quand le type est v3. Google note la visite, et un score sous cette valeur est refusé. Le départ est 0.5. Une valeur plus haute, par exemple 0.9, est plus stricte et peut refuser des clients sur un réseau partagé ou inhabituel. Une valeur plus basse, par exemple 0.1, laisse passer plus de visites automatiques. Un refus ne bannit pas l'IP. Si la valeur enregistrée manque, 0.5 est utilisé. |

### 3.7 Filtres de messages

![Filtres de messages, premiers champs](https://mypresta.eu/docs/images/docs/mycontactprotectionpro-filters.webp)

![Filtres de messages, champs suivants](https://mypresta.eu/docs/images/docs/mycontactprotectionpro-filters-content.webp)

Les filtres tournent dans la boutique, avant tout service externe. Sur une page de contact publique, laissez le honeypot et le temps minimum, et ajoutez les liens, les mots, les e-mails jetables ou les doublons quand la liste des blocages montre un motif qui se répète. Un client qui remplit le formulaire de façon ordinaire est accepté. Un script est refusé. Un captcha raté ou un envoi trop rapide ne bannit pas l'IP. Les autres filtres peuvent la bannir si la case de bannissement est cochée dans **Protection**.

| Champ | Au départ | Ce qu'il fait |
|---|---|---|
| **Champ honeypot** | Oui | Ajoute un champ caché que les gens ne voient pas. Le client le laisse vide et le message continue. Un script qui remplit chaque champ est bloqué, et **Protection** peut bannir cette IP. Éteignez-le si un remplissage automatique remplit le champ caché et bloque vos clients. |
| **Temps minimum sur la page** | Oui | Bloque un envoi plus rapide que la limite après le démarrage du script de la page. Un client qui lit et écrit a besoin de plus de quelques secondes. Un script qui envoie tout de suite est bloqué. L'absence du compteur est acceptée, un navigateur sans JavaScript peut donc encore envoyer. Ce blocage ne bannit pas l'IP. Éteint, il laisse passer les envois immédiats par ce contrôle. |
| **Secondes minimum** | 3 | Secondes. Utilisées quand le temps minimum est activé. 1 seconde attrape encore un script immédiat et touche rarement un client. 15 secondes ou plus bloquent un client qui connaît déjà le texte et envoie vite. Le compteur démarre quand le script de la page tourne. Un 0 enregistré est traité comme 1. |
| **Limiter les liens dans le message** | Oui | Compte http://, https:// et www. dans le message. Activé quand le spam reçu est surtout des liens. Désactivé quand les clients collent souvent une adresse de produit. Désactivé accepte un message plein de liens. Activé, avec un maximum bas, bloque aussi un client qui colle plusieurs adresses. |
| **Nombre maximum de liens** | 3 | Un message avec plus de liens est bloqué. Compté seulement quand la limite de liens est activée. 3 laisse coller quelques adresses. 0 bloque chaque message qui contient un lien, même vers une page produit. Une valeur haute, par exemple 20, laisse passer un spam de liens typique. |
| **Mots bloqués** | Non | Recherche sans tenir compte de la casse dans l'e-mail et dans le message. Activez-le après avoir ajouté des phrases vues dans le spam. Éteint, ou activé avec une liste vide, ne bloque rien. Un mot court et courant bloque aussi un vrai client qui l'a utilisé. |
| **Mots et expressions** | vide | Un mot ou une expression par ligne. Utilisé quand les mots bloqués sont activés. Laissez vide jusqu'à copier des phrases du vrai spam. Une expression correspond n'importe où dans l'e-mail ou le message, un bout court comme win correspond donc aussi à window et bloque une question ordinaire. Une expression longue et précise ne bloque que ce texte. |
| **Bloquer les e-mails jetables** | Non | Bloque une liste intégrée de domaines de boîtes temporaires et les domaines ajoutés dessous. Activé quand vous ne voulez pas de messages de boîtes jetables. Une adresse ordinaire est acceptée. Une boîte temporaire de la liste est bloquée, et **Protection** peut bannir cette IP. Les domaines absents de la liste passent encore jusqu'à ce que vous les ajoutiez. Désactivé accepte chaque domaine. |
| **Domaines jetables supplémentaires** | vide | Un domaine par ligne, par exemple dropmail.test. Utilisé quand les e-mails jetables sont bloqués. Laissez vide jusqu'à ce qu'un domaine apparaisse dans la liste des tentatives. Un domaine saisi ici bloque aussi ses sous-domaines. Ne tapez pas @. Saisir un vrai fournisseur de messagerie bloque chaque client qui l'utilise. |
| **Bloquer les messages en double** | Non | Bloque le même texte renvoyé dans la fenêtre, depuis n'importe quelle IP. Activé quand la même publicité part de beaucoup d'adresses. Les messages de moins de 20 caractères sont ignorés, un court bonjour peut donc être renvoyé. Un nouvel essai de captcha n'est pas traité comme un doublon. Un client qui envoie deux fois la même longue question dans la fenêtre est bloqué la seconde fois. Désactivé permet de renvoyer le même texte. |
| **Fenêtre des doublons** | 60 minutes | Combien de temps le texte est retenu. Une fenêtre courte, par exemple 5 minutes, oublie vite le texte, le même spam peut donc revenir. Une fenêtre longue, par exemple 1440 minutes (un jour), bloque aussi un client qui renvoie la même question plus tard le même jour. Utilisée seulement quand le blocage des doublons est activé. Un 0 enregistré est traité comme 1. |
| **Bloquer un user agent vide** | Non | Bloque une requête qui n'envoie pas d'identifiant de navigateur. Laissez-le éteint sauf si les tentatives montrent du spam avec un identifiant vide. Les vrais navigateurs en envoient un. Activé bloque aussi les outils de confidentialité qui retirent l'identifiant, ces clients ne peuvent donc pas envoyer. Désactivé ignore un identifiant vide. |
| **Ignorer les contrôles pour les clients connectés** | Non | Un client connecté saute tous les contrôles, y compris un bannissement actif. Laissez-le éteint dans une boutique où chacun peut s'inscrire. Activez-le si vos clients ont des comptes auxquels vous faites confiance. Les visiteurs sont toujours contrôlés. Activé laisse passer un robot connecté. Désactivé contrôle les clients connectés comme les visiteurs, une adresse de bureau bannie reste donc bannie aussi pour un compte. |

### 3.8 Liste blanche

![Liste blanche](https://mypresta.eu/docs/images/docs/mycontactprotectionpro-whitelist.webp)

La liste blanche, ce sont les adresses IP qui sautent tous les contrôles, y compris un bannissement actif. Ajoutez votre bureau, une agence ou un outil de surveillance qui envoie un message de test. Tous les autres sont toujours contrôlés. Une liste vide signifie qu'aucune adresse n'est sautée. Une ligne ajoutée par erreur laisse passer cette adresse, y compris un robot qui l'utilise.

| Champ | Au départ | Ce qu'il fait |
|---|---|---|
| **Adresses IP** | vide | Une adresse par ligne. Une ligne qui se termine par * correspond au début de l'adresse, par exemple 192.168.1.*. Laissez vide sauf si une adresse doit toujours pouvoir écrire, comme votre bureau. Une adresse complète saute les contrôles seulement pour cette IP. Un préfixe avec une étoile saute toute la plage, y compris chaque robot de cette plage. Une faute de frappe ne correspond à rien, ce visiteur reste donc protégé. Comparez IPv4 et IPv6 exactement comme la boutique les montre. |

### 3.9 Protection

![Protection](https://mypresta.eu/docs/images/docs/mycontactprotectionpro-protection.webp)

Un contrôle raté refuse toujours le message. Les cases sous **Que faire du spam** sont des étapes en plus pour un bannissement, le honeypot, le flood, les filtres, StopForumSpam et CleanTalk. Elles ne tournent pas quand le seul problème est le captcha ou un envoi trop rapide. Un client qui passe les contrôles n'est pas concerné.

| Champ | Au départ | Ce qu'il fait |
|---|---|---|
| **Actions supplémentaires** | aucune cochée | **Bannir l'adresse IP** : activé quand la même adresse revient. Le message suivant de cette IP est refusé jusqu'à ce que vous éteigniez le bannissement. Une IP de bureau partagée bloque alors chaque client qui l'utilise. **Envoyer un e-mail à la boutique** : activé si vous voulez un avis dans la boîte. Un e-mail par IP, puis silence pendant 30 minutes. Éteint, le spam bloqué reste seulement dans la liste des tentatives. **Rediriger vers la page d'accueil**, **Rediriger vers une page CMS** et **Rediriger vers Google** : laissez-les éteints pour que le visiteur reste sur la page de contact et lise l'erreur. Si plusieurs redirections sont cochées, la page d'accueil passe en premier, puis la page CMS, puis Google. |
| **Page CMS** | la première page de la liste de la boutique | Utilisée quand **Rediriger vers une page CMS** est cochée. Choisissez une page courte qui dit que le message n'a pas été envoyé. Si la boutique n'a pas de pages CMS, la liste contient **Aucune page CMS**. Sans page choisie, la redirection CMS est ignorée. Si **Rediriger vers Google** est aussi cochée, Google est utilisé ensuite. Sinon le visiteur reste sur la page de contact avec l'erreur. Un client qui passe les contrôles ne voit jamais cette page à cause du module. Les pages de la liste sont les pages CMS de la boutique. Si la boutique a déjà des pages, le choix vide enregistré n'est pas dans la liste, la première page s'affiche donc. Cliquez sur **Enregistrer** seulement quand c'est la page voulue. |

### 3.10 E-mail

![E-mail](https://mypresta.eu/docs/images/docs/mycontactprotectionpro-mail.webp)

Le panneau **E-mail à la boutique** règle l'objet de l'e-mail envoyé à l'adresse de la boutique quand un message est bloqué. L'e-mail part seulement si **Envoyer un e-mail à la boutique** est coché dans **Protection**, et seulement pour les blocages autres qu'un captcha raté ou un envoi trop rapide. Un e-mail part au premier blocage d'une IP. Les blocages suivants de cette IP pendant 30 minutes n'envoient pas de courrier. Un client accepté ne déclenche pas cet e-mail. Si l'e-mail de la boutique dans les paramètres de la boutique est vide, aucun courrier ne part.

| Champ | Au départ | Ce qu'il fait |
|---|---|---|
| **Objet** | Contact form spam blocked | Objet de l'avis à la boutique. Le nom court du contrôle est ajouté à la fin, par exemple [flood]. Le message va à l'e-mail de la boutique défini dans les paramètres de la boutique. Un objet court, que les règles de votre boîte reconnaissent, rempli pour chaque langue de la boutique. Un objet vide est remplacé par Contact form spam blocked. L'objet ne change pas qui est bloqué. |

Le bouton de langue passe l'objet à une autre langue de la boutique. Le corps du courrier est le modèle du module pour cette langue. Le texte anglais commence par **Contact form blocked.** puis indique le contrôle, l'IP, l'e-mail, la date et le début du message.

### 3.11 Mises à jour

![Mises à jour](https://mypresta.eu/docs/images/docs/mycontactprotectionpro-updates.webp)

Cette page demande à MyPresta.eu s'il existe une version plus récente du module. Les réglages ici ne concernent que la vérification des mises à jour. Ils ne changent pas la protection de la page de contact.

| Champ | Au départ | Ce qu'il fait |
|---|---|---|
| **Vérifier les mises à jour** | — | **Vérifier maintenant** demande tout de suite à MyPresta.eu s'il existe une version plus récente. Utilisez-le après l'installation et de nouveau avant une période chargée. Le bouton ne télécharge pas et n'installe pas de fichier. Si le serveur de la boutique n'atteint pas MyPresta.eu, le clic ne montre pas de nouvelle version. |
| **Notifications de mises à jour** | Activer | **Activer** interroge MyPresta.eu et affiche un avis dans le back-office quand une version plus récente est publiée. La vérification automatique a lieu environ tous les 3 jours pendant que vous travaillez dans le back-office. **Désactiver** arrête cette vérification et l'avis. Une nouvelle version reste alors inaperçue jusqu'à ce que vous cliquiez sur **Vérifier maintenant**. Ce choix ne change pas la protection du formulaire. |
| **Page du module** | Contact page - spam protection PRO | Un lien direct vers la page du module sur MyPresta.eu. Le journal des modifications de cette page montre ce qui a changé. Ouvrez-la avant une mise à jour. Le lien n'installe pas de fichier. Si la page ne charge pas, ouvrez l'adresse dans un nouvel onglet. |

**Enregistrer** confirme **Paramètres de mise à jour enregistrés.**

Quand une version plus récente existe, le back-office peut afficher **Nouvelle version disponible, consultez http://MyPresta.eu pour plus d'informations** et **Plus de détails dans le journal des modifications**. **Vérifier maintenant** répond **Nouvelle version disponible !** ou **Le module est à jour !**

### 3.12 Tentatives d'envoi de messages

![Tentatives d'envoi de messages](https://mypresta.eu/docs/images/docs/mycontactprotectionpro-attempts.webp)

Ouvrez **Tentatives d'envoi de messages** sous **Protection du contact**, ou le bouton du même nom dans la **Vue d'ensemble**.

La boutique écrit une ligne quand un message de contact est contrôlé. Il n'y a pas de bouton d'ajout. Vous ne modifiez pas une ligne depuis cette liste. Vous pouvez supprimer une ligne.

Les colonnes sont **ID**, **IP**, **E-mail**, **Motif**, **Bloqués** et **Date**. La ligne la plus récente est en premier. Une liste vide dit, sur la capture en anglais, **No records found**.

**Motif** dans cette liste est le nom court, pas le nom long de la **Vue d'ensemble** :

| Dans la vue d'ensemble | Dans cette liste |
|---|---|
| **IP bannie** | ban |
| **Honeypot** | honeypot |
| **Trop rapide** | timing |
| **User agent vide** | user-agent |
| **Anti-flood** | flood |
| **Message en double** | duplicate |
| **Trop de liens** | links |
| **Mot bloqué** | keyword |
| **E-mail jetable** | disposable |
| **reCAPTCHA** | recaptcha |
| **StopForumSpam** | stopforumspam |
| **CleanTalk** | cleantalk |

Un message autorisé a un motif vide et **Bloqués** sur non.

L'action de ligne est la suppression. Cochez des lignes et utilisez **Supprimer la sélection**. La boutique demande **Supprimer les éléments sélectionnés ?**

### 3.13 Adresses IP bannies

![Adresses IP bannies](https://mypresta.eu/docs/images/docs/mycontactprotectionpro-bans.webp)

Ouvrez **Adresses IP bannies** sous **Protection du contact**, ou le bouton du même nom dans la **Vue d'ensemble**.

Les colonnes sont **ID**, **IP**, **Date** et **Actif**. La ligne la plus récente est en premier. Une liste vide dit, sur la capture en anglais, **No records found**.

Le signe plus ouvre l'ajout. Le titre du formulaire est **Adresse IP bannie**.

![Nouvelle adresse IP bannie](https://mypresta.eu/docs/images/docs/mycontactprotectionpro-ban-form.webp)

| Champ | Au départ | Ce qu'il fait |
|---|---|---|
| **Adresse IP** | vide | Une adresse IP. Obligatoire. Tant que le bannissement est actif, les messages de contact de cette IP sont refusés. Collez l'adresse de la liste des tentatives, exactement comme elle a été enregistrée. Un chiffre faux bannit un autre visiteur, ou personne. Une adresse de bureau partagée bloque aussi de vrais clients sur cette IP jusqu'à ce que vous éteigniez le bannissement. |
| **Actif** | Non | **Oui** maintient le bannissement et le formulaire refuse cette IP. **Non** garde la ligne et arrête le blocage, l'adresse peut donc réécrire sauf si un autre contrôle l'arrête. Choisissez **Oui** tant que cette adresse envoie encore du spam. Choisissez **Non** quand un client à cette IP doit passer et que vous voulez garder la ligne. Un bannissement créé depuis **Protection** est enregistré déjà actif. |

**Enregistrer** enregistre la ligne. Annuler revient à la liste sans enregistrer.

Sur une ligne existante, **Modifier** ouvre le même formulaire, la suppression retire la ligne, et l'icône **Actif** allume ou éteint le bannissement. Cochez des lignes et utilisez **Supprimer la sélection**. La boutique demande **Supprimer les éléments sélectionnés ?**

Un bannissement de **Protection** refuse le message de contact suivant de cette IP avec le motif **IP bannie** (nom court ban) et ne crée pas un second bannissement pour le même résultat.

## 4. Boutique

Le module ne travaille que sur la page de contact de la boutique. Il n'ajoute rien aux autres pages.

Avec les réglages de l'installation, avant d'enregistrer les deux clés reCAPTCHA, le client voit le formulaire de contact ordinaire du thème. Il n'y a rien de plus à capturer sur la page : le honeypot est hors de l'écran, le compteur est caché, et la case reCAPTCHA n'est pas affichée.

Après avoir enregistré les deux clés et laissé **Activer reCAPTCHA** sur Oui :

- **reCAPTCHA v2** ajoute la case. Si le client envoie sans la cocher, la page dit **Veuillez confirmer que vous n'êtes pas un robot.** et le formulaire ne part pas.
- **reCAPTCHA v3** n'ajoute pas de défi. Le badge Google peut apparaître. Un score sous le seuil est refusé sur le serveur.

| Ce qui s'est passé | Ce que voit le client |
|---|---|
| Case v2 non cochée | **Veuillez confirmer que vous n'êtes pas un robot.** Le formulaire reste sur la page. |
| Captcha raté, ou Google injoignable | **La vérification captcha a échoué. Veuillez réessayer.** |
| Tout autre blocage, et aucune redirection cochée | **Votre message n'a pas pu être envoyé. Veuillez réessayer dans quelques minutes.** |
| Redirection vers la page d'accueil cochée | La page d'accueil de la boutique. Pas d'erreur sur la page de contact. |
| Redirection CMS cochée, une page choisie, et pas celle vers l'accueil | Cette page CMS. |
| Redirection vers Google cochée, et les autres ne sont pas utilisées | https://www.google.com |

Un message qui passe est envoyé par le formulaire de contact comme d'habitude. Le module ne change pas cette confirmation.

Le thème peut remplacer la feuille de style et le script de la boutique. Il ne peut pas remplacer un modèle de module pour le formulaire, parce que le formulaire est celui de la boutique. Si le thème retire le bouton d'envoi de ce formulaire, le honeypot, le compteur et le captcha ne s'accrochent pas.

## 5. Problèmes

**Le client voit « Veuillez confirmer que vous n'êtes pas un robot. »**

La case v2 n'était pas cochée. Demandez-lui de la cocher et de renvoyer. Cela ne bannit pas l'IP.

**Le client voit « La vérification captcha a échoué. Veuillez réessayer. »**

Le captcha n'est pas passé, ou la boutique n'a pas joint Google. Vérifiez que le **Type de reCAPTCHA** correspond à la clé de la console Google, que **Clé du site** et **Clé secrète** sont la paire de ce domaine, et que le serveur de la boutique joint Google. Un captcha raté ne bannit pas l'IP. Le client peut réessayer.

**Le client voit « Votre message n'a pas pu être envoyé. Veuillez réessayer dans quelques minutes. »**

Un autre contrôle a refusé le message, et aucune redirection n'est cochée. Ouvrez **Tentatives d'envoi de messages**, trouvez l'IP ou l'e-mail et lisez **Motif**. Puis :

- flood : augmentez **Messages autorisés** ou **Fenêtre de temps**, ou attendez que la fenêtre passe.
- honeypot : un script ou le remplissage automatique a rempli le champ caché. Éteignez **Champ honeypot** si vos propres clients sont bloqués.
- timing : le formulaire est parti plus vite que **Secondes minimum**. N'augmentez ce nombre que si de vrais clients sont bloqués. Ce blocage ne bannit pas l'IP.
- user-agent : éteignez **Bloquer un user agent vide** si un outil de confidentialité est en cause.
- duplicate : le même texte d'au moins 20 caractères a été renvoyé dans la **Fenêtre des doublons**.
- links : le message a plus de liens que **Nombre maximum de liens**.
- keyword : une ligne de **Mots et expressions** correspond à l'e-mail ou au message.
- disposable : le domaine de l'e-mail est dans la liste intégrée ou dans **Domaines jetables supplémentaires**.
- stopforumspam ou cleantalk : l'adresse est dans ce service. Augmentez **Signalements minimum** ou **Seuil du taux de spam**, ou ajoutez l'adresse à la **Liste blanche** si c'est un client.
- ban : l'adresse est dans **Adresses IP bannies** avec **Actif** sur **Oui**. Mettez **Non**, ou supprimez la ligne.

**Le client arrive sur la page d'accueil, une page CMS ou Google.**

Il y a eu un blocage dur et une redirection est cochée dans **Protection**. Décochez **Rediriger vers la page d'accueil**, **Rediriger vers une page CMS** et **Rediriger vers Google** si vous voulez que l'erreur reste sur la page de contact. Quand plusieurs sont cochées, la page d'accueil gagne, puis la page CMS, puis Google.

**Tout un bureau ne peut pas écrire.**

Le bureau partage une IP. Cette IP est bannie, au-dessus de la limite anti-flood, ou listée dans un service. Ouvrez **Adresses IP bannies** et mettez **Actif** sur **Non**, ou ajoutez l'adresse à la **Liste blanche**. Une ligne de liste blanche saute tous les contrôles, y compris le bannissement.

**reCAPTCHA reste éteint.**

L'avertissement dit **reCAPTCHA est activé, mais la clé du site ou la clé secrète est vide. Le captcha reste désactivé tant que les deux clés ne sont pas enregistrées.** Collez les deux clés et cliquez sur **Enregistrer**.

**Le CleanTalk payant ne bloque personne.**

L'avertissement dit **L'API payante CleanTalk est activée, mais la clé d'accès est vide.** Collez **Clé d'accès** et cliquez sur **Enregistrer**. Une clé refusée laisse aussi passer le message. Si le service ne répond pas, le message passe.

**Aucun e-mail n'arrive à la boutique.**

**Envoyer un e-mail à la boutique** doit être coché. Le blocage doit être autre chose que le captcha ou trop rapide. La même IP n'envoie qu'un courrier en 30 minutes. L'e-mail de la boutique dans les paramètres de la boutique doit être rempli. L'objet reçoit le nom court du contrôle, par exemple [flood].

**Vérifier maintenant ne montre rien de nouveau.**

Le serveur de la boutique n'a pas joint MyPresta.eu, ou le module est déjà à jour. La réponse **Le module est à jour !** signifie qu'aucune version plus récente n'a été signalée. **Vérifier maintenant** ne télécharge pas le fichier.

**Les listes sont vides après une nouvelle installation.**

La désinstallation efface les tentatives et les bannissements. Une nouvelle installation ne les ramène pas.

## 6. Pour les développeurs

### 6.1 Vue d'ensemble

Classe principale `mycontactprotectionpro`, version `1.0.0`, auteur MyPresta.eu, onglet `administration`. Le nom dans la liste est **Contact page - spam protection PRO**. La compatibilité dans le fichier est PrestaShop 1.7.7.0 à 9.99.99.

Les réglages sont lus avec `Configuration::get` dans le contexte de boutique actif au clic sur **Enregistrer**. Un POST de la page de contact avec `submitMessage` lance `hookActionFrontControllerInitAfter`. Un passage écrit une ligne autorisée et laisse le formulaire envoyer. Un blocage écrit une ligne bloquée, et un motif dur peut créer un bannissement, envoyer le courrier à la boutique et rediriger.

`install()` appelle l'installation parente, écrit la configuration, crée les deux tables, crée le menu et enregistre les trois hooks. Il ne vide pas le cache. Il n'y a pas de `enable()` ni de `disable()` propre. `uninstall()` efface les clés du 6.7 plus `update_mycontactprotectionpro` et `updatev_mycontactprotectionpro`, efface les onglets du menu, fait un DROP des deux tables et appelle la désinstallation parente. Il n'efface pas `mypresta_updates`. Les fichiers restent jusqu'à la suppression du dossier du module.

### 6.2 Fichiers

| Fichier | Rôle |
|---|---|
| mycontactprotectionpro.php | install, uninstall, hooks, formulaires, ordre des contrôles, tableau de bord, courrier à la boutique |
| controllers/admin/AdminMycontactprotectionpro.php | parent du menu ; redirige vers la configuration du module |
| controllers/admin/AdminMycontactprotectionproAttempts.php | liste des tentatives et suppression |
| controllers/admin/AdminMycontactprotectionproBans.php | liste des bannissements, ajout, édition, suppression, interrupteur active |
| models/attempt.php | table des tentatives et compteurs |
| models/ban.php | table des bannissements et `banIp()` |
| lib/sfs.php | consultation StopForumSpam |
| lib/ctalk.php | CleanTalk gratuit et payant |
| lib/updatesChecker.php | vérification des mises à jour, classe `mycontactprotectionproUpdate` |
| lib/recaptcha/ | bibliothèque reCAPTCHA utilisée par le module |
| views/templates/admin/configure.tpl | barre d'onglets et balisage de la vue d'ensemble |
| views/css/admin.css | mise en page de la configuration dans le back-office |
| views/css/front.css | place le honeypot hors de l'écran |
| views/js/front.js | honeypot, compteur, case v2 et jeton v3 sur le formulaire |
| mails/{iso}/mcpp_merchant.html | corps HTML de l'avis ; ne passe pas par `$this->l()` |
| mails/{iso}/mcpp_merchant.txt | corps texte de l'avis |
| translations/{iso}.php | textes du back-office et du client |
| key.php | valeur envoyée avec la requête CleanTalk gratuite |

Il n'y a pas de contrôleur front ni de modèle front pour le formulaire de contact.

### 6.3 Contrôleurs

| Classe | Parent dans le menu | Ce qu'elle accepte |
|---|---|---|
| AdminMycontactprotectionproController | id 0, icône security, titre Contact protection | redirige vers AdminModules avec `configure=mycontactprotectionpro` |
| AdminMycontactprotectionproAttemptsController | AdminMycontactprotectionpro | table `mcpp_attempt`, ordre `id_mcpp_attempt` DESC, `list_no_link`, suppression de ligne, suppression groupée. Pas d'ajout. |
| AdminMycontactprotectionproBansController | AdminMycontactprotectionpro | table `mcpp_ban`, ordre `id_mcpp_ban` DESC, édition et suppression de ligne, suppression groupée, statut sur `active`. Formulaire : `ip` (obligatoire) et `active`. |

La configuration est `getContent()` du module, pas un contrôleur séparé. L'onglet passe par `mcpp_tab`. Les noms d'envoi sont `submitMcppAntiFlood`, `submitMcppCleanTalk`, `submitMcppStopForumSpam`, `submitMcppRecaptcha`, `submitMcppFilters`, `submitMcppWhitelist`, `submitMcppProtection`, `submitMcppMail`. Le formulaire des mises à jour envoie `submit_settings_updates` et `submit_settings_updates_now`.

Il n'y a pas de contrôleur front. La page de contact est le `ContactController` de la boutique.

### 6.4 Hooks

| Hook | Quand il tourne |
|---|---|
| actionFrontControllerSetMedia | sur la page de contact, quand le honeypot, le compteur ou un reCAPTCHA prêt est actif ; ajoute front.css et front.js et passe les réglages publics au script |
| actionFrontControllerInitAfter | sur un POST de la page de contact avec submitMessage ; contrôle puis revient, arrête le formulaire ou redirige |
| displayBackOfficeHeader | ajoute views/css/admin.css |

Le module n'enregistre pas de hook d'affichage à lui. La page de contact est reconnue par `php_self` égal à `contact`, ou par la classe `ContactController` ou `ContactControllerCore`.

Dans le back-office, le constructeur appelle `runUpdateSetUp()`. Cette méthode interroge MyPresta environ toutes les 259200 secondes quand `mypresta_updates` n'est pas 0, range le résultat dans `updatev_mycontactprotectionpro` et ajoute un avertissement du contrôleur quand la version enregistrée est plus récente.

### 6.5 Surcharges

Le module ne livre aucune surcharge de classe ni de contrôleur.

### 6.6 Base

Le préfixe est celui de la boutique. L'ouverture d'une page n'ajoute pas de colonne. La désinstallation supprime les deux tables.

| Table | Contenu |
|---|---|
| mcpp_attempt | `id_mcpp_attempt` int clé primaire, `ip` varchar 64, `email` varchar 255, `message_hash` varchar 64 (MD5 du message en minuscules), `reason` varchar 255 (nom court, vide si autorisé), `blocked` tinyint, `date_add` datetime. Clés `ip_date` (`ip`, `date_add`) et `hash_date` (`message_hash`, `date_add`). |
| mcpp_ban | `id_mcpp_ban` int clé primaire, `ip` varchar 64, `date_add` datetime, `active` tinyint, défaut 1. Clé `ip_active` (`ip`, `active`). Le formulaire d'ajout s'ouvre avec Actif sur Non. `banIp()` insère ou met à jour la ligne avec `active` 1. |

### 6.7 Clés et traductions

Valeur quand la clé manque :

| Clé | Si elle manque |
|---|---|
| mcpp_af | 1 |
| mcpp_time | 10 |
| mcpp_atmpt | 5 |
| mcpp_ct | 0 |
| mcpp_ct_paid | 0 |
| mcpp_ct_key | vide |
| mcpp_ct_rate | 1, et un 0 enregistré est aussi traité comme 1 |
| mcpp_sfs | 0 |
| mcpp_sfs_key | vide |
| mcpp_sfs_freq | 1, et un 0 enregistré est aussi traité comme 1 |
| mcpp_rc | 1 |
| mcpp_rc_type | 0, soit v2 ; 1 est v3 |
| mcpp_rc_site | vide |
| mcpp_rc_secret | vide |
| mcpp_rc_theme | light, sauf si la valeur enregistrée est dark |
| mcpp_rc_score | 0.5 |
| mcpp_hp | 1 |
| mcpp_tg | 1 |
| mcpp_tg_sec | 3, et un 0 enregistré est traité comme 1 |
| mcpp_links | 1 |
| mcpp_links_max | 3 |
| mcpp_kw | 0 |
| mcpp_kw_list | vide |
| mcpp_disp | 0 |
| mcpp_disp_extra | vide |
| mcpp_dup | 0 |
| mcpp_dup_min | 60, et un 0 enregistré est traité comme 1 |
| mcpp_ua | 0 |
| mcpp_bypass | 0 |
| mcpp_ptype_1 | 0, bannir l'IP |
| mcpp_ptype_4 | 0, e-mail à la boutique |
| mcpp_ptype_7 | 0, redirection vers l'accueil |
| mcpp_ptype_6 | 0, redirection CMS |
| mcpp_ptype_5 | 0, redirection vers Google |
| mcpp_cms | 0 |
| mcpp_wh_ip | vide |
| mcpp_mtitle | Contact form spam blocked, par langue ; un objet vide utilise cette phrase anglaise |
| mcpp_dash_preset | 30 ; toute autre valeur que 7, 30, 90, 180, 365 ou custom revient à 30 |
| mcpp_dash_from | vide jusqu'à ce que la vue d'ensemble construise la fenêtre |
| mcpp_dash_to | vide jusqu'à ce que la vue d'ensemble construise la fenêtre |

`mypresta_updates` est partagé. S'il manque, les notifications sont traitées comme activées. La désinstallation ne le supprime pas. `key.php` affecte `mkey`. S'il est vide, la requête CleanTalk gratuite utilise `nlc`. La vérification des mises à jour utilise `nokey` quand la valeur manque.

Domaines jetables intégrés, reconnus sur le domaine et ses sous-domaines : mailinator.com, guerrillamail.com, guerrillamail.info, guerrillamail.biz, guerrillamail.de, guerrillamail.net, guerrillamail.org, guerrillamailblock.com, sharklasers.com, grr.la, yopmail.com, yopmail.fr, yopmail.net, trashmail.com, trashmail.de, trash-mail.com, tempmail.com, temp-mail.org, 10minutemail.com, 10minutemail.net, throwawaymail.com, getnada.com, dispostable.com, maildrop.cc, fakeinbox.com, mailnesia.com, mohmal.com, emailondeck.com, tempail.com, moakt.com, spam4.me, byom.de, mintemail.com, mytemp.email, tmpmail.net, tmpmail.org, discard.email, discardmail.com, inboxkitten.com, getairmail.com, generator.email, mailcatch.com. Les domaines de `mcpp_disp_extra` s'ajoutent de la même façon.

Les libellés, les descriptions de champs et les trois phrases client sont `$this->l()` dans `mycontactprotectionpro.php`, `lib/updatesChecker.php` (source `updatesChecker`), `AdminMycontactprotectionproAttempts.php` (source `AdminMycontactprotectionproAttempts`) et `AdminMycontactprotectionproBans.php` (source `AdminMycontactprotectionproBans`). Ajoutez une langue avec `translations/{iso}.php`. Les descriptions de champs sont dans le `desc` des champs HelperForm de la classe principale et du contrôleur des bannissements.

Les corps de `mails/{iso}/mcpp_merchant.html` et `mails/{iso}/mcpp_merchant.txt` ne passent pas par `$this->l()`. Le texte anglais commence par `Contact form blocked.` L'objet est `mcpp_mtitle` de la langue du courrier, avec le motif court ajouté, par exemple ` [flood]`. Le courrier va à `PS_SHOP_EMAIL`. Un e-mail de boutique vide n'envoie rien. Le corps contient les 500 premiers caractères du message sans balises.

### 6.8 Extension

Un thème peut surcharger `views/css/front.css` et `views/js/front.js`. Il n'y a pas de modèle front pour le formulaire, le thème n'a donc pas de modèle de formulaire du module à surcharger. Le balisage est le formulaire de contact de la boutique. `front.js` cherche `form [name=submitMessage]`. Si ce bouton manque, le script revient et n'ajoute rien.

Le nom du honeypot est `mcpp_website`. Le nom du compteur est `mcpp_ts`. Un honeypot rempli est un résultat. L'absence du compteur n'en est pas un. Un compteur dans le futur en est un. reCAPTCHA v3 utilise l'action `contact`.

L'ordre des contrôles est fixe : ban, honeypot, timing, user agent vide, flood, duplicate, links, keyword, disposable, recaptcha, stopforumspam, CleanTalk gratuit, CleanTalk payant. Le premier résultat gagne. La liste blanche et l'exception du client connecté reviennent avant qu'une ligne soit écrite. Si `protectionEnabled()` est faux et que l'IP n'est pas bannie, le hook revient sans écrire. `protectionEnabled()` est vrai quand l'un de `mcpp_af`, `mcpp_ct`, `mcpp_ct_paid`, `mcpp_sfs`, `mcpp_hp`, `mcpp_tg`, `mcpp_links`, `mcpp_kw`, `mcpp_disp`, `mcpp_dup`, `mcpp_ua` vaut 1, ou quand reCAPTCHA est prêt (interrupteur activé et les deux clés non vides).

Les motifs durs sont tous les motifs sauf `timing` et `recaptcha`. Seul un motif dur peut créer un bannissement, envoyer le courrier à la boutique et rediriger. La priorité de redirection est `mcpp_ptype_7` (accueil), puis `mcpp_ptype_6` quand `mcpp_cms` est supérieur à 0, puis `mcpp_ptype_5` (`https://www.google.com`). Sinon le module retire `submitMessage` et ajoute l'erreur. Un blocage recaptcha utilise la phrase du captcha. Tout autre blocage qui reste sur la page utilise la phrase des quelques minutes.

Le CleanTalk gratuit est ignoré quand `openssl_encrypt` n'existe pas. StopForumSpam et CleanTalk laissent passer le message quand l'appel distant échoue. reCAPTCHA bloque le message quand l'appel distant échoue. Le flood utilise `countByIpSince`, qui compte chaque tentative de la fenêtre. Le doublon utilise `countDuplicateSince`, qui ignore les lignes dont le motif est `timing` ou `recaptcha`, et ne tourne que si le message fait au moins 20 caractères.

Appels PHP : `curl_init` s'il existe, sinon `file_get_contents` pour StopForumSpam, CleanTalk et la vérification des mises à jour quand `allow_url_fopen` est actif. `openssl_encrypt` pour la requête CleanTalk gratuite. `json_decode` pour les réponses de StopForumSpam, du CleanTalk payant et de reCAPTCHA. Aucun autre module n'est nécessaire.

## 7. Aide

Page du module : https://mypresta.eu/modules/administration-tools/contact-page-spam-protection-pro.html

Pour une question sur ce module, connectez-vous au compte client sur [https://mypresta.eu/](https://mypresta.eu/) et ouvrez le formulaire de contact. Choisissez le sujet **Support for paid modules**. Le formulaire indique que la connexion est obligatoire. Ensuite, choisissez ce module dans l'historique des achats. La page est [https://mypresta.eu/contact-form](https://mypresta.eu/contact-form).
