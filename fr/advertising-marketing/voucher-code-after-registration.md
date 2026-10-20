---
title: "Code de bon d'achat après inscription - Manuel du marchand et guide de configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop 'Code de bon d'achat après inscription' par MyPresta.eu."
sidebar:
  label: "Code de bon d'achat après inscription - Manuel du marchand et guide de configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Voucher code after registration sur MyPresta.eu](https://mypresta.eu/modules/advertising-and-marketing/voucher-code-after-registration.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/advertising-marketing/voucher-code-after-registration/)
>
> ---


# Code de bon d'achat après inscription

## 1. Exigences et compatibilité

-   **Versions PrestaShop prises en charge** : PrestaShop 1.4.x, 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
-   **Compatibilité PHP** : PHP 5.6 - 8.5
-   **Exigences d'hébergement** : Les extensions PHP standard (cURL, JSON, OpenSSL) sont généralement suffisantes et sont généralement préinstallées sur la plupart des environnements d'hébergement web.

## 2. Guide de configuration complet (chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

Après l'installation, cliquez sur le bouton « Configurer » à côté du module « Code de bon d'achat après inscription ». Cela vous mènera à l'écran de configuration principal où vous pourrez définir le fonctionnement de vos bons d'achat pour nouveaux clients.

La page de configuration vous présentera des options pour définir les caractéristiques du bon d'achat que les nouveaux clients recevront. Ces paramètres correspondent directement aux fonctionnalités standard de « Règle panier » (bon d'achat) de PrestaShop.

Voici les paramètres typiques que vous rencontrerez :

-   **Description :**

    -   **Ce que fait ce paramètre :** C'est le nom interne de la règle panier (bon d'achat) qui sera créée. Il vous aide à identifier le bon d'achat dans votre Back Office.
    -   **Effet de la modification de ce paramètre :** Ce nom est uniquement pour votre référence et n'est pas visible par les clients.
    -   **Valeur recommandée :** Quelque chose de descriptif comme « Bon d'achat d'inscription nouveau client » ou « Remise de bienvenue ».
    -   **Scénario / exemple marchand :** Si vous gérez plusieurs promotions, une description claire comme « Bon de bienvenue - 10 % de réduction » vous aide à suivre ses performances.
-   **Code :**

    -   **Ce que fait ce paramètre :** Il définit le préfixe des codes de bon d'achat uniques générés. Le module ajoutera une chaîne unique à ce préfixe pour chaque nouveau client.
    -   **Effet de la modification de ce paramètre :** Si vous le définissez sur « BIENVENUE », les clients pourraient recevoir des codes comme « BIENVENUE12345 » ou « BIENVENUEABCDE ». Cela rend les codes facilement identifiables.
    -   **Valeur recommandée :** Un préfixe court et mémorable comme « BIENVENUE », « NOUVEAUCLIENT » ou « MABOUTIQUE ». Laissez vide pour un code entièrement aléatoire.
    -   **Scénario / exemple marchand :** L'utilisation de « BIENVENUE » indique clairement au client qu'il s'agit d'une offre de bienvenue.
-   **Mettre en avant :**

    -   **Ce que fait ce paramètre :** Si activé, ce bon d'achat sera affiché dans le récapitulatif du panier (le cas échéant) et sur la page produit (si configuré pour le faire par les paramètres de base de PrestaShop).
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsqu'activé :* L'existence du bon d'achat pourrait être subtilement suggérée aux endroits où les règles panier sont généralement promues.
        -   *Lorsqu'désactivé :* Le bon d'achat n'est connu du client que par e-mail et via son compte.
    -   **Valeur recommandée :** OUI (Activé), car cela peut subtilement rappeler aux clients les réductions disponibles.
    -   **Scénario / exemple marchand :** L'activation de cette option peut encourager les clients à utiliser le bon d'achat qu'ils ont reçu, même s'ils l'avaient oublié.
-   **Utilisation partielle :**

    -   **Ce que fait ce paramètre :** Détermine si le bon d'achat peut être utilisé plusieurs fois si sa valeur est supérieure au total de la commande.
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsqu'activé :* Si un client a un bon d'achat de 50 € et achète un article à 30 €, il lui restera un solde de 20 € sur le bon d'achat pour un futur achat.
        -   *Lorsqu'désactivé :* La valeur totale du bon d'achat doit être utilisée en une seule transaction, ou le solde restant est perdu.
    -   **Valeur recommandée :** NON (Désactivé) pour la plupart des bons de bienvenue, afin d'encourager un achat complet.
    -   **Scénario / exemple marchand :** Pour un bon d'achat « 10 % de réduction », ce paramètre est moins pertinent, mais pour un bon d'achat « montant fixe » (par exemple, « 10 € de réduction »), la désactivation de l'utilisation partielle encourage une première commande plus importante.
