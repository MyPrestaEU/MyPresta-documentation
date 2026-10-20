---
title: "Commande créée par un employé - Manuel du Marchand et Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop 'Commande créée par un employé' par MyPresta.eu."
sidebar:
  label: "Commande créée par un employé - Manuel du Marchand et Guide de Configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Order created by employee sur MyPresta.eu](https://mypresta.eu/modules/administration-tools/order-created-by-employee.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/back-office-tools/order-created-by-employee/)
>
> ---


# Commande créée par un employé

## 1. Exigences et compatibilité

- **Versions PrestaShop prises en charge** : PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilité PHP** : PHP 5.6 - 8.5
- **Exigences d'hébergement** : Extensions PHP standard (cURL, JSON, OpenSSL) généralement disponibles sur tout environnement d'hébergement compatible PrestaShop.

## 2. Guide de configuration complet (chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

Après l'installation, cliquer sur le bouton « Configurer » vous mènera à la page de configuration principale du module.

Ce module est conçu pour être extrêmement simple et efficace, nécessitant une configuration minimale. Dès l'installation, il commence automatiquement à collecter les données nécessaires.

**Ce que fait cet écran :**
Cette page sert de confirmation que le module est installé et actif. Elle ne présente aucun paramètre configurable car la fonctionnalité principale du module (journalisation des commandes créées par les employés) est activée par défaut lors de l'installation.

**Effet de la modification de ce paramètre :**
Il n'y a pas de paramètres à modifier sur cet écran. La fonctionnalité du module est « toujours active » une fois installée.

**Valeur recommandée :**
Aucune valeur à définir. Assurez-vous simplement que le module est installé et activé.

**Scénario / exemple de marchand :**
Vous venez d'installer le module. Vous naviguez vers sa page de configuration et voyez un simple message confirmant son statut. À partir de ce moment, chaque nouvelle commande créée par un employé via le Back Office de PrestaShop sera marquée comme telle. Lorsque vous visualiserez les détails d'une commande, vous verrez une nouvelle section indiquant si elle a été créée par un employé et quel employé l'a fait.

### 2.2 Écrans d'administration dédiés et vues de contrôleur

Ce module n'ajoute pas de nouveaux éléments de menu dédiés ni d'écrans d'administration complexes. Sa fonctionnalité s'intègre directement dans la page de détails de commande existante de PrestaShop.

**Nom de l'écran et emplacement du menu :**
Les informations fournies par ce module sont affichées directement sur la **Page de détails de la commande**.
Pour y accéder :

1.  Naviguez vers **Commandes > Commandes** dans votre Back Office PrestaShop.
2.  Cliquez sur n'importe quelle commande de la liste pour afficher ses détails.

**Actions et paramètres disponibles :**
Sur la page de détails de la commande, vous trouverez une nouvelle section (généralement près du haut ou dans un bloc dédié) qui indique si la commande a été créée par un employé. Si c'est le cas, elle affichera également le nom de l'employé qui l'a créée.

**Effet des modifications :**
Il n'y a pas d'actions ou de paramètres à modifier sur cette vue. Cette section est purement informative, vous fournissant les données collectées par le module.

**Flux de travail recommandé pour la gestion quotidienne de la boutique :**
Lors de l'examen des commandes, en particulier celles qui semblent inhabituelles, ou lors de la réalisation d'audits internes, vérifiez toujours la section « Commande créée par un employé » sur la page de détails de la commande. Cette vérification rapide peut fournir un contexte immédiat sur l'origine de la commande, vous aidant à comprendre s'il s'agissait d'un achat direct d'un client ou d'une saisie interne.

### 2.3 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Par défaut / Recommandé | Objectif et impact |
| --- | --- | --- | --- |
| Page de configuration du module | *(Aucun paramètre configurable)* | N/A | Confirme l'installation et l'activation du module. La fonctionnalité du module est toujours active. |
| Page de détails de la commande (Back Office) | Bloc d'informations « Commande créée par un employé » | N/A | Indique si la commande a été créée par un employé et son nom. Purement informatif. |

## 3. Dépannage du marchand et questions fréquemment posées (FAQ)

**Q : J'ai installé le module, mais je ne vois aucun changement sur les anciennes commandes.**
R : Ce module commence à collecter des données à partir du moment où il est installé. Il ne peut pas déterminer rétroactivement si les commandes passées ont été créées par un employé. Vous ne verrez les informations « Commande créée par un employé » que sur les commandes passées *après* que le module ait été installé et activé avec succès.

