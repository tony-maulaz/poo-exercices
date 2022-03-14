## Ex 1

Quel est l'affichage du programme suivant ?

```CPP
#include <iostream>

using namespace std;

struct Parent{
    void execute(){ cout << "From parent" << endl; }
};

struct Child : public Parent{
  void execute(){ cout << "From child" << endl; }
};

void func(Parent* p){
    p->execute();
}

int main(){
    Child child;
    child.execute();
    
    Parent* p = &child;
    p->execute();
    
    func(&child);
}
```

## Ex 2

Est-ce que le code suivant est exécutable ?

```CPP
struct Parent{
    void execute(){ cout << "From parent" << endl; }
};

struct Child : public Parent{
  void execute(){ cout << "From child" << endl; }
  
  int val;
};

int main(){
    Child child;
    Parent* p = &child;
    
    p->val = 12;
}
```

## Ex 3

Quels sont les attributs accessibles de l'objet `p` dans la fonction `func` ?

```CPP
#include <iostream>

using namespace std;

class Parent{
  public:
    int val1;

  protected:
    int val2;
};

struct Child : public Parent{

  int val3;
};

void func(Parent& p){
    //p.???
    // val1 ?
    // val2 ?
    // val3 ?
}

int main(){
    Child child;
    func(child);
}
```