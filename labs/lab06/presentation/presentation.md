---
## Front matter
lang: ru-RU
title: Лабораторная работа №6
subtitle: Управление процессами
author:
  - Лабси Мохаммед
institute:
  - Российский университет дружбы народов, Москва, Россия
date: 10 октября 2025

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

Получить практические навыки управления заданиями и процессами в операционной системе Linux: запуск, приостановка, завершение и изменение приоритетов выполнения.

# Ход выполнения работы

## Управление заданиями

![Запуск фоновых процессов и приостановка одного из них](Screenshot_1.png){ #fig:001 width=70% }

## Работа с заданиями

![Работа фоновых процессов dd и просмотр через top](Screenshot_2.png){ #fig:002 width=70% }

## Завершение процесса через top

![Завершение процесса dd через top](Screenshot_3.png){ #fig:003 width=70% }

## Просмотр и изменение приоритета

![Просмотр процессов dd](Screenshot_4.png){ #fig:004 width=70% }

## Иерархия процессов

![Изменение приоритета и завершение родительского процесса dd](Screenshot_5.png){ #fig:005 width=70% }

# Самостоятельная работа

## Задание 1

![Запуск трёх фоновых процессов dd](Screenshot_6.png){ #fig:006 width=70% }

## Задание 2

![Запуск yes в фоновом режиме](Screenshot_7.png){ #fig:007 width=70% }

## Работа с nohup и top

![Работа процессов yes и использование nohup](Screenshot_8.png){ #fig:008 width=70% }

## Изменение приоритетов yes

![Просмотр процессов yes через top](Screenshot_9.png){ #fig:009 width=70% }

## Завершение процессов yes

![Изменение приоритета и завершение процессов yes](Screenshot_10.png){ #fig:010 width=70% }

# Заключение

В ходе лабораторной работы были освоены команды управления процессами: **jobs**, **bg**, **fg**, **ps**, **top**, **kill**, **nice**, **renice**.  
Закреплены практические навыки управления заданиями, изменения приоритетов и завершения процессов в Linux.