-   **Priorité :**

    -   **Ce que fait ce paramètre :** Si un client a plusieurs bons d'achat, ce nombre détermine l'ordre dans lequel ils sont appliqués. Les nombres inférieurs signifient une priorité plus élevée.
    -   **Effet de la modification de ce paramètre :** Un bon d'achat avec la priorité 1 sera appliqué avant un bon d'achat avec la priorité 2. C'est important si les bons d'achat ne peuvent pas être combinés.
    -   **Valeur recommandée :** 1 (Priorité la plus élevée) pour les bons de bienvenue, garantissant qu'ils sont appliqués en premier.
    -   **Scénario / exemple marchand :** Si vous avez un bon d'achat général « livraison gratuite » (priorité 5) et un bon d'achat « réduction de bienvenue » (priorité 1), la réduction de bienvenue sera calculée en premier.
-   **Statut :**

    -   **Ce que fait ce paramètre :** Contrôle si le module est actif et génère des bons d'achat.
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsqu'activé :* Les nouveaux clients recevront des bons d'achat lors de leur inscription.
        -   *Lorsqu'désactivé :* Le module cessera de générer et d'envoyer des bons d'achat.
    -   **Valeur recommandée :** OUI (Activé) pour activer la fonctionnalité principale du module.
    -   **Scénario / exemple marchand :** Vous pourriez le désactiver temporairement lors d'un événement de vente spécifique où vous ne souhaitez pas offrir de réductions d'inscription supplémentaires.
-   **Type de réduction :**

    -   **Ce que fait ce paramètre :** Définit si la réduction est un pourcentage, un montant fixe ou la livraison gratuite.
    -   **Effet de la modification de ce paramètre :**
        -   *Pourcentage :* par exemple, « 10 % » de réduction sur la commande.
        -   *Montant :* par exemple, « 10 € » de réduction sur la commande.
        -   *Livraison gratuite :* Exonère les frais de port.
    -   **Valeur recommandée :** Pourcentage ou Montant, selon votre stratégie marketing.
    -   **Scénario / exemple marchand :** Offrir « 10 % de réduction » est courant pour les réductions de bienvenue. « 5 € de réduction » pourrait être mieux pour les articles à prix plus bas.
-   **Valeur :**

    -   **Ce que fait ce paramètre :** La valeur de réduction réelle, correspondant au « Type de réduction » sélectionné.
    -   **Effet de la modification de ce paramètre :** Si le « Type de réduction » est Pourcentage et la « Valeur » est 10, les clients obtiennent 10 % de réduction. Si le « Type de réduction » est Montant et la « Valeur » est 10, ils obtiennent 10 € de réduction.
    -   **Valeur recommandée :** Une valeur attrayante mais également rentable, par exemple, « 10 » pour 10 % ou « 5 € ».
    -   **Scénario / exemple marchand :** Une réduction de 10 % est un bon point de départ pour attirer de nouveaux clients.
-   **Montant minimum :**

    -   **Ce que fait ce paramètre :** Le total minimum de commande (avant frais de port) requis pour que le bon d'achat soit valide.
    -   **Effet de la modification de ce paramètre :** Si défini sur 50 €, le client doit passer une commande de 50 € ou plus pour utiliser le bon d'achat.
    -   **Valeur recommandée :** Définissez un minimum raisonnable pour encourager des premières commandes plus importantes, ou 0 si aucun minimum n'est requis.
    -   **Scénario / exemple marchand :** Définir un minimum de 50 € pour un bon d'achat de 10 % de réduction garantit que vous réalisez toujours un bon profit sur la première commande.
-   **Cumulable :**

    -   **Ce que fait ce paramètre :** Détermine si ce bon d'achat peut être combiné avec d'autres bons d'achat.
    -   **Effet de la modification de ce paramètre :**
        -   *Lorsqu'activé :* Les clients peuvent utiliser ce bon de bienvenue avec d'autres bons d'achat actifs (par exemple, un bon d'achat de livraison gratuite).
        -   *Lorsqu'désactivé :* Ce bon d'achat ne peut pas être utilisé si un autre bon d'achat est déjà appliqué au panier.
    -   **Valeur recommandée :** NON (Désactivé) pour la plupart des bons de bienvenue afin d'éviter des réductions excessives.
    -   **Scénario / exemple marchand :** Vous souhaitez généralement limiter le cumul des réductions pour protéger vos marges, il est donc souvent préférable de désactiver l'utilisation cumulée.
