---
## Front matter
lang: ru-RU
title: Лабораторная работа №2
subtitle: Управление пользователями и группами
author:
  - Лабси Мохаммед
institute:
  - Российский университет дружбы народов, Москва, Россия
date: 12 декаюря 2025

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

Получить практические навыки управления учётными записями пользователей и группами пользователей в операционной системе Linux, а также изучить механизмы разграничения прав доступа.

# Ход выполнения

## Определение текущей учётной записи

![Определение пользователя и групп](Screenshot_1.png){ #fig:001 width=70% }

## Файл sudoers

![Просмотр файла sudoers](Screenshot_2.png){ #fig:002 width=70% }

## Пользователь alice

![Создание пользователя alice](Screenshot_3.png){ #fig:003 width=70% }

## Файл login.defs

![Редактирование login.defs](Screenshot_4.png){ #fig:004 width=70% }

## Каталог /etc/skel

![Настройка /etc/skel](Screenshot_5.png){ #fig:005 width=70% }

## Создание и проверка

![Домашний каталог carol](Screenshot_6.png){ #fig:006 width=70% }

## Управление паролем

![Настройка пароля carol](Screenshot_7.png){ #fig:007 width=70% }

## Проверка групп

![Проверка групп пользователей](Screenshot_8.png){ #fig:008 width=70% }

## Проверка доступа

![Проверка прав доступа](Screenshot_9.png){ #fig:009 width=70% }

# Итоги работы

## Заключение

Получены практические навыки администрирования пользователей и групп в Linux.  
Работа показала принципы управления доступом, настройки безопасности и централизованного администрирования в многопользовательской системе.
