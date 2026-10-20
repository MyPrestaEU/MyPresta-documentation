---
title: "Remises cumulatives - Manuel du marchand et guide de configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop Remises cumulatives par MyPresta.eu."
sidebar:
  label: "Remises cumulatives - Manuel du marchand et guide de configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Cumulative discounts sur MyPresta.eu](https://mypresta.eu/modules/advertising-and-marketing/cumulative-discounts.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/advertising-marketing/cumulative-discounts/)
>
> ---


# Remises cumulatives

## 1. Exigences et compatibilité

- **Versions PrestaShop prises en charge** : PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilité PHP** : PHP 5.6 - 8.5
- **Exigences d'hébergement** : Les extensions PHP standard (cURL, JSON, OpenSSL) sont requises, qui sont généralement disponibles sur la plupart des environnements d'hébergement compatibles PrestaShop.

## 2. Parcours de configuration complet (chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

C'est l'écran de configuration principal où vous définissez le fonctionnement de votre programme de remises cumulatives.

#### **Activer le programme**

- **Ce que fait ce paramètre :** C'est l'interrupteur principal pour activer ou désactiver l'ensemble du programme de remises cumulatives.
- **Effet de la modification de ce paramètre :**
  - *Lorsqu'il est activé :* Le module suivra activement les dépenses des clients, attribuera des groupes et affichera les informations de remise dans votre front office.
  - *Lorsqu'il est désactivé :* Le module cessera toutes les opérations, aucune remise ne sera appliquée et aucune information ne sera affichée.
- **Valeur recommandée :** OUI (pour activer le programme).
- **Scénario/exemple de marchand :** Si vous configurez le module pour la première fois, activez-le après avoir configuré tous les autres paramètres. Si vous devez suspendre temporairement le programme (par exemple, pendant une vente majeure où d'autres remises s'appliquent), vous pouvez le désactiver ici.

#### **Désactiver le programme de remises cumulatives pour les groupes de clients sélectionnés**

- **Ce que fait ce paramètre :** Vous permet de sélectionner des groupes de clients spécifiques qui ne devraient *pas* faire partie du programme de remises cumulatives. Les clients de ces groupes sélectionnés ne recevront pas de remises cumulatives, quelles que soient leurs dépenses.
- **Effet de la modification de ce paramètre :**
  - *Lorsqu'un groupe est sélectionné :* Les clients appartenant à ce groupe seront exclus du programme.
  - *Lorsqu'aucun groupe n'est sélectionné :* Tous les groupes de clients sont éligibles au programme par défaut.
- **Valeur recommandée :** Sélectionnez des groupes comme « Visiteurs » ou « Invités » si vous souhaitez que seuls les clients enregistrés participent. Vous pouvez également exclure un groupe « Grossiste » s'il a une structure de prix distincte.
- **Scénario/exemple de marchand :** Vous pourriez avoir un groupe de clients « Grossiste » qui bénéficie déjà de prix spéciaux. Pour éviter les conflits ou les doubles remises, vous sélectionneriez le groupe « Grossiste » ici pour l'exclure du programme de remises cumulatives.

#### **Période**

- **Ce que fait ce paramètre :** Définit la période sur laquelle les commandes des clients sont prises en compte lors du calcul de leurs dépenses totales.
- **Effet de la modification de ce paramètre :**
  - *Toutes les commandes :* Prend en compte toutes les commandes jamais passées par le client.
  - *Commandes de l'année dernière / Commandes du dernier semestre / Commandes du dernier trimestre / Commandes du dernier mois / Commandes de la dernière semaine / Commandes du dernier jour :* Limite le calcul aux commandes passées au cours de la période récente spécifiée.
  - *Seule la dernière commande valide :* Ne prend en compte que la commande complétée la plus récente.
- **Valeur recommandée :** « Commandes de l'année dernière » ou « Toutes les commandes » sont des choix courants pour les programmes de fidélité. « Commandes du dernier mois » pourrait être utilisé pour une poussée de fidélité plus agressive et à court terme.
- **Scénario/exemple de marchand :** Si vous souhaitez récompenser la fidélité à long terme, choisissez « Toutes les commandes ». Si vous souhaitez encourager les achats récents et fréquents, « Commandes du dernier semestre » pourrait être plus approprié.

#### **Type de prix**

