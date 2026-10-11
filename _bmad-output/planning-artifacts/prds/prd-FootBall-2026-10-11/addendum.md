---
title: "Addendum PRD : El TacTiko"
created: 2026-10-11
updated: 2026-10-11
---

# Addendum PRD : El TacTiko

Ce document regroupe les choix techniques et les options étudiées. Ils servent à l'architecture et ne figurent pas dans le PRD lui-même.

## Architecture retenue lors du brainstorming

- **Rôles des capteurs :**
  - les Gilets GPS mesurent la partie physique : distance, vitesse, sprints, accélérations, et rythme cardiaque à terme ;
  - la Caméra mesure la partie ballon : passes, tirs, pertes de balle, positions.
- **Analyse :** entièrement sur un VPS dans le cloud. La Tablette banc se contente d'afficher.
- **Vidéo :** enregistrée en HD sur place. Un flux basse résolution peut partir en direct ; la HD est envoyée à la mi-temps ou après la Séance.
- **Caméra :** montée sur un mât télescopique de 6 à 8 m, pour les stades sans tribune haute.
- **Mode dégradé :**
  - si la Caméra tombe en panne, on garde les Métriques physiques ;
  - si un Gilet tombe en panne, la vidéo garde la position du Joueur.
- **Identification :** un grand numéro ou une couleur sur le Gilet aide l'identification vidéo, en vue de l'IA.

## Transmission : options étudiées (à trancher, voir PRD §11, question 2)

| Option | Principe | Avantages | Risques |
|---|---|---|---|
| 1. Puce 4G / IoT par Gilet | LTE-M ou NB-IoT, envoi direct au VPS | Aucun boîtier à installer | 25 abonnements SIM, batterie plus grosse, dépendance à la couverture du stade |
| 2. Tablette comme relais Bluetooth | Gilets → tablette → 4G | Pas de matériel en plus | Portée Bluetooth trop faible sur 105 m. Web Bluetooth est indisponible sur iOS et limité dans une PWA |
| 3. Mini-Passerelle LoRa → 4G | Relais simple avec stockage tampon, sans calcul | Une seule SIM, bonne portée | Un équipement de plus à installer |

Le Mode tampon sur chaque Gilet est obligatoire dans tous les cas. On peut aussi demander à un opérateur un APN dédié ou une priorité de débit les jours de match.

## Captation en salle et en five

- Le GPS ne capte pas en intérieur. Sur un terrain d'environ 40 × 20 m, son erreur de 1 à 2 m fausse fortement les distances et les sprints.
- **Pistes possibles :**
  - capteurs de mouvement portés (accéléromètre et gyroscope) : distance estimée, accélérations ;
  - balises radio UWB autour du terrain : précision de l'ordre de 10 cm, mais plus chères et plus longues à installer ;
  - vidéo seule avec suivi des Joueurs.
- D'où l'exigence FR-9 : une Plateforme qui accepte plusieurs sources de captation.

## Contraintes propres à une PWA

- **Mode hors ligne :** un service worker met l'application en cache, et les données sont stockées localement dans le navigateur (IndexedDB).
- **Vibration et notifications :** l'API Vibration n'existe pas sur iOS Safari. Les notifications push sur iOS demandent que la PWA soit installée sur l'écran d'accueil (iOS 16.4 et suivants).
- **Pas de lien direct avec les capteurs :** la PWA ne parle pas aux Gilets. Tout passe par la Plateforme, ce qui confirme que la Tablette banc ne fait qu'afficher.

## Matériel et coûts (veille du brief, à revérifier)

- **Capteurs en marque blanche (OEM, Alibaba) :** de 42 à 127 $ l'unité. Fréquence d'échantillonnage, IMU et certifications CE/FCC à vérifier.
- **Repère concurrent :** Catapult One coûte environ 180 $ par joueur et par an.
- **Matchs officiels :** il faut un appareil marqué FIFA Quality (EPTS). Les capteurs certifiés de STATSports, Catapult ou PlayerMaker sont plus chers ; leur prix pour un club se fait sur devis.

## Hébergement

- Un VPS chez un hébergeur local ou africain, conforme aux exigences de la CDP, permet de limiter les coûts en devises.
- **Vidéo :** compression, puis archivage des anciennes vidéos sur un stockage moins cher (stockage froid).
