## Ex 1 - Accessibilité

Mettez toutes les lignes qui ont une erreur d'accessibilité en commentaire pour
que le code compile.

```cpp
#include <iostream>

using namespace std;

class C1 {
  public:
    int pub_c1;
    
    void meth_pub_c1(){
        priv_c1 = 9;
    }
    
  protected:
    int prot_c1;
    
    void meth_prot_c1(){
        priv_c1 = 4;
    }
    
  private:
    int priv_c1;
    
    void meth_priv_c1(){
        priv_c1 = 12;
    }
};

class C2 : public C1 {
  public:
    
    void meth_pub_c2(){
        meth_priv_c1();
        prot_c1 = 8;
        priv_c2 = 1;
    }
    
    int pub_c2;
    
  protected:
    int prot_c2;
    
    void meth_prot_c2(){
        priv_c2 = 2;
        meth_prot_c1();
    }
    
  private:
    int priv_c2;
};

int main() {
    C1 c1;
    C2 c2;
    
    c1.pub_c1 = 2;
    c2.prot_c2 = 1;
}
```

## Ex 2

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
}
```

## Ex 3

Modifier le constructeur `Enfant` pour rendre le code compilable.

```CPP
#include <iostream>

using namespace std;

class Parent {
  public:
    Parent(int val){}
};

class Enfant : public Parent {
  public:
    Enfant() {}
};

int main() {
    Enfant e;
}
```


## Ex 4

Quel est l'affichage du programme suivant ?

```CPP
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

## Ex 5

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

## Ex 6 - Classe 
Écrire deux classes `Shape` et `Square`.
- la classe `Shape` a un attribut entier `nbr_side` qui doit être initialisé lors de la construction.
- l'attribut `nbr_side` doit être en lecture seule.
- la classe `Square` hérite de `Shape`.
- la classe `Shape` n'a pas de constructeur par défaut.
- lors de la création de la classe `Square`, le nombre de côtés est initialisé à `4`.

Modifier le `main` ci-dessous afin d'afficher le nombre de côtés de la forme.

```CPP
int main(){
    Square s;
    cout << "Number of sides : " << "???" << endl;
}
```

## Ex XX

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
