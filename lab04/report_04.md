---
## Front matter
title: "Отчет по лабораторной работе №4"
subtitle: "Дисциплина: операционные системы"
author: "Королев Федор Константинович"

## Generic otions
lang: ru-RU
toc-title: "Содержание"

## Bibliography
bibliography: bib/cite.bib
csl: pandoc/csl/gost-r-7-0-5-2008-numeric.csl

## Pdf output format
toc: true # Table of contents
toc-depth: 2
lof: true # List of figures
lot: true # List of tables
fontsize: 12pt
linestretch: 1.5
papersize: a4
documentclass: scrreprt
## I18n polyglossia
polyglossia-lang:
  name: russian
  options:
	- spelling=modern
	- babelshorthands=true
polyglossia-otherlangs:
  name: english
## I18n babel
babel-lang: russian
babel-otherlangs: english
## Fonts
mainfont: PT Serif
romanfont: PT Serif
sansfont: PT Sans
monofont: PT Mono
mainfontoptions: Ligatures=TeX
romanfontoptions: Ligatures=TeX
sansfontoptions: Ligatures=TeX,Scale=MatchLowercase
monofontoptions: Scale=MatchLowercase,Scale=0.9
## Biblatex
biblatex: true
biblio-style: "gost-numeric"
biblatexoptions:
  - parentracker=true
  - backend=biber
  - hyperref=auto
  - language=auto
  - autolang=other*
  - citestyle=gost-numeric
## Pandoc-crossref LaTeX customization
figureTitle: "Рис."
tableTitle: "Таблица"
listingTitle: "Листинг"
lofTitle: "Список иллюстраций"
lotTitle: "Список таблиц"
lolTitle: "Листинги"
## Misc options
indent: true
header-includes:
  - \usepackage{indentfirst}
  - \usepackage{float} # keep figures where there are in the text
  - \floatplacement{figure}{H} # keep figures where there are in the text
---

# Цель работы

Приобретение практических навыков взаимодействия пользователя с системой посредством командной строки

# Ход работы

Будем пользоваться дистрибутивом fedora, установленным на Virtual Box(Рис. 1)

![Рис. 1 Дистрибутив fedora](screenshots/1.png)

1. Узнаем полный путь домашнего каталога(Рис. 2)

![Рис. 2 Полный путь к домашнему каталогу](screenshots/2.png)

2.1 Перейдем в каталог /tmp(Рис. 3)

![Рис. 3 каталог /tmp](screenshots/3.png)

2.2 Выведем содержимое директории с различными опциями(Рис. 4 и Рис. 5)

![Рис. 4 вывод содержимого при ls](screenshots/4.png)

![Рис. 5 вывод содержимого при ls -all](screenshots/5.png)

Различие ls и ls -all в том, что при ls -all выводится вся информация о файле: права доступа, место, размер, время и дата создания.

2.3 Посмотрим есть ли в каталоге /var/spool подкаталог cron(Рис. 6) - подкаталога нет.

![Рис. 6 подкаталог cron не существует](screenshots/6.png)

2.4 Перейдем в домашний католог и с помощью команды ls -author посмотрим, кто является владельцем файлов и каталогов(Рис. 7)

![Рис. 7 владельцы файлов и каталогов](screenshots/7.png)

Владельцами файлов и каталогов являются root или сам пользователь

3.1, 3.2 В домашнем каталоге создадим новый каталог с именем newdir, в newdir создадим подкаталог morefun(Рис. 8)

![Рис. 8 создание каталога newdir и подкаталога morefun в нём](screenshots/8.png)

3.3 В домашнем каталоге одной командой создадим подкаталоги letters, memos, misk. Затем удалим их одной командой(Рис. 9)

![Рис. 9 Создание и удаление каталогов одной командой](screenshots/9.png)

3.4, 3.5 Попробуем удалить каталог newdir(Рис. 10). Попробуем удалить подкаталог morefun каталога newdir(Рис. 10)

![Рис. 10 попытка удалить каталог newdir и подкаталог morefun](screenshots/10.png)

Каталоги не удаляются, так как это директории и для них нужна дополнительная опция -r: rm -r directory

4. С помощью команды смотрим man ls: как посмотреть содержимое подкатологов с помощью команды ls(Рис. 11)

![Рис. 11 man ls](screenshots/11.png)

Определяем, что содержимое подкаталогов можно посмотреть с помощью опции --recursive(Рис. 12)

![Рис. 12 смотрим содержимое подкаталогов](screenshots/12.png)

5. С помощью команды man ls, находим как посмотреть содержимое каталога и его подкаталогов с подробным описанием и выведенное в порядке последнего изменения(Рис. 13)

![Рис. 13 man ls](screenshots/13.png)

```bash
ls --time atime --recursive -all
```

Смотрим содержимое каталога и его подктаталогов с подробным описанием, отсортированное в порядке последнего изменения(Рис. 14), список не полный, т.к. очень большой

![Рис. 14 содержимое каталога и его подкаталогов с подробным описанием, отсортированное в порядке последнего изменения](screenshots/14.png)

6.
cd(Рис. 15): 

- -p - позволяет следовать по символическим ссылкам перед тем, как будут обработаны все переходы ".."

- -l - переходит по символическим ссылкам после того, как были обработаны переходы ".."

![Рис. 15 опции cd](screenshots/15.png)

pwd(Рис. 16):

- -l - брать директорию из переменной окружения, даже если она содержит символические ссылки

- -p - отбрасывать все символические ссылки

![Рис. 16 опции pwd](screenshots/16.png)

mkdir(Рис. 17):

- -m - назначить права доступа -rwx

- -p - не показывать ошибки, а также игнорировать их

