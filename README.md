# RL

## Projektbeschreibung

Der vorliegende Projektbericht handelt vom Training eines Reiforcement Algorithmus auf der DonkeyCar Simulation.

Das Trainieren der Modelle auf den ursprünglichen Bilddaten, die 120x160x3 Pixel im Falle des Donkeycars darstellen, wird als ineffizient und zeitaufwändig angesehen. Deshalb wurden neben den Modellen auch verschiedene Bildvorverarbeitungsmethoden verwendet.

Hierfür wurde zuerst ein DDQN-Modell trainiert, das mit Lienendetection vorverarbeitete Bilder der Donkeycar-Umgebung als Eingabe bekommt und eine Aktion zurückgibt. Da dieser Ansatz nicht den gewünschten Trainingserfolg brachte, erfolgte im Anschluss das Trainieren eines SAC-Agenten, der anstelle der urpsrünglichen Bilder durch einen Autoencoder vorverarbeitete Bilder als Eingabe erhält.
Hierbei zeigt sich, dass der Agent trainiert. Dennoch sind weitere Optimierungen notwendig, wie ein längeres Trainieren, das Tuning von Hyperparametern oder das Trainieren des Autoencoders auf unterschiedlichen Umgebungen, um den Agenten ebenfalls auf diesen anwenden zu können.

## Ordnerstruktur

- data:
  - dataset-mountain/: erstellte Trainingsdaten
  - erstellte Grafiken der Notebooks
- src_DDQN:
  - car_simulator_lane_detection.ipynb: Modelltraining DDQN und Lane-Detection Vorverarbeitungsschritte
- src_SAC:
  - checkpoints/: modelcheckpoints during training
  - models/: trained autoencoder
  - train_ae_template/: functions from https://github.com/araffin/aae-train-donkeycar with minor changes for autoencoder training
  - sac_donkeycar.ipynb: training of SAC-model
  - test_autoencoder.ipynb: testing the autoencoder
- 0_1434_478_956_Epochen.mp4: Darstellung des Trainingsverlaufs in den verschiedenen Epochen; nur geringe Verbesserung ersichtlich
- demo_lasst.mp4: Demo des finalen Modells
 
## Ausführen
  - Download der Simulationsumgebung: https://github.com/tawnkramer/gym-donkeycar/releases
  - Installation von GymDonkeycar Master: pip install git+https://github.com/tawnkramer/gym-donkeycar
  - Installation der Requirements: conda install requirements.txt

## Mitarbeiter

Olena Lavrikova, Philipp Dingfelder

Matrikelnummern: 5436924, 868778

Aufgabenverteilung: Die meisten Teile des Codes wurden während pair programming sessions implementiert. Kleine Unterschiede gab es nur beim Autoencoder, der überwiegend von Olena trainiert wurde und bei SAC Notebook, bei Philipps Anteil etwas größer war.
