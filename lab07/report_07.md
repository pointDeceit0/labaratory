---
## Front matter
title: "Отчет по лабораторной работе №7"
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

Освоение основных возможностей командной оболочки Midnight Commander. Приобретение навыков практической работы по просмотру каталогов и файлов; манипуляций
с ними.

# Ход работы

1. С помощью команды:

```bash
man mc 
```

Посмотрим мануал по команде mc(Рис. 1):

![Рис. 1 man mc](screenshots/1.png)

2. С помощью команд F1-F10 просмотрим возможности mc(Рис. 2-4):

![Рис. 2 F1 - вызов контекстно-зависимой подсказки](screenshots/2.png)

![Рис. 3 F2 - вызов пользовательского меню с возможностью создания и/или дополнения дополнительных функций](screenshots/3.png)

![Рис. 4 F4 - вызов встроенного редактора mc для просмоотра содержиого файлов](screenshots/4.png)

3. С помощью клавиши ins выделим файл(выделится желтым) и с помощью повторного нажатия отменим выделение(Рис. 5, 6):

![Рис. 5 выделение файла](screenshots/5.png)

![Рис. 6 отмена выделения файла](screenshots/.png)

С помощью клавиши F5 скопируем файл test.txt в ранее созданный каталог newdir(Рис. 7):

![Рис. 7 копирование файла](screenshots/7.png)

Клавишей F6 переместим файл test.txt в каталог newdir(Рис. 8):

![Рис. 8 перемещение файла](screenshots/8.png)

В левой панели, просмотрим информацию о файле file.txt(Рис. 9):

![Рис. 9 информация о файле file.txt](screenshots/9.png)

Выполним основные действия правой панели(Рис. 10):

![Рис. 10 действия правой панели](screenshots/10.png)

Список файлов отображает размер файла и время его правки(Рис. 11):

![Рис. 11 список файлов](screenshots/11.png)

Пункт «Быстрый просмотр» нужен для предпросмотра содержания файла(Рис. 12):

![Рис. 12 быстрый просмотр](screenshots/12.png)

Пункт «Информация» отображает подробные данные о файле(Рис. 13, 14):

![Рис. 13 информация в mc](screenshots/13.png)

![Рис. 13 информация о даном файле\каталоге](screenshots/14.png)

Пункт «Дерево» необходим для просмотра дерева каталога (отображает минимум информации)(Рис. 15):

![Рис. 15 дерево каталога](screenshots/15.png)

Пункт «Формат списка» − «Укороченный» отображает только имя файла или каталога (видна минимальная информация)(Рис. 16, 17):

![Рис. 16 формат списка в(укороченный) mc](screenshots/16.png)

![Рис. 17 формат списка в(укороченный) mc](screenshots/17.png)

Пункт «Формат списка» − «Расширенный» отображает подробную информацию о файлах, но менее подробную,чем пункт «Информация»(Рис. 18):

![Рис. 18 формат списка(расширенный)](screenshots/18.png)

Пункт «Формат списка» − «Определенный пользователем» предоставляетпользователю возможность самому изменять степень подробности информации о файле, но она будет менее подробной, чем в пункте “Информация”.

Пункт «Формат списка» − «Стандартный» ставится по умолчанию(Рис. 19):

![Рис. 19 формат списка(стандартный)](screenshots/19.png)

Пункт «Порядок сортировки» необходим для сортировки файлов или каталогов по конкретному критерию(Рис. 20):

![Рис. 20 порядок соритровки](screenshots/20.png)

Пункт «Фильтр» необходим, чтобы просматривать название файлов или каталогов, которые подходят под указанную маску(Рис. 21):

![Рис. 21 фильтр](screenshots/21.png)

Пункт “Выбор кодировки” нужен для просмотра и смены кодировки(Рис. 22):

![Рис. 22 выбор кодировки](screenshots/22.png)

6. Используя возможности под меню «Файл»(Рис. 23):

![Рис. 23 файл в mc](screenshots/23.png)

![Рис. ](screenshots/.png)
