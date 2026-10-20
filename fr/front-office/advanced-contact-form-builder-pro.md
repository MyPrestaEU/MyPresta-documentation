---
title: "Advanced Contact Form Builder Pro - Manuel du Marchand et Guide de Configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop Advanced Contact Form Builder Pro par MyPresta.eu."
sidebar:
  label: "Advanced Contact Form Builder Pro - Manuel du Marchand et Guide de Configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Advanced Contact Form Builder Pro sur MyPresta.eu](https://mypresta.eu/modules/front-office-features/advanced-contact-form-builder-pro.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/front-office/advanced-contact-form-builder-pro/)
>
> ---


# Advanced Contact Form Builder Pro

## 1. Exigences et compatibilité

- **Versions de PrestaShop prises en charge** : PrestaShop 1.7.x, 8.x, 9.x (jusqu'à 12.x selon la définition du module)
- **Compatibilité PHP** : PHP 7.1 - 8.5
- **Exigences d'hébergement** : Les extensions PHP standard (cURL, JSON, OpenSSL) sont généralement requises pour PrestaShop lui-même et pour des fonctionnalités telles que les webhooks ou reCAPTCHA.

## 2. Guide de configuration complet (Chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

C'est l'écran principal où vous configurez le comportement général et les options par défaut de vos formulaires de contact.

-   **Profil de support de template**

    *   **Ce que fait ce paramètre :** Ce paramètre aide le module à adapter sa sortie visuelle pour mieux correspondre au thème de votre boutique. Différents thèmes PrestaShop peuvent avoir des structures HTML légèrement différentes.
    *   **Effet de la modification de ce paramètre :**
        *   *Lorsqu'il est défini sur 'Classic' (ou similaire) :* Le module utilisera des templates optimisés pour le thème PrestaShop Classic par défaut ou les thèmes basés sur celui-ci. Cela garantit que les formulaires ont une belle apparence sans effort de style supplémentaire.
        *   *Lorsqu'il est défini sur 'Custom' ou un autre nom de thème :* Le module peut utiliser des templates ou des règles de style spécifiques adaptés à ce thème particulier, si disponibles.
    *   **Valeur recommandée :** Choisissez l'option qui correspond le mieux à votre thème PrestaShop actif. Si vous utilisez le thème Classic par défaut ou un thème qui en dérive, 'Classic' est généralement le meilleur choix. Si vos formulaires ne s'affichent pas correctement, essayez d'expérimenter avec ce paramètre.
    *   **Scénario / exemple pour le marchand :** Si vos formulaires apparaissent sans style ou mal alignés après l'installation, le fait de passer de 'Classic' à un autre profil disponible (le cas échéant) pourrait résoudre le problème.
-   **Email de réponse automatique**

    *   **Ce que fait ce paramètre :** C'est l'adresse email à partir de laquelle les emails de confirmation automatiques seront envoyés à vos clients après qu'ils aient soumis un formulaire.
    *   **Effet de la modification de ce paramètre :**
        *   *Lorsqu'il est défini sur une adresse email valide :* Les clients recevront un email immédiat "Merci pour votre demande" de cette adresse.
        *   *Lorsqu'il est laissé vide :* Aucun email de confirmation automatique ne sera envoyé au client.
    *   **Valeur recommandée :** Utilisez une adresse email professionnelle associée à votre boutique, par exemple, `info@votreboutique.com` ou `noreply@votreboutique.com`.
    *   **Scénario / exemple pour le marchand :** Définir ceci sur `support@maboutique.com` garantit que les clients savent que leur message a été reçu et leur fournit un point de contact pour le suivi.
-   **Titre de l'email (pour le propriétaire de la boutique)**

    *   **Ce que fait ce paramètre :** Ceci définit la ligne d'objet pour les notifications par email que vous (le propriétaire de la boutique) recevez lorsqu'un client soumet un formulaire.
    *   **Effet de la modification de ce paramètre :**
        *   *Lorsqu'il est défini sur "Nouvelle demande de ma boutique" :* Vos emails de notification auront cet objet, ce qui les rendra faciles à identifier.
    *   **Valeur recommandée :** Quelque chose de clair et descriptif, comme "Nouvelle soumission de formulaire de contact - [Nom de votre boutique]".
    *   **Scénario / exemple pour le marchand :** L'utilisation de "Nouvelle demande client - MyPresta.eu" vous aide à repérer rapidement les messages importants dans votre boîte de réception.
-   **Email(s) du destinataire**

    *   **Ce que fait ce paramètre :** C'est ici que vous spécifiez une ou plusieurs adresses email qui recevront des notifications lorsqu'un client soumet *n'importe quel* formulaire créé par ce module. Vous pouvez séparer plusieurs emails par une virgule.
    *   **Effet de la modification de ce paramètre :**
        *   *Lorsqu'il est défini sur `ventes@votreboutique.com` :* Toutes les soumissions de formulaire seront envoyées au service des ventes.
        *   *Lorsqu'il est défini sur `ventes@votreboutique.com, support@votreboutique.com` :* Les deux services recevront des copies de toutes les soumissions.
    *   **Valeur recommandée :** L'adresse(s) email principale(s) de votre service client ou de votre équipe de vente.
    *   **Scénario / exemple pour le marchand :** Si vous avez une équipe de service client dédiée, vous entreriez `serviceclient@votreboutique.com` ici.
-   **BCC pour l'email de notification de la boutique**

    *   **Ce que fait ce paramètre :** Vous permet d'envoyer une "copie carbone invisible" (BCC) de l'email de notification du propriétaire de la boutique à des adresses email supplémentaires. Ces destinataires ne seront pas visibles pour le destinataire principal.
    *   **Effet de la modification de ce paramètre :**
        *   *Lorsqu'il est défini sur `manager@votreboutique.com` :* Le manager recevra une copie cachée de toutes les notifications de soumission de formulaire.
    *   **Valeur recommandée :** Utilisez ceci pour le suivi interne, la sauvegarde, ou pour les managers qui ont besoin de surveiller les demandes sans être le contact principal. Laissez vide si non nécessaire.
    *   **Scénario / exemple pour le marchand :** Votre équipe marketing pourrait vouloir se mettre en BCC pour suivre la génération de leads à partir des formulaires sans être directement impliquée dans les réponses aux clients.
-   **Oui / Non (pour divers paramètres de visibilité/exigence de champ)**

    *   **Ce que fait ce paramètre :** Ce sont des interrupteurs généraux pour activer ou désactiver des fonctionnalités spécifiques ou rendre certains champs obligatoires/facultatifs sur vos formulaires.
    *   **Effet de la modification de ce paramètre :**
        *   *Lorsqu'il est activé (Oui) :* La fonctionnalité est active (par exemple, le champ téléphone est visible, les pièces jointes sont autorisées).
        *   *Lorsqu'il est désactivé (Non) :* La fonctionnalité est inactive (par exemple, le champ téléphone est masqué, les pièces jointes ne sont pas autorisées).
    *   **Valeur recommandée :** Dépend entièrement des besoins de votre entreprise pour chaque paramètre spécifique (voir les paramètres individuels ci-dessous).
-   **Conforme au RGPD**

    *   **Ce que fait ce paramètre :** Active une case à cocher sur vos formulaires où les clients doivent explicitement accepter votre politique de confidentialité avant de soumettre leurs données. Ceci est crucial pour la conformité au RGPD.
    *   **Effet de la modification de ce paramètre :**
        *   *Lorsqu'il est activé :* Une case à cocher obligatoire apparaît sur vos formulaires, indiquant généralement quelque chose comme "J'accepte la politique de confidentialité". Le formulaire ne peut pas être soumis tant que cette case n'est pas cochée.
        *   *Lorsqu'il est désactivé :* Aucune case à cocher de consentement RGPD n'apparaîtra.
    *   **Valeur recommandée :** **OUI** si votre boutique opère dans des régions soumises au RGPD (par exemple, l'UE) ou si vous souhaitez garantir les meilleures pratiques en matière de confidentialité des données.
    *   **Scénario / exemple pour le marchand :** Une boutique basée dans l'UE *doit* activer ceci pour collecter légalement les données clients via des formulaires.
-   **Page de politique de confidentialité**

    *   **Ce que fait ce paramètre :** Si la conformité RGPD est activée, ce paramètre vous permet de lier à la page CMS de la politique de confidentialité de votre boutique. La case à cocher de consentement RGPD inclura généralement un lien vers cette page.
    *   **Effet de la modification de ce paramètre :**
        *   *Lorsqu'une page est sélectionnée :* Le texte de consentement RGPD inclura un lien cliquable vers la page de politique de confidentialité que vous avez choisie.
        *   *Lorsqu'aucune page n'est sélectionnée :* Le texte de consentement RGPD pourrait apparaître sans lien, ou lier à une page par défaut, ce qui n'est pas idéal pour la conformité.
    *   **Valeur recommandée :** Sélectionnez la page CMS officielle de la politique de confidentialité de votre boutique.
    *   **Scénario / exemple pour le marchand :** Après avoir activé le RGPD, vous sélectionneriez la page CMS intitulée "Politique de confidentialité" dans la liste déroulante.
-   **ReCaptcha (v2)**

    *   **Ce que fait ce paramètre :** Active Google reCAPTCHA v2 sur vos formulaires pour protéger contre le spam et les bots.
    *   **Effet de la modification de ce paramètre :**
        *   *Lorsqu'il est activé :* La case à cocher reCAPTCHA "Je ne suis pas un robot" apparaîtra sur vos formulaires. Les utilisateurs doivent relever ce défi avant de soumettre.
        *   *Lorsqu'il est désactivé :* Aucune protection reCAPTCHA n'est active.
    *   **Valeur recommandée :** **OUI** pour empêcher les soumissions de spam. Vous devrez également configurer la clé de site et la clé secrète ci-dessous.
    *   **Scénario / exemple pour le marchand :** Si vous recevez beaucoup de spam via vos formulaires de contact, l'activation de reCAPTCHA est la première étape pour le combattre.
-   **Clé de site ReCaptcha**

    *   **Ce que fait ce paramètre :** C'est une clé publique fournie par Google reCAPTCHA qui permet à votre site web d'afficher le widget reCAPTCHA.
    *   **Effet de la modification de ce paramètre :**
        *   *Lorsqu'elle est correctement saisie :* Le widget reCAPTCHA apparaîtra et fonctionnera correctement sur vos formulaires.
        *   *Lorsqu'elle est incorrecte ou vide :* reCAPTCHA ne fonctionnera pas, et les formulaires pourraient échouer à être soumis ou afficher des erreurs.
    *   **Valeur recommandée :** La clé de site obtenue depuis votre compte Google reCAPTCHA.
    *   **Scénario / exemple pour le marchand :** Après avoir créé une paire de clés reCAPTCHA v2 sur la console d'administration Google reCAPTCHA, vous copieriez la "clé de site" ici.
-   **Clé secrète ReCaptcha**

    *   **Ce que fait ce paramètre :** C'est une clé privée fournie par Google reCAPTCHA qui permet à votre serveur de vérifier la réponse reCAPTCHA. Elle doit être gardée secrète.
    *   **Effet de la modification de ce paramètre :**
        *   *Lorsqu'elle est correctement saisie :* Votre serveur peut vérifier avec succès si un utilisateur a réussi le défi reCAPTCHA.
        *   *Lorsqu'elle est incorrecte ou vide :* La vérification échouera, et les utilisateurs légitimes pourraient ne pas pouvoir soumettre de formulaires.
    *   **Valeur recommandée :** La clé secrète obtenue depuis votre compte Google reCAPTCHA.
    *   **Scénario / exemple pour le marchand :** Vous copieriez la "clé secrète" depuis votre console d'administration Google reCAPTCHA ici.
-   **URL du Webhook (Slack/Discord)**

    *   **Ce que fait ce paramètre :** Vous permet d'envoyer des notifications de soumission de formulaire à un canal Slack ou Discord spécifié via un webhook. Cela fournit des alertes instantanées à l'équipe.
    *   **Effet de la modification de ce paramètre :**
        *   *Lorsqu'une URL valide est saisie :* Chaque soumission de formulaire déclenchera une notification vers votre canal Slack/Discord configuré.
        *   *Lorsqu'il est vide :* Aucune notification de webhook ne sera envoyée.
    *   **Valeur recommandée :** Votre URL de webhook Slack ou Discord. Laissez vide si vous n'utilisez pas ces services pour les notifications.
    *   **Scénario / exemple pour le marchand :** Votre équipe de support client utilise Slack. Vous configurez un webhook dans Slack, collez l'URL ici, et maintenant chaque nouvelle demande apparaît directement dans leur canal #support-client.
-   **CSS personnalisé (front-office)**

    *   **Ce que fait ce paramètre :** Fournit une zone de texte où vous pouvez ajouter votre propre code CSS personnalisé pour styliser les formulaires sur votre front-office. Ceci est utile pour affiner l'apparence afin qu'elle corresponde parfaitement à votre marque.
    *   **Effet de la modification de ce paramètre :**
        *   *Lorsque du CSS est saisi :* Les styles définis ici seront appliqués à vos formulaires, remplaçant les styles par défaut du module.
    *   **Valeur recommandée :** Utilisez ceci uniquement si vous avez des besoins de style spécifiques au-delà de l'apparence par défaut du module. Consultez un web designer si vous n'êtes pas sûr.
    *   **Scénario / exemple pour le marchand :** Vous voulez que le bouton de soumission du formulaire soit d'une nuance de vert spécifique qui correspond à votre logo. Vous ajouteriez du CSS comme `.cfrompro-form button[type="submit"] { background-color: #00FF00; }` ici.
-   **Longueur minimale de la question (caractères)**

    *   **Ce que fait ce paramètre :** Définit le nombre minimum de caractères requis pour le champ principal "Question" ou "Message" dans vos formulaires.
    *   **Effet de la modification de ce paramètre :**
        *   *Lorsqu'il est défini sur 10 :* Les clients doivent taper au moins 10 caractères dans le champ message pour soumettre le formulaire.
        *   *Lorsqu'il est défini sur 0 (ou très bas) :* Permet des messages très courts.
    *   **Valeur recommandée :** 10-20 caractères pour encourager les clients à fournir suffisamment de détails.
    *   **Scénario / exemple pour le marchand :** Pour éviter les demandes vagues comme "Bonjour", vous définissez ceci sur 15, garantissant que les clients fournissent un message plus descriptif.
-   **Longueur maximale de la question (caractères)**

    *   **Ce que fait ce paramètre :** Définit le nombre maximal de caractères autorisés pour le champ principal "Question" ou "Message".
    *   **Effet de la modification de ce paramètre :**
        *   *Lorsqu'il est défini sur 500 :* Les clients ne peuvent pas taper plus de 500 caractères dans le champ message.
    *   **Valeur recommandée :** 500-1000 caractères, selon le niveau de détail que vous attendez des demandes. Trop bas pourrait frustrer les utilisateurs, trop haut pourrait entraîner des messages trop longs.
    *   **Scénario / exemple pour le marchand :** Vous voulez empêcher les essais extrêmement longs dans le formulaire de contact, vous définissez donc ceci sur 750 caractères.
-   **Autoriser les pièces jointes d'images**

    *   **Ce que fait ce paramètre :** Active ou désactive la possibilité pour les clients de télécharger des fichiers (comme des images, des PDF) avec leur soumission de formulaire.
    *   **Effet de la modification de ce paramètre :**
        *   *Lorsqu'il est activé :* Un champ de téléchargement de fichier apparaîtra sur vos formulaires.
        *   *Lorsqu'il est désactivé :* Aucune option de téléchargement de fichier ne sera disponible.
    *   **Valeur recommandée :** **OUI** si les clients ont souvent besoin de fournir des captures d'écran, des confirmations de commande ou d'autres documents. **NON** si vous voulez garder les formulaires simples.
    *   **Scénario / exemple pour le marchand :** Pour un formulaire de support, l'activation des pièces jointes permet aux clients d'envoyer des captures d'écran des problèmes, ce qui est très utile.
-   **Taille maximale des pièces jointes (Mo)**

    *   **Ce que fait ce paramètre :** Si les pièces jointes sont autorisées, ce paramètre définit la taille maximale du fichier (en mégaoctets) qu'un client peut télécharger.
    *   **Effet de la modification de ce paramètre :**
        *   *Lorsqu'il est défini sur 5 :* Les clients peuvent télécharger des fichiers jusqu'à 5 Mo. Les fichiers plus volumineux seront rejetés.
    *   **Valeur recommandée :** 2-5 Mo est généralement suffisant pour la plupart des documents et images sans surcharger votre serveur.
    *   **Scénario / exemple pour le marchand :** Vous autorisez les pièces jointes mais voulez empêcher les fichiers énormes, vous définissez donc la limite à 3 Mo.
-   **Durée du message de succès (ms)**

    *   **Ce que fait ce paramètre :** Contrôle la durée pendant laquelle le message "Formulaire soumis avec succès" (souvent une notification "toast") reste visible pour le client après qu'il ait soumis un formulaire. Mesuré en millisecondes (1000 ms = 1 seconde).
    *   **Effet de la modification de ce paramètre :**
        *   *Lorsqu'il est défini sur 3000 :* Le message de succès disparaîtra après 3 secondes.
        *   *Lorsqu'il est défini sur 0 :* Le message pourrait rester indéfiniment ou disparaître immédiatement (selon le thème/navigateur).
    *   **Valeur recommandée :** 3000-5000 ms (3-5 secondes) est un bon équilibre, donnant aux clients suffisamment de temps pour le lire sans être intrusif.
    *   **Scénario / exemple pour le marchand :** Vous voulez que les clients voient clairement la confirmation, vous le définissez donc sur 4000 ms.

### 2.2 Écrans d'administration dédiés et vues de contrôleur

Le module ajoute de nouveaux éléments de menu sous **"Advanced Contact Form Pro"** dans votre Back Office PrestaShop.

#### 2.2.1 Gestion des formulaires (Back Office > Advanced Contact Form Pro > Formulaires)

Cet écran vous permet de créer, modifier et gérer tous vos formulaires de contact personnalisés.

-   **Nom de l'écran et emplacement du menu :** **Advanced Contact Form Pro > Formulaires**
-   **Actions et paramètres disponibles :**
    *   **Vue Liste (Grille) :** Affiche un tableau de tous vos formulaires créés, indiquant leur nom, leur ID et leur statut.
    *   **Ajouter un nouveau formulaire :** Cliquez sur le bouton "Ajouter un nouveau formulaire" pour créer un tout nouveau formulaire personnalisé.
    *   **Modifier le formulaire :** Cliquez sur l'icône "Modifier" à côté d'un formulaire dans la liste pour modifier ses paramètres.
    *   **Supprimer le formulaire :** Cliquez sur l'icône "Supprimer" pour supprimer un formulaire.
    *   **Champs de configuration du formulaire (lors de l'ajout/modification) :**
        *   **Nom du formulaire :** Un nom interne clair pour votre formulaire (par exemple, "Demande de gros", "Support produit").
        *   **Shortcode :** Un code unique (par exemple, `[cfrompro id="1"]`) que vous utiliserez pour intégrer ce formulaire spécifique dans des pages CMS ou des descriptions de produits.
        *   **Statut du formulaire :** Activer/Désactiver le formulaire. Les formulaires désactivés n'apparaîtront pas sur le front-office.
        *   **Email(s) du destinataire pour CE formulaire :** Vous pouvez remplacer l'email(s) du destinataire global pour ce formulaire spécifique. C'est très puissant pour acheminer les demandes.
        *   **Email de réponse automatique pour CE formulaire :** Remplace l'email de réponse automatique global pour ce formulaire.
        *   **Titre de l'email (pour le propriétaire de la boutique) pour CE formulaire :** Remplace l'objet de l'email global pour les notifications de ce formulaire.
        *   **Champs personnalisés :** C'est ici que vous définissez les champs uniques pour *ce* formulaire. Vous pouvez ajouter des champs de texte, des zones de texte, des listes déroulantes, des cases à cocher, des boutons radio, des téléchargements de fichiers, et plus encore. Pour chaque champ personnalisé, vous pouvez définir :
            *   **Libellé :** Ce que le client voit (par exemple, "Nom de votre entreprise").
            *   **Type :** (Texte, Zone de texte, Sélection, Case à cocher, Radio, Fichier, etc.).
            *   **Obligatoire :** Ce champ est-il obligatoire ?
            *   **Placeholder :** Texte d'aide à l'intérieur du champ de saisie.
            *   **Options (pour Sélection, Case à cocher, Radio) :** Définissez les choix que les clients peuvent sélectionner.
            *   **Règles de validation :** (par exemple, format d'email, nombre uniquement).
        *   **Paramètres du déclencheur flottant :**
            *   **Activer le déclencheur flottant :** Afficher un bouton flottant sur le front-office qui ouvre ce formulaire.
            *   **Texte du déclencheur :** Quel texte apparaît sur le bouton flottant (par exemple, "Contactez-nous").
            *   **Position du déclencheur :** Où le bouton apparaît (par exemple, gauche, droite, en bas à gauche).
            *   **Icône du déclencheur :** Choisissez une icône pour le bouton.
            *   **Délai du déclencheur (ms) :** Combien de temps attendre avant que le bouton flottant n'apparaisse (par exemple, 2000ms = 2 secondes).
            *   **Couleur du déclencheur, Couleur du texte, Couleur au survol :** Personnalisez l'apparence du bouton.
-   **Effet des changements :**
    *   L'ajout/modification d'un formulaire le rend disponible pour l'intégration ou comme déclencheur flottant.
    *   Les modifications apportées aux champs personnalisés affectent directement ce que les clients voient et remplissent sur ce formulaire spécifique.
    *   Les modifications apportées aux emails des destinataires acheminent les soumissions vers différents services.
-   **Flux de travail recommandé pour la gestion quotidienne de la boutique :**
    1.  Décidez du type de demande que vous souhaitez traiter (par exemple, "Demande de gros").
    2.  Allez dans **Formulaires** et cliquez sur "Ajouter un nouveau formulaire".
    3.  Donnez-lui un nom clair.
    4.  Ajoutez tous les champs personnalisés spécifiques dont vous avez besoin (par exemple, Nom de l'entreprise, Numéro de TVA, Type d'entreprise, Volume de commande estimé).
    5.  Définissez un email de destinataire spécifique si ce formulaire doit être envoyé à une équipe particulière (par exemple, `grossiste@votreboutique.com`).
    6.  Enregistrez le formulaire. Notez son shortcode.
    7.  Intégrez le shortcode dans une page CMS pertinente (par exemple, "Informations sur les grossistes").

#### 2.2.2 Gestion des questions (Back Office > Advanced Contact Form Pro > Questions)

Cet écran sert de boîte de réception pour toutes les soumissions de formulaires.

-   **Nom de l'écran et emplacement du menu :** **Advanced Contact Form Pro > Questions**
-   **Actions et paramètres disponibles :**
    *   **Vue Liste (Grille) :** Affiche un tableau de toutes les questions/demandes soumises.
        *   **Colonnes :** Affiche des informations telles que le nom du formulaire, le nom du client, l'email, le sujet (le cas échéant), la date de soumission et le statut.
    *   **Voir la question :** Cliquez sur l'icône "Voir" (loupe) à côté d'une demande pour en voir tous les détails.
        *   **Vue détaillée :** Affiche toutes les informations soumises par le client, y compris les réponses aux champs personnalisés, les pièces jointes (avec des liens de téléchargement) et le formulaire d'où elle provient.
        *   **Section Répondre :** Vous permet de répondre directement au client depuis le Back Office de PrestaShop. Cette réponse sera envoyée depuis l'email de contact par défaut de votre boutique.
        *   **Changer le statut :** Vous pouvez mettre à jour le statut d'une demande (par exemple, "Nouveau", "En cours", "Résolu").
    *   **Supprimer la question :** Supprime une demande de la liste.
-   **Effet des changements :**
    *   La visualisation d'une question vous permet de traiter efficacement les demandes des clients.
    *   Répondre à partir d'ici conserve un enregistrement de la communication (bien que le module ne stocke pas l'historique complet des réponses en lui-même, il envoie un email standard).
    *   Le changement de statut vous aide à suivre la progression de chaque demande.
-   **Flux de travail recommandé pour la gestion quotidienne de la boutique :**
    1.  Vérifiez régulièrement cette section "Questions".
    2.  Pour chaque nouvelle demande, cliquez sur "Voir" pour lire les détails.
    3.  Si une réponse est nécessaire, utilisez la fonction "Répondre".
    4.  Mettez à jour le statut (par exemple, à "En cours") pour indiquer qu'elle est en cours de traitement.
    5.  Une fois résolue, changez le statut en "Résolu".

#### 2.2.3 index.php (cfrompro/controllers/admin/index.php)

Ce fichier est généralement un espace réservé ou un redirecteur dans les modules PrestaShop et ne représente pas un écran direct et configurable pour le marchand. Il garantit que si quelqu'un tente d'accéder directement au répertoire `controllers/admin`, il est redirigé ou une action par défaut est effectuée, empêchant les vulnérabilités de listage de répertoire. Les marchands n'interagiront pas directement avec cela.

### 2.3 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Valeur par défaut / Recommandée | Objectif et impact |
| --- | --- | --- | --- |
| **Configuration principale du module** | Profil de support de template | Classic | Adapte le style du formulaire à votre thème. |
| | Email de réponse automatique | `info@votreboutique.com` | Adresse email pour les confirmations client. |
| | Titre de l'email (pour le propriétaire de la boutique) | Nouvelle soumission de formulaire de contact | Ligne d'objet pour vos emails de notification. |
| | Email(s) du destinataire | `contact@votreboutique.com` | Où toutes les soumissions de formulaire sont envoyées (globalement). |
| | BCC pour l'email de notification de la boutique | Vide | Copie cachée des notifications pour le suivi interne. |
| | Conforme au RGPD | OUI | Ajoute une case à cocher obligatoire de consentement à la politique de confidentialité. |
| | Page de politique de confidentialité | Votre page CMS de politique de confidentialité | Lie la case à cocher RGPD à votre politique. |
| | ReCaptcha (v2) | OUI | Active Google reCAPTCHA pour la protection contre le spam. |
| | Clé de site ReCaptcha | Votre clé de site Google | Clé publique pour le widget reCAPTCHA. |
| | Clé secrète ReCaptcha | Votre clé secrète Google | Clé privée pour la vérification reCAPTCHA. |
| | URL du Webhook (Slack/Discord) | Vide | Envoie des notifications à Slack/Discord. |
| | CSS personnalisé (front-office) | Vide | Ajoute des styles personnalisés à vos formulaires. |
| | Longueur minimale de la question (caractères) | 10-20 | Caractères minimum pour le champ de message principal. |
| | Longueur maximale de la question (caractères) | 500-1000 | Caractères maximum pour le champ de message principal. |
| | Autoriser les pièces jointes d'images | OUI | Active le téléchargement de fichiers sur les formulaires. |
| | Taille maximale des pièces jointes (Mo) | 2-5 | Taille maximale pour les fichiers téléchargés. |
| | Durée du message de succès (ms) | 3000-5000 | Durée pendant laquelle la notification de succès reste visible. |
| **Gestion des formulaires** | Nom du formulaire | Nom descriptif | Nom interne de votre formulaire personnalisé. |
| | Shortcode | `[cfrompro id="X"]` généré automatiquement | Code pour intégrer le formulaire. |
| | Statut du formulaire | Activé | Active/désactive le formulaire. |
| | Email(s) du destinataire pour CE formulaire | Email(s) spécifique(s) | Remplace le destinataire global pour ce formulaire. |
| | Champs personnalisés | Variable | Définit des champs de saisie uniques pour chaque formulaire. |
| | Activer le déclencheur flottant | NON (ou OUI pour des formulaires spécifiques) | Affiche un bouton flottant pour ouvrir le formulaire. |
| | Texte du déclencheur | "Contactez-nous" | Texte sur le bouton flottant. |
| | Position du déclencheur | Droite/Gauche | Emplacement du bouton flottant. |
| **Gestion des questions** | Voir la question | N/A | Affiche tous les détails d'une demande client. |
| | Répondre | N/A | Envoie une réponse par email au client. |
| | Changer le statut | Nouveau, En cours, Résolu | Suivre le traitement des demandes. |

## 3. Dépannage pour le marchand et questions fréquemment posées (FAQ)

**Q : Mes formulaires ne s'affichent pas correctement, ou le style est cassé.**
R :

-   **Vérifiez le "Profil de support de template" :** Allez dans **Modules > Gestionnaire de modules > Advanced Contact Form Builder Pro > Configurer** et assurez-vous que le "Profil de support de template" correspond à votre thème PrestaShop actuel (par exemple, 'Classic' pour le thème par défaut).
-   **Videz le cache Smarty :** Allez dans **Paramètres avancés > Performances**, faites défiler jusqu'à "Cache", et cliquez sur "Vider le cache". Parfois, d'anciens fichiers de style peuvent rester bloqués.
-   **CSS personnalisé :** Si vous avez ajouté du CSS personnalisé, vérifiez-le attentivement pour les erreurs. Supprimez-le temporairement pour voir si c'est la cause du problème.
-   **Conflits de thème :** Si le problème persiste, votre thème pourrait avoir un conflit. Contactez le développeur de votre thème ou le support MyPresta.eu.

**Q : Je ne reçois pas de notifications par email lorsqu'un formulaire est soumis.**
R :

-   **Vérifiez les emails des destinataires :** Allez dans **Modules > Gestionnaire de modules > Advanced Contact Form Builder Pro > Configurer** et vérifiez que les "Email(s) du destinataire" sont corrects. Vérifiez également les paramètres individuels du formulaire sous **Advanced Contact Form Pro > Formulaires** pour voir si un formulaire spécifique remplace le destinataire global.
-   **Vérifiez le dossier spam :** Les emails pourraient aller dans votre dossier spam ou courrier indésirable.
-   **Paramètres de messagerie du serveur :** Assurez-vous que les paramètres de messagerie de votre boutique PrestaShop sont correctement configurés (**Paramètres avancés > E-mail**). Testez l'envoi d'un email normal depuis PrestaShop.
-   **Fournisseur d'hébergement :** Votre fournisseur d'hébergement pourrait avoir des limites ou des problèmes d'envoi d'emails. Vérifiez vos journaux de serveur ou contactez-les.

**Q : reCAPTCHA ne fonctionne pas, ou les formulaires ne se soumettent pas avec reCAPTCHA activé.**
R :

-   **Vérifiez les clés :** Vérifiez à nouveau votre "Clé de site ReCaptcha" et votre "Clé secrète ReCaptcha" dans la configuration principale du module. Assurez-vous qu'il n'y a pas de fautes de frappe et qu'elles correspondent à une configuration reCAPTCHA v2 sur votre compte Google.
-   **Enregistrement du domaine :** Assurez-vous que le nom de domaine de votre boutique est correctement enregistré dans votre compte Google reCAPTCHA.
-   **Problèmes réseau :** Désactivez temporairement reCAPTCHA pour voir si les formulaires se soumettent. Si c'est le cas, le problème vient certainement de la configuration reCAPTCHA ou de la communication avec les serveurs de Google.

**Q : Comment traduire les champs de formulaire et les messages dans d'autres langues ?**
R :

-   **Système de traduction PrestaShop :** Allez dans **International > Traductions**.
-   **Type de traduction :** Sélectionnez "Traductions des modules installés".
-   **Sélectionnez votre thème :** Choisissez votre thème actuel.
-   **Sélectionnez votre langue :** Choisissez la langue que vous souhaitez traduire.
-   **Module :** Sélectionnez "cfrompro" (le nom technique du module).
-   Vous verrez alors une liste de toutes les chaînes traduisibles du module, y compris les libellés de champ, les messages de succès et les messages d'erreur. Traduisez-les et enregistrez.

**Q : Mon bouton de déclenchement flottant n'apparaît pas.**
R :

-   **Activer le déclencheur :** Allez dans **Advanced Contact Form Pro > Formulaires**, modifiez le formulaire que vous souhaitez déclencher, et assurez-vous que "Activer le déclencheur flottant" est défini sur OUI.
-   **Délai du déclencheur :** Vérifiez le paramètre "Délai du déclencheur (ms)". S'il s'agit d'un nombre élevé, vous devrez peut-être simplement attendre plus longtemps pour qu'il apparaisse.
-   **Conflits de thème :** Certains thèmes peuvent avoir du CSS qui masque le bouton ou du JavaScript qui interfère. Vérifiez la console de développement de votre navigateur pour les erreurs.
-   **Cache :** Videz votre cache PrestaShop (**Paramètres avancés > Performances**).

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

### 4.1 Vue d'ensemble de l'architecture

Le module **Advanced Contact Form Builder Pro** (`cfrompro`) suit un modèle MVC (Modèle-Vue-Contrôleur) PrestaShop standard, étendant les classes PrestaShop de base pour sa fonctionnalité. Il utilise `ObjectModel` pour gérer les formulaires personnalisés et les questions soumises, utilise des contrôleurs d'administration dédiés pour la gestion du Back Office, et s'intègre avec divers hooks PrestaShop pour l'affichage en front-office et les actions en back-end. Les champs personnalisés sont gérés via une classe dédiée et stockés au format JSON.

### 4.2 Contrôleurs (`controllers/`)

#### Contrôleurs Front-Office

-   `cfrompro/controllers/front/index.php`
    *   **Nom de la classe :** `CfromproIndexModuleFrontController` (probable, basé sur le nom du fichier)
    *   **Classe parente :** `ModuleFrontController`
    *   **Responsabilité :** Ce contrôleur est probablement responsable de la gestion de l'affichage initial d'un formulaire s'il est accédé via une URL directe (bien que la plupart des formulaires soient intégrés ou ouverts via AJAX). Il pourrait également gérer le rendu initial du déclencheur flottant ou de la modale contenant le formulaire.
-   `cfrompro/controllers/front/question.php`
    *   **Nom de la classe :** `CfromproQuestionModuleFrontController` (probable)
    *   **Classe parente :** `ModuleFrontController`
    *   **Responsabilité :** C'est le contrôleur principal pour le traitement des soumissions de formulaires. Il reçoit les données POST des formulaires, effectue la validation (y compris reCAPTCHA, longueur des champs, champs obligatoires, taille des pièces jointes), enregistre les données soumises (question et champs personnalisés) dans la base de données, envoie des notifications par email au propriétaire de la boutique et une réponse automatique au client, et déclenche potentiellement le webhook. Il renvoie des réponses JSON pour les soumissions AJAX (par exemple, messages de succès/erreur).

#### Contrôleurs d'administration Back-Office

-   `cfrompro/controllers/admin/AdminCfromproForm.php`
    *   **Nom de la classe :** `AdminCfromproFormController`
    *   **Classe parente :** `ModuleAdminController`
    *   **Nom de l'onglet :** "Formulaires" sous "Advanced Contact Form Pro"
    *   **Entité gérée :** `CfromproForm` (`ObjectModel` hypothétique pour les formulaires)
    *   **Responsabilité :** Gère les opérations CRUD (Créer, Lire, Mettre à jour, Supprimer) pour les formulaires personnalisés. Il définit la vue liste (grille) pour les formulaires et la structure du formulaire pour l'ajout/modification d'un formulaire. Ce contrôleur gère l'enregistrement des paramètres du formulaire, y compris la structure JSON complexe pour les champs personnalisés.
-   `cfrompro/controllers/admin/AdminCfromproQuestion.php`
    *   **Nom de la classe :** `AdminCfromproQuestionController`
    *   **Classe parente :** `ModuleAdminController`
    *   **Nom de l'onglet :** "Questions" sous "Advanced Contact Form Pro"
    *   **Entité gérée :** `CfromproQuestion` (`ObjectModel` hypothétique pour les questions soumises)
    *   **Responsabilité :** Gère les opérations CRUD pour les questions soumises. Il affiche la liste des demandes, permet de visualiser les détails des questions individuelles et offre la fonctionnalité de répondre aux clients et de modifier le statut d'une demande.
-   `cfrompro/controllers/admin/index.php`
    *   **Nom de la classe :** (Aucun, généralement)
    *   **Classe parente :** (Aucune, généralement)
    *   **Responsabilité :** C'est une pratique PrestaShop standard pour empêcher le listage direct des répertoires. Il contient généralement un simple `header('Location: ../../index.php?controller=AdminHome');` ou similaire pour rediriger vers le tableau de bord du Back Office. Il ne représente pas un contrôleur fonctionnel pour la logique du module.

### 4.3 Classes et modèles de base (`classes/`)

-   `cfrompro/classes/CfromproCustomFields.php`
    *   **Nom de la classe :** `CfromproCustomFields`
    *   **Classe parente :** (Probablement `ObjectModel` ou une classe de base personnalisée pour la gestion de données complexes)
    *   **Table de base de données :** (Probablement `ps_cfrompro_form` si elle stocke les définitions de champs personnalisés dans l'objet formulaire, ou une table `ps_cfrompro_custom_field` séparée si les champs sont des entités autonomes). Le dossier du module indique `cfrompro_form` et `cfrompro_question` comme tables gérées, suggérant que les champs personnalisés sont probablement sérialisés dans la table `cfrompro_form`.
    *   **Champs `$definition` :** Si elle étend `ObjectModel`, elle définirait des champs liés aux propriétés des champs personnalisés (par exemple, `id_cfrompro_custom_field`, `id_cfrompro_form`, `type`, `label`, `required`, `options`, `validation`). Compte tenu de la description du module, il est plus probable que les champs personnalisés soient stockés sous forme de chaîne JSON dans la table `cfrompro_form`, et que cette classe fournisse des méthodes d'aide pour analyser, valider et rendre ces champs.
    *   **Méthodes publiques clés et logique métier :**
        *   Méthodes pour ajouter, modifier et supprimer des définitions de champs personnalisés dans un formulaire.
        *   Méthodes pour rendre les champs personnalisés dans le template du front-office.
        *   Méthodes pour valider les données de champs personnalisés soumises.
        *   Méthodes pour sérialiser/désérialiser les configurations de champs personnalisés vers/depuis JSON.

### 4.4 Actifs JavaScript (`views/js/`)

-   `cfrompro/views/cfrompro.js`
    *   **Portée :** Front-office.
    *   **Responsabilité :** C'est le fichier JavaScript principal du front-office. Il gère probablement :
        *   L'affichage et la gestion du bouton de déclenchement flottant (événements de clic, délais).
        *   L'ouverture et la fermeture de la modale/popup du formulaire.
        *   La soumission AJAX des formulaires (collecte des données, envoi au contrôleur `question.php`).
        *   L'affichage des messages de succès/erreur (notifications toast).
        *   La validation côté client des champs de formulaire.
        *   L'intégration avec reCAPTCHA v2 (rendu du widget, obtention du jeton de réponse).
        *   Les mises à jour dynamiques basées sur les types de champs personnalisés (par exemple, affichage/masquage d'options pour les listes déroulantes).
-   `cfrompro/views/js/admin-button-style.js`
    *   **Portée :** Back-office (AdminCfromproFormController).
    *   **Responsabilité :** Fournit des fonctionnalités JavaScript pour styliser le bouton de déclenchement flottant dans l'interface de configuration du formulaire. Cela peut inclure des sélecteurs de couleurs, des aperçus d'icônes et des mises à jour en temps réel d'un aperçu du bouton.
-   `cfrompro/views/js/admin-form-layout.js`
    *   **Portée :** Back-office (AdminCfromproFormController).
    *   **Responsabilité :** Gère la mise en page dynamique et la gestion des champs personnalisés dans l'interface de création/édition de formulaire. Cela inclurait :
        *   L'ajout de nouveaux champs personnalisés (génération dynamique de HTML pour différents types de champs).
        *   Le réordonnancement des champs (glisser-déposer).
        *   L'édition des propriétés des champs (libellé, type, obligatoire, options).
        *   La suppression des champs.
        *   La sérialisation de la configuration des champs personnalisés en une chaîne JSON avant d'enregistrer le formulaire.
-   `cfrompro/views/js/admin-icon-picker-data.js`
    *   **Portée :** Back-office (AdminCfromproFormController).
    *   **Responsabilité :** Contient les données (par exemple, un tableau de classes d'icônes ou de chemins SVG) utilisées par le sélecteur d'icônes pour le bouton de déclenchement flottant.
-   `cfrompro/views/js/admin-icon-picker.js`
    *   **Portée :** Back-office (AdminCfromproFormController).
    *   **Responsabilité :** Implémente l'interface utilisateur et la logique pour la sélection d'une icône pour le bouton de déclenchement flottant. Il utilise les données de `admin-icon-picker-data.js` pour afficher les icônes disponibles et met à jour l'icône sélectionnée dans le formulaire.

### 4.5 Feuilles de style CSS (`views/css/`)

-   `cfrompro/views/cfrompro.css`
    *   **Portée :** Style client du front-office.
    *   **Responsabilité :** Fournit le style de base pour les formulaires de contact, le déclencheur flottant, les popups modales et les messages de succès/erreur sur le front-office. Il définit la mise en page générale, la typographie, les couleurs et la réactivité.
    *   **Sélecteurs de classe CSS clés :** `.cfrompro-form`, `.cfrompro-field`, `.cfrompro-trigger`, `.cfrompro-modal`, `.cfrompro-toast`.
-   `cfrompro/views/css/admin-button-style.css`
    *   **Portée :** Style du formulaire d'administration du Back-office.
    *   **Responsabilité :** Style les éléments liés à la configuration de l'apparence du bouton de déclenchement flottant dans le Back Office (par exemple, sélecteurs de couleurs, zones d'aperçu d'icônes).
-   `cfrompro/views/css/admin-custom-fields.css`
    *   **Portée :** Style du formulaire d'administration du Back-office.
    *   **Responsabilité :** Style l'interface de gestion des champs personnalisés dans le constructeur de formulaires (par exemple, poignées de glisser-déposer, panneaux de configuration des champs).
-   `cfrompro/views/css/admin-form-layout.css`
    *   **Portée :** Style du formulaire d'administration du Back-office.
    *   **Responsabilité :** Fournit la structure de mise en page générale et le style de la page de création/édition de formulaire dans le Back Office.
-   `cfrompro/views/css/admin-icon-picker.css`
    *   **Portée :** Style du formulaire d'administration du Back-office.
    *   **Responsabilité :** Style l'interface de sélection d'icônes pour le bouton de déclenchement flottant.

### 4.6 Structure des templates Smarty (`views/templates/`)

#### Templates de hook (`views/templates/hook/`)

-   `cfrompro/views/templates/hook/dashboard_recent_messages.tpl`
    *   **Hook :** `displaydashboardZoneTwo` (ou un hook de tableau de bord similaire).
    *   **Sortie :** Un bloc sur le tableau de bord PrestaShop affichant les soumissions de formulaires récentes, offrant un aperçu rapide au marchand.

#### Templates d'administration (`views/templates/admin/`)

-   `cfrompro/views/templates/admin/button_style_block.tpl`
    *   **Portée :** AdminCfromproFormController (page d'édition de formulaire).
    *   **Sortie :** HTML pour la section où le marchand configure l'apparence du bouton de déclenchement flottant (couleurs, texte, icône).
-   `cfrompro/views/templates/admin/conversation_reply.tpl`
    *   **Portée :** AdminCfromproQuestionController (page de vue de la question).
    *   **Sortie :** HTML pour le formulaire de réponse et la section de mise à jour du statut lors de la visualisation d'une question soumise.
-   `cfrompro/views/templates/admin/custom_fields_block.tpl`
    *   **Portée :** AdminCfromproFormController (page d'édition de formulaire).
    *   **Sortie :** Le conteneur principal et les contrôles pour ajouter, modifier et organiser les champs personnalisés dans un formulaire. Ce template fonctionne probablement en conjonction avec `admin-form-layout.js`.
-   `cfrompro/views/templates/admin/form_layout_block.tpl`
    *   **Portée :** AdminCfromproFormController (page d'édition de formulaire).
    *   **Sortie :** Structure de mise en page générale pour la page de configuration du formulaire, enveloppant d'autres blocs comme les champs personnalisés et les styles de bouton.
-   `cfrompro/views/templates/admin/question_extras.tpl`
    *   **Portée :** AdminCfromproQuestionController (page de vue de la question).
    *   **Sortie :** Affiche des détails supplémentaires liés à une question soumise, tels que les pièces jointes ou des métadonnées spécifiques.
-   `cfrompro/views/templates/admin/question_form_profile.tpl`
    *   **Portée :** AdminCfromproQuestionController (page de vue de la question).
    *   **Sortie :** Affiche les détails du formulaire à partir duquel la question a été soumise.
-   `cfrompro/views/templates/admin/topic_options_block.tpl`
    *   **Portée :** AdminCfromproFormController (page d'édition de formulaire).
    *   **Sortie :** Si le module prend en charge des sujets prédéfinis, ce template rendrait les options pour les configurer.

#### Templates Front-office (`views/templates/front/` et racine `views/`)

-   `cfrompro/views/cfrompro-extra-forms.tpl`
    *   **Hook :** Probablement `displayFooter` ou `actionOutputHTMLBefore` pour le rendu des formulaires qui ne sont pas directement intégrés mais apparaissent dans des modales.
    *   **Sortie :** Contient la structure HTML pour les formulaires destinés à être affichés dans une fenêtre modale, souvent déclenchée par un bouton flottant.
-   `cfrompro/views/cfrompro-extra-trigger.tpl`
    *   **Hook :** Probablement `displayHeader` ou `actionOutputHTMLBefore` pour le rendu du bouton de déclenchement flottant.
    *   **Sortie :** Le HTML pour le bouton flottant qui, lorsqu'il est cliqué, ouvre un formulaire de contact.
-   `cfrompro/views/cfrompro-form-body.tpl`
    *   **Portée :** Utilisé par d'autres templates (par exemple, `cfrompro-extra-forms.tpl`) ou directement lors de l'intégration d'un formulaire via un shortcode.
    *   **Sortie :** La structure HTML de base pour un seul formulaire de contact, y compris les champs, les libellés, la case à cocher reCAPTCHA, la case à cocher RGPD et le bouton de soumission. Ce template est dynamiquement rempli avec des champs personnalisés.
-   `cfrompro/views/classic/cfrompro-extra-forms.tpl`
    *   **Portée :** Surcharge spécifique au thème pour `cfrompro-extra-forms.tpl`.
    *   **Sortie :** Identique à `cfrompro-extra-forms.tpl` mais spécifiquement adapté à la structure HTML du thème Classic.
-   `cfrompro/views/classic/cfrompro-extra-trigger.tpl`
    *   **Portée :** Surcharge spécifique au thème pour `cfrompro-extra-trigger.tpl`.
    *   **Sortie :** Identique à `cfrompro-extra-trigger.tpl` mais spécifiquement adapté au thème Classic.
-   `cfrompro/views/partials/cfrompro-custom-field-single.tpl`
    *   **Portée :** Inclus par `cfrompro-form-body.tpl`.
    *   **Sortie :** Rend le HTML pour un seul champ personnalisé en fonction de son type (texte, zone de texte, sélection, etc.).
-   `cfrompro/views/partials/cfrompro-custom-fields.tpl`
    *   **Portée :** Inclus par `cfrompro-form-body.tpl`.
    *   **Sortie :** Itère sur les définitions de champs personnalisés pour un formulaire et les rend chacun en utilisant `cfrompro-custom-field-single.tpl`.
-   `cfrompro/views/partials/cfrompro-field-fragment.tpl`
    *   **Portée :** Inclus par `cfrompro-form-body.tpl` ou `cfrompro-custom-field-single.tpl`.
    *   **Sortie :** Un fragment réutilisable de HTML pour les éléments de champ courants comme les libellés, les messages d'erreur ou les wrappers.

### 4.7 Schéma de la base de données et carte des hooks

#### Tables de la base de données

-   `ps_cfrompro_form` : Stocke les définitions de chaque formulaire de contact personnalisé créé par le module.
    *   `id_cfrompro_form` : Clé primaire.
    *   `name` : Nom interne du formulaire.
    *   `shortcode` : Identifiant unique pour l'intégration.
    *   `active` : (booléen) Statut du formulaire.
    *   `recipient_emails` : (texte) Emails des destinataires remplacés pour ce formulaire.
    *   `autoresponder_email` : (texte) Email de réponse automatique remplacé pour ce formulaire.
    *   `email_title` : (texte) Objet de l'email remplacé pour ce formulaire.
    *   `custom_fields_json` : (texte/JSON) Chaîne JSON sérialisée contenant les définitions de tous les champs personnalisés pour ce formulaire (type, libellé, obligatoire, options, validation, etc.).
    *   `trigger_enabled` : (booléen) Indique si le déclencheur flottant est actif pour ce formulaire.
    *   `trigger_text` : (texte) Texte sur le déclencheur flottant.
    *   `trigger_position` : (texte) Position du déclencheur flottant.
    *   `trigger_icon` : (texte) Classe d'icône pour le déclencheur.
    *   `trigger_delay_ms` : (int) Délai d'apparition du déclencheur.
    *   `trigger_color`, `trigger_text_color`, `trigger_hover_color` : (texte) Style du déclencheur.
-   `ps_cfrompro_question` : Stocke chaque question/demande soumise.
    *   `id_cfrompro_question` : Clé primaire.
    *   `id_cfrompro_form` : Clé étrangère vers `ps_cfrompro_form`.
    *   `customer_name` : Nom du client soumettant.
    *   `customer_email` : Email du client soumettant.
    *   `customer_phone` : Numéro de téléphone (si visible/obligatoire).
    *   `topic` : Sujet sélectionné (si visible/obligatoire).
    *   `message` : Contenu principal de la question/du message.
    *   `submitted_data_json` : (texte/JSON) Chaîne JSON sérialisée contenant toutes les valeurs de champs personnalisés soumises.
    *   `attachments` : (texte/JSON) Chemin(s) vers les fichiers téléchargés.
    *   `ip_address` : Adresse IP du soumetteur.
    *   `date_add` : Horodatage de la soumission.
    *   `status` : (int/texte) Statut de la demande (par exemple, 0=Nouveau, 1=En cours, 2=Résolu).
-   `ps_configuration` : Les paramètres du module sont stockés ici avec des clés comme `cfrompro_TITLE`, `cfrompro_AUTORESPONDER`, `cfrompro_GDPR`, `cfrompro_recaptcha_sitekey`, etc.

#### Tableau des hooks enregistrés

| Nom du Hook | Moment d'exécution | Objectif technique |
| --- | --- | --- |
| `actionOutputHTMLBefore` | Avant que la sortie HTML ne soit envoyée au navigateur. | Injection du HTML du déclencheur flottant, des formulaires modaux ou du CSS/JS personnalisé globalement. |
| `displaydashboardZoneTwo` | Rend le contenu dans la deuxième zone du tableau de bord PrestaShop. | Affichage d'un résumé des soumissions de formulaires récentes dans le Back Office. |
| `actionAdminControllerSetMedia` | Lorsqu'un contrôleur d'administration définit ses médias (JS/CSS). | Mise en file d'attente du JS spécifique au Back Office (`admin-button-style.js`, `admin-form-layout.js`, etc.) et du CSS (`admin-button-style.css`, `admin-custom-fields.css`, etc.) pour les pages de configuration du module. |
| `displayHeader` | Dans la section `<head>` du front-office. | Mise en file d'attente du JS spécifique au front-office (`cfrompro.js`) et du CSS (`cfrompro.css`), et potentiellement des scripts reCAPTCHA. |

## 5. Support officiel et mises à jour

Pour les dernières mises à jour du module, les corrections de bugs et le support officiel, veuillez vous connecter à votre compte client sur [MyPresta.eu](https://mypresta.eu/my-account/orders/). Notre équipe de support est disponible pour vous aider avec tout problème ou question que vous pourriez avoir concernant le module **Advanced Contact Form Builder Pro**.
