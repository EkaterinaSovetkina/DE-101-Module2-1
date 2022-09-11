# DE-101-Module2-1
Модели данных

Задание: составить модель данных для магазина Super Store (из модуля 1)

Схема "звезда". Разделила данные на таблицу фактов (данные о покупке, Sales_fact) и таблицы измерений - дата, регион, товар, покупатель, доставка.

Концептуальная модель данных

![2](https://user-images.githubusercontent.com/108063450/189538252-be3c2f9e-39e5-4a66-92e6-688e6a25298c.png)

Логическая модель данных

![star scheme](https://user-images.githubusercontent.com/108063450/189538264-3afb018c-9cae-47e1-880f-fed307a690e8.png)

Физическая модель данных

![3](https://user-images.githubusercontent.com/108063450/189538273-91bbae6b-970c-4860-8f88-b6fce584c6d6.png)

Скрипт на создание таблицы фактов о продаже

![4](https://user-images.githubusercontent.com/108063450/189538971-6411a3cc-8a60-4034-b074-dec4b088a94b.png)

Пример. Запрос на объединение таблицы Sales_fact с таблицами измерений Customer_dim и Ship_dim

``` js
SELECT Row_ID, Customer_ID, Customer_name, Ship_mode
FROM Sales_fact s
INNER JOIN Customer_dim c ON s.Customer_ID=c.Customer_ID
INNER JOIN Ship_dim sh ON s.Ship_ID=sh.Ship_ID;

```
