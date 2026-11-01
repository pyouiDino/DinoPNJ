# DinoPNJ — Guide d'utilisation

Plugin Nova Life permettant au staff de créer des PNJ : un PNJ immobile posé à votre position, ou un PNJ mobile qui rejoue à l'identique un parcours que vous avez enregistré. Son apparence se choisit par catégories ou par tenue spéciale, et les PNJ sont sauvegardés à chaque redémarrage.


---


## 1\. Commandes

## `/pnjpanel` — Ouvrir le panel de gestion

```
/pnjpanel
```

Ouvre le panel « Suivie PNJ » avec deux entrées : **Créer un PNJ** et **Liste des PNJ**.

En cliquant sur **Créer un PNJ**, le panel vous fait passer par ces étapes :

| Étape | Description |
| --- | --- |
| Nom | Nom du PNJ (ne peut pas être vide) |
| Sexe | Homme ou Femme : les vêtements proposés dépendent de ce choix |
| Apparence | Modifie les vêtements et l’apparence du PNJ. Valeurs par défaut si vous ne changez rien. |
| Type | **Mobile** ou **Immobile** : détermine la commande à faire ensuite |

Le bouton **Tester**, dans chaque liste de l'apparence, fait apparaître devant vous un PNJ de test qui ne porte que la pièce sélectionnée, pour la voir avant de la choisir.

### `/pnjspawn` — Créer un PNJ immobile

```
/pnjspawn
```

À faire après avoir choisi le type **Immobile**. Le PNJ est créé **à la position exacte du staff** au moment de la commande, tourné dans la direction où il regarde.

### `/pnjrec` et `/pnjfinrec` — Créer un PNJ mobile

```
/pnjrec
/pnjfinrec
```

À faire après avoir choisi le type **Mobile**. `/pnjrec` démarre l'enregistrement à l'endroit où vous êtes, puis vous marchez ou courez le trajet voulu (arrêts compris). `/pnjfinrec` termine l'enregistrement et crée le PNJ. Si vous ne faites rien, l'enregistrement s'arrête seul au bout d'**1 minute** et le PNJ est créé.

Le PNJ rejoue ensuite votre parcours à la même vitesse, avec l'animation de marche, de course ou d'attente, et fait demi-tour aux extrémités.

`/pnjspawn` et `/pnjrec` ne fonctionnent que si une création est en cours dans `/pnjpanel`.

### `/pnjpanel` → Liste des PNJ — Administrer les PNJ

Liste tous les PNJ existants (ID, nom, état :  actif ou  désactivé). Cliquer sur un PNJ ouvre son panel d'actions :

| Action | Effet |
| --- | --- |
| Activer / Désactiver | Un PNJ désactivé disparaît du monde mais reste enregistré |
| Téléporter au PNJ | Vous téléporte à lui (impossible s'il est désactivé) |
| Supprimer | Après confirmation, supprime le PNJ définitivement ; son ID n'est jamais réutilisé |

Les quatre commandes nécessitent que le staff ait un **AdminLevel** supérieur ou égal à `3` (valeur fixe).

---

## 2\. Configuration

dinoPNJ n'a pas de fichier de configuration : les réglages ci-dessous sont fixes. Un dossier `dinoPNJ/` est créé automatiquement à côté du plugin, avec `dinoPNJ_data.json` (les PNJ sauvegardés) et `dinoPNJ_log.txt` (le journal).

| Réglage | Valeur par défaut | Rôle |
| --- | --- | --- |
| Niveau admin minimum | `3` | Niveau requis pour les 4 commandes |
| Durée max d'un enregistrement | `60` secondes | Fin automatique et création du PNJ mobile |
| PNJ de test | `2` m devant vous, `120` secondes | Il disparaît aussi si vous terminez l'apparence, annulez la création ou vous déconnectez ; un seul par membre du staff |
| Mise en veille des PNJ mobiles | `120` m / `100` m | Un PNJ s'endort quand aucun joueur n'est à moins de 120 m (aucun calcul) et se réveille dès qu'un joueur passe sous 100 m, replacé où il serait |
| Arrêt rejoué maximum | `4` secondes | Durée max d'une pause de votre parcours |

---

## 3\. Dépendance obligatoire

### ModKit

dinoPNJ nécessite **ModKit** pour fonctionner.

Téléchargement de ModKit : <https://plugins.modnl.me/plugins>

---

## 4\. Support

Si vous avez des questions ou rencontrez un problème avec le plugin, vous pouvez contacter :

Discord : py0ui

Serveur discord : <https://discord.gg/2cwRtZTjM5> et ou <https://discord.gg/KnRR4GYpQV>