![Рис. 17 опции mkdir](screenshots/17.png)

rmdir(Рис. 18):

- -p - позволяет удалить папки через командную строку, а также её родительские каталоги

- -v - выводит диагностический текст для каждого обработанного диалога

![Рис. 18 опции rmdir](screenshots/18.png)

rm(Рис. 19):

- -r - рекурсивно удаляет каталоги и их содержимое

- -d - удаляет пустой каталог

![Рис. 19 опции rm](screenshots/19.png)

7. С поощью команды history выведем список прошлых команд(Рис. 20)

![Рис. 20 список прошлых команд](screenshots/20.png)

И исполним несколько команд(Рис. 21)

![Рис. 21 исполнение команд pwd, ls и rm newdir с помощью history](screenshots/21.png)

# Вывод
В ходе данной лабораторной работы я научился работать с начальными командами консоли Linux.

# Контрольные вопросы 

1). Компьютерный терминал — устройство ввода–вывода, основные функции которого заключаются в вводе и отображении данных.
У компьютерного терминала есть преимущества перед графическим интерфейсом:
— снижение начальных затрат на приобретение персональных компьютеров, поскольку требования к их конфигурации минимальны, а тонкие клиенты производятся без встроенных носителей информации.
— унификация – все терминалы имеют одинаковый набор программного обеспечения.
— простота первоначального внедрения – нет необходимости настраивать каждый персональный компьютер в отдельности, присутствует централизованное управление информационным процессом.
— экономия времени системного администратора. Все тонкие клиенты абсолютно одинаковы, вероятность поломок сведена к минимуму, а программное обеспечение установлено только на сервере.
— масштабируемость. Созданный единожды образ системы для работы всей группы пользователей позволяет при минимальных затратах поддерживать легко масштабируемую сеть. Возможно быстрое создание любого количества новых рабочих мест.
— безопасность и отказоустойчивость. Компьютерный терминал, загружаясь, получает операционную систему «от производителя», настройка которой осуществляется только отделом информационной поддержки. Все модификации операционной системы и прикладных программ никак не влияют ни на других пользователей, ни на образ, хранящийся на сервере. Вся пользовательская информация хранится на сервере и регулярно резервируется, что увеличивает отказоустойчивость.
— защита от утечек информации – нет локальных носителей – нет возможности делать копии документов на съемные носители информации.

2). Входное имя пользователя (Login) —название учётной записи пользователя. Входному имени пользователя ставится в соответствиевнутренний идентификатор пользователя в системе (User ID,UID) — положительное целое число в диапазоне от 0 до65535, по которому в системе однозначно отслеживаются действия пользователя.

3). Учётные записи пользователей хранятся в файле/etc/passwd,который имеет следу-ющую структуру:login:password:UID:GID:GECOS:home:shell .
Например,учётные записи пользователейrootиivanв файле/etc/passwdмогутбыть записаны следующим образом:root:x:0:0:root:/root:/bin/bashivan:x:1000:100::/home/ivan:/bin/bash .

4). Начиная с версии 4.6, настройки рабочей среды хранятсяв реестреx fconf.

5). В многопользовательской модели пользователи делятся напользователей с обычными правамии администраторов. Входному имени пользователя ставится в соответствие внутренний идентификатор пользователя в системе (User ID,UID) — положительное целое число в диапазоне от 0 до 65535, по которому в системе однозначно отслеживаются действия пользователя.

6). Полномочия пользователей с административными правами обычно не ограничены. В многопользовательской модели пользователи делятся напользователей с обычными правамии администраторов. Пользователь с обычными правами может производить действия с элементами операционной системы только в рамках выделенного ему пространства и ресурсов, не влияя на жизнеспособность самой операционной системыи работу других пользователей. 

7). Процедура регистрации в системе обязательна для Linux. Каждый пользователь операционный системы имеет определенные ограничения на возможные с его стороны действия: чтение, изменение, запуск файлов,а так же на ресурсы: пространствона файловой системе, процессорное время для выполнение текущих задач (процессов).При этом действия одного пользователя не влияютна работу другого.Такая модель разграничения доступа к ресурсам операционной системы получила название многопользовательской.

8). Учётная запись пользователя содержит:
–входное имя пользователя (Login Name);
–пароль (Password);
–внутренний идентификатор пользователя (User ID);
–идентификатор группы (Group ID);
–анкетные данные пользователя (General Information);
-домашний каталог (Home Dir);
–указатель на программную оболочку (Shell).

9). Входному имени пользователя ставится в соответствиевнутренний идентификатор пользователя в системе (User ID,UID) — положительное целое число в диапазоне от 0 до65535, по которому в системе однозначно отслеживаются действия пользователя.
Пользователю можетбыть назначена определенная группа для доступа к некоторымресурсам, разграничения прав доступа к различным файлам и директориям. Каждаягруппа пользователей в операционной системе имеетсвой идентификатор—Group ID(GID).

10). Анкетные данные пользователя (General Information или GECOS) являются необязательным параметром учётной записи и могут содержать реальное имя пользователя (фамилию,имя),адрес,телефон.

11). Для каждого пользователя организуется домашний каталог, где хранятся его данныеи настройки рабочей среды.
В домашнем каталоге пользователя хранятся данные (файлы) пользователя,настройки рабочего стола и других приложений. Содержимое домашнего каталога обычно недоступно другим пользователям с обычными правами и не влияет на работу и настройки рабочей среды других пользователей. 

12). Мой домашний каталок: /afs/.dk.sci.pfu.edu.ru/home/t/b/tbkonovalova (узнаём с помощью команды pwd)

13). Администратор имеет возможность изменить содержимое домашнего каталогапользователя.






