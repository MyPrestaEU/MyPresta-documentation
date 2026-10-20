---
title: "Derniers avis produits - Manuel Marchand & Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop Derniers avis produits par MyPresta.eu."
sidebar:
  label: "Derniers avis produits - Manuel Marchand & Guide de Configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Last product reviews sur MyPresta.eu](https://mypresta.eu/modules/front-office-features/last-product-reviews.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/front-office/last-product-reviews/)
>
> ---


# Derniers avis produits

## 1. Exigences et compatibilité

- **Versions PrestaShop prises en charge** : PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilité PHP** : PHP 5.6 - 8.5
- **Exigences d'hébergement** : Les extensions PHP standard (cURL, JSON, OpenSSL) sont généralement suffisantes pour ce module.

## 2. Présentation complète de la configuration (Chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

Ceci est l'écran de configuration principal du module « Derniers avis produits ». Vous y trouverez tous les paramètres pour contrôler comment et où vos avis sont affichés.

#### **Afficher les avis dans**

- **Ce que fait ce paramètre :** Cette option détermine où le bloc « Derniers avis produits » apparaîtra sur votre site web. Vous pouvez choisir parmi plusieurs positions de hook PrestaShop standard.
- **Effet de la modification de ce paramètre :**
  - *Lorsqu'il est défini sur « En-tête » :* Le bloc d'avis apparaîtra tout en haut de votre boutique, souvent au-dessus ou en dessous de votre navigation principale. Cela offre une visibilité maximale.
  - *Lorsqu'il est défini sur « Colonne de gauche » :* Le bloc d'avis apparaîtra dans la barre latérale gauche de votre boutique, si votre thème en possède une.
  - *Lorsqu'il est défini sur « Colonne de droite » :* Le bloc d'avis apparaîtra dans la barre latérale droite de votre boutique, si votre thème en possède une.
  - *Lorsqu'il est défini sur « Page produit » :* Le bloc d'avis apparaîtra sur les pages de produits individuelles. C'est excellent pour la vente croisée ou pour montrer une preuve sociale générale pendant qu'un client envisage un achat.
  - *Lorsqu'il est défini sur « Pied de page » :* Le bloc d'avis apparaîtra en bas de chaque page, généralement au-dessus des informations de copyright.
- **Valeur recommandée :** « Colonne de gauche » ou « Colonne de droite » pour une visibilité générale, ou « Page produit » si vous souhaitez mettre l'accent sur les avis pendant le processus de décision d'achat. « En-tête » peut être très impactant mais pourrait prendre trop d'espace précieux selon votre thème.
- **Scénario / exemple marchand :** Si vous souhaitez que les clients voient les avis récents, peu importe où ils naviguent, choisissez « Colonne de gauche ». Si vous souhaitez encourager les achats sur les pages produits, sélectionnez « Page produit ».

#### **Nombre d'avis à afficher**

- **Ce que fait ce paramètre :** Ceci contrôle le nombre d'avis produits individuels qui seront affichés dans le bloc « Derniers avis produits ».
- **Effet de la modification de ce paramètre :**
  - *Lorsqu'il est défini sur un nombre faible (par exemple, 3) :* Le bloc sera compact, affichant seulement quelques avis. C'est bon pour économiser de l'espace mais pourrait ne pas transmettre autant de preuve sociale.
  - *Lorsqu'il est défini sur un nombre plus élevé (par exemple, 10) :* Le bloc sera plus grand, affichant plus d'avis. Cela offre plus de preuve sociale mais nécessite plus d'espace d'écran.
- **Valeur recommandée :** 3-5 pour les colonnes, 5-8 pour l'en-tête/pied de page, selon la mise en page de votre thème et l'espace disponible.
- **Scénario / exemple marchand :** Si votre colonne de gauche est étroite, définissez ceci sur 3 pour éviter que le bloc ne devienne trop long. Si vous avez un pied de page large, vous pourriez le définir sur 6 pour présenter plus de commentaires.

#### **Afficher le nom du client**