-   **Valide du / Valide au :**

    -   **Ce que fait ce paramètre :** Définit la plage de dates pendant laquelle le bon d'achat est actif.
    -   **Effet de la modification de ce paramètre :** Le bon d'achat ne sera valide qu'entre ces dates.
    -   **Valeur recommandée :** Laissez « Valide du » comme date actuelle. Pour « Valide au », envisagez de définir une date d'expiration (par exemple, 30 jours après l'inscription) pour créer une urgence, ou laissez-la loin dans le futur si vous souhaitez qu'elle soit permanente.
    -   **Scénario / exemple marchand :** Définir « Valide au » 30 jours dans le futur encourage les clients à utiliser le bon d'achat rapidement.
-   **Quantité :**

    -   **Ce que fait ce paramètre :** Il s'agit du nombre total de bons d'achat *uniques* qui peuvent être générés par le module.
    -   **Effet de la modification de ce paramètre :** Si défini sur 100, seuls les 100 premiers nouveaux inscrits recevront un bon d'achat.
    -   **Valeur recommandée :** Un nombre très élevé (par exemple, 999999) ou laissez vide si vous souhaitez qu'un nombre illimité de bons d'achat soit généré pour les nouveaux inscrits.
    -   **Scénario / exemple marchand :** Pour une offre de bienvenue continue, vous souhaitez généralement une quantité illimitée. Si vous menez une campagne à durée limitée pour les X premiers inscrits, vous définiriez un nombre spécifique.
-   **Quantité par client :**

    -   **Ce que fait ce paramètre :** Définit le nombre de fois qu'un *seul client* peut recevoir ce bon d'achat spécifique.
    -   **Effet de la modification de ce paramètre :** Définissez sur 1 pour vous assurer que chaque client ne reçoit qu'un seul bon de bienvenue lors de son inscription initiale.
    -   **Valeur recommandée :** 1.
    -   **Scénario / exemple marchand :** Vous voulez que chaque nouveau client reçoive une réduction de bienvenue, pas plusieurs s'il s'inscrit à nouveau avec une adresse e-mail différente (bien que le cœur de PrestaShop empêche généralement cela).

### 2.2 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Par défaut / Recommandé | Objectif et impact |
| --- | --- | --- | --- |
| Configuration du module | **Description** | « Bon d'achat nouveau client » | Nom interne du bon d'achat dans le BO. |
| Configuration du module | **Code** | Vide (aléatoire) / « BIENVENUE » | Préfixe des codes de bon d'achat générés. |
| Configuration du module | **Mettre en avant** | OUI | Afficher le bon d'achat dans le récapitulatif du panier/page produit. |
| Configuration du module | **Utilisation partielle** | NON | Autoriser plusieurs utilisations si la valeur > total de la commande. |
| Configuration du module | **Priorité** | 1 | Ordre d'application si plusieurs bons d'achat. |
| Configuration du module | **Statut** | OUI | Activer/désactiver la génération de bons d'achat du module. |
| Configuration du module | **Type de réduction** | Pourcentage | Type de réduction (%, montant, livraison gratuite). |
| Configuration du module | **Valeur** | 10 | La valeur de réduction réelle (par exemple, 10 pour 10 %). |
| Configuration du module | **Montant minimum** | 0 | Total minimum de commande pour la validité du bon d'achat. |
| Configuration du module | **Cumulable** | NON | Autoriser la combinaison avec d'autres bons d'achat. |
| Configuration du module | **Valide du** | Date actuelle | Date de début de validité du bon d'achat. |
| Configuration du module | **Valide au** | Loin dans le futur / 30 jours | Date de fin de validité du bon d'achat. |
| Configuration du module | **Quantité** | 999999 | Nombre total de bons d'achat uniques à générer. |
| Configuration du module | **Quantité par client** | 1 | Combien de fois un seul client peut l'obtenir. |

## 3. Dépannage marchand et questions fréquemment posées (FAQ)

**Q : Mes clients ne reçoivent pas l'e-mail du bon d'achat. Que dois-je vérifier ?**
R :

1.  **Statut du module :** Assurez-vous que le paramètre « Statut » dans la configuration du module est défini sur OUI (Activé).
2.  **Configuration des e-mails :** Vérifiez les paramètres de votre e-mail PrestaShop sous **Paramètres avancés > E-mail**. Envoyez un e-mail de test pour vous assurer que le système d'e-mail de votre boutique fonctionne correctement.
3.  **Dossiers de spam :** Conseillez aux clients de vérifier leurs dossiers de spam ou de courrier indésirable.
4.  **Journaux du module :** Si disponibles, vérifiez les journaux d'erreurs liés au module ou à l'envoi d'e-mails.
5.  **Cache Smarty :** Parfois, vider le cache Smarty sous **Paramètres avancés > Performances** peut résoudre les problèmes d'affichage ou de fonctionnalité.

