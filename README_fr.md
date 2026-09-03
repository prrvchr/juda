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

**Juda Server** est une version amélioré de [Trino][3].

Juda est le résultat de la fusion des pull requests suivantes :

- [New HsqlDB connector][4]
- [New Firebird connector][5]
- [New Sqlite connector][6]
- [Improvement of ResultSet metadata][7]
- [Add support for case sensitive identifiers][8]

Associé à [LibreOffice Base][9] et [jdbcDriverOOo][10], il permet d'exécuter des requêtes sur des tables provenant de différentes bases de données.
Il est même possible de modifier ces tables au sein des grilles de données affichées dans Base.

Etant un logiciel libre je vous encourage:
- A dupliquer son [code source][11].
- A apporter des modifications, des corrections, des améliorations.
- D'ouvrir un [dysfonctionnement][12] si nécessaire.
- De [participer au frais][13] de la [certification CASA][14].

Bref, à participer au developpement de cette extension.  
Car c'est ensemble que nous pouvons rendre le Logiciel Libre plus intelligent.

___

## Prérequis:

Le serveur Juda est écrit en Java.  
Son utilisation nécessite l'installation d'un **JRE ou JDK Java version 25 ou ultérieure**.  
Je vous recommande [Adoptium][15] comme source d'installation de Java.

Le serveur Juda est une application conteneurisée avec [Docker][16].  
Il est donc nécessaire que Docker soit déjà installé.

___

## Installation:

Vous devez télécharger le [serveur Juda 484][17], disponible dans les versions du dépôt.  
Puis décompresser ce fichier dans le répertoire de votre choix.  
Et enfin, copiez le contenu du dossier `trino-server-484-SNAPSHOT` du dépôt vers le dossier correspondant dans le répertoire choisi.

___

## Utilisation:

Les catalogues pris en charge par le serveur sont définis par les fichiers `.properties` situés dans le dossier:  
`trino-server-484-SNAPSHOT/etc/catalog`.
Des exemples de fichiers `.properties` sont fournis dans le dossier racine du dépôt.

Ces fichiers sont configurés avec les paramètres par défaut spécifiques à chaque base de données.  
Toutefois, si vous souhaitez utiliser le connecteur SQLite, vous devez modifier le paramètre `connection-url` pour qu'il pointe vers votre fichier.

Pour contrôler le serveur, vous devez vous rendre dans le répertoire: `trino-server-484-SNAPSHOT/bin` et saisir les commandes suivantes:
- Démarrer le serveur : `./launcher run`
- Arrêter le serveur : `./launcher stop`

___

## Historique:

### Ce qui a été fait pour la version 484:

Le projet Juda 484 a nécessité plus de six mois de travail et l'ajout de près de 30 000 lignes de code à Trino afin d'en faciliter l'utilisation.  
L'essentiel de ce travail est visible à travers les diverses demandes de [tirage (PR) ajoutées au dépôt Trino][18].

[1]: <https://prrvchr.github.io/Juda-Server/>
[2]: <https://prrvchr.github.io/Juda-Server/README_fr#ce-qui-a-%C3%A9t%C3%A9-fait-pour-la-version-484>
[3]: <https://github.com/trinodb/trino>
[4]: <https://github.com/trinodb/trino/pull/30506>
[5]: <https://github.com/trinodb/trino/pull/30483>
[6]: <https://github.com/trinodb/trino/pull/27768>
[7]: <https://github.com/trinodb/trino/pull/27321>
[8]: <https://github.com/trinodb/trino/pull/29845>
[9]: <https://fr.libreoffice.org/download/>
[10]: <https://prrvchr.github.io/jdbcDriverOOo/>
[11]: <https://github.com/prrvchr/jdbcDriverOOo/>
[12]: <https://github.com/prrvchr/Juda-Server/issues/new>
[13]: <https://github.com/sponsors/prrvchr>
[14]: <https://appdefensealliance.dev/casa>
[15]: <https://adoptium.net/temurin/releases/?version=25&package=jre>
[16]: <https://www.docker.com/>
[17]: <https://github.com/prrvchr/Juda-Server/releases/download/484/trino-server-484-SNAPSHOT.tar.gz>
[18]: <https://github.com/trinodb/trino/issues?q=is%3Aopen%20is%3Apr%20author%3Aprrvchr>
