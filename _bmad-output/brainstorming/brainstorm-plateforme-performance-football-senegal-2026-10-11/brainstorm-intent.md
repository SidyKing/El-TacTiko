---
projet: El TacTiko
source: brainstorming 2026-10-11 (.memlog.md)
usage: entrée pour bmad-product-brief / bmad-prd
---

# El TacTiko : intention produit

## Vision en une phrase
Une plateforme d'analyse de performance (capteurs + vidéo/IA + historique) conçue pour les clubs de Ligue 1 et Ligue 2 sénégalaises. Elle fonctionne en match comme à l'entraînement, même sans 4G ni électricité, et doit devenir à terme l'infrastructure de données du football sénégalais.

## Problème & contexte
- Au Sénégal, l'espace est vide : aucun outil de suivi de performance n'est adapté aux clubs de L1/L2.
- Les solutions étrangères (Catapult, STATSports) sont vendues en euros, sans support local ni français/wolof, et ne sont pas pensées pour les terrains locaux.
- Les contraintes terrain sont fortes : 4G saturée ou absente les jours de match, électricité instable, chaleur, hivernage (juillet-octobre, terrains boueux), stades souvent sans tribune haute, budgets serrés.
- Le championnat n'a pas d'historique numérique et tous les matchs ne sont pas filmés.
- Métriques visées : km parcourus, sprint max, passes et tirs. On les croise avec les infos de match et l'historique pour détecter les baisses de forme et appuyer les changements et repositionnements. À l'entraînement, l'outil sert à tester des systèmes de jeu.

## Utilisateurs & acheteurs
- **Acheteur : le club, via son président.** On vend au club et non au coach, car l'outil doit survivre à un changement d'entraîneur.
- **Utilisateurs :** le coach (écran banc, mi-temps, entraînement), le préparateur physique (charge, fatigue, reprise après blessure), l'analyste (correction des actions détectées par l'IA) et les joueurs (accès à leurs propres données).
- **Payeurs alternatifs :** un sponsor ou un mécène peut recharger le crédit au nom du club.
- **Client à long terme : la Ligue (LSFP).** Les clubs sont la porte d'entrée.
- **Atout :** un contact siège à la présidence de la LSFP.

## Proposition de valeur / différenciation
- **Le hors-ligne est l'avantage concurrentiel.** Le kit marche sans 4G ni électricité (batterie, solaire, mode tampon), ce que les solutions européennes ne font pas. C'est un produit « conçu pour l'Afrique ».
- **Lecture en 3 secondes.** Un écran, trois couleurs (feu vert/orange/rouge par joueur, par rapport à sa propre moyenne) et une alerte. Interface en wolof et en français.
- **Fossé défensif.** Support local, wolof, historique du championnat construit match après match, vidéothèque qui manque à la Ligue, partenariat avec la Ligue.
- **Transparence joueur.** Le joueur voit ce que le staff voit et dispose d'un passeport data. Les joueurs méfiants deviennent ainsi des ambassadeurs.

## Architecture retenue
- **Hybride capteurs + caméra/IA.**
  - Les gilets capteurs (GPS précis, capteur dans le dos, tissu respirant, étanches IP67) mesurent le physique : km, vitesse, sprints, accélérations, cardio.
  - La caméra et l'IA vidéo mesurent le jeu avec ballon : passes, tirs, pertes, positions collectives.
  - Une horloge commune synchronise capteurs et vidéo. Un numéro géant ou une couleur sur le gilet aide l'IA à identifier les joueurs.
- **Transmission.** Le mode tampon est indispensable : chaque gilet stocke tout et se synchronise après coupure.
  - **Question ouverte :** faut-il un boîtier bord-terrain réduit à une passerelle (LoRa vers 4G, avec mémoire tampon, sans calcul) ou une puce 4G/IoT (LTE-M/NB-IoT) dans chaque gilet qui envoie directement au VPS ?
  - Le boîtier implique un équipement de plus. La puce par gilet implique 25 abonnements SIM, des batteries plus grosses et une dépendance à la couverture du stade.
