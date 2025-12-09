---
## Front matter
lang: ru-RU
title: Лабораторная работа №16
subtitle: Программный RAID (mdadm)
author:
  - Лабси Мохаммед
institute:
  - Российский университет дружбы народов, Москва, Россия
date: 10 декабря 2025

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

Освоить создание, настройку и управление программными RAID-массивами с использованием утилиты **mdadm**.

# Ход выполнения

## Проверка дисков

![Проверка дисков](Screenshot_1.png){ #fig:001 width=70% }

## Создание разделов и тип RAID

![Типы разделов RAID](Screenshot_2.png){ #fig:002 width=70% }

## Проверка состояния разделов

![Состояние разделов](Screenshot_3.png){ #fig:003 width=70% }

## Создание RAID 1

![Создание RAID 1](Screenshot_4.png){ #fig:004 width=70% }

## Просмотр состояния RAID

![Состояние массива](Screenshot_5.png){ #fig:005 width=70% }

## Создание файловой системы и монтирование

![Создание файловой системы](Screenshot_6.png){ #fig:006 width=70% }

## Изменение /etc/fstab

![fstab](Screenshot_7.png){ #fig:007 width=70% }

# Сбой и восстановление диска

## Перевод диска в состояние сбоя

![Сбой диска](Screenshot_8.png){ #fig:008 width=70% }

## Создание массива и добавление hotspare

![Создание RAID1 с hotspare](Screenshot_10.png){ #fig:010 width=70% }

## Просмотр состояния массива

![Состояние массива с hotspare](Screenshot_11.png){ #fig:011 width=70% }

## Автоматическая активация hotspare после сбоя

![Автозамена диска](Screenshot_12.png){ #fig:012 width=70% }

## Исходное состояние массива

![Состояние RAID1 с резервом](Screenshot_13.png){ #fig:013 width=80% }

## Исходное состояние массива

![Состояние RAID1 с резервом](Screenshot_14.png){ #fig:014 width=80% }

## Преобразование в RAID 5

![Переход в RAID5](Screenshot_15.png){ #fig:015 width=70% }

## RAID 5: три активных диска

![RAID5 с тремя дисками](Screenshot_16.png){ #fig:016 width=70% }

# Заключение

В ходе лабораторной работы были изучены методы конфигурирования программных RAID-массивов, работа с горячим резервом, восстановление после сбоя и преобразование массива между уровнями RAID. Получены практические навыки администрирования отказоустойчивых систем хранения.
