# Российский университет дружбы народов
### Факультет физико-математических и естественных наук

***

## Отчёт по лабораторной работе №13
### Программирование в командном процессоре ОС UNIX. Расширенное программирование 

**Дисциплина:** Операционные системы

**Студент:** Оразгелдиева Огулнур

**Группа:** НПИбд-02-20

**Студ. номер:** 1032205431

2021, Москва

***

**Лабораторная работа №13**

**Программирование в командном процессоре ОС UNIX. Расширенное программирование**

**Цель:**

* изучить основы программирования в оболочке ОС UNIX 
* научиться писать более сложные командные файлы с использованием логических управляющих конструкций и циклов.

***

**Задачи:**

1. Ознакомиться с теоретическим материалом

2. Написать командный файл, реализующий упрощённый механизм семафоров. Запустить командный файл в одном виртуальном терминале в фоновом режиме, перенаправив его вывод в другой, в котором также запущен этот файл, но не фоновом, а в привилегированном режиме. 

3. Реализовать команду man с помощью командного файла. Изучить содержимое каталога /usr/share/man/man1. Командный файл должен получать в виде аргумента командной строки название команды и в виде результата выдавать справку об этой команде или сообщение об отсутствии справки, если соответствующего файла нет в каталоге man1.

4. Используя встроенную переменную $RANDOM, написать командный файл, генерирующий случайную последовательность букв латинского алфавита. ($RANDOM выдаёт псевдослучайные числа в диапазоне от 0 до32767)

***

