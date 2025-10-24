---
## Front matter
lang: ru-RU
title: Лабораторная работа №8
subtitle: Планировщики событий
author:
  - Лабси Мохаммед
institute:
  - Российский университет дружбы народов, Москва, Россия
date: 11 октября 2025

## i18n babel
babel-lang: russian
babel-otherlangs: english

## Formatting pdf
toc: false
slide_level: 2
aspectratio: 169
section-titles: true
theme: metropolis
header-includes:
 - \metroset{progressbar=frametitle,sectionpage=progressbar,numbering=fraction}
---

# Цель работы

## Основная цель

Получить практические навыки работы с планировщиками событий **cron** и **at** в операционной системе Linux.

# Ход выполнения

## Проверка работы службы cron

![Проверка статуса службы crond](Screenshot_1.png){ #fig:001 width=70% }

## Просмотр системного файла crontab

![Просмотр содержимого /etc/crontab](Screenshot_2.png){ #fig:002 width=70% }

## Создание нового задания cron

![Создание записи в crontab для root](Screenshot_3.png){ #fig:003 width=70% }

## Проверка выполнения задания cron

![Проверка выполнения задания cron через системный журнал](Screenshot_4.png){ #fig:004 width=70% }

## Изменение расписания cron

![Изменение расписания cron](Screenshot_5.png){ #fig:005 width=70% }

## Создание скрипта eachhour

![Создание скрипта eachhour в /etc/cron.hourly](Screenshot_6.png){ #fig:006 width=70% }

## Настройка расписания в /etc/cron.d

![Создание расписания в /etc/cron.d](Screenshot_7.png){ #fig:007 width=70% }

# Планирование с помощью at

## Проверка службы atd

![Создание и выполнение задания через службу atd](Screenshot_8.png){ #fig:008 width=70% }

# Заключение

В ходе лабораторной работы были изучены и применены средства автоматизации в Linux — **cron** и **at**,  
что позволило освоить создание, редактирование и контроль выполнения заданий по расписанию.
