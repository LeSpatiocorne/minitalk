# minitalk
### Un client et un serveur se serrent la main, mais y'aura pas de pourboire
On a là un petit projet plutôt simple et amusant. On apprend à faire discuter un serveur et un client avec la lib signal.h.
Pour les électroniciens qui se sont déjà mangé des cours de binaire, c'est l'évidence même.
Pour les autres, promis, votre cerveau s'en remettra ! 🦄

### Notion importantes et pistes de travail
La conversion d'un charactère à la réception au travers de signaux binaires, intéressez-vous à l'utf-8.
-> Exercice en relation examrank02 : reverse_bit / swap_bit (et un autre il me semble).

Pour la première fois, on vous autorise des variables globales, la norminette ne sera pas contente et elle vous le fera savoir.
Que fait-on d'une variable globale ? Pour ma part, je m'en suis servi pour faire un [handshake](https://fr.wikipedia.org/wiki/Handshaking).
La procédure permet d'assurer une bonne synchronisation avec le client et le serveur pour limiter le risque de corrompre vos caratères,
surtout à l'envoie de très long messages qui ont tendance à assez mal vivre le usleep.

### Résultat
125/100 (rendu avec les bonus)
Norminette OK (Warning global variable justifié)
⚠️ J'ai appris après avoir rendu le projet (c'est une honnête erreur de ma part), qu'il faut traiter l'intégralité du signal puis afficher le texte.
Mon programme affiche au fur et à mesure de la réception le message. Personne n'a rien vu parce que mon serveur est très rapide à transmettre le message, donc je l'ai découvert en discutant avec des camarades. Donc si vous pensez faire quelque chose de similaire à moi... Pensez à traiter votre signal en faisant un malloc de votre chaîne, le print intégralement 😉
Une bonne piste à explorer c'est d'envoyer d'abord la taille de la chaîne de caractère à votre serveur pour qu'il puisse allouer l'espace, puis transmettre le message 👍