**Q : Le code du bon d'achat est généré, mais il ne s'applique pas correctement à la caisse.**
R :

1.  **Paramètres du bon d'achat :** Vérifiez à nouveau tous les paramètres du bon d'achat dans la configuration du module (par exemple, « Montant minimum », « Valide du/au », « Cumulable »). Assurez-vous que le panier du client remplit toutes les conditions.
2.  **Saisie du code :** Confirmez que le client saisit correctement le code dans le panier/la caisse.
3.  **Restrictions de produits :** Assurez-vous qu'il n'y a pas de restrictions de produits ou de catégories cachées appliquées à la règle panier générée (bien que ce module crée généralement des règles simples et générales).

**Q : Puis-je personnaliser le modèle d'e-mail qui envoie le bon d'achat ?**
R : Oui, le module utilise le système de modèles d'e-mail standard de PrestaShop. Vous pouvez trouver et personnaliser les fichiers de modèle d'e-mail pertinents (généralement dans `themes/votre_thème/mail/fr/` ou `mails/fr/` pour les versions plus anciennes) qui sont déclenchés lorsqu'une nouvelle règle panier est créée et envoyée. Recherchez les modèles liés à `voucher` ou `cart_rule`.

**Q : Que se passe-t-il si un client s'inscrit plusieurs fois avec des adresses e-mail différentes ?**
R : Le module générera un nouveau bon d'achat unique pour chaque nouvelle inscription. La fonctionnalité principale de PrestaShop empêche généralement les inscriptions d'e-mails en double, mais si un client utilise différentes adresses e-mail, il recevra un nouveau bon d'achat à chaque fois. Le paramètre « Quantité par client » s'applique à un seul ID client, pas nécessairement à des adresses e-mail uniques s'ils contournent les vérifications de base.

**Q : Le module est installé, mais je ne vois aucun nouvel élément de menu dans le Back Office.**
R : Ce module s'intègre directement dans la section existante « Modules > Gestionnaire de modules » et n'ajoute pas de nouveaux éléments de menu de niveau supérieur. Sa configuration est accessible en cliquant sur « Configurer » à côté de son nom dans la liste des modules.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

### 4.1 Aperçu de l'architecture

Le module « Code de bon d'achat après inscription » (`registervoucher`) est un module PrestaShop standard principalement conçu pour étendre le hook `actionCustomerAccountAdd`. Il exploite la fonctionnalité de base de PrestaShop `CartRule` (bon d'achat) pour créer et attribuer automatiquement un code de réduction unique aux nouveaux comptes clients. La configuration du module est gérée via la méthode `getContent()` dans le fichier principal du module, stockant les paramètres dans `ps_configuration`. Il inclut une interaction minimale avec le front-office, s'appuyant principalement sur le système d'e-mail natif de PrestaShop et l'affichage du compte client pour la livraison des bons d'achat.

### 4.2 Contrôleurs (`controllers/`)

Ce module ne contient aucun contrôleur d'administration Front-Office ou Back-Office personnalisé. Toute la logique est encapsulée dans le fichier principal du module et ses hooks enregistrés.

### 4.3 Classes et modèles de base (`classes/`)

Ce module ne définit aucune classe personnalisée et n'étend pas `ObjectModel`. Il interagit directement avec la classe `CartRule` de base de PrestaShop pour créer et gérer les bons d'achat.

### 4.4 Actifs JavaScript (`views/js/`)

