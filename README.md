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

``
CREATE TABLE `Sales_fact`
(
 `Row_ID`      integer NOT NULL ,
 `Region_ID`   serial NOT NULL ,
 `Customer_ID` serial NOT NULL ,
 `Product_ID`  serial NOT NULL ,
 `Date_ID`     serial NOT NULL ,
 `Ship_ID`     serial NOT NULL ,
 `Order_ID`    varchar(15) NOT NULL ,
 `Sales`       numeric(9,4) NOT NULL ,
 `Quantity`    integer NOT NULL ,
 `Discount`    numeric(4,2) NOT NULL ,
 `Profit`      numeric(21,16) NOT NULL ,
 `Return`      varchar(3) NULL ,

PRIMARY KEY (`Row_ID`, `Region_ID`, `Customer_ID`, `Product_ID`, `Date_ID`, `Ship_ID`),
KEY `FK_2` (`Region_ID`),
CONSTRAINT `FK_1` FOREIGN KEY `FK_2` (`Region_ID`) REFERENCES `Region_dim` (`Region_ID`),
KEY `FK_3` (`Customer_ID`),
CONSTRAINT `FK_2` FOREIGN KEY `FK_3` (`Customer_ID`) REFERENCES `Customer_dim` (`Customer_ID`),
KEY `FK_4` (`Product_ID`),
CONSTRAINT `FK_3` FOREIGN KEY `FK_4` (`Product_ID`) REFERENCES `Product_dim` (`Product_ID`),
KEY `FK_5` (`Date_ID`),
CONSTRAINT `FK_4` FOREIGN KEY `FK_5` (`Date_ID`) REFERENCES `Date_dim` (`Date_ID`),
KEY `FK_6` (`Ship_ID`),
CONSTRAINT `FK_5` FOREIGN KEY `FK_6` (`Ship_ID`) REFERENCES `Ship_dim` (`Ship_ID`)
);
``

