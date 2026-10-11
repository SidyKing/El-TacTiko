# El TacTiko — Prochaines actions

Source : `.memlog.md` de la session de brainstorming du 2026-10-11. Les phases sont ordonnées par dépendance : chacune s'appuie sur les résultats de la précédente.

**[CRITIQUE]** = l'une des 5 tâches qui conditionnent tout le reste.

---

## Phase 0 — Validation (avant tout achat)

- [ ] **[CRITIQUE]** Rencontrer le contact à la présidence de la LSFP pour présenter El TacTiko et obtenir son appui.
  - Pourquoi : le risque d'une interdiction par la Ligue ou la FIFA est à valider « avant d'acheter quoi que ce soit ». Le contact LSFP est un atout identifié, et la Ligue est vue comme le client à long terme.
- [ ] **[CRITIQUE]** Vérifier le règlement IFAB/FIFA sur les appareils électroniques portés (EPTS) et l'autorisation de la Ligue en match officiel de L1/L2.
  - Pourquoi : si c'est interdit, le plan B est un usage à l'entraînement seul. Cela change le périmètre du MVP.
- [ ] Vérifier si une tablette est autorisée sur le banc pendant le match.
  - Pourquoi : c'est une contrainte validée. Si la tablette est refusée, le contournement prévu est un analyste en tribune qui transmet à l'adjoint.
- [ ] Préparer la conformité CDP (loi 2008-12) : modèle de consentement écrit, déclaration CDP, exigences d'hébergement du VPS.
  - Pourquoi : la parade validée contre une fuite des données de santé est « conformité CDP dès le jour 1 ».

## Phase 1 — Faisabilité technique

- [ ] **[CRITIQUE]** Tester la couverture 4G dans les stades pilotes un jour de match, avec la foule.
  - Pourquoi : il faut éviter que la 4G lâche au premier match devant le président. Le réseau est saturé les jours de match, et l'architecture retenue envoie l'analyse sur un VPS.
- [ ] Comparer les gilets GPS du marché disponibles en marque blanche : précision, IP67, confort, tissu respirant, capteur dans le dos.
  - Pourquoi : la décision est une V1 en marque blanche et une conception propre en V2, pour ne pas s'enliser dans le matériel (leçon Jawbone). Les gilets inconfortables seraient retirés par les joueurs.
- [ ] Trancher entre une puce 4G/IoT par gilet et un mini-boîtier passerelle (LoRa vers 4G, avec mémoire tampon), le mode tampon sur chaque gilet étant obligatoire dans les deux cas.
  - Pourquoi : la question « le boîtier est-il nécessaire ? » reste ouverte. L'arbitrage porte sur 25 abonnements SIM et une batterie plus grosse face à un boîtier supplémentaire.
- [ ] Prototyper la caméra sur mât télescopique de 6 à 8 m en bord de terrain, avec enregistrement HD en local et flux basse résolution vers le VPS.
  - Pourquoi : beaucoup de stades n'ont pas de tribune haute, et la caméra/IA porte les stats ballon (passes, tirs) dans l'architecture hybride B+C.
- [ ] Choisir le VPS : hébergeur local ou en Afrique, conforme CDP, coûts maîtrisés (compression, archivage à froid).
  - Pourquoi : la décision finale place l'analyse sur un VPS et la tablette n'affiche que les résultats. Il y a aussi le risque des coûts en devises et l'explosion des coûts VPS et vidéo HD.
- [ ] Identifier deux fournisseurs de composants et étudier l'assemblage local à Dakar.
  - Pourquoi : risque de blocage en douane chez un fournisseur unique, et taxes à l'import.

## Phase 2 — Pilote

- [ ] **[CRITIQUE]** Recruter 2 ou 3 clubs pilotes, dont un club de Ligue 2, en vendant au club ou au président plutôt qu'au coach.
  - Pourquoi : lancer avec 30 clubs d'un coup serait ingérable. Un club de L2 est plus motivé car la montée se joue à rien, et vendre au président protège contre un renvoi du coach.
