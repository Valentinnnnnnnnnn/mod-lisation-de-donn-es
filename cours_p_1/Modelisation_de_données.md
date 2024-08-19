# Modelisation de donnees (Merise, MCD, MLD, MPD)

## 0. Informations sur la prise de notes et la notation

- Les notes sont prises en Markdown
- Tout rendu se fait avec un depot Git
- La qualite de la prise de note fera partie de la note finale

- Au cours de l'examen l'utilisation ou toute suspicion d'utilisation de chat GPT entrainera une note de 0

## 1. Introduction a Git

Pour creer un depot Git, placez vous au sein d'un repertoire et entrez la commande :

```sh
git init
```

Cette commande va initialiser un depot Git, Git va traquer les toutes les modifications effectuées au sein de ce dossier.

Pour consulter l'etat du depot Git il suffit de lancer la commande :

```bash
git status
```

Pour ajouter des fichiers non suivis :

```bash
git add .
```

Pour sauvegarder votre travail :

```bash
git commit -m "votre message de commit"
```

## 2. Merise

Merise est une méthode de modélisation de données. Elle permet de représenter les données d'un système d'information.
Merise est un acrnonyme de : Méthode d'Etude et de Réalisation Informatique pour les Systèmes d'Entreprise.

Presentation generale
Cette methode se caracterise par trois points clés:

- une approche dite systemique : on transforme les processus de l'entreprise en systeme d'information
- une separation des donnees et des traitements
- une approche nivelée

### L'approche systemique

![Alt text](image.png)

Le systeme de pilotage:

- Il est compose de l'ensemble des acteurs qui vont **piloter** le systeme d'information

Le systeme d'information:

- Il est compose de l'ensemble des acteurs qui vont **utiliser** le systeme d'information

Le systeme operant :

- Il est compose de l'ensemble des acteurs qui vont **produire** les donnees du systeme d'information

### La separation des donnees et des traitements

La separation des donnees et des traitements permet de separer les donnees du systeme d'information et les traitements effectues sur ces donnees.
Cette demarche se fait en 3 etapes :

- L'analyse des flux : on analyse les flux d'informations entre les acteurs du systeme d'information et les acteurs du systeme operant
- L'etude des documents internes (factures, bon de livraison,)
- L'etude des documents en externes (fournisseurs, clients,).

Les differents types d'informations:

- les infos de bases ou elementaires : ce sont les donnees de base du systeme d'information
- les informations calculees : ce sont les donnees calculees a partir des donnees de base
- les traitements ou les fonctions : ce sont les traitements effectues sur les donnees de base pour obtenir les donnees calculees

En résumé : vous devrez identifier les données et les traitements effectués sur ces données.

### L'approche nivelée

Pour effectuer la conception d'un SI, on va utiliser une approche nivelée. Cette approche se compose de 4 niveaux :

- le niveau conceptuel
- le niveau organisationnel
- le niveau logique
- le niveau physique

#### Le niveau conceptuel

Le niveau conceptuel permet de modéliser les données de l'entreprise. On va utiliser le modèle conceptuel de données (MCD) pour modéliser les données de l'entreprise, et le MCT pour modéliser les traitements effectués sur ces données.

#### Le niveau organisationnel

Le niveau organisationnel va permettre d'integrer a l'analyse precedente toutes les notions de temporalite, de chronologie des operations, de contraintes geographique, niveau d'acces. On va utiliser le modele organisationnel des traitements (MOT) et le modele organisationnel des donnees (MOD) pour modéliser les traitements de l'entreprise.

En resume on se pose les questions suivantes a partir des donnees recueillies au niveau conceptuel :

- **Quand** les traitements sont-ils effectues ?
- **Où** les traitements sont-ils effectues ?
- Par **qui** les traitements sont-ils effectues ?

#### Le niveau logique

Le niveau logique va permettre de modéliser les données de l'entreprise en utilisant le modèle logique de données (MLD) et les traitements de l'entreprise en utilisant le modèle logique des traitements (MLT).

Le MLD est independant des langages de programmation et des SGBD (Systeme de Gestion de Base de Donnees).

On repond a la question : **Avec Quoi** les traitements sont-ils effectues ?

#### Le niveau physique

Il s'agit de l'organisation `réelle` des données. On va utiliser le modèle physique de données (MPD) et le modèle physique des traitements (MPT).

Ici, on apporte les solutions techniques de stockage des données et de traitement des données.

