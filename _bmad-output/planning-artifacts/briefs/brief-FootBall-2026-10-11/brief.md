---
title: "Product Brief : El TacTiko"
status: draft
created: 2026-10-11
updated: 2026-10-11
---

# Product Brief : El TacTiko

## Résumé

El TacTiko est une plateforme d'analyse de performance pour les clubs de football sénégalais. Les joueurs portent des gilets GPS ; une caméra filme le terrain. Un serveur dans le cloud croise ces données avec l'historique des matchs, et le coach lit le résultat sur une tablette : qui décroche, qui doit sortir, quel système de jeu fonctionne le mieux.

Les solutions existantes (Catapult, STATSports, Veo…) sont pensées pour l'Europe : elles coûtent cher, sont payées en devises et supposent une bonne connexion internet. Au Sénégal, la 4G sature les jours de match et l'électricité manque souvent au stade. El TacTiko part de ces contraintes : il fonctionne sans réseau, se paie comme du crédit téléphonique via Wave ou Orange Money, et parle français et wolof.

Le projet vise d'abord les 32 clubs professionnels (16 en Ligue 1, 16 en Ligue 2). Il commencera plus petit : des équipes de five et de foot en salle, puis quelques clubs pilotes, en commençant par l'entraînement.

## Le problème

- Les coachs de Ligue 1 et de Ligue 2 décident des changements à l'œil. Ils n'ont aucune mesure de la fatigue, des distances ou de l'intensité de leurs joueurs.
- Le championnat n'a pas d'historique numérique, et tous les matchs ne sont pas filmés.
- Les outils professionnels existent, mais ils restent hors de portée :
  - Catapult One coûte environ 180 $ par joueur et par an ;
  - les offres d'équipe sont sur devis ;
  - les caméras intelligentes demandent un abonnement et un envoi vers le cloud.
- Les clubs ont peu de budget, paient mal leurs joueurs et n'ont pas d'analyste data.
- Aujourd'hui, le travail se fait au chronomètre, sur papier ou à l'intuition. Conséquences : des blessures qu'on aurait pu éviter, des changements tardifs, des systèmes de jeu jamais vraiment évalués, et des joueurs mal valorisés quand ils sont transférés.

## La solution

1. **Capter.**
   - Des gilets GPS mesurent la partie physique : km parcourus, vitesse maximale, sprints, accélérations.
   - Une caméra sur un mât mesure le jeu avec ballon : passes et tirs.
   - Chaque gilet garde ses données en mémoire et les renvoie quand le réseau revient.
2. **Analyser.** Un serveur cloud (VPS) fait tout le calcul et construit l'historique de chaque joueur.
3. **Afficher.** La tablette du banc ne fait qu'afficher :
   - chaque joueur est vert, orange ou rouge par rapport à sa propre moyenne ;
   - une alerte se déclenche quand un joueur décroche ;
   - un rapport d'après-match est envoyé sur WhatsApp ou en PDF.
4. **Entraîner.** Le mode entraînement compare deux systèmes de jeu, par exemple 20 minutes en 4-3-3 puis 20 minutes en 3-5-2.

Le temps réel est un bonus. La promesse ferme, c'est l'analyse après le match.

## Ce qui nous distingue

- **Le hors-ligne d'abord.** Le kit fonctionne sur batterie et garde les données en mémoire, là où les concurrents supposent du réseau.
- **Le prix et le paiement.** Un crédit mensuel prépayé en FCFA, via Wave ou Orange Money, au lieu d'un abonnement en devises. `[HYPOTHÈSE : nettement moins cher que 180 $ par joueur et par an]`
- **La proximité.** Support sur place, interface en français et en wolof, présence dans les stades.
- **Un historique que personne d'autre n'a.** Chaque match enregistré enrichit la seule base de données de performance du foot sénégalais, et la Ligue a intérêt à ce qu'elle existe.
- **Ce qui ne nous protège pas encore :** notre matériel. Au départ, on utilise des capteurs du marché à notre marque. Notre avance tient à l'exécution sur le terrain et à la relation avec la Ligue, pas à une technologie exclusive.

## Pour qui

- **Le club, à travers son président, est l'acheteur.** On vend au club plutôt qu'au coach, pour que l'outil survive à un changement d'entraîneur. Le président reçoit chaque mois un rapport de valeur qui justifie la recharge suivante.
- **Le coach et son adjoint** veulent savoir en 3 secondes qui doit sortir, et pouvoir justifier leurs choix.
- **Le préparateur physique** suit la fatigue et les retours de blessure.
- **Les joueurs** voient leurs propres données. Pour un jeune, c'est un CV chiffré à montrer aux recruteurs.
- **La Ligue (LSFP)** est le client à long terme : historique du championnat, vidéothèque, image moderne. Un contact siège à sa présidence.

