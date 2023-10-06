# data-engineering-swiss-army-knife

A collection of various tools, notebooks and virtual environments for a number of data engineering task.

## Table of Contents

- [data-engineering-swiss-army-knife](#data-engineering-swiss-army-knife)
  - [Table of Contents](#table-of-contents)
  - [Notebooks](#notebooks)
    - [Postgres Parquet ingest](#postgres-parquet-ingest)

## Notebooks

### Postgres Parquet ingest

This notebook provides the tooling for ingesting parquet files of an AWS RDS backup in a S3 bucket into a postgres database.

It allows to specify the databases, schemas or tables that should be read from the parquet files and ingested into the database. Schema and tables names can be altered on the fly with an template string. The notebook also creates the schemas and tables in the database if they do not exist.

The notebook is available [here](notebooks/postgres-parquet-ingest/postgres_parquet_ingest.ipynb). In order to use the notebook, create the virtual environment that the notebook is using. The virtual environment can be created using the following command:

```bash
cd notebooks/postgres_parquet_ingest
pipenv install
pipenv run python -m ipykernel install --user --name=postgres_parquet_ingest
pipenv run jupyter notebook
```

This will install the necessary dependencies (`S3Path`, `SQLAlchemy`, `pandas` and others) and create a virtual environment for the notebook. The virtual environment will be named `postgres_parquet_ingest`. The notebook can then be started by running `jupyter notebook` in the same directory. The notebook will be available in the browser at `http://localhost:8888/notebooks/postgres_parquet_ingestion.ipynb`.
