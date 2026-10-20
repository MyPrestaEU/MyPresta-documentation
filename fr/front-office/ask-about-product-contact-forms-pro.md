---
title: "Demander un produit - formulaires de contact pro - Manuel du marchand et guide de configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop 'Demander un produit - formulaires de contact pro' par MyPresta.eu."
sidebar:
  label: "Demander un produit - formulaires de contact pro - Manuel du marchand et guide de configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Ask about product - contact forms pro sur MyPresta.eu](https://mypresta.eu/modules/front-office-features/ask-about-product-contact-forms-pro.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/front-office/ask-about-product-contact-forms-pro/)
>
> ---


# Demander un produit - formulaires de contact pro

## 1. Exigences et compatibilité

- **Versions PrestaShop prises en charge** : PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilité PHP** : PHP 7.1 - 8.5
- **Exigences d'hébergement** : Les extensions PHP standard (cURL, JSON, OpenSSL) sont requises pour que le module fonctionne correctement, en particulier pour des fonctionnalités comme reCAPTCHA et les webhooks. Celles-ci sont généralement disponibles sur la plupart des environnements d'hébergement modernes.

## 2. Guide de configuration complet (Chaque paramètre regroupé par écran)

Ce module offre de nombreuses options de personnalisation pour adapter les formulaires de contact à vos besoins spécifiques. Nous allons passer en revue chaque écran de configuration et chaque paramètre.

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

C'est la zone de configuration principale du module, accessible directement après l'installation ou en naviguant vers **Modules > Gestionnaire de modules** et en cliquant sur « Configurer » à côté de « Demander un produit - formulaires de contact pro ».

#### Paramètres généraux

- **Profil de support de thème**

  - **Ce que fait ce paramètre :** Ce paramètre vous permet de sélectionner un profil de thème prédéfini qui correspond le mieux à votre thème PrestaShop. Différents thèmes peuvent nécessiter des ajustements de style ou structurels différents pour que le formulaire s'affiche correctement.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est défini sur « Classic » (ou similaire) :* Le module utilisera des modèles et un style optimisés pour le thème PrestaShop Classic par défaut ou les thèmes basés sur celui-ci.
    - *Lorsqu'il est défini sur un profil de thème spécifique :* Le module chargera des modèles et des CSS conçus pour s'intégrer en douceur à ce thème particulier, assurant une meilleure cohérence visuelle.
  - **Valeur recommandée :** Choisissez le profil qui correspond à votre thème PrestaShop actif. En cas de doute, commencez par « Classic » et ajustez si des problèmes de style surviennent.
  - **Scénario / exemple pour le marchand :** Si vous utilisez un thème personnalisé, vous devrez peut-être tester différents profils ou utiliser l'option « CSS personnalisé » pour affiner l'apparence.
- **Titre de l'e-mail (pour le propriétaire de la boutique)**

  - **Ce que fait ce paramètre :** C'est l'objet de la notification par e-mail que *vous* (le propriétaire/administrateur de la boutique) recevez lorsqu'un client soumet une question.
  - **Effet de la modification de ce paramètre :** Modifie l'objet des e-mails de notification internes.
  - **Valeur recommandée :** Quelque chose de clair et informatif, comme « Nouvelle question sur un produit de votre boutique - [Nom du produit] ».
  - **Scénario / exemple pour le marchand :** Définir ceci sur « URGENT : Nouvelle demande pour [Nom du produit] » peut aider votre équipe à prioriser.
- **Adresse(s) e-mail du destinataire**

  - **Ce que fait ce paramètre :** Spécifie l'adresse(s) e-mail où les demandes de produits seront envoyées. Vous pouvez saisir plusieurs e-mails séparés par des virgules.
  - **Effet de la modification de ce paramètre :** Détermine qui, dans votre organisation, reçoit les questions des clients.
  - **Valeur recommandée :** L'adresse e-mail de votre équipe de service client ou du service concerné.
  - **Scénario / exemple pour le marchand :** Si vous avez une adresse dédiée « [ventes@votreboutique.com](mailto:ventes@votreboutique.com) » ou « [support@votreboutique.com](mailto:support@votreboutique.com) », saisissez-la ici. Pour les grandes équipes, vous pouvez l'envoyer à une liste de distribution.
- **CCI pour l'e-mail de notification de la boutique**

  - **Ce que fait ce paramètre :** Vous permet d'envoyer une copie carbone invisible (CCI) de l'e-mail de notification de la boutique à des adresses e-mail supplémentaires. Ces destinataires ne seront pas visibles pour le destinataire principal.
  - **Effet de la modification de ce paramètre :** Fournit un moyen discret de notifier d'autres membres de l'équipe ou d'archiver les demandes sans encombrer la boîte de réception du destinataire principal ni révéler les destinataires supplémentaires.
  - **Valeur recommandée :** Laissez vide, sauf si vous avez un besoin spécifique de suivi interne ou de notifications secondaires.
  - **Scénario / exemple pour le marchand :** Vous pouvez mettre en CCI votre responsable marketing pour suivre l'intérêt des clients, ou une adresse e-mail d'archive interne.
- **E-mail de réponse automatique**

  - **Ce que fait ce paramètre :** C'est l'objet de l'e-mail automatique envoyé *au client* après qu'il a soumis une question.
  - **Effet de la modification de ce paramètre :** Modifie l'objet de l'e-mail de confirmation que vos clients reçoivent.
  - **Valeur recommandée :** « Merci pour votre demande - [Nom de votre boutique] ».
  - **Scénario / exemple pour le marchand :** Un objet de réponse automatique clair assure au client que son message a été reçu.
- **Durée du message de succès (ms)**

  - **Ce que fait ce paramètre :** Contrôle la durée pendant laquelle la notification « Votre message a été envoyé avec succès » reste visible à l'écran après qu'un client a soumis un formulaire, mesurée en millisecondes (ms).
  - **Effet de la modification de ce paramètre :**
    - *Valeur plus élevée (par exemple, 5000 ms) :* Le message reste visible plus longtemps, donnant aux clients plus de temps pour le lire.
    - *Valeur plus faible (par exemple, 2000 ms) :* Le message disparaît rapidement.
  - **Valeur recommandée :** 3000-5000 ms (3-5 secondes) est généralement un bon équilibre.
  - **Scénario / exemple pour le marchand :** Si vos clients sont souvent sur des connexions plus lentes ou ont besoin de plus de temps pour traiter l'information, une durée plus longue pourrait être bénéfique.
- **Masquer « Poser une question » pour les produits en rupture de stock (aappro\_HIDE\_OOS)**

  - **Ce que fait ce paramètre :** Si activé, le formulaire ou le bouton « Poser une question » ne sera pas affiché sur les pages produits où le produit est actuellement en rupture de stock.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé :* Empêche les clients de poser des questions sur des produits indisponibles, réduisant potentiellement les demandes non pertinentes pour votre équipe.
    - *Lorsqu'il est désactivé :* Le formulaire reste visible quelle que soit l'état du stock.
  - **Valeur recommandée :** « Oui » pour réduire les demandes concernant les articles indisponibles, sauf si vous souhaitez spécifiquement capter l'intérêt pour les réapprovisionnements.
  - **Scénario / exemple pour le marchand :** Si vous vendez des articles uniques ou en édition limitée qui ne seront pas réapprovisionnés, masquer le formulaire pour les produits en rupture de stock est logique. Si vous souhaitez évaluer l'intérêt pour de futurs réapprovisionnements, laissez-le désactivé.
