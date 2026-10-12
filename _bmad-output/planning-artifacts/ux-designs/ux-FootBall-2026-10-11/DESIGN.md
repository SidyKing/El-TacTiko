---
name: El TacTiko
description: Habillage broadcast sur pelouse à la craie. Une seule PWA, lisible en plein soleil au bord du terrain ; le Statut se lit en trois secondes, par la couleur, la forme et la lettre.
status: final
created: 2026-10-11
updated: 2026-10-12
sources:
  - ../../prds/prd-FootBall-2026-10-11/prd.md
  - ../../prds/prd-FootBall-2026-10-11/addendum.md
  - .memlog.md
  - imports/brainstorm-keepsake.html
  - mockups/tablette-banc.html
  - mockups/tableau-tactique.html
  - mockups/comparaison.html
  - mockups/rapport.html
  - mockups/vue-joueur.html
colors:
  # Surfaces et encre (clair par défaut, -dark pour le thème sombre)
  surface-base: '#F3EFE3'
  surface-base-dark: '#0A120E'
  surface-card: '#FFFCF3'
  surface-card-dark: '#121E18'
  surface-chip: '#ECE6D4'
  surface-chip-dark: '#1C2B23'
  border-hairline: '#E0D9C5'
  border-hairline-dark: '#24382C'
  ink-primary: '#14201A'
  ink-primary-dark: '#ECF2EA'
  ink-secondary: '#434F48'
  ink-secondary-dark: '#A3B3A9'
  # Marque : drapeau (fixe dans les deux thèmes)
  senegal-green: '#00853F'
  flag-yellow: '#E2C400'
  flag-red: '#C8161E'
  # Habillage broadcast (la dalle reste sombre même en thème clair)
  slab: '#0D0F0E'
  slab-dark: '#151A17'
  slab-line: '#0D0F0E'
  slab-line-dark: '#252C28'
  on-slab: '#FFFFFF'
  on-slab-dark: '#FFFFFF'
  broadcast-yellow: '#FFD60A'
  broadcast-yellow-dark: '#FDEF42'
  on-broadcast-yellow: '#0D0F0E'
  on-broadcast-yellow-dark: '#0D0F0E'
  live: '#C8161E'
  live-dark: '#C8161E'
  live-gradient-top: '#D91D26'
  live-gradient-bottom: '#B0121A'
  offline: '#5D6560'
  offline-dark: '#5D6560'
  offline-ticker: '#FFD60A'
  offline-ticker-dark: '#FFD60A'
  hud: '#0620129E'
  hud-dark: '#0000008C'
  tag-dark-glass: '#08120CD1'
  # Statuts : couleur doublée d'une forme et d'une lettre
  status-vert: '#00853F'
  status-vert-dark: '#36C574'
  status-orange: '#B85A00'
  status-orange-dark: '#FFA23A'
  status-rouge: '#C8161E'
  status-rouge-dark: '#FF4D55'
  status-apprentissage: '#6B746F'
  status-apprentissage-dark: '#8D9992'
  on-status: '#FFFFFF'
  on-status-dark: '#0A120E'
  text-vert: '#00582C'
  text-vert-dark: '#5FE09A'
  text-orange: '#8A4300'
  text-orange-dark: '#FFB866'
  bg-rouge: '#FDECEB'
  bg-rouge-dark: '#2A1416'
  bg-orange: '#FFF1DF'
  bg-orange-dark: '#2A1F10'
  bg-vert: '#E3F3E8'
  bg-vert-dark: '#11291B'
  alert-glow: '#FF4D55'
  alert-glow-dark: '#FF4D55'
  # Terrain
  pitch-stripe-a: '#12753F'
  pitch-stripe-a-dark: '#0C2D1B'
  pitch-stripe-b: '#0F6B3A'
  pitch-stripe-b-dark: '#0A2617'
  chalk: '#FFFFFF'
  chalk-dark: '#DFF0E4'
  gps-trace: '#FDEF42'
  gps-trace-dark: '#FDEF42'
  jersey: '#FFFCF3'
  jersey-dark: '#F1EEE4'
  jersey-number: '#14201A'
  jersey-number-dark: '#14201A'
  heat-low: '#FDEF4259'
  heat-mid: '#FDC80A'
  heat-high: '#FF7A1A'
  heat-max: '#E8202A'
  # Tableau tactique (aucune couleur de Statut)
  tactic-team-ring: '#00853F'
  tactic-team-ring-dark: '#36C574'
  tactic-opponent: '#1D2320'
  tactic-opponent-dark: '#151A17'
  tactic-opponent-mark: '#FF8A6A'
  tactic-opponent-mark-dark: '#FF8A6A'
  # Partage
  whatsapp-green: '#128C4A'
  whatsapp-green-dark: '#128C4A'
