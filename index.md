# Politique de confidentialité

_Dernière mise à jour : 13 septembre 2026._

MediaLibre est une application indépendante, éditée par un particulier. Elle n'est
affiliée à aucun site, à aucune plateforme de contenu et à aucun éditeur : elle affiche
les pages Web que vous ouvrez et enregistre, à votre demande, les fichiers que ces pages
publient en accès libre.

À l'installation, l'application fonctionne **sans compte**. Rien de ce que vous y faites
ne quitte votre appareil, en dehors des requêtes qu'un navigateur adresse normalement aux
sites que vous consultez.

Un compte est proposé, mais il reste **facultatif**. Naviguer, télécharger, lire,
organiser sa bibliothèque et régler l'application ne demandent jamais de se connecter.
Cette politique décrit ce qui reste sur l'appareil, ce qui en sort, et vers qui.

Elle est établie par lecture du code, non par déclaration d'intention. Une donnée absente
de ce document est une donnée que l'application ne détient pas.

## 1. Responsable du traitement

L'éditeur de l'application est responsable des traitements décrits ici.

Contact : **serge.simono27@gmail.com**

Aucune donnée n'est vendue, louée, ni cédée à un tiers à des fins commerciales.

## 2. Ce que fait l'application

MediaLibre est un navigateur Web doublé d'un gestionnaire de téléchargements et d'une
bibliothèque multimédia locale. Elle n'héberge aucun contenu et n'en distribue aucun.
Elle ne contourne aucune protection technique, ne franchit ni authentification ni
restriction de compte, et n'extrait ni cookie, ni jeton, ni identifiant des sites
visités.

## 3. Données stockées sur l'appareil

| Donnée | Finalité | Durée |
|---|---|---|
| Fichiers vidéo, audio et images téléchargés | Vous appartiennent | **Jamais supprimés automatiquement** |
| Bibliothèque : chemins, URI, métadonnées techniques | Retrouver et lire vos fichiers | Jusqu'à suppression par vous |
| Favoris, collections et collections intelligentes | Organiser la bibliothèque | Jusqu'à suppression par vous |
| Positions de lecture et repères | Reprendre là où vous en étiez | Jusqu'à suppression par vous |
| File de téléchargement et transferts terminés | Suivre et reprendre un transfert | Jusqu'à suppression par vous |
| Corbeille | Revenir sur une suppression | Jusqu'à vidage |
| Onglets, favoris Web et historique de navigation | Retrouver une page | Jusqu'à effacement par vous |
| Cookies, stockage local et sessions des sites | Tenus par le composant WebView d'Android | Jusqu'à effacement par vous |
| Vignettes et caches d'affichage | Accélérer l'affichage | Reconstruits depuis le fichier |
| Réglages, dossier de téléchargement, autorisations d'accès aux dossiers | Préférences de fonctionnement | Jusqu'à réinitialisation |
| Identifiant d'installation et jeton d'authentification | Distinguer vos appareils, tenir la session | Jusqu'à déconnexion ou désinstallation |
| Journal d'activité de synchronisation | Rendre compte de ce qui a été synchronisé | 50 dernières opérations, effaçable |

Ces données sont enregistrées dans l'espace privé de l'application. Le jeton
d'authentification et l'identifiant d'installation sont chiffrés (clé du Keystore
Android) et **exclus des sauvegardes système**.

Le journal d'activité de synchronisation ne consigne qu'une catégorie, un décompte, une
issue et une durée : **jamais un titre de média, jamais une adresse**. Il n'est envoyé
nulle part.

**Navigation privée.** Les onglets et les visites d'une fenêtre privée ne sont jamais
écrits sur le disque. La garantie ne vient pas d'un filtre appliqué après coup, mais
d'une absence d'écriture.

## 4. Compte utilisateur (facultatif)

Deux moyens de connexion sont proposés, tous deux traités par le service Firebase
Authentication de notre sous-traitant Google : **une adresse e-mail avec un mot de
passe**, ou **un compte Google** (via le gestionnaire d'identifiants d'Android). Les deux
peuvent être associés au même compte. L'application ne propose pas de compte anonyme.

