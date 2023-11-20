FROM python:3.10-alpine

ENV PYTHONUNBUFFERED 1
ENV PYTHONDONTWRITEBYTECODE 1

WORKDIR /app/api

COPY requeriments.txt /app/api/

# Build psycopg2 from source -- add required dependencies
RUN apk add --virtual .build-deps --no-cache postgresql-dev gcc python3-dev musl-dev && \
        pip install --no-cache-dir -r requeriments.txt && \
        apk --purge del .build-deps
        
COPY . /app/api/

EXPOSE 8000

CMD ["python", "manage.py", "runserver", "0.0.0.0:8000"]