- **Autoriser uniquement les clients connectés à poser des questions (aappro\_LOGGED\_CUSTOMERS\_ONLY)**

  - **Ce que fait ce paramètre :** Restreint la possibilité de soumettre des questions sur les produits uniquement aux clients qui sont connectés à leur compte de boutique.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé :* Les utilisateurs non enregistrés ou les invités ne verront pas ou ne pourront pas utiliser le formulaire « Poser une question ». Cela peut aider à réduire le spam et à garantir que vous avez les détails du compte client liés aux demandes.
    - *Lorsqu'il est désactivé :* N'importe qui peut soumettre une question, y compris les invités.
  - **Valeur recommandée :** « Non » pour une portée client maximale, « Oui » si vous privilégiez l'engagement des clients enregistrés et souhaitez réduire les demandes anonymes.
  - **Scénario / exemple pour le marchand :** Si vous gérez une boutique B2B où toutes les interactions nécessitent un compte, l'activation de cette option serait appropriée. Pour une boutique de détail générale, la désactiver est généralement préférable pour la conversion.

#### Champs de formulaire et validation

- **Oui / Non (aappro\_FIELD\_PHONE\_REQUIRED, aappro\_FIELD\_PHONE\_VISIBLE, aappro\_FIELD\_TOPIC\_VISIBLE, aappro\_QUOTE\_QUANTITY\_VISIBLE)**

  - **Ce que fait ce paramètre :** Il s'agit d'un groupe de commutateurs « Oui/Non » qui contrôlent la visibilité et l'obligation de champs spécifiques dans vos formulaires de demande de produit :
    - **Numéro de téléphone visible :** Affiche le champ du numéro de téléphone.
    - **Numéro de téléphone requis :** Rend le champ du numéro de téléphone obligatoire s'il est visible.
    - **Sélection de sujet visible :** Affiche une liste déroulante permettant aux clients de sélectionner un sujet pour leur question (par exemple, « Expédition », « Spécifications techniques », « Disponibilité »).
    - **Quantité de devis visible :** Affiche un champ où les clients peuvent demander un devis pour une quantité spécifique du produit.
  - **Effet de la modification de ce paramètre :**
    - *Activé (Visible) :* Le champ apparaît sur le formulaire.
    - *Désactivé (Visible) :* Le champ est masqué.
    - *Activé (Requis) :* Le client *doit* remplir le champ pour soumettre le formulaire.
  - **Valeur recommandée :**
    - **Téléphone :** Visible « Non », Requis « Non » (sauf si le contact téléphonique est essentiel pour votre modèle commercial).
    - **Sujet :** Visible « Oui » (aide à catégoriser les demandes), Requis « Non ».
    - **Quantité de devis :** Visible « Oui » (si vous proposez des remises en gros ou des ventes B2B), Requis « Non ».
  - **Scénario / exemple pour le marchand :** Si vous vendez des produits électroniques complexes, rendre la « Sélection de sujet » visible avec des options comme « Support technique » ou « Compatibilité » serait très utile. Si vous êtes un grossiste, la « Quantité de devis » est essentielle.
- **Longueur minimale de la question (caractères)**

  - **Ce que fait ce paramètre :** Définit le nombre minimum de caractères qu'un client doit taper dans le champ de question avant de pouvoir soumettre le formulaire.
  - **Effet de la modification de ce paramètre :** Empêche les questions très courtes, potentiellement inutiles ou spammantes.
  - **Valeur recommandée :** 10-20 caractères.
  - **Scénario / exemple pour le marchand :** Définir ceci à 15 caractères garantit que les clients fournissent suffisamment de détails au-delà de simplement « Question ».
- **Longueur maximale de la question (caractères)**

  - **Ce que fait ce paramètre :** Définit le nombre maximum de caractères qu'un client peut taper dans le champ de question.
  - **Effet de la modification de ce paramètre :** Empêche les questions excessivement longues qui pourraient être difficiles à lire ou indiquer qu'un client essaie d'utiliser le formulaire comme un chat général.
  - **Valeur recommandée :** 500-1000 caractères.
  - **Scénario / exemple pour le marchand :** Une limite de 750 caractères est généralement suffisante pour la plupart des demandes de produits.
- **Autoriser les pièces jointes d'images**

  - **Ce que fait ce paramètre :** Permet aux clients de télécharger un fichier image (par exemple, une capture d'écran, une photo d'un article endommagé ou un diagramme) avec leur question.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé :* Un champ « Télécharger un fichier » apparaît sur le formulaire.
    - *Lorsqu'il est désactivé :* Aucune option de pièce jointe n'est disponible.
  - **Valeur recommandée :** « Oui » peut être très utile pour les demandes visuelles, mais assurez-vous que votre serveur peut gérer le stockage.
  - **Scénario / exemple pour le marchand :** Un client pourrait vouloir joindre une photo d'une partie spécifique d'un produit sur lequel il a une question, ou une capture d'écran d'une erreur qu'il rencontre.
- **Taille maximale de la pièce jointe (Mo)**

  - **Ce que fait ce paramètre :** Si la pièce jointe d'image est activée, cela définit la taille maximale du fichier (en mégaoctets) autorisée pour chaque pièce jointe.
  - **Effet de la modification de ce paramètre :** Contrôle la charge du serveur et l'utilisation du stockage.
  - **Valeur recommandée :** 2-5 Mo est généralement suffisant pour la plupart des images.
  - **Scénario / exemple pour le marchand :** Le définir à 3 Mo empêche les clients de télécharger des images très grandes et haute résolution qui ne sont pas nécessaires pour une demande.

#### Sécurité et conformité

