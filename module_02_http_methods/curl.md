## Met2

### POST /posts

Команда:
curl -i --ssl-no-revoke -X POST https://jsonplaceholder.typicode.com/posts -H "Content-Type: application/json" -d "{\"title\": \"Мой пост\", \"body\": \"Текст\", \"userId\": 1}"

Вывод:
HTTP/1.1 201 Created
Content-Type: application/json; charset=utf-8
Content-Length: 84

### PATCH /users/1

Команда:
curl -i --ssl-no-revoke -X PATCH https://jsonplaceholder.typicode.com/users/1 -H "Content-Type: application/json" -d "{\"name\": \"Ada\"}"

Вывод:
HTTP/1.1 200 OK
Content-Type: application/json; charset=utf-8
Content-Length: 499
