# Surcharge

## Ex 1

A partir de la classe suivante 

```CPP
class List{
  public:
    
  private:
    int nbr = 0;
    int tab[20] = {0};
};
```

Ajouter des surcharges d'opérateurs afin de pouvoir exécuter le code suivant

```CPP
    List l;
    
    l += 5;
    l += 2;
    l += 9;

    for( int i=0; i<l.getNumberElement(); i++){
        cout << "El : " << l[i] << endl;
    }
```

Description des opérations

`+=`
: Ajoute un élément dans la liste

`[]`
: Permet d'accéder à un élément de la liste en fonction de son index


## Ex 2 - Copie

Analyser le code suivant et que ce passe-t-il lors de la copie de la classe tableau ?


```CPP
struct Shape
{
    Shape(int size) : size(size) {}
    virtual void print() = 0;
    int size;
};

struct Square : public Shape
{
    Square(int size) : Shape(size) {}
    void print()
    {
        cout << "je suis un carré de : " << size << endl;
    }
};

struct Round : public Shape
{
    Round(int size) : Shape(size) {}
    void print()
    {
        cout << "je suis un rond de : " << size << endl;
    }
};

static const int NBR_FORME = 10;
struct Tableau{
    Shape* tab[NBR_FORME] = {nullptr};

    void ajouter(Shape* s){
        tab[nbr++] = s;
    }

    Shape* operator[](int pos)
    {
        return tab[pos];
    }

    int nbr = 0;
};

void test_forme()
{
    Tableau t1;    
    t1.ajouter( new Round(2) );
    t1.ajouter( new Round(3) );
    t1.ajouter( new Square(4) );

    for(int i=0; i<t1.nbr; i++){
        t1[i]->print();
    }

    cout << "Copie du tableau" << endl;
    Tableau t2 = t1;

    for(int i=0; i<t2.nbr; i++){
        t2[i]->print();
    }

    cout << "Modification du tableau 2" << endl;
    for(int i=0; i<t2.nbr; i++){
        t2[i]->size += 10;
    }

    for(int i=0; i<t1.nbr; i++){
        cout << "Tableau 1 : ";
        t1[i]->print();
        cout << "Tableau 2 : ";
        t2[i]->print();
    }
}
```

## Ex 3 - Copie

Surcharger l'opérateur `=` de l'exercice `#2` pour que la copie rende les listes indépendantes.