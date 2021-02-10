## Ex 1

Est-ce que le programme ci-dessous est-correct ?
Quel est l'affichage du programme ?

```CPP
class C1 {
   public:
    void afficher();

   protected:
    int val;
};

void C1::afficher() { cout << "Val : " << val << endl; }

class C2 : public C1 {
   public:
    C2() { val = 4; }
};

void ex1() {
    C2 c;
    c.afficher();
    c.val = 2;
    c.afficher();
}
```

## Ex 2

Implémenter les classes `Vehicule` et `Voiture` de l'image suivante :

![alt text](images/heritage.png "UML")

Le nombre de roue est affecté pendant la construction des classes enfants.

Dans les méthodes, il faut juste afficher un texte.

Vous devez pouvoir exécuter le main suivant 

```CPP
void ex2()
{
    cout << "Exercice 2" << endl << endl;
    Voiture v;
    v.avancer();
    v.tourner();
}
```