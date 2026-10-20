---
title: "Page de confirmation de commande pour les commandes gratuites - Manuel du marchand et guide de configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop 'Page de confirmation de commande pour les commandes gratuites' par MyPresta.eu."
sidebar:
  label: "Page de confirmation de commande pour les commandes gratuites - Manuel du marchand et guide de configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Order confirmation page for free orders sur MyPresta.eu](https://mypresta.eu/modules/ordering-process/order-confirmation-page-for-free-orders.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/ordering-process/order-confirmation-page-for-free-orders/)
>
> ---


# Page de confirmation de commande pour les commandes gratuites

## 1. Exigences et compatibilité

- **Versions PrestaShop prises en charge** : PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilité PHP** : PHP 7.1 - 8.5
- **Exigences d'hébergement** : Les extensions PHP standard (cURL, JSON, OpenSSL) sont généralement requises pour PrestaShop lui-même et sont suffisantes pour ce module.

## 2. Guide de configuration complet (chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer > Page de confirmation de commande pour les commandes gratuites)

Ceci est l'écran de configuration principal et unique du module. Il est simple et vous permet d'activer ou de désactiver la fonctionnalité principale du module.

![Capture d'écran de la configuration du module - Placeholder]

- **Activer la page de confirmation de commande**
  - **Ce que fait ce paramètre :** C'est l'interrupteur principal pour activer ou désactiver la fonctionnalité du module. Il contrôle si les commandes gratuites affichent la page de confirmation standard ou reviennent au comportement par défaut de PrestaShop (redirection vers l'historique des commandes).
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé (sélectionné "Activé") :* Toutes les commandes, y compris celles avec un total de 0,00 €, afficheront la page standard de "Confirmation de commande" après le paiement.
    - *Lorsqu'il est désactivé (sélectionné "Désactivé") :* Les commandes gratuites reviendront au comportement par défaut de PrestaShop, redirigeant les clients directement vers leur page d'historique de commandes au lieu d'afficher la page de confirmation.
  - **Valeur recommandée :** **Activé**. C'est l'objectif principal du module et il offre une meilleure expérience client.
  - **Scénario / exemple de marchand :** Si vous proposez un téléchargement gratuit d'e-book, l'activation de cette option garantit que les clients voient une page de confirmation avec un lien de téléchargement, plutôt que d'être confus par une redirection directe vers leur historique de commandes. Si vous souhaitez temporairement revenir au comportement PrestaShop par défaut pour les commandes gratuites (par exemple, pour des tests spécifiques), vous pouvez le désactiver.

### 2.2 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Par défaut / Recommandé | Objectif et impact |
| --- | --- | --- | --- |
| Page de configuration du module | Activer la page de confirmation de commande | Activé | Contrôle si les commandes gratuites affichent la page de confirmation de commande standard (Activé) ou redirigent vers l'historique des commandes (Désactivé). |

## 3. Dépannage pour les marchands et questions fréquemment posées (FAQ)

**Q : Mes commandes gratuites redirigent toujours vers la page d'historique des commandes, même après avoir activé le module. Que dois-je faire ?**
R :

1. **Vérifiez l'état du module :** Allez dans **Modules > Gestionnaire de modules** et assurez-vous que "Page de confirmation de commande pour les commandes gratuites" est installé et activé.
2. **Vérifiez la configuration du module :** Allez dans **Modules > Gestionnaire de modules > Configurer** pour ce module et assurez-vous que le paramètre "Activer la page de confirmation de commande" est défini sur **"Activé"**.
3. **Videz le cache de PrestaShop :** Allez dans **Paramètres avancés > Performances** et cliquez sur "Vider le cache" dans le coin supérieur droit. C'est souvent nécessaire après des modifications de configuration de module.
4. **Cache du navigateur :** Essayez de vider le cache de votre navigateur ou de tester dans une fenêtre de navigation privée/incognito pour exclure les problèmes de cache local.

**Q : Ce module affectera-t-il mes commandes payantes ?**
R : Non, ce module cible spécifiquement le comportement des commandes avec un total de 0,00 €. Les commandes payantes continueront d'afficher la page de confirmation de commande standard comme elles l'ont toujours fait.

**Q : Ce module nécessite-t-il des modifications de thème spéciales ?**
R : Non, le module fonctionne en surchargeant un contrôleur PrestaShop de base. Il utilise le modèle de page de confirmation de commande de votre thème existant. Aucune modification de thème n'est requise. Si votre page de confirmation de commande est belle pour les commandes payantes, elle le sera aussi pour les commandes gratuites.

**Q : Que faire si je veux afficher un contenu différent sur la page de confirmation pour les commandes gratuites par rapport aux commandes payantes ?**
R : Ce module garantit que la *même* page de confirmation est affichée. Pour afficher un contenu différent, vous devrez personnaliser votre modèle `order-confirmation.tpl` (généralement trouvé dans `themes/votre-thème/templates/checkout/`) pour inclure une logique conditionnelle basée sur le total de la commande ou le mode de paiement. Cela nécessiterait l'aide d'un développeur.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

Cette section est strictement destinée aux développeurs, aux webmasters de boutiques et aux agences techniques qui maintiennent ou étendent la boutique.

### 4.1 Aperçu de l'architecture

Le module "Page de confirmation de commande pour les commandes gratuites" réalise sa fonctionnalité en surchargeant un contrôleur frontal PrestaShop de base. Plus précisément, il cible `OrderConfirmationController` pour modifier la logique de redirection qui se produit après qu'une commande gratuite est passée. Il s'agit d'un mécanisme de surcharge PrestaShop standard, garantissant un impact minimal sur les fichiers de base et permettant une désinstallation facile.

### 4.2 Contrôleurs (`controllers/`)

- **Contrôleurs Front-Office** :
  - `freeorderconfirmation/override/controllers/front/index.php`
    - Ce fichier est un espace réservé ou un artefact du processus de surcharge. Dans PrestaShop 1.7+, les surcharges sont généralement gérées en plaçant la classe surchargée directement dans le répertoire `override/classes` ou `override/controllers`, et l'autoloader de PrestaShop gère le reste. Ce fichier `index.php` lui-même ne contient pas de définition de classe ni de logique directe pour la fonctionnalité du module. Sa présence garantit que le mécanisme de surcharge est correctement déclenché pour le `OrderConfirmationController`.
  - `freeorderconfirmation/override/controllers/front/OrderConfirmationController.php`
    - **Nom de la classe et classe parente** : `OrderConfirmationController` (surcharge la classe `OrderConfirmationController` de base).
    - **Responsabilité** : C'est le cœur de la fonctionnalité du module. Il surcharge la méthode `initContent()` (ou une logique similaire dans le cycle de vie du contrôleur) de l'`OrderConfirmationController` original. La logique PrestaShop originale vérifie si le total de la commande est zéro et, si c'est le cas, redirige le client vers son historique de commandes. Ce contrôleur surchargé supprime ou modifie cette redirection conditionnelle, garantissant que la méthode `initContent()` de l'`OrderConfirmationController` standard (qui rend la page de confirmation) est toujours exécutée, même pour les commandes gratuites. Il empêche efficacement l'appel à `Tools::redirect()` pour les commandes de valeur nulle.

### 4.3 Classes et modèles de base (`classes/`)

Aucune classe personnalisée ou définition d'`ObjectModel` n'est présente dans ce module. Le module fonctionne uniquement en surchargeant un contrôleur PrestaShop de base.

### 4.4 Actifs JavaScript (`views/js/`)

Aucun fichier JavaScript personnalisé n'est inclus avec ce module.

### 4.5 Feuilles de style CSS (`views/css/`)

Aucun fichier CSS personnalisé n'est inclus avec ce module. Le module s'appuie sur le style existant du thème pour la page de confirmation de commande.

### 4.6 Structure du modèle Smarty (`views/templates/`)

Aucun fichier de modèle Smarty personnalisé n'est inclus avec ce module. Le module garantit que le modèle de confirmation de commande *standard* de PrestaShop (généralement `themes/votre-thème/templates/checkout/order-confirmation.tpl`) est rendu pour les commandes gratuites, tout comme pour les commandes payantes.

### 4.7 Schéma de base de données et carte des hooks

- **Tables de base de données** :

  - Ce module ne crée aucune table SQL personnalisée.
  - Il stocke ses paramètres de configuration (par exemple, `freeorderconfirmation_oc`) dans la table `ps_configuration`.
  - Il stocke également `mypresta_updates`, `update_`, `updatev_` pour le suivi interne des mises à jour par MyPresta.eu.
- **Table des hooks enregistrés** :

| Nom du hook | Moment d'exécution | Objectif technique |
| --- | --- | --- |
| `actionAdminControllerSetMedia` | Exécuté lorsqu'un contrôleur d'administration définit ses médias (CSS/JS). | Utilisé par le module pour potentiellement inclure ses propres actifs pour la page de configuration du back-office. Dans le cas de ce module, il est probablement utilisé pour s'assurer que le formulaire de configuration du module est correctement rendu dans l'interface d'administration de PrestaShop, même si aucun actif personnalisé n'est explicitement chargé. |

## 5. Support officiel et mises à jour

Pour les dernières mises à jour du module, les corrections de bugs et le support technique, veuillez vous référer à votre compte client sur MyPresta.eu. Notre équipe est disponible pour vous aider avec tout problème ou question concernant le module "Page de confirmation de commande pour les commandes gratuites".