- **Conforme au RGPD**

  - **Ce que fait ce paramètre :** Active des fonctionnalités pour aider vos formulaires à se conformer aux exigences du RGPD (Règlement Général sur la Protection des Données), généralement en ajoutant une case à cocher pour le consentement au traitement des données.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé :* Une case à cocher apparaîtra sur le formulaire, exigeant que les clients acceptent explicitement votre politique de confidentialité avant de soumettre leur question.
    - *Lorsqu'il est désactivé :* Aucune case à cocher de consentement RGPD n'est affichée.
  - **Valeur recommandée :** « Oui » si votre boutique opère dans ou sert des clients dans des régions soumises au RGPD (par exemple, l'UE).
  - **Scénario / exemple pour le marchand :** Si vous vendez à des clients en Europe, l'activation de cette option est juridiquement importante.
- **Page de politique de confidentialité**

  - **Ce que fait ce paramètre :** Si la conformité au RGPD est activée, ce paramètre vous permet de sélectionner la page CMS qui contient la politique de confidentialité de votre boutique. La case à cocher de consentement RGPD renverra à cette page.
  - **Effet de la modification de ce paramètre :** Fournit aux clients un accès facile à votre politique de confidentialité, remplissant une exigence clé du RGPD.
  - **Valeur recommandée :** Sélectionnez votre page CMS dédiée à la politique de confidentialité.
  - **Scénario / exemple pour le marchand :** Après avoir activé le RGPD, vous devez sélectionner la page CMS correcte afin que les clients puissent consulter vos pratiques de traitement des données.
- **ReCaptcha (v2)**

  - **Ce que fait ce paramètre :** Intègre Google reCAPTCHA v2 (la case à cocher « Je ne suis pas un robot ») dans vos formulaires pour empêcher le spam et les soumissions de bots.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé :* La case à cocher reCAPTCHA apparaît sur le formulaire, nécessitant une interaction de l'utilisateur pour prouver qu'il est humain.
    - *Lorsqu'il est désactivé :* Aucun reCAPTCHA n'est utilisé.
  - **Valeur recommandée :** « Oui » pour réduire considérablement le spam, surtout si vous recevez beaucoup de soumissions de bots.
  - **Scénario / exemple pour le marchand :** Si vous recevez beaucoup de demandes indésirables, l'activation de reCAPTCHA est une défense solide.
- **Clé du site ReCaptcha**

  - **Ce que fait ce paramètre :** C'est la clé publique fournie par Google lorsque vous enregistrez votre site web pour reCAPTCHA. Elle est utilisée pour afficher le widget reCAPTCHA sur votre site.
  - **Effet de la modification de ce paramètre :** Essentiel pour que reCAPTCHA fonctionne. Sans elle, reCAPTCHA n'apparaîtra pas ou ne fonctionnera pas.
  - **Valeur recommandée :** Votre clé de site reCAPTCHA unique de Google.
  - **Scénario / exemple pour le marchand :** Vous devrez vous rendre sur la console d'administration Google reCAPTCHA, enregistrer votre domaine et copier cette clé dans les paramètres du module.
- **Clé secrète ReCaptcha**

  - **Ce que fait ce paramètre :** C'est la clé privée fournie par Google, utilisée pour la vérification côté serveur de la réponse reCAPTCHA.
  - **Effet de la modification de ce paramètre :** Essentiel pour que reCAPTCHA fonctionne en toute sécurité. Le module utilise cette clé pour confirmer que l'utilisateur a réellement réussi le défi reCAPTCHA.
  - **Valeur recommandée :** Votre clé secrète reCAPTCHA unique de Google.
  - **Scénario / exemple pour le marchand :** Cette clé doit rester confidentielle et ne jamais être exposée dans le code côté client.

#### Intégration et personnalisation

- **URL du webhook (Slack/Discord)**

  - **Ce que fait ce paramètre :** Vous permet d'envoyer des notifications de nouvelles demandes de produits à une URL de webhook, généralement utilisée pour des services comme Slack ou Discord.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'une URL est fournie :* Les nouvelles demandes déclencheront une notification vers le canal de discussion spécifié.
    - *Lorsqu'il est vide :* Aucune notification de webhook n'est envoyée.
  - **Valeur recommandée :** Laissez vide, sauf si vous utilisez activement Slack, Discord ou un autre service qui prend en charge les webhooks entrants pour la communication d'équipe.
  - **Scénario / exemple pour le marchand :** Votre équipe de service client utilise Slack. Vous pouvez configurer un webhook entrant dans Slack et coller son URL ici, afin que chaque nouvelle question sur un produit apparaisse immédiatement dans votre canal #support-client.
- **CSS personnalisé (page produit uniquement)**

  - **Ce que fait ce paramètre :** Fournit une zone de texte où vous pouvez ajouter des règles CSS personnalisées pour styliser le formulaire de demande de produit spécifiquement sur les pages produits.
  - **Effet de la modification de ce paramètre :** Vous permet de remplacer les styles de module par défaut ou les styles de votre thème pour correspondre parfaitement à l'esthétique de votre marque sans modifier directement les fichiers du module.
  - **Valeur recommandée :** À utiliser avec parcimonie pour des ajustements mineurs. Pour un style majeur, envisagez les remplacements de thème.
  - **Scénario / exemple pour le marchand :** Vous souhaitez changer la couleur du bouton « Envoyer » pour la couleur principale de votre marque, ou ajuster l'espacement autour des champs du formulaire. Vous pouvez ajouter `.aappro-form-submit-button { background-color: #FF0000; }` ici.
- **Champs personnalisés (aappro\_CUSTOM\_FIELDS\_JSON)**

  - **Ce que fait ce paramètre :** C'est une fonctionnalité puissante qui vous permet de définir des champs supplémentaires et personnalisés pour vos formulaires de contact. Vous pouvez spécifier les types de champs (texte, zone de texte, sélection, case à cocher), les étiquettes et si elles sont obligatoires. Ceci est généralement géré via une interface dédiée, et non un champ JSON brut.
  - **Effet de la modification de ce paramètre :** Ajoute de nouveaux champs de saisie à vos formulaires, vous permettant de recueillir des informations plus spécifiques auprès des clients.
  - **Valeur recommandée :** Ajoutez des champs pertinents pour vos produits ou services (par exemple, « Numéro de commande » pour les clients existants, « Utilisation prévue » pour le B2B).
  - **Scénario / exemple pour le marchand :** Pour une boutique de vêtements, vous pourriez ajouter un champ personnalisé « Taille souhaitée » si les clients posent souvent des questions sur des tailles spécifiques non répertoriées. Pour une boutique de technologie, « Modèle d'appareil actuel » pourrait être utile.
- **Autoriser les commentaires (aappro\_ALLOW\_COMMENTS)**

  - **Ce que fait ce paramètre :** Ce paramètre contrôle probablement si les clients peuvent laisser des commentaires généraux sur la page produit, éventuellement séparément du formulaire spécifique « Poser une question ».
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'il est activé :* Une section de commentaires généraux pourrait apparaître.
    - *Lorsqu'il est désactivé :* Seul le formulaire structuré « Poser une question » est disponible.
  - **Valeur recommandée :** « Non » si vous souhaitez que la communication reste concentrée via le formulaire de question structuré. « Oui » si vous souhaitez encourager une discussion publique plus large.
  - **Scénario / exemple pour le marchand :** Si vous préférez les demandes directes et privées aux commentaires publics, désactivez cette option.
- **PS\_STOCK\_MANAGEMENT**

  - **Ce que fait ce paramètre :** Il s'agit d'un paramètre de base de PrestaShop, non directement contrôlé par le module, mais le module peut lire sa valeur. Il détermine si la gestion des stocks est activée globalement dans votre boutique.
  - **Effet de la modification de ce paramètre :** Si la gestion des stocks est désactivée, le paramètre du module « Masquer pour les produits en rupture de stock » pourrait ne pas fonctionner comme prévu, car les produits n'auront pas un état de stock clair.
  - **Valeur recommandée :** « Oui » pour la plupart des boutiques e-commerce afin de suivre précisément l'inventaire.
  - **Scénario / exemple pour le marchand :** Si vous vendez des produits numériques, vous pouvez désactiver la gestion des stocks. Cependant, pour les biens physiques, c'est crucial.
- **PS\_LANG\_DEFAULT, PS\_BO\_ALLOW\_EMPLOYEE\_FORM\_LANG**

  - **Ce que font ces paramètres :** Ce sont des paramètres de base de PrestaShop liés à la langue. `PS_LANG_DEFAULT` définit la langue par défaut du front-office, et `PS_BO_ALLOW_EMPLOYEE_FORM_LANG` permet aux employés de choisir leur langue du back-office. Le module utilise ces paramètres pour assurer un affichage correct de la langue pour les formulaires et les notifications.
  - **Effet de la modification de ces paramètres :** Affecte la langue des formulaires et des notifications.
  - **Valeur recommandée :** Définissez `PS_LANG_DEFAULT` sur la langue principale de votre boutique. `PS_BO_ALLOW_EMPLOYEE_FORM_LANG` peut être activé si vous avez une équipe multilingue.
  - **Scénario / exemple pour le marchand :** Si la langue principale de votre boutique est le français, assurez-vous que `PS_LANG_DEFAULT` est défini sur le français.

#### Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Valeur par défaut / Recommandée | Objectif et impact |
| --- | --- | --- | --- |
| Configuration principale | Profil de support de thème | Votre thème / Classic | Assure un style et une intégration corrects avec votre thème. |
| Configuration principale | Titre de l'e-mail (pour le propriétaire de la boutique) | « Nouvelle question sur un produit » | Objet des e-mails de notification interne de l'administrateur. |
| Configuration principale | Adresse(s) e-mail du destinataire | Votre e-mail d'administrateur | Où les questions des clients sont envoyées. |
| Configuration principale | CCI pour l'e-mail de notification de la boutique | Vide | Envoyer discrètement des copies des notifications à d'autres. |
| Configuration principale | E-mail de réponse automatique | « Merci pour votre demande » | Objet des e-mails de confirmation client. |
| Configuration principale | Durée du message de succès (ms) | 3000-5000 | Durée pendant laquelle la notification « message envoyé » reste visible. |
| Configuration principale | Masquer pour les produits en rupture de stock | Oui | Empêche les questions sur les produits indisponibles. |
| Configuration principale | Autoriser uniquement les clients connectés | Non | Restreint l'accès au formulaire aux utilisateurs enregistrés. |
| Configuration principale | Numéro de téléphone visible | Non | Affiche/masque le champ du numéro de téléphone. |
| Configuration principale | Numéro de téléphone requis | Non | Rend le numéro de téléphone obligatoire s'il est visible. |
| Configuration principale | Sélection de sujet visible | Oui | Affiche/masque une liste déroulante pour les sujets de question. |
| Configuration principale | Quantité de devis visible | Oui (si B2B) | Affiche/masque un champ pour les demandes de devis de quantité. |
| Configuration principale | Longueur minimale de la question | 15 caractères | Empêche les questions trop courtes. |
| Configuration principale | Longueur maximale de la question | 750 caractères | Empêche les questions trop longues. |
| Configuration principale | Autoriser les pièces jointes d'images | Oui | Permet aux clients de télécharger des fichiers. |
| Configuration principale | Taille maximale de la pièce jointe (Mo) | 3 Mo | Limite la taille des fichiers téléchargés. |
| Configuration principale | Conforme au RGPD | Oui (si applicable) | Ajoute une case à cocher de consentement pour le traitement des données. |
| Configuration principale | Page de politique de confidentialité | Votre CMS de politique de confidentialité | Lie la case à cocher RGPD à votre page de politique. |
| Configuration principale | ReCaptcha (v2) | Oui | Intègre Google reCAPTCHA pour la protection contre le spam. |
| Configuration principale | Clé du site ReCaptcha | Votre clé de site Google | Clé publique pour l'affichage du widget reCAPTCHA. |
| Configuration principale | Clé secrète ReCaptcha | Votre clé secrète Google | Clé privée pour la vérification côté serveur de reCAPTCHA. |
| Configuration principale | URL du webhook (Slack/Discord) | Vide | Envoie des notifications à des services de chat externes. |
| Configuration principale | CSS personnalisé (page produit uniquement) | Vide | Ajoutez du CSS personnalisé pour styliser le formulaire. |
| Configuration principale | Champs personnalisés | Configuré via AdminAapproForm | Définir des champs supplémentaires pour vos formulaires. |
| Configuration principale | Autoriser les commentaires | Non | Contrôle les commentaires généraux sur les produits par rapport aux questions structurées. |

### 2.2 Écrans d'administration dédiés et vues de contrôleur

Au-delà de la configuration principale, ce module fournit des sections dédiées dans votre Back Office PrestaShop pour gérer les formulaires, les questions et les champs personnalisés.

#### 2.2.1 AdminAapproFormController : Gestion des formulaires (Back Office > Modules > Demander un produit > Formulaires)

Cet écran vous permet de créer et de gérer différents formulaires de demande de produit et de spécifier où ils apparaissent dans votre boutique.

- **Nom de l'écran et emplacement du menu :** **Modules > Demander un produit > Formulaires**
- **Actions et paramètres disponibles :**
  - **Tableau de liste :** Affiche tous vos formulaires créés avec leurs noms, leur statut et les produits/catégories/fabricants associés.
  - **Bouton Ajouter un nouveau formulaire :** Cliquez pour créer un nouveau formulaire.
  - **Actions Modifier/Supprimer :** Modifiez ou supprimez les formulaires existants.
  - **Champs du formulaire :** Lors de l'ajout ou de la modification d'un formulaire, vous configurerez :
    - **Nom du formulaire :** Nom interne pour votre référence.
    - **Actif :** Active ou désactive le formulaire.
    - **Afficher sur la page produit :** Choisissez si ce formulaire doit apparaître sur les pages produits.
    - **Afficher sur la page de catégorie :** Choisissez si ce formulaire doit apparaître sur les pages de catégories.
    - **Afficher sur la page du fabricant :** Choisissez si ce formulaire doit apparaître sur les pages de fabricants.
    - **Adresse(s) e-mail du destinataire pour ce formulaire :** Remplace l'adresse e-mail du destinataire global pour ce formulaire spécifique. Ceci est crucial pour acheminer les questions vers des équipes spécifiques.
    - **Produits :** Sélectionnez les produits spécifiques où ce formulaire doit apparaître.
    - **Catégories :** Sélectionnez les catégories spécifiques où ce formulaire doit apparaître.
    - **Fabricants :** Sélectionnez les fabricants spécifiques où ce formulaire doit apparaître.
    - **Champs personnalisés :** C'est ici que vous définissez les champs uniques pour *ce formulaire spécifique*. Vous pouvez ajouter des champs de texte, des zones de texte, des listes déroulantes, des cases à cocher, etc., et les marquer comme obligatoires.
- **Effet des modifications :**
  - La création d'un nouveau formulaire vous permet de définir un ensemble unique de questions et de règles de routage.
  - L'association de formulaires à des produits, catégories ou fabricants spécifiques signifie que seul ce formulaire particulier sera affiché lorsqu'un client consulte un article correspondant à ces critères.
  - Le remplacement des e-mails des destinataires garantit que les questions concernant, par exemple, « l'électronique » vont au service électronique, tandis que les questions sur les « vêtements » vont à l'équipe mode.
  - Les champs personnalisés vous permettent de recueillir des informations très spécifiques pertinentes pour le contexte du formulaire.
- **Flux de travail recommandé pour la gestion quotidienne de la boutique :**
  1. **Identifier les besoins :** Déterminez si vous avez besoin de formulaires différents pour différents types de produits, services ou segments de clientèle.
  2. **Créer des formulaires :** Allez dans **Formulaires** et cliquez sur « Ajouter un nouveau formulaire ».
  3. **Configurer le routage :** Définissez les « Adresse(s) e-mail du destinataire pour ce formulaire » spécifiques pour vous assurer que les questions vont au bon endroit.
  4. **Définir la portée :** Utilisez les sélecteurs « Produits », « Catégories » et « Fabricants » pour contrôler où chaque formulaire apparaît.
  5. **Ajouter des champs personnalisés :** Adaptez les questions posées sur chaque formulaire à l'aide de la section « Champs personnalisés » pour recueillir des informations pertinentes.
  6. **Tester :** Testez toujours vos formulaires sur le front-office pour vous assurer qu'ils apparaissent correctement et envoient des e-mails aux bons destinataires.

#### 2.2.2 AdminAapproQuestionController : Gestion des questions (Back Office > Modules > Demander un produit > Questions)

Cet écran est votre centre de contrôle pour visualiser et gérer toutes les questions clients soumises.

- **Nom de l'écran et emplacement du menu :** **Modules > Demander un produit > Questions**
- **Tableau / Entité gérée :** `aappro_question` (stocke toutes les demandes soumises)
- **Champs de formulaire et colonnes :**
  - **Vue grille / gestion :** Affiche une liste de toutes les questions soumises.
    - **Colonnes :** Inclut généralement : Nom du client, E-mail du client, Nom du produit (le cas échéant), Sujet de la question, Date de soumission, Statut (par exemple, Nouveau, Répondu, Fermé).
    - **Filtrage et tri :** Fonctionnalités de liste PrestaShop standard pour filtrer par date, client, produit ou statut.
  - **Action Afficher/Répondre :** Cliquer sur une question vous permet de visualiser tous ses détails et de répondre au client.
    - **Détails de la question :** Affiche le message complet du client, les informations de contact, les détails du produit et toutes les pièces jointes.
    - **Interface de réponse :** Une zone de texte pour composer votre réponse, qui sera envoyée directement à l'adresse e-mail du client.
    - **Mise à jour du statut :** Option pour modifier le statut de la question (par exemple, de « Nouveau » à « Répondu »).
- **Effet des modifications :**
  - Cet écran fournit une boîte de réception centralisée pour toutes les demandes liées aux produits, ce qui facilite le suivi et la réponse.
  - Répondre directement à partir d'ici garantit que l'historique des conversations est conservé dans PrestaShop et lié au produit spécifique.
  - La mise à jour du statut aide votre équipe à gérer la charge de travail et garantit qu'aucune question n'est manquée.
- **Flux de travail recommandé pour la gestion quotidienne de la boutique :**
  1. **Vérifier régulièrement :** Prenez l'habitude de consulter cette section quotidiennement (ou plusieurs fois par jour, selon le volume).
  2. **Prioriser :** Utilisez les filtres pour identifier les questions urgentes ou sans réponse.
  3. **Afficher et répondre :** Cliquez sur « Afficher » sur une question, lisez les détails et composez une réponse claire et utile.
  4. **Mettre à jour le statut :** Après avoir répondu, modifiez le statut de la question en « Répondu » ou « Fermé » pour garder votre file d'attente organisée.
  5. **Utiliser le contexte du produit :** Le module lie automatiquement la question au produit, vous avez donc tout le contexte nécessaire pour répondre.

#### 2.2.3 index.php (aappro/controllers/admin/index.php)

Ce fichier est une pratique standard de PrestaShop pour empêcher la liste directe des répertoires dans le Back Office. Il contient généralement une simple `header('Location: ../../index.php?controller=AdminHome');` ou une redirection similaire, garantissant que si quelqu'un tente d'accéder directement au répertoire `controllers/admin/`, il est renvoyé au tableau de bord principal de l'administration. Il ne gère aucune entité spécifique et n'a pas de champs configurables.

## 3. Dépannage pour le marchand et questions fréquemment posées (FAQ)

- **Q : Mon formulaire n'apparaît pas sur la page produit.**

  - **R :**
    1. **Vérifier le statut du module :** Assurez-vous que le module est installé et activé dans **Modules > Gestionnaire de modules**.
    2. **Vérifier la configuration du formulaire :** Allez dans **Modules > Demander un produit > Formulaires**. Assurez-vous que le formulaire spécifique que vous vous attendez à voir est « Actif » et correctement associé au produit, à la catégorie ou au fabricant que vous consultez.
    3. **Emplacement du hook :** Vérifiez que le module est accroché à une zone d'affichage que votre thème rend (par exemple, `displayProductExtraContent`, `displayProductAdditionalInfo`). Parfois, les thèmes remplacent les positions de hook par défaut.
    4. **Compatibilité du thème :** Si vous utilisez un thème très personnalisé, essayez de passer temporairement au thème Classic par défaut pour voir si le formulaire apparaît. Si c'est le cas, il pourrait y avoir un conflit avec les fichiers de modèle ou le CSS de votre thème personnalisé.
    5. **Cache :** Videz votre cache PrestaShop (**Paramètres avancés > Performances > Vider le cache**).
- **Q : Je ne reçois pas de notifications par e-mail lorsqu'un client soumet une question.**

  - **R :**
    1. **Vérifier les e-mails des destinataires :** Vérifiez les « Adresse(s) e-mail du destinataire » dans la configuration principale du module et également les « Adresse(s) e-mail du destinataire pour ce formulaire » spécifiques dans les paramètres du formulaire (**Modules > Demander un produit > Formulaires > Modifier le formulaire**). Assurez-vous qu'ils sont corrects et sans fautes de frappe.
    2. **Dossier spam :** Vérifiez le dossier spam ou courrier indésirable de votre e-mail.
    3. **Paramètres de messagerie du serveur :** Assurez-vous que les paramètres de messagerie de votre boutique PrestaShop sont correctement configurés (**Paramètres avancés > E-mail**). Envoyez un e-mail de test depuis PrestaShop pour confirmer que votre serveur peut envoyer des e-mails.
    4. **Fournisseur d'hébergement :** Contactez votre fournisseur d'hébergement pour vérifier les restrictions ou problèmes d'envoi d'e-mails côté serveur.
    5. **Journaux du module :** Vérifiez les journaux d'erreurs de PrestaShop (si disponibles) ou les journaux d'erreurs PHP de votre serveur pour toute erreur liée à la messagerie.
- **Q : Le reCAPTCHA ne fonctionne pas ou n'apparaît pas.**

  - **R :**
    1. **Activer reCAPTCHA :** Assurez-vous que « ReCaptcha (v2) » est défini sur « Oui » dans la configuration principale du module.
    2. **Clés :** Vérifiez à nouveau que votre « Clé du site ReCaptcha » et votre « Clé secrète ReCaptcha » sont correctement saisies et correspondent aux clés de votre compte Google reCAPTCHA pour votre domaine.
    3. **Enregistrement du domaine :** Assurez-vous que votre domaine est correctement enregistré dans votre console d'administration Google reCAPTCHA.
    4. **Problèmes de navigateur :** Testez dans différents navigateurs et videz le cache du navigateur. Parfois, les bloqueurs de publicité peuvent interférer avec reCAPTCHA.
- **Q : Comment traduire les champs de formulaire et les messages dans d'autres langues ?**

  - **R :**
    1. Allez dans **International > Traductions**.
    2. Sélectionnez « Traductions des modules installés ».
    3. Choisissez votre thème, la langue que vous souhaitez traduire, puis sélectionnez « Demander un produit - formulaires de contact pro » dans la liste des modules.
    4. Vous pouvez ensuite traduire toutes les chaînes visibles, les étiquettes de champ et les messages utilisés par le module. N'oubliez pas d'enregistrer vos modifications.
- **Q : Le style du formulaire semble étrange avec mon thème personnalisé.**

  - **R :**
    1. **Profil de support de thème :** Essayez d'ajuster le paramètre « Profil de support de thème » dans la configuration principale du module pour voir si un profil différent fonctionne mieux.
    2. **CSS personnalisé :** Utilisez le champ « CSS personnalisé (page produit uniquement) » dans la configuration du module pour ajouter des règles CSS spécifiques afin de remplacer ou d'ajuster le style. Vous aurez besoin de connaissances CSS de base ou d'un développeur web pour cela.
    3. **Remplacements de thème :** Pour des modifications plus importantes, un développeur pourrait avoir besoin de créer des remplacements de thème pour les fichiers de modèle (`.tpl`) ou les fichiers CSS du module, en les plaçant dans le répertoire `modules/aappro/` de votre thème.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

Cette section fournit un aperçu technique détaillé du module « Demander un produit - formulaires de contact pro », destiné aux développeurs, webmasters et agences techniques.

### 4.1 Aperçu de l'architecture

Le module suit un modèle MVC (Modèle-Vue-Contrôleur) PrestaShop standard, étendant les classes PrestaShop de base pour sa fonctionnalité. Il utilise `ModuleFrontController` pour les interactions front-office (soumission de formulaire, réponses) et `AdminController` pour la gestion back-office des formulaires et des questions. Des classes `ObjectModel` personnalisées (`AapproCustomFields`, `AapproFormMatcher`) sont utilisées pour persister les données spécifiques au module. Les hooks sont largement utilisés pour intégrer le formulaire dans diverses parties du front-office.

### 4.2 Contrôleurs (`controllers/`)

#### Contrôleurs Front-Office

- `controllers/front/index.php`
  - **Nom de la classe et classe parente :** `AapproIndexModuleFrontController` étend `ModuleFrontController`.
  - **Responsabilité :** Gère probablement le rendu initial du formulaire ou un déclencheur pour le formulaire, potentiellement via AJAX. Il pourrait préparer les données pour le modèle de formulaire.
- `controllers/front/question.php`
  - **Nom de la classe et classe parente :** `AapproQuestionModuleFrontController` étend `ModuleFrontController`.
  - **Responsabilité :** Ce contrôleur est responsable du traitement de la soumission du formulaire de demande de produit. Il valide les entrées, gère la vérification reCAPTCHA, traite les téléchargements de fichiers (si activé), enregistre la question dans la base de données, envoie des notifications par e-mail au propriétaire de la boutique et potentiellement une réponse automatique au client. Il renvoie des réponses JSON pour les soumissions AJAX.
- `controllers/front/reply.php`
  - **Nom de la classe et classe parente :** `AapproReplyModuleFrontController` étend `ModuleFrontController`.
  - **Responsabilité :** Ce contrôleur gère probablement le mécanisme de réponse côté client, si le module permet aux clients de visualiser les réponses sur le front-office ou fournit un lien spécifique pour la visualisation des réponses. Il récupérerait la question et les réponses associées.

#### Contrôleurs d'administration Back-Office

- `controllers/admin/AdminAapproForm.php`
  - **Nom de la classe et classe parente :** `AdminAapproFormController` étend `ModuleAdminController`.
  - **Nom de l'onglet et entité gérée :** Gère les formulaires de demande personnalisés. Accessible via **Modules > Demander un produit > Formulaires**. Il gère les opérations CRUD pour les objets `AapproFormMatcher`, y compris la définition des noms de formulaire, du statut d'activation, des produits/catégories/fabricants associés et des champs personnalisés.
- `controllers/admin/AdminAapproQuestion.php`
  - **Nom de la classe et classe parente :** `AdminAapproQuestionController` étend `ModuleAdminController`.
  - **Nom de l'onglet et entité gérée :** Gère les questions clients soumises. Accessible via **Modules > Demander un produit > Questions**. Il fournit une vue liste des questions, permet de visualiser tous les détails des questions et offre une interface pour répondre aux clients et mettre à jour le statut des questions.
- `controllers/admin/index.php`
  - **Nom de la classe et classe parente :** Pas un contrôleur fonctionnel.
  - **Responsabilité :** Fichier de sécurité PrestaShop standard pour empêcher la liste des répertoires. Il redirige généralement vers le tableau de bord de l'administration.

### 4.3 Classes et modèles de base (`classes/`)

- `classes/AapproCustomFields.php`
  - **Table de base de données avec laquelle il interagit :** Probablement `ps_aappro_custom_field` (ou similaire).
  - **Étend ObjectModel :** Oui, il étend `ObjectModel`.
  - **Champs `$definition` :** Définirait des champs tels que `id_aappro_custom_field`, `id_aappro_form`, `name`, `type`, `label`, `required`, `options` (pour les champs de sélection, souvent encodés en JSON), `position`, `active`.
  - **Méthodes publiques clés et logique métier :** Méthodes pour enregistrer, récupérer et supprimer les définitions de champs personnalisés associées à des formulaires spécifiques. Logique pour l'analyse et le rendu des données de champs personnalisés.
- `classes/AapproFormMatcher.php`
  - **Table de base de données avec laquelle il interagit :** Probablement `ps_aappro_form` (ou similaire).
  - **Étend ObjectModel :** Oui, il étend `ObjectModel`.
  - **Champs `$definition` :** Définirait des champs tels que `id_aappro_form`, `name`, `active`, `recipient_emails`, `products` (tableau d'ID de produits encodé en JSON), `categories` (tableau d'ID de catégories encodé en JSON), `manufacturers` (tableau d'ID de fabricants encodé en JSON), `display_product`, `display_category`, `display_manufacturer`.
  - **Méthodes publiques clés et logique métier :** Méthodes pour gérer les configurations de formulaire, y compris l'enregistrement des associations avec les produits/catégories/fabricants, et la récupération du formulaire correct en fonction du contexte actuel (ID de produit, ID de catégorie).

### 4.4 Actifs JavaScript (`views/js/`)

- `aappro/lib/searchTool/views/js/autocomplete.js`
  - **Portée :** Back-office.
  - **Description :** Fournit une fonctionnalité d'autocomplétion pour la sélection de produits, catégories ou fabricants lors de la configuration des formulaires dans `AdminAapproFormController`. Se lie aux champs de saisie pour suggérer des entités au fur et à mesure que l'utilisateur tape, améliorant l'expérience utilisateur pour l'association de formulaires.
- `aappro/views/aappro.js`
  - **Portée :** Front-office.
  - **Description :** Script principal du front-office pour le module.
    - **Écouteurs d'événements :** Lie les événements de clic aux boutons/liens « Poser une question », les événements de soumission aux formulaires de demande.
    - **Manipulation du DOM :** Gère l'affichage/masquage du formulaire (par exemple, dans une modale ou une section extensible), l'affichage des messages de succès/erreur (notifications toast).
    - **Appels AJAX :** Soumet les données du formulaire de manière asynchrone à `AapproQuestionModuleFrontController`, gère la réponse reCAPTCHA et met à jour l'interface utilisateur en fonction de la réponse JSON du serveur.
    - **Validation :** Peut inclure une validation côté client pour les champs de formulaire (par exemple, longueur min/max).
- `aappro/views/js/admin-button-style.js`
  - **Portée :** Back-office.
  - **Description :** Fournit probablement des éléments interactifs ou des aperçus pour la configuration des styles de boutons (par exemple, sélecteurs de couleurs, curseurs de taille) dans les écrans de configuration du module ou de gestion des formulaires.
- `aappro/views/js/admin-form-layout.js`
  - **Portée :** Back-office.
  - **Description :** Gère la mise en page dynamique et l'interaction pour la création/modification de formulaires dans `AdminAapproFormController`, en particulier pour la gestion des champs personnalisés. Cela peut inclure l'ajout/suppression de lignes de champs personnalisés, le réordonnancement des champs et la gestion des options spécifiques au type de champ.
- `aappro/views/js/admin-icon-picker-data.js`
  - **Portée :** Back-office.
  - **Description :** Contient des données (par exemple, un tableau de classes d'icônes ou de chemins SVG) pour une interface de sélection d'icônes utilisée dans le back-office, éventuellement pour les icônes de champs personnalisés ou les options d'affichage de formulaire.
- `aappro/views/js/admin-icon-picker.js`
  - **Portée :** Back-office.
  - **Description :** Implémente la logique de l'interface utilisateur du sélecteur d'icônes, permettant aux administrateurs de sélectionner des icônes à partir d'un ensemble prédéfini, probablement utilisé en conjonction avec `admin-icon-picker-data.js`.

### 4.5 Feuilles de style CSS (`views/css/`)

- `aappro/lib/searchTool/views/css/autocomplete.css`
  - **Portée :** Back-office.
  - **Description :** Styles pour les listes déroulantes d'autocomplétion et les champs de saisie utilisés dans la configuration des formulaires d'administration (par exemple, pour la sélection de produits/catégories).
- `aappro/views/aappro.css`
  - **Portée :** Style client du Front-office.
  - **Description :** Style de base pour les formulaires de demande de produit, les boutons, les modales, les messages de succès/erreur (notifications toast) et tout autre élément du front-office rendu par le module.
  - **Sélecteurs de classe CSS clés :** `.aappro-form-container`, `.aappro-form-trigger`, `.aappro-modal`, `.aappro-field-group`, `.aappro-submit-button`, `.aappro-success-toast`, `.aappro-error-toast`.
- `aappro/views/css/admin-button-style.css`
  - **Portée :** Style des formulaires d'administration Back-office.
  - **Description :** Styles pour les éléments de configuration des boutons dans l'interface d'administration du module.
- `aappro/views/css/admin-custom-fields.css`
  - **Portée :** Style des formulaires d'administration Back-office.
  - **Description :** Styles pour l'interface de gestion dynamique des champs personnalisés dans `AdminAapproFormController`, assurant une mise en page claire et utilisable pour l'ajout/modification de champs personnalisés.
- `aappro/views/css/admin-form-layout.css`
  - **Portée :** Style des formulaires d'administration Back-office.
  - **Description :** Mise en page générale et style pour les écrans de création/modification de formulaires dans le panneau d'administration, offrant une apparence cohérente.
- `aappro/views/css/admin-icon-picker.css`
  - **Portée :** Style des formulaires d'administration Back-office.
  - **Description :** Styles pour l'interface de sélection d'icônes utilisée dans le panneau d'administration.

### 4.6 Structure des modèles Smarty (`views/templates/`)

#### Modèles de hook (`views/templates/hook/`)

- `aappro/views/aappro-extra-forms.tpl`
  - **Hook :** `displayProductExtraContent` ou similaire.
  - **Sortie :** Rend des formulaires supplémentaires ou des blocs de contenu liés au produit, potentiellement le formulaire de demande lui-même ou un déclencheur pour celui-ci.
- `aappro/views/aappro-extra-trigger.tpl`
  - **Hook :** `displayProductButtons`, `displayProductAdditionalInfo`.
  - **Sortie :** Rend un bouton ou un lien (par exemple, « Poser une question ») qui déclenche l'affichage du formulaire de demande, souvent dans une modale ou une section cachée.
- `aappro/views/aappro-extra.tpl`
  - **Hook :** `displayProductExtraContent`, `displayProductAdditionalInfo`.
  - **Sortie :** Un modèle général pour le contenu supplémentaire sur la page produit, enveloppant potentiellement le formulaire ou son déclencheur.
- `aappro/views/aappro-faq-tab-title.tpl`
  - **Hook :** `displayProductTab`.
  - **Sortie :** Rend le titre d'un onglet produit (par exemple, « Poser une question » ou « FAQ ») qui, lorsqu'il est cliqué, révèle le contenu du formulaire.
- `aappro/views/aappro-faq-tab.tpl`
  - **Hook :** `displayProductTabContent`.
  - **Sortie :** Rend le contenu réel de l'onglet produit, qui serait le formulaire de demande lui-même.
- `aappro/views/aappro-form-body.tpl`
  - **Hook :** Inclusion interne.
  - **Sortie :** La structure HTML principale pour les champs du formulaire de demande (nom, e-mail, question, champs personnalisés, reCAPTCHA, case à cocher RGPD). Ceci est probablement inclus par d'autres modèles.
- `aappro/views/aappro-form-tab.tpl`
  - **Hook :** `displayProductTabContent`.
  - **Sortie :** Similaire à `aappro-faq-tab.tpl`, spécifiquement pour le rendu du formulaire dans un onglet produit.
- `aappro/views/aappro-product-embed.tpl`
  - **Hook :** `displayProductAdditionalInfo`, `displayReassurance`.
  - **Sortie :** Intègre le formulaire de demande directement dans le contenu de la page produit, plutôt que dans un onglet ou une modale.
- `aappro/views/classic/` (et `views/partials/`)
  - Ces répertoires contiennent des modèles spécifiques au thème (pour le thème Classic) et des éléments partiels réutilisables. Ils reflètent la structure du répertoire `views/` principal mais sont optimisés ou spécifiquement stylisés pour le thème Classic.
  - `aappro-custom-field-single.tpl` : Rend un seul champ personnalisé en fonction de son type.
  - `aappro-custom-fields.tpl` : Itère et rend tous les champs personnalisés pour un formulaire.
  - `aappro-field-fragment.tpl` : Un fragment réutilisable pour le rendu des éléments de champ de formulaire courants.

#### Modèles d'administration (`views/templates/admin/`)

- `aappro/views/templates/admin/button_style_block.tpl`
  - **Objectif :** Rend l'interface de configuration des styles de boutons dans le panneau d'administration.
- `aappro/views/templates/admin/conversation_reply.tpl`
  - **Objectif :** Rend l'interface de réponse lors de la visualisation d'une question client dans `AdminAapproQuestionController`.
- `aappro/views/templates/admin/custom_fields_block.tpl`
  - **Objectif :** Rend l'interface dynamique pour l'ajout, la modification et la gestion des champs personnalisés dans `AdminAapproFormController`.
- `aappro/views/templates/admin/form_layout_block.tpl`
  - **Objectif :** Rend les options de mise en page générale pour les formulaires dans le panneau d'administration.
- `aappro/views/templates/admin/question_extras.tpl`
  - **Objectif :** Affiche des détails ou des actions supplémentaires liés à une question spécifique dans `AdminAapproQuestionController`.
- `aappro/views/templates/admin/question_product_preview.tpl`
  - **Objectif :** Rend un petit aperçu du produit associé à une question dans `AdminAapproQuestionController`.
- `aappro/views/templates/admin/topic_options_block.tpl`
  - **Objectif :** Rend l'interface de configuration pour la définition des sujets disponibles pour la liste déroulante « Sélection de sujet ».
- `aappro/views/templates/admin/view_question.tpl`
  - **Objectif :** Le modèle principal pour l'affichage d'une seule question client et de ses détails dans `AdminAapproQuestionController`.

### 4.7 Schéma de base de données et carte des hooks

#### Tables de base de données

- `ps_aappro_form` : Stocke les définitions de chaque formulaire de demande personnalisé créé par le marchand.

  - `id_aappro_form` (PK)
  - `name` (VARCHAR)
  - `active` (TINYINT)
  - `recipient_emails` (TEXT)
  - `products` (TEXT, tableau d'ID de produits encodé en JSON)
  - `categories` (TEXT, tableau d'ID de catégories encodé en JSON)
  - `manufacturers` (TEXT, tableau d'ID de fabricants encodé en JSON)
  - `display_product` (TINYINT)
  - `display_category` (TINYINT)
  - `display_manufacturer` (TINYINT)
- `ps_aappro_custom_field` : Stocke les définitions des champs personnalisés associés à chaque formulaire.

  - `id_aappro_custom_field` (PK)
  - `id_aappro_form` (FK vers `ps_aappro_form`)
  - `name` (VARCHAR)
  - `type` (VARCHAR, par exemple, 'text', 'textarea', 'select', 'checkbox')
  - `label` (TEXT, multilingue)
  - `required` (TINYINT)
  - `options` (TEXT, encodé en JSON pour les options de sélection/radio)
  - `position` (INT)
  - `active` (TINYINT)
- `ps_aappro_question` : Stocke chaque question client soumise.

  - `id_aappro_question` (PK)
  - `id_product` (FK vers `ps_product`)
  - `id_customer` (FK vers `ps_customer`, si connecté)
  - `id_aappro_form` (FK vers `ps_aappro_form`)
  - `customer_name` (VARCHAR)
  - `customer_email` (VARCHAR)
  - `customer_phone` (VARCHAR, si activé)
  - `topic` (VARCHAR, si activé)
  - `quantity_request` (INT, si activé)
  - `question_text` (TEXT)
  - `attachment_path` (VARCHAR, si activé)
  - `custom_fields_data` (TEXT, tableau de valeurs de champs personnalisés encodé en JSON)
  - `ip_address` (VARCHAR)
  - `date_add` (DATETIME)
  - `status` (VARCHAR, par exemple, 'new', 'replied', 'closed')
- `ps_aappro_question_reply` : Stocke les réponses de l'administrateur aux questions des clients.

  - `id_aappro_question_reply` (PK)
  - `id_aappro_question` (FK vers `ps_aappro_question`)
  - `id_employee` (FK vers `ps_employee`)
  - `reply_text` (TEXT)
  - `date_add` (DATETIME)
- **Enregistrements de configuration (dans la table `ps_configuration`) :**

  - `aappro_TITLE`
  - `aappro_AUTORESPONDER`
  - `aappro_FIELD_PHONE_REQUIRED`
  - `aappro_FIELD_PHONE_VISIBLE`
  - `aappro_FIELD_TOPIC_VISIBLE`
  - `aappro_QUOTE_QUANTITY_VISIBLE`
  - `aappro_WEBHOOK_URL`
  - `aappro_Q_LEN_MIN`
  - `aappro_Q_LEN_MAX`
  - `aappro_ATTACHMENT_ENABLE`
  - `aappro_ATTACHMENT_MAX_MB`
  - `aappro_SHOP_MAIL_BCC`
  - `aappro_TOAST_MS`
  - `aappro_FLOAT_DELAY_MS`
  - `aappro_THEME_SUPPORT`
  - `aappro_CUSTOM_CSS`
  - `aappro_CUSTOM_FIELDS_JSON` (probablement obsolète au profit de la table `ps_aappro_custom_field`)
  - `aappro_recaptcha`
  - `aappro_GDPR`
  - `aappro_GDPRCMS`
  - `aappro_recaptcha_sitekey`
  - `aappro_ALLOW_COMMENTS`
  - `aappro_recaptcha_secretkey`
  - `aappro_emailslist`
  - `aappro_HIDE_OOS`
  - `aappro_LOGGED_CUSTOMERS_ONLY`

#### Tableau des hooks enregistrés

| Nom du hook | Moment d'exécution | Objectif technique |
| --- | --- | --- |
| `displayHeader` | Dans la section `<head>` de chaque page. | Enregistre les actifs CSS/JS, initialise les variables JS globales ou rend les éléments cachés pour la fonctionnalité du module. |
| `displayFooter` | En bas de chaque page, avant `</body>`. | Peut être utilisé pour injecter du HTML modal, des boutons flottants ou des scripts qui doivent s'exécuter après le chargement de la page. |
| `displayProductExtraContent` | Dans le bloc « contenu supplémentaire » sur les pages produits (souvent sous la description). | Rend le formulaire de demande ou un déclencheur pour celui-ci, souvent sous forme de bloc complet. |
| `displayProductAdditionalInfo` | Dans le bloc d'informations produit, généralement près du prix/bouton d'ajout au panier. | Rend un déclencheur plus petit ou un formulaire compact directement dans les informations principales du produit. |
| `displayProductButtons` | Près du bouton « Ajouter au panier ». | Rend un bouton ou un lien pour ouvrir le formulaire de demande. |
| `displayProductTab` | Pour ajouter un nouveau titre d'onglet sur la page produit. | Rend le titre de l'onglet « Poser une question » ou « FAQ ». |
| `displayProductTabContent` | Pour ajouter du contenu à un nouvel onglet sur la page produit. | Rend le formulaire de demande réel dans son onglet produit dédié. |
| `displayReassurance` | Dans le bloc de réassurance (par exemple, « paiement sécurisé », « livraison gratuite »). | Peut être utilisé pour injecter un petit lien ou une icône « Poser une question » dans le bloc de réassurance. |
| `actionAdminControllerSetMedia` | Lorsqu'un contrôleur d'administration est chargé et que ses actifs multimédias sont définis. | Enregistre les CSS et JS spécifiques au module pour les contrôleurs du back-office (`AdminAapproForm`, `AdminAapproQuestion`). |
| `actionValidateOrder` | Après qu'une commande a été validée avec succès. | (Non directement utilisé par la fonction principale de ce module, mais pourrait être utilisé pour des questions de suivi après l'achat si étendu). |

## 5. Support officiel et mises à jour

Pour les dernières mises à jour, corrections de bugs et support officiel du module « Demander un produit - formulaires de contact pro », veuillez vous référer à votre compte client sur MyPresta.eu. Notre équipe de support est disponible pour vous aider avec tout problème technique ou question concernant la fonctionnalité du module. Assurez-vous toujours d'utiliser la dernière version compatible du module pour des performances et une sécurité optimales.
