---
title: "Désactiver les prix spécifiques pour les groupes sélectionnés - Manuel du Marchand et Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop 'Désactiver les prix spécifiques pour les groupes sélectionnés' par MyPresta.eu."
sidebar:
  label: "Désactiver les prix spécifiques pour les groupes sélectionnés - Manuel du Marchand et Guide de Configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Disable specific prices for selected groups sur MyPresta.eu](https://mypresta.eu/modules/ordering-process/disable-specific-prices-for-selected-groups.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/ordering-process/disable-specific-prices-for-selected-groups/)
>
> ---


# Désactiver les prix spécifiques pour les groupes sélectionnés

## 1. Exigences et compatibilité

- **Versions de PrestaShop prises en charge** : PrestaShop 1.6.x, 1.7.x
- **Compatibilité PHP** : PHP 5.6 - 8.5
- **Exigences d'hébergement** : Les extensions PHP standard (cURL, JSON, OpenSSL) sont généralement suffisantes. Aucune configuration de serveur spéciale n'est nécessaire.

## 2. Parcours de configuration complet (chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

Ceci est l'écran de configuration principal et unique pour le module « Désactiver les prix spécifiques pour les groupes sélectionnés ». Vous le trouverez en naviguant vers **Modules > Gestionnaire de modules**, en recherchant « Désactiver les prix spécifiques pour les groupes sélectionnés », et en cliquant sur « Configurer ».

#### **1. Désactiver les remises de prix spécifiques pour les groupes sélectionnés**

Ceci est le paramètre principal du module. Il détermine quels groupes de clients ne recevront *pas* de remises de prix spécifiques.

- **Ce que fait ce paramètre :** Cette section présente une liste de tous les groupes de clients définis dans votre boutique PrestaShop. Vous pouvez sélectionner un ou plusieurs groupes dans cette liste.
- **Effet de la modification de ce paramètre :**
  - *Lorsqu'un ou plusieurs groupes sont sélectionnés :* Les clients appartenant à l'un des groupes sélectionnés ne verront *pas* et ne bénéficieront *pas* des remises de prix spécifiques configurées pour les produits. Ils verront et paieront toujours le prix standard du produit.
  - *Lorsqu'aucun groupe n'est sélectionné :* Le module ne désactivera pas les prix spécifiques pour aucun groupe. Tous les clients recevront les remises de prix spécifiques telles que configurées dans les paramètres de vos produits.
- **Valeur recommandée :** Sélectionnez les groupes de clients spécifiques pour lesquels vous souhaitez désactiver les remises de prix spécifiques. Par exemple, si vous avez un groupe « Grossiste » que vous souhaitez toujours faire payer le prix standard, sélectionnez ce groupe.
- **Scénario / exemple de marchand :** Vous avez un groupe de clients « Invité » et un groupe « Nouveaux clients ». Vous souhaitez réserver les remises de prix spécifiques (comme les prix de gros ou les promotions temporaires) uniquement à votre groupe « Clients fidèles ». En sélectionnant « Invité » et « Nouveaux clients » ici, ces deux groupes verront toujours le prix régulier, tandis que les « Clients fidèles » bénéficieront toujours des prix spécifiques que vous avez configurés.

#### **2. Activé**

Ceci est l'interrupteur marche/arrêt global pour la fonctionnalité du module.

- **Ce que fait ce paramètre :** Il s'agit d'un simple interrupteur pour activer ou désactiver la logique principale du module.
- **Effet de la modification de ce paramètre :**
  - *Lorsqu'il est activé (OUI) :* Le module désactivera activement les prix spécifiques pour les groupes que vous avez sélectionnés dans la section « Désactiver les remises de prix spécifiques pour les groupes sélectionnés ».
  - *Lorsqu'il est désactivé (NON) :* Le module sera inactif. Tous les prix spécifiques fonctionneront comme le comportement standard de PrestaShop, quels que soient les groupes sélectionnés dans la section ci-dessus. Cela désactive efficacement l'impact du module sans le désinstaller.
