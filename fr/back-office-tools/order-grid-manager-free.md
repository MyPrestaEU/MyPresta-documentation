---
title: "Order Grid Manager Free - Manuel du Marchand & Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop Order Grid Manager Free par MyPresta.eu."
sidebar:
  label: "Order Grid Manager Free - Manuel du Marchand & Guide de Configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Order Grid Manager Free sur MyPresta.eu](https://mypresta.eu/modules/administration-tools/order-grid-manager-free.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/back-office-tools/order-grid-manager-free/)
>
> ---


# Order Grid Manager Free

## 1. Exigences et compatibilité

- **Versions PrestaShop prises en charge** : PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilité PHP** : PHP 7.1 - 8.5
- **Exigences d'hébergement** : Extensions PHP standard (cURL, JSON, OpenSSL) généralement incluses dans tout environnement d'hébergement web moderne.

## 2. Guide de configuration complet (Chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

Après l'installation, cliquer sur « Configurer » vous mènera à la page principale des paramètres du module. Ici, vous trouverez une liste de toutes les colonnes qui apparaissent dans la liste des commandes de votre Back Office PrestaShop. Chaque colonne dispose d'un simple interrupteur ON/OFF.

**Nom de l'écran et emplacement du menu :**

- **Chemin du menu :** Back Office > Modules > Gestionnaire de modules > Order Grid Manager Free > Configurer

**Paramètres disponibles :**
Vous verrez une liste de cases à cocher ou d'interrupteurs, chacun correspondant à une colonne de votre liste de commandes du Back Office. La liste exacte des colonnes peut varier légèrement en fonction de votre version de PrestaShop et des autres modules installés, mais les exemples courants incluent :

- **ID :** L'identifiant unique de chaque commande.

  - **Ce que fait ce paramètre :** Contrôle si la colonne « ID » est visible dans votre liste de commandes.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'activé :* La colonne « ID » sera affichée.
    - *Lorsqu'désactivé :* La colonne « ID » sera masquée.
  - **Valeur recommandée :** OUI (Souvent utile pour une référence rapide et le support).
  - **Scénario/exemple pour le marchand :** Si vous référencez fréquemment les commandes par leur ID unique lorsque vous communiquez avec les clients ou votre entrepôt, gardez cette option activée. Si vous utilisez principalement d'autres identifiants comme le nom du client ou la référence, vous pourriez la masquer.
- **Référence :** Le numéro de référence interne de la commande.

  - **Ce que fait ce paramètre :** Contrôle la visibilité de la colonne « Référence ».
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'activé :* La colonne « Référence » sera affichée.
    - *Lorsqu'désactivé :* La colonne « Référence » sera masquée.
  - **Valeur recommandée :** OUI (Crucial pour le suivi et la communication interne).
  - **Scénario/exemple pour le marchand :** La plupart des marchands utilisent la référence de commande pour les bons de livraison, les factures et le service client. Gardez cette option visible, sauf si vous avez un flux de travail très spécifique qui ne l'utilise pas.
- **Nouveau client :** Indique si la commande provient d'un nouveau client.

  - **Ce que fait ce paramètre :** Contrôle la visibilité de la colonne « Nouveau client ».
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'activé :* La colonne « Nouveau client » sera affichée.
    - *Lorsqu'désactivé :* La colonne « Nouveau client » sera masquée.
  - **Valeur recommandée :** NON (Sauf si vous ciblez spécifiquement les données des nouveaux clients dans votre flux de travail quotidien).
  - **Scénario/exemple pour le marchand :** Si votre équipe marketing examine fréquemment les commandes pour identifier les tendances d'acquisition de nouveaux clients, vous pourriez garder cette option visible. Sinon, c'est souvent un bon candidat à masquer pour une vue plus propre.
