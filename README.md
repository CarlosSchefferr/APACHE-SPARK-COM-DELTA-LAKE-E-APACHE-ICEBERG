# APACHE SPARK COM DELTA LAKE E APACHE ICEBERG

Projeto acadêmico com ambiente único para executar **PySpark + JupyterLab + Delta Lake + Apache Iceberg** e documentar o trabalho com **MkDocs**.

## 1) Estrutura do projeto

```text
.
├── docs/
│   ├── assets/er_model.svg
│   ├── delta.md
│   ├── iceberg.md
│   ├── index.md
│   └── pyspark.md
├── notebooks/
│   ├── cenario_modelagem.ipynb
│   ├── delta_lake_demo.ipynb
│   └── iceberg_demo.ipynb
├── mkdocs.yml
├── pyproject.toml
└── README.md
```

## 2) Pré-requisitos

- **Python 3.11+**
- **Java 17** (recomendado para Spark 3.5)
- **Poetry** (gerenciador único do projeto)
- Git

### Instalar Poetry

Documentação oficial: <https://python-poetry.org/docs/#installation>

```bash
pip install poetry
```

## 3) Configuração do ambiente

No diretório do repositório:

```bash
poetry install
```

Ativar shell virtual do Poetry:

```bash
poetry shell
```

> Alternativa: executar comandos com `poetry run <comando>` sem ativar shell.

## 4) Abrir JupyterLab

```bash
poetry run jupyter lab
```

Depois, abrir os notebooks em `notebooks/`:

- `cenario_modelagem.ipynb`
- `delta_lake_demo.ipynb`
- `iceberg_demo.ipynb`

## 5) Bibliotecas e versões principais

Versões declaradas em `pyproject.toml`:

- `pyspark==3.5.1`
- `delta-spark==3.2.0`
- `jupyterlab^4.2`
- `mkdocs^1.6`
- `mkdocs-material^9.5`

## 6) O que foi implementado

- Notebook de **cenário/modelagem** com modelo ER, descrição da fonte e DDL.
- Notebook de **Delta Lake** com `INSERT`, `UPDATE`, `DELETE`.
- Notebook de **Iceberg** com `INSERT`, `UPDATE`, `DELETE`.
- Documentação **MkDocs** com 4 páginas:
  - Contextualização
  - Apache Spark (PySpark)
  - Apache Iceberg
  - Delta Lake

## 7) Build local do MkDocs

```bash
poetry run mkdocs build
```

Servidor local de documentação:

```bash
poetry run mkdocs serve
```

Acesso local padrão: <http://127.0.0.1:8000>

## 8) Publicação em URL pública (GitHub Pages)

Executar:

```bash
poetry run mkdocs gh-deploy
```

URL esperada:

<https://carlosschefferr.github.io/APACHE-SPARK-COM-DELTA-LAKE-E-APACHE-ICEBERG/>

## 9) Referências utilizadas

- DataWay BR (YouTube)
- Projeto Spark + Delta: <https://github.com/jlsilva01/spark-delta>
- Projeto Spark + Iceberg: <https://github.com/jlsilva01/spark-iceberg>
- Apache Spark: <https://spark.apache.org/docs/latest/api/python/>
- Delta Lake: <https://docs.delta.io/latest/index.html>
- Apache Iceberg: <https://iceberg.apache.org/docs/latest/spark-getting-started/>
