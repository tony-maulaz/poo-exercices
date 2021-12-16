# Ex 1
Modifier le code suivant sans utiliser de `using` pour le rendre exécutable.

```cpp
#include <iostream>

namespace lib1 {
    int calc(int val){
        return val * 2;    
    }
}

namespace lib2 {
    int var = 2;
}

int main()
{
    
    cout << "Ex namespace" << endl;

    cout << calc( var ) << endl;
    
    return 0;
}
```

# Ex 2
Reprenez le code de l'exercice 1 et rendez le exécutable en utilisant des `using`

# Ex 3
Lors de l'exécution du code ci-dessous, quel est l'affichage.

```C
#include <iostream>

namespace lib1 {
    void afficher(int val){
        std::cout << "Afficher lib1" << std::endl;  
    }
}

namespace lib2 {
    void afficher(int val){
        std::cout << "Afficher lib2" << std::endl;  
    }
}

using namespace lib1;

int main()
{
    afficher(12);
    afficher(24);
    return 0;
}
```

# Ex 4
Dans l'exercice 3, modifier l'appel de la deuxième fonction `afficher` afin d'utiliser celle de la `lib2`.


# solutions
## Ex 1
```cpp
#include <iostream>

namespace lib1 {
    int calc(int val){
        return val * 2;    
    }
}

namespace lib2 {
    int var = 2;
}

int main()
{
    
    std::cout << "Ex namespace" << std::endl;

    std::cout << lib1::calc( lib2::var ) << std::endl;
    
    return 0;
}
```

## Ex 2
```cpp
#include <iostream>

namespace lib1 {
    int calc(int val){
        return val * 2;    
    }
}

namespace lib2 {
    int var = 2;
}

using namespace std;
using namespace lib1;
using namespace lib2;

int main()
{
    
    cout << "Ex namespace" << endl;

    cout << calc( var ) << endl;
    
    return 0;
}
```

## Ex 3
```console
Afficher lib1
Afficher lib1
```

## Ex 4
```cpp
lib2::afficher(24); // appel lib2
```