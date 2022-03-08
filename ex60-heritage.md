## Ex 1

Quel est le comportement du programme ci-dessous ?

```cpp
#include <iostream>

using namespace std;

class C1 {
  public:
    
  protected:
    int val;
};

class C2 : public C1 {
  public:
    C2() { }
};

int main() {
    C2 c;
    c.val = 3;
}
```


## Ex 2

Quel est l'affichage du programme suivant ?

```C++
struct Parent{
    Parent(){
        cout << "Aff : A" << endl;
    }
    Parent(int a){
        cout << "Aff : B" << endl;
    }
};

struct Enfant : public Parent{
    Enfant(){
        cout << "Aff : C" << endl;
    }
    Enfant(int a){
        cout << "Aff : D" << endl;
    }
    Enfant(int a, int b) : Parent(a){
        cout << "Aff : E" << endl;
    }
    Enfant(double a) : Parent(a){
        cout << "Aff : F" << endl;
    }
};

int main(){
    cout << "Exercice 2" << endl;
    cout << "E1" << endl;
    Enfant e1;
    cout << "p1" << endl;
    Parent p1(12);
    cout << "E2" << endl;
    Enfant e2(1,2);
    cout << "E3" << endl;
    Enfant e3(5.3);
    cout << "E4" << endl;
    Enfant e4(2);
}
```


## Ex 3

Quel est l'affichage du code suivant ?

```CPP
struct A
{
    A() { cout << "Constr A" << endl; }
    ~A() { cout << "Destr A" << endl; }
};

struct B: public A
{
    B() { cout << "Constr B" << endl; }
    ~B() { cout << "Destr B" << endl; }
};

int main()
{
    cout << "Part 1" << endl;
    A a;
    cout << "Part 2" << endl;
    B b;
    cout << "Part 3" << endl;
    p* p = new B();
    delete p;
}
```

## Ex 4

Modifier les `???` pour que la méthode dans la classe enfant appel la méthode `print` de la classe parente.

```CPP
#include <stdio.h>
#include <iostream>

using namespace std;

struct Parent{
    void print(){ cout << "Parent" << endl; }
};

struct Enfant : public Parent{
    void print(){ 
        // ??? 
        cout << "Enfant" << endl; 
    }
};

int main()
{
    Enfant e;
    e.print();
    return 0;
}
```

L'affichage du code sera
```console
Parent
Enfant
```

## Ex 5

```CPP
#include <stdio.h>
#include <iostream>

using namespace std;

struct Parent{
    
    Parent(string m){
        text = m;
    }
    
    string text;
};

struct Enfant : public Parent{
    
    Enfant(){}
};

int main()
{
    Enfant e;
    e.print();
    return 0;
}
```

1. Pourquoi le code ci-dessus ne compile pas ?
1. Modifier le code pour le rendre exécutable.

## Ex XXX

Implémenter les classes `Vehicule` et `Voiture` de l'image suivante :

![alt text](images/heritage.png "UML")

Le nombre de roues est affecté pendant la construction des classes enfants.

Dans les méthodes, il faut afficher un texte.

Vous devez pouvoir exécuter le main suivant 

```CPP
int main()
{
    cout << "Exercice 2" << endl << endl;
    Voiture v;
    v.avancer();
    v.tourner();
}
```
