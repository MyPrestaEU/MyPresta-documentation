---
title: "Changement de référence de commande gratuit - Manuel du marchand et guide de configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop 'Changement de référence de commande gratuit' par MyPresta.eu."
sidebar:
  label: "Changement de référence de commande gratuit - Manuel du marchand et guide de configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Order reference change free sur MyPresta.eu](https://mypresta.eu/modules/administration-tools/order-reference-change-free.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/back-office-tools/order-reference-change-free/)
>
> ---


# Changement de référence de commande gratuit

## 1. Exigences et compatibilité

- **Versions PrestaShop prises en charge** : PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilité PHP** : PHP 7.1 - 8.5
- **Exigences d'hébergement** : Les extensions PHP standard (cURL, JSON, OpenSSL) sont généralement suffisantes. Aucune exigence particulière au-delà d'un environnement d'hébergement PrestaShop standard.

## 2. Parcours de configuration complet (chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

Après l'installation, cliquez sur « Configurer » à côté du module « Changement de référence de commande gratuit ». L'écran de configuration principal s'affichera.

#### **Format de la référence de commande**

C'est le paramètre principal du module, vous permettant de définir le modèle de vos numéros de référence de commande.

- **Ce que fait ce paramètre :** Ce champ de saisie vous permet de spécifier un modèle pour la façon dont les nouveaux numéros de référence de commande seront générés. Vous pouvez utiliser une combinaison de caractères spéciaux et de placeholders pour créer le format souhaité.
- **Effet de la modification de ce paramètre :**
  - *Lorsqu'il est défini sur un format spécifique (par exemple, `[0-9]{6}`) :* Toutes les nouvelles commandes recevront un numéro de référence qui adhère strictement à ce modèle. Par exemple, `[0-9]{6}` générerait une référence numérique à 6 chiffres comme `123456`.
  - *Lorsqu'il est laissé par défaut (comportement par défaut de PrestaShop) :* Le module ne modifiera pas la génération de la référence de commande, et PrestaShop utilisera son format alphanumérique standard (par exemple, `ABCDEF123`).
- **Valeur recommandée :** Cela dépend entièrement des besoins de votre entreprise.
  - Si vous avez besoin d'une référence simple, entièrement numérique, essayez `[0-9]{6}` pour un nombre à 6 chiffres.
  - Si vous voulez un mélange de lettres majuscules et de chiffres, `[A-Z0-9]{8}` vous donnerait une référence alphanumérique à 8 caractères.
  - Vous pouvez également inclure des préfixes statiques, par exemple, `MYSTORE-[0-9]{5}` générerait `MYSTORE-12345`.
- **Scénario / exemple de marchand :**
  - **Scénario 1 : Références entièrement numériques pour la comptabilité.** Votre logiciel de comptabilité exige que toutes les références de commande soient purement numériques et de 8 chiffres. Vous définiriez cela sur `[0-9]{8}`.
  - **Scénario 2 : Références plus courtes et mémorables.** Vous souhaitez des références plus courtes, de 6 caractères, utilisant uniquement des lettres majuscules et des chiffres pour une communication client plus facile. Vous définiriez cela sur `[A-Z0-9]{6}`.
  - **Scénario 3 : Références de marque.** Vous voulez que toutes les références commencent par l'initiale de votre marque suivie d'un nombre à 5 chiffres. Vous définiriez cela sur `M-[0-9]{5}`.

**Placeholders et caractères disponibles :**
Le module utilise une syntaxe de type expression régulière pour définir le format :

- `[0-9]` : Représente n'importe quel chiffre unique de 0 à 9.
- `[a-z]` : Représente n'importe quelle lettre minuscule unique de a à z.
- `[A-Z]` : Représente n'importe quelle lettre majuscule unique de A à Z.
- `[a-zA-Z]` : Représente n'importe quelle lettre unique (majuscule ou minuscule).
- `[A-Z0-9]` : Représente n'importe quelle lettre majuscule ou chiffre unique.
- `{n}` : Spécifie que le caractère ou le groupe précédent doit être répété exactement `n` fois. Par exemple, `[0-9]{6}` signifie 6 chiffres.
- `{n,m}` : Spécifie que le caractère ou le groupe précédent doit être répété entre `n` et `m` fois.
- Tout autre caractère (par exemple, `-`, `_`, `MYSTORE-`) sera inclus littéralement dans la référence.

**Note importante :** Le module garantit que la référence générée est unique. Si une référence générée existe déjà, il essaiera d'en générer une nouvelle jusqu'à ce qu'une référence unique soit trouvée.

#### **Bouton Enregistrer**

- **Ce que fait ce paramètre :** Ce bouton enregistre toutes les modifications que vous avez apportées sur la page de configuration.
- **Effet de la modification de ce paramètre :**
  - *Lorsque vous cliquez :* Votre nouveau format de référence de commande sera appliqué immédiatement à toutes les *nouvelles* commandes passées dans votre boutique. Les références de commande existantes ne seront pas modifiées.
- **Valeur recommandée :** Cliquez toujours sur « Enregistrer » après avoir apporté des modifications pour vous assurer qu'elles sont appliquées.

### 2.2 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Valeur par défaut / Recommandée | Objectif et impact |
| --- | --- | --- | --- |
| Configuration du module | Format de la référence de commande | Par défaut PrestaShop (alphanumérique) | Définit le modèle des nouveaux numéros de référence de commande (par exemple, `[0-9]{6}`, `MYSTORE-[A-Z0-9]{5}`). Affecte la façon dont les nouvelles commandes sont référencées dans votre boutique et sur les documents clients. |

## 3. Dépannage du marchand et questions fréquemment posées (FAQ)

