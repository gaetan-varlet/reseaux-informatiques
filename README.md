# Les réseaux informatiques

## Introduction aux réseaux informatiques

### Les différents composants d'un réseau

Une **topologie** est une représentation de l'ensemble des connexions qu'il existe entre les différents composants du réseau informatique.

- les **endpoits** ( ou **périphériques terminaux**) : ordinateurs, smartphones, imprimantes...
- les **périphériques intermédiaires**, qui permettent de connecter les périphériques intermédiaires.  Il existe 2 principaux types de périphériques intermédiaires :
    - les **switchs** (commutateur en français)
    - les **routeurs**
- le **support** permet de relier les périphériques terminaux et les périphériques intermédiaires. Ils sont de 2 types :
    - avec fil : cuivre, fibre optique, coaxial...
    - sans fil : wifi, bluetooth, infrarouge, lifi...

### Le LAN et le WAN

- **LAN**
    - Local Area Network
    - réseau de taille réduite, par exemple le réseau de la maison
- **WAN**
    - Wired Area Network
    - réseau étendu, relie plusieurs LAN entre eux


### La fiabilité des réseaux

un réseau fiable est :
- **tolérant aux pannes** : si un équipement tombe en panne, le système doit continuer à fonctionner. Une solution est d'utiliser de la **redondance** en doublant les équipements critiques.
- **évolutif** : augmenter la taille du réseau existant sans dégrader l'expérience des utilisateurs actuels
- fournit une bonne **qualité de service** : priorisation de certains types de trafic par rapport à d'autres, en réservant un certain nombre de ressources disponibles pour un type de trafic
- **sécurisé** : les données doivent être protégées des manipulations malencontreuses des utilisateurs ou à des attaquants potentiels (pare-feu, mot de passe, filtrage d'adresses IP...)


## La couche physique du modèle OSI

![Les modèles OSI et TCP/IP](img/modeles_OSI_TCP_IP.png "Les modèles OSI et TCP/IP")

### A quoi correspond la couche physique du modèle OSI ?

La couche physique du modèle OSI fait référence à tout ce qui est support de connexion (câbles, Wifi...)

La carte réseau, via le port Ethernet (RJ45) que les données vont être transmises sur le réseau.
Le CPL est une autre manière de connecter les terminaux via le réseau électrique.

Traduction du signal électrique en signal numérique (des bits)

### Couche physique : bande passante et débit

La **bande passante** est la capacité qu'à la support à transmettre l'information, par exemple un port Ethernet 10 Mbits/s.

Le **débit** est la quantité de données qui est envoyé par seconde à un instant T. Il ne pourra pas dépasser la bande passante qui est la capacité du support.

### Couche physique : Les différents types de supports existants

Le câblage cuivre transmet un signal électrique. Il en existe différents types :
- câble à paires torsadées non blindées (UTP)
- câble à paires torsadées blindées (STP)
- câble coaxial

### Couche physique : Les catégories de câble UTP

- câble de catégorie 3 : pour les lignes téléphoniques

pour transmettre des données :
- câble de catégorie 5 : 100 Mbits/s
- câble de catégorie 5e : 1 Gbits/s
- câble de catégorie 6 : 10 Gbits/s

les câbles utilisent la norme RJ45

Il existe des câbles **droit** (pour les équipements différents, par exemple un ordinateur et un routeur) et des câbles **croisé** (pour les équipements identiques). Les machines savent maintenant gérer lorsqu'on se trompe entre les 2 types de câble.

### Couche physique : La fibre optique

La fibre optique transmet de la lumière au sein du coeur qui est en verre.
Elle peut transmettre un signal sur une plus longue distance qu'un câble en cuivre.

Il existe de la fibre monomode et multimode (plusieurs chemins possible pour la lumière).

### Couche physique : Le langage binaire

En binaire, il y a deux chiffres : 0 et 1.
En déciaml, il y a 10 chiffres : 0, 1... à 9

décimal | binaire
:---:   | :---: 
0       | 1
1       | 1
2       | 10
3       | 11
4       | 100
5       | 101
6       | 110
7       | 111
8       | 1000
9       | 1001
10      | 1010
11      | 1011
12      | 1100
...     | ...
16      | 10000
32      | 100000


## Couche 2 du modèle OSI - Liaison de données

### L'hexadecimal

En hexidécimal, il y a 16 chiffres : 0, 1, ..., 9, A, B, C, D, E et F

décimal | binaire | hexadécimal
:---:   | :---: | :---: 
0       | 1     | 0
1       | 1     | 1
2       | 10    | 2
3       | 11    | 3
4       | 100   | 4
5       | 101   | 5
6       | 110   | 6
7       | 111   | 7
8       | 1000  | 8
9       | 1001  | 9
10      | 1010  | A
11      | 1011  | B
12      | 1100  | C
13      | 1101  | D
14      | 1110  | E
15      | 1111  | F
16      | 10000 | 10

en hexadecimal, un caractère est codé sur 4 bits :
- 0 en héxa => 0001 en binaire
- 8 en héxa => 1000 en binaire
- F en héxa => 1111 en binaire

le code `01BE` en héxadécimal s'écrit en binaire `0000 0001 1011 1110` ou en décimal `0 1 11 14`

### Les adresses MACs

Les adresses MAC pour **Media Access Control** sont
- des adresses physiques
- identifiant unique du composant
- lié au matériel ce qui signifie que si on change la carte réseau de PC pour la brancher sur un autre PC, la carte réseau gardera son adresse MAC

Les adresses MAC sont codés en héxadécimal sur 48 bits (12 caractères héxadécimals). Exemple :
- `40-A3-CC-6D-43-91`
- `40:A3:CC:6D:43:91`
- `40A3.CC6D.4391`

L'adresse MAC est accessible :
- sur Linux avec la commande `ifconfig`
- sur Windows avec la commande `ipconfig /all`

L'adresse MAC est composé de 2 parties :
- l'identifiant du constructeur sur les 24 premiers bits (les constructeurs peuvent avoir plusieurs plages d'identifiants)
- l'identifiant unique du matériel sur les 24 derniers bits

