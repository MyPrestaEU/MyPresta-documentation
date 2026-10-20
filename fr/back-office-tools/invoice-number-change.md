---
title: "Modification du numéro de facture - Manuel du Marchand et Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop 'Modification du numéro de facture' par MyPresta.eu."
sidebar:
  label: "Modification du numéro de facture - Manuel du Marchand et Guide de Configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Invoice number change sur MyPresta.eu](https://mypresta.eu/modules/administration-tools/invoice-number-change.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/back-office-tools/invoice-number-change/)
>
> ---


# Modification du numéro de facture

## 1. Exigences et compatibilité

- **Versions de PrestaShop prises en charge** : PrestaShop 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilité PHP** : PHP 5.6 - 8.5
- **Exigences d'hébergement** : Les extensions PHP standard (cURL, JSON, OpenSSL) sont généralement suffisantes. Aucune configuration de serveur spéciale n'est requise au-delà d'un environnement d'hébergement PrestaShop standard.

## 2. Guide de configuration complet (chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

Après l'installation, naviguez vers **Modules > Gestionnaire de modules** et recherchez « Modification du numéro de facture ». Cliquez sur le bouton « Configurer ».

Ce module n'a pas d'écran de configuration séparé avec plusieurs paramètres. Sa fonctionnalité est intégrée directement dans la page de détails de la commande de votre Back Office. Le bouton « Configurer » confirmera simplement que le module est installé et prêt à l'emploi.

La fonctionnalité principale de ce module est d'ajouter un nouveau champ ou de modifier un affichage existant sur la page de détails de la commande, vous permettant de modifier directement le numéro de facture.

**Comment utiliser le module :**

