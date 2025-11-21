---
## Front matter
lang: ru-RU
title: Лабораторная работа №11
subtitle: Управление загрузкой системы
author:
  - Лабси Мохаммед
institute:
  - Российский университет дружбы народов, Москва, Россия
date: 27 октября 2025

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

Получить навыки работы с загрузчиком системы **GRUB2** и изучить способы управления загрузкой, восстановления системы и сброса пароля root.

# Ход выполнения работы

## Модификация параметров GRUB2

![Редактирование параметров GRUB](Screenshot_1.png){ #fig:001 width=70% }

## Генерация новой конфигурации

![Обновление конфигурации GRUB2](Screenshot_2.png){ #fig:002 width=70% }

## Меню загрузчика GRUB

![Меню загрузчика GRUB с выбором ядра](Screenshot_3.png){ #fig:003 width=70% }

# Режим восстановления (rescue.target)

## Переход в режим восстановления

![Добавление параметра systemd.unit=rescue.target](Screenshot_4.png){ #fig:004 width=70% }

## Проверка активных модулей

![Список активных модулей в режиме rescue](Screenshot_5.png){ #fig:005 width=70% }

# Аварийный режим (emergency.target)

## Переход в аварийный режим

![Добавление параметра systemd.unit=emergency.target](Screenshot_6.png){ #fig:006 width=70% }

## Минимальный набор модулей

![Минимальный набор активных модулей в emergency-режиме](Screenshot_7.png){ #fig:007 width=70% }

# Сброс пароля root

## Использование параметра rd.break

![Добавление параметра rd.break для сброса пароля](Screenshot_8.png){ #fig:008 width=70% }

## Попытка выполнения команд восстановления

![Попытка сброса пароля в initramfs](Screenshot_9.png){ #fig:009 width=70% }

# Заключение

В ходе лабораторной работы были изучены методы настройки и управления загрузчиком **GRUB2**.  
Освоены приёмы изменения конфигурации, восстановления системы и сброса пароля root,  
что позволяет администратору эффективно управлять процессом загрузки и устранять неполадки.
