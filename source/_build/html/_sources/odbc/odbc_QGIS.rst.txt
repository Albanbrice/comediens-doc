Paramétrage de la source ODBC dans QGIS
---------------------------------------

Les instructions suivantes ont été testées avec les versions 3.18 et 3.24 de QGIS (64-bit).

    `Pour télécharger votre version de QGIS <https://www.qgis.org/en/site/forusers/download.html>`_


Paramétrage dans le Data Source Manager
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~


1. Accéder au **Data Source Manager** : :menuselection:`Layer --> Data Source Manager` ou :kbd:`CTRL-L`

.. figure:: /images/QGIS_odbc_01.png

2. Dans la partie `Vector` du **Data Source Manager** :

- dans **Source Type**, cocher ``Database``, en demandant un encodage en ``UTF-8``.
- dans la section **Database**, selectionner ``ODBC`` dans le menu déroulant `Type`.

.. figure:: /images/QGIS_odbc_02.png

.. important:: 
        L'encodage en `UTF-8` est necessaire pour la bonne retranscription des caractères grecs.



3. Créer une nouvelle connexion en renseignant les champs suivants :

.. figure:: /images/QGIS_odbc_03.png

.. list-table:: Connection Information
    :header-rows: 1


    * - champ
      - valeur
      - commentaire
    * - Type
      - ODBC
      - obligatoire
    * - Name
      - Delos
      - nom que l'on souhaite donner à cette connexion dans QGIS
    * - Host
      - localhost
      - localhost, 127.0.0.1 ou autre IP
    * - Database
      - Delos
      - nom de la base que l'on a exposé via le driver ODBC
    * - Port
      -
      - facultatif


.. figure:: /images/QGIS_odbc_04.png

.. figure:: /images/QGIS_odbc_05.png

.. figure:: /images/QGIS_odbc_06.png

.. figure:: /images/QGIS_odbc_07.png

Réglages complémentaires
~~~~~~~~~~~~~~~~~~~~~~~~
A l'importation, les tables sont chargées dans le **Layers Panel** de QGIS. S'agissant de données exposées à la volée depuis FMPro, celles-ci ne disposent pas d'entités géographiques (pas de points, de lignes ou de surfaces) et ne peuvent donc pas être représentées graphiquement dans l'espace de travail.
On va procéder à plusieurs vérifications et réglages pour s'assurer que les données tabulaires peuvent s'afficher correctement.

1. :kbd:`clic-droit` sur une des tables affichées dans le **Layers Panel**, pour en afficher les `Properties`

    
.. figure:: /images/QGIS_odbc_08.png

2. Dans les **Layer Properties**, rubrique `Source`, on s'assure que l'encodage est bien en ``UTF-8``, puis on valide (``Apply``). On peut fermer le **Layer Properties** (``OK``)

.. warning:: 
    Un autre type d'encodage posera problème avec l'affichage des caractères grecs.

.. figure:: /images/QGIS_odbc_09.png  

3. :kbd:`clic-droit` sur une des tables affichées dans le **Layers Panel**, pour afficher cette fois la table attributaire `Open Attribute Table`

.. figure:: /images/QGIS_odbc_10.png

4. On vérifie la qualité des données. Ici les caractères grecs sont bien rendus.

.. figure:: /images/QGIS_odbc_11.png

5. On peut retourner dans les **Layer Properties** et vérifier, cette fois dans la rubrique `Information`, section `Information from provider`, que les données sont correctement endcodées. 

.. figure:: /images/QGIS_odbc_12.png