---
name: El TacTiko
status: draft
created: 2026-10-11
updated: 2026-10-11
sources:
  - ../../prds/prd-FootBall-2026-10-11/prd.md
  - ../../prds/prd-FootBall-2026-10-11/addendum.md
  - .memlog.md
  - DESIGN.md
  - mockups/tablette-banc.html
  - mockups/tableau-tactique.html
  - mockups/comparaison.html
  - mockups/rapport.html
  - mockups/vue-joueur.html
---

# El TacTiko — Experience Spine

> Le produit, les Rôles, les FR et les NFR sont dans le [PRD](../../prds/prd-FootBall-2026-10-11/prd.md) ; les contraintes PWA dans son [addendum](../../prds/prd-FootBall-2026-10-11/addendum.md). Les termes du Glossaire (§3) sont employés tels quels. L'identité visuelle vit dans [DESIGN.md](DESIGN.md). **Les spines priment sur les maquettes en cas de conflit.**

## Foundation

- **Une seule PWA installable** pour tous les Rôles (NFR-1). Aucun framework d'interface imposé : composants maison sur les tokens de `DESIGN.md`, qui est la référence visuelle.
- **Trois form factors :**

| Form factor | Taille de référence | Surfaces |
|---|---|---|
| Tablette paysage | 1180×820 | Tablette banc, Tableau tactique, Comparaison de systèmes, Rapport d'après-match, préparation et lancement de Séance |
| Téléphone portrait | 390×844 | Vue joueur, Rapport d'après-match mobile (lien WhatsApp) |
| Ordinateur | ≥ 1280 de large `[ASSUMPTION]` | saisie des Actions ballon (analyste), administration El TacTiko, tableau de bord d'adoption |

- **Thème clair par défaut**, thème sombre proposé (réglage par appareil, « auto » suit le système).
- **Langue :** français en v1 (NFR-4). Libellés de la Tablette banc et de la Vue joueur prévus pour une traduction en wolof en v1.1 : pas de texte dans les images, pas de libellé tronqué à la longueur française.
- **La Tablette banc affiche, elle ne calcule pas.** Tout Statut, toute Alerte et toute métrique viennent de la Plateforme.

## Information Architecture

### Surfaces par Rôle

| Surface | Rôles | Form factor | Référence |
|---|---|---|---|
| Connexion (code à usage unique SMS / WhatsApp / e-mail) | tous | tous | spine seule |
| Séances de l'Équipe (accueil staff : liste, état vidéo, état de synchro) | coach, préparateur, analyste, président (lecture) | tablette, ordinateur | spine seule `[ASSUMPTION]` accueil staff |
| Préparation de Séance : Joueurs convoqués + association Gilet–Joueur | coach | tablette | spine seule |
| Lancement / clôture de Séance (type, Équipe, terrain ; correction des heures) | coach | tablette | spine seule |
| Tablette banc (direct, match ou entraînement avec Phases) | coach, préparateur, analyste | tablette | [mockups/tablette-banc.html](mockups/tablette-banc.html) (match) ; contrôle des Phases : spine seule |
| Comparaison de systèmes | coach, préparateur, analyste | tablette | [mockups/comparaison.html](mockups/comparaison.html) |
| Tableau tactique (édition, bibliothèque, Présenter) | coach (édition) ; staff et Joueurs (lecture des Schémas partagés) | tablette, ordinateur | [mockups/tableau-tactique.html](mockups/tableau-tactique.html) |
| Rapport d'après-match (v1 / v2, PDF, partage) | coach, préparateur, analyste, président | tablette, téléphone | [mockups/rapport.html](mockups/rapport.html) |
| Historique joueur (staff) | coach, préparateur, analyste | tablette, ordinateur | spine seule |
| Saisie des Actions ballon sur la vidéo | analyste | ordinateur | spine seule |
| Effectif de l'Équipe (ajouter, modifier, archiver) | coach | tablette, ordinateur | spine seule |
| Consentement côté staff (enregistrement, charte, représentant légal) | coach `[ASSUMPTION]` ou Membre du staff désigné | tablette, ordinateur | spine seule |
| Vue joueur : Accueil, Séances, Progrès, Mes données | joueur | téléphone | [mockups/vue-joueur.html](mockups/vue-joueur.html) |
| Gestion Club / Équipes / invitations | admin El TacTiko | ordinateur | spine seule |
| Kit : inventaire, état, attribution, dernier lieu connu | admin El TacTiko | ordinateur | spine seule |
| Calibration (mesures manuelles vs calculées) | équipe El TacTiko | ordinateur, tablette | spine seule |
| Tableau de bord d'adoption + journal d'accès | admin El TacTiko | ordinateur | spine seule |