- [ ] Démarrer par le mode entraînement (comparaison de deux systèmes, par exemple 4-3-3 contre 3-5-2) avant tout match officiel.
  - Pourquoi : la décision MoSCoW le place en « Indispensable ». Il n'est pas soumis au règlement de match et permet de calibrer les données.
- [ ] Faire signer à chaque joueur le consentement et la charte de données, et activer son droit de regard sur ses propres données.
  - Pourquoi : les joueurs craignent que les données servent contre eux. La transparence les transforme en ambassadeurs, et c'est aussi une obligation CDP.
- [ ] Former sur place l'ensemble du staff et désigner un responsable du kit (valise numérotée, caution).
  - Pourquoi : il y a des coachs méfiants envers la technologie, la leçon des technologies importées sans formation, et le risque de vol ou de perte en déplacement.
- [ ] Calibrer les mesures avec des relevés manuels et afficher un indice de fiabilité.
  - Pourquoi : des données fausses font perdre la confiance du coach en un seul match.
- [ ] Définir et suivre chaque semaine les indicateurs d'adoption (connexions du coach, gilets portés) et de fiabilité.
  - Pourquoi : la plupart des échecs viennent de l'adoption, pas de la technologie (leçons miCoach et One Laptop per Child).
- [ ] Promettre de l'« après-match » et livrer le temps réel en bonus.
  - Pourquoi : c'est la parade validée contre une promesse de direct non tenue.

## Phase 3 — Business

- [ ] Finaliser les formules de crédit prépayé (Match seul, Saison, Pro) en FCFA, rechargeables via Wave et Orange Money, avec lecture seule et données conservées en cas de non-recharge.
  - Pourquoi : la décision retient un paiement mensuel prépayé « comme du crédit », sans commission sur transfert pour l'instant, face au budget limité des clubs.
- [ ] Concevoir le rapport de valeur mensuel envoyé au président à chaque recharge.
  - Pourquoi : c'est le « reçu » qui justifie la recharge suivante. Il répond au risque d'un bouche-à-oreille « ça ne sert à rien ».
- [ ] Démarcher un sponsor dès le pilote (opérateur télécom ou fintech), qui rechargerait au nom du club, voire fournirait une APN dédiée.
  - Pourquoi : il faut éviter l'épuisement sans revenus. Il faut aussi ancrer l'habitude avant le départ du sponsor (leçon des logiciels sponsorisés puis abandonnés).
- [ ] Déposer des demandes de financement DER/FJ.
  - Pourquoi : c'est la parade validée contre une équipe projet qui s'épuise sans revenus pendant un an.
- [ ] Étudier le statut Startup Act.
  - Pourquoi : il peut réduire les douanes et taxes à l'import du matériel.
- [ ] Candidater aux incubateurs, par exemple CTIC Dakar.
  - Pourquoi : c'est un soutien prévu dans la parade contre l'épuisement de l'équipe projet.

## Phase 4 — Produit / BMAD

- [ ] Passer `brainstorm-intent.md` dans `bmad-product-brief`.
  - Pourquoi : le MoSCoW du MVP pilote (familles A à G) est validé et doit devenir un brief formel.
- [ ] Produire le PRD avec `bmad-prd` : un écran banc « feu tricolore » (1 écran, 3 couleurs, 1 alerte), un mode entraînement, un mode hors-ligne avec tampon, une interface en wolof et français.
  - Pourquoi : une interface trop compliquée ne serait jamais regardée par le coach. Il faut aussi commencer par un seul besoin (leçon Hudl).
- [ ] Concevoir l'architecture avec `bmad-architecture` : gilets, passerelle, VPS, tablette en affichage seul, caméra et IA vidéo, synchronisation par horloge commune et mode dégradé.
  - Pourquoi : il faut formaliser l'hybride B+C et la décision « analyse sur VPS ». Le hors-ligne est l'avantage concurrentiel.
- [ ] Prévoir dans le PRD que l'analyste corrige manuellement les passes et tirs, et que ces corrections servent à ré-entraîner l'IA vidéo.
  - Pourquoi : il n'existe pas d'historique numérique du championnat. Chaque match enregistré devient un actif unique.
