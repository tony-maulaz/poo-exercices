# Exception
## Ex 0
Quel est l'affichage des programmes suivant ?

### 0.1

```CPP
#include <iostream>

using namespace std;

double calc(int a, int b)
{   
    try{

        if( b == 0)
            throw 1;
        else
            return a/b;

    }
    catch(int& val){
        cout << val << endl;
        return 0;
    }
}

int main(){

    int a = 5;
    int b = 0;

    calc(a,b);    
}
```

### 0.2
```CPP
void porcess(){
    try{
        cout << "1";
        throw 9;
        cout << "2";
    }
    catch(...){
        cout << "3";
        throw 'b';
        cout << "5";
    }

    cout << "7";
}

int main(){

    try{
        porcess();
    }
    catch(char c){
        cout << "6" << c;
    }
    catch(...){
        cout << "0";
    }
    
    cout << "4";
}
```

### 0.3
```CPP
void calc(int val){

    if( val == 1 )
        throw 1;

    else if( val == 2 )
        throw 2;

    else if( val == 3 )
        throw 'a';

    else if( val == 4 )
        throw "BOOM";

    else
        cout  << "5";

}

void porcess(int val){
    try{
        calc(val);
        cout << "9";
    }
    catch(double e){
        cout << "8";
    }
    catch(int e){
        cout << e;
    }

    cout << "7";
}

int main(){

    try{
        cout << 'a' << endl;
        porcess(0);
        cout << endl << 'b' << endl;
        porcess(1);
        cout << endl << 'c' << endl;
        porcess(2);
        cout << endl << 'd' << endl;
        porcess(3);
        cout << endl << 'e' << endl;
        porcess(4);
        cout << endl << 'f' << endl;
        porcess(5);
    }
    catch(...){
        cout << "0";
    }
}
```

### 0.4
```CPP
void calc(){

    try{
        throw 1;
    }
    catch(int v){
        cout << "1";
        throw 2;
        cout << "4";
    }
}

void porcess(int val){
    try{
        calc();
        cout << "9";
    }
    catch(double e){
        cout << "8";
    }
    catch(int e){
        cout << e;
    }

    cout << "7";
}

int main(){

    try{
        cout << 'a' << endl;
        porcess(0);
        cout << endl << 'b' << endl;
        calc();
    }
    catch(...){
        cout << "0";
    }
}
```

## Ex 1
Faire un programme qui lève une exception de type `int`.

Ce programme doit ensuite faire un `catch` de cette exception et afficher un message avec le nombre qui a provoqué l'erreur.

Exemple avec le nombre `12`

```console
Il y a eu une excéption avec le nombre 12
```


## Ex 2
L'exemple de code ci-dessous est une saisie d'un nombre entier

Modifier le code pour qu'il lève une exception si il y a une division par `0`

Vous pouvez lever une exception du type `overflow_error("votre message");`

Pour récupérer cette exception, il faut faire un `catch` sur `std::exception& e`

Vous devez placer le code suivant dans le `catch`
```CPP
    cout << "\033[1;31mIl y a eu une erreur\033[0m" << endl;
    cout << e.what() << endl;
```

```C
    int x = 0;
    cout << "Entrer la valeur de x pour le calcul 12 / x = " << endl;
    cin >> x;
    if (!cin) // test si erreur d'entrée
    {
        cout << "ERREUR d'entrée" << endl;
        cin.clear ();  // efface le bit d'erreur
        cin.ignore(numeric_limits<streamsize>::max(), '\n'); // vide le buffer
    }
    else
    {
        cout << "Le résultat est : " << 12/x << endl;
    }
```

## Ex 3

Quel est l'affichage du code suivant 

