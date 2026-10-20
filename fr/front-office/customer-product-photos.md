---
title: "Photos de produits par les clients - Manuel du marchand et guide de configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop 'Photos de produits par les clients' par MyPresta.eu."
sidebar:
  label: "Photos de produits par les clients - Manuel du marchand et guide de configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Customer product photos sur MyPresta.eu](https://mypresta.eu/modules/front-office-features/customer-product-photos.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/front-office/customer-product-photos/)
>
> ---


# Photos de produits par les clients

## 1. Exigences et compatibilité

- **Versions PrestaShop prises en charge** : PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilité PHP** : PHP 5.6 - 8.5
- **Exigences d'hébergement** : Les extensions PHP standard (cURL, JSON, OpenSSL) sont requises, qui sont généralement disponibles sur la plupart des environnements d'hébergement modernes.

## 2. Parcours de configuration complet (chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

Ceci est l'écran de configuration principal du module « Photos de produits par les clients ». Vous y trouverez une variété de paramètres pour contrôler le comportement et l'apparence du module sur votre boutique.

#### Paramètres généraux

- **Autoriser les fichiers JPEG ?**
  - **Ce que fait ce paramètre :** Détermine si les clients peuvent télécharger des images au format JPEG.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'activé :* Les clients peuvent télécharger des fichiers `.jpg` ou `.jpeg`.
    - *Lorsqu'il est désactivé :* Les fichiers JPEG seront rejetés lors du téléchargement.
  - **Valeur recommandée :** OUI
  - **Scénario / exemple pour le marchand :** La plupart des photos sont prises en JPEG. Garder cette option activée assure une compatibilité maximale pour les téléchargements des clients.
- **Autoriser les fichiers GIF ?**
  - **Ce que fait ce paramètre :** Détermine si les clients peuvent télécharger des images au format GIF.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'activé :* Les clients peuvent télécharger des fichiers `.gif`.
    - *Lorsqu'il est désactivé :* Les fichiers GIF seront rejetés lors du téléchargement.
  - **Valeur recommandée :** OUI (sauf si vous avez une raison spécifique d'interdire les images animées)
  - **Scénario / exemple pour le marchand :** Les GIF peuvent être utiles pour montrer de courtes animations d'un produit, mais peuvent aussi être des fichiers plus volumineux. Activez si vous souhaitez les prendre en charge.
- **Autoriser les fichiers PNG ?**
  - **Ce que fait ce paramètre :** Détermine si les clients peuvent télécharger des images au format PNG.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'activé :* Les clients peuvent télécharger des fichiers `.png`.
    - *Lorsqu'il est désactivé :* Les fichiers PNG seront rejetés lors du téléchargement.
  - **Valeur recommandée :** OUI
  - **Scénario / exemple pour le marchand :** Les PNG sont excellents pour les images avec transparence ou les graphiques nets. C'est un format courant, donc l'activer est généralement une bonne idée.
- **Autoriser les fichiers BMP ?**
  - **Ce que fait ce paramètre :** Détermine si les clients peuvent télécharger des images au format BMP.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'activé :* Les clients peuvent télécharger des fichiers `.bmp`.
    - *Lorsqu'il est désactivé :* Les fichiers BMP seront rejetés lors du téléchargement.
  - **Valeur recommandée :** NON (sauf si spécifiquement requis)
  - **Scénario / exemple pour le marchand :** Les fichiers BMP sont généralement très volumineux et non compressés, ce qui les rend inadaptés à l'utilisation web. Désactiver cette option aide à maintenir l'efficacité de votre galerie.
- **Autoriser les clients non connectés à télécharger des photos ?**
  - **Ce que fait ce paramètre :** Contrôle si les visiteurs qui ne sont pas connectés à un compte client peuvent télécharger des photos.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'activé :* Les invités peuvent télécharger des photos. Il peut leur être demandé une adresse e-mail ou un nom.
    - *Lorsqu'il est désactivé :* Seuls les clients enregistrés et connectés peuvent télécharger des photos.
  - **Valeur recommandée :** OUI (si vous voulez une génération de contenu maximale), NON (si vous voulez lier le contenu à des comptes clients spécifiques)
  - **Scénario / exemple pour le marchand :** Si vous voulez maximiser le contenu généré par les utilisateurs, autoriser les invités est bénéfique. Si vous voulez suivre qui télécharge quoi et potentiellement les récompenser, exigez une connexion.
- **Taille maximale du fichier (en Mo)**
  - **Ce que fait ce paramètre :** Définit la limite supérieure pour la taille d'un fichier image qu'un client peut télécharger.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est réglé sur 5 :* Les clients ne peuvent pas télécharger de fichiers de plus de 5 Mo.
    - *Lorsqu'il est réglé sur 0 :* Aucune limite (bien que les limites du serveur PHP s'appliqueront toujours).
  - **Valeur recommandée :** 2-5 Mo
  - **Scénario / exemple pour le marchand :** Une limite raisonnable empêche les clients de télécharger des fichiers excessivement volumineux qui pourraient ralentir votre site ou consommer trop d'espace serveur. 2-5 Mo est généralement suffisant pour des images web de haute qualité.
- **Hauteur de la vignette (px)**
  - **Ce que fait ce paramètre :** Définit la hauteur des images miniatures générées pour la galerie.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est réglé sur 100 :* Toutes les miniatures auront une hauteur de 100 pixels.
    - *Lorsqu'il est réglé sur 200 :* Toutes les miniatures auront une hauteur de 200 pixels.
  - **Valeur recommandée :** 150-250px (ajuster en fonction du design de votre thème)
  - **Scénario / exemple pour le marchand :** Des tailles de miniatures cohérentes garantissent une présentation de galerie propre et organisée. Ajustez cela pour correspondre à l'esthétique de votre thème.
