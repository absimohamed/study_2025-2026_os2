---
## Front matter
title: "Отчёт по лабораторной работе №11"
subtitle: "Управление загрузкой системы"
author: "Лабси Мохаммед"

## Generic otions
lang: ru-RU
toc-title: "Содержание"

## Bibliography
bibliography: bib/cite.bib
csl: pandoc/csl/gost-r-7-0-5-2008-numeric.csl

## Pdf output format
toc: true
toc-depth: 2
lof: true
lot: true
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
  - \usepackage{float}
  - \floatplacement{figure}{H}
---

# Цель работы

Получить навыки работы с загрузчиком системы GRUB2.

# Ход выполнения

## Модификация параметров GRUB2

1. В терминале получены права администратора с помощью команды **su -**.  
   После успешной аутентификации открыт сеанс суперпользователя **root**.  

2. Выполнено редактирование файла конфигурации загрузчика с помощью команды **nano /etc/default/grub**.  
   В файле изменено значение параметра **GRUB_TIMEOUT** на `10`, что задаёт время отображения меню загрузки.  

   ![Редактирование параметров GRUB](Screenshot_1.png){ #fig:001 width=80% }

3. После сохранения изменений выполнена команда **grub2-mkconfig > /boot/grub2/grub.cfg**.  
   В результате была сгенерирована новая конфигурация GRUB2, о чём свидетельствует сообщение о добавлении записи для UEFI Firmware Settings.  

   ![Обновление конфигурации GRUB2](Screenshot_2.png){ #fig:002 width=80% }

## Загрузка в режим восстановления (rescue.target)

4. После перезагрузки системы отображено меню **GRUB version 2.12**, содержащее несколько версий ядра **Rocky Linux**.  
   Для редактирования параметров выбранной записи нажата клавиша **e**.  

   ![Меню загрузчика GRUB с выбором ядра](Screenshot_3.png){ #fig:003 width=80% }

5. В конце строки, начинающейся с **linux**, добавлен параметр **systemd.unit=rescue.target**,  
   после чего загрузка продолжена с помощью **Ctrl + X**.  

   ![Добавление параметра systemd.unit=rescue.target](Screenshot_4.png){ #fig:004 width=80% }

6. После загрузки в режим восстановления выполнена проверка активных модулей командой **systemctl list-units**.  
   Видно, что загружены только базовые сервисы.  

   ![Список активных модулей в режиме rescue](Screenshot_5.png){ #fig:005 width=80% }

7. Отображены переменные окружения текущего сеанса с помощью команды **systemctl show-environment**.  

## Загрузка в аварийный режим (emergency.target)

8. После перезагрузки, на этапе выбора ядра, снова нажата клавиша **e**,  
   и в конце строки добавлен параметр **systemd.unit=emergency.target**.  
   Загрузка продолжена сочетанием **Ctrl + X**.  

   ![Добавление параметра systemd.unit=emergency.target](Screenshot_6.png){ #fig:006 width=80% }

9. После входа в систему отобразился минимальный список модулей — только критически необходимые службы.  

   ![Минимальный набор активных модулей в emergency-режиме](Screenshot_7.png){ #fig:007 width=80% }

## Сброс пароля root

10. Для восстановления пароля выполнена перезагрузка и редактирование строки загрузки ядра.  
    В конец строки добавлен параметр **rd.break**, после чего система остановилась на этапе инициализации initramfs.  

    ![Добавление параметра rd.break для сброса пароля](Screenshot_8.png){ #fig:008 width=80% }

11. Для получения доступа к файловой системе в режиме записи введена команда **mount -o remount,rw /sysroot**.  
    Далее попытка выполнить команды **chroot /sysroot** и **passwd** завершилась сообщениями о том,  
    что данные утилиты недоступны в текущем окружении.  

    ![Попытка сброса пароля в initramfs](Screenshot_9.png){ #fig:009 width=80% }

12. После завершения проверки режим аварийной загрузки был закрыт, и система перезагружена в обычном режиме.

# Контрольные вопросы

1. **Какой файл конфигурации следует изменить для применения общих изменений в GRUB2?**  
   Для изменения общих параметров загрузчика необходимо отредактировать файл **/etc/default/grub**.  
   В нём задаются основные настройки, такие как тайм-аут меню, параметры загрузки ядра и тип вывода.

2. **Как называется конфигурационный файл GRUB2, в котором вы применяете изменения для GRUB2?**  
   Итоговый конфигурационный файл, используемый загрузчиком, — это **/boot/grub2/grub.cfg**.  
   В него записываются все актуальные параметры после генерации новой конфигурации.

3. **После внесения изменений в конфигурацию GRUB2, какую команду вы должны выполнить, чтобы изменения сохранились и воспринялись при загрузке системы?**  
   Для обновления конфигурации GRUB2 необходимо выполнить команду  
   **grub2-mkconfig > /boot/grub2/grub.cfg**  
   или её эквивалент **grub2-mkconfig -o /boot/grub2/grub.cfg**.

# Заключение

В ходе работы были изучены методы настройки и управления загрузчиком **GRUB2** в операционной системе Linux.  
Были освоены приёмы изменения параметров конфигурации, генерации нового загрузочного файла, а также загрузки системы в режимах **rescue**, **emergency** и с параметром **rd.break** для восстановления пароля пользователя **root**.  
Полученные навыки позволяют администратору эффективно управлять процессом загрузки и устранять возможные проблемы при старте системы.