typography:
  display-broadcast:
    fontFamily: Archivo
    fontSize: 27px
    fontWeight: '900'
    lineHeight: '1'
    letterSpacing: 0.005em
    note: 'Axe wdth : font-stretch 76 % · MAJUSCULES · bug, bandeaux, noms d’Équipe. Variante bandeau 23–25px (78–82 %).'
  numeral-hero:
    fontFamily: Archivo
    fontSize: 72px
    fontWeight: '900'
    lineHeight: '0.82'
    letterSpacing: -0.02em
    note: 'font-stretch 72 % · chiffres tabulaires · numéro du Focus, chrono (48px, 78 %), numéro du bandeau bas (44px, 70 %).'
  data-numeral:
    fontFamily: Archivo
    fontSize: 46px
    fontWeight: '900'
    lineHeight: '0.9'
    letterSpacing: -0.03em
    note: 'font-stretch 90 % · font-variant-numeric: tabular-nums · tuiles KPI, Intensité de l’Équipe.'
  data-numeral-sm:
    fontFamily: Archivo
    fontSize: 27px
    fontWeight: '900'
    lineHeight: '1'
    note: 'font-stretch 74–78 % · tabular-nums · stats du Focus, face-à-face de la Comparaison, KPI téléphone (30–32px).'
  heading:
    fontFamily: Archivo
    fontSize: 25px
    fontWeight: '900'
    lineHeight: '0.95'
    note: 'font-stretch 80 % · MAJUSCULES · nom du Joueur en dalle, titre de bandeau bas.'
  title-page:
    fontFamily: Archivo
    fontSize: 38px
    fontWeight: '900'
    lineHeight: '1.05'
    letterSpacing: -0.02em
    note: 'font-stretch 90 % · titres de page hors habillage (surfaces ordinateur, gestion).'
  body:
    fontFamily: Archivo
    fontSize: 16px
    fontWeight: '400'
    lineHeight: '1.45'
  body-strong:
    fontFamily: Archivo
    fontSize: 14.5px
    fontWeight: '700'
    lineHeight: '1.2'
    note: 'Largeur 100 % · noms de Joueurs, valeurs, lignes de liste sur tablette.'
  button:
    fontFamily: Archivo
    fontSize: 16px
    fontWeight: '800'
    lineHeight: '1.1'
  label-mono:
    fontFamily: JetBrains Mono
    fontSize: 13px
    fontWeight: '700'
    lineHeight: '1.2'
    letterSpacing: 0.08em
    note: 'MAJUSCULES · titres de carte, étiquettes, légendes HUD, onglets de segment.'
  data-mono:
    fontFamily: JetBrains Mono
    fontSize: 13px
    fontWeight: '500'
    lineHeight: '1.3'
    note: 'tabular-nums · références, deltas, heures, unités.'
rounded:
  xs: 7px
  sm: 9px
  md: 12px
  lg: 16px
  xl: 18px
  full: 9999px
spacing:
  '1': 4px
  '2': 8px
  '3': 12px
  '4': 16px
  '5': 24px
  '6': 32px
  card-padding: 12px 14px
  rail-gap: 9px
  gutter-mobile: 16px
  touch-min: 48px
  bug-height: 60px
  flag-line: 6px
  field-width-tablet: 790px
  rail-width-tablet: 390px
  lower-third-height: 62px
  bench-height: 68px
  tab-bar-height: 84px
  text-min: 13px