-   `registervoucher/lib/voucherengine/script.js`
    -   **Portée :** Potentiellement Back-office, ou un script générique inclus pour la compatibilité.
    -   **Description :** Compte tenu de la fonction principale du module (génération de bons d'achat côté backend), ce script est probablement un utilitaire ou un script de compatibilité. Il pourrait gérer les améliorations de l'interface utilisateur sur la page de configuration, la validation de formulaire, ou fournir des correctifs de compatibilité pour les anciennes versions de PrestaShop, en particulier concernant les éléments de formulaire dynamiques ou les interactions AJAX au sein de la méthode `getContent()`. Sans inspection plus approfondie, son objectif exact est spéculatif mais généralement lié à l'amélioration de l'interface de configuration du module ou à l'assurance de la compatibilité inter-versions pour le panneau d'administration.

### 4.5 Feuilles de style CSS (`views/css/`)

-   `registervoucher/css.css`
    -   **Portée :** Probablement le style du formulaire d'administration du Back-office.
    -   **Description :** Cette feuille de style contient probablement des styles personnalisés pour la page de configuration du module dans le Back Office de PrestaShop. Elle pourrait ajuster la mise en page, l'espacement, les couleurs ou l'apparence d'éléments spécifiques pour garantir que le formulaire de configuration est visuellement cohérent ou pour appliquer une image de marque personnalisée.
    -   **Sélecteurs de classe CSS clés que les développeurs peuvent remplacer :** `.registervoucher-config`, `.form-group`, `.control-label`, `.help-block` (spécifiques au HTML généré par le module).
-   `registervoucher/lib/voucherengine/ps16.css`
    -   **Portée :** Style du formulaire d'administration du Back-office, spécifiquement pour la compatibilité PrestaShop 1.6.
    -   **Description :** Cette feuille de style est presque certainement incluse pour garantir que la page de configuration du module s'affiche correctement et de manière cohérente avec le thème du Back Office de PrestaShop 1.6. Elle aborde les différences de style entre PS 1.6 et les versions plus récentes, fournissant les remplacements nécessaires ou des styles spécifiques pour des éléments tels que les boutons, les champs de formulaire et les conteneurs de mise en page afin de maintenir une apparence et une convivialité appropriées.
    -   **Sélecteurs de classe CSS clés que les développeurs peuvent remplacer :** Spécifiques au thème d'administration de PS 1.6, par exemple, `.panel`, `.form-horizontal`, `.btn`.

### 4.6 Structure du modèle Smarty (`views/templates/`)

Le dossier du module n'indique aucun fichier `.tpl` personnalisé. Cela suggère que le formulaire de configuration du module est rendu directement dans la méthode `getContent()` à l'aide des classes d'aide de PrestaShop (par exemple, `HelperForm`), et que tout affichage front-office (comme le bon d'achat dans le compte client) est géré en remplaçant les modèles PrestaShop de base ou en injectant du contenu directement via des hooks sans modèles de module dédiés. Le contenu de l'e-mail est géré via les modèles de courrier natifs de PrestaShop.

### 4.7 Schéma de base de données et carte des hooks

-   **Tables de base de données** :
    -   Le module ne crée aucune table de base de données personnalisée.
    -   Les paramètres de configuration sont stockés dans la table `ps_configuration` (par exemple, `PS_REGISTERVOUCHER_DESCRIPTION`, `PS_REGISTERVOUCHER_CODE`, etc.).
    -   Les bons d'achat générés sont stockés dans les tables `ps_cart_rule` et `ps_cart_rule_lang` de base de PrestaShop.
-   **Table des hooks enregistrés** :

| Nom du hook | Moment d'exécution | Objectif technique |
| --- | --- | --- |
| `actionCustomerAccountAdd` | Exécuté immédiatement après la création réussie d'un nouveau compte client. | C'est le hook principal. Le module écoute cet événement pour déclencher le processus de génération et d'attribution du bon d'achat pour le client nouvellement inscrit. |
| `displayHeader` | Exécuté dans la section `<head>` de chaque page du front-office. | Souvent utilisé pour ajouter du CSS/JS, mais dans ce module, il n'est pas explicitement utilisé pour l'affichage front-office. Pourrait être pour la configuration interne du module ou la compatibilité. |
| `displayRightColumn` | Exécuté dans la colonne de droite du front-office. | Non directement utilisé pour la fonctionnalité principale du module d'affichage des bons d'achat. |
| `displayLeftColumn` | Exécuté dans la colonne de gauche du front-office. | Non directement utilisé pour la fonctionnalité principale du module d'affichage des bons d'achat. |
| `displayFooter` | Exécuté dans la section du pied de page de chaque page du front-office. | Non directement utilisé pour la fonctionnalité principale du module d'affichage des bons d'achat. |
| `displayProductButtons` | Exécuté sur la page produit, près du bouton d'ajout au panier. | Non directement utilisé pour la fonctionnalité principale du module d'affichage des bons d'achat. |
| `displayCustomerAccount` | Exécuté sur la page « Mon compte » du client. | Ce hook est crucial pour afficher le code du bon d'achat généré directement dans l'espace client, le rendant facilement accessible. |

## 5. Support officiel et mises à jour

Pour les dernières mises à jour, corrections de bugs et support professionnel pour le module « Code de bon d'achat après inscription », veuillez vous référer à votre compte client sur MyPresta.eu. Notre équipe de support est disponible pour vous aider avec tout problème technique ou question concernant la fonctionnalité du module.
