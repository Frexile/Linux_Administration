  Лабораторная работа №1. Управление файлами и каталогами
===
***Задачи:***
---
1. Освоить основные команды для работы с файлами и каталогами (директориями).
2. Научиться использовать справочную информацию по командам.

***Подсказки:***
---
1. При выполнении работы могут использоваться следующие команды:
cat; cd; chmod, cmp; cp; diff; find; head; less; ln; ls; man; mkdir; mv; nano; patch; rm; split; vi; wc.
2. Для получения подробного справочного руководства по любой команде можно набрать в консоли «man название команды», для кратной справки – название_команды --help.
3. По умолчанию, команды выводят результаты работы в консоль. Для перенаправления стандартного вывода с консоли в файл можно использовать операторы «>» или «>>».
4. Команды могут быть собраны в конвейеры с помощью оператора «|».
5. Для удобства работы можно пользоваться одновременно несколькими консолями. На одной консоли читать справочное руководство, на другой редактировать скрипт и т.п. Переключаться между ними можно нажатием комбинации клавиш Alt+Fn, где Fn — функциональная клавиша (F1 — для первой консоли, F2- для второй и т.д.).
6. Для того чтобы было удобнее смотреть результаты выполнения тех команд, которые что-то выводят на экран можно после них вставлять в скрипт паузу (с помощью команды sleep) или ожидать нажатия Enter с помощью команды read.

