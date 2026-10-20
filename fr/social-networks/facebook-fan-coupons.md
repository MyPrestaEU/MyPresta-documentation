---
title: "Coupons Fans Facebook - Manuel Marchand & Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop Coupons Fans Facebook par MyPresta.eu."
sidebar:
  label: "Coupons Fans Facebook - Manuel Marchand & Guide de Configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Facebook Fan Coupons sur MyPresta.eu](https://mypresta.eu/modules/social-networks/facebook-fan-coupons.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/social-networks/facebook-fan-coupons/)
>
> ---


# Coupons Fans Facebook

## 1. Exigences et compatibilité

- **Versions PrestaShop prises en charge :** PrestaShop 1.4.x, 1.5.x, 1.6.x, 1.7.x
- **Compatibilité PHP :** PHP 5.6 - 8.5
- **Exigences d'hébergement :** Extensions PHP standard (cURL, JSON, OpenSSL). Votre serveur doit pouvoir communiquer avec l'API de Facebook.

## 2. Parcours de configuration complet (Chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

Ceci est l'écran de configuration principal du module Coupons Fans Facebook, où vous définissez comment les coupons sont générés et comment le module se comporte.

#### Paramètres généraux

- **Ce que fait ce paramètre :** Ces paramètres contrôlent le comportement général du module, y compris les mises à jour et les fonctionnalités de base.
- **Effet de la modification de ce paramètre :**
  - `mypresta_updates`, `update_`, `updatev_` : Ce sont des paramètres internes liés aux mises à jour du module et aux vérifications de version par MyPresta.eu. Vous n'avez généralement pas besoin de les modifier.
- **Valeur recommandée :** Laissez ces valeurs par défaut.
- **Scénario / exemple marchand :** Ces paramètres garantissent que votre module est à jour et compatible avec les services MyPresta.eu.

#### Paramètres de génération de coupons

- **FANCOUPON\_FONTSTYLE**

  - **Ce que fait ce paramètre :** Définit le style de police utilisé pour le code de coupon généré affiché au client sur votre onglet Facebook. Ceci est purement pour la présentation visuelle.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'une police spécifique est définie :* Le code de coupon sera affiché dans cette police, le rendant plus attrayant visuellement ou correspondant à votre marque.
    - *Lorsqu'il est laissé par défaut :* Une police standard et lisible sera utilisée.
  - **Valeur recommandée :** Choisissez une police claire et lisible qui correspond à l'esthétique de votre marque.
  - **Scénario / exemple marchand :** Si votre marque utilise une police stylée spécifique, vous pouvez saisir son nom ici (par exemple, "Arial Black", "Verdana") pour que le coupon semble plus intégré.
- **FANCOUPON\_VOUCHERCODE**

  - **Ce que fait ce paramètre :** C'est le *préfixe* des codes de bon d'achat générés automatiquement. Chaque code commencera par ce texte, suivi de caractères aléatoires.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est défini sur "FANCOUPON" :* Tous les codes générés ressembleront à "FANCOUPONABCD123".
    - *Lorsqu'il est défini sur "FBPROMO" :* Tous les codes générés ressembleront à "FBPROMOXYZ789".
  - **Valeur recommandée :** Un préfixe court et mémorable lié à Facebook ou à votre promotion (par exemple, "FBPROMO", "FAN2024", "MYFAN").
  - **Scénario / exemple marchand :** L'utilisation de "FBPROMO" vous aide à identifier facilement les commandes provenant de cette campagne Facebook dans l'historique de vos commandes PrestaShop.
- **FANCOUPON\_MODE**

  - **Ce que fait ce paramètre :** Détermine le type de réduction que le code de bon d'achat généré fournira (par exemple, pourcentage, montant fixe, livraison gratuite).
  - **Effet de la modification de ce paramètre :**
    - *Réduction en pourcentage :* Le coupon réduira le total de la commande d'un pourcentage (par exemple, 10 % de réduction).
    - *Réduction de montant fixe :* Le coupon réduira le total de la commande d'une valeur monétaire fixe (par exemple, 10 € de réduction).
    - *Livraison gratuite :* Le coupon rendra la livraison gratuite pour la commande.
  - **Valeur recommandée :** Cela dépend de votre stratégie marketing. Les réductions en pourcentage sont souvent populaires pour les promotions générales.
  - **Scénario / exemple marchand :** Pour offrir 15 % de réduction aux nouveaux fans Facebook, vous sélectionneriez "Réduction en pourcentage" ici, puis spécifieriez "15" dans le champ de valeur correspondant (qui apparaît après avoir sélectionné le mode).