### Couverture des fonctionnalités du PRD

| PRD | Surfaces |
|---|---|
| 4.1 Clubs, Équipes, comptes, Rôles (FR-1 à FR-4) | Connexion · Gestion Club / Équipes · Effectif · filtrage par Rôle sur toutes les surfaces |
| 4.2 Kit et captation (FR-5 à FR-9) | Kit (admin) · Préparation de Séance · Lancement / clôture · état de synchro sur Séances et Rapport · source de captation par Joueur sur Rapport et Historique |
| 4.3 Analyse physique (FR-10 à FR-14) | pas de surface propre : affichée dans Tablette banc, Rapport, Historique, Vue joueur ; Calibration (admin) |
| 4.4 Tablette banc (FR-15 à FR-18) | Tablette banc |
| 4.5 Vidéo et Actions ballon (FR-19 à FR-22) | état vidéo sur Séances et Rapport · Saisie des Actions ballon |
| 4.6 Mode entraînement et Comparaison (FR-23 à FR-25) | contrôle des Phases sur la Tablette banc · Comparaison de systèmes |
| 4.7 Tableau tactique (FR-35 à FR-39) | Tableau tactique (édition, Présenter, bibliothèque, rattachement à une Séance ou une Phase) |
| 4.8 Rapports et Historique (FR-26 à FR-29) | Rapport d'après-match · Historique joueur · Vue joueur |
| 4.9 Consentement (FR-30 à FR-32) | Consentement côté staff · Mes données (Vue joueur) · journal d'accès (admin) |
| 4.10 Suivi de l'adoption (FR-33, FR-34) | Tableau de bord d'adoption |

### Navigation

- **Téléphone (joueur) :** `tab-bar` à quatre onglets — Accueil, Séances, Progrès, Mes données. Pas de tiroir.
- **Tablette (staff) :** l'accueil est la liste des Séances de l'Équipe ; on y lance une Séance, on ouvre un Rapport, une Comparaison ou le Tableau tactique. `[ASSUMPTION]` Navigation globale par un menu ouvert depuis le `broadcast-bug` ; elle est masquée pendant une Séance en direct, où la Tablette banc occupe tout l'écran avec une seule sortie.
- **Ordinateur :** mêmes destinations que la tablette, plus les surfaces d'administration pour l'admin El TacTiko.
- **Liens directs :** un lien de Rapport ou de Schéma tactique ouvre la surface directement. Un Joueur ne voit que les Schémas partagés avec son Équipe (FR-38) ; un Membre du staff ne voit jamais un autre Club (FR-3).

## Voice and Tone

Microcopy. La voix de marque et la posture visuelle vivent dans `DESIGN.md`.

| Do | Don't |
|---|---|
| Tutoyer le Joueur : « Ton Intensité est tombée à 71 m/min, sous ta Référence individuelle. » | Vouvoiement administratif ou jargon de préparateur avec le Joueur |
| « Pas une sanction, un signal. » | « Mauvaise performance », « Joueur faible » |
| « Ici, tu te compares uniquement à toi-même. » | Classements, comparaisons entre coéquipiers |
| « Hors ligne, données à jour à 18:42 » | « Erreur réseau », « Échec de connexion » |
| « Les Gilets continuent d'enregistrer. » | Laisser croire que des données sont perdues |
| « Actions ballon en attente de validation » | Afficher des zéros à la place de données à venir |
| Tendances et Statuts : « baisse de 27 % sur 10 min » | Certitudes : « va se blesser », « doit sortir », « fatigué à coup sûr » |
| Termes du Glossaire avec leur majuscule : Séance, Statut, Gilet, Phase | Synonymes : « session », « capteur » pour Gilet, « niveau » pour Statut |
| Phrases courtes, vocabulaire du terrain (« faire souffler », « causerie ») | Abréviations non expliquées, anglicismes (« dashboard », « tracking ») |
| Staff : vouvoiement neutre ou forme impersonnelle `[ASSUMPTION]` | Tutoiement du président ou de l'analyste |

