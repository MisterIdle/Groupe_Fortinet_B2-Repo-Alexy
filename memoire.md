# Mémoire Technique - Proposition pour l'Installation du Réseau et des Systèmes de Sécurité

## Introduction

Dans le cadre du développement du réseau d'entreprise, nous avons fait la mémoire technique de la proposition détaillée pour le déploiement du réseau informatique et des systèmes de sécurité dans le cadre du projet en cours. Il inclut les choix des équipements, les calculs des quantitatifs IP nécessaires, la vérification des besoins en PoE (Power over Ethernet), ainsi que des informations concernant la bande passante. De plus, les datasheets des équipements sélectionnés sont fournies pour chaque catégorie..

### Objectifs du Projet

- Installation d'un réseau performant et sécurisé
- Intégration des systèmes de sécurité (caméras, détecteurs de fumée, bornes Wi-Fi, etc.)
- Garantie d'une couverture optimale en termes de bande passante et de PoE pour l'ensemble des équipements
- Choix d'équipements réseau et sécurité adaptés

---
## Calculs de Quantitatifs IP

Pour chaque catégorie d’équipement, une adresse IP doit être attribuée. Chaque équipement doit être configuré pour s’assurer qu'il peut communiquer efficacement sur le réseau tout en garantissant la sécurité. En fonction du nombre d’équipements installés, il est prévu d’utiliser un sous-réseau approprié.

### Répartition des VLANs
Afin d'assurer une gestion fluide et segmentée du trafic réseau, plusieurs VLANs ont été
définis selon les départements et les types de services requis. Chaque VLAN est
dimensionné pour accueillir les utilisateurs et équipements prévus, avec une marge de
sécurité de 30% pour tenir compte de l’évolution du réseau.

# Répartition des VLANs

1. **VLAN 10 (RH)**  
   - **Adresse réseau** : 10.0.10.0/24  
   - **Plage d'adresses** : 10.0.10.1 - 10.0.10.254  

2. **VLAN 20 (IT)**  
   - **Adresse réseau** : 10.0.20.0/24  
   - **Plage d'adresses** : 10.0.20.1 - 10.0.20.254  

3. **VLAN 30 (Finance)**  
   - **Adresse réseau** : 10.0.30.0/24  
   - **Plage d'adresses** : 10.0.30.1 - 10.0.30.254  

4. **VLAN 40 (Logistique)**  
   - **Adresse réseau** : 10.0.40.0/24  
   - **Plage d'adresses** : 10.0.40.1 - 10.0.40.254  

5. **VLAN 50 (Production)**  
   - **Adresse réseau** : 10.0.50.0/24  
   - **Plage d'adresses** : 10.0.50.1 - 10.0.50.254  

6. **VLAN 60 (Sécurité)**  
   - **Adresse réseau** : 10.0.60.0/24  
   - **Plage d'adresses** : 10.0.60.1 - 10.0.60.254  

7. **VLAN 70 (Direction)**  
   - **Adresse réseau** : 10.0.70.0/24  
   - **Plage d'adresses** : 10.0.70.1 - 10.0.70.254  

8. **VLAN 80 (Invités)**  
   - **Adresse réseau** : 10.0.80.0/24  
   - **Plage d'adresses** : 10.0.80.1 - 10.0.80.254  

9. **VLAN 90**  
   - **Adresse réseau** : 10.0.90.0/24  
   - **Plage d'adresses** : 10.0.90.1 - 10.0.90.254  

10. **VLAN 100**  
    - **Adresse réseau** : 10.0.100.0/24  
    - **Plage d'adresses** : 10.0.100.1 - 10.0.100.254  

11. **VLAN 110**  
    - **Adresse réseau** : 10.0.110.0/24  
    - **Plage d'adresses** : 10.0.110.1 - 10.0.110.254    

12. **VLAN 120**  
    - **Adresse réseau** : 10.0.120.0/24  
    - **Plage d'adresses** : 10.0.120.1 - 10.0.120.254   

13. **VLAN 130**  
    - **Adresse réseau** : 10.0.130.0/24  
    - **Plage d'adresses** : 10.0.130.1 - 10.0.130.254  

14. **VLAN 140**  
    - **Adresse réseau** : 10.0.140.0/24  
    - **Plage d'adresses** : 10.0.140.1 - 10.0.140.254  

15. **VLAN 150**  
    - **Adresse réseau** : 10.0.150.0/24  
    - **Plage d'adresses** : 10.0.150.1 - 10.0.150.254  

16. **VLAN 160**  
    - **Adresse réseau** : 10.0.160.0/24  
    - **Plage d'adresses** : 10.0.160.1 - 10.0.160.254   

---

## 2. Comptage des Équipements