- **FANCOUPON\_CHARS**

  - **Ce que fait ce paramètre :** Spécifie les types de caractères (lettres, chiffres) qui seront utilisés dans la *partie aléatoire* du code de bon d'achat généré.
  - **Effet de la modification de ce paramètre :**
    - *Lettres et chiffres :* Les codes seront un mélange de caractères alphanumériques (par exemple, "ABC123").
    - *Chiffres uniquement :* Les codes ne contiendront que des chiffres (par exemple, "123456").
    - *Lettres uniquement :* Les codes ne contiendront que des lettres (par exemple, "ABCDEF").
  - **Valeur recommandée :** "Lettres et chiffres" pour une unicité et une sécurité maximales.
  - **Scénario / exemple marchand :** Pour rendre les codes plus faciles à lire, vous pourriez choisir "Lettres uniquement", mais cela réduit le nombre de combinaisons uniques possibles pour une longueur donnée.
- **FANCOUPON\_LENGTH**

  - **Ce que fait ce paramètre :** Définit la longueur de la *partie aléatoire* du code de bon d'achat généré (hors préfixe).
  - **Effet de la modification de ce paramètre :**
    - *Longueur plus courte (par exemple, 4) :* Les codes sont plus rapides à taper mais moins uniques (par exemple, "FBPROMOABCD").
    - *Longueur plus longue (par exemple, 8) :* Les codes sont plus sécurisés et uniques mais prennent plus de temps à taper (par exemple, "FBPROMOABCD12345").
  - **Valeur recommandée :** 6 à 8 caractères pour un bon équilibre entre unicité et convivialité.
  - **Scénario / exemple marchand :** Si vous vous attendez à un très grand volume de générations de coupons, une longueur plus longue garantit que chaque code est vraiment unique et évite les doublons accidentels.
- **FANCOUPON\_VOUCHER\_CAT**

  - **Ce que fait ce paramètre :** Vous permet de restreindre le code de bon d'achat généré pour qu'il ne s'applique qu'aux produits de catégories spécifiques de votre boutique.
  - **Effet de la modification de ce paramètre :**
    - *Lorsque des catégories spécifiques sont sélectionnées :* Le coupon ne fonctionnera que si le client a des produits de ces catégories dans son panier.
    - *Lorsqu'aucune catégorie n'est sélectionnée :* Le coupon s'appliquera à tous les produits de la boutique.
  - **Valeur recommandée :** Laissez vide si le coupon doit s'appliquer à l'ensemble de la boutique. Sélectionnez des catégories si vous souhaitez promouvoir des gammes de produits spécifiques.
  - **Scénario / exemple marchand :** Si vous organisez une promotion spécifiquement pour votre "Collection d'été", vous sélectionneriez cette catégorie ici afin que le coupon ne fonctionne que sur ces articles.
- **PS\_LANG\_DEFAULT**

  - **Ce que fait ce paramètre :** C'est l'ID de langue par défaut de votre boutique PrestaShop. Il est utilisé en interne par le module pour s'assurer que les descriptions de coupons et d'autres éléments dépendants de la langue sont créés correctement.
  - **Effet de la modification de ce paramètre :** Une modification incorrecte pourrait entraîner des problèmes avec la façon dont les coupons sont créés dans la langue par défaut de votre boutique.
  - **Valeur recommandée :** Laissez la valeur par défaut détectée automatiquement par PrestaShop.
  - **Scénario / exemple marchand :** Cela garantit que lorsqu'un coupon est généré, sa description interne (par exemple, "Coupon Fan Facebook") est correctement définie dans la langue principale de votre boutique.

