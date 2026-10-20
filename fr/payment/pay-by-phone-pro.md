---
title: "Pay By Phone Pro - Manuel du Marchand et Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop Pay By Phone Pro par MyPresta.eu."
sidebar:
  label: "Pay By Phone Pro - Manuel du Marchand et Guide de Configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Pay By Phone Pro sur MyPresta.eu](https://mypresta.eu/modules/payment-process/pay-by-phone-pro.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/payment/pay-by-phone-pro/)
>
> ---


# Pay By Phone Pro

## 1. Exigences et compatibilité

- **Versions PrestaShop prises en charge** : PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilité PHP** : PHP 5.6 - 8.5
- **Exigences d'hébergement** : Les extensions PHP standard (cURL, JSON, OpenSSL) sont généralement requises pour PrestaShop lui-même, et ce module n'a pas d'exigences spécifiques supplémentaires au-delà d'un environnement d'hébergement PrestaShop standard.

## 2. Guide de configuration complet (chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer > Pay By Phone Pro)

C'est l'écran de configuration principal où vous définissez comment la méthode de paiement « Pay By Phone Pro » apparaît et se comporte dans votre boutique.

- **Emplacement du menu :** Back Office > Modules > Gestionnaire de modules > Rechercher « Pay By Phone Pro » > Cliquer sur « Configurer ».

#### Paramètres et options

1. **Titre de la méthode de paiement**

   - **Ce que fait ce paramètre :** C'est le nom de la méthode de paiement que vos clients verront lors de la commande. C'est ce qui apparaît dans la liste des options de paiement.
   - **Effet de la modification de ce paramètre :**
     - *Si défini sur « Payer par téléphone » :* Les clients verront « Payer par téléphone » comme option.
     - *Si défini sur « Appelez-nous pour payer » :* Les clients verront « Appelez-nous pour payer » comme option.
   - **Valeur recommandée :** Quelque chose de clair et professionnel, comme « Payer par téléphone » ou « Appeler pour finaliser la commande ».
   - **Scénario / exemple de marchand :** Si vous souhaitez mettre l'accent sur le contact direct, vous pourriez utiliser « Appelez notre équipe de vente pour payer ». Si vous voulez que cela ressemble plus à une option de paiement standard, « Payer par téléphone » est préférable.
2. **Description de la méthode de paiement**

   - **Ce que fait ce paramètre :** C'est une courte description qui apparaît sous le titre de la méthode de paiement lors de la commande. Elle explique au client ce qu'implique cette méthode de paiement.
   - **Effet de la modification de ce paramètre :**
     - *Si défini sur « Appelez-nous pour fournir vos coordonnées de carte de crédit et finaliser votre commande. » :* Ce texte apparaîtra, guidant le client sur les étapes suivantes.
     - *Si défini sur « Contactez notre service client pour discuter des options de paiement. » :* Ce texte alternatif sera affiché.
   - **Valeur recommandée :** Indiquez clairement ce que le client doit faire, par exemple, « Veuillez nous appeler au [Votre numéro de téléphone] pour finaliser votre paiement et les détails de votre commande. »
   - **Scénario / exemple de marchand :** Vous pourriez écrire : « Après avoir passé votre commande, veuillez nous appeler au +1-800-123-4567 pendant les heures de bureau pour finaliser votre paiement. Ayez votre numéro de commande à portée de main. »
3. **Instructions pour le client sur la page de confirmation de commande**

   - **Ce que fait ce paramètre :** C'est un message plus détaillé affiché au client sur la page de confirmation de commande *après* qu'il ait sélectionné « Pay By Phone Pro » et passé sa commande. C'est là que vous fournissez des instructions spécifiques.
   - **Effet de la modification de ce paramètre :**
     - *Si défini sur « Merci pour votre commande. Veuillez nous appeler pour finaliser votre paiement. » :* Ce message sera affiché.
     - *Si défini sur « Votre commande est en attente. Veuillez contacter notre équipe de support avec votre numéro de commande pour organiser le paiement. » :* Ce message alternatif sera affiché.
   - **Valeur recommandée :** Incluez votre numéro de téléphone, les heures d'ouverture et les informations que le client doit avoir à portée de main (par exemple, le numéro de commande).
   - **Scénario / exemple de marchand :** « Votre commande #12345 a été passée. Veuillez appeler notre équipe de vente au +1-800-123-4567 (du lundi au vendredi, de 9h à 17h HNE) dans les 24 heures pour fournir les détails de paiement. Veuillez avoir votre numéro de commande à portée de main. »
