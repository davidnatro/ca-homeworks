# Индивидуальное домашнее задание №1

## Выполнил: Натро Давид, БПИ216 (ФКН, ПИ, 2 курс)

## Задача
Разработать программу, которая получает одномерный массив A размера N, после чего формирует из элементов массива A новый массив B по правилам, указанным в варианте, и выводит его. Память под массивы может выделяться статически, на стеке, автоматичеси по выбору разработчика. При решении задачи необходимо использовать подпрограммы для реализации ввода, вывода и формирования нового массива.
> 19 вариант: Сформировать массив B из элементов массива A заменой нулевых элементов, предшествующих первому отрицательному, единицей.

# <br> Инструкция к применению
## Запуск
Программа работает исключительно с файловым вводом/выводом.<br>
Для запуска пропишите команду:<br> ```./main.exe <input file> <output file>```,<br>где первым подаётся входной файл, а вторым выходной.<br>
В случае возникновения ошибки - будет выведено сообщение в консоль.
## Тестирование
Перейдите в папку ```tests``` и запустите скрипт ```script.py```, написанный на питоне, результаты тестов будут выведены в консоль. Более подробно с тестированием Вы можете ознакомиться, прочитав файл README.md, который находится в той же папке.
# <br> Отчет
### Задание выполнено на 7 балов.<br>
Далее будет указан каждый выполнений пункт. Более подробные комментарии, где это требуется, можно будет увидеть, как в примере ниже, под соответствующим критерием.
* Некоторый критерий
    > более подробное описание.

#

### 4 бала
* Приведено решение задачи на C :white_check_mark:
  > Файл main.c
* В полученную ассемблерную программу, откомпилированную без оптимизирующих и отладочных опций, добавлены комментарии, поясняющие эквивалентное представление переменных в программе на C. :white_check_mark:
  > К каждой переменной добавлен комментарий.
* Из ассемблерной программы убраны лишние макросы за счет использования соответствующих аргументов командной строки и/или за счет ручного редактирования исходного текста ассемблерной программы. :white_check_mark:
  > Комментарии в последнем критерии на 4 бала
* Модифицированная ассемблерная программа отдельно откомпилирована и скомпонована без использования опций отладки. :white_check_mark:
  > Комментарии в последнем критерии на 4 бала
* Представлено полное тестовое покрытие, дающее одинаковый результат на обоих программах. Приведены результаты тестовых прогонов для обоих программ, демонстрирующие эквивалентность функционирования. :white_check_mark:
  > В папке tests предоставлен скрипт script.py, который запускает тестирование и выводит результат. Более подробно со скриптом можно ознакомиться прочитав файл README.md, который находится в той же папке tests. В той же папке имеется файл report.txt, прочитав его, Вы можете ознакомиться с результатами тестовых прогонов. 
* Сформировать отчет, описывающий результаты тестовых прогонов и используемых опций компиляции и/или описания проведенных модификаций. :white_check_mark:
    > Обе программы проходят тестовое покрытие (отчет можно найти в папке tests или же убедиться лично, запустив скрипт script.py). <br><br>
    Было оптимизировано большое количество кода
    заменой строчек вида:<br>
    lea reg1, reg2<br>
    mov reg3, reg1<br>
    на строчки вида:<br>
    lea reg3, reg2<br>
    Сравнения теперь происходят напрямую, без использования
    регистра eax. <br>
    Удалено большое количество nop. <br><br>
    Опции компиляции: Вы можете ознакомиться с командами, применяющимися для компиляции проекта в файле build.py.
    Мной был написан скрипт на питоне, который позволил сэкономить много времени, благодаря автоматизации процесса компиляции. В данном скрипте вы увидите первые 3 команды, которые позволяли переводить C код в компактный ассемблер. После написаны 3 команды, которые переводили ассемблерные файлы в объектные. Последняя команда выполняла линковку. После чего удалялись все объектные файлы, происходил запуск программы и в консоль выводился результат её работы.


### 5 балов
* В реализованной программе использовать функции с передачей данных через параметры. :white_check_mark:
  > Реализованы функции read_data и print_data, в файлах read.c и print.c соответсвенно, с передачей данных через параметры
* Использовать локальные переменные. :white_check_mark:
  > В функциях read_data и main используются локальные переменные
* В ассемблерную программу при вызове функции добавить комментарии, описывающие передачу фактических параметров и перенос возвращаемого результата. :white_check_mark:
    > При вызове read_data и print_data добавлены коментарии.
* В функциях для формальных параметров добавить комментарии, описывающие связь между параметрами языка Си и регистрами (стеком).:white_check_mark:
* Добавить информацию о проведенных изменениях в отчет. :white_check_mark:

### 6 балов
* Рефакторинг программы на ассемблере за счет максимального использования регистров процессора. Добавление этой программы к уже представленным.:white_check_mark:
  > Были использованы регистры r12, r13, r14, r15, r12d, r13d, r14d, r15d.
* Добавление комментариев в разработанную программу, поясняющих эквивалентное использование регистров вместо переменных исходной программы на C.:white_check_mark:
  > Добавлены, где это требуется, коментарии. Так же в начале каждого ассемблерного файла Вы можете ознакомиться с рядом комментариев, которые описывают какие переменные хранит каждый из регистров 
* Представление результатов тестовых прогонов для разработанной программы. Оценка корректности ее выполнения на основе сравнения тестовых прогонов результатами тестирования предшествующих программ. :white_check_mark:
  > В папке tests предоставлен скрипт script.py, который запускает тестирование и выводит результат. Более подробно со скриптом можно ознакомиться прочитав файл README.md, который находится в той же папке tests. В той же папке имеется файл report.txt, прочитав его, Вы можете ознакомиться с результатами тестовых прогонов. 
* Добавить новую информацию в отчет. :white_check_mark:

### 7 балов
* Реализация программы на ассемблере, полученной после рефакторинга, в виде двух или более единиц компиляции. :white_check_mark:
  > main.c read.c print.c -> main.s read.s print.s<br>
  Программа состоит из трёх единиц компиляции.
* Задание файлов с исходными данными и файла для вывода результатов с использованием аргументов командной строки :white_check_mark:
  > Программа запускается командой ```./main.exe <input file> <output file>```, где первым подаётся входной файл, а вторым выходной.
* Добавить в отчет информацию о проделанных изменениях и результаты работы с тестовыми файлами. :white_check_mark:
