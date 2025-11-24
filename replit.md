# MODELS ACADEMY MANAGEMENT

Site web moderne et professionnel pour une agence de mannequins spécialisée dans la formation.

## Description du Projet

Site web complet développé en HTML, CSS et JavaScript vanilla pour MODELS ACADEMY MANAGEMENT. Le site présente une agence de formation de mannequins avec trois spécialités :
- Formation Mannequin Podium
- Formation Model Photo
- Formation Management

## Structure du Site

### Pages Principales

1. **index.html** - Page d'accueil
   - Section hero plein écran
   - Présentation de l'agence
   - Statistiques animées (mannequins formés, défilés, projets photos, années d'expérience)
   - Aperçu des 3 formations
   - FAQ interactive avec accordéon
   - Call-to-action pour l'inscription

2. **about.html** - À propos
   - Histoire et objectifs de l'agence
   - Valeurs de l'entreprise (4 piliers)
   - Vidéo de présentation (YouTube embed)
   - Galerie de 12 images responsive
   - Équipe de 2 personnes avec liens sociaux
   - Section blog avec 3 articles

3. **formations.html** - Formations
   - Détails complets des 3 formations :
     * Mannequin Podium (2 500 €, 4 mois)
     * Model Photo (2 000 €, 3 mois)
     * Management (3 500 €, 6 mois)
   - Pour chaque formation : objectifs, programme, durée, conditions, prix

4. **mannequins.html** - Nos mannequins
   - Liste de 6 mannequins en cartes
   - Navigation vers les profils individuels

5. **model-detail.html** - Profil mannequin dynamique
   - Données complètes pour 6 mannequins (Emma, Sophie, Léa, Clara, Marie, Julie)
   - Navigation par paramètre URL (?id=1-6)
   - Mensurations détaillées
   - Polaroids et portfolio
   - Expérience professionnelle

6. **inscription.html** - Formulaire d'inscription
   - Processus en 4 étapes :
     * Étape 1 : Informations personnelles
     * Étape 2 : Expérience et motivation
     * Étape 3 : Mensurations
     * Étape 4 : Upload de photos et validation
   - Navigation fluide entre les étapes
   - Validation des champs obligatoires

7. **contact.html** - Contact
   - Formulaire de contact
   - Coordonnées complètes (téléphone, email, WhatsApp, Instagram)
   - Localisation Google Maps
   - Horaires d'ouverture

### Fichiers CSS

- **styles.css** - Styles globaux
  - Header et footer constants
  - Design responsive mobile-first
  - Animations et transitions
  - Variables CSS pour la palette de couleurs
  - Media queries pour tous les écrans

- **inscription.css** - Styles du formulaire d'inscription
  - Barre de progression des étapes
  - Grille de formulaire responsive
  - Zones d'upload d'images
  - Animations des transitions

### Fichiers JavaScript

- **main.js** - Fonctionnalités globales
  - Menu mobile (hamburger)
  - Compteurs animés avec Intersection Observer
  - Accordéon FAQ
  - Marquage du lien actif dans la navigation
  - Effet de scroll sur le header

- **inscription.js** - Formulaire multi-étapes
  - Navigation entre les 4 étapes
  - Validation des champs obligatoires
  - Prévisualisation des images uploadées
  - Soumission du formulaire

- **model-detail.html (inline JS)** - Profils dynamiques
  - Base de données des 6 mannequins
  - Chargement dynamique via URL parameters
  - Mise à jour du DOM avec les données du mannequin

### Serveur

- **server.py** - Serveur HTTP Python
  - Port 5000 avec binding 0.0.0.0
  - Headers de cache désactivés
  - Réutilisation d'adresse (allow_reuse_address)
  - Redirection automatique / vers /index.html

## Technologies Utilisées

- **HTML5** - Structure sémantique
- **CSS3** - Flexbox, Grid, animations, media queries
- **JavaScript ES6+** - Vanilla JS sans frameworks
- **Boxicons** - Bibliothèque d'icônes (CDN)
- **Google Fonts** - Police Poppins
- **Python 3.11** - Serveur HTTP simple

## Fonctionnalités

### Design & UX
- Design moderne inspiré du style Fash Link
- Palette de couleurs élégante (noir, or, blanc)
- Responsive mobile-first
- Animations légères et transitions fluides
- Navigation intuitive

### Interactivité
- Compteurs animés déclenchés au scroll
- FAQ avec accordéon
- Menu mobile hamburger
- Formulaire multi-étapes avec validation
- Navigation dynamique entre profils de mannequins
- Prévisualisation d'images

### Optimisations
- Cache désactivé pour le développement
- Images optimisées depuis Unsplash
- Code modulaire et maintenable
- Variables CSS pour faciliter la personnalisation

## Lancement du Projet

Le serveur HTTP démarre automatiquement via le workflow "Start Web Server" :
```bash
python3 server.py
```

Le site est accessible sur : http://0.0.0.0:5000/

## Structure des Fichiers

```
/
├── index.html              # Page d'accueil
├── about.html             # À propos
├── formations.html        # Formations
├── mannequins.html        # Liste mannequins
├── model-detail.html      # Profil mannequin (dynamique)
├── inscription.html       # Formulaire 4 étapes
├── contact.html           # Contact
├── styles.css             # CSS global
├── inscription.css        # CSS formulaire
├── main.js               # JavaScript global
├── inscription.js        # JavaScript formulaire
├── server.py             # Serveur HTTP
└── replit.md             # Documentation
```

## Ajout de Nouveaux Mannequins

Pour ajouter un nouveau mannequin :

1. Dans **mannequins.html**, ajouter une nouvelle carte :
```html
<div class="model-card" onclick="window.location.href='model-detail.html?id=7'">
    <!-- Contenu de la carte -->
</div>
```

2. Dans **model-detail.html**, ajouter les données dans l'objet `models` :
```javascript
'7': {
    name: 'Nouveau Nom',
    specialty: 'Podium/Photo/Mixte',
    photo: 'url_image',
    height: '1m75',
    // ... autres données
}
```

## Personnalisation

Les couleurs principales sont définies dans `styles.css` via des variables CSS :
```css
:root {
    --primary-color: #000000;    /* Noir */
    --accent-color: #d4af37;     /* Or */
    --secondary-color: #f5f5f5;  /* Gris clair */
}
```

## Date de Création

Novembre 2024

## Notes Techniques

- Le serveur utilise `allow_reuse_address` pour permettre les redémarrages rapides
- Les images proviennent d'Unsplash (à remplacer par de vraies photos en production)
- Le formulaire d'inscription est actuellement front-end only (ajouter un backend pour le traitement réel)
- La vidéo Instagram peut être remplacée par un vrai embed