- **Ce que fait ce paramètre :** Ce commutateur détermine si le nom du client qui a laissé l'avis sera visible dans le bloc d'avis.
- **Effet de la modification de ce paramètre :**
  - *Lorsqu'il est activé (OUI) :* Chaque avis affichera le nom du client (par exemple, « Avis de Jean D. »). Cela ajoute de l'authenticité et de la personnalisation.
  - *Lorsqu'il est désactivé (NON) :* Le nom du client sera masqué, et seul le contenu de l'avis et le produit seront affichés. Cela peut être préféré pour la confidentialité ou un design plus minimaliste.
- **Valeur recommandée :** OUI. L'affichage des noms de clients ajoute de la crédibilité et rend les avis plus authentiques.
- **Scénario / exemple marchand :** Pour maximiser la confiance, activez ceci. Si vous êtes préoccupé par la confidentialité des clients ou préférez un look très épuré, vous pourriez le désactiver.

#### **Afficher le nom du produit**

- **Ce que fait ce paramètre :** Ce commutateur contrôle si le nom du produit évalué sera affiché à côté du texte de l'avis.
- **Effet de la modification de ce paramètre :**
  - *Lorsqu'il est activé (OUI) :* Chaque avis indiquera clairement à quel produit il se réfère (par exemple, « Produit : Super Widget »). Cela aide les clients à comprendre le contexte de l'avis.
  - *Lorsqu'il est désactivé (NON) :* Seul le texte de l'avis et le nom du client (si activé) seront affichés, sans mention explicite du produit. Cela rend le bloc plus générique.
- **Valeur recommandée :** OUI. Il est crucial pour les clients de savoir quel produit est évalué.
- **Scénario / exemple marchand :** Si un client voit un avis élogieux, il voudra savoir de quel produit il s'agit. L'activation de cette option leur permet de cliquer et potentiellement d'acheter cet article spécifique.

#### **Afficher le contenu de l'avis**

- **Ce que fait ce paramètre :** Ce commutateur détermine si le texte réel de l'avis du client sera affiché dans le bloc.
- **Effet de la modification de ce paramètre :**
  - *Lorsqu'il est activé (OUI) :* Le texte complet ou tronqué de l'avis sera affiché. Cela fournit des commentaires détaillés aux acheteurs potentiels.
  - *Lorsqu'il est désactivé (NON) :* Seule la note (étoiles), le nom du client et le nom du produit seront affichés, sans l'avis écrit. Cela crée un bloc très compact, se concentrant uniquement sur les notes en étoiles.
- **Valeur recommandée :** OUI. Le contenu de l'avis est la partie la plus précieuse de la preuve sociale.
- **Scénario / exemple marchand :** Pour donner aux clients un aperçu rapide de ce que disent les autres, activez ceci. Si vous souhaitez uniquement afficher les notes en étoiles comme un signal de confiance rapide, vous pouvez le désactiver.

#### **Afficher les étoiles de l'avis**

- **Ce que fait ce paramètre :** Ce commutateur contrôle si la note en étoiles (par exemple, 5 étoiles sur 5) associée à chaque avis sera visible.
- **Effet de la modification de ce paramètre :**
  - *Lorsqu'il est activé (OUI) :* La note en étoiles sera affichée de manière proéminente pour chaque avis. C'est un indicateur visuel rapide de la qualité du produit.
  - *Lorsqu'il est désactivé (NON) :* La note en étoiles sera masquée, et seul le contenu textuel (si activé) sera affiché. Ce n'est généralement pas recommandé car les notes en étoiles sont un signal de confiance universel.
- **Valeur recommandée :** OUI. Les notes en étoiles sont incroyablement efficaces pour transmettre rapidement la satisfaction du produit.
- **Scénario / exemple marchand :** Activez toujours ceci pour donner aux clients un indice visuel instantané de la qualité du produit et de la satisfaction client.

#### **Afficher l'image du produit**

- **Ce que fait ce paramètre :** Ce commutateur détermine si l'image principale du produit évalué sera affichée à côté de son avis.
- **Effet de la modification de ce paramètre :**
  - *Lorsqu'il est activé (OUI) :* Une petite vignette de l'image du produit apparaîtra avec chaque avis. Cela rend le bloc plus attrayant visuellement et aide les clients à identifier rapidement le produit.
  - *Lorsqu'il est désactivé (NON) :* Aucune image de produit ne sera affichée, rendant le bloc plus axé sur le texte.
