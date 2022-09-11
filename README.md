# Symfony-X-React
 
# Mise en place du projet (effectué)

> symfony composer req symfony/webpack-encore-bundle

supprimmer les fichiers et dossiers du dossier assets et créer à l’intérieur de celui ci un dossier react et un dossier styles
A l’intérieur du dossier react créer un fichier index.js
A l’intérieur du dossier styles creer un fichier styles.scss

Modification de la configuration dans le fichier webpack.config.js

Supprimer :

.enableStimulusBridge(‘./assets/controllers.json’)

Décommenter : 

.enableSassLoader()
.enableReactPreset()

Ajouter dans la partie Encore : 

.addEntry(‘app’, ‘./assets/react/index.js’)            (changement du chemin)
.addStyleEntry(‘styles’, ‘./assets/styles/styles.scss’)          (ligne ajouté)
 

Dans le fichier templates\base.html.twig changer le nom de fichier css appelé:

{{ encore_entry_link_tags(‘styles’) }}



> npm install --force
> npm run build  permet de voir les packages manquants et a chaque erreur faire un copier coller des package a installer et les installer depuis la console

> npm install @babel/preset-react@^7.0.0 --save-dev
> npm install sass-loader@^13.0.0 sass --save-dev

# Intégration de react (effecué)

> npm i react react-dom

> npm run watch 

Dans le fichier templates\base.html.twig à l’intérieur du body

<div id=»app»><div>

Dans le fichier assets\react\index.js

import React from «react»;
import App from «./component/app»;
import {createRoot }from ‘react-dom/client’;

const container = document.getElementById(‘app’);
const root = createRoot(container)

root.render(
    <React.StrictMode>
        <App />
    </React.StrictMode>
);

Dans le dossier react créer le dossier components et le fichier app.jsx

