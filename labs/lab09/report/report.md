---
## Front matter
title: "Отчёт по лабораторной работе №9"
subtitle: "Архитектура компьютера"
author: "Алехин Давид Андреевич"

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
mainfont: IBM Plex Serif
romanfont: IBM Plex Serif
sansfont: IBM Plex Sans
monofont: IBM Plex Mono
mathfont: STIX Two Math
mainfontoptions: Ligatures=Common,Ligatures=TeX,Scale=0.94
romanfontoptions: Ligatures=Common,Ligatures=TeX,Scale=0.94
sansfontoptions: Ligatures=Common,Ligatures=TeX,Scale=MatchLowercase,Scale=0.94
monofontoptions: Scale=MatchLowercase,Scale=0.94,FakeStretch=0.9
mathfontoptions:
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

Приобретение навыков написания программ с использованием подпрограмм. Знакомство с методами отладки при помощи GDB и его основными возможностями.

# Задание



# Теоретическое введение

Отладка — это процесс поиска и исправления ошибок в программе. В общем случае его
можно разделить на четыре этапа:
• обнаружение ошибки;
• поиск её местонахождения;
• определение причины ошибки;
• исправление ошибки.
Можно выделить следующие типы ошибок:
• синтаксические ошибки — обнаруживаются во время трансляции исходного кода и
вызваны нарушением ожидаемой формы или структуры языка;
• семантические ошибки — являются логическими и приводят к тому, что программа
запускается, отрабатывает, но не даёт желаемого результата;
• ошибки в процессе выполнения — не обнаруживаются при трансляции и вызывают пре-
рывание выполнения программы (например, это ошибки, связанные с переполнением
или делением на ноль).
Второй этап — поиск местонахождения ошибки. Некоторые ошибки обнаружить доволь-
но трудно. Лучший способ найти место в программе, где находится ошибка, это разбить
программу на части и произвести их отладку отдельно друг от друга.
Третий этап — выяснение причины ошибки. После определения местонахождения ошибки
обычно проще определить причину неправильной работы программы.
Последний этап — исправление ошибки. После этого при повторном запуске программы,
может обнаружиться следующая ошибка, и процесс отладки начнётся заново.

# Выполнение лабораторной работы

Создаю lab09/lab9-1.asm. (рис. [-@fig:001]).

