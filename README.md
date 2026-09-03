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

**Ce [document][1] en français.**

# version [484][2]

## Introduction:

**juda** is an improved version of [Trino][3].  
This is one of the [improvements][4] I have already been able to make to certain software programs.

juda is the merger of the following PRs:

- [New HsqlDB connector][5]
- [New Firebird connector][6]
- [New Sqlite connector][7]
- [Improvement of ResultSet metadata][8]
- [Add support for case sensitive identifiers][9]

Its source code is consolidated in the PR [juda][10] (Java Unified Database Access).

Combined with [LibreOffice Base][11] and [jdbcDriverOOo][12], it allows you to execute queries on tables from different databases.
It is even possible to edit these tables within the data grids displayed in Base.

Being free software I encourage you:
- To duplicate its [source code][10].
- To make changes, corrections, improvements.
- To open [issue][13] if needed.
- To [participate in the costs][14] of [CASA certification][15].

In short, to participate in the development of this extension.  
Because it is together that we can make Free Software smarter.

___

## Requirement:

The juda server is written in Java.  
Its use requires the installation of a **Java JRE or JDK version 25 or later**.  
I recommend [Adoptium][16] as your Java installation source.

The juda server is an application containerized with [Docker][17].  
It is therefore necessary for Docker to be already installed.

___

## Installation:

- ![juda logo][18] Download the file **[trino-server-484-SNAPSHOT][19]** [![Version][20]][19]

Then, extract this file into a directory of your choice.  
Finally, copy the contents of the `trino-server-484-SNAPSHOT` folder from the repository to the corresponding folder in the chosen directory.

___

## Use:

If necessary, in the `docker-compose.yml` configuration file, the Docker image name for the coordinator (`trino:484-SNAPSHOT-amd64`) must be adapted to your architecture.

The catalogs supported by the server are defined by the `.properties` files located in the folder:  
`trino-server-484-SNAPSHOT/etc/catalog`.  
Example `.properties` files are provided in the repository's root folder.

These files are configured with the default settings specific to each database.  
However, if you wish to use the SQLite connector, you must modify the `connection-url` parameter to point to your file or at least an existing folder.  
For the other connectors, the [dockerDB][21] repository allows you to set up a database very quickly, with no dependencies other than Docker.

To control the server, you need to navigate to the `trino-server-484-SNAPSHOT/bin` directory and enter the following commands:
- Start the server: `./launcher run`
- Stop the server: `./launcher stop`

If the juda server is running on the same machine:
- To connect to the server you must use the following URL:
  - For a connection outside of LibreOffice: `jdbc:trino://localhost:8080`
  - For a connection using LibreOffice Base: `//localhost:8080`, having selected `Juda pure Java` as the data source type.
- Server activity can be monitored using a browser at the address: `localhost:8080`.

___

## Historical:

### What was done for version 484:

The juda 484 project required over six months of work and the addition of nearly 30,000 lines of code to Trino to make it easier to use.  
Most of this work is visible through the various [PRs added to the Trino repository][22].

[1]: <https://prrvchr.github.io/juda/README_fr>
[2]: <https://prrvchr.github.io/juda#what-was-done-for-version-484>
[3]: <https://github.com/trinodb/trino>
[4]: <https://prrvchr.github.io/>
[5]: <https://github.com/trinodb/trino/pull/30506>
[6]: <https://github.com/trinodb/trino/pull/30483>
[7]: <https://github.com/trinodb/trino/pull/27768>
[8]: <https://github.com/trinodb/trino/pull/27321>
[9]: <https://github.com/trinodb/trino/pull/29845>
[10]: <https://github.com/trinodb/trino/pull/30916>
[11]: <https://www.libreoffice.org/download/>
[12]: <https://prrvchr.github.io/jdbcDriverOOo/>
[13]: <https://github.com/prrvchr/juda/issues/new>
[14]: <https://github.com/sponsors/prrvchr>
[15]: <https://appdefensealliance.dev/casa>
[16]: <https://adoptium.net/temurin/releases?version=25&os=any&arch=any>
[17]: <https://www.docker.com/>
[18]: <img/juda-icon.svg#middle>
[19]: <https://github.com/prrvchr/juda/releases/download/484/trino-server-484-SNAPSHOT.tar.gz>
[20]: <https://img.shields.io/github/downloads/prrvchr/juda/latest/total?label=484#right>
[21]: <https://prrvchr.github.io/dockerDB/>
[22]: <https://github.com/trinodb/trino/issues?q=is%3Aopen%20is%3Apr%20author%3Aprrvchr>
