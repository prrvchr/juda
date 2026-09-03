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

**Juda Server** is an improved version of [Trino][3].

Juda is the merger of the following PRs:

- [New HsqlDB connector][4]
- [New Firebird connector][5]
- [New Sqlite connector][6]
- [Improvement of ResultSet metadata][7]
- [Add support for case sensitive identifiers][8]

Combined with [LibreOffice Base][9] and [jdbcDriverOOo][10], it allows you to execute queries on tables from different databases.
It is even possible to edit these tables within the data grids displayed in Base.

Being free software I encourage you:
- To duplicate its [source code][11].
- To make changes, corrections, improvements.
- To open [issue][12] if needed.
- To [participate in the costs][13] of [CASA certification][14].

In short, to participate in the development of this extension.  
Because it is together that we can make Free Software smarter.

___

## Requirement:

Juda server is written in Java.  
Its use requires the installation of a **Java JRE or JDK version 25 or later**.  
I recommend [Adoptium][15] as your Java installation source.

The Juda server is an application containerized with [Docker][16].  
It is therefore necessary for Docker to be already installed.

___

## Installation:

You need to download the [Juda 484 server][17], available in the repository versions.  
Then, extract this file into a directory of your choice.  
Finally, copy the contents of the `trino-server-484-SNAPSHOT` folder from the repository to the corresponding folder in the chosen directory.

___

## Use:

The catalogs supported by the server are defined by the `.properties` files located in the folder:  
`trino-server-484-SNAPSHOT/etc/catalog`.
Example `.properties` files are provided in the repository's root folder.

These files are configured with the default settings specific to each database.  
However, if you wish to use the SQLite connector, you must modify the `connection-url` parameter to point to your file.

To control the server, you need to navigate to the `trino-server-484-SNAPSHOT/bin` directory and enter the following commands:
- Start the server: `./launcher run`
- Stop the server: `./launcher stop`

___

## Historical:

### What has been done for version 484:

Juda 484 involved over six months of work adding nearly 30,000 lines of code to Trino to make it easy to use.  
Most of this work is visible through the various [PRs added to the Trino repository][18].

[1]: <https://prrvchr.github.io/Juda-Server/README_fr>
[2]: <https://prrvchr.github.io/Juda-Server#what-has-been-done-for-version-484>
[3]: <https://github.com/trinodb/trino>
[4]: <https://github.com/trinodb/trino/pull/30506>
[5]: <https://github.com/trinodb/trino/pull/30483>
[6]: <https://github.com/trinodb/trino/pull/27768>
[7]: <https://github.com/trinodb/trino/pull/27321>
[8]: <https://github.com/trinodb/trino/pull/29845>
[9]: <https://www.libreoffice.org/download/>
[10]: <https://prrvchr.github.io/jdbcDriverOOo/>
[11]: <https://github.com/prrvchr/jdbcDriverOOo/>
[12]: <https://github.com/prrvchr/Juda-Server/issues/new>
[13]: <https://github.com/sponsors/prrvchr>
[14]: <https://appdefensealliance.dev/casa>
[15]: <https://adoptium.net/temurin/releases/?version=25&package=jre>
[16]: <https://www.docker.com/>
[17]: <https://github.com/prrvchr/Juda-Server/releases/download/484/trino-server-484-SNAPSHOT.tar.gz>
[18]: <https://github.com/trinodb/trino/issues?q=is%3Aopen%20is%3Apr%20author%3Aprrvchr>