- **Valeur recommandée :** OUI. Les images de produits améliorent considérablement l'attrait visuel et la clarté du bloc d'avis.
- **Scénario / exemple marchand :** Pour rendre votre bloc d'avis plus engageant et aider les clients à associer rapidement les avis à des produits spécifiques, activez les images de produits.

#### **Afficher le prix du produit**

- **Ce que fait ce paramètre :** Ce commutateur contrôle si le prix actuel du produit évalué sera affiché dans le bloc d'avis.
- **Effet de la modification de ce paramètre :**
  - *Lorsqu'il est activé (OUI) :* Le prix du produit sera affiché. Cela peut être utile pour les clients sensibles au prix ou qui veulent rapidement voir si un produit évalué correspond à leur budget.
  - *Lorsqu'il est désactivé (NON) :* Le prix ne sera pas affiché, en se concentrant uniquement sur l'avis et les détails du produit.
- **Valeur recommandée :** NON, sauf si vous souhaitez spécifiquement mettre en évidence les prix des produits dans le bloc d'avis. Cela peut parfois encombrer l'affichage.
- **Scénario / exemple marchand :** Si vous organisez une vente et souhaitez mettre en évidence les produits évalués qui sont actuellement en promotion, vous pouvez activer cette option. Sinon, il est souvent préférable de se concentrer uniquement sur l'avis lui-même.

#### **Afficher le lien du produit**

