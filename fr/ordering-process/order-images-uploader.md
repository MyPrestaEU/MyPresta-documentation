---
title: "Téléchargeur d'images de commande - Manuel du marchand et guide de configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop Téléchargeur d'images de commande par MyPresta.eu."
sidebar:
  label: "Téléchargeur d'images de commande - Manuel du marchand et guide de configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Order images uploader sur MyPresta.eu](https://mypresta.eu/modules/ordering-process/order-images-uploader.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/ordering-process/order-images-uploader/)
>
> ---


# Téléchargeur d'images de commande

## 1. Exigences et compatibilité

- **Versions PrestaShop prises en charge** : PrestaShop 1.5.x, 1.6.x, 1.7.x, 8.x, 9.x
- **Compatibilité PHP** : PHP 5.6 - 8.5
- **Exigences d'hébergement** : Les extensions PHP standard (cURL, JSON, OpenSSL) sont généralement suffisantes. Assurez-vous que votre serveur a des limites de téléchargement de fichiers adéquates configurées dans `php.ini` (par exemple, `upload_max_filesize`, `post_max_size`) pour prendre en charge la taille des fichiers que vos clients pourraient télécharger.

## 2. Guide de configuration complet (chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer > Téléchargeur d'images de commande)

Ceci est l'écran de configuration principal où vous contrôlez le comportement général et l'apparence du module.

#### Paramètres généraux

- **Activer le module :**

  - **Ce que fait ce paramètre :** C'est l'interrupteur principal pour activer ou désactiver la fonctionnalité complète du module.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé :* Les fonctionnalités du module (formulaires de téléchargement, gestion des fichiers) seront actives sur votre front office et votre back office.
    - *Lorsqu'il est désactivé :* Toutes les fonctionnalités du module seront masquées aux clients et aux administrateurs, ce qui mettra en pause son fonctionnement.
  - **Valeur recommandée :** OUI
  - **Scénario/exemple pour le marchand :** Si vous configurez le module pour la première fois, activez-le pour le tester. Si vous devez désactiver temporairement les téléchargements de fichiers pour la maintenance, réglez-le sur NON.
- **Autoriser les clients à télécharger des fichiers :**

  - **Ce que fait ce paramètre :** Détermine si les clients sont autorisés à télécharger des fichiers.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé :* Les clients verront les formulaires de téléchargement et pourront soumettre des fichiers.
    - *Lorsqu'il est désactivé :* Les clients ne verront aucune option de téléchargement, même si le module est activé.
  - **Valeur recommandée :** OUI
  - **Scénario/exemple pour le marchand :** Si vous souhaitez uniquement utiliser le module pour la gestion interne des fichiers (par exemple, les administrateurs téléchargeant des fichiers vers les commandes), vous pouvez le désactiver. Pour la plupart des cas d'utilisation, les clients doivent télécharger des fichiers, alors gardez-le activé.
- **Autoriser les clients invités à télécharger des fichiers :**

  - **Ce que fait ce paramètre :** Contrôle si les clients non connectés (invités) peuvent télécharger des fichiers.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé :* Les invités peuvent télécharger des fichiers, généralement associés à leur panier ou à leur commande lors du paiement.
    - *Lorsqu'il est désactivé :* Seuls les clients enregistrés et connectés peuvent télécharger des fichiers.
  - **Valeur recommandée :** OUI (si vous autorisez le paiement en tant qu'invité et avez besoin de fichiers des invités)
  - **Scénario/exemple pour le marchand :** Si votre boutique autorise le paiement en tant qu'invité et nécessite le téléchargement de fichiers pour les commandes des invités (par exemple, un travail d'impression rapide), activez ceci. Si vous souhaitez forcer les clients à s'enregistrer pour télécharger des fichiers, désactivez-le.
- **Autoriser les clients à supprimer des fichiers :**

  - **Ce que fait ce paramètre :** Donne aux clients la possibilité de supprimer les fichiers qu'ils ont précédemment téléchargés.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé :* Les clients verront une option « Supprimer » à côté de leurs fichiers téléchargés dans leur compte.
    - *Lorsqu'il est désactivé :* Les clients peuvent télécharger mais ne peuvent pas supprimer de fichiers. Seuls les administrateurs peuvent les supprimer.
  - **Valeur recommandée :** NON (sauf si vous faites confiance aux clients pour gérer parfaitement leurs fichiers)
  - **Scénario/exemple pour le marchand :** Pour les commandes d'impression personnalisées, vous pouvez désactiver ceci pour empêcher les clients de supprimer accidentellement un fichier déjà en production. Si les fichiers sont temporaires ou facilement remplaçables, vous pouvez l'activer pour la commodité du client.