![lab09/lab9-1.asm](/home/alekhin_david/work/study/2023-2024/Архитектура компьютера/arch-pc/labs/lab09/report/image/Снимок экрана от 2024-12-04 16-06-39.png){#fig:001 width=70%}

Вставляю туда Листинг 9.1, компаную и запускаю. (рис. [-@fig:002]).

![Листинг 9.1](/home/alekhin_david/work/study/2023-2024/Архитектура компьютера/arch-pc/labs/lab09/report/image/Снимок экрана от 2024-12-04 16-14-41.png){#fig:002 width=70%}

Изменяю текст программы, чтобы она решала выражение f(g(x)) и запускаю. (рис. [-@fig:003]), (рис. [-@fig:004]).

![Изменённый 9.1](/home/alekhin_david/work/study/2023-2024/Архитектура компьютера/arch-pc/labs/lab09/report/image/Снимок экрана от 2024-12-04 16-34-46.png){#fig:003 width=70%}

![./9.1 изменённый](/home/alekhin_david/work/study/2023-2024/Архитектура компьютера/arch-pc/labs/lab09/report/image/Снимок экрана от 2024-12-04 16-35-22.png){#fig:004 width=70%}

Создаю файл вписываю туда текст Листинг 9.2, компаную и запускаю через отладчик. (рис. [-@fig:005]).

![Отладка 9.2](/home/alekhin_david/work/study/2023-2024/Архитектура компьютера/arch-pc/labs/lab09/report/image/Снимок экрана от 2024-12-04 16-43-27.png){#fig:005 width=70%}

Запускаю 9.2 через отладчик. (рис. [-@fig:006]).

![./9.2 через отладчик](/home/alekhin_david/work/study/2023-2024/Архитектура компьютера/arch-pc/labs/lab09/report/image/Снимок экрана от 2024-12-04 16-43-57.png){#fig:006 width=70%}

Ставлю брекпоинт на метку _start и запустил программу. (рис. [-@fig:007]).

![Брекпоинт на метку _start](/home/alekhin_david/work/study/2023-2024/Архитектура компьютера/arch-pc/labs/lab09/report/image/Снимок экрана от 2024-12-04 16-45-26.png){#fig:007 width=70%}

Смотрю дисассимплированный код программы начиная с метки. (рис. [-@fig:008]).

![Дисассимплированный код](/home/alekhin_david/work/study/2023-2024/Архитектура компьютера/arch-pc/labs/lab09/report/image/Снимок экрана от 2024-12-04 16-46-28.png){#fig:008 width=70%}

С помощью команды я переключился на intel’овское отображение синтаксиса. Отличие заключается в командах, в диссамилированном отображении в командах используют % и $, а в Intel отображение эти символы не используются. (рис. [-@fig:009]).

![Intel’овское отображение](/home/alekhin_david/work/study/2023-2024/Архитектура компьютера/arch-pc/labs/lab09/report/image/Снимок экрана от 2024-12-04 16-47-15.png){#fig:009 width=70%}

Включаю режим псевдографики. (рис. [-@fig:010]).

![Псевдографика](/home/alekhin_david/work/study/2023-2024/Архитектура компьютера/arch-pc/labs/lab09/report/image/Снимок экрана от 2024-12-04 16-49-41.png){#fig:010 width=70%}

Смотрю наличие брейкпоинтов. (рис. [-@fig:011]).

![Смотрю наличие брейкпоинтов](/home/alekhin_david/work/study/2023-2024/Архитектура компьютера/arch-pc/labs/lab09/report/image/Снимок экрана от 2024-12-04 16-53-02.png){#fig:011 width=70%}

Добавляю метку на предпоследнюю строку. (рис. [-@fig:012]).

![Добавляю метку](/home/alekhin_david/work/study/2023-2024/Архитектура компьютера/arch-pc/labs/lab09/report/image/Снимок экрана от 2024-12-05 17-17-46.png){#fig:012 width=70%}

С помощью команды si просматриваю регистры. (рис. [-@fig:013]).

![Просмотр регистров](/home/alekhin_david/work/study/2023-2024/Архитектура компьютера/arch-pc/labs/lab09/report/image/Снимок экрана от 2024-12-07 12-08-44.png){#fig:013 width=70%}

С помощью команды смотрю значение переменной msg1. (рис. [-@fig:014]).

![Просмотр значения переменной](/home/alekhin_david/work/study/2023-2024/Архитектура компьютера/arch-pc/labs/lab09/report/image/Снимок экрана от 2024-12-07 12-09-36.png){#fig:014 width=70%}

Просматриваю значение второй переменной msg2. (рис. [-@fig:015]).

![Значение переменной msg2](/home/alekhin_david/work/study/2023-2024/Архитектура компьютера/arch-pc/labs/lab09/report/image/Снимок экрана от 2024-12-07 12-11-11.png){#fig:015 width=70%}

С помощью команды set меняю значение переменной msg1. (рис. [-@fig:016]).

![Изменение значения переменной](/home/alekhin_david/work/study/2023-2024/Архитектура компьютера/arch-pc/labs/lab09/report/image/Снимок экрана от 2024-12-07 12-13-49.png){#fig:016 width=70%}

Я изменяю переменную msg2. (рис. [-@fig:017]).

![Изменение msg2](/home/alekhin_david/work/study/2023-2024/Архитектура компьютера/arch-pc/labs/lab09/report/image/Снимок экрана от 2024-12-07 12-23-08.png){#fig:017 width=70%}

Вывожу значение регистров ecx и eax. (рис. [-@fig:018]).

![Значение регистров ecx и eax](/home/alekhin_david/work/study/2023-2024/Архитектура компьютера/arch-pc/labs/lab09/report/image/Снимок экрана от 2024-12-07 12-25-38.png){#fig:018 width=70%}

Меняю значение регистра ebx. Команда выводит два разных значения так как в первый раз мы вносим значение 2, а во второй раз регистр равен двум. (рис. [-@fig:019]).

![Меняю значение регистров ebx](/home/alekhin_david/work/study/2023-2024/Архитектура компьютера/arch-pc/labs/lab09/report/image/Снимок экрана от 2024-12-07 12-27-53.png){#fig:019 width=70%}

Копирую файл lab8-2.asm и запускаю в отладчике. (рис. [-@fig:020]).

![Запуск файла в отладчике](/home/alekhin_david/work/study/2023-2024/Архитектура компьютера/arch-pc/labs/lab09/report/image/Снимок экрана от 2024-12-07 12-42-46.png){#fig:020 width=70%}

Ставлю метку на _start и запускаю файл. (рис. [-@fig:021]).

![Запуск файла lab10-3 через метку](/home/alekhin_david/work/study/2023-2024/Архитектура компьютера/arch-pc/labs/lab09/report/image/Снимок экрана от 2024-12-07 12-44-36.png){#fig:021 width=70%}

Проверяю адрес вершины стека. (рис. [-@fig:022]).

![Адрес вершины стека](/home/alekhin_david/work/study/2023-2024/Архитектура компьютера/arch-pc/labs/lab09/report/image/Снимок экрана от 2024-12-07 12-45-09.png){#fig:022 width=70%}

Я смотрю все позиции стека. Элементы расположены с интервалом в 4 единицы, так как стек может хранить до 4 байт, и для того чтобы данные сохранялись нормально и без помех, компьютер использует новый стек для новой информации.(рис. [-@fig:023]).

![Все позиции стека](/home/alekhin_david/work/study/2023-2024/Архитектура компьютера/arch-pc/labs/lab09/report/image/Снимок экрана от 2024-12-07 12-46-47.png){#fig:023 width=70%}

Перехожу к самостоятельной работе. Преобразую программу из лабораторной работы №8 и реализую вычисления как подпрограмму. Запускаю. (рис. [-@fig:024]), (рис. [-@fig:025]).

![Текст программы](/home/alekhin_david/work/study/2023-2024/Архитектура компьютера/arch-pc/labs/lab09/report/image/Снимок экрана от 2024-12-07 14-15-30.png){#fig:024 width=70%}

![Запуск программы](/home/alekhin_david/work/study/2023-2024/Архитектура компьютера/arch-pc/labs/lab09/report/image/Снимок экрана от 2024-12-07 14-18-29.png){#fig:025 width=70%}

Копирую программу и запускаю, плучается арифметическая ошибка.(рис. [-@fig:026]).

![Запуск программы](/home/alekhin_david/work/study/2023-2024/Архитектура компьютера/arch-pc/labs/lab09/report/image/Снимок экрана от 2024-12-07 14-24-37.png){#fig:026 width=70%}

Запускаю программу в отладчике. (рис. [-@fig:027]).

![Запуск программы в отладчике](/home/alekhin_david/work/study/2023-2024/Архитектура компьютера/arch-pc/labs/lab09/report/image/Снимок экрана от 2024-12-07 14-30-49.png){#fig:027 width=70%}

Анализирую регистры, некоторые из них стоят не на своих местах. (рис. [-@fig:028]).

![Анализ регистров](/home/alekhin_david/work/study/2023-2024/Архитектура компьютера/arch-pc/labs/lab09/report/image/Снимок экрана от 2024-12-07 14-34-48.png){#fig:028 width=70%}

Исправляю ошибки и запускаю пргораммы, получаем верный результат. (рис. [-@fig:029]).

![Запуск](/home/alekhin_david/work/study/2023-2024/Архитектура компьютера/arch-pc/labs/lab09/report/image/Снимок экрана от 2024-12-07 14-39-52.png){#fig:029 width=70%}



# Выводы

Я приобрел навыки написания программ использованием подпрограмм. Обучился отладке программ.

# Список литературы{.unnumbered}

1. GDB: The GNU Project Debugger. — URL: https://www.gnu.org/software/gdb/.
2. GNU Bash Manual. — 2016. — URL: https://www.gnu.org/software/bash/manual/.
3. Midnight Commander Development Center. — 2021. — URL: https://midnight-commander.
org/.
4. NASM Assembly Language Tutorials. — 2021. — URL: https://asmtutor.com/.
5. Newham C. Learning the bash Shell: Unix Shell Programming. — O’Reilly Media, 2005. —
354 с. — (In a Nutshell). — ISBN 0596009658. — URL: http://www.amazon.com/Learning-
bash-Shell-Programming-Nutshell/dp/0596009658.
6. Robbins A. Bash Pocket Reference. — O’Reilly Media, 2016. — 156 с. — ISBN 978-1491941591.
7. The NASM documentation. — 2021. — URL: https://www.nasm.us/docs.php.
8. Zarrelli G. Mastering Bash. — Packt Publishing, 2017. — 502 с. — ISBN 9781784396879.
9. Колдаев В. Д., Лупин С. А. Архитектура ЭВМ. — М. : Форум, 2018.
10. Куляс О. Л., Никитин К. А. Курс программирования на ASSEMBLER. — М. : Солон-Пресс,
2017.
11. Новожилов О. П. Архитектура ЭВМ и систем. — М. : Юрайт, 2016.
12. Расширенный ассемблер: NASM. — 2021. — URL: https://www.opennet.ru/docs/RUS/nasm/.
13. Робачевский А., Немнюгин С., Стесик О. Операционная система UNIX. — 2-е изд. — БХВ-
Петербург, 2010. — 656 с. — ISBN 978-5-94157-538-1.
14. Столяров А. Программирование на языке ассемблера NASM для ОС Unix. — 2-е изд. —
М. : МАКС Пресс, 2011. — URL: http://www.stolyarov.info/books/asm_unix.
15. Таненбаум Э. Архитектура компьютера. — 6-е изд. — СПб. : Питер, 2013. — 874 с. —
(Классика Computer Science).
16. Таненбаум Э., Бос Х. Современные операционные системы. — 4-е изд. — СПб. : Питер,
2015. — 1120 с. — (Классика Computer Science).
