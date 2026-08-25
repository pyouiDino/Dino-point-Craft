# Dinocraftpoint — Guide d'utilisation

Plugin Nova Life permettant de créer des points de craft, un joueur entre dans un cercle bleu, consulte les infos du craft, clique sur "Craft", reste immobile pendant le temps requis, et reçoit l'objet fabriqué.

---

## 1. Commandes

### `/craftnom` — Créer un point de craft

```
/craftnom <nom> itemcraft <id résultat> <quantité> item <id nécessaire> <quantité> [item <id> <qté> ...] time <secondes> [visible <id entreprise>] ou [invisible <id entreprise>]
```

Le point est créé **à la position exacte du staff** au moment de la commande.

__Paramètres du point de craft__

<nom> | Nom du point de craft.

itemcraft <id> <quantité> | Définit l'item donné au joueur lorsque le craft est terminé, utilisable une seule fois.

item <id> <quantité> | Définit les items nécessaires pour réaliser le craft, au moins 1 item. Peut être utilisé plusieurs fois pour ajouter plusieurs ressources.

time <secondes> | Définit le temps nécessaire pour terminer le craft en seconde.

visible <id entreprise> | Rend le point visible et utilisable uniquement par l'entreprise indiquée, Optionnel.

invisible <id entreprise> | Empêche l'entreprise indiquée de voir et d'utiliser le point. Optionnel.

`visible` et `invisible` ne peuvent pas être utilisés ensemble sur le même point.

**Exemple :**
```
/craftnom Point_de_SP itemcraft 6 1 item 1088 20 item 1099 5 time 500 invisible 2 ( la police par exemple ) 
```
→ Un point nommé "Point_de_SP", qui donne 1x l'item #6, nécessite 20x l'item #1088 et 5x l'item #1099, dure 500 secondes, et n'est visible que par l'entreprise #2.

### `/listecraft` — Administrer les points

```
/listecraft
```

Ouvre le panel listant tous les points de craft existants (ID, nom, état). Cliquer sur un point ouvre son panel d'actions.

Les deux commandes nécessitent que le staff ait un **AdminLevel** supérieur ou égal à `CraftAdminMinLevel` (réglable dans la config).

---

## 2. Configuration

Un fichier `DinocraftpointConfig.json` est créé automatiquement au premier démarrage du plugin, dans le dossier `Plugins/Dinocraftpoint` du serveur. Réglages disponibles :

CraftAdminMinLevel
Valeur par défaut : 2
Niveau admin minimum requis pour utiliser /craftnom et /listecraft. 

TriggerRadius
Valeur par défaut : 2.5
Rayon informatif utilisé en interne, exprimé en mètres.

MaxStartDistance
Valeur par défaut : 5
Distance maximale entre le joueur et le point de craft pour pouvoir cliquer sur « Craft ».

MovementCancelTolerance
Valeur par défaut : 0.35
Déplacement maximal autorisé pendant un craft avant son annulation.
La distance est exprimée en mètres.

CheckpointSyncIntervalSeconds
Valeur par défaut : 8
Intervalle de sécurité entre deux resynchronisations des cercles bleus.
Une resynchronisation immédiate est également effectuée à chaque création, activation ou suppression d'un point.

TickIntervalSeconds
Valeur par défaut : 1
Fréquence du décompte pendant qu'un craft est en cours.

---

## 3. Dépendance obligatoire

### ModKit

Dinocraftpoint nécessite **ModKit** pour fonctionner.

Téléchargement de ModKit :
https://plugins.modnl.me/plugins

---

## 4. Support

Si vous avez des questions ou rencontrez un problème avec le plugin, vous pouvez contacter :

Discord : py0ui
Serveur discord : https://discord.gg/2cwRtZTjM5 et ou https://discord.gg/KnRR4GYpQV

