---
title: "Bon d'achat pour un ami - Manuel du marchand et guide de configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop 'Bon d'achat pour un ami' par MyPresta.eu."
sidebar:
  label: "Bon d'achat pour un ami - Manuel du marchand et guide de configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Voucher for friend sur MyPresta.eu](https://mypresta.eu/modules/advertising-and-marketing/voucher-for-friend.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/advertising-marketing/voucher-for-friend/)
>
> ---


# Bon d'achat pour un ami

## 1. Exigences et compatibilité

- **Versions PrestaShop prises en charge** : PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x
- **Compatibilité PHP** : PHP 5.6 - 8.5
- **Exigences d'hébergement** : Les extensions PHP standard (cURL, JSON, OpenSSL) sont généralement requises pour une boutique PrestaShop et sont suffisantes pour ce module.

## 2. Guide de configuration complet (chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer > Bon d'achat pour un ami)

C'est l'écran de configuration principal du module « Bon d'achat pour un ami ». Ici, vous définirez le comportement de la fonction de partage de bons d'achat et son emplacement sur votre boutique.

#### **Paramètres et options**

- **Afficher le lien « Bon d'achat pour un ami » dans le bloc Mon compte (fvc\_b\_position)**

  - **Ce que fait ce paramètre :** Contrôle si un lien vers la page « Bon d'achat pour un ami » apparaît dans le bloc « Mon compte » du client, qui se trouve généralement dans l'en-tête ou une colonne après qu'un client se soit connecté.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'activé (Oui) :* Un lien, généralement intitulé « Mes bons d'achat » ou « Bon d'achat pour un ami », sera visible dans le bloc du compte client, offrant un accès rapide à la fonction de partage.
    - *Lorsqu'désactivé (Non) :* Le lien n'apparaîtra pas dans le bloc du compte client. Les clients devront naviguer vers leur page complète « Mon compte » pour trouver le lien, ou utiliser une autre option de placement.
  - **Valeur recommandée :** OUI
  - **Scénario / exemple de marchand :** Si vous voulez faciliter la recherche de la fonctionnalité par les clients connectés, activez ceci. C'est un emplacement proéminent pour les utilisateurs actifs.
- **Afficher le lien « Bon d'achat pour un ami » sur la page Mon compte (fvc\_b\_position2)**

  - **Ce que fait ce paramètre :** Détermine si un lien vers la page « Bon d'achat pour un ami » est affiché sur la page principale « Mon compte », qui liste toutes les options spécifiques au client.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'activé (Oui) :* Un lien dédié apparaîtra sur la page « Mon compte », généralement sous forme d'icône ou de lien texte à côté d'autres options comme « Historique des commandes » ou « Mes adresses ».
    - *Lorsqu'désactivé (Non) :* Le lien ne sera pas présent sur la page « Mon compte ».
  - **Valeur recommandée :** OUI
  - **Scénario / exemple de marchand :** C'est un endroit standard et attendu pour que les clients trouvent une telle fonctionnalité. L'activer assure la découvrabilité pour tous les utilisateurs connectés.
- **Afficher le lien « Bon d'achat pour un ami » dans la colonne gauche/droite (fvc\_b\_position3)**

  - **Ce que fait ce paramètre :** Contrôle si un bloc promotionnel ou un lien pour « Bon d'achat pour un ami » apparaît dans les colonnes gauche ou droite de votre boutique. Cela peut être visible pour les visiteurs connectés et non connectés.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'activé (Oui) :* Un bloc ou un lien sera rendu dans la colonne spécifiée, encourageant les visiteurs à utiliser ou à en savoir plus sur la fonction de partage de bons d'achat.
    - *Lorsqu'désactivé (Non) :* Aucun bloc de ce type n'apparaîtra dans les colonnes.
  - **Valeur recommandée :** OUI (si vous souhaitez promouvoir largement la fonctionnalité)
  - **Scénario / exemple de marchand :** Si vous souhaitez promouvoir activement le programme de parrainage auprès de tous les visiteurs, y compris ceux qui ne sont pas encore connectés, l'activation de cette option augmentera la visibilité. Vous pourriez le placer dans la colonne de droite sur les pages produits pour encourager le partage.
