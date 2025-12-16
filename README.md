# Лабораторная работа 5-6
## Работа с векторными базами данных (ChromaDB). Работа с графовыми базами данных (Neo4j)
### Цели:
1) Освоить принципы работы с векторными базами данных на примере ChromaDB. Получить практические навыки создания коллекций, генерации эмбеддингов, выполнения семантического поиска и интеграции с ML-моделями.
2) Освоить принципы работы с графовыми базами данных на примере Neo4j. Получить практические навыки создания узлов и связей, выполнения запросов на языке Cypher и визуализации графовых структур.
### Выполнение:
#### Часть 1
Для подготовки к работе с ChromaDB, выполним команду *pip install chromadb sentence-transformers pandas numpy*.

Создадим скрипт [chroma.py](https://github.com/dropdeadsss/lab_5_6/blob/main/chroma.py), в котором создается векторная база данных ChromaDB, в нее помещаются документы и эмбеддинги.

![screenshot](https://github.com/dropdeadsss/lab_5_6/blob/main/imgs/2.JPG)

Далее создадим функцию для семантического поиска, которая выводит 3 самых похожих документа из коллекции и находит расстояние. Чем меньше расстояние, тем документ ближе к запросу. 

![screenshot](https://github.com/dropdeadsss/lab_5_6/blob/main/imgs/3.JPG)

Создадим функцию для семонтического поиска доп. фильтрацией и используем фильтр по категории.

![screenshot](https://github.com/dropdeadsss/lab_5_6/blob/main/imgs/4.JPG)

Также осуществим сохранение данных из базы локально, что позволит использовать их повторно.

![screenshot](https://github.com/dropdeadsss/lab_5_6/blob/main/imgs/1.JPG)

Создадим функцию, котрая добавляет новую коллекцию новостей и выполняет поиск по ним.

![screenshot](https://github.com/dropdeadsss/lab_5_6/blob/main/imgs/5.JPG)

#### Часть 2
Для работы с графовой базай данных Neo4j запустим отдельный контейнер Docker с помощью команды *docker run --name n4j -p 7474:7474 -p 7687:7687 -it --env NEO4J_AUTH=neo4j/password123 neo4j:latest*. После запуска можно подключиться к интерфейсу для работы с бд перейдя по адресу *http://localhost:7474*.

Создадим скрипт [neo4j_demo.py](https://github.com/dropdeadsss/lab_5_6/blob/main/neo4j_demo.py), который строит базу знаний и связи в графе.

![screenshot](https://github.com/dropdeadsss/lab_5_6/blob/main/imgs/(2)%202.JPG)

![screenshot](https://github.com/dropdeadsss/lab_5_6/blob/main/imgs/(2)%203.JPG)

Скрипт подгружает данные из csv-файла [ai_researchers.csv](https://github.com/dropdeadsss/lab_5_6/blob/main/neo4j_files/ai_researchers.csv). Далее перейдя по адресу в браузере и введя команду *MATCH (n) RETURN n LIMIT 25*, можно увидеть визуализацию связей в виде графа.

![screenshot](https://github.com/dropdeadsss/lab_5_6/blob/main/imgs/(2)%205.JPG)

Далее данные экспортируются в csv-файл [graph_export.csv](https://github.com/dropdeadsss/lab_5_6/blob/main/neo4j_files/graph_export.csv) и соединение закрывается.

![screenshot](https://github.com/dropdeadsss/lab_5_6/blob/main/imgs/(2)%204.JPG)
