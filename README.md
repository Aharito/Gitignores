## Gitignores
 
Примеры файлов .gitignore для разных workflows.

### 1. Разработка расширения для EvoCMS 1.4.x на локальном "живом" сайте

**Цель**: разработка расширения, которое можно будет устанавливать на 1.4.x через Extras.

**Описание**: Разработка ведется на локалке, на "живом" сайте. Для этого на OpenServer разворачивается какой-либо "подопытный" сайт с нужным для разарботки контентом и функционалом. Сам сайт неважен, он служит лишь для мгновенного тестирования разрабатываемого расширения.

Такой workflow удобен для **соло-разработки** и мгновенного тестирования расширения прямо в процессе разработки на локалке. При этом файл .gitignore исключает из репо для отправки на ГитХаб всё, кроме файлов самого дополнения. То есть в удалённое репо не пойдут ни файлы CMS, ни специфичные файлы сайта. Отправляться и отслеживаться будут только фалы расширения

#### По пунктам:

1. В локальном репо неважно какой тестовый сайт на 1.4.х для мгновенных тестов живого расширения "на горячую", там и делаем расширение.
2. Настроен .gitignore, который из этого большого локального репо выбирает для отслеживания и отправки на ГитХаб всего 4-5-6 нужных файла.
3. Также, создана папка install с файлом .tpl, нужная в 1.4.х для Экстрас, она работе на локалке не мешает.
4. Сделанные изменения отправляю на Гитхаб в соответствующее маленькое репо, которое и содержит эти 4-5-6 файлов расширения.
5. В корень того сайта, что служит подопытным кроликом, кладем кому нужно README и LICENSE, они также отслеживаются и отпраляются в репо на ГитХаб.

Когда дополнение готово, локальное репо с сайтом и ЦМС можно удалить вместе с файлами, и потом клонировать на локалку с ГитХаба маоенькое репо с файлами расширения.

**Файл**: ExtensionDev_EvoCMS_1.4.x.gitignore
