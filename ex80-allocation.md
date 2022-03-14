# Ex 1

La classe suivante est définie.

```cpp
class C1 {
   public:
    C1() { cout << "Constructor"; }
    ~C1() { cout << "Destructor"; }
};
``` 

Afin de pouvoir faire une allocation de la manière suivante `val = new C1();`.

Quel est le type de la variable `val` pour réaliser cette allocation ?


# Ex 2

Quel est l'affichage du programme suivant ?

```cpp
#include <iostream>

using namespace std;

class C1 {
   public:
    C1() { cout << "Constructor" << endl; }
    ~C1() { cout << "Destructor" << endl; }
};


int main(){
    C1* pc = new C1();
}
``` 


# Ex 3

Quel est le danger du code suivant ?

```cpp
#include <iostream>

using namespace std;

class C1 {
   public:
    C1() { cout << "Constructor" << endl; }
    ~C1() { cout << "Destructor" << endl; }
};

int main(){
    for(int i=0; i<1000; i++)
        C1* pc = new C1();
}
``` 


# Ex 4

Quel est l'affichage du programme suivant ?

```CPP
#include <iostream>

using namespace std;

class C1 {
   public:
    C1() { cout << "C1 Const" << endl; }
    ~C1() { cout << "C1 Dest" << endl; }
};

class C2 {
  public:
    C2() { cout << "C2 Const" << endl; }
    ~C2() { cout << "C2 Dest" << endl; }
    
    void add_c1(){
        tab[nb_c1++] = new C1();
    }
    
    C1* tab[5];
    int nb_c1 = 0;
};


int main(){
    C2 c2;
    
    c2.add_c1();
    c2.add_c1();
}
```

# Ex 5

Corriger l'exercice #4 pour que tous les objets soient détruits à la fin.


# Ex 6
Il faut créer une classe qui permet de gérer une liste de `double` de taille dynamique.

Créer une classe `Data` :

```CPP
struct Data{
    void init(int capacite){}
    void liberer(){}

    int capacite;
    double* tab;
};
```

`capacite`
: Un entier qui donne la capacité du tableau

`tab`
: Le tableau de `double` alloué dynamiquement.

`init(int cap)`
: Permet de faire l'allocation de la mémoire pour le tableau `tab`, la taille du tableau est passée en paramètre.

`liberer()`
: Libère la mémoire allouée pour le tableau.

L'utilisation de cette classe se fera de la manière suivante :

```CPP
void main(){
    Data d;
    d.init(10);
    d.tab[0] = 12;
    cout << "La valeur de tab[0] " << d.tab[0] << endl;
    d.liberer();
}
```