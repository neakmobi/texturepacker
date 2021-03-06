# TexturePacker (beta)
Небольшая утилита для упаковки отдельных файлов с текстурами (*.png) в текстурный атлас.
# Возможности
После вызова программа формирует 2 файла: 
1. atlas.png - файл текстурного атласа
2. description.xml - файл описания атласа
В описании записано разрешение атласа, названия текстур (для их идентификации), координаты и размеры текстур.
# Установка
1. Склонировать репозиторий:
    >git clone https://github.com/neakmobi/texturepacker.git
2. Перейти в директорию с проектом и запустить сборку:
    >cd texturepacker && ./gradlew jar
3. В папке texturepacker/build/libs появится файл texturepacker-0.1.jar, который может быть запущен следюущей командой:
    >java -jar texturepacker-0.1.jar \[OPTIONS\]
# Использование
Пример вызова программы:
> java -jar texturepacker-0.1.jar --inputDir <PATH_TO_SRC_DIR> -a atlas.png -d descr.xml -w 2048 -h 2048 -d 2

В этом вызове:
* --inputDir (или -i) - путь до директории, содержащий текстуры для упаковки. Является обязательным параметром вызова.
* --atlasName (или -a) - имя файла-атласа
* --descriptionName (или -d) - имя файла-описания
* --width (или -w) и --height (или -h) - размер выходного атласа
* --depth (или -d) - глубина поиска. Например при -d 2 поиск будет производиться в inputDir и во вложенных в нее директориях, но не глубже, т.е. файлы в inputDir/dir1/dir2/* не будут упакованы (для их упаковки нужен -d 3)

Более подробную информацию по использованию можно получить, вызвав программу с ключом -h или --help