- **Valeur recommandée :** **OUI** si vous avez l'intention d'utiliser la fonctionnalité du module. **NON** si vous souhaitez le désactiver temporairement sans perdre vos sélections de groupes.
- **Scénario / exemple de marchand :** Vous avez configuré le module pour désactiver les prix spécifiques pour votre groupe de clients « Détail ». Si vous souhaitez lancer une promotion temporaire où *tous* les groupes, y compris « Détail », devraient recevoir des remises de prix spécifiques, vous pouvez simplement définir « Activé » sur **NON**. Une fois la promotion terminée, remettez-le sur **OUI** pour réactiver la désactivation des prix spécifiques pour les clients « Détail ».

#### **3. Toujours retourner le prix le plus bas**

Ce paramètre offre une couche de contrôle supplémentaire, en particulier lorsque les prix spécifiques peuvent interagir avec d'autres règles de prix.

- **Ce que fait ce paramètre :** Cet interrupteur détermine si le module doit strictement appliquer le prix standard pour les groupes sélectionnés, ou s'il doit toujours prendre en compte le *prix le plus bas possible* (qui pourrait inclure d'autres types de remises non gérées par les prix spécifiques) s'il s'avère être inférieur au prix standard.
- **Effet de la modification de ce paramètre :**
  - *Lorsqu'il est activé (OUI) :* Pour les groupes sélectionnés, les prix spécifiques seront ignorés. Cependant, s'il existe *un autre* mécanisme (par exemple, une règle de panier, une remise globale ou un type de réduction de prix différent) qui entraîne un prix inférieur au prix standard, le module permettra à ce prix le plus bas d'être appliqué. Cela garantit que les clients obtiennent toujours le prix le plus bas absolu disponible *en dehors* des prix spécifiques.
  - *Lorsqu'il est désactivé (NON) :* Pour les groupes sélectionnés, les prix spécifiques seront ignorés, et le module appliquera strictement le *prix standard du produit*. Aucun autre prix potentiellement inférieur (sauf s'il fait partie du prix de base lui-même) ne sera pris en compte. Cela offre le contrôle le plus rigide sur les prix pour les groupes sélectionnés.
- **Valeur recommandée :** **NON** pour un contrôle strict, garantissant que les groupes sélectionnés paient toujours le prix standard. **OUI** si vous souhaitez désactiver les prix spécifiques mais permettre tout de même à d'autres remises non liées aux prix spécifiques de s'appliquer si elles entraînent un prix inférieur.
- **Scénario / exemple de marchand :**
  - *Scénario 1 (Recommandé : NON) :* Vous souhaitez que votre groupe « Grossiste » paie *toujours* le prix plein et standard, et ne bénéficie jamais de remises de prix spécifiques ou de toute autre réduction de prix potentielle. Vous définiriez ceci sur **NON**.
  - *Scénario 2 (Recommandé : OUI) :* Vous souhaitez désactiver les prix spécifiques pour votre groupe « Invité », mais vous avez également une règle de panier générale « 5 % de réduction sur tous les produits » qui s'applique à tout le monde. Si vous définissez « Toujours retourner le prix le plus bas » sur **OUI**, les invités n'obtiendront pas de remises de prix spécifiques, mais ils *obtiendront* toujours la remise de 5 % de la règle de panier si cela rend le prix inférieur au prix standard. Si défini sur **NON**, ils paieraient le prix standard complet, ignorant même la règle de panier de 5 %.

### 2.2 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Valeur par défaut / Recommandée | Objectif et impact |
| --- | --- | --- | --- |
| Configuration du module | Désactiver les remises de prix spécifiques pour les groupes sélectionnés | Sélectionner les groupes selon les besoins | Sélectionne les groupes de clients pour lesquels les remises de prix spécifiques seront ignorées. |
| Configuration du module | Activé | OUI | Interrupteur ON/OFF global pour la fonctionnalité du module. |
| Configuration du module | Toujours retourner le prix le plus bas | NON (pour un contrôle strict) / OUI (pour la flexibilité) | Détermine si d'autres remises non spécifiques aux prix peuvent toujours s'appliquer si elles entraînent un prix inférieur pour les groupes affectés. |

## 3. Dépannage pour les marchands et questions fréquemment posées (FAQ)

**Q : J'ai configuré le module, mais les clients du groupe sélectionné voient toujours les prix spécifiques. Qu'est-ce qui ne va pas ?**
R :

