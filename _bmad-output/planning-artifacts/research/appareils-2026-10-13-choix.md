---
title: "El TacTiko : choix du capteur"
created: 2026-10-13
---

# Choix du capteur : STATSports Apex, offre Pro Series

## Pourquoi celui-là, et un seul
- **Couvre tous les usages** (five, entraînement, matchs officiels) : certifié **FIFA Quality en direct et après la séance**. On n'aura pas à racheter de matériel pour les matchs.
- **Données ouvertes** : l'offre Pro donne l'**API**, l'export ADI et les **données brutes**. Les offres Team et Coach n'ont pas d'API : à éviter.
- **Pas de perte de données** : chaque pod enregistre en interne pendant plus de 8 h.

Écartés :
- Kinexon : certifié, mais aucune API documentée.
- Polar Team Pro : API publique, mais certification FIFA introuvable et application en direct liée à l'iPad.
- Catapult One : export CSV manuel, certification non confirmée.

## Prix (à confirmer par devis)
- Seul repère public : un devis de 2019, **35 400 € pour 22 unités**, soit environ 1 600 € par joueur, logiciel et accessoires compris.
- Pour un kit de 25 pods, prévoir **environ 40 000 €** (estimation non vérifiée).
- Le devis doit être **livré à Dakar** et préciser :
  - l'accès à l'API Pro ;
  - l'**accès au flux en direct** pour un logiciel tiers ;
  - la propriété des données ;
  - les stations de charge.

## Flux de données jusqu'à notre base
1. **Pendant la séance** : chaque pod enregistre tout en interne (mode tampon).
2. **En direct** : les pods envoient par radio au récepteur STATSports, au bord du terrain, relié à un ordinateur et au routeur 4G (Huawei E5785). Si STATSports ouvre le flux en direct, un petit service le transmet à notre VPS, puis à la Tablette banc. **Point à exiger dans le devis.**
3. **Après la séance** : les pods vont sur la station d'accueil, qui synchronise vers le cloud STATSports.
4. **Récupération** : notre VPS interroge l'API STATSports à la fin de chaque séance et toutes les 5 minutes tant que la synchronisation n'est pas complète. Il récupère les données brutes à 10 Hz et les écrit dans PostgreSQL. Le rattachement à la Séance et au Joueur se fait par l'ID du pod (association Gilet–Joueur, FR-6).
5. **Calcul** : nos métriques (Intensité, Statut, sprints) sont calculées à partir des **données brutes**, et non des métriques du fournisseur. On reste indépendant du fournisseur et on garde le contrôle des seuils.