- **Ce que fait ce paramètre :** Détermine si le calcul des dépenses cumulatives doit utiliser le « Prix net » (prix avant taxes) ou le « Prix brut » (prix incluant les taxes) des produits dans les commandes.
- **Effet de la modification de ce paramètre :**
  - *Prix net :* Les dépenses totales seront calculées sur la base des prix des produits hors taxes.
  - *Prix brut :* Les dépenses totales seront calculées sur la base des prix des produits incluant les taxes.
- **Valeur recommandée :** Le « Prix brut » est souvent plus intuitif pour les clients car il reflète ce qu'ils ont réellement payé. Cependant, le « Prix net » pourrait être préféré pour les boutiques B2B ou pour la cohérence comptable interne.
- **Scénario/exemple de marchand :** Si votre public cible est principalement des consommateurs, l'utilisation du « Prix brut » est la plus logique car elle correspond au prix final qu'ils voient et paient.

#### **Sélectionner les statuts de commande**

- **Ce que fait ce paramètre :** Vous permet de spécifier quels statuts de commande doivent être inclus lors du calcul des dépenses totales d'un client. Seules les commandes avec ces statuts sélectionnés compteront pour le total cumulatif.
- **Effet de la modification de ce paramètre :**
  - *Lorsque « Paiement accepté » et « Livré » sont sélectionnés :* Seules les commandes qui ont été payées avec succès et livrées contribueront au total des dépenses du client.
  - *Lorsque « Annulé » ou « Remboursé » NE SONT PAS sélectionnés :* Ces commandes ne compteront pas, empêchant les clients de gagner des points de fidélité pour des achats non complétés.
- **Valeur recommandée :** Sélectionnez les statuts qui indiquent une transaction complétée et réussie, tels que « Paiement accepté », « Livré ». Excluez les statuts comme « Annulé », « Remboursé », « Erreur de paiement », etc.
- **Scénario/exemple de marchand :** Vous voulez vous assurer que seuls les achats réels et complétés contribuent à la fidélité. Vous sélectionneriez « Paiement accepté » et « Livré » pour vous assurer que les clients ne gagnent des remises que pour les commandes qu'ils ont réellement payées et reçues.

#### **Exclure les commandes passées avec un code de bon de réduction**

- **Ce que fait ce paramètre :** Si activé, les commandes où un bon de réduction ou un code promo a été utilisé ne compteront pas pour le total des dépenses cumulatives du client.
- **Effet de la modification de ce paramètre :**
  - *Lorsqu'il est activé :* Les commandes avec des bons de réduction sont ignorées pour les calculs de fidélité.
  - *Lorsqu'il est désactivé :* Les commandes avec des bons de réduction *comptent* pour le total cumulatif.
- **Valeur recommandée :** OUI, si vous souhaitez récompenser plus fortement les achats à prix plein. NON, si vous souhaitez encourager tout achat, même les articles à prix réduit, à contribuer à la fidélité.
- **Scénario/exemple de marchand :** Vous organisez une promotion spéciale avec un coupon de 20 % de réduction. Si vous activez ce paramètre, les clients utilisant ce coupon ne verront pas cette commande compter pour leur progression de remise cumulative, garantissant qu'ils gagnent de la fidélité sur les achats à prix plein.

#### **Exclure les produits avec des prix spécifiques**

- **Ce que fait ce paramètre :** Si activé, les produits qui ont un « prix spécifique » (par exemple, un prix promotionnel spécial défini pour une durée limitée ou un groupe de clients particulier) ne contribueront pas au calcul des dépenses cumulatives.
- **Effet de la modification de ce paramètre :**
  - *Lorsqu'il est activé :* Les produits avec des prix spécifiques sont ignorés pour les calculs de fidélité.
  - *Lorsqu'il est désactivé :* Les produits avec des prix spécifiques *comptent* pour le total cumulatif.
- **Valeur recommandée :** OUI, si vous souhaitez récompenser les achats d'articles à prix régulier. NON, si vous souhaitez que tous les achats de produits contribuent.
- **Scénario/exemple de marchand :** Vous avez une vente flash sur certains articles en utilisant la fonction de prix spécifique de PrestaShop. Si vous activez cela, l'achat de ces articles en solde n'aidera pas le client à atteindre le niveau de fidélité suivant, l'encourageant plutôt à acheter des articles à prix régulier.

#### **Exclure les produits avec des remises par quantité**