- **Ce que fait ce paramètre :** Ce commutateur détermine si le nom du produit (ou l'image, si activée) dans le bloc d'avis sera un lien cliquable qui mènera le client directement à la page du produit.
- **Effet de la modification de ce paramètre :**
  - *Lorsqu'il est activé (OUI) :* Les clients peuvent cliquer sur le nom/l'image du produit pour naviguer vers la page complète du produit, où ils peuvent en savoir plus et potentiellement effectuer un achat. C'est crucial pour générer du trafic vers les pages produits.
  - *Lorsqu'il est désactivé (NON) :* Le nom/l'image du produit sera un texte/une image statique, et les clients ne pourront pas cliquer. Cela réduit la capacité du module à générer des conversions.
- **Valeur recommandée :** OUI. Activez toujours cette option pour permettre aux clients d'explorer facilement les produits évalués.
- **Scénario / exemple marchand :** Un client voit un excellent avis pour un « Haut-parleur Bluetooth ». Si le nom du produit est cliquable, il peut immédiatement se rendre sur la page du haut-parleur pour l'acheter.

#### **Afficher la date de l'avis**

- **Ce que fait ce paramètre :** Ce commutateur contrôle si la date de soumission de l'avis sera affichée.
- **Effet de la modification de ce paramètre :**
  - *Lorsqu'il est activé (OUI) :* La date (par exemple, « Avisé le 2023-10-26 ») sera affichée. Cela ajoute de la transparence et assure aux clients que les avis sont récents et pertinents.
  - *Lorsqu'il est désactivé (NON) :* La date sera masquée.
- **Valeur recommandée :** OUI. Les avis récents sont plus percutants et dignes de confiance.
- **Scénario / exemple marchand :** Afficher la date aide les clients à voir que votre boutique est active et reçoit constamment de nouveaux commentaires, renforçant la confiance.

#### **Afficher le titre de l'avis**

- **Ce que fait ce paramètre :** Ce commutateur détermine si le titre de l'avis (si les clients en fournissent un) sera affiché.
- **Effet de la modification de ce paramètre :**
  - *Lorsqu'il est activé (OUI) :* Si un avis a un titre (par exemple, « Produit Incroyable ! »), il sera affiché, souvent en gras, fournissant un résumé rapide du sentiment de l'avis.
  - *Lorsqu'il est désactivé (NON) :* Seul le contenu principal de l'avis sera affiché, sans titre séparé.
- **Valeur recommandée :** OUI. Les titres d'avis sont excellents pour attirer rapidement l'attention et résumer l'essence de l'avis.
- **Scénario / exemple marchand :** Un client qui parcourt rapidement les avis peut en saisir l'essentiel à partir de titres comme « Excellent rapport qualité-prix » ou « Déçu » avant de lire le texte complet.

#### **Note minimale à afficher**

- **Ce que fait ce paramètre :** Ce filtre vous permet de définir une note minimale en étoiles pour que les avis soient inclus dans le bloc « Derniers avis produits ».
- **Effet de la modification de ce paramètre :**
  - *Lorsqu'il est défini sur 1 étoile :* Tous les avis (1 à 5 étoiles) seront affichés.
  - *Lorsqu'il est défini sur 3 étoiles :* Seuls les avis avec 3, 4 ou 5 étoiles seront affichés. Les avis avec 1 ou 2 étoiles seront exclus.
  - *Lorsqu'il est défini sur 5 étoiles :* Seuls les avis parfaits de 5 étoiles seront affichés.
- **Valeur recommandée :** 3 ou 4 étoiles. Bien que la transparence soit bonne, vous pourriez vouloir mettre en évidence principalement les commentaires positifs dans ce bloc proéminent.
- **Scénario / exemple marchand :** Pour vous assurer que votre bloc « Derniers avis produits » affiche toujours des commentaires positifs, définissez ceci sur 4 étoiles. Cela aide à maintenir une image positive tout en restant authentique.

#### **Afficher uniquement les avis de la catégorie sélectionnée**

- **Ce que fait ce paramètre :** Cette option vous permet de filtrer les avis affichés pour n'inclure que ceux associés à des produits d'une catégorie spécifique.
- **Effet de la modification de ce paramètre :**
  - *Lorsque « Non » est sélectionné :* Les avis de toutes les catégories seront pris en compte pour l'affichage.
  - *Lorsqu'une catégorie spécifique (par exemple, « Électronique ») est sélectionnée :* Seuls les avis pour les produits de la catégorie « Électronique » (et ses sous-catégories) seront affichés.
- **Valeur recommandée :** « Non » pour une preuve sociale générale. Sélectionnez une catégorie si le bloc d'avis est placé dans un contexte où seuls des types de produits spécifiques sont pertinents (par exemple, sur une page de catégorie).
- **Scénario / exemple marchand :** Si vous placez le bloc d'avis sur votre page de catégorie « T-Shirts », vous pouvez sélectionner la catégorie « T-Shirts » ici pour vous assurer que seuls les avis pertinents sont affichés, améliorant ainsi l'expérience client.

#### **Afficher uniquement les avis du produit sélectionné**

- **Ce que fait ce paramètre :** Cette option vous permet de filtrer les avis affichés pour n'inclure que ceux associés à un produit spécifique.
- **Effet de la modification de ce paramètre :**
  - *Lorsque « Non » est sélectionné :* Les avis pour tous les produits seront pris en compte pour l'affichage.
  - *Lorsqu'un produit spécifique (par exemple, « Mon Super Gadget ») est sélectionné :* Seuls les avis pour « Mon Super Gadget » seront affichés.
- **Valeur recommandée :** « Non » pour une preuve sociale générale. Sélectionnez un produit si le bloc d'avis est placé dans un contexte où seuls les avis d'un seul produit sont pertinents (par exemple, sur une page de destination personnalisée pour ce produit).
- **Scénario / exemple marchand :** Si vous avez une page promotionnelle spéciale pour votre « Cafetière la plus vendue », vous pouvez configurer ce bloc pour n'afficher que les avis de cette cafetière spécifique sur cette page.

#### **Afficher les avis sous forme de curseur**

- **Ce que fait ce paramètre :** Ce commutateur active ou désactive un curseur dynamique (carrousel) pour le bloc d'avis.
- **Effet de la modification de ce paramètre :**
  - *Lorsqu'il est activé (OUI) :* Les avis défileront automatiquement ou permettront aux clients de naviguer à travers eux à l'aide de flèches/points. C'est excellent pour afficher de nombreux avis dans un espace compact.
  - *Lorsqu'il est désactivé (NON) :* Les avis seront affichés sous forme de liste statique, les uns après les autres.
- **Valeur recommandée :** OUI, surtout si vous affichez plus de 3-4 avis ou si le bloc se trouve dans une colonne étroite.
- **Scénario / exemple marchand :** Si vous souhaitez afficher 8 avis dans votre colonne de gauche mais ne voulez pas que la colonne devienne excessivement longue, l'activation du curseur la rendra compacte et interactive.

#### **Lecture automatique du curseur**

- **Ce que fait ce paramètre :** Si « Afficher les avis sous forme de curseur » est activé, ce paramètre contrôle si le curseur passe automatiquement à l'avis suivant sans interaction de l'utilisateur.
- **Effet de la modification de ce paramètre :**
  - *Lorsqu'il est activé (OUI) :* Le curseur passera automatiquement d'un avis à l'autre après un délai défini.
  - *Lorsqu'il est désactivé (NON) :* Le curseur ne se déplacera que lorsque le client cliquera sur les flèches de navigation ou les points.
- **Valeur recommandée :** OUI, mais assurez-vous que la « Vitesse de lecture automatique du curseur » est définie sur une durée raisonnable.
- **Scénario / exemple marchand :** Pour maintenir le bloc d'avis dynamique et garantir que tous les avis bénéficient d'une certaine visibilité, activez la lecture automatique.

#### **Vitesse de lecture automatique du curseur (en ms)**

- **Ce que fait ce paramètre :** Si la « Lecture automatique du curseur » est activée, ce paramètre détermine la durée (en millisecondes) pendant laquelle chaque avis est affiché avant que le curseur ne passe automatiquement au suivant.
- **Effet de la modification de ce paramètre :**
  - *Un nombre plus faible (par exemple, 2000ms = 2 secondes) :* Les avis changeront rapidement.
  - *Un nombre plus élevé (par exemple, 5000ms = 5 secondes) :* Les avis resteront visibles plus longtemps, donnant aux clients plus de temps pour lire.
- **Valeur recommandée :** 4000-6000 (4-6 secondes) pour donner aux clients suffisamment de temps pour lire un avis sans se sentir pressés.
- **Scénario / exemple marchand :** Définissez ceci sur 5000ms afin que les clients aient amplement le temps de lire chaque avis au fur et à mesure qu'il défile.

#### **Contrôles du curseur**

- **Ce que fait ce paramètre :** Si « Afficher les avis sous forme de curseur » est activé, ceci contrôle si les flèches de navigation (gauche/droite) sont visibles pour que les clients puissent parcourir manuellement les avis.
- **Effet de la modification de ce paramètre :**
  - *Lorsqu'il est activé (OUI) :* Des flèches apparaîtront sur le curseur, permettant une navigation manuelle.
  - *Lorsqu'il est désactivé (NON) :* Aucune flèche ne sera affichée. Les clients ne pourront compter que sur la lecture automatique (si activée) ou les gestes tactiles/de balayage.
- **Valeur recommandée :** OUI. Fournir des contrôles améliore l'expérience utilisateur, même avec la lecture automatique.
- **Scénario / exemple marchand :** Pour donner aux clients un contrôle total sur la navigation des avis, activez les contrôles du curseur.

#### **Pagineur du curseur**

- **Ce que fait ce paramètre :** Si « Afficher les avis sous forme de curseur » est activé, ceci contrôle si de petits points (pagination) sont visibles, indiquant le nombre total d'avis et l'avis actuellement affiché.
- **Effet de la modification de ce paramètre :**
  - *Lorsqu'il est activé (OUI) :* Des points apparaîtront, montrant la progression et permettant des sauts directs vers des avis spécifiques.
  - *Lorsqu'il est désactivé (NON) :* Aucun point ne sera affiché.
- **Valeur recommandée :** OUI. Les pagers fournissent une indication visuelle claire du nombre d'avis disponibles et de la position du client dans la séquence.
- **Scénario / exemple marchand :** Pour aider les clients à comprendre combien d'avis se trouvent dans le curseur et à passer facilement à un avis spécifique, activez le pagineur du curseur.

### 2.2 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Valeur par défaut / Recommandée | Objectif et impact |
| --- | --- | --- | --- |
| Configuration du module | Afficher les avis dans | Colonne de gauche / Colonne de droite | Contrôle la position du bloc d'avis dans votre boutique. |
| Configuration du module | Nombre d'avis à afficher | 3-5 (colonnes), 5-8 (en-tête/pied de page) | Définit le nombre d'avis visibles dans le bloc. |
| Configuration du module | Afficher le nom du client | OUI | Affiche le nom de l'évaluateur pour l'authenticité. |
| Configuration du module | Afficher le nom du produit | OUI | Lie clairement l'avis à son produit. |
| Configuration du module | Afficher le contenu de l'avis | OUI | Affiche le texte réel de l'avis. |
| Configuration du module | Afficher les étoiles de l'avis | OUI | Indicateur visuel de la note du produit. |
| Configuration du module | Afficher l'image du produit | OUI | Rend le bloc plus attrayant visuellement et identifiable. |
| Configuration du module | Afficher le prix du produit | NON | Affiche le prix du produit (peut encombrer, généralement pas nécessaire). |
| Configuration du module | Afficher le lien du produit | OUI | Permet aux clients de cliquer pour accéder à la page du produit. |
| Configuration du module | Afficher la date de l'avis | OUI | Indique la date de soumission de l'avis, prouvant sa récence. |
| Configuration du module | Afficher le titre de l'avis | OUI | Affiche le titre de l'avis pour des résumés rapides. |
| Configuration du module | Note minimale à afficher | 3 ou 4 étoiles | Filtre les avis moins bien notés pour un affichage positif. |
| Configuration du module | Afficher uniquement les avis de la catégorie sélectionnée | Non | Filtre les avis par catégorie de produit. |
| Configuration du module | Afficher uniquement les avis du produit sélectionné | Non | Filtre les avis par un produit spécifique. |
| Configuration du module | Afficher les avis sous forme de curseur | OUI | Présente les avis dans un carrousel dynamique et défilant. |
| Configuration du module | Lecture automatique du curseur | OUI | Fait avancer automatiquement le curseur. |
| Configuration du module | Vitesse de lecture automatique du curseur (en ms) | 4000-6000 | Définit la durée d'affichage de chaque avis dans le curseur. |
| Configuration du module | Contrôles du curseur | OUI | Affiche les flèches de navigation pour le contrôle manuel du curseur. |
| Configuration du module | Pagineur du curseur | OUI | Affiche des points pour la pagination du curseur. |

## 3. Dépannage marchand et questions fréquemment posées (FAQ)

**Q : J'ai configuré le module, mais le bloc d'avis n'apparaît pas sur ma boutique.**
R :

1.  **Vérifiez la position du module :** Allez dans **Design > Positions** (ou **Modules > Positions** dans les anciennes versions de PrestaShop) dans votre Back Office. Recherchez `displayLastReviews` (ou le hook que vous avez sélectionné dans la configuration du module). Assurez-vous que le module « Derniers avis produits » est listé et activé pour ce hook. Si ce n'est pas le cas, cliquez sur « Greffer un module » et ajoutez-le au hook souhaité.
2.  **Videz le cache :** PrestaShop met souvent en cache le contenu. Allez dans **Paramètres avancés > Performance** et cliquez sur « Vider le cache » (ou les boutons « Vider le cache Smarty » et « Vider le cache »).
3.  **Vérifiez les avis :** Assurez-vous que vous avez réellement des avis produits approuvés dans votre boutique. Le module ne peut afficher que les avis qui existent et sont visibles.
4.  **Compatibilité du thème :** Bien que le module soit conçu pour être compatible, certains thèmes très personnalisés peuvent nécessiter des ajustements CSS mineurs. Vérifiez la console de développement de votre navigateur pour toute erreur JavaScript.

**Q : Les avis s'affichent, mais ils ne semblent pas corrects (par exemple, mauvais style, images trop grandes).**
R :

1.  **Conflits de thème :** Le CSS de votre thème pourrait remplacer les styles du module. Vous pouvez essayer d'ajouter du CSS personnalisé au fichier `custom.css` de votre thème (s'il en a un) ou modifier directement `lastreviews/views/css/lastreviews.css` (bien que cela ne soit pas sûr pour les mises à jour).
2.  **Tailles d'image :** Si les images de produits sont trop grandes, vérifiez les paramètres d'image de votre thème ou le CSS du module. Le module utilise une taille d'image standard, mais votre thème pourrait la rendre différemment.
3.  **Problèmes de curseur :** Si le curseur ne fonctionne pas, assurez-vous que « Afficher les avis sous forme de curseur » est activé. Vérifiez les erreurs JavaScript dans la console de votre navigateur, car d'autres modules ou scripts de thème pourraient être en conflit.

