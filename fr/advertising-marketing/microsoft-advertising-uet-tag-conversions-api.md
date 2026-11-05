---
title: "Microsoft Advertising UET Tag & Conversions API - documentation et manuel utilisateur"
description: "Configurez le suivi, vérifiez les événements avec les diagnostics en direct et résolvez les problèmes après l’installation du module."
sidebar:
  label: "Microsoft Advertising UET Tag & Conversions API - documentation et manuel utilisateur"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Microsoft Advertising UET Tag & Conversions API sur MyPresta.eu](https://mypresta.eu/modules/advertising-and-marketing/microsoft-advertising-uet-tag-conversions-api.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/advertising-marketing/microsoft-advertising-uet-tag-conversions-api/)
>
> ---


## 1. Exigences

Préparez la boutique, le compte Microsoft Advertising et la tâche planifiée avant la configuration.

- Utilisez PrestaShop 1.7, 8 ou 9.
- Utilisez PHP 7.1–8.x, selon la version PHP requise par votre installation PrestaShop.
- Activez les extensions PHP cURL, JSON, OpenSSL et de hachage.
- Avoir un compte Microsoft Advertising et un identifiant de balise UET. Obtenez également un jeton porteur de l'API Conversions pour **Conversions API** ou **UET + CAPI**.
- Avoir accès à CRON lors de l'utilisation de CAPI, car sa file d'attente doit s'exécuter régulièrement.
- Configurez un module CMP ou cookie externe avant de transformer **Require marketing / analytics consent** en **Yes**.
- Aucun autre module PrestaShop n'est requis. Un module de flux Microsoft Merchant Center est facultatif et peut aider à aligner les identifiants de catalogue.

## 2. Installation

1. Ouvrez **Modules > Module Manager**.
2. Cliquez sur **Upload a module** et téléchargez le fichier ZIP.
3. Installez **Microsoft Advertising UET / Conversions API**.
4. Recherchez-le dans **Module Manager** et cliquez sur **Configure**.
5. Complétez **Setup Wizard** ou configurez tous les onglets manuellement.

Le module ne crée pas d'élément de menu **Catalog** visible. Son point de terminaison de données est un onglet back-office caché utilisé en interne.

L'installation ne vide pas le cache PrestaShop. Effacez-le sous **Advanced Parameters > Performance** uniquement si d'anciens actifs ou un ancien écran de configuration restent visibles.

La désinstallation supprime le journal des événements du module, les règles multi-balises, la file d'attente CAPI, le point de terminaison masqué et les clés de configuration du module. Les clés du vérificateur de mise à jour peuvent rester. La réinstallation démarre avec les paramètres par défaut et ne restaure pas les événements ou les règles supprimés.

## 3. Configuration et travail de back-office

Ouvrez **Modules > Module Manager**, recherchez **Microsoft Advertising UET / Conversions API** et cliquez sur **Configure**.

Suivez ce processus :

1. Complétez **Setup Wizard**.
2. Confirmez le canal et les informations d'identification dans **Tracking mode**.
3. Sélectionnez les signaux dans **Events**.
4. Faites correspondre les ID de produit d'événement à votre flux dans **Catalog IDs**.
5. Configurez **Privacy & consent**.
6. Définissez le comportement de paiement et de remboursement dans **Order lifecycle**.
7. Ajoutez **Multi-tag rules** uniquement pour les informations d'identification spécifiques au contexte.
8. Planifiez l'URL CRON affichée toutes les 1 à 5 minutes lorsque CAPI est actif.
9. Parcourez la vitrine et vérifiez les événements dans **Live Statistics** et **Health & diagnostics**.
10. Confirmez les événements dans Microsoft Advertising.

Les captures d'écran de ce manuel proviennent d'un back-office anglais.

### 3.1 Assistant de configuration

Utilisez l'assistant pour la première configuration. Il vous guide à travers **Mode**, **Tag ID**, **CAPI token**, **Test** et **Done**.

![Setup Wizard](https://mypresta.eu/docs/images/docs/mybing-wizard.webp)

| Champ | Au démarrage | Ce qu'il fait |
|---|---|---|
| **Mode** | Non sélectionné | Choisissez **UET Tag** pour le suivi du navigateur, **Conversions API** pour le suivi du serveur ou **UET + CAPI** pour les deux. Le mode double utilise un identifiant d'événement partagé pour la déduplication. |
| **Tag ID** | Vide | Collez l'ID de Microsoft Advertising sous Balise UET ou Suivi des conversions. Il est requis dans tous les modes. |
| **CAPI token** | Vide | En mode CAPI ou double, collez le jeton du porteur depuis la section API Conversions de la balise UET. Traitez-le comme un mot de passe. |
| **Enable Ghost Collector (msclkid / anonymousId sync)** | Oui | Collectez les identifiants de clic Microsoft et de visiteurs anonymes dans des modes compatibles CAPI sans effectuer d'appels de suivi UET. Gardez-le activé pour une correspondance plus forte et une continuité de session. |
| **Test** | Ne pas exécuter | En mode UET, validez l'ID de balise, puis vérifiez l'affichage d'une page de vitrine. Dans les modes compatibles CAPI, cliquez sur **Send test purchase** pour envoyer un achat test de 1 €. Attendez 10 à 30 minutes pour que Microsoft Advertising l'affiche. |
| **Done** | Incomplet | Terminez la configuration et ouvrez les raccourcis vers **Tracking mode**, **Health & Data Quality Coach** ou **Live Statistics**. |

Utilisez **Start over** pour réexécuter l'assistant. Les informations d'identification existantes restent pré-remplies jusqu'à ce qu'elles soient modifiées.

### 3.2 Mode de suivi et informations d'identification

Sélectionnez la manière dont tous les événements parviennent à Microsoft Advertising, remplissez les champs affichés pour ce mode, puis cliquez sur **Save**.

![Tracking mode and credentials](https://mypresta.eu/docs/images/docs/mybing-tracking-mode.webp)

| Champ | Au démarrage | Ce qu'il fait |
|---|---|---|
| **Tracking mode** | Non sélectionné | **UET Tag** envoie depuis le navigateur. **Conversions API** met en file d'attente les événements du serveur. **UET + CAPI** envoie les deux avec le même ID d'événement afin que Microsoft puisse les dédupliquer. |
| **Tag ID(s)** | Vide | Saisissez un ID de balise UET et appuyez sur virgule ou sur Entrée. L'ID est requis pour l'UET, le CAPI et le mode double. |
| **Conversions API token** | Vide | Collez le jeton du porteur de **Microsoft Advertising > UET tag > Use Conversions API > Copy Token**. |
| **CAPI endpoint override (advanced)** | Vide | Laissez vide pour utiliser la destination standard de Microsoft. Définissez-le uniquement lorsque Microsoft documente un hôte personnalisé pour votre compte. |
| **Ghost collector (CAPI)** | Oui | Capturez `msclkid` et l’ID de visiteur anonyme pour la correspondance CAPI. Il n'appelle pas le suivi UET. |
| **Bing ID Sync (remarketing)** | Oui | Lorsque l'UET est actif, envoyez l'ID de visiteur anonyme via Bing ID Sync pour améliorer la correspondance de l'audience de remarketing. |

Pour le mode CAPI ou double, copiez le **CRON URL** affiché sur votre planificateur et exécutez-le toutes les 1 à 5 minutes.

### 3.3 Événements

Sélectionnez et enregistrez d'abord un mode de suivi. Activez ensuite uniquement les signaux dont vous avez besoin et cliquez sur **Save**.

![Tracked events](https://mypresta.eu/docs/images/docs/mybing-events.webp)

| Champ | Au démarrage | Ce qu'il fait |
|---|---|---|
| **PAGE_VIEW** | Oui | Enregistrez chaque chargement de page de vitrine. Il prend en charge les rapports et l'attribution du trafic ; le désactiver n'arrête pas les autres événements. |
| **view_item (+ select_item)** | Oui | Envoyez `view_item` sur les pages de produits et `select_item` lorsqu'un produit est cliqué dans une catégorie, une recherche ou des listes de best-sellers. |
| **view_item_list** | Oui | Envoyez environ les 20 premiers produits à partir de listes de catégories, de recherches et de best-sellers avec des identifiants, des noms, des prix et des positions. Il possède son propre interrupteur. |
| **add_to_cart** | Oui | Enregistrez les ajouts au panier. L'UET et le mode double utilisent l'événement cart natif ainsi qu'une solution de secours CSS facultative. Le mode CAPI uniquement utilise le chemin du serveur et ne nécessite pas de sélecteurs CSS. |
| **REMOVE_FROM_CART (Microsoft: Other)** | Oui | Enregistrez les suppressions de panier sous **Other**, car Microsoft n’a pas de type natif de suppression du panier. |
| **CHECKOUT** | Oui | Déclenchez-vous lorsque le client entre dans le panier ou dans le flux de commande et marquez l'intention d'achat. |
| **CHECKOUT details** | Oui | Ajoutez de la valeur, de la devise et des données produit à **CHECKOUT**. Le désactiver envoie des paramètres minimaux. |
| **ADD_PAYMENT_INFO (Microsoft: Other)** | Oui | Lancez l'étape de paiement comme **Other**. Utilisez-le comme signal facultatif de fin d'entonnoir pour les statistiques en direct. |
| **purchase** | Oui | Envoyez **OffMicrosoftPurchases** avec la valeur de la commande, la devise et les lignes de produits. Un ID de déduplication client stable sécurise les actualisations. Utilisez **Order lifecycle** pour le retarder jusqu'au paiement. |
| **SEARCH** | Oui | Enregistrez les recherches en vitrine avec le terme de recherche. |
| **ADD_TO_WISHLIST (Microsoft: Other)** | Oui | Enregistrez les ajouts à la liste de souhaits sous **Other** lorsque le thème expose des contrôles compatibles. |
| **SIGN_UP (Signup)** | Oui | Envoyez **Signup** lorsqu'un compte client est créé. |
| **LEAD / SUBSCRIBE (newsletter)** | Oui | Envoyez **Lead** pour les abonnements à la newsletter. Désactivez-le si un autre outil suit la même conversion. |
| **LEAD (legacy product interest)** | Non | Préservez l’ancien comportement du Lead par intérêt pour le produit. Laissez-le désactivé à moins qu'une campagne historique ne l'exige ; son utilisation avec `view_item` peut gonfler les câbles. |
| **CONTACT** | Oui | Se déclenche lorsque le formulaire de contact est soumis, en utilisant la détection de secours du serveur et du navigateur. |
| **REFUND (Microsoft: Other)** | Oui | Se déclenche lorsqu'une commande atteint un état de remboursement ou d'annulation configuré. Microsoft le reçoit sous le nom **Other** pour la correction locale et les statistiques. |
| **Rich product payloads (productId / items)** | Oui | Incluez les identifiants de produits, les quantités et les prix. Le désactiver laisse un minimum de données de valeur/devise, sauf lorsque les événements de liste ou de clic nécessitent des identifiants. Gardez-le pour la correspondance du catalogue. |
| **Add to cart CSS selector** | `.add-to-cart` | En UET et en mode double, identifiez le bouton de la page produit lorsque le thème ne déclenche pas l'événement de panier natif. |
| **Product price CSS selector** | `.current-price span` | En UET et en mode dual, lisez le prix de repli visible. Un mauvais sélecteur envoie zéro ; combinez-le avec **Reformat price string** si nécessaire. |

Pour CAPI, activez **Advanced matching (email / phone)** et **Ghost collector (CAPI)** pour une meilleure correspondance.

### 3.4 ID de catalogue et ID de catalogue Doctor

Faites en sorte que les ID de produit d'événement correspondent exactement à votre flux Microsoft Merchant Center, cliquez sur **Save**, puis examinez **Catalog ID Doctor**.

![Catalog IDs and Catalog ID Doctor](https://mypresta.eu/docs/images/docs/mybing-catalog.webp)

| Champ | Au démarrage | Ce qu'il fait |
|---|---|---|
| **Product identification** | `id_product` | Choisissez l'ID de produit, l'ID de combinaison ou l'ID de produit plus le séparateur et l'ID de combinaison. Les identifiants combinés conviennent aux flux qui répertorient les variantes. Un format de flux différent empêche la correspondance. |
| **Separator** | `-` | Séparez les ID de produit et de combinaison en mode combiné. Le produit 12 et la combinaison 5 deviennent `12-5`. Utilisez le même séparateur dans l’alimentation. |
| **Product ID prefix** | Vide par langue | Ajoutez une valeur spécifique à la langue avant chaque identifiant uniquement lorsque le flux l'utilise également. |
| **Product ID suffix** | Vide par langue | Ajoutez une valeur spécifique à la langue après chaque identifiant uniquement lorsque le flux l'utilise également. |
| **Exclude free products** | Non | Omettez les produits à prix nul du panier et achetez des gammes de produits et des calculs de valeur. |
| **Force currency conversion** | Non | Convertissez toutes les valeurs monétaires dans une devise cible. Activez uniquement lorsque la devise du magasin n'est pas acceptée par Microsoft Advertising. |
| **Target currency** | Sélection en fonction du magasin | Sélectionnez la devise de destination. Il est ignoré lorsque la conversion forcée est désactivée. |
| **Reformat price string** | Non | En UET ou en mode double, nettoyez les prix des thèmes formatés avant que le remplacement CSS de l'ajout au panier ne les lise. Il n'est pas utilisé en mode CAPI uniquement. |

**Catalog ID Doctor** affiche des exemples générés à partir d'un produit et d'une combinaison actifs, les ID récents trouvés dans les données d'événement et des conseils sur l'ID de base, le séparateur, le préfixe et le suffixe sélectionnés. S'il signale **No active products found to validate catalog productId values**, activez un produit et rouvrez l'onglet.

### 3.5 Confidentialité et consentement

Configurez d’abord une source de consentement externe. Le module n'affiche pas de bandeau cookie.

![Privacy and consent](https://mypresta.eu/docs/images/docs/mybing-privacy.webp)

| Champ | Au démarrage | Ce qu'il fait |
|---|---|---|
| **Require marketing / analytics consent** | Non | Bloquez UET, CAPI et Ghost jusqu'à ce que le consentement soit accordé. Sans CMP connectée, le suivi reste silencieux. |
| **Default consent state** | `auto` | `auto` attend le consentement d'un cookie, d'un TCF ou d'un événement de navigateur ; `grant` permet immédiatement ; `revoke` se bloque jusqu'à ce qu'il soit accordé. Utilisez `auto` avec une bannière et `grant` uniquement avec une base légale appropriée. |
| **IAB TCF 2.x (__tcfapi)** | Oui | Écoutez un CMP certifié. L’objectif 1 et l’un des objectifs 2, 3 ou 4 déverrouillent les publicités et mettent à jour le consentement au stockage de publicités Microsoft UET. |
| **Include logged-in customer ID** | Non | Ajoutez l'ID client PrestaShop au contexte de connexion et aux diagnostics en tant que signal d'identification externe facultatif. Divulguez-le dans la politique de confidentialité. |
| **Advanced matching (email / phone)** | Non | Envoyez des e-mails et des champs e-mail/téléphone hachés disponibles pour une meilleure attribution UET et CAPI. Assurez-vous que la politique de confidentialité couvre cela. Il est fortement recommandé pour le CAPI. |
| **Ignore admin / employee traffic** | Oui | Ignorez le suivi de la vitrine lorsqu'une session d'employé est détectée. |
| **Simple bot filter** | Non | Ignorez les requêtes dont l’identification du navigateur ressemble à un robot ou à un robot. C'est heuristique. |

Pour une configuration dans l'UE, configurez le CMP, utilisez `auto`, activez le consentement requis et laissez le TCF activé lorsqu'il est pris en charge. Testez à la fois l'acceptation et le refus dans un navigateur privé. Le guide reconnaît les cookies marketing/statistiques courants, son propre cookie de consentement et son résultat TCF. Les rappels Cookiebot sont directement pris en charge ; d’autres CMP peuvent envoyer l’événement de consentement du module.

### 3.6 Cycle de vie des commandes

Contrôlez le moment où les ventes et les remboursements entrent dans les rapports de conversion.

![Order lifecycle](https://mypresta.eu/docs/images/docs/mybing-orders.webp)

| Champ | Au démarrage | Ce qu'il fait |
|---|---|---|
| **Purchase only when paid** | Non | Retardez l’achat jusqu’à ce qu’un état de commande soit payé. Activez-le lorsque les virements bancaires impayés ou les commandes contre remboursement gonflent les conversions. |
| **Paid statuses** | Vide | Sélectionnez une liste blanche facultative d’états payants. Laissez vide pour utiliser l’indicateur payant intégré de PrestaShop. Une liste remplie est utilisée lorsque le suivi payant uniquement est activé. |
| **Refund / cancel statuses** | Vide | Sélectionnez les États qui déclenchent le remboursement. Empty utilise la détection automatique à partir des noms de statut contenant un remboursement ou une annulation. L'événement Remboursement doit également être activé. |

Pour les paiements différés, activez le suivi des paiements uniquement, déplacez une commande test vers l'état payé et vérifiez que l'achat apparaît une fois.

### 3.7 Règles multi-balises

Utilisez des règles lorsqu'un magasin, une langue, un pays ou une devise nécessite des informations d'identification différentes. La première règle active correspondante l'emporte dans l'ordre croissant **Position**. Sans correspondance, les informations d'identification globales sont utilisées.

![Multi-tag rules](https://mypresta.eu/docs/images/docs/mybing-multitag.webp)

La liste **Active rules** affiche **Tag ID**, la source du jeton CAPI, **Shop**, **Language**, **Country**, **Currency**, **Active** et **Actions**. Cliquez sur **Delete** et confirmez pour supprimer une règle. Il n'y a pas de modification ou d'actions groupées ; recréer une règle pour la changer.

| Champ | Au démarrage | Ce qu'il fait |
|---|---|---|
| **Tag ID (UET)** | Vide | Définissez la balise UET pour faire correspondre le trafic. Il peut être vide uniquement pour un remplacement CAPI de jeton uniquement. |
| **Conversions API token** | Vide | Remplacez le jeton global. Empty hérite du jeton de **Tracking mode**. |
| **Shop** | **All shops** | Limitez la règle à un magasin multimagasin ou à tous les magasins. |
| **Language** | **All languages** | Limitez-le à une seule langue de vitrine ou à toutes les langues. |
| **Country** | **All countries** | Limitez-le au contexte actuel du pays client. |
| **Currency** | **All currencies** | Limitez-le à la devise actuelle. |
| **Active** | Oui | Activez ou désactivez la règle. Les règles inactives sont ignorées. |
| **Position** | `0` | Définir l’ordre d’évaluation. Les nombres inférieurs gagnent lorsque plusieurs règles correspondent. |

Cliquez sur **Add rule**. **Property rule saved** confirme son succès. Si **Could not save rule — provide a valid Tag ID and/or Conversions API token.** apparaît, corrigez l'ID de balise ou fournissez un jeton.

### 3.8 Statistiques en direct

Ouvrez cet onglet dans une fenêtre et parcourez la vitrine dans une autre. Les événements apparaissent sur la chronologie en temps réel de 30 minutes.

![Live Statistics](https://mypresta.eu/docs/images/docs/mybing-live.webp)

**Recovery Radar** affiche les achats sans ajout au panier, l'ajout au panier sans vues détaillées du produit, les remboursements par rapport aux achats et la récupération CAPI/Ghost. Utilisez les cases à cocher d'événement pour filtrer la chronologie ; PageView est masqué par défaut. **Pause** arrête l'interrogation sans arrêter le suivi et **Refresh** récupère les données actuelles.

| Champ | Au démarrage | Ce qu'il fait |
|---|---|---|
| **Enable live dashboard** | Oui | Activez ou désactivez l’interrogation de la chronologie. Le désactiver met le flux en pause, tandis que le suivi et les enregistrements de santé/radar se poursuivent. |
| **Also log PageView into the event database** | Non | Ajoutez des lignes PageView bruyantes au journal local. Il ne contrôle pas le déclenchement de Microsoft PageView ou d'autres journaux d'événements. Activer uniquement pour le débogage. |
| **Keep events for (days)** | `14` | Purger les lignes plus anciennes que cet âge. Les valeurs acceptées sont comprises entre 1 et 365 ; 7 à 30 est typique. |
| **Live poll interval (seconds)** | `5` | Sondez toutes les 2 à 60 secondes. Les valeurs inférieures sont plus rapides mais créent davantage de demandes de back-office. |

Utilisez **Purge older than retention**, **Delete failed only** ou **Clear entire event log** pour un nettoyage immédiat. Tout effacer nécessite une confirmation et ne peut pas être annulé. **Export recent events (CSV)** télécharge les enregistrements récents non-PageView.

### 3.9 Santé et diagnostics

Utilisez cet onglet après la configuration et chaque fois que des conversions sont manquantes.

![Health and diagnostics](https://mypresta.eu/docs/images/docs/mybing-health.webp)

Mode d'audit **Health Score**, informations d'identification, fraîcheur de la file d'attente, Ghost, PageView, consentement, TCF, achat, déduplication, erreurs récentes, format du catalogue et qualité des données. Lisez chaque vérification échouée, pas seulement l'étiquette **Excellent**, **Good**, **Fair** ou **Needs work**.

Pour CAPI, planifiez **CAPI CRON URL** toutes les 1 à 5 minutes. Examinez **Last CAPI flush**, les lignes traitées, envoyées, en attente, en échec, les totaux de file d'attente et les lignes datant de plus de 10 minutes.

**Data Quality Coach** estime la couverture correspondante à partir des charges utiles récentes du serveur ou d'un échantillon d'achat en cours. Il répertorie les identifiants présents et manquants, les améliorations attendues, les moyennes par événement et les correctifs au niveau du magasin. Améliorez l'identification anonyme, `msclkid`, la correspondance avancée e-mail/téléphone et l'identifiant client facultatif, le cas échéant. Confirmez les diagnostics finaux dans Microsoft Advertising.

| Champ | Au démarrage | Ce qu'il fait |
|---|---|---|
| **Enable front debug inspector** | Non | Affichez une superposition de vitrine flottante avec les événements, les charges utiles, la destination CAPI, l'état de la file d'attente et les erreurs. Éteignez-le après le test. Ajoutez temporairement `?mybing_debug=1` à une URL de vitrine pour l'activer sans enregistrer. |

Sous **Test & queue** :

- **Send test purchase** envoie une conversion test ; vérifiez Microsoft Advertising après 10 à 30 minutes.
- **Test CAPI token** vérifie que l'ID de balise et le jeton sont présents.
- **Process CAPI queue** exécute le même chemin de file d'attente que CRON.

**Recent events log** affiche l'événement, l'ID, le canal, l'état, la réponse/erreur, la date et le résultat. Utilisez **Re-send** pour une tentative immédiate ou **Re-add to queue** pour la prochaine exécution CRON.

**Recent queue rows** affiche les détails de l'événement, l'état, les tentatives, la dernière erreur et l'heure de mise à jour. Utilisez des actions par ligne ou **Re-send all failed now** et **Re-add all failed to queue**.

### 3.10 Mises à jour

Recherchez une version plus récente du module ici.

![Updates](https://mypresta.eu/docs/images/docs/mybing-updates.webp)

| Champ | Au démarrage | Ce qu'il fait |
|---|---|---|
| **Manual Check** | Aucun résultat | Cliquez sur **Check Now** pour contacter le service de mise à jour une fois. Il affiche **Module is up to date!** ou **New version available!**. |
| **Automatic Notifications** | Préférence de mise à jour partagée existante | **Enabled** vérifie environ tous les trois jours et peut avertir les employés. **Disabled** quitte le manuel de gestion des mises à jour. |
| **Product Page** | Lien affiché | Ouvrez la page officielle du module pour obtenir des informations sur la version, la documentation et l'accès au support. |

Cliquez sur **Save** après avoir modifié les notifications.

## 4. Vitrine de magasin

Le module n'ajoute aucun bloc de vitrine, formulaire, bouton ou page de compte client visible. Les clients utilisent les écrans normaux de produit, de panier, de paiement, d’inscription, de newsletter, de contact et de confirmation.

Les pages produits contiennent un bloc de données produit masqué utilisé par le suivi. Cela ne modifie pas le thème visible. Lorsque le débogage est activé, un inspecteur flottant devient visible ; désactivez-le après le test car il expose les détails de suivi.

Pour CAPI, copiez **CAPI CRON URL** depuis **Tracking mode** ou **Health & diagnostics** dans le planificateur d'hébergement et exécutez-le toutes les 1 à 5 minutes. L'URL protégée traite les événements mis en file d'attente et la rétention. Ne le publiez pas car il contient une clé d'accès.

Le point de terminaison des données de vitrine est appelé automatiquement pour les actions de consentement, d’ID de visiteur, de panier, d’affichage de page, de paiement, de contact et de débogage. Ne le construisez pas et ne l’ouvrez pas manuellement.

| Message visible | Que faire |
|---|---|
| L'inspecteur de débogage affiche le consentement refusé | Acceptez le consentement marketing via la CMP ou réparez la connexion CMP. |
| L'inspecteur de débogage affiche la file d'attente | Exécutez CRON ou **Process CAPI queue**, puis vérifiez **Health & diagnostics**. |
| L'inspecteur de débogage indique un échec | Lisez la réponse dans **Health & diagnostics**, corrigez les informations d'identification ou la connectivité, puis cliquez sur **Re-send**. |

## 5. Problèmes

| Symptôme | Cause et action |
|---|---|
| L'assistant reste incomplet | Enregistrez un mode, un ID de balise et un jeton valides, le cas échéant ; exécutez **Test** et terminez **Done**. |
| Aucun événement UET n'apparaît | Enregistrez un ID de balise valide, incluez l'UET dans le mode, activez l'événement, examinez le consentement et testez dans une session client privée. |
| **Missing Tag ID and/or Conversions API token** | Entrez les deux dans **Tracking mode**, enregistrez et exécutez à nouveau **Test CAPI token**. |
| Les événements CAPI restent en file d'attente | Planifiez **CAPI CRON URL** toutes les 1 à 5 minutes, cliquez une fois sur **Process CAPI queue** et inspectez **Last CAPI flush**. |
| Le test CAPI ou le renvoi échoue | Lisez **Response / error**, corrigez l'ID de balise/le jeton/la connectivité, laissez le remplacement du point de terminaison vide à moins que Microsoft n'en fournisse un, puis réessayez. |
| Le suivi s'arrête une fois le consentement requis | Configurez le CMP externe, utilisez `auto`, connectez le TCF ou ses rappels, puis acceptez le consentement marketing et retestez. |
| Les produits du catalogue ne correspondent pas | Alignez **Product identification**, le séparateur, le préfixe et le suffixe avec le flux et examinez **Catalog ID Doctor**. |
| Les achats apparaissent avant le paiement | Activez **Purchase only when paid** et sélectionnez éventuellement les états payés exacts. |
| Les commandes payantes ne créent pas d'achat | Activez **purchase** et assurez-vous que l’état de la commande est payé ou inclus dans **Paid statuses**. |
| Les remboursements n'apparaissent pas | Activez le remboursement et sélectionnez le bon **Refund / cancel statuses**. |
| Vos tests sont ignorés | Utilisez un navigateur privé sans session employé ou désactivez temporairement **Ignore admin / employee traffic**. |
| Le trafic de test de type robot est absent | Désactivez **Simple bot filter** pour le test, puis restaurez-le si nécessaire. |
| L'ajout au panier UET est absent | Mettez à jour les sélecteurs CSS de bouton et de prix pour qu'ils correspondent au thème. |
| La valeur de l'ajout au panier est nulle ou mal formée | Corrigez le sélecteur de prix et activez **Reformat price string** si nécessaire. |
| Étape de paiement L'autre événement est absent bien que son commutateur soit Oui | Le thème ou l'étape de paiement n'a pas déclenché le chemin du module. Traitez ce signal comme facultatif et vérifiez l’entonnoir restant. |
| Les statistiques en direct attendent les événements | Activez le tableau de bord, reprenez-le, supprimez les filtres, cliquez sur **Refresh** et parcourez la vitrine en tant que client. |
| PageView atteint Microsoft mais est absent localement | Activer temporairement la journalisation PageView locale ; il est désactivé par défaut. |
| Des informations d'identification multi-tags incorrectes sont utilisées | Supprimez/recréez les règles qui se chevauchent et attribuez à la plus spécifique la position la plus basse. |
| La règle ne peut pas être enregistrée | Fournissez un ID de balise et/ou un jeton valide, puis cliquez sur **Add rule**. |
| Santé met en garde contre la qualité des données | Suivez **Highest-impact fixes**, activez la correspondance Ghost et Advanced lorsque cela est légal et collectez des données téléphoniques de paiement valides. |
| L'écran du module semble obsolète | Videz le cache sous **Advanced Parameters > Performance** et rechargez. |

## 6. Référence du développeur

### 6.1 Architecture

Le nom technique est `mybing`, version `1.4.0`. La classe principale est `mybing extends Module` ; le nom de la liste est **Microsoft Advertising UET / Conversions API**, auteur `MyPresta.eu`, catégorie `front_office_features`.

`MybingTrackerFactory` sélectionne `MybingUetTracker`, `MybingCapiTracker` ou `MybingHybridTracker`. `MybingEvents` crée des événements ; `MybingEventId` génère et conserve les ID de déduplication. `MybingProductIdResolver`, `MybingCurrencyHelper` et `MybingUserData` normalisent les données de catalogue, d'argent et d'identité. `MybingCapiClient` crée des requêtes, les envoie et gère les tentatives. Diagnostics d'alimentation `MybingLiveStats`, `MybingHealthScore`, `MybingDataQualityCoach` et `MybingCatalogDoctor`.

Le mode double partage un ID d'événement entre les canaux du navigateur et du serveur. Le point de terminaison par défaut est `https://capi.uet.microsoft.com/v1/{tagId}/events`. Chaque appel CRON traite jusqu'à 50 lignes de file d'attente et applique la rétention.

### 6.2 Fichiers et classes

| Fichier ou classe | Responsabilité |
|---|---|
| `mybing.php` | Installation/désinstallation, valeurs par défaut, formulaires, actions, CRON, configuration frontale et hooks. |
| `classes/MybingTrackerInterface.php` | Contrat de traqueur. |
| `classes/MybingTrackerFactory.php` | Résolution de changement de mode et d’événement. |
| `classes/MybingUetTracker.php` | Charges utiles du navigateur et enregistrements UET locaux. |
| `classes/MybingCapiTracker.php` | Livraison du serveur et mise en file d'attente. |
| `classes/MybingHybridTracker.php` | Double sortie et déduplication. |
| `classes/MybingCapiClient.php` | Charges utiles, cURL, réponses, file d'attente, tentatives et résumés de vidage. |
| `classes/MybingEvents.php` | Mise en place d'événements commerciaux. |
| `classes/MybingEventMap.php` | Carte des événements internes à Microsoft. |
| `classes/MybingEventId.php` | ID d’événement, déduplication et guérison des tables d’événements. |
| `classes/MybingUserData.php` | ID de clic/visiteur, données client, normalisation et hachage. |
| `classes/MybingConsent.php` | Exigence de consentement, valeurs par défaut, cookies et TCF. |
| `classes/MybingPropertyRules.php` | Schéma de règles contextuelles, correspondance et résolution des informations d'identification. |
| `classes/MybingProductIdResolver.php` | Génération d’ID de catalogue. |
| `classes/MybingCurrencyHelper.php` | Contexte monétaire et conversion. |
| `classes/MybingLiveStats.php` | Flux, résumés, radar, rétention et nettoyage. |
| `classes/MybingHealthScore.php` | Vérifications d’état pondérées et diagnostics de file d’attente. |
| `classes/MybingDataQualityCoach.php` | Estimations de la couverture identitaire. |
| `classes/MybingCatalogDoctor.php` | Échantillons et identifiants de produits récents. |
| `controllers/admin/AdminMybingAjaxController.php` | Pont de back-office JSON authentifié. |
| `controllers/front/ajax.php` | Point de terminaison JSON de suivi protégé par jeton. |
| `controllers/front/cron.php` | Point de terminaison JSON de file d’attente protégée par clé. |
| `views/js/mybing.js` | Principales reliures avant et expédition. |
| `views/js/mybing-tcf.js` | Pont de consentement TCF. |
| `views/js/mybing-ghost.js` | Synchronisation visiteur/ID de clic. |
| `views/js/mybing-debug.js` | Inspecteur avant. |
| `views/js/mybing-admin.js`, `mybing-wizard.js`, `mybing-live.js` | Formulaires de back-office, assistant et tableau de bord en direct. |
| `views/templates/hook/header.tpl` | UET, consentement, correspondance, page vue, événements, script et ID Sync. |
| `views/templates/hook/product-details.tpl` | Produit caché JSON. |
| `views/templates/hook/displayOrderConfirmation.tpl` | Sortie d'achat du navigateur. |
| `views/templates/hook/capi-pageview.tpl`, `ghost.tpl`, `debug.tpl` | Affichage de la page CAPI, Ghost et sortie de l'inspecteur. |
| `views/templates/hook/payment.tpl` | Modèle d'événement de paiement non invoqué par un gestionnaire de hook dans la version 1.4.0. |
| `sql/install.php`, `sql/uninstall.php` | Créez/réparez et supprimez des tables personnalisées. |
| `lib/updateChecker.php` | Vérifications de mise à jour manuelles et périodiques. |

### 6.3 Contrôleurs

`AdminMybingAjaxController extends ModuleAdminController` est installé en tant qu'onglet caché `AdminMybingAjax` avec le parent `-1`. Il nécessite un employé et émet du JSON. Actions : `liveFeed`, `liveRadar`, `liveClear`, `wizardSave`, `wizardTest`, `wizardComplete`, `wizardReset`, `dqReport`/`emqReport` et `exportCsv`.

`MybingAjaxModuleFrontController extends ModuleFrontController` est SSL et JSON uniquement. Il accepte la clé sécurisée ou le jeton frontal généré. Actions : `ghost`, `consent`, `addToCart`, `removeFromCart`, `wishlist`, `selectItem`, `contact`, `beginCheckout`, `recalculate`, `pageview`, `ping` et `inspect` de débogage uniquement. Les erreurs incluent `invalid_token`, `disabled`, `empty_cart`, `invalid_currency`, `disabled_or_consent`, `debug_off` et `unknown_action`.

`MybingCronModuleFrontController` accepte `key` ou `secure_key`, renvoie JSON, émet HTTP 403 avec `access_denied` pour un accès non valide et appelle `runCapiCron()`.

`controllers/front/index.php` envoie uniquement des en-têtes sans cache et redirige vers le haut.

### 6.4 Crochets

| Crochet enregistré | Mise en œuvre |
|---|---|
| `displayHeader` | Filtre le trafic ; envoie des signaux de page, de liste, de produit, de paiement, de recherche, de contact et de newsletter ; restitue la sortie UET/Ghost/CAPI. |
| `displayOrderConfirmation` | Résout la commande, suit les achats autorisés, restitue la sortie du navigateur. |
| `actionValidateOrder` | Suit l'achat lors de la création, à moins que le paiement ne le retarde. |
| `actionOrderStatusPostUpdate` | Suit les achats payés retardés et les transitions de remboursement/annulation. |
| `actionCustomerAccountAdd` | Suit l'inscription et stocke la sortie du navigateur pour la page suivante. |
| `actionFrontControllerSetMedia` | Ajoute la configuration frontale et les ressources principales, TCF, Ghost et de débogage. |
| `displayPaymentTop` | Enregistré, mais `hookDisplayPaymentTop()` n'est pas implémenté dans la version 1.4.0. |
| `displayFooter` | Rend l'inspecteur de débogage et l'amorçage de la file d'attente lorsqu'ils sont activés. |
| `actionCartUpdateQuantityBefore`, `actionBeforeCartUpdateQty` | Suivre les changements de quantité du panier du serveur ; ce dernier délègue au premier. |
| `actionObjectProductInCartDeleteBefore`, `actionObjectProductInCartDeleteAfter` | Instantané, puis suivez la suppression complète de la ligne de panier. |
| `displayProductAdditionalInfo` | Affiche les détails cachés du produit. |
| `actionNewsletterRegistrationAfter` | Suit le responsable de la newsletter. |
| `displayContactContent` | Ajoute le marqueur de contact masqué. |

Il n’existe pas de méthodes `enable()` ou `disable()` personnalisées.

### 6.5 Base de données

Le préfixe PrestaShop actuel remplace `ps_`.

| Tableau | Contenu |
|---|---|
| `ps_mybing_events` | Nom/ID de l'événement, commande/panier/boutique, canal, charge utile, statut, code HTTP, réponse, date, index de recherche et clé de déduplication unique de l'événement/nom/boutique. |
| `ps_mybing_properties` | Sélecteurs de balise, de jeton, de boutique/langue/pays/devise, actif, position et date. |
| `ps_mybing_queue` | Charge utile, tentatives, statut, dernière erreur, dates de création/mise à jour. |

Nouvelles tentatives d'installation avec `utf8` si `utf8mb4` échoue. `MybingPropertyRules::ensureSchema()` peut ajouter `tag_id` et `access_token` lorsque la configuration est ouverte et migrer un jeton d'actualisation hérité. Le schéma d'événement ajoute son index unique. La désinstallation supprime les trois tables.

### 6.6 Clés de configuration

| Clés | Valeurs par défaut et objectif |
|---|---|
| `MYBING_MODE` | Vide; mode traqueur. |
| `MYBING_TAG_ID`, `MYBING_CAPI_TOKEN`, `MYBING_CAPI_ENDPOINT` | Vide; informations d'identification/destination mondiales. |
| `MYBING_MSCLKID_DAYS`, `MYBING_ID_SYNC` | `90`, `1` ; Durée de vie Click-ID et ID Sync. |
| `MYBING_PAGEVIEW`, `MYBING_PURCHASE`, `MYBING_PURCHASE_PAID_ONLY` | `1`, `1`, `0`. |
| `MYBING_LEAD`, `MYBING_LEAD_N`, `MYBING_INITIATE`, `MYBING_INITIATE_D` | `0`, `1`, `1`, `1`. |
| `MYBING_SEARCH`, `MYBING_ADDTOCART`, `MYBING_REMOVECART`, `MYBING_WISHLIST` | Tous les `1`. |
| `MYBING_ADDPAYMENT`, `MYBING_CONTACT`, `MYBING_REFUND` | Tous les `1`. |
| `MYBING_DPA`, `MYBING_VCONTENT`, `MYBING_VIEW_ITEM_LIST`, `MYBING_REG` | Tous les `1`. |
| `MYBING_ATTRID`, `MYBING_SEPSIGN`, `MYBING_PREFIX`, `MYBING_SUFIX` | `0`, `-`, vide par langue, vide par langue. |
| `MYBING_EXFREE`, `MYBING_ATC_B`, `MYBING_ATC_PPP`, `MYBING_PREPRICE` | `0`, `.add-to-cart`, `.current-price span`, `0`. |
| `MYBING_CONCURR`, `MYBING_CURRSELECT` | `0`, `0`. |
| `MYBING_CONSENT_REQUIRED`, `MYBING_CONSENT_MODE`, `MYBING_TCF` | `0`, `auto`, `1`. |
| `MYBING_GHOST`, `MYBING_USER_ID`, `MYBING_ENHANCED_CONV` | `1`, `0`, `0`. |
| `MYBING_IGNORE_ADMIN`, `MYBING_BOT_FILTER`, `MYBING_DEBUG` | `1`, `0`, `0`. |
| `MYBING_PAID_STATUSES`, `MYBING_REFUND_STATUSES` | ID d'état vides, séparés par des virgules. |
| `MYBING_STATS_ENABLED`, `MYBING_STATS_RETENTION`, `MYBING_STATS_POLL`, `MYBING_STATS_LOG_PV` | `1`, `14`, `5`, `0`. |
| `MYBING_WIZARD_DONE`, `MYBING_WIZARD_REDO` | `0`, `0`. |
| `MYBING_INSTALL_SQL_WARN`, `MYBING_INSTALL_ERROR` | Diagnostics d'installation d'exécution. |
| `MYBING_LAST_FLUSH` | Résumé du vidage JSON d’exécution ; pas dans la liste des clés de désinstallation. |

L'installation/désinstallation supprime également les anciens `MYBING_CAPI_AUTH_CLIENT_ID`, `MYBING_CAPI_AUTH_CLIENT_SECRET`, `MYBING_CAPI_AUTH_REFRESH_TOKEN`, `MYBING_CAPI_AUTH_ACCESS_TOKEN`, `MYBING_CAPI_AUTH_ACCESS_EXPIRES`, `MYBING_PROFILE_ID`, `MYBING_CAPI_REGION`, `MYBING_CAPI_COUNTRY`, `MYBING_ATC_PC`, `MYBING_ATC_PP`, `MYBING_LINKER_DOMAINS` et `MYBING_ADS_ID`. `MYBING_DEBUG_MODE` est purgé lors de l'installation mais est absent de la liste de désinstallation.

Le programme de mise à jour utilise `mypresta_updates`, `update_mybing` et `updatev_mybing` ; ceux-ci peuvent rester après la désinstallation. `mypresta_updates` est partagé.

### 6.7 Désinstallation, traductions et extension

`uninstall()` supprime l'onglet masqué, supprime toutes les tables de modules, supprime les valeurs `getConfigurationKeys()` et les diagnostics d'installation, puis appelle `parent::uninstall()`. Il ne supprime pas les clés de mise à jour ni `MYBING_LAST_FLUSH`.

Il n'y a pas de remplacement PrestaShop. Les traductions vivent dans `translations/{iso}.php` ; la plupart des chaînes d'interface utilisateur utilisent `$this->l()` ou Smarty `{l}`, tandis que les noms d'événements et certains diagnostics de classe restent en anglais.

Les thèmes peuvent repositionner les hooks pris en charge et styliser l'inspecteur, mais le bloc de produit est intentionnellement masqué. Conservez les attributs de données et les scripts lors du remplacement des modèles de hook. Un CMP personnalisé peut envoyer `mybing.consent` avec l'autorisation `1` ou `0`, ou fournir un signal reconnu par `MybingConsent`.

## 7. Aide

Ouvrez la page du module : https://mypresta.eu/modules/advertising-and-marketing/microsoft-advertising-uet-tag-conversions-api.html

Connectez-vous à votre compte client sur mypresta.eu, ouvrez la page de contact et choisissez **Support for paid modules**. La connexion est requise ; sélectionnez ensuite ce module dans votre historique d'achat et incluez le mode de suivi, l'erreur visible et le résultat du diagnostic.
