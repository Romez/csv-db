# csvdb

[![Build Status](https://travis-ci.org/Romez/csv-db.svg?branch=master)](https://travis-ci.org/Romez/csv-db)

Задание: необходимо сделать простую базу данных на основе CSV-файлов. Файлы, с которыми предлагается работать в задании: student.csv, student_subject.csv, subject.csv. Эти три файла реализуют связи типа "многие-ко-многим", т.е. один student может изучать множество subject-ов, один subject может принадлежать множеству student-ов.

Заготовка кода представлена  в файле src/csvdb/core.clj. Поскольку это простая база данных, мы будем реализовывать только различные виды запроса select, например, такие:

     (select student
       :where #(> (:id %) 1)
       :order-by :year
       :limit 2)

    (select student-subject
      :limit 2
      :joins [[:student_id student :id] [:subject_id subject :id]])

Выполнять эти запросы нужно в REPL, поэтому никакой дополнительной системы ввода-вывода для консоли писать не нужно.

Часть функций в заготовке помечены ключевым словом :ImplementMe -- эти функции вам необходимо реализовать. Перед каждой такой функцией в комментариях дан пример вызова функций, а снизу, после знака => -- результат вызова этой функции. В комментарии, после слова Hint, дана подсказка: список clojure-функций, которые я использовал для реализации этой функции.

После того, как вы реализуете все функции, выполните команду 'lein test' и убедитесь, что тесты проходят.
      
## License

Copyright © 2014 Dmitry Bushenko

Distributed under the Eclipse Public License either version 1.0 or (at
your option) any later version.