**Q : Puis-je afficher les avis d'un produit ou d'une catégorie spécifique uniquement ?**
R : Oui ! Dans la configuration du module, vous avez les options « Afficher uniquement les avis de la catégorie sélectionnée » et « Afficher uniquement les avis du produit sélectionné ». Utilisez ces listes déroulantes pour filtrer les avis affichés dans le bloc.

**Q : Mes avis sont en plusieurs langues. Le module les affichera-t-il correctement ?**
R : Le module s'appuie sur le système d'avis standard de PrestaShop. Si vos avis sont correctement associés aux langues dans PrestaShop, le module devrait afficher les avis dans la langue active du front-office. Assurez-vous que votre thème et PrestaShop sont correctement configurés pour le contenu multilingue.

**Q : Comment puis-je obtenir plus d'avis à afficher ?**
R : Ce module ne fait qu'*afficher* les avis existants. Pour obtenir plus d'avis, vous devez encourager les clients à en laisser. Envisagez d'utiliser un module séparé pour les rappels d'avis, d'offrir des incitations ou de rendre le processus de soumission d'avis très facile sur vos pages produits.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

### 4.1 Vue d'ensemble de l'architecture

Le module « Derniers avis produits » est un module PrestaShop standard suivant un modèle de type MVC. Il fonctionne principalement comme une fonctionnalité de front-office, se greffant sur divers points d'affichage pour rendre un bloc d'avis produits récents. Il exploite la fonctionnalité principale `ProductComment` (ou similaire) de PrestaShop pour récupérer les données d'avis. La logique principale du module réside dans `index.php`, gérant la configuration et l'enregistrement des hooks, tandis que les templates et les assets gèrent l'affichage front-end. Il utilise une bibliothèque JavaScript tierce, `lightslider.js`, pour la fonctionnalité de carrousel.

