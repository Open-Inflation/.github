# An open source project to collect consumer inflation data worldwide

# Roadmap / Дорожная карта
### 1. Создание библиотек для парсинга популярных розничных магазинов, а именно:

> Библиотеки будут только предоставлять текущий каталог *(в виде JSON)* и сохранение изображений *(в виде изображения PNG/JPEG записанных в ОЗУ)* возвращаемых несколькими асинхронными функциями.

#### В России:

1. Продуктовых: [Чижик](https://github.com/Open-Inflation/chizhik_api) ✅ *(низкие цены)*, [Пятёрочка](https://github.com/Open-Inflation/pyaterochka_api) ✅ *(средний сегмент)*, Магнит ⛔ *(средний сегмент)* [^1], [Перекрёсток](https://github.com/Open-Inflation/perekrestok_api) ✅ *(дорогой сегмент)*
2. Околопродуктовых: [FixPrice](https://github.com/Open-Inflation/fixprice_api) ✅ *(товары для дома)* [^2]
3. Электроника: DNS 👷, Eldorado 🕒, Citilink 🕒, M.video 🕒

[^1]: Сайт крайне медленный, написан как монолитный web-сервер, из-за чего для разработки и поддержания библиотеки требуется сильно больше сил чем обычно.
[^2]: Функция для получения информации о продукте не реализована, так как эта информация вшита в html код, решил не делать парсер пока не будут написаны тесты.

### 1.2. Написанию unit-тестов

> Для поддержания работоспособности библиотек требуется создать инструментарий для постоянного контроля за их устареванием и оперативным исправлением

**Чижик *(Chizhik)***

* [![GitHub Actions](https://github.com/Open-Inflation/chizhik_api/workflows/API%20Tests%20Daily/badge.svg)](https://github.com/Open-Inflation/chizhik_api/actions?query=workflow%3A"API+Tests+Daily")

**Пятёрочка *(Pyaterochka)***

* Не создан

**Перекрёсток *(Perekrestok)***

* Не создан

**FixPrice**

* Не создан

### 2. Создание "сборочных конвееров"

> Скрипты отдельные для каждой страны *(по причине оптимизации разработки, и банов селлерами опредленных IP-диапазонов)*. Они будут формировать списки каталогов собирая их в единый формат *(структуру)*, а так же иконки товаров.
> Собранные таким образом изображения и информация каталога будет запакована в архив и в таком виде отправлена на сервер хранения.

***Этап не проработан.***

### 3. Создание центра хранения

Это единый сервер куда будут присылаться данные на регистрацию. Регистрация будет проходить из:
1. Дополнения базы данных новыми записями *(создание новой карточки товара, если позиция новая)*/*(обновление текущей карточки товара новой информацией (обновленной цене, рейтингу и т.п.))*
2. Обновление изображений: сохранение новых изображений для новых товаров, замена изображений для текущих товаров.

#### Сервер отвечает 2-мя способами:
1. Пользователь может запросить актуальный дамп (датасет)
2. Пользователь может общаться с сервером как с обычным каталогом

### 4. Создание сайта-интерфейса

> Информация будет запрашиваться из центра хранений для визуализации инфляции, информации об изменении карточек товаров и т.п.
