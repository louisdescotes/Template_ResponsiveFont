# Template de fichier responsif pour vos Titres et Paragraphes

Ce template permet de ne plus gérer la taille des fonts sur vos sites internet (du responsif en moins à faire !)

## Comment ça marche ?

### 5 variables importantes

#### `--size-unit`
Permet de définir la taille principale du document. Par défaut : `16px` (ici 16px aussi, on ne change pas).

#### `--size-container-ideal`
Largeur idéale du conteneur selon le design. Exemple : `1440px` (wireframe Figma).

#### `--size-container-min`
La largeur minimale que le conteneur peut avoir dans l'affichage responsive.

#### `--size-container-max`
La largeur maximale que le conteneur peut atteindre dans l'affichage responsive.

#### `--size-container`
Garanti que la valeur calculée reste entre les bornes minimale et maximale, mais peut s’adapter dynamiquement en fonction de la largeur de l’écran.

#### `--size-font`
Calculée dynamiquement en divisant la largeur idéale du conteneur (`--size-container-ideal`) par la taille de base du texte (`--size-unit`). Cette proportion est ensuite multipliée par la largeur actuelle du conteneur (`--size-container`) pour ajuster automatiquement la taille des textes.

```css
:root {
  --size-unit: 16px;
  --size-container-ideal: 1440px;
  --size-container-min: 320px;
  --size-container-max: 1920px;
  --size-container: clamp(var(--size-container-min), 100vw, var(--size-container-max));
  --size-font: calc(var(--size-container) / (var(--size-container-ideal) / var(--size-unit)));
}

body {
  font-size: var(--size-font);
}
```

### Les media queries

Il ne reste plus qu'à élaborer des media queries pour ajuster dynamiquement les variables suivantes :

- `--size-container-ideal`
- `--size-container-min`
- `--size-container-max`

Voici un exemple :

```css
@media (max-width: 768px) {
  :root {
    --size-container-ideal: 1024px;
    --size-container-min: 320px;
    --size-container-max: 1280px;
  }
}

@media (max-width: 480px) {
  :root {
    --size-container-ideal: 768px;
    --size-container-min: 320px;
    --size-container-max: 1024px;
  }
}