- **Ce que fait ce paramètre :** Si activé, les produits achetés avec une remise par quantité (par exemple, « Achetez 3, obtenez 10 % de réduction ») ne contribueront pas au calcul des dépenses cumulatives.
- **Effet de la modification de ce paramètre :**
  - *Lorsqu'il est activé :* Les produits achetés avec des remises par quantité sont ignorés pour les calculs de fidélité.
  - *Lorsqu'il est désactivé :* Les produits achetés avec des remises par quantité *comptent* pour le total cumulatif.
- **Valeur recommandée :** OUI, si vous souhaitez récompenser les achats d'articles uniques à prix plein. NON, si vous souhaitez encourager les achats en gros à contribuer à la fidélité.
- **Scénario/exemple de marchand :** Vous offrez une offre « achetez 5, obtenez 15 % de réduction ». Si vous activez cela, les clients profitant de cette offre ne verront pas ces articles spécifiques compter pour leur progression de remise cumulative.

#### **Groupe de clients par défaut**

- **Ce que fait ce paramètre :** Définit le groupe de clients par défaut auquel les clients seront affectés s'ils ne remplissent pas les critères de dépenses pour un autre groupe de remises cumulatives. Il s'agit généralement de votre groupe « Client » standard.
- **Effet de la modification de ce paramètre :** Garantit que les clients appartiennent toujours à un groupe valide, même s'ils n'ont pas dépensé suffisamment pour être éligibles à un niveau de remise spécial.
- **Valeur recommandée :** Votre groupe « Client » standard (souvent ID 3).
- **Scénario/exemple de marchand :** Un nouveau client s'inscrit. Il n'a pas encore effectué d'achats, donc le module l'affecte au « groupe de clients par défaut » (par exemple, « Client »), qui pourrait avoir 0 % de remise. Au fur et à mesure qu'il dépense, il sera déplacé vers « Bronze », « Argent », etc.

#### **Informations pour les clients connectés (page produit)**

- **Ce que fait ce paramètre :** C'est un éditeur de texte où vous pouvez personnaliser le message affiché aux *clients connectés* sur les pages produit. Ce message les informe généralement de leur statut de remise actuel ou de leur progression.
- **Effet de la modification de ce paramètre :** Le texte que vous saisissez ici apparaîtra sur les pages produit pour les clients connectés à leur compte. Vous pouvez utiliser des variables Smarty (comme `{$total_spent}`, `{$discount_value}`, `{$next_group_name}`, `{$next_group_value}`) pour personnaliser le message.
- **Valeur recommandée :** Un message de bienvenue comme : « Bonjour {$customer\_name} ! Vous êtes actuellement dans le groupe {$current\_group\_name} et bénéficiez d'une remise de {$discount\_value} %. Dépensez {$to\_next\_group} de plus pour atteindre le groupe {$next\_group\_name} et obtenir {$next\_group\_value} % de réduction ! »
- **Scénario/exemple de marchand :** Vous voulez motiver les clients connectés. Vous pouvez leur dire exactement combien ils doivent dépenser de plus pour obtenir une remise plus élevée, créant ainsi une incitation claire.

#### **Informations pour les clients non connectés (page produit)**

- **Ce que fait ce paramètre :** C'est un éditeur de texte où vous pouvez personnaliser le message affiché aux *clients invités ou non connectés* sur les pages produit. Ce message les encourage généralement à s'inscrire et à participer au programme de fidélité.
- **Effet de la modification de ce paramètre :** Le texte que vous saisissez ici apparaîtra sur les pages produit pour les clients qui ne sont pas connectés à leur compte.
- **Valeur recommandée :** Un message invitant comme : « Inscrivez-vous maintenant et commencez à gagner des remises cumulatives ! Plus vous dépensez, plus vous économisez ! »
- **Scénario/exemple de marchand :** Un nouveau visiteur arrive sur une page produit. Ce message peut l'inciter à créer un compte en soulignant les avantages de votre programme de fidélité, le convertissant potentiellement en client enregistré.

#### **Informations pour les clients connectés (page panier)**

- **Ce que fait ce paramètre :** C'est un éditeur de texte où vous pouvez personnaliser le message affiché aux *clients connectés* sur la page du panier. Ce message peut renforcer leur statut de remise ou montrer comment leur panier actuel contribue à leur fidélité.
- **Effet de la modification de ce paramètre :** Le texte que vous saisissez ici apparaîtra sur la page du panier pour les clients connectés. Vous pouvez utiliser des variables Smarty.
- **Valeur recommandée :** Similaire au message de la page produit, mais peut-être en mettant l'accent sur la contribution du panier actuel : « La valeur de votre panier actuel est de {$cart\_value}. Avec votre remise {$current\_group\_name}, vous économisez {$discount\_value} % ! Dépensez {$to\_next\_group} de plus pour atteindre le groupe {$next\_group\_name} ! »
- **Scénario/exemple de marchand :** Un client est sur le point de passer à la caisse. Ce message lui rappelle ses avantages de fidélité et pourrait même l'encourager à ajouter un petit article pour atteindre le niveau de remise suivant.

