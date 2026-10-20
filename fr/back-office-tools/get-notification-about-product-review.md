---
title: "Recevoir une notification sur les avis produits - Manuel du Marchand et Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop 'Recevoir une notification sur les avis produits' par MyPresta.eu."
sidebar:
  label: "Recevoir une notification sur les avis produits"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Get notification about product review sur MyPresta.eu](https://mypresta.eu/modules/administration-tools/get-notification-about-product-review.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/back-office-tools/get-notification-about-product-review/)
>
> ---


# Recevoir une notification sur les avis produits

## 1. Exigences et compatibilité

-   **Versions PrestaShop prises en charge** : PrestaShop 1.7.x
-   **Compatibilité PHP** : PHP 7.1 - 8.5
-   **Exigences d'hébergement** : Extensions PHP standard (cURL, JSON, OpenSSL).
-   **Prérequis** : Ce module nécessite que notre module gratuit d'avis produits soit installé et actif. Il étend les fonctionnalités de ce module.

## 2. Guide de configuration complet (Chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)
Après l'installation, cliquer sur "Configurer" vous mènera à l'écran de configuration principal et unique de ce module. Cet écran vous permet de définir l'adresse e-mail qui recevra les notifications.

#### **Adresse e-mail pour envoyer les notifications**
-   **Ce que fait ce paramètre :** C'est le paramètre le plus crucial. Il détermine l'adresse e-mail où toutes les notifications liées aux avis seront envoyées.
-   **Effet de la modification de ce paramètre :**
    -   *Lorsqu'une adresse e-mail valide est saisie :* Toutes les alertes (nouvel avis, commentaire signalé, vote utile) seront envoyées à cette adresse e-mail spécifique.
    -   *Lorsqu'il est laissé vide ou qu'une adresse e-mail invalide est saisie :* Vous ne recevrez aucune notification, désactivant ainsi la fonction principale du module.
-   **Valeur recommandée :** Votre adresse e-mail professionnelle principale, ou une adresse e-mail régulièrement surveillée par votre service client ou votre équipe marketing.
-   **Scénario / exemple de marchand :** Si votre équipe de service client gère toutes les interactions avec les clients, vous pourriez saisir `serviceclient@votreboutique.com` ici. Si vous, en tant que propriétaire, souhaitez être personnellement informé, utilisez votre adresse e-mail directe.

#### **Tableau de référence rapide de la configuration**

| Écran / Vue | Paramètre / Option | Valeur par défaut / Recommandée | Objectif et impact |
| :------------ | :--------------- | :-------------------- | :--------------- |
| Configuration du module | Adresse e-mail pour envoyer les notifications | Votre adresse e-mail professionnelle principale | Spécifie le destinataire de l'e-mail pour toutes les alertes liées aux avis (nouvel avis, commentaire signalé, vote utile). |

## 3. Dépannage pour les marchands et questions fréquemment posées (FAQ)

**Q : Je ne reçois aucune notification par e-mail. Que dois-je faire ?**
R :
1.  **Vérifiez l'adresse e-mail :** Allez dans **Modules > Gestionnaire de modules > Configurer** pour "Recevoir une notification sur les avis produits" et assurez-vous que l'adresse e-mail saisie est correcte et sans fautes de frappe.
2.  **Vérifiez votre dossier de spam :** Les notifications peuvent parfois être filtrées dans votre dossier de spam ou de courrier indésirable. Ajoutez l'adresse e-mail de l'expéditeur (généralement l'e-mail par défaut de votre boutique) à votre liste d'expéditeurs sûrs.
3.  **Vérifiez les paramètres d'e-mail de PrestaShop :** Assurez-vous que les paramètres d'e-mail de votre boutique PrestaShop sont correctement configurés et envoient des e-mails en général. Vous pouvez tester cela en créant un nouveau compte client ou en passant une commande test. Allez dans **Paramètres avancés > E-mail** dans votre back office.
4.  **Contactez votre hébergeur :** Si les e-mails de PrestaShop ne fonctionnent pas du tout, il peut y avoir un problème avec la fonction de messagerie de votre serveur. Votre hébergeur peut vous aider à diagnostiquer cela.
5.  **Assurez-vous que le module prérequis est installé :** Ce module étend notre module gratuit d'avis produits. Assurez-vous que ce module est installé et fonctionne correctement.

**Q : Puis-je envoyer des notifications à plusieurs adresses e-mail ?**
R : La conception actuelle du module ne permet de configurer qu'une seule adresse e-mail. Si vous devez envoyer à plusieurs destinataires, vous pouvez configurer une règle de transfert d'e-mails dans votre client de messagerie ou votre serveur (par exemple, transférer les e-mails de l'adresse configurée vers un alias de groupe).

**Q : Ce module fonctionne-t-il avec n'importe quel système d'avis produits ?**
R : Non, ce module est spécifiquement conçu pour fonctionner comme une extension du **module gratuit d'avis produits de MyPresta.eu**. Il ne fournira pas de notifications pour d'autres modules d'avis tiers.

**Q : J'ai mis à jour mon thème PrestaShop, et maintenant les notifications ne fonctionnent plus.**
R : Ce module n'a pas de composants front-office, donc un changement de thème ne devrait pas affecter directement sa fonctionnalité de notification. Vérifiez à nouveau la configuration des e-mails dans le module et vos paramètres d'e-mail PrestaShop comme décrit ci-dessus. Si le problème persiste, il est probable qu'il ne soit pas lié au thème et indique un problème de serveur ou de messagerie PrestaShop.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

### 4.1 Vue d'ensemble de l'architecture
Le module "Recevoir une notification sur les avis produits" (`reviewsalerts`) est un module PrestaShop léger conçu pour étendre les fonctionnalités du module `productcomments` (ou d'un module d'avis similaire, spécifiquement le module gratuit d'avis produits de MyPresta.eu). Il fonctionne principalement en se connectant aux actions pertinentes déclenchées par le système d'avis et en envoyant des notifications par e-mail basées sur ces événements. Il suit un modèle simple basé sur les événements, tirant parti du système de hooks de PrestaShop sans introduire de structures MVC complexes ou de tables de base de données personnalisées.

### 4.2 Contrôleurs (`controllers/`)
Ce module ne contient aucun contrôleur front-office ou back-office personnalisé. Toute la logique est encapsulée dans le fichier principal du module et exécutée via des hooks.

### 4.3 Classes et modèles principaux (`classes/`)
Ce module ne définit aucune classe personnalisée ou instance `ObjectModel`. Sa fonctionnalité est contenue dans la classe principale `reviewsalerts`.

### 4.4 Actifs JavaScript (`views/js/`)
Ce module n'inclut aucun fichier JavaScript.

### 4.5 Feuilles de style CSS (`views/css/`)
Ce module n'inclut aucun fichier CSS.

### 4.6 Structure des modèles Smarty (`views/templates/`)
Ce module n'inclut aucun fichier de modèle Smarty personnalisé pour l'affichage front-office ou la configuration back-office. Le formulaire de configuration est généré dynamiquement par `getContent()` dans le fichier principal du module.

### 4.7 Schéma de base de données et carte des hooks

-   **Tables de base de données** : Ce module ne crée aucune table de base de données personnalisée. Il stocke son unique paramètre de configuration (l'adresse e-mail de notification) dans la table standard `ps_configuration`.
    *   **Clé de configuration** : `REVIEWSALERTS_EMAIL`

-   **Table des hooks enregistrés** :

| Nom du hook | Moment d'exécution | Objectif technique |
| :-------- | :--------------- | :---------------- |
| `actionObjectProductCommentAddAfter` | Après qu'un nouvel avis produit (commentaire) a été ajouté avec succès à la base de données. | Déclenche une notification par e-mail à l'adresse configurée, informant le marchand du nouvel avis. |
| `actionObjectProductCommentReportAfter` | Après qu'un avis produit a été signalé avec succès par un client. | Déclenche une notification par e-mail à l'adresse configurée, informant le marchand qu'un avis a été signalé. |
| `actionObjectProductCommentUsefulAfter` | Après qu'un client marque un avis produit comme "utile". | Déclenche une notification par e-mail à l'adresse configurée, informant le marchand qu'un vote sur l'utilité d'un avis a été effectué. |

La méthode `install()` du module enregistre ces hooks, et les méthodes correspondantes `hookActionObjectProductCommentAddAfter()`, `hookActionObjectProductCommentReportAfter()` et `hookActionObjectProductCommentUsefulAfter()` gèrent la logique d'envoi des e-mails.

L'envoi des e-mails est généralement géré par la fonction `Mail::Send()` de PrestaShop, utilisant les modèles d'e-mails et les paramètres configurés de la boutique. Le module construirait probablement le contenu de l'e-mail dynamiquement en fonction du contexte de l'action déclenchée (par exemple, contenu de l'avis, nom du produit, détails du signaleur).

## 5. Support officiel et mises à jour
Pour les dernières mises à jour, corrections de bugs et support officiel du module "Recevoir une notification sur les avis produits", veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu/). Notre équipe de support est disponible pour vous aider avec tout problème ou question que vous pourriez avoir concernant la fonctionnalité et la configuration du module.
"""