components:
  broadcast-bug:
    backgroundColor: '{colors.slab}'
    textColor: '{colors.on-slab}'
    height: '{spacing.bug-height}'
    typography: '{typography.display-broadcast}'
    accentColor: '{colors.broadcast-yellow}'
    liveColor: '{colors.live}'
  flag-line:
    height: '{spacing.flag-line}'
    colors: '{colors.senegal-green} · {colors.flag-yellow} · {colors.flag-red}'
  status-badge:
    size: 26px
    typography: '{typography.heading}'
    textColor: '{colors.on-status}'
    vert: '{colors.status-vert} · rond · V'
    orange: '{colors.status-orange} · triangle · O'
    rouge: '{colors.status-rouge} · octogone · R'
    apprentissage: '{colors.status-apprentissage} · cercle pointillé · A'
  jersey-marker:
    size: 60px
    shirtColor: '{colors.jersey}'
    numberColor: '{colors.jersey-number}'
    ringWidth: 4px
    ringColor: 'couleur du Statut'
    labelBackground: '{colors.tag-dark-glass}'
  pitch:
    stripeA: '{colors.pitch-stripe-a}'
    stripeB: '{colors.pitch-stripe-b}'
    lineColor: '{colors.chalk}'
    lineWidth: 3px
  heat-layer:
    ramp: '{colors.heat-low} → {colors.heat-mid} → {colors.heat-high} → {colors.heat-max}'
    opacity: '0.62 clair · 0.85 sombre (fusion écran)'
  gps-trace:
    strokeColor: '{colors.gps-trace}'
    strokeWidth: 4px
    dash: '2 10'
  card:
    backgroundColor: '{colors.surface-card}'
    borderColor: '{colors.border-hairline}'
    rounded: '{rounded.xl}'
    padding: '{spacing.card-padding}'
    titleTypography: '{typography.label-mono}'
  focus-slab:
    backgroundColor: '{colors.slab}'
    textColor: '{colors.on-slab}'
    rounded: '{rounded.lg}'
    kickerColor: '{colors.broadcast-yellow}'
    numberTypography: '{typography.numeral-hero}'
    numberColor: '{colors.alert-glow}'
  alert-lower-third:
    backgroundColor: '{colors.slab}'
    tagColor: '{colors.live}'
    numberBackground: '{colors.broadcast-yellow}'
    height: '{spacing.lower-third-height}'
    titleTypography: '{typography.heading}'
  offline-ticker:
    backgroundColor: '{colors.offline-ticker}'
    labelBackground: '{colors.slab}'
    labelColor: '{colors.broadcast-yellow}'
    textTypography: '{typography.data-mono}'
    height: '{spacing.lower-third-height}'
  button-primary:
    backgroundColor: '{colors.broadcast-yellow}'
    textColor: '{colors.on-broadcast-yellow}'
    rounded: '{rounded.md}'
    height: '{spacing.touch-min}'
    typography: '{typography.button}'
  button-share-whatsapp:
    backgroundColor: '{colors.whatsapp-green}'
    textColor: '#FFFFFF'
    rounded: '{rounded.md}'
    height: 52px
    typography: '{typography.button}'
  button-secondary:
    backgroundColor: '{colors.ink-primary}'
    textColor: '{colors.surface-card}'
    rounded: '{rounded.md}'
    height: '{spacing.touch-min}'
  tab-bar:
    backgroundColor: '{colors.surface-card}'
    height: '{spacing.tab-bar-height}'
    activePill: '{colors.broadcast-yellow}'
    inactiveText: '{colors.ink-secondary}'
  tool-palette:
    backgroundColor: '{colors.slab}'
    toolSize: 66px × 52px
    activeBackground: '{colors.broadcast-yellow}'
    rounded: '{rounded.md}'
  step-timeline:
    backgroundColor: '{colors.surface-card}'
    thumbSize: 160px × 66px
    activeRing: '{colors.broadcast-yellow}'
    playButton: '{colors.broadcast-yellow}'
    rounded: '{rounded.md}'
  kpi-tile:
    backgroundColor: '{colors.surface-card}'
    hotBackground: '{colors.slab}'
    valueTypography: '{typography.data-numeral}'
    labelTypography: '{typography.label-mono}'
    rounded: '{rounded.lg}'
  fiabilite-indicator:
    bars: 3
    eleve: '{colors.text-vert}'
    moyen: '{colors.text-orange}'
    faible: '{colors.status-rouge}'
    emptyBar: '{colors.border-hairline}'
    typography: '{typography.data-mono}'
  legend-hud:
    backgroundColor: '{colors.hud}'
    textColor: '#FFFFFF'
    rounded: '{rounded.md}'
    typography: '{typography.data-mono}'
    segmentActive: '{colors.broadcast-yellow}'
  status-row:
    height: 27px
    rounded: '{rounded.sm}'
    rougeBackground: '{colors.bg-rouge}'
    orangeBackground: '{colors.bg-orange}'
  delta-pill:
    rounded: '{rounded.full}'
    typography: '{typography.label-mono}'
  mirror-bars:
    trackColor: '#FFFFFF12'
    winColor: '{colors.broadcast-yellow}'
    height: 12px
  bench-strip:
    backgroundColor: '{colors.hud}'
    height: '{spacing.bench-height}'
    rounded: '{rounded.lg}'
---

# El TacTiko — Design Spine

