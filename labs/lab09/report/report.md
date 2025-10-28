---
## Front matter
title: "Отчёт по лабораторной работе №9"
subtitle: "Управление SELinux"
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

Получить навыки работы с контекстом безопасности и политиками SELinux.

# Выполнение работы

## Просмотр состояния SELinux

Для начала были получены права администратора с помощью команды su.  
После ввода пароля выполнена команда sestatus -v.

Вывод команды показывает подробную информацию о состоянии SELinux:  
- SELinux status: enabled — система безопасности SELinux включена;  
- SELinuxfs mount: /sys/fs/selinux — точка монтирования файловой системы SELinux;  
- SELinux root directory: /etc/selinux — корневой каталог конфигурации SELinux;  
- Loaded policy name: targeted — используется политика, защищающая только определённые процессы;  
- Current mode: enforcing — политика SELinux активно применяется;  
- Mode from config file: enforcing — тот же режим задан в конфигурации;  
- Policy MLS status: enabled — поддержка многоуровневой безопасности включена;  
- Policy deny_unknown status: allowed — неизвестные объекты разрешены;  
- Memory protection checking: actual (secure) — контроль памяти активен;  
- Process contexts и File contexts — показывают контексты безопасности активных процессов и файлов.

![Проверка состояния SELinux](Screenshot_1.png){ #fig:001 width=80% }

## Проверка и изменение режима SELinux

Режим SELinux был проверен с помощью команды getenforce.  
По умолчанию система находилась в состоянии Enforcing (принудительное исполнение политики).  
Затем режим был изменён на разрешающий Permissive.  
Повторная проверка показала, что SELinux работает в режиме Permissive.

![Изменение режима работы SELinux](Screenshot_2.png){ #fig:002 width=80% }

## Отключение SELinux через конфигурационный файл

Для полного отключения SELinux был отредактирован файл конфигурации /etc/sysconfig/selinux.  
В нём параметр SELINUX был изменён на disabled и сохранены изменения.

![Редактирование конфигурации SELinux (отключение)](Screenshot_3.png){ #fig:003 width=80% }

После перезагрузки проверка состояния показала, что SELinux отключён.  
Попытка включить SELinux без перезагрузки завершилась сообщением, что SELinux is disabled.

![SELinux отключён](Screenshot_4.png){ #fig:004 width=80% }

## Включение SELinux и возврат в режим Enforcing

Для повторного включения SELinux параметр SELINUX в файле /etc/sysconfig/selinux был изменён на enforcing.  

![Редактирование конфигурации SELinux (включение)](Screenshot_5.png){ #fig:005 width=80% }

После перезагрузки система вывела предупреждение о необходимости переразметки меток безопасности (relabeling), что может занять некоторое время.

![Переразметка меток безопасности при загрузке](Screenshot_6.png){ #fig:006 width=80% }

После завершения перезагрузки команда sestatus -v показала, что SELinux снова работает в режиме enforcing.

![Проверка состояния SELinux после включения](Screenshot_7.png){ #fig:007 width=80% }

## Восстановление контекста безопасности файлов

Для примера использовался системный файл /etc/hosts.  
При проверке его контекста была получена метка system_u:object_r:net_conf_t:s0.  
После копирования файла в домашний каталог его контекст изменился на admin_home_t, поскольку копирование создает новый объект.  
При перемещении файла обратно в /etc контекст остался прежним — admin_home_t.  
Для восстановления корректного контекста была использована команда restorecon -v /etc/hosts, после чего контекст вернулся к исходному — net_conf_t.

![Восстановление контекста безопасности файла /etc/hosts](Screenshot_8.png){ #fig:008 width=80% }

Для массового восстановления контекста безопасности на всей файловой системе была создана команда touch /.autorelabel.  
После перезагрузки система автоматически провела процесс перемаркировки (relabeling).

![Автоматическая перемаркировка файловой системы при загрузке](Screenshot_9.png){ #fig:009 width=80% }

## Настройка контекста безопасности для нестандартного расположения файлов веб-сервера

Для начала были установлены необходимые пакеты httpd и lynx.  
Создан новый каталог для веб-контента /web и файл index.html с текстом «Welcome to my web-server».  

В конфигурационном файле /etc/httpd/conf/httpd.conf были внесены изменения:  
строка DocumentRoot "/var/www/html" закомментирована и заменена на DocumentRoot "/web".  
Также добавлен новый раздел с правами доступа:

![Изменение конфигурации веб-сервера](Screenshot_10.png){ #fig:010 width=80% }

После запуска веб-сервера и обращения к адресу http://localhost отображалась стандартная тестовая страница Rocky Linux, что указывает на отсутствие доступа к пользовательскому каталогу.

![Тестовая страница Rocky Linux](Screenshot_11.png){ #fig:011 width=80% }

Для решения этой проблемы был задан новый контекст безопасности каталогу /web.  
Выполнена команда semanage fcontext для назначения типа httpd_sys_content_t и восстановлен контекст при помощи restorecon.  
В результате каталог /web и файл index.html получили корректные метки безопасности.

![Назначение контекста безопасности каталогу /web](Screenshot_12.png){ #fig:012 width=80% }

После этого при повторном обращении к серверу в браузере lynx отображается страница с пользовательским сообщением «Welcome to my web server».

![Доступ к пользовательской веб-странице](Screenshot_13.png){ #fig:013 width=80% }

## Работа с переключателями SELinux

Для анализа переключателей SELinux, связанных с FTP-службой, была выполнена команда getsebool -a | grep ftp.  
В списке найден параметр ftpd_anon_write, отвечающий за возможность анонимной записи через FTP, который по умолчанию имел состояние off.

Затем была выполнена команда semanage boolean -l | grep ftpd_anon для отображения описания параметра и его текущего состояния.  
Параметр ftpd_anon_write был временно включён при помощи setsebool ftpd_anon_write on.  
Проверка показала, что состояние изменилось на on, однако настройка постоянной (persistent) конфигурации осталась выключенной.  

Для включения постоянной настройки был применён ключ -P

Повторная проверка с помощью semanage boolean -l | grep ftpd_anon показала, что переключатель ftpd_anon_write теперь включён как временно, так и постоянно (on , on).

![Работа с переключателями SELinux для FTP](Screenshot_14.png){ #fig:014 width=80% }

# Контрольные вопросы

1. **Вы хотите временно поставить SELinux в разрешающем режиме. Какую команду вы используете?**  
   Для временного перевода SELinux в разрешающий режим используется команда  
   **setenforce 0**.  
   После этого можно проверить состояние командой **getenforce**.

2. **Вам нужен список всех доступных переключателей SELinux. Какую команду вы используете?**  
   Для вывода полного списка переключателей SELinux используется команда  
   **getsebool -a**.  
   Она отображает все логические параметры (boolean) и их текущее состояние.

3. **Каково имя пакета, который требуется установить для получения легко читаемых сообщений журнала SELinux в журнале аудита?**  
   Для интерпретации сообщений SELinux используется пакет **setroubleshoot**.  
   Он позволяет получать понятные уведомления о причинах блокировок и рекомендациях по их устранению.

4. **Какие команды вам нужно выполнить, чтобы применить тип контекста httpd_sys_content_t к каталогу /web?**  
   Необходимо выполнить следующие команды:  
   - **semanage fcontext -a -t httpd_sys_content_t "/web(/.*)?"** — добавляет правило для назначения типа контекста.  
   - **restorecon -R -v /web** — применяет изменения и обновляет контекст безопасности каталога.

5. **Какой файл вам нужно изменить, если вы хотите полностью отключить SELinux?**  
   Для полного отключения SELinux необходимо отредактировать файл **/etc/sysconfig/selinux**,  
   изменив строку **SELINUX=enforcing** на **SELINUX=disabled**.

6. **Где SELinux регистрирует все свои сообщения?**  
   Журнал событий SELinux записывается в файл **/var/log/audit/audit.log**.  
   Если служба аудита недоступна, сообщения также могут появляться в **/var/log/messages**.

7. **Вы не знаете, какие типы контекстов доступны для службы ftp. Какая команда позволяет получить более конкретную информацию?**  
   Для просмотра контекстов и разрешённых типов, связанных с FTP, используется команда  
   **semanage fcontext -l | grep ftp**.  
   Она показывает все файлы и каталоги, имеющие контексты, применяемые к FTP-службе.

8. **Ваш сервис работает не так, как ожидалось, и вы хотите узнать, связано ли это с SELinux или чем-то ещё. Какой самый простой способ узнать?**  
   Самый простой способ — временно перевести SELinux в разрешающий режим с помощью  
   **setenforce 0** и проверить, изменилось ли поведение сервиса.  
   Если после этого сервис начал работать корректно, значит, причина связана с политикой SELinux.

# Заключение

В ходе работы были изучены принципы управления безопасностью с помощью SELinux, включая изменение режимов работы, настройку контекстов безопасности и использование переключателей политик.