4. **Statut de la commande pour les paiements en attente**

   - **Ce que fait ce paramètre :** Cela détermine le statut initial d'une commande passée à l'aide de « Pay By Phone Pro » dans votre Back Office PrestaShop. Ce statut indique que le paiement n'est pas encore terminé et nécessite votre action.
   - **Effet de la modification de ce paramètre :**
     - *Si défini sur « En attente de virement bancaire » :* Les commandes apparaîtront avec ce statut.
     - *Si défini sur « Paiement accepté » :* (Non recommandé pour ce module) Cela marquerait incorrectement la commande comme payée avant que vous ne l'ayez traitée.
   - **Valeur recommandée :** Choisissez un statut qui indique clairement « paiement en attente » ou « en attente de paiement ». Les choix courants sont « En attente de virement bancaire », « Paiement en attente » ou « En attente de paiement par chèque ». Si vous avez un statut de commande personnalisé comme « En attente de paiement par téléphone », ce serait idéal.
   - **Scénario / exemple de marchand :** La sélection de « En attente de virement bancaire » garantit que ces commandes sont facilement identifiables dans votre liste de commandes comme nécessitant un traitement manuel du paiement.
5. **Activer pour des pays spécifiques**

   - **Ce que fait ce paramètre :** Vous permet de restreindre cette méthode de paiement aux clients de certains pays uniquement. Si laissé vide, il sera disponible pour tous les pays.
   - **Effet de la modification de ce paramètre :**
     - *Lorsque des pays spécifiques sont sélectionnés (par exemple, « États-Unis », « Canada ») :* Seuls les clients ayant une adresse de facturation dans ces pays verront « Pay By Phone Pro » comme option.
     - *Lorsque aucun pays n'est sélectionné :* La méthode de paiement est disponible dans le monde entier.
   - **Valeur recommandée :** Laissez vide si vous souhaitez l'offrir dans le monde entier, ou sélectionnez des pays spécifiques si vous avez des limitations opérationnelles (par exemple, support téléphonique uniquement dans certaines régions).
   - **Scénario / exemple de marchand :** Si votre support téléphonique n'est disponible qu'en anglais et que vous n'expédiez qu'aux États-Unis et au Canada, vous sélectionneriez « États-Unis » et « Canada » pour éviter de l'offrir à des clients que vous ne pouvez pas servir.
6. **Activer pour des devises spécifiques**

   - **Ce que fait ce paramètre :** Vous permet de restreindre cette méthode de paiement aux clients payant dans des devises spécifiques. Si laissé vide, il sera disponible pour toutes les devises.
   - **Effet de la modification de ce paramètre :**
     - *Lorsque des devises spécifiques sont sélectionnées (par exemple, « USD », « EUR ») :* Seuls les clients payant dans ces devises verront « Pay By Phone Pro ».
     - *Lorsque aucune devise n'est sélectionnée :* La méthode de paiement est disponible pour toutes les devises configurées dans votre boutique.
   - **Valeur recommandée :** Laissez vide si vous prenez en charge toutes les devises, ou sélectionnez des devises spécifiques si votre système de traitement manuel des paiements a des limitations de devise.
   - **Scénario / exemple de marchand :** Si votre terminal de carte de crédit ne traite que l'USD et l'EUR, vous sélectionneriez ces deux devises.
7. **Activer pour des groupes de clients spécifiques**

   - **Ce que fait ce paramètre :** Vous permet de restreindre cette méthode de paiement à certains groupes de clients (par exemple, « Invités », « Clients », « Grossistes »). Si laissé vide, il sera disponible pour tous les groupes de clients.
   - **Effet de la modification de ce paramètre :**
     - *Lorsque des groupes spécifiques sont sélectionnés (par exemple, « Grossistes ») :* Seuls les clients appartenant au groupe « Grossistes » verront cette option de paiement.
     - *Lorsque aucun groupe n'est sélectionné :* La méthode de paiement est disponible pour tous les groupes de clients.
   - **Valeur recommandée :** Laissez vide pour une utilisation générale, ou sélectionnez des groupes spécifiques si cette méthode de paiement fait partie d'un arrangement spécial (par exemple, pour les VIP ou les clients B2B).
   - **Scénario / exemple de marchand :** Vous pourriez l'offrir uniquement à votre groupe de clients « Grossistes », car ils ont souvent des conditions de paiement personnalisées qui nécessitent une discussion directe.

#### Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Valeur par défaut / Recommandée | Objectif et impact |
| --- | --- | --- | --- |
| Configuration du module | Titre de la méthode de paiement | « Payer par téléphone » | Nom affiché aux clients lors de la commande. |
| Configuration du module | Description de la méthode de paiement | « Appelez-nous pour fournir vos coordonnées de carte de crédit et finaliser votre commande. » | Courte explication sous le titre du paiement. |
| Configuration du module | Instructions pour le client sur la page de confirmation de commande | « Merci pour votre commande. Veuillez nous appeler pour finaliser votre paiement. » | Instructions détaillées sur la page de confirmation de commande. |
| Configuration du module | Statut de la commande pour les paiements en attente | « En attente de virement bancaire » (ou statut similaire en attente) | Statut initial des commandes passées avec cette méthode. |
| Configuration du module | Activer pour des pays spécifiques | Vide (Tous les pays) | Restreindre la méthode de paiement par pays du client. |
| Configuration du module | Activer pour des devises spécifiques | Vide (Toutes les devises) | Restreindre la méthode de paiement par devise sélectionnée. |
| Configuration du module | Activer pour des groupes de clients spécifiques | Vide (Tous les groupes) | Restreindre la méthode de paiement par groupe de clients. |

## 3. Dépannage du marchand et questions fréquemment posées (FAQ)

**Q1 : L'option « Pay By Phone Pro » n'apparaît pas lors de la commande.**
R :

- **Vérifier le statut du module :** Allez dans **Modules > Gestionnaire de modules** et assurez-vous que « Pay By Phone Pro » est installé et activé.
- **Paramètres de configuration :** Vérifiez les paramètres « Activer pour des pays spécifiques », « Activer pour des devises spécifiques » et « Activer pour des groupes de clients spécifiques ». Si vous avez restreint le module, assurez-vous que le client/panier de test actuel répond à ces critères.
- **Cache :** Videz votre cache PrestaShop sous **Paramètres avancés > Performance**. Parfois, un ancien cache empêche l'apparition de nouveaux modules ou paramètres.
- **Compatibilité du thème :** Bien que rare, un thème fortement personnalisé pourrait interférer. Basculez temporairement vers un thème PrestaShop par défaut (par exemple, Classic) pour exclure les conflits de thème.

**Q2 : Comment modifier le texte que les clients voient pour cette méthode de paiement ?**
R : Tout le texte visible par le client (titre, description et instructions de confirmation) peut être personnalisé directement depuis la page de configuration du module dans votre Back Office. Naviguez vers **Modules > Gestionnaire de modules**, recherchez « Pay By Phone Pro » et cliquez sur « Configurer ». Vous trouverez des champs tels que « Titre de la méthode de paiement », « Description de la méthode de paiement » et « Instructions pour le client sur la page de confirmation de commande ». N'oubliez pas d'enregistrer vos modifications.

**Q3 : Que se passe-t-il si un client passe une commande en utilisant « Pay By Phone Pro » mais n'appelle jamais ?**
R : La commande restera dans le statut « paiement en attente » que vous avez configuré (par exemple, « En attente de virement bancaire »). Vous devrez surveiller ces commandes dans votre Back Office. Vous pouvez configurer des rappels automatisés ou contacter manuellement le client après une certaine période (par exemple, 24 à 48 heures) pour faire un suivi. Si aucun contact n'est établi, vous devrez peut-être éventuellement annuler la commande.

**Q4 : Puis-je traduire le texte du module dans d'autres langues ?**
R : Oui, le système de traduction de PrestaShop gère les textes des modules. Allez dans **International > Traductions**, sélectionnez « Traductions des modules installés », choisissez votre thème, puis sélectionnez « Pay By Phone Pro ». Vous pouvez ensuite traduire tous les champs de texte configurables dans les langues actives de votre boutique.

