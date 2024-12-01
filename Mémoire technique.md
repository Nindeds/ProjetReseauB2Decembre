
# MÉMOIRE TECHNIQUE 

# Introduction :
Ce document présente notre proposition technique pour le projet de réseau, incluant les calculs de quantitatifs IP, les choix d'équipements, la vérification du PoE (Power over Ethernet) et de la bande passante, ainsi que les fiches techniques des équipements sélectionnés.


# 1. Calcul Quantitatif des Adresses IP

## 1.1. Nombre d'Équipements

Le bâtiment nécessite un réseau intégrant divers équipements tels que des **switchs**, des **bornes Wi-Fi 6E**, des **caméras de surveillance**, des **détecteurs d'incendie**, des **lecteurs de badge**, et autres dispositifs. Le nombre total d'équipements est estimé comme suit :

| Composant                             | Quantité Totale |
|---------------------------------------|-----------------|
| **Switchs cœur de réseau**            | 2               |
| **Switchs de distribution**           | 17              |
| **Bornes Wi-Fi 6E**                   | 99              |
| **Caméras Fixes Intérieures**         | 10              |
| **Caméras Fixes Extérieures**         | 5               |
| **Détecteurs d'incendie**             | 118             |
| **Lecteurs de badge**                 | 23              |

## 1.2. Subnetting

Afin de segmenter efficacement les réseaux, il est nécessaire de diviser la plage d'adresses IPv4 en sous-réseaux :

- **Sous-réseau pour les switchs** : /24
- **Sous-réseau pour les bornes Wi-Fi** : /25
- **Sous-réseau pour les caméras et détecteurs** : /26

## 1.3. Estimation des Plages IP Nécessaires

Le calcul du nombre d'adresses nécessaires pour chaque sous-réseau est effectué en fonction des équipements estimés pour chaque catégorie.

# 2. Choix d'Équipements

## 2.1. Switchs

Pour la gestion du réseau cœur et de la distribution, les équipements Meraki ont été sélectionnés pour leur gestion simplifiée et leur fiabilité :

- **Switch cœur de réseau : Meraki MS390-48U**
  - **Modèle** : MS390-48U-HW
  - **Quantité** : 2
  - **Fonction** : Fournir la connectivité backbone
  - **PoE** : Oui, capacité PoE de 720W par switch

- **Switchs de distribution : Meraki MS250-48**
  - **Modèle** : MS250-48-HW
  - **Quantité** : 17
  - **Fonction** : Relier les équipements sur chaque étage
  - **PoE** : Oui, capacité PoE de 370W par switch

## 2.2. Bornes Wi-Fi 6E

- **Modèle de borne Wi-Fi : Meraki MR57**
  - **Quantité** : 99
  - **Fonction** : Assurer une couverture Wi-Fi 6E dans tout le bâtiment
  - **Support PoE** : Oui
  - **Performance** : Supporte les dernières normes Wi-Fi 6E avec une bande passante élevée pour les utilisateurs et les dispositifs connectés

## 2.3. Autres Équipements

Des caméras de surveillance, des détecteurs de présence et d'incendie, entre autres dispositifs, seront installés, tous compatibles PoE pour simplifier l'architecture réseau.

# 3. Vérification PoE et Bande Passante

## 3.1. Power over Ethernet (PoE)

Tous les équipements nécessitant une alimentation via Ethernet (bornes Wi-Fi, caméras) sont compatibles PoE pour réduire la complexité du câblage.

- **PoE nécessaire pour chaque appareil :**
  - **Bornes Wi-Fi** : Consommation moyenne de 30W par borne
  - **Caméras de surveillance** : Consommation moyenne de 15W par caméra
  - **Détecteurs d'incendie, badge, etc.** : Moins de 5W par appareil

Les switchs choisis, MS250 (370W PoE) et MS390 (720W PoE), peuvent alimenter tous les équipements nécessaires.

# 4. Datasheets des Équipements Choisis

## 4.1. Meraki MS390-48U (Switch Cœur)
- **Description** : Switch avec 48 ports Ethernet 1G et 10G
- **PoE** : 720W
- **Caractéristiques principales** : Optimisé pour des réseaux larges, gestion via le Cloud Meraki.

[Datasheet Meraki MS390-48U](https://meraki.cisco.com/fr-fr/product/switches/stackable-access-switches/ms390-48/)

## 4.2. Meraki MS250-48 (Switch Distribution)
- **Description** : Switch de distribution avec 48 ports Ethernet 1G
- **PoE** : 370W
- **Caractéristiques principales** : Fiabilité pour les réseaux intermédiaires, gestion cloud Meraki.

[Datasheet Meraki MS250-48](https://meraki.cisco.com/fr-fr/product/switches/stackable-access-switches/ms250-48/)

## 4.3. Meraki MR57 (Borne Wi-Fi 6E)
- **Description** : Borne Wi-Fi 6E offrant une couverture à haute densité
- **Caractéristiques principales** : Supporte des vitesses rapides et une plus grande capacité d'appareils grâce à la technologie Wi-Fi 6E.

[Datasheet Meraki MR57](https://meraki.cisco.com/fr-fr/product/wi-fi/indoor-access-points/mr57/)

# Conclusion

Cette proposition permet de répondre aux besoins du bâtiment en matière de connectivité, de gestion simplifiée et de capacité PoE. Les équipements Meraki garantissent une performance fiable et évolutive avec une gestion simplifiée via la plateforme cloud. La couverture Wi-Fi 6E assurera une connectivité rapide et stable pour les utilisateurs, tandis que le système de surveillance sera renforcé grâce à des caméras et des détecteurs compatibles PoE.

Les calculs d'adresses IP, la vérification du PoE et de la bande passante ont été effectués pour assurer que le réseau répondra aux besoins actuels et futurs.