#### **Informations pour les clients non connectés (page panier)**

- **Ce que fait ce paramètre :** C'est un éditeur de texte où vous pouvez personnaliser le message affiché aux *clients invités ou non connectés* sur la page du panier. Ce message les encourage à s'inscrire avant de finaliser leur achat pour commencer à gagner de la fidélité.
- **Effet de la modification de ce paramètre :** Le texte que vous saisissez ici apparaîtra sur la page du panier pour les clients non connectés.
- **Valeur recommandée :** « Ne manquez pas les remises de fidélité ! Inscrivez-vous avant de passer à la caisse pour commencer à gagner des récompenses sur vos achats ! »
- **Scénario/exemple de marchand :** Un client invité a des articles dans son panier. Ce message fournit une dernière impulsion pour créer un compte, transformant un acheteur occasionnel en un client fidèle potentiel.

### 2.2 Écrans d'administration dédiés et vues de contrôleur

#### AdminCudiListController (Back Office > Remises cumulatives > Gérer les remises)

- **Nom de l'écran et emplacement du menu :** Vous pouvez trouver cet écran en naviguant vers **Catalogue > Remises cumulatives** (ou un emplacement similaire selon votre version de PrestaShop et la personnalisation du menu). L'étiquette exacte pourrait être « Gérer les remises » ou « Règles de remise cumulative ».
- **Actions et paramètres disponibles :** Cet écran présente une grille (liste) de vos règles de remise cumulative définies. Chaque règle spécifie :
  - **Montant de dépense minimum :** Le montant total qu'un client doit dépenser pour être éligible à ce groupe.
  - **Groupe de clients :** Le groupe de clients PrestaShop auquel les clients répondant aux critères de dépense seront affectés.
  - **Pourcentage de remise :** Le pourcentage de remise associé à ce groupe de clients.
  - **Actions :** Vous pouvez « Ajouter de nouvelles » règles, « Modifier » les règles existantes ou « Supprimer » les règles.
- **Effet des modifications :**
  - **Ajout d'une nouvelle règle :** Crée un nouveau niveau dans votre programme de fidélité. Par exemple, « Dépensez 500 € pour rejoindre le groupe Or et obtenir 15 % de réduction. »
  - **Modification d'une règle :** Modifie le seuil de dépense ou le groupe/remise attribué pour un niveau existant. Les modifications affecteront les futures attributions de groupe et les recalculs.
  - **Suppression d'une règle :** Supprime un niveau de fidélité. Les clients précédemment dans ce groupe seront réaffectés en fonction des règles restantes.
- **Flux de travail recommandé pour la gestion quotidienne de la boutique :**
  1. **Planifiez vos niveaux :** Décidez de vos seuils de dépense et des groupes de remise correspondants (par exemple, Bronze : 100 € pour 5 %, Argent : 500 € pour 10 %, Or : 1000 € pour 15 %).
  2. **Créez des groupes de clients :** Assurez-vous d'avoir des groupes de clients correspondants dans PrestaShop (Back Office > Clients > Groupes) pour chaque niveau (par exemple, « Client Bronze », « Client Argent », « Client Or »). Attribuez le pourcentage de remise global approprié à chacun de ces groupes.
  3. **Ajoutez des règles :** Utilisez le bouton « Ajouter nouveau » pour créer chaque niveau, en liant le montant de dépense au groupe de clients correct.
  4. **Ordonnez les règles :** Le module traite les règles du seuil de dépense le plus bas au plus élevé. Assurez-vous que vos règles sont logiquement ordonnées.
  5. **Examinez et ajustez :** Révisez périodiquement vos niveaux pour vous assurer qu'ils sont toujours efficaces et rentables.

#### index.php (cudi/controllers/admin/index.php)

Ce fichier est généralement un espace réservé ou un redirecteur au sein de la structure du contrôleur d'administration et ne représente pas un écran direct et configurable pour le marchand. Il fait partie du routage interne du module pour le back office. Toute la configuration du côté marchand pour les remises cumulatives se fait soit sur la page de configuration principale du module, soit via le `AdminCudiListController`.

