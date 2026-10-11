---
title: "PRD : El TacTiko"
status: draft
created: 2026-10-11
updated: 2026-10-11
---

# PRD : El TacTiko

## 0. Objet du document

Ce PRD décrit ce que la première version d'El TacTiko doit faire. Il s'adresse à l'équipe (Sidy et Theo) et sert de base aux étapes suivantes de la méthode BMAD : UX, architecture, puis découpage en epics et en stories.

Il s'appuie sur trois documents, sans les recopier :
- le product brief : `_bmad-output/planning-artifacts/briefs/brief-FootBall-2026-10-11/brief.md` ;
- l'addendum du brief, qui contient la veille marché et réglementaire ;
- le brainstorming : `_bmad-output/brainstorming/brainstorm-plateforme-performance-football-senegal-2026-10-11/`.

Les termes du §3 (Glossaire) sont employés tels quels dans tout le document. Les exigences fonctionnelles (FR) sont numérotées de façon unique et stable. Les hypothèses non confirmées sont signalées par `[HYPOTHÈSE]` et regroupées au §12. Les choix techniques (capteurs, transmission, hébergement, contraintes des PWA) figurent dans `addendum.md`.

## 1. Vision

El TacTiko donne aux coachs du football sénégalais ce que seuls les grands clubs avaient jusqu'ici : savoir, chiffres à l'appui, qui court, qui décroche et quel système de jeu fonctionne.

Les joueurs portent des Gilets. Une Caméra filme la Séance. La Plateforme analyse tout dans le cloud, et le staff consulte les résultats dans une seule application web installable (PWA). Sur le banc, chaque joueur apparaît en vert, orange ou rouge selon son Statut. Après la Séance, un Rapport d'après-match et l'Historique de chaque joueur sont disponibles.

Le produit est conçu pour les conditions locales. Il continue de fonctionner quand la 4G sature ou que l'électricité manque, il est peu coûteux et il est pensé pour des staffs qui n'ont pas d'analyste data. Le déploiement se fait en trois temps :
1. des équipes de five et de foot en salle ;
2. 2 ou 3 clubs pilotes de Ligue 1 ou Ligue 2, à l'entraînement ;
3. les matchs officiels, après validation de la Ligue (LSFP).

## 2. Utilisateurs cibles

### 2.1 Besoins à satisfaire (Jobs To Be Done)

- **Coach :** savoir pendant la Séance qui baisse de régime, pour décider d'un changement ou d'un repositionnement, et pouvoir justifier ce choix ensuite.
- **Coach :** comparer objectivement deux systèmes de jeu à l'entraînement.
- **Coach :** expliquer visuellement à ses joueurs un système, des lignes, une circulation du ballon, une façon d'attaquer ou de défendre.
- **Préparateur physique :** connaître la charge de chaque joueur pour éviter les blessures et suivre les retours de blessure.
- **Analyste :** obtenir rapidement des passes et des tirs fiables, rattachés au bon joueur.
- **Joueur :** voir ses propres données, progresser, et disposer d'un profil chiffré à montrer.
- **Président du club :** voir ce que l'outil apporte, afin de décider de continuer à payer.
- **Équipe El TacTiko :** mesurer pendant les tests si l'outil est réellement utilisé et si les données sont fiables.

### 2.2 Hors cible en v1

- Les sélections nationales et les clubs étrangers.
- Les particuliers qui veulent suivre leurs performances seuls, sans club ni équipe.
- Les médias, les opérateurs de paris et le grand public.
- La Ligue en tant qu'utilisatrice directe de la Plateforme. Elle reste partenaire et cliente à long terme.

### 2.3 Parcours utilisateurs clés

`[HYPOTHÈSE]` Ces parcours ont été proposés par l'équipe produit, à la demande de Sidy. Ils sont à confronter à de vrais coachs.

- **UJ-1. Moussa voit son ailier décrocher pendant un match de five.**
  Moussa coache une équipe de five à Dakar, un mardi soir, sur un terrain synthétique extérieur.
  1. Il ouvre la PWA sur sa tablette, choisit son Équipe et lance une Séance de type « match ».
  2. Il distribue les Gilets. Chaque Gilet est déjà associé à un joueur, l'écran affiche « 10/10 Gilets actifs ».
  3. Pendant le match, la Tablette banc affiche le Statut de chaque joueur.
  4. À la 18e minute, Ibou passe à l'orange, puis au rouge : une Alerte de décrochage s'affiche. Moussa le fait sortir.
  5. À la fin, il clôture la Séance. Le soir même, il reçoit le Rapport d'après-match sur WhatsApp.

  **Cas limite :** si le réseau coupe, la Tablette banc indique « hors ligne, données à jour à 18:42 ». Les Gilets continuent d'enregistrer et tout se synchronise après la Séance.

