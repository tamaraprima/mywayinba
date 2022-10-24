## Tamara Priymenko. Business Analysis Space

### Создание отчета в Qlik Sense на основе нескольких Excel таблиц данных

Все исходные данные в Excel, а также сам скрипт [тут](ETLQueryReporting)

#### ETL скрипт на SQL-like языке Qlik

Таблицы и все операции с ними взяты для примера. В итоговую модель данных берем лишь две из них

![изображение](https://user-images.githubusercontent.com/46677884/197364503-502f9e90-2da0-4073-9a43-1352405c4357.png)
![изображение](https://user-images.githubusercontent.com/46677884/197364509-d3a679ee-40d4-4ab8-b367-703299323156.png)

[QlikSQLLikeScript.txt](https://github.com/tamaraprima/mywayinba/files/9845371/QlikETLScript.txt)

#### Модель данных, используемая для отчета

Предполагаем, что остальные таблицы были выделены в отдельные скрипты 

![изображение](https://user-images.githubusercontent.com/46677884/197364648-1e220bfa-d1df-4bac-9641-93a759d30200.png)

#### Пример простого отчета в Qlik на основе полученных данных

![SimpleReport](https://user-images.githubusercontent.com/46677884/197364538-c438ff26-f65e-47f7-bb56-55f59e82480f.jpg)