```CPP
struct Foo
{
    Foo(string name) : name(name)
    {
        cout << "Foo : " << name << " est construit" << endl;
    }
    
    ~Foo()
    {
        cout << "Foo : " << name << " détruit" << endl;
    }
    string name;
};

void func2() {
    throw "BOOM";
}

void func1(Foo& f) {
    try
    {
        func2();
    }
    catch(char const* s)
    {
        cout << "Erreur func1 : " << s << endl;
    }
    
}

int main()
{
    try
    {
        Foo f1("f1");
        func1(f1);
    }
    catch (char const* m)
    {
        cout << "Erreur func1 : " << m << endl;
    }
}
```

## Ex 4
On reprend la même classe `Foo` et la même fonction `func2` que dans l'ex 3

Quel est l'affichage de ce programme

```CPP
struct Foo
{
    Foo(string name) : name(name)
    {
        cout << "Foo : " << name << " est construit" << endl;
    }
    
    ~Foo()
    {
        cout << "Foo : " << name << " détruit" << endl;
    }
    string name;
};

void func2() {
    throw "BOOM";
}

void func3(Foo& f) {
    try
    {
        func2();
    }
    catch(char const* s)
    {
        cout << "Erreur func3 : " << s << endl;
        throw;
    }
}

int main(){
    try
    {
        Foo f1("f1");
        func3(f1);
    }
    catch (char const* m)
    {
        cout << "Erreur ex4 : " << m << endl;
    }
}
```

## Ex 5
On garde la classe `Foo` des exercices précédant.

Quel est l'affichage du programme ?

```CPP
void func5(){
    Foo f4("f4");
    throw "BOOM";
    Foo f5("f5");
}

void ex5(){
    Foo f1("f1");
    Foo* f3 = new Foo("f3");

    try
    {
        Foo* f2 = new Foo("f2");
        func5();
        delete f2;
    }
    catch(char const* m)
    {
        cout << "Problème : " << m << endl;   
    }
}
```

## Ex 6

Quels objets n'ont pas été détruit dans l'exercice 5 ?

## Ex 7

Idem que l'ex `5` mais on ajoute une classe

Quel est l'affichage du programme suivant

```CPP
struct DynamicFoo
{
    DynamicFoo(string name)
    {
        p = new Foo(name);
    }

    ~DynamicFoo()
    {
        delete p;
    }

    Foo* p;
};

int main()
{
    Foo f1("f1");
    DynamicFoo f3("f3");

    try
    {
        DynamicFoo f2("f2");
        func5();
    }
    catch(char const* m)
    {
        cout << "Problème : " << m << endl;   
    }
}
```

## Solutions

### Ex 1

### Ex 2
```CPP
void ex2(){
    int x = 123;
    try
    {
        cout << "Entrer la valeur de x pour le calcul 12 / x = " << endl;
        cin >> x;
        if (!cin) // test si erreur d'entrée
        {
            cout << "ERREUR d'entrée" << endl;
            cin.clear ();  // efface le bit d'erreur
            cin.ignore(numeric_limits<streamsize>::max(), '\n'); // vide le buffer
        }
        else{
            if( x == 0 )
                throw overflow_error("Division par 0");
            cout << "Le résultat est : " << 12/x << endl;
        }
    }
    catch(std::exception& e)
    {
        cout << "\033[1;31mIl y a eu une erreur\033[0m" << endl;
        std::cerr << e.what() << endl;
    }
}
```

## Ex 3
```console
Foo : f1 est construit
Erreur func1 : BOOM
Foo : f1 détruit
```

## Ex 4
```console
Foo : f1 est construit
Erreur func3 : BOOM
Foo : f1 détruit
Erreur ex4 : BOOM
```

## Ex 5
```console
Foo : f1 est construit
Foo : f3 est construit
Foo : f2 est construit
Foo : f4 est construit
Foo : f4 détruit
Problème : BOOM
Foo : f1 détruit
```

## Ex 7
```console
Foo : f1 est construit
Foo : f3 est construit
Foo : f2 est construit
Foo : f4 est construit
Foo : f4 détruit
Foo : f2 détruit
Problème : BOOM
Foo : f3 détruit
Foo : f1 détruit
```