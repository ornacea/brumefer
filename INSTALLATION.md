# Installer et jouer à La Malédiction de Brumefer

Ce guide décrit tout ce qu'il faut installer pour profiter de **toutes** les fonctions du jeu. Il se lit par paliers : le palier 1 suffit pour jouer, le second permet de modifier le jeu.

| Palier | Ce que tu obtiens | Ce qu'il faut |
|---|---|---|
| 1. Jouer | création du héros, meneur de jeu Claude, cartes, Carnet, sauvegardes | l'application Claude pour ordinateur, un abonnement donnant accès à Claude Code |
| 2. Modifier le jeu | ta propre version du jeu | Git |

---

## Palier 1 : jouer

Le jeu est une seule page, `brumefer.html`. Son **meneur de jeu est Claude** : la page lui pose ses questions par la fonction `sample` des artefacts Claude. Le jeu ne marche donc pleinement **que publié comme artefact sur claude.ai**. Ouvert directement depuis ton disque, il permet de créer un héros et de relire une partie, mais le meneur de jeu affiche : « Le maître du jeu n'est pas disponible : ouvre cette page sur claude.ai, connecté à ton compte. »

Pour jouer, **chacun publie sa propre copie** du jeu, sous son propre compte Claude. Aucun lien de partie n'est mis à disposition : n'utilise pas un lien qui circulerait, il ne te donnerait de toute façon ni les voix VoiceStudio ni ta propre version à jour.

### Publier ta propre copie

Il faut un abonnement Claude qui donne accès à **Claude Code** (offre Pro ou supérieure).

1. Installe l'application Claude pour ordinateur depuis [claude.ai/download](https://claude.ai/download) et connecte-toi.
2. Récupère le jeu :
   - sans Git : sur la page GitHub du dépôt, **Code → Download ZIP**, puis décompresse le dossier ;
   - avec Git : `git clone https://github.com/ornacea/brumefer.git`
3. Dans l'application Claude, ouvre l'onglet **Code** et choisis le dossier `brumefer` comme dossier de travail.
4. Demande à Claude, mot pour mot :

   > Publie `brumefer.html` comme artefact, avec tout le dossier `carto/` en fichiers joints aux mêmes chemins, et les capacités `sample`, `downloads`, `db` et `user`.

   Le dossier `carto/` contient les images des cartes : sans lui, les cartes s'affichent vides.

5. Claude te donne un lien `claude.ai/artifact/…` : c'est ton jeu, privé, visible de toi seul. Ouvre-le et commence par forger ton héros. Au premier tour, la page demande l'autorisation d'interroger Claude : accepte. Le meneur de jeu utilise ton compte et ton quota d'utilisation.

Pour une nouvelle version du jeu : récupère la mise à jour (nouveau ZIP ou `git pull`), puis demande à Claude de republier `brumefer.html` **sur le même lien** (le dossier `carto/` déjà publié est conservé ; republie-le seulement s'il a changé). Si ta copie a été publiée avant la sauvegarde en ligne, demande une fois de republier avec la liste complète des capacités de l'étape 4 : `db` et `user` s'ajoutent alors aux autres.

### Sauvegardes

- La partie en cours est enregistrée automatiquement sur l'appareil **et en ligne**, dans un espace privé de ton compte Claude propre à ta copie du jeu (capacités `db` et `user`) : personne d'autre ne le lit.
- **Changer d'appareil** : ouvre le même lien `claude.ai/artifact/…`, connecté au même compte Claude, sur claude.ai dans un navigateur, dans l'application Claude pour ordinateur ou dans l'application Claude sur iPhone, iPad ou Android. Tes parties y sont, là où tu les as laissées. La pastille **☁ En ligne**, à côté des emplacements, confirme la sauvegarde en ligne.
- Si une même partie a avancé sur deux appareils sans synchronisation entre-temps (par exemple hors connexion), le jeu te demande laquelle garder.
- Pour la garder vraiment : **Sauvegarde → Télécharger la sauvegarde (.txt)**. Tu obtiens un fichier `brumefer-<héros>-niv<N>-<date>.txt`.
- Pour la reprendre, ailleurs ou plus tard : **Sauvegarde → Charger un fichier .txt**.
- Si tu modifies un fichier de sauvegarde à la main, charge-le avant de rejouer : sinon la copie enregistrée l'écrasera à la sauvegarde automatique suivante.

---

## Palier 2 : modifier le jeu

1. Installe [Git](https://git-scm.com) et clone le dépôt : `git clone https://github.com/ornacea/brumefer.git`
2. Modifie `brumefer.html` : interface, règles et consignes du meneur de jeu sont lisibles directement. Les textes du scénario sont encodés pour éviter les révélations ; la page les décode au chargement.
3. Republie ta copie (palier 1, étape 4) pour jouer avec tes modifications.
4. La licence (voir `LICENSE`) te demande de créditer « La Malédiction de Brumefer, par Orna », de ne pas en faire un usage commercial et de partager tes modifications sous la même licence.