### 2.3 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Valeur par défaut / Recommandée | Objectif et impact |
| --- | --- | --- | --- |
| **Page de configuration du module** | Activer le programme | OUI | Interrupteur principal pour le programme de fidélité. |
| | Désactiver le programme de remises cumulatives pour les groupes de clients sélectionnés | Sélectionner « Invité », « Visiteur » | Exclut les groupes de clients spécifiés du programme. |
| | Période | Commandes de l'année dernière / Toutes les commandes | Définit la période pour le calcul des dépenses totales. |
| | Type de prix | Prix brut | Détermine si les prix nets ou bruts sont utilisés pour le calcul des dépenses. |
| | Sélectionner les statuts de commande | Paiement accepté, Livré | Spécifie quels statuts de commande comptent pour les dépenses totales. |
| | Exclure les commandes passées avec un code de bon de réduction | OUI | Empêche les commandes avec des bons de réduction de contribuer à la fidélité. |
| | Exclure les produits avec des prix spécifiques | OUI | Empêche les produits en promotion à prix spécifique de contribuer. |
| | Exclure les produits avec des remises par quantité | OUI | Empêche les produits avec des remises par quantité de contribuer. |
| | Groupe de clients par défaut | Votre groupe « Client » standard | Le groupe attribué si aucun niveau de fidélité n'est atteint. |
| | Informations pour les clients connectés (page produit) | Texte personnalisable avec variables Smarty | Message pour les utilisateurs connectés sur les pages produit. |
| | Informations pour les clients non connectés (page produit) | Texte personnalisable | Message pour les invités sur les pages produit, encourageant l'inscription. |
| | Informations pour les clients connectés (page panier) | Texte personnalisable avec variables Smarty | Message pour les utilisateurs connectés sur les pages panier. |
| | Informations pour les clients non connectés (page panier) | Texte personnalisable | Message pour les invités sur les pages panier, encourageant l'inscription. |
| **AdminCudiListController** | Montant de dépense minimum | Varie selon le niveau | Seuil pour être éligible à un groupe de remise spécifique. |
| | Groupe de clients | Vos groupes de fidélité personnalisés (par exemple, Bronze, Argent) | Le groupe PrestaShop attribué lorsque le seuil de dépense est atteint. |
| | Pourcentage de remise | Varie selon le niveau | La remise appliquée au groupe de clients attribué. |

## 3. Dépannage pour les marchands et questions fréquemment posées (FAQ)

**Q1 : Mes clients ne sont pas affectés aux bons groupes, ou les remises ne s'appliquent pas.**
R1 :

- **Vérifiez « Activer le programme » :** Assurez-vous que l'interrupteur principal dans la configuration du module est réglé sur OUI.
- **Vérifiez « Période » et « Sélectionner les statuts de commande » :** Assurez-vous que les commandes que vous attendez de compter se situent dans la période sélectionnée et ont les bons statuts de commande (par exemple, « Livré », « Paiement accepté »).
- **Examinez les paramètres « Exclure » :** Vérifiez si « Exclure les commandes passées avec un code de bon de réduction », « Exclure les produits avec des prix spécifiques » ou « Exclure les produits avec des remises par quantité » sont activés et pourraient empêcher les commandes de compter.
- **Videz le cache :** Allez dans **Paramètres avancés > Performances** et cliquez sur « Vider le cache ». Parfois, le cache de PrestaShop peut empêcher les modifications de prendre effet immédiatement.
- **Vérifiez les groupes de clients :** Assurez-vous que les groupes de clients que vous avez liés dans le `AdminCudiListController` existent réellement dans PrestaShop (Clients > Groupes) et ont le bon pourcentage de remise global qui leur est attribué.
- **Ordre des règles :** Assurez-vous que vos règles dans `AdminCudiListController` sont ordonnées logiquement du seuil de dépense le plus bas au plus élevé.

**Q2 : Les informations de remise n'apparaissent pas sur mes pages produit ou mon panier.**
R2 :

