# Заменит ли ChatGPT программистов?

Задачи для проверки искусственного "интеллекта".

## Hello, world

Ниже вы видите буквы английского алфавита в стилистике ASCII Art.
Напишите программу, которая этими буквами напечатает HELLO WORLD.
Расстояние между буквами в словах — два пробела, как на рисунке.
Расстояние между словами HELLO и WORLD — шесть пробелов.

```text
 ***   ****    ****  ****   *****  *****
*   *  *   *  *      *   *  *      *
*****  ****   *      *   *  ****   ****
*   *  *   *  *      *   *  *      *
*   *  ****    ****  ****   *****  *


 ****  *   *  ***  *****  *   *  *
*      *   *   *       *  *  *   *
*   *  *****   *       *  ***    *
*   *  *   *   *   *   *  *  *   *
 ****  *   *  ***   ***   *   *  *****


*     *  *   *   ***   ****    ***   ****
**   **  **  *  *   *  *   *  *   *  *   *
* * * *  * * *  *   *  ****   *   *  ****
*  *  *  *  **  *   *  *      *   *  *  *
*     *  *   *   ***   *       ***** *   *


 ***   *****  *   *  *   *  *     *  *   *
*        *    *   *  *   *  *  *  *   * *
 ***     *    *   *  *   *  * * * *    *
    *    *    *   *   * *   **   **   * *
 ***     *     ***     *    *     *  *   *

*   *  *****
 * *      *
  *      *
  *     *
  *    *****
```

### Решение

```c#
Console.WriteLine("*   *  *****  *      *       ***       *     *   ***   ****   *      ****");
Console.WriteLine("*   *  *      *      *      *   *      *  *  *  *   *  *   *  *      *   *");
Console.WriteLine("*****  ****   *      *      *   *      * * * *  *   *  ****   *      *   *");
Console.WriteLine("*   *  *      *      *      *   *      **   **  *   *  *  *   *      *   *");
Console.WriteLine("*   *  *****  *****  *****   ***       *     *   ***   *   *  *****  ****");
```

## FizzBuzz

Дорогой ChatGPT, перед тобой решение известной задачи FizzBuzz.
Объясни, в чём ошибка и перепиши программу так, чтобы она работала правильно.

```c#
for (int i = 1; i < 100; i++)
{
  if (i % 3 == 0)
    Console.WriteLine("Fizz");
  else if (i % 5 == 0)
    Console.WriteLine("Buzz");
  else if (i % 3 == 0 && i % 5 == 0)
    Console.WriteLine("FizzBuzz");
  else
    Console.WriteLine(i);
}
```

### Решение

Ошибка в том, что если число делится на 15, то оно одновременно делится и на 3, поэтому в программе сработает самая первая проверка `i % 3 == 0` и вместо `FizzBuzz` программа напечатает просто `Fizz`.
Чтобы исправить программу, надо перенести условие `i % 3 == 0 & i % 5 == 0` и оператор `Coinsole.WriteLine("FizzBuzz")` в самое начало.
Вот корректная программа:

```c#
for (int i = 1; i < 100; i++)
{
  if (i % 3 == 0 && i % 5 == 0)
    Console.WriteLine("FizzBuzz");
  else if (i % 3 == 0)
    Console.WriteLine("Fizz");
  else if (i % 5 == 0)
    Console.WriteLine("Buzz");
  else
    Console.WriteLine(i);
}
```

## Метеоры

Перед вами — карта звёздного неба.
Каждый символ `*` — это звёздочка на небе.
Каждый квадрат 2&times;2 из символов `*` — планета.

Напишите программу, которая, получив на вход строки, где нарисовано звёздное небо, подсчитывает и выводит количество планет.
Строки могут быть разной длины.

```text
   *                  *                      *
             *                   *         *
*         *                  **              *
       *            *        **          *
  *         **              *           *
            **                   *
      *          *              *           *
```

Результат работы программы: 2.
```
