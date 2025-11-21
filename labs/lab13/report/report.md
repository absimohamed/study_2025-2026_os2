---
## Front matter
title: "Отчёт по лабораторной работе №13"
subtitle: "Фильтр пакетов"
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

Получить навыки настройки пакетного фильтра в Linux.

# Ход выполнения

## Управление брандмауэром с помощью firewall-cmd

1. Получены административные полномочия через команду **su -**.

2. Определена зона, используемая по умолчанию — **public**.

3. Просмотрен список доступных зон. На экране отобразился перечень: *block, dmz, drop, external, home, internal, public, trusted, work и др.*

   ![Просмотр зон](Screenshot_1.png){ #fig:001 width=80% }

4. Запрошен список всех доступных сервисов на системе. Отобразился длинный перечень служб (ssh, http, https, vnc-server, ftp и др.).

5. Выполнен просмотр сервисов, разрешённых в текущей зоне. Активными были:
   - cockpit  
   - dhcpv6-client  
   - ssh  

6. Сравнены результаты вывода:
   - информации о текущей зоне;
   - информации о зоне public.

   Вывод совпал, так как зона **public** является активной и используется по умолчанию.

   ![Просмотр конфигурации зоны public](Screenshot_2.png){ #fig:002 width=80% }

7. Добавлена служба VNC-сервера в конфигурацию временного выполнения.

8. Проверено наличие сервиса vnc-server — он появился в списке активных служб.

   ![Добавление VNC-сервера](Screenshot_3.png){ #fig:003 width=80% }

9. Выполнен перезапуск службы **firewalld**.

10. После перезапуска службы vnc-server исчез.  
    **Причина**: добавление производилось только во временную конфигурацию, не было сохранено на диск.

    ![VNC отсутствует после перезапуска](Screenshot_4.png){ #fig:004 width=80% }

11. Повторно добавлена служба vnc-server, но уже как постоянная (записанная на диск).

12. После проверки службы vnc-server не было видно, так как постоянная конфигурация ещё не была применена.

    ![Добавление permanent](Screenshot_5.png){ #fig:005 width=80% }

13. Выполнена перезагрузка конфигурации брандмауэра. После этого служба появилась в активной конфигурации.

14. В конфигурацию добавлен порт **2022/tcp** как постоянный. Далее выполнена перезагрузка конфигурации брандмауэра.

15. Проверено, что порт добавлен — он появился в разделе *ports*.

    ![Добавление порта 2022](Screenshot_6.png){ #fig:006 width=80% }

## Управление брандмауэром через графический интерфейс firewall-config

1. Запущено приложение **firewall-config**.

2. В меню **Configuration** выбрано состояние **Permanent**, чтобы изменения сохранялись.

3. Для зоны **public** активированы службы:
   - http  
   - https  
   - ftp  

   ![Включение служб в GUI](Screenshot_7.png){ #fig:007 width=80% }

4. На вкладке **Ports** добавлен порт `2022` протокола UDP.

   ![Добавление порта 2022/udp](Screenshot_8.png){ #fig:008 width=80% }

5. Приложение закрыто.

6. Проверка через firewall-cmd показала, что изменения ещё не применены (так как это постоянные настройки).

7. После перезагрузки конфигурации изменения вступили в силу:
   - службы http, https, ftp активированы;
   - порты `2022/tcp` и `2022/udp` присутствуют.

   ![Изменения применены](Screenshot_9.png){ #fig:009 width=80% }

## Самостоятельная работа

1. В конфигурацию добавлена служба **telnet** (через командную строку) как постоянная.

2. Через интерфейс **firewall-config** добавлены службы **imap**, **pop3**, **smtp**.

3. После перезагрузки конфигурации убедились, что настройки сохранены и загружаются автоматически.
   ![Изменения применены](Screenshot_10.png){ #fig:010 width=80% }

## Контрольные вопросы

1. **Какая служба должна быть запущена перед началом работы с менеджером конфигурации брандмауэра firewall-config?**  
   Перед запуском графического менеджера **firewall-config** должна быть активна служба **firewalld**.

2. **Какая команда позволяет добавить UDP-порт 2355 в конфигурацию брандмауэра в зоне по умолчанию?**  
   UDP-порт 2355 можно добавить с помощью команды:  
   **firewall-cmd --add-port=2355/udp --permanent**

3. **Какая команда позволяет показать всю конфигурацию брандмауэра во всех зонах?**  
   Для просмотра настроек во всех зонах используется команда:  
   **firewall-cmd --list-all-zones**

4. **Какая команда позволяет удалить службу vnc-server из текущей конфигурации брандмауэра?**  
   Удаление выполняется командой:  
   **firewall-cmd --remove-service=vnc-server**

5. **Какая команда firewall-cmd позволяет активировать новую конфигурацию, добавленную опцией --permanent?**  
   Чтобы изменения вступили в силу, выполняется команда:  
   **firewall-cmd --reload**

6. **Какой параметр firewall-cmd позволяет проверить, что новая конфигурация была добавлена в текущую зону и теперь активна?**  
   Проверка выполняется командой:  
   **firewall-cmd --list-all**

7. **Какая команда позволяет добавить интерфейс eno1 в зону public?**  
   Чтобы добавить интерфейс, используется команда:  
   **firewall-cmd --zone=public --add-interface=eno1 --permanent**

8. **Если добавить новый интерфейс в конфигурацию брандмауэра, пока не указана зона, в какую зону он будет добавлен?**  
   Если зона не указана, интерфейс автоматически будет добавлен в **зону по умолчанию**, указанную в системе (как правило, это *public*).

# Заключение

В ходе выполнения работы были изучены возможности управления межсетевым экраном в Linux с использованием утилиты **firewall-cmd** и графического интерфейса **firewall-config**. Были получены навыки просмотра активных зон и сервисов, добавления и удаления служб и портов, работы с временной и постоянной конфигурациями, а также применения изменений путём перезагрузки конфигурации. Кроме того, была создана пользовательская конфигурация брандмауэра, позволяющая доступ к определённым службам, как через командную строку, так и через графический интерфейс. Это позволило закрепить практические навыки администрирования сетевой безопасности в операционных системах семейства Linux.
