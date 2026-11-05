---
title: "Return Button Pro - documentation et manuel utilisateur"
description: "Configurez le formulaire de rétractation UE, gérez les dossiers dans le back-office et résolvez les problèmes courants si vous utilisez déjà Return Button Pro."
sidebar:
  label: "Return Button Pro - documentation et manuel utilisateur"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module EU Return Button – Online Withdrawal Form sur MyPresta.eu](https://mypresta.eu/modules/front-office-features/eu-return-button-online-withdrawal-form.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/front-office/eu-return-button-online-withdrawal-form/)
>
> ---



Les captures d’écran de ce manuel montrent le back-office en anglais. Utilisez les mêmes noms de menus et libellés que ceux indiqués ici.

## 1. Prérequis

Return Button Pro fonctionne sur PrestaShop 1.6, 1.7, 8 et 9. Utilisez le paquet adapté à votre boutique : le build dédié PrestaShop 1.6 pour les boutiques 1.6, et le build PrestaShop 1.7–9 pour les versions plus récentes. Lorsque les deux paquets sont disponibles dans l’historique de commandes MyPresta.eu, téléchargez le ZIP qui correspond.

- PrestaShop : 1.6.x, 1.7.x, 8.x et 9.x
- PHP : les versions déjà utilisées par votre PrestaShop, y compris les piles anciennes avec PrestaShop 1.6 (PHP 5.6 et PHP 7.x) et les versions exigées par PrestaShop 1.7–9 (PHP 7.1+ / PHP 8.x selon l’hébergement et la boutique). Le module est aussi maintenu pour les environnements PHP 7.x et le PHP actuel de la boutique.
- Extensions PHP utilisées par le module : JSON, curl (vérifications de mise à jour), fileinfo (contrôles MIME des pièces jointes), hash (jetons et sécurité invité)
- Autres modules : non requis. Si le module gratuit Return Button est installé et activé, désactivez-le avant de configurer ou d’utiliser Return Button Pro. Les deux ne peuvent pas fonctionner en même temps.
- Comptes externes : aucun. Les vérifications optionnelles de mise à jour MyPresta.eu utilisent Internet depuis l’onglet **Updates**.

## 2. Installation

1. Téléversez le ZIP du module dans **Modules** → **Module Manager**, puis installez et activez **Return Button Pro**.
2. Après l’installation, un élément **Withdrawals** apparaît sous **Customers**. Ouvrez la configuration via **Module Manager** → **Return Button Pro** → **Configure** (onglets : **Dashboard**, **Settings**, **Updates**).
3. L’installation ne vide pas le cache PrestaShop. Videz le cache vous-même après des changements de thème ou de hooks si la boutique front paraît encore incorrecte.

Désinstallation : l’entrée de menu **Withdrawals** est retirée et les valeurs de configuration sont supprimées. Les tables de rétractation et les dossiers restent dans la base de données comme preuve légale. Une réinstallation n’efface pas ces enregistrements ; le module peut les réutiliser lorsque les tables existent déjà. Les pièces jointes du personnel téléversées dans le dossier du module ne sont pas supprimées à la désinstallation.

Si vous migrez depuis le module gratuit Return Button, Pro peut copier les réglages compatibles et migrer des tables Pro vides à partir des données du module gratuit lorsque Pro n’a encore aucune ligne. Désactivez d’abord le module gratuit.

## 3. Configuration et travail en back-office

### 3.1 Processus complet de rétractation

Flux de bout en bout, du front-office au traitement par le personnel :

1. Le client trouve l’entrée de rétractation : bouton du pied de page, lien Mon compte, bouton sur le détail de commande, ou l’URL du formulaire lorsque l’accès invité est activé.
2. **Étape 1 – commande :** les clients connectés voient leurs commandes avec des indications d’éligibilité (jours restants, motifs d’indisponibilité). Les invités saisissent la référence de commande et l’e-mail. Le client sélectionne une commande éligible, choisit **Full order** ou **Partial** (avec quantités sur les lignes autorisées), ajoute éventuellement un message et un IBAN, puis continue.
3. **Étape 2 – confirmation :** le client examine le résumé de la déclaration. Lorsque **Require legal confirmation checkbox** est activé, il doit cocher le texte juridique, puis envoyer.
4. Le module enregistre le dossier, le passe en **Registered** et envoie la confirmation client (support durable) plus une notification boutique (et **Notification email** si défini). La page de succès affiche la référence de rétractation.
5. Le personnel ouvre **Customers** → **Withdrawals** (ou le panneau latéral de la commande), ouvre **View**, définit le statut (**In progress**, **Refunded**, **Rejected**, etc.) et saisit un message client lorsque c’est requis.
6. Le client suit le statut via **Track withdrawal status**, la page de statut et **Print / save PDF**. Les messages du personnel issus des changements de statut apparaissent dans l’historique de rétractation du client.

Statuts utilisés par le module :

| Champ | Au départ | Rôle |
|---|---|---|
| **Pending** | État bref lorsque la déclaration est d’abord enregistrée | Dossier ouvert avant la fin de la confirmation légale du client, ou lorsque le personnel fixe ce statut plus tard. Compte pour le blocage des doublons avec les autres statuts ouverts. |
| **Registered** | Après confirmation du client à l’étape 2 | Déclaration enregistrée ; tentatives d’e-mails de confirmation. Statut par défaut après envoi. |
| **In progress** | Action du personnel | La boutique traite le dossier (retours, contrôles, préparation du remboursement). Bloque toujours une seconde demande active si le blocage des doublons est actif. |
| **Refunded** | Action du personnel | Dossier clos avec remboursement. Visible sur la page de statut client. |
| **Rejected** | Action du personnel | Dossier clos sans remboursement. Utilisez un message client clair lorsque le réglage l’exige. |

Portée sur le formulaire : **Full order** ou **Partial**. Type : **Contract withdrawal** (payé) ou **Contract cancellation (unpaid order)** lorsque la commande n’a jamais été payée.

### 3.2 Dashboard

Ouvrez **Modules** → **Module Manager** → **Return Button Pro** → **Configure** → **Dashboard**.

![Dashboard](https://mypresta.eu/docs/images/docs/rbpro-dashboard.webp)

Filtrez avec **From** / **To** et **Apply**, ou réinitialisez avec **Last 30 days**. Le panneau affiche les totaux de tous les temps, le backlog en attente, le profil de thème détecté, le hook de pied actif, des KPI (rétractations sur la période, taux vs commandes, part de confirmation e-mail, jours moyens de la commande à la rétractation, part partielle/totale, annulations, part remboursée des dossiers clos, taux de rejet), un graphique des soumissions quotidiennes, la répartition des statuts, les produits les plus rétractés et les dossiers en attente les plus anciens avec **Open**.

Utilisez **Manage all withdrawals** pour la liste sous Customers, ou **Export CSV** pour télécharger les dossiers de la boutique actuelle.

### 3.3 Settings

Ouvrez l’onglet **Settings** et cliquez sur **Save** après les modifications.

![Settings](https://mypresta.eu/docs/images/docs/rbpro-settings.webp)

#### Intégration du thème

Adaptez le module à Classic, Hummingbird ou un thème personnalisé. Ajustez ces options si boutons ou formulaires semblent sans style après une mise à jour de thème.

| Champ | Au départ | Rôle |
|---|---|---|
| **Storefront theme profile** | Auto-detect | Choisit quels templates et CSS front-office le module charge (Classic vs Hummingbird). Style correct du bouton, mise en page du formulaire et apparence du lien Mon compte. Laissez Auto-detect sauf si le bouton est incorrect après un changement de thème ; forcez alors Classic-type ou Hummingbird-type selon votre thème actif. Après modification, videz le cache PrestaShop et actualisez le front. |
| **Footer button hook** | Auto (by theme profile) | Définit où le bouton de rétractation est injecté dans le pied de page. Auto suit le profil de thème (Hummingbird → displayFooterBefore, Classic → displayFooter). Si le bouton manque ou est mal aligné, essayez displayFooterBefore ou displayFooter manuellement, enregistrez, videz le cache et vérifiez le pied de la boutique. Pour un placement manuel, placez le hook personnalisé dans un template de thème et sélectionnez displayRbproButton ici ; gardez **Footer button** activé pour que le bouton n’apparaisse que dans ce template. |

#### Général et accès

| Champ | Au départ | Rôle |
|---|---|---|
| **Module enabled** | Yes | Interrupteur principal de tout le module. Lorsqu’il est désactivé, boutons de rétractation, formulaire, accès invité et suivi sont masqués sur le front ; les dossiers existants en back-office restent. Utilisez-le pour la maintenance ou une revue juridique sans désinstaller. |
| **Public status tracking page** | Yes | Active une page publique où les clients consultent le statut de rétractation avec référence + e-mail (sans connexion). Réduit les tickets « où en est mon retour ? ». Activez si vous voulez un lien **Track withdrawal status** à côté du bouton du pied ; communiquez la référence de l’e-mail de confirmation. Désactivez si vous gérez le statut uniquement par e-mail de compte ou téléphone. |
| **Guest access (order ref + email)** | Yes | Permet aux clients non connectés d’ouvrir le formulaire en saisissant référence de commande et e-mail à l’étape 1. Recommandé pour les ventes à distance B2C en UE. Désactivez si seuls les clients connectés peuvent se rétracter. Les sessions invité utilisent un cookie signé. |
| **Block duplicate active requests** | Yes | Empêche une seconde rétractation ouverte pour la même commande tant qu’une est déjà Pending, Registered ou In progress. Évite les doublons et les remboursements conflictuels. Gardez activé en production. Désactivez uniquement pour les tests ou des processus inhabituels de réclamation partielle. |
| **Require legal confirmation checkbox (step 2)** | Yes | Oblige le client à cocher une case à formulation juridique avant l’envoi. Trace de consentement explicite alignée sur les règles de rétractation UE. Modifiez le texte de la case par langue sous Texts & SEO. Si désactivé, l’envoi est quand même journalisé sans case obligatoire. |
| **Require message to customer when changing status** | Yes | Le personnel doit saisir un message au client avant de mettre à jour un statut de rétractation. Le message est stocké dans la piste d’audit et affiché sur la page de statut client. Désactivez uniquement si vous avez besoin de changements de statut rapides sans écrire à chaque fois. |
| **Show deadline countdown to customer** | Yes | Affiche combien de jours restent dans le délai légal de rétractation (liste de commandes et formulaire). Nécessite un mapping correct **Order state = delivered** et le délai de rétractation. Si les dates semblent incorrectes, vérifiez l’historique de commande et l’état livré. |
| **Optional IBAN field** | No | Ajoute un champ IBAN optionnel sur le formulaire pour les remboursements. Activez uniquement si vous remboursez par virement et que votre politique de confidentialité le couvre. Laissez désactivé si vous remboursez uniquement sur le moyen de paiement d’origine. |
| **Notification email** | Empty | Adresse supplémentaire qui reçoit les notifications de nouvelles rétractations (en plus du contact boutique). Exemple : returns@yourshop.com. Laissez vide pour n’utiliser que le flux mail par défaut de PrestaShop sans ce destinataire. |

#### Règles de rétractation

| Champ | Au départ | Rôle |
|---|---|---|
| **Withdrawal period (days from delivery)** | 14 | Jours calendaires dont disposent les clients pour se rétracter après que la commande est considérée livrée. Par défaut 14 pour les contrats à distance UE. Ne changez que si la loi ou vos CGV exigent une autre valeur. Le compte à rebours démarre à la date de livraison dérivée de l’historique de commande et de **Order state = delivered**. |
| **Order state = delivered** | Auto | État de commande qui marque les biens comme livrés (début du délai de rétractation). Choisissez l’état que vous définissez lorsque le colis est livré (par exemple Delivered, ou Shipped si c’est votre état final). Auto utilise une valeur sensée de votre boutique ; remplacez-la si les délais utilisent la mauvaise date. |
| **Allowed order statuses** | All order statuses | Contrôle quand les clients peuvent soumettre une rétractation selon l’état actuel de la commande. Choisissez **All order statuses** pour ignorer le filtre, ou **Only selected statuses** et déplacez des états de la colonne gauche vers **Allowed for withdrawal**. Les commandes hors liste apparaissent comme indisponibles dans la liste de commandes du compte. |
| **Excluded products** | Empty | Produits spécifiques non rétractables (biens scellés, sur mesure, etc.). Recherchez par nom ou conservez les ID ; les lignes exclues affichent le message d’exclusion sur le formulaire. |
| **Excluded product variants** | Empty | Variantes spécifiques exclues de la rétractation. Recherchez le produit, puis sélectionnez la variante. |
| **Excluded categories** | Empty | Tous les produits de ces catégories sont non rétractables. |
| **Excluded manufacturers** | Empty | Les produits de ces fabricants ne peuvent pas être rétractés. |
| **Excluded suppliers** | Empty | Les produits liés à ces fournisseurs ne peuvent pas être rétractés. |
| **Excluded customer groups** | Empty | Les clients de ces groupes ne peuvent pas utiliser la rétractation du tout (pas d’accès au formulaire, boutons masqués). |

#### Pied de page et apparence

| Champ | Au départ | Rôle |
|---|---|---|
| **Footer button** | Yes | Affiche l’appel à l’action principal de rétractation dans le pied de la boutique (hook configuré ci-dessus). Désactivez si vous ne voulez que les liens Mon compte et détail de commande. Nécessite **Module enabled** et un hook de pied correct. |
| **Footer theme** | Light footer (dark text) | Schéma de couleurs pour le texte et les liens du pied (pas le fond du bouton). Choisissez Light sur des pieds clairs, Dark sur des pieds noirs/sombres pour que **Track withdrawal status** reste lisible. Videz le cache après modification. |
| **Footer alignment** | Center | Alignement horizontal du bloc bouton du pied : Left, Center ou Right. N’affecte que la sortie du hook de pied. |
| **Button color** | #2563eb | Couleur de fond des boutons de rétractation (pied, détail de commande, etc.). Choisissez une couleur hex avec assez de contraste sur texte blanc. Ne change pas la couleur primaire du thème globalement. |
| **Custom CSS** | Empty | CSS supplémentaire sur les pages où apparaissent les boutons du module. Pour marges, polices ou masquage d’éléments sans éditer les fichiers du thème. Testez d’abord en staging. |
| **Link in customer account** | Yes | Ajoute une entrée de rétractation dans My Account. Recommandé activé. Désactivez uniquement si vous vous fiez seulement aux liens du pied ou de la commande. |
| **Link on order detail** | Yes | Affiche l’action de rétractation sur la page de détail de commande lorsque la commande est éligible. Les commandes bloquées affichent un motif court à la place du bouton. |

#### Texts & SEO

Remplissez chaque langue active de la boutique.

| Champ | Au départ | Rôle |
|---|---|---|
| **Noindex on form page** | Yes | Ajoute robots noindex,nofollow sur l’URL du formulaire de rétractation pour garder les pages juridiques/formulaire hors résultats de recherche. Désactivez uniquement si vous voulez indexer le formulaire volontairement. |
| **Button label** | Withdraw from contract | Texte de tous les boutons et liens de rétractation. Un libellé court fonctionne mieux dans le pied. Phrase principale orientée client du module. |
| **Exclusion message** | This product is excluded from the statutory right of withdrawal. | Affiché à côté des produits exclus sur le formulaire. Expliquez pourquoi l’article ne peut pas être sélectionné ; mentionnez vos CGV si besoin. |
| **SEO title** | Withdraw from contract | Titre HTML de la page du formulaire de rétractation (onglet du navigateur). Gardez sous environ 60 caractères par langue. |
| **SEO description** | Online withdrawal form for distance contracts. | Meta description du formulaire. Généralement inutilisée pour le ranking lorsque noindex est actif. Laissez vide pour omettre. |
| **Legal confirmation checkbox text** | I confirm that I am submitting a withdrawal statement and understand the legal consequences. | Libellé à côté de la case obligatoire à l’étape 2. Utilisez une formulation claire et adaptée au pays. Requis lorsque **Require legal confirmation checkbox** est activé. |

### 3.4 Updates

Ouvrez l’onglet **Updates**.

| Champ | Au départ | Rôle |
|---|---|---|
| **Manual Check** | — | Vérifie sur MyPresta.eu s’il existe une version plus récente du module. Vous voyez **New version available!** ou **Module is up to date!**. Nécessite curl et HTTPS sortant. |
| **Automatic Notifications** | Enabled (module default for update prefs) | Lorsqu’activé, le back-office peut afficher un avis qu’une nouvelle version existe. Enregistrez avec **Save**. |
| **Product Page** | Link on form | Ouvre la page produit officielle pour les informations de version. Utilisez Support (§7) pour l’aide aux modules payants après connexion. |

Si le module gratuit Return Button est encore activé, les réglages et actions de mise à jour sont bloqués jusqu’à sa désactivation.

### 3.5 Liste des rétractations

Allez dans **Customers** → **Withdrawals**.

![Withdrawals list](https://mypresta.eu/docs/images/docs/rbpro-withdrawals.webp)

Le tri par défaut est la soumission la plus récente en premier. Colonnes :

| Champ | Au départ | Rôle |
|---|---|---|
| **ID** | Auto | Id interne du dossier. |
| **Submitted** | From form | Date et heure de soumission par le client. |
| **Order** | From order | Référence de commande PrestaShop. |
| **First name** / **Last name** / **Email** | From customer | Identité de contact du dossier. |
| **Scope** | Full order or Partial | Si la commande entière ou des lignes sélectionnées ont été rétractées. |
| **Type** | Contract withdrawal or cancellation | Rétractation payée vs annulation de commande non payée. |
| **Status** | Registered after confirm | Statut actuel du dossier (Pending, Registered, In progress, Refunded, Rejected). |
| **Email** | Yes/No | Si l’e-mail de confirmation a été enregistré comme envoyé. |

Utilisez la recherche et le tri sur la liste. Ouvrez un dossier avec **View**. Il n’y a pas d’action **Add new** : les demandes ne sont créées que par les clients sur le front. Si quelqu’un tente de créer un dossier en back-office, l’avertissement explique que les rétractations ne peuvent pas être créées manuellement et la liste est réaffichée.

Exportez le CSV depuis **Dashboard** (**Export CSV**) lorsque vous avez besoin d’un tableur des dossiers de la boutique.

### 3.6 Vue du dossier de rétractation

Ouvrez une ligne avec **View**.

L’en-tête affiche référence, ID, date de soumission, statut, type, portée, indicateur et heure d’e-mail envoyé, échéance, IP, user-agent, nom et e-mail du client, et un lien vers la commande PrestaShop. Le bloc produits liste chaque ligne rétractée avec quantité et prix unitaire. L’IBAN et le message client apparaissent lorsque le client les a fournis.

**Update status**

1. Choisissez **New status**.
2. Rédigez **Message to customer** (requis lorsque ce réglage est actif ; optionnel sinon). Le texte d’aide explique que le message apparaît dans l’historique de rétractation du front.
3. Cliquez sur **Update status**.

Succès : **Status updated.** Autres messages : **Please enter a message for the customer when changing the status.**, **Status is already set to this value.**, **Invalid status.**, **Could not update status.**

**Resend confirmation email** renvoie la confirmation client, met à jour l’indicateur d’envoi en cas de succès et journalise l’événement. Succès : **Confirmation email sent.** Échec : **Could not send email.**

**Internal notes** sont réservées au personnel. Saisissez du texte et cliquez sur **Add note**. Les notes apparaissent sous **Internal notes** et dans la piste d’audit ; elles ne remplacent pas le message de statut destiné au client.

**Attachments** acceptent les téléversements du personnel (PDF et images courantes, max. 10 Mo). Téléchargez en cliquant sur le nom du fichier. Messages : **Attachment uploaded.**, **Invalid file or size over 10 MB.**, **File type not allowed.**, **Upload failed.**

**Audit trail** liste date, événement, employé et détails (transitions de statut et messages). Événements typiques : le client a soumis la déclaration, le client a confirmé la déclaration légale, statut mis à jour, e-mail de confirmation envoyé, document ajouté, note interne ajoutée.

Utilisez **Back to list** pour revenir à **Withdrawals**.

### 3.7 Panneau latéral de commande en back-office

Sous PrestaShop 1.7.7 et plus récent, ouvrez une commande en back-office. Lorsque cette commande a des dossiers de rétractation, un bloc latéral **Withdrawal requests** liste chaque référence, badge de statut, date et **View** (ouvre le dossier). Sur les builds 1.7 plus anciens sans hook latéral de commande, utilisez **Customers** → **Withdrawals** et filtrez par référence de commande.

Les dossiers en attente peuvent aussi déclencher un avertissement back-office avec le nombre de demandes en attente de revue et un lien vers la liste.

## 4. Front-office

Aucune capture front-office n’est incluse ici ; branchez le thème et vérifiez la boutique en direct après avoir enregistré Settings et vidé le cache.

### 4.1 Pied de page

Avec **Footer button** activé et le bon hook, les pages affichent le bouton de rétractation (libellé de **Button label**) stylé avec **Button color**, plus **Track withdrawal status** lorsque le suivi public est actif. **Footer alignment** et **Footer theme** contrôlent la mise en page et le contraste du texte. Si le thème n’appelle jamais le hook de pied sélectionné, changez le hook ou placez le hook personnalisé dans un template et sélectionnez cette option sous **Footer button hook**.

### 4.2 Compte client

Avec **Link in customer account** activé, My Account affiche l’entrée de rétractation (et le lien de suivi lorsque le template de compte l’inclut). Les groupes clients exclus ne voient aucun point d’entrée.

### 4.3 Détail de commande

Avec **Link on order detail** activé, les commandes éligibles affichent le bouton de rétractation prérempli pour cette commande. Les dossiers existants de la commande sont listés avec le statut. Les commandes non éligibles affichent un motif court à la place du bouton, par exemple délai expiré, statut non autorisé, demande active en double, ou aucun produit éligible.

### 4.4 Accès invité

Lorsque **Guest access** est activé, un visiteur ouvre le formulaire, saisit référence de commande et e-mail, puis continue comme un client connecté pour cette commande. Lorsque l’accès invité est désactivé, les invités voient qu’ils doivent se connecter (ou que vous devez activer l’accès invité dans Settings). Les jetons de sécurité invalides et trop de tentatives affichent des messages clairs d’attente / nouvel essai.

### 4.5 Suivi du statut

**Track withdrawal status** demande la référence de rétractation (format du type RBP-…) et l’e-mail, puis affiche le statut, la date de soumission, la portée, l’état de l’e-mail de confirmation et des liens vers les détails et l’impression. Mauvaise paire : **No withdrawal found for these details.**

### 4.6 Page de statut et impression

Après envoi, **Withdrawal submitted** affiche la référence, une checklist (déclaration enregistrée, e-mail de confirmation, la boutique traitera), puis **View withdrawal details**, **Track status** et **Print / save PDF**. La page de statut liste produits, quantités, prix, totaux et **Withdrawal history** y compris les messages du personnel issus des mises à jour de statut. L’impression ouvre une page de preuve imprimable avec un jeton sécurisé du flux de confirmation.

## 5. Problèmes

### 5.1 Return Button gratuit encore activé

**Symptôme :** la configuration est bloquée ; alerte indiquant que l’autre module de retour est activé ; l’enregistrement peut indiquer que les changements n’ont pas été sauvegardés tant que ce module n’est pas désactivé.

**Que faire :** **Modules** → **Module Manager** → trouvez le module gratuit Return Button → **Disable**. Puis rouvrez Return Button Pro.

### 5.2 Bouton du pied manquant

**Symptôme :** pas de bouton de rétractation dans le pied.

**Que faire :** confirmez que **Module enabled** et **Footer button** sont activés. Sous **Settings**, définissez **Footer button hook** sur Auto ou essayez les autres positions de pied une par une. Videz le cache et rechargez en dur la boutique. Pour les thèmes personnalisés, placez le hook personnalisé du module dans le template et sélectionnez cette option sous **Footer button hook**. Ouvrez **Dashboard** : il affiche le profil de thème détecté et le nom du hook de pied actif pour comparaison avec le thème.

### 5.3 « Return not available — the withdrawal period has ended. »

**Symptôme :** le détail de commande ou le formulaire bloque la rétractation avec ce message.

**Que faire :** vérifiez **Withdrawal period** et **Order state = delivered**. Corrigez l’historique de commande si la livraison n’a jamais été enregistrée. Prolongez le délai uniquement si vos CGV le permettent.

### 5.4 « An active withdrawal request already exists for this order. »

**Symptôme :** le client ne peut pas ouvrir un second dossier.

**Que faire :** terminez ou clôturez le dossier existant (**Refunded** / **Rejected**), ou désactivez temporairement **Block duplicate active requests** uniquement si votre processus autorise vraiment plusieurs réclamations ouvertes.

### 5.5 « This order status does not allow withdrawal. »

**Symptôme :** la commande est hors du filtre de statuts autorisés.

**Que faire :** sous **Settings**, définissez **Allowed order statuses** sur **All order statuses**, ou ajoutez l’état actuel de la commande à **Allowed for withdrawal**.

### 5.6 « No products in this order are eligible for withdrawal. » / message d’exclusion sur les lignes

**Symptôme :** chaque ligne exclue, ou lignes partielles sélectionnées invalides.

**Que faire :** examinez les produits, variantes, catégories, fabricants et fournisseurs exclus. Ajustez **Exclusion message** pour que les clients comprennent pourquoi.

### 5.7 « Withdrawal is not available for your customer account. »

**Symptôme :** formulaire ou boutons masqués pour un client connecté.

**Que faire :** retirez le groupe du client de **Excluded customer groups**, ou déplacez le client vers un groupe autorisé.

### 5.8 « Please enter a message for the customer when changing the status. »

**Symptôme :** la mise à jour de statut échoue dans la vue du dossier.

**Que faire :** renseignez **Message to customer**, ou désactivez **Require message to customer when changing status** si votre processus autorise des messages vides.

### 5.9 E-mail de confirmation non envoyé

**Symptôme :** le dossier indique e-mail non envoyé ; le client n’a pas de confirmation durable.

**Que faire :** corrigez les réglages mail PrestaShop, vérifiez les spams, utilisez **Resend confirmation email**. Définissez **Notification email** pour les copies au personnel. Confirmez que l’e-mail de contact de la boutique fonctionne.

### 5.10 L’invité ne trouve pas la commande

**Symptôme :** **No order found for the given details.** ou attente de limitation de débit.

**Que faire :** faites correspondre exactement la référence de commande et l’e-mail de commande. Attendez en cas de trop nombreuses tentatives. Confirmez que **Guest access** est activé.

### 5.11 La vérification des mises à jour échoue ou reste silencieuse

**Symptôme :** la vérification manuelle ne signale pas de version.

**Que faire :** assurez-vous que curl fonctionne et que le serveur peut joindre MyPresta.eu. Désactivez le module gratuit si Pro est bloqué. Réessayez **Manual Check** sur l’onglet **Updates**.

## 6. Pour les développeurs

### 6.1 Aperçu

- Nom technique : `rbpro`
- Version : paquet actuel 1.7–9 (ex. 1.4.6) ; PrestaShop 1.6 en paquet séparé (ex. 1.4.5) avec `ps_versions_compliancy` min `1.6.0.0`
- Nom affiché : Return Button Pro
- Auteur : MyPresta.eu
- Tab : `front_office_features`
- Classe principale : `Rbpro`
- `ps_versions_compliancy` du paquet 1.7–9 : min `1.7.0.0` ; du paquet 1.6 : min `1.6.0.0`
- Couche service : `RbpWithdrawalService` ; sécurité : `RbpSecurity` ; thème/hooks : `RbpCompatibility` ; analytics : `RbpStatsService`
- Flux : clés de configuration → hooks / contrôleurs front → tables `rbp_withdrawal*` → admin `AdminRbpWithdrawal` → statut/suivi/impression client

### 6.2 Fichiers importants

| Chemin | Rôle |
|---|---|
| `rbpro.php` | Bootstrap du module, install/uninstall, onglets configure, hooks, defaults |
| `classes/RbpWithdrawal.php` | Modèle objet du dossier et statuts |
| `classes/RbpWithdrawalService.php` | Éligibilité, délais, create/confirm, e-mails, mises à jour de statut |
| `classes/RbpSecurity.php` | CSRF, grant invité, rate limit, sanitization IBAN |
| `classes/RbpCompatibility.php` | Profil de thème, résolution du hook de pied, URL admin, hooks requis |
| `controllers/admin/AdminRbpWithdrawalController.php` | Liste et vue du dossier |
| `controllers/front/form.php` | Formulaire en deux étapes |
| `controllers/front/confirm.php` | Page de succès |
| `controllers/front/track.php` | Suivi public |
| `controllers/front/status.php` | Détails du dossier pour le client |
| `controllers/front/print.php` | Preuve imprimable |
| `sql/install.sql` | Crée les tables `rbp_*` |
| `sql/uninstall.sql` | Commentaire seulement — tables conservées |
| `lib/updateChecker.php` | UI de mise à jour MyPresta (`rbproUpdate`) |
| `views/templates/admin/*` | Dashboard, coque configure, vue dossier, avis latéral commande |
| `views/templates/front/*` | Formulaire, confirm, track, status, print, error |
| `views/templates/hook/*` | Boutons pied/compte/commande (classic / hummingbird) |
| `mails/*` | Templates `rbf_withdrawal_customer` / `rbf_withdrawal_admin` |
| `translations/*.php` | Traductions du pack |

### 6.3 Contrôleurs

| Contrôleur | Parent / entrée | Notes |
|---|---|---|
| Configure (`getContent`) | Module Manager | Onglets `rbp_tab` : `dashboard`, `settings`, `updates` |
| `AdminRbpWithdrawal` | Customers → Withdrawals | `add`/`edit` false ; chemin de création en lecture seule ; export CSV ; téléchargement de pièces jointes |
| Front `form` | Module link | Étapes 1–2 ; recherche invité ; cookie brouillon |
| Front `confirm` | Module link | Succès après envoi |
| Front `track` | Module link | Référence + e-mail |
| Front `status` | Module link | Chronologie + produits |
| Front `print` | Module link | Jeton HMAC sur la référence |

Les permissions suivent l’onglet admin. Les contrôleurs front exigent le module activé pour le formulaire ; le suivi respecte `RBP_ENABLE_STATUS_TRACK`.

### 6.4 Hooks

Enregistrés : `displayHeader`, `actionFrontControllerSetMedia`, `displayCustomerAccount`, `displayOrderDetail`, `actionPresentOrder`, `displayFooter`, `displayFooterBefore`, `displayFooterAfter`, `displayRbproButton` ; sur PS ≥ 1.7.7 aussi `displayBackOfficeHeader`, `displayAdminOrderSide`.

Exécutés par le module : `actionRbpWithdrawalCreated`, `actionRbpWithdrawalConfirmed` (et hooks liés au statut depuis le service lorsqu’ils sont définis).

La sortie du pied ne s’exécute que pour le nom de hook résolu par `RbpCompatibility::getFooterHookName()`.

### 6.5 Overrides

Aucun override de classe ou de contrôleur. L’intégration du thème utilise uniquement les hooks et des templates sélectionnables.

### 6.6 Base de données

| Table | Contenu |
|---|---|
| `PREFIX_rbp_withdrawal` | En-tête du dossier : boutique, commande, client, référence, portée, type, statut, IBAN, message, IP, UA, langue, flags e-mail, échéance, dates |
| `PREFIX_rbp_withdrawal_product` | Lignes sélectionnées et quantités |
| `PREFIX_rbp_withdrawal_note` | Notes internes du personnel |
| `PREFIX_rbp_withdrawal_attachment` | Métadonnées des téléversements du personnel |
| `PREFIX_rbp_withdrawal_history` | Événements d’audit |

La désinstallation **ne** supprime **pas** ces tables. `ensureDatabase()` crée les tables manquantes et peut migrer depuis `rbf_*` lorsque les tables Pro sont vides et que les tables gratuites ont des lignes.

### 6.7 Clés de configuration et traductions

Defaults de `Rbpro::CONFIG` :

| Clé | Default |
|---|---|
| `RBP_ENABLED` | 1 |
| `RBP_GUEST_ENABLED` | 1 |
| `RBP_IBAN_ENABLED` | 0 |
| `RBP_WITHDRAWAL_DAYS` | 14 |
| `RBP_DELIVERED_STATUS` | 0 (Auto) |
| `RBP_EXCLUDED_PRODUCTS` / `_COMBINATIONS` / `_CATEGORIES` / `_MANUFACTURERS` / `_SUPPLIERS` / `_CUSTOMER_GROUPS` | empty |
| `RBP_ALLOWED_ORDER_STATES` | empty |
| `RBP_ALLOWED_ORDER_STATES_RESTRICT` | 0 |
| `RBP_FOOTER_ENABLED` | 1 |
| `RBP_FOOTER_THEME` | light |
| `RBP_FOOTER_POSITION` | center |
| `RBP_BUTTON_COLOR` | `#2563eb` |
| `RBP_CUSTOM_CSS` | empty |
| `RBP_SHOW_ACCOUNT` / `RBP_SHOW_ORDER` | 1 |
| `RBP_SEO_NOINDEX` | 1 |
| `RBP_ADMIN_EMAIL` | empty |
| `RBP_BLOCK_DUPLICATE` | 1 |
| `RBP_SHOW_DEADLINE` | 1 |
| `RBP_REQUIRE_CHECKBOX` | 1 |
| `RBP_REQUIRE_STATUS_MESSAGE` | 1 |
| `RBP_THEME_TYPE` | auto |
| `RBP_FOOTER_HOOK` | auto |
| `RBP_ENABLE_STATUS_TRACK` | 1 |

Multilingue (pas dans le tableau `CONFIG`, installés par defaults) : `RBP_BUTTON_TEXT`, `RBP_EXCLUSION_MSG`, `RBP_SEO_TITLE`, `RBP_SEO_DESC`, `RBP_LEGAL_CHECKBOX`. Runtime : `RBP_ADMIN_FOLDER`. Les préférences de mise à jour utilisent les clés du vérificateur MyPresta. La migration du module gratuit mappe `RBF_*` → `RBP_*` lorsque les clés Pro sont vides.

Traductions : `translations/{iso}.php`. Les chaînes `desc` des champs vivent dans `renderConfigurationForm()` via `$this->l()`.

Statuts : `pending`, `confirmed` (libellé Registered), `processing`, `refunded`, `rejected`.

### 6.8 Extension

Surchargez les TPL/CSS de hooks dans le thème pour `modules/rbpro/...` sans modifier le module. Placez `{hook h='displayRbproButton'}` pour un placement personnalisé du bouton. Écoutez `actionRbpWithdrawalCreated` / `actionRbpWithdrawalConfirmed`. Ne comptez pas sur des overrides — il n’y en a aucun à enchaîner.

## 7. Support

Page produit : https://mypresta.eu/modules/front-office-features/eu-return-button-online-withdrawal-form.html

Aide pour ce module payant : connectez-vous à votre compte client sur mypresta.eu, ouvrez Contact et choisissez **Support for paid modules**. Le formulaire exige une connexion pour les modules payants ; après connexion, sélectionnez Return Button Pro dans votre historique d’achats.