## Comment on avance

1. **Valider le cadre.** On rencontre le contact à la Ligue avant tout achat de matériel. On vérifie aussi les règles CDP.
2. **Tester sur du five et du foot en salle.** C'est rapide, sans règlement fédéral et peu coûteux.
   - ⚠️ Le GPS ne fonctionne pas en salle, et il est peu précis sur un petit terrain. Pour ces tests, il faudra des capteurs de mouvement (accéléromètres), des balises radio autour du terrain ou la vidéo seule. `[À TRANCHER]`
3. **Lancer un pilote avec 2 ou 3 clubs de Ligue 1 ou de Ligue 2,** dont au moins un de Ligue 2, en commençant par le mode entraînement.
4. **Passer aux matchs officiels.** Le règlement FIFA (Loi 4) exige des capteurs certifiés « FIFA Quality » et l'accord de la Ligue pour transmettre les données au banc.

## Périmètre de la première version

- **Inclus :**
  - gilets GPS du marché à notre marque, avec mode tampon ;
  - envoi des données vers le serveur cloud ;
  - analyse physique : km, vitesse maximale, sprints, accélérations ;
  - tablette du banc en feu tricolore, avec alerte ;
  - passes et tirs après le match, par la vidéo, corrigés par un analyste ;
  - rapport d'après-match et historique de chaque joueur ;
  - mode entraînement ;
  - consentement des joueurs et conformité CDP ;
  - mesure de l'utilisation réelle.
- **Plus tard :**
  - résumé de mi-temps ;
  - indice de fatigue ;
  - paiement Wave / Orange Money (pendant les tests, l'accès peut être gratuit ou payé par un sponsor) ;
  - deuxième tablette en miroir ;
  - IA vidéo automatique, prédictions, appli joueur, fiche adversaire.
- **Exclu pour l'instant :** fabriquer nos propres capteurs, prendre une commission sur les transferts, vendre des données aux médias ou aux sites de paris, la saisie vocale en wolof.

## Critères de réussite

Mesurés pendant le pilote. `[HYPOTHÈSE : seuils à ajuster]`

- **Le coach s'en sert :** il ouvre l'application à au moins 80 % des séances et des matchs.
- **Les joueurs jouent le jeu :** au moins 90 % des gilets prévus sont portés.
- **Les données sont fiables :** l'écart avec des mesures faites à la main est inférieur à 5 % sur les distances.
- **Le club continue :** au moins 2 clubs pilotes sur 3 veulent poursuivre en payant.
- **La Ligue suit :** elle rend un avis favorable sur l'usage à l'entraînement, puis en match.

## Équipe et moyens

- **Sidy** : développeur, data scientist et analyste. Il est sénégalais et passionné de foot.
- **Theo** : développeur fullstack.
- **Ce qui manque :**
  - aucune compétence en électronique dans l'équipe, d'où des capteurs achetés et non fabriqués ;
  - pas encore de budget défini ;
  - pas de prix fixé.
- **Financements possibles :** DER/FJ, label Startup Act (avantages fiscaux et douaniers), incubateurs comme le CTIC Dakar, un sponsor télécom ou fintech.
- **Calendrier :** le plus tôt possible. La saison 2026-27 a démarré le 3 octobre 2026, donc le pilote en club se fera en cours de saison.

## Vision

Dans 2 ou 3 ans, El TacTiko serait la référence des données de performance du football sénégalais. Les 32 clubs professionnels l'utiliseraient, ainsi que les académies et les navétanes. La Ligue l'exploiterait pour l'historique du championnat et sa vidéothèque. Le même kit, conçu pour les réseaux faibles, pourrait ensuite s'exporter en Afrique de l'Ouest.

## Questions ouvertes

- Faut-il une puce 4G dans chaque gilet, ou un mini-boîtier qui relaie les données ? À trancher après un test de couverture dans les stades.
- Quels capteurs utiliser pour le five et le foot en salle ?
- Faut-il des capteurs certifiés « FIFA Quality » pour les matchs officiels, et à quel coût ?
- Quels prix pour les formules, et faut-il une caution ou un kit inclus ?
- Les données physiologiques des joueurs relèvent-elles du régime « données de santé » de la CDP ?
- À qui appartiennent les données d'un joueur quand il est transféré ?
- Quel budget de départ, et quels financements viser en premier ?
