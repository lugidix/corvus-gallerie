# MASTER — CORVUS × genjutsu (pipeline paint)

Source de vérité du design system de `tests/genjutsu/`. Tout token utilisé dans
`index.html` vient d'ici. Contenu : `tests/contenu-corvus.md` (corpus canonique).

## Thèses (UNVALIDATED — exécution headless)

- **Visuelle :** « Plume de corbeau » — fond bleu-noir profond, texte blanc cassé, un seul
  accent iridescent vert-bleu, espacement ample, composants aux arêtes vives délimités par
  des filets 1px, sans ombres ni élévation.
- **Interaction :** lenteur précise — 250 à 450 ms en ease-out franc, hover discret
  (translation 2 px + luminosité), reveals au scroll en cascade avec stagger 60 ms, une
  seule parallaxe ; interdits : bounce, elastic, boucles décoratives, animation de layout.
- **Allowed patterns :** étiquettes monospace (bornées : étiquettes, transcript, chiffres
  tabulaires — pas la navigation ni le corps), filets hairline (frontières de composants,
  pas d'encadrement de chaque ligne), horloge de veille vivante (heure réelle de la machine).
- **Dials envoyés :** variance 4 (« hiérarchie sobre, tout est frontière ») · motion 6
  (« cascade + stagger + parallaxe ») · density 3 (« ample et respiré »).

## Provenance (dataset ui-ux-pro-max, filtré thèse + tells)

- **Gardé :** fond `#0F172A` (slate profond ≈ plume), stagger 300-450 ms / 60 ms,
  IBM Plex Sans (corps), « éviter le #000 pur ».
- **Rejeté :** glassmorphism, glow, blobs flous, gradients, `back.out(1.4)` (overshoot),
  JetBrains Mono en titres (mono partout), accent `#22C55E`.
- **Tranché ici (amendement de thèse) :** display face = **IBM Plex Sans** 600, la même
  famille que le corps. Raison : le produit parle simplement ; une seule voix humaine,
  la mono reste au langage machine (étiquettes, console, chiffres).

## Couleurs (dark unique — la thèse est nocturne)

| Rôle | Token | Valeur | Contraste sur fond (calculé) |
|---|---|---|---|
| Fond | `--corvus-bg` | `#0F172A` | — |
| Fond relevé (cartes, console) | `--corvus-bg-lift` | `#16203A` | — |
| Fond nuit (console) | `--corvus-bg-night` | `#0A101D` | — |
| Texte | `--corvus-fg` | `#EEF2F6` | 15,87:1 |
| Texte secondaire | `--corvus-fg-soft` | `#A8B3C7` | 8,45:1 |
| Accent (nuque iridescente) | `--corvus-accent` | `#3FD6BE` | 9,84:1 |
| Encre sur accent | `--corvus-ink` | `#06251F` | 8,96:1 (sur accent) |
| Bordure hairline | `--corvus-line` | `#5D6D89` | 3,41:1 |
| Bordure accent | `--corvus-line-accent` | `#3FD6BE` | 9,84:1 |
| Erreur | `--corvus-error` | `#FF8A80` | réservé contenu réel (ex. échec console) |
| Succès | `--corvus-success` | `#7CE3B0` | réservé contenu réel |

Aucun noir pur (`#000000`). Aucune ombre portée : l'élévation est nulle partout.

## Typographie

- **Voix humaine :** IBM Plex Sans — 300 (manifeste), 400 (corps), 600 (titres).
- **Langage machine :** JetBrains Mono — 400/500, réservé aux étiquettes, au transcript
  console et aux chiffres tabulaires.
- Échelle (fluide aux extrêmes) : 12 (étiquette) · 13 (appui) · 17 (corps, interlignage
  1,7, mesure 65-75 caractères) · 20 · 24 · 32 · 48 · 72 · héros `clamp(3rem, 8vw, 5.5rem)`.
- Interlignes : titres 1,1 ; corps 1,7. Aucune capitale espacée hors étiquettes mono.

## Espacements (base 8, density 3 = ample)

`--corvus-s1` 4 · `s2` 8 · `s3` 16 · `s4` 24 · `s5` 40 · `s6` 64 · `s7` 104 · `s8` 160.
Sections : padding vertical `s7` (mobile `s6`). Gouttière de page : 24 px, max 1200 px.

## Rayons, ombres

Rayon unique : **0** (arêtes vives — `--corvus-radius: 0`). Ombres : aucune.

## Composants de base

- **Bouton primaire :** fond accent, texte encre, padding 14/28. États : défaut ;
  hover = translation -2 px + luminosité 1,08 ; focus-visible = contour 2 px fg, offset 3 px ;
  active = translation 0, luminosité 0,95 ; disabled = opacité 0,45, immobile.
- **Bouton fantôme :** filet 1px `line`, texte fg ; hover = filet + texte accent, -2 px.
- **Carte :** filet 1px `line`, fond transparent, padding `s5`. Pas de survol si non cliquable.
- **Lien :** accent, soulignement 1 px offset 4 px ; hover luminosité.
- **Étiquette :** mono 12 px, majuscules, approche 0,14em, couleur `fg-soft` ou accent.
- **Console :** mono 13 px sur `bg-night`, filet 1px, horodatages en `fg-soft`.
- **Stat :** mono tabulaire, valeur `clamp(2.5rem,5vw,4rem)` + légende 13 px.

## Mouvement

- Durées : `--corvus-t-fast` 150 ms (micro) · `--corvus-t-hover` 180 ms ·
  `--corvus-t-med` 300 ms (reveals) · `--corvus-t-slow` 450 ms (héros, grands plans).
- Easing unique : `--corvus-envol` = `cubic-bezier(0.22, 1, 0.36, 1)` (ease-out franc,
  aucun dépassement).
- Stagger : 60 ms. Reveals : opacité + translation Y 16 px, une fois, au scroll
  (IntersectionObserver, seuil 0,15).
- Une parallaxe : l'« escadrille » du héros, translation Y maximale 40 px, `requestAnimationFrame`.
- Interdits (thèse) : bounce, elastic, boucles décoratives, animer width/height/top/left/
  margin/padding. `prefers-reduced-motion` : reveals instantanés, parallaxe coupée,
  horloge conservée (information).
- Z-index : 10 (en-tête) · 20 (élément fixe éventuel). Rien au-delà.

## Contenu

Tout le texte visible provient de `../contenu-corvus.md`. Les tirets cadratins du corpus
sont adaptés en deux-points ou virgules à la mise en page (le cadratin est un tell).
Une seule intention d'action : « Laisser CORVUS veiller » ; contact distinct : « Nous écrire ».
