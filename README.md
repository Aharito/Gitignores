## Gitignores + workflow
 
Примеры разных workflows и .gitignore

### Папка 1. Разработка расширения для EvoCMS 1.4.x на локальном "живом" сайте

**Цель**: быстрая разработка расширения, которое можно будет устанавливать на 1.4.x через **Extras**.

**Описание**: Такой workflow удобен для **соло-разработки** и мгновенного тестирования расширения прямо в процессе. Файл .gitignore исключает из отправки на ГитХаб всё, кроме файлов самого дополнения. В удалённое репо не пойдут ни файлы CMS, ни специфичные файлы сайта. Отправляться и отслеживаться будут только файлы расширения.

#### По пунктам:

1. В локальном репо развернут dev-сайт на Evo 1.4.х для мгновенных тестов "на горячую", там и делаем расширение.
2. Настроен .gitignore, который из этого большого локального репо выбирает для отслеживания и отправки на ГитХаб всего 4-5-6 нужных файлов.
3. Также, создана папка install с файлом .tpl, нужная в 1.4.х для Экстрас, она работе на локалке не мешает.
4. Сделанные изменения идут на Гитхаб в соответствующее маленькое репо, которое и содержит эти 4-5-6 файлов расширения.
5. Если нужно, в корень того сайта, что служит подопытным кроликом, кладем README и LICENSE, они также отслеживаются и отпраляются в репо на ГитХаб.

Когда дополнение готово, локальное репо с сайтом и ЦМС можно *удалить* вместе с файлами, и потом клонировать на локалку с ГитХаба маленькое репо с готовым расширением.

### Папка 2. Разработка сайта на локалке

1. Данный `.gitignore` убирает из отслеживания все ненужные файлы и папки.
2. Конечно, он подходит не для всех случаев, но для большинства.
3. Под вопросом только картинки. В текущем проекте мне было нужно, чтобы картинки на данном этапе разработки отслеживались.
4. В общем случае это, конечно, ни к чему.