El TacTiko montre des tendances, jamais des décisions (PRD §5). Aucun libellé ne prescrit un changement de Joueur.

## Component Patterns

Comportement. Les spécifications visuelles vivent dans `DESIGN.md.Components`.

| Composant | Où | Règles de comportement |
|---|---|---|
| `broadcast-bug` | toutes les surfaces staff tablette, Rapport | Fraîcheur mise à jour chaque seconde (« À jour il y a N s ») ; bascule en « Données à jour à HH:MM » au-delà de 60 s. Le chrono local continue même hors ligne. Porte les actions d'écran (Partager, PDF, Présenter). |
| `flag-line` | sous chaque `broadcast-bug` | Statique, non interactive. |
| `status-badge` | partout où un Statut s'affiche | Toujours forme + lettre + couleur. Libellé accessible : « Statut rouge », « en apprentissage ». Jamais seul : accompagné du nom ou du numéro. |
| `jersey-marker` | Tablette banc, Comparaison, Tableau tactique | Banc et Comparaison : toucher → Métriques physiques de la Séance en cours du Joueur (FR-15), `[ASSUMPTION]` affichées dans la `focus-slab` jusqu'à un nouveau toucher ou 30 s. Tableau tactique : glisser pour déplacer, toucher pour sélectionner (inspecteur, nom, couleur, suppression). |
| `pitch` | Tablette banc, Comparaison, Tableau tactique, Rapport, Vue joueur | Format selon la Séance : football à 11, five, foot en salle. Coordonnées en mètres. |
| `heat-layer` | Tablette banc, Comparaison, Rapport, Vue joueur | Tablette banc : segment « Match entier / 10 dernières min » dans la `legend-hud`, « Match entier » par défaut. Rapport : bascule Équipe / Joueur. |
| `gps-trace` | Tablette banc | Tracé d'un seul Joueur à la fois ; par défaut le plus critique, sinon le dernier Joueur touché `[ASSUMPTION]`. Couvre la même plage que la `heat-layer`. |
| `legend-hud` | Tablette banc | Le segment change la plage de la `heat-layer` et du `gps-trace` ensemble. |
| `card` | rail, Rapport, Vue joueur, surfaces ordinateur | Valeur auxiliaire = Référence ou plage de temps ; jamais une action cachée. |
| `focus-slab` | rail de la Tablette banc | Montre en permanence le Joueur le plus critique (FR-15). Change de Joueur seulement quand l'ordre de criticité change. Hors ligne : « Figé à HH:MM ». |
| `status-row` | rail de la Tablette banc | Triée du plus critique au moins critique (FR-15). Un réordonnancement n'est jamais animé pendant un toucher en cours. Toucher → même effet que le `jersey-marker`. |
| `bench-strip` | Tablette banc | Remplaçants avec leur dernier Statut connu. Toucher → Métriques physiques. |
| `alert-lower-third` | Tablette banc | Apparaît quand un Joueur passe au Rouge (FR-16), avec vibration si l'appareil le permet. Reste visible 12 s puis se replie ; l'anneau rouge du Joueur continue. Une même Alerte n'est pas répétée pendant 5 minutes pour le même Joueur. Plusieurs Alertes : file d'attente, la plus récente d'abord. Toucher → Métriques du Joueur. |
| `offline-ticker` | Tablette banc | Remplace le `alert-lower-third` tant que l'écran est figé. Une Alerte reçue au retour du réseau passe avant le ticker. |
| `kpi-tile` | rail, Rapport, Vue joueur | Valeur + Référence ou delta. Valeur absente → libellé d'attente, jamais zéro. |
| `mirror-bars` | Comparaison | Phase gagnante surlignée selon le sens de la métrique (pertes de balle : moins = mieux). Lignes Actions ballon absentes tant qu'elles ne sont pas validées. |
| `delta-pill` | rail, Comparaison, Vue joueur | Toujours relatif à la Référence individuelle ou à l'autre Phase, avec l'unité. |
| `fiabilite-indicator` | partout où s'affichent des Métriques physiques (FR-13) | Faible → note sous le tableau (cause et « Séance exclue de sa Référence individuelle »). |
| `button-primary` | toutes surfaces | Une seule action principale par écran. |
| `button-share-whatsapp` | Rapport | Ouvre la feuille de partage du système avec le lien privé du Rapport (FR-27). |
| `button-secondary` | Rapport, Vue joueur | « Télécharger le PDF », « Exporter mes données ». |
| `tab-bar` | Vue joueur | Onglet actif conservé au retour dans l'application. |
| `tool-palette` | Tableau tactique | Un outil actif à la fois ; Échap ou nouvel outil le remplace. Annuler / Rétablir sur tout le Schéma. Dessin au doigt sur tablette, à la souris sur ordinateur (FR-36). |
| `step-timeline` | Tableau tactique | « + Étape » duplique l'Étape courante. « Animer » joue toutes les Étapes. Au moins 10 Étapes (FR-37). |

