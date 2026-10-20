---
title: "Code de bon d'achat Facebook like - Manuel du Marchand & Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop 'Code de bon d'achat Facebook like' par MyPresta.eu."
sidebar:
  label: "Code de bon d'achat Facebook like"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Facebook like voucher code sur MyPresta.eu](https://mypresta.eu/modules/social-networks/facebook-like-voucher-code.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/social-networks/facebook-like-voucher-code/)
>
> ---


# Code de bon d'achat Facebook like

## 1. Exigences et compatibilité
- **Versions PrestaShop prises en charge** : PrestaShop 1.4.x, 1.5.x, 1.6.x, 1.7.x
- **Compatibilité PHP** : PHP 5.6 - 8.5
- **Exigences d'hébergement** : Les extensions PHP standard (cURL, JSON, OpenSSL) sont généralement requises pour PrestaShop lui-même et tout module interagissant avec des API externes comme Facebook.

## 2. Présentation complète de la configuration (Chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)
Ceci est l'écran de configuration principal du module "Code de bon d'achat Facebook like", accessible après l'installation en cliquant sur le bouton "Configurer". Ici, vous définirez comment le bouton "J'aime" de Facebook apparaît et comment les codes de bon d'achat sont générés.

#### **URL de la page Facebook**
- **Ce que fait ce paramètre :** C'est le paramètre le plus crucial. Il indique au module quelle page Facebook vos clients doivent "Aimer" pour recevoir le bon d'achat.
- **Effet de la modification de ce paramètre :**
  - *Lorsqu'il est défini sur l'URL de votre page Facebook (par exemple, `https://www.facebook.com/MyPresta.eu`) :* Le bouton "J'aime" de votre boutique renverra directement à cette page Facebook spécifique et suivra les "J'aime" pour celle-ci.
  - *Lorsqu'il est laissé vide ou défini incorrectement :* Le bouton "J'aime" ne fonctionnera pas correctement, ou il pourrait renvoyer à une page inexistante, empêchant les clients de recevoir des bons d'achat.
- **Valeur recommandée :** Saisissez l'URL complète de votre page professionnelle Facebook officielle.
- **Scénario / exemple pour le marchand :** Si votre page Facebook est `https://www.facebook.com/maboutiquesupergeniale`, vous saisiriez cette URL exacte ici.

#### **Préfixe du code de bon d'achat**
- **Ce que fait ce paramètre :** Cela vous permet d'ajouter un préfixe personnalisé à tous les codes de bon d'achat générés par ce module. Cela vous aide à identifier facilement quels bons d'achat proviennent de votre promotion Facebook.
- **Effet de la modification de ce paramètre :**
  - *Lorsqu'il est défini sur "FB" :* Tous les codes de bon d'achat générés commenceront par "FB" (par exemple, FB123456).
  - *Lorsqu'il est laissé vide :* Les codes de bon d'achat seront générés sans préfixe spécifique, ce qui les rendra plus difficiles à distinguer des autres types de bons d'achat.
- **Valeur recommandée :** Un préfixe court et mémorable comme "FB", "LIKE" ou "SOCIAL".
- **Scénario / exemple pour le marchand :** L'utilisation de "FB" vous permet de filtrer rapidement vos codes de bon d'achat dans le Back Office de PrestaShop pour voir combien ont été générés via ce module.

#### **Valeur du code de bon d'achat**
- **Ce que fait ce paramètre :** Définit la valeur de la réduction du code de bon d'achat. Il peut s'agir d'un montant fixe ou d'un pourcentage.
- **Effet de la modification de ce paramètre :**
  - *Lorsqu'il est défini sur "10" et "Pourcentage" :* Les clients reçoivent une réduction de 10 %.
  - *Lorsqu'il est défini sur "5" et "Montant" :* Les clients reçoivent une réduction de 5 $ (ou votre devise par défaut).
- **Valeur recommandée :** Une valeur suffisamment attrayante pour encourager un achat mais également durable pour vos marges bénéficiaires (par exemple, 5, 10, 15).
- **Scénario / exemple pour le marchand :** Offrir "10" et "Pourcentage" pour une réduction de 10 % est une stratégie courante et efficace pour encourager les premiers acheteurs.

#### **Type de code de bon d'achat**
- **Ce que fait ce paramètre :** Détermine si le code de bon d'achat offre une réduction en pourcentage ou une réduction d'un montant fixe.
- **Effet de la modification de ce paramètre :**
  - *Lorsqu'il est défini sur "Pourcentage" :* La "Valeur du code de bon d'achat" sera interprétée comme un pourcentage (par exemple, 10 % de réduction).
  - *Lorsqu'il est défini sur "Montant" :* La "Valeur du code de bon d'achat" sera interprétée comme un montant monétaire fixe (par exemple, 10 $ de réduction).
- **Valeur recommandée :** "Pourcentage" est souvent plus attrayant car il s'adapte à la valeur de la commande, mais "Montant" peut être efficace pour les articles à bas prix ou les promotions spécifiques.
- **Scénario / exemple pour le marchand :** Si vous souhaitez offrir une réduction forfaitaire de 5 $ quelle que soit la taille de la commande, choisissez "Montant". Si vous souhaitez offrir une réduction qui augmente avec la valeur de la commande, choisissez "Pourcentage".

#### **Montant minimum du code de bon d'achat**
- **Ce que fait ce paramètre :** Définit un total de commande minimum (avant frais de port) que le client doit atteindre pour pouvoir utiliser le code de bon d'achat.
- **Effet de la modification de ce paramètre :**
  - *Lorsqu'il est défini sur "50" :* Le bon d'achat ne peut être utilisé que si le total du panier est de 50 $ ou plus.
  - *Lorsqu'il est laissé vide ou défini sur "0" :* Le bon d'achat peut être utilisé sur n'importe quel montant de commande.
- **Valeur recommandée :** Une valeur qui encourage les clients à ajouter plus d'articles à leur panier, augmentant ainsi la valeur moyenne des commandes (par exemple, 25, 50).
- **Scénario / exemple pour le marchand :** Si la valeur moyenne de votre commande est de 40 $, définir un montant minimum de 50 $ pour un bon d'achat de 10 % encourage les clients à ajouter un article supplémentaire pour bénéficier de la réduction.

#### **Jours d'expiration du code de bon d'achat**
- **Ce que fait ce paramètre :** Définit le nombre de jours pendant lesquels le code de bon d'achat généré sera valide à partir du moment où il est émis.
- **Effet de la modification de ce paramètre :**
  - *Lorsqu'il est défini sur "7" :* Le code de bon d'achat expirera 7 jours après que le client l'ait reçu.
  - *Lorsqu'il est laissé vide ou défini sur "0" :* Le code de bon d'achat n'aura pas de date d'expiration (ou une très longue date par défaut définie par PrestaShop).
- **Valeur recommandée :** Un délai raisonnable pour créer une urgence sans être trop restrictif (par exemple, 7, 14, 30 jours).
- **Scénario / exemple pour le marchand :** Le définir sur "7" jours encourage les clients à effectuer un achat plus tôt que plus tard, les empêchant d'oublier le bon d'achat.

#### **Description du code de bon d'achat**
- **Ce que fait ce paramètre :** Vous permet d'ajouter une description personnalisée au code de bon d'achat généré dans votre Back Office PrestaShop. Cela vous aide à suivre l'objectif du bon d'achat.
- **Effet de la modification de ce paramètre :**
  - *Lorsqu'il est défini sur "Promotion J'aime Facebook" :* Cette description sera visible lorsque vous consulterez les détails du bon d'achat dans votre Back Office PrestaShop, indiquant clairement l'origine du bon d'achat.
  - *Lorsqu'il est laissé vide :* Le bon d'achat n'aura pas de description spécifique, ce qui rendra plus difficile l'identification de sa source.
- **Valeur recommandée :** Une description claire et concise comme "Bon d'achat J'aime Facebook" ou "Promo Réseaux Sociaux".
- **Scénario / exemple pour le marchand :** L'utilisation de "Promotion J'aime Facebook" aide votre équipe de service client à comprendre le contexte du bon d'achat si un client a des questions à ce sujet.

#### **Afficher le bloc dans**
- **Ce que fait ce paramètre :** Détermine où le bloc du bouton "J'aime" de Facebook apparaîtra sur le front-office de votre boutique.
- **Effet de la modification de ce paramètre :**
  - *Lorsque "En-tête" est sélectionné :* Le bloc apparaît en haut de chaque page.
  - *Lorsque "Colonne de gauche" est sélectionné :* Le bloc apparaît dans la barre latérale gauche.
  - *Lorsque "Colonne de droite" est sélectionné :* Le bloc apparaît dans la barre latérale droite.
  - *Lorsque "Page produit" est sélectionné :* Le bloc apparaît sur les pages de produits individuelles.
  - *Lorsque "Pied de page" est sélectionné :* Le bloc apparaît en bas de chaque page.
- **Valeur recommandée :** "En-tête" ou "Page produit" pour une visibilité et un impact maximum, ou "Colonne de gauche/droite" si vous préférez un placement moins intrusif.
- **Scénario / exemple pour le marchand :** Le placer dans l'"En-tête" garantit que chaque visiteur le voit. Le placer sur la "Page produit" cible les clients qui sont déjà intéressés par un achat.

#### **Message de la fenêtre contextuelle du code de bon d'achat**
- **Ce que fait ce paramètre :** C'est le message que les clients verront dans la fenêtre contextuelle avec leur code de bon d'achat après avoir "Aimé" votre page Facebook.
- **Effet de la modification de ce paramètre :**
  - *Lorsqu'il est défini sur "Merci de nous avoir aimés ! Voici votre code de réduction : {voucher_code}" :* Le client verra ce message exact avec son code unique inséré.
  - *Lorsqu'il est laissé vide :* Le client pourrait ne voir que le code sans texte d'accompagnement, ce qui pourrait être déroutant.
- **Valeur recommandée :** Un message amical et clair qui remercie le client et indique explicitement que le code est pour une réduction. **Incluez toujours `{voucher_code}`** afin que le code réel soit affiché.
- **Scénario / exemple pour le marchand :** "Merci d'avoir rejoint notre communauté ! Voici une gâterie spéciale pour vous : {voucher_code}. Profitez de vos achats !"

#### **Titre de la fenêtre contextuelle du code de bon d'achat**
- **Ce que fait ce paramètre :** Définit le titre de la fenêtre contextuelle qui affiche le code de bon d'achat.
- **Effet de la modification de ce paramètre :**
  - *Lorsqu'il est défini sur "Votre réduction exclusive !" :* Ce titre apparaîtra en haut de la fenêtre contextuelle.
  - *Lorsqu'il est laissé vide :* La fenêtre contextuelle pourrait avoir un titre générique ou pas de titre, ce qui est moins professionnel.
- **Valeur recommandée :** Un titre accrocheur et clair qui renforce la récompense (par exemple, "Votre bon d'achat gratuit !", "Merci de nous avoir aimés !").
- **Scénario / exemple pour le marchand :** "Votre réduction exclusive !" indique immédiatement au client qu'il a reçu une récompense précieuse.

### 2.2 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Valeur par défaut / Recommandée | Objectif et impact
