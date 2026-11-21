---
title: "MyFAQ Free - documentation et manuel d'utilisation"
sidebar:
  label: "MyFAQ Free - documentation et manuel d'utilisation"
description: Manuel de configuration et de dépannage pour les boutiques qui ont déjà MyFAQ Free.
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Free Product FAQ sur MyPresta.eu](https://mypresta.eu/modules/front-office-features/free-product-faq.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/front-office/free-product-faq/)
>
> ---


## 1. Prérequis

MyFAQ Free tourne dans PrestaShop. Il n'a pas besoin d'un autre module.

- PrestaShop 1.7.0.0 jusqu'à PrestaShop 9.
- La version de PHP exigée par cette version de PrestaShop. Le module ne vérifie pas lui-même la version de PHP.
- Aucune extension PHP supplémentaire n'est exigée. La vérification des mises à jour utilise cURL quand le serveur l'a. Sans cURL, la vérification lit l'adresse seulement si le serveur autorise les lectures distantes.
- Aucun autre module n'est exigé. La page produit du thème doit imprimer le pied de produit ou les onglets produit supplémentaires pour que le client voie les questions.
- Écrire et afficher les trois questions ne demande pas de compte chez un service externe. Le don PayPal sur la page de configuration est facultatif. La vérification des mises à jour demande seulement que la boutique atteigne MyPresta.eu.

Chaque produit garde trois questions. Il n'y a pas d'import, donc un grand catalogue ne lance pas de lot et n'augmente pas la mémoire que le module demande.

## 2. Installation

1. Dans le back-office, ouvrez **Modules**, puis **Gestionnaire de modules**.
2. Envoyez le zip et cliquez sur **Installer**.
3. Ouvrez **Configurer** sur **MyFAQ Free**. La page s'ouvre sur **Unlock Pro**. La barre a aussi **Settings** et **Updates**.
4. MyFAQ Free n'ajoute pas d'entrée dans le menu de gauche. Les questions s'écrivent sur chaque produit.

L'installation ne vide pas le cache PrestaShop. Si la page produit garde l'ancienne mise en page après une mise à jour, videz le cache dans **Paramètres avancés**, **Performances**.

Pour l'éteindre, utilisez l'interrupteur du **Gestionnaire de modules**. La page produit n'imprime plus les questions, et la fiche produit ne montre plus le bloc FAQ. Les questions et le placement restent. Rallumez le module et ils servent comme avant. Le module n'a pas son propre bouton d'activation ou de désactivation.

Pour le retirer, cliquez sur **Désinstaller** et confirmez. La désinstallation retire les questions, le placement, le titre d'onglet et le titre. La page cachée qui enregistre les questions disparaît. Les fichiers du module restent sur le serveur jusqu'à ce que vous supprimiez le module. Une nouvelle installation repart avec des questions vides, **Product footer**, le titre d'onglet FAQ et un titre vide. Les anciennes questions ne reviennent pas. L'interrupteur des alertes de mise à jour est partagé avec les autres modules MyPresta et reste comme vous l'avez laissé.

## 3. Configuration et travail quotidien

Les écrans de ce manuel sont en anglais. Ensuite j'utilise les noms de ce manuel et je cite le libellé tel qu'il apparaît dans le back-office.

Vous écrivez les questions sur le produit, pas sur la page du module. Ouvrez **Catalogue**, **Produits**, et modifiez le produit. Dans une boutique à plusieurs magasins, la page produit demande de choisir un magasin dans l'en-tête multiboutique. Ouvrez l'onglet **Modules**, et dans **Module to configure** choisissez **MyFAQ Free**. Saisissez jusqu'à trois questions, cochez **Show on the product page** et cliquez sur **Save these questions**. Un emplacement dont la question est vide reste hors de la page produit.

Sur la page du module, vous choisissez seulement où ce bloc s'imprime et comment il s'appelle. **Product footer** imprime l'accordéon sous le produit. **Product tab** ajoute un onglet produit et laisse le pied vide. Un produit sans question n'affiche rien à ces deux endroits.

Le client ouvre le produit, clique une question et lit la réponse. Il n'y a pas de formulaire pour que le client envoie une nouvelle question. Le parcours se termine quand la page produit montre l'accordéon, ou quand le produit n'a rien à montrer.

Ouvrez **Modules**, **Gestionnaire de modules**, **MyFAQ Free**, **Configurer**. Au-dessus de la barre, la page dit **I am developing this module for free - if you want** et propose **send me a donation**. Sous cette ligne, une bande montre d'autres modules. La note sous la barre dit que les questions se règlent sur chaque produit.

### 3.1 Unlock Pro

![Unlock Pro](https://mypresta.eu/docs/images/docs/myfaqfree-configure-unlock.webp)

L'écran est la section **Unlock Pro**, avec la ligne de don au-dessus de la barre.

**Unlock Pro** n'enregistre aucun réglage et n'écrit pas de questions. La ligne sous la barre est **MyFAQ without the three-question limit**. Elle dit que MyFAQ garde chaque question déjà écrite et ajoute le catalogue, la rédaction par IA et l'API, et que les questions d'un produit restent dans le module gratuit jusqu'à ce que vous les déplaciez.

Le cadre **The full FAQ for the catalogue** liste ce que le module payant ajoute et se termine par **See MyFAQ**. Ce bouton ouvre la page du module payant dans un nouvel onglet. Cet onglet n'enregistre rien pour le module gratuit.

### 3.2 Settings

![Settings](https://mypresta.eu/docs/images/docs/myfaqfree-configure-settings.webp)

L'écran est la section **Settings**. L'image montre une boutique qui a déjà enregistré **Product tab** et un titre. Une installation neuve utilise les valeurs du tableau.

La ligne sous la barre est **Where the three questions are shown**. Elle dit que le module gratuit écrit la FAQ sur chaque produit, trois questions au plus, et qu'ici vous choisissez seulement le pied de produit ou un onglet produit, et les noms de ce bloc.

Le titre du formulaire est **Placement**.

| Champ | Au départ | Ce qu'il fait |
|---|---|---|
| **Show the FAQ** | Product footer | **Product footer** imprime l'accordéon sous le produit. **Product tab** ajoute un onglet produit et laisse le pied vide. Un produit sans question n'affiche rien à ces deux endroits. |
| **Tab title** | FAQ dans chaque langue | Nom de l'onglet produit quand **Show the FAQ** vaut **Product tab**. Remplissez chaque langue avec le bouton de langue. Une langue vide affiche FAQ. |
| **Heading** | vide | Titre au-dessus des questions, dans le pied et dans l'onglet. Remplissez chaque langue avec le bouton de langue. Vide n'affiche que les questions. |

Cliquez sur **Save**. La page affiche **Settings saved.**

Le bouton de langue montre les langues de cette boutique. Sur la boutique de l'image, ce sont l'anglais, le français et le polonais.

### 3.3 Updates

![Updates](https://mypresta.eu/docs/images/docs/myfaqfree-configure-updates.webp)

L'écran est la section **Updates**.

La ligne sous la barre est **Newer versions of MyFAQ Free**. Elle dit que la vérification annonce une version et que l'installation du paquet reste un téléchargement manuel.

Le titre du formulaire est **MyPresta Updates**.

| Champ | Au départ | Ce qu'il fait |
|---|---|---|
| **Check updates** | **Check now** | Vérifie à la main si une version plus récente de ce module est disponible sur les serveurs MyPresta.eu. Le bouton ne télécharge pas et n'installe pas le paquet. Après la vérification, **New version available!** ou **Module is up to date!** apparaît à côté du bouton. |
| **Updates notifications** | Enable | Activé, il interroge MyPresta.eu automatiquement et affiche une alerte sur les nouvelles versions de ce module. **Disable** arrête cette vérification automatique. L'interrupteur est partagé : les autres modules MyPresta de cette boutique utilisent le même interrupteur. La vérification automatique tourne environ tous les trois jours tant que le back-office est utilisé. |
| **Module page** | un lien nommé **MyFAQ Free** | Lien direct vers la page officielle du module, où lire les changements du module (changelog). Le lien ouvre [https://mypresta.eu/](https://mypresta.eu/). |

Cliquez sur **Save**. La page affiche **Update settings saved.**

Quand une version plus récente a été signalée et que les alertes sont actives, le back-office affiche **New version available, check http://MyPresta.eu for more informations** et le lien **More details in changelog**. Ce lien ouvre la même adresse que **Module page**.

### 3.4 Questions sur le produit

![FAQ sur le produit](https://mypresta.eu/docs/images/docs/myfaqfree-product-block.webp)

L'écran est le bloc **MyFAQ Free** sur le produit, dans l'onglet **Modules**. L'image montre un produit qui a déjà trois questions. Un produit neuf commence avec des champs vides. EN, FR et PL sont les langues de cette boutique.

Ouvrez **Catalogue**, **Produits**, modifiez le produit, ouvrez **Modules** et, dans **Module to configure**, choisissez **MyFAQ Free**.

Sur un produit qui n'a pas encore été enregistré, le bloc dit **Save the product first** et **The three FAQ slots appear after the product has an id.** Enregistrez le produit, puis revenez à ce bloc.

Le cadre **Three questions on this product** répète la note sur le module payant et se termine par **See MyFAQ**. Il n'enregistre pas les questions gratuites.

En dessous, **FAQ for this product** dit : trois questions, une question vide reste hors de la page, et **Save these questions** vous laisse sur ce produit. Les boutons de langue changent la question et la réponse. Ils apparaissent quand la boutique a plus d'une langue.

| Champ | Au départ | Ce qu'il fait |
|---|---|---|
| **Question 1**, **Question 2**, **Question 3** | trois emplacements vides, **Show on the product page** coché | Les trois emplacements de ce produit dans ce magasin. Le client les voit dans cet ordre. |
| **Show on the product page** | coché | Coché, l'emplacement s'affiche quand la question est remplie. Décochez pour garder le texte et masquer l'emplacement. |
| **Question** | vide | La ligne que le client clique. Le champ accepte 512 caractères. Une question vide reste hors de la page. Remplissez la question dans chaque langue de vente. Une langue dont la question est vide n'est pas affichée dans cette langue. |
| **Answer** | vide | Le texte sous la question. Un saut de ligne dans le champ devient une nouvelle ligne sur la page produit. Le texte saisi s'affiche comme du texte. |
| **Save these questions** | un bouton | Enregistre les trois emplacements et reste sur ce produit. Pendant l'enregistrement, la ligne sous le bouton dit **Saving the three questions…** Après un enregistrement réussi, elle dit **The three FAQ slots are saved. A slot with an empty question stays off the product page.** |

Il n'y a pas de liste de questions en dehors du produit, ni d'action groupée. Supprimer le produit supprime ses trois questions. Les questions écrites dans un magasin ne s'affichent pas dans un autre tant que vous ne les y écrivez pas.

## 4. Boutique

![Questions sur la page produit](https://mypresta.eu/docs/images/docs/myfaqfree-front-tab.webp)

L'écran de la boutique est en anglais.

Le client voit le bloc seulement sur une page produit, et seulement quand ce produit a au moins une question remplie, cochée **Show on the product page**, et écrite dans la langue du client.

Avec **Show the FAQ** sur **Product footer**, l'accordéon est sous le produit. Avec **Product tab**, le même accordéon est dans un onglet produit et le pied reste vide. Le nom de l'onglet est **Tab title**. Un titre d'onglet vide s'affiche comme FAQ. L'image est l'onglet de cette boutique : l'onglet s'appelle FAQ et le titre est **Questions before you buy**.

Le titre, quand vous en avez saisi un, s'imprime au-dessus des questions. La première question est ouverte au chargement de la page. Le client clique une question pour ouvrir ou fermer sa réponse. Un client sans JavaScript voit chaque réponse. Sous la liste, la ligne **Powered by MyFAQ for PrestaShop** mène au module payant.

Il n'y a pas de page séparée, pas d'adresse à copier et pas de formulaire pour le client. Un produit qui n'a rien à montrer n'imprime pas de bloc.

## 5. Problèmes

**Le produit n'affiche pas de questions.** La question de cette langue est vide, **Show on the product page** est décoché, le module est éteint, ou le thème n'imprime pas l'endroit choisi. Ouvrez le produit, vérifiez l'emplacement, puis sur **Settings** confirmez **Show the FAQ**. **Product footer** demande que le thème imprime le pied de produit. **Product tab** demande que le thème imprime les onglets produit supplémentaires. Un produit sans question remplie n'affiche rien à ces deux endroits.

**Le bloc d'un produit neuf dit Save the product first.** Le produit n'a pas encore d'id. Enregistrez le produit, rouvrez-le, et les trois emplacements apparaissent. Si vous cliquez sur **Save these questions** avant, la ligne dit **Save the product first, then add the FAQ.**

**Save these questions se termine par The FAQ could not be saved.** Cliquez encore sur **Save these questions**. Si cela échoue encore, vérifiez que le module est installé et que le profil de l'employé peut modifier les produits.

**La ligne dit The FAQ could not reach the shop.** Le navigateur n'a pas atteint le back-office. Vérifiez la connexion et cliquez encore sur **Save these questions**. Pendant la requête, la ligne dit **Saving the three questions…**

**La question en boutique est plus courte que celle que vous avez saisie.** Le champ de la question s'arrête à 512 caractères.

**La réponse montre les balises que vous avez saisies.** La réponse est du texte brut. Le saut de ligne est conservé. Les balises s'affichent comme des caractères.

**Le pied est vide après avoir choisi Product tab.** C'est le réglage. **Product tab** laisse le pied vide et place l'accordéon dans l'onglet produit. Choisissez **Product footer** dans **Settings** et cliquez sur **Save** quand l'accordéon doit être sous le produit.

**Un autre magasin n'affiche pas les questions.** Les trois emplacements appartiennent au magasin que vous avez modifié. Basculez l'en-tête multiboutique sur ce magasin, ouvrez le produit et écrivez-y les questions.

**La page produit du back-office demande de choisir un magasin.** La fiche produit travaille dans un magasin à la fois. Choisissez le magasin dans l'en-tête multiboutique, puis ouvrez **Modules**.

**Check now dit Module is up to date! et vous attendiez une version plus récente.** La vérification n'a pas lu de version sur MyPresta.eu, ou ce paquet est celui que le serveur a annoncé. Vérifiez que la boutique atteint MyPresta.eu et cliquez encore sur **Check now**. Le bouton n'installe jamais le paquet.

**Un avertissement dit New version available, check http://MyPresta.eu for more informations.** Les alertes sont actives et une version plus récente a été signalée. Ouvrez **Updates**, lisez **Module page** et installez le paquet vous-même quand vous le voulez. **Disable** sous **Updates notifications** arrête l'avertissement. Cet interrupteur est partagé avec les autres modules MyPresta.

**La bande de don reste vide.** Le reste de la page de configuration continue de fonctionner. Écrivez les questions sur le produit et réglez le placement dans **Settings**.

## 6. Pour le développeur

### 6.1 Aperçu

Classe principale `myfaqfree`, version `1.0.0`, nom dans la liste **MyFAQ Free**, auteur mypresta.eu, onglet `front_office_features`. La compatibilité est déclarée de `1.7.0.0` à `9.99.99`.

Le placement est lu dans `MYFAQFREE_DISPLAY` (`footer` tant que la valeur n'est pas `tab`). Le titre d'onglet et le titre sont lus par langue dans `MYFAQFREE_TAB_TITLE` et `MYFAQFREE_HEADING`. La page produit charge au plus trois emplacements actifs de la boutique et de la langue courantes via `MyfaqfreeRepository::frontItems()` et rend `views/templates/hook/product.tpl`. Le premier élément reçoit `is-open` dans le template. La réponse est échappée puis passée à `nl2br`.

### 6.2 Fichiers

- `myfaqfree.php` — installation, configuration, panneau produit, rendu front.
- `lib/MyfaqfreeRepository.php` — trois emplacements, tables, enregistrement et suppression.
- `lib/updatesChecker.php` — classe `myfaqfreeUpdate`, vérification des mises à jour.
- `lib/prestashop9compatibility.php` — répertoires de templates HelperForm et `curl_close` avant PHP 8.
- `controllers/admin/AdminMyfaqfreeController.php` — enregistrement ajax. Le contrôleur est un onglet caché.
- `views/templates/admin/configure.tpl` — Unlock Pro, Settings, Updates.
- `views/templates/admin/_pro.tpl` — cadre du module payant.
- `views/templates/admin/product.tpl` — trois emplacements sur le produit.
- `views/templates/hook/product.tpl` — accordéon. Variables : `mff_heading`, `mff_items` (`id`, `question`, `answer`), `mff_pro_url`.
- `views/js/admin.js` — changement de langue et enregistrement sur le produit.
- `views/js/front.js` — ouvrir et fermer une question.
- `views/css/admin.css`, `views/css/front.css`.
- `translations/en.php` — présent et vide. Les textes anglais sont les textes source.

### 6.3 Contrôleurs

`AdminMyfaqfree` étend `ModuleAdminController`. L'onglet est créé avec `id_parent = -1`, il n'est donc pas dans le menu de gauche. Le nom de classe de l'onglet est `AdminMyfaqfree` et le libellé est MyFAQ Free. `ajaxProcessSave` transmet à `myfaqfree::ajaxProcessSave()`. Le bloc produit envoie `id_product`, `mff_on_{position}`, `mff_q_{position}_{id_lang}` et `mff_a_{position}_{id_lang}` à `AdminMyfaqfree` avec `ajax=1` et `action=Save`.

Il n'y a pas de contrôleur front. L'accordéon est rendu par les hooks.

`getContent()` est la page de configuration. `mff_tab` accepte `unlock`, `settings` et `updates`. Toute autre valeur ouvre `unlock`.

### 6.4 Hooks

Enregistrés dans `install()` :

| Hook | Rôle |
|---|---|
| `displayHeader` | CSS et JS sur la page produit seulement. |
| `displayFooterProduct` | Accordéon quand le placement est le pied. |
| `displayProductFooter` | Le même accordéon. Un drapeau statique l'imprime une fois par requête. |
| `displayProductExtraContent` | Un onglet produit quand le placement est l'onglet. Sinon un tableau vide. |
| `displayAdminProductsExtra` | Les trois emplacements sur la fiche produit. |
| `actionAdminControllerSetMedia` | CSS et JS d'admin sur la page produit et sur la configuration du module. |
| `actionProductDelete` | Supprime les emplacements de ce produit. |

La classe ne définit ni `enable()` ni `disable()`. Éteindre le module dans le Gestionnaire de modules utilise l'interrupteur du cœur. La classe n'expose pas de hook propre.

`ensureHiddenTab()` et `grantHiddenTabAccess()` partent du constructeur quand l'objet est `myfaqfree`, de `getContent()` et du hook produit. L'accès accorde `view`, `add`, `edit` et `delete` au profil 1 et au profil de l'employé courant.

### 6.5 Surcharges

Le module ne surcharge ni une classe ni un contrôleur.

### 6.6 Base

| Table | Contenu |
|---|---|
| `ps_myfaqfree_item` | `id_item`, `id_product`, `id_shop`, `position` (1–3), `active`, `date_upd`. Clé unique sur produit, boutique et position. |
| `ps_myfaqfree_item_lang` | `id_item`, `id_lang`, `question` (varchar 512), `answer` (text). |

`uninstall()` supprime les deux tables quand `parent::uninstall()` renvoie true. Si `parent::uninstall()` renvoie false, les tables restent. L'onglet et les trois clés de configuration sont supprimés avant ce return. Supprimer un produit supprime ses lignes dans les deux tables. Un emplacement dont chaque langue a une question vide est supprimé à l'enregistrement. Une langue dont la question est vide n'est pas insérée.

Les tables sont créées à l'installation. Ouvrir la page de configuration n'ajoute pas de colonne.

### 6.7 Clés et traductions

| Clé | Si elle manque ou à l'installation |
|---|---|
| `MYFAQFREE_DISPLAY` | L'installation écrit `footer`. Toute valeur autre que `tab` est traitée comme le pied. |
| `MYFAQFREE_TAB_TITLE` | L'installation écrit `FAQ` pour chaque langue. Une langue vide retombe sur le texte source FAQ au rendu. |
| `MYFAQFREE_HEADING` | L'installation écrit une chaîne vide pour chaque langue. Un titre vide n'est pas imprimé. |
| `mypresta_updates` | Ce module ne le crée pas. L'absence est traitée comme activé. **Disable** écrit `0`. La désinstallation ne le supprime pas. |
| `update_myfaqfree` | Horodatage Unix du dernier contrôle. La désinstallation ne le supprime pas. |
| `updatev_myfaqfree` | Chaîne de version renvoyée par le contrôle. La désinstallation ne la supprime pas. |

L'adresse du contrôle est `https://dev.mypresta.eu/update/get.php`. L'intervalle est de 259200 secondes. cURL est utilisé quand `curl_init` existe, avec un délai de 3 secondes. Sinon `file_get_contents` quand `allow_url_fopen` est actif. Le corps de la réponse est débarrassé des balises et stocké comme version disponible.

Les textes du back-office passent par `$this->l()`. Le formulaire de mise à jour utilise la source `updatesChecker`. Ajoutez une langue avec `translations/{iso}.php`. Textes qui ne passent pas par `$this->l()` : **Saving the three questions…**, **The FAQ could not reach the shop.**, et les replis JavaScript **The FAQ could not be saved.** et **Saved.** dans `views/js/admin.js`. Le crédit boutique **Powered by MyFAQ for PrestaShop** est fixe dans `product.tpl`.

Les descriptions de champs sont les chaînes `desc` de `renderSettingsForm()` et de `renderUpdateForm()`.

### 6.8 Extension

Surchargez `views/templates/hook/product.tpl` depuis le thème dans `themes/{theme}/modules/myfaqfree/views/templates/hook/product.tpl`. De la même façon `views/css/front.css` et `views/js/front.js`. Le template n'est pas rendu quand le produit n'a pas d'emplacement visible, une surcharge de thème n'a alors rien à imprimer.

## 7. Aide

Page du module : [https://mypresta.eu/](https://mypresta.eu/)

Pour écrire au sujet de ce module, connectez-vous au compte client sur [mypresta.eu](https://mypresta.eu), ouvrez le contact et choisissez le sujet **Support for paid modules**. Le formulaire indique que la connexion est exigée pour ce sujet. Une fois connecté, choisissez ce module dans l'historique des achats. Ce module est gratuit : s'il n'est pas dans cet historique, nommez **MyFAQ Free** dans le message.
