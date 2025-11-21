---
## Front matter
lang: ru-RU
title: Лабораторная работа №10
subtitle: Основы работы с модулями ядра операционной системы
author:
  - Лабси Мохаммед
institute:
  - Российский университет дружбы народов, Москва, Россия
date: 23 октября 2025

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

Получить навыки работы с утилитами управления модулями ядра Linux: их загрузкой, выгрузкой, просмотром параметров и обновлением ядра системы.

# Ход выполнения работы

## Управление модулями ядра

![Вывод команды lspci -k](Screenshot_1.png){ #fig:001 width=70% }

## Просмотр загруженных модулей

![Просмотр списка загруженных модулей](Screenshot_2.png){ #fig:002 width=70% }

## Информация о модуле ext4

![Просмотр информации о модуле ext4](Screenshot_3.png){ #fig:003 width=70% }

## Выгрузка модулей ext4 и xfs

![Попытка выгрузки модулей ext4 и xfs](Screenshot_4.png){ #fig:004 width=70% }

## Проверка и загрузка bluetooth

![Информация о модуле bluetooth](Screenshot_5.png){ #fig:005 width=70% }

## Выгрузка модуля bluetooth

![Выгрузка модуля bluetooth](Screenshot_6.png){ #fig:006 width=70% }

## Просмотр версии ядра и списка пакетов

![Просмотр версии и списка пакетов ядра](Screenshot_7.png){ #fig:007 width=70% }

## Обновление пакетов и ядра

![Обновление ядра и системы](Screenshot_8.png){ #fig:008 width=70% }

## Проверка новой версии ядра

![Просмотр информации о системе после обновления](Screenshot_9.png){ #fig:009 width=70% }

# Заключение

В ходе лабораторной работы освоены основные команды работы с модулями ядра Linux, их загрузка, выгрузка, просмотр параметров и обновление ядра системы.
