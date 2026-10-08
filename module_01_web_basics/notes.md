Web2

- Статус: 200
- Имя: Leanne Graham
- Почта: Sincere@april.biz

Web3

- Метод: GET
- Статус: 200
- Content-Type: application/json; charset=utf-8
- Пользователей: 10
- Запрос со статусом ≠ 200: нет

Web4

- Комментариев: 5
- С postId=5: 5

Web5

- Объектов: 3
- id: 1, 2, 3

Web6

- postId=3: 5 комментариев
- postId=4: 5 комментариев
- Вывод: параметр postId фильтрует комментарии по номеру поста, к которому они относятся

Web7

- Гипотеза: limit ограничивает число объектов в ответе
- limit=2: 2 объекта
- limit=7: 7 объектов

  Web9
  
- GET /users/2/posts: 10 объектов, первый id = 11
- GET /posts?userId=2: 10 объектов, первый id = 11
- Вывод: одни и те же данные получены двумя разными дорогами — через вложенный путь /users/2/posts и через фильтр /posts?userId=2

  Web10
  
- GET /users/1 → 200
- GET /users/11 → 404 Not Found
- GET /users/1?foo=bar → 200
- Вывод: ресурс ломает путь (пользователя №11 нет → 404), а query-параметр на выбор ресурса не влияет (200)

  Web11
    
- Postman GET /users:
  - Content-Type: application/json; charset=utf-8
  - Content-Length: ~2.71 KB (2775 байт, отображается в Postman как размер ответа)
- DevTools HTML-страница: Content-Type: text/html; charset=utf-8
- DevTools JSON-ответ: Content-Type: application/json; charset=utf-8
- Вывод: Content-Type различается для HTML и JSON — сервер сообщает клиенту тип тела ответа

  Web12
  
- GET /todos?limit=5&page=1: 5 объектов, первый id = 1
- GET /todos?limit=5&page=2: 5 объектов, первый id = 6
- _page указывает номер страницы, _limit — размер страницы (сколько объектов на одной странице)