## State Patterns

| État | Surface | Traitement |
|---|---|---|
| En direct | Tablette banc | Bug « EN DIRECT » rouge, point de fraîcheur pulsant, « À jour il y a N s ». |
| Données en retard (> 60 s) | Tablette banc | Même traitement que hors ligne (FR-17) : « Hors ligne, données à jour à HH:MM ». |
| Hors ligne figé | Tablette banc | Étiquette « HORS LIGNE » grise, terrain, maillots, banc, zones chaudes et Focus désaturés et immobiles, `offline-ticker` défilant, listes marquées « Figés à HH:MM ». Chrono local actif. Retour automatique en direct dès que des données fraîches arrivent, sans action. |
| Ouverture sans réseau | toutes | La PWA s'ouvre et affiche la dernière Séance et les dernières données consultées (FR-17, NFR-2), marquées de leur heure. |
| En apprentissage (< 3 Séances) | Tablette banc, Rapport, Vue joueur | `status-badge` A pointillé, « en apprentissage » ou « sans réf. » à la place du delta ; jamais orange ni rouge. |
| Gilets incomplets | bug, Préparation de Séance | « 9/10 Gilets actifs » ; le Joueur sans signal apparaît avec un Statut gris « signal perdu » `[ASSUMPTION]`. |
| Vidéo en attente / en cours d'envoi / disponible | Séances, Rapport, Saisie des Actions ballon | Libellé d'état (FR-19). En attente : saisie impossible, message « vidéo en attente » ; l'analyste est notifié à l'arrivée. |
| Actions ballon en attente de validation | Rapport, Comparaison, Vue joueur | Colonnes masquées ou étiquette pointillée « Actions ballon en attente de validation » ; jamais de zéros. |
| Rapport v1 / v2 | Rapport | v1 à la clôture (physique seul, « Rapport v1 · HH:MM ») ; v2 quand les Actions ballon sont validées (« Rapport v2 mis à jour JJ/MM HH:MM »). Le même lien sert les deux. |
| Synchronisation partielle / complète | Séances, Rapport | Mention « synchronisation partielle » tant que des données tamponnées manquent (FR-8) ; le Rapport se met à jour seul. |
| Indice de fiabilité faible | Rapport, Historique, Vue joueur | `fiabilite-indicator` rouge « Faible » + cause ; Séance exclue de la Référence individuelle (FR-13). |
| Consentement absent | Préparation de Séance, Effectif | Le Joueur apparaît mais ne peut pas recevoir de Gilet (FR-30) : ligne grisée, mention « Consentement manquant », action « Enregistrer le Consentement ». Mineur : mention du représentant légal. |
| Consentement retiré | Effectif, Vue joueur | Plus d'association de Gilet possible ; le Joueur voit « Après un retrait, plus aucune donnée n'est collectée sur toi. » Sort des données passées : `[À TRANCHER]` dans le PRD. |
| Alerte de décrochage | Tablette banc | Voir `alert-lower-third` ; anti-répétition 5 min. |
| Vide : aucune Séance | Séances, Vue joueur | « Aucune Séance pour l'instant. » + action « Lancer une Séance » (coach) ; joueur : « Ta première Séance apparaîtra ici. » |
| Vide : bibliothèque | Tableau tactique | « Aucun Schéma tactique. » + « Nouveau Schéma tactique » et formations en un geste. |
| Vide : Comparaison | Comparaison | Moins de deux Phases → « Crée deux Phases pendant une Séance d'entraînement pour les comparer. » |
| Chargement | toutes | Squelettes à la forme des cartes ; jamais de spinner plein écran sur la Tablette banc. |
| Accès refusé (Rôle) | toutes | Message neutre « Cette page n'est pas disponible avec ton compte » (joueur) ou « … avec votre Rôle » (staff) ; aucune donnée d'un autre Joueur ou Club n'est chargée. |
| Lien de Rapport expiré | Rapport mobile | « Ce lien a expiré. » + accès par Connexion. |
| Focus clavier | toutes | Anneau 3px `{colors.broadcast-yellow}`, décalé de 2px. |

