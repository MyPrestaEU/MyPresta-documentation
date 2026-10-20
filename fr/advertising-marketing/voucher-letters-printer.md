---
title: "Voucher & Letters Printer - Manuel Marchand & Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop Voucher & Letters Printer par MyPresta.eu."
sidebar:
  label: "Voucher & Letters Printer - Manuel Marchand & Guide de Configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Voucher & Letters Printer sur MyPresta.eu](https://mypresta.eu/modules/advertising-and-marketing/voucher-letters-printer.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/advertising-marketing/voucher-letters-printer/)
>
> ---


# Voucher & Letters Printer

## 1. Exigences et compatibilité

- **Versions PrestaShop prises en charge** : PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilité PHP** : PHP 7.1 - 8.5
- **Exigences d'hébergement** : Extensions PHP standard (cURL, JSON, OpenSSL). Aucune exigence d'hébergement spéciale au-delà d'une configuration PrestaShop typique.

## 2. Parcours de configuration complet (Chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer > Voucher & Letters Printer)

C'est l'écran de configuration principal où vous définirez les paramètres de vos bons et lettres.

#### **Paramètres généraux**

-   **Ce que fait ce paramètre :** Ces paramètres contrôlent le comportement général et l'apparence des bons et lettres générés.
-   **Effet de la modification de ce paramètre :** Les modifications ici auront un impact direct sur le contenu et le format des documents que vous imprimez.

#### **Génération de codes de réduction**

-   **Préfixe du bon :**

    -   **Ce que fait ce paramètre :** Ce texte sera ajouté au début de chaque code de bon généré. Il vous aide à identifier la source du bon (par exemple, « BIENVENUE- », « FIDELITE- »).
    -   **Effet de la modification de ce paramètre :**
        -   *Si défini sur « SOLDE- » :* Tous les codes générés commenceront par « SOLDE- », comme « SOLDE-ABC123XYZ ».
        -   *Si laissé vide :* Les codes seront des caractères purement aléatoires, par exemple, « ABC123XYZ ».
    -   **Valeur recommandée :** Un préfixe court et descriptif lié à votre campagne.
    -   **Scénario / exemple marchand :** Si vous envoyez une récompense de fidélité, utilisez « FIDELITE- ». Pour une vente saisonnière, « ETE- ».
-   **Suffixe du bon :**

    -   **Ce que fait ce paramètre :** Similaire au préfixe, ce texte sera ajouté à la fin de chaque code de bon généré.
    -   **Effet de la modification de ce paramètre :**
        -   *Si défini sur « -2024 » :* Tous les codes générés se termineront par « -2024 », comme « ABC123XYZ-2024 ».
        -   *Si laissé vide :* Les codes n'auront pas de suffixe.
    -   **Valeur recommandée :** Laisser vide sauf si vous avez un besoin de suivi spécifique.
    -   **Scénario / exemple marchand :** Vous pourriez utiliser un suffixe d'année comme « -2024 » pour les campagnes annuelles.
-   **Longueur du code de bon (hors préfixe/suffixe) :**

    -   **Ce que fait ce paramètre :** Détermine le nombre de caractères aléatoires dans le code de bon lui-même, entre le préfixe et le suffixe. Un code plus long est plus sécurisé mais plus difficile à taper.
    -   **Effet de la modification de ce paramètre :**
        -   *Si défini sur 8 :* Les codes auront 8 caractères aléatoires (par exemple, « ABC123XY »).
        -   *Si défini sur 12 :* Les codes auront 12 caractères aléatoires (par exemple, « ABC123XYZ456 »).
    -   **Valeur recommandée :** 8-12 caractères pour un bon équilibre entre sécurité et convivialité.
    -   **Scénario / exemple marchand :** Pour une promotion générale, 8 caractères sont généralement suffisants. Pour des bons exclusifs de grande valeur, vous pourriez opter pour 10-12.

#### **Contenu du bon et de la lettre**

