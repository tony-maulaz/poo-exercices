# Cast

## Ex 1
Quel est l'affichage du programme suivant ?

```cpp
#include <iostream>

using namespace std;

struct ClassA {
    virtual void show(){ cout << "Hello" << endl; }
};

struct ClassB : public ClassA {
    void show(){ cout << "Bonjour" << endl; }
    void test(){ cout << "Test" << endl; }
};

void print(ClassA* c){

    c->show();
    
    ClassB* pt = dynamic_cast<ClassB*>(c);
    if( pt != nullptr ){
        pt->test();
    }
}

int main()
{
    ClassB cb;
    print(&cb);
    
    return 0;
}
```


## Ex 2
Modifier la boucle `for`afin d'obtenir l'affichage suivant :
```
A
A
B
A
C
```

```CPP
#include <iostream>

using namespace std;

struct ClassA {
    virtual void testA(){ cout << "A" << endl; }
};

struct ClassB : public ClassA {
    void testB(){ cout << "B" << endl; }
};

struct ClassC : public ClassA {
    void testC(){ cout << "C" << endl; }
};


void print(ClassA* tab[], int size){

    for(int i=0; i<size; i++){

    }
}

int main()
{
    ClassA* tab[3];
    tab[0] = new ClassA();
    tab[1] = new ClassB();
    tab[2] = new ClassC();
    
    print(tab, 3);
    
    return 0;
}
```


# Solution
## Ex 2
```CPP
void print(ClassA* tab[], int size){

    for(int i=0; i<size; i++){
        tab[i]->testA();
        
        ClassB* cb = dynamic_cast<ClassB*>(tab[i]);
        if( cb != nullptr ){
            cb->testB();
        }
        
        ClassC* cc = dynamic_cast<ClassC*>(tab[i]);
        if( cc != nullptr ){
            cc->testC();
        }
    }
}
```