> Maquettes de référence : [Tablette banc](mockups/tablette-banc.html) · [Tableau tactique](mockups/tableau-tactique.html) · [Comparaison de systèmes](mockups/comparaison.html) · [Rapport d'après-match](mockups/rapport.html) · [Vue joueur](mockups/vue-joueur.html). Import d'origine : [page souvenir du brainstorming](imports/brainstorm-keepsake.html). **Les spines priment sur les maquettes en cas de conflit.** Le comportement vit dans [EXPERIENCE.md](EXPERIENCE.md).

## Brand & Style

El TacTiko met une pelouse dans la main du coach et l'habille comme une retransmission télé. Trois couches se superposent sur chaque écran du staff :

- **La toile — le terrain.** Pelouse rayée, lignes à la craie, maillots à leur place. Le coach retrouve ses Joueurs là où ils jouent, pas dans un tableur. Zones chaudes et tracé GPS se posent directement sur le terrain.
- **Le cadre — l'habillage broadcast.** Bug « EN DIRECT » en haut avec le chrono jaune, ligne drapeau dessous, bandeau bas pour l'Alerte de décrochage ou le mode hors ligne. Les chiffres sont condensés, en Archivo très gras, comme un score à l'écran.
- **Le rail — les cartes.** Cartes claires, à la FotMob, pour les chiffres d'appoint : Intensité de l'Équipe, Focus du plus critique, liste des Statuts.

La posture : haut de gamme, réaliste, dynamique, mais jamais décoratif au détriment de la lecture. Le coach doit comprendre en trois secondes, en plein soleil, d'une main. Les couleurs du drapeau sénégalais (vert, jaune, rouge) donnent l'identité ; elles viennent de la [page souvenir du brainstorming](imports/brainstorm-keepsake.html), dont la palette est reprise et améliorée.

Le thème **clair est le thème par défaut** (lisibilité en plein soleil). Le thème **sombre** est proposé pour le match de nuit, la pelouse sous projecteurs et la causerie du soir. Les deux thèmes portent les mêmes informations et la même hiérarchie.

## Colors

Chaque couleur a un rôle unique. Dans le frontmatter, la variante sombre de chaque couleur porte le suffixe `-dark`.

**Surfaces et encre.** `{colors.surface-base}` (`#F3EFE3`, ivoire chaud) est le fond ; `{colors.surface-card}` (`#FFFCF3`) porte les cartes ; `{colors.surface-chip}` les puces de numéro et les segments. `{colors.ink-primary}` (`#14201A`, vert presque noir) sert au texte ; `{colors.ink-secondary}` (`#434F48`), aux références et aux unités. En sombre, le fond devient `#0A120E`, un vert nuit, jamais un noir pur.

**Drapeau.** `{colors.senegal-green}`, `{colors.flag-yellow}`, `{colors.flag-red}` ne servent qu'à la `flag-line` (6px sous le bug) et à l'écusson. Ce sont des marqueurs d'identité, pas des couleurs d'état.

**Habillage broadcast.** `{colors.slab}` (`#0D0F0E`) est la dalle sombre du bug, du Focus, du bandeau bas et de la palette d'outils ; **elle reste sombre en thème clair**. `{colors.broadcast-yellow}` (`#FFD60A` / `#FDEF42`) est le jaune d'habillage : chrono, valeur gagnante, outil actif, bouton principal, anneau de focus clavier. `{colors.live}` est le rouge du bandeau « EN DIRECT » (dégradé `{colors.live-gradient-top}` → `{colors.live-gradient-bottom}`) ; il passe au gris `{colors.offline}` hors ligne.

**Statuts.** Quatre couleurs : `{colors.status-vert}`, `{colors.status-orange}`, `{colors.status-rouge}` et `{colors.status-apprentissage}`. Les versions sombres sont plus lumineuses pour tenir sur la pelouse de nuit. Le texte coloré utilise `{colors.text-vert}` et `{colors.text-orange}`, plus foncés que le fond de pastille, pour tenir le contraste. Les fonds de ligne `{colors.bg-rouge}`, `{colors.bg-orange}` et `{colors.bg-vert}` signalent une ligne sans recolorer le texte.

**Le rouge est réservé.** `{colors.status-rouge}` et `{colors.alert-glow}` ne désignent que le Statut Rouge et l'Alerte de décrochage (plus l'Indice de fiabilité faible, qui est aussi une alerte). Ils ne servent jamais pour une Équipe, un adversaire, une décoration ou une erreur de formulaire banale.

