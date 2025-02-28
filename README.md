## Лабораторная работа №1 [15.02.2025]
### Таблица
![0_table](https://github.com/user-attachments/assets/d72a275b-8c4b-4cda-9a78-91d3b1837a2b)

![](/LabW1/0_table.png)
### Задание №1
Выберите из таблицы orders все заказы
![1](https://github.com/user-attachments/assets/593567ce-fa65-4be0-88ab-247d8b9e1c2b)

![](/LabW1/1.png)

```
SELECT * FROM orders;
```
### Задание №2
Выберите из таблицы orders все заказы кроме новых. У новых заказов status равен "new". Использовать in
![2](https://github.com/user-attachments/assets/5ef0a9d7-da66-4834-ba7d-e35a1b54b0ba)

![](/LabW1/2.png)

```
SELECT * FROM orders WHERE status IN ('cancelled','in_progress','delivery')
```
### Задание №3
Выберите из таблицы orders все новые и отмененные заказы. У отмененных заказов status равен "cancelled". У новых заказов status равен "new"
![3](https://github.com/user-attachments/assets/00374a9f-dc33-4d56-b687-62ffeafaed85)

![](/LabW1/3.png)

```
SELECT * FROM orders WHERE status = 'new' OR status = 'cancelled'
```
### Задание №4
Выберите из таблицы orders все заказы содержащие более 3 товаров (products_count).
Вывести нужно только номер (id) и сумму (sum) заказа
![4](https://github.com/user-attachments/assets/0ce1a15c-e506-4cb0-aea8-d990df8c8414)

![](/LabW1/4.png)

```
SELECT id,sum FROM orders WHERE products_count > 3
```
## Лабораторная работа №2 [22.02.2025]
### Задание №161
#### Таблица
![0_table](https://github.com/user-attachments/assets/b528b4ff-9908-461c-aaf9-ac1d65f970ca)

![](/LabW2/161/0_table.png)

1) Выберите из таблицы orders 3 самых дешевых заказа за всё время.
Данные нужно отсортировать в порядке убывания цены.
Отмененные заказы не учитывайте.
![1](https://github.com/user-attachments/assets/87bff77b-73e7-48e2-b24c-e5957aa85ef4)

![](/LabW2/161/1.png)

```
select * from orders where status in('new','in_progress','delivery') order by sum desc limit 3;
```
2) Выберите из таблицы orders 2 самых дорогих заказов за всё время.
Данные нужно отсортировать в порядке убывания цены.
Отмененные заказы не учитывайте.
![2](https://github.com/user-attachments/assets/9f998151-11e4-4138-81f6-1a0d44cea986)

![](/LabW2/161/2.png)

```
select * from orders where status in('new','in_progress','delivery') order by sum desc limit 2;
```
### Задание №166
#### Таблица
![0_table](https://github.com/user-attachments/assets/54c76e7a-3720-4863-8110-d9bd81538449)

![](/LabW2/166/0_table.png)

3) Добавьте в таблицу orders данные о новом заказе стоимостью 8000 рублей. В заказе 4 товара (products).
![1](https://github.com/user-attachments/assets/43b060b4-093c-425f-af6a-af996689814e)

![](/LabW2/166/1.png)

```
insert into orders (id, products, sum) value (6, 4, 8000);
```
#### Результат:
![1_result](https://github.com/user-attachments/assets/eaf78441-9a10-4a1f-bbe4-6464cc34a7e5)

![](/LabW2/166/1_result.png)

### Задание №167
#### Таблица

![](/LabW2/167/0_table.png)

4) Добавьте в таблицу products новый товар — «VR-очки», стоимостью 70000 рублей в количестве (count) 2 штук.
   
![](/LabW2/167/1.png)

```
insert into products (id, name, count, price) value (7, 'VR-очки', 2, 70000);
```
#### Результат:

![](/LabW2/167/1_result.png)

### Задание №172
#### Таблица

![](/LabW2/172/0_table.png)

5) В таблицу products внесли данные с ошибкой, вместо "PS5" в наименовании написали IMAC. Исправьте ошибку.

![](/LabW2/172/1.png)

```
update products set name='PS5' where id=7;
```
#### Результат:

![](/LabW2/172/1_result.png)