## Interaction Primitives

- **Une main, sur tablette paysage.** Zones tactiles ≥ `{spacing.touch-min}`. Rien d'essentiel ne demande de geste à deux doigts ni de glisser précis pendant une Séance.
- **Toucher pour voir.** Toucher un maillot, une ligne ou une tuile du banc affiche les Métriques physiques du Joueur (FR-15). Pas d'appui long obligatoire.
- **Alerte : anti-répétition 5 minutes** par Joueur (FR-16). Vibration seulement si l'API existe (Android) ; sinon visuel seul.
- **Phases en un geste** (FR-23) : pendant une Séance d'entraînement, un seul toucher démarre la Phase suivante et arrête la précédente. `[ASSUMPTION]` Contrôle placé dans le bug à la place de l'étiquette « EN DIRECT ». Phases corrigeables après coup.
- **Segment Match entier / 10 dernières min** sur la Tablette banc : bascule instantanée, réglage gardé pour la Séance.
- **Étapes et animation** (Tableau tactique) : « Animer » fait glisser les Joueurs le long de leurs flèches, le ballon suit la passe, en boucle ; pause possible. Avec « réduire les animations », les Étapes changent sans glissement.
- **Mode Présenter** : plein écran, palette, rail et frise masqués, textes agrandis d'un tiers. Grandes flèches Précédente / Suivante au pouce, Étapes cliquables, « Quitter » (Échap au clavier).
- **Formations en un geste** (FR-35) : 4-4-2, 4-3-3, 3-5-2… posées puis ajustées par glisser.
- **Partage** : Comparaison (lien interne ou PDF, FR-25), Schéma tactique (lien interne, image ou PDF, FR-38), Rapport (lien privé et PDF, partage WhatsApp, FR-27). `[ASSUMPTION]` Le lien du Rapport s'ouvre sans compte, privé, valable 30 jours, comme dans la maquette.
- **Saisie des Actions ballon au clavier** (FR-21) : une Action en moins de 10 s — raccourci du type, numéro du Joueur, instant pris sur la vidéo ; validation en un geste. Correspondance des touches à fixer `[ASSUMPTION]`.
- **Synchronisation silencieuse** : les saisies hors ligne (Phases, corrections) partent seules au retour du réseau (NFR-2).
- **Banni :** classements entre Joueurs, notifications de relance, temps passé valorisé (SM-C2), carrousels.

## Accessibility Floor

Comportement. Les contrastes visuels vivent dans `DESIGN.md`.

- Texte de la Tablette banc ≥ 7:1 dans les deux thèmes ; 13px minimum à taille native.
- Aucune information portée par la couleur seule : Statut = couleur + forme + lettre ; Indice de fiabilité = barres + mot.
- `prefers-reduced-motion` coupe toutes les animations : pulsation du Rouge, glissement du bandeau bas, marche du tracé GPS, point de fraîcheur, défilement hors ligne (le texte reste lisible en entier), croissance des barres, chiffres qui montent, animation des Étapes.
- Lecteurs d'écran : chaque Joueur annoncé « n°7, Ibou Diallo, Statut rouge, Intensité −27 % ». L'Alerte de décrochage est annoncée une fois (région live assertive) ; la fraîcheur ne l'est pas à chaque seconde.
- Clavier complet sur ordinateur (saisie des Actions ballon, administration, Tableau tactique) ; ordre de focus = ordre de lecture.
- Zones tactiles ≥ 48px.
- Zoom du navigateur à 200 % sans perte d'information sur téléphone et ordinateur.
- Attribut `lang="fr"` ; prêt pour le wolof (NFR-4).

