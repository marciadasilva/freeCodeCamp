---
title: SQL Aliases
localeTitle: Aliases SQL
---
## Aliases SQL

## Usando o AS para atribuir nomes significativos ou mais simples

Você pode usar o AS para atribuir um nome a uma coluna de dados que você está selecionando ou que foi calculada.

```sql
SELECT user_only_num1 AS AgeOfServer, (user_only_num1 - warranty_period) AS NonWarrantyPeriod FROM server_table 
```

Isso resulta na saída como abaixo.

```text
+-------------+------------------------+ 
 | AgeOfServer | NonWarrantyPeriod      | 
 +-------------+------------------------+ 
 |         36  |                     24 | 
 |         24  |                     12 | 
 |         61  |                     49 | 
 |         12  |                      0 | 
 |          6  |                     -6 | 
 |          0  |                    -12 | 
 |         36  |                     24 | 
 |         36  |                     24 | 
 |         24  |                     12 | 
 +-------------+------------------------+ 
```

Você também pode usar o AS para atribuir um nome a uma tabela para facilitar a referência nas junções.

```sql
SELECT ord.product, ord.ord_number, ord.price, cust.cust_name, cust.cust_number FROM customer_table AS cust 
 
 JOIN order_table AS ord ON cust.cust_number = ord.cust_number 
```

Isso resulta na saída como abaixo.

```text
+-------------+------------+-----------+-----------------+--------------+ 
 | product     | ord_number | price     | cust_name       | cust_number  | 
 +-------------+------------+-----------+-----------------+--------------+ 
 |     RAM     |   12345    |       124 | John Smith      |  20          | 
 |     CPU     |   12346    |       212 | Mia X           |  22          | 
 |     USB     |   12347    |        49 | Elise Beth      |  21          | 
 |     Cable   |   12348    |         0 | Paul Fort       |  19          | 
 |     Mouse   |   12349    |        66 | Nats Back       |  15          | 
 |     Laptop  |   12350    |       612 | Mel S           |  36          | 
 |     Keyboard|   12351    |        24 | George Z        |  95          | 
 |     Keyboard|   12352    |        24 | Ally B          |  55          | 
 |     Air     |   12353    |        12 | Maria Trust     |  11          | 
 +-------------+------------+-----------+-----------------+--------------+ 

```