On repond a la question : **Comment** les traitements sont-ils effectues ?

#### Résumé: les 4 niveaux de Merise

![Alt text](image-1.png)

#### L'interet de la methodologie Merise

La force de la méthode Merise est de structurer les besoins des décideurs de façon simple et compréhensible. Merise améliore la communication entre les différents acteurs du processus de développement. Cette méthode, grâce à ses modèles, encadre le projet et de ce fait protège les intervenants d’un possible développement hors sujet.

Suivre ce cheminement intellectuel peut aussi aider l’entreprise à mieux se connaître, mieux se comprendre et ainsi mieux communiquer.

Le projet Merise s’articule autour d’un schéma directeur qui détermine et planifie le projet et ses enchaînements.

### Les dependances fonctionnelles

#### Des donnees aux dependances fonctionnelles

Pour etre integrees dans un systeme d'information, les donnees doivent etre triees et organisees. On va souvent tenter de les classer par type de donnees :

- chaines de caracteres, format texte
- type alphanumerique, format texte
- le type numerique (integer, float...)
- le type date (date, datetime, timestamp)
- le logique ou booleen (true, false)

Suite à l’interview et la collecte des documents, il est nécessaire de centraliser toutes les informations et règles de gestion (calcul d’un taux de remise par exemple) au sein d’un document. Ce document se nomme le dictionnaire des données.

Creation d'un dictionnaire de donnees

![Alt text](image-2.png)

Le dictionnaire de donnees est un document qui va permettre de recenser l'ensemble des donnees du systeme d'information. Il va permettre de recenser les donnees, les proprietes des donnees, les contraintes d'integrite, les dependances fonctionnelles.

Il suit une structure bien precise :

- le nom de la donnee
- le format de la donnee
- la longueur de la donnee
- le type de la donnee (elementaire, derivee, calculee)
- regle de calcul
- regle de gestion
- document

<u>Voici un exemple de dictionnaire de donnees :</u>

![Alt text](image-3.png)

#### Les dépendances fonctionnelles

Une dependance fonctionnelle est une relation entre deux attributs d'une table. Elle permet de definir une relation de dependance entre deux attributs d'une table.

Le role d'une dependance fonctionnelle est de permettre de definir une relation de dependance entre deux attributs d'une table: une donnee A depend fonctionnellement d'une donnee B lorsque la valeur de B determine la valeur de A.

Pour formaliser une dependance fonctionnelle on utilise la notation suivante :
`Numero adherent (Nom, prenom, code postal, ville, telephone, date d'adhesion, mail)`

La partie gauche (numero adherent) est la `source` de la dependance fonctionnelle.
La partie droite desgine le `but` de la dependance.

##### Les dependances fonctionnelles composees

Si une dependance fonctionnelle qui fait intervenir plus de deux attributs (source) on parle de dependance fonctionnelle composee.

Exemple: Pour connaitre le temps d'un coureur sur une etape donnee il nous faut son numero ou son nom ainsi que le nom ou le numero de l'etape.

Formalisation :
`(numero coureur, numero etape)  (temps)`

##### Les dependances fonctionnelles elementaires

Une dependance fonctionnelle A -> B est elementaire s'il n'existe pas une donnee C, sous-ensemble de A, decrivant une dependance fonctionnelle type C -> B.

Exemples :

- RefProduit -> LibelleProduit
- NumCommande RefProduit -> QuantiteCommandee
- <strike>NumCommande RefProduit -> DesignationProduit</strike>

##### Dependance fonctionnelle elementaire directe

"On dit que la dépendance fonctionnelle A -> B est directe s’il n’existe aucun attribut C tel que l’on puisse avoir A -> C et C -> B. En d’autres termes, cela signifie que la dépendance fonctionnelle entre A et B ne peut pas être obtenue par transitivité."

Exemple :

- RefPromo -> NumApprenant
- NumApprenant -> NomApprenant
- RefPromo -> NomApprenant : RefPromo -> NumApprenant -> NomApprenant

### Le Modele Conceptuel de Donnees (MCD)

Le MCD est un schema conceptuel qui permet de representer les donnees d'une entreprise. Il est compose de 3 elements principaux :

- les proprietes
- les entites
- les relations

#### Les proprietes

Les proprietes sont les informations de base d'un systeme d'information. Elles disposent d'un type et d'une longueur\*. Au niveau conceptuel nous n'allons pas décrire en detail les proprietes. Nous allons simplement les nommer.

#### Les entites ou objets

