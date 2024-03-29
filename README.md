- [Introduction](#introduction)
  * [Introduction Part 1](#introduction-part-1)
  * [Introduction Part 2](#introduction-part-2)
    + [Java est sensible à la casse](#java-est-sensible---la-casse)
  * [Introduction Part 3](#introduction-part-3)
    + [Règles de syntaxes](#r-gles-de-syntaxes)
    + [Définition d’une classe](#d-finition-d-une-classe)
    + [Accéder aux classes à travers les packages](#acc-der-aux-classes---travers-les-packages)
    + [Création de la classe applicative Main](#cr-ation-de-la-classe-applicative-main)
    + [Compilation du programme java](#compilation-du-programme-java)
    + [Execution du programme java](#execution-du-programme-java)
    + [Les commentaires et la java documentatiaon](#les-commentaires-et-la-java-documentatiaon)
  * [TP 1 Verification de l'installation de son JDK](#tp-1-verification-de-l-installation-de-son-jdk)
  * [TP 1 Creation, compilation et execution d'une application JAVA](#tp-1-creation--compilation-et-execution-d-une-application-java)
- [Types primitifs, opérateurs et instructions de contrôle de flux](#types-primitifs--op-rateurs-et-instructions-de-contr-le-de-flux)
  * [Primitive](#primitive)
  * [Declaration et initialisation d'une variable](#declaration-et-initialisation-d-une-variable)
  * [Liste des opérteurs](#liste-des-op-rteurs)
  * [Operations arithmétique et type casting](#operations-arithm-tique-et-type-casting)
  * [Opérations sur les binaires](#op-rations-sur-les-binaires)
  * [Relations (egale, superieur ...)](#relations--egale--superieur--)
  * [Controle du flux avec **if/elseif/else**](#controle-du-flux-avec---if-elseif-else--)
  * [Operation ternaire](#operation-ternaire)
  * [Controle du flux avec **switch case**](#controle-du-flux-avec---switch-case--)
  * [Tester une variable ou un calcule simplement avec **JShell**](#tester-une-variable-ou-un-calcule-simplement-avec---jshell--)


<h1>ORACLE_JAVA_CERTIFICATION</h1>

Documentation cours de certification

https://learning.oracle.com/player/play?in_sessionid=500188244353JJ19&classroom_id=113880473

Documentation java11

https://docs.oracle.com/en/java/javase/11/

# Introduction 

## Introduction Part 1

JAVA SE est la base suivie de :

Java EE : le plus (haut niveau) complet pour les entreprises

JAVA MP = Micro profil (ex micro service)

JAVA ME = electronic device

JAVA CARD = exemple carte de crédit

Les fichiers avec l'extension .java contiennent le **Code source**.

Pour compiler du code java cad file.java faire la commande

```cmd
javac
```

Le fichier .java génèrera le fichier .class

Les fichiers avec l'extension .class contiennent le **Code source compilé** dis binary code

## Introduction Part 2

On crée des classes, dans lesquelles se trouvent les déclarations de variables, des opérations, algorithme, méthodes ...
Toutes les actions que peuvent réaliser une classe.

Un objet est une instance spécifique de classe. Chaque objet pourra avoir exactement la structure des attributs et des
comportements définis par la classe.

Exemple:

```java
class Person {
    void play() {
        Dog dog = new Dog();
        Dog.name = "Rex";
        Ball ball = new Ball();
        Dog.fetch(ball);
    }
}

class Dog {
    String name;

    Fetch(Ball ball) {
        Ball.find();
        Ball.chew();
    }
}
```

**L’héritage** permet à une class spécifiques d’hériter d’attributs et méthode décrite dans la classe mère. Les types
parents sont appelées **superclass**. Les sous-types sont appelés des **sous-classes**. L’idée est de faire du code
réutilisable par un ensemble de classe.

Exemple :

```java
class Animal extends OrganismeVivant {
    // generic attributes et comportements
}

class Dog extends Animal {
    //spécifique attributes et comportements
}


```

Un grand nombre de classes sont déjà utilisées par JDK. Exemples :

* Types de datas basics : **String, LocalDateTime, BigDecimal**.
* Pour manipuler des collections : **Enumeration, ArrayList, HashMap**.
* Pour gérer un comportement générique et effectuer des actions système : **System, Object, Class**.
* Pour exécuter des opérations sur les input et output : **FileInputStream, FileOutputStream**.
* Beaucoup d’autres API (Application Programming Interface) sont utilisées pour : accès base de données, gérer la
  concurrence, activer les communications réseau, exécuter des scripts, gestions des transactions, sécurité, connexion,
  construction d’interface graphique.

Documentations API JAVA :

https://docs.oracle.com/en/java/javase/16/docs/api/index.html

### Les mots clés JAVA, réserves.

![Mot reservé](./Resources/img_reserve.bmp)

### Java est sensible à la casse

![Case Sensitive](./Resources/img_case.bmp)

## Introduction Part 3

### Règles de syntaxes

Toutes les instructions java doivent être terminées par le symbole ‘ ; ’.

Les blocs de code doivent être entourés de symboles { }.

L’indentation et les espaces n’ont aucun impact sur la compilation mais est nécessaire pour une bonne visibilité de
lecture de code.

Exemple:

```java
package com.oracle.demos.animals;

class Dog {
    void fetch() {
        while (ball == null) {
            keepLooking();
        }
    }

    void makeNoise() {
        if (ball != null) {
            dropBall();
        } else {
            bark();
        }
    }
}
```

### Définition d’une classe

Le nom de la classe est généralement représenté par un ou plusieurs noms. Exemples : Dog, SabreLaser, Person …

La classe doit être enregistrée dans un fichier portant le même nom que la classe et l'extension .java.

Les classes sont regroupées par packages.

Les packages sont représentés sous forme de dossiers dans lesquels les fichiers de classe sont enregistrés.

Le nom du package est généralement l'inverse du nom de domaine de votre entreprise, plus un système de dénomination
adopté au sein de votre entreprise. Exemple : com.oracle.demos ou org.acme.something

Les packages et le nom de la classe doivent former une combinaison unique.

Si le nom du package est absent la class sera mis dans un package par default. Attention cela n’est pas recommandé.

Exemple:

```java
package com.oracle.demos.animals;

class Dog {

}
```

La classe et package représentés ci-dessus devra être sauvegardé dans le dossier :**
/somepath/com/oracle/demos/animals/Dog.java**

### Accéder aux classes à travers les packages

![Case Sensitive](./Resources/img_packager.PNG)

Les imports sont ignorés du compilateur.

### Utilisation de modificateur d’accès

* Public : Visible par toutes les autres class.
* Protected : Visible par les classes se trouvant dans le même package ou sous package.
* <default> Visible seulement dans la classe d’un même package.
* Private : Visible uniquement à l’intérieur de ça class.

Exemple :

![Case Sensitive](./Resources/img_acces.PNG)

### Création de la classe applicative Main

La class Main est le point d’entrée de notre programme. La machine virtuel Java recherchera et exécutera cette méthode
en première.

Exemple :

![Case Sensitive](./Resources/img_main.PNG)

### Compilation du programme java

Compilez les classes avec le compilateur **javac** java.

Le paramètre **-classpath ou -cp** pointe vers les emplacements d'autres classes qui peuvent être nécessaires pour
compiler votre code. Le paramètre **-d** pointe vers un chemin pour stocker le résultat de la compilation. (Le
compilateur crée des sous-dossiers de package avec des fichiers de classe compilés dans ce chemin.). Le reste fournir le
chemin vers le code source.

Exemple pour compiler le ficher ci dessous:

```java
package demos;

public class Whatever {
    public static void main(String[] args) {
        // programm execution starts here
    }
}

```

La commande de compilation pour avoir le resultat dans le dossier /project/classes/demos/Whatever.class sera :

```cmd
javac -cp /project/classes -d /project/classes /project/sources/demos/Whatever.java
```

### Execution du programme java

Exécutez le programme à l'aide de la machine virtuelle Java exécutable Java (JVM).

Spécifiez **-classpath ou -cp** pour pointer vers les dossiers où se trouvent vos classes.

Spécifiez le nom de classe complet. **Utilisez le préfixe de package** n'utilisez pas l'extension .class. Fournissez
une **liste de paramètres** séparés par des espaces après le nom de la classe.

Acces aux paramètres de ligne de commande:

* Utilisez un objet tableau pour accéder aux paramètres.
* L'index du tableau commence à 0 (premier paramètre).

Depuis java 11, il est également possible de ré exécuter du code source à un seul fichier comme s'il s'agissait d'une
classe compilée. JVM interprétera votre code, mais aucun fichier de classe compilé ne sera créé.

Exemple compilation puis execution du programme ci-dessous

```java
package demos;

public class Whatever {
    public static void main(String[] args) {
        String param1 = args[1];
        System.out.println("Hello " + param1);
    }
}
```

```cmd
java -cp /project/classes demos.Whatever Jo John

// Resultat
Hello John
```

### Les commentaires et la java documentatiaon

Commentaire sur une ligne // Comment here

Commenter un bloc /* Comment here */

Creer de documentation pour java doc

```java
/**
 * The {@code Whatever} class
 * representataions d'un exemple de documentation
 * @version 1.0
 * @author ruffin
 */

```

Génération de la documentation HTML java doc

```cmd
javadoc -d <documentation path>
        -sourcepath <source code path>
        -subpackages <name of the root package>
```

## TP 1 Verification de l'installation de son JDK

```cmd
java -version

java version "11.0.10" 2021-01-19 LTS
Java(TM) SE Runtime Environment 18.9 (build 11.0.10+8-LTS-162)
Java HotSpot(TM) 64-Bit Server VM 18.9 (build 11.0.10+8-LTS-162, mixed mode)
```

Installation jdk java11 https://www.oracle.com/fr/java/technologies/javase-jdk11-downloads.html

## TP 1 Creation, compilation et execution d'une application JAVA

* Creation class

```java
package labs;

public class HelloWorld {
    public static void main(String[] args) {
        System.out.println("Hello " + args[0]);
    }
}
```

* Compilation

```bash
$ javac -d ./classes ./src/labs/HelloWorld.java
```

Cela aura pour effet de creer un dossier classes avec le code compiler /labs/HelloWorld.class.

* Consulter le contenu du dossier de compilation

```bash
$ ls -alR ./classes

./classes:
total 0
drwxr-xr-x 1 ruffi 197609 0 Apr 15 12:31 .
drwxr-xr-x 1 ruffi 197609 0 Apr 15 12:31 ..
drwxr-xr-x 1 ruffi 197609 0 Apr 15 12:31 labs

./classes/labs:
total 4
drwxr-xr-x 1 ruffi 197609   0 Apr 15 12:31 .
drwxr-xr-x 1 ruffi 197609   0 Apr 15 12:31 ..
-rw-r--r-- 1 ruffi 197609 872 Apr 15 12:31 HelloWorld.class


```

* Execution du programme

```bash
$ java -cp ./classes labs.HelloWorld "Niels Bohr"
Hello Niels Bohr
```

# Types primitifs, opérateurs et instructions de contrôle de flux

## Primitive

![primitive number](./Resources/img_primitive.PNG)

## Declaration et initialisation d'une variable

![Declaration de variables](./Resources/img_variables.PNG)

On ne peut "convertir" directement un type primitif vers un autre **uniquement** dans le cas ou d'une élévation exemple convertir un int en long fonctionne mais l'inverse non.

## Liste des opérteurs

![Opérateurs](./Resources/img_list_operators.PNG)
![Opérateurs_2](./Resources/img_operator2.PNG)

## Operations arithmétique et type casting

![Arithmetic](./Resources/img_arith.PNG)
![Arithmetic_2](./Resources/img_arith2.PNG)

## Opérations sur les binaires

![Binary](./Resources/img_binary.PNG)
![Binary](./Resources/img_binary_2.PNG)

## Relations (egale, superieur ...)

![Logic](./Resources/img_operator3.PNG)
![Logic](./Resources/img_operator4.PNG)

## Controle du flux avec **if/elseif/else**

![If/Else](./Resources/flow.PNG)

## Operation ternaire

![Ternaire](./Resources/ternaire.PNG)

##  Controle du flux avec **switch case**

![Switch](./Resources/switch.PNG)

##  Tester une variable ou un calcule simplement avec **JShell**

![Switch](./Resources/jshell.PNG)

# Text, Date, Time et objet numérique

## String et StringBuilder

String est immuable, cad , recreer un espace memoire avec un nouveau contenu a chaque modification du String.
StringBuilder et mutable, cad que nous modifions le contenu a une adresse memoire contenant le string.

![String](./Resources/img_string.PNG)
![String](./Resources/img_string2.PNG)
![String](./Resources/img_string3.PNG)
![String](./Resources/img_string4.PNG)

## Wrapper classes pour primitives

Le wrapper permet d'appliquer des capacités orientées objet aux primitive.

![Wrapper](./Resources/wrapper.png)
![Wrapper](./Resources/wrapper1.png)

## Enchainement de méthodes

![Chain](./Resources/chain.PNG)

## Date local et temps

![Date](./Resources/date.PNG)
![Date](./Resources/date2.PNG)
![Date](./Resources/instant.PNG)

## Zone Date et temps

![Zone](./Resources/zone.PNG)
![Zone](./Resources/zone2.PNG)

## Format

![Format](./Resources/format.PNG)
![Format](./Resources/format1.PNG)

## Ressource Bundle

![bundle](./Resources/bundle.PNG)
![bundle](./Resources/bundle1.PNG)
![bundle](./Resources/format_bundle.PNG)

## Classes et Objects

![UML](./Resources/uml.PNG)