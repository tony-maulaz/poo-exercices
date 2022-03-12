## Ex 1.1

Quel est l'affichage du programme suivant :

```cpp
class C1 {
   public:
    C1() { cout << "1"; }
    ~C1() { cout << "2"; }
};

class C2 {
   public:
    C2() { cout << "3"; }
    ~C2() { cout << "4"; }
};

int main(){
    C2 c;
}
```

## Ex 1.2

Quel est l'affichage du programme suivant :

```cpp
class C1 {
   public:
    C1() { cout << "1"; }
    ~C1() { cout << "2"; }
};

class C2 {
   public:
    C2() { cout << "3"; }
    ~C2() { cout << "4"; }

    C1 varC1; // attribut
};

int main(){
    C2 c;
}
```

## Ex 1.3

Quel est l'affichage du programme suivant :

```cpp
class C1 {
   public:
    C1() { cout << "1"; }
    ~C1() { cout << "2"; }
};

class C2 {
   public:
    C2() { cout << "3"; }
    ~C2() { cout << "4"; }
};

int main(){
    C1 c1;
    C2 c2;
}
```

## Ex 1.4

Quel est l'affichage du programme suivant :

```cpp
class C1 {
   public:
    C1() { cout << "1"; }
    ~C1() { cout << "2"; }
};

class C2 {
   public:
    C2() { 
        cout << "3";
        C1 c1; 
        cout << "5";
    }
    ~C2() { cout << "4"; }
};

int main(){
    C2 c;
}
```

## Ex 1.5

Quel est l'affichage du programme suivant :

```cpp
class C1 {
   public:
    C1() { cout << "1"; }
    C1(int val) { cout << "5"; }

    ~C1() { cout << "2"; }
};

class C2 {
   public:
    C2() { 
        cout << "3";
        c1 = C1(1); 
    }
    ~C2() { cout << "4"; }

    C1 c1; // attribut
};

int main(){
    C2 c;
}
```

## Ex 1.6

- Quel est l'affichage du programme suivant ?
- Quelle est la différence avec l'exercice précédant ?

```cpp
class C1 {
   public:
    C1() { cout << "1"; }
    C1(int val) { cout << "5"; }

    ~C1() { cout << "2"; }
};

class C2 {
   public:
    C2() : c(1) { 
        cout << "3";
    }
    ~C2() { cout << "4"; }

    C1 c; // attribut
};

int main(){
    C2 c;
}
```

## Ex 1.7

- Quel est l'affichage du programme suivant ?

```cpp
class C1 {
   public:
    C1() { cout << "1"; }
    C1(int val) { cout << "5"; }

    ~C1() { cout << "2"; }
};

class C2 {
   public:
    C2() { 
        cout << "3";
    }
    ~C2() { cout << "4"; }

    C1* pc; // attribut
};

int main(){
    C2 c;
}
```

## Ex 1.8

- Quel est l'affichage du programme suivant ?

```cpp
class C1 {
   public:
    C1() { cout << "1"; }
    C1(int val) { cout << "5"; }

    ~C1() { cout << "2"; }
};

class C2 {
   public:
    C2() { 
        cout << "3";
    }
    ~C2() { cout << "4"; }

    C1 pc = C1(4); // attribut
};

int main(){
    C2 c;
}
```

## Ex 1.9

- Quel est l'affichage du programme suivant ?

```cpp
class C1 {
   public:
    C1() { cout << "1"; }
    C1(int val) { cout << "5"; }

    ~C1() { cout << "2"; }
};

class C2 {
   public:
    C2() { 
        cout << "3";
    }
    ~C2() { cout << "4"; }

    C1 pc[3]; // attribut
};

int main(){
    C2 c;
}
```


## Ex 2

Dans le code ci-dessous, quelles instructions compilent ?

```CPP
#include <stdio.h>
#include <iostream>

using namespace std;

class ClassA{
  public:
    ClassA(int val){ this->val = val;}
 
  private:    
    int val;
};

class ClassB{
  public:
    ClassA a;
};

int main()
{
    printf("Constructeur de classe");

    // 1) ClassA ca;
    // 2) ClassA ca(12);
    // 3) ClassB cb;

    return 0;
}
```

# Ex 3

Ajouter des constructeurs afin que le code dans le `main` fonctionne, il doit initialiser les deux valeurs
de mesures qui seront affichées par le programme.

```cpp
#include <iostream>

using namespace std;

class Measure{
    public:
        
        string toString(){
            return "val=" + to_string(value);
        }
        
    private:
        double value;
};

class Test{
    public:
    
        void plot(){
            cout << "m1 : " << m1.toString() << endl;
            cout << "m2 : " << m2.toString() << endl;
        }
    
    private:
        Measure m1;
        Measure m2;
};

int main()
{
    // les valeurs des mesures passées en paramètres
    Test t(2.34, 12,8);
    t.plot();
}
```

## Ex 4

Créer une classe `Voiture` qui possède un attribut `Marque` de type `String`

La `marque` est passée lors de la construction de l'objet et ne doit pas pouvoir être modifiée.

Il doit être possible de lire la marque.

Il ne doit pas être possible de créer une voiture sans marque.


## Ex 5

Créer une classe `Velo` qui possède un attribut `nbr_roue` de type `int`

Créer une classe `Garage` qui possède un attribut `Velo` de type `Velo`

Le nombre de roue du vélo sera passé en paramètre lors de la création du garage. 

Le constructeur pas défaut du vélo ne doit pas exister, car il doit être obligatoire
de donner le nombre de roue lors de la création d'un vélo.



## Ex XXX

Quel est l'affichage du programme suivant :

```CPP
class Point {
   public:
    Point() { cout << "Point construit" << endl; }

    Point(const Point& p) { 
        cout << "Point copié" << endl; 
        this->value = p.value; 
    }

    ~Point() { cout << "Point détruit" << endl; }

    int value;
};

int main()
{
    cout << "Ex 2 :" << endl;
    Point p1;
    p1.value = 5;
    cout << "Décl P2" << endl;
    Point p2;

    cout << "P2 = P1"  << endl;
    p2 = p1;

    cout << "P3 = p1" << endl;
    Point p3 = p1;
    cout << "P4(p1)" << endl;
    Point p4(p1);

    p4.value = 6;

    cout << "P1 val : " << p1.value << endl;
    cout << "P2 val : " << p2.value << endl;
    cout << "P3 val : " << p3.value << endl;
    cout << "P4 val : " << p4.value << endl;
}
```

## Ex XXX
Ajouter un constructeur et un destructeur dans la classe ci-dessous.

Le constructeur permet d'initialiser les cordonnées lors de la création.

Le destructeur permet d'afficher un message lorsque le point est détruit.

```cpp
#include <iostream>

using namespace std;

class Point{
    public:
    
        void plot(){
            cout << "x : " << x << " - y : " << y << endl;
        }
        
    private:
        int x;
        int y;
};

int main()
{
    cout<<"Exercice constructeur" << endl;

    Point* p1 = new Point();
    p1->plot();
    delete p1;
    cout << "fin de l'exercice";
}
```




# Ex XXX
Quel est l'affichage du programme suivant ?

```cpp
#include <iostream>
using namespace std;

struct Test{
    Test(){ cout << "Test is construct" << endl; }
};

int main()
{
    cout << "Test construction" << endl;
    cout << "Case 1" << endl;
    Test t[3];
    
    cout << "Case 2" << endl;
    Test* pt[3];
    
    cout << "Case 3" << endl;
    pt[0] = new Test();
}
```