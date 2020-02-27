# Работа с API

## Доступ
API Online использует basic авторизацию. Необходимо получить токен для доступа к API.

Точка входа тестового контура расположена по адресу: https://test-api-online.ecredit.one

Точка входа production контура в данный момент находится в стадии модернизации. Сейчас боевая версия расположена по адресу: https://api-online-test.ecredit.one

Но в ближайшем будущем эта точку доступа изменится на https://api-online.ecredit.one

## Swagger

Форма для тестирования запросов расположена по адресу `https://test-api-online.ecredit.one/openapi/index.html`

Скачать файл API в формате Open Api можно [по ссылке](https://test-api-online.ecredit.one/site/swag?download=1)

## Формат вызова
URL запроса строится по такой схеме:

`/{version}/{method_group}/{method_name}?access-token=xxxxx`

`version` - версия API. На текущий момент используется версия `v1`

`method_group` - имя группы методов, например, application или dictionary

`method_name` - имя метода

`access-token` - имя параметра, в котором будет передан секретный токен для доступа к API

Например, чтобы получить список брендов, запрос будет выглядеть вот так:

`/v1/dictionary/brand?access-token=xxx`

## Формат ответа

error_code - код ошибки. Если 200, то запрос отработал без ошибок

error_text - уточняющий текст ошибки

response - тело ответа. Зависит от конкретного метода

id - служебное поле

context - окружение в котором отработал запрос. [Описание контекста](../methods/context.md)

```json
{
    "error_code": 200,
    "error_text": "Ok",
    "response": {
        "client_application_id": "",
        "application_id": 383,
        "notice": {
            "message": null
        }
    },
    "id": null,
    "context": {
        "dealer_id": null,
        "user_id": null,
        "environment": "12",
        "ecredit_api_url": "https://test2-auto.e-credit.one"
    }
}
```