Si on trouve 2 matériel qui ont la même adresse MAC, on parle de **collision**.

Au moment du démarrage du PC, l'adresse MAC est stockée dans la mémoire vive. Des logiciels peuvent modifier l'adresse MAC dans la mémoire vive. Au redémarrage du PC, l'adresse MAC du matériel est de nouveau stockée dans la mémoire vive à la place de celle modifié par un évenuel logiciel.

### Communication entre deux machines grâce à la notion de trame

Un premier PC A a une adresse MAC AAAA.AAAA.AAAA.AAAA
Un second PC B a une adresse MAC BBBB.BBBB.BBBB.BBBB

Si le PC A veut envoyer un message au PC B, il va écrire une **trame** sous la forme `adresseMacDestinaire adresseMacExpéditeur données`.  
Exemple : `BBBB.BBBB.BBBB.BBBB AAAA.AAAA.AAAA.AAAA données`

Quand le PC B reçoit la trame, il regarde s'il est le bon destinataire en regardant l'adresse MAC destinataire. S'il n'est pas destinataire, il jette la trame


La forme complète d'une trame contient quelques éléments supplémentaires :
- **Préambule** : bits de synchronisation de l'horloge, pour prévenir qu'une trame Ethernet arrive juste après et qu'elle va devoir être analysée comme telle
- **Type de protocole** : protocole de niveau qui va être utilisé, IPv4 (0x0800), IPv6 (0x86DD), ARP (0x0806)
- **Frame Check Sequence** (FCS) est un code de détection d'erreur pour savoir si les données transmises ont été altérés. L'émetteur passe tous les bits de la trame dans un algorithme (CRC) pour obtneir une signature unique qu'il inscrit dans le champs FCS. Le destinataire effectue la même opération et compare le code qu'il a obtenu avec celui du champ FCS. Si les codes sont identiques, c'est bon, sinon les données ont probablement été altérés.

Une trame complète a donc :
- un préambule
- une adresse MAC de destination
- une adresse MAC source
- un type de protocole
- les données
- une séquence de contrôle

### Le fonctionnement d'un switch

Le switch, ou commutateur en français, permet de relier plusieurs ordinateurs pour qu'ils puissent communiquer entre-eux.

Plusieurs PC vont être relié à un switch :
- un PC A (adresse A.A.A) est relié au switch via l'interface Ethernet 0/1
- un PC B (adresse B.B.B) est relié au switch via l'interface Ethernet 0/2
- un PC C (adresse C.C.C) est relié au switch via l'interface Ethernet 0/3

Le switch possède une **table CAM**, aussi appelé table des adresses MAC. On y trouve les correspondances entre les interfaces et les adresses MACs connectés à ces interfaces. Elle se remplit grâce aux trames émis par les PC.

Exemple :
- le PC A émet une trame avec comme destinataire B
- le switch reçoit la trame et inscrit dans sa table CAM que l'adresse MAC A.A.A est connectée à son interface Ethernet 0/1
- le switch examine la MAC destination, et ne la trouve pas dans sa table CAM. Il va donc transmettre la trame par tous ses ports sauf le port excepté le port source
- le PC C va rejeter la trame
- le PC B va accepter la trame. Le PC B va répondre en construisant une trame qu'il envoie au switch
- le switch reçoit la trame, et inscrit dans sa table CAM que l'adresse MAC B.B.B  est connectée à son interface Ethernet 0/2
- il regarde le destinataire de la trame (A.A.A) et il le connait déjà. Le switch va donc uniquement diffuser uniquement la trame via son interface Ethernet 0/1.

### Half Duplex - Full Duplex

Lorsque 2 éléments communiquent entre-eux via un câble, ils peuvent échanger des données en même temps.
- en half-duplex, cela peut poser des problèmes de **collision** et altérer les données
- en full-duplex, il n'y a pas de problèmes, les données peuvent transiter dans les deux sens en même temps

Aujourd'hui, uniquement du **Full Duplex**. Il est possible de rencontrer du **Half Duplex** sur les anciennes infrastructures.