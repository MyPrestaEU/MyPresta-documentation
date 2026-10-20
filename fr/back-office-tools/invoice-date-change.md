---
title: "Changement de date de facture - Manuel du Marchand & Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop 'Changement de date de facture' par MyPresta.eu."
sidebar:
  label: "Changement de date de facture - Manuel du Marchand & Guide de Configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Invoice date change sur MyPresta.eu](https://mypresta.eu/modules/administration-tools/invoice-date-change.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/back-office-tools/invoice-date-change/)
>
> ---


# Changement de date de facture

## 1. Exigences et compatibilité

- **Versions PrestaShop prises en charge** : PrestaShop 1.6.x, 1.7.x
- **Compatibilité PHP** : PHP 5.6 - 8.5
- **Exigences d'hébergement** : Les extensions PHP standard (cURL, JSON, OpenSSL) sont généralement suffisantes. Aucune configuration de serveur spéciale n'est requise au-delà d'un environnement d'hébergement PrestaShop standard.

## 2. Parcours de configuration complet (chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

Après l'installation, cliquez sur « Configurer » à côté du module « Changement de date de facture ». Cela vous mènera à l'écran de configuration principal.

Sur cet écran, vous trouverez la fonctionnalité principale du module, qui vous permet de définir la date de facture souhaitée pour une commande.

**Comment l'utiliser :**

1. **Naviguez vers une commande :**
   - Allez dans **Commandes > Commandes** dans votre Back Office PrestaShop.
   - Cliquez sur une commande existante pour afficher ses détails.
2. **Localisez la section Date de facture :**
   - Sur la page de détail de la commande, faites défiler vers le bas. Vous trouverez une nouvelle section ou un bloc lié au « Changement de date de facture ».
   - Cette section apparaîtra généralement dans le bloc « Documents » ou une zone similaire où les factures sont gérées.
3. **Sélectionnez la date souhaitée :**
   - Vous verrez un champ de sélection de date. Cliquez sur ce champ pour ouvrir un calendrier.
   - Choisissez la date exacte que vous souhaitez voir apparaître sur la facture. Il peut s'agir d'une date passée ou future.
4. **Enregistrez vos modifications :**
   - Après avoir sélectionné la date, il y aura un bouton « Enregistrer » ou « Mettre à jour » dans cette section. Cliquez dessus pour appliquer la nouvelle date de facture à la commande.
5. **Générez ou régénérez la facture :**
   - Une fois la date enregistrée, si vous générez une nouvelle facture pour cette commande (ou régénérez une facture existante), le PDF reflétera la date que vous venez de définir.

**Ce que fait ce paramètre :** Ce module n'a pas d'interrupteur global « on/off » ou de paramètres complexes. Sa fonction principale est d'injecter un sélecteur de date directement dans les pages de détail de vos commandes dans le Back Office. Ce sélecteur de date vous permet de remplacer manuellement la date de génération de facture par défaut pour les commandes individuelles.

**Effet de la modification de ce paramètre :**

- *Lorsque vous sélectionnez une date et enregistrez :* La date choisie est stockée pour cette commande spécifique. Toute facture générée pour cette commande *après* que vous ayez défini cette date utilisera votre date sélectionnée au lieu de la date système actuelle.
- *Lorsque vous n'utilisez pas le sélecteur de date du module :* PrestaShop continuera à générer des factures avec la date actuelle, comme il le fait par défaut.

**Valeur recommandée :** Utilisez le sélecteur de date pour sélectionner la date exacte requise pour chaque facture spécifique. Il n'y a pas de « valeur recommandée » globale car la date variera par commande.

**Scénario / exemple de marchand :**
Imaginez qu'un client ait passé une commande le 15 janvier, mais qu'en raison d'un retard de stock, le produit n'ait été expédié et facturé que le 25 janvier. Cependant, à des fins comptables, vous avez besoin que la date de la facture reflète la date de commande originale du 15 janvier.