- **Client :** Le nom du client qui a passé la commande.

  - **Ce que fait ce paramètre :** Contrôle la visibilité de la colonne « Client ».
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'activé :* La colonne « Client » sera affichée.
    - *Lorsqu'désactivé :* La colonne « Client » sera masquée.
  - **Valeur recommandée :** OUI (Presque toujours essentiel pour l'identification des commandes).
  - **Scénario/exemple pour le marchand :** Vous avez presque certainement besoin de voir qui a passé la commande. Gardez cette option activée.
- **Total :** Le montant total de la commande.

  - **Ce que fait ce paramètre :** Contrôle la visibilité de la colonne « Total ».
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'activé :* La colonne « Total » sera affichée.
    - *Lorsqu'désactivé :* La colonne « Total » sera masquée.
  - **Valeur recommandée :** OUI (Important pour un aperçu financier).
  - **Scénario/exemple pour le marchand :** Essentiel pour voir rapidement la valeur de chaque commande. Gardez cette option activée.
- **Paiement :** La méthode de paiement utilisée pour la commande.

  - **Ce que fait ce paramètre :** Contrôle la visibilité de la colonne « Paiement ».
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'activé :* La colonne « Paiement » sera affichée.
    - *Lorsqu'désactivé :* La colonne « Paiement » sera masquée.
  - **Valeur recommandée :** OUI (Utile pour la réconciliation des paiements).
  - **Scénario/exemple pour le marchand :** Si vous avez besoin de voir rapidement si une commande a été payée par carte de crédit, PayPal ou virement bancaire, gardez cette option activée.
- **Statut :** Le statut actuel de la commande (par exemple, Paiement accepté, Expédié, Livré).

  - **Ce que fait ce paramètre :** Contrôle la visibilité de la colonne « Statut ».
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'activé :* La colonne « Statut » sera affichée.
    - *Lorsqu'désactivé :* La colonne « Statut » sera masquée.
  - **Valeur recommandée :** OUI (Critique pour le suivi de l'avancement des commandes).
  - **Scénario/exemple pour le marchand :** Absolument essentiel pour la gestion de l'exécution des commandes. Gardez cette option activée.
- **Date :** La date et l'heure de la commande.

  - **Ce que fait ce paramètre :** Contrôle la visibilité de la colonne « Date ».
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'activé :* La colonne « Date » sera affichée.
    - *Lorsqu'désactivé :* La colonne « Date » sera masquée.
  - **Valeur recommandée :** OUI (Important pour l'ordre chronologique et le vieillissement).
  - **Scénario/exemple pour le marchand :** Utile pour trier les commandes par date de placement ou identifier les commandes plus anciennes qui nécessitent une attention. Gardez cette option activée.
- **Facture :** Lien pour afficher/télécharger la facture.

  - **Ce que fait ce paramètre :** Contrôle la visibilité de la colonne « Facture ».
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'activé :* La colonne « Facture » sera affichée.
    - *Lorsqu'désactivé :* La colonne « Facture » sera masquée.
  - **Valeur recommandée :** OUI (Pratique pour un accès rapide aux factures).
  - **Scénario/exemple pour le marchand :** Si votre équipe a fréquemment besoin de télécharger ou d'afficher des factures directement depuis la liste des commandes, gardez cette option activée.
- **Livraison :** Lien pour afficher/télécharger le bon de livraison.

  - **Ce que fait ce paramètre :** Contrôle la visibilité de la colonne « Livraison ».
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'activé :* La colonne « Livraison » sera affichée.
    - *Lorsqu'désactivé :* La colonne « Livraison » sera masquée.
  - **Valeur recommandée :** OUI (Pratique pour un accès rapide aux bons de livraison).
  - **Scénario/exemple pour le marchand :** Si votre entrepôt ou votre équipe d'expédition utilise des bons de livraison, garder cette option visible offre un accès rapide.
- **Actions :** Boutons pour afficher, modifier ou supprimer la commande.

  - **Ce que fait ce paramètre :** Contrôle la visibilité de la colonne « Actions ».
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'activé :* La colonne « Actions » sera affichée.
    - *Lorsqu'désactivé :* La colonne « Actions » sera masquée.
  - **Valeur recommandée :** OUI (Essentiel pour la gestion des commandes individuelles).
  - **Scénario/exemple pour le marchand :** Vous aurez presque toujours besoin d'afficher ou de modifier une commande. Gardez cette option activée.

**Enregistrement de vos modifications :**
Après avoir fait vos sélections, n'oubliez pas de cliquer sur le bouton **« Enregistrer »** (généralement en bas de la page de configuration) pour appliquer vos modifications. Une fois enregistré, naviguez vers **Commandes > Commandes** dans votre Back Office pour voir la disposition des colonnes mise à jour.

### 2.2 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Par défaut / Recommandé | Objectif et impact |
| --- | --- | --- | --- |
| Configuration du module | ID | OUI | Affiche/masque l'ID unique de la commande. |
| Configuration du module | Référence | OUI | Affiche/masque la référence interne de la commande. |
| Configuration du module | Nouveau client | NON | Affiche/masque l'indicateur pour les nouveaux clients. |
| Configuration du module | Client | OUI | Affiche/masque le nom du client. |
| Configuration du module | Total | OUI | Affiche/masque le montant total de la commande. |
| Configuration du module | Paiement | OUI | Affiche/masque la méthode de paiement utilisée. |
| Configuration du module | Statut | OUI | Affiche/masque le statut actuel de la commande. |
| Configuration du module | Date | OUI | Affiche/masque la date de placement de la commande. |
| Configuration du module | Facture | OUI | Affiche/masque le lien de téléchargement de la facture. |
| Configuration du module | Livraison | OUI | Affiche/masque le lien de téléchargement du bon de livraison. |
| Configuration du module | Actions | OUI | Affiche/masque les boutons d'action (afficher, modifier, supprimer). |

## 3. Dépannage pour les marchands et questions fréquemment posées (FAQ)

**Q : J'ai configuré le module, mais la grille des commandes n'a pas changé.**
R : Après avoir enregistré vos modifications dans la configuration du module, vous devrez peut-être vider le cache de votre PrestaShop. Allez dans **Paramètres avancés > Performances**, et cliquez sur « Vider le cache » dans le coin supérieur droit. Essayez également de rafraîchir la page de votre navigateur (Ctrl+F5 ou Cmd+R) pour vous assurer que vous ne voyez pas une version en cache du Back Office.

**Q : Puis-je avoir différentes vues de colonnes pour différents utilisateurs administrateurs ?**
R : Le module « Order Grid Manager Free » applique un paramètre unique et universel pour tous les administrateurs. Il ne prend pas en charge les préférences utilisateur individuelles pour la visibilité des colonnes. Si vous avez besoin de cette fonctionnalité avancée, vous devrez peut-être rechercher un module premium ou un développement personnalisé.

**Q : Ce module affectera-t-il les performances de ma boutique ?**
R : Non, ce module a un impact négligeable sur les performances. Il ne modifie que les colonnes affichées dans la liste des commandes du Back Office, ce qui est un ajustement de rendu côté client (navigateur) basé sur une configuration simple. Il n'altère pas les requêtes de base de données ni les temps de chargement du front-office.

**Q : Que se passe-t-il si je masque accidentellement une colonne dont j'ai besoin ?**
R : Pas de problème ! Retournez simplement dans **Modules > Gestionnaire de modules > Order Grid Manager Free > Configurer**, réactivez la colonne souhaitée en cochant sa case, et enregistrez vos modifications. Ensuite, videz votre cache et rafraîchissez votre navigateur.

**Q : Ce module prend-il en charge les traductions multilingues pour les noms de colonnes ?**
R : Le module lui-même n'introduit pas de nouvelles chaînes traduisibles pour les noms de colonnes. Il contrôle simplement la visibilité des noms de colonnes PrestaShop existants, qui sont déjà gérés par le système de traduction principal de PrestaShop.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

Cette section fournit un aperçu technique pour les développeurs et les webmasters souhaitant comprendre, déboguer ou étendre le module « Order Grid Manager Free ».

### 4.1 Aperçu de l'architecture

Le module `Order Grid Manager Free` est un module PrestaShop simple, principalement conçu pour modifier l'affichage de la liste `AdminOrders`. Il utilise le système de configuration de PrestaShop pour stocker les préférences de l'utilisateur concernant la visibilité des colonnes et injecte du JavaScript pour masquer/afficher dynamiquement les colonnes en fonction de ces paramètres. Il suit une structure de module PrestaShop de base, sa logique principale résidant dans le fichier principal du module.

### 4.2 Contrôleurs (`controllers/`)

Ce module n'utilise pas de contrôleurs Front-Office ou Back-Office personnalisés. Toute la configuration et la logique sont gérées au sein de la classe principale du module et de sa méthode `getContent()`.

### 4.3 Classes et modèles principaux (`classes/`)

Ce module ne définit aucune classe personnalisée ou instance d'`ObjectModel`. Il opère directement sur la configuration principale de PrestaShop et les structures existantes du Back Office.

### 4.4 Actifs JavaScript (`views/js/`)

Ce module n'inclut aucun fichier JavaScript dédié dans `views/js/`. La logique de masquage/affichage des colonnes est probablement injectée directement dans le Back Office via un hook ou dans le template de la méthode `getContent()`, en utilisant du JavaScript en ligne ou une simple injection CSS. Compte tenu de la simplicité du module et de sa désignation « Free », il est fort probable que le masquage des colonnes soit réalisé en ajoutant des règles CSS `display: none;` ou en manipulant directement le DOM après le chargement de la page, en fonction de la configuration stockée.

### 4.5 Feuilles de style CSS (`views/css/`)

Ce module n'inclut aucun fichier CSS dédié dans `views/css/`. Similaire au JavaScript, tout style (principalement `display: none;` pour les colonnes) est probablement injecté en ligne ou généré dynamiquement en fonction de la configuration.

### 4.6 Structure du template Smarty (`views/templates/`)

- **`myordergridfree/views/templates/admin/advert.tpl`** :
  - **Portée :** Back-office (page de configuration de l'administrateur).
  - **Objectif :** Ce template est probablement utilisé pour afficher une publicité ou un message promotionnel dans la page de configuration du module dans le Back Office. C'est une pratique courante pour les modules gratuits d'inclure de tels éléments. Il ne contrôle pas directement la fonctionnalité de la grille des commandes mais fait partie de la sortie `getContent()` du module.

Le formulaire de configuration réel pour la visibilité des colonnes est probablement rendu directement dans la méthode `getContent()` du fichier principal du module, éventuellement en utilisant `HelperForm` de PrestaShop ou du HTML personnalisé, puis `advert.tpl` est inclus pour le contenu promotionnel.

### 4.7 Schéma de la base de données et carte des hooks

- **Tables de la base de données** :

  - Ce module ne crée aucune table SQL personnalisée.
  - Il stocke ses paramètres de configuration dans la table standard `ps_configuration` de PrestaShop. Chaque paramètre (par exemple, `MYORDERGRIDFREE_HIDE_ID_COLUMN`) correspondra à une ligne dans cette table, stockant une valeur booléenne (0 ou 1) pour la visibilité.
- **Table des hooks enregistrés** :
  La fonctionnalité principale de ce module repose sur la modification de l'affichage du Back Office. Compte tenu de la simplicité de la version « Free », il utilise probablement une ou plusieurs des approches suivantes :

| Nom du hook | Moment d'exécution | Objectif technique |
| --- | --- | --- |
| `displayBackOfficeHeader` | Exécuté dans la section `<head>` des pages du Back Office. | Hook le plus probable pour injecter du CSS ou du JavaScript en ligne afin de masquer les colonnes sur la page `AdminOrders`. Cela permet au module d'appliquer `display: none;` à des éléments `<th>` et `<td>` spécifiques en fonction de la configuration enregistrée. |
| `actionAdminControllerSetMedia` | Exécuté lorsqu'un contrôleur Admin définit ses ressources média. | Pourrait être utilisé pour enregistrer un petit fichier JS ou un script en ligne qui s'exécute spécifiquement sur le contrôleur `AdminOrders` pour manipuler le DOM. |
| `displayAdminOrderListBefore` / `displayAdminOrderListAfter` | Avant/Après le rendu du tableau de la liste des commandes. | Moins probable pour ce module, car il modifie la liste elle-même, et non seulement ajoute du contenu autour d'elle. |

La méthode `install()` du module enregistrerait ces hooks, et la méthode `hookDisplayBackOfficeHeader()` (ou similaire) contiendrait la logique pour récupérer la configuration stockée et générer le CSS/JS nécessaire pour masquer les colonnes sélectionnées lorsque la page `AdminOrders` est chargée.

## 5. Support officiel et mises à jour

Pour les dernières mises à jour, corrections de bugs et support officiel du module « Order Grid Manager Free », veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu/my-account/orders/). Notre équipe de support est disponible pour vous aider avec toutes les questions ou problèmes que vous pourriez rencontrer concernant la fonctionnalité du module.