**Terrain.** Deux bandes `{colors.pitch-stripe-a}` / `{colors.pitch-stripe-b}` de 79px, `{colors.chalk}` trace les lignes (légèrement lumineuse en sombre) et `{colors.gps-trace}`, jaune, le tracé GPS. Les zones chaudes suivent la rampe `{colors.heat-low}` → `{colors.heat-mid}` → `{colors.heat-high}` → `{colors.heat-max}` : 62 % d'opacité sous la craie en clair, fusion « écran » à 85 % en sombre.

**Tableau tactique.** Aucune couleur de Statut. L'Équipe porte un anneau `{colors.tactic-team-ring}` (vert), les adversaires sont des pions sombres `{colors.tactic-opponent}` marqués `{colors.tactic-opponent-mark}`, pour ne jamais confondre un adversaire avec un Joueur au Rouge.

**Partage.** `{colors.whatsapp-green}` (`#128C4A`) ne sert qu'au bouton « Partager sur WhatsApp », sans logo de marque.

### Contrastes visés

| Paire | Ratio | Usage |
|---|---|---|
| `ink-primary` sur `surface-base` | 14,6:1 | texte courant, banc |
| `ink-primary-dark` sur `surface-base-dark` | 16,7:1 | texte courant, sombre |
| `ink-secondary` sur `surface-card` | 8,4:1 (7,5:1 sur `surface-base`) | références dans les cartes |
| `ink-secondary-dark` sur `surface-base-dark` | 8,7:1 | références, sombre |
| `on-slab` sur `slab` | 19,2:1 | bug, Focus, bandeaux |
| `broadcast-yellow` sur `slab` | 13,6:1 | chrono, kicker |
| `text-orange` sur `surface-card` | 7,1:1 | delta orange |
| `text-vert` sur `surface-card` | 8,4:1 (7,5:1 sur `surface-base`) | delta vert, fiabilité élevée |
| `on-status-dark` sur `status-*-dark` | 5,8 à 9,5:1 | lettre de Statut, sombre |
| `on-status` sur `status-vert` / `status-orange` / `status-rouge` | 4,7 / 4,7 / 5,9:1 | lettre de Statut, clair (glyphe 900 doublé par la forme) |

Cible ferme : **texte du banc ≥ 7:1** (FR-15). `ink-secondary` et `text-vert` ont été foncés (`#434F48`, `#00582C`) pour tenir cette cible ; les maquettes utilisent encore les anciennes teintes, et ces tokens priment. `[ASSUMPTION]` La lettre dans la pastille de Statut est un glyphe de redondance, jugé à ≥ 4,5:1.

## Typography

Deux familles, chargées depuis Google Fonts : **Archivo** (axes `wdth` 62–125 et `wght` 400–900) et **JetBrains Mono** (400–800).

| Rôle | Spécification | Usage |
|---|---|---|
| `display-broadcast` | Archivo 900, 27px, largeur 76 %, majuscules | bug, noms d'Équipe, titres de bandeau |
| `numeral-hero` | Archivo 900, 72px, largeur 72 %, tabulaire | numéro du Focus ; chrono à 48px |
| `data-numeral` | Archivo 900, 46px, largeur 90 %, tabulaire | tuiles KPI, Intensité de l'Équipe |
| `data-numeral-sm` | Archivo 900, 27px, largeur 74–78 % | stats du Focus, face-à-face |
| `heading` | Archivo 900, 25px, largeur 80 %, majuscules | nom du Joueur en dalle, bandeau bas |
| `title-page` | Archivo 900, 38px, largeur 90 % | titres de pages ordinateur et gestion |
| `body` | Archivo 400, 16px | texte courant, phrases d'explication |
| `body-strong` | Archivo 700, 14,5px, largeur 100 % | noms, valeurs, lignes de liste |
| `button` | Archivo 800, 16px | boutons |
| `label-mono` | JetBrains Mono 700, 13px, majuscules, +0,08em | titres de carte, étiquettes, segments |
| `data-mono` | JetBrains Mono 500, 13px, tabulaire | références, deltas, heures |

Règles :

- **Plus petit texte : 13px à taille native** (`{spacing.text-min}`), sur tablette comme sur téléphone.
- Tous les chiffres comparables sont en `font-variant-numeric: tabular-nums`.
- L'habillage broadcast se condense (largeur 70–82 %) ; le contenu des cartes reste à largeur 100 % pour la lecture.
- En mode Présenter (Tableau tactique), tous les textes grossissent d'un tiers.
- Le mono porte les métadonnées (unités, références, heures) ; il ne porte jamais un nom de Joueur.

