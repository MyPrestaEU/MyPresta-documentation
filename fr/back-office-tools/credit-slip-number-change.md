---
title: "Modification du numéro d'avoir - Manuel du Marchand & Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop 'Modification du numéro d'avoir' par MyPresta.eu."
sidebar:
  label: "Modification du numéro d'avoir - Manuel du Marchand & Guide de Configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Credit slip number change sur MyPresta.eu](https://mypresta.eu/modules/administration-tools/credit-slip-number-change.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/back-office-tools/credit-slip-number-change/)
>
> ---


# Modification du numéro d'avoir

## 1. Exigences et compatibilité

- **Versions de PrestaShop prises en charge :** PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilité PHP :** PHP 7.1 - 8.5
- **Exigences d'hébergement :** Les extensions PHP standard (cURL, JSON, OpenSSL) sont généralement requises par PrestaShop lui-même et sont suffisantes pour ce module.

## 2. Parcours de configuration complet (chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

Ce module dispose d'une page de configuration très simple, principalement pour les mises à jour internes de MyPresta.eu. La fonctionnalité principale de modification des numéros d'avoir est accessible directement depuis la page de détails de la commande.

- **Emplacement du menu :** Back Office > Modules > Gestionnaire de modules > Recherchez « Modification du numéro d'avoir » > Cliquez sur « Configurer ».

| Paramètre / Option | Ce que fait ce paramètre | Effet de la modification de ce paramètre | Valeur recommandée | Scénario / exemple pour le marchand |
| --- | --- | --- | --- | --- |
| **Mises à jour MyPresta.eu** | Ce paramètre contrôle si le module vérifie les mises à jour de MyPresta.eu. | *Lorsque activé :* Le module vérifiera périodiquement les nouvelles versions et vous en informera dans le back-office. *Lorsque désactivé :* Le module ne vérifiera pas les mises à jour automatiquement. | OUI | Garder cette option activée vous assure d'être toujours informé des nouvelles versions, des corrections de bugs et des améliorations de fonctionnalités pour le module. |

### 2.2 Écrans d'administration dédiés et vues de contrôleur

La fonctionnalité principale de ce module est intégrée directement dans la **page de détails de la commande** de votre back-office PrestaShop. Il n'y a pas d'écrans d'administration dédiés séparés.

- **Nom de l'écran et emplacement du menu :** Back Office > Commandes > Commandes > Cliquez sur n'importe quelle commande pour afficher ses détails.
- **Actions et paramètres disponibles :**
  - Sur la page de détails de la commande, faites défiler jusqu'à la section « Avoirs ».
  - Pour chaque avoir listé, vous verrez un nouveau champ de saisie à côté de son numéro actuel.
  - Vous pouvez taper un nouveau numéro dans ce champ.
  - Après avoir entré le nouveau numéro, cliquez sur le bouton « Enregistrer » (ou une icône similaire, généralement une disquette ou une coche) à côté du champ de saisie pour appliquer la modification.
- **Effet des modifications :**
  - Lorsque vous modifiez un numéro d'avoir et l'enregistrez, le nouveau numéro est immédiatement mis à jour dans votre base de données PrestaShop.
  - Ce nouveau numéro sera ensuite reflété sur le PDF d'avoir généré pour cet avoir spécifique. Vous et votre client verrez le numéro mis à jour sur le document.
- **Flux de travail recommandé pour la gestion quotidienne du magasin :**
  1. Allez dans **Commandes > Commandes** dans votre back-office PrestaShop.
  2. Sélectionnez la commande pour laquelle vous devez modifier un numéro d'avoir.
  3. Sur la page de détails de la commande, localisez le bloc « Avoirs ».
  4. Trouvez l'avoir spécifique que vous souhaitez modifier.
  5. Entrez le nouveau numéro souhaité dans le champ de saisie fourni.
  6. Cliquez sur l'icône d'enregistrement à côté du champ de saisie.
  7. Vérifiez la modification en téléchargeant le PDF de l'avoir ; il devrait maintenant afficher le nouveau numéro.

### 2.3 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Par défaut / Recommandé | Objectif et impact |
| --- | --- | --- | --- |
| Configuration du module | Mises à jour MyPresta.eu | OUI | Contrôle les vérifications automatiques des mises à jour pour le module. |
| Page de détails de la commande (section Avoirs) | Champ de saisie du numéro d'avoir | N/A (Défini par l'utilisateur) | Permet la modification directe des numéros d'avoir individuels. Les modifications sont reflétées sur le PDF. |

## 3. Dépannage pour le marchand et questions fréquemment posées (FAQ)

**Q : J'ai changé le numéro d'avoir, mais il n'apparaît pas sur le PDF.**
R : Après avoir changé le numéro, assurez-vous d'avoir cliqué sur le bouton « Enregistrer » à côté du champ de saisie. Ensuite, régénérez ou téléchargez à nouveau le PDF de l'avoir. Si cela ne s'affiche toujours pas, essayez de vider le cache de votre navigateur ou le cache Smarty de PrestaShop (Paramètres avancés > Performance > Vider le cache).

**Q : Puis-je modifier le numéro d'un avoir déjà validé ou envoyé ?**
R : Oui, le module vous permet de modifier le numéro de tout avoir existant. La modification n'affectera que le numéro affiché sur le PDF, et non la transaction financière sous-jacente elle-même.

**Q : Existe-t-il un moyen de modifier en masse les numéros d'avoir ?**
R : Non, ce module est conçu pour les modifications individuelles des numéros d'avoir directement sur la page de détails de la commande. Il n'offre pas de fonctionnalité de modification en masse. Pour les opérations en masse, un développement personnalisé pourrait être nécessaire.

