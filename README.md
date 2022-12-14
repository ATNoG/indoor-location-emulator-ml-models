# Machine Learning Models

This repository includes machine learning modules for the SDRT project.

src - ML techniques based on the SDRT simulator. It contains python scripts for model training, stored in the corresponding location directory and a python script "predictor.py" that contains a MQTT agent responsible for communicating with the simulator and predict the location of assets based on their rssi values and the previously trained ml models.

By default, the predictor.py script will make predictions based on the models stored in the "somos_saude" dir but this could be changed by running with --models "name of another folder": python3 predictor.py --models it

Model Training:
The train.sh script was created as an easier and faster way to train all the models.
To use it, there must be a dataset which name starts with "rssi_antennas" in the same dir as the script, where shouldn't be stored any important model with the same name as the new ones, otherwise they will be overwritten.
The dir which the models will be moved into is the "somos_saude" by default, but it can be changed in the script.

## Main features

- MQTT client for communication ((paho-mqtt) at <em>predictor.py</em>)
- Model trainning
- Asset location prediction based on stored models

The Dev environment implies the creation of a virtual environment (venv) whose dependencies come in the ```requirements.txt``` file.

### Usefull commands:
- install venv package: > ```sudo apt-get install python3-venv```
- remove .venv directory: > ```rm -Rfv .venv```
- create .venv directory: > ```python3 -m venv .venv```
- activate .venv: > ```source .venv/bin/activate```
- install dependencies on .venv from requirements.txt: > ```pip install -r requirements.txt```
- generate documentation using pdoc: > ```pdoc --math -d google -o docs src/predictor.py```
- show .venv network ip route: > ```ip route```

### Documentation

Python Documentation of ML Models Module, built with <em>pdoc</em>: [here](https://atnog.github.io/indoor-location-emulator-ml-models/).

---