**Q5 : Comment traiter le paiement une fois qu'un client appelle ?**
R : Ce module ne traite pas les paiements lui-même. Il facilite la passation de commande. Une fois qu'un client appelle, vous utiliserez vos méthodes de traitement de paiement hors ligne existantes (par exemple, un terminal de carte de crédit physique, un terminal virtuel fourni par votre banque ou l'enregistrement d'un virement bancaire) pour prendre ses détails de paiement et finaliser la transaction. Après un paiement réussi, vous devez mettre à jour manuellement le statut de la commande dans votre Back Office PrestaShop de « paiement en attente » à « Paiement accepté » (ou « Traitement en cours ») pour refléter le changement.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

Cette section fournit un aperçu technique détaillé du module « Pay By Phone Pro » pour les développeurs et les webmasters.

### 4.1 Aperçu de l'architecture

Le module « Pay By Phone Pro » suit une architecture de module PrestaShop standard, exploitant principalement `PaymentModule` pour sa fonctionnalité principale. Il s'intègre au flux de commande en enregistrant des hooks et en fournissant des contrôleurs frontaux pour l'exécution et la validation du paiement. La configuration est gérée via la méthode `getContent()` de la classe principale du module.

### 4.2 Contrôleurs (`controllers/`)

#### Contrôleurs Front-Office

Ces contrôleurs gèrent les aspects du processus de paiement visibles par le client.

- **`controllers/front/index.php`**

  - **Nom de la classe et classe parente :** `PayByPhoneIndexModuleFrontController` étendant `ModuleFrontController`.
  - **Responsabilité :** Ce contrôleur est généralement responsable de l'affichage du formulaire de paiement initial ou de la redirection vers la page d'exécution du paiement. Dans le contexte de ce module, il agit probablement comme une passerelle avant l'exécution réelle du paiement, potentiellement en configurant des données de session ou en redirigeant vers `payment_execution.tpl`.
- **`controllers/front/validation.php`**

  - **Nom de la classe et classe parente :** `PayByPhoneValidationModuleFrontController` étendant `ModuleFrontController`.
  - **Responsabilité :** C'est le contrôleur critique qui traite la commande après que le client a sélectionné « Pay By Phone Pro ». Il valide la commande, la crée dans la base de données PrestaShop avec le statut en attente configuré, puis redirige le client vers la page de confirmation de commande, affichant les instructions spécifiques. Il utilise la méthode `validateOrder` de la classe parente `PaymentModule`.

#### Contrôleurs d'administration Back-Office

Ce module n'inclut aucun contrôleur d'administration Back-Office personnalisé. Toute la configuration est gérée dans la méthode `getContent()` du module principal.

### 4.3 Classes et modèles de base (`classes/`)

Ce module ne contient aucune classe personnalisée ou définition `ObjectModel` dans le répertoire `classes/`. Il s'appuie sur les classes `PaymentModule` et `Configuration` de base de PrestaShop.

### 4.4 Actifs JavaScript (`views/js/`)

Ce module n'inclut aucun fichier JavaScript personnalisé. Sa fonctionnalité est principalement côté serveur et basée sur des modèles.

### 4.5 Feuilles de style CSS (`views/css/`)

- **`paybyphone/css/paybyphone.css`**
  - **Portée :** Style client Front-office.
  - **Principaux composants et conteneurs d'interface utilisateur qu'il stylise :** Cette feuille de style est probablement utilisée pour fournir un style de base pour l'apparence de la méthode de paiement lors de la commande, comme le bloc d'option de paiement, le texte de description ou tout élément spécifique dans les modèles `payment.tpl` ou `shopping-cart.tpl`.
  - **Sélecteurs de classe CSS clés que les développeurs peuvent remplacer :** Les développeurs peuvent inspecter le code HTML généré pour la méthode de paiement sur la page de commande afin d'identifier des classes spécifiques (par exemple, `.paybyphone-payment-option`, `.paybyphone-description`) à remplacer dans le `custom.css` de leur thème ou via les options de personnalisation du thème.

### 4.6 Structure des modèles Smarty (`views/templates/`)

#### Modèles de hook (`views/templates/hook/`)

Ces modèles sont rendus lorsque des hooks PrestaShop spécifiques sont exécutés.

- **`views/templates/hook/infos.tpl`**

  - **Hook :** Probablement `displayPaymentTop` ou similaire, fournissant des informations supplémentaires sur la méthode de paiement.
  - **Bloc visuel :** Pourrait être utilisé pour afficher un bloc d'informations générales sur l'option « Payer par téléphone », peut-être sur la page du produit ou dans une colonne, avant que le client n'atteigne la commande.