1. **Naviguez vers une commande :** Dans votre Back Office PrestaShop, allez dans **Commandes > Commandes**.
2. **Sélectionnez une commande :** Cliquez sur n'importe quelle commande pour afficher ses détails.
3. **Localisez la section Facture :** Faites défiler la page de détails de la commande jusqu'à ce que vous trouviez la section « Documents » ou « Factures ».
4. **Modifiez le numéro de facture :** Vous verrez maintenant un champ modifiable ou un bouton à côté du numéro de facture qui vous permet de le modifier.
   - **Ce que fait ce paramètre :** Cette fonctionnalité vous permet de saisir directement un nouveau numéro de facture pour une facture spécifique associée à la commande actuelle.
   - **Effet de la modification de ce paramètre :**
     - *Lorsque vous entrez un nouveau numéro et enregistrez :* Le numéro de facture pour cette facture de commande spécifique sera mis à jour dans votre base de données et reflété sur le document de facture lui-même (s'il est régénéré ou consulté). Ce changement est permanent et affecte vos registres financiers.
   - **Valeur recommandée :** Ne modifiez les numéros de facture que lorsque cela est absolument nécessaire et vérifiez toujours leur exactitude. Assurez-vous que le nouveau numéro suit votre schéma de numérotation interne ou les exigences légales.
   - **Scénario / exemple de marchand :** Une commande a été initialement facturée comme INV00123. En raison d'une migration de données, vous avez besoin que cette facture soit INV2024-005. Vous naviguerez vers la commande, trouverez INV00123, cliquerez pour modifier, entrerez INV2024-005 et enregistrerez.

### 2.2 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Valeur par défaut / Recommandée | Objectif et impact |
| --- | --- | --- | --- |
| Page de détails de la commande (section Documents/Factures) | Numéro de facture (champ modifiable) | N/A (dépend de la facture existante) | Permet la modification directe d'un numéro de facture pour une commande spécifique. Crucial pour les corrections, la conformité ou l'intégration avec des systèmes externes. |

## 3. Dépannage pour les marchands et questions fréquemment posées (FAQ)

**Q1 : J'ai installé le module, mais je ne vois aucune nouvelle page de paramètres. Fonctionne-t-il ?**
R1 : Oui, le module fonctionne comme prévu. Ce module n'ajoute pas de page de configuration séparée. Sa fonctionnalité est intégrée directement dans la page de détails de la commande. Naviguez vers **Commandes > Commandes**, sélectionnez une commande, et vous devriez trouver un champ modifiable ou une option pour changer le numéro de facture dans la section « Documents » ou « Factures ».

**Q2 : J'ai changé un numéro de facture, mais l'ancien numéro apparaît toujours sur la facture PDF.**
R2 : Après avoir changé le numéro de facture dans le Back Office, vous devrez peut-être régénérer la facture PDF pour cette commande afin que le nouveau numéro soit pris en compte. PrestaShop met souvent en cache le contenu PDF. Téléchargez à nouveau la facture depuis la page de détails de la commande, et elle devrait afficher le numéro mis à jour.

**Q3 : Puis-je annuler un changement de numéro de facture ?**
R3 : Le module vous permet de changer le numéro à votre guise. Si vous devez annuler, vous devrez simplement modifier le champ à nouveau et entrer le numéro original (si vous vous en souvenez ou si vous l'avez enregistré). Le module ne conserve pas d'historique des modifications lui-même, il est donc recommandé de tenir un journal précis de votre part.

**Q4 : La modification d'un numéro de facture affectera-t-elle mes rapports comptables dans PrestaShop ?**
R4 : Oui, la modification d'un numéro de facture mettra à jour le champ `invoice_number` dans votre base de données pour cette facture spécifique. Tous les rapports PrestaShop qui extraient les numéros de facture directement de la base de données refléteront le nouveau numéro. Assurez-vous que vos modifications sont cohérentes avec vos pratiques comptables.

**Q5 : Le module ne semble pas être actif sur mon thème personnalisé. Que dois-je faire ?**
R5 : Ce module utilise le système d'override de PrestaShop pour modifier le comportement de base et s'accroche aux modèles d'administration standard. Il devrait fonctionner avec la plupart des thèmes personnalisés sans problème, car il n'affecte que le Back Office. Si vous rencontrez des problèmes, videz d'abord votre cache PrestaShop (**Paramètres avancés > Performances > Vider le cache**). Si le problème persiste, il peut s'agir d'un conflit avec un autre module ou d'un modèle d'administration hautement personnalisé. Contactez le support MyPresta.eu avec les détails de votre thème et de tout autre module pertinent.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

### 4.1 Vue d'ensemble de l'architecture

Le module « Modification du numéro de facture » (`invoicenb`) est conçu pour étendre la fonctionnalité de gestion des factures de base de PrestaShop sans modifier le schéma de la base de données. Il y parvient principalement grâce à un `override` de la classe `OrderInvoice` et en s'accrochant à la page de détails de la commande du Back Office pour fournir une interface modifiable pour le numéro de facture. Cette approche garantit un impact minimal sur le système de base tout en offrant la fonctionnalité souhaitée.

### 4.2 Contrôleurs (`controllers/`)

Ce module n'introduit aucun contrôleur front-office ou back-office personnalisé. Toutes les fonctionnalités sont intégrées via le fichier de module principal, les overrides et les hooks de template.

### 4.3 Classes et modèles de base (`classes/`)

- **`invoicenb/override/classes/order/OrderInvoice.php`**
  - **Nom de la classe** : `OrderInvoice` (override de la classe `OrderInvoice` de base)
  - **Classe parente** : `OrderInvoiceCore`
  - **Responsabilité** : Cet override est le cœur de la fonctionnalité du module. Il modifie le comportement de la classe `OrderInvoice`, en particulier la façon dont les numéros de facture sont gérés et potentiellement enregistrés. L'override est responsable de permettre la mise à jour du numéro de facture depuis le Back Office. Il ajoute ou modifie probablement une méthode pour faciliter l'enregistrement d'un nouveau numéro de facture lorsqu'il est soumis via l'interface d'administration.
  - **Table de base de données** : `ps_order_invoice` (ou votre préfixe de table)
  - **Champs `$definition`** : Cet override fonctionne avec la `$definition` existante de `OrderInvoiceCore`, en particulier le champ `number`.

### 4.4 Actifs JavaScript (`views/js/`)

Ce module n'inclut aucun fichier JavaScript personnalisé. La fonctionnalité d'édition interactive est gérée directement dans les templates Smarty et potentiellement via les mécanismes AJAX standard de PrestaShop si une soumission de formulaire est impliquée.

### 4.5 Feuilles de style CSS (`views/css/`)

Ce module n'inclut aucun fichier CSS personnalisé. Le style du champ modifiable ou du bouton sur la page de commande reposera sur le CSS par défaut du Back Office de PrestaShop.

### 4.6 Structure des templates Smarty (`views/templates/`)

Ce module utilise des templates pour injecter le champ de numéro de facture modifiable dans la page de détails de la commande du Back Office.

- **Templates de hook (`views/templates/hook/`)** :
  - **`invoicenb/views/templates/hook/displayAdminOrder16.tpl`**
    - **Hook** : `displayAdminOrder` (pour PrestaShop 1.6.x)
    - **Objectif** : Ce template est rendu sur la page de détails de la commande dans PrestaShop 1.6.x. Il injecte les éléments de formulaire HTML (par exemple, un champ de saisie et un bouton d'enregistrement) qui permettent à l'administrateur de visualiser et de modifier le numéro de facture pour une commande spécifique. Il inclut probablement une logique pour afficher le numéro de facture actuel et gérer la soumission d'un nouveau.
  - **`invoicenb/views/templates/hook/displayAdminOrder17.tpl`**
    - **Hook** : `displayAdminOrder` (pour PrestaShop 1.7.x, 8.x, 9.x)
    - **Objectif** : Similaire à `displayAdminOrder16.tpl`, mais adapté à la structure des templates et potentiellement aux différents paramètres de hook de PrestaShop 1.7.x et des versions plus récentes. Il offre la même fonctionnalité : afficher un champ de numéro de facture modifiable sur la page de détails de la commande.

### 4.7 Schéma de base de données et carte des hooks

- **Tables de base de données** :

  - Le module ne crée aucune nouvelle table de base de données personnalisée. Il interagit avec la table `ps_order_invoice` existante (ou votre préfixe de table) pour mettre à jour la colonne `number`.
  - Les enregistrements de configuration sont stockés dans `ps_configuration` pour les paramètres internes du module (le cas échéant, bien que ce module semble avoir des paramètres explicites minimaux).
- **Table des hooks enregistrés** :

  | Nom du hook | Moment d'exécution | Objectif technique |
  | --- | --- | --- |
  | `displayAdminOrder` | Rend le contenu sur la page de détails de la commande du Back Office. | Utilisé pour injecter le formulaire HTML permettant de modifier le numéro de facture directement dans la vue de la commande. Le module fournit des templates séparés pour PrestaShop 1.6 et 1.7+ pour ce hook. |
  | `actionObjectOrderInvoiceUpdateAfter` | Exécuté après la mise à jour d'un objet `OrderInvoice`. | (Implicite, si l'override l'utilise) Pourrait être utilisé pour déclencher des actions supplémentaires ou la journalisation après qu'un numéro de facture a été modifié avec succès. |
  | `actionObjectOrderInvoiceAddAfter` | Exécuté après l'ajout d'un objet `OrderInvoice`. | (Implicite, si l'override l'utilise) Pourrait être utilisé pour modifier le numéro de facture initial lors de la création, bien que l'objectif principal soit de modifier ceux qui existent déjà. |

## 5. Support officiel et mises à jour

Pour les dernières mises à jour, corrections de bugs et le support officiel du module « Modification du numéro de facture », veuillez vous référer à votre compte client MyPresta.eu. Vous pouvez télécharger les versions les plus récentes depuis l'historique de vos commandes et accéder à nos canaux de support dédiés pour toute assistance technique ou question.