#### Paramètres des blocs publicitaires (Optionnel)

- **FANCOUPON\_ADV\_POS1**

  - **Ce que fait ce paramètre :** Contrôle l'image/bannière affichée dans la **colonne de gauche** de votre boutique PrestaShop pour promouvoir l'offre de coupon Facebook.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'une URL d'image est saisie :* L'image spécifiée apparaîtra dans la colonne de gauche.
    - *Lorsqu'il est laissé vide :* Aucune image ne sera affichée dans la colonne de gauche.
  - **Valeur recommandée :** Une image de bannière attrayante (par exemple, 200px de large) qui annonce clairement l'offre "Aimez-nous sur Facebook, obtenez un coupon !".
  - **Scénario / exemple marchand :** Vous téléchargez une image de bannière personnalisée sur votre serveur (par exemple, `img/cms/fb-coupon-left.jpg`) et saisissez son URL complète ici.
- **FANCOUPON\_ADV\_POS2**

  - **Ce que fait ce paramètre :** Contrôle l'image/bannière affichée dans la **colonne de droite** de votre boutique PrestaShop pour promouvoir l'offre de coupon Facebook.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'une URL d'image est saisie :* L'image spécifiée apparaîtra dans la colonne de droite.
    - *Lorsqu'il est laissé vide :* Aucune image ne sera affichée dans la colonne de droite.
  - **Valeur recommandée :** Similaire à `FANCOUPON_ADV_POS1`, une image de bannière attrayante (par exemple, 200px de large).
  - **Scénario / exemple marchand :** Vous pourriez utiliser un design différent pour la bannière de la colonne de droite ou simplement dupliquer celle de la colonne de gauche.
- **FANCOUPON\_ADV\_POS3**

  - **Ce que fait ce paramètre :** Contrôle l'image/bannière affichée dans le **pied de page** de votre boutique PrestaShop pour promouvoir l'offre de coupon Facebook.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'une URL d'image est saisie :* L'image spécifiée apparaîtra dans le pied de page.
    - *Lorsqu'il est laissé vide :* Aucune image ne sera affichée dans le pied de page.
  - **Valeur recommandée :** Une image de bannière attrayante adaptée à la zone du pied de page.
  - **Scénario / exemple marchand :** Une bannière plus large et plus courte (par exemple, 900px de large, 100px de haut) qui s'intègre bien dans le pied de page.
- **FANCOUPON\_ADV\_URL**

  - **Ce que fait ce paramètre :** C'est l'URL vers laquelle toutes les bannières publicitaires (`FANCOUPON_ADV_POS1`, `POS2`, `POS3`) redirigeront lorsqu'elles seront cliquées. Il doit s'agir de l'URL directe de l'onglet de votre Page Fan Facebook où le coupon peut être généré.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est défini sur l'URL de votre onglet Facebook :* Cliquer sur l'une des bannières mènera le client directement à l'onglet de génération de coupons sur votre page Facebook.
    - *Lorsqu'il est laissé vide ou incorrect :* Les bannières ne seront pas cliquables ou mèneront à une page incorrecte.
  - **Valeur recommandée :** L'URL exacte de l'onglet de votre Page Fan Facebook où le module de coupon est intégré.
  - **Scénario / exemple marchand :** Après avoir configuré l'onglet Facebook, vous obtiendrez une URL unique pour celui-ci (par exemple, `https://www.facebook.com/VOTREPAGE/app_1234567890`). Saisissez cette URL ici.

