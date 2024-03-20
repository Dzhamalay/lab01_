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
$ find . -name "*.cpp" | wc -l
```

result:
`13789`


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

8. Скомпилирутйе _boost_.

script:
$ ./bootstrap.sh --prefix=boost_output
$ ./b2 install

_______

Current task: 9

Перенесите все скомпилированные на предыдущем шаге статические библиотеки в директорию ` ~/boost-libs`.


script:
$ mv lib ~/boost-lib

________

Current task: 10

Подсчитайте сколько занимает дискового пространства каждый файл в этой директории.


script:
```shel
ls -lh
```

result:
```shell
total 36M
-rw-rw-r-- 1 jamalay jamalay 2,6K мар 20 10:20 libboost_atomic.a
lrwxrwxrwx 1 jamalay jamalay   25 мар 20 10:27 libboost_atomic.so -> libboost_atomic.so.1.69.0
-rwxrwxr-x 1 jamalay jamalay  16K мар 20 10:27 libboost_atomic.so.1.69.0
-rw-rw-r-- 1 jamalay jamalay 236K мар 20 10:35 libboost_chrono.a
lrwxrwxrwx 1 jamalay jamalay   25 мар 20 10:27 libboost_chrono.so -> libboost_chrono.so.1.69.0
-rwxrwxr-x 1 jamalay jamalay  61K мар 20 10:27 libboost_chrono.so.1.69.0
-rw-rw-r-- 1 jamalay jamalay 147K мар 20 10:20 libboost_container.a
lrwxrwxrwx 1 jamalay jamalay   28 мар 20 10:27 libboost_container.so -> libboost_container.so.1.69.0
-rwxrwxr-x 1 jamalay jamalay 104K мар 20 10:27 libboost_container.so.1.69.0
-rw-rw-r-- 1 jamalay jamalay  21K мар 20 10:20 libboost_context.a
lrwxrwxrwx 1 jamalay jamalay   26 мар 20 10:27 libboost_context.so -> libboost_context.so.1.69.0
-rwxrwxr-x 1 jamalay jamalay  24K мар 20 10:27 libboost_context.so.1.69.0
-rw-rw-r-- 1 jamalay jamalay 344K мар 20 10:20 libboost_contract.a
lrwxrwxrwx 1 jamalay jamalay   27 мар 20 10:27 libboost_contract.so -> libboost_contract.so.1.69.0
-rwxrwxr-x 1 jamalay jamalay 185K мар 20 10:27 libboost_contract.so.1.69.0
-rw-rw-r-- 1 jamalay jamalay 150K мар 20 10:20 libboost_date_time.a
lrwxrwxrwx 1 jamalay jamalay   28 мар 20 10:27 libboost_date_time.so -> libboost_date_time.so.1.69.0
-rwxrwxr-x 1 jamalay jamalay  89K мар 20 10:27 libboost_date_time.so.1.69.0
-rw-rw-r-- 1 jamalay jamalay 1,7K мар 20 10:35 libboost_exception.a
-rw-rw-r-- 1 jamalay jamalay 239K мар 20 10:21 libboost_fiber.a
lrwxrwxrwx 1 jamalay jamalay   24 мар 20 10:28 libboost_fiber.so -> libboost_fiber.so.1.69.0
-rwxrwxr-x 1 jamalay jamalay 100K мар 20 10:28 libboost_fiber.so.1.69.0
-rw-rw-r-- 1 jamalay jamalay 414K мар 20 10:20 libboost_filesystem.a
lrwxrwxrwx 1 jamalay jamalay   29 мар 20 10:27 libboost_filesystem.so -> libboost_filesystem.so.1.69.0
-rwxrwxr-x 1 jamalay jamalay 153K мар 20 10:27 libboost_filesystem.so.1.69.0
-rw-rw-r-- 1 jamalay jamalay 880K мар 20 10:21 libboost_graph.a
lrwxrwxrwx 1 jamalay jamalay   24 мар 20 10:29 libboost_graph.so -> libboost_graph.so.1.69.0
-rwxrwxr-x 1 jamalay jamalay 412K мар 20 10:29 libboost_graph.so.1.69.0
-rw-rw-r-- 1 jamalay jamalay 172K мар 20 10:21 libboost_iostreams.a
lrwxrwxrwx 1 jamalay jamalay   28 мар 20 10:29 libboost_iostreams.so -> libboost_iostreams.so.1.69.0
-rwxrwxr-x 1 jamalay jamalay  88K мар 20 10:29 libboost_iostreams.so.1.69.0
-rw-rw-r-- 1 jamalay jamalay 579K мар 20 10:25 libboost_math_c99.a
-rw-rw-r-- 1 jamalay jamalay 488K мар 20 10:25 libboost_math_c99f.a
lrwxrwxrwx 1 jamalay jamalay   28 мар 20 10:32 libboost_math_c99f.so -> libboost_math_c99f.so.1.69.0
-rwxrwxr-x 1 jamalay jamalay  88K мар 20 10:32 libboost_math_c99f.so.1.69.0
-rw-rw-r-- 1 jamalay jamalay 501K мар 20 10:25 libboost_math_c99l.a
lrwxrwxrwx 1 jamalay jamalay   28 мар 20 10:32 libboost_math_c99l.so -> libboost_math_c99l.so.1.69.0
-rwxrwxr-x 1 jamalay jamalay  88K мар 20 10:32 libboost_math_c99l.so.1.69.0
lrwxrwxrwx 1 jamalay jamalay   27 мар 20 10:32 libboost_math_c99.so -> libboost_math_c99.so.1.69.0
-rwxrwxr-x 1 jamalay jamalay 106K мар 20 10:32 libboost_math_c99.so.1.69.0
-rw-rw-r-- 1 jamalay jamalay 2,8M мар 20 10:24 libboost_math_tr1.a
-rw-rw-r-- 1 jamalay jamalay 2,8M мар 20 10:24 libboost_math_tr1f.a
lrwxrwxrwx 1 jamalay jamalay   28 мар 20 10:31 libboost_math_tr1f.so -> libboost_math_tr1f.so.1.69.0
-rwxrwxr-x 1 jamalay jamalay 550K мар 20 10:31 libboost_math_tr1f.so.1.69.0
-rw-rw-r-- 1 jamalay jamalay 2,8M мар 20 10:24 libboost_math_tr1l.a
lrwxrwxrwx 1 jamalay jamalay   28 мар 20 10:32 libboost_math_tr1l.so -> libboost_math_tr1l.so.1.69.0
-rwxrwxr-x 1 jamalay jamalay 552K мар 20 10:32 libboost_math_tr1l.so.1.69.0
lrwxrwxrwx 1 jamalay jamalay   27 мар 20 10:31 libboost_math_tr1.so -> libboost_math_tr1.so.1.69.0
-rwxrwxr-x 1 jamalay jamalay 562K мар 20 10:31 libboost_math_tr1.so.1.69.0
-rw-rw-r-- 1 jamalay jamalay 216K мар 20 10:26 libboost_prg_exec_monitor.a
lrwxrwxrwx 1 jamalay jamalay   35 мар 20 10:33 libboost_prg_exec_monitor.so -> libboost_prg_exec_monitor.so.1.69.0
-rwxrwxr-x 1 jamalay jamalay 116K мар 20 10:33 libboost_prg_exec_monitor.so.1.69.0
-rw-rw-r-- 1 jamalay jamalay 1,6M мар 20 10:25 libboost_program_options.a
lrwxrwxrwx 1 jamalay jamalay   34 мар 20 10:32 libboost_program_options.so -> libboost_program_options.so.1.69.0
-rwxrwxr-x 1 jamalay jamalay 693K мар 20 10:32 libboost_program_options.so.1.69.0
-rw-rw-r-- 1 jamalay jamalay  81K мар 20 10:25 libboost_random.a
lrwxrwxrwx 1 jamalay jamalay   25 мар 20 10:32 libboost_random.so -> libboost_random.so.1.69.0
-rwxrwxr-x 1 jamalay jamalay  56K мар 20 10:32 libboost_random.so.1.69.0
-rw-rw-r-- 1 jamalay jamalay 3,1M мар 20 10:21 libboost_regex.a
lrwxrwxrwx 1 jamalay jamalay   24 мар 20 10:28 libboost_regex.so -> libboost_regex.so.1.69.0
-rwxrwxr-x 1 jamalay jamalay 1,3M мар 20 10:28 libboost_regex.so.1.69.0
-rw-rw-r-- 1 jamalay jamalay 1,2M мар 20 10:25 libboost_serialization.a
lrwxrwxrwx 1 jamalay jamalay   32 мар 20 10:33 libboost_serialization.so -> libboost_serialization.so.1.69.0
-rwxrwxr-x 1 jamalay jamalay 480K мар 20 10:33 libboost_serialization.so.1.69.0
-rw-rw-r-- 1 jamalay jamalay  22K мар 20 10:26 libboost_stacktrace_addr2line.a
lrwxrwxrwx 1 jamalay jamalay   39 мар 20 10:33 libboost_stacktrace_addr2line.so -> libboost_stacktrace_addr2line.so.1.69.0
-rwxrwxr-x 1 jamalay jamalay  32K мар 20 10:33 libboost_stacktrace_addr2line.so.1.69.0
-rw-rw-r-- 1 jamalay jamalay  21K мар 20 10:26 libboost_stacktrace_backtrace.a
lrwxrwxrwx 1 jamalay jamalay   39 мар 20 10:33 libboost_stacktrace_backtrace.so -> libboost_stacktrace_backtrace.so.1.69.0
-rwxrwxr-x 1 jamalay jamalay  91K мар 20 10:33 libboost_stacktrace_backtrace.so.1.69.0
-rw-rw-r-- 1 jamalay jamalay  13K мар 20 10:26 libboost_stacktrace_basic.a
lrwxrwxrwx 1 jamalay jamalay   35 мар 20 10:33 libboost_stacktrace_basic.so -> libboost_stacktrace_basic.so.1.69.0
-rwxrwxr-x 1 jamalay jamalay  22K мар 20 10:33 libboost_stacktrace_basic.so.1.69.0
-rw-rw-r-- 1 jamalay jamalay 2,8K мар 20 10:26 libboost_stacktrace_noop.a
lrwxrwxrwx 1 jamalay jamalay   34 мар 20 10:33 libboost_stacktrace_noop.so -> libboost_stacktrace_noop.so.1.69.0
-rwxrwxr-x 1 jamalay jamalay  16K мар 20 10:33 libboost_stacktrace_noop.so.1.69.0
-rw-rw-r-- 1 jamalay jamalay 1,5K мар 20 10:35 libboost_system.a
lrwxrwxrwx 1 jamalay jamalay   25 мар 20 10:27 libboost_system.so -> libboost_system.so.1.69.0
-rwxrwxr-x 1 jamalay jamalay  15K мар 20 10:27 libboost_system.so.1.69.0
-rw-rw-r-- 1 jamalay jamalay 2,3M мар 20 10:35 libboost_test_exec_monitor.a
-rw-rw-r-- 1 jamalay jamalay  56K мар 20 10:35 libboost_timer.a
lrwxrwxrwx 1 jamalay jamalay   24 мар 20 10:33 libboost_timer.so -> libboost_timer.so.1.69.0
-rwxrwxr-x 1 jamalay jamalay  49K мар 20 10:33 libboost_timer.so.1.69.0
-rw-rw-r-- 1 jamalay jamalay 2,3M мар 20 10:26 libboost_unit_test_framework.a
lrwxrwxrwx 1 jamalay jamalay   38 мар 20 10:34 libboost_unit_test_framework.so -> libboost_unit_test_framework.so.1.69.0
-rwxrwxr-x 1 jamalay jamalay 954K мар 20 10:34 libboost_unit_test_framework.so.1.69.0
-rw-rw-r-- 1 jamalay jamalay 4,6M мар 20 10:27 libboost_wave.a
-rw-rw-r-- 1 jamalay jamalay 780K мар 20 10:26 libboost_wserialization.a
lrwxrwxrwx 1 jamalay jamalay   33 мар 20 10:33 libboost_wserialization.so -> libboost_wserialization.so.1.69.0
-rwxrwxr-x 1 jamalay jamalay 331K мар 20 10:33 libboost_wserialization.so.1.69.0
jamalay@jamalay-VirtualBox:~/boost-libs/lib$ ls -hl
total 36M
-rw-rw-r-- 1 jamalay jamalay 2,6K мар 20 10:20 libboost_atomic.a
lrwxrwxrwx 1 jamalay jamalay   25 мар 20 10:27 libboost_atomic.so -> libboost_atomic.so.1.69.0
-rwxrwxr-x 1 jamalay jamalay  16K мар 20 10:27 libboost_atomic.so.1.69.0
-rw-rw-r-- 1 jamalay jamalay 236K мар 20 10:35 libboost_chrono.a
lrwxrwxrwx 1 jamalay jamalay   25 мар 20 10:27 libboost_chrono.so -> libboost_chrono.so.1.69.0
-rwxrwxr-x 1 jamalay jamalay  61K мар 20 10:27 libboost_chrono.so.1.69.0
-rw-rw-r-- 1 jamalay jamalay 147K мар 20 10:20 libboost_container.a
lrwxrwxrwx 1 jamalay jamalay   28 мар 20 10:27 libboost_container.so -> libboost_container.so.1.69.0
-rwxrwxr-x 1 jamalay jamalay 104K мар 20 10:27 libboost_container.so.1.69.0
-rw-rw-r-- 1 jamalay jamalay  21K мар 20 10:20 libboost_context.a
lrwxrwxrwx 1 jamalay jamalay   26 мар 20 10:27 libboost_context.so -> libboost_context.so.1.69.0
-rwxrwxr-x 1 jamalay jamalay  24K мар 20 10:27 libboost_context.so.1.69.0
-rw-rw-r-- 1 jamalay jamalay 344K мар 20 10:20 libboost_contract.a
lrwxrwxrwx 1 jamalay jamalay   27 мар 20 10:27 libboost_contract.so -> libboost_contract.so.1.69.0
-rwxrwxr-x 1 jamalay jamalay 185K мар 20 10:27 libboost_contract.so.1.69.0
-rw-rw-r-- 1 jamalay jamalay 150K мар 20 10:20 libboost_date_time.a
lrwxrwxrwx 1 jamalay jamalay   28 мар 20 10:27 libboost_date_time.so -> libboost_date_time.so.1.69.0
-rwxrwxr-x 1 jamalay jamalay  89K мар 20 10:27 libboost_date_time.so.1.69.0
-rw-rw-r-- 1 jamalay jamalay 1,7K мар 20 10:35 libboost_exception.a
-rw-rw-r-- 1 jamalay jamalay 239K мар 20 10:21 libboost_fiber.a
lrwxrwxrwx 1 jamalay jamalay   24 мар 20 10:28 libboost_fiber.so -> libboost_fiber.so.1.69.0
-rwxrwxr-x 1 jamalay jamalay 100K мар 20 10:28 libboost_fiber.so.1.69.0
-rw-rw-r-- 1 jamalay jamalay 414K мар 20 10:20 libboost_filesystem.a
lrwxrwxrwx 1 jamalay jamalay   29 мар 20 10:27 libboost_filesystem.so -> libboost_filesystem.so.1.69.0
-rwxrwxr-x 1 jamalay jamalay 153K мар 20 10:27 libboost_filesystem.so.1.69.0
-rw-rw-r-- 1 jamalay jamalay 880K мар 20 10:21 libboost_graph.a
lrwxrwxrwx 1 jamalay jamalay   24 мар 20 10:29 libboost_graph.so -> libboost_graph.so.1.69.0
-rwxrwxr-x 1 jamalay jamalay 412K мар 20 10:29 libboost_graph.so.1.69.0
-rw-rw-r-- 1 jamalay jamalay 172K мар 20 10:21 libboost_iostreams.a
lrwxrwxrwx 1 jamalay jamalay   28 мар 20 10:29 libboost_iostreams.so -> libboost_iostreams.so.1.69.0
-rwxrwxr-x 1 jamalay jamalay  88K мар 20 10:29 libboost_iostreams.so.1.69.0
-rw-rw-r-- 1 jamalay jamalay 579K мар 20 10:25 libboost_math_c99.a
-rw-rw-r-- 1 jamalay jamalay 488K мар 20 10:25 libboost_math_c99f.a
lrwxrwxrwx 1 jamalay jamalay   28 мар 20 10:32 libboost_math_c99f.so -> libboost_math_c99f.so.1.69.0
-rwxrwxr-x 1 jamalay jamalay  88K мар 20 10:32 libboost_math_c99f.so.1.69.0
-rw-rw-r-- 1 jamalay jamalay 501K мар 20 10:25 libboost_math_c99l.a
lrwxrwxrwx 1 jamalay jamalay   28 мар 20 10:32 libboost_math_c99l.so -> libboost_math_c99l.so.1.69.0
-rwxrwxr-x 1 jamalay jamalay  88K мар 20 10:32 libboost_math_c99l.so.1.69.0
lrwxrwxrwx 1 jamalay jamalay   27 мар 20 10:32 libboost_math_c99.so -> libboost_math_c99.so.1.69.0
-rwxrwxr-x 1 jamalay jamalay 106K мар 20 10:32 libboost_math_c99.so.1.69.0
-rw-rw-r-- 1 jamalay jamalay 2,8M мар 20 10:24 libboost_math_tr1.a
-rw-rw-r-- 1 jamalay jamalay 2,8M мар 20 10:24 libboost_math_tr1f.a
lrwxrwxrwx 1 jamalay jamalay   28 мар 20 10:31 libboost_math_tr1f.so -> libboost_math_tr1f.so.1.69.0
-rwxrwxr-x 1 jamalay jamalay 550K мар 20 10:31 libboost_math_tr1f.so.1.69.0
-rw-rw-r-- 1 jamalay jamalay 2,8M мар 20 10:24 libboost_math_tr1l.a
lrwxrwxrwx 1 jamalay jamalay   28 мар 20 10:32 libboost_math_tr1l.so -> libboost_math_tr1l.so.1.69.0
-rwxrwxr-x 1 jamalay jamalay 552K мар 20 10:32 libboost_math_tr1l.so.1.69.0
lrwxrwxrwx 1 jamalay jamalay   27 мар 20 10:31 libboost_math_tr1.so -> libboost_math_tr1.so.1.69.0
-rwxrwxr-x 1 jamalay jamalay 562K мар 20 10:31 libboost_math_tr1.so.1.69.0
-rw-rw-r-- 1 jamalay jamalay 216K мар 20 10:26 libboost_prg_exec_monitor.a
lrwxrwxrwx 1 jamalay jamalay   35 мар 20 10:33 libboost_prg_exec_monitor.so -> libboost_prg_exec_monitor.so.1.69.0
-rwxrwxr-x 1 jamalay jamalay 116K мар 20 10:33 libboost_prg_exec_monitor.so.1.69.0
-rw-rw-r-- 1 jamalay jamalay 1,6M мар 20 10:25 libboost_program_options.a
lrwxrwxrwx 1 jamalay jamalay   34 мар 20 10:32 libboost_program_options.so -> libboost_program_options.so.1.69.0
-rwxrwxr-x 1 jamalay jamalay 693K мар 20 10:32 libboost_program_options.so.1.69.0
-rw-rw-r-- 1 jamalay jamalay  81K мар 20 10:25 libboost_random.a
lrwxrwxrwx 1 jamalay jamalay   25 мар 20 10:32 libboost_random.so -> libboost_random.so.1.69.0
-rwxrwxr-x 1 jamalay jamalay  56K мар 20 10:32 libboost_random.so.1.69.0
-rw-rw-r-- 1 jamalay jamalay 3,1M мар 20 10:21 libboost_regex.a
lrwxrwxrwx 1 jamalay jamalay   24 мар 20 10:28 libboost_regex.so -> libboost_regex.so.1.69.0
-rwxrwxr-x 1 jamalay jamalay 1,3M мар 20 10:28 libboost_regex.so.1.69.0
-rw-rw-r-- 1 jamalay jamalay 1,2M мар 20 10:25 libboost_serialization.a
lrwxrwxrwx 1 jamalay jamalay   32 мар 20 10:33 libboost_serialization.so -> libboost_serialization.so.1.69.0
-rwxrwxr-x 1 jamalay jamalay 480K мар 20 10:33 libboost_serialization.so.1.69.0
-rw-rw-r-- 1 jamalay jamalay  22K мар 20 10:26 libboost_stacktrace_addr2line.a
lrwxrwxrwx 1 jamalay jamalay   39 мар 20 10:33 libboost_stacktrace_addr2line.so -> libboost_stacktrace_addr2line.so.1.69.0
-rwxrwxr-x 1 jamalay jamalay  32K мар 20 10:33 libboost_stacktrace_addr2line.so.1.69.0
-rw-rw-r-- 1 jamalay jamalay  21K мар 20 10:26 libboost_stacktrace_backtrace.a
lrwxrwxrwx 1 jamalay jamalay   39 мар 20 10:33 libboost_stacktrace_backtrace.so -> libboost_stacktrace_backtrace.so.1.69.0
-rwxrwxr-x 1 jamalay jamalay  91K мар 20 10:33 libboost_stacktrace_backtrace.so.1.69.0
-rw-rw-r-- 1 jamalay jamalay  13K мар 20 10:26 libboost_stacktrace_basic.a
lrwxrwxrwx 1 jamalay jamalay   35 мар 20 10:33 libboost_stacktrace_basic.so -> libboost_stacktrace_basic.so.1.69.0
-rwxrwxr-x 1 jamalay jamalay  22K мар 20 10:33 libboost_stacktrace_basic.so.1.69.0
-rw-rw-r-- 1 jamalay jamalay 2,8K мар 20 10:26 libboost_stacktrace_noop.a
lrwxrwxrwx 1 jamalay jamalay   34 мар 20 10:33 libboost_stacktrace_noop.so -> libboost_stacktrace_noop.so.1.69.0
-rwxrwxr-x 1 jamalay jamalay  16K мар 20 10:33 libboost_stacktrace_noop.so.1.69.0
-rw-rw-r-- 1 jamalay jamalay 1,5K мар 20 10:35 libboost_system.a
lrwxrwxrwx 1 jamalay jamalay   25 мар 20 10:27 libboost_system.so -> libboost_system.so.1.69.0
-rwxrwxr-x 1 jamalay jamalay  15K мар 20 10:27 libboost_system.so.1.69.0
-rw-rw-r-- 1 jamalay jamalay 2,3M мар 20 10:35 libboost_test_exec_monitor.a
-rw-rw-r-- 1 jamalay jamalay  56K мар 20 10:35 libboost_timer.a
lrwxrwxrwx 1 jamalay jamalay   24 мар 20 10:33 libboost_timer.so -> libboost_timer.so.1.69.0
-rwxrwxr-x 1 jamalay jamalay  49K мар 20 10:33 libboost_timer.so.1.69.0
-rw-rw-r-- 1 jamalay jamalay 2,3M мар 20 10:26 libboost_unit_test_framework.a
lrwxrwxrwx 1 jamalay jamalay   38 мар 20 10:34 libboost_unit_test_framework.so -> libboost_unit_test_framework.so.1.69.0
-rwxrwxr-x 1 jamalay jamalay 954K мар 20 10:34 libboost_unit_test_framework.so.1.69.0
-rw-rw-r-- 1 jamalay jamalay 4,6M мар 20 10:27 libboost_wave.a
-rw-rw-r-- 1 jamalay jamalay 780K мар 20 10:26 libboost_wserialization.a
lrwxrwxrwx 1 jamalay jamalay   33 мар 20 10:33 libboost_wserialization.so -> libboost_wserialization.so.1.69.0
-rwxrwxr-x 1 jamalay jamalay 331K мар 20 10:33 libboost_wserialization.so.1.69.0
```


________

Current task: 11

Найдите топ10 самых "тяжёлых".

script:
$ find . -type f -size +1000k

result:
./libboost_serialization.a
./libboost_test_exec_monitor.a
./libboost_regex.a
./libboost_program_options.a
./libboost_math_tr1f.a
./libboost_regex.so.1.69.0
./libboost_wave.a
./libboost_math_tr1.a
./libboost_math_tr1l.a
./libboost_unit_test_framework.a
_______

