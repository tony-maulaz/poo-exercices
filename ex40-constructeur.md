## Ex 1

Quel est l'affichage du programme suivant :

```cpp
class C1 {
   public:
    C1() { cout << "C1 est construit" << endl; }
    ~C1() { cout << "C1 est détruit" << endl; }
};

class C2 {
   public:
    C2() { cout << "C2 est construit" << endl; }
    C2(int a) { cout << "C2 avec param : " << a << endl; }
    ~C2() { cout << "C2 est détruit" << endl; }

    C1 c1[3];
};

void main(){
    C2 c(3);
}
```

## Ex 2

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

## Ex 3
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


# Ex 4

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
    Test t(2.34, 12,8);
    t.plot();
}
```

## Ex 5

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
