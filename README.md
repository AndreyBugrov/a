# Лабораторная работа 1. Алгебра полиномов

[![Build Status](https://travis-ci.org/joemccann/dillinger.svg?branch=master)](https://travis-ci.org/joemccann/dillinger)

## Модели объектов
### Моном
Содержит коэффициент и степень. Представляется в виде строки со знаком "+" или "-", цифрами и буквами x, y, z. Степени не выделяются отдельно символом "^".
### Полином
Строится на основе списка (может либо содержать начальное звено, либо список мономов). Таким образом, реализуется однонаправленный линейный список. Представление аналогично представлению монома за исключением того, что знаков "+" и "-" может быть много.
### Алгоритмы, используемые с мономами и полиномами (мономы в данном случае рассматриваются как тривиальные полиномы)
1. Сложение. Реализуется при помощи слияния двух отсортированнх списков.
2. Вычитание. Реализуется при помощи слияния двух отсортированных списков полиномов (применяется инверсия коэффициентов).
4. Умножение. Реализутся при помощи слияния множества (по числу мономов во втором полиноме) отсортированных списков полиномов.
5. Деление. Реализуется при использовании алгоритма деления "уголком".
6. Дифференцирование. Ненулевая степень уменьшается на 1, коэффициент умножается на показатель соответствующей степени. Моном с нулевой степенью удаляется.
7. Интегрирование. Соответствующая степень увеличивается на 1, а коэффициент делится на эту соответствующую степень.
8. Нахождение значения в точке. У каждого монома высчитывается при помощи умножения и возведения в степень, затем все полученные результаты складываются.

__Строка таблицы__. Неразрывно связана с таблицей (поэтому возможен вариант наследования таблицы от строки). Имеет следующие поля: ключ (в данном случае это имя полинома), строку с представлением полинома 
__Таблицы__. Содержит структуру хранения строк таблицы. Визуально представляется в виде символов псевдографики, доступных в ASCII.








## Используемые инструменты
- Система контроля версий Git.
- Фреймворк для написания автоматических тестов Google Test.
- Среда разработки Microsoft Visual Studio.

## Состав команды
- Бугров Андрей
- Колесников Денс
- Цветков Алексей

## Общая структура проекта

Структура проекта:

  - `gtest` — библиотека Google Test.
  - `base` — каталог с основным проектом ЛР.
  - `base_test` — каталог с проектом с модульными тестами.
  - `README.md` — информация о проекте.
  - `mp2-lab6-algebra-polynom.sln` - файл с решением (solution) для Microsoft Visual Studio.
  - Служебные файлы
    - `.gitignore` — перечень расширений файлов, игнорируемых Git при добавлении файлов в репозиторий.
    - ` CMakeLists.txt` — корневой файл для сборки проекта с помощью CMake.


## Программа должна выполнять следующие операции:
1. Операции с полиномом:
    - Сложение;
    - Вычитание;
    - Умножение;
    - Деление;
    - Нахождение значения в точке;
    - Интегрирование;
    - Дифференцирование.
2. Операции с постфиксной формой:
    - Те же операции, что и у полинома, кроме нахождения значения в точке;
    - Подразумевается использование скобок.
3. Операции с таблицами:
    - Добавление;
    - Поиск;
    - Удаление.


## Требования к различным системам классов
1. Система классов для работы с полиномом:
    - Полином должен быть от трёх переменных;
    - Достаточно требовать от пользователя ввода коэффициентов в порядке сначала x, затем y, затем z;
    - Пользователь вправе не вводить коэффициент 1 перед мономами, вводить мономы в случайном порядке, вводить сразу несколько мономов с одинаковыми степенями переменных.
    - Полином должен быть организован на списке.
2. Система классов для работы с постфиксной формой:
    - Возможность использования в выражениях имена полиномов;
    - Проверка на корректность алгебраического выражения;
3. Система классов для работы с таблицами:
    - Ключ в таблице — имя полинома;
    - Достаточно консольное визуальное представление таблицы;
    - Должны быть представлены следующие 6 таблиц:
        - Хэш-таблица (с открытым перемешиванием и со списками);
        - Неупорядоченная таблица (на массиве и на списке);
        - Упорядоченная таблцица (на массиве и на дереве поиска).
4. Общее требование — разумное время работы алгоритмов.
