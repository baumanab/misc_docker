FROM python:3.7.0

RUN pip install mlflow
RUN pip install psycopg2

RUN mkdir /mlflow/

CMD mlflow server \
    --backend-store-uri postgresql://admin:secret@postgres:5432/mlflow \
    --default-artifact-root /mlflow \
    --host 0.0.0.0