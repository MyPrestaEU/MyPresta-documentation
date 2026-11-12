---
title: "MyFAQ - documentation et manuel d'utilisation"
sidebar:
  label: "MyFAQ - documentation et manuel d'utilisation"
description: Manuel de configuration et de dépannage pour les boutiques qui ont déjà MyFAQ.
---

> ⚠️ **Notice:** This is the documentation officielle du module PrestaShop.
> - 🛒 **Vous trouverez la spécification commerciale complète, le journal des modifications et les options d'achat sur la page officielle du produit sur MyPresta.eu :** [Acheter le module MyFAQ: product FAQ with FAQPage schema sur MyPresta.eu](https://mypresta.eu/modules/front-office-features/myfaq-product-faq-with-faqpage-schema.html)
> - 🌐 **Portail de documentation en ligne officiel :** [Lire la documentation interactive sur MyPresta.eu](https://mypresta.eu/docs/fr/front-office/myfaq-product-faq-with-faqpage-schema/)
>
> ---


## 1. Prérequis

MyFAQ tourne à l'intérieur de PrestaShop. Il n'a pas besoin d'un autre module.

- PrestaShop 1.7.0.0 jusqu'à PrestaShop 9. Le même paquet et les mêmes écrans servent PrestaShop 8 et PrestaShop 9.
- PHP 7.0 ou plus récent, et au minimum la version de PHP exigée par cette version de PrestaShop. L'installation et l'adresse planifiée utilisent `random_bytes`.
- cURL est nécessaire pour générer des questions. Sans cURL la génération s'arrête et la ligne de progression affiche `curl_missing`. La vérification des mises à jour utilise cURL quand PHP le fournit, et lit l'adresse directement quand cURL manque et que le serveur autorise les lectures distantes.
- OpenSSL chiffre la clé d'IA que vous enregistrez. Sans OpenSSL la clé reste enregistrée telle que vous la collez.
- Aucun autre module n'est obligatoire. La page produit du thème doit imprimer le pied de produit ou les onglets produit supplémentaires pour que le client voie l'accordéon.
- Un compte chez OpenAI, Anthropic, Google, DeepSeek ou Mistral n'est utile que pour ce fournisseur. La tuile compatible peut pointer vers votre propre serveur, par exemple Ollama, vLLM ou LM Studio, et ce serveur peut fonctionner sans compte externe.
- Un système externe n'est utile que lorsque vous appelez l'adresse FAQ depuis l'extérieur de la boutique. Un planificateur n'est utile que lorsque le serveur doit terminer une file alors que le back-office est fermé.

Un grand catalogue s'écrit une langue à la fois. Laissez la page de génération en masse ouverte jusqu'à ce que la barre atteigne 100 %, ou planifiez l'adresse depuis **Génération en masse**. Chaque appel travaille environ 20 secondes puis s'arrête, pour ne pas heurter la limite de temps de PHP. Un appel écrit au plus 30 langues.

## 2. Installation

1. Dans le back-office, ouvrez **Modules**, puis **Gestionnaire de modules**.
2. Téléversez le zip du module et cliquez sur **Installer**.
3. Ouvrez **Configurer** sur **MyFAQ**. La page s'ouvre sur **Affichage**. La barre contient aussi **Entrées**, **IA**, **Génération en masse**, **API** et **Mises à jour**.
4. MyFAQ n'ajoute pas de point dans le menu de gauche. Le catalogue, la liste des clés et l'historique des requêtes sont des pages cachées. La première ouverture de **Configurer** les crée et donne au profil de l'employé actuel le droit de les ouvrir.
5. L'installation ne vide pas le cache dans une étape séparée. Si après une mise à jour la page produit montre encore l'ancienne mise en page, videz le cache dans **Paramètres avancés**, **Performances**.

Sur un produit, ouvrez le produit et le bloc **MyFAQ**. C'est là que vous fixez l'emplacement de ce produit et que vous rédigez des questions qui ne lui appartiennent qu'à lui.

Pour éteindre le module, utilisez l'interrupteur du **Gestionnaire de modules**. La page produit n'imprime plus l'accordéon et la fiche produit n'affiche plus le bloc MyFAQ. Les questions, les clés et les réglages restent. Rallumez le module et ils sont réutilisés. Le module n'a pas de bouton activer ou désactiver qui lui soit propre.

Pour le retirer, cliquez sur **Désinstaller** et confirmez. La désinstallation retire les pages cachées, les questions et réponses, les liens, l'emplacement par produit, les clés API, l'historique des requêtes, la file de génération et les réglages d'affichage et d'IA. Les deux adresses planifiées cessent de fonctionner parce que le secret qu'elles contiennent est supprimé. Les fichiers du module restent sur le serveur jusqu'à ce que vous supprimiez le module. Une nouvelle installation repart avec des entrées vides et les réglages d'une installation fraîche. Les anciennes questions ne reviennent pas. L'interrupteur de vérification des mises à jour n'est pas effacé par la désinstallation.

## 3. Configuration et travail quotidien

Rédigez une question et une réponse, puis liez cette entrée à un produit ou à quelque chose que le produit possède déjà : une catégorie, une valeur de caractéristique, une valeur d'attribut, une étiquette, une marque ou un fournisseur. Un seul lien correspondant suffit. La FAQ de la page produit est l'accordéon que la boutique imprime après avoir rassemblé chaque correspondance active dans la langue du client et remplacé les jetons. Les entrées liées directement au produit passent en premier. Ensuite, l'ordre est la position que vous fixez.

Le pied de produit se place sous le produit. L'onglet produit est le même accordéon dans un onglet. Sur un produit vous pouvez forcer le pied, forcer l'onglet ou masquer MyFAQ. Masquer retire aussi le bloc FAQ que lisent les moteurs de recherche. Le client ouvre seulement les questions. Il n'y a pas de formulaire pour qu'il envoie une nouvelle question. Le parcours se termine quand la page produit affiche l'accordéon, ou quand l'emplacement est **Masquer** ou qu'aucune entrée active ne correspond : ce produit n'affiche alors aucun bloc MyFAQ.

Écrire avec un modèle est facultatif. Enregistrez le fournisseur et la clé dans **IA**. Enregistrer là ne génère rien. **Générer** sur un produit, ou **Démarrer la génération** dans **Génération en masse**, met le travail en file. Chaque langue d'un produit est une requête. **Ajouter** conserve les entrées IA actuelles et en ajoute d'autres. **Remplacer les entrées IA non verrouillées liées uniquement au produit** supprime les entrées IA non verrouillées liées seulement à ce produit, puis en écrit de nouvelles. Une entrée que vous avez modifiée est verrouillée et conservée. Une entrée également liée à une catégorie ou à une autre cible est conservée. L'adresse planifiée ne lit pas les filtres de **Génération en masse**. Elle termine une file qui existe déjà ou, avec la seconde adresse, ajoute chaque produit actif de cette boutique qui n'a pas encore d'entrée IA.

Un système externe est facultatif. Dans **API**, générez une clé, copiez l'URL de base et collez les deux dans ce système.

Ouvrez **Modules**, **Gestionnaire de modules**, **MyFAQ**, **Configurer**. La ligne sous la barre explique la section ouverte.

Les noms des tuiles de fournisseur, les titres des cartes de données et les textes des boutons de shortcode restent en anglais à l'écran. Les phrases de la barre de progression restent aussi en anglais.

### 3.1 Affichage

**Affichage** est la présentation de toute la boutique. Un produit peut encore utiliser un autre emplacement.

| Champ | Au départ | Ce que cela fait |
|---|---|---|
| **Emplacement** | Pied de page du produit | Valeur de la boutique pour chaque produit qui ne définit pas le sien. **Pied de page du produit** imprime l'accordéon sous le produit. **Onglet produit** ajoute un onglet sur la page produit. Sur un produit vous pouvez encore forcer le pied, l'onglet ou masquer MyFAQ. Les autres modules du même hook restent là où **Design**, **Positions** les place. |
| **Titre de l'onglet** | FAQ dans chaque langue | Libellé de l'onglet produit. Il n'est utilisé que lorsque l'emplacement est **Onglet produit**. Remplissez-le dans chaque langue vendue. Si une langue est vide, cette langue affiche FAQ. |
| **Titre au-dessus de la liste** | FAQ dans chaque langue | Titre imprimé au-dessus des questions, dans le pied comme dans l'onglet. Remplissez-le par langue. Les clients voient ce texte. Laissez FAQ si vous n'avez pas besoin d'un titre personnalisé. |
| **Inclure les catégories parentes** | Non | **Oui** affiche aussi une entrée liée à un parent des catégories du produit, ainsi un seul lien couvre les sous-catégories. Le parcours s'arrête avant Accueil, donc un lien vers Accueil ne couvre pas tout le catalogue. **Non** ne fait correspondre que les catégories dans lesquelles le produit se trouve directement. |
| **Ouvrir la première question** | Non | **Oui** déplie la première réponse au chargement de la page. **Non** laisse toutes les réponses fermées jusqu'au clic du client. Les clients sans JavaScript voient toujours les réponses. |
| **Balisage schema FAQ** | Oui | **Oui** ajoute un seul bloc schema.org FAQPage construit à partir des questions réellement affichées sur ce produit, après remplacement des shortcodes. Les moteurs de recherche peuvent l'utiliser pour les résultats enrichis FAQ. **Non** affiche la FAQ sans ce bloc. Une liste vide ou un produit masqué ne le produisent jamais. |

Cliquez sur **Enregistrer**. La page affiche **Enregistré.**

### 3.2 Entrées

**Entrées** est un aperçu des questions. La ligne sous la barre dit qu'il s'agit des 10 entrées mises à jour le plus récemment, et que **Nouvelle entrée** et **Modifier** ouvrent le catalogue.

| Champ | Au départ | Ce que cela fait |
|---|---|---|
| **Nouvelle entrée** | un bouton | Ouvre le formulaire du catalogue pour une question neuve. |
| **Voir la liste complète** | un bouton | Ouvre le catalogue avec recherche, où vous changez l'ordre et supprimez une entrée. |
| **Question** | vide jusqu'à ce que vous en enregistriez une | La question dans la langue actuelle du back-office. **Aucune question dans cette langue** signifie que cette langue n'a pas de texte de question. |
| **Liée à** | vide | Jusqu'à quatre liens, puis des points de suspension. |
| **Source** | Rédigée à la main pour une entrée que vous avez tapée | **IA** ou **Rédigée à la main**. **verrouillée** signifie qu'un remplacement ultérieur conserve cette entrée. |
| **Statut** | Active sur une entrée neuve | **Active** est affichée sur les pages produit correspondantes. **Inactive** reste dans le back-office et est masquée dans la boutique. |

Le nombre à droite est le total des entrées, pas seulement les dix de cet aperçu. **Modifier** ouvre cette entrée dans le catalogue.

Quand il n'y a pas d'entrées, la page dit **Aucune entrée pour le moment** et explique que la boutique n'affiche rien tant qu'une entrée active n'est pas liée à un produit, une catégorie, une caractéristique, un attribut, une étiquette, une marque ou un fournisseur.

### 3.3 Catalogue

Ouvrez **Voir la liste complète**. Le titre de la page est **Entrées FAQ**. La note du haut dit que la recherche porte sur la question, le nom ou l'ID du produit, la langue et les autres liens. La question est celle de la langue actuelle du back-office. Le nom du produit ouvre ce produit. **Modifier** ouvre le formulaire sur cette page. **Haut** et **Bas** déplacent l'entrée. Faites glisser la colonne position pour définir le même ordre. **Supprimer** demande une confirmation. **Active** affiche ou masque l'entrée. Les entrées verrouillées sont conservées lorsque l'IA remplace un produit.

Colonnes : **ID**, **Question**, **Produit**, **Également lié à**, **Langues**, **Boutique**, **Source**, **Active**, **Verrouillée**, **Position**, **Créée**, **Mise à jour**.

**Boutique** affiche **Toutes les boutiques** lorsque l'entrée a été enregistrée avec le contexte de toutes les boutiques. Sinon elle affiche le nom de cette boutique. La vitrine d'une boutique affiche les entrées de toutes les boutiques et celles enregistrées pour cette boutique.

**Source** est **Rédigée à la main** ou **IA**. Filtrez cette colonne avec la liste. **Active** est un interrupteur sur la ligne : cliquez pour afficher ou masquer l'entrée. **Verrouillée** est une marque, pas un interrupteur. Modifier une entrée existante la verrouille. Une entrée neuve n'est pas verrouillée.

Les actions de ligne sont **Modifier**, **Haut**, **Bas** et **Supprimer**. **Supprimer** demande **Supprimer cette entrée ? Elle disparaîtra de tous les produits qui l'utilisaient.** L'action groupée **Supprimer la sélection** demande **Supprimer les entrées sélectionnées ? Elles disparaîtront de tous les produits qui les utilisaient.** Si une suppression ne se termine pas, la page affiche **L'entrée n'a pas pu être supprimée.**

**Nouvelle entrée** dans la barre ouvre un formulaire vide. **Retour au module** revient à **Entrées**.

Le titre du formulaire est **Nouvelle entrée** ou **Modifier l'entrée**.

| Champ | Au départ | Ce que cela fait |
|---|---|---|
| **Question** | vide | La ligne sur laquelle le client clique pour ouvrir la réponse. C'est l'en-tête de l'accordéon. Rédigez une question par langue. L'aide sous le champ dit que la langue par défaut est obligatoire. La question peut aussi contenir des shortcodes. Ils sont remplacés sur la page produit et affichés en texte brut. Si toutes les langues sont vides, **Enregistrer** affiche **Saisissez une question dans au moins une langue.** |
| **Réponse** | vide | Le texte affiché lorsque le client ouvre la question. Utilisez l'éditeur pour les paragraphes et les listes. Les shortcodes sont remplacés sur la page produit et le HTML environnant est conservé. La liste des shortcodes se trouve sous ce champ : cliquez sur un jeton pour l'insérer au curseur. Remplissez chaque langue que vous vendez. Une langue vide n'est pas affichée dans cette langue. |
| **Shortcodes** | les boutons de jeton | Cliquez sur un jeton pour l'insérer à l'endroit du curseur, dans la question ou dans la réponse. La boutique le remplace sur la page produit par les données de ce produit, dans la langue et la devise du client. Le texte enregistré conserve le jeton, donc une modification de prix ou de nom met à jour chaque entrée qui l'utilise. Dans la question, le résultat est du texte brut. |
| **Active** | Oui | **Oui** affiche l'entrée sur les pages produits correspondantes et l'inclut dans le schema. **Non** la conserve dans le back-office et la masque de la boutique. |
| **Produits** | aucun | Saisissez le nom d'un produit dans la zone de recherche et sélectionnez-le. L'entrée est affichée sur ces produits même si aucun autre lien ne correspond. Un seul lien correspondant suffit. Enregistrer remplace les liens précédents de cette entrée. |
| **Catégories** | aucune | Saisissez le nom d'une catégorie et sélectionnez-la. L'entrée est affichée sur les produits placés dans ces catégories. Un lien est une FAQ pour toute une catégorie. Les catégories parentes ne comptent que si cette option est activée dans **Affichage**. |
| **Valeurs de caractéristiques** | aucune | Saisissez une valeur de caractéristique et sélectionnez-la, par exemple Coton. L'entrée est affichée lorsque le produit a cette valeur. |
| **Valeurs d'attributs** | aucune | Saisissez une valeur d'attribut et sélectionnez-la, par exemple M. L'entrée est affichée lorsqu'une déclinaison du produit utilise cette valeur. |
| **Étiquettes** | aucune | Saisissez une étiquette et sélectionnez-la. L'entrée est affichée lorsque le produit possède cette étiquette dans la langue de la page. |
| **Marques** | aucune | Saisissez un nom de marque et sélectionnez-le. L'entrée est affichée sur les produits de ces marques. |
| **Fournisseurs** | aucun | Saisissez un nom de fournisseur et sélectionnez-le. L'entrée est affichée sur les produits de ces fournisseurs, y compris le fournisseur par défaut et les fournisseurs ajoutés sur les déclinaisons. |

**Enregistrer** sans aucun lien affiche **Liez l'entrée à au moins un produit, une catégorie, une caractéristique, un attribut, une étiquette, une marque ou un fournisseur.** Si la ligne ne peut pas être stockée, la page affiche **L'entrée n'a pas pu être enregistrée.** Un enregistrement réussi reste sur le formulaire et PrestaShop confirme la mise à jour. **Retour à la liste** revient au catalogue.

Les boutons de jeton, et le texte anglais de chaque bouton, sont :

| Jeton | Ce que voit le client |
|---|---|
| `[product_name]` | Nom du produit |
| `[product_reference]` | Référence |
| `[product_ean13]` | EAN-13 |
| `[product_isbn]` | ISBN |
| `[product_upc]` | UPC |
| `[product_mpn]` | MPN |
| `[product_condition]` | État : New, Used ou Refurbished |
| `[product_price]` | Prix TTC, dans la devise du client |
| `[product_price_tax_excl]` | Prix HT |
| `[product_price_before_discount]` | Prix avant réduction |
| `[product_discount_amount]` | Montant de la remise, vide lorsqu'il n'y a pas de réduction |
| `[product_discount_percent]` | Pourcentage de remise, vide lorsqu'il n'y a pas de réduction |
| `[product_quantity]` | Quantité disponible de la déclinaison par défaut, ou du produit s'il n'y a pas de déclinaison |
| `[product_availability]` | Libellé « disponible maintenant » si la quantité est supérieure à zéro, ou libellé « disponible plus tard » si la quantité est zéro |
| `[product_minimal_quantity]` | Quantité minimale |
| `[product_manufacturer]` | Marque |
| `[product_supplier]` | Fournisseur |
| `[product_category]` | Catégorie par défaut |
| `[product_categories]` | Toutes les catégories |
| `[product_features]` | Liste des caractéristiques, nom et valeur |
| `[product_feature id=ID]` | Une valeur de caractéristique. Remplacez ID par le numéro de la caractéristique dans **Catalogue**, **Attributs et caractéristiques**. |
| `[product_tags]` | Étiquettes dans la langue actuelle |
| `[product_url]` | URL du produit |
| `[product_weight]` | Poids avec l'unité de poids de la boutique |
| `[product_description_short]` | Description courte, en texte brut |
| `[shop_name]` | Nom de la boutique |
| `[shop_url]` | URL de la boutique |

La ligne sous les boutons dit de cliquer sur un shortcode pour l'insérer au curseur. Les prix et les noms sont remplacés sur la page produit, dans la devise et la langue du client. `[product_price]` est le shortcode de prix : il devient le prix vivant dans une réponse, dans la devise du client.

### 3.4 IA

**IA** enregistre la connexion utilisée par le générateur. La ligne sous la barre dit qu'enregistrer ici ne génère rien. Utilisez **Génération en masse** pour de nombreux produits, ou le bloc du produit pour un seul.

Cliquez sur une tuile. La tuile en cours affiche **Actif**. Une tuile affiche **Clé enregistrée**, **Pas de clé**, ou **Clé facultative** sur la tuile compatible. Les noms des tuiles restent en anglais.

| Tuile | Ce qu'elle appelle |
|---|---|
| **OpenAI** | Modèles GPT de l'API officielle d'OpenAI. La liste commence par `gpt-4o-mini`, `gpt-4o`, `gpt-4.1-mini`, `gpt-4.1`. |
| **Anthropic Claude** | Modèles Claude de l'API officielle d'Anthropic. La liste commence par `claude-sonnet-4-5`, `claude-3-5-haiku-latest`, `claude-3-5-sonnet-latest`. |
| **Google Gemini** | Modèles Gemini de l'API officielle de Google. La liste commence par `gemini-2.0-flash`, `gemini-1.5-pro`, `gemini-1.5-flash`. |
| **DeepSeek** | Modèles DeepSeek via une API compatible OpenAI. La liste commence par `deepseek-chat`. |
| **Mistral AI** | Modèles Mistral de l'API officielle. La liste commence par `mistral-small-latest`, `mistral-large-latest`. |
| **OpenAI-compatible / Ollama** | Votre propre serveur : Ollama, vLLM, LM Studio. Il peut fonctionner entièrement en local. La liste est vide jusqu'à ce que vous ajoutiez un identifiant de modèle. |

| Champ | Au départ | Ce que cela fait |
|---|---|---|
| **Fournisseur** | OpenAI | Cliquez sur une tuile pour choisir le service qui rédige les questions. La liste des modèles change immédiatement. **Enregistrer** conserve le fournisseur, la clé et le modèle. Les fournisseurs officiels appellent leur propre hôte. L'URL de base n'apparaît que pour la tuile compatible. |
| **Clé API** | vide | Secret du compte chez le fournisseur de la tuile sélectionnée. Collez une nouvelle clé pour remplacer celle enregistrée. Laissez le champ vide et enregistrez pour conserver la clé déjà enregistrée pour ce fournisseur. La clé est chiffrée lorsque le serveur a OpenSSL. Chaque tuile indique si une clé est enregistrée. Un serveur local compatible, comme Ollama, peut fonctionner sans clé. |
| **Supprimer la clé enregistrée** | Non | **Oui** supprime la clé enregistrée du fournisseur sélectionné lors de l'enregistrement. Utilisez-le lorsque vous changez ou révoquez une clé. **Non** laisse la clé enregistrée en place. Une génération sans clé échoue chez les fournisseurs officiels. |
| **URL de base compatible** | vide | Utilisée uniquement lorsque la tuile compatible est sélectionnée. Saisissez la racine de l'API qui se termine par `/v1`, par exemple `http://localhost:11434/v1` pour Ollama. Les fournisseurs officiels ignorent ce champ. Laissez-la vide et une exécution ne démarre pas : la page affiche **Définissez l'URL de base compatible dans l'onglet IA avant de lancer une exécution.** |
| **Modèle** | `gpt-4o-mini` pour OpenAI | Identifiant du modèle envoyé à chaque génération pour le fournisseur sélectionné. La liste contient les identifiants intégrés et ceux que vous avez ajoutés dans l'encadré sous ce formulaire. Un identifiant erroné est refusé par le fournisseur, et cette langue est marquée en échec dans la file. La tuile compatible affiche **Aucun modèle pour l'instant. Ajoutez-en un ci-dessous.** jusqu'à ce que vous en ajoutiez un. |
| **Température** | 0,4 | Liberté d'écriture du modèle, de 0 à 2. 0,4 garde les réponses proches des données produit. Une valeur plus élevée varie la formulation et peut s'éloigner des faits. Les valeurs hors de 0 à 2 sont ramenées dans cet intervalle. Certains fournisseurs refusent ce réglage. Le module réessaie alors une fois sans celui-ci. |
| **Jetons maximum** | 2000 | Limite supérieure de la longueur d'une réponse. 2000 suffisent pour quelques réponses courtes. Augmentez-la si les réponses sont coupées. Le fournisseur peut s'arrêter plus tôt. Les valeurs très élevées coûtent davantage et peuvent atteindre la limite du fournisseur. La valeur enregistrée reste entre 200 et 8000. |
| **Questions par produit** | 5 | Nombre de paires question-réponse à demander pour chaque produit et chaque langue. Ce nombre est la valeur par défaut de **Génération en masse** et de la page produit. 5 est un bon point de départ. Une exécution ultérieure peut utiliser un autre nombre. La valeur enregistrée reste entre 1 et 20. |
| **Instructions supplémentaires** | vide | Règles facultatives ajoutées à chaque prompt : ton, longueur ou sujets à éviter. Le module demande déjà au modèle d'écrire `[product_name]` et `[product_price]` au lieu d'un nom ou d'un prix fixe, afin qu'un changement de prix ultérieur reste correct. Laissez vide pour n'utiliser que les instructions intégrées. |

Cliquez sur **Enregistrer**. La page affiche **Enregistré.**

**Modèles que vous avez ajoutés** se trouve sous le formulaire. C'est un encadré séparé pour les identifiants qui ne sont pas dans la liste intégrée. Renommez ou retirez seulement ceux-là. Les modèles intégrés restent dans la liste **Modèle** et n'ont pas de bouton supprimer.

| Champ | Au départ | Ce que cela fait |
|---|---|---|
| **Nouvel identifiant de modèle** | vide | Ajoute l'identifiant à la tuile du fournisseur sélectionnée ci-dessus et le sélectionne pour la prochaine exécution. Lettres, chiffres et `.` `_` `:` `/` `@` `-` uniquement, jusqu'à 100 caractères. Un identifiant intégré est refusé. |
| **Ajouter un modèle** | un bouton | Enregistre cet identifiant. |
| **Enregistrer** sur une ligne que vous avez ajoutée | l'identifiant actuel | Renomme cet identifiant. S'il était le modèle sélectionné, la sélection suit le nouvel identifiant. |
| **Supprimer** | un bouton sur une ligne que vous avez ajoutée | Demande **Supprimer ce modèle ?** et retire cet identifiant. Un identifiant intégré ne peut pas être retiré. |

Tant que vous n'en avez pas ajouté, l'encadré dit **Aucun modèle personnel pour ce fournisseur pour le moment. Les identifiants intégrés restent dans la liste ci-dessus.**

Messages que vous pouvez voir ici :

- **Choisissez un fournisseur avant d'ajouter un modèle.**
- **Cet identifiant correspond déjà à un modèle intégré. Il reste dans la liste et ne peut pas être ajouté de nouveau.**
- **Cet identifiant de modèle n'est pas valide. Utilisez des lettres, des chiffres et . _ : / @ -, jusqu'à 100 caractères.**
- **Les modèles intégrés ne peuvent pas être modifiés.**
- **Cet identifiant correspond à un modèle intégré. Saisissez un autre identifiant.**
- **Ce modèle n'a pas pu être renommé. Utilisez un nouvel identifiant qui n'est pas déjà dans la liste.**
- **Les modèles intégrés ne peuvent pas être supprimés.**
- **Ce modèle n'a pas été ajouté par vous, il a donc été laissé en place.**

### 3.5 Génération en masse

**Génération en masse** met de nombreux produits en file. La ligne sous la barre dit que les filtres vides sont ignorés, que **Démarrer la génération** écrit une langue par requête et que cette page affiche une barre de 0 % à 100 %. L'adresse planifiée ne lit pas ces filtres.

**Produits actifs dans cette boutique** affiche le nombre de produits actifs avant tout filtre. Ce nombre est le catalogue de la boutique, pas une valeur fixe du module.

| Champ | Au départ | Ce que cela fait |
|---|---|---|
| **Catégories** | aucune cochée | Cochez chaque catégorie à inclure. Une sous-catégorie n'est pas incluse si vous ne la cochez pas aussi. Laissez l'arborescence vide pour ignorer les catégories. Un produit présent dans plusieurs catégories cochées n'est mis en file qu'une fois. |
| **Marques** | aucune sélectionnée | Maintenez Ctrl ou Cmd et cliquez sur une ou plusieurs marques. Seuls les produits de ces marques sont mis en file. Ne touchez pas à la liste pour ignorer la marque. Combiné aux catégories, le produit doit se trouver dans une catégorie cochée et appartenir à l'une de ces marques. |
| **Fournisseurs** | aucun sélectionné | Maintenez Ctrl ou Cmd et cliquez sur un ou plusieurs fournisseurs. Un produit correspond lorsque ce fournisseur est le fournisseur par défaut ou un fournisseur supplémentaire. Ne touchez pas à la liste pour ignorer le fournisseur. |
| **Ignorer les produits qui ont déjà une entrée IA** | Non | **Oui** exclut les produits qui ont déjà une entrée IA liée directement. Les entrées rédigées à la main ne comptent pas, donc ces produits restent dans la file. **Non** remet en file les produits correspondants. |
| **Ignorer les produits qui ont déjà une FAQ quelconque** | Non | **Oui** exclut les produits qui ont déjà une entrée quelconque liée directement, y compris celles rédigées à la main. **Non** n'applique que l'interrupteur IA ci-dessus. |
| **Seulement les produits en stock** | Non | **Oui** conserve les produits dont la quantité est supérieure à zéro, y compris une déclinaison en stock. **Non** ignore le stock. |
| **Seulement les produits avec une image de couverture** | Non | **Oui** exclut les produits sans image de couverture dans cette boutique. **Non** ignore les images. |
| **Seulement les produits avec une description** | Non | **Oui** conserve les produits dont la description courte ou complète est renseignée dans la langue par défaut de la boutique. **Non** ignore le texte. |
| **Prix de base à partir de** | vide | Prix catalogue hors taxes, avant les prix spécifiques. Laissez vide pour aucun minimum. Un produit en dessous de ce prix est exclu. |
| **Prix de base jusqu'à** | vide | Prix catalogue hors taxes, avant les prix spécifiques. Laissez vide pour aucun maximum. Un produit au-dessus de ce prix est exclu. |
| **Ajoutés depuis** | vide | Ne mettre en file que les produits créés à cette date ou après. Laissez vide pour ignorer la date de création. |
| **Nombre maximum de produits** | vide | S'arrête après ce nombre de produits, en commençant par le plus petit ID. 0 ou vide signifie aucune limite. Utilisez un petit nombre pour tester les filtres avant une exécution complète. |
| **Langues** | aucune sélectionnée | Maintenez Ctrl ou Cmd et cliquez sur les langues à rédiger. Chaque langue correspond à une requête par produit. Laissez la liste vide pour rédiger toutes les langues actives de cette boutique. Les noms sont les langues de cette boutique. |
| **Questions** | 5, le nombre de **IA** | Nombre de paires à rédiger pour chaque produit dans cette exécution. Remplace la valeur par défaut de l'onglet **IA** pour cette file uniquement. Utilisez le même nombre dans toutes les langues du produit. |
| **Entrées IA existantes du produit** | Ajouter | **Ajouter** conserve les entrées IA actuelles et en ajoute de nouvelles. **Remplacer les entrées IA non verrouillées liées uniquement au produit** supprime les entrées IA non verrouillées liées uniquement à ce produit, une fois par produit, puis écrit les nouvelles. Les entrées que vous avez modifiées à la main sont verrouillées et conservées. Les entrées également liées à une catégorie ou à une autre cible sont conservées. |
| **Envoyer au modèle** | voir les cartes | Choisissez les données produit que le modèle peut lire. Une carte désactivée n'est pas envoyée. Enregistrer une exécution stocke aussi ces cartes pour la fois suivante. |

Les titres des cartes sous **Envoyer au modèle** restent en anglais. La phrase sous chaque titre est l'aide de la carte.

| Carte | Au départ | Aide de la carte |
|---|---|---|
| **Name and reference** | activée | Titre et référence du produit. |
| **Short description** | activée | Le résumé affiché sous le titre. |
| **Full description** | activée | La description longue de la page produit. |
| **Price summary** | activée | Prix actuel et prix avant remise. |
| **Categories** | activée | Catégorie par défaut et autres catégories. |
| **Features** | activée | Noms des caractéristiques et leurs valeurs. |
| **Brand** | activée | Nom de la marque. |
| **Attributes and combinations** | désactivée | Attributs de chaque déclinaison. |
| **Tags** | désactivée | Étiquettes dans la langue en cours de rédaction. |
| **Supplier** | désactivée | Nom du fournisseur par défaut. |
| **Stock and availability** | désactivée | Quantité et libellé de disponibilité. |
| **Weight and dimensions** | désactivée | Poids, largeur, hauteur et profondeur. |
| **EAN, ISBN and condition** | désactivée | EAN, ISBN, UPC, MPN et état. |
| **Attachment titles** | désactivée | Titres des fichiers joints au produit. |
| **Existing questions (avoid duplicates)** | désactivée | Questions déjà publiées, pour que le modèle ne les répète pas. |

**Exécuter** a deux cartes.

**Démarrer dans ce navigateur.** **Démarrer la génération** met en file les produits qui correspondent aux champs ci-dessus, une ligne par langue. Cette page reste ouverte et affiche ici l'état, puis envoie chaque langue au modèle. Laissez l'onglet ouvert jusqu'à la fin de la barre. Fermer l'onglet arrête cette page. La file reste en place et l'adresse planifiée peut la terminer.

La barre commence à `Starting…` et 0 %. Pendant qu'elle court, la ligne est le nombre fait, une barre oblique et le total. À la fin elle lit `Finished.` plus ce compte. Une langue en échec ajoute `failed` et le dernier texte d'erreur du fournisseur. Quand rien ne correspond, la page affiche **Aucun produit ne correspond à cette sélection.** Quand la file ne peut pas être stockée, elle affiche **La file n'a pas pu être créée.** Quand l'exécution ne peut pas démarrer, la ligne d'état affiche `The run did not start.` Une réponse que la page ne peut pas lire affiche `That request could not be read.` Une étape en échec affiche `The generation request failed.` ou le texte d'erreur du fournisseur. Ces phrases de progression restent en anglais.

**Continuer sur le serveur.** Ce n'est pas un second bouton de démarrage. Il ne lit pas dans ce formulaire les catégories, le nombre de questions ni ajouter ou remplacer. Planifiez une URL toutes les quelques minutes. Chaque appel travaille environ 20 secondes puis s'arrête.

Copiez **Terminer une file existante** après **Démarrer la génération** si vous allez fermer l'onglet, ou lorsqu'une exécution s'est arrêtée avant la fin de la barre. Cela n'écrit que les lignes déjà mises en file.

Copiez **Compléter les produits qui n'ont pas encore d'entrée IA** lorsque vous voulez que les nouveaux produits soient complétés sans ouvrir cette page. Cette adresse ajoute chaque produit actif de cette boutique qui n'a pas d'entrée IA, en utilisant le nombre de questions et les choix de données enregistrés dans **IA**. Elle ajoute toujours, puis vide la file.

Gardez les deux adresses privées. Elles contiennent le secret qui autorise l'appel. **Enregistrer** sur ce formulaire n'est pas ce qui lance l'exécution. C'est **Démarrer la génération**.

Avant une exécution, la page refuse de démarrer et affiche l'un de ces messages :

- **Choisissez un fournisseur dans l'onglet IA avant de lancer une exécution.**
- **Choisissez un modèle dans l'onglet IA avant de lancer une exécution.**
- **Définissez l'URL de base compatible dans l'onglet IA avant de lancer une exécution.** Remplissez **URL de base compatible** sur la tuile compatible. Une adresse vide ne lance pas l'exécution.
- **Enregistrez une clé API pour le fournisseur sélectionné dans l'onglet IA avant de lancer une exécution.**

### 3.6 API

**API** sert à un système hors de la boutique. La ligne sous la barre dit que vous générez ici une clé, lui donnez un libellé et copiez l'URL de base. **Voir la liste complète** ouvre le catalogue des clés. **Historique des requêtes** liste chaque appel, avec les paramètres et la réponse. **Documentation de l'API** liste chaque action.

| Champ | Au départ | Ce que cela fait |
|---|---|---|
| **URL de base** | l'adresse de cette boutique | Adresse appelée par un système externe. Envoyez `action` et `api_key` comme paramètres de requête ou comme champs POST. L'en-tête `X-Api-Key` est aussi accepté. Ouvrez **Documentation de l'API** pour la liste des paramètres de chaque action. Une clé absente ou révoquée est refusée. |
| **Libellé de la clé** | vide | Un nom pour distinguer les clés, par exemple ERP ou staging. Ce n'est pas le secret. **Générer une clé** crée un nouveau secret et l'affiche dans le tableau. **Révoquer** arrête une clé et la laisse dans la liste. **Supprimer** retire la ligne et le secret. Les autres clés continuent de fonctionner. Vous pouvez créer plusieurs clés. |

**Générer une clé** ajoute la clé et revient sur cette page. L'aperçu **Clés déjà émises** liste les cinq clés les plus récentes. Le compte est le nombre total de clés. Le secret de cet aperçu est raccourci. **Voir la liste complète** montre le secret entier pour le copier dans l'autre système.

| Colonne | À quoi elle sert |
|---|---|
| **Libellé** | Le nom que vous avez saisi. |
| **Clé** | Le début du secret dans cet aperçu. Le secret complet est dans la liste des clés. |
| **Statut** | **Active** ou **Révoquée**. |
| **Créée** | Quand la clé a été générée. |
| **Dernière utilisation** | Le dernier appel accepté, ou **Pas encore utilisée**. |
| **Historique** | Ouvre **Historique des requêtes** filtré sur cette clé. |
| **Révoquer** | Demande **Révoquer cette clé ? Elle cesse de fonctionner immédiatement et reste dans cette liste.** Masqué lorsque la clé est déjà révoquée. |
| **Supprimer** | Demande **Supprimer cette clé ? La ligne et le secret sont supprimés. Les requêtes passées restent dans l'historique.** |

Quand il n'y a pas de clés, la page dit **Aucune clé pour le moment**.

**Documentation de l'API** ouvre une fenêtre. **Copier** copie l'URL de base puis affiche **OK**. Chaque action a **Copier l'URL** et **Copier cURL**. Remplacez `YOUR_API_KEY` de l'exemple par le secret de la liste des clés. La fenêtre liste aussi **Paramètre**, **Obligatoire** et **Description**. **Fermer** quitte la fenêtre.

| Action | Quoi envoyer | Ce que cela fait |
|---|---|---|
| `list` | `action=list`. Facultatif `id_product`, `resolved=1`, `page`, `id_shop`. | Renvoie des entrées. Avec `id_product`, seulement celles liées directement à ce produit. Avec `resolved=1`, l'ensemble que la page produit afficherait. Sans produit, `page` parcourt le catalogue, 50 entrées par page. |
| `get` | `action=get` et `id`. | Renvoie une entrée avec chaque traduction et chaque association. |
| `create` | `action=create`, plus une question et au moins un lien. Facultatif `id_product`, `id_lang`, `question`, `answer`, `translations`, `assoc`, `active`, `id_shop`. | Crée une entrée. `id_product` l'attache à ce produit. `translations` est un objet JSON dont la clé est l'id de langue. Les shortcodes tels que `[product_name]` sont stockés tels quels. `active` démarre activé. Une question ou un lien manquant est refusé. |
| `update` | `action=update` et `id`, plus seulement les champs que vous voulez changer. | Met à jour seulement les champs que vous envoyez. `replace_assoc=1` remplace les associations. Sinon `id_product` et `assoc` sont ajoutés. Cet appel ne verrouille pas l'entrée. |
| `activate` | `action=activate` et `id`. | Affiche de nouveau l'entrée sans changer le texte. |
| `deactivate` | `action=deactivate` et `id`. | Masque l'entrée. Elle reste dans le back-office et disparaît de la page produit. |
| `delete` | `action=delete` et `id`. | Supprime l'entrée, ses traductions et ses liens. |

`assoc` est une liste JSON d'objets avec `type` et `id`. Le type est `product`, `category`, `feature_value`, `attribute`, `tag`, `manufacturer` ou `supplier`. Le `id_shop` facultatif sélectionne la boutique. Sans lui, la boutique de l'URL appelée est utilisée. GET suffit pour un appel court. Envoyez les mêmes champs en POST lorsqu'une question ou une réponse est un long HTML.

**Historique des requêtes** est une liste en lecture seule. La note dit que chaque ligne correspond à un appel. Cherchez dans les champs sous les titres de colonnes. **Voir** ouvre les paramètres et la réponse. Le secret de l'appel stocké est masqué. Les lignes restent telles qu'elles ont été enregistrées. Vous ne pouvez pas ajouter, modifier ni supprimer une ligne. Si une écriture est tentée, la page affiche **L'historique des requêtes est un registre des appels. Ouvrez Voir pour lire une ligne.**

Colonnes : **ID**, **Date**, **Action**, **HTTP**, **ID de clé**, **Clé**, **Détails**, **IP**. **Clés API** dans la barre ouvre le catalogue des clés. **Retour au module** revient à **API**. Ouvrir l'historique depuis le module utilise un lien de réinitialisation, donc un filtre précédent est effacé. **Historique** sur une clé conserve le filtre de cette clé.

Le catalogue des clés s'intitule **Clés API**. La note dit que le secret est affiché pour que vous puissiez le copier dans l'autre système. **Révoquer** arrête cette clé et laisse la ligne. **Supprimer** retire la ligne et le secret. Les requêtes passées restent dans **Historique des requêtes**. **Générer une clé** revient à l'onglet **API**. Cette liste n'a pas de bouton **Nouveau**. Colonnes : **ID**, **Libellé**, **Clé**, **Statut**, **Créée**, **Dernière utilisation**. **Statut** indique **Active** ou **Révoquée**. **Dernière utilisation** indique **Pas encore utilisée** jusqu'au premier appel accepté. Les actions de ligne sont **Révoquer**, **Historique** et **Supprimer**. **Révoquer** est masqué sur une clé révoquée et demande **Révoquer cette clé ? Elle cesse de fonctionner immédiatement et reste dans cette liste.** **Supprimer** demande **Supprimer cette clé ? La ligne et le secret sont supprimés. Les requêtes passées restent dans l'historique.** Les actions groupées sont **Révoquer la sélection** et **Supprimer la sélection**, avec le même effet sur chaque ligne cochée. Si l'employé ne peut pas modifier, la page affiche **Vous n'avez pas l'autorisation de modifier ceci.**

### 3.7 Mises à jour

**Mises à jour** interroge MyPresta.eu pour une version plus récente. La vérification n'indique qu'une version. Installer le paquet reste un téléchargement manuel depuis la page du module. Le titre du formulaire est **Mises à jour MyPresta**.

| Champ | Au départ | Ce que cela fait |
|---|---|---|
| **Vérifier les mises à jour** | un bouton **Vérifier maintenant** | Vérifie à la main si une nouvelle version de ce module est disponible sur les serveurs de MyPresta.eu. **Nouvelle version disponible !** signifie qu'une version plus récente est listée. **Le module est à jour !** signifie que cette installation correspond à la version publiée. Le bouton ne téléverse pas de zip. |
| **Notifications de mises à jour** | Activer | **Activer** répète cette vérification environ tous les trois jours pendant que vous travaillez dans le back-office. **Désactiver** la saute. **Activer** et **Désactiver** sont les deux choix. |
| **Page du module** | un lien nommé **MyFAQ** | Lien direct vers la page officielle du module, où vous pouvez lire les changements. |

Cliquez sur **Enregistrer**. La page affiche **Paramètres de mise à jour enregistrés.**

Lorsqu'une version plus récente est connue, le back-office peut afficher **Une nouvelle version est disponible, consultez http://MyPresta.eu pour plus d'informations** et un lien **Plus de détails dans le journal des modifications**. Téléversez le nouveau zip depuis le **Gestionnaire de modules**.

### 3.8 Un produit

Ouvrez **Catalogue**, **Produits**, le produit, puis le bloc **MyFAQ**. Le titre est **FAQ sur ce produit**. Le texte dessous dit : choisissez où ce produit affiche ses questions, vérifiez ce qu'il hérite du catalogue et rédigez des entrées qui n'appartiennent qu'à ce produit. Si aucune entrée n'est active, ou si l'emplacement est **Masquer**, la boutique n'affiche aucun bloc MyFAQ sur ce produit.

Les onglets sont **Entrées FAQ**, **Question et réponse** et **Générer avec l'IA**.

**Entrées FAQ** commence par **Emplacement**.

| Champ | Au départ | Ce que cela fait |
|---|---|---|
| **Emplacement** | Utiliser la valeur par défaut de la boutique | **Utiliser la valeur par défaut de la boutique** suit **Affichage**. **Pied de page du produit** ou **Onglet produit** force cet endroit pour ce produit uniquement. **Masquer** retire MyFAQ de ce produit, y compris le bloc schema. Les autres modules du hook ne sont pas déplacés. Leur ordre reste dans **Design**, **Positions**. |

**Enregistrer** affiche **Enregistré.**

**FAQ sur ce produit** a deux listes. La première est en lecture seule et provient d'une catégorie, d'une caractéristique, d'un attribut, d'une étiquette, d'une marque ou d'un fournisseur. La seconde est enregistrée pour ce produit. Faites glisser une ligne pour changer l'ordre, utilisez l'interrupteur pour afficher ou masquer une question, et supprimez pour la retirer.

**Depuis le catalogue** liste les entrées affichées parce qu'un autre produit avec le même lien les afficherait aussi. Changez le texte dans le catalogue du module. Les colonnes sont **Question**, **Statut** et **Actions**. **Statut** est **Active** ou **Inactive**. **Modifier dans le catalogue** ouvre cette entrée. Une entrée IA peut afficher **IA** et **verrouillée**. Une entrée tapée affiche **Rédigée à la main**. Quand rien ne correspond, la carte dit **Rien d'hérité**.

**Ce produit uniquement** liste les questions liées à ce produit. Faites glisser la poignée (**Faites glisser pour réordonner**) pour définir leur ordre sur la page produit. L'interrupteur affiche **Active** ou **Inactive**. **Modifier** ouvre **Question et réponse**. **Supprimer** demande **Supprimer cette entrée ?** Quand la liste est vide, la carte dit **Aucune FAQ pour ce produit pour le moment** et propose **Ajouter une entrée**. **Aucune question dans cette langue** signifie que la langue actuelle du back-office n'a pas de texte de question ; une autre langue peut en avoir un.

**Question et réponse** est **Ajouter une entrée** ou **Modifier l'entrée**. La note dit que l'enregistrement ne concerne que ce produit. Les liens de catégorie, de caractéristique et les autres restent sur l'écran **Entrées**. La question est du texte brut dans la boutique. La réponse conserve la mise en forme de l'éditeur. Les shortcodes sont sous la réponse. Le bouton de langue à droite change la question et la réponse ensemble.

| Champ | Au départ | Ce que cela fait |
|---|---|---|
| **Question** | vide | Le même rôle que dans le catalogue. L'aide dit que la langue par défaut est obligatoire. Si toutes les langues sont vides, le bloc affiche **Saisissez une question dans au moins une langue.** |
| **Réponse** | vide | Le même rôle que dans le catalogue. Une langue vide n'est pas affichée dans cette langue. |
| **Shortcodes** | les boutons de jeton | Les mêmes jetons que dans le catalogue. Cliquez sur l'un d'eux pour l'insérer au curseur. |
| **Active** | Oui | **Oui** affiche l'entrée. **Non** la masque de la boutique. |

**Enregistrer** lie l'entrée seulement à ce produit. Modifier une ligne existante la verrouille, donc un remplacement ultérieur la conserve. Une ligne neuve n'est pas verrouillée. **Nouvelle entrée** vide le formulaire. **Supprimer l'entrée** la retire après **Supprimer cette entrée ?** Si vous ouvrez une entrée qui est aussi liée à autre chose, le bloc affiche **Cette entrée n'est pas exclusive au produit.** et n'enregistre pas par-dessus. Changez-la depuis **Modifier dans le catalogue**.

Si l'enregistrement n'atteint pas la boutique, le bloc affiche en anglais `The save could not reach the shop. Reload the product and try again.`

**Générer avec l'IA** rédige des questions pour ce produit à partir de ses données catalogue, dans toutes les langues de la boutique. L'exécution continue en arrière-plan. Une barre de progression apparaît ici après le démarrage.

| Champ | Au départ | Ce que cela fait |
|---|---|---|
| **Questions** | 5, le nombre de **IA** | Nombre de paires à rédiger pour ce produit, dans toutes les langues de la boutique. Remplace la valeur par défaut de l'onglet **IA** pour cette exécution uniquement. |
| **Entrées IA existantes du produit** | Ajouter | **Ajouter** conserve les entrées IA actuelles et en ajoute de nouvelles. **Remplacer les entrées IA non verrouillées liées uniquement au produit** supprime les entrées IA non verrouillées liées uniquement à ce produit, puis écrit les nouvelles. Les entrées que vous avez modifiées à la main sont verrouillées et conservées. |
| **Envoyer au modèle** | les mêmes cartes que **Génération en masse** | Les mêmes cartes. Une carte désactivée n'est pas envoyée. Cette exécution enregistre les cartes pour la fois suivante. |

**Générer** lance l'exécution. Les quatre mêmes messages que sur **Génération en masse** apparaissent lorsque le fournisseur, le modèle, l'adresse compatible ou la clé manque. La barre utilise les mêmes phrases anglaises : `Starting…`, puis les comptes, puis `Finished.` Laissez cette page produit ouverte jusqu'à la fin de la barre, ou terminez la file avec l'adresse de **Génération en masse**.

## 4. Boutique

Le client ne voit le bloc que sur une page produit.

Lorsque **Emplacement** est **Pied de page du produit**, l'accordéon est sous le produit. Le titre est **Titre au-dessus de la liste** dans la langue du client. Chaque question est un bouton. La réponse s'ouvre dessous. **Ouvrir la première question** sur **Oui** ouvre la première réponse au chargement. Sans JavaScript toutes les réponses sont visibles.

Lorsque **Emplacement** est **Onglet produit**, le thème ajoute un onglet produit. Le libellé de l'onglet est **Titre de l'onglet** de cette langue, ou FAQ lorsque cette langue est vide. Le contenu de l'onglet est le même accordéon et le même titre.

Les entrées liées directement au produit passent en premier. Ensuite, l'ordre est la position du catalogue et de **Faites glisser pour réordonner** sur le produit. Une question ou une réponse vide dans la langue du client est ignorée. Après le remplacement des jetons, une question qui reste vide, ou une réponse qui ne laisse plus de texte, est ignorée aussi. Les entrées inactives sont ignorées. **Masquer** sur ce produit n'imprime rien, y compris le bloc schema.

**Balisage schema FAQ** sur **Oui** est le schema FAQ que PrestaShop écrit dans le code de la page : un bloc FAQPage, construit à partir des questions que le client peut ouvrir, dans la langue de la page, et pointant vers l'URL du produit. Le client ne voit pas une boîte de schema séparée. **Non**, une liste vide ou **Masquer** n'impriment pas ce bloc.

Le client ne peut pas ajouter, modifier ni envoyer une question. Il n'y a pas de page de compte pour ces entrées.

Si le thème n'imprime pas le pied de produit et n'imprime pas d'onglets produit supplémentaires, le client ne voit rien même lorsque des entrées existent. Déplacez **MyFAQ** dans **Design**, **Positions**, sur `displayFooterProduct` ou `displayProductExtraContent`. Les autres modules de ce hook restent dans l'ordre que vous y fixez.

Un thème peut avoir deux positions de pied. L'accordéon n'est imprimé qu'une fois.

## 5. Problèmes

**La page produit n'a pas d'accordéon.** Le produit n'a pas d'entrée active dans la langue du client, la question ou la réponse est vide après le remplacement des jetons, ou **Emplacement** de ce produit est **Masquer**. Ouvrez le produit, mettez **Emplacement** sur **Utiliser la valeur par défaut de la boutique**, **Pied de page du produit** ou **Onglet produit**, et confirmez une entrée **Active**. Si le thème n'a ni pied ni onglets supplémentaires, déplacez le module dans **Design**, **Positions**.

**Une entrée liée à une catégorie parente ne s'affiche pas.** **Inclure les catégories parentes** est sur **Non**, ou le lien est Accueil. Mettez **Inclure les catégories parentes** sur **Oui**. Un lien vers Accueil ne couvre pas le catalogue. Cochez le parent que vous voulez vraiment, sous Accueil.

**La boutique affiche l'entrée dans une langue et pas dans une autre.** Cette langue a une question ou une réponse vide. Modifiez l'entrée et remplissez les deux. La page ignore une langue vide.

**Enregistrer affiche « Saisissez une question dans au moins une langue. »** Saisissez une question dans au moins une langue et cliquez de nouveau sur **Enregistrer**.

**Enregistrer affiche « Liez l'entrée à au moins un produit, une catégorie, une caractéristique, un attribut, une étiquette, une marque ou un fournisseur. »** Choisissez au moins un résultat dans **Produits**, **Catégories**, **Valeurs de caractéristiques**, **Valeurs d'attributs**, **Étiquettes**, **Marques** ou **Fournisseurs**.

**Le bloc produit affiche « Cette entrée n'est pas exclusive au produit. »** Cette question est aussi liée à une catégorie ou à une autre cible. Cliquez sur **Modifier dans le catalogue** et changez-la là.

**Le bloc produit affiche « The save could not reach the shop. Reload the product and try again. »** Rechargez le produit et enregistrez de nouveau. Cette phrase reste en anglais.

**Générer ne fait rien et affiche un message sur l'onglet IA.** Ouvrez **IA**, choisissez la tuile, enregistrez un modèle et enregistrez une clé pour un fournisseur officiel. Sur la tuile compatible, remplissez **URL de base compatible**, par exemple `http://localhost:11434/v1` pour Ollama. Relancez ensuite l'exécution.

**Démarrer la génération affiche « Aucun produit ne correspond à cette sélection. »** Retirez un filtre ou cochez une catégorie qui contient des produits actifs. Les filtres vides sont ignorés, donc un filtre que vous avez défini est ce qui a retiré les produits.

**La barre s'arrête avant 100 %.** Laissez l'onglet ouvert, ou copiez **Terminer une file existante** et ouvrez-la selon un planning. Fermer l'onglet ne supprime pas la file. Une ligne avec `failed` et un message du fournisseur signifie que cette langue a été refusée. Lisez le message, corrigez la clé ou l'identifiant du modèle, et relancez. **Ajouter** ajoute un autre ensemble. **Remplacer les entrées IA non verrouillées liées uniquement au produit** retire d'abord l'ensemble IA non verrouillé.

**La ligne de progression affiche `curl_missing`.** Le serveur n'a pas cURL. Demandez à l'hébergeur de l'activer. La génération ne tourne pas sans lui.

**Un avis de nouvelle version apparaît.** Le texte est **Une nouvelle version est disponible, consultez http://MyPresta.eu pour plus d'informations**. Ouvrez **Mises à jour** et cliquez sur **Vérifier maintenant**. Téléchargez le zip depuis la page du module et téléversez-le dans le **Gestionnaire de modules**. **Désactiver** sous **Notifications de mises à jour** arrête l'avis automatique.

**MyFAQ n'est pas dans le menu de gauche.** C'est attendu. Ouvrez **Modules**, **Gestionnaire de modules**, **MyFAQ**, **Configurer**. Le catalogue, les clés et l'historique s'ouvrent depuis cette page. Si **Configurer** ne peut pas ouvrir le catalogue, ouvrez **Configurer** une fois pendant que vous êtes connecté en tant qu'employé autorisé à installer des modules. Cette visite crée les pages cachées et donne l'accès au profil actuel.

**Une clé est refusée.** La clé a été révoquée, supprimée, ou copiée sans le secret complet. Ouvrez **Clés API**, copiez la **Clé** complète d'une ligne **Active**, ou cliquez sur **Générer une clé**.

**Vous ne pouvez pas supprimer une ligne de l'historique des requêtes.** La page affiche **L'historique des requêtes est un registre des appels. Ouvrez Voir pour lire une ligne.** Utilisez **Voir**.

**Vous n'avez pas l'autorisation de modifier ceci.** Le profil de l'employé ne peut pas modifier la liste des clés. Ouvrez **Configurer** en tant qu'administrateur, ou donnez au profil l'accès aux pages du module.

**La première réponse est fermée alors que Ouvrir la première question est sur Oui.** Le client a JavaScript désactivé. Dans ce cas toutes les réponses sont visibles. Avec JavaScript activé, seul le premier élément démarre ouvert.

**La même question apparaît deux fois.** Elle n'est liée deux fois que si vous avez enregistré deux entrées. Une entrée n'est affichée qu'une fois. Vérifiez **Ce produit uniquement** et **Depuis le catalogue** pour deux lignes différentes avec le même texte.

**Remplacer a laissé une ancienne question IA.** Cette entrée est verrouillée, ou elle est aussi liée à une catégorie ou à une autre cible. Verrouillée est la marque de la ligne. Modifiez-la et supprimez-la si vous voulez qu'elle disparaisse.

## 6. Pour le développeur

### 6.1 Aperçu

Classe principale `myfaq` dans `myfaq.php`. Version `1.3.1`. Libellé de la liste **MyFAQ**. Auteur `mypresta.eu`. Onglet `front_office_features`. `ps_versions_compliancy` va de `1.7.0.0` à `9.99.99`. `need_instance` vaut 0. `bootstrap` vaut true. `config.xml` indique encore la version `1.0.0` ; la version de la classe est celle que la boutique exécute.

`getContent()` rend `MyfaqAdminBo`. Les réglages d'affichage sont des clés `Configuration`. Les entrées, les liens, l'emplacement par produit, les clés API, le journal des requêtes et la file IA sont des tables. La vitrine lit les correspondances par `MyfaqMatcher`, remplace les jetons par `MyfaqShortcode` et imprime éventuellement `MyfaqSchema`. Les appels IA sortent par `MyfaqAi` et `MyfaqQueue`. L'adresse publique est le contrôleur front `api`.

Il n'y a ni `enable()` ni `disable()`.

### 6.2 Fichiers

- `myfaq.php` — installation, désinstallation, hooks, valeurs de départ, entrées ajax.
- `config.xml` — métadonnées du paquet. La version y est `1.0.0`.
- `lib/MyfaqAdminBo.php` — formulaires du back-office, textes `desc`, panneau produit.
- `lib/MyfaqConfig.php` — fournisseurs, modèles, drapeaux, chiffrement, jeton cron.
- `lib/MyfaqRepository.php` — tables et CRUD.
- `lib/MyfaqMatcher.php` — quelles entrées un produit affiche.
- `lib/MyfaqShortcode.php` — catalogue des jetons et remplacement.
- `lib/MyfaqSchema.php` — publie le JSON-LD FAQ sur la page produit.
- `lib/MyfaqAi.php` — appels HTTP vers les fournisseurs. Exige cURL.
- `lib/MyfaqQueue.php` — lot et file.
- `lib/MyfaqApi.php` — API publique.
- `lib/MyfaqApiDocumentation.php` — texte de la fenêtre.
- `lib/updatesChecker.php` — classe `myfaqUpdate`.
- `lib/prestashop9compatibility.php` — gabarits d'aide, prix, listes d'id.
- `lib/searchTool/searchTool.php` — autocomplétion des champs d'association.
- `controllers/admin/AdminMyfaqController.php` — ajax seulement : recherche, panneau produit, démarrage de masse, pas de masse, réordonnancement.
- `controllers/admin/AdminMyfaqEntriesController.php` — catalogue.
- `controllers/admin/AdminMyfaqKeysController.php` — clés.
- `controllers/admin/AdminMyfaqLogsController.php` — historique.
- `controllers/front/api.php` — API JSON publique.
- `controllers/front/cron.php` — travailleur de la file.
- `views/templates/admin/tabs.tpl` — barre de sections.
- `views/templates/admin/entries.tpl` — aperçu des dix dernières.
- `views/templates/admin/product.tpl` — bloc d'édition produit.
- `views/templates/admin/api.tpl` — aperçu des clés.
- `views/templates/admin/_shortcodes.tpl` — boutons de jeton.
- `views/templates/admin/_api_documentation_modal.tpl` — fenêtre des actions.
- `views/templates/admin/_api_log_modal.tpl` — un appel stocké.
- `views/templates/hook/product.tpl` — accordéon de la vitrine.
- `views/css/myfaq.css`, `views/js/myfaq.js` — vitrine.
- `views/css/myfaq-admin.css`, `views/css/myfaq-controls.css`, `views/js/admin.js` — back-office. Plusieurs phrases de progression dans `admin.js` sont fixées en anglais.
- `upgrade/upgrade-1.0.0.php` — appelle `installDb()`.
- `key.php` — facultatif. S'il est présent, la vérification de mise à jour envoie sa valeur de licence. S'il est absent, la vérification envoie `nlc`.

### 6.3 Contrôleurs

`AdminMyfaq`, `AdminMyfaqEntries`, `AdminMyfaqKeys` et `AdminMyfaqLogs` sont des onglets avec `id_parent` `-1`. Ils n'apparaissent pas dans le menu. `ensureSearchTab()` crée un onglet manquant. `grantHiddenTabAccess()` accorde voir, ajouter, modifier et supprimer au profil super-administrateur et au profil de l'employé actuel.

`AdminMyfaq` ne sert que l'ajax : `SearchTool`, `ProductPanel`, `BulkStart`, `BulkStep`, `Reorder`. Les mêmes actions existent sur l'objet du module parce que le panneau produit et la page de masse y postent.

`AdminMyfaqEntries` est le catalogue. **Nouvelle entrée** de la barre est `addmyfaq_item`. Enregistrer envoie `submitMyfaqItem` et redirige avec `conf=4`. La position utilise les liens de position du helper.

`AdminMyfaqKeys` n'a pas de formulaire d'ajout. **Générer une clé** renvoie vers `configure=myfaq&mfq_tab=api`. `processRevoke` et la révocation groupée appellent `MyfaqRepository::revokeApiKey`. Supprimer appelle `deleteApiKey`.

`AdminMyfaqLogs` refuse l'ajout, la mise à jour et la suppression avec **L'historique des requêtes est un registre des appels. Ouvrez Voir pour lire une ligne.** `action=View` renvoie la requête et la réponse stockées en JSON pour la fenêtre. `id_api_key` dans la requête préremplit le filtre de clé sauf si la liste est réinitialisée.

Le contrôleur front `api` (`module/myfaq/api`) appelle `MyfaqApi::handle()` et renvoie du JSON. Il pose le statut HTTP à partir du résultat. Le contrôleur front `cron` (`module/myfaq/cron`) exige `token` égal à `MYFAQ_CRON_TOKEN`. Un mauvais jeton renvoie `403` et `{"error":"forbidden"}`. `fill_missing=1` appelle `MyfaqQueue::enqueueMissing` pour la boutique actuelle, puis l'action vide les lignes en attente pendant environ 20 secondes, au plus 30 lignes. Le JSON est `ok`, `enqueued_batch`, `processed`, `finished`.

Résultats de l'API : clé absente ou révoquée `401` `unauthorized`. `action` inconnue `400` `unknown_action`. Id absent ou inconnu `400` `missing_id` ou `not_found`. Création sans question `422` `question_required`. Création sans lien `422` `association_required`. Création réussie `201`. Mise à jour, activation, désactivation et suppression réussies `200`. Une écriture en échec `500`.

`list` avec `id_product` et `resolved=1` utilise `MyfaqMatcher::forProductAllLangs`. `list` avec `id_product` et sans `resolved` renvoie les entrées liées directement à ce produit. `list` sans produit pagine `MyfaqRepository::listItems` à 50 par page. La mise à jour utilise `lock_on_update` false, donc une mise à jour par API ne verrouille pas la ligne.

### 6.4 Hooks

Enregistrés dans `install()` :

| Hook | Rôle |
|---|---|
| `displayHeader` | Sur un contrôleur produit, ajoute `views/css/myfaq.css` et `views/js/myfaq.js`. |
| `displayFooterProduct` | Rend l'accordéon lorsque l'emplacement résolu est `footer`. |
| `displayProductFooter` | Le même rendu. Un drapeau statique n'imprime le bloc de pied qu'une fois par requête. |
| `displayProductExtraContent` | Lorsque l'emplacement est `tab`, renvoie un `ProductExtraContent`. Le titre est `MYFAQ_TAB_TITLE` de la langue actuelle, ou la chaîne source FAQ lorsque cette valeur est vide. |
| `displayAdminProductsExtra` | Bloc d'édition produit plus CSS et JS. |
| `actionAdminControllerSetMedia` | CSS et JS d'administration sur la page produit, sur `configure=myfaq` et sur les contrôleurs d'entrées, de clés et d'historique. |

Le module n'enregistre pas de hooks propres et n'appelle pas `Hook::exec` pour un hook personnalisé. `displayProductExtraContent` renvoie un tableau vide lorsque l'emplacement n'est pas `tab`, lorsque le HTML est vide ou lorsque `ProductExtraContent` n'existe pas.

### 6.5 Surcharges

Le module ne surcharge aucune classe ni aucun contrôleur de PrestaShop.

### 6.6 Base

`MyfaqRepository::installDb()` crée les tables avec `_MYSQL_ENGINE_` et `utf8mb4`, et réessaie avec `utf8` si cela échoue. `uninstall()` les supprime dans cet ordre : `myfaq_queue`, `myfaq_batch`, `myfaq_api_log`, `myfaq_api_key`, `myfaq_product_display`, `myfaq_assoc`, `myfaq_item_lang`, `myfaq_item`. La désinstallation supprime bien les tables. Une réinstallation ne restaure pas les lignes.

| Table | Contenu |
|---|---|
| `myfaq_item` | `id_item`, `id_shop` (`0` signifie toutes les boutiques), `active`, `position`, `source` (`manual` ou `ai`), `locked`, `date_add`, `date_upd`. |
| `myfaq_item_lang` | `id_item`, `id_lang`, `question`, `answer`. |
| `myfaq_assoc` | `id_assoc`, `id_item`, `type`, `id_target`. Unique sur entrée, type et cible. Types : `product`, `category`, `feature_value`, `attribute`, `tag`, `manufacturer`, `supplier`. |
| `myfaq_product_display` | `id_product`, `id_shop`, `mode` (`inherit`, `footer`, `tab`, `hidden`). |
| `myfaq_api_key` | `id_api_key`, `api_key`, `label`, `active`, `date_add`, `last_used`. |
| `myfaq_api_log` | `id_log`, `id_api_key`, `label`, `action`, `http_code`, `ip`, `request`, `response`, `date_add`. La clé stockée est masquée. |
| `myfaq_batch` | `id_batch`, `id_shop`, `id_employee`, `status` (`pending`, `running`, `done`), `total`, `done`, `failed`, `options`, `date_add`, `date_upd`. |
| `myfaq_queue` | `id_queue`, `id_batch`, `id_shop`, `id_product`, `id_lang`, `status` (`pending`, `running`, `done`, `error`), `attempts`, `error`, `date_upd`. Une ligne `running` de plus de cinq minutes revient à `pending`. |

`ensureApiSchema()` s'exécute à l'ouverture de l'onglet API, de la liste des clés, de l'historique ou d'un appel public à l'API. Il ajoute `last_used` lorsque cette colonne manque et crée `myfaq_api_log` lorsque cette table manque.

L'enregistrement du catalogue pose `lock_on_update`, donc une mise à jour met `locked` à 1. `source` lors d'une mise à jour reste la valeur actuelle sauf si `force_source` est posé. Une ligne neuve du catalogue est `manual` et non verrouillée. Une mise à jour depuis la page produit verrouille aussi. Une insertion depuis la page produit ne lie que ce produit et ne verrouille pas. Le remplacement IA supprime les lignes dont `source` est `ai`, `locked` vaut 0 et qui n'ont pas d'association autre que ce produit.

`MyfaqMatcher::categoryIds()` ajoute les parents seulement lorsque `MYFAQ_INCLUDE_PARENT_CAT` vaut 1. Le parcours s'arrête lorsque `id_parent` est inférieur ou égal à 2, ou après 25 pas.

### 6.7 Clés et traductions

Installées par `installConfig()`. Retirées par `deleteConfig()` à la désinstallation.

| Clé | Quand elle manque ou à l'installation |
|---|---|
| `MYFAQ_DISPLAY` | `footer` |
| `MYFAQ_TAB_TITLE` | `FAQ` par langue |
| `MYFAQ_HEADING` | `FAQ` par langue |
| `MYFAQ_INCLUDE_PARENT_CAT` | `0` |
| `MYFAQ_SCHEMA` | `1` |
| `MYFAQ_OPEN_FIRST` | `0` |
| `MYFAQ_AI_PROVIDER` | `openai` |
| `MYFAQ_AI_MODEL_OPENAI` | `gpt-4o-mini` |
| `MYFAQ_AI_MODEL_ANTHROPIC`, `MYFAQ_AI_MODEL_GEMINI`, `MYFAQ_AI_MODEL_DEEPSEEK`, `MYFAQ_AI_MODEL_MISTRAL`, `MYFAQ_AI_MODEL_COMPATIBLE` | vides jusqu'à ce qu'un modèle soit enregistré. `MyfaqConfig::model()` renvoie alors le premier id intégré, ou une chaîne vide pour `compatible` |
| `MYFAQ_AI_KEY_` plus le fournisseur en majuscules | vide. Stockée avec `MyfaqConfig::encrypt` (`enc:` et AES-256-CBC, clé `sha256` de `_COOKIE_KEY_`) |
| `MYFAQ_AI_BASE_URL` | vide. `baseUrl('compatible')` utilise alors `http://localhost:11434/v1`. `aiBlockReason()` refuse une exécution tant que cette valeur est vide, donc les boutons du back-office n'atteignent pas ce repli |
| `MYFAQ_AI_TEMPERATURE` | `0.4`. La lecture borne de 0 à 2 |
| `MYFAQ_AI_MAX_TOKENS` | `2000`. La lecture utilise 2000 lorsque la valeur stockée est sous 200, et plafonne à 8000 |
| `MYFAQ_AI_COUNT` | `5`. La lecture utilise 5 lorsque la valeur stockée est sous 1, et plafonne à 20 |
| `MYFAQ_AI_PROMPT` | vide |
| `MYFAQ_AI_CONTEXT` | JSON de `MyfaqConfig::defaultFlags()`. Activés : `name`, `description_short`, `description`, `prices`, `categories`, `features`, `manufacturer`. Désactivés : `combinations`, `tags`, `supplier`, `stock`, `dimensions`, `identifiers`, `attachments`, `existing` |
| `MYFAQ_CUSTOM_MODELS` | `{}` |
| `MYFAQ_CRON_TOKEN` | `bin2hex(random_bytes(16))`. `ensureCronToken()` en crée un lorsque la valeur est vide |
| `MYFAQ_BO_TAB` | non posée à l'installation. La section ouverte est stockée à chaque rendu. Les valeurs inconnues reviennent à `display` |

`deleteConfig()` supprime aussi chaque `MYFAQ_AI_KEY_*` et `MYFAQ_AI_MODEL_*` pour `openai`, `anthropic`, `gemini`, `deepseek`, `mistral`, `compatible`.

La désinstallation ne supprime pas `mypresta_updates`, `update_myfaq` ni `updatev_myfaq`. Ils appartiennent à la vérification des mises à jour. `mypresta_updates` est activé lorsque la clé manque. L'intervalle de la vérification automatique est de 259200 secondes.

Les descriptions de champs sont dans `MyfaqAdminBo` (`desc` et les textes `sectionBrief`) et dans `MyfaqApiDocumentation`. Les chaînes du back-office passent par `$this->l()`. Ajoutez une langue avec le fichier `translations/{iso}.php`. Chaînes qui ne passent pas par `$this->l()` : les aides de shortcode dans `MyfaqShortcode::catalogue()`, les noms des tuiles de fournisseur, les titres des cartes de données dans `MyfaqConfig::contextFlagDefs()` (ils passent par `$this->l()`, mais il n'y a pas de traduction, donc ils s'affichent en anglais) et les phrases de progression fixées dans `views/js/admin.js`. Les aides des cartes sont traduites. Les libellés d'état de `conditionLabel()` sont `New`, `Used` et `Refurbished`.

`MyfaqConfig::shopScope()` renvoie `0` lorsque le contexte multiboutique est toutes les boutiques, et l'id de la boutique actuelle sinon. Les enregistrements du catalogue utilisent cette valeur. Les enregistrements de la page produit utilisent seulement l'id de la boutique actuelle.

### 6.8 Étendre

Surchargez `views/templates/hook/product.tpl` depuis le thème dans `themes/{theme}/modules/myfaq/views/templates/hook/product.tpl`. Les variables assignées sont `mfq_items` (`id`, `question`, `answer`), `mfq_heading`, `mfq_open_first` et `mfq_schema`. Surchargez `views/css/myfaq.css` et `views/js/myfaq.js` de la même façon. L'accordéon n'est pas rendu lorsque l'appariement ne renvoie aucune ligne visible, donc une surcharge de thème n'a alors rien à imprimer. N'éditez pas les gabarits du module sur place si le thème peut porter la surcharge.

## 7. Aide

Page du module : [https://mypresta.eu/contact.html](https://mypresta.eu/contact.html)

Pour écrire au sujet de ce module, connectez-vous au compte client sur [mypresta.eu](https://mypresta.eu), ouvrez le contact et choisissez le sujet **Support for paid modules**. Le formulaire indique que la connexion est exigée pour ce sujet. Une fois connecté, choisissez ce module dans l'historique des achats.
