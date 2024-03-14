---
## Front matter
title: "Отчёт к лабораторной работе №5"
subtitle: "Менеджер паролей pass"
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
Целью лаборатоной работы №5 является освоение навыков работы с менеджером паролей pass и изучение операционной системы  Linux. 

# Задание

- Установить и настроить менеджер паролей pass.
- Изучить управление файлами конфигурации.
- установить и подключить необходимое программное обеспечение.


# Выполнение лабораторной работы

## Менеджер паролей pass

1. Установка

Установим менеджер паролей на ОС Fedora с помощью команд

*sudo dnf install pass pass-otp*
*sudo dnf install gopass*

![ Установка менеджера паролей ](image/1.png){#fig:001 width=50%}

2. Настройки
	1. Ключи GPG
	Рассмотрим список ключей с помощью команды
	
	*gpg --list-secret-keys*
	
![ Рассмотрим список ключей ](image/2.png){#fig:002 width=50%}

	2. Инициальзируем хранилище с помощью команды 
	
	*pass init ilovekiwiverymuch@gmail.com*
	
	![ Инициальзируем хранилище  ](image/3.png){#fig:003 width=50%}
	
	3. Синхронизируем с git
	
	- Создадим структуру git
	- зададим адрес репозитория в хостинге 
	- для синхронизации выполним команды 
	
	*pass git pull*
	*pass git push*
	
	![ Синхронизируем с git  ](image/4.png){#fig:004 width=50%}
	
	1. Прямые изменения
	- Заметим, что отслеживаются изменения, сделанные только на pass
	- Если измения сделаны непосредственно на файловой системе,  необходимо вруччную закоммитить и выложить изменения
	- Проверим статус синхронизации командой
	
	*pass git status*
	
	![ Прямые изменения ч1 ](image/5.png){#fig:005 width=50%}	
	![ Прямые изменения ч2 ](image/6.png){#fig:006 width=50%}
	
3. Настройка интерфейса с браузером

- Для взаимодействия с браузером используем интерфейс native massaging
- Поэтому кроме плагина к браузеру устанавливается программа, обеспичивающая интерфейс native massaging

Установим нужное программное обеспечение на Fedora с помощью команды:

*dnf copr enable maximbaz/browserpass*
*dnf install browserpass*

![ Установка на ОС Fedora ](image/7.png){#fig:007 width=50%}

4. Сохранение пароля

- Добавим новый пароль с помощью команды

*pass insert <filename>*

- отобразим пароль для указанного имени файла:	

*pass <filename>*

![ Сохранение пароля ](image/8.png){#fig:008 width=50%}

## Управление файлами конфигурации
## Дополнительное программное обеспечение

- Установим всё дополнительное программное обеспечение  с помощью команд типа 

*sudo dnf -у install <название>*

![ Установка всех необходимых пакетов ](image/9.png){#fig:009 width=50%}

- Установим все необходимые шрифты:

![ Установка необходимых шрифтов ](image/10.png){#fig:010 width=50%}

1. Установка 
- Установим бинарный файл. Скрипт определяет архитектуру процессора и ОС и скачивает необходимый файл:

с помощью *wget*

![ Установка бинарного файла ](image/11.png){#fig:011 width=50%}

2. Создание собственного репозитория

- Для создания репозитория используем улиты командной строки для работы с github
- Создадим свой репозиторий для конфигурационных файлов на основе курса шаблона:

![ Создание репозитория для конфигурационных файлов ](image/12.png){#fig:012 width=50%}

3. Подключение репозитория к новой системе

- Инициализируем chezmoi с репозиторием dotfiles или через ssh

- Далее проверим, какие изменения внесёт chezmoi  в домашний каталог, запустив его через команду 

* chezmoi diff*

- Изменения устраивают меня, поэтому запустим его через команду

*chezmoi apply -v*

![ Подключение репозитория к новой системе ](image/13.png){#fig:013 width=50%}

4. Ежедневные операции с chezmoi

- Извлечём последние изменения из репозитория и применим их с помощью команды
	*chezmoi update* 
	

![ Извлечём последние изменения из репозитория ](image/14.png){#fig:014 width=50%}
	
- Извлечём последние изменения из репозитория и посмотрим, что изменится, фактически не применяя изменения


![ Извлечём последние изменения из репозитория и посмотрим, что изменится ](image/15.png){#fig:015 width=50%}


- Я довольна изменениями, так что применяю их все с помощью команды

*chezmoi apply*

![ Применяем изменения в репозитории ](image/16.png){#fig:016 width=50%}

- В файле chezmoi.toml изменим пару строк, чтобы включить функцию автоматического фиксирования и отправки изменений в репозиторий:


![ В файле chezmoi.toml ](image/17.png){#fig:017 width=50%}



# Выводы
В ходе выполнения лабораторной работы №5 мы приобрели ценные знания о работе с такими системами как chezmoi и pass, а также применили полученные знания на практике


::: {#refs}
:::
