


#  Revue 2 – Validation des solutions techniques

##  Objectif de cette tâche

Dans cette deuxième revue, ma mission était de :

- Créer un code pour le positionnement du robot
- Réaliser un montage simulé sur **Wokwi** avec l'ESP32 et un capteur de température
- Afficher les données de température sur ThingSpeak
- Vérifier que la chaîne de données fonctionne correctement

---

##  Installation et configuration

J'ai utilisé les éléments suivants pour cette simulation sur **Wokwi** :

- **Carte ESP32** : Utilisée pour la gestion du capteur de température et la connexion sans fil
- **Capteur de température** : Pour mesurer la température ambiante
- **Plateforme ThingSpeak** : Pour l'affichage et la collecte des données

J'ai configuré le montage sur **Wokwi**, où l'ESP32 collecte les données du capteur de température et les envoie à ThingSpeak via Wi-Fi.

---

##  Mise en œuvre de la chaîne d’acquisition

Voici la configuration de la chaîne de traitement des données :

1. **Acquisition** : Le capteur de température mesure la température ambiante.
2. **Transmission** : L'ESP32 envoie les données à ThingSpeak via Wi-Fi.
3. **Restitution** : Les données sont affichées en temps réel sur ThingSpeak, pour une visualisation à distance.

---

##  Grandeur mesurée

- **Température** (en °C)

---

##  Respect des contraintes

| Contrainte | Statut | Détails |
|------------|--------|---------|
| Fiabilité des données | oui | Les données sont stables et envoyées à ThingSpeak sans erreur |
| Transmission sans fil |  oui| L'ESP32 se connecte correctement à Wi-Fi et transmet les données |
| Affichage des données |oui | Les données de température s'affichent correctement sur ThingSpeak |

---

##  Prototypage rapide

- Le montage a été simulé sur **Wokwi**, avec l'ESP32 et le capteur de température connectés
- J'ai testé la communication avec ThingSpeak et cela fonctionne bien

---

##  Bilan personnel

> Le montage est simulé sur Wokwi et fonctionne comme prévu.  
> L'ESP32 récupère bien la température et l'envoie à ThingSpeak en temps réel.  
> Le système de collecte et d'affichage des données est validé.  
> Il me reste à finaliser le code pour le positionnement du robot dans la prochaine étape.

---

##  Fichiers fournis

- [Lien vers le projet Wokwi](https://wokwi.com/projects/XXXXXX) – Simulation du montage ESP32 et capteur de température (remplace par ton lien)
- `code/esp32_temperature.ino` – code Arduino pour ESP32 et capteur de température
- Lien vers ThingSpeak : [Ton Channel ThingSpeak](https://thingspeak.com/channels/XXXXXX)
![image](https://github.com/user-attachments/assets/83f118fa-2bfb-40aa-b33a-e6d1dd7952ba)



