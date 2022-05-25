---------------------------------------------------------------------------
			Création de la base de données "location"
---------------------------------------------------------------------------

j'ai créer la base de données "location" contenant cinq entités (tables) avec toutes leurs propiétes

syntaxe:  CREATE DATABASE IF NOT EXISTS location



------------------------------------------------------------------------------------------
		creation de tables ou entités de la base de données "location"
------------------------------------------------------------------------------------------
 créer les différentes tables dans cet ordre: clients, films, louer, paiement, categoriesfilms.

syntaxe pour créer une table exemple de la création de la table Client)

CREATE TABLE IF NOT EXISTS clients (
  idclient int(11) NOT NULL AUTO_INCREMENT,
  nomclient varchar(45) NOT NULL,
  prenomclient varchar(50) NOT NULL,
  email varchar(50) NOT NULL,
  datecreation date NOT NULL,
  date_mise_jour date NOT NULL,
  PRIMARY KEY (idclient)
);



-----------------------------------------------------------------------------------------------------
					Modélisation UML
-----------------------------------------------------------------------------------------------------

 géréré le diagramme UML (dans longlet "File" MySQL Workbench => "export as" et choisir le format sur lequel tu souhaite l'exportation).
 


------------------------------------------------------------------------------------------------
					Requêtes SQL
------------------------------------------------------------------------------------------------
Quelques requêtes pour faire des essais

1. afficher les titres et dates de sorties des films du plus récent au plus ancien.
syntaxe: 	SELECT codefilm, datesortie, titrefilm
		FROM films
		ORDER BY datesortie DESC;


===========requêtes pour AJOUTER, MODIFIER et SUPPRIMER un fiml ensuite afficher les derniers films ajoutés ========================
1. une requête pour ajouter un film
syntaxe: INSERT INTO nom_tablevVALUES("valeur1","valeur2",...)
		INSERT INTO films VALUES ("1", "Lune de miel", "2021-12-12", "2021-12-12-01-23-52", "inconu", "1999-04-21", "2002-03-04", "1")

2. une requête pour modifier un film
syntaxe: UPDATE nom_table SET nom_attribut = nouvelle_valeur WHERE condition
		UPDATE films SET titrefilm = 'EN_CAVALE' WHERE codefilm = 4;

3. une requête pour supprimer un film
syntaxe: DELETE FROM nom_table WHERE condition
		DELETE FROM films WHERE codefilm = 11 

4. une requête pour afficher les 3 derniers films ajoutés
syntaxe: 
		SELECT codefilm, titrefilm, datesortie
		FROM films
		ORDER BY datesortie ASC LIMIT 3



===========requêtes pour AJOUTER, MODIFIER et SUPPRIMER un client ensuite afficher les derniers films ajoutés ========================
1. une requête pour ajouter un film
syntaxe: INSERT INTO nom_tablevVALUES("valeur1","valeur2",...)
		INSERT INTO clients VALUES ("9", "Marie", "Claire", "Claire@gmail.com", "2022-04-12", "2022-04-21")

2. une requête pour modifier un film
syntaxe: UPDATE nom_table SET nom_attribut = nouvelle_valeur WHERE condition
		UPDATE clients SET nomclient = 'Marie_De_Jésus' WHERE idclient = 9;

3. une requête pour supprimer un film
syntaxe: DELETE FROM nom_table WHERE condition
		DELETE FROM clients WHERE idclient = 9 

4. une requête pour afficher les 5 derniers clients ajoutés
syntaxe: 
		SELECT idclient, nomclient, prenomclient, email
		FROM clients
		ORDER BY datecreation ASC LIMIT 5





=======================================================
implémentation

pour un dev web qui souhaite implémenter le base de données il vous suffit de cloner le projet sur GitHub
ensuite importer la base de données sur votre serveur de base de données Soit WAMP XAMP sous PhpMyAdmin ou MySQL Workbench, générer le model( diagramme de classe).
et c'est tout
merci !!!
=======================================================