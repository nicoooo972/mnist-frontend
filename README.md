# MNIST Frontend

Cette application Streamlit constitue l'interface utilisateur (UI) de notre projet. Elle permet à un utilisateur d'interagir avec le modèle de classification de chiffres en dessinant un chiffre et en obtenant une prédiction en temps réel.

## Rôle dans l'architecture MLOps

Le frontend est la vitrine de notre système. Il joue plusieurs rôles :

- **Interaction utilisateur** : Il fournit un moyen simple et intuitif de tester le modèle avec `streamlit-drawable-canvas`. C'est crucial pour la démonstration du projet et pour obtenir des retours qualitatifs.
- **Consommation de l'API** : Il communique avec le `mnist-backend` en envoyant les images dessinées par l'utilisateur à l'API de prédiction et en affichant le résultat.
- **Monitoring (potentiel)** : Il peut être utilisé pour collecter de nouvelles données. Les prédictions incorrectes signalées par les utilisateurs peuvent être enregistrées et utilisées pour améliorer les futures versions du modèle (boucle de rétroaction).

## Technologies

- **Streamlit** : Pour construire rapidement une application web interactive en Python.
- **Docker** : Pour packager l'application et ses dépendances.

## Démarrage

Pour lancer le service localement (généralement orchestré par `docker-compose` depuis le dossier `mnist-deployment`):

```bash
docker build -t mnist-frontend .
docker run -p 8501:8501 mnist-frontend
```

## 🚀 Démarrage rapide

```bash
# Installation des dépendances
pip install -r requirements.txt

# Lancement de l'interface (assure-toi que l'API backend tourne)
streamlit run app.py
```

## 🎯 Fonctionnalités

- 🖊️ Canvas de dessin interactif
- 🔍 Classification en temps réel
- 📊 Affichage des probabilités pour chaque classe
- 🌐 Connexion automatique à l'API backend

## ⚙️ Configuration

L'application se connecte au backend via la variable d'environnement :
```bash
export API_URL=http://localhost:8000
```

## 📱 Utilisation

1. Dessine un chiffre (0-9) dans le canvas blanc
2. Clique sur "🚀 Prédire"
3. Vois le résultat et les probabilités

## 🔗 Prérequis

Le backend API doit être en cours d'exécution sur `http://localhost:8000` (ou l'URL configurée dans `API_URL`). 