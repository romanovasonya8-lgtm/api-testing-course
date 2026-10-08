## Met1
- POST /posts -> 201 Created, { "id": 101, ... }
- GET /posts/101 → 404 Not Found
- вывод: запись не сохранилась, песочница имитирует создание

HTTP/1.1 201 Created
Date: Thu, 08 Oct 2026 11:45:30 GMT
Content-Type: application/json; charset=utf-8
Content-Length: 84

HTTP/1.1 200 OK
Date: Thu, 08 Oct 2026 11:48:07 GMT
Content-Type: application/json; charset=utf-8
Content-Length: 499
