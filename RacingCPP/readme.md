# Racing CPP| 


## Configuration :




### Configuration pour Linux basé sur Debian : *(Debian, Ubuntu)*

1. Installations essentielles pour C/C++ & CMake : <br/>
`sudo apt install build-essential cmake`

2. Installation de la Bibliothèque de Développement SDL : <br/>
`sudo apt install libsdl2-dev`

3. Installation du Chargeur Assimp & Utilitaires : (Chargeur de Modèles) <br/>
`sudo apt install assimp-utils libassimp-dev libassimp5`

4. Installer Bullet Physics depuis VCPKG *(Car la dernière version d'Apt de bullet n'est pas bullet3, et 2.7 a quelques problèmes lol)*

**Installer VCPKG, puis Bullet3**

```sh
git clone https://github.com/microsoft/vcpkg.git
cd vcpkg
./bootstrap-vcpkg.sh
./vcpkg integrate install
./vcpkg install bullet3
```

*La Distribution OpenGL vient nativement avec Kubuntu & Debian-Bookworm, si vous ne l'avez pas, veuillez installer... *

Essayez : `sudo apt install libgl-dev mesa-utils` ?


### CMake & Compilation de l'Exécutable :

1. Préliminaire, pour la compilation initiale : <br/>
`mkdir build && cd build`

2. Exécuter CMake, puis Make pour la compilation de l'exécutable : <br/>
`cmake ..` <br/>
`make`

3. L'exécuter :
`./cppkart`

<br/>

---


**Astuce :** dans le répertoire principal (cppkart) vous pouvez simplement exécuter `./DC_full_rebuild.sh` et il supprime automatiquement et re-CMake et Make le projet.

---

### Quelques Docs Utiles que je garde sous la main...

Dear ImGUI [Exemple](https://github.com/ocornut/imgui/wiki/Getting-Started#example-if-you-are-using-sdl2--openglwebgl) 
<br/>
Dear ImGUI | [Commencer](https://github.com/ocornut/imgui/wiki/Getting-Started)
<br/>
J'ai suivi pour le code source SDL2 et OpenGL3+ : [example_sdl2_opengl3/main.cpp](https://github.com/ocornut/imgui/blob/master/examples/example_sdl2_opengl3/main.cpp) 


---

Dans l'esprit open source, tout Asset que j'utilise, je lie les Téléchargements, et crédite les Artistes pour leur Travail Génial sur le Modèle ! 🏁🔥

**1997 Dale Aristocrat (Modèle Style PS1)** PAR *Aike*

[Lien sketchfab.com](https://sketchfab.com/3d-models/ps1-gt1-style-model-1997-dale-aristocrat-e4cf08baa46548e58e96413663daffee)

**Icescape 1 Alien Moon Skybox** PAR *Luis Vidal*

[LIEN sketchfab.com](https://sketchfab.com/3d-models/icescape-1-alien-moon-skybox-bfc9a041814f4112b016904edfaad0c5)
