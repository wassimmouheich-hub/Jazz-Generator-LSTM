# Jazz Improvisation AI Generator (LSTM)

Projet de Deep Learning : Génération de séquences musicales mélodiques en utilisant des réseaux de neurones récurrents.**

Ce projet explore la capacité des modèles **LSTM (Long Short-Term Memory)** à apprendre les structures complexes du Jazz (intervalles, rythmique, motifs) pour générer de nouvelles improvisations au format MIDI.

---

## Vision du Produit (Product Vision)
L'idée était de créer un "compagnon d'improvisation". Le modèle ne se contente pas de copier des notes, il apprend la probabilité qu'une note suive une autre en fonction du contexte précédent (la "mémoire" du réseau).

### Résultats du Modèle (Audio MIDI)
Les fichiers générés par l'IA sont disponibles à la racine du dépôt :
* [mon_impro_jazz_3.mid](./mon_impro_jazz_3.mid)
* [mon_impro_jazz_4.mid](./mon_impro_jazz_4.mid)
*(Vous pouvez les lire avec VLC ou n'importe quel séquenceur MIDI).*

---

## Stack Technique & Architecture

* **Framework :** TensorFlow / Keras
* **Architecture :** **LSTM** (Réseau de neurones récurrents). 
    * *Pourquoi ?* Contrairement à un réseau classique, le LSTM possède des "portes" (gates) qui lui permettent de retenir des informations sur le long terme, ce qui est essentiel pour la cohérence d'une mélodie.
* **Traitement de Données :** Librairie music21 pour convertir les fichiers MIDI en séquences numériques.

### Pipeline Technique :
1. **Encodage :** Transformation des notes (C4, Eb3...) en entiers.
2. **Séquençage :** Création de fenêtres glissantes (ex: 100 notes pour prédire la 101ème).
3. **Entraînement :** Optimisation via l'algorithme RMSprop ou Adam pour minimiser la perte (loss).

---

## Accès aux Modèles Entraînés (Fichiers Lourds)

En raison de leur taille, les poids du modèle sont hébergés sur Google Drive :

lien :
* jazz_weights.weights.h5:( https://drive.google.com/file/d/1pcc-NUgzwNcMj7dPTjcN8pcLZ1X9V2-1/view?usp=sharing ) (Poids optimisés lors de l'entraînement)
mon_modele_jazz_metheny.keras:( https://drive.google.com/file/d/1fjX04YB14zOB4ciE3cFkbWDznOj6dKD9/view?usp=sharing ) (Modèle complet exporté)

---

## Défis et Apprentissages (Key Insights)

* **Challenge de la température :** Ajuster le degré d'aléa lors de la génération pour éviter que l'IA ne joue toujours la même note ou, au contraire, ne fasse n'importe quoi.
* **Représentation des données :** Comment encoder les silences et les accords ? Une question cruciale pour la qualité du rendu final.

---
**Développé par Wassim** – Passionné par l'intersection entre l'IA et la création.