## Layout & Spacing

Échelle de base 4 / 8 / 12 / 16 / 24 / 32px (`{spacing.1}` à `{spacing.6}`). Les cartes du rail sont espacées de `{spacing.rail-gap}` (9px) et rembourrées de `{spacing.card-padding}`.

**Tablette paysage 1180×820** (Tablette banc, Tableau tactique, Comparaison, Rapport) :

- Bug broadcast pleine largeur (`{spacing.bug-height}`), puis `flag-line` (`{spacing.flag-line}`).
- Tablette banc : terrain `{spacing.field-width-tablet}` à gauche, rail `{spacing.rail-width-tablet}` à droite. Banc des remplaçants en bande (`{spacing.bench-height}`) en bas du terrain, bandeau bas d'alerte (`{spacing.lower-third-height}`) sous le banc, tous deux à 18px des bords.
- Tableau tactique : palette d'outils à gauche, terrain au centre, rail Bibliothèque à droite, frise des Étapes sous le terrain. Le terrain est dessiné en mètres (105 × 68 pour le football à 11) pour s'afficher à toutes les tailles.
- Comparaison : face-à-face en dalle et deux terrains orientés attaque vers le haut, détail par Joueur et verdict à droite.

**Téléphone portrait 390×844** (Vue joueur, Rapport mobile) : une colonne, marges `{spacing.gutter-mobile}`, en-tête broadcast compact, `tab-bar` en bas (`{spacing.tab-bar-height}`) pour la Vue joueur ; bouton PDF toujours à portée du pouce pour le Rapport.

**Ordinateur** (analyste, admin) : pas de maquette ; mêmes tokens, contenu en cartes sur `surface-base`. `[ASSUMPTION]` Largeur de contenu bornée à 1280px.

Les zones tactiles mesurent **au moins `{spacing.touch-min}` (48px)** partout sur tablette et téléphone.

## Elevation & Depth

La profondeur imite une retransmission, pas une interface de bureau.

- **Cartes** : ombre douce `0 1px 2px rgba(20,32,26,.06), 0 14px 30px -20px rgba(20,32,26,.45)` en clair ; en sombre, `0 1px 0 rgba(255,255,255,.03), 0 16px 34px -20px rgba(0,0,0,.9)`.
- **Bug broadcast** : reflet haut (dégradé blanc 7 % → transparent) et ombre portée `0 6px 18px -8px rgba(0,0,0,.5)` sur le terrain.
- **Verre HUD** : légende, banc, inspecteur et étiquettes de Joueur sur le terrain utilisent `{colors.hud}` avec flou d'arrière-plan 8px et filet blanc 14–16 %.
- **Terrain** : vignettage radial, grain fin en surimpression (16 %), ombre portée elliptique sous chaque maillot. En sombre, halos de projecteurs aux quatre coins.
- **Bandeaux bas** : ombre `0 16px 30px -12px rgba(0,0,0,.65)`, au-dessus du terrain.

L'ordre d'empilement est fixe : terrain → zones chaudes → tracé GPS → maillots → HUD et banc → bandeau bas → bug.

## Shapes

| Token | Valeur | Usage |
|---|---|---|
| `{rounded.xs}` | 7px | puces de numéro, touches clavier |
| `{rounded.sm}` | 9px | lignes de liste, petits boutons d'icône |
| `{rounded.md}` | 12px | boutons, HUD, bandeau craie, outils |
| `{rounded.lg}` | 16px | Focus, tuiles KPI, banc |
| `{rounded.xl}` | 18px | cartes du rail |
| `{rounded.full}` | 9999px | pastilles de delta, segments, onglet actif |

L'habillage broadcast ne s'arrondit pas : bug, bandeau « EN DIRECT », chrono, numéro du bandeau bas et kicker jaune sont **coupés en biais** (parallélogrammes, biseau 6 à 18px). Les cartes s'arrondissent. Ce contraste coupe / arrondi sépare le cadre télé du contenu.

Formes des Statuts : rond (Vert), triangle (Orange), octogone (Rouge), cercle pointillé (en apprentissage). Ces quatre formes sont réservées au Statut.

## Components

**broadcast-bug** — Dalle `{colors.slab}` pleine largeur, 60px. De gauche à droite :

