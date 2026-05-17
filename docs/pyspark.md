# Apache Spark (PySpark)

O PySpark é a API Python do Apache Spark, usada para processamento distribuído de dados em larga escala.

## Sessão Spark base

```python
from pyspark.sql import SparkSession

spark = (
    SparkSession.builder
    .appName("spark-delta-iceberg")
    .master("local[*]")
    .getOrCreate()
)
```

## Catálogo para Iceberg

```python
spark = (
    SparkSession.builder
    .appName("iceberg-demo")
    .master("local[*]")
    .config("spark.sql.extensions", "org.apache.iceberg.spark.extensions.IcebergSparkSessionExtensions")
    .config("spark.sql.catalog.demo", "org.apache.iceberg.spark.SparkCatalog")
    .config("spark.sql.catalog.demo.type", "hadoop")
    .config("spark.sql.catalog.demo.warehouse", "./warehouse/iceberg")
    .config("spark.jars.packages", "org.apache.iceberg:iceberg-spark-runtime-3.5_2.12:1.5.2")
    .getOrCreate()
)
```

## Boas práticas do trabalho

- Usar o mesmo ambiente Poetry para notebooks e documentação.
- Versionar notebooks com células executáveis e markdown explicativo.
- Garantir comandos DDL e DML reproduzíveis localmente.
