---
categories:
  - Clean code
tags:
  - Jekyll
  - update
---

Dans cette série d'articles, nous allons aborder tout ce qui tourne autour du Clean Code (je vous conseil le livre portant le même nom)

## Qu'est-ce que le clean code ?

C'est une ensemble de principes, règles à respecter qui font que le code est facilement lisable, maintenable. Cela rejoint les principes SOLID.

Par exemple on va éviter autant que se peut le code dupliqué, ajouter de l'abstraction dès que possible...

Il vaut mieux prendre du temps à faire du clean code dés le début afin d'en gagner plus tard lors la lecture ou la modification de celui-ci.

#### Noms explicites

Qui n'est jamais tombé sur une variable de ce style

```c#
int a; //age
```

Alors que cela pourrait être lisible en la renommant ainsi

```c#
int age;
```

Les noms des méthodes, class, variables doivent indiquer

* ce qu'elles font
* pourquoi elles existent
* comment elles sont utilisées

Sauf règle métier bien précise, si on a besoin d'ajouter un commentaire, un renommage s'impose peut-être alors !

Il faut éviter d'induire en erreur le lecteur :

```c#
var studentList = GetStudents();
```
Le nom de la variable peut porter à confusion : est-ce une _**liste d'étudiants**_ ou bien l'objet _**List**_ ? 

On pourrait l'écrire plutot _**studentGroup**_ ou encore mieux _**students**_

Il ne sert à rien non plus de mettre le contenant ou le type dans le nom d'une variable : ageVariable, nameString, ageNumber...

#### Une règle simple

Si vous vous demandez si votre méthode ou votre variable ont des noms assez explicites, essayer de les prononcer à l'oral lors d'une discussion avec un autre développeur.

En effet, il est plus facile de dire _Ma variable age est toujours à 0_ que _Ma variable a est à 0_

On encore _qsdqsd est null, je ne comprends pas_, cela devient compliqué pour l'autre personne de saisir le contexte !


#### Nom des méthodes

Il est toujours bon d'ajouter dans le nom d'une méthode, un préfixe indiquant une action comme _**GetStudents**_(), _**DeleteMovie()**_ afin d'avoir une idée de ce qu'elle fait sans aller dans son implémentation.

On peut aussi remplacer l'instanciation d'une variable avec une méthode static au lieu de son constructeur permettant de décrire les argument, ainsi

```c#
Card card = Card.InactiveByDefault(true);
```

est mieux que 

```c#
Card card = new Card(true);
```





