---
## Front matter
lang: ru-RU
title: Лабораторная работа №1
subtitle: Установка и конфигурация ОС на виртуальную машину
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

Получение практических навыков установки операционной системы **Rocky Linux**  
на виртуальную машину и выполнения базовой конфигурации системы.

# Ход выполнения работы

## Параметры ВМ

![Параметры созданной виртуальной машины](Screenshot_1.png){ #fig:001 width=70% }

## Выбор языка установки

![Выбор языка установки](Screenshot_2.png){ #fig:002 width=70% }

![Настройка раскладки клавиатуры](Screenshot_3.png){ #fig:003 width=70% }

## Базовая среда и компоненты

![Выбор ПО](Screenshot_4.png){ #fig:004 width=70% }

## Выбор устройства установки

![Выбор диска](Screenshot_5.png){ #fig:005 width=70% }

## Kdump

![Настройка Kdump](Screenshot_6.png){ #fig:006 width=70% }

## Сеть и имя узла

![Настройка сети](Screenshot_7.png){ #fig:007 width=70% }

## Настройка root

![Настройка root](Screenshot_8.png){ #fig:008 width=70% }

## Создание пользователя

![Создание пользователя](Screenshot_9.png){ #fig:009 width=70% }

## Процесс установки

![Завершение установки](Screenshot_10.png){ #fig:010 width=70% }

## Установка Guest Additions

![Установка Guest Additions](Screenshot_11.png){ #fig:011 width=70% }

## Использование dmesg

![Вывод dmesg](Screenshot_12.png){ #fig:012 width=70% }

## Файловые системы

![Вывод mount](Screenshot_13.png){ #fig:013 width=70% }

# Заключение

## Итоги работы

В ходе лабораторной работы была установлена и настроена ОС **Rocky Linux**  
на виртуальной машине. Освоены базовые этапы установки, конфигурации системы,  
установки дополнений гостевой ОС и анализа загрузки Linux.