| Donnée | Origine | Finalité |
|---|---|---|
| Adresse e-mail | Vous, ou votre compte Google | Identifier le compte, envoyer un lien de vérification ou de réinitialisation |
| Nom et adresse de la photo de profil | Votre compte Google, ou vous | Afficher le compte connecté |
| Identifiant de compte (UID) | Firebase | Rattacher vos données synchronisées |
| Nom applicatif de l'appareil, modèle commercial, version de MediaLibre, dates | L'appareil | Lister et révoquer vos appareils |

**Le mot de passe n'est détenu ni conservé par MediaLibre**, pas même sous forme de
condensat : il traverse l'application jusqu'au SDK Firebase et s'arrête là. Ni base
locale, ni réglage, ni journal, ni sauvegarde.

**Aucun identifiant matériel n'est lu** : ni IMEI, ni adresse MAC, ni Android ID, ni
identifiant publicitaire. Le modèle commercial de l'appareil sert uniquement à ce que
vous reconnaissiez vos propres appareils dans la liste.

Une attestation d'intégrité est demandée à **Google Play Integrity**, via Firebase App
Check, avant d'autoriser une synchronisation. Elle répond à « la requête vient-elle d'une
installation légitime », jamais à « qui est l'utilisateur » : elle ne contient aucune
donnée applicative ni identifiant de compte.

## 5. Synchronisation (facultative, et catégorie par catégorie)

Sans compte, rien ne part. Avec un compte, seules les catégories que vous laissez actives
sont envoyées vers **Cloud Firestore**, hébergé en Europe (`europe-west1`). Chaque
catégorie se coupe séparément, et la synchronisation entière se coupe d'un seul réglage.

| Catégorie | Par défaut | Ce qui part réellement |
|---|---|---|
| Favoris | **Activé** | Clé de contenu, titre, durée, taille, **domaine seul** de la source, date |
| Collections | **Activé** | Titre, description, dates d'ajout et de retrait par média |
| Progression de lecture | **Activé** | Position, durée, instant |
| Réglages | **Activé** | Une liste blanche de préférences — ni chemins d'accès, ni réglages liés au matériel |
| Favoris Web | **Activé** | Adresse assainie, titre, dossier. Pas la favicone |
| Historique Web | **Désactivé** | Adresse assainie, titre, date. Une entrée par adresse, 1 000 au maximum |
| Onglets ouverts | **Désactivé** | Titre, adresse assainie, appareil, date. **Jamais l'état de la WebView** |

**Ce qui n'est jamais synchronisé**, même compte ouvert : les fichiers média eux-mêmes,
les chemins et URI de votre appareil, les téléchargements, la corbeille, les
autorisations d'accès aux dossiers, les cookies et sessions des sites, les onglets et
visites privés.

**Toute adresse est assainie avant de partir.** Une adresse signée (S3, CloudFront, GCS)
ou portant un identifiant dans son autorité n'est pas synchronisée du tout ; une adresse
ordinaire est nettoyée de ses paramètres susceptibles de porter un secret.

> Vos fichiers média ne sont jamais téléversés. Aucune fonction de l'application ne les
> envoie ailleurs.

## 6. Navigation Web

Un navigateur envoie aux sites que vous ouvrez les requêtes nécessaires à leur
affichage : l'adresse demandée, l'en-tête `User-Agent`, et un en-tête `Referer` réduit à
la seule origine lorsque la requête change de site. Ces sites peuvent donc vous observer
comme le ferait n'importe quel navigateur.

**MediaLibre n'ajoute rien à ces requêtes et n'en adresse de copie à personne.**

Les cookies, le stockage local et les sessions sont tenus par le composant WebView du
système Android. L'application ne les lit pas, ne les synchronise pas et ne les place
dans aucune sauvegarde. Vous pouvez les effacer à tout moment depuis les réglages ou
depuis les informations d'un site.

## 7. Caméra, microphone et localisation

Ces trois capteurs ne sont **jamais utilisés par MediaLibre pour son propre compte**.