Le comptage des équipements a été réalisé selon les besoins du projet. Voici un récapitulatif de la répartition des équipements par étage :

| **Équipement**            | **Calcul**                          | **Quantité** |
|---------------------------|--------------------------------------|--------------|
| **Switchs de distribution** | ⌈640 / 48⌉                          | 14           |
| **Bornes Wi-Fi (bureaux)**  | 12 par étage × 6 étages             | 72           |
| **Bornes Wi-Fi (RDC et SS)**| 6 (RDC) + 8 (SS)                    | 14           |
| **Total Bornes Wi-Fi**      | 72 + 14                             | 86           |
| **Routeurs**                | Minimum recommandé : 1 + 1 pour redondance | 2     |
| **Cœurs de réseau**         | Prévision pour évolutivité : 4       | 4            |


---

## 3. Choix des Équipements

### 3.1. Équipements Fortinet Choisis

Pour assurer une infrastructure réseau sécurisée et fiable, les équipements Fortinet suivants ont été sélectionnés :

- **Switch** : FortiSwitch 148F-FPOE
  - **Role** : Switch PoE pour alimenter les équipements réseau comme les caméras et bornes Wi-Fi.
  - **Type** : Switch PoE (Power over Ethernet)
  - **Caractéristiques** :
  - Ports : 48 ports Gigabit Ethernet PoE+
  - Poids : 7 kg
  - Vitesse : 10/100/1000 Mbps
  - Protocoles : LACP, VLAN, QoS, Spanning Tree Protocol
  - Documentation : [FortiSwitch Secure AccessSeries](https://www.fortinet.com/products/switches)
- **Prix Unitaire** : 2 245,00 €
- **Prix Total (avec 30% de marge)** : 22 001,00 €

- **Switch Core** : FortiSwitch 448D
  - **Role** : Switch central pour la gestion du trafic réseau.
  - **Type** : Switch de cœur de réseau
  - **Caractéristiques** :
  - 48 ports Gigabit Ethernet
  - Supporte les VLANs et les protocoles de gestion réseau avancée
  - Documentation : [FortiSwitch Secure AccessSeries](https://www.fortinet.com/products/switches)
 - **Prix Unitaire** : 4 860,00 €
- **Prix Total (avec 30% de marge)** : 13 608,00 €

- **Routeur** : FortiGate 200F
  - **Role** : Pare-feu haute performance pour protéger le réseau.
  - **Documentation** : [FortiGate 200F](https://www.fortinet.com/content/dam/fortinet/assets/data-sheets/pdf/fortigate-200f-series.pdf)

- **Point d'Accès Wi-Fi** : FortiAP 231G
  - **Caractéristiques** : Bornes Wi-Fi pour une couverture optimale du réseau sans fil.
  - **Type** : Point d'accès Wi-Fi
  - **Caractéristiques** :
  - 2.4GHz & 5GHz avec technologie MU-MIMO
  - Prise en charge de l'authentification 802.1X
  - Documentation : [FortiAP Series](https://www.fortinet.com/products/wireless)
  - **Prix Unitaire** : 713,00 €
  - **Prix Total (avec 30% de marge)** : 42 922,60 €

### 3.2 Licences et Coûts Associés
- **Licence FortiGate 200F (5 ans)** : 13 471,92 € (après marge de 30% : 9 430,34 €)
- **Licence FortiSwitch 448D (5 ans)** : 2 430,00 € (après marge de 30% : 1 701,00 €)
- **Coût de configuration du réseau** : 1 000,00 € (après marge de 30% : 700,00 €)

### 3.3 Estimation des Coûts Totaux
- **Prix total de l'intervention** : 132 600€

---

##  4. Power over Ethernet (PoE)

### 4.1 Vérification du PoE (Power over Ethernet)

Les équipements PoE doivent être capables de fournir l'alimentation nécessaire aux dispositifs réseau, tels que les caméras et les bornes Wi-Fi, sans avoir besoin de câblage supplémentaire.

- **Switch FortiSwitch 148F-FPOE** : Ce switch prend en charge le PoE pour alimenter jusqu'à 30W par port. Cela est suffisant pour les équipements tels que les caméras IP et les points d'accès Wi-Fi.
  
- **Borne Wi-Fi FortiAP 231G** : Chaque point d'accès Wi-Fi nécessite un maximum de 15W, et peut être alimenté par PoE via le switch.

La capacité PoE du **FortiSwitch 148F-FPOE** garantit que tous les dispositifs peuvent être alimentés directement par les câbles réseau, simplifiant ainsi l'installation.


### 4.2 Estimation des Besoins PoE
Le PoE permet d'alimenter des équipements réseau (comme des bornes Wi-Fi et des
switches) directement via les câbles Ethernet, simplifiant l'architecture physique du réseau.
Une attention particulière a été portée sur les besoins en PoE pour chaque équipement.

#### Switchs de Distribution
- **Quantité** : 14 Switchs FortiSwitch 148F-POE
- **Puissance totale nécessaire par switch** : 370 W (par switch avec PoE actif)
- **Total de puissance nécessaire** : 370 W x 14 = **5 180 W**
- **Marge de sécurité (30%)** : 5 180 W x 1.30 = **6 744 W**
- **Capacité PoE disponible par switch** : 370 W par switch
- **Capacité totale PoE disponible** : **5 180 W**

#### Bornes Wi-Fi
- **Quantité** : 86 Bornes FortiAP 231G
- **Puissance totale nécessaire par borne** : 30 W
- **Total de puissance nécessaire pour toutes les bornes** : 30 W x 86 = **2 580 W**
- **Marge de sécurité (30%)** : 2 580 W x 1.30 = **3 354 W**
- **Capacité PoE disponible** : 5 180 W

#### Total PoE
- **Puissance totale requise pour les équipements PoE** : 5 180 W (Switchs) + 3 354 W
(Bornes Wi-Fi) = **8 534 W**
- **Marge totale avec PoE** : 8 534 W x 1.30 = **11 095 W**
- **Capacité PoE disponible** : 5 180 W

**Conclusion sur le PoE** : La capacité PoE actuelle est insuffisante pour couvrir la
demande totale (en particulier pour les bornes Wi-Fi). Il sera nécessaire de prévoir une
alimentation supplémentaire pour répondre aux besoins du réseau.

---


##  5. Bande Passante et Dimensionnement du Réseau
### 5.1 Vérification de la Bande Passante

Les équipements réseau doivent être dimensionnés pour supporter le trafic généré par les équipements de sécurité et les utilisateurs.

- **FortiSwitch 148F-FPOE** : Ce switch offre des ports 1G pour les connexions de périphériques, et des ports 10G pour le backbone du réseau.
- **FortiGate 200F** : Le pare-feu FortiGate 200F peut gérer jusqu'à 6 Gbps de débit en inspection complète de paquets, ce qui est suffisant pour sécuriser les flux de données du réseau.
- **FortiAP 231G** : Ces bornes Wi-Fi offrent des vitesses jusqu'à 1,75 Gbps (802.11ac Wave 2), ce qui permet de gérer un grand nombre de connexions simultanées tout en assurant des performances élevées.

La bande passante totale du réseau est largement suffisante pour supporter les applications de sécurité et de communication sans compromettre les performances.

### 5.2 Estimation des Besoins en Bande Passante
Les équipements du réseau doivent être capables de supporter un volume élevé de
données. Il est crucial de dimensionner correctement la bande passante afin d'éviter les
goulets d'étranglement et d’assurer une performance optimale.

#### Routeurs FortiGate 200F
- **Quantité** : 2
- **Bande passante totale nécessaire** : 2 Gbps (capacité maximale du modèle)
- **Bande passante totale après marge (30%)** : 2 Gbps x 1.30 = **2,6 Gbps**µ

#### Cœurs de Réseau (Switch FortiSwitch 448D)
- **Quantité** : 4
- **Bande passante totale nécessaire** : 160 Gbps (capacité combinée des 4 switches)
- **Marge de sécurité (30%)** : 160 Gbps x 1.30 = **208 Gbps**
- **Bande passante totale disponible** : 160 Gbps

#### Total Bande Passante
- **Bande passante totale nécessaire (routeurs + switches)** : 2,6 Gbps (Routeurs) + 208
Gbps (Switches) = **210,6 Gbps**
- **Bande passante totale disponible** : 160 Gbps (Switches)

**Conclusion sur la Bande Passante** : Le dimensionnement actuel du cœur de réseau
(Switches) est insuffisant par rapport aux besoins totaux estimés. Une mise à jour des
switches ou l’ajout de switches supplémentaires pourrait être nécessaire pour garantir un
réseau fluide.


---

## 6. Datasheets des Équipements Choisis

1. **FortiSwitch 148F-FPOE** : [Télécharger la datasheet](https://www.fortinet.com/content/dam/fortinet/assets/data-sheets/pdf/fortiswitch-secure-access-series.pdf)
2. **FortiSwitch 448D** : [Télécharger la datasheet](https://www.avfirewalls.com/datasheets/FortiSwitch/FortiSwitch_Secure_Access_Series.pdf)
3. **FortiGate 200F** : [Télécharger la datasheet](https://www.fortinet.com/content/dam/fortinet/assets/data-sheets/pdf/fortigate-200f-series.pdf)
4. **FortiAP 231G** : [Télécharger la datasheet](https://www.fortinet.com/content/dam/fortinet/assets/data-sheets/pdf/fortiap-series.pdf)
