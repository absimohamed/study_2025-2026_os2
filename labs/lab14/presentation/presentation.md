---
## Front matter
lang: ru-RU
title: Лабораторная работа №14
subtitle: Партиции, файловые системы, монтирование
author:
  - Лабси Мохаммед
institute:
  - Российский университет дружбы народов, Москва, Россия
date: 14 ноября 2025

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

Получить навыки создания разделов, файловых систем и монтирования в Linux с использованием утилит **fdisk**, **gdisk**, **mkfs**, **mkswap** и конфигурации **/etc/fstab**.

# Ход выполнения работы

## Создание разделов MBR с помощью fdisk

![Просмотр списка дисков](Screenshot_1.png){ width=70% }

## Основные действия

![Справка fdisk](Screenshot_2.png){ width=70% }

## Создание основного раздела 300 MiB

![Создание раздела 300M](Screenshot_3.png){ width=70% }

## Результат

![Появление /dev/sda1](Screenshot_4.png){ width=70% }

## Extended + Logical

![Создание extended и логического](Screenshot_5.png){ width=70% }

### Проверка структуры

![Просмотр разметки](Screenshot_6.png){ width=70% }

## Создание swap раздела

![Создание swap-раздела](Screenshot_7.png){ width=70% }

## Итоговая структура

![Разделы sda1, sda2, sda5, sda6](Screenshot_8.png){ width=70% }

## Создание таблицы GPT

![Просмотр GPT-разметки](Screenshot_9.png){ width=70% }

## Создание GPT-раздела 300 MiB

![Создание GPT-раздела 300MiB](Screenshot_10.png){ width=70% }

## Проверка результата

![Проверка разделов](Screenshot_11.png){ width=70% }

## XFS → /dev/sda1

![Создание XFS-раздела](Screenshot_12.png){ width=70% }

## EXT4 → /dev/sda5

![Создание EXT4-раздела](Screenshot_13.png){ width=70% }

## Ручное монтирование


![Ручное монтирование EXT4](Screenshot_14.png){ width=70% }

## Получение UUID

![Просмотр UUID](Screenshot_15.png){ width=70% }

# Самостоятельная работа

## Создание дополнительных GPT-разделов

![Создание двух GPT-разделов](Screenshot_17.png){ width=70% }

### Форматирование и настройка

![Форматирование EXT4 и swap](Screenshot_18.png){ width=70% }

## Создание записей в fstab

![Настройка fstab](Screenshot_19.png){ width=70% }

## Проверка после перезагрузки

![Проверка результата](Screenshot_20.png){ width=70% }

# Заключение

Были освоены операции разметки дисков (MBR, GPT), создание основных и логических разделов, форматирование файловых систем **XFS** и **EXT4**, настройка области подкачки и автоматического монтирования через **/etc/fstab**. Полученные навыки позволяют выполнять базовое администрирование дисковой подсистемы Linux.