- **Vérifiez les hooks du module :** Assurez-vous que le module est accroché à `displayProductAdditionalInfo` et `displayShoppingCart`. Vous pouvez le vérifier dans **Design > Positions** (ou **Modules > Positions** dans les anciennes versions de PS). Recherchez « Remises cumulatives » sous ces hooks. Si ce n'est pas le cas, essayez de réinstaller le module ou de l'accrocher manuellement.
- **Texte de configuration du module :** Assurez-vous d'avoir saisi du texte dans les champs « Informations pour les clients connectés » et « Informations pour les clients non connectés » pour les pages produit et panier. Si ces champs sont vides, rien ne s'affichera.
- **Compatibilité du thème :** Votre thème personnalisé peut remplacer les positions de hook standard. Si les informations n'apparaissent toujours pas, vous pourriez avoir besoin d'un développeur web pour ajuster les fichiers `.tpl` de votre thème afin d'inclure explicitement les hooks du module.

**Q3 : Comment traduire les messages du module dans d'autres langues ?**
R3 :

- Allez dans **International > Traductions** dans votre Back Office PrestaShop.
- Sélectionnez « Traductions des modules installés », choisissez votre thème, puis sélectionnez « Remises cumulatives » dans la liste déroulante des modules.
- Vous pouvez ensuite traduire toutes les chaînes statiques du module. Pour les messages personnalisés que vous avez saisis dans la configuration (par exemple, « Informations pour les clients connectés »), vous devrez utiliser le sélecteur de langue en haut à droite de la page de configuration du module pour changer de langue et saisir le texte traduit pour chaque langue.

**Q4 : Puis-je affecter manuellement un client à un groupe de remise cumulative ?**
R4 : Oui, vous pouvez modifier manuellement le groupe d'un client dans son profil client (Back Office > Clients > Clients > Modifier le client). Cependant, le module réévaluera automatiquement son groupe en fonction de son historique de dépenses lors de la prochaine mise à jour du statut de commande ou lorsque la logique du module sera déclenchée. Si vous souhaitez qu'un client reste *en permanence* dans un groupe spécifique, quelles que soient ses dépenses, vous devrez peut-être exclure ce groupe du programme de remises cumulatives (en utilisant le paramètre « Désactiver le programme de remises cumulatives pour les groupes de clients sélectionnés ») et le gérer manuellement.