### 4.2 Contrôleurs (`controllers/`)

Ce module ne contient aucun contrôleur d'administration Front-Office ou Back-Office personnalisé. Toute la configuration est gérée directement dans la méthode `getContent()` de la classe principale du module.

### 4.3 Classes et modèles de base (`classes/`)

Ce module ne définit aucune classe personnalisée ou `ObjectModel` dans un répertoire `classes/`. Il s'appuie sur le `ProductComment` de base de PrestaShop (ou équivalent, selon la version de PrestaShop et si le module officiel de commentaires de produits est installé) pour récupérer les données d'avis.

### 4.4 Assets JavaScript (`views/js/`)

-   **`lastreviews/lib/src/js/lightslider.js`**
    -   **Portée :** Front-office.
    -   **Objectif :** Il s'agit de la bibliothèque JavaScript principale pour créer des curseurs/carrousels de contenu réactifs. Elle fournit la fonctionnalité pour la fonction « Afficher les avis sous forme de curseur ».
    -   **Fonctionnalité :** Se lie à un élément `<ul>` (ou un conteneur similaire) pour le transformer en un curseur réactif. Il gère la lecture automatique, les contrôles de navigation (flèches), la pagination (points), les gestes tactiles/de balayage et le redimensionnement réactif.
    -   **Dépendances :** Nécessite généralement jQuery.

