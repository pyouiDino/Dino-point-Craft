# Dinocraftpoint — Guide d'utilisation

Plugin Nova Life permettant de créer des points de craft, un joueur entre dans un cercle bleu, consulte les infos du craft, clique sur "Craft", reste immobile pendant le temps requis, et reçoit l'objet fabriqué.

---

## 1. Commandes

### `/craftnom` — Créer un point de craft

```
/craftnom <nom> itemcraft <id résultat> <quantité> item <id nécessaire> <quantité> [item <id> <qté> ...] time <secondes> [visible <id entreprise>] ou [invisible <id entreprise>]
```

Le point est créé **à la position exacte du staff** au moment de la commande.

| Paramètre | Obligatoire | Description |
|---|---|---|
| `<nom>` | Oui | Nom du point de craft |
| `itemcraft <id> <quantité>` | Oui (une seule fois) | Item donné au joueur à la fin, et la quantité donnée |
| `item <id> <quantité>` | Oui (au moins un, répétable) | Item(s) nécessaire(s) pour le craft |
| `time <secondes>` | Oui | Durée du craft |
| `visible <id entreprise>` | Non | Seule cette entreprise peut voir/utiliser le point |
| `invisible <id entreprise>` | Non | Cette entreprise ne peut pas voir/utiliser le point |

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

| Réglage | Valeur par défaut | Rôle |
|---|---|---|
| `CraftAdminMinLevel` | `2` | Niveau admin minimum requis pour `/craftnom` et `/listecraft` |
| `TriggerRadius` | `2.5` | Rayon informatif utilisé en interne (mètres) |
| `MaxStartDistance` | `5` | Distance max du point pour pouvoir cliquer "Craft" |
| `MovementCancelTolerance` | `0.35` | Déplacement max toléré (mètres) pendant un craft avant annulation |
| `CheckpointSyncIntervalSeconds` | `8` | Intervalle de sécurité entre deux resynchronisations des cercles bleus (une resynchro immédiate a de toute façon lieu à chaque création/activation/suppression de point) |
| `TickIntervalSeconds` | `1` | Fréquence du décompte pendant un craft en cours |

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

