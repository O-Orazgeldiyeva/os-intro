# Российский университет дружбы народов
### Факультет физико-математических и естественных наук

***

## Отчёт по лабораторной работе №6
### Анализ файловой системы Linux. Команды для работы с файлами и каталогами 


**Дисциплина:** Операционные системы

**Студент:** Оразгелдиева Огулнур

**Группа:** НПИбд-02-20

**Студ. номер:** 1032205431

2021, Москва

***

**Лабораторная работа №6**

**Анализ файловой системы Linux. Команды для работы с файлами и каталогами**

**Цель:**

* Ознакомление с файловой системой Linux, её структурой, именами и содержанием каталогов. 
* Приобретение практических навыков по применению команд для работы с файлами и каталогами, по управлению процессами (и работами), по проверке использования диска и обслуживанию файловой системы

***

**Задачи:**

1. Выполнить все примеры, приведённые в первой части описания лабораторной работы

2. Копировать файлы, каталоги

3. Перемещать и переименовывать файлы и каталоги

4. Присвоить и отнять определенные права доступа у владельца, членов группы и остальных

5. Изучить команды *mount, fsck, mkfs, kill*


***

**Выполнение работы:**

***

1. Выполнила все примеры, приведенные в первой части описания лабораторной работы.

* **Копирование файлов и каталогов** 

 **Примеры**
      
  **1.** Копирование файла в текущем каталоге. Скопировать файл *~/abc1* в файл *april* и в файл *may*: 
           (см. рис. 1)
           
