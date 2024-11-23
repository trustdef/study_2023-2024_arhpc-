---
## Front matter
title: "Отчёт по лабораторной работе №7"
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

Изучение команд условного и безусловного переходов. Приобретение навыков написания
программ с использованием переходов. Знакомство с назначением и структурой файла
листинга.

# Задание

1. Реализация переходов в NASM
2. Изучение структуры файлы листинга
3. Задание для самостоятельной работы

# Теоретическое введение

Для реализации ветвлений в ассемблере используются так называемые команды передачи
управления или команды перехода. Можно выделить 2 типа переходов:
• условный переход – выполнение или не выполнение перехода в определенную точку
программы в зависимости от проверки условия.
• безусловный переход – выполнение передачи управления в определенную точку про-
граммы без каких-либо условий.

# Выполнение лабораторной работы

Создаю папку для лабораторной работы №7, в ней создаб файл lab7-1.asm (рис. [-@fig:001]). Переношу в эту папку файл in_out.asm. (рис. [-@fig:002]).

![Создание lab07/lab7-1.asm](/home/alekhin_david/work/study/2023-2024/Архитектура компьютера/arch-pc/labs/lab07/report/image/Снимок экрана от 2024-11-23 12-16-43.png){#fig:001 width=70%}

![in_out.asm](/home/alekhin_david/work/study/2023-2024/Архитектура компьютера/arch-pc/labs/lab07/report/image/Снимок экрана от 2024-11-23 12-25-12.png){#fig:002 width=70%}

Ввожу в файл lab7-1.asm текст программы 7.1. Программа с использованием инструкции jmp. (рис. [-@fig:003]).

![Программа 7.1](/home/alekhin_david/work/study/2023-2024/Архитектура компьютера/arch-pc/labs/lab07/report/image/Снимок экрана от 2024-11-23 12-25-41.png){#fig:003 width=70%}

Компеллирую файл  и запускаю его.(рис. [-@fig:004]).

![./lab7-1](/home/alekhin_david/work/study/2023-2024/Архитектура компьютера/arch-pc/labs/lab07/report/image/Снимок экрана от 2024-11-23 12-27-58.png){#fig:004 width=70%}

Создаю файл lab7-1.2.asm с текстом команды 7.2. Программа с использованием инструкции jmp. (рис. [-@fig:005]). Компеллирую и запускаю его. (рис. [-@fig:006]).

![lab7-1.2.asm](/home/alekhin_david/work/study/2023-2024/Архитектура компьютера/arch-pc/labs/lab07/report/image/Снимок экрана от 2024-11-23 12-33-49.png){#fig:005 width=70%}

![Запуск lab7-1.2.asm ](/home/alekhin_david/work/study/2023-2024/Архитектура компьютера/arch-pc/labs/lab07/report/image/Снимок экрана от 2024-11-23 12-35-17.png){#fig:006 width=70%}

Корректирую текст клманды чтобы она выводила Сообщение №1, Сообщение №2, Сообщение №3 в обратном порядке. (рис. [-@fig:007]).Компеллирую и запускаю исправленый файл. (рис. [-@fig:008]).

![Откорректрированный lab7-1.2.asm](/home/alekhin_david/work/study/2023-2024/Архитектура компьютера/arch-pc/labs/lab07/report/image/Снимок экрана от 2024-11-23 12-40-18.png){#fig:007 width=70%}

![Запуск откорректрированного lab7-1.2.asm ](/home/alekhin_david/work/study/2023-2024/Архитектура компьютера/arch-pc/labs/lab07/report/image/Снимок экрана от 2024-11-23 12-40-32.png){#fig:008 width=70%}

Слздаю файл lab7-2.asm с текстом команды 7.3. Программа, которая определяет и выводит на экран наибольшую из 3
целочисленных переменных: A,B и C. (рис. [-@fig:009]).

![lab7-2.asm](/home/alekhin_david/work/study/2023-2024/Архитектура компьютера/arch-pc/labs/lab07/report/image/Снимок экрана от 2024-11-23 12-50-36.png){#fig:009 width=70%}

Компеллирую и запускаю lab7-2.asm. (рис. [-@fig:010]).

![Запуск lab7-2.asm](/home/alekhin_david/work/study/2023-2024/Архитектура компьютера/arch-pc/labs/lab07/report/image/Снимок экрана от 2024-11-23 12-50-52.png){#fig:010 width=70%}

Создаю и открываю листинг lab7-2.asm. (рис. [-@fig:011]).

![lab7-2.lst](/home/alekhin_david/work/study/2023-2024/Архитектура компьютера/arch-pc/labs/lab07/report/image/Снимок экрана от 2024-11-23 13-01-34.png){#fig:011 width=70%}

Расшифровка 3х строк листинга: 
1)Строка 5: Эта строка находится на 5 месте, ее адрес "00000035", Машинный код - [32300000], A dd '20' - исходный текст программы, присваивающий переменной А значение 20.
2)Строка 6: Эта строка находится на 6 месте, ее адрес "00000039", Машинный код - [35300000], A dd '50' - исходный текст программы,  присваивающий переменной B значение 50.
3)Строка 8 : Эта строка находится на 8 месте, ее адрес "00000000", Машинный код - res Ah, max resb 10 - исходный текст программы, означающий, что максимальное резервирование может быть 10 байт. (рис. [-@fig:012]).


![Расшифровка 3х строк листинга](/home/alekhin_david/work/study/2023-2024/Архитектура компьютера/arch-pc/labs/lab07/report/image/Снимок экрана от 2024-11-23 14-57-07.png){#fig:012 width=70%}

У даляю в строке mov eax, max операнду max.(рис. [-@fig:013]).

![mov eax](/home/alekhin_david/work/study/2023-2024/Архитектура компьютера/arch-pc/labs/lab07/report/image/Снимок экрана от 2024-11-23 15-27-42.png){#fig:013 width=70%}

В результате получаю ошибку при создании asm файла и lst файла (рис. [-@fig:014])., а в фай с листингом получаю ошибку в 34 строке.(рис. [-@fig:015]).

![Ошибка при создании](/home/alekhin_david/work/study/2023-2024/Архитектура компьютера/arch-pc/labs/lab07/report/image/Снимок экрана от 2024-11-23 13-39-35.png){#fig:014 width=70%}

![Ошибка в листинге](/home/alekhin_david/work/study/2023-2024/Архитектура компьютера/arch-pc/labs/lab07/report/image/Снимок экрана от 2024-11-23 13-39-09.png){#fig:015 width=70%}

Приступаю к самостоятельной работе (1 вариант). Создаю файл lab7-1s.asm и пишу код для первого задания. (рис. [-@fig:016]).

![Код 1 задания](/home/alekhin_david/work/study/2023-2024/Архитектура компьютера/arch-pc/labs/lab07/report/image/Снимок экрана от 2024-11-23 14-06-10.png){#fig:016 width=70%}

Компеллирую и запускаю lab7-1s.asm, проверяю работоспособность.(рис. [-@fig:017]).

![./lab7-1s.asm](/home/alekhin_david/work/study/2023-2024/Архитектура компьютера/arch-pc/labs/lab07/report/image/Снимок экрана от 2024-11-23 14-10-35.png){#fig:017 width=70%}

Создаю файл lab7-2s.asm и пишу код для второго задания. (рис. [-@fig:018]).

![Код 2 задания](/home/alekhin_david/work/study/2023-2024/Архитектура компьютера/arch-pc/labs/lab07/report/image/Снимок экрана от 2024-11-23 14-15-29.png){#fig:018 width=70%}

Компеллирую и запускаю lab7-2s.asm, проверяю работоспособность. (рис. [-@fig:019]).

![./lab7-2s.asm](/home/alekhin_david/work/study/2023-2024/Архитектура компьютера/arch-pc/labs/lab07/report/image/Снимок экрана от 2024-11-23 14-15-53.png){#fig:019 width=70%}





# Выводы

Сделав лабораторную работу я выполнил её главную цель: 
"Изучение команд условного и безусловного переходов. Приобретение навыков написания
программ с использованием переходов. Знакомство с назначением и структурой файла
листинга."



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
