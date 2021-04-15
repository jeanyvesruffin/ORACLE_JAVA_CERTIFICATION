# ORACLE_JAVA_CERTIFICATION

# Introduction Part 1

JAVA SE est la base suivie de :
Java EE : le plus (haut niveau) complet pour les entreprises
JAVA MP = Micro profil (ex micro service)
JAVA ME = electronic device
JAVA CARD = exemple carte de crédit
Les fichier avec l'extension .java contiennent le *Code source*.
Pour compiler du code java cad file.java faire la commande

```cmd
javac
```

Le fichier .java génèrera le fichier .class
Les fichiers avec l'extension .class contiennent le *Code source compilé* dis binary code

# Introduction Part 2

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

# Introduction Part 3