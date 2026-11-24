# Contribuer à La Malédiction de Brumefer

Merci de vouloir aider ! Les propositions sont les bienvenues : corrections de règles, bugs, interface, accessibilité, cartes, idées d'aventure.

## Les règles du dépôt

- **Seul l'auteur (@ornacea) décide** de ce qui entre dans le jeu. La branche `main` est protégée : personne d'autre ne peut y écrire, ni directement ni par une fusion.
- Ce dépôt est **l'export public** du jeu. Chaque version y arrive en un seul commit « Version X.Y.Z », depuis la source de travail de l'auteur. Une proposition acceptée n'est donc **pas fusionnée telle quelle** : l'auteur la reporte dans sa source, et elle paraît dans la version suivante. La pull request est alors fermée avec la mention de la version qui l'intègre.

## Proposer une modification

1. Fais une copie du dépôt sur ton compte (**Fork**).
2. Crée une branche pour ta proposition, par exemple `correctif-initiative` ou `carte-legende`.
3. Modifie `brumefer.html` et vérifie ta modification dans ta propre copie publiée du jeu (voir [INSTALLATION.md](INSTALLATION.md)).
4. Ouvre une **pull request** vers `main`, en expliquant :
   - ce que ta modification change pour le joueur ;
   - comment l'auteur peut la vérifier en jeu ;
   - si une ancienne sauvegarde est concernée.

Une pull request courte, qui fait une seule chose, a beaucoup plus de chances d'être acceptée.

## Branche `voix` : la lecture à voix haute

La lecture du récit à voix haute a été retirée de `main` à la version 0.89.0. Son code est conservé dans la branche [`voix`](https://github.com/ornacea/brumefer/tree/voix), dans l'état de la version 0.88.0, et la communauté est invitée à la reprendre : fiabilité, voix plus naturelles, téléphones, réglages plus simples.

1. Dans ton fork, crée ta branche **à partir de `voix`**.
2. Ouvre ta pull request **vers `voix`**, pas vers `main`.
3. Les mêmes règles s'appliquent : seul l'auteur décide de ce qui est intégré. Quand la lecture à voix haute sera assez solide, elle reviendra dans `main`.

## Signaler un problème ou proposer une idée

Ouvre un ticket (**Issues → New issue**) avec :
- ce que tu as fait, ce que tu attendais, ce qui s'est passé ;
- la version du jeu (bouton de version en haut de la page) ;
- si possible, ta sauvegarde exportée (`.txt`), sans données personnelles.

## Le scénario

Les textes du scénario sont encodés dans `brumefer.html` pour ne pas être lus par hasard : une modification de ces textes est illisible dans une pull request. Pour l'histoire, les personnages ou les lieux, **décris ton idée dans un ticket** plutôt que de modifier le code.

**Pas de révélations** dans les tickets, les pull requests et les messages de commit : d'autres joueurs les lisent avant d'avoir fini l'aventure. Si tu dois parler d'un passage précis, reste vague ou décris-le sans nommer qui ou quoi.

## Licence de tes contributions

En proposant une contribution, tu acceptes qu'elle soit diffusée sous la licence du projet, **CC BY-NC-SA 4.0** (voir [LICENSE](LICENSE)), et que l'auteur l'adapte en l'intégrant. Tes contributions acceptées sont créditées dans le journal des versions.

N'ajoute que du contenu dont tu as les droits : pas de texte, d'image ou de son repris d'un autre jeu ou d'une œuvre protégée, et, pour les règles, seulement des éléments du SRD 5.1.

## Respect

Sois bienveillant dans les échanges. Les messages agressifs ou hors sujet sont fermés.