## Key Flows

### UJ-1 — Moussa voit son ailier décrocher pendant un match de five

Moussa, coach à Dakar, mardi soir, terrain synthétique extérieur, tablette à l'horizontale. Référence : [mockups/tablette-banc.html](mockups/tablette-banc.html), [mockups/rapport.html](mockups/rapport.html).

1. Il ouvre la PWA, choisit son Équipe et lance une Séance « match » (type, terrain).
2. Préparation : les associations Gilet–Joueur de la Séance précédente sont reprises ; il distribue les Gilets. Le bug affiche « 10/10 Gilets actifs ».
3. La Tablette banc passe en direct : terrain avec maillots et anneaux de Statut, Intensité de l'Équipe, Focus du plus critique, Statuts triés.
4. À la 18e minute, Ibou passe à l'orange puis au rouge.
5. **Climax :** le bandeau bas « Alerte de décrochage » glisse sous le terrain, l'anneau d'Ibou pulse, le Focus affiche « 7 · Ibou Diallo · −27 % sur 10 min ». Moussa le fait sortir.
6. Il clôture la Séance. Rapport v1 généré ; le soir même, le lien arrive dans le groupe WhatsApp du staff.

Échec : le réseau coupe → « Hors ligne, données à jour à 18:42 », écran figé et désaturé, ticker « Les Gilets continuent d'enregistrer ». Tout se synchronise après la Séance ; le Rapport le signale si la synchronisation est partielle.

### UJ-2 — Le coach d'un club de Ligue 2 compare le 4-3-3 et le 3-5-2 à l'entraînement

Le coach de l'AS Ziguinchor, Club pilote de Ligue 2, football à 11. Références : [mockups/comparaison.html](mockups/comparaison.html), [mockups/tableau-tactique.html](mockups/tableau-tactique.html).

1. Il crée une Séance d'entraînement avec deux Phases, « 4-3-3 » puis « 3-5-2 », de 20 minutes.
2. Pendant la Séance, il bascule de l'une à l'autre en un geste sur la tablette.
3. Après la Séance, il ouvre la Comparaison de systèmes : face-à-face en `mirror-bars`, deux terrains en zones chaudes, détail par Joueur, verdict.
4. **Climax :** la colonne 3-5-2 s'allume en jaune — +8 % d'Intensité, +3 récupérations. Il garde le 3-5-2 et partage la comparaison avec son adjoint (lien ou PDF).
5. Avant la Séance suivante, il ouvre le Tableau tactique, pose le 3-5-2 en un geste, dessine les lignes et le circuit de relance en trois Étapes, rattache le Schéma à la Phase « 3-5-2 ».
6. Au vestiaire, il passe en Présenter : les Joueurs glissent le long de leurs flèches, le ballon suit la passe.

Échec : Actions ballon pas encore validées → la Comparaison montre les Métriques physiques seules et signale l'attente. Pas de réseau au vestiaire → le Schéma déjà ouvert reste consultable hors ligne (FR-38).

### UJ-3 — Awa, analyste, valide les passes et les tirs le lendemain du match

Awa, analyste pour un Club ou pour El TacTiko, sur son ordinateur. Surface spine seule.

1. Elle ouvre la Séance terminée ; l'état vidéo indique « disponible ».
2. Elle parcourt la vidéo et la liste des Actions ballon ; pour chacune, elle choisit le type, le Joueur et l'instant, au clavier.
3. Elle corrige ou supprime les Actions erronées.
4. **Climax :** elle valide ; le Rapport passe en v2 (« mis à jour 07/10 10:42 »), les Actions ballon validées rejoignent le Rapport et l'Historique joueur de chaque Joueur.

Échec : la vidéo n'est pas encore envoyée → la Séance affiche « vidéo en attente », la saisie est indisponible ; Awa reçoit une notification à l'arrivée (voir Responsive & Platform pour iOS).