### 2.2 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Valeur par défaut / Recommandée | Objectif et impact |
| --- | --- | --- | --- |
| Configuration du module | `FANCOUPON_FONTSTYLE` | Police système par défaut | Style de police pour le code de coupon affiché sur Facebook. |
| Configuration du module | `FANCOUPON_VOUCHERCODE` | `FANCOUPON` | Préfixe des codes de bon d'achat générés. Aide à identifier la campagne. |
| Configuration du module | `FANCOUPON_MODE` | Réduction en pourcentage | Type de réduction (pourcentage, fixe, livraison gratuite). |
| Configuration du module | `FANCOUPON_CHARS` | Lettres et chiffres | Jeu de caractères pour la partie aléatoire du code. |
| Configuration du module | `FANCOUPON_LENGTH` | 6-8 caractères | Longueur de la partie aléatoire du code. Affecte l'unicité. |
| Configuration du module | `FANCOUPON_VOUCHER_CAT` | Vide (tous les produits) | Restreint l'utilisation du coupon à des catégories de produits spécifiques. |
| Configuration du module | `FANCOUPON_ADV_POS1` | Vide | URL de l'image de bannière pour la colonne de gauche. |
| Configuration du module | `FANCOUPON_ADV_POS2` | Vide | URL de l'image de bannière pour la colonne de droite. |
| Configuration du module | `FANCOUPON_ADV_POS3` | Vide | URL de l'image de bannière pour le pied de page. |
| Configuration du module | `FANCOUPON_ADV_URL` | Vide | URL de destination pour toutes les bannières publicitaires (votre onglet Facebook). |

## 3. Dépannage marchand et questions fréquemment posées (FAQ)

**Q : Mes coupons ne fonctionnent pas après la génération.**
R : Vérifiez les points suivants :
1. **Règles panier PrestaShop :** Allez dans **Catalogue > Réductions > Règles panier** dans votre back office PrestaShop. Recherchez les coupons avec le préfixe que vous avez défini (`FANCOUPON_VOUCHERCODE`). Assurez-vous qu'ils sont actifs et n'ont pas expiré. Le module les crée automatiquement, mais une intervention manuelle ou un conflit peut parfois se produire.
2. **Configuration du module :** Vérifiez à nouveau vos paramètres `FANCOUPON_MODE` et `FANCOUPON_VOUCHER_CAT`. Si vous avez restreint le coupon à une catégorie, assurez-vous que le client essaie de l'utiliser sur des produits de cette catégorie.
3. **Cache :** Videz le cache de votre PrestaShop (**Paramètres avancés > Performances**) et le cache de votre navigateur.

**Q : Les bannières publicitaires n'apparaissent pas dans ma boutique.**
R :
1. **Hooks du module :** Assurez-vous que le module est correctement accroché. Dans **Modules > Gestionnaire de modules**, trouvez "Coupons Fans Facebook" et cliquez sur "Configurer". Vérifiez l'onglet "Positions" (ou l'onglet "Hooks" dans les versions antérieures) pour voir s'il est attribué à `displayLeftColumn`, `displayRightColumn` ou `displayFooter`. Si ce n'est pas le cas, vous devrez peut-être l'accrocher manuellement via **Design > Positions** (ou **Modules > Positions**).
2. **URL des images :** Vérifiez que les URL saisies pour `FANCOUPON_ADV_POS1`, `POS2`, `POS3` sont correctes et que les images existent à ces emplacements.
3. **Compatibilité du thème :** Certains thèmes personnalisés peuvent remplacer les positions de hook standard. Si les bannières n'apparaissent toujours pas, vous devrez peut-être demander à un webmaster de vérifier les fichiers de modèle de votre thème.

**Q : L'onglet Facebook ne fonctionne pas ou n'affiche pas le générateur de coupons.**
R : Ce module fournit la logique backend pour la génération de coupons. La configuration réelle de l'onglet Facebook est effectuée *dans les outils de développement de Facebook* ou une application tierce qui intègre du contenu personnalisé.
1. **Configuration de l'application Facebook :** Assurez-vous d'avoir correctement configuré une application Facebook et de l'avoir liée à votre Page Fan, en la pointant vers l'URL du module (qui est généralement le domaine de votre boutique PrestaShop avec un chemin spécifique, ou une page dédiée que vous avez configurée pour héberger la sortie du module). Ce module fournit la *logique* du coupon, mais l'*affichage sur Facebook* nécessite une configuration appropriée de l'application Facebook.
2. **Permissions de la page Facebook :** Assurez-vous que votre page Facebook dispose des permissions nécessaires pour les onglets personnalisés.
3. **Connexion sécurisée (HTTPS) :** Facebook exige que toutes les applications intégrées s'exécutent via HTTPS. Assurez-vous que votre boutique PrestaShop est entièrement sécurisée avec un certificat SSL.