- **Nombre de bons d'achat à générer (FV\_NBC)**

  - **Ce que fait ce paramètre :** Définit le nombre de codes de bons d'achat uniques qu'un seul client peut générer et envoyer à des amis.
  - **Effet de la modification de ce paramètre :**
    - *Défini à 1 :* Chaque client ne peut envoyer qu'un seul bon d'achat à un seul ami.
    - *Défini à 5 :* Chaque client peut envoyer jusqu'à cinq bons d'achat à cinq amis différents.
    - *Défini à 0 (ou un nombre très élevé) :* Permet un nombre illimité de générations de bons d'achat par client.
  - **Valeur recommandée :** 3-5 (pour encourager le partage sans surcharger le système ou créer trop de réductions)
  - **Scénario / exemple de marchand :** Si vous souhaitez limiter le nombre de parrainages qu'un seul client peut effectuer pour éviter les abus ou gérer votre budget de réduction, définissez un nombre spécifique comme 3. Si vous souhaitez une diffusion virale maximale, définissez un nombre plus élevé ou 0 pour un nombre illimité.
- **Autoriser les utilisateurs non connectés à envoyer des bons d'achat (FV\_UNLOGGED)**

  - **Ce que fait ce paramètre :** Détermine si les visiteurs qui ne sont pas connectés à un compte client peuvent toujours accéder au formulaire « Bon d'achat pour un ami » et envoyer un bon d'achat.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'activé (Oui) :* Les utilisateurs non connectés verront les liens « Bon d'achat pour un ami » (si activés dans les colonnes/pied de page) et pourront remplir le formulaire. Ils seront probablement invités à saisir leur propre adresse e-mail en tant que parrain.
    - *Lorsqu'désactivé (Non) :* Seuls les clients connectés peuvent accéder et utiliser la fonction de partage de bons d'achat. Les utilisateurs non connectés cliquant sur le lien pourraient être redirigés vers la page de connexion/inscription.
  - **Valeur recommandée :** NON (pour s'assurer que seuls les clients réels parrainent, et pour éviter le spam/les abus)
  - **Scénario / exemple de marchand :** Si vous souhaitez contrôler strictement qui peut parrainer et vous assurer que seule votre base de clients existante participe, désactivez ceci. Si vous souhaitez autoriser n'importe qui à parrainer, même s'il n'a pas encore acheté, activez-le (mais soyez attentif aux spams potentiels).
- **E-mail de la boutique (PS\_SHOP\_EMAIL)**

  - **Ce que fait ce paramètre :** Ce champ affiche généralement l'adresse e-mail de contact par défaut de votre boutique, qui est utilisée comme e-mail « expéditeur » pour la notification de bon d'achat envoyée aux amis. Il est généralement extrait de vos paramètres généraux PrestaShop.
  - **Effet de la modification de ce paramètre :** La modification ici pourrait remplacer l'e-mail de la boutique à l'échelle du système pour les e-mails spécifiques de ce module.
  - **Valeur recommandée :** Assurez-vous qu'il s'agit d'une adresse e-mail valide et professionnelle associée à votre boutique (par exemple, `info@votreboutique.com`).
  - **Scénario / exemple de marchand :** L'ami recevant le bon d'achat verra cet e-mail comme expéditeur. Ce doit être une adresse qu'il peut reconnaître et à laquelle il peut faire confiance.
- **Nom de la boutique (PS\_SHOP\_NAME)**

  - **Ce que fait ce paramètre :** Ce champ affiche généralement le nom officiel de votre boutique, qui est utilisé dans l'objet et le corps de l'e-mail lors de l'envoi du bon d'achat à un ami. Il est généralement extrait de vos paramètres généraux PrestaShop.
  - **Effet de la modification de ce paramètre :** La modification ici pourrait remplacer le nom de la boutique à l'échelle du système pour les e-mails spécifiques de ce module.
  - **Valeur recommandée :** Le nom officiel de votre boutique (par exemple, « Ma Super Boutique »).
  - **Scénario / exemple de marchand :** L'ami recevant le bon d'achat verra ce nom. Il doit être clair et cohérent avec votre marque.

#### 2.1.1 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Valeur par défaut / Recommandée | Objectif et impact |
| --- | --- | --- | --- |
| Configuration du module | Afficher le lien « Bon d'achat pour un ami » dans le bloc Mon compte (fvc\_b\_position) | OUI | Affiche un lien dans le bloc du compte client (en-tête/colonne) pour un accès rapide. |
| Configuration du module | Afficher le lien « Bon d'achat pour un ami » sur la page Mon compte (fvc\_b\_position2) | OUI | Affiche un lien sur la page principale « Mon compte ». |
| Configuration du module | Afficher le lien « Bon d'achat pour un ami » dans la colonne gauche/droite (fvc\_b\_position3) | OUI | Affiche un bloc/lien promotionnel dans les colonnes latérales pour tous les visiteurs. |
| Configuration du module | Nombre de bons d'achat à générer (FV\_NBC) | 3-5 | Limite le nombre de bons d'achat qu'un seul client peut envoyer. |
| Configuration du module | Autoriser les utilisateurs non connectés à envoyer des bons d'achat (FV\_UNLOGGED) | NON | Restreint l'envoi de bons d'achat aux seuls clients connectés. |
| Configuration du module | E-mail de la boutique (PS\_SHOP\_EMAIL) | E-mail de votre boutique | E-mail de l'expéditeur pour les notifications de bons d'achat. |
| Configuration du module | Nom de la boutique (PS\_SHOP\_NAME) | Nom de votre boutique | Nom de la boutique utilisé dans les e-mails de notification de bons d'achat. |

## 3. Dépannage pour les marchands et questions fréquemment posées (FAQ)

**Q1 : Mes clients ne trouvent pas le lien « Bon d'achat pour un ami ».**
R1 : Allez dans **Modules > Gestionnaire de modules > Configurer** pour « Bon d'achat pour un ami ». Assurez-vous que `fvc_b_position`, `fvc_b_position2` et `fvc_b_position3` sont définis sur « Oui » pour les emplacements souhaités (bloc Mon compte, page Mon compte, colonne gauche/droite). Vérifiez également les affectations de hooks de votre thème sous **Design > Positions** pour vous assurer que le module est accroché à `displayMyAccountBlock`, `displayCustomerAccount`, `displayLeftColumn` ou `displayRightColumn` comme prévu.

**Q2 : Les amis ne reçoivent pas les e-mails de bons d'achat.**
R2 :
1. **Vérifiez les dossiers de spam :** Conseillez à vos clients de demander à leurs amis de vérifier leurs dossiers de spam ou de courrier indésirable.
2. **Configuration de l'e-mail de la boutique :** Vérifiez que le paramètre `PS_SHOP_EMAIL` dans la configuration du module est une adresse e-mail valide et active.
3. **Paramètres d'e-mail PrestaShop :** Allez dans **Paramètres avancés > E-mail** dans votre back office PrestaShop. Envoyez un e-mail de test pour vous assurer que le système d'e-mail de votre boutique fonctionne correctement. Si ce n'est pas le cas, vous pourriez avoir un problème avec la configuration de votre serveur SMTP.
4. **Journaux du serveur :** Votre webmaster peut vérifier les journaux de courrier du serveur pour toute erreur liée aux e-mails sortants.

**Q3 : Le code du bon d'achat ne fonctionne pas pour l'ami.**
R3 :
1. **Vérifiez l'expiration/les conditions :** Assurez-vous que le bon d'achat n'a pas expiré et que le panier de l'ami respecte les exigences d'achat minimum ou les restrictions de produits qui pourraient être définies pour le bon d'achat généré (celles-ci sont généralement définies dans la section native « Règles panier » de PrestaShop, que ce module utilise).
2. **Saisie correcte du code :** Confirmez que l'ami saisit le code exactement tel qu'il apparaît (sensible à la casse, pas d'espaces supplémentaires).
3. **Utilisation unique :** La plupart des bons d'achat de parrainage sont à usage unique. Si l'ami a déjà essayé de l'utiliser, il pourrait ne plus être valide.

**Q4 : Le module ne s'affiche pas correctement sur mon thème personnalisé.**
R4 : Les thèmes personnalisés ont souvent un style unique qui peut parfois entrer en conflit avec les conceptions de modules.
1. **Videz le cache :** Tout d'abord, essayez de vider votre cache PrestaShop sous **Paramètres avancés > Performance**.
2. **Surcharges de thème :** Votre webmaster devra peut-être créer des surcharges CSS dans la feuille de style de votre thème pour ajuster l'apparence du module. Le module utilise `views/css/ps16.css` pour son style, ce qui peut être un point de départ pour les ajustements.
3. **Affichage mobile :** Assurez-vous que votre thème est entièrement réactif. Si les problèmes persistent sur mobile, il s'agit probablement d'un conflit CSS nécessitant l'intervention d'un développeur.

**Q5 : Puis-je modifier le montant ou le type de réduction du bon d'achat ?**
R5 : Le module lui-même génère une règle de panier PrestaShop standard. Vous configurerez généralement les spécificités du bon d'achat généré (par exemple, pourcentage de réduction, montant fixe, achat minimum, produits spécifiques) dans la section native **Catalogue > Réductions > Règles panier** de PrestaShop. Le module crée le *mécanisme* de partage, mais les *détails* de la réduction sont gérés par le système de réduction de base de PrestaShop.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

Cette section fournit une analyse approfondie de la structure technique du module « Bon d'achat pour un ami », destinée aux développeurs, webmasters et agences techniques.

### 4.1 Aperçu de l'architecture

Le module « Bon d'achat pour un ami » suit une architecture de module PrestaShop standard, exploitant principalement `ModuleFrontController` pour les interactions front-office et la classe de module principale pour la configuration et la gestion des hooks. Il s'intègre au système natif `CartRule` de PrestaShop pour générer et gérer les bons de réduction. La logique du module est contenue dans son fichier PHP principal et ses contrôleurs frontaux dédiés, avec des templates Smarty gérant la présentation.

### 4.2 Contrôleurs (`controllers/`)

#### Contrôleurs Front-Office

Ces contrôleurs gèrent la logique côté client pour la génération et la gestion des bons d'achat.

- **`controllers/front/index.php`**

  - **Nom de la classe :** `FriendvoucherIndexModuleFrontController` (étend `ModuleFrontController`)
  - **Responsabilité :** Ce contrôleur est probablement responsable de l'affichage du formulaire initial « Bon d'achat pour un ami » où un client saisit les détails de son ami. Il gère la soumission de ce formulaire, valide les entrées, génère la `CartRule` (bon d'achat) et envoie la notification par e-mail à l'ami. Il gère également la logique de limitation du nombre de bons d'achat qu'un client peut envoyer.
  - **Routes :** Répond à une URL comme `votreboutique.com/module/friendvoucher/index`.
- **`controllers/front/myvoucher.php`**

  - **Nom de la classe :** `FriendvoucherMyvoucherModuleFrontController` (étend `ModuleFrontController`)
  - **Responsabilité :** Ce contrôleur est responsable de l'affichage de la page personnelle « Mes bons d'achat » du client, généralement accessible depuis la section « Mon compte ». Il liste les bons d'achat que le client a déjà envoyés et offre potentiellement des options pour afficher leur statut ou en envoyer de nouveaux.
  - **Routes :** Répond à une URL comme `votreboutique.com/module/friendvoucher/myvoucher`.

#### Contrôleurs d'administration Back-Office

Ce module ne semble pas avoir de contrôleurs d'administration personnalisés dédiés. Toute la configuration du back-office est gérée via la méthode `getContent()` de la classe de module principale.

### 4.3 Classes et modèles principaux (`classes/`)

Sur la base de l'inventaire fourni, ce module ne définit pas de classes personnalisées ou d'`ObjectModel` dans un répertoire `classes/`. Il utilise probablement la classe `CartRule` de base de PrestaShop pour la gestion des bons d'achat et `Customer` pour les données utilisateur.

### 4.4 Actifs JavaScript (`views/js/`)

- **`lib/voucherengine/script.js`**
  - **Portée :** Front-office.
  - **Détails :** Ce script gère probablement les interactions côté client sur le formulaire « Bon d'achat pour un ami ». Cela pourrait inclure :
    - La validation du formulaire (par exemple, vérification des formats d'e-mail valides, des champs obligatoires).
    - Les soumissions AJAX de la demande de bon d'achat au contrôleur frontal `index.php`.
    - L'affichage des messages de succès ou d'erreur à l'utilisateur sans rechargement complet de la page.
    - Potentiellement des mises à jour dynamiques du formulaire basées sur l'entrée de l'utilisateur.
    - Tout élément interactif lié au processus de génération de bons d'achat.

### 4.5 Feuilles de style CSS (`views/css/`)

- **`lib/voucherengine/ps16.css`**
  - **Portée :** Style client Front-office.
  - **Détails :** Cette feuille de style fournit le style visuel pour les formulaires, les liens et les blocs d'affichage « Bon d'achat pour un ami » dans le front office. Elle contient probablement des styles pour :
    - Les éléments du formulaire de partage de bons d'achat (champs de saisie, boutons).
    - La liste « Mes bons d'achat » sur la page du compte client.
    - Les blocs promotionnels dans les colonnes gauche/droite.
    - La mise en page de base et la typographie pour assurer la lisibilité.
  - **Sélecteurs de classe CSS clés que les développeurs peuvent surcharger :** Les développeurs doivent inspecter le HTML rendu pour identifier les noms de classes spécifiques (par exemple, `.friendvoucher-form`, `.voucher-list`, `.friendvoucher-block`) à cibler pour l'intégration et la personnalisation du thème.

### 4.6 Structure des templates Smarty (`views/templates/`)

#### Templates de hook (`views/templates/hook/`)

Le module ne liste pas explicitement les templates dans un sous-répertoire `hook/`, mais les templates listés ci-dessous sont généralement rendus via des hooks.

- **`views/templates/front/footer.tpl`**

  - **Hook :** `displayFooter`
  - **Sorties :** Un lien ou un bloc lié à « Bon d'achat pour un ami » dans le pied de page de la boutique.
- **`views/templates/front/leftcolumn.tpl`**

  - **Hook :** `displayLeftColumn`
  - **Sorties :** Un bloc promotionnel ou un lien pour « Bon d'achat pour un ami » dans la barre latérale gauche de la boutique.
- **`views/templates/front/rightcolumn.tpl`**

  - **Hook :** `displayRightColumn`
  - **Sorties :** Un bloc promotionnel ou un lien pour « Bon d'achat pour un ami » dans la barre latérale droite de la boutique.

#### Templates d'administration (`views/templates/admin/`)

Ce module ne semble pas avoir de templates d'administration personnalisés. La configuration est probablement rendue directement par la méthode `getContent()` à l'aide des formulaires d'aide de PrestaShop.

#### Templates Front-office (`views/templates/front/`)

Ces templates sont rendus par les contrôleurs frontaux du module.

- **`views/templates/front/my-account.tpl`**

  - **Hook :** `displayCustomerAccount` (ou `displayMyAccountBlock`)
  - **Sorties :** Un lien ou une icône sur la page principale « Mon compte » du client, le dirigeant vers le contrôleur `myvoucher.php`.
- **`views/templates/front/my-voucher.tpl`**

  - **Contrôleur :** `FriendvoucherMyvoucherModuleFrontController`
  - **Sorties :** La page dédiée affichant une liste des bons d'achat que le client a envoyés, leur statut, et potentiellement un formulaire pour en envoyer de nouveaux.

### 4.7 Schéma de base de données et carte des hooks

#### Tables de base de données

Ce module ne semble pas créer de tables SQL personnalisées. Il stocke probablement sa configuration dans `ps_configuration` et utilise les tables principales `ps_cart_rule` et `ps_cart_rule_lang` de PrestaShop pour les bons d'achat générés.

#### Tableau des hooks enregistrés

Le module s'enregistre à divers hooks pour afficher son contenu et ses fonctionnalités.

| Nom du hook | Moment d'exécution | Objectif technique |
| --- | --- | --- |
| `displaymyAccountBlock` | Rendu dans le bloc du compte client (en-tête/colonne) après la connexion. | Affiche un lien rapide vers la page des bons d'achat pour les utilisateurs connectés. |
| `displayrightColumn` | Rend le contenu dans la barre latérale droite. | Affiche un bloc/lien promotionnel pour la fonctionnalité de bon d'achat. |
| `displayLeftColumn` | Rend le contenu dans la barre latérale gauche. | Affiche un bloc/lien promotionnel pour la fonctionnalité de bon d'achat. |
| `displayFooter` | Rend le contenu dans le pied de page de la boutique. | Affiche un lien vers la page des bons d'achat dans le pied de page. |
| `displaycustomerAccount` | Rend le contenu sur la page principale « Mon compte » du client. | Affiche un lien/icône dédié pour la fonctionnalité de bon d'achat sur la page du compte. |
| `actionValidateOrder` | Exécuté après la validation réussie d'une commande. | (Potentiel) Pourrait être utilisé pour déclencher des actions liées aux récompenses des parrains ou au suivi des parrainages réussis, bien que non explicitement confirmé par l'inventaire des fichiers. |

## 5. Support officiel et mises à jour

Pour le support officiel, les mises à jour du module et toute assistance supplémentaire, veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu/). Vous pouvez accéder à vos modules achetés, télécharger les dernières versions et soumettre des tickets de support directement depuis votre compte.