### UJ-4 — Ibou, 19 ans, consulte sa progression sur son téléphone

Ibou Diallo, n°7, ailier droit, compte joueur. Référence : [mockups/vue-joueur.html](mockups/vue-joueur.html).

1. Il ouvre la PWA : en-tête broadcast avec son numéro, « Ta progression » en une phrase, chiffres clés de la dernière Séance.
2. Il descend sur « Ma dernière Séance » : frise des Statuts, Alerte à 18′ expliquée — « Pas une sanction, un signal. »
3. Il ouvre Progrès : courbes du mois contre sa Référence individuelle et ses records.
4. **Climax :** « Vitesse max +2 km/h depuis le début du test » — record de sprint battu, 31,4 km/h.
5. Dans Mes données, il voit son Consentement, ce qui est collecté, et peut exporter ses données ou retirer son Consentement.

Garde-fou : il ne voit jamais les données de ses coéquipiers ; aucune surface ne charge de données d'un autre Joueur. `[ASSUMPTION]` La carte « Qui a consulté » de la maquette est un résumé du journal d'accès (FR-32, réservé à l'admin dans le PRD) ; à confirmer.

### UJ-5 — Le président du Club pilote décide de continuer

Le président du Club pilote, à la fin du premier mois de test.

1. Il reçoit le Rapport club mensuel, produit à la main pendant les tests (hors PWA en v1).
2. Dans la PWA, il ouvre les Rapports d'après-match de son Club et les données agrégées, en lecture seule (FR-3).
3. Il présente le tout à son bureau.
4. **Climax :** le bureau confirme la poursuite du test.

Limite : il ne peut ni modifier une Séance ni voir un autre Club. La surface de données agrégées du président n'est pas encore spécifiée.

## Responsive & Platform

| Contexte | Règle |
|---|---|
| Tablette paysage 1180×820 | Mise en page de référence des surfaces staff. `[ASSUMPTION]` En portrait, le rail passe sous le terrain. |
| Téléphone portrait 390×844 | Une colonne, `tab-bar` (joueur), bouton principal à portée du pouce. Le Rapport mobile reprend l'ordre : bandeau, 4 chiffres en grille 2×2, 3 alertes, zones chaudes, liste des Joueurs. |
| Ordinateur | Mêmes tokens ; surfaces de saisie et d'administration pensées pour clavier et souris. |
| Hors ligne | Service worker : application en cache ; dernières Séances, Rapports et Schémas tactiques ouverts stockés dans IndexedDB (NFR-2). |
| Réseau faible | Écrans principaux < 3 s une fois en cache (NFR-3) ; vidéo jamais chargée automatiquement en 3G. |
| iOS Safari | Pas d'API Vibration : l'Alerte de décrochage est visuelle seulement. Notifications push seulement si la PWA est installée sur l'écran d'accueil (iOS 16.4+) ; sinon l'état « vidéo disponible » est visible au prochain accès `[ASSUMPTION]`. |
| Capteurs | La PWA ne parle jamais aux Gilets (pas de Web Bluetooth) ; tout passe par la Plateforme. |
| Installation | Invitation à installer la PWA proposée au staff dès la première Séance `[ASSUMPTION]` (nécessaire aux notifications sur iOS). |

## Inspiration & Anti-patterns

- **Repris de FotMob** (appréciée de Sidy) : cartes claires et denses, page joueur façon appli de foot, chiffres clés en tête.
- **Repris des habillages TV sportifs** : bug « EN DIRECT » et chrono, bandeau bas d'alerte, dalles condensées, face-à-face statistique en barres miroir.
- **Repris du tableau noir** : terrain à la craie comme toile pour le banc comme pour le Tableau tactique.
- **Rejeté — tableau de bord encombré** : pas de grilles de graphiques ; un écran, trois couleurs, une alerte (PRD §4.4).
- **Rejeté — lorem ipsum et zéros de remplissage** : données plausibles, états d'attente explicites.
- **Rejeté — classements entre Joueurs** dans la Vue joueur.
- **Rejeté — prédictions présentées comme des certitudes** (prédictions et conseils de remplacement hors v1).