Les entités sont un ensemble de propriétés qui décrivent un objet du système d'information. Elles sont représentées par un rectangle.

![alt text](image-39.png)

##### L'identifiant

L'une de ces propriétés est l'identifiant. L'identifiant est une propriété qui permet d'identifier de manière unique une entité. Il est représenté par un souligné.

![alt text](image-40.png)

#### Les relations ou associations

Les relations permettent de relier les entités entre elles. Par exemple :

- un client peut passer une ou plusieurs commandes:
  ![alt text](image-41.png)

##### Les cardinalités

Une cardinalite exprime le nombre de fois ou l'occurrence d'une entite participe aux occurrences de la relation:

- Combien de fois au minimum un client peut-il commander un article ?
- Cmibne de fois au maximum un client peut-il commander un article ?

![alt text](image-42.png)

Pour obtenir la cardinalite suivante on se pose les memes questions, mais cette fois-ci pour l'entite Article.

![alt text](image-43.png)

Un petit exemple :

![alt text](image-44.png)

Les cardinalités:

- Une mere peut elever un ou plusieurs enfants
- un enfant peut etre eleve par une et une seule mere

![alt text](image-45.png)

##### Les relations porteuses

Une relation est dite porteuse si elle possede des proprietes.
Imaginons que nous souhaitions maintenant faire apparaitre la quantite d'articles commandes par un client. Nous allons donc ajouter une propriete a la relation.

![alt text](image-46.png)

Ci-dessus nous avons une relataion qui fait intervenir deux entites: c'est une relation <b> binaire </b>. Une relation faisant intervenir trois entites est dite <b> ternaire </b>.
![alt text](image-47.png)

##### Les relations reflexives

Une relation est dite reflexive si elle relie une entite a elle meme.
![alt text](image-48.png)

##### Quelques regles de conception

cf prise de notes

##### Notion d'entite forte et d'entite faible

##### Contraintes d'integrite fonctionnelle (CIF)

Une CIF est definie par le fait qu'une des entites de l'association est completement determinee par la connaissance d'une ou de plusieurs entites participant a l'association.

![alt text](image-49.png)

### Sujet TP/TD MCD jour 1

![Alt text](image-14.png)
![Alt text](image-5.png)
![Alt text](image-6.png)
![Alt text](image-7.png)

Le but de l'exercie est d'elaborer un MCD a partir d'un dictionnaire de donnees.

Ici on va introduire les notions d'entite, de relations et de propriétés.

##### Les proprietes sont les informations de bases d'un SI.

##### Les entités sont les objets du SI.

![Alt text](image-8.png)

Quelques definitions:

    - entite forte: une entite qui ne depend pas d'une autre entite pour exister
    - entite faible: une entite qui depend d'une autre entite pour exister

##### Les relations

![Alt text](image-9.png)

**Les cardinalités**: elles permettent de définir le nombre d'occurences d'une entité par rapport à une autre entité dans le cadre d'une relation.

![Alt text](image-10.png)

Petit Exemple :

![Alt text](image-11.png)

![Alt text](image-12.png)

![Alt text](image-13.png)

##### Les relations "porteuses"

Une relation est dite porteuse si elle possede des proprietes.

![Alt text](image-15.png)

![Alt text](image-16.png)

##### Les relations reflexives

Une relation est dite reflexive si elle relie une entite a elle meme.

![Alt text](image-17.png)

##### Quelques regles de conception :

- toute entite doit avoir un identifiant
- toutes les proprietes dependent fonctionnellement de l'identifiant
- le nom d'une propriete ne doit apparaitre qu'une seule fois dans le MCD : si vous avez une entite Eleve et une entite Professeur, vous ne pouvez pas avoir une propriete nom dans les deux entites. Il faut donc renommer la propriete nom de l'entite Professeur en nomProfesseur par exemple.
- les proprietes issues d'un calcul ne doivent pas apparaitre dans le MCD

Installation d'AnalyseSI, pre requis java :

Sur windows, creez la variable d'environnement systeme `JAVA_HOME` et mettez la valeur du chemin d'installation de java.

```
C:\Program Files\Java\jdk1.8.0_121
```

Modifier la variable d'environnement `PATH` et ajoutez `%JAVA_HOME%\bin`

Pour tester le fonctionnement, ouvrez un terminal et tapez la commande `java -version`

##### Les contraintes d'integrite fonctionnelle (CIF)

