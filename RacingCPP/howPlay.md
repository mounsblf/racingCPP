# Comment Utiliser CPP Kart

CPP Kart est un jeu de course 3D développé avec C++, OpenGL, SDL2 et Bullet Physics. Ce guide vous aidera à configurer, compiler et jouer au jeu.

## Table des Matières
- [Prérequis](#prérequis)
- [Installation](#installation)
- [Compilation du Jeu](#compilation-du-jeu)
- [Lancer le Jeu](#lancer-le-jeu)
- [Contrôles du Jeu](#contrôles-du-jeu)
- [Fonctionnalités du Jeu](#fonctionnalités-du-jeu)
- [Résolution de Problèmes](#résolution-de-problèmes)
- [Développement](#développement)

## Prérequis

### Configuration Système Requise
- **Système d'Exploitation**: Linux (distributions basées sur Debian comme Ubuntu recommandées)
- **Compilateur**: GCC avec support C++17
- **Graphiques**: Carte graphique compatible OpenGL 3.3+
- **Audio**: Support audio SDL2

### Dépendances Requises
Vous devez installer les paquets suivants avant de compiler le jeu :

#### Outils de Développement Essentiels
```bash
sudo apt install build-essential cmake
```

#### Graphiques et Gestion de Fenêtres
```bash
sudo apt install libsdl2-dev libgl-dev mesa-utils
```

#### Chargement de Modèles 3D
```bash
sudo apt install assimp-utils libassimp-dev libassimp5
```

#### Moteur Physique (Bullet3 via VCPKG)
Installer le gestionnaire de paquets VCPKG et Bullet3 :
```bash
git clone https://github.com/microsoft/vcpkg.git
cd vcpkg
./bootstrap-vcpkg.sh
./vcpkg integrate install
./vcpkg install bullet3
```

## Installation

1. **Cloner ou Télécharger le Projet**
   ```bash
   git clone [url-du-dépôt]  # Remplacer par l'URL réelle du dépôt
   cd 3dgame/cppkart
   ```

2. **Rendre les Scripts de Compilation Exécutables**
   ```bash
   chmod +x build_and_run.sh
   chmod +x DC_full_rebuild.sh
   chmod +x full_rebuild.sh
   ```

## Compilation du Jeu

### Recompilation Complète et Propre
Pour une compilation complète et propre (supprime les fichiers de compilation précédents) :
```bash
./DC_full_rebuild.sh
```

## Lancer le Jeu

Après une compilation réussie, vous pouvez lancer le jeu de plusieurs façons :

1. **Depuis le répertoire build :**
   ```bash
   cd build
   ./cppkart
   ```

2. **En utilisant le script de compilation :**
   ```bash
   ./build_and_run.sh
   ```

## Contrôles du Jeu

### Contrôles du Véhicule
- **Mouvement**: Utilisez les flèches du clavier ou WASD pour la direction et l'accélération
- **Frein/Marche arrière**: Utilisez la touche appropriée (généralement flèche vers le bas ou S)
- **Caméra**: Le mouvement de la souris contrôle l'angle de la caméra
- **Réinitialiser la vue**: Appuyez sur la touche appropriée pour réinitialiser la position de la caméra

### Contrôles de Débogage
- **Interface ImGui**: Le jeu dispose d'une interface de débogage pour l'ajustement des paramètres en temps réel
- **Affichage Debug Physique**: Basculer la visualisation physique pour déboguer les collisions
- **Modes de Caméra**: Basculer entre le suivi du véhicule joueur et la caméra libre

### Contrôles Généraux
- **ESC**: Quitter le jeu
- **Souris**: Contrôle de la caméra et interaction avec les menus
- **Support Manette**: Support joystick/manette de jeu disponible

## Fonctionnalités du Jeu

### Gameplay Principal
- **Course de Kart 3D**: Conduisez des véhicules dans un environnement 3D avec une physique réaliste
- **Physique Véhicule**: Propulsé par le moteur physique Bullet Physics pour un maniement de voiture réaliste
- **Adversaires IA**: Véhicules contrôlés par IA qui suivent des chemins spline
- **Système de Terrain**: Plusieurs cartes incluant une île carrée et des collines de haute route
- **Détection de Collision**: Système de collision avancé avec effets sonores

### Fonctionnalités Techniques
- **Rendu OpenGL Moderne**: Graphiques 3D accélérés par matériel
- **Système Entité-Composant**: Architecture de jeu modulaire
- **Simulation Physique**: Physique Bullet3 pour véhicules et environnement
- **Chargement d'Assets**: Support pour modèles 3D via Assimp
- **Système Audio**: SDL2 Mixer pour effets sonores
- **Interface de Débogage**: Outils de débogage en temps réel basés sur ImGui

### Cartes/Scènes Disponibles
- **Île Carrée**: Un environnement d'île contenu parfait pour la course
- **Collines de Haute Route**: Terrain élevé avec des tracés de route difficiles

### Types de Véhicules
- **Dale Aristocrat (1997)**: Modèle de voiture de course rétro style PS1
- **Contrôles Basés sur la Physique**: Direction, accélération et freinage réalistes

## Résolution de Problèmes

### Problèmes de Compilation

**Échec de Configuration CMake :**
- Assurez-vous que toutes les dépendances sont installées
- Vérifiez que le chemin VCPKG est correct dans les scripts de compilation
- Vérifiez la version CMake (3.10+ recommandée)

**Erreurs de Compilation :**
- Mettez à jour votre compilateur pour supporter C++17
- Installez les en-têtes de développement manquants
- Vérifiez que les pilotes graphiques sont correctement installés

**Problèmes VCPKG :**
- Assurez-vous que VCPKG est correctement initialisé
- Vérifiez que le paquet Bullet3 a été installé avec succès
- Mettez à jour le chemin du fichier toolchain VCPKG dans les scripts de compilation

### Problèmes d'Exécution

**Le Jeu ne Démarre Pas :**
- Vérifiez que les pilotes OpenGL sont installés et à jour
- Assurez-vous que le système audio fonctionne (ALSA/PulseAudio)
- Vérifiez que tous les assets sont présents dans le répertoire `assets/`

**Problèmes de Performance :**
- Baissez les paramètres graphiques si disponibles
- Assurez-vous que les pilotes graphiques sont optimisés
- Fermez les applications inutiles en arrière-plan

**Pas de Son :**
- Installez les paquets de développement SDL2 mixer
- Vérifiez la configuration audio du système
- Vérifiez que les fichiers sonores sont présents et accessibles

### Problèmes Graphiques

**Écran Noir ou Pas de Rendu :**
- Mettez à jour les pilotes graphiques
- Vérifiez la compatibilité de la version OpenGL
- Vérifiez la création de fenêtre et la configuration du contexte

**Faible Fréquence d'Images :**
- Vérifiez les paramètres graphiques dans l'interface de débogage
- Surveillez les ressources système
- Considérez les limitations matérielles

## Développement

### Structure du Projet
```
cppkart/
├── src/                    # Code source
│   ├── game/              # Code spécifique au jeu
│   ├── jx_engine/         # Moteur de jeu personnalisé
│   ├── core/              # Systèmes centraux du moteur
│   └── main.cpp           # Point d'entrée
├── assets/                # Assets du jeu (modèles, textures, sons)
├── build/                 # Répertoire de compilation (généré)
├── CMakeLists.txt        # Configuration de compilation
└── *.sh                  # Scripts de compilation
```

### Composants Clés
- **DemoGame**: Classe de jeu principale gérant la boucle de jeu
- **GameScene**: Scène principale contenant l'environnement de course
- **ECManager**: Gestionnaire du système entité-composant
- **PhysicsWorldSingleton**: Gestion du monde physique Bullet
- **GameGLRenderer**: Système de rendu OpenGL

### Modifier le Jeu
- **Ajouter des Modèles**: Placez les modèles 3D dans les sous-répertoires `assets/` appropriés
- **Changer la Physique**: Modifiez les paramètres physiques dans les composants véhicule
- **Nouvelles Cartes**: Créez de nouveaux chunks de terrain et chargez-les dans GameScene
- **Contrôles**: Modifiez la gestion des entrées dans la classe GameInput

### Fonctionnalités de Débogage
Le jeu inclut des capacités de débogage étendues :
- Visualisation physique en temps réel
- Surveillance des performances
- Inspection entité-composant
- Options de contrôle de caméra

## Crédits

Ce projet utilise plusieurs assets open-source :
- **Modèle Dale Aristocrat (1997)** par *Aike* ([Sketchfab](https://sketchfab.com/3d-models/ps1-gt1-style-model-1997-dale-aristocrat-e4cf08baa46548e58e96413663daffee))
- **Skybox Icescape 1 Alien Moon** par *Luis Vidal* ([Sketchfab](https://sketchfab.com/3d-models/icescape-1-alien-moon-skybox-bfc9a041814f4112b016904edfaad0c5))

## Support

Pour les problèmes et questions :
1. Consultez d'abord ce guide
2. Consultez le `readme.md` existant pour les détails techniques
3. Vérifiez la sortie de la console de débogage pour les messages d'erreur
4. Assurez-vous que toutes les dépendances sont correctement installées

---

*Bonne Course ! 🏁* 