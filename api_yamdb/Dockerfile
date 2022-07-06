FROM python:3.7-slim

WORKDIR /app

COPY . .

RUN pip install -r requirements.txt --no-cache-dir

WORKDIR /app/api_yamdb/

CMD ["gunicorn", "api_yamdb.wsgi:application", "--bind", "0:8000"]
