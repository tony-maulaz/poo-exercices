# Ex 1

- Créer une classe `Animal` qui contient une méthode `speak`.
- Créer une classe `Dog` qui affiche `Wouf` sur la console lorsque la méthode  
  `speak` est appelée.

Le code suivant doit fonctionner.

```cpp
#include <iostream>
using namespace std;

int main()
{
    cout << "The dog is here" << endl;
    Animal* a = new Dog();
    a->speak();
}
```