***Задание:***
---
Создать скрипт (создать текстовый файл с необходимыми командами (добавив в начало #!/bin/sh), сделать его исполняемым). Создать и редактировать скрипт можно в редакторах nano или vi.
Скрипт должен выполнять следующие действия:
1. Создать каталог test в домашнем каталоге пользователя.
2. Создать в нем файл list, содержащий список всех файлов и поддиректориев каталога /etc (включая скрытые) в таком виде, что можно однозначно определить какая из записей является именем файла, а какая — названием директории.
3. Вывести в конец этого файла два числа. Сначала количество поддиректориев в каталоге /etc, а затем количество скрытых файлов в каталоге /etc.
4. Создать в каталоге test каталог links.
5. Создать в каталоге links жесткую ссылку на файл list с именем list_hlink.
6. Создать в каталоге links символическую ссылку на файл list с именем list_slink.
7. Вывести на экран количество имен (жестких ссылок) файла list_hlink, количество имен (жестких ссылок) файла list и количество имен (жестких ссылок) файла list_slink.
8. Дописать в конец файла list_hlink число строк в файле links.
9. Сравнить содержимое файлов list_hlink и list_slink. Вывести на экран YES, если файлы идентичны.
10. Переименовать файл list в list1.
11. Сравнить содержимое файлов list_hlink и list_slink. Вывести на экран YES, если файлы идентичны.
12. Создать в домашнем каталоге пользователя жесткую ссылку на файл list_link с именем list1.
13. Создать в домашнем каталоге файл list_conf, содержащий список файлов с расширением .conf, из каталога /etc и всех его подкаталогов.
14. Создать в домашнем каталоге файл list_d, содержащий список всех подкаталогов каталога /etc, расширение которых .d.
15. Создать файл list_conf_d, включив в него последовательно содержимое list_conf и list_d.
16. Создать в каталоге test скрытый каталог sub.
17. Скопировать в него файл list_conf_d.
18. Еще раз скопировать туда же этот же файл в режиме автоматического создания резервной копии замещаемых файлов.
19. Вывести на экран полный список файлов (включая все подкаталоги и их содержимое) каталога test.
20. Создать в домашнем каталоге файл man.txt, содержащий документацию на команду man.
21. Разбить файл man.txt на несколько файлов, каждый из которых будет иметь размер не более 1 килобайта.
22. Создать каталог man.dir.
23. Переместить одной командой все файлы, полученные в пункте 21 в каталог man.dir.
24. Собрать файлы в каталоге man.dir обратно в файл с именем man.txt.
25. Сравнить файлы man.txt в домашней каталоге и в каталоге man.dir и вывести YES, если файлы идентичны.
26. Добавить в файл man.txt, находящийся в домашнем каталоге несколько строчек с произвольными символами в начало файла и несколько строчек в конце файла.
27. Одной командой получить разницу между файлами в отдельный файл в стандартном формате для наложения патчей.
28. Переместить файл с разницей в каталог man.dir.
29. Наложить патч из файла с разницей на man.txt в каталоге man.dir.
30. Сравнить файлы man.txt в домашней каталоге и в каталоге man.dir и вывести YES, если файлы идентичны.

***Описание команд:***
---
* ***CAT*** - чтение данных из файла или стандартного ввода и их вывод на экран.

    `$ cat [options] file1 file2 ...`
  
    ***Основные опции:***
    ###
    * -b - нумеровать только непустые строки;
    * -E - показывать символ $ в конце каждой строки;
    * -n - нумеровать все строки;
    * -s - удалять пустые повторяющиеся строки;
    * -T - отображать табуляции в виде ^I;
    * -h - отобразить справку;
    * -v - версия утилиты.
  
* ***CD*** - встроенная команда Bash изменяет текущую папку только для оболочки, в которой выполняется.
 
    `$ cd [options] destination_directory`
    
    ***Основные опции:***
    ###
    * -P - позволяет следовать по символическим ссылкам перед тем, как будут обработаны все переходы "..";
    * -L - переходит по символическим ссылкам только после того, как были обработаны "..";
    * -e - если папку, в которую нужно перейти не удалось найти - выдает ошибку.
    
* ***CHMOD*** - используется для установки прав.  

    `$ chmod [options] rights file_path`
    
    ***Основные опции:***
    ###
    
    * -c - выводить информацию обо всех изменениях;
    * -f - не выводить сообщения об ошибках;
    * -v - выводить максимум информации;
    * --preserve-root - не выполнять рекурсивные операции для корня "/";
    * --reference - взять маску прав из указанного файла;
    * -R - включить поддержку рекурсии;
    * --version - вывести версию утилиты;

* ***CMP*** - побайтовое сравнение содержимого двух файлов.

  `$ cmp [options] file1 file2`
  
   ***Основные опции:***
   ### 
   
   * -b - отображение различных байтов
   * -i [bytes-to-skipped] - пропуск определенного количества начальных байтов из обоих файлов, а затем после пропуска сравнение файлов.
   * -l - печать позиции байта и значения байта для всех отличающихся байтов.
   * -s - сравнение двух файлов без записи каких-либо сообщений. Это дает значение выхода 0, если файлы идентичны, значение 1, если они разные, или значение 2, если появляется сообщение об ошибке.
   * -n [bytes-to-compare] - ограничить количество байтов для сравнения.
   
* ***CP*** - утилита позволяет полностью копировать файлы и директории.  

  `$ cp [options] source_file target_file`
  
  `$ cp [options] source_file target_directory/`
  
   ***Основные опции:***
   ### 
   
   * --attributes-only - не копировать содержимое файла, а только флаги доступа и владельца;
   * -f, --force - перезаписывать существующие файлы;
   * -i, --interactive - спрашивать, нужно ли перезаписывать существующие файлы;
   * -L - копировать не символические ссылки, а то, на что они указывают;
   * -n - не перезаписывать существующие файлы;
   * -P - не следовать символическим ссылкам;
   * -r - копировать папку Linux рекурсивно;
   * -s - не выполнять копирование файлов в Linux, а создавать символические ссылки;
   * -u - скопировать файл, только если он был изменён;
   * -x - не выходить за пределы этой файловой системы;
   * -p - сохранять владельца, временные метки и флаги доступа при копировании;
   * -t - считать файл-приемник директорией и копировать файл-источник в эту директорию.
  
* ***DIFF*** - построчное сравнеие файлов.

  `$ diff [options] file1 file2`
   
   ***Основные опции:***
   ### 
   
   * -q - выводить только отличия файлов;
   * -s - выводить только совпадающие части;
   * -с - выводить нужное количество строк после совпадений;
   * -u - выводить только нужное количество строк после отличий;
   * -y - выводить в две колонки;
   * -e - вывод в формате ed скрипта;
   * -n - вывод в формате RCS;
   * -a - сравнивать файлы как текстовые, даже если они не текстовые;
   * -t - заменить табуляции на пробелы в выводе;
   * -l - разделить на страницы и добавить поддержку листания;
   * -r - рекурсивное сравнение папок;
   * -i - игнорировать регистр;
   * -E - игнорировать изменения в табуляциях;
   * -Z - не учитывать пробелы в конце строки;
   * -b - не учитывать пробелы;
   * -B - не учитывать пустые строки.
   
* ***FIND*** - поиск файлов и каталогов на основе специальных условий.

  `$ find [dir] [params] criterion template [action]`
  
   ***Основные параметры:***
   ### 
   
   * -P никогда не открывать символические ссылки
   * -L - получает информацию о файлах по символическим ссылкам. Важно для дальнейшей обработки, чтобы обрабатывалась не ссылка, а сам файл.
   * -maxdepth - максимальная глубина поиска по подкаталогам, для поиска только в текущем каталоге установите 1.
   * -depth - искать сначала в текущем каталоге, а потом в подкаталогах
   * -mount искать файлы только в этой файловой системе.
   * -version - показать версию утилиты find
   * -print - выводить полные имена файлов
   * -type f - искать только файлы
   * -type d - поиск папки в Linux

   ***Основные критерии:***
   ###

   * -name - поиск файлов по имени
   * -perm - поиск файлов в Linux по режиму доступа
   * -user - поиск файлов по владельцу
   * -group - поиск по группе
   * -mtime - поиск по времени модификации файла
   * -atime - поиск файлов по дате последнего чтения
   * -nogroup - поиск файлов, не принадлежащих ни одной группе
   * -nouser - поиск файлов без владельцев
   * -newer - найти файлы новее чем указанный
   * -size - поиск файлов в Linux по их размеру
   
* ***HEAD*** - вывод начальных строк (10 по умолчанию) из одного ил нескольких файлов.

   `$ head [options] file`
   
   ***Основные опции:***
   ###
   
   * -c (--bytes) — позволяет задавать количество текста не в строках, а в байтах. При записи в виде --bytes=[-]NUM выводит на экран все содержимое файла, кроме NUM байт, расположенных в конце документа.
   * -n (--lines) — показывает заданное количество строк вместо 10, которые выводятся по умолчанию. Если записать эту опцию в виде --lines=[-]NUM, будет показан весь текст кроме последних NUM строк.
   * -q (--quiet, --silent) — выводит только текст, не добавляя к нему название файла.
   * -v (--verbose) — перед текстом выводит название файла.
   * -z (--zero-terminated) — символы перехода на новую строку заменяет символами завершения строк.
   
* ***LESS*** - позволяет перематывать текст не только вперёд, но и назад, осуществлять поиск в обоих направлениях, переходить сразу в конец или в начало файла.

  `$ less [options] file`
  
  ***Основные опции:***
  ###
  
  * -a, --search-skip-screen — не осуществлять поиск в тексте, который в данный момент отображен на экране;
  * -bn, --buffers=n — задать размер буфера памяти;
  * -c, --clear-screen — листать текст, полностью стирая содержимое экрана (построчная прокрутка работать не будет);
  * -Dxcolor, --color=xcolor — задать цвет отображаемого текста;
  * -E, --QUIT-AT-EOF — выйти, когда утилита достигнет конца файла;
  * -e, --quit-at-eof — выйти, когда утилита второй раз достигнет конца файла;
  * -F, --quit-if-one-screen — выйти, если содержимое файла помещается на одном экране;
  * -f, --force — открыть специальный файл;
  * -hn, --max-back-scroll=n — задать максимальное количество строк для прокрутки назад;
  * -yn, --max-forw-scroll=n — задать максимальное количество строк для прокрутки вперёд;
  * -i, --ignore-case — игнорировать регистр;
  * -I, --IGNORE-CASE — игнорировать регистр, даже если паттерн для поиска содержит заглавные буквы;
  * -jn, --jump-target=n — указать, в какой строке должна быть выведена искомая информация;
  * -J, --status-column — пометить строки, соответствующие результатам поиска;
  * -n, --line-numbers — не выводить номера строк;
  * -N, --LINE-NUMBERS — вывести номера строк;
  * -s, --squeeze-blank-lines — заменить множество идущих подряд пустых строк одной пустой строкой;
  * -w, --hilite-unread — выделить первую строку нового фрагмента текста.  
  
* ***LN*** - утилита для создания ссылок.
  
  ***Особенности символических ссылок:***
  ###

  * Могут ссылаться на файлы и каталоги;
  * После удаления, перемещения или переименования файла становятся недействительными;
  * Права доступа и номер inode отличаются от исходного файла;
  * При изменении прав доступа для исходного файла, права на ссылку останутся неизменными;
  * Можно ссылаться на другие разделы диска;
  * Содержат только имя файла, а не его содержимое.
  
  ***Особенности жестких ссылок:***
  ###
  
  * Работают только в пределах одной файловой системы;
  * Нельзя ссылаться на каталоги;
  * Имеют ту же информацию inode и набор разрешений что и у исходного файла;
  * Разрешения на ссылку изменяться при изменении разрешений файла;
  * Можно перемещать и переименовывать и даже удалять файл без вреда ссылке.

  `$ ln [options] source_file link_file`

  ***Основные опции:***
  ###
  
  * -d - разрешить создавать жесткие ссылки для директорий суперпользователю;
  * -f - удалять существующие ссылки;
  * -i - спрашивать нужно ли удалять существующие ссылки;
  * -P - создать жесткую ссылку; (для создания жесктой ссылки можно вызвать утилиту без параметров)
  * -r - создать символическую ссылку с относительным путем к файлу;
  * -s - создать символическую ссылку.
  
* ***PATCH*** - наложение патча.

  `$ patch [options] original_file patch_file`

  ***Основные опции:***
  ###
  
  * -i - читает информацию из патч-файла, указываемого параметром patchfile.
  * -R - откатывает все изменения (если они возможны), т. е. отменяет установку патча.
  * -с - интерпретирует файл патча как обычный контекстный формат, генерируемый утилитой diff.
  * -b - cоздаёт резервную копию оригинального файла вместо его удаления.
  
* ***SPLIT*** разбиение файла на несколько меньших. Работает как с текстовыми, так и с бинарными файлами.

  `$ split [options] file`

  ***Основные опции:***
  ###

  * -b, --bytes=SIZE - задает размер выводимых файлов.
  * -d, --numeric-suffixes - использовать цифровые суффиксы вместо алфавитных
  * -n, --number=CHUNKS - задает количество выводимых файлов

* ***WC*** - считает количество строк/слов в тексте
  
  ***Основные опции:***
  ###
  
  * -c - Отобразить размер объекта в байтах
  * -m - Показать количесто символов в объекте
  * -l - Вывести количество строк в объекте
  * -w - Отобразить количество слов в объекте
