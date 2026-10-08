Met2
POST /posts

Команда:
curl -i --ssl-no-revoke -X POST https://jsonplaceholder.typicode.com/posts -H "Content-Type: application/json" -d "{\"title\": \"Мой пост\", \"body\": \"Текст\", \"userId\": 1}"

Вывод:
HTTP/1.1 201 Created
Content-Type: application/json; charset=utf-8
Content-Length: 84

PATCH /users/1

Команда:
curl -i --ssl-no-revoke -X PATCH https://jsonplaceholder.typicode.com/users/1 -H "Content-Type: application/json" -d "{\"name\": \"Ada\"}"

Вывод:
HTTP/1.1 200 OK
Content-Type: application/json; charset=utf-8
Content-Length: 499

Met8
POST /posts
Команда:
curl -i --ssl-no-revoke -X POST https://jsonplaceholder.typicode.com/posts -H "Content-Type: application/json" -d "{\"title\": \"Мой пост\", \"body\": \"Текст\", \"userId\": 1}"
Вывод:
HTTP/1.1 201 Created
Content-Type: application/json; charset=utf-8
Content-Length: 84

GET /users/3
Команда:
curl -i --ssl-no-revoke https://jsonplaceholder.typicode.com/users/3
Вывод:
HTTP/1.1 200 OK
Content-Type: application/json; charset=utf-8
Content-Length: 520

Met9
С Accept
Команда:
curl -i --ssl-no-revoke -H "Accept: application/json" https://jsonplaceholder.typicode.com/users/1
Вывод:
HTTP/1.1 200 OK
Content-Type: application/json; charset=utf-8
Начало тела:"id": 1,"name": "Leanne Graham","username": "Bret","email": "Sincere@april.biz",

Без Accept
Команда:
curl -i --ssl-no-revoke https://jsonplaceholder.typicode.com/users/1
Вывод:
HTTP/1.1 200 OK
Content-Type: application/json; charset=utf-8
Начало тела:"id": 1,"name": "Leanne Graham","username": "Bret","email": "Sincere@april.biz",