-   **Valeur du bon :**

    -   **Ce que fait ce paramètre :** C'est la valeur monétaire ou le pourcentage de réduction que le bon généré fournira.
    -   **Effet de la modification de ce paramètre :**
        -   *Si défini sur « 10 » :* Le bon accordera une réduction de 10 unités (par exemple, 10 €, 10 $).
        -   *Si défini sur « 20% » :* Le bon accordera une réduction de 20 %.
    -   **Valeur recommandée :** Une valeur qui encourage les achats sans impacter significativement vos marges.
    -   **Scénario / exemple marchand :** Offrez 15 € de réduction pour une commande minimale de 100 €, ou 10 % de réduction sur l'ensemble du panier.
-   **Montant minimum du bon :**

    -   **Ce que fait ce paramètre :** Le total minimum de commande (avant frais de port) requis pour que le client utilise le bon.
    -   **Effet de la modification de ce paramètre :**
        -   *Si défini sur « 50 » :* Les clients doivent dépenser au moins 50 € pour utiliser le bon.
        -   *Si défini sur « 0 » ou laissé vide :* Aucun achat minimum n'est requis.
    -   **Valeur recommandée :** Définissez un montant minimum pour assurer la rentabilité, généralement 2 à 3 fois la valeur du bon.
    -   **Scénario / exemple marchand :** Si le bon est de 10 €, définissez un minimum de 30 € pour encourager un achat plus important.
-   **Date d'expiration du bon (jours à partir de la génération) :**

    -   **Ce que fait ce paramètre :** Définit le nombre de jours après la génération du bon avant son expiration. Cela crée une urgence.
    -   **Effet de la modification de ce paramètre :**
        -   *Si défini sur « 30 » :* Le bon sera valide pendant 30 jours à compter de sa date de création.
        -   *Si défini sur « 0 » ou laissé vide :* Le bon n'aura pas de date d'expiration (non recommandé pour la plupart des campagnes).
    -   **Valeur recommandée :** 30-90 jours, selon l'urgence que vous souhaitez créer.
    -   **Scénario / exemple marchand :** Pour une vente rapide, 30 jours. Pour une récompense de fidélité, 90 jours.
-   **Texte d'en-tête de la lettre :**

    -   **Ce que fait ce paramètre :** C'est le titre principal ou la salutation qui apparaîtra en haut de votre lettre personnalisée.
    -   **Effet de la modification de ce paramètre :**
        -   *Si défini sur « Cher client, » :* Ce sera la ligne d'ouverture de chaque lettre.
        -   *Si défini sur « Une offre spéciale juste pour vous ! » :* Ce sera le titre proéminent.
    -   **Valeur recommandée :** Une salutation chaleureuse et personnelle.
    -   **Scénario / exemple marchand :** « Bonjour [Nom du client], » (si vous prévoyez d'insérer manuellement les noms ou d'utiliser un outil de publipostage plus tard) ou « Merci d'être un client fidèle ! »
-   **Texte du corps de la lettre :**

    -   **Ce que fait ce paramètre :** C'est le contenu principal de votre lettre, où vous expliquez l'offre, remerciez le client et fournissez toute autre information pertinente. Vous pouvez utiliser des espaces réservés pour le contenu dynamique (bien que le module lui-même n'offre pas d'espaces réservés directs, vous utiliseriez généralement un outil de publipostage pour cela après l'exportation).
    -   **Effet de la modification de ce paramètre :** Ce texte constituera le message principal de votre lettre physique.
    -   **Valeur recommandée :** Un texte clair, concis et persuasif qui explique les avantages du bon et encourage son utilisation.
    -   **Scénario / exemple marchand :** « En guise de remerciement, profitez de [Valeur du bon] sur votre prochain achat de [Montant minimum]. Utilisez le code : [Code du bon]. Valable jusqu'au [Date d'expiration]. »