Definition : Une CIF est definie par le fait qu'une des entites de l'association est completement determinee par la connaissance d'une ou de plusieurs entites participant a l'association.

Exemple :

![Alt text](image-18.png)

Une Salle peut contenir 0 ou plusieurs Ordinateurs. Un ordinateur existe dans une et une seule salle.
Dans ce type de relation une CIF existe si on a une cardinalite 1,1

### Modele Logique des donnees (MLD)

Le MLD est la suite du processus Merise, on se rapproche un peu plus de la base de donnees.

#### Cas simple:
Partons du MCD suivant :

![Alt text](image-19.png)

Nous arrivons au MLD suivant :

![Alt text](image-20.png)

L'`entite` qui possede la cardinalite 1,1 ou 0,1 absorbe l'identifiant de l'entite la plus forte (0,n ou 1,n). Cet identifiant devient alors une cle etrangere.

#### Cas (0,n), (0,n) ou (1,n), (1,n)

Partons du MCD suivant :

![Alt text](image-21.png)

Dans le cas ou la `cardinalite max` est n des deux cotes, on cree une entite intermediaire qui va contenir les deux cles etrangeres des deux entites.

![Alt text](image-22.png)

Continuons avec le MCD suivant :

![Alt text](image-23.png)

On obtient le MLD suivant en suivant la meme logique:

![Alt text](image-24.png)

#### Cas d'une relation reflexive

Partons du MCD suivant :

![Alt text](image-25.png)

![Alt text](image-26.png)

#### Regles de passage du MCD au MLD

Règles simples de passage du MCD au MLD
L’entité qui possède la cardinalité maximale égale à 1 recevra l’identifiant ou les identifiants des entités ayant les cardinalités maximales les plus fortes.

Les relations ayant toutes leurs entités reliées avec des cardinalités maximales supérieures à 1 se transformeront en entité en absorbant les identifiants des entités jointes.

Toute relation porteuse de propriétés se transformera en entité et absorbera comme clé étrangère les identifiants des entités qui lui sont liées.

Toute relation réflexive se transformera en entité et absorbera comme clé étrangère l’identifiant de l’entité qui lui est liée.

##### Petit exercice pratique :

A partir du MCD suivant construisez le MLD :

![Alt text](image-27.png)

Voici le MLD :

![Alt text](image-28.png)

### Modele physique des donnees (MPD)

Voici le schema relationnel correspondant au MLD precedent :

Diplômes (Diplomes)

