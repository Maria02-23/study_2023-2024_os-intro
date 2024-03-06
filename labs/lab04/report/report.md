---
## Front matter
title: "Отчёт к лабораторной работе №4"
subtitle: "Продвинутое использование git"
author: "Четвергова Мария Викторовна"

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

Целью работы является получение навыков правильной работы с репозиториями git.

# Задание

- Выполнить работу для тестового репозитория.
- Преобразовать рабочий репозиторий в репозиторий с git-flow и  convertional commits.


# Выполнение лабораторной работы

## Установка программного обеспечения 
установим git-flow на ОС Linux. Для этого необходимо установим программное обеспечение из коллекции *Copr*

*dnf install nodejs*
*dnf install gitflow*

![ Установка пакетов nodejs и gitflow из коллекции Copr ](image/1.png){#fig:001 width=50%}

Далее установим Node.js
Установим пакет nodejs  через командную строки с помощью команд

*dnf install nodejs*
*apt-get install pnpm*

![ установим Node.js ](image/2.png){#fig:002 width=50%}

Теперь настроим node.js:
Для работы с Node.js добавим каталог с исполняемыми файлами, устанавливаемыми yarn, в переменную PATH.
Запустим pnpm, перелогинемся и выполним:


![ Добавим каталог с исполняемыми файлами ](image/3.png){#fig:003 width=50%}

## Общепринятые коммиты. 

1. commitizen
- используется для помощи в форматировании коммитов.
- При этом устанавливается скрипт   git-cz, который мы и будем использовать для коммитов.

![ commitizen ](image/4.png){#fig:004 width=50%}

2. standard-changelog
- используется для помощи в создании логов.

![ commitizen ](image/5.png){#fig:005 width=50%}

3. Практический сценарий  использования git 

	1. Создание репозитория git
	1. Подключение репозитория  к github
	-Создать репозиторий на гитхаб
	- Делаем первый коммит 

![ Подключение репозитория  к github ](image/6.png){#fig:006 width=50%} 

	2. Конфигурация обзепринятых коммитов
	- конфигурация для пакетов Node.js
	
	*pnpm init*
	
	необходимо заполнить несколько параметров пакета.
	--Название пакета
	--Лицензия пакета
	В конечном счёте файл package.json  приобретает следующий вид:

![ Конфигурация обзепринятых коммитов ](image/7.png){#fig:007 width=50%} 

- Добавим новые файлы, выполним коммит и отправим на гитхаб:


![ ](image/8.png){#fig:008 width=50%} 

3. Конфигурация git-flow
- Инициализируем git-flow через команду 

*git flow init*

Префикс для ярлыков установим в v.

- Проверим, что мы на ветке develop

- Загрузим весь репозиторий в хранилище  через номанду *git push --all*
- Установим внещнюю ветку как вышестоящую для этой ветки
- Создадим релиз с версией 1.0.0 и создадим журнал изменений
- Зальём релизную ветку в основную ветку, отправим данные на гитхаб и создадим релиз на гитхаб


![ выполнение вышеприведённых программ ](image/9.png){#fig:009 width=50%} 

2. Работа с репозиторием git
- создадим релиз с версией 1.2.3 и укажем эту новую версию в package.json


![  создание релиза новой версии ](image/10.png){#fig:010 width=50%} 

- создадим журнал изменений и добавим его в индекс


![ создание журнала изменений ](image/11.png){#fig:011 width=50%} 

- Зальём релизную ветку в основную ветку и отправим данные на гитхаб

![ заливаем релизную ветку в основную ветку ](image/12.png){#fig:012 width=50%} 

- В конце создадим релиз на github  с комментариями из журнала изменений	

![ Создадим релиз на гитхаб с комментариями из журнала ](image/13.png){#fig:013 width=50%}

# Выводы

В ходе выполнения лабораторной работы №4 Мы приобрали ценные знания и навыки по продвинутому использованию системы git.

# Список литературы{.unnumbered}

::: {#refs}
:::