- étiquette « EN DIRECT » (dégradé `live`, point clignotant, coupée en biais) ; grise et « HORS LIGNE » hors ligne ; verte « FIN DU MATCH » dans le Rapport ;
- écusson jaune `{colors.flag-yellow}` 38px ;
- nom d'Équipe en `display-broadcast`, avec sous-titre mono jaune (type · format · terrain) ;
- chrono sur parallélogramme jaune (`numeral-hero` 48px) ;
- compteur « 10/10 Gilets actifs » ;
- fraîcheur : « À jour il y a 4 s » avec point vert pulsant ; quand l'écran est figé, « Données à jour à HH:MM » en blanc, point jaune fixe.

Sur les autres écrans, le bug porte le titre d'écran et les actions (Partager, PDF, Présenter).

**flag-line** — 6px sous le bug, trois tiers vert / jaune / rouge du drapeau. Toujours présente sous un bug.

**status-badge** — 26px (22px en liste compacte, 20px en dalle). Lettre en Archivo 900 dans `{colors.on-status}`. Vert : rond. Orange : triangle (lettre décalée vers le bas). Rouge : octogone. En apprentissage : cercle pointillé 2,5px, lettre « A » grise, fond transparent (blanc à 92 % sur le terrain). Sur le terrain, filet blanc 2px autour du Vert et du A.

**jersey-marker** — Maillot 60px couleur `{colors.jersey}`, numéro `{colors.jersey-number}` en Archivo 900 20px, anneau de 4px à la couleur du Statut (pointillé pour A), pastille de Statut en haut à droite, étiquette verre sous le maillot (nom + Intensité en m/min, delta en mono). Joueur au Rouge : étiquette sur fond rouge, anneau en onde et halo pulsants. Sur le Tableau tactique, l'anneau est `{colors.tactic-team-ring}` et l'étiquette sélectionnée passe en jaune avec poignées.

**pitch** — Bandes, craie 3px, buts, grain et vignettage (voir Elevation & Depth). Le format s'adapte : football à 11, five, foot en salle. Orientation : attaque vers la droite sur la Tablette banc, vers le haut sur la Comparaison.

**heat-layer** — Rampe de chaleur sur la surface du terrain, du coup d'envoi à la minute en cours (« match entier ») ou sur les 10 dernières minutes. Désaturée hors ligne.

**gps-trace** — Pointillés `{colors.gps-trace}` 4px (2 / 10) avec halo flou 11px, point de départ cerclé et étiqueté « 0′ départ », trace fantôme blanche 34 % pour le passé lointain. Marche animée des pointillés en direct.

**card** — `{colors.surface-card}`, filet `{colors.border-hairline}`, `{rounded.xl}`, titre en `label-mono` `ink-secondary`, valeur auxiliaire à droite en mono.

**focus-slab** — « Focus · le plus critique ». Dalle `{colors.slab}` même en clair, hachures diagonales à 5 % en coin, kicker jaune coupé en biais. Numéro en `numeral-hero` `{colors.alert-glow}`, nom en `heading`, poste et Statut en mono, trois stats en `data-numeral-sm` séparées par un filet, mini-courbe d'Intensité rouge sur aire rouge 22 % avec ligne de Référence en tirets blancs. Hors ligne : désaturée, pastille « Figé à HH:MM ».

**alert-lower-third** — Bandeau bas 62px qui glisse depuis la gauche : étiquette rouge « ALERTE DE DÉCROCHAGE » coupée en biais, numéro sur jaune (`numeral-hero` 44px), nom en `heading` et détail mono (« Intensité −27 % sur 10 min · 112 m/min, réf. 154 »), delta géant rouge à droite. Barre de minuterie rouge 3px qui se vide, reflet qui balaie.

**offline-ticker** — Remplace le bandeau d'alerte quand l'écran est hors ligne. Fond `{colors.offline-ticker}`, étiquette « HORS LIGNE » jaune sur dalle coupée en biais, texte mono 15px qui défile en boucle : « Données à jour à HH:MM · Positions et Statuts figés · Les Gilets continuent d'enregistrer · Synchronisation automatique après la Séance ».

**legend-hud** — Verre `{colors.hud}` en haut à gauche du terrain : segment « Match entier / 10 dernières min » (actif en jaune), rampe des zones chaudes avec plage de minutes, clé du tracé GPS.

**bench-strip** — Bande verre sur le bas du terrain, libellé vertical « BANC », une tuile par remplaçant (mini-maillot 34px, pastille de Statut, nom, Intensité en mono).

**status-row** — Ligne de 27px : pastille, puce de numéro, nom en `body-strong`, valeur / Référence en mono, `delta-pill`. Rouge : fond `{colors.bg-rouge}` et filet gauche rouge 3px. Orange : fond `{colors.bg-orange}` dégradé. En apprentissage : étiquette italique pointillée « en apprentissage » à la place des valeurs.

