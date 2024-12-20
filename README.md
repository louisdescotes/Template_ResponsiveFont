# Template de fichier responsif pour vos Titres et Paragraphes
Ce template permet de ne plus gérer la taille des fonts sur vos sites internet (du responsif en moins à faire !) 

# Comment ça marche ? 
 
## 5 variables importantes 
### --size-unit
Permet de définir la size principal du document, de base de 16px (ici 16px aussi on ne change pas) 
 
### --size-container-ideal 
Ici on définit la largeur idéale du conteneur selon le design (ici 1440px, wireframe figma) 
 
### --size-container-min
La largeur minimale que le conteneur peut avoir dans l'affichage responsive 
 
### --size-container-max 
La largeur maximale que le conteneur peut atteindre dans l'affichage responsive 

### --size-container 
garantit que la valeur calculée reste entre les bornes minimale et maximale, mais peut s’adapter en fonction de la largeur de l’écran 

### --size-font
Divise la largeur idéale du conteneur (--size-container-ideal) par la taille de base du texte (--size-unit), obtenant ainsi une relation proportionnelle entre la largeur et la taille du texte. 
Multiplie cette proportion par la largeur actuelle du conteneur (--size-container) pour ajuster dynamiquement la taille du texte. 

## Les médias queries 
Il ne nous reste plus qu'a élaborer des medias queries afin de changer seulement : 
--size-container-ideal 
--size-container-min 
--size-container-max 