Possède (#NumEmployé, #Diplôme, Date d’obtention)

Employés (NumEmployé, Nom, Prénom, Adresse, Code Postal, Ville, Téléphone)

Tables (NumTable, Capacité)

Date (Date)

Service (TypeService, Désignation)

Boissons Diverses (NumBoissons, Désignation, Prix de vente)

Contenir (#NumCommande, #NumBoissons, Quantité)

Commande (NumCommande, #Numemployé, #Date, #TypeService, #NumTable)

Comprend (#NumMenu, #NumCommande, Quantité)

Menus (NumMenu, Libellé, Prix de vente)

Constitué (#NumMenu, #NumPlat)

Constituer (#NumCommande, #NumPlat, Quantité)

Sélectionner (#NumCommande, #NumVin, Quantité)

Carte des vins (NumVin, Nom du vin, Millesime, Prix de vente)

Carte des plats (NumPlat, LibelléPlat, Prix de vente, #NumType)

Type des plats (NumType, Désignation)

Bouteilles (NumBouteille, Date Achat, Prix d’achat, # NumVin, #NumViticulteur)

Viticulteur (NumViticulteur, Nom viticulteur, Prénom viticulteur, Adresse viticulteur, Code postal, Ville, Téléphone)

A partir d'ici il est facile de generer le script SQL correspondant.

```SQL
CREATE TABLE CARTE_DES_VINS
   (
   NUMVIN INTEGER(2) NOT NULL ,
   NOM_DU_VIN CHAR(40)   ,
   MILLESIME INTEGER(2)  ,
   PRIX_DE_VENTE REAL(5,2)
,
    PRIMARY KEY (NUMVIN) CONSTRAINT PK_CARTE_DES_VINS
   );

CREATE TABLE BOUTEILLES
   (
   NUMVITICULTEUR INTEGER(2) NOT NULL ,
   NUMVIN INTEGER(2) NOT NULL ,
   NUMBOUTEILLE INTEGER(2) NOT NULL ,
   DATE_ACHAT DATE(8) ,
   PRIX_D_ACHAT REAL(5,2)
,
    PRIMARY KEY (NUMVITICULTEUR, NUMVIN, NUMBOUTEILLE) CONSTRAINT
PK_BOUTEILLES
   );


CREATE TABLE VITICULTEUR
   (
   NUMVITICULTEUR INTEGER(2) NOT NULL ,
   NOM_VITICULTEUR CHAR(20) ,
   PRÉNOM_VITICULTEUR CHAR(20) ,
   ADRESSE_VITICULTEUR CHAR(40) ,
   CODE_POSTAL CHAR(5) ,
   VILLE CHAR(40) ,
   TÉLÉPHONE CHAR(15)
,
    PRIMARY KEY (NUMVITICULTEUR) CONSTRAINT PK_VITICULTEUR
   );
```

## Les formes normales (FN)

Ensemble de regles qui a pour but d'eviter les anomalies au sein des BDDR.
Pour appliquer les concepts des formes normales il est necessaire de connaitre les trois premieres formes normales.

### Forme normale 1 (1FN)

Une relation est en premiere forme normale si :

- tous les attributs sont atomiques
- les attributs ne ocntiennent pas de valeurs repetitives

Exemple:
Clients (NumCli, Nom, Prenom, Adresse, Telephone)

![Alt text](image-29.png)

![Alt text](image-30.png)

### Forme normale 2 (2FN)

Une relation est en deuxieme forme normale si :

- elle est en 1FN
- si tous les attributs qui ne sont ps des cles ne dependent pas d'une partie de la cle primaire

Exemple:

Commande(NumClient, CodeArticle, Date, QteCommande, Designation)

![Alt text](image-31.png)

![Alt text](image-32.png)

### Forme normale 3 (3FN)

Une relation est en troisieme forme normale si :

- Elle est en deuxieme forme normale
- Si toutes les dependances fonctionnelles sont directes

Les attributs non cle primaire ne dependent pas d'un attribut non cle primaire

Exemple:

Commande(NumCommande, #CodeClient, #RefArticle)

![Alt text](image-34.png)

### Les diagrammes des flux

Les diagrammes des flux permettent de modéliser les flux d'informations entre les acteurs du systeme d'information et les acteurs du systeme operant.

Quelques definitions:

- Domaine d'etude: le perimetre d'une activite au sein d'une entreprise, d'une activite specifique
- L'acteur: une personne, un service, une entreprise, un systeme informatique qui intervient dans le domaine d'etude au moyen d'un flux d'information
- les flux: les informations qui circulent entre les acteurs, represente par une fleche et porte un nom et peut etre numerote (par soucis de chronologie)

Representation graphique :

![Alt text](image-35.png)

Quelques regles a respecter :

- un flux ne peut pas etre bidirectionnel
- un flux ne doit pas etre reflexif
- on ne represente pas les flux entre les acteurs externes

## UML

UML: Unified Modeling Language (langage de modélisation unifié) est un langage de modelisation de données. UML a ete normalisé en 1997 par l'OMG (Object Management Group). Son but est de mettre en forme les concepts orientés objets au travers de diagramme.

UML propose 13 diagrammes dependants de facon hierarchique et se complétant.

1. Les diagrammes statiques : ils permettent de modéliser la structure d'un système

   - Diagramme de classe
   - Diagramme d'objets
   - Diagramme de composants
   - Diagramme de déploiement
   - Diagramme de paquetages
   - Diagramme de structure composite

2. Les diagrammes comportementaux:

- Diagramme des cas d'usage
- diagramme etats-transitions
- diagramme d'activité

3. Les diagrammes dynamiques:

- Diagramme de sequences
- Diagramme de communication
- Diagramme global d'interaction
- Diagramme de temps

### Analogie Merise / UML

1. Cas du MCD et du diagramme des classes

Le MCD et le diagramme de classes partagent beaucoup de points communs. Les différences majeures apparaissent dans le côté objet d’UML. Cependant, au niveau du processus d’analyse, le diagramme de classes se rapproche plus du modèle logique des données. Le langage UML pour représenter une base de données ne passe pas d’un état correspondant à un MCD à un MLD. Il faut donc à l’analyste une bonne approche ou vision de la base de données pour la représenter sans faille en langage UML. Le découpage MCD, MLD apporte plus de sécurité, à ce niveau-là, qu’UML.

![Alt text](image-36.png)

![Alt text](image-37.png)

Representation d'une relation

![Alt text](image-38.png)
