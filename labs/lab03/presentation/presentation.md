---
## Front matter
lang: ru-RU
title: Лабораторная работа №3
subtitle: Настройка прав доступа
author:
  - Лабси Мохаммед
institute:
  - Российский университет дружбы народов, Москва, Россия
date: 12 декабря 2025

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

Получить практические навыки настройки базовых, специальных и расширенных прав доступа для пользователей и групп в операционной системе Linux.

# Ход выполнения

## Защита файлов от удаления

![Проверка setgid и sticky bit](Screenshot_1.png){ #fig:001 width=70% }

## Назначение прав группам

![Просмотр ACL](Screenshot_2.png){ #fig:002 width=70% }

## Наследование прав

![Наследование ACL](Screenshot_4.png){ #fig:003 width=70% }

## Пользователь carol

![Проверка прав пользователем carol](Screenshot_5.png){ #fig:004 width=70% }

# Итоги работы

## Заключение

В ходе лабораторной работы были изучены механизмы управления правами доступа в Linux.  
Практически применены базовые, специальные и расширенные разрешения, что позволило наглядно продемонстрировать принципы разграничения доступа между пользователями и группами.
