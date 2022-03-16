Configuration du driver ODBC
============================

ODBC (Open Database Connectivity) est un protocole permettant de connecter une application à une source de données. Ce protocole a été nativement développé en environnement Windows; il est également disponible sur MacOS et il existe quelques drivers sur Linux.
Ce protocole permet de se passer d'un serveur de données, ces dernières étant servies à la volée par le logiciel abritant la base. Il en resulte qu'un seul utilisateur peut s'y connecter simultanément, et que le logiciel les servant doit de préférence se trouver sur la même machine que le logiciel tiers qui les consomme.
 
Paramétrage du driver ODBC (Windows)
------------------------------------

Téléchargement
~~~~~~~~~~~~~~

Télécharger, sur le site de l'éditeur, le driver **xDBC** correspondant à la version de FMPro installée. 
A priori, il existe peu de différence entre les différentes versions du driver. Ainsi, la version actuelle (FMPro 19) fonctionne sans problème avec la version 17 installée sur Windows 10.

.. NOTE::
    A l'inverse, il est possible qu'une version du driver ne soit pas complémentement fonctionnelle avec la version de FileMaker pour laquelle elle a été créée.

`Vers la page de téléchargement (Claris) <https://support.claris.com/s/article/Software-Update-FileMaker-xDBC-client-drivers-for-FileMaker-1503692806454?language=en_US>`_


Installation
~~~~~~~~~~~~

Extraire l'executable, se rendre dans le dossier ``FileMaker 19 xDBC\ODBC Client Driver Installer\`` et installer la version voulue (de préference, ``FMODBC_Installer_Win64.msi``)


Paramétrage du partage ODBC dans FileMaker
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

- ouvrir la BdD dans FileMaker
- dans :menuselection:`File --> Sharing --> Enable ODBC/JDBC`, ouvrir la boîte de dialogue *ODBC/JDBC Settings*.
- mettre *ODBC/JDBC Sharing* sur ``on``, avec le fichier courant, valable pour tous les utilisateurs, puis valider.

.. NOTE::
    Laisser FileMaker et la BdD ouverts tant que l'on souhaite partager les données avec une application tiers.


Paramétrage du gestionnaire ODBC de Windows
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Saisir ``ODBC`` dans l'invite de recherche de Windows et lancer ``ODBC Data Source (64-bit)``. Si le driver ODBC pour FileMaker a bien été installé, on doit pouvoir, dans l'onglet *User DSN*, ajouter une nouvelle source de données :

- Cliquer sur `add`
- Sélectionner `FileMaker ODBC` dans la fenêtre `Create New Data Source`, puis `Finish`
- Donner un nom à cette source de données. Par exemple, `Delos`; le remplissage du champ `description` est facultatif
- Si le fichier fmp12 se trouve sur le même poste, il faut renseigner l'hôte `localhost` ou `127.0.0.1`. Si le fichier est ouvert sur un autre poste, il faut renseigner l'IP appropriée.
- Certificat SSL : `se connecter` ou `se connecter avec avertissement`... peu importe...
- Dans la liste déroulante, sélectionner le nom de la base qui devrait normalement s'y afficher.


.. IMPORTANT:: 
    Pour que les caractères grecs soient pleinement pris en compte, il faut accéder aux options de `langue avancée`, décocher la détection automatique et forcer l'encodage du texte en `UTF-8` puis valider.

.. warning:: 
    Je n'ai pas testé ce paramètrage, mais peut-être serait-ce judicieux : cocher `Interpréter les rubriques Texte comme long varchar`

- Terminer, puis fermer ce gestionnaire ODBC.

.. seealso:: 
    Pour plus de détail, voir sur le site de l'éditeur : `Configuring a DSN for FileMaker ODBC drivers <https://support.claris.com/s/article/Configuring-a-DSN-for-FileMaker-ODBC-drivers-1503693049730?language=en_US>`_


Associer la source de données à QGIS
------------------------------------



- Accéder au `Data Source Manager` (`Layer\Data Source Manager` ou `CTRL-L`)
- Dans la rubrique Vector, séléctionner `Database` comme  `Source Type`
- **IMPORTANT** : pour la prise en compte des caractères grecs, spécifier l'encodage en `UTF-8`

- Dans la sous-rubrique `Database`, Sélectionner `ODBC` dans la liste déroulante
- Créer une nouvelle connexion en sélectionnant celle que nous avons précédemment créée ou en spécifiant les données suivantes :
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

