# 🏁 Piste Drift RC

**Logiciel de conception de pistes de drift RC**, dans un seul fichier HTML, sans installation.
On indique les dimensions de l'espace et la largeur de voie, on dessine la piste d'un trait à la souris (ou au doigt), et le logiciel calcule une piste propre : courbes lissées, niveaux et rampes, vibreurs, barrières, marquages, vue 3D, dossier PDF et maquette imprimable en 3D.

![Version](https://img.shields.io/badge/version-1.31.0-1f2937)
![HTML](https://img.shields.io/badge/HTML%20%2F%20JavaScript-un%20seul%20fichier-e85d04)
![Plateformes](https://img.shields.io/badge/PC-compatible-5f8f4e)
![Échelle](https://img.shields.io/badge/%C3%A9chelle-1%2F10-d62828)

> 📖 Captures d'écran et guide illustré : voir le **Wiki** du dépôt.

---

## Sommaire

- [Démarrage rapide](#démarrage-rapide)
- [Fonctionnalités](#fonctionnalités)
- [Outils et onglets](#outils-et-onglets)
- [Commandes](#commandes)
- [Exports](#exports)
- [Fichier projet](#fichier-projet)
- [Compatibilité](#compatibilité)
- [Structure du dépôt](#structure-du-dépôt)
- [Crédits](#crédits)

---

## Démarrage rapide

1. Télécharger `index.html`.
2. L'ouvrir dans un navigateur récent (Chrome, Edge, Firefox, Safari).
3. Régler l'espace disponible et la largeur de voie dans l'onglet **Piste**, puis dessiner avec l'outil **✏️ Tracer**.

Aucune installation et aucun serveur ne sont nécessaires. Seule la **vue 3D** charge la bibliothèque Three.js depuis un CDN : elle a besoin d'une connexion internet.

**Version en ligne avec GitHub Pages :** *Settings → Pages → Deploy from a branch → `main` / racine*. L'application est ensuite disponible à l'adresse `https://<utilisateur>.github.io/<dépôt>/`, utilisable aussi sur téléphone.

---

## Fonctionnalités

### Tracé et édition
- Tracé à main levée, recalculé en **lignes droites et belles courbes**, avec un lissage réglable (0 à 1).
- **Boucle automatique** quand on termine près du point de départ. Commencer sur une extrémité verte prolonge le tracé, et terminer sur l'extrémité d'un autre tracé raccorde les deux.
- Édition point par point : déplacer, ajouter un point sur la courbe, supprimer. La modification ne touche que la portion concernée.
- Largeur de voie propre à chaque tracé, modifiable après coup.
- Gomme, déplacement de toute la piste, annulation sur 100 niveaux.
- Contrôle du **rayon minimal** : les virages trop serrés sont signalés en rouge.
- **Raccords propres** entre tracés : arrondi de rayon réglable quand un tracé arrive sur un autre.

### Niveaux
- **Niveau 1** à hauteur réglable, peint au pinceau le long de la piste. Le pinceau suit la bonne branche, même à un croisement.
- **Rampes** calculées automatiquement selon l'angle de pente choisi.
- **Pieds** placés automatiquement, jamais sur la piste du dessous. Le logiciel contrôle aussi la hauteur libre au croisement et la portée entre deux pieds.
- Mode **niveau travaillé** : on n'affiche et on ne modifie qu'un niveau, l'autre est protégé. Il peut rester visible en transparence.

### Habillage
- **Barrières pleines** (7,5 cm, échelle 1/10), posées au sol au **pinceau** ou en mode automatique (extérieur des virages, des deux côtés…). Au niveau 1 et sur les rampes, elles sont **obligatoires des deux côtés**.
- **Vibreurs rouges et blancs** posés au **pinceau**, avec réglage de la largeur, de la longueur des bandes et de l'épaisseur. Leur profil est incliné (épaisseur réglée au bord, 1 mm vers l'intérieur), avec des extrémités coupées en biais (30° par défaut) et un biseau arrondi.
- **Marquages blancs** : points de passage numérotés, croix, couloirs d'entrée et de sortie. Chaque entrée est **reliée à sa sortie** par une ligne qui suit la courbe.
- **Couleur du sol** réglable (gazon, béton, moquette, parquet…), visible en 2D et en 3D.

### Visualisation
- Plan 2D quadrillé, avec zoom à la molette ou au pincement.
- **Vue 3D** orbitale : tablier, rampes, pieds, barrières, vibreurs en relief, marquages.

---

## Outils et onglets

La barre d'outils choisit le mode de travail. Seuls les onglets utiles à l'outil choisi sont affichés ; **Fichier** et **Aide** restent toujours visibles.

| Outil | Rôle | Onglets affichés |
|---|---|---|
| ✏️ **Tracer** | Dessiner un nouveau tracé | Piste, Niveaux |
| ✋ **Éditer** | Modifier les points, la largeur, boucler / ouvrir | Édition, Piste, Niveaux |
| **Gomme** | Supprimer une portion | Édition |
| ⛰️ **Niveau** | Peindre une portion au niveau 0 ou 1 | Niveaux, Édition |
| ✥ **Déplacer** | Déplacer toute la piste | Piste |
| 🚧 **Barrières** | Peindre le masque des barrières du sol | Barrières, Édition |
| 🟥 **Vibreurs** | Peindre le masque des vibreurs | Vibreurs, Édition |
| ◯ **Marquage** | Poser des points, croix et couloirs | Marquage, Édition |

---

## Commandes

| Action | Souris / clavier | Téléphone / tablette |
|---|---|---|
| Zoom | Molette | Pincement à deux doigts |
| Déplacer la vue | Bouton du milieu | Glisser à deux doigts |
| Supprimer (point, marquage, vibreur, barrière) | Clic droit ou `Suppr` | Appui long |
| Changer le niveau du point sélectionné | `0` / `1` | Boutons de l'onglet Édition |
| Tourner un marquage | `R` | Boutons ⟲ ⟳ |
| Annuler | `Ctrl+Z` | Bouton Annuler |
| Vue 3D | Glisser = tourner, molette = zoom, clic droit = déplacer | Un doigt = tourner, deux doigts = zoom |

Sur téléphone, le bouton **☰ Menu** replie le panneau pour agrandir le plan.

---

## Exports

Tout se trouve dans l'onglet **Fichier**.

| Export | Contenu |
|---|---|
| **Projet `.json`** | Enregistrer et rouvrir la piste. Une sauvegarde automatique est faite aussi dans le navigateur. |
| **Dossier PDF** (A4 ou A3 paysage, 4 pages) | Vue 2D cotée, vue 3D, quadrillage avec repères numérotés pour reporter la piste au sol, résumé complet (dimensions, niveaux, pieds, barrières, vibreurs, marquages, maquette). |
| **Maquette `.3mf`** | Une seule pièce, **20 cm maximum**, prête pour Bambu Studio et les autres slicers. Les pieds, barrières et épaisseurs gardent une taille minimale imprimable. Les vibreurs et marquages ne sont pas inclus. |

---

## Fichier projet

Le projet est un fichier JSON lisible (version de format 3) :

```json
{
  "app": "piste-drift-rc",
  "version": 3,
  "appVersion": "1.31.0",
  "params": { "espL": "12", "espW": "8", "voie": "1.2", "h2": "0.25", "pente": "10", "solCol": "#5f8f4e" },
  "strokes": [ { "ctrl": [{ "x": 2.1, "y": 3.4 }], "lev": [0], "w": 1.2, "closed": true } ],
  "marks":  [ { "type": "in", "x": 5.2, "y": 1.1, "rot": 0, "len": 1, "wid": 0.6, "label": "Entrée" } ],
  "kerbs":  [ { "x": 6.0, "y": 2.0, "r": 0.3, "lv": "all", "neg": false } ],
  "rails":  [ { "x": 6.0, "y": 2.0, "r": 0.3, "lv": "0", "neg": false } ]
}
```

- `strokes` : tracés. `ctrl` contient les points de contrôle en mètres, `lev` le niveau de chaque point (0 = sol, 1 = niveau 1 en hauteur), `w` la largeur de voie et `closed` indique si le tracé est bouclé.
- `kerbs` / `rails` : masques peints. Ce sont des tampons ronds ; `neg` vaut `true` pour un coup de gomme.
- Les projets des anciennes versions sont convertis automatiquement à l'ouverture.

---

## Compatibilité

- **PC** : Chrome, Edge, Firefox, Safari (versions récentes).
- **iPhone / iPad et Android** : interface adaptée, avec le menu en haut, une barre d'outils défilante, le zoom au pincement et l'appui long.
- **Hors ligne** : tout fonctionne sauf la vue 3D, qui a besoin de Three.js depuis le CDN jsDelivr.

---

## Structure du dépôt

```
.
├── index.html        # l'application complète (HTML + CSS + JavaScript)
└── README.md
```

---

## Crédits

- Idée, conception et essais : **Vince**
- Avec le club **RC DRIVERS 50**
- Vue 3D : [Three.js](https://threejs.org/)
