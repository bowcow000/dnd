# dnd

ЗАДАНИЕ/РЕШЕНИЕ/СКРИНШОТ

**#1 ЗАДАНИЕ:**
Выберите из таблицы orders все заказы

**РЕШЕНИЕ:**

```
SELECT * FROM orders;
```

**СКРИНШОТ:**

![image](https://github.com/user-attachments/assets/72e879df-c678-4c79-a638-86255e888035)


**#2 ЗАДАНИЕ:**
Выберите из таблицы orders все заказы кроме новых. У новых заказов status равен "new". Использовать in

**РЕШЕНИЕ:**

```
SELECT * FROM orders
WHERE not STATUS IN ('new')
```

**СКРИНШОТ:**

![image](https://github.com/user-attachments/assets/5e4db919-bb92-4f9b-8d1f-72dad829a440)

**#3 ЗАДАНИЕ:**
Выберите из таблицы orders все новые и отмененные заказы. У отмененных заказов status равен "cancelled". У новых заказов status равен "new".

**РЕШЕНИЕ:**

```
SELECT * FROM orders
WHERE STATUS IN ('new', 'cancelled')
```

**СКРИНШОТ:**

![image](https://github.com/user-attachments/assets/461764da-cc08-4d06-acd1-d852d708564e)

**#4 ЗАДАНИЕ:**
Выберите из таблицы orders все заказы содержащие более 3 товаров (products_count).
Вывести нужно только номер (id) и сумму (sum) заказа.

**РЕШЕНИЕ:**

```
SELECT id,sum FROM orders
WHERE products_count > 3
```

**СКРИНШОТ:**

![image](https://github.com/user-attachments/assets/85494cbd-ac27-424a-8fff-501665c80438)



