## Laboratory work I


____________
Current task: 1

1. Скачайте библиотеку boost с помощью утилиты wget. Адрес для скачивания ` https://sourceforge.net/projects/boost/files/boost/1.69.0/boost_1_69_0.tar.gz.`


script:

```shell
$ wget https://sourceforge.net/projects/boost/files/boost/1.69.0/boost_1_69_0.tar.gz
```
______________


Current task: 2

2. Разархивируйте скаченный файл в директорию `~/boost_1_69_0`



script: 
```shell
$ tar -xf boost_1_69_0.tar.gz
$ mv boost_1_69_0 ~/boost_1_69_0
```

result:
```shell
boost_1_69_0  boost_1_69_0.tar.gz  REPORT.md
```

script:
```shell
mv boost_1_69_0 ~/boost_1_69_0
```

result:
```shell
boost_1_69_0.tar.gz  REPORT.md
```
__________

Current task: 3

3. Подсчитайте количество файлов в директории ` ~/boost_1_69_0`  не включая вложенные директории.


script:
```shell
$ find . -maxdepth 1 -type f | wc -l
```

result:
`12` 

_________

Current task: 4

Подсчитайте количество файлов в директории `~/boost_1_69_0`  включая вложенные директории.


script:
```shell
$ find . -type f | wc -l
```

result:
`61191`

_______

Current task: 5

5. Подсчитайте количество заголовочных файлов, файлов с расширением `.cpp`, сколько остальных файлов (не заголовочных и не `.cpp`).


script:
```shell
$ find . -name "*.png" | wc -l
```

result:
`2038`


script:
```shell
$ find -name "include" | wc -l
```

result:
`21 `

________

Current task: 6

6. Найдите полный путь до файла any.hpp внутри библиотеки _boost_. 


script:
```shell
$ find . -name "any.hpp"
```

result:
```
./proto/detail/any.hpp
./type_erasure/any.hpp
./fusion/include/any.hpp
./fusion/algorithm/query/detail/any.hpp
./fusion/algorithm/query/any.hpp
./hana/fwd/any.hpp
./hana/any.hpp
./xpressive/detail/utility/any.hpp
./spirit/home/support/algorithm/any.hpp
./any.hpp
```

_______

Current task: 7

7. Выведите в консоль все файлы, где упоминается последовательность `boost::asio`.

script:
```shell
grep -r "boost::asio" | wc -l
```

result: 
`4152`

_______

Current task: 8

8. Скомпилирутйе _boost_. Можно воспользоваться инструкцией или ссылкой.

script:



_______

Current task: 9

Перенесите все скомпилированные на предыдущем шаге статические библиотеки в директорию ` ~/boost-libs`.


script:


________

Current task: 10

Подсчитайте сколько занимает дискового пространства каждый файл в этой директории.


script:

________

Current task: 11

Найдите топ10 самых "тяжёлых".

script:
