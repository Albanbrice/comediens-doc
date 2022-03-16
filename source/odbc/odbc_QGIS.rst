Associer la source de données à QGIS
------------------------------------

Les instructions suivantes ont été testées avec des versions récentes de QGIS (3.18, 3.24)

`Pour télécharger votre version de QGIS <https://www.qgis.org/en/site/forusers/download.html>`_



- Accéder au `Data Source Manager` (`Layer\Data Source Manager` ou `CTRL-L`)

.. figure:: /images/QGIS_odbc_01.png

- Dans la rubrique `Vector` : 

    - dans `Source Type`, cocher `Database`, en demandant un encodage en `UTF-8`.
    - dans la section `Database`,selectionner `ODBC` dans le menu déroulant `Type`.

.. important:: 
    L'encodage en `UTF-8` est necessaire pour la bonne retranscription des caractères grecs.

.. figure:: /images/QGIS_odbc_02.png



- Créer une nouvelle connexion en spécifiant les paramètres suivants :

.. figure:: /images/QGIS_odbc_03.png

    
    - `Type` : ODBC
    - `Name` : le nom que l'on souhaite
    - `Host` : localhost
    - `Database` : le nom que l'on a défini dans le gestionnaire ODBC de Windows
    - `Port` : peu rester vide
    - Si l'on a défini un utilisateur et mot de passe, il faut le renseigner dans la rubrique autentification. Cela sera demander à plusieurs reprises.
    - Tester la connexion puis valider le cas échéant.
    - Selectionner la base que l'on vient de renseigner dans la liste déroulante, puis cliquer sur `add`
    - Après un court délai, une fenêtre s'ouvre avec la liste des tables contenues dans la base FileMaker, dont on peut sélectionner tout ou partie et ouvrir dans QGIS. 
    - Les tables seront empilées dans la palette des calques, il est possible de les inspecter une à une par un clic-droit, `Open Attribute Table`
    - si les textes en grec ne s'affichent toujours pas correctement, aller dans les propriétés du claque et forcer encore une fois l'encodage en `UTF-8`. 
