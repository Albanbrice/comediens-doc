Paramétrage du gestionnaire ODBC de Windows
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~


Saisir ``ODBC`` dans l'invite de recherche de Windows et lancer ``ODBC Data Source (64-bit)``.

.. figure:: /images/WIN_DataSources.png

Si le driver ODBC pour FileMaker a bien été :doc:`installé </odbc/installation>` et si la base est correctement ouverte et :doc:`partagée </odbc/odbc_FMPro>` dans FileMaker, on doit pouvoir, dans l'onglet *User DSN* (ou *System DSN*), ajouter une nouvelle source de données en cliquant sur `add`.



.. figure:: /images/DSN_FM.png

- Sélectionner `FileMaker ODBC` dans la fenêtre `Create New Data Source`, puis `Finish`.

.. figure:: /images/DSN_FM_00.png


- Une nouvelle fenêtre de configuration s'affiche, suivre pas à pas la procédure.

.. figure:: /images/DSN_FM_01.png


- Donner un nom à cette source de données. Par exemple, `Delos`; le remplissage du champ `description` est facultatif. Par convention, et pour éviter tout problème d'interconnexion, il est préférable de n'utiliser que des caractères non accentués dans le nom de la source.

.. figure:: /images/DSN_FM_02.png

- Si le fichier fmp12 se trouve sur le même poste, il faut renseigner l'hôte `localhost` ou `127.0.0.1`. Si le fichier est ouvert sur un autre poste, il faut renseigner l'IP appropriée.
- Certificat SSL : `se connecter` ou `se connecter avec avertissement`... peu importe...

.. figure:: /images/DSN_FM_03.png



- Dans la liste déroulante, sélectionner le nom de la base qui devrait normalement s'y afficher.

.. warning::
    Je n'ai pas testé ce paramètrage, mais peut-être serait-ce judicieux de cocher `Interpréter les rubriques Texte comme long varchar`.

.. figure:: /images/DSN_FM_04.png

.. IMPORTANT:: 
    Pour que les caractères grecs soient pleinement pris en compte, il faut accéder aux options de `langue avancée`, décocher la détection automatique et forcer l'encodage du texte en `UTF-8` puis valider.



.. figure:: /images/DSN_FM_05.png


- La configuration achevée, on vérifie les différents paramètres, notamment l'encodage en UTF-8, puis on s'assure que la connexion fonctionne en la testant.

.. figure:: /images/DSN_FM_06.png

- Si l'on a précisé, au sein de FileMaker, des droits d'accès à la base, ce qui est une bonne pratique, on est invité à les saisir.

.. figure:: /images/DSN_FM_07.png

.. figure:: /images/DSN_FM_08.png   

- Si le test de connexion est positif, on peut terminer la configuration puis fermer le gestionnaire ODBC. Comme indiqué précédemment, FileMaker devra toutefois rester ouvert avec le fichier en cours pour maintenir l'exposition des données.

.. seealso:: 
    Pour plus de détails, voir sur le site de l'éditeur : `Configuring a DSN for FileMaker ODBC drivers <https://support.claris.com/s/article/Configuring-a-DSN-for-FileMaker-ODBC-drivers-1503693049730?language=en_US>`_