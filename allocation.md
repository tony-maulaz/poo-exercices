# Allocation

## Ex 1

Dans le code ci-dessous, modifier le `main` pour ajouter
- Faire une allocation d'un objet `Example` dans une variable `e1` et libérer ensuite la mémoire.
- Faire une allocation d'un tableau de `5` entiers dans une variable `tab` et libérer ensuite la mémoire.
- Faire une allocation pour un tableau de `5` pointeurs sur des objets `Example`.
  - L'allocation du tableau doit aller dans une variable `e2`.
  - Créer un objets `Example` dans le premier indice du tableau
  - Libérer la mémoire.

```CPP
struct Example{
    Example() {cout << "Construit" << endl; }
    ~Example() {cout << "Détruit" << endl; }
    int foo;
    int bar;
};

void main() {
    cout << "Example d'allocation"  << endl;
}
```

## Ex 2
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


## Solutions

### Ex 1
```CPP
void main() {
    cout << "Example d'allocation"  << endl;

    Example* e1 = new Example();
    delete e1; 

    int* tab = new int[5];
    delete[] tab; 

    Example** e2 = new Example*[5]();
    e2[0] = new Example();
    delete e2[0];
    delete[] e2;
}
```

### Ex 2
```CPP
struct Data{
    void init(int capacite){
        tab = new double[capacite]();
        this->capacite = capacite;
    }

    void liberer(){
        delete[] tab;
        tab = nullptr;
        capacite = 0;
    }

    int capacite = 0;
    double* tab = nullptr;
};
```

