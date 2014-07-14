# Pourquoi utiliser jirac ?
Les développements et les tests vont de paires dans le processus de construction de logiciels de qualité.
Pour cela les devs et les testeurs doivent travailler de concert pour être le plus efficace possible.   
Cela passe par une bonne communication. Ainsi, des outils existent pour faciliter à la fois les communications
mais aussi les workflows.  
[Jira](https://www.atlassian.com/software/jira/#!) est un outil permettant cela. Néanmoins, aussi bon que soit l'outil, il ne pourra pas palier à certaines carences comme le manque d'informations utiles dans un commentaire (ou a contrario le surplus).  
Le problème ce situe comme bien souvent entre la chaise et le clavier.  
Ceci est particulièrement prégnant lors de la correction d'un bug ou du développement d'une feature.

**Le scénario est le suivant**:  
Un bug est remonté au testeur. Le testeur s'occupe de créer un ticket idoine (via jira par exemple) et l'affecte à un développeur. 
Le développeur, en retour, traite le ticket et le retourne à l'envoyeur.  
En toute bonne logique il faudrait que le ticket soit commenté pour fournir des informationsi telle que le changeset (sha1), la branche de commit, 
la version concernée de l'application, le contexte de la correction...  
Ainsi le testeur serait tout de suite en mesure de tester le développement. 
Aucune perte de temps induit par des interrogations.  

Dans les fait, cela n'arrive pas. En général **chacun met le degré d'information qu'il souhaite**. De plus, les formats seront de toute manière trop hétérogènes pour permettre une lecture efficace. 

**Jirac propose d'apporter une solution à ce problème en automatisant la génération de commentaire pour un ticket donné**.  
En *fournissant* les commits concernés par l'évolution  ou la correction, jirac produira en sorti un commentaire formatté apportant le juste niveau d'information au testeur pour qu'il puisse traiter le ticket efficacement.
