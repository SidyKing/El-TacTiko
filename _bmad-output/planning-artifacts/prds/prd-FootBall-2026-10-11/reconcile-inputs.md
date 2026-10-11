---
title: "Réconciliation des entrées : PRD El TacTiko"
created: 2026-10-11
compare: brief.md + addendum.md (brief), brainstorm-intent.md, .memlog.md (décisions validées) → prd.md + addendum.md (PRD)
---

# Réconciliation des entrées : PRD El TacTiko

Ce document liste ce que les entrées contiennent et que le PRD omet ou contredit. Il exclut les choix déjà connus et assumés : paiement Wave/Orange Money en v1.1, rapport mensuel au président fait à la main pendant les tests, wolof en v1.1, partage WhatsApp par simple lien, pas de commission sur les transferts, pas de matériel maison, v1 limitée à l'entraînement et aux matchs non officiels. Les idées du coach qui n'ont jamais été retenues (seuil « −20 % sur 10 min », adaptation chaleur/Ramadan, bien-être en emojis, etc.) ne sont pas considérées comme des écarts.

Priorité : **P1** = contradiction ou omission d'une décision validée ; **P2** = intention ou garde-fou affaibli ; **P3** = contexte utile manquant.

## 1. Périmètre MoSCoW validé

### P1. Le Tableau tactique n'est pas dans le MoSCoW validé
- **Entrées :** le MoSCoW validé (memlog, décisions finales ; brainstorm-intent, « Périmètre du pilote ») ne contient aucun tableau noir numérique ni éditeur de schémas. Le brief (« Inclus ») non plus. L'insight validé « commencer par un seul besoin simple, comme Hudl » et la parade « 1 écran, 3 couleurs, 1 alerte » vont dans le sens d'un périmètre resserré.
- **PRD :** §4.7 (FR-35 à FR-39), §6.1, JTBD « expliquer visuellement à ses joueurs un système » (§2.1) et étape 5 de UJ-2 ajoutent un module complet (formations, dessin, Étapes animées, bibliothèque, partage).
- **Écart :** ajout de périmètre non validé, qui contredit la logique « un seul besoin ». Aucune trace de la décision dans les entrées.
- **Suggestion :** soit consigner explicitement la décision de Sidy (date, raison) au §6.1 et la classer dans le MoSCoW (Indispensable, Important ou Bonus), soit déplacer FR-35 à FR-39 vers §6.2 (v1.1). Retirer l'étape 5 de UJ-2 si le module est reporté.