- **Vidéo.** La caméra est montée sur un mât télescopique de 6 à 8 m. L'enregistrement HD se fait en local, un flux basse résolution part en direct vers le VPS, et la HD est envoyée à la mi-temps ou après le match.
- **Analyse sur un VPS dans le cloud** (hébergeur local ou africain, conforme CDP). La tablette ne fait qu'afficher : tablette durcie fournie, ou appli sur n'importe quelle tablette Android.
- **Deux niveaux de délai.** Les données physiques arrivent en direct. Les stats ballon arrivent à la mi-temps, puis complètes après le match.
- **Mode dégradé.** Si la caméra tombe, on garde le physique. Si un gilet tombe, la vidéo garde le positionnement.
- **Correction manuelle.** L'analyste corrige les actions après le match, et ces corrections servent à ré-entraîner l'IA sur le football sénégalais.
- **Matériel V1.** Capteurs du marché en marque blanche. La conception propre attend la V2, une fois qu'il y a des clients payants.
- **Kit mobile.** Une valise numérotée (gilets + caméra + mât) part avec le club pour les matchs à l'extérieur.

## Modèle économique
- **Crédit mensuel prépayé**, comme un crédit téléphonique, payé en FCFA via Wave ou Orange Money.
  - Sans recharge, l'appli passe en lecture seule et les données restent conservées.
- **Formules :** « Match seul », « Saison » (matchs + entraînements) et « Pro » (+ IA vidéo + prédictions, vidéo facturée dans Pro).
- **Recharge possible par un sponsor ou un mécène.** Caution sur le kit matériel, ou kit inclus dans la recharge.
- **Chaque recharge s'accompagne d'un rapport de valeur envoyé au président.** C'est le reçu qui justifie la recharge suivante.
- **Commission sur les transferts : écartée pour l'instant**, à rediscuter plus tard.

## Périmètre du pilote (MoSCoW)
- Le MoSCoW proposé par le coach a été validé, avec une modification : **le mode entraînement passe en Indispensable**.
  - Ce mode compare deux systèmes de jeu, par exemple 20 min en 4-3-3 puis 20 min en 3-5-2, sur la distance, le pressing et les récupérations.
- **Indispensable :** validation LSFP avant tout achat ; 2 ou 3 clubs pilotes dont un de L2 ; gilets GPS du marché en marque blanche ; envoi vers le VPS avec mode tampon (puce 4G par gilet ou mini-boîtier, tranché après le test de couverture) ; analyse VPS (km, vitesse max, sprints, accélérations) ; tablette banc en feu tricolore avec alerte de décrochage ; passes et tirs après le match via la caméra sur mât, corrigés par un analyste ; rapport d'après-match (WhatsApp/PDF) et historique par joueur ; consentement et conformité CDP ; suivi de l'adoption ; mode entraînement.
- **Important :** résumé automatique de mi-temps ; indice de fatigue et risque de blessure ; crédit prépayé Wave/Orange Money (pilote gratuit ou sponsorisé) ; deuxième tablette en miroir.
- **Bonus :** IA vidéo automatique ; prédictions et conseils de remplacement ; passeport data et appli joueur ; fiche adversaire ; location aux académies et navétanes.
- **Pas maintenant :** capteurs maison ; commission sur les transferts ; classement national et données pour médias ou paris ; saisie vocale en wolof ; clips TikTok.
- **Pourquoi l'entraînement est la porte d'entrée :** pas de règlement de match à respecter, pas de problème d'accès au banc, et les données sont calibrées avant le premier match officiel.
- **Pilote :** 2 ou 3 clubs, dont un de Ligue 2.
- **Promesse :** on promet l'analyse « après-match » et on livre le direct en bonus.
- **Mesures du pilote :** l'adoption (connexions du coach, gilets portés) autant que la précision.

