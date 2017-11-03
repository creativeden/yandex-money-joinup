

[![яндекс касса](/i/yakassalogo.png "Яндекс Касса")](https://kassa.yandex.ru) / [помощь](https://yandex.ru/support/checkout/) / [api-докуметация](https://kassa.yandex.ru/docs/checkout-api/#api-yandex-kassy), [api-гайды](https://kassa.yandex.ru/docs/guides/#bystryj-start), [YandexCheckout.js](https://kassa.yandex.ru/docs/checkout-js/#yandexcheckout-js)

Return_url. Рекомендации по реализации
======================================

### Один платеж, один `return_url`

> При [создании платежа](https://kassa.yandex.ru/docs/checkout-api/#sozdanie-platezha) в параметре `return_url` вы передаете ссылку, которая будет работать на любом этапе платежа как ссылка кнопки "вернуться в магазин". Определение статуса платежа в момент перехода на вашу страницу `return_url` должно выполняться через [запрос о статусе платежа](https://kassa.yandex.ru/docs/checkout-api/#informaciq-o-platezhe).

#### Как обрабатывать переходы

1. После перехода 

### Чего не будет

Сценарий, к которому привыкли пользователи нашего старого API и которого теперь не будет. В старом API было три ссылки:
* shopDefaultUrl - ссылка "вернуться в магазин", на странице платежа до момента осуществления оплаты;
* shopSuccessURL - ссылка на странице успеха платежа, после успешной оплаты;
* shopFailURL - ссылка на странице, которая отображается после нажатия кнопки "оплатить" и если оплата была не успешной (не достаточно средств, не пройден 3DS и т.д.)

Теперь только одна ссылка, значение которой передается в `return_url`.