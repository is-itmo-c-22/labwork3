# Лабораторная работа 3

## Задача 

Релазовать упрощенную [Модель песчаной кучи](https://en.wikipedia.org/wiki/Abelian_sandpile_model), позволяющую сохранять свои состояния в картинку в [формате BMP](https://en.wikipedia.org/wiki/BMP_file_format). 

Изначальное состояние и размер сетки задается.  

Размер сетки может изменяться в процессе*

Реализация - консольное приложение, поддерживающее следующие аргументы командной строки:

  **-l, --length**   - длина сетки
  
  **-w, --width**    - ширина сетки     
  
  **-i, --input**    - tsv-файл (tab-separated values) c начальными данными
  
  **-o, --output**   - путь к директории, для сохранения картинок
  
  **-m, --max-iter** - максимальное количество итераций модели
  
  **-f, --freq**     - частота с которой должны сохранятся картинки (если 0, то сохраняется только последнее состояние)
  
## Начальное состояние

Начальное состояние задается размерами сетки, переданными в качестве аргументов программы и файлом с изначальным количеством песчинок в каждой ячейке, кроме пустых.

Формат файла: 
Каждая сторчка содержит информацию об обной ячейке, в виде (x-координаты, y-координаты, количестве песчинок), разделенных символом табуляции. Количество песчинок гарантированно влезет в uint64_t. 

## Примечания к модели

1. Новые песчинки добавляются только при инициализации.
2. Состояние след поколения ячейки зависит только от предыдущего состояния сетки
3. В случае если песчинки обваливаютя за сетку, они пропадают
3*. В случае если песчинки обваливаютя за сетку, размер сетки увеличивается на 1 в соответсвующу стороны

## Результат работы программа

Программа должна пересчитывать состояние модели, согласно начальным данным, а также сохранять промежуточные состояния с заданной частотой в картинку в формате bmp.

Картинка для текущего состояния формируется по след правилам:

1. Размер картинки равен размеру поля

2. Каждый пиксель соответствует ячейке поля

3. Цвет пикселя зависит от количество песчинок  в ячейке: 0 - белый, 1 - зеленый, 2 - фиолетовый, 3 - желтый, > 3 - черный.

Программа должна закончить свою работу в случае если модель достигла стабильного состояния, либо номера итерации заданной изначально. 

## Примечание

1. Для реализации Вам может пригодиться [библиотека](https://en.cppreference.com/w/cpp/filesystem) для работы с файловой системы из стандартной библиоткеи 
2. Пользовать сторонними библиотеками, кроме стандартной запрещено. Это в частности означает, что вы должны сами спроектировать и реализовать функции для работы с картинками в формате bmp
3. В данной лабе вам дано только описание, структура проекта, и организация сборки - так же ваша задача. 

## Deadline

1. 30.10.22 24:00 - 0.8
2. 06.11.22 24:00 - 0.65
3. 13.11.22 24:00 - 0.5

## NB

Данная оценивается 15 баллами и первый дедлайн через 3 недели.
* для первого полупотока



  
