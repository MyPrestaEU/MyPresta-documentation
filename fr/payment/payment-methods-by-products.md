---
title: "Moyens de paiement par produit - documentation et manuel du vendeur"
description: "Ce manuel sert à fixer les moyens de paiement par produit, à les combiner dans le panier et à corriger une caisse qui affiche encore le mauvais moyen."
sidebar:
  label: "Moyens de paiement par produit - documentation et manuel du vendeur"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Payment methods by products sur MyPresta.eu](https://mypresta.eu/modules/payment-process/payment-methods-by-products.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/payment/payment-methods-by-products/)
>
> ---


## 1. Prérequis

Vérifiez ces points avant l’installation.

- Utilisez PrestaShop 1.7.0.0 ou plus récent, y compris PrestaShop 8 et 9. Le module accepte les versions de boutique jusqu’à 9.99.99.
- Gardez la version de PHP exigée par cette version de PrestaShop. L’installateur ne contrôle pas PHP à part.
- Activez l’extension PHP cURL si le contrôle de mise à jour doit joindre MyPresta.eu. Sans cURL, le contrôle tente d’ouvrir l’adresse avec le réglage serveur qui autorise les lectures distantes. Les règles de paiement n’ont pas besoin de cURL.
- Aucun autre module PrestaShop n’est requis. La liste des moyens vient des modules de paiement déjà installés. S’il n’y en a aucun, les cases sont vides.
- Installez et activez au moins un module de paiement si un moyen doit apparaître à la caisse.
- Le module ne demande pas de compte externe.

Les textes du module dans le back-office sont en anglais. Seul le polonais est livré. Les noms de ce guide sont les équivalents français de ces libellés anglais.

## 2. Installation

1. Ouvrez **Modules**, puis **Gestionnaire de modules**.
2. Cliquez sur **Installer un module** et envoyez le fichier ZIP.
3. Cliquez sur **Installer** pour **Payment options by products**.

L’installation fait ceci :

- Elle ajoute **Payment - Product associations** sous **Améliorer**, puis **Paiement**. Si ce menu manque, l’entrée est placée sous **Améliorer**.
- Elle crée la table. Une ligne est un produit, un module de paiement, une boutique et un pays.
- Elle enregistre le filtre de caisse et l’onglet de la fiche produit.
- Elle copie la surcharge de la caisse. PrestaShop doit autoriser les surcharges. Si elles sont coupées, l’onglet produit et le filtre de caisse fonctionnent quand même. L’avertissement jaune de la configuration le dit.
- Elle ne vide pas le cache de la boutique. Videz-le dans **Paramètres avancés**, **Performances**, seulement si un ancien écran reste affiché.
- Elle ne crée aucune règle. La caisse ne change pas tant que vous n’enregistrez pas une règle.

**Configurer** dans le **Gestionnaire de modules** ouvre les réglages. L’entrée **Payment - Product associations** ouvre la liste des règles.

Désinstallation :

- Retire l’entrée **Payment - Product associations**.
- Retire la surcharge de caisse et les hooks enregistrés.
- Retire la version enregistrée utilisée par la mise à jour.
- Ne supprime pas les règles produit. Une nouvelle installation relit ces lignes.
- Ne coupe pas les avis de mise à jour communs aux autres modules MyPresta.
- Laisse le dossier du module tant que vous ne le supprimez pas dans le **Gestionnaire de modules** ou sur le serveur.

Désactiver le module dans le **Gestionnaire de modules** arrête le filtre de caisse. Les règles restent dans la base.

## 3. Configuration et travail dans le back-office

Une règle est une liste de moyens de paiement pour un produit, dans la boutique que vous modifiez, pour un pays de livraison ou pour tous les pays.

Suivez cet ordre :

1. Ouvrez **Configurer** et choisissez comment plusieurs produits restreints se combinent dans un même panier. Cliquez sur **Save**. Cette étape est facultative. Tant que vous n’enregistrez pas, la boutique garde chaque moyen autorisé par au moins un produit restreint.
2. Ouvrez un produit et l’onglet **Payment methods**, ou **Améliorer**, **Paiement**, **Payment - Product associations**, et ajoutez une ligne.
3. Cochez les moyens qui doivent rester disponibles quand ce produit est dans le panier. Choisissez **All countries** ou un pays. Enregistrez.
4. À la caisse, la boutique lit l’adresse de livraison et masque les moyens que les règles n’autorisent pas.

Un produit sans règle enregistrée ne retire aucun moyen. **Free order** reste quand c’est le seul moyen d’un panier à zéro.

Il n’y a pas de statut de commande. Le résultat est la liste de paiement sur la page de caisse.

Les captures de ce chapitre montrent le back-office en anglais. La légende donne le nom de ce manuel.

### 3.1 Configuration du module

Ouvrez **Modules**, **Gestionnaire de modules**, **Payment options by products**, **Configurer**.

Deux notes sont en haut. Le premier lien ouvre **Payment - Product associations**. La seconde indique l’onglet **Payment methods** du produit. Aucune des deux n’enregistre une règle.

Si les surcharges sont coupées, l’avertissement jaune dit : « Overrides are disabled. Checkout filtering still runs through the payment options hook. » Laissez-les coupées si vous n’utilisez que PrestaShop 8 ou 9. Activez-les dans **Paramètres avancés**, **Performances**, seulement si vous avez aussi besoin de l’ancienne surcharge de caisse.

Le panneau **Settings** explique la règle de pays et le mode de combinaison. Le texte au-dessus de la liste ne se sauvegarde pas tout seul.

![Settings](https://mypresta.eu/docs/images/docs/pobp-configure-settings.webp)

**Configurer**, panneau **Settings**. Le texte bleu explique les pays. La liste est **How to get available payment methods?**.

| Champ | Au départ | Effet |
|---|---|---|
| **How to get available payment methods?** | **Show all payment methods from products**, tant que vous n’enregistrez pas un autre choix | **Show the same payment methods available for all products in cart** garde un moyen seulement si chaque produit restreint du panier l’autorise. **Show all payment methods from products** le garde si au moins un produit restreint l’autorise. Un produit sans règle ne retire aucun moyen. |
| **Save** | — | Enregistre seulement ce choix. Il ne modifie pas une règle produit. La page se recharge avec la valeur choisie. |

### 3.2 Payment - Product associations

Ouvrez **Améliorer**, **Paiement**, **Payment - Product associations**. La note du haut rappelle que la même règle est sur le produit, dans l’onglet **Payment methods**.

La liste montre une ligne par produit de la boutique en cours.

![Payment - Product associations](https://mypresta.eu/docs/images/docs/pobp-associations-list.webp)

**Payment - Product associations** sans ligne. Les colonnes sont **ID**, **Product**, **Payment** et **Country**. Le signe plus est **Add new**.

| Colonne | Contenu |
|---|---|
| **ID** | Le numéro de ligne. Ce n’est pas le numéro de produit. |
| **Product** | Numéro et nom du produit. |
| **Payment** | Chaque moyen enregistré pour ce produit, l’un sous l’autre. |
| **Country** | **All countries**, ou le pays de livraison enregistré. Le texte de colonne dit qu’un pays choisi ne s’applique que si l’adresse de livraison est dans ce pays, et que **All countries** s’applique à toute adresse. |

**Add new** ouvre un formulaire vide. **Edit** ouvre le formulaire de ce produit. **Delete** supprime cette seule ligne de base, pas chaque moyen listé dans **Payment**. **Delete selected** fait de même pour les lignes cochées. Ce formulaire refuse une sélection vide. Supprimez les lignes restantes, ou videz la règle dans l’onglet produit, où une sélection vide est permise.

La recherche et les filtres de la liste sont les filtres habituels du back-office pour ces colonnes.

### 3.3 Formulaire d’association

Sur **Add new** ou **Edit** :

![Formulaire d’association](https://mypresta.eu/docs/images/docs/pobp-associations-form.webp)

**Add new**, rempli pour cette image et non enregistré. **ID Product** vaut 1. Le formulaire montre **Payment methods** et **Country** (**All countries**).

| Champ | Au départ | Effet |
|---|---|---|
| **ID Product** | Vide sur une nouvelle ligne. Rempli en modification. | Saisissez le numéro de produit ou utilisez **Search**. L’aide dit de chercher par nom, ID ou référence. **Save** sans produit affiche « Product is required. » et n’écrit pas de règle. |
| **Payment methods** | Non cochés sur une nouvelle ligne. En modification, les moyens déjà enregistrés sont cochés. | Cochez les moyens qui restent à la caisse quand le panier contient ce produit et que le pays de livraison correspond au pays en dessous. Le libellé montre le nom du module de paiement. |
| **Country** | **All countries** | Si vous choisissez un pays, les moyens cochés ne s’appliquent que lorsque l’adresse de livraison du client est dans ce pays. **All countries** les applique à toute adresse. |
| **Save** | — | Remplace tous les moyens enregistrés pour ce produit dans la boutique en cours par les cases et le pays de ce formulaire. Si rien n’est coché, la page affiche « There was a problem with form. No payment method selected » et les anciennes lignes restent. |

Un produit a un pays. Un nouvel enregistrement remplace les moyens précédents de ce produit dans cette boutique. Les règles d’une autre boutique restent. Changez le contexte de boutique avant d’y modifier.

### 3.4 Fiche produit

Ouvrez **Catalogue**, **Produits**, modifiez le produit, puis l’onglet **Payment methods**.

![Payment methods sur le produit](https://mypresta.eu/docs/images/docs/pobp-product-tab.webp)

Produit Hummingbird printed t-shirt, onglet **Payment methods**. On y voit **Country** et **Available payment methods**. Les coches sont seulement sur l’image. Le produit n’a pas été enregistré.

| Champ | Au départ | Effet |
|---|---|---|
| **Country** | **All countries** si le produit n’a pas de règle. Sinon le pays déjà enregistré. | Si vous choisissez un pays, les moyens cochés ne s’appliquent que si l’adresse de livraison est dans ce pays. **All countries** les applique à toute adresse. |
| **Available payment methods** | Non cochés s’il n’y a pas de règle. Sinon les moyens déjà enregistrés sont cochés. | Les moyens cochés restent à la caisse quand le panier contient ce produit et que le pays de livraison correspond au pays au-dessus. Ne rien cocher retire la restriction de ce produit. |

Cliquez sur **Save** du produit. PrestaShop confirme l’enregistrement du produit. La règle de paiement est écrite avec cet enregistrement, pour la boutique que vous modifiez. Une sélection vide supprime la règle de ce produit dans cette boutique. Le formulaire d’association, lui, refuse d’enregistrer si rien n’est coché.

Les mêmes données figurent dans **Payment - Product associations**.

### 3.5 Mises à jour MyPresta

Dans **Configurer**, sous les réglages, **MyPresta Updates** vérifie s’il existe un fichier plus récent. Il ne l’installe pas.

![MyPresta Updates](https://mypresta.eu/docs/images/docs/pobp-updates.webp)

**MyPresta Updates**, sous les réglages dans **Configurer**.

| Champ | Au départ | Effet |
|---|---|---|
| **Check updates** | — | **Check now** demande à MyPresta.eu s’il existe un fichier plus récent. La ligne au-dessus du bouton indique une nouvelle version ou que le module est à jour. Il ne télécharge ni n’installe le fichier. |
| **Updates notifications** | Activées, tant que vous n’enregistrez pas **Disable** | **Enable** affiche un avertissement dans le back-office quand une version plus récente est publiée. **Disable** arrête ce contrôle automatique. **Save** enregistre le choix et affiche « Update settings saved. » |
| **Module page** | — | Ouvre la page du module sur MyPresta.eu, où se trouve le journal des changements. N’enregistre aucun réglage. |
| **Save** | — | Enregistre seulement **Updates notifications**. |

## 4. Boutique

Le module n’ajoute ni bloc, ni page, ni message sur le produit, le panier ou le compte client. Le thème n’a rien à modifier à ces endroits.

Le client voit l’effet à l’étape de paiement de la caisse. Les moyens que les règles n’autorisent pas sont absents de la liste. Les moyens sans règle, et **Free order** quand c’est le seul choix, restent.

Le pays est celui de l’adresse de livraison. Avant qu’une adresse existe, seules les règles **All countries** s’appliquent. Une règle pour un pays attend que l’adresse soit dans ce pays.

## 5. Problèmes

**La liste de paiement n’a pas changé.** Le produit n’a pas de règle, ou aucun produit du panier n’en a. Ouvrez le produit, **Payment methods**, cochez les moyens et enregistrez le produit. Un produit sans case cochée ne limite pas la caisse.

**Un moyen a disparu pour un seul pays.** Le pays de la règle n’est pas **All countries**, et l’adresse de livraison est dans ce pays. Mettez **All countries** si la règle doit valoir pour toute adresse.

**Un moyen est encore proposé.** Un autre produit du panier l’autorise, et **How to get available payment methods?** est sur **Show all payment methods from products**. Passez à **Show the same payment methods available for all products in cart** si chaque produit restreint doit autoriser le moyen. Un produit sans règle ne le bloque pas.

**La configuration affiche « Overrides are disabled… » et vous ne savez pas si le filtre tourne.** Sous PrestaShop 8 et 9, le filtre continue. Le texte jaune dit que le hook de caisse filtre. Activez les surcharges seulement si vous comptez aussi sur l’ancien fichier.

**Save dans Payment - Product associations affiche « Product is required. »** Le champ produit est vide. Cherchez le produit ou saisissez son numéro, puis cliquez de nouveau sur **Save**.

**Save affiche « There was a problem with form. No payment method selected ».** Aucun moyen n’est coché. Cochez-en au moins un. L’ancienne règle n’a pas été remplacée. Pour retirer une règle entièrement, utilisez l’onglet **Payment methods** du produit et enregistrez sans coche.

**Delete dans la liste n’a retiré qu’un moyen.** **Delete** supprime la seule ligne de cette entrée, alors que **Payment** liste tous les moyens. Ouvrez **Edit** et **Save** pour réécrire l’ensemble, ou supprimez jusqu’à ce que le produit disparaisse de la liste.

**Free order est le seul moyen et la règle ne le contient pas.** Un panier à zéro garde **Free order**. Le module ne retire pas ce moyen unique.

**La règle d’une boutique manque dans une autre.** Les règles sont enregistrées par boutique. Changez de boutique dans l’en-tête multiboutique et enregistrez la règle là.

## 6. Pour le développeur

### 6.1 Vue d’ensemble

Classe principale `pobp`, version `1.4.0`, nom **Payment options by products**, auteur MyPresta.eu, onglet `administration`. Compatibilité de `1.7.0.0` à `9.99.99`.

Une ligne de `ps_pobp` est un module de paiement autorisé pour un produit, une boutique et un pays (`id_country` `0` signifie tous les pays). La caisse lit les produits du panier et l’adresse de livraison dans `pobp::filterPaymentOptions()`. Le hook `actionPresentPaymentOptions` retire les clés écartées par le filtre. La surcharge `PaymentOptionsFinder::find()` renvoie le même filtre si le module est actif. `pobp_innerjoin` vrai signifie l’intersection des produits restreints. Toute autre valeur, y compris une clé absente, signifie l’union. Les produits sans ligne correspondante sont ignorés. La clé `free_order` n’est jamais retirée. Une liste qui ne contient que `free_order` est renvoyée telle quelle.

### 6.2 Fichiers

| Fichier | Rôle |
|---|---|
| `pobp.php` | Installation, formulaire de réglages, filtre de caisse, onglet produit. |
| `lib/updatesChecker.php` | Classe `pobpUpdate`. Contrôle de mise à jour et formulaire MyPresta Updates. |
| `lib/searchTool/searchTool.php` | Recherche produit dans le formulaire d’association. |
| `models/pob.php` | ObjectModel `pob` et `replaceForProduct()`. |
| `controllers/admin/AdminPobpController.php` | Liste et formulaire des associations. |
| `override/classes/checkout/PaymentOptionsFinder.php` | `find()` appelle `filterPaymentOptions()`. |
| `upgrade/upgrade-1.4.0.php` | Appelle `ensureModuleComplements()` et enregistre `POBP_VERSION`. |
| `translations/pl.php` | Textes polonais. |

Il n’y a ni contrôleur ni modèle de front.

### 6.3 Contrôleurs

`AdminPobpController` étend `ModuleAdminController`. Classe d’onglet `AdminPobp`, parent `AdminParentPayment`, ou `IMPROVE` si ce parent manque. Icône `credit_card`. Nom visible **Payment - Product associations**.

La liste groupe par une sous-requête `MIN(id_pobp)` par produit et boutique. `processAdd()` et `processUpdate()` appellent `pob::replaceForProduct()`. Un ensemble vide ou un produit absent renvoie false et ne remplace pas les lignes. Les textes passent par `$this->module->l(..., 'AdminPobpController')`.

La configuration du module est `getContent()` de `pobp`, pas un contrôleur séparé.

### 6.4 Hooks

Enregistrés dans `registerHooks()` :

| Hook | Rôle |
|---|---|
| `actionPresentPaymentOptions` | Retire les modules de paiement écartés par le filtre. Le tableau est modifié sur place. |
| `actionProductFormBuilderModifier` | Ajoute l’onglet `pobp` (pays et paiements) au formulaire produit. |
| `actionAfterUpdateProductFormHandler` | Écrit `form_data['pobp']` pour le produit enregistré. |
| `actionAfterCreateProductFormHandler` | La même écriture après la création d’un produit. |

Il n’y a pas de `enable()` ni de `disable()` propres. Désactiver le module retire les hooks. La surcharge se charge encore et renvoie la liste parente quand `Module::isEnabled('pobp')` est faux.

Le premier chargement du back-office après un envoi de fichiers appelle `ensureModuleComplements()` si `POBP_VERSION` diffère de la version du fichier.

### 6.5 Surcharges

`override/classes/checkout/PaymentOptionsFinder.php` ne remplace que `find()`. Il ne surcharge ni `present()` ni `findFree()`.

### 6.6 Base de données

| Table | Contenu |
|---|---|
| `ps_pobp` | `id_pobp`, `id_product`, `id_payment` (id du module), `id_shop`, `id_country`. `inconsistency()` ajoute `id_country` si la colonne manque. `0` signifie tous les pays. |

La désinstallation ne supprime pas `ps_pobp`. L’installation utilise `CREATE TABLE IF NOT EXISTS` : une nouvelle installation conserve les anciennes lignes.

### 6.7 Clés et traductions

| Clé | Si elle manque |
|---|---|
| `pobp_innerjoin` | Traitée comme inactive. La caisse utilise l’union des produits restreints. |
| `POBP_VERSION` | La requête back-office suivante lance `ensureModuleComplements()` puis enregistre la version du fichier. |
| `mypresta_updates` | Traitée comme active. `0` arrête le contrôle automatique. La clé est partagée avec d’autres modules MyPresta. |
| `update_pobp` | Horodatage du dernier contrôle. |
| `updatev_pobp` | Chaîne de version renvoyée par le serveur de mise à jour. |

Les textes boutique passent par `$this->l()`. Le panneau de mise à jour utilise la source `updatesChecker`. Le contrôleur d’association utilise `AdminPobpController`. Le polonais est dans `translations/pl.php`. Ajoutez une langue comme `translations/{iso}.php` avec la même forme de clé.

`key.php` dans le dossier du module peut fixer `$this->mkey`. Si le fichier manque, le contrôle envoie `nlc`.

### 6.8 Extension

Le front ne rend pas de modèle du module : le thème n’a rien à surcharger. Pour changer la liste de caisse, restez sur le hook des options de paiement ou sur la surcharge de `PaymentOptionsFinder`. Pour changer l’onglet produit, étendez `hookActionProductFormBuilderModifier` et gardez les clés de formulaire `pobp`, sinon le hook d’enregistrement ignore les données.

## 7. Aide

Page du module : [https://mypresta.eu/modules/payment-process/payment-methods-by-products.html](https://mypresta.eu/modules/payment-process/payment-methods-by-products.html)

Pour écrire au sujet de ce module, connectez-vous à votre compte client sur mypresta.eu, ouvrez le formulaire de contact et choisissez le sujet **Support for paid modules**. Le formulaire indique que la connexion est obligatoire pour ce sujet. Une fois connecté, choisissez ce module dans l’historique d’achat.