**Q : J'ai créé une commande dans le Back Office, mais je ne vois pas les informations de l'employé sur la page de détails de la commande.**
R : Tout d'abord, assurez-vous que le module est installé et activé (vérifiez **Modules > Gestionnaire de modules**). Si c'est le cas, videz votre cache PrestaShop (**Paramètres avancés > Performances**). Si le problème persiste, assurez-vous que vous visualisez une commande qui a été *effectivement créée par un employé* dans le Back Office *après* l'installation du module.

**Q : Ce module affecte-t-il les performances de ma boutique ?**
R : Non, le module est très léger. Il n'ajoute qu'une petite quantité de données pendant le processus de création de commande dans le Back Office et affiche ces données sur la page de détails de la commande. Il n'a aucun impact sur les performances de votre front office ou l'expérience client.

**Q : Puis-je désactiver la fonctionnalité du module sans le désinstaller ?**
R : Ce module n'a pas d'interrupteur marche/arrêt dans sa configuration. Pour arrêter sa fonctionnalité, vous devrez désactiver ou désinstaller le module via le Gestionnaire de modules. Cependant, compte tenu de sa nature bénéfique pour le suivi interne, il est généralement recommandé de le maintenir actif.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

### 4.1 Vue d'ensemble de l'architecture

Le module « Commande créée par un employé » (`logoe`) est un module PrestaShop simple conçu pour étendre la fonctionnalité de base de la classe `Order`. Il fonctionne principalement en s'accrochant au processus de création de commande dans le Back Office pour enregistrer l'`id_employee` responsable de la commande. Ces informations sont ensuite affichées sur la page de détails de commande existante dans le Back Office. Il suit un modèle simple basé sur les événements en utilisant les hooks PrestaShop.

### 4.2 Contrôleurs (`controllers/`)

Ce module n'introduit aucun contrôleur front-office ou back-office personnalisé. Toute sa logique est gérée dans le fichier principal du module et via des hooks.

### 4.3 Classes et modèles principaux (`classes/`)

Ce module n'introduit aucune classe personnalisée ou définition d'`ObjectModel`. Il interagit directement avec l'objet `Order` et `Configuration` pour ses paramètres.

### 4.4 Actifs JavaScript (`views/js/`)

Ce module n'inclut aucun fichier JavaScript personnalisé.

### 4.5 Feuilles de style CSS (`views/css/`)

Ce module n'inclut aucun fichier CSS personnalisé. Le style des informations affichées est généralement minimal et repose sur les styles existants du Back Office de PrestaShop.

### 4.6 Structure des modèles Smarty (`views/templates/`)

Ce module utilise un seul fichier de modèle pour afficher des informations dans le Back Office.

-   **Modèles d'administration (`views/templates/admin/`)** :
    -   `logoe/views/templates/admin/logoelog.tpl` : Ce modèle est responsable du rendu du bloc d'informations « Commande créée par un employé » sur la page de détails de commande du Back Office de PrestaShop. Il affiche généralement le nom de l'employé si la commande a été créée par un employé. Il est probablement rendu via un hook comme `displayAdminOrder` ou `displayAdminOrderTabContent`.

### 4.7 Schéma de base de données et carte des hooks

-   **Tables de base de données** :
    Le module ne crée pas de nouvelle table de base de données dédiée. Au lieu de cela, il étend la table `ps_orders` existante en ajoutant une nouvelle colonne lors de l'installation.

    -   `ps_orders` : Une nouvelle colonne, probablement `id_employee_created`, est ajoutée à cette table pour stocker l'ID de l'employé qui a créé la commande. Cette colonne serait `INT(10) UNSIGNED` et nullable, avec une valeur par défaut de `NULL`.
-   **Table des hooks enregistrés** :

    | Nom du hook | Moment d'exécution | Objectif technique |
    | --- | --- | --- |
    | `actionOrderAdd` | Après qu'une nouvelle commande a été ajoutée avec succès à la base de données. | Ce hook est crucial. Il est utilisé pour capturer l'`id_employee` de la session Back Office actuelle et mettre à jour la colonne `id_employee_created` de la commande nouvellement créée dans `ps_orders`. |
    | `displayAdminOrder` (ou similaire, par exemple, `displayAdminOrderTabContent`, `displayAdminOrderMain`) | Lorsque la page de détails de commande du Back Office est rendue. | Ce hook est utilisé pour injecter le modèle `logoelog.tpl` dans la page de détails de commande, affichant les informations `id_employee_created` (par exemple, le nom de l'employé). |

## 5. Support officiel et mises à jour

Pour le support officiel, les mises à jour du module et toute assistance supplémentaire, veuillez visiter votre compte client sur [MyPresta.eu](https://mypresta.eu/my-account/orders/). Notre équipe est dédiée à fournir un support rapide et à garantir le fonctionnement parfait de votre module.
"""
