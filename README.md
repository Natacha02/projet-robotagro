# projet-robotagro

1. Contexte et objectif du projet
Dans le cadre de notre projet, nous avons dû mettre en place un système capable de :

Acquérir des données depuis un capteur connecté à une carte (Micro:bit ou Arduino),

Transmettre les données à un serveur pour les stocker et les exploiter,

Visualiser la position des fraises sur une carte numérique.

Ce projet s’inscrit dans une démarche d’agriculture connectée, où l’objectif est de surveiller en temps réel l’état de cultures (humidité, température...) pour mieux intervenir.



2. Matériel et technologies utilisés
Élément	Utilité
Micro:bit	Acquisition de données (T4)
Capteur d’humidité	Mesure du sol (ex: connecté à P0)
Port USB (liaison série)	Transfert des données vers PC
Python	Script pour lire et traiter les données
Flask	Serveur web pour afficher les infos
Folium	Affichage des fraises sur une carte
GitHub	Stockage du projet et livrable final
Images / captures	Pour illustrer le fonctionnement



3. Fonctionnement du système
✅ Lecture des données :
Le Micro:bit lit la valeur d’un capteur d’humidité.

Les données sont envoyées via liaison série à un ordinateur.

✅ Traitement :
Un script Python lit ces données avec serial et les convertit en un format exploitable.

Les données sont organisées par localisation (chaque fraise → coordonnées GPS simulées).

✅ Visualisation :
Une carte Folium est générée avec des points interactifs représentant les fraises.

Chaque point affiche les données reçues (ex: humidité).


4. Programme utilisé sur le Micro:bi
from microbit import *
while True:
    valeur = pin0.read_analog()
    print(valeur)
    sleep(1000)

5. Serveur Flask                             
from flask import Flask, render_template, jsonify

app = Flask(__name__)

# Exemple de données reçues
data = {
    "fraise_1": {"humidité": 612, "coord": [48.85, 2.35]},
    "fraise_2": {"humidité": 580, "coord": [48.851, 2.351]}
}

@app.route('/')
def home():
    return render_template("index.html", data=data)

@app.route('/api/data')
def get_data():
    return jsonify(data)

if __name__ == '__main__':
    app.run(debug=True)


 6. Carte interactive Folium

import folium

m = folium.Map(location=[48.85, 2.35], zoom_start=15)
folium.Marker([48.85, 2.35], popup="Fraise 1 - Humidité 612").add_to(m)
m.save("templates/index.html")

8. Conclusion
Le projet a permis de créer une chaîne complète d’acquisition, de traitement et de visualisation de données.
L’objectif est atteint : les fraises sont visibles sur une carte, avec les données environnementales à jour.

🔧 Améliorations possibles :
Ajouter du Bluetooth / Wi-Fi pour éviter le filaire

Sauvegarder les données dans une base de données (MySQL, Firebase…)

Ajouter des capteurs supplémentaires (température, luminosité…)

	




