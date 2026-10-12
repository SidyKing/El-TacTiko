---
title: "El TacTiko : appareils utilisables"
created: 2026-10-12
source: recherche web du 12/10/2026
---

# El TacTiko : appareils utilisables

**À lire avant tout :**
- Les prix sont indicatifs et **non vérifiés** : ils viennent de revendeurs, d'anciens appels d'offres ou de blogs.
- Aucun distributeur au Sénégal ni en Afrique de l'Ouest n'a été trouvé. Il faut demander des **devis livrés à Dakar**.
- Les sites de la FIFA, de Polar et de Catapult n'ont pas pu être consultés directement.

## 1. Gilets et capteurs GPS (EPTS)

| Modèle | Mesures | Accès aux données | Prix indicatif | FIFA Quality | Source |
|---|---|---|---|---|---|
| STATSports Apex (Pro Series) | GPS 18 Hz (GNSS augmenté 10 Hz), accéléromètre 952 Hz, autonomie 8 h et plus | API en offre Pro ; données brutes en Team ; CSV en Coach | sur devis (22 unités pour 35 400 € dans un devis de 2019) | ✅ en direct et après la séance | [statsports](https://statsports.com/article/statsports-certified-by-fifa-for-live-and-post-session-data-accuracy) |
| STATSports Apex Athlete | mêmes métriques, usage individuel | application fermée | ≈ 235 € avec gilet | — | [11teamsports](https://www.11teamsports.com/nl-nl/p/statsports-apex-athlete-gps-tracker-gr-l-zwart) |
| STATSports Sonra Lite | plateforme pour clubs amateurs | ? | non publié | — | [statsports](https://statsports.com/article/launching-sonra-lite-a-new-performance-tracking-platform-for-grassroots-teams) |
| Catapult One | GPS 10 Hz | **export CSV brut à 10 Hz, sur demande au support** | abonnement annuel | non confirmé | [catapult](https://onesupport.catapultsports.com/hc/en-us/articles/7443854057103-How-to-Export-GPS-Raw-Data-from-Catapult-One) |
| Catapult Vector S7 | GPS et positionnement local, haut de gamme | API OpenField Cloud, CSV 10 Hz | sur devis | « Vector » listé par la FIFA ; la version S7 reste à vérifier | [catapult](https://www.catapult.com/products/vector) |
| Kinexon PERFORM GPS Pro | GPS et accéléromètre, synchronisation Wi-Fi vers le cloud | données brutes, sans API documentée | sur devis | ✅ du 28/11/2024 au 27/11/2028 | [rapport FIFA](https://kinexon-sports.com/uploads/images/Blog/Kinexon_GPS_PRO_Live_2024_Report_EPTS_FIFA-Quality_Report.pdf.pdf) |
| Polar Team Pro | GPS et fréquence cardiaque | **API REST publique** (OAuth2) | 32 capteurs, 3 ans de logiciel et 4 iPad ≈ 30,8 lakh INR (appel d'offres de 2024) | non trouvé | [polar](https://www.polar.com/teampro-api/) |
| PlayerData EDGE | GPS 10 Hz, Bluetooth et cellulaire | pas d'export documenté | ≈ 120 £ par an (Royaume-Uni) | — | [playerdata](https://playerdata.com/new-pages/product) |
| Footbar Team Pack | valise de 15, 20 ou 30 capteurs | « export » annoncé, format inconnu | à partir de 828 €, plus un abonnement | — | [footbar](https://footbar.com/en/products/malette-de-capteurs) |
| Capteurs génériques en marque blanche | annonces peu fiables | aucun SDK sérieux trouvé | lot de 12 ≈ 771 à 881 $ | ❌ | à éviter sans documentation |
| Puces u-blox NEO-M9N / ZED-F9P | modules GPS qui servent à fabriquer des capteurs | ouvert | — | — | [u-blox](https://www.u-blox.com/en/u-blox-and-Fitogether-Empowering-sports-teams-with-data) |

## 2. Foot en salle et five

- **PlayerMaker** : capteurs fixés sur la chaussure (touches, passes, distance, vitesse). Données dans le cloud, pas d'API trouvée, prix sur devis.
- **Kinexon LPS** : balises radio UWB autour du terrain, validé scientifiquement. Certification FIFA en salle non confirmée, prix sur devis.

## 3. Cardio

- **Polar H10** : Bluetooth et ANT+, électrocardiogramme 130 Hz, accéléromètre. **SDK Bluetooth gratuit** pour Android et iOS, et bibliothèque Python BleakHeart. Environ 87 à 90 €.

## 4. Caméras et mâts

- **Veo Cam 3 / 3 5G** : caméra avec suivi automatique par IA, plateforme fermée, abonnement obligatoire. Environ 1 199 à 1 599 $. Autonomie 6,5 h.
- **Pixellot Air NXT** : 4K, envoi par Wi-Fi ou 4G/5G, batterie 6 h, abonnement obligatoire. Environ 999 à 1 229 $.
- **Trace** : en location, à partir de 15 à 25 $ par mois.
- **XbotGo Chameleon / Falcon** : suivi automatique en 4K, **sans abonnement**. Falcon ≈ 600 $.
- **GoPro HERO13 Black** : 4K, fichiers MP4 ouverts, 349 à 399 $. ⚠️ Risque de surchauffe sur les longues sessions en 4K.
- **Reolink GO PT Ultra** : caméra 4K avec carte SIM 4G et panneau solaire, ≈ 273 €.
- **Mât TipTop de 8 m** en carbone : 1 329 € HT (charge 5 kg) ou 1 695 € HT (charge 7 kg).

## 5. Connexion

- **Huawei E5785** : routeur 4G de poche, environ 12 h d'autonomie, ≈ 133 €.
- **Teltonika RUT241** : routeur 4G industriel, ≈ 207 $. À protéger dans un boîtier étanche.
- **Teltonika RUTX50** : routeur 5G, ≈ 578 $, conçu pour l'intérieur.
- **RAK7289CV2** : passerelle radio longue portée (LoRaWAN) pour l'extérieur, étanche (IP67), 4G en option, ≈ 375 €.
- **Nordic nRF9151 DK** : kit d'essai pour l'option « puce 4G par gilet » (LTE-M / NB-IoT et GPS), 85 à 100 €.
- **Au Sénégal :** Orange couvre en 4G. **Aucune offre LTE-M ou NB-IoT n'est confirmée** chez Orange, Free ou Expresso, donc l'option « puce 4G par gilet » n'est pas réaliste pour l'instant. À vérifier auprès de l'ARTP.

## 6. Tablette du banc

| Modèle | Écran | Résistance | Prix |
|---|---|---|---|
| Samsung Galaxy Tab Active5 Pro | 10,1", ≈ 456 nits (682 en luminosité renforcée) | IP68, norme militaire MIL-STD-810H | ≈ 799 € |
| Samsung Galaxy Tab Active5 | 8", 540 nits | renforcée | 479 € (579 € en 5G) |
| Samsung Galaxy Tab S10 FE | 10,9", 800 nits en luminosité maximale | IP68 | à partir de 849 AUD |
| iPad A16 / iPad Air M3 | 500 nits | pas d'indice d'étanchéité | 349 / 599 $ |

Sur iPad, la PWA ne peut pas faire vibrer l'appareil, et les notifications ne fonctionnent que si l'appli est installée sur l'écran d'accueil (iOS 16.4 et suivants). **Une tablette Android renforcée est recommandée.**

## 7. Alimentation

- **Anker Prime 20 000 mAh** (200 W) : ≈ 100 à 122 €.
- **EcoFlow River 3** : ≈ 159 $, avec un panneau solaire flexible de 100 W à ≈ 129 €.
- **Anker SOLIX C1000X** avec panneau solaire PS100X : ≈ 799 €.
- **Stations de charge :** les gilets STATSports se rechargent sur des stations de 16 places ; Catapult One est livré avec sa station (2 h de charge).

## Recommandation par palier

1. **Palier 1, five en extérieur :**
   - pour les données physiques : **Catapult One**, grâce à son export CSV à 10 Hz documenté, ou **Footbar** si son format d'export est confirmé ;
   - en complément : la ceinture cardio Polar H10 (SDK gratuit), une caméra sans abonnement (XbotGo ou GoPro) sur un mât TipTop, un routeur Huawei E5785 et une batterie Anker.
2. **Palier 2, pilote en club à l'entraînement :**
   - **Polar Team Pro**, la seule API REST publique trouvée, ou **STATSports Apex en offre Pro**, la seule qui donne accès à l'API ;
   - au banc : une Galaxy Tab Active5 Pro, et un Teltonika RUT241 dans un boîtier étanche.
3. **Palier 3, matchs officiels :** uniquement des systèmes **certifiés FIFA Quality** : Kinexon GPS Pro (valable jusqu'en 2028) ou STATSports Apex. Pour Catapult Vector, la version certifiée reste à vérifier.
4. **À clarifier :** l'absence de LTE-M au Sénégal, qui écarte pour l'instant la puce 4G dans chaque gilet. Il faut aussi obtenir des devis livrés à Dakar.
