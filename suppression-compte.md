---
title: Suppression de compte et de données
permalink: /suppression-compte/
---

# MediaLibre — Supprimer votre compte et vos données

_Dernière mise à jour : 13 septembre 2026._

Cette page décrit comment demander la suppression de votre compte **MediaLibre**
(`com.medialibre.app`) et des données qui y sont associées.

MediaLibre s'utilise **sans compte**. Si vous ne vous êtes jamais connecté, il n'existe
aucune donnée vous concernant hors de votre appareil : désinstaller l'application suffit.

## 1. Supprimer votre compte depuis l'application

1. Ouvrez **MediaLibre**.
2. Allez dans **Compte**.
3. Touchez **Supprimer mon compte**.
4. Confirmez. L'opération est immédiate et définitive.

## 2. Supprimer votre compte sans passer par l'application

Si vous avez désinstallé MediaLibre ou si vous ne parvenez pas à vous connecter, écrivez à :

**serge.simono27@gmail.com**

Indiquez l'adresse e-mail du compte à supprimer, avec « Suppression de compte MediaLibre »
en objet. La demande est traitée **sous 30 jours**. Il vous sera demandé de confirmer
depuis l'adresse du compte, afin que personne ne puisse faire supprimer le compte d'un
autre.

## 3. Ce qui est supprimé

La suppression du compte efface **définitivement et sans délai supplémentaire** :

- le **compte d'authentification** lui-même (Firebase Authentication) : adresse e-mail,
  nom, photo de profil, identifiant de compte, et le mot de passe s'il en existait un ;
- l'ensemble des **données synchronisées** dans Cloud Firestore : favoris, collections,
  progressions de lecture, réglages synchronisés, favoris Web, historique Web et onglets
  ouverts ;
- la **liste de vos appareils** et les dates d'utilisation associées.

Aucune copie n'est conservée à des fins d'archivage, de statistiques ou de sauvegarde
commerciale. Aucune de ces données n'a jamais été transmise à un tiers.

## 4. Ce qui n'est pas supprimé

| Donnée | Où elle se trouve | Ce qu'il faut faire |
|---|---|---|
| **Vos fichiers téléchargés** | Sur votre appareil, dans le dossier que vous avez choisi | Ils vous appartiennent et ne sont **jamais supprimés automatiquement**. Supprimez-les vous-même si vous le souhaitez |
| Bibliothèque, file de téléchargement, corbeille, cookies, historique local, réglages | Dans l'espace privé de l'application, sur votre appareil | Réglages → Confidentialité, ou désinstallation de l'application |
| Marqueurs techniques de suppression | Cloud Firestore | Purgés automatiquement sous **30 jours**. Ils ne contiennent qu'un identifiant interne et une date, jamais un titre ni une adresse |

Ces données n'ont jamais quitté votre appareil, à l'exception des marqueurs techniques
mentionnés ci-dessus.

## 5. Supprimer une partie de vos données sans supprimer votre compte

Vous n'êtes pas obligé de supprimer votre compte pour effacer des données :

- **Supprimer un élément** — un favori, une collection, un favori Web, une entrée
  d'historique — le supprime aussi du serveur à la synchronisation suivante.
- **Compte → Synchronisation** coupe la synchronisation en bloc ou catégorie par
  catégorie. Attention : couper une catégorie **arrête l'envoi sans rien effacer** de ce
  qui a déjà été synchronisé. Pour effacer, supprimez les éléments concernés, ou
  écrivez-nous.
- **Réglages → Confidentialité** efface l'historique Web, les cookies et les données de
  site conservés sur l'appareil.
- **Compte → Exporter mes données** vous remet une copie lisible de vos données avant
  toute suppression.

Pour la suppression d'une catégorie précise de données côté serveur sans supprimer le
compte, écrivez à **serge.simono27@gmail.com** en indiquant ce que vous souhaitez voir
effacé. Délai de traitement : **30 jours**.

---

Voir aussi la [politique de confidentialité](./) de MediaLibre.
