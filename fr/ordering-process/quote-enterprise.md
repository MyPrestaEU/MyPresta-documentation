---
title: "Quote Enterprise - manuel marchand"
sidebar:
  label: "Quote Enterprise - manuel marchand"
description: "Comment configurer Quote Enterprise, dérouler le processus complet du devis à la commande, et résoudre les problèmes courants."
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Quote Enterprise sur MyPresta.eu](https://mypresta.eu/modules/ordering-process/quote-enterprise.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/ordering-process/quote-enterprise/)
>
> ---


## 1. Requirements

Le module fonctionne sur PrestaShop 1.7, 8 et 9, et sur PHP 7.1 à 8.5.

Le serveur a besoin de cURL et de JSON. Aucun autre module n’est requis.

Vous créez vous-même les clés Google reCAPTCHA uniquement si vous activez reCAPTCHA. Les webhooks Slack ou Teams sont facultatifs et servent uniquement aux digests destinés au personnel. Les e-mails de rappel et les digests nécessitent une tâche cron serveur sur l’URL cron du module.

## 2. Installation

1. Téléversez le module dans **Modules**, **Module Manager**, et activez-le.
2. Après l’installation, **Orders** contient deux entrées : **Quotes** et **Audit log**.
3. Le module ne vide pas le cache pendant l’installation.
4. L’installation crée les tables de devis et un produit virtuel masqué pour les lignes de service personnalisées. Elle enregistre aussi les paramètres par défaut décrits ci-dessous.

La désinstallation retire les entrées de menu, les tables du module et les clés de configuration. Le produit de frais masqué dans le catalogue n’est pas supprimé à la désinstallation.

## 3. Configuration and back-office work

Ouvrez **Modules**, **Module Manager**, **Quote Enterprise**, **Configure**. Le module s’ouvre sur **Dashboard**. La barre supérieure contient : **Dashboard**, **Quotes**, **Audit log**, **Settings**, **PDF**, **Emails**, **API**, **Notifications**, **Updates**.

Les captures d’écran de ce manuel proviennent d’un back-office en anglais.

Le travail quotidien sur les devis se trouve aussi sous **Orders**, **Quotes** (liste complète et éditeur) et **Orders**, **Audit log**.

### 3.1 Full quote process

Utilisez ce flux comme carte. Les sections ci-dessous détaillent chaque écran.

1. Un client demande un devis depuis une fiche produit, une liste de produits, le panier, ou une liste de devis multi-produits. Les visiteurs peuvent voir les boutons si cela est autorisé, mais l’enregistrement de la demande exige toujours un compte client.
2. La demande devient un devis en **Pending review** (demande client) ou le personnel crée un **Draft** depuis le back-office.
3. Le personnel ouvre le devis sous **Orders**, **Quotes**, définit les prix, remises, livraison et messages, puis **Save** ou **Save & send**.
4. **Save & send** envoie un e-mail au client et passe le devis en **Sent** (ou conserve le flux de négociation lors d’un renvoi).
5. Le client ouvre **My quotes**, consulte l’offre, peut télécharger le PDF, accepter, refuser, ou demander des modifications (**Negotiation**).
6. Après **Accepted**, le client peut passer commande. Le checkout construit un panier à partir du devis et peut devenir une commande (**Converted**). Le devis se verrouille alors.
7. Passé **valid until**, les devis envoyés ou en négociation deviennent **Expired** à l’ouverture ou lors de l’exécution du cron. Les e-mails de rappel nécessitent le cron.

Statuts que vous verrez : **Draft**, **Pending review**, **Sent**, **Negotiation**, **Accepted**, **Converted**, **Expired**, **Rejected**, **Cancelled**.

Seuls **Sent** et **Negotiation** peuvent être acceptés par le client. Modifiez le statut manuellement dans l’éditeur si nécessaire.

### 3.2 Dashboard

Le tableau de bord affiche le pipeline des devis. Ouvrez **Analytics parameters** pour définir la période des KPI et les plages des graphiques, puis cliquez sur **Save analytics parameters**. Confirmation : **Tracking parameters updated.**

![Dashboard](https://mypresta.eu/docs/images/docs/quoteenterprise-dashboard.webp)

![Dashboard tables](https://mypresta.eu/docs/images/docs/quoteenterprise-dashboard-b.webp)

| Field | At the start | What it does |
|---|---|---|
| **KPI period** | **Last 90 days** | Fenêtre temporelle pour les cartes KPI, le tableau d’entonnoir, les meilleurs clients et le personnel. Choisissez 30, 90, 180 ou 365 jours et enregistrez. Compte les devis créés, envoyés, acceptés, convertis et refusés sur cette période. |
| **Weekly chart range** | 12 | Nombre de semaines sur le graphique d’entonnoir hebdomadaire (4–52). L’onglet Weekly affiche créés, envoyés, acceptés et convertis par semaine ISO. |
| **Monthly chart range** | 12 | Nombre de mois sur le graphique d’entonnoir mensuel (3–24). |
| **Yearly chart range** | 5 | Nombre d’années sur le graphique d’entonnoir annuel (2–10). |
| **Default chart tab** | **Monthly** | Quel onglet de graphique s’ouvre en premier : Weekly, Monthly ou Yearly. Vous pouvez toujours changer d’onglet sans enregistrer. |
| **Expiring soon window** | 7 | Nombre de jours à l’avance pour signaler les devis bientôt expirés. En général 7 ou 14. Seuls les devis envoyés et en négociation avec une date valid_until dans cette fenêtre sont listés. |

Cartes KPI : valeur du pipeline ouvert, en attente de revue, bientôt expirés, valeur convertie, taux de conversion, taux de succès. En dessous : créés, envoyés, acceptés, convertis, refusés, durée moyenne jusqu’à conversion, valeur moyenne du devis. Les graphiques montrent l’entonnoir dans le temps. Tableaux : entonnoir de période, vieillissement du pipeline ouvert, bientôt expirés, activité récente, meilleurs clients et personnel. Le pipeline ouvert désigne les devis envoyés, en négociation ou acceptés.

### 3.3 Quotes tab in module configuration

Cet onglet est un aperçu court. Les filtres complets, actions groupées et l’éditeur se trouvent sous **Orders**, **Quotes**.

![Quotes overview](https://mypresta.eu/docs/images/docs/quoteenterprise-quotes.webp)

Rôle de cet écran : une liste rapide des devis récents depuis la configuration du module. Cliquez sur **View** pour ouvrir l’éditeur de devis complet. Utilisez **Manage all quotes** pour les filtres, l’export et les opérations groupées. Effet : la configuration du module reste légère tandis que le travail complet sur les devis se fait dans l’écran back-office dédié.

**Create quote :** sélectionnez un client (recherche), saisissez éventuellement une **Internal note**, cliquez sur **Create draft quote**. Vous êtes redirigé vers l’éditeur complet. Client vide : **Please select a customer.**

**Quote templates** (lorsque des modèles existent) : choisissez un modèle et un client, puis **Create from template**.

Colonnes **Recent quotes** : Reference, Customer, Status, Total. Vide : **No quotes yet.** Liens : **Manage all quotes**, **CSV**, **XML**, **Open full quotes list**.

### 3.4 Quotes list (Orders menu)

Ouvrez **Orders**, **Quotes**. C’est l’écran de gestion principal.

Colonnes : **ID**, **Reference**, **Customer**, **Status**, **Total**, **Valid until**, **Assigned**, **Created**. Actions de ligne : éditer et dupliquer. Vous ne pouvez pas ajouter un devis vide depuis la barre d’outils de la liste ; créez depuis l’aperçu du module, depuis un modèle, ou par duplication. Erreur si vous essayez : **Create quotes from module configuration or duplicate an existing quote.**

Actions groupées :

| Action | What it does |
|---|---|
| **Assign to employee** | Définit l’employé assigné sur les devis sélectionnés. |
| **Extend validity** | Repousse la date de validité pour la sélection. |
| **Send expiry reminder** | Envoie des e-mails de rappel aux clients sélectionnés (dialogue de confirmation). |
| **Export CSV** | Télécharge un CSV pour la sélection. |
| **Export XML** | Télécharge un XML pour la sélection. |

Filtrez par statut et recherchez comme sur une liste PrestaShop standard. Ouvrez une ligne pour éditer.

### 3.5 Quote editor — how to manage a request

Ouvrez un devis depuis la liste. La légende affiche la référence et le statut, par exemple `Q-2026-00001 — Pending review`.

**Parcours type du personnel pour une nouvelle demande client**

1. Filtrez ou ouvrez les devis en **Pending review**.
2. Consultez **Messages from customer** (texte de la demande, motifs de modification ou de refus ultérieurs). Lecture seule.
3. Ajoutez ou ajustez **Line items** (produits du catalogue et services personnalisés).
4. Définissez **Global discount %** / **Global discount amount**, **Shipping label** et les montants de livraison.
5. Rédigez **General message to customer** et éventuellement **Internal note**.
6. Définissez **Validity period** et **Validity unit**, vérifiez la date de validité actuelle.
7. Définissez **Status** si nécessaire, puis **Save** (**Quote saved.**) ou **Save & send** (**Quote sent to customer by e-mail.**).

**Verrouillage.** Les devis acceptés ou convertis se verrouillent. Devis expirés : **This quote has expired. Click Unlock to extend validity and send an updated offer.** Convertis : **This quote is locked because it was converted to an order.** Acceptés : **This quote is locked because the customer accepted it. Click Unlock to make changes.** Déverrouillage : **Quote unlocked for editing.** Reverrouillage : **Quote locked again.**

| Field | What it does (from field descriptions) |
|---|---|
| **Status** | Étape actuelle du parcours commercial. Draft : interne uniquement. Pending review : demandé par le client, en attente de votre tarification. Sent : envoyé par e-mail au client. Accepted : le client a accepté. Converted : devenu une commande. Seuls Sent et Negotiation peuvent être acceptés par le client. Modifiez le statut manuellement si nécessaire. |
| **Validity period** | Durée pendant laquelle le client peut accepter, comptée à partir de l’enregistrement / l’envoi. Exemples : 15 avec Minutes, 1 avec Hours, 30 avec Days. L’enregistrement recalcule l’expiration à partir de maintenant. Le client ne peut plus accepter après expiration. Des périodes courtes peuvent expirer avant que le cron quotidien n’envoie les rappels. |
| **Validity unit** | Minutes, heures ou jours avec le nombre de validité. |
| **Payment hint** | Courte note sur le paiement attendu, p. ex. « 30 days net transfer ». Affichée sur la vue client et le PDF. N’impose pas de module de paiement. |
| **Global discount %** | Remise supplémentaire 0–100 sur toutes les lignes produits avant livraison. Au checkout, elle peut s’appliquer comme règle panier. |
| **Global discount amount (tax excl.)** | Remise fixe sur le sous-total produits. Le pourcentage est appliqué en premier lorsque les deux sont définis. |
| **Shipping label** | Nom sur le PDF, p. ex. « Express delivery ». |
| **Shipping (tax excl.)** / **Shipping (tax incl.)** | Frais de livraison. Le TTC se calcule automatiquement à partir du HT lorsqu’une règle de taxe est définie dans les paramètres du module. Inclus dans le total et transmis au checkout comme livraison fixe. |
| **Messages from customer** | Tout ce que le client a écrit (demande, demande de modification, refus). Lecture seule. Répondez dans les champs ci-dessous. |
| **General message to customer** | Message permanent toujours visible pour le client (périmètre, délai, conditions). Affiché sur la vue devis, le PDF et les e-mails. |
| **Internal note** | Note privée d’équipe. Jamais montrée au client. |
| **Line items** | Lignes produits et lignes de service personnalisées. Ajoutez un produit catalogue (choisissez la déclinaison si besoin). Ajoutez une ligne personnalisée : description, qté, prix unitaire HT, taxe %. Les lignes personnalisées apparaissent sur le PDF et, au checkout, passent dans le produit de frais. Messages : **Product line added.**, **Custom line added.**, **Line removed.**, **Select a product to add.**, **Please select a product combination.**, **Enter a service line description.** |
| **Comment for this send** | Note ponctuelle pour ce **Save & send** uniquement. Explique ce qui a changé. Effacée après l’envoi. Apparaît dans la chronologie, l’historique PDF optionnel, et l’e-mail de cet envoi. |
| **Version history** | Instantanés des versions précédentes. |
| **Save as template** | Saisissez un nom de modèle et enregistrez. Créez ensuite de nouveaux devis depuis ce modèle pour un autre client. Messages : **Please enter a template name.**, **Template "…" saved.** |
| **Quote timeline** | Chronologie des événements personnel et client sur ce devis. |

Dupliquez depuis la liste ou l’éditeur : **Unable to duplicate quote.** en cas d’échec. Après duplication, vous éditez la copie.

### 3.6 Audit log

Onglet du module : activité récente (demandes, envois, acceptation/refus, négociations). Utilisez **View** pour le contexte complet. Ouvrez **Orders**, **Audit log** pour les filtres, l’export et l’historique complet.

Objectif : journal en ajout uniquement pour la conformité et le diagnostic. Les entrées ne peuvent pas être modifiées ni supprimées. Chaque ligne stocke le nom et l’ID de l’acteur (employé ou client) au moment de l’action. Badges d’acteur : Employee, Customer, System.

### 3.7 Settings — Theme & display

Ouvrez **Settings**. Cliquez sur **Save** en bas après les modifications.

![Theme and display](https://mypresta.eu/docs/images/docs/quoteenterprise-settings-theme.webp)

| Field | At the start | What it does |
|---|---|---|
| **Front theme template** | **Auto-detect (recommended)** | Choisit le jeu de templates et de CSS utilisé pour My quotes, l’aperçu du devis et le lien du compte client. Laissez Auto-detect sauf si votre fork de thème est mal détecté — forcez alors Classic ou Hummingbird. |
| **Quantity display format** | **Integer (e.g. 1, 2)** | Affichage des quantités de lignes en front-office, back-office, PDF et e-mails. Ou **Fixed decimals (e.g. 1.000, 2.500)**. Les champs de formulaire utilisent le même format pour les valeurs par défaut. |
| **Quantity decimal places** | 3 | Chiffres après la virgule lorsque le format est en décimales fixes. En général 3 pour le B2B ou 2 pour le retail. Ignoré en mode entier. |

### 3.8 Settings — General

![General](https://mypresta.eu/docs/images/docs/quoteenterprise-settings-general.webp)

| Field | At the start | What it does |
|---|---|---|
| **Module enabled** | **Yes** | Interrupteur principal de toute la fonctionnalité devis-vers-commande. Yes : les clients demandent des devis et le personnel gère les offres. No : masquer tous les boutons de devis et les liens du compte client sans désinstaller. Lorsqu’il est désactivé, aucune nouvelle demande et aucun bouton sur le panier, les fiches ou les pages catégorie. Les devis existants restent dans le back-office. |
| **Product page quote button** | **Yes** | Affiche **Request a quote** sur chaque fiche produit. Pour les boutiques B2B où les acheteurs demandent un prix sur un SKU unique. Le client doit être connecté (ou le flux invité autorisé) et dans un groupe autorisé. Le mode Instant ouvre le formulaire pour ce produit. Le mode List ajoute la quantité et la déclinaison à la liste de devis flottante. |
| **Cart quote button** | **Yes** | Affiche **Request a quote** sur le panier. Activez lorsque les clients demandent une offre pour plusieurs produits à la fois. Respecte le total panier minimum ci-dessous. Le contenu actuel du panier devient la base d’une nouvelle demande de devis après confirmation. |
| **Category / list quote button** | **Yes** | **Request quote** compact sur les pages de liste (catégorie, recherche, nouveautés). Mêmes règles d’éligibilité. Le mode Instant ouvre le flux de devis produit. Le mode List ajoute le produit (déclinaison par défaut, qté 1) à la liste flottante. |
| **Product quote mode** | **Instant — open form for this product** | Instant : ouvrir le formulaire pour le produit courant. List : ajouter à un panier de devis ; le bouton flottant ouvre un formulaire avec tous les produits. Les demandes depuis le panier restent indépendantes. Le bouton flottant n’apparaît qu’en mode List lorsque la liste n’est pas vide. |
| **Floating quote button position** | **Bottom right** | Ou **Bottom left**. Uniquement lorsque le mode de devis produit est List. Le badge affiche le nombre de produits ; ouvre le formulaire de demande multi-produits. |
| **Allow guests** | **No** | Indique si les visiteurs sans compte peuvent démarrer une demande. Laissez désactivé pour un B2B strict. Activez si les invités doivent voir le bouton — ils doivent tout de même se connecter ou s’inscrire avant l’enregistrement de la demande. Ne crée pas de devis anonymes. |

### 3.9 Settings — Quote button visibility

![Visibility](https://mypresta.eu/docs/images/docs/quoteenterprise-settings-visibility.webp)

| Field | At the start | What it does |
|---|---|---|
| Customer groups | all groups | Restreint qui peut voir les boutons de devis. Tous les groupes, ou seulement les groupes sélectionnés (p. ex. Wholesale). Les clients hors des groupes sélectionnés ne verront pas les boutons même si le module est activé. |
| **Enable catalog visibility rules** | **No** | Active ou désactive les règles de boutons de devis basées sur le catalogue. Activez pour limiter les devis à des produits, catégories, marques ou fournisseurs précis. Lorsqu’elles sont désactivées, tout produit peut être demandé (les règles de groupes s’appliquent toujours). Lorsqu’elles sont activées, la liste blanche / noire et les filtres ci-dessous sont appliqués. |
| **Catalog rule mode** | **Whitelist — only matching products** | Whitelist : boutons uniquement sur les produits correspondants. Blacklist : masquer les boutons sur les produits correspondants. Un produit correspond s’il est dans la liste produits ou appartient à une catégorie, fabricant ou fournisseur sélectionné. |
| Catalog pickers | empty | Catégories (arbre), produits (recherche), fabricants et fournisseurs. Laissez vide pour n’appliquer que les filtres auxiliaires. Les règles se combinent en OU — une correspondance suffit. |
| **Minimum product price** | 0 | Masquer les boutons de devis sous ce prix TTC vitrine. 0 désactive. Appliqué lorsque les règles catalogue sont activées. |
| **Exclude virtual products** | **No** | Empêche de demander un devis pour les produits téléchargeables / virtuels lorsque les règles catalogue sont activées. |
| **Exclude out-of-stock products** | **No** | Masque les boutons lorsque le produit ne peut pas être commandé en rupture (respecte le comportement PrestaShop hors stock). |
| **Mixed cart (eligible + excluded items)** | **Hide cart quote button** | Lorsque le panier mélange produits cotables et non cotables : Show = bouton visible, seules les lignes éligibles importées ; Hide = bouton masqué jusqu’à ce que le panier ne contienne que des articles cotables. Tous éligibles → toujours afficher. Tous exclus → toujours masquer. |

### 3.10 Settings — Product quote request form

| Field | At the start | What it does |
|---|---|---|
| **Require privacy policy acceptance** | **Yes** | Case de confidentialité obligatoire sur la modale de demande de devis produit (RGPD). Les clients doivent accepter avant d’envoyer. |
| **Privacy policy CMS page** | none | Page CMS liée depuis la case. Si vide, le texte de la case n’a pas de lien. |
| **Enable reCAPTCHA** | **No** | Protège le formulaire de demande de devis produit avec Google reCAPTCHA v2. Lorsqu’il est activé, les clés site et secrète ci-dessous sont obligatoires. |
| **reCAPTCHA site key** | empty | Clé site publique depuis l’admin Google reCAPTCHA (case à cocher v2). |
| **reCAPTCHA secret key** | empty | Clé secrète. Stockée dans la configuration de la boutique. |
| **Minimum cart total** | 0 | Valeur minimale du panier avant d’afficher le bouton de devis panier. Devise par défaut de la boutique. 0 = pas de minimum. N’affecte que le bouton panier, pas les demandes mono-produit. Les petits paniers n’afficheront pas le bouton. |

### 3.11 Settings — Offers & references

| Field | At the start | What it does |
|---|---|---|
| **Default validity** | 30 | Durée par défaut pendant laquelle un devis reste valide après création. Nombre plus unité : minutes pour les offres flash, heures pour les décisions le jour même, jours pour le B2B standard. Définit valid_until sur les nouveaux devis depuis la boutique, le back-office et les duplicatas. Surchargez par devis dans l’éditeur. |
| **Default validity unit** | **Days** | Minutes, heures ou jours avec le nombre ci-dessus. Les e-mails de rappel et le statut Expired automatique s’appuient toujours sur le cron pour les rappels. |
| **Expiry reminder (days before)** | 3 | E-mail de rappel avant expiration. Envoyé uniquement par la tâche cron quotidienne. Chaque devis éligible reçoit au plus un rappel avec un lien pour consulter et accepter. Sans cron, pas de rappels. |
| Cron URL | generated token | Rappels d’expiration et mises à jour de statut automatisés. Ajoutez l’URL au crontab une fois par jour (exemple 08:00). Régénérez le jeton s’il a été exposé. L’expiration est aussi appliquée à l’ouverture du devis ; les e-mails de rappel nécessitent toujours le cron. |
| **Reference prefix** | Q | Préfixe des numéros de devis. Le module ajoute l’année et la séquence, p. ex. Q-2026-00042. Aide le personnel et les clients à reconnaître les documents dans les e-mails et le PDF. |
| **Notify staff on new request** | **Yes** | E-mail au personnel de la boutique lorsqu’un client envoie une demande. Vérifiez que Preferences > Contact e-mail est correct. Modèle : qe-request-staff dans l’onglet Emails. |

Avis jaune à l’écran : le cron est requis pour l’automatisation de la validité ; l’expiration s’applique aussi à l’ouverture ; les rappels utilisent l’URL cron.

### 3.12 Settings — Checkout

| Field | At the start | What it does |
|---|---|---|
| **Shipping / service tax rule** | shop default tax rule | Règle de TVA pour la livraison et les lignes de service personnalisées lorsque vous saisissez des montants hors taxe. Choisissez un groupe de règles de taxe dans Catalog → Products. Une fois sélectionné, l’enregistrement d’un devis recalcule la livraison TTC à partir du HT. |
| **Fee product (custom lines)** | created on install | Produit virtuel masqué qui porte les lignes de service personnalisées jusqu’au checkout. Créé automatiquement — ne changez que si vous devez pointer les lignes personnalisées vers un autre produit. Au checkout, les totaux de service deviennent une ligne panier avec le prix de devis verrouillé. |

### 3.13 PDF

Ouvrez l’onglet **PDF**. Légende : **PDF documents**. Lorsque le PDF est désactivé, les boutons de téléchargement sont masqués et les URL PDF renvoient introuvable.

| Field | At the start | What it does |
|---|---|---|
| **Enable PDF** | **Yes** | Interrupteur principal pour la génération PDF et les liens de téléchargement. Désactivez si vous ne souhaitez pas de proformas PDF. Lorsqu’il est désactivé, les boutons PDF sont masqués en back-office, boutique et détail de commande ; les URL PDF directes renvoient introuvable. Les modèles d’e-mail reçoivent toujours un placeholder d’URL PDF vide. |
| **Use shop logo on PDF** | **Yes** | Utilise le logo de la boutique depuis Preferences > Themes. No : utiliser uniquement un logo personnalisé téléversé ci-dessous (s’il y en a un). Le logo apparaît en haut des documents PDF / proforma. |
| **Add negotiation history to PDF** | **No** | Ajoute un court journal de communication (demandes de modification, renvois, acceptation, refus). Tableau compact avant les conditions. Vide s’il n’y a pas d’activité de négociation. |
| **Custom PDF logo** | empty | PNG ou JPG facultatif pour les PDF de devis uniquement. Remplace le logo boutique lorsqu’il est présent. |
| **PDF terms & conditions** | empty | Conditions légales ou commerciales en bas de chaque PDF. |
| **Authorized signature** | empty | Nom ou ligne du signataire, p. ex. « John Smith, Sales Director ». Laissez vide pour omettre. |

### 3.14 Emails

Ouvrez l’onglet **Emails**. E-mails transactionnels du cycle de vie du devis. Modifiez l’objet et le corps par langue. Utilisez les placeholders de la barre latérale de l’éditeur (nom client, référence devis, lien, totaux). Clés intégrées : qe-request-staff, qe-quote-sent, qe-quote-accepted, qe-quote-rejected, qe-quote-negotiation, qe-quote-reminder, qe-staff-digest. Clients et personnel les reçoivent lorsqu’un devis est demandé, envoyé, accepté, ou sur le point d’expirer. Testez après modification.

### 3.15 API

Ouvrez l’onglet **API**. Connectez CRM, ERP ou automatisation. Saisissez un libellé de clé et **Generate new API key**. Copiez la clé. **Revoke** la désactive (confirmation). Vide : **No API keys yet.** **API documentation** décrit les actions : list, get, pending, stats, update_status. Appelez l’URL API du module avec la clé.

### 3.16 Notifications

Ouvrez **Notifications** (**Staff digest notifications**). Résumé périodique lorsque des devis nécessitent une action, sans un e-mail par événement.

Ce qui compte comme en attente : **Pending review** (nouvelle demande) ou **Negotiation** (le client a demandé des modifications). Sent, accepted, expired et converted ne sont pas inclus. Le cron s’exécute selon votre planning. Lorsque le digest est activé, qu’au moins un devis est en attente, et que l’intervalle est écoulé, un message part vers chaque canal configuré. Le personnel voit un résumé avec références, statut, nom client et liens back-office (jusqu’à 20 devis listés).

| Field | At the start | What it does |
|---|---|---|
| **Enable digest** | **No** | Interrupteur principal. Activez après avoir configuré au moins un canal. Le cron doit être planifié — les digests ne sont pas envoyés par les visites de page. Lorsqu’il est désactivé, le cron gère toujours les rappels d’expiration et les mises à jour de statut, mais pas de digest. |
| **Interval (hours)** | 24 | Délai minimum entre digests (1–168). Exécutez le cron au moins aussi souvent que cette valeur. Après un digest réussi, le suivant attend que ce nombre d’heures soit passé. |
| **E-mail recipients** | empty | Séparés par virgule ou point-virgule. Vide utilise l’e-mail boutique de Preferences > Contact. Modèle qe-staff-digest. |
| **Slack webhook URL** | empty | URL de webhook entrant. Laissez vide pour ignorer Slack. |
| **Teams webhook URL** | empty | URL de webhook connecteur. Laissez vide pour ignorer Teams. |

**Save** enregistre les paramètres. **Send test digest now** envoie un test lorsque des devis sont en attente. Même URL cron que Settings.

### 3.17 Updates

Ouvrez **Updates**. **Check Now** recherche une nouvelle version. **Automatic Notifications** activé ou désactivé. **Save** enregistre les paramètres de mise à jour.

### 3.18 Quote block on an order

Sur une commande créée depuis un devis, le back-office affiche **Source quote** avec un lien vers le devis et éventuellement **View quote PDF**.

## 4. Front office

Les clients voient les outils de devis lorsque le module est activé et que leur groupe est autorisé.

**Product page.** **Request a quote** ouvre le formulaire (instant) ou ajoute à la liste de devis (mode list). La case de confidentialité et reCAPTCHA s’appliquent lorsqu’ils sont activés.

**Product list.** **Request quote** — mêmes règles.

**Cart.** **Request a quote** — respecte le total panier minimum et les règles de panier mixte. Le panier confirmé devient un devis en attente.

**List mode.** Le bouton flottant avec un compteur ouvre le formulaire de demande multi-produits.

**Customer account.** Lien vers **My quotes** : historique, statut, valid until, **View**, PDF si activé, **Checkout** après acceptation, **Request re-opening** lorsqu’expiré/verrouillé. Vide : **You have no quotes yet. Request a quote from a product page or your cart to get started.** Après envoi : **Your quote request has been submitted. Our team will prepare an offer shortly.**

**Quote view.** Accepter, refuser, demander des modifications, télécharger le PDF, checkout une fois accepté. Expiré verrouillé : **Locked — validity expired**.

Les visiteurs invités peuvent voir les boutons si **Allow guests** est **Yes**, mais la demande n’est enregistrée que pour un client connecté.

Il n’y a pas de capture d’écran boutique dans ce pack car la boutique de test n’était pas accessible lorsque les écrans ont été finalisés.

## 5. Common problems

**Pas de bouton de devis sur le produit ou le panier.** Vérifiez **Module enabled**, l’interrupteur de bouton correspondant, le groupe client, et la visibilité catalogue. Pour le panier, vérifiez **Minimum cart total** et **Mixed cart**.

**Un invité ne peut pas terminer une demande.** L’envoi exige toujours un compte.

**Le devis est verrouillé / impossible d’éditer.** Déverrouillez s’il est accepté ou expiré (prolongez la validité). Les devis convertis restent verrouillés sur la commande.

**Le client ne peut pas accepter.** Le statut doit être Sent ou Negotiation, et valid until doit être dans le futur.

**Les e-mails de rappel n’arrivent jamais.** Planifiez l’URL cron et gardez **Expiry reminder** au-dessus de zéro. Ouvrir un devis peut l’expirer sans cron ; les rappels nécessitent toujours le cron.

**Boutons PDF manquants.** Activez **Enable PDF**.

**reCAPTCHA bloque le formulaire.** Désactivez-le, ou saisissez les deux clés.

**Le digest personnel n’arrive jamais.** Activez le digest, configurez un canal, exécutez le cron au moins aussi souvent que l’intervalle.

**Désinstallé et le menu a disparu.** Réinstallez. La désinstallation supprime les tables de devis. Le produit de frais peut rester dans le catalogue.

## 6. Developer guide

### 6.1 Overview

Nom technique `quoteenterprise`, version 1.7.6, classe `quoteenterprise` extends `Module`. Nom d’affichage via `$this->l('Quote Enterprise')`. Auteur MyPresta.eu. Onglet `checkout`. URL produit dans `$this->mypresta_link`.

Flux : demande → ligne `quote` → édition/envoi par le personnel → acceptation/négociation client → checkout → commande. Les textes de champs pour les marchands se trouvent dans `QuoteSettingDescTrait` et les méthodes `desc*` de l’éditeur de devis.

### 6.2 Files

- `quoteenterprise.php` — installation, hooks, entrée de configuration, URL cron.
- `classes/QuoteAdmin.php` — onglets de configuration et formulaires de paramètres.
- `classes/QuoteAdminQuoteForm.php` — éditeur de devis.
- `classes/QuoteQuotesManager.php` — aperçu, enregistrement/envoi/lignes/modèles.
- `classes/QuoteDashboard.php`, `QuoteVisibility.php`, `QuoteListHelper.php`, `QuoteRequestHelper.php`, `QuoteMailer.php`, `QuotePdf.php`, `QuoteApi.php`, `QuoteNotifyDigest.php`, `QuoteExpiry.php`, `QuoteConverter.php`, `QuoteFeeProduct.php`, `QuoteSettingDescTrait.php`.
- `controllers/admin/AdminQuoteEnterpriseQuotes.php`, `AdminQuoteEnterpriseAuditLog.php`.
- `controllers/front/` — `list`, `view`, `request`, `quoteList`, `pdf`, `cron`, `api`.
- `models/` — `quote`, `quotedetail`, `quoteauditlog`, `quoterevision`, `quoteapikey`.
- `views/templates/`, `lib/updateChecker.php`, `lib/emailTemplatesManager/`, `lib/searchTool/`.

### 6.3 Controllers

Admin sous **Orders** (`AdminParentOrders`). Contrôleurs front dans `$this->controllers`. Le cron attend `QE_CRON_TOKEN`. L’API attend une clé active et un nom d’action.

### 6.4 Hooks

Enregistrés : `displayHeader`, `displayShoppingCart`, `displayCustomerAccount`, `displayProductAdditionalInfo`, `displayProductActions`, `displayFooterProduct`, `displayFooter`, `actionProductPriceCalculation`, `actionValidateOrder`, `actionAdminControllerSetMedia`, `displayProductListFunctionalButtons`, `displayProductListReviews`, `displayProductPriceBlock`, `displayAdminOrderMain`, `displayAdminOrderSide`, `displayAdminOrder`, `actionCartGetPackageShippingCost`. Aucun hook personnalisé exposé.

### 6.5 Overrides

Ce module ne livre pas d’overrides de classes ou de contrôleurs.

### 6.6 Database

| Table | Contents |
|---|---|
| `quote` | En-tête du devis. |
| `quote_detail` | Lignes. |
| `quote_revision` | Instantanés de version. |
| `quote_audit_log` | Activité en ajout uniquement. |
| `quote_api_key` | Clés API. |
| `qe_cart_quote` | Lien panier–devis. |

La désinstallation supprime ces tables. `QuoteSchema::ensure` et `inconsistency()` réparent les éléments manquants à l’ouverture de la configuration.

### 6.7 Keys and translations

Clés de configuration `QE_*`. Valeurs par défaut dans `installDefaults()`. Nouvelle langue : `translations/{iso}.php`. Aide des champs marchand : `QuoteSettingDescTrait` et méthodes `desc*` de l’éditeur. Chaînes via `$this->l()` et `{l s=... mod='quoteenterprise'}`.

### 6.8 Extending

Surchargez les templates front sous `modules/quoteenterprise/` dans le thème. Classic et Hummingbird sont pris en charge. Une mise en page PDF différente implique de modifier le template PDF ou le code du module.

## 7. Support

Page du module : [Quote Enterprise](https://mypresta.eu/modules/ordering-process/quote-enterprise.html).

Pour écrire à propos de ce module, connectez-vous à votre compte client sur [mypresta.eu](https://mypresta.eu/), ouvrez [Contact](https://mypresta.eu/contact.html) et choisissez le sujet **Support for paid modules**. Le formulaire indique que la connexion est requise. Après connexion, sélectionnez ce module dans votre historique d’achats.