## Contraintes & risques clés avec parades
Les 15 contraintes et les 16 parades ont toutes été validées. En condensé :
- **Réseau saturé ou absent :** mode tampon, test de couverture de chaque stade, partenariat opérateur (APN dédiée ou priorité de débit).
- **Électricité :** kit 100 % batterie et panneau solaire.
- **Chaleur et hivernage :** matériel IP67 testé localement.
- **Règlement IFAB/FIFA sur les EPTS et tablette au banc :** valider avec le contact LSFP avant tout achat.
  - Contournement : un analyste en tribune transmet à l'adjoint.
  - Plan B : usage à l'entraînement seulement.
- **Données fausses :** calibrage par mesures manuelles et indice de fiabilité affiché.
- **Coachs méfiants ou interface trop complexe :** un seul écran, interface wolof/français, maquette testée avec un vrai coach, coach ambassadeur, formation sur place.
- **Joueurs méfiants ou gilets inconfortables :** charte de données signée, accès du joueur à ses données, prototype testé par les joueurs.
- **Données personnelles (loi 2008-12, CDP) :** consentement écrit, déclaration CDP, chiffrement, accès par rôle dès le premier jour.
- **Peu de compétences data dans les clubs :** analyste mutualisé et rapports automatiques.
- **Vol ou perte du matériel :** valise numérotée, responsable désigné, caution, assurance, traçage GPS des gilets.
- **Douanes et approvisionnement :** assemblage local ou régime Startup Act, deux fournisseurs, stock tampon.
- **Coûts en devises :** VPS local ou africain, achat groupé de composants, compression et archivage à froid de la vidéo.
- **Désabonnement :** suivi client mensuel et rapport de valeur au président.
- **Coach remplacé en cours de saison :** vendre au club et former tout le staff.
- **Prédictions erronées :** afficher des tendances et des probabilités, jamais des certitudes. Le coach décide.
- **Concurrent étranger à prix cassé :** s'appuyer sur le fossé local.
- **Lancement trop large :** 2 ou 3 clubs pilotes.
- **Équipe sans revenus :** subventions (DER/FJ, Startup Act, CTIC Dakar) et un sponsor dès le pilote.
- **Pas d'historique :** chaque match enregistré devient un actif unique.

## Insights de synthèse
- **La plupart des échecs viennent de l'adoption, pas de la technologie.** Leçons de Jawbone, miCoach et des technologies importées sans maintenance : un technicien local, de la formation et un usage mesuré chaque semaine.
- **Commencer par un seul besoin simple**, comme Hudl l'a fait. Viser un prix bas, de la simplicité et une présence terrain, comme Wave.
- **L'humain d'aujourd'hui fabrique l'automatisation de demain :** la correction manuelle par l'analyste entraîne la future IA vidéo.
- **L'historique, la vidéothèque et le contact LSFP** font d'El TacTiko l'infrastructure de données du football sénégalais.

## Questions ouvertes à trancher
- Boîtier passerelle ou puce 4G/IoT par gilet (voir Architecture) ?
- Le règlement LSFP/FIFA autorise-t-il les EPTS en match officiel et la tablette au banc ?
- Quand parler au partenaire LSFP : avant le prototype pour co-construire, ou après pour montrer du concret ?
- Calendrier des tests : pré-saison ou en saison ? Quelles sont les dates de la saison sénégalaise ?
- Les données de vitesse et de distance restent-elles fiables sur terrain boueux en hivernage ?
- Prix des formules en FCFA et choix entre caution et kit inclus.
- Qui manipule les capteurs le jour du match (kitman, analyste, équipe El TacTiko) ?
- Propriété des données d'un joueur lorsqu'il est transféré.

## Prochaines étapes
1. Valider la conformité réglementaire (EPTS, tablette au banc) avec le contact LSFP avant tout achat de matériel.
2. Trancher l'architecture de transmission et tester la couverture 4G des stades pilotes.
3. Sélectionner 2 ou 3 clubs pilotes, dont un de Ligue 2, et démarrer par le mode entraînement.
4. Faire tester la maquette de l'écran banc par un vrai coach. Faire tester les gilets en marque blanche par des joueurs.
5. Engager les démarches CDP, chercher des subventions (DER/FJ, Startup Act, CTIC) et un sponsor pour le pilote.
6. Passer en bmad-product-brief, puis en bmad-prd.