- **UJ-2. Le coach d'un club de Ligue 2 compare le 4-3-3 et le 3-5-2 à l'entraînement.**
  Le coach d'un club pilote de Ligue 2 prépare le match du week-end.
  1. Il crée une Séance d'entraînement avec deux Phases, « 4-3-3 » puis « 3-5-2 », de 20 minutes chacune.
  2. Il bascule de l'une à l'autre en un geste sur la tablette.
  3. Après la Séance, l'écran de Comparaison de systèmes montre, phase par phase, la distance totale, le nombre de sprints et l'intensité de l'équipe.
  4. Il décide de garder le 3-5-2 et partage la comparaison avec son adjoint.
  5. Avant la séance suivante, il ouvre le Tableau tactique, dessine le 3-5-2 avec ses lignes et le circuit de relance du ballon, puis le montre aux joueurs sur la tablette.

- **UJ-3. Awa, analyste, valide les passes et les tirs le lendemain du match.**
  Awa est analyste, pour un club ou pour El TacTiko.
  1. Elle ouvre la Séance terminée dans la PWA, sur son ordinateur.
  2. La vidéo est disponible. Elle parcourt la liste des Actions ballon et, pour chacune, choisit le joueur, le type (passe réussie ou ratée, tir cadré ou non cadré) et l'instant.
  3. Quand elle valide, les statistiques ballon s'ajoutent au Rapport d'après-match et à l'Historique de chaque joueur.

  **Cas limite :** si la vidéo n'est pas encore envoyée, faute de réseau au stade, la Séance affiche « vidéo en attente » et Awa reçoit une notification dès qu'elle arrive.

- **UJ-4. Ibou, 19 ans, consulte sa progression sur son téléphone.**
  Ibou ouvre la PWA sur son téléphone, connecté avec son compte joueur.
  1. Il voit uniquement ses propres données : distance, vitesse maximale et sprints de la dernière Séance, et leur évolution sur le mois.
  2. Il constate que sa vitesse maximale a progressé de 2 km/h depuis le début du test.
  3. Il ne voit jamais les données de ses coéquipiers.

- **UJ-5. Le président du club pilote décide de continuer.**
  À la fin du premier mois de test, le président reçoit un Rapport club : nombre de Séances suivies, Alertes de décrochage, évolution de l'effectif. Il le présente à son bureau et confirme la poursuite du test.

  `[HYPOTHÈSE]` Ce rapport sera produit à la main pendant les tests (voir §6.2).

## 3. Glossaire