**Q5 : Que se passe-t-il si les dépenses totales d'un client tombent en dessous d'un niveau (par exemple, en raison d'un remboursement) ?**
R5 : Le module recalcule les dépenses totales du client en fonction de la « Période » et des « Statuts de commande sélectionnés » configurés chaque fois qu'un statut de commande est mis à jour. Si un remboursement fait chuter leur total en dessous d'un niveau, le module les réaffectera automatiquement au groupe de niveau inférieur approprié lors du prochain recalcul, garantissant ainsi la précision.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

Cette section est strictement destinée aux développeurs, aux webmasters de boutiques et aux agences techniques qui maintiennent ou étendent la boutique.

### 4.1 Aperçu de l'architecture

Le module « Remises cumulatives » (`cudi`) suit une architecture de module PrestaShop standard, tirant parti des principes MVC. Il fonctionne principalement en s'accrochant à divers événements du front-office et du back-office pour calculer les dépenses des clients et les affecter dynamiquement aux groupes de clients appropriés. La configuration est gérée via la méthode `getContent()` principale et un `AdminCudiListController` dédié pour la gestion des niveaux de remise. Il n'introduit pas de tables de base de données personnalisées mais s'appuie sur `ps_configuration` de PrestaShop pour les paramètres et `ps_customer_group` pour les affectations de groupes.

### 4.2 Contrôleurs (`controllers/`)

#### Contrôleurs Front-Office

- `cudi/controllers/front/index.php`
  - **Nom de la classe et classe parente :** `CudiIndexModuleFrontController` étend `ModuleFrontController`.
  - **Responsabilité :** Ce contrôleur sert probablement de valeur par défaut ou de secours pour le routage front-office du module. Il peut gérer la configuration initiale ou la redirection, bien que `mydiscount.php` soit plus spécifique au contenu destiné aux clients.
- `cudi/controllers/front/mydiscount.php`
  - **Nom de la classe et classe parente :** `CudiMydiscountModuleFrontController` étend `ModuleFrontController`.
  - **Responsabilité :** Ce contrôleur est responsable du rendu de la page dédiée « Mes remises » dans la zone de compte du client. Il récupère les dépenses totales du client, le groupe actuel et la progression vers le niveau suivant, puis transmet ces données au template `myDiscount.tpl` pour l'affichage. Il répond à une route comme `votreboutique.com/module/cudi/mydiscount`.

#### Contrôleurs d'administration Back-Office

- `cudi/controllers/admin/AdminCudiList.php`
  - **Nom de l'onglet et entité gérée :** « Remises cumulatives » (ou similaire, accessible via le menu Catalogue). Gère l'entité `cudi`, qui représente les règles de remise cumulative (seuils de dépenses liés aux groupes de clients).
  - **Responsabilité :** C'est le contrôleur d'administration principal pour la gestion des niveaux de remise. Il étend `AdminController` et utilise `HelperList` pour l'affichage de la grille et `HelperForm` pour l'ajout/la modification de règles individuelles. Il gère les opérations CRUD pour les règles de remise cumulative, y compris la définition des dépenses minimales, du groupe de clients cible et de la remise associée.
- `cudi/controllers/admin/index.php`
  - **Responsabilité :** Ce fichier sert généralement de point d'entrée ou de redirecteur dans le répertoire du contrôleur d'administration. Dans de nombreux modules, il peut contenir un simple `header('Location: ...')` pour rediriger vers le contrôleur d'administration principal (`AdminCudiList.php` dans ce cas) ou être un espace réservé. Il ne représente pas un écran direct et configurable.

### 4.3 Classes et modèles principaux (`classes/`)

Le dossier du module n'indique aucune classe personnalisée dans le répertoire `classes/`. La logique principale pour le calcul des dépenses cumulatives et l'affectation des groupes est probablement encapsulée dans le fichier de module `cudi.php` lui-même, en particulier dans ses méthodes de hook et potentiellement des fonctions d'aide. Il interagit directement avec les `ObjectModel`s `Customer`, `Order`, `OrderState` et `Group` de PrestaShop.

### 4.4 Actifs JavaScript (`views/js/`)

- `cudi/views/admin/js/cudi.js`
  - **Portée :** Back-office.
  - **Responsabilité :** Ce script gère probablement les interactions côté client sur la page de configuration du module ou le `AdminCudiListController`. Cela pourrait inclure :
    - La visibilité dynamique des champs de formulaire en fonction des options sélectionnées (par exemple, afficher/masquer les options d'exclusion).
    - Les appels AJAX pour enregistrer les paramètres sans rechargement complet de la page.
    - La validation des entrées ou les éléments interactifs spécifiques à l'interface d'administration du module.
    - Les écouteurs d'événements pour les modifications de formulaire ou les clics de bouton dans le panneau d'administration.

### 4.5 Feuilles de style CSS (`views/css/`)

- `cudi/views/admin/css/cudi.css`
  - **Portée :** Style du formulaire d'administration du back-office.
  - **Responsabilité :** Fournit le style pour la page de configuration du module et l'interface `AdminCudiListController`, garantissant son intégration visuelle avec le thème du back-office de PrestaShop.
  - **Sélecteurs de classe CSS clés :** Cible probablement des ID ou des classes spécifiques dans les templates d'administration du module (par exemple, `.cudi-settings-panel`, `.cudi-list-table`).
- `cudi/views/css/cudi.css`
  - **Portée :** Style client du front-office.
  - **Responsabilité :** Style les informations affichées aux clients sur les pages produit, les pages panier et la page « Mes remises ».
  - **Sélecteurs de classe CSS clés :** Ciblera les éléments générés par les templates front-office du module (par exemple, `.cudi-info-block`, `.cudi-discount-message`, `.cudi-progress-bar`). Les développeurs peuvent les remplacer dans le `custom.css` de leur thème ou en créant un thème enfant.

### 4.6 Structure des templates Smarty (`views/templates/`)

#### Templates de hook (`views/templates/hook/`)

- `cudi/views/templates/hook/displayProductAdditionalInfo-unlogged.tpl`
  - **Hook :** `displayProductAdditionalInfo` (spécifiquement pour les utilisateurs non connectés).
  - **Sortie :** Affiche le message personnalisable pour les clients non connectés sur les pages produit, encourageant l'inscription et soulignant le programme de fidélité.
- `cudi/views/templates/hook/displayProductAdditionalInfo.tpl`
  - **Hook :** `displayProductAdditionalInfo` (pour les utilisateurs connectés).
  - **Sortie :** Affiche le message personnalisable pour les clients connectés sur les pages produit, montrant leur statut de remise actuel et leur progression vers le niveau suivant.
- `cudi/views/templates/hook/myAccount.tpl`
  - **Hook :** `displayCustomerAccount`.
  - **Sortie :** Rend un lien ou un bloc dans la section « Mon compte » du client, généralement intitulé « Mes remises », qui mène à la page `mydiscount` dédiée.

#### Templates d'administration (`views/templates/admin/`)

- `cudi/views/admin/assignButton.tpl`
  - **Portée :** Back-office.
  - **Sortie :** Rend probablement un bouton ou un lien d'action dans l'interface d'administration, éventuellement pour déclencher un recalcul manuel ou une affectation de groupes de clients.
- `cudi/views/admin/orderstates.tpl`
  - **Portée :** Back-office.
  - **Sortie :** Utilisé dans le formulaire de configuration principal du module (`getContent()`) pour rendre la liste déroulante à sélection multiple ou les cases à cocher pour « Sélectionner les statuts de commande ».

#### Templates Front-office (`views/templates/front/`)

- `cudi/views/templates/front/myDiscount.tpl`
  - **Portée :** Front-office.
  - **Sortie :** C'est le template de page dédié pour le `CudiMydiscountModuleFrontController`. Il affiche un aperçu complet du statut de fidélité du client, y compris le total dépensé, le groupe actuel, le pourcentage de remise et la progression vers des niveaux supérieurs.

### 4.7 Schéma de base de données et carte des hooks

#### Tables de base de données

Le module ne crée pas de tables SQL personnalisées. Il stocke ses paramètres de configuration dans la table `ps_configuration` de PrestaShop, en utilisant des clés comme `CUDI_ACTIVE`, `CUDI_ORDERSDATE`, `CUDI_PRICETYPE`, `CUDI_ORDERSTATES`, `CUDI_EX_SP`, `CUDI_EX_SP_QTY`, `CUDI_ORDERCOUPON`, `CUDI_DEFGROUP`, `CUDI_GROUPSNOT`, `CUDI_SHOWINFO_PRODUCT`, `CUDI_SHOWINFO_CART`, `logged_cudi_contents`, `unlogged_cudi_contents`.
Les règles de remise cumulative (seuils de dépenses et groupes de clients associés) sont probablement stockées sous forme de données sérialisées dans une entrée `ps_configuration` ou gérées directement par le `AdminCudiListController` qui pourrait utiliser une table personnalisée (bien que non explicitement listée dans `classes/` ou `sql/`). *Autocorrection : Étant donné le `AdminCudiListController` et sa gestion de l'entité `cudi`, il est très probable qu'une table personnalisée `ps_cudi` existe, même si elle n'est pas explicitement listée dans `classes/` ou `sql/` dans le dossier fourni. Cette table stockerait l'`id_cudi`, `min_spend`, `id_group`, `discount_percentage` pour chaque règle.*

#### Tableau des hooks enregistrés

| Nom du hook | Moment d'exécution | Objectif technique |
| --- | --- | --- |
| `displayHeader` | Rendu dans la section `<head>` de toutes les pages du front-office. | Utilisé pour inclure les actifs CSS/JS du module pour le front-office, ou pour initialiser des variables JS globales. |
| `displayProductAdditionalInfo` | Sur les pages produit, généralement sous la description du produit ou le bouton d'ajout au panier. | Affiche les informations du programme de fidélité (remise actuelle, progression) aux clients. |
| `displayCustomerAccount` | Sur la page « Mon compte » du client. | Ajoute un lien vers la page dédiée « Mes remises ». |
| `displayShoppingCart` | Sur la page de résumé du panier. | Affiche les informations du programme de fidélité (remise actuelle, contribution du panier) aux clients. |
| `updateOrderStatus` | Déclenché lorsqu'un statut de commande est modifié dans le back-office. | **Crucial pour recalculer les dépenses totales du client et réaffecter son groupe.** |
| `actionOrderStatusUpdate` | Similaire à `updateOrderStatus`, offre un contrôle plus granulaire après une mise à jour du statut de commande. | **Également crucial pour recalculer les dépenses totales du client et réaffecter son groupe.** |
| `actionAdminControllerSetMedia` | Dans le back-office, lorsqu'un contrôleur d'administration est chargé. | Utilisé pour inclure les actifs CSS/JS du module pour le back-office (par exemple, `cudi.js`, `cudi.css`). |

## 5. Support officiel et mises à jour

Pour les dernières mises à jour du module, les corrections de bugs et le support officiel, veuillez vous connecter à votre compte client sur [MyPresta.eu](https://mypresta.eu/my-account/orders/). Vous y trouverez vos modules achetés et leurs liens de téléchargement. Pour une assistance technique, veuillez utiliser les canaux de support fournis sur MyPresta.eu.
