---
title: "Points de fidélité manuels et historique - Manuel du marchand et guide de configuration"
description: "Manuel utilisateur complet, guide de configuration écran par écran et référence développeur pour le module PrestaShop Points de fidélité manuels et historique par MyPresta.eu."
sidebar:
  label: "Points de fidélité manuels et historique - Manuel du marchand et guide de configuration"
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module Manual Loyalty Points & History sur MyPresta.eu](https://mypresta.eu/modules/advertising-and-marketing/manual-loyalty-points-history.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/advertising-marketing/manual-loyalty-points-history/)
>
> ---


# Points de fidélité manuels et historique

## 1. Exigences et compatibilité

- **Versions de PrestaShop prises en charge** : PrestaShop 1.7.x, 8.x, 9.x
- **Compatibilité PHP** : PHP 7.1 - 8.5
- **Exigences d'hébergement** : Extensions PHP standard (cURL, JSON, OpenSSL). Ce module nécessite également que le système de fidélité principal de PrestaShop (par exemple, `myprestaloyalty` ou le module de fidélité par défaut de PrestaShop) soit installé et actif, car il étend ses fonctionnalités.

## 2. Guide de configuration complet (chaque paramètre regroupé par écran)

### 2.1 Page de configuration du module (Back Office > Modules > Configurer)

Ceci est l'écran de configuration principal du module, où vous pouvez définir les préférences globales.

- **Activer les notifications par e-mail pour les changements manuels de points :**
  - **Ce que fait ce paramètre :** Contrôle si les clients reçoivent une notification par e-mail lorsque leurs points de fidélité sont ajustés manuellement par un administrateur.
  - **Effet de la modification de ce paramètre :**
    - *Lorsqu'activé (OUI) :* Après avoir ajouté ou soustrait manuellement des points pour un client, un e-mail sera envoyé à son adresse e-mail enregistrée, l'informant du changement et de son nouveau solde.
    - *Lorsqu'désactivé (NON) :* Aucune notification par e-mail ne sera envoyée aux clients pour les ajustements manuels de points.
  - **Valeur recommandée :** OUI
  - **Scénario / exemple de marchand :** Activez ceci pour tenir les clients pleinement informés et engagés dans leur programme de fidélité. Si un client reçoit des points en compensation, une notification par e-mail confirme l'action et renforce votre service client. Si désactivé, les clients pourraient ne pas réaliser immédiatement que leur solde a changé.

### 2.2 Écrans d'administration dédiés et vues du contrôleur

#### 2.2.1 Gestion manuelle des points de fidélité (Back Office > Modules > Points de fidélité manuels)

Ceci est l'écran principal où vous gérerez et enregistrerez tous les ajustements manuels des points de fidélité. Vous pouvez trouver cet écran en naviguant vers **Modules > Points de fidélité manuels** dans le menu de votre Back Office PrestaShop.

Cet écran présente une liste de tous les ajustements historiques manuels des points de fidélité. Vous pouvez également ajouter de nouveaux ajustements à partir d'ici.

**Actions et paramètres disponibles :**

- **Bouton « Ajouter un nouvel ajustement de points de fidélité » :**

  - **Ce que fait ce bouton :** Cliquer sur ce bouton vous amène à un formulaire où vous pouvez ajouter ou soustraire manuellement des points de fidélité pour un client spécifique.
  - **Effet de cliquer sur ce bouton :** Ouvre un nouveau formulaire pour créer une nouvelle entrée de points de fidélité.
- **Formulaire d'ajustement des points de fidélité (accessible via « Ajouter un nouvel ajustement de points de fidélité ») :**

  - **Champ de recherche client :**

    - **Ce que fait ce champ :** Vous permet de rechercher et de sélectionner le client dont vous souhaitez ajuster les points de fidélité. Commencez à taper le nom ou l'e-mail du client, et une liste de clients correspondants apparaîtra.
    - **Effet de la modification de ce paramètre :** Une fois un client sélectionné, l'ajustement sera appliqué à son compte.
    - **Valeur recommandée :** Sélectionnez le bon client.
    - **Scénario / exemple de marchand :** Vous devez ajouter des points pour « Jean Dupont ». Tapez « Jean » et sélectionnez-le dans la liste déroulante.
  - **Champ Points à ajouter/soustraire :**

    - **Ce que fait ce champ :** C'est ici que vous entrez le nombre de points de fidélité à ajuster.
    - **Effet de la modification de ce paramètre :**
      - *Nombre positif (par exemple, 50) :* Ajoute 50 points au solde de fidélité du client.
      - *Nombre négatif (par exemple, -25) :* Soustrait 25 points du solde de fidélité du client.
    - **Valeur recommandée :** Le nombre exact de points que vous avez l'intention d'ajouter ou de soustraire.
    - **Scénario / exemple de marchand :** Un client a reçu un article endommagé, vous ajoutez donc « 100 » points en compensation. Un autre client a retourné un article pour lequel il avait gagné des points, vous soustrayez donc « -50 » points.
  - **Champ Période de validité (jours) :**

    - **Ce que fait ce champ :** Définit le nombre de jours pendant lesquels les points ajoutés manuellement seront valides à partir de la date d'ajustement. Après cette période, les points expireront.
    - **Effet de la modification de ce paramètre :**
      - *Défini sur un nombre (par exemple, 365) :* Les points expireront après 365 jours.
      - *Défini sur 0 ou vide :* Les points n'auront pas de date d'expiration (ou suivront l'expiration par défaut de votre module de fidélité principal, le cas échéant).
    - **Valeur recommandée :** Considérez la stratégie globale de votre programme de fidélité. Si vous souhaitez encourager un échange rapide, définissez une période plus courte. Pour un geste commercial général, une période plus longue ou aucune expiration pourrait être préférable.
    - **Scénario / exemple de marchand :** Vous offrez 50 points comme cadeau d'anniversaire, valables pendant « 30 » jours pour encourager un achat rapide. Pour une compensation majeure, vous pouvez le laisser vide pour aucune expiration.
  - **Champ Raison / Commentaire :**

    - **Ce que fait ce champ :** Un champ de texte pour enregistrer la raison de l'ajustement des points de fidélité. Ceci est destiné au suivi interne et à l'audit.
    - **Effet de la modification de ce paramètre :** Ce texte sera enregistré dans le journal de fidélité, fournissant un historique clair des raisons pour lesquelles les points ont été ajustés. Il n'est pas visible pour le client.
    - **Valeur recommandée :** Fournissez toujours une raison claire et concise.
    - **Scénario / exemple de marchand :** « Compensation pour produit endommagé #12345 », « Cadeau d'anniversaire pour client VIP », « Points pour participation à un événement hors ligne ».
  - **Bouton « Enregistrer » :**

    - **Ce que fait ce bouton :** Applique l'ajustement des points de fidélité au compte du client et enregistre l'entrée dans le journal d'historique.
    - **Effet de cliquer sur ce bouton :** Les points de fidélité du client sont mis à jour, et une nouvelle entrée apparaît dans le tableau « Gestion manuelle des points de fidélité ». Si les notifications par e-mail sont activées, le client reçoit un e-mail.
- **Tableau de l'historique des points de fidélité :**

  - **Ce que fait ce tableau :** Affiche une liste chronologique de tous les ajustements manuels des points de fidélité effectués via ce module.
  - **Colonnes :**
    - **ID :** Identifiant unique de l'entrée du journal.
    - **Client :** Le nom du client dont les points ont été ajustés.
    - **Points :** Le nombre de points ajoutés ou soustraits.
    - **Validité (jours) :** La période d'expiration définie pour les points.
    - **Raison :** Le commentaire interne fourni pour l'ajustement.
    - **Date d'ajout :** La date et l'heure de l'ajustement.
    - **Admin :** Le nom de l'administrateur qui a effectué l'ajustement.
  - **Effet des changements :** Ce tableau fournit une piste d'audit complète. Vous pouvez trier et filtrer les entrées pour examiner les ajustements passés.

**Flux de travail recommandé pour la gestion quotidienne de la boutique :**

1. Lorsqu'une situation nécessite un ajustement manuel des points (par exemple, une plainte client, une promotion spéciale), naviguez vers **Modules > Points de fidélité manuels**.
2. Cliquez sur « Ajouter un nouvel ajustement de points de fidélité ».
3. Recherchez et sélectionnez le client.
4. Entrez le nombre de points (positif pour ajouter, négatif pour soustraire).
5. Définissez une période de validité si vous le souhaitez.
6. Surtout, ajoutez une « Raison / Commentaire » claire pour référence future.
7. Cliquez sur « Enregistrer ».
8. Vérifiez le tableau d'historique pour confirmer l'entrée.

### 2.3 Tableau de référence rapide de la configuration

| Écran / Vue | Paramètre / Option | Par défaut / Recommandé | Objectif et impact |
| --- | --- | --- | --- |
| Configuration du module | Activer les notifications par e-mail | OUI | Envoyer un e-mail au client lors des changements manuels de points. |
| Points de fidélité manuels | Recherche client | N/A | Sélectionner le client pour l'ajustement des points. |
| Points de fidélité manuels | Points à ajouter/soustraire | N/A | Entrer une valeur positive ou négative pour les points. |
| Points de fidélité manuels | Période de validité (jours) | Vide (Pas d'expiration) | Définir l'expiration des points ajoutés manuellement. |
| Points de fidélité manuels | Raison / Commentaire | N/A | Note interne pour la piste d'audit. |

## 3. Dépannage pour les marchands et questions fréquemment posées (FAQ)

**Q : J'ai ajouté des points, mais le client dit qu'il n'a pas reçu d'e-mail.**
R : Tout d'abord, vérifiez si « Activer les notifications par e-mail pour les changements manuels de points » est défini sur OUI dans la configuration du module. Si c'est le cas, vérifiez les journaux d'e-mails de votre boutique (si disponibles) ou les journaux de courrier de votre serveur pour voir si l'e-mail a été envoyé. De plus, conseillez au client de vérifier son dossier de spam ou de courrier indésirable. Assurez-vous que les paramètres d'e-mail de votre PrestaShop sont correctement configurés et envoient des e-mails avec succès.

**Q : Le solde des points de fidélité du client n'a pas été mis à jour après que j'ai ajouté des points.**
R : Ce module met à jour le système de fidélité principal de PrestaShop. Si le solde ne s'affiche pas, videz d'abord le cache de votre PrestaShop (Paramètres avancés > Performances > Vider le cache). Si le problème persiste, assurez-vous que votre module de fidélité principal (par exemple, le module de fidélité par défaut de PrestaShop ou `myprestaloyalty`) est correctement installé et actif, car ce module en dépend.

**Q : Puis-je modifier un ajustement de points de fidélité après l'avoir enregistré ?**
R : Non, pour des raisons d'audit et d'intégrité des données, les ajustements individuels de points de fidélité ne peuvent pas être modifiés une fois enregistrés. Si vous avez fait une erreur, vous devez ajouter un *nouvel* ajustement pour la corriger (par exemple, si vous avez accidentellement ajouté 100 points au lieu de 50, ajoutez une nouvelle entrée soustrayant 50 points) et notez clairement la correction dans le champ « Raison / Commentaire ».

**Q : Que se passe-t-il si je soustrais plus de points qu'un client n'en a ?**
R : Le système autorisera généralement la soustraction, ce qui entraînera un solde de points de fidélité négatif pour le client. Cela peut être utile dans des scénarios spécifiques, mais généralement, vous devez vous assurer que les clients ont suffisamment de points avant de soustraire.

**Q : Comment savoir qui a effectué un ajustement de points spécifique ?**
R : La colonne « Admin » dans le tableau d'historique « Gestion manuelle des points de fidélité » indique clairement quel compte administrateur a effectué chaque ajustement, fournissant une piste d'audit complète.

## 4. Guide du développeur et du webmaster (Architecture technique et carte du code)

### 4.1 Aperçu de l'architecture

Le module `Points de fidélité manuels et historique` (myprestaloyalty_manual) est conçu comme un module PrestaShop standard, étendant la fonctionnalité de fidélité de base. Il fonctionne principalement dans le Back Office, fournissant une interface administrative pour les ajustements manuels de points et la journalisation. Il exploite le modèle MVC de PrestaShop pour son contrôleur d'administration et utilise un `ObjectModel` pour le stockage persistant des entrées de journal manuelles. Le module s'intègre au système de fidélité existant en manipulant directement les points de fidélité des clients.

### 4.2 Contrôleurs (`controllers/`)

- **Contrôleurs Front-Office** : Ce module n'inclut aucun contrôleur front-office dédié. Tout l'affichage des points de fidélité côté client est géré par le module de fidélité principal.
- **Contrôleurs d'administration Back-Office** :

  - `controllers/admin/AdminMyprestaloyaltyManualController.php`

    - **Nom de la classe et classe parente** : `AdminMyprestaloyaltyManualController` étend `ModuleAdminController`.
    - **Responsabilité** : C'est le contrôleur administratif principal pour la gestion des ajustements manuels des points de fidélité. Il gère l'affichage de la liste du journal de fidélité (en utilisant `HelperList`) et le formulaire pour ajouter de nouveaux ajustements (en utilisant `HelperForm`). Il traite les soumissions de formulaires, valide les données, crée des objets `MyprestaloyaltyManualLog` et met à jour les points de fidélité du client. Il déclenche également les notifications par e-mail si elles sont activées.
    - **Nom de l'onglet** : « Points de fidélité manuels » (sous le menu Modules).
    - **Entité gérée** : `MyprestaloyaltyManualLog` (le journal des ajustements manuels).
  - `controllers/admin/index.php`

    - **Responsabilité** : Il s'agit d'un fichier de remplacement vide, souvent inclus dans les répertoires `controllers/admin` des modules PrestaShop pour empêcher l'affichage du contenu du répertoire. Il ne contient aucune logique de contrôleur fonctionnelle.

### 4.3 Classes et modèles de base (`classes/`)

- `classes/index.php`

  - **Responsabilité** : Fichier de remplacement vide pour empêcher l'affichage du contenu du répertoire.
- `classes/MyprestaloyaltyManualLog.php`

  - **Table de base de données avec laquelle il interagit** : `ps_myprestaloyalty_manual_log`
  - **Étend `ObjectModel`** : Oui.
  - **Champs `$definition`** :
    - `id_myprestaloyalty_manual_log` : Clé primaire.
    - `id_customer` : ID du client affecté.
    - `points` : Nombre de points ajustés (peut être positif ou négatif).
    - `validity` : Période de validité en jours pour les points.
    - `reason` : Raison textuelle de l'ajustement.
    - `id_employee` : ID de l'administrateur qui a effectué l'ajustement.
    - `date_add` : Horodatage de l'ajout de l'entrée.
  - **Méthodes publiques clés et logique métier encapsulée** :
    - Méthodes `ObjectModel` standard (`add`, `update`, `delete`).
    - Gère la validation des données pour ses champs.

### 4.4 Actifs JavaScript (`views/js/`)

Ce module n'inclut aucun fichier JavaScript personnalisé. Le JS standard de PrestaShop pour la gestion des formulaires et AJAX (par exemple, la recherche de clients) est utilisé.

### 4.5 Feuilles de style CSS (`views/css/`)

Ce module n'inclut aucun fichier CSS personnalisé. Il s'appuie sur le style par défaut du Back Office de PrestaShop.

### 4.6 Structure des modèles Smarty (`views/templates/`)

Ce module n'inclut aucun fichier de modèle Smarty personnalisé. Il s'appuie sur les modèles `HelperList` et `HelperForm` par défaut de PrestaShop pour son interface Back Office.

### 4.7 Schéma de base de données et carte des hooks

- **Tables de base de données** :

  - `ps_myprestaloyalty_manual_log` :
    - `id_myprestaloyalty_manual_log` INT(10) UNSIGNED NOT NULL AUTO_INCREMENT
    - `id_customer` INT(10) UNSIGNED NOT NULL
    - `points` INT(10) NOT NULL
    - `validity` INT(10) UNSIGNED DEFAULT 0
    - `reason` TEXT NULL
    - `id_employee` INT(10) UNSIGNED NOT NULL
    - `date_add` DATETIME NOT NULL
    - PRIMARY KEY (`id_myprestaloyalty_manual_log`)
    - KEY `id_customer` (`id_customer`)
- **Enregistrements de configuration (dans `ps_configuration`)** :

  - `PS_LOYALTY_MANUAL_EMAIL_ENABLED` : Stocke la valeur booléenne (0 ou 1) pour activer/désactiver les notifications par e-mail.
- **Table des hooks enregistrés** :

  | Nom du hook | Moment d'exécution | Objectif technique |
  | --- | --- | --- |
  | `displayBackOfficeHeader` | Rend le contenu dans la section `<head>` du Back Office. | Utilisé pour inclure des CSS/JS spécifiques au module (bien que ce module n'en ait pas) ou pour enregistrer des éléments de menu d'administration. |
  | `actionCustomerAccountAdd` | Après la création d'un nouveau compte client. | Non explicitement utilisé par ce module, mais un hook de fidélité courant. |
  | `actionValidateOrder` | Après la validation réussie d'une commande. | Non explicitement utilisé par ce module, mais un hook de fidélité courant. |
  | `actionObjectCustomerUpdateAfter` | Après la mise à jour d'un objet client. | Non explicitement utilisé par ce module. |
  | `actionObjectCustomerDeleteAfter` | Après la suppression d'un objet client. | Non explicitement utilisé par ce module. |

  *Note : La fonctionnalité principale du module (ajout/soustraction de points) est déclenchée directement depuis son contrôleur d'administration, et non via des hooks front-office. Le module interagit avec les méthodes du système de fidélité de base pour ajuster les points.*

## 5. Support officiel et mises à jour

Pour les dernières mises à jour, corrections de bugs et support officiel du module « Points de fidélité manuels et historique », veuillez vous référer à votre compte client sur [MyPresta.eu](https://mypresta.eu/my-account/orders/). Notre équipe de support est disponible pour vous aider avec tout problème ou question concernant la fonctionnalité du module.
