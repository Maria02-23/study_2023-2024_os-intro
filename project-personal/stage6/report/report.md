---
## Front matter
title: "Отчёт к 6 этапу индивидуального проекта"
subtitle: "Создание сайта-визитки"
author: "Четвергова М.В."

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

Размещение двуязычного сайта на Github. Сайт должен поддерживать как русский, так и английский языки.

# Задание


1. Сделать поддержку английского и русского языков.
2. Разместить элементы сайта на обоих языках.
3. Разместить контент на обоих языках.
4. Сделать пост по прошедшей неделе.
5. Добавить пост на тему по выбору (на двух языках).

# Выполнение лабораторной работы


## 1. Настройка Английского языка на сайте
В первой части выполнения я настроила поддержку английского языка на сайте. 
Для этого перейдём в каталог под адресом work/site_name/config/__default/

В этом каталоге находятся несколько текстовых файлов, отвечающих за возможности сайта. Нам нужно изменить настройки в языке, поэтому нам понадобиться изменить только два из них: 
hugo.yaml и languages.yaml

![ Каталог с необходимыми файлами ](image/1.jpg){#fig:001 width=70%}


Сначала изменим файл languages.yaml . Для этого переходим в него и переписываем ряд строк. 
Скрипт файла - на скриншоте ниже. Мы изменили несколько строк и позволили программе переводить разделы сайта на английский.

![ Изменение поддержки языка на страницах сайта в файле languages.yaml ](image/2.1.jpg){#fig:002 width=70%}

После этого сохраняем изменения и открываем файл hugo.yaml и немного меняем скрипт файла. 
Результат на скриншоте:

![ Изменение скрипта в файле hugo.yaml ](image/2.2.jpg){#fig:003 width=70%}

Отлично! Мы настроили поддержку английского языка и русского языка. Теперь переходим ко второй части этапа - написанию постов.

## 2. Написание постов

В этом этапе мы напишем два поста: пост по прошедшей неделе и "Легковесные языки разметки"

Для начала сохраняем изменения предыдущего этапа и переходим в директорию по адресу site_name/content/post.

Там создаём нужные папки для постов и переименовываем их в название поста.

![ Директория я постами ](image/3.jpg){#fig:004 width=70%}

Первым делом заполним пост по прошедшей неделе. Переходим в файл index.md соответствующего каталога и пишем пост на русском языке

![ Пост по прошедшей неделе ](image/4.jpg){#fig:005 width=70%}

А затем - на английском

![ Пост по прошедшей неделе на английском языке ](image/5.jpg){#fig:006 width=70%}

Сохраняем изменения и выходим из данного каталога. Далее переходим в каталог, посвященный "Легковесным языкам разметки".
Там также заполняем пост на русском

![ Пост на тему "Легковесные языки разметки"](image/6.jpg){#fig:007 width=70%}

И на английском языке:

![ Пост на тему "Легковесные языки разметки" на английском ](image/7.jpg){#fig:008 width=70%}

Сохраняем изменения и отправляем их на гитхаб с помощью команд git add/commit/push.

На этом выполнение 6 этапа проекта подходит к концу.

# Выводы

В ходе выполнения 6 этапа индивидуального проекта по созданию сайта-визитки, мы заполнили оставшиесы разделы сайта и 
настроили его так, чтобы помимо русского языка на нём поддерживался и английский. Таким образом мы выполнили все поставленные задачи: 
Сделали поддержку английского и русского языка, разместили элементы сайта на обоих языках, сделали пост по прошежшей неделе и добавили пост на тему "Легковесные языки разметки". 
Мы не только приобрели важные теоретические навыки по работе с ОС Линукс, но и закрепили их на практике.


::: {#refs}
:::