| Capteur | Quand | Ce qui se passe |
|---|---|---|
| Microphone | Vous touchez le microphone de la barre de recherche | La reconnaissance vocale du système transcrit votre requête. Aucun enregistrement n'est conservé |
| Caméra | Un site la demande, ou vous ouvrez le lecteur de code | Le flux ne transite par aucun code applicatif. Aucune image n'est conservée |
| Localisation approchée | Un site la demande | Relayée à ce site seulement. La position fine n'est jamais demandée |

Pour la caméra et la localisation réclamées par une page, **deux accords distincts** sont
nécessaires, dans cet ordre : vous répondez d'abord « Autoriser » dans la boîte du
navigateur, puis Android vous pose sa propre question. Aucun refus n'est mémorisé pour
vous : un site qui redemande repose la question.

## 8. Diffusion sur un autre appareil

La diffusion repose sur **Google Cast**. Rien n'est diffusé avant que vous ne choisissiez
une destination. Une fois choisie, l'adresse du média et les informations nécessaires à
sa lecture sont transmises à cet appareil et aux services Google Cast qui établissent la
liaison.

Un récepteur va chercher le média lui-même : il ne peut donc pas ouvrir un fichier stocké
sur votre téléphone. Pour diffuser un fichier de votre bibliothèque, MediaLibre le rend
joignable **sur votre réseau local uniquement**, et rien de plus :

| Propriété | Garantie |
|---|---|
| Portée | Le seul média diffusé, plus la piste de sous-titres jointe. Aucun dossier n'est exposé |
| Adresse | Un jeton aléatoire de 24 octets, tiré au hasard pour la séance |
| Durée | Le temps de la séance ; l'adresse cesse de fonctionner avec elle |
| Réseau | Adresse locale uniquement, jamais d'exposition hors de votre réseau |
| Refus | La fonction se coupe dans Réglages → Lecteur → Diffusion |

> Le fichier ne quitte jamais votre réseau : il n'est envoyé à aucun service, ni à Google,
> ni à nous.

## 9. Destinataires

