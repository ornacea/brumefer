# Installer et jouer à La Malédiction de Brumefer

Ce guide décrit tout ce qu'il faut installer pour profiter de **toutes** les fonctions du jeu. Il se lit par paliers : le palier 1 suffit pour jouer, les suivants ajoutent les voix puis la modification du jeu.

| Palier | Ce que tu obtiens | Ce qu'il faut |
|---|---|---|
| 1. Jouer | création du héros, meneur de jeu Claude, cartes, Carnet, sauvegardes | l'application Claude pour ordinateur, un abonnement donnant accès à Claude Code |
| 2. Voix du navigateur | lecture du récit à voix haute | une voix française installée sur ton ordinateur |
| 3. Voix VoiceStudio | une voix différente par personnage, plus naturelle | l'application Claude pour ordinateur, VoiceStudio, Node.js |
| 4. Modifier le jeu | ta propre version du jeu | Git |

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

   > Publie `brumefer.html` comme artefact, avec tout le dossier `carto/` en fichiers joints aux mêmes chemins, et les capacités `sample`, `downloads` et `mcp` (serveur `host:voicestudio`, outils `generate_speech`, `design_voice`, `check_health`, `list_voices`).

   Le dossier `carto/` contient les images des cartes : sans lui, les cartes s'affichent vides.

5. Claude te donne un lien `claude.ai/artifact/…` : c'est ton jeu, privé, visible de toi seul. Ouvre-le et commence par forger ton héros. Au premier tour, la page demande l'autorisation d'interroger Claude : accepte. Le meneur de jeu utilise ton compte et ton quota d'utilisation.

Pour une nouvelle version du jeu : récupère la mise à jour (nouveau ZIP ou `git pull`), puis demande à Claude de republier `brumefer.html` **sur le même lien** (le dossier `carto/` déjà publié est conservé ; republie-le seulement s'il a changé).

### Sauvegardes

- La partie en cours est enregistrée automatiquement dans ton navigateur, pour cet artefact. Elle peut disparaître si tu vides les données du site ou changes de navigateur.
- Pour la garder vraiment : **Sauvegarde → Télécharger la sauvegarde (.txt)**. Tu obtiens un fichier `brumefer-<héros>-niv<N>-<date>.txt`.
- Pour la reprendre, ailleurs ou plus tard : **Sauvegarde → Charger un fichier .txt**.
- Si tu modifies un fichier de sauvegarde à la main, charge-le avant de rejouer : sinon la copie du navigateur l'écrasera à la sauvegarde automatique suivante.

---

## Palier 2 : voix du navigateur

Le bouton de lecture lit le récit avec les voix françaises de ton système. Il n'y a rien à installer dans le jeu, seulement une voix française sur l'ordinateur :

- **Windows 11** : Paramètres → Heure et langue → Voix (ou Langue et région) → ajoute une voix **Français (France)**.
- **macOS** : Réglages Système → Accessibilité → Contenu énoncé → Voix du système → Gérer les voix → Français.
- **Android / iOS** : réglages de synthèse vocale du système, langue française.

Redémarre ensuite le navigateur. Les navigateurs Chrome et Edge proposent en général les voix les plus naturelles.

---

## Palier 3 : voix VoiceStudio (une voix par personnage)

[VoiceStudio](https://github.com/debpalash/VoiceStudio) génère les voix **sur ton ordinateur** : le narrateur et chaque personnage reçoivent une voix propre. Le jeu passe par l'application Claude pour l'atteindre ; sans elle, ou si VoiceStudio est fermé, il reprend la voix du navigateur.

Prérequis : ta propre copie publiée avec la capacité `mcp` (palier 1).

1. **Installe VoiceStudio** en suivant les instructions de sa page GitHub, puis lance l'application.
2. Dans VoiceStudio, ouvre **Model Catalogue**, télécharge un modèle de synthèse vocale qui parle français et **accepte sa licence**. Sans cela, le jeu affiche : « la licence du modèle n'est pas acceptée ».
3. Vérifie que le service tourne : la page `http://127.0.0.1:3900/health` doit répondre dans ton navigateur.
4. **Installe Node.js** (version LTS) depuis [nodejs.org](https://nodejs.org). Il sert à relier l'application Claude à VoiceStudio.
5. Dans l'application Claude : **Paramètres → Développeur → Modifier la configuration**. Le fichier `claude_desktop_config.json` s'ouvre. Ajoute le serveur `voicestudio` dans `mcpServers` :

   ```json
   {
     "mcpServers": {
       "voicestudio": {
         "command": "npx",
         "args": ["-y", "mcp-remote", "http://127.0.0.1:3900/mcp/"]
       }
     }
   }
   ```

   Si le fichier contient déjà d'autres serveurs, ajoute seulement le bloc `"voicestudio": { … }` à côté d'eux. Sous Windows, si `npx` n'est pas trouvé, mets son chemin complet, par exemple `"C:\\Program Files\\nodejs\\npx.cmd"`.
6. Quitte complètement l'application Claude, puis relance-la (VoiceStudio étant ouvert).
7. Ouvre ton jeu **dans l'application Claude** (pas dans un navigateur web) et lance la lecture d'un passage. L'application demande l'accès à VoiceStudio pour cette page : accepte.

Si la voix ne change pas, le message du jeu indique la cause :

| Message | Que faire |
|---|---|
| « VoiceStudio injoignable… » | VoiceStudio n'est pas lancé, ou le serveur `voicestudio` manque dans la configuration de l'application Claude (étapes 1, 5 et 6) ; ou le jeu est ouvert dans un navigateur au lieu de l'application |
| « Accès à VoiceStudio refusé pour cette page » | l'accès a été refusé, ou l'artefact a été publié sans la capacité `mcp` (palier 1, étape 4) |
| « la licence du modèle n'est pas acceptée » | étape 2 |

---

## Palier 4 : modifier le jeu

1. Installe [Git](https://git-scm.com) et clone le dépôt : `git clone https://github.com/ornacea/brumefer.git`
2. Modifie `brumefer.html` : interface, règles et consignes du meneur de jeu sont lisibles directement. Les textes du scénario sont encodés pour éviter les révélations ; la page les décode au chargement.
3. Republie ta copie (palier 1, étape 4) pour jouer avec tes modifications.
4. La licence (voir `LICENSE`) te demande de créditer « La Malédiction de Brumefer, par Orna », de ne pas en faire un usage commercial et de partager tes modifications sous la même licence.