- **Club** : organisation cliente (club professionnel, équipe de five ou de foot en salle, académie). Un Club possède une ou plusieurs Équipes.
- **Équipe** : groupe de Joueurs suivi ensemble (par exemple l'équipe première). Elle appartient à un seul Club.
- **Joueur** : personne suivie. Il appartient à une Équipe et possède un Historique joueur.
- **Membre du staff** : utilisateur rattaché à un Club avec un Rôle.
- **Rôle** : coach, préparateur, analyste, président, joueur ou admin El TacTiko. Le Rôle détermine les droits d'accès.
- **Séance** : période de suivi d'une Équipe, de type « match » ou « entraînement ». Elle a un début, une fin et un terrain.
- **Phase** : sous-période nommée d'une Séance d'entraînement (par exemple « 4-3-3 »). Elle sert à la Comparaison de systèmes.
- **Kit** : ensemble de matériel prêté à un Club, composé de Gilets, éventuellement d'une Passerelle, d'une Caméra et d'une tablette.
- **Gilet** : capteur porté par un Joueur pendant une Séance. Un Gilet est associé à un seul Joueur pendant une Séance donnée.
- **Mode tampon** : capacité d'un Gilet ou d'une Caméra à stocker ses données localement et à les envoyer quand le réseau revient.
- **Passerelle** : relais optionnel au bord du terrain, qui transmet les données des Gilets vers la Plateforme. Il ne fait aucun calcul.
- **Caméra** : dispositif qui filme la Séance (par exemple sur un mât au bord du terrain).
- **Plateforme** : partie serveur, dans le cloud, qui reçoit, stocke et analyse toutes les données.
- **Tablette banc** : vue de la PWA utilisée par le staff pendant la Séance. Elle affiche, mais ne calcule pas.
- **Métriques physiques** : distance parcourue, vitesse maximale, nombre de sprints et nombre d'accélérations.
- **Référence individuelle** : moyenne glissante d'une métrique pour un Joueur, calculée sur ses Séances précédentes du même type.
- **Intensité** : distance parcourue par minute (m/min) par un Joueur, mesurée sur une fenêtre glissante. `[HYPOTHÈSE : définition v1, à affiner avec un préparateur physique]`
- **Statut** : vert, orange ou rouge. Il compare l'Intensité récente d'un Joueur à sa Référence individuelle d'Intensité.
- **Joueur convoqué** : Joueur déclaré présent pour une Séance par le coach. Sert de base au taux de port des Gilets.
- **Alerte de décrochage** : notification émise quand le Statut d'un Joueur passe au rouge.
- **Action ballon** : passe ou tir, rattaché à un Joueur et à un instant de la Séance.
- **Rapport d'après-match** : synthèse d'une Séance, avec Métriques physiques, Actions ballon validées et Statuts.
- **Historique joueur** : ensemble des données d'un Joueur sur toutes ses Séances.
- **Schéma tactique** : dessin enregistré sur un terrain virtuel, composé de positions de joueurs, de lignes, de flèches de déplacement et de trajectoires du ballon. Il peut comporter plusieurs Étapes. Il appartient à une Équipe.
- **Étape** : état successif d'un Schéma tactique, qui permet d'animer une séquence (par exemple une phase de relance en trois temps).
- **Tableau tactique** : écran de la PWA qui sert à créer, modifier et présenter les Schémas tactiques.
- **Comparaison de systèmes** : vue qui met en regard les Métriques physiques collectives de deux Phases.
- **Indice de fiabilité** : indicateur de qualité des données d'un Gilet sur une Séance (signal perdu, valeurs aberrantes).
- **Consentement** : accord écrit et enregistré d'un Joueur pour la collecte et l'usage de ses données.

## 4. Fonctionnalités

### 4.1 Clubs, Équipes, comptes et Rôles

**Description :** l'admin El TacTiko crée un Club et invite ses Membres du staff. Le coach gère l'effectif de son Équipe. Chaque utilisateur n'accède qu'aux données de son Club, selon son Rôle. Les Joueurs peuvent avoir un compte en lecture seule sur leurs propres données (UJ-4).

#### FR-1 : Création de Club et d'Équipe
L'admin El TacTiko peut créer un Club, ses Équipes, et inviter des Membres du staff par numéro de téléphone ou par e-mail.
- Un Club peut contenir plusieurs Équipes.
- Une invitation expire au bout de 7 jours. `[HYPOTHÈSE]`

#### FR-2 : Gestion de l'effectif
Le coach peut ajouter, modifier et archiver des Joueurs dans son Équipe : nom, poste, numéro, date de naissance.
- Archiver un Joueur conserve son Historique joueur.

#### FR-3 : Contrôle d'accès par Rôle
La Plateforme doit restreindre chaque action et chaque donnée selon le Rôle et le Club de l'utilisateur.
- Un Joueur ne voit que ses propres données (réalise UJ-4).
- Un Membre du staff ne voit jamais les données d'un autre Club.
- Seuls le coach, le préparateur et l'analyste voient les Statuts de toute l'Équipe. Chaque Joueur voit ses propres Statuts (FR-29).
- Le président voit les Rapports d'après-match et les données agrégées de son Club, sans modifier les Séances.
- Si le coach quitte le Club, l'Équipe, ses Séances et ses Schémas tactiques restent la propriété du Club et sont transmis au nouveau coach.

#### FR-4 : Connexion simple
Les utilisateurs peuvent se connecter par code à usage unique, envoyé par SMS ou WhatsApp, ou par e-mail.
- La session reste ouverte 30 jours sur un appareil de confiance. `[HYPOTHÈSE]`

### 4.2 Kit et captation

**Description :** avant la Séance, le coach associe chaque Gilet à un Joueur, puis lance la Séance. Les Gilets enregistrent en continu et envoient leurs données à la Plateforme quand le réseau le permet, directement ou via une Passerelle. Sans réseau, le Mode tampon prend le relais. Réalise UJ-1 et UJ-2.

#### FR-5 : Inventaire du Kit
L'admin El TacTiko peut enregistrer les Gilets, les Passerelles et les Caméras d'un Kit et les attribuer à un Club.
- Chaque équipement a un identifiant unique et un état : actif, en panne ou perdu.
- Chaque Kit a un responsable désigné au sein du Club ; le dernier lieu connu de chaque Gilet est visible par l'admin El TacTiko (lutte contre la perte et le vol).

#### FR-6 : Association Gilet–Joueur
Le coach peut associer chaque Gilet à un Joueur pour une Séance. Par défaut, la Plateforme reprend les associations de la Séance précédente.
- Un Gilet ne peut être associé qu'à un seul Joueur par Séance.
- Le coach indique les Joueurs convoqués pour la Séance ; par défaut, ce sont les Joueurs associés à un Gilet.
- L'écran indique le nombre de Gilets actifs par rapport aux Joueurs convoqués, par exemple « 10/10 ».

#### FR-7 : Lancement et clôture de Séance
Le coach peut lancer une Séance (type match ou entraînement, Équipe, terrain) et la clôturer.
- Seules les données horodatées entre le début et la fin sont rattachées à la Séance, quel que soit le moment où elles arrivent (FR-8).
- Le coach peut corriger l'heure de début et de fin après coup.

#### FR-8 : Mode tampon et synchronisation
Les données enregistrées sans réseau doivent être envoyées automatiquement dès que la connexion revient, sans action de l'utilisateur.
- Aucune donnée n'est perdue si la coupure dure moins que l'autonomie de stockage du Gilet. `[HYPOTHÈSE : au moins 3 heures]`
- La Plateforme indique pour chaque Séance si la synchronisation est complète ou partielle.

#### FR-9 : Sources de captation multiples
La Plateforme doit accepter les Métriques physiques de plusieurs types de capteurs (GPS en extérieur, capteurs de mouvement ou balises en salle) sans changer l'expérience du coach.
- Une Séance indique la source utilisée pour chaque Joueur.
- `[À TRANCHER]` Le capteur retenu pour le foot en salle (voir §11).

### 4.3 Analyse physique

**Description :** la Plateforme calcule les Métriques physiques de chaque Joueur, met à jour sa Référence individuelle et évalue la qualité des données. Réalise UJ-1, UJ-2 et UJ-4.

#### FR-10 : Calcul des Métriques physiques
La Plateforme calcule pour chaque Joueur et chaque Séance la distance parcourue, la vitesse maximale, le nombre de sprints et le nombre d'accélérations.
- Les seuils de sprint et d'accélération sont configurables par Club. `[HYPOTHÈSE : sprint au-delà de 25 km/h pour le football à 11]`
- Les métriques sont recalculées quand des données arrivent en retard (FR-8).

#### FR-11 : Référence individuelle
La Plateforme maintient pour chaque Joueur une Référence individuelle par type de Séance.
- Elle n'est pas affichée avant 3 Séances. Le Statut est alors marqué « en apprentissage ». `[HYPOTHÈSE]`

#### FR-12 : Calcul du Statut
Pendant et après une Séance, la Plateforme attribue à chaque Joueur un Statut (vert, orange ou rouge) en comparant son Intensité des dernières minutes à sa Référence individuelle.
- Les seuils sont configurables. `[HYPOTHÈSE : orange en dessous de 85 %, rouge en dessous de 75 % sur une fenêtre de 10 minutes]`

#### FR-13 : Indice de fiabilité
La Plateforme calcule un Indice de fiabilité par Joueur et par Séance et le montre partout où les Métriques physiques s'affichent.
- Une Séance dont l'Indice est faible est signalée et exclue de la Référence individuelle.

#### FR-14 : Calibration
L'équipe El TacTiko peut saisir des mesures manuelles (distance chronométrée, sprint sur 30 m) et les comparer aux Métriques physiques calculées.
- L'écart est affiché et historisé par Gilet. Il alimente SM-3.

### 4.4 Tablette banc

**Description :** pendant la Séance, la Tablette banc montre l'Équipe en un coup d'œil : un écran, trois couleurs, une alerte. Elle n'effectue aucun calcul. Réalise UJ-1.

#### FR-15 : Vue Statut de l'Équipe
La Tablette banc affiche chaque Joueur actif avec son numéro, son nom et son Statut, triés du plus critique au moins critique.
- L'écran est lisible en plein soleil : contraste du texte d'au moins 7:1, couleurs de Statut doublées d'une forme ou d'une lettre. Il est utilisable d'une seule main : zones tactiles d'au moins 48 px.
- Un toucher sur un Joueur affiche ses Métriques physiques de la Séance en cours.

#### FR-16 : Alerte de décrochage
La Tablette banc émet une alerte visuelle, et une vibration si l'appareil le permet, quand un Joueur passe au rouge.
- Une même alerte n'est pas répétée pendant 5 minutes pour le même Joueur. `[HYPOTHÈSE]`

#### FR-17 : Fraîcheur et mode hors ligne
La Tablette banc affiche à tout moment l'heure de la dernière mise à jour. Sans réseau, elle conserve le dernier état connu.
- Le message « hors ligne, données à jour à HH:MM » s'affiche dès que la dernière donnée a plus de 60 secondes.
- La PWA s'ouvre et affiche la dernière Séance même sans connexion.

#### FR-18 : Délai d'affichage
Quand le réseau est disponible, le Statut affiché a moins de 30 secondes de retard sur le terrain. `[HYPOTHÈSE]`
- Le temps réel reste un bonus : la promesse ferme est le Rapport d'après-match (voir §5).

### 4.5 Vidéo et Actions ballon

**Description :** la Caméra filme la Séance. La vidéo est envoyée à la Plateforme quand le réseau le permet. Un analyste saisit ou corrige les Actions ballon. Réalise UJ-3.

#### FR-19 : Enregistrement et envoi de la vidéo
La vidéo d'une Séance est rattachée à cette Séance et envoyée à la Plateforme, en direct si possible, sinon après la Séance.
- La Séance affiche l'état de la vidéo : en attente, en cours d'envoi ou disponible.
- L'analyste est notifié quand la vidéo est disponible.

#### FR-20 : Synchronisation vidéo et capteurs
La vidéo et les données des Gilets partagent la même horloge, pour qu'un instant de la vidéo corresponde aux données au même instant.
- Le décalage toléré est inférieur à 1 seconde. `[HYPOTHÈSE]`

#### FR-21 : Saisie et correction des Actions ballon
L'analyste peut créer, modifier et supprimer des Actions ballon depuis la vidéo : type, Joueur et instant.
- Types en v1 : passe réussie, passe ratée, tir cadré, tir non cadré, récupération, perte de balle.
- Une Action ballon est saisie en moins de 10 secondes, au clavier ou par raccourcis. `[HYPOTHÈSE]`
- Si une détection automatique existe plus tard, ses propositions passent par la même validation.

#### FR-22 : Données pour entraîner l'IA
Toutes les Actions ballon validées sont conservées avec leur extrait vidéo, pour pouvoir entraîner plus tard une détection automatique.
- `[NON-GOAL pour la v1]` La détection automatique elle-même.

### 4.6 Mode entraînement et Comparaison de systèmes

**Description :** le coach découpe une Séance d'entraînement en Phases nommées et compare leurs Métriques physiques collectives. C'est la porte d'entrée du pilote : aucune contrainte réglementaire et l'occasion de calibrer les données avant les matchs. Réalise UJ-2.

#### FR-23 : Phases d'entraînement
Le coach peut créer, nommer, démarrer et arrêter des Phases pendant une Séance d'entraînement, en un geste sur la tablette.
- Les Phases peuvent aussi être définies ou corrigées après la Séance.

#### FR-24 : Comparaison de systèmes
La PWA affiche côte à côte, pour deux Phases, la distance totale de l'Équipe, la distance par minute, le nombre de sprints, l'intensité moyenne et, quand les Actions ballon sont validées, le nombre de récupérations et de pertes de balle, ainsi que le détail par Joueur.
- `[HYPOTHÈSE]` Le pressing est approché par le nombre de récupérations et l'intensité dans les Phases sans ballon ; une mesure plus fine attend la v2.
- La comparaison peut porter sur deux Phases de Séances différentes.

#### FR-25 : Partage de comparaison
Le coach peut partager une Comparaison de systèmes avec son staff, sous forme de lien interne ou de PDF.

### 4.7 Tableau tactique

**Description :** le coach utilise la PWA comme un tableau noir numérique. Il place ses Joueurs, dessine les lignes, la circulation du ballon, la façon d'attaquer ou de défendre, et présente le résultat à l'Équipe, en causerie ou au bord du terrain. Réalise UJ-2.

#### FR-35 : Création de Schéma tactique
Le coach peut créer un Schéma tactique sur un terrain virtuel. Il y place des Joueurs de son effectif ou des pions génériques, ainsi que des adversaires et le ballon.
- Les formations courantes (4-4-2, 4-3-3, 3-5-2…) peuvent être posées en un geste, puis ajustées.
- Le terrain s'adapte au format : football à 11, five, foot en salle.

#### FR-36 : Dessin des intentions de jeu
Le coach peut dessiner des lignes (défensive, médiane, offensive), des flèches de déplacement, des trajectoires de passe et des zones.
- Chaque élément peut être nommé, coloré, déplacé et supprimé.
- Le dessin se fait au doigt sur tablette et à la souris sur ordinateur.

#### FR-37 : Étapes et animation
Le coach peut découper un Schéma tactique en Étapes et les faire défiler, avec une animation des déplacements entre deux Étapes.
- Une séquence d'au moins 10 Étapes est possible. `[HYPOTHÈSE]`

#### FR-38 : Présentation et partage
Le coach peut présenter un Schéma tactique en plein écran, et le partager avec son staff ou ses Joueurs (lien interne, image ou PDF).
- Un Joueur ne voit que les Schémas tactiques partagés avec son Équipe.
- Les Schémas tactiques sont consultables hors ligne une fois ouverts (NFR-2).

#### FR-39 : Bibliothèque de schémas
Le coach peut classer ses Schémas tactiques (par exemple « sortie de balle », « pressing haut », « coups de pied arrêtés »), les dupliquer et les retrouver.
- Un Schéma tactique peut être rattaché à une Séance ou à une Phase, pour relier l'intention de jeu aux Métriques physiques mesurées.

`[NON-GOAL pour la v1]` Générer automatiquement un Schéma tactique à partir des positions réelles mesurées.

### 4.8 Rapports et Historique joueur

**Description :** après chaque Séance, un Rapport d'après-match est généré automatiquement. L'Historique joueur s'enrichit à chaque Séance. Réalise UJ-1, UJ-3 et UJ-4.

#### FR-26 : Rapport d'après-match
La Plateforme génère un Rapport d'après-match d'une page par Séance : Métriques physiques par Joueur, Statuts, Alertes de décrochage et Actions ballon validées.
- Le rapport est disponible dans la PWA et en PDF.
- Il est mis à jour quand les Actions ballon sont validées.

#### FR-27 : Envoi WhatsApp
Le coach peut recevoir ou partager le Rapport d'après-match par WhatsApp.
- `[HYPOTHÈSE]` En v1, un simple lien de partage vers le PDF suffit, sans intégration de l'API WhatsApp Business.

#### FR-28 : Historique joueur
Le staff peut consulter l'Historique joueur : évolution des Métriques physiques et des Actions ballon par Séance, et filtrage par période et par type de Séance.

#### FR-29 : Vue joueur
Le Joueur peut consulter, depuis son téléphone, tout ce que le staff voit sur lui : ses Métriques physiques, leurs évolutions, ses Statuts, ses Alertes de décrochage et ses Actions ballon. Réalise UJ-4.
- Il ne voit aucune donnée d'un autre Joueur (FR-3).

### 4.9 Consentement et maîtrise des données

**Description :** aucune donnée n'est collectée sans le Consentement du Joueur. Le Joueur voit tout ce que le staff voit sur lui.

#### FR-30 : Enregistrement du Consentement
Le Club doit enregistrer le Consentement de chaque Joueur, accompagné de la charte des données signée (document signé ou validation dans la PWA), avant qu'un Gilet puisse lui être associé.
- Un Joueur sans Consentement ne peut pas être associé à un Gilet (FR-6).
- Pour un Joueur mineur, le Consentement d'un représentant légal est requis.

#### FR-31 : Retrait et export
Le Joueur peut demander l'export de ses données ou retirer son Consentement.
- Après un retrait, plus aucune donnée n'est collectée. Les données passées sont supprimées ou anonymisées selon la règle définie avec la CDP. `[À TRANCHER]`

#### FR-32 : Journal d'accès
La Plateforme conserve un journal des consultations et des exports de données joueur, consultable par l'admin El TacTiko.

### 4.10 Suivi de l'adoption

**Description :** pendant les tests, l'équipe El TacTiko doit savoir si l'outil est réellement utilisé. Ce suivi est interne.

#### FR-33 : Indicateurs d'usage
La Plateforme mesure, par Club et par semaine :
- le nombre de Séances lancées ;
- le taux de Gilets portés par rapport aux Joueurs convoqués ;
- les ouvertures de la Tablette banc pendant les Séances ;
- les consultations des Rapports d'après-match.

#### FR-34 : Tableau de bord interne
L'admin El TacTiko peut consulter ces indicateurs pour tous les Clubs, ainsi que l'Indice de fiabilité moyen par Club. Ce tableau alimente SM-1 à SM-4.

`[NOTE FOR PM]` **Direct et après-match.** La Tablette banc en direct est la cible de l'expérience (UJ-1) ; le Rapport d'après-match est la garantie. Si le réseau du terrain ne permet pas le direct, la valeur doit rester entière après la Séance : SM-1 compte donc les deux usages.

`[NOTE FOR PM]` **Préparateur physique.** En v1, il dispose des Métriques physiques, des Statuts et de l'Historique joueur. L'indice de fatigue et le suivi de retour de blessure arrivent en v1.1 (§6.2).

## 5. Non-objectifs

- El TacTiko **ne fabrique pas** ses propres capteurs en v1 : il utilise du matériel du marché à sa marque.
- El TacTiko **ne prend pas de décision** à la place du coach. Il montre des tendances et des statuts, jamais des certitudes.
- El TacTiko **ne promet pas le temps réel**. La promesse ferme est l'analyse après la Séance ; le direct est un bonus quand le réseau le permet.
- El TacTiko **ne détecte pas automatiquement** les passes et les tirs en v1.
- El TacTiko **ne vend pas** de données aux médias, aux opérateurs de paris ni à des tiers.
- El TacTiko **ne prend pas** de commission sur les transferts.
- El TacTiko **n'est pas** un outil de scouting ou de recrutement en v1.

## 6. Périmètre de la v1

### 6.1 Inclus

Priorité par Étape de déploiement (§10) :

| Étape | Fonctionnalités nécessaires |
|---|---|
| Étape 1 : five extérieur | 4.1 Clubs et Rôles · 4.2 Kit et captation · 4.3 Analyse physique · 4.4 Tablette banc · 4.8 Rapports (FR-26 à FR-28) · 4.9 Consentement · 4.10 Suivi de l'adoption · 4.7 Tableau tactique |
| Étape 2 : pilote clubs | 4.5 Vidéo et Actions ballon · 4.6 Mode entraînement · 4.8 Vue joueur (FR-29) |

`[HYPOTHÈSE]` Le Tableau tactique ne dépend pas des capteurs : il peut être livré tôt pour créer l'habitude chez le coach.

Contenu :

- Clubs, Équipes, comptes, Rôles et connexion simple (FR-1 à FR-4).
- Kit, association Gilet–Joueur, Séances, Mode tampon et sources de captation multiples (FR-5 à FR-9).
- Analyse physique, Statut, Indice de fiabilité et calibration (FR-10 à FR-14).
- Tablette banc avec Statuts, Alerte de décrochage et mode hors ligne (FR-15 à FR-18).
- Vidéo et saisie manuelle des Actions ballon (FR-19 à FR-22).
- Mode entraînement et Comparaison de systèmes (FR-23 à FR-25).
- Tableau tactique : Schémas tactiques, dessin, Étapes, présentation et bibliothèque (FR-35 à FR-39).
- Rapport d'après-match, partage WhatsApp, Historique joueur et vue joueur (FR-26 à FR-29).
- Consentement, export et journal d'accès (FR-30 à FR-32).
- Suivi de l'adoption (FR-33 et FR-34).

### 6.2 Hors v1

- **Paiement par crédit prépayé via Wave ou Orange Money :** reporté en v1.1. Pendant les tests, l'accès est gratuit ou payé par un sponsor ; l'activation des Clubs est manuelle.
- **Rapport club mensuel pour le président :** produit à la main pendant les tests (UJ-5), automatisé en v1.1.
- **Résumé automatique de mi-temps, indice de fatigue et risque de blessure :** v1.1.
- **Deuxième tablette en miroir :** v1.1. La PWA le permet déjà en partie, mais ce n'est pas un objectif de test.
- **Détection automatique des Actions ballon par IA :** v2, une fois assez de données validées accumulées (FR-22).
- **Prédictions et conseils de remplacement :** v2.
- **Passeport data partageable avec les recruteurs, fiche adversaire, location aux académies et aux navétanes :** v2.
- **Saisie vocale en wolof et clips vidéo pour les réseaux sociaux :** non planifiés.
- **Usage en match officiel de Ligue 1 ou Ligue 2 :** conditionné à l'accord de la LSFP et à des capteurs certifiés FIFA Quality (voir §9).

## 7. Indicateurs de réussite

**Principaux** (mesurés pendant les tests)
- **SM-1 : adoption par le coach.** Pourcentage des Séances où le coach ouvre la Tablette banc pendant la Séance ou consulte le Rapport d'après-match dans les 48 heures. Cible : au moins 80 %. `[HYPOTHÈSE]` Valide FR-15 et FR-33.
- **SM-2 : port des Gilets.** Gilets portés rapportés aux Joueurs convoqués. Cible : au moins 90 %. `[HYPOTHÈSE]` Valide FR-6 et FR-33.
- **SM-3 : fiabilité des distances.** Écart moyen entre la distance calculée et la mesure manuelle. Cible : moins de 5 %. `[HYPOTHÈSE]` Valide FR-10 et FR-14.
- **SM-4 : rétention des clubs pilotes.** À la fin du pilote, au moins 2 Clubs pilotes signent un engagement à continuer en formule payante dès la v1.1. Valide l'ensemble.

**Secondaires**
- **SM-5 : délai du Rapport d'après-match.** Rapport physique disponible moins d'une heure après la clôture de la Séance, quand le réseau le permet. Valide FR-26.
- **SM-6 : données complètes.** Au moins 95 % des Séances ont une synchronisation complète sous 24 heures. Valide FR-8.
- **SM-7 : traitement de la vidéo.** Actions ballon validées moins de 48 heures après la Séance. Valide FR-21.
- **SM-8 : usage du Tableau tactique.** Au moins un Schéma tactique créé ou présenté par coach et par semaine pendant le pilote. `[HYPOTHÈSE]` Valide FR-35 à FR-38.

**Contre-indicateurs (à ne pas optimiser)**
- **SM-C1 : nombre d'Alertes de décrochage.** Plus d'alertes ne veut pas dire plus de valeur : trop d'alertes finissent ignorées. Contrebalance SM-1.
- **SM-C2 : temps passé dans l'application.** Le coach doit comprendre en 3 secondes. Un temps élevé peut signaler une interface confuse. Contrebalance SM-1.
- **SM-C3 : volume d'Actions ballon saisies.** La justesse prime sur la quantité. Contrebalance SM-7.

## 8. Exigences non fonctionnelles transverses

- **NFR-1, application :** une seule PWA installable pour tous les Rôles. Elle fonctionne sur tablette Android, sur smartphone (Android et iOS) et sur ordinateur, dans les navigateurs récents. Elle s'adapte du téléphone à l'ordinateur.
- **NFR-2, hors ligne :** la PWA s'ouvre sans réseau et affiche les dernières données consultées. Les saisies faites hors ligne (Phases, corrections) sont synchronisées automatiquement ensuite.
- **NFR-3, réseau faible :** la PWA reste utilisable en 3G ou en 4G saturée. Les écrans principaux se chargent en moins de 3 secondes une fois l'application en cache. `[HYPOTHÈSE]`
- **NFR-4, langue :** interface en français en v1. Les libellés de la Tablette banc et de la vue joueur peuvent être traduits en wolof. `[HYPOTHÈSE : traduction wolof en v1.1]`
- **NFR-5, sécurité :** chiffrement des données en transit et au repos, cloisonnement strict entre Clubs (FR-3), journal d'accès (FR-32).
- **NFR-6, disponibilité :** la Plateforme vise 99 % de disponibilité. Une indisponibilité ne doit faire perdre aucune donnée de captation, grâce au Mode tampon.
- **NFR-7, coûts :** stockage et diffusion vidéo maîtrisés (compression, archivage des anciennes vidéos). Le coût d'hébergement par Club doit rester compatible avec un prix bas en FCFA. `[HYPOTHÈSE : à chiffrer en architecture]`

## 9. Contraintes et garde-fous

### 9.1 Réglementation sportive
- La Loi 4 de l'IFAB autorise, depuis 2019, les données des systèmes de suivi électronique (EPTS) dans la zone technique pendant un match. Il faut pour cela un appareil marqué FIFA Quality et l'accord de l'organisateur de la compétition.
- En v1, El TacTiko ne vise donc **que l'entraînement et les matchs non officiels** (five, foot en salle, amicaux).
- L'usage en match officiel de Ligue 1 ou Ligue 2 attend l'avis de la LSFP et le choix de capteurs certifiés. Le banc est limité à 7 officiels, ce qui compte si un analyste doit y prendre place.

### 9.2 Protection des données (CDP, loi 2008-12)
- Le traitement doit être déclaré à la CDP avant la collecte.
- Les données physiologiques (rythme cardiaque, charge) pourraient relever du régime des données de santé, qui impose une autorisation. `[À TRANCHER avec la CDP]`
- Consentement écrit des Joueurs, et d'un représentant légal pour les mineurs (FR-30).
- Hébergement conforme aux exigences de la CDP (voir `addendum.md`).

### 9.3 Matériel
- Capteurs du marché en marque blanche, sans électronique développée en interne.
- Le GPS ne fonctionne pas en salle et manque de précision sur un terrain de five : d'où les sources de captation multiples (FR-9).
- Le Kit doit résister à la chaleur, à la poussière et à la pluie de l'hivernage (matériel étanche de type IP67) et fonctionner entièrement sur batterie, avec une recharge possible par panneau solaire.
- Les Gilets doivent être confortables : tissu respirant, capteur placé dans le dos. Ils sont essayés par des joueurs avant tout achat en volume.
- Le Kit est transporté dans une valise numérotée, sous la responsabilité d'une personne désignée, et assuré.

## 10. Déploiement par étapes

1. **Étape 0, validation :**
   - rencontre avec le contact de la LSFP ;
   - démarches auprès de la CDP ;
   - choix des capteurs ;
   - test de couverture 4G dans les stades visés.
2. **Étape 1, five en extérieur :** 2 à 4 équipes, avec le GPS des Gilets. Le foot en salle attend la réponse à la Q1 (capteur adapté). `[HYPOTHÈSE]` On vise la stabilité de la captation, la Tablette banc et le Rapport d'après-match, ainsi que la calibration (SM-3).
3. **Étape 2, pilote :** 2 ou 3 Clubs de Ligue 1 ou Ligue 2, dont au moins un de Ligue 2. Le pilote démarre à l'entraînement (Mode entraînement), avec un suivi hebdomadaire de l'adoption.
4. **Étape 3, matchs :** amicaux, puis matchs officiels si la LSFP donne son accord et que les capteurs sont conformes.

### Conditions de passage et accompagnement

- **Avant tout achat de matériel :** avis de la LSFP obtenu via notre contact, déclaration CDP engagée.
- **Avant l'Étape 1 :** maquette de la Tablette banc testée par un vrai coach ; Gilets essayés par des joueurs.
- **Avant l'Étape 2 :** SM-3 atteint en Étape 1 (fiabilité des distances).
- **Accompagnement de chaque Club :** formation sur place de tout le staff, un technicien local joignable, un coach respecté comme ambassadeur, un point de suivi mensuel avec le président.

## 11. Questions ouvertes

1. Quel capteur utiliser en salle et en five : capteurs de mouvement, balises radio ou vidéo seule ? (FR-9)
2. Faut-il une puce 4G par Gilet ou une Passerelle ? À trancher après le test de couverture.
3. Quels capteurs certifiés FIFA Quality sont abordables pour l'Étape 3, et à quel coût ?
4. Les données physiologiques relèvent-elles du régime des données de santé de la CDP ?
5. Que deviennent les données passées après un retrait de Consentement, et quand un Joueur est transféré ?
6. Qui saisit les Actions ballon pendant les tests : un analyste El TacTiko ou un analyste du club ?
7. Quel prix fixer pour les formules de crédit (v1.1), et faut-il une caution sur le Kit ?
8. Faut-il une intégration WhatsApp Business ou un simple lien de partage suffit-il ? (FR-27)
9. Qui manipule les capteurs le jour de la Séance : l'intendant du club, un analyste, l'équipe El TacTiko ?
10. Les distances et vitesses restent-elles fiables sur terrain boueux pendant l'hivernage ?
11. Quel calendrier pour le pilote, la saison 2026-27 ayant démarré le 3 octobre 2026 ?

## 12. Index des hypothèses

- §2.3 : les parcours UJ-1 à UJ-5 sont proposés par l'équipe produit et restent à valider avec de vrais coachs.
- §2.3 (UJ-5) : le rapport club est produit à la main pendant les tests.
- FR-1 : une invitation expire au bout de 7 jours.
- FR-4 : la session dure 30 jours sur un appareil de confiance.
- FR-8 : le Gilet stocke au moins 3 heures de données.
- FR-10 : un sprint commence au-delà de 25 km/h (football à 11).
- FR-11 : la Référence individuelle s'affiche après 3 Séances.
- FR-12 : orange en dessous de 85 %, rouge en dessous de 75 %, sur une fenêtre de 10 minutes.
- FR-16 : une alerte ne se répète pas avant 5 minutes.
- FR-18 : le Statut a moins de 30 secondes de retard.
- FR-20 : vidéo et capteurs sont synchronisés à moins d'1 seconde.
- FR-21 : une Action ballon se saisit en moins de 10 secondes.
- FR-27 : un lien de partage WhatsApp suffit en v1.
- FR-37 : un Schéma tactique peut compter au moins 10 Étapes.
- SM-1 à SM-3 : seuils de réussite des tests.
- NFR-3 : chargement en moins de 3 secondes une fois en cache.
- NFR-4 : traduction wolof en v1.1.
- NFR-7 : coût d'hébergement par Club à chiffrer.
- §3 : l'Intensité est définie comme la distance par minute.
- FR-24 : le pressing est approché par les récupérations et l'Intensité sans ballon.
- §6.1 : le Tableau tactique est livré dès l'Étape 1.
- §10 : l'Étape 1 se limite au five en extérieur.
- SM-8 : un Schéma tactique par coach et par semaine.
