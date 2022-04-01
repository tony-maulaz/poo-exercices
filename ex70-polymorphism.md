# Ex 1

- Créer une classe `Animal` qui contient une méthode `speak`.
- Créer une classe `Dog` qui affiche `Wouf` sur la console lorsque la méthode  
  `speak` est appelée.

Le code suivant doit fonctionner.

```cpp
#include <iostream>
using namespace std;

int main()
{
    cout << "The dog is here" << endl;
    Animal* a = new Dog();
    a->speak();
}
```

# Ex 2

Créer la classe manquante afin de rendre le code exécutable.

```CPP
#include <iostream>
using namespace std;

// ???

struct Circle : public Shape{
    void draw() override{
        cout << "Drawing a circle" << endl;
    }
};

struct Square : public Shape{
    void draw() override{
        cout << "Drawing a square" << endl;
    }
};

int main()
{
    Shape* s = new Circle();
    s->draw();
    s = new Square();
    s->draw();
}
```

# Ex 3

Quelle est la différence entre une méthode virtuelle et une méthode virtuelle pure ?

# Ex 4

- Quel est le problème du code suivant ?
- Modifier le `main` afin de rendre le code exécutable ?

```CPP	
#include <iostream>
using namespace std;

class Human{
    public:
        virtual void speak() = 0;
};

struct Child : public Human{
    void speak() override{
        cout << "Hello" << endl;
    }
};

int main()
{
    Human* h = new Human();
    h->speak();
}
```

# Ex 5

Reprendre l'exercice `Person` et modifier la classe `School` pour avoir un tableau de `Person*`.  
Ajouter une méthode `printInfos` dans la classe `Person`.  
La méthode `printList` de la classe `School` doit afficher la liste des personnes, et appeler la méthode `printInfos` de chaque personne.  
Il est impossible de créer une personne.  
