## Json1

| Путь | Значение | Тип |
|------|----------|-----|
| address.city | Казань | строка |
| scores[0] | 5 | число |
| scores[2] | 5 | число |
| active | true | булево |
| comment | null | null |
| groups[1].name | QA-2 | строка |

## Json2

| № | Ошибка | Исправлено |
|---|--------|------------|
| 1 | ключ в одинарных кавычках | `{ "name": "Анна" }` |
| 2 | ключ без кавычек | `{ "name": "Анна" }` |
| 3 | лишняя запятая после последней пары | `{ "a": 1, "b": 2 }` |
| 4 | пропущена запятая между парами | `{ "a": 1, "b": 2 }` |
| 5 | не закрыта строка и объект | `{ "a": "незакрытая" }` |

## Json3

| Путь | Значение | Тип | Признак |
|------|----------|-----|---------|
| address.geo.lat | "-37.3159" | строка | кавычки вокруг значения |
| address.geo.lng | "81.1496" | строка | кавычки вокруг значения |
| company.name | "Romaguera-Crona" | строка | кавычки вокруг значения |
| website | "hildegard.org" | строка | кавычки вокруг значения |

Json3
address.geo.lat = "-37.3159"  тип: строка признак: кавычки вокруг значения 
address.geo.lng = "81.1496"  тип: строка признак: кавычки вокруг значения 
company.name = "Romaguera-Crona"  тип: строка признак: кавычки вокруг значения 
website =  "hildegard.org" тип: строка признак: кавычки вокруг значения 

Json4
Корень ответа: массив
Количество элементов: 5
Первый: путь [0].email, значение "Eliseo@gardner.biz"
Последний: индекс 4, путь [4].email, значение "Hayden@althea.biz"
Связь индекса и количества: индекс последнего = количество − 1

Json5
- Число полей: 8
- Все шесть типов: да (строка, число, булево, null, объект, массив)
- Первая ошибка валидатора: не было
- Итоговый вердикт: Valid JSON

Json6
1) моя ошибка: несовпадение скобок — объект открыт `{`, а закрыт `]`
   валидатор: E086 unclosed object, expected '}' (line 2, col 19)
   исправлено: { "a": 1, "b": "2" }
2) моя ошибка: точка с запятой вместо запятой
   валидатор: E001 unexpected character (0x3B) — line 1, col 9
   исправлено: { "a": 1, "b": 2 }
3)  моя ошибка: пропущена запятая между 3 и 4; круглая скобка вместо квадратной
   валидатор: E009 (нет запятой) и E001 (0x29 — круглая скобка)
   исправлено: `[1, 2, 3, 4]`
4) моя ошибка: True с большой буквы — в JSON только true строчными
   валидатор: E030 'True' is not valid JSON (line 1, col 8) — «this looks like a Python literal — use 'true'»
   исправлено: { "a": true }
5) моя ошибка: undefined нет в JSON — есть только null
   валидатор: E030 'undefined' is not valid JSON (line 1, col 18) — use 'null'
   исправлено: { "a": "x", "b": null }

  Json7 
- Строка поиска: "id": 3
- Объектов до найденного: 2
- Индекс найденного: 2
- title найденного объекта: "officia porro iure quia iusto qui ipsa ut modi"
- Путь: [2].title

Json8
Статус: 200
Content-Type: text/html; charset=utf-8
Первые два тега: <!DOCTYPE html> и <html>
JSON ли это: нет
Признак 1 (заголовок): Content-Type = text/html, а не application/json 
признак 2 (тело): начинается с `<`, а не с `{` или `[`

Json9
Запрос 1 (raw JSON)
- Content-Type запроса: application/json (видно в headers ответа httpbin)
- json в ответе: {"title": "T", "userId": "1"}
- form в ответе: {}
Запрос 2 (x-www-form-urlencoded)
- Content-Type запроса: application/x-www-form-urlencoded (в headers ответа httpbin)
- json в ответе: null
- form в ответе: {"title": "T", "userId": "1"}
Вывод
httpbin читает тело по Content-Type: application/json → парсит как JSON,
application/x-www-form-urlencoded → парсит как форму

Json10
- Объявление версии: <?xml version='1.0' encoding='us-ascii'?>
- Корневой тег: slideshow
- Вложенные теги: slide, title
- Атрибут: title="Sample Slide Show" (у корня) или type="all" (у slide)
- Пустой тег или аналог null: нет. Проверяла теги slide и title — все с содержимым

Json11
XML → JSON

Исходный XML:
<task id="5" done="true">
  <title>Купить хлеб</title>
  <tag>еда</tag>
  <tag>срочно</tag>
</task>

Результат в JSON:
{
  "id": "5",
  "done": "true",
  "title": "Купить хлеб",
  "tag": ["еда", "срочно"]
}

Решение по типам id и done: оба оставляю строками, потому что XML все значения считает текстом. Чтобы получить числа и булевы, нужна схема XSD.

JSON → XML
Исходный JSON:
{
  "city": "Казань",
  "metros": ["Кремлёвская", "Суконная"]
}

Результат в XML:
<?xml version="1.0" encoding="UTF-8"?>
<card>
  <city>Казань</city>
  <metros>
    <metro>Кремлёвская</metro>
    <metro>Суконная</metro>
  </metros>
</card>

Решение по city: оставляю тегом, а не атрибутом, потому что это данные, а не метаданные корневого элемента.

Валидатор про JSON: Valid JSON

Json12
- Строка: путь [0].name, значение "Leanne Graham"
- Число: путь [0].id, значение 1
- Объект: путь [0].address, поля: street, suite, city, zipcode, geo
- Массив: путь — корень ответа (весь ответ), 10 элементов
- Цифры как строка: путь [0].phone, значение "1-770-736-8031 x56442"
- Признак отличия: строка — в двойных кавычках, число — без кавычек
