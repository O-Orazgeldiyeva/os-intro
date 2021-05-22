# Российский университет дружбы народов
### Факультет физико-математических и естественных наук

***

## Отчёт по лабораторной работе №10
### Текстовой редактор emacs

**Дисциплина:** Операционные системы

**Студент:** Оразгелдиева Огулнур

**Группа:** НПИбд-02-20

**Студ. номер:** 1032205431

2021, Москва

***

**Лабораторная работа №10**

**Текстовой редактор emacs**

**Цель:**

* познакомиться с операционной системой Linux 
* получить практические навыки работы с редактором *Emacs*
***

**Задачи:**

1. Ознакомиться с теоретическим материалом
2. Ознакомиться с редактором emacs
3. Выполнить упражнения, используя команды emacs
4. Ответить на контрольные вопросы 

***

**Теоретические сведения**  [[1]](https://docs.altlinux.org/ru-RU/archive/2.2/html-single/master/user-html/ch06s02.html)
[[2]](https://esystem.rudn.ru/pluginfile.php/1142374/mod_resource/content/3/007-lab_emacs.pdf)

Emacs представляет собой мощный экранный редактор текста, написанный на языке высокого уровня *Elisp*

Буфер — это основная единица редактирования; один буфер соответствует одному куску редактируемого текста.
Чаще всего буферы обращаются к какому-либо файлу, считывая данные из файла в буфер, или записывая данные из буфера в файл.

Фрейм соответствует окну в обычном понимании этого слова. Каждый фрейм содержит область вывода и одно или несколько окон *Emacs*.

Окно в Emacs — это область экрана, в которой отображается буфер. Когда Emacs запускается, у вас на экране отображается одно окно. При обращении к некоторым функциям Emacs (таким, как оперативная справка и интерактивная документация) часто (временно) открываются дополнительные окна на экране Emacs. [[1]](https://docs.altlinux.org/ru-RU/archive/2.2/html-single/master/user-html/ch06s02.html)

Область вывода—одна или несколько строк внизу фрейма, в которой Emacs выводит различные сообщения, а также запрашивает подтверждения и дополнительную информацию от пользователя. 

Минибуфер используется для ввода дополнительной информации и всегда отображается в области вывода. 

Точка вставки - место вставки (удаления) данных в буфере.

Для запуска Emacs необходимо в командной строке набрать emacs (или emacs & для работы в фоновом режиме относительно консоли).

Для работы с Emacs можно использовать как элементы меню, так и различные сочетания клавиш. [[2]](https://esystem.rudn.ru/pluginfile.php/1142374/mod_resource/content/3/007-lab_emacs.pdf)

***

**Ход работы**

1. Ознакомилась с теоретическим материалом.
2. Ознакомилась с редакором emacs.
3. Выполнила следующие упражнения.

**Основные команды emacs**

1. Открыла emacs, вводя в командной строке соответсвующюю команду. В новом окне открылся редактор. (см. рис. 1-2)

![Рисунок 1. Открытие текстового редактора emacs](https://i.imgur.com/RwPK4Wd.png)

*Рисунок 1. Открытие текстового редактора emacs*

![Рисунок 2. Открытие текстового редактора emacs](https://i.imgur.com/DPnPPb2.png)

*Рисунок 2. Открытие текстового редактора emacs*

2. Создала файл *lab10.sh* с помощью комбинации *Ctrl-x Ctrl-f (C-x C-f)*. 
(см. рис. 3-4)

После нажатия комбинации клавиш появилась строка, в которой написала название файла.

![Рисунок 3. Создание файла lab10.txt](https://i.imgur.com/Hn3tGRf.png)

*Рисунок 3. Создание файла lab10.txt*

![Рисунок 4. Создание файла lab10.txt](https://i.imgur.com/ciQOPMx.png)

*Рисунок 4. Создание файла lab10.txt*

3. Набрала следующий текст в файле. (см. рис. 5)

![Рисунок 5. Текст](https://i.imgur.com/vxmlc0a.png)

*Рисунок 5. Текст*

4.  Сохранила файл с помощью комбинации клавиш *C-x, C-s*, после чего внизу появилась строка с местом сохранения файла. (см. рис. 6)

![Рисунок 6. Сохранение файла](https://i.imgur.com/mePJmPv.png)

*Рисунок 6. Сохранение файла*

5. Проделала с текстом стандартные процедуры редактирования.

  **5.1.** Вырезалаь одной командой целую строку *(С-k)*.
  
  Поставила курсор на строке, которую вырежем (7-ая строка). (см. рис. 7). Нажав ранее указанную комбинацию клавиш, вырезала строку. (см. рис. 8)
  
![Рисунок 7.Вырезать одной командой целую строку (С-k)](https://i.imgur.com/hxARL6a.png)

*Рисунок 7. Вырезать одной командой целую строку (С-k)*

![Рисунок 8. Вырезать одной командой целую строку (С-k)](https://i.imgur.com/965Yzjh.png)

*Рисунок 8. Вырезать одной командой целую строку (С-k)*

  **5.2.**  Вставила эту строку в конец файла *(C-y)*. (см. рис. 9)
  
![Рисунок 9. Вставить строку в конец файла](https://i.imgur.com/LRvVkn9.png)

*Рисунок 9. Вставка строки в конец файла*

Как видно, строка *echo $HELLO* вырезана и вставлена в конец файла.

  **5.3.** Выделила область текста *(C-space)*.
  
  Выделяемая часть текста обозначается серым цветом. (слово *hello*)
  (см. рис. 10)
  
![Рисунок 10. Выделение части текста](https://i.imgur.com/lHFWmGy.png)

*Рисунок 10. Выделение части текста*

  **5.4..**  Скопировала выделеую часть текста область в буфер обмена *(Esc-w)*. Выделение слова исчезло. (см рис. 11)
  
![Рисунок 11. Копирование в буфер обмена](https://i.imgur.com/rQ9yzGd.png)

*Рисунок 11. Копирование в буфер обмена*

  **5.5.** Вставила скопированную область в конец файла. 
  (см. рис. 12)
  
![Рисунок 12. Вставка скопированной области в конец файла](https://i.imgur.com/rw2YBYb.png)

*Рисунок 12. Вставка скопированной области в конец файла*

Как видно, скопированное слово *hello* вставили в конец текста.

  **5.6.**  Вновь выделила эту область с помощью *C-space* и на этот раз вырезала её *(C-w)*. 
  (см. рис. 13-14)
  
![Рисунок 13. Выделение области текста](https://i.imgur.com/5UECujK.png)

*Рисунок 13. Выделение области текста*

![Рисунок 14. Вырез области текста](https://i.imgur.com/GQKDCZf.png)

*Рисунок 14. Вырез области текста*

  **5.7.** Отменила последнее действие *(C-/)*. Вырезанное слово *hello* опять появилось (см. рис. 15)
  
![Рисунок 15. Отмена изменений](https://i.imgur.com/HBKfOFm.png)

*Рисунок 15. Отмена изменений*

6. Научилась использовать команды по перемещению курсора

  **6.1** Переместила курсор в начало строки (использовала клавиши *C-a*). 

  Для примера поставила курсор на конец строки 4, и используя *C-a* переместила курсор в начала этой строки. (см. рис. 16-17)

![Рисунок 16. Перемещение курсора в начало строки](https://i.imgur.com/ai0Ghpd.png)

*Рисунок 16. Перемещение курсора в начало строки*

![Рисунок 17. Перемещение курсора в начало строки*](https://i.imgur.com/KsEuUMd.png)

*Рисунок 17. Перемещение курсора в начало строки*

  **6.2.** Переместила курсор в конец строки (использовала *C-e*)
  
Теперь в той же строке переместилась в конец. (см. рис. 18)

![Рисунок 18. Перемещение курсора в конец строки](https://i.imgur.com/XiPBypr.png)

*Рисунок 18. Перемещение курсора в конец строки*

  **6.3.** Переместила курсор в начало буфера. Для этого нужно использовать комбинацию *M-<*. 
(см. рис. 19)

![Рисунок 19. Перемещение курсора в начало буфера](https://i.imgur.com/vi7930k.png)

*Рисунок 19. Перемещение курсора в начало буфера*

Курсор переместился в начало буфера, т.е текста файла.

  **6.4.** Переместила курсор в конец буфера (*M->*). (см. рис. 20)
  
![Рисунок 20. Перемещение курсора в конец буфера](https://i.imgur.com/PCXMms9.png)

*Рисунок 20. Перемещение курсора в конец буфера*

Курсор переместила в конец буфера.

7. Управление буферами.

  **7.1.** Вывела список активных буферов на экран с помощью *C-x C-b*. (см. рис. 21)
  
![Рисунок 21. Вывод списка активных буферов](https://i.imgur.com/TnjsOzl.png)

*Рисунок 21. Вывод списка активных буферов*

В результате появилось окно со спиком буферов.

  **7.2.** Переместилась во вновь открытое окно с помощью *C-x o* со списком открытых буферов 
  (см. рис. 22) 
  
![Рисунок 22. Перемещение в открытое окно](https://i.imgur.com/7WJbbNb.png)

*Рисунок 22. Перемещение в открытое окно*

Переключилась на другой буфер. Например, в буфер "Messages". (см. рис. 23-24)

![Рисунок 23. Перемещение в буфер](https://i.imgur.com/vMESzR4.png)

*Рисунок 23. Перемещение в буфер*

![Рисунок 24. Перемещение в буфер](https://i.imgur.com/Xo8mx5m.png)

*Рисунок 24. Перемещение в буфер*

  **7.3.** Закрыла это окно, используя *C-x 0*. (см. рис. 25)
  
![Рисунок 25. Закрытие](https://i.imgur.com/60rVDwA.png)

*Рисунок 25. Закрытие*

  **7.4.** Теперь вновь переключалась между буферами, но уже без вывода их списка на экран (с помощью *C-x b*). Переместилась в буфер "Messages". (см. рис. 26-27) 
  
![Рисунок 26. Перемещене в буфер](https://i.imgur.com/94F82IA.png)

*Рисунок 26. Перемещение в буфер*

![Рисунок 27. Перемещение в буфер](https://i.imgur.com/9N2AFsI.png)

*Рисунок 27. Перемещение в буфер*

На этот раз перешли в буфер в этом же окне, так как до этого осуществили перемещение между буферами через окно со списком активных буферов.

8. Управление окнами

  **8.1** Поделила фрейм на 4 части: разделила фрейм на два окна по вертикали (C-x 3), а затем каждое из этих окон на две части по горизонтали (C-x 2). (см. рис. 28-30)
  
![Рисунок 28. Деление фрейма на несколько окон](https://i.imgur.com/2DdNJnq.png)

*Рисунок 28. Деление окон на несколько окок*

Как видно из рис. 28, поделила фрей на дв вертикальных окна с помощью клавиш *C-x 3*. Теперь поделим  одну из  вертикальных окон на два горизонтальных с помощью *C-x 2*. (см. рис. 29)

![Рисунок 29. Деление фрейма на несколько окон](https://i.imgur.com/9plWFBi.png)

*Рисунок 29. Деление фрейма на несколько окон*

Теперь то же самое сделала и со второй частью. (см. рис. 30)

![Рисунок 30. Деление фрейма на несколько окон](https://i.imgur.com/LkLXGD1.png)

*Рисунок 30. Деление фрейма на несколько окон*

  **8.2.** В каждом из окон создала и открыла с помощью *C-x C-f* файл *lab.txt*. (см. рис. 31)

![Рисунок 31. Открытие файла](https://i.imgur.com/uvMulVY.png)

*Рисунок 31. Открытие файла*

(внизу каждого окна написано название файла, которая открыта)

Написала некоторые текст в файле. (см. рис. 32)

![Рисунок 32. Текст](https://i.imgur.com/ZNWERKS.png)

*Рисунок 32. Текст*

9. Режим поиска

  **9.1.** Переключилась в режим поиска с помощью *C-s*. Внизу появилась строка. (см. рис. 33)
  
![Рисунок 33. Режим поиска](https://i.imgur.com/UIotRdm.png)

*Рисунок 33. Режим поиска*

Написала в этой строке слово, которое нужно найти. Например. "hello" и найдем ее. (см. рис. 34-35)

![Рисунок 34. Поиск](https://i.imgur.com/QZ0s9uS.png)

*Рисунок 34. Поиск*

![Рисунок 35. Поиск](https://i.imgur.com/MynzfIT.png)

*Рисунок 35. Поиск*

Теперь найдем слово "systems". (см. рис. 36)

![Рисунок 36. Поиск](https://i.imgur.com/wOKkIvN.png)

*Рисунок 36. Поиск*

  **9.2.** Переключалась между результатами поиска, нажимая *C-s*. В результате во всех окнах выделялось слово, которое искали ранее. (см. рис. 37)
  
![Рисунок 37. Переключение между результатами поиска](https://i.imgur.com/FXuR2PT.png)

*Рисунок 37. Переключение между результами поиска*

  **9.3.** Выйшла из режима поиска, нажав *C-g*. (см. рис. 38)
  
![Рисунок 38. Выход из режима поиска](https://i.imgur.com/gvn3oay.png)

*Рисунок 38. Выход из режима поиска*

  **9.4.** Перешла в режим поиска и замены (M-%) и ввела слово, которое нужно заменит (lab10). (см. рис. 39)
  
![Рисунок 39. Режим поиска и замены. Заменяемое слово](https://i.imgur.com/Ofu0kun.png)

*Рисунок 39. Режим поиска и  замены. Заменяемое слово*

Нажав *Enter*, ввела слово, на которое нужно заменить (laboratory). (см. рис. 40)

![Рисунок 40. Режим поиска и замены. Слово, на которое заменяем](https://i.imgur.com/jl7coc2.png)

*Рисунок 40. Режим поиска и замены. Слово, на которое заменяем*

Нажала *Enter*, результаты подсвечены фиолетовым цветом. (см. рис. 41)

![Рисунок 41. Режим поиска и замены. Подсветка результатов](https://i.imgur.com/sfpTbjp.png)

*Рисунок 41. Режим поиска и замены. Подсветка результатов*

Нажала "!" для подтверждения. Слово "lab10" заменилось на "laboratory". (см. рис. 42)

![Рисунок 42. Режим поиска и замены. Замена](https://i.imgur.com/s5cDBsE.png)

*Рисунок 42. Режим поиска и замены. Замена*

  **9.5.** Попробовала другой режим поиска, нажав *M-s o*.
  
Появилась строка поиска, написала туда слово для поиска (hello). (см. рис. 43)

![Рисунок 43. Поиск](https://i.imgur.com/2KfxCGd.png)

*Рисунок 43. Поиск*

Результат: (см. рис. 44)

![Рисунок 44. Поиск](https://i.imgur.com/OdnBSot.png)

*Рисунок 44. Поиск*

Отличие этого способа от другого: в первом методе поиска находимое слово только выделялось цветом, а в этом - выделяется цветом, и показывается номер строки и сама строка, в которой находится это слово.  

***

**Вывод:** познакомилась с операционной системой Linux; получила практические навыки работы с редактором Emacs.

***

**Библиография**

[[1] - Основы работы с Emacs. Emacs для начинающих](https://docs.altlinux.org/ru-RU/archive/2.2/html-single/master/user-html/ch06s02.html)

[[2] - РУДН, Операционные ситемы, лабораторная работа: Тексовой редактор Emacs](https://esystem.rudn.ru/pluginfile.php/1142374/mod_resource/content/3/007-lab_emacs.pdf)

