# SESAR

Gestionnaire de Tâches Dynamique (Front + Back séparés)

## Structure du projet

- `backend/` : serveur Flask + stockage (tasks.json)
- `frontend/` : UI (HTML/CSS/JS)

## Démarrer le projet

### 1) Installer les dépendances (backend)

```bash
cd backend
python -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
```

### 2) Lancer le serveur

#### Option A — En local (mode dev)

```bash
cd backend
source .venv/bin/activate
python app.py
```

Le backend tourne alors sur : **http://localhost:5000**

#### Option B — En Docker (recommandé)

```bash
# Build l'image
docker build -t sesar-task-manager .

# Lancer le conteneur
docker run --rm -p 5000:5000 sesar-task-manager
```

> Ou avec Docker Compose :
>
> ```bash
> docker compose up --build
> ```

### 3) Ouvrir l'interface utilisateur

Ouvre dans ton navigateur :

```
http://localhost:5000
```

## Points importants

- Les tâches sont persistées dans `backend/tasks.json`
- Le frontend appelle les routes :
  - `GET /api/get-tasks`
  - `POST /api/add-task`

---

## Améliorations possibles

- Édition / suppression des tâches
- Authentification + multi-utilisateurs
- Tri par priorité, filtrage par statut
