## Tamara Priymenko. Business Analysis Space

![Aspose Words 8f78dbe2-0f64-4054-99a9-87984a458556 001](https://user-images.githubusercontent.com/46677884/197335120-be76f905-ae07-4d66-a23d-d0a7dccbe44c.jpeg)

### Проектирование API для онлайн кинотеатра

Взаимодействие **Пользователь – Онлайн кинотеатр** для следующих сценариев:

1. Пользователь заходит на главную страницу
1. Пользователь открывает раздел с определенным жанром
1. Пользователь выбирает фильм и видит детальную информацию о нем

#### Use Case

![OnlineCinemaUseCasePlantTextUML](https://user-images.githubusercontent.com/46677884/197335243-322788df-ee70-4c50-8083-d50a7d7fc9dd.png)

[OnlineCinemaUseCasePlanttextUML.txt](https://github.com/tamaraprima/mywayinba/files/9844134/OnlineCinemaUseCasePlanttextUML.txt)

Архитектура нашего онлайн кинотеатра будет следующей: **Frontend – Backend - БД**

#### Sequence diagram

![OnlineCinemaSequenceDiagramPlantTextUML](https://user-images.githubusercontent.com/46677884/197335263-fdb81243-ad73-4efd-8326-e38aba95177f.png)

[OnlineCinemaSequenceDiagramPlanttextUML.txt](https://github.com/tamaraprima/mywayinba/files/9844141/OnlineCinemaSequenceDiagramPlanttextUML.txt)

Проектируем возможные методы с указанием предлагаемых параметров в виде простого текстового описания. 

#### Методы API

**Метод**: Получить данные для главной страницы

**Параметры запроса**: 

- Идентификатор пользователя
- Доступная  пользовательская информация
  - Геолокация
  - Язык интерфейса 

**Параметры ответа**: 

- Список разделов (“Новинки”, “Жанры”, “По категориям” и т.д.)
  - Идентификатор раздела
  - Информация о разделе 
    - Краткое описание
    - Картинка
    - Превью фильмов

**Метод**: Получить список фильмов в разделе

**Параметры запроса**: 

- Идентификатор раздела
- Фильтры
  - Жанр
  - Год
  - Режиссер
  - Рейтинг

**Параметры ответа**: 

- Список фильмов
  - Идентификатор фильма
  - Краткая информация о фильме
  - Превью

**Метод**: Получить информацию о фильме

**Параметры запроса**: 

- Идентификатор фильма

**Параметры ответа**: 

- Информация о фильме
  - Описание
  - Актерский состав
  - Отзывы
  - Трейлер
  - Основная информация


#### JSON представление объекта Фильм**

![Aspose Words 8f78dbe2-0f64-4054-99a9-87984a458556 004](https://user-images.githubusercontent.com/46677884/197335303-4ba272ca-9db6-45a8-9450-6a1d1b758265.png)

[OnlineCinemaFilmJSONjsonformatter.txt](https://github.com/tamaraprima/mywayinba/files/9844145/OnlineCinemaFilmJSONjsonformatter.txt)
