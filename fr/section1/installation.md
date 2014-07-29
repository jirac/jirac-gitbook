# Installation

## Dépendances
Assurez-vous d'avoir :  

1. installé Git (avec Git Bash sous Windows) 
1. installé XMLStarlet dont vous trouverez une tarball sur ce [lien](http://xmlstar.sourceforge.net/download.php) ou via votre package manager.
1. cloné ce  [repo](https://github.com/jirac/jirac "jirac repository") et inclus le répertoire dans votre `PATH`
1. définit une variable d'environnement `VISUAL` ou `EDITOR` (ex: "vim")

### Utilisateurs Linux
Assurez-vous d'installer:  
* `xclip` package

### Utilisateurs Windows 
Assurez-vous d'installer:  
* [mktemp](http://gnuwin32.sourceforge.net/packages/mktemp.htm) et d'inclure son répertoire `bin` dans votre `PATH`.

### Utilisateurs Mac 
Assurez-vous d'installer:  
* `pbcopy`

### Note sur l'éditeur
Si vous prévoyez d'exporter un éditeur graphique (tels que gedit, Sublime Text...) vous devriez déjà savoir que **VOUS DEVEZ** spécifier des options ("-w -s" pour gedit, "-n -w" pour Sublime) dans l'export de l'éditeur pour que ce dernier **BLOQUE** le script appelant.  

Par ailleurs, **n'oubliez pas d'échapper les espaces du path avant de l'exporter!**
