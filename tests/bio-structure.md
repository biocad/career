## Тестовое задание на позицию разработчика биоинформатического ПО в компанию [BIOCAD](https://biocad.ru/)

### Введение

Белок представляет из себя набор [аминокислот](https://en.wikipedia.org/wiki/Amino_acid), которые идут одна за другой. Например, белок [1FSD](https://www.rcsb.org/structure/1fsd) состоит из следующей последовательности аминокислот (каждая буква соответствует одной аминокислоте):
```
QQYTAKIKGRTFRNEKELRDFIEKFKGR
```

[Структуру белка](https://en.wikipedia.org/wiki/Protein_structure) можно представить по-разному. Если мы говорим о третичной структуре, то это набор атомов, которые связаны ковалентными взаимодействиями. По той же [ссылке](https://www.rcsb.org/structure/1fsd) вы можете скачать структуру этого белка в формате PDB и открыть её с помощью инструмента [pymol](https://pymol.org/2/). Эту структуру можно также открыть с помощью обычного текстового редактора и найти секцию ATOM ([спецификация](http://www.wwpdb.org/documentation/file-format-content/format33/sect9.html#ATOM)), которая как раз описывает положение каждого атома. В колонках 13-16 указывается тип атомов. Нас будут интересовать атомы с типом `CA` (это номера 2, 21, 38 и так далее).

Более того, белок может находиться в различных состояниях. Поэтому в рассматриваемом файле описана не одна, а 41 модель этого белка. В инструменте pymol в правом нажнем углу вы можете нажать на "play" и увидеть все модели, которые доступны для этого белка.

### Задание

  1. Взять белок 1FSD.
  2. Для каждой модели этого белка:
      - найти координаты атомов с типом `CA`. Каждая координата -- тройка из `x`, `y` и `z`.
      - построить матрицу квадратов попарных расстояний (должна получится матрица 28x28);
      - посчитать ранг получившейся матрицы.
  3. Сравнить получившиеся ранги и привести обоснование результату.
  4. Предложить алгоритм, который будет преобразовывать матрицу квадратов попарных расстояний в матрицу меньшей размерности и обратно.

### Подсказка

Если вы не хотите мучиться с парсингом PDB-формата, то для работы с PDB на языке Python существует библиотека [biopython](https://biopython.org/wiki/The_Biopython_Structural_Bioinformatics_FAQ).