**Q : Que se passe-t-il si j'entre un numéro d'avoir en double ?**
R : Le système principal de PrestaShop pourrait ne pas empêcher les numéros d'avoir en double, car le module met directement à jour le numéro. Il est de votre responsabilité d'assurer l'unicité si vos pratiques comptables l'exigent. Le module facilite la modification mais n'applique pas de contraintes d'unicité au-delà du comportement par défaut de PrestaShop.

**Q : Le champ de saisie pour modifier le numéro n'apparaît pas sur ma page de commande.**
R :

1. **Vérifiez l'installation du module :** Assurez-vous que le module est correctement installé et activé dans **Modules > Gestionnaire de modules**.
2. **Videz le cache :** Allez dans **Paramètres avancés > Performance** et cliquez sur « Vider le cache ».
3. **Compatibilité du thème :** Bien que le module utilise des hooks PrestaShop standard, des thèmes très fortement personnalisés peuvent parfois interférer. Si le problème persiste, passez temporairement au thème PrestaShop par défaut pour voir si le champ apparaît. Si c'est le cas, votre thème pourrait nécessiter un petit ajustement.
4. **Version de PrestaShop :** Assurez-vous d'avoir téléchargé la version correcte du module pour votre installation PrestaShop.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

### 4.1 Aperçu de l'architecture

Le module « Modification du numéro d'avoir » (`creditnb`) est un module PrestaShop léger qui étend la fonctionnalité du back-office en injectant un champ de saisie personnalisé dans le hook `displayAdminOrder`. Cela permet aux administrateurs de modifier les numéros d'avoir directement sur la page de détails de la commande. Le module interagit principalement avec l'objet `OrderSlip` de PrestaShop et sa table de base de données associée pour mettre à jour le champ `number`. Il utilise la structure de module et le templating standard de PrestaShop.

### 4.2 Contrôleurs (`controllers/`)

Ce module n'introduit aucun contrôleur front-office ou back-office personnalisé. Toutes les interactions sont gérées via le fichier principal du module (`creditnb.php`) et les mécanismes AJAX standard de PrestaShop pour les soumissions de formulaires au sein de la page d'administration des commandes.

### 4.3 Classes et modèles principaux (`classes/`)

Ce module n'introduit aucune classe ou modèle personnalisé dans le répertoire `classes/`. Il interagit directement avec l'objet natif `OrderSlip` de PrestaShop.

### 4.4 Actifs JavaScript (`views/js/`)

Ce module n'inclut aucun fichier JavaScript personnalisé. La fonctionnalité de sauvegarde du nouveau numéro d'avoir est gérée par la soumission du formulaire dans le template du hook `displayAdminOrder`, probablement en utilisant les mécanismes AJAX ou de gestion de formulaire existants de PrestaShop.

### 4.5 Feuilles de style CSS (`views/css/`)

Ce module n'inclut aucun fichier CSS personnalisé. Le style du champ de saisie est censé hériter du thème du back-office de PrestaShop.

### 4.6 Structure des templates Smarty (`views/templates/`)

Le module utilise des templates de hook pour injecter sa fonctionnalité dans le back-office de PrestaShop.

- **Templates de hook (`views/templates/hook/`)** :
  - `creditnb/views/templates/hook/displayAdminOrder16.tpl`
    - **Objectif :** Ce template est conçu pour PrestaShop 1.6.x (bien que le module liste la compatibilité 1.7.x, 8.x, 9.x, ce fichier pourrait être une inclusion héritée ou pour une compatibilité plus large). Il rend le champ de saisie et le bouton d'enregistrement pour modifier les numéros d'avoir dans la section « Avoirs » de la page de détails de la commande.
    - **Hook :** `displayAdminOrder`
    - **Sortie :** Un bloc HTML contenant un élément de formulaire avec un champ de saisie pour le numéro de chaque avoir et un mécanisme pour enregistrer la valeur mise à jour.
  - `creditnb/views/templates/hook/displayAdminOrder17.tpl`
    - **Objectif :** Ce template est conçu pour PrestaShop 1.7.x, 8.x et 9.x. Il rend le champ de saisie et le bouton d'enregistrement pour modifier les numéros d'avoir dans la section « Avoirs » de la page de détails de la commande, adapté à la nouvelle interface utilisateur du back-office.
    - **Hook :** `displayAdminOrder`
    - **Sortie :** Un bloc HTML contenant un élément de formulaire avec un champ de saisie pour le numéro de chaque avoir et un mécanisme pour enregistrer la valeur mise à jour.

### 4.7 Schéma de la base de données et carte des hooks

- **Tables de la base de données** :

  - Le module ne crée aucune nouvelle table de base de données personnalisée.
  - Il modifie la colonne `number` dans la table `ps_order_slip` (ou `_order_slip`), qui fait partie du schéma de base de données principal de PrestaShop.
  - Les paramètres de configuration (`mypresta_updates`, `update_`, `updatev_`) sont stockés dans la table `ps_configuration`.
- **Table des hooks enregistrés** :

| Nom du hook | Moment d'exécution | Objectif technique |
| --- | --- | --- |
| `displayAdminOrder` | Rend le contenu sur la page de détails de la commande du back-office PrestaShop. | Injecte le champ de saisie personnalisé et le mécanisme de sauvegarde pour modifier les numéros d'avoir directement dans la section « Avoirs » de la vue de la commande. |

## 5. Support officiel et mises à jour

Pour les dernières mises à jour, corrections de bugs et support professionnel pour le module « Modification du numéro d'avoir », veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu/my-account/orders/). Notre équipe est dédiée à assurer le bon fonctionnement et l'amélioration continue de nos modules.
