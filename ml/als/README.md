Для более чёткого описания сопровождаю ноутбук постанвкой задачи от организаторов курса NewProLab.

В итоге задача была решена через [libfm](http://www.libfm.org/libfm-1.42.manual.pdf), а результат оказался лучшим на курсе


### Задача

В вашем распоряжении имеется уже предобработанный и очищенный датасет с фактами
покупок абонентами телепередач от компании E-Contenta. По доступным вам данным нужно предсказать вероятность покупки других передач этими, а, возможно, и другими абонентами.

### Обработка данных на вход



- В `lab10_train.csv` содержатся факты покупки (колонка `purchase`) пользователями (колонка `user_id`) телепередач (колонка `item_id`). Такой формат файла вам уже знаком.

- `lab10_items.csv` — дополнительные данные по items. В данном файле много лишней или ненужной информации, так что задача её фильтрации и отбора ложится на вас. Поля в файле, на которых хотелось бы остановиться:
  - `item_id` — primary key. Соответствует `item_id` в предыдущем файле.
  - `content_type` — тип телепередачи (`1` — платная, `0` — бесплатная). Вас интересуют платные передачи.
  - `title` — название передачи, текстовое поле.
  - `year` — год выпуска передачи, число.
  - `genres` — поле с жанрами передачи, разделёнными через запятую.
- `lab10_test.csv` — тестовый датасет без указанного целевого признака `purchase`, который вам и предстоит предсказать.
- Дополнительный файл `lab10_views_programmes.csv` по просмотрам передач с полями:
  - `ts_start` — время начала просмотра
  - `ts_end` — время окончания просмотра
  - `item_type`— тип просматриваемого контента:
    - `live` — просмотр "вживую", в момент показа контента в эфире
    - `pvr` — просмотр в записи, после показа контента в эфире

### Обработка данных на выход

Предсказание целевой переменной "купит/не купит".