**Теоретические сведения** [[1]](https://esystem.rudn.ru/pluginfile.php/1142377/mod_resource/content/2/008-lab_shell_prog_1.pdf)


Командный процессор (командная оболочка, интерпретатор команд shell) — это программа, позволяющая пользователю взаимодействовать с операционной системой компьютера. 

Bash (Bourne again shell или «возрождённый» shell) – это модифицированная версия программной оболочки Bourne-shell (sh или «Оболочка Борна»). Она является командным процессором, работающим интерактивно в текстовом окне. Bash нужен для приема команд пользователя и их отправки операционной системе для последующей обработки.

Взаимодействие оболочки и операционной системы обеспечивается с помощью специальной программы – терминала.

Командный процессор bash обеспечивает возможность использования переменных типа строка символов.
Имена переменных могут быть выбраны пользователем. Пользователь имеет возможность присвоить переменной значение некоторой строки символов.

Использование значения, присвоенного некоторой переменной, называется подстановкой. Для того чтобы имя переменной не сливалось с символами, которые могут следовать за ним в командной строке, при подстановке в общем случае используется следующая форма записи: ${имя переменной} 

Оболочка bash позволяет работать с массивами. Для создания массива используется команда set с флагом -A. [[1]](https://esystem.rudn.ru/pluginfile.php/1142377/mod_resource/content/2/008-lab_shell_prog_1.pdf)

test — UNIX-утилита для проверки типа файла и сравнения значений.

test -f file — истина, если file существует и является обычным файлом. [[2]](https://ru.wikipedia.org/wiki/Test)

Особенность less заключается в том, что команда не считывает текст полностью, а загружает его небольшими фрагментами.

Перечень всех опций и внутренних команд можно просмотреть в терминале, выполнив команду *man less*.

Использование опций не является обязательным. Открыть файл можно, выполнив следующую команду: *less filename.txt*

Командная строка исчезнет, а в окне терминала откроется указанный вами документ. [[3]](https://losst.ru/komanda-less-v-linux)

***

**Ход работы:**

1. Сначала создаём командный файл *lab13-1.sh* для задания 1 с помощью текстового редактора vi.

Напишем в нём программу (см. рис. 1), по которой в течение некоторого времени t1 (в нашем случае 3 секунды) дожидаться освобождения ресурса, выдавая об этом сообщение, а дождавшись его освобождения, использовать его в течение некоторого времени t2<>t1 (5 секунд), также выдавая информацию о том, что ресурс используется соответствующим командным файлом (процессом).

![Рисунок 1. Код программы для задания 1](https://i.imgur.com/CNu1FvG.png)

*Рисунок 1. Код программы для задания 1*

**Пояснения:** сначала файлу нужно задать номер (flock работает с дескрипторами), далее идет цикл while: пока файл существует (test -f ./lockfile), проверка заблокирован/разблокирован ли файл в течение некоторого времени. Если условие не выполняется, то выдаётся ошибка, так как файл может выполняться другим терминалом.

Даём права на выполнение командного файла. (см. рис. 2)

![Рисунок 2. Права на выполнение](https://i.imgur.com/6OZAVm9.png)

*Рисунок 2. Права на выполнение*

Теперь запускаем командный файл.

![Рисунок 3. Выполнение командного файла](https://i.imgur.com/tiBxS2E.png)

*Рисунок 3. Выполнение командного файла*

Когда процесс заблокирован выводится сообщение "Locked", когда разблокирован: "Unlocked" (см. рис. 3), а если он используется другим терминалом, то выдается "Error". (см. рис. 4) Когда запущено несколько терминалов для выполнения командного файла, когда в одном процесс разблокирован, в других выводится сообщение об ошибке.

![Рисунок 4. Выполнение командного файла несколькими терминалами](https://i.imgur.com/bZOaljJ.png)

*Рисунок 4. Выполнение командного файла несколькими терминалами*

Когда запущено несколько терминалов для выполнения командного файла, когда в одном процесс разблокирован, в других выводится сообщение об ошибке.

2. Создаём и открываем командный файл *lab13-2.sh* для выполнения задания 2 с помощью редактора vi.

Нажав "i", переходим в режим вставки и пишем код программы, который реализует команду man. (с. рис. 5)

![Рисунок 5. Код программы для задания 2](https://i.imgur.com/YY1z8sX.png)

*Рисунок 5. Код программы для задания 2*

**Пояснения:** так как в каталоге  */usr/share/man/man1* находятся архивы текстовых файлов, содержащих справку по большинству установленных в системе программ и команд, переходим в этот каталог, используя команду cd. После ввода названия команды, открываем архив со справкой об этой команде с помощью *less* в текущем каталоге (*/usr/share/man/man1*).

Даём права на выполнение командного файла и запускаем его. Введём, например, команду mkdir для справки. (см. рис. 6-7)

![Рисунок 6. Выполнение командного файла](https://i.imgur.com/QjPOhIR.png)

*Рисунок 6. Выполнение командного файла*

![Рисунок 7. Справка о команде mkdir](https://i.imgur.com/NnANYNd.png)

*Рисунок 7. Справка о команде mkdir*

3. Создаём и открываем командный файл *lab13-3.sh* для выполнения задания 3 с помощью редактора vi. (см. рис. 8)

![Рисунок 8. Создание командного файла](https://i.imgur.com/LM1qseW.png)

*Рисунок 8ю Создание командного файла*

Напишем в нём программу, генерирующую случайную последовательность букв латинского алфавита. (см. рис. 9)

![Рисунок 9. Код программы для задания 3](https://i.imgur.com/Sa080ww.png)

*Рисунок 9. Код программы для задания 3*

**Пояснения:** сначала задаем переменную, которая будет содержать случайную длину (количество символов) от 1 до 10 символов (не включая 10, т.е наибольшее 9); далее задаем массив *alphabet* с помощью *set -a*. Вносим в массив элементы - буквы латинского алфавита. Затем идёт создаём цикл *for*, который записывает случайные буквы ($RANDOM % 26 - случайные буква из 26, т.к в алфавите 26 букв от 0 до 25)  из массива длиной a ($RANDOM % 10 - это значит случайные числа от 1 до 10).
Даём права на выполнение и запускаем командный файл. (см рис. 10-11)

![Рисунок 10. Права на выполнение](https://i.imgur.com/OCIOHSH.png)

*Рисунок 10. Права на выполнение*

![Рисунок 11. Выполнение командного файла](https://i.imgur.com/F51ODTE.png)

*Рисунок 11. Выполнение командного файла*

Как видно из рис. 11, в результате выполнения программы выводятся от 1 до 10 случайных букв латинского алфавита, но каждая буква в отдельной строке.

Чтобы исправить, добавим в коде программы опцию *-n* к команде *echo*. (см. рис. 12) С помощью этой опции можно вывести буквы в одной строке, т.е после вывода буквы перехода на новую строку не будет.

![Рисунок 12. Код программы для задания 3](https://i.imgur.com/TV6tnNj.png)

*Рисунок 12. Код программы для задания 3*

Выполним командный файл. (см. рис. 13)

![Рисунок 13. Выполнение командного файла](https://i.imgur.com/IH9flyf.png)

*Рисунок 13. Выполнение командного файла*

Как видно из рис. 13, случайные буквы в одной строке. После использования опции не было переходов в новую строку, поэтому, вывод программы "слился" с командной строкой.

Чтобы исправить это , в коде программы сделаем следующие изменения: уменьшим число шагов (итераций на 1). Теперь у нас при выполнении цикла выводится на одну букву меньше, поэтому после выполнения цикла *for* еще раз выводим случайную букву с помощью *echo*, но на это раз без использования *-n*. (см. рис. 14)

![Рисунок 14. Код программы для задания 3](https://i.imgur.com/1OZXIEc.png)

*Рисунок 14. Код программы для задания 3*

Выполняем программу. (см. рис. 15)

![Рисунок 15. Выполнение коандного файла](https://i.imgur.com/DmmSJBm.png)

*Рисунок 15. Выполнение командного файла*

Теперь буквы выводятся в одной строке, не "сливаясь" при этом с командной строкой.

Строка случайной длины (до 10 букв) состоит из случайных букв латинского алфавита.

***
**Вывод:** на лабораторной работе изучила основы программирования в оболочке ОС UNIX и научилась писать более сложные командные файлы с использованием логических управляющих конструкций и циклов

***

**Библиография**

[[1] - РУДН, Операционные системы, "Программирование в командном процессоре ОС UNIX. Командные файлы"](https://esystem.rudn.ru/pluginfile.php/1142377/mod_resource/content/2/008-lab_shell_prog_1.pdf)

[[2] - Утилита test](https://ru.wikipedia.org/wiki/Test)

[[3] - Команда less в Linux](https://losst.ru/komanda-less-v-linux)

***