1. **Vérifiez le paramètre « Activé » :** Assurez-vous que l'interrupteur « Activé » dans la configuration du module est réglé sur **OUI**.
2. **Vérifiez la sélection du groupe :** Vérifiez à nouveau que le ou les groupes de clients corrects sont sélectionnés sous « Désactiver les remises de prix spécifiques pour les groupes sélectionnés ».
3. **Videz le cache de PrestaShop :** Allez dans **Paramètres avancés > Performances** et cliquez sur « Vider le cache ». PrestaShop met souvent en cache les informations de prix.
4. **Vérifiez le groupe du client :** Assurez-vous que le client avec lequel vous testez est bien affecté au groupe que vous avez sélectionné dans le module. Vous pouvez le vérifier dans **Clients > Clients** dans le Back Office.
5. **Compatibilité du thème :** Bien que rare, certains thèmes fortement personnalisés peuvent interférer. Si le problème persiste, essayez de passer temporairement au thème PrestaShop par défaut pour exclure les conflits de thème.

**Q : Que se passe-t-il si un client appartient à plusieurs groupes, et qu'un groupe est sélectionné pour la désactivation des prix spécifiques tandis qu'un autre ne l'est pas ?**
R : La logique de base de PrestaShop privilégie généralement le prix le plus bas. La surcharge de ce module tentera de supprimer les prix spécifiques pour *tout* groupe sélectionné. Si un client fait partie d'un groupe qui *devrait* avoir les prix spécifiques désactivés, le module tentera d'appliquer le prix standard. Le paramètre « Toujours retourner le prix le plus bas » déterminera ensuite si d'autres remises non spécifiques aux prix sont toujours prises en compte.

