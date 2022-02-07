# Ex 1

Écrire une fonction qui permet d'afficher le carré d'un `int` ou d'un `double`.


# Ex 2
Quel est l'affichage du programme suivant ?

```CPP
#include <iostream>
#include <iomanip>

using namespace std;

void func(int a){
    cout << "Val_2 : " << a << endl;
}

void func(double a){
    cout << "Val_3 : " << a << endl;
}

void func1(int a){
    cout << "Val_1 : " << a << endl;
    func( (double)a );
}

int main()
{
    double val_d = 2.0;
    int val_i = 5;
    
    func(val_d);
    
    func(val_i);
    
    func1(val_d);
    
    return 0;
}
```


# Solutions
## Ex 1
```CPP
#include <iostream>
#include <iomanip>

using namespace std;

void aff(int a){
    cout << "Res : " << a*a << endl;
}

void aff(double a){
    cout << "Res : " << a*a << endl;
}

int main()
{
    double val_d = 2.3;
    int val_i = 5;
    
    aff(val_d);
    aff(val_i);
    
    return 0;
}
```