**Q : J'ai changé le format, mais les anciennes commandes ont toujours l'ancienne référence. Pourquoi ?**
R : Ce module n'affecte que les *nouvelles* commandes passées après que vous ayez enregistré la configuration. Il ne modifie pas rétroactivement les références de commande existantes, car cela pourrait entraîner des incohérences de données avec les enregistrements passés, les factures et les communications clients.

**Q : Mes nouvelles références de commande ne suivent pas le format que j'ai défini.**
R :

1.  **Avez-vous cliqué sur « Enregistrer » ?** Assurez-vous d'avoir cliqué sur le bouton « Enregistrer » après avoir apporté des modifications sur la page de configuration du module.
2.  **Vérifiez la syntaxe du format :** Vérifiez attentivement votre chaîne `Order Reference Format` pour toute faute de frappe ou caractère incorrect. Reportez-vous à la section « Placeholders et caractères disponibles » ci-dessus.
3.  **Videz le cache :** Parfois, le cache de PrestaShop peut empêcher les modifications de prendre effet immédiatement. Allez dans **Paramètres avancés > Performances** et cliquez sur « Vider le cache » (ou « Vider le cache Smarty » dans les versions plus anciennes).
4.  **Conflits de modules :** Bien que rares, un autre module qui modifie fortement le processus de commande pourrait entrer en conflit. Essayez de désactiver temporairement d'autres modules récemment installés pour voir si le problème se résout.

**Q : Puis-je rendre la référence de commande plus courte ou plus longue ?**
R : Oui, absolument ! Utilisez la syntaxe `{n}` ou `{n,m}` pour spécifier la longueur exacte ou une plage. Par exemple, `[0-9]{4}` pour un nombre à 4 chiffres, ou `[A-Z0-9]{10}` pour une référence alphanumérique à 10 caractères.

**Q : Que se passe-t-il si le module génère une référence qui existe déjà ?**
R : Le module est conçu pour garantir l'unicité. S'il génère une référence déjà utilisée, il essaiera automatiquement d'en générer une autre jusqu'à ce qu'une référence unique soit trouvée. Ce processus est généralement instantané et garantit qu'aucune commande ne partage la même référence.

**Q : Ce module affecte-t-il le référencement (SEO) ou les performances de ma boutique ?**
R : Non, ce module opère purement sur la logique de backend de la génération de référence de commande. Il n'a aucun impact direct sur le référencement de votre boutique ou sur les performances du front-office.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

### 4.1 Aperçu de l'architecture

Le module « Changement de référence de commande gratuit » réalise sa fonctionnalité grâce à une surcharge de la classe `Order` de base de PrestaShop. Au lieu de s'accrocher directement aux écouteurs d'événements, il modifie le comportement par défaut de la méthode `Order::generateReference()`, qui est responsable de la création de la référence de commande unique. Cette approche garantit que la logique de génération de référence personnalisée est appliquée chaque fois qu'une nouvelle commande est créée, quel que soit le flux spécifique du front-office.

### 4.2 Contrôleurs (`controllers/`)

Ce module n'introduit aucun contrôleur front-office ou back-office personnalisé. Toute la configuration est gérée via la méthode `getContent()` du fichier principal du module.

### 4.3 Classes et modèles de base (`classes/`)

- **`refchange/override/classes/order/Order.php`**
  - **Objectif** : Ce fichier contient la surcharge de la classe `Order` de base de PrestaShop. Sa fonction principale est de remplacer la méthode `generateReference()` par défaut par une logique personnalisée qui applique le format défini dans la configuration du module.
  - **Classe parente** : Étend `OrderCore`.
  - **Méthodes clés** :
    - `generateReference()` : Cette méthode surchargée est le cœur du module.
      - Elle récupère le format de référence personnalisé de `Configuration::get('REFCHANGE_FORMAT')`.
      - Si un format personnalisé est défini, elle utilise une boucle pour générer une chaîne de référence basée sur le modèle configuré (en utilisant `preg_match` et `rand` pour la sélection des caractères).
      - Elle vérifie ensuite la table `ps_orders` pour s'assurer que la référence générée est unique. Si elle n'est pas unique, elle régénère jusqu'à ce qu'une référence unique soit trouvée.
      - Si aucun format personnalisé n'est défini, elle revient à la méthode `OrderCore::generateReference()` parente.
  - **Interaction avec la base de données** : Interagit avec la table `ps_orders` pour vérifier les références existantes.

### 4.4 Actifs JavaScript (`views/js/`)

Ce module n'inclut aucun fichier JavaScript personnalisé.

### 4.5 Feuilles de style CSS (`views/css/`)

Ce module n'inclut aucun fichier CSS personnalisé.

### 4.6 Structure des modèles Smarty (`views/templates/`)

Ce module n'inclut aucun fichier de modèle Smarty personnalisé. L'interface de configuration est rendue directement dans la méthode `getContent()` du fichier principal du module.

### 4.7 Schéma de base de données et carte des hooks

- **Tables de base de données** :
  - `ps_configuration` : Stocke le paramètre de configuration du module :
    - `REFCHANGE_FORMAT` : La chaîne de format de référence de commande personnalisée (par exemple, `[0-9]{6}`).
- **Table des hooks enregistrés** :
  Ce module n'enregistre explicitement aucun hook dans la table `ps_hook_module`. Sa fonctionnalité est implémentée via une surcharge de classe, ce qui signifie qu'il modifie directement le comportement de base plutôt que de répondre à des événements de hook spécifiques.

## 5. Support officiel et mises à jour

Pour les dernières mises à jour, corrections de bugs et support professionnel pour le module « Changement de référence de commande gratuit », veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu). Notre équipe s'engage à garantir le fonctionnement optimal du module avec votre boutique PrestaShop.