**Q : Ce module affecte-t-il d'autres types de remises, comme les règles de panier ou les règles de prix catalogue ?**
R : Ce module cible spécifiquement les « prix spécifiques » tels que définis dans PrestaShop (les remises définies directement sur les pages produits ou via l'importation CSV).

- Si « Toujours retourner le prix le plus bas » est **NON**, le module appliquera strictement le prix standard pour les groupes sélectionnés, potentiellement en annulant d'autres remises si elles entraînent un prix inférieur au prix standard.
- Si « Toujours retourner le prix le plus bas » est **OUI**, le module désactivera les prix spécifiques mais permettra tout de même à d'autres types de remises (comme les règles de panier ou les règles de prix catalogue) de s'appliquer si elles entraînent un prix inférieur au prix standard.

**Q : Je souhaite désactiver temporairement le module sans perdre mes paramètres. Comment faire ?**
R : Rendez-vous simplement sur la page de configuration du module et réglez l'interrupteur « Activé » sur **NON**. Tous vos groupes sélectionnés et autres paramètres seront conservés, et vous pourrez le réactiver à tout moment en le remettant sur **OUI**.

**Q : Comment traduire le texte du module dans d'autres langues ?**
R : Allez dans **International > Traductions** dans votre Back Office PrestaShop. Sélectionnez « Traductions des modules installés », choisissez votre thème, puis sélectionnez « Désactiver les prix spécifiques pour les groupes sélectionnés ». Vous pourrez alors traduire toutes les chaînes de texte visibles.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

Cette section est strictement destinée aux développeurs, aux webmasters de boutiques et aux agences techniques qui maintiennent ou étendent la boutique.

### 4.1 Aperçu de l'architecture

Le module « Désactiver les prix spécifiques pour les groupes sélectionnés » fonctionne principalement en surchargeant les classes PrestaShop de base liées à la tarification des produits, en particulier `Product.php` et `SpecificPrice.php`. Cela lui permet d'intercepter et de modifier la logique qui détermine si les prix spécifiques sont appliqués à un produit, en fonction du groupe du client actuel et de la configuration du module. Il suit une structure de module PrestaShop standard avec un fichier de module principal et des surcharges de classe.

### 4.2 Contrôleurs (`controllers/`)

Ce module n'utilise aucun contrôleur d'administration Front-Office ou Back-Office personnalisé. Toute la configuration est gérée via la méthode `getContent()` de la classe principale du module.

### 4.3 Classes et modèles de base (`classes/`)

La fonctionnalité principale du module est implémentée via des surcharges de classe.

- **`exsdis/override/classes/index.php`** :

  - **Classe d'origine** : `classes/index.php`
  - **Objectif** : Il s'agit d'un fichier `index.php` vide standard, généralement placé dans les répertoires pour empêcher la liste des répertoires. Il n'a aucun impact fonctionnel sur la logique du module.
- **`exsdis/override/classes/Product.php`** :

  - **Classe d'origine** : `classes/Product.php`
  - **Objectif** : Cette surcharge modifie la classe `Product`, qui est essentielle à la manière dont les informations sur les produits, y compris les prix, sont récupérées et calculées dans PrestaShop. La logique du module au sein de cette surcharge intercepte les appels pour récupérer les prix spécifiques d'un produit.
  - **Logique clé** : Elle vérifie si le module est activé et si le groupe du client actuel fait partie de ceux sélectionnés pour avoir les prix spécifiques désactivés. Si c'est le cas, elle manipule le processus de récupération des prix spécifiques pour s'assurer qu'aucun prix spécifique n'est retourné pour ce client. Elle prend également en compte la configuration `exsdis_lowest` pour déterminer si le prix le plus bas absolu (hors prix spécifiques) doit toujours être retourné.
- **`exsdis/override/classes/SpecificPrice.php`** :

  - **Classe d'origine** : `classes/SpecificPrice.php`
  - **Objectif** : Cette surcharge cible la classe `SpecificPrice`, qui est responsable de la gestion et de l'application des règles de prix spécifiques.
  - **Logique clé** : Elle modifie probablement les méthodes au sein de cette classe (par exemple, `getSpecificPrice()`, `getSpecificPrices()`) pour empêcher la création ou le retour d'objets de prix spécifiques pour les clients des groupes désignés. Cela fonctionne en conjonction avec la surcharge `Product.php` pour garantir que les prix spécifiques sont effectivement ignorés.

### 4.4 Actifs JavaScript (`views/js/`)

Ce module n'inclut aucun fichier JavaScript personnalisé.

### 4.5 Feuilles de style CSS (`views/css/`)

Ce module n'inclut aucun fichier CSS personnalisé.

### 4.6 Structure des modèles Smarty (`views/templates/`)

Ce module n'inclut aucun fichier de modèle Smarty personnalisé. Le formulaire de configuration est rendu dynamiquement par la méthode `getContent()` dans `exsdis.php`.

### 4.7 Schéma de base de données et carte des hooks

- **Tables de base de données** :
  Le module ne crée aucune table de base de données personnalisée. Il stocke ses paramètres de configuration dans la table standard `ps_configuration`.

  - Entrées `ps_configuration` :
    - `exsdis_` : (Préfixe pour les paramètres généraux du module)
    - `exsdis_groups` : Stocke un tableau sérialisé ou une chaîne de caractères séparée par des virgules d'ID de groupes de clients pour lesquels les prix spécifiques sont désactivés.
    - `exsdis_lowest` : Stocke la valeur (0 ou 1) pour le paramètre « Toujours retourner le prix le plus bas ».
    - `mypresta_updates`, `update_`, `updatev_` : Lié aux vérifications de mise à jour de MyPresta.eu.
- **Table des hooks enregistrés** :
  Le module n'enregistre explicitement aucun hook PrestaShop standard dans sa méthode `install()`. Sa fonctionnalité est principalement réalisée par des surcharges de classe, qui modifient directement le comportement de base de PrestaShop plutôt que de réagir aux événements de hook.
  La description du module mentionne « Hooks Front-Office : En-tête, Colonnes, Produit ou Pied de page », mais il s'agit probablement d'une déclaration générique sur l'endroit où la *tarification* pourrait être affichée, et non l'endroit où le module lui-même injecte du contenu via des hooks. Les surcharges gèrent la logique de tarification à un niveau inférieur.

## 5. Support officiel et mises à jour

Pour les dernières mises à jour, corrections de bugs et support officiel du module « Désactiver les prix spécifiques pour les groupes sélectionnés », veuillez vous référer à votre compte client MyPresta.eu. Vous pouvez télécharger les versions les plus récentes depuis l'historique de vos commandes et accéder aux canaux de support dédiés fournis par MyPresta.eu.
