# Usage
 Cette partie décrit les usages courants que l'on peut avoir avec jirac.

## jirac
Le cas d'usage classique est de simplement lancer la commande 'jirac' depuis un *projet git+maven*.  
Il est à noter que la commande ne se lance pas nécessairement depuis le répertoire racine d'un projet mais peut tout aussi être invoqué depuis 
n'importe quels sous-répertoires.  
L'éditeur de votre choix s'ouvrira par défaut avec les dix dernier commits que vous avez pushés.  
Pour spécifier à jirac les commits que vous souhaitez intégrer dans votre commentaire, il faut précéder les sha1 d'un caractère **x **.
Vous ne pouvez sortir de ce mode sans avoir choisi au moins un commit.  

Une fois les commits choisis vous aurez la possibilité de surcharger la ou les descriptions (selon que vous aurez selectionné plusieurs commits).  
Par défaut elles correspondent à l'intitulé du commit ainsi que sa description.
La surcharge permet de les remplacer par un texte unique.  
Peut être utile selon les cas.

La fin de la génération du commentaire jirac sera notifié par l'apparition d'un ASCII art.  
Le commentaire sera automatiquement dans le presse papier, évitant par là même de faire un copier/coller.
**Vous être prêt pour coller le commentaire dans le ticket idoine.**

PS: La syntaxe est celle du markdown utilisée dans jira.

## jirac -n [number_of_commit]
Il est courant de ne finalement générer un commentaire qu'à partir du dernier commit voire des deux ou trois dernier.  
Dans ce contexte, il est fastidieux de devoir selectionner manuellement les sha1 des commits.  
C'est pour ce cas de figure que l'option **--number** existe.  
Elle permet de spécifier les n dernier commits que l'on souhaite incorporer dans le commentaire.


## jirac -s
Pour éviter un excès de verbosité, une option **--silent** existe.   
Enclenchée elle ocultera l'ensemble des messages de logs ainsi que autres banières et ASCII art.

## jirac -g
En général, les titres de commit (short description) contiennent un numéro de tickets, pour permettre de rapidement les associer lors d'une revue d'historique de branche.   
On peut se servir de cela via l'option **--grep** qui prendra en paramètre une regexp.  
Pour générer un commentaire à partir des commits lié au *ticket_foo* on lancera la commande:   
*jira -g 'ticket_foo'*

Tous les commits contenant *ticket_foo* dans leur short description seront alors utilisés pour générer le commentaire.

## jirac -p [0|1]
L'option **--print_mode** permet de modifier la partie déscription du commentaire généré.
Les commentaires suivant sont générés à partir de trois même commits.  
### Mode par défaut `jirac -p 0`
*fooProject*
* branche   : origin/grep
* version   : 1.0-SNAPSHOT
* commit(s) :
** http://somerepository.com/svn_repo/trunk/commit/83e9751c78d9d52bc1d1ec79e1d75f321ef05907**
** http://somerepository.com/svn_repo/trunk/commit/5c6337a7eb18033d57184b8cd5d484c8d79c06f4**
** http://somerepository.com/svn_repo/trunk/commit/0b8b1e91177a1d064637504474e23733a7077199**
* Description:
Added new grep option  
Shift parameter for print_mode \\  
\\
Previouly we didn't shit the value of print_mode option.
Thus, we couldn't add option following the print_mode
User with no pushed commit cannot generate comment \\  
\\
Previously, when someone tried to generate comments while he
didn't have pushed commit he was redirected on the EDITOR with
no commit to choose. A stalemate. \\  
\\
Now we prevent this by controling the existence of commits of his. \\

### Mode centré sur le commit `jirac -p 1`
*fooProject*
* branche   : origin/grep
* version   : 1.0-SNAPSHOT
* User with no pushed commit cannot generate comment
** http://somerepository.com/svn_repo/trunk/commit/0b8b1e91177a1d064637504474e23733a7077199**
Previously, when someone tried to generate comments while he
didn't have pushed commit he was redirected on the EDITOR with
no commit to choose. A stalemate. \\
\\
Now we prevent this by controling the existence of commits of his.
* Shift parameter for print_mode
** http://somerepository.com/svn_repo/trunk/commit/5c6337a7eb18033d57184b8cd5d484c8d79c06f4**
Previouly we didn't shit the value of print_mode option.
Thus, we couldn't add option following the print_mode
* Added new grep option
** http://somerepository.com/svn_repo/trunk/commit/83e9751c78d9d52bc1d1ec79e1d75f321ef05907**