### P1. La Comparaison de systèmes perd le pressing et les récupérations
- **Entrées :** le mode entraînement, passé en Indispensable, compare deux systèmes « sur la distance, le pressing et les récupérations » (brainstorm-intent ; memlog, idée Coach Ziguinchor reprise dans la décision MoSCoW).
- **PRD :** FR-24 compare distance totale, distance par minute, sprints et intensité moyenne. Le pressing et les récupérations ont disparu.
- **Écart :** les deux indicateurs les plus « tactiques » de la fonction validée sont absents. Les récupérations relèvent des Actions ballon (vidéo), le pressing d'un indicateur physique ou positionnel.
- **Suggestion :** FR-24 (et FR-21 pour ajouter le type d'action « récupération / perte de balle ») ; sinon marquer explicitement le report en `[NON-GOAL v1]` avec la raison.

### P2. Le comparatif doit pouvoir s'appuyer sur la vidéo et l'analyste
- **Entrées :** l'architecture validée attribue au couple caméra/IA les « pertes, positions collectives ».
- **PRD :** FR-21 limite les Actions ballon à quatre types (passe réussie/ratée, tir cadré/non cadré).
- **Suggestion :** FR-21, ajouter au moins « perte de balle » et « récupération » si FR-24 les reprend.

## 2. Garde-fous de démarche et d'adoption

### P1. « Validation LSFP avant tout achat » n'est plus une porte bloquante
- **Entrées :** Indispensable n° 1 du MoSCoW validé ; brief « Démarche » étape 1 (« avant tout achat de matériel ») ; parade validée « valider avec le contact LSFP avant d'acheter quoi que ce soit ».
- **PRD :** §10 Étape 0 met sur le même plan la rencontre LSFP, la CDP, le choix des capteurs et le test de couverture, sans ordre ni condition.
- **Suggestion :** §10 Étape 0 : écrire que l'achat de matériel est conditionné à l'avis du contact LSFP (et au test de couverture pour Q2).

### P1. Tests avec de vrais utilisateurs avant de construire
- **Entrées :** prochaines étapes du brainstorming (n° 4) et parades validées : maquette de l'écran banc testée par un vrai coach « dès la maquette » ; prototype de gilet testé par les joueurs eux-mêmes (confort, chaleur).
- **PRD :** seule la mention `[HYPOTHÈSE]` du §2.3 (« à confronter à de vrais coachs »). Rien sur le test des gilets par les joueurs.
- **Suggestion :** §10 Étape 0 ou 1 : ajouter « test de la maquette Tablette banc avec un coach » et « essai de port des Gilets par des joueurs » comme critères de passage d'étape.

### P2. Accompagnement terrain : formation, technicien local, coach ambassadeur
- **Entrées :** insight validé « la plupart des échecs viennent de l'adoption, pas de la technologie » (Jawbone, miCoach, OLPC) ; parades validées : formation sur place, technicien local, coach ambassadeur, former tout le staff (pour survivre au départ du coach), suivi client mensuel.
- **PRD :** seul le suivi d'usage (FR-33, FR-34) est repris. La formation et la présence terrain, cœur de la différenciation « proximité », ne figurent nulle part.
- **Suggestion :** §10 (Étapes 1 et 2) : formation sur place de tout le staff, interlocuteur local désigné, point mensuel avec le club. Éventuellement une ligne au §1 Vision sur la présence terrain (« comme Wave »).

### P3. Plan de contournement « analyste en tribune »
- **Entrées :** parade validée : si la tablette est interdite au banc, un analyste en tribune transmet à l'adjoint ; plan B = entraînement seul.
- **PRD :** §9.1 cite la limite de 7 officiels au banc, sans le contournement.
- **Suggestion :** §9.1, une phrase pour l'Étape 3.

## 3. Matériel et Kit (contexte sénégalais)

### P2. Exigences terrain du Kit affaiblies
- **Entrées :** parades validées : « kit 100 % batterie + panneau solaire » ; matériel étanche IP67 testé localement ; gilet à tissu respirant, capteur dans le dos ; numéro géant ou couleur sur le gilet.
- **PRD :** §9.3 dit seulement « résister à la chaleur, à la poussière et à la pluie, fonctionner sur batterie ». Le solaire, l'IP67 et le confort du gilet ont disparu (le numéro est dans l'addendum).
- **Suggestion :** §9.3 : ajouter la recharge solaire (autonomie d'une journée de match sans prise), l'IP67, et le confort (tissu respirant, capteur dans le dos) comme critères de choix des capteurs. Le lien avec SM-2 (port des Gilets) est direct.

### P2. Vol et perte du Kit
- **Entrées :** parades validées : valise numérotée, responsable désigné, caution, assurance, traçage GPS des gilets ; kit mobile en valise pour les matchs à l'extérieur.
- **PRD :** FR-5 prévoit un état « perdu », sans responsable du Kit ni localisation des Gilets. La caution est renvoyée à Q7 (v1.1).
- **Suggestion :** FR-5 : rattacher un responsable du Kit au Club ; afficher la dernière position connue d'un Gilet ; contrôle « Kit complet » à la clôture de Séance (FR-7). Assurance et valise au §10.

## 4. Transparence joueur et maîtrise des données

### P2. « Le joueur voit tout ce que le staff voit sur lui »
- **Entrées :** parade validée (« droit de regard », « le joueur voit ses propres données ») et insight « la transparence joueur transforme les méfiants en ambassadeurs » ; charte de données signée.
- **PRD :** §4.9 reprend la phrase, mais FR-29 et UJ-4 limitent la vue joueur aux Métriques physiques et Actions ballon ; FR-3 réserve les Statuts au staff. Rien n'indique que le Joueur voit ses propres Statuts, Alertes de décrochage, Indice de fiabilité ou sa ligne du Rapport d'après-match. La « charte de données » n'apparaît pas (seul le Consentement).
- **Suggestion :** FR-29 : lister explicitement ce que le Joueur voit sur lui-même (Statuts et Alertes le concernant inclus) ; FR-3 : préciser « Statuts de toute l'Équipe » vs Statut propre ; FR-30 : mentionner la charte de données (usages interdits : salaire, sanction).

### P3. Historique du championnat et vidéothèque comme actif
- **Entrées :** insight validé : l'historique match après match, la vidéothèque et le contact LSFP font d'El TacTiko « l'infrastructure de données du football sénégalais » ; « chaque match enregistré devient un actif unique ».
- **PRD :** le §1 Vision n'en parle pas ; NFR-7 prévoit l'archivage des vidéos sans dire qu'elles sont conservées ; le Consentement (FR-30) ne couvre pas une réutilisation agrégée future (Ligue).
- **Suggestion :** §1 Vision (une phrase) ; NFR-7 : durée de conservation des vidéos ; FR-30 / §11 Q5 : périmètre du Consentement pour un usage agrégé futur.

## 5. Besoins d'utilisateurs sans exigence

### P2. Préparateur physique : retour de blessure
- **Entrées :** brief (« Cibles ») : le préparateur « suit la fatigue et les retours de blessure ».
- **PRD :** JTBD au §2.1, mais aucune FR ne le sert en v1 (l'indice de fatigue est en v1.1, ce qui est conforme au MoSCoW). Le suivi de reprise après blessure n'est ni en v1 ni dans §6.2.
- **Suggestion :** §6.2 : classer explicitement le suivi de retour de blessure (v1.1 avec l'indice de fatigue), ou FR-28 : permettre au préparateur de marquer une période de blessure et de comparer la reprise à la Référence individuelle.

### P3. Président : ce que voit l'acheteur
- **Entrées :** « vendre au club/président, pas au coach » ; l'outil doit survivre au changement d'entraîneur.
- **PRD :** le Rôle président existe (§3) mais FR-3 ne dit pas ce qu'il voit ; rien n'assure que les données restent au Club si le coach part (transfert des droits de gestion de l'Équipe).
- **Suggestion :** FR-3 : droits du président ; FR-1/FR-2 : la gestion de l'Équipe peut être réattribuée sans perte de données.

## 6. Contexte local et calendrier

### P3. Calendrier et hivernage
- **Entrées :** saison 2026-27 démarrée le 3 octobre 2026, pilote en club en cours de saison (brief) ; question ouverte sur la fiabilité vitesse/distance sur terrain boueux en hivernage (juillet-octobre) ; question « qui manipule les capteurs le jour du match ».
- **PRD :** §10 sans calendrier ; §11 ne reprend ni l'hivernage ni la question du manipulateur des capteurs.
- **Suggestion :** §10 : rappel du démarrage en cours de saison ; §11 : ajouter les deux questions.

### P3. Vision régionale
- **Entrées :** brief « Vision » : référence en 2-3 ans pour les 32 clubs, académies et navétanes, puis export en Afrique de l'Ouest.
- **PRD :** §1 s'arrête aux matchs officiels.
- **Suggestion :** §1, une phrase d'horizon.

## Points vérifiés sans écart

- Tous les Indispensables du MoSCoW validé sont couverts (FR-5 à FR-34), sauf la nuance « avant tout achat » (§2 ci-dessus).
- Les Importants (mi-temps, fatigue, prépayé, tablette miroir) sont bien en v1.1, et les Bonus et « Pas maintenant » en v2 ou non planifiés.
- « 1 écran, 3 couleurs, 1 alerte », lecture en 3 secondes, contraste plein soleil : repris au §4.4 et dans SM-C2.
- Après-match promis, direct en bonus ; tendances plutôt que certitudes : §5.
- 2 ou 3 clubs pilotes dont un de Ligue 2, entrée par l'entraînement : §10.
- Indice de fiabilité, calibration manuelle, correction manuelle qui entraîne la future IA : FR-13, FR-14, FR-22.
- Nom définitif El TacTiko : respecté.
