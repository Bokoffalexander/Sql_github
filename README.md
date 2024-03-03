# SQL

**SQL** _postgres_

## Создание БД (две таблицы) с внешним ключом:

```sql
CREATE DATABASE cats_db;
```

```sql
CREATE TABLE shops
(
    id         BIGSERIAL PRIMARY KEY,
    shop       VARCHAR(99) NOT NULL
);
```

```sql
CREATE TABLE cats
(
    id         BIGSERIAL PRIMARY KEY,
    cat        VARCHAR(99) NOT NULL,
    id_shop    INTEGER NOT NULL,

    FOREIGN KEY (id_shop) REFERENCES shops(id) ON DELETE SET NULL
);
```

## Вставим значения в таблицы:

```sql
INSERT INTO shops VALUES (DEFAULT, 'Pets I love');
INSERT INTO shops VALUES (DEFAULT, 'Pets are inside');
INSERT INTO shops VALUES (DEFAULT, 'Pets are here');
```

```sql
INSERT INTO cats VALUES (DEFAULT, 'Murzik', 1);
INSERT INTO cats VALUES (DEFAULT, 'Barsik', 2);
INSERT INTO cats VALUES (DEFAULT, 'Lapsik', 3);
```

## Пример LEFT JOIN:

![](https://raw.githubusercontent.com/Bokoffalexander/Sql_github/main/LEFT_JOIN.png)

## Запрос LEFT JOIN 2-х таблиц кошки и магазины:

```sql

SELECT cats.cat, shops.shop FROM cats LEFT JOIN shops ON cats.id_shop = shops.id;

```
