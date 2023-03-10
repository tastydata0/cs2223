# Введение в std::vector

`std::vector` - это класс шаблона контейнера, который представляет собой динамический массив, в котором размер может меняться во время выполнения программы. Он является одним из наиболее полезных контейнеров в C++, и используется часто во многих приложениях.
## Создание вектора

Чтобы создать std::vector, необходимо включить заголовочный файл <vector> и использовать следующий синтаксис:

```cpp
vector<int> myVector;
```
Этот код создает пустой вектор типа int. Как только вектор создан, можно добавлять элементы в него.

## Добавление элементов

Чтобы добавить элемент в вектор, можно использовать метод `push_back()`:

```cpp
myVector.push_back(10);
```
Этот код добавляет элемент 10 в конец вектора myVector. 
<br>
<img src="09aowmJDzhBlOn0-n.webp">
<br>
Если вам нужно добавить несколько элементов сразу, можно использовать инициализацию вектора:


```cpp
vector<int> myVector = { 1, 2, 3, 4, 5 };
```
Этот код создает вектор myVector, содержащий пять элементов.

## Обращение к элементам

Чтобы получить доступ к элементам вектора, можно использовать оператор индексирования []:

```cpp
int x = myVector[0]; // получаем первый элемент вектора
```
Этот код присваивает переменной x значение первого элемента вектора myVector. Обратите внимание, что если индекс находится за пределами размера вектора, то программа может завершиться с ошибкой.

## Изменение размера вектора

Если вы хотите изменить размер вектора, вы можете использовать метод resize():

```cpp
myVector.resize(10); // устанавливаем размер вектора в 10
```
Этот код устанавливает размер вектора myVector в 10. Если новый размер вектора больше старого, то новые элементы будут заполнены значениями по умолчанию. Если новый размер меньше старого, то элементы, которые выходят за пределы нового размера, будут удалены.

## Использование цикла for для обхода вектора

Один из самых простых и удобных способов обхода элементов std::vector - это использование цикла for. С помощью цикла for можно легко пройти по всем элементам вектора, начиная с первого и заканчивая последним.

```c++
#include <vector>
#include <iostream>

int main()
{
    std::vector<int> v{ 1, 2, 3, 4, 5 };
    for (int i = 0; i < v.size(); ++i)
    {
        std::cout << v[i] << " ";
    }
    std::cout << std::endl;
    return 0;
}
```
В этом примере мы создаем вектор v, который содержит пять целых чисел. Затем мы проходимся по всем элементам вектора с помощью цикла for и выводим их на экран.
## Использование итераторов

В C++ также можно использовать итераторы для обхода элементов std::vector. Итераторы - это объекты, которые предоставляют доступ к элементам контейнера.

```c++
#include <vector>
#include <iostream>

int main()
{
    std::vector<int> v{ 1, 2, 3, 4, 5 };
    for (auto it = v.begin(); it != v.end(); ++it)
    {
        std::cout << *it << " ";
    }
    std::cout << std::endl;
    return 0;
}
```
Здесь мы используем auto для определения типа итератора, так как он может изменяться в зависимости от типа элементов вектора. Затем мы проходимся по всем элементам вектора, начиная с первого элемента (используя метод begin()) и заканчивая элементом, следующим за последним (используя метод end()).
## Использование диапазонного цикла for (foreach)

В C++11 появился диапазонный цикл for, который упрощает обход элементов std::vector. С его помощью можно проходить по всем элементам вектора без использования итераторов или индексов.

```c++
#include <vector>
#include <iostream>

int main()
{
    std::vector<int> v{ 1, 2, 3, 4, 5 };
    for (auto& x : v)
    {
        std::cout << x << " ";
    }
    std::cout << std::endl;
    return 0;
}
```
Здесь мы используем диапазонный цикл for, чтобы пройти по всем элементам вектора.

## Алгоритмическая сложность

| Операция             | Сложность       |
|----------------------|-----------------|
| Вставка в начало     |          `O(n)` |
| Вставка по индексу   |          `O(n)` |
| Вставка в конец      |          `O(1)` |
| Удаление из начала   |          `O(n)` |
| Удаление по индексу  |          `O(n)` |
| Удаление из конца    |          `O(1)` |
| Получение по индексу |          `O(1)` |
| Поиск по значению    |          `O(n)` |

## Практика
1. Написать программу, которая запрашивает у пользователя 10 целых чисел и сохраняет их в `vector`. Затем программа должна вывести сумму всех чисел и среднее значение.

2. Написать программу, которая запрашивает у пользователя строку, разбивает ее на слова и сохраняет каждое слово в отдельном элементе `vector<string>`. Затем программа должна вывести все слова в обратном порядке.

3. Написать программу, которая запрашивает у пользователя два вектора целых чисел a и b одинаковой длины. Затем программа должна вычислить и вывести скалярное произведение этих векторов.

4. Написать функцию, которая принимает на вход `vector<int>` и возвращает новый вектор, содержащий только четные числа из исходного вектора.

5. Написать программу, которая запрашивает у пользователя два вектора целых чисел a и b одинаковой длины. Затем программа должна создать новый вектор c, содержащий сумму соответствующих элементов векторов a и b. Например, если `a = {1, 2, 3}` и `b = {4, 5, 6}`, то `c = {5, 7, 9}`.

6. Написать функцию, которая принимает на вход `vector<int>` и сортирует его в порядке возрастания.

7. Написать программу, которая запрашивает у пользователя целое число n и затем заполняет вектор `vector<int>` числами от 1 до n. Затем программа должна вывести все простые числа в векторе.

8. Написать функцию, которая принимает на вход `vector<int>` и возвращает новый вектор, содержащий только уникальные элементы из исходного вектора.

9. Написать программу, которая запрашивает у пользователя два вектора целых чисел a и b. Затем программа должна создать новый вектор c, содержащий все элементы векторов a и b, но без повторений.

10. Написать программу, которая запрашивает у пользователя два вектора целых чисел a и b. Затем программа должна создать новый вектор c, содержащий все элементы векторов a и b, но отсортированные в порядке возрастания.