# Разработка учебного проекта на Backbone
[Книга на gitbooks](https://ilya-matrosov.gitbook.io/backbone-intern-tasks/)

### Задачи

1. Создать проект на гитхабе. Разобраться с NPM, добавить package.json с backbone, jquery, lodash.
2. Настроить сборку scss, js используя webpack.
3. Сверстать форму ввода артикула.
4. Создать коллекцию для товаров.
5. Создать вью для формы поиска.
6. Добавить в проект Jasmine, написать тесты на модель и вью. Протестировать каждый метод. Все последующие задачи должны включать тесты.
7. Сверстать страницу товара с фото и характеристиками.
8. Создать модель и вью товара, реализовать вывод данных о товаре.
9. Реализовать вывод характеристик товара.
10. Реализовать вывод фото товара.
11. *Сверстать отзывы*.
12. *Создать коллекцию и вью для отзывов*.
13. *Реализовать вывод отзывов*.


#### Подготовка к работе.

- Установить расширение для браузера, разрешающее cross origin запросы (для работы с API).
- Установить node.js и git.
- Зарегистрироваться на github, сгенерировать ключи прописать в настройках.
- Создать новый проект на github.
- Посмотреть макеты [на яндекс-диске](https://yadi.sk/d/WIR1yuyI3a6GWQ).

#### Соглашения по оформлению.

+ Каждая задача должна быть выполнена в новой ветке и оформлена в пулл-реквест в репозиторий проекта.
+ Названия веток должны быть вида BB-*номер задачи* (например BB-1).
+ Название пулл-реквеста соответсвует названию ветки.  
+ В описании пулл-реквеста содержится описание того, что было сделано.


### 1. Создать проект на гитхабе. Разобраться с NPM, добавить package.json с backbone, jquery, lodash.

##### Подсказки:
- Папка node_modules не должна быть под гитом.
- Разобраться с назначением файлов .gitignore.

##### Результат: 
- Репозиторий с проектом (файлы package.json, .gitignore).
- Понимание работы с пакетами.
- Понимание назначения файла package.json, .gitignore.

### 2. Настроить сборку scss, js используя webpack.

##### Результат: 
- Файл настроек webpack.
- Исходные файлы js и scss, index.html с подключенными стилями и скриптами.
- Папка для результатов сборки.

##### Подсказки:
- Результаты сборки не должны быть под гитом.
- В результате сборки должен получаться один файл со скриптами и один файл со стилями.

### 3. Сверстать форму ввода артикула

##### Результат:
- Форма ввода артикула должна соответствовать макетам.

### 4. Создать коллекцию для товаров 
     Пример запроса на API: https://www.sima-land.ru/api/v3/item/?sid=123456,1005002

##### Результат:
- Созданы файлы вью и коллекции для товаров.
- При открытии страницы отправляется запрос на сервер, в консоль выводится заполненная коллекция.

##### Подсказки:
- Расширять коллекцию от `Backbone.Collection`.
- Для корректного заполнения коллекции необходимо переопределить метод `parse`.
- Прочитать про систему событий Backbone. Изучить, как работают коллекции, в какой момент происходит событие sync.  
- Свойство url может быть строкой или функцией.

### 5. Создать вью для формы поиска.

##### Подсказки:
- Расширять вью от `Backbone.View`.
- Изучить синтаксис lodash-шаблонов.
- Создать lodash-шаблон в теге `<script>`.
- Создать метод render, использовать `$.html()` для вставки новой разметки в элемент.

##### Изменения в запросе к API:
- Добавить к запросу товаров `&expand=photo_sizes,description` для получения описания товара и информации о размерах фото.
- Ссылки на фото товара приходят в массиве `photos`, информация о версиях фото в массиве `photoVersions`.
- Адрес фото товара строится по шаблону:
`PHOTO_PART/PHOTO_INDEX/PHOTO_SIZE.jpg?v=PHOTO_VERSION`.
- Пример адреса фотографии товара:
`https://cdn2.static1-sima-land.com/items/802893/0/700.jpg?v=0`.


### 6. Добавить в проект Jasmine, написать тесты на модель и вью. Протестировать каждый метод. Все последующие задачи должны включать тесты.

##### Результат:
- Два файла тестов (для вью и коллекции).
- Подключенный karma и jasmine.

##### Подсказки:
- Разобраться с методами фреймворка для тестов: beforeEach, afterEach, spyOn, expect.