- **`views/templates/hook/payment.tpl`**

  - **Hook :** `displayPayment` (PrestaShop 1.6) ou `paymentOptions` (PrestaShop 1.7+).
  - **Bloc visuel :** C'est le modèle principal pour afficher l'option « Pay By Phone Pro » sur la page de sélection du paiement lors de la commande. Il contiendra le titre et la description de la méthode de paiement tels que configurés dans le Back Office.

#### Modèles d'administration (`views/templates/admin/`)

Ce module ne contient aucun modèle d'administration personnalisé. Le formulaire de configuration est probablement généré directement dans la méthode `getContent()` de `index.php` à l'aide de `HelperForm` de PrestaShop.

#### Modèles Front-office (`views/templates/front/`)

Ces modèles sont rendus par les contrôleurs frontaux du module.

- **`views/templates/front/payment_execution.tpl`**

  - **Objectif :** Ce modèle est probablement rendu par `PayByPhoneIndexModuleFrontController` ou directement après que le client a sélectionné la méthode de paiement. Il pourrait servir de page intermédiaire ou d'étape de confirmation avant la validation finale, affichant potentiellement un bouton « Confirmer la commande ».
- **`views/templates/front/shopping-cart.tpl`**

  - **Objectif :** Ce modèle est probablement un fallback ou un affichage alternatif pour l'option de paiement dans le résumé du panier, éventuellement pour les anciennes versions de PrestaShop ou des intégrations de thème spécifiques. Il présenterait l'option « Payer par téléphone » avant le début du processus de commande complet.
- **`views/templates/front/validation.tpl`**

  - **Objectif :** C'est le modèle de la page de confirmation de commande, rendu après que `PayByPhoneValidationModuleFrontController` a validé et créé la commande avec succès. Il affiche le texte « Instructions pour le client sur la page de confirmation de commande », ainsi qu'un résumé de la commande.

### 4.7 Schéma de la base de données et carte des hooks

#### Tables de la base de données

Le module « Pay By Phone Pro » ne crée aucune table de base de données personnalisée. Il stocke ses paramètres de configuration dans la table `ps_configuration` de PrestaShop en utilisant des clés telles que `PAYBYPHONE_TITLE`, `PAYBYPHONE_DESCRIPTION`, `PAYBYPHONE_INSTRUCTIONS`, `PAYBYPHONE_ORDER_STATUS`, `PAYBYPHONE_COUNTRIES`, `PAYBYPHONE_CURRENCIES` et `PAYBYPHONE_GROUPS`.

#### Tableau des hooks enregistrés

| Nom du hook | Moment d'exécution | Objectif technique |
| --- | --- | --- |
| `displayPayment` (PrestaShop 1.6) | Sur la page de sélection du paiement lors de la commande. | Affiche l'option de paiement « Pay By Phone Pro ». |
| `paymentOptions` (PrestaShop 1.7+) | Sur la page de sélection du paiement lors de la commande. | Affiche l'option de paiement « Pay By Phone Pro » (hook moderne). |
| `displayPaymentReturn` | Sur la page de confirmation de commande après le paiement. | Affiche les instructions spécifiques pour que le client appelle. |
| `displayHeader` | Dans la section `<head>` de chaque page du Front-office. | Potentiellement utilisé pour charger des fichiers CSS (`paybyphone.css`). |
| `displayLeftColumn` / `displayRightColumn` / `displayFooter` | Dans les zones de colonne/pied de page respectives. | Pourrait être utilisé pour afficher des blocs d'informations sur la méthode de paiement (via `infos.tpl`). |
| `actionValidateOrder` | Après qu'une commande a été validée et créée avec succès. | Permet au module d'effectuer des actions supplémentaires ou de la journalisation après la création de la commande (par exemple, la définition de détails de commande spécifiques). |

## 5. Support officiel et mises à jour

Pour les dernières mises à jour, corrections de bugs et support professionnel pour le module « Pay By Phone Pro », veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu/my-account/orders/). Notre équipe s'engage à assurer le bon fonctionnement et la compatibilité continue de nos modules avec les dernières versions de PrestaShop.
