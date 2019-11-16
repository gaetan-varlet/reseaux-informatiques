# Les réseaux informatiques

## Introduction aux réseaux informatiques

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


# Couche 2 du modèle OSI - Liaison de données
