# Ex1

Quel est l'affichage du programme suivant

```cpp
void ex1()
{
    int var_a = 6;
    int var_b = 4;
    int& ref_a = var_a;
    int& ref_b = var_b;

    std::cout << "1) a : " << var_a << " / ref_a : " << ref_a << " / var_b : " << var_b
              << " / ref_b : " << ref_b << std::endl;

    var_a = 5;
    std::cout << "2) a : " << var_a << " / ref_a : " << ref_a << " / var_b : " << var_b
              << " / ref_b : " << ref_b << std::endl;

    ref_a = 7;
    std::cout << "3) a : " << var_a << " / ref_a : " << ref_a << " / var_b : " << var_b
              << " / ref_b : " << ref_b << std::endl;

    ref_b = ref_a;
    std::cout << "4) a : " << var_a << " / ref_a : " << ref_a << " / var_b : " << var_b
              << " / ref_b : " << ref_b << std::endl;

    var_a = 9;
    std::cout << "5) a : " << var_a << " / ref_a : " << ref_a << " / var_b : " << var_b
              << " / ref_b : " << ref_b << std::endl;

    ref_b = 1;
    std::cout << "6) a : " << var_a << " / ref_a : " << ref_a << " / var_b : " << var_b
              << " / ref_b : " << ref_b << std::endl;

    var_b = 3;
    std::cout << "6) a : " << var_a << " / ref_a : " << ref_a << " / var_b : " << var_b
              << " / ref_b : " << ref_b << std::endl;
}
```

## Ex 2

Quel est l'affichage du programme

```CPP
typedef struct {
    int x;
    int y;
    int z;
} Point;

Point point_global;

Point& get_ref(){
    return point_global;
}

void ex2(){
    std::cout << "Exercice 2" << std::endl;
    // sizeof(int) == 4
    // sizeof(void*) == 8

    Point p1 {.x=1, .y=2};
    point_global.x = 4;
    point_global.y = 8;

    std::cout << "P1.x : " << p1.x << std::endl;
    std::cout << "Pg.x : " << point_global.x << std::endl;

    get_ref().x = 5;
    std::cout << "Sizeof : " << sizeof(get_ref()) << std::endl;
    std::cout << "Pg.x : " << point_global.x << std::endl;
    std::cout << "Pg.y : " << get_ref().y << std::endl;
}
```