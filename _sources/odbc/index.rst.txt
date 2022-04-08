Configuration du protocole ODBC
==================================

ODBC (Open Database Connectivity) est un protocole permettant de connecter une application à une source de données. Ce protocole a été nativement développé en environnement Windows; il est également disponible sur MacOS et il existe quelques drivers sur Linux. Ce protocole permet de se passer d'un serveur de données, ces dernières étant servies à la volée par le logiciel abritant la base. Il en resulte qu'un seul utilisateur peut s'y connecter simultanément, et que le logiciel les servant doit de préférence se trouver sur la même machine que le logiciel tiers qui les consomme.

.. toctree:: 
    :maxdepth: 2

    installation.rst
    odbc_FMPro.rst
    odbc_Windows.rst
    odbc_QGIS.rst