**delta-pill** — Mono 13px, `{rounded.full}`. Rouge : fond `status-rouge`, texte blanc. Orange : fond `bg-orange`, texte `text-orange`. Vert : texte `text-vert` sans fond. Apprentissage : texte `ink-secondary`.

**kpi-tile** — Carte `{rounded.lg}` : étiquette `label-mono`, valeur `data-numeral`, unité et Référence en mono. Variante « chaude » sur dalle (`{colors.slab}`, valeur jaune) pour l'Alerte ou le chiffre clé. Barre de répartition des Statuts (9px, segments R/O/V/A, A hachuré).

**mirror-bars** — Face-à-face de la Comparaison sur dalle : valeur A à gauche, B à droite, barres en miroir de 12px ; la Phase gagnante passe en `{colors.broadcast-yellow}` avec lueur, valeur sur parallélogramme jaune.

**fiabilite-indicator** — Trois barres verticales + un mot (« Élevé », « Moyen », « Faible ») en `data-mono`. Barres actives `text-vert`, `text-orange` ou `status-rouge` ; inactives `border-hairline`. Faible : mot en rouge gras et marque « ! ». Présent sur chaque ligne où s'affichent des Métriques physiques.

**button-primary** — Fond `{colors.broadcast-yellow}`, texte `{colors.on-broadcast-yellow}`, `button`, `{rounded.md}`, hauteur ≥ 48px, ombre intérieure basse. Sur dalle sombre en thème clair, la variante inverse (dalle + texte jaune) est permise.

**button-secondary** — Fond `ink-primary`, texte `surface-card` (ex. « Télécharger le PDF »). Variante contour rouge réservée à « Retirer mon consentement ».

**button-share-whatsapp** — Fond `{colors.whatsapp-green}`, texte blanc, icône de partage générique, 52px de haut, pleine largeur sur téléphone.

**tab-bar** — Téléphone uniquement. Quatre onglets (Accueil, Séances, Progrès, Mes données), icône 21px + libellé ; onglet actif : pilule jaune 54 × 30px derrière l'icône, libellé `ink-primary`. Libellé à 13px minimum (la maquette en 12px est à corriger).

**tool-palette** — Colonne sur dalle : outils 66 × 52px (icône 24px + libellé 13px) : Joueur, Adversaire, Ballon, Flèche, Passe, Ligne, Zone, Texte, Gomme, puis Annuler, Rétablir, Couleur. Outil actif sur jaune avec flèche pointant vers le terrain ; outils indisponibles à 45 %.

**step-timeline** — Bande sous le terrain : vignettes d'Étape 160 × 66px (mini-terrain + numéro + légende), Étape active cerclée de jaune, tuile « + Étape » pointillée, bouton « Animer » avec durée. En Présenter : grandes flèches Précédente / Suivante, Étapes cliquables, barre de progression jaune.

## Do's and Don'ts

| Do | Don't |
|---|---|
| Doubler chaque Statut par sa forme et sa lettre (V rond, O triangle, R octogone, A pointillé) | Communiquer un Statut par la couleur seule |
| Réserver le rouge au Statut Rouge, aux Alertes et à l'Indice de fiabilité faible | Rouge pour une Équipe, un adversaire, un bouton ou une décoration |
| Anneau vert pour l'Équipe et pions sombres pour l'adversaire sur le Tableau tactique | Couleurs de Statut dans le Tableau tactique |
| Texte du banc à ≥ 7:1 ; 13px minimum à taille native | Texte gris clair sur ivoire ; libellés en 10–12px |
| Thème clair par défaut ; sombre proposé avec la même hiérarchie | Sombre forcé au bord du terrain en plein jour |
| Garder la dalle broadcast sombre dans les deux thèmes | Éclaircir le bug ou le Focus en thème clair |
| Couper toutes les animations si « réduire les animations » est actif | Pulsation, défilement, marche du tracé ou croissance des barres sans repli statique |
| Chiffres tabulaires et condensés pour toutes les données | Chiffres proportionnels qui sautent quand ils changent |
| Jaune pour le bouton principal et l'élément actif | Jaune décoratif sans action ni état |
| Désaturer et figer tout l'écran hors ligne | Laisser des animations « vivantes » sur des données figées |
| Données plausibles et noms réels du contexte dans les maquettes | Lorem ipsum, zéros à la place de données en attente |