### 4.5 Feuilles de style CSS (`views/css/`)

-   **`lastreviews/lib/src/css/lightslider.css`**
    -   **Portée :** Style client du front-office.
    -   **Objectif :** Fournit le style par défaut pour la bibliothèque `lightslider.js`, y compris la mise en page de base, les flèches de navigation, les points de pagination et les styles d'animation pour le curseur.
    -   **Sélecteurs clés :** `.lightSlider`, `.lSAction > .lSPrev`, `.lSAction > .lSNext`, `.lSPager`, etc. Les développeurs peuvent les remplacer pour correspondre à l'esthétique de leur thème.
-   **`lastreviews/views/css/lastreviews.css`**
    -   **Portée :** Style client du front-office.
    -   **Objectif :** Contient des styles personnalisés spécifiques au bloc d'affichage du module « Derniers avis produits ». Cela inclut le style du conteneur d'avis, des éléments d'avis individuels, des images de produits, des notes en étoiles et des éléments de texte.
    -   **Sélecteurs clés :** `.last-reviews-block`, `.last-review-item`, `.review-product-image`, `.review-stars`, `.review-customer-name`, `.review-product-name`, etc. Ces sélecteurs sont conçus pour être facilement remplacés par le CSS d'un thème personnalisé pour l'intégration.