1. Vous accédez à la page des détails de cette commande spécifique.
2. Dans la section « Changement de date de facture », vous ouvrez le calendrier et sélectionnez le 15 janvier.
3. Vous cliquez sur « Enregistrer ».
4. Maintenant, lorsque vous générez la facture PDF pour cette commande, elle affichera « 15 janvier » comme date de facture, même si vous l'avez générée le 25 janvier.

### 2.2 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Par défaut / Recommandé | Objectif et impact |
| --- | --- | --- | --- |
| Page de détail de la commande (Back Office) | Sélecteur de date (dans la section « Changement de date de facture ») | Varie par commande | Permet la sélection manuelle de la date d'émission de la facture pour une commande spécifique. La date sélectionnée apparaîtra sur la facture PDF générée, remplaçant la date actuelle par défaut. |
| Page de détail de la commande (Back Office) | Bouton Enregistrer/Mettre à jour | N/A | Applique la date de facture sélectionnée à la commande actuelle. |

## 3. Dépannage du marchand et questions fréquemment posées (FAQ)

**Q : J'ai changé la date, mais la facture affiche toujours l'ancienne date. Qu'est-ce qui ne va pas ?**
R : Assurez-vous d'avoir cliqué sur le bouton « Enregistrer » ou « Mettre à jour » après avoir sélectionné la nouvelle date sur la page de détail de la commande. Assurez-vous également de générer une *nouvelle* facture ou de *régénérer* celle existante *après* avoir enregistré la nouvelle date. Si vous consultez un PDF déjà téléchargé, il ne se mettra pas à jour comme par magie. Vous devez le télécharger à nouveau.

**Q : Le sélecteur de date n'apparaît pas sur ma page de commande.**
R :

1. **Vérifiez l'installation du module :** Allez dans **Modules > Gestionnaire de modules** et assurez-vous que « Changement de date de facture » est installé et activé.
2. **Videz le cache :** Allez dans **Paramètres avancés > Performances** et cliquez sur « Vider le cache » (ou « Vider le cache Smarty » dans les versions plus anciennes). Parfois, PrestaShop a besoin d'une actualisation du cache pour afficher les nouveaux éléments du module.
3. **Compatibilité du thème :** Bien que le module soit conçu pour s'intégrer de manière transparente, des thèmes très fortement personnalisés peuvent occasionnellement interférer. Si vider le cache ne résout pas le problème, passez temporairement au thème PrestaShop par défaut pour voir si le sélecteur de date apparaît. Si c'est le cas, votre thème pourrait nécessiter un petit ajustement.

**Q : Puis-je modifier la date de plusieurs factures à la fois ?**
R : Non, ce module est conçu pour les modifications de date de facture de commandes individuelles. Vous devez accéder à la page de détail de chaque commande pour définir sa date de facture spécifique. Il n'y a pas de fonction d'édition en masse.

**Q : Ce module affecte-t-il d'autres dates dans PrestaShop, comme la date de commande ou la date de paiement ?**
R : Non, ce module ne modifie *que* la date d'émission qui apparaît sur la facture PDF générée. Il ne modifie pas la date de création de la commande, la date de paiement ou tout autre horodatage associé à la commande dans votre base de données.

**Q : Ce module fonctionnera-t-il avec mon modèle de facture personnalisé ?**
R : Oui, le module injecte la date choisie dans le processus de génération de facture standard de PrestaShop. Tant que votre modèle de facture personnalisé utilise correctement les variables standard pour la date de facture, il devrait afficher la date définie par le module.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

### 4.1 Vue d'ensemble de l'architecture

Le module « Changement de date de facture » est un module PrestaShop léger principalement conçu pour étendre la fonctionnalité de gestion des commandes du Back Office. Il tire parti du système de hooks de PrestaShop pour injecter un champ de saisie de date personnalisé dans la page de détail de la commande. Lorsqu'une nouvelle date est sélectionnée et enregistrée, il met à jour le champ `invoice_date` de l'objet `OrderInvoice`, garantissant que les générations de factures PDF ultérieures reflètent la date définie par l'utilisateur. Il suit une approche simple et directe sans structures MVC complexes ni tables de base de données personnalisées, en s'appuyant sur les fonctionnalités de base existantes de PrestaShop.

