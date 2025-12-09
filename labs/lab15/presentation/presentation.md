---
## Front matter
lang: ru-RU
title: "Лабораторная работа №15"
subtitle: "Управление логическими томами LVM"
author:
  - Лабси Мохаммед
institute:
  - Российский университет дружбы народов, Москва, Россия
date: 08 декабря 2025

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

Получить навыки создания, управления и модификации логических томов LVM в Linux.

# Ход выполнения работы

## Разметка диска /dev/sdb

![Создание PV на sdb1](Screenshot_1.png){ width=70% }

## Формирование VG

![Создание VG и проверка PV/VG](Screenshot_2.png){ width=70% }

## Создание LV и файловой системы

![Добавление записи в fstab](Screenshot_3.png){ width=70% }

## Проверка монтирования

![Проверка монтирования LV](Screenshot_4.png){ width=70% }

## Добавление нового раздела /dev/sdb2

![Создание раздела sdb2](Screenshot_5.png){ width=70% }

## Расширение группы томов

![Добавление PV и расширение VG](Screenshot_6.png){ width=70% }

## Увеличение размера LV и ФС

![Увеличение LV и ФС](Screenshot_7.png){ width=70% }

## Уменьшение размера LV

![Уменьшение размера LV](Screenshot_8.png){ width=70% }

# Самостоятельная работа

## Разметка диска /dev/sdc

![Разметка диска sdc](Screenshot_9.png){ width=70% }

## Создание PV, VG и LV

![Создание PV и VG](Screenshot_10.png){ width=70% }

## Форматирование XFS

![Форматирование XFS](Screenshot_10.png){ width=70% }

## Добавление записи в fstab

![fstab](Screenshot_11.png){ width=70% }

## Проверка монтирования

![Монтирование](Screenshot_12.png){ width=70% }

## Добавление PV и расширение VG

![Расширение VG](Screenshot_13.png){ width=70% }

## Увеличение LV и XFS

![Расширение LV и ФС](Screenshot_13.png){ width=70% }

## Проверка результата

![Проверка LV, VG и ФС](Screenshot_14.png){ width=70% }

## Финальная проверка

![Финальная проверка](Screenshot_15.png){ width=70% }

# Заключение

В ходе работы были освоены:

– Создание физических томов (PV)  
– Работа с группами томов (VG)  
– Создание и модификация логических томов (LV)  
– Форматирование томов ext4 и XFS  
– Постоянное монтирование через /etc/fstab  
– Увеличение и уменьшение размеров LV с изменением файловой системы  

Полученные навыки формируют основу для грамотного управления дисковой подсистемой Linux с использованием LVM.