- **Largeur de la vignette (px)**
  - **Ce que fait ce paramètre :** Définit la largeur des images miniatures générées pour la galerie.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est réglé sur 100 :* Toutes les miniatures auront une largeur de 100 pixels.
    - *Lorsqu'il est réglé sur 200 :* Toutes les miniatures auront une largeur de 200 pixels.
  - **Valeur recommandée :** 150-250px (ajuster en fonction du design de votre thème)
  - **Scénario / exemple pour le marchand :** Similaire à la hauteur, une largeur cohérente aide à maintenir une galerie visuellement attrayante.
- **Photos par page dans la galerie** (`CG_PAGINATION`)
  - **Ce que fait ce paramètre :** Contrôle le nombre de photos de clients affichées sur une seule page dans la vue principale de la galerie avant que la pagination n'intervienne.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est réglé sur 12 :* La galerie affichera 12 photos par page.
    - *Lorsqu'il est réglé sur 24 :* La galerie affichera 24 photos par page.
  - **Valeur recommandée :** 12-24
  - **Scénario / exemple pour le marchand :** Un nombre modéré évite de submerger l'utilisateur et maintient des temps de chargement de page raisonnables. Trop peu signifie plus de clics, trop peut ralentir la page.
- **Activer le vote pour les photos ?** (`CG_voting`)
  - **Ce que fait ce paramètre :** Permet aux clients de voter sur les photos téléchargées, généralement avec un simple « j'aime » ou une note par étoiles.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'activé :* Les contrôles de vote (par exemple, étoiles, pouces levés) apparaîtront à côté de chaque photo.
    - *Lorsqu'il est désactivé :* Aucune option de vote ne sera affichée.
  - **Valeur recommandée :** OUI (encourage l'interaction)
  - **Scénario / exemple pour le marchand :** L'activation du vote peut mettre en évidence les photos populaires et encourager davantage d'engagement de la part de votre communauté.
- **Autoriser les clients non connectés à voter ?** (`cg_unl_voting`)
  - **Ce que fait ce paramètre :** Détermine si les visiteurs non connectés peuvent voter sur les photos.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'activé :* Les invités peuvent voter sur les photos.
    - *Lorsqu'il est désactivé :* Seuls les clients connectés peuvent voter.
  - **Valeur recommandée :** NON (pour éviter le spam/le vote par des robots et assurer un engagement plus significatif)
  - **Scénario / exemple pour le marchand :** Restreindre le vote aux utilisateurs connectés aide à garantir que les votes proviennent de clients réels et réduit le risque de manipulation.
- **Style de vote** (`CG_VOTE_STAR`, `CGV_voting`)
  - **Ce que fait ce paramètre :** Sélectionne le style visuel du mécanisme de vote (par exemple, différentes couleurs d'étoiles).
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est réglé sur « Étoiles noires » :* Le vote utilisera des icônes d'étoiles noires.
    - *Lorsqu'il est réglé sur « Étoiles dorées » :* Le vote utilisera des icônes d'étoiles dorées.
  - **Valeur recommandée :** Étoiles dorées (souvent associées à la qualité et aux avis)
  - **Scénario / exemple pour le marchand :** Choisissez un style qui correspond le mieux à l'image de marque et à l'esthétique de votre boutique.
- **Activer le mode concours ?** (`cg_contest`)
  - **Ce que fait ce paramètre :** Active les fonctionnalités qui prennent en charge l'organisation d'un concours photo, telles que l'affichage des gagnants ou des règles de concours spécifiques.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'activé :* Des options ou des affichages supplémentaires liés au concours peuvent apparaître.
    - *Lorsqu'il est désactivé :* Comportement standard de la galerie.
  - **Valeur recommandée :** NON (sauf si vous organisez activement un concours)
  - **Scénario / exemple pour le marchand :** Si vous prévoyez d'organiser un concours de « meilleure photo », activez cette option pour tirer parti des fonctionnalités de concours du module.

#### Emplacements d'affichage Front-Office

Ces paramètres contrôlent où la galerie de photos des clients et les options de téléchargement apparaissent sur votre boutique.

- **Afficher le formulaire de téléchargement sur la page produit ?** (`CG_FUPLOADON`)
  - **Ce que fait ce paramètre :** Détermine si le formulaire de téléchargement de photos est directement visible sur la page produit.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'activé :* Les clients verront un formulaire pour télécharger des photos directement sur la page produit.
    - *Lorsqu'il est désactivé :* Le formulaire de téléchargement n'apparaîtra pas sur la page produit ; les clients devront peut-être se rendre sur leur compte ou sur une page de galerie dédiée pour télécharger.
  - **Valeur recommandée :** OUI (pour une commodité maximale et une génération de contenu)
  - **Scénario / exemple pour le marchand :** Rendre le formulaire de téléchargement facilement accessible sur la page produit encourage davantage de clients à partager leurs photos juste après avoir consulté le produit.
- **Afficher la galerie sur la page produit sous forme d'onglet ?** (`CG_PRODUCTTAB`, `cg_productTabM`)
  - **Ce que fait ce paramètre :** Intègre la galerie de photos des clients comme un nouvel onglet sur la page produit (par exemple, à côté de « Description » ou « Fiche technique »).
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'activé :* Un nouvel onglet apparaîtra sur les pages produits, affichant les photos des clients pour ce produit spécifique.
    - *Lorsqu'il est désactivé :* La galerie n'apparaîtra pas sous forme d'onglet.
  - **Valeur recommandée :** OUI
  - **Scénario / exemple pour le marchand :** C'est un moyen très visible et efficace d'afficher le contenu généré par les utilisateurs, le rendant facilement découvrable pour les acheteurs.
- **Afficher la galerie sur la page produit dans le pied de page ?** (`CG_PRODUCTFOOTER`)
  - **Ce que fait ce paramètre :** Affiche une section de photos de clients dans la zone du pied de page de la page produit.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'activé :* Un bloc de photos de clients apparaîtra sous le contenu principal du produit.
    - *Lorsqu'il est désactivé :* Aucune photo n'apparaîtra dans le pied de page de la page produit.
  - **Valeur recommandée :** OUI (comme point d'affichage supplémentaire)
  - **Scénario / exemple pour le marchand :** Cela offre une autre opportunité de présenter les photos des clients sans encombrer la zone d'informations principales du produit.
- **Afficher la galerie dans le compte client ?** (`CG_CUSTOMERACCOUNT`, `CG_CUSTOMERACCOUNTV`)
  - **Ce que fait ce paramètre :** Crée une section dédiée « Mes photos » dans l'espace de compte personnel du client.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'activé :* Les clients connectés verront un nouveau lien et une nouvelle page dans leur compte pour gérer leurs photos téléchargées.
    - *Lorsqu'il est désactivé :* Les clients ne peuvent pas gérer leurs photos depuis leur compte.
  - **Valeur recommandée :** OUI
  - **Scénario / exemple pour le marchand :** Essentiel pour que les clients puissent visualiser et gérer leurs contributions, favorisant un sentiment d'appartenance et de communauté.
- **Afficher le lien vers la galerie dans le bloc « Mon compte » ?** (`CG_MYACCOUNTBLOCK`, `CG_MYACCOUNTBLOCKV`)
  - **Ce que fait ce paramètre :** Ajoute un lien vers la section « Mes photos » (ou la galerie principale) dans le bloc « Mon compte », qui se trouve souvent dans la colonne de gauche ou de droite ou le pied de page.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'activé :* Un lien rapide apparaîtra pour les utilisateurs connectés.
    - *Lorsqu'il est désactivé :* Le lien ne sera pas présent dans le bloc.
  - **Valeur recommandée :** OUI (pour une navigation facile)
  - **Scénario / exemple pour le marchand :** Facilite grandement l'accès des clients à leur galerie de photos ou le téléchargement de nouvelles photos depuis presque n'importe quelle page.
- **Afficher la galerie dans la colonne de droite ?** (`CG_RIGHTCOL`)
  - **Ce que fait ce paramètre :** Affiche un bloc de photos de clients dans la colonne de droite de votre boutique.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'activé :* Un bloc dynamique de photos apparaîtra dans la barre latérale droite.
    - *Lorsqu'il est désactivé :* Aucune photo n'apparaîtra dans la colonne de droite.
  - **Valeur recommandée :** NON (peut être distrayant, à considérer uniquement si votre thème dispose de beaucoup d'espace)
  - **Scénario / exemple pour le marchand :** Utile si vous avez une mise en page large et que vous souhaitez présenter constamment du contenu client, mais peut parfois encombrer la page.
- **Afficher la galerie dans la colonne de gauche ?** (`CG_LEFTCOL`)
  - **Ce que fait ce paramètre :** Affiche un bloc de photos de clients dans la colonne de gauche de votre boutique.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'activé :* Un bloc dynamique de photos apparaîtra dans la barre latérale gauche.
    - *Lorsqu'il est désactivé :* Aucune photo n'apparaîtra dans la colonne de gauche.
  - **Valeur recommandée :** NON (similaire à la colonne de droite, à utiliser avec parcimonie)
  - **Scénario / exemple pour le marchand :** Similaire à la colonne de droite, à utiliser si la conception de votre thème le permet sans compromettre la lisibilité.
- **Afficher la galerie sur la page d'accueil ?** (`CG_GALLERY`, `cg_hpg_nb`, `cg_hpg_o`)
  - **Ce que fait ce paramètre :** Affiche une sélection de photos de clients directement sur la page d'accueil de votre boutique. Vous pouvez également avoir des options pour contrôler le nombre de photos (`cg_hpg_nb`) et leur ordre (`cg_hpg_o`).
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'activé :* Une section avec des photos de clients apparaîtra sur la page d'accueil.
    - *Lorsqu'il est désactivé :* Aucune photo de client ne sera affichée sur la page d'accueil.
  - **Valeur recommandée :** OUI (fortement recommandé pour l'engagement)
  - **Scénario / exemple pour le marchand :** La page d'accueil est un emplacement de choix. Présenter des photos de clients ici transmet immédiatement la confiance et la communauté aux nouveaux visiteurs.
- **Exclure des produits spécifiques de la galerie ?** (`cg_excludeproduct`)
  - **Ce que fait ce paramètre :** Vous permet de spécifier les ID de produits pour lesquels les photos de clients ne doivent pas être affichées ou téléchargées.
  - **Effet de la modification de ce paramètre :**
    - *Lorsque l'ID produit 123 est saisi :* Le produit 123 n'affichera pas de photos de clients, et les téléchargements pour celui-ci seront désactivés.
    - *Lorsqu'il est laissé vide :* Tous les produits sont éligibles aux photos de clients.
  - **Valeur recommandée :** Laisser vide, sauf si vous avez des produits sensibles ou non visuels.
  - **Scénario / exemple pour le marchand :** Si vous vendez des produits numériques ou des services qui n'ont pas de composant visuel, ou des produits pour lesquels vous ne souhaitez pas de contenu généré par les utilisateurs, vous pouvez les exclure ici.

#### Notifications et mises à jour

- **Activer les notifications par e-mail pour les nouveaux téléchargements ?** (`CG_NTF`)
  - **Ce que fait ce paramètre :** Envoie une notification par e-mail à l'administrateur de la boutique chaque fois qu'une nouvelle photo de client est téléchargée.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'activé :* Vous recevrez un e-mail pour chaque nouveau téléchargement, vous permettant de modérer rapidement.
    - *Lorsqu'il est désactivé :* Aucune notification par e-mail ne sera envoyée.
  - **Valeur recommandée :** OUI (essentiel pour la modération et le contrôle qualité)
  - **Scénario / exemple pour le marchand :** Rester informé des nouveaux téléchargements vous aide à garantir que tout le contenu est approprié et de haute qualité avant qu'il ne soit largement visible.
- **Mises à jour MyPresta.eu** (`mypresta_updates`, `update_`, `updatev_`)
  - **Ce que fait ce paramètre :** C'est un paramètre standard dans les modules MyPresta.eu pour vérifier les mises à jour disponibles.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'activé :* Le module vérifiera périodiquement MyPresta.eu pour de nouvelles versions.
    - *Lorsqu'il est désactivé :* Le module ne vérifiera pas automatiquement les mises à jour.
  - **Valeur recommandée :** OUI (toujours rester à jour pour la sécurité et les fonctionnalités)
  - **Scénario / exemple pour le marchand :** Garder cette option activée vous assure d'être informé des nouvelles fonctionnalités, des corrections de bugs et des correctifs de sécurité, aidant votre boutique à rester à jour et sécurisée.

#### Paramètres internes/avancés (généralement à laisser par défaut)

- **`CG_LAST_TAB`** : Paramètre interne pour mémoriser le dernier onglet actif dans la configuration du module.
- **`cg_altered1`, `cg_altered2`** : Indicateurs internes, généralement liés aux mises à jour du module ou aux migrations de données.

### 2.2 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Valeur par défaut / Recommandée | Objectif et impact |
| --- | --- | --- | --- |
| Configuration du module | Autoriser les fichiers JPEG ? | OUI | Permet aux clients de télécharger des images JPEG. |
| Configuration du module | Autoriser les fichiers GIF ? | OUI | Permet aux clients de télécharger des images GIF. |
| Configuration du module | Autoriser les fichiers PNG ? | OUI | Permet aux clients de télécharger des images PNG. |
| Configuration du module | Autoriser les fichiers BMP ? | NON | Interdit les images BMP volumineuses et non compressées. |
| Configuration du module | Autoriser les clients non connectés à télécharger des photos ? | OUI / NON (Choix du marchand) | Contrôle les téléchargements des invités. |
| Configuration du module | Taille maximale du fichier (en Mo) | 2-5 Mo | Limite la taille de téléchargement pour éviter les fichiers volumineux. |
| Configuration du module | Hauteur de la vignette (px) | 150-250px | Définit une hauteur cohérente pour les miniatures de la galerie. |
| Configuration du module | Largeur de la vignette (px) | 150-250px | Définit une largeur cohérente pour les miniatures de la galerie. |
| Configuration du module | Photos par page dans la galerie | 12-24 | Contrôle la pagination pour la galerie principale. |
| Configuration du module | Activer le vote pour les photos ? | OUI | Permet aux clients de voter sur les photos. |
| Configuration du module | Autoriser les clients non connectés à voter ? | NON | Empêche le spam/le vote par des robots. |
| Configuration du module | Style de vote | Étoiles dorées | Définit le style visuel des icônes de vote. |
| Configuration du module | Activer le mode concours ? | NON | Active les fonctionnalités spécifiques aux concours. |
| Configuration du module | Afficher le formulaire de téléchargement sur la page produit ? | OUI | Affiche le formulaire de téléchargement directement sur les pages produits. |
| Configuration du module | Afficher la galerie sur la page produit sous forme d'onglet ? | OUI | Ajoute un onglet dédié pour les photos sur les pages produits. |
| Configuration du module | Afficher la galerie sur la page produit dans le pied de page ? | OUI | Affiche les photos sous le contenu du produit. |
| Configuration du module | Afficher la galerie dans le compte client ? | OUI | Crée une section « Mes photos » dans les comptes clients. |
| Configuration du module | Afficher le lien vers la galerie dans le bloc « Mon compte » ? | OUI | Ajoute un lien rapide vers la galerie dans le bloc Mon compte. |
| Configuration du module | Afficher la galerie dans la colonne de droite ? | NON | Affiche les photos dans la barre latérale droite. |
| Configuration du module | Afficher la galerie dans la colonne de gauche ? | NON | Affiche les photos dans la barre latérale gauche. |
| Configuration du module | Afficher la galerie sur la page d'accueil ? | OUI | Affiche les photos sur la page d'accueil de la boutique. |
| Configuration du module | Exclure des produits spécifiques de la galerie ? | Laisser vide | Empêche les photos pour les produits spécifiés. |
| Configuration du module | Activer les notifications par e-mail pour les nouveaux téléchargements ? | OUI | Envoie un e-mail à l'administrateur lors de nouveaux téléchargements de photos. |
| Configuration du module | Mises à jour MyPresta.eu | OUI | Active les vérifications automatiques des mises à jour. |

## 3. Dépannage pour les marchands et questions fréquemment posées (FAQ)

**Q1 : Mes photos de clients n'apparaissent pas après le téléchargement, ou la galerie semble vide.**
**R1 :**

- **Vérifiez la configuration du module :** Assurez-vous que les options d'affichage (par exemple, « Afficher la galerie sur la page produit sous forme d'onglet », « Afficher la galerie sur la page d'accueil ? ») sont activées dans les paramètres du module.
- **Videz le cache :** PrestaShop utilise la mise en cache. Allez dans **Paramètres avancés > Performances** et cliquez sur « Vider le cache » (ou « Vider le cache Smarty » et « Vider le cache » si les options sont séparées). Cela résout souvent les problèmes d'affichage.
- **Modération des images :** Certains modules ont un processus d'approbation. Vérifiez s'il existe une section d'administration (bien que ce module n'ait pas de contrôleur d'administration dédié, il peut avoir un statut d'approbation interne) où les photos doivent être approuvées avant d'être mises en ligne.
- **Permissions de fichiers :** Assurez-vous que votre dossier `img/customersgallery` (ou un chemin similaire où les images sont stockées) a les bonnes permissions d'écriture (généralement 755 ou 775). Votre hébergeur peut vous aider à ce sujet.

**Q2 : Les clients ont des difficultés à télécharger des photos, ou ils reçoivent un message d'erreur.**
**R2 :**

- **Vérifiez les limites de type et de taille de fichier :** Examinez les paramètres « Autoriser les fichiers JPEG/GIF/PNG/BMP ? » et « Taille maximale du fichier (en Mo) » dans la configuration du module. Assurez-vous que le fichier du client correspond aux types autorisés et respecte la limite de taille.
- **Limites PHP du serveur :** Même si le module autorise une grande taille de fichier, la configuration PHP de votre serveur (par exemple, `upload_max_filesize`, `post_max_size` dans `php.ini`) peut imposer une limite plus stricte. Contactez votre hébergeur pour vérifier et potentiellement augmenter ces limites si nécessaire.
- **Compatibilité du navigateur :** Demandez au client d'essayer un autre navigateur ou de vider le cache de son navigateur.
- **Erreurs JavaScript :** Ouvrez la console de développement de votre navigateur (F12) et vérifiez les erreurs JavaScript pendant le processus de téléchargement. Cela pourrait indiquer un conflit avec un autre module ou thème.

**Q3 : Les photos des clients semblent déformées ou mal dimensionnées dans la galerie.**
**R3 :**

- **Dimensions des miniatures :** Ajustez les paramètres « Hauteur de la vignette (px) » et « Largeur de la vignette (px) » dans la configuration du module. Expérimentez avec différentes valeurs pour trouver ce qui convient le mieux à votre thème. N'oubliez pas de vider le cache de votre PrestaShop après avoir effectué des modifications.
- **Conflits CSS :** Le CSS de votre thème pourrait annuler le style du module. Utilisez les outils de développement de votre navigateur (F12) pour inspecter les éléments et identifier les règles CSS conflictuelles. Vous pourriez avoir besoin d'un webmaster pour ajouter du CSS personnalisé à votre thème afin de corriger cela.

**Q4 : Le lien « Mes photos » n'apparaît pas dans le compte client ou le bloc « Mon compte ».**
**R4 :**

- **Accrochage du module :** Assurez-vous que le module est correctement accroché à `displayCustomerAccount` et `displayMyAccountBlock` (ou `displayMyAccountBlockFooter` selon votre thème). Vous pouvez vérifier cela dans **Design > Positions** (ou **Modules > Positions** dans les versions plus anciennes) et rechercher le module. S'il n'est pas accroché, essayez de réinstaller le module ou de l'accrocher manuellement.
- **Configuration du module :** Vérifiez à nouveau que « Afficher la galerie dans le compte client ? » et « Afficher le lien vers la galerie dans le bloc 'Mon compte' ? » sont activés dans les paramètres du module.
- **Connexion client :** Le lien « Mes photos » n'est visible que pour les clients connectés. Assurez-vous d'être connecté lors des tests.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

Cette section fournit un aperçu technique détaillé du module « Photos de produits par les clients », conçu pour les développeurs et les webmasters qui ont besoin de comprendre son fonctionnement interne, de personnaliser son comportement ou de résoudre des problèmes avancés.

### 4.1 Vue d'ensemble de l'architecture

Le module « Photos de produits par les clients » suit une architecture de module PrestaShop standard, tirant principalement parti des contrôleurs frontaux pour l'interaction utilisateur et des modèles Smarty pour le rendu. Il utilise la classe de module principale (`customersgallery.php`) pour la gestion de la configuration et l'enregistrement des hooks. Bien qu'il n'étende pas `ObjectModel` pour ses données de base, il interagit directement avec la base de données pour stocker les métadonnées des photos et s'appuie sur le système de fichiers de PrestaShop pour le stockage des images. AJAX est fortement utilisé pour le chargement dynamique du contenu et le téléchargement de photos, offrant une expérience utilisateur fluide sans rechargement complet de la page.

### 4.2 Contrôleurs (`controllers/`)

#### Contrôleurs Front-Office

Ces contrôleurs gèrent toutes les interactions côté client, y compris l'affichage des galeries, la gestion des photos des utilisateurs et le traitement des requêtes AJAX.

- **`controllers/front/ajax.php`**
  - **Nom de la classe :** `CustomersGalleryAjaxModuleFrontController` (étend `ModuleFrontController`)
  - **Responsabilité :** C'est le point d'accès principal pour toutes les opérations asynchrones (AJAX). Il gère :
    - Les téléchargements de photos depuis la page produit ou le compte client.
    - Les actions de vote (aimer/noter des photos).
    - Potentiellement les demandes de suppression ou de modération d'images depuis la section « Mes photos » du client.
    - Renvoie des réponses JSON indiquant le succès ou l'échec, ainsi que les données pertinentes.
- **`controllers/front/gallery.php`**
  - **Nom de la classe :** `CustomersGalleryGalleryModuleFrontController` (étend `ModuleFrontController`)
  - **Responsabilité :** Rend la page principale et dédiée de la galerie de photos des clients. Cette page affiche généralement toutes les photos de clients approuvées, éventuellement avec des options de pagination et de filtrage. Elle récupère les données des photos de la base de données et les attribue au modèle `gallery.tpl`.
- **`controllers/front/index.php`**
  - **Nom de la classe :** `CustomersGalleryIndexModuleFrontController` (étend `ModuleFrontController`)
  - **Responsabilité :** Ce contrôleur sert probablement de point d'entrée par défaut ou de secours pour les routes front-office du module. Il peut rediriger vers la galerie principale ou le contrôleur `myphotos` s'il est accédé directement sans paramètres spécifiques.
- **`controllers/front/myphotos.php`**
  - **Nom de la classe :** `CustomersGalleryMyPhotosModuleFrontController` (étend `ModuleFrontController`)
  - **Responsabilité :** Gère la section « Mes photos » dans le compte client. Il affiche les photos téléchargées par le client actuellement connecté, leur permet de gérer (par exemple, supprimer) leurs propres photos, et fournit potentiellement une interface de téléchargement. Il nécessite une authentification client.
- **`controllers/front/myvideos.php`**
  - **Nom de la classe :** `CustomersGalleryMyVideosModuleFrontController` (étend `ModuleFrontController`)
  - **Responsabilité :** Bien que le nom du module soit « Photos de produits par les clients », ce contrôleur suggère une fonctionnalité potentielle (ou prévue) pour le téléchargement de vidéos par les clients. Il fonctionnerait probablement de manière similaire à `myphotos.php` mais pour le contenu vidéo.

#### Contrôleurs d'administration Back-Office

Le module ne possède pas de contrôleurs d'administration dédiés. Toute la configuration est gérée via la méthode `getContent()` du module principal.

### 4.3 Classes et modèles de base (`classes/`)

Le module ne semble pas définir de classes personnalisées étendant `ObjectModel` dans un répertoire `classes/` dédié. Toute la logique de base pour l'interaction avec la base de données, le traitement des images et les règles métier est probablement encapsulée dans le fichier `customersgallery.php` principal et les contrôleurs frontaux. Cela signifie que les opérations de base de données sont gérées directement via des appels à `Db::getInstance()`.

### 4.4 Actifs JavaScript (`views/js/`)

- **`customersgallery/js/customersgallery.js`**
  - **Portée :** Front-office
  - **Détails :** C'est le principal JavaScript personnalisé pour le module. Il gère probablement :
    - Les appels AJAX pour les téléchargements de photos (par exemple, liaison aux soumissions de formulaires).
    - Les appels AJAX pour les mécanismes de vote.
    - Le chargement dynamique du contenu de la galerie.
    - La validation côté client pour les types et tailles de fichiers avant le téléchargement.
    - L'interaction avec la bibliothèque Fancybox pour les lightboxes d'images.
    - Les écouteurs d'événements pour la pagination, le filtrage et d'autres interactions de la galerie.
- **`customersgallery/js/fancybox.js`**
  - **Portée :** Front-office
  - **Détails :** C'est une bibliothèque tierce (Fancybox) utilisée pour afficher les images dans une superposition de lightbox réactive et élégante lorsqu'un utilisateur clique sur une miniature. Elle gère le zoom d'image, la navigation entre les images de la galerie et la présentation modale.
- **`customersgallery/js/script.js`**
  - **Portée :** Front-office
  - **Détails :** Il pourrait s'agir d'un script supplémentaire, potentiellement pour des améliorations générales de l'interface utilisateur, des animations spécifiques ou une gestion d'événements supplémentaire non couverte par `customersgallery.js`. Il pourrait également contenir des routines d'initialisation pour d'autres composants JS.
- **`customersgallery/lib/voucherengine/script.js`**
  - **Portée :** Front-office (potentiellement)
  - **Détails :** La présence de `voucherengine` suggère une intégration potentielle ou une fonctionnalité distincte pour la génération/gestion de bons, éventuellement en récompense pour les téléchargements de photos ou la participation à un concours. Ce script gérerait la logique côté client pour un tel système.

### 4.5 Feuilles de style CSS (`views/css/`)

- **`customersgallery/css/customersgallery.css`**
  - **Portée :** Style client Front-office
  - **Détails :** C'est la feuille de style principale pour les composants front-office du module. Elle stylise :
    - La mise en page de la galerie de photos (grille, flexbox).
    - Les conteneurs de photos individuels et les miniatures.
    - Les formulaires de téléchargement et les boutons.
    - Les contrôles de pagination.
    - Les éléments de vote (si non gérés par un CSS d'étoiles spécifique).
    - Les ajustements réactifs pour différentes tailles d'écran.
  - **Sélecteurs de classe CSS clés :** `.customer-photo-gallery`, `.cg-item`, `.cg-thumbnail`, `.cg-upload-form`, `.cg-vote-stars`
- **`customersgallery/css/fancybox.css`**
  - **Portée :** Style client Front-office
  - **Détails :** Feuille de style pour la bibliothèque de lightbox Fancybox, garantissant que la superposition d'image, les flèches de navigation, le bouton de fermeture et les légendes sont visuellement cohérents et attrayants.
- **`customersgallery/css/star-black.css`, `star-blue.css`, `star-gold.css`, `star-pink.css`, `star-red.css`, `star-whitered.css`, `star.css`**
  - **Portée :** Style client Front-office
  - **Détails :** Ce sont des feuilles de style spécifiques pour le système de vote par étoiles. Chaque fichier fournit une palette de couleurs ou un style visuel différent pour les icônes d'étoiles, permettant au marchand de choisir un design qui correspond à son thème. `star.css` est probablement le style de base, les autres fournissant des remplacements de couleur.
- **`customersgallery/lib/voucherengine/ps16.css`**
  - **Portée :** Front-office (potentiellement)
  - **Détails :** Cette feuille de style, trouvée dans le répertoire `voucherengine`, suggère un style spécifiquement pour les fonctionnalités liées aux bons, potentiellement optimisé pour les thèmes PrestaShop 1.6, mais probablement compatible ou adaptable pour les versions plus récentes.

### 4.6 Structure des modèles Smarty (`views/templates/`)

#### Modèles de hook (`views/templates/hook/`)

Ces modèles sont conçus pour être rendus lorsque des hooks PrestaShop spécifiques sont exécutés, intégrant le contenu du module dans diverses parties de la boutique.

- **`customersgallery/views/templates/hook/column-link.tpl`**
  - **Hook :** `displayLeftColumn`, `displayRightColumn`
  - **Sortie :** Un lien ou un bloc qui dirige les utilisateurs vers la galerie de photos principale des clients ou leur section « Mes photos », généralement placé dans les barres latérales.
- **`customersgallery/views/templates/hook/customer-my-account.tpl`**
  - **Hook :** `displayCustomerAccount`
  - **Sortie :** Un lien ou un bloc dans la page « Mon compte » du client, menant à sa section dédiée « Mes photos ».
- **`customersgallery/views/templates/hook/hookHome.tpl`**
  - **Hook :** `displayHome`
  - **Sortie :** Un bloc ou une section affichant une sélection de photos de clients sur la page d'accueil de la boutique, présentant souvent les téléchargements les plus récents ou les plus populaires.
- **`customersgallery/views/templates/hook/my-account.tpl`**
  - **Hook :** `displayMyAccountBlock`, `displayMyAccountBlockFooter`
  - **Sortie :** Un lien vers la section « Mes photos », intégré dans le bloc standard « Mon compte » qui apparaît dans les colonnes ou le pied de page pour les utilisateurs connectés.
- **`customersgallery/views/templates/hook/productfooter.tpl`**
  - **Hook :** `displayProductFooter`, `displayProductExtraContent`
  - **Sortie :** Une section affichant les photos des clients pour le produit actuel, située sous le contenu principal du produit sur la page produit.
- **`customersgallery/views/templates/hook/tab.tpl`**
  - **Hook :** `displayProductTab`
  - **Sortie :** Le code HTML pour un nouvel en-tête d'onglet (par exemple, « Photos des clients ») qui apparaît sur la page produit.
- **`customersgallery/views/templates/hook/tabContents.tpl`**
  - **Hook :** `displayProductTabContent`
  - **Sortie :** Le contenu réel affiché lorsque l'onglet « Photos des clients » est actif sur la page produit, montrant la galerie et potentiellement le formulaire de téléchargement pour ce produit spécifique.

#### Modèles personnalisés (`views/templates/custom/`)

Ces modèles sont probablement utilisés pour des formulaires spécifiques ou des parties du processus de téléchargement.

- **`customersgallery/views/templates/custom/upload-form.tpl`**
  - **Objectif :** Rend le formulaire HTML que les clients utilisent pour télécharger leurs photos de produits. Il peut s'agir d'une version plus simple ou d'une itération plus ancienne.
- **`customersgallery/views/templates/custom/upload-form2.tpl`**
  - **Objectif :** Probablement une version mise à jour ou alternative du formulaire de téléchargement, potentiellement avec un style, des fonctionnalités ou une compatibilité différents pour les versions plus récentes de PrestaShop.

#### Modèles Front-Office (`views/templates/front/`)

Ces modèles sont généralement utilisés par les contrôleurs frontaux du module pour rendre des pages complètes ou des sections importantes de la fonctionnalité du module.

- **`customersgallery/views/templates/front/gallery.tpl`**
  - **Objectif :** Le modèle principal pour la page dédiée de la galerie de photos des clients, affichant toutes les photos avec pagination.
- **`customersgallery/views/templates/front/gallery2.tpl`**
  - **Objectif :** Une version alternative ou mise à jour du modèle de galerie principal, offrant potentiellement différentes mises en page ou fonctionnalités.
- **`customersgallery/views/templates/front/gallery3.tpl`**
  - **Objectif :** Une autre version alternative ou mise à jour du modèle de galerie principal. Le module peut basculer entre ceux-ci en fonction de la configuration ou de la version de PrestaShop.
- **`customersgallery/views/templates/front/menu.tpl`**
  - **Objectif :** Rend un menu de navigation spécifique à la galerie de photos des clients, potentiellement pour le filtrage, le tri ou la navigation entre « Mes photos » et la galerie principale.
- **`customersgallery/views/templates/front/my-photos.tpl`**
  - **Objectif :** Rend la page « Mes photos » dans le compte client, affichant leurs images téléchargées et les options de gestion.
- **`customersgallery/views/templates/front/my-videos-16.tpl`**
  - **Objectif :** Modèle pour la section « Mes vidéos », spécifiquement conçu ou optimisé pour PrestaShop 1.6, si la fonctionnalité de téléchargement de vidéos est activée.
- **`customersgallery/views/templates/front/video-upload.tpl`**
  - **Objectif :** Rend le formulaire permettant aux clients de télécharger des vidéos, si cette fonctionnalité est active.

### 4.7 Schéma de la base de données et carte des hooks

#### Tables de la base de données

Le module ne définit pas explicitement de fichiers SQL personnalisés, mais en fonction de ses fonctionnalités, il interagira avec la base de données.

- **Tables personnalisées (probablement créées lors de `install()`):**
  - `_customersgallery` : Stocke les métadonnées de chaque photo téléchargée (par exemple, `id_customersgallery`, `id_customer`, `id_product`, `filename`, `date_add`, `approved`, `votes`, `active`).
  - `_customersgallery_vote` : Stocke les enregistrements des votes des clients (par exemple, `id_customersgallery_vote`, `id_customersgallery`, `id_customer`, `ip_address`, `date_add`).
- **Enregistrements de configuration (stockés dans `ps_configuration`):**
  - `CG_LAST_TAB`, `CG_ALLOW_JPEG`, `CG_ALLOW_GIF`, `CG_ALLOW_PNG`, `CG_ALLOW_BMP`, `mypresta_updates`, `CG_PAGINATION`, `CG_ALLOW_UNLOGGED`, `CG_MAX_FILE_SIZE`, `CG_PRODUCTTAB`, `cg_productTabM`, `CG_PRODUCTFOOTER`, `CG_CUSTOMERACCOUNT`, `CG_MYACCOUNTBLOCK`, `CG_THUMBHEIGHT`, `CG_THUMBWIDTH`, `CG_FUPLOADON`, `CG_GALLERY`, `CG_RIGHTCOL`, `CG_LEFTCOL`, `CG_NTF`, `update_`, `updatev_`, `cg_altered1`, `cg_altered2`, `cg_hpg_nb`, `cg_hpg_o`, `cg_contest`, `cg_excludeproduct`, `CG_CUSTOMERACCOUNTV`, `CG_MYACCOUNTBLOCKV`, `CG_voting`, `CG_VOTE_STAR`, `CGV_voting`, `cg_unl_voting`.

#### Tableau des hooks enregistrés

| Nom du hook | Moment d'exécution | Objectif technique |
| --- | --- | --- |
| `displayHeader` | Dans la section `<head>` de chaque page. | Injecte les actifs CSS et JavaScript requis par le module (par exemple, `customersgallery.css`, `fancybox.js`, `customersgallery.js`). |
| `displayMyAccountBlock` | Dans le bloc « Mon compte » du client (souvent dans la colonne gauche/droite ou le pied de page). | Ajoute un lien vers la section « Mes photos » du client. |
| `displayLeftColumn` | Dans la barre latérale gauche de la boutique. | Affiche un bloc de photos de clients ou un lien vers la galerie. |
| `displayRightColumn` | Dans la barre latérale droite de la boutique. | Affiche un bloc de photos de clients ou un lien vers la galerie. |
| `displayHome` | Sur la page d'accueil de la boutique. | Affiche une section de photos de clients (les plus récentes, les plus populaires). |
| `displayProductTab` | Sur la page produit, pour ajouter de nouveaux onglets. | Ajoute l'en-tête de l'onglet « Photos des clients ». |
| `displayProductTabContent` | Sur la page produit, pour le contenu d'un onglet. | Affiche la galerie de photos des clients et le formulaire de téléchargement dans l'onglet « Photos des clients ». |
| `displayProductFooter` | En bas de la page produit. | Affiche une section de photos de clients pour le produit actuel. |
| `displayProductExtraContent` | Un autre hook pour du contenu supplémentaire sur la page produit. | Peut être utilisé comme emplacement alternatif ou additionnel pour le contenu photo spécifique au produit. |
| `displayCustomerAccount` | Sur la page « Mon compte » du client. | Ajoute un lien vers la section « Mes photos » pour le client connecté. |
| `displayLeftColumnProduct` | Dans la colonne de gauche spécifiquement sur les pages produits. | Affiche un bloc de photos de clients ou un lien vers la galerie sur les pages produits. |
| `displayRightColumnProduct` | Dans la colonne de droite spécifiquement sur les pages produits. | Affiche un bloc de photos de clients ou un lien vers la galerie sur les pages produits. |
| `displayMyAccountBlockFooter` | Dans la version pied de page du bloc « Mon compte ». | Ajoute un lien vers la section « Mes photos » du client dans le pied de page. |
| `actionValidateOrder` | Après qu'une commande a été validée avec succès. | (Potentiel) Pourrait être utilisé pour déclencher un e-mail au client l'encourageant à télécharger des photos pour les produits achetés. |

## 5. Support officiel et mises à jour

Pour le support officiel, les mises à jour du module et toute assistance supplémentaire concernant le module « Photos de produits par les clients », veuillez vous référer à votre compte client MyPresta.eu. Vous pouvez vous connecter sur [Historique des commandes et téléchargements MyPresta.eu](https://mypresta.eu/my-account/orders/) pour accéder aux dernières versions et soumettre des tickets de support.
