# Форматированный вывод в С++

> В C++ форматированный вывод осуществляется с помощью манипуляторов, которые мы можем использовать вместе с оператором вывода cout или другого потока вывода. В общем виде это выглядит так:

```cpp

cout << манипулятор1 << манипулятор2 << ... << манипуляторN << значение1 << значение2 << ... << значениеN << endl;

```

## Setw

> setw - устанавливает ширину поля вывода. Если ширина поля меньше, чем длина выводимого значения, то значение выводится без изменений. Если ширина поля больше, чем длина выводимого значения, то значение выравнивается по правому краю поля. Можно задать символ заполнения поля, который будет выводиться вместо пробелов. Также можно выравнивать по левому краю поля, используя флаг left.

```cpp
#include <iostream>
#include <iomanip>

using namespace std;

int main() {
    int a = 5;
    cout << "a = |" << a << "|" << endl;                                // a = |5|
    cout << "a = |" << setw(10) << a << "|" << endl;                    // a = |         5|
    cout << "a = |" << left << setw(10) << a << "|" << endl;            // a = |5         |
    cout << "a = |" << setw(10) << setfill('0') << a << "|" << endl;    // a = |0000000005|
    return 0;
}
```
## Setprecision

> setprecision - устанавливает количество цифр после запятой, которые будут выводиться при выводе чисел с плавающей точкой. Если количество цифр после запятой меньше, чем количество цифр в числе, то число выводится без изменений. Если количество цифр после запятой больше, чем количество цифр в числе, то число округляется.

```cpp
#include <iostream>
#include <iomanip>

using namespace std;

int main() {
    double a = 3.14159265358979323846;
    cout << "a = " << a << endl;                                // a = 3.14159
    cout << "a = " << setprecision(10) << a << endl;            // a = 3.1415926536
    cout << "a = " << setprecision(2) << a << endl;             // a = 3.1
    return 0;
}
```