---
## Front matter
title: "Лабораторная работа №10"
subtitle: "Архетиктура компьютера"
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

Приобретение навыков написания программ для работы с файлами.

# Задание



# Теоретическое введение

Права доступа к файлам
ОС GNU/Linux является многопользовательской операционной системой. И для обеспече-
ния защиты данных одного пользователя от действий других пользователей существуют
специальные механизмы разграничения доступа к файлам. Кроме ограничения доступа, дан-
ный механизм позволяет разрешить другим пользователям доступ данным для совместной
работы.
Права доступа определяют набор действий (чтение, запись, выполнение), разрешённых
для выполнения пользователям системы над файлами. Для каждого файла пользователь
может входить в одну из трех групп: владелец, член группы владельца, все остальные. Для
каждой из этих групп может быть установлен свой набор прав доступа. Владельцем файла
является его создатель. Для предоставления прав доступа другому пользователю или другой
группе командой
chown [ключи] <новый_пользователь>[:новая_группа] <файл>
или
chgrp [ключи] < новая_группа > <файл>
Набор прав доступа задается тройками битов и состоит из прав на чтение, запись и ис-
полнение файла. В символьном представлении он имеет вид строк rwx, где вместо любого
символа может стоять дефис. Всего возможно 8 комбинаций, приведенных в таблице 10.1.
Буква означает наличие права (установлен в единицу второй бит триады r — чтение, первый
бит w — запись, нулевой бит х — исполнение), а дефис означает отсутствие права (нулевое
значение соответствующего бита). Также права доступа могут быть представлены как вось-
меричное число. Так, права доступа rw- (чтение и запись, без исполнения) понимаются как
три двоичные цифры 110 или как восьмеричная цифра 6.

# Выполнение лабораторной работы

Создаю lab10/lab10-1.asm. (рис. [-@fig:001]).

![lab10/lab10-1.asm](/home/alekhin_david/work/study/2023-2024/Архитектура компьютера/arch-pc/labs/lab10/report/image/Снимок экрана от 2024-12-10 16-33-26.png){#fig:001 width=70%}

Ввожу туда текст команды 10.1. (рис. [-@fig:002]).

![10.1](/home/alekhin_david/work/study/2023-2024/Архитектура компьютера/arch-pc/labs/lab10/report/image/Снимок экрана от 2024-12-10 16-36-16.png){#fig:002 width=70%}

Компеллирую и запускаю команду, проверяю чтобы введённый текст был в нужном файле. (рис. [-@fig:003]).

![Запуск 10.1](/home/alekhin_david/work/study/2023-2024/Архитектура компьютера/arch-pc/labs/lab10/report/image/Снимок экрана от 2024-12-10 16-42-36.png){#fig:003 width=70%}

С помощью команды сhmod я запрещаю выполнять программу. Выдаёт отказ в доступе, так как я запретил запускать программу для владельца. (рис. [-@fig:004]).

![Запрет на программу](/home/alekhin_david/work/study/2023-2024/Архитектура компьютера/arch-pc/labs/lab10/report/image/Снимок экрана от 2024-12-10 16-45-32.png){#fig:004 width=70%}

С помощью команды даю разрешение на исполнение файлу с исходным текстом и перекомпелирую программу, она заработала, так как файл был со всеми разрешениями. (рис. [-@fig:005]).

![Разрешения для исходного файла](/home/alekhin_david/work/study/2023-2024/Архитектура компьютера/arch-pc/labs/lab10/report/image/Снимок экрана от 2024-12-10 16-49-55.png){#fig:005 width=70%}

Предоставляю определенные права файлу readme.txt в соответствие с вариантом 1. (рис. [-@fig:006]).

![Разрешения для файла readme.txt](/home/alekhin_david/work/study/2023-2024/Архитектура компьютера/arch-pc/labs/lab10/report/image/Снимок экрана от 2024-12-10 17-04-29.png){#fig:006 width=70%}

Предоставляю определенные права файлу readme-2.txt в соответствие с вариантом 1. (рис. [-@fig:007]).

![Разрешения для файла readme-2.txt](/home/alekhin_david/work/study/2023-2024/Архитектура компьютера/arch-pc/labs/lab10/report/image/Снимок экрана от 2024-12-10 17-38-34.png){#fig:007 width=70%}

Провожу проверку. (рис. [-@fig:008]).

![проверка](/home/alekhin_david/work/study/2023-2024/Архитектура компьютера/arch-pc/labs/lab10/report/image/Снимок экрана от 2024-12-10 17-38-47.png){#fig:008 width=70%}

Перехожу к самостоятельной работе, пишу программу для запроса имени и его вывода в файл name.txt. (рис. [-@fig:009]),  (рис. [-@fig:010]).

![имя.тхт](/home/alekhin_david/work/study/2023-2024/Архитектура компьютера/arch-pc/labs/lab10/report/image/Снимок экрана от 2024-12-10 17-45-12.png){#fig:009 width=70%}

![текст программы](/home/alekhin_david/work/study/2023-2024/Архитектура компьютера/arch-pc/labs/lab10/report/image/Снимок экрана от 2024-12-10 17-47-56.png){#fig:010 width=70%}

Запускаю программу и проверяю наличие имени. (рис. [-@fig:011]).

![Запуск](/home/alekhin_david/work/study/2023-2024/Архитектура компьютера/arch-pc/labs/lab10/report/image/Снимок экрана от 2024-12-10 17-50-51.png){#fig:011 width=70%}

# Выводы

Я приобрел навыки написания программ для работы с файлами.

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