![Рисунок 1. Копирование файла abc1 в файлы april и may](https://i.imgur.com/3o2FtnK.png )

*Рисунок 1. Копирование файла abc1 в файлы april и may*
           
**Пояснения:**
           
* сначала вводим команду *cd* для перехода в домашний каталог;
* создаем там файл *abc1*, используя команду *touch* (эта команда предназначена для создания файлов, а для создания каталогов существует команда *mkdir*).
* копируем *abc1* в файлы *april* и *may*, используя команду *ср* 
           
  ***
           
  **2.** Копирование нескольких файлов в каталог. Скопировать файлы *april* и *may* в каталог *monthly* (см. рис. 2):
           
![Рисунок 2. Копирование файлов may и april в каталог monthly](https://i.imgur.com/KgAJQzK.png)
            
*Рисунок 2. Копирование файлов may и april в каталог monthly*
  
  **Пояснения:**
           
* создаем каталог *monthly*  помощью команды *mkdir*
* копируем файлы *april* и *may* с помощью команды *ср* в каталог *monthly*. Для этого после перечисляем файлы через пробел, а в конце указываем каталог, которую копируем
* проверяем содержимое каталога *monthly*  помощью команды *ls*
           
***
           
  **3.** Копирование файлов в произвольном каталоге.Скопировать файл *monthly/may* в файл с именем *june* (см. рис. 3):
           
![Рисунок 3. Копирование файла monthly/may в monthly/june](https://i.imgur.com/Hc2jbnc.png)
           
*Рисунок 3. Копирование файла monthly/may в monthly/june*
           
**Пояснения:**
           
* копируем *monthly/may* в *monthly/june*, используя ср. Сначала пишем, что копируем, в конце - куда
* смотрим содержимое *monthly*. оявился файл *june*
           
   ***
           
  **4.** Копирование каталогов в текущем каталоге. Скопировать каталог monthly в каталог *monthly.00* (см. рис. 4)
           
![Рисунок 4. Копирование monthly месте с входящими в него файлами monthly.00](https://i.imgur.com/AVh4Kce.png)
            
*Рисунок 4. Копирование monthly месте с входящими в него файлами monthly.00*
           
**Пояснения:**
           
* создаем каталог *monthly.00*  помощью команды *mkdir*
* рекурсивно копируем *monthly* в *monthly.00* (с опцией *r*, т.е рекурсивно - вместе со всеми входящими в каталог файлами и подкаталогами)
* проверила содержимое *monthly.00*  и *monthly*
        
   ***
        
  **5.** Копирование каталогов в произвольном каталоге. Скопировать каталог *monthly.00* в каталог */tmp* (см. рис. 5)
        
![Рисунок 5. Копирование monthly.00 в /tmp](https://i.imgur.com/Nbfsv7d.png)

*Рисунок 5. Копирование monthly.00 в /tmp*
        
**Пояснения:**
           
* опируем *monthly.00* в */tmp* вместе со всем содержимым, используя команду *ср* с опцией *r*
* проверяем содержимое каталога */tmp*. Внутри этога каталога появился подкаталог *monthly.00*
        
    ***
    
* **Перемещение и переименование файлов и каталогов**
        
 **Примеры:**
        
  **1.** Переименование файлов в текущем каталоге. Изменить название файла *april* на *july* в домашнем каталоге. (см. рис. 6)
        
![Рисунок 6. Переименование april на july](https://i.imgur.com/EctKfc1.png)

*Рисунок 6. Переименование april на july*
        
**Пояснения:**
        
* переходим на домашний каталог
* переименовываем *april* на *july*, используя команду *mv*. Эта команда используется для перемещения или переименования файлов и каталогов.
* смотрим содержимое дом. каталога, проверяем, что изменили название файла с *april* на *july*
        
***
        
  **2.** Перемещение файлов в другой каталог. Переместить файл *july* в каталог *monthly.00*
        (см. рис. 7)
        
![Рисунок 7. Перемещение файла july в каталог monthly.00](https://i.imgur.com/KAruEpS.png)

*Рисунок 7. Перемещение файла july в каталог monthly.00*
        
**Пояснения:**
        
* перемещаем файл *july*  каталог *monthly.00* используя команду *mv*
* проверяем содержимое каталога, появляется файл *july*
        
  ***
        
  **3.**  Переименование каталогов в текущем каталоге. Переименовать каталог *monthly.00* в *monthly.01*
        (см. рис. 8)
        
![Рисунок 8. Переименование каталога monthly.00 в monthly.01](https://i.imgur.com/SGyE2pN.png)

*Рисунок 8. Переименование каталога monthly.00 в monthly.01*
        
**Пояснения:**
        
* переименовываем каталог *monthly.00* в *monthly.01* используя *mv*
* с помощью команды *ls* проверяем, что файл переименован
        
***
        
  **4.** Перемещение каталога в другой каталог. Переместить каталог *monthly.01* в каталог *reports* (см. рис. 9)
        
![Рисунок 9. Перемещение monthly.01 в reports](https://i.imgur.com/xvFrpNL.png)
        
*Рисунок 9. Перемещение monthly.01 в reports*
        
**Пояснения:**
        
* с помощью команды создания каталогов создаем каталог *reports*
* перемещаем каталог *monthly.01* в каталог *reports*, вводя вкомандной строке команду *mv* 
* проверяем, что в каталоге *reports* присутствуем каталог *monthly.01*
        
   ***
        
  **5.** Переименование каталога, не являющегося текущим. Переименовать каталог *reports/monthly.01* в *reports/monthly*
        (см. рис. 10) 
        
![Рисунок 10. Переименование каталога reports/monthly.01 в reports/monthly](https://i.imgur.com/MyBLYYM.png)

*Рисунок 10. Переименование каталога reports/monthly.01 в reports/monthly*
        
**Пояснения:**
        
* используя команду *mv* переименовываем подкаталог *monthly.01* в *monthly* каталога *reports*
* смотрим содержимое каталога *reports*, *monthly.01* переименован в *monthly*
        
   ***
        
* **Изменение прав доступа**
      
 **Примеры:**
      
  **1.** Требуется создать файл *~/may* с правом выполнения для владельца
        (см. рис. 11)
        
![Рисунок 11. Файл *~/may* с правом выполнения для владельца](https://i.imgur.com/5VWlXjm.png)

*Рисунок 11. Файл *~/may* с правом выполнения для владельца*
        
**Пояснения:**
        
* переходим на домашний каталог с помощью команды *cd* и создаём там файл с именем *may*, используя команду *touch*
* смотрим, какие права доступа у созданного файла, используя *ls* с опцией *l*
* так как у владельца нет права выполнения, добавляем это право с помощью команды *chmod* с режимом *u+x*, где *u* - это владелец, *+* означает "даем право", а *x* - право на выполнение
* проверяем, появилось ли у владельца право на выполнение файла *may*
        
 ***
        
  **2.** Требуется лишить владельца файла *~/may* права на выполнение (см. рис. 12)
        
![Рисунок 12. Лишение владельца прав на выполнение файла may](https://i.imgur.com/8tmcOHq.png)

*Рисунок 12. Лишение владельца прав на выполнение файла may*
        
**Пояснения:**
        
* с помощью команды *chmod* и режима *u-x* (где *u* - это владелец, *-* означает лишение прав, а *x* - право на выполнение) убираему владельца право на выполнение
* вводя команду *ls* с опцией *l*, видим, что у владельца нет прав на выполнения файла *may*
        
***
        
  **3.** Требуется создать каталог monthly с запретом на чтение для членов группы и всех остальных пользователей
        (см. рис. 13)
        
![Рисунок 13. Запрет на чтение каталога monthly для членов группы и остальных](https://i.imgur.com/2wuhlNC.png)

*Рисунок 13. Запрет на чтение каталога monthly для членов группы и остальных*
       
**Пояснения:**
        
* в одном из предыдущих примеров уже создали каталог *monthly*, поэтому проверяем его наличие
* используя команду *chmod* и режим *g-r,o-r*, отнимаем у членов группы и остальных права на чтение каталога *monthly*
* проверяем, убрали ли у группы и остальных права на чтение каталога *monthly* (*d* перед правами доступа, означает, что это каталог; перед файлами стоит знак "-")
        
***
        
  **4.**  Требуется создать файл *~/abc1* с правом записи для членов группы
        (см. рис. 14)
        
![Рисунок 14. Право на запись для членов группы файла abc1](https://i.imgur.com/KNVDeQP.png)

*Рисунок 14. Право на запись для членов группы файла abc1*
        
**Пояснения:**
        
* в одном из предыдущих примеров уже создали  *abc1*, поэтому проверяем его наличие
* с помощью команды *chmod* и режима *g+w* даем членам группы право на запись 
* проверяем права доступа файла 
        
   ***
    ***
2. Выполняем следующие действия:
    
  **2.1.** Скопируем файл */usr/include/sys/io.h* в домашний каталог и назовем его *equipment*. 
    (см. рис. 15)
    
![Рисунок 15. Копирование io.h и переименование в equipment](https://i.imgur.com/0JU6Fbr.png)

*Рисунок 15. Копирование io.h и переименование в equipment*
    
**Пояснения:**
    
* проверяем есть ли файл *io.h* в */usr/include/sys*
* копируем это файл с помощью команды *ср* в домашний каталог
* изменяем название файла в *equipment* с помощью *mv*
* проверяем, что файл скопирован и переименован
    
  ***
    
  **2.2.** В домашнем каталоге создала директорию *~/ski.plases* с помощью команды *mkdir* (см. рис. 16)
    
![Рисунок 16. Создание каталога ski.places](https://i.imgur.com/beeh37L.png)

*Рисунок 16. Создание каталога ski.places*
    
***
    
  **2.3.**  Перемещаем файл *equipment* в каталог *~/ski.plases* с помощью команды *mv*. (см. рис. 17)
    
![Рисунок 17. Перемещение файла equipment в каталог ~/ski.plases](https://i.imgur.com/65Q3X5c.png)

*Рисунок 17. Перемещение файла equipment в каталог ~/ski.plases*
    
***
    
  **2.4.** Переименовываем файл *~/ski.plases/equipment* в *~/ski.plases/equiplist* с помощью команды *mv* (эта команда используется не только для перемещения, но и для переименования)
    (см. рис. 18)
    
![Рисунок 18. Переименование файла ski.plases/equipment в ski.plases/equiplist](https://i.imgur.com/jwn52Ap.png)

*Рисунок 18. Переименование файла ski.plases/equipment в ski.plases/equiplist*
    
***
    
  **2.5.** Создаем в домашнем каталоге файл *abc1* и копируем его в каталог *~/ski.plases*, называем его *equiplist2*. (см. рис. 19)
    
![Рисунок 19. Копирование и переименование abc1](https://i.imgur.com/7rkOrMo.png)

*Рисунок 19. Копирование и переименование abc1*
    
**Пояснения:**
    
* файл *abc1* был создан ранее, проверяем его наличие
* с помощью команды *ср* копируем его в каталог *ski.places* 
* меняем название файла *abc1* на *equiplist2* используя *mv*
* проверяем с помощью *ls* содержимое *ski.places*
    
***
    
  **2.6.**  Создаём каталог с именем *equipment* в каталоге *~/ski.plases*, используя команду *mkdir*. (см. рис. 20)
    
![Рисунок 20. Создание в каталоге ski.places подкаталога equipment](https://i.imgur.com/QnB5Eyw.png)

*Рисунок 20. Создание в каталоге ski.places подкаталога equipment*
    
***
    
  **2.7.** Перемещаем файлы *~/ski.plases/equiplist* и *equiplist2* в каталог *~/ski.plases/equipment*.
    Для этого воспользуемся командой *mv*, вводя файлы через пробе, а в конце - каталог, в которую перемещаем файлы
    (см. рис. 21)
    
![Рисунок 21. Перемещение файлов в equipment](https://i.imgur.com/ASEVY8A.png)

*Рисунок 21. Перемещение файлов в equipment*
    
***
    
  **2.8.** Создаём и перемещаем каталог *~/newdir* в каталог *~/ski.plases* и называем его *plans*. (см. рис. 22)
    
![Рисунок 22. Создание, перемещение и переименование каталога newdir](https://i.imgur.com/vOxXSac.png)
    
*Рисунок 22. Создание, перемещение и переименование каталога newdir*
    
**Пояснения:**
    
* создаём каталог *newdir* при помощи *mkdir*
* используем команду *mv* для перемещения этого каталога в каталог *ski.places*
* переименовываем каталог *newdir* в *plans* с помощью *mv*
    
***
 ***
    
3. Выполняем следующие действия:
    
  **3.1.** Создаем каталог *australia* с правами доступа *drwxr--r--*
    
![Рисунок 23. Присвоение прав доступа к каталогу australia](https://i.imgur.com/oeiqjvu.png)

*Рисунок 23. Присвоение прав доступа к каталогу australia*
    
**Пояснения:**
    
* *drwxr--r--* - права доступа, которые нужно установить. Так как в начале прав доступа есть *d*, то мы должны создать каталог. Создаём каталог с помощью команды *mkdir*
* смотрим, какие права изначально даются к этому каталогу.
* лишаем прва на запись и выполнение членов группы, а остальных - прав на выполнение. Нужные права доступа устанолены
    
***
    
  **3.2** Создаем каталог *play* с правами доступа *drwx--x--x*
    
Чтобы было просто в режиме команды *chmod*, используем "=". (см. рис. 24)
    
![Рисунок 24. Присвоение прав доступа к каталогу play](https://i.imgur.com/gn8LTSW.png)

*Рисунок 24. Присвоение прав доступа к каталогу play*
    
***
    
  **3.3.** На этот раз нужно создать файл, так как в начале прав доступа идет "-".
    Уставливаем  права доступа  *-r-xr--r--* аналогично предыдущему пункту. (см. рис. 25)
    
![Рисунок 25. Присвоение прав доступа к файлу my_os](https://i.imgur.com/1BO5d2u.png)

*Рисунок 25. Присвоение прав доступа к файлу my_os*
    
 ***
    
  **3.4** Создаем файл *feathers*, установим права доступа аналогично предыдущим пунктам
    (см. рис. 26)
    
![Рисунок 26. Присвоение прав доступа к файлу feathers](https://i.imgur.com/hXAedYv.png)

*Рисунок 26. Присвоение прав доступа к файлу feathers*
    

8**
 ***
4. Проделаем приведеннные ниже упражнения:

  **4.1.** Просматриваем содержимое файла */etc/password*. Для того, чтобы просмотреть содержимое файла используем команду *cat* (для просмотра каталога используем *ls*). Такого файла нет; попробуем посмотреть содержимое каталога */etc* при помощи *ls*. (см. рис. 27)  
    
![Рисунок 27. Содержимое файла /etc/password, содержимое каталога /etc](https://i.imgur.com/Jk2ZK7j.png)

*Рисунок 27. Содержимое файла /etc/password, содержимое каталога /etc*
    
Просмотрев каталог */etc* нашла два файла с похожими названиями, поэтому просмотрела их содержимое. (файлы *passwd* и *passwd-*), используя команду *cat*.
    (см. рис. 28-30)
    
    
![Рисунок 28. Файлы passwd и passwd. Содержимое файла /etc/passwd](https://i.imgur.com/DK2fBBo.png)

*Рисунок 28. Файлы passwd и passwd. Содержимое файла /etc/passwd*
    
![Рисунок 29. Содержимое файла /etc/passwd и /etc/passwd-](https://i.imgur.com/zy3Fn2M.png)

*Рисунок 29. Содержимое файла /etc/passwd и /etc/passwd-*
    
![Рисунок 30. Содержимое файла /etc/passwd-](https://i.imgur.com/C8til48.png)
  
*Рисунок 30. Содержимое файла /etc/passwd-*
    
  ***
    
  **4.2.** Скопирум файл *~/feathers* в файл *~/file.old*.
    
Для это используем команду *cp*. (см. рис. 31)
    
![Рисунок 31. Копирование fearhers в file.old](https://i.imgur.com/FfdWFBa.png)

*Рисунок 31. Копирование fearhers в file.old*
    
***
    
  **4.3.**  Переместим файл *~/file.old* в каталог *~/play*.
    Сделаем это при помощи команды *mv*. (см. рис. 32)
    
![Рисунок 32. Копирвание file.old в play](https://i.imgur.com/n6sCKno.png)

*Рисунок 32. Копирвание file.old в play*
    
 ***
    
  **4.4** Скопируем каталог *~/play* в каталог *~/fun*. Для этого воспользуемся командой *cp*. (см. рис. 33)
    
![Рисунок 33. Копирование каталога ~/play в каталог ~/fun](https://i.imgur.com/IAkht7C.png)

*Рисунок 33. Копирование каталога ~/play в каталог ~/fun*
    
**Пояснения:**
    
* сначала использовала команду *cp* для того, чтобы скопировать каталог. Но это не получилось, потому что этот каталог был не пустым. 
* исправила ошибку и в команде *ср* использовала опцию *r*, которая копирует файл вместе с содержимым
    
***
    
  **4.5.** Перемещаем каталог *fun* в *play*, используя при этом команду *mv*. Потом используя эту же команду переименовываем *fun* в *games*. (см. рис. 34)
    
![Рисунок 34. Перемещение и переименование fun](https://i.imgur.com/9U3uWyD.png)

*Рисунок 34. Перемещение и переименование fun*
    
***
    
  **4.6.** Лишим владельца файла *~/feathers* права на чтение. Сделаем это при помощи *chmod u-r*. (см. рис. 35)
    
![Рисунок 35. Лишение права на чтение для владельца feathers](https://i.imgur.com/A2thTV8.png)

*[Рисунок 35. Лишение права на чтение для владельца feathers*
    
***
   
  **4.7.** Если попытаемся просмотреть файл *~/feathers* командой *cat*, произойдет ошибка, так как мы лишили владельца права на чтение. (предыдущий пункт). (см. рис. 36)
    
![Рисунок 36. Попытка просмотреть файл feathers](https://i.imgur.com/BWN9NCd.png)

*Рисунок 36. Попытка просмотреть файл feathers*
    
   ***
    
  **4.8.** Если попытаемся скопировать файл, например в каталог */tmp*, произойдет та же ошибка. что и в предыдущем пункте задания. (см. рис. 37)
    
![Рисунок 37. Попытка скопировать файл feathers](https://i.imgur.com/FNS3Lx7.png)
  
*Рисунок 37. Попытка скопировать файл feathers*
    
   ***
    
  **4.9.** Дадим владельцу файла *~/feathers* право на чтение с помощью *chmod u+r*. Теперь мы можем скопировать файл, например, в каталог *monthly* (см. рис. 38)
    
![Рисунок 38. Добавление прав на чтение feathers](https://i.imgur.com/NzTyBJL.png)

*Рисунок 38. Добавление прав на чтение feathers*
    
***
    
  **4.10.**  Лишим владельца каталога *~/play* права на выполнение. Для это нужно использовать команду *chmod u-x*. (см. рис. 39)
    
![Рисунок 39. Лишение прав на выполнение play](https://i.imgur.com/EafyXBw.png)

*Рисунок 39. Лишение прав на выполнение play*
    
***
    
  **4.11** Попытаемся перейти в каталог *~/play*. Не получается, так как ранее мы лишили владельца прав на выполнение. (см. рис. 40)
    
![Рисунок 40. Попытка перейти в каталог play](https://i.imgur.com/AV0sTo7.png)

*Рисунок 40. Попытка перейти в каталог play*
    
***
    
  **4.12** Дадим владельцу право на выполение *play*. еперь можем перейти на этот каталог.
    (см. рис. 41)
    
![Рисунок 41. Добавление прав на выпонение play](https://i.imgur.com/sCEifBa.png)

*Рисунок 41. Добавление прав на выпонение play*
    
 ***
 ***
    
5. Прочитаем man по командам *mount, fsck, mkfs, kill*

*mount* - это команда для просмотра используемых в операционной системе файловых систем.

*fsck* - это команда, которая проверяет и устраняет ошибки в файловой системе.

*mkfs* - это команда для создания файловой системы Linux на некотором устройстве, обычно в разделе жёсткого диска

*kill* - это команда, которая посылает системе сигнал, чтобы заставить ее завершить процесс.

***

**Вывод:** на лабораторной работе ознакомилась с файловой системой Linux, её структурой, именами и содержанием каталогов; приобрела практические навыки по применению команд для работы с файлами и каталогами, по управлению процессами (и работами), по проверке использования диска и обслуживанию файловой системы