**Q : Comment traduire le texte du module ?**
R : Vous pouvez traduire les phrases du module via le back office de PrestaShop :
1. Allez dans **International > Traductions** (ou **Localisation > Traductions** dans les versions antérieures).
2. Sélectionnez "Traductions des modules installés".
3. Choisissez votre thème, votre langue, puis sélectionnez "Coupons Fans Facebook" dans la liste des modules.
4. Vous pouvez ensuite modifier toutes les chaînes traduisibles utilisées par le module.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

Cette section est strictement destinée aux développeurs, aux webmasters de boutiques et aux agences techniques qui maintiennent ou étendent la boutique.

### 4.1 Aperçu de l'architecture

Le module Coupons Fans Facebook (`fancoupon`) est un module PrestaShop standard principalement axé sur la logique backend pour la génération de coupons et la publicité front-office de base. Il s'appuie sur la classe `Module` et la classe `Configuration` de PrestaShop pour stocker les paramètres. La fonctionnalité principale implique la création dynamique d'objets `CartRule` (bons d'achat) basés sur l'interaction de l'utilisateur sur un onglet Facebook (qui est externe à PrestaShop mais interagit avec la logique du module). Les composants front-office sont limités à de simples bannières d'images accrochées à des positions d'affichage standard.

### 4.2 Contrôleurs (`controllers/`)

Ce module ne contient **pas** de contrôleurs front-office ou back-office dédiés. Toute la configuration est gérée via la méthode `getContent()` de la classe principale du module. Toute interaction pour la génération de coupons serait généralement gérée par une application Facebook externe qui pointe vers une URL sur le site PrestaShop, ce qui déclenche ensuite la logique du module (probablement via un hook ou un point d'entrée personnalisé non explicitement défini comme `ModuleFrontController` dans l'inventaire fourni, mais plutôt géré par la logique principale du module lorsqu'il est appelé).

### 4.3 Classes et modèles principaux (`classes/`)

Ce module ne contient **pas** de classes ou de modèles personnalisés dans le répertoire `classes/`. Il utilise directement les classes `CartRule` et `Configuration` de PrestaShop.

### 4.4 Actifs JavaScript (`views/js/`)

- `fancoupon/lib/voucherengine/script.js`
  - **Portée :** Probablement Front-office (destiné à l'interface de l'onglet Facebook).
  - **Responsabilité :** Ce script est censé gérer la logique côté client pour le processus de génération de coupons. Cela inclurait :
    - Détecter si un utilisateur a "aimé" la page Facebook (via l'API de Facebook).
    - Déclencher une requête AJAX vers le backend PrestaShop (ou le point d'entrée du module) pour générer un coupon.
    - Afficher le code de coupon généré à l'utilisateur.
    - Potentiellement gérer les éléments d'interface utilisateur comme les indicateurs de chargement ou les messages de succès/erreur.
- `fancoupon/views/js/voucherengine/script.js`
  - **Portée :** Probablement Front-office (destiné à l'interface de l'onglet Facebook).
  - **Responsabilité :** Cela semble être un doublon ou une version du script dans `lib/`. Il servirait le même objectif que décrit ci-dessus, gérant les éléments interactifs de la génération de coupons sur l'onglet Facebook. Les développeurs doivent vérifier quel `script.js` est réellement chargé et utilisé.

### 4.5 Feuilles de style CSS (`views/css/`)

- `fancoupon/lib/voucherengine/ps16.css`
  - **Portée :** Style client Front-office.
  - **Responsabilité :** Fournit un style de base pour l'interface de génération de coupons, probablement dans l'onglet Facebook. Le `ps16` dans le nom de fichier suggère qu'il pourrait contenir des styles spécifiquement adaptés à la structure de thème par défaut de PrestaShop 1.6, mais il devrait être généralement compatible ou facilement adaptable.
  - **Sélecteurs de classe CSS clés :** Incluraient généralement des styles pour les boutons, les champs de saisie, les zones d'affichage de texte pour le code de coupon et la mise en page générale du générateur de coupons. Les développeurs peuvent inspecter le HTML rendu sur l'onglet Facebook pour identifier les sélecteurs spécifiques à remplacer.

### 4.6 Structure des modèles Smarty (`views/templates/`)

- **Modèles de hook (`views/templates/advert-*.tpl`)** :
  - `fancoupon/views/templates/advert-footer.tpl`
    - **Hook :** `displayFooter` (ou `footer` dans les versions antérieures).
    - **Sortie :** Rend une bannière/image publicitaire dans le pied de page de la boutique, renvoyant à l'onglet de la Page Fan Facebook. Il utilise `FANCOUPON_ADV_POS3` pour la source de l'image et `FANCOUPON_ADV_URL` pour le lien.
  - `fancoupon/views/templates/advert-left.tpl`
    - **Hook :** `displayLeftColumn` (ou `leftcolumn` dans les versions antérieures).
    - **Sortie :** Rend une bannière/image publicitaire dans la colonne de gauche de la boutique, renvoyant à l'onglet de la Page Fan Facebook. Il utilise `FANCOUPON_ADV_POS1` pour la source de l'image et `FANCOUPON_ADV_URL` pour le lien.
  - `fancoupon/views/templates/advert-right.tpl`
    - **Hook :** `displayRightColumn` (ou `rightcolumn` dans les versions antérieures).
    - **Sortie :** Rend une bannière/image publicitaire dans la colonne de droite de la boutique, renvoyant à l'onglet de la Page Fan Facebook. Il utilise `FANCOUPON_ADV_POS2` pour la source de l'image et `FANCOUPON_ADV_URL` pour le lien.
- **Modèles d'administration (`views/templates/admin/`)** : Aucun identifié.
- **Modèles Front-office (`views/templates/front/`)** : Aucun identifié. L'interface utilisateur principale de génération de coupons est probablement rendue dynamiquement via JavaScript ou directement dans la logique de `fancoupon.php` lorsqu'elle est appelée depuis Facebook.

### 4.7 Schéma de base de données et carte des hooks

- **Tables de base de données** :
  - Ce module ne crée pas de tables SQL personnalisées.
  - Il stocke ses paramètres de configuration dans la table `ps_configuration` de PrestaShop en utilisant des clés comme `FANCOUPON_FONTSTYLE`, `FANCOUPON_VOUCHERCODE`, etc.
  - Il crée des entrées dans `ps_cart_rule` et les tables associées (`ps_cart_rule_lang`, `ps_cart_rule_product_rule_group`, etc.) pour chaque coupon généré.
- **Table des hooks enregistrés** :

| Nom du hook | Moment d'exécution | Objectif technique |
| --- | --- | --- |
| `displayLeftColumn` | Rend le contenu dans la barre latérale gauche de la boutique. | Affiche la bannière publicitaire de la colonne de gauche. |
| `displayRightColumn` | Rend le contenu dans la barre latérale droite de la boutique. | Affiche la bannière publicitaire de la colonne de droite. |
| `displayFooter` | Rend le contenu dans la section du pied de page de la boutique. | Affiche la bannière publicitaire du pied de page. |
| `leftcolumn` | (PrestaShop 1.6.x et versions antérieures) Rend le contenu dans la barre latérale gauche. | Hook hérité pour la bannière publicitaire de la colonne de gauche. |
| `rightcolumn` | (PrestaShop 1.6.x et versions antérieures) Rend le contenu dans la barre latérale droite. | Hook hérité pour la bannière publicitaire de la colonne de droite. |
| `footer` | (PrestaShop 1.6.x et versions antérieures) Rend le contenu dans la section du pied de page. | Hook hérité pour la bannière publicitaire du pied de page. |

## 5. Support officiel et mises à jour

Pour les dernières mises à jour du module, le support technique et toute question concernant le module Coupons Fans Facebook, veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu/my-account/orders/). Notre équipe de support dédiée est disponible pour aider les marchands et les développeurs avec tout problème ou question.
