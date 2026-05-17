# Apache Iceberg

Apache Iceberg é um formato de tabela open table format para data lakes com foco em confiabilidade de metadados, evolução de esquema e performance.

## DDL da tabela Iceberg

```sql
CREATE TABLE IF NOT EXISTS demo.default.pedidos_iceberg (
    pedido_id STRING,
    cliente_id STRING,
    status STRING,
    valor_total DOUBLE,
    data_pedido DATE
) USING iceberg;
```

## INSERT

```sql
INSERT INTO demo.default.pedidos_iceberg VALUES
('P001','C001','criado',120.50,DATE '2026-01-10'),
('P002','C002','criado',89.90,DATE '2026-01-11');
```

## UPDATE

```sql
UPDATE demo.default.pedidos_iceberg
SET status = 'faturado'
WHERE pedido_id = 'P001';
```

## DELETE

```sql
DELETE FROM demo.default.pedidos_iceberg
WHERE pedido_id = 'P002';
```

As operações acima estão implementadas no notebook `notebooks/iceberg_demo.ipynb`.