### 4.2 Contrôleurs (`controllers/`)

Ce module n'introduit aucun contrôleur front-office ou back-office personnalisé. Toute la logique est gérée dans le fichier principal du module (`invoicedate/index.php`) et via le système de hooks de PrestaShop.

### 4.3 Classes et modèles de base (`classes/`)

Ce module n'introduit aucune classe ou modèle personnalisé dans le répertoire `classes/`. Il interagit directement avec l'objet `OrderInvoice` de base et ses propriétés.

### 4.4 Actifs JavaScript (`views/js/`)

Aucun fichier JavaScript personnalisé n'est inclus dans ce module. La fonctionnalité de sélecteur de date est généralement fournie par les bibliothèques JavaScript de base de PrestaShop (par exemple, jQuery UI Datepicker) qui sont déjà chargées dans le Back Office.

### 4.5 Feuilles de style CSS (`views/css/`)

Aucun fichier CSS personnalisé n'est inclus dans ce module. Le style du sélecteur de date et des éléments environnants repose sur le CSS par défaut du Back Office de PrestaShop.

### 4.6 Structure des modèles Smarty (`views/templates/`)

Le module utilise deux modèles spécifiques pour afficher le champ de saisie de date sur la page de détail de la commande, en fonction de la version de PrestaShop.

- **Modèles de hook (`views/templates/hook/`)** :
  - `invoicedate/views/templates/hook/displayAdminOrder16.tpl`
    - **Hook** : Ce modèle est rendu dans le hook `displayAdminOrder`, spécifiquement pour les versions de PrestaShop 1.6.x.
    - **Objectif** : Il génère la structure HTML pour le champ de saisie de la date de facture (un sélecteur de date) et un bouton de soumission dans la page des détails de la commande dans le Back Office de PrestaShop 1.6. Il permet à l'administrateur de sélectionner et d'enregistrer une date de facture personnalisée pour la commande actuelle.
  - `invoicedate/views/templates/hook/displayAdminOrder17.tpl`
    - **Hook** : Ce modèle est rendu dans le hook `displayAdminOrder`, spécifiquement pour les versions de PrestaShop 1.7.x et plus récentes.
    - **Objectif** : Similaire à la version 1.6, ce modèle fournit le HTML pour le champ de saisie de la date de facture et le bouton de soumission, adapté aux différences structurelles et de style de la page de commande du Back Office de PrestaShop 1.7+.

### 4.7 Schéma de base de données et carte des hooks

- **Tables de base de données** :
  Ce module ne crée aucune nouvelle table de base de données personnalisée. Il modifie le champ `invoice_date` de la table `ps_order_invoice` existante (ou `_order_invoice` selon votre préfixe) lorsqu'une date de facture est mise à jour via l'interface du module.
- **Table des hooks enregistrés** :

| Nom du hook | Moment d'exécution | Objectif technique |
| --- | --- | --- |
| `displayAdminOrder` | Exécuté sur la page de détail de la commande du Back Office de PrestaShop. | Ce hook est utilisé pour injecter le HTML personnalisé du module (le sélecteur de date et le bouton d'enregistrement) dans la vue des détails de la commande, permettant au marchand d'interagir avec le paramètre de date de facture. Le module utilise des modèles spécifiques à la version (`displayAdminOrder16.tpl` ou `displayAdminOrder17.tpl`) pour ce hook. |

## 5. Support officiel et mises à jour

Pour les dernières mises à jour, corrections de bugs et support officiel du module « Changement de date de facture », veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu/). Notre équipe de support est disponible pour vous aider avec tout problème ou question concernant la fonctionnalité et la compatibilité du module.