- **Autoriser les clients à télécharger des fichiers :**

  - **Ce que fait ce paramètre :** Détermine si les clients peuvent télécharger les fichiers qu'ils (ou vous) ont téléchargés vers leurs commandes.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé :* Les clients peuvent cliquer pour télécharger leurs fichiers depuis leur historique de commandes.
    - *Lorsqu'il est désactivé :* Les clients ne peuvent pas télécharger de fichiers.
  - **Valeur recommandée :** OUI (pour la transparence et l'accès client)
  - **Scénario/exemple pour le marchand :** Si vous téléchargez une épreuve ou une conception finale pour que le client la révise, l'activation de ceci lui permet de la télécharger.
- **Autoriser les clients à télécharger des fichiers vers les commandes :**

  - **Ce que fait ce paramètre :** Contrôle spécifiquement si les clients peuvent télécharger des fichiers *après* qu'une commande a été passée, depuis leur page d'historique des commandes.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé :* Une option de téléchargement apparaîtra sur la page de détails de la commande individuelle du client dans « Mon compte ».
    - *Lorsqu'il est désactivé :* Les clients ne peuvent télécharger des fichiers que pendant le processus de panier/paiement ou sur les pages produits, pas vers des commandes existantes.
  - **Valeur recommandée :** OUI (fortement recommandé pour la flexibilité)
  - **Scénario/exemple pour le marchand :** Un client a oublié de télécharger un logo spécifique après avoir passé une commande de t-shirts personnalisés. Avec cette option activée, il peut facilement l'ajouter plus tard.
- **Autoriser les clients à télécharger des fichiers vers les paniers :**

  - **Ce que fait ce paramètre :** Contrôle si les clients peuvent télécharger des fichiers tant que leurs articles sont encore dans le panier.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé :* Une option de téléchargement apparaîtra sur la page du panier.
    - *Lorsqu'il est désactivé :* Les clients ne peuvent pas télécharger de fichiers vers leur panier.
  - **Valeur recommandée :** OUI (pratique pour les clients)
  - **Scénario/exemple pour le marchand :** Un client est en train de créer un album photo personnalisé. Il peut télécharger des photos directement dans le panier avant de passer à la caisse.
- **Autoriser les clients à télécharger des fichiers vers les produits :**

  - **Ce que fait ce paramètre :** Contrôle si les clients peuvent télécharger des fichiers directement sur les pages produits individuelles.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé :* Une option de téléchargement apparaîtra sur les pages produits.
    - *Lorsqu'il est désactivé :* Les clients ne peuvent pas télécharger de fichiers sur les pages produits.
  - **Valeur recommandée :** OUI (pour les produits hautement personnalisables)
  - **Scénario/exemple pour le marchand :** Pour une tasse personnalisée, le client peut télécharger la photo souhaitée directement sur la page produit de la tasse avant de l'ajouter au panier.
- **Autoriser les clients à télécharger des fichiers vers le compte client :**

  - **Ce que fait ce paramètre :** Active une section dédiée « Mes fichiers » dans le compte du client, lui permettant de télécharger et de gérer des fichiers qui ne sont pas nécessairement liés à une commande ou un panier spécifique.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé :* Un nouvel élément de menu « Mes fichiers » apparaît dans le tableau de bord « Mon compte » du client.
    - *Lorsqu'il est désactivé :* Cette section est masquée.
  - **Valeur recommandée :** NON (sauf si vous avez un besoin spécifique de stockage de fichiers général)
  - **Scénario/exemple pour le marchand :** Si vous souhaitez que les clients pré-téléchargent des ressources courantes (par exemple, le logo de leur entreprise) qu'ils pourraient utiliser pour plusieurs commandes futures, cela pourrait être utile. Sinon, cela pourrait ajouter une complexité inutile.
- **Forcer les clients à télécharger des fichiers vers les commandes :**

  - **Ce que fait ce paramètre :** Rend le téléchargement de fichiers obligatoire pour qu'une commande soit complétée. Si aucun fichier n'est téléchargé, le client ne peut pas continuer.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé :* Les clients seront bloqués pour finaliser la commande tant qu'ils n'auront pas téléchargé au moins un fichier.
    - *Lorsqu'il est désactivé :* Le téléchargement de fichiers est facultatif.
  - **Valeur recommandée :** NON (n'activez que si absolument critique pour chaque commande)
  - **Scénario/exemple pour le marchand :** Pour une imprimerie où *chaque* commande nécessite un fichier de conception, l'activation de ceci garantit qu'aucune commande ne passe sans les ressources nécessaires. Soyez prudent, car cela peut avoir un impact sur les taux de conversion si tous les produits ne nécessitent pas de fichier.
- **Forcer les clients à télécharger des fichiers vers les produits :**

  - **Ce que fait ce paramètre :** Rend le téléchargement de fichiers obligatoire pour qu'un produit soit ajouté au panier.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé :* Les clients ne peuvent pas ajouter un produit au panier tant qu'ils n'ont pas téléchargé au moins un fichier pour ce produit.
    - *Lorsqu'il est désactivé :* Le téléchargement de fichiers est facultatif sur la page produit.
  - **Valeur recommandée :** NON (n'activez que pour les produits qui sont *toujours* personnalisés)
  - **Scénario/exemple pour le marchand :** Pour un produit « Créez votre propre T-shirt », cela garantit que le client fournit sa conception avant de l'ajouter au panier.
- **Forcer les clients à télécharger des fichiers vers les paniers :**

  - **Ce que fait ce paramètre :** Rend le téléchargement de fichiers obligatoire pour que l'ensemble du panier soit traité.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé :* Les clients ne peuvent pas passer du panier à la caisse tant qu'ils n'ont pas téléchargé au moins un fichier pour le panier.
    - *Lorsqu'il est désactivé :* Le téléchargement de fichiers est facultatif sur la page du panier.
  - **Valeur recommandée :** NON (à utiliser avec une extrême prudence, peut gravement affecter la conversion)
  - **Scénario/exemple pour le marchand :** Ceci est rarement recommandé, sauf si *chaque commande* de votre boutique nécessite un téléchargement de fichier général. Il est généralement préférable de forcer les téléchargements au niveau du produit ou de la commande si nécessaire.
- **Extensions de fichier autorisées (séparées par des virgules) :**

  - **Ce que fait ce paramètre :** Définit les types de fichiers que les clients sont autorisés à télécharger.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est modifié :* Seuls les fichiers avec les extensions spécifiées (par exemple, `jpg,png,gif,pdf`) seront acceptés. Tout autre type de fichier sera rejeté.
  - **Valeur recommandée :** `jpg,jpeg,png,gif,pdf,doc,docx,xls,xlsx,txt` (ajuster en fonction de vos besoins)
  - **Scénario/exemple pour le marchand :** Une imprimerie pourrait autoriser `jpg,png,pdf,ai,eps`. Une bijouterie personnalisée pourrait n'avoir besoin que de `jpg,png`. La limitation des extensions améliore la sécurité et garantit que vous recevez des fichiers utilisables.
- **Taille maximale du fichier (en Mo) :**

  - **Ce que fait ce paramètre :** Définit la limite supérieure pour la taille d'un seul fichier qu'un client peut télécharger.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est modifié :* Les fichiers plus grands que cette limite seront rejetés.
  - **Valeur recommandée :** `10` (ou plus si vous vous attendez à des fichiers de conception volumineux)
  - **Scénario/exemple pour le marchand :** Si les clients téléchargent des images haute résolution ou des fichiers de conception volumineux, vous pouvez définir cette valeur sur `50` ou `100`. Sachez que des fichiers très volumineux peuvent ralentir les téléchargements et consommer de l'espace serveur. Assurez-vous que les paramètres `upload_max_filesize` et `post_max_size` de votre serveur `php.ini` sont également configurés pour prendre en charge cette valeur.
- **Nombre maximal de fichiers par commande :**

  - **Ce que fait ce paramètre :** Limite le nombre de fichiers individuels qu'un client peut télécharger pour une seule commande.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est modifié :* Les clients seront empêchés de télécharger plus de fichiers une fois qu'ils auront atteint cette limite pour une commande donnée.
  - **Valeur recommandée :** `5` (ou plus si de nombreux fichiers sont attendus)
  - **Scénario/exemple pour le marchand :** Si un client commande 10 articles personnalisés différents, et que chacun nécessite un fichier, vous pouvez définir cette valeur sur `10` ou `20`. Si seulement un ou deux fichiers sont généralement nécessaires, un nombre inférieur évite l'encombrement.
- **Nombre maximal de fichiers par produit :**

  - **Ce que fait ce paramètre :** Limite le nombre de fichiers individuels qu'un client peut télécharger pour un seul produit.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est modifié :* Les clients seront empêchés de télécharger plus de fichiers une fois qu'ils auront atteint cette limite pour un produit donné.
  - **Valeur recommandée :** `1` (si chaque produit nécessite une conception) ou `5` (si plusieurs angles/versions sont nécessaires)
  - **Scénario/exemple pour le marchand :** Pour un portrait personnalisé, vous pouvez autoriser `3` fichiers (photos de référence avant, côté, arrière). Pour une simple impression de logo, `1` fichier est suffisant.
- **Nombre maximal de fichiers par panier :**

  - **Ce que fait ce paramètre :** Limite le nombre de fichiers individuels qu'un client peut télécharger pour l'ensemble du panier.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est modifié :* Les clients seront empêchés de télécharger plus de fichiers une fois qu'ils auront atteint cette limite pour le panier.
  - **Valeur recommandée :** `5` (ou plus si de nombreux fichiers généraux sont attendus)
  - **Scénario/exemple pour le marchand :** Si un client télécharge un document d'instructions générales qui s'applique à l'ensemble du panier, vous pouvez définir cette valeur sur `1`.
- **Afficher le formulaire de téléchargement sur la page produit :**

  - **Ce que fait ce paramètre :** Contrôle l'emplacement du formulaire de téléchargement sur la page produit.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est défini sur « Dans l'onglet produit » :* Le formulaire de téléchargement apparaîtra dans un nouvel onglet sur la page produit (par exemple, à côté de « Description » ou « Fiche technique »).
    - *Lorsqu'il est défini sur « Sous la description du produit » :* Le formulaire de téléchargement apparaîtra directement sous la description principale du produit.
    - *Lorsqu'il est défini sur « Sous le prix du produit » :* Le formulaire de téléchargement apparaîtra près du prix du produit, généralement au-dessus du bouton « Ajouter au panier ».
  - **Valeur recommandée :** « Dans l'onglet produit » (pour un affichage moins intrusif) ou « Sous le prix du produit » (pour une grande visibilité)
  - **Scénario/exemple pour le marchand :** Pour un produit où le téléchargement de fichiers est critique, le placer « Sous le prix du produit » le rend très visible. Pour les téléchargements moins critiques, un « onglet produit » maintient les informations principales du produit propres.
- **Afficher le formulaire de téléchargement sur la page du panier :**

  - **Ce que fait ce paramètre :** Contrôle l'emplacement du formulaire de téléchargement sur la page du panier.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est défini sur « Dans le bloc récapitulatif » :* Le formulaire de téléchargement apparaîtra dans la zone principale du récapitulatif du panier.
    - *Lorsqu'il est défini sur « Sous le récapitulatif du panier » :* Le formulaire de téléchargement apparaîtra sous l'ensemble du récapitulatif du panier.
  - **Valeur recommandée :** « Sous le récapitulatif du panier » (offre souvent plus d'espace)
  - **Scénario/exemple pour le marchand :** Si les clients doivent télécharger un fichier général pour l'ensemble de la commande, le placer clairement sur la page du panier garantit qu'ils ne le manquent pas avant le paiement.
- **Afficher le formulaire de téléchargement sur la page d'historique des commandes :**

  - **Ce que fait ce paramètre :** Contrôle l'emplacement du formulaire de téléchargement sur la page de détails de la commande individuelle du client.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est défini sur « Dans le bloc de détails de la commande » :* Le formulaire de téléchargement apparaîtra dans la section principale des détails de la commande.
    - *Lorsqu'il est défini sur « Sous les détails de la commande » :* Le formulaire de téléchargement apparaîtra sous les détails de la commande.
  - **Valeur recommandée :** « Dans le bloc de détails de la commande » (pour une association plus étroite avec la commande)
  - **Scénario/exemple pour le marchand :** Après qu'un client a passé une commande, il peut facilement trouver l'option de téléchargement sur sa page d'historique des commandes pour ajouter les fichiers manquants.
- **Afficher le formulaire de téléchargement sur la page Mon compte :**

  - **Ce que fait ce paramètre :** Contrôle si un lien dédié « Mes fichiers » apparaît dans le tableau de bord « Mon compte » du client.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé :* Un lien apparaîtra, menant à une page où les clients peuvent gérer les fichiers généraux.
    - *Lorsqu'il est désactivé :* Le lien n'apparaîtra pas.
  - **Valeur recommandée :** NON (sauf si vous avez activé « Autoriser les clients à télécharger des fichiers vers le compte client » et que vous avez besoin de cette fonctionnalité)
  - **Scénario/exemple pour le marchand :** Si vous souhaitez que les clients aient un endroit central pour tous leurs fichiers téléchargés, indépendamment des commandes spécifiques, activez ceci.
- **Afficher le formulaire de téléchargement dans le pied de page :**

  - **Ce que fait ce paramètre :** Ajoute un lien vers le gestionnaire de téléchargement de fichiers dans le pied de page de votre boutique.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé :* Un lien apparaîtra dans le pied de page, offrant un autre point d'accès au gestionnaire de fichiers.
    - *Lorsqu'il est désactivé :* Aucun lien dans le pied de page.
  - **Valeur recommandée :** NON (sauf si vous souhaitez une grande visibilité pour le gestionnaire de fichiers)
  - **Scénario/exemple pour le marchand :** Si les téléchargements de fichiers sont un élément central de votre entreprise, un lien dans le pied de page peut le rendre facilement accessible depuis n'importe quelle page.
- **Afficher le formulaire de téléchargement dans la colonne de gauche :**

  - **Ce que fait ce paramètre :** Ajoute un lien vers le gestionnaire de téléchargement de fichiers dans la colonne de gauche de votre boutique.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé :* Un lien apparaîtra dans la colonne de gauche.
    - *Lorsqu'il est désactivé :* Aucun lien dans la colonne de gauche.
  - **Valeur recommandée :** NON (sauf si vous souhaitez une grande visibilité pour le gestionnaire de fichiers)
  - **Scénario/exemple pour le marchand :** Similaire au pied de page, cela offre un autre point d'accès proéminent.
- **Afficher le formulaire de téléchargement dans la colonne de droite :**

  - **Ce que fait ce paramètre :** Ajoute un lien vers le gestionnaire de téléchargement de fichiers dans la colonne de droite de votre boutique.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé :* Un lien apparaîtra dans la colonne de droite.
    - *Lorsqu'il est désactivé :* Aucun lien dans la colonne de droite.
  - **Valeur recommandée :** NON (sauf si vous souhaitez une grande visibilité pour le gestionnaire de fichiers)
  - **Scénario/exemple pour le marchand :** Similaire au pied de page et à la colonne de gauche, cela offre un autre point d'accès proéminent.
- **Envoyer un e-mail au client concernant un nouveau fichier :**

  - **Ce que fait ce paramètre :** Contrôle si une notification par e-mail est envoyée au client lorsqu'un nouveau fichier est téléchargé sur sa commande par un administrateur.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé :* Les clients reçoivent une notification par e-mail.
    - *Lorsqu'il est désactivé :* Aucune notification par e-mail n'est envoyée.
  - **Valeur recommandée :** OUI (pour une bonne communication client)
  - **Scénario/exemple pour le marchand :** Si vous téléchargez une épreuve de conception pour que le client la révise, il en sera informé par e-mail.
- **Envoyer un e-mail au propriétaire de la boutique concernant un nouveau fichier :**

  - **Ce que fait ce paramètre :** Contrôle si une notification par e-mail est envoyée au propriétaire de la boutique (ou à l'e-mail de la boutique configuré) lorsqu'un client télécharge un nouveau fichier.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé :* Vous (le propriétaire de la boutique) recevez une notification par e-mail.
    - *Lorsqu'il est désactivé :* Aucune notification par e-mail n'est envoyée.
  - **Valeur recommandée :** OUI (fortement recommandé pour un traitement rapide)
  - **Scénario/exemple pour le marchand :** Un client télécharge un fichier de conception critique. Vous recevez un e-mail immédiatement, ce qui vous permet de commencer à traiter la commande sans délai.
- **Joindre les fichiers à l'e-mail de confirmation de commande :**

  - **Ce que fait ce paramètre :** Détermine si les fichiers téléchargés par le client sont joints à l'e-mail de confirmation de commande standard de PrestaShop.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé :* Les fichiers seront inclus en tant que pièces jointes dans l'e-mail de confirmation de commande envoyé au client.
    - *Lorsqu'il est désactivé :* Les fichiers ne sont pas joints à l'e-mail.
  - **Valeur recommandée :** NON (sauf si les fichiers sont petits et peu nombreux, car les pièces jointes volumineuses peuvent causer des problèmes de livraison d'e-mails)
  - **Scénario/exemple pour le marchand :** Si les clients téléchargent de très petits fichiers non critiques, vous pouvez activer ceci. Pour des fichiers plus volumineux ou nombreux, il est préférable de laisser les clients les télécharger depuis leur compte pour éviter les problèmes de serveur de messagerie.
- **Joindre les fichiers à l'e-mail du service client :**

  - **Ce que fait ce paramètre :** Détermine si les fichiers téléchargés par le client sont joints à l'e-mail envoyé au client lorsqu'un administrateur télécharge un nouveau fichier.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé :* Les fichiers seront inclus en tant que pièces jointes dans l'e-mail.
    - *Lorsqu'il est désactivé :* Les fichiers ne sont pas joints à l'e-mail.
  - **Valeur recommandée :** NON (similaire à la confirmation de commande, évitez les pièces jointes volumineuses)
  - **Scénario/exemple pour le marchand :** Si vous téléchargez une petite épreuve pour le client, vous pouvez activer ceci. Pour des fichiers plus volumineux, dirigez-les vers le téléchargement depuis leur compte.
- **Joindre les fichiers à l'e-mail du propriétaire de la boutique :**

  - **Ce que fait ce paramètre :** Détermine si les fichiers téléchargés par le client sont joints à l'e-mail envoyé au propriétaire de la boutique lorsqu'un nouveau fichier est téléchargé par un client.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé :* Les fichiers seront inclus en tant que pièces jointes dans la notification par e-mail que vous recevez.
    - *Lorsqu'il est désactivé :* Les fichiers ne sont pas joints à l'e-mail.
  - **Valeur recommandée :** NON (sauf si les fichiers sont petits et peu nombreux, car les pièces jointes volumineuses peuvent encombrer votre boîte de réception)
  - **Scénario/exemple pour le marchand :** Si vous préférez télécharger les fichiers directement depuis le back office, désactivez ceci. Si vous ne vous attendez qu'à de très petits fichiers et que vous les voulez immédiatement dans votre boîte de réception, activez-le.
- **Activer les commentaires pour les fichiers :**

  - **Ce que fait ce paramètre :** Permet aux clients et aux administrateurs d'ajouter des commentaires à chaque fichier téléchargé.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé :* Un champ de texte apparaîtra à côté de chaque fichier pour ajouter des notes ou des instructions.
    - *Lorsqu'il est désactivé :* Aucun champ de commentaire ne sera disponible.
  - **Valeur recommandée :** OUI (pour une meilleure communication et un meilleur contexte)
  - **Scénario/exemple pour le marchand :** Un client télécharge un logo et ajoute un commentaire : « Utilisez ce logo, mais veuillez changer la couleur en bleu. » Cela fournit un contexte crucial.
- **Activer les commentaires pour les paniers :**

  - **Ce que fait ce paramètre :** Permet aux clients d'ajouter un commentaire général à leur panier.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé :* Un champ de texte apparaîtra sur la page du panier pour les commentaires généraux du panier.
    - *Lorsqu'il est désactivé :* Aucun champ de commentaire général du panier.
  - **Valeur recommandée :** OUI (utile pour les instructions générales)
  - **Scénario/exemple pour le marchand :** Un client peut ajouter un commentaire comme : « Veuillez vous assurer que tous les articles sont emballés ensemble. »
- **Activer les commentaires pour les commandes :**

  - **Ce que fait ce paramètre :** Permet aux clients d'ajouter un commentaire général à leur commande.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé :* Un champ de texte apparaîtra sur la page de détails de la commande pour les commentaires généraux de la commande.
    - *Lorsqu'il est désactivé :* Aucun champ de commentaire général de la commande.
  - **Valeur recommandée :** OUI (utile pour les instructions post-commande)
  - **Scénario/exemple pour le marchand :** Un client peut ajouter un commentaire après avoir passé une commande : « J'ai besoin que cela soit livré avant vendredi, s'il vous plaît. »
- **Activer les commentaires pour les produits :**

  - **Ce que fait ce paramètre :** Permet aux clients d'ajouter un commentaire spécifique à un produit.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé :* Un champ de texte apparaîtra sur la page produit pour les commentaires spécifiques au produit.
    - *Lorsqu'il est désactivé :* Aucun champ de commentaire spécifique au produit.
  - **Valeur recommandée :** OUI (utile pour les instructions de personnalisation de produit)
  - **Scénario/exemple pour le marchand :** Un client commandant une gravure personnalisée peut ajouter un commentaire : « Gravez 'Joyeux Anniversaire John' en police script. »
- **Activer l'onglet « Mes fichiers » dans le compte client :**

  - **Ce que fait ce paramètre :** Ajoute un onglet dédié « Mes fichiers » au tableau de bord du compte client.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé :* Un nouvel onglet apparaît, permettant aux clients de visualiser et de gérer tous leurs fichiers téléchargés en un seul endroit.
    - *Lorsqu'il est désactivé :* L'onglet est masqué.
  - **Valeur recommandée :** OUI (améliore l'expérience client en centralisant les fichiers)
  - **Scénario/exemple pour le marchand :** Les clients peuvent facilement trouver toutes leurs conceptions, épreuves ou documents téléchargés dans un seul endroit pratique.
- **Activer l'onglet « Mes fichiers » sur la page d'historique des commandes :**

  - **Ce que fait ce paramètre :** Ajoute une section dédiée « Mes fichiers » dans la page d'historique des commandes pour chaque commande spécifique.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé :* Une section apparaît dans la page de détails de chaque commande, affichant les fichiers liés à cette commande spécifique.
    - *Lorsqu'il est désactivé :* Cette section est masquée.
  - **Valeur recommandée :** OUI (crucial pour la gestion des fichiers spécifiques aux commandes)
  - **Scénario/exemple pour le marchand :** Lorsqu'un client consulte une commande passée, il peut immédiatement voir tous les fichiers qu'il a téléchargés pour cette commande.
- **Activer l'onglet « Mes fichiers » sur la page produit :**

  - **Ce que fait ce paramètre :** Ajoute une section dédiée « Mes fichiers » dans la page produit.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé :* Une section apparaît sur la page produit, affichant les fichiers liés à ce produit spécifique.
    - *Lorsqu'il est désactivé :* Cette section est masquée.
  - **Valeur recommandée :** NON (sauf si vous avez un cas d'utilisation très spécifique, car cela peut encombrer les pages produits)
  - **Scénario/exemple pour le marchand :** Cela pourrait être utile si les clients commandent fréquemment le même produit personnalisé et ont besoin de se référer aux fichiers précédemment téléchargés pour ce produit.
- **Activer l'onglet « Mes fichiers » sur la page du panier :**

  - **Ce que fait ce paramètre :** Ajoute une section dédiée « Mes fichiers » dans la page du panier.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé :* Une section apparaît sur la page du panier, affichant les fichiers liés aux articles du panier.
    - *Lorsqu'il est désactivé :* Cette section est masquée.
  - **Valeur recommandée :** NON (sauf si vous avez un cas d'utilisation très spécifique, car cela peut encombrer les pages du panier)
  - **Scénario/exemple pour le marchand :** Si les clients créent une commande complexe avec de nombreux fichiers, cela pourrait fournir un aperçu de tous les fichiers actuellement associés au panier.
- **Afficher le bouton de téléchargement de fichier sur la page produit :**

  - **Ce que fait ce paramètre :** Contrôle la visibilité du bouton « Télécharger un fichier » sur les pages produits.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé :* Le bouton sera visible.
    - *Lorsqu'il est désactivé :* Le bouton sera masqué.
  - **Valeur recommandée :** OUI (si vous autorisez les téléchargements de fichiers produits)
  - **Scénario/exemple pour le marchand :** Si vous souhaitez que les clients téléchargent des fichiers pour la personnalisation des produits, ce bouton doit être visible.
- **Afficher le bouton de téléchargement de fichier sur la page du panier :**

  - **Ce que fait ce paramètre :** Contrôle la visibilité du bouton « Télécharger un fichier » sur la page du panier.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé :* Le bouton sera visible.
    - *Lorsqu'il est désactivé :* Le bouton sera masqué.
  - **Valeur recommandée :** OUI (si vous autorisez les téléchargements de fichiers du panier)
  - **Scénario/exemple pour le marchand :** Si les clients doivent télécharger un fichier général pour l'ensemble de leur commande, ce bouton doit être visible sur la page du panier.
- **Afficher le bouton de téléchargement de fichier sur la page d'historique des commandes :**

  - **Ce que fait ce paramètre :** Contrôle la visibilité du bouton « Télécharger un fichier » sur la page de détails de la commande du client.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé :* Le bouton sera visible.
    - *Lorsqu'il est désactivé :* Le bouton sera masqué.
  - **Valeur recommandée :** OUI (si vous autorisez les téléchargements de fichiers après commande)
  - **Scénario/exemple pour le marchand :** Si les clients peuvent avoir besoin d'ajouter des fichiers après avoir passé une commande, ce bouton doit être visible sur leur page d'historique des commandes.
- **Afficher le bouton de téléchargement de fichier sur la page Mon compte :**

  - **Ce que fait ce paramètre :** Contrôle la visibilité du bouton « Télécharger un fichier » sur la page « Mon compte » du client.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé :* Le bouton sera visible.
    - *Lorsqu'il est désactivé :* Le bouton sera masqué.
  - **Valeur recommandée :** NON (sauf si vous avez activé « Autoriser les clients à télécharger des fichiers vers le compte client » et que vous avez besoin de cette fonctionnalité)
  - **Scénario/exemple pour le marchand :** Si vous souhaitez que les clients téléchargent des fichiers généraux sur leur compte, ce bouton doit être visible.
- **Afficher le bouton de téléchargement de fichier dans le pied de page :**

  - **Ce que fait ce paramètre :** Contrôle la visibilité du bouton « Télécharger un fichier » dans le pied de page.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé :* Le bouton sera visible.
    - *Lorsqu'il est désactivé :* Le bouton sera masqué.
  - **Valeur recommandée :** NON (sauf si vous souhaitez une grande visibilité pour le gestionnaire de fichiers)
  - **Scénario/exemple pour le marchand :** Si les téléchargements de fichiers sont un élément central de votre entreprise, un bouton dans le pied de page peut le rendre facilement accessible depuis n'importe quelle page.
- **Afficher le bouton de téléchargement de fichier dans la colonne de gauche :**

  - **Ce que fait ce paramètre :** Contrôle la visibilité du bouton « Télécharger un fichier » dans la colonne de gauche.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé :* Le bouton sera visible.
    - *Lorsqu'il est désactivé :* Le bouton sera masqué.
  - **Valeur recommandée :** NON (sauf si vous souhaitez une grande visibilité pour le gestionnaire de fichiers)
  - **Scénario/exemple pour le marchand :** Similaire au pied de page, cela offre un autre point d'accès proéminent.
- **Afficher le bouton de téléchargement de fichier dans la colonne de droite :**

  - **Ce que fait ce paramètre :** Contrôle la visibilité du bouton « Télécharger un fichier » dans la colonne de droite.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé :* Le bouton sera visible.
    - *Lorsqu'il est désactivé :* Le bouton sera masqué.
  - **Valeur recommandée :** NON (sauf si vous souhaitez une grande visibilité pour le gestionnaire de fichiers)
  - **Scénario/exemple pour le marchand :** Similaire au pied de page et à la colonne de gauche, cela offre un autre point d'accès proéminent.

#### Paramètres avancés

- **Activer le mode débogage :**

  - **Ce que fait ce paramètre :** Active un mode spécial qui affiche des informations supplémentaires et des messages d'erreur, principalement pour le dépannage.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé :* Des messages d'erreur plus détaillés et des informations de débogage peuvent apparaître à l'écran ou dans les journaux.
    - *Lorsqu'il est désactivé :* Fonctionnement normal, les erreurs sont supprimées ou enregistrées silencieusement.
  - **Valeur recommandée :** NON (n'activez que lors du dépannage avec le support)
  - **Scénario/exemple pour le marchand :** Si vous rencontrez un problème et devez fournir plus d'informations au support MyPresta.eu, ils peuvent vous demander d'activer le mode débogage.
- **Supprimer les fichiers lorsque la commande est supprimée :**

  - **Ce que fait ce paramètre :** Supprime automatiquement tous les fichiers téléchargés associés lorsqu'une commande est supprimée du back office de PrestaShop.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé :* Les fichiers sont définitivement supprimés de votre serveur lorsqu'une commande est supprimée.
    - *Lorsqu'il est désactivé :* Les fichiers restent sur le serveur même si la commande associée est supprimée.
  - **Valeur recommandée :** OUI (pour garder votre serveur propre et éviter les fichiers orphelins)
  - **Scénario/exemple pour le marchand :** Si vous supprimez fréquemment des commandes de test, l'activation de ceci empêche votre serveur d'accumuler des fichiers inutiles.
- **Supprimer les fichiers lorsque le produit est supprimé :**

  - **Ce que fait ce paramètre :** Supprime automatiquement tous les fichiers téléchargés associés lorsqu'un produit est supprimé du back office de PrestaShop.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé :* Les fichiers sont définitivement supprimés de votre serveur lorsqu'un produit est supprimé.
    - *Lorsqu'il est désactivé :* Les fichiers restent sur le serveur même si le produit associé est supprimé.
  - **Valeur recommandée :** OUI (pour garder votre serveur propre et éviter les fichiers orphelins)
  - **Scénario/exemple pour le marchand :** Si vous supprimez des produits anciens ou abandonnés, cela garantit que leurs fichiers associés sont également nettoyés.
- **Supprimer les fichiers lorsque le panier est supprimé :**

  - **Ce que fait ce paramètre :** Supprime automatiquement tous les fichiers téléchargés associés lorsqu'un panier est supprimé du back office de PrestaShop.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé :* Les fichiers sont définitivement supprimés de votre serveur lorsqu'un panier est supprimé.
    - *Lorsqu'il est désactivé :* Les fichiers restent sur le serveur même si le panier associé est supprimé.
  - **Valeur recommandée :** OUI (pour garder votre serveur propre et éviter les fichiers orphelins)
  - **Scénario/exemple pour le marchand :** Les paniers sont souvent temporaires. L'activation de ceci empêche votre serveur d'accumuler des fichiers provenant de paniers abandonnés.
- **Supprimer les fichiers lorsque le client est supprimé :**

  - **Ce que fait ce paramètre :** Supprime automatiquement tous les fichiers téléchargés associés lorsqu'un compte client est supprimé du back office de PrestaShop.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé :* Les fichiers sont définitivement supprimés de votre serveur lorsqu'un client est supprimé.
    - *Lorsqu'il est désactivé :* Les fichiers restent sur le serveur même si le client associé est supprimé.
  - **Valeur recommandée :** OUI (pour la confidentialité des données et l'hygiène du serveur)
  - **Scénario/exemple pour le marchand :** Si un client demande la suppression de ses données (conformité RGPD), cela garantit que ses fichiers téléchargés sont également supprimés.
- **Supprimer les fichiers lorsque le fichier client est supprimé :**

  - **Ce que fait ce paramètre :** Lorsqu'un administrateur ou un client supprime un fichier spécifique, ce paramètre contrôle si le fichier réel est supprimé du serveur.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé :* Le fichier est définitivement supprimé du serveur.
    - *Lorsqu'il est désactivé :* L'enregistrement du fichier est supprimé de la base de données, mais le fichier réel reste sur le serveur (orphelin).
  - **Valeur recommandée :** OUI (toujours, pour éviter les fichiers orphelins et économiser de l'espace disque)
  - **Scénario/exemple pour le marchand :** Lorsqu'un client décide qu'il n'a plus besoin d'un fichier, sa suppression libère également de l'espace serveur.
- **Activer le CSS personnalisé :**

  - **Ce que fait ce paramètre :** Fournit une zone de texte où vous pouvez ajouter vos propres règles CSS pour personnaliser l'apparence des éléments du module.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé et que du CSS est ajouté :* Vos styles personnalisés remplaceront ou compléteront le style par défaut du module.
    - *Lorsqu'il est désactivé ou vide :* Le module utilise son style par défaut.
  - **Valeur recommandée :** NON (sauf si vous avez des besoins de conception spécifiques et des connaissances CSS)
  - **Scénario/exemple pour le marchand :** Vous souhaitez changer la couleur du bouton de téléchargement pour qu'elle corresponde à la couleur principale de votre marque. Vous ajouteriez des règles CSS ici.
- **CSS personnalisé :**

  - **Ce que fait ce paramètre :** C'est la zone de texte où vous tapez ou collez votre code CSS personnalisé.
  - **Effet de la modification de ce paramètre :** L'apparence visuelle des éléments du module changera selon vos règles CSS.
  - **Valeur recommandée :** Laisser vide sauf si vous connaissez le CSS.
  - **Scénario/exemple pour le marchand :** `button.upload-btn { background-color: #ff0000; color: white; }`

### 2.2 Écrans d'administration dédiés et vues de contrôleur

Le module ajoute de nouvelles sections à votre back office PrestaShop pour gérer les fichiers téléchargés.

#### 2.2.1 Gestionnaire de fichiers clients (Back Office > Commandes > Fichiers clients)

Cet écran fournit un endroit centralisé pour visualiser et gérer tous les fichiers téléchargés par vos clients.

- **Nom de l'écran et emplacement du menu :** **Fichiers clients** (situé sous le menu **Commandes** dans PrestaShop 1.7/8/9. Dans les versions antérieures, il peut être directement sous le menu principal Modules ou un onglet personnalisé).
- **Actions et paramètres disponibles :**
  - **Tableau de liste de fichiers :** Vous verrez un tableau listant tous les fichiers téléchargés. Chaque ligne affiche généralement :
    - **Nom du fichier :** Le nom du fichier téléchargé.
    - **Client :** Le nom du client qui a téléchargé le fichier (ou « Invité » si applicable).
    - **ID de commande :** L'ID de la commande à laquelle le fichier est associé.
    - **Produit :** Le nom du produit si le fichier est lié à un produit spécifique.
    - **ID du panier :** L'ID du panier auquel le fichier est associé.
    - **Date de téléchargement :** Quand le fichier a été téléchargé.
    - **Taille :** La taille du fichier.
    - **Actions :** Boutons pour **Télécharger** le fichier, **Afficher les détails** (y compris les commentaires), ou **Supprimer** le fichier.
  - **Filtrage et recherche :** Vous pouvez généralement filtrer la liste par client, ID de commande, ou rechercher par nom de fichier pour trouver rapidement des fichiers spécifiques.
  - **Actions en masse :** Options pour sélectionner plusieurs fichiers et effectuer des actions comme la suppression en masse.
- **Effet des modifications :**
  - **Téléchargement d'un fichier :** Enregistre le fichier sur votre ordinateur pour examen ou traitement.
  - **Suppression d'un fichier :** Supprime le fichier de la liste et, si configuré, de votre serveur.
  - **Affichage des détails :** Ouvre une fenêtre contextuelle ou une nouvelle page avec plus d'informations sur le fichier, y compris les commentaires associés.
- **Flux de travail recommandé pour la gestion quotidienne de la boutique :**
  1. Vérifiez régulièrement cette section, surtout si vous recevez des notifications par e-mail pour les nouveaux téléchargements.
  2. Utilisez les filtres pour trouver rapidement les fichiers des commandes spécifiques que vous traitez.
  3. Téléchargez les fichiers nécessaires pour la production, la conception ou la révision.
  4. Ajoutez des commentaires aux fichiers si vous devez communiquer avec le client ou votre équipe à leur sujet.
  5. Supprimez les fichiers anciens ou inutiles pour garder votre serveur propre.

#### 2.2.2 Intégration de la page de détails de la commande (Back Office > Commandes > Commandes > Afficher la commande)

Le module s'intègre également directement dans la page de détails de commande standard de PrestaShop.

- **Nom de l'écran et emplacement du menu :** Lorsque vous consultez une commande spécifique dans **Back Office > Commandes > Commandes**, vous trouverez une nouvelle section ou un nouvel onglet lié aux « Fichiers clients » ou aux « Fichiers téléchargés ».
- **Actions et paramètres disponibles :**
  - **Fichiers pour cette commande :** Une liste de tous les fichiers spécifiquement téléchargés pour la commande actuelle par le client ou par un administrateur.
  - **Télécharger un nouveau fichier :** Une option pour télécharger un fichier vous-même en tant qu'administrateur, l'associant directement à cette commande. Ceci est utile pour télécharger des épreuves, des conceptions finales ou des documents internes.
  - **Ajouter des commentaires :** Vous pouvez ajouter des commentaires à des fichiers individuels ou un commentaire général pour la commande.
  - **Télécharger/Supprimer :** Options pour télécharger ou supprimer des fichiers individuels associés à cette commande.
- **Effet des modifications :**
  - **Téléchargement d'un fichier en tant qu'administrateur :** Le fichier devient une partie des pièces jointes de la commande, visible par le client dans son historique de commandes (si configuré).
  - **Ajout de commentaires :** Fournit un contexte pour le fichier ou la commande, visible par le client et les autres administrateurs.
- **Flux de travail recommandé pour la gestion quotidienne de la boutique :**
  1. Lors du traitement d'une commande qui nécessite des fichiers clients, accédez à la page de détails de la commande.
  2. Examinez les fichiers téléchargés dans la section dédiée.
  3. Téléchargez les fichiers nécessaires pour la production.
  4. Si vous créez une épreuve ou une conception finale, téléchargez-la ici afin que le client puisse y accéder.
  5. Utilisez les champs de commentaire pour communiquer avec le client ou laisser des notes internes.

### 2.3 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Valeur par défaut / Recommandée | Objectif et impact |
| --- | --- | --- | --- |
| **Configuration du module** | Activer le module | OUI | Interrupteur principal pour la fonctionnalité du module. |
| | Autoriser les clients à télécharger des fichiers | OUI | Permettre aux clients de soumettre des fichiers. |
| | Autoriser les clients invités à télécharger des fichiers | OUI | Permettre aux utilisateurs non connectés de télécharger. |
| | Autoriser les clients à supprimer des fichiers | NON | Empêcher les clients de supprimer des fichiers. |
| | Autoriser les clients à télécharger des fichiers | OUI | Permettre aux clients de récupérer leurs fichiers. |
| | Autoriser les clients à télécharger des fichiers vers les commandes | OUI | Activer les téléchargements après commande via l'historique des commandes. |
| | Autoriser les clients à télécharger des fichiers vers les paniers | OUI | Activer les téléchargements sur la page du panier. |
| | Autoriser les clients à télécharger des fichiers vers les produits | OUI | Activer les téléchargements sur les pages produits individuelles. |
| | Autoriser les clients à télécharger des fichiers vers le compte client | NON | Activer le stockage général de fichiers dans « Mon compte ». |
| | Forcer les clients à télécharger des fichiers vers les commandes | NON | Rendre le téléchargement de fichiers obligatoire pour la finalisation de la commande. |
| | Forcer les clients à télécharger des fichiers vers les produits | NON | Rendre le téléchargement de fichiers obligatoire pour ajouter un produit au panier. |
| | Forcer les clients à télécharger des fichiers vers les paniers | NON | Rendre le téléchargement de fichiers obligatoire pour passer du panier. |
| | Extensions de fichier autorisées | `jpg,jpeg,png,gif,pdf,doc,docx,xls,xlsx,txt` | Restreindre les types de fichiers pour la sécurité et l'utilisabilité. |
| | Taille maximale du fichier (Mo) | `10` | Limiter la taille des fichiers individuels. |
| | Nombre maximal de fichiers par commande | `5` | Limiter les fichiers par commande. |
| | Nombre maximal de fichiers par produit | `1` | Limiter les fichiers par produit. |
| | Nombre maximal de fichiers par panier | `5` | Limiter les fichiers par panier. |
| | Afficher le formulaire de téléchargement sur la page produit | « Dans l'onglet produit » ou « Sous le prix du produit » | Position du formulaire de téléchargement sur la page produit. |
| | Afficher le formulaire de téléchargement sur la page du panier | « Sous le récapitulatif du panier » | Position du formulaire de téléchargement sur la page du panier. |
| | Afficher le formulaire de téléchargement sur la page d'historique des commandes | « Dans le bloc de détails de la commande » | Position du formulaire de téléchargement sur la page d'historique des commandes. |
| | Afficher le formulaire de téléchargement sur la page Mon compte | NON | Afficher/masquer le lien « Mes fichiers » dans le compte client. |
| | Afficher le formulaire de téléchargement dans le pied de page | NON | Afficher/masquer le lien « Mes fichiers » dans le pied de page. |
| | Afficher le formulaire de téléchargement dans la colonne de gauche | NON | Afficher/masquer le lien « Mes fichiers » dans la colonne de gauche. |
| | Afficher le formulaire de téléchargement dans la colonne de droite | NON | Afficher/masquer le lien « Mes fichiers » dans la colonne de droite. |
| | Envoyer un e-mail au client concernant un nouveau fichier | OUI | Notifier le client lorsqu'un administrateur télécharge un fichier. |
| | Envoyer un e-mail au propriétaire de la boutique concernant un nouveau fichier | OUI | Notifier le propriétaire de la boutique lorsqu'un client télécharge un fichier. |
| | Joindre les fichiers à l'e-mail de confirmation de commande | NON | Joindre les fichiers téléchargés à la confirmation de commande. |
| | Joindre les fichiers à l'e-mail du service client | NON | Joindre les fichiers téléchargés à l'e-mail du service client. |
| | Joindre les fichiers à l'e-mail du propriétaire de la boutique | NON | Joindre les fichiers téléchargés à la notification du propriétaire de la boutique. |
| | Activer les commentaires pour les fichiers | OUI | Autoriser les commentaires sur les fichiers individuels. |
| | Activer les commentaires pour les paniers | OUI | Autoriser les commentaires généraux sur les paniers. |
| | Activer les commentaires pour les commandes | OUI | Autoriser les commentaires généraux sur les commandes. |
| | Activer les commentaires pour les produits | OUI | Autoriser les commentaires sur les produits individuels. |
| | Activer l'onglet « Mes fichiers » dans le compte client | OUI | Afficher l'onglet dédié « Mes fichiers » dans le compte client. |
| | Activer l'onglet « Mes fichiers » sur la page d'historique des commandes | OUI | Afficher la section des fichiers sur la page d'historique des commandes. |
| | Activer l'onglet « Mes fichiers » sur la page produit | NON | Afficher la section des fichiers sur la page produit. |
| | Activer l'onglet « Mes fichiers » sur la page du panier | NON | Afficher la section des fichiers sur la page du panier. |
| | Afficher le bouton de téléchargement de fichier sur la page produit | OUI | Contrôler la visibilité du bouton de téléchargement sur la page produit. |
| | Afficher le bouton de téléchargement de fichier sur la page du panier | OUI | Contrôler la visibilité du bouton de téléchargement sur la page du panier. |
| | Afficher le bouton de téléchargement de fichier sur la page d'historique des commandes | OUI | Contrôler la visibilité du bouton de téléchargement sur la page d'historique des commandes. |
| | Afficher le bouton de téléchargement de fichier sur la page Mon compte | NON | Contrôler la visibilité du bouton de téléchargement sur la page Mon compte. |
| | Afficher le bouton de téléchargement de fichier dans le pied de page | NON | Contrôler la visibilité du bouton de téléchargement dans le pied de page. |
| | Afficher le bouton de téléchargement de fichier dans la colonne de gauche | NON | Contrôler la visibilité du bouton de téléchargement dans la colonne de gauche. |
| | Afficher le bouton de téléchargement de fichier dans la colonne de droite | NON | Contrôler la visibilité du bouton de téléchargement dans la colonne de droite. |
| **Paramètres avancés** | Activer le mode débogage | NON | Afficher les messages d'erreur détaillés. |
| | Supprimer les fichiers lorsque la commande est supprimée | OUI | Supprimer les fichiers lorsque la commande associée est supprimée. |
| | Supprimer les fichiers lorsque le produit est supprimé | OUI | Supprimer les fichiers lorsque le produit associé est supprimé. |
| | Supprimer les fichiers lorsque le panier est supprimé | OUI | Supprimer les fichiers lorsque le panier associé est supprimé. |
| | Supprimer les fichiers lorsque le client est supprimé | OUI | Supprimer les fichiers lorsque le client associé est supprimé. |
| | Supprimer les fichiers lorsque le fichier client est supprimé | OUI | Supprimer le fichier réel du serveur lorsqu'il est supprimé. |
| | Activer le CSS personnalisé | NON | Activer la saisie de CSS personnalisé. |
| | CSS personnalisé | Laisser vide | Zone de texte pour les règles CSS personnalisées. |

## 3. Dépannage pour les marchands et questions fréquemment posées (FAQ)

**Q1 : Mes clients ne peuvent pas télécharger de fichiers, ou ils reçoivent un message d'erreur.**
R1 :

- **Vérifier l'état du module :** Assurez-vous que « Activer le module » et « Autoriser les clients à télécharger des fichiers » sont tous deux réglés sur OUI dans la configuration du module.
- **Type et taille du fichier :** Vérifiez que le type de fichier (extension) et la taille respectent les limites de « Extensions de fichier autorisées » et de « Taille maximale du fichier » que vous avez définies.
- **Limites du serveur :** Votre hébergeur peut avoir des limites de téléchargement PHP (`upload_max_filesize`, `post_max_size` dans `php.ini`) inférieures à vos paramètres de module. Contactez votre hébergeur ou votre webmaster pour les augmenter si nécessaire.
- **Permissions :** Assurez-vous que le répertoire de téléchargement du module (généralement `modules/orderfiles/uploads/`) dispose des permissions d'écriture (par exemple, 755 ou 777, bien que 777 ne soit généralement pas recommandé pour la sécurité).
- **Mode débogage :** Activez temporairement le « Mode débogage » dans les paramètres avancés du module et recherchez tout message d'erreur spécifique.

**Q2 : Le formulaire de téléchargement n'apparaît pas sur ma page produit/panier/commande.**
R2 :

- **Configuration du module :** Vérifiez à nouveau les paramètres « Afficher le formulaire de téléchargement sur... » pour la page spécifique (produit, panier, historique des commandes) dans la configuration du module.
- **Conflits de hooks :** Un autre module pourrait interférer avec les hooks d'affichage. Essayez de désactiver temporairement d'autres modules qui modifient les pages produit, panier ou commande pour voir si le formulaire apparaît.
- **Compatibilité du thème :** Les thèmes personnalisés peuvent ne pas rendre correctement les hooks PrestaShop standard. Si vous utilisez un thème personnalisé, vous pourriez avoir besoin d'un webmaster pour intégrer manuellement les hooks du module dans vos fichiers de thème.
- **Cache :** Videz le cache de votre PrestaShop (Paramètres avancés > Performances > Vider le cache) et le cache de votre navigateur.

**Q3 : Je ne reçois pas de notifications par e-mail lorsque les clients téléchargent des fichiers.**
R3 :

- **Configuration du module :** Assurez-vous que « Envoyer un e-mail au propriétaire de la boutique concernant un nouveau fichier » est réglé sur OUI.
- **E-mail de la boutique :** Vérifiez que l'adresse e-mail de votre boutique (PS\_SHOP\_EMAIL dans Paramètres avancés > E-mail) est correctement configurée et fonctionne.
- **Paramètres d'e-mail :** Vérifiez vos paramètres d'e-mail PrestaShop (Paramètres avancés > E-mail) et assurez-vous que les e-mails sont envoyés avec succès (par exemple, essayez d'envoyer un e-mail de test).
- **Dossier de spam :** Vérifiez votre dossier de spam ou de courrier indésirable pour les notifications.
- **Serveur de messagerie :** La fonction de messagerie de votre serveur pourrait être mal configurée. Consultez votre hébergeur.

**Q4 : Comment traduire le texte du module dans d'autres langues ?**
R4 :

- Dans votre back office PrestaShop, naviguez vers **International > Traductions**.
- Sélectionnez « Traductions des modules installés ».
- Choisissez votre thème, la langue que vous souhaitez traduire, puis sélectionnez « Téléchargeur d'images de commande » dans la liste des modules.
- Vous pourrez alors traduire toutes les chaînes de texte visibles du module.

**Q5 : Mes fichiers téléchargés ne sont pas supprimés lorsque je supprime une commande/un produit/un client.**
R5 :

- **Configuration du module :** Assurez-vous que les paramètres correspondants « Supprimer les fichiers lorsque... » (par exemple, « Supprimer les fichiers lorsque la commande est supprimée ») sont réglés sur OUI dans les paramètres avancés du module.
- **Suppression manuelle :** Si ces paramètres étaient désactivés, des fichiers pourraient s'être accumulés. Vous devrez peut-être nettoyer manuellement le répertoire `modules/orderfiles/uploads/` sur votre serveur pour les fichiers anciens et orphelins.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

### 4.1 Vue d'ensemble de l'architecture

Le module « Téléchargeur d'images de commande » suit une architecture de module PrestaShop standard, tirant parti des principes MVC. Il étend la classe `Module` pour sa fonctionnalité principale et utilise `ModuleFrontController` et `AdminController` pour gérer respectivement les requêtes du front-office et du back-office. Les téléchargements de fichiers sont gérés via des contrôleurs dédiés et JavaScript, garantissant une expérience utilisateur fluide. La configuration est stockée dans `ps_configuration`, et les données personnalisées (enregistrements de fichiers) sont gérées via une interaction directe avec la base de données ou potentiellement un `ObjectModel` personnalisé (bien qu'aucun n'ait été explicitement listé dans l'inventaire, le module utilise probablement du SQL direct pour les enregistrements de fichiers).

### 4.2 Contrôleurs (`controllers/`)

#### Contrôleurs Front-Office

Ces contrôleurs gèrent les interactions client et la gestion des fichiers sur la boutique.

- `controllers/front/customerfiles.php`
  - **Nom de la classe et classe parente :** `OrderFilesCustomerfilesModuleFrontController` étendant `ModuleFrontController`
  - **Responsabilité :** Gère la section « Mes fichiers » du client, affichant une liste de ses fichiers téléchargés, lui permettant de les visualiser, de les télécharger et potentiellement de les supprimer. Il gère probablement les requêtes AJAX pour les opérations de fichiers dans ce contexte.
- `controllers/front/download.php`
  - **Nom de la classe et classe parente :** `OrderFilesDownloadModuleFrontController` étendant `ModuleFrontController`
  - **Responsabilité :** Gère les téléchargements de fichiers sécurisés. Il vérifie les permissions de l'utilisateur (par exemple, si le fichier appartient au client connecté ou si l'utilisateur est un administrateur) avant de servir le fichier, empêchant ainsi l'accès non autorisé.
- `controllers/front/filesmanager.php`
  - **Nom de la classe et classe parente :** `OrderFilesFilesmanagerModuleFrontController` étendant `ModuleFrontController`
  - **Responsabilité :** Il s'agit probablement d'un contrôleur central pour l'interface principale de gestion des fichiers, potentiellement utilisé pour les téléchargements de fichiers généraux non liés à une commande/un produit spécifique, ou comme un hub pour tous les fichiers clients.
- `controllers/front/index.php`
  - **Nom de la classe et classe parente :** `OrderFilesIndexModuleFrontController` étendant `ModuleFrontController`
  - **Responsabilité :** Un contrôleur frontal de remplacement ou par défaut. Dans PrestaShop, `index.php` dans un répertoire de contrôleur sert souvent de solution de repli ou de simple redirection.
- `controllers/front/myfiles.php`
  - **Nom de la classe et classe parente :** `OrderFilesMyfilesModuleFrontController` étendant `ModuleFrontController`
  - **Responsabilité :** Similaire à `customerfiles.php`, ce contrôleur gère probablement la section « Mes fichiers » dans le compte client, fournissant l'interface pour visualiser et gérer les fichiers personnels.
- `controllers/front/thumb.php`
  - **Nom de la classe et classe parente :** `OrderFilesThumbModuleFrontController` étendant `ModuleFrontController`
  - **Responsabilité :** Génère et sert des miniatures pour les fichiers image téléchargés, améliorant les performances et l'affichage dans les listes de fichiers.
- `controllers/front/upload.php`
  - **Nom de la classe et classe parente :** `OrderFilesUploadModuleFrontController` étendant `ModuleFrontController`
  - **Responsabilité :** Le contrôleur principal pour gérer toutes les requêtes de téléchargement de fichiers depuis le front office (page produit, page panier, historique des commandes, « Mes fichiers »). Il traite le fichier téléchargé, valide son type et sa taille, le stocke sur le serveur et enregistre ses détails dans la base de données. Il gère probablement les réponses AJAX pour la progression et l'état du téléchargement.

#### Contrôleurs d'administration Back-Office

Ces contrôleurs fournissent l'interface administrative pour la gestion des fichiers téléchargés.

- `controllers/admin/customerFiles.php`
  - **Nom de l'onglet et entité gérée :** « Fichiers clients » (sous le menu Commandes). Gère la liste, la visualisation, le téléchargement et la suppression de tous les fichiers téléchargés par les clients dans l'ensemble de la boutique. Il fournit une vue en grille complète avec des options de filtrage.
- `controllers/admin/index.php`
  - **Nom de l'onglet et entité gérée :** Similaire au `index.php` du front-office, il peut s'agir d'un espace réservé ou d'une simple redirection pour la section d'administration. La gestion principale des fichiers est gérée par `AdminCustomerFilesController`.

### 4.3 Classes et modèles principaux (`classes/`)

L'inventaire fourni n'indique aucune classe personnalisée dans le répertoire `classes/`. Cela suggère que le module pourrait utiliser des requêtes de base de données directes pour la gestion des fichiers ou stocker les informations de fichier directement dans `ps_configuration` ou une table personnalisée sans `ObjectModel` dédié. Compte tenu de la complexité de la gestion des fichiers, il est plus probable que les enregistrements de fichiers soient stockés dans une table de base de données personnalisée et gérés via du SQL direct ou une simple classe d'aide dans le fichier de module principal.

### 4.4 Actifs JavaScript (`views/js/`)

Ces scripts améliorent l'expérience utilisateur pour les téléchargements et la gestion de fichiers.

- `orderfiles/js/jquery.form.js`
  - **Portée :** Front-office et Back-office (partout où les formulaires sont soumis via AJAX).
  - **Description :** Un plugin jQuery pour soumettre facilement des formulaires HTML via AJAX, y compris les téléchargements de fichiers. Il gère le suivi de la progression et simplifie les soumissions de formulaires asynchrones.
- `orderfiles/js/orders.js`
  - **Portée :** Back-office (spécifiquement dans les pages de détails de commande).
  - **Description :** Gère probablement la fonctionnalité AJAX pour télécharger des fichiers directement depuis la page de détails de commande de l'administrateur, afficher les fichiers associés à une commande et gérer les commentaires dans le contexte de la commande.
- `orderfiles/js/script-customers.js`
  - **Portée :** Front-office (pages de compte client, section « Mes fichiers »).
  - **Description :** Gère les éléments interactifs de la section « Mes fichiers » du client, y compris l'affichage des listes de fichiers, la gestion des actions de téléchargement/suppression et potentiellement les mises à jour AJAX pour l'état des fichiers ou les commentaires.
- `orderfiles/js/script.js`
  - **Portée :** Front-office (pages produits, pages panier, formulaires de téléchargement généraux).
  - **Description :** Le JavaScript principal du front-office pour gérer les téléchargements de fichiers. Il initialise probablement les formulaires de téléchargement, gère la fonctionnalité de glisser-déposer, affiche la progression du téléchargement, valide les types/tailles de fichiers côté client et envoie des requêtes AJAX à `upload.php`.

### 4.5 Feuilles de style CSS (`views/css/`)

Ces feuilles de style contrôlent la présentation visuelle des éléments du module.

- `orderfiles/css/ajaxuploader.css`
  - **Portée :** Front-office et Back-office (partout où l'interface de téléchargement AJAX est utilisée).
  - **Description :** Styles pour le widget de téléchargement de fichiers lui-même, y compris les barres de progression, les zones de glisser-déposer et les éléments de prévisualisation de fichiers.
  - **Sélecteurs de classe CSS clés :** `.ajax-uploader-container`, `.upload-drop-zone`, `.file-list`, `.progress-bar`
- `orderfiles/css/backoffice.css`
  - **Portée :** Back-office (contrôleurs d'administration).
  - **Description :** Style spécifique pour les interfaces administratives du module, telles que la liste des « Fichiers clients » et l'intégration dans la page de détails de la commande.
  - **Sélecteurs de classe CSS clés :** `.orderfiles-admin-table`, `.orderfiles-order-details-block`
- `orderfiles/css/orderfiles.css`
  - **Portée :** Front-office (éléments généraux du module).
  - **Description :** Style général pour les composants du front-office du module, y compris les boutons, les listes de fichiers et les sections de commentaires sur les pages produit, panier et historique des commandes.
  - **Sélecteurs de classe CSS clés :** `.orderfiles-upload-form`, `.orderfiles-file-item`, `.orderfiles-comments`
- `orderfiles/css.css`
  - **Portée :** Potentiellement un style global ou de secours.
  - **Description :** Il peut s'agir d'une feuille de style plus ancienne ou générique. Les développeurs doivent vérifier son contenu pour comprendre son impact spécifique, car `orderfiles.css` est plus descriptif.
  - **Sélecteurs de classe CSS clés :** (Nécessite une inspection)

### 4.6 Structure des modèles Smarty (`views/templates/`)

#### Modèles de hook (`views/templates/hook/`)

Ces modèles sont rendus via des hooks PrestaShop pour injecter le contenu du module dans diverses parties de la boutique.

- `displayProductPageUploadFormSmall.tpl` : Rend un formulaire de téléchargement compact sur la page produit.
- `filesmanager-orderhistory.tpl` : Affiche l'interface du gestionnaire de fichiers dans la page d'historique des commandes du client.
- `force-redirect.tpl` : Un modèle utilitaire, éventuellement utilisé pour les redirections après certaines actions ou pour forcer les téléchargements de fichiers.
- `header.tpl` : Injecte les actifs CSS/JS ou tout autre code nécessaire dans la section `<head>` du front office.
- `my-account-17.tpl` : Rend le lien/onglet « Mes fichiers » pour les tableaux de bord des comptes clients de PrestaShop 1.7.x et plus récents.
- `my-account.tpl` : Rend le lien/onglet « Mes fichiers » pour les tableaux de bord des comptes clients des anciennes versions de PrestaShop (par exemple, 1.6.x).
- `orderConfirmation.tpl` : Affiche les options de téléchargement de fichiers ou un résumé sur la page de confirmation de commande.
- `product-files-button.tpl` : Rend le bouton « Télécharger un fichier » sur la page produit.
- `product-files.tpl` : Affiche une liste de fichiers associés à un produit, potentiellement avec des options de téléchargement.
- `shopping-cart-force-files-alert.tpl` : Affiche un message d'alerte si le téléchargement de fichiers est obligatoire sur la page du panier et qu'aucun fichier n'est téléchargé.
- `shopping-cart-qty-infos-alert.tpl` : Affiche probablement une alerte liée aux informations de quantité dans le panier, éventuellement liée aux téléchargements de fichiers.
- `shopping-cart.tpl` : Intègre la fonctionnalité de téléchargement de fichiers ou les listes de fichiers dans la page du panier.
- `tab.tpl` : Un modèle d'onglet générique, éventuellement utilisé pour créer de nouveaux onglets sur les pages produits ou dans le compte client.

#### Modèles d'administration (`views/templates/admin/`)

Ces modèles sont utilisés pour les interfaces back-office du module.

- `admin.tpl` : Le modèle de configuration principal pour la méthode `getContent()` du module, rendant le formulaire de paramètres.
- `adminOrderDetailUpload.tpl` : Intègre l'interface de téléchargement et de gestion de fichiers directement dans la page de détails de commande de PrestaShop dans le back office.
- `boscript.tpl` : Contient du code JavaScript spécifiquement pour le back office, probablement inclus dans les pages d'administration.
- `bulk-delete-files.tpl` : Modèle pour une interface ou une confirmation de suppression de fichiers en masse.
- `comments_cartfiles.tpl` : Rend la section de commentaires pour les fichiers associés à un panier.
- `comments_orderfiles.tpl` : Rend la section de commentaires pour les fichiers associés à une commande.
- `comments_productfiles.tpl` : Rend la section de commentaires pour les fichiers associés à un produit.
- `customerfilesmanager.tpl` : Le modèle principal pour `AdminCustomerFilesController`, affichant la grille de tous les fichiers téléchargés.
- `_configure/helpers/list/list_action_details.tpl` : Un modèle d'aide pour afficher un bouton d'action « détails » dans une liste.
- `_configure/helpers/list/list_content.tpl` : Un modèle d'aide pour rendre les lignes de contenu d'une liste.
- `_configure/prestashopbug/helpers/list/*.tpl` : Ces modèles semblent être des remplacements ou des correctifs spécifiques pour les aides de liste par défaut de PrestaShop, éventuellement pour résoudre des problèmes de compatibilité ou personnaliser l'affichage de la liste pour les grilles d'administration du module. Ils incluent `list.tpl`, `list_action_delete.tpl`, `list_action_details.tpl`, `list_content.tpl`, `list_footer.tpl`, `list_header.tpl`.

#### Modèles Front-office (`views/templates/front/`)

Ce sont des modèles autonomes pour des pages front-office dédiées.

- `access-denied.tpl` : Affiche un message lorsqu'un client tente d'accéder à un fichier ou à une page sans les autorisations appropriées.
- `customerfilesmanager.tpl` : Le modèle principal pour la page « Mes fichiers » du client, affichant ses fichiers téléchargés.
- `filesmanager.tpl` : Un modèle de gestionnaire de fichiers général, potentiellement utilisé pour une page de gestion de fichiers plus large.
- `my-files.tpl` : Un autre modèle pour la section « Mes fichiers », probablement similaire à `customerfilesmanager.tpl` ou une vue spécifique à l'intérieur de celle-ci.

### 4.7 Schéma de la base de données et carte des hooks

#### Tables de base de données

Le module crée probablement au moins une table de base de données personnalisée pour stocker les informations sur les fichiers téléchargés.

- **`ps_orderfiles_files` (ou similaire) :**
  - `id_order_file` (Clé primaire)
  - `id_customer` (Lien vers `ps_customer`)
  - `id_order` (Lien vers `ps_order`)
  - `id_cart` (Lien vers `ps_cart`)
  - `id_product` (Lien vers `ps_product`)
  - `filename` (Nom original du fichier)
  - `filepath` (Chemin d'accès au fichier stocké sur le serveur)
  - `file_extension`
  - `file_size`
  - `comment` (Commentaires utilisateur/administrateur)
  - `date_add`
  - `date_upd`
  - `is_admin_upload` (Booléen, pour distinguer les téléchargements client vs administrateur)
- **`ps_configuration` :** Stocke tous les paramètres du module (par exemple, `OF_ALLOW_CUSTOMER_UPLOAD`, `OF_MAX_FILE_SIZE`, `OF_ALLOWED_EXTENSIONS`, `OF_CEMAIL_CUSTOMER`, `OF_CEMAIL_ATTACH`, etc.). Ces clés sont préfixées par `OF_` (Order Files).

#### Tableau des hooks enregistrés

| Nom du hook | Moment d'exécution | Objectif technique |
| --- | --- | --- |
| `displayHeader` | Dans la section `<head>` de chaque page du front-office. | Injecte les fichiers CSS (`orderfiles.css`, `ajaxuploader.css`) et JavaScript (`jquery.form.js`, `script.js`, `script-customers.js`) du module. |
| `displayProductAdditionalInfo` (ou hook de page produit similaire) | Sur la page produit, généralement sous les détails principaux du produit. | Rend `product-files.tpl` ou `displayProductPageUploadFormSmall.tpl` pour les téléchargements de fichiers spécifiques au produit. |
| `displayShoppingCartFooter` (ou hook de page panier similaire) | En bas du récapitulatif du panier. | Rend `shopping-cart.tpl` pour les téléchargements de fichiers à l'échelle du panier et les alertes. |
| `displayCustomerAccount` | Dans le tableau de bord « Mon compte » du client. | Rend `my-account.tpl` ou `my-account-17.tpl` pour ajouter le lien « Mes fichiers ». |
| `displayMyAccountBlock` | Dans le tableau de bord « Mon compte » du client (alternative pour certains thèmes). | Rend `my-account.tpl` ou `my-account-17.tpl` pour ajouter le lien « Mes fichiers ». |
| `displayOrderConfirmation` | Sur la page de confirmation de commande après un achat réussi. | Rend `orderConfirmation.tpl` pour afficher les options de téléchargement ou les résumés de fichiers. |
| `displayOrderDetail` | Sur la page de détails de commande du client dans « Mon compte ». | Rend `filesmanager-orderhistory.tpl` pour afficher les fichiers liés à la commande spécifique. |
| `displayLeftColumn` | Dans la colonne de gauche du front office. | Rend `tab.tpl` (ou similaire) pour afficher un lien vers le gestionnaire de fichiers. |
| `displayRightColumn` | Dans la colonne de droite du front office. | Rend `tab.tpl` (ou similaire) pour afficher un lien vers le gestionnaire de fichiers. |
| `displayFooter` | Dans le pied de page du front office. | Rend `tab.tpl` (ou similaire) pour afficher un lien vers le gestionnaire de fichiers. |
| `actionObjectOrderAddAfter` | Après qu'une nouvelle commande est ajoutée avec succès à la base de données. | Déclenche des notifications par e-mail au propriétaire de la boutique si un client a téléchargé des fichiers lors du paiement. |
| `actionObjectOrderDeleteAfter` | Après la suppression d'une commande de la base de données. | Déclenche la suppression de fichiers du serveur si « Supprimer les fichiers lorsque la commande est supprimée » est activé. |
| `actionObjectProductDeleteAfter` | Après la suppression d'un produit de la base de données. | Déclenche la suppression de fichiers du serveur si « Supprimer les fichiers lorsque le produit est supprimé » est activé. |
| `actionObjectCartDeleteAfter` | Après la suppression d'un panier de la base de données. | Déclenche la suppression de fichiers du serveur si « Supprimer les fichiers lorsque le panier est supprimé » est activé. |
| `actionObjectCustomerDeleteAfter` | Après la suppression d'un client de la base de données. | Déclenche la suppression de fichiers du serveur si « Supprimer les fichiers lorsque le client est supprimé » est activé. |
| `actionAdminOrdersControllerSaveAfter` | Après l'enregistrement/la mise à jour d'une commande dans le back office. | Gère potentiellement les téléchargements de fichiers d'administration ou les mises à jour de commentaires depuis la page de détails de la commande. |
| `actionAdminControllerSetMedia` | Lorsqu'un contrôleur d'administration est chargé et que ses actifs multimédias sont définis. | Injecte les fichiers CSS (`backoffice.css`) et JavaScript (`orders.js`, `jquery.form.js`, `boscript.tpl`) du module pour la fonctionnalité back-office. |

## 5. Support officiel et mises à jour

Pour les dernières mises à jour du module, les corrections de bugs et le support technique, veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu/my-account/orders/). Notre équipe de support est disponible pour vous aider avec tout problème ou question concernant le module « Téléchargeur d'images de commande ».
