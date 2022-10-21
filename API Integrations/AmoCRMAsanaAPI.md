## Tamara Priymenko. Business Analysis Space

### ТЗ на интеграцию AmoCRM и Asana

![Aspose Words 03287024-dbce-421d-b73b-d06f700eb9d8 001](https://user-images.githubusercontent.com/46677884/197208992-2d5af1cd-7c4e-4000-826d-fb67a7684202.png)

#### Создание задачи в Asana по кнопке из сделки AmoCRM

Когда я работаю со сделкой в AmoCRM, я хочу иметь возможность автоматически создать соответствующую задачу в Asana, чтобы сократить общее время на обработку сделок 

**Триггер:** Авторизация в **AmoCRM** и нажатие кнопки на экране сделки, находящейся на этапе "**Отправить в Asana**"

**Действие:** Создание задачи в **Asana** в секции "**На очереди**", где название задачи и ответственный за нее соответствуют названию сделки и ответственному из AmoCRM

![Aspose Words 03287024-dbce-421d-b73b-d06f700eb9d8 002](https://user-images.githubusercontent.com/46677884/197209062-a10c88fd-6270-438a-9d39-112f4ce88474.png)

#### Авторизация в AmoCRM

[Scope (список разрешений)](https://www.amocrm.ru/developers/content/oauth/scopes) – Действие или набор действий от имени пользователя, которые доступны для интеграции по протоколу OAuth.

Чтобы приложение/сервис смогли обращаться к API amoCRM, вам необходимо добавить интеграцию в разделе Интеграции. После заполнения минимальной формы amoCRM сгенерирует и отобразит необходимые для авторизации ключи, которые вы сможете использовать в процессе авторизации.

Некоторые ключи являются уникальными для интеграции и будут видны всегда только в том аккаунте, в котором вы создадите эту интеграцию, а аккаунт будет считаться аккаунтом разработчика. При этом все администраторы аккаунта смогут редактировать данную интеграцию.

Именно после создания интеграции у нее появляются два уникальных именно для нее параметра. Они будут использоваться независимо от аккаунта, в котором она будет включаться: Secret key и Integration ID, которые в дальнейшем будут использоваться при работе с авторизацией.

[Полный цикл получения доступа к данным](https://www.amocrm.ru/developers/content/oauth/step-by-step#request_to_api), начиная от регистрации новой интеграции.

#### Авторизация в Asana

Для авторизации также используется протокол [oAuth](https://developers.asana.com/docs/oauth) и рекомендуется получить и использовать [персональный токен](https://developers.asana.com/docs/authentication-quick-start) 

Базовый адрес для всех запросов к Asana API: <https://app.asana.com/api/1.0>

![Aspose Words 03287024-dbce-421d-b73b-d06f700eb9d8 002](https://user-images.githubusercontent.com/46677884/197209062-a10c88fd-6270-438a-9d39-112f4ce88474.png)

#### Взаимодействие с API

![Aspose Words 03287024-dbce-421d-b73b-d06f700eb9d8 003](https://user-images.githubusercontent.com/46677884/197209128-d43fb021-7d86-4326-9330-20847a708b14.png)**amoCRM  ![](Aspose.Words.03287024-dbce-421d-b73b-d06f700eb9d8.004.png)![Aspose Words 03287024-dbce-421d-b73b-d06f700eb9d8 004](https://user-images.githubusercontent.com/46677884/197209230-8186f2a8-b241-4b39-b33e-03e3826932de.png)**

Метод позволяет получить данные конкретной сделки по ID

|**Обязательный Параметр**|**Тип Данных**|**Описание**|
| :- | :- | :- |
|"name"|string|Название сделки|
|"responsible\_user\_id"|int|ID пользователя, ответственного за сделку|

![Aspose Words 03287024-dbce-421d-b73b-d06f700eb9d8 005](https://user-images.githubusercontent.com/46677884/197210492-18f0d1b2-d7f0-486e-9e72-c5d87e11f245.png)**Asana    ![Aspose Words 03287024-dbce-421d-b73b-d06f700eb9d8 006](https://user-images.githubusercontent.com/46677884/197209271-10b57d13-daaf-4f59-9f44-e8ec20a984af.png)**


Метод позволяет создать задачу по заданным параметрам 

Объект **"data"**


|**Параметр**|**Тип данных**|**Описание**|
| :- | :- | :- |
|"name"|string|Название сделки из AmoCRM|
|"assignee"|int|ID в Asana ответственного за задачу из AmoCRM|
|"assignee\_section"|int|GID секции "На очереди"|


#### Валидация
##### [Ошибки валидации данных](https://www.amocrm.ru/developers/content/crm_platform/error-codes) при выполнении некорректного запроса к AmoCRM
##### [Ошибки валидации данных](https://developers.asana.com/docs/errors) при выполнении некорректного запроса к Asana
**Пример ответа от Asana:** 

![изображение](https://user-images.githubusercontent.com/46677884/197211077-a35b1be5-9e9c-45c1-8c9a-cd845790184e.png)


![Aspose Words 03287024-dbce-421d-b73b-d06f700eb9d8 007](https://user-images.githubusercontent.com/46677884/197209337-afe03449-a177-434a-8f4d-4ed25be88696.png)


#### Ссылки

AmoCRM. Сделки: <https://www.amocrm.ru/developers/content/crm_platform/leads-api#lead-detail> 

Asana API. Создание задачи: <https://developers.asana.com/docs/create-a-task>  