-   **Texte de pied de page de la lettre :**

    -   **Ce que fait ce paramètre :** Ce texte apparaît en bas de votre lettre, généralement pour les coordonnées de votre boutique, votre site web ou une formule de clôture.
    -   **Effet de la modification de ce paramètre :** Ce sera la section de clôture de votre lettre.
    -   **Valeur recommandée :** Le site web de votre boutique, votre adresse e-mail de contact, ou une formule de clôture amicale comme « Sincèrement, L'équipe de [Nom de votre boutique]. »
    -   **Scénario / exemple marchand :** « Visitez-nous sur [www.votreboutique.com](http://www.votreboutique.com) pour plus de produits incroyables ! »

#### **Options d'impression et de conception**

-   **Imprimer le code de bon sur la lettre :**

    -   **Ce que fait ce paramètre :** Un simple interrupteur pour inclure le code de bon généré directement dans la lettre imprimée.
    -   **Effet de la modification de ce paramètre :**
        -   *Si activé (OUI) :* Le code de bon unique sera automatiquement inséré dans le corps de la lettre où vous le spécifiez (ou à une position par défaut s'il n'est pas spécifié dans le corps du texte).
        -   *Si désactivé (NON) :* Le code de bon ne sera pas imprimé sur la lettre. Vous pourriez choisir cela si vous imprimez des cartes de bon séparées.
    -   **Valeur recommandée :** OUI, pour la commodité et pour s'assurer que le client a le code.
    -   **Scénario / exemple marchand :** Si vous voulez un seul document pour le client, activez ceci.
-   **Couleur du texte (pour lettre/bon) :**

    -   **Ce que fait ce paramètre :** Vous permet de choisir la couleur du texte sur vos documents imprimés.
    -   **Effet de la modification de ce paramètre :** Modifie la couleur de l'encre utilisée pour le texte.
    -   **Valeur recommandée :** Noir ou une couleur foncée et lisible qui contraste bien avec le papier blanc.
    -   **Scénario / exemple marchand :** Utilisez la couleur de texte principale de votre marque pour la cohérence.
-   **Couleur de fond (pour la section bon) :**

    -   **Ce que fait ce paramètre :** Si vous imprimez des bons directement sur la lettre, cela définit une couleur de fond pour la zone du code de bon afin de le faire ressortir.
    -   **Effet de la modification de ce paramètre :** Crée une boîte colorée derrière le code de bon.
    -   **Valeur recommandée :** Une couleur claire et subtile qui n'obscurcit pas le texte, ou laissez-la blanche si vous préférez.
    -   **Scénario / exemple marchand :** Un gris clair ou une version pastel de la couleur de votre marque pour mettre en évidence le bon.
-   **Taille de la police (pour lettre/bon) :**

    -   **Ce que fait ce paramètre :** Contrôle la taille du texte sur vos documents imprimés.
    -   **Effet de la modification de ce paramètre :**
        -   *Si défini sur « 12px » :* Le texte aura une taille standard lisible.
        -   *Si défini sur « 16px » :* Le texte sera plus grand, plus facile à lire pour certains.
    -   **Valeur recommandée :** 10-14px pour le corps du texte, légèrement plus grand pour les titres.
    -   **Scénario / exemple marchand :** Si votre public cible inclut des personnes âgées, une taille de police légèrement plus grande pourrait être bénéfique.

#### **Sélection et génération de clients**

-   **Sélectionner les clients :**

    -   **Ce que fait ce paramètre :** Cette section vous permet de choisir quels clients recevront les lettres et bons personnalisés. Vous pouvez sélectionner des clients spécifiques à partir d'une liste.
    -   **Effet de la modification de ce paramètre :** Seuls les clients sélectionnés auront des bons générés pour eux, et leurs détails seront utilisés pour les lettres.
    -   **Valeur recommandée :** Sélectionnez les clients en fonction des objectifs de votre campagne (par exemple, nouveaux clients, clients fidèles, clients inactifs).
    -   **Scénario / exemple marchand :** Sélectionnez tous les clients qui n'ont pas acheté au cours des 6 derniers mois pour les réengager.
-   **Bouton Générer les bons et les lettres :**

    -   **Ce que fait ce paramètre :** Après avoir configuré tous les paramètres et sélectionné les clients, cliquer sur ce bouton lancera le processus de génération des codes de bon uniques et de préparation des lettres personnalisées pour l'impression.
    -   **Effet de la modification de ce paramètre :** Cette action crée de nouvelles règles de panier (bons) dans votre boutique PrestaShop et génère les documents imprimables.
    -   **Valeur recommandée :** Cliquez uniquement après avoir examiné attentivement tous les paramètres.
    -   **Scénario / exemple marchand :** Une fois qu'une campagne est planifiée, cliquez sur ce bouton pour préparer l'envoi.

#### **Tableau de référence rapide de la configuration**

| Écran / Vue | Paramètre / Option | Valeur par défaut / Recommandée | Objectif et impact |
| --- | --- | --- | --- |
| Config principale | Préfixe du bon | `FIDELITE-` | Texte au début du code de bon. Aide à identifier la campagne. |
| Config principale | Suffixe du bon | Vide | Texte à la fin du code de bon. Utile pour le suivi. |
| Config principale | Longueur du code de bon | 8-12 | Nombre de caractères aléatoires dans le code. Affecte la sécurité/convivialité. |
| Config principale | Valeur du bon | `10` (par exemple, 10 € ou 10 %) | Montant ou pourcentage de réduction. |
| Config principale | Montant minimum du bon | `0` (ou 2-3x la valeur du bon) | Commande minimum pour l'utilisation du bon. Assure la rentabilité. |
| Config principale | Date d'expiration du bon (jours) | `30-90` | Jours avant l'expiration du bon. Crée une urgence. |
| Config principale | Texte d'en-tête de la lettre | `Cher client,` | Salutation/titre principal de la lettre. |
| Config principale | Texte du corps de la lettre | (Message personnalisé) | Contenu principal de la lettre, expliquant l'offre. |
| Config principale | Texte de pied de page de la lettre | `www.votreboutique.com` | Remarques finales, informations de contact. |
| Config principale | Imprimer le code de bon sur la lettre | OUI | Inclut le code de bon directement sur la lettre. |
| Config principale | Couleur du texte | Noir | Couleur de tout le texte sur les documents imprimés. |
| Config principale | Couleur de fond | Blanc (ou gris clair) | Couleur de fond pour la zone du code de bon. |
| Config principale | Taille de la police | `12px` | Taille du texte sur les documents imprimés. |
| Config principale | Sélectionner les clients | (Sélection spécifique) | Choisir les clients qui recevront l'envoi. |
| Config principale | Générer les bons et les lettres | (Clic sur le bouton) | Crée les bons et les documents imprimables. |

## 3. Dépannage marchand et questions fréquemment posées (FAQ)

**Q1 : J'ai généré des bons, mais ils ne semblent pas fonctionner sur ma boutique.**
R1 : Après la génération, le module crée des « Règles panier » dans PrestaShop.
1.  **Vérifier les règles panier :** Allez dans **Catalogue > Réductions > Règles panier** dans votre Back Office. Assurez-vous que les bons générés y sont listés et sont « Activés ».
2.  **Vérifier les conditions :** Vérifiez que les conditions du bon (montant minimum, date d'expiration, restrictions client) correspondent à ce que vous aviez prévu. Si un client essaie d'utiliser un bon qui ne remplit pas les critères, il ne sera pas appliqué.
3.  **Vider le cache :** Parfois, le cache de PrestaShop peut empêcher les nouveaux paramètres de prendre effet immédiatement. Allez dans **Paramètres avancés > Performances** et cliquez sur « Vider le cache ».

**Q2 : Les lettres imprimées ne semblent pas correctes, ou les couleurs sont faussées.**
R2 :
1.  **Vérifier les paramètres du module :** Revoyez la page de configuration du module. Vérifiez à nouveau vos paramètres « Couleur du texte », « Couleur de fond » et « Taille de la police ». Assurez-vous d'avoir sélectionné des couleurs qui s'impriment bien.
2.  **Paramètres de l'imprimante :** La qualité de la sortie finale dépend fortement de votre imprimante physique. Vérifiez les niveaux d'encre de votre imprimante, le type de papier et les paramètres de qualité d'impression. Essayez d'imprimer une page de test à partir d'une autre application.
3.  **Aperçu avant impression du navigateur :** Lorsque vous lancez l'impression depuis votre navigateur, utilisez la fonction d'aperçu avant impression pour voir à quoi cela ressemblera avant de consommer de l'encre et du papier. Ajustez les paramètres d'impression du navigateur (par exemple, marges, en-têtes/pieds de page) si nécessaire.

**Q3 : Puis-je traduire le contenu de la lettre dans différentes langues pour les clients internationaux ?**
R3 : La version actuelle du module n'offre pas de champs multilingues intégrés pour le contenu de la lettre directement dans sa configuration. Vous devrez :
1.  **Générer pour chaque langue :** Configurez le module avec le contenu de la lettre dans une langue, générez les lettres pour les clients concernés, puis répétez le processus pour d'autres langues et groupes de clients.
2.  **Traduction manuelle :** Si vous exportez les données client et les codes de bon, vous pouvez utiliser un outil de publipostage séparé pour créer des lettres multilingues.

**Q4 : Je souhaite envoyer des lettres uniquement aux clients d'un pays spécifique. Comment puis-je faire cela ?**
R4 : La fonction « Sélectionner les clients » du module vous permet de choisir des clients individuels. Si vous devez filtrer par pays ou d'autres critères, vous devrez généralement :
1.  **Exporter les données client :** Allez dans **Clients > Clients** dans votre Back Office et utilisez la fonction d'exportation pour obtenir une liste de tous vos clients.
2.  **Filtrer en externe :** Utilisez un programme de feuille de calcul (comme Excel ou Google Sheets) pour filtrer votre liste de clients par pays ou tout autre critère souhaité.
3.  **Sélection manuelle :** Retournez au module et sélectionnez manuellement les clients filtrés dans la liste. Cela peut être fastidieux pour de grandes listes.
4.  **Personnalisation par un développeur (Avancé) :** Pour des besoins de filtrage très importants ou complexes, un développeur pourrait étendre le module pour ajouter des options de filtrage client plus avancées.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

Cette section fournit un aperçu technique détaillé pour les développeurs et les webmasters travaillant avec le module « Voucher & Letters Printer ».

### 4.1 Vue d'ensemble de l'architecture

Le module « Voucher & Letters Printer » est un module PrestaShop standard fonctionnant principalement dans le Back Office. Il utilise la classe `Module` de PrestaShop pour sa fonctionnalité principale et la classe `Configuration` pour stocker les paramètres. L'objectif principal du module est de générer des objets `CartRule` (bons) puis de rendre du contenu HTML imprimable basé sur les paramètres du module et les données client sélectionnées. Il n'introduit pas de tables de base de données personnalisées ni de structures `ObjectModel` complexes au-delà de ce que PrestaShop fournit déjà pour `CartRule` et `Customer`.

### 4.2 Contrôleurs (`controllers/`)

Ce module n'utilise pas de contrôleurs d'administration Front-Office ou Back-Office personnalisés. Toute la configuration et la logique sont gérées dans la méthode `getContent()` du fichier principal du module.

### 4.3 Classes et modèles principaux (`classes/`)

Ce module ne définit aucune classe personnalisée dans le répertoire `classes/`. Il interagit directement avec les classes principales de PrestaShop, principalement :

-   `Module` : La classe de base du module lui-même.
-   `Configuration` : Pour stocker et récupérer les paramètres du module.
-   `Customer` : Pour récupérer les données client pour la personnalisation des lettres.
-   `CartRule` : Pour créer et gérer les codes de bon générés.

### 4.4 Actifs JavaScript (`views/js/`)

-   **`voucherletter/js/jscolor/jscolor.js`**

    -   **Portée :** Back-office.
    -   **Description :** Il s'agit d'une bibliothèque JavaScript tierce pour un sélecteur de couleurs avancé. Elle permet à l'utilisateur administrateur de sélectionner visuellement les couleurs du texte et de l'arrière-plan dans le formulaire de configuration du module.
    -   **Fonctionnalité :** Se lie aux champs de saisie avec des classes spécifiques (par exemple, `jscolor`) pour afficher une palette de couleurs et mettre à jour la valeur de saisie avec le code couleur hexadécimal choisi.
-   **`voucherletter/js/script.js`**

    -   **Portée :** Back-office (page de configuration du module).
    -   **Description :** Contient une logique JavaScript personnalisée spécifique au formulaire de configuration du module.
    -   **Fonctionnalité :**
        -   Gère probablement les requêtes AJAX pour la génération de bons et de lettres (bien que le dossier du module implique que `getContent()` gère le processus complet, ce script pourrait aider à la soumission du formulaire ou aux mises à jour dynamiques).
        -   Pourrait inclure une logique de validation pour les champs du formulaire (par exemple, s'assurer que la valeur du bon est un nombre).
        -   Pourrait gérer l'affichage/masquage de certains éléments du formulaire en fonction d'autres sélections.
        -   Déclenche potentiellement la fonctionnalité d'impression dans le navigateur après la génération du contenu de la lettre.

### 4.5 Feuilles de style CSS (`views/css/`)

Le dossier du module indique qu'aucun fichier CSS personnalisé n'est présent dans `views/css/`. Le style de la configuration du Back Office reposerait sur le CSS du thème d'administration par défaut de PrestaShop. Tout style pour la *sortie imprimée* serait du CSS en ligne généré par le code PHP ou un style HTML très basique.

### 4.6 Structure des modèles Smarty (`views/templates/`)

Le dossier du module indique qu'aucun fichier `.tpl` personnalisé n'est présent dans `views/templates/`. Cela suggère que :

-   Le formulaire de configuration du Back Office est probablement rendu directement dans la méthode `getContent()` à l'aide de `HelperForm` de PrestaShop ou en concaténant des chaînes HTML.
-   Le contenu de la lettre imprimable est généré dynamiquement sous forme de chaîne HTML dans le code PHP, puis affiché pour la fonction d'impression du navigateur.

### 4.7 Schéma de base de données et carte des hooks

-   **Tables de base de données** :

    -   Le module ne crée aucune table de base de données personnalisée.
    -   Il stocke ses paramètres de configuration dans la table `ps_configuration` de PrestaShop. Les clés de configuration suivraient généralement un modèle comme `VOUCHERLETTER_PREFIX`, `VOUCHERLETTER_VALUE`, etc.
    -   Il crée de nouvelles entrées dans les tables `ps_cart_rule` et les tables associées (`ps_cart_rule_lang`, `ps_cart_rule_product_rule_group`, etc.) lors de la génération des bons.
-   **Table des hooks enregistrés** :
    Le dossier du module indique que le module n'enregistre aucun hook front-office (En-tête, Colonnes, Produit, Pied de page). Cela confirme sa fonction principale en tant qu'outil Back Office pour la génération de courrier physique.

| Nom du hook | Moment d'exécution | Objectif technique |
| --- | --- | --- |
| `actionModuleInstall` | Lors de l'installation du module | Définit les valeurs de configuration par défaut dans `ps_configuration`. |
| `actionModuleUninstall` | Lors de la désinstallation du module | Nettoie les valeurs de configuration de `ps_configuration`. |

## 5. Support officiel et mises à jour

Pour les mises à jour officielles, le support technique et toute assistance supplémentaire concernant le module « Voucher & Letters Printer », veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu/). Notre équipe de support est disponible pour vous aider avec tout problème ou question que vous pourriez avoir.
