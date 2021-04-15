# Héritage avancé

## Ex 1

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

void ex1()
{
    A* a = new B();
    delete a;
}
```

## Ex 2

Quel est l'affichage du programme suivant :

```CPP
struct Parent
{
    Parent() { cout << "Constr parent" << endl; }
    virtual ~Parent() { cout << "Destr parent" << endl; }
};

struct Enfant: public Parent
{
    Enfant() { cout << "Constr enfant" << endl; }
    ~Enfant() { cout << "Destr enfant" << endl; }
};

void ex2(){
    Parent* p = new Enfant();
    delete p;
}
```

## Ex 3

Quel est l'affichage du programme suivant 

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

struct C: public A
{
    C() { cout << "Constr C" << endl; }
    ~C() { cout << "Destr C" << endl; }
};

struct D: public B, public C {
};

void ex(){
    D d;
}
```

## Ex 4

Quel est l'affichage du programme

```CPP
struct A
{
    A() { cout << "Constr A" << endl; }
    A(int a) { cout << "Constr A, val : " << a << endl; }
    ~A() { cout << "Destr A" << endl; }
};

struct B: public A
{
    B(): A(4) { cout << "Constr B" << endl; }
    ~B() { cout << "Destr B" << endl; }
};

struct C: public A
{
    C() { cout << "Constr C" << endl; }
    ~C() { cout << "Destr C" << endl; }
};

struct D: public B, public C {
};

void ex(){
    D d;
}
```

## Ex 5

Quel est l'affichage du programme

```CPP
struct A
{
    A() { cout << "Constr A" << endl; }
    A(int a) { cout << "Constr A, val : " << a << endl; }
    ~A() { cout << "Destr A" << endl; }
};

struct B: public virtual A
{
    B(): A(4) { cout << "Constr B" << endl; }
    ~B() { cout << "Destr B" << endl; }
};

struct C: public virtual A
{
    C() { cout << "Constr C" << endl; }
    ~C() { cout << "Destr C" << endl; }
};

struct D: public B, public C {
};


void ex(){
    D d;
}
```

## Ex 6

Quel est l'affichage du programme ?

*Le constructeur de `B` est modifié par rapport à l'exercice précédant*

```CPP
struct A
{
    A() { cout << "Constr A" << endl; }
    A(int a) { cout << "Constr A, val : " << a << endl; }
    ~A() { cout << "Destr A" << endl; }
};

struct B: public virtual A
{
    B(): A(4) { cout << "Constr B" << endl; }
    ~B() { cout << "Destr B" << endl; }
};

struct C: public virtual A
{
    C() { cout << "Constr C" << endl; }
    ~C() { cout << "Destr C" << endl; }
};

struct D: public B, public C {
};

void ex(){
    D d;
}
```

## Ex 6

Quel est l'affichage du programme ?

```CPP
struct A
{
    A() { cout << "Constr A" << endl; }
    A(int a) { cout << "Constr A, val : " << a << endl; }
    ~A() { cout << "Destr A" << endl; }
};

struct B: public virtual A
{
    B(): A(4) { cout << "Constr B" << endl; }
    ~B() { cout << "Destr B" << endl; }
};

struct C: public virtual A
{
    C() { cout << "Constr C" << endl; }
    ~C() { cout << "Destr C" << endl; }
};

struct D: public B, public C {
    D() : A(5) {}
};

void ex(){
    D d;
}
```

## Ex 7

Quel est l'affichage du programme suivant

```CPP
struct Parent
{
    virtual void test() = 0;
};

struct Enfant: public Parent
{
    void test() { cout << "Enfant test" << endl; }
};

struct PetitEnfant : public Enfant
{
    void test() { cout << "Petit enfant test" << endl; }
};

void ex(){
    Parent* p = new Enfant();
    p->test();

    Parent* p1 = new PetitEnfant();
    p1->test();

    Enfant* e = new PetitEnfant();
    e->test();

    Enfant e1 = PetitEnfant();
    e1.test();
}
```

## Solutions

### Ex 1
```console
Constr A
Constr B
Destr A
```

### Ex 2
```console
Constr parent
Constr enfant
Destr enfant
Destr parent
```

### Ex 3
```console
Constr A
Constr B
Constr A
Constr C
Destr C
Destr A
Destr B
Destr A
```

### Ex 4
```console
Constr A, val : 4
Constr B
Constr A
Constr C
Destr C
Destr A
Destr B
Destr A
```

### Ex 5
```console
Constr A
Constr B
Constr C
Destr C
Destr B
Destr A
```

## Ex 6
```console
Constr A, val : 5
Constr B
Constr C
Destr C
Destr B
Destr A
```

## Ex 7
```console
Enfant test
Petit enfant test
Petit enfant test
Enfant test
```