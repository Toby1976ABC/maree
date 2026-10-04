# Marée

Prévisions de touche pour la mer, les lacs et les rivières, en France et au Royaume-Uni.
Application web mobile (PWA) : elle s'installe sur l'écran d'accueil d'un téléphone et s'ouvre en plein écran, comme une app.

## Fonctions

- **Prévisions** : indice de touche heure par heure sur 7 jours, meilleur créneau, préparation de sortie par espèce (profondeur, technique, leurres, couleur, animation), conditions détaillées, lune, soleil et marées.
- **Carte** : prévisions n'importe où d'un simple toucher, couches satellite, profondeur, balisage, température de la mer, chlorophylle et vent en direct.
- **Espèces** : saisons, meilleurs moments, eau idéale et profondeur selon la température.
- **Carnet** : prises enregistrées avec leurs conditions, ce qui marche pour vous, export CSV. Les données restent dans le navigateur de l'appareil.

## Mettre en ligne avec GitHub Pages

1. Créez un dépôt sur GitHub (par exemple `maree`) et poussez-y le contenu de ce dossier :
   ```bash
   git init
   git add .
   git commit -m "Marée : première version"
   git branch -M main
   git remote add origin https://github.com/<votre-compte>/maree.git
   git push -u origin main
   ```
2. Sur GitHub : **Settings › Pages › Build and deployment › Source : GitHub Actions**.
3. Le workflow `.github/workflows/pages.yml` publie le site à chaque push sur `main`.
   L'adresse s'affiche dans l'onglet **Actions** : `https://<votre-compte>.github.io/maree/`.

## Installer sur le téléphone

- **iPhone (Safari)** : bouton Partager › *Sur l'écran d'accueil*.
- **Android (Chrome)** : menu ⋮ › *Installer l'application*.

## Tester en local

```bash
python3 -m http.server 8000
# puis ouvrir http://localhost:8000
```

## Structure

```
index.html              application complète (HTML, CSS, JS)
manifest.webmanifest    nom, couleurs et icônes de l'app installée
sw.js                   service worker : interface disponible hors ligne
icons/                  icônes de l'app (SVG et PNG)
.github/workflows/      déploiement automatique sur GitHub Pages
```

## Données

Open-Meteo (météo, mer, débits), OpenStreetMap, OpenSeaMap, EMODnet Bathymetry, NASA GIBS, Esri.
Les hauteurs de marée et les températures des lacs et rivières sont des estimations : utilisez les annuaires officiels (SHOM) pour naviguer.
Vérifiez toujours permis, tailles minimales et périodes de fermeture.
