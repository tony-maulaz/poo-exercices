# Ex 1
Afficher le texte suivant dans la console.

```console
Bonjour
Comment allez-vous ?
```

# Ex 2
Écrire un programme qui affiche les valeurs des deux variables.

Le résultat est affiché avec deux chiffres après la virgule.

```CPP
double val_d = 12.34;
int cpt = 4;
```

L'affichage : 
```console
Affichage :
Cpt : 4 / Val : 12.34 
```

# Solutions
## Ex 1
```cpp
#include <iostream>

using namespace std;

int main()
{
    cout<<"Bonjour" << endl << "Comment allez-vous ?";
    return 0;
}
```

## Ex 2
```cpp
#include <iostream>
#include <iomanip>

using namespace std;

int main()
{
    double val_d = 12.34;
    int cpt = 4;
    
    cout << "Affichage" << endl;
    cout << "Cpt : " << cpt << " / Val : " << fixed << setprecision(2) << val_d;
    return 0;
}
```