| Destinataire | Ce qu'il reçoit | Base |
|---|---|---|
| **Google Identity** (gestionnaire d'identifiants) | L'application reçoit un jeton d'identité ; aucune donnée applicative ne part par ce canal | Consentement, à l'ouverture de session |
| **Firebase Authentication** | Selon la méthode : le jeton d'identité Google, ou l'adresse e-mail et le mot de passe saisis | Consentement |
| **Firebase Authentication — courrier sortant** | L'adresse du compte, pour un lien de vérification ou de réinitialisation | Consentement, à la demande |
| **Google Play Integrity** (via Firebase App Check) | Une attestation d'intégrité de l'installation, sans donnée applicative ni identifiant | Nécessaire au service de synchronisation |
| **Cloud Firestore** (`europe-west1`) | Les seules catégories que vous avez laissées actives, section 5 | Consentement, révocable |
| **Sites que vous visitez** | Ce qu'un navigateur envoie : requête, `User-Agent`, `Referer` réduit à l'origine | Usage du navigateur |
| **Appareil de diffusion choisi** | L'adresse du média et ses métadonnées ; pour un fichier local, le fichier lui-même, sur votre réseau seulement | Geste explicite, le temps d'une séance |
| **Services Google Cast** | Découverte des appareils et établissement de la liaison ; le fichier local ne transite pas par eux | Consentement, à l'ouverture d'une séance |

Google agit en sous-traitant pour Firebase Authentication et Cloud Firestore.

## 10. Transferts hors de l'Union européenne

Les données synchronisées sont hébergées dans l'Union européenne (`europe-west1`).
Certains traitements de Google (authentification, attestation d'intégrité, services Cast)
peuvent impliquer des transferts hors de l'Union, encadrés par les clauses
contractuelles types de la Commission européenne.

## 11. Publicité, mesure d'audience et journalisation

L'application n'intègre **aucune régie publicitaire, aucun traqueur, aucun outil de
mesure d'audience et aucun rapporteur de plantage**. Aucun profil publicitaire n'est
constitué et l'identifiant publicitaire Android n'est pas lu. Aucune adresse e-mail ni
aucun identifiant de compte n'est transmis à un service de mesure, puisqu'il n'y en a
aucun.

Les journaux techniques ne sont produits qu'en version de développement. Ils ne
contiennent ni cookie, ni en-tête d'autorisation, ni paramètre d'adresse susceptible de
porter un jeton.

## 12. Achats

L'application ne propose aucun achat. Aucune donnée de paiement n'est traitée, ni par
l'application, ni pour son compte.

## 13. Vos droits

Vous disposez des droits d'accès, de rectification, d'effacement, de portabilité, de
limitation et d'opposition prévus par le RGPD.

- **Compte → Exporter mes données** produit un fichier lisible, éventuellement chiffré
  par un mot de passe de votre choix. Il ne contient ni jeton, ni cookie, ni mot de
  passe, ni fichier média.
- **Compte → Supprimer mon compte** efface vos données synchronisées, la liste de vos
  appareils **et le compte d'authentification lui-même**.
- **Réglages → Confidentialité** efface l'historique Web local, les cookies et les
  données de site.
- **Compte → Synchronisation** coupe la synchronisation, en bloc ou catégorie par
  catégorie, et efface le journal d'activité.
- La désinstallation supprime toutes les données internes de l'application. Les fichiers
  que vous avez téléchargés dans un dossier public, eux, subsistent : ils vous
  appartiennent.

Pour toute demande, écrivez à **serge.simono27@gmail.com**. Si la réponse ne vous
satisfait pas, vous pouvez saisir la CNIL : <https://www.cnil.fr/fr/plaintes>.

## 14. Conservation et suppression

| Donnée | Conservation | Suppression |
|---|---|---|
| Données synchronisées | Tant que le compte existe | Compte → Supprimer mon compte |
| Marqueurs de suppression (synchronisation) | 30 jours | Purge automatique |
| Historique Web local | Jusqu'à effacement | Réglages → Confidentialité |
| Journal d'activité de synchronisation | 50 dernières opérations | Compte → Synchronisation → Activité |
| Session locale | Jusqu'à déconnexion | Compte → Se déconnecter |
| Fichiers téléchargés | Indéfiniment | **Jamais supprimés automatiquement**, y compris à la suppression du compte |

## 15. Enfants

L'application ne s'adresse pas aux enfants et ne collecte pas sciemment de données les
concernant. Si vous constatez qu'un compte a été créé par un enfant, écrivez-nous : il
sera supprimé.

## 16. Permissions demandées

Aucune permission n'est demandée au premier lancement. Chacune est demandée au moment où
vous activez la fonction qui en a besoin, et un refus ne désactive que cette fonction.

| Permission | Quand | Pourquoi |
|---|---|---|
| Internet, état du réseau | En continu | Afficher les pages, télécharger, détecter le mode hors ligne |
| Notifications | Au premier téléchargement | Suivre l'avancement d'un transfert. Un refus laisse le suivi consultable dans l'application |
| Service au premier plan, maintien en éveil | Pendant un transfert ou une lecture | Poursuivre un téléchargement ou une lecture écran éteint |
| Accès aux vidéos, aux fichiers audio et aux images de l'appareil | Quand vous activez l'indexation des médias déjà présents | Retrouver dans la bibliothèque des fichiers que vous possédez déjà. Android 14 et suivants : une sélection partielle est honorée telle quelle |
| Microphone | Quand vous touchez le microphone de la recherche | Recherche vocale. Le clavier fait la même chose |
| Caméra | Quand un site la demande, ou à l'ouverture du lecteur de code | Visioconférence et lecture d'un code |
| Localisation approchée | Quand un site la demande | Répondre à une page qui demande votre position |

**`MANAGE_EXTERNAL_STORAGE` n'est délibérément pas demandée** : elle donnerait accès à
l'intégralité du stockage alors que les permissions granulaires suffisent. Télécharger,
lire et gérer ses propres fichiers fonctionne sans aucune permission de stockage.

## 17. Modifications de cette politique

Toute modification substantielle sera publiée sur cette page avec une nouvelle date de
mise à jour, et signalée dans l'application avant l'activation d'un nouveau traitement.
La politique est également consultable hors ligne depuis l'application, dans la version
qui accompagne celle que vous avez installée.

---

Voir aussi : [Supprimer votre compte et vos données](suppression-compte/).
