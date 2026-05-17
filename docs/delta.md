# Delta Lake

Delta Lake é uma camada de armazenamento transacional para Spark que oferece ACID, time travel e confiabilidade de escrita.

## DDL da tabela Delta

```sql
CREATE TABLE IF NOT EXISTS pedidos_delta (
    pedido_id STRING,
    cliente_id STRING,
    status STRING,
    valor_total DOUBLE,
    data_pedido DATE
) USING delta
LOCATION './warehouse/delta/pedidos_delta';
```

## INSERT

```sql
INSERT INTO pedidos_delta VALUES
('P001','C001','criado',120.50,DATE '2026-01-10'),
('P002','C002','criado',89.90,DATE '2026-01-11');
```

## UPDATE

```sql
UPDATE pedidos_delta
SET status = 'faturado'
WHERE pedido_id = 'P001';
```

## DELETE

```sql
DELETE FROM pedidos_delta
WHERE pedido_id = 'P002';
```

As operações acima estão implementadas no notebook `notebooks/delta_lake_demo.ipynb`.
