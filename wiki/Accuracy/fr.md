# Accuracy
L'accuracy (précision) est la mesure de la constance d'un joueur. Il existe 3 types d'accuracy qu'un joueur peut avoir. L'un d'eux étant l'accuracy de la beatmap qui dépend du score obtenu. Un autre étant l'accuracy d'ensemble du joueur qui est pesé de manière à faire plus ressortir les meilleurs scores. Et dernièrement, l'accuracy [pp](/wiki/pp) du joueur qui dépenderas de l'accuracy du score enregistré.

## Game modes

### osu!standard

![Accuracy = (50 \* number of 50s + 100 \* number of 100s + 300 \* number of 300s) / 300(number of 0s + number of 50s + number of 100s + number of 300s)](img/accuracy_standard.png "Accuracy formula for osu!standard")

Dans osu!standard, l'accuracy est calculé en pondérant la précision obtenu de chaque objet touché par sa valeur et diviser par le maximum possible.

Reference for one hit circle:

```
300 -> 300 / 300 = 1   = 100.00%
100 -> 100 / 300 = 1/3 =  33.00%
50  ->  50 / 300 = 1/6 =  16.67%
0   ->   0 / 300 = 0   =   0.00%
```

### osu!taiko

![Accuracy = 0.5(number of GOOD + number of GREAT) / (number of BAD + number of GOOD + number of GREAT)](img/accuracy_taiko.png "Accuracy formula for osu!taiko")

En osu!taiko, l'accuracy est calculé en prenant la somme de la précision de la note divisé par le nombre de notes. La précision des notes sont : a GREAT (良) counts as 100%, GOOD (可) as 50% (half), and MISS/BAD (不可) as 0% (which also breaks the combo). Drum rolls (équivalent des sliders) et spinners n'influence pas l'accuracy.

### osu!catch

![Accuracy = (number of droplets + number of drops + number of fruits) / (number of missed droplets + number of missed drops + number of missed fruits + number of droplets + number of drops + number of fruits)](img/accuracy_catch.png "Accuracy formula for osu!catch")

En osu!catch, l'accuracy est calculé en prenant le total des objets touché (sauf spinner) par le total d'objets touchable (sauf spinner). Tous les objets ont la même valeur, sauf pour les bananes (skin de base), du fait que ce soit les objets formant le spinner.

*Note pour les utilisateurs d' API : Pour calculé l'accuracy en osu!catch, le nombre de goutellettes sont en dessous `count50` et le nombre de goutelletes raté dont sous `countkatu`.*

### osu!mania

![Accuracy = (50 \* number of 50s + 100 \* number of 100s + 200 \* number of 200s + 300 \* number of 300s + 300 \* number of MAXs) / 300(number of 0s + number of 50s + number of 100s + number of 200s + number of 300s + number of MAXs)](img/accuracy_mania.png "Accuracy formula for osu!mania")

En osu!mania, l'accuracy est calculé de la même manière qu'en [osu!standard](#osu!standard).

## Performance graph

![Performance graph](img/performance_graph.jpg "Performance graph")

Le graph de performance est un graphique récapitulatif qui montre la performance du joueur (en se basant sur sa barre de vie) au fil de la partie. Des informations supplémentaires sont disponible lorsqu'on passe le curseur du jeu dessus.

*Note: Les informations supplémentaires sont disponible qu'après avoir joué une beatmap ou regardé un replay exporté. Après avoir quitté le [results screen](/wiki/results_screen), les informations ne seront pas sauvegardé.*

### Accuracy

Lorsqu'on passe sur le performance graph, une info-bulle apparrait avec *Error* et *Unstable Rate*.

Du fait que [DT](/wiki/DT) (Double Time) and [HT](/wiki/HT) (Half Time) mods sont tel, la valeur de l'error et unstable rate (taux d'instabilité) seront multiplié par les mêmes facteurs que la music. Pour avoir les vrais valeur, lorsque vous jouez DT, il faut divisé le résultat de 1.5. De la même manière avec HT, il faut multiplié de 1.33.

#### Error

Error montrera toujours 2 valeurs représentant la moyenne de comment les clics étaient trop tôt (première valeur) et trop tard (seconde valeur). Plus haute est lavaleur d'[Overall Difficulty](/wiki/Overall_Difficulty), moins les erreurs (Error) devront être présente pour bien joué la beatmap.

#### Unstable rate

Unstable rate (taux d'instabilité) représente la constance des clic par rapport au timing, où il est mieux de faire de petite valeurs (les top joueurs ont souvement un taux inférieur à 100). A noté que la valeur mesure la constance, et non l'accuracy, donc tapé toujours 15ms trop tôt est pareil que de tapé "sur le bon timing". La formule est essentiellement l'écart type des erreurs de frappe (en millisecondes) multiplié par 10.

### Spin

*Note: Spin est seulement utilisé pour [osu!standard](/wiki/osu!standard).*

En plus de l'accuracy, quelques informations sur les spinner est également montré dans notre info-bulle.

#### Speed

Speed représente la moyenne d'RPM (Revolutions Per Minute, soit le nombre de tours par minute) sur tous les spinners de la beatmap. Max est le RPM le plus haut fait sur n'importe quel spinner de cette beatmap.

#### Unstable rate

Unstable rate représente la moyenne de la déviation Max, où les petits nombres sont mieux. La formule est inconnu.
