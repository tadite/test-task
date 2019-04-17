## Макет
![Макет](https://raw.githubusercontent.com/tadite/demo/master/test-project4.png)


## Задания  
Реализовать SPA с использованием следующих технологий: React, Redux, Typescript, react-router, redux-thunk(или аналоги), axios(или аналоги), html5, css(или css-препроцессоры) 
### 1. Верстка, рендер карточек и работа с api    
Сделать верстку по макету(иконки, изображения и данные, которых нет на апи могут быть произвольными, не обязательно верстать один в один, но структура страницы должна соответствовать макет).  
Отрендерить карточки из получаемых от апи данных по примеру из макета.  
Для отображения картинки на карточке можно использовать первый preview и при наведении показывать элементы для навигации по остальным preview.  
Реализовать пагинацию с помощью запросов с параметром _page.   

необходимые данные надо получать от апи: /items - основной массив, /authors - юзернейм по id из свойства author, /tags - названия тегов, /previews - url картинок из массива previews для их показа в карусели карточки.  

### 2. Реализовать фильтры и сортировку  
Фильтрацию ао автору или по типу при выборе из выпадающего списка.  
Сортировка по полю downloads при нажатии на кнопку "Сначала популярные".   
Пример запроса к апи с сортировкой и фильтрами: /items?type=1&author=2&_sort=downloads&_order=desc  

### 3. Реализовать пути с помощью react-router  
При нажатии на кнопки слева (Предметы, Настройки, Уведомления) должен происходить переход на другие страницы с помощью history, Switch, Route в react-router. Информация на этих страницах не важна, проверяется знание роутера.

### 4. Страница предмета  
Используя react-router реализовать параметризованный путь (предположительно /items/:itemId) и переходы по этому пути при нажатии на карточки. По этому пути произвольным образом можно выводить полную информацию о предмете включая теги и описание.

### 5. Поиск  
Реализовать поиск с выпадающим списком подсказок с помощью запроса с использованием параметра q у апи. При нажатии на подсказку происходит переход к странице item'а.  

Пример запрос для поиска: /items?q=Test 22

## API
Api url: https://my-json-server.typicode.com/tadite/test-task
### resources:
#### Items:  
Запрос: GET /items  
```json
[
    {
        "id": 1,
        "author": 1,
        "name": "Test 1",
        "desc": "desc 1",
        "tags": [
            1
        ],
        "downloads": 33,
        "previews": [
            3,
            9
        ],
        "type": 1
    },
]
```  
##### Возможные пути (работают для всех ресурсов):  
Получить item по id=5: GET /items/5  
Пагинация: GET /items?_page=1  
Фильтрация: GET /items?type=1  
Пагинация+Фильтрация по типу: GET /items?type=1&_page=1  
Полнотекстовый поиск: GET /items?q=Test 22

#### Authors:  
Запрос: GET /authors  
```json
[
  {
    "id": 1,
    "username": "admin"
  },
]
```    

#### Types:  
Запрос: GET /types  
```json
[
  {
    "id": 1,
    "name": "type1"
  },
]
```  

#### Tags:  
Запрос: GET /tags  
```json
[
  {
    "id": 1,
    "name": "tag1"
  },
]
```  

#### Previews:  
Запрос: GET /previews  
```json
[
  {
    "id": 1,
    "url": "https://picsum.photos/500/200?image=61"
  },
]
```  
