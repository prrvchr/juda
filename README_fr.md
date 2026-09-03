<!--
╔════════════════════════════════════════════════════════════════════════════════════╗
║                                                                                    ║
║   Copyright (c) 2020-25 https://prrvchr.github.io                                  ║
║                                                                                    ║
║   Permission is hereby granted, free of charge, to any person obtaining            ║
║   a copy of this software and associated documentation files (the "Software"),     ║
║   to deal in the Software without restriction, including without limitation        ║
║   the rights to use, copy, modify, merge, publish, distribute, sublicense,         ║
║   and/or sell copies of the Software, and to permit persons to whom the Software   ║
║   is furnished to do so, subject to the following conditions:                      ║
║                                                                                    ║
║   The above copyright notice and this permission notice shall be included in       ║
║   all copies or substantial portions of the Software.                              ║
║                                                                                    ║
║   THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND,                  ║
║   EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES                  ║
║   OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT.        ║
║   IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY             ║
║   CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT,             ║
║   TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE       ║
║   OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.                                    ║
║                                                                                    ║
╚════════════════════════════════════════════════════════════════════════════════════╝
-->
# Documentation

**This [document][1] in English.**

# version [484][2]

## Introduction:

**juda** est une version amélioré de [Trino][3].  
C'est l'une des [améliorations][4] que j'ai déjà pu apporter à certains logiciels.

juda est le résultat de la fusion des pull requests suivantes :

- [New HsqlDB connector][5]
- [New Firebird connector][6]
- [New Sqlite connector][7]
- [Improvement of ResultSet metadata][8]
- [Add support for case sensitive identifiers][9]

Son code source est rassemblé dans le PR [juda][10] (Java Unified Database Access).

Grâce à ces modifications, le serveur **juda** est un serveur **Trino** qui prend en charge:
- Des identifiants sensibles à la casse.
- Des ensembles de résultats (ResultSets) fournissant les métadonnées suivantes:
  - Nom du catalogue.
  - Nom du schéma.
  - Nom de la table.
  - Indication si la colonne est en auto-incrémentation.
  - Indication si la colonne est en lecture seule.
- 3 connecteurs supplémentaires:
  - [HyperSQL][11].
  - [Firebird][12].
  - [SQLite][13].

Libéré de ces limitations et combiné à [LibreOffice Base][14] et [jdbcDriverOOo][15], il permet d'exécuter des requêtes sur des tables issues de différentes bases de données.  
Il est même possible de modifier ces tables au sein des grilles de données affichées dans Base.

Etant un logiciel libre je vous encourage:
- A dupliquer son [code source][10].
- A apporter des modifications, des corrections, des améliorations.
- D'ouvrir un [dysfonctionnement][16] si nécessaire.
- De [participer au frais][17] de la [certification CASA][18].

Bref, à participer au developpement de cette extension.  
Car c'est ensemble que nous pouvons rendre le Logiciel Libre plus intelligent.

___

## Prérequis:

Le serveur juda est écrit en Java.  
Son utilisation nécessite l'installation d'un **JRE ou JDK Java version 25 ou ultérieure**.  
Je vous recommande [Adoptium][19] comme source d'installation de Java.

Le serveur juda est une application conteneurisée avec [Docker][20].  
Il est donc nécessaire que Docker soit déjà installé.

___

## Installation:

- ![juda logo][21] Télécharger le fichier **[trino-server-484-SNAPSHOT][22]** [![Version][23]][22]

Puis décompresser ce fichier dans le répertoire de votre choix.  
Et enfin, copiez le contenu du dossier `trino-server-484-SNAPSHOT` du dépôt vers le dossier correspondant dans le répertoire choisi.

___

## Utilisation:

Si nécessaire, dans le fichier de configuration `docker-compose.yml`, le nom de l'image Docker pour le coordinateur (`trino:484-SNAPSHOT-amd64`) doit être adaptée à votre architecture.

Les catalogues pris en charge par le serveur sont définis par les fichiers `.properties` situés dans le dossier:  
`trino-server-484-SNAPSHOT/etc/catalog`.  
Des exemples de fichiers `.properties` sont fournis dans le dossier racine du dépôt.

Ces fichiers sont configurés avec les paramètres par défaut spécifiques à chaque base de données.  
Toutefois, si vous souhaitez utiliser le connecteur SQLite, vous devez modifier le paramètre `connection-url` pour qu'il pointe vers votre fichier ou, du moins, vers un dossier existant.  
Pour les autres connecteurs, le dépôt [dockerDB][24] permet de mettre en place une base de données très rapidement, sans aucune dépendance autre que Docker.

Pour contrôler le serveur, vous devez vous rendre dans le répertoire: `trino-server-484-SNAPSHOT/bin` et saisir les commandes suivantes:
- Démarrer le serveur : `./launcher run`
- Arrêter le serveur : `./launcher stop`

Si le serveur juda s'exécute sur la même machine:
- Pour vous connecter au serveur, vous devez utiliser l'URL suivante:
  - Pour une connexion en dehors de LibreOffice: `jdbc:trino://localhost:8080`
  - Pour une connexion via LibreOffice Base: `//localhost:8080`, après avoir sélectionné `Juda pure Java` comme type de source de données.
- L'activité du serveur peut être surveillée à l'aide d'un navigateur à l'adresse: `localhost:8080`.

___

## Historique:

### Ce qui a été fait pour la version 484:

Le projet juda 484 a nécessité plus de six mois de travail et l'ajout de près de 30 000 lignes de code à Trino afin d'en faciliter l'utilisation.  
L'essentiel de ce travail est visible à travers les diverses [demandes de tirage (PR) ajoutées au dépôt Trino][25].

[1]: <https://prrvchr.github.io/juda/>
[2]: <https://prrvchr.github.io/juda/README_fr#ce-qui-a-%C3%A9t%C3%A9-fait-pour-la-version-484>
[3]: <https://github.com/trinodb/trino>
[4]: <https://prrvchr.github.io/README_fr>
[5]: <https://github.com/trinodb/trino/pull/30506>
[6]: <https://github.com/trinodb/trino/pull/30483>
[7]: <https://github.com/trinodb/trino/pull/27768>
[8]: <https://github.com/trinodb/trino/pull/27321>
[9]: <https://github.com/trinodb/trino/pull/29845>
[10]: <https://github.com/trinodb/trino/pull/30916>
[11]: <https://hsqldb.org/>
[12]: <https://www.firebirdsql.org/>
[13]: <https://www.sqlite.org/>
[14]: <https://fr.libreoffice.org/download/>
[15]: <https://prrvchr.github.io/jdbcDriverOOo/>
[16]: <https://github.com/prrvchr/juda/issues/new>
[17]: <https://github.com/sponsors/prrvchr>
[18]: <https://appdefensealliance.dev/casa>
[19]: <https://adoptium.net/fr/temurin/releases?version=25&package=jre&os=any&arch=any>
[20]: <https://www.docker.com/>
[21]: <img/juda-icon.svg#middle>
[22]: <https://github.com/prrvchr/juda/releases/download/484/trino-server-484-SNAPSHOT.tar.gz>
[23]: <https://img.shields.io/github/downloads/prrvchr/juda/latest/total?label=484#right>
[24]: <https://prrvchr.github.io/dockerDB/README_fr>
[25]: <https://github.com/trinodb/trino/issues?q=is%3Aopen%20is%3Apr%20author%3Aprrvchr>
