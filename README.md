# Protein databank filtering

*Проект реализован в рамках производственной практики в университете НИУ ВШЭ. Целью работы является изучение базы белковых структур и анализ её отдельных компонентов.*

**Ключевые слова:** Python, biopython, database, sqlalchemy, mysql. 

## Идея
Protein Databank - всемирная база данных белковых структур. Она хранит в себе информацию о всевозможных белках и исследованиях, связанных с ними. Так как база ежедневно пополняется учеными со всего мира, в ней может быть тяжело ориентироваться, поэтому я предлагаю создать альтернативную базу данных, которая будет хранить в себе агрегированные данные о конкретных белках из protein databank. 

## Описание подхода 
В этой работе реализована функция `pdb_filtering`. Она принимает на вход кортеж из Id белковых структур (id такие же как в protein databank). Функция скачивает данные из protein databank, при этом проверяя белковую цепочку на наличие уникальных характеристик (присутсвие воды в середине, присутсвие воды в конце цепочки и тд.). После того, как анализ белка произведен функция добавляет полученные данные в новую базу данных.  
Новая база данных реализована с помощью сервера Mysql, взаимодействие с базой реализовано через sqlalchemy. 