### 4.6 Structure des templates Smarty (`views/templates/`)

-   **Templates de hook (`views/templates/hook/`)** :
    -   **`lastreviews/views/templates/hook/admin-tips.tpl`**
        -   **Objectif :** Ce template est probablement utilisé dans la page de configuration du Back Office (`getContent()`) pour afficher des conseils ou des instructions administratives au marchand. Il n'est pas rendu dans le front office.
        -   **Contenu :** Contient généralement du code HTML pour des messages d'information, des liens vers la documentation ou des avertissements.
    -   **`lastreviews/views/templates/hook/last-reviews.tpl`**
        -   **Objectif :** Il s'agit du template principal du front-office responsable du rendu du bloc « Derniers avis produits ». Il est greffé sur divers points d'affichage (par exemple, `displayLeftColumn`, `displayFooter`).
        -   **Données :** Reçoit un tableau de données d'avis (nom du client, nom du produit, note, contenu, date, image, lien) de la logique PHP du module.
        -   **Structure :** Itère sur les avis fournis, affichant conditionnellement des éléments basés sur la configuration du module (par exemple, nom du client, image du produit, curseur). Il inclut la structure HTML nécessaire pour que `lightslider.js` s'initialise si l'option de curseur est activée.

### 4.7 Schéma de base de données et carte des hooks

-   **Tables de base de données** :
    -   Ce module ne crée pas ses propres tables de base de données personnalisées. Il s'appuie sur les tables principales de PrestaShop pour les avis produits, généralement `ps_product_comment` et les tables associées (si le module officiel de commentaires de produits est installé et actif).
    -   Les paramètres de configuration sont stockés dans la table `ps_configuration`, avec des clés généralement préfixées par `LASTREVIEWS_` (par exemple, `LASTREVIEWS_DISPLAY_IN`, `LASTREVIEWS_NUM_REVIEWS`).
-   **Table des hooks enregistrés** :

| Nom du hook | Moment d'exécution | Objectif technique |
| --- | --- | --- |
| `displayHeader` | Dans la section `<head>` de toutes les pages du front-office. | Utilisé pour inclure les assets CSS/JS et potentiellement rendre le bloc d'avis en haut de la page. |
| `displayLeftColumn` | Dans la barre latérale gauche des pages du front-office. | Rend le bloc d'avis dans la colonne de gauche. |
| `displayRightColumn` | Dans la barre latérale droite des pages du front-office. | Rend le bloc d'avis dans la colonne de droite. |
| `displayFooter` | Dans la section du pied de page de toutes les pages du front-office. | Rend le bloc d'avis dans le pied de page. |
| `displayProductAdditionalInfo` (ou hook de page produit similaire) | Sur la page produit, généralement sous les informations principales du produit. | Rend le bloc d'avis sur les pages de produits individuelles. |
| `actionFrontControllerSetMedia` | Exécuté lorsqu'un contrôleur frontal définit ses médias (CSS/JS). | Utilisé pour enregistrer les fichiers CSS et JavaScript du module (`lightslider.js`, `lastreviews.css`) à charger sur le front-office. |

## 5. Support officiel et mises à jour

Pour les dernières mises à jour, corrections de bugs et support officiel du module « Derniers avis produits », veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu/my-account/orders/). Notre équipe de support est disponible pour vous aider avec tout problème ou question que vous pourriez avoir concernant la fonctionnalité et la compatibilité du module.
